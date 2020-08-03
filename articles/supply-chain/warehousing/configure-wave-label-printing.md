---
title: Configurare e utilizzare la stampa di etichette ondata
description: Questo argomento descrive la stampa di etichette ondata e spiega come configurarla.
author: GarmMSFT
manager: PJacobse
ms.date: 05/01/2020
ms.topic: configure-wave-label-printing
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSWaveLabel, WHSWaveLabelTemplate
audience: Application User
ms.reviewer: PJacobse
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: v-olbara
ms.search.validFrom: yyyy-mm-dd
ms.dyn365.ops.version: 10.0.0
ms.openlocfilehash: 49e0ef1b3020cd1236203c0f243f145dd7a7c10d
ms.sourcegitcommit: 137e2bd30f0a85bd2e1baf1cf16b993edd2094f9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2020
ms.locfileid: "3546441"
---
# <a name="set-up-and-use-wave-label-printing"></a><span data-ttu-id="57ca3-103">Configurare e utilizzare la stampa di etichette ondata</span><span class="sxs-lookup"><span data-stu-id="57ca3-103">Set up and use wave label printing</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="57ca3-104">La stampa di etichette ondata offre un approccio alternativo alla stampa di etichette introducendo un nuovo metodo di passaggio ondata che consente di creare e stampare etichette direttamente dal modello di ondata durante l'esecuzione dell'ondata.</span><span class="sxs-lookup"><span data-stu-id="57ca3-104">Wave label printing offers an alternative approach to label printing by introducing a new wave step method that lets you create and print labels directly from the wave template during wave execution.</span></span> <span data-ttu-id="57ca3-105">Pertanto, le etichette saranno già disponibili prima che i lavoratori eseguano l'ordine di lavoro su un dispositivo mobile.</span><span class="sxs-lookup"><span data-stu-id="57ca3-105">Therefore, the labels will already be available before workers run the work order on a mobile device.</span></span> <span data-ttu-id="57ca3-106">I lavoratori possono quindi associare le etichette necessarie durante il prelievo anziché dopo il prelievo.</span><span class="sxs-lookup"><span data-stu-id="57ca3-106">Workers can then attach the required labels during picking instead of after picking.</span></span>

<span data-ttu-id="57ca3-107">La stampa di etichette ondata utilizza Zebra Programming Language (ZPL) per creare layout di etichette.</span><span class="sxs-lookup"><span data-stu-id="57ca3-107">Wave label printing uses Zebra Programming Language (ZPL) to create label layouts.</span></span> <span data-ttu-id="57ca3-108">Un layout di etichetta è diviso in tre sezioni (intestazione, corpo e piè di pagina) per consentire etichette con struttura ripetuta.</span><span class="sxs-lookup"><span data-stu-id="57ca3-108">A label layout is divided into three sections (header, body, and footer) to allow for labels that have repeating structure.</span></span> <span data-ttu-id="57ca3-109">I modelli di etichette ondata indicano al sistema quale layout di etichetta utilizzare.</span><span class="sxs-lookup"><span data-stu-id="57ca3-109">Wave label templates tell the system which label layout to use.</span></span> <span data-ttu-id="57ca3-110">Gli utenti possono specificare quale stampante viene utilizzata.</span><span class="sxs-lookup"><span data-stu-id="57ca3-110">Users can specify which printer is used.</span></span> <span data-ttu-id="57ca3-111">Possono anche stampare etichette su più stampanti contemporaneamente, come necessario.</span><span class="sxs-lookup"><span data-stu-id="57ca3-111">They can also print labels on several printers at the same time, as they require.</span></span> <span data-ttu-id="57ca3-112">La pagina **Storico etichette ondata** mostra un record di tutte le etichette che sono state create utilizzando questa configurazione.</span><span class="sxs-lookup"><span data-stu-id="57ca3-112">The **Wave label history** page shows a record of all labels that have been created by using this setup.</span></span>

<span data-ttu-id="57ca3-113">È possibile stampare e fascicolare etichette in base alle intestazioni di lavoro, stampare etichette di interruzione per intestazione di lavoro e stampare etichette di contenuto di contenitore, etichette di cassa e altre etichette simili.</span><span class="sxs-lookup"><span data-stu-id="57ca3-113">You can print and collate labels based on work headers, you can print break labels per work header, and you can print container content labels, case labels, and other similar labels.</span></span>

> [!NOTE]
> <span data-ttu-id="57ca3-114">Questa funzionalità non sostituisce la funzionalità di stampa di etichette esistente basata sulla distribuzione dei documenti.</span><span class="sxs-lookup"><span data-stu-id="57ca3-114">This functionality doesn't replace existing label printing functionality that is based on document routing.</span></span>

<span data-ttu-id="57ca3-115">La stampa di etichette ondata offre i seguenti miglioramenti:</span><span class="sxs-lookup"><span data-stu-id="57ca3-115">Wave label printing offers the following enhancements:</span></span>

