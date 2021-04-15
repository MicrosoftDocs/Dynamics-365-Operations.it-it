---
title: Risolvere problemi relativi a prezzi, sconti, accordi e ribassi
description: Questo argomento descrive come risolvere i problemi che potrebbero verificarsi mentre lavori con prezzi, sconti, accordi e ribassi.
author: SmithaNataraj
ms.date: 09/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: PurchTable, PurchTablePart, PurchRFQTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: smnatara
ms.search.validFrom: 2020-9-16
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: 12bc3cbccb1577c278489f640299510b3ced17e7
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5811088"
---
# <a name="troubleshoot-prices-discounts-agreements-and-rebates"></a><span data-ttu-id="e4f62-103">Risolvere problemi relativi a prezzi, sconti, accordi e ribassi</span><span class="sxs-lookup"><span data-stu-id="e4f62-103">Troubleshoot prices, discounts, agreements, and rebates</span></span>

<span data-ttu-id="e4f62-104">Questo argomento descrive come risolvere i problemi che potrebbero verificarsi mentre lavori con prezzi, sconti, accordi e ribassi.</span><span class="sxs-lookup"><span data-stu-id="e4f62-104">This topic describes how to fix issues that you might encounter while you work with prices, discounts, agreements, and rebates.</span></span>

## <a name="i-cant-link-a-purchase-agreement-to-a-purchase-order-line-after-the-purchase-order-is-created"></a><span data-ttu-id="e4f62-105">Non riesco a collegare un contratto di acquisto a una riga dell'ordine fornitore dopo aver creato l'ordine fornitore.</span><span class="sxs-lookup"><span data-stu-id="e4f62-105">I can't link a purchase agreement to a purchase order line after the purchase order is created.</span></span>

<span data-ttu-id="e4f62-106">Un contratto di acquisto deve essere associato a un ordine fornitore dopo aver creato l'ordine fornitore.</span><span class="sxs-lookup"><span data-stu-id="e4f62-106">A purchase agreement must be associated with a purchase order when the purchase order is created.</span></span> <span data-ttu-id="e4f62-107">In caso contrario, le righe dell'ordine fornitore non possono essere associate alle righe del contratto di acquisto.</span><span class="sxs-lookup"><span data-stu-id="e4f62-107">Otherwise, purchase order lines can't be associated with purchase agreement lines.</span></span>

## <a name="what-check-triggers-the-update-prices-and-discounts-entered-manually-or-external-document-message"></a><span data-ttu-id="e4f62-108">Quale controllo attiva il messaggio "Aggiorna prezzi e sconti inseriti manualmente o documento esterno"?</span><span class="sxs-lookup"><span data-stu-id="e4f62-108">What check triggers the "Update prices and discounts entered manually or external document" message?</span></span>

<span data-ttu-id="e4f62-109">Quando si modifica la data di spedizione, è possibile che venga visualizzato un messaggio che indica "Aggiorna prezzi e sconti inseriti manualmente o documento esterno".</span><span class="sxs-lookup"><span data-stu-id="e4f62-109">When you change the shipping date, you might receive a message that states, "Update prices and discounts entered manually or external document."</span></span> <span data-ttu-id="e4f62-110">Viene visualizzato questo messaggio perché, se la data di spedizione viene modificata, potrebbe essere attivato un accordo commerciale o di vendita diverso e potrebbe causare una variazione del prezzo.</span><span class="sxs-lookup"><span data-stu-id="e4f62-110">You receive this message because, if the shipping date is changed, a different trade or sales agreement might be triggered and cause a price change.</span></span> <span data-ttu-id="e4f62-111">Una modifica alla data di spedizione può anche influire sui programmi di magazzino e su altre informazioni correlate.</span><span class="sxs-lookup"><span data-stu-id="e4f62-111">A change to the shipping date can also affect warehouse schedules and other related information.</span></span>

