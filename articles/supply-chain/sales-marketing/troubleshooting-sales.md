---
title: Risolvere i problemi relativi agli ordini cliente
description: Questo argomento descrive come risolvere i problemi che potresti riscontrare mentre lavori con gli ordini cliente.
author: SmithaNataraj
manager: tfehr
ms.date: 09/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesTable, SalesTableListPage
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
ms.openlocfilehash: 6e51723915892f465ce09d09ee9ed622bab9451e
ms.sourcegitcommit: c986d5234b81d31cc6d054298be6f6ec92c1754c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/25/2020
ms.locfileid: "3889459"
---
# <a name="troubleshoot-sales-orders"></a><span data-ttu-id="b52c3-103">Risolvere i problemi relativi agli ordini cliente</span><span class="sxs-lookup"><span data-stu-id="b52c3-103">Troubleshoot sales orders</span></span>

<span data-ttu-id="b52c3-104">Questo argomento descrive come risolvere i problemi che potresti riscontrare mentre lavori con gli ordini cliente.</span><span class="sxs-lookup"><span data-stu-id="b52c3-104">This topic describes how to fix issues that you might encounter while you work with sales orders.</span></span>

## <a name="the-tax-information-isnt-updated-if-i-change-the-location-on-a-sales-order-header"></a><span data-ttu-id="b52c3-105">I dati fiscali non vengono aggiornati se cambio la posizione nell'intestazione di un ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="b52c3-105">The tax information isn't updated if I change the location on a sales order header.</span></span>

### <a name="issue-description"></a><span data-ttu-id="b52c3-106">Descrizione del problema</span><span class="sxs-lookup"><span data-stu-id="b52c3-106">Issue description</span></span>

<span data-ttu-id="b52c3-107">Se il sito, il magazzino o l'indirizzo di consegna viene modificato nell'intestazione di un ordine cliente o a livello di riga, le informazioni sull'imposta del caso non vengono aggiornate automaticamente per le righe.</span><span class="sxs-lookup"><span data-stu-id="b52c3-107">If the site, warehouse, or delivery address is changed either on a sales order header or at the line level, the case tax information isn't automatically updated for the lines.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="b52c3-108">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="b52c3-108">Issue resolution</span></span>

<span data-ttu-id="b52c3-109">Questo comportamento è predefinito.</span><span class="sxs-lookup"><span data-stu-id="b52c3-109">This behavior is by design.</span></span> <span data-ttu-id="b52c3-110">Il problema si verifica perché anche l'indirizzo di consegna, il sito e il magazzino non vengono modificati automaticamente a livello di riga.</span><span class="sxs-lookup"><span data-stu-id="b52c3-110">The issue occurs because the delivery address, site, and warehouse aren't automatically changed at the line level either.</span></span> <span data-ttu-id="b52c3-111">È necessario aggiornarli manualmente.</span><span class="sxs-lookup"><span data-stu-id="b52c3-111">You must update them manually.</span></span>

## <a name="if-there-are-two-trade-agreements-for-the-same-period-or-overlapping-periods-the-same-agreement-line-is-always-selected"></a><span data-ttu-id="b52c3-112">Se sono presenti due accordi commerciali per lo stesso periodo o periodi sovrapposti, viene sempre selezionata la stessa riga dell'accordo.</span><span class="sxs-lookup"><span data-stu-id="b52c3-112">If there are two trade agreements for the same period or overlapping periods, the same agreement line is always selected.</span></span>

### <a name="issue-description"></a><span data-ttu-id="b52c3-113">Descrizione del problema</span><span class="sxs-lookup"><span data-stu-id="b52c3-113">Issue description</span></span>

<span data-ttu-id="b52c3-114">Se due accordi commerciali sono definiti per lo stesso periodo o periodi sovrapposti, lo stesso accordo commerciale sembra essere selezionato ogni volta che si creano righe ordine cliente che contengono tali articoli.</span><span class="sxs-lookup"><span data-stu-id="b52c3-114">If two trade agreements are defined for the same period or overlapping periods, the same trade agreement seems to be selected every time when you create sales order lines that contain those items.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="b52c3-115">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="b52c3-115">Issue resolution</span></span>

<span data-ttu-id="b52c3-116">Se è presente più di un accordo commerciale per una determinata data, viene sempre selezionato l'accordo commerciale con il prezzo più basso.</span><span class="sxs-lookup"><span data-stu-id="b52c3-116">If there is more than one trade agreement for a given date, the trade agreement that has the lowest price is always selected.</span></span> <span data-ttu-id="b52c3-117">Per altre informazioni, scarica il seguente white paper: [Accordi commerciali in Microsoft Dynamics AX 2012](https://www.axug.com/HigherLogic/System/DownloadDocumentFile.ashx?DocumentFileKey=3396a3a8-1f48-4d85-8cd6-5fa982f62e90).</span><span class="sxs-lookup"><span data-stu-id="b52c3-117">For more information, download the following white paper: [Trade agreements in Microsoft Dynamics AX 2012](https://www.axug.com/HigherLogic/System/DownloadDocumentFile.ashx?DocumentFileKey=3396a3a8-1f48-4d85-8cd6-5fa982f62e90).</span></span>

