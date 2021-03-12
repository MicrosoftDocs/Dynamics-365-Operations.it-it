---
title: Liquidazione provvigione su pagamento
description: Questo argomento fornisce informazioni sulla liquidazione delle provvigioni sui pagamenti.
author: ilkond
manager: AnnBe
ms.date: 03/17/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Italy
ms.author: ilyako
ms.search.validFrom: 2020-06-01
ms.dyn365.ops.version: 10.0.10
ms.openlocfilehash: d3a9073b491511771cd8a8252b8b78ebfd8d1267
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4962620"
---
# <a name="commission-settlement-on-payments"></a><span data-ttu-id="6214b-103">Liquidazione provvigione su pagamento</span><span class="sxs-lookup"><span data-stu-id="6214b-103">Commission settlement on payments</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="6214b-104">In Italia, le società in genere non liquidano le provvigioni agli agenti di vendita quando vengono emesse le fatture.</span><span class="sxs-lookup"><span data-stu-id="6214b-104">In Italy, companies don't typically settle the commissions for their sales agents when invoices are issued.</span></span> <span data-ttu-id="6214b-105">Liquidano le provvigioni quando i clienti pagano l'intero saldo delle fatture.</span><span class="sxs-lookup"><span data-stu-id="6214b-105">Instead, they settle the commissions when customers pay the full balance of their invoices.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="6214b-106">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="6214b-106">Prerequisites</span></span>

<span data-ttu-id="6214b-107">Prima di poter utilizzare la funzionalità per la liquidazione delle provvigioni su pagamenti, devono essere soddisfatti i seguenti prerequisiti:</span><span class="sxs-lookup"><span data-stu-id="6214b-107">Before you can use the functionality for commission settlement on payments, the following prerequisites must be met:</span></span>

- <span data-ttu-id="6214b-108">L'indirizzo principale della persona giuridica deve essere in Italia.</span><span class="sxs-lookup"><span data-stu-id="6214b-108">The primary address of the legal entity must be in Italy.</span></span>
- <span data-ttu-id="6214b-109">La funzionalità **Liquidazione delle provvigioni sui pagamenti** deve essere attivata nell'area di lavoro **Gestione delle funzionalità**.</span><span class="sxs-lookup"><span data-stu-id="6214b-109">The **Commission settlement on payments** feature must be turned on in the **Feature management** workspace.</span></span> <span data-ttu-id="6214b-110">Per ulteriori informazioni, vedere [Panoramica della gestione funzionalità](../../fin-and-ops/get-started/feature-management/feature-management-overview.md).</span><span class="sxs-lookup"><span data-stu-id="6214b-110">For more information, see [Feature management overview](../../fin-and-ops/get-started/feature-management/feature-management-overview.md).</span></span>

## <a name="a-namedefault-commission-settlement-periodset-up-the-default-commission-settlement-method"></a><span data-ttu-id="6214b-111"><a name="default-commission-settlement-period">Impostare il metodo di liquidazione delle provvigioni predefinito</span><span class="sxs-lookup"><span data-stu-id="6214b-111"><a name="default-commission-settlement-period">Set up the default commission settlement method</span></span>

1. <span data-ttu-id="6214b-112">Andare a **Contabilità clienti** \> **Impostazioni** \> **Parametri contabilità clienti**.</span><span class="sxs-lookup"><span data-stu-id="6214b-112">Go to **Accounts receivable** \> **Setup** \> **Accounts receivable parameters**.</span></span>
2. <span data-ttu-id="6214b-113">Nella pagina **Parametri contabilità clienti**, nella scheda **Liquidazione** nella scheda dettaglio **Altro**, nel campo **Liquidazione delle provvigioni**, selezionare il metodo di liquidazione delle provvigioni predefinito che viene utilizzato quando viene creato un ordine cliente:</span><span class="sxs-lookup"><span data-stu-id="6214b-113">On the **Accounts receivable parameters** page, on the **Settlement** tab, on the **Other** FastTab, in the **Commission settlement** field, select the default commission settlement method that is used when a sales order is created:</span></span>

    - <span data-ttu-id="6214b-114">**Su fattura** - Le provvigioni vengono addebitate durante il processo di fatturazione.</span><span class="sxs-lookup"><span data-stu-id="6214b-114">**On invoice** – Commissions are charged during the invoice process.</span></span>
    - <span data-ttu-id="6214b-115">**Su pagamento** - Le provvigioni vengono addebitate durante il processo di pagamento.</span><span class="sxs-lookup"><span data-stu-id="6214b-115">**On payment** – Commissions are charged during the payment process.</span></span>

