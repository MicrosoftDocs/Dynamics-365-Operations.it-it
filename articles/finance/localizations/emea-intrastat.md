---
title: Panoramica di Intrastat
description: In questo argomento vengono fornite informazioni sulla dichiarazione Intrastat per gli scambi commerciali di beni e servizi tra paesi dell'Unione Europea. Sono riportate informazioni generali sul processo di dichiarazione e vengono descritte le impostazioni necessarie e i prerequisiti.
author: EvgenyPopovMBS
manager: AnnBe
ms.date: 01/13/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: Intrastat
audience: Application User
ms.reviewer: kfend
ms.custom: 28581
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: epopov
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 9396637c27707f1732d06ec704c7e609aa6c170b
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4962727"
---
# <a name="intrastat-overview"></a><span data-ttu-id="39cac-104">Panoramica di Intrastat</span><span class="sxs-lookup"><span data-stu-id="39cac-104">Intrastat overview</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="39cac-105">In questo argomento vengono fornite informazioni sulla dichiarazione Intrastat per gli scambi commerciali di beni e servizi tra paesi dell'Unione Europea.</span><span class="sxs-lookup"><span data-stu-id="39cac-105">This topic provides information about Intrastat reporting for the trade of goods and, in some cases, services among countries/regions of the European Union (EU).</span></span> <span data-ttu-id="39cac-106">Sono riportate informazioni generali sul processo di dichiarazione e vengono descritte le impostazioni necessarie e i prerequisiti.</span><span class="sxs-lookup"><span data-stu-id="39cac-106">It provides an overview of the reporting process, and describes the required settings and prerequisites.</span></span>

<span data-ttu-id="39cac-107">Intrastat è il sistema per la raccolta e la generazione di statistiche sugli scambi commerciali tra paesi dell'Unione Europea.</span><span class="sxs-lookup"><span data-stu-id="39cac-107">Intrastat is the system for collecting information and generating statistics about the trade of goods among countries/regions of the European Union (EU).</span></span> <span data-ttu-id="39cac-108">La dichiarazione Intrastat è richiesta ogni volta che un prodotto attraversa il confine di un altro paese UE.</span><span class="sxs-lookup"><span data-stu-id="39cac-108">Intrastat reporting is required whenever a product crosses the border of another EU country/region.</span></span> <span data-ttu-id="39cac-109">In più paesi, il report Intrastat si applica anche ai servizi.</span><span class="sxs-lookup"><span data-stu-id="39cac-109">In several countries/regions, Intrastat reporting also applies to services.</span></span> <span data-ttu-id="39cac-110">Gli elementi obbligatori e facoltativi possono essere raccolti nella dichiarazione Intrastat.</span><span class="sxs-lookup"><span data-stu-id="39cac-110">Mandatory and optional elements can be collected in Intrastat reporting.</span></span> <span data-ttu-id="39cac-111">Gli elementi seguenti sono obbligatori: numero di imposta sul valore aggiunto (IVA) della parte responsabile di immettere informazioni, il periodo di riferimento, il flusso (arrivo o spedizione), il codice di voce doganale di otto cifre, lo stato membro del partner (stato membro della spedizione negli arrivi e stato membro di destinazione delle spedizioni), il valore delle merci, la quantità delle merci (massa netto e unità supplementare) e la natura della transazione.</span><span class="sxs-lookup"><span data-stu-id="39cac-111">The following elements are mandatory: the value-added tax (VAT) number of the party that is responsible for providing information, the reference period, the flow (arrival or dispatch), the eight-digit commodity code, the partner member state (member state of consignment on arrivals and member state of destination on dispatches), the value of the goods, the quantity of the goods (net mass and supplementary unit), and the nature of the transaction.</span></span> <span data-ttu-id="39cac-112">Per i paesi/regioni è inoltre possibile raccogliere gli elementi facoltativi nelle varie condizioni.</span><span class="sxs-lookup"><span data-stu-id="39cac-112">Countries/regions can also collect optional elements under various conditions.</span></span> <span data-ttu-id="39cac-113">Alcuni elementi facoltativi sono il paese di origine, i termini di consegna, la modalità di trasporto, un codice di voce doganale più dettagliato che CN8, l'area di origine nelle spedizioni e l'area di destinazione degli arrivi, la procedura statistica, il valore statistico, una descrizione delle merci e il porto/aeroporto di carico/di scarico.</span><span class="sxs-lookup"><span data-stu-id="39cac-113">Some optional elements are the country/region of origin, the delivery terms, the mode of transport, a more detailed commodity code than CN8, the region of origin on dispatches and the region of destination on arrivals, the statistical procedure, the statistical value, a description of the goods, and the port/airport of loading/unloading.</span></span>

## <a name="overview-of-the-intrastat-reporting-process"></a><span data-ttu-id="39cac-114">Panoramica del processo di reporting Intrastat</span><span class="sxs-lookup"><span data-stu-id="39cac-114">Overview of the Intrastat reporting process</span></span>
<span data-ttu-id="39cac-115">Le seguenti sezioni illustrano il flusso globale di informazioni utilizzato per la dichiarazione Intrastat.</span><span class="sxs-lookup"><span data-stu-id="39cac-115">The following sections describe the overall flow of information that is used for Intrastat reporting.</span></span>

### <a name="1-enter-a-transaction-that-crosses-the-border-of-another-eu-countryregion"></a><span data-ttu-id="39cac-116">1. Immettere una transazione che attraversa il confine di un altro paese UE</span><span class="sxs-lookup"><span data-stu-id="39cac-116">1. Enter a transaction that crosses the border of another EU country/region</span></span>

