--- 
title: Impostare i dati master tariffe
description: Questa procedura mostra come impostare dati master tariffe.
author: BibiSp
manager: AnnBe
ms.date: 11/11/2016
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
ms.openlocfilehash: b7c02e5a6f5eeee270ca4b6f91e90f7799c2ca11
ms.contentlocale: it-it
ms.lasthandoff: 08/29/2017

---
# <a name="set-up-rate-masters"></a><span data-ttu-id="b304b-103">Impostare i dati master tariffe</span><span class="sxs-lookup"><span data-stu-id="b304b-103">Set up rate masters</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="b304b-104">Questa procedura mostra come impostare dati master tariffe.</span><span class="sxs-lookup"><span data-stu-id="b304b-104">This procedure shows you how to set up a rate master.</span></span> <span data-ttu-id="b304b-105">Il responsabile della logistica in genere imposta i dati master tariffe, a seconda dei contratti firmati con i vettori.</span><span class="sxs-lookup"><span data-stu-id="b304b-105">The logistic manager usually sets up rate masters, depending on the contracts signed with the carriers.</span></span> <span data-ttu-id="b304b-106">In questo scenario verranno impostati dati master per una compagnia aerea.</span><span class="sxs-lookup"><span data-stu-id="b304b-106">In this scenario you will set up a rate master for an air carrier.</span></span> <span data-ttu-id="b304b-107">La società di dati dimostrativi utilizzata per creare questa procedura è USMF.</span><span class="sxs-lookup"><span data-stu-id="b304b-107">The demo data company used to create this procedure is USMF.</span></span>


## <a name="set-up-rate-master"></a><span data-ttu-id="b304b-108">Impostare dati master tariffe</span><span class="sxs-lookup"><span data-stu-id="b304b-108">Set up rate master</span></span>
1. <span data-ttu-id="b304b-109">Passare a Gestione trasporto > Impostazioni > Valutazione > Tariffa principale.</span><span class="sxs-lookup"><span data-stu-id="b304b-109">Go to Transportation management > Setup > Rating > Rate master.</span></span>
2. <span data-ttu-id="b304b-110">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="b304b-110">Click New.</span></span>
3. <span data-ttu-id="b304b-111">Digitare un valore nel campo Tariffa principale.</span><span class="sxs-lookup"><span data-stu-id="b304b-111">In the Rate master field, type a value.</span></span>
4. <span data-ttu-id="b304b-112">Digitare un valore nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="b304b-112">In the Name field, type a value.</span></span>
5. <span data-ttu-id="b304b-113">Nel campo dell'ID di valutazione dei metadati fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="b304b-113">In the Rating metadata ID field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="b304b-114">L'ID dei metadati di valutazione determinerà i dati necessari per i dati master tariffe, perché definisce i metadati previsti dal motore TMS che utilizza tali dati master.</span><span class="sxs-lookup"><span data-stu-id="b304b-114">The rating metadata ID will determine the data needed for the rate master, as it defines the metadata expected by the TMS engine using this rate master.</span></span>  
6. <span data-ttu-id="b304b-115">Per questo esempio, selezionare l'opzione P2P</span><span class="sxs-lookup"><span data-stu-id="b304b-115">For this example, select the P2P option</span></span>
7. <span data-ttu-id="b304b-116">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="b304b-116">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="b304b-117">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="b304b-117">Click Save.</span></span>

## <a name="set-up-rate-base"></a><span data-ttu-id="b304b-118">Impostare una base tariffa</span><span class="sxs-lookup"><span data-stu-id="b304b-118">Set up rate base</span></span>
1. <span data-ttu-id="b304b-119">Fare clic su Base tariffa.</span><span class="sxs-lookup"><span data-stu-id="b304b-119">Click Rate base.</span></span>
    * <span data-ttu-id="b304b-120">La base della tariffa determina la tariffa del vettore e può essere utilizzata per impostare una struttura tariffaria perché organizza le tariffe in punti di interruzione definiti nei dati master di interruzione.</span><span class="sxs-lookup"><span data-stu-id="b304b-120">The rate base determines the rate of the carrier, and can be used to set up a tariff structure as it structures the rates in the breakpoints defined in the break master.</span></span>  
