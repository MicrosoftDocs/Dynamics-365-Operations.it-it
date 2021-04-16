---
title: Creare un giornale di registrazione annullamento per un cliente
description: Questa guida attività indicherà come impostare i parametri per gli annullamenti e come annullare le transazioni nelle pagine Riscossioni, Fatture cliente aperte e Cliente.
author: ShivamPandey-msft
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: CustParameters, CustPosting, DefaultDashboard, CustCollectionsPoolsListPage, CustWriteOff, LedgerJournalTable, LedgerJournalTransDaily, CustCollections, CustOpenInvoicesListPage, CustTable
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 857d3a224f35c4eeedbf4913aea14011091d5466
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5823121"
---
# <a name="create-a-write-off-journal-for-a-customer"></a><span data-ttu-id="0843d-103">Creare un giornale di registrazione annullamento per un cliente</span><span class="sxs-lookup"><span data-stu-id="0843d-103">Create a write-off journal for a customer</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="0843d-104">Questa guida attività indicherà come impostare i parametri per gli annullamenti e come annullare le transazioni nelle pagine Riscossioni, Fatture cliente aperte e Cliente.</span><span class="sxs-lookup"><span data-stu-id="0843d-104">This task guide will show you how to set up the parameters for write-offs and then write off transactions from the Collections page, the Open customer invoices page, and the Customer page.</span></span> <span data-ttu-id="0843d-105">In questa attività viene utilizzata la società dimostrativa USMF.</span><span class="sxs-lookup"><span data-stu-id="0843d-105">This task uses the USMF demo company.</span></span>


## <a name="set-up-the-write-off-parameters"></a><span data-ttu-id="0843d-106">Impostare i parametri di annullamento</span><span class="sxs-lookup"><span data-stu-id="0843d-106">Set up the write off parameters</span></span>
1. <span data-ttu-id="0843d-107">Andare a **Pannello di navigazione > Moduli > Crediti e riscossioni > Impostazione > Parametri contabilità clienti**.</span><span class="sxs-lookup"><span data-stu-id="0843d-107">Go to **Navigation pane > Modules > Credit and collections > Setup > Accounts receivable parameters**.</span></span>
2. <span data-ttu-id="0843d-108">Fare clic sulla scheda **Riscossioni**.</span><span class="sxs-lookup"><span data-stu-id="0843d-108">Click the **Collections** tab.</span></span>
3. <span data-ttu-id="0843d-109">Espandere o comprimere la sezione **Annullamento**</span><span class="sxs-lookup"><span data-stu-id="0843d-109">Expand or collapse the **Write-off** section.</span></span>
    - <span data-ttu-id="0843d-110">Il **giornale di registrazione annullamento** è il giornale di registrazione generale che contiene le transazioni di annullamento create.</span><span class="sxs-lookup"><span data-stu-id="0843d-110">The **Write-off journal** is the general journal that will hold the write-off transactions that you create.</span></span>  
    - <span data-ttu-id="0843d-111">È possibile collegare un codice motivo a ogni annullamento.</span><span class="sxs-lookup"><span data-stu-id="0843d-111">You can attach a reason code to every write-off.</span></span> <span data-ttu-id="0843d-112">È possibile sovrascrivere questo valore predefinito al momento dell'annullamento.</span><span class="sxs-lookup"><span data-stu-id="0843d-112">You can override this default at the time of the write-off.</span></span>  
    - <span data-ttu-id="0843d-113">Impostare **IVA separata** su Sì se si desidera separare l'IVA dalla transazione originale nell'annullamento.</span><span class="sxs-lookup"><span data-stu-id="0843d-113">Set the **Separate sales tax** to Yes if you want to separate the sales tax from the original transaction in the write-off.</span></span>  
4. <span data-ttu-id="0843d-114">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="0843d-114">Close the page.</span></span>
5. <span data-ttu-id="0843d-115">Andare a **Crediti e riscossioni > Impostazione > Profili di registrazione cliente**.</span><span class="sxs-lookup"><span data-stu-id="0843d-115">Go to **Credit and collections > Setup > Customer posting profiles**.</span></span> <span data-ttu-id="0843d-116">Il conto di annullamento verrà utilizzato come rettifica del conto spese o di prenotazione nel giornale di registrazione generale.</span><span class="sxs-lookup"><span data-stu-id="0843d-116">The write-off account will be used as the expense account or reserve adjustment in the general journal.</span></span>
6. <span data-ttu-id="0843d-117">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="0843d-117">Close the page.</span></span>

