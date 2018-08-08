---
title: Avviare un ordine di produzione
description: Questa procedura mostra come avviare un ordine di produzione in Controllo shop floor.
author: johanhoffmann
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: f83091a9f3e96a9176860bd16fa5969507488a25
ms.contentlocale: it-it
ms.lasthandoff: 08/07/2018

---
# <a name="start-a-production-order"></a><span data-ttu-id="c9f4d-103">Avviare un ordine di produzione</span><span class="sxs-lookup"><span data-stu-id="c9f4d-103">Start a production order</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="c9f4d-104">Questa procedura mostra come avviare un ordine di produzione in Controllo shop floor.</span><span class="sxs-lookup"><span data-stu-id="c9f4d-104">This procedure shows how to start a production order on the shop floor.</span></span> <span data-ttu-id="c9f4d-105">Il consumo di tempo e materiali è dichiarato in questo processo.</span><span class="sxs-lookup"><span data-stu-id="c9f4d-105">Time and material consumption are reported in this process.</span></span> <span data-ttu-id="c9f4d-106">La società di dati dimostrativi utilizzata per creare questa procedura è USMF.</span><span class="sxs-lookup"><span data-stu-id="c9f4d-106">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="c9f4d-107">Si tratta della quinta procedura su sette che spiega il ciclo di vita dell'ordine di produzione.</span><span class="sxs-lookup"><span data-stu-id="c9f4d-107">This is the fifth procedure out of seven which explains the production order lifecycle.</span></span>


## <a name="start-a-production-order"></a><span data-ttu-id="c9f4d-108">Avviare un ordine di produzione</span><span class="sxs-lookup"><span data-stu-id="c9f4d-108">Start a production order</span></span>
1. <span data-ttu-id="c9f4d-109">Andare a Controllo produzione > Ordini di produzione > Tutti gli ordini di produzione.</span><span class="sxs-lookup"><span data-stu-id="c9f4d-109">Go to Production control > Production orders > All production orders.</span></span>
    * <span data-ttu-id="c9f4d-110">Selezionare un ordine di produzione con stato Rilasciato.</span><span class="sxs-lookup"><span data-stu-id="c9f4d-110">Select a production order that has the Released status.</span></span>  
2. <span data-ttu-id="c9f4d-111">Nel riquadro azioni fare clic su Ordine di produzione.</span><span class="sxs-lookup"><span data-stu-id="c9f4d-111">On the Action Pane, click Production order.</span></span>
3. <span data-ttu-id="c9f4d-112">Fare clic su Inizia.</span><span class="sxs-lookup"><span data-stu-id="c9f4d-112">Click Start.</span></span>
    * <span data-ttu-id="c9f4d-113">In questa pagina, è possibile confermare l'avvio dell'ordine di produzione.</span><span class="sxs-lookup"><span data-stu-id="c9f4d-113">On this page, you can confirm the start of the production order.</span></span>  
4. <span data-ttu-id="c9f4d-114">Fare clic sulla scheda Generale.</span><span class="sxs-lookup"><span data-stu-id="c9f4d-114">Click the General tab.</span></span>
5. <span data-ttu-id="c9f4d-115">Nel campo Da oper.</span><span class="sxs-lookup"><span data-stu-id="c9f4d-115">In the From Oper.</span></span> <span data-ttu-id="c9f4d-116">N.</span><span class="sxs-lookup"><span data-stu-id="c9f4d-116">No.</span></span> <span data-ttu-id="c9f4d-117">immettere '10'.</span><span class="sxs-lookup"><span data-stu-id="c9f4d-117">field, enter '10'.</span></span>
6. <span data-ttu-id="c9f4d-118">Nel campo Consumo automatico ciclo di lavorazione selezionare 'Sempre'.</span><span class="sxs-lookup"><span data-stu-id="c9f4d-118">In the Automatic route consumption field, select 'Always'.</span></span>
7. <span data-ttu-id="c9f4d-119">Fare clic sulla casella di controllo Registra scheda ciclo di lav. ora.</span><span class="sxs-lookup"><span data-stu-id="c9f4d-119">Click the Post route card now checkbox.</span></span>
8. <span data-ttu-id="c9f4d-120">Nel campo Consumo DBA automatico selezionare 'Sempre'.</span><span class="sxs-lookup"><span data-stu-id="c9f4d-120">In the Automatic BOM consumption field, select 'Always'.</span></span>
9. <span data-ttu-id="c9f4d-121">Fare clic sulla casella di controllo Registra distinta di prelievo ora.</span><span class="sxs-lookup"><span data-stu-id="c9f4d-121">Click the Post picking list now checkbox.</span></span>
10. <span data-ttu-id="c9f4d-122">Fare clic sulla casella di controllo Stampa distinta di prelievo.</span><span class="sxs-lookup"><span data-stu-id="c9f4d-122">Click the Print picking list checkbox.</span></span>
11. <span data-ttu-id="c9f4d-123">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="c9f4d-123">Click OK.</span></span>
    * <span data-ttu-id="c9f4d-124">Si tratta della distinta di prelievo stampata contenente i materiali utilizzati per l'ordine di produzione.</span><span class="sxs-lookup"><span data-stu-id="c9f4d-124">This is the printed picking list that shows the materials used for the production order.</span></span>  
