---
title: Alternative di consegna
description: I dipendenti che gestiscono gli ordini cliente possono utilizzare la pagina Alternative di consegna per trovare opzioni alternative l'evasione dell'ordine.
author: ChristianRytt
manager: AnnBe
ms.date: 04/10/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SalesLineDeliveryDetails
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 271623
ms.assetid: 527f6084-44fe-41bb-924f-4386e926358a
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: crytt
ms.dyn365.ops.intro: Version 1611
ms.search.validFrom: 2016-11-30
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: cbfbdf5f79ef557ea934505285b57562b0b289ba
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---

# <a name="delivery-alternatives"></a><span data-ttu-id="09288-103">Alternative di consegna</span><span class="sxs-lookup"><span data-stu-id="09288-103">Delivery alternatives</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="09288-104">I dipendenti che gestiscono gli ordini cliente possono utilizzare la pagina Alternative di consegna per trovare opzioni alternative l'evasione dell'ordine.</span><span class="sxs-lookup"><span data-stu-id="09288-104">Sales order takers can use the Delivery alternatives page to discover alternative order fulfillment options.</span></span>

<span data-ttu-id="09288-105">In Microsoft Dynamics 365 for Operations versione 1611 (novembre 2016), i dipendenti che gestiscono gli ordini cliente possono utilizzare la pagina **Alternative di consegna** per verificare le opzioni alternative l'esecuzione dell'ordine.</span><span class="sxs-lookup"><span data-stu-id="09288-105">In Microsoft Dynamics 365 for Operations version 1611 (November 2016), sales order takers can use the **Delivery alternatives** page to discover alternative order fulfillment options.</span></span> <span data-ttu-id="09288-106">Il layout della pagina riprogettato offre una migliore panoramica di tutte le opzioni alternative.</span><span class="sxs-lookup"><span data-stu-id="09288-106">The redesigned page layout gives a better overview of all alternative options.</span></span> <span data-ttu-id="09288-107">Consente inoltre ai dipendenti che gestiscono gli ordini di effettuare un'analisi oltre la società corrente per individuare opportunità di evasione.</span><span class="sxs-lookup"><span data-stu-id="09288-107">It also lets order takers look beyond the current company for fulfillment opportunities.</span></span> <span data-ttu-id="09288-108">È ora possibile visualizzare sia le opportunità interaziendali che le opportunità di fornitori esterni.</span><span class="sxs-lookup"><span data-stu-id="09288-108">They can now view both intercompany opportunities and opportunities from external vendors.</span></span> <span data-ttu-id="09288-109">Tramite l'ordinamento delle opzioni per data di consegna, dipendenti che gestiscono gli ordini cliente possono visualizzare un elenco di intelligente di alternative di consegna.</span><span class="sxs-lookup"><span data-stu-id="09288-109">By sorting the options by delivery date, sales order takers can view an intelligent list of delivery alternatives.</span></span> <span data-ttu-id="09288-110">Inoltre, i parametri consentono di gestire in modo migliore le consegne suggerite.</span><span class="sxs-lookup"><span data-stu-id="09288-110">In addition, parameters help them better manage the suggested deliveries.</span></span> <span data-ttu-id="09288-111">Poiché il tempo di trasporto può influire sulle date di consegna, gli addetti agli ordini cliente possono esaminare le varie opzioni di trasporto che i vettori offrono.</span><span class="sxs-lookup"><span data-stu-id="09288-111">Because transport time can affect delivery dates, sales order takers can explore the various transportation choices that carriers offer.</span></span> <span data-ttu-id="09288-112">Per ogni suggerimento vengono mostrate informazioni dettagliate, gli addetti agli ordini cliente possono quindi prendere decisioni informate direttamente nella pagina **Alternative di consegna**.</span><span class="sxs-lookup"><span data-stu-id="09288-112">Because detailed information is shown for each suggestion, order takers can make informed decisions directly from the **Delivery alternatives** page.</span></span>

## <a name="open-the-delivery-alternatives-page"></a><span data-ttu-id="09288-113">Aprire la pagina di Alternative di consegna</span><span class="sxs-lookup"><span data-stu-id="09288-113">Open the Delivery alternatives page</span></span>
<span data-ttu-id="09288-114">È possibile aprire la pagina **Alternative di** **consegna** della riga ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="09288-114">You can open the **Delivery** **alternatives** page from the sales order line.</span></span>

