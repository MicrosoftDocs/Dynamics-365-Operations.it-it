---
title: Definire le regole di copertura per gli articoli
description: La società di dati dimostrativi utilizzata per creare questa procedura è USMF.
author: ShylaThompson
manager: tfehr
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqGroup, DefaultDashboard, EcoResProductDetailsExtended, EcoResProductCreate, InventItemOrderSetup, ReqItemTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: fd44c458da03807ddc1dc9d652da29c1404dbe64
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2020
ms.locfileid: "3209607"
---
# <a name="define-coverage-rules-for-items"></a><span data-ttu-id="d0216-103">Definire le regole di copertura per gli articoli</span><span class="sxs-lookup"><span data-stu-id="d0216-103">Define coverage rules for items</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="d0216-104">La società di dati dimostrativi utilizzata per creare questa procedura è USMF.</span><span class="sxs-lookup"><span data-stu-id="d0216-104">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="d0216-105">Questa procedura mostra come creare le regole di copertura e ignorare le impostazioni di copertura per un articolo specifico.</span><span class="sxs-lookup"><span data-stu-id="d0216-105">This procedure shows how to create coverage rules and override coverage settings for a specific item.</span></span> <span data-ttu-id="d0216-106">Viene inoltre illustrato come specificare le impostazioni predefinite di magazzino.</span><span class="sxs-lookup"><span data-stu-id="d0216-106">It also shows how to specify default inventory settings.</span></span>


## <a name="create-a-coverage-group"></a><span data-ttu-id="d0216-107">Creare un gruppo di copertura</span><span class="sxs-lookup"><span data-stu-id="d0216-107">Create a coverage group</span></span>
1. <span data-ttu-id="d0216-108">Passare a **Pannello di navigazione > Moduli > Pianificazione generale > Impostazioni > Gruppi di copertura**.</span><span class="sxs-lookup"><span data-stu-id="d0216-108">Go to **Navigation pane > Modules > Master planning > Setup > Coverage groups**.</span></span>
2. <span data-ttu-id="d0216-109">Fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="d0216-109">Click **New**.</span></span>
3. <span data-ttu-id="d0216-110">Digitare un valore nel campo **Gruppo di copertura**.</span><span class="sxs-lookup"><span data-stu-id="d0216-110">In the **Coverage group** field, type a value.</span></span>
4. <span data-ttu-id="d0216-111">Digitare un valore nel campo **Nome**.</span><span class="sxs-lookup"><span data-stu-id="d0216-111">In the **Name** field, type a value.</span></span>
5. <span data-ttu-id="d0216-112">Digitare un valore nel campo **Calendario**.</span><span class="sxs-lookup"><span data-stu-id="d0216-112">In the **Calendar** field, type a value.</span></span> <span data-ttu-id="d0216-113">Selezionare il calendario utilizzato dalla pianificazione generale per creare i suggerimenti di rifornimento per gli articoli inclusi nel gruppo.</span><span class="sxs-lookup"><span data-stu-id="d0216-113">Choose the calendar that master planning uses to create replenishment suggestions for items in this group.</span></span>  
6. <span data-ttu-id="d0216-114">Nel campo **Codice copertura** selezionare un'opzione.</span><span class="sxs-lookup"><span data-stu-id="d0216-114">In the **Coverage code** field, select an option.</span></span> <span data-ttu-id="d0216-115">Selezionare 'Fabbisogno' per questa procedura.</span><span class="sxs-lookup"><span data-stu-id="d0216-115">Select 'Requirement' for this procedure.</span></span>  
7. <span data-ttu-id="d0216-116">Nel campo **Intervallo temporale di copertura (giorni)** immettere '90'.</span><span class="sxs-lookup"><span data-stu-id="d0216-116">In the **Coverage time fence (days) field**, enter '90'.</span></span> <span data-ttu-id="d0216-117">Per gli articoli inclusi nel gruppo, la pianificazione generale creerà i suggerimenti di rifornimento per i fino a 90 giorni nel futuro.</span><span class="sxs-lookup"><span data-stu-id="d0216-117">For items in this group, master planning will create replenishment suggestions for up to 90 days in the future.</span></span>  
8. <span data-ttu-id="d0216-118">Nel campo **Giorni negativi** immettere '1'.</span><span class="sxs-lookup"><span data-stu-id="d0216-118">In the **Negative days** field, enter '1'.</span></span>
9. <span data-ttu-id="d0216-119">Nel campo **Giorni positività** immettere '1'.</span><span class="sxs-lookup"><span data-stu-id="d0216-119">In the **Positive days** field, enter '1'.</span></span>
10. <span data-ttu-id="d0216-120">Espandere o comprimere la sezione **Altro**.</span><span class="sxs-lookup"><span data-stu-id="d0216-120">Expand or collapse the **Other** section.</span></span>
11. <span data-ttu-id="d0216-121">Nella sezione **Margini di sicurezza in giorni**, nel campo **Margine su entrata in magazzino aggiunto dalla data del fabbisogno**, immettere '1'.</span><span class="sxs-lookup"><span data-stu-id="d0216-121">Under the **Safety margins in days** section, in the **Receipt margin added to requirement date** field, enter '1'.</span></span> <span data-ttu-id="d0216-122">Ad esempio, se il margine sull'entrata in magazzino è impostato su 1 giorno e una riga ordine fornitore è programmata per l'entrata il 15 maggio, la programmazione generale calcola come data di entrata rettificata il giorno 16 maggio.</span><span class="sxs-lookup"><span data-stu-id="d0216-122">For example, if the receipt margin is set to 1 day, and a purchase order line is scheduled for receipt on May 15, master planning calculates the adjusted receipt date as May 16.</span></span>  
12. <span data-ttu-id="d0216-123">Nel campo **Margine su uscita da magazzino detratto dalla data del fabbisogno** immettere '1'.</span><span class="sxs-lookup"><span data-stu-id="d0216-123">In the **Issue margin deducted from requirement date** field, enter '1'.</span></span> <span data-ttu-id="d0216-124">Ad esempio, se il margine di sicurezza è impostato su 1 giorno e una riga ordine cliente è programmata per la consegna il 15 maggio, la programmazione generale calcola come data rettificata il giorno 14 maggio.</span><span class="sxs-lookup"><span data-stu-id="d0216-124">For example, if the safety margin is set to 1 day, and a sales order line is scheduled for delivery on May 15, master scheduling calculates the adjusted delivery date as May 14.</span></span>  
13. <span data-ttu-id="d0216-125">Nel campo **Margine di riordino aggiunto al lead time dell'articolo** immettere '1'.</span><span class="sxs-lookup"><span data-stu-id="d0216-125">In the **Reorder margin added to item lead time** field, enter '1'.</span></span>
14. <span data-ttu-id="d0216-126">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="d0216-126">Click **Save**.</span></span>

