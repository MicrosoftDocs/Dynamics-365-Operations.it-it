---
title: Pagamenti anticipati dei clienti
description: Questo argomento spiega come impostare ed elaborare i pagamenti anticipati dei clienti (noti anche come depositi cliente).
author: roschlom
ms.date: 04/30/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustPosting, LedgerJournalTransCustPaym, CustParameters
audience: Application User
ms.reviewer: ''
ms.search.scope: Core, Operations
ms.custom: 24651
ms.assetid: cb82245e-8c02-429c-b36e-8db0e3e6f7e5
ms.search.region: Global
ms.author: raprofit
ms.search.validFrom: ''
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c3314803b994aed40e5b04d8546a45bd305d48b6
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2021
ms.locfileid: "6019422"
---
# <a name="customer-prepayments"></a><span data-ttu-id="8a139-103">Pagamenti anticipati dei clienti</span><span class="sxs-lookup"><span data-stu-id="8a139-103">Customer prepayments</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="8a139-104">I pagamenti anticipati dei clienti vengono utilizzati quando si riceve un pagamento da un cliente, ma non esiste alcuna fattura in base alla quale il pagamento può essere liquidato.</span><span class="sxs-lookup"><span data-stu-id="8a139-104">Customer prepayments are used when you receive a payment from a customer, but there is no invoice that the payment can be settled against.</span></span> <span data-ttu-id="8a139-105">Questi tipi di pagamenti sono anche denominati depositi cliente.</span><span class="sxs-lookup"><span data-stu-id="8a139-105">These types of payments are also referred to as customer deposits.</span></span>

<span data-ttu-id="8a139-106">Il processo di impostazione e utilizzo dei pagamenti anticipati dei clienti consiste nei seguenti passaggi di base.</span><span class="sxs-lookup"><span data-stu-id="8a139-106">The process of setting up and working with customer prepayments consists of the following basic steps.</span></span>

1. <span data-ttu-id="8a139-107">Crea un profilo di registrazione cliente per i pagamenti anticipati.</span><span class="sxs-lookup"><span data-stu-id="8a139-107">Create a customer posting profile for prepayments.</span></span>
2. <span data-ttu-id="8a139-108">Imposta il parametro **Profilo registrazione con giustificativo giornale di registrazione per pagamento anticipato**.</span><span class="sxs-lookup"><span data-stu-id="8a139-108">Set the **Posting profile with prepayment journal voucher** parameter.</span></span>
3. <span data-ttu-id="8a139-109">Crea un giornale di registrazione pagamenti del cliente e seleziona la casella di controllo **Giustificativo giornale di registrazione per pagamento anticipato** in ogni riga.</span><span class="sxs-lookup"><span data-stu-id="8a139-109">Create a customer payment journal, and select the **Prepayment journal voucher** check box on each line.</span></span>
4. <span data-ttu-id="8a139-110">Registra il giornale di registrazione pagamenti cliente.</span><span class="sxs-lookup"><span data-stu-id="8a139-110">Post the customer payment journal.</span></span>
5. <span data-ttu-id="8a139-111">Dopo aver generato una fattura, liquida il pagamento anticipato con la stessa utilizzando la pagina **Liquida transazioni aperte**.</span><span class="sxs-lookup"><span data-stu-id="8a139-111">After an invoice is generated, settle the prepayment with it by using the **Settle open transactions** page.</span></span>

## <a name="create-a-customer-posting-profile-for-prepayments"></a><span data-ttu-id="8a139-112">Creare un profilo di registrazione cliente per i pagamenti anticipati</span><span class="sxs-lookup"><span data-stu-id="8a139-112">Create a customer posting profile for prepayments</span></span>

