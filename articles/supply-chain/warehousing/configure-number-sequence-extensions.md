---
title: Configurare sequenze numeriche per flussi di magazzino
description: Questo argomento fornisce una panoramica della funzionalità che fornisce estensioni di sequenza numerica per ID targa, ID etichetta ondata, ID contenitore e ID polizza di carico.
author: GarmMSFT
manager: tfehr
ms.date: 06/10/2020
ms.topic: configure-number-sequence-extensions
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSNumberSequenceExtension
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: v-olbara
ms.search.validFrom: 2020-06-10
ms.dyn365.ops.version: 10.0.2
ms.openlocfilehash: 3ee74ba108008ccef53fe3b904c71ddf5f51afb7
ms.sourcegitcommit: 137e2bd30f0a85bd2e1baf1cf16b993edd2094f9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2020
ms.locfileid: "3546440"
---
# <a name="configure-number-sequences-for-warehouse-flows"></a><span data-ttu-id="c59d5-103">Configurare sequenze numeriche per flussi di magazzino</span><span class="sxs-lookup"><span data-stu-id="c59d5-103">Configure number sequences for warehouse flows</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c59d5-104">La funzionalità *Estensioni di sequenza numerica* aggiunge una nuova pagina di configurazione per l'impostazione di sequenze numeriche.</span><span class="sxs-lookup"><span data-stu-id="c59d5-104">The *Number sequence extensions* feature adds a new configuration page for setting up number sequences.</span></span> <span data-ttu-id="c59d5-105">Consente la configurazione flessibile di ID regolati da GS1, inclusi prefissi GS1 e cifre di controllo (modulo 10), e applica un limite di lunghezza sulle sequenze numeriche esistenti.</span><span class="sxs-lookup"><span data-stu-id="c59d5-105">It enables flexible configuration of GS1-regulated IDs, including GS1 prefixes and check digits (modulo 10), and enforces a length limit on existing number sequences.</span></span>

<span data-ttu-id="c59d5-106">I segmenti di sequenza numerica standard non sono adatti per l'implementazione GS1, poiché non viene calcolata alcuna cifra di controllo e il prefisso GS1 dell'azienda deve essere aggiornato manualmente.</span><span class="sxs-lookup"><span data-stu-id="c59d5-106">Standard number sequence segments aren't suitable for GS1 implementation, because no check digit is calculated, and the company's GS1 prefix must be updated manually.</span></span>

<span data-ttu-id="c59d5-107">Questa soluzione aggiunge le seguenti funzionalità:</span><span class="sxs-lookup"><span data-stu-id="c59d5-107">This feature adds the following functionality:</span></span>

- <span data-ttu-id="c59d5-108">Gli ID polizza di carico possono essere generati in anticipo.</span><span class="sxs-lookup"><span data-stu-id="c59d5-108">Bill of lading (BOL) IDs can be generated in advance.</span></span>
- <span data-ttu-id="c59d5-109">È possibile generare una sequenza numerica univoca per i numeri SSCC.</span><span class="sxs-lookup"><span data-stu-id="c59d5-109">A unique number sequence can be generated for serial shipping container code (SSCC) numbers.</span></span>
- <span data-ttu-id="c59d5-110">È possibile creare sequenze numeriche conformi a GS1 per numeri di polizza di carico e SSCC.</span><span class="sxs-lookup"><span data-stu-id="c59d5-110">GS1-compliant number sequences can be created for BOL and SSCC numbers.</span></span> <span data-ttu-id="c59d5-111">La funzionalità aggiunge supporto predefinito per ID targa, ID contenitore, ID etichetta ondata e ID polizza di carico.</span><span class="sxs-lookup"><span data-stu-id="c59d5-111">The feature adds out-of-box support for license plate IDs, container IDs, wave label IDs, and BOL IDs.</span></span>
- <span data-ttu-id="c59d5-112">La configurazione dei numeri ID targa è flessibile.</span><span class="sxs-lookup"><span data-stu-id="c59d5-112">Configuration of license plate ID numbers is flexible.</span></span> <span data-ttu-id="c59d5-113">Ad esempio, è possibile includere o escludere l'intelligenza artificiale (IA), come gli zeri iniziali (00).</span><span class="sxs-lookup"><span data-stu-id="c59d5-113">For example, you can include or exclude artificial intelligence (AI), such as leading zeros (00).</span></span>