2. <span data-ttu-id="b304b-121">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="b304b-121">Click New.</span></span>
3. <span data-ttu-id="b304b-122">Digitare un valore nel campo Base tariffa.</span><span class="sxs-lookup"><span data-stu-id="b304b-122">In the Rate base field, type a value.</span></span>
4. <span data-ttu-id="b304b-123">Digitare un valore nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="b304b-123">In the Name field, type a value.</span></span>
5. <span data-ttu-id="b304b-124">Nel campo Interruzione principale fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="b304b-124">In the Break master field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="b304b-125">I dati master di interruzione vengono utilizzati per definire la struttura dei prezzi e i relativi punti di interruzione.</span><span class="sxs-lookup"><span data-stu-id="b304b-125">Break masters are used to define the pricing structure and its breakpoints.</span></span> <span data-ttu-id="b304b-126">La struttura dei prezzi utilizza livelli di prezzo basati su dimensioni fisiche.</span><span class="sxs-lookup"><span data-stu-id="b304b-126">The pricing structure uses tiered pricing that is based on physical dimensions.</span></span>  
6. <span data-ttu-id="b304b-127">Per questo esempio, utilizzare il peso</span><span class="sxs-lookup"><span data-stu-id="b304b-127">For this example, use weight</span></span>
7. <span data-ttu-id="b304b-128">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="b304b-128">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="b304b-129">Attivare/disattivare l'espansione della sezione Dettagli.</span><span class="sxs-lookup"><span data-stu-id="b304b-129">Toggle the expansion of the Details section.</span></span>
9. <span data-ttu-id="b304b-130">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="b304b-130">Click New.</span></span>
10. <span data-ttu-id="b304b-131">Nel campo CAP consegna da digitare "30301".</span><span class="sxs-lookup"><span data-stu-id="b304b-131">In the Drop-off Postal Code From field, type '30301'.</span></span>
11. <span data-ttu-id="b304b-132">Nel campo CAP consegna A digitare "30318".</span><span class="sxs-lookup"><span data-stu-id="b304b-132">In the Drop-off Postal Code To field, type '30318'.</span></span>
12. <span data-ttu-id="b304b-133">Nel campo Paese consegna digitare "USA".</span><span class="sxs-lookup"><span data-stu-id="b304b-133">In the Drop-off Country Region field, type 'USA'.</span></span>
13. <span data-ttu-id="b304b-134">Nel campo <1,00 kg, digitare '100'.</span><span class="sxs-lookup"><span data-stu-id="b304b-134">In the <1.00 Lbs field, type '100'.</span></span>
    * <span data-ttu-id="b304b-135">Inserire la tariffa per chilogrammi se il peso totale del carico è inferiore a 1 chilogrammo.</span><span class="sxs-lookup"><span data-stu-id="b304b-135">Insert the rate per lbs if the total weight of the load is less than 1 pound.</span></span>  
14. <span data-ttu-id="b304b-136">Nel campo <5,00 kg digitare "300".</span><span class="sxs-lookup"><span data-stu-id="b304b-136">In the <5.00 Lbs field, type '300'.</span></span>
    * <span data-ttu-id="b304b-137">Inserire la tariffa per chilogrammi se il peso totale del carico è inferiore a 5 chilogrammi.</span><span class="sxs-lookup"><span data-stu-id="b304b-137">Insert the rate per lbs if the total weight of the load is less than 5 pounds.</span></span>  
15. <span data-ttu-id="b304b-138">Nel campo <20,00 kg digitare "500".</span><span class="sxs-lookup"><span data-stu-id="b304b-138">In the <20.00 Lbs field, type '500'.</span></span>
    * <span data-ttu-id="b304b-139">Inserire la tariffa per chilogrammi se il peso totale del carico è inferiore a 20 chilogrammi.</span><span class="sxs-lookup"><span data-stu-id="b304b-139">Insert the rate per lbs if the total weight of the load is less than 20 pounds.</span></span>  
