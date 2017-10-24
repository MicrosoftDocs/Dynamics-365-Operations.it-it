--- 
title: Creare un giornale di registrazione annullamento per un cliente
description: "Questa guida attività indicherà come impostare i parametri per gli annullamenti e come annullare le transazioni nelle pagine Riscossioni, Fatture cliente aperte e Cliente."
author: ShivamPandey-msft
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
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 19a816f04283ce4f200de7396617313e45e057db
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---
# <a name="create-a-write-off-journal-for-a-customer"></a><span data-ttu-id="507bc-103">Creare un giornale di registrazione annullamento per un cliente</span><span class="sxs-lookup"><span data-stu-id="507bc-103">Create a write-off journal for a customer</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="507bc-104">Questa guida attività indicherà come impostare i parametri per gli annullamenti e come annullare le transazioni nelle pagine Riscossioni, Fatture cliente aperte e Cliente.</span><span class="sxs-lookup"><span data-stu-id="507bc-104">This task guide will show you how to set up the parameters for write-offs and then write off transactions from the Collections page, the Open customer invoices page, and the Customer page.</span></span> <span data-ttu-id="507bc-105">In questa attività viene utilizzata la società dimostrativa USMF.</span><span class="sxs-lookup"><span data-stu-id="507bc-105">This task uses the USMF demo company.</span></span>


## <a name="set-up-the-write-off-parameters"></a><span data-ttu-id="507bc-106">Impostare i parametri di annullamento</span><span class="sxs-lookup"><span data-stu-id="507bc-106">Set up the write off parameters</span></span>
1. <span data-ttu-id="507bc-107">Andare a Crediti e riscossioni > Impostazioni > Parametri contabilità clienti.</span><span class="sxs-lookup"><span data-stu-id="507bc-107">Go to Credit and collections > Setup > Accounts receivable parameters.</span></span>
2. <span data-ttu-id="507bc-108">Fare clic sulla scheda Riscossioni.</span><span class="sxs-lookup"><span data-stu-id="507bc-108">Click the Collections tab.</span></span>
3. <span data-ttu-id="507bc-109">Espandere o comprimere la sezione Annullamento.</span><span class="sxs-lookup"><span data-stu-id="507bc-109">Expand or collapse the Write-off section.</span></span>
    * <span data-ttu-id="507bc-110">Il giornale di registrazione di annullamento contiene le transazioni di annullamento create.</span><span class="sxs-lookup"><span data-stu-id="507bc-110">The Write-off journal is the general journal that will hold the write-off transactions that you create.</span></span>  
    * <span data-ttu-id="507bc-111">È possibile collegare un codice motivo a ogni annullamento.</span><span class="sxs-lookup"><span data-stu-id="507bc-111">You can attach a reason code to every write-off.</span></span> <span data-ttu-id="507bc-112">È possibile sovrascrivere questo valore predefinito al momento dell'annullamento.</span><span class="sxs-lookup"><span data-stu-id="507bc-112">You can override this default at the time of the write-off.</span></span>  
    * <span data-ttu-id="507bc-113">Impostare questa opzione su Sì se si desidera separare l'IVA dalla transazione originale nell'annullamento.</span><span class="sxs-lookup"><span data-stu-id="507bc-113">Set this to Yes if you want to separate the sales tax from the original transaction in the write-off.</span></span>  
4. <span data-ttu-id="507bc-114">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="507bc-114">Close the page.</span></span>
5. <span data-ttu-id="507bc-115">Andare a Crediti e riscossioni > Impostazioni > Profili di registrazione cliente.</span><span class="sxs-lookup"><span data-stu-id="507bc-115">Go to Credit and collections > Setup > Customer posting profiles.</span></span>
    * <span data-ttu-id="507bc-116">Il conto di annullamento verrà utilizzato come rettifica del conto spese o di prenotazione nel giornale di registrazione generale</span><span class="sxs-lookup"><span data-stu-id="507bc-116">The write-off account will be used as the expense account or reserve adjustment in the general journal</span></span>   
6. <span data-ttu-id="507bc-117">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="507bc-117">Close the page.</span></span>

