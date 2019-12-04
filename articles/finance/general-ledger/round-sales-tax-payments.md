---
title: Pagamenti IVA e regole di arrotondamento
description: Questo articolo illustra il funzionamento dell'impostazione della regola di arrotondamento in Uffici IVA e l'arrotondamento del saldo dell'IVA durante il processo Liquida e registra IVA.
author: ShylaThompson
manager: AnnBe
ms.date: 05/30/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxAuthority
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 6134
ms.assetid: 7dcd3cf5-ebdf-4a9f-806c-1296c7da0331
ms.search.region: Global
ms.author: yijialuan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4e66a62007025964b3d58ff0620ebecd6d9769f9
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/06/2019
ms.locfileid: "2771754"
---
# <a name="sales-tax-payments-and-rounding-rules"></a><span data-ttu-id="d39e5-103">Pagamenti IVA e regole di arrotondamento</span><span class="sxs-lookup"><span data-stu-id="d39e5-103">Sales tax payments and rounding rules</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d39e5-104">Questo articolo illustra il funzionamento dell'impostazione della regola di arrotondamento in Uffici IVA e l'arrotondamento del saldo dell'IVA durante il processo Liquida e registra IVA.</span><span class="sxs-lookup"><span data-stu-id="d39e5-104">This article explains how the rounding rule setup on the Sales tax authorities works and rounding the sales tax balance during the Settle and post sales tax job.</span></span>

<span data-ttu-id="d39e5-105">Periodicamente, l'IVA deve essere dichiarata e pagata agli uffici tributari.</span><span class="sxs-lookup"><span data-stu-id="d39e5-105">Periodically, sales tax needs to be reported and paid to tax authorities.</span></span> <span data-ttu-id="d39e5-106">Questa operazione può essere effettuata mediante l'esecuzione del processo di liquidazione e registrazione IVA nella pagina IVA.</span><span class="sxs-lookup"><span data-stu-id="d39e5-106">This can be done by running the settle and post sales tax process in the Sales tax page.</span></span> <span data-ttu-id="d39e5-107">L'IVA per un periodo verrà liquidata nei conti IVA e il saldo IVA verrà registrato nel conto di liquidazione IVA.</span><span class="sxs-lookup"><span data-stu-id="d39e5-107">Sales tax for a period will be settled against the sales tax accounts and the sales tax balance will be posted to the Sales tax settlement account.</span></span> <span data-ttu-id="d39e5-108">Il saldo IVA, registrato nel conto di liquidazione IVA, può essere arrotondato in base a quanto richiesto dagli uffici tributari impostando una regola di arrotondamento nella pagina IVA.</span><span class="sxs-lookup"><span data-stu-id="d39e5-108">The sales tax balance, which is posted on the Sales tax settlement account, can be rounded as required by tax authorities by setting up a rounding rule on the Sales tax page.</span></span> 

<span data-ttu-id="d39e5-109">La differenza di arrotondamento viene registrata nel conto di arrotondamento IVA selezionato nel campo Conti per transazioni automatiche nella contabilità generale.</span><span class="sxs-lookup"><span data-stu-id="d39e5-109">The rounding difference is posted to the Sales tax rounding account that is selected in the Accounts for automatic transactions field in the General ledger.</span></span>

<span data-ttu-id="d39e5-110">Nell'esempio seguente viene illustrato il funzionamento della regola di arrotondamento IVA.</span><span class="sxs-lookup"><span data-stu-id="d39e5-110">The below example illustrates how the rounding rule on Sales tax authority works.</span></span>

## <a name="examples"></a><span data-ttu-id="d39e5-111">Esempi</span><span class="sxs-lookup"><span data-stu-id="d39e5-111">Examples</span></span>

<span data-ttu-id="d39e5-112">L'IVA totale per un periodo mostra un saldo in avere di -98.765,43.</span><span class="sxs-lookup"><span data-stu-id="d39e5-112">The total sales tax for a period shows a credit balance of -98,765.43.</span></span> <span data-ttu-id="d39e5-113">La persona giuridica dispone più prelievo IVA superiore a quanto ha pagato.</span><span class="sxs-lookup"><span data-stu-id="d39e5-113">The legal entity collected more sales taxes than it paid.</span></span> <span data-ttu-id="d39e5-114">Di conseguenza, la persona giuridica deve denaro all'ufficio tributario.</span><span class="sxs-lookup"><span data-stu-id="d39e5-114">Therefore, the legal entity owes money to the tax authority.</span></span> 

