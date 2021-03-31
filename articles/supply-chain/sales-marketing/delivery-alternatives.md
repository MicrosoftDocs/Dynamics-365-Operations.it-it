---
title: Alternative di consegna
description: I dipendenti che gestiscono gli ordini cliente possono utilizzare la pagina Alternative di consegna per trovare opzioni alternative l'evasione dell'ordine.
author: ChristianRytt
manager: tfehr
ms.date: 04/10/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesLineDeliveryDetails
audience: Application User
ms.reviewer: kamaybac
ms.custom: 271623
ms.assetid: 527f6084-44fe-41bb-924f-4386e926358a
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: crytt
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: 783307ea5cc764f4a04d069dfd7d614a4f63dd2d
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5229257"
---
# <a name="delivery-alternatives"></a><span data-ttu-id="98834-103">Alternative di consegna</span><span class="sxs-lookup"><span data-stu-id="98834-103">Delivery alternatives</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="98834-104">I dipendenti che gestiscono gli ordini cliente possono utilizzare la pagina **Alternative di consegna** per trovare opzioni alternative l'evasione dell'ordine.</span><span class="sxs-lookup"><span data-stu-id="98834-104">Sales order takers can use the **Delivery alternatives** page to discover alternative order fulfillment options.</span></span>

<span data-ttu-id="98834-105">Il layout della pagina **Alternative di consegna** offre una panoramica di tutte le opzioni alternative.</span><span class="sxs-lookup"><span data-stu-id="98834-105">The **Delivery alternatives** page layout gives an overview of all alternative options.</span></span> <span data-ttu-id="98834-106">Consente inoltre ai dipendenti che gestiscono gli ordini di effettuare un'analisi oltre la società corrente per individuare opportunità di evasione.</span><span class="sxs-lookup"><span data-stu-id="98834-106">It also lets order takers look beyond the current company for fulfillment opportunities.</span></span> <span data-ttu-id="98834-107">È ora possibile visualizzare sia le opportunità interaziendali che le opportunità di fornitori esterni.</span><span class="sxs-lookup"><span data-stu-id="98834-107">They can now view both intercompany opportunities and opportunities from external vendors.</span></span> <span data-ttu-id="98834-108">Tramite l'ordinamento delle opzioni per data di consegna, dipendenti che gestiscono gli ordini cliente possono visualizzare un elenco di intelligente di alternative di consegna.</span><span class="sxs-lookup"><span data-stu-id="98834-108">By sorting the options by delivery date, sales order takers can view an intelligent list of delivery alternatives.</span></span> <span data-ttu-id="98834-109">Inoltre, i parametri consentono di gestire in modo migliore le consegne suggerite.</span><span class="sxs-lookup"><span data-stu-id="98834-109">In addition, parameters help them better manage the suggested deliveries.</span></span> <span data-ttu-id="98834-110">Poiché il tempo di trasporto può influire sulle date di consegna, gli addetti agli ordini cliente possono esaminare le varie opzioni di trasporto che i vettori offrono.</span><span class="sxs-lookup"><span data-stu-id="98834-110">Because transport time can affect delivery dates, sales order takers can explore the various transportation choices that carriers offer.</span></span> <span data-ttu-id="98834-111">Per ogni suggerimento vengono mostrate informazioni dettagliate, gli addetti agli ordini cliente possono quindi prendere decisioni informate direttamente nella pagina **Alternative di consegna**.</span><span class="sxs-lookup"><span data-stu-id="98834-111">Because detailed information is shown for each suggestion, order takers can make informed decisions directly from the **Delivery alternatives** page.</span></span>

## <a name="open-the-delivery-alternatives-page"></a><span data-ttu-id="98834-112">Aprire la pagina di Alternative di consegna</span><span class="sxs-lookup"><span data-stu-id="98834-112">Open the Delivery alternatives page</span></span>

<span data-ttu-id="98834-113">È possibile aprire la pagina **Alternative di consegna** della riga ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="98834-113">You can open the **Delivery alternatives** page from the sales order line.</span></span>