12. <span data-ttu-id="c9f4d-125">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="c9f4d-125">Close the page.</span></span>

## <a name="validate-the-picking-list"></a><span data-ttu-id="c9f4d-126">Convalidare la distinta di prelievo</span><span class="sxs-lookup"><span data-stu-id="c9f4d-126">Validate the picking list</span></span>
1. <span data-ttu-id="c9f4d-127">Nel riquadro azioni fare clic su Visualizza.</span><span class="sxs-lookup"><span data-stu-id="c9f4d-127">On the Action Pane, click View.</span></span>
2. <span data-ttu-id="c9f4d-128">Fare clic su Distinta di prelievo.</span><span class="sxs-lookup"><span data-stu-id="c9f4d-128">Click Picking list.</span></span>
3. <span data-ttu-id="c9f4d-129">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="c9f4d-129">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="c9f4d-130">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="c9f4d-130">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="c9f4d-131">Fare clic su Modifica.</span><span class="sxs-lookup"><span data-stu-id="c9f4d-131">Click Edit.</span></span>
6. <span data-ttu-id="c9f4d-132">Nel campo Consumo immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="c9f4d-132">In the Consumption field, enter a number.</span></span>
7. <span data-ttu-id="c9f4d-133">Fare clic su Registra.</span><span class="sxs-lookup"><span data-stu-id="c9f4d-133">Click Post.</span></span>
8. <span data-ttu-id="c9f4d-134">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="c9f4d-134">Click OK.</span></span>
    * <span data-ttu-id="c9f4d-135">Nel giornale di registrazione distinte di prelievo, i materiali consumati nell'ordine di produzione vengono registrati.</span><span class="sxs-lookup"><span data-stu-id="c9f4d-135">In the picking list journal, the materials consumed by the production order are posted.</span></span> <span data-ttu-id="c9f4d-136">Prima della registrazione del giornale di registrazione, è possibile apportare rettifiche se è presente una differenza tra la quantità stimata e la quantità effettiva.</span><span class="sxs-lookup"><span data-stu-id="c9f4d-136">Before posting the journal, you can make adjustments if there is a difference between the estimated quantity and the actual consumed quantity.</span></span>  
9. <span data-ttu-id="c9f4d-137">Fare clic sulla scheda GridPanel.</span><span class="sxs-lookup"><span data-stu-id="c9f4d-137">Click the GridPanel tab.</span></span>
10. <span data-ttu-id="c9f4d-138">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="c9f4d-138">Close the page.</span></span>

## <a name="verify-the-route-card-journal"></a><span data-ttu-id="c9f4d-139">Verificare il giornale di registrazione delle schede cicli di lavorazione</span><span class="sxs-lookup"><span data-stu-id="c9f4d-139">Verify the route card journal</span></span>
1. <span data-ttu-id="c9f4d-140">Nel riquadro azioni fare clic su Visualizza.</span><span class="sxs-lookup"><span data-stu-id="c9f4d-140">On the Action Pane, click View.</span></span>
2. <span data-ttu-id="c9f4d-141">Fare clic su Scheda ciclo di lavorazione.</span><span class="sxs-lookup"><span data-stu-id="c9f4d-141">Click Route card.</span></span>
3. <span data-ttu-id="c9f4d-142">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="c9f4d-142">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="c9f4d-143">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="c9f4d-143">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="c9f4d-144">Fare clic su Modifica.</span><span class="sxs-lookup"><span data-stu-id="c9f4d-144">Click Edit.</span></span>
6. <span data-ttu-id="c9f4d-145">Nel campo Ore immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="c9f4d-145">In the Hours field, enter a number.</span></span>
7. <span data-ttu-id="c9f4d-146">Fare clic su Registra.</span><span class="sxs-lookup"><span data-stu-id="c9f4d-146">Click Post.</span></span>
8. <span data-ttu-id="c9f4d-147">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="c9f4d-147">Click OK.</span></span>
    * <span data-ttu-id="c9f4d-148">Nel giornale di registrazione schede cicli di lavorazione, il tempo trascorso sulle singole operazioni viene registrato.</span><span class="sxs-lookup"><span data-stu-id="c9f4d-148">In the Route card journal, the time spent on the individual operations is recorded.</span></span> <span data-ttu-id="c9f4d-149">È possibile dichiarare anche la quantità idonea e quella difettosa.</span><span class="sxs-lookup"><span data-stu-id="c9f4d-149">Good and error quantity can also be reported.</span></span>  

