--- 
title: 'Dichiarazione di finito per un''ubicazione controllata da targa '
description: "In questa guida di attività è riportato un esempio di dichiarazione di finito a un'ubicazione che non controllata da targa."
author: ChristianRytt
manager: AnnBe
ms.date: 06/23/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 9a7901b307cffb81cce351e4e45ac8f73f328b02
ms.contentlocale: it-it
ms.lasthandoff: 04/13/2018

---
# <a name="report-as-finished-to-a-plate-controlled-location"></a><span data-ttu-id="4f727-103">Dichiarazione di finito per un'ubicazione controllata da targa </span><span class="sxs-lookup"><span data-stu-id="4f727-103">Report as finished to a plate-controlled location</span></span> 

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="4f727-104">In questa guida di attività è riportato un esempio di dichiarazione di finito a un'ubicazione che non controllata da targa.</span><span class="sxs-lookup"><span data-stu-id="4f727-104">This task guide shows an example of reporting as finished to a location that isn't license plate–controlled.</span></span> <span data-ttu-id="4f727-105">I criteri di lavoro applicabili sono il prerequisito per questa attività.</span><span class="sxs-lookup"><span data-stu-id="4f727-105">An applicable work policy is the prerequisite for this task.</span></span> <span data-ttu-id="4f727-106">Una guida di attività precedente ha mostrato l'impostazione dei criteri di lavoro.</span><span class="sxs-lookup"><span data-stu-id="4f727-106">A previous task guide showed the setup of the work policy.</span></span> <span data-ttu-id="4f727-107">Questa guida attività richiede l'applicazione Dynamics AX 7.0.1 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="4f727-107">This task guide requires Dynamics AX application 7.0.1 or later.</span></span>




## <a name="set-up-an-output-location"></a><span data-ttu-id="4f727-108">Impostare un'ubicazione di output</span><span class="sxs-lookup"><span data-stu-id="4f727-108">Set up an output location</span></span>
1. <span data-ttu-id="4f727-109">Andare ad Amministrazione organizzazione > Risorse > Gruppi di risorse.</span><span class="sxs-lookup"><span data-stu-id="4f727-109">Go to Organization administration > Resources > Resource groups.</span></span>
2. <span data-ttu-id="4f727-110">Nell'elenco selezionare il gruppo di risorse "5102".</span><span class="sxs-lookup"><span data-stu-id="4f727-110">In the list, select resource group '5102'.</span></span>
3. <span data-ttu-id="4f727-111">Fare clic su Modifica.</span><span class="sxs-lookup"><span data-stu-id="4f727-111">Click Edit.</span></span>
4. <span data-ttu-id="4f727-112">Nel campo Magazzino di output immettere "51".</span><span class="sxs-lookup"><span data-stu-id="4f727-112">In the Output warehouse field, enter '51'.</span></span>
5. <span data-ttu-id="4f727-113">Nel campo Ubicazione di output immettere "001".</span><span class="sxs-lookup"><span data-stu-id="4f727-113">In the Output location field, enter '001'.</span></span>
    * <span data-ttu-id="4f727-114">L'ubicazione 001 non è un'ubicazione controllata da targa.</span><span class="sxs-lookup"><span data-stu-id="4f727-114">Location 001 isn't a license plate–controlled location.</span></span> <span data-ttu-id="4f727-115">È possibile impostare un'ubicazione di output senza targa solo se i criteri di lavoro applicabili sono disponibili per l'ubicazione.</span><span class="sxs-lookup"><span data-stu-id="4f727-115">You can set up a non–license plate output location only if an applicable work policy exists for the location.</span></span>  

