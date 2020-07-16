---
title: Certificazione unica
description: Questo argomento fornisce informazioni sulla certificazione unica per le società in Italia.
author: ilkond
manager: AnnBe
ms.date: 06/30/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Italy
ms.author: ilyako
ms.search.validFrom: 2020-06-01
ms.dyn365.ops.version: 10.0.9
ms.openlocfilehash: 30c6f3e3ef973b211ef6564a4d68aa391a61d66e
ms.sourcegitcommit: ce397c2759f642c595e30fef58a770b50360b2bd
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "3527622"
---
# <a name="unique-certification"></a><span data-ttu-id="328c5-103">Certificazione unica</span><span class="sxs-lookup"><span data-stu-id="328c5-103">Unique certification</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="328c5-104">In Italia, gli addetti alla ritenuta d'acconto devono comunicare elettronicamente la certificazione unica all'agenzia delle entrate per certificare le seguenti informazioni:</span><span class="sxs-lookup"><span data-stu-id="328c5-104">In Italy, withholding tax agents must electronically communicate the Unique certification to the revenue agency to certify the following information:</span></span>

- <span data-ttu-id="328c5-105">Reddito di lavoro dipendente</span><span class="sxs-lookup"><span data-stu-id="328c5-105">Income of dependent employments</span></span>
- <span data-ttu-id="328c5-106">Reddito autonomo</span><span class="sxs-lookup"><span data-stu-id="328c5-106">Self-employed income</span></span>
- <span data-ttu-id="328c5-107">Provvigioni</span><span class="sxs-lookup"><span data-stu-id="328c5-107">Commissions</span></span>
- <span data-ttu-id="328c5-108">Altri redditi</span><span class="sxs-lookup"><span data-stu-id="328c5-108">Other income</span></span>

## <a name="prerequisites"></a><span data-ttu-id="328c5-109">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="328c5-109">Prerequisites</span></span>

<span data-ttu-id="328c5-110">Per poter utilizzare questa funzionalità è necessario soddisfare i seguenti prerequisiti:</span><span class="sxs-lookup"><span data-stu-id="328c5-110">The following prerequisites must be met before the functionality can be used:</span></span>

- <span data-ttu-id="328c5-111">L'indirizzo principale della persona giuridica deve essere in Italia.</span><span class="sxs-lookup"><span data-stu-id="328c5-111">The primary address of the legal entity must be in Italy.</span></span>
- <span data-ttu-id="328c5-112">La funzionalità **Certificazione unica** deve essere attivata nell'area di lavoro **Gestione funzionalità**.</span><span class="sxs-lookup"><span data-stu-id="328c5-112">The **Unique certification** feature must be turned on in the **Feature management** workspace.</span></span> <span data-ttu-id="328c5-113">Per ulteriori informazioni, vedere [Panoramica della gestione funzionalità](../../fin-and-ops/get-started/feature-management/feature-management-overview.md).</span><span class="sxs-lookup"><span data-stu-id="328c5-113">For more information, see [Feature management overview](../../fin-and-ops/get-started/feature-management/feature-management-overview.md).</span></span>

## <a name="set-up-the-unique-certification"></a><span data-ttu-id="328c5-114">Impostare la certificazione unica</span><span class="sxs-lookup"><span data-stu-id="328c5-114">Set up the Unique certification</span></span>

### <a name="set-up-a-number-sequence"></a><span data-ttu-id="328c5-115">Impostare una sequenza numerica</span><span class="sxs-lookup"><span data-stu-id="328c5-115">Set up a number sequence</span></span>

1. <span data-ttu-id="328c5-116">Selezionare **Contabilità generale** \> **Impostazione contabilità generale** \> **Parametri di contabilità generale**.</span><span class="sxs-lookup"><span data-stu-id="328c5-116">Go to **General ledger** \> **Ledger setup** \> **General ledger parameters**.</span></span>
2. <span data-ttu-id="328c5-117">Nella scheda **Sequenze numeriche** nella scheda **ID certificazione unica**, definire una sequenza numerica.</span><span class="sxs-lookup"><span data-stu-id="328c5-117">On the **Number sequences** tab, in the **Unique certification Id** field, define a number sequence.</span></span>

