--- 
title: Creare un nuovo mandato di addebito diretto per un cliente
description: "In questa guida attività viene illustrata la creazione di un mandato di addebito diretto e il suo utilizzo in una fattura."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 10/23/2016
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
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: d01c7c19925a3c7064ab3f845b92b610b162066c
ms.contentlocale: it-it
ms.lasthandoff: 08/29/2017

---
# <a name="create-a-direct-debit-mandate-for-a-customer"></a><span data-ttu-id="4fcc0-103">Creare un nuovo mandato di addebito diretto per un cliente</span><span class="sxs-lookup"><span data-stu-id="4fcc0-103">Create a direct debit mandate for a customer</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="4fcc0-104">In questa guida attività viene illustrata la creazione di un mandato di addebito diretto e il suo utilizzo in una fattura.</span><span class="sxs-lookup"><span data-stu-id="4fcc0-104">This task guide demonstrates how to create a direct debit mandate and use it on an invoice.</span></span>


## <a name="create-a-bank-account"></a><span data-ttu-id="4fcc0-105">Creare un conto bancario</span><span class="sxs-lookup"><span data-stu-id="4fcc0-105">Create a bank account</span></span>
1. <span data-ttu-id="4fcc0-106">Andare a Contabilità clienti > Clienti > Tutti i clienti.</span><span class="sxs-lookup"><span data-stu-id="4fcc0-106">Go to Accounts receivable > Customers > All customers.</span></span>
2. <span data-ttu-id="4fcc0-107">Selezionare, ad esempio, US-001</span><span class="sxs-lookup"><span data-stu-id="4fcc0-107">For example, select US-001</span></span>
3. <span data-ttu-id="4fcc0-108">Nel riquadro azioni fare clic su Cliente.</span><span class="sxs-lookup"><span data-stu-id="4fcc0-108">On the Action Pane, click Customer.</span></span>
4. <span data-ttu-id="4fcc0-109">Fare clic su Conti bancari.</span><span class="sxs-lookup"><span data-stu-id="4fcc0-109">Click Bank accounts.</span></span>
5. <span data-ttu-id="4fcc0-110">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="4fcc0-110">Click New.</span></span>
6. <span data-ttu-id="4fcc0-111">Digitare un valore nel campo Conto bancario.</span><span class="sxs-lookup"><span data-stu-id="4fcc0-111">In the Bank account field, type a value.</span></span>
7. <span data-ttu-id="4fcc0-112">Digitare un valore nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="4fcc0-112">In the Name field, type a value.</span></span>
8. <span data-ttu-id="4fcc0-113">Digitare un valore nel campo IBAN.</span><span class="sxs-lookup"><span data-stu-id="4fcc0-113">In the IBAN field, type a value.</span></span>
9. <span data-ttu-id="4fcc0-114">Digitare un valore nel campo Valuta.</span><span class="sxs-lookup"><span data-stu-id="4fcc0-114">In the Currency field, type a value.</span></span>
10. <span data-ttu-id="4fcc0-115">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="4fcc0-115">Click Save.</span></span>
11. <span data-ttu-id="4fcc0-116">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="4fcc0-116">Close the page.</span></span>
12. <span data-ttu-id="4fcc0-117">Andare a Gestione cassa e banche > Conti bancari > Conti bancari.</span><span class="sxs-lookup"><span data-stu-id="4fcc0-117">Go to Cash and bank management > Bank accounts > Bank accounts.</span></span>
13. <span data-ttu-id="4fcc0-118">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="4fcc0-118">In the list, find and select the desired record.</span></span>
14. <span data-ttu-id="4fcc0-119">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="4fcc0-119">In the list, click the link in the selected row.</span></span>
15. <span data-ttu-id="4fcc0-120">Fare clic su Modifica.</span><span class="sxs-lookup"><span data-stu-id="4fcc0-120">Click Edit.</span></span>
16. <span data-ttu-id="4fcc0-121">Espandere la sezione Identificazione aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="4fcc0-121">Expand the Additional identification section.</span></span>
17. <span data-ttu-id="4fcc0-122">Immettere un valore nel campo ID addebito diretto.</span><span class="sxs-lookup"><span data-stu-id="4fcc0-122">In the Direct debit ID field, type a value.</span></span>
18. <span data-ttu-id="4fcc0-123">Digitare un valore nel campo IBAN.</span><span class="sxs-lookup"><span data-stu-id="4fcc0-123">In the IBAN field, type a value.</span></span>
19. <span data-ttu-id="4fcc0-124">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="4fcc0-124">Close the page.</span></span>
20. <span data-ttu-id="4fcc0-125">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="4fcc0-125">Close the page.</span></span>

## <a name="define-the-electronic-payment-method"></a><span data-ttu-id="4fcc0-126">Definire il metodo di pagamento elettronico</span><span class="sxs-lookup"><span data-stu-id="4fcc0-126">Define the electronic payment method</span></span>
1. <span data-ttu-id="4fcc0-127">Andare a Contabilità clienti > Impostazione pagamenti > Metodi di pagamento.</span><span class="sxs-lookup"><span data-stu-id="4fcc0-127">Go to Accounts receivable > Payments setup > Methods of payment.</span></span>
2. <span data-ttu-id="4fcc0-128">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="4fcc0-128">Click New.</span></span>
3. <span data-ttu-id="4fcc0-129">Digitare un valore nel campo Metodo di pagamento.</span><span class="sxs-lookup"><span data-stu-id="4fcc0-129">In the Method of payment field, type a value.</span></span>
4. <span data-ttu-id="4fcc0-130">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="4fcc0-130">In the Description field, type a value.</span></span>
5. <span data-ttu-id="4fcc0-131">Il tipo di pagamento per il metodo di pagamento mandato di addebito diretto deve essere pagamento elettronico.</span><span class="sxs-lookup"><span data-stu-id="4fcc0-131">The payment type for a direct debit mandate method of payment must be Electronic payment.</span></span>
6. <span data-ttu-id="4fcc0-132">Selezionare Sì nel campo Richiedi mandato.</span><span class="sxs-lookup"><span data-stu-id="4fcc0-132">Select Yes in the Require mandate field.</span></span>
7. <span data-ttu-id="4fcc0-133">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="4fcc0-133">Close the page.</span></span>