## <a name="write-off-a-customer-balance-from-the-aged-balances-page"></a><span data-ttu-id="0843d-118">Annullare il saldo di un cliente dalla pagina dei saldi con aging</span><span class="sxs-lookup"><span data-stu-id="0843d-118">Write off a customer balance from the aged balances page</span></span>
1. <span data-ttu-id="0843d-119">Andare a **Crediti e riscossioni > Riscossioni > Saldi con aging**.</span><span class="sxs-lookup"><span data-stu-id="0843d-119">Go to **Credit and collections > Collections > Aged balances**.</span></span>
2. <span data-ttu-id="0843d-120">Contrassegnare la riga per il cliente per cui si desidera eseguire l'annullamento.</span><span class="sxs-lookup"><span data-stu-id="0843d-120">Mark the row for the customer that you want to write off.</span></span> <span data-ttu-id="0843d-121">Ad esempio, contrassegnare la riga con Birch Company.</span><span class="sxs-lookup"><span data-stu-id="0843d-121">For example, mark the line with Birch Company on it.</span></span>
3. <span data-ttu-id="0843d-122">Nel **riquadro azioni** fare clic su **Raccolta**.</span><span class="sxs-lookup"><span data-stu-id="0843d-122">On the **Action Pane**, click **Collect**.</span></span>
4. <span data-ttu-id="0843d-123">Fare clic su **Annullare**.</span><span class="sxs-lookup"><span data-stu-id="0843d-123">Click **Write off**.</span></span>
5. <span data-ttu-id="0843d-124">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="0843d-124">Click **OK**.</span></span>
6. <span data-ttu-id="0843d-125">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="0843d-125">Close the page.</span></span>
7. <span data-ttu-id="0843d-126">Andare a **Pannello di navigazione > Moduli > Contabilità generale > Inserimenti nel giornale di registrazione > Giornali di registrazione generali**.</span><span class="sxs-lookup"><span data-stu-id="0843d-126">Go to **Navigation pane > Modules > General ledger > Journal entries > General journals**.</span></span>
8. <span data-ttu-id="0843d-127">Selezionare il numero batch del giornale di registrazione contenente l'annullamento.</span><span class="sxs-lookup"><span data-stu-id="0843d-127">Select the journal batch number for the journal that contains your write-off.</span></span> <span data-ttu-id="0843d-128">Una riga viene creata per stornare il saldo del cliente.</span><span class="sxs-lookup"><span data-stu-id="0843d-128">One line is created to reverse the customer balance.</span></span> <span data-ttu-id="0843d-129">Una o più righe vengono create per registrare l'annullamento nel conto relativo.</span><span class="sxs-lookup"><span data-stu-id="0843d-129">One or more lines are created to post the write-off to the write-off account.</span></span>  
9. <span data-ttu-id="0843d-130">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="0843d-130">Close the page.</span></span>
10. <span data-ttu-id="0843d-131">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="0843d-131">Close the page.</span></span>

## <a name="write-off-transactions-from-the-collections-form"></a><span data-ttu-id="0843d-132">Annullare transazioni nel modulo delle riscossioni.</span><span class="sxs-lookup"><span data-stu-id="0843d-132">Write off transactions from the collections form.</span></span>
1. <span data-ttu-id="0843d-133">Andare a **Crediti e riscossioni > Riscossioni > Saldi con aging**.</span><span class="sxs-lookup"><span data-stu-id="0843d-133">Go to **Credit and collections > Collections > Aged balances**.</span></span>
2. <span data-ttu-id="0843d-134">Selezionare il nome del cliente a cui sono associate le transazioni che si desidera annullare.</span><span class="sxs-lookup"><span data-stu-id="0843d-134">Select the name of the customer that has the transactions that you want to write off.</span></span> <span data-ttu-id="0843d-135">Ad esempio, selezionare Cave Wholesales (US-004).</span><span class="sxs-lookup"><span data-stu-id="0843d-135">For example, select Cave Wholesales (US-004).</span></span>
3. <span data-ttu-id="0843d-136">Contrassegnare la riga per la prima transazione.</span><span class="sxs-lookup"><span data-stu-id="0843d-136">Mark the row for the first transaction.</span></span>
4. <span data-ttu-id="0843d-137">Contrassegnare la riga per la seconda transazione.</span><span class="sxs-lookup"><span data-stu-id="0843d-137">Mark the row for the second transaction.</span></span>
5. <span data-ttu-id="0843d-138">Fare clic su **Annullare**.</span><span class="sxs-lookup"><span data-stu-id="0843d-138">Click **Write off**.</span></span>
6. <span data-ttu-id="0843d-139">Nel campo **Commento motivo** digitare "Crediti inesigibili".</span><span class="sxs-lookup"><span data-stu-id="0843d-139">In the **Reason comment** field, type 'Bad debts'.</span></span>
7. <span data-ttu-id="0843d-140">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="0843d-140">Click **OK**.</span></span>
8. <span data-ttu-id="0843d-141">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="0843d-141">Close the page.</span></span>
9. <span data-ttu-id="0843d-142">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="0843d-142">Close the page.</span></span>
10. <span data-ttu-id="0843d-143">Fare clic su **Contabilità generale > Scritture contabili > Giornali di registrazione generali**.</span><span class="sxs-lookup"><span data-stu-id="0843d-143">Go to **General ledger > Journal entries > General journals**.</span></span>
11. <span data-ttu-id="0843d-144">Selezionare il numero batch del giornale di registrazione contenente l'annullamento.</span><span class="sxs-lookup"><span data-stu-id="0843d-144">Select the journal batch number for the journal that contains your write-off.</span></span> <span data-ttu-id="0843d-145">Una riga viene creata per stornare il saldo del cliente.</span><span class="sxs-lookup"><span data-stu-id="0843d-145">One line is created to reverse the customer balance.</span></span> <span data-ttu-id="0843d-146">Una o più righe vengono create per registrare l'annullamento nel conto relativo.</span><span class="sxs-lookup"><span data-stu-id="0843d-146">One or more lines are created to post the write-off to the write-off account.</span></span>  
12. <span data-ttu-id="0843d-147">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="0843d-147">Close the page.</span></span>
13. <span data-ttu-id="0843d-148">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="0843d-148">Close the page.</span></span>

