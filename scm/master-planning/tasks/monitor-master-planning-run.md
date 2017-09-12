--- 
title: Monitorare un'esecuzione di pianificazione generale
description: "Il pianificatore di produzione desidera verificare se è in esecuzione una pianificazione generale."
author: YuyuScheller
manager: AnnBe
ms.date: 06/10/2016
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
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 1e08d9fd3388561563e6fb982416186a652b4ce2
ms.contentlocale: it-it
ms.lasthandoff: 08/29/2017

---
# <a name="monitor-a-master-planning-run"></a><span data-ttu-id="e60ba-103">Monitorare un'esecuzione di pianificazione generale</span><span class="sxs-lookup"><span data-stu-id="e60ba-103">Monitor a master planning run</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="e60ba-104">Il pianificatore di produzione desidera verificare se è in esecuzione una pianificazione generale.</span><span class="sxs-lookup"><span data-stu-id="e60ba-104">The production planner wants to see if a master planning run is in progress.</span></span> <span data-ttu-id="e60ba-105">Per completare questa procedura utilizzare la società di dati dimostrativi USMF.</span><span class="sxs-lookup"><span data-stu-id="e60ba-105">Use the demo data company USMF to complete this procedure.</span></span>


## <a name="run-master-planning"></a><span data-ttu-id="e60ba-106">Eseguire la pianificazione generale</span><span class="sxs-lookup"><span data-stu-id="e60ba-106">Run master planning</span></span>
1. <span data-ttu-id="e60ba-107">Fare clic su Pianificazione generale.</span><span class="sxs-lookup"><span data-stu-id="e60ba-107">Click Master planning.</span></span>
    * <span data-ttu-id="e60ba-108">Apparirà sul dashboard predefinito.</span><span class="sxs-lookup"><span data-stu-id="e60ba-108">You'll find this on the default dashboard.</span></span>  
2. <span data-ttu-id="e60ba-109">Nel campo Piano immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="e60ba-109">In the Plan field, enter or select a value.</span></span>
    * <span data-ttu-id="e60ba-110">Esempio: StaticPlan</span><span class="sxs-lookup"><span data-stu-id="e60ba-110">Example: StaticPlan</span></span>  
3. <span data-ttu-id="e60ba-111">Fare clic su Esegui.</span><span class="sxs-lookup"><span data-stu-id="e60ba-111">Click Run.</span></span>
4. <span data-ttu-id="e60ba-112">Selezionare Sì nel campo Traccia ora di elaborazione.</span><span class="sxs-lookup"><span data-stu-id="e60ba-112">Select Yes in the Track processing time field.</span></span>
    * <span data-ttu-id="e60ba-113">Se il campo è già selezionato, ignorare questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="e60ba-113">If the field is already selected, skip this step.</span></span>  
5. <span data-ttu-id="e60ba-114">Nel campo Numero di thread immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="e60ba-114">In the Number of threads field, enter a number.</span></span>
6. <span data-ttu-id="e60ba-115">Espandere la sezione Record da includere.</span><span class="sxs-lookup"><span data-stu-id="e60ba-115">Expand the Records to include section.</span></span>
7. <span data-ttu-id="e60ba-116">Fare clic su Filtro.</span><span class="sxs-lookup"><span data-stu-id="e60ba-116">Click Filter.</span></span>
8. <span data-ttu-id="e60ba-117">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="e60ba-117">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="e60ba-118">Contrassegnare la riga con Campo = Numero articolo.</span><span class="sxs-lookup"><span data-stu-id="e60ba-118">Mark the row where Field = Item number.</span></span>  
9. <span data-ttu-id="e60ba-119">Nel campo Criteri immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="e60ba-119">In the Criteria field, enter or select a value.</span></span>
    * <span data-ttu-id="e60ba-120">Esempio: T0001</span><span class="sxs-lookup"><span data-stu-id="e60ba-120">Example: T0001</span></span>  
10. <span data-ttu-id="e60ba-121">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="e60ba-121">Click OK.</span></span>
11. <span data-ttu-id="e60ba-122">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="e60ba-122">Click OK.</span></span>

## <a name="monitor-the-master-planning-run"></a><span data-ttu-id="e60ba-123">Monitorare l'esecuzione di pianificazione generale</span><span class="sxs-lookup"><span data-stu-id="e60ba-123">Monitor the master planning run</span></span>
1. <span data-ttu-id="e60ba-124">Fare clic su Storico.</span><span class="sxs-lookup"><span data-stu-id="e60ba-124">Click History.</span></span>
2. <span data-ttu-id="e60ba-125">Fare clic su Richieste di informazioni.</span><span class="sxs-lookup"><span data-stu-id="e60ba-125">Click Inquiries.</span></span>
3. <span data-ttu-id="e60ba-126">Fare clic su Durata attività di processo.</span><span class="sxs-lookup"><span data-stu-id="e60ba-126">Click Process task duration.</span></span>
4. <span data-ttu-id="e60ba-127">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="e60ba-127">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="e60ba-128">Per ogni articolo è possibile ottenere una panoramica del tempo necessario per completare ogni fase di pianificazione.</span><span class="sxs-lookup"><span data-stu-id="e60ba-128">For each item you can get an overview of how long it took to complete each planning step.</span></span>  


