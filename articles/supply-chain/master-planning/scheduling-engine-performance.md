---
title: Migliorare le prestazioni del motore di pianificazione
description: In questo argomento vengono fornite informazioni sul motore di pianificazione e su come migliorarne le prestazioni.
author: ChristianRytt
manager: tfehr
ms.date: 09/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19311
ms.assetid: 5ffb1486-2e08-4cdc-bd34-b47ae795ef0f
ms.search.region: Global
ms.search.industry: ''
ms.author: kamaybac
ms.search.validFrom: 2020-09-03
ms.dyn365.ops.version: ''
ms.openlocfilehash: 0b55d0e94b40adf232e6b5cc3a9fb422e4539340
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5246767"
---
# <a name="improve-scheduling-engine-performance"></a>Migliorare le prestazioni del motore di pianificazione

[!include [banner](../includes/banner.md)]

Il motore di pianificazione delle risorse viene utilizzato quando si pianificano cicli di lavorazione per ordini di produzione pianificati e rilasciati. Il motore è stato originariamente rilasciato come parte di Dynamics AX 2012 e ha subito diversi miglioramenti da allora.

Il [problema di pianificazione in officina](https://en.wikipedia.org/wiki/Job_shop_scheduling) è un problema combinatorio estremamente complesso in cui il tempo di soluzione cresce esponenzialmente con il numero di variabili decisionali. Spesso, i clienti impostano cicli di produzione e dati correlati in modo tale da creare un problema di pianificazione che non può essere risolto in tempi ragionevoli anche con l'hardware più moderno. Questo argomento ti aiuterà a comprendere il motore di pianificazione e il modo in cui una configurazione specifica può influire sulle prestazioni.

Quando si tratta di migliorare le prestazioni della pianificazione, le linee guida generali raccomandano di ridurre la complessità del problema che il motore deve risolvere. Alcuni dei principali fattori che possono influire sulle prestazioni sono:

- Cicli di lavorazione con molte operazioni
- Cicli di lavorazione con operazioni parallele
- Operazioni con una quantità di risorse superiore a uno
- Operazioni con molte risorse applicabili
- Uso di collegamenti rigidi
- Uso di una capacità limitata
- Il numero di differenti calendari utilizzati
- Il numero di fasce orarie di lavoro giornaliere nel calendario
- La durata totale del ciclo di lavorazione
- Esecuzione di più motori di pianificazione in parallelo

## <a name="overview-of-basic-scheduling-flow"></a>Panoramica del flusso di pianificazione di base

Per comprendere come una determinata configurazione può influenzare le prestazioni, è importante capire lo svolgimento del processo, sia all'interno del motore che nel codice X++ circostante.

Il processo di base della pianificazione di un ordine comporta tre passaggi principali:

- **Caricamento dei dati** - I modelli di dati X++ vengono trasformati nel modello di dati interno del motore sotto forma di processi e vincoli.
- **Pianificazione** - È l'origine principale della pianificazione che elabora il modello e i vincoli dati e genera un risultato. Durante questo processo, il motore richiederà informazioni sull'orario di lavoro e le prenotazioni della capacità esistenti in X++ come necessario.
- **Salvataggio dei dati** - Il risultato del motore sotto forma di slot di prenotazione della capacità dei processi viene elaborato mediante il codice X++ per salvare le prenotazioni della capacità e aggiornare l'ora di inizio e di fine di processi/operazione/ordine.

## <a name="load-data-into-the-engine"></a>Caricare i dati nel motore

Il motore di pianificazione ha un modello di dati più astratto rispetto al database di Supply Chain Management perché è stato creato come motore generico in grado di gestire diverse origini di dati. I concetti di ciclo di lavorazione, operazioni secondarie e tempo di esecuzione devono essere "tradotti" nel modello di processo e vincolo generico che il motore espone. La logica per la creazione del modello include una quantità significativa di logica aziendale ed è diversa a seconda dei dati di origine. La classe X++ responsabile è `WrkCtrScheduler` e ha classi derivate per ordini di produzione pianificati, ordini di produzione rilasciati e previsioni di progetto.

Ad esempio, considera un ciclo di lavorazione nella tabella e nell'immagine seguenti, che sembra relativamente semplice.

| Oper. n. | Priorità | Tempo di attrezzaggio | Tempo di esecuzione | Tempo di attesa dopo | Quantità di risorse | Indietro |
| --- | --- | --- | --- | --- | --- | --- |
| 10 | Primaria | 1.00 | 2.00 | | 1 | 20 |
| 10 | Secondaria&nbsp;1 | | | | 1 | 20 |
| 20 | Primario | | 3.00 | 1.00 | 3 | 0 |

![Esempio di diagramma di ciclo di lavorazione](media/scheduling-engine-route.png "Esempio di diagramma di ciclo di lavorazione")

Quando inviato al motore, questo ciclo di lavorazione viene suddiviso in otto processi, come mostrato nell'illustrazione seguente (seleziona l'immagine per ingrandirla).

[![Processi del motore di pianificazione](media/scheduling-engine-jobs.png "Processi del motore di pianificazione")](media/scheduling-engine-jobs-large.png)

