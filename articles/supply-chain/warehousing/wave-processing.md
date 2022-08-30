---
title: Creazione ed elaborazione dei cicli
description: In questo articolo viene descritto come creare, elaborare e rilasciare un'ondata per creare il lavoro di prelievo per un carico, una spedizione, un ordine di produzione o un ordine kanban.
author: Mirzaab
ms.date: 08/09/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSWaveTemplateTable, WHSParameters, whswavetablecreatenew, WHSWaveTable, WHSWaveAttributes, WHSKanbanWaveTable, WHSWaveTableListPage, WHSKanbanWaveTableListPage, WHSProdWaveTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-03-08
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 0466019990773ee93e063a255c15a7d64eecdf78
ms.sourcegitcommit: 203c8bc263f4ab238cc7534d4dd902fd996d2b0f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/23/2022
ms.locfileid: "9336007"
---
# <a name="wave-creation-and-processing"></a>Creazione ed elaborazione dei cicli

[!include [banner](../includes/banner.md)]

In questo articolo viene descritto come creare, elaborare e rilasciare un'ondata per creare il lavoro di prelievo per un carico, una spedizione, un ordine di produzione o un ordine kanban. È possibile creare cicli per i seguenti tipi di ordini:

- **Ordini cliente**: utilizza i cicli di spedizione per includere le righe da ordini cliente. Quando un ordine cliente viene rilasciato al magazzino, le righe ordine cliente possono essere incluse nel ciclo.
- **Ordini di produzione**: utilizza i cicli di produzione per includere le righe dalla distinta base (DBA) per il prodotto.
- **Ordini kanban**: i cicli kanban includono righe della distinta di prelievo da ordini kanban.

Per gli ordini cliente e gli ordini di kanban, l'inventario deve essere prenotato prima che l'ordine venga rilasciato al magazzino. In caso contrario, gli articoli o le righe di allocazione non possono essere elaborati in un ciclo. Tuttavia, gli ordini di produzione sono leggermente più flessibili. Per gli ordini di produzione, puoi scegliere una delle seguenti opzioni:

- Richiedi che tutti i materiali siano prenotati prima di poter rilasciare un ordine al magazzino.
- Consenti agli ordini di produzione di essere rilasciati al magazzino anche se non possono essere prenotati tutti i materiali. Se si seleziona questa opzione, è necessario ripetere manualmente il rilascio al processo di magazzino quando i materiali aggiuntivi diventano disponibili. Ad esempio, questo è utile se hai i materiali necessari per avviare una produzione e puoi attendere fino a quando i materiali aggiuntivi diventano disponibili.

Puoi specificare quale di queste opzioni dell'ordine di produzione utilizzare per impostazione predefinita utilizzando il campo **Requisito per prenotazione materiale** nella pagina **Parametri di controllo produzione**. Tuttavia, puoi modificare l'impostazione per ogni ordine di produzione specifico come necessario. Per ulteriori informazioni, vedi [Parametri di magazzino per elaborazione ciclo](wave-warehouse-parameters.md).

## <a name="create-and-process-a-wave"></a>Creare ed elaborare un ciclo

Il diagramma seguente mostra il flusso di come vengono creati, elaborati e rilasciati i cicli di spedizione. I numeri corrispondenti alle sezioni riportate di seguito in questa sezione.

![Procedura per la creazione di un ciclo.](media/wave-processing-diagram.png "Procedura per la creazione di un ciclo")

### <a name="prerequisites"></a>Prerequisiti

Prima di iniziare, deve essere disponibile un modello di ciclo per il tipo di ciclo che desideri creare (spedizione, produzione o kanban). Il modello di ciclo stabilisce molte impostazioni su come il ciclo verrà generato ed elaborato, inclusi i passaggi che devono essere eseguiti manualmente e quali vengono eseguiti automaticamente. Per ulteriori informazioni, vedi [Modelli di ciclo](wave-templates.md).

### <a name="create-a-wave"></a>Crea un'ondata