## <a name="add-a-direct-debit-mandate-to-a-customer"></a><span data-ttu-id="4fcc0-134">Aggiungere un mandato di addebito diretto a un cliente.</span><span class="sxs-lookup"><span data-stu-id="4fcc0-134">Add a direct debit mandate to a customer.</span></span>
1. <span data-ttu-id="4fcc0-135">Andare a Contabilità clienti > Clienti > Tutti i clienti.</span><span class="sxs-lookup"><span data-stu-id="4fcc0-135">Go to Accounts receivable > Customers > All customers.</span></span>
2. <span data-ttu-id="4fcc0-136">Selezionare, ad esempio, US-001</span><span class="sxs-lookup"><span data-stu-id="4fcc0-136">For example, select US-001</span></span>
3. <span data-ttu-id="4fcc0-137">Fare clic su Modifica.</span><span class="sxs-lookup"><span data-stu-id="4fcc0-137">Click Edit.</span></span>
4. <span data-ttu-id="4fcc0-138">Espandere la sezione Impostazioni predefinite pagamento.</span><span class="sxs-lookup"><span data-stu-id="4fcc0-138">Expand the Payment defaults section.</span></span>
5. <span data-ttu-id="4fcc0-139">Nel campo Metodo di pagamento immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="4fcc0-139">In the Method of payment field, enter or select a value.</span></span>
6. <span data-ttu-id="4fcc0-140">Espandere la sezione Impostazioni predefinite pagamento.</span><span class="sxs-lookup"><span data-stu-id="4fcc0-140">Expand the Payment defaults section.</span></span>
7. <span data-ttu-id="4fcc0-141">Espandere la sezione Mandati di addebito diretto.</span><span class="sxs-lookup"><span data-stu-id="4fcc0-141">Expand the Direct debit mandates section.</span></span>
8. <span data-ttu-id="4fcc0-142">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="4fcc0-142">Click Add.</span></span>
9. <span data-ttu-id="4fcc0-143">Nel campo Conto bancario immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="4fcc0-143">In the Bank account field, enter or select a value.</span></span>
10. <span data-ttu-id="4fcc0-144">Nel campo Conto bancario del creditore immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="4fcc0-144">In the Creditor bank account field, enter or select a value.</span></span>
11. <span data-ttu-id="4fcc0-145">Immettere il numero di pagamenti che si prevede di elaborare per il mandato.</span><span class="sxs-lookup"><span data-stu-id="4fcc0-145">Enter the number of payments that you expect to process for this mandate.</span></span>
12. <span data-ttu-id="4fcc0-146">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="4fcc0-146">Click OK.</span></span>
13. <span data-ttu-id="4fcc0-147">Fare clic su Stampa.</span><span class="sxs-lookup"><span data-stu-id="4fcc0-147">Click Print.</span></span>
14. <span data-ttu-id="4fcc0-148">Fare clic su Report mandati.</span><span class="sxs-lookup"><span data-stu-id="4fcc0-148">Click Mandate report.</span></span>
15. <span data-ttu-id="4fcc0-149">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="4fcc0-149">Close the page.</span></span>
16. <span data-ttu-id="4fcc0-150">Fare clic su Modifica.</span><span class="sxs-lookup"><span data-stu-id="4fcc0-150">Click Edit.</span></span>
17. <span data-ttu-id="4fcc0-151">Immettere una data nel campo Data di firma.</span><span class="sxs-lookup"><span data-stu-id="4fcc0-151">In the Signature date field, enter a date.</span></span>
18. <span data-ttu-id="4fcc0-152">Fare clic su Sì.</span><span class="sxs-lookup"><span data-stu-id="4fcc0-152">Click Yes.</span></span>
19. <span data-ttu-id="4fcc0-153">Immettere il luogo in cui è stato firmato il mandato.</span><span class="sxs-lookup"><span data-stu-id="4fcc0-153">Enter the location where the mandate was signed.</span></span>
20. <span data-ttu-id="4fcc0-154">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="4fcc0-154">Click OK.</span></span>
21. <span data-ttu-id="4fcc0-155">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="4fcc0-155">Close the page.</span></span>

## <a name="create-a-free-text-invoice-with-mandate"></a><span data-ttu-id="4fcc0-156">Creare una fattura a testo libero con mandato</span><span class="sxs-lookup"><span data-stu-id="4fcc0-156">Create a free text invoice with mandate</span></span>
1. <span data-ttu-id="4fcc0-157">Andare a Contabilità clienti > Fatture > Tutte le fatture a testo libero.</span><span class="sxs-lookup"><span data-stu-id="4fcc0-157">Go to Accounts receivable > Invoices > All free text invoices.</span></span>
2. <span data-ttu-id="4fcc0-158">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="4fcc0-158">Click New.</span></span>
3. <span data-ttu-id="4fcc0-159">Selezionare il cliente aggiunto al mandato.</span><span class="sxs-lookup"><span data-stu-id="4fcc0-159">Select the customer that you added the mandate to.</span></span>
4. <span data-ttu-id="4fcc0-160">Nel campo ID mandato di addebito diretto, immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="4fcc0-160">In the Direct debit mandate ID field, enter or select a value.</span></span>

