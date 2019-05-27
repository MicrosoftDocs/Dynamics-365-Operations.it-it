---
title: Impostare vettori di spedizione
description: Questa procedura descrive come impostare un vettore di spedizione e come definire dettagli quali servizio, modalità di spedizione, metodo di pagamento del trasporto, vincoli di trasporto e tariffa di trasporto.
author: ShylaThompson
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6c5ac13d17c97f20ee79e7faf57c570f02158424
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "1569104"
---
# <a name="set-up-shipping-carriers"></a><span data-ttu-id="8067e-103">Impostare vettori di spedizione</span><span class="sxs-lookup"><span data-stu-id="8067e-103">Set up shipping carriers</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="8067e-104">Questa procedura descrive come impostare un vettore di spedizione e come definire dettagli quali servizio, modalità di spedizione, metodo di pagamento del trasporto, vincoli di trasporto e tariffa di trasporto.</span><span class="sxs-lookup"><span data-stu-id="8067e-104">This procedure shows how to set up a shipping carrier and define details such as service, shipment mode, transportation tender, transportation constraints, and shipping rate.</span></span> <span data-ttu-id="8067e-105">Un coordinatore dei trasporti può quindi assegnare un vettore di spedizione a un carico in entrata o in uscita.</span><span class="sxs-lookup"><span data-stu-id="8067e-105">A transportation coordinator can then assign a shipping carrier to an inbound or outbound load.</span></span>


## <a name="create-a-new-shipping-carrier"></a><span data-ttu-id="8067e-106">Creare un nuovo vettore di spedizione</span><span class="sxs-lookup"><span data-stu-id="8067e-106">Create a new shipping carrier</span></span>
1. <span data-ttu-id="8067e-107">Andare a Gestione trasporto > Impostazioni > Vettori > Vettori spedizione.</span><span class="sxs-lookup"><span data-stu-id="8067e-107">Go to Transportation management > Setup > Carriers > Shipping carriers.</span></span>
2. <span data-ttu-id="8067e-108">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="8067e-108">Click New.</span></span>
3. <span data-ttu-id="8067e-109">Nel campo Vettore spedizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="8067e-109">In the Shipping carrier field, type a value.</span></span>
4. <span data-ttu-id="8067e-110">Digitare un valore nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="8067e-110">In the Name field, type a value.</span></span>
5. <span data-ttu-id="8067e-111">Nel campo Modalità fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="8067e-111">In the Mode field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="8067e-112">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="8067e-112">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="8067e-113">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="8067e-113">In the list, click the link in the selected row.</span></span>

## <a name="fill-in-the-general-information-for-the-shipping-carrier"></a><span data-ttu-id="8067e-114">Inserire le informazioni generali per il vettore di spedizione</span><span class="sxs-lookup"><span data-stu-id="8067e-114">Fill in the general information for the shipping carrier</span></span>
1. <span data-ttu-id="8067e-115">Attivare/disattivare l'espansione della sezione Panoramica.</span><span class="sxs-lookup"><span data-stu-id="8067e-115">Toggle the expansion of the Overview section.</span></span>
2. <span data-ttu-id="8067e-116">Selezionare o deselezionare la casella di controllo Attiva vettore di spedizione.</span><span class="sxs-lookup"><span data-stu-id="8067e-116">Check or uncheck the Activate shipping carrier checkbox.</span></span>
3. <span data-ttu-id="8067e-117">Nel campo Fornitore fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="8067e-117">In the Vendor field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="8067e-118">Selezionare il conto fornitore a cui assegnare il vettore di spedizione.</span><span class="sxs-lookup"><span data-stu-id="8067e-118">Select the vendor account to assign the shipping carrier to.</span></span>  
4. <span data-ttu-id="8067e-119">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="8067e-119">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="8067e-120">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="8067e-120">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="8067e-121">Nel campo Tipo di pagamento trasporto selezionare un'opzione.</span><span class="sxs-lookup"><span data-stu-id="8067e-121">In the Transportation tender type field, select an option.</span></span>
    * <span data-ttu-id="8067e-122">Selezionare Manuale per utilizzare la pagina Metodo di pagamento trasporto o selezionare EDI per aggiornare il metodo di pagamento utilizzando il formato EDI (Electronic Data Interchange).</span><span class="sxs-lookup"><span data-stu-id="8067e-122">Select Manual to use the Transportation Tender page, or select EDI to update the tender by using Electronic Data Interchange (EDI).</span></span>  
7. <span data-ttu-id="8067e-123">Selezionare o deselezionare la casella di controllo Attiva valutazione vettore.</span><span class="sxs-lookup"><span data-stu-id="8067e-123">Check or uncheck the Activate carrier rating checkbox.</span></span>

