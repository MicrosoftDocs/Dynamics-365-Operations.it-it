--- 
title: Adempiere ai contratti di vendita
description: Questa procedura indica come soddisfare un contratto di vendita associando gli ordini cliente.
author: omulvad
manager: AnnBe
ms.date: 11/10/2016
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
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: f0894bf962c139c2e9e4c9f8d1589fd933afcedb
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---
# <a name="fulfill-sales-agreements"></a><span data-ttu-id="0fb70-103">Adempiere ai contratti di vendita</span><span class="sxs-lookup"><span data-stu-id="0fb70-103">Fulfill sales agreements</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="0fb70-104">Questa procedura indica come soddisfare un contratto di vendita associando gli ordini cliente.</span><span class="sxs-lookup"><span data-stu-id="0fb70-104">This procedure shows you how to fulfill a sales agreement by associating sales orders with it.</span></span> <span data-ttu-id="0fb70-105">È possibile eseguire questa procedura nella società di dati dimostrativi USMF oppure nei propri dati.</span><span class="sxs-lookup"><span data-stu-id="0fb70-105">You can run this procedure in demo data company USMF or on your own data.</span></span> <span data-ttu-id="0fb70-106">Prima di iniziare questa guida, assicurarsi di disporre di un contratto di vendita valido di tipo "Impegno valore prodotto".</span><span class="sxs-lookup"><span data-stu-id="0fb70-106">Before starting this guide, make sure you have an effective sales agreement of type "Product value commitment".</span></span> <span data-ttu-id="0fb70-107">In alternativa, è possibile eseguire la guida attività denominata "Creare contratti di vendita".</span><span class="sxs-lookup"><span data-stu-id="0fb70-107">Alternatively, you can run the task guide called "Create sales agreements".</span></span>  




## <a name="release-a-sales-order-from-the-agreement"></a><span data-ttu-id="0fb70-108">Rilasciare un ordine cliente dal contratto</span><span class="sxs-lookup"><span data-stu-id="0fb70-108">Release a sales order from the agreement</span></span>
1. <span data-ttu-id="0fb70-109">Passare a Vendite e marketing > Contratti di vendita > Contratti di vendita.</span><span class="sxs-lookup"><span data-stu-id="0fb70-109">Go to Sales and marketing > Sales agreements > Sales agreements.</span></span>
2. <span data-ttu-id="0fb70-110">Nell'elenco, aprire il contratto con cui si desidera rilasciare l'ordine.</span><span class="sxs-lookup"><span data-stu-id="0fb70-110">In the list, open the agreement against which you want to release the order.</span></span>
3. <span data-ttu-id="0fb70-111">Nel riquadro azioni, fare clic su Contratto di vendita.</span><span class="sxs-lookup"><span data-stu-id="0fb70-111">On the Action Pane, click Sales agreement.</span></span>
4. <span data-ttu-id="0fb70-112">Fare clic su Ordine di rilascio.</span><span class="sxs-lookup"><span data-stu-id="0fb70-112">Click Release order.</span></span>
    * <span data-ttu-id="0fb70-113">Come indicato dal testo nella parte superiore della pagina Crea ordine di rilascio, i dettagli richiesti per le righe ordine cliente variano a seconda se il contratto si basa sulla quantità o sul valore.</span><span class="sxs-lookup"><span data-stu-id="0fb70-113">As the text on top of the  Create release order page points out, the details required for the sales order lines will differ depending on whether the agreement is quantity- or value-based.</span></span>  
    * <span data-ttu-id="0fb70-114">Il contratto in questa guida è di tipo "Impegno valore prodotto"</span><span class="sxs-lookup"><span data-stu-id="0fb70-114">The agreement in this guide is of type "Product value commitment".</span></span> <span data-ttu-id="0fb70-115">e pertanto la Righe di questa pagina è vuota.</span><span class="sxs-lookup"><span data-stu-id="0fb70-115">This is why the Lines section of this page is blank.</span></span> <span data-ttu-id="0fb70-116">Se l'impegno fosse stato basato sulla quantità, le informazioni sulle righe sarebbero state copiate dal contratto.</span><span class="sxs-lookup"><span data-stu-id="0fb70-116">If the commitment was based on quantity, the line information would be copied from the agreement.</span></span>  
