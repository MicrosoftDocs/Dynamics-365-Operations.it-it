---
title: Conteggio ciclo ubicazioni parziale
description: "I piani di conteggio ciclo definiscono le operazioni di conteggio effettivo. È possibile fare in modo che solo prodotti specifici e varianti di prodotto vengano conteggiati anziché tutte le scorte disponibili in un'ubicazione."
author: perlynne
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
keywords: WHSCycleCountPlan, WHSWorkLineCycleCount, WHSWorkTemplateLineGroup, WHSWorkTemplateTable
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 08c38aada355583c5a6872f75b57db95d9b81786
ms.openlocfilehash: 2ee4de8eabc55271e272ca3026746787353f5fc3
ms.contentlocale: it-it
ms.lasthandoff: 07/18/2017

---

# <a name="partial-location-cycle-counting"></a><span data-ttu-id="85879-105">Conteggio ciclo ubicazioni parziale</span><span class="sxs-lookup"><span data-stu-id="85879-105">Partial location cycle counting</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="85879-106">I piani di conteggio ciclo definiscono le operazioni di conteggio effettivo.</span><span class="sxs-lookup"><span data-stu-id="85879-106">Cycle count plans guide the actual counting operations.</span></span> <span data-ttu-id="85879-107">È possibile fare in modo che solo prodotti specifici e varianti di prodotto vengano conteggiati anziché tutte le scorte disponibili in un'ubicazione.</span><span class="sxs-lookup"><span data-stu-id="85879-107">You can request that only specific products and product variants be counted instead of all on-hand inventory in a location.</span></span>

<span data-ttu-id="85879-108">Utilizzando i piani di conteggio ciclo per creare il lavoro di conteggio, è possibile definire le operazioni di conteggio effettivo.</span><span class="sxs-lookup"><span data-stu-id="85879-108">By using cycle count plans to create counting work, you can guide the actual counting operations.</span></span> <span data-ttu-id="85879-109">È possibile fare in modo che solo prodotti specifici e varianti di prodotto vengano conteggiati anziché tutte le scorte disponibili in un'ubicazione.</span><span class="sxs-lookup"><span data-stu-id="85879-109">You can request that only specific products and product variants be counted instead of all on-hand inventory in a location.</span></span> <span data-ttu-id="85879-110">Filtrando per prodotti specifici, il responsabile del magazzino può ridurre i costi generali di revisione, evitare errori di consolidamento e risparmiare tempo.</span><span class="sxs-lookup"><span data-stu-id="85879-110">By filtering on specific products, the warehouse manager can reduce review overhead, avoid consolidation mistakes, and save time.</span></span>

## <a name="how-to-configure-partial-location-cycle-counting"></a><span data-ttu-id="85879-111">Istruzioni per configurare il conteggio ciclo dell'ubicazione</span><span class="sxs-lookup"><span data-stu-id="85879-111">How to configure partial location cycle counting</span></span>
<span data-ttu-id="85879-112">Quando si utilizza il processo di lavoro di magazzino per le operazioni di conteggio, un'intestazione di lavoro viene creata per ogni ubicazione.</span><span class="sxs-lookup"><span data-stu-id="85879-112">When you use the warehouse work process for counting operations, a work header is created for each location.</span></span> <span data-ttu-id="85879-113">Quando si definisce il piano di conteggio ciclo, è possibile utilizzare la query **Seleziona ubicazioni** per limitare il lavoro di conteggio ciclo creato.</span><span class="sxs-lookup"><span data-stu-id="85879-113">When you define the cycle count plan, you can use the **Select locations** query to limit the cycle counting work that is created.</span></span> <span data-ttu-id="85879-114">Quando si selezionano i prodotti per il piano di conteggio ciclo, è possibile selezionare le query per il prodotto e le varianti di prodotto per perfezionare il conteggio.</span><span class="sxs-lookup"><span data-stu-id="85879-114">When you select products for the cycle count plan, you can select both product and product variant queries to refine what is counted.</span></span> 

<span data-ttu-id="85879-115">È possibile associare un **modello di lavoro** a un piano di conteggio ciclo per definire in che modo il lavoro di conteggio ciclo deve essere creato.</span><span class="sxs-lookup"><span data-stu-id="85879-115">You can associate a **work template** with a cycle count plan to define how the cycle count work should be created.</span></span> <span data-ttu-id="85879-116">Il modello di lavoro per le operazioni di conteggio è un riferimento diretto per il piano di conteggio ciclo.</span><span class="sxs-lookup"><span data-stu-id="85879-116">The work template for counting operations is directly referenced from the cycle count plan.</span></span> 

<span data-ttu-id="85879-117">Quando si definiscono i dettagli del modello di lavoro, è possibile utilizzare l'opzione **Interruzioni riga lavoro** per specificare se le righe del lavoro di conteggio devono essere raggruppate in base al numero di articolo o al numero di variante prodotto.</span><span class="sxs-lookup"><span data-stu-id="85879-117">When you define the work template details, you can use the **Work line breaks** option to specify whether the counting work lines must be grouped by item number or product variant number.</span></span> <span data-ttu-id="85879-118">Questa impostazione è necessaria se si desidera conteggiare le scorte disponibili solo per i prodotti specifici di un'ubicazione.</span><span class="sxs-lookup"><span data-stu-id="85879-118">This setup is required if you want to count on-hand inventory only for specific products in a location.</span></span> <span data-ttu-id="85879-119">Le righe del lavoro di conteggio ciclo create avranno il livello di informazioni definito qui e l'operazione di conteggio guidata verrà gestita in base a tale livello.</span><span class="sxs-lookup"><span data-stu-id="85879-119">The cycle counting work lines that are created will have the level of information that you define here, and the guided counting operation will be handled based on this level.</span></span> 