1.  <span data-ttu-id="09288-115">Fare clic su **Prodotti e fornitura** &gt; **Alternative di consegna**.</span><span class="sxs-lookup"><span data-stu-id="09288-115">Click **Products and supply** &gt; **Delivery alternatives**.</span></span>
2.  <span data-ttu-id="09288-116">Fare clic su **Dettagli riga** &gt; **Consegna** &gt; **Alternative di consegna**.</span><span class="sxs-lookup"><span data-stu-id="09288-116">Click **Line details** &gt; **Delivery** &gt; **Delivery alternatives.**</span></span>

<span data-ttu-id="09288-117">È anche possibile aprire la pagina **Alternative di consegna** aprendo l'area di lavoro **Elaborazione e richiesta di informazioni ordini cliente** e facendo clic su **Ordini e preferiti** &gt; **Righe ordine ritardate** &gt; **Alternative di consegna** **Nota**: è possibile aprire la pagina **Alternative di consegna** solo se entrambe le seguenti condizioni sono state soddisfatte:</span><span class="sxs-lookup"><span data-stu-id="09288-117">You can also open the **Delivery alternatives** page by opening the **Sales order processing and inquiry** workspace, and then clicking **Orders and favorites** &gt; **Delayed order lines** &gt; **Delivery alternatives** **Note:** You can open the **Delivery alternatives** page only if both the following conditions are met:</span></span>

-   <span data-ttu-id="09288-118">Tutte le informazioni obbligatorie per la riga di vendita sono state specificate.</span><span class="sxs-lookup"><span data-stu-id="09288-118">All mandatory sales line information is filled in.</span></span>
-   <span data-ttu-id="09288-119">Il campo **Controllo data di consegna** è impostato su un valore deverso da **Nessuno**.</span><span class="sxs-lookup"><span data-stu-id="09288-119">The **Delivery date control** field is set to a value other than **None**.</span></span>