## <a name="create-a-new-product"></a><span data-ttu-id="d0216-127">Creare un nuovo prodotto</span><span class="sxs-lookup"><span data-stu-id="d0216-127">Create a new product</span></span>
1. <span data-ttu-id="d0216-128">Andare a **Pannello di navigazione > Moduli > Gestione informazioni sul prodotto > Prodotti > Prodotti rilasciati**.</span><span class="sxs-lookup"><span data-stu-id="d0216-128">Go to **Navigation pane > Modules > Product information management > Products > Released products**.</span></span>
2. <span data-ttu-id="d0216-129">Fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="d0216-129">Click **New**.</span></span>
3. <span data-ttu-id="d0216-130">Nel campo **Numero prodotto**, digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="d0216-130">In the **Product number** field, type a value.</span></span>
4. <span data-ttu-id="d0216-131">Digitare un valore nel campo **Nome prodotto**.</span><span class="sxs-lookup"><span data-stu-id="d0216-131">In the **Product name** field, type a value.</span></span>
5. <span data-ttu-id="d0216-132">Nel campo **Gruppo di modelli di articoli** fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="d0216-132">In the **Item model group** field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="d0216-133">Trovare e selezionare il record desiderato nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="d0216-133">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="d0216-134">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="d0216-134">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="d0216-135">Nel campo **Gruppo di articoli** fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="d0216-135">In the **Item group** field, click the drop-down button to open the lookup.</span></span>
9. <span data-ttu-id="d0216-136">Trovare e selezionare il record desiderato nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="d0216-136">In the list, find and select the desired record.</span></span>
10. <span data-ttu-id="d0216-137">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="d0216-137">In the list, click the link in the selected row.</span></span>
11. <span data-ttu-id="d0216-138">Nel campo **Gruppo di dimensioni di immagazzinamento** fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="d0216-138">In the **Storage dimension group** field, click the drop-down button to open the lookup.</span></span>
12. <span data-ttu-id="d0216-139">Trovare e selezionare il record desiderato nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="d0216-139">In the list, find and select the desired record.</span></span>
13. <span data-ttu-id="d0216-140">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="d0216-140">In the list, click the link in the selected row.</span></span>
14. <span data-ttu-id="d0216-141">Nel campo **Gruppo di dimensioni di tracciabilità** fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="d0216-141">In the **Tracking dimension group** field, click the drop-down button to open the lookup.</span></span>
15. <span data-ttu-id="d0216-142">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="d0216-142">In the list, find and select the desired record.</span></span>
16. <span data-ttu-id="d0216-143">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="d0216-143">In the list, click the link in the selected row.</span></span>
17. <span data-ttu-id="d0216-144">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="d0216-144">Click **OK**.</span></span>