### <a name="set-up-the-unique-certification-values"></a><span data-ttu-id="328c5-118">Impostare i valori della certificazione unica</span><span class="sxs-lookup"><span data-stu-id="328c5-118">Set up the unique certification values</span></span>

1. <span data-ttu-id="328c5-119">Vai a **Imposta** \> **Impostazione** \> **Ritenuta d'acconto** \> **Imposta valori di certificazione univoci**</span><span class="sxs-lookup"><span data-stu-id="328c5-119">Go to **Tax** \> **Setup** \> **Withholding tax** \> **Set up unique certification values**</span></span>
2. <span data-ttu-id="328c5-120">Specifica i valori per la funzionalità **Certificazione unica**.</span><span class="sxs-lookup"><span data-stu-id="328c5-120">Specify the values for the **Unique certification** feature.</span></span>

<span data-ttu-id="328c5-121">La pagina **Imposta valori di certificazione univoca** consente di configurare i valori disponibili per diversi campi:</span><span class="sxs-lookup"><span data-stu-id="328c5-121">The **Set up unique certification values** page allows you to configure the values available for several fields:</span></span>

- <span data-ttu-id="328c5-122">**Record B**: Eventi eccezionali</span><span class="sxs-lookup"><span data-stu-id="328c5-122">**record B**: Exceptional events</span></span>
- <span data-ttu-id="328c5-123">**record D** : eventi eccezionali, categorie speciali e province unificate</span><span class="sxs-lookup"><span data-stu-id="328c5-123">**record D**: Exceptional events, special categories, and unified counties</span></span>
- <span data-ttu-id="328c5-124">**Record H**: motivo e codice</span><span class="sxs-lookup"><span data-stu-id="328c5-124">**record H**: Reason and code</span></span>

<span data-ttu-id="328c5-125">Il formato del modello telematico della certificazione unica è stato aggiornato secondo le nuove specifiche nell'aggiornamento normativo della certificazione unica, valido dal 7 marzo 2018:</span><span class="sxs-lookup"><span data-stu-id="328c5-125">The format of the telematics model of unique certification has been updated according to the new specifications in the regulatory update of Unique Certification, valid from March 7, 2018:</span></span>

- <span data-ttu-id="328c5-126">**Record A**: codice di fornitura CUR18</span><span class="sxs-lookup"><span data-stu-id="328c5-126">**record A**: CUR18 supply code</span></span>
- <span data-ttu-id="328c5-127">**Record B**: nuovi valori per eventi eccezionali</span><span class="sxs-lookup"><span data-stu-id="328c5-127">**record B**: New values for exceptional events</span></span>
- <span data-ttu-id="328c5-128">**Record D**: nuovi valori per eventi eccezionali e categorie speciali e introduzione di campi di province unificate</span><span class="sxs-lookup"><span data-stu-id="328c5-128">**record D**: New values for exceptional events and special categories and the introduction of unified counties fields</span></span>
- <span data-ttu-id="328c5-129">**Record H**: nuovi valori per i campi motivo e codice</span><span class="sxs-lookup"><span data-stu-id="328c5-129">**record H**: New values for reason and code fields</span></span>
- <span data-ttu-id="328c5-130">**Record Z**: conteggio di record L su 0</span><span class="sxs-lookup"><span data-stu-id="328c5-130">**record Z**: Count of L records to 0</span></span>

<span data-ttu-id="328c5-131">I valori specificati sulla pagina **Imposta valori di certificazione unica** e contrassegnati con **Sì** nella colonna **Attivo**, saranno disponibili nei relativi campi di ricerca nella pagina **Certificazione unica**.</span><span class="sxs-lookup"><span data-stu-id="328c5-131">Values that are specified on **Setup Unique Certification values** page, and marked with **Yes** in the **Active** column, will be available in the related lookup fields on the **Unique certification** page.</span></span> <span data-ttu-id="328c5-132">Utilizza questa pagina per futuri aggiornamenti normativi della certificazione unica per aggiungere o eliminare valori.</span><span class="sxs-lookup"><span data-stu-id="328c5-132">Use this page for future regulatory upgrades of the unique certification to add or delete values.</span></span>

