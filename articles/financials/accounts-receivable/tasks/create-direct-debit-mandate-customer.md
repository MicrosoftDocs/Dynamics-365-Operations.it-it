---
title: Creare un nuovo mandato di addebito diretto per un cliente
description: In questa guida attività viene illustrata la creazione di un mandato di addebito diretto e il suo utilizzo in una fattura.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustTable, CustBankAccounts, BankAccountTable, CustPaymMode, CustDirectDebitMandate, BankAccountTableLookUp, SrsReportViewerForm,  LogisticsAddressCityLookup, CustFreeInvoice, CustTableLookup
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5ca5ff2290df2179004ca1cebd11f67fbb7a724e
ms.sourcegitcommit: cbcf344b3b552acca56c3e27606eac7f2f124afe
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "1916371"
---
# <a name="create-a-direct-debit-mandate-for-a-customer"></a><span data-ttu-id="2419e-103">Creare un nuovo mandato di addebito diretto per un cliente</span><span class="sxs-lookup"><span data-stu-id="2419e-103">Create a direct debit mandate for a customer</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="2419e-104">In questa guida attività viene illustrata la creazione di un mandato di addebito diretto e il suo utilizzo in una fattura.</span><span class="sxs-lookup"><span data-stu-id="2419e-104">This task guide demonstrates how to create a direct debit mandate and use it on an invoice.</span></span>


## <a name="create-a-bank-account"></a><span data-ttu-id="2419e-105">Creare un conto bancario</span><span class="sxs-lookup"><span data-stu-id="2419e-105">Create a bank account</span></span>
1. <span data-ttu-id="2419e-106">Nel **pannello di navigazione**, andare a **Moduli > Contabilità clienti > Clienti > Tutti i clienti**.</span><span class="sxs-lookup"><span data-stu-id="2419e-106">In the **Navigation pane**, go to **Modules > Accounts receivable > Customers > All customers**.</span></span>
2. <span data-ttu-id="2419e-107">Nell'elenco selezionare un record.</span><span class="sxs-lookup"><span data-stu-id="2419e-107">In the list, select a record.</span></span> <span data-ttu-id="2419e-108">Selezionare, ad esempio, US-001</span><span class="sxs-lookup"><span data-stu-id="2419e-108">For example, select US-001</span></span>
3. <span data-ttu-id="2419e-109">Nel riquadro azioni fare clic su **Cliente**.</span><span class="sxs-lookup"><span data-stu-id="2419e-109">On the Action Pane, click **Customer**.</span></span>
4. <span data-ttu-id="2419e-110">Fare clic su **Conti bancari**.</span><span class="sxs-lookup"><span data-stu-id="2419e-110">Click **Bank accounts**.</span></span>
5. <span data-ttu-id="2419e-111">Fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="2419e-111">Click **New**.</span></span>
6. <span data-ttu-id="2419e-112">Digitare un valore nel campo **Conto bancario**.</span><span class="sxs-lookup"><span data-stu-id="2419e-112">In the **Bank account** field, type a value.</span></span>
7. <span data-ttu-id="2419e-113">Digitare un valore nel campo **Nome**.</span><span class="sxs-lookup"><span data-stu-id="2419e-113">In the **Name** field, type a value.</span></span>
8. <span data-ttu-id="2419e-114">Digitare un valore nel campo **IBAN**.</span><span class="sxs-lookup"><span data-stu-id="2419e-114">In the **IBAN** field, type a value.</span></span>
9. <span data-ttu-id="2419e-115">Digitare un valore nel campo **Valuta**.</span><span class="sxs-lookup"><span data-stu-id="2419e-115">In the **Currency** field, type a value.</span></span>
10. <span data-ttu-id="2419e-116">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="2419e-116">Click **Save**.</span></span>
11. <span data-ttu-id="2419e-117">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="2419e-117">Close the page.</span></span>
12. <span data-ttu-id="2419e-118">Nel **pannello di navigazione**, andare a **Moduli > Gestione cassa e banche > Conti bancari > Conti bancari**.</span><span class="sxs-lookup"><span data-stu-id="2419e-118">In the **Navigation pane**, go to **Modules > Cash and bank management > Bank accounts > Bank accounts**.</span></span>
13. <span data-ttu-id="2419e-119">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="2419e-119">In the list, find and select the desired record.</span></span>
14. <span data-ttu-id="2419e-120">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="2419e-120">In the list, click the link in the selected row.</span></span>
15. <span data-ttu-id="2419e-121">Fare clic su **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="2419e-121">Click **Edit**.</span></span>
16. <span data-ttu-id="2419e-122">Espandere la Scheda dettaglio **Identificazione aggiuntiva**.</span><span class="sxs-lookup"><span data-stu-id="2419e-122">Expand the **Additional identification** fastTab.</span></span>
17. <span data-ttu-id="2419e-123">Immettere un valore nel campo **ID addebito diretto**.</span><span class="sxs-lookup"><span data-stu-id="2419e-123">In the **Direct debit ID** field, type a value.</span></span>
18. <span data-ttu-id="2419e-124">Digitare un valore nel campo **IBAN**.</span><span class="sxs-lookup"><span data-stu-id="2419e-124">In the **IBAN** field, type a value.</span></span>
19. <span data-ttu-id="2419e-125">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="2419e-125">Close the page.</span></span>
20. <span data-ttu-id="2419e-126">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="2419e-126">Close the page.</span></span>

