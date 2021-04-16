---
title: Pagamenti IVA e regole di arrotondamento
description: Questo articolo illustra il funzionamento dell'impostazione della regola di arrotondamento in Uffici IVA e l'arrotondamento del saldo dell'IVA durante il processo Liquida e registra IVA.
author: ShylaThompson
ms.date: 04/20/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TaxAuthority
audience: Application User
ms.reviewer: roschlom
ms.custom: 6134
ms.assetid: 7dcd3cf5-ebdf-4a9f-806c-1296c7da0331
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: edbe92d009c77702a21d32afb5aebe93bc5e2ee0
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5815382"
---
# <a name="sales-tax-payments-and-rounding-rules"></a><span data-ttu-id="a849c-103">Pagamenti IVA e regole di arrotondamento</span><span class="sxs-lookup"><span data-stu-id="a849c-103">Sales tax payments and rounding rules</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a849c-104">Questo articolo illustra il funzionamento dell'impostazione della regola di arrotondamento in Uffici IVA e l'arrotondamento del saldo dell'IVA durante il processo Liquida e registra IVA.</span><span class="sxs-lookup"><span data-stu-id="a849c-104">This article explains how the rounding rule setup on the Sales tax authorities works and rounding the sales tax balance during the Settle and post sales tax job.</span></span>

<span data-ttu-id="a849c-105">Periodicamente, l'IVA deve essere dichiarata e pagata agli uffici tributari.</span><span class="sxs-lookup"><span data-stu-id="a849c-105">Periodically, sales tax needs to be reported and paid to tax authorities.</span></span> <span data-ttu-id="a849c-106">Questa operazione può essere effettuata mediante l'esecuzione del processo di liquidazione e registrazione IVA nella pagina IVA.</span><span class="sxs-lookup"><span data-stu-id="a849c-106">This can be done by running the settle and post sales tax process in the Sales tax page.</span></span> <span data-ttu-id="a849c-107">L'IVA per un periodo verrà liquidata nei conti IVA e il saldo IVA verrà registrato nel conto di liquidazione IVA.</span><span class="sxs-lookup"><span data-stu-id="a849c-107">Sales tax for a period will be settled against the sales tax accounts and the sales tax balance will be posted to the Sales tax settlement account.</span></span> <span data-ttu-id="a849c-108">Il saldo IVA, registrato nel conto di liquidazione IVA, può essere arrotondato in base a quanto richiesto dagli uffici tributari impostando una regola di arrotondamento nella pagina IVA.</span><span class="sxs-lookup"><span data-stu-id="a849c-108">The sales tax balance, which is posted on the Sales tax settlement account, can be rounded as required by tax authorities by setting up a rounding rule on the Sales tax page.</span></span> 

<span data-ttu-id="a849c-109">La differenza di arrotondamento viene registrata nel conto di arrotondamento IVA selezionato nel campo Conti per transazioni automatiche nella contabilità generale.</span><span class="sxs-lookup"><span data-stu-id="a849c-109">The rounding difference is posted to the Sales tax rounding account that is selected in the Accounts for automatic transactions field in the General ledger.</span></span>

<span data-ttu-id="a849c-110">Nell'esempio seguente viene illustrato il funzionamento della regola di arrotondamento IVA.</span><span class="sxs-lookup"><span data-stu-id="a849c-110">The below example illustrates how the rounding rule on Sales tax authority works.</span></span>

## <a name="examples"></a><span data-ttu-id="a849c-111">Esempi</span><span class="sxs-lookup"><span data-stu-id="a849c-111">Examples</span></span>

<span data-ttu-id="a849c-112">L'IVA totale per un periodo mostra un saldo in avere di -98.765,43.</span><span class="sxs-lookup"><span data-stu-id="a849c-112">The total sales tax for a period shows a credit balance of -98,765.43.</span></span> <span data-ttu-id="a849c-113">La persona giuridica dispone più prelievo IVA superiore a quanto ha pagato.</span><span class="sxs-lookup"><span data-stu-id="a849c-113">The legal entity collected more sales taxes than it paid.</span></span> <span data-ttu-id="a849c-114">Di conseguenza, la persona giuridica deve denaro all'ufficio tributario.</span><span class="sxs-lookup"><span data-stu-id="a849c-114">Therefore, the legal entity owes money to the tax authority.</span></span> 