## <a name="write-off-a-customer-balance-from-the-aged-balances-page"></a><span data-ttu-id="507bc-118">Annullare il saldo di un cliente dalla pagina dei saldi con aging</span><span class="sxs-lookup"><span data-stu-id="507bc-118">Write off a customer balance from the aged balances page</span></span>
1. <span data-ttu-id="507bc-119">Andare a Crediti e riscossioni > Riscossioni > Saldi con aging.</span><span class="sxs-lookup"><span data-stu-id="507bc-119">Go to Credit and collections > Collections > Aged balances.</span></span>
2. <span data-ttu-id="507bc-120">Contrassegnare la riga per il cliente per cui si desidera eseguire l'annullamento.</span><span class="sxs-lookup"><span data-stu-id="507bc-120">Mark the row for the customer that you want to write off.</span></span> <span data-ttu-id="507bc-121">Ad esempio, contrassegnare la riga con Birch Company.</span><span class="sxs-lookup"><span data-stu-id="507bc-121">For example, mark the line with Birch Company on it.</span></span>
3. <span data-ttu-id="507bc-122">Nel riquadro azioni fare clic su Raccolta.</span><span class="sxs-lookup"><span data-stu-id="507bc-122">On the Action Pane, click Collect.</span></span>
4. <span data-ttu-id="507bc-123">Fare clic su Annullare.</span><span class="sxs-lookup"><span data-stu-id="507bc-123">Click Write off.</span></span>
5. <span data-ttu-id="507bc-124">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="507bc-124">Click OK.</span></span>
6. <span data-ttu-id="507bc-125">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="507bc-125">Close the page.</span></span>
7. <span data-ttu-id="507bc-126">Fare clic su Contabilità generale > Scritture contabili > Giornali di registrazione generali.</span><span class="sxs-lookup"><span data-stu-id="507bc-126">Go to General ledger > Journal entries > General journals.</span></span>
8. <span data-ttu-id="507bc-127">Selezionare il numero batch del giornale di registrazione contenente l'annullamento.</span><span class="sxs-lookup"><span data-stu-id="507bc-127">Select the journal batch number for the journal that contains your write-off.</span></span>
    * <span data-ttu-id="507bc-128">Una riga viene creata per stornare il saldo del cliente.</span><span class="sxs-lookup"><span data-stu-id="507bc-128">One line is created to reverse the customer balance.</span></span> <span data-ttu-id="507bc-129">Una o più righe vengono create per registrare l'annullamento nel conto relativo.</span><span class="sxs-lookup"><span data-stu-id="507bc-129">One or more lines are created to post the write-off to the write-off account.</span></span>  
9. <span data-ttu-id="507bc-130">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="507bc-130">Close the page.</span></span>
10. <span data-ttu-id="507bc-131">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="507bc-131">Close the page.</span></span>

## <a name="write-off-transactions-from-the-collections-form"></a><span data-ttu-id="507bc-132">Annullare transazioni nel modulo delle riscossioni.</span><span class="sxs-lookup"><span data-stu-id="507bc-132">Write off transactions from the collections form.</span></span>
1. <span data-ttu-id="507bc-133">Andare a Crediti e riscossioni > Riscossioni > Saldi con aging.</span><span class="sxs-lookup"><span data-stu-id="507bc-133">Go to Credit and collections > Collections > Aged balances.</span></span>
2. <span data-ttu-id="507bc-134">Selezionare il nome del cliente a cui sono associate le transazioni che si desidera annullare.</span><span class="sxs-lookup"><span data-stu-id="507bc-134">Select the name of the customer that has the transactions that you want to write off.</span></span> <span data-ttu-id="507bc-135">Ad esempio, selezionare Cave Wholesales (US-004).</span><span class="sxs-lookup"><span data-stu-id="507bc-135">For example, select Cave Wholesales (US-004).</span></span>
3. <span data-ttu-id="507bc-136">Contrassegnare la riga per la prima transazione.</span><span class="sxs-lookup"><span data-stu-id="507bc-136">Mark the row for the first transaction.</span></span>
4. <span data-ttu-id="507bc-137">Contrassegnare la riga per la seconda transazione.</span><span class="sxs-lookup"><span data-stu-id="507bc-137">Mark the row for the second transaction.</span></span>
5. <span data-ttu-id="507bc-138">Fare clic su Annullare.</span><span class="sxs-lookup"><span data-stu-id="507bc-138">Click Write off.</span></span>
6. <span data-ttu-id="507bc-139">Nel campo Commento motivo digitare "Crediti inesigibili".</span><span class="sxs-lookup"><span data-stu-id="507bc-139">In the Reason comment field, type 'Bad debts'.</span></span>
7. <span data-ttu-id="507bc-140">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="507bc-140">Click OK.</span></span>
8. <span data-ttu-id="507bc-141">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="507bc-141">Close the page.</span></span>
9. <span data-ttu-id="507bc-142">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="507bc-142">Close the page.</span></span>
10. <span data-ttu-id="507bc-143">Fare clic su Contabilità generale > Scritture contabili > Giornali di registrazione generali.</span><span class="sxs-lookup"><span data-stu-id="507bc-143">Go to General ledger > Journal entries > General journals.</span></span>
11. <span data-ttu-id="507bc-144">Selezionare il numero batch del giornale di registrazione contenente l'annullamento.</span><span class="sxs-lookup"><span data-stu-id="507bc-144">Select the journal batch number for the journal that contains your write-off.</span></span>
    * <span data-ttu-id="507bc-145">Una riga viene creata per stornare il saldo del cliente.</span><span class="sxs-lookup"><span data-stu-id="507bc-145">One line is created to reverse the customer balance.</span></span> <span data-ttu-id="507bc-146">Una o più righe vengono create per registrare l'annullamento nel conto relativo.</span><span class="sxs-lookup"><span data-stu-id="507bc-146">One or more lines are created to post the write-off to the write-off account.</span></span>  