Il collegamento standard tra due processi è `FinishStart`, il che significa che l'ora di fine di un processo deve essere precedente all'ora di inizio di un altro processo. Poiché la configurazione deve essere eseguita dalla stessa risorsa che in seguito eseguirà il processo, ci sono vincoli `OnSameResource` tra gli stessi. Tra i processi per l'operazione primaria e secondaria per 10, ci sono collegamenti `StartStart` e `FinishFinish`, il che significa che i processi devono iniziare e finire allo stesso tempo, e ci sono vincoli `NotOnSameResource` , che impediranno l'utilizzo della stessa risorsa per l'operazione primaria e quella secondaria.

Per l'operazione 20, in cui la quantità di risorse è stata impostata su 3, il processo è stato suddiviso in tre processi distinti dove tutti i processi devono essere eseguiti contemporaneamente.
In questo caso, il gruppo di cicli di lavorazione è stato impostato in modo da non riservare capacità per la coda dopo i tempi prestabiliti ed è questo il motivo per cui c'è un solo processo per la coda che segue.

Il motore di pianificazione comprende solo la nozione di processo e non quella di operazione. Ciò significa che quando si esegue la pianificazione delle operazioni, anche le operazioni vengono suddivise in lavori, sebbene questi non vengano mantenuti nel database.

Per ogni processo, definiremo anche qual è il fabbisogno di capacità del processo (il numero di secondi necessari). A seconda di come sono stati definiti i fabbisogni delle risorse, per ogni processo possiamo anche inviare un elenco di tutte le potenziali risorse applicabili su cui il processo potrebbe essere eseguito e dei requisiti di capacità per quella specifica risorsa. Anche se l'elenco di risorse applicabili viene inviato durante la creazione del modello, il motore dovrà comunque garantire che l'assegnazione delle risorse sia effettivamente valida per l'intera durata del processo.

## <a name="scheduling-engine-internals"></a>Componenti interni del motore di pianificazione

### <a name="scheduling-engine-interface"></a>Interfaccia del motore di pianificazione

Per avere un'idea del funzionamento interno del motore, è meglio esaminare le funzionalità che espone esternamente. In X++, l'interfaccia principale è `WrkCtrSchedulerEngineInterface`. Questa interfaccia comporta i metodi descritti nelle sottosezioni seguenti.

#### <a name="general-engine"></a>Motore generale

| **Metodo** | **Scopo** |
| --- | --- |
| `run` | Pianifica tutti i processi caricati e restituisce il codice di errore. |
| `getJobSchedulingSequenceResult` | Ottiene il risultato della pianificazione e il primo processo di errore per la sequenza identificata da un processo specifico. |
| `validateJobCapacityReservations` | Convalida le prenotazioni della capacità per tutti i processi archiviati dal motore. |
| `setReservationsTimeStamp` | Invia un timestamp al motore impostato su tutte le nuove prenotazioni della capacità per i lavori pianificati nella cache del motore. |
| `addPropertyToGroupAggregation` | Aggiunge un prefisso di proprietà all'insieme di proprietà utilizzate quando la capacità viene aggregata. |
| `addResource` | Aggiunge una risorsa al pool di risorse del motore di pianificazione. |
| `addResourceGroup` | Aggiunge un gruppo di risorse al pool di gruppi di risorse del motore di pianificazione. |
| `addResourceGroupMembership` | Aggiunge una risorsa come membro a un gruppo di risorse. |
| `addOptimizationGoal` | Aggiunge un obiettivo di ottimizzazione della pianificazione (durata o priorità). |

#### <a name="individual-jobs"></a>Singoli processi

| **Metodo** | **Scopo** |
| --- | --- |
| `addJobInfo` | Aggiunge un record di informazioni di processo che informa il motore su un processo che deve essere pianificato. |
| `addConstraintJobEndsAt` | Aggiunge un vincolo in base al quale un processo deve terminare a una data e un'ora specificate. |
| `addConstraintJobStartsAt` | Aggiunge un vincolo in base al quale un processo deve iniziare a una data e un'ora specificate. |
| `addConstraintMaxJobDays` | Definisce il vincolo indicante che un processo può estendersi su un numero massimo di giorni specificato. |
| `addConstraintResourceRequirement` | Aggiunge il vincolo indicante che il processo deve essere pianificato su una risorsa specifica. |
| `addJobBindPriority` | Aggiunge una priorità di associazione di processo per una coppia (processo, livello di vincolo). Un valore di priorità più alto indica che le variabili di processo verranno associate prima. Il processo verrà elaborato prima dei processi con un valore di priorità inferiore nella stessa sequenza. |
| `addJobCapacity` | Aggiunge informazioni sul carico di capacità per un processo (come il runtime di processo richiesto) indipendentemente dalla risorsa su cui viene eseguito il processo. |
| `addJobResourceCapacity` | Aggiunge una risorsa all'insieme di risorse che possono essere utilizzate per eseguire un processo e indica la capacità necessaria durante l'esecuzione su quella risorsa. |
| `addJobGoal` | Aggiunge informazioni sull'obiettivo del processo per un livello di vincolo specifico (prima ora di fine o ultima ora di inizio). |
| `addJobResourcePriority` | Aggiunge la priorità da utilizzare quando un processo è pianificato su una risorsa. |
| `addJobResourceRuntime` | Specifica la durata del processo che dipende dalla risorsa su cui verrà pianificato il processo. |
| `addJobRuntime` | Specifica la durata del processo che è indipendente dalla risorsa su cui verrà pianificato il processo. |
| `scheduleJobOnResourceGroup` | Contrassegna un processo per la pianificazione a livello di gruppo di risorse. |
| `setJobResourcePreemptionAllowed` | Determina se la precedenza è consentita per un processo su una risorsa (se il motore è autorizzato a pianificare il processo in slot di capacità non contigui). |
| `setRequiredNumberOfResources` | Imposta il numero di risorse necessarie per pianificare un processo (solo per la pianificazione delle operazioni). |

