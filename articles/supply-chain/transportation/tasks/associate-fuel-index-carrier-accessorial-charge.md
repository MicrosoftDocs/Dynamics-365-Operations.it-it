--- 
title: Associare un indice carburante a un vettore come spesa accessoria
description: Questa guida illustra creare un'assegnazione di spese accessorie, di spese accessorie per il vettore spedizione e di spese accessorie principali per il supplemento carburante e come associare un indice carburante a un vettore.
author: BibiSp
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: a2b8534231c5fa50b1e0f709e09d318bb8202a43
ms.contentlocale: it-it
ms.lasthandoff: 08/29/2017

---
# <a name="associate-a-fuel-index-with-a-carrier-as-an-accessorial-charge"></a><span data-ttu-id="2c83f-103">Associare un indice carburante a un vettore come spesa accessoria</span><span class="sxs-lookup"><span data-stu-id="2c83f-103">Associate a fuel index with a carrier as an accessorial charge</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="2c83f-104">Questa guida illustra creare un'assegnazione di spese accessorie, di spese accessorie per il vettore spedizione e di spese accessorie principali per il supplemento carburante e come associare un indice carburante a un vettore.</span><span class="sxs-lookup"><span data-stu-id="2c83f-104">This guide shows how to create an accessorial assignment, carrier accessorial charge, accessorial master for fuel surcharge, and associate a carrier fuel index with a carrier.</span></span> <span data-ttu-id="2c83f-105">Prima di eseguire questa guida. è necessario aver impostato un indice carburante vettore.</span><span class="sxs-lookup"><span data-stu-id="2c83f-105">You need to have set up a carrier fuel index before you run this guide.</span></span> <span data-ttu-id="2c83f-106">A tale scopo, è possibile utilizzare la guida "Impostare un indice carburante vettore".</span><span class="sxs-lookup"><span data-stu-id="2c83f-106">You can use the “Set up a carrier fuel index” guide to do this.</span></span> <span data-ttu-id="2c83f-107">Queste attività di impostazione in genere vengono effettuate da un responsabile della logistica.</span><span class="sxs-lookup"><span data-stu-id="2c83f-107">These setup tasks are typically done by a Logistics manager.</span></span> <span data-ttu-id="2c83f-108">La società di dati dimostrativi utilizzata per creare questa procedura è USMF.</span><span class="sxs-lookup"><span data-stu-id="2c83f-108">The demo data used to create this procedure is USMF.</span></span>


## <a name="create-an-accessorial-master"></a><span data-ttu-id="2c83f-109">Creare spese accessorie principali</span><span class="sxs-lookup"><span data-stu-id="2c83f-109">Create an accessorial master</span></span>
1. <span data-ttu-id="2c83f-110">Andare a Gestione trasporto > Impostazioni > Valutazione > Rappresentazioni generali accessorie.</span><span class="sxs-lookup"><span data-stu-id="2c83f-110">Go to Transportation management > Setup > Rating > Accessorial masters.</span></span>
2. <span data-ttu-id="2c83f-111">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="2c83f-111">Click New.</span></span>
3. <span data-ttu-id="2c83f-112">Nel campo Spese accessorie principali digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="2c83f-112">In the Accessorial master field, type a value.</span></span>
4. <span data-ttu-id="2c83f-113">Digitare un valore nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="2c83f-113">In the Name field, type a value.</span></span>
5. <span data-ttu-id="2c83f-114">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="2c83f-114">Click Save.</span></span>

## <a name="create-a-carrier-accessorial-charge"></a><span data-ttu-id="2c83f-115">Creare spese accessorie vettore</span><span class="sxs-lookup"><span data-stu-id="2c83f-115">Create a carrier accessorial charge</span></span>
1. <span data-ttu-id="2c83f-116">Andare a Gestione trasporto > Impostazioni > Valutazione > Spese accessorie vettore.</span><span class="sxs-lookup"><span data-stu-id="2c83f-116">Go to Transportation management > Setup > Rating > Carrier accessorial charges.</span></span>
2. <span data-ttu-id="2c83f-117">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="2c83f-117">Click New.</span></span>
3. <span data-ttu-id="2c83f-118">Nel campo ID spese accessorie vettore digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="2c83f-118">In the Carrier accessorial ID field, type a value.</span></span>
4. <span data-ttu-id="2c83f-119">Nel campo Vettore spedizione fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="2c83f-119">In the Shipping carrier field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="2c83f-120">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="2c83f-120">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="2c83f-121">In questo esempio scegliere Truck Carrier.</span><span class="sxs-lookup"><span data-stu-id="2c83f-121">In this example, choose Truck Carrier.</span></span>  
6. <span data-ttu-id="2c83f-122">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="2c83f-122">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="2c83f-123">Nel campo Servizio trasporto fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="2c83f-123">In the Carrier service field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="2c83f-124">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="2c83f-124">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="2c83f-125">Nel campo Spese accessorie principali fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="2c83f-125">In the Accessorial master field, click the drop-down button to open the lookup.</span></span>
10. <span data-ttu-id="2c83f-126">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="2c83f-126">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="2c83f-127">In questo esempio scegliere le spese accessorie principali create.</span><span class="sxs-lookup"><span data-stu-id="2c83f-127">In this example, choose the newly created Accessorial master.</span></span>  
11. <span data-ttu-id="2c83f-128">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="2c83f-128">Click Save.</span></span>