<span data-ttu-id="c59d5-114">Questa funzionalità rende più efficiente il supporto dell'etichettatura di cartoni e la regolazione di nuovi numeri generati dal sistema.</span><span class="sxs-lookup"><span data-stu-id="c59d5-114">This functionality makes it more efficient to support labeling of cartons and to adjust new numbers that are generated by the system.</span></span>

## <a name="turn-on-the-number-sequence-extensions-feature"></a><span data-ttu-id="c59d5-115">Attivare la funzionalità Estensioni di sequenza numerica</span><span class="sxs-lookup"><span data-stu-id="c59d5-115">Turn on the Number sequence extensions feature</span></span>

<span data-ttu-id="c59d5-116">Prima di poter utilizzare questa funzionalità, è necessario attivarla nel sistema.</span><span class="sxs-lookup"><span data-stu-id="c59d5-116">Before you can use the feature, it must be turned on in your system.</span></span> <span data-ttu-id="c59d5-117">Gli amministratori possono utilizzare l'area di lavoro [Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) per controllare lo stato della funzionalità e attivarla se necessario.</span><span class="sxs-lookup"><span data-stu-id="c59d5-117">Admins can use the [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) workspace to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="c59d5-118">Nell'area di lavoro, la funzionalità è elencata nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="c59d5-118">There, the feature is listed in the following way:</span></span>

- <span data-ttu-id="c59d5-119">**Modulo:** *Gestione Magazzino*</span><span class="sxs-lookup"><span data-stu-id="c59d5-119">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="c59d5-120">**Nome funzionalità:** *Estensioni di sequenza numerica*</span><span class="sxs-lookup"><span data-stu-id="c59d5-120">**Feature name:** *Number sequence extensions*</span></span>

## <a name="set-up-the-feature"></a><span data-ttu-id="c59d5-121">Configurare la funzionalità</span><span class="sxs-lookup"><span data-stu-id="c59d5-121">Set up the feature</span></span>

<span data-ttu-id="c59d5-122">Per configurare le estensioni di sequenza numerica nel sistema, attenersi alla seguente procedura.</span><span class="sxs-lookup"><span data-stu-id="c59d5-122">To set up number sequence extensions in your system, follow these steps.</span></span>

1. <span data-ttu-id="c59d5-123">Fare clic su **Gestione magazzino \> Impostazione \> Parametri di gestione magazzino**.</span><span class="sxs-lookup"><span data-stu-id="c59d5-123">Go to **Warehouse management \> Setup \> Warehouse management parameters**.</span></span>
1. <span data-ttu-id="c59d5-124">Nella scheda **Generale**, nel campo **Prefisso società GS1** immettere il prefisso GS1 della propria società.</span><span class="sxs-lookup"><span data-stu-id="c59d5-124">On the **General** tab, in the **GS1 company prefix** field, and enter your company's GS1 prefix.</span></span> <span data-ttu-id="c59d5-125">Questo valore influirà su tutte le sequenze numeriche in cui il prefisso GS1 è incluso come segmento.</span><span class="sxs-lookup"><span data-stu-id="c59d5-125">This value will affect all number sequences where the GS1 prefix is included as a segment.</span></span>
1. <span data-ttu-id="c59d5-126">Se si desidera generare numeri di polizza di carico per etichette ondata, nella scheda **Report**, selezionare la casella di controllo **Genera numero polizza di carico quando si stampano etichette ondata**.</span><span class="sxs-lookup"><span data-stu-id="c59d5-126">If you want to generate BOL numbers for wave labels, on the **Reports** tab, select the **Generate BOL number when printing wave labels** check box.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c59d5-127">Questa casella di controllo è disponibile solo se la funzionalità per la [stampa di etichette ondata](configure-wave-label-printing.md) è attivata.</span><span class="sxs-lookup"><span data-stu-id="c59d5-127">This check box is available only if the functionality for [wave label printing](configure-wave-label-printing.md) is turned on.</span></span>