## <a name="setup-default-order-settings"></a><span data-ttu-id="d0216-145">Configura impostazioni ordine predefinite</span><span class="sxs-lookup"><span data-stu-id="d0216-145">Setup default order settings</span></span>
1. <span data-ttu-id="d0216-146">Nel **riquadro azioni**, fare clic su **Piano**.</span><span class="sxs-lookup"><span data-stu-id="d0216-146">On the **Action Pane**, click **Plan**.</span></span>
2. <span data-ttu-id="d0216-147">In **Impostazioni ordine**, fare clic su **Impostazioni ordine predefinite**.</span><span class="sxs-lookup"><span data-stu-id="d0216-147">Under **Order settings**, click **Default order settings**.</span></span>
3. <span data-ttu-id="d0216-148">In **Ordine fornitore**, nel campo **Sito predefinito**, immettere il sito utilizzato come predefinito quando vengono creati gli ordini fornitore.</span><span class="sxs-lookup"><span data-stu-id="d0216-148">Under **Purchase order**, in the **Default site** field, type the site used as default when purchase orders are created.</span></span>
4. <span data-ttu-id="d0216-149">Nel campo **Magazzino predefinito** immettere il sito in cui è immagazzinato l'articolo.</span><span class="sxs-lookup"><span data-stu-id="d0216-149">In the **Default warehouse** field, type the site where the item is stored.</span></span>
5. <span data-ttu-id="d0216-150">Espandere o comprimere la sezione **Inventario**.</span><span class="sxs-lookup"><span data-stu-id="d0216-150">Expand or collapse the **Inventory** section.</span></span>
6. <span data-ttu-id="d0216-151">Nel campo **Multiplo** digitare '10'.</span><span class="sxs-lookup"><span data-stu-id="d0216-151">In the **Multiple** field, type '10'.</span></span>
7. <span data-ttu-id="d0216-152">Nel campo **Quantità min. ordine**, immettere '10'.</span><span class="sxs-lookup"><span data-stu-id="d0216-152">In the **Min. order quantity** field, type '10'.</span></span>
8. <span data-ttu-id="d0216-153">Nel campo **Quantità max. ordine**, immettere '100'.</span><span class="sxs-lookup"><span data-stu-id="d0216-153">In the **Max. order quantity** field, type '100'.</span></span>
9. <span data-ttu-id="d0216-154">Nel campo **Quantità ordine standard**, immettere '10'.</span><span class="sxs-lookup"><span data-stu-id="d0216-154">In the **Standard order quantity**, type '10'.</span></span>
10. <span data-ttu-id="d0216-155">Nel campo **Lead time acquisto** immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="d0216-155">In the **Purchase lead time** field, enter a number.</span></span>
11. <span data-ttu-id="d0216-156">Selezionare o deselezionare la casella di controllo **Giorni lavorativi**.</span><span class="sxs-lookup"><span data-stu-id="d0216-156">Select or clear the **Working days** check box.</span></span>
12. <span data-ttu-id="d0216-157">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="d0216-157">Click **Save**.</span></span>
13. <span data-ttu-id="d0216-158">Nel campo **Tipo di ordine predefinito** selezionare 'Ordine fornitore'.</span><span class="sxs-lookup"><span data-stu-id="d0216-158">In the **Default order type** field select 'Purchase order'.</span></span>
14. <span data-ttu-id="d0216-159">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="d0216-159">Click **Save**.</span></span>
15. <span data-ttu-id="d0216-160">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="d0216-160">Close the page.</span></span> <span data-ttu-id="d0216-161">Chiudere la pagina Impostazioni ordine predefinite.</span><span class="sxs-lookup"><span data-stu-id="d0216-161">Close the Default order settings page.</span></span>  