#### <a name="constraints-between-jobs"></a>Vincoli tra processi

| **Metodo** | **Scopo** |
| --- | --- |
| `addJobLink` | Aggiunge un collegamento (come terminare\>iniziare) tra due processi. |
| `addConstraintEndsDelayed` | Definisce il vincolo secondo cui un processo non può terminare prima della fine di un altro processo più un ritardo. |
| `addConstraintJobListWorkingTimeIntersect` | Aggiunge un vincolo secondo cui gli slot di capacità riservati per i processi devono trovarsi su orari di lavoro che si sovrappongono per le due risorse utilizzate nei processi. |
| `addConstraintJobOverlap` | Aggiunge un vincolo che definisce il modo in cui i processi vengono sequenziati quando una data quantità di un articolo può essere spostata tra due risorse allorché l'elaborazione della prima risorsa non è ancora completata, di modo che la seconda risorsa possa iniziare l'elaborazione. |
| `addConstraintNotOnSameResource` | Aggiunge un vincolo per cui due lavori non devono essere pianificati sulla stessa risorsa. |
| `addConstraintOnSameResource` | Aggiunge un vincolo per cui due lavori devono utilizzare la stessa risorsa. |
| `addJobSameReservations` | Aggiunge un vincolo per cui un lavoro deve finire avendo prenotazioni della capacità per le stesse fasce orarie del processo primario. |
| `setPrimaryParallelJob` | Aggiunge informazioni su quale processo è quello primario in un set di processi paralleli. |

### <a name="solver"></a>Risolutore

Il motore stesso è essenzialmente un risolutore di vincoli specializzato a cui è aggiunta un'euristica personalizzata. Il risolutore si basa su due elementi principali: variabili e vincoli.

#### <a name="variable"></a>Variabile

Una variabile rappresenta un dominio di possibili valori. Il motore di pianificazione ha due tipi di variabili:

- **Variabile DateTime** - Ha un dominio di tutte le date e ore e il dominio può essere limitato avvicinando i limiti inferiore e superiore di tempo della variabile.
- **Variabile Resource** - Ha un dominio di risorse applicabili e il dominio può essere limitato eliminando le risorse dall'elenco.

#### <a name="constraint"></a>Vincolo

Un vincolo agisce sulle variabili limitandone i domini, ma dipende anche dalle variabili, quindi viene attivato quando queste cambiano. Il processo di "propagazione del vincolo" avviene quando un vincolo svolge la sua funzione principale e, in caso di operazione riuscita, lo segnala alla logica principale.

Una variabile è considerata associata quando non può essere limitata ulteriormente, il che per la variabile DateTime significa che il limite superiore e inferiore sono identici mentre per la variabile Resource significa che ha soltanto una singola risorsa applicabile. Quando tutte le variabili sono associate, viene trovata una soluzione.

### <a name="constraint-levels"></a>Livelli di vincolo

Quando la pianificazione viene eseguita come parte della fase di copertura della pianificazione dei fabbisogni materiali (MRP), gli ordini verranno pianificati a ritroso dalla data del fabbisogno. Tuttavia, se non è possibile trovare una pianificazione che inizi oggi o successivamente e termini prima della data del fabbisogno, la direzione della pianificazione cambierà in avanti a partire dalla data corrente.

Questa regola aziendale principale viene gestita organizzando i vincoli in livelli. Se non viene trovata alcuna soluzione quando si utilizzano i vincoli al livello più alto, i vincoli a quel livello vengono tutti eliminati e viene provato il livello inferiore. In pratica, ciò significa che per la pianificazione a ritroso, il modello conterrà un livello 1 con obiettivi di processo di ultima ora di inizio dato un vincolo massimo di ora di fine (la data del fabbisogno) e un livello 0 con obiettivi di processo di prima ora di fine dato un vincolo minimo di ora iniziale oggi.

### <a name="algorithm"></a>Algoritmo

I passaggi principali dell'algoritmo del motore sono:

1. Trovare sequenze (catene di lavoro) che possono essere risolte separatamente.
1. Cercare di trovare una soluzione iniziale per la sequenza per il livello di vincolo più alto.
    1. Ordinare i processi nella sequenza in base all'obiettivo e alle priorità del processo, di modo che sia possibile trovare un processo iniziale.
    1. Ripetere i lavori nella seguente sequenza:
        1. Trovare tutti i vincoli che devono essere propagati ed eseguire la propagazione.
        1. Se tutte le variabili per il processo sono state associate, è stata trovata una soluzione per quel processo.
        1. Se non è stato possibile associare una delle variabili senza violare i vincoli, eseguire il rollback dell'associazione della variabile, provare un valore diverso nel dominio (per la variabile Resource) ed eseguire nuovamente la propagazione del vincolo.
1. Se non è stata trovata alcuna soluzione, tutti i vincoli sul livello di vincolo corrente vengono rimossi, il livello di vincolo viene abbassato (se sono disponibili livelli inferiori) e viene ripetuta la ricerca della soluzione con il nuovo insieme di vincoli.
1. Se viene trovata una soluzione fattibile, viene avviata la fase di ottimizzazione, che tenterà di trovare una soluzione migliore fino al raggiungimento del timeout di ottimizzazione o all'esaurimento di tutte le combinazioni di risorse.