<span data-ttu-id="39cac-117">Una fattura cliente, una fattura a testo libero, una fattura di acquisto, una fattura di progetto, un documento di trasporto cliente, un'entrata prodotti del fornitore, un ordine di trasferimento viene trasferito nel giornale di registrazione Intrastat solo se il tipo di paesi di destinazione (sulle spedizioni) o la spedizione (gli arrivi) è **UE**.</span><span class="sxs-lookup"><span data-stu-id="39cac-117">A customer invoice, free text invoice, purchase invoice, project invoice, customer packing slip, vendor product receipt, or transfer order is transferred to the Intrastat journal only if the country/region type of the destination (on dispatches) or consignment (on arrivals) is **EU**.</span></span> <span data-ttu-id="39cac-118">Questa funzionalità è stata estesa per Microsoft Dynamics 365 for Operations (1611) e consente di specificare gli indirizzi di carico per una transazione intracomunitaria.</span><span class="sxs-lookup"><span data-stu-id="39cac-118">This feature was extended for Microsoft Dynamics 365 for Operations (1611) and allows you to specify lading addresses for an intra-community transaction.</span></span> <span data-ttu-id="39cac-119">Se l'indirizzo di carico è diverso all'ufficio del fornitore (o l'indirizzo commerciale del cliente per ordine di reso) la dichiarazione Intrastat opererà con queste informazioni.</span><span class="sxs-lookup"><span data-stu-id="39cac-119">If a lading address differs with a vendor business address (or customer business address for return order) the Intrastat reporting will operate with this information.</span></span> <span data-ttu-id="39cac-120">Quando si crea un ordine cliente, una fattura a testo libero, un ordine fornitore, una fattura fornitore, una fattura di progetto, un ordine di trasferimento, alcuni campi correlati al commercio estero hanno valori predefiniti nell'intestazione del documento o nella riga.</span><span class="sxs-lookup"><span data-stu-id="39cac-120">When you create a sales order, free text invoice, purchase order, vendor invoice, project invoice, or transfer order, some fields that are related to foreign trade have default values in the document header or on the line.</span></span> <span data-ttu-id="39cac-121">Il codice transazione predefinito viene ricavato dal campo corrispondente sulla pagina **Parametri per il commercio estero**.</span><span class="sxs-lookup"><span data-stu-id="39cac-121">The default transaction code is taken from the corresponding field on the **Foreign trade parameters** page.</span></span> <span data-ttu-id="39cac-122">Il codice di voce doganale predefinito, il paese di origine e lo stato/regione o provincia di origine vengono ottenuti dall'articolo.</span><span class="sxs-lookup"><span data-stu-id="39cac-122">The default commodity code, country/region of origin, and state/province of origin are taken from the item.</span></span> <span data-ttu-id="39cac-123">È possibile modificare i valori predefiniti ed è inoltre necessario completare altre informazioni commerciali estere: procedura statistica, metodo di trasporto e porto.</span><span class="sxs-lookup"><span data-stu-id="39cac-123">You can change the default values and can also fill in other foreign trade–related information: the statistics procedure, transport method, and port.</span></span>

### <a name="2-use-the-intrastat-journal-to-generate-information-about-trade-among-eu-countriesregions"></a><span data-ttu-id="39cac-124">2. Utilizzare il giornale di registrazione Intrastat per generare informazioni relative agli scambi commerciali tra i paesi dell'Unione Europea (UE).</span><span class="sxs-lookup"><span data-stu-id="39cac-124">2. Use the Intrastat journal to generate information about trade among EU countries/regions</span></span>

