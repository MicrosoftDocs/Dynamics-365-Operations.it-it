--- 
title: Creare e modificare offerte di vendita
description: Questa procedura dimostra come creare e aggiornare un'offerta di vendita.
author: omulvad
manager: AnnBe
ms.date: 11/03/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 8e7d2198b4976a6f60f05690d7b6f11f3da55e28
ms.openlocfilehash: 7ffa4fe8d87db5b3f8293ec9dbc042496d09d6e3
ms.contentlocale: it-it
ms.lasthandoff: 11/03/2017

---
# <a name="create-and-edit-sales-quotations"></a><span data-ttu-id="07ba2-103">Creare e modificare offerte di vendita</span><span class="sxs-lookup"><span data-stu-id="07ba2-103">Create and edit sales quotations</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="07ba2-104">Questa procedura dimostra come creare e aggiornare un'offerta di vendita.</span><span class="sxs-lookup"><span data-stu-id="07ba2-104">This procedure demonstrates how to create and update a sales quotation.</span></span> <span data-ttu-id="07ba2-105">È possibile eseguire questa procedura sui propri dati o nella società di dati dimostrativi USMF.</span><span class="sxs-lookup"><span data-stu-id="07ba2-105">You can run this procedure on your own data or in demo data company USMF.</span></span>


## <a name="create-a-sales-quotation"></a><span data-ttu-id="07ba2-106">Creare un'offerta di vendita</span><span class="sxs-lookup"><span data-stu-id="07ba2-106">Create a sales quotation</span></span>
1. <span data-ttu-id="07ba2-107">Passare a Vendite e marketing > Offerte di vendita > Tutte le offerte.</span><span class="sxs-lookup"><span data-stu-id="07ba2-107">Go to Sales and marketing > Sales quotations > All quotations.</span></span>
2. <span data-ttu-id="07ba2-108">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="07ba2-108">Click New.</span></span>
3. <span data-ttu-id="07ba2-109">Nel campo Tipo di conto selezionare 'Prospect'.</span><span class="sxs-lookup"><span data-stu-id="07ba2-109">In the Account type field, select 'Prospect'.</span></span>
4. <span data-ttu-id="07ba2-110">Nel campo Prospect immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="07ba2-110">In the Prospect field, enter or select a value.</span></span>
5. <span data-ttu-id="07ba2-111">Espandere la sezione Generale.</span><span class="sxs-lookup"><span data-stu-id="07ba2-111">Expand the General section.</span></span>
    * <span data-ttu-id="07ba2-112">Poiché è stato scelto di creare un'offerta dall'area Vendita e marketing, il tipo viene automaticamente impostato su Offerta di vendita.</span><span class="sxs-lookup"><span data-stu-id="07ba2-112">Because you chose to create a quotation from the Sales and Marketing area, the type is automatically set to Sales quotation.</span></span> <span data-ttu-id="07ba2-113">Per creare un'offerta per un progetto è necessario accedervi dal modulo Gestione progetti e contabilità.</span><span class="sxs-lookup"><span data-stu-id="07ba2-113">To create a quotation for a project you must access it from the Project management and accounting module.</span></span>   
6. <span data-ttu-id="07ba2-114">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="07ba2-114">Click OK.</span></span>
    * <span data-ttu-id="07ba2-115">I campi e le azioni sulle righe dell'offerta sono simili a quelli delle righe ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="07ba2-115">The fields and actions on the quotation lines are very similar to the ones on the sales order lines.</span></span>   <span data-ttu-id="07ba2-116">Analogamente agli ordini cliente, le offerte possono essere create per un articolo specifico o, se il numero articolo non è definito o non esiste al momento della creazione dell'offerta, le offerte possono essere create per una categoria di vendita.</span><span class="sxs-lookup"><span data-stu-id="07ba2-116">Like sales orders, quotations can be created for a specific item or, when item number is not known or does not exist at the time of quotation creation, quotations can be created for a sales category.</span></span>  