Il risolutore di vincoli non riconosce le specifiche dell'algoritmo di pianificazione. È nella definizione e combinazione dei vari vincoli che avviene la "magia".

### <a name="determining-working-times"></a>Determinazione degli orari di lavoro

La maggior parte dei vincoli (interni) nel motore controlla l'orario di lavoro e la capacità di una risorsa. In sostanza, l'attività consiste nel percorrere le fasce orarie lavorative di una risorsa a partire da un dato punto in una data direzione e trovare un intervallo sufficientemente lungo in cui la capacità (tempo) richiesta per i processi può rientrare.

A questo proposito, il motore deve conoscere gli orari di lavoro di una risorsa. Contrariamente ai dati del modello principale, gli orari di lavoro sono *caricati alla domanda*, a significare che vengono caricati nel motore secondo necessità. La ragione di questo approccio è che spesso in Supply Chain Management vi sono degli orari di lavoro che coprono un periodo molto lungo e in genere molti calendari, a tal punto che i dati da caricare sarebbero molto voluminosi.

Le informazioni di calendario vengono richieste dal motore in blocchi, invocando il metodo della classe X++ `WrkCtrSchedulingInteropDataProvider.getWorkingTimes`. La richiesta riguarda è un ID calendario specifico in un intervallo di tempo specifico. A seconda dello stato della cache del server in Supply Chain Management, ognuna di queste richieste può finire in diverse chiamate di database, il che richiede molto tempo (rispetto al tempo di calcolo puro). Inoltre, se il calendario contiene definizioni dell'orario di lavoro molto elaborate con molti intervalli di orari di lavoro al giorno, la durata del caricamento aumenta.

Quando i dati sull'orario di lavoro vengono caricati nel motore di pianificazione, questi vengono conservati nella cache interna per il calendario specifico, il che significa che se altri processi o risorse utilizzano lo stesso calendario, le successive ricerche possono essere eseguite rapidamente nella memoria. Una causa frequente di cattive prestazioni è l'utilizzo di un ID calendario distinto per ciascuna risorsa, perché i dati dovranno essere richiesti per ogni calendario, anche se il contenuto dei calendari potrebbe essere identico.

### <a name="finite-capacity"></a>Capacità limitata

Quando si utilizza la capacità finita, le fasce orarie di lavoro del calendario vengono suddivise e ridotte in base alle prenotazioni della capacità esistenti. Anche queste prenotazioni, come i calendari, vengono recuperate tramite la stessa classe `WrkCtrSchedulingInteropDataProvider`, ma utilizzano invece il metodo `getCapacityReservations`. Durante la pianificazione generale, vengono prese in considerazione le prenotazioni per il piano generale specifico e se abilitate nella pagina **Parametri di pianificazione generale**, sono incluse anche le prenotazioni da ordini di produzione stabilizzati. Allo stesso modo, quando si pianifica un ordine di produzione, è anche possibile includere prenotazioni di ordini pianificati esistenti, sebbene questo metodo non sia così frequente come l'altro.

L'utilizzo della capacità finita aumenterà la durata della pianificazione per diversi motivi:

- Il recupero delle informazioni sulla capacità dal database è un'operazione lenta e la memorizzazione nella cache lato server delle informazioni sulla capacità in genere non è efficace come per gli orari di lavoro perché non sono condivise tra le risorse come in genere i calendari.
- Il numero di fasce orarie di lavoro da percorrere aumenta a causa delle suddivisioni e in genere le fasce orarie per un periodo di tempo più lungo devono essere esaminate prima di poter trovare una soluzione.
- Al termine della pianificazione, è necessario eseguire un controllo per determinare la presenza di prenotazioni in conflitto (vedi la sezione "Esecuzione di motori di pianificazione in parallelo" per i dettagli).

### <a name="examining-the-resource-combinations"></a>Esame delle combinazioni di risorse

Se la sequenza di processi contiene solo i collegamenti `FinishStart` standard, nel senso che forma una catena semplice senza diramazioni, un risultato ottimale (dal punto di vista di un singolo ordine, non di più ordini) può essere ottenuto trovando la soluzione migliore per il primo processo e poi passando alla ricerca della soluzione migliore per il processo successivo. La migliore soluzione per un processo significa trovare la risorsa che può avere la data di inizio e fine del processo più vicina all'obiettivo del processo (nella pianificazione in avanti ciò significa avere la data di fine del processo il prima possibile) pur rispettando i vincoli.

Quando ci sono processi paralleli, trovare una soluzione può comportare l'analisi di diverse combinazioni di risorse. Il numero di possibili combinazioni di risorse è il prodotto del numero di risorse applicabili per i lavori paralleli connessi. Soprattutto quando si pianifica un ordine a ritroso da una data di fabbisogno, può essere necessario un po' di tempo prima che la logica determini che non esiste una soluzione al problema che renderà i lavori paralleli adatti prima della data odierna. In effetti, deve controllare tutte le combinazioni in quanto potrebbero esserci alcune risorse che presentano una maggiore efficacia o un altro calendario in grado d'offrire un risultato. Ciò significa che se non è stato impostato alcun limite di timeout, verrà eseguita per molto tempo prima di passare alla direzione in avanti.