<span data-ttu-id="39cac-125">A fini statistici, generare ogni mese le informazioni relative al commercio tra i diversi paesi/regioni UE.</span><span class="sxs-lookup"><span data-stu-id="39cac-125">For statistical purposes, you generate information about trade among EU countries/regions every month.</span></span> <span data-ttu-id="39cac-126">È possibile trasferire le transazioni da una fattura a testo libero, una fattura cliente, un documento di trasporto cliente, una fattura fornitore, un documento di trasporto fornitore, una fattura progetto, o un ordine di trasferimento, in base ai criteri di trasferimento impostati nella pagina **Parametri per il commercio estero**.</span><span class="sxs-lookup"><span data-stu-id="39cac-126">You can transfer transactions from a free text invoice, customer invoice, customer packing slip, vendor invoice, vendor packing slip, project invoice, or transfer order, according to the transfer criteria that are set up on the **Foreign trade parameters** page.</span></span> <span data-ttu-id="39cac-127">In alternativa, è possibile immettere le transazioni manualmente.</span><span class="sxs-lookup"><span data-stu-id="39cac-127">Alternatively, you can enter transactions manually.</span></span> <span data-ttu-id="39cac-128">È possibile aggiornare manualmente le transazioni trasferite nel giornale di registrazione Intrastat, se gli aggiornamenti vengono richiesti.</span><span class="sxs-lookup"><span data-stu-id="39cac-128">You can manually update transferred transactions in the Intrastat journal, if any updates are required.</span></span> <span data-ttu-id="39cac-129">Sotto le condizioni specifiche impostate nella pagina **Compressione di Intrastat**, è possibile comprimere le transazioni nel giornale di registrazione Intrastat.</span><span class="sxs-lookup"><span data-stu-id="39cac-129">Under specific conditions that are set up on the **Compression of Intrastat** page, you can compress the transactions in the Intrastat journal.</span></span> <span data-ttu-id="39cac-130">Alcuni paesi consentono di applicare una piccola soglia di transazione.</span><span class="sxs-lookup"><span data-stu-id="39cac-130">Some countries/regions let you apply a small transaction threshold.</span></span> <span data-ttu-id="39cac-131">È quindi possibile dichiarare tutte le transazioni in tale soglia nel codice di voce doganale specificato.</span><span class="sxs-lookup"><span data-stu-id="39cac-131">You can then report transactions that are below that threshold under the specified commodity code.</span></span> <span data-ttu-id="39cac-132">È possibile aggiornare il codice di voce doganale sulle righe del giornale di registrazione Intrastat corrispondenti, in **Limite minimo** base all'impostazione della pagina **Parametri per il commercio estero**.</span><span class="sxs-lookup"><span data-stu-id="39cac-132">You can update the commodity code on the corresponding Intrastat journal lines, based on the **Minimum limit** setting on the **Foreign trade parameters** page.</span></span> <span data-ttu-id="39cac-133">È inoltre possibile comprimere le transazioni, in base all'impostazione **Compressione di Intrastat**.</span><span class="sxs-lookup"><span data-stu-id="39cac-133">You can also compress those transactions, based on the **Compression of Intrastat** setting.</span></span> <span data-ttu-id="39cac-134">È possibile convalidare la completezza delle transazioni nel giornale di registrazione Intrastat, in base all'impostazione **Impostazione dell'assegno** della pagina **Parametri per il commercio estero**.</span><span class="sxs-lookup"><span data-stu-id="39cac-134">You can validate the completeness of the transactions in the Intrastat journal, based on the **Check setup** setting on the **Foreign trade parameters** page.</span></span> <span data-ttu-id="39cac-135">I dati nei campi corrispondenti possono essere convalidati per completezza: paese, stato/regione o provincia, peso, codice di voce doganale, codice transazione, unità aggiuntiva, porta, origine, termini di consegna, metodo di trasporto e numero esenzione IVA.</span><span class="sxs-lookup"><span data-stu-id="39cac-135">The data in corresponding fields might be validated for completeness: country/region, state or province, weight, commodity code, transaction code, additional unit, port, origin, terms of delivery, transport method, and tax exempt number.</span></span> <span data-ttu-id="39cac-136">Le transazioni che non vengono completate verranno contrassegnate come non valide.</span><span class="sxs-lookup"><span data-stu-id="39cac-136">Transactions that aren't completed will be marked as not valid.</span></span>

### <a name="3-use-the-intrastat-journal-to-report-information-about-trade-among-eu-countriesregions"></a><span data-ttu-id="39cac-137">3. Utilizzare il giornale di registrazione Intrastat per registrare e visualizzare informazioni relative agli scambi commerciali tra i paesi dell'Unione Europea (UE).</span><span class="sxs-lookup"><span data-stu-id="39cac-137">3. Use the Intrastat journal to report information about trade among EU countries/regions</span></span>

<span data-ttu-id="39cac-138">A fini statistici, registrare ogni mese le informazioni relative al commercio tra i diversi paesi/regioni UE.</span><span class="sxs-lookup"><span data-stu-id="39cac-138">For statistical purposes, you report information about trade among EU countries/regions every month.</span></span> <span data-ttu-id="39cac-139">È possibile stampare il report Intrastat, in base alle impostazioni **Mapping formato di report** nella pagina **Parametri per il commercio estero**.</span><span class="sxs-lookup"><span data-stu-id="39cac-139">You can print the Intrastat report, based on the **Report format mapping** settings on the **Foreign trade parameters** page.</span></span> <span data-ttu-id="39cac-140">È possibile anche generare un file elettronico, in base alle impostazioni **Mapping formato file** nella pagina **Parametri per il commercio estero**.</span><span class="sxs-lookup"><span data-stu-id="39cac-140">You can also generate an electronic file, based on the **File format mapping** settings on the **Foreign trade parameters** page.</span></span> <span data-ttu-id="39cac-141">Per ulteriori informazioni sulla dichiarazione Intrastat, inclusi i prerequisiti necessari, vedere le registrazioni attività sulla dichiarazione Intrastat:</span><span class="sxs-lookup"><span data-stu-id="39cac-141">For more information about Intrastat reporting, including required prerequisites, see the Intrastat reporting task recordings:</span></span>