<span data-ttu-id="d39e5-115">La persona giuridica desidera utilizzare un metodo che consenta di arrotondare il saldo all'unità più vicina.</span><span class="sxs-lookup"><span data-stu-id="d39e5-115">The legal entity wants to use a rounding method that rounds the balance to the nearest 1.00.</span></span> <span data-ttu-id="d39e5-116">L'utente responsabile della contabilità IVA esegue le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="d39e5-116">The user who is responsible for sales tax accounting performs the following steps.</span></span>

1.  <span data-ttu-id="d39e5-117">Fare clic su Imposta &gt; Imposte indirette &gt; IVA &gt; Uffici IVA.</span><span class="sxs-lookup"><span data-stu-id="d39e5-117">Click Tax &gt; Indirect taxes &gt; Sales tax &gt; Sales tax authorities</span></span>
2.  <span data-ttu-id="d39e5-118">Nella scheda dettaglio Generale selezionare Normale nel campo Tipo di arrotondamento.</span><span class="sxs-lookup"><span data-stu-id="d39e5-118">On the General FastTab, select Normal in the Rounding form field.</span></span>
3.  <span data-ttu-id="d39e5-119">Nel campo Arrotondamento immettere 1.</span><span class="sxs-lookup"><span data-stu-id="d39e5-119">In the Round-off field, enter 1.00.</span></span>
4.  <span data-ttu-id="d39e5-120">Al momento del pagamento dell'IVA all'ufficio tributario, aprire la pagina Liquida e registra IVA.</span><span class="sxs-lookup"><span data-stu-id="d39e5-120">When it is time to pay the sales taxes to the tax authority, open the Settle and post sales tax page.</span></span> <span data-ttu-id="d39e5-121">Fare clic su Imposta &gt; Dichiarazioni &gt; IVA &gt; Liquida e registra IVA.</span><span class="sxs-lookup"><span data-stu-id="d39e5-121">(Click Tax &gt; Declarations &gt; Sales tax &gt; Settle and post sales tax.)</span></span>
5.  <span data-ttu-id="d39e5-122">Nel conti di liquidazione IVA l'importo di soggettività tributaria di 98.765,43 viene arrotondato a 98.765.</span><span class="sxs-lookup"><span data-stu-id="d39e5-122">On the sales tax settlement account, the tax liability amount of 98,765.43 is rounded to 98,765.</span></span>

<span data-ttu-id="d39e5-123">Le seguente tabella mostra un importo di 98.765,43 arrotondato utilizzando ogni metodo di arrotondamento disponibile nel campo Tipo di arrotondamento del modulo Uffici IVA.</span><span class="sxs-lookup"><span data-stu-id="d39e5-123">The following table shows how an amount of 98,765.43 is rounded by using each rounding method that is available in the Rounding form field in the Sales tax authorities page.</span></span>