## <a name="define-the-electronic-payment-method"></a><span data-ttu-id="2419e-127">Definire il metodo di pagamento elettronico</span><span class="sxs-lookup"><span data-stu-id="2419e-127">Define the electronic payment method</span></span>
1. <span data-ttu-id="2419e-128">Nel **pannello di navigazione** andare a **Moduli > Crediti e riscossioni > Impostazione pagamenti > Metodi di pagamento**.</span><span class="sxs-lookup"><span data-stu-id="2419e-128">In the **Navigation pane**, go to **Modules > Accounts receivable > Payments setup > Methods of payment**.</span></span>
2. <span data-ttu-id="2419e-129">Fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="2419e-129">Click **New**.</span></span>
3. <span data-ttu-id="2419e-130">Digitare un valore nel campo **Metodo di pagamento**.</span><span class="sxs-lookup"><span data-stu-id="2419e-130">In the **Method of payment** field, type a value.</span></span>
4. <span data-ttu-id="2419e-131">Digitare un valore nel campo **Descrizione**</span><span class="sxs-lookup"><span data-stu-id="2419e-131">In the **Description** field, type a value.</span></span>
5. <span data-ttu-id="2419e-132">Nel campo **Tipo di pagamento** immettere "Pagamento elettronico".</span><span class="sxs-lookup"><span data-stu-id="2419e-132">In the **Payment type** field, enter 'Electronic payment'.</span></span> <span data-ttu-id="2419e-133">Il tipo di pagamento per il metodo di pagamento mandato di addebito diretto deve essere pagamento elettronico.</span><span class="sxs-lookup"><span data-stu-id="2419e-133">The payment type for a direct debit mandate method of payment must be Electronic payment.</span></span>
6. <span data-ttu-id="2419e-134">Selezionare Sì nel campo **Richiedi mandato**.</span><span class="sxs-lookup"><span data-stu-id="2419e-134">Select Yes in the **Require mandate** field.</span></span>
7. <span data-ttu-id="2419e-135">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="2419e-135">Close the page.</span></span>

