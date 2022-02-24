---
title: Gestire il lavoro in conto lavoro in produzione
description: In questo argomento viene descritto come le operazioni in conto lavoro vengono gestite in Dynamics 365 Supply Chain Management. Ovvero viene illustrato come le operazioni di produzione alllocate a una risorsa vengono gestite da un fornitore.
author: cvocph
manager: tfehr
ms.date: 11/03/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LeanDocumentServiceCreation, PlanActivity, ProdBOMVendorListPage, ProdRoute, ProdTable, ProdTableListPage, PurchAgreementSubcontractorLookup, RouteTable, WrkCtrResourceGroup, ProdBOMVendorListPagePreviewPane, ProdBOMVendor
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 268174
ms.assetid: fe47c498-4f48-42a2-a0cf-5436c19ab3ea
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9119655384cd05e5aa3622712e699b346a43f492
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4431372"
---
# <a name="manage-subcontracting-work-in-production"></a>Gestire il lavoro in conto lavoro in produzione

[!include [banner](../includes/banner.md)]

In questo argomento viene descritto come le operazioni in conto lavoro vengono gestite in Dynamics 365 Supply Chain Management. Ovvero viene illustrato come le operazioni di produzione alllocate a una risorsa vengono gestite da un fornitore.

Nei [processi di produzione](production-process-overview.md), il lavoro può essere eseguito da risorse di proprietà o amministrate dai fornitori. In genere, le risorse fornitore vengono utilizzate per l'eccesso periodico di domanda che supera la capacità disponibile delle risorse proprie di una società. Il fornitore può inoltre essere in grado di offrire specifiche [capacità risorsa](resource-capabilities.md) o risorse a un prezzo più basso.  

A seconda delle risorse fornitore utilizzate in un processo di produzione, un [ciclo di lavorazione](routes-operations.md) spesso ha requisiti logistici aggiuntivi, poiché il materiale e i prodotti semilavorati devono essere prima trasportati nel sito del fornitore. Quindi il risultato dell'operazione in conto lavoro deve essere trasportato o presso l'ubicazione assegnata all'operazione successiva o a un magazzino dei prodotti finiti.  

Quando si usano operazioni o attività in conto lavoro, queste influiscono su tutte le fasi delle operazioni, dalla definizione delle operazioni necessarie nella produzione, a determinazione costi, previsioni, pianificazione e programmazione, fino alla gestione della logistica per i materiali, prodotti semilavorati e dei prodotti finiti. Infine, le risorse richiedono propri processi per contabilità e controllo dei costi.  

Per le risorse interne, un tasso di costo fisso in genere è assegnato per un periodo. Di contro, il costo di risorse in conto lavoro è basato sul prezzo di acquisto del servizio correlato. Il servizio viene definito come un altro prodotto e viene utilizzato per determinare i processi di approvvigionamento e di acquisto per un'operazione in conto lavoro specificata.  

Attualmente, non esiste un esplicito concetto di prodotti semilavorati in Supply Chain Management. Per un ordine di produzione che richiede più operazioni per la trasformazione delle materie prime in prodotto finito, il prodotto finito viene registrato nuovamente nel magazzino solo nell'ultima operazione. I prodotti semilavorati prodotti da operazioni precedenti vengono considerati come WIP, ma non vengono registrati o tracciati in magazzino. Sebbene sia possibile dividere i cicli di lavorazione e le distinte base (DBA) in più unità inferiori, tale approccio aumenta il numero di prodotti, distinte base e cicli di lavorazione che devono essere gestiti.  

Sono disponibili due metodi per la modellazione del lavoro in conto lavoro per le operazioni di produzione. Questi metodi differiscono nel senso che il processo di conto lavoro può essere modellizzato, nel modo in cui i prodotti semilavorati vengono rappresentati nel processo e nel modo in cui il controllo costi viene gestito.

-   Assegnazione in conto lavoro delle operazioni del ciclo di lavorazione negli ordini di produzione o negli ordini batch
    -   Il prodotto di tipo servizio deve essere stoccato e deve far parte della DBA.
    -   Questo metodo supporta il costo standard o FIFO.
    -   I prodotti semilavorati vengono rappresentati dal prodotto di tipo servizio del processo.
    -   Il controllo dei costi alloca i costi associati a lavoro in conto lavoro ai costi del materiale.
-   Assegnazione in conto lavoro delle attività del flusso di produzione in un flusso di produzione snella
    -   Il servizio è un prodotto di tipo servizio non stoccato e non fa parte della DBA.
    -   Questo metodo utilizza i contratti di acquisto come contratti di servizio.
    -   Questo metodo utilizza la determinazione costi di tipo backflush.
    -   Questo metodo consente approvvigionamento e aggregato e asincrono. Il flusso di materiale non dipende dal processo di approvvigionamento.
    -   Il controllo dei costi assegna il lavoro in conto lavoro nel proprio blocco di scomposizione dei costi.

