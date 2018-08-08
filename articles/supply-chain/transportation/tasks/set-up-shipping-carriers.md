--- 
title: Impostare vettori di spedizione
description: "Questa procedura descrive come impostare un vettore di spedizione e come definire dettagli quali servizio, modalità di spedizione, metodo di pagamento del trasporto, vincoli di trasporto e tariffa di trasporto."
author: ShylaThompson
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: 6c5ac13d17c97f20ee79e7faf57c570f02158424
ms.contentlocale: it-it
ms.lasthandoff: 08/07/2018

---
# <a name="set-up-shipping-carriers"></a><span data-ttu-id="30aaf-103">Impostare vettori di spedizione</span><span class="sxs-lookup"><span data-stu-id="30aaf-103">Set up shipping carriers</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="30aaf-104">Questa procedura descrive come impostare un vettore di spedizione e come definire dettagli quali servizio, modalità di spedizione, metodo di pagamento del trasporto, vincoli di trasporto e tariffa di trasporto.</span><span class="sxs-lookup"><span data-stu-id="30aaf-104">This procedure shows how to set up a shipping carrier and define details such as service, shipment mode, transportation tender, transportation constraints, and shipping rate.</span></span> <span data-ttu-id="30aaf-105">Un coordinatore dei trasporti può quindi assegnare un vettore di spedizione a un carico in entrata o in uscita.</span><span class="sxs-lookup"><span data-stu-id="30aaf-105">A transportation coordinator can then assign a shipping carrier to an inbound or outbound load.</span></span>


## <a name="create-a-new-shipping-carrier"></a><span data-ttu-id="30aaf-106">Creare un nuovo vettore di spedizione</span><span class="sxs-lookup"><span data-stu-id="30aaf-106">Create a new shipping carrier</span></span>
1. <span data-ttu-id="30aaf-107">Andare a Gestione trasporto > Impostazioni > Vettori > Vettori spedizione.</span><span class="sxs-lookup"><span data-stu-id="30aaf-107">Go to Transportation management > Setup > Carriers > Shipping carriers.</span></span>
2. <span data-ttu-id="30aaf-108">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="30aaf-108">Click New.</span></span>
3. <span data-ttu-id="30aaf-109">Nel campo Vettore spedizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="30aaf-109">In the Shipping carrier field, type a value.</span></span>
4. <span data-ttu-id="30aaf-110">Digitare un valore nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="30aaf-110">In the Name field, type a value.</span></span>
5. <span data-ttu-id="30aaf-111">Nel campo Modalità fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="30aaf-111">In the Mode field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="30aaf-112">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="30aaf-112">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="30aaf-113">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="30aaf-113">In the list, click the link in the selected row.</span></span>

## <a name="fill-in-the-general-information-for-the-shipping-carrier"></a><span data-ttu-id="30aaf-114">Inserire le informazioni generali per il vettore di spedizione</span><span class="sxs-lookup"><span data-stu-id="30aaf-114">Fill in the general information for the shipping carrier</span></span>
1. <span data-ttu-id="30aaf-115">Attivare/disattivare l'espansione della sezione Panoramica.</span><span class="sxs-lookup"><span data-stu-id="30aaf-115">Toggle the expansion of the Overview section.</span></span>
2. <span data-ttu-id="30aaf-116">Selezionare o deselezionare la casella di controllo Attiva vettore di spedizione.</span><span class="sxs-lookup"><span data-stu-id="30aaf-116">Check or uncheck the Activate shipping carrier checkbox.</span></span>
3. <span data-ttu-id="30aaf-117">Nel campo Fornitore fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="30aaf-117">In the Vendor field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="30aaf-118">Selezionare il conto fornitore a cui assegnare il vettore di spedizione.</span><span class="sxs-lookup"><span data-stu-id="30aaf-118">Select the vendor account to assign the shipping carrier to.</span></span>  
4. <span data-ttu-id="30aaf-119">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="30aaf-119">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="30aaf-120">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="30aaf-120">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="30aaf-121">Nel campo Tipo di pagamento trasporto selezionare un'opzione.</span><span class="sxs-lookup"><span data-stu-id="30aaf-121">In the Transportation tender type field, select an option.</span></span>
    * <span data-ttu-id="30aaf-122">Selezionare Manuale per utilizzare la pagina Metodo di pagamento trasporto o selezionare EDI per aggiornare il metodo di pagamento utilizzando il formato EDI (Electronic Data Interchange).</span><span class="sxs-lookup"><span data-stu-id="30aaf-122">Select Manual to use the Transportation Tender page, or select EDI to update the tender by using Electronic Data Interchange (EDI).</span></span>  
7. <span data-ttu-id="30aaf-123">Selezionare o deselezionare la casella di controllo Attiva valutazione vettore.</span><span class="sxs-lookup"><span data-stu-id="30aaf-123">Check or uncheck the Activate carrier rating checkbox.</span></span>

