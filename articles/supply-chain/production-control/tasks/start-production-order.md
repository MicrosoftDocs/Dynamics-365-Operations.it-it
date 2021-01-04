---
title: Avviare un ordine di produzione
description: Questa procedura mostra come avviare un ordine di produzione in Controllo shop floor.
author: johanhoffmann
manager: tfehr
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: JmgRegistrationStartJob
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 47915a93151b1adc99ddb4e3facb29bf8db49dd6
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4431068"
---
# <a name="start-a-production-order"></a><span data-ttu-id="d371e-103">Avviare un ordine di produzione</span><span class="sxs-lookup"><span data-stu-id="d371e-103">Start a production order</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="d371e-104">Questa procedura mostra come avviare un ordine di produzione in Controllo shop floor.</span><span class="sxs-lookup"><span data-stu-id="d371e-104">This procedure shows how to start a production order on the shop floor.</span></span> <span data-ttu-id="d371e-105">Il consumo di tempo e materiali è dichiarato in questo processo.</span><span class="sxs-lookup"><span data-stu-id="d371e-105">Time and material consumption are reported in this process.</span></span> <span data-ttu-id="d371e-106">La società di dati dimostrativi utilizzata per creare questa procedura è USMF.</span><span class="sxs-lookup"><span data-stu-id="d371e-106">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="d371e-107">Si tratta della quinta procedura su sette che spiega il ciclo di vita dell'ordine di produzione.</span><span class="sxs-lookup"><span data-stu-id="d371e-107">This is the fifth procedure out of seven which explains the production order lifecycle.</span></span>


## <a name="start-a-production-order"></a><span data-ttu-id="d371e-108">Avviare un ordine di produzione</span><span class="sxs-lookup"><span data-stu-id="d371e-108">Start a production order</span></span>
1. <span data-ttu-id="d371e-109">Andare a Controllo produzione > Ordini di produzione > Tutti gli ordini di produzione.</span><span class="sxs-lookup"><span data-stu-id="d371e-109">Go to Production control > Production orders > All production orders.</span></span>
    * <span data-ttu-id="d371e-110">Selezionare un ordine di produzione con stato Rilasciato.</span><span class="sxs-lookup"><span data-stu-id="d371e-110">Select a production order that has the Released status.</span></span>  
2. <span data-ttu-id="d371e-111">Nel riquadro azioni fare clic su Ordine di produzione.</span><span class="sxs-lookup"><span data-stu-id="d371e-111">On the Action Pane, click Production order.</span></span>
3. <span data-ttu-id="d371e-112">Fare clic su Inizia.</span><span class="sxs-lookup"><span data-stu-id="d371e-112">Click Start.</span></span>
    * <span data-ttu-id="d371e-113">In questa pagina, è possibile confermare l'avvio dell'ordine di produzione.</span><span class="sxs-lookup"><span data-stu-id="d371e-113">On this page, you can confirm the start of the production order.</span></span>  
4. <span data-ttu-id="d371e-114">Fare clic sulla scheda Generale.</span><span class="sxs-lookup"><span data-stu-id="d371e-114">Click the General tab.</span></span>
5. <span data-ttu-id="d371e-115">Nel campo Da oper.</span><span class="sxs-lookup"><span data-stu-id="d371e-115">In the From Oper.</span></span> <span data-ttu-id="d371e-116">N.</span><span class="sxs-lookup"><span data-stu-id="d371e-116">No.</span></span> <span data-ttu-id="d371e-117">immettere '10'.</span><span class="sxs-lookup"><span data-stu-id="d371e-117">field, enter '10'.</span></span>
6. <span data-ttu-id="d371e-118">Nel campo Consumo automatico ciclo di lavorazione selezionare 'Sempre'.</span><span class="sxs-lookup"><span data-stu-id="d371e-118">In the Automatic route consumption field, select 'Always'.</span></span>
7. <span data-ttu-id="d371e-119">Fare clic sulla casella di controllo Registra scheda ciclo di lav. ora.</span><span class="sxs-lookup"><span data-stu-id="d371e-119">Click the Post route card now checkbox.</span></span>
8. <span data-ttu-id="d371e-120">Nel campo Consumo DBA automatico selezionare 'Sempre'.</span><span class="sxs-lookup"><span data-stu-id="d371e-120">In the Automatic BOM consumption field, select 'Always'.</span></span>
9. <span data-ttu-id="d371e-121">Fare clic sulla casella di controllo Registra distinta di prelievo ora.</span><span class="sxs-lookup"><span data-stu-id="d371e-121">Click the Post picking list now checkbox.</span></span>
10. <span data-ttu-id="d371e-122">Fare clic sulla casella di controllo Stampa distinta di prelievo.</span><span class="sxs-lookup"><span data-stu-id="d371e-122">Click the Print picking list checkbox.</span></span>
11. <span data-ttu-id="d371e-123">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="d371e-123">Click OK.</span></span>
    * <span data-ttu-id="d371e-124">Si tratta della distinta di prelievo stampata contenente i materiali utilizzati per l'ordine di produzione.</span><span class="sxs-lookup"><span data-stu-id="d371e-124">This is the printed picking list that shows the materials used for the production order.</span></span>  