<span data-ttu-id="a849c-115">La persona giuridica desidera utilizzare un metodo che consenta di arrotondare il saldo all'unità più vicina.</span><span class="sxs-lookup"><span data-stu-id="a849c-115">The legal entity wants to use a rounding method that rounds the balance to the nearest 1.00.</span></span> <span data-ttu-id="a849c-116">L'utente responsabile della contabilità IVA esegue le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="a849c-116">The user who is responsible for sales tax accounting performs the following steps.</span></span>

1. <span data-ttu-id="a849c-117">Fare click su **Imposte** > **Imposte indirette** > **IVA** > **Uffici IVA**.</span><span class="sxs-lookup"><span data-stu-id="a849c-117">Click **Tax** > **Indirect taxes** > **Sales tax** > **Sales tax authorities**.</span></span>
2. <span data-ttu-id="a849c-118">Nella scheda dettaglio **Generale**, nel campo **Tipo di arrotondamento** selezionare **Normale**.</span><span class="sxs-lookup"><span data-stu-id="a849c-118">On the **General** FastTab, in the **Rounding form** field, select **Normal**.</span></span>
3. <span data-ttu-id="a849c-119">Nel campo **Arrotondamento**, immettere 1,00.</span><span class="sxs-lookup"><span data-stu-id="a849c-119">In the **Round-off** field, enter 1.00.</span></span>
4. <span data-ttu-id="a849c-120">Quando è il momento di pagare le imposte sulle vendite all'autorità fiscale, andare a **Tasse** > **Dichiarazioni** > **IVA** > **Liquida e registra IVA**.</span><span class="sxs-lookup"><span data-stu-id="a849c-120">When it is time to pay the sales taxes to the tax authority, go to **Tax** > **Declarations** > **Sales tax** > **Settle and post sale tax**.</span></span> <span data-ttu-id="a849c-121">Nel conti di liquidazione IVA, è possibile notare che l'importo di soggettività tributaria di **98.765,43** viene arrotondato a **98.765**.</span><span class="sxs-lookup"><span data-stu-id="a849c-121">On the sales tax settlement account, you can see that the tax liability amount of **98,765.43** is rounded to **98,765**.</span></span>

<span data-ttu-id="a849c-122">Le seguente tabella mostra un importo di 98.765,43 arrotondato utilizzando ogni metodo di arrotondamento disponibile nel campo **Tipo di arrotondamento** nella pagina **Uffici IVA**.</span><span class="sxs-lookup"><span data-stu-id="a849c-122">The following table shows how an amount of 98,765.43 is rounded by using each rounding method that is available in the **Rounding form** field in the **Sales tax authorities** page.</span></span>

> [!NOTE]                                                                                  
> <span data-ttu-id="a849c-123">Se il valore di arrotondamento è impostato su 0,00:</span><span class="sxs-lookup"><span data-stu-id="a849c-123">If the round-off value is set as 0.00, then:</span></span>
>
> - <span data-ttu-id="a849c-124">Per l'arrotondamento normale, il comportamento dell'arrotondamento è lo stesso di **Arrotondamento = 0,01**.</span><span class="sxs-lookup"><span data-stu-id="a849c-124">For normal rounding, the rounding behavior is the same as for **Round-off = 0.01**.</span></span>
> - <span data-ttu-id="a849c-125">Per **Opzioni Tipo di arrotondamento**, **Arrotondamento per difetto**, **Arrotondamento per eccesso** e **A proprio vantaggio**, il comportamento è lo stesso di **Arrotondamento = 1,00**.</span><span class="sxs-lookup"><span data-stu-id="a849c-125">For the **Rounding form options**, **Downward**, **Rounding-up**, and **Own advantage**, the behavior is the same as for **Round-off = 1.00**.</span></span>

