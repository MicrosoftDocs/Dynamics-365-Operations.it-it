---
title: Distinte base e formule
description: Questo articolo offre informazioni sulle distinte base (DBA) e sulle formule, che sono una parte centrale della definizione dei prodotti e varianti prodotto.
author: cvocph
manager: tfehr
ms.date: 11/03/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BOMConsistOf, BOMDesigner, BOMTable, EcoResProductProcessManufacturingWorkspace, ProdBOM, ProdJournalTransBOM, ProdBOMCurrent, PmfBOMDesignerEditCoBy, ProdJournalPickingListLineSummary, ProdBOMOverview, PmfCoReqPlanning, EcoResProductProdTypeFormulaNoActiveFormulaFormPart, EcoResItemsMissingActiveRouteVersionFormPart, EcoResItemsProdTypeBOMExpiringBOMFormPart, BOMDesignerBOMVersion, BOMExpandPurch, BOMChangeLine, BOMExpandSales, EcoResItemsProdTypeBOMExpiringRouteFormPart, EngChgEcmBomDesigner, EngChgEcmProductBOMItemIdLookup, EngChgEcmProductBOMConsistOf, EngChgEcmBOMCopyDialog, EngChgEcmBomDesignerEditBom, BOMDesignerFilterDialog, BOMDesignerFilterDialog, BOMPartOf, BOMSetupReportFinish, EcoResItemsMissingActiveBOMVersionFormPart, BOMIdLookup, EcoResProductProdTypeFormulaNoActiveRouteFormPart, BOMExpandPurchRFQ, EngChgCaseRouteTablePart
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 19331
ms.assetid: c19b437a-2de2-4728-9477-2bcb0c2b1f5e
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d0a02bc506057a02e822733077c45286f3e23db2
ms.sourcegitcommit: 97d4a9bd442fe20f90605d8154c3a947c7645b37
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/28/2020
ms.locfileid: "3895331"
---
# <a name="bills-of-materials-and-formulas"></a>Distinte base e formule

[!include [banner](../includes/banner.md)]

Questo articolo offre informazioni sulle distinte base (DBA) e sulle formule, che sono una parte centrale della definizione dei prodotti e varianti prodotto. Le distinte base e le formule specificano i materiali o gli ingredienti necessari per un prodotto specifico. Le formule inoltre specificano i co-prodotti e sottoprodotti ricevuti nel contesto di produzione specifico. 

<a name="bills-of-materials"></a>Distinte base
------------------

Una distinta base (DBA) definisce i componenti necessari per produrre un prodotto. I componenti possono essere materie prime, prodotti semilavorati, o ingredienti. In alcuni casi in una DBA può essere fatto riferimento ai servizi. Tuttavia, nelle DBA vengono in genere descritte le *risorse materiali* necessarie.  

Quando viene associata a un ciclo di lavorazione o a un flusso di produzione che descrive le operazioni e le risorse necessarie per sviluppare un prodotto, la DBA forma la base per calcolare il costo stimato del prodotto.  

Una DBA è una singola entità descritta dalle seguenti informazioni:

-   ID DBA
-   Nome DBA
-   Le righe DBA che descrivono i componenti e gli ingredienti
-   Le versioni DBA che definiscono il prodotto e il periodo di validità della DBA

Una singola DBA descrive un singolo livello che viene identificato da un ID univoco. I componenti potrebbero avere le proprie DBA cui fanno riferimento le versioni DBA. È possibile visualizzare e modificare la gerarchia completa di DBA per un prodotto specifico nel designer DBA.

### <a name="formulas-co-products-and-by-products"></a>Formule, co-prodotti e sottoprodotti

Una formula è un sottotipo di DBA che viene in genere utilizzato per la produzione del processo. Oltre ai componenti e agli ingredienti, una formula descrive i co-prodotti e i sottoprodotti. Nella versione corrente, la definizione dei co-prodotti e sottoprodotti per la formula richiede la versione della formula. Una formula viene definita in genere per un prodotto finito specifico (un articolo formula o di pianificazione) definito nella versione della formula.

### <a name="boms-in-the-product-lifecycle"></a>DBA nel ciclo di vita del prodotto

Nel ciclo di vita del prodotto numerosi tipi di DBA potrebbero essere creati per diversi motivi:

-   **Schizzo/bozza DBA** - Questa DBA fornisce una stima bozza dei materiali richiesti in fase di pianificazione anticipata e consente di creare una stima approssimativa del costo e degli attributi del prodotto stimati. Questa DBA non viene in genere utilizzata nella pianificazione delle risorse aziendali (ERP).
-   **DBA progettazione** - Questa DBA viene in genere utilizzata per progettare i prodotti basati sui portafogli di prodotti esistenti. Le DBA di progettazione vengono strutturate per semplificare il processo di progettazione e per raggruppare i prodotti complessi in moduli di progettazione. Per i prodotti semplici, potrebbe essere possibile progettare DBA per il processo di produzione effettivo. Tuttavia, per altri prodotti, la DBA di progettazione deve essere convertita in una DBA di produzione effettiva. Le DBA di progettazione vengono in genere rappresentate da voci fittizie nella gerarchia DBA. Sebbene le DBA di progettazione possano essere utilizzate per la pianificazione e l'esecuzione di operazioni produttive, questo approccio può condurre a inefficienze, in particolare a operazioni ripetitive nelle quali si assiste alla creazione di più ordini.
-   **DBA di pianificazione** - Questa DBA viene utilizzata per effettuare la pianificazione dei fabbisogni di materiali. La richiesta di componenti e di ingredienti viene calcolata in base alla richiesta di prodotti finiti. Analogamente alle DBA di determinazione costi, le DBA di pianificazione potrebbero rappresentare una combinazione specifica di materiale utilizzato in un periodo.
-   **DBA di produzione** – Questa è la DBA effettiva utilizzata per una produzione specifica. Una DBA di produzione deve considerare le risorse effettive utilizzate per produrre il prodotto. Quando un ordine di produzione, un ordine batch o un kanban viene creato, i livelli multipli di DBA che sono rappresentati da voci fittizie sono compressi in un unico livello e vengono distribuiti sulle operazioni dell'ordine.
-   **DBA di determinazione costi** – Questa DBA consente di calcolare il costo stimato di un prodotto. Ad esempio, è possibile utilizzare una DBA di determinazione costi quando viene utilizzato il costo standard o viene calcolato il costo pianificato stimato di un prodotto specificato. La determinazione costi DBA può fare riferimento a una specifica combinazione di materiali e di risorse che si prevede di utilizzare. Di conseguenza, è possibile utilizzare la DBA di determinazione costi per creare un costo stimato rappresentativo per un periodo e contribuire a evitare gli scostamenti nel tempo.

I tipi di DBA che vengono effettivamente utilizzati in un'implementazione dipendono dall'implementazione e anche dagli scenari e dai requisiti aziendali. Nelle implementazioni semplici una DBA pianificante, una DBA di produzione e una DBA di determinazione costi possono essere modellate come DBA unica. Negli ambienti con frequenti modifiche di progetto e più cicli alternativi verrà probabilmente richiesto un maggiore set di tipi di DBA.

### <a name="approval-of-boms-and-formulas"></a>Approvazione delle DBA e delle formule

Ogni DBA e formula può essere approvata separatamente o non approvata. In genere, l'approvazione di una DBA o formula si verifica quando la prima versione rilevante della DBA è approvata. Tuttavia, in alcuni scenari aziendali, le approvazioni potrebbero costituire diversi passaggi del processo e potrebbero coinvolgere più proprietari.  

Si noti che, se una DBA non è approvata, anche tutte le versioni DBA correlate non sono approvate.

## <a name="bom-and-formula-versions"></a>Versioni DBA e formula
Per dichiarare una DBA o una formula specifica in una variante prodotto che può essere prodotta, è necessario creare una versione formula o DBA. La validità delle versioni DBA e delle versioni formula può essere vincolata dal periodo, dalla quantità, dal sito, dalle dimensioni specifiche del prodotto e da altri criteri. Le versioni formula hanno altri importanti attributi, ad esempio rendimento, definizioni di co-prodotto e sottoprodotto e le istruzioni di scomposizione dei costi per la formula.

### <a name="approval-of-bom-and-formula-versions"></a>Approvazione della versioni DBA e formula

Prima che una versione DBA possa essere utilizzata nella pianificazione o nel processo di produzione, deve essere approvata. Quando una versione DBA viene approvata, la DBA correlata può essere approvata, a seconda dei diritti di selezione e di autenticazione dell'utente. Si noti che una versione DBA può essere approvata solo se la DBA correlata stessa è stata approvata.

### <a name="activation-of-the-default-bom-or-formula-version"></a>Attivazione della versione DBA o formula predefinita

