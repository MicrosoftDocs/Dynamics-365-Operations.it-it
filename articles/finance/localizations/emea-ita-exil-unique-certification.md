---
title: Certificazione unica
description: Questo argomento fornisce informazioni sulla certificazione unica per le società in Italia.
author: ilkond
manager: AnnBe
ms.date: 02/06/2020
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
ms.openlocfilehash: 3b13e6196afeb757d6130e431011593129d9a61d
ms.sourcegitcommit: 523049c363a999050c58d20695f1c7d151b3fd3e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "3029523"
---
# <a name="unique-certification"></a><span data-ttu-id="203cb-103">Certificazione unica</span><span class="sxs-lookup"><span data-stu-id="203cb-103">Unique certification</span></span>

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

<span data-ttu-id="203cb-104">In Italia, gli addetti alla ritenuta d'acconto devono comunicare elettronicamente la certificazione unica all'agenzia delle entrate per certificare le seguenti informazioni:</span><span class="sxs-lookup"><span data-stu-id="203cb-104">In Italy, withholding tax agents must electronically communicate the Unique certification to the revenue agency to certify the following information:</span></span>

- <span data-ttu-id="203cb-105">Reddito di lavoro dipendente</span><span class="sxs-lookup"><span data-stu-id="203cb-105">Income of dependent employments</span></span>
- <span data-ttu-id="203cb-106">Reddito autonomo</span><span class="sxs-lookup"><span data-stu-id="203cb-106">Self-employed income</span></span>
- <span data-ttu-id="203cb-107">Provvigioni</span><span class="sxs-lookup"><span data-stu-id="203cb-107">Commissions</span></span>
- <span data-ttu-id="203cb-108">Altri redditi</span><span class="sxs-lookup"><span data-stu-id="203cb-108">Other income</span></span>

## <a name="prerequisites"></a><span data-ttu-id="203cb-109">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="203cb-109">Prerequisites</span></span>

<span data-ttu-id="203cb-110">Per poter utilizzare questa funzionalità è necessario soddisfare i seguenti prerequisiti:</span><span class="sxs-lookup"><span data-stu-id="203cb-110">The following prerequisites must be met before the functionality can be used:</span></span>

- <span data-ttu-id="203cb-111">L'indirizzo principale della persona giuridica deve essere in Italia.</span><span class="sxs-lookup"><span data-stu-id="203cb-111">The primary address of the legal entity must be in Italy.</span></span>
- <span data-ttu-id="203cb-112">La funzionalità **Certificazione unica** deve essere attivata nell'area di lavoro **Gestione funzionalità**.</span><span class="sxs-lookup"><span data-stu-id="203cb-112">The **Unique certification** feature must be turned on in the **Feature management** workspace.</span></span> <span data-ttu-id="203cb-113">Per ulteriori informazioni, vedere [Panoramica della gestione funzionalità](../../fin-and-ops/get-started/feature-management/feature-management-overview.md).</span><span class="sxs-lookup"><span data-stu-id="203cb-113">For more information, see [Feature management overview](../../fin-and-ops/get-started/feature-management/feature-management-overview.md).</span></span>

## <a name="set-up-the-unique-certification"></a><span data-ttu-id="203cb-114">Impostare la certificazione unica</span><span class="sxs-lookup"><span data-stu-id="203cb-114">Set up the Unique certification</span></span>

### <a name="set-up-a-number-sequence"></a><span data-ttu-id="203cb-115">Impostare una sequenza numerica</span><span class="sxs-lookup"><span data-stu-id="203cb-115">Set up a number sequence</span></span>

1. <span data-ttu-id="203cb-116">Selezionare **Contabilità generale** \> **Impostazione contabilità generale** \> **Parametri di contabilità generale**.</span><span class="sxs-lookup"><span data-stu-id="203cb-116">Go to **General ledger** \> **Ledger setup** \> **General ledger parameters**.</span></span>
2. <span data-ttu-id="203cb-117">Nella scheda **Sequenze numeriche** nella scheda **ID certificazione unica**, definire una sequenza numerica.</span><span class="sxs-lookup"><span data-stu-id="203cb-117">On the **Number sequences** tab, in the **Unique certification Id** field, define a number sequence.</span></span>