Questa logica combinatoria significa anche che l'aggiunta di più risorse applicabili può rallentare il funzionamento del motore. Se si verificano problemi di prestazioni durante le operazioni parallele e si esegue la pianificazione con una capacità infinita, è possibile risolverli in parte chiedendo allo sviluppatore dei cicli di lavorazione di decidere quale risorsa utilizzare e quindi di assegnare la risorsa direttamente all'operazione (perché il motore nella maggior parte dei casi finisce sempre per scegliere la stessa risorsa, quindi il risultato finale sarà lo stesso).

### <a name="hard-links"></a>Collegamenti reali

L'impostazione del tipo di collegamento tra due processi su Rigido, garantisce che non vi sia alcun intervallo temporale tra la fine di un processo e l'inizio di quello successivo. Ciò può essere molto utile in scenari in cui il metallo viene riscaldato in un processo e poi lavorato in quello successivo e non deve quindi avere il tempo di raffreddarsi.

Con i collegamenti flessibili standard e la programmazione in avanti, se il ciclo di lavorazione forma una catena semplice senza diramazioni, è possibile ottenere un risultato trovando una soluzione per il primo processo che soddisfi i relatiovi vincoli e quindi proseguendo lungo la catena propagando l'ora di fine dal processo precedente al processo successivo. Se il processo corrente non trova alcuna capacità, l'ora di inizio verrà spostata ulteriormente, senza alcuna conseguenza per i processi precedenti, creando potenzialmente intervalli tra i processi. Tuttavia, con i collegamenti rigidi (specialmente in relazione a capacità finite) nello stesso scenario, il fatto che un processo successivo nella catena non possa trovare capacità, significa che tutti i processi programmati precedenti dovranno essere "trascinati" uno a uno e quindi riprogrammati più volte. Soprattutto in scenari con un carico elevato per più risorse, i collegamenti rigidi possono causare una reazione a catena in cui i processi si influenzeranno a vicenda e sarà necessario eseguire una serie di iterazioni prima che il risultato si stabilizzi in una pianificazione fattibile.

## <a name="running-scheduling-engines-in-parallel"></a>Esecuzione di motori di pianificazione in parallelo

Quando si esegue la pianificazione come parte di un'esecuzione di pianificazione generale in cui vengono utilizzati gli helper, ciascuno dei thread degli helper della pianificazione generale può anche scegliere attività di pianificazione degli ordini di produzione. Ciò significa che più motori di pianificazione possono essere eseguiti contemporaneamente. Sebbene il multithreading in generale rappresenti un vantaggio altamente significativo in termini di prestazioni, vi sono anche alcuni aspetti negativi funzionali quando si tratta di pianificazione.

Nella MRP, tutti gli ordini di produzione per un determinato livello di distinta base sono programmati in sequenza di date di fabbisogno, il che significa che gli ordini con la prima data di fabbisogno devono essere pianificati per primi e quindi hanno le maggiori possibilità di ottenere la capacità di risorse disponibile. Tuttavia, con più motori che selezionano dall'elenco di ordini non pianificati, la sequenza non è più garantita, poiché uno potrebbe completarsi più velocemente dell'altro.

Inoltre, quando si esegue la pianificazione utilizzando una capacità finita e quando più istanze del motore tentano di pianificare ordini che potenzialmente utilizzano le stesse risorse nello stesso intervallo di tempo, può verificarsi una race condition. Il numero di tali race condition è registrato nel campo **Conflitti di pianificazione** nella pagina dello storico dei piani generali. La logica di risoluzione dei conflitti è la seguente:

- Pianificare un ordine (senza blocco) e ottenere prenotazioni della capacità.
- Applicare il blocco.
- Verificare se esistono prenotazioni della capacità più recenti per le risorse pianificate nell'intervallo di tempo.
  - Se non esistono, scrivere la capacità e rilasciare il blocco.
  - Se esistono, rilasciare il blocco e ripianificare l'ordine dall'inizio.

Quindi, quando si esegue la pianificazione con più istanze del motore, il risultato non è completamente deterministico perché dipenderà dalla tempistica esatta di ogni thread.

## <a name="operation-scheduling-performance"></a>Prestazioni di pianificazione delle operazioni

Anche se la pianificazione delle operazioni è nota anche come pianificazione approssimativa della capacità, vista dal punto di vista del motore, può essere un problema più difficile da risolvere se viene utilizzata la capacità finita, poiché sono necessari più dati per determinare la fattibilità.

La capacità di un gruppo di risorse dipende da quali e quante risorse sono membri del gruppo di risorse. Un gruppo di risorse di per sé non ha alcuna capacità: ne avrà solo quando le risorse sono un membro del gruppo. Poiché l'appartenenza al gruppo di risorse può variare nel tempo, la capacità deve essere valutata ogni giorno.

Nella pianificazione delle operazioni, il calendario del gruppo di risorse viene utilizzato per determinare l'ora di inizio e di fine di ciascuna operazione. Ciò significa che il calendario del gruppo di risorse pone un limite al tempo che può essere pianificato per un'operazione in un giorno in un gruppo di risorse. Contrariamente al calendario delle risorse specifiche, i dati di efficienza del calendario vengono ignorati per il gruppo di risorse poiché indicano semplicemente gli orari di apertura e non la capacità effettiva.

Ad esempio, se l'orario di lavoro di un gruppo di risorse in una data specifica è compreso tra le 8:00 e le 16:00, un'operazione non può imporre più carico al gruppo di risorse di quanto possa gestirne in 8 ore, qualunque sia la capacità disponibile del gruppo di risorse in quel giorno. La capacità disponibile può tuttavia limitare ulteriormente il carico.

