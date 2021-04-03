---
title: Impostare i dati master tariffe
description: Questa procedura mostra come impostare dati master tariffe.
author: ShylaThompson
manager: tfehr
ms.date: 10/16/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TMSBreakMaster,TMSRateMaster,TMSRateMasterBase,TMSRateBaseType, TMSRouteWorkbench
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 77629cbaec4c4d4608b8941e55ab23a106d38727
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5233609"
---
# <a name="set-up-rate-masters"></a><span data-ttu-id="78a80-103">Impostare i dati master tariffe</span><span class="sxs-lookup"><span data-stu-id="78a80-103">Set up rate masters</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="78a80-104">Questa procedura mostra come impostare dati master tariffe.</span><span class="sxs-lookup"><span data-stu-id="78a80-104">This procedure shows you how to set up a rate master.</span></span> <span data-ttu-id="78a80-105">Il responsabile della logistica in genere imposta i dati master tariffe, a seconda dei contratti firmati con i vettori.</span><span class="sxs-lookup"><span data-stu-id="78a80-105">The logistic manager usually sets up rate masters, depending on the contracts signed with the carriers.</span></span> <span data-ttu-id="78a80-106">In questo scenario verranno impostati dati master per una compagnia aerea.</span><span class="sxs-lookup"><span data-stu-id="78a80-106">In this scenario you will set up a rate master for an air carrier.</span></span> <span data-ttu-id="78a80-107">La società di dati dimostrativi utilizzata per creare questa procedura è USMF.</span><span class="sxs-lookup"><span data-stu-id="78a80-107">The demo data company used to create this procedure is USMF.</span></span>

## <a name="set-up-break-master"></a><span data-ttu-id="78a80-108">Impostare i dati master di interruzione</span><span class="sxs-lookup"><span data-stu-id="78a80-108">Set up break master</span></span>

1. <span data-ttu-id="78a80-109">Passare a **Gestione trasporto > Impostazioni > Valutazione > Dati master di interruzione**.</span><span class="sxs-lookup"><span data-stu-id="78a80-109">Go to **Transportation management > Setup > Rating > Break master**.</span></span> <span data-ttu-id="78a80-110">I dati master di interruzione vengono utilizzati per definire la struttura dei prezzi e i relativi punti di interruzione.</span><span class="sxs-lookup"><span data-stu-id="78a80-110">Break masters are used to define the pricing structure and its breakpoints.</span></span> <span data-ttu-id="78a80-111">La struttura dei prezzi utilizza livelli di prezzo basati su dimensioni fisiche.</span><span class="sxs-lookup"><span data-stu-id="78a80-111">The pricing structure uses tiered pricing that is based on physical dimensions.</span></span>  
1. <span data-ttu-id="78a80-112">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="78a80-112">Select **New**.</span></span>
1. <span data-ttu-id="78a80-113">Nel campo **Dati master di interruzione** immettere un valore.</span><span class="sxs-lookup"><span data-stu-id="78a80-113">In the **Break master** field, enter a value.</span></span>
1. <span data-ttu-id="78a80-114">Nel campo **Nome** immettere un valore.</span><span class="sxs-lookup"><span data-stu-id="78a80-114">In the **Name** field, enter a value.</span></span>
1. <span data-ttu-id="78a80-115">Nel campo **Tipo di dati** selezionare il tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="78a80-115">In the **Data type** field, select the data type.</span></span>
1. <span data-ttu-id="78a80-116">Nel campo **Confronto** inserire il tipo di confronto richiesto (tramite operatori).</span><span class="sxs-lookup"><span data-stu-id="78a80-116">In the **Comparison** field, enter the kind of comparison requested (using operators).</span></span>
1. <span data-ttu-id="78a80-117">Nel campo **Unità di interruzione** immettere i valori dell'unità di interruzione.</span><span class="sxs-lookup"><span data-stu-id="78a80-117">In the **Break unit** field, enter the break unit.</span></span>
1. <span data-ttu-id="78a80-118">Nella sezione **Dettagli** creare tutte le interruzioni necessarie per la struttura dei prezzi.</span><span class="sxs-lookup"><span data-stu-id="78a80-118">In the **Details** section, create as many breaks as needed for the pricing structure.</span></span>
1. <span data-ttu-id="78a80-119">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="78a80-119">Select **Save**.</span></span>

