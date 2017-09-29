--- 
title: Impostare vettori di spedizione
description: "Questa procedura descrive come impostare un vettore di spedizione e come definire dettagli quali servizio, modalità di spedizione, metodo di pagamento del trasporto, vincoli di trasporto e tariffa di trasporto."
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
ms.openlocfilehash: e27be049bebd63c9266029b8981874417a9f0a8c
ms.contentlocale: it-it
ms.lasthandoff: 08/29/2017

---
# <a name="set-up-shipping-carriers"></a><span data-ttu-id="df60f-103">Impostare vettori di spedizione</span><span class="sxs-lookup"><span data-stu-id="df60f-103">Set up shipping carriers</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="df60f-104">Questa procedura descrive come impostare un vettore di spedizione e come definire dettagli quali servizio, modalità di spedizione, metodo di pagamento del trasporto, vincoli di trasporto e tariffa di trasporto.</span><span class="sxs-lookup"><span data-stu-id="df60f-104">This procedure shows how to set up a shipping carrier and define details such as service, shipment mode, transportation tender, transportation constraints, and shipping rate.</span></span> <span data-ttu-id="df60f-105">Un coordinatore dei trasporti può quindi assegnare un vettore di spedizione a un carico in entrata o in uscita.</span><span class="sxs-lookup"><span data-stu-id="df60f-105">A transportation coordinator can then assign a shipping carrier to an inbound or outbound load.</span></span>


## <a name="create-a-new-shipping-carrier"></a><span data-ttu-id="df60f-106">Creare un nuovo vettore di spedizione</span><span class="sxs-lookup"><span data-stu-id="df60f-106">Create a new shipping carrier</span></span>
1. <span data-ttu-id="df60f-107">Andare a Gestione trasporto > Impostazioni > Vettori > Vettori spedizione.</span><span class="sxs-lookup"><span data-stu-id="df60f-107">Go to Transportation management > Setup > Carriers > Shipping carriers.</span></span>
2. <span data-ttu-id="df60f-108">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="df60f-108">Click New.</span></span>
3. <span data-ttu-id="df60f-109">Nel campo Vettore spedizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="df60f-109">In the Shipping carrier field, type a value.</span></span>
4. <span data-ttu-id="df60f-110">Digitare un valore nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="df60f-110">In the Name field, type a value.</span></span>
5. <span data-ttu-id="df60f-111">Nel campo Modalità fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="df60f-111">In the Mode field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="df60f-112">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="df60f-112">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="df60f-113">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="df60f-113">In the list, click the link in the selected row.</span></span>

## <a name="fill-in-the-general-information-for-the-shipping-carrier"></a><span data-ttu-id="df60f-114">Inserire le informazioni generali per il vettore di spedizione</span><span class="sxs-lookup"><span data-stu-id="df60f-114">Fill in the general information for the shipping carrier</span></span>
1. <span data-ttu-id="df60f-115">Attivare/disattivare l'espansione della sezione Panoramica.</span><span class="sxs-lookup"><span data-stu-id="df60f-115">Toggle the expansion of the Overview section.</span></span>
2. <span data-ttu-id="df60f-116">Selezionare o deselezionare la casella di controllo Attiva vettore di spedizione.</span><span class="sxs-lookup"><span data-stu-id="df60f-116">Check or uncheck the Activate shipping carrier checkbox.</span></span>
3. <span data-ttu-id="df60f-117">Nel campo Fornitore fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="df60f-117">In the Vendor field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="df60f-118">Selezionare il conto fornitore a cui assegnare il vettore di spedizione.</span><span class="sxs-lookup"><span data-stu-id="df60f-118">Select the vendor account to assign the shipping carrier to.</span></span>  
4. <span data-ttu-id="df60f-119">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="df60f-119">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="df60f-120">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="df60f-120">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="df60f-121">Nel campo Tipo di pagamento trasporto selezionare un'opzione.</span><span class="sxs-lookup"><span data-stu-id="df60f-121">In the Transportation tender type field, select an option.</span></span>
    * <span data-ttu-id="df60f-122">Selezionare Manuale per utilizzare la pagina Metodo di pagamento trasporto o selezionare EDI per aggiornare il metodo di pagamento utilizzando il formato EDI (Electronic Data Interchange).</span><span class="sxs-lookup"><span data-stu-id="df60f-122">Select Manual to use the Transportation Tender page, or select EDI to update the tender by using Electronic Data Interchange (EDI).</span></span>  
7. <span data-ttu-id="df60f-123">Selezionare o deselezionare la casella di controllo Attiva valutazione vettore.</span><span class="sxs-lookup"><span data-stu-id="df60f-123">Check or uncheck the Activate carrier rating checkbox.</span></span>

