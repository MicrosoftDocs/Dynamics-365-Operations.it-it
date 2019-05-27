---
title: Generare un piano con vincoli
description: In questa procedura viene descritta la creazione di un piano in cui verranno considerati sia i vincoli materiali che di capacità.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, ReqCreatePlanWorkspace, ReqTransPlanCard, ReqPlanSched
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0e2265f7788fd2a4a37f6fb96d7562649dbc5b1c
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "1556025"
---
# <a name="generate-a-constrained-plan"></a><span data-ttu-id="fadc3-103">Generare un piano con vincoli</span><span class="sxs-lookup"><span data-stu-id="fadc3-103">Generate a constrained plan</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="fadc3-104">In questa procedura viene descritta la creazione di un piano in cui verranno considerati sia i vincoli materiali che di capacità.</span><span class="sxs-lookup"><span data-stu-id="fadc3-104">This procedure shows how to create a plan that takes into account both material and capacity constraints.</span></span> <span data-ttu-id="fadc3-105">Il piano garantisce che la produzione non inizi prima che i materiali siano disponibili e che le risorse non siano sovraprenotate.</span><span class="sxs-lookup"><span data-stu-id="fadc3-105">The plan ensures that manufacturing doesn't start before materials are available and resources are not overbooked.</span></span> 

<span data-ttu-id="fadc3-106">La società di dati dimostrativi utilizzata per creare questa procedura è USMF.</span><span class="sxs-lookup"><span data-stu-id="fadc3-106">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="fadc3-107">Questa procedura è destinata al responsabile pianificazione produzione.</span><span class="sxs-lookup"><span data-stu-id="fadc3-107">This procedure is intended for the production planner.</span></span>


## <a name="set-up-a-constrained-plan"></a><span data-ttu-id="fadc3-108">Impostare un piano con vincoli</span><span class="sxs-lookup"><span data-stu-id="fadc3-108">Set up a constrained plan</span></span>
1. <span data-ttu-id="fadc3-109">Fare clic su Pianificazione generale.</span><span class="sxs-lookup"><span data-stu-id="fadc3-109">Click Master planning.</span></span>
2. <span data-ttu-id="fadc3-110">Fare clic su Piani generali.</span><span class="sxs-lookup"><span data-stu-id="fadc3-110">Click Master plans.</span></span>
3. <span data-ttu-id="fadc3-111">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="fadc3-111">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="fadc3-112">Esempio: StaticPlan</span><span class="sxs-lookup"><span data-stu-id="fadc3-112">Example: StaticPlan</span></span>  
4. <span data-ttu-id="fadc3-113">Selezionare Sì nel campo Capacità limitata.</span><span class="sxs-lookup"><span data-stu-id="fadc3-113">Select Yes in the Finite capacity field.</span></span>
5. <span data-ttu-id="fadc3-114">Nel campo Intervallo temporale capacità limitata immettere "30".</span><span class="sxs-lookup"><span data-stu-id="fadc3-114">In the Finite capacity time fence field, enter '30'.</span></span>
6. <span data-ttu-id="fadc3-115">Espandere gli intervalli temporali nella sezione Giorni.</span><span class="sxs-lookup"><span data-stu-id="fadc3-115">Expand the Time fences in days section.</span></span>
7. <span data-ttu-id="fadc3-116">Selezionare Sì nel campo Capacità.</span><span class="sxs-lookup"><span data-stu-id="fadc3-116">Select Yes in the Capacity field.</span></span>
8. <span data-ttu-id="fadc3-117">Nel campo Intervallo temporale programmazione capacità (giorni) immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="fadc3-117">In the Capacity scheduling time fence (days) field, enter a number.</span></span>
    * <span data-ttu-id="fadc3-118">Esempio: 60</span><span class="sxs-lookup"><span data-stu-id="fadc3-118">Example: 60</span></span>  
9. <span data-ttu-id="fadc3-119">Selezionare Sì nel campo Ritardi calcolati.</span><span class="sxs-lookup"><span data-stu-id="fadc3-119">Select Yes in the Calculated delays field.</span></span>
10. <span data-ttu-id="fadc3-120">Nel campo Calcola intervallo temporale dei ritardi (giorni) immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="fadc3-120">In the Calculate delays time fence (days) field, enter a number.</span></span>
    * <span data-ttu-id="fadc3-121">Esempio: 60</span><span class="sxs-lookup"><span data-stu-id="fadc3-121">Example: 60</span></span>  
11. <span data-ttu-id="fadc3-122">Espandere la sezione Ritardi calcolati.</span><span class="sxs-lookup"><span data-stu-id="fadc3-122">Expand the Calculated delays section.</span></span>
12. <span data-ttu-id="fadc3-123">Selezionare Sì nel campo Aggiungere il ritardo calcolato alla data del fabbisogno</span><span class="sxs-lookup"><span data-stu-id="fadc3-123">Select Yes in the Add the calculated delay to the requirement date field.</span></span>
13. <span data-ttu-id="fadc3-124">Selezionare Sì nel campo Aggiungere il ritardo calcolato alla data del fabbisogno</span><span class="sxs-lookup"><span data-stu-id="fadc3-124">Select Yes in the Add the calculated delay to the requirement date field.</span></span>
14. <span data-ttu-id="fadc3-125">Selezionare Sì nel campo Aggiungere il ritardo calcolato alla data del fabbisogno</span><span class="sxs-lookup"><span data-stu-id="fadc3-125">Select Yes in the Add the calculated delay to the requirement date field.</span></span>
15. <span data-ttu-id="fadc3-126">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="fadc3-126">Close the page.</span></span>

## <a name="create-a-constrained-plan"></a><span data-ttu-id="fadc3-127">Crea un piano con vincoli</span><span class="sxs-lookup"><span data-stu-id="fadc3-127">Create a constrained plan</span></span>
1. <span data-ttu-id="fadc3-128">Fare clic su Esegui.</span><span class="sxs-lookup"><span data-stu-id="fadc3-128">Click Run.</span></span>
2. <span data-ttu-id="fadc3-129">Nel campo Piano generale immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="fadc3-129">In the Master plan field, enter or select a value.</span></span>
    * <span data-ttu-id="fadc3-130">Selezionare il piano per cui sono stati impostati i vincoli.</span><span class="sxs-lookup"><span data-stu-id="fadc3-130">Select the plan for which you have set up constraints.</span></span>  
3. <span data-ttu-id="fadc3-131">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="fadc3-131">Click OK.</span></span>
    * <span data-ttu-id="fadc3-132">Questa operazione potrebbe richiedere tempo.</span><span class="sxs-lookup"><span data-stu-id="fadc3-132">This may take a while.</span></span>  
4. <span data-ttu-id="fadc3-133">Fare clic su Ordini pianificati.</span><span class="sxs-lookup"><span data-stu-id="fadc3-133">Click Planned orders.</span></span>