## <a name="create-a-production-order-and-report-it-as-finished"></a><span data-ttu-id="4f727-116">Creare un ordine di produzione e segnalarlo come finito</span><span class="sxs-lookup"><span data-stu-id="4f727-116">Create a production order and report it as finished</span></span>
1. <span data-ttu-id="4f727-117">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="4f727-117">Close the page.</span></span>
2. <span data-ttu-id="4f727-118">Andare a Controllo produzione > Ordini di produzione > Tutti gli ordini di produzione.</span><span class="sxs-lookup"><span data-stu-id="4f727-118">Go to Production control > Production orders > All production orders.</span></span>
3. <span data-ttu-id="4f727-119">Fare clic su Nuovo ordine di produzione.</span><span class="sxs-lookup"><span data-stu-id="4f727-119">Click New production order.</span></span>
4. <span data-ttu-id="4f727-120">Nel campo Numero articolo immettere "L0101".</span><span class="sxs-lookup"><span data-stu-id="4f727-120">In the Item number field, enter 'L0101'.</span></span>
5. <span data-ttu-id="4f727-121">Fare clic su Crea.</span><span class="sxs-lookup"><span data-stu-id="4f727-121">Click Create.</span></span>
6. <span data-ttu-id="4f727-122">Nel riquadro azioni, fare clic su Ordine di produzione.</span><span class="sxs-lookup"><span data-stu-id="4f727-122">On the Action Pane, click Production order.</span></span>
7. <span data-ttu-id="4f727-123">Fare clic su Stima.</span><span class="sxs-lookup"><span data-stu-id="4f727-123">Click Estimate.</span></span>
8. <span data-ttu-id="4f727-124">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="4f727-124">Click OK.</span></span>
9. <span data-ttu-id="4f727-125">Fare clic su Inizia.</span><span class="sxs-lookup"><span data-stu-id="4f727-125">Click Start.</span></span>
10. <span data-ttu-id="4f727-126">Fare clic sulla scheda Generale.</span><span class="sxs-lookup"><span data-stu-id="4f727-126">Click the General tab.</span></span>
11. <span data-ttu-id="4f727-127">Nel campo Consumo DBA automatico selezionare "Mai".</span><span class="sxs-lookup"><span data-stu-id="4f727-127">In the Automatic BOM consumption field, select 'Never'.</span></span>
12. <span data-ttu-id="4f727-128">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="4f727-128">Click OK.</span></span>
13. <span data-ttu-id="4f727-129">Fare clic su Dichiarato finito.</span><span class="sxs-lookup"><span data-stu-id="4f727-129">Click Report as finished.</span></span>
14. <span data-ttu-id="4f727-130">Fare clic sulla scheda Generale.</span><span class="sxs-lookup"><span data-stu-id="4f727-130">Click the General tab.</span></span>
15. <span data-ttu-id="4f727-131">Selezionare Sì nel campo Accetta errore.</span><span class="sxs-lookup"><span data-stu-id="4f727-131">Select Yes in the Accept error field.</span></span>
16. <span data-ttu-id="4f727-132">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="4f727-132">Click OK.</span></span>
17. <span data-ttu-id="4f727-133">Nel riquadro azioni fare clic su Magazzino.</span><span class="sxs-lookup"><span data-stu-id="4f727-133">On the Action Pane, click Warehouse.</span></span>
18. <span data-ttu-id="4f727-134">Fare clic su Dettagli lavoro.</span><span class="sxs-lookup"><span data-stu-id="4f727-134">Click Work details.</span></span>
    * <span data-ttu-id="4f727-135">Quando l'ordine di produzione è stato dichiarato finito, nessun lavoro è stato generato per lo stoccaggio.</span><span class="sxs-lookup"><span data-stu-id="4f727-135">When the production order was reported as finished, no work was generated for put-away.</span></span> <span data-ttu-id="4f727-136">Questa situazione si verifica perché vengono definiti criteri di lavoro che impediscono la generazione del lavoro quando il prodotto L0101 viene dichiarato finito all'ubicazione 001.</span><span class="sxs-lookup"><span data-stu-id="4f727-136">This occurs because a work policy is defined that prevents work from being generated when product L0101 is reported as finished to location 001.</span></span>  


