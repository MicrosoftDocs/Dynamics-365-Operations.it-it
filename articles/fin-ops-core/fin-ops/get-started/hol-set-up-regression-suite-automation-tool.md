---
title: Esercitazione sull'impostazione e l'installazione di Regression Suite Automation Tool
description: Questo argomento è un'esercitazione in cui viene illustrato come impostare e installare lo strumento Regression Suite Automation Tool (RSAT).
author: robinarh
manager: AnnBe
ms.date: 09/20/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ROBOTS: NOINDEX, NOFOLLOW
audience: Application User, Developer, IT Pro
ms.reviewer: rhaertle
ms.custom: 21761, NotInToc
ms.search.region: Global
ms.author: rhaertle
ms.search.validFrom: 2019-05-30
ms.dyn365.ops.version: AX 7.0.0, Operations
ms.openlocfilehash: 4757d506239e309dcbc3e181469b17e3286cc111
ms.sourcegitcommit: f5e31c34640add6d40308ac1365cc0ee60e60e24
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/08/2020
ms.locfileid: "4695117"
---
# <a name="set-up-and-install-regression-suite-automation-tool-tutorial"></a><span data-ttu-id="553cf-103">Esercitazione sull'impostazione e l'installazione di Regression Suite Automation Tool</span><span class="sxs-lookup"><span data-stu-id="553cf-103">Set up and install Regression suite automation tool tutorial</span></span>
<span data-ttu-id="553cf-104">Questo argomento è un'esercitazione che consente di iniziare a utilizzare RSAT e gli strumenti ad esso associati.</span><span class="sxs-lookup"><span data-stu-id="553cf-104">This topic is a tutorial that helps you get setup and get started with RSAT and the tools associated with using RSAT.</span></span> 

[!include [banner](../includes/banner.md)]

> [!NOTE]
> <span data-ttu-id="553cf-105">Utilizzare gli strumenti del browser Internet per scaricare e salvare questa pagina in formato PDF.</span><span class="sxs-lookup"><span data-stu-id="553cf-105">Use your internet browser tools to download and save this page in PDF format.</span></span> 

## <a name="key-concepts"></a><span data-ttu-id="553cf-106">Concetti chiave</span><span class="sxs-lookup"><span data-stu-id="553cf-106">Key concepts</span></span>

- <span data-ttu-id="553cf-107">Comprendere i prerequisiti di impostazione e installazione necessari per le varie applicazioni che supportano lo strumento Regression Suite Automation Tool (RSAT).</span><span class="sxs-lookup"><span data-stu-id="553cf-107">Understand the installation and prerequisite setup that are required for the various applications that support Regression suite automation tool (RSAT).</span></span>
- <span data-ttu-id="553cf-108">Comprendere il modo in cui la funzionalità Registrazione attività in , insieme a Microsoft Dynamics Lifecycle Services (LCS) e Microsoft Azure DevOps, consente di creare, configurare, eseguire e analizzare test case nonché generare report sugli stessi.</span><span class="sxs-lookup"><span data-stu-id="553cf-108">Understand how the Task recorder feature, together with Microsoft Dynamics Lifecycle Services (LCS) and Microsoft Azure DevOps, let you create, configure, run, investigate, and report on test cases.</span></span>
- <span data-ttu-id="553cf-109">Consentire agli utenti funzionali di registrare attività aziendali utilizzando Registrazione attività e quindi convertire le registrazioni attività in un gruppo di test automatici, senza dover scrivere codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="553cf-109">Empower functional users to record business tasks by using Task recorder, and then convert the task recordings into a suite of automated tests, without having to write source code.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="553cf-110">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="553cf-110">Before you begin</span></span>

### <a name="prerequisites"></a><span data-ttu-id="553cf-111">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="553cf-111">Prerequisites</span></span>

- <span data-ttu-id="553cf-112">Un ambiente in cui viene eseguito Microsoft Dynamics 365 for Finance and Operations versione 10.0 (aprile 2019) o versione successiva è necessario per questa esercitazione.</span><span class="sxs-lookup"><span data-stu-id="553cf-112">An environment that runs Microsoft Dynamics 365 for Finance and Operations version 10.0 (April 2019) or later is required for this tutorial.</span></span> <span data-ttu-id="553cf-113">Per i clienti che utilizzano Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition 7.3, è supportato anche l'aggiornamento 20 della piattaforma (PU20) o un aggiornamento successivo.</span><span class="sxs-lookup"><span data-stu-id="553cf-113">For customers who are using Microsoft Dynamics 365 for Finance and Operations, Enterprise edition 7.3, Platform update 20 (PU20) or later is also supported.</span></span>
- <span data-ttu-id="553cf-114">L'utente deve disporre dei diritti di amministratore per l'ambiente.</span><span class="sxs-lookup"><span data-stu-id="553cf-114">The user must have admin rights to the environment.</span></span>
- <span data-ttu-id="553cf-115">È necessario avere accesso ai servizi LCS del tenant del cliente e ad Azure DevOps (in precedenza noto come Microsoft Visual Studio Team Services\[VSTS\]).</span><span class="sxs-lookup"><span data-stu-id="553cf-115">You must have access to the customer tenant LCS and Azure DevOps (previously known as Microsoft Visual Studio Team Services \[VSTS\]).</span></span>
- <span data-ttu-id="553cf-116">L'utente che crea e gestisce i gruppi di test deve disporre della licenza per Test manager o i piani di test di Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="553cf-116">The user that is creating and managing tests suites must have an Azure DevOps Test Plans or Test Manager license.</span></span> <span data-ttu-id="553cf-117">Anche le seguenti licenze forniranno accesso ai piani di test:</span><span class="sxs-lookup"><span data-stu-id="553cf-117">The following licenses will also give you access to Test Plans:</span></span>
    - <span data-ttu-id="553cf-118">Licenza di Visual Studio Enterprise</span><span class="sxs-lookup"><span data-stu-id="553cf-118">Visual Studio Enterprise license</span></span>
    - <span data-ttu-id="553cf-119">Licenza di Visual Studio Test Professional</span><span class="sxs-lookup"><span data-stu-id="553cf-119">Visual Studio Test Professional license</span></span>
    - <span data-ttu-id="553cf-120">Licenza dei sottoscrittori di MSDN Platforms</span><span class="sxs-lookup"><span data-stu-id="553cf-120">MSDN Platforms subscriber license</span></span>
- <span data-ttu-id="553cf-121">RSAT deve avere accesso all'ambiente di test tramite un Web browser.</span><span class="sxs-lookup"><span data-stu-id="553cf-121">RSAT must have access to the test environment via a web browser.</span></span>
- <span data-ttu-id="553cf-122">Per generare e modificare i parametri di test, è necessario che Microsoft Excel sia installato.</span><span class="sxs-lookup"><span data-stu-id="553cf-122">To generate and edit test parameters, you must have Microsoft Excel installed.</span></span>

## <a name="configure-azure-devops"></a><span data-ttu-id="553cf-123">Configura Azure DevOps</span><span class="sxs-lookup"><span data-stu-id="553cf-123">Configure Azure DevOps</span></span>

### <a name="user-eligibility"></a><span data-ttu-id="553cf-124">Idoneità dell'utente</span><span class="sxs-lookup"><span data-stu-id="553cf-124">User eligibility</span></span>