Il carico della pianificazione del processo su tutte le risorse incluse nel gruppo di risorse in un dato giorno viene considerato quando viene calcolata la capacità disponibile del gruppo di risorse nello stesso giorno. Per ogni data, il calcolo è:

*Capacità del gruppo di risorse disponibile = Capacità per le risorse nel gruppo in base al loro calendario &ndash; Caricamento pianificato del lavoro sulle risorse nel gruppo &ndash; Caricamento pianificato delle operazioni sulle risorse del gruppo &ndash; Caricamento pianificato delle operazioni sul gruppo di risorse*

Nella scheda **Requisiti risorsa** dell'operazione del ciclo di lavorazione, i requisiti delle risorse possono essere specificati utilizzando una risorsa specifica (nel qual caso l'operazione verrà pianificata utilizzando quella risorsa), per un gruppo di risorse, per un tipo di risorsa o per una o più abilità, competenze, corsi o certificati. Sebbene da un lato l'utilizzo di tutte queste opzioni offra una grande flessibilità nella progettazione dei cicli di lavorazione, dall'altro complica la programmazione per il motore poiché la capacità deve essere considerata per "proprietà" (il nome astratto utilizzato nel motore per abilità, competenza e così via).

La capacità del gruppo di risorse per una competenza è la somma della capacità di tutte le risorse nel gruppo di risorse che possiede la competenza in questione. Se una risorsa nel gruppo possiede una competenza, verrà presa in considerazione indipendentemente dal livello di capacità richiesto.

Nella pianificazione delle operazioni, la capacità disponibile per una determinata competenza di un gruppo di risorse verrà ridotta quando viene caricata con un'operazione che richiede la competenza in questione. Se l'operazione richiede più competenze, la capacità sarà ridotta per tutte le competenze richieste.

Per ogni data, il calcolo necessario è:

*Capacità disponibile per una capacità = Capacità per la capacità &ndash; Caricamento pianificato del lavoro sulle risorse con la capacità specifica, incluse nel gruppo di risorse &ndash; Caricamento pianificato delle operazioni sulle risorse con la capacità specifica, incluse nel gruppo di risorse &ndash; Caricamento pianificato delle operazioni sul gruppo di risorse stesso che richiedono la capacità specifica*

Ciò significa che se c'è un carico su una risorsa specifica, quel carico viene considerato nel calcolo della capacità disponibile del gruppo di risorse per competenza, perché il carico su una risorsa specifica riduce il relativo contributo alla capacità del gruppo di risorse per una competenza, indipendentemente dal fatto che il carico sulla risorsa specifica sia o meno per quella competenza specifica. Se è presente un carico a livello di gruppo di risorse, viene considerato nel calcolo della capacità disponibile del gruppo di risorse per competenza solo se il carico proviene da un'operazione che richiede la competenza specifica.

La logica sopra è complicata, poiché è la stessa per ogni tipo di "proprietà", quindi l'utilizzo della pianificazione delle operazioni con capacità finita richiede il caricamento di una quantità significativa di dati.

## <a name="viewing-scheduling-engine-input-and-output"></a>Visualizzazione di input e output del motore di pianificazione

Per ottenere dettagli specifici dell'input e dell'output del processo di pianificazione, abilita la registrazione selezionando **Amministrazione organizzazione \> Impostazioni \> Pianificazione \> Pannello di controllo tracciatura di programmazione**.

In questa pagina, seleziona dapprima **Abilita registrazione** nel riquadro azioni. Quindi esegui la pianificazione per l'ordine di produzione. Al termine, torna alla pagina **Pannello di controllo tracciatura di programmazione** e seleziona **Disabilita registrazione** nel riquadro azioni. Aggiorna la pagina. Una nuova riga verrà visualizzata nella griglia. Seleziona la nuova riga e seleziona **Scarica** nel riquadro azioni. Viene scaricata una cartella compressa contenente i seguenti file:

- **Log.txt** - Il file di registro che descrive i passaggi del motore. È molto elaborato e complesso, ma quando è utilizzato per sperimentare la configurazione dei cicli di lavorazione per risolvere i problemi di prestazioni la prima cosa da cercare è la differenza di tempo tra la prima e l'ultima riga, poiché indica il tempo esatto impiegato dall'utilità di pianificazione.
- **XmlModel.xml** - Contiene il modello creato in X++ e su cui viene eseguito il motore. Il `JobId` utilizzato nel file è correlato al `RecId` nella tabella di origine contenente i processi (`ReqRouteJob` o`ProdRouteJob`). Ciò che bisogna verificare in questo file è che le date in `ConstraintJobStartsAt` e `ConstraintJobEndsAt` siano quelle previste, che la proprietà `JobGoal` sia impostata correttamente e che i lavori siano correlati tra loro tramite i vincoli `JobLink`.
- **XmlSlots.xml** - Contiene tutti i orari di lavoro e le prenotazioni della capacità che il motore ha richiesto. Gli orari di lavoro e le prenotazioni del calendario saranno richiesti dal motore solo per i periodi di tempo in cui cerca di posizionare i processi (con un buffer aggiuntivo), quindi se il file contiene orari molto distanti nel futuro, potrebbe essere un'indicazione di un problema con la configurazione. I nodi `ResourceProperty` mostreranno il gruppo di risorse e le competenze a cui ogni risorsa è associata e per quali periodi.
- **Result.xml** - Contiene il risultato dell'esecuzione della pianificazione.

