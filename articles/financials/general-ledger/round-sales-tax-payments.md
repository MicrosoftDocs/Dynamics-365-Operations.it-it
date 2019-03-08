---
title: Pagamenti IVA e regole di arrotondamento
description: Questo articolo illustra il funzionamento dell'impostazione della regola di arrotondamento in Uffici IVA e l'arrotondamento del saldo dell'IVA durante il processo Liquida e registra IVA.
author: ShylaThompson
manager: AnnBe
ms.date: 08/01/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxAuthority
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 6134
ms.assetid: 7dcd3cf5-ebdf-4a9f-806c-1296c7da0331
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f03336c834e74cd12d039c7b9692874843811746
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2019
ms.locfileid: "367848"
---
# <a name="sales-tax-payments-and-rounding-rules"></a><span data-ttu-id="88cc1-103">Pagamenti IVA e regole di arrotondamento</span><span class="sxs-lookup"><span data-stu-id="88cc1-103">Sales tax payments and rounding rules</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="88cc1-104">Questo articolo illustra il funzionamento dell'impostazione della regola di arrotondamento in Uffici IVA e l'arrotondamento del saldo dell'IVA durante il processo Liquida e registra IVA.</span><span class="sxs-lookup"><span data-stu-id="88cc1-104">This article explains how the rounding rule setup on the Sales tax authorities works and rounding the sales tax balance during the Settle and post sales tax job.</span></span>

<span data-ttu-id="88cc1-105">Periodicamente, l'IVA deve essere dichiarata e pagata agli uffici tributari.</span><span class="sxs-lookup"><span data-stu-id="88cc1-105">Periodically, sales tax needs to be reported and paid to tax authorities.</span></span> <span data-ttu-id="88cc1-106">Questa operazione può essere effettuata mediante l'esecuzione del processo di liquidazione e registrazione IVA nella pagina IVA.</span><span class="sxs-lookup"><span data-stu-id="88cc1-106">This can be done by running the settle and post sales tax process in the Sales tax page.</span></span> <span data-ttu-id="88cc1-107">L'IVA per un periodo verrà liquidata nei conti IVA e il saldo IVA verrà registrato nel conto di liquidazione IVA.</span><span class="sxs-lookup"><span data-stu-id="88cc1-107">Sales tax for a period will be settled against the sales tax accounts and the sales tax balance will be posted to the Sales tax settlement account.</span></span> <span data-ttu-id="88cc1-108">Il saldo IVA, registrato nel conto di liquidazione IVA, può essere arrotondato in base a quanto richiesto dagli uffici tributari impostando una regola di arrotondamento nella pagina IVA.</span><span class="sxs-lookup"><span data-stu-id="88cc1-108">The sales tax balance, which is posted on the Sales tax settlement account, can be rounded as required by tax authorities by setting up a rounding rule on the Sales tax page.</span></span> 

<span data-ttu-id="88cc1-109">La differenza di arrotondamento viene registrata nel conto di arrotondamento IVA selezionato nel campo Conti per transazioni automatiche nella contabilità generale.</span><span class="sxs-lookup"><span data-stu-id="88cc1-109">The rounding difference is posted to the Sales tax rounding account that is selected in the Accounts for automatic transactions field in the General ledger.</span></span>

<span data-ttu-id="88cc1-110">Nell'esempio seguente viene illustrato il funzionamento della regola di arrotondamento IVA.</span><span class="sxs-lookup"><span data-stu-id="88cc1-110">The below example illustrates how the rounding rule on Sales tax authority works.</span></span>

### <a name="example"></a><span data-ttu-id="88cc1-111">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="88cc1-111">Example:</span></span>

<span data-ttu-id="88cc1-112">L'IVA totale per un periodo mostra un saldo in avere di -98.765,43.</span><span class="sxs-lookup"><span data-stu-id="88cc1-112">The total sales tax for a period shows a credit balance of -98,765.43.</span></span> <span data-ttu-id="88cc1-113">La persona giuridica dispone più prelievo IVA superiore a quanto ha pagato.</span><span class="sxs-lookup"><span data-stu-id="88cc1-113">The legal entity collected more sales taxes than it paid.</span></span> <span data-ttu-id="88cc1-114">Di conseguenza, la persona giuridica deve denaro all'ufficio tributario.</span><span class="sxs-lookup"><span data-stu-id="88cc1-114">Therefore, the legal entity owes money to the tax authority.</span></span> 