12. <span data-ttu-id="d371e-125">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="d371e-125">Close the page.</span></span>

## <a name="validate-the-picking-list"></a><span data-ttu-id="d371e-126">Convalidare la distinta di prelievo</span><span class="sxs-lookup"><span data-stu-id="d371e-126">Validate the picking list</span></span>
1. <span data-ttu-id="d371e-127">Nel riquadro azioni fare clic su Visualizza.</span><span class="sxs-lookup"><span data-stu-id="d371e-127">On the Action Pane, click View.</span></span>
2. <span data-ttu-id="d371e-128">Fare clic su Distinta di prelievo.</span><span class="sxs-lookup"><span data-stu-id="d371e-128">Click Picking list.</span></span>
3. <span data-ttu-id="d371e-129">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="d371e-129">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="d371e-130">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="d371e-130">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="d371e-131">Fare clic su Modifica.</span><span class="sxs-lookup"><span data-stu-id="d371e-131">Click Edit.</span></span>
6. <span data-ttu-id="d371e-132">Nel campo Consumo immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="d371e-132">In the Consumption field, enter a number.</span></span>
7. <span data-ttu-id="d371e-133">Fare clic su Registra.</span><span class="sxs-lookup"><span data-stu-id="d371e-133">Click Post.</span></span>
8. <span data-ttu-id="d371e-134">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="d371e-134">Click OK.</span></span>
    * <span data-ttu-id="d371e-135">Nel giornale di registrazione distinte di prelievo, i materiali consumati nell'ordine di produzione vengono registrati.</span><span class="sxs-lookup"><span data-stu-id="d371e-135">In the picking list journal, the materials consumed by the production order are posted.</span></span> <span data-ttu-id="d371e-136">Prima della registrazione del giornale di registrazione, è possibile apportare rettifiche se è presente una differenza tra la quantità stimata e la quantità effettiva.</span><span class="sxs-lookup"><span data-stu-id="d371e-136">Before posting the journal, you can make adjustments if there is a difference between the estimated quantity and the actual consumed quantity.</span></span>  
9. <span data-ttu-id="d371e-137">Fare clic sulla scheda GridPanel.</span><span class="sxs-lookup"><span data-stu-id="d371e-137">Click the GridPanel tab.</span></span>
10. <span data-ttu-id="d371e-138">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="d371e-138">Close the page.</span></span>

## <a name="verify-the-route-card-journal"></a><span data-ttu-id="d371e-139">Verificare il giornale di registrazione delle schede cicli di lavorazione</span><span class="sxs-lookup"><span data-stu-id="d371e-139">Verify the route card journal</span></span>
1. <span data-ttu-id="d371e-140">Nel riquadro azioni fare clic su Visualizza.</span><span class="sxs-lookup"><span data-stu-id="d371e-140">On the Action Pane, click View.</span></span>
2. <span data-ttu-id="d371e-141">Fare clic su Scheda ciclo di lavorazione.</span><span class="sxs-lookup"><span data-stu-id="d371e-141">Click Route card.</span></span>
3. <span data-ttu-id="d371e-142">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="d371e-142">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="d371e-143">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="d371e-143">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="d371e-144">Fare clic su Modifica.</span><span class="sxs-lookup"><span data-stu-id="d371e-144">Click Edit.</span></span>
6. <span data-ttu-id="d371e-145">Nel campo Ore immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="d371e-145">In the Hours field, enter a number.</span></span>
7. <span data-ttu-id="d371e-146">Fare clic su Registra.</span><span class="sxs-lookup"><span data-stu-id="d371e-146">Click Post.</span></span>
8. <span data-ttu-id="d371e-147">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="d371e-147">Click OK.</span></span>
    * <span data-ttu-id="d371e-148">Nel giornale di registrazione schede cicli di lavorazione, il tempo trascorso sulle singole operazioni viene registrato.</span><span class="sxs-lookup"><span data-stu-id="d371e-148">In the Route card journal, the time spent on the individual operations is recorded.</span></span> <span data-ttu-id="d371e-149">È possibile dichiarare anche la quantità idonea e quella difettosa.</span><span class="sxs-lookup"><span data-stu-id="d371e-149">Good and error quantity can also be reported.</span></span>  