## <a name="create-the-necessary-services-for-the-shipping-carrier"></a><span data-ttu-id="30aaf-124">Creare i servizi necessari per il vettore di spedizione</span><span class="sxs-lookup"><span data-stu-id="30aaf-124">Create the necessary services for the shipping carrier</span></span>
1. <span data-ttu-id="30aaf-125">Attivare/disattivare l'espansione della sezione Servizi.</span><span class="sxs-lookup"><span data-stu-id="30aaf-125">Toggle the expansion of the Services section.</span></span>
2. <span data-ttu-id="30aaf-126">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="30aaf-126">Click New.</span></span>
3. <span data-ttu-id="30aaf-127">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="30aaf-127">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="30aaf-128">Nel campo Servizio trasporto digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="30aaf-128">In the Carrier service field, type a value.</span></span>
5. <span data-ttu-id="30aaf-129">Digitare un valore nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="30aaf-129">In the Name field, type a value.</span></span>
6. <span data-ttu-id="30aaf-130">Nel campo Metodo di trasporto fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="30aaf-130">In the Transportation method field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="30aaf-131">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="30aaf-131">In the list, find and select the desired record.</span></span>
8. <span data-ttu-id="30aaf-132">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="30aaf-132">In the list, click the link in the selected row.</span></span>

## <a name="set-up-the-address-for-the-carrier-optional"></a><span data-ttu-id="30aaf-133">Impostare l'indirizzo del vettore (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="30aaf-133">Set up the address for the carrier (optional)</span></span>
1. <span data-ttu-id="30aaf-134">Attiva/disattiva l'espansione della sezione Indirizzi.</span><span class="sxs-lookup"><span data-stu-id="30aaf-134">Toggle the expansion of the Addresses section.</span></span>
2. <span data-ttu-id="30aaf-135">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="30aaf-135">Click New.</span></span>
3. <span data-ttu-id="30aaf-136">Digitare un valore nel campo Nome o Descrizione.</span><span class="sxs-lookup"><span data-stu-id="30aaf-136">In the Name or description field, type a value.</span></span>
4. <span data-ttu-id="30aaf-137">Nel campo Paese fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="30aaf-137">In the Country/region field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="30aaf-138">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="30aaf-138">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="30aaf-139">Nel campo Codice postale (CAP) fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="30aaf-139">In the ZIP/postal code field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="30aaf-140">Trovare e selezionare il record desiderato nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="30aaf-140">In the list, find and select the desired record.</span></span>
8. <span data-ttu-id="30aaf-141">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="30aaf-141">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="30aaf-142">Digitare un valore nel campo Via.</span><span class="sxs-lookup"><span data-stu-id="30aaf-142">In the Street field, type a value.</span></span>
10. <span data-ttu-id="30aaf-143">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="30aaf-143">Click OK.</span></span>

## <a name="set-up-the-rating-profile-for-the-shipping-carrier"></a><span data-ttu-id="30aaf-144">Impostare il profilo di valutazione per il vettore di spedizione</span><span class="sxs-lookup"><span data-stu-id="30aaf-144">Set up the rating profile for the shipping carrier</span></span>
1. <span data-ttu-id="30aaf-145">Attivare/disattivare l'espansione della sezione Profili valutazione.</span><span class="sxs-lookup"><span data-stu-id="30aaf-145">Toggle the expansion of the Rating profiles section.</span></span>
2. <span data-ttu-id="30aaf-146">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="30aaf-146">Click New.</span></span>
3. <span data-ttu-id="30aaf-147">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="30aaf-147">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="30aaf-148">Nel campo Profilo valutazione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="30aaf-148">In the Rating profile field, type a value.</span></span>
5. <span data-ttu-id="30aaf-149">Digitare un valore nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="30aaf-149">In the Name field, type a value.</span></span>
6. <span data-ttu-id="30aaf-150">Nel campo Sito fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="30aaf-150">In the Site field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="30aaf-151">Trovare e selezionare il record desiderato nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="30aaf-151">In the list, find and select the desired record.</span></span>
8. <span data-ttu-id="30aaf-152">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="30aaf-152">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="30aaf-153">Nel campo Magazzino fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="30aaf-153">In the Warehouse field, click the drop-down button to open the lookup.</span></span>
10. <span data-ttu-id="30aaf-154">Trovare e selezionare il record desiderato nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="30aaf-154">In the list, find and select the desired record.</span></span>
11. <span data-ttu-id="30aaf-155">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="30aaf-155">In the list, click the link in the selected row.</span></span>
12. <span data-ttu-id="30aaf-156">Nel campo Motore tariffe fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="30aaf-156">In the Rate engine field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="30aaf-157">Selezionare il motore tariffe in base al contratto stipulato con il vettore.</span><span class="sxs-lookup"><span data-stu-id="30aaf-157">Select the Rate engine that is in accordance with the contract that you have with the carrier.</span></span>  
13. <span data-ttu-id="30aaf-158">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="30aaf-158">In the list, find and select the desired record.</span></span>
14. <span data-ttu-id="30aaf-159">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="30aaf-159">In the list, click the link in the selected row.</span></span>
15. <span data-ttu-id="30aaf-160">Nel campo Tariffa principale fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="30aaf-160">In the Rate master field, click the drop-down button to open the lookup.</span></span>
16. <span data-ttu-id="30aaf-161">Trovare e selezionare il record desiderato nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="30aaf-161">In the list, find and select the desired record.</span></span>
17. <span data-ttu-id="30aaf-162">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="30aaf-162">In the list, click the link in the selected row.</span></span>
18. <span data-ttu-id="30aaf-163">Nel campo Motore tempo di transito fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="30aaf-163">In the Transit time engine field, click the drop-down button to open the lookup.</span></span>
19. <span data-ttu-id="30aaf-164">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="30aaf-164">In the list, click the link in the selected row.</span></span>
20. <span data-ttu-id="30aaf-165">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="30aaf-165">Click Save.</span></span>


