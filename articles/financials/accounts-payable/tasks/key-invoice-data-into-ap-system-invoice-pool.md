--- 
title: "Inserire dati fattura nel sistema di contabilità fornitore tramite un pool di fatture"
description: "Questa guida attività indicherà come utilizzare il registro fatture per creare le fatture."
author: abruer
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: 4b4e9a52a383d4acc0bf2adc669fd88c0c0f7402
ms.contentlocale: it-it
ms.lasthandoff: 08/07/2018

---
# <a name="key-invoice-data-into-the-ap-system-using-invoice-pool"></a><span data-ttu-id="f8ee6-103">Inserire dati fattura nel sistema di contabilità fornitore tramite un pool di fatture</span><span class="sxs-lookup"><span data-stu-id="f8ee6-103">Key invoice data into the AP system using invoice pool</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="f8ee6-104">Questa guida attività indicherà come utilizzare il registro fatture per creare le fatture.</span><span class="sxs-lookup"><span data-stu-id="f8ee6-104">This task guide will show you how to use the invoice register to create invoices.</span></span>  <span data-ttu-id="f8ee6-105">Utilizzare quindi il pool di fatture per abbinare la fattura a un ordine fornitore e per finalizzare la spesa nella pagina della fattura fornitore.</span><span class="sxs-lookup"><span data-stu-id="f8ee6-105">Then use the invoice pool to match the invoice to a purchase order and finalize the expense in the vendor invoice page.</span></span>


## <a name="create-a-purchase-order"></a><span data-ttu-id="f8ee6-106">Creare un ordine fornitore</span><span class="sxs-lookup"><span data-stu-id="f8ee6-106">Create a purchase order</span></span>
1. <span data-ttu-id="f8ee6-107">Fare clic su Contabilità fornitori > Ordini fornitore > Ordini fornitore.</span><span class="sxs-lookup"><span data-stu-id="f8ee6-107">Go to Accounts payable > Purchase orders > Purchase orders.</span></span>
2. <span data-ttu-id="f8ee6-108">Fare clic su Nuovo per creare un nuovo ordine fornitore.</span><span class="sxs-lookup"><span data-stu-id="f8ee6-108">Click New to create a purchase order.</span></span>
3. <span data-ttu-id="f8ee6-109">Nel campo Conto fornitore fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="f8ee6-109">In the Vendor account field, click the drop down button to open the lookup.</span></span>
4. <span data-ttu-id="f8ee6-110">Selezionare il fornitore dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="f8ee6-110">Select the vendor from the list.</span></span> <span data-ttu-id="f8ee6-111">Ad esempio, il fornitore 1001.</span><span class="sxs-lookup"><span data-stu-id="f8ee6-111">For example, vendor 1001.</span></span>
5. <span data-ttu-id="f8ee6-112">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="f8ee6-112">Click OK.</span></span>
6. <span data-ttu-id="f8ee6-113">Nel campo Numero articolo fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="f8ee6-113">In the Item number field, click the drop down button to open the lookup.</span></span>
7. <span data-ttu-id="f8ee6-114">Individuare il numero di articolo servizi nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="f8ee6-114">Find the services item number in the list.</span></span> <span data-ttu-id="f8ee6-115">Selezionare, ad esempio S0001.</span><span class="sxs-lookup"><span data-stu-id="f8ee6-115">For example, select S0001.</span></span>
8. <span data-ttu-id="f8ee6-116">Fare clic sul numero di articolo e selezionarlo.</span><span class="sxs-lookup"><span data-stu-id="f8ee6-116">Click on the item number and select it.</span></span>
    * <span data-ttu-id="f8ee6-117">L'importo netto è 75,00.</span><span class="sxs-lookup"><span data-stu-id="f8ee6-117">The net amount is 75.00.</span></span>  <span data-ttu-id="f8ee6-118">Si tratta dell'importo previsto nella fattura.</span><span class="sxs-lookup"><span data-stu-id="f8ee6-118">That is the amount that we will expect on the invoice.</span></span>  
