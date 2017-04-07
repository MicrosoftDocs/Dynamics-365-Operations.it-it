---
title: Gestione del conto lavoro di lavoro in produzione
description: In questo argomento viene descritto come le operazioni in conto lavoro vengono gestite in Microsoft Dynamics 365 per le operazioni. Ovvero viene illustrato come le operazioni di produzione assegnate a una risorsa vengono gestite da un fornitore.
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: LeanDocumentServiceCreation, PlanActivity, ProdBOMVendorListPage, ProdRoute, ProdTable, ProdTableListPage, PurchAgreementSubcontractorLookup, RouteTable, WrkCtrResourceGroup
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 268174
ms.assetid: fe47c498-4f48-42a2-a0cf-5436c19ab3ea
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: f707d45290682e79ee439ba0d504852429defa90
ms.openlocfilehash: 79430358bebd93fd96f1169d22737d3537dbfc08
ms.lasthandoff: 03/31/2017


---

# <a name="manage-subcontracting-work-in-production"></a>Gestione del conto lavoro di lavoro in produzione

In questo argomento viene descritto come le operazioni in conto lavoro vengono gestite in Microsoft Dynamics 365 per le operazioni. Ovvero viene illustrato come le operazioni di produzione assegnate a una risorsa vengono gestite da un fornitore.

In [processi di produzione production-process-overview.md] (), il lavoro può essere eseguito dalle risorse di proprietà o amministrate dai fornitori. In genere, le risorse fornitore vengono utilizzate per livellare il limite di domanda periodico che supera la capacità disponibile delle risorse proprie da una società. Il fornitore può inoltre possibile offrire specifico [] capacità delle risorse (resource-capabilities.md) o le risorse a un prezzo più basso.  

A seconda delle risorse fornitore utilizzate in un processo di produzione, alla lavorazione [] () routes-operations.md sono spesso logistici requisiti aggiuntivi, poiché il materiale e i prodotti semilavorati devono essere trasportati nel sito del fornitore. Selezionare il risultato dell'operazione in conto lavoro deve trasporto desiderata per uno presso l'ubicazione assegnata all'operazione successiva o a un magazzino dei prodotti finiti.  

Nel subappaltare operazioni o le attività vengono utilizzate, che influiscono su tutte le fasi delle operazioni, dalla definizione delle operazioni necessarie nella produzione, nella determinazione costi, nelle previsioni, nella pianificazione e la programmazione, la gestione della logistica per i materiali, prodotti semilavorati e dei prodotti finiti. Infine, le risorse richiedono i propri processi della stima e il controllo dei costi.  

Per le risorse interne, un tasso di costo fisso genere assegnato per un periodo. Di contro, il costo di risorse in conto lavoro è basato sul prezzo di acquisto del servizio correlato. Il servizio viene definito come altro prodotto e viene utilizzato per determinare di approvvigionamento e di acquisto i processi per un'operazione in conto lavoro specificata.  

Attualmente, non viene esplicito concetto dei prodotti semilavorati in Microsoft Dynamics 365 per le operazioni. Per un ordine di produzione che richiede la più operazioni per la trasformazione delle materie prime un prodotto finito, il prodotto finito viene registrato al magazzino solo l'ultima operazione. I prodotti semilavorati che i prodotti più precoci delle operazioni vengono spiegati al lavoro in corso (WIP), non vengono registrati o non tiene traccia in magazzino. Sebbene sia possibile condividere i cicli di lavorazione e distinte base (BOMs) in più piccoli più unità, aumentare di tale approccio il numero di voce doganale, distinte base e cicli di lavorazione che devono essere gestiti.  

Sono disponibili due metodi per la modellazione di lavoro di conto lavoro per le operazioni di produzione. Questi metodi diversi in modo che il processo di conto lavoro può essere modellizzato, in modo che i prodotti semilavorati vengono rappresentati nel processo e in modo che il controllo costi viene gestito.

-   Conto lavoro le operazioni del ciclo di lavorazione negli ordini di produzione o negli ordini lotto
    -   Il prodotto di assistenza deve essere stoccato un prodotto e che fa parte della DBA.
    -   Questo metodo supporta First In, First Out (FIFO) o Costo standard.
    -   I prodotti semilavorati vengono rappresentati dal prodotto servizio del processo.
    -   Il controllo dei costi allocati i costi associati a lavoro in conto lavoro ai costi del materiale.
-   Conto lavoro delle attività del flusso di produzione in un flusso di produzione snella
    -   Il servizio è un prodotto non stoccato di assistenza e non fanno parte della DBA.
    -   Questo metodo utilizza i contratti di acquisto come contratti di assistenza.
    -   Questo metodo utilizza la determinazione costi di tipo backflush.
    -   Questo metodo consente approvvigionamento e aggregazione asincrono. Il flusso di materiale non dipende dal processo di approvvigionamento).
    -   Il controllo dei costi assegnato il lavoro in conto lavoro nel relativo blocchetto di scomposizione dei costi.