5. <span data-ttu-id="0fb70-117">Fare clic su Crea.</span><span class="sxs-lookup"><span data-stu-id="0fb70-117">Click Create.</span></span>
    * <span data-ttu-id="0fb70-118">Il messaggio informa che l'ordine cliente è stato creato.</span><span class="sxs-lookup"><span data-stu-id="0fb70-118">The message informs you that a sales order has been created.</span></span> <span data-ttu-id="0fb70-119">Poiché l'ordine non contiene righe, è necessario aggiungere i dettagli riga ordine per completare il processo di rilascio.</span><span class="sxs-lookup"><span data-stu-id="0fb70-119">Since the order does not contain any lines, you must add order line details to complete the release process.</span></span>   
6. <span data-ttu-id="0fb70-120">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="0fb70-120">Close the page.</span></span>
7. <span data-ttu-id="0fb70-121">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="0fb70-121">Close the page.</span></span>
8. <span data-ttu-id="0fb70-122">Passare a Vendite e marketing > Ordini cliente > Tutti gli ordini cliente.</span><span class="sxs-lookup"><span data-stu-id="0fb70-122">Go to Sales and marketing > Sales orders > All sales orders.</span></span>
9. <span data-ttu-id="0fb70-123">Nell'elenco, individuare e aprire l'ordine creato come risultato del rilascio dell'ordine dell'attività precedente.</span><span class="sxs-lookup"><span data-stu-id="0fb70-123">In the list, find and open the order that was created as the result of the order release in the previous task.</span></span>
10. <span data-ttu-id="0fb70-124">Fare clic su Aggiungi riga.</span><span class="sxs-lookup"><span data-stu-id="0fb70-124">Click Add line.</span></span>
11. <span data-ttu-id="0fb70-125">Nel campo Numero articolo fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="0fb70-125">In the Item number field, click the drop-down button to open the lookup.</span></span>
12. <span data-ttu-id="0fb70-126">Nel campo Numero articolo, digitare o selezionare l'articolo specificato nel contratto di vendita associato.</span><span class="sxs-lookup"><span data-stu-id="0fb70-126">In the Item number field, type or select the item that is specified on the associated sales agreement.</span></span>
13. <span data-ttu-id="0fb70-127">Nel campo Quantità immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="0fb70-127">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="0fb70-128">Assicurarsi di immettere una quantità tale che l'importo netto sia inferiore al valore del contratto di vendita collegato.</span><span class="sxs-lookup"><span data-stu-id="0fb70-128">Make sure that you enter a quantity that brings the Net amount under the value of the associated sales agreement.</span></span>  
    * <span data-ttu-id="0fb70-129">Si noti che poiché l'ordine cliente è collegato al contratto, la percentuale negoziata di sconto viene applicata alla riga ordine.</span><span class="sxs-lookup"><span data-stu-id="0fb70-129">Notice that because the sales order is linked to the agreement, the negotiated discount percent is applied to the order line.</span></span>  
14. <span data-ttu-id="0fb70-130">Fare clic su Aggiorna riga.</span><span class="sxs-lookup"><span data-stu-id="0fb70-130">Click Update line.</span></span>
15. <span data-ttu-id="0fb70-131">Fare clic su Collegata.</span><span class="sxs-lookup"><span data-stu-id="0fb70-131">Click Attached.</span></span>
    * <span data-ttu-id="0fb70-132">La pagina Contratto allegato mostra l'ID e i termini del contratto da cui la riga viene rilasciata.</span><span class="sxs-lookup"><span data-stu-id="0fb70-132">The Attached agreement page shows the ID and terms of the agreement from which the line is released.</span></span>  
16. <span data-ttu-id="0fb70-133">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="0fb70-133">Close the page.</span></span>
17. <span data-ttu-id="0fb70-134">Nel riquadro azioni fare clic su Generale.</span><span class="sxs-lookup"><span data-stu-id="0fb70-134">On the Action Pane, click General.</span></span>
18. <span data-ttu-id="0fb70-135">Fare clic su Contratto di vendita allegato.</span><span class="sxs-lookup"><span data-stu-id="0fb70-135">Click Attached sales agreement.</span></span>
19. <span data-ttu-id="0fb70-136">Espandere la sezione Dettagli riga.</span><span class="sxs-lookup"><span data-stu-id="0fb70-136">Expand the Line details section.</span></span>
20. <span data-ttu-id="0fb70-137">Fare clic sulla scheda Evasione.</span><span class="sxs-lookup"><span data-stu-id="0fb70-137">Click the Fulfillment tab.</span></span>
    * <span data-ttu-id="0fb70-138">La scheda Evasione mostra un riepilogo di tutte le righe ordine cliente che sono associate a questo impegno e il relativo stato di adempimento nonché l'importo o la quantità che ancora non è stata rilasciata.</span><span class="sxs-lookup"><span data-stu-id="0fb70-138">The Fulfillment tab shows a summary of all the sales order lines that are associated with this commitment, and their fulfillment state, as well as the amount or quantity that has not yet been released.</span></span>   
