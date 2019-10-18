---
title: Dati principali della fattura in sistema di contabilità fornitori utilizzando la fattura fornitore
description: Questa guida attività consentirà di creare una fattura fornitore da un ordine fornitore e di visualizzare i risultati dell'abbinamento dell'ordine fornitore, dell'entrata e della fattura (corrispondenza a 3 elementi di verifica).
author: abruer
manager: AnnBe
ms.date: 07/22/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable, PurchCreateOrder, InventItemIdLookupPurchase, PurchEditLines, VendEditInvoice, InventItemIdLookupSimple, VendInvoiceMatchingDetails
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7abae6d680d899a0294ad3c298a4b0264ba01d0b
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/27/2019
ms.locfileid: "2189432"
---
# <a name="key-invoice-data-in-ap-system-using-vendor-invoice"></a><span data-ttu-id="7fcae-103">Dati principali della fattura in sistema di contabilità fornitori utilizzando la fattura fornitore</span><span class="sxs-lookup"><span data-stu-id="7fcae-103">Key invoice data in AP system using vendor invoice</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="7fcae-104">Questa guida attività consentirà di creare una fattura fornitore da un ordine fornitore e di visualizzare i risultati dell'abbinamento dell'ordine fornitore, dell'entrata e della fattura (corrispondenza a 3 elementi di verifica).</span><span class="sxs-lookup"><span data-stu-id="7fcae-104">This task guide will help you create a vendor invoice from a purchase order and view the results of matching the purchase order, receipt, and invoice (3 way matching).</span></span>


## <a name="create-a-purchase-order"></a><span data-ttu-id="7fcae-105">Creare un ordine fornitore</span><span class="sxs-lookup"><span data-stu-id="7fcae-105">Create a purchase order</span></span>
1. <span data-ttu-id="7fcae-106">Passare al pannello di navigazione, andare a **Moduli > Contabilità fornitori > Ordini fornitore > Tutti gli ordini fornitore**.</span><span class="sxs-lookup"><span data-stu-id="7fcae-106">In the Navigation pane, go to **Modules > Accounts payable > Purchase orders > All purchase orders**.</span></span>
2. <span data-ttu-id="7fcae-107">Fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="7fcae-107">Click **New**.</span></span>
3. <span data-ttu-id="7fcae-108">Nel campo **Conto fornitore** fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="7fcae-108">In the **Vendor account** field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="7fcae-109">Individuare un fornitore da selezionare.</span><span class="sxs-lookup"><span data-stu-id="7fcae-109">Find a vendor to select.</span></span> <span data-ttu-id="7fcae-110">Ad esempio, scorrere verso il basso fino a US-104.</span><span class="sxs-lookup"><span data-stu-id="7fcae-110">For example, scroll down to US-104.</span></span>
5. <span data-ttu-id="7fcae-111">Seleziona il fornitore US-104.</span><span class="sxs-lookup"><span data-stu-id="7fcae-111">Select vendor US-104.</span></span>
6. <span data-ttu-id="7fcae-112">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="7fcae-112">Click **OK**.</span></span>
7. <span data-ttu-id="7fcae-113">Nel campo **Numero articolo** fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="7fcae-113">In the **Item number** field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="7fcae-114">Selezionare un articolo di magazzino.</span><span class="sxs-lookup"><span data-stu-id="7fcae-114">Select an inventory item.</span></span> <span data-ttu-id="7fcae-115">Ad esempio, selezionare il numero articolo 1000.</span><span class="sxs-lookup"><span data-stu-id="7fcae-115">For example, select item number 1000.</span></span>
9. <span data-ttu-id="7fcae-116">Espandere la Scheda dettaglio **Dettagli riga**.</span><span class="sxs-lookup"><span data-stu-id="7fcae-116">Expand the **Line details** fastTab.</span></span>
10. <span data-ttu-id="7fcae-117">Fare clic sulla scheda **Impostazione**. È possibile sostituire i criteri di abbinamento per utilizzare nessun abbinamento, l'abbinamento a due elementi di verifica o quello a tre elementi di verifica.</span><span class="sxs-lookup"><span data-stu-id="7fcae-117">Click the **Setup** tab. You can override the matching policy to use no matching, 2-way matching, or 3-way matching.</span></span>  
11. <span data-ttu-id="7fcae-118">Nel riquadro azioni, fare clic su **Acquisti**.</span><span class="sxs-lookup"><span data-stu-id="7fcae-118">On the Action Pane, click **Purchase**.</span></span>
12. <span data-ttu-id="7fcae-119">Fare clic su **Conferma**.</span><span class="sxs-lookup"><span data-stu-id="7fcae-119">Click **Confirm**.</span></span>