<span data-ttu-id="88cc1-115">La persona giuridica desidera utilizzare un metodo che consenta di arrotondare il saldo all'unità più vicina.</span><span class="sxs-lookup"><span data-stu-id="88cc1-115">The legal entity wants to use a rounding method that rounds the balance to the nearest 1.00.</span></span> <span data-ttu-id="88cc1-116">L'utente responsabile della contabilità IVA esegue le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="88cc1-116">The user who is responsible for sales tax accounting performs the following steps.</span></span>

1.  <span data-ttu-id="88cc1-117">Fare clic su Imposta &gt; Imposte indirette &gt; IVA &gt; Uffici IVA.</span><span class="sxs-lookup"><span data-stu-id="88cc1-117">Click Tax &gt; Indirect taxes &gt; Sales tax &gt; Sales tax authorities</span></span>
2.  <span data-ttu-id="88cc1-118">Nella scheda dettaglio Generale selezionare Normale nel campo Tipo di arrotondamento.</span><span class="sxs-lookup"><span data-stu-id="88cc1-118">On the General FastTab, select Normal in the Rounding form field.</span></span>
3.  <span data-ttu-id="88cc1-119">Nel campo Arrotondamento immettere 1.</span><span class="sxs-lookup"><span data-stu-id="88cc1-119">In the Round-off field, enter 1.00.</span></span>
4.  <span data-ttu-id="88cc1-120">Al momento del pagamento dell'IVA all'ufficio tributario, aprire la pagina Liquida e registra IVA.</span><span class="sxs-lookup"><span data-stu-id="88cc1-120">When it is time to pay the sales taxes to the tax authority, open the Settle and post sales tax page.</span></span> <span data-ttu-id="88cc1-121">Fare clic su Imposta &gt; Dichiarazioni &gt; IVA &gt; Liquida e registra IVA.</span><span class="sxs-lookup"><span data-stu-id="88cc1-121">(Click Tax &gt; Declarations &gt; Sales tax &gt; Settle and post sales tax.)</span></span>
5.  <span data-ttu-id="88cc1-122">Nel conti di liquidazione IVA l'importo di soggettività tributaria di 98.765,43 viene arrotondato a 98.765.</span><span class="sxs-lookup"><span data-stu-id="88cc1-122">On the sales tax settlement account, the tax liability amount of 98,765.43 is rounded to 98,765.</span></span>

<span data-ttu-id="88cc1-123">Le seguente tabella mostra un importo di 98.765,43 arrotondato utilizzando ogni metodo di arrotondamento disponibile nel campo Tipo di arrotondamento del modulo Uffici IVA.</span><span class="sxs-lookup"><span data-stu-id="88cc1-123">The following table shows how an amount of 98,765.43 is rounded by using each rounding method that is available in the Rounding form field in the Sales tax authorities page.</span></span>