#### <a name="automatically-create-waves-based-on-warehouse-and-order-type"></a>Crea automaticamente cicli in base al magazzino e al tipo di ordine

Per creare cicli automaticamente, imposta [Modelli ciclo](wave-templates.md) che si applicano a ciascun tipo di ordine e magazzino pertinenti. Assicurati che ogni modello abbia l'opzione **Automatizza creazione ciclo** impostata su *Sì*.

#### <a name="manually-create-waves"></a>Creare manualmente cicli

Per creare un ciclo manualmente, attieniti alla procedura seguente:

1. Assicurati che i [modelli di ciclo](wave-templates.md) non siano impostati per creare automaticamente un ciclo per il magazzino e i tipi di ordine in cui desideri farlo manualmente.
1. A seconda del tipo di ciclo da creare, effettua una delle seguenti operazioni:

    - Vai a **Gestione magazzino** \> **Ondate in uscita** \> **Ondate spedizione** \> **Tutte le ondate**. Nel riquadro azioni seleziona **Ciclo**.
    - Seleziona **Gestione magazzino** \> **Ondate in uscita** \> **Ondate produzione** \> **Tutte le ondate di produzione**. Nel riquadro azioni seleziona **Ciclo produzione**.
    - Seleziona **Gestione magazzino** \> **Ondate in uscita** \> **Ondate Kanban** \> **Tutte le ondate kanban**. Nel riquadro azioni seleziona **Crea ciclo**.

1. Nel campo **Descrizione** immetti una breve descrizione del ciclo. Questa descrizione deve indicare che cosa si sta elaborando nel ciclo.

1. Nel campo **Nome modello ciclo** seleziona il modello di ciclo per il tipo di ciclo da creare. Il modello di ciclo contiene i metodi di ciclo che eseguiranno le azioni come la creazione del lavoro per il ciclo. Ad esempio, il modello di ciclo per i cicli di spedizione può contenere metodi per la creazione di carichi, l'allocazione di righe a cicli. il rifornimento e la creazione del lavoro di prelievo per il ciclo.

1. Facoltativo: se vuoi utilizzare gli attributi di ciclo come criteri di query aggiuntivi per il ciclo, seleziona gli attributi nei campi **Attributi ciclo**.

### <a name="specify-what-to-include-in-a-wave"></a>Specificare cosa includere in un ciclo

Dopo che un ciclo è stato creato, puoi iniziare ad aggiungervi dei contenuti.

> [!NOTE]
> Se necessario, puoi aggiungere righe a un ciclo anche dopo che è stato elaborato purché non sia stato rilasciato.

#### <a name="automatically-specify-what-to-include-in-a-wave"></a>Specificare automaticamente cosa includere in un ciclo

Per creare cicli automaticamente, imposta [Modelli ciclo](wave-templates.md) che si applicano a ciascun tipo di ordine e magazzino pertinenti. Assicurati che ogni modello abbia l'opzione **Automatizza creazione ciclo** impostata su *Sì*. In alternativa, il tuo modello potrebbe assegnare automaticamente righe a qualsiasi ciclo aperto idoneo se l'opzione **Assegna a cicli aperti** è impostata su *Sì*.

#### <a name="manually-specify-what-to-include-in-a-wave"></a>Specificare manualmente cosa includere in un ciclo

Quando un ciclo è statoo creato ma non ancora rilasciato, puoi specificare manualmente cosa includere. Per aggiungere manualmente righe a un ciclo:

1. A seconda del tipo di ciclo a cui aggiungere le righe, effettua una delle seguenti operazioni:

    - Vai a **Gestione magazzino** \> **Ondate in uscita** \> **Ondate spedizione** \> **Tutte le ondate**. Nel riquadro azioni seleziona **Ciclo**.
    - Seleziona **Gestione magazzino** \> **Ondate in uscita** \> **Ondate produzione** \> **Tutte le ondate di produzione**. Nel riquadro azioni seleziona **Ciclo produzione**.
    - Seleziona **Gestione magazzino** \> **Ondate in uscita** \> **Ondate Kanban** \> **Tutte le ondate kanban**. Nel riquadro azioni seleziona **Crea ciclo**.