## <a name="delivery-date-control-methods"></a><span data-ttu-id="09288-120">Metodi di controllo data di consegna</span><span class="sxs-lookup"><span data-stu-id="09288-120">Delivery date control methods</span></span>
<span data-ttu-id="09288-121">Il metodo di controllo della data di consegna determina le modalità secondo cui il sistema stabilisce le date di consegna, calcola le alternative di consegna e stabilisce le informazioni da visualizzare.</span><span class="sxs-lookup"><span data-stu-id="09288-121">The delivery date control method determines how the system establishes delivery dates, how delivery alternatives are calculated, and what information is shown.</span></span> <span data-ttu-id="09288-122">Si noti che il controllo dei dati di consegna si basa sui calendari.</span><span class="sxs-lookup"><span data-stu-id="09288-122">Note that delivery data control takes calendars into consideration.</span></span> <span data-ttu-id="09288-123">Di conseguenza, i calendari seguenti possono influire sulla data di ricezione suggerita: calendario di magazzino, calendario di spedizione, calendario del fornitore e calendario del cliente.</span><span class="sxs-lookup"><span data-stu-id="09288-123">Therefore, the following calendars can affect the suggested receipt date: Warehouse calendar, Transport calendar, Vendor calendar, and Customer calendar.</span></span> <span data-ttu-id="09288-124">Nella seguente tabella viene descritto ogni metodo per il controllo della data di consegna.</span><span class="sxs-lookup"><span data-stu-id="09288-124">The following table describes each method for delivery date control.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><span data-ttu-id="09288-125"><strong>Metodo</strong></span><span class="sxs-lookup"><span data-stu-id="09288-125"><strong>Method</strong></span></span></td>
<td><span data-ttu-id="09288-126"><strong>Descrizione</strong></span><span class="sxs-lookup"><span data-stu-id="09288-126"><strong>Description</strong></span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="09288-127"><strong>Nessuna</strong></span><span class="sxs-lookup"><span data-stu-id="09288-127"><strong>None</strong></span></span></td>
<td><ul>
<li><span data-ttu-id="09288-128">Le alternative di consegna per le righe di vendita non sono supportate.</span><span class="sxs-lookup"><span data-stu-id="09288-128">Delivery alternatives for sales lines aren't supported.</span></span> <span data-ttu-id="09288-129">Questa opzione disattiva il controllo dei dati di consegna.</span><span class="sxs-lookup"><span data-stu-id="09288-129">This option turns off delivery data control.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="09288-130"><strong>Lead time di vendita</strong></span><span class="sxs-lookup"><span data-stu-id="09288-130"><strong>Sales lead time</strong></span></span></td>
<td><ul>
<li><span data-ttu-id="09288-131">Le alternative di consegna vengono calcolate in base al lead time di vendita predefinito.</span><span class="sxs-lookup"><span data-stu-id="09288-131">Delivery alternatives are calculated based on the predefined sales lead time.</span></span> <span data-ttu-id="09288-132">I giorni di trasporto vengono calcolati in base alla modalità di consegna.</span><span class="sxs-lookup"><span data-stu-id="09288-132">The transport days are calculated based on the mode of delivery.</span></span></li>
<li><span data-ttu-id="09288-133">Le alternative di consegna includono i magazzini con scorte disponibili e ordini di domanda/fornitura.</span><span class="sxs-lookup"><span data-stu-id="09288-133">Delivery alternatives include warehouses that have on-hand inventory, and supply/demand orders.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="09288-134"><strong>ATP</strong></span><span class="sxs-lookup"><span data-stu-id="09288-134"><strong>ATP</strong></span></span></td>
<td><ul>
<li><span data-ttu-id="09288-135">Le alternative di consegna vengono calcolate in base a logica available-to-promise (ATP).</span><span class="sxs-lookup"><span data-stu-id="09288-135">Delivery alternatives are calculated based on available to promise (ATP) logic.</span></span> <span data-ttu-id="09288-136">Vengono considerate la disponibilità corrente e la disponibilità futura.</span><span class="sxs-lookup"><span data-stu-id="09288-136">The current availability and expected future availability are considered.</span></span> <span data-ttu-id="09288-137">I giorni di trasporto vengono calcolati in base alla modalità di consegna.</span><span class="sxs-lookup"><span data-stu-id="09288-137">The transport days are calculated based on the mode of delivery.</span></span></li>
<li><span data-ttu-id="09288-138">Le alternative di consegna includono i magazzini con scorte disponibili e ordini di domanda/fornitura.</span><span class="sxs-lookup"><span data-stu-id="09288-138">Delivery alternatives include warehouses that have on-hand inventory, and supply/demand orders.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="09288-139"><strong>ATP + margine su uscita magazzino</strong></span><span class="sxs-lookup"><span data-stu-id="09288-139"><strong>ATP + Issue margin</strong></span></span></td>
<td><ul>
<li><span data-ttu-id="09288-140">Le alternative di consegna vengono calcolate come per il metodo di calcolo ATP, ma il margine su uscita da magazzino viene incluso nel calcolo.</span><span class="sxs-lookup"><span data-stu-id="09288-140">Delivery alternatives are calculated as for the ATP method, but the issue margin is included in the calculation.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="09288-141"><strong>CTP</strong></span><span class="sxs-lookup"><span data-stu-id="09288-141"><strong>CTP</strong></span></span></td>
<td><ul>
<li><span data-ttu-id="09288-142">Le alternative di consegna vengono calcolate in base a logica capable-to-promise (CTP).</span><span class="sxs-lookup"><span data-stu-id="09288-142">Delivery alternatives are calculated based on the capable to promise (CTP) logic.</span></span> <span data-ttu-id="09288-143">L'esplosione MRP viene utilizzata per determinare la disponibilità.</span><span class="sxs-lookup"><span data-stu-id="09288-143">MRP explosion is used to determine availability.</span></span> <span data-ttu-id="09288-144">Tenere presente che, al minimo, CTP imposta le date di consegna al lead time di vendita.</span><span class="sxs-lookup"><span data-stu-id="09288-144">Note that, at a minimum, CTP offsets delivery dates to the sales lead time.</span></span> <span data-ttu-id="09288-145">I giorni di trasporto vengono calcolati in base alla modalità di consegna.</span><span class="sxs-lookup"><span data-stu-id="09288-145">The transport days are calculated based on the mode of delivery.</span></span></li>
<li><span data-ttu-id="09288-146">Le date di consegna alternative includono suggerimenti per i magazzini seguenti:</span><span class="sxs-lookup"><span data-stu-id="09288-146">Delivery alternatives include suggestions for the following warehouses:</span></span>
<ul>
<li><span data-ttu-id="09288-147">Magazzino corrente</span><span class="sxs-lookup"><span data-stu-id="09288-147">Current warehouse</span></span></li>
<li><span data-ttu-id="09288-148">Magazzino predefinito</span><span class="sxs-lookup"><span data-stu-id="09288-148">Default warehouse</span></span></li>
<li><span data-ttu-id="09288-149">Tutti i magazzini con scorte disponibili</span><span class="sxs-lookup"><span data-stu-id="09288-149">All warehouses that have available on-hand inventory</span></span></li>
<li><span data-ttu-id="09288-150">Tutti i magazzini con ordini di fornitura</span><span class="sxs-lookup"><span data-stu-id="09288-150">All warehouses that have supply orders</span></span></li>
<li><span data-ttu-id="09288-151">Tutti i magazzini con versioni attive della distinta base (BOM)</span><span class="sxs-lookup"><span data-stu-id="09288-151">All warehouses that have active bill of materials (BOM) versions</span></span></li>
</ul></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="view-information-about-delivery-alternatives"></a><span data-ttu-id="09288-152">Visualizzare informazioni sulle alternative di consegna</span><span class="sxs-lookup"><span data-stu-id="09288-152">View information about delivery alternatives</span></span>
<span data-ttu-id="09288-153">In questa sezione vengono descritte le informazioni sulle alternative di consegna disponibili in ogni scheda della pagina **Alternative di consegna**.</span><span class="sxs-lookup"><span data-stu-id="09288-153">This section describes the information about delivery alternatives that is available on each tab of the **Delivery alternatives** page.</span></span>