1. <span data-ttu-id="98834-114">Selezionare **Prodotti e fornitura \> Alternative di consegna**.</span><span class="sxs-lookup"><span data-stu-id="98834-114">Select **Products and supply \> Delivery alternatives**.</span></span>
1. <span data-ttu-id="98834-115">Selezionare **Dettagli riga \> Consegna \> Alternative di consegna**.</span><span class="sxs-lookup"><span data-stu-id="98834-115">Select **Line details \> Delivery \> Delivery alternatives.**</span></span>

<span data-ttu-id="98834-116">È anche possibile aprire la pagina **Alternative di consegna** aprendo l'area di lavoro **Elaborazione e richiesta di informazioni ordini cliente** e selezionando **Ordini e preferiti \> Righe ordine ritardate \> Alternative di consegna** **Nota:** è possibile aprire la pagina **Alternative di consegna** solo se entrambe le seguenti condizioni sono state soddisfatte:</span><span class="sxs-lookup"><span data-stu-id="98834-116">You can also open the **Delivery alternatives** page by opening the **Sales order processing and inquiry** workspace, and then selecting **Orders and favorites \> Delayed order lines \> Delivery alternatives** **Note:** You can open the **Delivery alternatives** page only if both the following conditions are met:</span></span>

- <span data-ttu-id="98834-117">Tutte le informazioni obbligatorie per la riga di vendita sono state specificate.</span><span class="sxs-lookup"><span data-stu-id="98834-117">All mandatory sales line information is filled in.</span></span>
- <span data-ttu-id="98834-118">Il campo **Controllo data di consegna** è impostato su un valore deverso da **Nessuno**.</span><span class="sxs-lookup"><span data-stu-id="98834-118">The **Delivery date control** field is set to a value other than **None**.</span></span>

## <a name="delivery-date-control-methods"></a><span data-ttu-id="98834-119">Metodi di controllo data di consegna</span><span class="sxs-lookup"><span data-stu-id="98834-119">Delivery date control methods</span></span>

