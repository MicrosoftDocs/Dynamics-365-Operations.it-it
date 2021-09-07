---
title: Panoramica dei processi di importazione ed esportazione dati
description: Utilizzare l'area di lavoro Gestione dati per creare e gestire i processi di importazione ed esportazione di dati.
author: peakerbl
ms.date: 04/22/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: sericks
ms.custom: intro-internal
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4f9ae06893a8247828fa4d3c2cb40b9155043c87
ms.sourcegitcommit: 7aa7d756e1e98a53da62e03c608a9597ef9893ea
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/20/2021
ms.locfileid: "7404036"
---
# <a name="data-import-and-export-jobs-overview"></a>Panoramica processi di importazione ed esportazione dati

[!include [banner](../includes/banner.md)]

Per creare e gestire processi di importazione ed esportazione di dati si utilizza l'area di lavoro **Gestione dati**. Per impostazione predefinita, il processo di importazione ed esportazione crea una tabella di gestione temporanea per ciascuna entità nel database di destinazione. Le tabelle di gestione temporanea consentono di verificare, pulire o convertire i dati prima di spostarli.

> [!NOTE]
> In questo argomento si presuppone di aver acquisito dimestichezza con l'argomento [entità di dati](data-entities.md).

## <a name="data-importexport-process"></a>Processo di importazione/esportazione di dati
Di seguito vengono riportati i passaggi per l'importazione o l'esportazione di dati.

1. Creare un processo di importazione o esportazione in cui completare le seguenti attività:

    - Definire la categoria del progetto.
    - Identificare le entità da importare o esportare.
    - Impostare il formato dei dati per il processo.
    - Sequenziare le entità di modo che vengano elaborate in gruppi logici e in un ordine significativo.
    - Determinare se utilizzare le tabelle di gestione temporanea.

2. Verificare che i dati di origine e i dati di destinazione siano mappati correttamente.
3. Verificare la protezione per il processo di importazione o esportazione.
4. Eseguire il processo di importazione o di esportazione.
5. Verificare che il processo sia stato eseguito come previsto esaminando lo storico processi.
6. Pulire le tabelle di gestione temporanea.

Le altre sezioni di questo argomento forniscono ulteriori dettagli su ogni fase del processo.

> [!NOTE]
> Per aggiornare il modulo di importazione/esportazione dei dati per visualizzare i progressi più recenti, utilizzare l'icona di aggiornamento dei moduli. L'aggiornamento a livello del browser non è consigliato perché interromperebbe qualsiasi lavoro di importazione/esportazione che non viene eseguito in batch.

## <a name="create-an-import-or-export-job"></a>Creare un processo di importazione o di esportazione
Un processo di importazione o esportazione di dati può essere eseguito una sola volta oppure più volte.

### <a name="define-the-project-category"></a>Definire la categoria del progetto
Si consiglia di selezionare attentamente una categoria di progetto appropriata per il processo di esportazione o di importazione. Le categorie di progetto consentono di gestire i processi correlati.

### <a name="identify-the-entities-to-import-or-export"></a>Identificare le entità da importare o esportare
È possibile aggiungere specifiche entità a un processo di esportazione o di importazione oppure selezionare un modello da applicare. I modelli includono un elenco di entità in un processo. L'opzione **Applica modello** è disponibile dopo aver denominato e salvato il processo.

### <a name="set-the-data-format-for-the-job"></a>Impostare il formato dei dati per il processo
Quando si seleziona un'entità, è necessario selezionare il formato dei dati da esportare o importare. Si definiscono i formati utilizzando il riquadro **Impostazione origini dati**. Un formato di dati di origine è una combinazione **Tipo**, **Formato file**, **Delimitatore di riga** e **Delimitatore di colonna**. Sono inclusi anche altri attributi, ma questi sono quelli fondamentale da ricordare. Nella tabella riportata di seguito vengono elencate le combinazioni valide.

