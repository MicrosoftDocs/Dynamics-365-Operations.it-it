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
ms.search.form: WHSCycleCountPlan, WHSWorkLineCycleCount, WHSWorkTemplateLineGroup, WHSWorkTemplateTable
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: 626b2f9f35b94124168adb7bb09c75a086d38a97
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---

# <a name="partial-location-cycle-counting"></a><span data-ttu-id="8fade-104">Conteggio ciclo ubicazioni parziale</span><span class="sxs-lookup"><span data-stu-id="8fade-104">Partial location cycle counting</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="8fade-105">I piani di conteggio ciclo definiscono le operazioni di conteggio effettivo.</span><span class="sxs-lookup"><span data-stu-id="8fade-105">Cycle count plans guide the actual counting operations.</span></span> <span data-ttu-id="8fade-106">È possibile fare in modo che solo prodotti specifici e varianti di prodotto vengano conteggiati anziché tutte le scorte disponibili in un'ubicazione.</span><span class="sxs-lookup"><span data-stu-id="8fade-106">You can request that only specific products and product variants be counted instead of all on-hand inventory in a location.</span></span>

<span data-ttu-id="8fade-107">Utilizzando i piani di conteggio ciclo per creare il lavoro di conteggio, è possibile definire le operazioni di conteggio effettivo.</span><span class="sxs-lookup"><span data-stu-id="8fade-107">By using cycle count plans to create counting work, you can guide the actual counting operations.</span></span> <span data-ttu-id="8fade-108">È possibile fare in modo che solo prodotti specifici e varianti di prodotto vengano conteggiati anziché tutte le scorte disponibili in un'ubicazione.</span><span class="sxs-lookup"><span data-stu-id="8fade-108">You can request that only specific products and product variants be counted instead of all on-hand inventory in a location.</span></span> <span data-ttu-id="8fade-109">Filtrando per prodotti specifici, il responsabile del magazzino può ridurre i costi generali di revisione, evitare errori di consolidamento e risparmiare tempo.</span><span class="sxs-lookup"><span data-stu-id="8fade-109">By filtering on specific products, the warehouse manager can reduce review overhead, avoid consolidation mistakes, and save time.</span></span>

## <a name="how-to-configure-partial-location-cycle-counting"></a><span data-ttu-id="8fade-110">Istruzioni per configurare il conteggio ciclo dell'ubicazione</span><span class="sxs-lookup"><span data-stu-id="8fade-110">How to configure partial location cycle counting</span></span>
<span data-ttu-id="8fade-111">Quando si utilizza il processo di lavoro di magazzino per le operazioni di conteggio, un'intestazione di lavoro viene creata per ogni ubicazione.</span><span class="sxs-lookup"><span data-stu-id="8fade-111">When you use the warehouse work process for counting operations, a work header is created for each location.</span></span> <span data-ttu-id="8fade-112">Quando si definisce il piano di conteggio ciclo, è possibile utilizzare la query **Seleziona ubicazioni** per limitare il lavoro di conteggio ciclo creato.</span><span class="sxs-lookup"><span data-stu-id="8fade-112">When you define the cycle count plan, you can use the **Select locations** query to limit the cycle counting work that is created.</span></span> <span data-ttu-id="8fade-113">Quando si selezionano i prodotti per il piano di conteggio ciclo, è possibile selezionare le query per il prodotto e le varianti di prodotto per perfezionare il conteggio.</span><span class="sxs-lookup"><span data-stu-id="8fade-113">When you select products for the cycle count plan, you can select both product and product variant queries to refine what is counted.</span></span> 

<span data-ttu-id="8fade-114">È possibile associare un **modello di lavoro** a un piano di conteggio ciclo per definire in che modo il lavoro di conteggio ciclo deve essere creato.</span><span class="sxs-lookup"><span data-stu-id="8fade-114">You can associate a **work template** with a cycle count plan to define how the cycle count work should be created.</span></span> <span data-ttu-id="8fade-115">Il modello di lavoro per le operazioni di conteggio è un riferimento diretto per il piano di conteggio ciclo.</span><span class="sxs-lookup"><span data-stu-id="8fade-115">The work template for counting operations is directly referenced from the cycle count plan.</span></span> 

<span data-ttu-id="8fade-116">Quando si definiscono i dettagli del modello di lavoro, è possibile utilizzare l'opzione **Interruzioni riga lavoro** per specificare se le righe del lavoro di conteggio devono essere raggruppate in base al numero di articolo o al numero di variante prodotto.</span><span class="sxs-lookup"><span data-stu-id="8fade-116">When you define the work template details, you can use the **Work line breaks** option to specify whether the counting work lines must be grouped by item number or product variant number.</span></span> <span data-ttu-id="8fade-117">Questa impostazione è necessaria se si desidera conteggiare le scorte disponibili solo per i prodotti specifici di un'ubicazione.</span><span class="sxs-lookup"><span data-stu-id="8fade-117">This setup is required if you want to count on-hand inventory only for specific products in a location.</span></span> <span data-ttu-id="8fade-118">Le righe del lavoro di conteggio ciclo create avranno il livello di informazioni definito qui e l'operazione di conteggio guidata verrà gestita in base a tale livello.</span><span class="sxs-lookup"><span data-stu-id="8fade-118">The cycle counting work lines that are created will have the level of information that you define here, and the guided counting operation will be handled based on this level.</span></span> 