## <a name="subcontracting-of-route-operations"></a>Conto lavoro le operazioni del ciclo di lavorazione
Per utilizzare il conto lavoro le operazioni del ciclo di lavorazione per la produzione o ordini lotto, il prodotto di servizio utilizzato per l'approvvigionamento di assistenza venga definito come prodotto ** assistenza ** del tipo. Inoltre, è possibile selezionare un gruppo di modelli di articoli con ** prodotto non stoccato ** di opzione nel set ** criteri di magazzino ** ** Sì **. Questa opzione indica se il prodotto è contabilizzato come magazzino relative all'entrata prodotti (** prodotto non stoccato ** = ** Sì **), ovvero se il prodotto Sezione in un conto profitti e perdite (** prodotto non stoccato ** ** = non **). Sebbene questo comportamento può essere presente contraddittorio, in base al fatto che solo i prodotti con i criteri creare le transazioni di magazzino che è possibile utilizzare il controllo dei costi per calcolare il costo pianificato e determinare il costo effettivo quando un ordine di produzione è terminato.  

Per essere considerato nel calcolo dei costi e di pianificazione, il servizio deve essere aggiunto alla DBA. La riga DBA sia di ** fornitore ** tipi e deve essere assegnato all'operazione del ciclo di lavorazione che il servizio è assegnati. Questa operazione del ciclo di lavorazione deve disporre di un utilizzo di determinazione costi e condizione di risorse che indica una risorsa ** del fornitore ** digitare per collegare l'operazione e assistenza correlato al conto fornitore corrispondente.  

Se la configurazione viene utilizzata, viene creato un ordine fornitore per il prodotto correlato di assistenza, in base alla stima di un ordine di produzione. L'ordine fornitore del servizio viene utilizzato come un nuovo per le operazioni in conto lavoro. Il lavoro in conto lavoro può essere gestito da ** lavoro in conto lavoro ** la pagina elenco in Controllo produzione. Il lavoro in conto lavoro viene utilizzato per spedire le materie prime e, quindi, un prodotto semilavorato al fornitore in preparazione dell'operazione. Viene inoltre utilizzata per ricevere il prodotto risultante dell'operazione in conto lavoro in arrivo articoli, in cui il prodotto di assistenza viene utilizzato per identificare l'arrivo di prodotti semilavorati. Quando la riga ordine fornitore è ricevuta, l'operazione di produzione viene aggiornata come completata.  

Un ordine di produzione possono essere incluse diverse operazioni e ciascuna operazione può essere assegnata a un fornitore diverso. Di conseguenza, un ordine di produzione completa potrebbe attivare gli ordini fornitore.

## <a name="subcontracting-of-production-flow-activities"></a>Conto lavoro da attività del flusso di produzione
Lean snella [] () lean-manufacturing-overview.md la soluzione modellizzazioneutilizzo di conto lavoro come servizio correlato a un'attività a [flusso di produzione (http://ax.help.dynamics.com/en/wiki/create-a-production-flow-version/)] (argomento della Guida di attività). Di conseguenza, questo tipo di conto lavoro è noto anche come [in conto lavoro basato sull'attività. activity-based-subcontracting.md] () Tipo speciale di costo per gruppo, ** esternalizzazione ** diretta, è stato immesso e servizi in conto lavoro non fanno parte della DBA dei prodotti finiti. Quando si utilizza la produzione snella, tutte le attività vengono definite da kanban che possono essere collegati a a uno o più attività del flusso di produzione. Finora, la descrizione suona analogamente a una spiegazione degli ordini di produzione. Tuttavia, mentre gli ordini di produzione devono terminare sempre aggiunto un prodotto finito, è possibile creare kanban per fornire un prodotto semilavorato. Non è necessario immettere un nuovo prodotto e un livello DBA.  

