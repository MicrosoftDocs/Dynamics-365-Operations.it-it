--- 
title: "Inserire dati fattura nella contabilità fornitori tramite una fattura fornitore"
description: "Questa guida attività consentirà di creare una fattura fornitore da un ordine fornitore e di visualizzare i risultati dell'abbinamento dell'ordine fornitore, dell'entrata e della fattura (corrispondenza a 3 elementi di verifica)."
author: abruer
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 48535a283cbdfdc7343a20105b139c527cac85f4
ms.contentlocale: it-it
ms.lasthandoff: 08/29/2017

---
# <a name="key-invoice-data-into-accounts-payable-using-a-vendor-invoice"></a><span data-ttu-id="3438e-103">Inserire dati fattura nella contabilità fornitori tramite una fattura fornitore</span><span class="sxs-lookup"><span data-stu-id="3438e-103">Key invoice data into accounts payable using a vendor invoice</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="3438e-104">Questa guida attività consentirà di creare una fattura fornitore da un ordine fornitore e di visualizzare i risultati dell'abbinamento dell'ordine fornitore, dell'entrata e della fattura (corrispondenza a 3 elementi di verifica).</span><span class="sxs-lookup"><span data-stu-id="3438e-104">This task guide will help you create a vendor invoice from a purchase order and view the results of matching the purchase order, receipt, and invoice (3 way matching).</span></span>


## <a name="create-a-purchase-order"></a><span data-ttu-id="3438e-105">Creare un ordine fornitore</span><span class="sxs-lookup"><span data-stu-id="3438e-105">Create a purchase order</span></span>
1. <span data-ttu-id="3438e-106">Fare clic su Contabilità fornitori > Ordini fornitore > Tutti gli ordini fornitore.</span><span class="sxs-lookup"><span data-stu-id="3438e-106">Go to Accounts payable > Purchase orders > All purchase orders.</span></span>
2. <span data-ttu-id="3438e-107">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="3438e-107">Click New.</span></span>
3. <span data-ttu-id="3438e-108">Nel campo Conto fornitore fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="3438e-108">In the Vendor account field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="3438e-109">Individuare un fornitore da selezionare.</span><span class="sxs-lookup"><span data-stu-id="3438e-109">Find a vendor to select.</span></span> <span data-ttu-id="3438e-110">Ad esempio, scorrere verso il basso fino a US-104.</span><span class="sxs-lookup"><span data-stu-id="3438e-110">For example, scroll down to US-104.</span></span>
5. <span data-ttu-id="3438e-111">Seleziona il fornitore US-104.</span><span class="sxs-lookup"><span data-stu-id="3438e-111">Select vendor US-104.</span></span>
6. <span data-ttu-id="3438e-112">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="3438e-112">Click OK.</span></span>
7. <span data-ttu-id="3438e-113">Nel campo Numero articolo fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="3438e-113">In the Item number field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="3438e-114">Selezionare un articolo di magazzino.</span><span class="sxs-lookup"><span data-stu-id="3438e-114">Select an inventory item.</span></span> <span data-ttu-id="3438e-115">Ad esempio, selezionare il numero articolo 1000.</span><span class="sxs-lookup"><span data-stu-id="3438e-115">For example, select item number 1000.</span></span>
9. <span data-ttu-id="3438e-116">Espandere o comprimere la sezione Dettagli riga.</span><span class="sxs-lookup"><span data-stu-id="3438e-116">Expand or collapse the Line details section.</span></span>
10. <span data-ttu-id="3438e-117">Fare clic sulla scheda Impostazioni.</span><span class="sxs-lookup"><span data-stu-id="3438e-117">Click the Setup tab.</span></span>
    * <span data-ttu-id="3438e-118">È possibile sostituire i criteri di abbinamento per non utilizzare la corrispondenza, la corrispondenza o due elementi di verifica o quella a tre elementi di verifica.</span><span class="sxs-lookup"><span data-stu-id="3438e-118">You can override the matching policy to use no matching, 2-way matching, or 3-way matching.</span></span>  
