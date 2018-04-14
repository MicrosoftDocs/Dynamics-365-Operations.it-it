--- 
title: Definire le regole di copertura per gli articoli
description: "La società di dati dimostrativi utilizzata per creare questa procedura è USMF."
author: YuyuScheller
manager: AnnBe
ms.date: 11/02/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 4d28abe06cb7bfd43fd95af8cd88e022a51f5380
ms.contentlocale: it-it
ms.lasthandoff: 04/13/2018

---
# <a name="define-coverage-rules-for-items"></a><span data-ttu-id="8f106-103">Definire le regole di copertura per gli articoli</span><span class="sxs-lookup"><span data-stu-id="8f106-103">Define coverage rules for items</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="8f106-104">La società di dati dimostrativi utilizzata per creare questa procedura è USMF.</span><span class="sxs-lookup"><span data-stu-id="8f106-104">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="8f106-105">Questa procedura mostra come creare le regole di copertura e ignorare le impostazioni di copertura per un articolo specifico.</span><span class="sxs-lookup"><span data-stu-id="8f106-105">This procedure shows how to create coverage rules and override coverage settings for a specific item.</span></span> <span data-ttu-id="8f106-106">Viene inoltre illustrato come specificare le impostazioni predefinite di magazzino.</span><span class="sxs-lookup"><span data-stu-id="8f106-106">It also shows how to specify default inventory settings.</span></span>


## <a name="create-a-coverage-group"></a><span data-ttu-id="8f106-107">Creare un gruppo di copertura</span><span class="sxs-lookup"><span data-stu-id="8f106-107">Create a coverage group</span></span>
1. <span data-ttu-id="8f106-108">Fare clic su Gruppi di copertura</span><span class="sxs-lookup"><span data-stu-id="8f106-108">Go to Coverage groups.</span></span>
2. <span data-ttu-id="8f106-109">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="8f106-109">Click New.</span></span>
3. <span data-ttu-id="8f106-110">Digitare un valore nel campo Gruppo di copertura.</span><span class="sxs-lookup"><span data-stu-id="8f106-110">In the Coverage group field, type a value.</span></span>
4. <span data-ttu-id="8f106-111">Digitare un valore nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="8f106-111">In the Name field, type a value.</span></span>
5. <span data-ttu-id="8f106-112">Digitare un valore nel campo Calendario.</span><span class="sxs-lookup"><span data-stu-id="8f106-112">In the Calendar field, type a value.</span></span>
    * <span data-ttu-id="8f106-113">Selezionare il calendario utilizzato dalla pianificazione generale per creare i suggerimenti di rifornimento per gli articoli inclusi nel gruppo.</span><span class="sxs-lookup"><span data-stu-id="8f106-113">Choose the calendar that master planning uses to create replenishment suggestions for items in this group.</span></span>  
6. <span data-ttu-id="8f106-114">Nel campo Codice copertura selezionare un'opzione.</span><span class="sxs-lookup"><span data-stu-id="8f106-114">In the Coverage code field, select an option.</span></span>
    * <span data-ttu-id="8f106-115">Selezionare Fabbisogno per questa procedura.</span><span class="sxs-lookup"><span data-stu-id="8f106-115">Select Requirement for this procedure.</span></span>  
7. <span data-ttu-id="8f106-116">Nel campo Intervallo temporale di copertura (giorni) immettere "90".</span><span class="sxs-lookup"><span data-stu-id="8f106-116">In the Coverage time fence (days) field, enter '90'.</span></span>
    * <span data-ttu-id="8f106-117">Per gli articoli inclusi nel gruppo, la pianificazione generale creerà i suggerimenti di rifornimento per i fino a 90 giorni nel futuro.</span><span class="sxs-lookup"><span data-stu-id="8f106-117">For items in this group, master planning will create replenishment suggestions for up to 90 days in the future.</span></span>  