### <a name="set-up-a-revenue-typology-for-the-unique-certification"></a><span data-ttu-id="203cb-118">Impostare una tipologia di entrate per la certificazione unica</span><span class="sxs-lookup"><span data-stu-id="203cb-118">Set up a revenue typology for the Unique certification</span></span>

<span data-ttu-id="203cb-119">È necessario impostare una tipologia di entrate nel campo **Tipologia di entrate** nella sezione **Fattura e consegna** della pagina **Fornitori**.</span><span class="sxs-lookup"><span data-stu-id="203cb-119">You must set up a revenue typology in the **Revenue typology** field in the **Invoice and delivery** section of the **Vendors** page.</span></span>

<span data-ttu-id="203cb-120">È possibile importare l'elenco dei possibili valori di tipologia di entrate utilizzando l'entità **Impostazione valori certificazione unica** (UniqueCertificationValueEntity) e il framework di gestione dei dati.</span><span class="sxs-lookup"><span data-stu-id="203cb-120">You can import the list of possible revenue typology values by using the **Setup Unique certification values** (UniqueCertificationValueEntity) entity and the Data management framework.</span></span> <span data-ttu-id="203cb-121">Per ulteriori informazioni, vedere [Panoramica dei processi di importazione ed esportazione dei dati](../../dev-itpro/data-entities/data-import-export-job.md).</span><span class="sxs-lookup"><span data-stu-id="203cb-121">For more information, see [Data import and export jobs overview](../../dev-itpro/data-entities/data-import-export-job.md).</span></span>

<span data-ttu-id="203cb-122">I dati di origine utilizzati per importare i valori di tipologia di entrate possono essere presentati come file di Microsoft Excel con i seguenti nomi di colonna:</span><span class="sxs-lookup"><span data-stu-id="203cb-122">The source data that is used to import revenue typology values can be presented as a Microsoft Excel file that has the following column names:</span></span>

- <span data-ttu-id="203cb-123">FIELD</span><span class="sxs-lookup"><span data-stu-id="203cb-123">FIELD</span></span>
- <span data-ttu-id="203cb-124">VALUE</span><span class="sxs-lookup"><span data-stu-id="203cb-124">VALUE</span></span>
- <span data-ttu-id="203cb-125">ACTIVE</span><span class="sxs-lookup"><span data-stu-id="203cb-125">ACTIVE</span></span>
- <span data-ttu-id="203cb-126">VALUEDESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="203cb-126">VALUEDESCRIPTION</span></span>

<span data-ttu-id="203cb-127">È possibile modificare manualmente i valori di tipologia di entrate selezionando **Imposta**\> **Impostazione** \> **Ritenuta d'acconto** \> **Impostazione valori certificazione unica**.</span><span class="sxs-lookup"><span data-stu-id="203cb-127">You can manually edit revenue topology values by going to **Tax** \> **Setup** \> **Withholding tax** \> **Setup Unique certification values**.</span></span>

### <a name="set-up-a-format-for-the-unique-certification"></a><span data-ttu-id="203cb-128">Impostare un formato per la certificazione unica</span><span class="sxs-lookup"><span data-stu-id="203cb-128">Set up a format for the Unique certification</span></span>

1. <span data-ttu-id="203cb-129">Selezionare **Contabilità generale** \> **Impostazione contabilità generale** \> **Parametri di contabilità generale**.</span><span class="sxs-lookup"><span data-stu-id="203cb-129">Go to **General ledger** \> **Ledger setup** \> **General ledger parameters**.</span></span>
2. <span data-ttu-id="203cb-130">Nella scheda **Ritenuta d'acconto** nel campo **Mapping formato certificazione unica**, definire il formato ER da utilizzare per generare la certificazione unica.</span><span class="sxs-lookup"><span data-stu-id="203cb-130">On the **Withholding tax** tab, in the **Unique Certification format mapping** field, define the Electronic reporting (ER) format that should be used to generate the Unique certification.</span></span>