<span data-ttu-id="98834-120">Il metodo di controllo della data di consegna determina le modalità secondo cui il sistema stabilisce le date di consegna, calcola le alternative di consegna e stabilisce le informazioni da visualizzare.</span><span class="sxs-lookup"><span data-stu-id="98834-120">The delivery date control method determines how the system establishes delivery dates, how delivery alternatives are calculated, and what information is shown.</span></span> <span data-ttu-id="98834-121">Si noti che il controllo della data di consegna si basa sui calendari.</span><span class="sxs-lookup"><span data-stu-id="98834-121">Note that delivery date control takes calendars into consideration.</span></span> <span data-ttu-id="98834-122">Di conseguenza, i calendari seguenti possono influire sulla data di ricezione suggerita: calendario di magazzino, calendario di spedizione, calendario del fornitore e calendario del cliente.</span><span class="sxs-lookup"><span data-stu-id="98834-122">Therefore, the following calendars can affect the suggested receipt date: Warehouse calendar, Transport calendar, Vendor calendar, and Customer calendar.</span></span> <span data-ttu-id="98834-123">Nella seguente tabella viene descritto ogni metodo per il controllo della data di consegna.</span><span class="sxs-lookup"><span data-stu-id="98834-123">The following table describes each method for delivery date control.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><span data-ttu-id="98834-124"><strong>Metodo</strong></span><span class="sxs-lookup"><span data-stu-id="98834-124"><strong>Method</strong></span></span></td>
<td><span data-ttu-id="98834-125"><strong>Descrizione</strong></span><span class="sxs-lookup"><span data-stu-id="98834-125"><strong>Description</strong></span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="98834-126"><strong>Nessuna priorità</strong></span><span class="sxs-lookup"><span data-stu-id="98834-126"><strong>None</strong></span></span></td>
<td><ul>
<li><span data-ttu-id="98834-127">Le alternative di consegna per le righe di vendita non sono supportate.</span><span class="sxs-lookup"><span data-stu-id="98834-127">Delivery alternatives for sales lines aren't supported.</span></span> <span data-ttu-id="98834-128">Questa opzione disattiva il controllo della data di consegna.</span><span class="sxs-lookup"><span data-stu-id="98834-128">This option turns off delivery date control.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="98834-129"><strong>Lead time di vendita</strong></span><span class="sxs-lookup"><span data-stu-id="98834-129"><strong>Sales lead time</strong></span></span></td>
<td><ul>
<li><span data-ttu-id="98834-130">Le alternative di consegna vengono calcolate in base al lead time di vendita predefinito.</span><span class="sxs-lookup"><span data-stu-id="98834-130">Delivery alternatives are calculated based on the predefined sales lead time.</span></span> <span data-ttu-id="98834-131">I giorni di trasporto vengono calcolati in base alla modalità di consegna.</span><span class="sxs-lookup"><span data-stu-id="98834-131">The transport days are calculated based on the mode of delivery.</span></span></li>
<li><span data-ttu-id="98834-132">Le alternative di consegna includono i magazzini con scorte disponibili e ordini di domanda/fornitura.</span><span class="sxs-lookup"><span data-stu-id="98834-132">Delivery alternatives include warehouses that have on-hand inventory, and supply/demand orders.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="98834-133"><strong>ATP</strong></span><span class="sxs-lookup"><span data-stu-id="98834-133"><strong>ATP</strong></span></span></td>
<td><ul>
<li><span data-ttu-id="98834-134">Le alternative di consegna vengono calcolate in base a logica available-to-promise (ATP).</span><span class="sxs-lookup"><span data-stu-id="98834-134">Delivery alternatives are calculated based on available to promise (ATP) logic.</span></span> <span data-ttu-id="98834-135">Vengono considerate la disponibilità corrente e la disponibilità futura.</span><span class="sxs-lookup"><span data-stu-id="98834-135">The current availability and expected future availability are considered.</span></span> <span data-ttu-id="98834-136">I giorni di trasporto vengono calcolati in base alla modalità di consegna.</span><span class="sxs-lookup"><span data-stu-id="98834-136">The transport days are calculated based on the mode of delivery.</span></span></li>
<li><span data-ttu-id="98834-137">Le alternative di consegna includono i magazzini con scorte disponibili e ordini di domanda/fornitura.</span><span class="sxs-lookup"><span data-stu-id="98834-137">Delivery alternatives include warehouses that have on-hand inventory, and supply/demand orders.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="98834-138"><strong>ATP + margine su uscita magazzino</strong></span><span class="sxs-lookup"><span data-stu-id="98834-138"><strong>ATP + Issue margin</strong></span></span></td>
<td><ul>
<li><span data-ttu-id="98834-139">Le alternative di consegna vengono calcolate come per il metodo di calcolo ATP, ma il margine su uscita da magazzino viene incluso nel calcolo.</span><span class="sxs-lookup"><span data-stu-id="98834-139">Delivery alternatives are calculated as for the ATP method, but the issue margin is included in the calculation.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="98834-140"><strong>CTP</strong></span><span class="sxs-lookup"><span data-stu-id="98834-140"><strong>CTP</strong></span></span></td>
<td><ul>
<li><span data-ttu-id="98834-141">Le alternative di consegna vengono calcolate in base a logica capable-to-promise (CTP).</span><span class="sxs-lookup"><span data-stu-id="98834-141">Delivery alternatives are calculated based on the capable to promise (CTP) logic.</span></span> <span data-ttu-id="98834-142">L'esplosione MRP viene utilizzata per determinare la disponibilità.</span><span class="sxs-lookup"><span data-stu-id="98834-142">MRP explosion is used to determine availability.</span></span> <span data-ttu-id="98834-143">Tenere presente che, al minimo, CTP imposta le date di consegna al lead time di vendita.</span><span class="sxs-lookup"><span data-stu-id="98834-143">Note that, at a minimum, CTP offsets delivery dates to the sales lead time.</span></span> <span data-ttu-id="98834-144">I giorni di trasporto vengono calcolati in base alla modalità di consegna.</span><span class="sxs-lookup"><span data-stu-id="98834-144">The transport days are calculated based on the mode of delivery.</span></span></li>
<li><span data-ttu-id="98834-145">Le date di consegna alternative includono suggerimenti per i magazzini seguenti:</span><span class="sxs-lookup"><span data-stu-id="98834-145">Delivery alternatives include suggestions for the following warehouses:</span></span>
<ul>
<li><span data-ttu-id="98834-146">Magazzino corrente</span><span class="sxs-lookup"><span data-stu-id="98834-146">Current warehouse</span></span></li>
<li><span data-ttu-id="98834-147">Magazzino predefinito</span><span class="sxs-lookup"><span data-stu-id="98834-147">Default warehouse</span></span></li>
<li><span data-ttu-id="98834-148">Tutti i magazzini con scorte disponibili</span><span class="sxs-lookup"><span data-stu-id="98834-148">All warehouses that have available on-hand inventory</span></span></li>
<li><span data-ttu-id="98834-149">Tutti i magazzini con ordini di fornitura</span><span class="sxs-lookup"><span data-stu-id="98834-149">All warehouses that have supply orders</span></span></li>
<li><span data-ttu-id="98834-150">Tutti i magazzini con versioni attive della distinta base (BOM)</span><span class="sxs-lookup"><span data-stu-id="98834-150">All warehouses that have active bill of materials (BOM) versions</span></span></li>
</ul></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="view-information-about-delivery-alternatives"></a><span data-ttu-id="98834-151">Visualizzare informazioni sulle alternative di consegna</span><span class="sxs-lookup"><span data-stu-id="98834-151">View information about delivery alternatives</span></span>