<span data-ttu-id="553cf-125">Assicurarsi che l'utente sia creato in Azure DevOps e che disponga di un livello di sottoscrizione che fornisce accesso ai piani di test di Azure.</span><span class="sxs-lookup"><span data-stu-id="553cf-125">Make sure that the user is created in Azure DevOps and has a subscription level that provides access to Azure Test Plans.</span></span> <span data-ttu-id="553cf-126">Una licenza dei piani di test di Azure DevOps è necessaria solo se l'utente creerà e gestirà test case (ovvero, non tutti gli utenti RSAT necessitano questa licenza).</span><span class="sxs-lookup"><span data-stu-id="553cf-126">An Azure DevOps Test Plans license is required only if the user will create and manage test cases (that is, not all RSAT users require this license).</span></span> <span data-ttu-id="553cf-127">Per informazioni sui requisiti di licenza, vedere [Requisiti di licenza](https://docs.microsoft.com/azure/devops/test/manual-test-permissions#license-requirements).</span><span class="sxs-lookup"><span data-stu-id="553cf-127">For information about the license requirements, see [License requirements](https://docs.microsoft.com/azure/devops/test/manual-test-permissions#license-requirements).</span></span>

### <a name="create-a-new-azure-devops-project"></a><span data-ttu-id="553cf-128">Creare un nuovo progetto Azure DevOps</span><span class="sxs-lookup"><span data-stu-id="553cf-128">Create a new Azure DevOps project</span></span>
<span data-ttu-id="553cf-129">RSAT utilizza Azure Devops per la gestione di test case e gruppi di test, la creazione di report e l'analisi dei risultati dell'esecuzione dei test.</span><span class="sxs-lookup"><span data-stu-id="553cf-129">RSAT uses Azure Devops for test case and test suite management, reporting, and investigating test run results.</span></span> 

> [!NOTE]
> <span data-ttu-id="553cf-130">È possibile utilizzare un progetto Azure DevOps esistente.</span><span class="sxs-lookup"><span data-stu-id="553cf-130">You can use an existing Azure DevOps project.</span></span> <span data-ttu-id="553cf-131">Tuttavia, se il progetto Azure DevOps esistente è impostato in modo da avere un modello personalizzato, verrà visualizzato un messaggio "Errore di sincronizzazione VSTS" quando si sincronizzano i test case da Modellatore di processi aziendali (BPM) a Azure DevOps (vedere la sezione [Testare la sincronizzazione da BPM a Azure DevOps](#test-the-synchronization-from-bpm-to-azure-devops)).</span><span class="sxs-lookup"><span data-stu-id="553cf-131">However, if your existing Azure DevOps project is set up so that it has a custom template, you will receive a "VSTS Sync Failure" error when you sync test cases from Business process modeler (BPM) to Azure DevOps (see the [Test the synchronization from BPM to Azure DevOps](#test-the-synchronization-from-bpm-to-azure-devops) section).</span></span> <span data-ttu-id="553cf-132">Se le seguenti procedure consigliate sono state seguite per il modello personalizzato, sarà possibile sincronizzare i test case ad Azure DevOps</span><span class="sxs-lookup"><span data-stu-id="553cf-132">If the following best practices have been followed for the custom template, you will be able to sync the test cases to Azure DevOps.</span></span> <span data-ttu-id="553cf-133">(queste procedure consigliate sono elencate nel messaggio di errore).</span><span class="sxs-lookup"><span data-stu-id="553cf-133">(These best practices are listed in the error message.)</span></span>

- <span data-ttu-id="553cf-134">Non eliminare i tipi di elementi di lavoro o i campi predefiniti.</span><span class="sxs-lookup"><span data-stu-id="553cf-134">Do not delete any work item types or out-of-the-box fields.</span></span>
- <span data-ttu-id="553cf-135">Non eliminare alcun stato di un tipo di elemento di lavoro.</span><span class="sxs-lookup"><span data-stu-id="553cf-135">Do not delete any state of a work item type.</span></span>
- <span data-ttu-id="553cf-136">Non aggiungere alcun campo richiesto a un tipo di elemento di lavoro.</span><span class="sxs-lookup"><span data-stu-id="553cf-136">Do not add any required fields to a work item type.</span></span>

![Messaggio di errore con un elenco di procedure consigliate](./media/setup_rsa_tool_02.png)

<span data-ttu-id="553cf-138">In caso contrario, per questa esercitazione, si consiglia di creare un nuovo progetto Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="553cf-138">Otherwise, for this tutorial, we recommend that you create a new Azure DevOps project.</span></span> <span data-ttu-id="553cf-139">Per ulteriori informazioni, vedere [Problemi durante la sincronizzazione a BPM utilizzando un modello di elaborazione Azure DevOps (VSTS) personalizzato](https://blogs.msdn.microsoft.com/lcs/2018/11/28/issues-when-syncing-to-bpm-using-a-custom-azure-devops-vsts-process-template/).</span><span class="sxs-lookup"><span data-stu-id="553cf-139">For more information, see [Issues when syncing to BPM using a custom Azure DevOps (VSTS) process template](https://blogs.msdn.microsoft.com/lcs/2018/11/28/issues-when-syncing-to-bpm-using-a-custom-azure-devops-vsts-process-template/).</span></span>

1. <span data-ttu-id="553cf-140">Aprire l'URL di Azure DevOps (`https://dev.azure.com/<Azure DevOps Name>`).</span><span class="sxs-lookup"><span data-stu-id="553cf-140">Open the Azure DevOps URL (`https://dev.azure.com/<Azure DevOps Name>`).</span></span>
2. <span data-ttu-id="553cf-141">Selezionare **Crea progetto** nell'angolo superiore destro della pagina Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="553cf-141">Select **Create project** in the upper-right corner of the Azure DevOps page.</span></span>

    ![Pulsante Crea budget](./media/setup_rsa_tool_03.png)

3. <span data-ttu-id="553cf-143">Completare i seguenti campi, quindi selezionare **Crea**:</span><span class="sxs-lookup"><span data-stu-id="553cf-143">Fill in the following fields, and then select **Create**:</span></span>

    - <span data-ttu-id="553cf-144">**Nome progetto**</span><span class="sxs-lookup"><span data-stu-id="553cf-144">**Project name**</span></span>
    - <span data-ttu-id="553cf-145">**Controllo versione** - Selezionare **Controllo della versione di Team Foundation**.</span><span class="sxs-lookup"><span data-stu-id="553cf-145">**Version control** – Select **Team Foundation Version Control**.</span></span> <span data-ttu-id="553cf-146">Da notare che l'opzione predefinita, **Git**, non è supportata.</span><span class="sxs-lookup"><span data-stu-id="553cf-146">Note that the default option, **Git**, isn't supported.</span></span>
    - <span data-ttu-id="553cf-147">**Processo di elemento di lavoro**</span><span class="sxs-lookup"><span data-stu-id="553cf-147">**Work item process**</span></span>

    ![Finestra di dialogo Crea nuovo progetto](./media/setup_rsa_tool_04.png)

### <a name="create-a-personal-access-token"></a><span data-ttu-id="553cf-149">Creare un token di accesso personale</span><span class="sxs-lookup"><span data-stu-id="553cf-149">Create a personal access token</span></span>

<span data-ttu-id="553cf-150">In questa esercitazione, si utilizzerà il Modellatore di processi aziendali (BPM) LCS per creare una libreria di test case e sincronizzare i propri test case con Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="553cf-150">In this tutorial, you will use the LCS Business Process Modeler (BPM) to create a test case library and synchronize your test cases with Azure DevOps.</span></span> <span data-ttu-id="553cf-151">Sarà necessario un token di accesso personale per sincronizzare BPM con Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="553cf-151">You will need a personal access token to sync BPM with Azure DevOps.</span></span>

1. <span data-ttu-id="553cf-152">Selezionare l'icona del profilo nell'angolo superiore destro della pagina per il progetto Azure DevOps e quindi selezionare **Sicurezza**.</span><span class="sxs-lookup"><span data-stu-id="553cf-152">Select the profile icon in the upper-right corner of the page for your Azure DevOps project, and then select **Security**.</span></span>

    ![Comando Sicurezza](./media/setup_rsa_tool_05.png)

2. <span data-ttu-id="553cf-154">Nel riquadro sinistro, sotto **Sicurezza**, selezionare **Token di accesso personali**.</span><span class="sxs-lookup"><span data-stu-id="553cf-154">In the left pane, under **Security**, select **Personal access tokens**.</span></span> <span data-ttu-id="553cf-155">Selezionare quindi **Nuovo token**.</span><span class="sxs-lookup"><span data-stu-id="553cf-155">Then select **New Token**.</span></span>

    ![Pulsante Nuovo token nella scheda Token di accesso personali in Impostazioni utente](./media/setup_rsa_tool_06.png)

3. <span data-ttu-id="553cf-157">Completare i seguenti campi, quindi selezionare **Crea**:</span><span class="sxs-lookup"><span data-stu-id="553cf-157">Fill in the following fields, and then select **Create**:</span></span>

    - <span data-ttu-id="553cf-158">**Nome**</span><span class="sxs-lookup"><span data-stu-id="553cf-158">**Name**</span></span>
    - <span data-ttu-id="553cf-159">**Scadenza (UTC)** - Selezionare **Definizione personalizzata** quindi utilizzare Selezione data per selezionare l'ultima data disponibile.</span><span class="sxs-lookup"><span data-stu-id="553cf-159">**Expiration (UTC)** – Select **Custom defined**, and then use the date picker to select the last available date.</span></span>
    - <span data-ttu-id="553cf-160">**Ambiti** - Selezionare l'opzione **Accesso completo**.</span><span class="sxs-lookup"><span data-stu-id="553cf-160">**Scopes** – Select the **Full access** option.</span></span>

    ![Finestra di dialogo Creare un nuovo token di accesso personale](./media/setup_rsa_tool_07.png)

    > [!NOTE]
    > <span data-ttu-id="553cf-162">Annotare il token di accesso personale creato.</span><span class="sxs-lookup"><span data-stu-id="553cf-162">Make a note of the personal access token that is created.</span></span> <span data-ttu-id="553cf-163">Questo token sarà necessario quando si imposta la configurazione RSAT.</span><span class="sxs-lookup"><span data-stu-id="553cf-163">You will need it later when you set up the RSAT configuration.</span></span>

    ![Token di accesso personale](./media/setup_rsa_tool_08.png)

## <a name="configure-the-lcs-project"></a><span data-ttu-id="553cf-165">Configurare il progetto LCS</span><span class="sxs-lookup"><span data-stu-id="553cf-165">Configure the LCS project</span></span>

<span data-ttu-id="553cf-166">È necessario un progetto Lifecycle Services (LCS) per la libreria di test principale.</span><span class="sxs-lookup"><span data-stu-id="553cf-166">You need a Lifecycle Services (LCS) project for your master test library.</span></span> <span data-ttu-id="553cf-167">Il Modellatore di processi aziendali (BPM) LCS viene utilizzato come libreria principale per i test case.</span><span class="sxs-lookup"><span data-stu-id="553cf-167">The LCS Business Process Modeler (BPM) is used as the master library for your test cases.</span></span> <span data-ttu-id="553cf-168">BPM è utilizzato per gestire e distribuire le librerie di test nei progetti LCS.</span><span class="sxs-lookup"><span data-stu-id="553cf-168">BPM is used to manage and distribute test libraries across LCS projects.</span></span> <span data-ttu-id="553cf-169">Ad esempio, un partner Microsoft o un fornitore di software indipendente (ISV) che crea librerie di test rilascerà test case sotto forma di librerie BPM.</span><span class="sxs-lookup"><span data-stu-id="553cf-169">For example, a Microsoft partner or independent software vendor (ISV) building test libraries will release test cases in the form of BPM libraries.</span></span> <span data-ttu-id="553cf-170">In BPM, i test case sono organizzati per processo aziendale.</span><span class="sxs-lookup"><span data-stu-id="553cf-170">In BPM, test cases are organized by business process.</span></span> <span data-ttu-id="553cf-171">BPM non definisce l'ordine di esecuzione o la frequenza del passaggio dei test.</span><span class="sxs-lookup"><span data-stu-id="553cf-171">BPM doesn't define the execution order or frequency of your test pass.</span></span> <span data-ttu-id="553cf-172">Queste informazioni sono gestite in Azure DevOps, come descritto nelle sezioni successive di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="553cf-172">These details are managed in Azure DevOps, as described later in this topic.</span></span>  

<span data-ttu-id="553cf-173">Per il progetto LC, è possibile utilizzare un progetto partner o di implementazione cliente esistente.</span><span class="sxs-lookup"><span data-stu-id="553cf-173">For your LCS project, you can use an existing customer implementation or partner project.</span></span>

### <a name="update-the-lcs-language"></a><span data-ttu-id="553cf-174">Aggiornare la lingua LCS</span><span class="sxs-lookup"><span data-stu-id="553cf-174">Update the LCS language</span></span>

> [!NOTE]
> <span data-ttu-id="553cf-175">Per visualizzare correttamente i processi aziendali nell'interfaccia utente, la lingua LCS preferita deve essere **Inglese (Stati Uniti)**.</span><span class="sxs-lookup"><span data-stu-id="553cf-175">For the user interface (UI) to correctly show business processes, the LCS preferred language must be set to **English (United States)**.</span></span>

1. <span data-ttu-id="553cf-176">Accedere al progetto di implementazione LCS.</span><span class="sxs-lookup"><span data-stu-id="553cf-176">Go to the LCS implementation project.</span></span>
2. <span data-ttu-id="553cf-177">Selezionare il pulsante **Impostazioni** (il simbolo dell'ingranaggio) nell'angolo superiore destro, quindi selezionare **Preferenza lingua**.</span><span class="sxs-lookup"><span data-stu-id="553cf-177">Select the **Settings** button (the gear symbol) in the upper-right corner, and then select **Language preference**.</span></span>

    ![Comandi del menu Impostazioni](./media/setup_rsa_tool_09.png)

3. <span data-ttu-id="553cf-179">Nel campo **Lingua preferita** selezionare **Inglese (Stati Uniti)** e quindi **Salva**.</span><span class="sxs-lookup"><span data-stu-id="553cf-179">In the **Preferred language** field, select **English (United States)**, and then select **Save**.</span></span>

    ![Scheda Preferenza lingua in Impostazioni utente](./media/setup_rsa_tool_10.png)

### <a name="configure-lcs-to-connect-to-the-azure-devops-project"></a><span data-ttu-id="553cf-181">Configurare LCS per la connessione al progetto Azure DevOps</span><span class="sxs-lookup"><span data-stu-id="553cf-181">Configure LCS to connect to the Azure DevOps project</span></span>

<span data-ttu-id="553cf-182">Se in precedenza è stato creato un nuovo progetto Azure DevOps, configurare il progetto LCS per eseguire la connessione allo stesso.</span><span class="sxs-lookup"><span data-stu-id="553cf-182">If you created a new Azure DevOps project earlier, configure the LCS project to connect to it.</span></span> <span data-ttu-id="553cf-183">Se il progetto LCS è già connesso al progetto Azure DevOps, è possibile passare alla sezione successiva.</span><span class="sxs-lookup"><span data-stu-id="553cf-183">Otherwise, if your LCS project is already connected to your Azure DevOps project, you can continue to the next section.</span></span>

1. <span data-ttu-id="553cf-184">Accedere al progetto di implementazione LCS.</span><span class="sxs-lookup"><span data-stu-id="553cf-184">Go to the LCS implementation project.</span></span>
2. <span data-ttu-id="553cf-185">Selezionare il pulsante **Menu** e quindi selezionare **Impostazioni progetto**.</span><span class="sxs-lookup"><span data-stu-id="553cf-185">Select the **Menu** button, and then select **Project settings**.</span></span>

    ![Comando Impostazioni progetto](./media/setup_rsa_tool_11.png)

3. <span data-ttu-id="553cf-187">Nel riquadro sinistro, selezionare **Visual Studio Team Services**, quindi selezionare **Imposta Visual Studio Team Services**.</span><span class="sxs-lookup"><span data-stu-id="553cf-187">In the left pane, select **Visual Studio Team Services**, and then select **Setup Visual Studio Team Services**.</span></span>

    ![Scheda Visual Studio Team Services in Impostazioni progetto](./media/setup_rsa_tool_12.png)

4. <span data-ttu-id="553cf-189">Nel campo **URL sito Azure DevOps** immettere l'URL del sito Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="553cf-189">In the **Azure DevOps site URL** field, enter the URL of the Azure DevOps site.</span></span> <span data-ttu-id="553cf-190">Nel campo **Token di accesso personale**, immettere il token di accesso personale creato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="553cf-190">In the **Personal access token** field, enter the personal access token that was created earlier.</span></span>

    > [!NOTE]
    > <span data-ttu-id="553cf-191">Sebbene VSTS sia ora denominato Azure DevOps, per connettere LCS al progetto Azure DevOps, utilizzare il vecchio URL.</span><span class="sxs-lookup"><span data-stu-id="553cf-191">Although VSTS is now known as Azure DevOps, to connect LCS to your Azure DevOps project, use the old URL.</span></span> <span data-ttu-id="553cf-192">Ad esempio, l'URL di Azure DevOps utilizzato in questa esercitazione è `https://dev.azure.com/D365FOFastTrack/`.</span><span class="sxs-lookup"><span data-stu-id="553cf-192">For example, the Azure DevOps URL that is used in this tutorial is `https://dev.azure.com/D365FOFastTrack/`.</span></span> <span data-ttu-id="553cf-193">Tuttavia, nella figura seguente, è `https://D365FOFastTrack.visualstudio.com/`.</span><span class="sxs-lookup"><span data-stu-id="553cf-193">However, in the following illustration, it's entered as `https://D365FOFastTrack.visualstudio.com/`.</span></span>

    ![Passaggio 1 in Imposta Visual Studio Team Services](./media/setup_rsa_tool_13.png)

5. <span data-ttu-id="553cf-195">Selezionare **Continua**.</span><span class="sxs-lookup"><span data-stu-id="553cf-195">Select **Continue**.</span></span>
6. <span data-ttu-id="553cf-196">Nel campo **Progetto Visual Studio Team Services**, selezionare il progetto VSTS sul sito selezionato per eseguire il collegamento al progetto LCS.</span><span class="sxs-lookup"><span data-stu-id="553cf-196">In the **Visual Studio Team Services project** field, select the VSTS project on the selected site to link with the LCS project.</span></span> <span data-ttu-id="553cf-197">Per impostazione predefinita, il campo **Modello di processo** è impostato su **Agilità**.</span><span class="sxs-lookup"><span data-stu-id="553cf-197">The **Process template** field is set to **Agile** by default.</span></span> <span data-ttu-id="553cf-198">Per un modello predefinito, esaminare le Linee guida per le procedure consigliate nella sezione [Creare un nuovo progetto Azure DevOps](#create-a-new-azure-devops-project).</span><span class="sxs-lookup"><span data-stu-id="553cf-198">For a custom template, review the best practice guidance in the [Create a new Azure DevOps project](#create-a-new-azure-devops-project) section.</span></span> <span data-ttu-id="553cf-199">Quindi selezionare **Continua**.</span><span class="sxs-lookup"><span data-stu-id="553cf-199">Then select **Continue**.</span></span>

    ![Passaggio 2 in Imposta Visual Studio Team Services](./media/setup_rsa_tool_14.png)

7. <span data-ttu-id="553cf-201">Esaminare le impostazioni e quindi selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="553cf-201">Review your settings, and then select **Save**.</span></span>

    ![Passaggio 3 in Imposta Visual Studio Team Services](./media/setup_rsa_tool_15.png)

8. <span data-ttu-id="553cf-203">Selezionare **Autorizza** per autorizzare LCS ad accedere al sito Azure DevOps configurato per conto dell'utente e per attivare le funzionalità che si integrano con VSTS.</span><span class="sxs-lookup"><span data-stu-id="553cf-203">Select **Authorize** to authorize LCS to access the configured Azure DevOps site on your behalf and to turn on features that integrate with VSTS.</span></span>

    ![Pulsante Autorizza](./media/setup_rsa_tool_16.png)

9. <span data-ttu-id="553cf-205">Viene visualizzato il messaggio "Si sta per essere reindirizzati a un sito esterno per autorizzare LCS a connettersi a Visual Studio Team Services per conto dell'utente.</span><span class="sxs-lookup"><span data-stu-id="553cf-205">A message box appears that states, "You are about to be redirected to an eternal site to authorize LCS to connect to Visual Studio Team Services on your behalf.</span></span> <span data-ttu-id="553cf-206">Continuare?"</span><span class="sxs-lookup"><span data-stu-id="553cf-206">Proceed?"</span></span> <span data-ttu-id="553cf-207">Selezionare **Sì**.</span><span class="sxs-lookup"><span data-stu-id="553cf-207">Select **Yes**.</span></span>

    ![Finestra di messaggio](./media/setup_rsa_tool_17.png)

10. <span data-ttu-id="553cf-209">Selezionare **Accetta**.</span><span class="sxs-lookup"><span data-stu-id="553cf-209">Select **Accept**.</span></span>

    ![Autorizzare l'accesso](./media/setup_rsa_tool_18.png)

11. <span data-ttu-id="553cf-211">Se si è autorizzati come utente, viene visualizzata di nuovo la pagina delle impostazioni del progetto LCS.</span><span class="sxs-lookup"><span data-stu-id="553cf-211">If you're authorized as a user, the UI should you return to the LCS project settings page.</span></span>

    ![Utente autorizzato](./media/setup_rsa_tool_19.png)

### <a name="create-a-new-bpm-library"></a><span data-ttu-id="553cf-213">Creare nuova libreria BPM</span><span class="sxs-lookup"><span data-stu-id="553cf-213">Create a new BPM library</span></span>

1. <span data-ttu-id="553cf-214">Accedere al progetto di implementazione LCS.</span><span class="sxs-lookup"><span data-stu-id="553cf-214">Go to the LCS implementation project.</span></span>
2. <span data-ttu-id="553cf-215">Selezionare il pulsante **Menu** e quindi selezionare **Modellatore di processi aziendali**.</span><span class="sxs-lookup"><span data-stu-id="553cf-215">Select the **Menu** button, and then select **Business process modeler**.</span></span>

    ![Comando Modellatore di processi aziendali](./media/setup_rsa_tool_20.png)

3. <span data-ttu-id="553cf-217">Selezionare **Nuova libreria**.</span><span class="sxs-lookup"><span data-stu-id="553cf-217">Select **New library**.</span></span>

    ![Pulsante Nuova libreria](./media/setup_rsa_tool_21.png)

4. <span data-ttu-id="553cf-219">Nel campo **Nome libreria**, immettere un nome e selezionare **Crea**.</span><span class="sxs-lookup"><span data-stu-id="553cf-219">In the **Library name** field, enter a name, and then select **Create**.</span></span> <span data-ttu-id="553cf-220">Per questa esercitazione, denominare la libreria BPM **RSAT**.</span><span class="sxs-lookup"><span data-stu-id="553cf-220">For this tutorial, name the BPM library **RSAT**.</span></span>

    ![Finestra di dialogo Crea nuova libreria](./media/setup_rsa_tool_22.png)

5. <span data-ttu-id="553cf-222">Aprire la nuova raccolta libreria BPM **RSAT**.</span><span class="sxs-lookup"><span data-stu-id="553cf-222">Open the new **RSAT** BPM library.</span></span>
6. <span data-ttu-id="553cf-223">Selezionare **Processo aziendale di base di esempio**, quindi a destra, selezionare **Modalità di modifica**.</span><span class="sxs-lookup"><span data-stu-id="553cf-223">Select the **Sample Core Business Process** process, and then, on the right, select **Edit mode**.</span></span>

    ![Pulsante Modalità di modifica](./media/setup_rsa_tool_23.png)

7. <span data-ttu-id="553cf-225">Modificare il valore dei campi **Nome** e **Descrizione** per **creare un prodotto**.</span><span class="sxs-lookup"><span data-stu-id="553cf-225">Change the value of both the **Name** field and the **Description** field to **Create a product**.</span></span> <span data-ttu-id="553cf-226">Quindi selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="553cf-226">Then select **Save**.</span></span>

    ![Campi Nome e Descrizione](./media/setup_rsa_tool_24.png)

## <a name="environment"></a><span data-ttu-id="553cf-228">Ambiente</span><span class="sxs-lookup"><span data-stu-id="553cf-228">Environment</span></span>

### <a name="version-requirement"></a><span data-ttu-id="553cf-229">Requisiti di versione</span><span class="sxs-lookup"><span data-stu-id="553cf-229">Version requirement</span></span>

<span data-ttu-id="553cf-230">È necessario un ambiente di test o sandbox in cui viene eseguita la versione 10.</span><span class="sxs-lookup"><span data-stu-id="553cf-230">A test or sandbox environment that runs version 10 is required.</span></span> <span data-ttu-id="553cf-231">Per i clienti che utilizzano la versione 7.3, è supportato anche l'update 20 della piattaforma o un update successivo.</span><span class="sxs-lookup"><span data-stu-id="553cf-231">For customers that are using version 7.3, Platform update 20 or later is also supported.</span></span>

> [!NOTE]
> <span data-ttu-id="553cf-232">RSAT deve avere accesso all'ambiente di test tramite un Web browser.</span><span class="sxs-lookup"><span data-stu-id="553cf-232">RSAT must have access to your test environment via a web browser.</span></span>

### <a name="user-criteria"></a><span data-ttu-id="553cf-233">Criteri utente</span><span class="sxs-lookup"><span data-stu-id="553cf-233">User criteria</span></span>

<span data-ttu-id="553cf-234">L'utente deve disporre dei diritti di amministratore per questo ambiente.</span><span class="sxs-lookup"><span data-stu-id="553cf-234">The user must have admin rights to this environment.</span></span>

### <a name="set-up-help-settings-to-connect-with-lcs"></a><span data-ttu-id="553cf-235">Configurare le impostazioni della Guida per connettersi a LCS</span><span class="sxs-lookup"><span data-stu-id="553cf-235">Set up Help settings to connect with LCS</span></span>

<span data-ttu-id="553cf-236">Questo passaggio è necessario per eseguire la connessione a LCS di modo che le registrazioni attività possano essere salvate nella libreria BPM appropriata in LCS tramite il client.</span><span class="sxs-lookup"><span data-stu-id="553cf-236">This step is required in order to connect with LCS so that task recordings can be saved to the appropriate BPM library in LCS through the client.</span></span>

1. <span data-ttu-id="553cf-237">Avviare il client.</span><span class="sxs-lookup"><span data-stu-id="553cf-237">Open the client.</span></span>
2. <span data-ttu-id="553cf-238">Passare ad **Amministrazione sistema \> Impostazioni \> Parametri di sistema**.</span><span class="sxs-lookup"><span data-stu-id="553cf-238">Go to **System Administration \> Setup \> System parameters**.</span></span>
3. <span data-ttu-id="553cf-239">Nella scheda **Guida**, nel campo **Configurazione Guida di Lifecycle Services**, selezionare il progetto LCS pertinente (**RSAT** per questa esercitazione).</span><span class="sxs-lookup"><span data-stu-id="553cf-239">On the **Help** tab, in the **Lifecycle Services help configuration** field, select the relevant LCS project (**RSAT** for this tutorial).</span></span>

    ![Campo Configurazione Guida di Lifecycle Services nella scheda Guida](./media/setup_rsa_tool_25.png)

    <span data-ttu-id="553cf-241">Le librerie BPM vengono inserite nel progetto LCS appropriato.</span><span class="sxs-lookup"><span data-stu-id="553cf-241">BPM libraries are filled in under the appropriate LCS project.</span></span>

4. <span data-ttu-id="553cf-242">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="553cf-242">Select **Save**.</span></span>
5. <span data-ttu-id="553cf-243">È possibile che sia necessario aggiornare il browser per visualizzare il contenuto della Guida aggiornato.</span><span class="sxs-lookup"><span data-stu-id="553cf-243">You might have to refresh the browser to see the updated Help content.</span></span>

    ![Notifica sull'aggiornamento del browser](./media/setup_rsa_tool_26.png)

## <a name="task-recordings"></a><span data-ttu-id="553cf-245">Registrazioni attività</span><span class="sxs-lookup"><span data-stu-id="553cf-245">Task recordings</span></span>

> [!NOTE]
> <span data-ttu-id="553cf-246">Verificare che tutte le registrazioni attività siano avviate del dashboard principale.</span><span class="sxs-lookup"><span data-stu-id="553cf-246">Make sure that all your task recordings start on the main dashboard.</span></span> <span data-ttu-id="553cf-247">Fare in modo che le singole registrazioni siano brevi e focalizzarsi su un'attività aziendale, ad esempio la creazione di un ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="553cf-247">Keep individual recordings short, and focus on one business task, such as creating a sales order.</span></span>

### <a name="create-a-task-recording-and-save-it-to-the-bpm-library"></a><span data-ttu-id="553cf-248">Creare una registrazione attività e salvarla nella libreria BPM</span><span class="sxs-lookup"><span data-stu-id="553cf-248">Create a task recording and save it to the BPM library</span></span>

<span data-ttu-id="553cf-249">Creare una registrazione attività corrispondente che è possibile collegare al processo aziendale semplice creato nella nuova libreria BPM.</span><span class="sxs-lookup"><span data-stu-id="553cf-249">Create a corresponding task recording that you can attach to the simple business process that was created in the new BPM library.</span></span>

1. <span data-ttu-id="553cf-250">Avviare il client.</span><span class="sxs-lookup"><span data-stu-id="553cf-250">Open the client.</span></span>
2. <span data-ttu-id="553cf-251">Nel dashboard principale, selezionare il pulsante **Impostazioni** (il simbolo di ingranaggio) e quindi **Registrazione attività**.</span><span class="sxs-lookup"><span data-stu-id="553cf-251">On the main dashboard, select the **Settings** button (the gear symbol), and then select **Task recorder**.</span></span>

    ![Comandi del menu Impostazioni](./media/setup_rsa_tool_27.png)

3. <span data-ttu-id="553cf-253">Selezionare **Crea registrazione**.</span><span class="sxs-lookup"><span data-stu-id="553cf-253">Select **Create recording**.</span></span>

    ![Pulsante Crea registrazione](./media/setup_rsa_tool_28.png)

4. <span data-ttu-id="553cf-255">Compilare i campi **Nome registrazione** e **Descrizione registrazione** e selezionare **Avvia**.</span><span class="sxs-lookup"><span data-stu-id="553cf-255">Fill in the **Recording name** and **Recording description** fields, and then select **Start**.</span></span>

    ![Campi Nome registrazione e Descrizione registrazione](./media/setup_rsa_tool_29.png)

5. <span data-ttu-id="553cf-257">Registrare i passaggi per la creazione di un prodotto.</span><span class="sxs-lookup"><span data-stu-id="553cf-257">Record the steps for creating a product.</span></span> <span data-ttu-id="553cf-258">Al termine, selezionare **Interrompi** per interrompere la registrazione.</span><span class="sxs-lookup"><span data-stu-id="553cf-258">When you've finished, select **Stop** to stop recording.</span></span>

    ![Passaggi per la creazione di un prodotto](./media/setup_rsa_tool_30.png)

6. <span data-ttu-id="553cf-260">Selezionare **Salvare in Lifecycle Services**.</span><span class="sxs-lookup"><span data-stu-id="553cf-260">Select **Save to Lifecycle Services**.</span></span>

    ![Opzioni di salvataggio](./media/setup_rsa_tool_31.png)

    <span data-ttu-id="553cf-262">Le informazioni sulla libreria vengono caricate da LCS.</span><span class="sxs-lookup"><span data-stu-id="553cf-262">Library information is loaded from LCS.</span></span>

    ![Indicatore di stato](./media/setup_rsa_tool_32.png)

7. <span data-ttu-id="553cf-264">Selezionare la libreria BPM a cui associare la registrazione attività.</span><span class="sxs-lookup"><span data-stu-id="553cf-264">Select the BPM library to associate the task recording with.</span></span> <span data-ttu-id="553cf-265">Per questa esercitazione, selezionare la libreria BPM **RSAT** creata in precedenza e il processo aziendale **Creare un prodotto** sottostante.</span><span class="sxs-lookup"><span data-stu-id="553cf-265">For this tutorial, select the **RSAT** BPM library that was created earlier and the **Create a product** business process under it.</span></span> <span data-ttu-id="553cf-266">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="553cf-266">Then select **OK**.</span></span>

    ![Associare la registrazione attività a una libreria BPM e a un processo aziendale](./media/setup_rsa_tool_33.png)

    <span data-ttu-id="553cf-268">Viene visualizzato il messaggio "Salvataggio in Lifecycle Services completato".</span><span class="sxs-lookup"><span data-stu-id="553cf-268">A "Saving to Lifecycle Services was successful" message appears.</span></span>

    ![Messaggio su un salvataggio completato in LCS](./media/setup_rsa_tool_34.png)

8. <span data-ttu-id="553cf-270">Per salvare la registrazione attività localmente e quindi aggiornarla a BPM mediante LCS, effettuare le seguenti operazioni:</span><span class="sxs-lookup"><span data-stu-id="553cf-270">If you want to save the task recording locally and then upload it to BPM through LCS, follow these steps:</span></span>

    1. <span data-ttu-id="553cf-271">Al termine della registrazione, selezionare **Salva nel PC**.</span><span class="sxs-lookup"><span data-stu-id="553cf-271">After the recording is completed, select **Save to this PC**.</span></span>

        ![Opzioni di salvataggio](./media/setup_rsa_tool_35.png)

    2. <span data-ttu-id="553cf-273">Nella barra di notifica del browser, selezionare **Salva** o **Salva con nome** per salvare il file nel computer locale.</span><span class="sxs-lookup"><span data-stu-id="553cf-273">In the browser's Notification bar, select **Save** or **Save As** to save the file on your local computer.</span></span>

        ![Barra di notifica](./media/setup_rsa_tool_36.png)

    3. <span data-ttu-id="553cf-275">Passare alla libreria BPM **RSAT** e selezionare il processo aziendale per salvare la registrazione attività.</span><span class="sxs-lookup"><span data-stu-id="553cf-275">Go to the **RSAT** BPM library, and select the business process to save the task recording against.</span></span>
    4. <span data-ttu-id="553cf-276">Nella scheda **Panoramica**, selezionare **Carica**.</span><span class="sxs-lookup"><span data-stu-id="553cf-276">On the **Overview** tab, select **Upload**.</span></span>

        ![Pulsante Carica](./media/setup_rsa_tool_37.png)

    5. <span data-ttu-id="553cf-278">Selezionare **Sfoglia** e il file .axtr salvato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="553cf-278">Select **Browse**, and select the .axtr file that you saved earlier.</span></span> <span data-ttu-id="553cf-279">Quindi selezionare **Carica**.</span><span class="sxs-lookup"><span data-stu-id="553cf-279">Then select **Upload**.</span></span>

        ![Selezione del file .axtr da caricare](./media/setup_rsa_tool_38.png)

### <a name="test-the-synchronization-from-bpm-to-azure-devops"></a><span data-ttu-id="553cf-281">Testare la sincronizzazione da BPM a Azure DevOps</span><span class="sxs-lookup"><span data-stu-id="553cf-281">Test the synchronization from BPM to Azure DevOps</span></span>

<span data-ttu-id="553cf-282">Ora che una registrazione attività è associata al processo aziendale, è necessario verificare che il processo aziendale e la registrazione attività associata possano essere sincronizzati con Azure DevOps rispettivamente come funzionalità e test case utilizzando la funzionalità di sincronizzazione VSTS in LCS.</span><span class="sxs-lookup"><span data-stu-id="553cf-282">Now that a task recording is attached to the business process, you must validate that the business process and the associated task recording can be synced to Azure DevOps as a feature and a test case (respectively) by using the VSTS sync feature in LCS.</span></span>

> [!NOTE]
> <span data-ttu-id="553cf-283">Il tipo di elemento di lavoro corrispondente creato in Azure DevOps varierà, in base al modello di processo selezionato durante la configurazione del progetto LCS con Azure DevOps, come descritto nella sezione [Creare un nuovo progetto Azure DevOps](#create-a-new-azure-devops-project).</span><span class="sxs-lookup"><span data-stu-id="553cf-283">The corresponding work item type that is created in Azure DevOps will vary, depending on the process template that you selected when you configured the LCS project with Azure DevOps, as described in the [Create a new Azure DevOps project](#create-a-new-azure-devops-project) section.</span></span>

1. <span data-ttu-id="553cf-284">Passare alla libreria BPM e aprire la libreria **RSAT** creata in precedenza.</span><span class="sxs-lookup"><span data-stu-id="553cf-284">Go to the BPM library, and open the **RSAT** library that you created earlier.</span></span>
2. <span data-ttu-id="553cf-285">Selezionare il pulsante con i puntini di sospensione (**...**) e selezionare **Sincronizzazione VSTS**.</span><span class="sxs-lookup"><span data-stu-id="553cf-285">Select the ellipsis button (**...**), and select **VSTS sync**.</span></span>

    ![Comando Sincronizzazione VSTS nel menu con i puntini di sospensione](./media/setup_rsa_tool_39.png)

    <span data-ttu-id="553cf-287">Al termine della sincronizzazione di VSTS, sul lato sinistro viene visualizzata una scheda **Requisiti** che include l'elemento di lavoro di Azure DevOps corrispondente.</span><span class="sxs-lookup"><span data-stu-id="553cf-287">After VSTS sync is completed, a **Requirements** tab appears on the left side and includes the corresponding Azure DevOps work item.</span></span>

    > [!NOTE]
    > <span data-ttu-id="553cf-288">L'elemento di lavoro creato in Azure DevOps avrà il nome della libreria BPM come prefisso del titolo.</span><span class="sxs-lookup"><span data-stu-id="553cf-288">The work item that is created in Azure DevOps will have the BPM library name as the title prefix.</span></span>

    ![Scheda Requisiti](./media/setup_rsa_tool_40.png)

3. <span data-ttu-id="553cf-290">Aggiorna la pagina.</span><span class="sxs-lookup"><span data-stu-id="553cf-290">Refresh the page.</span></span>
4. <span data-ttu-id="553cf-291">Selezionare il pulsante con i puntini di sospensione (**...**). Verrà visualizzata un'ulteriore opzione, **Test case di sincronizzazione**.</span><span class="sxs-lookup"><span data-stu-id="553cf-291">Select the ellipsis button (**...**). You will see an additional option, **Sync test cases**.</span></span> <span data-ttu-id="553cf-292">Selezionare questa opzione.</span><span class="sxs-lookup"><span data-stu-id="553cf-292">Select this option.</span></span>

    ![Comando Test case di sincronizzazione nel menu con i puntini di sospensione](./media/setup_rsa_tool_41.png)

    > [!NOTE]
    > <span data-ttu-id="553cf-294">Se l'opzione **Test case di sincronizzazione** non è disponibile dopo l'aggiornamento della pagina, passare alla pagina principale per BPM e selezionare **Test case di sincronizzazione** per l'intera libreria.</span><span class="sxs-lookup"><span data-stu-id="553cf-294">If the **Sync test cases** option isn't available after you refresh the page, go to main page for BPM, and select **Sync test cases** for the whole library itself.</span></span> <span data-ttu-id="553cf-295">In questo modo, si forza una sincronizzazione per l'intera libreria.</span><span class="sxs-lookup"><span data-stu-id="553cf-295">In this way, you effectively force a synchronization for the whole library.</span></span>
    > 
    > ![Selezionare Test case di sincronizzazione per l'intera libreria](./media/setup_rsa_tool_42.png)

    <span data-ttu-id="553cf-297">Al termine della sincronizzazione, viene creato un nuovo test case nella scheda **Requisiti**.</span><span class="sxs-lookup"><span data-stu-id="553cf-297">After Sync test cases is completed, a new test case is created on the **Requirements** tab.</span></span>

    ![Nuovo test case nella scheda Requisiti](./media/setup_rsa_tool_43.png)

5. <span data-ttu-id="553cf-299">Passare al progetto di Azure DevOps e selezionare **Boards \> Elementi di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="553cf-299">Go to your Azure DevOps project, and select **Boards \> Work Items**.</span></span>

    ![Comando Elementi di lavoro in Boards](./media/setup_rsa_tool_44.png)

6. <span data-ttu-id="553cf-301">Verificare che l'elemento di lavoro e il test case creato mediante la sincronizzazione con BPM siano presenti.</span><span class="sxs-lookup"><span data-stu-id="553cf-301">Validate that the work item and test case that you created through BPM synchronization exist.</span></span>

    ![Elemento di lavoro e test case](./media/setup_rsa_tool_45.png)

## <a name="install-and-configure-rsat"></a><span data-ttu-id="553cf-303">Installare e configurare RSAT</span><span class="sxs-lookup"><span data-stu-id="553cf-303">Install and Configure RSAT</span></span>

<span data-ttu-id="553cf-304">RSAT può essere installato in qualsiasi computer in cui è in esecuzione Windows 10 e che può essere connesso all'ambiente tramite un Web browser (Internet Explorer o Google Chrome).</span><span class="sxs-lookup"><span data-stu-id="553cf-304">RSAT can be installed on any computer that runs Windows 10 and that can connect to the environment via a web browser (Internet Explorer or Google Chrome).</span></span>

> [!NOTE]
> <span data-ttu-id="553cf-305">Prima di installare una nuova versione dello strumento, si consiglia di disinstallare la versione precedente.</span><span class="sxs-lookup"><span data-stu-id="553cf-305">Before you install a new version of the tool, we recommend that you uninstall the previous version.</span></span>

### <a name="install-an-authentication-certificate"></a><span data-ttu-id="553cf-306">Installare un certificato di autenticazione</span><span class="sxs-lookup"><span data-stu-id="553cf-306">Install an authentication certificate</span></span>

<span data-ttu-id="553cf-307">Per abilitare l'autenticazione, è necessario generare e installare un certificato nello stesso computer in cui RSAT è in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="553cf-307">To enable authentication, you must generate and install a certificate on the same computer that RSAT is running on.</span></span>

#### <a name="generate-a-certificate"></a><span data-ttu-id="553cf-308">Generare un certificato</span><span class="sxs-lookup"><span data-stu-id="553cf-308">Generate a certificate</span></span>

1. <span data-ttu-id="553cf-309">Per generare un file di certificato, aprire una finestra di Microsoft Windows PowerShell come amministratore ed eseguire il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="553cf-309">To generate a certificate file, open a Microsoft Windows PowerShell window as an admin, and run the following command.</span></span>

    ```
    $certificate = New-SelfSignedCertificate -dnsname 127.0.0.1 -CertStoreLocation cert:\LocalMachine\My -FriendlyName "D365 Automated testing certificate" -Provider "Microsoft Strong Cryptographic Provider"
    ```

2. <span data-ttu-id="553cf-310">Aprire il gestore di certificati immettendo **certlm.msc** nella finestra di dialogo **Esegui** e confermare che il certificato **D365 Automated testing certificate** venga creato in **Personale \> Certificati**.</span><span class="sxs-lookup"><span data-stu-id="553cf-310">Open certificate manager by entering **certlm.msc** in the **Run** dialog box, and confirm that the **D365 Automated testing certificate** certificate is created under **Personal \> Certificates**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="553cf-311">Assicurarsi di immettere **certlm.msc** e non **certmgr.msc**, poiché i certificati sono archiviati nel computer locale.</span><span class="sxs-lookup"><span data-stu-id="553cf-311">Be sure to enter **certlm.msc**, not **certmgr.msc**, because the certificates are stored on the local computer.</span></span>

    ![Certificato D365 Automated testing certificate](./media/setup_rsa_tool_46.png)

3. <span data-ttu-id="553cf-313">Fare clic con il pulsante destro del mouse sul certificato, quindi selezionare **Copia**.</span><span class="sxs-lookup"><span data-stu-id="553cf-313">Right-click the certificate, and then select **Copy**.</span></span>
4. <span data-ttu-id="553cf-314">Accedere a **Autorità di certificazione principale attendibili \> Certificati**.</span><span class="sxs-lookup"><span data-stu-id="553cf-314">Go to **Trusted Root Certification Authorities \> Certificates**.</span></span>

    ![Cartella Certificati nella cartella Autorità di certificazione principale attendibili](./media/setup_rsa_tool_47.png)

5. <span data-ttu-id="553cf-316">Nel menu **Azione**, selezionare **Incolla** per copiare il certificato nella posizione **Autorità di certificazione principale attendibili**.</span><span class="sxs-lookup"><span data-stu-id="553cf-316">On the **Action** menu, select **Paste** to copy the certificate to the **Trusted Root Certification Authorities** location.</span></span>

    ![Comando Incolla del menu Azione](./media/setup_rsa_tool_48.png)

6. <span data-ttu-id="553cf-318">Per ottenere l'identificazione personale del certificato installato, ma senza spazi o caratteri speciali, aprire una finestra di Windows PowerShell come amministratore ed eseguire i comandi seguenti.</span><span class="sxs-lookup"><span data-stu-id="553cf-318">To get the thumbprint of the installed certificate, but without spaces or special characters, open a Windows PowerShell window as an admin, and run the following commands.</span></span>

    ```
    cd Cert:\LocalMachine\My

    Get-ChildItem | Where-Object { $_.Subject -like "CN=127.0.0.1" }
    ```

    > [!NOTE]
    > <span data-ttu-id="553cf-319">Salvare l'identificazione personale, poiché sarà necessaria in seguito quando si aggiorneranno i file .wif per Server oggetti applicativi (AOS) e si imposterà la configurazione RSAT.</span><span class="sxs-lookup"><span data-stu-id="553cf-319">Save the thumbprint, because you will need it later when you update the .wif files for Application Object Server (AOS) and set up the RSAT configuration.</span></span>

#### <a name="configure-the-aos-computer-to-trust-the-connection"></a><span data-ttu-id="553cf-320">Configurare il computer AOS per consentire la connessione</span><span class="sxs-lookup"><span data-stu-id="553cf-320">Configure the AOS computer to trust the connection</span></span>

> [!NOTE]
> <span data-ttu-id="553cf-321">Se l'ambiente è di livello 2+, l'identificazione personale del certificato deve essere aggiornata nel file wif.config per **tutti** i computer AOS per l'ambiente.</span><span class="sxs-lookup"><span data-stu-id="553cf-321">If the environment is a Tier 2+ environment, the certificate thumbprint must be updated in the wif.config file for **all** AOS computers for the environment.</span></span>

1. <span data-ttu-id="553cf-322">Stabilire una connessione Remote Desktop Protocol (RDP) al computer AOS.</span><span class="sxs-lookup"><span data-stu-id="553cf-322">Establish a Remote Desktop Protocol (RDP) connection to the AOS computer.</span></span> <span data-ttu-id="553cf-323">Le informazioni di accesso sono disponibili nella pagina dei dettagli dell'ambiente in LCS.</span><span class="sxs-lookup"><span data-stu-id="553cf-323">Sign-in details are available on the environment details page in LCS.</span></span>
2. <span data-ttu-id="553cf-324">Aprire Microsoft Internet Information Services (IIS) e trovare **AOSService** nell'elenco dei siti.</span><span class="sxs-lookup"><span data-stu-id="553cf-324">Open Microsoft Internet Information Services (IIS), and find **AOSService** in the list of sites.</span></span>

    ![AOSService nell'elenco dei siti](./media/setup_rsa_tool_49.png)

3. <span data-ttu-id="553cf-326">Fare clic con il pulsante destro del mouse su **Esplora** per aprire la cartella **\<Drive\>: \\AosService\\Webroot**.</span><span class="sxs-lookup"><span data-stu-id="553cf-326">Right-click **Explore** to open the **\<Drive\>: \\AosService\\WebRoot** folder.</span></span> <span data-ttu-id="553cf-327">Individuare il file **wif.config**.</span><span class="sxs-lookup"><span data-stu-id="553cf-327">Find the **wif.config** file.</span></span>

    ![File Wif.config nella cartella Webroot](./media/setup_rsa_tool_50.png)

4. <span data-ttu-id="553cf-329">Aggiornare il file **wif.config** aggiungendo una nuova voce di autorità per il certificato e il nome dell'autorità, come illustrato nell'esempio riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="553cf-329">Update the **wif.config** file by adding a new authority entry for your certificate and authority name, as shown in the following example.</span></span>

    ```
    <issuerNameRegistry type="Microsoft.Dynamics.AX.Security.SharedUtility.AxIssuerNameRegistry,Microsoft.Dynamics.AX.Security.SharedUtility">
        <authority name="CN=127.0.0.1">
            <keys>
                <add thumbprint="xxxxxxxxxxxxxxxxxxxx" />
                <add thumbprint="xxxxxxxxxxxxxxxxxxxx" />
            </keys>
            <validIssuers>
                <add name="CN=127.0.0.1" />
            </validIssuers>
        </authority>
    ```

    > [!NOTE]
    > <span data-ttu-id="553cf-330">Se più utenti utilizzano la stessa applicazione, ogni utente deve generare identificazioni digitali distinte e ognuna di queste identificazioni deve essere aggiunta nella sezione **\<keys\>**.</span><span class="sxs-lookup"><span data-stu-id="553cf-330">If multiple users are using the same application, each user must generate separate thumbprints, and each of those thumbprints must be added in the **\<keys\>** section.</span></span>

5. <span data-ttu-id="553cf-331">Se vi sono più computer AOS, ripetere i passaggi da 3 a 4 per ogni computer aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="553cf-331">If there is more than one AOS computer, repeat steps 3 through 4 for each additional computer.</span></span>

    > [!NOTE]
    > <span data-ttu-id="553cf-332">A differenza degli ambienti di livello 2 meno recenti, quelli nuovi sono distribuiti con due istanze AOS.</span><span class="sxs-lookup"><span data-stu-id="553cf-332">Unlike older Tier 2 environments, new Tier 2 environments are deployed with two AOS instances.</span></span>

6. <span data-ttu-id="553cf-333">Eseguire **iisreset** su tutti i computer AOS.</span><span class="sxs-lookup"><span data-stu-id="553cf-333">Run **iisreset** on all the AOS computers.</span></span>

    > [!NOTE]
    > <span data-ttu-id="553cf-334">Se non si dispone dei diritti di amministratore per eseguire **iisreset** in un computer di livello 1, nella pagina Dettagli ambiente in LCS selezionare Gestisci > Riavvia servizi.</span><span class="sxs-lookup"><span data-stu-id="553cf-334">If you don't have admin rights to run **iisreset** on a Tier 1 computer, on the Environment details page in LCS, select Maintain > Restart services.</span></span>

#### <a name="tier-2-environment"></a><span data-ttu-id="553cf-335">Ambiente di livello 2+</span><span class="sxs-lookup"><span data-stu-id="553cf-335">Tier 2+ environment</span></span>

<span data-ttu-id="553cf-336">Se si utilizza un ambiente di livello 2+ (Sandbox test di accettazione standard o superiore), verificare o configurare l'impostazione del Registro di sistema seguente nel computer in cui RSAT è installato.</span><span class="sxs-lookup"><span data-stu-id="553cf-336">If a Tier 2+ (Standard Acceptance Test sandbox or higher) environment is used, verify or set the following registry setting on the computer where RSAT is installed.</span></span> <span data-ttu-id="553cf-337">Questo passaggio è necessario in quanto consente di evitare errori di connessione RSAT o di autenticazione.</span><span class="sxs-lookup"><span data-stu-id="553cf-337">This step is required because it helps you avoid authentication or RSAT connection errors.</span></span>

```
if ((Test-Path HKLM:\SOFTWARE\Wow6432Node\Microsoft\.NETFramework\v4.0.30319))
{
    Set-ItemProperty HKLM:\SOFTWARE\Wow6432Node\Microsoft\.NETFramework\v4.0.30319 -Name SchUseStrongCrypto -Value 1 -Type dword -Force -Confirm:$false
}
```

### <a name="install-rsat"></a><span data-ttu-id="553cf-338">Installare RSAT</span><span class="sxs-lookup"><span data-stu-id="553cf-338">Install RSAT</span></span>

1. <span data-ttu-id="553cf-339">Andare a <https://www.microsoft.com/download/details.aspx?id=57357> e selezionare **Scarica**.</span><span class="sxs-lookup"><span data-stu-id="553cf-339">Go to <https://www.microsoft.com/download/details.aspx?id=57357>, and select **Download**.</span></span>
2. <span data-ttu-id="553cf-340">Selezionare tutti i file e quindi **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="553cf-340">Select all the files, and then select **Next**.</span></span>

    ![Selezionare tutti i file](./media/setup_rsa_tool_51.png)

3. <span data-ttu-id="553cf-342">Fare doppio clic sul pacchetto .msi per l'eseguire il programma di installazione.</span><span class="sxs-lookup"><span data-stu-id="553cf-342">Double-click the .msi package to run the installer.</span></span> <span data-ttu-id="553cf-343">Quindi, al termine dell'installazione, selezionare **Fine**.</span><span class="sxs-lookup"><span data-stu-id="553cf-343">Then, when the installation is completed, select **Finish**.</span></span>

    ![File del programma di installazione di RSAT](./media/setup_rsa_tool_52.png)

### <a name="install-selenium-and-browser-drivers"></a><span data-ttu-id="553cf-345">Installare i driver del browser e Selenium</span><span class="sxs-lookup"><span data-stu-id="553cf-345">Install Selenium and browser drivers</span></span>

<span data-ttu-id="553cf-346">Nelle versioni precedenti di RSAT, si dovevano installare i driver del browser e Selenium.</span><span class="sxs-lookup"><span data-stu-id="553cf-346">In older versions of RSAT, you had to install Selenium and browser drivers.</span></span> <span data-ttu-id="553cf-347">Non è più necessario installare questi driver poiché vengono installati automaticamente.</span><span class="sxs-lookup"><span data-stu-id="553cf-347">You no longer have to install these drivers because they are automatically installed.</span></span>

1. <span data-ttu-id="553cf-348">La prima volta che si apre RSAT, viene richiesto di scaricare e installare automaticamente Selenium.</span><span class="sxs-lookup"><span data-stu-id="553cf-348">The first time that you open RSAT, you're prompted to automatically download and install Selenium.</span></span> <span data-ttu-id="553cf-349">Per ulteriori informazioni, vedere la sezione [Configurare RSAT](#configure-rsat).</span><span class="sxs-lookup"><span data-stu-id="553cf-349">For more information, see the [Configure RSAT](#configure-rsat) section.</span></span>
2. <span data-ttu-id="553cf-350">Prima di eseguire un test case, viene richiesto di scaricare e installare automaticamente il driver del browser corrispondente al browser predefinito selezionato nella configurazione RSAT.</span><span class="sxs-lookup"><span data-stu-id="553cf-350">Before you can run a test case, you're prompted to automatically download and install the browser driver that corresponds to the default browser that is selected in the RSAT configuration.</span></span> <span data-ttu-id="553cf-351">Per ulteriori informazioni, vedere la sezione [Caricare ed eseguire test case](#load-and-run-test-cases).</span><span class="sxs-lookup"><span data-stu-id="553cf-351">For more information, see the [Load and run test cases](#load-and-run-test-cases) section.</span></span>

## <a name="get-started-with-rsat"></a><span data-ttu-id="553cf-352">Introduzione a RSAT</span><span class="sxs-lookup"><span data-stu-id="553cf-352">Get started with RSAT</span></span>

### <a name="create-a-test-plan-and-test-suites"></a><span data-ttu-id="553cf-353">Creare un piano di test e gruppi di test</span><span class="sxs-lookup"><span data-stu-id="553cf-353">Create a test plan and test suites</span></span>

1. <span data-ttu-id="553cf-354">Passare al progetto Azure DevOps e selezionare **Piani di test**.</span><span class="sxs-lookup"><span data-stu-id="553cf-354">Go to the Azure DevOps project, and select **Test Plans**.</span></span>

    ![Comando Piani di test](./media/setup_rsa_tool_53.png)

2. <span data-ttu-id="553cf-356">Selezionare **Nuovo piano di test**.</span><span class="sxs-lookup"><span data-stu-id="553cf-356">Select **New Test Plan**.</span></span>

    ![Pulsante Nuovo piano di test](./media/setup_rsa_tool_54.png)

3. <span data-ttu-id="553cf-358">Completare il campo **Nome** e selezionare **Crea**.</span><span class="sxs-lookup"><span data-stu-id="553cf-358">Fill in the **Name** field, and then select **Create**.</span></span> <span data-ttu-id="553cf-359">Per questa esercitazione, denominare il piano di test **Piano di test RSAT**.</span><span class="sxs-lookup"><span data-stu-id="553cf-359">For this tutorial, name the test plan **RSAT Test Plan**.</span></span>

    ![Finestra di dialogo Nuovo piano di test](./media/setup_rsa_tool_55.png)

4. <span data-ttu-id="553cf-361">Selezionare il segno **+** e quindi selezionare **Gruppo statico** per creare un gruppo statico sotto il nuovo piano di test.</span><span class="sxs-lookup"><span data-stu-id="553cf-361">Select the plus sign (**+**), and then select **Static suite** to create a static suite under the new test plan.</span></span> <span data-ttu-id="553cf-362">Denominare il nuovo gruppo di test **T01 - Produzione per scorte**.</span><span class="sxs-lookup"><span data-stu-id="553cf-362">Name the new test suite **T01 – Make to Stock**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="553cf-363">È inoltre possibile creare un gruppo basato su query, se i nuovi test case da BPM devono essere inseriti automaticamente nel gruppo di test RSAT.</span><span class="sxs-lookup"><span data-stu-id="553cf-363">You can also create a query-based suite, if you want the new test cases from BPM to be automatically pulled into the RSAT test suite.</span></span>

    ![Creazione di un gruppo statico](./media/setup_rsa_tool_56.png)

### <a name="attach-test-cases-to-test-suites"></a><span data-ttu-id="553cf-365">Associare test case a gruppi di test</span><span class="sxs-lookup"><span data-stu-id="553cf-365">Attach test cases to test suites</span></span>

1. <span data-ttu-id="553cf-366">Selezionare **Aggiungi esistente** a destra per aggiungere case test esistenti al gruppo di test.</span><span class="sxs-lookup"><span data-stu-id="553cf-366">Select **Add existing** on the right side to add existing test cases to the test suite.</span></span>

    ![Pulsante Aggiungi esistente](./media/setup_rsa_tool_57.png)

2. <span data-ttu-id="553cf-368">Nella pagina **Aggiungi test case a gruppo** selezionare **Esegui query**, quindi selezionare il test case da aggiungere al gruppo di test.</span><span class="sxs-lookup"><span data-stu-id="553cf-368">On the **Add test cases to suite** page, select **Run query**, and then select the test case to add to the test suite.</span></span> <span data-ttu-id="553cf-369">Per questa esercitazione, selezionare il test case **Creare un nuovo prodotto**.</span><span class="sxs-lookup"><span data-stu-id="553cf-369">For this tutorial, select the **Create a new product** test case.</span></span> <span data-ttu-id="553cf-370">Selezionare quindi **Aggiungi test case** nell'angolo in basso a destra della pagina (questo pulsante non è presente nell'illustrazione seguente).</span><span class="sxs-lookup"><span data-stu-id="553cf-370">Then select **Add test cases** in the lower-right corner of the page (this button isn't shown in the following illustration).</span></span>

    ![Pulsante Esegui query](./media/setup_rsa_tool_58.png)

    <span data-ttu-id="553cf-372">Il test case viene aggiunto al gruppo di test **T01- Produzione per scorte**.</span><span class="sxs-lookup"><span data-stu-id="553cf-372">The test case is added to the **T01-Make to Stock** test suite.</span></span>

    ![Test case aggiunto al gruppo di test](./media/setup_rsa_tool_59.png)

### <a name="configure-rsat"></a><span data-ttu-id="553cf-374">Configura RSAT</span><span class="sxs-lookup"><span data-stu-id="553cf-374">Configure RSAT</span></span>

1. <span data-ttu-id="553cf-375">Aprire RSAT.</span><span class="sxs-lookup"><span data-stu-id="553cf-375">Open RSAT.</span></span>

    ![Icona RSAT](./media/setup_rsa_tool_60.png)

2. <span data-ttu-id="553cf-377">Viene visualizzato il messaggio di avviso "Per Regression Suite Automation Tool è necessario Selenium. Scaricare e installare automaticamente Selenium ora?".</span><span class="sxs-lookup"><span data-stu-id="553cf-377">You receive a warning message that states, "The Regression Suite Automation Tool requires Selenium, do you want to automatically download and install it now?"</span></span> <span data-ttu-id="553cf-378">Selezionare **Sì**.</span><span class="sxs-lookup"><span data-stu-id="553cf-378">Select **Yes**.</span></span>

    ![Messaggio di avviso](./media/setup_rsa_tool_61.png)

3. <span data-ttu-id="553cf-380">Fare clic sul pulsante **Impostazioni** (il simbolo di ingranaggio) nell'angolo superiore destro e quindi, nella finestra di dialogo visualizzata, riempire i seguenti campi:</span><span class="sxs-lookup"><span data-stu-id="553cf-380">Select the **Settings** button (the gear symbol) in the upper-right corner, and then, in the dialog box that appears, fill in the following fields:</span></span>

    - <span data-ttu-id="553cf-381">**URL di Azure DevOps** - Immettere l'URL del progetto Azure DevOps, ad esempio `https://yourAzureDevOpsUrlHere.visualStudio.com`.</span><span class="sxs-lookup"><span data-stu-id="553cf-381">**Azure DevOps Url** – Enter the URL of your Azure DevOps project, such as `https://yourAzureDevOpsUrlHere.visualStudio.com`.</span></span>
    - <span data-ttu-id="553cf-382">**Token di accesso** - Immettere il token di accesso che consente la connessione dello strumento a Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="553cf-382">**Access Token** – Enter the access token that lets the tool connect to Azure DevOps.</span></span> <span data-ttu-id="553cf-383">Utilizzare il token di accesso personale creato in precedenza in questa esercitazione.</span><span class="sxs-lookup"><span data-stu-id="553cf-383">Use the personal access token that you created earlier in this tutorial.</span></span> <span data-ttu-id="553cf-384">Per ulteriori informazioni, vedere [Autenticare l'accesso con token di accesso personali](https://www.visualstudio.com/docs/setup-admin/team-services/use-personal-access-tokens-to-authenticate).</span><span class="sxs-lookup"><span data-stu-id="553cf-384">For more information, see [Authenticate access with personal access tokens](https://www.visualstudio.com/docs/setup-admin/team-services/use-personal-access-tokens-to-authenticate).</span></span>
    - <span data-ttu-id="553cf-385">**Nome progetto** - Selezionare il nome del progetto Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="553cf-385">**Project Name** – Select the name of your Azure DevOps project.</span></span>
    - <span data-ttu-id="553cf-386">**Piano di test** - Selezionare il piano di test Azure DevOps che contiene i test case.</span><span class="sxs-lookup"><span data-stu-id="553cf-386">**Test Plan** – Select the Azure DevOps test plan that contains your test cases.</span></span> <span data-ttu-id="553cf-387">Per ulteriori informazioni, vedere [Creare piani di test e gruppi di test](https://www.visualstudio.com/docs/test/manual-exploratory-testing/getting-started/create-a-test-plan).</span><span class="sxs-lookup"><span data-stu-id="553cf-387">For more information, see [Create test plans and test suites](https://www.visualstudio.com/docs/test/manual-exploratory-testing/getting-started/create-a-test-plan).</span></span> <span data-ttu-id="553cf-388">Dopo avere selezionato un piano di test, selezionare **Test connessione** per testare la connessione a Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="553cf-388">After you select a test plan, select **Test Connection** to test your connection to Azure DevOps.</span></span>
    - <span data-ttu-id="553cf-389">**Nome host** - Immettere il nome host dell'ambiente di test, ad esempio **\<myaos\>.cloudax.dynamics.com**.</span><span class="sxs-lookup"><span data-stu-id="553cf-389">**Hostname** – Enter the host name of the test environment, such as **\<myaos\>.cloudax.dynamics.com**.</span></span> <span data-ttu-id="553cf-390">Non includere il prefisso **http://** o **https://**.</span><span class="sxs-lookup"><span data-stu-id="553cf-390">Don't include the **https://** or **http://** prefix.</span></span>
    - <span data-ttu-id="553cf-391">**Nome host SOAP** - Immettere il nome host SOAP dell'ambiente di test.</span><span class="sxs-lookup"><span data-stu-id="553cf-391">**SOAP Hostname** – Enter the SOAP host name of the test environment.</span></span> <span data-ttu-id="553cf-392">In genere, il nome host SOAP corrisponde al nome host, ma presenta il suffisso **soap**.</span><span class="sxs-lookup"><span data-stu-id="553cf-392">Typically, the SOAP host name is the same as the host name, but it has a **soap** suffix.</span></span> <span data-ttu-id="553cf-393">Ad esempio: **\<myaos\>soap.cloudax.dynamics.com**.</span><span class="sxs-lookup"><span data-stu-id="553cf-393">Here is an example: **\<myaos\>soap.cloudax.dynamics.com**.</span></span> <span data-ttu-id="553cf-394">Non includere il prefisso **http://** o **https://**.</span><span class="sxs-lookup"><span data-stu-id="553cf-394">Don't include the **https://** or **http://** prefix.</span></span>

        > [!NOTE]
        > <span data-ttu-id="553cf-395">Per trovare il nome host e il nome host SOAP, aprire Gestione IIS, fare clic con il pulsante destro del mouse su **Siti \> AOSService** e selezionare **Modifica binding**.</span><span class="sxs-lookup"><span data-stu-id="553cf-395">To find the host name and SOAP host name, open IIS Manager, right-click **Sites \> AOSService**, and then select **Edit bindings**.</span></span> <span data-ttu-id="553cf-396">I valori nella colonna **Nome host** indicano il nome host e il nome host SOAP (il nome host SOAP ha il suffisso **soap** nell'URL).</span><span class="sxs-lookup"><span data-stu-id="553cf-396">The values in the **Host Name** column give you the host name and SOAP host name (the SOAP host name has the suffix **soap** in the URL).</span></span>

        ![Nome host e nome host SOAP nella colonna Nome host](./media/setup_rsa_tool_63.png)

    - <span data-ttu-id="553cf-398">**Nome utente amministratore** - Immettere l'indirizzo di posta elettronica di un utente amministratore nell'ambiente di test.</span><span class="sxs-lookup"><span data-stu-id="553cf-398">**Admin user name** – Enter the email address of an admin user in the test environment.</span></span>
    - <span data-ttu-id="553cf-399">**Identificazione personale** - Immettere l'identificazione personale del certificato di autenticazione come descritto in precedenza in questa esercitazione.</span><span class="sxs-lookup"><span data-stu-id="553cf-399">**Thumbprint** – Enter the thumbprint of the authentication certificate, as described earlier in this tutorial.</span></span>
    - <span data-ttu-id="553cf-400">**Directory di lavoro** - Specificare il percorso della cartella per l'archiviazione dei file di automazione dei test, ad esempio i file di dati di test di Excel.</span><span class="sxs-lookup"><span data-stu-id="553cf-400">**Working directory** – Specify the folder location for storing test automation files, such as Excel test data files.</span></span> <span data-ttu-id="553cf-401">Ad esempio, immettere o selezionare **C:\\ITemp\\RegressionTool**.</span><span class="sxs-lookup"><span data-stu-id="553cf-401">For example, enter or select **C:\\Temp\\RegressionTool**.</span></span>

        > [!NOTE]
        > <span data-ttu-id="553cf-402">Se il nome della cartella presenta degli spazi, l'esecuzione avrà esito negativo in quanto la cartella non viene trovata.</span><span class="sxs-lookup"><span data-stu-id="553cf-402">If the name of the folder has spaces, execution will fail because the folder can't be found.</span></span> <span data-ttu-id="553cf-403">Questo problema è noto e dovrebbe risultare risolto nell'ultima versione dello strumento.</span><span class="sxs-lookup"><span data-stu-id="553cf-403">This issue is a known issue and should be fixed in the latest version of the tool.</span></span>

    - <span data-ttu-id="553cf-404">**Browser predefinito** - Selezionare **Internet Explorer** o **Google Chrome**.</span><span class="sxs-lookup"><span data-stu-id="553cf-404">**Default browser** – Select either **Internet Explorer** or **Google Chrome**.</span></span> <span data-ttu-id="553cf-405">Verificare che i driver del browser siano installati.</span><span class="sxs-lookup"><span data-stu-id="553cf-405">Make sure that the appropriate browser drivers have been installed.</span></span>
    - <span data-ttu-id="553cf-406">**Timeout esecuzione dei test** - Specificare il timeout, in minuti, per le esecuzioni dei test.</span><span class="sxs-lookup"><span data-stu-id="553cf-406">**Test run timeout** – Specify the time-out period, in minutes, for test runs.</span></span> <span data-ttu-id="553cf-407">Alla scadenza del timeout, tutte le finestre attive vengono chiuse e i test case in sospeso hanno esito negativo.</span><span class="sxs-lookup"><span data-stu-id="553cf-407">When the time-out period elapses, all active windows are closed, and pending test cases fail.</span></span>
    - <span data-ttu-id="553cf-408">**Tiemout azione dei test** - Questo campo controlla il timeout, in minuti, per le richieste del server dell'ambiente di Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="553cf-408">**Test action timeout** – This field controls the time-out period, in minutes, for Finance and Operation environment server requests.</span></span> <span data-ttu-id="553cf-409">In genere, il valore predefinito (2 minuti) è sufficiente.</span><span class="sxs-lookup"><span data-stu-id="553cf-409">Usually, the default value (2 minutes) should be enough.</span></span> <span data-ttu-id="553cf-410">Tuttavia, per gli ambienti più lenti, è possibile aumentare il valore se si verificano errori relativi ai timeout.</span><span class="sxs-lookup"><span data-stu-id="553cf-410">However, for slower environments, you might want to increase the value if errors that are related to time-outs occur.</span></span>
    - <span data-ttu-id="553cf-411">**Nome società** - Immettere il nome della società da utilizzare come società predefinita quando vengono creati i file di parametri di Excel.</span><span class="sxs-lookup"><span data-stu-id="553cf-411">**Company name** – Enter the company name to use as your default company when Excel parameter files are created.</span></span> <span data-ttu-id="553cf-412">È possibile modificare la società in seguito modificando il file di parametri di Excel.</span><span class="sxs-lookup"><span data-stu-id="553cf-412">You can change the company later by editing the Excel parameter file.</span></span>

    ![Finestra di dialogo Impostazioni](./media/setup_rsa_tool_62.png)

4. <span data-ttu-id="553cf-414">Selezionare **Applica** per applicare e salvare le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="553cf-414">Select **Apply** to apply and save your settings.</span></span>

    <span data-ttu-id="553cf-415">Per salvare le impostazioni correnti in un file di configurazione nel computer, selezionare **Salva con nome**.</span><span class="sxs-lookup"><span data-stu-id="553cf-415">To save your current settings to a configuration file on your computer, select **Save as**.</span></span> <span data-ttu-id="553cf-416">Per ripristinare le impostazioni da un file di configurazione nel computer, selezionare **Apri**.</span><span class="sxs-lookup"><span data-stu-id="553cf-416">To restore your settings from a configuration file on your computer, select **Open**.</span></span>

5. <span data-ttu-id="553cf-417">Selezionare **Chiudi** per chiudere la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="553cf-417">Select **Close** to close the dialog box.</span></span>

### <a name="load-and-run-test-cases"></a><span data-ttu-id="553cf-418">Caricare ed eseguire test case</span><span class="sxs-lookup"><span data-stu-id="553cf-418">Load and run test cases</span></span>

1. <span data-ttu-id="553cf-419">Selezionare **Carica** per caricare il piano di test **Piano di test RSAT** dal progetto. Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="553cf-419">Select **Load** to load the **RSAT Test Plan** test plan from the Azure DevOps project.</span></span>

    ![Pulsante Carica](./media/setup_rsa_tool_64.png)

2. <span data-ttu-id="553cf-421">Selezionare il test case **Creare un nuovo prodotto** nel gruppo di test e selezionare **Nuovo \> Genera file di esecuzione di test e di parametri**.</span><span class="sxs-lookup"><span data-stu-id="553cf-421">Select the **Create a new product** test case from the test suite, and then select **New \> Generate Test Execution and Parameter files**.</span></span>

    ![Comando Genera file di esecuzione di test e di parametri nel menu Nuovo](./media/setup_rsa_tool_65.png)

    <span data-ttu-id="553cf-423">Il file di parametri di Excel viene creato nella cartella locale specificata nella configurazione RSAT (ad esempio **C:\\Temp\\RegressionTool**).</span><span class="sxs-lookup"><span data-stu-id="553cf-423">The Excel parameter file is created in the local folder that you specified in the RSAT configuration (for example, **C:\\Temp\\RegressionTool**).</span></span>

    ![File di parametri di Excel creato](./media/setup_rsa_tool_66.png)

3. <span data-ttu-id="553cf-425">Per salvare i file di parametri, selezionare **Carica**.</span><span class="sxs-lookup"><span data-stu-id="553cf-425">If you want to save the parameter files, select **Upload**.</span></span> <span data-ttu-id="553cf-426">I file di automazione di test di tutti i test case selezionati vengono caricati in Azure DevOps per un utilizzo futuro</span><span class="sxs-lookup"><span data-stu-id="553cf-426">Test automation files of all selected test cases are uploaded to Azure DevOps for future use.</span></span> <span data-ttu-id="553cf-427">(tali file includono i file di parametri di test di Excel).</span><span class="sxs-lookup"><span data-stu-id="553cf-427">(These files include Excel test parameter files.)</span></span>

    <span data-ttu-id="553cf-428">In questo modo, è possibile selezionare **Carica** per caricare i file di parametri (nonché i file di automazione) del test case direttamente da Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="553cf-428">In this way, you can select **Load** to load the parameter files (and automation files) from the test case directly from Azure DevOps.</span></span> <span data-ttu-id="553cf-429">Non è necessario generare nuovamente i file di parametri.</span><span class="sxs-lookup"><span data-stu-id="553cf-429">You don't have to regenerate the parameter files.</span></span> <span data-ttu-id="553cf-430">Questo approccio risulterà importante in seguito, quando si desidera mantenere le modifiche nel file di parametri ed evitare che vengano sovrascritte.</span><span class="sxs-lookup"><span data-stu-id="553cf-430">This approach will become important later, when you want to keep the modifications in the parameter file and don't want them to be overwritten.</span></span>

4. <span data-ttu-id="553cf-431">Per verificare che i file di automazione e di parametri vengono salvati in Azure DevOps, accedere al progetto Azure DevOps selezionare **Boards \> Elementi di lavoro**, quindi selezionare il test case **Creare un nuovo prodotto**.</span><span class="sxs-lookup"><span data-stu-id="553cf-431">To verify that the automation files and parameter files are saved to Azure DevOps, go to the Azure DevOps project, select **Boards \> Work Items**, and select the **Create a new product** test case.</span></span> <span data-ttu-id="553cf-432">Nella scheda **Allegati**, dovrebbero essere visualizzati quattro file:</span><span class="sxs-lookup"><span data-stu-id="553cf-432">On the **Attachments** tab, you should see four files:</span></span>

    - <span data-ttu-id="553cf-433">**.cs** - File di automazione C\#</span><span class="sxs-lookup"><span data-stu-id="553cf-433">**.cs** – C\# automation file</span></span>
    - <span data-ttu-id="553cf-434">**.dll** - File di automazione compilato come assembly</span><span class="sxs-lookup"><span data-stu-id="553cf-434">**.dll** – Compiled automation file as an assembly</span></span>
    - <span data-ttu-id="553cf-435">**.xlsx** – File di parametri di Excel</span><span class="sxs-lookup"><span data-stu-id="553cf-435">**.xlsx** – Excel parameter file</span></span>
    - <span data-ttu-id="553cf-436">**.xml** - File di registrazione</span><span class="sxs-lookup"><span data-stu-id="553cf-436">**.xml** – Recording file</span></span>

    ![File nella scheda Allegati](./media/setup_rsa_tool_67.png)

5. <span data-ttu-id="553cf-438">Selezionare il test case da eseguire e selezionare **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="553cf-438">Select the test case to run, and then select **Run**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="553cf-439">Prima di eseguire i test case, se si utilizza Internet Explorer come browser, verificare che la risoluzione dello schermo sia **100%** in **Impostazioni di visualizzazione di Windows \> Ridimensionamento e layout**.</span><span class="sxs-lookup"><span data-stu-id="553cf-439">Before you run test cases, if you're using Internet Explorer as the browser, make sure that your desktop resolution is set to **100%** at **Windows Display settings \> Scale and layout**.</span></span> <span data-ttu-id="553cf-440">Se non è possibile modificare questa impostazione su una macchina virtuale (VM), modificarla nel client (computer portatile) utilizzato per accedere alla macchina virtuale.</span><span class="sxs-lookup"><span data-stu-id="553cf-440">If you can't change this setting on a virtual machine (VM), change it on the client (laptop) that you're trying to access the VM from.</span></span> <span data-ttu-id="553cf-441">Le impostazioni di risoluzione verranno ereditate dalle impostazioni di visualizzazione della macchina virtuale.</span><span class="sxs-lookup"><span data-stu-id="553cf-441">The resolution settings will then be inherited by the VM display settings.</span></span>

    ![Risoluzione dello schermo impostata su 100%](./media/setup_rsa_tool_68.png)

6. <span data-ttu-id="553cf-443">Se i driver del browser non sono installati nel sistema, verrà visualizzato il messaggio di avviso "Per eseguire questa operazione è necessario il driver \<browser name\>.</span><span class="sxs-lookup"><span data-stu-id="553cf-443">If the browser drivers aren't installed in the system, you receive a warning message that states, "This operation requires the \<browser name\> driver.</span></span> <span data-ttu-id="553cf-444">Scaricare e installare automaticamente il driver ora?</span><span class="sxs-lookup"><span data-stu-id="553cf-444">Do you want to automatically downloads and install it now?"</span></span> <span data-ttu-id="553cf-445">Selezionare **Sì**.</span><span class="sxs-lookup"><span data-stu-id="553cf-445">Select **Yes**.</span></span>

    ![Messaggio di avviso per Internet Explorer](./media/setup_rsa_tool_69.png)

    ![Messaggio di avviso per Chrome](./media/setup_rsa_tool_70.png)

    > [!NOTE]
    > <span data-ttu-id="553cf-448">Se si utilizza Chrome come browser e viene visualizzato un messaggio di errore in cui viene indicato che la sessione non è stata creata in quanto la versione di Chrome non è corretta, scaricare il driver di Chrome più recente da <http://chromedriver.chromium.org/downloads> nella cartella **C:\\Programmi (x86)\\Regression Suite Automation Tool\\Common\\External\\Selenium**.</span><span class="sxs-lookup"><span data-stu-id="553cf-448">If you're using Chrome as the browser and receive an error message that states that the session wasn't created because the Chrome version isn't correct, download the latest Chrome driver from <http://chromedriver.chromium.org/downloads> to the **C:\\Program Files (x86)\\Regression Suite Automation Tool\\Common\\External\\Selenium** folder.</span></span>

    ![Messaggio di errore per Chrome](./media/setup_rsa_tool_71.png)

    <span data-ttu-id="553cf-450">Il test case viene eseguito e il campo **Risultato** aggiornato.</span><span class="sxs-lookup"><span data-stu-id="553cf-450">The test case is run, and the **Result** field is updated.</span></span>

    ![Indicatore di stato](./media/setup_rsa_tool_72.png)

    <span data-ttu-id="553cf-452">Se si è svolta questa esercitazione come descritto, il test case **Creare un nuovo prodotto** avrà esito negativo poiché l'attività registrata per la creazione di un prodotto ha salvato il nome del prodotto come valore hardcoded.</span><span class="sxs-lookup"><span data-stu-id="553cf-452">If you've followed this tutorial as it's written, the **Create a new product** test case will fail, because the task recording for creating a product saved the product name as a hard-coded value.</span></span> <span data-ttu-id="553cf-453">Se si esegue di nuovo lo stesso test case, dovrebbe essere visualizzato un messaggio di errore in quanto il prodotto esiste già.</span><span class="sxs-lookup"><span data-stu-id="553cf-453">If you rerun the same test case, you should receive an error message, because the product already exists.</span></span>

    ![Campo Risultato impostato su Non superato](./media/setup_rsa_tool_72.png)

### <a name="view-the-test-results"></a><span data-ttu-id="553cf-455">Visualizzare i risultati dei test</span><span class="sxs-lookup"><span data-stu-id="553cf-455">View the test results</span></span>

1. <span data-ttu-id="553cf-456">Fare doppio sul test case non riuscito.</span><span class="sxs-lookup"><span data-stu-id="553cf-456">Double-click the failed test case.</span></span>

    <span data-ttu-id="553cf-457">Viene visualizzato un messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="553cf-457">You receive an error message.</span></span>

    ![Messaggio di errore](./media/setup_rsa_tool_73.png)

2. <span data-ttu-id="553cf-459">Selezionare **Dettagli** per visualizzare l'intero messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="553cf-459">Select **Details** to view the whole error message.</span></span>

    ![Messaggio di errore completo](./media/setup_rsa_tool_74.png)

3. <span data-ttu-id="553cf-461">Per visualizzare una versione dettagliata del messaggio di errore in Azure DevOps, selezionare **Apri in Azure DevOps**.</span><span class="sxs-lookup"><span data-stu-id="553cf-461">To view a detailed version of the error message in Azure DevOps, select **Open in Azure DevOps**.</span></span> <span data-ttu-id="553cf-462">In Azure DevOps, è possibile visualizzare lo stato del test case e del messaggio di errore dettagliato.</span><span class="sxs-lookup"><span data-stu-id="553cf-462">In Azure DevOps, you can view the status of the test case and the detailed error message.</span></span>

    ![Messaggio di errore dettagliato in Azure DevOps](./media/setup_rsa_tool_75.png)

4. <span data-ttu-id="553cf-464">Per visualizzare i risultati dei test direttamente nel progetto Azure DevOps, passare a **Piani di test \> Piani di test \> Esecuzioni**.</span><span class="sxs-lookup"><span data-stu-id="553cf-464">To view the test results directly in the Azure DevOps project, go to **Test Plans \> Test Plans \> Runs**.</span></span> <span data-ttu-id="553cf-465">Fare doppio clic sull'esecuzione di test per la quale si desidera visualizzare ulteriori dettagli.</span><span class="sxs-lookup"><span data-stu-id="553cf-465">Double-click the test run that you want to see more details for.</span></span>

    ![Elenco delle esecuzioni di test in Azure DevOps](./media/setup_rsa_tool_76.png)

5. <span data-ttu-id="553cf-467">La scheda **Riepilogo esecuzione** indica che il test case non è riuscito, ma non fornisce il messaggio di errore vero e proprio.</span><span class="sxs-lookup"><span data-stu-id="553cf-467">The **Run summary** tab indicates that the test case failed, but it doesn't provide the actual error message.</span></span> <span data-ttu-id="553cf-468">Per visualizzare il messaggio di errore dettagliato, selezionare la scheda **Risultati test**.</span><span class="sxs-lookup"><span data-stu-id="553cf-468">To view the detailed error message, select the **Test results** tab.</span></span>

    ![Scheda Riepilogo esecuzione](./media/setup_rsa_tool_77.png)

    <span data-ttu-id="553cf-470">La scheda **Risultati test** fornisce informazioni sul test case, nonché il risultato e il messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="553cf-470">The **Test results** tab provides the test case information, together with the outcome and the error message.</span></span>

    ![Scheda Risultati test](./media/setup_rsa_tool_78.png)

6. <span data-ttu-id="553cf-472">Fare doppio clic sul record pertinente per visualizzare il messaggio di errore dettagliato.</span><span class="sxs-lookup"><span data-stu-id="553cf-472">Double-click the relevant record to view the detailed error message.</span></span>

    ![Messaggio di errore dettagliato](./media/setup_rsa_tool_79.png)

    > [!NOTE]
    > <span data-ttu-id="553cf-474">Tutti i messaggi di errore sono disponibili localmente in **C:\\Utenti\\\$YourUserName\\AppData\\Roaming\\regressionTool\\errormsg-.txt**.</span><span class="sxs-lookup"><span data-stu-id="553cf-474">All error messages are also available locally in **C:\\Users\\\$YourUserName\\AppData\\Roaming\\regressionTool\\errormsg-.txt**.</span></span>

7. <span data-ttu-id="553cf-475">È inoltre possibile esportare i risultati delle esecuzioni dei test dal livello piano di test selezionando **Esporta**.</span><span class="sxs-lookup"><span data-stu-id="553cf-475">You can also export the test run results from the test plan level by selecting **Export**.</span></span>

    ![Esportare un piano di test](./media/setup_rsa_tool_80.png)

### <a name="modify-the-excel-parameter-file"></a><span data-ttu-id="553cf-477">Modificare il file di parametri di Excel</span><span class="sxs-lookup"><span data-stu-id="553cf-477">Modify the Excel parameter file</span></span>

1. <span data-ttu-id="553cf-478">Aprire RSAT.</span><span class="sxs-lookup"><span data-stu-id="553cf-478">Open RSAT.</span></span>
2. <span data-ttu-id="553cf-479">Selezionare il test case derivati, quindi selezionare **Modifica** per aprire il file di parametri di Excel.</span><span class="sxs-lookup"><span data-stu-id="553cf-479">Select the test case, and then select **Edit** to open the Excel parameter file.</span></span>

    <span data-ttu-id="553cf-480">Nel foglio **EcoResProductCreate**, notare che il valore del campo **Numero prodotto** è hardcoded.</span><span class="sxs-lookup"><span data-stu-id="553cf-480">On the **EcoResProductCreate** sheet, notice that the value of the **Product number** field is hard-coded.</span></span> <span data-ttu-id="553cf-481">È necessario aggiornare questo campo a un nuovo numero di prodotto prima di eseguire di nuovo il test case.</span><span class="sxs-lookup"><span data-stu-id="553cf-481">You must update this field to a new product number before you run the test case again.</span></span>

3. <span data-ttu-id="553cf-482">Per generare un numero di prodotto univoco per ogni esecuzione senza dover riaprire il file di parametri di Excel e aggiornare manualmente il numero di prodotto ogni volta, utilizzare la seguente formula di Excel.</span><span class="sxs-lookup"><span data-stu-id="553cf-482">To generate a unique product number for each run without having to reopen the Excel parameter file and manually update the product number every time, use the following Excel formula.</span></span>

    ```
    ="RSAT_"&TEXT(NOW(),"yyymmddhhmm")
    ```

    > [!NOTE]
    > <span data-ttu-id="553cf-483">Oltre alla scheda **Generale**, il file di parametri di Excel contiene una scheda dati per ogni pagina modulo visitata dal test case.</span><span class="sxs-lookup"><span data-stu-id="553cf-483">In addition to the **General** tab, the Excel parameter file contains a data tab for every form page the test case visits.</span></span>

    ![Campo Numero prodotto](./media/setup_rsa_tool_81.png)

4. <span data-ttu-id="553cf-485">Selezionare **Salva**, quindi chiudere la cartella di lavoro di Excel.</span><span class="sxs-lookup"><span data-stu-id="553cf-485">Select **Save**, and then close the Excel workbook.</span></span>
5. <span data-ttu-id="553cf-486">Selezionare **Carica** per salvare il file di parametri di Excel in Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="553cf-486">Select **Upload** to save the Excel parameter file to Azure DevOps.</span></span>

    ![Messaggio che indica il completamento del caricamento](./media/setup_rsa_tool_82.png)

    > [!NOTE]
    > <span data-ttu-id="553cf-488">Per eseguire test case in un contesto utente specifico, immettere l'ID di posta elettronica dell'utente nel campo **Verifica utente** della scheda **Generale** del file di parametri di Excel.</span><span class="sxs-lookup"><span data-stu-id="553cf-488">To run test cases in a specific user context, enter the user's email ID in the **Test User** field on the **General** tab of the Excel parameter file.</span></span> <span data-ttu-id="553cf-489">Nell'ultima versione di RSAT, il layout dei campi nel file di parametri di Excel è stato aggiornato, ma il concetto è invariato.</span><span class="sxs-lookup"><span data-stu-id="553cf-489">In the latest version of RSAT, the layout of the fields in the Excel parameter file has been updated, but the concept remains the same.</span></span>
    >
    > ![Campo Verifica utente](./media/setup_rsa_tool_83.png)

### <a name="validate-the-results"></a><span data-ttu-id="553cf-491">Convalidare i risultati</span><span class="sxs-lookup"><span data-stu-id="553cf-491">Validate the results</span></span>

- <span data-ttu-id="553cf-492">Selezionare **Esegui** per eseguire di nuovo il test case e verificare che ha avuto esito positivo.</span><span class="sxs-lookup"><span data-stu-id="553cf-492">Select **Run** to rerun the test case, and verify that the test case has passed.</span></span> <span data-ttu-id="553cf-493">È possibile visualizzare i risultati dei test come descritto nella sezione [Visualizzare i risultati dei test](#view-the-test-results).</span><span class="sxs-lookup"><span data-stu-id="553cf-493">You can view the test results as described in the [View the test results](#view-the-test-results) section.</span></span>

    ![Campo Risultato impostato su Superato](./media/setup_rsa_tool_84.png)

### <a name="chaining-of-test-cases"></a><span data-ttu-id="553cf-495">Concatenamento dei test case</span><span class="sxs-lookup"><span data-stu-id="553cf-495">Chaining of test cases</span></span>

<span data-ttu-id="553cf-496">Una funzionalità importante di RSAT è il concatenamento dei test case (ovvero la capacità di un test di passare valori ad altri test).</span><span class="sxs-lookup"><span data-stu-id="553cf-496">One key feature of RSAT is the chaining of test cases (that is, the capability of a test to pass values to other tests).</span></span> <span data-ttu-id="553cf-497">I test case vengono eseguiti in base all'ordine definito nel piano di test di Azure DevOps</span><span class="sxs-lookup"><span data-stu-id="553cf-497">Test cases are run according to their defined order in the Azure DevOps test plan.</span></span> <span data-ttu-id="553cf-498">(questo ordine può essere aggiornato nello strumento di test stesso). Di conseguenza, se si desidera passare variabili da un test case a un altro, è molto importante che i test siano nell'ordine corretto.</span><span class="sxs-lookup"><span data-stu-id="553cf-498">(This order can also be updated in the test tool itself.) Therefore, if you want to pass variables from one test case to another, it's very important that the tests be in the correct order.</span></span>

<span data-ttu-id="553cf-499">In questa sezione, si creerà una variabile salvata nel primo test case, si creerà un secondo test case e quindi si passerà la variabile salvata dal primo test case al secondo test case.</span><span class="sxs-lookup"><span data-stu-id="553cf-499">In this section, you will create a saved variable in the first test case, create a second test case, and pass the saved variable from the first test case to the second test case.</span></span> <span data-ttu-id="553cf-500">Successivamente si eseguiranno i test case come test case concatenato in RSAT.</span><span class="sxs-lookup"><span data-stu-id="553cf-500">You will then run the test cases as a chained test case in RSAT.</span></span>

#### <a name="modify-an-existing-task-recording-to-create-a-saved-variable"></a><span data-ttu-id="553cf-501">Modificare una registrazione attività esistente per creare una variabile salvata</span><span class="sxs-lookup"><span data-stu-id="553cf-501">Modify an existing task recording to create a saved variable</span></span>

1. <span data-ttu-id="553cf-502">Avviare il client.</span><span class="sxs-lookup"><span data-stu-id="553cf-502">Open the client.</span></span>
2. <span data-ttu-id="553cf-503">Selezionare il pulsante **Impostazioni** (il simbolo di ingranaggio) e quindi **Registrazione attività**.</span><span class="sxs-lookup"><span data-stu-id="553cf-503">Select the **Settings** button (the gear symbol), and then select **Task recorder**.</span></span>
3. <span data-ttu-id="553cf-504">Selezionare **Modifica registrazione**.</span><span class="sxs-lookup"><span data-stu-id="553cf-504">Select **Edit Recording**.</span></span>

    ![Pulsante Modifica registrazione](./media/setup_rsa_tool_85.png)

4. <span data-ttu-id="553cf-506">Selezionare **Aprire da Lifecycle Services**</span><span class="sxs-lookup"><span data-stu-id="553cf-506">Select **Open from Lifecycle Services**.</span></span>

    ![Pulsante Aprire da Lifecycle Services](./media/setup_rsa_tool_86.png)

5. <span data-ttu-id="553cf-508">Selezionare **Selezionare la libreria di Lifecycle Services**.</span><span class="sxs-lookup"><span data-stu-id="553cf-508">Select **Select the Lifecycle Services library**.</span></span>

    ![Pulsante Selezionare la libreria di Lifecycle Services](./media/setup_rsa_tool_87.png)

    <span data-ttu-id="553cf-510">Le librerie BPM vengono caricate da LCS.</span><span class="sxs-lookup"><span data-stu-id="553cf-510">BPM libraries are loaded from LCS.</span></span>

    ![Indicatore di stato](./media/setup_rsa_tool_88.png)

6. <span data-ttu-id="553cf-512">Dopo il caricamento delle librerie BPM da LCS, selezionare la libreria BMP **RSAT** e il processo aziendale **Creare un nuovo prodotto** a cui la registrazione attività era associata.</span><span class="sxs-lookup"><span data-stu-id="553cf-512">After the BPM libraries are loaded from LCS, select the **RSAT** BPM library and the **Create a new product** business process that the task recording was associated with.</span></span> <span data-ttu-id="553cf-513">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="553cf-513">Then select **OK**.</span></span>

    ![Selezionare una libreria BPM e un processo aziendale](./media/setup_rsa_tool_89.png)

7. <span data-ttu-id="553cf-515">Il nome della registrazione attività appropriata viene immesso nel campo **Nome registrazione**.</span><span class="sxs-lookup"><span data-stu-id="553cf-515">The name of the appropriate task recording is entered in the **Recording name** field.</span></span> <span data-ttu-id="553cf-516">Selezionare **Avvia**.</span><span class="sxs-lookup"><span data-stu-id="553cf-516">Select **Start**.</span></span>

    ![Nome della registrazione attività nel campo Nome registrazione](./media/setup_rsa_tool_90.png)

8. <span data-ttu-id="553cf-518">Andare a **Gestione informazioni sul prodotto \> Prodotti** e selezionare **Nuovo** per aprire la pagina in cui la registrazione attività originale, **Creare un prodotto**, è stata registrata.</span><span class="sxs-lookup"><span data-stu-id="553cf-518">Go to **Product information management \> Products**, and select **New** to open the page where the original task recording, **Create a product**, was recorded.</span></span>
9. <span data-ttu-id="553cf-519">Selezionare **Inserisci passaggio**.</span><span class="sxs-lookup"><span data-stu-id="553cf-519">Select **Insert step**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="553cf-520">Il nuovo passaggio viene inserito **dopo** il passaggio selezionato nel riquadro.</span><span class="sxs-lookup"><span data-stu-id="553cf-520">The new step is inserted **after** the step that you selected in the pane.</span></span>

    ![Pulsante Inserisci passaggio](./media/setup_rsa_tool_91.png)

10. <span data-ttu-id="553cf-522">Fare clic con il pulsante destro del mouse sul campo **Numero prodotto** e selezionare **Registrazione attività \> Copia**.</span><span class="sxs-lookup"><span data-stu-id="553cf-522">Right-click the **Product number** field, and then select **Task recorder \> Copy**.</span></span>

    ![Comando Copia](./media/setup_rsa_tool_92.png)

11. <span data-ttu-id="553cf-524">Un nuovo passaggio viene aggiunto nel riquadro.</span><span class="sxs-lookup"><span data-stu-id="553cf-524">A new step is added in the pane.</span></span> <span data-ttu-id="553cf-525">Annotare il valore nel campo **Numero prodotto**, poiché sarà necessario in seguito.</span><span class="sxs-lookup"><span data-stu-id="553cf-525">Make a note of the value in the **Product number** field, because you will need it later.</span></span>

    ![Nuovo passaggio aggiunto](./media/setup_rsa_tool_93.png)

12. <span data-ttu-id="553cf-527">Selezionare **Fine modifica**.</span><span class="sxs-lookup"><span data-stu-id="553cf-527">Select **Done editing**.</span></span>
13. <span data-ttu-id="553cf-528">Selezionare **Salvare in Lifecycle Services** e associare la nuova registrazione attività alla stessa libreria BPM e allo stesso processo aziendale a cui la registrazione attività originale era associata.</span><span class="sxs-lookup"><span data-stu-id="553cf-528">Select **Save to Lifecycle Services**, and associate the new task recording with the same BPM library and business process that the original task recording was associated with.</span></span> <span data-ttu-id="553cf-529">Per ulteriori informazioni, vedere la sezione [Creare una registrazione attività e salvarla nella libreria BPM](#create-a-task-recording-and-save-it-to-the-bpm-library).</span><span class="sxs-lookup"><span data-stu-id="553cf-529">For more information, see the [Create a task recording and save it to the BPM library](#create-a-task-recording-and-save-it-to-the-bpm-library) section.</span></span>
14. <span data-ttu-id="553cf-530">Passare alla libreria BPM e selezionare **Test case di sincronizzazione** per sovrascrivere la registrazione attività associata al test case in Azure DevOps, come descritto nella sezione [Testare la sincronizzazione da BPM a Azure DevOps](#test-the-synchronization-from-bpm-to-azure-devops).</span><span class="sxs-lookup"><span data-stu-id="553cf-530">Go to the BPM library, and select **Sync testcases** to overwrite the task recording that is attached to the test case in Azure DevOps, as described in the [Test the synchronization from BPM to Azure DevOps](#test-the-synchronization-from-bpm-to-azure-devops) section.</span></span>
15. <span data-ttu-id="553cf-531">Aprire RSAT e selezionare **Carica** per caricare di nuovo tutti i test case nel gruppo di test.</span><span class="sxs-lookup"><span data-stu-id="553cf-531">Open RSAT, and select **Load** to reload all the test cases in the test suite.</span></span> <span data-ttu-id="553cf-532">È necessario rigenerare i file di automazione e di parametri per il test case appropriato selezionando il test case e quindi **Nuovo \> Genera file di esecuzione di test e di parametri**, come descritto nella sezione [Caricare ed eseguire test case](#load-and-run-test-cases).</span><span class="sxs-lookup"><span data-stu-id="553cf-532">You must regenerate the automation and parameter files for the appropriate test case by selecting the test case and then selecting **New \> Generate Test Execution and Parameter files**, as described in the [Load and run test cases](#load-and-run-test-cases) section.</span></span>

    > [!NOTE]
    > <span data-ttu-id="553cf-533">Se il file di parametri di Excel era aperto, la rigenerazione avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="553cf-533">If the Excel parameter file was left open, regeneration will fail.</span></span> <span data-ttu-id="553cf-534">Di conseguenza, verificare che il file di parametri di Excel per il test case venga chiuso prima di generare il nuovo file di parametri di Excel.</span><span class="sxs-lookup"><span data-stu-id="553cf-534">Therefore, make sure that the Excel parameter file for the test case is closed before you generate the new Excel parameter file.</span></span>

16. <span data-ttu-id="553cf-535">Selezionare **Modifica** per aprire il nuovo file di parametri di Excel.</span><span class="sxs-lookup"><span data-stu-id="553cf-535">Select **Edit** to open the new Excel parameter file.</span></span> <span data-ttu-id="553cf-536">Verrà visualizzata una nuova voce **Variabile salvata** nella riga 9.</span><span class="sxs-lookup"><span data-stu-id="553cf-536">You will see a new **Saved variable** entry on line 9.</span></span> <span data-ttu-id="553cf-537">Questa variabile, **{{ecoResProductCreate\_Identification\_ProductNumber\_Copy}}**, viene salvata nel file XML della registrazione attività e può essere utilizzata nei test successivi.</span><span class="sxs-lookup"><span data-stu-id="553cf-537">This variable, **{{EcoResProductCreate\_Identification\_ProductNumber\_Copy}}**, is saved in the task recording's XML file and can be used in subsequent tests.</span></span>

    ![Voce di variabile salvata](./media/setup_rsa_tool_94.png)

#### <a name="create-a-new-test-case"></a><span data-ttu-id="553cf-539">Creare un nuovo test case</span><span class="sxs-lookup"><span data-stu-id="553cf-539">Create a new test case</span></span>

1. <span data-ttu-id="553cf-540">Andare alla libreria BPM **RSAT**.</span><span class="sxs-lookup"><span data-stu-id="553cf-540">Go to the **RSAT** BPM library.</span></span>
2. <span data-ttu-id="553cf-541">Selezionare **Processo aziendale di supporto di esempio**, quindi a destra, selezionare **Modalità di modifica**.</span><span class="sxs-lookup"><span data-stu-id="553cf-541">Select the **Sample Support Business Process** process, and then, on the right, select **Edit mode**.</span></span>
3. <span data-ttu-id="553cf-542">Impostare i campi **Nome** e **Descrizione** su **Rilasciare un prodotto**.</span><span class="sxs-lookup"><span data-stu-id="553cf-542">Change the value of both the **Name** field and the **Description** field to **Release a product**.</span></span> <span data-ttu-id="553cf-543">Quindi selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="553cf-543">Then select **Save**.</span></span>

    ![Nome e descrizione modificati per rilasciare un prodotto](./media/setup_rsa_tool_95.png)

#### <a name="create-a-new-task-recording-that-has-a-validate-function"></a><span data-ttu-id="553cf-545">Creare una nuova registrazione attività che include una funzione Convalida</span><span class="sxs-lookup"><span data-stu-id="553cf-545">Create a new task recording that has a Validate function</span></span>

- <span data-ttu-id="553cf-546">Creare una registrazione attività per rilasciare il prodotto creato in precedenza alla persona giuridica USRT.</span><span class="sxs-lookup"><span data-stu-id="553cf-546">Create a task recording to release the product that was created earlier to the USRT legal entity.</span></span> <span data-ttu-id="553cf-547">Per ulteriori informazioni, vedere la sezione [Creare una registrazione attività e salvarla nella libreria BPM](#create-a-task-recording-and-save-it-to-the-bpm-library).</span><span class="sxs-lookup"><span data-stu-id="553cf-547">For more information, see the [Create a task recording and save it to the BPM library](#create-a-task-recording-and-save-it-to-the-bpm-library) section.</span></span>

    > [!NOTE]
    > <span data-ttu-id="553cf-548">Per i test case concatenati, è sempre consigliabile individuare o filtrare il record necessario *digitando manualmente il valore del campo*.</span><span class="sxs-lookup"><span data-stu-id="553cf-548">For chained test cases, we always recommend that you find or filter for the record that you require by *manually typing the value of the field*.</span></span> <span data-ttu-id="553cf-549">In tal modo, lo strumento può determinare il record in base al quale eseguire l'azione nel test case successivo.</span><span class="sxs-lookup"><span data-stu-id="553cf-549">In that way, the tool can determine the record that the action must be taken against in the subsequent test case.</span></span>

    ![Nuova registrazione attività che include una funzione Convalida](./media/setup_rsa_tool_96.png)

    <span data-ttu-id="553cf-551">Come illustrato nella figura precedente, dopo l'individuazione del prodotto mediante il filtro rapido, ma prima di selezionare **Rilascia prodotti**, si convalida il valore del campo **Numero prodotto** per assicurarsi che l'ID prodotto è l'ID prodotto creato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="553cf-551">As the preceding illustration shows, after the product is found by using the Quick Filter, but before you select **Release products**, you validate the value of the **Product number** field to make sure that the product ID is the product ID that was created earlier.</span></span> <span data-ttu-id="553cf-552">Per convalidare il valore, fare clic con il pulsante destro del mouse sul campo **Numero prodotto** e scegliere **Registrazione attività \> Convalida \> Valore corrente**.</span><span class="sxs-lookup"><span data-stu-id="553cf-552">To validate the value, right-click the **Product number** field, and then select **Task recorder \> Validate \> Current Value**.</span></span>

    ![Convalidare il valore corrente](./media/setup_rsa_tool_97.png)

#### <a name="save-the-task-recording-to-bpm"></a><span data-ttu-id="553cf-554">Salvare la registrazione attività in BPM</span><span class="sxs-lookup"><span data-stu-id="553cf-554">Save the task recording to BPM</span></span>

1. <span data-ttu-id="553cf-555">Al termine della registrazione attività, selezionare **Salvare in Lifecycle Services**.</span><span class="sxs-lookup"><span data-stu-id="553cf-555">After the task recording is completed, select **Save to Lifecycle Services**.</span></span>

    ![Opzioni di salvataggio](./media/setup_rsa_tool_98.png)

2. <span data-ttu-id="553cf-557">Le informazioni sulla libreria vengono caricate da LCS.</span><span class="sxs-lookup"><span data-stu-id="553cf-557">Library information is loaded from LCS.</span></span>

    ![Indicatore di stato](./media/setup_rsa_tool_99.png)

3. <span data-ttu-id="553cf-559">Selezionare la libreria BPM a cui associare la registrazione attività.</span><span class="sxs-lookup"><span data-stu-id="553cf-559">Select the BPM library to associate the task recording with.</span></span> <span data-ttu-id="553cf-560">Per questa esercitazione, selezionare la libreria BPM **RSAT** creata in precedenza e il processo aziendale **Rilasciare un prodotto** sottostante.</span><span class="sxs-lookup"><span data-stu-id="553cf-560">For this tutorial, select the **RSAT** BPM library that was created earlier and the **Release a product** business process under it.</span></span> <span data-ttu-id="553cf-561">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="553cf-561">Then select **OK**.</span></span>

#### <a name="sync-bpm-to-azure-devops"></a><span data-ttu-id="553cf-562">Sincronizzare BPM con Azure DevOps</span><span class="sxs-lookup"><span data-stu-id="553cf-562">Sync BPM to Azure DevOps</span></span>

1. <span data-ttu-id="553cf-563">Passare alla libreria BPM e aprire la libreria **RSAT**.</span><span class="sxs-lookup"><span data-stu-id="553cf-563">Go to the BPM library, and open the **RSAT** library.</span></span>
2. <span data-ttu-id="553cf-564">Selezionare **Sincronizzazione VSTS** e quindi **Test case di sincronizzazione**.</span><span class="sxs-lookup"><span data-stu-id="553cf-564">Select **VSTS sync** and then **Sync test cases**.</span></span> <span data-ttu-id="553cf-565">Per ulteriori informazioni, vedere la sezione [Testare la sincronizzazione da BPM a Azure DevOps](#test-the-synchronization-from-bpm-to-azure-devops).</span><span class="sxs-lookup"><span data-stu-id="553cf-565">For more information, see the [Test the synchronization from BPM to Azure DevOps](#test-the-synchronization-from-bpm-to-azure-devops) section.</span></span>

    <span data-ttu-id="553cf-566">Al termine della sincronizzazione, il nuovo elemento di lavoro e il test case corrispondente per il processo aziendale **Rilasciare un prodotto** vengono visualizzati in Azure DevOps in **Boards \> Elementi di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="553cf-566">After the synchronization is completed, the new work item and the corresponding test case for the **Release a product** business process appear in Azure DevOps at **Boards \> Work Items**.</span></span>

#### <a name="add-the-new-test-case-to-the-existing-test-suite"></a><span data-ttu-id="553cf-567">Aggiungere il nuovo test case al gruppo di test esistente</span><span class="sxs-lookup"><span data-stu-id="553cf-567">Add the new test case to the existing test suite</span></span>

1. <span data-ttu-id="553cf-568">Passare a **Piani di test \> Piani di test** e selezionare il piano **Piano di test RSAT**.</span><span class="sxs-lookup"><span data-stu-id="553cf-568">Go to **Test plans \> Test plans**, and select the **RSAT Test Plan** plan.</span></span>
2. <span data-ttu-id="553cf-569">Selezionare **Aggiungi esistente**.</span><span class="sxs-lookup"><span data-stu-id="553cf-569">Select **Add existing**.</span></span>
3. <span data-ttu-id="553cf-570">Nella pagina **Aggiungi test case a gruppo**, selezionare **Esegui query**.</span><span class="sxs-lookup"><span data-stu-id="553cf-570">On the **Add test cases to suite** page, select **Run query**.</span></span>
4. <span data-ttu-id="553cf-571">Selezionare il nuovo test case creato per **Rilasciare un prodotto** e selezionare **Aggiungi test case** in basso a destra nella pagina (questo pulsante non è presente nella seguente illustrazione).</span><span class="sxs-lookup"><span data-stu-id="553cf-571">Select the new test case that was created for **Release a product**, and then select **Add test cases** in the lower-right corner of the page (this button isn't shown in the following illustration).</span></span>

    ![Pagina Aggiungi test case a gruppo](./media/setup_rsa_tool_100.png)

    <span data-ttu-id="553cf-573">Nel gruppo di test sono ora presenti due test case.</span><span class="sxs-lookup"><span data-stu-id="553cf-573">The test suite now has two test cases.</span></span>

    ![Gruppo di test con due test case](./media/setup_rsa_tool_101.png)

#### <a name="load-test-cases-into-rsat"></a><span data-ttu-id="553cf-575">Caricare test case in RSAT</span><span class="sxs-lookup"><span data-stu-id="553cf-575">Load test cases into RSAT</span></span>

1. <span data-ttu-id="553cf-576">Aprire RSAT e selezionare **Carica**.</span><span class="sxs-lookup"><span data-stu-id="553cf-576">Open RSAT, and select **Load**.</span></span>
2. <span data-ttu-id="553cf-577">I test case vengono caricati e viene visualizzato l'avviso "Questa operazione sovrascriverà i file di dati di test di Excel; le modifiche locali andranno perse.</span><span class="sxs-lookup"><span data-stu-id="553cf-577">The test cases are loaded, and you receive a warning that states, "This action will overwrite Excel test data files, local changes will be lost.</span></span> <span data-ttu-id="553cf-578">Continuare?".</span><span class="sxs-lookup"><span data-stu-id="553cf-578">Do you want to proceed?"</span></span> <span data-ttu-id="553cf-579">Selezionare **Sì** per aggiornare i file di parametri di Excel nel sistema locale ma non i file di parametri di Excel caricati in Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="553cf-579">Select **Yes** to update the Excel parameter files in the local system but not the Excel parameter files that were uploaded to Azure DevOps.</span></span>

    ![Messaggio di avviso](./media/setup_rsa_tool_102.png)

    <span data-ttu-id="553cf-581">Entrambi i case test vengono caricati, insieme al file di parametri di Excel per il primo test case.</span><span class="sxs-lookup"><span data-stu-id="553cf-581">Both the test cases are loaded, together with the Excel parameter file for the first test case.</span></span> <span data-ttu-id="553cf-582">Poiché si è selezionato **Carica** nell'ultima esecuzione, i file di parametri vengono acquisiti da Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="553cf-582">Because you selected **Upload** in the last run, the parameter files are pulled from Azure DevOps.</span></span>

    ![Test case caricati](./media/setup_rsa_tool_103.png)

3. <span data-ttu-id="553cf-584">Selezionare solo il secondo test case e quindi **Nuovo \> Genera file di esecuzione di test e di parametri**.</span><span class="sxs-lookup"><span data-stu-id="553cf-584">Select only the second test case, and then select **New \> Generate test execution and parameter files**.</span></span>

#### <a name="edit-the-excel-parameter-file"></a><span data-ttu-id="553cf-585">Modificare il file di parametri di Excel</span><span class="sxs-lookup"><span data-stu-id="553cf-585">Edit the Excel parameter file</span></span>

1. <span data-ttu-id="553cf-586">Selezionare solo il secondo test case e quindi **Modifica** per aprire il file di parametri di Excel corrispondente.</span><span class="sxs-lookup"><span data-stu-id="553cf-586">Select only the second test case, and then select **Edit** to open the corresponding Excel parameter file.</span></span>
2. <span data-ttu-id="553cf-587">Copiare la variabile salvata **{{EcoResProductCreate\_Identification\_ProductNumber\_Copy}}** (vedere la sezione [Modificare una registrazione attività esistente per creare una variabile salvata](#modify-an-existing-task-recording-to-create-a-saved-variable)) dal primo test case in tutti i campi in cui il numero di prodotto è utilizzato.</span><span class="sxs-lookup"><span data-stu-id="553cf-587">Copy the **{{EcoResProductCreate\_Identification\_ProductNumber\_Copy}}** saved variable (see the [Modify an existing task recording to create a saved variable](#modify-an-existing-task-recording-to-create-a-saved-variable) section) from the first test case into all the fields where the product number is used.</span></span> <span data-ttu-id="553cf-588">In questo caso, si copia la variabile nei campi **Numero prodotto** **Convalida numero prodotto** nel foglio **EcoResProductListPage**.</span><span class="sxs-lookup"><span data-stu-id="553cf-588">In this case, you copy the variable into the **Product number** and **Validate Product number** fields on the **EcoResProductListPage** sheet.</span></span>

    ![Campi Numero prodotto e Convalida numero prodotto](./media/setup_rsa_tool_104.png)

    > [!NOTE]
    > <span data-ttu-id="553cf-590">Le variabili possono essere passate da un test all'altro solo durante la stessa esecuzione di test.</span><span class="sxs-lookup"><span data-stu-id="553cf-590">Variables can be passed between tests only during the same test run.</span></span> <span data-ttu-id="553cf-591">I nomi delle variabili devono corrispondere esattamente.</span><span class="sxs-lookup"><span data-stu-id="553cf-591">The names of the variables must match exactly.</span></span>

3. <span data-ttu-id="553cf-592">Selezionare **Salva**, quindi chiudere la cartella di lavoro di Excel.</span><span class="sxs-lookup"><span data-stu-id="553cf-592">Select **Save**, and then close the Excel workbook.</span></span>
4. <span data-ttu-id="553cf-593">Selezionare **Carica** per salvare le modifiche apportate al file di parametri di Excel.</span><span class="sxs-lookup"><span data-stu-id="553cf-593">Select **Upload** to save the changes that you made to the Excel parameter file.</span></span>

#### <a name="run-the-chained-test-cases"></a><span data-ttu-id="553cf-594">Eseguire i test case concatenati</span><span class="sxs-lookup"><span data-stu-id="553cf-594">Run the chained test cases</span></span>

1. <span data-ttu-id="553cf-595">Selezionare entrambi i test case e selezionare **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="553cf-595">Select both the test cases, and then select **Run**.</span></span>
2. <span data-ttu-id="553cf-596">Verificare che entrambi i test casi abbiano avuto esito positivo.</span><span class="sxs-lookup"><span data-stu-id="553cf-596">Verify that both test cases have passed.</span></span>

    ![Campo Risultato impostato su Superato per entrambi i test case](./media/setup_rsa_tool_105.png)