9. <span data-ttu-id="f8ee6-119">Nel riquadro azioni fare clic su Acquisti.</span><span class="sxs-lookup"><span data-stu-id="f8ee6-119">On the action pane, click Purchase.</span></span>
10. <span data-ttu-id="f8ee6-120">Fare clic su Conferma.</span><span class="sxs-lookup"><span data-stu-id="f8ee6-120">Click Confirm.</span></span>

## <a name="create-and-post-and-invoice"></a><span data-ttu-id="f8ee6-121">Creare e registrare una fattura</span><span class="sxs-lookup"><span data-stu-id="f8ee6-121">Create and post and invoice</span></span>
1. <span data-ttu-id="f8ee6-122">Andare a Contabilità fornitori > Fatture > Registro fatture.</span><span class="sxs-lookup"><span data-stu-id="f8ee6-122">Go to Accounts payable > Invoices > Invoice register.</span></span>
2. <span data-ttu-id="f8ee6-123">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="f8ee6-123">Click New.</span></span>
3. <span data-ttu-id="f8ee6-124">Aprire la ricerca per selezionare il nome del registro fatture che si desidera utilizzare.</span><span class="sxs-lookup"><span data-stu-id="f8ee6-124">Open the lookup to select the name of the invoice register that you want to use.</span></span>
4. <span data-ttu-id="f8ee6-125">Selezionare il nome del registro fatture che si desidera utilizzare.</span><span class="sxs-lookup"><span data-stu-id="f8ee6-125">Select the name of the invoice register that you want to use.</span></span>
5. <span data-ttu-id="f8ee6-126">Fare clic su Righe per aprire il registro e immettere le righe di spesa.</span><span class="sxs-lookup"><span data-stu-id="f8ee6-126">Click on Lines to open the register and enter expense lines.</span></span>
6. <span data-ttu-id="f8ee6-127">Nella ricerca selezionare un fornitore.</span><span class="sxs-lookup"><span data-stu-id="f8ee6-127">In the lookup, select a vendor.</span></span> <span data-ttu-id="f8ee6-128">Ad esempio, fare clic sul fornitore 1001.</span><span class="sxs-lookup"><span data-stu-id="f8ee6-128">For example, click on vendor 1001.</span></span>
7. <span data-ttu-id="f8ee6-129">Nel campo Fattura immettere il numero di fattura.</span><span class="sxs-lookup"><span data-stu-id="f8ee6-129">In the Invoice field, enter the invoice number.</span></span>
8. <span data-ttu-id="f8ee6-130">Digitare un valore nel campo Descrizione.</span><span class="sxs-lookup"><span data-stu-id="f8ee6-130">In the Description field, type a value.</span></span>
9. <span data-ttu-id="f8ee6-131">Nel campo Credito immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="f8ee6-131">In the Credit field, enter a number.</span></span>
10. <span data-ttu-id="f8ee6-132">Nel campo Ordine fornitore fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="f8ee6-132">In the Purchase order field, click the drop down button to open the lookup.</span></span>
11. <span data-ttu-id="f8ee6-133">Selezionare l'ordine fornitore creato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="f8ee6-133">Select the purchase order that you created earlier.</span></span>
12. <span data-ttu-id="f8ee6-134">Nel campo Approvata da fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="f8ee6-134">In the Approved by field, click the drop down button to open the lookup.</span></span>
13. <span data-ttu-id="f8ee6-135">Evidenzi un approvatore e fare clic su per selezionare tale approvatore.</span><span class="sxs-lookup"><span data-stu-id="f8ee6-135">Highlight an approver and click Select to select that approver.</span></span>
14. <span data-ttu-id="f8ee6-136">Fare clic su Registra.</span><span class="sxs-lookup"><span data-stu-id="f8ee6-136">Click Post.</span></span>
15. <span data-ttu-id="f8ee6-137">Chiudere il modulo.</span><span class="sxs-lookup"><span data-stu-id="f8ee6-137">Close the form.</span></span>
16. <span data-ttu-id="f8ee6-138">Chiudere il modulo.</span><span class="sxs-lookup"><span data-stu-id="f8ee6-138">Close the form.</span></span>