| <span data-ttu-id="88cc1-124">Opzione Tipo di arrotondamento</span><span class="sxs-lookup"><span data-stu-id="88cc1-124">Rounding form option</span></span>                | <span data-ttu-id="88cc1-125">Valore arrotondamento = 0,01</span><span class="sxs-lookup"><span data-stu-id="88cc1-125">Round-off value = 0.01</span></span> | <span data-ttu-id="88cc1-126">Valore arrotondamento = 0,10</span><span class="sxs-lookup"><span data-stu-id="88cc1-126">Round-off value = 0.10</span></span> | <span data-ttu-id="88cc1-127">Valore arrotondamento = 1,00</span><span class="sxs-lookup"><span data-stu-id="88cc1-127">Round-off value = 1.00</span></span> | <span data-ttu-id="88cc1-128">Valore arrotondamento = 100,00</span><span class="sxs-lookup"><span data-stu-id="88cc1-128">Round-off value = 100.00</span></span> |
|-------------------------------------|------------------------|------------------------|------------------------|--------------------------|
| <span data-ttu-id="88cc1-129">Normale</span><span class="sxs-lookup"><span data-stu-id="88cc1-129">Normal</span></span>                              | <span data-ttu-id="88cc1-130">98.765,43</span><span class="sxs-lookup"><span data-stu-id="88cc1-130">98,765.43</span></span>              | <span data-ttu-id="88cc1-131">98.765,40</span><span class="sxs-lookup"><span data-stu-id="88cc1-131">98,765.40</span></span>              | <span data-ttu-id="88cc1-132">98.765,00</span><span class="sxs-lookup"><span data-stu-id="88cc1-132">98,765.00</span></span>              | <span data-ttu-id="88cc1-133">98.800,00</span><span class="sxs-lookup"><span data-stu-id="88cc1-133">98,800.00</span></span>                |
| <span data-ttu-id="88cc1-134">Arrotondamento per difetto</span><span class="sxs-lookup"><span data-stu-id="88cc1-134">Downward</span></span>                            | <span data-ttu-id="88cc1-135">98.765,43</span><span class="sxs-lookup"><span data-stu-id="88cc1-135">98,765.43</span></span>              | <span data-ttu-id="88cc1-136">98.765,40</span><span class="sxs-lookup"><span data-stu-id="88cc1-136">98,765.40</span></span>              | <span data-ttu-id="88cc1-137">98.765,00</span><span class="sxs-lookup"><span data-stu-id="88cc1-137">98,765.00</span></span>              | <span data-ttu-id="88cc1-138">98.700,00</span><span class="sxs-lookup"><span data-stu-id="88cc1-138">98,700.00</span></span>                |
| <span data-ttu-id="88cc1-139">Arrotondamento per eccesso</span><span class="sxs-lookup"><span data-stu-id="88cc1-139">Rounding-up</span></span>                         | <span data-ttu-id="88cc1-140">98.765,43</span><span class="sxs-lookup"><span data-stu-id="88cc1-140">98,765.43</span></span>              | <span data-ttu-id="88cc1-141">98.765,50</span><span class="sxs-lookup"><span data-stu-id="88cc1-141">98,765.50</span></span>              | <span data-ttu-id="88cc1-142">98.766,00</span><span class="sxs-lookup"><span data-stu-id="88cc1-142">98,766.00</span></span>              | <span data-ttu-id="88cc1-143">98.800,00</span><span class="sxs-lookup"><span data-stu-id="88cc1-143">98,800.00</span></span>                |
| <span data-ttu-id="88cc1-144">A proprio vantaggio, per un saldo in avere</span><span class="sxs-lookup"><span data-stu-id="88cc1-144">Own advantage, for a credit balance</span></span> | <span data-ttu-id="88cc1-145">98.765,43</span><span class="sxs-lookup"><span data-stu-id="88cc1-145">98,765.43</span></span>              | <span data-ttu-id="88cc1-146">98.765,40</span><span class="sxs-lookup"><span data-stu-id="88cc1-146">98,765.40</span></span>              | <span data-ttu-id="88cc1-147">98.765,00</span><span class="sxs-lookup"><span data-stu-id="88cc1-147">98,765.00</span></span>              | <span data-ttu-id="88cc1-148">98.700,00</span><span class="sxs-lookup"><span data-stu-id="88cc1-148">98,700.00</span></span>                |
| <span data-ttu-id="88cc1-149">A proprio vantaggio, per un saldo in dare</span><span class="sxs-lookup"><span data-stu-id="88cc1-149">Own advantage, for a debit balance</span></span>  | <span data-ttu-id="88cc1-150">98.765,43</span><span class="sxs-lookup"><span data-stu-id="88cc1-150">98,765.43</span></span>              | <span data-ttu-id="88cc1-151">98.765,50</span><span class="sxs-lookup"><span data-stu-id="88cc1-151">98,765.50</span></span>              | <span data-ttu-id="88cc1-152">98.766,00</span><span class="sxs-lookup"><span data-stu-id="88cc1-152">98,766.00</span></span>              | <span data-ttu-id="88cc1-153">98.800,00</span><span class="sxs-lookup"><span data-stu-id="88cc1-153">98,800.00</span></span>                |

> [!NOTE]                                                                                  
> <span data-ttu-id="88cc1-154">Se si seleziona A proprio vantaggio, l'arrotondamento è sempre a vantaggio della persona giuridica.</span><span class="sxs-lookup"><span data-stu-id="88cc1-154">If you select Own advantage, the rounding is always to the advantage of the legal entity.</span></span> 

<span data-ttu-id="88cc1-155">Per ulteriori informazioni, vedere i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="88cc1-155">For more information, see the following topics:</span></span>
- [<span data-ttu-id="88cc1-156">Panoramica dell'IVA</span><span class="sxs-lookup"><span data-stu-id="88cc1-156">Sales tax overview</span></span>](indirect-taxes-overview.md)
- [<span data-ttu-id="88cc1-157">Creare un pagamento IVA</span><span class="sxs-lookup"><span data-stu-id="88cc1-157">Create a sales tax payment</span></span>](tasks/create-sales-tax-payment.md)
- [<span data-ttu-id="88cc1-158">Creare transazioni IVA su documenti</span><span class="sxs-lookup"><span data-stu-id="88cc1-158">Create sales transactions on documents</span></span>](tasks/create-sales-tax-transactions-documents.md)
- [<span data-ttu-id="88cc1-159">Visualizzare transazioni IVA registrate</span><span class="sxs-lookup"><span data-stu-id="88cc1-159">View posted sales tax transactions</span></span>](tasks/view-posted-sales-tax-transactions.md)


