---
title: Creare un giornale di registrazione annullamento per un cliente
description: Questa guida attività indicherà come impostare i parametri per gli annullamenti e come annullare le transazioni nelle pagine Riscossioni, Fatture cliente aperte e Cliente.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustParameters, CustPosting, DefaultDashboard, CustCollectionsPoolsListPage, CustWriteOff, LedgerJournalTable, LedgerJournalTransDaily, CustCollections, CustOpenInvoicesListPage, CustTable
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 182afb5b105fec6dcac323b4f98db5fb7b3e0d68
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5220277"
---
# <a name="create-a-write-off-journal-for-a-customer"></a><span data-ttu-id="47e09-103">Creare un giornale di registrazione annullamento per un cliente</span><span class="sxs-lookup"><span data-stu-id="47e09-103">Create a write-off journal for a customer</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="47e09-104">Questa guida attività indicherà come impostare i parametri per gli annullamenti e come annullare le transazioni nelle pagine Riscossioni, Fatture cliente aperte e Cliente.</span><span class="sxs-lookup"><span data-stu-id="47e09-104">This task guide will show you how to set up the parameters for write-offs and then write off transactions from the Collections page, the Open customer invoices page, and the Customer page.</span></span> <span data-ttu-id="47e09-105">In questa attività viene utilizzata la società dimostrativa USMF.</span><span class="sxs-lookup"><span data-stu-id="47e09-105">This task uses the USMF demo company.</span></span>


## <a name="set-up-the-write-off-parameters"></a><span data-ttu-id="47e09-106">Impostare i parametri di annullamento</span><span class="sxs-lookup"><span data-stu-id="47e09-106">Set up the write off parameters</span></span>
1. <span data-ttu-id="47e09-107">Andare a **Pannello di navigazione > Moduli > Crediti e riscossioni > Impostazione > Parametri contabilità clienti**.</span><span class="sxs-lookup"><span data-stu-id="47e09-107">Go to **Navigation pane > Modules > Credit and collections > Setup > Accounts receivable parameters**.</span></span>
2. <span data-ttu-id="47e09-108">Fare clic sulla scheda **Riscossioni**.</span><span class="sxs-lookup"><span data-stu-id="47e09-108">Click the **Collections** tab.</span></span>
3. <span data-ttu-id="47e09-109">Espandere o comprimere la sezione **Annullamento**</span><span class="sxs-lookup"><span data-stu-id="47e09-109">Expand or collapse the **Write-off** section.</span></span>
    - <span data-ttu-id="47e09-110">Il **giornale di registrazione annullamento** è il giornale di registrazione generale che contiene le transazioni di annullamento create.</span><span class="sxs-lookup"><span data-stu-id="47e09-110">The **Write-off journal** is the general journal that will hold the write-off transactions that you create.</span></span>  
    - <span data-ttu-id="47e09-111">È possibile collegare un codice motivo a ogni annullamento.</span><span class="sxs-lookup"><span data-stu-id="47e09-111">You can attach a reason code to every write-off.</span></span> <span data-ttu-id="47e09-112">È possibile sovrascrivere questo valore predefinito al momento dell'annullamento.</span><span class="sxs-lookup"><span data-stu-id="47e09-112">You can override this default at the time of the write-off.</span></span>  
    - <span data-ttu-id="47e09-113">Impostare **IVA separata** su Sì se si desidera separare l'IVA dalla transazione originale nell'annullamento.</span><span class="sxs-lookup"><span data-stu-id="47e09-113">Set the **Separate sales tax** to Yes if you want to separate the sales tax from the original transaction in the write-off.</span></span>  
4. <span data-ttu-id="47e09-114">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="47e09-114">Close the page.</span></span>
5. <span data-ttu-id="47e09-115">Andare a **Crediti e riscossioni > Impostazione > Profili di registrazione cliente**.</span><span class="sxs-lookup"><span data-stu-id="47e09-115">Go to **Credit and collections > Setup > Customer posting profiles**.</span></span> <span data-ttu-id="47e09-116">Il conto di annullamento verrà utilizzato come rettifica del conto spese o di prenotazione nel giornale di registrazione generale.</span><span class="sxs-lookup"><span data-stu-id="47e09-116">The write-off account will be used as the expense account or reserve adjustment in the general journal.</span></span>
6. <span data-ttu-id="47e09-117">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="47e09-117">Close the page.</span></span>