1. Seleziona il ciclo. Nel riquadro azioni seleziona uno degli elementi riportati di seguito:

      - **Gestisci spedizioni**
      - **Gestisci produzioni**
      - **Gestisci distinte di prelievo processo kanban**

1. Nella parte superiore della finestra seleziona la riga da aggiungere al ciclo, quindi seleziona **Aggiungi a ciclo**. La riga viene spostata nella scheda dettaglio **Righe ciclo**.

    Ripeti questo passaggio per ogni riga da aggiungere. Per aggiungere tutte le righe, seleziona **Aggiungi tutto**.

    > [!TIP]
    > Per i cicli di spedizione, è possibile trovare rapidamente un ordine specifico selezionando un filtro personalizzato nel campo **Codice filtro ciclo**. I codici di filtro ciclo contengono criteri di query per le spedizioni, che sono creati nel modulo **Filtri ciclo**. Questo campo non è disponibile per i cicli di produzione o kanban.
    > Un segno di spunta verde nella colonna **In ciclo** indica che la spedizione è stata aggiunta al ciclo.

### <a name="process-the-wave-to-create-the-picking-work"></a>Elaborare il ciclo per creare il lavoro di prelievo

Dopo che un ciclo è stato creato e contiene tutte le righe richieste, sei pronto per elaborarlo per creare il lavoro di prelievo corrispondente.

#### <a name="automatically-process-a-wave"></a>Elaborare automaticamente un ciclo

Per elaborare automaticamente un ciclo, imposta i [Modelli di ciclo](wave-templates.md) corrispondenti con le opzioni di elaborazione automatica richieste.

#### <a name="manually-process-a-wave"></a>Elaborare manualmente un ciclo

Puoi elaborare un ciclo solo quando lo **stato ciclo** è *Creato*. Dopo aver elaborato un ciclo, lo **Stato ciclo** sarà cambiato in *Trattenuto*.

Per elaborare manualmente un ciclo con tutto il contenuto richiesto, segui questi passaggi:

1. A seconda del tipo di ciclo da elaborare, effettua quanto segue:

    - Seleziona **Gestione magazzino** \> **Ondate in uscita** \> **Ondate spedizione** \> **Tutte le ondate**. Nel riquadro azioni seleziona **Ciclo**.
    - Seleziona **Gestione magazzino** \> **Ondate in uscita** \> **Ondate produzione** \> **Tutte le ondate produzione**. Nel riquadro azioni seleziona **Ciclo produzione**.
    - Seleziona **Gestione magazzino** \> **Ondate in uscita** \> **Ondate Kanban** \> **Tutte le ondate kanban**. Nel riquadro azioni seleziona **Crea ciclo**.

1. Seleziona il ciclo da elaborare. Nel riquadro azioni selezionare **Elabora**.

### <a name="release-the-wave-to-the-warehouse-to-start-picking-and-packing"></a>Rilascia il ciclo al magazzino per avviare il prelievo e l'imballaggio

È necessario elaborare il ciclo prima di poterlo rilasciare. Quando si rilascia il ciclo, il lavoro di prelievo è disponibile nel magazzino. È possibile annullare un ciclo dopo che è stato rilasciato e aggiungere altre righe, ma non è possibile modificare le righe esistenti.

#### <a name="automatically-release-a-wave"></a>Rilasciare automaticamente un ciclo

Per elaborare automaticamente un ciclo, imposta i [Modelli di ciclo](wave-templates.md) corrispondenti con le opzioni di elaborazione automatica richieste.

#### <a name="manually-release-a-wave"></a>Rilasciare manualmente un ciclo

Per rilasciare un ciclo manualmente, attieniti alla procedura seguente:

1. A seconda del tipo di ciclo da rilasciare, effettua quanto segue:

      - Seleziona **Gestione magazzino** \> **Ondate in uscita** \> **Ondate spedizione** \> **Tutte le ondate**. Nel riquadro azioni seleziona **Ciclo**.
      - Seleziona **Gestione magazzino** \> **Ondate in uscita** \> **Ondate produzione** \> **Tutte le ondate produzione**. Nel riquadro azioni seleziona **Ciclo produzione**.
      - Seleziona **Gestione magazzino** \> **Ondate in uscita** \> **Ondate Kanban** \> **Tutte le ondate kanban**. Nel riquadro azioni seleziona **Crea ciclo**.

1. Seleziona il ciclo da rilasciare. Nel riquadro azioni seleziona **Rilascia ciclo**.

## <a name="containerize-a-wave"></a>Containerizzazione di un ciclo

La containerizzazione automatica consente di creare contenitori e il lavoro di prelievo per le spedizioni al momento dell'elaborazione del ciclo. Per i dettagli su come configurarlo, vedi [Containerizzazione](wave-containerization.md).

## <a name="work-with-the-scheduled-work-creation"></a>Lavorare con la creazione del lavoro programmato

Quando la funzionalità *Pianifica creazione lavoro* è abilitata, l'elaborazione dell'ondata creerà il lavoro pianificato, che verrà in seguito utilizzato dal nuovo processo di creazione del lavoro. Durante la creazione del lavoro, il lavoro verrà bloccato utilizzando la funzionalità *Blocco lavoro a livello di organizzazione*. Per ulteriori informazioni, vedi [Pianificare la creazione del lavoro nel corso del ciclo](configure-wave-schedule-work-creation.md).

Il diagramma di flusso seguente mostra come viene creato il lavoro pianificato durante l'elaborazione dell'ondata.

![Programma creazione lavoro.](media/schedule-work-creation-process.png)

### <a name="planned-work"></a>Lavoro pianificato

La pagina **Dettagli lavoro pianificato** (**Gestione magazzino \> Lavoro \> Dettagli del lavoro pianificato**) mostra le informazioni sul lavoro pianificato, che viene inizialmente creato durante l'elaborazione dell'ondata. Sono disponibili i seguenti valori di **Stato processo**:

- **In coda**: il lavoro pianificato attende di essere utilizzato per creare lavoro.
- **Completato**: il lavoro pianificato è stato utilizzato per creare lavoro.
- **Non riuscita**: l'elaborazione dell'ondata non è riuscita. Notare che il lavoro pianificato può essere in uno stato **Non riuscita** con o senza lavoro effettivo correlato. Quando il processo di creazione del lavoro effettivo non riesce, il lavoro effettivo rimane nello stato *Annullato*.

### <a name="batch-job-for-the-work-creation-process"></a>Processo batch per il processo di creazione del lavoro

Per visualizzare i processi batch per l'elaborazione delle ondate, selezionare **Processi batch** nel riquadro azioni della pagina **Tutte le ondate**.

Da qui, è possibile visualizzare tutti i dettagli dell'attività batch per ciascuno degli ID processo batch.

## <a name="cancel-a-wave"></a>Annullare un ciclo

Se necessario, è possibile annullare un' ciclo che è stato elaborato. Per annullare un ciclo e il lavoro di prelievo creato, effettua le operazioni seguenti:

1. A seconda del tipo di ciclo da annullare, effettua quanto segue:

      - Vai a **Gestione magazzino** \> **Ondate in uscita** \> **Ondate spedizione** \> **Tutte le ondate**.
      - Seleziona **Gestione magazzino** \> **Ondate in uscita** \> **Ondate produzione** \> **Tutte le ondate di produzione**.
      - Seleziona **Gestione magazzino** \> **Ondate in uscita** \> **Ondate Kanban** \> **Tutte le ondate kanban**.

1. Seleziona il ciclo da annullare. Nel riquadro azioni, nella scheda **Lavoro**, seleziona **Annulla**.