| <span data-ttu-id="d39e5-124">Opzione Tipo di arrotondamento</span><span class="sxs-lookup"><span data-stu-id="d39e5-124">Rounding form option</span></span>                | <span data-ttu-id="d39e5-125">Valore arrotondamento = 0,01</span><span class="sxs-lookup"><span data-stu-id="d39e5-125">Round-off value = 0.01</span></span> | <span data-ttu-id="d39e5-126">Valore arrotondamento = 0,10</span><span class="sxs-lookup"><span data-stu-id="d39e5-126">Round-off value = 0.10</span></span> | <span data-ttu-id="d39e5-127">Valore arrotondamento = 1,00</span><span class="sxs-lookup"><span data-stu-id="d39e5-127">Round-off value = 1.00</span></span> | <span data-ttu-id="d39e5-128">Valore arrotondamento = 100,00</span><span class="sxs-lookup"><span data-stu-id="d39e5-128">Round-off value = 100.00</span></span> |
|-------------------------------------|------------------------|------------------------|------------------------|--------------------------|
| <span data-ttu-id="d39e5-129">Normale</span><span class="sxs-lookup"><span data-stu-id="d39e5-129">Normal</span></span>                              | <span data-ttu-id="d39e5-130">98.765,43</span><span class="sxs-lookup"><span data-stu-id="d39e5-130">98,765.43</span></span>              | <span data-ttu-id="d39e5-131">98.765,40</span><span class="sxs-lookup"><span data-stu-id="d39e5-131">98,765.40</span></span>              | <span data-ttu-id="d39e5-132">98.765,00</span><span class="sxs-lookup"><span data-stu-id="d39e5-132">98,765.00</span></span>              | <span data-ttu-id="d39e5-133">98.800,00</span><span class="sxs-lookup"><span data-stu-id="d39e5-133">98,800.00</span></span>                |
| <span data-ttu-id="d39e5-134">Arrotondamento per difetto</span><span class="sxs-lookup"><span data-stu-id="d39e5-134">Downward</span></span>                            | <span data-ttu-id="d39e5-135">98.765,43</span><span class="sxs-lookup"><span data-stu-id="d39e5-135">98,765.43</span></span>              | <span data-ttu-id="d39e5-136">98.765,40</span><span class="sxs-lookup"><span data-stu-id="d39e5-136">98,765.40</span></span>              | <span data-ttu-id="d39e5-137">98.765,00</span><span class="sxs-lookup"><span data-stu-id="d39e5-137">98,765.00</span></span>              | <span data-ttu-id="d39e5-138">98.700,00</span><span class="sxs-lookup"><span data-stu-id="d39e5-138">98,700.00</span></span>                |
| <span data-ttu-id="d39e5-139">Arrotondamento per eccesso</span><span class="sxs-lookup"><span data-stu-id="d39e5-139">Rounding-up</span></span>                         | <span data-ttu-id="d39e5-140">98.765,43</span><span class="sxs-lookup"><span data-stu-id="d39e5-140">98,765.43</span></span>              | <span data-ttu-id="d39e5-141">98.765,50</span><span class="sxs-lookup"><span data-stu-id="d39e5-141">98,765.50</span></span>              | <span data-ttu-id="d39e5-142">98.766,00</span><span class="sxs-lookup"><span data-stu-id="d39e5-142">98,766.00</span></span>              | <span data-ttu-id="d39e5-143">98.800,00</span><span class="sxs-lookup"><span data-stu-id="d39e5-143">98,800.00</span></span>                |
| <span data-ttu-id="d39e5-144">A proprio vantaggio, per un saldo in avere</span><span class="sxs-lookup"><span data-stu-id="d39e5-144">Own advantage, for a credit balance</span></span> | <span data-ttu-id="d39e5-145">98.765,43</span><span class="sxs-lookup"><span data-stu-id="d39e5-145">98,765.43</span></span>              | <span data-ttu-id="d39e5-146">98.765,40</span><span class="sxs-lookup"><span data-stu-id="d39e5-146">98,765.40</span></span>              | <span data-ttu-id="d39e5-147">98.765,00</span><span class="sxs-lookup"><span data-stu-id="d39e5-147">98,765.00</span></span>              | <span data-ttu-id="d39e5-148">98.700,00</span><span class="sxs-lookup"><span data-stu-id="d39e5-148">98,700.00</span></span>                |
| <span data-ttu-id="d39e5-149">A proprio vantaggio, per un saldo in dare</span><span class="sxs-lookup"><span data-stu-id="d39e5-149">Own advantage, for a debit balance</span></span>  | <span data-ttu-id="d39e5-150">98.765,43</span><span class="sxs-lookup"><span data-stu-id="d39e5-150">98,765.43</span></span>              | <span data-ttu-id="d39e5-151">98.765,50</span><span class="sxs-lookup"><span data-stu-id="d39e5-151">98,765.50</span></span>              | <span data-ttu-id="d39e5-152">98.766,00</span><span class="sxs-lookup"><span data-stu-id="d39e5-152">98,766.00</span></span>              | <span data-ttu-id="d39e5-153">98.800,00</span><span class="sxs-lookup"><span data-stu-id="d39e5-153">98,800.00</span></span>                |


### <a name="no-rounding-at-all-since-the-round-off-is-000"></a><span data-ttu-id="d39e5-154">Nessun arrotondamento, poiché è 0,00</span><span class="sxs-lookup"><span data-stu-id="d39e5-154">No rounding at all, since the round-off is 0.00</span></span>

<span data-ttu-id="d39e5-155">round(1,0151, 0,00) = 1,0151 round(1,0149, 0,00) = 1,0149</span><span class="sxs-lookup"><span data-stu-id="d39e5-155">round(1.0151, 0.00) = 1.0151 round(1.0149, 0.00) = 1.0149</span></span>

### <a name="normal-round-and-round-precision-is-001"></a><span data-ttu-id="d39e5-156">Arrotondamento normale e la precisione dell'arrotondamento è 0.01</span><span class="sxs-lookup"><span data-stu-id="d39e5-156">Normal round, and round precision is 0.01</span></span>

