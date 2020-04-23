---
title: Articoli fittizi
description: Questo argomento descrive in dettaglio in che modo è possibile usare il tipo di riga Fittizio per le righe di una distinta base (DBA) e una formula in Dynamics 365 Supply Chain Management.
author: ShylaThompson
manager: tfehr
ms.date: 06/15/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysOperationTemplateForm
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 1705903
ms.search.region: Global
ms.author: shylaw
ms.search.validfrom: ''
ms.dyn365.ops.version: 8.0999999999999996
ms.openlocfilehash: dc69687b1dd94407b28209178e923fe5169bcdac
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2020
ms.locfileid: "3211332"
---
# <a name="phantom-items"></a><span data-ttu-id="a2536-103">Articoli fittizi</span><span class="sxs-lookup"><span data-stu-id="a2536-103">Phantom items</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a2536-104">Questo argomento descrive in dettaglio in che modo è possibile usare il tipo di riga Fittizio per le righe di una distinta base (DBA) e una formula.</span><span class="sxs-lookup"><span data-stu-id="a2536-104">This topic describes, in detail, how the Phantom line type can be used for the lines of a bill of materials (BOM) and a formula.</span></span> <span data-ttu-id="a2536-105">Nella figura seguente, (a) è la DBA per il prodotto H e le parti F e G e (b) è la scheda cicli di lavorazione per i prodotti H e la parte F.</span><span class="sxs-lookup"><span data-stu-id="a2536-105">In the following illustration, (a) is the BOM for product H and parts F and G, and (b) is the route sheet for products H and part F.</span></span>

![Prodotto H e parte F](media/product-H-part-F.png)


<span data-ttu-id="a2536-107">Questa figura mostra un esempio di una struttura DBA a due livelli.</span><span class="sxs-lookup"><span data-stu-id="a2536-107">This illustration shows an example of a BOM structure in two levels.</span></span> <span data-ttu-id="a2536-108">Il prodotto finito H rappresenta un prodotto per l'assemblaggio di una macchina.</span><span class="sxs-lookup"><span data-stu-id="a2536-108">Finished product H represents a product for a machine assembly.</span></span> <span data-ttu-id="a2536-109">L'assemblaggio della macchina consiste di due parti, un'unità elettrica (F) che ha due materiali (A e B) e un gruppo di materiali da imballaggio (G) che ha anch'esso due materiali (C e D).</span><span class="sxs-lookup"><span data-stu-id="a2536-109">The machine assembly consists of two parts, an electrical unit (F) that has two materials (A and B) and a group of packaging materials (G) that also has two materials (C and D).</span></span> <span data-ttu-id="a2536-110">Un altro materiale (E) viene utilizzato durante l'assemblaggio generale della macchina.</span><span class="sxs-lookup"><span data-stu-id="a2536-110">Another material (E) is used during the general assembly of the machine.</span></span>

![Prodotto H e parte F](media/product-H-part-B.png)

<span data-ttu-id="a2536-112">La figura precedente rappresenta la DBA progettazione per il prodotto H. Questa struttura offre una buona panoramica delle parti e dei componenti dell'intero assemblaggio della macchina.</span><span class="sxs-lookup"><span data-stu-id="a2536-112">The preceding illustration represents the Engineering BOM for product H. This structure provides a good overview of the parts and components of the overall machine assembly.</span></span> <span data-ttu-id="a2536-113">Tuttavia, sebbene i progettisti possano preferire di vedere la DBA rappresentata in questo modo, questa struttura potrebbe non rappresentare correttamente in modo in cui la macchina viene costruita nello shop floor.</span><span class="sxs-lookup"><span data-stu-id="a2536-113">However, although product designers might prefer to see the BOM represented in this way, this structure might not correctly represent the way that the machine is built on the shop floor.</span></span> 

<span data-ttu-id="a2536-114">La DBA progettazione nella figura precedente, ad esempio, indica che l'unità elettrica F viene assemblata come parte separata in un ordine di lavoro separato.</span><span class="sxs-lookup"><span data-stu-id="a2536-114">For example, the Engineering BOM in the preceding illustration indicates that electrical unit F is assembled as a separate part on a separate work order.</span></span> <span data-ttu-id="a2536-115">Tuttavia, nello shop floor potrebbe risultare più ottimale assemblare l'unità elettrica come parte dell'intero assemblaggio della macchina, non come ordine di lavoro separato.</span><span class="sxs-lookup"><span data-stu-id="a2536-115">However, on the shop floor, it might be judged more optimal to assemble the electrical unit as part of the overall machine assembly, not as a separate work order.</span></span>