### <a name="products"></a><span data-ttu-id="09288-154">Prodotti</span><span class="sxs-lookup"><span data-stu-id="09288-154">Products</span></span>

<span data-ttu-id="09288-155">In questa scheda viene visualizzato un riepilogo dei prodotti e i dettagli della riga di vendita corrente.</span><span class="sxs-lookup"><span data-stu-id="09288-155">This tab shows a summary of the product and details of the current sales line.</span></span>

### <a name="delivery-alternatives"></a><span data-ttu-id="09288-156">Alternative di consegna</span><span class="sxs-lookup"><span data-stu-id="09288-156">Delivery alternatives</span></span>

<span data-ttu-id="09288-157">La scheda consente di visualizzare un elenco di alternative di consegna ordinate per dati di ricezione.</span><span class="sxs-lookup"><span data-stu-id="09288-157">This tab shows a list of delivery alternatives that is sorted by receipt data.</span></span> <span data-ttu-id="09288-158">Sopra l'elenco, è possibile selezionare le opzione in base alla quale visualizzare i suggerimenti.</span><span class="sxs-lookup"><span data-stu-id="09288-158">Above the list, you can select which options to base the suggestions on.</span></span> <span data-ttu-id="09288-159">È inoltre possibile selezionare la modalità di consegna, che determina i giorni di spedizione.</span><span class="sxs-lookup"><span data-stu-id="09288-159">You can also select the mode of delivery, which determines the transport days.</span></span> <span data-ttu-id="09288-160">Sono disponibili le seguenti opzioni:</span><span class="sxs-lookup"><span data-stu-id="09288-160">The following options are available:</span></span>