12. <span data-ttu-id="507bc-147">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="507bc-147">Close the page.</span></span>
13. <span data-ttu-id="507bc-148">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="507bc-148">Close the page.</span></span>

## <a name="write-off-an-invoice-from-the-open-customers-invoices-page"></a><span data-ttu-id="507bc-149">Annullare una fattura nella pagina Fatture cliente aperte</span><span class="sxs-lookup"><span data-stu-id="507bc-149">Write off an invoice from the Open customers invoices page</span></span>
1. <span data-ttu-id="507bc-150">Andare a Contabilità clienti > Fatture > Fatture cliente aperte.</span><span class="sxs-lookup"><span data-stu-id="507bc-150">Go to Accounts receivable > Invoices > Open customer invoices.</span></span>
2. <span data-ttu-id="507bc-151">Contrassegnare la riga per una fattura.</span><span class="sxs-lookup"><span data-stu-id="507bc-151">Mark the line for an invoice.</span></span> <span data-ttu-id="507bc-152">Ad esempio, contrassegnare la riga per CIV-000667.</span><span class="sxs-lookup"><span data-stu-id="507bc-152">For example, mark the line for CIV-000667.</span></span>
3. <span data-ttu-id="507bc-153">Nel riquadro azioni fare clic su Fattura.</span><span class="sxs-lookup"><span data-stu-id="507bc-153">On the Action Pane, click Invoice.</span></span>
4. <span data-ttu-id="507bc-154">Fare clic su Annullare.</span><span class="sxs-lookup"><span data-stu-id="507bc-154">Click Write off.</span></span>
5. <span data-ttu-id="507bc-155">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="507bc-155">Click OK.</span></span>
6. <span data-ttu-id="507bc-156">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="507bc-156">Close the page.</span></span>

## <a name="write-off-a-customer-balance-from-the-customer-page"></a><span data-ttu-id="507bc-157">Annullare un saldo cliente dalla pagina clienti</span><span class="sxs-lookup"><span data-stu-id="507bc-157">Write off a customer balance from the customer page</span></span>
1. <span data-ttu-id="507bc-158">Andare a Contabilità clienti > Clienti > Tutti i clienti.</span><span class="sxs-lookup"><span data-stu-id="507bc-158">Go to Accounts receivable > Customers > All customers.</span></span>
2. <span data-ttu-id="507bc-159">Selezionare un account cliente.</span><span class="sxs-lookup"><span data-stu-id="507bc-159">Select a customer account.</span></span> <span data-ttu-id="507bc-160">Ad esempio, selezionare US-001 (Contoso Retail San Diego).</span><span class="sxs-lookup"><span data-stu-id="507bc-160">For example, select US-001 (Contoso Retail San Diego).</span></span>
3. <span data-ttu-id="507bc-161">Nel riquadro azioni fare clic su Raccolta.</span><span class="sxs-lookup"><span data-stu-id="507bc-161">On the Action Pane, click Collect.</span></span>
4. <span data-ttu-id="507bc-162">Fare clic su Annullare.</span><span class="sxs-lookup"><span data-stu-id="507bc-162">Click Write off.</span></span>
5. <span data-ttu-id="507bc-163">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="507bc-163">Click OK.</span></span>
6. <span data-ttu-id="507bc-164">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="507bc-164">Close the page.</span></span>