-   <span data-ttu-id="39cac-142">Generare una dichiarazione Intrastat UE</span><span class="sxs-lookup"><span data-stu-id="39cac-142">Generate an EU Intrastat declaration,</span></span>
-   <span data-ttu-id="39cac-143">Trasferire transazioni a Intrastat</span><span class="sxs-lookup"><span data-stu-id="39cac-143">Transfer transactions to the Intrastat,</span></span>
-   <span data-ttu-id="39cac-144">Specifica di un indirizzo di carico per una transazione intracomunitaria</span><span class="sxs-lookup"><span data-stu-id="39cac-144">Specifying lading address for an intra-community transaction.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="39cac-145">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="39cac-145">Prerequisites</span></span>
<span data-ttu-id="39cac-146">Nella seguente tabella vengono elencati i prerequisiti per la dichiarazione Intrastat.</span><span class="sxs-lookup"><span data-stu-id="39cac-146">The following table lists the prerequisites for Intrastat reporting.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="39cac-147">Prerequisito</span><span class="sxs-lookup"><span data-stu-id="39cac-147">Prerequisite</span></span></th>
<th><span data-ttu-id="39cac-148">Descrizione</span><span class="sxs-lookup"><span data-stu-id="39cac-148">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="39cac-149">Impostazione indirizzo</span><span class="sxs-lookup"><span data-stu-id="39cac-149">Address setup</span></span></td>
<td><span data-ttu-id="39cac-150">Configurare codice del paese utilizzato dall'ISO (International Organization for Standardization).</span><span class="sxs-lookup"><span data-stu-id="39cac-150">Set up International Organization for Standardization (ISO) codes for countries/regions.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="39cac-151">Persona giuridica</span><span class="sxs-lookup"><span data-stu-id="39cac-151">Legal entity</span></span></td>
<td><span data-ttu-id="39cac-152">Impostare le partite VAT dell'importazione/esportazione, l'estensione del codice filiale di importazione/esportazione e il codice Intrastat assegnato alla persona giuridica.</span><span class="sxs-lookup"><span data-stu-id="39cac-152">Set up tax exempt numbers for import/export, the branch number extension for import/export, and the Intrastat code that is assigned to the legal entity.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="39cac-153">Gerarchia di categorie di prodotti (gerarchia di vendita, gerarchia di approvvigionamento)</span><span class="sxs-lookup"><span data-stu-id="39cac-153">Product category hierarchy (sales hierarchy, procurement hierarchy)</span></span></td>
<td><span data-ttu-id="39cac-154">Assegnare i codici di voce doganale Intrastat ai nodi di categoria <strong>Codici di voce doganale</strong> nella scheda <strong>Gerarchia di categorie</strong> della pagina.</span><span class="sxs-lookup"><span data-stu-id="39cac-154">Assign the Intrastat commodity codes to the category nodes on the <strong>Commodity codes</strong> tab of the <strong>Category hierarchy</strong> page.</span></span> <span data-ttu-id="39cac-155">Quando si assegna un codice di voce doganale a un nodo di categoria padre, il codice è applicabile a tutti i nodi di categoria figlio.</span><span class="sxs-lookup"><span data-stu-id="39cac-155">When you assign a commodity code to a parent category node, that code is applicable to all child category nodes.</span></span> <span data-ttu-id="39cac-156">I codici di voce doganale selezionati saranno disponibili nella visualizzazione <strong>Selezionato</strong> quando si seleziona un codice di voce doganale nei dettagli del prodotto rilasciato e nelle righe di ordine cliente, ordine fornitore e ordine di trasferimento.</span><span class="sxs-lookup"><span data-stu-id="39cac-156">The selected commodity codes will be available in the <strong>Selected</strong> view when you select a commodity code in the released product details, and on sales order, purchase order, and transfer order lines.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="39cac-157">Dettagli prodotto rilasciato</span><span class="sxs-lookup"><span data-stu-id="39cac-157">Released product details</span></span></td>
<td><span data-ttu-id="39cac-158">Impostare i seguenti dati del commercio estero per i prodotti rilasciati:</span><span class="sxs-lookup"><span data-stu-id="39cac-158">Set up the following foreign trade data for released products:</span></span>
<ul>
<li><span data-ttu-id="39cac-159"><strong>Codice di voce doganale</strong> Consente di selezionare dall presente una o due l'elenco delle voci doganali selezionate che viene recuperato dalle categorie di prodotti assegnati o dall'elenco completo di codici di voce doganale Intrastat.</span><span class="sxs-lookup"><span data-stu-id="39cac-159"><strong>Commodity code</strong> – Select from either the list of selected commodities that is retrieved from assigned product categories or the full list of Intrastat commodity codes.</span></span></li>
<li><span data-ttu-id="39cac-160"><strong>Percentuale spese totali</strong></span><span class="sxs-lookup"><span data-stu-id="39cac-160"><strong>Statistical charges percentage</strong></span></span></li>
<li><span data-ttu-id="39cac-161"><strong>Paese di origine</strong> Consente di selezionare il paese predefinito in cui le merci sono state completamente ottenute o prodotto si.</span><span class="sxs-lookup"><span data-stu-id="39cac-161"><strong>Country/region of origin</strong> – Select the default country/region where the goods were completely obtained or produced.</span></span></li>
<li><span data-ttu-id="39cac-162"><strong>Stato/regione o provincia di origine/destinazione</strong> Consente di selezionare lo stato predefinito/regione di destinazione per gli arrivi e il stato/regione o provincia di origine per le spedizioni.</span><span class="sxs-lookup"><span data-stu-id="39cac-162"><strong>State/province of origin/destination</strong> – Select the default state/province of destination for arrivals and the state/province of origin for dispatches.</span></span></li>
<li><span data-ttu-id="39cac-163"><strong>Peso netto in kg</strong></span><span class="sxs-lookup"><span data-stu-id="39cac-163"><strong>Net weight in kg</strong></span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="39cac-164">Clienti</span><span class="sxs-lookup"><span data-stu-id="39cac-164">Customers</span></span></td>
<td><span data-ttu-id="39cac-165">Paese in cui è presente l'indirizzo di consegna del cliente nella regione UE.</span><span class="sxs-lookup"><span data-stu-id="39cac-165">Set up the customer delivery address in the EU country/region.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="39cac-166">Fornitori</span><span class="sxs-lookup"><span data-stu-id="39cac-166">Vendors</span></span></td>
<td><span data-ttu-id="39cac-167">Paese in cui è presente l'indirizzo di consegna del cliente nella regione UE.</span><span class="sxs-lookup"><span data-stu-id="39cac-167">Set up the vendor address in the EU country/region.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="39cac-168">Spese varie</span><span class="sxs-lookup"><span data-stu-id="39cac-168">Miscellaneous charges</span></span></td>
<td><span data-ttu-id="39cac-169">Impostare il codice spese varie da includere nell'importo della fattura, l'importo statistico, o entrambi.</span><span class="sxs-lookup"><span data-stu-id="39cac-169">Set up the miscellaneous charges code to include in the invoice amount, the statistical amount, or both.</span></span> <span data-ttu-id="39cac-170"><strong>Codici spese</strong> In <strong>Commercio estero</strong> la pagina, nella scheda, attivare <strong>Valore di fattura Intrastat</strong> per includere le spese ammontano il valore di fattura e consentono <strong>Valore statistico Intrastat</strong> per includere le spese ammontano il valore statistico.</span><span class="sxs-lookup"><span data-stu-id="39cac-170">On the <strong>Charges codes</strong> page, on the <strong>Foreign trade</strong> tab, enable <strong>Intrastat invoice value</strong> to include the charges amount in the invoice value, and enable <strong>Intrastat statistical value</strong> to include the charges amount in the statistical value.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="39cac-171">Creazione di report elettronici</span><span class="sxs-lookup"><span data-stu-id="39cac-171">Electronic reporting</span></span></td>
<td><span data-ttu-id="39cac-172">Impostare le configurazioni del report elettroniche per esportare i dati Intrastat in un file elettronico con il formato richiesto dagli uffici competenti e visualizzare l'anteprima dei dati Intrastat in formato semplice da usare e leggibile (ad esempio, in Microsoft Excel).</span><span class="sxs-lookup"><span data-stu-id="39cac-172">Set up electronic reporting configurations to export Intrastat data in an electronic file that has the format that is requested by the relevant authorities, and to preview Intrastat data in a user-friendly, readable format (for example, in Microsoft Excel).</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="39cac-173">Magazzino</span><span class="sxs-lookup"><span data-stu-id="39cac-173">Warehousing</span></span></td>
<td><span data-ttu-id="39cac-174">Associare i conti fornitore con i codici magazzino per il ricaricamento della partita IVA durante il trasferimento dell'ordine di trasferimento.</span><span class="sxs-lookup"><span data-stu-id="39cac-174">Associate vendor accounts with warehouse codes for filling tax exempt number when transferring Transfer order.</span></span></td>
</tr>
</tbody>
</table>