1. <span data-ttu-id="c59d5-128">Andare a **Gestione magazzino** \> **Impostazioni** \> **Estensioni di sequenza numerica**</span><span class="sxs-lookup"><span data-stu-id="c59d5-128">Go to **Warehouse management** \> **Setup** \> **Number sequence extensions**</span></span>
1. <span data-ttu-id="c59d5-129">Nel riquadro azioni, selezionare **Crea impostazione predefinita**.</span><span class="sxs-lookup"><span data-stu-id="c59d5-129">On the Action Pane, select **Create default setup**.</span></span> <span data-ttu-id="c59d5-130">Vengono creati una sequenza numerica di polizze di carico conforme a GS1 e tre tipi di sequenze numeriche SSCC.</span><span class="sxs-lookup"><span data-stu-id="c59d5-130">A GS1-compliant BOL number sequence and three types of SSCC number sequences are created.</span></span> <span data-ttu-id="c59d5-131">Tutte queste sequenze numeriche tengono conto della lunghezza del prefisso GS1 della società.</span><span class="sxs-lookup"><span data-stu-id="c59d5-131">All these number sequences take the length of your company's GS1 prefix into account.</span></span>

    <span data-ttu-id="c59d5-132">Per ulteriori informazioni su come personalizzare queste sequenze numeriche predefinite e/o aggiungere nuove sequenze, vedere la sezione successiva.</span><span class="sxs-lookup"><span data-stu-id="c59d5-132">For more information about how to customize these default number sequences and/or add new sequences, see the next section.</span></span> <span data-ttu-id="c59d5-133">È anche possibile rimuovere una di queste sequenze se non è necessaria.</span><span class="sxs-lookup"><span data-stu-id="c59d5-133">You can also remove any of these sequences if you don't need them.</span></span>

1. <span data-ttu-id="c59d5-134">Ritornare **Gestione magazzino \> Impostazione \> Parametri di gestione magazzino**.</span><span class="sxs-lookup"><span data-stu-id="c59d5-134">Go back to **Warehouse management \> Setup \> Warehouse management parameters**.</span></span>
1. <span data-ttu-id="c59d5-135">Nella scheda **Sequenze numeriche**, selezionare un'estensione di sequenza numerica pertinente da utilizzare per generare numeri per ID targa, ID etichetta ondata, ID contenitore (in questo caso, selezionare la sequenza **Numero SSCC-18** appropriata) e/o ID polizza di carico (in questo caso, selezionare la sequenza **Polizza di carico**).</span><span class="sxs-lookup"><span data-stu-id="c59d5-135">On the **Number sequences** tab, select a relevant number sequence extension to use to generate numbers for your license plate IDs, wave label IDs, container IDs (in this case, select the appropriate **SSCC-18 number** sequence), and/or BOL IDs (in this case, select the **BOL** sequence).</span></span> <span data-ttu-id="c59d5-136">Per impostazione predefinita, le estensioni di sequenza numerica sono supportate solo per questi quattro tipi di ID.</span><span class="sxs-lookup"><span data-stu-id="c59d5-136">By default, number sequence extensions are supported only for these four types of IDs.</span></span>

<span data-ttu-id="c59d5-137">La prossima volta che viene generato un nuovo numero per una di queste sequenze numeriche, verrà utilizzata la nuova logica.</span><span class="sxs-lookup"><span data-stu-id="c59d5-137">The next time that a new number is generated for one of these number sequences, the new logic will be used.</span></span>