| Formato file            | Delimitatore di riga/colonna                       | Stile XML                 |
|------------------------|--------------------------------------------|---------------------------|
| Excel                  | Excel                                      | \-N/D-                     |
| XML                    | \-N/D-                                      | Elemento XML Attributo XML |
| Larghezza fissa, delimitata | Virgola, punto e virgola, tabulazione, barra verticale, due punti | \-N/D-                     |

### <a name="sequence-the-entities"></a>Sequenziare le entità
È possibile sequenziare le entità in un modello di dati o nei processi di importazione e esportazione. Quando si esegue un processo contenente più entità di dati, è necessario assicurarsi che le entità di dati siano sequenziate correttamente. Il sequenziamento delle entità deve essere eseguito in modo da poter risolvere qualsiasi dipendenza funzionale tra le entità. Se le entità non hanno dipendenze funzionali, possono essere programmate per l'importazione o l'esportazione parallela.

#### <a name="execution-units-levels-and-sequences"></a>Unità di esecuzione, livelli e sequenze
L'unità di esecuzione, il livello nell'unità di esecuzione e la sequenza di un'entità consentono di determinare l'ordine in cui i dati vengono esportati o importati.

- Le entità nelle differenti unità di esecuzione sono elaborate in parallelo.
- In ogni unità di esecuzione, le entità vengono elaborate in parallelo se hanno lo stesso livello.
- In ogni livello, le entità vengono elaborate in base al relativo numero di sequenza in tale livello.
- Dopo l'elaborazione di un livello, viene elaborato il livello successivo.

#### <a name="resequencing"></a>Risequenziamento
È possibile che si intenda sequenziare di nuovo le entità nelle situazioni seguenti:

- Se si utilizza un solo processo di dati per tutte le modifiche, è possibile utilizzare le opzioni di risequenziamento in modo da ottimizzare il tempo di esecuzione dell'intero processo. In questi casi, è possibile utilizzare l'unità di esecuzione per rappresentare il modulo, il livello per rappresentare l'area funzionale nel modulo e la sequenza per rappresentare l'entità. Utilizzando questo approccio, è possibile gestire i moduli in parallelo, ma anche in sequenza. Per assicurare una corretta esecuzione delle operazioni in parallelo, è necessario considerare tutte le dipendenze.
- Se si utilizzano più processi di dati (ad esempio un processo per ogni modulo), è possibile utilizzare il sequenziamento per modificare il livello e la sequenza delle entità per un'esecuzione ottimale.
- Se non vi sono dipendenze, è possibile sequenziare le entità in differenti unità di esecuzione per un'ottimizzazione massima.

Il menu **Risequenziamento** è disponibile quando si selezionano più entità. È possibile eseguire il risequenziamento in base alle opzioni relative a unità di esecuzione, livello o sequenza. È possibile impostare un incremento per il risequenziamento delle entità selezionate. L'unità, il livello e/o il numero di sequenza selezionato per ciascuna entità viene aggiornato in base all'incremento specificato.

#### <a name="sorting"></a>Ordinamento
È possibile utilizzare **Ordina per** per visualizzare l'elenco delle entità nell'ordine sequenziale.

### <a name="truncating"></a>Troncamento
Per i progetti di importazione, è possibile scegliere di troncare i record nelle entità prima dell'importazione. Questa opzione è utile se i record devono essere importati in un set di tabelle pulito. Per impostazione predefinita questa opzione è disattivata.

## <a name="validate-that-the-source-data-and-target-data-are-mapped-correctly"></a>Verificare che i dati di origine e i dati di destinazione siano mappati correttamente
Il mapping è una funzione disponibile per i processi di importazione e quelli di esportazione.

- Nel contesto di un processo di importazione, il mapping descrive quali colonne nel file di origine diventano colonne nella tabella di gestione temporanea. Di conseguenza, il sistema può determinare quale colonna di dati nel file di origine deve essere copiata in quale colonna della tabella di gestione temporanea.
- Nel contesto di un processo di esportazione, il mapping descrive quali colonne della tabella di gestione temporanea diventano le colonne nel file di origine.