<span data-ttu-id="328c5-133">È possibile importare il set iniziale di valori per **Impostazione valori di certificazione unica** utilizzando l'entità **Impostazione valori certificazione unica** (UniqueCertificationValueEntity) e il framework di gestione dei dati.</span><span class="sxs-lookup"><span data-stu-id="328c5-133">You can import the initial set of values for **Setup Unique Certification values** by using the **Setup Unique certification values** (UniqueCertificationValueEntity) entity and the Data management framework.</span></span> <span data-ttu-id="328c5-134">Per ulteriori informazioni, vedere [Panoramica dei processi di importazione ed esportazione dei dati](../../dev-itpro/data-entities/data-import-export-job.md).</span><span class="sxs-lookup"><span data-stu-id="328c5-134">For more information, see [Data import and export jobs overview](../../dev-itpro/data-entities/data-import-export-job.md).</span></span> <span data-ttu-id="328c5-135">È possibile scaricare il set iniziale di valori per **Imposta valori di certificazione unica** dal file **IT SetupUniqueCertificationValues** nella sezione del tipo di dati risorsa **Pacchetto dati** della **Libreria di risorse condivisa** nel [Portale LCS](https://lcs.dynamics.com/v2) e quindi importarlo nel framework di gestione dei dati.</span><span class="sxs-lookup"><span data-stu-id="328c5-135">You can download the initial set of values for the **Setup Unique Certification values** from the **IT SetupUniqueCertificationValues** file in the **Data package** asset data type section of the **Shared asset library** in the [LCS portal](https://lcs.dynamics.com/v2) and then import it in to the Data management framework.</span></span>

<span data-ttu-id="328c5-136">I dati di origine utilizzati per l'importazione possono essere presentati come un file di Microsoft Excel con i seguenti nomi di colonna:</span><span class="sxs-lookup"><span data-stu-id="328c5-136">The source data used for import can be presented as a Microsoft Excel file that has the following column names:</span></span>

- <span data-ttu-id="328c5-137">FIELD</span><span class="sxs-lookup"><span data-stu-id="328c5-137">FIELD</span></span>
- <span data-ttu-id="328c5-138">VALORE</span><span class="sxs-lookup"><span data-stu-id="328c5-138">VALUE</span></span>
- <span data-ttu-id="328c5-139">ACTIVE</span><span class="sxs-lookup"><span data-stu-id="328c5-139">ACTIVE</span></span>
- <span data-ttu-id="328c5-140">VALUEDESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="328c5-140">VALUEDESCRIPTION</span></span>

### <a name="set-up-a-revenue-typology-for-the-unique-certification"></a><span data-ttu-id="328c5-141">Impostare una tipologia di entrate per la certificazione unica</span><span class="sxs-lookup"><span data-stu-id="328c5-141">Set up a revenue typology for the Unique certification</span></span>

<span data-ttu-id="328c5-142">È necessario impostare una tipologia di entrate nel campo **Tipologia di entrate** nella sezione **Fattura e consegna** della pagina **Fornitori**.</span><span class="sxs-lookup"><span data-stu-id="328c5-142">You must set up a revenue typology in the **Revenue typology** field in the **Invoice and delivery** section on the **Vendors** page.</span></span>

### <a name="set-up-a-format-for-the-unique-certification"></a><span data-ttu-id="328c5-143">Impostare un formato per la certificazione unica</span><span class="sxs-lookup"><span data-stu-id="328c5-143">Set up a format for the Unique certification</span></span>