16. <span data-ttu-id="b304b-140">Nel campo <100,00 kg digitare "1000".</span><span class="sxs-lookup"><span data-stu-id="b304b-140">In the <100.00 Lbs field, type '1000'.</span></span>
    * <span data-ttu-id="b304b-141">Inserire la tariffa per chilogrammi se il peso totale del carico è inferiore a 100 chilogrammi.</span><span class="sxs-lookup"><span data-stu-id="b304b-141">Insert the rate per lbs if the total weight of the load is less than 100 pounds.</span></span>  
17. <span data-ttu-id="b304b-142">Nel campo <1.000,00 kg digitare "3000".</span><span class="sxs-lookup"><span data-stu-id="b304b-142">In the <1,000.00 Lbs field, type '3000'.</span></span>
    * <span data-ttu-id="b304b-143">Inserire la tariffa per chilogrammi se il peso totale del carico è inferiore a 1000 chilogrammi.</span><span class="sxs-lookup"><span data-stu-id="b304b-143">Insert the rate per lbs if the total weight of the load is less than 1000 pounds.</span></span>  
18. <span data-ttu-id="b304b-144">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="b304b-144">Click Save.</span></span>
19. <span data-ttu-id="b304b-145">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="b304b-145">Close the page.</span></span>

## <a name="assign-rate-base"></a><span data-ttu-id="b304b-146">Assegnare una base tariffa</span><span class="sxs-lookup"><span data-stu-id="b304b-146">Assign rate base</span></span>
1. <span data-ttu-id="b304b-147">Attivare/disattivare l'espansione della sezione Assegnazioni base tariffa.</span><span class="sxs-lookup"><span data-stu-id="b304b-147">Toggle the expansion of the Rate base assignments section.</span></span>
2. <span data-ttu-id="b304b-148">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="b304b-148">Click New.</span></span>
    * <span data-ttu-id="b304b-149">È possibile includere più assegnazioni di base della tariffa per ogni dato master tariffa.</span><span class="sxs-lookup"><span data-stu-id="b304b-149">You can have several rate base assignments for each rate master.</span></span> <span data-ttu-id="b304b-150">Ciò consente di creare prezzi diversi per ogni vettore a seconda delle destinazioni, dei servizi e delle diverse basi di tariffa.</span><span class="sxs-lookup"><span data-stu-id="b304b-150">This makes it possible to create several different price points for each carrier depending on destinations, services, or different rate bases.</span></span> <span data-ttu-id="b304b-151">In questa procedura verrà creata solo un'assegnazione di base della tariffa.</span><span class="sxs-lookup"><span data-stu-id="b304b-151">In this procedure you will only create one rate base assignment.</span></span>  
3. <span data-ttu-id="b304b-152">Digitare un valore nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="b304b-152">In the Name field, type a value.</span></span>
4. <span data-ttu-id="b304b-153">Nel campo Base tariffa fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="b304b-153">In the Rate base field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="b304b-154">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="b304b-154">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="b304b-155">Nel campo Servizio fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="b304b-155">In the Service field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="b304b-156">Trovare e selezionare il record desiderato nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="b304b-156">In the list, find and select the desired record.</span></span>
8. <span data-ttu-id="b304b-157">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="b304b-157">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="b304b-158">Nel campo CAP prelievo digitare "98052".</span><span class="sxs-lookup"><span data-stu-id="b304b-158">In the Pick-up Postal Code field, type '98052'.</span></span>
    * <span data-ttu-id="b304b-159">Specificare il codice postale da cui questa assegnazione di base della tariffa deve essere valida.</span><span class="sxs-lookup"><span data-stu-id="b304b-159">Specify which postal code this rate base assignment should be valid from.</span></span>    
10. <span data-ttu-id="b304b-160">Nel campo Paese prelievo digitare "USA".</span><span class="sxs-lookup"><span data-stu-id="b304b-160">In the Pick-up Country Region field, type 'USA'.</span></span>
11. <span data-ttu-id="b304b-161">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="b304b-161">Click Save.</span></span>

