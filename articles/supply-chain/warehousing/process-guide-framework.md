---
title: Elaborare il framework della guida
description: Questo argomento fornisce informazioni sul framework della guida per gli sviluppatori che estendono i nostri processi per dispositivi mobili di magazzino in X++.
author: Mirzaab
ms.date: 11/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: mirzaab
ms.search.validFrom: 2018-4-30
ms.dyn365.ops.version: 8
ms.openlocfilehash: 6882c979ad9b37eb4f95a04259b6ac0f0a0edcdc
ms.sourcegitcommit: fd6270dc7f49f93a8155d2b827153b13edb7be8a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2021
ms.locfileid: "7902048"
---
# <a name="process-guide-framework"></a>Elaborare il framework della guida

[!include [banner](../includes/banner.md)]

Questo argomento fornisce informazioni sul framework della guida per gli sviluppatori che estendono i processi per dispositivi mobili di magazzino in X++. I processi per dispositivi mobili di magazzino sono estensibili in quanto i processi vengono suddivisi in piccoli passaggi. La creazione della logica di business e dell'interfaccia utente di ogni passaggio è stata estratta in singole classi, il che consente l'estensibilità.

## <a name="overview-of-the-existing-design"></a>Panoramica della progettazione esistente

I flussi di esecuzione per i dispositivi mobili del magazzino sono esposti tramite un singolo endpoint del servizio personalizzato. La richiesta arriva dall'app per i dispositivi mobili sotto forma di stringa XML, che contiene i metadati dell'interfaccia utente presentata nell'app per i dispositivi mobili, nonché i valori inseriti dall'utente.

Quando la richiesta viene ricevuta, il primo passaggio consiste nel deserializzare questa stringa XML. La classe **WHSMobileAppServiceXMLTranslator** converte l'XML in un contenitore, che contiene sia le informazioni di controllo, sia le informazioni sulla sessione.

Successivamente, le informazioni nel contenitore vengono utilizzate per dedurre su quale processo di magazzino l'utente sta usando o sta per usare (rappresentato dall'enumerazione **WHSWorkExecuteMode**), e di conseguenza creare l'istanza della classe derivata **WHSWorkExecuteDisplay**. Il metodo **displayform()** viene invocato ed esegue le seguenti operazioni:

-   Elabora i dati dell'utente (delegati alla classe **WHSRFControlData**, ma alcuni processi implementano una logica specifica sovrascrivendo il metodo **processControl()**).

-   Esegue la logica di business.

-   Incrementa il passaggio.

-   Crea il contenitore che rappresenta la nuova interfaccia utente (tipicamente in un metodo **build…()**).

Il contenitore viene quindi restituito al traduttore, che quindi serializza l'XML e lo invia come risposta al dispositivo mobile.

Nel diagramma riportato di seguito viene mostrata in seguenza una panoramica del flusso di esecuzione. Il diagramma è più una panoramica schematica e non è una rappresentazione 1:1 del codice effettivo.

![Panoramica schematica del processo.](media/schematic-overview.png) 

### <a name="reason-for-the-redesign"></a>Motivo della riprogettazione