## <a name="open-an-invoice-from-the-pool-and-match-it-to-a-purchase-order-to-complete-the-invoice-process"></a><span data-ttu-id="f8ee6-139">Aprire una fattura dal pool e abbinarla a un ordine fornitore per completare il processo di fatturazione</span><span class="sxs-lookup"><span data-stu-id="f8ee6-139">Open an invoice from the pool and match it to a purchase order to complete the invoice process</span></span>
1. <span data-ttu-id="f8ee6-140">Andare a Contabilità fornitori > Fatture > Pool fatture.</span><span class="sxs-lookup"><span data-stu-id="f8ee6-140">Go to Accounts payable > Invoices > Invoice pool.</span></span>
2. <span data-ttu-id="f8ee6-141">Fare clic su Ordine fornitore per creare una fattura fornitore dalla fattura nel pool.</span><span class="sxs-lookup"><span data-stu-id="f8ee6-141">Click Purchase order to create a vendor invoice from the invoice in the pool.</span></span>
3. <span data-ttu-id="f8ee6-142">Selezionare la fattura che si desidera rivedere.</span><span class="sxs-lookup"><span data-stu-id="f8ee6-142">Select the invoice that you want to review.</span></span>
4. <span data-ttu-id="f8ee6-143">Fare clic su Aggiorna stato di abbinamento per completare la l'abbinamento.</span><span class="sxs-lookup"><span data-stu-id="f8ee6-143">Click Update match status to complete the matching.</span></span>
5. <span data-ttu-id="f8ee6-144">Nel riquadro azioni fare clic su Opzioni.</span><span class="sxs-lookup"><span data-stu-id="f8ee6-144">On the action pane, click Options.</span></span>
6. <span data-ttu-id="f8ee6-145">Fare clic su Cambia visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="f8ee6-145">Click Change view.</span></span>
7. <span data-ttu-id="f8ee6-146">Fare clic su Visualizzazione griglia.</span><span class="sxs-lookup"><span data-stu-id="f8ee6-146">Click Grid view.</span></span>
8. <span data-ttu-id="f8ee6-147">Fare clic su Registra.</span><span class="sxs-lookup"><span data-stu-id="f8ee6-147">Click Post.</span></span>
9. <span data-ttu-id="f8ee6-148">Chiudere il modulo.</span><span class="sxs-lookup"><span data-stu-id="f8ee6-148">Close the form.</span></span>
10. <span data-ttu-id="f8ee6-149">Passare a Contabilità fornitori > Fornitori > Fornitori.</span><span class="sxs-lookup"><span data-stu-id="f8ee6-149">Go to Accounts payable > Vendors > Vendors.</span></span>
11. <span data-ttu-id="f8ee6-150">Selezionare il fornitore dell'ordine fornitore.</span><span class="sxs-lookup"><span data-stu-id="f8ee6-150">Select the vendor that was on the purchase order.</span></span> <span data-ttu-id="f8ee6-151">Selezionare, ad esempio, il fornitore 1001.</span><span class="sxs-lookup"><span data-stu-id="f8ee6-151">For example, select vendor 1001.</span></span>
12. <span data-ttu-id="f8ee6-152">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="f8ee6-152">In the list, click the link in the selected row.</span></span>
13. <span data-ttu-id="f8ee6-153">Nel riquadro azioni, fare clic su Fornitore.</span><span class="sxs-lookup"><span data-stu-id="f8ee6-153">On the action pane, click Vendor.</span></span>
14. <span data-ttu-id="f8ee6-154">Fare clic su Transazioni.</span><span class="sxs-lookup"><span data-stu-id="f8ee6-154">Click Transactions.</span></span>
15. <span data-ttu-id="f8ee6-155">Selezionare la fattura creata.</span><span class="sxs-lookup"><span data-stu-id="f8ee6-155">Select the invoice that you created.</span></span>
    * <span data-ttu-id="f8ee6-156">Il rateo del registro fatture è stato stornato e registrato nel conto spese appropriato.</span><span class="sxs-lookup"><span data-stu-id="f8ee6-156">The invoice register accrual was reversed and posted to the appropriate expense account.</span></span>  