## <a name="set-up-rate-master"></a><span data-ttu-id="78a80-120">Impostare dati master tariffe</span><span class="sxs-lookup"><span data-stu-id="78a80-120">Set up rate master</span></span>

1. <span data-ttu-id="78a80-121">Passare a **Gestione trasporto > Impostazioni > Valutazione > Tariffa principale**.</span><span class="sxs-lookup"><span data-stu-id="78a80-121">Go to **Transportation management > Setup > Rating > Rate master**.</span></span>
1. <span data-ttu-id="78a80-122">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="78a80-122">Select **New**.</span></span>
1. <span data-ttu-id="78a80-123">Digitare un valore nel campo **Tariffa principale**.</span><span class="sxs-lookup"><span data-stu-id="78a80-123">In the **Rate master** field, type a value.</span></span>
1. <span data-ttu-id="78a80-124">Digitare un valore nel campo **Nome**.</span><span class="sxs-lookup"><span data-stu-id="78a80-124">In the **Name** field, type a value.</span></span>
1. <span data-ttu-id="78a80-125">Nel campo **ID di valutazione dei metadati** selezionare il pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="78a80-125">In the **Rating metadata ID** field, select the drop-down button to open the lookup.</span></span> <span data-ttu-id="78a80-126">L'ID dei metadati di valutazione determinerà i dati necessari per i dati master tariffe, perché definisce i metadati previsti dal motore di gestione trasporto che utilizza tali dati master.</span><span class="sxs-lookup"><span data-stu-id="78a80-126">The rating metadata ID will determine the data needed for the rate master, as it defines the metadata expected by the transportation management engine using this rate master.</span></span>  
1. <span data-ttu-id="78a80-127">Per questo esempio, selezionare l'opzione P2P.</span><span class="sxs-lookup"><span data-stu-id="78a80-127">For this example, select the P2P option.</span></span> <span data-ttu-id="78a80-128">Questa è già definita nei dati della demo.</span><span class="sxs-lookup"><span data-stu-id="78a80-128">This is already defined in the demo data.</span></span>
1. <span data-ttu-id="78a80-129">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="78a80-129">In the list, select the link in the selected row.</span></span>
1. <span data-ttu-id="78a80-130">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="78a80-130">Select **Save**.</span></span>

## <a name="set-up-rate-base"></a><span data-ttu-id="78a80-131">Impostare una base tariffa</span><span class="sxs-lookup"><span data-stu-id="78a80-131">Set up rate base</span></span>

1. <span data-ttu-id="78a80-132">Selezionare la **base della tariffa**.</span><span class="sxs-lookup"><span data-stu-id="78a80-132">Select **Rate base**.</span></span>
    * <span data-ttu-id="78a80-133">La base della tariffa determina la tariffa del vettore e può essere utilizzata per impostare una struttura tariffaria perché organizza le tariffe in punti di interruzione definiti nei dati master di interruzione.</span><span class="sxs-lookup"><span data-stu-id="78a80-133">The rate base determines the rate of the carrier, and can be used to set up a tariff structure as it structures the rates in the breakpoints defined in the break master.</span></span>  
