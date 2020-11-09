---
title: Risolvere i problemi relativi agli ordini fornitore
description: Questo argomento descrive come risolvere i problemi che potresti riscontrare mentre lavori con gli ordini fornitore.
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
ms.openlocfilehash: 234458f865e37a2d962aee8ab218b9521847081d
ms.sourcegitcommit: e3f4dd2257a3255c2982f4fc7b72a1121275b88a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "4018562"
---
# <a name="troubleshoot-purchase-orders"></a><span data-ttu-id="1d195-103">Risolvere i problemi relativi agli ordini fornitore</span><span class="sxs-lookup"><span data-stu-id="1d195-103">Troubleshoot purchase orders</span></span>

<span data-ttu-id="1d195-104">Questo argomento descrive come risolvere i problemi che potresti riscontrare mentre lavori con gli ordini fornitore.</span><span class="sxs-lookup"><span data-stu-id="1d195-104">This topic describes how to fix issues that you might encounter while you work with purchase orders.</span></span>

## <a name="an-action-can-be-completed-only-after-the-line-number-is-fully-distributed"></a><span data-ttu-id="1d195-105">Un'azione può essere completata solo dopo che il numero di riga è stato completamente distribuito.</span><span class="sxs-lookup"><span data-stu-id="1d195-105">An action can be completed only after the line number is fully distributed.</span></span>

<span data-ttu-id="1d195-106">Questo problema può verificarsi a causa di incoerenze nelle distribuzioni degli ordini fornitore.</span><span class="sxs-lookup"><span data-stu-id="1d195-106">This issue can occur because of inconsistency in purchase order distributions.</span></span>