![Parametri contabilità clienti](media/emea-ita-exil-commission-setup-parameters.PNG)

## <a name="set-up-commission-calculations"></a><span data-ttu-id="6214b-117">Impostare i calcoli della provvigione</span><span class="sxs-lookup"><span data-stu-id="6214b-117">Set up commission calculations</span></span>

<span data-ttu-id="6214b-118">È possibile impostare il calcolo delle provvigioni per una provvigione **Su pagamento** andando a **Vendite e marketing** \> **Provvigioni** \> **Calcolo provvigione**.</span><span class="sxs-lookup"><span data-stu-id="6214b-118">You can set up the calculation of commissions for an **On payment** commission by going to **Sales and marketing** \> **Commissions** \> **Commission calculation**.</span></span>

![Impostare il calcolo della provvigione](media/emea-ita-exil-commission-%20calculation-setup.PNG)

<span data-ttu-id="6214b-120">Se l'opzione **Soglie di pagamento** nella sezione **Provvigioni su pagamento** è impostata su **Sì**, è possibile specificare due limiti (soglie) per i calcoli delle provvigioni:</span><span class="sxs-lookup"><span data-stu-id="6214b-120">If the **Payment thresholds** option in the **On payment commissions** section is set to **Yes**, you can specify two limits (thresholds) for commission calculations:</span></span>

- <span data-ttu-id="6214b-121">Se l'importo della provvigione raggiunto (in percentuale dell'importo raggiungibile) è più basso del limite inferiore, non vengono accumulate commissioni.</span><span class="sxs-lookup"><span data-stu-id="6214b-121">If the commission amount that is reached (as a percentage of the reachable amount) is below the lower limit, no commissions are accrued.</span></span>
- <span data-ttu-id="6214b-122">Quando viene raggiunto il limite superiore, viene accumulato l'intero importo raggiungibile.</span><span class="sxs-lookup"><span data-stu-id="6214b-122">When the upper limit is reached, the whole reachable amount is accrued.</span></span>

<span data-ttu-id="6214b-123">Tra i due limiti, le provvigioni vengono accumulate in modo regolare.</span><span class="sxs-lookup"><span data-stu-id="6214b-123">Between the two limits, commissions are accrued in the regular way.</span></span>

### <a name="example"></a><span data-ttu-id="6214b-124">Esempio</span><span class="sxs-lookup"><span data-stu-id="6214b-124">Example</span></span>

<span data-ttu-id="6214b-125">Considerare l'esempio riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="6214b-125">Consider the following example:</span></span>

- <span data-ttu-id="6214b-126">**Importo totale della fattura:** € 1.000</span><span class="sxs-lookup"><span data-stu-id="6214b-126">**Total amount of the invoice:** €1,000</span></span>
- <span data-ttu-id="6214b-127">**Limite inferiore:** 10 %</span><span class="sxs-lookup"><span data-stu-id="6214b-127">**Lower limit:** 10 percent</span></span>
- <span data-ttu-id="6214b-128">**Limite superiore:** 80 %</span><span class="sxs-lookup"><span data-stu-id="6214b-128">**Upper limit:** 80 percent</span></span>

<span data-ttu-id="6214b-129">Vengono effettuati i seguenti pagamenti:</span><span class="sxs-lookup"><span data-stu-id="6214b-129">The following payments are made:</span></span>