## <a name="create-the-necessary-services-for-the-shipping-carrier"></a><span data-ttu-id="df60f-124">Creare i servizi necessari per il vettore di spedizione</span><span class="sxs-lookup"><span data-stu-id="df60f-124">Create the necessary services for the shipping carrier</span></span>
1. <span data-ttu-id="df60f-125">Attivare/disattivare l'espansione della sezione Servizi.</span><span class="sxs-lookup"><span data-stu-id="df60f-125">Toggle the expansion of the Services section.</span></span>
2. <span data-ttu-id="df60f-126">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="df60f-126">Click New.</span></span>
3. <span data-ttu-id="df60f-127">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="df60f-127">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="df60f-128">Nel campo Servizio trasporto digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="df60f-128">In the Carrier service field, type a value.</span></span>
5. <span data-ttu-id="df60f-129">Digitare un valore nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="df60f-129">In the Name field, type a value.</span></span>
6. <span data-ttu-id="df60f-130">Nel campo Metodo di trasporto fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="df60f-130">In the Transportation method field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="df60f-131">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="df60f-131">In the list, find and select the desired record.</span></span>
8. <span data-ttu-id="df60f-132">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="df60f-132">In the list, click the link in the selected row.</span></span>

## <a name="set-up-the-address-for-the-carrier-optional"></a><span data-ttu-id="df60f-133">Impostare l'indirizzo del vettore (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="df60f-133">Set up the address for the carrier (optional)</span></span>
1. <span data-ttu-id="df60f-134">Attiva/disattiva l'espansione della sezione Indirizzi.</span><span class="sxs-lookup"><span data-stu-id="df60f-134">Toggle the expansion of the Addresses section.</span></span>
2. <span data-ttu-id="df60f-135">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="df60f-135">Click New.</span></span>
3. <span data-ttu-id="df60f-136">Digitare un valore nel campo Nome o Descrizione.</span><span class="sxs-lookup"><span data-stu-id="df60f-136">In the Name or description field, type a value.</span></span>
4. <span data-ttu-id="df60f-137">Nel campo Paese fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="df60f-137">In the Country/region field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="df60f-138">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="df60f-138">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="df60f-139">Nel campo Codice postale (CAP) fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="df60f-139">In the ZIP/postal code field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="df60f-140">Trovare e selezionare il record desiderato nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="df60f-140">In the list, find and select the desired record.</span></span>
8. <span data-ttu-id="df60f-141">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="df60f-141">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="df60f-142">Digitare un valore nel campo Via.</span><span class="sxs-lookup"><span data-stu-id="df60f-142">In the Street field, type a value.</span></span>
10. <span data-ttu-id="df60f-143">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="df60f-143">Click OK.</span></span>

## <a name="set-up-the-rating-profile-for-the-shipping-carrier"></a><span data-ttu-id="df60f-144">Impostare il profilo di valutazione per il vettore di spedizione</span><span class="sxs-lookup"><span data-stu-id="df60f-144">Set up the rating profile for the shipping carrier</span></span>
1. <span data-ttu-id="df60f-145">Attivare/disattivare l'espansione della sezione Profili valutazione.</span><span class="sxs-lookup"><span data-stu-id="df60f-145">Toggle the expansion of the Rating profiles section.</span></span>
2. <span data-ttu-id="df60f-146">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="df60f-146">Click New.</span></span>
3. <span data-ttu-id="df60f-147">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="df60f-147">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="df60f-148">Nel campo Profilo valutazione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="df60f-148">In the Rating profile field, type a value.</span></span>
5. <span data-ttu-id="df60f-149">Digitare un valore nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="df60f-149">In the Name field, type a value.</span></span>
6. <span data-ttu-id="df60f-150">Nel campo Sito fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="df60f-150">In the Site field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="df60f-151">Trovare e selezionare il record desiderato nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="df60f-151">In the list, find and select the desired record.</span></span>
8. <span data-ttu-id="df60f-152">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="df60f-152">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="df60f-153">Nel campo Magazzino fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="df60f-153">In the Warehouse field, click the drop-down button to open the lookup.</span></span>
10. <span data-ttu-id="df60f-154">Trovare e selezionare il record desiderato nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="df60f-154">In the list, find and select the desired record.</span></span>
11. <span data-ttu-id="df60f-155">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="df60f-155">In the list, click the link in the selected row.</span></span>
12. <span data-ttu-id="df60f-156">Nel campo Motore tariffe fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="df60f-156">In the Rate engine field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="df60f-157">Selezionare il motore tariffe in base al contratto stipulato con il vettore.</span><span class="sxs-lookup"><span data-stu-id="df60f-157">Select the Rate engine that is in accordance with the contract that you have with the carrier.</span></span>  
13. <span data-ttu-id="df60f-158">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="df60f-158">In the list, find and select the desired record.</span></span>
14. <span data-ttu-id="df60f-159">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="df60f-159">In the list, click the link in the selected row.</span></span>
15. <span data-ttu-id="df60f-160">Nel campo Tariffa principale fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="df60f-160">In the Rate master field, click the drop-down button to open the lookup.</span></span>
16. <span data-ttu-id="df60f-161">Trovare e selezionare il record desiderato nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="df60f-161">In the list, find and select the desired record.</span></span>
17. <span data-ttu-id="df60f-162">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="df60f-162">In the list, click the link in the selected row.</span></span>
18. <span data-ttu-id="df60f-163">Nel campo Motore tempo di transito fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="df60f-163">In the Transit time engine field, click the drop-down button to open the lookup.</span></span>
19. <span data-ttu-id="df60f-164">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="df60f-164">In the list, click the link in the selected row.</span></span>
20. <span data-ttu-id="df60f-165">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="df60f-165">Click Save.</span></span>


