---
title: Determinazione costi di tipo backflush
description: In questo argomento viene presentato il concetto di determinazione costi di tipo backflush utilizzato per la produzione snella o lean manufacturing.
author: cvocph
manager: AnnBe
ms.date: 04/10/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LeanCosting, LeanCostingTimeBucket
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 272063
ms.assetid: 62a2a7da-ff79-49bf-a6e8-29460ba5252f
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: conradv
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: 484bac74ccb498f0b006458f5e6d8fb0e9461a8f
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "1556071"
---
# <a name="backflush-costing"></a>Determinazione costi di tipo backflush

[!include [banner](../includes/banner.md)]

In questo argomento viene presentato il concetto di determinazione costi di tipo backflush utilizzato per la produzione snella o lean manufacturing. 

La determinazione costi per la produzione lean manufacturing consente al flusso di produzione di utilizzare il metodo di accumulo dei costi noto come determinazione costi di tipo backflush. Nel metodo di determinazione costi di tipo backflush, i materiali diretti consumati vengono accumulati nel conto costi (WIP) semilavorati del flusso di produzione. Viene utilizzato un gruppo di modelli inventariali per costi standard. I prodotti ricevuti dal flusso di produzione vengono detratti dal WIP al costo standard. La differenza principale tra la determinazione costi di tipo backflush e il costo standard consiste nel fatto che per la determinazione costi di tipo backflush, gli scostamenti non vengono calcolati per kanban o prodotto finito. Gli scostamenti vengono invece calcolati per flusso di produzione in un determinato periodo. Questo metodo introduce un concetto di produzione snella effettiva per i report di consumo materiali. Le quantità prelevate dedicate di materiale non vengono dichiarate in un kanban o un ordine di produzione. In questo caso, i batch o le unità movimentazione completi vengono approntati nel flusso di produzione. Dopo che i batch o le unità movimentazione sono stati registrati come vuoti, vengono dichiarati come consumati. È possibile utilizzare il consumo avanzato, in base alla [configurazione del flusso di produzione](../production-control/lean-manufacturing-modeling-lean-organization.md). Prima di poter utilizzare il consumo avanzato, le organizzazioni devono consentire l'eliminazione del materiale nel WIP del flusso di produzione. La determinazione costi di tipo backflush periodica determina il valore WIP effettivo fino alla fine del periodo. Questa determinazione si basa sulle unità movimentazione kanban e sullo stato del processo kanban. Gli scostamenti da tra i valori effettivi e i valori effettivi WIP per gruppo di costi e articoli vengono contabilizzati e mostrati come scostamenti.

## <a name="configuring-backflush-costing"></a>Configurazione della determinazione costi di tipo backflush
Per attivare la determinazione costi, è necessario completare la seguente impostazione:

-   **Impostazione dei conti WIP per il gruppo e il flusso di produzione.** I conti WIP per il flusso di produzione sono specificati nel gruppo di produzione. Il flusso di produzione di determinazione costi di tipo backflush calcola gli scostamenti come differenza nel valore WIP prima e dopo l'esecuzione della determinazione costi di tipo backflush per ogni flusso di produzione. Pertanto, si consiglia di creare un conto WIP per ogni flusso di produzione.
-   **Assegnare una categoria di costi al gruppo di risorse.** È necessario assegnare una categoria di costi alla categoria del tempo di esecuzione della cella di lavoro. Per determinare gli scostamenti per attività, è necessario creare una categoria di costi per ogni cella di lavoro. Le categorie di costi per l'impostazione e la quantità non sono considerate nella determinazione costi per la produzione snella. I conti WIP per gruppo di risorse vengono ignorati nella determinazione dei costi di tipo backflush. Per le attività in conto lavoro, non è necessaria alcune categoria di costi. Il gruppo di costi assegnato al servizio attivo viene utilizzato in alternativa.
-   **Assegnare i gruppi di costi.** Per consentire la segmentazione del contributo costi di un flusso di produzione, è necessario assegnare i gruppi di costi per tipo di gruppo di costi:
    -   **Gruppo costi per materiale diretto** - Il materiale diretto richiede un gruppo costi che identifica la categoria materiale per la determinazione costi. Il gruppo di costi consente una visualizzazione aggregata di costi, WIP e scostamenti per materiale diretto.
    -   **Gruppo costi di fabbricazione diretta** - Il gruppo costi di fabbricazione diretta consente di registrare il contributo dei costi diretti delle risorse operative nel flusso di produzione. Il gruppo di costi consente una visualizzazione aggregata di costi, WIP e scostamenti per costo di fabbricazione diretta.
    -   **Gruppo costi indiretti** - Il gruppo costi indiretti è necessario per calcolare il contributo dei costi indiretti nel flusso di produzione. Il gruppo di costi consente una visualizzazione aggregata di costi, WIP e scostamenti per costo indiretto.
    -   **Gruppo costi di esternalizzazione diretta** - Il gruppo costi per i servizi consente una visualizzazione aggregata di costo assegnato e WIP e determina gli scostamenti dei costi dei servizi in conto lavoro.
    -   **Gruppo costi per prodotto finito** - I prodotti finiti richiedono un gruppo costi che identifica la categoria di prodotti per la determinazione costi. Il gruppo di costi consente una visualizzazione aggregata di costi, WIP e scostamenti per categoria di prodotti. Il costo standard per i prodotti viene calcolato utilizzando il calcolo dei costi basato sulle distinte base (BOM) e il flusso di produzione e regole kanban oppure il ciclo di lavorazione.