## <a name="add-a-direct-debit-mandate-to-a-customer"></a><span data-ttu-id="2419e-136">Aggiungere un mandato di addebito diretto a un cliente.</span><span class="sxs-lookup"><span data-stu-id="2419e-136">Add a direct debit mandate to a customer.</span></span>
1. <span data-ttu-id="2419e-137">Nel **pannello di navigazione**, andare a **Moduli > Contabilità clienti > Clienti > Tutti i clienti**.</span><span class="sxs-lookup"><span data-stu-id="2419e-137">In the **Navigation pane**, go to **Modules > Accounts receivable > Customers > All customers**.</span></span>
2. <span data-ttu-id="2419e-138">Nell'elenco selezionare un record.</span><span class="sxs-lookup"><span data-stu-id="2419e-138">In the list, select a record.</span></span> <span data-ttu-id="2419e-139">Selezionare, ad esempio, US-001</span><span class="sxs-lookup"><span data-stu-id="2419e-139">For example, select US-001</span></span>
3. <span data-ttu-id="2419e-140">Fare clic su **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="2419e-140">Click **Edit**.</span></span>
4. <span data-ttu-id="2419e-141">Espandere la Scheda dettaglio **Impostazioni predefinite pagamento**.</span><span class="sxs-lookup"><span data-stu-id="2419e-141">Expand the **Payment defaults** fastTab.</span></span>
5. <span data-ttu-id="2419e-142">Nel campo **Metodo di pagamento** immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="2419e-142">In the **Method of payment** field, enter or select a value.</span></span>
6. <span data-ttu-id="2419e-143">Espandere la Scheda dettaglio **Impostazioni predefinite pagamento**.</span><span class="sxs-lookup"><span data-stu-id="2419e-143">Expand the **Payment defaults** fastTab.</span></span>
7. <span data-ttu-id="2419e-144">Espandere la Scheda dettaglio **Mandati di addebito diretto**.</span><span class="sxs-lookup"><span data-stu-id="2419e-144">Expand the **Direct debit mandates** fastTab.</span></span>
8. <span data-ttu-id="2419e-145">Scegliere **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="2419e-145">Click **Add**.</span></span>
9. <span data-ttu-id="2419e-146">Nel campo **Conto bancario** immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="2419e-146">In the **Bank account** field, enter or select a value.</span></span>
10. <span data-ttu-id="2419e-147">Nel campo **Conto bancario del creditore** immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="2419e-147">In the **Creditor bank account** field, enter or select a value.</span></span>
11. <span data-ttu-id="2419e-148">Nel campo **Frequenza pagamenti**, immettere il numero di pagamenti che si prevede di elaborare per il mandato.</span><span class="sxs-lookup"><span data-stu-id="2419e-148">In the **Payment frequency** field, enter the number of payments that you expect to process for this mandate.</span></span>
12. <span data-ttu-id="2419e-149">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="2419e-149">Click **OK**.</span></span>
13. <span data-ttu-id="2419e-150">Fare clic su **Stampa**.</span><span class="sxs-lookup"><span data-stu-id="2419e-150">Click **Print**.</span></span>
14. <span data-ttu-id="2419e-151">Fare clic su **Report mandati**.</span><span class="sxs-lookup"><span data-stu-id="2419e-151">Click **Mandate report**.</span></span>
15. <span data-ttu-id="2419e-152">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="2419e-152">Close the page.</span></span>
16. <span data-ttu-id="2419e-153">Fare clic su **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="2419e-153">Click **Edit**.</span></span>
17. <span data-ttu-id="2419e-154">Immettere una data nel campo **Data di firma**.</span><span class="sxs-lookup"><span data-stu-id="2419e-154">In the **Signature date** field, enter a date.</span></span>
18. <span data-ttu-id="2419e-155">Fare clic su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="2419e-155">Click **Yes**.</span></span>
19. <span data-ttu-id="2419e-156">Immettere il luogo in cui è stato firmato il mandato.</span><span class="sxs-lookup"><span data-stu-id="2419e-156">Enter the location where the mandate was signed.</span></span>
20. <span data-ttu-id="2419e-157">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="2419e-157">Click **OK**.</span></span>
21. <span data-ttu-id="2419e-158">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="2419e-158">Close the page.</span></span>

## <a name="create-a-free-text-invoice-with-mandate"></a><span data-ttu-id="2419e-159">Creare una fattura a testo libero con mandato</span><span class="sxs-lookup"><span data-stu-id="2419e-159">Create a free text invoice with mandate</span></span>
1. <span data-ttu-id="2419e-160">Nel **pannello di navigazione** andare a **Moduli > Contabilità clienti > Fatture > Tutte le fatture a testo libero**.</span><span class="sxs-lookup"><span data-stu-id="2419e-160">In the **Navigation pane**, go to **Modules > Accounts receivable > Invoices > All free text invoices**.</span></span>
2. <span data-ttu-id="2419e-161">Fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="2419e-161">Click **New**.</span></span>
3. <span data-ttu-id="2419e-162">Selezionare il cliente aggiunto al mandato.</span><span class="sxs-lookup"><span data-stu-id="2419e-162">Select the customer that you added the mandate to.</span></span>
4. <span data-ttu-id="2419e-163">Nel campo **ID mandato di addebito diretto**, immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="2419e-163">In the **Direct debit mandate ID** field, enter or select a value.</span></span>