Se i nomi di colonna nella tabella di gestione temporanea e nel file corrispondono, il sistema stabilisce automaticamente il mapping in base ai nomi. Tuttavia, se i nomi differiscono, le colonne non vengono mappate automaticamente. In questi casi, è necessario completare il mapping selezionando l'opzione **Visualizza mapping** per l'entità nel processo di dati.

Sono disponibili due visualizzazioni di mapping: **Visualizzazione mapping**, ovvero la visualizzazione predefinita, e **Dettagli mapping**. Un asterisco rosso (\*) identifica i campi obbligatori nell'entità. È necessario mappare questi campi per poter utilizzare l'entità. È possibile annullare il mapping di altri campi quando si utilizza l'entità. Per annullare il mapping di un campo, selezionare il campo nella colonna **Entità** o nella colonna **Origine** e quindi selezionare **Elimina la selezione**. Selezionare **Salva** per salvare le modifiche e chiudere la pagina per ritornare al progetto. È possibile utilizzare lo stesso processo per modificare il mapping da Origine a Gestione temporanea dopo l'importazione.

È possibile generare un mapping nella pagina selezionando **Genera mapping origine**. Il comportamento di un mapping generato è quello di un mapping automatico. Di conseguenza, è necessario mappare manualmente tutti i campi non mappati.

![Mapping dei dati.](./media/dixf-map.png)

## <a name="verify-the-security-for-your-import-or-export-job"></a>Verificare la protezione per il processo di importazione o esportazione
L'accesso all'area di lavoro **Gestione dati** può essere limitato, di modo che gli utenti non amministratori possano accedere solo a specifici processi di dati. L'accesso a un processo di dati implica l'accesso completo allo storico esecuzione di quel processo e l'accesso alle tabelle di gestione temporanea. Di conseguenza, è necessario assicurarsi di aver implementato i controlli di accesso appropriati quando si crea un processo di dati.

### <a name="secure-a-job-by-roles-and-users"></a>Proteggere un processo in base a ruoli e utenti
Utilizzare il menu **Ruoli applicabili** per limitare l'accesso al processo a uno o più ruoli di sicurezza. Solo gli utenti con quei ruoli avranno accesso al processo.

È inoltre possibile limitare l'accesso a un processo a specifici utenti. Quando si protegge un processo in base agli utenti anziché ai ruoli, il livello di controllo è maggiore se molteplici utenti sono assegnati a un ruolo.

### <a name="secure-a-job-by-legal-entity"></a>Proteggere un processo in base alla persona giuridica
I processi di dati sono globali per natura. Di conseguenza, se un processo di dati è stato creato e utilizzato in una persona giuridica, il processo sarà visibile in altre persone giuridiche nel sistema. Questo comportamento predefinito potrebbe essere preferibile in alcuni scenari di applicazione. Ad esempio, un'organizzazione che importa fatture mediante entità di dati potrebbe fornire un team di elaborazione delle fatture centralizzato che è responsabile della gestione degli errori nelle fatture per tutti i reparti dell'organizzazione. In questo scenario, per il team di elaborazione delle fatture centralizzato è utile avere accesso a processi di importazione delle fatture di tutte le persone giuridiche. Di conseguenza, il comportamento predefinito soddisfa il requisito a livello di persona giuridica.

Tuttavia, un'organizzazione potrebbe necessitare di avere team di elaborazione delle fatture per entità giuridica. In tal caso, un team in una persona giuridica deve avere accesso solo al processo di importazione delle fatture nella relativa persona giuridica. Per soddisfare questo requisito, è possibile configurare il controllo dell'accesso basato sulle persone giuridiche nei processi di dati utilizzando il menu **Persone giuridiche applicabili** nel processo di dati. Dopo la configurazione, gli utenti possono visualizzare solo i processi disponibili nella persona giuridica a cui hanno correntemente accesso. Per visualizzare i processi di un'altra persona giuridica, gli utenti devono accedere a quella persona giuridica.

Un processo può essere protetto in base a ruoli, utenti e persone giuridiche contemporaneamente.

