---
title: Definire gruppi di produzione snella
description: I gruppi di programmazione snella sono definiti per raggruppare e distinguere i prodotti nella programmazione kanban.
author: cvocph
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LeanScheduleGroup, GanttColorTableLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a9ad470d81d94a0af1c4c4dc6c5072354cfd96d2
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4430850"
---
# <a name="define-lean-schedule-groups"></a><span data-ttu-id="d749c-103">Definire gruppi di produzione snella</span><span class="sxs-lookup"><span data-stu-id="d749c-103">Define lean schedule groups</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="d749c-104">I gruppi di programmazione snella sono definiti per raggruppare e distinguere i prodotti nella programmazione kanban.</span><span class="sxs-lookup"><span data-stu-id="d749c-104">Lean schedule groups are defined to group and distinguish products in kanban scheduling.</span></span> <span data-ttu-id="d749c-105">Il raggruppamento può essere eseguito come associazione generica per società o specifica per cella di lavoro.</span><span class="sxs-lookup"><span data-stu-id="d749c-105">The grouping can be done as generic association per company or specific to a work cell.</span></span> <span data-ttu-id="d749c-106">A ciascun gruppo è associato un codice colore per l'indicazione visiva nella pagina elenco di programmazione kanban.</span><span class="sxs-lookup"><span data-stu-id="d749c-106">Each group has a color code assigned for visual indication in the kanban scheduling listpage.</span></span> <span data-ttu-id="d749c-107">La società di dati dimostrativi utilizzata per creare questa procedura è USMF.</span><span class="sxs-lookup"><span data-stu-id="d749c-107">The demo data company used to create this procedure is USMF.</span></span>


## <a name="define-lean-scheduling-group"></a><span data-ttu-id="d749c-108">Definire un gruppo di produzione snella</span><span class="sxs-lookup"><span data-stu-id="d749c-108">Define lean scheduling group</span></span>
1. <span data-ttu-id="d749c-109">Passare a Gestione informazioni sul prodotto > Produzione snella > Gruppi di programmazione snella.</span><span class="sxs-lookup"><span data-stu-id="d749c-109">Go to Product information management > Lean manufacturing > Lean schedule groups.</span></span>
2. <span data-ttu-id="d749c-110">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="d749c-110">Click New.</span></span>
3. <span data-ttu-id="d749c-111">Digitare un valore nel campo Gruppo di programmazione.</span><span class="sxs-lookup"><span data-stu-id="d749c-111">In the Schedule group field, type a value.</span></span>
    * <span data-ttu-id="d749c-112">Un gruppo di programmazione può essere definito come gruppo globale o specifico di una cella di lavoro.</span><span class="sxs-lookup"><span data-stu-id="d749c-112">A schedule group can be defined as global group or specific to a work cell.</span></span> <span data-ttu-id="d749c-113">In questo esempio semplice, si definisce un gruppo globale e la cella di lavoro viene mantenuta vuota.</span><span class="sxs-lookup"><span data-stu-id="d749c-113">In this simple example, we define a global group, and the work cell is kept empty.</span></span> <span data-ttu-id="d749c-114">Le impostazioni del gruppo si applicano a tutte le celle di lavoro che non dispongono di gruppi di programmazione specifici.</span><span class="sxs-lookup"><span data-stu-id="d749c-114">The settings of this group apply to all work cells that do not have specific schedule groups.</span></span>  
4. <span data-ttu-id="d749c-115">Selezionare un colore dalla selezione colori.</span><span class="sxs-lookup"><span data-stu-id="d749c-115">Select a color from the color selection.</span></span>
    * <span data-ttu-id="d749c-116">I colori utilizzati per evidenziare i processi nella pagina elenco di programmazione kanban o nella scheda del processo kanban.</span><span class="sxs-lookup"><span data-stu-id="d749c-116">The colors are used to highlight the jobs on the kanban schedule list page or the kanban process board.</span></span>  
5. <span data-ttu-id="d749c-117">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="d749c-117">In the list, mark the selected row.</span></span>
6. <span data-ttu-id="d749c-118">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="d749c-118">In the list, click the link in the selected row.</span></span>