21. <span data-ttu-id="0fb70-139">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="0fb70-139">Close the page.</span></span>
22. <span data-ttu-id="0fb70-140">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="0fb70-140">Close the page.</span></span>
23. <span data-ttu-id="0fb70-141">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="0fb70-141">Close the page.</span></span>

## <a name="apply-sales-agreement-in-the-order-process"></a><span data-ttu-id="0fb70-142">Applicare il contratto di vendita nel processo dell'ordine</span><span class="sxs-lookup"><span data-stu-id="0fb70-142">Apply sales agreement in the order process</span></span>
1. <span data-ttu-id="0fb70-143">Passare a Vendite e marketing > Ordini cliente > Tutti gli ordini cliente.</span><span class="sxs-lookup"><span data-stu-id="0fb70-143">Go to Sales and marketing > Sales orders > All sales orders.</span></span>
2. <span data-ttu-id="0fb70-144">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="0fb70-144">Click New.</span></span>
3. <span data-ttu-id="0fb70-145">Nel campo Conto cliente fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="0fb70-145">In the Customer account field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="0fb70-146">Nell'elenco, trovare e selezionare il cliente specificato nel contratto di vendita.</span><span class="sxs-lookup"><span data-stu-id="0fb70-146">In the list, find and select the customer specified on the sales agreement.</span></span>
5. <span data-ttu-id="0fb70-147">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="0fb70-147">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="0fb70-148">Espandere la sezione Generale.</span><span class="sxs-lookup"><span data-stu-id="0fb70-148">Expand the General section.</span></span>
7. <span data-ttu-id="0fb70-149">Nel campo ID contratto di vendita fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="0fb70-149">In the Sales agreement ID field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="0fb70-150">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="0fb70-150">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="0fb70-151">Fare clic su Sì.</span><span class="sxs-lookup"><span data-stu-id="0fb70-151">Click Yes.</span></span>
10. <span data-ttu-id="0fb70-152">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="0fb70-152">Click OK.</span></span>
11. <span data-ttu-id="0fb70-153">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="0fb70-153">In the list, mark the selected row.</span></span>
12. <span data-ttu-id="0fb70-154">Nel campo Numero articolo fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="0fb70-154">In the Item number field, click the drop-down button to open the lookup.</span></span>
13. <span data-ttu-id="0fb70-155">Nel campo Numero articolo, digitare o selezionare l'articolo specificato nel contratto di vendita associato.</span><span class="sxs-lookup"><span data-stu-id="0fb70-155">In the Item number field, type or select the item that is specified on the associated sales agreement.</span></span>
14. <span data-ttu-id="0fb70-156">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="0fb70-156">In the list, click the link in the selected row.</span></span>
15. <span data-ttu-id="0fb70-157">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="0fb70-157">Click Save.</span></span>
16. <span data-ttu-id="0fb70-158">Nel riquadro azioni fare clic su Preleva e imballa.</span><span class="sxs-lookup"><span data-stu-id="0fb70-158">On the Action Pane, click Pick and pack.</span></span>
17. <span data-ttu-id="0fb70-159">Fare clic su Registra documento di trasporto.</span><span class="sxs-lookup"><span data-stu-id="0fb70-159">Click Post packing slip.</span></span>
18. <span data-ttu-id="0fb70-160">Espandere la sezione Parametri.</span><span class="sxs-lookup"><span data-stu-id="0fb70-160">Expand the Parameters section.</span></span>
19. <span data-ttu-id="0fb70-161">Selezionare Sì nel campo Registrazione.</span><span class="sxs-lookup"><span data-stu-id="0fb70-161">Select Yes in the Posting field.</span></span>
20. <span data-ttu-id="0fb70-162">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="0fb70-162">Click OK.</span></span>
21. <span data-ttu-id="0fb70-163">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="0fb70-163">Click OK.</span></span>
22. <span data-ttu-id="0fb70-164">Nel riquadro azioni fare clic su Generale.</span><span class="sxs-lookup"><span data-stu-id="0fb70-164">On the Action Pane, click General.</span></span>
23. <span data-ttu-id="0fb70-165">Fare clic su Contratto di vendita allegato.</span><span class="sxs-lookup"><span data-stu-id="0fb70-165">Click Attached sales agreement.</span></span>
24. <span data-ttu-id="0fb70-166">Fare clic sulla scheda Evasione.</span><span class="sxs-lookup"><span data-stu-id="0fb70-166">Click the Fulfillment tab.</span></span>