## <a name="review-wave-batch-job-details"></a>Rivedere i dettagli del processo batch ciclo

Utilizza la pagina **Dettagli processo batch ciclo** per ispezionare i processi batch e le attività correlate associate a qualsiasi ciclo. Ciò è particolarmente utile per la risoluzione dei problemi di un ciclo non riuscito. Senza questa funzione, solo gli amministratori avranno in genere accesso ai dettagli del processo batch. La pagina **Dettagli processo batch ciclo** può essere resa disponibile agli utenti non amministratori e fornisce una visualizzazione di sola lettura dei processi batch e delle attività correlate.

### <a name="turn-the-wave-batch-job-details-page-on-or-off"></a>Attivare o disattivare la pagina Dettagli processo batch ciclo

Per utilizzare questa funzionalità, è necessario attivarla per il sistema. A partire dalla versione 10.0.25 di Supply Chain Management, la funzionalità è attivata per impostazione predefinita. A partire dalla versione 10.0.29 di Supply Chain Management, la funzionalità è obbligatoria e non può essere disattivata. Se si sta eseguendo una versione precedente alla versione 10.0.29, gli amministratori possono attivare o disattivare questa funzionalità cercando la funzionalità *Dettagli processo batch ciclo* nell'area di lavoro [Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

### <a name="use-the-wave-batch-job-details-page"></a>Usare la pagina dettagli processo batch ciclo

La pagina **Dettagli processo batch ciclo** combina processi batch e attività di processi batch consentendo di esaminare tutti i passaggi del ciclo senza la necessità di spostarsi avanti e indietro tra un singolo processo batch e l'elenco delle attività batch. La pagina fornisce anche l'accesso al registro batch e, se hai le autorizzazioni necessarie, fornisce un collegamento alla pagina **Processi batch**.

Per aprire questa pagina, seleziona un ciclo in una qualsiasi delle diverse pagine ciclo, quindi seleziona **Dettagli processo batch ciclo** dal riquadro azioni.

## <a name="review-load-validation-and-error-messages"></a>Esaminare i messaggi di errore e convalida del caricamento

Durante l'elaborazione del ciclo, il sistema convalida e visualizza lo stato di ciascuna riga di carico nel ciclo. Se non si verificano avvisi, continua con il passaggio del ciclo successivo. Se si verificano avvisi, viene invece visualizzato il seguente errore dopo aver terminato la convalida dell'intero ciclo:

> Trovate righe di carico non valide nel ciclo. Rimuovere le righe di carico non valide.

È quindi possibile rivedere lo stato finale di ciascuna riga di carico nel ciclo e correggere tutti gli avvisi prima di riprovare. Ciò consente di risolvere tutti gli avvisi contemporaneamente prima di rielaborare il ciclo. (Nelle versioni precedenti, il sistema interrompeva l'elaborazione del ciclo dopo il primo avviso, quindi era possibile correggere gli avvisi solo uno alla volta.)

Il modo in cui il sistema visualizza i messaggi di stato dell'elaborazione del ciclo dipende da come è stato impostata l'opzione **Crea registro cronologia elaborazione ciclo** nella pagina **Parametri di gestione magazzino**.

- Quando **Crea registro cronologia elaborazione ciclo** è impostato su *No*, i messaggi di stato della riga di carico vengono visualizzati nel **Registro informazioni**.
- Quando **Crea registro cronologia elaborazione ciclo** è impostato su *Sì*, i messaggi di stato della riga di carico vengono visualizzati nella pagina **Registro cronologia elaborazione ciclo**. Per visualizzare il registro, vai a **Gestione magazzino \> Cicli in uscita \> Registro cronologia elaborazione ciclo**.

## <a name="additional-resources"></a>Risorse aggiuntive

- [Configurare l'elaborazione di cicli di esempio](tasks/configure-wave-processing.md)
- [Modelli ondata](wave-templates.md)
- [Containerizzazione](wave-containerization.md)