---
title: Allocazione ciclo
description: Questo argomento descrive come impostare la fase di allocazione del ciclo, incluso come abilitare l'elaborazione parallela.
author: Mirzaab
ms.date: 03/08/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-03-08
ms.dyn365.ops.version: Release 10.0.18
ms.openlocfilehash: feee33a7d4ea3f0d9c4d671210293a28aac14f61
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5823169"
---
# <a name="wave-allocation"></a>Allocazione ciclo

[!include [banner](../includes/banner.md)]

L'elaborazione del ciclo può richiedere molto tempo e la maggior parte del tempo viene impiegata nella fase di allocazione e nella fase di creazione del lavoro.

È ora possibile eseguire ciascuna di queste fasi in parallelo, il che può migliorare le prestazioni dell'elaborazione del ciclo e consentire una maggiore produttività dei cicli nello stesso magazzino. Questo argomento spiega come impostare il metodo di allocazione del ciclo per l'esecuzione in parallelo. Per ulteriori informazioni su come impostare la creazione del lavoro per l'esecuzione in parallelo, vedi [Programmare la creazione del lavoro durante il ciclo](configure-wave-schedule-work-creation.md).

In precedenza era possibile allocare solo un ciclo alla volta in un magazzino. Questo vincolo è stato rimosso e sostituito da un nuovo vincolo che blocca solo l'elemento e le dimensioni che si trovano al di sopra dell'ubicazione nella gerarchia di prenotazione. Le dimensioni sopra l'ubicazione includono sempre le dimensioni del prodotto. Ad esempio, se un elemento è configurato utilizzando *Colore*, quindi le varianti per *Rosso*, *Blu*, e *Giallo* potrebbero essere elaborate in parallelo.

Ciò significa che se lo stesso oggetto con le stesse dimensioni sopra l'ubicazione viene allocato da un ciclo, gli altri cicli dovranno attendere per acquisire un blocco sullo stesso oggetto e dimensioni. Se il blocco non può essere acquisito in modo tempestivo, si verificherà un errore e l'elaborazione del ciclo non riesce.

Per utilizzare l'elaborazione parallela, il ciclo deve essere eseguito in batch.

## <a name="performance-improvements"></a>Miglioramenti delle prestazioni

I vantaggi in termini di prestazioni dell'elaborazione parallela rientrano in due categorie:

- **Throughput migliorato** - La velocità effettiva dei cicli in genere migliorerà anche se l'elaborazione parallela non è configurata, soprattutto per gli scenari in cui non vi è sovrapposizione di elementi all'interno dei cicli.
- **Miglioramento dell'assegnazione per un singolo ciclo** - I test sui dati dei clienti hanno mostrato un miglioramento delle prestazioni di quasi il 50% dopo il passaggio all'allocazione parallela. L'elaborazione parallela viene eseguita per elementi e dimensioni sopra l'ubicazione, quindi i miglioramenti dipendono dal numero di elementi diversi contenuti in un ciclo, dall'infrastruttura disponibile e dalla durata dell'allocazione rispetto alla durata della creazione del lavoro.

## <a name="configure-parallel-allocation"></a>Configurare l'allocazione parallela

### <a name="warehouse-management-parameters"></a>Parametri di gestione magazzino

Per utilizzare l'elaborazione dell'allocazione parallela, vai a **Gestione magazzino> Impostazioni > Parametri di gestione magazzino**, apri la scheda **Elaborazione ciclo** ed effettua le seguenti impostazioni:

- **Gruppo batch di elaborazione ciclo** - Seleziona il gruppo batch che deve essere utilizzato dall'elaborazione iniziale dei cicli. La successiva elaborazione dell'allocazione può essere eseguita utilizzando diversi gruppi di batch.
- **Elabora cicli in batch** - Imposta su *Sì* per utilizzare l'elaborazione parallela.
- **Attesa blocco (ms)** - Immetti il tempo, espresso in millisecondi, in cui un passaggio di allocazione aspetterà una risorsa di sistema bloccata da un altro passaggio di allocazione. Quando il tempo viene superato, l'ondata non viene elaborata e viene visualizzato un messaggio di errore. Consigliamo di consentire almeno alcuni secondi per permettere il completamento dell'allocazione di un'unità logica.