7. <span data-ttu-id="07ba2-117">Nel campo Articolo immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="07ba2-117">In the Item field, enter or select a value.</span></span>
8. <span data-ttu-id="07ba2-118">Digitare un valore nel campo Articolo.</span><span class="sxs-lookup"><span data-stu-id="07ba2-118">In the Item field, type a value.</span></span>
9. <span data-ttu-id="07ba2-119">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="07ba2-119">Close the page.</span></span>
10. <span data-ttu-id="07ba2-120">Nel campo Quantità immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="07ba2-120">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="07ba2-121">Se sono presenti contratti commerciali validi per l'articolo selezionato nella riga, il prezzo e gli sconti applicabili verranno automaticamente copiati nella riga dell'offerta.</span><span class="sxs-lookup"><span data-stu-id="07ba2-121">If there are valid trade agreements for the item selected on the line, the applicable price and discounts will be automatically copied to the quotation line.</span></span> <span data-ttu-id="07ba2-122">Verificare che il campo Prezzo unitario contenga un valore ed è possibile immettere i valori di sconto se desiderato.</span><span class="sxs-lookup"><span data-stu-id="07ba2-122">Make sure that the Unit price field contains a value and you can also enter discount values if you want to.</span></span>  
11. <span data-ttu-id="07ba2-123">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="07ba2-123">Click Save.</span></span>
12. <span data-ttu-id="07ba2-124">Nel riquadro azioni fare clic su Offerta di vendita.</span><span class="sxs-lookup"><span data-stu-id="07ba2-124">On the Action Pane, click Sales quotation.</span></span>
13. <span data-ttu-id="07ba2-125">Fare clic su Totali.</span><span class="sxs-lookup"><span data-stu-id="07ba2-125">Click Totals.</span></span>
14. <span data-ttu-id="07ba2-126">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="07ba2-126">Click OK.</span></span>
15. <span data-ttu-id="07ba2-127">Fare clic su Riga offerta di vendita.</span><span class="sxs-lookup"><span data-stu-id="07ba2-127">Click Sales quotation line.</span></span>
16. <span data-ttu-id="07ba2-128">Fare clic su Prezzi.</span><span class="sxs-lookup"><span data-stu-id="07ba2-128">Click Prices.</span></span>
    * <span data-ttu-id="07ba2-129">Nella pagina Esegui simulazione prezzo è possibile sperimentare la rettifica dei ricavi o della redditività previsti per l'offerta in base al prezzo unitario, l'importo di sconto, la percentuale di sconto, l'importo totale, il margine o il rapporto di contribuzione desiderato.</span><span class="sxs-lookup"><span data-stu-id="07ba2-129">In the Run price simulation page you can experiment with adjusting the expected revenue or profitability of your quotation based on the desired unit price, discount amount, discount percentage, total amount, margin, or contribution ratio.</span></span>   <span data-ttu-id="07ba2-130">Al termine, applicare il suggerimento alla riga dell'offerta e i campi relativi al prezzo verranno aggiornati di conseguenza.</span><span class="sxs-lookup"><span data-stu-id="07ba2-130">When you are satisfied with the target figures, you apply the suggestion to the quotation line, and its price-related fields will be updated accordingly.</span></span>  
    * <span data-ttu-id="07ba2-131">È possibile creare qualsiasi numero di simulazioni di prezzo.</span><span class="sxs-lookup"><span data-stu-id="07ba2-131">You can create as many price simulations as you wish.</span></span> <span data-ttu-id="07ba2-132">Quando si fa clic su Nuovo, i termini del prezzo dalla riga offerta corrente vengono copiati nella pagina.</span><span class="sxs-lookup"><span data-stu-id="07ba2-132">When you click New, the price conditions from the current quotation line are copied to the page.</span></span> <span data-ttu-id="07ba2-133">È quindi possibile modificare i valori dei campi relativi al prezzo impostando quelli di destinazione.</span><span class="sxs-lookup"><span data-stu-id="07ba2-133">You can then modify values in any of the price-related fields to the target ones.</span></span> <span data-ttu-id="07ba2-134">Una modifica in uno dei campi avvierà il ricalcolo in tutti gli altri campi.</span><span class="sxs-lookup"><span data-stu-id="07ba2-134">A change in one of the fields will trigger recalculation in all the other fields.</span></span> <span data-ttu-id="07ba2-135">Affinché il sistema calcoli il margine di vendita e il rapporto di contribuzione, il costo unitario del prodotto deve essere noto.</span><span class="sxs-lookup"><span data-stu-id="07ba2-135">In order for the system to calculate the sales margin and contribution ratio, the product's unit cost has to be known.</span></span> <span data-ttu-id="07ba2-136">Utilizzare la scheda Prezzi simulati per una visualizzazione dettagliata dei prezzi originali, le modifiche proposte e i relativi effetti nei totali dell'offerta.</span><span class="sxs-lookup"><span data-stu-id="07ba2-136">Use the Simulated prices tab for a detailed view of the original prices, proposed changes and their effect on the quotation totals.</span></span>   <span data-ttu-id="07ba2-137">In genere, quando una simulazione che imposta un nuovo importo viene applicata alla riga offerta, il sistema ricalcola e immette un nuovo valore nel campo Prezzo unitario.</span><span class="sxs-lookup"><span data-stu-id="07ba2-137">As a general rule, when a simulation that sets a new amount is applied to the quotation line, the system recalculates and enters a new value in the Unit price field.</span></span> <span data-ttu-id="07ba2-138">Se la simulazione si basa su un nuovo margine o un nuovo rapporto di contribuzione, solo il campo Importo netto viene aggiornato e il campo Prezzo unitario risulterà vuoto.</span><span class="sxs-lookup"><span data-stu-id="07ba2-138">If the simulation is based on a new margin or a new contribution ratio, only the Net amount field is updated, and the Unit price is blank.</span></span> <span data-ttu-id="07ba2-139">In entrambi i casi, gli eventuali sconti inclusi nella riga dell'offerta prima della simulazione vengono eliminati.</span><span class="sxs-lookup"><span data-stu-id="07ba2-139">In both cases, any discounts that were on the quotation line before simulation will be deleted.</span></span>  