## <a name="can-i-link-a-purchase-order-to-a-sales-order-to-fulfill-demand"></a><span data-ttu-id="b52c3-118">Posso collegare un ordine fornitore a un ordine cliente per soddisfare la domanda?</span><span class="sxs-lookup"><span data-stu-id="b52c3-118">Can I link a purchase order to a sales order to fulfill demand?</span></span>

<span data-ttu-id="b52c3-119">Puoi creare un ordine fornitore da un ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="b52c3-119">You can create a purchase order from a sales order.</span></span> <span data-ttu-id="b52c3-120">Per ulteriori informazioni, vedi [Creare un ordine fornitore da un ordine cliente](tasks/create-purchase-order-sales-order.md).</span><span class="sxs-lookup"><span data-stu-id="b52c3-120">For more information, see [Create a purchase order from a sales order](tasks/create-purchase-order-sales-order.md).</span></span>

## <a name="i-cant-cancel-or-delete-a-return-order-or-a-sales-order"></a><span data-ttu-id="b52c3-121">Non posso annullare o eliminare un ordine di reso o un ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="b52c3-121">I can't cancel or delete a return order or a sales order.</span></span>

<span data-ttu-id="b52c3-122">Puoi annullare solo gli ordini cliente e gli ordini di reso che si trovano in uno stato *Creato*.</span><span class="sxs-lookup"><span data-stu-id="b52c3-122">You can cancel only sales orders and return orders that are in a *Created* state.</span></span> <span data-ttu-id="b52c3-123">Per ulteriori informazioni, vedi [Annullare un ordine di reso](../service-management/cancel-return-order.md).</span><span class="sxs-lookup"><span data-stu-id="b52c3-123">For more information, see [Cancel a return order](../service-management/cancel-return-order.md).</span></span>

## <a name="when-i-try-to-cancel-a-sales-order-i-receive-a-reservations-cannot-be-removed-because-there-is-work-created-which-relies-on-the-reservations-error"></a><span data-ttu-id="b52c3-124">Quando provo ad annullare un ordine client, ricevo un messaggio di errore "Impossibile rimuovere le prenotazioni perché è presente lavoro creato che si basa sulle prenotazioni".</span><span class="sxs-lookup"><span data-stu-id="b52c3-124">When I try to cancel a sales order, I receive a "Reservations cannot be removed because there is work created which relies on the reservations" error.</span></span>

<span data-ttu-id="b52c3-125">Se il lavoro è associato a un ordine cliente, non è possibile annullare l'ordine cliente finché il lavoro non viene annullato e stornato.</span><span class="sxs-lookup"><span data-stu-id="b52c3-125">If work is associated with a sales order, you can't cancel the sales order until the work is canceled and reversed.</span></span> <span data-ttu-id="b52c3-126">Questo requisito si applica anche se il lavoro associato all'ordine cliente viene chiuso.</span><span class="sxs-lookup"><span data-stu-id="b52c3-126">This requirement applies even if the work that is associated with the sales order is closed.</span></span>

<span data-ttu-id="b52c3-127">Per risolvere questo problema, procedere come segue.</span><span class="sxs-lookup"><span data-stu-id="b52c3-127">To fix this issue, follow these steps.</span></span>

1. <span data-ttu-id="b52c3-128">Annulla il lavoro e inserisci nuovamente le scorte nell'ubicazione desiderata.</span><span class="sxs-lookup"><span data-stu-id="b52c3-128">Cancel the work, and put inventory back into the desired location.</span></span> <span data-ttu-id="b52c3-129">Vai al carico rilevante dell'ordine cliente e seleziona **Riduci quantità prelevata** sulla riga di carico o **Storna lavoro** nel riquadro azioni.</span><span class="sxs-lookup"><span data-stu-id="b52c3-129">Go to the relevant load of the sales order, and select either **Reduce picked quantity** on the load line or **Reverse work** on the Action Pane.</span></span>

    <span data-ttu-id="b52c3-130">Il lavoro ora ha uno stato di *Annullato* e viene creato ed elaborato automaticamente un nuovo lavoro di movimento scorte per reinserire le scorte nell'ubicazione descritta al momento dello storno.</span><span class="sxs-lookup"><span data-stu-id="b52c3-130">The work now has a status of *Canceled*, and new inventory movement work is automatically created and processed to put inventory back into the location that was described at the time of reversal.</span></span>

