---
title: Numerazione cronologica di documenti e giustificativi
description: Questo argomento spiega come impostare e utilizzare i numeri cronologici per i documenti applicabili e i relativi giustificativi.
author: ikond
manager: AnnBe
ms.date: 02/01/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: NumberSequenceGroup
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 401195
ms.search.region: Global
ms.author: ilyako
ms.search.validFrom: 2021-03-15
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 31745632de7339d167ac9f18f02e6611e1a78b28
ms.sourcegitcommit: e88c96d1cb817a22db81856cadb563c095ab2671
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/02/2021
ms.locfileid: "5104402"
---
# <a name="numbering-documents-and-vouchers-chronologically"></a><span data-ttu-id="2f8f4-103">Numerazione cronologica di documenti e giustificativi</span><span class="sxs-lookup"><span data-stu-id="2f8f4-103">Numbering documents and vouchers chronologically</span></span>

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

<span data-ttu-id="2f8f4-104">In alcuni paesi, esiste l'obbligo legale di numerare i documenti e i relativi giustificativi in ordine cronologico.</span><span class="sxs-lookup"><span data-stu-id="2f8f4-104">In some countries, there is a legal requirement to number documents and related vouchers in chronological order.</span></span> <span data-ttu-id="2f8f4-105">La cronologia deve essere supportata in base a periodi.</span><span class="sxs-lookup"><span data-stu-id="2f8f4-105">The chronology must be supported by periods.</span></span> <span data-ttu-id="2f8f4-106">Tutti i numeri che appartengono a periodi precedenti devono essere inferiori ai numeri che appartengono a periodi successivi.</span><span class="sxs-lookup"><span data-stu-id="2f8f4-106">All of the numbers that belong to earlier periods must be less than the numbers that belong to later periods.</span></span> <span data-ttu-id="2f8f4-107">Per soddisfare questo requisito, è stata implementata la funzionalità di numerazione cronologica.</span><span class="sxs-lookup"><span data-stu-id="2f8f4-107">To meet this requirement, chronological numbering functionality has been implemented.</span></span> <span data-ttu-id="2f8f4-108">Questo argomento spiega come configurare e utilizzare i numeri cronologici per i documenti applicabili e i relativi giustificativi.</span><span class="sxs-lookup"><span data-stu-id="2f8f4-108">This topic explains how to configure and use chronological numbers for applicable documents and related vouchers.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="2f8f4-109">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="2f8f4-109">Prerequisites</span></span>

<span data-ttu-id="2f8f4-110">Nell'area di lavoro Gestione funzionalità, abilita la funzionalità **Numerazione cronologica**.</span><span class="sxs-lookup"><span data-stu-id="2f8f4-110">In the Feature management workspace, turn on the **Chronological numbering** feature.</span></span> <span data-ttu-id="2f8f4-111">Per ulteriori informazioni, vedere [Panoramica della gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).</span><span class="sxs-lookup"><span data-stu-id="2f8f4-111">For more information, see [Feature management overview](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).</span></span>

## <a name="configure-chronological-numbering"></a><span data-ttu-id="2f8f4-112">Configurare la numerazione cronologica</span><span class="sxs-lookup"><span data-stu-id="2f8f4-112">Configure chronological numbering</span></span>

<span data-ttu-id="2f8f4-113">La numerazione cronologica interessa i seguenti documenti.</span><span class="sxs-lookup"><span data-stu-id="2f8f4-113">Chronological numbering affects the following documents.</span></span>

