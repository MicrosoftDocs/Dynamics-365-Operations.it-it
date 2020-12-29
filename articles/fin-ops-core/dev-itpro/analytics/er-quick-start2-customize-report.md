---
title: Modificare un formato ER per generare un documento elettronico personalizzato
description: Questo argomento spiega come modificare un formato di report elettronico (ER) fornito da Microsoft in modo che generi un documento elettronico personalizzato.
author: NickSelin
manager: AnnBe
ms.date: 06/22/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERParameters, ERDataModelDesigner, ERModelMappingTable, ERModelMappingDesigner, EROperationDesigner, ERVendorTable
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 20e7a32ac5f6ab21f89ed3c11c64458286864c9d
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/05/2020
ms.locfileid: "4680172"
---
# <a name="adjust-an-er-format-to-generate-a-custom-electronic-document"></a><span data-ttu-id="11d42-103">Modificare un formato ER per generare un documento elettronico personalizzato</span><span class="sxs-lookup"><span data-stu-id="11d42-103">Adjust an ER format to generate a custom electronic document</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="11d42-104">Le procedure in questo argomento spiegano come un utente con il ruolo Amministratore di sistema o Consulente funzionale per la creazione di report elettronici può eseguire queste attività:</span><span class="sxs-lookup"><span data-stu-id="11d42-104">The procedures in this topic explain how a user in the System Administrator or Electronic Reporting Functional Consultant role can perform these tasks:</span></span>

- <span data-ttu-id="11d42-105">Configura i parametri per il [framework di report elettronico](general-electronic-reporting.md).</span><span class="sxs-lookup"><span data-stu-id="11d42-105">Configure parameters for the [Electronic reporting (ER) framework](general-electronic-reporting.md).</span></span>
- <span data-ttu-id="11d42-106">Importa le configurazioni di report elettronico fornite da Microsoft e utilizzate per generare un file di pagamento mentre un [pagamento del fornitore](../../../finance/cash-bank-management/tasks/vendor-payment-overview.md) è in fase di elaborazione.</span><span class="sxs-lookup"><span data-stu-id="11d42-106">Import ER configurations that are provided by Microsoft and used to generate a payment file while a [vendor payment](../../../finance/cash-bank-management/tasks/vendor-payment-overview.md) is being processed.</span></span>
- <span data-ttu-id="11d42-107">Crea una versione personalizzata di una configurazione di formato ER standard fornita da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="11d42-107">Create a custom version of a standard ER format configuration that is provided by Microsoft.</span></span>
- <span data-ttu-id="11d42-108">Modifica la configurazione del formato ER personalizzato in modo che generi file di pagamento che soddisfino i requisiti di una banca specifica.</span><span class="sxs-lookup"><span data-stu-id="11d42-108">Modify the custom ER format configuration so that it generates payment files that meets the requirements of a specific bank.</span></span>
- <span data-ttu-id="11d42-109">Adotta le modifiche apportate alla configurazione del formato ER standard nella configurazione del formato ER personalizzato.</span><span class="sxs-lookup"><span data-stu-id="11d42-109">Adopt changes that are made to the standard ER format configuration in the custom ER format configuration.</span></span>

<span data-ttu-id="11d42-110">Tutte le seguenti procedure possono essere eseguite nell'azienda **GBSI**.</span><span class="sxs-lookup"><span data-stu-id="11d42-110">All the following procedures can be done in the **GBSI** company.</span></span> <span data-ttu-id="11d42-111">Non è richiesta alcuna codifica.</span><span class="sxs-lookup"><span data-stu-id="11d42-111">No coding is required.</span></span>