## <a name="write-off-an-invoice-from-the-open-customers-invoices-page"></a><span data-ttu-id="0843d-149">Annullare una fattura nella pagina Fatture cliente aperte</span><span class="sxs-lookup"><span data-stu-id="0843d-149">Write off an invoice from the Open customers invoices page</span></span>
1. <span data-ttu-id="0843d-150">Andare a **Pannello di navigazione > Moduli > Contabilità clienti > Fatture > Fatture cliente aperte**.</span><span class="sxs-lookup"><span data-stu-id="0843d-150">Go to **Navigation pane > Modules > Accounts receivable > Invoices > Open customer invoices**.</span></span>
2. <span data-ttu-id="0843d-151">Contrassegnare la riga per una fattura.</span><span class="sxs-lookup"><span data-stu-id="0843d-151">Mark the line for an invoice.</span></span> <span data-ttu-id="0843d-152">Ad esempio, contrassegnare la riga per CIV-000667.</span><span class="sxs-lookup"><span data-stu-id="0843d-152">For example, mark the line for CIV-000667.</span></span>
3. <span data-ttu-id="0843d-153">Nel **riquadro azioni** fare clic su **Fattura**.</span><span class="sxs-lookup"><span data-stu-id="0843d-153">On the **Action Pane**, click **Invoice**.</span></span>
4. <span data-ttu-id="0843d-154">Fare clic su **Annulla**.</span><span class="sxs-lookup"><span data-stu-id="0843d-154">Click **Write off**.</span></span>
5. <span data-ttu-id="0843d-155">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="0843d-155">Click **OK**.</span></span>
6. <span data-ttu-id="0843d-156">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="0843d-156">Close the page.</span></span>

## <a name="write-off-a-customer-balance-from-the-customer-page"></a><span data-ttu-id="0843d-157">Annullare un saldo cliente dalla pagina clienti</span><span class="sxs-lookup"><span data-stu-id="0843d-157">Write off a customer balance from the customer page</span></span>
1. <span data-ttu-id="0843d-158">Andare a **Contabilità clienti > Clienti > Tutti i clienti**.</span><span class="sxs-lookup"><span data-stu-id="0843d-158">Go to **Accounts receivable > Customers > All customers**.</span></span>
2. <span data-ttu-id="0843d-159">Selezionare un account cliente.</span><span class="sxs-lookup"><span data-stu-id="0843d-159">Select a customer account.</span></span> <span data-ttu-id="0843d-160">Ad esempio, selezionare US-001 (Contoso Retail San Diego).</span><span class="sxs-lookup"><span data-stu-id="0843d-160">For example, select US-001 (Contoso Retail San Diego).</span></span>
3. <span data-ttu-id="0843d-161">Nel **riquadro azioni** fare clic su **Raccolta**.</span><span class="sxs-lookup"><span data-stu-id="0843d-161">On the **Action Pane**, click **Collect**.</span></span>
4. <span data-ttu-id="0843d-162">Fare clic su **Annulla**.</span><span class="sxs-lookup"><span data-stu-id="0843d-162">Click **Write off**.</span></span>
5. <span data-ttu-id="0843d-163">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="0843d-163">Click **OK**.</span></span>
6. <span data-ttu-id="0843d-164">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="0843d-164">Close the page.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]