<span data-ttu-id="2f8f4-114">**Contabilità clienti**</span><span class="sxs-lookup"><span data-stu-id="2f8f4-114">**Accounts receivable**</span></span>
- <span data-ttu-id="2f8f4-115">Fattura cliente</span><span class="sxs-lookup"><span data-stu-id="2f8f4-115">Customer invoice</span></span>
- <span data-ttu-id="2f8f4-116">Giustificativo fattura cliente</span><span class="sxs-lookup"><span data-stu-id="2f8f4-116">Customer invoice voucher</span></span>
- <span data-ttu-id="2f8f4-117">Nota di accredito vendita</span><span class="sxs-lookup"><span data-stu-id="2f8f4-117">Sales credit note</span></span>
- <span data-ttu-id="2f8f4-118">Giustificativo nota di accredito vendita</span><span class="sxs-lookup"><span data-stu-id="2f8f4-118">Sales credit note voucher</span></span>
- <span data-ttu-id="2f8f4-119">Fattura a testo libero</span><span class="sxs-lookup"><span data-stu-id="2f8f4-119">Free text invoice</span></span>
- <span data-ttu-id="2f8f4-120">Giustificativo fattura a testo libero</span><span class="sxs-lookup"><span data-stu-id="2f8f4-120">Free text invoice voucher</span></span>
- <span data-ttu-id="2f8f4-121">Nota di accredito a testo libero</span><span class="sxs-lookup"><span data-stu-id="2f8f4-121">Free text credit note</span></span>
- <span data-ttu-id="2f8f4-122">Giustificativo nota di accredito a testo libero</span><span class="sxs-lookup"><span data-stu-id="2f8f4-122">Free text credit note voucher</span></span>
- <span data-ttu-id="2f8f4-123">Documento di trasporto</span><span class="sxs-lookup"><span data-stu-id="2f8f4-123">Packing slip</span></span>
- <span data-ttu-id="2f8f4-124">Giustificativo documento di trasporto</span><span class="sxs-lookup"><span data-stu-id="2f8f4-124">Packing slip voucher</span></span>
- <span data-ttu-id="2f8f4-125">Giustificativo di correzione documento di trasporto</span><span class="sxs-lookup"><span data-stu-id="2f8f4-125">Packing slip correction voucher</span></span>
- <span data-ttu-id="2f8f4-126">Giustificativo nota d'interesse</span><span class="sxs-lookup"><span data-stu-id="2f8f4-126">Interest note voucher</span></span>
- <span data-ttu-id="2f8f4-127">Giustificativo lettera di sollecito</span><span class="sxs-lookup"><span data-stu-id="2f8f4-127">Collection letter voucher</span></span>

<span data-ttu-id="2f8f4-128">**Contabilità fornitori**</span><span class="sxs-lookup"><span data-stu-id="2f8f4-128">**Accounts payable**</span></span>
- <span data-ttu-id="2f8f4-129">Giustificativo fattura</span><span class="sxs-lookup"><span data-stu-id="2f8f4-129">Invoice voucher</span></span>
- <span data-ttu-id="2f8f4-130">Giustificativo nota di accredito</span><span class="sxs-lookup"><span data-stu-id="2f8f4-130">Credit note voucher</span></span>
- <span data-ttu-id="2f8f4-131">Giustificativo entrata prodotti</span><span class="sxs-lookup"><span data-stu-id="2f8f4-131">Product receipt voucher</span></span>

<span data-ttu-id="2f8f4-132">**Gestione progetti**</span><span class="sxs-lookup"><span data-stu-id="2f8f4-132">**Project management**</span></span>
- <span data-ttu-id="2f8f4-133">Fattura</span><span class="sxs-lookup"><span data-stu-id="2f8f4-133">Invoice</span></span>
- <span data-ttu-id="2f8f4-134">Giustificativo fattura</span><span class="sxs-lookup"><span data-stu-id="2f8f4-134">Invoice voucher</span></span>
- <span data-ttu-id="2f8f4-135">Nota di accredito</span><span class="sxs-lookup"><span data-stu-id="2f8f4-135">Credit note</span></span>
- <span data-ttu-id="2f8f4-136">Giustificativo nota di accredito</span><span class="sxs-lookup"><span data-stu-id="2f8f4-136">Credit note voucher</span></span> 

### <a name="define-number-sequences"></a><span data-ttu-id="2f8f4-137">Definire le sequenze numeriche</span><span class="sxs-lookup"><span data-stu-id="2f8f4-137">Define number sequences</span></span>

<span data-ttu-id="2f8f4-138">Per definire sequenze numeriche, vai a **Amministrazione organizzazione** > **Sequenze numeriche** > **Sequenze numeriche**.</span><span class="sxs-lookup"><span data-stu-id="2f8f4-138">To define number sequences, go to **Organization administration** > **Number sequences** > **Number sequences**.</span></span> <span data-ttu-id="2f8f4-139">È possibile definire tutte le sequenze numeriche necessarie per coprire i periodi interessati dei documenti richiesti.</span><span class="sxs-lookup"><span data-stu-id="2f8f4-139">You can define as many number sequences as required to cover the affected periods for required documents.</span></span> 

<span data-ttu-id="2f8f4-140">Specifica una società per ogni sequenza numerica.</span><span class="sxs-lookup"><span data-stu-id="2f8f4-140">Specify a company for each number sequence.</span></span> <span data-ttu-id="2f8f4-141">I segmenti delle sequenze numeriche devono essere definiti in modo che forniscano un ordine cronologico per i periodi.</span><span class="sxs-lookup"><span data-stu-id="2f8f4-141">The segments of the number sequences must be defined so that they provide chronological order for periods.</span></span> <span data-ttu-id="2f8f4-142">Ad esempio, i nomi dei segmenti possono contenere un prefisso speciale che identifica un periodo specifico.</span><span class="sxs-lookup"><span data-stu-id="2f8f4-142">For example, the segment names can contain a special prefix that identifies a specific period.</span></span>