### <a name="costing-sheet"></a>Scheda di determinazione costi

La scheda di determinazione costi effettua la modellizzazione della struttura dei costi per la società e viene creata dai gruppi di costi per classificare il costo. La scheda di determinazione costi include diverse aree. Consente di visualizzare le informazioni in base alla struttura che è stata progettata al suo interno. Nella scheda di determinazione costi, si definisce anche la formula utilizzata per calcolare i costi indiretti. La formula di calcolo può essere basata su quantità, peso, volume o valore.

-   **Definire una versione di determinazione costi.** Nella versione di determinazione costi, la società definisce come deve essere gestito il costo. In una versione di determinazione costi può essere contenuto un insieme di record dei costi standard o un insieme di record dei costi pianificati in base al tipo di determinazione costi assegnato alla versione di determinazione costi. La versione di determinazione costi utilizzata per determinare per la produzione snella o lean manufacturing deve essere basata sui costi standard.
-   **Assegnare un gruppo di modelli inventariali per i prodotti rilasciati.** Tutti i prodotti correlati al flusso di produzione devono essere assegnati a un gruppo di modelli inventariali che utilizza il gruppo di modelli inventariali **Costo standard**. Il costo standard viene gestito per sito e data di attivazione. Per le rappresentazioni generali prodotto, il gruppo di modelli inventariali può essere selezionato se il costo viene gestito per ogni variante o rappresentazione generale prodotto.
-   **Per definizione, servizi in conto lavoro sono i servizi non inventariati.** Le attività in conto lavoro non hanno gruppo di modelli inventariali. Per stabilire correttamente il costo di un'attività in conto lavoro, è necessario assicurarsi che l'attività di servizio appartenga a un gruppo di modelli inventariali in cui i criteri di magazzino sono **Prodotto stoccato = False**.

Per i prodotti risultanti, il calcolo dei costi basato sul flusso di produzione richiede che un costo standard venga gestito per i servizi correlati alle attività in conto lavoro. Il gruppo di costi assegnato ai servizi viene utilizzato per determinare gli scostamenti dei costi dell'attività in conto lavoro.

## <a name="cost-calculation-for-lean-manufacturing"></a>Calcolo dei costi per la produzione snella o lean manufacturing
Per i prodotti forniti al di fuori da un flusso di produzione, il calcolo DBA deve basarsi su una versione del ciclo di lavorazione o di un flusso di produzione. Il calcolo DBA consente di calcolare il costo di un prodotto e la suddivisione relativa alle risorse e al materiale richiesti per costruire il prodotto. La detrazione dal WIP per il flusso di produzione viene effettuata utilizzando la suddivisione di un prodotto per gruppo di costi e articolo.

### <a name="calculation-that-is-based-on-the-production-flow"></a>Calcolo basato sul flusso di lavoro.

Il Lean manufacturing per Microsoft Dynamics 365 for Finance and Operations è indipendente dai cicli di lavorazione. Il calcolo dei costi per i prodotti forniti da un flusso di produzione può essere basato sul flusso di produzione stesso. Prima che il calcolo possa essere effettuato, è necessario creare una regola kanban che fornisce il prodotto dal flusso di produzione. Se un prodotto può essere fornito da più flussi di produzione allo stesso sito alla data di calcolo, è possibile selezionare il flusso di produzione per il calcolo DBA. Nella pagina **Flusso di produzione predefinito**, è possibile configurare un flusso di produzione predefinito per ciascun articolo. Se esistono più regole kanban per lo stesso prodotto nello stesso flusso di produzione attivo nella data di calcolo, il calcolo seleziona la prima regola kanban attiva per il calcolo.

### <a name="calculation-that-is-based-on-the-route"></a>Calcolo basato sul ciclo di lavorazione