<span data-ttu-id="8fade-119">Se si associano i piani di conteggio ciclo ai modelli di lavoro mediante l'opzione **Interruzioni riga lavoro**, il campo **Conteggio ciclo parziale** viene selezionato per il lavoro di conteggio ciclo creato e più righe del lavoro di conteggio ciclo verranno create in base alla definizione del modello di lavoro.</span><span class="sxs-lookup"><span data-stu-id="8fade-119">If you associate cycle count plans with work templates by using the **Work lines breaks** option, the **Partial cycle count** field is selected for the cycle counting work that is created, and multiple cycle counting work lines will be created based on the definition of the work template.</span></span> 

<span data-ttu-id="8fade-120">Prima che il lavoro di conteggio ciclo parziale possa essere elaborato, è necessario, come minimo, selezionare **Visualizza numero articolo** per la voce di menu del dispositivo mobile come parte della configurazione del conteggio ciclo.</span><span class="sxs-lookup"><span data-stu-id="8fade-120">Before partial cycle count work can be processed, you must, at a minimum, select **Display item number** for the mobile device menu item as part of the cycle counting setup.</span></span> <span data-ttu-id="8fade-121">All'operatore di magazzino verrà chiesto di registrare solo le informazioni di conteggio correlate alle righe di conteggio (numeri articolo e dimensioni prodotto).</span><span class="sxs-lookup"><span data-stu-id="8fade-121">The warehouse operator will be asked to record only counting information that is related to the counting lines (item numbers and product dimensions).</span></span> <span data-ttu-id="8fade-122">Tutte le altre scorte disponibili verranno ignorate in questo processo di conteggio.</span><span class="sxs-lookup"><span data-stu-id="8fade-122">All other on-hand inventory will be ignored for this counting process.</span></span> 

<span data-ttu-id="8fade-123">Per il processo di conteggio ciclo parziale, la data/ora **Ultimo conteggio ciclo** non verranno aggiornate per l'ubicazione.</span><span class="sxs-lookup"><span data-stu-id="8fade-123">For the partial cycle count process, the **Last cycle count** date/time won’t be updated for the location.</span></span>

## <a name="example"></a><span data-ttu-id="8fade-124">Esempio</span><span class="sxs-lookup"><span data-stu-id="8fade-124">Example</span></span>
<span data-ttu-id="8fade-125">Per questo esempio, solo il numero di articolo A0001 deve essere conteggiato nel magazzino 61.</span><span class="sxs-lookup"><span data-stu-id="8fade-125">For this example, only item number A0001 must be counted in warehouse 61.</span></span>

1.  <span data-ttu-id="8fade-126">Viene creato un nuovo modello di lavoro per il conteggio ciclo.</span><span class="sxs-lookup"><span data-stu-id="8fade-126">A new work template for cycle counting is created.</span></span> <span data-ttu-id="8fade-127">L'opzione **Interruzioni riga lavoro** viene utilizzata per raggruppare le righe del lavoro di conteggio per numero di articolo.</span><span class="sxs-lookup"><span data-stu-id="8fade-127">The **Work line breaks** option is used to group counting work lines by item number.</span></span> <span data-ttu-id="8fade-128">Di conseguenza, il lavoro di conteggio ciclo creato avrà righe per numero di articolo.</span><span class="sxs-lookup"><span data-stu-id="8fade-128">Therefore, the cycle counting work that is created will have lines per item number.</span></span> <span data-ttu-id="8fade-129">È inoltre possibile raggruppare le righe per numero di varianti prodotto.</span><span class="sxs-lookup"><span data-stu-id="8fade-129">You can also group the lines by product variant number.</span></span>
2.  <span data-ttu-id="8fade-130">Viene creato un nuovo piano di conteggio ciclo che fa riferimento al modello di lavoro appena creato.</span><span class="sxs-lookup"><span data-stu-id="8fade-130">A new cycle counting plan is created that references the newly created work template.</span></span> <span data-ttu-id="8fade-131">Il piano di conteggio ciclo include tutte le ubicazioni nel magazzino 61 (query **Seleziona ubicazioni** ) che dispongono di scorte per il numero di articolo A0001.</span><span class="sxs-lookup"><span data-stu-id="8fade-131">The cycle counting plan includes all locations in warehouse 61 (**Select locations** query) that hold inventory for item number A0001.</span></span> <span data-ttu-id="8fade-132">La selezione di prodotti specifici viene definita nella sezione **Selezioni del prodotto del piano di conteggio ciclo**.</span><span class="sxs-lookup"><span data-stu-id="8fade-132">The selection of specific products is defined in the **Cycle count product selections** section.</span></span>
3.  <span data-ttu-id="8fade-133">È possibile selezionare i prodotti per i piani di conteggio ciclo impostando il campo **Ubicazioni vuote** su  **Escludi ubicazioni vuote**. Quando il piano di conteggio ciclo viene elaborato, viene creato il lavoro di conteggio ciclo parziale per il numero di articolo A0001.</span><span class="sxs-lookup"><span data-stu-id="8fade-133">You can select products for cycle counting plans by setting the **Empty locations** field to **Exclude empty**.When the cycle counting plan is processed, partial cycle count work for item number A0001 is created.</span></span> <span data-ttu-id="8fade-134">Il processo di conteggio effettivo può essere eseguito mediante una voce di menu del dispositivo mobile per il conteggio ciclo guidato.</span><span class="sxs-lookup"><span data-stu-id="8fade-134">The actual counting process can be performed by using a mobile device menu item for guided cycle counting.</span></span>



<a name="see-also"></a><span data-ttu-id="8fade-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8fade-135">See also</span></span>
--------

[<span data-ttu-id="8fade-136">Conteggio ciclo</span><span class="sxs-lookup"><span data-stu-id="8fade-136">Cycle counting</span></span>](cycle-counting.md)


