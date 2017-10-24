--- 
title: Generare un piano con vincoli
description: "In questa procedura viene descritta la creazione di un piano in cui verranno considerati sia i vincoli materiali che di capacità."
author: YuyuScheller
manager: AnnBe
ms.date: 03/02/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: 59c6a4a2b239b3fd6b6ddc8f06bfd007f0191f0a
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---
# <a name="generate-a-constrained-plan"></a><span data-ttu-id="c5abe-103">Generare un piano con vincoli</span><span class="sxs-lookup"><span data-stu-id="c5abe-103">Generate a constrained plan</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="c5abe-104">In questa procedura viene descritta la creazione di un piano in cui verranno considerati sia i vincoli materiali che di capacità.</span><span class="sxs-lookup"><span data-stu-id="c5abe-104">This procedure shows how to create a plan that takes into account both material and capacity constraints.</span></span> <span data-ttu-id="c5abe-105">Il piano garantisce che la produzione non inizi prima che i materiali siano disponibili e che le risorse non siano sovraprenotate.</span><span class="sxs-lookup"><span data-stu-id="c5abe-105">The plan ensures that manufacturing doesn't start before materials are available and resources are not overbooked.</span></span> 

<span data-ttu-id="c5abe-106">La società di dati dimostrativi utilizzata per creare questa procedura è USMF.</span><span class="sxs-lookup"><span data-stu-id="c5abe-106">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="c5abe-107">Questa procedura è destinata al responsabile pianificazione produzione.</span><span class="sxs-lookup"><span data-stu-id="c5abe-107">This procedure is intended for the production planner.</span></span>


## <a name="set-up-a-constrained-plan"></a><span data-ttu-id="c5abe-108">Impostare un piano con vincoli</span><span class="sxs-lookup"><span data-stu-id="c5abe-108">Set up a constrained plan</span></span>
1. <span data-ttu-id="c5abe-109">Fare clic su Pianificazione generale.</span><span class="sxs-lookup"><span data-stu-id="c5abe-109">Click Master planning.</span></span>
2. <span data-ttu-id="c5abe-110">Fare clic su Piani generali.</span><span class="sxs-lookup"><span data-stu-id="c5abe-110">Click Master plans.</span></span>
3. <span data-ttu-id="c5abe-111">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="c5abe-111">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="c5abe-112">Esempio: StaticPlan</span><span class="sxs-lookup"><span data-stu-id="c5abe-112">Example: StaticPlan</span></span>  
4. <span data-ttu-id="c5abe-113">Selezionare Sì nel campo Capacità limitata.</span><span class="sxs-lookup"><span data-stu-id="c5abe-113">Select Yes in the Finite capacity field.</span></span>
5. <span data-ttu-id="c5abe-114">Nel campo Intervallo temporale capacità limitata immettere "30".</span><span class="sxs-lookup"><span data-stu-id="c5abe-114">In the Finite capacity time fence field, enter '30'.</span></span>
6. <span data-ttu-id="c5abe-115">Espandere gli intervalli temporali nella sezione Giorni.</span><span class="sxs-lookup"><span data-stu-id="c5abe-115">Expand the Time fences in days section.</span></span>
7. <span data-ttu-id="c5abe-116">Selezionare Sì nel campo Capacità.</span><span class="sxs-lookup"><span data-stu-id="c5abe-116">Select Yes in the Capacity field.</span></span>
8. <span data-ttu-id="c5abe-117">Nel campo Intervallo temporale programmazione capacità (giorni) immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="c5abe-117">In the Capacity scheduling time fence (days) field, enter a number.</span></span>
    * <span data-ttu-id="c5abe-118">Esempio: 60</span><span class="sxs-lookup"><span data-stu-id="c5abe-118">Example: 60</span></span>  
9. <span data-ttu-id="c5abe-119">Selezionare Sì nel campo Ritardi calcolati.</span><span class="sxs-lookup"><span data-stu-id="c5abe-119">Select Yes in the Calculated delays field.</span></span>
10. <span data-ttu-id="c5abe-120">Nel campo Calcola intervallo temporale dei ritardi (giorni) immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="c5abe-120">In the Calculate delays time fence (days) field, enter a number.</span></span>
    * <span data-ttu-id="c5abe-121">Esempio: 60</span><span class="sxs-lookup"><span data-stu-id="c5abe-121">Example: 60</span></span>  
11. <span data-ttu-id="c5abe-122">Espandere la sezione Ritardi calcolati.</span><span class="sxs-lookup"><span data-stu-id="c5abe-122">Expand the Calculated delays section.</span></span>
12. <span data-ttu-id="c5abe-123">Selezionare Sì nel campo Aggiungere il ritardo calcolato alla data del fabbisogno</span><span class="sxs-lookup"><span data-stu-id="c5abe-123">Select Yes in the Add the calculated delay to the requirement date field.</span></span>
13. <span data-ttu-id="c5abe-124">Selezionare Sì nel campo Aggiungere il ritardo calcolato alla data del fabbisogno</span><span class="sxs-lookup"><span data-stu-id="c5abe-124">Select Yes in the Add the calculated delay to the requirement date field.</span></span>
14. <span data-ttu-id="c5abe-125">Selezionare Sì nel campo Aggiungere il ritardo calcolato alla data del fabbisogno</span><span class="sxs-lookup"><span data-stu-id="c5abe-125">Select Yes in the Add the calculated delay to the requirement date field.</span></span>
15. <span data-ttu-id="c5abe-126">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="c5abe-126">Close the page.</span></span>

## <a name="create-a-constrained-plan"></a><span data-ttu-id="c5abe-127">Crea un piano con vincoli</span><span class="sxs-lookup"><span data-stu-id="c5abe-127">Create a constrained plan</span></span>
1. <span data-ttu-id="c5abe-128">Fare clic su Esegui.</span><span class="sxs-lookup"><span data-stu-id="c5abe-128">Click Run.</span></span>
2. <span data-ttu-id="c5abe-129">Nel campo Piano generale immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="c5abe-129">In the Master plan field, enter or select a value.</span></span>
    * <span data-ttu-id="c5abe-130">Selezionare il piano per cui sono stati impostati i vincoli.</span><span class="sxs-lookup"><span data-stu-id="c5abe-130">Select the plan for which you have set up constraints.</span></span>  
3. <span data-ttu-id="c5abe-131">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="c5abe-131">Click OK.</span></span>
    * <span data-ttu-id="c5abe-132">Questa operazione potrebbe richiedere tempo.</span><span class="sxs-lookup"><span data-stu-id="c5abe-132">This may take a while.</span></span>  
4. <span data-ttu-id="c5abe-133">Fare clic su Ordini pianificati.</span><span class="sxs-lookup"><span data-stu-id="c5abe-133">Click Planned orders.</span></span>


