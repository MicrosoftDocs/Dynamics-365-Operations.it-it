---
title: Configurazione di Finance Insights per l'anteprima pubblica (anteprima) - Versione 10.0.20 e successive
description: Questo argomento spiega come configurare il sistema per utilizzare le funzionalità disponibili in Finance Insights per l'anteprima pubblica nella versione 10.0.20 e successive.
author: ShivamPandey-msft
ms.date: 06/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2021-06-03
ms.dyn365.ops.version: AX 10.0.20
ms.openlocfilehash: 613bd4816e2f0c4fbb56cf79779a08c6a09592bd
ms.sourcegitcommit: 655b0e16c7aef6182cd58bc816b901470e1bb2ce
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/10/2021
ms.locfileid: "6222614"
---
# <a name="configuration-for-finance-insights-for-public-preview-preview---version-10020-and-later"></a><span data-ttu-id="44be2-103">Configurazione di Finance Insights per l'anteprima pubblica (anteprima) - Versione 10.0.20 e successive</span><span class="sxs-lookup"><span data-stu-id="44be2-103">Configuration for Finance insights for public preview (preview) - version 10.0.20 and later</span></span>

[!include [banner](../includes/banner.md)]

[!include [preview banner](../includes/preview-banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="44be2-104">Finance Insights combina le funzionalità di Microsoft Dynamics 365 Finance con Dataverse, Azure e AI Builder per fornire potenti strumenti di previsione per la tua organizzazione.</span><span class="sxs-lookup"><span data-stu-id="44be2-104">Finance insights combines functionality from Microsoft Dynamics 365 Finance with Dataverse, Azure, and AI Builder to provide powerful forecasting tools for your organization.</span></span> <span data-ttu-id="44be2-105">Questo argomento spiega come configurare Dynamics 365 Finance version 10.0.20 in modo che il sistema possa usare le funzionalità disponibili in Finance Insights per l'anteprima pubblica.</span><span class="sxs-lookup"><span data-stu-id="44be2-105">This topic explains how to configure Dynamics 365 Finance version 10.0.20 so that your system can use the capabilities that are available in Finance insights public preview.</span></span>

> [!NOTE]
> <span data-ttu-id="44be2-106">I passaggi di configurazione descritti in questo argomento si applicano solo a Finance versione 10.0.20 e successive.</span><span class="sxs-lookup"><span data-stu-id="44be2-106">The configuration steps that are described in this topic apply only to Finance version 10.0.20 and later.</span></span> <span data-ttu-id="44be2-107">'Per impostare Finance Insight sulla versione 10.0.19 e precedenti, vedi [Configurazione per Finance Insights - Versioni fino a 10.0.18](configure-for-fin-insites.md).</span><span class="sxs-lookup"><span data-stu-id="44be2-107">'To set up Finance insights on version 10.0.19 and earlier, see [Configuration for Finance insights - versions up to 10.0.18](configure-for-fin-insites.md).</span></span>

## <a name="deploy-finance"></a><span data-ttu-id="44be2-108">Distribuzione di Finance</span><span class="sxs-lookup"><span data-stu-id="44be2-108">Deploy Finance</span></span>

<span data-ttu-id="44be2-109">Attieniti a questa procedura per distribuire gli ambienti.</span><span class="sxs-lookup"><span data-stu-id="44be2-109">Follow these steps to deploy the environments.</span></span>

1. <span data-ttu-id="44be2-110">In Microsoft Dynamics Lifecycle Services (LCS), crea o aggiorna un ambiente Finance.</span><span class="sxs-lookup"><span data-stu-id="44be2-110">In Microsoft Dynamics Lifecycle Services (LCS), create or update a Finance environment.</span></span> <span data-ttu-id="44be2-111">L'ambiente richiede la versione dell'app 10.0.20 o successiva delle app Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="44be2-111">The environment requires app version 10.0.20 or later of Finance and Operations apps.</span></span>
2. <span data-ttu-id="44be2-112">L'ambiente deve essere un ambiente ad alta disponibilità (HA) in Sandbox.</span><span class="sxs-lookup"><span data-stu-id="44be2-112">The environment must be a high-availability (HA) environment in Sandbox.</span></span> <span data-ttu-id="44be2-113">(Questo tipo di ambiente è noto anche come ambiente Tier-2). Per altre informazioni, vedi [Pianificazione ambientale](../../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md).</span><span class="sxs-lookup"><span data-stu-id="44be2-113">(This type of environment is also known as a Tier-2 environment.) For more information, see [Environment planning](../../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md).</span></span>
3. <span data-ttu-id="44be2-114">Se stai configurando Finance Insights in un ambiente sandbox, potresti dover copiare i dati di produzione in tale ambiente affinché le stime funzionino.</span><span class="sxs-lookup"><span data-stu-id="44be2-114">If you are configuring Finance insights in a Sandbox environment, you might need to copy production data to that environment for predictions to work.</span></span> <span data-ttu-id="44be2-115">Il modello di stima utilizza più anni di dati per creare previsioni.</span><span class="sxs-lookup"><span data-stu-id="44be2-115">The prediction model uses multiple years of data to build predictions.</span></span> <span data-ttu-id="44be2-116">I dati della demo di Contoso non contengono dati storici sufficienti per addestrare adeguatamente il modello di stima.</span><span class="sxs-lookup"><span data-stu-id="44be2-116">The Contoso demo data doesn’t contain enough historical data to train the prediction model adequately.</span></span> 

## <a name="configure-dataverse"></a><span data-ttu-id="44be2-117">Configura Dataverse</span><span class="sxs-lookup"><span data-stu-id="44be2-117">Configure Dataverse</span></span>

<span data-ttu-id="44be2-118">Segui questa procedura per configurare Dataverse per Finance insights.</span><span class="sxs-lookup"><span data-stu-id="44be2-118">Follow these steps to configure Dataverse for Finance insights.</span></span>

1. <span data-ttu-id="44be2-119">In LCS, apri la pagina dell'ambiente e verifica che la sezione **Integrazione di Power Platform** sia già configurata.</span><span class="sxs-lookup"><span data-stu-id="44be2-119">In LCS, open the environment page, and verify that the **Power Platform Integration** section is already set up.</span></span>

    - <span data-ttu-id="44be2-120">Se è già configurata, il nome dell'ambiente Dataverse collegato all'ambiente Finance dovrebbe essere incluso nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="44be2-120">If it's already set up, the Dataverse environment name that is linked to the Finance environment should be listed.</span></span>
    - <span data-ttu-id="44be2-121">In caso contrario, segui questi passaggi:</span><span class="sxs-lookup"><span data-stu-id="44be2-121">If it isn't yet set up, follow these steps:</span></span>

        1. <span data-ttu-id="44be2-122">Nella sezione **Integrazione di Power Platform**, seleziona **Configurazione**.</span><span class="sxs-lookup"><span data-stu-id="44be2-122">In the **Power Platform Integration** section, select **Setup**.</span></span> <span data-ttu-id="44be2-123">La configurazione dell'ambiente potrebbe richiedere fino a un'ora.</span><span class="sxs-lookup"><span data-stu-id="44be2-123">Setup of the environment might take up to an hour.</span></span>
        2. <span data-ttu-id="44be2-124">Se l'ambiente Dataverse è correttamente configurato, il nome dell'ambiente Dataverse collegato all'ambiente Finance dovrebbe essere incluso nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="44be2-124">If the Dataverse environment is successfully set up, the Dataverse environment name that is linked to the Finance environment should be listed.</span></span>

        > [!NOTE]
        > <span data-ttu-id="44be2-125">Dopo aver completato la configurazione dell'ambiente, **non** selezionare **Collegamento a CDS per le app**.</span><span class="sxs-lookup"><span data-stu-id="44be2-125">After you complete the environment setup, do **not** select **Link to CDS for Apps**.</span></span> <span data-ttu-id="44be2-126">Questo pulsante non è necessario per Finance Insights.</span><span class="sxs-lookup"><span data-stu-id="44be2-126">This button isn't required for Finance insights.</span></span> <span data-ttu-id="44be2-127">Se lo selezioni, non sarai in grado di configurare i componenti aggiuntivi dell'ambiente richiesti in LCS.</span><span class="sxs-lookup"><span data-stu-id="44be2-127">If you select it, you won't be able to configure the required environment add-ins in LCS.</span></span>

## <a name="configure-azure"></a><span data-ttu-id="44be2-128">Configurazione di Azure</span><span class="sxs-lookup"><span data-stu-id="44be2-128">Configure Azure</span></span>

### <a name="use-azure-cloud-shell-to-set-up-finance-insights-data-lake-resources"></a><span data-ttu-id="44be2-129">Utilizzare Azure Cloud Shell per configurare le risorse Data Lake di Finance Insights</span><span class="sxs-lookup"><span data-stu-id="44be2-129">Use Azure Cloud Shell to set up Finance insights Data Lake resources</span></span>

# <a name="use-a-windows-powershell-script"></a>[<span data-ttu-id="44be2-130">Utilizzare uno script di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="44be2-130">Use a Windows PowerShell script</span></span>](#tab/use-a-powershell-script)

<span data-ttu-id="44be2-131">È stato fornito uno script di Windows PowerShell, in modo da poter configurare facilmente le risorse di Azure descritte in [Configurare l'esportazione in Azure Data Lake](../../fin-ops-core/dev-itpro/data-entities/configure-export-data-lake.md).</span><span class="sxs-lookup"><span data-stu-id="44be2-131">A Windows PowerShell script has been provided so that you can easily set up the Azure resources that are described in [Configure export to Azure Data Lake](../../fin-ops-core/dev-itpro/data-entities/configure-export-data-lake.md).</span></span> <span data-ttu-id="44be2-132">Se preferisci eseguire la configurazione manualmente, salta questa procedura e continua con la procedura della sezione [Configurazione manuale](#manual-setup).</span><span class="sxs-lookup"><span data-stu-id="44be2-132">If you prefer to do the setup manually, skip this procedure, and complete the procedure in the [Manual setup](#manual-setup) section instead.</span></span>

> [!NOTE]
> <span data-ttu-id="44be2-133">Utilizza la procedura seguente per eseguire lo script di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="44be2-133">Use the following procedure to run the Windows PowerShell script.</span></span> <span data-ttu-id="44be2-134">La configurazione potrebbe non funzionare se utilizzi l'opzione **Prova** nell'interfaccia della riga di comando di Azure o se esegui lo script nel computer.</span><span class="sxs-lookup"><span data-stu-id="44be2-134">The setup might not work if you use the **Try it** option in Azure CLI or if you run the script on your computer.</span></span>

<span data-ttu-id="44be2-135">Attieniti alla seguente procedura per usare lo script Windows PowerShell per configurare Azure.</span><span class="sxs-lookup"><span data-stu-id="44be2-135">Follow these steps to use the Windows PowerShell script to configure Azure.</span></span> <span data-ttu-id="44be2-136">Devi disporre dei diritti per creare un gruppo di risorse di Azure, risorse di Azure e un'applicazione Azure AD.</span><span class="sxs-lookup"><span data-stu-id="44be2-136">You must have rights to create an Azure resource group, Azure resources, and an Azure AD application.</span></span> <span data-ttu-id="44be2-137">Per informazioni sulle autorizzazioni obbligatorie, vedi [Controllare le autorizzazioni di Azure AD](/azure/active-directory/develop/howto-create-service-principal-portal#permissions-required-for-registering-an-app).</span><span class="sxs-lookup"><span data-stu-id="44be2-137">For information about the required permissions, see [Check Azure AD permissions](/azure/active-directory/develop/howto-create-service-principal-portal#permissions-required-for-registering-an-app).</span></span>

1. <span data-ttu-id="44be2-138">Nel [portale di Azure](https://portal.azure.com), vai alla sottoscrizione di Azure di destinazione.</span><span class="sxs-lookup"><span data-stu-id="44be2-138">In the [Azure portal](https://portal.azure.com), go to your target Azure subscription.</span></span>
2. <span data-ttu-id="44be2-139">Seleziona **Cloud Shell** a destra del campo **Cerca**.</span><span class="sxs-lookup"><span data-stu-id="44be2-139">Select **Cloud Shell** to the right of the **Search** field.</span></span>
3. <span data-ttu-id="44be2-140">Seleziona **PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="44be2-140">Select **PowerShell**.</span></span>
4. <span data-ttu-id="44be2-141">Crea lo spazio di archiviazione, se ti viene chiesto di farlo.</span><span class="sxs-lookup"><span data-stu-id="44be2-141">Create storage if you're prompted to create it.</span></span>
5. <span data-ttu-id="44be2-142">Nella scheda **Interfaccia della riga di comando di Azure**, seleziona **Copia**.</span><span class="sxs-lookup"><span data-stu-id="44be2-142">On the **Azure CLI** tab, select **Copy**.</span></span>
6. <span data-ttu-id="44be2-143">In Blocco note, apri un nuovo file e incolla lo script di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="44be2-143">In Notepad, open a new file, and paste in the Windows PowerShell script.</span></span>
7. <span data-ttu-id="44be2-144">Salva il file come **ConfigureDataLake.ps1**.</span><span class="sxs-lookup"><span data-stu-id="44be2-144">Save the file as **ConfigureDataLake.ps1**.</span></span>
8. <span data-ttu-id="44be2-145">Carica lo script di Windows PowerShell nella sessione utilizzando l'opzione di menu per il caricamento in Cloud Shell.</span><span class="sxs-lookup"><span data-stu-id="44be2-145">Upload the Windows PowerShell script to the session by using the menu option for upload in Cloud Shell.</span></span>
9. <span data-ttu-id="44be2-146">Esegui lo script **.\ConfigureDataLake.ps1**.</span><span class="sxs-lookup"><span data-stu-id="44be2-146">Run the **.\ConfigureDataLake.ps1** script.</span></span>
10. <span data-ttu-id="44be2-147">Segui le istruzioni per eseguire lo script.</span><span class="sxs-lookup"><span data-stu-id="44be2-147">Follow the prompts to run the script.</span></span>
11. <span data-ttu-id="44be2-148">Utilizza le informazioni dall'output dello script per installare il componente aggiuntivo Esporta in Data Lake in LCS.</span><span class="sxs-lookup"><span data-stu-id="44be2-148">Use the information from the script output to install the Export to Data Lake add-in in LCS.</span></span>

### <a name="manual-setup"></a><span data-ttu-id="44be2-149">Configurazione manuale</span><span class="sxs-lookup"><span data-stu-id="44be2-149">Manual setup</span></span>

#### <a name="add-applications-to-the-azure-ad-tenant"></a><span data-ttu-id="44be2-150">Aggiungere applicazioni al tenant Azure AD</span><span class="sxs-lookup"><span data-stu-id="44be2-150">Add applications to the Azure AD tenant</span></span>

1. <span data-ttu-id="44be2-151">Nel [portale di Azure](https://portal.azure.com), passa a **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="44be2-151">In the [Azure portal](https://portal.azure.com), go to **Azure Active Directory**.</span></span>
2. <span data-ttu-id="44be2-152">Seleziona **Gestisci \> Applicazioni aziendali**.</span><span class="sxs-lookup"><span data-stu-id="44be2-152">Select **Manage \> Enterprise applications**.</span></span>
3. <span data-ttu-id="44be2-153">Cerca le seguenti applicazioni per ID app.</span><span class="sxs-lookup"><span data-stu-id="44be2-153">Search for the following applications by app ID.</span></span>

    | <span data-ttu-id="44be2-154">Domanda di lavoro</span><span class="sxs-lookup"><span data-stu-id="44be2-154">Application</span></span>                              | <span data-ttu-id="44be2-155">ID app</span><span class="sxs-lookup"><span data-stu-id="44be2-155">App ID</span></span>                               |
    |------------------------------------------|--------------------------------------|
    | <span data-ttu-id="44be2-156">Microservizi ERP Microsoft Dynamics</span><span class="sxs-lookup"><span data-stu-id="44be2-156">Microsoft Dynamics ERP Microservices</span></span>     | <span data-ttu-id="44be2-157">0cdb527f-a8d1-4bf8-9436-b352c68682b2</span><span class="sxs-lookup"><span data-stu-id="44be2-157">0cdb527f-a8d1-4bf8-9436-b352c68682b2</span></span> |
    | <span data-ttu-id="44be2-158">CDS microservizi ERP Microsoft Dynamics</span><span class="sxs-lookup"><span data-stu-id="44be2-158">Microsoft Dynamics ERP Microservices CDS</span></span> | <span data-ttu-id="44be2-159">703e2651-d3fc-48f5-942c-74274233dba8</span><span class="sxs-lookup"><span data-stu-id="44be2-159">703e2651-d3fc-48f5-942c-74274233dba8</span></span> |
    | <span data-ttu-id="44be2-160">Servizio di autorizzazione di AI Builder</span><span class="sxs-lookup"><span data-stu-id="44be2-160">AI Builder Authorization Service</span></span>         | <span data-ttu-id="44be2-161">ad40333e-9910-4b61-b281-e3aeeb8c3ef3</span><span class="sxs-lookup"><span data-stu-id="44be2-161">ad40333e-9910-4b61-b281-e3aeeb8c3ef3</span></span> |

<span data-ttu-id="44be2-162">Se non riesci a trovare nessuna delle applicazioni precedenti, prova i seguenti passaggi.</span><span class="sxs-lookup"><span data-stu-id="44be2-162">If you can't find any of the preceding applications, try the following steps.</span></span>

1. <span data-ttu-id="44be2-163">Sul tuo computer locale, nel menu **Start**, cerca **powershell**.</span><span class="sxs-lookup"><span data-stu-id="44be2-163">On your local computer, on the **Start** menu, search for **powershell**.</span></span>
2. <span data-ttu-id="44be2-164">Seleziona e tieni premuto (o fai clic con il pulsante destro del mouse su) **Windows PowerShell** e quindi seleziona **Esegui come amministratore**.</span><span class="sxs-lookup"><span data-stu-id="44be2-164">Select and hold (or right-click) **Windows PowerShell**, and then select **Run as administrator**.</span></span>
3. <span data-ttu-id="44be2-165">Esegui il comando seguente per installare il modulo **AzureAD**.</span><span class="sxs-lookup"><span data-stu-id="44be2-165">Run the following command to install the **AzureAD** module.</span></span>

    `Install-Module -Name AzureAD`

4. <span data-ttu-id="44be2-166">Se è necessario un provider NuGet per continuare, seleziona **Y** per installarlo.</span><span class="sxs-lookup"><span data-stu-id="44be2-166">If a NuGet provider is required to continue, select **Y** to install it.</span></span>
5. <span data-ttu-id="44be2-167">Se ricevi il messaggio "Repository non attendibile", seleziona **Y** per continuare.</span><span class="sxs-lookup"><span data-stu-id="44be2-167">If you receive an "Untrusted repository" message, select **Y** to continue.</span></span>
6. <span data-ttu-id="44be2-168">Per ciascuna applicazione che deve essere aggiunta, esegui i seguenti comandi per aggiungere l'applicazione ad Azure AD.</span><span class="sxs-lookup"><span data-stu-id="44be2-168">For each application that must be added, run the following commands to add the application to Azure AD.</span></span> <span data-ttu-id="44be2-169">Quando ti viene richiesto, accedi come amministratore Azure AD.</span><span class="sxs-lookup"><span data-stu-id="44be2-169">When you're prompted, sign in as the Azure AD administrator.</span></span>

    `Connect-AzureAD`

    `New-AzureADServicePrincipal –AppId <AppId>`

#### <a name="create-azure-resources"></a><span data-ttu-id="44be2-170">Creare risorse Azure</span><span class="sxs-lookup"><span data-stu-id="44be2-170">Create Azure resources</span></span>

> [!NOTE]
> <span data-ttu-id="44be2-171">Assicurati di creare le seguenti risorse nella stessa istanza di Azure AD in cui si trova l'ambiente Dataverse.</span><span class="sxs-lookup"><span data-stu-id="44be2-171">Make sure that you create the following resources in the same Azure AD instance that the Dataverse environment is in.</span></span> <span data-ttu-id="44be2-172">Non puoi utilizzare risorse da un'altra istanza di Azure AD.</span><span class="sxs-lookup"><span data-stu-id="44be2-172">You can't use resources from a different Azure AD instance.</span></span>

1. <span data-ttu-id="44be2-173">Crea un account di archiviazione:</span><span class="sxs-lookup"><span data-stu-id="44be2-173">Create a storage account:</span></span>

    1. <span data-ttu-id="44be2-174">Nel [portale di Azure](https://portal.azure.com), crea un account di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="44be2-174">In the [Azure portal](https://portal.azure.com), create a storage account.</span></span>
    2. <span data-ttu-id="44be2-175">Nella finestra di dialogo **Crea account di archiviazione**, imposta i seguenti campi:</span><span class="sxs-lookup"><span data-stu-id="44be2-175">In the **Create storage account** dialog box, set the following fields:</span></span>

        - <span data-ttu-id="44be2-176">**Posizione**: seleziona il data center in cui si trova il tuo ambiente.</span><span class="sxs-lookup"><span data-stu-id="44be2-176">**Location** – Select the data center where your environment is located.</span></span>
        - <span data-ttu-id="44be2-177">**Prestazioni**: è compatibile selezionare **Standard**.</span><span class="sxs-lookup"><span data-stu-id="44be2-177">**Performance** – We recommend that you select **Standard**.</span></span>
        - <span data-ttu-id="44be2-178">**Tipo di account**: devi selezionare **StorageV2**.</span><span class="sxs-lookup"><span data-stu-id="44be2-178">**Account kind** – You must select **StorageV2**.</span></span>

    3. <span data-ttu-id="44be2-179">Nella finestra di dialogo **Opzioni avanzate**, per l'opzione **Data Lake Storage Gen2**, seleziona **Abilita** nella funzionalità **Spazi dei nomi gerarchici**.</span><span class="sxs-lookup"><span data-stu-id="44be2-179">In the **Advanced options** dialog box, for the **Data Lake storage Gen2** option, select **Enable** under the **Hierarchical namespaces** feature.</span></span> <span data-ttu-id="44be2-180">Se non abiliti questa funzionalità, non puoi utilizzare i dati che le app Finance and Operations scrivono utilizzando servizi come i flussi di dati di Power BI.</span><span class="sxs-lookup"><span data-stu-id="44be2-180">If you don't enable this feature, you can't consume data that Finance and Operations apps write by using services such as Power BI data flows.</span></span>
    4. <span data-ttu-id="44be2-181">Seleziona **Rivedi e crea**.</span><span class="sxs-lookup"><span data-stu-id="44be2-181">Select **Review and create**.</span></span> <span data-ttu-id="44be2-182">Al termine della distribuzione, la nuova risorsa verrà visualizzata nel portale di Azure.</span><span class="sxs-lookup"><span data-stu-id="44be2-182">When the deployment is completed, the new resource is shown in the Azure portal.</span></span>
    5. <span data-ttu-id="44be2-183">Vai all'account di archiviazione che hai creato.</span><span class="sxs-lookup"><span data-stu-id="44be2-183">Go to the storage account that you created.</span></span>
    6. <span data-ttu-id="44be2-184">Nel menu a sinistra, seleziona **Chiavi di accesso**.</span><span class="sxs-lookup"><span data-stu-id="44be2-184">On the left menu, select **Access keys**.</span></span>
    7. <span data-ttu-id="44be2-185">Copia e salva il nome il nome dell'account di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="44be2-185">Copy and save the name of the storage account.</span></span> <span data-ttu-id="44be2-186">Dovrai fornire questo valore in un secondo momento, quando configuri i segreti del Key Vault.</span><span class="sxs-lookup"><span data-stu-id="44be2-186">You will have to provide this value later, when you set up key vault secrets.</span></span>

2. <span data-ttu-id="44be2-187">Crea un Key Vault:</span><span class="sxs-lookup"><span data-stu-id="44be2-187">Create a key vault:</span></span>

    1. <span data-ttu-id="44be2-188">Nel [portale di Azure](https://portal.azure.com), crea un Key Vault.</span><span class="sxs-lookup"><span data-stu-id="44be2-188">In the [Azure portal](https://portal.azure.com), create a key vault.</span></span>
    2. <span data-ttu-id="44be2-189">Nella finestra di dialogo **Crea Key Vault**, nel campo **Posizione**, seleziona il data center in cui si trova il tuo ambiente.</span><span class="sxs-lookup"><span data-stu-id="44be2-189">In the **Create key vault** dialog box, in the **Location** field, select the data center where your environment is located.</span></span>
    3. <span data-ttu-id="44be2-190">Dopo aver creato il Key Vault, vai a **Panoramica di Key Vault**, quindi copia e salva il nome DNS.</span><span class="sxs-lookup"><span data-stu-id="44be2-190">After key vault is created, go to **Key Vault Overview**, and copy and save the DNS name.</span></span> <span data-ttu-id="44be2-191">Dovrai fornire questo valore in un secondo momento, quando configuri il componente aggiuntivo Data Lake.</span><span class="sxs-lookup"><span data-stu-id="44be2-191">You will have to provide this value later, when you set up the Data Lake add-in.</span></span>

3. <span data-ttu-id="44be2-192">Crea e registra un'applicazione Azure AD:</span><span class="sxs-lookup"><span data-stu-id="44be2-192">Create and register an Azure AD application:</span></span>

    1. <span data-ttu-id="44be2-193">Nel [portale di Azure](https://portal.azure.com), passa ad **Azure Active Directory**, quindi seleziona **Registrazioni app**.</span><span class="sxs-lookup"><span data-stu-id="44be2-193">In the [Azure portal](https://portal.azure.com), go to **Azure Active Directory**, and then select **App registrations**.</span></span>
    2. <span data-ttu-id="44be2-194">Seleziona **Nuova registrazione dell'applicazione** e imposta i seguenti campi:</span><span class="sxs-lookup"><span data-stu-id="44be2-194">Select **New application registration**, and set the following fields:</span></span>

        - <span data-ttu-id="44be2-195">**Nome**: immetti il nome dell'app.</span><span class="sxs-lookup"><span data-stu-id="44be2-195">**Name** – Enter the name of the app.</span></span>
        - <span data-ttu-id="44be2-196">**Tipo di applicazione**: seleziona **API Web**.</span><span class="sxs-lookup"><span data-stu-id="44be2-196">**Application type** – Select **Web API**.</span></span>
        - <span data-ttu-id="44be2-197">**Configurazione URI reindirizzamento**: immetti l'URL per la tua istanza di Dynamics 365, ad esempio, `https://yourdynamicsinstance.dynamics.com/auth`.</span><span class="sxs-lookup"><span data-stu-id="44be2-197">**Redirect URI setup** – Enter the URL for your Dynamics 365 instance, such as `https://yourdynamicsinstance.dynamics.com/auth`.</span></span>

    3. <span data-ttu-id="44be2-198">Vai all'app che hai appena creato e copia e salva il suo valore **ID applicazione (client)**.</span><span class="sxs-lookup"><span data-stu-id="44be2-198">Go to the app that you just created, and copy and save its **Application (client) ID** value.</span></span> <span data-ttu-id="44be2-199">Dovrai fornire questo valore in un secondo momento, quando configuri i segreti del Key Vault.</span><span class="sxs-lookup"><span data-stu-id="44be2-199">You will have to provide this value later, when you set up key vault secrets.</span></span>
    4. <span data-ttu-id="44be2-200">Vai ad **Autorizzazioni API** e segui questi passaggi:</span><span class="sxs-lookup"><span data-stu-id="44be2-200">Go to **API permissions**, and follow these steps:</span></span>

        1. <span data-ttu-id="44be2-201">Seleziona **Aggiungi un'autorizzazione**.</span><span class="sxs-lookup"><span data-stu-id="44be2-201">Select **Add a permission**.</span></span>
        2. <span data-ttu-id="44be2-202">Seleziona **Azure Key Vault**.</span><span class="sxs-lookup"><span data-stu-id="44be2-202">Select **Azure Key vault**.</span></span>
        3. <span data-ttu-id="44be2-203">Dopo aver selezionato le autorizzazioni delegate, seleziona **utente\_impersonificazione**.</span><span class="sxs-lookup"><span data-stu-id="44be2-203">After you select delegated permissions, select **user\_impersonation**.</span></span>
        4. <span data-ttu-id="44be2-204">Seleziona **Aggiungi autorizzazioni**.</span><span class="sxs-lookup"><span data-stu-id="44be2-204">Select **Add permissions**.</span></span>

    5. <span data-ttu-id="44be2-205">Nel menu dell'app, seleziona **Certificati \& segreti** e quindi segui questi passaggi per creare segreti di Key Vault:</span><span class="sxs-lookup"><span data-stu-id="44be2-205">On the menu for the app, select **Certificates \& secrets**, and then follow these steps to create Key Vault secrets:</span></span>

        1. <span data-ttu-id="44be2-206">Seleziona **Nuovo segreto client**.</span><span class="sxs-lookup"><span data-stu-id="44be2-206">Select **New client secret**.</span></span>
        2. <span data-ttu-id="44be2-207">Nel campo **Descrizione chiave** immetti un nome.</span><span class="sxs-lookup"><span data-stu-id="44be2-207">In the **Key Description** field, enter a name.</span></span>
        3. <span data-ttu-id="44be2-208">Seleziona una durata e quindi seleziona **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="44be2-208">Select a duration, and then select **Add**.</span></span> <span data-ttu-id="44be2-209">Un segreto viene generato nel campo **Valore**.</span><span class="sxs-lookup"><span data-stu-id="44be2-209">A secret is generated in the **Value** field.</span></span>
        4. <span data-ttu-id="44be2-210">Copia e salva il valore del segreto client.</span><span class="sxs-lookup"><span data-stu-id="44be2-210">Copy and save the client secret value.</span></span> <span data-ttu-id="44be2-211">Dovrai fornire questo valore in un secondo momento, quando configuri i segreti del Key Vault.</span><span class="sxs-lookup"><span data-stu-id="44be2-211">You will have to provide this value later, when you set up key vault secrets.</span></span>

4. <span data-ttu-id="44be2-212">Crea segreti Key Vault:</span><span class="sxs-lookup"><span data-stu-id="44be2-212">Create Key Vault secrets:</span></span>

    1. <span data-ttu-id="44be2-213">Vai al Key Vault creato in precedenza e seleziona **Segreti**.</span><span class="sxs-lookup"><span data-stu-id="44be2-213">Go to the key vault that you created earlier, and select **Secrets**.</span></span>
    2. <span data-ttu-id="44be2-214">Per ogni nome segreto nella tabella seguente, segui questi passaggi:</span><span class="sxs-lookup"><span data-stu-id="44be2-214">For each secret name in the following table, follow these steps:</span></span>

        1. <span data-ttu-id="44be2-215">Seleziona **Genera/Importa**.</span><span class="sxs-lookup"><span data-stu-id="44be2-215">Select **Generate/Import**.</span></span>
        2. <span data-ttu-id="44be2-216">Nella finestra di dialogo **Crea un segreto**, nel campo **Opzioni di caricamento**, seleziona **Manuale**.</span><span class="sxs-lookup"><span data-stu-id="44be2-216">In the **Create a secret** dialog box, in the **Upload options** field, select **Manual**.</span></span>
        3. <span data-ttu-id="44be2-217">Crea il nome e il valore del segreto dalla tabella.</span><span class="sxs-lookup"><span data-stu-id="44be2-217">Create the secret name and value from the table.</span></span>
        4. <span data-ttu-id="44be2-218">Seleziona **Abilitato** e quindi **Crea**.</span><span class="sxs-lookup"><span data-stu-id="44be2-218">Select **Enabled**, and then select **Create**.</span></span> <span data-ttu-id="44be2-219">Il segreto viene creato e aggiunto al Key Vault.</span><span class="sxs-lookup"><span data-stu-id="44be2-219">The secret is created and added to Key Vault.</span></span>

        | <span data-ttu-id="44be2-220">Nome segreto</span><span class="sxs-lookup"><span data-stu-id="44be2-220">Secret name</span></span>                       | <span data-ttu-id="44be2-221">Valore segreto</span><span class="sxs-lookup"><span data-stu-id="44be2-221">Secret value</span></span>                                                                                 |
        |-----------------------------------|----------------------------------------------------------------------------------------------|
        | <span data-ttu-id="44be2-222">app-id</span><span class="sxs-lookup"><span data-stu-id="44be2-222">app-id</span></span>                            | <span data-ttu-id="44be2-223">L'ID app dell'applicazione che hai creato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="44be2-223">The app ID of the application that you created earlier.</span></span>                                      |
        | <span data-ttu-id="44be2-224">app-secret</span><span class="sxs-lookup"><span data-stu-id="44be2-224">app-secret</span></span>                        | <span data-ttu-id="44be2-225">Il segreto client che hai salvato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="44be2-225">The client secret that you saved earlier.</span></span>                                                    |
        | <span data-ttu-id="44be2-226">storage-account-name</span><span class="sxs-lookup"><span data-stu-id="44be2-226">storage-account-name</span></span>              | <span data-ttu-id="44be2-227">Il nome dell'account di archiviazione creato in precedenza, ad esempio **storageaccount1**.</span><span class="sxs-lookup"><span data-stu-id="44be2-227">The name of the storage account that you created earlier, such as **storageaccount1**.</span></span>       |

5. <span data-ttu-id="44be2-228">Autorizza l'applicazione ad accedere al Key Vault:</span><span class="sxs-lookup"><span data-stu-id="44be2-228">Authorize the application to access the key vault:</span></span>

    1. <span data-ttu-id="44be2-229">Nel [portale di Azure](https://portal.azure.com), apri il Key Vault creato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="44be2-229">In the [Azure portal](https://portal.azure.com), open the key vault that you created earlier.</span></span>
    2. <span data-ttu-id="44be2-230">Seleziona i criteri di accesso.</span><span class="sxs-lookup"><span data-stu-id="44be2-230">Select the access policies.</span></span>
    3. <span data-ttu-id="44be2-231">Per ogni applicazione nella tabella seguente, segui questi passaggi:</span><span class="sxs-lookup"><span data-stu-id="44be2-231">For each application in the following table, follow these steps:</span></span>

        1. <span data-ttu-id="44be2-232">Seleziona **Aggiungi criteri di accesso** per creare un criterio di accesso.</span><span class="sxs-lookup"><span data-stu-id="44be2-232">Select **Add Access Policy** to create an access policy.</span></span>
        2. <span data-ttu-id="44be2-233">Nel campo **Autorizzazioni segreto**, seleziona le autorizzazioni dalla tabella.</span><span class="sxs-lookup"><span data-stu-id="44be2-233">In the **Secret permissions** field, select the permissions from the table.</span></span>
        3. <span data-ttu-id="44be2-234">Nel campo **Seleziona entità di sicurezza**, cerca il nome visualizzato dell'applicazione dalla tabella.</span><span class="sxs-lookup"><span data-stu-id="44be2-234">In the **Select principal** field, search for the application display name from the table.</span></span>
        4. <span data-ttu-id="44be2-235">Seleziona **Seleziona**.</span><span class="sxs-lookup"><span data-stu-id="44be2-235">Select **Select**.</span></span>
        5. <span data-ttu-id="44be2-236">Seleziona **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="44be2-236">Select **Add**.</span></span>
        6. <span data-ttu-id="44be2-237">Seleziona **Salva**.</span><span class="sxs-lookup"><span data-stu-id="44be2-237">Select **Save**.</span></span>

        | <span data-ttu-id="44be2-238">Applicazione</span><span class="sxs-lookup"><span data-stu-id="44be2-238">Application</span></span>                                              | <span data-ttu-id="44be2-239">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="44be2-239">Permissions</span></span> |
        |----------------------------------------------------------|-------------|
        | <span data-ttu-id="44be2-240">Il nome visualizzato della nuova applicazione che hai creato</span><span class="sxs-lookup"><span data-stu-id="44be2-240">The display name of the new application that you created</span></span> | <span data-ttu-id="44be2-241">Get, List</span><span class="sxs-lookup"><span data-stu-id="44be2-241">Get, List</span></span>   |
        | <span data-ttu-id="44be2-242">**Microservizi ERP Microsoft Dynamics**</span><span class="sxs-lookup"><span data-stu-id="44be2-242">**Microsoft Dynamics ERP Microservices**</span></span>                 | <span data-ttu-id="44be2-243">Get, List</span><span class="sxs-lookup"><span data-stu-id="44be2-243">Get, List</span></span>   |

6. <span data-ttu-id="44be2-244">Assegna ruoli per accedere all'account di archiviazione:</span><span class="sxs-lookup"><span data-stu-id="44be2-244">Assign roles to access the storage account:</span></span>

    1. <span data-ttu-id="44be2-245">Nel [portale di Azure](https://portal.azure.com), apri l'account di archiviazione creato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="44be2-245">In the [Azure portal](https://portal.azure.com), open the storage account that you created earlier.</span></span>
    2. <span data-ttu-id="44be2-246">Seleziona **Controllo dei diritti di accesso (IAM)** e quindi seleziona **Assegnazioni di ruolo**.</span><span class="sxs-lookup"><span data-stu-id="44be2-246">Select **Access Control (IAM)**, and then select **Role Assignments**.</span></span>
    3. <span data-ttu-id="44be2-247">Seleziona **Aggiungi, Aggiungi assegnazione di ruolo**.</span><span class="sxs-lookup"><span data-stu-id="44be2-247">Select **Add, Add Role Assignment**.</span></span>
    4. <span data-ttu-id="44be2-248">Per ogni applicazione nella tabella seguente, segui questi passaggi:</span><span class="sxs-lookup"><span data-stu-id="44be2-248">For each application in the following table, follow these steps:</span></span>

        1. <span data-ttu-id="44be2-249">Seleziona il ruolo dalla tabella.</span><span class="sxs-lookup"><span data-stu-id="44be2-249">Select the role from the table.</span></span>
        2. <span data-ttu-id="44be2-250">Lascia il campo **Assegna accesso a** impostato su **Utente, gruppo o entità servizio Azure AD**.</span><span class="sxs-lookup"><span data-stu-id="44be2-250">Leave the **Assign access to** field set to **Azure AD user, group, or service principal**.</span></span>
        3. <span data-ttu-id="44be2-251">Nel campo **Seleziona**, immetti l'applicazione dalla tabella.</span><span class="sxs-lookup"><span data-stu-id="44be2-251">In the **Select** field, enter the application from the table.</span></span>
        4. <span data-ttu-id="44be2-252">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="44be2-252">Select **Save**.</span></span>

        | <span data-ttu-id="44be2-253">Domanda di lavoro</span><span class="sxs-lookup"><span data-stu-id="44be2-253">Application</span></span>                                              | <span data-ttu-id="44be2-254">Ruolo</span><span class="sxs-lookup"><span data-stu-id="44be2-254">Role</span></span>                        |
        |----------------------------------------------------------|-----------------------------|
        | <span data-ttu-id="44be2-255">Il nome visualizzato della nuova applicazione che hai creato</span><span class="sxs-lookup"><span data-stu-id="44be2-255">The display name of the new application that you created</span></span> | <span data-ttu-id="44be2-256">Proprietario</span><span class="sxs-lookup"><span data-stu-id="44be2-256">Owner</span></span>                       |
        | <span data-ttu-id="44be2-257">Il nome visualizzato della nuova applicazione che hai creato</span><span class="sxs-lookup"><span data-stu-id="44be2-257">The display name of the new application that you created</span></span> | <span data-ttu-id="44be2-258">Collaboratore</span><span class="sxs-lookup"><span data-stu-id="44be2-258">Contributor</span></span>                 |
        | <span data-ttu-id="44be2-259">Il nome visualizzato della nuova applicazione che hai creato</span><span class="sxs-lookup"><span data-stu-id="44be2-259">The display name of the new application that you created</span></span> | <span data-ttu-id="44be2-260">Collaboratore account di archiviazione</span><span class="sxs-lookup"><span data-stu-id="44be2-260">Storage Account Contributor</span></span> |
        | <span data-ttu-id="44be2-261">Il nome visualizzato della nuova applicazione che hai creato</span><span class="sxs-lookup"><span data-stu-id="44be2-261">The display name of the new application that you created</span></span> | <span data-ttu-id="44be2-262">Proprietario dei dati del BLOB di archiviazione</span><span class="sxs-lookup"><span data-stu-id="44be2-262">Storage Blob Data Owner</span></span>     |
        | <span data-ttu-id="44be2-263">**Servizio di autorizzazione di AI Builder**</span><span class="sxs-lookup"><span data-stu-id="44be2-263">**AI Builder Authorization Service**</span></span>                     | <span data-ttu-id="44be2-264">Lettore dati del BLOB di archiviazione</span><span class="sxs-lookup"><span data-stu-id="44be2-264">Storage Blob Data Reader</span></span>    |

# <a name="azure-cli"></a>[<span data-ttu-id="44be2-265">Azure CLI</span><span class="sxs-lookup"><span data-stu-id="44be2-265">Azure CLI</span></span>](#tab/azure-azure-cli)

```
function New-FinanceDataLakeAzureResources {
    Assert-ScriptSetup

    $ClientAppName = 'Finance Data Lake Application'
    $DefaultSecretExpiryInYear = 1
    $MicrosoftDynamicsERPMicroservicesAppId = '0cdb527f-a8d1-4bf8-9436-b352c68682b2'
    $MicrosoftDynamicsERPMicroservicesCDSAppId = '703e2651-d3fc-48f5-942c-74274233dba8'
    $AIBuilderAuthorizationServiceAppId = 'ad40333e-9910-4b61-b281-e3aeeb8c3ef3'
    $KeyVaultServicePrincipalAppId = 'cfa8b339-82a2-471a-a3c9-0fc0be7a4093'
    $GraphServicePrincipalAppId = '00000003-0000-0000-c000-000000000000'

    Import-Module AzureAD.Standard.Preview
    $connectAzureADParameters = @{ 'Identity' = $true; 'TenantId' = $env:ACC_TID }
    $azContext = AzureAD.Standard.Preview\Connect-AzureAD @connectAzureADParameters
    $userContext = ConvertFrom-Json ((az ad signed-in-user show) -join '')
    $user = Get-AzureADUser -Filter ("UserPrincipalName eq '" + $userContext.UserPrincipalName + "'")

    Set-AzureSubscription
    
    $resourceGroup = $null
    $ResourceGroupName = 'D365FinanceInsightsDataLake'
    $ResourceGroupNameSuffix = ''
    $FullResourceGroupName = ''
    Write-Output ("The default Azure Resource Group name is '{0}'" -f $ResourceGroupName)
    while (-not ($resourceGroup)) {
        $ResourceGroupNameSuffix = (Read-Host -Prompt "Enter optional Azure Resource Group name suffix: (leave blank for no suffix)")
        if ([string]::IsNullOrWhitespace($ResourceGroupNameSuffix))
        {
            $FullResourceGroupName = $ResourceGroupName
        }
        else
        {
            if ($ResourceGroupNameSuffix -notmatch "^[A-Za-z0-9]+$") {
                Write-Warning "The Azure Resource Group name suffix can only include alphanumeric characters."
                continue
            }

            if ($ResourceGroupNameSuffix.Length -gt 60) {
                Write-Warning "The Azure Resource Group name suffix cannot be longer than 60 characters."
                continue
            }

            $FullResourceGroupName = $ResourceGroupName + $ResourceGroupNameSuffix
        }
        
        $resourceGroup = Get-AzResourceGroup -Name $FullResourceGroupName -ErrorAction SilentlyContinue

        if (-not ($resourceGroup)) {
            Write-Output ("Your new Azure Resource Group name is '{0}'" -f $FullResourceGroupName)
            $resourceLocation = ''
            $azResourceLocations = (Get-AzLocation | Select-Object Location).Location
            while ([string]::IsNullOrWhitespace($resourceLocation) -or (-not ($resourceLocation -in $azResourceLocations))) {
                $resourceLocation = (Read-Host -Prompt "Enter the location in which to create the Azure Resource Group: ('help' to see values)")
                if ($resourceLocation -eq 'help') {
                    Write-Output ("List of available regions is '{0}'" -f ($azResourceLocations -join ','))
                }
                elseif ([string]::IsNullOrWhitespace($resourceLocation) -or (-not ($resourceLocation -in $azResourceLocations)))
                {
                    Write-Warning ("The provided location is not available for resource group. List of available regions is '{0}'" -f ($azResourceLocations -join ','))
                }
            }
            $resourceGroup = New-AzResourceGroup -Name $FullResourceGroupName -Location $resourceLocation
            Write-Output ("Created Azure Resource Group '{0}'" -f $resourceGroup.ResourceGroupName)
        }
        else {
            Write-Output ("Found Azure Resource Group '{0}'" -f ($resourceGroup.ResourceGroupName))
        }
    }

    Write-Output '================================================================================='
    $MicrosoftDynamicsERPMicroservicesAppObjectId = Create-ADServicePrincipal -AppId $MicrosoftDynamicsERPMicroservicesAppId
    Create-ADServicePrincipal -AppId $MicrosoftDynamicsERPMicroservicesCDSAppId | Out-Null
    $aibuilderAuthorizationServiceObjectId = Create-ADServicePrincipal -AppId $AIBuilderAuthorizationServiceAppId
    Write-Output ('=================================================================================')

    $clientAppSPN = Get-AzureADServicePrincipal -Filter ("DisplayName eq '" + $ClientAppName + "'")
    if (-not ($clientAppSPN)) {
        $keyVaultPrincipal = Get-AzureADServicePrincipal -Filter ("AppId eq '" + $KeyVaultServicePrincipalAppId + "'")
        if (-not $keyVaultPrincipal)
        {
            New-AzureADServicePrincipal -AppId $KeyVaultServicePrincipalAppId | Format-Table -AutoSize
            Write-Output "Added Key Vault principal to AAD"
            $keyVaultPrincipal = Get-AzureADServicePrincipal -Filter ("AppId eq '" + $KeyVaultServicePrincipalAppId + "'")
        }
        $keyVaultAccess = New-Object -TypeName "Microsoft.Open.AzureAD.Model.RequiredResourceAccess"
        $keyVaultAccess.ResourceAppId = $keyVaultPrincipal.AppId
        $keyVaultAccess.ResourceAccess = (New-Object -TypeName "microsoft.open.azuread.model.resourceAccess" -ArgumentList $keyVaultPrincipal.Oauth2Permissions.Id, "Scope")

        $graphPrincipal = Get-AzureADServicePrincipal -Filter ("AppId eq '" + $GraphServicePrincipalAppId + "'")
        if (-not $graphPrincipal)
        {
            New-AzureADServicePrincipal -AppId $GraphServicePrincipalAppId | Format-Table -AutoSize
            Write-Output "Added Graph principal to AAD"
            $graphPrincipal = Get-AzureADServicePrincipal -Filter ("AppId eq '" + $GraphServicePrincipalAppId + "'")
        }
        $userRead = $graphPrincipal.Oauth2Permissions | Where-Object { $_.Type -eq "User" -and $_.Value -eq "User.Read" }
        $graphAccess = New-Object -TypeName "Microsoft.Open.AzureAD.Model.RequiredResourceAccess"
        $graphAccess.ResourceAppId = $graphPrincipal.AppId
        $graphAccess.ResourceAccess = (New-Object -TypeName "microsoft.open.azuread.model.resourceAccess" -ArgumentList $userRead.Id, "Scope")

        $clientApp = New-AzureADApplication -DisplayName $ClientAppName -RequiredResourceAccess @($keyVaultAccess, $graphAccess)
        $clientAppSPN = New-AzureADServicePrincipal -AppId $clientApp.AppId -Tags @($ClientAppName)
        $clientAppId = $clientApp.AppId
        Write-Output ('Created App Registration "' + $ClientAppName + '" with Application Id: ' + $clientAppId)
    }
    else {
        $clientApp = Get-AzureADApplication -Filter ("DisplayName eq '" + $ClientAppName + "'")
        $clientAppId = $clientApp.AppId
        Write-Output ('Found App Registration "' + $ClientAppName + '" with Application Id: ' + $clientAppId)
    }
            
    $clientAppSecretCredential = New-AzureADApplicationPasswordCredential -ObjectId $clientApp.ObjectId -CustomKeyIdentifier "ClientAppAccessKey" -EndDate (get-date).AddYears($DefaultSecretExpiryInYear)
    $ClientAppSecret = $clientAppSecretCredential.Value
    $clientAppSpId = $clientAppSPN.ObjectId

    Write-Output ('Generated application secret: ' + $ClientAppSecret)
    Write-Output '================================================================================='

    $templateObject = ConvertFrom-Json $azureTemplate -AsHashtable
    $templateObject.{$schema} = "https://schema.management.azure.com/schemas/2019-04-01/deploymentTemplate.json#"
    Write-Output 'Provisioning Azure resources. This may take a few minutes.'
    try {
        $deployment = New-AzResourceGroupDeployment -ResourceGroupName $FullResourceGroupName -TemplateObject $templateObject -aibuilderAppObjectId $aibuilderAuthorizationServiceObjectId -clientAppId $clientAppId -clientAppSecret $ClientAppSecret -clientAppSpObjectId  $clientAppSpId -microserviceSpObjectId $MicrosoftDynamicsERPMicroservicesAppObjectId -userSpObjectId $user.ObjectId -Force -ErrorAction Stop
    }
    catch {
        $ErrorMessage = $_.Exception.Message
        if ($ErrorMessage.Contains("not allowed to be updated"))
        {
            Write-Error ($ErrorMessage)
            Write-Warning "Some items in the existing resource group $FullResourceGroupName could not be updated. To resolve the issue, remove the existing resource group $FullResourceGroupName and run the script again."
        }
        else {
            throw
        }

    }
    if ($deployment.ProvisioningState -eq 'Succeeded') {
        Write-Output "Successfully deployed the following resources to Azure:"
        Write-Output ("  Key Vault:                         " + $deployment.Outputs.keyVaultName.Value)
        Write-Output ("  Storage Account:                   " + $deployment.Outputs.storageAccountName.Value)
        
        $keyVault = Get-AzKeyVault -VaultName $deployment.Outputs.keyVaultName.Value
        $tenantId = (Get-AzContext).Tenant.Id

        Write-Output "Values for LCS Data Lake Add-In:"
        Write-Output ("  Tenant ID:                         " + $tenantId)
        Write-Output ("  DNS Name:                          " + $keyVault.VaultUri)
        Write-Output "  Storage account secret name:       storage-account-name"
        Write-Output "  Application ID secret name:        app-id"
        Write-Output "  Application Secret secret name:    app-secret"
        Write-Warning "Copy this information for the LCS Add-in for easy access. Azure Cloud Shell will eventually time out and close."

        Write-Output '================================================================================='
        Write-Output "Values for System parameters > Data connections:"
        Write-Output ("  Application ID:                    " + $clientAppId)
        Write-Output ("  Application Secret:                " + $ClientAppSecret)
        Write-Output ("  DNS name:                          " + $keyVault.VaultUri)
        Write-Output "  Secret name:                       storage-account-connection-string"
        Write-Warning "Copy this information for the System parameters for easy access. Azure Cloud Shell will eventually time out and close."
    }
    else {
        Write-Output ("Provisioning Azure resources failed with the following state: " + $deployment.ProvisioningState)
        Write-Output ("Some of the resources may have been created in resource group: " + $FullResourceGroupName)
    }
}

function Assert-ScriptSetup {
    if ($PSVersionTable.PSEdition -ne 'Core' -or -not $env:ACC_TID) { 
        throw "This script needs to be uploaded and run from Azure Cloud Shell (PowerShell)." 
    }
    
    if ((Get-AzContext) -eq $null -and (Connect-AzAccount) -eq $null) {
        throw 'Unable to connect to Azure account.'
    }
}

function Set-AzureSubscription {
    $azSubscription = $null
    while (-not ($azSubscription)) {
        $subscriptionId = (Read-Host -Prompt "Enter the Azure Subscription ID: (leave blank for default)")
        if ([string]::IsNullOrWhitespace($subscriptionId)){
            break
        }
        elseif (-not [guid]::TryParse($subscriptionId, $([ref][guid]::Empty))) {
                Write-Warning "Azure Subscription ID must be a valid GUID."
                continue
        }

        $azSubscription = Select-AzSubscription -SubscriptionId $subscriptionId
    }
}

function Create-ADServicePrincipal {
    param (
        [string] $AppId
    )

    $service = Get-AzureADServicePrincipal -Filter ("AppId eq '" + $AppId + "'")
    if (-not $service) {
        New-AzureADServicePrincipal -AppId $AppId | Out-Null
        $service = Get-AzureADServicePrincipal -Filter ("AppId eq '" + $AppId + "'")
        Write-Host ("Added AAD Enterprise Application {0} with Application ID {1}" -f $service.DisplayName,$AppId)
    }
    else {
        Write-Host ("Found AAD Enterprise Application {0} with Application ID {1}" -f $service.DisplayName,$AppId)
    }

    return $service.ObjectId
}

$azureTemplate = @"
{
    "contentVersion": "1.0.0.0",
    "parameters": {
      "aibuilderAppObjectId": {
        "type": "string",
        "metadata": {
          "description": "Specifies the object ID of the AI Builder application."
        }
      },
      "clientAppId": {
        "type": "string",
        "metadata": {
          "description": "Specifies the application ID of client application."
        }
      },
      "clientAppSecret": {
        "type": "String",
        "metadata": {
          "description": "Specifies the Azure App ID client secret to in azure key vault."
        }
      },
      "clientAppSpObjectId": {
        "type": "string",
        "metadata": {
          "description": "Specifies the object ID of a client application service principal."
        }
      },
      "userSpObjectId": {
        "type": "string",
        "metadata": {
          "description": "Specifies the object ID of tenant admin service principal."
        }
      },
      "microserviceSpObjectId": {
        "type": "string",
        "metadata": {
          "description": "Specifies the object ID of Microsoft Dynamics ERP Microservices service principal."
        }
      },
      "storageAccountType": {
        "type": "string",
        "defaultValue": "Standard_LRS",
        "allowedValues": [
          "Standard_LRS",
          "Standard_GRS",
          "Standard_ZRS",
          "Premium_LRS"
        ],
        "metadata": {
          "description": "Storage Account type"
        }
      }
    },
    "variables": {
      "storageAccountApiVersion": "2019-06-01",
      "keyVaultApiVersion": "2018-02-14",
      "secretsPermissions": [
        "list",
        "get"
      ],
      "location": "[resourceGroup().location]",
      "storageAccountName": "[concat('store', uniquestring(resourceGroup().id))]",
      "keyVaultName": "[concat('keyvault', uniquestring(resourceGroup().id))]",
      "owner": "[concat('/subscriptions/', subscription().subscriptionId, '/providers/Microsoft.Authorization/roleDefinitions/', '8e3af657-a8ff-443c-a75c-2fe8c4bcb635')]",
      "contributor": "[concat('/subscriptions/', subscription().subscriptionId, '/providers/Microsoft.Authorization/roleDefinitions/', 'b24988ac-6180-42a0-ab88-20f7382dd24c')]",
      "storageAccountContributor": "[concat('/subscriptions/', subscription().subscriptionId, '/providers/Microsoft.Authorization/roleDefinitions/', '17d1049b-9a84-46fb-8f53-869881c3d3ab')]",
      "storageBlobDataOwner": "[concat('/subscriptions/', subscription().subscriptionId, '/providers/Microsoft.Authorization/roleDefinitions/', 'b7e6dc6d-f1e8-4753-8033-0f276bb0955b')]",
      "storageBlobDataReader": "[concat('/subscriptions/', subscription().subscriptionId, '/providers/Microsoft.Authorization/roleDefinitions/', '2a2b9908-6ea1-4ae2-8e65-a410df84e7d1')]"
    },
    "resources": [
      {
        "type": "Microsoft.Storage/storageAccounts",
        "apiVersion": "[variables('storageAccountApiVersion')]",
        "name": "[variables('storageAccountName')]",
        "location": "[variables('location')]",
        "sku": {
          "name": "[parameters('storageAccountType')]"
        },
        "kind": "StorageV2",
        "properties": {
          "accessTier": "Hot",
          "supportsHttpsTrafficOnly": true,
          "isHnsEnabled": true
        },
        "resources": [
          {
            "type": "Microsoft.Storage/storageAccounts/providers/roleAssignments",
            "apiVersion": "2018-09-01-preview",
            "name": "[concat(variables('storageAccountName'), '/Microsoft.Authorization/', guid(uniqueString(variables('storageAccountName'),'1')))]",
            "dependsOn": [
              "[variables('storageAccountName')]"
            ],
            "properties": {
              "roleDefinitionId": "[variables('owner')]",
              "principalId": "[parameters('clientAppSpObjectId')]"
            }
          },
          {
            "type": "Microsoft.Storage/storageAccounts/providers/roleAssignments",
            "apiVersion": "2018-09-01-preview",
            "name": "[concat(variables('storageAccountName'), '/Microsoft.Authorization/', guid(uniqueString(variables('storageAccountName'),'2')))]",
            "dependsOn": [
              "[variables('storageAccountName')]"
            ],
            "properties": {
              "roleDefinitionId": "[variables('contributor')]",
              "principalId": "[parameters('clientAppSpObjectId')]"
            }
          },
          {
            "type": "Microsoft.Storage/storageAccounts/providers/roleAssignments",
            "apiVersion": "2018-09-01-preview",
            "name": "[concat(variables('storageAccountName'), '/Microsoft.Authorization/', guid(uniqueString(variables('storageAccountName'),'3')))]",
            "dependsOn": [
              "[variables('storageAccountName')]"
            ],
            "properties": {
              "roleDefinitionId": "[variables('storageAccountContributor')]",
              "principalId": "[parameters('clientAppSpObjectId')]"
            }
          },
          {
            "type": "Microsoft.Storage/storageAccounts/providers/roleAssignments",
            "apiVersion": "2018-09-01-preview",
            "name": "[concat(variables('storageAccountName'), '/Microsoft.Authorization/', guid(uniqueString(variables('storageAccountName'),'4')))]",
            "dependsOn": [
              "[variables('storageAccountName')]"
            ],
            "properties": {
              "roleDefinitionId": "[variables('storageBlobDataOwner')]",
              "principalId": "[parameters('clientAppSpObjectId')]"
            }
          },
          {
            "type": "Microsoft.Storage/storageAccounts/providers/roleAssignments",
            "apiVersion": "2018-09-01-preview",
            "name": "[concat(variables('storageAccountName'), '/Microsoft.Authorization/', guid(uniqueString(variables('storageAccountName'),'5')))]",
            "dependsOn": [
              "[variables('storageAccountName')]"
            ],
            "properties": {
              "roleDefinitionId": "[variables('storageBlobDataReader')]",
              "principalId": "[parameters('aibuilderAppObjectId')]"
            }
          }
        ]
      },
      {
        "type": "Microsoft.KeyVault/vaults",
        "apiVersion": "[variables('keyVaultApiVersion')]",
        "name": "[variables('keyVaultName')]",
        "location": "[variables('location')]",
        "dependsOn": [
          "[resourceId('Microsoft.Storage/storageAccounts', variables('storageAccountName'))]"
        ],
        "tags": {
        },
        "properties": {
          "enabledForDeployment": false,
          "enabledForTemplateDeployment": false,
          "enabledForDiskEncryption": false,
          "enableRbacAuthorization": false,
          "accessPolicies": [
            {
              "objectId": "[parameters('clientAppSpObjectId')]",
              "tenantId": "[subscription().tenantId]",
              "permissions": {
                "secrets": "[variables('secretsPermissions')]"
              }
            },
            {
              "objectId": "[parameters('microserviceSpObjectId')]",
              "tenantId": "[subscription().tenantId]",
              "permissions": {
                "secrets": "[variables('secretsPermissions')]"
              }
            },
            {
              "objectId": "[parameters('userSpObjectId')]",
              "tenantId": "[subscription().tenantId]",
              "permissions": {
                "secrets": "[variables('secretsPermissions')]"
              }
            }
          ],
          "tenantId": "[subscription().tenantId]",
          "sku": {
            "name": "Standard",
            "family": "A"
          },
          "enableSoftDelete": false,
          "networkAcls": {
            "defaultAction": "Allow",
            "bypass": "AzureServices"
          }
        }
      },
      {
        "type": "Microsoft.KeyVault/vaults/secrets",
        "name": "[concat(variables('keyVaultName'), '/', 'app-id')]",
        "apiVersion": "[variables('keyVaultApiVersion')]",
        "location": "[variables('location')]",
        "dependsOn": [
          "[resourceId('Microsoft.KeyVault/vaults', variables('keyVaultName'))]"
        ],
        "properties": {
          "value": "[parameters('clientAppId')]"
        }
      },
      {
        "type": "Microsoft.KeyVault/vaults/secrets",
        "name": "[concat(variables('keyVaultName'), '/', 'app-secret')]",
        "apiVersion": "[variables('keyVaultApiVersion')]",
        "location": "[variables('location')]",
        "dependsOn": [
          "[resourceId('Microsoft.KeyVault/vaults', variables('keyVaultName'))]"
        ],
        "properties": {
          "value": "[parameters('clientAppSecret')]"
        }
      },
      {
        "type": "Microsoft.KeyVault/vaults/secrets",
        "name": "[concat(variables('keyVaultName'), '/', 'storage-account-name')]",
        "apiVersion": "[variables('keyVaultApiVersion')]",
        "location": "[variables('location')]",
        "dependsOn": [
          "[resourceId('Microsoft.KeyVault/vaults', variables('keyVaultName'))]"
        ],
        "properties": {
          "value": "[variables('storageAccountName')]"
        }
      },
      {
        "type": "Microsoft.KeyVault/vaults/secrets",
        "name": "[concat(variables('keyVaultName'), '/', 'storage-account-connection-string')]",
        "apiVersion": "[variables('keyVaultApiVersion')]",
        "location": "[variables('location')]",
        "dependsOn": [
          "[resourceId('Microsoft.KeyVault/vaults', variables('keyVaultName'))]"
        ],
        "properties": {
          "value": "[concat('DefaultEndpointsProtocol=https;AccountName=', variables('storageAccountName'), ';AccountKey=', listKeys(resourceId('Microsoft.Storage/storageAccounts', variables('storageAccountName')), variables('storageAccountApiVersion')).keys[0].value, ';EndpointSuffix=core.windows.net')]"
        }
      }
    ],
    "outputs": {
      "storageAccountName": {
        "type": "string",
        "value": "[variables('storageAccountName')]"
      },
      "keyVaultName": {
        "type": "string",
        "value": "[variables('keyVaultName')]"
      }
    }
  }
"@

try {
  Start-Transcript -path (Join-Path $HOME Provision-FinInsights-Azure.log)
  New-FinanceDataLakeAzureResources
}
catch {
  Write-Error $_.Exception.Message

  if ($PSItem.Exception.StackTrace -ne $null)
  {
      Write-Warning $_.Exception.StackTrace
  }

  $inner = $_.Exception.InnerException
  while ($null -ne $inner) {
    Write-Output 'Inner Exception:'
    Write-Error $_.Exception.Message
    Write-Warning $_.Exception.StackTrace
    $inner = $inner.InnerException
  }
}
finally {
  Stop-Transcript
}
```
---

## <a name="configure-the-export-to-data-lake-add-in"></a><span data-ttu-id="44be2-266">Configurare l'esportazione nel componente aggiuntivo Data Lake</span><span class="sxs-lookup"><span data-stu-id="44be2-266">Configure the Export to Data Lake add-in</span></span>

<span data-ttu-id="44be2-267">Segui questi passaggi per utilizzare LCS per aggiungere il componente aggiuntivo Esporta in Data Lake all'ambiente.</span><span class="sxs-lookup"><span data-stu-id="44be2-267">Follow these steps to use LCS to add the Export to Data Lake add-in to the environment.</span></span>

1. <span data-ttu-id="44be2-268">Accedi a LCS, quindi, sotto il nome dell'ambiente sul lato destro della pagina, seleziona **Dettagli completi**.</span><span class="sxs-lookup"><span data-stu-id="44be2-268">Sign in to LCS, and then, under the environment name on the right side of the page, select **Full Details**.</span></span>
2. <span data-ttu-id="44be2-269">Nella sezione **Componenti aggiuntivi per l'ambiente**, selezionare **Installa un nuovo componente aggiuntivo**.</span><span class="sxs-lookup"><span data-stu-id="44be2-269">In the **Environment add-ins** section, select **Install a new add-in**.</span></span>
3. <span data-ttu-id="44be2-270">Seleziona il componente aggiunti **Esporta in Data Lake**.</span><span class="sxs-lookup"><span data-stu-id="44be2-270">Select the **Export to Data Lake** add-in.</span></span>
4. <span data-ttu-id="44be2-271">Immetti i valori seguenti.</span><span class="sxs-lookup"><span data-stu-id="44be2-271">Enter the following values.</span></span>

    | <span data-ttu-id="44be2-272">Valore</span><span class="sxs-lookup"><span data-stu-id="44be2-272">Value</span></span>                                                              | <span data-ttu-id="44be2-273">Descrizione</span><span class="sxs-lookup"><span data-stu-id="44be2-273">Description</span></span> |
    |--------------------------------------------------------------------|-------------|
    | <span data-ttu-id="44be2-274">ID tenant della sottoscrizione di Azure in cui si trova il Key Vault</span><span class="sxs-lookup"><span data-stu-id="44be2-274">Tenant ID of the Azure Subscription where the Key Vault is located</span></span> | <span data-ttu-id="44be2-275">L'ID tenant in cui si trovano l'account di archiviazione, le app e i Key Vault.</span><span class="sxs-lookup"><span data-stu-id="44be2-275">The tenant ID where the storage account, apps, and key vaults are located.</span></span> <span data-ttu-id="44be2-276">Per ottenere questo valore, apri il [portale di Azure](https://portal.azure.com), vai ad **Azure Active Directory** e copia il valore **ID tenant**.</span><span class="sxs-lookup"><span data-stu-id="44be2-276">To obtain this value, open the [Azure portal](https://portal.azure.com), go to **Azure Active Directory**, and copy the **Tenant ID** value.</span></span> |
    | <span data-ttu-id="44be2-277">Specificare il nome DNS del Key Vault</span><span class="sxs-lookup"><span data-stu-id="44be2-277">Provide the DNS name of your Key Vault</span></span>                             | <span data-ttu-id="44be2-278">Il nome DNS del Key Vault, ad esempio `https://customkeyvault.vault.azure.net/`.</span><span class="sxs-lookup"><span data-stu-id="44be2-278">The DNS name of the key vault, such as `https://customkeyvault.vault.azure.net/`.</span></span> |
    | <span data-ttu-id="44be2-279">Fornire il segreto contenente il nome dell'account di archiviazione</span><span class="sxs-lookup"><span data-stu-id="44be2-279">Provide the secret that contains the name of the storage account</span></span>   | <span data-ttu-id="44be2-280">**storage-account-name**</span><span class="sxs-lookup"><span data-stu-id="44be2-280">**storage-account-name**</span></span> |
    | <span data-ttu-id="44be2-281">Nome segreto per l'ID app da utilizzare per accedere al data lake</span><span class="sxs-lookup"><span data-stu-id="44be2-281">Secret Name for App ID to be used for accessing Data Lake</span></span>          | <span data-ttu-id="44be2-282">**app-id**</span><span class="sxs-lookup"><span data-stu-id="44be2-282">**app-id**</span></span> |
    | <span data-ttu-id="44be2-283">Nome del segreto per il segreto del client dell'app</span><span class="sxs-lookup"><span data-stu-id="44be2-283">Secret name for App client secret</span></span>                                  | <span data-ttu-id="44be2-284">**app-secret**</span><span class="sxs-lookup"><span data-stu-id="44be2-284">**app-secret**</span></span> |

5. <span data-ttu-id="44be2-285">Accetta le condizioni e seleziona **Installa**.</span><span class="sxs-lookup"><span data-stu-id="44be2-285">Agree to the terms, and then select **Install**.</span></span>

<span data-ttu-id="44be2-286">Il componente aggiuntivo verrà installato in pochi minuti.</span><span class="sxs-lookup"><span data-stu-id="44be2-286">The add-in will be installed within a few minutes.</span></span>

## <a name="configure-the-finance-insights-add-in"></a><span data-ttu-id="44be2-287">Configurare il componente aggiuntivo Finance Insights</span><span class="sxs-lookup"><span data-stu-id="44be2-287">Configure the Finance insights add-in</span></span>

> [!NOTE]
> <span data-ttu-id="44be2-288">Se in precedenza hai installato il componente aggiuntivo Ottieni informazioni dettagliate, disinstallalo prima di completare la procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="44be2-288">If you previously installed the Get insights add-in, uninstall it before you complete the following procedure.</span></span>

<span data-ttu-id="44be2-289">Segui questi passaggi per installare il componente aggiuntivo Finance Insights.</span><span class="sxs-lookup"><span data-stu-id="44be2-289">Follow these steps to install the Finance insights add-in.</span></span>

1. <span data-ttu-id="44be2-290">Accedi a LCS, quindi, sotto il nome dell'ambiente sul lato destro della pagina, seleziona **Dettagli completi**.</span><span class="sxs-lookup"><span data-stu-id="44be2-290">Sign in to LCS, and then, under the environment name on the right side of the page, select **Full Details**.</span></span>
2. <span data-ttu-id="44be2-291">Nella sezione **Componenti aggiuntivi per l'ambiente**, selezionare **Installa un nuovo componente aggiuntivo**.</span><span class="sxs-lookup"><span data-stu-id="44be2-291">In the **Environment add-ins** section, select **Install a new add-in**.</span></span>
3. <span data-ttu-id="44be2-292">Seleziona il componente aggiuntivo **Finance Insights**.</span><span class="sxs-lookup"><span data-stu-id="44be2-292">Select the **Finance insights** add-in.</span></span>
4. <span data-ttu-id="44be2-293">Accetta le condizioni e seleziona **Installa**.</span><span class="sxs-lookup"><span data-stu-id="44be2-293">Agree to the terms, and then select **Install**.</span></span>

## <a name="feedback-and-support"></a><span data-ttu-id="44be2-294">Feedback e supporto</span><span class="sxs-lookup"><span data-stu-id="44be2-294">Feedback and support</span></span>

<span data-ttu-id="44be2-295">Se vuoi fornire un feedback o hai bisogno di supporto, invia un'e-mail a [Finance Insights (anteprima)](mailto:fiap@microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="44be2-295">If you're interested in providing feedback, or if you require support, send an email to [Finance insights (Preview)](mailto:fiap@microsoft.com).</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