11. <span data-ttu-id="3438e-119">Espandere o comprimere la sezione Dettagli riga.</span><span class="sxs-lookup"><span data-stu-id="3438e-119">Expand or collapse the Line details section.</span></span>
12. <span data-ttu-id="3438e-120">Nel riquadro azioni fare clic su Acquisti.</span><span class="sxs-lookup"><span data-stu-id="3438e-120">On the Action Pane, click Purchase.</span></span>
13. <span data-ttu-id="3438e-121">Fare clic su Conferma.</span><span class="sxs-lookup"><span data-stu-id="3438e-121">Click Confirm.</span></span>

## <a name="receive-the-products"></a><span data-ttu-id="3438e-122">Ricevere i prodotti</span><span class="sxs-lookup"><span data-stu-id="3438e-122">Receive the products</span></span>
1. <span data-ttu-id="3438e-123">Nel riquadro azioni fare clic su Ricevimento.</span><span class="sxs-lookup"><span data-stu-id="3438e-123">On the Action Pane, click Receive.</span></span>
2. <span data-ttu-id="3438e-124">Fare clic su Entrata prodotti.</span><span class="sxs-lookup"><span data-stu-id="3438e-124">Click Product receipt.</span></span>
3. <span data-ttu-id="3438e-125">Nel campo Entrata prodotti, immettere il numero dell'entrata prodotti.</span><span class="sxs-lookup"><span data-stu-id="3438e-125">In the Product receipt field, enter the product receipt number.</span></span> <span data-ttu-id="3438e-126">Ad esempio, immettere PR123.</span><span class="sxs-lookup"><span data-stu-id="3438e-126">For example, enter PR123.</span></span>
4. <span data-ttu-id="3438e-127">Fare clic su OK per registrare l'entrata prodotti.</span><span class="sxs-lookup"><span data-stu-id="3438e-127">Click OK to post the product receipt.</span></span>
5. <span data-ttu-id="3438e-128">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="3438e-128">Close the page.</span></span>

## <a name="create-a-vendor-invoice"></a><span data-ttu-id="3438e-129">Creare una fattura fornitore</span><span class="sxs-lookup"><span data-stu-id="3438e-129">Create a vendor invoice</span></span>
1. <span data-ttu-id="3438e-130">Andare a Contabilità fornitori > Ordini acquisto > Ordini acquisto ricevuti ma non fatturati.</span><span class="sxs-lookup"><span data-stu-id="3438e-130">Go to Accounts payable > Purchase orders > Purchase orders received but not invoiced.</span></span>
2. <span data-ttu-id="3438e-131">Selezionare l'ordine fornitore creato.</span><span class="sxs-lookup"><span data-stu-id="3438e-131">Select the purchase order that you created.</span></span>
3. <span data-ttu-id="3438e-132">Nel riquadro azioni fare clic su Fattura.</span><span class="sxs-lookup"><span data-stu-id="3438e-132">On the Action Pane, click Invoice.</span></span>
4. <span data-ttu-id="3438e-133">Fare clic su Fattura.</span><span class="sxs-lookup"><span data-stu-id="3438e-133">Click Invoice.</span></span>
5. <span data-ttu-id="3438e-134">Nel campo Numero immettere il numero di fattura.</span><span class="sxs-lookup"><span data-stu-id="3438e-134">In the Number field, enter the invoice number.</span></span>
6. <span data-ttu-id="3438e-135">Nel campo Descrizione fattura digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="3438e-135">In the Invoice description field, type a value.</span></span>
7. <span data-ttu-id="3438e-136">Immettere una data nel campo Data fattura.</span><span class="sxs-lookup"><span data-stu-id="3438e-136">In the Invoice date field, enter a date.</span></span>
8. <span data-ttu-id="3438e-137">Immettere 1200 nel campo Prezzo unitario.</span><span class="sxs-lookup"><span data-stu-id="3438e-137">In the Unit price field, enter 1200.</span></span>
9. <span data-ttu-id="3438e-138">Fare clic su Aggiungi riga.</span><span class="sxs-lookup"><span data-stu-id="3438e-138">Click Add line.</span></span>
10. <span data-ttu-id="3438e-139">Nel campo Numero articolo fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="3438e-139">In the Item number field, click the drop-down button to open the lookup.</span></span>
11. <span data-ttu-id="3438e-140">Nell'elenco, individuare il numero di articolo della spesa di installazione.</span><span class="sxs-lookup"><span data-stu-id="3438e-140">In the list, find the installation charge item number.</span></span> <span data-ttu-id="3438e-141">Ad esempio, S0001</span><span class="sxs-lookup"><span data-stu-id="3438e-141">For example, S0001</span></span>
12. <span data-ttu-id="3438e-142">Selezionare il numero articolo della spesa di installazione.</span><span class="sxs-lookup"><span data-stu-id="3438e-142">Select the installation charge item number.</span></span>
    * <span data-ttu-id="3438e-143">Si noti che la corrispondenza non è stata eseguita da quando sono state apportate le modifiche.</span><span class="sxs-lookup"><span data-stu-id="3438e-143">Note that matching has not been performed since you made the changes.</span></span>  