<table>
  <tr>
    <td><span data-ttu-id="d39e5-157">Arrotondamento</span><span class="sxs-lookup"><span data-stu-id="d39e5-157">Rounding</span></span>
    </td>
    <td><span data-ttu-id="d39e5-158">Processo di calcolo</span><span class="sxs-lookup"><span data-stu-id="d39e5-158">Calculation process</span></span>
    </td>
  </tr>
    <tr>
    <td><span data-ttu-id="d39e5-159">round(1,015, 0,01) = 1,02</span><span class="sxs-lookup"><span data-stu-id="d39e5-159">round(1.015, 0.01) = 1.02</span></span>
    </td>
    <td>
      <ol>
        <li><span data-ttu-id="d39e5-160">round(1,015 / 0,01, 0) = round(101,5, 0) = 102</span><span class="sxs-lookup"><span data-stu-id="d39e5-160">round(1.015 / 0.01, 0) = round(101.5, 0) = 102</span></span>
        </li>
        <li><span data-ttu-id="d39e5-161">102 \* 0,01 = 1,02</span><span class="sxs-lookup"><span data-stu-id="d39e5-161">102 \* 0.01 = 1.02</span></span>
        </li>
      </ol>
    </td>
  </tr>
    <tr>
    <td><span data-ttu-id="d39e5-162">round(1,014, 0,01) = 1,01</span><span class="sxs-lookup"><span data-stu-id="d39e5-162">round(1.014, 0.01) = 1.01</span></span>
    </td>
    <td> <ol>
        <li><span data-ttu-id="d39e5-163">round(1,014 / 0,01, 0) = round(101,4, 0) = 101</span><span class="sxs-lookup"><span data-stu-id="d39e5-163">round(1.014 / 0.01, 0) = round(101.4, 0) = 101</span></span>
        </li>
        <li><span data-ttu-id="d39e5-164">101 \* 0,01 = 1,01</span><span class="sxs-lookup"><span data-stu-id="d39e5-164">101 \* 0.01 = 1.01</span></span>
        </li>
      </ol>
    </td>
  </tr>
    <tr>
    <td><span data-ttu-id="d39e5-165">round(1,011, 0,02) = 1,02</span><span class="sxs-lookup"><span data-stu-id="d39e5-165">round(1.011, 0.02) = 1.02</span></span>
    </td>
    <td> <ol>
        <li><span data-ttu-id="d39e5-166">round(1,011 / 0,02, 0) = round(50,55, 0) = 51</span><span class="sxs-lookup"><span data-stu-id="d39e5-166">round(1.011 / 0.02, 0) = round(50.55, 0) = 51</span></span>
        </li>
        <li><span data-ttu-id="d39e5-167">51 \* 0,02 = 1,02</span><span class="sxs-lookup"><span data-stu-id="d39e5-167">51 \* 0.02 = 1.02</span></span>
        </li>
      </ol>
    </td>
  </tr>
    <tr>
    <td><span data-ttu-id="d39e5-168">round(1,009, 0,02) = 1,00</span><span class="sxs-lookup"><span data-stu-id="d39e5-168">round(1.009, 0.02) = 1.00</span></span>
    </td>
    <td> <ol>
        <li><span data-ttu-id="d39e5-169">round(1,009 / 0,02, 0) = round(50,45, 0) = 50</span><span class="sxs-lookup"><span data-stu-id="d39e5-169">round(1.009 / 0.02, 0) = round(50.45, 0) = 50</span></span>
        </li>
        <li><span data-ttu-id="d39e5-170">50 \* 0,02 = 1,00</span><span class="sxs-lookup"><span data-stu-id="d39e5-170">50 \* 0.02 = 1.00</span></span>
        </li>
      </ol>
    </td>
  </tr>
</table>

> [!NOTE]                                                                                  
> <span data-ttu-id="d39e5-171">Se si seleziona A proprio vantaggio, l'arrotondamento è sempre a vantaggio della persona giuridica.</span><span class="sxs-lookup"><span data-stu-id="d39e5-171">If you select Own advantage, the rounding is always to the advantage of the legal entity.</span></span> 

<span data-ttu-id="d39e5-172">Per ulteriori informazioni, vedere i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="d39e5-172">For more information, see the following topics:</span></span>
- [<span data-ttu-id="d39e5-173">Panoramica dell'IVA</span><span class="sxs-lookup"><span data-stu-id="d39e5-173">Sales tax overview</span></span>](indirect-taxes-overview.md)
- [<span data-ttu-id="d39e5-174">Creare un pagamento IVA</span><span class="sxs-lookup"><span data-stu-id="d39e5-174">Create a sales tax payment</span></span>](tasks/create-sales-tax-payment.md)
- [<span data-ttu-id="d39e5-175">Creare transazioni IVA in documenti</span><span class="sxs-lookup"><span data-stu-id="d39e5-175">Create sales tax transactions on documents</span></span>](tasks/create-sales-tax-transactions-documents.md)
- [<span data-ttu-id="d39e5-176">Visualizzare transazioni IVA registrate</span><span class="sxs-lookup"><span data-stu-id="d39e5-176">View posted sales tax transactions</span></span>](tasks/view-posted-sales-tax-transactions.md)
- [<span data-ttu-id="d39e5-177">Funzione di arrotondamento</span><span class="sxs-lookup"><span data-stu-id="d39e5-177">round Function</span></span>](https://msdn.microsoft.com/library/aa850656.aspx)