17. <span data-ttu-id="07ba2-140">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="07ba2-140">Close the page.</span></span>
18. <span data-ttu-id="07ba2-141">Nel riquadro azioni fare clic su Offerta.</span><span class="sxs-lookup"><span data-stu-id="07ba2-141">On the Action Pane, click Quotation.</span></span>
19. <span data-ttu-id="07ba2-142">Fare clic su Invia offerta.</span><span class="sxs-lookup"><span data-stu-id="07ba2-142">Click Send quotation.</span></span>
20. <span data-ttu-id="07ba2-143">Selezionare Sì nel campo Stampa offerta.</span><span class="sxs-lookup"><span data-stu-id="07ba2-143">Select Yes in the Print quotation field.</span></span>
21. <span data-ttu-id="07ba2-144">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="07ba2-144">Click OK.</span></span>
    * <span data-ttu-id="07ba2-145">La generazione del report può richiedere un minuto.</span><span class="sxs-lookup"><span data-stu-id="07ba2-145">The report may take a minute to generate.</span></span> <span data-ttu-id="07ba2-146">Non chiudere la pagina finché non termina l'operazione.</span><span class="sxs-lookup"><span data-stu-id="07ba2-146">Don’t close the page until it does so.</span></span>  
22. <span data-ttu-id="07ba2-147">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="07ba2-147">Close the page.</span></span>

## <a name="update-a-sales-quotation"></a><span data-ttu-id="07ba2-148">Aggiornare un'offerta di vendita</span><span class="sxs-lookup"><span data-stu-id="07ba2-148">Update a sales quotation</span></span>
1. <span data-ttu-id="07ba2-149">Nel riquadro azioni fare clic su Follow-up.</span><span class="sxs-lookup"><span data-stu-id="07ba2-149">On the Action Pane, click Follow up.</span></span>
2. <span data-ttu-id="07ba2-150">Fare clic su Converti in cliente.</span><span class="sxs-lookup"><span data-stu-id="07ba2-150">Click Convert to customer.</span></span>
3. <span data-ttu-id="07ba2-151">Digitare un valore nel campo Conto cliente.</span><span class="sxs-lookup"><span data-stu-id="07ba2-151">In the Customer account field, type a value.</span></span>
4. <span data-ttu-id="07ba2-152">Fare clic su Verifica.</span><span class="sxs-lookup"><span data-stu-id="07ba2-152">Click Check.</span></span>
    * <span data-ttu-id="07ba2-153">Verificare che venga visualizzato un messaggio indicante che il numero di conto immesso può essere utilizzato.</span><span class="sxs-lookup"><span data-stu-id="07ba2-153">Make sure you see a message that the account number you typed in is free to use.</span></span>  
5. <span data-ttu-id="07ba2-154">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="07ba2-154">Click OK.</span></span>
    * <span data-ttu-id="07ba2-155">Il sistema ora ha creato un nuovo conto cliente per il prospect dell'offerta.</span><span class="sxs-lookup"><span data-stu-id="07ba2-155">The system has now created a new customer account for the prospect on the quotation.</span></span>  
6. <span data-ttu-id="07ba2-156">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="07ba2-156">Close the page.</span></span>
7. <span data-ttu-id="07ba2-157">Nel riquadro azioni fare clic su Follow-up.</span><span class="sxs-lookup"><span data-stu-id="07ba2-157">On the Action Pane, click Follow up.</span></span>
8. <span data-ttu-id="07ba2-158">Fare clic su Conferma.</span><span class="sxs-lookup"><span data-stu-id="07ba2-158">Click Confirm.</span></span>
9. <span data-ttu-id="07ba2-159">Nel campo Motivo immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="07ba2-159">In the Reason field, enter or select a value.</span></span>
10. <span data-ttu-id="07ba2-160">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="07ba2-160">Click OK.</span></span>
11. <span data-ttu-id="07ba2-161">Nel riquadro azioni fare clic su Generale.</span><span class="sxs-lookup"><span data-stu-id="07ba2-161">On the Action Pane, click General.</span></span>
12. <span data-ttu-id="07ba2-162">Fare clic su Ordini cliente.</span><span class="sxs-lookup"><span data-stu-id="07ba2-162">Click Sales orders.</span></span>
13. <span data-ttu-id="07ba2-163">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="07ba2-163">Close the page.</span></span>