## <a name="receive-the-products"></a><span data-ttu-id="7fcae-120">Ricevere i prodotti</span><span class="sxs-lookup"><span data-stu-id="7fcae-120">Receive the products</span></span>
1. <span data-ttu-id="7fcae-121">Nel riquadro azioni, fare clic su **Ricevimento**.</span><span class="sxs-lookup"><span data-stu-id="7fcae-121">On the Action Pane, click **Receive**.</span></span>
2. <span data-ttu-id="7fcae-122">Fare clic su **Entrata prodotti**.</span><span class="sxs-lookup"><span data-stu-id="7fcae-122">Click **Product receipt**.</span></span>
3. <span data-ttu-id="7fcae-123">Nel campo **Entrata prodotti**, immettere il numero dell'entrata prodotti.</span><span class="sxs-lookup"><span data-stu-id="7fcae-123">In the **Product receipt** field, enter the product receipt number.</span></span> <span data-ttu-id="7fcae-124">Ad esempio, immettere PR123.</span><span class="sxs-lookup"><span data-stu-id="7fcae-124">For example, enter PR123.</span></span>
4. <span data-ttu-id="7fcae-125">Fare clic su **OK** per registrare l'entrata prodotti.</span><span class="sxs-lookup"><span data-stu-id="7fcae-125">Click **OK** to post the product receipt.</span></span>
5. <span data-ttu-id="7fcae-126">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="7fcae-126">Close the page.</span></span>