## <a name="subcontracting-of-route-operations"></a>Assegnazione in conto lavoro delle operazioni del ciclo di lavorazione
Per utilizzare il conto lavoro per le operazioni del ciclo di lavorazione per ordini di produzione o batch, il prodotto di tipo servizio utilizzato per l'approvvigionamento del servizio deve essere definito come prodotto di tipo  **Servizio**. Inoltre, deve avere un gruppo di modelli di articoli con l'opzione **Prodotto stoccato** in **Criteri di magazzino** impostata su **Sì**. Questa opzione indica se un prodotto è contabilizzato come magazzino all'entrata prodotti (**Prodotto stoccato** = **Sì**), ovvero se il prodotto è speso in un conto profitti e perdite (**Prodotto stoccato** = **No**). Sebbene questo comportamento può sembrare contraddittorio, è basato sul fatto che solo i prodotti con questi criteri creeranno operazioni di magazzino che possono essere utilizzate nel controllo dei costi per calcolare il costo pianificato e determinare il costo effettivo quando un ordine di produzione è terminato.  

Per essere considerato nella pianificazione e nel calcolo dei costi, il servizio deve essere aggiunto alla DBA. La riga DBA deve essere di tipo **Fornitore** e deve essere assegnata all'operazione del ciclo di lavorazione a cui il servizio è assegnato. Questa operazione del ciclo di lavorazione deve disporre di una risorsa e di un fabbisogno di risorse che puntano a una risorsa  di tipo **Fornitore** che connette l'operazione e il servizio correlato al conto fornitore corrispondente.  

Se questa configurazione viene utilizzata, viene creato un ordine fornitore per il prodotto servizio correlato, in base alla stima di un ordine di produzione. L'ordine fornitore del servizio viene utilizzato come riferimento per le operazioni in conto lavoro. Il lavoro in conto lavoro può essere gestito tramite la pagina elenco **Conto lavoro** in Controllo produzione. Il lavoro in conto lavoro viene utilizzato per spedire le materie prime e, infine, un prodotto semilavorato al fornitore in preparazione dell'operazione. Viene inoltre utilizzato per ricevere il prodotto risultante dell'operazione in conto lavoro in arrivo articoli, in cui il prodotto di tipo servizio viene utilizzato per identificare l'arrivo dei prodotti semilavorati. Quando la riga ordine fornitore è ricevuta, l'operazione di produzione viene aggiornata come completata.  

Un ordine di produzione può includere molte operazioni e ciascuna operazione può essere assegnata a un fornitore diverso. Di conseguenza, un ordine di produzione completo potrebbe attivare più ordini fornitore.

## <a name="subcontracting-of-production-flow-activities"></a>Assegnazione in conto lavoro di attività del flusso di produzione
La soluzione [lean manufacturing](lean-manufacturing-overview.md) modella il lavoro in conto lavoro come servizio correlato a un'attività di un [flusso di produzione](tasks/create-production-flow-version.md) (argomento della guida attività). Di conseguenza, questo tipo di conto lavoro è noto anche come [conto lavoro basato sull'attività.](activity-based-subcontracting.md) Un tipo speciale di tipo di gruppo di costi denominato **Esternalizzazione diretta** è stato introdotto e i servizi in conto lavoro non fanno parte della DBA dei prodotti finiti. Quando si utilizza il lean manufacturing, tutte le attività vengono definite da kanban che possono essere correlati a una o più attività del flusso di produzione. Finora, la descrizione suona analoga a una spiegazione degli ordini di produzione. Tuttavia, mentre gli ordini di produzione devono terminare sempre con un prodotto finito, è possibile creare kanban per fornire un prodotto semilavorato. Non è necessario immettere un nuovo prodotto e un livello DBA.  

Poiché le regole kanban possono essere molto dinamiche, è possibile definire varianti diverse di rifornimento per lo stesso prodotto in un flusso di produzione. Quando si utilizza il conto lavoro snello, il flusso di materiale e il flusso finanziario sono separati rigorosamente. Tutto il flusso di materiale è rappresentato da attività kanban. Gli ordini fornitore per i prodotti di tipo servizio e le registrazioni di entrata di tali servizi possono essere automatici, in base allo stato dei processi kanban nel flusso di produzione. I processi kanban possono essere avviati e completati anche prima che gli ordini fornitore vengono creati. I documenti di conto lavoro (ordine fornitore e ricevimento degli acquisti del servizio) possono essere aggregati per periodo e servizio. Di conseguenza, il numero di documenti e righe di acquisto può essere tenuto basso, anche in operazioni molto ripetitive in cui i fornitori forniscono i servizi in conto lavoro in un flusso a singolo componente.

### <a name="modeling-subcontracting-in-a-production-flow"></a>Modellizzazione del conto lavoro in un flusso di produzione