> [!NOTE]
> <span data-ttu-id="c59d5-138">Se non si seleziona un'estensione di sequenza numerica per gli ID targa, verranno utilizzate le regole correnti per la generazione di ID targa.</span><span class="sxs-lookup"><span data-stu-id="c59d5-138">If you don't select a number sequence extension for license plate IDs, the current rules for generating license plate IDs will be used.</span></span> <span data-ttu-id="c59d5-139">Altrimenti, verrà utilizzata la sequenza numerica selezionata.</span><span class="sxs-lookup"><span data-stu-id="c59d5-139">Otherwise, your selected number sequence will be used.</span></span> <span data-ttu-id="c59d5-140">Gli altri ID useranno una sequenza numerica semplice fino a quando non si applica un'estensione di sequenza numerica per tali ID.</span><span class="sxs-lookup"><span data-stu-id="c59d5-140">The other IDs will use a plain number sequence until you apply a number sequence extension for them.</span></span>

## <a name="create-and-edit-number-sequences"></a><span data-ttu-id="c59d5-141">Creare e modificare sequenze numeriche</span><span class="sxs-lookup"><span data-stu-id="c59d5-141">Create and edit number sequences</span></span>

<span data-ttu-id="c59d5-142">Nella sezione precedente, è stato generato un set predefinito di sequenze numeriche.</span><span class="sxs-lookup"><span data-stu-id="c59d5-142">In the previous section, you generated a default set of number sequences.</span></span> <span data-ttu-id="c59d5-143">Questa sezione spiega come viene definita ciascuna sequenza numerica.</span><span class="sxs-lookup"><span data-stu-id="c59d5-143">This section explains how each number sequence is defined.</span></span> <span data-ttu-id="c59d5-144">Descrive inoltre come creare sequenze personalizzate e come modificare le sequenze predefinite o personalizzate.</span><span class="sxs-lookup"><span data-stu-id="c59d5-144">It also explains how to create custom sequences, and how to edit the default or custom sequences.</span></span>

<span data-ttu-id="c59d5-145">Per creare e modificare sequenze numeriche, attenersi alla seguente procedura.</span><span class="sxs-lookup"><span data-stu-id="c59d5-145">To create and edit number sequences, follow these steps.</span></span>