Poiché le regole kanban possono essere molto il caching attivo, è possibile definire le varianti diverse di rifornimento per lo stesso prodotto in un flusso di produzione. Quando si utilizza il conto lavoro snella, il flusso di materiale e il flusso finanziario sono separati rigorosamente. Tutto il flusso di materiale è rappresentato da attività di kanban. Gli ordini fornitore per i prodotti di assistenza e le registrazioni di entrata di tali servizi possono essere automatici, in base allo stato dei processi kanban nel flusso di produzione. I processi kanban è possibile avviare e completati anche prima degli ordini fornitore vengono creati. I documenti in conto lavoro (ricevimento degli acquisti e dell'ordine fornitore del servizio) possono essere aggregati al periodo e al servizio. Di conseguenza, il numero di documenti e le righe di acquisto può essere gestito Small, anche nelle operazioni ripetitive particolarmente in cui i fornitori forniscono i servizi in conto lavoro in un flusso del singolo pezzo.

### <a name="modeling-subcontracting-in-a-production-flow"></a>Modellizzazione di conto lavoro in un flusso di produzione

In a [flusso di produzione snella lean-manufacturing-modeling-lean-organization.md] (), un'attività di processo può essere definita come subappaltato quando è assegnato a una cella di lavoro (gruppo di risorse) che prevede di un nome univoco con un venditore. Quando una cella di lavoro viene subappaltata, le attività di processo correlati devono essere collegate a una riga attiva del contratto di acquisto contenente un articolo di tipo Assistenza e il prezzo del servizio. Contratto di assistenza dell'attività definisce inoltre il rapporto di calcolo tra la quantità di prodotto del processo kanban e la quantità risultante di assistenza. È possibile selezionare se la quantità di assistenza viene calcolata in base al numero di processi, la quantità idonea di l dichiarata nei processi, oppure la quantità totale di prodotti (questa quantità totale include i prodotti scartati).  

Le attività di trasferimento possono inoltre essere impostate come subappaltate. Questa definizione modo implicito quando si seleziona la parte responsabile della spedizione in attività di trasferimento. Quando si seleziona ** spedizioniere o ** ** destinatario **, se il magazzino corrispondente di entrata o di inizio corrisponde a un magazzino batch gestito, l'attività verrà considerato subappaltato. Quando si seleziona ** vettore **, l'attività verrà sempre subappaltata. Poiché le attività di processo in conto lavoro, un'attività di trasferimento in conto lavoro deve essere collegata a un contratto di assistenza prima del flusso di produzione possa essere attivato.

### <a name="backflush-costing"></a>Determinazione costi di tipo backflush

La contabilità industriale di lavoro in conto lavoro è completamente integrata per la registrazione dei costi per la soluzione della produzione snella (determinazione costi di tipo backflush). Quando il ricevimento dell'ordine fornitore del servizio viene registrata, oppure quando viene eseguita la fatturazione, il costo del servizio è assegnato il flusso di produzione. Per determinazione costi di tipo backflush, lo scostamento dei servizi in conto lavoro viene calcolato in contropartita il blocchetto di conto lavoro del costo standard dei prodotti in entrata rispetto alle quantità ricevute la fattura effettivi di assistenza.

## <a name="material-supply-for-subcontracted-operations"></a>Rifornimento materiale per le operazioni in conto lavoro
I prodotti semilavorati e altri materiali correlati devono essere trasferiti nella posizione in cui viene eseguito l'intervento fisicamente. Se si utilizzano operazioni e le attività in conto lavoro, il trasferimento è correlato al trasporto aggiuntivo in un sito specificati azionato. L'assegnazione del materiale nella DBA all'operazione in conto lavoro, dichiarazione del materiale deve essere messo in scenae a quella di entrata del gruppo di risorse per la risorsa allocata. Pianificazione generale o di produzione snella di rifornimento al materiale a tale posizione.  

Per definire cui è si trova a un sito fornitore, è consigliabile consigliate nel settore specificare un magazzino batch gestito. È possibile definire facilmente un magazzino batch gestito crea un nuovo magazzino e assegna il conto fornitore. Per documentare che il materiale deve essere trasferito al fornitore prima del catalogo possa essere eseguita, è necessario assegnare il magazzino batch gestito al magazzino di entrata del gruppo di risorse che comprende la risorsa.  

Per specificare il materiale al magazzino, è possibile utilizzare le strategie più:

-   Ordini di trasferimento
-   Giornali di registrazione trasferimenti
-   Kanban di prelievo
-   Acquisti diretto percorso del fornitore

I prodotti semilavorati sono l'eccezione a questa regola. Per trasferire prodotti semilavorati, sarà possibile utilizzare solo con le seguenti opzioni:

-   Per produzione e ordini lotto, i prodotti semilavorati possono essere trasferiti solo una connessione logica comune utilizzando il giornale di registrazione distinte di prelievo ** lavoro in conto lavoro ** dalla pagina elenco. Il giornale di registrazione crea un documento bolla di consegna che può essere utilizzato per trasferire le materie prime semilavorata e al fornitore.
-   Per le operazioni in conto lavoro in un flusso di produzione, il trasferimento di prodotti semilavorati non vengano dal ricevimento di kanban di produzione o di prelievo della sede del fornitore. Per definire un'attività di trasferimento esplicita, è possibile terminare un kanban di produzione con un'attività di trasferimento aggiuntiva.

** Nota: ** Un ciclo di lavorazione produzione per un singolo ordine di produzione non può eseguire più siti. Questa regola vale anche per il lavoro in conto lavoro. Di conseguenza, i magazzini che rappresentano le ubicazioni gestire specificati materiali devono essere definiti nello stesso sito Risorse interne utilizzate nel ciclo di lavorazione. Sebbene i flussi di produzione possano eseguire i siti, non possono trasportare i prodotti semilavorati da un sito a un altro, poiché tale operazione implica una modifica il contesto di costo.  

In genere, il magazzino di output e l'ubicazione di un gruppo di risorse in conto lavoro vengono assegnati direttamente al magazzino e percorso del passaggio successivo dell'operazione nel ciclo di lavorazione o nel flusso di produzione. Questa impostazione consente di ridurre l'importo di processo in corso o delle operazioni di trasferimento aggiuntivi di numeri che deve essere modellizzato.