Per informazioni su queste e altre opzioni di elaborazione ciclo nella pagina **Parametri di gestione magazzino**, vedi [Parametri di magazzino per l'elaborazione ciclo](wave-warehouse-parameters.md).

## <a name="wave-process-methods"></a>Metodi di elaborazione ondata

Per impostare l'elaborazione parallela:

1. Vai a **Gestione magazzino > Impostazione > Cicli > Metodi di elaborazione ciclo**.
1. Seleziona il metodo `allocateWave` nella griglia.
1. Nel riquadro azioni, seleziona **Configurazione attività**.
1. Viene visualizzata la pagina **Configurazione attività metodo di registrazione ciclo**. Questa griglia elenca ogni magazzino in cui hai configurato il metodo `allocateWave`. L'elaborazione parallela verrà utilizzata solo per i magazzini elencati. Utilizza i pulsanti del riquadro azioni per aggiungere o rimuovere magazzini dalla griglia in base alle esigenze. 
1. Per ogni magazzino, effettua le seguenti impostazioni:
    - **Numero massimo di attività batch** - Specifica il numero di attività batch da utilizzare per l'allocazione per il magazzino selezionato. Il numero ottimale di attività batch dipende dall'infrastruttura disponibile e da quali altri lavori batch vengono elaborati sul server. I test effettuati su un ambiente a quattro core dedicato all'elaborazione dei cicli hanno mostrato che l'utilizzo di otto attività ha prodotto buoni risultati.
    - **Gruppo batch di elaborazione ciclo** - È possibile utilizzare gruppi batch specifici per magazzini diversi per consentire la scalabilità orizzontale dell'elaborazione dell'allocazione per magazzino.

## <a name="enable-or-disable-parallelization-across-all-legal-entities"></a>Abilitare o disabilitare la parallelizzazione tra tutte le persone giuridiche

Ti consigliamo di impostare il metodo `allocateWave` da eseguire in parallelo tra tutte le persone giuridiche perché questo aiuta a migliorare le prestazioni dell'elaborazione ciclo. A partire dalla versione 10.0.17 di Supply Chain Management, la funzione *Parallelizzazione dei cicli per metodo allocazione del ciclo* è abilitata per impostazione predefinita per tutte le installazioni nuove e aggiornate e non può essere disattivata. Dopo aver abilitato questa funzione, si verifica quanto segue:

- Il metodo `allocateWave` viene aggiornato per includere un'impostazione di configurazione dell'attività che consente di utilizzare la pagina **Metodi di elaborazione ciclo** per definire il numero di attività che verranno eseguite simultaneamente, equivalente al numero di processi paralleli. Di conseguenza, il tempo utilizzato nella fase di allocazione del ciclo (che in genere è compreso tra il 30% e il 60% del tempo di elaborazione totale) viene ridotto di un fattore approssimativamente equivalente al numero di attività. È anche possibile selezionare quale batch verrà assegnato per elaborare queste attività. È importante notare che tutte le persone giuridiche saranno configurate per elaborare i cicli in batch. Per i magazzini già configurati per elaborare i cicli in batch e per i magazzini già configurati per l'utilizzo del metodo `allocateWave` in parallelo, verrà mantenuta la configurazione esistente.
- Per impostazione predefinita, tutte le nuove persone giuridiche sono configurate per elaborare i cicli in batch. Tutti i nuovi magazzini con l'opzione **Processi di gestione magazzino** abilitata avranno il metodo `allocateWave` configurato per essere eseguito in parallelo per impostazione predefinita.
- Nella pagina **Parametri di gestione magazzino**, **Elabora salvataggi in batch** è impostato su *Sì* e **Attendi blocco (ms)** è impostato su un valore predefinito di 15 secondi. Ciò significa che tutti i cicli verranno eseguiti in batch. Quando un ciclo è in esecuzione, acquisisce un blocco sull'elemento e sulle dimensioni sopra l'ubicazione durante la fase di allocazione. Quando un'altra attività di elaborazione ciclo tenta di acquisire lo stesso blocco per lo stesso record, viene bloccata fino al termine del processo corrente. L'impostazione **Attendi blocco (ms)** stabilisce il tempo massimo che il sistema attenderà prima che il blocco venga rilasciato.

L'elaborazione di allocazione parallela richiede che l'elaborazione del ciclo venga eseguita in batch. Pertanto, ridurrai le prestazioni di elaborazione del ciclo se disattivi l'impostazione **Elabora salvataggi in batch**, soprattutto se l'elaborazione del ciclo utilizza un processo parallelo come definito dalla configurazione dell'attività per i metodi di ciclo pertinenti.

Se necessario, è possibile annullare ciascuna delle impostazioni configurate per impostazione predefinita quando la funzionalità *Parallelizzazione dei cicli per metodo allocazione del ciclo* viene abilitata automaticamente per la tua istanza. A questo proposito:

- Vai a **Gestione magazzino \> Impostazioni \> Parametri di gestione magazzino**. Nella scheda **Elaborazione ciclo** applica i tuoi valori preferiti per **Elabora cicli in batch** e **Attesa blocco (ms)**.
- Andare a **Gestione magazzino \> Impostazione \> Ondate \> Metodi di elaborazione ondata**. Seleziona il metodo `allocateWave`. Nel riquadro azioni seleziona **Configurazione attività** per aprire una pagina che elenca ogni magazzino in cui il metodo è impostato per essere eseguito in parallelo. Modifica o elimina il numero di attività batch e il gruppo di cicli assegnato per ogni magazzino elencato in base alle esigenze.

## <a name="troubleshooting"></a>Risoluzione dei problemi

### <a name="troubleshoot-using-the-infolog"></a>Risolvere i problemi usando il Registro informazioni

Poiché viene utilizzato il framework batch, gli errori che si verificano durante l'elaborazione ciclo verranno acquisiti come parte del Registro informazioni dei processi batch. Per leggere i processi batch relativi a un ciclo:

1. Selezionare **Gestione magazzino \> Ondate in uscita \> Ondate spedizione \> Tutte le ondate**.
1. Seleziona il ciclo che vuoi ispezionare.
1. Nel riquadro azioni, apri la scheda **Ciclo** e, nel gruppo **Ciclo**, seleziona **Processi batch**.

L'elaborazione ciclo si corregge automaticamente, quindi qualsiasi errore rilevato durante l'elaborazione deve essere segnalato utilizzando il Registro informazioni.

Un errore tipico relativo all'elaborazione parallela potrebbe essere che due cicli tentano di allocare lo stesso elemento contemporaneamente e uno non viene completato in modo che l'altro ciclo non sia in grado di acquisire un blocco entro il tempo specificato. Se si verifica questa situazione, il registro dei processi batch conterrà le informazioni che indicano che non è stato possibile acquisire il blocco per l'articolo, nel qual caso il ciclo non riuscito deve essere elaborato di nuovo.

Poiché l'elaborazione avviene in parallelo, i dati devono essere conservati in tabelle diverse per tenere traccia dello stato dell'elaborazione. Ciò significa che i registri per i lavori batch potrebbero contenere errori, come errori di chiavi duplicate.

Anche gli errori delle attività batch fanno parte del registro dei processi batch. Le informazioni più importanti sono in genere in fondo.

In rari casi, ad esempio se la connessione SQL è terminata, è possibile che l'elaborazione ciclo termini in uno stato incoerente in cui il processo batch sembra essere in esecuzione ma l'elaborazione viene interrotta. Il ciclo non può gestire errori come questo, quindi un tentativo di ripulire i cicli non riusciti viene eseguito quando viene eseguito il ciclo successivo. In alternativa, se il ciclo corrente è in uno stato incoerente, esegui le seguenti operazioni:

1. Selezionare **Gestione magazzino \> Ondate in uscita \> Ondate spedizione \> Tutte le ondate**.
1. Seleziona il ciclo che devi pulire.
1. Nel riquadro azioni, apri la scheda **Ciclo** e, nel gruppo **Ciclo**, seleziona **Pulizia dati ciclo**.

### <a name="troubleshoot-using-the-wave-progress-log"></a>Risolvere i problemi utilizzando il registro stato ciclo

Se l'opzione **Crea registro stato ciclo** è abilitata nella pagina **Parametri di gestione magazzino** viene creato un record di registro ogni volta che l'allocazione di un articolo e le sue dimensioni iniziano e finiscono. Devi abilitare questo registro solo quando necessario, ad esempio durante il test iniziale o per la risoluzione dei problemi. Quando questa opzione è abilitata, è possibile visualizzare il registro effettuando le seguenti operazioni:

1. Selezionare **Gestione magazzino \> Ondate in uscita \> Ondate spedizione \> Tutte le ondate**.
1. Seleziona il ciclo che vuoi ispezionare.
1. Nel riquadro azioni, apri la scheda **Ciclo** e nel gruppo **Ciclo**, seleziona **Stato**.
