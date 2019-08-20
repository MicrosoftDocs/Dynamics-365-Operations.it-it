---
title: Monitorare un'esecuzione di pianificazione generale
description: Il pianificatore di produzione desidera verificare se è in esecuzione una pianificazione generale.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, ReqCreatePlanWorkspace, ReqTransPlanCard, SysQueryForm, InventItemIdLookupSimple, ReqLog, ReqProcessTaskTrace
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b923b215528ecceaed9b5057ddb736ec959f1d65
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/01/2019
ms.locfileid: "1845115"
---
# <a name="monitor-a-master-planning-run"></a><span data-ttu-id="c8e96-103">Monitorare un'esecuzione di pianificazione generale</span><span class="sxs-lookup"><span data-stu-id="c8e96-103">Monitor a master planning run</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="c8e96-104">Il pianificatore di produzione desidera verificare se è in esecuzione una pianificazione generale.</span><span class="sxs-lookup"><span data-stu-id="c8e96-104">The production planner wants to see if a master planning run is in progress.</span></span> <span data-ttu-id="c8e96-105">Per completare questa procedura utilizzare la società di dati dimostrativi USMF.</span><span class="sxs-lookup"><span data-stu-id="c8e96-105">Use the demo data company USMF to complete this procedure.</span></span>


## <a name="run-master-planning"></a><span data-ttu-id="c8e96-106">Eseguire la pianificazione generale</span><span class="sxs-lookup"><span data-stu-id="c8e96-106">Run master planning</span></span>
1. <span data-ttu-id="c8e96-107">Fare clic su Pianificazione generale.</span><span class="sxs-lookup"><span data-stu-id="c8e96-107">Click Master planning.</span></span>
    * <span data-ttu-id="c8e96-108">Apparirà sul dashboard predefinito.</span><span class="sxs-lookup"><span data-stu-id="c8e96-108">You'll find this on the default dashboard.</span></span>  
2. <span data-ttu-id="c8e96-109">Nel campo Piano immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="c8e96-109">In the Plan field, enter or select a value.</span></span>
    * <span data-ttu-id="c8e96-110">Esempio: StaticPlan</span><span class="sxs-lookup"><span data-stu-id="c8e96-110">Example: StaticPlan</span></span>  
3. <span data-ttu-id="c8e96-111">Fare clic su Esegui.</span><span class="sxs-lookup"><span data-stu-id="c8e96-111">Click Run.</span></span>
4. <span data-ttu-id="c8e96-112">Selezionare Sì nel campo Traccia ora di elaborazione.</span><span class="sxs-lookup"><span data-stu-id="c8e96-112">Select Yes in the Track processing time field.</span></span>
    * <span data-ttu-id="c8e96-113">Se il campo è già selezionato, ignorare questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="c8e96-113">If the field is already selected, skip this step.</span></span>  
5. <span data-ttu-id="c8e96-114">Nel campo Numero di thread immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="c8e96-114">In the Number of threads field, enter a number.</span></span>
6. <span data-ttu-id="c8e96-115">Espandere la sezione Record da includere.</span><span class="sxs-lookup"><span data-stu-id="c8e96-115">Expand the Records to include section.</span></span>
7. <span data-ttu-id="c8e96-116">Fare clic su Filtro.</span><span class="sxs-lookup"><span data-stu-id="c8e96-116">Click Filter.</span></span>
8. <span data-ttu-id="c8e96-117">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="c8e96-117">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="c8e96-118">Contrassegnare la riga con Campo = Numero articolo.</span><span class="sxs-lookup"><span data-stu-id="c8e96-118">Mark the row where Field = Item number.</span></span>  
9. <span data-ttu-id="c8e96-119">Nel campo Criteri immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="c8e96-119">In the Criteria field, enter or select a value.</span></span>
    * <span data-ttu-id="c8e96-120">Esempio: T0001</span><span class="sxs-lookup"><span data-stu-id="c8e96-120">Example: T0001</span></span>  
10. <span data-ttu-id="c8e96-121">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="c8e96-121">Click OK.</span></span>
11. <span data-ttu-id="c8e96-122">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="c8e96-122">Click OK.</span></span>

## <a name="monitor-the-master-planning-run"></a><span data-ttu-id="c8e96-123">Monitorare l'esecuzione di pianificazione generale</span><span class="sxs-lookup"><span data-stu-id="c8e96-123">Monitor the master planning run</span></span>
1. <span data-ttu-id="c8e96-124">Fare clic su Storico.</span><span class="sxs-lookup"><span data-stu-id="c8e96-124">Click History.</span></span>
2. <span data-ttu-id="c8e96-125">Fare clic su Richieste di informazioni.</span><span class="sxs-lookup"><span data-stu-id="c8e96-125">Click Inquiries.</span></span>
3. <span data-ttu-id="c8e96-126">Fare clic su Durata attività di processo.</span><span class="sxs-lookup"><span data-stu-id="c8e96-126">Click Process task duration.</span></span>
4. <span data-ttu-id="c8e96-127">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="c8e96-127">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="c8e96-128">Per ogni articolo è possibile ottenere una panoramica del tempo necessario per completare ogni fase di pianificazione.</span><span class="sxs-lookup"><span data-stu-id="c8e96-128">For each item you can get an overview of how long it took to complete each planning step.</span></span>  