In un [flusso di produzione snella](lean-manufacturing-modeling-lean-organization.md), un'attività di processo può essere definita come in conto lavoro quando è assegnata a una cella di lavoro (gruppo di risorse) che prevede una singola risorsa fornitore. Quando una cella di lavoro viene assegnata in conto lavoro, le attività di processo correlate devono essere collegate a una riga attiva del contratto di acquisto attivo contenente un articolo di tipo Assistenza e il prezzo del servizio. Il contratto di servizio dell'attività definisce inoltre il rapporto di calcolo tra la quantità di prodotto del processo kanban e la quantità risultante di servizio. È possibile selezionare se la quantità di servizio viene calcolata in base al numero di processi, la quantità di prodotti dichiarata nei processi, oppure la quantità totale di prodotti (questa quantità totale include i prodotti scartati).  

Anche le attività di trasferimento possono essere impostate come in conto lavoro. Questa definizione avviene in modo implicito quando si seleziona la parte responsabile della spedizione nell' attività di trasferimento. Quando si seleziona **Spedizioniere** o **Destinatario**, se il magazzino corrispondente di origine o destinazione è un magazzino gestito da un fornitore, l'attività verrà considerata in conto lavoro. Quando si seleziona **Vettore**, l'attività è sempre in conto lavoro. Come le attività di processo in conto lavoro, un'attività di trasferimento in conto lavoro deve essere collegata a un contratto di servizio prima che il flusso di produzione possa essere attivato.

### <a name="backflush-costing"></a>Determinazione costi di tipo backflush

La contabilità industriale di lavoro in conto lavoro è completamente integrata nella determinazione costi per la soluzione lean manufacturing (determinazione costi di tipo backflush). Quando il ricevimento dell'ordine fornitore del servizio viene registrato, oppure quando viene eseguita la fatturazione, il costo del servizio è assegnato al flusso di produzione. Per la determinazione costi di tipo backflush, lo scostamento dei servizi in conto lavoro viene calcolato assegnando in contropartita il blocco di conto lavoro del costo standard dei prodotti in entrata rispetto alle quantità di servizio effettive ricevute e fatturate.

## <a name="material-supply-for-subcontracted-operations"></a>Rifornimento materiale per le operazioni in conto lavoro
I prodotti semilavorati e altri materiali correlati devono essere trasferiti nella ubicazione in cui viene eseguito l'il lavoro fisicamente. Se si utilizzano operazioni e le attività in conto lavoro, il trasferimento è spesso correlato al trasporto aggiuntivo in un sito gestito dal fornitore. Assegnando il materiale nella DBA all'operazione in conto lavoro, si dichiara che il materiale deve essere approntato all'ubicazione di entrata del gruppo di risorse per la risorsa allocata. La pianificazione generale o il rifornimento snello eseguono quindi il rifornimento del materiale in tale ubicazione.  

Per modellare l'inventario che si trova in un sito fornitore, è procedura consigliata nel settore specificare un magazzino gestito dal fornitore. È possibile definire facilmente un magazzino gestito dal fornitore creando un nuovo magazzino e assegnando il conto fornitore. Per documentare che il materiale deve essere trasferito al fornitore prima che un'operazione possa essere eseguita, è necessario assegnare il magazzino gestito dal fornitore al magazzino di entrata del gruppo di risorse che detiene la risorsa.  

Per rifornire il materiale al magazzino, è possibile utilizzare più strategie:

-   Ordini di trasferimento
-   Giornali di registrazione trasferimenti
-   Kanban di prelievo
-   Acquisto diretto all'ubicazione del fornitore

I prodotti semilavorati sono l'eccezione a questa regola. Per trasferire prodotti semilavorati, sarà possibile utilizzare solo le seguenti opzioni:

-   Per ordini di  produzione e ordini batch, i prodotti semilavorati possono essere trasferiti solo in modo logico usando il giornale di registrazione distinte di prelievo dalla pagina elenco **Conto lavoro**. Il giornale di registrazione crea un documento bolla di consegna che può essere utilizzato per trasferire le materie prime e semilavorate al fornitore.
-   Per le operazioni in conto lavoro in un flusso di produzione, il trasferimento di prodotti semilavorati è documentato dal ricevimento di kanban di produzione o di prelievo all'ubicazione del fornitore. Per modellare un'attività di trasferimento esplicita, è possibile terminare un kanban di produzione con un'attività di trasferimento aggiuntiva.

**Nota:** Un ciclo di lavorazione di produzione per un singolo ordine di produzione non può attraversare più siti. Questa regola vale anche per il lavoro in conto lavoro. Di conseguenza, i magazzini che rappresentano ubicazioni gestite dal fornitore devono essere definiti nello stesso sito delle risorse interne utilizzate nel ciclo di lavorazione. Sebbene i flussi di produzione possano attraversare i siti, non possono trasportare i prodotti semilavorati da un sito a un altro, poiché tale operazione implica una modifica del contesto di costo.  

In genere, il magazzino di uscita e l'ubicazione di un gruppo di risorse in conto lavoro vengono assegnati direttamente al magazzino e l'ubicazione del passaggio successivo dell'operazione nel ciclo di lavorazione o nel flusso di produzione. Questa impostazione consente di ridurre la quantità di segnalazione processi o il numero di operazioni di trasferimento aggiuntive da modellare.