Il calcolo in base a un ciclo di lavorazione è valido come calcolo basato su un flusso di produzione. Tuttavia, il calcolo in base a un ciclo di prelievo non utilizza la determinazione costi per il funzionamento della lean manufacturing. Il ciclo di lavorazione deve utilizzare i requisiti risorsa del gruppo di risorse. Per evitare gli scostamenti sistematici, deve inoltre utilizzare le stesse celle di lavoro, o almeno le stesse categorie di costi. Anche in questo caso, è opportuno evitare le categorie di costi per l'impostazione e la quantità. Queste non consentono di calcolare il costo in una scomposizione più granulare rispetto al backflush di costo di lean manufacturing. Per determinare l'opzione (flusso di produzione o ciclo di lavorazione) da utilizzare per calcolare il costo, esaminare i risultati della scomposizione dei costi. La versione disponibile più vicina alla realtà e che produce inferiore scostamenti complessivi rappresenta la migliore opzione. In un ambiente di lean manufacturing in cui un prodotto viene specificato in base a un singolo flusso di produzione e una singola regola kanban, il calcolo basato sul flusso di produzione probabilmente è più accurato. Per un prodotto che può essere fornito da lean manufacturing e ordini di produzione nello stesso sito o che può avere più flussi di produzione o più regole kanban nello stesso flusso, il calcolo potrebbe risultare più accurato se basato su una versione del ciclo di lavorazione generata in modo specifico per il calcolo dei costi, non per la produzione. Il calcolo del flusso di produzione deve essere utilizzato per calcolare i prodotti che includono il conto lavoro. In Microsoft Dynamics 365 for Finance and Operations, i modelli dei costi per il conto lavoro tramite gli ordini di produzione e il conto lavoro in lean manufacturing utilizzano due diversi metodi. In lean manufacturing è stata introdotto un nuovo tipo di gruppo di costi **Esternalizzazione diretta**, per calcolare i servizi in conto lavoro.

## <a name="material-consumption"></a>Consumo materiali
Quando il materiale viene consumato dal magazzino al WIP, il costo dei materiali viene aggiunto al calcolo WIP al costo standard effettivo per un gruppo di costi. Questa operazione viene eseguita nelle seguenti condizioni:

-   I problemi kanban vengono registrati per le righe di prelievo kanban che aggiornano l'inventario.
-   I processi di trasferimento completati che comportano l'aggiornamento dell'inventario nel prelievo ma non nella ricezione (trasferimento di materiale dalle scorte al WIP).

## <a name="receiving-products-from-the-production-flow"></a>Ricezione di prodotti dal flusso di produzione
I prodotti vengono ricevuti dal flusso di produzione nei seguenti casi:

-   I processi di lavorazione completati con **aggiornamento alla ricezione** impostato **Sì**.
-   I processi completati che comportano l'aggiornamento delle scorte alla ricezione, ma che hanno **aggiornamento al prelievo** impostato su **No** (trasferimento dal WIP alle scorte). Questa opzione consente di ricevere tutti i prodotti di un flusso di produzione indipendentemente dalla configurazione di DBA e ciclo di lavorazione. Il processo segue solo i flussi fisici. Questa opzione è particolarmente adattata per ricevere i sottoprodotti, i co-prodotti o scarto da un flusso di produzione e per correggere il saldo del flusso di produzione WIP di conseguenza.

I prodotti ricevuti dal flusso di produzione vengono detratti dal WIP.

## <a name="products-in-wip"></a>Prodotti nel WIP
Il modello WIP di lean manufacturing in Microsoft Dynamics 365 for Finance and Operations consente di utilizzare lo stato dell'unità movimentazione kanban per gestire il materiale, i prodotti semilavorati e i prodotti finiti che fanno parte del WIP.

-   **Assegnato** - Il kanban può avere consumato il materiale registrato nel WIP.
-   **Ricevuto** - Se il kanban fa riferimento all'ultima attività in cui l'**aggiornamento alla ricezione** è impostato su **No**, rappresenta un'unità movimentazione completa di un prodotto o di un prodotto semilavorato non registrato nell'inventario.

Si noti che il materiale nel valore WIP non è visibile nella panoramica delle scorte disponibili. Tuttavia, è visibile nella panoramica quantità kanban.

## <a name="consuming-products-in-wip"></a>Prodotti di consumo in WIP
I prodotti nel WIP vengono consumati quando le unità movimentazione kanban vengono svuotate. Un segnale di vuoto kanban non genera una transazione attiva di determinazione costi ma avrà effetto quando la seguente determinazione costi di tipo backflush viene eseguita. Le unità movimentazione svuotate kanban non sono state contabilizzate come disponibili e quindi vengono calcolate come consumate durante il periodo.