## <a name="create-a-vendor-invoice"></a><span data-ttu-id="7fcae-127">Creare una fattura fornitore</span><span class="sxs-lookup"><span data-stu-id="7fcae-127">Create a vendor invoice</span></span>
1. <span data-ttu-id="7fcae-128">Passare al pannello di navigazione, andare a **Moduli > Contabilità fornitori > Ordini fornitore > Ordini fornitore ricevuti ma non fatturati**.</span><span class="sxs-lookup"><span data-stu-id="7fcae-128">In the Navigation pane, go to **Modules > Accounts payable > Purchase orders > Purchase orders received but not invoiced**.</span></span>
2. <span data-ttu-id="7fcae-129">Selezionare l'ordine fornitore creato.</span><span class="sxs-lookup"><span data-stu-id="7fcae-129">Select the purchase order that you created.</span></span>
3. <span data-ttu-id="7fcae-130">Nel riquadro azioni fare clic su **Fattura**.</span><span class="sxs-lookup"><span data-stu-id="7fcae-130">On the Action Pane, click **Invoice**.</span></span>
4. <span data-ttu-id="7fcae-131">Fare clic su **Fattura**.</span><span class="sxs-lookup"><span data-stu-id="7fcae-131">Click **Invoice**.</span></span>
5. <span data-ttu-id="7fcae-132">Nel campo **Numero** immettere il numero di fattura.</span><span class="sxs-lookup"><span data-stu-id="7fcae-132">In the **Number** field, enter the invoice number.</span></span>
6. <span data-ttu-id="7fcae-133">Nel campo **Descrizione fattura** digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="7fcae-133">In the **Invoice description** field, type a value.</span></span>
7. <span data-ttu-id="7fcae-134">Immettere una data nel campo **Data fattura**.</span><span class="sxs-lookup"><span data-stu-id="7fcae-134">In the **Invoice date** field, enter a date.</span></span>
8. <span data-ttu-id="7fcae-135">Immettere 1200 nel campo **Prezzo unitario**.</span><span class="sxs-lookup"><span data-stu-id="7fcae-135">In the **Unit price** field, enter 1200.</span></span>
9. <span data-ttu-id="7fcae-136">Fare clic su **Aggiungi riga**.</span><span class="sxs-lookup"><span data-stu-id="7fcae-136">Click **Add line**.</span></span>
10. <span data-ttu-id="7fcae-137">Nel campo **Numero articolo** fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="7fcae-137">In the **Item number** field, click the drop-down button to open the lookup.</span></span>
11. <span data-ttu-id="7fcae-138">Nell'elenco, individuare il numero di articolo della spesa di installazione.</span><span class="sxs-lookup"><span data-stu-id="7fcae-138">In the list, find the installation charge item number.</span></span> <span data-ttu-id="7fcae-139">Ad esempio, S0001</span><span class="sxs-lookup"><span data-stu-id="7fcae-139">For example, S0001</span></span>
12. <span data-ttu-id="7fcae-140">Selezionare il numero articolo della spesa di installazione.</span><span class="sxs-lookup"><span data-stu-id="7fcae-140">Select the installation charge item number.</span></span> <span data-ttu-id="7fcae-141">Si noti che la corrispondenza non è stata eseguita da quando sono state apportate le modifiche.</span><span class="sxs-lookup"><span data-stu-id="7fcae-141">Note that matching has not been performed since you made the changes.</span></span>  
13. <span data-ttu-id="7fcae-142">Fare clic su **Aggiorna stato di abbinamento**.</span><span class="sxs-lookup"><span data-stu-id="7fcae-142">Click **Update match status**.</span></span>
14. <span data-ttu-id="7fcae-143">Nel riquadro azioni fare clic su **Revisione**.</span><span class="sxs-lookup"><span data-stu-id="7fcae-143">On the Action Pane, click **Review**.</span></span>
15. <span data-ttu-id="7fcae-144">Fare clic su **Dettagli abbinamento**.</span><span class="sxs-lookup"><span data-stu-id="7fcae-144">Click **Matching details**.</span></span> <span data-ttu-id="7fcae-145">La nuova riga con i servizi non deve essere abbinata, quindi lo stato rimane "Non eseguito".</span><span class="sxs-lookup"><span data-stu-id="7fcae-145">The new line with services does not need to be matched so the status stays "Not performed".</span></span>  
16. <span data-ttu-id="7fcae-146">Selezionare l'entrata prodotti per l'articolo di magazzino ricevuto.</span><span class="sxs-lookup"><span data-stu-id="7fcae-146">Select the product receipt for the inventory item that you received.</span></span> <span data-ttu-id="7fcae-147">La riga con l'entrata prodotti è stata abbinata, ma la quantità o il prezzo non sono corrispondenti e pertanto restituisce l'esito negativo.</span><span class="sxs-lookup"><span data-stu-id="7fcae-147">The line with the product receipt was matched but there is a mismatch of quantity or price so it fails.</span></span>  
17. <span data-ttu-id="7fcae-148">Immettere un numero nel campo **Prezzo unitario**.</span><span class="sxs-lookup"><span data-stu-id="7fcae-148">In the **Unit price** field, enter a number.</span></span> <span data-ttu-id="7fcae-149">Ora che il prezzo unitario corrisponde, lo stato verrà aggiornato su Superato.</span><span class="sxs-lookup"><span data-stu-id="7fcae-149">Now that the unit price matches, the status is updated to Passed.</span></span> <span data-ttu-id="7fcae-150">Se i criteri consentono le discrepanze o se la corrispondenza è solo un avviso, è comunque possibile registrare la fattura.</span><span class="sxs-lookup"><span data-stu-id="7fcae-150">If your policy allows discrepancies or if matching is only a warning, you can still post the invoice.</span></span>  
18. <span data-ttu-id="7fcae-151">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="7fcae-151">Close the page.</span></span>
19. <span data-ttu-id="7fcae-152">Fare clic su **Registra**.</span><span class="sxs-lookup"><span data-stu-id="7fcae-152">Click **Post**.</span></span>
20. <span data-ttu-id="7fcae-153">Chiudere il modulo.</span><span class="sxs-lookup"><span data-stu-id="7fcae-153">Close the form.</span></span> <span data-ttu-id="7fcae-154">Si noti che l'ordine fornitore non è più elencato come ricevuto ma come non fatturato.</span><span class="sxs-lookup"><span data-stu-id="7fcae-154">Note that the purchase order is no longer listed as received but not invoiced.</span></span>  