![Impostazione della sequenza numerica](media/chrono-num-sequence.jpg)

### <a name="configure-number-sequence-groups"></a><span data-ttu-id="2f8f4-144">Configurare i gruppi di sequenze numeriche</span><span class="sxs-lookup"><span data-stu-id="2f8f4-144">Configure number sequence groups</span></span>

<span data-ttu-id="2f8f4-145">Per configurare i gruppi di sequenze numeriche, vai a **Contabilità clienti** > **Impostazione** > **Parametri contabilità clienti**.</span><span class="sxs-lookup"><span data-stu-id="2f8f4-145">To configure number sequence groups, go to **Accounts receivable** > **Setup** > **Accounts receivable parameters**.</span></span> <span data-ttu-id="2f8f4-146">Nella scheda **Sequenze numeriche** definisci tutti i gruppi di sequenze numeriche necessari per coprire i periodi interessati.</span><span class="sxs-lookup"><span data-stu-id="2f8f4-146">On the **Number sequences** tab, define as many number sequences groups as required to cover the affected periods.</span></span> 

<span data-ttu-id="2f8f4-147">Per ogni gruppo, nella sezione **Riferimento** seleziona uno dei riferimenti di documenti supportati e nel campo **Codice sequenza numerica** e fai riferimento a una sequenza numerica creata in precedenza per il periodo correlato.</span><span class="sxs-lookup"><span data-stu-id="2f8f4-147">For each group, in the **Reference** section, select one of the supported document references, and in the **Number sequence code** field, refer to a number sequence that was previously created for the related period.</span></span>

![Impostazione del gruppo di sequenze numeriche](media/chrono-num-sequence-group.jpg)

<span data-ttu-id="2f8f4-149">Allo stesso modo, configura i gruppi di sequenze numeriche nei moduli **Contabilità fornitori** e **Gestione progetti e contabilità**.</span><span class="sxs-lookup"><span data-stu-id="2f8f4-149">Similarly, configure number sequence groups in **Accounts payable** and **Project management and accounting** modules.</span></span>

### <a name="configure-number-sequence-groups-chronology"></a><span data-ttu-id="2f8f4-150">Configurare la cronologia dei gruppi di sequenze numeriche</span><span class="sxs-lookup"><span data-stu-id="2f8f4-150">Configure number sequence groups chronology</span></span>

<span data-ttu-id="2f8f4-151">Per configurare la cronologia dei gruppi di sequenze numeriche, vai a **Amministrazione organizzazione** > **Sequenze numeriche** > **Gruppi di sequenze numeriche cronologiche**.</span><span class="sxs-lookup"><span data-stu-id="2f8f4-151">To configure number sequence groups chronology, go to **Organization administration** > **Number sequences** > **Chronological number sequence groups**.</span></span> <span data-ttu-id="2f8f4-152">Definisci le condizioni di applicabilità per i gruppi di sequenze numeriche.</span><span class="sxs-lookup"><span data-stu-id="2f8f4-152">Define the applicability conditions for number sequence groups.</span></span>

![Impostazione dei numeri cronologici](media/chrono-num-sequence-group-period.jpg)