<span data-ttu-id="a2536-116">Questa DBA progettazione indica anche che la parte G è una parte separata.</span><span class="sxs-lookup"><span data-stu-id="a2536-116">This Engineering BOM also indicates that part G is a separate part.</span></span> <span data-ttu-id="a2536-117">Tuttavia, in questa struttura la parte G non rappresenta una parte fisica ma una raccolta di materiali da imballaggio.</span><span class="sxs-lookup"><span data-stu-id="a2536-117">However, in this structure, part G doesn’t represent a physical part but a collection of packaging materials.</span></span> 

<span data-ttu-id="a2536-118">Di conseguenza, anche se una DBA progettazione ha immesso valore per la progettazione di un prodotto e la gestione di quel progetto, potrebbe non essere il modo più logico per supportare il processo di produzione del prodotto.</span><span class="sxs-lookup"><span data-stu-id="a2536-118">Therefore, although an Engineering BOM provides great value for the design of a product and maintenance of that design, it might not be the most logical way to support the manufacturing execution process of the product.</span></span> <span data-ttu-id="a2536-119">Per contro, una DBA di produzione rappresenta il modo migliore per creare un prodotto.</span><span class="sxs-lookup"><span data-stu-id="a2536-119">By contrast, a Manufacturing BOM represents the best way to build a product.</span></span>

<span data-ttu-id="a2536-120">La figura seguente mostra come la DBA progettazione precedente viene importata in una DBA di produzione.</span><span class="sxs-lookup"><span data-stu-id="a2536-120">The following illustration shows how the preceding Engineering BOM is transitioned into a Manufacturing BOM.</span></span> <span data-ttu-id="a2536-121">In questa illustrazione, (a) è la DBA per il prodotto H e (b) è la scheda cicli di lavorazione per il prodotto H.</span><span class="sxs-lookup"><span data-stu-id="a2536-121">In this illustration, (a) is the BOM for product H, and b is the route sheet for product H.</span></span>

<span data-ttu-id="a2536-122">In questa struttura, si noterà che non sono presenti nozioni delle parti F e G e i materiali di cui consistono queste parti sono stati elevati al livello successivo della DBA.</span><span class="sxs-lookup"><span data-stu-id="a2536-122">In this structure, you can see that there is no notion of parts F and G, and the materials that these parts consist of have been elevated to the next BOM level.</span></span> 

<span data-ttu-id="a2536-123">A differenza della DBA progettazione, che ha due prospetti operativi, la DBA di produzione ha un solo prospetto operativo.</span><span class="sxs-lookup"><span data-stu-id="a2536-123">Unlike the Engineering BOM, which had two operations sheets, the Manufacturing BOM has only one operations sheet.</span></span> <span data-ttu-id="a2536-124">Anche l'operazione di imballaggio che è stata associata alla parte G è stata elevata e ora fa parte del prospetto operativo per il prodotto H. L'assemblaggio dell'unità elettrica è la prima operazione.</span><span class="sxs-lookup"><span data-stu-id="a2536-124">The packaging operation that was linked to part G has also been elevated and is now part of the operations sheet for product H. The assembly of the electrical unit is the first operation.</span></span> <span data-ttu-id="a2536-125">Questo ordine è logico perché questa unità viene utilizzata nell'operazione successiva che è l'assemblaggio della macchina.</span><span class="sxs-lookup"><span data-stu-id="a2536-125">This order makes good sense, because this unit is used in the next operation, which is the machine assembly.</span></span> <span data-ttu-id="a2536-126">L'ultima operazione è l'operazione di imballaggio, che utilizza due materiali di imballaggio (C e D).</span><span class="sxs-lookup"><span data-stu-id="a2536-126">The last operation is the packaging operation, which consumes two packing materials (C and D).</span></span>

<span data-ttu-id="a2536-127">La transizione tra la DBA progettazione e la DBA di produzione viene abilitata attraverso il tipo di riga di DBA fittizio.</span><span class="sxs-lookup"><span data-stu-id="a2536-127">The transition between the Engineering BOM and the Manufacturing BOM is enabled through the Phantom BOM line type.</span></span> <span data-ttu-id="a2536-128">Come indica il termine" fittizio", le parti F e G sono scomparse durante la transizione tra i due tipi di DBA.</span><span class="sxs-lookup"><span data-stu-id="a2536-128">As the term “phantom” indicates, parts F and G have disappeared during the transition between the two BOM types.</span></span> <span data-ttu-id="a2536-129">In questo esempio, il tipo di riga fittizio viene applicato alle righe DBA per le parti F e G nella DBA progettazione.</span><span class="sxs-lookup"><span data-stu-id="a2536-129">In this example, the Phantom line type is applied to the BOM lines for parts F and G in the Engineering BOM.</span></span> <span data-ttu-id="a2536-130">Quando viene creato un ordine batch o di produzione, la DBA progettazione viene copiata nell'ordine batch o di produzione.</span><span class="sxs-lookup"><span data-stu-id="a2536-130">When a production or batch order is created, the Engineering BOM is copied to the production or batch order.</span></span> <span data-ttu-id="a2536-131">In seguito, quando l'ordine viene stimato, viene eseguita la transizione dalla DBA progettazione alla DBA di produzione, come mostrato nelle illustrazioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="a2536-131">Then, when the order is estimated, the transition from the Engineering BOM to the Manufacturing BOM occurs, as shown in the preceding illustrations.</span></span> <span data-ttu-id="a2536-132">Dal prospetto operativo nella seconda illustrazione, i materiali di imballaggio C e D sono input per l'operazione.</span><span class="sxs-lookup"><span data-stu-id="a2536-132">From the operations sheet in the second illustration, packaging materials C and D are input for the operation.</span></span> 

