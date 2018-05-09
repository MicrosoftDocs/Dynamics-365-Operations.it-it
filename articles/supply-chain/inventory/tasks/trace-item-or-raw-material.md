---
title: Tracciare un articolo o la materia prima
description: "Questa procedura dimostra come utilizzare la tracciabilità articolo per identificare gli articoli o le materie prime che sono stati utilizzati o vengono utilizzati."
author: pjacobse
manager: AnnBe
ms.date: 06/21/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: pjacobse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 86868fc3a5d1543e46b3ebd4dcc31cbc3a78479b
ms.contentlocale: it-it
ms.lasthandoff: 05/08/2018

---
# <a name="trace-an-item-or-raw-material"></a><span data-ttu-id="bd86d-103">Tracciare un articolo o la materia prima</span><span class="sxs-lookup"><span data-stu-id="bd86d-103">Trace an item or raw material</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="bd86d-104">Questa procedura dimostra come utilizzare la tracciabilità articolo per identificare gli articoli o le materie prime che sono stati utilizzati o vengono utilizzati.</span><span class="sxs-lookup"><span data-stu-id="bd86d-104">This procedure demonstrates how to use item tracing to identify where items or raw materials have been used or are being used.</span></span> <span data-ttu-id="bd86d-105">Con questa procedura è possibile identificare un articolo, risalire all'origine, quindi tracciarlo in avanti attraverso la produzione e la vendita del prodotto finito.</span><span class="sxs-lookup"><span data-stu-id="bd86d-105">With this procedure, you can identify an item, trace it back to the source, and then trace forward through the production and sale of the finished product.</span></span> <span data-ttu-id="bd86d-106">Il processo può essere utilizzato per esaminare i clienti interessati, gli ordini clienti interessati e altro.</span><span class="sxs-lookup"><span data-stu-id="bd86d-106">The process can be used to investigate the customers impacted, the sales orders affected, and more.</span></span> <span data-ttu-id="bd86d-107">Questa procedura utilizza la società di dati dimostrativi USP2.</span><span class="sxs-lookup"><span data-stu-id="bd86d-107">This procedure uses demo data company USP2.</span></span>


## <a name="trace-an-item-backwards-using-a-known-batch-number"></a><span data-ttu-id="bd86d-108">Tracciare un articolo a ritroso utilizzando un numero batch noto</span><span class="sxs-lookup"><span data-stu-id="bd86d-108">Trace an item backwards using a known batch number</span></span>
1. <span data-ttu-id="bd86d-109">Andare a Gestione inventario > Richieste di informazioni e report > Dimensioni di tracciabilità > Tracciabilità articolo.</span><span class="sxs-lookup"><span data-stu-id="bd86d-109">Go to Inventory management > Inquiries and reports > Tracking dimensions > Item tracing.</span></span>
2. <span data-ttu-id="bd86d-110">Nel campo Numero articolo selezionare P9100.</span><span class="sxs-lookup"><span data-stu-id="bd86d-110">In the Item number field, select P9100.</span></span>
3. <span data-ttu-id="bd86d-111">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="bd86d-111">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="bd86d-112">Nel campo Avanti o indietro, selezionare 'Indietro'.</span><span class="sxs-lookup"><span data-stu-id="bd86d-112">In the Forward or backward field, select 'Backward'.</span></span>
5. <span data-ttu-id="bd86d-113">Nel campo Numero batch selezionare as-12-344-01.</span><span class="sxs-lookup"><span data-stu-id="bd86d-113">In the Batch number field, select as-12-344-01.</span></span>
6. <span data-ttu-id="bd86d-114">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="bd86d-114">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="bd86d-115">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="bd86d-115">Click OK.</span></span>

## <a name="identify-an-item-trace-it-forward-and-make-an-analysis"></a><span data-ttu-id="bd86d-116">Identificare un articolo, tracciarlo in avanti e fare un'analisi</span><span class="sxs-lookup"><span data-stu-id="bd86d-116">Identify an item, trace it forward, and make an analysis</span></span>
    * <span data-ttu-id="bd86d-117">Il nodo principale della struttura rappresenta la quantità disponibile dell'articolo e del batch selezionati.</span><span class="sxs-lookup"><span data-stu-id="bd86d-117">The top node of the tree represents the on hand quantity of the selected item and batch.</span></span> <span data-ttu-id="bd86d-118">È necessario espandere i nodi della struttura per trovare l'articolo su cui deve essere eseguita la tracciabilità in avanti.</span><span class="sxs-lookup"><span data-stu-id="bd86d-118">You need to expand the nodes of the tree to find the item that the forward trace should be executed on.</span></span>   