8. <span data-ttu-id="8f106-118">Nel campo Giorni negativi immettere "1".</span><span class="sxs-lookup"><span data-stu-id="8f106-118">In the Negative days field, enter '1'.</span></span>
9. <span data-ttu-id="8f106-119">Nel campo Giorni positività immettere "1".</span><span class="sxs-lookup"><span data-stu-id="8f106-119">In the Positive days field, enter '1'.</span></span>
10. <span data-ttu-id="8f106-120">Espandere o comprimere la sezione Altro.</span><span class="sxs-lookup"><span data-stu-id="8f106-120">Expand or collapse the Other section.</span></span>
11. <span data-ttu-id="8f106-121">Nel campo Margine su entrata in magazzino aggiunto dalla data del fabbisogno immettere "1".</span><span class="sxs-lookup"><span data-stu-id="8f106-121">In the Receipt margin added to requirement date field, enter '1'.</span></span>
    * <span data-ttu-id="8f106-122">Ad esempio, se il margine sull'entrata in magazzino è impostato su 1 giorno e una riga ordine fornitore è programmata per l'entrata il 15 maggio, la programmazione generale calcola come data di entrata rettificata il giorno 16 maggio.</span><span class="sxs-lookup"><span data-stu-id="8f106-122">For example, if the receipt margin is set to 1 day, and a purchase order line is scheduled for receipt on May 15, master planning calculates the adjusted receipt date as May 16.</span></span>  
12. <span data-ttu-id="8f106-123">Nel campo Margine su uscita da magazzino detratto dalla data del fabbisogno immettere "1".</span><span class="sxs-lookup"><span data-stu-id="8f106-123">In the Issue margin deducted from requirement date field, enter '1'.</span></span>
    * <span data-ttu-id="8f106-124">Ad esempio, se il margine di sicurezza è impostato su 1 giorno e una riga ordine cliente è programmata per la consegna il 15 maggio, la programmazione generale calcola come data rettificata il giorno 14 maggio.</span><span class="sxs-lookup"><span data-stu-id="8f106-124">For example, if the safety margin is set to 1 day, and a sales order line is scheduled for delivery on May 15, master scheduling calculates the adjusted delivery date as May 14.</span></span>  
13. <span data-ttu-id="8f106-125">Nel campo Margine di riordino aggiunto al lead time dell'articolo immettere "1".</span><span class="sxs-lookup"><span data-stu-id="8f106-125">In the Reorder margin added to item lead time field, enter '1'.</span></span>
14. <span data-ttu-id="8f106-126">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="8f106-126">Click Save.</span></span>

## <a name="create-a-new-product"></a><span data-ttu-id="8f106-127">Crea un nuovo prodotto</span><span class="sxs-lookup"><span data-stu-id="8f106-127">Create a new product</span></span>
1. <span data-ttu-id="8f106-128">Fare clic su Prodotti rilasciati.</span><span class="sxs-lookup"><span data-stu-id="8f106-128">Go to Released products.</span></span>
2. <span data-ttu-id="8f106-129">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="8f106-129">Click New.</span></span>
3. <span data-ttu-id="8f106-130">Nel campo Numero prodotto, digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="8f106-130">In the Product number field, type a value.</span></span>
4. <span data-ttu-id="8f106-131">Digitare un valore nel campo Nome prodotto.</span><span class="sxs-lookup"><span data-stu-id="8f106-131">In the Product name field, type a value.</span></span>
5. <span data-ttu-id="8f106-132">Nel campo Gruppo di modelli di articoli fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="8f106-132">In the Item model group field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="8f106-133">Trovare e selezionare il record desiderato nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="8f106-133">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="8f106-134">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="8f106-134">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="8f106-135">Nel campo Gruppo di articoli fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="8f106-135">In the Item group field, click the drop-down button to open the lookup.</span></span>
9. <span data-ttu-id="8f106-136">Trovare e selezionare il record desiderato nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="8f106-136">In the list, find and select the desired record.</span></span>
10. <span data-ttu-id="8f106-137">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="8f106-137">In the list, click the link in the selected row.</span></span>
11. <span data-ttu-id="8f106-138">Nel campo Gruppo di dimensioni di immagazzinamento fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="8f106-138">In the Storage dimension group field, click the drop-down button to open the lookup.</span></span>
12. <span data-ttu-id="8f106-139">Trovare e selezionare il record desiderato nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="8f106-139">In the list, find and select the desired record.</span></span>
13. <span data-ttu-id="8f106-140">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="8f106-140">In the list, click the link in the selected row.</span></span>
14. <span data-ttu-id="8f106-141">Nel campo Gruppo di dimensioni di tracciabilità fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="8f106-141">In the Tracking dimension group field, click the drop-down button to open the lookup.</span></span>
15. <span data-ttu-id="8f106-142">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="8f106-142">In the list, find and select the desired record.</span></span>
16. <span data-ttu-id="8f106-143">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="8f106-143">In the list, click the link in the selected row.</span></span>
17. <span data-ttu-id="8f106-144">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="8f106-144">Click OK.</span></span>

