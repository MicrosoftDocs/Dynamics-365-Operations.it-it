---
title: Creare pagamenti per un cliente con mandati di addebito diretto
description: In questa procedura viene illustrato come generare un file di pagamento in addebito diretto ISO20022 per un cliente che ha configurato l'addebito diretto e una fattura da pagare.
author: mrolecki
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustFreeInvoice, CustTableLookup, CustPostInvoiceJob, LedgerJournalTable, LedgerJournalTransCustPaym, SysQueryForm, CustPaymProposalEdit, BankAccountTableLookUp
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e1959904befc62c32a8da185729f13525db27d4b
ms.sourcegitcommit: 16bfa0fd08feec1647829630401ce62ce2ffa1a4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/02/2019
ms.locfileid: "1848924"
---
# <a name="create-payments-for-a-customer-who-have-direct-debit-mandates"></a><span data-ttu-id="fc425-103">Creare pagamenti per un cliente con mandati di addebito diretto</span><span class="sxs-lookup"><span data-stu-id="fc425-103">Create payments for a customer who have direct debit mandates</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="fc425-104">In questa procedura viene illustrato come generare un file di pagamento in addebito diretto ISO20022 per un cliente che ha configurato l'addebito diretto e una fattura da pagare.</span><span class="sxs-lookup"><span data-stu-id="fc425-104">This procedure shows how to generate an ISO20022 direct debit payment file for a customer who has direct debit configured and an invoice to be paid.</span></span> <span data-ttu-id="fc425-105">La creazione e registrazione di una fattura sono facoltativi.</span><span class="sxs-lookup"><span data-stu-id="fc425-105">Creating and posting an invoice is optional.</span></span> <span data-ttu-id="fc425-106">Anziché avere una fattura da pagare è possibile selezionare un mandato in un giornale di registrazione prima di generare un file di pagamento, per supportare uno scenario di pagamento anticipato del cliente.</span><span class="sxs-lookup"><span data-stu-id="fc425-106">Instead of having an invoice to be paid you can select a mandate in a journal prior to generating a payment file, to support a customer prepayment scenario.</span></span>



<span data-ttu-id="fc425-107">La società di dati dimostrativi utilizzata per creare questa procedura è DEMF.</span><span class="sxs-lookup"><span data-stu-id="fc425-107">The demo data company used to create this procedure is DEMF.</span></span>



<span data-ttu-id="fc425-108">Si tratta della quinta di cinque procedure che illustrano il processo di pagamento cliente utilizzando le configurazioni di creazione di report elettronici.</span><span class="sxs-lookup"><span data-stu-id="fc425-108">This is the fifth of five procedures that demonstrate the customer payment process using electronic reporting configurations.</span></span> <span data-ttu-id="fc425-109">Per completare questa attività, è necessario completare le attività precedenti.</span><span class="sxs-lookup"><span data-stu-id="fc425-109">Before you can complete this task, you must complete the earlier tasks.</span></span> <span data-ttu-id="fc425-110">È innanzitutto necessario importare le configurazioni per la creazione di report elettronici di pagamento cliente, configurare il metodo di pagamento e impostare le informazioni sulla società e sul cliente.</span><span class="sxs-lookup"><span data-stu-id="fc425-110">You must first import customer payment electronic reporting configurations, configure method of payments, and set up your company and customer information.</span></span> 


## <a name="post-a-free-text-invoice-with-direct-debit-information"></a><span data-ttu-id="fc425-111">Registrare una fattura a testo libero con le informazioni sull'addebito diretto</span><span class="sxs-lookup"><span data-stu-id="fc425-111">Post a free text invoice with direct debit information</span></span>
1. <span data-ttu-id="fc425-112">Andare a Contabilità clienti > Fatture > Tutte le fatture a testo libero.</span><span class="sxs-lookup"><span data-stu-id="fc425-112">Go to Accounts receivable > Invoices > All free text invoices.</span></span>
2. <span data-ttu-id="fc425-113">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="fc425-113">Click New.</span></span>
3. <span data-ttu-id="fc425-114">Nel campo Conto cliente, immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="fc425-114">In the Customer account field, enter or select a value.</span></span>
    * <span data-ttu-id="fc425-115">Selezionare, ad esempio, DE-010.</span><span class="sxs-lookup"><span data-stu-id="fc425-115">For example, select DE-010.</span></span>  
4. <span data-ttu-id="fc425-116">Nel campo Metodo di pagamento immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="fc425-116">In the Method of payment field, enter or select a value.</span></span>
    * <span data-ttu-id="fc425-117">Ad esempio,</span><span class="sxs-lookup"><span data-stu-id="fc425-117">For example.</span></span> <span data-ttu-id="fc425-118">selezionare Elettronico.</span><span class="sxs-lookup"><span data-stu-id="fc425-118">select Electronic.</span></span>  