- <span data-ttu-id="57ca3-116">Stampa di etichette in base al numero di cartoni su una singola riga di lavoro, senza utilizzare la containerizzazione</span><span class="sxs-lookup"><span data-stu-id="57ca3-116">Print labels according to the number of cartons on a single work line, without using containerization.</span></span> <span data-ttu-id="57ca3-117">(un "cartone" è un'unità designata su righe di gruppi di sequenze di unità).</span><span class="sxs-lookup"><span data-stu-id="57ca3-117">(A "carton" is a unit that is designated on unit sequence group lines.)</span></span>
- <span data-ttu-id="57ca3-118">Stampa di diverse sequenze di etichette (ad esempio etichette di cartoni e pallet).</span><span class="sxs-lookup"><span data-stu-id="57ca3-118">Print several different label sequences (for example, carton and pallet labels).</span></span>
- <span data-ttu-id="57ca3-119">Inclusione dell'enumerazione di etichette (ad esempio, 1/124, 2/124, ... 124/124) e definizione dell'intervallo di enumerazione (ad esempio, riga di lavoro, riga di carico o spedizione).</span><span class="sxs-lookup"><span data-stu-id="57ca3-119">Include label enumeration (for example, 1/124, 2/124, ... 124/124), and define the range of enumeration (for example, work line, load line, or shipment).</span></span>
- <span data-ttu-id="57ca3-120">Creazione e stampa di un ID polizza di carico sulle etichette prima che venga generata la polizza di carico.</span><span class="sxs-lookup"><span data-stu-id="57ca3-120">Create and print a bill of lading ID on labels before the bill of lading is generated.</span></span>
- <span data-ttu-id="57ca3-121">Creazione di un codice SSCC univoco per ciascun cartone e inclusione in ciascuna etichetta.</span><span class="sxs-lookup"><span data-stu-id="57ca3-121">Create a unique serial shipping container code (SSCC) for each carton, and include it on each label.</span></span>
- <span data-ttu-id="57ca3-122">Creazione di sequenze numeriche conformi a GS1 per ID polizza di carico e SSCC.</span><span class="sxs-lookup"><span data-stu-id="57ca3-122">Create GS1-compliant number sequences for bill of lading IDs and SSCCs.</span></span>
- <span data-ttu-id="57ca3-123">Ristampa di etichette da dispositivi mobili e dal rich client.</span><span class="sxs-lookup"><span data-stu-id="57ca3-123">Reprint labels from both mobile devices and the rich client.</span></span>
- <span data-ttu-id="57ca3-124">Annullamento delle etichette (ad esempio, in scenari di prelievo in difetto) e ristampa delle stesse.</span><span class="sxs-lookup"><span data-stu-id="57ca3-124">Void labels (for example, in short pick scenarios), and reprint them.</span></span>
- <span data-ttu-id="57ca3-125">Pulire lo storico delle etichette ondata.</span><span class="sxs-lookup"><span data-stu-id="57ca3-125">Clean up the wave label history.</span></span>
- <span data-ttu-id="57ca3-126">I miglioramenti ai layout di distribuzione dei documenti sono condivisi tra i layout di distribuzione dei documenti e quelli delle etichette ondata</span><span class="sxs-lookup"><span data-stu-id="57ca3-126">Improvements to document routing layouts are shared between document routing layouts and wave label layouts.</span></span> <span data-ttu-id="57ca3-127">(per ulteriori informazioni, vedere [Layout di distribuzione dei documenti per le targhe](../warehousing/document-routing-layout-for-license-plates.md)).</span><span class="sxs-lookup"><span data-stu-id="57ca3-127">(For more information, see [Document routing layout for license plates](../warehousing/document-routing-layout-for-license-plates.md).)</span></span>

<span data-ttu-id="57ca3-128">Questi miglioramenti rendono più efficiente l'etichettatura dei cartoni prima della pallettizzazione.</span><span class="sxs-lookup"><span data-stu-id="57ca3-128">These enhancements make it more efficient to label cartons before palletization.</span></span> <span data-ttu-id="57ca3-129">Sono particolarmente utili per le aziende che spediscono a grandi rivenditori che confermano automaticamente la ricezione degli ordini sottoponendo a scansione ciascun cartone separatamente.</span><span class="sxs-lookup"><span data-stu-id="57ca3-129">They especially benefit companies that ship to large retailers that automatically confirm order receipts by scanning each carton separately.</span></span>

> [!NOTE]
> <span data-ttu-id="57ca3-130">È possibile implementare gli scenari di configurazione descritti in questo argomento separatamente o in combinazione, a seconda delle esigenze aziendali.</span><span class="sxs-lookup"><span data-stu-id="57ca3-130">You can implement the configuration scenarios that are described in this topic either separately or in combination, depending on your business requirements.</span></span> <span data-ttu-id="57ca3-131">È possibile progettare diversi modelli di etichette ondata che funzionano in sequenza (come illustrato nello scenario 3).</span><span class="sxs-lookup"><span data-stu-id="57ca3-131">You can design several wave label templates that work in sequence (as illustrated in scenario 3).</span></span> <span data-ttu-id="57ca3-132">Ad esempio, è possibile utilizzare lo scenario 1 per stampare etichette di cartoni e lo scenario 2 per stampare etichette di pallet (se i pallet in stock variano quanto a dimensioni e composizione).</span><span class="sxs-lookup"><span data-stu-id="57ca3-132">For example, you can use scenario 1 to print carton labels and scenario 2 to print pallet labels (if pallets in stock vary in size and composition).</span></span>

## <a name="turn-on-the-wave-label-printing-feature"></a><span data-ttu-id="57ca3-133">Attivare la funzionalità di stampa di etichette ondata</span><span class="sxs-lookup"><span data-stu-id="57ca3-133">Turn on the Wave label printing feature</span></span>

<span data-ttu-id="57ca3-134">Per poter utilizzare la funzionalità *Stampa di etichette ondata*, è necessario attivarla nel sistema.</span><span class="sxs-lookup"><span data-stu-id="57ca3-134">Before you can use the *Wave label printing* feature, it must be turned on in your system.</span></span> <span data-ttu-id="57ca3-135">Gli amministratori possono utilizzare l'area di lavoro [Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) per controllare lo stato della funzionalità e attivarla se necessario.</span><span class="sxs-lookup"><span data-stu-id="57ca3-135">Admins can use the [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) workspace to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="57ca3-136">Nell'area di lavoro, la funzionalità è elencata nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="57ca3-136">There, the feature is listed in the following way:</span></span>

- <span data-ttu-id="57ca3-137">**Modulo:** *Gestione Magazzino*</span><span class="sxs-lookup"><span data-stu-id="57ca3-137">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="57ca3-138">**Nome funzionalità:** *Stampa di etichette ondata*</span><span class="sxs-lookup"><span data-stu-id="57ca3-138">**Feature name:** *Wave label printing*</span></span>

## <a name="scenario-1-wave-label-printing-where-a-single-wave-label-is-generated"></a><span data-ttu-id="57ca3-139">Scenario 1: stampa di etichette ondata in cui viene generata una singola etichetta ondata</span><span class="sxs-lookup"><span data-stu-id="57ca3-139">Scenario 1: Wave label printing where a single wave label is generated</span></span>

<span data-ttu-id="57ca3-140">Questo scenario mostra come un'azienda può stampare etichette indirizzo per un grande rivenditore che conferma automaticamente la ricezione degli ordini sottoponendo a scansione ogni cartone separatamente.</span><span class="sxs-lookup"><span data-stu-id="57ca3-140">This scenario shows how a company can print shipping labels for a large retailer that automatically confirms order receipts by scanning each carton separately.</span></span>

<span data-ttu-id="57ca3-141">Questo scenario mostra il flusso end-to-end.</span><span class="sxs-lookup"><span data-stu-id="57ca3-141">This scenario shows the end-to-end flow.</span></span>

### <a name="make-demo-data-available"></a><span data-ttu-id="57ca3-142">Rendi disponibili i dati dimostrativi</span><span class="sxs-lookup"><span data-stu-id="57ca3-142">Make demo data available</span></span>

<span data-ttu-id="57ca3-143">Per eseguire questo scenario, i dati dimostrativi devono essere installati ed è necessario selezionare la persona giuridica **USMF**.</span><span class="sxs-lookup"><span data-stu-id="57ca3-143">To follow this scenario, you must have demo data installed, and you must select the **USMF** legal entity.</span></span>

### <a name="make-sure-that-the-wave-label-method-is-available"></a><span data-ttu-id="57ca3-144">Assicurarsi che il metodo di etichetta ondata sia disponibile</span><span class="sxs-lookup"><span data-stu-id="57ca3-144">Make sure that the wave label method is available</span></span>

<span data-ttu-id="57ca3-145">Potrebbe essere necessario rigenerare i metodi di elaborazione ondata per rendere disponibile il metodo di stampa di etichette ondata.</span><span class="sxs-lookup"><span data-stu-id="57ca3-145">You might have to regenerate the wave process methods to make the wave label printing method available.</span></span>

1. <span data-ttu-id="57ca3-146">Andare a **Gestione magazzino \> Impostazione \> Ondate \> Metodi di elaborazione ondata**.</span><span class="sxs-lookup"><span data-stu-id="57ca3-146">Go to **Warehouse management \> Setup \> Waves \> Wave process methods**.</span></span>
1. <span data-ttu-id="57ca3-147">Verificare che **waveLabelPrinting** sia nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="57ca3-147">Confirm that **waveLabelPrinting** is in the list.</span></span> <span data-ttu-id="57ca3-148">Se non lo è, selezionare **Rigenera metodi** nel riquadro azioni per aggiungerlo.</span><span class="sxs-lookup"><span data-stu-id="57ca3-148">If it isn't, select **Regenerate methods** on the Action Pane to add it.</span></span>

### <a name="configure-a-wave-template"></a><span data-ttu-id="57ca3-149">Configurare un modello di ondata</span><span class="sxs-lookup"><span data-stu-id="57ca3-149">Configure a wave template</span></span>

<span data-ttu-id="57ca3-150">I modelli di ondata consentono di collegare istanze specifiche dei metodi di ondata a un modello di etichetta ondata corrispondente.</span><span class="sxs-lookup"><span data-stu-id="57ca3-150">Wave templates let you link specific instances of wave methods to a corresponding wave label template.</span></span>

1. <span data-ttu-id="57ca3-151">Selezionare **Gestione magazzino \> Impostazioni \> Ondate \> Modelli ondata**.</span><span class="sxs-lookup"><span data-stu-id="57ca3-151">Go to **Warehouse management \> Setup \> Waves \> Wave templates**.</span></span>
1. <span data-ttu-id="57ca3-152">Selezionare un modello, ad esempio **62 Spedizione predefinita**.</span><span class="sxs-lookup"><span data-stu-id="57ca3-152">Select a template, such as **62 Shipping Default**.</span></span>
1. <span data-ttu-id="57ca3-153">Nella Scheda dettaglio **Metodi**, spostare il metodo **Stampa di etichette ondata** nella colonna **Metodi selezionati**.</span><span class="sxs-lookup"><span data-stu-id="57ca3-153">On the **Methods** FastTab, move the **Wave label printing** method to the **Selected methods** column.</span></span>
1. <span data-ttu-id="57ca3-154">Nella colonna **Metodi selezionati**, seleziona il metodo **Stampa di etichette ondata** e impostare il relativo campo **Codice passaggio ondata** su *PrintLabel*.</span><span class="sxs-lookup"><span data-stu-id="57ca3-154">In the **Selected methods** column, select the **Wave label printing** method, and set its **Wave step code** field to *PrintLabel*.</span></span> <span data-ttu-id="57ca3-155">Per ulteriori informazioni sui codici del passaggio ondata, vedere [Codici del passaggio ondata](wave-step-codes.md).</span><span class="sxs-lookup"><span data-stu-id="57ca3-155">For more information about wave step codes, see [Wave step codes](wave-step-codes.md).</span></span>

### <a name="create-a-wave-label-layout"></a><span data-ttu-id="57ca3-156">Creare un layout di etichetta ondata</span><span class="sxs-lookup"><span data-stu-id="57ca3-156">Create a wave label layout</span></span>

<span data-ttu-id="57ca3-157">Il layout di etichetta controlla quali informazioni sono stampate sull'etichetta e come sono disposte. Nel layout si inserisce il codice ZPL inviato alla stampante.</span><span class="sxs-lookup"><span data-stu-id="57ca3-157">The label layout controls what information is printed on the label and how it's laid out. Here, you enter the ZPL code that is sent to the printer.</span></span>

1. <span data-ttu-id="57ca3-158">Andare a **Gestione magazzino \> Impostazioni \> Distribuzione documenti \> Layout etichette ondata**.</span><span class="sxs-lookup"><span data-stu-id="57ca3-158">Go to **Warehouse management \> Setup \> Document routing \> Wave label layouts**.</span></span>
1. <span data-ttu-id="57ca3-159">Crea un record con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="57ca3-159">Create a record that has the following settings:</span></span>

    - <span data-ttu-id="57ca3-160">**ID layout etichetta:** *Cartone*</span><span class="sxs-lookup"><span data-stu-id="57ca3-160">**Label layout ID:** *Carton*</span></span>
    - <span data-ttu-id="57ca3-161">**Descrizione:** *Cartone (SSCC)*</span><span class="sxs-lookup"><span data-stu-id="57ca3-161">**Description:** *Carton (SSCC)*</span></span>

1. <span data-ttu-id="57ca3-162">Nel riquadro azioni selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="57ca3-162">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="57ca3-163">Nel riquadro azioni selezionare **Impostazioni di riga delle etichette ondata**.</span><span class="sxs-lookup"><span data-stu-id="57ca3-163">On the Action Pane, select **Wave label row settings**.</span></span>

    <span data-ttu-id="57ca3-164">Viene visualizzata la pagina **Impostazioni di riga delle etichette ondata**.</span><span class="sxs-lookup"><span data-stu-id="57ca3-164">The **Wave label row settings** page appears.</span></span> <span data-ttu-id="57ca3-165">Qui è possibile configurare la parte dinamica dell'etichetta.</span><span class="sxs-lookup"><span data-stu-id="57ca3-165">Here, you can configure the dynamic part of the label.</span></span>

1. <span data-ttu-id="57ca3-166">Aggiungere una riga con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="57ca3-166">Add a row that has the following settings:</span></span>

    - <span data-ttu-id="57ca3-167">**ID riga:** *WaveLabel*</span><span class="sxs-lookup"><span data-stu-id="57ca3-167">**Row Id:** *WaveLabel*</span></span>
    - <span data-ttu-id="57ca3-168">**Nome tabella di righe:** *WHSWaveLabel*</span><span class="sxs-lookup"><span data-stu-id="57ca3-168">**Row table name:** *WHSWaveLabel*</span></span>
    - <span data-ttu-id="57ca3-169">**Posizione di inizio riga:** *0*</span><span class="sxs-lookup"><span data-stu-id="57ca3-169">**Row start position:** *0*</span></span>

        <span data-ttu-id="57ca3-170">Questo campo definisce la posizione verticale iniziale della riga sull'etichetta.</span><span class="sxs-lookup"><span data-stu-id="57ca3-170">This field defines the vertical position where the row will begin on the label.</span></span>

    - <span data-ttu-id="57ca3-171">**Altezza riga:** *0*</span><span class="sxs-lookup"><span data-stu-id="57ca3-171">**Row height:** *0*</span></span>

        <span data-ttu-id="57ca3-172">Questo campo definisce l'altezza di ogni riga (in punti), secondo lo standard ZPL.</span><span class="sxs-lookup"><span data-stu-id="57ca3-172">This field defines the height of each row (in points), according to the ZPL standard.</span></span> <span data-ttu-id="57ca3-173">L'altezza della riga è positiva per le etichette orizzontali e negativa per le etichette verticali.</span><span class="sxs-lookup"><span data-stu-id="57ca3-173">The row height is positive for horizontal labels and negative for vertical labels.</span></span> <span data-ttu-id="57ca3-174">Poiché in questo esempio c'è una sola riga, è possibile impostare il valore su *0* (zero).</span><span class="sxs-lookup"><span data-stu-id="57ca3-174">Because there is just one row in this example, you can set the value to *0* (zero).</span></span>

    - <span data-ttu-id="57ca3-175">**Righe per pagina:** *1*</span><span class="sxs-lookup"><span data-stu-id="57ca3-175">**Rows per page:** *1*</span></span>

        <span data-ttu-id="57ca3-176">Questo campo definisce il numero di righe che è possibile stampare su ciascuna etichetta.</span><span class="sxs-lookup"><span data-stu-id="57ca3-176">This field defines the number of rows that can be printed on each label.</span></span>

        > [!NOTE]
        > <span data-ttu-id="57ca3-177">Questa impostazione causerà la stampa di un'etichetta ZPL separata per ciascun record nella tabella delle etichette ondata.</span><span class="sxs-lookup"><span data-stu-id="57ca3-177">This setup will cause a separate ZPL label to be printed for each record in the wave labels table.</span></span>

1. <span data-ttu-id="57ca3-178">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="57ca3-178">Close the page.</span></span>
1. <span data-ttu-id="57ca3-179">Nel riquadro azioni, seleziona **Modifica query**.</span><span class="sxs-lookup"><span data-stu-id="57ca3-179">On the Action Pane, select **Edit query**.</span></span>
1. <span data-ttu-id="57ca3-180">Nella finestra di dialogo dell'editor di query, nella scheda **Intervallo**, aggiungere una riga con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="57ca3-180">In the query editor dialog box, on the **Range** tab, add a row that has the following settings:</span></span>

    - <span data-ttu-id="57ca3-181">**Tabella:** *Righe di lavoro*</span><span class="sxs-lookup"><span data-stu-id="57ca3-181">**Table:** *Work lines*</span></span>
    - <span data-ttu-id="57ca3-182">**Tabella derivata:** *Righe di lavoro*</span><span class="sxs-lookup"><span data-stu-id="57ca3-182">**Derived table:** *Work lines*</span></span>
    - <span data-ttu-id="57ca3-183">**Campo:** *Tipo di lavoro*</span><span class="sxs-lookup"><span data-stu-id="57ca3-183">**Field:** *Work type*</span></span>
    - <span data-ttu-id="57ca3-184">**Criteri:** *Prelievo*</span><span class="sxs-lookup"><span data-stu-id="57ca3-184">**Criteria:** *Pick*</span></span>

    <span data-ttu-id="57ca3-185">Questa query garantisce che sull'etichetta vengano stampate solo le righe di lavoro di tipo prelievo, non le righe di lavoro di tipo stoccaggio.</span><span class="sxs-lookup"><span data-stu-id="57ca3-185">This query ensures that only pick-type work lines will be printed on the label, not put-type work lines.</span></span>

1. <span data-ttu-id="57ca3-186">Se si desidera poter stampare l'ID polizza di carico, nella scheda **Join**, selezionare la tabella **Righe lavoro** e unirvi la tabella **Spedizioni**.</span><span class="sxs-lookup"><span data-stu-id="57ca3-186">If you want to be able to print the bill of lading ID, on the **Joins** tab, select the **Work lines** table, and join the **Shipments** table to it.</span></span>
1. <span data-ttu-id="57ca3-187">Chiudere la finestra di dialogo dell'editor di query.</span><span class="sxs-lookup"><span data-stu-id="57ca3-187">Close the query editor dialog box.</span></span>
1. <span data-ttu-id="57ca3-188">La Scheda dettaglio **Layout testo stampante** ha tre sezioni in cui è possibile scrivere il codice della stampante: **Sezione di intestazione**, **Sezione del corpo** e **Sezione piè di pagina**.</span><span class="sxs-lookup"><span data-stu-id="57ca3-188">The **Printer text Layout** FastTab has three sections where you can write printer code: **Header section**, **Body section**, and **Footer section**.</span></span> <span data-ttu-id="57ca3-189">Nella sezione **Sezione di intestazione**, nel campo **Intestazione etichetta**, immettere il codice per l'intestazione necessaria.</span><span class="sxs-lookup"><span data-stu-id="57ca3-189">In the **Header section** section, in the **Label header** field, enter code for the required header.</span></span> <span data-ttu-id="57ca3-190">Ad esempio, se si utilizzano stampanti Zebra, è possibile utilizzare il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="57ca3-190">For example, if you're using Zebra printers, you can use the following code.</span></span>

    ```plaintext
    CT~~CD,~CC^~CT~
    ^XA~TA000~JSN^LT0^MNW^MTT^PON^PMN^LH0,0^JMA^PR8,8~SD15^JUS^LRN^CI0^XZ
    ^XA
    ^MMT
    ^PW812
    ^LL1218
    ^LS0
    ^FT85,505^A0N,28,28^FH\^FD$WHSShipmentTable.CustomerReq$^FS
    ^FO1,173^GB809,0,1^FS
    ^FO0,391^GB809,0,1^FS
    ^FO3,599^GB809,0,2^FS
    ^FO420,176^GB0,216,1^FS
    ^FO313,3^GB0,169,1^FS
    ^FO0,807^GB809,0,1^FS
    ^FT529,370^A0N,28,26^FH\^FD$WHSShipmentTable.BillOfLadingId$^FS
    ^BY2,3,132^FT25,344^BCN,,N,N
    ^FD>:(420)>38102>63^FS
    ^FT526,315^A0N,28,28^FH\^FD ^FS
    ^FT437,248^A0N,28,28^FH\^FDCARR: $WHSShipmentTable.SCAC$^FS
    ^FT425,201^A0N,23,24^FH\^FDCARRIER:^FS
    ^FT17,68^A0N,20,19^FH\^FDIntershipping, Inc.^FS
    ^FT15,99^A0N,20,19^FH\^FD1000 Shipping Lane^FS
    ^FT16,158^A0N,20,19^FH\^FD ^FS
    ^FT438,368^A0N,28,28^FH\^FDB/L#^FS
    ^FT15,128^A0N,20,19^FH\^FDShelbyville TN 38102^FS
    ^FT19,203^A0N,23,24^FH\^FD(420) SHIP TO POSTAL CODE^FS
    ^FT331,39^A0N,28,28^FH\^FDShip To:^FS
    ^FT14,39^A0N,28,28^FH\^FDShip From:^FS
    ^FT331,67^A0N,23,24^FH\^FDWAL-MART DC 1111A-ABC DIS^FS
    ^FT330,98^A0N,23,24^FH\^FDDEPT 10^FS
    ^FT329,166^A0N,23,24^FH\^FDSpringfield TN 39021^FS
    ^FT330,134^A0N,23,24^FH\^FD100 Main Street^FS
    ^FT19,504^A0N,28,28^FH\^FDPO#:^FS
    ^FT437,316^A0N,28,28^FH\^FDPRO#^FS
    ^FT105,371^A0N,28,28^FB130,1,0,C^FH\^FD(420)39021^FS
    ```

1. <span data-ttu-id="57ca3-191">Nella sezione **Sezione del corpo**, nel campo **Corpo etichetta**, immettere il codice ZPL per il corpo necessario.</span><span class="sxs-lookup"><span data-stu-id="57ca3-191">In the **Body section** section, in the **Label body** field, enter ZPL code for the required body.</span></span> <span data-ttu-id="57ca3-192">Ecco un esempio.</span><span class="sxs-lookup"><span data-stu-id="57ca3-192">Here is an example.</span></span>

    ```plaintext
    <Row name="WaveLabel">
    ^FT127,439^A0N,28,28^FH\^FD$WHSWaveLabel.SeqNum$^FS
    ^FT256,439^A0N,28,28^FH\^FD$WHSWaveLabel.NumberOfLabels$^FS
    ^FT17,439^A0N,28,28^FH\^FDCARTON^FS
    ^FT522,422^A0N,23,24^FH\^FDVPN:^FS
    ^FT74,1156^A0N,28,28^FH\^FDSSCC-18^FS
    ^FT21,579^A0N,28,28^FH\^FDItem name:^FS
    ^FT107,580^A0N,28,28^FH\^FD$WHSWaveLabel.LabelItemName$^FS
    ^FT576,423^A0N,23,21^FH\^FD$WHSWaveLabel.LabelItemId$^FS
    ^FT252,1155^A0N,32,31^FH\^FD(00)$WHSWaveLabel.WaveLabelId$^FS
    ^BY4,3,283^FT66,1115^BCN,,N,N
    ^FD>;>800$WHSWaveLabel.WaveLabelId$^FS
    ^FT194,439^A0N,28,28^FH\^FDof^FS
    </Row>
    ```

1. <span data-ttu-id="57ca3-193">Nella sezione **Sezione del corpo**, nel campo **Piè di pagina etichetta**, immettere il codice ZPL per il piè di pagina necessario.</span><span class="sxs-lookup"><span data-stu-id="57ca3-193">In the **Body section** section, in the **Label footer** field, enter ZPL code for the required footer.</span></span> <span data-ttu-id="57ca3-194">Ecco un esempio.</span><span class="sxs-lookup"><span data-stu-id="57ca3-194">Here is an example.</span></span>

    ```plaintext
    ^PQ1^XZ
    ```

    > [!NOTE]
    > <span data-ttu-id="57ca3-195">Questa configurazione stamperà una copia di ciascuna etichetta.</span><span class="sxs-lookup"><span data-stu-id="57ca3-195">This setup will print one copy of each label.</span></span> <span data-ttu-id="57ca3-196">Se sono necessarie più copie (ad esempio una copia per ciascun lato del pallet), impostare il valore **n** per la sezione **\^PQn** nel piè di pagina sul numero di copie necessarie.</span><span class="sxs-lookup"><span data-stu-id="57ca3-196">If you require more copies (for example, one copy for each side of the pallet), set the **n** value for the **\^PQn** section in the footer to the required number of copies.</span></span> <span data-ttu-id="57ca3-197">Ad esempio, per stampare quattro copie di ciascuna etichetta, specificare **\^PQ4**.</span><span class="sxs-lookup"><span data-stu-id="57ca3-197">For example, to print four copies of each label, specify **\^PQ4**.</span></span>

<span data-ttu-id="57ca3-198">L'etichetta è ora pronta per l'uso.</span><span class="sxs-lookup"><span data-stu-id="57ca3-198">Your label is now ready to use.</span></span>

### <a name="create-a-wave-label-type"></a><span data-ttu-id="57ca3-199">Creare un tipo di etichetta ondata</span><span class="sxs-lookup"><span data-stu-id="57ca3-199">Create a wave label type</span></span>

<span data-ttu-id="57ca3-200">I tipi di etichetta ondata vengono utilizzati per collegare modelli di etichette ondata a un'unità su righe di gruppi di sequenze unità.</span><span class="sxs-lookup"><span data-stu-id="57ca3-200">Wave label types are used to link wave label templates to a unit on unit sequence group lines.</span></span>

1. <span data-ttu-id="57ca3-201">Andare a **Gestione magazzino \> Impostazioni \> Distribuzione documenti \> Tipi di etichette ondata**.</span><span class="sxs-lookup"><span data-stu-id="57ca3-201">Go to **Warehouse management \> Setup \> Document routing \> Wave label types**.</span></span>
1. <span data-ttu-id="57ca3-202">Aggiungere un tipo di etichetta ondata con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="57ca3-202">Add a wave label type that has the following settings:</span></span>

    - <span data-ttu-id="57ca3-203">**Tipo di etichetta:** *Cartone*</span><span class="sxs-lookup"><span data-stu-id="57ca3-203">**Label type:** *Carton*</span></span>
    - <span data-ttu-id="57ca3-204">**Descrizione:** *Cartone*</span><span class="sxs-lookup"><span data-stu-id="57ca3-204">**Description:** *Carton*</span></span>

### <a name="set-up-unit-sequence-groups"></a><span data-ttu-id="57ca3-205">Imposta gruppi di sequenze unità</span><span class="sxs-lookup"><span data-stu-id="57ca3-205">Set up unit sequence groups</span></span>

<span data-ttu-id="57ca3-206">Quindi, impostare il gruppo di sequenze di unità per il tipo di etichetta ondata.</span><span class="sxs-lookup"><span data-stu-id="57ca3-206">Next, set up the unit sequence group for the wave label type.</span></span>

1. <span data-ttu-id="57ca3-207">Fare clic su **Gestione magazzino \> Impostazione \> Magazzino \> Gruppi di sequenze unità**.</span><span class="sxs-lookup"><span data-stu-id="57ca3-207">Go to **Warehouse management \> Setup \> Warehouse \> Unit sequence groups**.</span></span>
1. <span data-ttu-id="57ca3-208">Selezionare il gruppo **unità scatola pallet**.</span><span class="sxs-lookup"><span data-stu-id="57ca3-208">Select the **Ea Box PL** group.</span></span>
1. <span data-ttu-id="57ca3-209">Per la riga **Scatola**, impostare il campo **Tipo di livello ondata** su *Scatola*.</span><span class="sxs-lookup"><span data-stu-id="57ca3-209">For the **Box** line, set the **Wave level type** field to *Carton*.</span></span>

### <a name="create-a-wave-label-template"></a><span data-ttu-id="57ca3-210">Creare un modello di etichetta ondata</span><span class="sxs-lookup"><span data-stu-id="57ca3-210">Create a wave label template</span></span>

<span data-ttu-id="57ca3-211">Ora si creerà il modello di etichetta ondata per il tipo di etichetta ondata.</span><span class="sxs-lookup"><span data-stu-id="57ca3-211">Next, create the wave label template for the wave label type.</span></span>

1. <span data-ttu-id="57ca3-212">Andare a **Gestione magazzino \> Impostazioni \> Distribuzione documenti \> Modelli di etichette ondata**.</span><span class="sxs-lookup"><span data-stu-id="57ca3-212">Go to **Warehouse management \> Setup \> Document routing \> Wave label templates**.</span></span>
1. <span data-ttu-id="57ca3-213">Aggiungere un modello di livello ondata e impostare i seguenti valori nell'intestazione:</span><span class="sxs-lookup"><span data-stu-id="57ca3-213">Add a wave level template, and set the following values in the header:</span></span>

    - <span data-ttu-id="57ca3-214">**Nome modello etichetta:** *Etichette cartoni*</span><span class="sxs-lookup"><span data-stu-id="57ca3-214">**Label template name:** *Carton labels*</span></span>
    - <span data-ttu-id="57ca3-215">**Descrizione:** *Etichette cartoni*</span><span class="sxs-lookup"><span data-stu-id="57ca3-215">**Description:** *Carton labels*</span></span>
    - <span data-ttu-id="57ca3-216">**Codice passaggio ondata:** *PrintLabel*</span><span class="sxs-lookup"><span data-stu-id="57ca3-216">**Wave step code:** *PrintLabel*</span></span>
    - <span data-ttu-id="57ca3-217">**Magazzino:** *62*</span><span class="sxs-lookup"><span data-stu-id="57ca3-217">**Warehouse:** *62*</span></span>

1. <span data-ttu-id="57ca3-218">Nella Scheda dettaglio**Generale**, impostare il campo **Tipo di etichetta ondata** su *Cartone*.</span><span class="sxs-lookup"><span data-stu-id="57ca3-218">On the **General** FastTab, set the **Wave label type** field to *Carton*.</span></span>
1. <span data-ttu-id="57ca3-219">Nella Scheda dettaglio **Dettagli modello di etichette ondata**, aggiungere una nuova riga con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="57ca3-219">On the **Wave label template details** FastTab, add a new row that has the following settings:</span></span>

    - <span data-ttu-id="57ca3-220">**ID layout etichetta:** *Cartone*</span><span class="sxs-lookup"><span data-stu-id="57ca3-220">**Label layout ID:** *Carton*</span></span>
    - <span data-ttu-id="57ca3-221">**Nome stampante:** selezionare una stampante ZPL appropriata.</span><span class="sxs-lookup"><span data-stu-id="57ca3-221">**Printer name:** Select an appropriate ZPL printer.</span></span>
    - <span data-ttu-id="57ca3-222">**Esegui query:** *Sì* (questa impostazione è facoltativa, ma è consigliata per prestazioni ottimali).</span><span class="sxs-lookup"><span data-stu-id="57ca3-222">**Run query:** *Yes* (This setting is optional, but it's recommended for optimal performance.)</span></span>

1. <span data-ttu-id="57ca3-223">Nel riquadro azioni selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="57ca3-223">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="57ca3-224">Facoltativo: se si sta progettando un'etichetta specifica per il cliente, è necessario creare una query per trovare il conto del cliente.</span><span class="sxs-lookup"><span data-stu-id="57ca3-224">Optional: If you're setting up a customer-specific label design, you must create a query to find the customer's account.</span></span> <span data-ttu-id="57ca3-225">Nella scheda dettaglio **Dettagli modello di etichette ondata**, selezionare **Modifica query**.</span><span class="sxs-lookup"><span data-stu-id="57ca3-225">On the **Wave label template details** FastTab, select **Edit query**.</span></span> <span data-ttu-id="57ca3-226">Quindi, nella finestra di dialogo dell'editor di query, nella scheda **Intervallo**, aggiungere una riga con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="57ca3-226">Then, in the query editor dialog box, on the **Range** tab, add a row that has the following settings:</span></span>

    - <span data-ttu-id="57ca3-227">**Tabella:** *Spedizioni*</span><span class="sxs-lookup"><span data-stu-id="57ca3-227">**Table:** *Shipments*</span></span>
    - <span data-ttu-id="57ca3-228">**Tabella derivata:** *Spedizioni*</span><span class="sxs-lookup"><span data-stu-id="57ca3-228">**Derived table:** *Shipments*</span></span>
    - <span data-ttu-id="57ca3-229">**Campo:** *Numero di conto*</span><span class="sxs-lookup"><span data-stu-id="57ca3-229">**Field:** *Account number*</span></span>
    - <span data-ttu-id="57ca3-230">**Criteri:** Immettere il numero di conto cliente pertinente.</span><span class="sxs-lookup"><span data-stu-id="57ca3-230">**Criteria:** Enter the relevant customer account number.</span></span>

    <span data-ttu-id="57ca3-231">Al termine, selezionare **OK** per chiudere la finestra di dialogo dell'editor di query.</span><span class="sxs-lookup"><span data-stu-id="57ca3-231">When you've finished, select **OK** to close the query editor dialog box.</span></span>

1. <span data-ttu-id="57ca3-232">Nel riquadro azioni, selezionare **Modifica query** per aprire la finestra di dialogo dell'editor di query per l'intero modello di etichetta.</span><span class="sxs-lookup"><span data-stu-id="57ca3-232">On the Action Pane, select **Edit query** to open the query editor dialog box for the whole label template.</span></span>
1. <span data-ttu-id="57ca3-233">Nella finestra di dialogo dell'editor di query, nella scheda **Ordinamento**, aggiungere una riga con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="57ca3-233">In the query editor dialog box, on the **Sorting** tab, add a row that has the following settings:</span></span>

    - <span data-ttu-id="57ca3-234">**Tabella:** *Righe di lavoro*</span><span class="sxs-lookup"><span data-stu-id="57ca3-234">**Table:** *Work lines*</span></span>
    - <span data-ttu-id="57ca3-235">**Tabella derivata:** *Righe di lavoro*</span><span class="sxs-lookup"><span data-stu-id="57ca3-235">**Derived table:** *Work lines*</span></span>
    - <span data-ttu-id="57ca3-236">**Campo:** *ID riga di carico di riferimento (ID record)*</span><span class="sxs-lookup"><span data-stu-id="57ca3-236">**Field:** *Reference load line id (Record-ID)*</span></span>
    - <span data-ttu-id="57ca3-237">**Direzione di ricerca:** *Crescente*</span><span class="sxs-lookup"><span data-stu-id="57ca3-237">**Search direction:** *Ascending*</span></span>

1. <span data-ttu-id="57ca3-238">Selezionare **OK** per chiudere la finestra di dialogo dell'editor di query.</span><span class="sxs-lookup"><span data-stu-id="57ca3-238">Select **OK** to close the query editor dialog box.</span></span>
1. <span data-ttu-id="57ca3-239">Viene visualizzato un messaggio che richiede di confermare l'operazione di ripristino del raggruppamento.</span><span class="sxs-lookup"><span data-stu-id="57ca3-239">A message box prompts you to confirm the grouping reset operation.</span></span> <span data-ttu-id="57ca3-240">Selezionare **Sì** per continuare.</span><span class="sxs-lookup"><span data-stu-id="57ca3-240">Select **Yes** to continue.</span></span>
1. <span data-ttu-id="57ca3-241">Nel riquadro azioni selezionare **Gruppo di modelli di etichette ondata**.</span><span class="sxs-lookup"><span data-stu-id="57ca3-241">On the Action Pane, select **Wave label template group**.</span></span>
1. <span data-ttu-id="57ca3-242">Nella finestra di dialogo **Gruppo di modelli di etichette ondata**, selezionare la riga in cui il campo **Nome campo di riferimento** è impostato su *ID riga di carico di riferimento*, quindi selezionare la casella di controllo **ID build etichetta** per questa riga.</span><span class="sxs-lookup"><span data-stu-id="57ca3-242">In the **Wave label template group** dialog box, select the row where the **Reference field name** field is set to *Reference load line id*, and then select the **Label build ID** check box for this row.</span></span>

    > [!NOTE]
    > <span data-ttu-id="57ca3-243">Questa configurazione creerà una sequenza di etichette ("Cartone 1 di X") per riga di carico in tutta l'ondata, indipendentemente dall'impostazione del raggruppamento di lavoro.</span><span class="sxs-lookup"><span data-stu-id="57ca3-243">This setup will create one label sequence ("Carton 1 of X") per load line throughout the wave, regardless of the work grouping setup.</span></span> <span data-ttu-id="57ca3-244">Questa sequenza di etichette può essere stampata sul layout di etichetta.</span><span class="sxs-lookup"><span data-stu-id="57ca3-244">This label sequence can be printed on the label layout.</span></span>

### <a name="configure-number-sequence-extensions"></a><span data-ttu-id="57ca3-245">Configurare le estensioni di sequenza numerica</span><span class="sxs-lookup"><span data-stu-id="57ca3-245">Configure number sequence extensions</span></span>

<span data-ttu-id="57ca3-246">Le estensioni di sequenza numerica controllano la conformità GS1 delle sequenze numeriche specifiche.</span><span class="sxs-lookup"><span data-stu-id="57ca3-246">Number sequence extensions control the GS1 compliance of specific number sequences.</span></span> <span data-ttu-id="57ca3-247">Questa configurazione è facoltativa per lo scenario corrente.</span><span class="sxs-lookup"><span data-stu-id="57ca3-247">This configuration is optional for the current scenario.</span></span> <span data-ttu-id="57ca3-248">Per ulteriori informazioni e istruzioni sulla configurazione, vedere [Configurare le estensioni di sequenza numerica](../warehousing/configure-number-sequence-extensions.md).</span><span class="sxs-lookup"><span data-stu-id="57ca3-248">For more information and configuration instructions, see [Configure number sequence extensions](../warehousing/configure-number-sequence-extensions.md).</span></span>

### <a name="create-a-sales-order-and-release-it-to-the-warehouse"></a><span data-ttu-id="57ca3-249">Creare un ordine cliente e rilasciarlo nel magazzino</span><span class="sxs-lookup"><span data-stu-id="57ca3-249">Create a sales order and release it to the warehouse</span></span>

1. <span data-ttu-id="57ca3-250">Andare a **Vendite e marketing \> Ordine cliente \> Tutti gli ordini cliente**.</span><span class="sxs-lookup"><span data-stu-id="57ca3-250">Go to **Sales and marketing \> Sales order \> All sales orders**.</span></span>
1. <span data-ttu-id="57ca3-251">Crea un ordine cliente con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="57ca3-251">Create a sales order that has the following settings:</span></span>

    - <span data-ttu-id="57ca3-252">**Conto cliente:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="57ca3-252">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="57ca3-253">**Magazzino:** *62*</span><span class="sxs-lookup"><span data-stu-id="57ca3-253">**Warehouse:** *62*</span></span>

1. <span data-ttu-id="57ca3-254">Aggiungere due righe di ordine cliente con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="57ca3-254">Add two sales order lines that have the following settings:</span></span>

    - <span data-ttu-id="57ca3-255">Riga ordine cliente 1:</span><span class="sxs-lookup"><span data-stu-id="57ca3-255">Sales order line 1:</span></span>

        - <span data-ttu-id="57ca3-256">**Numero articolo:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="57ca3-256">**Item number:** *A0001*</span></span>
        - <span data-ttu-id="57ca3-257">**Quantità:** *9024*</span><span class="sxs-lookup"><span data-stu-id="57ca3-257">**Quantity:** *9024*</span></span>
        - <span data-ttu-id="57ca3-258">**Unità:** *unità* (9024 unità = 376 scatole = 47 pallet)</span><span class="sxs-lookup"><span data-stu-id="57ca3-258">**Unit:** *ea* (9024 ea = 376 Box = 47 PL)</span></span>

    - <span data-ttu-id="57ca3-259">Riga ordine cliente 2:</span><span class="sxs-lookup"><span data-stu-id="57ca3-259">Sales order line 2:</span></span>

        - <span data-ttu-id="57ca3-260">**Numero articolo:** *A0002*</span><span class="sxs-lookup"><span data-stu-id="57ca3-260">**Item number:** *A0002*</span></span>
        - <span data-ttu-id="57ca3-261">**Quantità:** *9016*</span><span class="sxs-lookup"><span data-stu-id="57ca3-261">**Quantity:** *9016*</span></span>
        - <span data-ttu-id="57ca3-262">**Unità:** *unità* (9016 unità = 322 scatole = 46 pallet)</span><span class="sxs-lookup"><span data-stu-id="57ca3-262">**Unit:** *ea* (9016 ea = 322 Box = 46 PL)</span></span>

    > [!NOTE]
    > <span data-ttu-id="57ca3-263">Gli articoli e le quantità forniti qui sono solo esempi.</span><span class="sxs-lookup"><span data-stu-id="57ca3-263">The items and quantities that are provided here are only examples.</span></span> <span data-ttu-id="57ca3-264">Devono utilizzare il gruppo di sequenze di unità definito in precedenza, conversioni di unità appropriate da *unità* a *scatola* a *pallet* devono essere definite per gli stessi e devono avere stock nel magazzino *62*.</span><span class="sxs-lookup"><span data-stu-id="57ca3-264">They must use the unit sequence group that you defined earlier, appropriate unit conversions from *ea* to *Box* to *PL* must be defined for them, and they must have stock in warehouse *62*.</span></span> <span data-ttu-id="57ca3-265">Per ulteriori informazioni, vedere [Unità di misura e politiche di stoccaggio](unit-measure-stocking-policies.md).</span><span class="sxs-lookup"><span data-stu-id="57ca3-265">For more information, see [Unit of measure and stocking policies](unit-measure-stocking-policies.md).</span></span>

1. <span data-ttu-id="57ca3-266">Selezionare la riga ordine cliente 1.</span><span class="sxs-lookup"><span data-stu-id="57ca3-266">Select sales order line 1.</span></span> <span data-ttu-id="57ca3-267">Nella sezione **Riga ordine cliente**, nel menu **Scorte**, selezionare **Prenotazioni**.</span><span class="sxs-lookup"><span data-stu-id="57ca3-267">Then, in the **Sales order line** section, on the **Inventory** menu, select **Reservations**.</span></span>
1. <span data-ttu-id="57ca3-268">Nella pagina **Prenotazione** del riquadro azioni, selezionare **Prenota lotto** e chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="57ca3-268">On the **Reservation** page, on the Action Pane, select **Reserve lot**, and then close the page.</span></span>
1. <span data-ttu-id="57ca3-269">Ripetere i passaggi 4 e 5 per la riga ordine cliente 2.</span><span class="sxs-lookup"><span data-stu-id="57ca3-269">Repeat steps 4 and 5 for sales order line 2.</span></span>
1. <span data-ttu-id="57ca3-270">Nel riquadro azioni, nella scheda **Magazzino**, seleziona **Rilascia in magazzino**.</span><span class="sxs-lookup"><span data-stu-id="57ca3-270">On the Action Pane, on the **Warehouse** tab, select **Release to warehouse**.</span></span>

    <span data-ttu-id="57ca3-271">Si verificano gli eventi seguenti:</span><span class="sxs-lookup"><span data-stu-id="57ca3-271">The following events occur:</span></span>

    - <span data-ttu-id="57ca3-272">Il sistema elabora la spedizione creata utilizzando il modello che include il passaggio di stampa dell'etichetta.</span><span class="sxs-lookup"><span data-stu-id="57ca3-272">The system processes the created shipment by using the template that includes the label printing step.</span></span> <span data-ttu-id="57ca3-273">Il layout di etichetta verrà utilizzato per definire il formato dell'etichetta e il risultato sarà un'etichetta stampata sulla stampante selezionata nel modello di etichetta.</span><span class="sxs-lookup"><span data-stu-id="57ca3-273">The label layout will be used to define the format of the label, and the result will be a label that is printed on the printer that is selected in the label template.</span></span>
    - <span data-ttu-id="57ca3-274">Le etichette ondata vengono generate e stampate.</span><span class="sxs-lookup"><span data-stu-id="57ca3-274">Wave labels are generated and printed.</span></span> <span data-ttu-id="57ca3-275">Il numero di etichette sarà uguale al numero di cartoni (in questo esempio, 376 etichette per scatole per la riga 1 e 322 etichette per scatole per la riga 2).</span><span class="sxs-lookup"><span data-stu-id="57ca3-275">The number of labels will equal the number of cartons (in this example, 376 Box labels for line 1 and 322 Box labels for line 2).</span></span>
    - <span data-ttu-id="57ca3-276">Viene generato un nuovo ID polizza di carico per le spedizioni.</span><span class="sxs-lookup"><span data-stu-id="57ca3-276">A new bill of lading ID is generated for the shipments.</span></span> <span data-ttu-id="57ca3-277">Se sono state configurate le estensioni della sequenza numerica, gli ID etichetta ondata avranno il formato numerico **SSCC-18**.</span><span class="sxs-lookup"><span data-stu-id="57ca3-277">If you configured the number sequence extensions, the wave label IDs will follow the **SSCC-18** number format.</span></span> 

<span data-ttu-id="57ca3-278">È possibile visualizzare e ristampare le etichette ondata dalle seguenti pagine.</span><span class="sxs-lookup"><span data-stu-id="57ca3-278">You can view and reprint wave labels from the following pages.</span></span> <span data-ttu-id="57ca3-279">Nel riquadro azioni di ogni pagina della scheda **Spedizioni** nel gruppo **Informazioni correlate**, selezionare **Etichette ondata**.</span><span class="sxs-lookup"><span data-stu-id="57ca3-279">On the Action Pane of each page, on the **Shipments** tab, in the **Related information** group, select **Wave labels**.</span></span>

- <span data-ttu-id="57ca3-280">Tutte le spedizioni \> Dettagli spedizione</span><span class="sxs-lookup"><span data-stu-id="57ca3-280">All shipments \> Shipment details</span></span>
- <span data-ttu-id="57ca3-281">Tutti i carichi \> Dettagli carico</span><span class="sxs-lookup"><span data-stu-id="57ca3-281">All loads \> Load details</span></span>
- <span data-ttu-id="57ca3-282">Tutte le ondate</span><span class="sxs-lookup"><span data-stu-id="57ca3-282">All waves</span></span>
- <span data-ttu-id="57ca3-283">Etichette ondata</span><span class="sxs-lookup"><span data-stu-id="57ca3-283">Wave labels</span></span>
- <span data-ttu-id="57ca3-284">Storico etichette ondata</span><span class="sxs-lookup"><span data-stu-id="57ca3-284">Wave label history</span></span>

## <a name="scenario-2-wave-label-printing-for-containerization-without-wave-label-records"></a><span data-ttu-id="57ca3-285">Scenario 2: stampa di etichette ondata per containerizzazione (senza record di etichette ondata)</span><span class="sxs-lookup"><span data-stu-id="57ca3-285">Scenario 2: Wave label printing for containerization (without wave label records)</span></span>

<span data-ttu-id="57ca3-286">Questo scenario consente di stampare etichette ondata quando si utilizza la containerizzazione per suddividere automaticamente gli articoli in cartoni e quindi non è necessario un record di etichette ondata.</span><span class="sxs-lookup"><span data-stu-id="57ca3-286">This scenario lets you print wave labels when you use containerization to automatically split items into cartons and therefore don't require a wave label record.</span></span> <span data-ttu-id="57ca3-287">In questo caso, l'ID contenitore funge da segnaposto per SSCC.</span><span class="sxs-lookup"><span data-stu-id="57ca3-287">In this case, the container ID acts as a placeholder for the SSCC.</span></span>

<span data-ttu-id="57ca3-288">Di seguito sono riportate le principali differenze tra questo scenario e lo scenario 1:</span><span class="sxs-lookup"><span data-stu-id="57ca3-288">Here are the main differences between this scenario and scenario 1:</span></span>

- <span data-ttu-id="57ca3-289">**Modelli di etichette ondata:** non si selezionerà un tipo di etichetta ondata nel modello di etichetta ondata e non sarà necessario un raggruppamento di build di etichetta.</span><span class="sxs-lookup"><span data-stu-id="57ca3-289">**Wave label templates:** You won't select a wave label type on the wave label template, and you won't require a label build grouping.</span></span> <span data-ttu-id="57ca3-290">Altrimenti, si configurerà il modello di etichetta ondata e si eseguirà il collegamento al modello di ondata nello stesso modo descritto nello scenario 1.</span><span class="sxs-lookup"><span data-stu-id="57ca3-290">Otherwise, you will configure the wave label template and link to the wave template in the same way that is described in scenario 1.</span></span> <span data-ttu-id="57ca3-291">È necessario lasciare vuoto il tipo di etichetta ondata per impedire la generazione di etichette ondata.</span><span class="sxs-lookup"><span data-stu-id="57ca3-291">You must leave the wave label type blank to prevent wave labels from being generated.</span></span>
- <span data-ttu-id="57ca3-292">**Layout etichette ondata:** si configureranno le impostazioni delle righe del layout di etichetta ondata per le righe di lavoro anziché i record di etichetta ondata.</span><span class="sxs-lookup"><span data-stu-id="57ca3-292">**Wave label layouts:** You will configure the wave label layout row settings for work lines instead of wave label records.</span></span> <span data-ttu-id="57ca3-293">È necessario configurare l'impostazione della riga per il layout di etichetta utilizzando la tabella **WHSWorkLine** anziché la tabella **WHSWaveLabel**.</span><span class="sxs-lookup"><span data-stu-id="57ca3-293">You must configure the row setting for the label layout by using the **WHSWorkLine** table instead of the **WHSWaveLabel** table.</span></span> <span data-ttu-id="57ca3-294">L'impostazione **Righe per pagina** controlla il numero di righe che avrà la sezione del corpo.</span><span class="sxs-lookup"><span data-stu-id="57ca3-294">The **Rows per page** setting controls the number of rows that the body section will have.</span></span> 

<span data-ttu-id="57ca3-295">Questa configurazione è adatta anche per scenari aziendali in cui più articoli diversi sono imballati in una scatola etichettata o in un pallet e questo processo di imballaggio può essere definito dalla creazione di lavoro (ad esempio, lavoro raggruppato per spedizione).</span><span class="sxs-lookup"><span data-stu-id="57ca3-295">This configuration is also suitable for business scenarios where multiple different items are packed into one labeled box or into a pallet, and this packing process can be defined by work creation (for example, work that is grouped by shipment).</span></span>

<span data-ttu-id="57ca3-296">Questo scenario mostra il flusso end-to-end.</span><span class="sxs-lookup"><span data-stu-id="57ca3-296">This scenario shows the end-to-end flow.</span></span>

### <a name="make-demo-data-available"></a><span data-ttu-id="57ca3-297">Rendi disponibili i dati dimostrativi</span><span class="sxs-lookup"><span data-stu-id="57ca3-297">Make demo data available</span></span>

<span data-ttu-id="57ca3-298">Per eseguire questo scenario, i dati dimostrativi devono essere installati ed è necessario selezionare la persona giuridica **USMF**.</span><span class="sxs-lookup"><span data-stu-id="57ca3-298">To follow this scenario, you must have demo data installed, and you must select the **USMF** legal entity.</span></span>

### <a name="make-sure-that-the-wave-label-method-is-available"></a><span data-ttu-id="57ca3-299">Assicurarsi che il metodo di etichetta ondata sia disponibile</span><span class="sxs-lookup"><span data-stu-id="57ca3-299">Make sure that the wave label method is available</span></span>

<span data-ttu-id="57ca3-300">Potrebbe essere necessario rigenerare i metodi di elaborazione ondata per rendere disponibile il metodo di stampa di etichette ondata.</span><span class="sxs-lookup"><span data-stu-id="57ca3-300">You might have to regenerate the wave process methods to make the wave label printing method available.</span></span>

1. <span data-ttu-id="57ca3-301">Andare a **Gestione magazzino \> Impostazione \> Ondate \> Metodi di elaborazione ondata**.</span><span class="sxs-lookup"><span data-stu-id="57ca3-301">Go to **Warehouse management \> Setup \> Waves \> Wave process methods**.</span></span>
1. <span data-ttu-id="57ca3-302">Verificare che **waveLabelPrinting** sia nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="57ca3-302">Confirm that **waveLabelPrinting** is in the list.</span></span> <span data-ttu-id="57ca3-303">Se non lo è, selezionare **Rigenera metodi** nel riquadro azioni per aggiungerlo.</span><span class="sxs-lookup"><span data-stu-id="57ca3-303">If it isn't, select **Regenerate methods** on the Action Pane to add it.</span></span>

### <a name="set-up-a-wave-template"></a><span data-ttu-id="57ca3-304">Impostare un modello di ondata</span><span class="sxs-lookup"><span data-stu-id="57ca3-304">Set up a wave template</span></span>

<span data-ttu-id="57ca3-305">I modelli di ondata consentono di collegare istanze specifiche dei metodi di ondata a un modello di etichetta ondata corrispondente.</span><span class="sxs-lookup"><span data-stu-id="57ca3-305">Wave templates let you link specific instances of wave methods to a corresponding wave label template.</span></span>

1. <span data-ttu-id="57ca3-306">Selezionare **Gestione magazzino \> Impostazioni \> Ondate \> Modelli ondata**.</span><span class="sxs-lookup"><span data-stu-id="57ca3-306">Go to **Warehouse management \> Setup \> Waves \> Wave templates**.</span></span>
1. <span data-ttu-id="57ca3-307">Selezionare un modello, ad esempio **Contaneirizzazione 63**.</span><span class="sxs-lookup"><span data-stu-id="57ca3-307">Select a template, such as **63 Containerization**.</span></span>
1. <span data-ttu-id="57ca3-308">Nella Scheda dettaglio **Metodi**, spostare il metodo **Stampa di etichette ondata** nella colonna **Metodi selezionati**.</span><span class="sxs-lookup"><span data-stu-id="57ca3-308">On the **Methods** FastTab, move the **Wave label printing** method to the **Selected methods** column.</span></span>
1. <span data-ttu-id="57ca3-309">Nella colonna **Metodi selezionati**, seleziona il metodo **Stampa di etichette ondata** e impostare il relativo campo **Codice passaggio ondata** su *PrintLabel*.</span><span class="sxs-lookup"><span data-stu-id="57ca3-309">In the **Selected methods** column, select the **Wave label printing** method, and set its **Wave step code** field to *PrintLabel*.</span></span> <span data-ttu-id="57ca3-310">Per ulteriori informazioni sui codici del passaggio ondata, vedere [Codici del passaggio ondata](wave-step-codes.md).</span><span class="sxs-lookup"><span data-stu-id="57ca3-310">For more information about wave step codes, see [Wave step codes](wave-step-codes.md).</span></span>

### <a name="create-a-wave-label-layout"></a><span data-ttu-id="57ca3-311">Creare un layout di etichetta ondata</span><span class="sxs-lookup"><span data-stu-id="57ca3-311">Create a wave label layout</span></span>

1. <span data-ttu-id="57ca3-312">Andare a **Gestione magazzino \> Impostazioni \> Distribuzione documenti \> Layout etichette ondata**.</span><span class="sxs-lookup"><span data-stu-id="57ca3-312">Go to **Warehouse management \> Setup \> Document routing \> Wave label layouts**.</span></span>
1. <span data-ttu-id="57ca3-313">Crea un record con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="57ca3-313">Create a record that has the following settings:</span></span>

    - <span data-ttu-id="57ca3-314">**ID layout etichetta:** *Cartone*</span><span class="sxs-lookup"><span data-stu-id="57ca3-314">**Label layout ID:** *Carton*</span></span>
    - <span data-ttu-id="57ca3-315">**Descrizione:** *Cartone (SSCC)*</span><span class="sxs-lookup"><span data-stu-id="57ca3-315">**Description:** *Carton (SSCC)*</span></span>

1. <span data-ttu-id="57ca3-316">Nel riquadro azioni selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="57ca3-316">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="57ca3-317">Nel riquadro azioni selezionare **Impostazioni di riga delle etichette ondata**.</span><span class="sxs-lookup"><span data-stu-id="57ca3-317">On the Action Pane, select **Wave label row settings**.</span></span>

    <span data-ttu-id="57ca3-318">Viene visualizzata la pagina **Impostazioni di riga delle etichette ondata**.</span><span class="sxs-lookup"><span data-stu-id="57ca3-318">The **Wave label row settings** page appears.</span></span> <span data-ttu-id="57ca3-319">Qui è possibile configurare la parte dinamica dell'etichetta.</span><span class="sxs-lookup"><span data-stu-id="57ca3-319">Here, you can configure the dynamic part of the label.</span></span>

1. <span data-ttu-id="57ca3-320">Aggiungere una riga con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="57ca3-320">Add a row that has the following settings:</span></span>

    - <span data-ttu-id="57ca3-321">**ID riga:** *WorkLine*</span><span class="sxs-lookup"><span data-stu-id="57ca3-321">**Row Id:** *WorkLine*</span></span>
    - <span data-ttu-id="57ca3-322">**Nome tabella di righe:** *WHSWorkLine*</span><span class="sxs-lookup"><span data-stu-id="57ca3-322">**Row table name:** *WHSWorkLine*</span></span>
    - <span data-ttu-id="57ca3-323">**Posizione di inizio riga:** *500*</span><span class="sxs-lookup"><span data-stu-id="57ca3-323">**Row start position:** *500*</span></span>

        <span data-ttu-id="57ca3-324">Questo campo definisce la posizione verticale iniziale della riga sull'etichetta.</span><span class="sxs-lookup"><span data-stu-id="57ca3-324">This field defines the vertical position where the row will begin on the label.</span></span>

    - <span data-ttu-id="57ca3-325">**Altezza riga:** *-50*</span><span class="sxs-lookup"><span data-stu-id="57ca3-325">**Row height:** *-50*</span></span>

        <span data-ttu-id="57ca3-326">Questo campo definisce l'altezza di ogni riga.</span><span class="sxs-lookup"><span data-stu-id="57ca3-326">This field defines the height of each row.</span></span> <span data-ttu-id="57ca3-327">L'altezza della riga è positiva per le etichette orizzontali e negativa per le etichette verticali.</span><span class="sxs-lookup"><span data-stu-id="57ca3-327">The row height is positive for horizontal labels and negative for vertical labels.</span></span>

    - <span data-ttu-id="57ca3-328">**Righe per pagina:** *5*</span><span class="sxs-lookup"><span data-stu-id="57ca3-328">**Rows per page:** *5*</span></span>

        <span data-ttu-id="57ca3-329">Questo campo definisce il numero di righe che è possibile stampare su ciascuna etichetta.</span><span class="sxs-lookup"><span data-stu-id="57ca3-329">This field defines the number of rows that can be printed on each label.</span></span>

        > [!NOTE]
        > <span data-ttu-id="57ca3-330">Questa configurazione stamperà diverse etichette ZPL per lavoro, dove ogni pagina può contenere fino a cinque righe di lavoro.</span><span class="sxs-lookup"><span data-stu-id="57ca3-330">This setup will print several ZPL labels per work, where each page can hold up to five work lines.</span></span> <span data-ttu-id="57ca3-331">Ad esempio, se un'etichetta viene stampata per un contenitore che ha 12 righe, verranno stampate tre etichette.</span><span class="sxs-lookup"><span data-stu-id="57ca3-331">For example, if a label is printed for a container that has 12 lines, three labels will be printed.</span></span> <span data-ttu-id="57ca3-332">Se si desidera stampare un'etichetta separata per ogni riga di prelievo, impostare questo valore su *1*.</span><span class="sxs-lookup"><span data-stu-id="57ca3-332">If you want to print a separate label for each pick line, set this value to *1*.</span></span>

1. <span data-ttu-id="57ca3-333">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="57ca3-333">Close the page.</span></span>
1. <span data-ttu-id="57ca3-334">Nel riquadro azioni, seleziona **Modifica query**.</span><span class="sxs-lookup"><span data-stu-id="57ca3-334">On the Action Pane, select **Edit query**.</span></span>
1. <span data-ttu-id="57ca3-335">Nella finestra di dialogo dell'editor di query, nella scheda **Intervallo**, aggiungere una riga con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="57ca3-335">In the query editor dialog box, on the **Range** tab, add a row that has the following settings:</span></span>

    - <span data-ttu-id="57ca3-336">**Tabella:** *Righe di lavoro*</span><span class="sxs-lookup"><span data-stu-id="57ca3-336">**Table:** *Work lines*</span></span>
    - <span data-ttu-id="57ca3-337">**Tabella derivata:** *Righe di lavoro*</span><span class="sxs-lookup"><span data-stu-id="57ca3-337">**Derived table:** *Work lines*</span></span>
    - <span data-ttu-id="57ca3-338">**Campo:** *Tipo di lavoro*</span><span class="sxs-lookup"><span data-stu-id="57ca3-338">**Field:** *Work type*</span></span>
    - <span data-ttu-id="57ca3-339">**Criteri:** *Prelievo*</span><span class="sxs-lookup"><span data-stu-id="57ca3-339">**Criteria:** *Pick*</span></span>

1. <span data-ttu-id="57ca3-340">Se si desidera poter stampare l'ID polizza di carico, nella scheda **Join**, selezionare la tabella **Righe lavoro** e unirvi la tabella **Spedizioni**.</span><span class="sxs-lookup"><span data-stu-id="57ca3-340">If you want to be able to print the bill of lading ID, on the **Joins** tab, select the **Work lines** table, and join the **Shipments** table to it.</span></span>
1. <span data-ttu-id="57ca3-341">Chiudere la finestra di dialogo dell'editor di query.</span><span class="sxs-lookup"><span data-stu-id="57ca3-341">Close the query editor dialog box.</span></span>
1. <span data-ttu-id="57ca3-342">La Scheda dettaglio **Layout testo stampante** ha tre sezioni in cui è possibile scrivere il codice della stampante: **Sezione di intestazione**, **Sezione del corpo** e **Sezione piè di pagina**.</span><span class="sxs-lookup"><span data-stu-id="57ca3-342">The **Printer text Layout** FastTab has three sections where you can write printer code: **Header section**, **Body section**, and **Footer section**.</span></span> <span data-ttu-id="57ca3-343">Nella sezione **Sezione di intestazione**, nel campo **Intestazione etichetta**, immettere il codice per l'intestazione necessaria.</span><span class="sxs-lookup"><span data-stu-id="57ca3-343">In the **Header section** section, in the **Label header** field, enter code for the required header.</span></span> <span data-ttu-id="57ca3-344">Ad esempio, se si utilizzano stampanti Zebra, è possibile utilizzare il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="57ca3-344">For example, if you're using Zebra printers, you can use the following code.</span></span>

    ```plaintext
    CT~~CD,~CC^~CT~
    ^XA
    ^LH10,10
    ^FO0,0 ^AT ^FD$WHSWorkTable.ContainerId$ ^FS
    ^FO0,75 ^AT ^FD$WHSWorkLine.ShipmentId$ ^FS
    ^FO0,150 ^AT ^FD$WHSShipmentTable.BillOfLadingId$ ^FS
    ```

1. <span data-ttu-id="57ca3-345">Nella sezione **Sezione del corpo**, nel campo **Corpo etichetta**, immettere il codice ZPL per il corpo necessario.</span><span class="sxs-lookup"><span data-stu-id="57ca3-345">In the **Body section** section, in the **Label body** field, enter ZPL code for the required body.</span></span> <span data-ttu-id="57ca3-346">Ecco un esempio.</span><span class="sxs-lookup"><span data-stu-id="57ca3-346">Here is an example.</span></span>

    ```plaintext
    <Row name="WorkLine">
    <Heading>
    //Optional heading for section of rows
    </Heading>
    ^FO0,450 ^AT ^FDItem ^FS
    ^FO200,450 ^AT ^FDQuantity ^FS
    ^FO0,[[YPos]] ^AT ^FD$WHSWorkLine.ItemId$ ^FS
    ^FO200,[[YPos]] ^AT ^FD$WHSWorkLine.QtyWork$ ^FS
    </Row>
    ```

1. <span data-ttu-id="57ca3-347">Nella sezione **Sezione del corpo**, nel campo **Piè di pagina etichetta**, immettere il codice ZPL per il piè di pagina necessario.</span><span class="sxs-lookup"><span data-stu-id="57ca3-347">In the **Body section** section, in the **Label footer** field, enter ZPL code for the required footer.</span></span> <span data-ttu-id="57ca3-348">Ecco un esempio.</span><span class="sxs-lookup"><span data-stu-id="57ca3-348">Here is an example.</span></span>

    ```plaintext
    ^PQ1^XZ
    ```

    > [!NOTE]
    > <span data-ttu-id="57ca3-349">Questa configurazione stamperà una copia di ciascuna etichetta.</span><span class="sxs-lookup"><span data-stu-id="57ca3-349">This setup will print one copy of each label.</span></span> <span data-ttu-id="57ca3-350">Se sono necessarie più copie (ad esempio una copia per ciascun lato del pallet), impostare il valore **n** per la sezione **\^PQn** nel piè di pagina sul numero di copie necessarie.</span><span class="sxs-lookup"><span data-stu-id="57ca3-350">If you require more copies (for example, one copy for each side of the pallet), set the **n** value for the **\^PQn** section in the footer to the required number of copies.</span></span> <span data-ttu-id="57ca3-351">Ad esempio, per stampare quattro copie di ciascuna etichetta, specificare **\^PQ4**.</span><span class="sxs-lookup"><span data-stu-id="57ca3-351">For example, to print four copies of each label, specify **\^PQ4**.</span></span>

<span data-ttu-id="57ca3-352">L'etichetta è ora pronta per l'uso.</span><span class="sxs-lookup"><span data-stu-id="57ca3-352">Your label is now ready to use.</span></span>

### <a name="create-a-wave-label-template"></a><span data-ttu-id="57ca3-353">Creare un modello di etichetta ondata</span><span class="sxs-lookup"><span data-stu-id="57ca3-353">Create a wave label template</span></span>

1. <span data-ttu-id="57ca3-354">Andare a **Gestione magazzino \> Impostazioni \> Distribuzione documenti \> Modelli di etichette ondata**.</span><span class="sxs-lookup"><span data-stu-id="57ca3-354">Go to **Warehouse management \> Setup \> Document routing \> Wave label templates**.</span></span>
1. <span data-ttu-id="57ca3-355">Aggiungere un modello di livello ondata e impostare i seguenti valori nell'intestazione:</span><span class="sxs-lookup"><span data-stu-id="57ca3-355">Add a wave level template, and set the following values in the header:</span></span>

    - <span data-ttu-id="57ca3-356">**Nome modello etichetta:** *Etichette contenitori*</span><span class="sxs-lookup"><span data-stu-id="57ca3-356">**Label template name:** *Container labels*</span></span>
    - <span data-ttu-id="57ca3-357">**Descrizione:** *Etichette contenitori*</span><span class="sxs-lookup"><span data-stu-id="57ca3-357">**Description:** *Container labels*</span></span>
    - <span data-ttu-id="57ca3-358">**Codice passaggio ondata:** *PrintLabel*</span><span class="sxs-lookup"><span data-stu-id="57ca3-358">**Wave step code:** *PrintLabel*</span></span>
    - <span data-ttu-id="57ca3-359">**Magazzino:** *63*</span><span class="sxs-lookup"><span data-stu-id="57ca3-359">**Warehouse:** *63*</span></span>

1. <span data-ttu-id="57ca3-360">Nella Scheda dettaglio **Dettagli modello di etichette ondata**, aggiungere una riga con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="57ca3-360">On the **Wave label template details** FastTab, add a row that has the following settings:</span></span>

    - <span data-ttu-id="57ca3-361">**ID layout etichetta:** *Contenitore*</span><span class="sxs-lookup"><span data-stu-id="57ca3-361">**Label layout ID:** *Container*</span></span>
    - <span data-ttu-id="57ca3-362">**Nome stampante:** selezionare una stampante ZPL appropriata.</span><span class="sxs-lookup"><span data-stu-id="57ca3-362">**Printer name:** Select an appropriate ZPL printer.</span></span>
    - <span data-ttu-id="57ca3-363">**Esegui query:** *Sì* (questa impostazione è facoltativa, ma è consigliata per prestazioni ottimali).</span><span class="sxs-lookup"><span data-stu-id="57ca3-363">**Run query:** *Yes* (This setting is optional, but it's recommended for optimal performance.)</span></span>

1. <span data-ttu-id="57ca3-364">Nel riquadro azioni selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="57ca3-364">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="57ca3-365">Facoltativo: se si sta progettando un'etichetta specifica per il cliente, è necessario creare una query per trovare il conto del cliente.</span><span class="sxs-lookup"><span data-stu-id="57ca3-365">Optional: If you're setting up a customer-specific label design, you must create a query to find the customer's account.</span></span> <span data-ttu-id="57ca3-366">Nella scheda dettaglio **Dettagli modello di etichette ondata**, selezionare **Modifica query**.</span><span class="sxs-lookup"><span data-stu-id="57ca3-366">On the **Wave label template details** FastTab, select **Edit query**.</span></span> <span data-ttu-id="57ca3-367">Quindi, nella finestra di dialogo dell'editor di query, nella scheda **Intervallo**, aggiungere una riga con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="57ca3-367">Then, in the query editor dialog box, on the **Range** tab, add a row that has the following settings:</span></span>

    - <span data-ttu-id="57ca3-368">**Tabella:** *Spedizioni*</span><span class="sxs-lookup"><span data-stu-id="57ca3-368">**Table:** *Shipments*</span></span>
    - <span data-ttu-id="57ca3-369">**Tabella derivata:** *Spedizioni*</span><span class="sxs-lookup"><span data-stu-id="57ca3-369">**Derived table:** *Shipments*</span></span>
    - <span data-ttu-id="57ca3-370">**Campo:** *Numero di conto*</span><span class="sxs-lookup"><span data-stu-id="57ca3-370">**Field:** *Account number*</span></span>
    - <span data-ttu-id="57ca3-371">**Criteri:** Immettere il numero di conto cliente pertinente.</span><span class="sxs-lookup"><span data-stu-id="57ca3-371">**Criteria:** Enter the relevant customer account number.</span></span>

    <span data-ttu-id="57ca3-372">Al termine, selezionare **OK** per chiudere la finestra di dialogo dell'editor di query.</span><span class="sxs-lookup"><span data-stu-id="57ca3-372">When you've finished, select **OK** to close the query editor dialog box.</span></span>

### <a name="configure-number-sequence-extensions"></a><span data-ttu-id="57ca3-373">Configurare le estensioni di sequenza numerica</span><span class="sxs-lookup"><span data-stu-id="57ca3-373">Configure number sequence extensions</span></span>

<span data-ttu-id="57ca3-374">Le estensioni di sequenza numerica controllano la conformità GS1 delle sequenze numeriche specifiche.</span><span class="sxs-lookup"><span data-stu-id="57ca3-374">Number sequence extensions control the GS1 compliance of specific number sequences.</span></span> <span data-ttu-id="57ca3-375">Questa configurazione è facoltativa per lo scenario corrente.</span><span class="sxs-lookup"><span data-stu-id="57ca3-375">This configuration is optional for the current scenario.</span></span> <span data-ttu-id="57ca3-376">Per ulteriori informazioni e istruzioni sulla configurazione, vedere [Configurare le estensioni di sequenza numerica](../warehousing/configure-number-sequence-extensions.md).</span><span class="sxs-lookup"><span data-stu-id="57ca3-376">For more information and configuration instructions, see [Configure number sequence extensions](../warehousing/configure-number-sequence-extensions.md).</span></span>

### <a name="create-a-sales-order-and-release-it-to-the-warehouse"></a><span data-ttu-id="57ca3-377">Creare un ordine cliente e rilasciarlo nel magazzino</span><span class="sxs-lookup"><span data-stu-id="57ca3-377">Create a sales order and release it to the warehouse</span></span>

1. <span data-ttu-id="57ca3-378">Andare a **Vendite e marketing \> Ordine cliente \> Tutti gli ordini cliente**.</span><span class="sxs-lookup"><span data-stu-id="57ca3-378">Go to **Sales and marketing \> Sales order \> All sales orders**.</span></span>
1. <span data-ttu-id="57ca3-379">Crea un ordine cliente con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="57ca3-379">Create a sales order that has the following settings:</span></span>

    - <span data-ttu-id="57ca3-380">**Conto cliente:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="57ca3-380">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="57ca3-381">**Magazzino:** *63*</span><span class="sxs-lookup"><span data-stu-id="57ca3-381">**Warehouse:** *63*</span></span>

1. <span data-ttu-id="57ca3-382">Aggiungere cinque righe ordine cliente:</span><span class="sxs-lookup"><span data-stu-id="57ca3-382">Add five sales order lines:</span></span>

    - <span data-ttu-id="57ca3-383">Riga ordine cliente 1:</span><span class="sxs-lookup"><span data-stu-id="57ca3-383">Sales order line 1:</span></span>

        - <span data-ttu-id="57ca3-384">**Numero articolo:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="57ca3-384">**Item number:** *A0001*</span></span>
        - <span data-ttu-id="57ca3-385">**Quantità:** *10*</span><span class="sxs-lookup"><span data-stu-id="57ca3-385">**Quantity:** *10*</span></span>

    - <span data-ttu-id="57ca3-386">Riga ordine cliente 2:</span><span class="sxs-lookup"><span data-stu-id="57ca3-386">Sales order line 2:</span></span>

        - <span data-ttu-id="57ca3-387">**Numero articolo:** *A0002*</span><span class="sxs-lookup"><span data-stu-id="57ca3-387">**Item number:** *A0002*</span></span>
        - <span data-ttu-id="57ca3-388">**Quantità:** *20*</span><span class="sxs-lookup"><span data-stu-id="57ca3-388">**Quantity:** *20*</span></span>

    - <span data-ttu-id="57ca3-389">Riga ordine cliente 3:</span><span class="sxs-lookup"><span data-stu-id="57ca3-389">Sales order line 3:</span></span>

        - <span data-ttu-id="57ca3-390">**Numero articolo:** *L0006*</span><span class="sxs-lookup"><span data-stu-id="57ca3-390">**Item number:** *L0006*</span></span>
        - <span data-ttu-id="57ca3-391">**Quantità:** *20*</span><span class="sxs-lookup"><span data-stu-id="57ca3-391">**Quantity:** *20*</span></span>

    - <span data-ttu-id="57ca3-392">Riga ordine cliente 4:</span><span class="sxs-lookup"><span data-stu-id="57ca3-392">Sales order line 4:</span></span>

        - <span data-ttu-id="57ca3-393">**Numero articolo:** *L0100*</span><span class="sxs-lookup"><span data-stu-id="57ca3-393">**Item number:** *L0100*</span></span>
        - <span data-ttu-id="57ca3-394">**Quantità:** *40*</span><span class="sxs-lookup"><span data-stu-id="57ca3-394">**Quantity:** *40*</span></span>

    - <span data-ttu-id="57ca3-395">Riga ordine cliente 5:</span><span class="sxs-lookup"><span data-stu-id="57ca3-395">Sales order line 5:</span></span>

        - <span data-ttu-id="57ca3-396">**Numero articolo:** *L0101*</span><span class="sxs-lookup"><span data-stu-id="57ca3-396">**Item number:** *L0101*</span></span>
        - <span data-ttu-id="57ca3-397">**Quantità:** *50*</span><span class="sxs-lookup"><span data-stu-id="57ca3-397">**Quantity:** *50*</span></span>

    > [!NOTE]
    > <span data-ttu-id="57ca3-398">Gli articoli e le quantità forniti qui sono solo esempi.</span><span class="sxs-lookup"><span data-stu-id="57ca3-398">The items and quantities that are provided here are only examples.</span></span> <span data-ttu-id="57ca3-399">Devono disporre di scorte nel magazzino specificato.</span><span class="sxs-lookup"><span data-stu-id="57ca3-399">They must have stock in the specified warehouse.</span></span>

1. <span data-ttu-id="57ca3-400">Selezionare la riga ordine cliente 1.</span><span class="sxs-lookup"><span data-stu-id="57ca3-400">Select sales order line 1.</span></span> <span data-ttu-id="57ca3-401">Nella sezione **Riga ordine cliente**, nel menu **Scorte**, selezionare **Prenotazioni**.</span><span class="sxs-lookup"><span data-stu-id="57ca3-401">Then, in the **Sales order line** section, on the **Inventory** menu, select **Reservations**.</span></span>
1. <span data-ttu-id="57ca3-402">Nella pagina **Prenotazione** del riquadro azioni, selezionare **Prenota lotto** e chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="57ca3-402">On the **Reservation** page, on the Action Pane, select **Reserve lot**, and then close the page.</span></span>
1. <span data-ttu-id="57ca3-403">Ripetere i passaggi 4 e 5 per ogni riga ordine cliente aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="57ca3-403">Repeat steps 4 and 5 for each additional sales order line.</span></span>
1. <span data-ttu-id="57ca3-404">Nel riquadro azioni, nella scheda **Magazzino**, seleziona **Rilascia in magazzino**.</span><span class="sxs-lookup"><span data-stu-id="57ca3-404">On the Action Pane, on the **Warehouse** tab, select **Release to warehouse**.</span></span>

    <span data-ttu-id="57ca3-405">Si verificano gli eventi seguenti:</span><span class="sxs-lookup"><span data-stu-id="57ca3-405">The following events occur:</span></span>

    - <span data-ttu-id="57ca3-406">Il sistema elabora la spedizione creata utilizzando il modello che include il passaggio di stampa dell'etichetta.</span><span class="sxs-lookup"><span data-stu-id="57ca3-406">The system processes the created shipment using the template that includes the label printing step.</span></span> <span data-ttu-id="57ca3-407">Il layout di etichetta verrà utilizzato per definire il formato dell'etichetta e il risultato finale sarà un'etichetta con cinque righe stampata sulla stampante selezionata nel modello di etichetta.</span><span class="sxs-lookup"><span data-stu-id="57ca3-407">The label layout will be used to define the format of the label, and the end result will be a label that has five lines and that is printed on the printer that is selected in the label template.</span></span>
    - <span data-ttu-id="57ca3-408">Viene generato un nuovo ID polizza di carico per le spedizioni.</span><span class="sxs-lookup"><span data-stu-id="57ca3-408">A new bill of lading ID is generated for the shipments.</span></span> <span data-ttu-id="57ca3-409">Se sono state configurate le estensioni della sequenza numerica, gli ID etichetta ondata avranno il formato numerico **SSCC-18**.</span><span class="sxs-lookup"><span data-stu-id="57ca3-409">If you configured the number sequence extensions, the wave label IDs will follow the **SSCC-18** number format.</span></span> 

<span data-ttu-id="57ca3-410">È possibile ristampare queste etichette ondata selezionando **Gestione magazzino \> Richieste e rapporti \>Storico etichetta ondata**.</span><span class="sxs-lookup"><span data-stu-id="57ca3-410">You can reprint these wave labels by going to **Warehouse management \> Inquiries and reports \> Wave label history**.</span></span>

## <a name="scenario-3-wave-label-printing-for-multi-tiered-labels"></a><span data-ttu-id="57ca3-411">Scenario 3: stampa di etichette ondata per etichette a più livelli</span><span class="sxs-lookup"><span data-stu-id="57ca3-411">Scenario 3: Wave label printing for multi-tiered labels</span></span>

<span data-ttu-id="57ca3-412">Questo scenario mostra come utilizzare la funzionalità di stampa di etichette ondata quando i processi di magazzino richiedono diversi livelli di etichette indirizzo.</span><span class="sxs-lookup"><span data-stu-id="57ca3-412">This scenario shows how to use the wave label printing functionality when the warehousing processes require several tiers of shipping labels.</span></span> <span data-ttu-id="57ca3-413">Ad esempio, potrebbe essere necessario stampare etichette separate per cartoni e pallet e stampare un'etichetta di interruzione per un'intera spedizione.</span><span class="sxs-lookup"><span data-stu-id="57ca3-413">For example, separate labels might have to be printed for cartons and pallets, and a break label might have to be printed for a whole shipment.</span></span> <span data-ttu-id="57ca3-414">Le etichette di interruzione sono un tipo distinto di etichetta che può essere utilizzato come divisore tra rotoli e contenitori, ad esempio etichette per l'ID spedizione e un codice a barre, di modo che le etichette possano essere facilmente ordinate dopo la stampa.</span><span class="sxs-lookup"><span data-stu-id="57ca3-414">Break labels are a separate type of label that can be used as a divider between rolls and containers, such as labels for the shipment ID and a barcode, so that the labels can easily be sorted after they are printed.</span></span>

<span data-ttu-id="57ca3-415">La differenza principale tra la configurazione di questo scenario e la configurazione dello scenario 1, oltre al fatto che le etichette di interruzione sono abilitate, è che più tipi di etichette ondata devono essere associati a modelli di etichette ondata e righe di gruppi di sequenze di unità.</span><span class="sxs-lookup"><span data-stu-id="57ca3-415">The main difference between the configuration of this scenario and the configuration of scenario 1, besides the fact that break labels are enabled, is that multiple wave label types must be associated with wave label templates and unit sequence group lines.</span></span> <span data-ttu-id="57ca3-416">Per realizzare questa configurazione, i seguenti elementi sono stati impostati per questo scenario:</span><span class="sxs-lookup"><span data-stu-id="57ca3-416">To accomplish this configuration, you set up the following elements for this scenario:</span></span>

- <span data-ttu-id="57ca3-417">**Metodi di elaborazione ondata:** si contrassegnerà il metodo di etichetta ondata come "ripetibile", lo si aggiungerà due (o più) volte al modello di ondata e si imposteranno diversi codici passaggio ondata.</span><span class="sxs-lookup"><span data-stu-id="57ca3-417">**Wave processing methods:** You will mark the wave label method as "repeatable," add it two (or more) times to the wave template, and set different wave step codes.</span></span>
- <span data-ttu-id="57ca3-418">**Modelli di etichette ondata:** si configureranno i modelli di etichette ondata e li si collegheranno al modello di ondata.</span><span class="sxs-lookup"><span data-stu-id="57ca3-418">**Wave label templates:** You will configure the wave label templates and link them to the wave template.</span></span> <span data-ttu-id="57ca3-419">Ogni modello di etichetta ondata dispone del proprio tipo di etichetta ondata.</span><span class="sxs-lookup"><span data-stu-id="57ca3-419">Each wave label template has its own wave label type.</span></span>
- <span data-ttu-id="57ca3-420">**Layout di etichette ondata:** si creeranno più layout di etichette ondata.</span><span class="sxs-lookup"><span data-stu-id="57ca3-420">**Wave label layouts:** You will create multiple wave label layouts.</span></span> <span data-ttu-id="57ca3-421">Ci sarà un layout di etichetta separato per ogni "livello" di etichette nonché un layout di etichette di interruzione.</span><span class="sxs-lookup"><span data-stu-id="57ca3-421">There will be a separate label layout for each "tier" of labels, and there will also be a break label layout.</span></span>

<span data-ttu-id="57ca3-422">Questo scenario mostra il flusso end-to-end.</span><span class="sxs-lookup"><span data-stu-id="57ca3-422">This scenario shows the end-to-end flow.</span></span>

### <a name="make-demo-data-available"></a><span data-ttu-id="57ca3-423">Rendi disponibili i dati dimostrativi</span><span class="sxs-lookup"><span data-stu-id="57ca3-423">Make demo data available</span></span>

<span data-ttu-id="57ca3-424">Per eseguire questo scenario, i dati dimostrativi devono essere installati ed è necessario selezionare la persona giuridica **USMF**.</span><span class="sxs-lookup"><span data-stu-id="57ca3-424">To follow this scenario, you must have demo data installed, and you must select the **USMF** legal entity.</span></span>

### <a name="set-up-a-wave-process-method"></a><span data-ttu-id="57ca3-425">Impostare un metodo di processo ondata</span><span class="sxs-lookup"><span data-stu-id="57ca3-425">Set up a wave process method</span></span>

1. <span data-ttu-id="57ca3-426">Andare a **Gestione magazzino \> Impostazione \> Ondate \> Metodi di elaborazione ondata**.</span><span class="sxs-lookup"><span data-stu-id="57ca3-426">Go to **Warehouse management \> Setup \> Waves \> Wave process methods**.</span></span>
1. <span data-ttu-id="57ca3-427">Verificare che **waveLabelPrinting** sia nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="57ca3-427">Confirm that **waveLabelPrinting** is in the list.</span></span> <span data-ttu-id="57ca3-428">Se non lo è, selezionare **Rigenera metodi** nel riquadro azioni per aggiungerlo.</span><span class="sxs-lookup"><span data-stu-id="57ca3-428">If it isn't, select **Regenerate methods** on the Action Pane to add it.</span></span>
1. <span data-ttu-id="57ca3-429">Per il metodo **waveLabelPrinting**, selezionare la casella di controllo **Rendi ripetibile il metodo**.</span><span class="sxs-lookup"><span data-stu-id="57ca3-429">For the **waveLabelPrinting** method, select the **Make method repeatable** check box.</span></span>

### <a name="set-up-a-wave-template"></a><span data-ttu-id="57ca3-430">Impostare un modello di ondata</span><span class="sxs-lookup"><span data-stu-id="57ca3-430">Set up a wave template</span></span>

1. <span data-ttu-id="57ca3-431">Selezionare **Gestione magazzino \> Impostazioni \> Ondate \> Modelli ondata**.</span><span class="sxs-lookup"><span data-stu-id="57ca3-431">Go to **Warehouse management \> Setup \> Waves \> Wave templates**.</span></span>
2. <span data-ttu-id="57ca3-432">Selezionare un modello, ad esempio **62 Spedizione predefinita**.</span><span class="sxs-lookup"><span data-stu-id="57ca3-432">Select a template, such as **62 Shipping Default**.</span></span>
3. <span data-ttu-id="57ca3-433">Nella Scheda dettaglio **Metodi**, spostare il metodo **Stampa di etichette ondata** nella colonna **Metodi selezionati**.</span><span class="sxs-lookup"><span data-stu-id="57ca3-433">On the **Methods** FastTab, move the **Wave label printing** method to the **Selected methods** column.</span></span>
4. <span data-ttu-id="57ca3-434">Nella colonna **Metodi selezionati**, assegnare un valore **Codice passaggio ondata**, come *Cartone*, al metodo **Stampa di etichette ondata**.</span><span class="sxs-lookup"><span data-stu-id="57ca3-434">In the **Selected methods** column, assign a **Wave step code** value, such as *Carton*, to the **Wave label printing** method.</span></span> <span data-ttu-id="57ca3-435">Per ulteriori informazioni sui codici del passaggio ondata, vedere [Codici del passaggio ondata](wave-step-codes.md).</span><span class="sxs-lookup"><span data-stu-id="57ca3-435">For more information about wave step codes, see [Wave step codes](wave-step-codes.md).</span></span>
5. <span data-ttu-id="57ca3-436">Spostare il metodo **Stampa di etichette ondata** nella colonna **Metodi selezionati** una seconda volta.</span><span class="sxs-lookup"><span data-stu-id="57ca3-436">Move the **Wave label printing** method to the **Selected methods** column a second time.</span></span>
6. <span data-ttu-id="57ca3-437">Nella colonna **Metodi selezionati**, assegnare un valore **Codice passaggio ondata** differente, come *Pallet*, al secondo metodo **Stampa di etichette ondata**.</span><span class="sxs-lookup"><span data-stu-id="57ca3-437">In the **Selected methods** column, assign a different **Wave step code** value, such as *Pallet*, to the second **Wave label printing** method.</span></span> <span data-ttu-id="57ca3-438">Per ulteriori informazioni sui codici del passaggio ondata, vedere [Codici del passaggio ondata](wave-step-codes.md).</span><span class="sxs-lookup"><span data-stu-id="57ca3-438">For more information about wave step codes, see [Wave step codes](wave-step-codes.md).</span></span>

### <a name="create-three-wave-label-layouts"></a><span data-ttu-id="57ca3-439">Creare tre layout di etichetta ondata</span><span class="sxs-lookup"><span data-stu-id="57ca3-439">Create three wave label layouts</span></span>

1. <span data-ttu-id="57ca3-440">Andare a **Gestione magazzino \> Impostazioni \> Distribuzione documenti \> Layout etichette ondata**.</span><span class="sxs-lookup"><span data-stu-id="57ca3-440">Go to **Warehouse management \> Setup \> Document routing \> Wave label layouts**.</span></span>
1. <span data-ttu-id="57ca3-441">Crea un record con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="57ca3-441">Create a record that has the following settings:</span></span>

    - <span data-ttu-id="57ca3-442">**ID layout etichetta:** *Cartone*</span><span class="sxs-lookup"><span data-stu-id="57ca3-442">**Label layout ID:** *Carton*</span></span>
    - <span data-ttu-id="57ca3-443">**Descrizione:** *Cartone (SSCC)*</span><span class="sxs-lookup"><span data-stu-id="57ca3-443">**Description:** *Carton (SSCC)*</span></span>

1. <span data-ttu-id="57ca3-444">Nel riquadro azioni selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="57ca3-444">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="57ca3-445">Nel riquadro azioni selezionare **Impostazioni di riga delle etichette ondata**.</span><span class="sxs-lookup"><span data-stu-id="57ca3-445">On the Action Pane, select **Wave label row settings**.</span></span>

    <span data-ttu-id="57ca3-446">Viene visualizzata la pagina **Impostazioni di riga delle etichette ondata**.</span><span class="sxs-lookup"><span data-stu-id="57ca3-446">The **Wave label row settings** page appears.</span></span> <span data-ttu-id="57ca3-447">Qui è possibile configurare la parte dinamica dell'etichetta.</span><span class="sxs-lookup"><span data-stu-id="57ca3-447">Here, you can configure the dynamic part of the label.</span></span>

1. <span data-ttu-id="57ca3-448">Aggiungere una riga con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="57ca3-448">Add a row that has the following settings:</span></span>

    - <span data-ttu-id="57ca3-449">**ID riga:** *WaveLabel*</span><span class="sxs-lookup"><span data-stu-id="57ca3-449">**Row Id:** *WaveLabel*</span></span>
    - <span data-ttu-id="57ca3-450">**Nome tabella di righe:** *WHSWaveLabel*</span><span class="sxs-lookup"><span data-stu-id="57ca3-450">**Row table name:** *WHSWaveLabel*</span></span>
    - <span data-ttu-id="57ca3-451">**Posizione di inizio riga:** *0*</span><span class="sxs-lookup"><span data-stu-id="57ca3-451">**Row start position:** *0*</span></span>

        <span data-ttu-id="57ca3-452">Questo campo definisce la posizione verticale iniziale della riga sull'etichetta.</span><span class="sxs-lookup"><span data-stu-id="57ca3-452">This field defines the vertical position where the row will begin on the label.</span></span>

    - <span data-ttu-id="57ca3-453">**Altezza riga:** *0*</span><span class="sxs-lookup"><span data-stu-id="57ca3-453">**Row height:** *0*</span></span>

        <span data-ttu-id="57ca3-454">Questo campo definisce l'altezza di ogni riga (in punti), secondo lo standard ZPL.</span><span class="sxs-lookup"><span data-stu-id="57ca3-454">This field defines the height of each row (in points), according to the ZPL standard.</span></span> <span data-ttu-id="57ca3-455">L'altezza della riga è positiva per le etichette orizzontali e negativa per le etichette verticali.</span><span class="sxs-lookup"><span data-stu-id="57ca3-455">The row height is positive for horizontal labels and negative for vertical labels.</span></span> <span data-ttu-id="57ca3-456">Poiché in questo esempio c'è una sola riga, è possibile impostare il valore su *0* (zero).</span><span class="sxs-lookup"><span data-stu-id="57ca3-456">Because there is just one row in this example, you can set the value to *0* (zero).</span></span>

    - <span data-ttu-id="57ca3-457">**Righe per pagina:** *1*</span><span class="sxs-lookup"><span data-stu-id="57ca3-457">**Rows per page:** *1*</span></span>

        <span data-ttu-id="57ca3-458">Questo campo definisce il numero di righe che è possibile stampare su ciascuna etichetta.</span><span class="sxs-lookup"><span data-stu-id="57ca3-458">This field defines the number of rows that can be printed on each label.</span></span>

        > [!NOTE]
        > <span data-ttu-id="57ca3-459">Questa impostazione causerà la stampa di un'etichetta ZPL separata per ciascun record nella tabella delle etichette ondata.</span><span class="sxs-lookup"><span data-stu-id="57ca3-459">This setup will cause a separate ZPL label to be printed for each record in the wave labels table.</span></span>

1. <span data-ttu-id="57ca3-460">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="57ca3-460">Close the page.</span></span>
1. <span data-ttu-id="57ca3-461">Nel riquadro azioni, seleziona **Modifica query**.</span><span class="sxs-lookup"><span data-stu-id="57ca3-461">On the Action Pane, select **Edit query**.</span></span>
1. <span data-ttu-id="57ca3-462">Nella finestra di dialogo dell'editor di query, nella scheda **Intervallo**, aggiungere una riga con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="57ca3-462">In the query editor dialog box, on the **Range** tab, add a row that has the following settings:</span></span>

    - <span data-ttu-id="57ca3-463">**Tabella:** *Righe di lavoro*</span><span class="sxs-lookup"><span data-stu-id="57ca3-463">**Table:** *Work lines*</span></span>
    - <span data-ttu-id="57ca3-464">**Tabella derivata:** *Righe di lavoro*</span><span class="sxs-lookup"><span data-stu-id="57ca3-464">**Derived table:** *Work lines*</span></span>
    - <span data-ttu-id="57ca3-465">**Campo:** *Tipo di lavoro*</span><span class="sxs-lookup"><span data-stu-id="57ca3-465">**Field:** *Work type*</span></span>
    - <span data-ttu-id="57ca3-466">**Criteri:** *Prelievo*</span><span class="sxs-lookup"><span data-stu-id="57ca3-466">**Criteria:** *Pick*</span></span>

    <span data-ttu-id="57ca3-467">Questa query garantisce che sull'etichetta vengano stampate solo le righe di lavoro di tipo prelievo, non le righe di lavoro di tipo stoccaggio.</span><span class="sxs-lookup"><span data-stu-id="57ca3-467">This query ensures that only pick-type work lines will be printed on the label, not put-type work lines.</span></span>

1. <span data-ttu-id="57ca3-468">Se si desidera poter stampare l'ID polizza di carico, nella scheda **Join**, selezionare la tabella **Righe lavoro** e unirvi la tabella **Spedizioni**.</span><span class="sxs-lookup"><span data-stu-id="57ca3-468">If you want to be able to print the bill of lading ID, on the **Joins** tab, select the **Work lines** table, and join the **Shipments** table to it.</span></span> 
1. <span data-ttu-id="57ca3-469">Chiudere la finestra di dialogo dell'editor di query.</span><span class="sxs-lookup"><span data-stu-id="57ca3-469">Close the query editor dialog box.</span></span>
1. <span data-ttu-id="57ca3-470">La Scheda dettaglio **Layout testo stampante** ha tre sezioni in cui è possibile scrivere il codice della stampante: **Sezione di intestazione**, **Sezione del corpo** e **Sezione piè di pagina**.</span><span class="sxs-lookup"><span data-stu-id="57ca3-470">The **Printer text Layout** FastTab has three sections where you can write printer code: **Header section**, **Body section**, and **Footer section**.</span></span> <span data-ttu-id="57ca3-471">Nella sezione **Sezione di intestazione**, nel campo **Intestazione etichetta**, immettere il codice per l'intestazione necessaria.</span><span class="sxs-lookup"><span data-stu-id="57ca3-471">In the **Header section** section, in the **Label header** field, enter code for the required header.</span></span> <span data-ttu-id="57ca3-472">Ad esempio, se si utilizzano stampanti Zebra, è possibile utilizzare il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="57ca3-472">For example, if you're using Zebra printers, you can use the following code.</span></span>


    ```plaintext
    CT~~CD,~CC^~CT~
    ^XA~TA000~JSN^LT0^MNW^MTT^PON^PMN^LH0,0^JMA^PR8,8~SD15^JUS^LRN^CI0^XZ
    ^XA
    ^MMT
    ^PW812
    ^LL1218
    ^LS0
    ^FT85,505^A0N,28,28^FH\^FD$WHSShipmentTable.CustomerReq$^FS
    ^FO1,173^GB809,0,1^FS
    ^FO0,391^GB809,0,1^FS
    ^FO3,599^GB809,0,2^FS
    ^FO420,176^GB0,216,1^FS
    ^FO313,3^GB0,169,1^FS
    ^FO0,807^GB809,0,1^FS
    ^FT529,370^A0N,28,26^FH\^FD$WHSShipmentTable.BillOfLadingId$^FS
    ^BY2,3,132^FT25,344^BCN,,N,N
    ^FD>:(420)>38102>63^FS
    ^FT526,315^A0N,28,28^FH\^FD ^FS
    ^FT437,248^A0N,28,28^FH\^FDCARR: $WHSShipmentTable.SCAC$^FS
    ^FT425,201^A0N,23,24^FH\^FDCARRIER:^FS
    ^FT17,68^A0N,20,19^FH\^FDIntershipping, Inc.^FS
    ^FT15,99^A0N,20,19^FH\^FD1000 Shipping Lane^FS
    ^FT16,158^A0N,20,19^FH\^FD ^FS
    ^FT438,368^A0N,28,28^FH\^FDB/L#^FS
    ^FT15,128^A0N,20,19^FH\^FDShelbyville TN 38102^FS
    ^FT19,203^A0N,23,24^FH\^FD(420) SHIP TO POSTAL CODE^FS
    ^FT331,39^A0N,28,28^FH\^FDShip To:^FS
    ^FT14,39^A0N,28,28^FH\^FDShip From:^FS
    ^FT331,67^A0N,23,24^FH\^FDWAL-MART DC 1111A-ABC DIS^FS
    ^FT330,98^A0N,23,24^FH\^FDDEPT 10^FS
    ^FT329,166^A0N,23,24^FH\^FDSpringfield TN 39021^FS
    ^FT330,134^A0N,23,24^FH\^FD100 Main Street^FS
    ^FT19,504^A0N,28,28^FH\^FDPO#:^FS
    ^FT437,316^A0N,28,28^FH\^FDPRO#^FS
    ^FT105,371^A0N,28,28^FB130,1,0,C^FH\^FD(420)39021^FS
    ```

1. <span data-ttu-id="57ca3-473">Nella sezione **Sezione del corpo**, nel campo **Corpo etichetta**, immettere il codice ZPL per il corpo necessario.</span><span class="sxs-lookup"><span data-stu-id="57ca3-473">In the **Body section** section, in the **Label body** field, enter ZPL code for the required body.</span></span> <span data-ttu-id="57ca3-474">Ecco un esempio.</span><span class="sxs-lookup"><span data-stu-id="57ca3-474">Here is an example.</span></span>

    ```plaintext
    <Row name="WaveLabel">
    ^FT127,439^A0N,28,28^FH\^FD$WHSWaveLabel.SeqNum$^FS
    ^FT256,439^A0N,28,28^FH\^FD$WHSWaveLabel.NumberOfLabels$^FS
    ^FT17,439^A0N,28,28^FH\^FDCARTON^FS
    ^FT522,422^A0N,23,24^FH\^FDVPN:^FS
    ^FT74,1156^A0N,28,28^FH\^FDSSCC-18^FS
    ^FT21,579^A0N,28,28^FH\^FDItem name:^FS
    ^FT107,580^A0N,28,28^FH\^FD$WHSWaveLabel.LabelItemName$^FS
    ^FT576,423^A0N,23,21^FH\^FD$WHSWaveLabel.LabelItemId$^FS
    ^FT252,1155^A0N,32,31^FH\^FD(00)$WHSWaveLabel.WaveLabelId$^FS
    ^BY4,3,283^FT66,1115^BCN,,N,N
    ^FD>;>800$WHSWaveLabel.WaveLabelId$^FS
    ^FT194,439^A0N,28,28^FH\^FDof^FS
    </Row>
    ```

1. <span data-ttu-id="57ca3-475">Nella sezione **Sezione del corpo**, nel campo **Piè di pagina etichetta**, immettere il codice ZPL per il piè di pagina necessario.</span><span class="sxs-lookup"><span data-stu-id="57ca3-475">In the **Body section** section, in the **Label footer** field, enter ZPL code for the required footer.</span></span> <span data-ttu-id="57ca3-476">Ecco un esempio.</span><span class="sxs-lookup"><span data-stu-id="57ca3-476">Here is an example.</span></span>

    ```plaintext
    ^PQ1^XZ
    ```

    > [!NOTE]
    > <span data-ttu-id="57ca3-477">Questa configurazione stamperà una copia di ciascuna etichetta.</span><span class="sxs-lookup"><span data-stu-id="57ca3-477">This setup will print one copy of each label.</span></span> <span data-ttu-id="57ca3-478">Se sono necessarie più copie (ad esempio una copia per ciascun lato del pallet), impostare il valore **n** per la sezione **\^PQn** nel piè di pagina sul numero di copie necessarie.</span><span class="sxs-lookup"><span data-stu-id="57ca3-478">If you require more copies (for example, one copy for each side of the pallet), set the **n** value for the **\^PQn** section in the footer to the required number of copies.</span></span> <span data-ttu-id="57ca3-479">Ad esempio, per stampare quattro copie di ciascuna etichetta, specificare **\^PQ4**.</span><span class="sxs-lookup"><span data-stu-id="57ca3-479">For example, to print four copies of each label, specify **\^PQ4**.</span></span>

1. <span data-ttu-id="57ca3-480">La prima etichetta è ora pronta per l'uso.</span><span class="sxs-lookup"><span data-stu-id="57ca3-480">The first label is now ready to use.</span></span>
1. <span data-ttu-id="57ca3-481">Crea un secondo record di layout con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="57ca3-481">Create a second layout record that has the following settings:</span></span>

    - <span data-ttu-id="57ca3-482">**ID layout etichetta:** *Pallet*</span><span class="sxs-lookup"><span data-stu-id="57ca3-482">**Label layout ID:** *Pallet*</span></span>
    - <span data-ttu-id="57ca3-483">**Descrizione:** *Pallet*</span><span class="sxs-lookup"><span data-stu-id="57ca3-483">**Description:** *Pallet*</span></span>

1. <span data-ttu-id="57ca3-484">Nel riquadro azioni selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="57ca3-484">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="57ca3-485">Nel riquadro azioni selezionare **Impostazioni di riga delle etichette ondata**.</span><span class="sxs-lookup"><span data-stu-id="57ca3-485">On the Action Pane, select **Wave label row settings**.</span></span>

    <span data-ttu-id="57ca3-486">Viene visualizzata la pagina **Impostazioni di riga delle etichette ondata**.</span><span class="sxs-lookup"><span data-stu-id="57ca3-486">The **Wave label row settings** page appears.</span></span> <span data-ttu-id="57ca3-487">Qui è possibile configurare la parte dinamica dell'etichetta.</span><span class="sxs-lookup"><span data-stu-id="57ca3-487">Here, you can configure the dynamic part of the label.</span></span>

1. <span data-ttu-id="57ca3-488">Aggiungere una riga con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="57ca3-488">Add a row that has the following settings:</span></span>

    - <span data-ttu-id="57ca3-489">**ID riga:** *WaveLabel*</span><span class="sxs-lookup"><span data-stu-id="57ca3-489">**Row Id:** *WaveLabel*</span></span>
    - <span data-ttu-id="57ca3-490">**Nome tabella di righe:** *WHSWaveLabel*</span><span class="sxs-lookup"><span data-stu-id="57ca3-490">**Row table name:** *WHSWaveLabel*</span></span>
    - <span data-ttu-id="57ca3-491">**Posizione di inizio riga:** *0*</span><span class="sxs-lookup"><span data-stu-id="57ca3-491">**Row start position:** *0*</span></span>

        <span data-ttu-id="57ca3-492">Questo campo definisce la posizione verticale iniziale della riga sull'etichetta.</span><span class="sxs-lookup"><span data-stu-id="57ca3-492">This field defines the vertical position where the row will begin on the label.</span></span>

    - <span data-ttu-id="57ca3-493">**Altezza riga:** *0*</span><span class="sxs-lookup"><span data-stu-id="57ca3-493">**Row height:** *0*</span></span>

        <span data-ttu-id="57ca3-494">Questo campo definisce l'altezza di ogni riga (in punti), secondo lo standard ZPL.</span><span class="sxs-lookup"><span data-stu-id="57ca3-494">This field defines the height of each row (in points), according to the ZPL standard.</span></span> <span data-ttu-id="57ca3-495">L'altezza della riga è positiva per le etichette orizzontali e negativa per le etichette verticali.</span><span class="sxs-lookup"><span data-stu-id="57ca3-495">The row height is positive for horizontal labels and negative for vertical labels.</span></span> <span data-ttu-id="57ca3-496">Poiché in questo esempio c'è una sola riga, è possibile impostare il valore su *0* (zero).</span><span class="sxs-lookup"><span data-stu-id="57ca3-496">Because there is just one row in this example, you can set the value to *0* (zero).</span></span>

    - <span data-ttu-id="57ca3-497">**Righe per pagina:** *1*</span><span class="sxs-lookup"><span data-stu-id="57ca3-497">**Rows per page:** *1*</span></span>

        <span data-ttu-id="57ca3-498">Questo campo definisce il numero di righe che è possibile stampare su ciascuna etichetta.</span><span class="sxs-lookup"><span data-stu-id="57ca3-498">This field defines the number of rows that can be printed on each label.</span></span>

        > [!NOTE]
        > <span data-ttu-id="57ca3-499">Questa impostazione causa la stampa di un'etichetta ZPL separata per ciascun record nella tabella di etichette ondata.</span><span class="sxs-lookup"><span data-stu-id="57ca3-499">This setup causes a separate ZPL label to be printed for each record in the wave labels table.</span></span>

1. <span data-ttu-id="57ca3-500">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="57ca3-500">Close the page.</span></span>
1. <span data-ttu-id="57ca3-501">Nel riquadro azioni, seleziona **Modifica query**.</span><span class="sxs-lookup"><span data-stu-id="57ca3-501">On the Action Pane, select **Edit query**.</span></span>
1. <span data-ttu-id="57ca3-502">Nella finestra di dialogo dell'editor di query, nella scheda **Intervallo**, aggiungere una riga con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="57ca3-502">In the query editor dialog box, on the **Range** tab, add a row that has the following settings:</span></span>

    - <span data-ttu-id="57ca3-503">**Tabella:** *Righe di lavoro*</span><span class="sxs-lookup"><span data-stu-id="57ca3-503">**Table:** *Work lines*</span></span>
    - <span data-ttu-id="57ca3-504">**Tabella derivata:** *Righe di lavoro*</span><span class="sxs-lookup"><span data-stu-id="57ca3-504">**Derived table:** *Work lines*</span></span>
    - <span data-ttu-id="57ca3-505">**Campo:** *Tipo di lavoro*</span><span class="sxs-lookup"><span data-stu-id="57ca3-505">**Field:** *Work type*</span></span>
    - <span data-ttu-id="57ca3-506">**Criteri:** *Prelievo*</span><span class="sxs-lookup"><span data-stu-id="57ca3-506">**Criteria:** *Pick*</span></span>

    <span data-ttu-id="57ca3-507">Questa query garantisce che sull'etichetta vengano stampate solo le righe di lavoro di tipo prelievo, non le righe di lavoro di tipo stoccaggio.</span><span class="sxs-lookup"><span data-stu-id="57ca3-507">This query ensures that only pick-type work lines will be printed on the label, not put-type work lines.</span></span>

1. <span data-ttu-id="57ca3-508">Se si desidera poter stampare l'ID polizza di carico, nella scheda **Join**, selezionare la tabella **Righe lavoro** e unirvi la tabella **Spedizioni**.</span><span class="sxs-lookup"><span data-stu-id="57ca3-508">If you want to be able to print the bill of lading ID, on the **Joins** tab, select the **Work lines** table, and join the **Shipments** table to it.</span></span>
1. <span data-ttu-id="57ca3-509">Chiudere la finestra di dialogo dell'editor di query.</span><span class="sxs-lookup"><span data-stu-id="57ca3-509">Close the query editor dialog box.</span></span>
1. <span data-ttu-id="57ca3-510">La Scheda dettaglio **Layout testo stampante** ha tre sezioni in cui è possibile scrivere il codice della stampante: **Sezione di intestazione**, **Sezione del corpo** e **Sezione piè di pagina**.</span><span class="sxs-lookup"><span data-stu-id="57ca3-510">The **Printer text Layout** FastTab has three sections where you can write printer code: **Header section**, **Body section**, and **Footer section**.</span></span> <span data-ttu-id="57ca3-511">Nella sezione **Sezione di intestazione**, nel campo **Intestazione etichetta**, immettere il codice per l'intestazione necessaria.</span><span class="sxs-lookup"><span data-stu-id="57ca3-511">In the **Header section** section, in the **Label header** field, enter code for the required header.</span></span> <span data-ttu-id="57ca3-512">Ad esempio, se si utilizzano stampanti Zebra, è possibile utilizzare il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="57ca3-512">For example, if you're using Zebra printers, you can use the following code.</span></span>

    ```plaintext
    CT~~CD,~CC^~CT~
    ^XA
    ^LH10,10
    ^FO0,0 ^AT ^FD$WHSWaveLabel.WaveLabelId$ ^FS
    ^FO0,75 ^AT ^FD$WHSWorkLine.ShipmentId$ ^FS
    ^FO0,150 ^AT ^FD$WHSShipmentTable.BillOfLadingId$ ^FS
    ```

1. <span data-ttu-id="57ca3-513">Nella sezione **Sezione del corpo**, nel campo **Corpo etichetta**, immettere il codice ZPL per il corpo necessario.</span><span class="sxs-lookup"><span data-stu-id="57ca3-513">In the **Body section** section, in the **Label body** field, enter ZPL code for the required body.</span></span> <span data-ttu-id="57ca3-514">Ecco un esempio.</span><span class="sxs-lookup"><span data-stu-id="57ca3-514">Here is an example.</span></span>

    ```plaintext
    <Row name="WaveLabel">
    ^FO0,450 ^AT ^FDItem ^FS
    ^FO200,450 ^AT ^FDQuantity ^FS
    ^FO0,[[YPos]] ^AT ^FD$WHSWaveLabel.LabelItemId$ ^FS
    ^FO200,[[YPos]] ^AT ^FD$WHSWaveLabel.QtyWork$ ^FS
    </Row>
    ```

1. <span data-ttu-id="57ca3-515">Nella sezione **Sezione del corpo**, nel campo **Piè di pagina etichetta**, immettere il codice ZPL per il piè di pagina necessario.</span><span class="sxs-lookup"><span data-stu-id="57ca3-515">In the **Body section** section, in the **Label footer** field, enter ZPL code for the required footer.</span></span> <span data-ttu-id="57ca3-516">Ecco un esempio.</span><span class="sxs-lookup"><span data-stu-id="57ca3-516">Here is an example.</span></span>

    ```plaintext
    ^PQ1^XZ
    ```

    > [!NOTE]
    > <span data-ttu-id="57ca3-517">Questa configurazione stamperà una copia di ciascuna etichetta.</span><span class="sxs-lookup"><span data-stu-id="57ca3-517">This setup will print one copy of each label.</span></span> <span data-ttu-id="57ca3-518">Se sono necessarie più copie (ad esempio una copia per ciascun lato del pallet), impostare il valore **n** per la sezione **\^PQn** nel piè di pagina sul numero di copie necessarie.</span><span class="sxs-lookup"><span data-stu-id="57ca3-518">If you require more copies (for example, one copy for each side of the pallet), set the **n** value for the **\^PQn** section in the footer to the required number of copies.</span></span> <span data-ttu-id="57ca3-519">Ad esempio, per stampare quattro copie di ciascuna etichetta, specificare **\^PQ4**.</span><span class="sxs-lookup"><span data-stu-id="57ca3-519">For example, to print four copies of each label, specify **\^PQ4**.</span></span>

1. <span data-ttu-id="57ca3-520">La seconda etichetta è ora pronta per l'uso.</span><span class="sxs-lookup"><span data-stu-id="57ca3-520">The second label is now ready to use.</span></span>
1. <span data-ttu-id="57ca3-521">Creare un terzo record di layout con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="57ca3-521">Create a third layout record that has the following settings:</span></span>

    - <span data-ttu-id="57ca3-522">**ID layout etichetta:** *Interruzione*</span><span class="sxs-lookup"><span data-stu-id="57ca3-522">**Label layout ID:** *Break*</span></span>
    - <span data-ttu-id="57ca3-523">**Descrizione:** *Etichetta di interruzione*</span><span class="sxs-lookup"><span data-stu-id="57ca3-523">**Description:** *Break label*</span></span>

1. <span data-ttu-id="57ca3-524">Nel riquadro azioni selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="57ca3-524">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="57ca3-525">La Scheda dettaglio **Layout testo stampante** ha tre sezioni in cui è possibile scrivere il codice della stampante: **Sezione di intestazione**, **Sezione del corpo** e **Sezione piè di pagina**.</span><span class="sxs-lookup"><span data-stu-id="57ca3-525">The **Printer text Layout** FastTab has three sections where you can write printer code: **Header section**, **Body section**, and **Footer section**.</span></span> <span data-ttu-id="57ca3-526">Nella sezione **Sezione di intestazione**, nel campo **Intestazione etichetta**, immettere il codice ZPL per l'intestazione necessaria.</span><span class="sxs-lookup"><span data-stu-id="57ca3-526">In the **Header section** section, in the **Label header** field, enter ZPL code for the required header.</span></span> <span data-ttu-id="57ca3-527">Ecco un esempio.</span><span class="sxs-lookup"><span data-stu-id="57ca3-527">Here is an example.</span></span>

    ```plaintext
    CT~~CD,~CC^~CT~
    ^XA
    ^LH10,10
    ^FO0,0 ^AT ^FD$WHSWorkLine.ShipmentId$ ^FS
    ```

1. <span data-ttu-id="57ca3-528">Questa volta, non è necessario un corpo.</span><span class="sxs-lookup"><span data-stu-id="57ca3-528">This time, no body is required.</span></span> <span data-ttu-id="57ca3-529">Pertanto, immettere il testo necessario nella sezione **Sezione piè di pagina**.</span><span class="sxs-lookup"><span data-stu-id="57ca3-529">Therefore, just enter the required text in the **Footer section** section.</span></span> <span data-ttu-id="57ca3-530">Ecco un esempio.</span><span class="sxs-lookup"><span data-stu-id="57ca3-530">Here is an example.</span></span>

    ```plaintext
    ^XZ
    ```

    <span data-ttu-id="57ca3-531">La terza etichetta è ora pronta per l'uso.</span><span class="sxs-lookup"><span data-stu-id="57ca3-531">The third label is now ready to use.</span></span>

    > [!NOTE]
    > <span data-ttu-id="57ca3-532">Questa terza etichetta è un'etichetta di interruzione che verrà utilizzata come divisore tra i rotoli di etichette.</span><span class="sxs-lookup"><span data-stu-id="57ca3-532">This third label is a break label that will be used as a divider between label rolls.</span></span>

### <a name="create-two-wave-label-types"></a><span data-ttu-id="57ca3-533">Creare due tipi di etichetta ondata</span><span class="sxs-lookup"><span data-stu-id="57ca3-533">Create two wave label types</span></span>

1. <span data-ttu-id="57ca3-534">Andare a **Gestione magazzino \> Impostazioni \> Distribuzione documenti \> Tipi di etichette ondata**.</span><span class="sxs-lookup"><span data-stu-id="57ca3-534">Go to **Warehouse management \> Setup \> Document routing \> Wave label types**.</span></span>
1. <span data-ttu-id="57ca3-535">Crea un record con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="57ca3-535">Create a record that has the following settings:</span></span>

    - <span data-ttu-id="57ca3-536">**Tipo di etichetta:** *Cartone*</span><span class="sxs-lookup"><span data-stu-id="57ca3-536">**Label type:** *Carton*</span></span>
    - <span data-ttu-id="57ca3-537">**Descrizione:** *Cartone*</span><span class="sxs-lookup"><span data-stu-id="57ca3-537">**Description:** *Carton*</span></span>

1. <span data-ttu-id="57ca3-538">Crea un secondo record con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="57ca3-538">Create a second record that has the following settings:</span></span>

    - <span data-ttu-id="57ca3-539">**Tipo di etichetta:** *Pallet*</span><span class="sxs-lookup"><span data-stu-id="57ca3-539">**Label type:** *Pallet*</span></span>
    - <span data-ttu-id="57ca3-540">**Descrizione:** *Pallet*</span><span class="sxs-lookup"><span data-stu-id="57ca3-540">**Description:** *Pallet*</span></span>

### <a name="set-up-unit-sequence-groups"></a><span data-ttu-id="57ca3-541">Imposta gruppi di sequenze unità</span><span class="sxs-lookup"><span data-stu-id="57ca3-541">Set up unit sequence groups</span></span>

1. <span data-ttu-id="57ca3-542">Fare clic su **Gestione magazzino \> Impostazione \> Magazzino \> Gruppi di sequenze unità**.</span><span class="sxs-lookup"><span data-stu-id="57ca3-542">Go to **Warehouse management \> Setup \> Warehouse \> Unit sequence groups**.</span></span>
1. <span data-ttu-id="57ca3-543">Selezionare o creare un gruppo **unità scatola pallet**.</span><span class="sxs-lookup"><span data-stu-id="57ca3-543">Select or create an **Ea Box PL** group.</span></span>
1. <span data-ttu-id="57ca3-544">Per la riga **Scatola**, impostare il campo **Tipo di livello ondata** su *Scatola*.</span><span class="sxs-lookup"><span data-stu-id="57ca3-544">For the **Box** line, set the **Wave level type** field to *Carton*.</span></span>
1. <span data-ttu-id="57ca3-545">Per la riga **PALLET**, impostare il campo **Tipo di livello ondata** su *Pallet*.</span><span class="sxs-lookup"><span data-stu-id="57ca3-545">For the **PL** line, set the **Wave level type** field to *Pallet*.</span></span>

### <a name="create-wave-label-templates"></a><span data-ttu-id="57ca3-546">Creare modelli di etichetta ondata</span><span class="sxs-lookup"><span data-stu-id="57ca3-546">Create wave label templates</span></span>

1. <span data-ttu-id="57ca3-547">Andare a **Gestione magazzino \> Impostazioni \> Distribuzione documenti \> Modelli di etichette ondata**.</span><span class="sxs-lookup"><span data-stu-id="57ca3-547">Go to **Warehouse management \> Setup \> Document routing \> Wave label templates**.</span></span>
1. <span data-ttu-id="57ca3-548">Creare un modello di etichetta con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="57ca3-548">Create a label template that has the following settings:</span></span>

    - <span data-ttu-id="57ca3-549">**Nome modello etichetta:** *Etichette cartoni*</span><span class="sxs-lookup"><span data-stu-id="57ca3-549">**Label template name:** *Carton labels*</span></span>
    - <span data-ttu-id="57ca3-550">**Descrizione:** *Etichette cartoni*</span><span class="sxs-lookup"><span data-stu-id="57ca3-550">**Description:** *Carton labels*</span></span>
    - <span data-ttu-id="57ca3-551">**Codice passaggio ondata:** *Cartone*</span><span class="sxs-lookup"><span data-stu-id="57ca3-551">**Wave step code:** *Carton*</span></span>
    - <span data-ttu-id="57ca3-552">**Magazzino:** *62*</span><span class="sxs-lookup"><span data-stu-id="57ca3-552">**Warehouse:** *62*</span></span>

1. <span data-ttu-id="57ca3-553">Nella Scheda dettaglio **Generale**, nel campo **Tipo di etichetta ondata**, selezionare un valore, ad esempio *Cartone*.</span><span class="sxs-lookup"><span data-stu-id="57ca3-553">On the **General** FastTab, in the **Wave label type** field, select a value, such as *Carton*.</span></span>
1. <span data-ttu-id="57ca3-554">Nella Scheda dettaglio **Dettagli modello di etichette ondata**, aggiungere una riga con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="57ca3-554">On the **Wave label template details** FastTab, add a row that has the following settings:</span></span>

    - <span data-ttu-id="57ca3-555">**ID layout etichetta:** *Cartone*</span><span class="sxs-lookup"><span data-stu-id="57ca3-555">**Label layout ID:** *Carton*</span></span>
    - <span data-ttu-id="57ca3-556">**Nome stampante:** selezionare una stampante ZPL appropriata.</span><span class="sxs-lookup"><span data-stu-id="57ca3-556">**Printer name:** Select an appropriate ZPL printer.</span></span>
    - <span data-ttu-id="57ca3-557">**Esegui query:** *Sì* (questa impostazione è facoltativa, ma è consigliata per prestazioni ottimali).</span><span class="sxs-lookup"><span data-stu-id="57ca3-557">**Run query:** *Yes* (This setting is optional, but it's recommended for optimal performance.)</span></span>

1. <span data-ttu-id="57ca3-558">Nel riquadro azioni selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="57ca3-558">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="57ca3-559">Facoltativo: se si sta progettando un'etichetta specifica per il cliente, è necessario creare una query per trovare il conto del cliente.</span><span class="sxs-lookup"><span data-stu-id="57ca3-559">Optional: If you're setting up a customer-specific label design, you must create a query to find the customer's account.</span></span> <span data-ttu-id="57ca3-560">Nella scheda dettaglio **Dettagli modello di etichette ondata**, selezionare **Modifica query**.</span><span class="sxs-lookup"><span data-stu-id="57ca3-560">On the **Wave label template details** FastTab, select **Edit query**.</span></span> <span data-ttu-id="57ca3-561">Quindi, nella finestra di dialogo dell'editor di query, nella scheda **Intervallo**, aggiungere una riga con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="57ca3-561">Then, in the query editor dialog box, on the **Range** tab, add a row that has the following settings:</span></span>

    - <span data-ttu-id="57ca3-562">**Tabella:** *Spedizioni*</span><span class="sxs-lookup"><span data-stu-id="57ca3-562">**Table:** *Shipments*</span></span>
    - <span data-ttu-id="57ca3-563">**Tabella derivata:** *Spedizioni*</span><span class="sxs-lookup"><span data-stu-id="57ca3-563">**Derived table:** *Shipments*</span></span>
    - <span data-ttu-id="57ca3-564">**Campo:** *Numero di conto*</span><span class="sxs-lookup"><span data-stu-id="57ca3-564">**Field:** *Account number*</span></span>
    - <span data-ttu-id="57ca3-565">**Criteri:** Immettere il numero di conto cliente pertinente.</span><span class="sxs-lookup"><span data-stu-id="57ca3-565">**Criteria:** Enter the relevant customer account number.</span></span>

    <span data-ttu-id="57ca3-566">Al termine, selezionare **OK** per chiudere la finestra di dialogo dell'editor di query.</span><span class="sxs-lookup"><span data-stu-id="57ca3-566">When you've finished, select **OK** to close the query editor dialog box.</span></span>

1. <span data-ttu-id="57ca3-567">Nel riquadro azioni, selezionare **Modifica query** per aprire la finestra di dialogo dell'editor di query per l'intero modello di etichetta.</span><span class="sxs-lookup"><span data-stu-id="57ca3-567">On the Action Pane, select **Edit query** to open the query editor dialog box for the whole label template.</span></span>
1. <span data-ttu-id="57ca3-568">Nella finestra di dialogo dell'editor di query, nella scheda **Ordinamento**, aggiungere una riga con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="57ca3-568">In the query editor dialog box, on the **Sorting** tab, add a row that has the following settings:</span></span>

    - <span data-ttu-id="57ca3-569">**Tabella:** *Righe di lavoro*</span><span class="sxs-lookup"><span data-stu-id="57ca3-569">**Table:** *Work lines*</span></span>
    - <span data-ttu-id="57ca3-570">**Tabella derivata:** *Righe di lavoro*</span><span class="sxs-lookup"><span data-stu-id="57ca3-570">**Derived table:** *Work lines*</span></span>
    - <span data-ttu-id="57ca3-571">**Campo:** *ID riga di carico di riferimento (ID record)*</span><span class="sxs-lookup"><span data-stu-id="57ca3-571">**Field:** *Reference load line id (Record-ID)*</span></span>
    - <span data-ttu-id="57ca3-572">**Direzione di ricerca:** *Crescente*</span><span class="sxs-lookup"><span data-stu-id="57ca3-572">**Search direction:** *Ascending*</span></span>

1. <span data-ttu-id="57ca3-573">Aggiungere una seconda riga con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="57ca3-573">Add a second row that has the following settings:</span></span>

    - <span data-ttu-id="57ca3-574">**Tabella:** *Righe di lavoro*</span><span class="sxs-lookup"><span data-stu-id="57ca3-574">**Table:** *Work lines*</span></span>
    - <span data-ttu-id="57ca3-575">**Tabella derivata:** *Righe di lavoro*</span><span class="sxs-lookup"><span data-stu-id="57ca3-575">**Derived table:** *Work lines*</span></span>
    - <span data-ttu-id="57ca3-576">**Campo:** *ID spedizione*</span><span class="sxs-lookup"><span data-stu-id="57ca3-576">**Field:** *Shipment ID*</span></span>
    - <span data-ttu-id="57ca3-577">**Direzione di ricerca:** *Crescente*</span><span class="sxs-lookup"><span data-stu-id="57ca3-577">**Search direction:** *Ascending*</span></span>

1. <span data-ttu-id="57ca3-578">Selezionare **OK** per chiudere la finestra di dialogo dell'editor di query.</span><span class="sxs-lookup"><span data-stu-id="57ca3-578">Select **OK** to close the query editor dialog box.</span></span>
1. <span data-ttu-id="57ca3-579">Viene visualizzato un messaggio che richiede di confermare l'operazione di ripristino del raggruppamento.</span><span class="sxs-lookup"><span data-stu-id="57ca3-579">A message box prompts you to confirm the grouping reset operation.</span></span> <span data-ttu-id="57ca3-580">Selezionare **Sì** per continuare.</span><span class="sxs-lookup"><span data-stu-id="57ca3-580">Select **Yes** to continue.</span></span>
1. <span data-ttu-id="57ca3-581">Nel riquadro azioni selezionare **Gruppo di modelli di etichette ondata**.</span><span class="sxs-lookup"><span data-stu-id="57ca3-581">On the Action Pane, select **Wave label template group**.</span></span>
1. <span data-ttu-id="57ca3-582">Nella finestra di dialogo **Gruppo di modelli di etichette ondata**, per la riga in cui il campo **Nome campo di riferimento** è impostato su *ID spedizione*, impostare i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="57ca3-582">In the **Wave label template group** dialog box, for the row where the **Reference field name** field is set to *Shipment ID*, set the following values:</span></span>

    - <span data-ttu-id="57ca3-583">**Stampa etichetta di interruzione:** selezionare questa casella di controllo.</span><span class="sxs-lookup"><span data-stu-id="57ca3-583">**Print break label:** Select this check box.</span></span>
    - <span data-ttu-id="57ca3-584">**ID layout etichetta:** selezionare un'etichetta di interruzione.</span><span class="sxs-lookup"><span data-stu-id="57ca3-584">**Label layout ID:** Select a break label.</span></span> <span data-ttu-id="57ca3-585">(ad esempio, selezionare il layout di etichetta *Interruzione* creato in precedenza in questo scenario).</span><span class="sxs-lookup"><span data-stu-id="57ca3-585">(For example, select the *Break* label layout that you created earlier in this scenario.)</span></span>
    - <span data-ttu-id="57ca3-586">**Nome stampante:** selezionare la stampante per l'etichetta di interruzione</span><span class="sxs-lookup"><span data-stu-id="57ca3-586">**Printer name:** Select the printer for the break label.</span></span> <span data-ttu-id="57ca3-587">(in genere, per lo scopo di suddividere i rotoli di etichette, è necessario selezionare la stessa stampante selezionata nella Scheda dettagli **Dettagli modello di etichette ondata**.</span><span class="sxs-lookup"><span data-stu-id="57ca3-587">(Typically, for the purpose of splitting label rolls, you should select the same printer that is selected on the **Wave label template details** FastTab.</span></span> <span data-ttu-id="57ca3-588">Sono tuttavia possibili altri scenari).</span><span class="sxs-lookup"><span data-stu-id="57ca3-588">However, other scenarios are possible.)</span></span>

1. <span data-ttu-id="57ca3-589">Per la riga in cui il campo **Nome campo di riferimento** è impostato su *ID riga di carico di riferimento*, seleziona la casella di controllo **ID build etichetta**.</span><span class="sxs-lookup"><span data-stu-id="57ca3-589">For the row where the **Reference field name** field is set to *Reference load line id*, select the **Label build ID** check box.</span></span>

    > [!NOTE]
    > <span data-ttu-id="57ca3-590">Questa configurazione creerà una sequenza di etichette ("Cartone 1 di X") per riga di carico in tutta l'ondata, indipendentemente dall'impostazione del raggruppamento di lavoro.</span><span class="sxs-lookup"><span data-stu-id="57ca3-590">This setup will create one label sequence ("Carton 1 of X") per load line throughout the wave, regardless of the work grouping setup.</span></span> <span data-ttu-id="57ca3-591">Questa sequenza di etichette può essere stampata su un layout di etichetta.</span><span class="sxs-lookup"><span data-stu-id="57ca3-591">This label sequence can be printed on a label layout.</span></span> <span data-ttu-id="57ca3-592">Inoltre, le etichette di diverse spedizioni saranno separate dall'etichetta di interruzione selezionata.</span><span class="sxs-lookup"><span data-stu-id="57ca3-592">Additionally, labels for different shipments will be separated by the selected break label.</span></span>

1. <span data-ttu-id="57ca3-593">Selezionare **OK** per chiudere la finestra di dialogo **Gruppo di modelli di etichette ondata**.</span><span class="sxs-lookup"><span data-stu-id="57ca3-593">Select **OK** to close the **Wave label template group** dialog box.</span></span>
1. <span data-ttu-id="57ca3-594">Creare un secondo modello di etichetta con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="57ca3-594">Create a second label template that has the following settings:</span></span>

    - <span data-ttu-id="57ca3-595">**Nome modello etichetta:** *Etichette pallet*</span><span class="sxs-lookup"><span data-stu-id="57ca3-595">**Label template name:** *Pallet labels*</span></span>
    - <span data-ttu-id="57ca3-596">**Descrizione:** *Etichette pallet*</span><span class="sxs-lookup"><span data-stu-id="57ca3-596">**Description:** *Pallet labels*</span></span>
    - <span data-ttu-id="57ca3-597">**Codice passaggio ondata:** *Pallet*</span><span class="sxs-lookup"><span data-stu-id="57ca3-597">**Wave step code:** *Pallet*</span></span>
    - <span data-ttu-id="57ca3-598">**Magazzino:** *62*</span><span class="sxs-lookup"><span data-stu-id="57ca3-598">**Warehouse:** *62*</span></span>

1. <span data-ttu-id="57ca3-599">Nella Scheda dettaglio **Generale**, nel campo **Tipo di etichetta ondata**, selezionare un valore, ad esempio *Pallet*.</span><span class="sxs-lookup"><span data-stu-id="57ca3-599">On the **General** FastTab, in the **Wave label type** field, select a value, such as *Pallet*.</span></span>
1. <span data-ttu-id="57ca3-600">Nella Scheda dettaglio **Dettagli modello di etichette ondata**, aggiungere una riga con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="57ca3-600">On the **Wave label template details** FastTab, add a row that has the following settings:</span></span>

    - <span data-ttu-id="57ca3-601">**ID layout etichetta:** *Pallet*</span><span class="sxs-lookup"><span data-stu-id="57ca3-601">**Label layout ID:** *Pallet*</span></span>
    - <span data-ttu-id="57ca3-602">**Nome stampante:** selezionare una stampante ZPL appropriata.</span><span class="sxs-lookup"><span data-stu-id="57ca3-602">**Printer name:** Select an appropriate ZPL printer.</span></span>
    - <span data-ttu-id="57ca3-603">**Esegui query:** *Sì* (questa impostazione è facoltativa, ma è consigliata per prestazioni ottimali).</span><span class="sxs-lookup"><span data-stu-id="57ca3-603">**Run query:** *Yes* (This setting is optional, but it's recommended for optimal performance.)</span></span>

1. <span data-ttu-id="57ca3-604">Nel riquadro azioni selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="57ca3-604">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="57ca3-605">Facoltativo: se si sta progettando un'etichetta specifica per il cliente, è necessario creare una query per trovare il conto del cliente.</span><span class="sxs-lookup"><span data-stu-id="57ca3-605">Optional: If you're setting up a customer-specific label design, you must create a query to find the customer's account.</span></span> <span data-ttu-id="57ca3-606">Nella scheda dettaglio **Dettagli modello di etichette ondata**, selezionare **Modifica query**.</span><span class="sxs-lookup"><span data-stu-id="57ca3-606">On the **Wave label template details** FastTab, select **Edit query**.</span></span> <span data-ttu-id="57ca3-607">Quindi, nella finestra di dialogo dell'editor di query, nella scheda **Intervallo**, aggiungere una riga con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="57ca3-607">Then, in the query editor dialog box, on the **Range** tab, add a row that has the following settings:</span></span>

    - <span data-ttu-id="57ca3-608">**Tabella:** *Spedizioni*</span><span class="sxs-lookup"><span data-stu-id="57ca3-608">**Table:** *Shipments*</span></span>
    - <span data-ttu-id="57ca3-609">**Tabella derivata:** *Spedizioni*</span><span class="sxs-lookup"><span data-stu-id="57ca3-609">**Derived table:** *Shipments*</span></span>
    - <span data-ttu-id="57ca3-610">**Campo:** *Numero di conto*</span><span class="sxs-lookup"><span data-stu-id="57ca3-610">**Field:** *Account number*</span></span>
    - <span data-ttu-id="57ca3-611">**Criteri:** Immettere il numero di conto cliente pertinente.</span><span class="sxs-lookup"><span data-stu-id="57ca3-611">**Criteria:** Enter the relevant customer account number.</span></span>

    <span data-ttu-id="57ca3-612">Al termine, selezionare **OK** per chiudere la finestra di dialogo dell'editor di query.</span><span class="sxs-lookup"><span data-stu-id="57ca3-612">When you've finished, select **OK** to close the query editor dialog box.</span></span> 

1. <span data-ttu-id="57ca3-613">Nel riquadro azioni, selezionare **Modifica query** per aprire la finestra di dialogo dell'editor di query per l'intero modello di etichetta.</span><span class="sxs-lookup"><span data-stu-id="57ca3-613">On the Action Pane, select **Edit query** to open the query editor dialog box for the whole label template.</span></span>
1. <span data-ttu-id="57ca3-614">Nella finestra di dialogo dell'editor di query, nella scheda **Ordinamento**, aggiungere una riga con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="57ca3-614">In the query editor dialog box, on the **Sorting** tab, add a row that has the following settings:</span></span>

    - <span data-ttu-id="57ca3-615">**Tabella:** *Righe di lavoro*</span><span class="sxs-lookup"><span data-stu-id="57ca3-615">**Table:** *Work lines*</span></span>
    - <span data-ttu-id="57ca3-616">**Tabella derivata:** *Righe di lavoro*</span><span class="sxs-lookup"><span data-stu-id="57ca3-616">**Derived table:** *Work lines*</span></span>
    - <span data-ttu-id="57ca3-617">**Campo:** *ID riga di carico di riferimento (ID record)*</span><span class="sxs-lookup"><span data-stu-id="57ca3-617">**Field:** *Reference load line id (Record-ID)*</span></span>
    - <span data-ttu-id="57ca3-618">**Direzione di ricerca:** *Crescente*</span><span class="sxs-lookup"><span data-stu-id="57ca3-618">**Search direction:** *Ascending*</span></span>

1. <span data-ttu-id="57ca3-619">Aggiungere una seconda riga con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="57ca3-619">Add a second row that has the following settings:</span></span>

    - <span data-ttu-id="57ca3-620">**Tabella:** *Righe di lavoro*</span><span class="sxs-lookup"><span data-stu-id="57ca3-620">**Table:** *Work lines*</span></span>
    - <span data-ttu-id="57ca3-621">**Tabella derivata:** *Righe di lavoro*</span><span class="sxs-lookup"><span data-stu-id="57ca3-621">**Derived table:** *Work lines*</span></span>
    - <span data-ttu-id="57ca3-622">**Campo:** *ID spedizione*</span><span class="sxs-lookup"><span data-stu-id="57ca3-622">**Field:** *Shipment ID*</span></span>
    - <span data-ttu-id="57ca3-623">**Direzione di ricerca:** *Crescente*</span><span class="sxs-lookup"><span data-stu-id="57ca3-623">**Search direction:** *Ascending*</span></span>

1. <span data-ttu-id="57ca3-624">Selezionare **OK** per chiudere la finestra di dialogo dell'editor di query.</span><span class="sxs-lookup"><span data-stu-id="57ca3-624">Select **OK** to close the query editor dialog box.</span></span>
1. <span data-ttu-id="57ca3-625">Viene visualizzato un messaggio che richiede di confermare l'operazione di ripristino del raggruppamento.</span><span class="sxs-lookup"><span data-stu-id="57ca3-625">A message box prompts you to confirm the grouping reset operation.</span></span> <span data-ttu-id="57ca3-626">Selezionare **Sì** per continuare.</span><span class="sxs-lookup"><span data-stu-id="57ca3-626">Select **Yes** to continue.</span></span>
1. <span data-ttu-id="57ca3-627">Nel riquadro azioni selezionare **Gruppo di modelli di etichette ondata**.</span><span class="sxs-lookup"><span data-stu-id="57ca3-627">On the Action Pane, select **Wave label template group**.</span></span>
1. <span data-ttu-id="57ca3-628">Nella finestra di dialogo **Gruppo di modelli di etichette ondata**, per la riga in cui il campo **Nome campo di riferimento** è impostato su *ID spedizione*, impostare i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="57ca3-628">In the **Wave label template group** dialog box, for the row where the **Reference field name** field is set to *Shipment ID*, set the following values:</span></span>

    - <span data-ttu-id="57ca3-629">**Stampa etichetta di interruzione:** selezionare questa casella di controllo.</span><span class="sxs-lookup"><span data-stu-id="57ca3-629">**Print break label:** Select this check box.</span></span>
    - <span data-ttu-id="57ca3-630">**ID layout etichetta:** selezionare un'etichetta di interruzione.</span><span class="sxs-lookup"><span data-stu-id="57ca3-630">**Label layout ID:** Select a break label.</span></span> <span data-ttu-id="57ca3-631">(ad esempio, selezionare il layout di etichetta *Interruzione* creato in precedenza in questo scenario).</span><span class="sxs-lookup"><span data-stu-id="57ca3-631">(For example, select the *Break* label layout that you created earlier in this scenario.)</span></span>
    - <span data-ttu-id="57ca3-632">**Nome stampante:** selezionare la stampante per l'etichetta di interruzione</span><span class="sxs-lookup"><span data-stu-id="57ca3-632">**Printer name:** Select the printer for the break label.</span></span> <span data-ttu-id="57ca3-633">(in genere, per lo scopo di suddividere i rotoli di etichette, è necessario selezionare la stessa stampante selezionata nella Scheda dettagli **Dettagli modello di etichette ondata**.</span><span class="sxs-lookup"><span data-stu-id="57ca3-633">(Typically, for the purpose of splitting label rolls, you should select the same printer that is selected on the **Wave label template details** FastTab.</span></span> <span data-ttu-id="57ca3-634">Sono tuttavia possibili altri scenari).</span><span class="sxs-lookup"><span data-stu-id="57ca3-634">However, other scenarios are possible.)</span></span>

1. <span data-ttu-id="57ca3-635">Per la riga in cui il campo **Nome campo di riferimento** è impostato su *ID riga di carico di riferimento*, seleziona la casella di controllo **ID build etichetta**.</span><span class="sxs-lookup"><span data-stu-id="57ca3-635">For the row where the **Reference field name** field is set to *Reference load line id*, select the **Label build ID** check box.</span></span>

    > [!NOTE]
    > <span data-ttu-id="57ca3-636">Questa configurazione creerà una sequenza di etichette ("Cartone 1 di X") per riga di carico in tutta l'ondata, indipendentemente dall'impostazione del raggruppamento di lavoro.</span><span class="sxs-lookup"><span data-stu-id="57ca3-636">This setup will create one label sequence ("Carton 1 of X") per load line throughout the wave, regardless of the work grouping setup.</span></span> <span data-ttu-id="57ca3-637">Questa sequenza di etichette può essere stampata su un layout di etichetta.</span><span class="sxs-lookup"><span data-stu-id="57ca3-637">This label sequence can be printed on a label layout.</span></span> <span data-ttu-id="57ca3-638">Inoltre, le etichette di diverse spedizioni saranno separate dall'etichetta di interruzione selezionata.</span><span class="sxs-lookup"><span data-stu-id="57ca3-638">Additionally, labels for different shipments will be separated by the selected break label.</span></span>

### <a name="configure-number-sequence-extensions"></a><span data-ttu-id="57ca3-639">Configurare le estensioni di sequenza numerica</span><span class="sxs-lookup"><span data-stu-id="57ca3-639">Configure number sequence extensions</span></span>

<span data-ttu-id="57ca3-640">Le estensioni di sequenza numerica controllano la conformità GS1 delle sequenze numeriche specifiche.</span><span class="sxs-lookup"><span data-stu-id="57ca3-640">Number sequence extensions control the GS1 compliance of specific number sequences.</span></span> <span data-ttu-id="57ca3-641">Questa configurazione è facoltativa per lo scenario corrente.</span><span class="sxs-lookup"><span data-stu-id="57ca3-641">This configuration is optional for the current scenario.</span></span> <span data-ttu-id="57ca3-642">Per ulteriori informazioni e istruzioni sulla configurazione, vedere [Configurare le estensioni di sequenza numerica](../warehousing/configure-number-sequence-extensions.md).</span><span class="sxs-lookup"><span data-stu-id="57ca3-642">For more information and configuration instructions, see [Configure number sequence extensions](../warehousing/configure-number-sequence-extensions.md).</span></span>

### <a name="create-a-sales-order-and-release-it-to-the-warehouse"></a><span data-ttu-id="57ca3-643">Creare un ordine cliente e rilasciarlo nel magazzino</span><span class="sxs-lookup"><span data-stu-id="57ca3-643">Create a sales order and release it to the warehouse</span></span>

1. <span data-ttu-id="57ca3-644">Andare a **Vendite e marketing \> Ordine cliente \> Tutti gli ordini cliente**.</span><span class="sxs-lookup"><span data-stu-id="57ca3-644">Go to **Sales and marketing \> Sales order \> All sales orders**.</span></span>
1. <span data-ttu-id="57ca3-645">Crea un ordine cliente con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="57ca3-645">Create a sales order that has the following settings:</span></span>

    - <span data-ttu-id="57ca3-646">**Conto cliente:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="57ca3-646">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="57ca3-647">**Magazzino:** *62*</span><span class="sxs-lookup"><span data-stu-id="57ca3-647">**Warehouse:** *62*</span></span>

1. <span data-ttu-id="57ca3-648">Aggiungere due righe ordine cliente:</span><span class="sxs-lookup"><span data-stu-id="57ca3-648">Add two sales order lines:</span></span>

    - <span data-ttu-id="57ca3-649">Riga ordine cliente 1:</span><span class="sxs-lookup"><span data-stu-id="57ca3-649">Sales order line 1:</span></span>

        - <span data-ttu-id="57ca3-650">**Numero articolo:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="57ca3-650">**Item number:** *A0001*</span></span>
        - <span data-ttu-id="57ca3-651">**Quantità:** *9024*</span><span class="sxs-lookup"><span data-stu-id="57ca3-651">**Quantity:** *9024*</span></span>
        - <span data-ttu-id="57ca3-652">**Unità:** *unità* (9024 unità = 376 scatole = 47 pallet)</span><span class="sxs-lookup"><span data-stu-id="57ca3-652">**Unit:** *ea* (9024 ea = 376 Box = 47 PL)</span></span>

    - <span data-ttu-id="57ca3-653">Riga ordine cliente 2:</span><span class="sxs-lookup"><span data-stu-id="57ca3-653">Sales order line 2:</span></span>

        - <span data-ttu-id="57ca3-654">**Numero articolo:** *A0002*</span><span class="sxs-lookup"><span data-stu-id="57ca3-654">**Item number:** *A0002*</span></span>
        - <span data-ttu-id="57ca3-655">**Quantità:** *9016*</span><span class="sxs-lookup"><span data-stu-id="57ca3-655">**Quantity:** *9016*</span></span>
        - <span data-ttu-id="57ca3-656">**Unità:** *unità* (9016 unità = 322 scatole = 46 pallet)</span><span class="sxs-lookup"><span data-stu-id="57ca3-656">**Unit:** *ea* (9016 ea = 322 Box = 46 PL)</span></span>

    > [!NOTE]
    > <span data-ttu-id="57ca3-657">Gli articoli e le quantità forniti qui sono solo esempi.</span><span class="sxs-lookup"><span data-stu-id="57ca3-657">The items and quantities that are provided here are only examples.</span></span> <span data-ttu-id="57ca3-658">Devono utilizzare il gruppo di sequenze di unità definito in precedenza, conversioni di unità appropriate da *unità* a *scatola* a *pallet* devono essere definite per gli stessi e devono avere stock nel magazzino *62*.</span><span class="sxs-lookup"><span data-stu-id="57ca3-658">They must use the unit sequence group that you defined earlier, appropriate unit conversions from *ea* to *Box* to *PL* must be defined for them, and they must have stock in warehouse *62*.</span></span> <span data-ttu-id="57ca3-659">Per ulteriori informazioni, vedere [Unità di misura e politiche di stoccaggio](unit-measure-stocking-policies.md).</span><span class="sxs-lookup"><span data-stu-id="57ca3-659">For more information, see [Unit of measure and stocking policies](unit-measure-stocking-policies.md).</span></span>

1. <span data-ttu-id="57ca3-660">Selezionare la riga ordine cliente 1.</span><span class="sxs-lookup"><span data-stu-id="57ca3-660">Select sales order line 1.</span></span> <span data-ttu-id="57ca3-661">Nella sezione **Riga ordine cliente**, nel menu **Scorte**, selezionare **Prenotazioni**.</span><span class="sxs-lookup"><span data-stu-id="57ca3-661">Then, in the **Sales order line** section, on the **Inventory** menu, select **Reservations**.</span></span>
1. <span data-ttu-id="57ca3-662">Nella pagina **Prenotazione** del riquadro azioni, selezionare **Prenota lotto** e chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="57ca3-662">On the **Reservation** page, on the Action Pane, select **Reserve lot**, and then close the page.</span></span>
1. <span data-ttu-id="57ca3-663">Ripetere i passaggi 4 e 5 per la riga ordine cliente 2.</span><span class="sxs-lookup"><span data-stu-id="57ca3-663">Repeat steps 4 and 5 for sales order line 2.</span></span>
1. <span data-ttu-id="57ca3-664">Nel riquadro azioni, nella scheda **Magazzino**, seleziona **Rilascia in magazzino**.</span><span class="sxs-lookup"><span data-stu-id="57ca3-664">On the Action Pane, on the **Warehouse** tab, select **Release to warehouse**.</span></span>

    <span data-ttu-id="57ca3-665">Si verificano gli eventi seguenti:</span><span class="sxs-lookup"><span data-stu-id="57ca3-665">The following events occur:</span></span> 

    - <span data-ttu-id="57ca3-666">Il sistema elabora la spedizione creata utilizzando il modello che include il passaggio di stampa dell'etichetta.</span><span class="sxs-lookup"><span data-stu-id="57ca3-666">The system processes the created shipment by using the template that includes the label printing step.</span></span> <span data-ttu-id="57ca3-667">Il layout di etichetta verrà utilizzato per definire il formato dell'etichetta e il risultato sarà un'etichetta stampata sulla stampante selezionata nel modello di etichetta.</span><span class="sxs-lookup"><span data-stu-id="57ca3-667">The label layout will be used to define the format of the label, and the result will be a label that is printed on the printer that is selected in the label template.</span></span>
    - <span data-ttu-id="57ca3-668">Le etichette ondata vengono generate e stampate.</span><span class="sxs-lookup"><span data-stu-id="57ca3-668">Wave labels are generated and printed.</span></span> <span data-ttu-id="57ca3-669">Il numero di etichette sarà uguale al numero di cartoni (in questo esempio, 376 etichette scatola per la riga 1, 322 etichette scatola per la riga 2, 47 etichette pallet per la riga 1, 47 etichette pallet per la riga 2 e due etichette di interruzione che hanno l'ID spedizione).</span><span class="sxs-lookup"><span data-stu-id="57ca3-669">The number of labels will equal the number of cartons (in this example, 376 Box labels for line 1, 322 Box labels for line 2, 47 PL labels for line 1, 47 PL labels for line 2, and two break labels that have the shipment ID).</span></span>
    - <span data-ttu-id="57ca3-670">Viene generato un nuovo ID polizza di carico per le spedizioni.</span><span class="sxs-lookup"><span data-stu-id="57ca3-670">A new bill of lading ID is generated for the shipments.</span></span> <span data-ttu-id="57ca3-671">Se sono state configurate le estensioni della sequenza numerica, gli ID etichetta ondata avranno il formato numerico **SSCC-18**.</span><span class="sxs-lookup"><span data-stu-id="57ca3-671">If you configured the number sequence extensions, the wave label IDs will follow the **SSCC-18** number format.</span></span> 

<span data-ttu-id="57ca3-672">È possibile visualizzare e ristampare le etichette ondata dalle seguenti pagine:</span><span class="sxs-lookup"><span data-stu-id="57ca3-672">You can view and reprint wave labels from the following pages:</span></span>

- <span data-ttu-id="57ca3-673">Tutte le spedizioni \> Dettagli spedizione</span><span class="sxs-lookup"><span data-stu-id="57ca3-673">All shipments \> Shipment details</span></span>
- <span data-ttu-id="57ca3-674">Tutti i carichi \> Dettagli carico</span><span class="sxs-lookup"><span data-stu-id="57ca3-674">All loads \> Load details</span></span>
- <span data-ttu-id="57ca3-675">Tutte le ondate</span><span class="sxs-lookup"><span data-stu-id="57ca3-675">All waves</span></span>
- <span data-ttu-id="57ca3-676">Etichette ondata</span><span class="sxs-lookup"><span data-stu-id="57ca3-676">Wave labels</span></span>
- <span data-ttu-id="57ca3-677">Storico etichette ondata</span><span class="sxs-lookup"><span data-stu-id="57ca3-677">Wave label history</span></span>

<span data-ttu-id="57ca3-678">Per la maggior parte di queste pagine, è possibile trovare la funzione pertinente selezionando **Etichette ondata** nel gruppo **Informazioni correlate** della scheda **Spedizioni** del riquadro azioni.</span><span class="sxs-lookup"><span data-stu-id="57ca3-678">For most of these pages, you can find the relevant function by selecting **Wave labels** in the **Related information** group on the **Shipments** tab of the Action Pane.</span></span>