La progettazione precedente offre un framework molto semplice per la creazione di processi utilizzati nei flussi per dispositivi mobili. Tuttavia, come è evidente sopra, i metodi **displayform()** assumono più responsabilità. Vengono delegati ad altri metodi e classi, ma in assenza di responsabilità concrete della classe, vengono eseguiti in modo incoerente tra le classi. Inoltre, poiché il numero di scenari supportati cresce in modo organico, alcune di queste classi possono diventare piuttosto complesse. Per rendere le cose più interessanti, alcune di queste classi o di questi metodi vengono sovrascritti e riutilizzati in più modalità. Il risultato sono metodi estremamente lunghi con elevata complessità ciclomatica. Questi metodi hanno causato problemi di manutenzione in passato. La correzione di bug in questi metodi è stata rischiosa e soggetta a regressione.
Ad esempio, al metodo **processWorkLine()** nella classe **WhsWorkExecuteDisplay** viene fatto riferimento in più processi (in pratica, ovunque venga eseguita l'esecuzione del lavoro).

Per renderli estensibili, una delle opzioni sarebbe quella di dividere i metodi **displayForm** in metodi più piccoli e introdurre punti di estensibilità. Tuttavia, a causa della matrice dello scenario, sarebbe difficile per i partner scrivere estensioni e convalidare rispetto alle regressioni. Non solo, a causa della mancanza di una distribuzione strutturata delle responsabilità come indicato sopra, il codice continuerebbe a crescere in modi imprevedibili nel tempo, ponendo sfide nella creazione di estensioni di qualità.

Di conseguenza, la riprogettazione è l'opzione sostenibile, con l'obiettivo di avere classi chiaramente definite con responsabilità indipendenti. Una classe deve avere una responsabilità, una sola ragione per cambiare e una sola ragione per essere estesa.

## <a name="design-overview"></a>Panoramica della progettazione

Nel framework riprogettato, la strategia principale ruota attorno a due principi: dividere il flusso di esecuzione in singoli componenti con responsabilità ben definite e avere punti di estensione ben definiti in ciascuno dei componenti.

Il nome del nuovo framework è "ProcessGuide". Questo perché lo scopo di queste classi è guidare un utente attraverso un processo aziendale (al contrario del rich client che è un'esperienza basata su moduli in cui l'utente ha maggiore flessibilità nel modo in cui interagisce con i dati o in quale ordine esegue le attività).

> [!NOTE]
> Un dettaglio degno di nota è l'omissione deliberata del prefisso "WHS". Sebbene i processi per dispositivi mobili siano stati inizialmente introdotti per il magazzino, in seguito hanno trasceso i confini per supportare vari processi di produzione e gestione dell'inventario. Di conseguenza, il riferimento al magazzino è stato escluso nel nome del framework.

Per identificare i componenti, il primo passaggio è guardare il processo di avvio della produzione (classe **WhsWorkExecuteDisplayProdStart**). Ecco uno schema del processo.

![Immagine dello schema del processo.](media/production-start-process-schematic.png)

Guardando il flusso di controllo, i seguenti sono i componenti necessari:

-   Un controller per ripercorrere l'intero processo aziendale.
-   Un passaggio responsabile dell'esecuzione di un passaggio del processo.
-   Un elaboratore di dati per l'elaborazione dei dati in un passaggio.
-   Un generatore di pagine responsabile della creazione dell'interfaccia utente per un passaggio.
-   Un agente di spostamento responsabile della transizione dei passaggi.
-   Una classe responsabile dell'esecuzione del processo aziendale.

Nel diagramma di flusso del processo sopra, se inizi dal passaggio 1 e avvii l'elaborazione dei dati dal passaggio precedente, quindi finisci la creazione di un'interfaccia utente, i dati continueranno a essere elaborati nel passaggio successivo. Questo comporta una stretta associazione tra passaggi consecutivi e di conseguenza il nostro nuovo schema di alto livello è simile al seguente:

![Immagine dello schema di alto livello del processo.](media/high-level-schematic.png)

Di seguito sono riportati i componenti chiave del processo riprogettato:

-   **ProcessGuideController** - Questa classe orchestra l'esecuzione complessiva del processo aziendale. Definisce le factory che creano l'istanza del passaggio e dell'agente di spostamento, che successivamente costituiscono l'esecuzione del processo, nonché la logica di pulizia per l'annullamento o l'uscita dal processo.

-   **ProcessGuideStep** - Questa classe rappresenta un singolo passaggio nel processo aziendale. Questa classe contiene una definizione delle factory che creano un'istanza di un generatore di pagine, azioni e processori di dati ed è responsabile della loro invocazione nella sequenza corretta.

-   **ProcessGuideNavigationAgent** - Questa classe è responsabile dello spostamento tra i passaggi. Quando un passaggio è completato, l'agente di spostamento è responsabile della definizione del passaggio successivo e passa tutti i parametri che il passaggio precedente può aver bisogno di comunicare a quello successivo.

-   **ProcessGuidePageBuilder** - Questa classe è responsabile della creazione dell'istanza dell'interfaccia utente.

-   **ProcessGuideAction** - Questa classe rappresenta un'azione, mostrata all'utente come un pulsante.

-   **ProcessGuideDataProcessor** - Questa classe è responsabile dell'elaborazione dei dati inseriti dall'utente in un campo.

## <a name="execution-flow"></a>Flusso di esecuzione

Il punto di partenza del flusso di esecuzione rimane invariato. Quindi, la richiesta arriva ancora attraverso gli stessi endpoint, seguita dalla deserializzazione dell'XML nel contenitore. Questo contenitore viene quindi passato a **getNextFormState()**.

Ci sono tre classi importanti da tenere presenti:

-  **ProcessGuideSessionState** – Contiene le informazioni sullo stato della sessione: modalità, passaggio, controller e passaggio in esecuzione e così via.

-  **ProcessGuidePage** – Contiene una rappresentazione fortemente tipizzata dei metadati dell'interfaccia utente.

-  **ProcessGuideRequest** – Contiene i due precedenti come membri ed è una rappresentazione fortemente tipizzata della richiesta ricevuta dal dispositivo mobile.

Queste classi vengono create utilizzando le informazioni del contenitore (sia i dati di controllo dello stato che quelli immessi dall'utente). Ciò fornisce un modo indipendente dai tipi per accedere e manipolare i valori. Rispetto all'accesso ripetuto del contenitore durante il processo, questo offre vantaggi sia in termini di leggibilità che di prestazioni.

Le informazioni sullo stato della sessione vengono utilizzate per creare l'istanza della classe corretta **ProcessGuideController**. Una volta creata l'istanza, il metodo **createResponse()** nella classe **ProcessGuideController** viene invocato. Questo metodo è il punto di ingresso alla logica di guida del processo e, dopo l'esecuzione, torna con la risposta (rappresentata nella classe **ProcessGuideResponse**). La risposta viene quindi riconvertita nel contenitore e restituita alla logica legacy, che quindi la serializza nell'XML e la invia al dispositivo mobile.

Successivamente, il controller deve trovare il passaggio successivo da eseguire. Se questo è l'inizio di un nuovo processo, il controller chiamerà **initialStep()** per ottenere il primo passaggio nel processo. Dopo di che, chiama il metodo **execute()** in **ProcessGuideStep**. Questo metodo crea l'istanza di una classe **ProcessGuidePageBuilder** e chiama **buildPage()**, che restituisce un oggetto **ProcessGuidePage**, che è una rappresentazione virtuale dell'interfaccia utente da presentare all'utente. Il passaggio invia quindi il risultato al controller, che quindi salva lo stato della sessione corrente e restituisce il risultato a **getNextFormState()** sotto forma di classe **ProcessGuideResponse**. Successivamente, la risposta viene riconvertita nel contenitore e serializzata in XML e inviata al dispositivo mobile.

Il seguente diagramma di sequenza spiega questo flusso di controllo. Nota che questo è il flusso di controllo più comune, semplificato per spiegare la progettazione.

![Flusso di controllo semplificato.](media/control-flow.png)

Quando l'utente esegue un'azione sul dispositivo mobile facendo clic su un pulsante (o scansionando un valore, che in genere attiva l'azione predefinita), la richiesta arriva al metodo **createResponse()** nella classe **ProcessGuideController** attraverso lo stesso percorso. Questa volta, tuttavia, il controller conosce dalle informazioni sullo stato della sessione in quale passaggio si trova l'utente. Di conseguenza, crea l'istanza della classe appropriata **ProcessGuideStep** e invoca il metodo execute. La classe **ProcessGuideStep**, a sua volta, legge il nome dell'azione invocata dall'utente e quindi crea l'instanza della classe appropriata **ProcessGuideAction** e chiama **execute()**.

La classe **ProcessGuideAction** è responsabile dell'esecuzione dell'azione specifica, tuttavia ci sono due notevoli eccezioni.

La prima è la classe **ProcessGuideOKAction**. Questa azione implica che l'utente voglia confermare e andare avanti nel processo. In conformità a ciò, questo metodo esegue effettivamente un callback alla classe ProcessGuideStep, il che significa che il passaggio richiama **processData()** in **ProcessGuideDataProcessor**. Questo elabora i dati che l'utente ha inserito, quindi aggiorna lo stato del passaggio e invia il risultato al controller. A seconda del risultato del processore, il passaggio richiama il generatore di pagine per creare l'interfaccia utente appropriata o imposta lo stato del passaggio come completato. Ciò è riportato nella metà superiore del diagramma di sequenza sottostante.

L'altra eccezione è l'azione di annullamento, implementata nelle classi **ProcessGuideCancelResetProcessAction** e **ProcessGuideCancelExitProcessAction**. Queste azioni rappresentano l'intento di annullare il processo e tornare all'inizio del processo o uscire del tutto dal processo. Simile all'azione **OK**, queste azioni eseguono anche un callback al passaggio, che segnala l'intento al **ProcessGuideController**. Il controller esegue quindi la necessaria pulizia delle variabili di stato e sposta il controllo al passaggio iniziale del processo o termina del tutto il processo.

Al termine del passaggio, se lo stato del passaggio è impostato su **Completato**, quindi il controller crea l'istanza di **ProcessGuideNavigationAgent**, che restituisce il nome del passaggio successivo. Il controller quindi crea un'istanza di questo passaggio e invoca il metodo **execute()** e il ciclo continua. Più comunemente, il nuovo passaggio richiama il corrispondente **ProcessGuidePageBuilder** per creare l'interfaccia utente per la schermata successiva da presentare all'utente, che viene poi rispedita. Il flusso è illustrato nella metà inferiore del diagramma di sequenza sottostante.

![Diagramma di sequenza.](media/sequence-diagram.png)

## <a name="building-a-new-process-using-the-processguide-framework"></a>Costruire un nuovo processo utilizzando il framework ProcessGuide

Il modo migliore per spiegare il flusso di controllo è utilizzare un esempio presente nell'applicazione: il processo di avvio della produzione.

## <a name="overview-of-the-production-start-process"></a>Panoramica del processo di avvio della produzione

Iniziamo con la comprensione del flusso del processo. Nel primo passaggio all'utente viene richiesto l'ID dell'ordine di produzione.

![Richiesta dell'ID di produzione.](media/production-id-prompt.png)

Quando l'utente immette l'ID dell'ordine di produzione, il numero dell'ordine viene convalidato. Alcune delle convalide eseguite si basano sul fatto che l'ordine si trovi nello stesso magazzino in cui l'utente ha effettuato l'accesso e sullo stato dell'ordine. Se la convalida non riesce, all'utente viene mostrato un messaggio di errore. Se la convalida ha esito positivo, all'utente vengono visualizzati i dettagli dell'ordine di produzione e dell'articolo.

L'utente può annullare per tornare all'inizio del processo o fare clic su **OK** per confermare. In quest'ultimo caso, l'ordine di produzione è impostato sullo stato **Avviato**, i giornali di registrazione corrispondenti vengono registrati, il controllo torna al primo passaggio e all'utente viene mostrato il messaggio "Lavoro completato".


## <a name="creating-the-controller"></a>Creazione del controller

Il primo passaggio della creazione del processo aziendale è la creazione della classe controller, che si estende dalla classe astratta **ProcessGuideController** che implementa i comportamenti predefiniti di un controller. Il nuovo nome della classe è **ProdProcessGuideProductionStartController** e decorato con il valore **WHSWorkExecuteMode** di **StartProdOrder**. Viene utilizzata a stessa istanza basata su **SysExtension** che è stata utilizzata nelle classi **WHSWorkExecuteDisplay**, che aiuta a creare un'istanza del controller quando l'utente esegue una voce di menu per questa modalità.

```xpp
[WHSWorkExecuteMode(WHSWorkExecuteMode::StartProdOrder)]
public class ProdProcessGuideProductionStartController extends ProcessGuideController
```

> [!NOTE]
> Il modello di denominazione della classe è **\<FunctionalArea\>ProcessGuide\<Businessprocessname\>Controller**. Questo è il modello utilizzato per le classi di controller e da estendere ad altre classi.


## <a name="building-the-first-step"></a>Creazione del primo passaggio

Successivamente, per definire il primo passaggio si crea la classe **ProdProcessGuidePromptProductionIdStep** che si estende da **ProcessGuideStep**.

L'attività di creazione dell'istanza della classe è delegata a una factory di passaggio che viene invocata dalla classe di base **ProcessGuideController**. L'implementazione predefinita della factory crea un'istanza del passaggio in base al nome. Pertanto, per creare l'istanza di **ProdProcessGuidePromptProductionIdStep** come primo passaggio nel controller, devi fare due cose:

-   Decorare la classe **ProdProcessGuidePromptProductionIdStep** con un attributo **ProcessGuideStepName**.

    ```xpp
    [ProcessGuideStepName(classStr(ProdProcessGuidePromptProductionIdStep))] public class ProdProcessGuidePromptProductionIdStep extends ProcessGuideStep
    ```

-   Nella classe del controller, implementare il metodo astratto **initialStepName()** per restituire il nome del passaggio.

    ```xpp
    protected final ProcessGuideStepName initialStepName()
    {
        return classStr(ProdProcessGuidePromptProductionIdStep);
    }
    ````   
    
> [!NOTE]
> Il valore dell'attributo **ProcessGuideStepName** non necessita che l'attributo corrisponda esattamente al nome della classe come mostrato sopra. Tuttavia, l'implementazione di ciò consente l'uniformità e la sicurezza del tipo per i riferimenti incrociati quando si utilizza la classe. Si consiglia di utilizzare questa convenzione di denominazione.
>
> La creazione dell'istanza basata su **ProcessGuideStepName** del passaggio è implementata nella classe **ProcessGuideStepDefaultFactory**. Nel raro caso in cui desideri una strategia diversa per creare l'istanza del passaggio, devi eseguire le seguenti operazioni:
> -   Crea una nuova classe factory ereditando da **ProcessGuidStepAbstractFactory**.
> -   Facoltativamente, crea una nuova classe di parametri che implementi l'interfaccia **ProcessGuideIStepCreationParameters** contenente i parametri necessari alla factory.
> -   Nella tua classe controller, esegui l'override dei metodi **stepFactory()** e **stepCreationParameters()** per restituire la factory e i parametri di cui sopra.

Il passaggio successivo consiste nell'implementare la funzionalità della classe **ProdProcessGuidePromptProductionIdStep**. È necessario implementare la logica per la creazione dell'interfaccia utente, l'elaborazione dei dati immessi dall'utente e la determinazione del completamento del passaggio.

### <a name="building-the-user-interface-for-the-first-step"></a>Creazione dell'interfaccia utente per il primo passaggio

L'interfaccia utente è creata utilizzando una classe che eredita dalla classe astratta **ProcessGuidePageBuilder**. Per questo passaggio, assegna un nome alla classe per rappresentare ciò che fa: **ProdProcessGuidePromptProductionIdPageBuilder**.

Il meccanismo di creazione dell'istanza della classe è simile alla creazione dell'istanza del passaggio dal controller. 

-   Decora la classe **ProdProcessGuidePromptProductionIdPageBuilder** con un attributo **ProcessGuidePageBuilderName**.

    ```xpp
    [ProcessGuidePageBuilderName(classStr(ProdProcessGuidePromptProductionIdPageBuilder))] public class ProdProcessGuidePromptProductionIdPageBuilder extends ProcessGuidePageBuilder
    ```

-   Nella classe **ProdProcessGuidePromptProductionIdStep** implementa il metodo astratto **pageBuilderName()** per restituire questo nome.

    ```xpp
    protected final ProcessGuidePageBuilderName pageBuilderName()
    {
        return classStr(ProdProcessGuidePromptProductionIdPageBuilder);
    }
    ```    

> [!TIP]
> Simile alla factory del passaggio, esiste anche un modello di factory astratto implementato per la factory del generatore di pagine. Pertanto, nel raro caso in cui desideri una strategia diversa per creare l'istanza del generatore di pagine, devi eseguire le seguenti operazioni:
> - Crea una nuova classe factory ereditando da **ProcessGuidePageBuilderAbstractFactory**.
> - Facoltativamente, crea una nuova classe di parametri che implementi l'interfaccia **ProcessGuideIPageBuilderCreationParameters** contenente i parametri necessari alla factory.
> - Nella tua classe passaggio, esegui l'override dei metodi **pageBuilderFactory()** e **pageBuilderCreationParameters()** per restituire la factory e i parametri di cui sopra.

Per implementare l'interfaccia utente è necessaria una pagina con una casella di testo per inserire l'ID dell'ordine di produzione, più un pulsante **OK** e un pulsante **Annulla**. Il pulsante **Annulla** deve uscire dal processo.

Per implementarlo, devi eseguire l'override di due metodi nella classe **ProdProcessGuidePromptProductionIdPageBuilder**:

-   Utilizza il metodo **addDataControls()** per aggiungere la casella di testo.

    ```xpp
    protected final void addDataControls(ProcessGuidePage _page)
    {
        _page.addTextBox(ProcessGuideDataTypeNames::ProdId, "@SYS4398", extendedTypeNum(ProdId));
    }
    ```   

-   Utilizza il metodo **addActionControls()** per aggiungere i pulsanti **OK** e **Annulla**.

    ```xpp
    protected final void addActionControls(ProcessGuidePage _page)
    {
        #ProcessGuideActionNames
        _page.addButton(step.createAction(#ActionOK), true);
        _page.addButton(step.createAction(#ActionCancelExitProcess));
    }
    ``` 

Questo aggiunge i controlli dei dati, seguiti dai pulsanti. Tuttavia, se vuoi creare una schermata con controlli e pulsanti per i dati intervallati, è possibile eseguire l'override del metodo **addControls()** per la flessibilità.

Un ulteriore scenario da considerare è come si ricrea la pagina in caso di errori di convalida, ad esempio se l'utente immette un ID ordine di produzione errato. La classe di base **ProcessGuidePageBuilder** implementa il comportamento predefinito, che ricrea l'interfaccia utente, cancella il valore scansionato e aggiunge il controllo degli errori con il messaggio di errore. Poiché questo è il comportamento predefinito che vuoi utilizzare, non è necessario aggiungere alcun codice per la gestione degli errori.

> [!TIP]
> Se desideri implementare un comportamento dell'interfaccia utente personalizzato per situazioni di errore, puoi eseguire l'override di uno o più metodi **rebuildFromRequestPage()**, **isErrorState()**, e **reuseRequestPageOnError()**.

### <a name="processing-the-user-entered-data-in-the-first-step"></a>Elaborazione dei dati immessi dall'utente nel primo passaggio

Il trattamento dei dati avviene nella classe **ProcessGuideDataProcessorDefault** che a sua volta invoca la classe legactìy **WhsRfControlData**. Non sono necessarie modifiche a questo comportamento predefinito e **WhsRfControlData** ha già una logica per convalidare il campo **ProdId** quindi non è necessario scrivere alcuna logica per gestirlo. In caso di estensioni richieste per la logica di convalida, considera l'utilizzo del meccanismo di estensione basato su **WhsControl**.

### <a name="determine-if-the-first-step-is-complete"></a>Determinare se il primo passaggio è completato

Quando la convalida ha esito positivo, è il momento di contrassegnare il passaggio come completato. Questa operazione viene eseguita nella classe di base, ma è necessario implementare la condizione per determinare il completamento del passaggio. Il seguente metodo sostituito lo fa.

```xpp
protected final boolean isComplete()
{
    WhsrfPassthrough pass = controller.parmSessionState().parmPass();
    ProdId prodId = pass.lookup(ProcessGuideDataTypeNames::ProdId);
        return (prodId != '');
}
```   

### <a name="step-two-view-order-details-and-confirm"></a>Passaggio 2: visualizza i dettagli dell'ordine e conferma

Nel secondo passaggio del processo, all'utente viene mostrata una schermata con i dettagli sull'ordine. L'utente può fare clic sul pulsante **OK** per confermare l'inizio dell'ordine di produzione, oppure fare clic su **Annulla** per tornare all'inizio del processo. Per questo esempio, dai al passaggio il nome **ProdProcessGuideConfirmProductionOrderStep** e la classe del generatore di pagine **ProdProcessGuideConfirmProductionOrderPageBuilder**.

La classe ProdProcessGuideConfirmProductionOrderStep ha il seguente aspetto.

```xpp
[ProcessGuideStepName(classStr(ProdProcessGuideConfirmProductionOrderStep))]
public class ProdProcessGuideConfirmProductionOrderStep extends ProcessGuideStep
{
    protected final ProcessGuidePageBuilderName pageBuilderName()
    {
        return classStr(ProdProcessGuideConfirmProductionOrderPageBuilder);
     }
}
```     

Poiché l'utente non inserisce alcun valore qui, non è necessario eseguire l'override del metodo **isComplete()**. Il passaggio è completato quando l'utente fa clic su **OK**.

La classe del generatore di pagine sostituisce il metodo **addDataControls()** per aggiungere tre etichette. La prima etichetta mostra l'ID dell'ordine di produzione, la seconda contiene informazioni sull'articolo (come ID articolo, dimensioni o descrizione) e la terza contiene la quantità e l'unità di misura.

Il metodo **addActionControls()** viene quindi sostituito per aggiungere 2 pulsanti: il pulsante **ok** e il pulsante **Annulla** per annullare il processo e tornare all'inizio del processo.

```xpp
/// <summary>
/// The <c>ProdProcessGuideConfirmProductionOrderPageBuilder</c> builds a page that allows the user to see details of a production order
/// and then confirm.
/// </summary>
[ProcessGuidePageBuilderName(classStr(ProdProcessGuideConfirmProductionOrderPageBuilder))]
public class ProdProcessGuideConfirmProductionOrderPageBuilder extends ProcessGuidePageBuilder
{
    protected void addDataControls(ProcessGuidePage _page)
    {
        WhsrfPassthrough pass = controller.parmSessionState().parmPass();
        ProdTable prodTable = ProdTable::find(pass.lookup(ProcessGuideDataTypeNames::ProdId));
        UnitOfMeasureSymbol inventUOM = InventTableModule::find(prodTable.ItemId, ModuleInventPurchSales::Invent).UnitId;
        
        _page.addLabel(ProcessGuideDataTypeNames::ProdIdLabelName, strFmt("@WAX1684", prodTable.ProdId), extendedTypeNum(ProdId));
        _page.addLabel(ProcessGuideDataTypeNames::ItemInfo, this.generateItemInfoForProdId(pass.lookup(ProcessGuideDataTypeNames::ProdId)), extendedTypeNum(WHSRFUndefinedDataType));
        _page.addLabel(ProcessGuideDataTypeNames::QtyLabelName, strFmt("@WAX1685", WHSWorkExecuteDisplay::num2StrDisplay(ProdUpdStartUp::proposalStartUpQty(prodTable.ProdId)), inventUOM), extendedTypeNum(WHSRFQuantityAndUOM));

        if (PdsGlobal::pdsIsCWItem(prodTable.ItemId))
        {
            _page.addLabel(ProcessGuideDataTypeNames::InventQtyLabelName, strFmt("@WAX1685", WHSWorkExecuteDisplay::num2StrDisplay(ProdUpdStartUp::pdsCWProposalStartupQty(prodTable.ProdId)), PdsCatchWeightItem::pdsCWUnitId(prodTable.ItemId)), extendedTypeNum(WHSRFQuantityAndUOM));
        }
    }

    protected void addActionControls(ProcessGuidePage _page)
    {
        #ProcessGuideActionNames
        _page.addButton(step.createAction(#ActionOK), true);
        _page.addButton(step.createAction(#ActionCancelResetProcess));
    }
```

> [!NOTE]
> Puoi trovare lo stesso codice sorgente per i metodi X++ in questo argomento utilizzando Application Explorer. Filtra per il nome della classe, quindi fai clic con il pulsante destro del mouse sul nome della classe e seleziona **Visualizza codice**.

### <a name="step-3-start-the-production-order"></a>Passaggio 3: avvia l'ordine di produzione

Il terzo passaggio esegue la logica aziendale di avvio dell'ordine di produzione. Questo passaggio è leggermente diverso dai passaggi precedenti, in quanto non ha un'interfaccia utente. Questo passaggio viene eseguito in modo invisibile quando l'utente fa clic su **ok** nel passaggio precedente.

La classe astratta **ProcessGuideStepWithoutPrompt** implementa il comportamento predefinito per tali passaggi. Il passaggio attuale, quindi, deve estendere la classe **ProcessGuideStepWithoutPrompt** e eseguire l'override del metodo **doExecute()**.

Il seguente esempio di codice mostra la classe e l'implementazione del metodo **doExecute()**. Il metodo recupera semplicemente l'ID dell'ordine e l'ID utente dallo stato della sessione e richiama il metodo per avviare questo ordine di produzione.

```xpp
/// <summary>
/// The <c>ProdProcessGuideStartProductionOrderStep</c> represents a step that starts a production order.
/// </summary>
[ProcessGuideStepName(classStr(ProdProcessGuideStartProductionOrderStep))]
public class ProdProcessGuideStartProductionOrderStep extends ProcessGuideStepWithoutPrompt
{
    protected final void doExecute()
    {
        WhsrfPassthrough pass = controller.parmSessionState().parmPass();
        WHSUserId userId = pass.lookup(ProcessGuideDataTypeNames::UserId);
        ProdTable prodTable = ProdTable::find(pass.lookup(ProcessGuideDataTypeNames::ProdId));
        WhsWorkExecute workExecute = WhsWorkExecute::construct();
        workExecute.prodStartUp(prodTable.ProdId, ProdUpdStartUp::proposalStartUpQty(prodTable.ProdId), userId);

        this.addProcessCompletionMessage();

        super();
    }

}
```

In caso di eccezione, la logica di gestione delle eccezioni del framework garantisce il rollback del processo al passaggio precedente.

> [!NOTE]
> La chiamata ad **addProcessCompletionMessage()** aggiunge ai parametri di spostamento il messaggio "Lavoro completato". Il passaggio successivo (supponendo che disponga di un'interfaccia utente) visualizzerà questo messaggio. Le classi di base gestiscono questa logica e non è necessario aggiungere codice specifico alle classi di processo per ottenere questo comportamento.


### <a name="building-the-navigation-through-the-steps"></a>Creare lo spostamento tramite i passaggi

La classe di base **ProcessGuideController** crea l'istanza della classe **ProcessGuideNavigationAgentDefault** che si basa su un percorso di spostamento predefinito, che è una semplice mappa dei passaggi di origine e destinazione. Per lo scenario di avvio della produzione, poiché non esiste una diramazione condizionale, questa implementazione sarebbe sufficiente. Pertanto, devi solo eseguire l'override del metodo **initializeNavigationRoute()** per definire il percorso di spostamento.

```xpp
    protected ProcessGuideNavigationRoute initializeNavigationRoute()
    {
        ProcessGuideNavigationRoute navigationRoute = new ProcessGuideNavigationRoute();
        navigationRoute.addFollowingStep(classStr(ProdProcessGuidePromptProductionIdStep), classStr(ProdProcessGuideConfirmProductionOrderStep));
        navigationRoute.addFollowingStep(classStr(ProdProcessGuideConfirmProductionOrderStep), classStr(ProdProcessGuideStartProductionOrderStep));
        navigationRoute.addFollowingStep(classStr(ProdProcessGuideStartProductionOrderStep), classStr(ProdProcessGuidePromptProductionIdStep));

        return navigationRoute;
    }
```

Ci sono processi in cui ci saranno ramificazioni condizionali (basate sulle azioni dell'utente o su qualsiasi altra condizione). Tali processi devono fare quanto segue:

-   Implementare agenti di navigazione specifici ereditati dalla classe **ProcessGuideNavigationAgent**.

-   Implementare la factory dell'agente di spostamento specifica ereditata dalla classe **ProcessGuideNavigationAgentAbstractFactory** contenente la logica per creare un'istanza dell'agente di spostamento corretto in base al passaggio corrente, allo stato della sessione, all'azione dell'utente o ad altra logica.

-   Facoltativamente, eseguire l'override del metodo **navigationAgentCreationParameters()** nella classe controller per passare parametri adeguati.

-   Eseguire l'override di **navigationAgentFactory()** nel controller per creare un'istanza della factory dell'agente di navigazione creata sopra.

### <a name="action-classes"></a>Classi di azioni

Le classi di azioni rappresentano le azioni dell'utente, quindi questo esempio usa l'azione **ok** per mostrare come vengono create le azioni.

```xpp
[ProcessGuideActionName(#ActionOK)]
public class ProcessGuideOKAction extends ProcessGuideAction
{
    public final str label()
    {
        return "@SYS5473";
     }
     protected final void doExecute()
     {
        step.executeOKAction();
      }
}
```    

La classe deve implementare 2 metodi astratti:

-   **label()**, che restituisce l'etichetta da visualizzare in un controllo pulsante legato a questa azione.

-   **doExecute()**, che esegue l'azione. Come accennato in precedenza, il pulsante **ok** esegue semplicemente un callback al passaggio. Tuttavia, altre azioni potrebbero avere una logica più complessa.

Vengono create le istanze delle azioni utilizzando il framework **SysExtension** basato sull'attributo **ProcessGuideActionName**. Simile alla creazione dell'istanza dei generatori di pagine, la classe del passaggio implementa la factory di azione predefinita ed è possibile sostituirla. Il generatore di pagine aggiunge un controllo pulsante come questo.

```xpp
_page.addButton(step.createAction(#ActionOK), true);
```

In tal modo, chiede al passaggio di creare una classe di azione per il nome passato e lega tale azione al pulsante.

### <a name="summary"></a>Riepilogo

Per riassumere tutto ciò che è stato spiegato in questo argomento, ecco un riepilogo completo del codice necessario per il processo:

1.  **ProdProcessGuideProductionStartController**

    1.  Esegui l'override di **initialStepName()** per fornire il nome del primo passaggio.
    2.  Esegui l'override di **initializeNavigationRoute()** per creare la mappa di spostamento.

        ```xpp
        /// <summary>
        /// The <c>ProdProcessGuideProductionStartController</c> class is the controller class for the production order start process guide.
        /// </summary>
        [WHSWorkExecuteMode(WHSWorkExecuteMode::StartProdOrder)]
        public class ProdProcessGuideProductionStartController extends ProcessGuideController
        {
            protected ProcessGuideStepName initialStepName()
            {
                return classStr(ProdProcessGuidePromptProductionIdStep);
            }

            protected ProcessGuideNavigationRoute initializeNavigationRoute()
            {
                ProcessGuideNavigationRoute navigationRoute = new ProcessGuideNavigationRoute();
                navigationRoute.addFollowingStep(classStr(ProdProcessGuidePromptProductionIdStep), classStr(ProdProcessGuideConfirmProductionOrderStep));
                navigationRoute.addFollowingStep(classStr(ProdProcessGuideConfirmProductionOrderStep), classStr(ProdProcessGuideStartProductionOrderStep));
                navigationRoute.addFollowingStep(classStr(ProdProcessGuideStartProductionOrderStep), classStr(ProdProcessGuidePromptProductionIdStep));

                return navigationRoute;
            }

        }
        ```

2.  **ProdProcessGuidePromptProductionIdStep**

    1.  Esegui l'override di **isComplete()** per specificare quando il passaggio è considerato completato.
    2.  Esegui l'override di **pageBuilderName()** per specificare il generatore di pagine da utilizzare.

        ```xpp
        /// <summary>
        /// The <c>ProdProcessGuidePromptProductionIdStep</c> represents a step that 
        /// that prompts the user for a production order id.
        /// </summary>
        [ProcessGuideStepName(classStr(ProdProcessGuidePromptProductionIdStep))]
        public class ProdProcessGuidePromptProductionIdStep extends ProcessGuideStep
        {
            protected boolean isComplete()
            {
                WhsrfPassthrough pass = controller.parmSessionState().parmPass();
                ProdId prodId = pass.lookup(ProcessGuideDataTypeNames::ProdId);

                return (prodId != '');
            }

            protected ProcessGuidePageBuilderName pageBuilderName()
            {
                return classStr(ProdProcessGuidePromptProductionIdPageBuilder);
            }

        }
        ```

3.  **ProdProcessGuidePromptProductionIdPageBuilder**

    1.  Esegui l'override di **addDataControls()** per aggiungere la casella di testo **ID prodotto**.
    2.  Esegui l'override di **addActionControls()** per aggiungere i pulsanti **OK** e **Annulla**.
        
        ```xpp
        /// <summary>
        /// The <c>ProdProcessGuidePromptProductionIdPageBuilder</c> class builds a page 
        /// that prompts the user for a production order id.
        /// </summary>
        [ProcessGuidePageBuilderName(classStr(ProdProcessGuidePromptProductionIdPageBuilder))]
        public class ProdProcessGuidePromptProductionIdPageBuilder extends ProcessGuidePageBuilder
        {
            protected void addDataControls(ProcessGuidePage _page)
            {
                _page.addTextBox(ProcessGuideDataTypeNames::ProdId, "@SYS4398", extendedTypeNum(ProdId));
            }

            protected void addActionControls(ProcessGuidePage _page)
            {
                #ProcessGuideActionNames
                _page.addButton(step.createAction(#ActionOK), true);
                _page.addButton(step.createAction(#ActionCancelExitProcess));
            }

        }
        ```

4.  **ProdProcessGuideConfirmProductionOrderStep**

    1.  Esegui l'override di **pageBuilderName()** per specificare il generatore di pagine da utilizzare.
        
        ```xpp
        /// <summary>
        /// The <c>ProdProcessGuideConfirmProductionOrderStep</c> class represents the step for viewing production order
        /// details and confirming the same.
        /// </summary>
        [ProcessGuideStepName(classStr(ProdProcessGuideConfirmProductionOrderStep))]
        public class ProdProcessGuideConfirmProductionOrderStep extends ProcessGuideStep
        {    
            protected ProcessGuidePageBuilderName pageBuilderName()
            {
                return classStr(ProdProcessGuideConfirmProductionOrderPageBuilder);
            }

        }
        ```

3.  **ProdProcessGuideConfirmProductionOrderPageBuilder**

    1.  Esegui l'override di **addDataControls()** per aggiungere le etichette delle informazioni sull'ordine, sull'articolo e sulla quantità.

    2.  Esegui l'override di **addActionControls()** per aggiungere i pulsanti **OK** e **Annulla**.
        
        ```xpp
        /// <summary>
        /// The <c>ProdProcessGuideConfirmProductionOrderPageBuilder</c> builds a page that allows the user to see details of a production order
        /// and then confirm.
        /// </summary>
        [ProcessGuidePageBuilderName(classStr(ProdProcessGuideConfirmProductionOrderPageBuilder))]
        public class ProdProcessGuideConfirmProductionOrderPageBuilder extends ProcessGuidePageBuilder
        {
            protected void addDataControls(ProcessGuidePage _page)
            {
                WhsrfPassthrough pass = controller.parmSessionState().parmPass();
                ProdTable prodTable = ProdTable::find(pass.lookup(ProcessGuideDataTypeNames::ProdId));
                UnitOfMeasureSymbol inventUOM = InventTableModule::find(prodTable.ItemId, ModuleInventPurchSales::Invent).UnitId;

                _page.addLabel(ProcessGuideDataTypeNames::ProdIdLabelName, strFmt("@WAX1684", prodTable.ProdId), extendedTypeNum(ProdId));
                _page.addLabel(ProcessGuideDataTypeNames::ItemInfo, this.generateItemInfoForProdId(pass.lookup(ProcessGuideDataTypeNames::ProdId)), extendedTypeNum(WHSRFUndefinedDataType));
                _page.addLabel(ProcessGuideDataTypeNames::QtyLabelName, strFmt("@WAX1685", WHSWorkExecuteDisplay::num2StrDisplay(ProdUpdStartUp::proposalStartUpQty(prodTable.ProdId)), inventUOM), extendedTypeNum(WHSRFQuantityAndUOM));

                if (PdsGlobal::pdsIsCWItem(prodTable.ItemId))
                {
                    _page.addLabel(ProcessGuideDataTypeNames::InventQtyLabelName, strFmt("@WAX1685", WHSWorkExecuteDisplay::num2StrDisplay(ProdUpdStartUp::pdsCWProposalStartupQty(prodTable.ProdId)), PdsCatchWeightItem::pdsCWUnitId(prodTable.ItemId)), extendedTypeNum(WHSRFQuantityAndUOM));
                }
            }

            protected void addActionControls(ProcessGuidePage _page)
            {
                #ProcessGuideActionNames
                _page.addButton(step.createAction(#ActionOK), true);
                _page.addButton(step.createAction(#ActionCancelResetProcess));
            }

        ```

        > [!NOTE]
        > Il metodo **generateItemInfoForProdId()** utilizzato per generare le etichette delle informazioni sull'articolo è escluso da questo argomento. Questo metodo interroga alcune tabelle per ottenere l'ID articolo, la descrizione e le dimensioni. Per una migliore comprensione di **generateItemInfoForProdId()**, guarda il codice sorgente.

4.  **ProdProcessGuideStartProductionOrderStep**

    1.  Esegui l'override di **doExecute()** per eseguire il processo di avvio della produzione e aggiungere il messaggio di completamento del processo.

        ```xpp
        /// <summary>
        /// The <c>ProdProcessGuideStartProductionOrderStep</c> represents a step that starts a production order.
        /// </summary>
        [ProcessGuideStepName(classStr(ProdProcessGuideStartProductionOrderStep))]
        public class ProdProcessGuideStartProductionOrderStep extends ProcessGuideStepWithoutPrompt
        {
            protected final void doExecute()
            {
                WhsrfPassthrough pass = controller.parmSessionState().parmPass();
                WHSUserId userId = pass.lookup(ProcessGuideDataTypeNames::UserId);
                ProdTable prodTable = ProdTable::find(pass.lookup(ProcessGuideDataTypeNames::ProdId));
                WhsWorkExecute workExecute = WhsWorkExecute::construct();
                workExecute.prodStartUp(prodTable.ProdId, ProdUpdStartUp::proposalStartUpQty(prodTable.ProdId), userId);

                this.addProcessCompletionMessage();

                super();
            }

        }
        ```

> [!NOTE]
> Nota che molti dei modelli comuni (rigenerazione dell'interfaccia utente in caso di errore, impostazione del messaggio di completamento del processo, **ok** e **Annulla**) sono stati spostati nel framework, evitando così allo sviluppatore dell'applicazione la scrittura di codice standard che è sia soggetto a errori, sia presenta il rischio di comportamenti incoerenti tra i processi. Laddove lo scenario deve deviare dal percorso comune, tuttavia, allo sviluppatore dell'applicazione viene fornita l'opzione di ignorare i metodi adeguati, ma in questo caso si tratta di una deviazione intenzionale che è sia esplicita che tracciabile.


### <a name="extending-a-business-process"></a>Estensione di un processo aziendale

Finora, questo argomento ha evidenziato come costruire un nuovo processo utilizzando il framework **ProcessGuide**. In questa sezione finale troverai alcuni esempi di come questo processo aziendale può essere esteso.

### <a name="add-a-step-in-a-flow-using-processguidenavigationagentdefault"></a>Aggiungere un passaggio in un flusso (usando ProcessGuideNavigationAgentDefault)

Dove estendere:

-   Figlio della classe **ProcessGuideController** per il processo.

Come estendere:

-   Estendi il metodo **initializeNavigationRoute()** nella classe controller e invoca **addFollowingStep()** nella classe **ProcessGuideNavigationRoute**.

### <a name="add-a-step-in-a-flow-using-custom-navigation-agent"></a>Aggiungere un passaggio in un flusso (usando l'agente di spostamento personalizzato)

Dove estendere:

-   Figlio di **ProdProcessGuideNavigationAgentFactory/ProdProcessGuideNavigationAgent**.

Come estendere:

-   Crea una nuova classe figlio di **ProcessGuideNavigationAgent** che restituisce il nome del passaggio desiderato.

-   Crea una nuova classe derivante da **ProcessGuideNavigationAgentFactory** che restituisce in modo condizionale l'agente di spostamento creato sopra.

-   Estendi il metodo **navigationAgentFactory()** nella classe del controller per restituire la factory creata sopra.

### <a name="add-a-new-control-in-the-ui-of-an-existing-step"></a>Aggiungere un nuovo controllo nell'interfaccia utente di un passaggio esistente 

Dove estendere:

-   Figlio di **ProdProcessGuidePageBuilder** per il passaggio.

Come estendere:

-   Estendi il metodo **addDataControls()** e aggiungi il controllo aggiuntivo.

### <a name="complete-overhaul-of-the-user-interface-in-an-existing-step"></a>Revisione completa dell'interfaccia utente in un passaggio esistente

Dove estendere:

-   Figlio di **ProdProcessGuideStep**.

Come estendere:

-   Crea una nuova classe figlio della classe **ProdProcessGuidePageBuilder** e implementa l'interfaccia utente desiderata.

-   Estendi il metodo **pageBuildeName()** nella classe del passaggio per restituire **ProcessGuidePageBuilderNameAttribute** per la classe creata sopra.

### <a name="alter-logic-when-a-step-is-considered-complete"></a>Alterare la logica quando un passaggio è considerato completato

Dove estendere:

-   Figlio di **ProdProcessGuideStep**.

Come estendere:

-   Estendi il metodo **isComplete()** per creare la logica aggiuntiva.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]