- [<span data-ttu-id="11d42-112">Configurare il framework ER</span><span class="sxs-lookup"><span data-stu-id="11d42-112">Configure the ER framework</span></span>](#ConfigureFramework)

    - [<span data-ttu-id="11d42-113">Configurare i parametri ER</span><span class="sxs-lookup"><span data-stu-id="11d42-113">Configure ER parameters</span></span>](#ConfigureParameters)
    - [<span data-ttu-id="11d42-114">Attivare un provider di configurazioni ER</span><span class="sxs-lookup"><span data-stu-id="11d42-114">Activate an ER configuration provider</span></span>](#ActivateProvider)

        - [<span data-ttu-id="11d42-115">Rivedere l'elenco dei provider di configurazione ER</span><span class="sxs-lookup"><span data-stu-id="11d42-115">Review the list of ER configuration providers</span></span>](#ReviewProvidersList)
        - [<span data-ttu-id="11d42-116">Aggiungere un nuovo provider di configurazione ER</span><span class="sxs-lookup"><span data-stu-id="11d42-116">Add a new ER configuration provider</span></span>](#ActivateProvider)
        - [<span data-ttu-id="11d42-117">Attivare un provider di configurazioni ER</span><span class="sxs-lookup"><span data-stu-id="11d42-117">Activate an ER configuration provider</span></span>](#ActivateAddedProvider)

- [<span data-ttu-id="11d42-118">Importare le configurazioni del formato ER standard</span><span class="sxs-lookup"><span data-stu-id="11d42-118">Import the standard ER format configurations</span></span>](#ImportERSolution1)

    - [<span data-ttu-id="11d42-119">Importare le configurazioni ER standard</span><span class="sxs-lookup"><span data-stu-id="11d42-119">Import the standard ER configurations</span></span>](#ImportERFormat1)
    - [<span data-ttu-id="11d42-120">Rivedere le configurazioni ER importate</span><span class="sxs-lookup"><span data-stu-id="11d42-120">Review the imported ER configurations</span></span>](#ReviewImportedERSolution)

- [<span data-ttu-id="11d42-121">Preparare un pagamento fornitore per l'elaborazione</span><span class="sxs-lookup"><span data-stu-id="11d42-121">Prepare a vendor payment for processing</span></span>](#PrepareVendorPayment)

    - [<span data-ttu-id="11d42-122">Aggiungere le informazioni bancarie per un conto fornitore</span><span class="sxs-lookup"><span data-stu-id="11d42-122">Add bank information for a vendor account</span></span>](#AddBankAccount)
    - [<span data-ttu-id="11d42-123">Immettere un pagamento fornitore</span><span class="sxs-lookup"><span data-stu-id="11d42-123">Enter a vendor payment</span></span>](#EnterVendorPayment)

- [<span data-ttu-id="11d42-124">Elaborare un pagamento fornitore utilizzando il formato ER standard</span><span class="sxs-lookup"><span data-stu-id="11d42-124">Process a vendor payment by using the standard ER format</span></span>](#ProcessVendorPayment1)

    - [<span data-ttu-id="11d42-125">Configurare il metodo di pagamento elettronico</span><span class="sxs-lookup"><span data-stu-id="11d42-125">Set up the electronic payment method</span></span>](#ConfigureMethodOfPayment1)
    - [<span data-ttu-id="11d42-126">Elaborare un pagamento fornitore</span><span class="sxs-lookup"><span data-stu-id="11d42-126">Process a vendor payment</span></span>](#ProcessPayment1)

- [<span data-ttu-id="11d42-127">Personalizzare il formato ER standard</span><span class="sxs-lookup"><span data-stu-id="11d42-127">Customize the standard ER format</span></span>](#CustomizeProvidedFormat)

    - [<span data-ttu-id="11d42-128">Creare un formato personalizzato</span><span class="sxs-lookup"><span data-stu-id="11d42-128">Create a custom format</span></span>](#DeriveProvidedFormat)
    - [<span data-ttu-id="11d42-129">Modificare un formato personalizzato</span><span class="sxs-lookup"><span data-stu-id="11d42-129">Edit a custom format</span></span>](#ConfigureDerivedFormat)
    - [<span data-ttu-id="11d42-130">Contrassegnare un formato personalizzato come eseguibile</span><span class="sxs-lookup"><span data-stu-id="11d42-130">Mark a custom format as runnable</span></span>](#MarkFormatRunnable)

- [<span data-ttu-id="11d42-131">Elaborare un pagamento fornitore utilizzando il formato ER personalizzato</span><span class="sxs-lookup"><span data-stu-id="11d42-131">Process a vendor payment by using the custom ER format</span></span>](#ProcessVendorPayment2)

    - [<span data-ttu-id="11d42-132">Configurare il metodo di pagamento elettronico</span><span class="sxs-lookup"><span data-stu-id="11d42-132">Set up the electronic payment method</span></span>](#ConfigureMethodOfPayment2)
    - [<span data-ttu-id="11d42-133">Elaborare un pagamento fornitore</span><span class="sxs-lookup"><span data-stu-id="11d42-133">Process a vendor payment</span></span>](#ProcessPayment2)

- [<span data-ttu-id="11d42-134">Importare nuove versioni delle configurazioni del formato ER standard</span><span class="sxs-lookup"><span data-stu-id="11d42-134">Import new versions of the standard ER format configurations</span></span>](#ImportERSolution2)

    - [<span data-ttu-id="11d42-135">Importare nuove versioni delle configurazioni ER standard</span><span class="sxs-lookup"><span data-stu-id="11d42-135">Import new versions of the standard ER configurations</span></span>](#ImportERFormat2)
    - [<span data-ttu-id="11d42-136">Rivedere le configurazioni del formato ER importate</span><span class="sxs-lookup"><span data-stu-id="11d42-136">Review the imported ER format configurations</span></span>](#ReviewImportedERFormat)

- [<span data-ttu-id="11d42-137">Adottare le modifiche nella nuova versione di un formato importato in un formato personalizzato</span><span class="sxs-lookup"><span data-stu-id="11d42-137">Adopt the changes in the new version of an imported format in a custom format</span></span>](#AdoptNewBaseVersion)

    - [<span data-ttu-id="11d42-138">Completare la versione in bozza corrente di un formato personalizzato</span><span class="sxs-lookup"><span data-stu-id="11d42-138">Complete the current draft version of a custom format</span></span>](#CompleteDerivedFormat)
    - [<span data-ttu-id="11d42-139">Riassegnare un formato personalizzato su una nuova versione di base</span><span class="sxs-lookup"><span data-stu-id="11d42-139">Rebase a custom format to a new base version</span></span>](#RebaseDerivedFormat)
    - [<span data-ttu-id="11d42-140">Elaborare un pagamento fornitore utilizzando un formato ER riassegnato</span><span class="sxs-lookup"><span data-stu-id="11d42-140">Process a vendor payment by using a rebased ER format</span></span>](#ProcessPayment3)

- [<span data-ttu-id="11d42-141">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="11d42-141">Additional resources</span></span>](#References)

## <a name="configure-the-er-framework"></a><a id="ConfigureFramework"></a><span data-ttu-id="11d42-142">Configurare il framework ER</span><span class="sxs-lookup"><span data-stu-id="11d42-142">Configure the ER framework</span></span>

<span data-ttu-id="11d42-143">Come utente che dispone del ruolo di Consulente funzionale per la creazione di report elettronici, è necessario configurare il set minimo di parametri ER prima di poter iniziare a utilizzare il framework ER per progettare una versione personalizzata di un formato ER standard.</span><span class="sxs-lookup"><span data-stu-id="11d42-143">As a user in the Electronic Reporting Functional Consultant role, you must configure the minimal set of ER parameters before you can start to use the ER framework to design a custom version of a standard ER format.</span></span>

### <a name="configure-er-parameters"></a><a id="ConfigureParameters"></a><span data-ttu-id="11d42-144">Configurare i parametri ER</span><span class="sxs-lookup"><span data-stu-id="11d42-144">Configure ER parameters</span></span>

1. <span data-ttu-id="11d42-145">Andare a **Amministrazione organizzazione** \> **Aree di lavoro** \> **Creazione di report elettronici**.</span><span class="sxs-lookup"><span data-stu-id="11d42-145">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
2. <span data-ttu-id="11d42-146">Nella pagina **Configurazioni localizzazione**, nella sezione **Collegamenti correlati**, seleziona **Parametri per la creazione di report elettronici**.</span><span class="sxs-lookup"><span data-stu-id="11d42-146">On the **Localization configurations** page, in the **Related links** section, select **Electronic reporting parameters**.</span></span>
3. <span data-ttu-id="11d42-147">Nella pagina **Parametri per la creazione di report elettronici**, nella scheda **Generale**, imposta l'opzione **Abilita integrazione fiscale** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="11d42-147">On the **Electronic reporting parameters** page, on the **General** tab, set the **Enable design mode** option to **Yes**.</span></span>
4. <span data-ttu-id="11d42-148">Nella scheda **Allegati**, imposta i seguenti parametri:</span><span class="sxs-lookup"><span data-stu-id="11d42-148">On the **Attachments** tab, set the following parameters:</span></span>

    - <span data-ttu-id="11d42-149">Nel campo **Configurazioni**, seleziona il tipo **File** per l'azienda **USMF**.</span><span class="sxs-lookup"><span data-stu-id="11d42-149">In the **Configurations** field, select the **File** type for the **USMF** company.</span></span>
    - <span data-ttu-id="11d42-150">Nei campi **Archivio processi**, **Temporaneo**, **Base** e **Altri**, seleziona il tipo **File**.</span><span class="sxs-lookup"><span data-stu-id="11d42-150">In the **Job archive**, **Temporary**, **Baseline**, and **Others** fields, select the **File** type.</span></span>

<span data-ttu-id="11d42-151">Per ulteriori informazioni sui parametri ER, vedi [Configurare il framework ER](electronic-reporting-er-configure-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="11d42-151">For more information about ER parameters, see [Configure the ER framework](electronic-reporting-er-configure-parameters.md).</span></span>

### <a name="activate-an-er-configuration-provider"></a><a id="ActivateProvider"></a><span data-ttu-id="11d42-152">Attivare un provider di configurazioni ER</span><span class="sxs-lookup"><span data-stu-id="11d42-152">Activate an ER configuration provider</span></span>

<span data-ttu-id="11d42-153">Ogni configurazione ER aggiunta viene contrassegnata come di proprietà di un provider di configurazione ER.</span><span class="sxs-lookup"><span data-stu-id="11d42-153">Every ER configuration that is added is marked as owned by an ER configuration provider.</span></span> <span data-ttu-id="11d42-154">Il provider di configurazione ER che è attivato nell'area di lavoro **Creazione di report elettronici** viene utilizzato per questo scopo.</span><span class="sxs-lookup"><span data-stu-id="11d42-154">The ER configuration provider that is activated in the **Electronic reporting** workspace is used for this purpose.</span></span> <span data-ttu-id="11d42-155">Pertanto, è necessario attivare un provider di configurazione ER nell'area di lavoro **Creazione di report elettronici** prima di iniziare ad aggiungere o modificare le configurazioni ER.</span><span class="sxs-lookup"><span data-stu-id="11d42-155">Therefore, you must activate an ER configuration provider in the **Electronic reporting** workspace before you start to add or edit ER configurations.</span></span>

> [!NOTE]
> <span data-ttu-id="11d42-156">Solo il proprietario di una configurazione ER può modificarla.</span><span class="sxs-lookup"><span data-stu-id="11d42-156">Only the owner of an ER configuration can edit it.</span></span> <span data-ttu-id="11d42-157">Pertanto, prima di poter modificare una configurazione ER, è necessario attivare il provider di configurazione ER appropriato nell'area di lavoro **Creazione di report elettronici**.</span><span class="sxs-lookup"><span data-stu-id="11d42-157">Therefore, before an ER configuration can be edited, the appropriate ER configuration provider must be activated in the **Electronic reporting** workspace.</span></span>

#### <a name="review-the-list-of-er-configuration-providers"></a><a id="ReviewProvidersList"></a><span data-ttu-id="11d42-158">Rivedere l'elenco dei provider di configurazione ER</span><span class="sxs-lookup"><span data-stu-id="11d42-158">Review the list of ER configuration providers</span></span>

1. <span data-ttu-id="11d42-159">Andare a **Amministrazione organizzazione** \> **Aree di lavoro** \> **Creazione di report elettronici**.</span><span class="sxs-lookup"><span data-stu-id="11d42-159">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
2. <span data-ttu-id="11d42-160">Nella pagina **Configurazioni localizzazione**, nella sezione **Collegamenti correlati**, seleziona **Provider di configurazione**.</span><span class="sxs-lookup"><span data-stu-id="11d42-160">On the **Localization configurations** page, in the **Related links** section, select **Configuration providers**.</span></span>
3. <span data-ttu-id="11d42-161">Nella pagina **Tabella del provider di configurazione**, ogni record del provider ha un nome e un URL univoci.</span><span class="sxs-lookup"><span data-stu-id="11d42-161">On the **Configuration provider table** page, each provider record has a unique name and URL.</span></span> <span data-ttu-id="11d42-162">Rivedi il contenuto della pagina.</span><span class="sxs-lookup"><span data-stu-id="11d42-162">Review the contents of this page.</span></span> <span data-ttu-id="11d42-163">Se un record per **Litware, Inc.** (`https://www.litware.com`) esiste già, salta la procedura successiva, [Aggiungere un nuovo provider di configurazione ER](#ActivateProvider).</span><span class="sxs-lookup"><span data-stu-id="11d42-163">If a record for **Litware, Inc.** (`https://www.litware.com`) already exists, skip the next procedure, [Add a new ER configuration provider](#ActivateProvider).</span></span>

#### <a name="add-a-new-er-configuration-provider"></a><a id="ActivateProvider"></a><span data-ttu-id="11d42-164">Aggiungere un nuovo provider di configurazione ER</span><span class="sxs-lookup"><span data-stu-id="11d42-164">Add a new ER configuration provider</span></span>

1. <span data-ttu-id="11d42-165">Andare a **Amministrazione organizzazione** \> **Aree di lavoro** \> **Creazione di report elettronici**.</span><span class="sxs-lookup"><span data-stu-id="11d42-165">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
2. <span data-ttu-id="11d42-166">Nella pagina **Configurazioni localizzazione**, nella sezione **Collegamenti correlati**, seleziona **Provider di configurazione**.</span><span class="sxs-lookup"><span data-stu-id="11d42-166">On the **Localization configurations** page, in the **Related links** section, select **Configuration providers**.</span></span>
3. <span data-ttu-id="11d42-167">Nella pagina **Provider di configurazione**, seleziona **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="11d42-167">On the **Configuration providers** page, select **New**.</span></span>
4. <span data-ttu-id="11d42-168">Nel campo **Nome**, immetti **Litware, Inc.**</span><span class="sxs-lookup"><span data-stu-id="11d42-168">In the **Name** field, enter **Litware, Inc.**</span></span>
5. <span data-ttu-id="11d42-169">Nel campo **Indirizzo Internet** immetti `https://www.litware.com`.</span><span class="sxs-lookup"><span data-stu-id="11d42-169">In the **Internet address** field, enter `https://www.litware.com`.</span></span>
6. <span data-ttu-id="11d42-170">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="11d42-170">Select **Save**.</span></span>

#### <a name="activate-an-er-configuration-provider"></a><a id="ActivateAddedProvider"></a><span data-ttu-id="11d42-171">Attivare un provider di configurazioni ER</span><span class="sxs-lookup"><span data-stu-id="11d42-171">Activate an ER configuration provider</span></span>

1. <span data-ttu-id="11d42-172">Andare a **Amministrazione organizzazione** \> **Aree di lavoro** \> **Creazione di report elettronici**.</span><span class="sxs-lookup"><span data-stu-id="11d42-172">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
2. <span data-ttu-id="11d42-173">Nella pagina **Configurazioni localizzazione**, nella sezione **Provider di configurazione**, seleziona il riquadro **Litware, Inc.**, quindi seleziona **Imposta attivo**.</span><span class="sxs-lookup"><span data-stu-id="11d42-173">On the **Localization configurations** page, in the **Configuration providers** section, select the **Litware, Inc.** tile, and then select **Set active**.</span></span>

<span data-ttu-id="11d42-174">Per ulteriori informazioni sui provider di configurazione ER, vedi [Creare provider di configurazioni e contrassegnarli come attivi](tasks/er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="11d42-174">For more information about ER configuration providers, see [Create configuration providers and mark them as active](tasks/er-configuration-provider-mark-it-active-2016-11.md).</span></span>

## <a name="import-the-standard-er-format-configurations"></a><a id="ImportERSolution1"></a><span data-ttu-id="11d42-175">Importare le configurazioni del formato ER standard</span><span class="sxs-lookup"><span data-stu-id="11d42-175">Import the standard ER format configurations</span></span>

### <a name="import-the-standard-er-configurations"></a><a id="ImportERFormat1"></a><span data-ttu-id="11d42-176">Importare le configurazioni ER standard</span><span class="sxs-lookup"><span data-stu-id="11d42-176">Import the standard ER configurations</span></span>

<span data-ttu-id="11d42-177">Per aggiungere le configurazioni ER standard all'istanza corrente di Microsoft Dynamics 365 Finance, è necessario importarle dall'[archivio](general-electronic-reporting.md#Repository) ER che era configurato per quell'istanza.</span><span class="sxs-lookup"><span data-stu-id="11d42-177">To add the standard ER configurations to your current instance of Microsoft Dynamics 365 Finance, you must import them from the ER [repository](general-electronic-reporting.md#Repository) that was configured for that instance.</span></span>

1. <span data-ttu-id="11d42-178">Andare a **Amministrazione organizzazione** \> **Aree di lavoro** \> **Creazione di report elettronici**.</span><span class="sxs-lookup"><span data-stu-id="11d42-178">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
2. <span data-ttu-id="11d42-179">Nella pagina **Configurazioni localizzazione**, nella sezione **Provider di configurazione**, seleziona il riquadro **Microsoft**, quindi seleziona **Archivi** per visualizzare l'elenco dei repository per il provider Microsoft.</span><span class="sxs-lookup"><span data-stu-id="11d42-179">On the **Localization configurations** page, in the **Configuration providers** section, select the **Microsoft** tile, and then select **Repositories** to view the list of repositories for the Microsoft provider.</span></span>
3. <span data-ttu-id="11d42-180">Nella pagina **Archivi di configurazione** seleziona l'archivio del tipo **Globale**, quindi seleziona **Apri**.</span><span class="sxs-lookup"><span data-stu-id="11d42-180">On the **Configuration repositories** page, select the repository of the **Global** type, and then select **Open**.</span></span> <span data-ttu-id="11d42-181">Se viene richiesta l'autorizzazione per connettersi a Regulatory Configuration Service, segui le istruzioni di autorizzazione.</span><span class="sxs-lookup"><span data-stu-id="11d42-181">If you're prompted for authorization to connect to Regulatory Configuration Service, follow the authorization instructions.</span></span>
4. <span data-ttu-id="11d42-182">Nella pagina **Archivio di configurazioni**, nella struttura delle configurazioni del riquadro sinistro, seleziona la configurazione del formato **BACS (Regno Unito)**.</span><span class="sxs-lookup"><span data-stu-id="11d42-182">On the **Configuration repository** page, in the configuration tree in the left pane, select the **BACS (UK)** format configuration.</span></span>
5. <span data-ttu-id="11d42-183">Nella scheda dettaglio **Versioni** seleziona la versione **1.1** della configurazione del formato ER selezionata.</span><span class="sxs-lookup"><span data-stu-id="11d42-183">On the **Versions** FastTab, select version **1.1** of the selected ER format configuration.</span></span>
6. <span data-ttu-id="11d42-184">Seleziona **Importa** per scaricare la versione selezionata dall'archivio Globale nell'istanza corrente di Finance.</span><span class="sxs-lookup"><span data-stu-id="11d42-184">Select **Import** to download the selected version from the Global repository to the current Finance instance.</span></span>

![Configurazione della pagina dell'archivio](./media/er-quick-start2-import-solution1.png)

> [!TIP]
> <span data-ttu-id="11d42-186">In caso di problemi di accesso all'[archivio globale](er-download-configurations-global-repo.md), puoi invece [scaricare le configurazioni](download-electronic-reporting-configuration-lcs.md) da Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="11d42-186">If you have trouble accessing the [Global repository](er-download-configurations-global-repo.md), you can [download configurations](download-electronic-reporting-configuration-lcs.md) from Microsoft Dynamics Lifecycle Services (LCS) instead.</span></span>

### <a name="review-the-imported-er-configurations"></a><a id="ReviewImportedERSolution"></a><span data-ttu-id="11d42-187">Rivedere le configurazioni ER importate</span><span class="sxs-lookup"><span data-stu-id="11d42-187">Review the imported ER configurations</span></span>

1. <span data-ttu-id="11d42-188">Andare a **Amministrazione organizzazione** \> **Aree di lavoro** \> **Creazione di report elettronici**.</span><span class="sxs-lookup"><span data-stu-id="11d42-188">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
2. <span data-ttu-id="11d42-189">Nella pagina **Configurazioni localizzazione**, nella sezione **Configurazioni**, selezionare il riquadro **Configurazioni report**.</span><span class="sxs-lookup"><span data-stu-id="11d42-189">On the **Localization configurations** page, in the **Configurations** section, select the **Reporting configurations** tile.</span></span>
3. <span data-ttu-id="11d42-190">Nella pagina **Configurazioni**, nella struttura delle configurazioni del riquadro sinistro, espandi **Modello di pagamento**.</span><span class="sxs-lookup"><span data-stu-id="11d42-190">On the **Configurations** page, in the configuration tree in the left pane, expand **Payment model**.</span></span>
4. <span data-ttu-id="11d42-191">Si noti che, oltre al formato ER **BACS (Regno Unito)** selezionato, sono state importate altre configurazioni ER necessarie.</span><span class="sxs-lookup"><span data-stu-id="11d42-191">Notice that, in addition to the selected **BACS (UK)** ER format, other required ER configurations were imported.</span></span> <span data-ttu-id="11d42-192">Verifica che le seguenti configurazioni ER siano disponibili nella struttura di configurazione:</span><span class="sxs-lookup"><span data-stu-id="11d42-192">Make sure that the following ER configurations are available in the configuration tree:</span></span>

    - <span data-ttu-id="11d42-193">**Modello di pagamento**: questa configurazione contiene il componente ER [modello di dati](general-electronic-reporting.md#data-model-and-model-mapping-components) che rappresenta la struttura dei dati del dominio aziendale di pagamento.</span><span class="sxs-lookup"><span data-stu-id="11d42-193">**Payment model** – This configuration contains the [data model](general-electronic-reporting.md#data-model-and-model-mapping-components) ER component that represents the data structure of the payment business domain.</span></span>
    - <span data-ttu-id="11d42-194">**Mapping di modello di pagamento 1611**: questa configurazione contiene il componente ER [mapping del modello](general-electronic-reporting.md#data-model-and-model-mapping-components) che descrive in che modo il modello di dati viene compilato con i dati dell'applicazione in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="11d42-194">**Payment model mapping 1611** – This configuration contains the [model mapping](general-electronic-reporting.md#data-model-and-model-mapping-components) ER component that describes how the data model is filled in with application data at runtime.</span></span>
    - <span data-ttu-id="11d42-195">**BACS (Regno Unito)**: questa configurazione contiene i componenti ER [formato](general-electronic-reporting.md#FormatComponentOutbound) e mapping del formato.</span><span class="sxs-lookup"><span data-stu-id="11d42-195">**BACS (UK)** – This configuration contains the [format](general-electronic-reporting.md#FormatComponentOutbound) and format mapping ER components.</span></span> <span data-ttu-id="11d42-196">Il componente di formato specifica il layout del report.</span><span class="sxs-lookup"><span data-stu-id="11d42-196">The format component specifies the report layout.</span></span> <span data-ttu-id="11d42-197">Il componente di mapping del formato contiene l'origine dati del modello e specifica come viene compilato il layout del report utilizzando questa origine dati in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="11d42-197">The format mapping component contains the model data source and specifies how the report layout is filled in by using this data source at runtime.</span></span>

![Pagina Configurazioni](./media/er-quick-start2-imported-solution1.png)

## <a name="prepare-a-vendor-payment-for-processing"></a><a id="PrepareVendorPayment"></a><span data-ttu-id="11d42-199">Preparare un pagamento fornitore per l'elaborazione</span><span class="sxs-lookup"><span data-stu-id="11d42-199">Prepare a vendor payment for processing</span></span>

### <a name="add-bank-information-for-a-vendor-account"></a><a id="AddBankAccount"></a><span data-ttu-id="11d42-200">Aggiungere le informazioni bancarie per un conto fornitore</span><span class="sxs-lookup"><span data-stu-id="11d42-200">Add bank information for a vendor account</span></span>

<span data-ttu-id="11d42-201">È necessario aggiungere le informazioni bancarie per un conto fornitore a cui si farà riferimento in seguito in un pagamento registrato.</span><span class="sxs-lookup"><span data-stu-id="11d42-201">You must add bank information for a vendor account that will be referred to later in a registered payment.</span></span>

1. <span data-ttu-id="11d42-202">Andare a **Contabilità fornitori** \> **Fornitori** \> **Tutti i fornitori**.</span><span class="sxs-lookup"><span data-stu-id="11d42-202">Go to **Accounts payable** \> **Vendors** \> **All vendors**.</span></span>
2. <span data-ttu-id="11d42-203">Nella pagina **Tutti i fornitori**, seleziona il conto fornitore **GB_SI_000001**, quindi, nel riquadro Azioni, nella scheda **Fornitore** del gruppo **Imposta**, seleziona **Conti bancari**.</span><span class="sxs-lookup"><span data-stu-id="11d42-203">On the **All vendors** page, select the **GB_SI_000001** vendor account, and then, on the Action Pane, on the **Vendor** tab, in the **Set up** group, select **Bank accounts**.</span></span>
3. <span data-ttu-id="11d42-204">Nella pagina **Conti bancari fornitore**, seleziona **Nuovo**, quindi immetti le seguenti informazioni:</span><span class="sxs-lookup"><span data-stu-id="11d42-204">On the **Vendor bank accounts** page, select **New**, and then enter the following information:</span></span>

    1. <span data-ttu-id="11d42-205">Nel campo **Conto bancario** immetti **GBP OPER**.</span><span class="sxs-lookup"><span data-stu-id="11d42-205">In the **Bank account** field, enter **GBP OPER**.</span></span>
    2. <span data-ttu-id="11d42-206">Nel campo **Gruppi bancari**, seleziona **BankGBP**.</span><span class="sxs-lookup"><span data-stu-id="11d42-206">In the **Bank groups** field, select **BankGBP**.</span></span>
    3. <span data-ttu-id="11d42-207">Nel campo **Numero conto bancario**, immetti **202015**.</span><span class="sxs-lookup"><span data-stu-id="11d42-207">In the **Bank account number** field, enter **202015**.</span></span>
    4. <span data-ttu-id="11d42-208">Nel campo **Codice SWIFT**, immetti <a id="DefineSWIFTCode"></a>**CHASDEFXXXX**.</span><span class="sxs-lookup"><span data-stu-id="11d42-208">In the **SWIFT code** field, enter <a id="DefineSWIFTCode"></a>**CHASDEFXXXX**.</span></span>
    5. <span data-ttu-id="11d42-209">Nel campo **IBAN**, immetti **GB33BUKB20201555555555**.</span><span class="sxs-lookup"><span data-stu-id="11d42-209">In the **IBAN** field, enter **GB33BUKB20201555555555**.</span></span>
    6. <span data-ttu-id="11d42-210">Nel campo **Numero di registrazione**, mantieni il valore predefinito, <a id="DefineRoutingNumber"></a>**123456**.</span><span class="sxs-lookup"><span data-stu-id="11d42-210">In the **Routing number** field, keep the default value, <a id="DefineRoutingNumber"></a>**123456**.</span></span>

    ![Pagina Conti bancari fornitore](./media/er-quick-start2-bank-account.png)

4. <span data-ttu-id="11d42-212">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="11d42-212">Select **Save**.</span></span>
5. <span data-ttu-id="11d42-213">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="11d42-213">Close the page.</span></span>
6. <span data-ttu-id="11d42-214">Nella pagina **Tutti i fornitori**, apri il conto fornitore **GB_SI_000001**.</span><span class="sxs-lookup"><span data-stu-id="11d42-214">On the **All vendors** page, open the **GB_SI_000001** vendor account.</span></span>
7. <span data-ttu-id="11d42-215">Nella pagina dei dettagli del fornitore, seleziona **Modifica** per rendere modificabile la pagina, se necessario.</span><span class="sxs-lookup"><span data-stu-id="11d42-215">On the vendor details page, select **Edit** to make the page editable, if required.</span></span>
8. <span data-ttu-id="11d42-216">Nella scheda dettaglio **Pagamento**, nel campo **Conto bancario**, seleziona **GBP OPER**.</span><span class="sxs-lookup"><span data-stu-id="11d42-216">On the **Payment** FastTab, in the **Bank account** field, select **GBP OPER**.</span></span>

    ![Pagina Dettagli fornitore](./media/er-quick-start2-bank-account-reference.png)

9. <span data-ttu-id="11d42-218">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="11d42-218">Select **Save**.</span></span>
10. <span data-ttu-id="11d42-219">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="11d42-219">Close the page.</span></span>

### <a name="enter-a-vendor-payment"></a><a id="EnterVendorPayment"></a><span data-ttu-id="11d42-220">Immettere un pagamento fornitore</span><span class="sxs-lookup"><span data-stu-id="11d42-220">Enter a vendor payment</span></span>

<span data-ttu-id="11d42-221">È necessario immettere un nuovo pagamento fornitore utilizzando una [proposta di pagamento](https://docs.microsoft.com/dynamics365/finance/accounts-payable/create-vendor-payments-payment-proposal).</span><span class="sxs-lookup"><span data-stu-id="11d42-221">You must enter a new vendor payment by using a [payment proposal](https://docs.microsoft.com/dynamics365/finance/accounts-payable/create-vendor-payments-payment-proposal).</span></span>

1. <span data-ttu-id="11d42-222">Andare a **Contabilità fornitori** \> **Pagamenti** \> **Giornale di registrazione pagamenti fornitore**.</span><span class="sxs-lookup"><span data-stu-id="11d42-222">Go to **Accounts payable** \> **Payments** \> **Vendor payment journal**.</span></span>
2. <span data-ttu-id="11d42-223">Nella pagina **Giornale di registrazione pagamenti fornitore**, seleziona **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="11d42-223">On the **Vendor payment journal** page, select **New**.</span></span>
3. <span data-ttu-id="11d42-224">Nel campo **Nome**, seleziona **VendPay**.</span><span class="sxs-lookup"><span data-stu-id="11d42-224">In the **Name** field, select **VendPay**.</span></span>
4. <span data-ttu-id="11d42-225">Selezionare **Righe**.</span><span class="sxs-lookup"><span data-stu-id="11d42-225">Select **Lines**.</span></span>
5. <span data-ttu-id="11d42-226">Seleziona **Proposta di pagamento** \> **Crea proposta di pagamento**.</span><span class="sxs-lookup"><span data-stu-id="11d42-226">Select **Payment proposal** \> **Create payment proposal**.</span></span>
6. <span data-ttu-id="11d42-227">Nella finestra di dialogo **Proposta di pagamento fornitore**, configura le condizioni per filtrare i record per il conto fornitore **GB_SI_000001**, quindi seleziona **OK**.</span><span class="sxs-lookup"><span data-stu-id="11d42-227">In the **Vendor payment proposal** dialog box, configure conditions to filter for records for the **GB_SI_000001** vendor account only, and then select **OK**.</span></span>
7. <span data-ttu-id="11d42-228">Seleziona la riga per la fattura **00000007_Inv**, quindi seleziona **Crea pagamento**.</span><span class="sxs-lookup"><span data-stu-id="11d42-228">Select the line for the **00000007_Inv** invoice, and then select **Create payment**.</span></span>

    ![Finestra di dialogo Proposta di pagamento fornitore](./media/er-quick-start2-payment-proposal.png)

8. <span data-ttu-id="11d42-230">Verifica che il pagamento immesso sia configurato per l'utilizzo del metodo di pagamento **Elettronico**.</span><span class="sxs-lookup"><span data-stu-id="11d42-230">Verify that the payment that is entered is configured to use the **Electronic** method of payment.</span></span>

    ![Pagina Pagamenti fornitore](./media/er-quick-start2-payment-line.png)

## <a name="process-a-vendor-payment-by-using-the-standard-er-format"></a><a id="ProcessVendorPayment1"></a><span data-ttu-id="11d42-232">Elaborare un pagamento fornitore utilizzando il formato ER standard</span><span class="sxs-lookup"><span data-stu-id="11d42-232">Process a vendor payment by using the standard ER format</span></span>

### <a name="set-up-the-electronic-payment-method"></a><a id="ConfigureMethodOfPayment1"></a><span data-ttu-id="11d42-233">Configurare il metodo di pagamento elettronico</span><span class="sxs-lookup"><span data-stu-id="11d42-233">Set up the electronic payment method</span></span>

<span data-ttu-id="11d42-234">È necessario configurare il metodo di pagamento elettronico in modo che utilizzi la configurazione del formato ER importato.</span><span class="sxs-lookup"><span data-stu-id="11d42-234">You must configure the electronic method of payment so that it uses the imported ER format configuration.</span></span>

1. <span data-ttu-id="11d42-235">Andare a **Contabilità fornitori** \> **Impostazione pagamenti** \> **Metodi di pagamento**.</span><span class="sxs-lookup"><span data-stu-id="11d42-235">Go to **Accounts payable** \> **Payment setup** \> **Methods of payment**.</span></span>
2. <span data-ttu-id="11d42-236">Nella pagina **Metodi di pagamento - Fornitori**, seleziona il metodo di pagamento **Elettronico** nel riquadro a sinistra.</span><span class="sxs-lookup"><span data-stu-id="11d42-236">On the **Methods of payment - vendors** page, select the **Electronic** method of payment in the left pane.</span></span>
3. <span data-ttu-id="11d42-237">Selezionare **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="11d42-237">Select **Edit**.</span></span>
4. <span data-ttu-id="11d42-238">Nella scheda dettaglio **Formati file**, imposta l'opzione **Formato esportazione elettronica generica** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="11d42-238">On the **File formats** FastTab, set the **General electronic Export format** option to **Yes**.</span></span>
5. <span data-ttu-id="11d42-239">Nel campo **Esporta configurazione formato** seleziona la configurazione del formato **BACS (Regno Unito)**.</span><span class="sxs-lookup"><span data-stu-id="11d42-239">In the **Export format configuration** field, select the **BACS (UK)** format configuration.</span></span>

    ![Pagina Metodi di pagamento - Fornitori](./media/er-quick-start2-method-of-payment1.png)

6. <span data-ttu-id="11d42-241">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="11d42-241">Select **Save**.</span></span>

### <a name="process-a-vendor-payment"></a><a id="ProcessPayment1"></a><span data-ttu-id="11d42-242">Elaborare un pagamento fornitore</span><span class="sxs-lookup"><span data-stu-id="11d42-242">Process a vendor payment</span></span>

1. <span data-ttu-id="11d42-243">Andare a **Contabilità fornitori** \> **Pagamenti** \> **Giornale di registrazione pagamenti fornitore**.</span><span class="sxs-lookup"><span data-stu-id="11d42-243">Go to **Accounts payable** \> **Payments** \> **Vendor payment journal**.</span></span>
2. <span data-ttu-id="11d42-244">Nella pagina **Giornale di registrazione pagamenti fornitore** selezionare il giornale di registrazione pagamenti aggiunti in precedenza, quindi selezionare **Righe**.</span><span class="sxs-lookup"><span data-stu-id="11d42-244">On the **Vendor payment journal** page, select the payment journal that you added earlier, and then select **Lines**.</span></span>
3. <span data-ttu-id="11d42-245">Nella pagina **Pagamenti fornitore**, seleziona **Genera pagamenti**.</span><span class="sxs-lookup"><span data-stu-id="11d42-245">On the **Vendor payments** page, select **Generate payments**.</span></span>
4. <span data-ttu-id="11d42-246">Nella finestra di dialogo **Genera pagamenti** immetti le seguenti informazioni:</span><span class="sxs-lookup"><span data-stu-id="11d42-246">In the **Generate payments** dialog box, enter the following information:</span></span>

    - <span data-ttu-id="11d42-247">Nel campo **Metodo di pagamento** seleziona **Elettronico**.</span><span class="sxs-lookup"><span data-stu-id="11d42-247">In the **Method of payment** field, select **Electronic**.</span></span>
    - <span data-ttu-id="11d42-248">Nel campo **Conto bancario** selezionare **GBSI OPER**.</span><span class="sxs-lookup"><span data-stu-id="11d42-248">In the **Bank account** field, select **GBSI OPER**.</span></span>

5. <span data-ttu-id="11d42-249">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="11d42-249">Select **OK**.</span></span>
6. <span data-ttu-id="11d42-250">Nella finestra di dialogo **Parametri per la creazione di report elettronici**, imposta l'opzione **Stampa report di controllo** su **Sì**, quindi seleziona **OK**.</span><span class="sxs-lookup"><span data-stu-id="11d42-250">In the **Electronic report parameters** dialog box, set the **Print control report** option to **Yes**, and then select **OK**.</span></span>

    ![Pagina Parametri per la creazione di report elettronici](./media/er-quick-start2-payment-dialog1.png)

    > [!NOTE]
    > <span data-ttu-id="11d42-252">Oltre al file di pagamento, è ora possibile generare il report di controllo.</span><span class="sxs-lookup"><span data-stu-id="11d42-252">In addition to the payment file, you can now generate the control report.</span></span>

7. <span data-ttu-id="11d42-253">Scarica il file zip, quindi estrai i seguenti file:</span><span class="sxs-lookup"><span data-stu-id="11d42-253">Download the zip file, and then extract the following files from it:</span></span>

    - <span data-ttu-id="11d42-254">Il report di controllo in formato Excel</span><span class="sxs-lookup"><span data-stu-id="11d42-254">The control report in Excel format</span></span>
    - <span data-ttu-id="11d42-255">Il file di pagamento in formato TXT</span><span class="sxs-lookup"><span data-stu-id="11d42-255">The payment file in TXT format</span></span>

        <span data-ttu-id="11d42-256">Si noti che, in conformità con la [struttura](#PositionRoutingNumber) del formato ER fornito, la riga di pagamento nel file generato inizia con il numero di registrazione che era [definito](#DefineRoutingNumber)per il conto bancario configurato.</span><span class="sxs-lookup"><span data-stu-id="11d42-256">Notice that, in accordance with the [structure](#PositionRoutingNumber) of the provided ER format, the payment line in the generated file starts with the routing number that was [defined](#DefineRoutingNumber) for the configured bank account.</span></span>

        ![File di pagamento in formato TXT](./media/er-quick-start2-payment-file1.png)

## <a name="customize-the-standard-er-format"></a><a id="CustomizeProvidedFormat"></a><span data-ttu-id="11d42-258">Personalizzare il formato ER standard</span><span class="sxs-lookup"><span data-stu-id="11d42-258">Customize the standard ER format</span></span>

<span data-ttu-id="11d42-259">Nell'esempio mostrato in questa sezione, vuoi utilizzare le configurazioni ER fornite da Microsoft per generare file di pagamento del fornitore in formato BACS, ma è necessario aggiungere una personalizzazione per supportare i requisiti di una banca specifica.</span><span class="sxs-lookup"><span data-stu-id="11d42-259">For the example that is shown in this section, you want to use the ER configurations that are provided by Microsoft to generate vendor payment files in BACS format, but you must add a customization to support the requirements of a specific bank.</span></span> <span data-ttu-id="11d42-260">Vuoi anche essere in grado di aggiornare il tuo formato personalizzato quando saranno disponibili nuove versioni delle configurazioni ER.</span><span class="sxs-lookup"><span data-stu-id="11d42-260">You also want to be able to upgrade your custom format when new versions of ER configurations become available.</span></span> <span data-ttu-id="11d42-261">Tuttavia, desideri anche poter eseguire l'aggiornamento al minor costo.</span><span class="sxs-lookup"><span data-stu-id="11d42-261">However, you want to be able to do the upgrade at the lowest cost.</span></span>

<span data-ttu-id="11d42-262">In questo caso, in qualità di rappresentante di Litware, Inc., devi creare (derivare) una nuova configurazione del formato ER utilizzando la configurazione **BACS (Regno Unito)** fornita da Microsoft come base.</span><span class="sxs-lookup"><span data-stu-id="11d42-262">In this case, as the representative of Litware, Inc., you must create (derive) a new ER format configuration by using the **BACS (UK)** Microsoft-provided configuration as a base.</span></span>

### <a name="create-a-custom-format"></a><a id="DeriveProvidedFormat"></a><span data-ttu-id="11d42-263">Creare un formato personalizzato</span><span class="sxs-lookup"><span data-stu-id="11d42-263">Create a custom format</span></span>

1. <span data-ttu-id="11d42-264">Andare a **Amministrazione organizzazione** \> **Creazione di report elettronici** \> **Configurazioni**.</span><span class="sxs-lookup"><span data-stu-id="11d42-264">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="11d42-265">Nella pagina **Configurazioni**, nella struttura delle configurazioni del riquadro sinistro, espandi **Modello di pagamento**, quindi seleziona **BACS (Regno Unito)**.</span><span class="sxs-lookup"><span data-stu-id="11d42-265">On the **Configurations** page, in the configuration tree in the left pane, expand **Payment model**, and then select **BACS (UK)**.</span></span> <span data-ttu-id="11d42-266">Litware, Inc. utilizzerà la versione 1.1 di questa configurazione del formato ER come base per la versione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="11d42-266">Litware, Inc. will use version 1.1 of this ER format configuration as the base for the custom version.</span></span>
3. <span data-ttu-id="11d42-267">Seleziona **Crea configurazione** per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="11d42-267">Select **Create configuration** to open the drop-down dialog box.</span></span> <span data-ttu-id="11d42-268">Puoi utilizzare questa finestra di dialogo per creare una nuova configurazione per un formato di pagamento personalizzato.</span><span class="sxs-lookup"><span data-stu-id="11d42-268">You can use this dialog box to create a new configuration for a custom payment format.</span></span>
4. <span data-ttu-id="11d42-269">Nel gruppo di campi **Nuovo**, selezionare l'opzione **Deriva da nome: BACS (Regno Unito), Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="11d42-269">In the **New** field group, select the **Derive from Name: BACS (UK), Microsoft** option.</span></span>
5. <span data-ttu-id="11d42-270">Nel campo **Nome**, immetti **BACS (Regno Unito, personalizzato)**.</span><span class="sxs-lookup"><span data-stu-id="11d42-270">In the **Name** field, enter **BACS (UK custom)**.</span></span>

    ![Finestra di dialogo a discesa Crea configurazione](./media/er-quick-start2-add-derived-format.png)

6. <span data-ttu-id="11d42-272">Selezionare **Crea configurazione**.</span><span class="sxs-lookup"><span data-stu-id="11d42-272">Select **Create configuration**.</span></span>

<span data-ttu-id="11d42-273">Viene creata la versione 1.1.1 della configurazione del formato ER **BACS (Regno Unito, personalizzato)**.</span><span class="sxs-lookup"><span data-stu-id="11d42-273">Version 1.1.1 of the **BACS (UK custom)** ER format configuration is created.</span></span> <span data-ttu-id="11d42-274">Questa versione ha uno [stato](general-electronic-reporting.md#component-versioning) di **Bozza** e può essere modificata.</span><span class="sxs-lookup"><span data-stu-id="11d42-274">This version has a [status](general-electronic-reporting.md#component-versioning) of **Draft** and can be edited.</span></span> <span data-ttu-id="11d42-275">Il contenuto corrente del tuo formato ER personalizzato corrisponde al contenuto del formato fornito da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="11d42-275">The current content of your custom ER format matches the content of the format that is provided by Microsoft.</span></span>

![Pagina Configurazioni](./media/er-quick-start2-derived-format-configuration1.png)

### <a name="edit-a-custom-format"></a><a id="ConfigureDerivedFormat"></a><span data-ttu-id="11d42-277">Modificare un formato personalizzato</span><span class="sxs-lookup"><span data-stu-id="11d42-277">Edit a custom format</span></span>

<span data-ttu-id="11d42-278">È necessario configurare il formato personalizzato in modo che soddisfi i requisiti specifici della banca.</span><span class="sxs-lookup"><span data-stu-id="11d42-278">You must configure your custom format so that it meets bank-specific requirements.</span></span> <span data-ttu-id="11d42-279">Ad esempio, una banca potrebbe richiedere che i file di pagamento generati includano il codice SWIFT (Society for Worldwide Interbank Financial Telecommunication) di una banca a cui è assegnato il ruolo di agente nel pagamento del fornitore elaborato.</span><span class="sxs-lookup"><span data-stu-id="11d42-279">For example, a bank might require that payment files that are generated include the Society for Worldwide Interbank Financial Telecommunication (SWIFT) code of a bank that is assigned the agent role in the processed vendor payment.</span></span> <span data-ttu-id="11d42-280">I codici SWIFT sono codici bancari internazionali che identificano banche specifiche in tutto il mondo.</span><span class="sxs-lookup"><span data-stu-id="11d42-280">SWIFT codes are international bank codes that identify specific banks worldwide.</span></span> <span data-ttu-id="11d42-281">Sono anche noti come codici identificativi bancari (BIC).</span><span class="sxs-lookup"><span data-stu-id="11d42-281">They are also known as Bank Identifier Codes (BICs).</span></span> <span data-ttu-id="11d42-282">Il codice SWIFT deve contenere 11 caratteri e deve essere inserito all'inizio di ogni riga di pagamento in un file di pagamento generato.</span><span class="sxs-lookup"><span data-stu-id="11d42-282">The SWIFT code must be 11 characters long, and it must be entered at the beginning of every payment line in a generated payment file.</span></span>

1. <span data-ttu-id="11d42-283">Andare a **Amministrazione organizzazione** \> **Creazione di report elettronici** \> **Configurazioni**.</span><span class="sxs-lookup"><span data-stu-id="11d42-283">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="11d42-284">Nella pagina **Configurazioni**, nella struttura delle configurazioni del riquadro sinistro, espandi **Modello di pagamento**, quindi seleziona **BACS (Regno Unito, personalizzato)**.</span><span class="sxs-lookup"><span data-stu-id="11d42-284">On the **Configurations** page, in the configuration tree in the left pane, expand **Payment model**, and then select **BACS (UK custom)**.</span></span>
3. <span data-ttu-id="11d42-285">Nella scheda dettaglio **Versioni** seleziona la versione **1.1.1** della configurazione selezionata.</span><span class="sxs-lookup"><span data-stu-id="11d42-285">On the **Versions** FastTab, select version **1.1.1** of the selected configuration.</span></span>
4. <span data-ttu-id="11d42-286">Selezionare **Progettazione**.</span><span class="sxs-lookup"><span data-stu-id="11d42-286">Select **Designer**.</span></span>
5. <span data-ttu-id="11d42-287">Nella pagina **Progettazione formati**, seleziona **Mostra dettagli** per visualizzare altre informazioni sugli elementi del formato.</span><span class="sxs-lookup"><span data-stu-id="11d42-287">On the **Format designer** page, select **Show details** to view more information about the format elements.</span></span>
6. <span data-ttu-id="11d42-288">Espandi e rivedi i seguenti elementi:</span><span class="sxs-lookup"><span data-stu-id="11d42-288">Expand and review the following elements:</span></span>

    - <span data-ttu-id="11d42-289">L'elemento **BACSReportsFolder** del tipo **Cartella**.</span><span class="sxs-lookup"><span data-stu-id="11d42-289">The **BACSReportsFolder** element of the **Folder** type.</span></span> <span data-ttu-id="11d42-290">Questo elemento viene utilizzato per generare output in formato ZIP.</span><span class="sxs-lookup"><span data-stu-id="11d42-290">This element is used to generate output in ZIP format.</span></span>
    - <span data-ttu-id="11d42-291">L'elemento **file** del tipo **File**.</span><span class="sxs-lookup"><span data-stu-id="11d42-291">The **file** element of the **File** type.</span></span> <span data-ttu-id="11d42-292">Questo elemento viene utilizzato per generare un file di pagamento in formato TXT.</span><span class="sxs-lookup"><span data-stu-id="11d42-292">This element is used to generate a payment file in TXT format.</span></span>
    - <span data-ttu-id="11d42-293">L'elemento **transazioni** del tipo **Sequenza**.</span><span class="sxs-lookup"><span data-stu-id="11d42-293">The **transactions** element of the **Sequence** type.</span></span> <span data-ttu-id="11d42-294">Questo elemento viene utilizzato per generare una riga di pagamento singola in un file di pagamento.</span><span class="sxs-lookup"><span data-stu-id="11d42-294">This element is used to generate a single payment line in a payment file.</span></span>
    - <span data-ttu-id="11d42-295">L'elemento **transazione** del tipo **Sequenza**.</span><span class="sxs-lookup"><span data-stu-id="11d42-295">The **transaction** element of the **Sequence** type.</span></span> <span data-ttu-id="11d42-296">Questo elemento viene utilizzato per generare campi singoli di una riga di pagamento singola.</span><span class="sxs-lookup"><span data-stu-id="11d42-296">This element is used to generate individual fields of a single payment line.</span></span>

7. <span data-ttu-id="11d42-297">Seleziona l'elemento **transazione**.</span><span class="sxs-lookup"><span data-stu-id="11d42-297">Select the **transaction** element.</span></span>

    ![Elemento di transazione nella finestra di progettazione Operazioni ER](./media/er-quick-start2-derived-format0.png)

    > [!NOTE]
    > <span data-ttu-id="11d42-299">Il report fornito è configurato in modo tale che <a id="PositionRoutingNumber"></a>ogni riga di pagamento inizi con il numero di registrazione bancario.</span><span class="sxs-lookup"><span data-stu-id="11d42-299">The provided report is configured so that <a id="PositionRoutingNumber"></a>every payment line starts with the bank routing number.</span></span> <span data-ttu-id="11d42-300">L'elemento di formato **vendBankRouteNum** viene utilizzato per questo scopo.</span><span class="sxs-lookup"><span data-stu-id="11d42-300">The **vendBankRouteNum** format element is used for this purpose.</span></span> 

8. <span data-ttu-id="11d42-301">Seleziona **Aggiungi**, quindi seleziona il tipo **Testo\\Stringa** dell'elemento di formato che stai aggiungendo:</span><span class="sxs-lookup"><span data-stu-id="11d42-301">Select **Add**, and then select the **Text\\String** type of the format element that you're adding:</span></span>

    1. <span data-ttu-id="11d42-302">Nel campo **Nome**, immetti **vendBankSWIFT**.</span><span class="sxs-lookup"><span data-stu-id="11d42-302">In the **Name** field, enter **vendBankSWIFT**.</span></span>
    2. <span data-ttu-id="11d42-303">Nel campo **Lunghezza minima** immetti **11**.</span><span class="sxs-lookup"><span data-stu-id="11d42-303">In the **Minimum length** field, enter **11**.</span></span>
    3. <span data-ttu-id="11d42-304">Nel campo **Lunghezza massima** immetti **11**.</span><span class="sxs-lookup"><span data-stu-id="11d42-304">In the **Maximum length** field, enter **11**.</span></span>
    4. <span data-ttu-id="11d42-305">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="11d42-305">Select **OK**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="11d42-306">L'elemento **vendBankSWIFT** verrà utilizzato per inserire il codice SWIFT di una banca del fornitore nei file generati.</span><span class="sxs-lookup"><span data-stu-id="11d42-306">The **vendBankSWIFT** element will be used to enter the SWIFT code of a vendor bank in generated files.</span></span>

9. <span data-ttu-id="11d42-307">Nell'albero della struttura del formato, seleziona **vendBankSWIFT**.</span><span class="sxs-lookup"><span data-stu-id="11d42-307">In the format structure tree, select **vendBankSWIFT**.</span></span>
10. <span data-ttu-id="11d42-308">Seleziona **Sposta su** per spostare l'elemento del formato selezionato di un livello superiore.</span><span class="sxs-lookup"><span data-stu-id="11d42-308">Select **Move up** to move the selected format element up one level.</span></span> <span data-ttu-id="11d42-309">Ripeti questo passaggio fino a quando l'elemento **vendBankSWIFT** è il <a id="PositionSWIFTCode"></a>primo elemento sotto l'elemento padre **transazione**.</span><span class="sxs-lookup"><span data-stu-id="11d42-309">Repeat this step until the **vendBankSWIFT** element is the <a id="PositionSWIFTCode"></a>first element under the parent **transaction** element.</span></span>

    ![VendBankSWIFT come primo elemento in transazione nella finestra di progettazione Operazioni ER](./media/er-quick-start2-derived-format1.png)

11. <span data-ttu-id="11d42-311">Mentre **vendBankSWIFT** è ancora selezionato nella struttura ad albero del formato, seleziona la scheda **Mapping**, quindi espandi l'origine dati **modello**.</span><span class="sxs-lookup"><span data-stu-id="11d42-311">While the **vendBankSWIFT** is still selected in the format structure tree, select the **Mapping** tab, and then expand the **model** data source.</span></span>
12. <span data-ttu-id="11d42-312">Espandi **model.Payment**\>**model.Payment.CreditorAgent** e seleziona il campo dell'origine dati **model.Payment.CreditorAgent.BICFI**.</span><span class="sxs-lookup"><span data-stu-id="11d42-312">Expand **model.Payment** \> **model.Payment.CreditorAgent**, and select the **model.Payment.CreditorAgent.BICFI** data source field.</span></span> <span data-ttu-id="11d42-313">Questo campo dell'origine dati espone il codice SWIFT di una banca del fornitore a cui è assegnato il ruolo di agente nel pagamento del fornitore elaborato.</span><span class="sxs-lookup"><span data-stu-id="11d42-313">This data source field exposes the SWIFT code of a vendor bank that is assigned the agent role in the processed vendor payment.</span></span>
13. <span data-ttu-id="11d42-314">Selezionare **Associa**.</span><span class="sxs-lookup"><span data-stu-id="11d42-314">Select **Bind**.</span></span> <span data-ttu-id="11d42-315">L'elemento di formato **vendBankSWIFT** è ora associato al campo dell'origine dati **model.Payment.CreditorAgent.BICFI**, in modo che i codici SWIFT vengano inseriti nei file di pagamento generati.</span><span class="sxs-lookup"><span data-stu-id="11d42-315">The **vendBankSWIFT** format element is now bound with the **model.Payment.CreditorAgent.BICFI** data source field, so that SWIFT codes will be entered in generated payment files.</span></span>

    ![Elemento del formato vendBankSWIFT associato al campo dell'origine dati model.Payment.CreditorAgent.BICFI nella finestra di progettazione Operazioni ER](./media/er-quick-start2-derived-format2.png)

14. <span data-ttu-id="11d42-317">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="11d42-317">Select **Save**.</span></span>
15. <span data-ttu-id="11d42-318">Chiudi la pagina della finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="11d42-318">Close the designer page.</span></span>

### <a name="mark-a-custom-format-as-runnable"></a><a id="MarkFormatRunnable"></a><span data-ttu-id="11d42-319">Contrassegnare un formato personalizzato come eseguibile</span><span class="sxs-lookup"><span data-stu-id="11d42-319">Mark a custom format as runnable</span></span>

<span data-ttu-id="11d42-320">Ora che la prima versione del tuo formato personalizzato è stata creata e ha uno stato di **Bozza**, puoi eseguirla a scopo di test.</span><span class="sxs-lookup"><span data-stu-id="11d42-320">Now that the first version of your custom format has been created and has a status of **Draft**, you can run it for testing purposes.</span></span> <span data-ttu-id="11d42-321">Per eseguire il report, è necessario elaborare un pagamento fornitore utilizzando il metodo di pagamento che fa riferimento al formato ER personalizzato.</span><span class="sxs-lookup"><span data-stu-id="11d42-321">To run the report, you must process a vendor payment by using the payment method that refers to your custom ER format.</span></span> <span data-ttu-id="11d42-322">Per impostazione predefinita, quando chiami un formato ER dall'applicazione, solo le versioni che hanno uno stato di **Completata** o **Condivisa** vengono [considerate](general-electronic-reporting.md#component-versioning).</span><span class="sxs-lookup"><span data-stu-id="11d42-322">By default, when you call an ER format from the application, only versions that have a status of **Completed** or **Shared** are [considered](general-electronic-reporting.md#component-versioning).</span></span> <span data-ttu-id="11d42-323">Questo comportamento consente di impedire l'utilizzo di formati ER con progettazioni incomplete.</span><span class="sxs-lookup"><span data-stu-id="11d42-323">This behavior helps prevent ER formats that have unfinished designs from being used.</span></span> <span data-ttu-id="11d42-324">Tuttavia, per le esecuzioni di test, è possibile forzare l'applicazione a utilizzare la versione del formato ER con uno stato di **Bozza**.</span><span class="sxs-lookup"><span data-stu-id="11d42-324">However, for your test runs, you can force the application to use the version of your ER format that has a status of **Draft**.</span></span> <span data-ttu-id="11d42-325">In questo modo, è possibile regolare la versione del formato corrente se sono necessarie modifiche.</span><span class="sxs-lookup"><span data-stu-id="11d42-325">In this way, you can adjust the current format version if any modifications are required.</span></span> <span data-ttu-id="11d42-326">Per ulteriori informazioni, vedi [Applicabilità](electronic-reporting-destinations.md#applicability).</span><span class="sxs-lookup"><span data-stu-id="11d42-326">For more information, see [Applicability](electronic-reporting-destinations.md#applicability).</span></span>

<span data-ttu-id="11d42-327">Per utilizzare la versione bozza di un formato ER, è necessario contrassegnare esplicitamente il formato ER.</span><span class="sxs-lookup"><span data-stu-id="11d42-327">To use the draft version of an ER format, you must explicitly mark the ER format.</span></span>

1. <span data-ttu-id="11d42-328">Andare a **Amministrazione organizzazione** \> **Creazione di report elettronici** \> **Configurazioni**.</span><span class="sxs-lookup"><span data-stu-id="11d42-328">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="11d42-329">Nella pagina **Configurazioni**, nel Riquadro azioni, nella scheda **Configurazioni**, nel gruppo **Impostazioni avanzate**, selezionare **Parametri utente**.</span><span class="sxs-lookup"><span data-stu-id="11d42-329">On the **Configurations** page, on the Action Pane, on the **Configurations** tab, in the **Advanced settings** group, select **User parameters**.</span></span>
3. <span data-ttu-id="11d42-330">Nella finestra di dialogo **Parametri utente**, imposta l'opzione **Esegui impostazioni** su **Sì**, quindi seleziona **OK**.</span><span class="sxs-lookup"><span data-stu-id="11d42-330">In the **User parameters** dialog box, set the **Run settings** option to **Yes**, and then select **OK**.</span></span>
4. <span data-ttu-id="11d42-331">Seleziona **Modifica** per rendere la pagina modificabile come richiesto.</span><span class="sxs-lookup"><span data-stu-id="11d42-331">Select **Edit** to make the current page editable, as required.</span></span>
5. <span data-ttu-id="11d42-332">Nell'albero di configurazione nel riquadro sinistro, seleziona **BACS (Regno Unito, personalizzato)**.</span><span class="sxs-lookup"><span data-stu-id="11d42-332">In the configuration tree in the left pane, select **BACS (UK custom)**.</span></span>
6. <span data-ttu-id="11d42-333">Imposta l'opzione **Esegui bozza** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="11d42-333">Set the **Run Draft** option to **Yes**.</span></span>

    ![Opzione Esegui bozza nella pagina Configurazioni](./media/er-quick-start2-derived-format-configuration2.png)

## <a name="process-a-vendor-payment-by-using-the-custom-er-format"></a><a id="ProcessVendorPayment2"></a><span data-ttu-id="11d42-335">Elaborare un pagamento fornitore utilizzando il formato ER personalizzato</span><span class="sxs-lookup"><span data-stu-id="11d42-335">Process a vendor payment by using the custom ER format</span></span>

### <a name="set-up-the-electronic-payment-method"></a><a id="ConfigureMethodOfPayment2"></a><span data-ttu-id="11d42-336">Configurare il metodo di pagamento elettronico</span><span class="sxs-lookup"><span data-stu-id="11d42-336">Set up the electronic payment method</span></span>

<span data-ttu-id="11d42-337">È necessario configurare il metodo di pagamento elettronico in modo che il formato ER personalizzato venga utilizzato per elaborare i pagamenti del fornitore.</span><span class="sxs-lookup"><span data-stu-id="11d42-337">You must configure the electronic method of payment so that your custom ER format is used to process vendor payments.</span></span>

1. <span data-ttu-id="11d42-338">Andare a **Contabilità fornitori** \> **Impostazione pagamenti** \> **Metodi di pagamento**.</span><span class="sxs-lookup"><span data-stu-id="11d42-338">Go to **Accounts payable** \> **Payment setup** \> **Methods of payment**.</span></span>
2. <span data-ttu-id="11d42-339">Nella pagina **Metodi di pagamento - Fornitori**, seleziona il metodo di pagamento **Elettronico** nel riquadro a sinistra.</span><span class="sxs-lookup"><span data-stu-id="11d42-339">On the **Methods of payment - vendors** page, select the **Electronic** method of payment in the left pane.</span></span>
3. <span data-ttu-id="11d42-340">Selezionare **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="11d42-340">Select **Edit**.</span></span>
4. <span data-ttu-id="11d42-341">Nella scheda dettaglio **Formatofile**, imposta l'opzione **Formato esportazione elettronica generica** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="11d42-341">On the **File format** FastTab, set the **General electronic export format** option to **Yes**.</span></span>
5. <span data-ttu-id="11d42-342">Nel campo **Esporta configurazione formato** seleziona la configurazione del formato **BACS (Regno Unito, personalizzato)**.</span><span class="sxs-lookup"><span data-stu-id="11d42-342">In the **Export format configuration** field, select the **BACS (UK custom)** format configuration.</span></span>

    ![Pagina Metodi di pagamento - Fornitori](./media/er-quick-start2-method-of-payment2.png)

6. <span data-ttu-id="11d42-344">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="11d42-344">Select **Save**.</span></span>

### <a name="process-a-vendor-payment"></a><a id="ProcessPayment2"></a><span data-ttu-id="11d42-345">Elaborare un pagamento fornitore</span><span class="sxs-lookup"><span data-stu-id="11d42-345">Process a vendor payment</span></span>

1. <span data-ttu-id="11d42-346">Andare a **Contabilità fornitori** \> **Pagamenti** \> **Giornale di registrazione pagamenti fornitore**.</span><span class="sxs-lookup"><span data-stu-id="11d42-346">Go to **Accounts payable** \> **Payments** \> **Vendor payment journal**.</span></span>
2. <span data-ttu-id="11d42-347">Nella pagina **Giornale di registrazione pagamenti fornitore** seleziona il giornale di registrazione pagamenti creato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="11d42-347">On the **Vendor payment journal** page, select the payment journal that you created earlier.</span></span>
3. <span data-ttu-id="11d42-348">Selezionare **Righe**.</span><span class="sxs-lookup"><span data-stu-id="11d42-348">Select **Lines**.</span></span>
4. <span data-ttu-id="11d42-349">Nella pagina **Pagamenti fornitore**, sopra la griglia, seleziona e **Stato pagamenti**\>**Nessuno**.</span><span class="sxs-lookup"><span data-stu-id="11d42-349">On the **Vendor payments** page, above the grid, select **Payment status** \> **None**.</span></span>
5. <span data-ttu-id="11d42-350">Seleziona **Genera pagamento**.</span><span class="sxs-lookup"><span data-stu-id="11d42-350">Select **Generate payment**.</span></span>
6. <span data-ttu-id="11d42-351">Nella finestra di dialogo **Genera pagamenti** immetti le seguenti informazioni:</span><span class="sxs-lookup"><span data-stu-id="11d42-351">In the **Generate payments** dialog box, enter the following information:</span></span>

    - <span data-ttu-id="11d42-352">Nel campo **Metodo di pagamento** seleziona **Elettronico**.</span><span class="sxs-lookup"><span data-stu-id="11d42-352">In the **Method of payment** field, select **Electronic**.</span></span>
    - <span data-ttu-id="11d42-353">Nel campo **Conto bancario** selezionare **GBSI OPER**.</span><span class="sxs-lookup"><span data-stu-id="11d42-353">In the **Bank account** field, select **GBSI OPER**.</span></span>

7. <span data-ttu-id="11d42-354">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="11d42-354">Select **OK**.</span></span>
8. <span data-ttu-id="11d42-355">Nella finestra di dialogo **Parametri per la creazione di report elettronici**, imposta l'opzione **Stampa report di controllo** su **Sì**, quindi seleziona **OK**.</span><span class="sxs-lookup"><span data-stu-id="11d42-355">In the **Electronic report parameters** dialog box, set the **Print control report** option to **Yes**, and then select **OK**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="11d42-356">Oltre al file di pagamento, è ora possibile generare solo il report di controllo.</span><span class="sxs-lookup"><span data-stu-id="11d42-356">In addition to the payment file, you can generate only the control report.</span></span>

9. <span data-ttu-id="11d42-357">Scarica il file zip, quindi estrai i seguenti file:</span><span class="sxs-lookup"><span data-stu-id="11d42-357">Download the zip file, and then extract the following files from it:</span></span>

    - <span data-ttu-id="11d42-358">Il report di controllo in formato Excel</span><span class="sxs-lookup"><span data-stu-id="11d42-358">The control report in Excel format</span></span>
    - <span data-ttu-id="11d42-359">Il file di pagamento in formato TXT</span><span class="sxs-lookup"><span data-stu-id="11d42-359">The payment file in TXT format</span></span>

        <span data-ttu-id="11d42-360">Si noti che, in conformità con la struttura del formato ER personalizzato, la riga di pagamento nel file generato ora [inizia](#PositionSWIFTCode) con il codice SWIFT [immesso](#DefineSWIFTCode) per il conto bancario del fornitore il cui pagamento è stato elaborato.</span><span class="sxs-lookup"><span data-stu-id="11d42-360">Notice that, in accordance with the structure of your custom ER format, the payment line in the generated file now [starts](#PositionSWIFTCode) with the SWIFT code that was [entered](#DefineSWIFTCode) for the bank account of the vendor whose payment has been processed.</span></span>

        ![File di pagamento in formato TXT](./media/er-quick-start2-payment-file2.png)

## <a name="import-new-versions-of-the-standard-er-format-configurations"></a><a id="ImportERSolution2"></a><span data-ttu-id="11d42-362">Importare nuove versioni delle configurazioni del formato ER standard</span><span class="sxs-lookup"><span data-stu-id="11d42-362">Import new versions of the standard ER format configurations</span></span>

<span data-ttu-id="11d42-363">Nell'esempio mostrato in questa sezione, ricevi una notifica sull'articolo della Knowledge Base [KB3763330](https://fix.lcs.dynamics.com/Issue/Details?kb=3182046).</span><span class="sxs-lookup"><span data-stu-id="11d42-363">For the example that is shown in this section, you receive a notification about Knowledge Base article [KB3763330](https://fix.lcs.dynamics.com/Issue/Details?kb=3182046).</span></span> <span data-ttu-id="11d42-364">Questa notifica ti informa sulla nuova versione del formato ER **BACS (Regno Unito)** che è stato pubblicato da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="11d42-364">This notification informs you about the new version of the **BACS (UK)** ER format that has been published by Microsoft.</span></span> <span data-ttu-id="11d42-365">Oltre al report di controllo, questa nuova versione consente agli utenti di generare il report di avviso di pagamento e il report della nota di partecipazione durante l'elaborazione di un pagamento fornitore.</span><span class="sxs-lookup"><span data-stu-id="11d42-365">In addition to the control report, this new version lets users generate the payment advice report and the attending note report while a vendor payment is being processed.</span></span> <span data-ttu-id="11d42-366">Vuoi iniziare a usare quella funzionalità.</span><span class="sxs-lookup"><span data-stu-id="11d42-366">You want to start to use that functionality.</span></span>

### <a name="import-new-versions-of-the-standard-er-configurations"></a><a id="ImportERFormat2"></a><span data-ttu-id="11d42-367">Importare nuove versioni delle configurazioni ER standard</span><span class="sxs-lookup"><span data-stu-id="11d42-367">Import new versions of the standard ER configurations</span></span>

<span data-ttu-id="11d42-368">Per aggiungere le nuove versioni delle configurazioni ER standard all'istanza corrente di Finance , è necessario importarle dall'[archivio](general-electronic-reporting.md#Repository) ER che hai configurato.</span><span class="sxs-lookup"><span data-stu-id="11d42-368">To add new versions of the ER configurations to the current Finance instance, you must import them from the ER [repository](general-electronic-reporting.md#Repository) that you've configured.</span></span>

1. <span data-ttu-id="11d42-369">Andare a **Amministrazione organizzazione** \> **Aree di lavoro** \> **Creazione di report elettronici**.</span><span class="sxs-lookup"><span data-stu-id="11d42-369">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
2. <span data-ttu-id="11d42-370">Nella pagina **Configurazioni localizzazione**, nella sezione **Provider di configurazione**, seleziona il riquadro **Microsoft**, quindi seleziona **Archivi** per visualizzare l'elenco dei repository per il provider Microsoft.</span><span class="sxs-lookup"><span data-stu-id="11d42-370">On the **Localization configurations** page, in the **Configuration providers** section, select the **Microsoft** tile, and then select **Repositories** to view the list of repositories for the Microsoft provider.</span></span>
3. <span data-ttu-id="11d42-371">Nella pagina **Archivi di configurazione** seleziona l'archivio del tipo **Globale**, quindi seleziona **Apri**.</span><span class="sxs-lookup"><span data-stu-id="11d42-371">On the **Configuration repositories** page, select the repository of the **Global** type, and then select **Open**.</span></span> <span data-ttu-id="11d42-372">Se viene richiesta l'autorizzazione per connettersi a Regulatory Configuration Service, segui le istruzioni di autorizzazione.</span><span class="sxs-lookup"><span data-stu-id="11d42-372">If you're prompted for authorization to connect to Regulatory Configuration Service, follow the authorization instructions.</span></span>
4. <span data-ttu-id="11d42-373">Nella pagina **Archivio di configurazioni**, nella struttura delle configurazioni del riquadro sinistro, seleziona la configurazione del formato **BACS (Regno Unito)**.</span><span class="sxs-lookup"><span data-stu-id="11d42-373">On the **Configuration repository** page, in the configuration tree in the left pane, select the **BACS (UK)** format configuration.</span></span>
5. <span data-ttu-id="11d42-374">Nella scheda dettaglio **Versioni** seleziona la versione **3.3** della configurazione del formato ER selezionata.</span><span class="sxs-lookup"><span data-stu-id="11d42-374">On the **Versions** FastTab, select version **3.3** of the selected ER format configuration.</span></span>
6. <span data-ttu-id="11d42-375">Seleziona **Importa** per scaricare la versione selezionata dall'archivio Globale nell'istanza corrente di Finance.</span><span class="sxs-lookup"><span data-stu-id="11d42-375">Select **Import** to download the selected version from the Global repository to the current Finance instance.</span></span>

![Configurazione della pagina dell'archivio](./media/er-quick-start2-import-solution2.png)

> [!TIP]
> <span data-ttu-id="11d42-377">In caso di problemi di accesso all'[archivio globale](er-download-configurations-global-repo.md), puoi invece [scaricare le configurazioni](download-electronic-reporting-configuration-lcs.md) da LCS.</span><span class="sxs-lookup"><span data-stu-id="11d42-377">If you have trouble accessing the [Global repository](er-download-configurations-global-repo.md), you can [download configurations](download-electronic-reporting-configuration-lcs.md) from LCS instead.</span></span>

### <a name="review-the-imported-er-format-configurations"></a><a id="ReviewImportedERFormat"></a><span data-ttu-id="11d42-378">Rivedere le configurazioni del formato ER importate</span><span class="sxs-lookup"><span data-stu-id="11d42-378">Review the imported ER format configurations</span></span>

1. <span data-ttu-id="11d42-379">Andare a **Amministrazione organizzazione** \> **Aree di lavoro** \> **Creazione di report elettronici**.</span><span class="sxs-lookup"><span data-stu-id="11d42-379">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
2. <span data-ttu-id="11d42-380">Nella pagina **Configurazioni localizzazione**, nella sezione **Configurazioni**, selezionare il riquadro **Configurazioni report**.</span><span class="sxs-lookup"><span data-stu-id="11d42-380">On the **Localization configurations** page, in the **Configurations** section, select the **Reporting configurations** tile.</span></span>
3. <span data-ttu-id="11d42-381">Nella pagina **Configurazioni**, nella struttura delle configurazioni del riquadro sinistro, espandi **Modello di pagamento**, quindi seleziona **BACS (Regno Unito)**.</span><span class="sxs-lookup"><span data-stu-id="11d42-381">On the **Configurations** page, in the configuration tree in the left pane, expand **Payment model**, and then select **BACS (UK)**.</span></span>
4. <span data-ttu-id="11d42-382">Nella scheda dettaglio **Versioni**, selezionare la versione **3.3**.</span><span class="sxs-lookup"><span data-stu-id="11d42-382">On the **Versions** FastTab, select version **3.3**.</span></span>
5. <span data-ttu-id="11d42-383">Selezionare **Progettazione**.</span><span class="sxs-lookup"><span data-stu-id="11d42-383">Select **Designer**.</span></span>
6. <span data-ttu-id="11d42-384">Nella pagina **Progettazione formati**, espandi l'elemento di formato **BACSReportsFolder**.</span><span class="sxs-lookup"><span data-stu-id="11d42-384">On the **Format designer** page, expand the **BACSReportsFolder** format element.</span></span>
7.  <span data-ttu-id="11d42-385">Si noti che la versione 3.3 contiene l'elemento di formato **PaymentAdviceReport** utilizzato per generare un report di avviso di pagamento quando viene elaborato un pagamento fornitore.</span><span class="sxs-lookup"><span data-stu-id="11d42-385">Notice that version 3.3 contains the **PaymentAdviceReport** format element that is used to generate a payment advice report when a vendor payment is processed.</span></span>

    ![Elemento di formato PaymentAdviceReport nella finestra di progettazione Operazioni ER](./media/er-quick-start2-imported-solution2.png)

8. <span data-ttu-id="11d42-387">Chiudi la pagina della finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="11d42-387">Close the designer page.</span></span>

## <a name="adopt-the-changes-in-the-new-version-of-an-imported-format-in-a-custom-format"></a><a id="AdoptNewBaseVersion"></a><span data-ttu-id="11d42-388">Adottare le modifiche nella nuova versione di un formato importato in un formato personalizzato</span><span class="sxs-lookup"><span data-stu-id="11d42-388">Adopt the changes in the new version of an imported format in a custom format</span></span>

### <a name="complete-the-current-draft-version-of-a-custom-format"></a><a id="CompleteDerivedFormat"></a><span data-ttu-id="11d42-389">Completare la versione in bozza corrente di un formato personalizzato</span><span class="sxs-lookup"><span data-stu-id="11d42-389">Complete the current draft version of a custom format</span></span>

<span data-ttu-id="11d42-390">Se desideri mantenere lo stato corrente del formato personalizzato, completa la versione della bozza 1.1.1 modificandone lo stato da **Bozza** a **Completato**.</span><span class="sxs-lookup"><span data-stu-id="11d42-390">If you want to keep the current state of your custom format, complete the draft version 1.1.1 by changing its status from **Draft** to **Completed**.</span></span>

1. <span data-ttu-id="11d42-391">Andare a **Amministrazione organizzazione** \> **Aree di lavoro** \> **Creazione di report elettronici**.</span><span class="sxs-lookup"><span data-stu-id="11d42-391">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
2. <span data-ttu-id="11d42-392">Nella pagina **Configurazioni localizzazione**, nella sezione **Configurazioni**, selezionare il riquadro **Configurazioni report**.</span><span class="sxs-lookup"><span data-stu-id="11d42-392">On the **Localization configurations** page, in the **Configurations** section, select the **Reporting configurations** tile.</span></span>
3. <span data-ttu-id="11d42-393">Nella pagina **Configurazioni**, nella struttura delle configurazioni del riquadro sinistro, espandi **Modello di pagamento**, espandi **BACS (Regno Unito)** quindi seleziona **BACS (Regno Unito, personalizzato)**.</span><span class="sxs-lookup"><span data-stu-id="11d42-393">On the **Configurations** page, in the configuration tree in the left pane, expand **Payment model**, expand **BACS (UK)**, and then select **BACS (UK custom)**.</span></span>
4. <span data-ttu-id="11d42-394">Nella Scheda dettaglio **Versioni**, seleziona **Cambia stato**\>**Completa**, quindi seleziona **OK**.</span><span class="sxs-lookup"><span data-stu-id="11d42-394">On the **Versions** FastTab, select **Change status** \> **Complete**, and then select **OK**.</span></span>

<span data-ttu-id="11d42-395">Lo stato della versione 1.1.1 viene modificato da **Bozza** in **Completato** e la versione diventa di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="11d42-395">The status of version 1.1.1 is changed from **Draft** to **Completed**, and the version becomes read-only.</span></span> <span data-ttu-id="11d42-396">Una nuova versione modificabile, 1.1.2, è stata aggiunta e ha uno stato di **Bozza**.</span><span class="sxs-lookup"><span data-stu-id="11d42-396">A new editable version, 1.1.2, has been added and has a status of **Draft**.</span></span> <span data-ttu-id="11d42-397">Puoi utilizzare questa versione per apportare ulteriori modifiche al tuo formato ER personalizzato.</span><span class="sxs-lookup"><span data-stu-id="11d42-397">You can use this version to make further changes in your custom ER format.</span></span>

### <a name="rebase-a-custom-format-to-a-new-base-version"></a><a id="RebaseDerivedFormat"></a><span data-ttu-id="11d42-398">Riassegnare un formato personalizzato su una nuova versione di base</span><span class="sxs-lookup"><span data-stu-id="11d42-398">Rebase a custom format to a new base version</span></span>

<span data-ttu-id="11d42-399">Per iniziare a utilizzare la nuova funzionalità della versione 3.3 del formato **BACS (Regno Unito)** nella personalizzazione, è necessario modificare la versione della configurazione di base per la configurazione personalizzata, **BACS (Regno Unito, personalizzazione)**.</span><span class="sxs-lookup"><span data-stu-id="11d42-399">To start to use the new functionality of version 3.3 of the **BACS (UK)** format in your customization, you must change the base configuration version for the custom configuration, **BACS (UK custom)**.</span></span> <span data-ttu-id="11d42-400">Questo processo è noto come [riassegnazione](general-electronic-reporting.md#upgrading-a-format-selecting-a-new-version-of-base-format-rebase).</span><span class="sxs-lookup"><span data-stu-id="11d42-400">This process is known as [rebasing](general-electronic-reporting.md#upgrading-a-format-selecting-a-new-version-of-base-format-rebase).</span></span> <span data-ttu-id="11d42-401">Anziché la versione 1.1 di **BACS (Regno Unito)**, utilizza la versione 3.3.</span><span class="sxs-lookup"><span data-stu-id="11d42-401">Instead of version 1.1 of **BACS (UK)**, use version 3.3.</span></span>

1. <span data-ttu-id="11d42-402">Andare a **Amministrazione organizzazione** \> **Creazione di report elettronici** \> **Configurazioni**.</span><span class="sxs-lookup"><span data-stu-id="11d42-402">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="11d42-403">Nella pagina **Configurazioni**, nella struttura delle configurazioni del riquadro sinistro, espandi **Modello di pagamento**, quindi seleziona **BACS (Regno Unito, personalizzato)**.</span><span class="sxs-lookup"><span data-stu-id="11d42-403">On the **Configurations** page, in the configuration tree in the left pane, expand **Payment model**, and then select **BACS (UK custom)**.</span></span>
3. <span data-ttu-id="11d42-404">Nella Scheda Dettaglio **Versioni**, seleziona la versione **1.1.2**, quindi seleziona **Riassegna**.</span><span class="sxs-lookup"><span data-stu-id="11d42-404">On the **Versions** FastTab, select version **1.1.2**, and then select **Rebase**.</span></span>
4. <span data-ttu-id="11d42-405">Nella finestra di dialogo **Riassegna**, nel campo **Versione destinazione**, seleziona la versione **3.3** della configurazione di base per applicarla come nuova base e utilizzarla per aggiornare la configurazione.</span><span class="sxs-lookup"><span data-stu-id="11d42-405">In the **Rebase** dialog box, in the **Target version** field, select version **3.3** of the base configuration to apply it as the new base and use it to update the configuration.</span></span>

    ![Finestra di dialogo Riassegna](./media/er-quick-start2-rebase1.png)

5. <span data-ttu-id="11d42-407">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="11d42-407">Select **OK**.</span></span>
6. <span data-ttu-id="11d42-408">Si noti che il numero della versione bozza è stato modificato da **1.1.2** a **3.3.2** per riflettere la modifica nella versione base.</span><span class="sxs-lookup"><span data-stu-id="11d42-408">Notice that the number of the draft version has been changed from **1.1.2** to **3.3.2** to reflect the change in the base version.</span></span>

    <span data-ttu-id="11d42-409">Quando la versione personalizzata e la nuova versione di base vengono unite, alcuni conflitti potrebbero essere individuati a causa di modifiche di formato che non possono essere unite automaticamente.</span><span class="sxs-lookup"><span data-stu-id="11d42-409">When the custom version and a new base version are merged, some conflicts might be discovered because of format changes that can't be merged automatically.</span></span>

    ![Configurazione riassegnata con conflitti nella pagina Configurazioni](./media/er-quick-start2-rebase2.png)

    <span data-ttu-id="11d42-411">Se vengono rilevati conflitti, devono essere risolti manualmente nella finestra di progettazione del formato.</span><span class="sxs-lookup"><span data-stu-id="11d42-411">If conflicts are discovered, they must be manually resolved in the format designer.</span></span>

7. <span data-ttu-id="11d42-412">Nella scheda dettaglio **Versioni**, selezionare la versione **3.3.2**.</span><span class="sxs-lookup"><span data-stu-id="11d42-412">On the **Versions** FastTab, select version **3.3.2**.</span></span>
8. <span data-ttu-id="11d42-413">Selezionare **Progettazione**.</span><span class="sxs-lookup"><span data-stu-id="11d42-413">Select **Designer**.</span></span>
9. <span data-ttu-id="11d42-414">Nella pagina **Progettazione formato**, sulla Scheda Dettaglio **Dettagli**, seleziona un record di conflitto di riassegnazione e quindi seleziona **Applica valore base**.</span><span class="sxs-lookup"><span data-stu-id="11d42-414">On the **Format designer** page, on the **Details** FastTab, select a rebase conflict record, and then select **Apply base value**.</span></span>

    ![Record di conflitto riassegnazione nella finestea di progettazione Operazioni ER](./media/er-quick-start2-rebase3.png)

10. <span data-ttu-id="11d42-416">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="11d42-416">Select **Save**.</span></span>

    <span data-ttu-id="11d42-417">Il record di conflitto di riassegnazione non dovrebbe più apparire nella scheda Dettaglio **Dettagli**.</span><span class="sxs-lookup"><span data-stu-id="11d42-417">The rebase conflict record should no longer appear on the **Details** FastTab.</span></span>

    ![Conflitto risolto nella finestea di progettazione Operazioni ER](./media/er-quick-start2-rebase4.png)

    > [!NOTE]
    > <span data-ttu-id="11d42-419">Hai risolto il conflitto confermando che la versione 3 del modello base deve essere utilizzata in questo formato ER.</span><span class="sxs-lookup"><span data-stu-id="11d42-419">You resolved the conflict by confirming that version 3 of the base model must be used in this ER format.</span></span>

11. <span data-ttu-id="11d42-420">Espandi **BACSReportsFolder** \> **file** \> **transazioni** \> **transazione**.</span><span class="sxs-lookup"><span data-stu-id="11d42-420">Expand **BACSReportsFolder** \> **file** \> **transactions** \> **transaction**.</span></span>
12. <span data-ttu-id="11d42-421">Nella scheda **Mapping**, tieni presente che la versione 3.3.2 del tuo formato ER personalizzato contiene sia la tua personalizzazione (l'elemento di formato **vendBankSWIFT** ed è vincolante) e la nuova funzionalità della versione 3.3 del formato ER di base fornito da Microsoft (l'elemento di formato **PaymentAdviceReport** insieme ai suoi elementi nidificati e ai binding configurati).</span><span class="sxs-lookup"><span data-stu-id="11d42-421">On the **Mapping** tab, notice that version 3.3.2 of your custom ER format contains both your customization (the **vendBankSWIFT** format element and its binding) and the new functionality of version 3.3 of the base ER format that was provided by Microsoft (the **PaymentAdviceReport** format element together with its nested elements and configured bindings).</span></span> <span data-ttu-id="11d42-422">In pochi clic del mouse, hai adottato le modifiche di una nuova versione di base unendole alla tua personalizzazione.</span><span class="sxs-lookup"><span data-stu-id="11d42-422">In just a few mouse clicks, you adopted the modifications of a new base version by merging them with your customization.</span></span>

    ![Formato unito nella finestra di progettazione Operazioni ER](./media/er-quick-start2-rebase5.png)

13. <span data-ttu-id="11d42-424">Chiudi la pagina della finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="11d42-424">Close the designer page.</span></span>

> [!NOTE]
> <span data-ttu-id="11d42-425">L'azione di riassegnazione è reversibile.</span><span class="sxs-lookup"><span data-stu-id="11d42-425">The rebase action is reversible.</span></span> <span data-ttu-id="11d42-426">Per annullare questa riassegnazione, seleziona la versione **1.1.1** del formato **BACS (Regno Unito personalizzato)** nella Scheda Dettaglio **Versioni**, quindi seleziona **Ottieni questa versione**.</span><span class="sxs-lookup"><span data-stu-id="11d42-426">To cancel this rebase, select version **1.1.1** of the **BACS (UK custom)** format on the **Versions** FastTab, and then select **Get this version**.</span></span> <span data-ttu-id="11d42-427">La versione 3.3.2 verrà quindi rinumerata 1.1.2 e il contenuto della bozza della versione 1.1.2 corrisponderà al contenuto della versione 1.1.1.</span><span class="sxs-lookup"><span data-stu-id="11d42-427">Version 3.3.2 will then be renumbered 1.1.2, and the content of draft version 1.1.2 will match the content of version 1.1.1.</span></span>

### <a name="process-a-vendor-payment-by-using-a-rebased-er-format"></a><a id="ProcessPayment3"></a><span data-ttu-id="11d42-428">Elaborare un pagamento fornitore utilizzando un formato ER riassegnato</span><span class="sxs-lookup"><span data-stu-id="11d42-428">Process a vendor payment by using a rebased ER format</span></span>

1. <span data-ttu-id="11d42-429">Andare a **Contabilità fornitori** \> **Pagamenti** \> **Giornale di registrazione pagamenti fornitore**.</span><span class="sxs-lookup"><span data-stu-id="11d42-429">Go to **Accounts payable** \> **Payments** \> **Vendor payment journal**.</span></span>
2. <span data-ttu-id="11d42-430">Nella pagina **Giornale di registrazione pagamenti fornitore** seleziona il giornale di registrazione pagamenti creato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="11d42-430">On the **Vendor payment journal** page, select the payment journal that you created earlier.</span></span>
3. <span data-ttu-id="11d42-431">Selezionare **Righe**.</span><span class="sxs-lookup"><span data-stu-id="11d42-431">Select **Lines**.</span></span>
4. <span data-ttu-id="11d42-432">Nella pagina **Pagamenti fornitore**, sopra la griglia, seleziona e **Stato pagamenti**\>**Nessuno**.</span><span class="sxs-lookup"><span data-stu-id="11d42-432">On the **Vendor payments** page, above the grid, select **Payment status** \> **None**.</span></span>
5. <span data-ttu-id="11d42-433">Seleziona **Genera pagamento**.</span><span class="sxs-lookup"><span data-stu-id="11d42-433">Select **Generate payment**.</span></span>
6. <span data-ttu-id="11d42-434">Nella finestra di dialogo **Genera pagamenti** immetti le seguenti informazioni:</span><span class="sxs-lookup"><span data-stu-id="11d42-434">In the **Generate payments** dialog box, enter the following information:</span></span>

    - <span data-ttu-id="11d42-435">Nel campo **Metodo di pagamento** seleziona **Elettronico**.</span><span class="sxs-lookup"><span data-stu-id="11d42-435">In the **Method of payment** field, select **Electronic**.</span></span>
    - <span data-ttu-id="11d42-436">Nel campo **Conto bancario** selezionare **GBSI OPER**.</span><span class="sxs-lookup"><span data-stu-id="11d42-436">In the **Bank account** field, select **GBSI OPER**.</span></span>

7. <span data-ttu-id="11d42-437">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="11d42-437">Select **OK**.</span></span>
8. <span data-ttu-id="11d42-438">Nella finestra di dialogo **Parametri per la creazione di report elettronici** immetti le seguenti informazioni:</span><span class="sxs-lookup"><span data-stu-id="11d42-438">In the **Electronic report parameters** dialog box, enter the following information:</span></span>

    - <span data-ttu-id="11d42-439">Impostare l'opzione **Stampa report controllo** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="11d42-439">Set the **Print control report** option to **Yes**.</span></span>
    - <span data-ttu-id="11d42-440">Imposta l'opzione **Stampa avviso di pagamento** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="11d42-440">Set the **Print payment advice** option to **Yes**.</span></span>

    ![Finestra di dialogo Parametri per la creazione di report elettronici](./media/er-quick-start2-payment-dialog2.png)

    > [!NOTE]
    > <span data-ttu-id="11d42-442">Oltre al file di pagamento, è ora possibile generare sia il report di controllo sia il report dell'avviso di pagamento.</span><span class="sxs-lookup"><span data-stu-id="11d42-442">In addition to the payment file, you can now generate both the control report and the payment advice report.</span></span>

9. <span data-ttu-id="11d42-443">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="11d42-443">Select **OK**.</span></span>
10. <span data-ttu-id="11d42-444">Scarica il file zip, quindi estrai i seguenti file:</span><span class="sxs-lookup"><span data-stu-id="11d42-444">Download the zip file, and then extract the following files from it:</span></span>

    - <span data-ttu-id="11d42-445">Il report di controllo in formato Excel</span><span class="sxs-lookup"><span data-stu-id="11d42-445">The control report in Excel format</span></span>
    - <span data-ttu-id="11d42-446">Il report di avviso di pagamento in formato Excel</span><span class="sxs-lookup"><span data-stu-id="11d42-446">The payment advice report in Excel format</span></span>

        ![Report di avviso di pagamento in formato Excel](./media/er-quick-start2-payment-advice-report.png)

    - <span data-ttu-id="11d42-448">Il file di pagamento in formato TXT</span><span class="sxs-lookup"><span data-stu-id="11d42-448">The payment file in TXT format</span></span>

        <span data-ttu-id="11d42-449">Si noti che la riga di pagamento nel file generato ora inizia con il codice SWIFT immesso per il conto bancario del fornitore il cui pagamento è stato elaborato.</span><span class="sxs-lookup"><span data-stu-id="11d42-449">Notice that the payment line in the generated file starts  with the SWIFT code that was entered for the bank account of a vendor whose payment has been processed.</span></span>

        ![File di pagamento in formato TXT](./media/er-quick-start2-payment-file3.png)

## <a name="additional-resources"></a><a id="References"></a><span data-ttu-id="11d42-451">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="11d42-451">Additional resources</span></span>

- [<span data-ttu-id="11d42-452">Panoramica sui report elettronici</span><span class="sxs-lookup"><span data-stu-id="11d42-452">Electronic Reporting overview</span></span>](general-electronic-reporting.md)
- [<span data-ttu-id="11d42-453">Scaricare configurazioni ER da Lifecycle Services</span><span class="sxs-lookup"><span data-stu-id="11d42-453">Download ER configurations from Lifecycle Services</span></span>](download-electronic-reporting-configuration-lcs.md)
- [<span data-ttu-id="11d42-454">Scaricare configurazioni ER dall'archivio globale del servizio di configurazione</span><span class="sxs-lookup"><span data-stu-id="11d42-454">Download ER configurations from Global repository of Configuration service</span></span>](er-download-configurations-global-repo.md)