1. <span data-ttu-id="bd86d-119">Nella struttura espandere "i nodi descritti sotto, quindi selezionare l'ultimo nodo".</span><span class="sxs-lookup"><span data-stu-id="bd86d-119">In the tree, expand 'the nodes described below, and then select the last node'.</span></span>
    * <span data-ttu-id="bd86d-120">Espandere: "P9100 / 1 / 10 / as-12-344-01 ● 2 keg ● 7,00 gal \P9100 ● Prelevato ● Ordine cliente 000072 ● 12/22/2015 ● -1 keg ● -4,00 gal ● Sito=1, Magazzino=10, Numero batch=as-12-344-01 \P9100 ● Produzione B-000050 ● 12/9/2015● 7 keg ● 27,00 gal ● Sito=1, Magazzino=10, Numero batch=as-12-344-01 ● Co-prodotti: P9101", quindi selezionare quel nodo.</span><span class="sxs-lookup"><span data-stu-id="bd86d-120">Expand: 'P9100 / 1 / 10 / as-12-344-01 ● 2 keg ● 7.00 gal  \P9100 ● Picked ● Sales order 000072 ● 12/22/2015  ● -1 keg ● -4.00 gal ● Site=1, Warehouse=10, Batch number=as-12-344-01  \P9100 ● Production B-000050 ● 12/9/2015● 7 keg ● 27.00 gal ● Site=1,Warehouse=10,Batch number=as-12-344-01 ● Co-products: P9101' and then select that node.</span></span>     
2. <span data-ttu-id="bd86d-121">Nella struttura espandere "il nodo descritto sotto, quindi selezionare quel nodo".</span><span class="sxs-lookup"><span data-stu-id="bd86d-121">In the tree, expand 'the node described below and then select that node'.</span></span>
    * <span data-ttu-id="bd86d-122">A partire dal nodo appena selezionato, espandere "M9103 ● Riga produzione B-000050 ● 12/9/2015 ● -160,00 lb ● Dimensione=70, Colore=OK, Sito=1, Magazzino=10, Numero batch=App01", quindi selezionare quel nodo.</span><span class="sxs-lookup"><span data-stu-id="bd86d-122">Starting from the node that you’ve just selected,  expand 'M9103 ● Production line B-000050 ● 12/9/2015  ● -160.00 lb ● Size=70, Color=OK, Site=1, Warehouse=10, Batch number=App01' and then select that node.</span></span>  
3. <span data-ttu-id="bd86d-123">Fare clic su Traccia da nodo.</span><span class="sxs-lookup"><span data-stu-id="bd86d-123">Click Trace from node.</span></span>
4. <span data-ttu-id="bd86d-124">Fare clic su Avanti.</span><span class="sxs-lookup"><span data-stu-id="bd86d-124">Click Forward.</span></span>
5. <span data-ttu-id="bd86d-125">Nel riquadro azioni fare clic su Tracciatura.</span><span class="sxs-lookup"><span data-stu-id="bd86d-125">On the Action Pane, click Tracing.</span></span>
    * <span data-ttu-id="bd86d-126">Sono disponibili più opzioni di tracciabilità che forniscono informazioni sui clienti interessati dall'articolo che si sta tracciando e sugli ordini cliente correlati all'articolo che sono stati sia spediti che non spediti.</span><span class="sxs-lookup"><span data-stu-id="bd86d-126">There are several tracing options which provide information about the customers impacted by the item that you’re tracing, and the sales orders related to the item which have and haven’t been shipped.</span></span>   
6. <span data-ttu-id="bd86d-127">Fare clic su Clienti.</span><span class="sxs-lookup"><span data-stu-id="bd86d-127">Click Customers.</span></span>
7. <span data-ttu-id="bd86d-128">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="bd86d-128">Close the page.</span></span>
8. <span data-ttu-id="bd86d-129">Nel riquadro azioni fare clic su Tracciatura.</span><span class="sxs-lookup"><span data-stu-id="bd86d-129">On the Action Pane, click Tracing.</span></span>
9. <span data-ttu-id="bd86d-130">Fare clic su Ordini cliente spediti.</span><span class="sxs-lookup"><span data-stu-id="bd86d-130">Click Shipped sales orders.</span></span>
10. <span data-ttu-id="bd86d-131">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="bd86d-131">Close the page.</span></span>