2. <span data-ttu-id="b52c3-131">Elimina il carico.</span><span class="sxs-lookup"><span data-stu-id="b52c3-131">Delete the load.</span></span> <span data-ttu-id="b52c3-132">Anche la spedizione viene eliminata.</span><span class="sxs-lookup"><span data-stu-id="b52c3-132">The shipment is also deleted.</span></span>
3. <span data-ttu-id="b52c3-133">Ora dovresti essere in grado di accedere all'ordine cliente e annullarlo.</span><span class="sxs-lookup"><span data-stu-id="b52c3-133">You should now be able to go to the sales order and cancel it.</span></span>

## <a name="i-cant-cancel-an-intercompany-purchase-order-that-is-linked-to-a-sales-order"></a><span data-ttu-id="b52c3-134">Non riesco ad annullare un ordine fornitore interaziendale collegato a un ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="b52c3-134">I can't cancel an intercompany purchase order that is linked to a sales order.</span></span>

### <a name="issue-description"></a><span data-ttu-id="b52c3-135">Descrizione del problema</span><span class="sxs-lookup"><span data-stu-id="b52c3-135">Issue description</span></span>

<span data-ttu-id="b52c3-136">Se tenti di annullare un ordine fornitore interaziendale collegato a un ordine cliente, è possibile che venga visualizzato il seguente messaggio di errore: "Impossibile ridurre la quantità perché la quantità di aggiornamento rimanente cambia segno".</span><span class="sxs-lookup"><span data-stu-id="b52c3-136">If you try to cancel an intercompany purchase order that is linked to a sales order, you might receive the following error message: "Quantity cannot be reduced because the remaining update quantity changes sign."</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="b52c3-137">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="b52c3-137">Issue resolution</span></span>

<span data-ttu-id="b52c3-138">Questo problema è stato risolto in Microsoft Dynamics 365 Supply Chain Management versione 10.0.13.</span><span class="sxs-lookup"><span data-stu-id="b52c3-138">This issue was fixed in Microsoft Dynamics 365 Supply Chain Management version 10.0.13.</span></span> <span data-ttu-id="b52c3-139">In quella versione e nelle versioni successive è ora possibile annullare un ordine fornitore interaziendale collegato a un ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="b52c3-139">In that version and later versions, you can now cancel an intercompany purchase order that is linked to a sales order.</span></span>

## <a name="can-i-restore-an-invoiced-sales-order-that-was-deleted"></a><span data-ttu-id="b52c3-140">Posso ripristinare un ordine cliente fatturato che è stato eliminato?</span><span class="sxs-lookup"><span data-stu-id="b52c3-140">Can I restore an invoiced sales order that was deleted?</span></span>

### <a name="issue-description"></a><span data-ttu-id="b52c3-141">Descrizione del problema</span><span class="sxs-lookup"><span data-stu-id="b52c3-141">Issue description</span></span>

<span data-ttu-id="b52c3-142">Un ordine cliente fatturato è stato eliminato per errore e si desidera ripristinarlo o visualizzarne i dettagli.</span><span class="sxs-lookup"><span data-stu-id="b52c3-142">An invoiced sales order was deleted by mistake, and you want to restore it or view its details.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="b52c3-143">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="b52c3-143">Issue resolution</span></span>

<span data-ttu-id="b52c3-144">Se l'ordine cliente eliminato è già stato fatturato, passa a **Account cliente \> Transazioni \>Documento originale \> Visualizza dettagli**.</span><span class="sxs-lookup"><span data-stu-id="b52c3-144">If the deleted sales order has already been invoiced, go to **Customer account \> Transactions \> Original document \> View details**.</span></span> <span data-ttu-id="b52c3-145">Trova la fattura che stai cercando e selezionala per visualizzarne i dettagli.</span><span class="sxs-lookup"><span data-stu-id="b52c3-145">Find the invoice that you're looking for, and select it to view its details.</span></span> <span data-ttu-id="b52c3-146">Questi dettagli includono il riferimento dell'ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="b52c3-146">These details include the sales order reference.</span></span> <span data-ttu-id="b52c3-147">Dovresti anche essere in grado di accedere ai dettagli dell'ordine cliente da quella pagina.</span><span class="sxs-lookup"><span data-stu-id="b52c3-147">You should also be able to access the sales order details from that page.</span></span>

## <a name="the-deadline-of-a-sales-order-header-cant-be-found-in-the-salesorderheaderv2entity-data-entity"></a><span data-ttu-id="b52c3-148">La scadenza di un'intestazione di un ordine cliente non si trova nell'entità di dati SalesOrderHeaderV2Entity.</span><span class="sxs-lookup"><span data-stu-id="b52c3-148">The deadline of a sales order header can't be found in the SalesOrderHeaderV2Entity data entity.</span></span>