Tieni presente che la funzionalità di tracciabilità può alterare le prestazioni, quindi utilizzala solo per esaminare la pianificazione di ordini specifici. Se è attivata durante un'esecuzione di pianificazione generale, raggiungerà rapidamente il relativo limite di dimensioni e si arresterà.

## <a name="troubleshooting-performance"></a>Risoluzione dei problemi relativi alle prestazioni

Come si può capire leggendo tutte le sezioni precedenti, la configurazione e l'utilizzo del motore di pianificazione presentano alcune insidie che possono condurre a problemi di prestazioni. Il seguente elenco di controllo può essere utilizzato per la risoluzione di tali problemi. È importante esaminare tutti i punti poiché molto spesso i problemi sono dovuti a una combinazione di più fattori.

### <a name="performing-scheduling-as-part-of-mrp-when-it-is-not-needed"></a>Esecuzione della pianificazione nel quadro della pianificazione MRP quando non è necessaria

Anche se i cicli di lavorazione vengono utilizzati per scopi di controllo della produzione come la determinazione dei costi e il reporting, potrebbe non essere necessario prenderli in considerazione durante la pianificazione MRP. In alcuni casi, per la pianificazione sarà sufficiente avere un lead time di produzione standard specificato per l'articolo. Per disattivare la pianificazione dei cicli di lavorazione, imposta l'intervallo temporale di capacità su zero. Se è necessario eseguire la pianificazione, l'intervallo temporale di capacità deve essere impostato c on attenzione perché potrebbe non essere necessario prendere in considerazione i cicli di lavorazione per l'intera estensione dell'intervallo temporale di copertura della pianificazione MRP.

Nota che se l'ordine non è pianificato durante la pianificazione MRP, sarà invece necessario pianificarlo quando l'ordine pianificato viene stabilizzato. Ciò significa che il processo di stabilizzazione richiederà più tempo, quindi a seconda di quanti degli ordini pianificati suggeriti vengono stabilizzati, il miglioramento delle prestazioni durante la pianificazione MRP potrebbe essere annullato durante la stabilizzazione.

### <a name="route-with-unnecessary-operations"></a>Ciclo di lavorazione con operazioni non necessarie

Quando si progetta il ciclo di lavorazione, si è tentati di provare a modellare il mondo reale esattamente con tutti i passaggi della produzione. Sebbene ciò possa essere utile in alcuni casi, dal punto di vista delle prestazioni è controproducente poiché le dimensioni del modello su cui il motore deve lavorare aumentano (sia in termini di processi che di vincoli) e verranno eseguite più istruzioni SQL per l'inserimento e l'aggiornamento dei processi e delle prenotazioni della capacità. Inoltre, si ha l'effetto downstream di dover infine segnalare l'avanzamento nei processi, che può essere mitigato con registrazioni automatiche. Se i dati non vengono utilizzati, creano un carico non necessario.

Si consiglia di creare solo operazioni strettamente necessarie per la pianificazione (che in genere saranno le risorse collo di bottiglia) e/o per la determinazione dei costi. In alternativa, devi raggruppare molte operazioni distinte più piccole in un'operazione più grande che rappresenta una parte maggiore del processo.

### <a name="many-applicable-resources-for-an-operation"></a>Molte risorse applicabili per un'operazione

Il numero di risorse applicabili per un'operazione viene determinato mediante requisiti di risorse impostati nella relazione operativa. Il requisito può essere per una risorsa (individuale) specifica oppure può essere basato sull'appartenenza della risorsa a un gruppo di risorse o una competenza.

Se la pianificazione non viene eseguita utilizzando la capacità finita e tutte le risorse applicabili hanno lo stesso calendario ed efficienza, il motore di pianificazione finirà sempre per scegliere la stessa risorsa per un'operazione, ma solo dopo aver provato tutte le risorse applicabili per verificare se ce n'è una che è "migliore" delle altre. In questo caso, il carico della pianificazione può essere notevolmente ridotto semplicemente assegnando sempre una specifica risorsa all'operazione durante la progettazione del ciclo di lavorazione.

### <a name="route-with-parallel-operations"></a>Ciclo di lavorazione con operazioni parallele

Sebbene le operazioni parallele (primarie/secondarie) siano un potente strumento per modellare scenari in cui una macchina e un operatore sono entrambi necessari per eseguire un'attività specifica, sono anche l'origine di molti problemi di prestazioni. Se un requisito per una singola risorsa specifica viene assegnato sia all'operazione primaria che a quella secondaria, in genere non è un problema. Ma se ci sono molte risorse possibili per ciascuna delle operazioni, allora aggiunge una significativa complessità computazionale alla pianificazione.