## <a name="setup-default-order-settings"></a><span data-ttu-id="8f106-145">Configura impostazioni ordine predefinite</span><span class="sxs-lookup"><span data-stu-id="8f106-145">Setup default order settings</span></span>
1. <span data-ttu-id="8f106-146">Nel riquadro azioni fare clic su Piano.</span><span class="sxs-lookup"><span data-stu-id="8f106-146">On the Action Pane, click Plan.</span></span>
2. <span data-ttu-id="8f106-147">Fare clic su Impostazioni ordine predefinite.</span><span class="sxs-lookup"><span data-stu-id="8f106-147">Click Default order settings.</span></span>
3. <span data-ttu-id="8f106-148">Nel campo Sito acquisto, immettere il sito utilizzato come valore predefinito quando vengono creati gli ordini fornitore.</span><span class="sxs-lookup"><span data-stu-id="8f106-148">In the Purchase site field, type the site used as default when purchase orders are created.</span></span>
4. <span data-ttu-id="8f106-149">Nel campo Sito magazzino immettere il sito in cui è immagazzinato l'articolo.</span><span class="sxs-lookup"><span data-stu-id="8f106-149">In the Inventory site field, type the site where the item is stored.</span></span>
5. <span data-ttu-id="8f106-150">Espandere o comprimere la sezione Inventario.</span><span class="sxs-lookup"><span data-stu-id="8f106-150">Expand or collapse the Inventory section.</span></span>
6. <span data-ttu-id="8f106-151">Imposta Multiplo su "10".</span><span class="sxs-lookup"><span data-stu-id="8f106-151">Set Multiple to '10'.</span></span>
7. <span data-ttu-id="8f106-152">Impostare la quantità</span><span class="sxs-lookup"><span data-stu-id="8f106-152">Set Min.</span></span> <span data-ttu-id="8f106-153">ordine minima su "10".</span><span class="sxs-lookup"><span data-stu-id="8f106-153">order quantity to '10'.</span></span>
8. <span data-ttu-id="8f106-154">Impostare quantità ordine</span><span class="sxs-lookup"><span data-stu-id="8f106-154">Set Max.</span></span> <span data-ttu-id="8f106-155">ordine minima massima su "100".</span><span class="sxs-lookup"><span data-stu-id="8f106-155">order quantity to '100'.</span></span>
9. <span data-ttu-id="8f106-156">Imposta la quantità ordine standard su "10".</span><span class="sxs-lookup"><span data-stu-id="8f106-156">Set Standard order quantity to '10'.</span></span>
10. <span data-ttu-id="8f106-157">Nel campo Lead time acquisto immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="8f106-157">In the Purchase lead time field, enter a number.</span></span>
11. <span data-ttu-id="8f106-158">Selezionare o deselezionare la casella di controllo Giorni lavorativi.</span><span class="sxs-lookup"><span data-stu-id="8f106-158">Select or clear the Working days check box.</span></span>
12. <span data-ttu-id="8f106-159">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="8f106-159">Click Save.</span></span>
13. <span data-ttu-id="8f106-160">Nel campo Tipo di ordine predefinito selezionare "Ordine acquisto".</span><span class="sxs-lookup"><span data-stu-id="8f106-160">In the Default order type field select 'Purchase order'.</span></span>
14. <span data-ttu-id="8f106-161">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="8f106-161">Click Save.</span></span>
15. <span data-ttu-id="8f106-162">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="8f106-162">Close the page.</span></span>
    * <span data-ttu-id="8f106-163">Chiudere la pagina Impostazioni ordine predefinite.</span><span class="sxs-lookup"><span data-stu-id="8f106-163">Close the Default order settings page.</span></span>  