<span data-ttu-id="8a139-113">In genere, quando accetti pagamenti anticipati o depositi dai clienti prima della consegna di beni o servizi o prima dell'esistenza di una fattura nel tuo sistema, ti consigliamo di registrare il contante come passività anziché come cespite nel piano dei conti.</span><span class="sxs-lookup"><span data-stu-id="8a139-113">Typically, when you accept prepayments or deposits from your customers before goods or services are delivered, or before an invoice exists in your system, you will want to record the cash as a liability instead of an asset in your chart of accounts.</span></span> <span data-ttu-id="8a139-114">Tuttavia, i requisiti per la registrazione di questi importi nella contabilità generale potrebbero differire, a seconda del paese.</span><span class="sxs-lookup"><span data-stu-id="8a139-114">However, the requirements for recording these amounts in your general ledger might differ, depending on your country or region.</span></span> <span data-ttu-id="8a139-115">Pertanto, assicurati di consultare i contabili in merito a eventuali normative locali applicabili.</span><span class="sxs-lookup"><span data-stu-id="8a139-115">Therefore, be sure to consult your accountants about any local regulations that apply.</span></span>

<span data-ttu-id="8a139-116">In generale, il processo per la creazione di un profilo di registrazione che può essere utilizzato per i pagamenti anticipati è lo stesso del processo per la creazione di altri profili di registrazione.</span><span class="sxs-lookup"><span data-stu-id="8a139-116">In general, the process for creating a posting profile that can be used for prepayments is the same as the process for creating other posting profiles.</span></span> <span data-ttu-id="8a139-117">La differenza principale è il conto principale selezionato nel campo **Conto riepilogativo**.</span><span class="sxs-lookup"><span data-stu-id="8a139-117">The primary difference is the main account that you select in the **Summary account** field.</span></span> <span data-ttu-id="8a139-118">Per ulteriori informazioni, vedi [Profili di registrazione cliente](customer-posting-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="8a139-118">For more information, see [Customer posting profiles](customer-posting-profiles.md).</span></span>

## <a name="define-parameters-for-customer-prepayments"></a><span data-ttu-id="8a139-119">Definire parametri per i pagamenti anticipati dei clienti</span><span class="sxs-lookup"><span data-stu-id="8a139-119">Define parameters for customer prepayments</span></span>

<span data-ttu-id="8a139-120">Esistono due parametri di contabilità clienti principali che devi considerare quando configuri il sistema per i pagamenti anticipati dei clienti.</span><span class="sxs-lookup"><span data-stu-id="8a139-120">There are two main Accounts receivable parameters that you must consider when you configure the system for customer prepayments.</span></span> <span data-ttu-id="8a139-121">Per configurare i parametri, procedi come descritto di seguito.</span><span class="sxs-lookup"><span data-stu-id="8a139-121">Follow these steps to configure the parameters.</span></span>

1. <span data-ttu-id="8a139-122">Andare a **Contabilità clienti \> Impostazioni \> Parametri contabilità clienti**.</span><span class="sxs-lookup"><span data-stu-id="8a139-122">Go to **Accounts receivable \> Setup \> Accounts receivable parameters**.</span></span>
2. <span data-ttu-id="8a139-123">Facoltativo: nella scheda **Contabilità generale e IVA**, nella Scheda dettaglio **Pagamento**, imposta l'opzione **IVA su giustificativo giornale di registrazione per pagamento anticipato** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="8a139-123">Optional: On the **Ledger and sales tax** tab, on the **Payment** FastTab, set the **Sales tax on prepayment journal voucher** option to **Yes**.</span></span>
3. <span data-ttu-id="8a139-124">Nel campo **Profilo registrazione con giustificativo giornale di registrazione per pagamento anticipato** seleziona il profilo di registrazione cliente da utilizzare quando vengono registrati i pagamenti anticipati dei clienti.</span><span class="sxs-lookup"><span data-stu-id="8a139-124">In the **Posting profile with prepayment journal voucher** field, select the customer posting profile to use when customer prepayments are posted.</span></span>
4. <span data-ttu-id="8a139-125">Chiudi la pagina.</span><span class="sxs-lookup"><span data-stu-id="8a139-125">Close the page.</span></span>

## <a name="create-customer-prepayment-vouchers"></a><span data-ttu-id="8a139-126">Creare giustificativi di pagamenti anticipati dei clienti</span><span class="sxs-lookup"><span data-stu-id="8a139-126">Create customer prepayment vouchers</span></span>

<span data-ttu-id="8a139-127">Quando crei il giornale di registrazione pagamenti dei clienti, per ogni pagamento anticipato devi impostare l'opzione **Giustificativo giornale di registrazione per pagamento anticipato** su **Sì** nella pagina **Giornale di registrazione pagamenti cliente**.</span><span class="sxs-lookup"><span data-stu-id="8a139-127">When you create the customer payment journal, for every prepayment, you must set the **Prepayment journal voucher** option to **Yes** on the **Customer payment journal** page.</span></span> <span data-ttu-id="8a139-128">Per creare un pagamento anticipato dei clienti, completa i passaggi seguenti.</span><span class="sxs-lookup"><span data-stu-id="8a139-128">Follow these steps to create a customer prepayment.</span></span>

1. <span data-ttu-id="8a139-129">Vai a **Contabilità clienti \> Pagamenti \> Giornale di registrazione pagamenti cliente**.</span><span class="sxs-lookup"><span data-stu-id="8a139-129">Go to **Accounts receivable \> Payments \> Customer payment journal**.</span></span>
2. <span data-ttu-id="8a139-130">Seleziona **Nuovo** per creare un giornale di registrazione.</span><span class="sxs-lookup"><span data-stu-id="8a139-130">Select **New** to create a journal.</span></span>
3. <span data-ttu-id="8a139-131">Seleziona il nome del giornale di registrazione nel campo **Nome**.</span><span class="sxs-lookup"><span data-stu-id="8a139-131">In the **Name** field, select the journal name to use.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="8a139-132">Se imposti l'opzione **IVA su giustificativo giornale di registrazione per pagamento anticipato** su **Sì** nella procedura precedente, devi selezionare un nome di giornale di registrazione in cui il parametro **L'importo include l'IVA** è selezionato.</span><span class="sxs-lookup"><span data-stu-id="8a139-132">If you set the **Sales tax on prepayment journal voucher** option to **Yes** in the previous procedure, you must select a journal name where the **Amount includes sales tax** parameter is selected.</span></span> 

4. <span data-ttu-id="8a139-133">Facoltativo: nel campo **Descrizione**, immetti una descrizione dettagliata.</span><span class="sxs-lookup"><span data-stu-id="8a139-133">Optional: In the **Description** field, enter a detailed description.</span></span>
5. <span data-ttu-id="8a139-134">Selezionare **Righe**.</span><span class="sxs-lookup"><span data-stu-id="8a139-134">Select **Lines**.</span></span>
6. <span data-ttu-id="8a139-135">Se non esiste una riga vuota, seleziona **Nuovo** per creare una riga.</span><span class="sxs-lookup"><span data-stu-id="8a139-135">If a blank line doesn't exist, select **New** to create a line.</span></span>
7. <span data-ttu-id="8a139-136">Nel campo **Data** immetti la data in cui il pagamento anticipato deve essere registrato.</span><span class="sxs-lookup"><span data-stu-id="8a139-136">In the **Date** field, enter the date when the prepayment should be posted.</span></span>
8. <span data-ttu-id="8a139-137">Nel campo **Conto** seleziona il cliente per il pagamento anticipato.</span><span class="sxs-lookup"><span data-stu-id="8a139-137">In the **Account** field, select the customer for the prepayment.</span></span>
9. <span data-ttu-id="8a139-138">Facoltativo: nel campo **Descrizione**, immetti una descrizione dettagliata della transazione.</span><span class="sxs-lookup"><span data-stu-id="8a139-138">Optional: In the **Description** field, enter a detailed description of the transaction.</span></span>
10. <span data-ttu-id="8a139-139">Nel campo **Avere**, immetti l'importo del pagamento anticipato.</span><span class="sxs-lookup"><span data-stu-id="8a139-139">In the **Credit** field, enter the amount of the prepayment.</span></span>
11. <span data-ttu-id="8a139-140">Nel campo **Conto di contropartita** seleziona il conto a cui applicare la contropartita per il pagamento.</span><span class="sxs-lookup"><span data-stu-id="8a139-140">In the **Offset account** field, select the account to offset the payment to.</span></span> <span data-ttu-id="8a139-141">Ad esempio, seleziona la banca o il conto principale in cui registrare il pagamento.</span><span class="sxs-lookup"><span data-stu-id="8a139-141">For example, select the bank or main account to post the payment to.</span></span>
12. <span data-ttu-id="8a139-142">Nel campo **Metodo di pagamento** seleziona il metodo di pagamento del cliente.</span><span class="sxs-lookup"><span data-stu-id="8a139-142">In the **Method of payment** field, select the customer's method of payment.</span></span>
13. <span data-ttu-id="8a139-143">Nella scheda **Pagamento**, imposta l'opzione **Giustificativo giornale di registrazione per pagamento anticipato** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="8a139-143">On the **Payment** tab, set the **Prepayment journal voucher** option to **Yes**.</span></span>
14. <span data-ttu-id="8a139-144">Ripeti i passaggi da 7 a 13 per ogni pagamento anticipato aggiuntivo che deve essere registrato.</span><span class="sxs-lookup"><span data-stu-id="8a139-144">Repeat steps 7 through 13 for each additional prepayment that must be posted.</span></span>
15. <span data-ttu-id="8a139-145">Seleziona **Registra** per finalizzare il giornale di registrazione.</span><span class="sxs-lookup"><span data-stu-id="8a139-145">Select **Post** to finalize the journal.</span></span>

## <a name="settle-prepayments-with-invoices"></a><span data-ttu-id="8a139-146">Liquidare pagamenti anticipati con fatture</span><span class="sxs-lookup"><span data-stu-id="8a139-146">Settle prepayments with invoices</span></span>

<span data-ttu-id="8a139-147">Puoi usare l'area di lavoro **Pagamenti clienti** per trovare e liquidare facilmente i pagamenti che non sono stati completamente liquidati.</span><span class="sxs-lookup"><span data-stu-id="8a139-147">You can use the **Customer payments** workspace to easily find and settle payments that haven't been fully settled.</span></span>

1. <span data-ttu-id="8a139-148">Nel dashboard **Home**, seleziona il riquadro **Pagamenti clienti**.</span><span class="sxs-lookup"><span data-stu-id="8a139-148">On the **Home** dashboard, select the **Customer payments** tile.</span></span>
2. <span data-ttu-id="8a139-149">Nella sezione **Transazioni cliente**, nella scheda **Pagamenti non liquidati**, cerca e seleziona il pagamento da liquidare.</span><span class="sxs-lookup"><span data-stu-id="8a139-149">In the **Customer transactions** section, on the **Payments not settled** tab, search for and select the payment to settle.</span></span>
3. <span data-ttu-id="8a139-150">Seleziona **Liquida transazioni**.</span><span class="sxs-lookup"><span data-stu-id="8a139-150">Select **Settle transactions**.</span></span>
4. <span data-ttu-id="8a139-151">Seleziona la casella di controllo **Contrassegna** per la fattura e il pagamento che verrà liquidato.</span><span class="sxs-lookup"><span data-stu-id="8a139-151">Select the **Mark** check box for the invoice and the payment that will be settled.</span></span>
5. <span data-ttu-id="8a139-152">Selezionare **Registra**.</span><span class="sxs-lookup"><span data-stu-id="8a139-152">Select **Post**.</span></span>

<span data-ttu-id="8a139-153">Per ulteriori informazioni su come liquidare le transazioni aperte, vedi [Panoramica della liquidazione](/cash-bank-management/settlement-overview.md).</span><span class="sxs-lookup"><span data-stu-id="8a139-153">For more information about how to settle open transactions, see [Settlement overview](/cash-bank-management/settlement-overview.md).</span></span>