Un'alternativa all'uso di operazioni parallele è modellare le coppie come risorse "virtuali" (che rappresenteranno quindi il team sempre associato all'operazione) o semplicemente non modellare una delle operazioni se non rappresenta un collo di bottiglia.

### <a name="route-with-quantity-of-resources-higher-than-1"></a>Ciclo di lavorazione con una quantità di risorse superiore a uno

Se si imposta la quantità di risorse necessarie per un'operazione su un valore superiore a uno, risulta effettivamente uguale all'utilizzo di operazioni primarie/secondarie poiché più lavori paralleli vengono inviati al motore. Tuttavia, per questo caso non è possibile utilizzare assegnazioni di risorse specifiche, poiché una quantità superiore a una richiede che più di una risorsa sia applicabile per l'operazione.

### <a name="excessive-use-of-finite-capacity"></a>Uso eccessivo di una capacità finita

L'utilizzo di una capacità finita richiede che il motore carichi le informazioni sulla capacità da un database e può avere un sovraccarico di calcolo in quanto sarà più difficile trovare una soluzione soprattutto negli ambienti in cui le risorse sono prenotate quasi alla loro capacità massima. Di conseguenza, è importante valutare attentamente se una risorsa ha davvero bisogno di utilizzare una capacità finita o se può essere prenotata in eccesso. Poiché l'importanza di non prenotare in eccesso le risorse a capacità finita è variabile, si consiglia di utilizzare l'opzione collo di bottiglia su una risorsa in combinazione con un valore distinto sul piano in "Intervallo temporale capacità per risorse collo di bottiglia". L'utilizzo del concetto di collo di bottiglia può consentire di abbassare il limite temporale generale della capacità finita.

### <a name="setting-hard-links"></a>Impostazione di collegamenti rigidi

Il tipo di collegamento standard del ciclo di lavorazione è *flessibile*, il che significa che è consentito un intervallo temporale tra l'ora di fine di un'operazione e l'inizio di quella successiva. Questa tolleranza può avere l'effetto indesiderabile di interrompere la produzione per un determinato periodo di tempo e quindi implicare un aumento del lavoro in corso se i materiali o la capacità non sono disponibili per una delle operazioni per un periodo molto lungo. Ciò non avviene con i collegamenti rigidi perché l'inizio devono essere perfettamente allineati. Tuttavia, l'impostazione di collegamenti rigidi complica il problema della pianificazione perché l'intersezione tra l'orario di lavoro e la capacità deve essere calcolata per due risorse delle operazioni. Se sono coinvolte anche operazioni parallele, ciò aggiunge un tempo di calcolo significativo. Se le risorse delle due operazioni hanno calendari diversi che non si sovrappongono affatto, il problema è irrisolvibile.

Si consiglia di utilizzare collegamenti rigidi solo quando strettamente necessario e valutare attentamente se è necessario per ciascuna operazione del ciclo di lavorazione.

Per ridurre il lavoro in corso senza applicare collegamenti rigidi, una soluzione è programmare due volte l'ordine scegliendo la direzione contraria per il secondo passaggio. Se la prima pianificazione è stata eseguita a ritroso dalla data di consegna, la seconda deve essere eseguita in avanti a partire dalla data di inizio pianificata. Ciò comporterà la compressione massima dei processi in modo da ridurre al minimo il lavoro in corso.

### <a name="separate-calendar-for-each-resource"></a>Calendario distinto per ogni risorsa

Una delle principali origini dati per il motore di pianificazione sono le informazioni del calendario, il cui caricamento dal database può risultare costoso. Poiché i calendari vengono generati in base a modelli, si sarebbe tentati di generare un calendario per ogni risorsa e quindi modificare le informazioni in questo calendario quando la risorsa ha tempi di inattività e altri problemi. Tuttavia, questa operazione limiterà notevolmente la capacità dei motori di memorizzare nella cache i dati del calendario poiché richiederebbe nuovi dati per ciascuna risorsa e può essere una fonte importante di problemi di prestazioni. Consigliamo invece di riutilizzare il più possibile i calendari tra le risorse e quindi di controllare le modifiche ai tempi di inattività assegnando un ID calendario diverso per un periodo.

### <a name="high-number-of-working-time-slots-per-calendar-day"></a>Numero elevato di fasce orarie di lavoro per giorno di calendario

Poiché il motore funziona esaminando ogni singola fascia oraria per la capacità, è utile ridurre al minimo il numero di fasce orarie per giorno di calendario. Ciò potrebbe essere fatto, ad esempio, valutando se è importante che la pianificazione risultante rifletta il fatto che i lavoratori hanno una pausa di 5 minuti ogni ora.

### <a name="large-or-none-scheduling-timeouts"></a>Timeout di pianificazione importanti (o inesistenti)

Le prestazioni del motore di pianificazione possono essere ottimizzate utilizzando i parametri presenti nella pagina **Parametri di pianificazione**. Le impostazioni **Timeout pianificazione abilitato** e **Timeout ottimizzazione pianificazione abilitato** devono essere sempre impostate su **Sì**. Se impostate su **No**, la pianificazione può potenzialmente essere eseguita all'infinito se è stato creato un ciclo di lavorazione non fattibile con molte opzioni.

Il valore di **Tempo di pianificazione per sequenza** determina il numero massimo di secondi durante i quali viene eseguita la ricerca di una soluzione per una singola sequenza (nella maggior parte dei casi una sequenza corrisponde a un singolo ordine). Il valore da utilizzare dipende molto dalla complessità del ciclo di lavorazione e da impostazioni come la capacità finita, ma un massimo di circa 30 secondi è un buon punto di partenza.

Il valore di **Timeout tentativi ottimizzazione** determina il numero massimo di secondi durante i quali viene eseguita la ricerca di una soluzione di quella trovata originariamente. Ciò influenzerà solo i cicli lavorativi che utilizzano operazioni parallele poiché queste rendono necessario testare diverse combinazioni.

> [!NOTE]
> I valori impostati per i timeout verranno applicati sia per la pianificazione degli ordini di produzione rilasciati sia per gli ordini pianificati nel quadro della pianificazione MRP. Di conseguenza, l'impostazione di valori molto alti potrebbe aumentare notevolmente il tempo di esecuzione della pianificazione MRP durante l'esecuzione di un piano con molti ordini di produzione pianificati.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]