## <a name="add-an-item-to-a-coverage-group"></a><span data-ttu-id="8f106-164">Aggiunge un articolo a un gruppo di copertura</span><span class="sxs-lookup"><span data-stu-id="8f106-164">Add an item to a coverage group</span></span>
1. <span data-ttu-id="8f106-165">Espandere o comprimere la sezione Piano.</span><span class="sxs-lookup"><span data-stu-id="8f106-165">Expand or collapse the Plan section.</span></span>
2. <span data-ttu-id="8f106-166">Nel campo Gruppo di copertura fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="8f106-166">In the Coverage group field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="8f106-167">Nell'elenco, individuare il gruppo di copertura creato.</span><span class="sxs-lookup"><span data-stu-id="8f106-167">In the list, find the Coverage group you have created.</span></span>
4. <span data-ttu-id="8f106-168">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="8f106-168">In the list, click the link in the selected row.</span></span>

## <a name="create-item-coverage-rules"></a><span data-ttu-id="8f106-169">Crea le regole copertura articoli</span><span class="sxs-lookup"><span data-stu-id="8f106-169">Create item coverage rules</span></span>
1. <span data-ttu-id="8f106-170">Nel riquadro azioni fare clic su Piano.</span><span class="sxs-lookup"><span data-stu-id="8f106-170">On the Action Pane, click Plan.</span></span>
2. <span data-ttu-id="8f106-171">Fare clic su Copertura articoli.</span><span class="sxs-lookup"><span data-stu-id="8f106-171">Click Item coverage.</span></span>
3. <span data-ttu-id="8f106-172">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="8f106-172">Click New.</span></span>
4. <span data-ttu-id="8f106-173">Fare clic sulla scheda Generale.</span><span class="sxs-lookup"><span data-stu-id="8f106-173">Click the General tab.</span></span>
5. <span data-ttu-id="8f106-174">Selezionare la casella nell'intestazione di Ignora impostazioni gruppo di copertura.</span><span class="sxs-lookup"><span data-stu-id="8f106-174">Check the box on the header of Override coverage group settings.</span></span>
6. <span data-ttu-id="8f106-175">Nel campo Intervallo temporale di copertura (giorni) immettere "60".</span><span class="sxs-lookup"><span data-stu-id="8f106-175">In the Coverage time fence (days) field, enter '60'.</span></span>
    * <span data-ttu-id="8f106-176">Anche se gli articoli nel gruppo di copertura Fabbisogno sono pianificati 90 giorni in anticipo, l'articolo verrà pianificato 60 giorni in anticipo.</span><span class="sxs-lookup"><span data-stu-id="8f106-176">Although items in coverage group Requirement are planned 90 days ahead, this item will be planned 60 days ahead.</span></span>  
7. <span data-ttu-id="8f106-177">Nel campo Giorni negativi immettere "2".</span><span class="sxs-lookup"><span data-stu-id="8f106-177">In the Negative days field, enter '2'.</span></span>
8. <span data-ttu-id="8f106-178">Nel campo Giorni positività immettere "2".</span><span class="sxs-lookup"><span data-stu-id="8f106-178">In the Positive days field, enter '2'.</span></span>
9. <span data-ttu-id="8f106-179">Fare clic sulla scheda Lead time.</span><span class="sxs-lookup"><span data-stu-id="8f106-179">Click the Lead time tab.</span></span>
10. <span data-ttu-id="8f106-180">Selezionare la casella sull'intestazione di Acquisto.</span><span class="sxs-lookup"><span data-stu-id="8f106-180">Check the box on the header of Purchase.</span></span>
11. <span data-ttu-id="8f106-181">Nel campo Ora dell'acquisto immettere "5".</span><span class="sxs-lookup"><span data-stu-id="8f106-181">In the Purchase time field, enter '5'.</span></span>
12. <span data-ttu-id="8f106-182">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="8f106-182">Click Save.</span></span>