## <a name="generate-the-unique-certification"></a><span data-ttu-id="203cb-131">Generare la certificazione unica</span><span class="sxs-lookup"><span data-stu-id="203cb-131">Generate the Unique certification</span></span>

1. <span data-ttu-id="203cb-132">Selezionare **Imposta** \>**Dichiarazioni** \> **Ritenuta d'acconto** \> **Certificazione unica**.</span><span class="sxs-lookup"><span data-stu-id="203cb-132">Go to **Tax** \> **Declarations** \> **Withholding tax** \> **Unique Certification**.</span></span>
2. <span data-ttu-id="203cb-133">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="203cb-133">Select **New**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="203cb-134">L'anno precedente l'anno della data di sistema corrente viene automaticamente assegnato come anno di riferimento della dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="203cb-134">The year before the year of the current system date is automatically assigned as the reporting year of the declaration.</span></span>

3. <span data-ttu-id="203cb-135">Nella sezione **Titolo pagina**, immettere le informazioni sulla società e le informazioni sulla persona responsabile della trasmissione della certificazione unica all'agenzia delle entrate.</span><span class="sxs-lookup"><span data-stu-id="203cb-135">In the **Title-page** section, enter the company information and the information about the person who is in charge of communicating the Unique certification to the revenue agency.</span></span>
4. <span data-ttu-id="203cb-136">Selezionare **Genera** per creare le certificazioni per ogni destinatario e compilare automaticamente le altre sezioni.</span><span class="sxs-lookup"><span data-stu-id="203cb-136">Select **Generate** to create the certifications for each recipient and to automatically fill in the other sections.</span></span> <span data-ttu-id="203cb-137">La sezione **Fornitore** contiene l'elenco dei destinatari (fornitori) e i dettagli sui fornitori.</span><span class="sxs-lookup"><span data-stu-id="203cb-137">The **Vendor** section contains the list of recipients (vendors) and the vendor details.</span></span>
5. <span data-ttu-id="203cb-138">Selezionare **Generare dettagli** per immettere i dettagli delle transazioni dei fornitori nella dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="203cb-138">Select **Generate details** to enter the details of vendors transactions in the declaration.</span></span>
6. <span data-ttu-id="203cb-139">La sezione **Ritenuta d'acconto** mostra gli importi di ogni certificazione dei fornitori.</span><span class="sxs-lookup"><span data-stu-id="203cb-139">The **Withholding tax** section shows the amounts of each vendor certification.</span></span> <span data-ttu-id="203cb-140">Gli importi sono calcolati e ordinati per codice ritenuta d'acconto.</span><span class="sxs-lookup"><span data-stu-id="203cb-140">The amounts are calculated and sorted by withholding tax code.</span></span>

## <a name="process-the-unique-certification"></a><span data-ttu-id="203cb-141">Elaborare la certificazione unica</span><span class="sxs-lookup"><span data-stu-id="203cb-141">Process the Unique certification</span></span>

<span data-ttu-id="203cb-142">Dopo che la certificazione univoca è stata generata e riempita con i dati, è possibile selezionare **Convalida** per convalidare i dati prima che venga generato il file di output.</span><span class="sxs-lookup"><span data-stu-id="203cb-142">After the Unique certification is generated and filled with data, you can select **Validate** to validate the data before the output file is generated.</span></span> <span data-ttu-id="203cb-143">Dopo la convalida del file di output, selezionare **Esporta** per generare il file di output elettronico nel formato legalmente richiesto.</span><span class="sxs-lookup"><span data-stu-id="203cb-143">After the output file is validated, select **Export** to generate the electronic output file in the legally required format.</span></span>