Per impostare una DBA o una formula specifica nella versione DBA o formula predefinita che verrà utilizzata dalla pianificazione generale o che verrà usata per creare gli ordini di produzione, è necessario attivare la versione. Quando una versione è attivata, la unicità della versione per i vincoli dati, ad esempio periodo, il sito, o quantità, viene verificata. Viene visualizzato un messaggio di errore se la versione che si sta tentando di attivare è in conflitto con una versione già attiva. È quindi necessario disattivare la versione in conflitto o modificare i vincoli della versione (in genere il periodo) per impedire un'attivazione ambigua.

### <a name="product-change-with-case-management"></a>Modifica dei prodotti con gestione dei casi

Il caso di modifica del prodotto per l'approvazione e l'attivazione di nuovi DBA e versioni DBA fornisce un modo semplice di visualizzare una panoramica dei vincoli della versione DBA. È inoltre possibile approvare e attivare tutte le DBA e le formule correlate alla modifica specifica di una data di attivazione.

### <a name="alternative-bom-versions"></a>Versioni DBA alternative

Talvolta, la versione DBA o formula attiva non deve essere utilizzata nelle previsioni, nelle vendite o in un prodotto padre. In questo caso, è possibile selezionare una DBA approvata specifica come parte del fabbisogno (riga di previsione, riga di vendita o riga DBA) se una versione DBA o formula approvata è presente per la DBA o la formula alternativa.  

Quando gli ordini pianificati, gli ordini di produzione o i kanban vengono creati, il responsabile della pianificazione o il supervisore del shop floor possono utilizzare qualsiasi versione DBA approvata che sia valida alla data di produzione pianificata richiesta per pianificare o produrre un prodotto specifico. La versione DBA utilizzata non deve essere attivata nella versione DBA predefinita.

## <a name="bom-and-formula-lines"></a>Righe DBA e formula
Una riga DBA viene creata per ogni materiale, servizio o ingrediente. La riga definisce il consumo pianificato della variante di prodotto specificata e definisce anche i vari attributi relativi al consumo pianificato.  

Le righe DBA possono avere i seguenti tipi di riga: **Articolo**, **Fittizio**, **Fornitura sottoposta a pegging**, **Fornitore**.

### <a name="item"></a>Articolo

Selezionare il tipo di riga **Articolo** per i materiali o i servizi che vengono direttamente utilizzati e che non richiedono ulteriore esplosione o fornitura sottoposta a pegging.

### <a name="phantom"></a>Fittizio

Selezionare il tipo di riga **Fittizio** quando si desidera esplodere qualsiasi articolo DBA di livello inferiore contenuto nella riga DBA. Nella programmazione generale, nel calcolo dei costi pianificati o nella valutazione di un ordine di produzione che utilizza le righe DBA di tipo **Fittizio**, la riga DBA padre che fa riferimento a una variante prodotto con una distinta base fittizia viene sostituita dagli articoli componenti elencati nelle righe DBA di tale DBA, come determinato dalla versione DBA attiva applicabile di tale variante prodotto. Se la variante prodotto ha un ciclo di lavorazione attivo applicabile, i funzionamenti del ciclo di lavorazione sono fusi nel ciclo di lavorazione padre.  

Le DBA fittizie in genere vengono utilizzate per semplificare il processo di progettazione. L'utilizzo esteso delle DBA fittizie in più livelli produce un effetto sulle prestazioni, in particolare negli scenari altamente ripetitivi di produzione. Per migliorare le prestazioni, è consigliabile evitare le gerarchie di DBA fittizie. Invece, utilizzare DBA di produzione pre-esplose e cicli di lavorazione.

### <a name="pegged-supply"></a>Fornitura sottoposta a pegging

Selezionare il tipo di riga**Fornitura sottoposta a pegging** quando si desidera creare una produzione secondaria, un kanban evento riga DBA o un ordine fornitore diretto per qualsiasi variante prodotto cui fa riferimento la riga DBA. La produzione secondaria, il kanban evento o l'ordine fornitore viene creato quando si stima l'ordine di produzione. Le quantità di articoli richiesti vengono automaticamente prenotate per l'ordine di produzione in uso.

### <a name="vendor"></a>Fornitore

Selezionare il tipo di riga **Fornitore** se per il processo di produzione viene utilizzato un terzista e si desidera creare automaticamente una produzione secondaria o un ordine fornitore per il terzista.  

**Nota sulle operazioni in conto lavoro in una DBA:** Il servizio o il lavoro realizzato dal terzista deve essere creato come articolo di tipo Assistenza di cui viene tenuta traccia nell'inventario. È necessario collegare un articolo di tipo Assistenza all'articolo principale come riga DBA. Nel ciclo di lavorazione deve essere presente un'operazione assegnata alla risorsa operativa del terzista.