5. <span data-ttu-id="fc425-119">Nel campo ID mandato di addebito diretto, immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="fc425-119">In the Direct debit mandate ID field, enter or select a value.</span></span>
6. <span data-ttu-id="fc425-120">Fare clic su Aggiungi riga.</span><span class="sxs-lookup"><span data-stu-id="fc425-120">Click Add line.</span></span>
7. <span data-ttu-id="fc425-121">Digitare un valore nel campo Descrizione.</span><span class="sxs-lookup"><span data-stu-id="fc425-121">In the Description field, type a value.</span></span>
8. <span data-ttu-id="fc425-122">Nel campo Conto principale, specificare i valori desiderati.</span><span class="sxs-lookup"><span data-stu-id="fc425-122">In the Main account field, specify the desired values.</span></span>
9. <span data-ttu-id="fc425-123">Nel campo Prezzo unitario immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="fc425-123">In the Unit price field, enter a number.</span></span>
10. <span data-ttu-id="fc425-124">Fare clic su Registra.</span><span class="sxs-lookup"><span data-stu-id="fc425-124">Click Post.</span></span>
11. <span data-ttu-id="fc425-125">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="fc425-125">Click OK.</span></span>

## <a name="create-a-payment"></a><span data-ttu-id="fc425-126">Creare un pagamento</span><span class="sxs-lookup"><span data-stu-id="fc425-126">Create a payment</span></span>
1. <span data-ttu-id="fc425-127">Andare a Contabilità clienti > Pagamenti > Giornale di registrazione pagamenti.</span><span class="sxs-lookup"><span data-stu-id="fc425-127">Go to Accounts receivable > Payments > Payment journal.</span></span>
2. <span data-ttu-id="fc425-128">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="fc425-128">Click New.</span></span>
3. <span data-ttu-id="fc425-129">Nel campo Nome immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="fc425-129">In the Name field, enter or select a value.</span></span>
4. <span data-ttu-id="fc425-130">Fare clic su Righe.</span><span class="sxs-lookup"><span data-stu-id="fc425-130">Click Lines.</span></span>
5. <span data-ttu-id="fc425-131">Fare clic su Proposta di pagamento.</span><span class="sxs-lookup"><span data-stu-id="fc425-131">Click Payment proposal.</span></span>
6. <span data-ttu-id="fc425-132">Fare clic su Crea proposta di pagamento.</span><span class="sxs-lookup"><span data-stu-id="fc425-132">Click Create payment proposal.</span></span>
7. <span data-ttu-id="fc425-133">Espandere la sezione Record da includere.</span><span class="sxs-lookup"><span data-stu-id="fc425-133">Expand the Records to include section.</span></span>
8. <span data-ttu-id="fc425-134">Fare clic su Filtro.</span><span class="sxs-lookup"><span data-stu-id="fc425-134">Click Filter.</span></span>
9. <span data-ttu-id="fc425-135">Nell'elenco, selezionare la riga relativa alla tabella delle transazioni cliente e il campo Metodo di pagamento.</span><span class="sxs-lookup"><span data-stu-id="fc425-135">In the list, select the row for the Customer transactions table and the Method of payment field.</span></span>
    * <span data-ttu-id="fc425-136">È possibile applicare qualsiasi criterio per la selezione delle transazioni cliente per il pagamento.</span><span class="sxs-lookup"><span data-stu-id="fc425-136">You can apply any criteria for selecting customer transactions to pay.</span></span> <span data-ttu-id="fc425-137">Per questo esempio, utilizzare Elettronico come metodo di pagamento per filtrare le transazioni.</span><span class="sxs-lookup"><span data-stu-id="fc425-137">For this example, use Electronic as a method of payment to filter transactions.</span></span>  
10. <span data-ttu-id="fc425-138">Nel campo Criteri immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="fc425-138">In the Criteria field, enter or select a value.</span></span>
11. <span data-ttu-id="fc425-139">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="fc425-139">Click OK.</span></span>
12. <span data-ttu-id="fc425-140">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="fc425-140">Click OK.</span></span>
13. <span data-ttu-id="fc425-141">Fare clic su Crea pagamenti.</span><span class="sxs-lookup"><span data-stu-id="fc425-141">Click Create payments.</span></span>

## <a name="generate-a-payment-file"></a><span data-ttu-id="fc425-142">Generare un file di pagamento</span><span class="sxs-lookup"><span data-stu-id="fc425-142">Generate a payment file</span></span>