<span data-ttu-id="b52c3-149">Il campo della scadenza non esiste nell'entità *SalesOrderHeaderV2Entity*.</span><span class="sxs-lookup"><span data-stu-id="b52c3-149">The deadline field doesn't exist on the *SalesOrderHeaderV2Entity* entity.</span></span>

## <a name="i-must-delete-orphaned-sales-order-records"></a><span data-ttu-id="b52c3-150">Devo eliminare i record degli ordini cliente orfani.</span><span class="sxs-lookup"><span data-stu-id="b52c3-150">I must delete orphaned sales order records.</span></span>

<span data-ttu-id="b52c3-151">Per pulire i record degli ordini cliente orfani, esegui il processo periodico *Eliminazione dell'ordine cliente* andando in una delle seguenti posizioni:</span><span class="sxs-lookup"><span data-stu-id="b52c3-151">To clean up orphaned sales order records, run the *Sales order deletion* periodic job by going to either of the following places:</span></span>

- <span data-ttu-id="b52c3-152">Vendite e marketing \> Attività periodiche \> Pulisci \> Elimina ordini cliente</span><span class="sxs-lookup"><span data-stu-id="b52c3-152">Sales and marketing \> Periodic tasks \> Clean up \> Delete sales orders</span></span>
- <span data-ttu-id="b52c3-153">Vendita al dettaglio e commercio \> Vendita al dettaglio e commercio IT \> Pulisci \> Elimina ordini cliente</span><span class="sxs-lookup"><span data-stu-id="b52c3-153">Retail and commerce \> Retail and commerce IT \> Clean up \> Delete sales orders</span></span>

## <a name="is-there-a-way-to-calculate-commissions-on-invoices-that-have-already-been-posted"></a><span data-ttu-id="b52c3-154">Esiste un modo per calcolare le commissioni sulle fatture già registrate?</span><span class="sxs-lookup"><span data-stu-id="b52c3-154">Is there a way to calculate commissions on invoices that have already been posted?</span></span>

<span data-ttu-id="b52c3-155">Supply Chain Management non supporta attualmente il calcolo delle commissioni per le fatture registrate.</span><span class="sxs-lookup"><span data-stu-id="b52c3-155">Supply Chain Management doesn't currently support the calculation of commissions for posted invoices.</span></span>

## <a name="a-bundle-item-isnt-supported-in-an-intercompany-process"></a><span data-ttu-id="b52c3-156">Un articolo in aggregazione non è supportato in un processo interaziendale.</span><span class="sxs-lookup"><span data-stu-id="b52c3-156">A bundle item isn't supported in an intercompany process.</span></span>

<span data-ttu-id="b52c3-157">L'articolo in aggregazione non è disponibile per l'ordine fornitore perché, se esamini le righe dell'ordine cliente per l'articolo aggregato, noterai che la quantità è *0* (zero) e lo stato è *Annullato*.</span><span class="sxs-lookup"><span data-stu-id="b52c3-157">The bundle item isn't available for the purchase order because, if you examine the sales order lines for the bundle item, you will notice that the quantity is *0* (zero) and the status is *Cancelled*.</span></span> <span data-ttu-id="b52c3-158">Questo comportamento è predefinito.</span><span class="sxs-lookup"><span data-stu-id="b52c3-158">This behavior is by design.</span></span> <span data-ttu-id="b52c3-159">L'ordine cliente acquista solo i componenti dell'articolo in aggregazione.</span><span class="sxs-lookup"><span data-stu-id="b52c3-159">The sales order buys only the components of the bundle item.</span></span> <span data-ttu-id="b52c3-160">Non acquista l'articolo in aggregazione stesso.</span><span class="sxs-lookup"><span data-stu-id="b52c3-160">It doesn't buy the bundle item itself.</span></span>

<span data-ttu-id="b52c3-161">Se devi acquistare un'aggregazione, valuta se devi contrassegnarlo come articolo dell'aggregazione, perché questa funzionalità è effettivamente progettata per scenari di riconoscimento dei ricavi.</span><span class="sxs-lookup"><span data-stu-id="b52c3-161">If you must buy a bundle, consider whether you have to mark it as bundle item, because this functionality is actually designed for revenue recognition scenarios.</span></span> <span data-ttu-id="b52c3-162">Per ulteriori informazioni su articoli e aggregazioni, vedi [Aggregazioni](../../finance/accounts-receivable/revenue-recognition-setup.md#bundles).</span><span class="sxs-lookup"><span data-stu-id="b52c3-162">For more information about bundle items, see [Bundles](../../finance/accounts-receivable/revenue-recognition-setup.md#bundles).</span></span>