<span data-ttu-id="e4f62-112">Il messaggio viene attivato ogni volta che una delle date o alcuni altri parametri vengono modificati.</span><span class="sxs-lookup"><span data-stu-id="e4f62-112">The message is triggered whenever any of the dates or some other parameters are changed.</span></span> <span data-ttu-id="e4f62-113">Lo scopo del messaggio è assicurarsi di essere a conoscenza delle variazioni di prezzo che possono verificarsi a causa di tali cambiamenti.</span><span class="sxs-lookup"><span data-stu-id="e4f62-113">The purpose of the message is to make sure that you're aware of price changes that can occur because of those changes.</span></span>

<span data-ttu-id="e4f62-114">Il messaggio è il prompt della valutazione dell'accordo commerciale (TAE).</span><span class="sxs-lookup"><span data-stu-id="e4f62-114">The message is the trade agreement evaluation (TAE) prompt.</span></span> <span data-ttu-id="e4f62-115">Per una descrizione completa, vedi [Criteri di valutazione degli accordi commerciali](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/trade-agreement-evaluation-policies-white-paper).</span><span class="sxs-lookup"><span data-stu-id="e4f62-115">For a full description, see [Trade agreement evaluation policies](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/trade-agreement-evaluation-policies-white-paper).</span></span>

## <a name="a-purchase-order-receipt-doesnt-include-all-charges"></a><span data-ttu-id="e4f62-116">Una ricevuta dell'ordine fornitore non include tutti gli addebiti.</span><span class="sxs-lookup"><span data-stu-id="e4f62-116">A purchase order receipt doesn't include all charges.</span></span>

### <a name="reproduce-the-issue"></a><span data-ttu-id="e4f62-117">Riprodurre il problema</span><span class="sxs-lookup"><span data-stu-id="e4f62-117">Reproduce the issue</span></span>

<span data-ttu-id="e4f62-118">La seguente procedura mostra un modo per riprodurre il problema.</span><span class="sxs-lookup"><span data-stu-id="e4f62-118">The following procedure shows one way to reproduce the issue.</span></span>

1. <span data-ttu-id="e4f62-119">Nella pagina **Parametri di approvvigionamento**, nella scheda **Consegna**, assicurati che l'opzione **Genera spese sull'entrata prodotti** sia impostata su *Sì*.</span><span class="sxs-lookup"><span data-stu-id="e4f62-119">On the **Procurement and sourcing parameters** page, on the **Delivery** tab, make sure that the **Generate charges on product receipt** option is set to *Yes*.</span></span>
1. <span data-ttu-id="e4f62-120">Crea un ordine fornitore che includa le spese.</span><span class="sxs-lookup"><span data-stu-id="e4f62-120">Create a purchase order that includes charges.</span></span>
1. <span data-ttu-id="e4f62-121">Conferma l'ordine fornitore.</span><span class="sxs-lookup"><span data-stu-id="e4f62-121">Confirm the purchase order.</span></span>
1. <span data-ttu-id="e4f62-122">Ricevi l'ordine fornitore.</span><span class="sxs-lookup"><span data-stu-id="e4f62-122">Receive the purchase order.</span></span>
1. <span data-ttu-id="e4f62-123">Guarda il totale dell'entrata e confrontalo con il totale previsto.</span><span class="sxs-lookup"><span data-stu-id="e4f62-123">Look at the receipt total, and compare it to the expected total.</span></span>
1. <span data-ttu-id="e4f62-124">Si noti che non tutte le spese sono incluse nella ricevuta dell'ordine fornitore.</span><span class="sxs-lookup"><span data-stu-id="e4f62-124">Notice that not all the charges are included on the purchase order receipt.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="e4f62-125">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="e4f62-125">Issue resolution</span></span>