## <a name="add-an-item-to-a-coverage-group"></a><span data-ttu-id="d0216-162">Aggiunge un articolo a un gruppo di copertura</span><span class="sxs-lookup"><span data-stu-id="d0216-162">Add an item to a coverage group</span></span>
1. <span data-ttu-id="d0216-163">Espandere o comprimere la sezione **Piano**.</span><span class="sxs-lookup"><span data-stu-id="d0216-163">Expand or collapse the **Plan** section.</span></span>
2. <span data-ttu-id="d0216-164">Nel campo **Gruppo di copertura** fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="d0216-164">In the **Coverage group** field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="d0216-165">Nell'elenco, individuare il **gruppo di copertura** creato.</span><span class="sxs-lookup"><span data-stu-id="d0216-165">In the list, find the **Coverage group** you have created.</span></span>
4. <span data-ttu-id="d0216-166">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="d0216-166">In the list, click the link in the selected row.</span></span>

## <a name="create-item-coverage-rules"></a><span data-ttu-id="d0216-167">Crea le regole copertura articoli</span><span class="sxs-lookup"><span data-stu-id="d0216-167">Create item coverage rules</span></span>
1. <span data-ttu-id="d0216-168">Nel **riquadro azioni**, fare clic su **Piano**.</span><span class="sxs-lookup"><span data-stu-id="d0216-168">On the **Action Pane**, click **Plan**.</span></span>
2. <span data-ttu-id="d0216-169">In **Copertura**, fare clic su **Copertura articoli**.</span><span class="sxs-lookup"><span data-stu-id="d0216-169">Under **Coverage**, click **Item coverage**.</span></span>
3. <span data-ttu-id="d0216-170">Fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="d0216-170">Click **New**.</span></span>
4. <span data-ttu-id="d0216-171">Fare clic sulla scheda **Generale**.</span><span class="sxs-lookup"><span data-stu-id="d0216-171">Click the **General** tab.</span></span>
5. <span data-ttu-id="d0216-172">Selezionare la casella nell'intestazione di **Ignora impostazioni gruppo di copertura**.</span><span class="sxs-lookup"><span data-stu-id="d0216-172">Check the box on the header of **Override coverage group** settings.</span></span>
6. <span data-ttu-id="d0216-173">Nel campo **Intervallo temporale di copertura (giorni)** immettere '60'.</span><span class="sxs-lookup"><span data-stu-id="d0216-173">In the **Coverage time fence (days)** field, enter '60'.</span></span> <span data-ttu-id="d0216-174">Anche se gli articoli nel gruppo di copertura Fabbisogno sono pianificati 90 giorni in anticipo, l'articolo verrà pianificato 60 giorni in anticipo.</span><span class="sxs-lookup"><span data-stu-id="d0216-174">Although items in coverage group Requiremen are planned 90 days ahead, this item will be planned 60 days ahead.</span></span>  
7. <span data-ttu-id="d0216-175">Nel campo **Giorni negativi** immettere '2'.</span><span class="sxs-lookup"><span data-stu-id="d0216-175">In the **Negative days** field, enter '2'.</span></span>
8. <span data-ttu-id="d0216-176">Nel campo **Giorni positività** immettere '2'.</span><span class="sxs-lookup"><span data-stu-id="d0216-176">In the **Positive days** field, enter '2'.</span></span>
9. <span data-ttu-id="d0216-177">Fare clic sulla scheda **Lead time**.</span><span class="sxs-lookup"><span data-stu-id="d0216-177">Click the **Lead time** tab.</span></span>
10. <span data-ttu-id="d0216-178">Selezionare la casella sull'intestazione di **Acquisto**.</span><span class="sxs-lookup"><span data-stu-id="d0216-178">Check the box on the header of **Purchase**.</span></span>
11. <span data-ttu-id="d0216-179">Nel campo **Ora dell'acquisto** immettere '5'.</span><span class="sxs-lookup"><span data-stu-id="d0216-179">In the **Purchase time** field, enter '5'.</span></span>
12. <span data-ttu-id="d0216-180">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="d0216-180">Click **Save**.</span></span>