| <span data-ttu-id="a849c-126">Opzione Tipo di arrotondamento</span><span class="sxs-lookup"><span data-stu-id="a849c-126">Rounding form option</span></span>                | <span data-ttu-id="a849c-127">Valore arrotondamento = 0,01</span><span class="sxs-lookup"><span data-stu-id="a849c-127">Round-off value = 0.01</span></span> | <span data-ttu-id="a849c-128">Valore arrotondamento = 0,10</span><span class="sxs-lookup"><span data-stu-id="a849c-128">Round-off value = 0.10</span></span> | <span data-ttu-id="a849c-129">Valore arrotondamento = 1,00</span><span class="sxs-lookup"><span data-stu-id="a849c-129">Round-off value = 1.00</span></span> | <span data-ttu-id="a849c-130">Valore arrotondamento = 100,00</span><span class="sxs-lookup"><span data-stu-id="a849c-130">Round-off value = 100.00</span></span> | <span data-ttu-id="a849c-131">Valore arrotondamento = 0,00</span><span class="sxs-lookup"><span data-stu-id="a849c-131">Round-off value = 0.00</span></span>   |
|-------------------------------------|------------------------|------------------------|------------------------|--------------------------|--------------------------|
| <span data-ttu-id="a849c-132">Normale</span><span class="sxs-lookup"><span data-stu-id="a849c-132">Normal</span></span>                              | <span data-ttu-id="a849c-133">98,765.43</span><span class="sxs-lookup"><span data-stu-id="a849c-133">98,765.43</span></span>              | <span data-ttu-id="a849c-134">98,765.40</span><span class="sxs-lookup"><span data-stu-id="a849c-134">98,765.40</span></span>              | <span data-ttu-id="a849c-135">98,765.00</span><span class="sxs-lookup"><span data-stu-id="a849c-135">98,765.00</span></span>              | <span data-ttu-id="a849c-136">98,800.00</span><span class="sxs-lookup"><span data-stu-id="a849c-136">98,800.00</span></span>                | <span data-ttu-id="a849c-137">98,765.43</span><span class="sxs-lookup"><span data-stu-id="a849c-137">98,765.43</span></span>                |
| <span data-ttu-id="a849c-138">Arrotondamento per difetto</span><span class="sxs-lookup"><span data-stu-id="a849c-138">Downward</span></span>                            | <span data-ttu-id="a849c-139">98,765.43</span><span class="sxs-lookup"><span data-stu-id="a849c-139">98,765.43</span></span>              | <span data-ttu-id="a849c-140">98,765.40</span><span class="sxs-lookup"><span data-stu-id="a849c-140">98,765.40</span></span>              | <span data-ttu-id="a849c-141">98,765.00</span><span class="sxs-lookup"><span data-stu-id="a849c-141">98,765.00</span></span>              | <span data-ttu-id="a849c-142">98,700.00</span><span class="sxs-lookup"><span data-stu-id="a849c-142">98,700.00</span></span>                | <span data-ttu-id="a849c-143">98,765.00</span><span class="sxs-lookup"><span data-stu-id="a849c-143">98,765.00</span></span>                |
| <span data-ttu-id="a849c-144">Arrotondamento per eccesso</span><span class="sxs-lookup"><span data-stu-id="a849c-144">Rounding-up</span></span>                         | <span data-ttu-id="a849c-145">98,765.43</span><span class="sxs-lookup"><span data-stu-id="a849c-145">98,765.43</span></span>              | <span data-ttu-id="a849c-146">98,765.50</span><span class="sxs-lookup"><span data-stu-id="a849c-146">98,765.50</span></span>              | <span data-ttu-id="a849c-147">98,766.00</span><span class="sxs-lookup"><span data-stu-id="a849c-147">98,766.00</span></span>              | <span data-ttu-id="a849c-148">98,800.00</span><span class="sxs-lookup"><span data-stu-id="a849c-148">98,800.00</span></span>                | <span data-ttu-id="a849c-149">98,766.00</span><span class="sxs-lookup"><span data-stu-id="a849c-149">98,766.00</span></span>                |
| <span data-ttu-id="a849c-150">A proprio vantaggio, per un saldo in avere</span><span class="sxs-lookup"><span data-stu-id="a849c-150">Own advantage, for a credit balance</span></span> | <span data-ttu-id="a849c-151">98,765.43</span><span class="sxs-lookup"><span data-stu-id="a849c-151">98,765.43</span></span>              | <span data-ttu-id="a849c-152">98,765.40</span><span class="sxs-lookup"><span data-stu-id="a849c-152">98,765.40</span></span>              | <span data-ttu-id="a849c-153">98,765.00</span><span class="sxs-lookup"><span data-stu-id="a849c-153">98,765.00</span></span>              | <span data-ttu-id="a849c-154">98,700.00</span><span class="sxs-lookup"><span data-stu-id="a849c-154">98,700.00</span></span>                | <span data-ttu-id="a849c-155">98,765.00</span><span class="sxs-lookup"><span data-stu-id="a849c-155">98,765.00</span></span>                |
| <span data-ttu-id="a849c-156">A proprio vantaggio, per un saldo in dare</span><span class="sxs-lookup"><span data-stu-id="a849c-156">Own advantage, for a debit balance</span></span>  | <span data-ttu-id="a849c-157">98,765.43</span><span class="sxs-lookup"><span data-stu-id="a849c-157">98,765.43</span></span>              | <span data-ttu-id="a849c-158">98,765.50</span><span class="sxs-lookup"><span data-stu-id="a849c-158">98,765.50</span></span>              | <span data-ttu-id="a849c-159">98,766.00</span><span class="sxs-lookup"><span data-stu-id="a849c-159">98,766.00</span></span>              | <span data-ttu-id="a849c-160">98,800.00</span><span class="sxs-lookup"><span data-stu-id="a849c-160">98,800.00</span></span>                | <span data-ttu-id="a849c-161">98,766.00</span><span class="sxs-lookup"><span data-stu-id="a849c-161">98,766.00</span></span>                |