## <a name="run-the-import-or-export-job"></a>Eseguire il processo di importazione o di esportazione
È possibile eseguire un processo una volta facendo clic sul pulsante **Importa** o **Esporta** dopo aver definito il processo. Per impostare un processo ricorrente, selezionare **Crea processo dati ricorrente**.

> [!NOTE]
> Un processo di importazione o esportazione può essere eseguito selezionando il pulsante **Importa** o **Esporta**. Questo pianificherà un processo batch da eseguire solo una volta. Il processo potrebbe non essere eseguito immediatamente se il servizio batch subisce una limitazione a causa del carico sul servizio batch. I processi possono anche essere eseguiti in modo sincrono selezionando **Importa adesso** o **Esporta adesso**. Questa selezione avvia immediatamente il processo e risulta utile se il batch non viene avviato a causa di una limitazione. I processi possono anche essere programmati per essere eseguiti in un secondo momento. Questo può essere fatto scegliendo l'opzione **Esegui in batch**. Le risorse batch sono soggette a limitazione, quindi il processo batch potrebbe non essere avviato immediatamente. L'utilizzo di un batch è l'opzione consigliata perché aiuta anche con grandi volumi di dati che devono essere importati o esportati. I processi batch possono essere pianificati per l'esecuzione in un gruppo batch specifico, che consente un maggior controllo da una prospettiva di bilanciamento del carico.

## <a name="validate-that-the-job-ran-as-expected"></a>Verificare che il processo è stato eseguito come previsto
Lo storico processi è disponibile per la risoluzione dei problemi e l'analisi dei processi di importazione e di esportazione. Le esecuzioni dello storico processi sono organizzate in base a intervalli di tempo.

![Intervalli dello storico processi.](./media/dixf-job-history.md.png)

Ogni esecuzione di processo fornisce i seguenti dettagli:

- Dettagli esecuzione
- Registro di esecuzione

I dettagli relativi all'esecuzione indicano lo stato di ciascuna entità di dati elaborata nel processo. Di conseguenza, è possibile trovare rapidamente le seguenti informazioni:

- Quali entità sono state elaborate
- Per un'entità, quanti record sono stati elaborati correttamente e quanti no
- I record di gestione temporanea per ogni entità

È possibile scaricare i dati di gestione temporanea in un file per i processi di esportazione, oppure scaricarlo come pacchetto per i processi di esportazione e importazione.

Dai dettagli di esecuzione è anche possibile aprire il registro di esecuzione.

## <a name="parallel-imports"></a>Importazioni parallele
Per accelerare l'importazione di dati, è possibile abilitare l'elaborazione parallela dell'importazione di un file se l'entità supporta le importazioni parallele. Per configurare l'importazione parallela per un'entità, è necessario seguire i seguenti passaggi.

1. Passare all'**Amministrazione sistema \> Aree di lavoro \> Gestione dati**.
2. Nella sezione **Importa/Esporta**, selezionare il riquadro **Parametri framework** per aprire la pagina **Parametri framework di importazione/esportazione dei dati**.
3. Nella scheda **Impostazioni entità**, selezionare **Configura parametri di esecuzione entità** per aprire la pagina **Parametri di esecuzione importazione entità**.
4. Impostare i seguenti campi per configurare l'importazione parallela per un'entità:

    - Nel campo **Entità**, selezionare l'entità.
    - Nel campo **Conteggio dei record di soglia importazione** immettere il conteggio dei record di soglia per l'importazione. Ciò determina il conteggio dei record che deve essere elaborato da un thread. Se un file ha 10.000 record, un conteggio di record di 2500 con un conteggio di attività 4 significa che ogni thread elaborerà 2500 record.
    - Nel campo **Conteggio attività importazione** inserire il conteggio delle attività di importazione. Questo valore non deve superare il numero massimo di thread in batch assegnati per l'elaborazione batch in **Amministrazione di sistema \>Configurazione del server**.