## <a name="multilevel-phantom-bom-structures"></a><span data-ttu-id="a2536-133">Strutture DBA fittizie multilivello</span><span class="sxs-lookup"><span data-stu-id="a2536-133">Multilevel phantom BOM structures</span></span>
<span data-ttu-id="a2536-134">È possibile utilizzare il tipo di riga fittizio nelle strutture DBA multilivello, come mostrato nell'illustrazione seguente.</span><span class="sxs-lookup"><span data-stu-id="a2536-134">The Phantom line type can be used in multilevel BOM structures, as shown in the following illustration.</span></span> <span data-ttu-id="a2536-135">In questa illustrazione, (a) è la DBA per il prodotto G e (b) è la scheda cicli di lavorazione per le parti E e F e il prodotto G.</span><span class="sxs-lookup"><span data-stu-id="a2536-135">In this illustration, (a) is the BOM for product G, and (b) is the route sheet for parts E and F and product G.</span></span> 

![Prodotto G e parte F con le schede cicli di lavorazione](media/product-G-route-sheet-G.png)


<span data-ttu-id="a2536-137">La figura seguente mostra la DBA di produzione e la scheda cicli di produzione risultanti se la righe DBA per le parti E e F vengono configurate con il tipo di riga fittizio.</span><span class="sxs-lookup"><span data-stu-id="a2536-137">The following illustration shows the resulting Manufacturing BOM and route sheet if the BOM lines for parts E and F are configured so that the line type is Phantom.</span></span> <span data-ttu-id="a2536-138">In questa illustrazione, (a) è la DBA per il prodotto G e (b) è la scheda cicli di lavorazione per il prodotto G.</span><span class="sxs-lookup"><span data-stu-id="a2536-138">In this illustration, (a) is the BOM for product G, and (b) is the route sheet for product G.</span></span>

![Prodotto G](media/product-G.png)


## <a name="phantom-and-route-network"></a><span data-ttu-id="a2536-140">Rete di cicli di lavorazione e fittizia</span><span class="sxs-lookup"><span data-stu-id="a2536-140">Phantom and route network</span></span>
<span data-ttu-id="a2536-141">La DBA fittizia può essere utilizzata anche per una DBA con una rete di cicli di lavorazione.</span><span class="sxs-lookup"><span data-stu-id="a2536-141">Phantom BOMs can also be used for a BOM that has a route network.</span></span> <span data-ttu-id="a2536-142">In una rete di cicli di lavorazione, una o più operazioni vengono eseguite in parallelo.</span><span class="sxs-lookup"><span data-stu-id="a2536-142">In a route network, one or more operations run in parallel.</span></span> <span data-ttu-id="a2536-143">La figura seguente mostra un esempio di una rete di cicli di lavorazione utilizzata in una distinta base multilivello.</span><span class="sxs-lookup"><span data-stu-id="a2536-143">The following illustration shows an example of a route network that is used in a multilevel BOM.</span></span> <span data-ttu-id="a2536-144">In questa illustrazione, (a) è la DBA per il prodotto G e la parte F e (b) è la scheda cicli di lavorazione per il prodotto G e la parte F, che ha una rete di cicli di lavorazione.</span><span class="sxs-lookup"><span data-stu-id="a2536-144">In this illustration, (a) is the BOM for product G and part F, and (b) is the route sheet for product G and part F, which has a route network.</span></span>

![Prodotto G e parte F](media/product-G-part-F.png)


<span data-ttu-id="a2536-146">Nella figura seguente, (a) è la DBA per il prodotto G e la parte F e (b) è la scheda cicli di lavorazione per il prodotto G e la parte F.</span><span class="sxs-lookup"><span data-stu-id="a2536-146">In the following illustration, (a) is the BOM for product G and part F, and (b) is the route sheet for product G and part F.</span></span>

![Prodotto G e parte F con le schede cicli di lavorazione](media/product-G-part-F-with-route-sheet.png)