2. <span data-ttu-id="78a80-134">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="78a80-134">Select **New**.</span></span>
3. <span data-ttu-id="78a80-135">Digitare un valore nel campo **Base tariffa**.</span><span class="sxs-lookup"><span data-stu-id="78a80-135">In the **Rate base** field, type a value.</span></span>
4. <span data-ttu-id="78a80-136">Digitare un valore nel campo **Nome**.</span><span class="sxs-lookup"><span data-stu-id="78a80-136">In the **Name** field, type a value.</span></span>
5. <span data-ttu-id="78a80-137">Nel campo **Dati master di interruzione** selezionare il pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="78a80-137">In the **Break master** field, select the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="78a80-138">I dati master di interruzione vengono utilizzati per definire la struttura dei prezzi e i relativi punti di interruzione.</span><span class="sxs-lookup"><span data-stu-id="78a80-138">Break masters are used to define the pricing structure and its breakpoints.</span></span> <span data-ttu-id="78a80-139">La struttura dei prezzi utilizza livelli di prezzo basati su dimensioni fisiche.</span><span class="sxs-lookup"><span data-stu-id="78a80-139">The pricing structure uses tiered pricing that is based on physical dimensions.</span></span>  
6. <span data-ttu-id="78a80-140">Per questo esempio, utilizzare il peso.</span><span class="sxs-lookup"><span data-stu-id="78a80-140">For this example, use weight.</span></span> <span data-ttu-id="78a80-141">Questa è già definita nei dati della demo.</span><span class="sxs-lookup"><span data-stu-id="78a80-141">This is already defined in the demo data.</span></span>
7. <span data-ttu-id="78a80-142">Nell'elenco fare clic sul collegamento nella riga evidenziata.</span><span class="sxs-lookup"><span data-stu-id="78a80-142">In the list, select the link in the highlighted row.</span></span>
8. <span data-ttu-id="78a80-143">Espandere la sezione **Dettagli**.</span><span class="sxs-lookup"><span data-stu-id="78a80-143">Expand the **Details** section.</span></span>
9. <span data-ttu-id="78a80-144">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="78a80-144">Select **New**.</span></span>
10. <span data-ttu-id="78a80-145">Nel campo **CAP consegna da** digitare "30301".</span><span class="sxs-lookup"><span data-stu-id="78a80-145">In the **Drop-off Postal Code From** field, type "30301".</span></span>
11. <span data-ttu-id="78a80-146">Nel campo **CAP consegna a** digitare "30318".</span><span class="sxs-lookup"><span data-stu-id="78a80-146">In the **Drop-off Postal Code To** field, type "30318".</span></span>
12. <span data-ttu-id="78a80-147">Nel campo **Paese consegna** digitare "USA".</span><span class="sxs-lookup"><span data-stu-id="78a80-147">In the **Drop-off Country Region** field, type "USA".</span></span>
13. <span data-ttu-id="78a80-148">Nel campo **<1,00 kg**, digitare "100".</span><span class="sxs-lookup"><span data-stu-id="78a80-148">In the **<1.00 Lbs** field, type "100".</span></span>
    * <span data-ttu-id="78a80-149">Inserire la tariffa per chilogrammi se il peso totale del carico è inferiore a 1 chilogrammo.</span><span class="sxs-lookup"><span data-stu-id="78a80-149">Insert the rate per pounds if the total weight of the load is less than 1 pound.</span></span>  
14. <span data-ttu-id="78a80-150">Nel campo **<5,00 kg**, digitare "300".</span><span class="sxs-lookup"><span data-stu-id="78a80-150">In the **<5.00 Lbs** field, type "300".</span></span>
    * <span data-ttu-id="78a80-151">Inserire la tariffa per chilogrammi se il peso totale del carico è inferiore a 5 chilogrammi.</span><span class="sxs-lookup"><span data-stu-id="78a80-151">Insert the rate per pounds if the total weight of the load is less than 5 pounds.</span></span>  
15. <span data-ttu-id="78a80-152">Nel campo **<20,00 kg**, digitare "500".</span><span class="sxs-lookup"><span data-stu-id="78a80-152">In the **<20.00 Lbs** field, type "500".</span></span>
    * <span data-ttu-id="78a80-153">Inserire la tariffa per chilogrammi se il peso totale del carico è inferiore a 20 chilogrammi.</span><span class="sxs-lookup"><span data-stu-id="78a80-153">Insert the rate per pounds if the total weight of the load is less than 20 pounds.</span></span>  
16. <span data-ttu-id="78a80-154">Nel campo **<100,00 kg**, digitare "1000".</span><span class="sxs-lookup"><span data-stu-id="78a80-154">In the **<100.00 Lbs** field, type "1000".</span></span>
    * <span data-ttu-id="78a80-155">Inserire la tariffa per chilogrammi se il peso totale del carico è inferiore a 100 chilogrammi.</span><span class="sxs-lookup"><span data-stu-id="78a80-155">Insert the rate per pounds if the total weight of the load is less than 100 pounds.</span></span>  