<span data-ttu-id="85879-120">Se si associano i piani di conteggio ciclo ai modelli di lavoro mediante l'opzione **Interruzioni riga lavoro**, il campo **Conteggio ciclo parziale** viene selezionato per il lavoro di conteggio ciclo creato e più righe del lavoro di conteggio ciclo verranno create in base alla definizione del modello di lavoro.</span><span class="sxs-lookup"><span data-stu-id="85879-120">If you associate cycle count plans with work templates by using the **Work lines breaks** option, the **Partial cycle count** field is selected for the cycle counting work that is created, and multiple cycle counting work lines will be created based on the definition of the work template.</span></span> 

<span data-ttu-id="85879-121">Prima che il lavoro di conteggio ciclo parziale possa essere elaborato, è necessario, come minimo, selezionare **Visualizza numero articolo** per la voce di menu del dispositivo mobile come parte della configurazione del conteggio ciclo.</span><span class="sxs-lookup"><span data-stu-id="85879-121">Before partial cycle count work can be processed, you must, at a minimum, select **Display item number** for the mobile device menu item as part of the cycle counting setup.</span></span> <span data-ttu-id="85879-122">All'operatore di magazzino verrà chiesto di registrare solo le informazioni di conteggio correlate alle righe di conteggio (numeri articolo e dimensioni prodotto).</span><span class="sxs-lookup"><span data-stu-id="85879-122">The warehouse operator will be asked to record only counting information that is related to the counting lines (item numbers and product dimensions).</span></span> <span data-ttu-id="85879-123">Tutte le altre scorte disponibili verranno ignorate in questo processo di conteggio.</span><span class="sxs-lookup"><span data-stu-id="85879-123">All other on-hand inventory will be ignored for this counting process.</span></span> 

<span data-ttu-id="85879-124">Per il processo di conteggio ciclo parziale, la data/ora **Ultimo conteggio ciclo** non verranno aggiornate per l'ubicazione.</span><span class="sxs-lookup"><span data-stu-id="85879-124">For the partial cycle count process, the **Last cycle count** date/time won’t be updated for the location.</span></span>

## <a name="example"></a><span data-ttu-id="85879-125">Esempio</span><span class="sxs-lookup"><span data-stu-id="85879-125">Example</span></span>
<span data-ttu-id="85879-126">Per questo esempio, solo il numero di articolo A0001 deve essere conteggiato nel magazzino 61.</span><span class="sxs-lookup"><span data-stu-id="85879-126">For this example, only item number A0001 must be counted in warehouse 61.</span></span>

1.  <span data-ttu-id="85879-127">Viene creato un nuovo modello di lavoro per il conteggio ciclo.</span><span class="sxs-lookup"><span data-stu-id="85879-127">A new work template for cycle counting is created.</span></span> <span data-ttu-id="85879-128">L'opzione **Interruzioni riga lavoro** viene utilizzata per raggruppare le righe del lavoro di conteggio per numero di articolo.</span><span class="sxs-lookup"><span data-stu-id="85879-128">The **Work line breaks** option is used to group counting work lines by item number.</span></span> <span data-ttu-id="85879-129">Di conseguenza, il lavoro di conteggio ciclo creato avrà righe per numero di articolo.</span><span class="sxs-lookup"><span data-stu-id="85879-129">Therefore, the cycle counting work that is created will have lines per item number.</span></span> <span data-ttu-id="85879-130">È inoltre possibile raggruppare le righe per numero di varianti prodotto.</span><span class="sxs-lookup"><span data-stu-id="85879-130">You can also group the lines by product variant number.</span></span>
2.  <span data-ttu-id="85879-131">Viene creato un nuovo piano di conteggio ciclo che fa riferimento al modello di lavoro appena creato.</span><span class="sxs-lookup"><span data-stu-id="85879-131">A new cycle counting plan is created that references the newly created work template.</span></span> <span data-ttu-id="85879-132">Il piano di conteggio ciclo include tutte le ubicazioni nel magazzino 61 (query **Seleziona ubicazioni** ) che dispongono di scorte per il numero di articolo A0001.</span><span class="sxs-lookup"><span data-stu-id="85879-132">The cycle counting plan includes all locations in warehouse 61 (**Select locations** query) that hold inventory for item number A0001.</span></span> <span data-ttu-id="85879-133">La selezione di prodotti specifici viene definita nella sezione **Selezioni del prodotto del piano di conteggio ciclo**.</span><span class="sxs-lookup"><span data-stu-id="85879-133">The selection of specific products is defined in the **Cycle count product selections** section.</span></span>
3.  <span data-ttu-id="85879-134">È possibile selezionare i prodotti per i piani di conteggio ciclo impostando il campo **Ubicazioni vuote** su  **Escludi ubicazioni vuote**. Quando il piano di conteggio ciclo viene elaborato, viene creato il lavoro di conteggio ciclo parziale per il numero di articolo A0001.</span><span class="sxs-lookup"><span data-stu-id="85879-134">You can select products for cycle counting plans by setting the **Empty locations** field to **Exclude empty**.When the cycle counting plan is processed, partial cycle count work for item number A0001 is created.</span></span> <span data-ttu-id="85879-135">Il processo di conteggio effettivo può essere eseguito mediante una voce di menu del dispositivo mobile per il conteggio ciclo guidato.</span><span class="sxs-lookup"><span data-stu-id="85879-135">The actual counting process can be performed by using a mobile device menu item for guided cycle counting.</span></span>



<a name="see-also"></a><span data-ttu-id="85879-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="85879-136">See also</span></span>
--------

[<span data-ttu-id="85879-137">Conteggio ciclo</span><span class="sxs-lookup"><span data-stu-id="85879-137">Cycle counting</span></span>](cycle-counting.md)