-   <span data-ttu-id="09288-161">**Includi altre varianti prodotto** - Questa opzione è disponibile per i prodotti con varianti prodotto.</span><span class="sxs-lookup"><span data-stu-id="09288-161">**Include other product variants** - This option is available for products that have product variants.</span></span> <span data-ttu-id="09288-162">verranno incluse le alternative di consegna per altre varianti prodotto.</span><span class="sxs-lookup"><span data-stu-id="09288-162">It will include delivery alternatives for other variants of the product.</span></span> <span data-ttu-id="09288-163">Questa opzione non è disponibile per CTP.</span><span class="sxs-lookup"><span data-stu-id="09288-163">This option isn't available for CTP.</span></span>
-   <span data-ttu-id="09288-164">**Includi quantità parziale** - Per impostazione predefinita, vengono inclusi solo i suggerimenti che soddisfano l'intera quantità della riga cliente.</span><span class="sxs-lookup"><span data-stu-id="09288-164">**Include partial quantity** - By default, only suggestions that fulfill the full quantity of the sales line are included.</span></span> <span data-ttu-id="09288-165">Selezionare questa opzione per includere i suggerimenti che soddisfano solo parzialmente la riga di vendita.</span><span class="sxs-lookup"><span data-stu-id="09288-165">Select this option to include suggestions that only partially fulfill the order line.</span></span> <span data-ttu-id="09288-166">Questa opzione è utile quando il cliente richiede una data più vicina e accetta la consegna parziale.</span><span class="sxs-lookup"><span data-stu-id="09288-166">This option is useful when the customer requests an earlier delivery date and accepts partial delivery.</span></span>
-   <span data-ttu-id="09288-167">**Includi date successive** - Per impostazione predefinita, vengono mostrati solo i suggerimenti migliori (precedenti) rispetto alle date correnti nella riga di vendita.</span><span class="sxs-lookup"><span data-stu-id="09288-167">**Include later dates** - By default, only suggestions that are better (earlier) than the current dates on the sales line are shown.</span></span> <span data-ttu-id="09288-168">Selezionare questa opzione per includere le dati successive.</span><span class="sxs-lookup"><span data-stu-id="09288-168">Select this option to include later dates.</span></span> <span data-ttu-id="09288-169">Questa opzione può risultare utile nelle situazioni in cui parametri diversi dalla data hanno priorità.</span><span class="sxs-lookup"><span data-stu-id="09288-169">This option can be useful in situations where parameters other than the date have priority.</span></span> <span data-ttu-id="09288-170">Ad esempio, un fornitore o un magazzino specifico può essere preferito.</span><span class="sxs-lookup"><span data-stu-id="09288-170">For example, a specific vendor or warehouse might be preferred.</span></span>
-   <span data-ttu-id="09288-171">**Modalità di consegna** - Selezionare la modalità di consegna preferita per ottimizzare il tempo e costo di trasporto.</span><span class="sxs-lookup"><span data-stu-id="09288-171">**Mode of delivery** - Select the preferred mode of delivery to optimize transport time and cost.</span></span> <span data-ttu-id="09288-172">L'effetto sarà immediatamente visualizzato nelle alternative di consegna suggerite.</span><span class="sxs-lookup"><span data-stu-id="09288-172">You will immediately see the effect on the suggested delivery alternatives.</span></span> <span data-ttu-id="09288-173">Di conseguenza, è facile confrontare le alternative.</span><span class="sxs-lookup"><span data-stu-id="09288-173">Therefore, it's easy to compare the alternatives.</span></span>
-   <span data-ttu-id="09288-174">**Includi approvvigionamento** - Quando è selezionato l'approvvigionamento, le alternative di consegna suggerite includono opzioni relative sia ai fornitori esterni che ad altre società dell'impresa (interaziendale).</span><span class="sxs-lookup"><span data-stu-id="09288-174">**Include procurement** - When procurement is selected, the suggested delivery alternatives include options to procure from both external vendors and other companies in the enterprise (intercompany).</span></span> <span data-ttu-id="09288-175">L'opzione **Includi approvvigionamento** è supportata per il controllo delle date di consegna ATP e ATP + margine su uscita magazzino.</span><span class="sxs-lookup"><span data-stu-id="09288-175">The **Include procurement** option is supported for ATP and ATP + Issue margin delivery date control.</span></span> <span data-ttu-id="09288-176">Vengono incluse le opzioni di approvvigionamento del fornitore acquisti predefinito per il prodotto e di tutti i fornitori approvati per il prodotto.</span><span class="sxs-lookup"><span data-stu-id="09288-176">Procurement options from the default purchase vendor for the product and all approved vendors for the product are included.</span></span>
-   <span data-ttu-id="09288-177">Per i fornitori esterni, il calcolo è basato sul lead time di acquisto.</span><span class="sxs-lookup"><span data-stu-id="09288-177">For external vendors, the calculation is based on the purchase lead time.</span></span>
-   <span data-ttu-id="09288-178">Per gli ordini interaziendali, il calcolo prende in considerazione i prodotti disponibili dalla società di approvvigionamento, in base al controllo della data di consegna nella società di approvvigionamento.</span><span class="sxs-lookup"><span data-stu-id="09288-178">For intercompany, the calculation considers what is available from the sourcing company, based on delivery date control in the sourcing company.</span></span>
-   <span data-ttu-id="09288-179">**Tipo di consegna** (Rilevante per l'approvvigionamento)</span><span class="sxs-lookup"><span data-stu-id="09288-179">**Delivery type** (Relevant for procurement)</span></span>
    -   <span data-ttu-id="09288-180">**Scorte** - I prodotti vengono spediti dal magazzino di approvvigionamento al sito/magazzino nella riga di vendita.</span><span class="sxs-lookup"><span data-stu-id="09288-180">**Stock** - Products are shipped from the sourcing warehouse to the site/warehouse on the sales line.</span></span> <span data-ttu-id="09288-181">Vengono quindi spediti da tale magazzino al cliente.</span><span class="sxs-lookup"><span data-stu-id="09288-181">They are then shipped from that warehouse to the customer.</span></span>
    -   <span data-ttu-id="09288-182">**Consegna diretta** - I prodotti devono essere inviati direttamente dal magazzino di approvvigionamento al cliente.</span><span class="sxs-lookup"><span data-stu-id="09288-182">**Direct delivery** - Products are shipped directly from the sourcing warehouse to the customer.</span></span>

### <a name="availability-information"></a><span data-ttu-id="09288-183">Informazioni sulla disponibilità</span><span class="sxs-lookup"><span data-stu-id="09288-183">Availability information</span></span>

<span data-ttu-id="09288-184">Le informazioni contenute in questa scheda sono correlate alla riga alternativa di consegna selezionata.</span><span class="sxs-lookup"><span data-stu-id="09288-184">Information on this tab is related to the delivery alternative line that is selected.</span></span> <span data-ttu-id="09288-185">Vengono indicate le seguenti informazioni, a seconda del controllo della data di consegna per la riga ordine:</span><span class="sxs-lookup"><span data-stu-id="09288-185">The following information is shown, depending on the delivery date control for the sales line:</span></span>

-   <span data-ttu-id="09288-186">**Lead time di vendita**</span><span class="sxs-lookup"><span data-stu-id="09288-186">**Sales lead time**</span></span>
    -   <span data-ttu-id="09288-187">**Disponibile oggi** - Mostra le scorte fisiche attualmente disponibili, la qtà fisica prenotata e la qtà fisica disponibile.</span><span class="sxs-lookup"><span data-stu-id="09288-187">**Available today** - Show the current physical on-hand, physical reserved, and available physical inventory.</span></span>
    -   <span data-ttu-id="09288-188">**Parametri** - Mostra il lead time di vendita e l'unità di magazzino.</span><span class="sxs-lookup"><span data-stu-id="09288-188">**Parameters** - Show the inventory unit and sales lead time.</span></span>

-   <span data-ttu-id="09288-189">**ATP e ATP + Margine su uscita da magazzino**</span><span class="sxs-lookup"><span data-stu-id="09288-189">**ATP and ATP + Issue margin**</span></span>
    -   <span data-ttu-id="09288-190">**Disponibile oggi** - Mostra le scorte fisiche attualmente disponibili, la qtà fisica prenotata e la qtà fisica disponibile.</span><span class="sxs-lookup"><span data-stu-id="09288-190">**Available today** - Show the current physical on-hand, physical reserved, and available physical inventory.</span></span>
    -   <span data-ttu-id="09288-191">**Parametri** - Mostra il lead time di vendita e l'unità di magazzino.</span><span class="sxs-lookup"><span data-stu-id="09288-191">**Parameters** - Show the inventory unit and sales lead time.</span></span>
    -   <span data-ttu-id="09288-192">**Disponibilità futura** - Mostra una rappresentazione grafica della disponibilità corrente e futura per il sito e il magazzino selezionati in **Alternative di consegna**.</span><span class="sxs-lookup"><span data-stu-id="09288-192">**Future availability** - Show a graphical representation of current and future availability for the selected site and warehouse under **Delivery alternatives**.</span></span> <span data-ttu-id="09288-193">È possibile fare clic sulle colonne del grafico per visualizzare informazioni più dettagliate sulla futura disponibilità del prodotto.</span><span class="sxs-lookup"><span data-stu-id="09288-193">You can click the chart columns to see more detailed information about the future availability of the product.</span></span> <span data-ttu-id="09288-194">Il cursore mostra un elenco degli ordini di fornitura rilevanti e della domanda in un intervallo temporale ATP.</span><span class="sxs-lookup"><span data-stu-id="09288-194">The slider shows a list of relevant demand and supply orders within the ATP time fence.</span></span>

-   <span data-ttu-id="09288-195">**CTP**</span><span class="sxs-lookup"><span data-stu-id="09288-195">**CTP**</span></span>
    -   <span data-ttu-id="09288-196">**Disponibile oggi** - Mostra le scorte fisiche attualmente disponibili, la qtà fisica prenotata e la qtà fisica disponibile.</span><span class="sxs-lookup"><span data-stu-id="09288-196">**Available today** - Show the current physical on-hand, physical reserved, and available physical inventory.</span></span>
    -   <span data-ttu-id="09288-197">**Parametri** - Mostra il lead time di vendita e l'unità di magazzino.</span><span class="sxs-lookup"><span data-stu-id="09288-197">**Parameters** - Show the inventory unit and sales lead time.</span></span>
    -   <span data-ttu-id="09288-198">**Esplosione** - Mostra un'esplosione della fornitura per l'alternativa di consegna selezionata.</span><span class="sxs-lookup"><span data-stu-id="09288-198">**Explosion** - Show a supply explosion of the selected delivery alternative.</span></span> <span data-ttu-id="09288-199">È possibile utilizzare le **impostazioni** per modificare i campi e le dimensioni inventariali che vengono visualizzati nell'esplosione.</span><span class="sxs-lookup"><span data-stu-id="09288-199">You can use **Setup** to change the fields and inventory dimensions that are shown in the explosion.</span></span>

### <a name="impact-of-selected-alternative"></a><span data-ttu-id="09288-200">Impatto dell'alternativa selezionata</span><span class="sxs-lookup"><span data-stu-id="09288-200">Impact of selected alternative</span></span>

<span data-ttu-id="09288-201">Questa scheda evidenzia l'impatto dell'alternativa di consegna selezionata.</span><span class="sxs-lookup"><span data-stu-id="09288-201">This tab highlights the impact of the selected delivery alternative.</span></span> <span data-ttu-id="09288-202">Se si fa clic su **OK**, la riga di vendita viene aggiornata con i valori evidenziati nelle colonne SELEZIONATE.</span><span class="sxs-lookup"><span data-stu-id="09288-202">If you click **OK**, the sales line is updated with the highlighted values in the SELECTED columns.</span></span> <span data-ttu-id="09288-203">Si noti che, se la quantità dell'alternativa di consegna selezionata è inferiore alla quantità delle righe di vendita, viene creata una programmazione consegna e la riga ordine viene divisa in due righe: una riga per la quantità selezionata e una riga per la quantità rimanente.</span><span class="sxs-lookup"><span data-stu-id="09288-203">Note that, if the quantity on the selected delivery alternative is less than quantity on the sales line, a delivery schedule is created, and the order line is split into two lines: one line for the selected quantity and one line for the remaining quantity.</span></span> <span data-ttu-id="09288-204">È inoltre possibile aggiornare la riga commerciale in modo che corrisponda alle righe di programmazione che influiscono sulla valutazione.</span><span class="sxs-lookup"><span data-stu-id="09288-204">You can also update the commercial line so that it matches the schedule lines and affects the pricing.</span></span>

<a name="see-also"></a><span data-ttu-id="09288-205">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="09288-205">See also</span></span>
--------

[<span data-ttu-id="09288-206">Promesse ordine</span><span class="sxs-lookup"><span data-stu-id="09288-206">Order promising</span></span>](delivery-dates-available-promise-calculations.md)