| <span data-ttu-id="2f8f4-154">Campo</span><span class="sxs-lookup"><span data-stu-id="2f8f4-154">Field</span></span>            | <span data-ttu-id="2f8f4-155">descrizione</span><span class="sxs-lookup"><span data-stu-id="2f8f4-155">Description</span></span>                                                                                                                                                                                                                                                                                                                                                                                   |
|---------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="2f8f4-156">Valido</span><span class="sxs-lookup"><span data-stu-id="2f8f4-156">Effective</span></span>  | <span data-ttu-id="2f8f4-157">La data di inizio dell'applicabilità del gruppo di sequenze numeriche.</span><span class="sxs-lookup"><span data-stu-id="2f8f4-157">The start date of number sequence group applicability.</span></span> |
| <span data-ttu-id="2f8f4-158">Scadenza</span><span class="sxs-lookup"><span data-stu-id="2f8f4-158">Expiration</span></span>      | <span data-ttu-id="2f8f4-159">La data di fine dell'applicabilità del gruppo di sequenze numeriche.</span><span class="sxs-lookup"><span data-stu-id="2f8f4-159">The end date of number sequence group applicability.</span></span> <span data-ttu-id="2f8f4-160">Se non si applica alcuna data di fine, seleziona **Mai**.</span><span class="sxs-lookup"><span data-stu-id="2f8f4-160">If no end date is applied, select **Never**.</span></span> |
| <span data-ttu-id="2f8f4-161">Gruppo di sequenze numeriche</span><span class="sxs-lookup"><span data-stu-id="2f8f4-161">Number sequence group</span></span> | <span data-ttu-id="2f8f4-162">Gruppo di sequenza numerica che verrà utilizzato per generare i numeri di documento durante il periodo.</span><span class="sxs-lookup"><span data-stu-id="2f8f4-162">Number sequence group that will be used to generate document numbers during the period.</span></span> |
| <span data-ttu-id="2f8f4-163">Gruppo di sequenze numeriche originale</span><span class="sxs-lookup"><span data-stu-id="2f8f4-163">Original number sequence group</span></span> | <span data-ttu-id="2f8f4-164">Questo codice di gruppo di sequenza numerica viene utilizzato per i filtri aggiuntivi nei casi in cui i documenti hanno già un specifico gruppo di sequenze numeriche *permanente* assegnato.</span><span class="sxs-lookup"><span data-stu-id="2f8f4-164">This number sequence group code is used for additional filtering for the cases when documents already have a specific *permanent* number sequence group assigned.</span></span> <span data-ttu-id="2f8f4-165">Un valore vuoto è considerato un valore specifico.</span><span class="sxs-lookup"><span data-stu-id="2f8f4-165">An empty value is considered a specific value.</span></span> <span data-ttu-id="2f8f4-166">Se è necessario ignorare un gruppo assegnato preliminarmente, utilizza l'opzione **Predefinito** per questa configurazione.</span><span class="sxs-lookup"><span data-stu-id="2f8f4-166">If you need to ignore a preliminary assigned group, use the **Default** option for this setup.</span></span> |
| <span data-ttu-id="2f8f4-167">Predefinita</span><span class="sxs-lookup"><span data-stu-id="2f8f4-167">Default</span></span> | <span data-ttu-id="2f8f4-168">Se attivato, il sistema ignora il gruppo di sequenza numerica documento assegnato in precedenza e utilizza solo le date di inizio e di fine dei periodi per l'analisi di applicabilità.</span><span class="sxs-lookup"><span data-stu-id="2f8f4-168">If turned on, the system ignores the preliminary assigned document number sequence group and uses only the periods start and end dates for applicability analysis.</span></span> <span data-ttu-id="2f8f4-169">Se disattivato, il sistema utilizza la combinazione completa **Validità** + **Scadenza** + **Gruppo di sequenza numerica originale** per la selezione.</span><span class="sxs-lookup"><span data-stu-id="2f8f4-169">If turned off, the system uses the full combination **Effective** + **Expiration** + **Original number sequence group** for selection.</span></span> |

## <a name="document-posting"></a><span data-ttu-id="2f8f4-170">Registrazione del documento</span><span class="sxs-lookup"><span data-stu-id="2f8f4-170">Document posting</span></span>
<span data-ttu-id="2f8f4-171">Quando si registra un documento, il gruppo di sequenza numerica appropriato viene assegnato al documento, in base alla data di registrazione del documento, e quindi utilizzato per generare un numero di documento in base alla sequenza numerica rilevata.</span><span class="sxs-lookup"><span data-stu-id="2f8f4-171">When you post a document, the appropriate number sequence group is assigned to the document, based on document's posting date, and then used to generate a document number based on the detected number sequence.</span></span> <span data-ttu-id="2f8f4-172">Il sistema fornisce un messaggio relativo all'assegnazione del gruppo di sequenze numeriche.</span><span class="sxs-lookup"><span data-stu-id="2f8f4-172">The system provides a message regarding the number sequence group assignment.</span></span>

![Numero documento](media/chrono-num-sequence-fti.jpg)

> [!NOTE]
> <span data-ttu-id="2f8f4-174">Per alcuni paesi esiste una logica specifica già implementata per la numerazione dei documenti.</span><span class="sxs-lookup"><span data-stu-id="2f8f4-174">For some countries, there is a specific logic already implemented for document numbering.</span></span> <span data-ttu-id="2f8f4-175">In questo caso, la logica specifica del paese avrà la precedenza sulla funzionalità **Numerazione cronologica**.</span><span class="sxs-lookup"><span data-stu-id="2f8f4-175">In this case, country-specific logic will override the **Chronological numbering** feature.</span></span>
