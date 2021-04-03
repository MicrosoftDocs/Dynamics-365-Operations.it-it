---
title: Modulo Costo sbarcato
description: Il modulo Costo sbarcato consente alle aziende di semplificare le operazioni di spedizione in entrata fornendo agli utenti un controllo finanziario e logistico completo sulle merci importate, dal produttore al magazzino.
author: sherry-zheng
manager: tfehr
ms.date: 12/07/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-12-07
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: 9d04c377080a1d301efb771b98c249f610a3289d
ms.sourcegitcommit: 2b4809e60974e72df9476ffd62706b1bfc8da4a7
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/04/2021
ms.locfileid: "5500334"
---
# <a name="landed-cost-module"></a><span data-ttu-id="14e51-103">Modulo Costo sbarcato</span><span class="sxs-lookup"><span data-stu-id="14e51-103">Landed cost module</span></span>

[!include [banner](../../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="14e51-104">Il modulo **Costo sbarcato** consente alle aziende di semplificare le operazioni di spedizione in entrata fornendo agli utenti un controllo finanziario e logistico completo sulle merci importate, dal produttore al magazzino.</span><span class="sxs-lookup"><span data-stu-id="14e51-104">The **Landed cost** module helps businesses streamline inbound shipping operations by giving users complete financial and logistical control over imported freight, from the manufacturer to the warehouse.</span></span> <span data-ttu-id="14e51-105">Per le merci importate, i costi sbarcati possono rappresentare il 40% o più del costo totale di ogni articolo importato.</span><span class="sxs-lookup"><span data-stu-id="14e51-105">For imported goods, landed costs can account for 40 percent or more of the total cost of each imported item.</span></span> <span data-ttu-id="14e51-106">Pertanto, la sfida è fornire stime accurate per i costi sbarcati.</span><span class="sxs-lookup"><span data-stu-id="14e51-106">Therefore, the challenge is to provide accurate estimates for landed costs.</span></span>

<span data-ttu-id="14e51-107">Le aziende possono utilizzare Costo sbarcato per completare le seguenti attività:</span><span class="sxs-lookup"><span data-stu-id="14e51-107">Businesses can use Landed cost to complete the following tasks:</span></span>

- <span data-ttu-id="14e51-108">Stimare costi sbarcati al momento della creazione del viaggio.</span><span class="sxs-lookup"><span data-stu-id="14e51-108">Estimate landed costs at the time of voyage creation.</span></span>
- <span data-ttu-id="14e51-109">Ripartire costi sbarcati su più articoli e ordini fornitore o ordini di trasferimento in un unico viaggio.</span><span class="sxs-lookup"><span data-stu-id="14e51-109">Apportion landed costs to multiple items and purchase orders or transfer orders in a single voyage.</span></span>
- <span data-ttu-id="14e51-110">Supportare il trasferimento di merci tra luoghi fisici riconoscendo i costi sbarcati.</span><span class="sxs-lookup"><span data-stu-id="14e51-110">Support the transfer of goods between physical locations by recognizing landed costs.</span></span>
- <span data-ttu-id="14e51-111">Riconoscere gli accumuli per le merci in transito.</span><span class="sxs-lookup"><span data-stu-id="14e51-111">Recognize accruals for goods in transit.</span></span>

<span data-ttu-id="14e51-112">Il modulo Costo sbarcato fornisce stime accurate e tempestive dei costi sbarcati generali.</span><span class="sxs-lookup"><span data-stu-id="14e51-112">Landed cost provides accurate and timely cost estimates for overhead landed costs.</span></span> <span data-ttu-id="14e51-113">Allo stesso tempo, fornisce una maggiore visibilità finanziaria e logistica nella supply chain estesa.</span><span class="sxs-lookup"><span data-stu-id="14e51-113">At the same time, it provides increased financial and logistical visibility into the extended supply chain.</span></span> <span data-ttu-id="14e51-114">Aiuta inoltre a ridurre le operazioni di gestione della determinazione dei costi e degli errori di determinazione dei costi.</span><span class="sxs-lookup"><span data-stu-id="14e51-114">It also helps reduce the administration of costing and costing errors.</span></span>

## <a name="highlights"></a><span data-ttu-id="14e51-115">Caratteristiche principali</span><span class="sxs-lookup"><span data-stu-id="14e51-115">Highlights</span></span>

### <a name="voyages"></a><span data-ttu-id="14e51-116">Viaggi</span><span class="sxs-lookup"><span data-stu-id="14e51-116">Voyages</span></span>

<span data-ttu-id="14e51-117">In Costo sbarcato, un viaggio è un movimento distinto da un'ubicazione in uscita, attraverso un insieme specifico di destinazioni in un periodo specificato, a un'ubicazione di magazzino in entrata specificata.</span><span class="sxs-lookup"><span data-stu-id="14e51-117">In Landed cost, a voyage is a distinct movement from an outbound location, through a specific set of destinations over a specified period, to a specified inbound warehouse location.</span></span> <span data-ttu-id="14e51-118">Gli ordini fornitore e le righe d'ordine possono essere aggiunti a un singolo contenitore o più contenitori per un viaggio e i costi verranno allocati correttamente alla riga articolo.</span><span class="sxs-lookup"><span data-stu-id="14e51-118">Purchase orders and order lines can be added to either a single container or multiple containers for a voyage, and the costs will be correctly allocated back to the item line.</span></span> <span data-ttu-id="14e51-119">Gli ordini e le righe di ordine possono anche essere aggiunti tra persone giuridiche per un singolo viaggio.</span><span class="sxs-lookup"><span data-stu-id="14e51-119">Orders and order lines can also be added across legal entities for a single voyage.</span></span>

### <a name="item-ownership"></a><span data-ttu-id="14e51-120">Proprietà degli articoli</span><span class="sxs-lookup"><span data-stu-id="14e51-120">Item ownership</span></span>

<span data-ttu-id="14e51-121">In Microsoft Dynamics 365 Supply Chain Management, le merci vengono generalmente ricevute al magazzino di destinazione e quindi fatturate.</span><span class="sxs-lookup"><span data-stu-id="14e51-121">In Microsoft Dynamics 365 Supply Chain Management, goods are typically received at the warehouse destination and then invoiced.</span></span> <span data-ttu-id="14e51-122">Tuttavia, la maggior parte degli accordi commerciali internazionali prevede che un'azienda assuma la proprietà delle merci dal momento in cui queste lasciano il porto originale, prima che siano state ricevute fisicamente.</span><span class="sxs-lookup"><span data-stu-id="14e51-122">However, under most international trade agreements, a business takes ownership of goods from the time when they leave the original port, before they have been physically received.</span></span> <span data-ttu-id="14e51-123">Costo sbarcato consente alle aziende di fatturare le merci prima che siano state ricevute fisicamente.</span><span class="sxs-lookup"><span data-stu-id="14e51-123">Landed cost enables businesses to invoice goods before they have been physically received.</span></span> <span data-ttu-id="14e51-124">Questo concetto è noto come ordine di merci in transito.</span><span class="sxs-lookup"><span data-stu-id="14e51-124">This concept is known as a goods in transit order.</span></span> <span data-ttu-id="14e51-125">Crea un nuovo tipo di ordine per gestire il ricevimento delle merci dopo che l'ordine fornitore originale è stato fatturato.</span><span class="sxs-lookup"><span data-stu-id="14e51-125">It creates a new type of order to manage the receipt of goods after the original purchase order has been invoiced.</span></span>

### <a name="costs"></a><span data-ttu-id="14e51-126">Costi</span><span class="sxs-lookup"><span data-stu-id="14e51-126">Costs</span></span>

<span data-ttu-id="14e51-127">Quando si crea un viaggio in Costo sbarcato, è possibile aggiungervi automaticamente i costi.</span><span class="sxs-lookup"><span data-stu-id="14e51-127">When you create a voyage in Landed cost, costs can automatically be added to it.</span></span> <span data-ttu-id="14e51-128">Questi costi sono impostati in Costo sbarcato e sono disponibili varie basi di costo e opzioni relative ai costi.</span><span class="sxs-lookup"><span data-stu-id="14e51-128">These costs are set up in Landed cost, and various cost options and cost bases are available for them.</span></span> <span data-ttu-id="14e51-129">Ogni costo può essere impostato per diversi livelli di un viaggio e ripartito a livello di articolo tramite regole di ripartizione che supportano quantità, volume, peso, importo e divisori volumetrici definiti.</span><span class="sxs-lookup"><span data-stu-id="14e51-129">Each cost can be set up for different levels of a voyage and apportioned to the item level through apportionment rules that support quantity, volume, weight, amount, and defined volumetric divisors.</span></span> <span data-ttu-id="14e51-130">Questi costi stimati forniscono una stima accurata di tutti i costi per un viaggio.</span><span class="sxs-lookup"><span data-stu-id="14e51-130">These estimated costs provide an accurate estimate of all costs for a voyage.</span></span>

<span data-ttu-id="14e51-131">Costo sbarcato esegue quindi un accumulo/registrazione preliminare dei costi sbarcati stimati per garantire un calcolo accurato dei costi stimati al momento della creazione del viaggio.</span><span class="sxs-lookup"><span data-stu-id="14e51-131">Landed cost then runs a preliminary posting/accrual of the estimated landed costs to ensure that an accurate calculation of estimated costs is provided at the time of voyage creation.</span></span> <span data-ttu-id="14e51-132">Poiché questi costi automatici vengono fatturati, i costi stimati vengono stornati e sostituiti dai costi effettivi, in base alle fatture di costi.</span><span class="sxs-lookup"><span data-stu-id="14e51-132">As these automatic costs are invoiced, the estimated costs are reversed and replaced by the actual costs, based on cost invoices.</span></span>

<span data-ttu-id="14e51-133">I costi effettivi sono costi stimati stornati che vengono registrati al momento della fatturazione dei costi utilizzando conti di compensazione impostati per ogni tipo di costo (ad esempio, dazi, trasporto e assicurazione).</span><span class="sxs-lookup"><span data-stu-id="14e51-133">Actual costs are reverse estimated costs that are posted at the time of cost invoicing by using clearing accounts that are set up for each type of cost (for example, duty, freight, and insurance).</span></span> <span data-ttu-id="14e51-134">Queste registrazioni seguono il comportamento di registrazione associato all'articolo specifico.</span><span class="sxs-lookup"><span data-stu-id="14e51-134">These postings follow the posting behavior that is associated with the specific item.</span></span> <span data-ttu-id="14e51-135">Aggiornano automaticamente la registrazione dell'inventario, indipendentemente dal fatto che il tipo di registrazione sia first in, first out (FIFO), last in, first out (LIFO), media ponderata mobile o media mobile.</span><span class="sxs-lookup"><span data-stu-id="14e51-135">They automatically update inventory posting, regardless of whether the posting type is first in, first out (FIFO), last in, first out (LIFO), moving weighted average, or moving average.</span></span> <span data-ttu-id="14e51-136">Sono supportati tutti i tipi di registrazione del gruppo di modelli inventariali.</span><span class="sxs-lookup"><span data-stu-id="14e51-136">All inventory model group posting types are supported.</span></span> <span data-ttu-id="14e51-137">Per la registrazione della media mobile e dei costi standard, sono disponibili conti scostamento di prezzo di acquisto per registrare le differenze tra i costi stimati e quelli effettivi.</span><span class="sxs-lookup"><span data-stu-id="14e51-137">For moving average and standard cost posting, purchase price variance accounts are available to post the differences between estimated costs and actual costs.</span></span>

### <a name="item-and-order-tracking"></a><span data-ttu-id="14e51-138">Tracciabilità di articoli e ordini</span><span class="sxs-lookup"><span data-stu-id="14e51-138">Item and order tracking</span></span>

<span data-ttu-id="14e51-139">Quando un viaggio passa dall'ubicazione di partenza di origine al magazzino di destinazione finale, gli utenti possono aggiornare ogni fase, o *scalo*, del relativo percorso come necessario.</span><span class="sxs-lookup"><span data-stu-id="14e51-139">As a voyage moves from the originating outbound location to the final destination warehouse, users can update each step, or *leg*, of its journey as required.</span></span> <span data-ttu-id="14e51-140">Per ogni scalo, vengono identificati un lead time e uno stato della spedizione.</span><span class="sxs-lookup"><span data-stu-id="14e51-140">For each leg, a lead time and a shipment status are identified.</span></span> <span data-ttu-id="14e51-141">Vengono inoltre identificate le date di consegna confermate per il passaggio allo scalo successivo del percorso.</span><span class="sxs-lookup"><span data-stu-id="14e51-141">Confirmed delivery dates for movement to the next leg of the journey are also identified.</span></span> <span data-ttu-id="14e51-142">Insieme, queste date di consegna forniscono una data di consegna stimata delle merci al magazzino in entrata.</span><span class="sxs-lookup"><span data-stu-id="14e51-142">Together, these delivery dates provide an estimated delivery date of the goods to the inbound warehouse.</span></span> <span data-ttu-id="14e51-143">Gli utenti possono modificare queste date di consegna.</span><span class="sxs-lookup"><span data-stu-id="14e51-143">Users can change these delivery dates.</span></span> <span data-ttu-id="14e51-144">In questo caso, la data di consegna stimata delle merci viene quindi aggiornata automaticamente, in base ai lead time e agli scali del percorso.</span><span class="sxs-lookup"><span data-stu-id="14e51-144">In this case, the estimated delivery date of the goods is then automatically updated, based on the lead times and legs of the journey.</span></span> <span data-ttu-id="14e51-145">La visibilità delle merci in transito per viaggio e imbarcazione è disponibile per ogni contenitore prima del ricevimento della merce.</span><span class="sxs-lookup"><span data-stu-id="14e51-145">Visibility into goods in transit by voyage and vessel is available on a per-container basis before receipt of the goods.</span></span> <span data-ttu-id="14e51-146">Poiché le date vengono aggiornate su ogni riga dell'ordine fornitore, le aziende hanno un maggiore controllo sulla logistica e sulla pianificazione del magazzino.</span><span class="sxs-lookup"><span data-stu-id="14e51-146">Because the dates are updated on each purchase order line, businesses have more control over logistics and warehouse planning.</span></span>

## <a name="landed-cost-concepts"></a><span data-ttu-id="14e51-147">Concetti di Costo sbarcato</span><span class="sxs-lookup"><span data-stu-id="14e51-147">Landed cost concepts</span></span>

<span data-ttu-id="14e51-148">La tabella seguente riassume alcuni concetti fondamentali di Costo sbarcato.</span><span class="sxs-lookup"><span data-stu-id="14e51-148">The following table summarizes some core concepts of Landed cost.</span></span>

| <span data-ttu-id="14e51-149">Concetto</span><span class="sxs-lookup"><span data-stu-id="14e51-149">Concept</span></span> | <span data-ttu-id="14e51-150">Descrizione</span><span class="sxs-lookup"><span data-stu-id="14e51-150">Description</span></span> |
|---|---|
| <span data-ttu-id="14e51-151">Viaggio</span><span class="sxs-lookup"><span data-stu-id="14e51-151">Voyage</span></span> | <span data-ttu-id="14e51-152">Tipicamente, un viaggio è un'imbarcazione.</span><span class="sxs-lookup"><span data-stu-id="14e51-152">Typically, a voyage is one vessel.</span></span> <span data-ttu-id="14e51-153">Tuttavia, a seconda delle pratiche e delle procedure, può essere un fornitore o un ordine fornitore.</span><span class="sxs-lookup"><span data-stu-id="14e51-153">However, depending on your practices and procedures, it can be one vendor or one purchase order.</span></span> <span data-ttu-id="14e51-154">Non vi sono limitazioni all'uso di questo concetto.</span><span class="sxs-lookup"><span data-stu-id="14e51-154">There are no limitations on the use of this concept.</span></span> |
| <span data-ttu-id="14e51-155">Registrazione</span><span class="sxs-lookup"><span data-stu-id="14e51-155">Folio</span></span> | <span data-ttu-id="14e51-156">Una registrazione è spesso determinata dalle normative doganali.</span><span class="sxs-lookup"><span data-stu-id="14e51-156">A folio is often determined by customs regulations.</span></span> <span data-ttu-id="14e51-157">Può essere costituita dalle merci di un fornitore per un'entità/azienda per spedizione.</span><span class="sxs-lookup"><span data-stu-id="14e51-157">It can consist of one vendor's goods for one entity/company per shipment.</span></span> <span data-ttu-id="14e51-158">Le merci in una registrazione possono essere in un contenitore o distribuite tra più contenitori.</span><span class="sxs-lookup"><span data-stu-id="14e51-158">The goods in a folio can be in one container or spread among multiple containers.</span></span> |
| <span data-ttu-id="14e51-159">Contenitore di spedizione</span><span class="sxs-lookup"><span data-stu-id="14e51-159">Shipping container</span></span> | <span data-ttu-id="14e51-160">I contenitori di spedizione memorizzano le righe dell'ordine fornitore.</span><span class="sxs-lookup"><span data-stu-id="14e51-160">Shipping containers store purchase order lines.</span></span> <span data-ttu-id="14e51-161">Sono un livello inferiore al livello di spedizione.</span><span class="sxs-lookup"><span data-stu-id="14e51-161">They are a level below the shipment level.</span></span> <span data-ttu-id="14e51-162">In genere vengono utilizzati se i costi sono ripartiti per merci per contenitore o se la ricezione viene effettuata per contenitore.</span><span class="sxs-lookup"><span data-stu-id="14e51-162">They are typically used if costs are apportioned for goods by container, or if receiving is done per container.</span></span> |
| <span data-ttu-id="14e51-163">Tipo di contenitore di spedizione</span><span class="sxs-lookup"><span data-stu-id="14e51-163">Shipping container type</span></span> | <span data-ttu-id="14e51-164">I tipi di contenitore di spedizione possono determinare il prezzo per un tipo di costo (ad esempio, trasporto).</span><span class="sxs-lookup"><span data-stu-id="14e51-164">Shipping container types can determine the price for a cost type (for example, freight).</span></span> <span data-ttu-id="14e51-165">Forniscono anche informazioni utili sulla spedizione.</span><span class="sxs-lookup"><span data-stu-id="14e51-165">They also provide useful shipping information.</span></span> |
| <span data-ttu-id="14e51-166">Tipo di costo</span><span class="sxs-lookup"><span data-stu-id="14e51-166">Cost type</span></span> | <span data-ttu-id="14e51-167">I tipi di costo identificano i costi associati alle importazioni, come dazi, trasporto e assicurazione.</span><span class="sxs-lookup"><span data-stu-id="14e51-167">Cost types identify costs that are associated with imports, such as duty, freight, and insurance.</span></span> |
| <span data-ttu-id="14e51-168">Costo automatico</span><span class="sxs-lookup"><span data-stu-id="14e51-168">Auto cost</span></span> | <span data-ttu-id="14e51-169">I costi automatici funzionano come accordi commerciali.</span><span class="sxs-lookup"><span data-stu-id="14e51-169">Auto costs work like trade agreements.</span></span> <span data-ttu-id="14e51-170">Un costo automatico è collegato a un livello di viaggio.</span><span class="sxs-lookup"><span data-stu-id="14e51-170">An auto cost is linked to a voyage level.</span></span> |
| <span data-ttu-id="14e51-171">Porto</span><span class="sxs-lookup"><span data-stu-id="14e51-171">Port</span></span> | <span data-ttu-id="14e51-172">I porti sono aree in cui le merci vengono ricevute e trasferite.</span><span class="sxs-lookup"><span data-stu-id="14e51-172">Ports are areas where goods are received and transferred from.</span></span> |
| <span data-ttu-id="14e51-173">Imbarcazione</span><span class="sxs-lookup"><span data-stu-id="14e51-173">Vessel</span></span> | <span data-ttu-id="14e51-174">Un'imbarcazione è il mezzo utilizzato per il trasporto di merci, ad esempio una nave o un aeroplano.</span><span class="sxs-lookup"><span data-stu-id="14e51-174">A vessel is the medium that is used to transport goods, such as a ship or an airplane.</span></span> |
| <span data-ttu-id="14e51-175">Merci in transito</span><span class="sxs-lookup"><span data-stu-id="14e51-175">Goods in transit</span></span> | <span data-ttu-id="14e51-176">A seconda delle impostazioni, le merci vengono trasferite in un magazzino in transito dopo l'aggiornamento di una fattura.</span><span class="sxs-lookup"><span data-stu-id="14e51-176">Depending on settings, goods are put into an in-transit warehouse after an invoice is updated.</span></span> |
| <span data-ttu-id="14e51-177">Attività</span><span class="sxs-lookup"><span data-stu-id="14e51-177">Activity</span></span> | <span data-ttu-id="14e51-178">Le attività possono essere utilizzate per memorizzare ogni fase significativa del percorso tra due porti.</span><span class="sxs-lookup"><span data-stu-id="14e51-178">Activities can be used to store each significant step of the journey between two ports.</span></span> <span data-ttu-id="14e51-179">Possono essere utilizzate per aggiornare le date.</span><span class="sxs-lookup"><span data-stu-id="14e51-179">They can be used to update dates.</span></span> |
| <span data-ttu-id="14e51-180">Modello di percorso</span><span class="sxs-lookup"><span data-stu-id="14e51-180">Journey template</span></span> | <span data-ttu-id="14e51-181">I modelli di percorso sono gli itinerari delle merci tra due porti.</span><span class="sxs-lookup"><span data-stu-id="14e51-181">Journey templates are routes that goods take between two ports.</span></span> |

<span data-ttu-id="14e51-182">Per un confronto della terminologia e delle funzionalità dei moduli **Costo sbarcato** e **Gestione trasporto** (TMS), vedere [Costo sbarcato e Gestione trasporto](landed-cost-vs-tms.md).</span><span class="sxs-lookup"><span data-stu-id="14e51-182">For a comparison of the terminology and features of the **Landed cost** and **Transportation management** (TMS) modules, see [Landed cost vs. Transportation management](landed-cost-vs-tms.md).</span></span>