17. <span data-ttu-id="78a80-156">Nel campo **<1.000,00 kg**, digitare "3000".</span><span class="sxs-lookup"><span data-stu-id="78a80-156">In the **<1,000.00 Lbs** field, type "3000".</span></span>
    * <span data-ttu-id="78a80-157">Inserire la tariffa per chilogrammi se il peso totale del carico è inferiore a 1000 chilogrammi.</span><span class="sxs-lookup"><span data-stu-id="78a80-157">Insert the rate per pounds if the total weight of the load is less than 1000 pounds.</span></span>  
18. <span data-ttu-id="78a80-158">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="78a80-158">Select **Save**.</span></span>
19. <span data-ttu-id="78a80-159">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="78a80-159">Close the page.</span></span>

## <a name="assign-rate-base"></a><span data-ttu-id="78a80-160">Assegnare una base tariffa</span><span class="sxs-lookup"><span data-stu-id="78a80-160">Assign rate base</span></span>

1. <span data-ttu-id="78a80-161">Espandere la sezione **Assegnazioni base tariffa**.</span><span class="sxs-lookup"><span data-stu-id="78a80-161">Expand the **Rate base assignments** section.</span></span>
2. <span data-ttu-id="78a80-162">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="78a80-162">Select **New**.</span></span>
    * <span data-ttu-id="78a80-163">È possibile includere più assegnazioni di base della tariffa per ogni dato master tariffa.</span><span class="sxs-lookup"><span data-stu-id="78a80-163">You can have several rate base assignments for each rate master.</span></span> <span data-ttu-id="78a80-164">Ciò consente di creare prezzi diversi per ogni vettore a seconda delle destinazioni, dei servizi e delle diverse basi di tariffa.</span><span class="sxs-lookup"><span data-stu-id="78a80-164">This makes it possible to create several different price points for each carrier depending on destinations, services, or different rate bases.</span></span> <span data-ttu-id="78a80-165">In questa procedura verrà creata solo un'assegnazione di base della tariffa.</span><span class="sxs-lookup"><span data-stu-id="78a80-165">In this procedure you will only create one rate base assignment.</span></span>  
3. <span data-ttu-id="78a80-166">Digitare un valore nel campo **Nome**.</span><span class="sxs-lookup"><span data-stu-id="78a80-166">In the **Name** field, type a value.</span></span>
4. <span data-ttu-id="78a80-167">Nel campo **Base tariffa** selezionare il pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="78a80-167">In the **Rate base** field, select the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="78a80-168">Nell'elenco fare clic sul collegamento nella riga evidenziata.</span><span class="sxs-lookup"><span data-stu-id="78a80-168">In the list, select the link in the highlighted row.</span></span>
6. <span data-ttu-id="78a80-169">Nel campo **Servizio** selezionare il pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="78a80-169">In the **Service** field, select the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="78a80-170">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="78a80-170">In the list, find and select the desired record.</span></span>
8. <span data-ttu-id="78a80-171">Nell'elenco fare clic sul collegamento nella riga evidenziata.</span><span class="sxs-lookup"><span data-stu-id="78a80-171">In the list, select the link in the highlighted row.</span></span>
9. <span data-ttu-id="78a80-172">Nel campo **CAP prelievo** digitare "98052".</span><span class="sxs-lookup"><span data-stu-id="78a80-172">In the **Pick-up Postal Code** field, type "98052".</span></span>
    * <span data-ttu-id="78a80-173">Specificare il codice postale da cui questa assegnazione di base della tariffa deve essere valida.</span><span class="sxs-lookup"><span data-stu-id="78a80-173">Specify which postal code this rate base assignment should be valid from.</span></span>
10. <span data-ttu-id="78a80-174">Nel campo **Paese prelievo** digitare "USA".</span><span class="sxs-lookup"><span data-stu-id="78a80-174">In the **Pick-up Country Region** field, type "USA".</span></span>
11. <span data-ttu-id="78a80-175">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="78a80-175">Select **Save**.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]