## <a name="setup"></a><span data-ttu-id="39cac-175">Imposta</span><span class="sxs-lookup"><span data-stu-id="39cac-175">Setup</span></span>
<span data-ttu-id="39cac-176">Nelle sezioni seguenti sono descritte le impostazioni necessarie per la dichiarazione Intrastat.</span><span class="sxs-lookup"><span data-stu-id="39cac-176">The following sections describe the settings that are required for Intrastat reporting.</span></span>

### <a name="set-up-all-required-intrastat-related-lists"></a><span data-ttu-id="39cac-177">Impostare tutti gli elenchi correlati a Intrastat richiesti</span><span class="sxs-lookup"><span data-stu-id="39cac-177">Set up all required Intrastat-related lists</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="39cac-178">Elenco</span><span class="sxs-lookup"><span data-stu-id="39cac-178">List</span></span></th>
<th><span data-ttu-id="39cac-179">Informazioni aggiuntive</span><span class="sxs-lookup"><span data-stu-id="39cac-179">Additional information</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="39cac-180">Codici voce doganale</span><span class="sxs-lookup"><span data-stu-id="39cac-180">Commodity codes</span></span></td>
<td><span data-ttu-id="39cac-181">Impostare una gerarchia di categorie di tipo <strong>Codice di voce doganale</strong> e immettere i codici di voce doganale in base all'elenco di nomenclatura combinata.</span><span class="sxs-lookup"><span data-stu-id="39cac-181">Set up a category hierarchy of type <strong>Commodity code</strong>, and enter all commodity codes according to the combined nomenclature list.</span></span> <span data-ttu-id="39cac-182">Per ciascuna voce doganale è possibile definire le seguenti informazioni:</span><span class="sxs-lookup"><span data-stu-id="39cac-182">For each commodity, you set up the following information:</span></span>
<ul>
<li><span data-ttu-id="39cac-183">Il nome della voce doganale e il codice della voce doganale</span><span class="sxs-lookup"><span data-stu-id="39cac-183">The name of the commodity and the commodity code</span></span></li>
<li><span data-ttu-id="39cac-184">Il nome descrittivo e/o il nome tradotto</span><span class="sxs-lookup"><span data-stu-id="39cac-184">The friendly name and/or translated name</span></span></li>
<li><span data-ttu-id="39cac-185">Impostazioni per la dichiarazione di unità aggiuntive (supplementari) nella scheda <strong>Commercio estero</strong>. È possibile selezionare l'unità aggiuntiva nell'elenco di unità.</span><span class="sxs-lookup"><span data-stu-id="39cac-185">Settings for reporting additional (supplementary) units on the <strong>Foreign trade</strong> tab. You can select the additional unit in the unit list.</span></span> <span data-ttu-id="39cac-186">È inoltre possibile specificare se il peso delle voci doganali deve essere dichiarato oltre all'unità aggiuntiva selezionata.</span><span class="sxs-lookup"><span data-stu-id="39cac-186">You can also specify whether the weight of commodities must be reported in addition to the selected additional unit.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="39cac-187">Codici transazioni</span><span class="sxs-lookup"><span data-stu-id="39cac-187">Transaction codes</span></span></td>
<td><span data-ttu-id="39cac-188">Impostare la natura della transazione in base ai requisiti per il paese.</span><span class="sxs-lookup"><span data-stu-id="39cac-188">Set up the nature of the transaction according to your country&#39;s/region&#39;s requirements.</span></span> <span data-ttu-id="39cac-189">Per ogni codice transazione impostato, è necessario impostare le regole per calcolare gli importi fattura e gli importi statistici per gli ordini di trasferimento e vendite.</span><span class="sxs-lookup"><span data-stu-id="39cac-189">For each transaction code that you set up, you must set up the rules for calculating invoice amounts and statistical amounts for transfer orders and sales/purchase orders.</span></span>
<ul>
<li><span data-ttu-id="39cac-190">Per gli ordini di trasferimento, si imposta una delle seguenti regole per calcolare gli importi fattura e gli importi statistici:</span><span class="sxs-lookup"><span data-stu-id="39cac-190">For transfer orders, you set up one of the following rules for calculating invoice amounts and statistical amounts:</span></span>
<ul>
<li><span data-ttu-id="39cac-191"><strong>Vuoto</strong> – L'importo sarà 0 (zero).</span><span class="sxs-lookup"><span data-stu-id="39cac-191"><strong>Empty</strong> – The amount will be 0 (zero).</span></span></li>
<li><span data-ttu-id="39cac-192"><strong>Importo costo finanziario</strong> – L'importo sarà uguale al costo finanziario.</span><span class="sxs-lookup"><span data-stu-id="39cac-192"><strong>Financial cost amount</strong> – The amount will be equal to the financial cost.</span></span></li>
<li><span data-ttu-id="39cac-193"><strong>Costo totale</strong> – L'importo sarà uguale al costo totale della transazione.</span><span class="sxs-lookup"><span data-stu-id="39cac-193"><strong>Total cost</strong> – The amount will be equal to the total cost of the transaction.</span></span></li>
<li><span data-ttu-id="39cac-194"><strong>Manuale</strong> – L'importo sarà uguale a quello che è specificato manualmente nella riga ordine di trasferimento.</span><span class="sxs-lookup"><span data-stu-id="39cac-194"><strong>Manual</strong> – The amount will be equal to the amount that is manually specified on the transfer order line.</span></span></li>
</ul></li>
<li><span data-ttu-id="39cac-195">Per gli ordini cliente e gli ordini acquisto, si imposta una delle seguenti regole per calcolare gli importi fattura e gli importi statistici:</span><span class="sxs-lookup"><span data-stu-id="39cac-195">For sales orders and purchase orders, you set up one of the following rules for calculating invoice amounts and statistical amounts:</span></span>
<ul>
<li><span data-ttu-id="39cac-196"><strong>Vuoto</strong> – L'importo sarà 0 (zero).</span><span class="sxs-lookup"><span data-stu-id="39cac-196"><strong>Empty</strong> – The amount will be 0 (zero).</span></span></li>
<li><span data-ttu-id="39cac-197"><strong>Importo della fattura</strong> – L'importo sarà uguale a quello fatturato per la voce doganale.</span><span class="sxs-lookup"><span data-stu-id="39cac-197"><strong>Invoice amount</strong> – The amount will be equal to the amount that is invoiced for the commodity.</span></span></li>
<li><span data-ttu-id="39cac-198"><strong>Imponibile</strong> – L'importo sarà uguale a quello che sarà fatturato prima di qualsiasi sconto applicato.</span><span class="sxs-lookup"><span data-stu-id="39cac-198"><strong>Base amount</strong> – The amount will be equal to the amount that would be invoiced before any discount is applied.</span></span></li>
</ul></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="39cac-199">Metodi di trasporto</span><span class="sxs-lookup"><span data-stu-id="39cac-199">Transport methods</span></span></td>
<td><span data-ttu-id="39cac-200">Impostare la modalità di trasporto in base ai requisiti per il paese.</span><span class="sxs-lookup"><span data-stu-id="39cac-200">Set up the transport mode according to your country&#39;s/region&#39;s requirements.</span></span> <span data-ttu-id="39cac-201">Per ciascuna modalità di consegna, è possibile impostare un metodo predefinito di trasporto nella scheda <strong>Commercio estero</strong>.</span><span class="sxs-lookup"><span data-stu-id="39cac-201">For each delivery mode, you can set up a default transport method on the <strong>Foreign trade</strong> tab.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="39cac-202">Porti</span><span class="sxs-lookup"><span data-stu-id="39cac-202">Ports</span></span></td>
<td><span data-ttu-id="39cac-203">Impostare il porto/aeroporto di carico/scarico se queste informazioni vengono raccolte dal proprio paese.</span><span class="sxs-lookup"><span data-stu-id="39cac-203">Set up the port/airport of loading/unloading if this information is collected by your country/region.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="39cac-204">Procedure statistiche</span><span class="sxs-lookup"><span data-stu-id="39cac-204">Statistics procedures</span></span></td>
<td><span data-ttu-id="39cac-205">Impostare la procedura statistica se queste informazioni vengono raccolte dal proprio paese.</span><span class="sxs-lookup"><span data-stu-id="39cac-205">Set up the statistical procedure if this information is collected by your country/region.</span></span></td>
</tr>
</tbody>
</table>