## <a name="write-off-a-customer-balance-from-the-aged-balances-page"></a><span data-ttu-id="47e09-118">Annullare il saldo di un cliente dalla pagina dei saldi con aging</span><span class="sxs-lookup"><span data-stu-id="47e09-118">Write off a customer balance from the aged balances page</span></span>
1. <span data-ttu-id="47e09-119">Andare a **Crediti e riscossioni > Riscossioni > Saldi con aging**.</span><span class="sxs-lookup"><span data-stu-id="47e09-119">Go to **Credit and collections > Collections > Aged balances**.</span></span>
2. <span data-ttu-id="47e09-120">Contrassegnare la riga per il cliente per cui si desidera eseguire l'annullamento.</span><span class="sxs-lookup"><span data-stu-id="47e09-120">Mark the row for the customer that you want to write off.</span></span> <span data-ttu-id="47e09-121">Ad esempio, contrassegnare la riga con Birch Company.</span><span class="sxs-lookup"><span data-stu-id="47e09-121">For example, mark the line with Birch Company on it.</span></span>
3. <span data-ttu-id="47e09-122">Nel **riquadro azioni** fare clic su **Raccolta**.</span><span class="sxs-lookup"><span data-stu-id="47e09-122">On the **Action Pane**, click **Collect**.</span></span>
4. <span data-ttu-id="47e09-123">Fare clic su **Annullare**.</span><span class="sxs-lookup"><span data-stu-id="47e09-123">Click **Write off**.</span></span>
5. <span data-ttu-id="47e09-124">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="47e09-124">Click **OK**.</span></span>
6. <span data-ttu-id="47e09-125">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="47e09-125">Close the page.</span></span>
7. <span data-ttu-id="47e09-126">Andare a **Pannello di navigazione > Moduli > Contabilità generale > Inserimenti nel giornale di registrazione > Giornali di registrazione generali**.</span><span class="sxs-lookup"><span data-stu-id="47e09-126">Go to **Navigation pane > Modules > General ledger > Journal entries > General journals**.</span></span>
8. <span data-ttu-id="47e09-127">Selezionare il numero batch del giornale di registrazione contenente l'annullamento.</span><span class="sxs-lookup"><span data-stu-id="47e09-127">Select the journal batch number for the journal that contains your write-off.</span></span> <span data-ttu-id="47e09-128">Una riga viene creata per stornare il saldo del cliente.</span><span class="sxs-lookup"><span data-stu-id="47e09-128">One line is created to reverse the customer balance.</span></span> <span data-ttu-id="47e09-129">Una o più righe vengono create per registrare l'annullamento nel conto relativo.</span><span class="sxs-lookup"><span data-stu-id="47e09-129">One or more lines are created to post the write-off to the write-off account.</span></span>  
9. <span data-ttu-id="47e09-130">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="47e09-130">Close the page.</span></span>
10. <span data-ttu-id="47e09-131">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="47e09-131">Close the page.</span></span>

## <a name="write-off-transactions-from-the-collections-form"></a><span data-ttu-id="47e09-132">Annullare transazioni nel modulo delle riscossioni.</span><span class="sxs-lookup"><span data-stu-id="47e09-132">Write off transactions from the collections form.</span></span>
1. <span data-ttu-id="47e09-133">Andare a **Crediti e riscossioni > Riscossioni > Saldi con aging**.</span><span class="sxs-lookup"><span data-stu-id="47e09-133">Go to **Credit and collections > Collections > Aged balances**.</span></span>
2. <span data-ttu-id="47e09-134">Selezionare il nome del cliente a cui sono associate le transazioni che si desidera annullare.</span><span class="sxs-lookup"><span data-stu-id="47e09-134">Select the name of the customer that has the transactions that you want to write off.</span></span> <span data-ttu-id="47e09-135">Ad esempio, selezionare Cave Wholesales (US-004).</span><span class="sxs-lookup"><span data-stu-id="47e09-135">For example, select Cave Wholesales (US-004).</span></span>
3. <span data-ttu-id="47e09-136">Contrassegnare la riga per la prima transazione.</span><span class="sxs-lookup"><span data-stu-id="47e09-136">Mark the row for the first transaction.</span></span>
4. <span data-ttu-id="47e09-137">Contrassegnare la riga per la seconda transazione.</span><span class="sxs-lookup"><span data-stu-id="47e09-137">Mark the row for the second transaction.</span></span>
5. <span data-ttu-id="47e09-138">Fare clic su **Annullare**.</span><span class="sxs-lookup"><span data-stu-id="47e09-138">Click **Write off**.</span></span>
6. <span data-ttu-id="47e09-139">Nel campo **Commento motivo** digitare "Crediti inesigibili".</span><span class="sxs-lookup"><span data-stu-id="47e09-139">In the **Reason comment** field, type 'Bad debts'.</span></span>
7. <span data-ttu-id="47e09-140">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="47e09-140">Click **OK**.</span></span>
8. <span data-ttu-id="47e09-141">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="47e09-141">Close the page.</span></span>
9. <span data-ttu-id="47e09-142">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="47e09-142">Close the page.</span></span>
10. <span data-ttu-id="47e09-143">Fare clic su **Contabilità generale > Scritture contabili > Giornali di registrazione generali**.</span><span class="sxs-lookup"><span data-stu-id="47e09-143">Go to **General ledger > Journal entries > General journals**.</span></span>
11. <span data-ttu-id="47e09-144">Selezionare il numero batch del giornale di registrazione contenente l'annullamento.</span><span class="sxs-lookup"><span data-stu-id="47e09-144">Select the journal batch number for the journal that contains your write-off.</span></span> <span data-ttu-id="47e09-145">Una riga viene creata per stornare il saldo del cliente.</span><span class="sxs-lookup"><span data-stu-id="47e09-145">One line is created to reverse the customer balance.</span></span> <span data-ttu-id="47e09-146">Una o più righe vengono create per registrare l'annullamento nel conto relativo.</span><span class="sxs-lookup"><span data-stu-id="47e09-146">One or more lines are created to post the write-off to the write-off account.</span></span>  
12. <span data-ttu-id="47e09-147">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="47e09-147">Close the page.</span></span>
13. <span data-ttu-id="47e09-148">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="47e09-148">Close the page.</span></span>