### <a name="automatic-empty-registration"></a>Registrazione si svuotamento automatica

Kanban evento o kanban programmati possono essere impostati per la registrazione automatica dello svuotamento nella regola kanban:

-   **Quando le unità movimentazione vengono ricevute** - Per impostazione predefinita, per i kanban programmati, il materiale viene dichiarato come consumato quando l'ultimo processo kanban viene completato. Per i kanban a quantità fissa, questa opzione è consigliata solo per i kanban a singolo contenitore, perché restituisce la scheda all'origine della domanda ogni volta che un kanban viene inviato alla destinazione finale.
-   **Quando il fabbisogno viene registrato** - Questa opzione è disponibile solo per i kanban evento ed è l'opzione predefinita la merce. Nella connessione al WIP, questa opzione è utile per mantenere il WIP integro, poiché i kanban per i componenti nel WIP vengono svuotati automaticamente e quindi consumati dal WIP, quando il kanban padre viene preparato.

In fine, le unità movimentazione kanban possono essere assegnate (= in lavorazione), essere ricevute (= piene) oppure svuotate. No esiste svuotamento parziale. Di conseguenza, per consentire la registrazione accurata del consumo, è importante che si limitino le quantità di prodotto kanban in modo che siano inferiori al consumo per periodo. I prodotti spostati nello shop floor in grandi batch che coprono giorni o settimane di domanda non devono essere consumati nel conto WIP. In questo caso, i prodotti devono essere gestiti nell'inventario.

## <a name="backflush-costing"></a>Determinazione costi di tipo backflush
È opportuno eseguire la determinazione costi di tipo backflush per stimare il WIP e per produrre periodicamente lo stato di fine periodo che calcola gli scostamenti di materiale, manodopera e costi indiretti. Gli scostamenti calcolati verranno registrati nei conti di scostamento. Durante il processo di determinazione costi di tipo backflush della persona giuridica, tutti i flussi di produzione vengono utilizzati nella stessa esecuzione batch. Quando la determinazione costi di tipo backflush viene eseguita in un batch, l'elaborazione potrebbe essere effettuata a thread multipli dal flusso di produzione. Il periodo del backflush viene definito da una data di fine. Non è possibile registrare nuove transazioni per una data se è stato eseguito il calcolo di determinazione costi di tipo backflush. Non si deve mai eseguire la determinazione costi di tipo backflush per la data corrente prima che il giorno sia effettivamente trascorso. La procedura di determinazione costi di tipo backflush è costituita dai passaggi indicati di seguito.

1.  Determinare le quantità inventariali inutilizzate il flusso di produzione a partire dalla data di fine del periodo. Dopo che la determinazione costi di tipo backflush è stata eseguita, è possibile visualizzare le quantità inventariali non utilizzate alla data della determinazione costi effettuata nella finestra di dialogo **Quantità inventariali non utilizzate**.
2.  Calcolare l'utilizzo realizzato netto del flusso di produzione per il periodo.
3.  Annullare il WIP del consumo risorse realizzato e dei i prodotti.
4.  Calcolare gli scostamenti di produzione a costo standard per il periodo. **Per i componenti consumati per il periodo:**
    -   Aggiornare finanziariamente le quantità realizzate nette di materiali che il flusso di produzione ha consumato durante il periodo. Il sistema elabora l'ordine First In, First Out (FIFO) per le singole transazioni di magazzino per aggiornare finanziariamente le transazioni aggiornate fisicamente per il flusso di produzione, fino al raggiungimento delle quantità realizzate nette per il periodo.
    -   Le transazioni sono suddivise finanziariamente per mappare le quantità consumate esatte.
    -   Le quantità inventariali non utilizzate nel WIP del flusso di produzione rimangono nello stato aggiornato fisicamente.

    **Per le quantità completate di produzione del periodo:**
    -   Aggiornare finanziariamente le transazioni di magazzino per le quantità completate per il periodo.

    **Per il costo di conversione:**
    -   Le transazioni di costo di conversione applicate (transazioni cicli di lavorazione) registrate per il periodo vengono aggiornate finanziariamente.
    -   Il costo di fabbricazione diretto viene aggiornato finanziariamente. Tutti i processi kanban completati durante un periodo vengono accumulati.
    -   Tutti i costi indiretti calcolati per il materiale consumato durante il periodo vengono calcolati e sottratti dal WIP. I costi indiretti rimanenti vengono registrati come scostamento.

5.  Calcolare gli scostamenti di produzione a costo standard. Lo scostamento viene calcolato per gruppo di costi.