## <a name="associate-product"></a><span data-ttu-id="d749c-119">Associare un prodotto</span><span class="sxs-lookup"><span data-stu-id="d749c-119">Associate product</span></span>
1. <span data-ttu-id="d749c-120">Associare un prodotto specifico</span><span class="sxs-lookup"><span data-stu-id="d749c-120">Associate a specific product</span></span>
    * <span data-ttu-id="d749c-121">Sono disponibili due metodi per associare i prodotti ai gruppi di programmazione snella, come prodotto specifico (tipo di relazione articolo=articolo) o come parte di una chiave di allocazione articolo (tipo di relazione articolo=gruppo).</span><span class="sxs-lookup"><span data-stu-id="d749c-121">There are two ways to associate products to lean schedule groups, either as a specific product (Item relation type = Item) or as part of an item allocation key (item relation type = group).</span></span>    
2. <span data-ttu-id="d749c-122">Nel campo Tipo di relazione articolo selezionare l'articolo</span><span class="sxs-lookup"><span data-stu-id="d749c-122">In the Item relation type field, select Item</span></span>
3. <span data-ttu-id="d749c-123">Nel campo Numero articolo, digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="d749c-123">In the Item number field, type a value.</span></span>
4. <span data-ttu-id="d749c-124">Immettere un numero nel campo Rapporto produttività.</span><span class="sxs-lookup"><span data-stu-id="d749c-124">In the Throughput ratio field, enter a number.</span></span>
    * <span data-ttu-id="d749c-125">La relazione di produttività predefinita è 1, in modo da indicare che i prodotti correlati utilizzano esattamente la capacità specificata nelle attività di elaborazione dei flussi di produzione.</span><span class="sxs-lookup"><span data-stu-id="d749c-125">The default Throughput ratio is 1, which means that the related products consume exactly the capacity specified in the process activites of the production flows.</span></span> <span data-ttu-id="d749c-126">Rapporto produttività > 1 definisce un consumo di risorse superiore, Rapporto produttività < 1 definisce un consumo di risorse inferiore.</span><span class="sxs-lookup"><span data-stu-id="d749c-126">Throughput ratio > 1 defines a higher resource consumption, Throughput ratio < 1 defines a lower resource consumption.</span></span> <span data-ttu-id="d749c-127">Il rapporto viene utilizzato nel calcolo dei costi e nel calcolo dell'avanzamento processo kanban.</span><span class="sxs-lookup"><span data-stu-id="d749c-127">The ratio is used in the cost calculation and in the calculation of the kanban job consumption.</span></span>  

## <a name="associate-item-allocation-key"></a><span data-ttu-id="d749c-128">Associare una chiave di allocazione articolo</span><span class="sxs-lookup"><span data-stu-id="d749c-128">Associate item allocation key</span></span>
1. <span data-ttu-id="d749c-129">Associare una chiave di allocazione articolo</span><span class="sxs-lookup"><span data-stu-id="d749c-129">Associate an item allocation key</span></span>
    * <span data-ttu-id="d749c-130">Aggiungere un'associazione a una chiave di allocazione articolo utilizzando il tipo di relazione articolo Gruppo.</span><span class="sxs-lookup"><span data-stu-id="d749c-130">Add an association to an item allocation key by using the Item relation type Group.</span></span>   <span data-ttu-id="d749c-131">Si noti che per questo processo, è necessario una chiave di allocazione articolo di previsione definita nei dati.</span><span class="sxs-lookup"><span data-stu-id="d749c-131">Note that for this process, you need a forecast item alllocation key defined in your data.</span></span>  
2. <span data-ttu-id="d749c-132">Nel campo Tipo di relazione articolo selezionare Gruppo</span><span class="sxs-lookup"><span data-stu-id="d749c-132">In the Item relation type field, select Group</span></span>
3. <span data-ttu-id="d749c-133">Nel campo Chiave di allocazione articolo fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="d749c-133">In the Item allocation key field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="d749c-134">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="d749c-134">In the list, click the link in the selected row.</span></span>