<span data-ttu-id="1d195-107">Per sbloccare questo problema e reimpostare l'ordine fornitore su uno stato *Bozza* , vai a **Approvvigionamento \>Attività periodiche \> Pulisci \> Reimpostazione distribuzione ordine fornitore**.</span><span class="sxs-lookup"><span data-stu-id="1d195-107">To unblock this issue and reset the purchase order to a *Draft* state, go to **Procurement and sourcing \> Periodic tasks \> Clean up \> Purchase order distribution reset**.</span></span> <span data-ttu-id="1d195-108">Per ulteriori informazioni, vedi il seguente post del blog: [Risolvere gli errori di distribuzione dell'ordine fornitore in Dynamics 365 Supply Chain Management](https://cloudblogs.microsoft.com/dynamics365/it/2020/08/12/resolve-po-distribution-errors-in-dynamics-365-supply-chain-management/).</span><span class="sxs-lookup"><span data-stu-id="1d195-108">For more information, see the following blog post: [Resolve PO distribution errors in Dynamics 365 Supply Chain Management](https://cloudblogs.microsoft.com/dynamics365/it/2020/08/12/resolve-po-distribution-errors-in-dynamics-365-supply-chain-management/).</span></span>

## <a name="when-purchase-orders-are-imported-through-data-management-purchase-order-line-numbers-dont-follow-the-increment-that-defined-in-system-parameters"></a><span data-ttu-id="1d195-109">Quando gli ordini fornitore vengono importati tramite la gestione dei dati, i numeri di riga dell'ordine fornitore non seguono l'incremento definito nei parametri di sistema.</span><span class="sxs-lookup"><span data-stu-id="1d195-109">When purchase orders are imported through data management, purchase order line numbers don't follow the increment that defined in system parameters.</span></span>

### <a name="issue-description"></a><span data-ttu-id="1d195-110">Descrizione del problema</span><span class="sxs-lookup"><span data-stu-id="1d195-110">Issue description</span></span>

<span data-ttu-id="1d195-111">Per impostazione predefinita, i numeri di riga generati automaticamente per le righe ordine fornitore importate tramite l'entità di dati *Righe ordine fornitore V2* non utilizza l'incremento del numero di riga di sistema specificato nei parametri di sistema.</span><span class="sxs-lookup"><span data-stu-id="1d195-111">By default, automatically generated line numbers for purchase order lines that are imported through the *Purchase order lines V2* data entity don't use the system line number increment that is specified in system parameters.</span></span> <span data-ttu-id="1d195-112">Se crei manualmente un ordine fornitore e aggiungi righe tramite l'interfaccia utente (UI), i numeri di riga vengono incrementati correttamente.</span><span class="sxs-lookup"><span data-stu-id="1d195-112">If you manually create a purchase order and add lines through the user interface (UI), the line numbers are incremented correctly.</span></span> <span data-ttu-id="1d195-113">Tuttavia, se utilizzi Data Management Framework (DMF), non vengono incrementati correttamente.</span><span class="sxs-lookup"><span data-stu-id="1d195-113">However, if you use the Data management framework (DMF), they aren't incremented correctly.</span></span>

<span data-ttu-id="1d195-114">Questo problema si verifica perché, quando si importano righe tramite DMF, se i numeri di riga non sono già assegnati nell'entità importata, il sistema utilizza il metodo DMF per assegnarli.</span><span class="sxs-lookup"><span data-stu-id="1d195-114">This issue occurs because, when you import lines via DMF, if line numbers aren't already assigned in the imported entity, the system uses DMF's method for assigning them.</span></span> <span data-ttu-id="1d195-115">Questo metodo incrementa sempre i numeri di riga di uno.</span><span class="sxs-lookup"><span data-stu-id="1d195-115">That method always increments line numbers by one.</span></span>

### <a name="issue-workaround"></a><span data-ttu-id="1d195-116">Soluzione del problema</span><span class="sxs-lookup"><span data-stu-id="1d195-116">Issue workaround</span></span>

<span data-ttu-id="1d195-117">Accertarsi che i numeri di riga desiderati siano già specificati nei campi del numero di riga dell'entità di dati quando si importano le righe dell'ordine fornitore.</span><span class="sxs-lookup"><span data-stu-id="1d195-117">Make sure that the desired line numbers are already given in the data entity line number fields when you import the purchase order lines.</span></span> <span data-ttu-id="1d195-118">In questo caso, DMF non sovrascriverà i numeri di riga.</span><span class="sxs-lookup"><span data-stu-id="1d195-118">In this case, DMF won't overwrite the line numbers.</span></span>

## <a name="a-default-tax-group-and-a-default-cash-discount-arent-filled-in-from-the-invoice-account"></a><span data-ttu-id="1d195-119">Un gruppo fiscale predefinito e uno sconto di cassa predefinito non vengono compilati dal conto fattura.</span><span class="sxs-lookup"><span data-stu-id="1d195-119">A default tax group and a default cash discount aren't filled in from the invoice account.</span></span>

<span data-ttu-id="1d195-120">Se utilizzi un conto fattura diverso dal conto cliente, un gruppo fiscale predefinito e uno sconto di cassa predefinito non vengono compilati dal conto fattura quando viene creato un ordine fornitore.</span><span class="sxs-lookup"><span data-stu-id="1d195-120">If you're using an invoice account that differs from the customer account, a default tax group and a default cash discount aren't filled in from the invoice account when a purchase order is created.</span></span>

<span data-ttu-id="1d195-121">Questo comportamento è predefinito.</span><span class="sxs-lookup"><span data-stu-id="1d195-121">This behavior is by design.</span></span> <span data-ttu-id="1d195-122">I valori predefiniti per il gruppo IVA, sconti di cassa e altre informazioni sui prezzi si basano sul conto cliente, non sul conto fattura.</span><span class="sxs-lookup"><span data-stu-id="1d195-122">The default values for the tax group, cash discounts, and other price information are based on the customer account, not the invoice account.</span></span>

## <a name="i-receive-an-object-reference-not-set-error-during-purchase-order-confirmation-or-an-exception-has-been-thrown-by-the-target-of-an-invocation-exception-occurs-during-vendor-invoice-posting"></a><span data-ttu-id="1d195-123">Ricevo un errore "Riferimento oggetto non impostato" durante la conferma dell'ordine fornitore o un'eccezione "È stata generata un'eccezione dalla destinazione di una chiamata" durante la registrazione della fattura fornitore.</span><span class="sxs-lookup"><span data-stu-id="1d195-123">I receive an "Object reference not set" error during purchase order confirmation, or an "Exception has been thrown by the target of an invocation" exception occurs during vendor invoice posting.</span></span>

<span data-ttu-id="1d195-124">Questo problema può verificarsi a causa di incoerenze nelle distribuzioni degli ordini fornitore.</span><span class="sxs-lookup"><span data-stu-id="1d195-124">This issue can occur because of inconsistency in purchase order distributions.</span></span>

<span data-ttu-id="1d195-125">Per sbloccare questo problema e reimpostare l'ordine fornitore su uno stato *Bozza* , vai a **Approvvigionamento \>Attività periodiche \> Pulisci \> Reimpostazione distribuzione ordine fornitore**.</span><span class="sxs-lookup"><span data-stu-id="1d195-125">To unblock this issue and reset the purchase order to a *Draft* state, go to **Procurement and sourcing \> Periodic tasks \> Clean up \> Purchase order distribution reset**.</span></span> <span data-ttu-id="1d195-126">Per ulteriori informazioni, vedi il seguente post del blog: [Risolvere gli errori di distribuzione dell'ordine fornitore in Dynamics 365 Supply Chain Management](https://cloudblogs.microsoft.com/dynamics365/it/2020/08/12/resolve-po-distribution-errors-in-dynamics-365-supply-chain-management/).</span><span class="sxs-lookup"><span data-stu-id="1d195-126">For more information, see the following blog post: [Resolve PO distribution errors in Dynamics 365 Supply Chain Management](https://cloudblogs.microsoft.com/dynamics365/it/2020/08/12/resolve-po-distribution-errors-in-dynamics-365-supply-chain-management/).</span></span>

## <a name="one-or-more-accounting-distributions-are-either-over-distributed-or-under-distributed"></a><span data-ttu-id="1d195-127">Una o più distribuzioni contabili è distribuita eccessivamente o sottodistribuita.</span><span class="sxs-lookup"><span data-stu-id="1d195-127">One or more accounting distributions are either over-distributed or under-distributed.</span></span>

### <a name="issue-description"></a><span data-ttu-id="1d195-128">Descrizione del problema</span><span class="sxs-lookup"><span data-stu-id="1d195-128">Issue description</span></span>

<span data-ttu-id="1d195-129">Viene visualizzato il seguente errore: "Una o più distribuzioni contabili è distribuita eccessivamente o sottodistribuita".</span><span class="sxs-lookup"><span data-stu-id="1d195-129">You receive the following error: "One or more accounting distributions is either over-distributed or under-distributed."</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="1d195-130">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="1d195-130">Issue resolution</span></span>

<span data-ttu-id="1d195-131">Questo problema può verificarsi a causa di incoerenze nelle distribuzioni degli ordini fornitore.</span><span class="sxs-lookup"><span data-stu-id="1d195-131">This issue can occur because of inconsistency in purchase order distributions.</span></span>

<span data-ttu-id="1d195-132">Per sbloccare questo problema e reimpostare l'ordine fornitore su uno stato *Bozza* , vai a **Approvvigionamento \>Attività periodiche \> Pulisci \> Reimpostazione distribuzione ordine fornitore**.</span><span class="sxs-lookup"><span data-stu-id="1d195-132">To unblock this issue and reset the purchase order to a *Draft* state, go to **Procurement and sourcing \> Periodic tasks \> Clean up \> Purchase order distribution reset**.</span></span> <span data-ttu-id="1d195-133">Per ulteriori informazioni, vedi il seguente post del blog: [Risolvere gli errori di distribuzione dell'ordine fornitore in Dynamics 365 Supply Chain Management](https://cloudblogs.microsoft.com/dynamics365/it/2020/08/12/resolve-po-distribution-errors-in-dynamics-365-supply-chain-management/).</span><span class="sxs-lookup"><span data-stu-id="1d195-133">For more information, see the following blog post: [Resolve PO distribution errors in Dynamics 365 Supply Chain Management](https://cloudblogs.microsoft.com/dynamics365/it/2020/08/12/resolve-po-distribution-errors-in-dynamics-365-supply-chain-management/).</span></span>

## <a name="can-i-show-only-purchase-orders-that-i-created"></a><span data-ttu-id="1d195-134">Posso mostrare solo gli ordini fornitore che ho creato?</span><span class="sxs-lookup"><span data-stu-id="1d195-134">Can I show only purchase orders that I created?</span></span>

<span data-ttu-id="1d195-135">Questa funzionalità non è attualmente disponibile.</span><span class="sxs-lookup"><span data-stu-id="1d195-135">This functionality isn't currently available.</span></span>

## <a name="can-i-reserve-inventory-and-create-transactions-against-registered-inventory-on-a-purchase-order"></a><span data-ttu-id="1d195-136">Posso prenotare scorte e creare transazioni a partire dall'inventario registrato in un ordine fornitore?</span><span class="sxs-lookup"><span data-stu-id="1d195-136">Can I reserve inventory and create transactions against registered inventory on a purchase order?</span></span>

### <a name="issue-description"></a><span data-ttu-id="1d195-137">Descrizione del problema</span><span class="sxs-lookup"><span data-stu-id="1d195-137">Issue description</span></span>

<span data-ttu-id="1d195-138">Anche quando gli articoli sono in uno stato *Registrato* su un ordine fornitore, è comunque possibile prenotare scorte.</span><span class="sxs-lookup"><span data-stu-id="1d195-138">Even when items are in a *Registered* state on a purchase order, you can still reserve the inventory.</span></span> <span data-ttu-id="1d195-139">In altre parole, puoi creare transazioni a fronte dell'inventario registrato.</span><span class="sxs-lookup"><span data-stu-id="1d195-139">In other words, you can create transactions against the registered inventory.</span></span>

### <a name="reproduce-the-issue"></a><span data-ttu-id="1d195-140">Riprodurre il problema</span><span class="sxs-lookup"><span data-stu-id="1d195-140">Reproduce the issue</span></span>

<span data-ttu-id="1d195-141">La seguente procedura mostra un modo per riprodurre il problema.</span><span class="sxs-lookup"><span data-stu-id="1d195-141">The following procedure shows one way to reproduce the issue.</span></span>

1. <span data-ttu-id="1d195-142">Creare un ordine fornitore.</span><span class="sxs-lookup"><span data-stu-id="1d195-142">Create a purchase order.</span></span>
2. <span data-ttu-id="1d195-143">Registra la riga relativa all'ordine fornitore.</span><span class="sxs-lookup"><span data-stu-id="1d195-143">Register the purchase order line.</span></span>
3. <span data-ttu-id="1d195-144">Tieni presente che puoi generare prenotazioni o transazioni a fronte dell'inventario registrato.</span><span class="sxs-lookup"><span data-stu-id="1d195-144">Notice that you can generate reservations or transactions against the registered inventory.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="1d195-145">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="1d195-145">Issue resolution</span></span>

<span data-ttu-id="1d195-146">Questo comportamento è predefinito.</span><span class="sxs-lookup"><span data-stu-id="1d195-146">This behavior is by design.</span></span> <span data-ttu-id="1d195-147">L'aspettativa è che gli articoli registrati siano fisicamente arrivati nel magazzino o nell'inventario e che siano quindi disponibili per la prenotazione.</span><span class="sxs-lookup"><span data-stu-id="1d195-147">The expectation is that the registered items have physically arrived in the warehouse or inventory, and that they are therefore available for reservation.</span></span>

## <a name="purchase-orders-dont-reflect-the-language-settings-of-the-legal-entity"></a><span data-ttu-id="1d195-148">Gli ordini fornitore non riflettono le impostazioni della lingua della persona giuridica.</span><span class="sxs-lookup"><span data-stu-id="1d195-148">Purchase orders don't reflect the language settings of the legal entity.</span></span>

### <a name="issue-description"></a><span data-ttu-id="1d195-149">Descrizione del problema</span><span class="sxs-lookup"><span data-stu-id="1d195-149">Issue description</span></span>

<span data-ttu-id="1d195-150">Il nome del prodotto in un ordine fornitore viene visualizzato nella lingua del sistema anziché nella lingua impostata per la persona giuridica in cui è stato creato l'ordine fornitore.</span><span class="sxs-lookup"><span data-stu-id="1d195-150">The product name on a purchase order is shown in the system language instead of the language that is set for the legal entity where the purchase order was created.</span></span>

### <a name="reproduce-the-issue"></a><span data-ttu-id="1d195-151">Riprodurre il problema</span><span class="sxs-lookup"><span data-stu-id="1d195-151">Reproduce the issue</span></span>

<span data-ttu-id="1d195-152">La seguente procedura mostra un modo per riprodurre il problema.</span><span class="sxs-lookup"><span data-stu-id="1d195-152">The following procedure shows one way to reproduce the issue.</span></span>

1. <span data-ttu-id="1d195-153">Imposta la lingua del sistema su *EN-US* (Inglese americano).</span><span class="sxs-lookup"><span data-stu-id="1d195-153">Set the system language to *EN-US* (US English).</span></span>
1. <span data-ttu-id="1d195-154">Assicurati che ci sia un prodotto in cui le lingue *EN-US* e *DE* (tedesco) vengono mantenute per le traduzioni del nome del prodotto.</span><span class="sxs-lookup"><span data-stu-id="1d195-154">Make sure that there is a product where the *EN-US* and *DE* (German) languages are maintained for translations of the product name.</span></span>
1. <span data-ttu-id="1d195-155">Cambia la lingua di una persona giuridica in *DE*.</span><span class="sxs-lookup"><span data-stu-id="1d195-155">Change the language of a legal entity to *DE*.</span></span>
1. <span data-ttu-id="1d195-156">Nella persona giuridica dove *DE* è impostata come lingua, crea un ordine fornitore che includa il prodotto.</span><span class="sxs-lookup"><span data-stu-id="1d195-156">In the legal entity where *DE* is set as the language, create a purchase order that includes the product.</span></span>
1. <span data-ttu-id="1d195-157">Si noti che il nome del prodotto è ancora visualizzato in inglese americano (la lingua del sistema).</span><span class="sxs-lookup"><span data-stu-id="1d195-157">Notice that the product name is still shown in US English (the system language).</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="1d195-158">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="1d195-158">Issue resolution</span></span>

<span data-ttu-id="1d195-159">Questo comportamento è predefinito.</span><span class="sxs-lookup"><span data-stu-id="1d195-159">This behavior is by design.</span></span> <span data-ttu-id="1d195-160">Negli ordini fornitore, il prodotto viene sempre mostrato nella lingua del sistema.</span><span class="sxs-lookup"><span data-stu-id="1d195-160">On purchase orders, the product is always shown in the system language.</span></span> <span data-ttu-id="1d195-161">La lingua dell'ordine fornitore viene utilizzata quando viene creato un giornale di registrazione conferme.</span><span class="sxs-lookup"><span data-stu-id="1d195-161">The purchase order language is used when a confirmation journal is created.</span></span>

## <a name="the-approved-vendor-list-by-product-entity-doesnt-allow-the-effective-date-to-be-changed"></a><span data-ttu-id="1d195-162">L'elenco dei fornitori approvati per entità prodotto non consente la modifica della data di validità.</span><span class="sxs-lookup"><span data-stu-id="1d195-162">The Approved vendor list by product entity doesn't allow the effective date to be changed.</span></span>

### <a name="issue-description"></a><span data-ttu-id="1d195-163">Descrizione del problema</span><span class="sxs-lookup"><span data-stu-id="1d195-163">Issue description</span></span>

<span data-ttu-id="1d195-164">Un prodotto ha un fornitore approvato che ha, ad esempio, una data di validità dell'11 gennaio 2018 ( *11/01/2018* ) e una data di scadenza di *Mai*.</span><span class="sxs-lookup"><span data-stu-id="1d195-164">A product has an approved vendor that has, for example, an effective date of January 11, 2018 ( *01/11/2018* ), and an expiration date of *Never*.</span></span> <span data-ttu-id="1d195-165">Se provi a modificare la data di validità al 10 gennaio 2018 ( *10/01/2018* ) o il 12 gennaio 2018 ( *12/01/2018* ), viene visualizzato il seguente errore:</span><span class="sxs-lookup"><span data-stu-id="1d195-165">If you try to change the effective date to January 10, 2018 ( *01/10/2018* ), or January 12, 2018 ( *01/12/2018* ), you receive the following error:</span></span>

> <span data-ttu-id="1d195-166">Impossibile creare un record nell'elenco dei fornitori approvati (PdsApproveVendorList).</span><span class="sxs-lookup"><span data-stu-id="1d195-166">Cannot create a record in Approved supplier list (PdsApproveVendorList).</span></span> <span data-ttu-id="1d195-167">Il valore "Scadenza" deve essere maggiore o uguale al valore "Validità".</span><span class="sxs-lookup"><span data-stu-id="1d195-167">The 'Expiration' value needs to be greater than or equal to the 'Effective' value.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="1d195-168">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="1d195-168">Issue resolution</span></span>

<span data-ttu-id="1d195-169">È possibile estendere solo il periodo per il quale il fornitore è approvato.</span><span class="sxs-lookup"><span data-stu-id="1d195-169">You can only extend the period that the vendor is approved for.</span></span> <span data-ttu-id="1d195-170">Vengono applicate le seguenti regole:</span><span class="sxs-lookup"><span data-stu-id="1d195-170">The following rules apply:</span></span>

- <span data-ttu-id="1d195-171">Per modificare la data di validità in modo che sia precedente a qualsiasi record (periodo) esistente per il fornitore dell'articolo, la data di scadenza del nuovo periodo deve essere precedente a tutte le date di scadenza nei record esistenti.</span><span class="sxs-lookup"><span data-stu-id="1d195-171">To change the effective date so that it's earlier than any of the existing records (periods) for the item vendor, the expiration date of the new period must be before all the expiration dates in the existing records.</span></span>
- <span data-ttu-id="1d195-172">Per modificare la data di scadenza in modo che sia successiva a uno qualsiasi dei periodi esistenti, la data di validità deve essere successiva all'ultima data di scadenza in qualsiasi record esistente.</span><span class="sxs-lookup"><span data-stu-id="1d195-172">To change the expiration date so that it's later than any of the existing periods, the effective date must be after the latest expiration date in any existing record.</span></span>
- <span data-ttu-id="1d195-173">Per ridurre il periodo complessivo per il quale il fornitore è approvato, è necessario eliminare o modificare i record esistenti.</span><span class="sxs-lookup"><span data-stu-id="1d195-173">To reduce the overall period that the vendor is approved for, you must delete or modify existing records.</span></span> <span data-ttu-id="1d195-174">In alternativa, puoi utilizzare l'interruttore **Tronca** durante l'importazione.</span><span class="sxs-lookup"><span data-stu-id="1d195-174">Alternatively, you can use the **truncate** switch during import.</span></span> <span data-ttu-id="1d195-175">Questa opzione elimina tutti i record esistenti nella tabella per i fornitori approvati per articolo.</span><span class="sxs-lookup"><span data-stu-id="1d195-175">This switch deletes all existing records in the table for approved vendors by item.</span></span>

<span data-ttu-id="1d195-176">Per lo scenario di esempio descritto nella descrizione del problema, in cui un record ha una data di validità di *11/01/2018* e una data di scadenza di *Mai* , puoi importare un nuovo record con data di validità *10/01/2018* e una data di scadenza di *Mai*.</span><span class="sxs-lookup"><span data-stu-id="1d195-176">For the example scenario that is described in the issue description, where a record has an effective date of *01/11/2018* and an expiration date of *Never* , you can import a new record that has an effective date of *01/10/2018* and an expiration date of *Never*.</span></span> <span data-ttu-id="1d195-177">Tuttavia, non è possibile ridurre il periodo in modo che la data di validità venga aggiornata a *12/01/2018* tramite la gestione dei dati.</span><span class="sxs-lookup"><span data-stu-id="1d195-177">However, you can't reduce the period so that the effective date is updated to *01/12/2018* via data management.</span></span> <span data-ttu-id="1d195-178">È necessario apportare questa modifica tramite l'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="1d195-178">You must make this change through the UI.</span></span>

## <a name="after-i-change-the-delivery-address-on-a-purchase-order-header-the-delivery-nameisnt-synced"></a><span data-ttu-id="1d195-179">Dopo aver modificato l'indirizzo di consegna nell'intestazione di un ordine fornitore, il nome della consegna non viene sincronizzato.</span><span class="sxs-lookup"><span data-stu-id="1d195-179">After I change the delivery address on a purchase order header, the delivery name isn't synced.</span></span>

### <a name="issue-description"></a><span data-ttu-id="1d195-180">Descrizione del problema</span><span class="sxs-lookup"><span data-stu-id="1d195-180">Issue description</span></span>

<span data-ttu-id="1d195-181">L'indirizzo nell'intestazione di un ordine fornitore viene aggiornato su un indirizzo che non è un indirizzo di consegna.</span><span class="sxs-lookup"><span data-stu-id="1d195-181">The address on the header of a purchase order is updated to an address that isn't a delivery address.</span></span> <span data-ttu-id="1d195-182">Sebbene l'indirizzo sia aggiornato nell'ordine fornitore, il nome della consegna non viene aggiornato in base all'indirizzo aggiornato.</span><span class="sxs-lookup"><span data-stu-id="1d195-182">Although the address is updated on the purchase order, the delivery name isn't updated based on the updated address.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="1d195-183">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="1d195-183">Issue resolution</span></span>

<span data-ttu-id="1d195-184">Questo comportamento è predefinito.</span><span class="sxs-lookup"><span data-stu-id="1d195-184">This behavior is by design.</span></span> <span data-ttu-id="1d195-185">L'indirizzo selezionato deve essere classificato come indirizzo di consegna.</span><span class="sxs-lookup"><span data-stu-id="1d195-185">The selected address must be classified as a delivery address.</span></span> <span data-ttu-id="1d195-186">In caso contrario, il nome della consegna non viene aggiornato in base all'indirizzo selezionato.</span><span class="sxs-lookup"><span data-stu-id="1d195-186">Otherwise, the delivery name isn't updated based on the selected address.</span></span>

## <a name="can-i-find-the-user-who-canceled-a-purchase-order"></a><span data-ttu-id="1d195-187">Posso trovare l'utente che ha annullato un ordine fornitore?</span><span class="sxs-lookup"><span data-stu-id="1d195-187">Can I find the user who canceled a purchase order?</span></span>

<span data-ttu-id="1d195-188">Questa informazioni viene registrata solo se per l'ordine fornitore è soggetto alla gestione delle modifiche.</span><span class="sxs-lookup"><span data-stu-id="1d195-188">This information is tracked only if the purchase order is subject to change management.</span></span> <span data-ttu-id="1d195-189">Se utilizzi la gestione delle modifiche, puoi vedere chi ha inviato la modifica (l'annullamento) e chi l'ha approvata.</span><span class="sxs-lookup"><span data-stu-id="1d195-189">If you use change management, you can see who submitted the change (the cancellation), and who approved it.</span></span>