<span data-ttu-id="e4f62-126">La risoluzione dipende dal modo in cui sono state configurate le spese varie.</span><span class="sxs-lookup"><span data-stu-id="e4f62-126">The resolution depends on the way that the miscellaneous charges have been set up.</span></span> <span data-ttu-id="e4f62-127">Per informazioni su come configurare le spese varie per soddisfare le tue esigenze, consulta il seguente post del blog: [Pubblicare spese varie al momento dell'entrata del prodotto](https://cloudblogs.microsoft.com/dynamics365/no-audience/2014/11/11/post-misc-charges-at-time-of-product-receipt/).</span><span class="sxs-lookup"><span data-stu-id="e4f62-127">For information about how to set up miscellaneous charges to meet your requirements, see the following blog post: [Post misc. charges at time of product receipt](https://cloudblogs.microsoft.com/dynamics365/no-audience/2014/11/11/post-misc-charges-at-time-of-product-receipt/).</span></span>

## <a name="trade-agreement-prices-and-discounts-arent-applied-on-sales-or-purchase-order-lines-that-are-imported-through-data-management"></a><span data-ttu-id="e4f62-128">I prezzi e gli sconti degli accordi commerciali non vengono applicati alle righe dell'ordine fornitore o cliente importate tramite la gestione dei dati.</span><span class="sxs-lookup"><span data-stu-id="e4f62-128">Trade agreement prices and discounts aren't applied on sales or purchase order lines that are imported through data management.</span></span>

### <a name="issue-description"></a><span data-ttu-id="e4f62-129">Descrizione del problema</span><span class="sxs-lookup"><span data-stu-id="e4f62-129">Issue description</span></span>

<span data-ttu-id="e4f62-130">Gli accordi commerciali applicabili alle righe dell'ordine fornitore o cliente non vengono applicate alle righe importate tramite la gestione dei dati.</span><span class="sxs-lookup"><span data-stu-id="e4f62-130">Trade agreements that are applicable to sales or purchase order lines aren't applied on lines that are imported through data management.</span></span> <span data-ttu-id="e4f62-131">Tuttavia, gli stessi accordi commerciali vengono applicati alle righe dell'ordine fornitore o cliente create manualmente.</span><span class="sxs-lookup"><span data-stu-id="e4f62-131">However, the same trade agreements are applied on sales or purchase order lines that are manually created.</span></span>

### <a name="reason-for-the-issue"></a><span data-ttu-id="e4f62-132">Motivo del problema</span><span class="sxs-lookup"><span data-stu-id="e4f62-132">Reason for the issue</span></span>

<span data-ttu-id="e4f62-133">Se le righe dell'ordine fornitore importate tramite la gestione dei dati includono già informazioni sui prezzi, l'accordo commerciale non verrà rivalutato per tali righe.</span><span class="sxs-lookup"><span data-stu-id="e4f62-133">If purchase order lines that are imported via data management already include price information, the trade agreement won't be reevaluated for those lines.</span></span> <span data-ttu-id="e4f62-134">Ad esempio, se **Percentuale sconto riga** o uno qualsiasi dei valori di prezzo e sconto è impostata per una riga, gli accordi commerciali non verranno cercati per quella riga.</span><span class="sxs-lookup"><span data-stu-id="e4f62-134">For example, if **Line discount percentage** or any of the price and discount values is set for a line, then trade agreements will not be looked up for that line.</span></span>

### <a name="issue-workaround"></a><span data-ttu-id="e4f62-135">Soluzione del problema</span><span class="sxs-lookup"><span data-stu-id="e4f62-135">Issue workaround</span></span>

<span data-ttu-id="e4f62-136">Questo comportamento è previsto ed è simile sia per gli ordini cliente che per gli ordini fornitore.</span><span class="sxs-lookup"><span data-stu-id="e4f62-136">This behavior is expected, and is similar for both sales orders and purchase orders.</span></span>

<span data-ttu-id="e4f62-137">Come soluzione alternativa, importa le righe dell'ordine fornitore senza impostare alcuna informazione sul prezzo.</span><span class="sxs-lookup"><span data-stu-id="e4f62-137">As a workaround, import the purchase order lines without setting any price information.</span></span> <span data-ttu-id="e4f62-138">Gli accordi commerciali verranno quindi applicati e le righe dell'ordine fornitore verranno aggiornate in base agli accordi commerciali definiti.</span><span class="sxs-lookup"><span data-stu-id="e4f62-138">The trade agreements will then be applied, and the purchase order lines will be updated based on the defined trade agreements.</span></span>

## <a name="a-vendor-rebate-isnt-cumulated-based-on-invoices"></a><span data-ttu-id="e4f62-139">Uno sconto fornitore non viene accumulato in base alle fatture.</span><span class="sxs-lookup"><span data-stu-id="e4f62-139">A vendor rebate isn't cumulated based on invoices.</span></span>

### <a name="issue-description"></a><span data-ttu-id="e4f62-140">Descrizione del problema</span><span class="sxs-lookup"><span data-stu-id="e4f62-140">Issue description</span></span>

<span data-ttu-id="e4f62-141">Se le fatture registrate hanno date di scadenza diverse, tali fatture non vengono riflesse negli sconti fornitore generati da esse.</span><span class="sxs-lookup"><span data-stu-id="e4f62-141">If invoices that are posted have different due dates, those invoices aren't reflected in vendor rebates that are generated from them.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="e4f62-142">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="e4f62-142">Issue resolution</span></span>

<span data-ttu-id="e4f62-143">In base alla progettazione, la data di scadenza non viene considerata quando viene calcolato lo sconto fornitore.</span><span class="sxs-lookup"><span data-stu-id="e4f62-143">By design, the due date isn't considered when the vendor rebate is calculated.</span></span> <span data-ttu-id="e4f62-144">Valuta la possibilità di personalizzare il sistema in modo che la data di scadenza e la relazione con la fattura siano più evidenti rispetto all'effettivo sconto fornitore.</span><span class="sxs-lookup"><span data-stu-id="e4f62-144">Consider customizing the system so that the due date and the relation to the invoice are more apparent with respect to the actual vendor rebate.</span></span>

## <a name="unit-prices-on-purchase-orders-arent-calculated-based-on-the-unit-conversion"></a><span data-ttu-id="e4f62-145">I prezzi unitari sugli ordini fornitore non vengono calcolati in base alla conversione delle unità.</span><span class="sxs-lookup"><span data-stu-id="e4f62-145">Unit prices on purchase orders aren't calculated based on the unit conversion.</span></span>

### <a name="issue-description"></a><span data-ttu-id="e4f62-146">Descrizione del problema</span><span class="sxs-lookup"><span data-stu-id="e4f62-146">Issue description</span></span>

<span data-ttu-id="e4f62-147">Quando un'unità viene modificata in un ordine fornitore, i prezzi degli accordi commerciali non vengono ricalcolati in base alle definizioni di conversione delle unità.</span><span class="sxs-lookup"><span data-stu-id="e4f62-147">When a unit is changed on a purchase order, trade agreement prices aren't recalculated according to unit conversion definitions.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="e4f62-148">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="e4f62-148">Issue resolution</span></span>

<span data-ttu-id="e4f62-149">I prezzi sono sempre ottenuti da accordi commerciali (o altre impostazioni di prezzo nel sistema, come accordi di vendita o prezzi degli articoli) e sono impostati per un'unità.</span><span class="sxs-lookup"><span data-stu-id="e4f62-149">Prices are always obtained from trade agreements (or other price settings in the system, such as sales agreements or item prices), and they are set for a unit.</span></span>

<span data-ttu-id="e4f62-150">Se l'unità viene modificata in una riga ordine, il sistema cerca un prezzo per la nuova unità e lo applica.</span><span class="sxs-lookup"><span data-stu-id="e4f62-150">If the unit is changed on an order line, the system looks for a price for the new unit and applies that price.</span></span> <span data-ttu-id="e4f62-151">Se non viene trovato alcun prezzo per l'unità, il sistema non applica un prezzo.</span><span class="sxs-lookup"><span data-stu-id="e4f62-151">If no price is found for the unit, the system doesn't apply a price.</span></span> <span data-ttu-id="e4f62-152">La conversione di unità non può essere utilizzata per ricalcolare il prezzo in un'altra unità.</span><span class="sxs-lookup"><span data-stu-id="e4f62-152">The unit conversion can't be used to recalculate the price into another unit.</span></span> <span data-ttu-id="e4f62-153">In teoria, il prezzo per una scatola da dieci potrebbe non essere uguale a dieci volte il prezzo di una scatola.</span><span class="sxs-lookup"><span data-stu-id="e4f62-153">Theoretically, the price for one box of ten might not equal ten times the price of one box.</span></span>

### <a name="issue-workaround"></a><span data-ttu-id="e4f62-154">Soluzione del problema</span><span class="sxs-lookup"><span data-stu-id="e4f62-154">Issue workaround</span></span>

<span data-ttu-id="e4f62-155">Un modo per risolvere questo problema è assicurarsi che siano presenti accordi commerciali per le unità che si prevede verranno utilizzate nelle righe ordine per l'articolo.</span><span class="sxs-lookup"><span data-stu-id="e4f62-155">One way to work around this issue is to make sure that there are trade agreements for the units that you expect will be used on order lines for the item.</span></span>

## <a name="currency-conversion-issues-occur-with-trade-agreements"></a><span data-ttu-id="e4f62-156">Problemi di conversione di valuta si verificano con accordi commerciali.</span><span class="sxs-lookup"><span data-stu-id="e4f62-156">Currency conversion issues occur with trade agreements.</span></span>

<span data-ttu-id="e4f62-157">I prezzi degli accordi commerciali non vengono ricalcolati in base alla valuta quando la valuta è diversa in un ordine fornitore.</span><span class="sxs-lookup"><span data-stu-id="e4f62-157">Trade agreement prices aren't recalculated according to the currency when the currency differs on a purchase order.</span></span>

<span data-ttu-id="e4f62-158">La funzionalità *Valuta generica* consente di definire prezzi e sconti in una sola valuta.</span><span class="sxs-lookup"><span data-stu-id="e4f62-158">The *Generic currency* feature lets you define prices and discounts in only one currency.</span></span> <span data-ttu-id="e4f62-159">È quindi possibile convertire in altre valute come richiesto.</span><span class="sxs-lookup"><span data-stu-id="e4f62-159">You can then convert to other currencies as you require.</span></span> <span data-ttu-id="e4f62-160">Inoltre, al termine della conversione, la funzionalità può applicare automaticamente l'arrotondamento psicologico.</span><span class="sxs-lookup"><span data-stu-id="e4f62-160">Furthermore, after the conversion is done, the feature can automatically apply smart rounding.</span></span>

## <a name="when-i-open-the-purchase-agreement-page-in-a-line-view-mode-i-cant-personalize-the-page-by-adding-the-price-unit-field-in-the-overview-of-the-line"></a><span data-ttu-id="e4f62-161">Quando apro la pagina del contratto di acquisto in modalità di visualizzazione riga, non posso personalizzare la pagina aggiungendo il campo Unità di prezzo nella panoramica della riga.</span><span class="sxs-lookup"><span data-stu-id="e4f62-161">When I open the Purchase agreement page in a line view mode, I can't personalize the page by adding the Price unit field in the overview of the line.</span></span>

<span data-ttu-id="e4f62-162">Alcuni campi condivisi nel framework dell'accordo non possono essere inclusi nelle personalizzazioni.</span><span class="sxs-lookup"><span data-stu-id="e4f62-162">Some shared fields in the agreement framework can't be included in personalizations.</span></span> <span data-ttu-id="e4f62-163">Questa limitazione si verifica a causa del modello di dati implementato.</span><span class="sxs-lookup"><span data-stu-id="e4f62-163">This limitation occurs because of the data model that is implemented.</span></span> <span data-ttu-id="e4f62-164">Pertanto, non è possibile personalizzare il campo **Unità di prezzo**.</span><span class="sxs-lookup"><span data-stu-id="e4f62-164">Therefore, you can't personalize the **Price unit** field.</span></span>

## <a name="the-maximum-limit-from-a-purchase-agreement-isnt-effective-on-a-purchase-requisition"></a><span data-ttu-id="e4f62-165">Il limite massimo di un contratto di acquisto non è valido per una richiesta di acquisto.</span><span class="sxs-lookup"><span data-stu-id="e4f62-165">The maximum limit from a purchase agreement isn't effective on a purchase requisition.</span></span>

### <a name="issue-description"></a><span data-ttu-id="e4f62-166">Descrizione del problema</span><span class="sxs-lookup"><span data-stu-id="e4f62-166">Issue description</span></span>

<span data-ttu-id="e4f62-167">Quando una richiesta di acquisto è collegata a un contratto di acquisto, il limite massimo del contratto di acquisto non è valido per la richiesta di acquisto.</span><span class="sxs-lookup"><span data-stu-id="e4f62-167">When a purchase requisition is linked to a purchase agreement, the maximum limit from the purchase agreement isn't effective on the purchase requisition.</span></span> <span data-ttu-id="e4f62-168">Le informazioni sul prezzo predefinito sono inserite correttamente, ma nella richiesta di acquisto è possibile ordinare più del limite massimo del contratto di acquisto.</span><span class="sxs-lookup"><span data-stu-id="e4f62-168">The default price information is correctly entered, but more than the maximum limit from the purchase agreement can be ordered in the purchase requisition.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="e4f62-169">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="e4f62-169">Issue resolution</span></span>

<span data-ttu-id="e4f62-170">Questo comportamento è previsto.</span><span class="sxs-lookup"><span data-stu-id="e4f62-170">This behavior is expected.</span></span> <span data-ttu-id="e4f62-171">Poiché le richieste non sono sempre approvate, una quantità o un importo non deve essere riservato nel contratto di acquisto.</span><span class="sxs-lookup"><span data-stu-id="e4f62-171">Because requisitions aren't always approved, a quantity or amount should not be reserved on the purchase agreement.</span></span> <span data-ttu-id="e4f62-172">Pertanto, non raggiungerai il limite massimo del contratto di acquisto.</span><span class="sxs-lookup"><span data-stu-id="e4f62-172">Therefore, you won't meet the maximum limit from the purchase agreement.</span></span>

## <a name="trade-agreements-can-be-created-from-rejected-rfqs-therefore-the-system-doesnt-prevent-trade-agreement-journals-from-being-created-if-the-rfq-line-hasnt-been-accepted"></a><span data-ttu-id="e4f62-173">È possibile creare accordi commerciali da richieste di offerta rifiutate.</span><span class="sxs-lookup"><span data-stu-id="e4f62-173">Trade agreements can be created from rejected RFQs.</span></span> <span data-ttu-id="e4f62-174">Pertanto, il sistema non impedisce la creazione dei giornali di registrazione degli accordi commerciali se la riga RdO non è stata accettata.</span><span class="sxs-lookup"><span data-stu-id="e4f62-174">Therefore, the system doesn't prevent trade agreement journals from being created if the RFQ line hasn't been accepted.</span></span>

<span data-ttu-id="e4f62-175">È possibile creare accordi commerciali per qualsiasi risposta a una richiesta di offerta (RdO), indipendentemente dal fatto che sia stata accettata o rifiutata.</span><span class="sxs-lookup"><span data-stu-id="e4f62-175">You can create trade agreements for any replies for a request for quotation (RFQ), regardless of whether they were accepted or rejected.</span></span> <span data-ttu-id="e4f62-176">Per ulteriori informazioni, vedi [Panoramica sulle richieste di offerta (RdO)](request-quotations.md).</span><span class="sxs-lookup"><span data-stu-id="e4f62-176">For more information, see [Requests for quotation (RFQs) overview](request-quotations.md).</span></span>



[!INCLUDE[footer-include](../../includes/footer-banner.md)]