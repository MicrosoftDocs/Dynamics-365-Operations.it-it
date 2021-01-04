---
title: Risolvere problemi relativi a entrate prodotti e fatturazione
description: Questo argomento descrive come risolvere i problemi che potrebbero verificarsi mentre lavori con entrate prodotti e fatturazione.
author: SmithaNataraj
manager: tfehr
ms.date: 09/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable, PurchTablePart
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: smnatara
ms.search.validFrom: 2020-9-16
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: a89effb686d60dde9d11f99be51d4101897ad4ea
ms.sourcegitcommit: 827d77c638555396b32d36af5d22d1b61dafb0e8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "4431573"
---
# <a name="troubleshoot-product-receipts-and-invoicing"></a><span data-ttu-id="dde46-103">Risolvere problemi relativi a entrate prodotti e fatturazione</span><span class="sxs-lookup"><span data-stu-id="dde46-103">Troubleshoot product receipts and invoicing</span></span>

<span data-ttu-id="dde46-104">Questo argomento descrive come risolvere i problemi che potrebbero verificarsi mentre lavori con entrate prodotti e fatturazione.</span><span class="sxs-lookup"><span data-stu-id="dde46-104">This topic describes how to fix issues that you might encounter while you work with product receipts and invoicing.</span></span>

## <a name="i-cant-post-more-than-one-invoice-for-a-purchase-order-line-that-has-category-based-items"></a><span data-ttu-id="dde46-105">Non riesco a registrare più di una fattura per una riga di ordine fornitore con articoli basati sulla categoria.</span><span class="sxs-lookup"><span data-stu-id="dde46-105">I can't post more than one invoice for a purchase order line that has category-based items.</span></span>

<span data-ttu-id="dde46-106">Una quantità è obbligatoria se si desidera registrare le fatture.</span><span class="sxs-lookup"><span data-stu-id="dde46-106">A quantity is mandatory if you want to post invoices.</span></span> <span data-ttu-id="dde46-107">Pertanto, se l'intera quantità di una riga è stata fatturata solo per un importo parziale, non sarà possibile fatturare l'importo rimanente su un'altra fattura.</span><span class="sxs-lookup"><span data-stu-id="dde46-107">Therefore, if the full quantity of a line has been invoiced for only a partial amount, you won't be able to invoice the remaining amount on another invoice.</span></span>

## <a name="i-receive-an-object-reference-not-set-error-during-purchase-order-confirmation-or-an-exception-has-been-thrown-by-the-target-of-an-invocation-exception-occurs-during-vendor-invoice-posting"></a><span data-ttu-id="dde46-108">Ricevo un errore "Riferimento oggetto non impostato" durante la conferma dell'ordine fornitore o un'eccezione "È stata generata un'eccezione dalla destinazione di una chiamata" durante la registrazione della fattura fornitore.</span><span class="sxs-lookup"><span data-stu-id="dde46-108">I receive an "Object reference not set" error during purchase order confirmation, or an "Exception has been thrown by the target of an invocation" exception occurs during vendor invoice posting.</span></span>

<span data-ttu-id="dde46-109">Questo problema può verificarsi a causa di incoerenze nelle distribuzioni degli ordini fornitore.</span><span class="sxs-lookup"><span data-stu-id="dde46-109">This issue can occur because of inconsistency in purchase order distributions.</span></span>