1. <span data-ttu-id="328c5-144">Selezionare **Contabilità generale** \> **Impostazione contabilità generale** \> **Parametri di contabilità generale**.</span><span class="sxs-lookup"><span data-stu-id="328c5-144">Go to **General ledger** \> **Ledger setup** \> **General ledger parameters**.</span></span>
2. <span data-ttu-id="328c5-145">Nella scheda **Ritenuta d'acconto** nel campo **Mapping formato certificazione unica**, definire il formato ER da utilizzare per generare la certificazione unica.</span><span class="sxs-lookup"><span data-stu-id="328c5-145">On the **Withholding tax** tab, in the **Unique Certification format mapping** field, define the Electronic reporting (ER) format that should be used to generate the Unique certification.</span></span>

## <a name="generate-the-unique-certification"></a><span data-ttu-id="328c5-146">Generare la certificazione unica</span><span class="sxs-lookup"><span data-stu-id="328c5-146">Generate the Unique certification</span></span>

1. <span data-ttu-id="328c5-147">Selezionare **Imposta** \>**Dichiarazioni** \> **Ritenuta d'acconto** \> **Certificazione unica**.</span><span class="sxs-lookup"><span data-stu-id="328c5-147">Go to **Tax** \> **Declarations** \> **Withholding tax** \> **Unique Certification**.</span></span>
2. <span data-ttu-id="328c5-148">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="328c5-148">Select **New**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="328c5-149">L'anno precedente l'anno della data di sistema corrente viene automaticamente assegnato come anno di riferimento della dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="328c5-149">The year before the year of the current system date is automatically assigned as the reporting year of the declaration.</span></span>

3. <span data-ttu-id="328c5-150">Nella sezione **Titolo pagina**, immettere le informazioni sulla società e le informazioni sulla persona responsabile della trasmissione della certificazione unica all'agenzia delle entrate.</span><span class="sxs-lookup"><span data-stu-id="328c5-150">In the **Title-page** section, enter the company information and the information about the person who is in charge of communicating the Unique certification to the revenue agency.</span></span>
4. <span data-ttu-id="328c5-151">Selezionare **Genera** per creare le certificazioni per ogni destinatario e compilare automaticamente le altre sezioni.</span><span class="sxs-lookup"><span data-stu-id="328c5-151">Select **Generate** to create the certifications for each recipient and to automatically fill in the other sections.</span></span> <span data-ttu-id="328c5-152">La sezione **Fornitore** contiene l'elenco dei destinatari (fornitori) e i dettagli sui fornitori.</span><span class="sxs-lookup"><span data-stu-id="328c5-152">The **Vendor** section contains the list of recipients (vendors) and the vendor details.</span></span>
5. <span data-ttu-id="328c5-153">Selezionare **Generare dettagli** per immettere i dettagli delle transazioni dei fornitori nella dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="328c5-153">Select **Generate details** to enter the details of vendors transactions in the declaration.</span></span>
6. <span data-ttu-id="328c5-154">La sezione **Ritenuta d'acconto** mostra gli importi di ogni certificazione dei fornitori.</span><span class="sxs-lookup"><span data-stu-id="328c5-154">The **Withholding tax** section shows the amounts of each vendor certification.</span></span> <span data-ttu-id="328c5-155">Gli importi sono calcolati e ordinati per codice ritenuta d'acconto.</span><span class="sxs-lookup"><span data-stu-id="328c5-155">The amounts are calculated and sorted by withholding tax code.</span></span>

## <a name="process-the-unique-certification"></a><span data-ttu-id="328c5-156">Elaborare la certificazione unica</span><span class="sxs-lookup"><span data-stu-id="328c5-156">Process the Unique certification</span></span>

<span data-ttu-id="328c5-157">Dopo che la certificazione univoca è stata generata e riempita con i dati, è possibile selezionare **Convalida** per convalidare i dati prima che venga generato il file di output.</span><span class="sxs-lookup"><span data-stu-id="328c5-157">After the Unique certification is generated and filled with data, you can select **Validate** to validate the data before the output file is generated.</span></span> <span data-ttu-id="328c5-158">Dopo la convalida del file di output, selezionare **Esporta** per generare il file di output elettronico nel formato legalmente richiesto.</span><span class="sxs-lookup"><span data-stu-id="328c5-158">After the output file is validated, select **Export** to generate the electronic output file in the legally required format.</span></span>