1. <span data-ttu-id="c59d5-146">Andare a **Gestione magazzino** \> **Impostazioni** \> **Estensioni di sequenza numerica**.</span><span class="sxs-lookup"><span data-stu-id="c59d5-146">Go to **Warehouse management** \> **Setup** \> **Number sequence extensions**.</span></span>
1. <span data-ttu-id="c59d5-147">Nel Riquadro azioni selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="c59d5-147">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="c59d5-148">Nel campo **Estensione di sequenza numerica**, immettere un nome per la nuova sequenza.</span><span class="sxs-lookup"><span data-stu-id="c59d5-148">In the **Number sequence extension** field, enter a name for the new sequence.</span></span> <span data-ttu-id="c59d5-149">Nel campo **Descrizione** immettere una descrizione.</span><span class="sxs-lookup"><span data-stu-id="c59d5-149">In the **Description** field, enter a description.</span></span>
1. <span data-ttu-id="c59d5-150">Nella Scheda dettaglio **Segmenti**, utilizzare i pulsanti sulla barra degli strumenti per assemblare il formato di numerazione aggiungendo, eliminando e disponendo i segmenti.</span><span class="sxs-lookup"><span data-stu-id="c59d5-150">On the **Segments** FastTab, use the buttons on the toolbar to assemble your numbering format by adding, deleting, and arranging segments.</span></span> <span data-ttu-id="c59d5-151">Nel campo **Segmento** di ogni riga, assegnare un tipo di segmento per definire lo scopo e il contenuto di quel segmento.</span><span class="sxs-lookup"><span data-stu-id="c59d5-151">In the **Segment** field for each row, assign a segment type to define the purpose and content of that segment.</span></span> <span data-ttu-id="c59d5-152">Nella seguente tabella vengono illustrati i tipi di segmenti disponibili.</span><span class="sxs-lookup"><span data-stu-id="c59d5-152">The following table describes the types of segments that are available.</span></span>

    | <span data-ttu-id="c59d5-153">Tipo di segmento</span><span class="sxs-lookup"><span data-stu-id="c59d5-153">Segment type</span></span> | <span data-ttu-id="c59d5-154">descrizione</span><span class="sxs-lookup"><span data-stu-id="c59d5-154">Description</span></span> |
    |---|---|
    | <span data-ttu-id="c59d5-155">Costante</span><span class="sxs-lookup"><span data-stu-id="c59d5-155">Constant</span></span> | <span data-ttu-id="c59d5-156">Questo tipo di segmento aggiunge lo stesso testo costante per ciascun numero generato nella sequenza.</span><span class="sxs-lookup"><span data-stu-id="c59d5-156">This segment type adds the same constant text for each generated number in the sequence.</span></span> <span data-ttu-id="c59d5-157">Nel campo **Valore** immettere il testo necessario.</span><span class="sxs-lookup"><span data-stu-id="c59d5-157">In the **Value** field, enter the required text.</span></span> <span data-ttu-id="c59d5-158">Il campo **Lunghezza** viene automaticamente aggiornato alla lunghezza del testo immesso nel campo **Valore**.</span><span class="sxs-lookup"><span data-stu-id="c59d5-158">The **Length** field is automatically updated to the length of the text that you entered in the **Value** field.</span></span> |
    | <span data-ttu-id="c59d5-159">Sequenza numerica</span><span class="sxs-lookup"><span data-stu-id="c59d5-159">Number sequence</span></span> | <span data-ttu-id="c59d5-160">Nel campo **Valore** immettere un segno numerico (*\#*) per ogni carattere che dovrebbe essere mostrato nella sequenza generata.</span><span class="sxs-lookup"><span data-stu-id="c59d5-160">In the **Value** field, enter a number sign (*\#*) for each character that should be shown in the generated sequence.</span></span> <span data-ttu-id="c59d5-161">La sequenza numerica stessa potrebbe generare numeri più lunghi, ma verranno visualizzati solo i caratteri più a destra.</span><span class="sxs-lookup"><span data-stu-id="c59d5-161">The number sequence itself might generate longer numbers, but only the right-most characters will be shown.</span></span> <span data-ttu-id="c59d5-162">Il campo **Lunghezza** viene automaticamente aggiornato al numero di segni numerici immessi nel campo **Valore**.</span><span class="sxs-lookup"><span data-stu-id="c59d5-162">The **Length** field is automatically updated to the number of number signs that you entered in the **Value** field.</span></span><p><span data-ttu-id="c59d5-163">Per soddisfare i requisiti GS1 per i numeri SSCC-18, assicurarsi che la lunghezza di questo segmento sia 16 meno la lunghezza del prefisso GS1.</span><span class="sxs-lookup"><span data-stu-id="c59d5-163">To comply with GS1 requirements for SSCC-18 numbers, make sure that the length of this segment is 16 minus the length of your GS1 prefix.</span></span></p> |
    | <span data-ttu-id="c59d5-164">Prefisso GS1</span><span class="sxs-lookup"><span data-stu-id="c59d5-164">GS1 prefix</span></span> | <span data-ttu-id="c59d5-165">Questo tipo di segmento aggiunge il valore impostato nel campo **Prefisso società GS1** alla pagina **Parametri di gestione magazzino**.</span><span class="sxs-lookup"><span data-stu-id="c59d5-165">This segment type adds the value that is set in the **GS1 company prefix** field on the **Warehouse management parameters** page.</span></span> <span data-ttu-id="c59d5-166">Il campo **Valore** mostra il valore impostato nella **Parametri di gestione magazzino** e il campo **Lunghezza** mostra il numero di caratteri nel valore.</span><span class="sxs-lookup"><span data-stu-id="c59d5-166">The **Value** field shows the value that is set on the **Warehouse management parameters** page, and the **Length** field shows the number of characters in the value.</span></span> <span data-ttu-id="c59d5-167">Il campo **Valore** e il campo **Lunghezza** sono entrambi di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="c59d5-167">Both the **Value** field and the **Length** field are read-only.</span></span> |
    | <span data-ttu-id="c59d5-168">Identificatore applicazione</span><span class="sxs-lookup"><span data-stu-id="c59d5-168">Application identifier</span></span> | <span data-ttu-id="c59d5-169">Nel campo **Valore**, immettere un identificatore dell'applicazione, come specificato dai criteri GS1 pertinenti per questo tipo di sequenza numerica.</span><span class="sxs-lookup"><span data-stu-id="c59d5-169">In the **Value** field, enter an application identifier, as specified by the relevant GS1 policy for this type of number sequence.</span></span> <span data-ttu-id="c59d5-170">Ad esempio, immettere *00* per SSCC o *420* per Polizza di carico.</span><span class="sxs-lookup"><span data-stu-id="c59d5-170">For example, enter *00* for SSCC or *420* for BOL.</span></span> <span data-ttu-id="c59d5-171">Il campo **Lunghezza** viene automaticamente aggiornato alla lunghezza dell'identificatore immesso nel campo **Valore**.</span><span class="sxs-lookup"><span data-stu-id="c59d5-171">The **Length** field is automatically updated to the length of the identifier that you entered in the **Value** field.</span></span> |
    | <span data-ttu-id="c59d5-172">Tipo di imballaggio</span><span class="sxs-lookup"><span data-stu-id="c59d5-172">Packing type</span></span> | <span data-ttu-id="c59d5-173">Per gli articoli che possono essere chiaramente identificati, questo tipo di segmento aggiunge un valore di campo dal relativo gruppo di sequenze unità (nella pagina **Gruppi di sequenze unità**)</span><span class="sxs-lookup"><span data-stu-id="c59d5-173">For items that can be clearly identified, this segment type adds a field value from the relevant unit sequence group (from the **Unit sequence groups** page).</span></span> <span data-ttu-id="c59d5-174">(questo comportamento corrisponde alla logica esistente per gli ID targa). Per le targhe che includono più unità di stockkeeping (SKU), questo tipo di segmento aggiunge *0* (zero) per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="c59d5-174">(This behavior matches the existing logic for license plate IDs.) For license plates that include multiple stock keeping units (SKUs), this segment type adds *0* (zero) by default.</span></span> <span data-ttu-id="c59d5-175">Per questo tipo di segmento, il campo **Valore** è sempre impostato su *P* e il campo **Lunghezza** è sempre impostato su *1*.</span><span class="sxs-lookup"><span data-stu-id="c59d5-175">For this segment type, the **Value** field is always set to *P*, and the **Length** field is always set to *1*.</span></span>|
    | <span data-ttu-id="c59d5-176">Cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="c59d5-176">Check digit</span></span> | <span data-ttu-id="c59d5-177">Questo tipo di segmento aggiunge una cifra di controllo, che è un calcolo del modulo 10</span><span class="sxs-lookup"><span data-stu-id="c59d5-177">This segment type adds a check digit, which is a modulo 10 calculation.</span></span> <span data-ttu-id="c59d5-178">(questo comportamento corrisponde alla logica esistente per gli ID targa). Per questo tipo di segmento, il campo **Valore** è sempre impostato su un accento circonflesso (*^*) e il campo **Lunghezza** è sempre impostato su *1*.</span><span class="sxs-lookup"><span data-stu-id="c59d5-178">(This behavior matches the existing logic for license plate IDs.) For this segment type, the **Value** field is always set to a caret (*^*), and the **Length** field is always set to *1*.</span></span> |

1. <span data-ttu-id="c59d5-179">Per visualizzare un esempio del formato numerico finale, controllare il campo **Formato** nella parte inferiore della Scheda dettaglio **Segmenti**.</span><span class="sxs-lookup"><span data-stu-id="c59d5-179">To view an example of your final number format, inspect the **Format** field at the bottom of the **Segments** FastTab.</span></span>