## <a name="write-off-an-invoice-from-the-open-customers-invoices-page"></a><span data-ttu-id="47e09-149">Annullare una fattura nella pagina Fatture cliente aperte</span><span class="sxs-lookup"><span data-stu-id="47e09-149">Write off an invoice from the Open customers invoices page</span></span>
1. <span data-ttu-id="47e09-150">Andare a **Pannello di navigazione > Moduli > Contabilità clienti > Fatture > Fatture cliente aperte**.</span><span class="sxs-lookup"><span data-stu-id="47e09-150">Go to **Navigation pane > Modules > Accounts receivable > Invoices > Open customer invoices**.</span></span>
2. <span data-ttu-id="47e09-151">Contrassegnare la riga per una fattura.</span><span class="sxs-lookup"><span data-stu-id="47e09-151">Mark the line for an invoice.</span></span> <span data-ttu-id="47e09-152">Ad esempio, contrassegnare la riga per CIV-000667.</span><span class="sxs-lookup"><span data-stu-id="47e09-152">For example, mark the line for CIV-000667.</span></span>
3. <span data-ttu-id="47e09-153">Nel **riquadro azioni** fare clic su **Fattura**.</span><span class="sxs-lookup"><span data-stu-id="47e09-153">On the **Action Pane**, click **Invoice**.</span></span>
4. <span data-ttu-id="47e09-154">Fare clic su **Annulla**.</span><span class="sxs-lookup"><span data-stu-id="47e09-154">Click **Write off**.</span></span>
5. <span data-ttu-id="47e09-155">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="47e09-155">Click **OK**.</span></span>
6. <span data-ttu-id="47e09-156">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="47e09-156">Close the page.</span></span>

## <a name="write-off-a-customer-balance-from-the-customer-page"></a><span data-ttu-id="47e09-157">Annullare un saldo cliente dalla pagina clienti</span><span class="sxs-lookup"><span data-stu-id="47e09-157">Write off a customer balance from the customer page</span></span>
1. <span data-ttu-id="47e09-158">Andare a **Contabilità clienti > Clienti > Tutti i clienti**.</span><span class="sxs-lookup"><span data-stu-id="47e09-158">Go to **Accounts receivable > Customers > All customers**.</span></span>
2. <span data-ttu-id="47e09-159">Selezionare un account cliente.</span><span class="sxs-lookup"><span data-stu-id="47e09-159">Select a customer account.</span></span> <span data-ttu-id="47e09-160">Ad esempio, selezionare US-001 (Contoso Retail San Diego).</span><span class="sxs-lookup"><span data-stu-id="47e09-160">For example, select US-001 (Contoso Retail San Diego).</span></span>
3. <span data-ttu-id="47e09-161">Nel **riquadro azioni** fare clic su **Raccolta**.</span><span class="sxs-lookup"><span data-stu-id="47e09-161">On the **Action Pane**, click **Collect**.</span></span>
4. <span data-ttu-id="47e09-162">Fare clic su **Annulla**.</span><span class="sxs-lookup"><span data-stu-id="47e09-162">Click **Write off**.</span></span>
5. <span data-ttu-id="47e09-163">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="47e09-163">Click **OK**.</span></span>
6. <span data-ttu-id="47e09-164">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="47e09-164">Close the page.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]