### <a name="set-up-rules-for-compressing-intrastat-transactions"></a><span data-ttu-id="39cac-206">Impostare regole di compressione per le transazioni Intrastat</span><span class="sxs-lookup"><span data-stu-id="39cac-206">Set up rules for compressing Intrastat transactions</span></span>

<span data-ttu-id="39cac-207">Nella pagina **Compressione di Intrastat**, è possibile selezionare i campi da utilizzare per la compressione.</span><span class="sxs-lookup"><span data-stu-id="39cac-207">On the **Compression of Intrastat** page, you can select the fields to use for compression.</span></span> <span data-ttu-id="39cac-208">Tutte le transazioni con la stessa combinazione di valori dei campi selezionati nel giornale di registrazione Intrastat verranno compresse in una singola transazione quando si esegue la funzione di comprimi nel giornale di registrazione Intrastat.</span><span class="sxs-lookup"><span data-stu-id="39cac-208">All transactions that have the same combination of values for the selected fields in the Intrastat journal will be compressed into a single transaction when you run the Compress function in the Intrastat journal.</span></span>

### <a name="set-up-foreign-trade-parameters"></a><span data-ttu-id="39cac-209">Imposta parametri per il commercio estero</span><span class="sxs-lookup"><span data-stu-id="39cac-209">Set up foreign trade parameters</span></span>