13. <span data-ttu-id="3438e-144">Fare clic su Aggiorna stato di abbinamento.</span><span class="sxs-lookup"><span data-stu-id="3438e-144">Click Update match status.</span></span>
14. <span data-ttu-id="3438e-145">Nel riquadro azioni fare clic su Revisione.</span><span class="sxs-lookup"><span data-stu-id="3438e-145">On the Action Pane, click Review.</span></span>
15. <span data-ttu-id="3438e-146">Fare clic su Dettagli abbinamento.</span><span class="sxs-lookup"><span data-stu-id="3438e-146">Click Matching details.</span></span>
    * <span data-ttu-id="3438e-147">La nuova riga con i servizi non deve essere abbinata, quindi lo stato rimane "Non eseguito".</span><span class="sxs-lookup"><span data-stu-id="3438e-147">The new line with services does not need to be matched so the status stays "Not performed".</span></span>  
16. <span data-ttu-id="3438e-148">Selezionare l'entrata prodotti per l'articolo di magazzino ricevuto.</span><span class="sxs-lookup"><span data-stu-id="3438e-148">Select the product receipt for the inventory item that you received.</span></span>
    * <span data-ttu-id="3438e-149">La riga con l'entrata prodotti è stata abbinata, ma la quantità o il prezzo non sono corrispondenti e pertanto restituisce l'esito negativo.</span><span class="sxs-lookup"><span data-stu-id="3438e-149">The line with the product receipt was matched but there is a mismatch of quantity or price so it fails.</span></span>  
17. <span data-ttu-id="3438e-150">Nel campo Prezzo unitario immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="3438e-150">In the Unit price field, enter a number.</span></span>
    * <span data-ttu-id="3438e-151">Ora che il prezzo unitario corrisponde, lo stato verrà aggiornato su Superato.</span><span class="sxs-lookup"><span data-stu-id="3438e-151">Now that the unit price matches, the status is updated to Passed.</span></span> <span data-ttu-id="3438e-152">Se i criteri consentono le discrepanze o se la corrispondenza è solo un avviso, è comunque possibile registrare la fattura.</span><span class="sxs-lookup"><span data-stu-id="3438e-152">If your policy allows discrepancies or if matching is only a warning, you can still post the invoice.</span></span>  
18. <span data-ttu-id="3438e-153">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="3438e-153">Close the page.</span></span>
19. <span data-ttu-id="3438e-154">Fare clic su Registra.</span><span class="sxs-lookup"><span data-stu-id="3438e-154">Click Post.</span></span>
20. <span data-ttu-id="3438e-155">Chiudere il modulo.</span><span class="sxs-lookup"><span data-stu-id="3438e-155">Close the form.</span></span>
    * <span data-ttu-id="3438e-156">Si noti che l'ordine fornitore non è più elencato come ricevuto ma come non fatturato.</span><span class="sxs-lookup"><span data-stu-id="3438e-156">Note that the purchase order is no longer listed as received but not invoiced.</span></span>  