- <span data-ttu-id="6214b-130">€ 50 (5 % dell'importo totale della fattura): poiché le provvigioni sono inferiori al limite inferiore del 10 %, non si verifica alcun accumulo.</span><span class="sxs-lookup"><span data-stu-id="6214b-130">€50 (5 percent of the total amount of the invoice): Because commissions are below the lower limit of 10 percent, no accrual occurs.</span></span>
- <span data-ttu-id="6214b-131">€ 100 (10 % dell'importo totale della fattura): la fattura viene liquidata al 15 %.</span><span class="sxs-lookup"><span data-stu-id="6214b-131">€100 (10 percent of the total amount of the invoice): The invoice is settled at 15 percent.</span></span> <span data-ttu-id="6214b-132">Pertanto, le provvigioni maturano a questa percentuale.</span><span class="sxs-lookup"><span data-stu-id="6214b-132">Therefore, commissions are accrued at that percentage.</span></span>
- <span data-ttu-id="6214b-133">€ 500 (50 % dell'importo totale della fattura): la fattura viene liquidata al 65 %.</span><span class="sxs-lookup"><span data-stu-id="6214b-133">€500 (50 percent of the total amount of the invoice): The invoice is settled at 65 percent.</span></span> <span data-ttu-id="6214b-134">Le provvigioni maturano anche al 65 %.</span><span class="sxs-lookup"><span data-stu-id="6214b-134">Commissions are also accrued at 65 percent.</span></span>
- <span data-ttu-id="6214b-135">€ 200 (20 % dell'importo totale della fattura): la fattura viene liquidata al 85 %.</span><span class="sxs-lookup"><span data-stu-id="6214b-135">€200 (20 percent of the total amount of the invoice): The invoice is settled at 85 percent.</span></span> <span data-ttu-id="6214b-136">Poiché questa cifra supera il limite superiore, le provvigioni vengono completamente liquidate al 100 %.</span><span class="sxs-lookup"><span data-stu-id="6214b-136">Because this figure exceeds the upper limit, commissions become fully settled at 100 percent.</span></span>
- <span data-ttu-id="6214b-137">Ulteriori pagamenti non modificano l'importo maturato, poiché tale importo ha già raggiunto il limite superiore.</span><span class="sxs-lookup"><span data-stu-id="6214b-137">Further payments don't change the amount that is accrued, because that amount has already reached the upper limit.</span></span> <span data-ttu-id="6214b-138">Tuttavia, le transazioni di attribuzione per competenza vengono comunque create.</span><span class="sxs-lookup"><span data-stu-id="6214b-138">However, accrual transactions are still created.</span></span>

<span data-ttu-id="6214b-139">È possibile aggiungere un'altra impostazione al singolo agente che appartiene a un gruppo specifico.</span><span class="sxs-lookup"><span data-stu-id="6214b-139">Another setup can be added to the individual agent who belongs to a specific group.</span></span> <span data-ttu-id="6214b-140">Nei calcoli delle provvigioni, l'impostazione sugli agenti (dipendenti) ha una priorità più alta rispetto all'impostazione sulle vendite.</span><span class="sxs-lookup"><span data-stu-id="6214b-140">In commission calculations, the setup on agents (employees) has higher priority than the setup on sales.</span></span>

## <a name="set-the-commission-settlement-and-preview-commission-transactions-on-the-sales-order-page"></a><span data-ttu-id="6214b-141">Impostare la liquidazione delle provvigioni e visualizzare in anteprima le transazioni delle provvigioni nella pagina Ordine cliente</span><span class="sxs-lookup"><span data-stu-id="6214b-141">Set the commission settlement and preview commission transactions on the Sales order page</span></span>

<span data-ttu-id="6214b-142">Dopo aver creato un ordine cliente, un utente può aggiornare la liquidazione della provvigione nell'intestazione dell'ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="6214b-142">After a sales order is created, a user can update the commission settlement in the sales order header.</span></span>

1. <span data-ttu-id="6214b-143">Andare a **Contabilità clienti** \> **Ordini** \> **Tutti gli ordini cliente**.</span><span class="sxs-lookup"><span data-stu-id="6214b-143">Go to **Accounts receivable** \> **Orders** \> **All sales orders**.</span></span>
2. <span data-ttu-id="6214b-144">Selezionare e aprire un ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="6214b-144">Select and open a sales order.</span></span>
3. <span data-ttu-id="6214b-145">Nella pagina **Dettagli ordine cliente**, nella visualizzazione **Intestazione**, nella scheda dettaglio **Impostazione** aggiornare il valore del campo **Liquidazione delle provvigioni** come richiesto.</span><span class="sxs-lookup"><span data-stu-id="6214b-145">On the **Sales order details** page, in the **Header** view, on the **Setup** FastTab update the value of the **Commission settlement** field as you require.</span></span>

![Liquidazione delle provvigioni sull'ordine cliente](media/emea-ita-exil-commission-sales-order.png)

<span data-ttu-id="6214b-147">Per impostazione predefinita, il valore del campo **delle provvigioni** è ereditato dalla pagina **Parametri contabilità clienti**.</span><span class="sxs-lookup"><span data-stu-id="6214b-147">By default, the value of the **Commission settlement** field is inherited from the **Accounts receivable parameters** page.</span></span> <span data-ttu-id="6214b-148">Per ulteriori informazioni, vedere [Impostare il metodo di liquidazione delle provvigioni predefinito](#default-commission-settlement-period).</span><span class="sxs-lookup"><span data-stu-id="6214b-148">For more information, see [Set up the default commission settlement method](#default-commission-settlement-period).</span></span>

<span data-ttu-id="6214b-149">È inoltre possibile visualizzare in anteprima il calcolo della provvigione di vendita da un ordine cliente per ordini aperti o fatturati.</span><span class="sxs-lookup"><span data-stu-id="6214b-149">You can also preview the sales commission calculation from a sales order for either open or invoiced orders.</span></span> <span data-ttu-id="6214b-150">Nella pagina **Dettagli ordine cliente**, nella scheda **Generale**, selezionare **Informazioni correlate** \> **Anteprima provvigione**.</span><span class="sxs-lookup"><span data-stu-id="6214b-150">On the **Sales order details** page, on the **General** tab, select **Related information** \> **Commission preview**.</span></span>

![Anteprima delle transazioni delle provvigioni](media/emea-ita-exil-commission-preview.PNG)

> [!NOTE]
> <span data-ttu-id="6214b-152">Un utente può combinare gli ordini cliente in un'unica fattura se tutti gli ordini cliente per la fatturazione hanno lo stesso valore di **Liquidazione delle provvigioni** nell'intestazione dell'ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="6214b-152">A user can combine sales orders in a single invoice if all the sales orders for invoicing have the same **Commission settlement** value in the sales order header.</span></span>

### <a name="get-an-overview-of-commission-transactions-on-a-sales-order-invoice"></a><span data-ttu-id="6214b-153">Ottenere una panoramica delle transazioni delle provvigioni su una fattura dell'ordine cliente</span><span class="sxs-lookup"><span data-stu-id="6214b-153">Get an overview of commission transactions on a sales order invoice</span></span>

<span data-ttu-id="6214b-154">È inoltre possibile visualizzare le transazioni delle provvigioni nella pagina **Giornale di registrazione fatture**.</span><span class="sxs-lookup"><span data-stu-id="6214b-154">You can also view commission transactions on the **Invoice journal** page.</span></span>

1. <span data-ttu-id="6214b-155">Andare a **Contabilità clienti** \> **Richieste di informazioni e report** \> **Fatture** \> **Giornale di registrazione fatture**.</span><span class="sxs-lookup"><span data-stu-id="6214b-155">Go to **Accounts receivable** \> **Inquiries and reports** \> **Invoices** \> **Invoice journal**.</span></span>
2. <span data-ttu-id="6214b-156">Nella scheda **Fattura**, selezionare **Dettagli** \> **Transazioni delle provvigioni**.</span><span class="sxs-lookup"><span data-stu-id="6214b-156">On the **Invoice** tab, select **Details** \> **Commission transactions**.</span></span>

> [!NOTE]
> <span data-ttu-id="6214b-157">Quando si registra la fattura, il sistema crea le transazioni di provvigione e giustificativo.</span><span class="sxs-lookup"><span data-stu-id="6214b-157">When you post the invoice, the system creates commission and voucher transactions.</span></span> <span data-ttu-id="6214b-158">Se il valore del campo **Liquidazione delle provvigioni** è **Su fattura** nell'intestazione dell'ordine cliente, il sistema crea un record **Liquidazione**.</span><span class="sxs-lookup"><span data-stu-id="6214b-158">If the value in the **Commission settlement** field is **On invoice** in the sales order header, the system creates a **Settlement** record.</span></span> <span data-ttu-id="6214b-159">Se il valore nel campo **Liquidazione delle provvigioni** è **Su pagamento** nell'intestazione dell'ordine cliente, il record **Liquidazione** viene creato solo dopo che la fattura e il pagamento sono stati liquidati.</span><span class="sxs-lookup"><span data-stu-id="6214b-159">If the value in the **Commission settlement** field is **On payment** in the sales order header, the **Settlement** record is created only after the invoice and a payment are settled.</span></span>