<span data-ttu-id="98834-152">In questa sezione vengono descritte le informazioni sulle alternative di consegna disponibili in ogni Scheda dettaglio della pagina **Alternative di consegna**.</span><span class="sxs-lookup"><span data-stu-id="98834-152">This section describes the information about delivery alternatives that is available on each FastTab of the **Delivery alternatives** page.</span></span>

### <a name="the-product-fasttab"></a><span data-ttu-id="98834-153">Scheda dettaglio Prodotto</span><span class="sxs-lookup"><span data-stu-id="98834-153">The Product FastTab</span></span>

<span data-ttu-id="98834-154">In questa Scheda dettaglio viene visualizzato un riepilogo dei prodotti e i dettagli della riga di vendita corrente.</span><span class="sxs-lookup"><span data-stu-id="98834-154">This FastTab shows a summary of the product and details of the current sales line.</span></span>

### <a name="the-delivery-alternatives-fasttab"></a><span data-ttu-id="98834-155">Scheda dettaglio Alternative di consegna</span><span class="sxs-lookup"><span data-stu-id="98834-155">The Delivery alternatives FastTab</span></span>

<span data-ttu-id="98834-156">La Scheda dettaglio consente di visualizzare un elenco di alternative di consegna ordinate per data di ricezione.</span><span class="sxs-lookup"><span data-stu-id="98834-156">This FastTab shows a list of delivery alternatives that is sorted by receipt date.</span></span> <span data-ttu-id="98834-157">Sopra l'elenco, è possibile selezionare le opzione in base alla quale visualizzare i suggerimenti.</span><span class="sxs-lookup"><span data-stu-id="98834-157">Above the list, you can select which options to base the suggestions on.</span></span> <span data-ttu-id="98834-158">È inoltre possibile selezionare la modalità di consegna, che determina i giorni di spedizione.</span><span class="sxs-lookup"><span data-stu-id="98834-158">You can also select the mode of delivery, which determines the transport days.</span></span> <span data-ttu-id="98834-159">Sono disponibili le seguenti opzioni:</span><span class="sxs-lookup"><span data-stu-id="98834-159">The following options are available:</span></span>