## <a name="create-an-accessorial-assignment"></a><span data-ttu-id="2c83f-129">Creare un'assegnazione di spese accessorie</span><span class="sxs-lookup"><span data-stu-id="2c83f-129">Create an accessorial assignment</span></span>
1. <span data-ttu-id="2c83f-130">Fare clic su Assegnazioni spese accessorie.</span><span class="sxs-lookup"><span data-stu-id="2c83f-130">Click Accessorial assignments.</span></span>
2. <span data-ttu-id="2c83f-131">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="2c83f-131">Click New.</span></span>
3. <span data-ttu-id="2c83f-132">Digitare un valore nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="2c83f-132">In the Name field, type a value.</span></span>
4. <span data-ttu-id="2c83f-133">Attivare/disattivare l'espansione della sezione Criteri.</span><span class="sxs-lookup"><span data-stu-id="2c83f-133">Toggle the expansion of the Criteria section.</span></span>
    * <span data-ttu-id="2c83f-134">Nei criteri è possibile scegliere di applicare sempre il supplemento carburante, anche se per questo esempio è possibile scegliere di applica solo all'interno di un paese specifico.</span><span class="sxs-lookup"><span data-stu-id="2c83f-134">In the criteria, you can choose to always apply the fuel surcharge or for this example choose that it only applies within a certain region.</span></span>  
5. <span data-ttu-id="2c83f-135">Digitare un valore nel campo Da codice postale (CAP).</span><span class="sxs-lookup"><span data-stu-id="2c83f-135">In the ZIP/postal code from field, type a value.</span></span>
6. <span data-ttu-id="2c83f-136">Digitare un valore nel campo A codice postale (CAP).</span><span class="sxs-lookup"><span data-stu-id="2c83f-136">In the ZIP/postal code to field, type a value.</span></span>
7. <span data-ttu-id="2c83f-137">Attivare/disattivare l'espansione della sezione Calcolo.</span><span class="sxs-lookup"><span data-stu-id="2c83f-137">Toggle the expansion of the Calculation section.</span></span>
    * <span data-ttu-id="2c83f-138">Nella sezione di calcolo è possibile specificare la modalità di calcolo del supplemento carburante.</span><span class="sxs-lookup"><span data-stu-id="2c83f-138">In the calculation section you can specify how to calculate the fuel surcharge.</span></span> <span data-ttu-id="2c83f-139">Questo calcolo dipende dall'unità di spese accessorie scelta come base per il calcolo.</span><span class="sxs-lookup"><span data-stu-id="2c83f-139">This calculation depends on the Accessorial unit that you chose as the base for your calculation.</span></span>  
8. <span data-ttu-id="2c83f-140">Nel campo per il tipo di commissioni per le spese accessorie selezionare "Supplemento carburante".</span><span class="sxs-lookup"><span data-stu-id="2c83f-140">In the Accessorial fee type field, select 'Fuel surcharge'.</span></span>
9. <span data-ttu-id="2c83f-141">Nel campo Unità di spese accessorie selezionare "Chilometraggio".</span><span class="sxs-lookup"><span data-stu-id="2c83f-141">In the Accessorial unit field, select 'Mileage'.</span></span>
10. <span data-ttu-id="2c83f-142">Nel campo Paese fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="2c83f-142">In the Region field, click the drop-down button to open the lookup.</span></span>
11. <span data-ttu-id="2c83f-143">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="2c83f-143">In the list, click the link in the selected row.</span></span>
12. <span data-ttu-id="2c83f-144">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="2c83f-144">Click Save.</span></span>

## <a name="update-the-carrier-rating-profile"></a><span data-ttu-id="2c83f-145">Aggiornare il profilo di valutazione vettore</span><span class="sxs-lookup"><span data-stu-id="2c83f-145">Update the carrier rating profile</span></span>
1. <span data-ttu-id="2c83f-146">Andare a Gestione trasporto > Impostazioni > Vettori > Vettori spedizione.</span><span class="sxs-lookup"><span data-stu-id="2c83f-146">Go to Transportation management > Setup > Carriers > Shipping carriers.</span></span>
2. <span data-ttu-id="2c83f-147">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="2c83f-147">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="2c83f-148">Attivare/disattivare l'espansione della sezione Profili valutazione.</span><span class="sxs-lookup"><span data-stu-id="2c83f-148">Toggle the expansion of the Rating profiles section.</span></span>
4. <span data-ttu-id="2c83f-149">Fare clic su Modifica.</span><span class="sxs-lookup"><span data-stu-id="2c83f-149">Click Edit.</span></span>
5. <span data-ttu-id="2c83f-150">Nel campo Indice carburante vettore fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="2c83f-150">In the Carrier fuel index field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="2c83f-151">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="2c83f-151">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="2c83f-152">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="2c83f-152">Click Save.</span></span>