<span data-ttu-id="39cac-210">Utilizzare la pagina **Parametri per il commercio estero** per impostare i parametri nella seguente tabella.</span><span class="sxs-lookup"><span data-stu-id="39cac-210">Use the **Foreign trade parameters** page to set up the parameters in the following table.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="39cac-211">TAB</span><span class="sxs-lookup"><span data-stu-id="39cac-211">Tab</span></span></th>
<th><span data-ttu-id="39cac-212">Parametri</span><span class="sxs-lookup"><span data-stu-id="39cac-212">Parameters</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="39cac-213">Generale</span><span class="sxs-lookup"><span data-stu-id="39cac-213">General</span></span></td>
<td><ul>
<li><span data-ttu-id="39cac-214">Nella scheda <strong>Generale </strong> specificare le e seguenti informazioni:</span><span class="sxs-lookup"><span data-stu-id="39cac-214"><strong>General</strong> – Specify the following information:</span></span>
<ul>
<li><span data-ttu-id="39cac-215">Valore predefinito per i codici transazione da utilizzare sugli ordini acquisto, note di credito e ordini di trasferimento.</span><span class="sxs-lookup"><span data-stu-id="39cac-215">The default transaction codes for sales orders, purchase orders, credit notes, and transfer orders.</span></span> <span data-ttu-id="39cac-216">Il codice transazione impostato per le note di accredito verrà utilizzato come il codice per le merci fisiche restituite ed è utilizzato per i resi fisici di scostamento rispetto alle note di accredito della correzione.</span><span class="sxs-lookup"><span data-stu-id="39cac-216">The transaction code that is set up for credit notes is also used as the code for physical goods return and is used for deviating physical returns versus correction credit notes.</span></span> <span data-ttu-id="39cac-217">I resi di beni fisici vengono dichiarati in trasferimento Intrastat con una direzione diversa.</span><span class="sxs-lookup"><span data-stu-id="39cac-217">Returns of physical goods are reported in Intrastat transfer with a different direction.</span></span> <span data-ttu-id="39cac-218">Il reso di arrivo è dichiarato come intervento e il reso di intervento è dichiarato come arrivo.</span><span class="sxs-lookup"><span data-stu-id="39cac-218">The return of arrival is reported as dispatch and the return of dispatch is reported as arrival.</span></span></li>
<li><span data-ttu-id="39cac-219">Il dipendente responsabile di produzione report Intrastat.</span><span class="sxs-lookup"><span data-stu-id="39cac-219">The employee who is responsible for preparing Intrastat reports.</span></span></li>
</ul></li>
<li><span data-ttu-id="39cac-220"><strong>Limite minimo</strong> Consente di specificare le impostazioni per aggiornare le transazioni nella soglia:</span><span class="sxs-lookup"><span data-stu-id="39cac-220"><strong>Minimum limit</strong> – Specify the settings for updating transactions that are below the threshold:</span></span>
<ul>
<li><span data-ttu-id="39cac-221">L'importo e il peso di soglia</span><span class="sxs-lookup"><span data-stu-id="39cac-221">The threshold amount and weight</span></span></li>
<li><span data-ttu-id="39cac-222">Il codice di voce doganale da applicare alle transazioni che sono sotto la soglia</span><span class="sxs-lookup"><span data-stu-id="39cac-222">The commodity code to apply to transactions that are under the threshold</span></span></li>
</ul></li>
<li><span data-ttu-id="39cac-223"><strong>Trasferisci</strong> Consente di specificare i criteri per le transazioni di trasferimento nel giornale di registrazione Intrastat.</span><span class="sxs-lookup"><span data-stu-id="39cac-223"><strong>Transfer</strong> – Specify the criteria for transferring transactions to the Intrastat journal.</span></span> <span data-ttu-id="39cac-224">È possibile specificare le transazioni vengono trasferite solo quando gli articoli sono conformi a un o tutti criteri seguente:</span><span class="sxs-lookup"><span data-stu-id="39cac-224">You can specify that transactions are transferred only when the items meet one or all of the following criteria:</span></span>
<ul>
<li><span data-ttu-id="39cac-225">Gli articoli non sono articoli di tipo Assistenza.</span><span class="sxs-lookup"><span data-stu-id="39cac-225">The items aren&#39;t service items.</span></span></li>
<li><span data-ttu-id="39cac-226">Gli articoli hanno un codice voce doganale.</span><span class="sxs-lookup"><span data-stu-id="39cac-226">The items have a commodity code.</span></span></li>
<li><span data-ttu-id="39cac-227">Gli articoli hanno un peso.</span><span class="sxs-lookup"><span data-stu-id="39cac-227">The items have a weight.</span></span></li>
<li><span data-ttu-id="39cac-228">Gli articoli hanno unità supplementari.</span><span class="sxs-lookup"><span data-stu-id="39cac-228">The items have additional units.</span></span></li>
</ul></li>
<li><span data-ttu-id="39cac-229"><strong>Impostazione dell'assegno</strong> Consente di specificare le regole per la convalida della completezza dei dati Intrastat.</span><span class="sxs-lookup"><span data-stu-id="39cac-229"><strong>Check setup</strong> – Specify the rules for validating the completeness of Intrastat data.</span></span> <span data-ttu-id="39cac-230">È possibile selezionare i dati vengono convalidati.</span><span class="sxs-lookup"><span data-stu-id="39cac-230">You can select which data is validated.</span></span></li>
<li><span data-ttu-id="39cac-231"><strong>Regole di arrotondamento</strong> Consente di specificare le seguenti impostazioni per gli importi di arrotondamento e i pesi nella dichiarazione Intrastat:</span><span class="sxs-lookup"><span data-stu-id="39cac-231"><strong>Rounding rules</strong> – Specify the following settings for rounding amounts and weights in Intrastat reporting:</span></span>
<ul>
<li><span data-ttu-id="39cac-232">Regola di arrotondamento (precisione)</span><span class="sxs-lookup"><span data-stu-id="39cac-232">The rounding rule (precision)</span></span></li>
<li><span data-ttu-id="39cac-233">Metodo di arrotondamento per eccesso: eccesso, difetto o normale</span><span class="sxs-lookup"><span data-stu-id="39cac-233">The rounding method: up, down, or normal</span></span></li>
<li><span data-ttu-id="39cac-234">Il numero di posizioni decimali per gli importi e i pesi</span><span class="sxs-lookup"><span data-stu-id="39cac-234">The number of decimal places for amounts and weights</span></span></li>
<li><span data-ttu-id="39cac-235">Istruzioni per l'arrotondamento i pesi minori di 1 chilogrammo (kg): con arrotondamento a 1 chilogrammo, normale, o non arrotondamento</span><span class="sxs-lookup"><span data-stu-id="39cac-235">Instructions for rounding weights that are less than 1 kilogram (kg): up to 1 kg, normal, or no rounding</span></span></li>
</ul></li>
<li><span data-ttu-id="39cac-236"><strong>Report elettronico</strong> Consente di specificare i riferimenti alle configurazioni del report elettroniche, in modo da poter generare un file elettronico e un report.</span><span class="sxs-lookup"><span data-stu-id="39cac-236"><strong>Electronic reporting</strong> – Specify references to electronic reporting configurations, so that you can generate an electronic file and report.</span></span></li>
<li><span data-ttu-id="39cac-237"><strong>Gerarchia di codici di voce doganale</strong> Consente di specificare la gerarchia <strong>Codice di voce doganale</strong> di categorie di tipo che rappresenta il codice di voce doganale CN8 Intrastat.</span><span class="sxs-lookup"><span data-stu-id="39cac-237"><strong>Commodity code hierarchy</strong> – Specify the category hierarchy of the <strong>Commodity code</strong> type that represents Intrastat commodity code CN8.</span></span></li>
  <li> <span data-ttu-id="39cac-238"><strong>Tipo di tasso di cambio</strong> - Facoltativamente, specificare un tasso di cambio da utilizzare per dichiarare le vendite Intrastat e le transazioni di acquisto in valuta estera.</span><span class="sxs-lookup"><span data-stu-id="39cac-238"><strong>Exchange rate type</strong> – Optionally, specify an exchange rate to be used to report Intrastat sales and purchase transactions in foreign currencies.</span></span> <span data-ttu-id="39cac-239">Questa opzione viene utilizzata se il tasso è diverso da quello applicato quando si registra la transazione.</span><span class="sxs-lookup"><span data-stu-id="39cac-239">This is used if the rate is different than the one applied when posting the transaction.</span></span></li>  
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="39cac-240">Informazioni sul contatto agente</span><span class="sxs-lookup"><span data-stu-id="39cac-240">Agent contact information</span></span></td>
<td><span data-ttu-id="39cac-241">Specificare il nome, indirizzo, la partita IVA, il numero di telefono e il numero di fax agente.</span><span class="sxs-lookup"><span data-stu-id="39cac-241">Specify the agent&#39;s name, address, tax exempt number, telephone number, and fax number.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="39cac-242">Proprietà paese</span><span class="sxs-lookup"><span data-stu-id="39cac-242">Country/region properties</span></span></td>
<td><span data-ttu-id="39cac-243">Impostare il paese della persona giuridica corrente su <strong>Domestico</strong>.</span><span class="sxs-lookup"><span data-stu-id="39cac-243">Set the country/region of the current legal entity to <strong>Domestic</strong>.</span></span> <span data-ttu-id="39cac-244">Impostare il paese dei diversi paesi UE delle aree in cui partecipi al commercio UE alla persona giuridica corrente <strong>UE</strong>.</span><span class="sxs-lookup"><span data-stu-id="39cac-244">Set the country/region of EU countries/regions that participate in EU trade with the current legal entity to <strong>EU</strong>.</span></span> <span data-ttu-id="39cac-245">Per ogni paese, vengono identificate il codice paese per scopi di commercio estero.</span><span class="sxs-lookup"><span data-stu-id="39cac-245">For each country/region, you also identify country/region code for foreign trade purposes.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="39cac-246">Sequenza numerica</span><span class="sxs-lookup"><span data-stu-id="39cac-246">Number sequence</span></span></td>
<td><span data-ttu-id="39cac-247">Specificare la sequenza numerica del giornale di registrazione Intrastat.</span><span class="sxs-lookup"><span data-stu-id="39cac-247">Specify the number sequence for the Intrastat journal.</span></span></td>
</tr>
</tbody>
</table>