## <a name="job-history-clean-up"></a>Pulizia Storico processi 
La funzionalità di pulizia dello storico processi nella gestione dei dati deve essere utilizzata per programmare una pulizia periodica dello storico di esecuzione. Questa funzionalità sostituisce la funzionalità precedente della pulizia delle tabelle di gestione temporanea, ora deprecata. Le seguenti tabelle verranno pulite dal processo di pulizia.

-   Tutte le tabelle di gestione temporanea

-   DMFSTAGINGVALIDATIONLOG

-   DMFSTAGINGEXECUTIONERRORS

-   DMFSTAGINGLOGDETAIL

-   DMFSTAGINGLOG

-   DMFDEFINITIONGROUPEXECUTIONHISTORY

-   DMFEXECUTION

-   DMFDEFINITIONGROUPEXECUTION

La funzionalità **di pulizia storico esecuzione** deve essere abilitata nella gestione delle funzionalità ed è quindi accessibile da **Gestione dati \> Pulizia storico processi**.

### <a name="scheduling-parameters"></a>Parametri di programmazione

Quando si esegue la programmazione del processo di pulizia, i seguenti parametri devono essere definite per definire i criteri di pulizia.

-   **Numero di giorni di mantenimento storico** - Questa impostazione viene utilizzata per stabilire la quantità dello storico di esecuzione da conservare. Specificato in numero di giorni. Quando il processo di pulizia viene programmato come processo batch ricorrente, questa impostazione agirà come una finestra in continuo spostamento, sempre lasciando lo storico intatto per il numero di giorni specificato ed eliminando il resto. Il valore predefinito è 7 giorni.

-   **Numero di ore per eseguire il processo** - Seconda della quantità dello storico da pulire, il tempo di esecuzione totale per il processo di pulizia può variare da alcuni minuti a qualche ora. Questo parametro deve essere impostato sul numero di ore di esecuzione del processo. Dopo che il processo di pulizia è stato eseguito per il numero di ore specificato, il processo verrà terminato e riprenderà la pulizia alla successiva esecuzione in base alla pianificazione della ricorrenza.

    Un tempo di esecuzione massimo può essere specificato impostando un limite massimo sul numero di ore in cui il processo deve essere eseguito mediante questa impostazione. La logica di pulizia gestisce un ID di esecuzione processo alla volta in una sequenza cronologica, con il più vecchio come primo della pulizia dello storico di esecuzione correlato. Smetterà di prendere nuovi ID di esecuzione per la pulizia quando la durata rimanente di esecuzione rientra nell'ultimo 10% della durata specificata. In alcuni casi, verrà previsto che il processo di pulizia continua oltre il tempo massimo specificato. Ciò dipende in gran parte dal numero di record da eliminare per l'ID di esecuzione corrente che è stato avviata prima della soglia di 10% venga raggiunta. La pulizia iniziata deve essere completata per assicurarla l'integrità dei dati, pertanto la pulizia continuare nonostante il superamento del limite specificato. Al termine, i nuovi ID di esecuzione non vengono prelevate e il processo di pulizia termina. Lo storico di esecuzione rimanente che non è stato pulito per mancanza di tempo di esecuzione, verrà selezionato nella successiva programmazione del processo di pulizia. Il valore predefinito e minimo per questa impostazione è impostato su 2 ore.

-   **Batch ricorrente** - Il processo di pulizia può essere eseguito come esecuzione manuale occasionale, oppure può essere programmata per l'esecuzione ricorrente in batch. Il batch può essere programmato utilizzando le impostazioni **Esecuzione in background**, che è l'impostazione batch standard.

> [!NOTE]
> Se i record nelle tabelle di gestione temporanea non vengono ripuliti completamente, assicurarsi che il processo di pulizia sia pianificato per essere ripetuto. Come spiegato sopra, in qualsiasi esecuzione di pulizia il processo pulirà il maggior numero di ID di esecuzione possibile entro le ore massime previste. Per continuare la pulizia di tutti i record di gestione temporanea rimanenti, è necessario pianificare l'esecuzione periodica del processo.