### <a name="normal-round-and-round-precision-is-001"></a><span data-ttu-id="a849c-162">Arrotondamento normale e la precisione dell'arrotondamento è 0.01</span><span class="sxs-lookup"><span data-stu-id="a849c-162">Normal round, and round precision is 0.01</span></span>

<table>
  <tr>
    <td><span data-ttu-id="a849c-163">Arrotondamento</span><span class="sxs-lookup"><span data-stu-id="a849c-163">Rounding</span></span>
    </td>
    <td><span data-ttu-id="a849c-164">Processo di calcolo</span><span class="sxs-lookup"><span data-stu-id="a849c-164">Calculation process</span></span>
    </td>
  </tr>
    <tr>
    <td><span data-ttu-id="a849c-165">round(1,015, 0,01) = 1,02</span><span class="sxs-lookup"><span data-stu-id="a849c-165">round(1.015, 0.01) = 1.02</span></span>
    </td>
    <td>
      <ol>
        <li><span data-ttu-id="a849c-166">round(1,015 / 0,01, 0) = round(101,5, 0) = 102</span><span class="sxs-lookup"><span data-stu-id="a849c-166">round(1.015 / 0.01, 0) = round(101.5, 0) = 102</span></span>
        </li>
        <li><span data-ttu-id="a849c-167">102 \* 0,01 = 1,02</span><span class="sxs-lookup"><span data-stu-id="a849c-167">102 \* 0.01 = 1.02</span></span>
        </li>
      </ol>
    </td>
  </tr>
    <tr>
    <td><span data-ttu-id="a849c-168">round(1,014, 0,01) = 1,01</span><span class="sxs-lookup"><span data-stu-id="a849c-168">round(1.014, 0.01) = 1.01</span></span>
    </td>
    <td> <ol>
        <li><span data-ttu-id="a849c-169">round(1,014 / 0,01, 0) = round(101,4, 0) = 101</span><span class="sxs-lookup"><span data-stu-id="a849c-169">round(1.014 / 0.01, 0) = round(101.4, 0) = 101</span></span>
        </li>
        <li><span data-ttu-id="a849c-170">101 \* 0,01 = 1,01</span><span class="sxs-lookup"><span data-stu-id="a849c-170">101 \* 0.01 = 1.01</span></span>
        </li>
      </ol>
    </td>
  </tr>
    <tr>
    <td><span data-ttu-id="a849c-171">round(1,011, 0,02) = 1,02</span><span class="sxs-lookup"><span data-stu-id="a849c-171">round(1.011, 0.02) = 1.02</span></span>
    </td>
    <td> <ol>
        <li><span data-ttu-id="a849c-172">round(1,011 / 0,02, 0) = round(50,55, 0) = 51</span><span class="sxs-lookup"><span data-stu-id="a849c-172">round(1.011 / 0.02, 0) = round(50.55, 0) = 51</span></span>
        </li>
        <li><span data-ttu-id="a849c-173">51 \* 0,02 = 1,02</span><span class="sxs-lookup"><span data-stu-id="a849c-173">51 \* 0.02 = 1.02</span></span>
        </li>
      </ol>
    </td>
  </tr>
    <tr>
    <td><span data-ttu-id="a849c-174">round(1,009, 0,02) = 1,00</span><span class="sxs-lookup"><span data-stu-id="a849c-174">round(1.009, 0.02) = 1.00</span></span>
    </td>
    <td> <ol>
        <li><span data-ttu-id="a849c-175">round(1,009 / 0,02, 0) = round(50,45, 0) = 50</span><span class="sxs-lookup"><span data-stu-id="a849c-175">round(1.009 / 0.02, 0) = round(50.45, 0) = 50</span></span>
        </li>
        <li><span data-ttu-id="a849c-176">50 \* 0,02 = 1,00</span><span class="sxs-lookup"><span data-stu-id="a849c-176">50 \* 0.02 = 1.00</span></span>
        </li>
      </ol>
    </td>
  </tr>