- <span data-ttu-id="98834-160">**Includi altre varianti prodotto** - Questa opzione è disponibile per i prodotti con varianti prodotto.</span><span class="sxs-lookup"><span data-stu-id="98834-160">**Include other product variants** - This option is available for products that have product variants.</span></span> <span data-ttu-id="98834-161">verranno incluse le alternative di consegna per altre varianti prodotto.</span><span class="sxs-lookup"><span data-stu-id="98834-161">It will include delivery alternatives for other variants of the product.</span></span> <span data-ttu-id="98834-162">Questa opzione non è disponibile per CTP.</span><span class="sxs-lookup"><span data-stu-id="98834-162">This option isn't available for CTP.</span></span>
- <span data-ttu-id="98834-163">**Includi quantità parziale** - Per impostazione predefinita, vengono inclusi solo i suggerimenti che soddisfano l'intera quantità della riga cliente.</span><span class="sxs-lookup"><span data-stu-id="98834-163">**Include partial quantity** - By default, only suggestions that fulfill the full quantity of the sales line are included.</span></span> <span data-ttu-id="98834-164">Selezionare questa opzione per includere i suggerimenti che soddisfano solo parzialmente la riga di vendita.</span><span class="sxs-lookup"><span data-stu-id="98834-164">Select this option to include suggestions that only partially fulfill the order line.</span></span> <span data-ttu-id="98834-165">Questa opzione è utile quando il cliente richiede una data più vicina e accetta la consegna parziale.</span><span class="sxs-lookup"><span data-stu-id="98834-165">This option is useful when the customer requests an earlier delivery date and accepts partial delivery.</span></span>
- <span data-ttu-id="98834-166">**Includi date successive** - Per impostazione predefinita, vengono mostrati solo i suggerimenti migliori (precedenti) rispetto alle date correnti nella riga di vendita.</span><span class="sxs-lookup"><span data-stu-id="98834-166">**Include later dates** - By default, only suggestions that are better (earlier) than the current dates on the sales line are shown.</span></span> <span data-ttu-id="98834-167">Selezionare questa opzione per includere le dati successive.</span><span class="sxs-lookup"><span data-stu-id="98834-167">Select this option to include later dates.</span></span> <span data-ttu-id="98834-168">Questa opzione può risultare utile nelle situazioni in cui parametri diversi dalla data hanno priorità.</span><span class="sxs-lookup"><span data-stu-id="98834-168">This option can be useful in situations where parameters other than the date have priority.</span></span> <span data-ttu-id="98834-169">Ad esempio, un fornitore o un magazzino specifico può essere preferito.</span><span class="sxs-lookup"><span data-stu-id="98834-169">For example, a specific vendor or warehouse might be preferred.</span></span>
- <span data-ttu-id="98834-170">**Modalità di consegna** - Selezionare la modalità di consegna preferita per ottimizzare il tempo e costo di trasporto.</span><span class="sxs-lookup"><span data-stu-id="98834-170">**Mode of delivery** - Select the preferred mode of delivery to optimize transport time and cost.</span></span> <span data-ttu-id="98834-171">L'effetto sarà immediatamente visualizzato nelle alternative di consegna suggerite.</span><span class="sxs-lookup"><span data-stu-id="98834-171">You will immediately see the effect on the suggested delivery alternatives.</span></span> <span data-ttu-id="98834-172">Di conseguenza, è facile confrontare le alternative.</span><span class="sxs-lookup"><span data-stu-id="98834-172">Therefore, it's easy to compare the alternatives.</span></span>
- <span data-ttu-id="98834-173">**Includi approvvigionamento** - Quando è selezionato l'approvvigionamento, le alternative di consegna suggerite includono opzioni relative sia ai fornitori esterni che ad altre società dell'impresa (interaziendale).</span><span class="sxs-lookup"><span data-stu-id="98834-173">**Include procurement** - When procurement is selected, the suggested delivery alternatives include options to procure from both external vendors and other companies in the enterprise (intercompany).</span></span> <span data-ttu-id="98834-174">L'opzione **Includi approvvigionamento** è supportata per il controllo delle date di consegna ATP e ATP + margine su uscita magazzino.</span><span class="sxs-lookup"><span data-stu-id="98834-174">The **Include procurement** option is supported for ATP and ATP + Issue margin delivery date control.</span></span> <span data-ttu-id="98834-175">Vengono incluse le opzioni di approvvigionamento del fornitore acquisti predefinito per il prodotto e di tutti i fornitori approvati per il prodotto.</span><span class="sxs-lookup"><span data-stu-id="98834-175">Procurement options from the default purchase vendor for the product and all approved vendors for the product are included.</span></span>
- <span data-ttu-id="98834-176">Per i fornitori esterni, il calcolo è basato sul lead time di acquisto.</span><span class="sxs-lookup"><span data-stu-id="98834-176">For external vendors, the calculation is based on the purchase lead time.</span></span>
- <span data-ttu-id="98834-177">Per gli ordini interaziendali, il calcolo prende in considerazione i prodotti disponibili dalla società di approvvigionamento, in base al controllo della data di consegna nella società di approvvigionamento.</span><span class="sxs-lookup"><span data-stu-id="98834-177">For intercompany, the calculation considers what is available from the sourcing company, based on delivery date control in the sourcing company.</span></span>
- <span data-ttu-id="98834-178">**Tipo di consegna** (Rilevante per l'approvvigionamento)</span><span class="sxs-lookup"><span data-stu-id="98834-178">**Delivery type** (Relevant for procurement)</span></span>
  - <span data-ttu-id="98834-179">**Scorte** - I prodotti vengono spediti dal magazzino di approvvigionamento al sito/magazzino nella riga di vendita.</span><span class="sxs-lookup"><span data-stu-id="98834-179">**Stock** - Products are shipped from the sourcing warehouse to the site/warehouse on the sales line.</span></span> <span data-ttu-id="98834-180">Vengono quindi spediti da tale magazzino al cliente.</span><span class="sxs-lookup"><span data-stu-id="98834-180">They are then shipped from that warehouse to the customer.</span></span>
  - <span data-ttu-id="98834-181">**Consegna diretta** - I prodotti devono essere inviati direttamente dal magazzino di approvvigionamento al cliente.</span><span class="sxs-lookup"><span data-stu-id="98834-181">**Direct delivery** - Products are shipped directly from the sourcing warehouse to the customer.</span></span>

### <a name="the-availability-information-fasttab"></a><span data-ttu-id="98834-182">Scheda dettaglio Informazioni sulla disponibilità</span><span class="sxs-lookup"><span data-stu-id="98834-182">The Availability information FastTab</span></span>

<span data-ttu-id="98834-183">Le informazioni contenute in questa Scheda dettaglio sono correlate alla riga alternativa di consegna selezionata.</span><span class="sxs-lookup"><span data-stu-id="98834-183">Information on this FastTab is related to the delivery alternative line that is selected.</span></span> <span data-ttu-id="98834-184">Vengono indicate le seguenti informazioni, a seconda del controllo della data di consegna per la riga ordine:</span><span class="sxs-lookup"><span data-stu-id="98834-184">The following information is shown, depending on the delivery date control for the sales line:</span></span>

- <span data-ttu-id="98834-185">**Lead time di vendita**</span><span class="sxs-lookup"><span data-stu-id="98834-185">**Sales lead time**</span></span>
  - <span data-ttu-id="98834-186">**Disponibile oggi** - Mostra le scorte fisiche attualmente disponibili, la qtà fisica prenotata e la qtà fisica disponibile.</span><span class="sxs-lookup"><span data-stu-id="98834-186">**Available today** - Show the current physical on-hand, physical reserved, and available physical inventory.</span></span>
  - <span data-ttu-id="98834-187">**Parametri** - Mostra il lead time di vendita e l'unità di magazzino.</span><span class="sxs-lookup"><span data-stu-id="98834-187">**Parameters** - Show the inventory unit and sales lead time.</span></span>

- <span data-ttu-id="98834-188">**ATP e ATP + Margine su uscita da magazzino**</span><span class="sxs-lookup"><span data-stu-id="98834-188">**ATP and ATP + Issue margin**</span></span>
  - <span data-ttu-id="98834-189">**Disponibile oggi** - Mostra le scorte fisiche attualmente disponibili, la qtà fisica prenotata e la qtà fisica disponibile.</span><span class="sxs-lookup"><span data-stu-id="98834-189">**Available today** - Show the current physical on-hand, physical reserved, and available physical inventory.</span></span>
  - <span data-ttu-id="98834-190">**Parametri** - Mostra il lead time di vendita e l'unità di magazzino.</span><span class="sxs-lookup"><span data-stu-id="98834-190">**Parameters** - Show the inventory unit and sales lead time.</span></span>
  - <span data-ttu-id="98834-191">**Disponibilità futura** - Mostra una rappresentazione grafica della disponibilità corrente e futura per il sito e il magazzino selezionati in **Alternative di consegna**.</span><span class="sxs-lookup"><span data-stu-id="98834-191">**Future availability** - Show a graphical representation of current and future availability for the selected site and warehouse under **Delivery alternatives**.</span></span> <span data-ttu-id="98834-192">È possibile selezionare le colonne del grafico per visualizzare informazioni più dettagliate sulla futura disponibilità del prodotto.</span><span class="sxs-lookup"><span data-stu-id="98834-192">You can select the chart columns to see more detailed information about the future availability of the product.</span></span> <span data-ttu-id="98834-193">Il cursore mostra un elenco degli ordini di fornitura rilevanti e della domanda in un intervallo temporale ATP.</span><span class="sxs-lookup"><span data-stu-id="98834-193">The slider shows a list of relevant demand and supply orders within the ATP time fence.</span></span>

- <span data-ttu-id="98834-194">**CTP**</span><span class="sxs-lookup"><span data-stu-id="98834-194">**CTP**</span></span>
  - <span data-ttu-id="98834-195">**Disponibile oggi** - Mostra le scorte fisiche attualmente disponibili, la qtà fisica prenotata e la qtà fisica disponibile.</span><span class="sxs-lookup"><span data-stu-id="98834-195">**Available today** - Show the current physical on-hand, physical reserved, and available physical inventory.</span></span>
  - <span data-ttu-id="98834-196">**Parametri** - Mostra il lead time di vendita e l'unità di magazzino.</span><span class="sxs-lookup"><span data-stu-id="98834-196">**Parameters** - Show the inventory unit and sales lead time.</span></span>
  - <span data-ttu-id="98834-197">**Esplosione** - Mostra un'esplosione della fornitura per l'alternativa di consegna selezionata.</span><span class="sxs-lookup"><span data-stu-id="98834-197">**Explosion** - Show a supply explosion of the selected delivery alternative.</span></span> <span data-ttu-id="98834-198">È possibile utilizzare le **impostazioni** per modificare i campi e le dimensioni inventariali che vengono visualizzati nell'esplosione.</span><span class="sxs-lookup"><span data-stu-id="98834-198">You can use **Setup** to change the fields and inventory dimensions that are shown in the explosion.</span></span>

### <a name="the-impact-of-selected-alternative-fasttab"></a><span data-ttu-id="98834-199">Scheda dettaglio Impatto dell'alternativa selezionata</span><span class="sxs-lookup"><span data-stu-id="98834-199">The Impact of selected alternative FastTab</span></span>

<span data-ttu-id="98834-200">Questa Scheda dettaglio evidenzia l'impatto dell'alternativa di consegna selezionata.</span><span class="sxs-lookup"><span data-stu-id="98834-200">This FastTab highlights the impact of the selected delivery alternative.</span></span> <span data-ttu-id="98834-201">Se si seleziona **OK**, la riga di vendita viene aggiornata con i valori evidenziati nelle colonne SELEZIONATE.</span><span class="sxs-lookup"><span data-stu-id="98834-201">If you select **OK**, the sales line is updated with the highlighted values in the SELECTED columns.</span></span> <span data-ttu-id="98834-202">Si noti che, se la quantità dell'alternativa di consegna selezionata è inferiore alla quantità delle righe di vendita, viene creata una programmazione consegna e la riga ordine viene divisa in due righe: una riga per la quantità selezionata e una riga per la quantità rimanente.</span><span class="sxs-lookup"><span data-stu-id="98834-202">Note that, if the quantity on the selected delivery alternative is less than quantity on the sales line, a delivery schedule is created, and the order line is split into two lines: one line for the selected quantity and one line for the remaining quantity.</span></span> <span data-ttu-id="98834-203">È inoltre possibile aggiornare la riga commerciale in modo che corrisponda alle righe di programmazione che influiscono sulla valutazione.</span><span class="sxs-lookup"><span data-stu-id="98834-203">You can also update the commercial line so that it matches the schedule lines and affects the pricing.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="98834-204">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="98834-204">Additional resources</span></span>

[<span data-ttu-id="98834-205">Promesse ordine</span><span class="sxs-lookup"><span data-stu-id="98834-205">Order promising</span></span>](delivery-dates-available-promise-calculations.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]