## <a name="job-history-clean-up-and-archival-available-for-preview-in-platform-update-39-or-version-10015"></a>Pulizia e archiviazione storico processi (disponibile per l'anteprima nel Platform update 39 o nella versione 10.0.15)
La funzionalità di pulizia e archiviazione storico processi sostituisce le versioni precedenti della funzionalità di pulizia. Questa sezione spiegherà queste nuove funzionalità.

Una delle principali modifiche alla funzionalità di pulizia è l'uso del processo batch di sistema per la pulizia dello storico. L'utilizzo del processo batch di sistema consente alle Finance and Operations app di pianificare ed eseguire automaticamente il processo batch di pulizia non appena il sistema è pronto. Non è più necessario pianificare manualmente il processo batch. In questa modalità di esecuzione predefinita, il processo batch verrà eseguito ogni ora a partire dalla mezzanotte e conserverà lo storico delle esecuzioni per i 7 giorni più recenti. Lo storco eliminato viene archiviato per il recupero futuro.

> [!NOTE]
> Poiché questa funzionalità è in anteprima, il processo batch di sistema non eliminerà alcuno storico esecuzione fino a quando non verrà abilitato tramite l'anteprima DMFEnableExecutionHistoryCleanupSystemJob. Quando la funzione sarà generalmente disponibile in una versione futura, questo periodo di pubblicazione non sarà necessario e il processo batch del sistema inizierà a essere eliminato e archiviato dopo che il sistema è pronto, in base alla pianificazione definita come spiegato sopra. 

> [!NOTE]
> In una versione futura, le versioni precedenti della funzionalità di pulizia verranno rimosse dalle Finance and Operations app.

La seconda modifica nel processo di pulizia è l'archiviazione dello storico esecuzione eliminato. Il processo di pulizia archivierà i record eliminati nell'archiviazione BLOB che DIXF utilizza per le integrazioni regolari. Il file archiviato sarà nel formato del pacchetto DIXF e sarà disponibile per 7 giorni nel BLOB durante il quale potrà essere scaricato. La longevità predefinita di 7 giorni per il file archiviato può essere modificata fino a un massimo di 90 giorni nei parametri.

### <a name="changing-the-default-settings"></a>Modifica delle impostazioni predefinite
Questa funzionalità è attualmente in anteprima e deve essere esplicitamente attivata abilitando l'anteprima DMFEnableExecutionHistoryCleanupSystemJob. La funzionalità di pulizia della gestione temporanea deve essere attivata anche nella gestione delle funzionalità.

Per modificare l'impostazione predefinita per la longevità del file archiviato, accedere all'area di lavoro della gestione dei dati e selezionare **Pulizia storico processi**. Impostare **Giorni in cui conservare il pacchetto in BLOB** su un valore compreso tra 7 e 90 (inclusi). Ciò avrà effetto sugli archivi creati dopo questa modifica.

### <a name="downloading-the-archived-package"></a>Download del pacchetto archiviato
Questa funzionalità è attualmente in anteprima e deve essere esplicitamente attivata abilitando l'anteprima DMFEnableExecutionHistoryCleanupSystemJob. La funzionalità di pulizia della gestione temporanea deve essere attivata anche nella gestione delle funzionalità.

Per scaricare lo storico esecuzione archiviata, andare all'area di lavoro della gestione dei dati e selezionare **Pulizia storico processi**. Selezionare **Storico backup del pacchetto** per aprire il modulo dello storico. Questo modulo mostra l'elenco di tutti i pacchetti archiviati. Un archivio può essere selezionato e scaricato selezionando **Scarica il pacchetto**. Il pacchetto scaricato sarà nel formato del pacchetto DIXF e conterrà i seguenti file:

-   Il file della tabella di gestione temporanea dell'entità
-   DMFDEFINITIONGROUPEXECUTION
-   DMFDEFINITIONGROUPEXECUTIONHISTORY
-   DMFEXECUTION
-   DMFSTAGINGEXECUTIONERRORS
-   DMFSTAGINGLOG
-   DMFSTAGINGLOGDETAILS
-   DMFSTAGINGVALIDATIONLOG



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