</table>

> [!NOTE]                                                                                  
> <span data-ttu-id="a849c-177">Se si seleziona A proprio vantaggio, l'arrotondamento è sempre a vantaggio della persona giuridica.</span><span class="sxs-lookup"><span data-stu-id="a849c-177">If you select Own advantage, the rounding is always to the advantage of the legal entity.</span></span> 

<span data-ttu-id="a849c-178">Per ulteriori informazioni, vedere i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="a849c-178">For more information, see the following topics:</span></span>
- [<span data-ttu-id="a849c-179">Panoramica dell'IVA</span><span class="sxs-lookup"><span data-stu-id="a849c-179">Sales tax overview</span></span>](indirect-taxes-overview.md)
- [<span data-ttu-id="a849c-180">Creare un pagamento IVA</span><span class="sxs-lookup"><span data-stu-id="a849c-180">Create a sales tax payment</span></span>](tasks/create-sales-tax-payment.md)
- [<span data-ttu-id="a849c-181">Creare transazioni IVA in documenti</span><span class="sxs-lookup"><span data-stu-id="a849c-181">Create sales tax transactions on documents</span></span>](tasks/create-sales-tax-transactions-documents.md)
- [<span data-ttu-id="a849c-182">Visualizzare transazioni IVA registrate</span><span class="sxs-lookup"><span data-stu-id="a849c-182">View posted sales tax transactions</span></span>](tasks/view-posted-sales-tax-transactions.md)
- [<span data-ttu-id="a849c-183">Funzione di arrotondamento</span><span class="sxs-lookup"><span data-stu-id="a849c-183">round Function</span></span>](https://msdn.microsoft.com/library/aa850656.aspx)




[!INCLUDE[footer-include](../../includes/footer-banner.md)]