## <a name="create-the-necessary-services-for-the-shipping-carrier"></a><span data-ttu-id="8067e-124">Creare i servizi necessari per il vettore di spedizione</span><span class="sxs-lookup"><span data-stu-id="8067e-124">Create the necessary services for the shipping carrier</span></span>
1. <span data-ttu-id="8067e-125">Attivare/disattivare l'espansione della sezione Servizi.</span><span class="sxs-lookup"><span data-stu-id="8067e-125">Toggle the expansion of the Services section.</span></span>
2. <span data-ttu-id="8067e-126">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="8067e-126">Click New.</span></span>
3. <span data-ttu-id="8067e-127">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="8067e-127">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="8067e-128">Nel campo Servizio trasporto digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="8067e-128">In the Carrier service field, type a value.</span></span>
5. <span data-ttu-id="8067e-129">Digitare un valore nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="8067e-129">In the Name field, type a value.</span></span>
6. <span data-ttu-id="8067e-130">Nel campo Metodo di trasporto fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="8067e-130">In the Transportation method field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="8067e-131">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="8067e-131">In the list, find and select the desired record.</span></span>
8. <span data-ttu-id="8067e-132">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="8067e-132">In the list, click the link in the selected row.</span></span>

## <a name="set-up-the-address-for-the-carrier-optional"></a><span data-ttu-id="8067e-133">Impostare l'indirizzo del vettore (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="8067e-133">Set up the address for the carrier (optional)</span></span>
1. <span data-ttu-id="8067e-134">Attiva/disattiva l'espansione della sezione Indirizzi.</span><span class="sxs-lookup"><span data-stu-id="8067e-134">Toggle the expansion of the Addresses section.</span></span>
2. <span data-ttu-id="8067e-135">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="8067e-135">Click New.</span></span>
3. <span data-ttu-id="8067e-136">Digitare un valore nel campo Nome o Descrizione.</span><span class="sxs-lookup"><span data-stu-id="8067e-136">In the Name or description field, type a value.</span></span>
4. <span data-ttu-id="8067e-137">Nel campo Paese fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="8067e-137">In the Country/region field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="8067e-138">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="8067e-138">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="8067e-139">Nel campo Codice postale (CAP) fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="8067e-139">In the ZIP/postal code field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="8067e-140">Trovare e selezionare il record desiderato nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="8067e-140">In the list, find and select the desired record.</span></span>
8. <span data-ttu-id="8067e-141">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="8067e-141">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="8067e-142">Digitare un valore nel campo Via.</span><span class="sxs-lookup"><span data-stu-id="8067e-142">In the Street field, type a value.</span></span>
10. <span data-ttu-id="8067e-143">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="8067e-143">Click OK.</span></span>

## <a name="set-up-the-rating-profile-for-the-shipping-carrier"></a><span data-ttu-id="8067e-144">Impostare il profilo di valutazione per il vettore di spedizione</span><span class="sxs-lookup"><span data-stu-id="8067e-144">Set up the rating profile for the shipping carrier</span></span>
1. <span data-ttu-id="8067e-145">Attivare/disattivare l'espansione della sezione Profili valutazione.</span><span class="sxs-lookup"><span data-stu-id="8067e-145">Toggle the expansion of the Rating profiles section.</span></span>
2. <span data-ttu-id="8067e-146">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="8067e-146">Click New.</span></span>
3. <span data-ttu-id="8067e-147">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="8067e-147">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="8067e-148">Nel campo Profilo valutazione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="8067e-148">In the Rating profile field, type a value.</span></span>
5. <span data-ttu-id="8067e-149">Digitare un valore nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="8067e-149">In the Name field, type a value.</span></span>
6. <span data-ttu-id="8067e-150">Nel campo Sito fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="8067e-150">In the Site field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="8067e-151">Trovare e selezionare il record desiderato nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="8067e-151">In the list, find and select the desired record.</span></span>
8. <span data-ttu-id="8067e-152">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="8067e-152">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="8067e-153">Nel campo Magazzino fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="8067e-153">In the Warehouse field, click the drop-down button to open the lookup.</span></span>
10. <span data-ttu-id="8067e-154">Trovare e selezionare il record desiderato nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="8067e-154">In the list, find and select the desired record.</span></span>
11. <span data-ttu-id="8067e-155">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="8067e-155">In the list, click the link in the selected row.</span></span>
12. <span data-ttu-id="8067e-156">Nel campo Motore tariffe fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="8067e-156">In the Rate engine field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="8067e-157">Selezionare il motore tariffe in base al contratto stipulato con il vettore.</span><span class="sxs-lookup"><span data-stu-id="8067e-157">Select the Rate engine that is in accordance with the contract that you have with the carrier.</span></span>  
13. <span data-ttu-id="8067e-158">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="8067e-158">In the list, find and select the desired record.</span></span>
14. <span data-ttu-id="8067e-159">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="8067e-159">In the list, click the link in the selected row.</span></span>
15. <span data-ttu-id="8067e-160">Nel campo Tariffa principale fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="8067e-160">In the Rate master field, click the drop-down button to open the lookup.</span></span>
16. <span data-ttu-id="8067e-161">Trovare e selezionare il record desiderato nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="8067e-161">In the list, find and select the desired record.</span></span>
17. <span data-ttu-id="8067e-162">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="8067e-162">In the list, click the link in the selected row.</span></span>
18. <span data-ttu-id="8067e-163">Nel campo Motore tempo di transito fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="8067e-163">In the Transit time engine field, click the drop-down button to open the lookup.</span></span>
19. <span data-ttu-id="8067e-164">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="8067e-164">In the list, click the link in the selected row.</span></span>
20. <span data-ttu-id="8067e-165">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="8067e-165">Click Save.</span></span>