<span data-ttu-id="dde46-110">Per sbloccare questo problema e reimpostare l'ordine fornitore su uno stato *Bozza*, vai a **Approvvigionamento \>Attività periodiche \> Pulisci \> Reimpostazione distribuzione ordine fornitore**.</span><span class="sxs-lookup"><span data-stu-id="dde46-110">To unblock this issue and reset the purchase order to a *Draft* state, go to **Procurement and sourcing \> Periodic tasks \> Clean up \> Purchase order distribution reset**.</span></span> <span data-ttu-id="dde46-111">Per ulteriori informazioni, vedi il seguente post del blog: [Risolvere gli errori di distribuzione dell'ordine fornitore in Dynamics 365 Supply Chain Management](https://cloudblogs.microsoft.com/dynamics365/it/2020/08/12/resolve-po-distribution-errors-in-dynamics-365-supply-chain-management/).</span><span class="sxs-lookup"><span data-stu-id="dde46-111">For more information, see the following blog post: [Resolve PO distribution errors in Dynamics 365 Supply Chain Management](https://cloudblogs.microsoft.com/dynamics365/it/2020/08/12/resolve-po-distribution-errors-in-dynamics-365-supply-chain-management/).</span></span>

## <a name="i-cant-consolidate-multiple-product-receipts-into-a-single-purchase-order"></a><span data-ttu-id="dde46-112">Non riesco a consolidare più entrate prodotto in un unico ordine fornitore.</span><span class="sxs-lookup"><span data-stu-id="dde46-112">I can't consolidate multiple product receipts into a single purchase order.</span></span>

<span data-ttu-id="dde46-113">Non è possibile consolidare più entrate prodotti in un unico ordine fornitore se le diverse righe di entrata prodotti hanno date contabili diverse.</span><span class="sxs-lookup"><span data-stu-id="dde46-113">You can't consolidate multiple product receipts into a single purchase order if the different product receipt lines have different accounting dates.</span></span>

<span data-ttu-id="dde46-114">Nelle versioni precedenti di Microsoft Dynamics 365 Supply Chain Management, il consolidamento era consentito in questa situazione.</span><span class="sxs-lookup"><span data-stu-id="dde46-114">In earlier versions of Microsoft Dynamics 365 Supply Chain Management, consolidation was allowed in this situation.</span></span> <span data-ttu-id="dde46-115">Tuttavia, la procedura è soggetta a errori.</span><span class="sxs-lookup"><span data-stu-id="dde46-115">However, the practice is prone to error.</span></span> <span data-ttu-id="dde46-116">La data contabile nelle righe ordine fornitore create non deve essere diversa dalla data contabile nelle righe entrata prodotti da cui sono state create tali righe ordine fornitore.</span><span class="sxs-lookup"><span data-stu-id="dde46-116">The accounting date on the purchase order lines that are created should not differ from the accounting date on the product receipt lines that those purchase order lines were created from.</span></span> <span data-ttu-id="dde46-117">(La data contabile nelle righe dell'ordine fornitore corrisponde alla data contabile nell'intestazione dell'ordine fornitore). Pertanto, il consolidamento di più entrate prodotti in un unico ordine fornitore non è più consentito.</span><span class="sxs-lookup"><span data-stu-id="dde46-117">(The accounting date on the purchase order lines matches the accounting date on the purchase order header.) Therefore, the consolidation of multiple product receipts into a single purchase orders is no longer allowed.</span></span>

<span data-ttu-id="dde46-118">La data contabile viene utilizzata, ad esempio, per le prenotazioni di budget e gli impegni di spesa.</span><span class="sxs-lookup"><span data-stu-id="dde46-118">The accounting date is used, for example, for budget reservations and encumbrance.</span></span> <span data-ttu-id="dde46-119">Pertanto, deve essere conservata durante il passaggio dall'entrata del prodotto all'ordine fornitore.</span><span class="sxs-lookup"><span data-stu-id="dde46-119">Therefore, it should be kept during the transition from product receipt to purchase order.</span></span>

## <a name="when-product-receipts-are-canceled-transactions-can-be-posted-to-a-suspended-ledger-account"></a><span data-ttu-id="dde46-120">Quando le entrate prodotti vengono annullate, le transazioni possono essere registrate in un conto CoGe sospeso.</span><span class="sxs-lookup"><span data-stu-id="dde46-120">When product receipts are canceled, transactions can be posted to a suspended ledger account.</span></span>

### <a name="issue-description"></a><span data-ttu-id="dde46-121">Descrizione del problema</span><span class="sxs-lookup"><span data-stu-id="dde46-121">Issue description</span></span>

<span data-ttu-id="dde46-122">Se un'entrata prodotti viene annullata, il sistema consente la registrazione delle transazioni nei conti CoGe sospesi, anche se i conti principali sono sospesi.</span><span class="sxs-lookup"><span data-stu-id="dde46-122">If a product receipt is canceled, the system allows transactions to be posted to suspended ledger accounts, even though the main accounts are suspended.</span></span>

### <a name="reproduce-the-issue"></a><span data-ttu-id="dde46-123">Riprodurre il problema</span><span class="sxs-lookup"><span data-stu-id="dde46-123">Reproduce the issue</span></span>

<span data-ttu-id="dde46-124">La seguente procedura mostra un modo per riprodurre il problema.</span><span class="sxs-lookup"><span data-stu-id="dde46-124">The following procedure shows one way to reproduce the issue.</span></span>

1. <span data-ttu-id="dde46-125">Nella pagina **Parametri contabilità fornitori**, nella scheda **Generale**, assicurati che l'opzione **Registra entrata prodotti nella contabilità generale** sia impostata su *Sì*.</span><span class="sxs-lookup"><span data-stu-id="dde46-125">On the **Accounts payable parameters** page, on the **General** tab, make sure that the **Post product receipt in ledger** option is set to *Yes*.</span></span>
1. <span data-ttu-id="dde46-126">Crea un ordine fornitore e aggiungi una riga ordine con una quantità di *1.000* per un prodotto.</span><span class="sxs-lookup"><span data-stu-id="dde46-126">Create a purchase order, and add an order line that has a quantity of *1,000* for a product.</span></span>
1. <span data-ttu-id="dde46-127">Conferma l'ordine fornitore.</span><span class="sxs-lookup"><span data-stu-id="dde46-127">Confirm the purchase order.</span></span>
1. <span data-ttu-id="dde46-128">Registra l'entrata del prodotto e controlla i giustificativi.</span><span class="sxs-lookup"><span data-stu-id="dde46-128">Post the product receipt, and check the vouchers.</span></span>
1. <span data-ttu-id="dde46-129">Sospendi i relativi conti principali, *200140* e *140200*.</span><span class="sxs-lookup"><span data-stu-id="dde46-129">Suspend the relevant main accounts, *200140* and *140200*.</span></span>
1. <span data-ttu-id="dde46-130">Annulla l'entrata del prodotto registrata.</span><span class="sxs-lookup"><span data-stu-id="dde46-130">Cancel the posted product receipt.</span></span>
1. <span data-ttu-id="dde46-131">Si noti che le transazioni possono essere registrate nei conti CoGe sospesi.</span><span class="sxs-lookup"><span data-stu-id="dde46-131">Notice that transactions can be posted to the suspended leger accounts.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="dde46-132">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="dde46-132">Issue resolution</span></span>

<span data-ttu-id="dde46-133">Le transazioni possono essere registrate nei conti CoGe sospesi quando le entrate prodotti vengono annullate, poiché questo comportamento consente registrazioni corrette.</span><span class="sxs-lookup"><span data-stu-id="dde46-133">Transactions can be posted to the suspended leger accounts when product receipts are canceled, because this behavior allows for correct postings.</span></span>

## <a name="a-product-receipt-voucher-number-is-consumed-even-if-no-financial-voucher-is-generated-during-product-receipt"></a><span data-ttu-id="dde46-134">Un numero di giustificativo di entrata prodotti viene utilizzato anche se non viene generato alcun giustificativo finanziario durante l'entrata prodotti.</span><span class="sxs-lookup"><span data-stu-id="dde46-134">A product receipt voucher number is consumed even if no financial voucher is generated during product receipt.</span></span>

<span data-ttu-id="dde46-135">Se l'opzione **Passività ratei all'entrata prodotti** è impostata su *No* per il gruppo di modelli di articoli, non verranno effettuate registrazioni nella contabilità generale.</span><span class="sxs-lookup"><span data-stu-id="dde46-135">If the **Accrue liability on product receipt** option is set to *No* for the item model group, no postings to the general ledger will occur.</span></span> <span data-ttu-id="dde46-136">Tuttavia, un evento fisico verrà registrato ai fini della contabilità in un giornale di registrazione secondario e tale evento richiede un numero di giustificativo.</span><span class="sxs-lookup"><span data-stu-id="dde46-136">However, a physical event will be recorded for the purpose of accounting in a subledger, and that event requires a voucher number.</span></span> <span data-ttu-id="dde46-137">Questo numero di giustificativo è il numero di giustificativo a cui si fa riferimento nelle transazioni di magazzino.</span><span class="sxs-lookup"><span data-stu-id="dde46-137">This voucher number is the voucher number that is referenced in the inventory transactions.</span></span>

<span data-ttu-id="dde46-138">Ti consigliamo di impostare l'opzione **Passività ratei all'entrata prodotti** su *Sì*, come descritto nel seguente post del blog: [Registrare le spese varie al momento dell'entrata del prodotto](https://cloudblogs.microsoft.com/dynamics365/no-audience/2014/11/11/post-misc-charges-at-time-of-product-receipt/).</span><span class="sxs-lookup"><span data-stu-id="dde46-138">We recommend that you set the **Accrue liability on product receipt** option to *Yes*, as described in the following blog post: [Post Misc. charges at time of product receipt](https://cloudblogs.microsoft.com/dynamics365/no-audience/2014/11/11/post-misc-charges-at-time-of-product-receipt/).</span></span>

## <a name="the-post-to-charge-account-in-ledger-setting-isnt-turned-on"></a><span data-ttu-id="dde46-139">L'impostazione Registra nel conto di addebito nella contabilità generale non è attivata.</span><span class="sxs-lookup"><span data-stu-id="dde46-139">The Post to charge account in ledger setting isn't turned on.</span></span>

### <a name="issue-description"></a><span data-ttu-id="dde46-140">Descrizione del problema</span><span class="sxs-lookup"><span data-stu-id="dde46-140">Issue description</span></span>

<span data-ttu-id="dde46-141">Questo problema si verifica quando viene fatturato un ordine fornitore, se l'opzione **Registra nel conto di addebito nella contabilità generale** è impostata su *Sì* nella scheda **Fattura** della pagina **Parametri contabilità fornitori**.</span><span class="sxs-lookup"><span data-stu-id="dde46-141">This issue occurs when a purchase order is invoiced, if the **Post to charge account in ledger** option is set to *Yes* on the **Invoice** tab of the **Accounts payable parameters** page.</span></span>

### <a name="reproduce-the-issue"></a><span data-ttu-id="dde46-142">Riprodurre il problema</span><span class="sxs-lookup"><span data-stu-id="dde46-142">Reproduce the issue</span></span>

<span data-ttu-id="dde46-143">La seguente procedura mostra un modo per riprodurre il problema.</span><span class="sxs-lookup"><span data-stu-id="dde46-143">The following procedure shows one way to reproduce the issue.</span></span>

1. <span data-ttu-id="dde46-144">Passare a **Contabilità fornitori \> Impostazioni \> Parametri contabilità fornitori**.</span><span class="sxs-lookup"><span data-stu-id="dde46-144">Go to **Accounts payable \> Setup \> Accounts payable parameters**.</span></span>
1. <span data-ttu-id="dde46-145">Nella scheda **Fattura**, imposta l'opzione **Registra nel conto di addebito nella contabilità generale** su *Sì*.</span><span class="sxs-lookup"><span data-stu-id="dde46-145">On the **Invoice** tab, set the **Post to charge account in ledger** option to *Yes*.</span></span>
1. <span data-ttu-id="dde46-146">Vai a **Gestione scorte \> Impostazione \> Registrazione \> Registrazione**.</span><span class="sxs-lookup"><span data-stu-id="dde46-146">Go to **Inventory management \> Setup \> Posting \> Posting**.</span></span>
1. <span data-ttu-id="dde46-147">Nella scheda **Ordine fornitore**, assicurati di aver eliminato tutte le righe nella spesa di acquisto del prodotto.</span><span class="sxs-lookup"><span data-stu-id="dde46-147">On the **Purchase order** tab, make sure that you've deleted all the lines in the purchase expenditure for the product.</span></span>
1. <span data-ttu-id="dde46-148">Vai a **Contabilità fornitori \> Ordini fornitore \> Tutti gli ordini fornitore**.</span><span class="sxs-lookup"><span data-stu-id="dde46-148">Go to **Accounts payable \> Purchase orders \> All purchase orders**.</span></span>
1. <span data-ttu-id="dde46-149">Creare un ordine fornitore.</span><span class="sxs-lookup"><span data-stu-id="dde46-149">Create a purchase order.</span></span> <span data-ttu-id="dde46-150">Nel campo **Conto fornitore**, seleziona *1001 Acme Office Supplies*.</span><span class="sxs-lookup"><span data-stu-id="dde46-150">In the **Vendor account** field, select *1001 Acme Office Supplies*.</span></span>
1. <span data-ttu-id="dde46-151">Aggiungi una riga ordine fornitore con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="dde46-151">Add a purchase order line that has the following settings:</span></span>

    - <span data-ttu-id="dde46-152">**Numero articolo:** *D0011 Laser Projector*</span><span class="sxs-lookup"><span data-stu-id="dde46-152">**Item number:** *D0011 Laser Projector*</span></span>
    - <span data-ttu-id="dde46-153">**Sito:** *1*</span><span class="sxs-lookup"><span data-stu-id="dde46-153">**Site:** *1*</span></span>
    - <span data-ttu-id="dde46-154">**Magazzino:** *11*</span><span class="sxs-lookup"><span data-stu-id="dde46-154">**Warehouse:** *11*</span></span>
    - <span data-ttu-id="dde46-155">**Quantità:** *4*</span><span class="sxs-lookup"><span data-stu-id="dde46-155">**Quantity:** *4*</span></span>

1. <span data-ttu-id="dde46-156">Nel riquadro azioni, nella scheda **Acquisto**, nel gruppo **Azione**, seleziona **Conferma**.</span><span class="sxs-lookup"><span data-stu-id="dde46-156">On the Action Pane, on the **Purchase** tab, in the **Action** group, select **Confirm**.</span></span>
1. <span data-ttu-id="dde46-157">Nel riquadro azioni, nella scheda **Ricevi**, nel gruppo **Genera**, seleziona **Entrata prodotto**.</span><span class="sxs-lookup"><span data-stu-id="dde46-157">On the Action Pane, on the **Receive** tab, in the **Generate** group, select **Product receipt**.</span></span>
1. <span data-ttu-id="dde46-158">Nella finestra di dialogo **Registrazione entrata prodotti**, nel campo **Entrata prodotti**, immetti un numero arbitrario, quindi seleziona **OK**.</span><span class="sxs-lookup"><span data-stu-id="dde46-158">In the **Posting product receipt** dialog box, in the **Product receipt** field, enter an arbitrary number, and then select **OK**.</span></span>
1. <span data-ttu-id="dde46-159">Nel riquadro azioni, nel gruppo **Genera** della scheda **Fattura**, seleziona **Fattura**.</span><span class="sxs-lookup"><span data-stu-id="dde46-159">On the Action Pane, on the **Invoice** tab, in the **Generate** group, select **Invoice**.</span></span>
1. <span data-ttu-id="dde46-160">Nel campo **Numero**, immetti un numero arbitrario come numero di fattura.</span><span class="sxs-lookup"><span data-stu-id="dde46-160">In the **Number** field, enter an arbitrary number as the invoice number.</span></span>
1. <span data-ttu-id="dde46-161">Aggiorna lo stato di abbinamento e registra.</span><span class="sxs-lookup"><span data-stu-id="dde46-161">Update the match status, and post.</span></span>
1. <span data-ttu-id="dde46-162">Si noti che ora viene visualizzato il seguente errore quando si genera una fattura da un ordine fornitore: "Numero di conto per il tipo di transazione spesa di acquisto per il prodotto inesistente".</span><span class="sxs-lookup"><span data-stu-id="dde46-162">Notice that you now receive the following error when you generate an invoice from a purchase order: "Account number for transaction type Purchase expenditure for product does not exist."</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="dde46-163">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="dde46-163">Issue resolution</span></span>

<span data-ttu-id="dde46-164">Ciò dipende dalle impostazioni dei parametri per le fatture e i gruppi di fatture.</span><span class="sxs-lookup"><span data-stu-id="dde46-164">This depends on the parameter settings for invoices and invoice groups.</span></span> <span data-ttu-id="dde46-165">Per ulteriori informazioni, vedi il seguente post del blog: [Contabilizzazione per spese di acquisto e variazione delle scorte](https://cloudblogs.microsoft.com/dynamics365/no-audience/2014/12/15/accounting-for-purchase-charge-and-stock-variation/).</span><span class="sxs-lookup"><span data-stu-id="dde46-165">For more information, see the following blog post: [Accounting for Purchase charge and Stock variation](https://cloudblogs.microsoft.com/dynamics365/no-audience/2014/12/15/accounting-for-purchase-charge-and-stock-variation/).</span></span>
