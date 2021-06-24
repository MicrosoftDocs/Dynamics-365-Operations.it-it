---
title: Configurazione per Finance Insights (anteprima) - versioni fino alla 10.0.19
description: In questo argomento vengono illustrati i passaggi di configurazione che consentiranno al sistema di utilizzare le funzionalità disponibili in Finance Insights per le versioni fino alla 10.0.19..
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
ms.search.validFrom: 2020-07-20
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 6ad06bb6d041fc060b3a99538f6d4d0af333180f
ms.sourcegitcommit: ebcd9019cbb88a7f2afd9e701812e222566fd43d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2021
ms.locfileid: "6186422"
---
# <a name="configuration-for-finance-insights-preview"></a><span data-ttu-id="c1e98-103">Configurazione per Finance Insights (anteprima)</span><span class="sxs-lookup"><span data-stu-id="c1e98-103">Configuration for Finance insights (preview)</span></span>

[!include [banner](../includes/banner.md)]

[!include [preview banner](../includes/preview-banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

> [!NOTE]
> <span data-ttu-id="c1e98-104">Le seguenti procedure per l'impostazione di Finance Insights sono valide per Microsoft Dynamics 365 Finance versioni fino alla 10.0.19.</span><span class="sxs-lookup"><span data-stu-id="c1e98-104">The following procedures for setting up Finance insights are valid for Microsoft Dynamics 365 Finance versions up to 10.0.19.</span></span> <span data-ttu-id="c1e98-105">'Per impostare Finance Insight sulla versione 10.0.20 e successive, vedi [Configurazione per Finance Insights (anteprima) - Versioni superiori a 10.0.20](configure-for-fin-insites-PubPrvw.md).</span><span class="sxs-lookup"><span data-stu-id="c1e98-105">To set up Finance insights on version 10.0.20 and later, see [Configuration for Finance Insights (preview) - versions 10.0.20 and beyond](configure-for-fin-insites-PubPrvw.md).</span></span>

<span data-ttu-id="c1e98-106">Finance Insights combina le funzionalità di Microsoft Dynamics 365 Finance con Microsoft Dataverse, Azure e AI Builder per fornire potenti strumenti di previsione per la tua organizzazione.</span><span class="sxs-lookup"><span data-stu-id="c1e98-106">Finance insights combines functionality from Microsoft Dynamics 365 Finance with Microsoft Dataverse, Azure, and AI Builder to provide powerful forecasting tools for your organization.</span></span> <span data-ttu-id="c1e98-107">In questo argomento vengono illustrati i passaggi di configurazione che consentiranno al sistema di utilizzare le funzionalità disponibili in Finance Insights.</span><span class="sxs-lookup"><span data-stu-id="c1e98-107">This topic explains the configuration steps that will enable your system to use the capabilities that are available in Finance insights.</span></span>

## <a name="deploy-dynamics-365-finance"></a><span data-ttu-id="c1e98-108">Distribuire Dynamics 365 Finance</span><span class="sxs-lookup"><span data-stu-id="c1e98-108">Deploy Dynamics 365 Finance</span></span>

<span data-ttu-id="c1e98-109">Distribuisci l'ambiente seguendo questa procedura.</span><span class="sxs-lookup"><span data-stu-id="c1e98-109">Deploy the environments by following these steps.</span></span>

1. <span data-ttu-id="c1e98-110">In Microsoft Dynamics Lifecycle Services (LCS), crea o aggiorna un ambiente Dynamics 365 Finance.</span><span class="sxs-lookup"><span data-stu-id="c1e98-110">In Microsoft Dynamics Lifecycle Services (LCS), create or update a Dynamics 365 Finance environment.</span></span> <span data-ttu-id="c1e98-111">L'ambiente richiede la versione dell'app 10.0.11/Platform update 35 o successive.</span><span class="sxs-lookup"><span data-stu-id="c1e98-111">The environment requires app version 10.0.11/Platform update 35 or later.</span></span>
2. <span data-ttu-id="c1e98-112">L'ambiente deve essere un ambiente ad alta disponibilità (HA) in Sandbox.</span><span class="sxs-lookup"><span data-stu-id="c1e98-112">The environment must be a high-availability (HA) environment in Sandbox.</span></span> <span data-ttu-id="c1e98-113">(Questo tipo di ambiente è noto anche come ambiente Tier-2). Per altre informazioni, vedi [Pianificazione ambientale](../../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md).</span><span class="sxs-lookup"><span data-stu-id="c1e98-113">(This type of environment is also known as a Tier-2 environment.) For more information, see [Environment planning](../../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md).</span></span>
3. <span data-ttu-id="c1e98-114">Se stai configurando Finance Insights in un ambiente sandbox, potresti dover copiare i dati di produzione in tale ambiente affinché le stime funzionino.</span><span class="sxs-lookup"><span data-stu-id="c1e98-114">If you are configuring Finance insights in a Sandbox environment, you might need to copy production data to that environment for predictions to work.</span></span> <span data-ttu-id="c1e98-115">Il modello di stima utilizza più anni di dati per creare previsioni.</span><span class="sxs-lookup"><span data-stu-id="c1e98-115">The prediction model uses multiple years of data to build predictions.</span></span> <span data-ttu-id="c1e98-116">I dati della demo di Contoso non contengono dati storici sufficienti per addestrare adeguatamente il modello di stima.</span><span class="sxs-lookup"><span data-stu-id="c1e98-116">The Contoso demo data doesn’t contain enough historical data to train the prediction model adequately.</span></span> 

## <a name="configure-dataverse"></a><span data-ttu-id="c1e98-117">Configura Dataverse</span><span class="sxs-lookup"><span data-stu-id="c1e98-117">Configure Dataverse</span></span>

<span data-ttu-id="c1e98-118">Utilizzare i seguenti passaggi per configurare Dataverse per Finance Insights.</span><span class="sxs-lookup"><span data-stu-id="c1e98-118">Use the following steps to configure Dataverse for Finance insights.</span></span>

1. <span data-ttu-id="c1e98-119">Apri la pagina dell'ambiente in LCS e verifica che la sezione **Integrazione Power Platform** è già configurata.</span><span class="sxs-lookup"><span data-stu-id="c1e98-119">Open the environment page in LCS and verify that the **Power Platform Integration** section is already setup.</span></span>
    1. <span data-ttu-id="c1e98-120">Se è già configurata, il nome dell'ambiente Dataverse collegato all'ambiente Dynamics 365 Finance dovrebbe essere elencato.</span><span class="sxs-lookup"><span data-stu-id="c1e98-120">If it is already set up, the Dataverse environment name linked to the Dynamics 365 Finance Environment should be listed.</span></span> <span data-ttu-id="c1e98-121">Copia il  nome dell'ambiente Dataverse.</span><span class="sxs-lookup"><span data-stu-id="c1e98-121">Copy the Dataverse environment name.</span></span>
    2. <span data-ttu-id="c1e98-122">Se non è configurato, segui questi passaggi:</span><span class="sxs-lookup"><span data-stu-id="c1e98-122">If it is not set up, follow these steps:</span></span>
        1. <span data-ttu-id="c1e98-123">Seleziona il pulsante **Imposta** nella sezione Integrazione Power Platform.</span><span class="sxs-lookup"><span data-stu-id="c1e98-123">Select the **Setup** button in the Power Platform Integration section.</span></span> <span data-ttu-id="c1e98-124">Potrebbe essere necessaria fino a un'ora per la configurazione dell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="c1e98-124">It may take up to an hour for the environment to be set up.</span></span>
        2. <span data-ttu-id="c1e98-125">Se l'ambiente Dataverse è correttamente configurato, il nome dell'ambiente Dataverse collegato all'ambiente Dynamics 365 Finance dovrebbe essere elencato.</span><span class="sxs-lookup"><span data-stu-id="c1e98-125">If the Dataverse environment is successfully set up, the Dataverse environment name linked to the Dynamics 365 Finance Environment should be listed.</span></span> <span data-ttu-id="c1e98-126">Copia il  nome dell'ambiente Dataverse.</span><span class="sxs-lookup"><span data-stu-id="c1e98-126">Copy the Dataverse environment name.</span></span>
> [!NOTE]
> <span data-ttu-id="c1e98-127">Dopo aver completato la configurazione dell'ambiente, **NON** selezionare il pulsante **Collega a CDS per app**.</span><span class="sxs-lookup"><span data-stu-id="c1e98-127">After completing the environment set up, **DO NOT** select the **Link to CDS for Apps** button.</span></span> <span data-ttu-id="c1e98-128">Non è necessario per Finance Insights e disabiliterà la possibilità di completare i componenti aggiuntivi dell'ambiente richiesti in LCS.</span><span class="sxs-lookup"><span data-stu-id="c1e98-128">This is not needed for Finance Insights and will disable the ability to complete the required Environment Add-ins in LCS.</span></span>

2. <span data-ttu-id="c1e98-129">Apri l'[interfaccia di amministrazione di Power Platform](https://admin.powerplatform.microsoft.com/) e segui questi passaggi per creare un nuovo ambiente Dataverse nello stesso tenant di Active Directory:</span><span class="sxs-lookup"><span data-stu-id="c1e98-129">Open the [Power Platform admin center](https://admin.powerplatform.microsoft.com/), and follow these steps to create a new Dataverse environment in the same Active Directory tenant:</span></span>

    1. <span data-ttu-id="c1e98-130">Apri la pagina **Ambienti**.</span><span class="sxs-lookup"><span data-stu-id="c1e98-130">Open the **Environments** page.</span></span>

        <span data-ttu-id="c1e98-131">[![Pagina Ambienti](./media/power-pltfrm-admin-center.png)](./media/power-pltfrm-admin-center.png)</span><span class="sxs-lookup"><span data-stu-id="c1e98-131">[![Environments page](./media/power-pltfrm-admin-center.png)](./media/power-pltfrm-admin-center.png)</span></span>

    2. <span data-ttu-id="c1e98-132">Seleziona l'ambiente Dataverse creato prima, quindi selezionare **Impostazioni**.</span><span class="sxs-lookup"><span data-stu-id="c1e98-132">Select the Dataverse environment created above and then select **Settings**.</span></span>
    3. <span data-ttu-id="c1e98-133">Seleziona **Risorse \> Tutte le impostazioni legacy**.</span><span class="sxs-lookup"><span data-stu-id="c1e98-133">Select **Resources \> All Legacy Settings**.</span></span>
    4. <span data-ttu-id="c1e98-134">Nella barra di spostamento in alto, seleziona **Impostazioni** e quindi seleziona **Personalizzazioni**.</span><span class="sxs-lookup"><span data-stu-id="c1e98-134">On the top navigation bar, select **Settings**, and then select **Customizations**.</span></span>
    5. <span data-ttu-id="c1e98-135">Seleziona **Risorse per sviluppatori**.</span><span class="sxs-lookup"><span data-stu-id="c1e98-135">Select **Developer Resources**.</span></span>
    6. <span data-ttu-id="c1e98-136">Copia il valore di **ID organizzazione Dataverse**.</span><span class="sxs-lookup"><span data-stu-id="c1e98-136">Copy the **Dataverse organization ID** value.</span></span>
    7. <span data-ttu-id="c1e98-137">Nella barra degli indirizzi del browser, prendi nota dell'URL dell'organizzazione Dataverse.</span><span class="sxs-lookup"><span data-stu-id="c1e98-137">In the browser's address bar, make a note of the URL for the Dataverse organization.</span></span> <span data-ttu-id="c1e98-138">Ad esempio, l'URL potrebbe essere `https://org42b2b3d3.crm.dynamics.com`.</span><span class="sxs-lookup"><span data-stu-id="c1e98-138">For example, the URL might be `https://org42b2b3d3.crm.dynamics.com`.</span></span>

3. <span data-ttu-id="c1e98-139">Se prevedi di utilizzare la funzionalità Previsioni di cassa o Previsioni di budget, segui questi passaggi per aggiornare il limite di annotazioni per la tua organizzazione ad almeno 50 megabyte (MB):</span><span class="sxs-lookup"><span data-stu-id="c1e98-139">If you plan to use the Cash flow forecasts or Budget forecasts feature, follow these steps to update the annotation limit for your organization to at least 50 megabytes (MB):</span></span>

    1. <span data-ttu-id="c1e98-140">Apri il [portale di Power Apps](https://make.powerapps.com).</span><span class="sxs-lookup"><span data-stu-id="c1e98-140">Open the [Power Apps portal](https://make.powerapps.com).</span></span>
    2. <span data-ttu-id="c1e98-141">Seleziona l'ambiente appena creato, quindi seleziona **Impostazioni avanzate**.</span><span class="sxs-lookup"><span data-stu-id="c1e98-141">Select the environment that you just created, and then select **Advanced settings**.</span></span>
    3. <span data-ttu-id="c1e98-142">Seleziona **Impostazioni \> Configurazione e-mail**.</span><span class="sxs-lookup"><span data-stu-id="c1e98-142">Select **Settings \> Email Configuration**.</span></span>
    4. <span data-ttu-id="c1e98-143">Modifica il valore del campo **Dimensioni massime file** su **51.200**.</span><span class="sxs-lookup"><span data-stu-id="c1e98-143">Change the value of the **Maximum file size** field to **51,200**.</span></span> <span data-ttu-id="c1e98-144">Il valore viene espresso in kilobytes \[KB\].</span><span class="sxs-lookup"><span data-stu-id="c1e98-144">(The value is expressed in kilobytes \[KB\].)</span></span>
    5. <span data-ttu-id="c1e98-145">Seleziona **OK** per salvare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="c1e98-145">Select **OK** to save your changes.</span></span>

## <a name="configure-the-azure-setup"></a><span data-ttu-id="c1e98-146">Configurare l'impostazione di Azure</span><span class="sxs-lookup"><span data-stu-id="c1e98-146">Configure the Azure setup</span></span>

### <a name="enter-the-dataverse-directory-id-and-the-users-azure-ad-object-id"></a><span data-ttu-id="c1e98-147">Immettere l'ID directory di Dataverse e l'iD oggetto Azure AD dell'utente</span><span class="sxs-lookup"><span data-stu-id="c1e98-147">Enter the Dataverse directory ID and the user's Azure AD object ID</span></span>

1. <span data-ttu-id="c1e98-148">Immetti l'ID directory di Dataverse :</span><span class="sxs-lookup"><span data-stu-id="c1e98-148">Enter the Dataverse directory ID:</span></span>

    1. <span data-ttu-id="c1e98-149">Apri il [portale di Azure](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="c1e98-149">Open the [Azure portal](https://portal.azure.com).</span></span>
    2. <span data-ttu-id="c1e98-150">Accedi utilizzando l'ID utente utilizzato per creare l'ambiente Dataverse.</span><span class="sxs-lookup"><span data-stu-id="c1e98-150">Sign in by using the user ID that was used to create the Dataverse environment.</span></span>
    3. <span data-ttu-id="c1e98-151">Accedere a **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="c1e98-151">Go to **Azure Active Directory**.</span></span>
    4. <span data-ttu-id="c1e98-152">Copia il valore di **ID tenant**.</span><span class="sxs-lookup"><span data-stu-id="c1e98-152">Copy the **Tenant ID** value.</span></span>

2. <span data-ttu-id="c1e98-153">Immettere l'ID oggetto Azure Active Directory (Azure AD) dell'utente:</span><span class="sxs-lookup"><span data-stu-id="c1e98-153">Enter the user's Azure Active Directory (Azure AD) object ID:</span></span>

    1. <span data-ttu-id="c1e98-154">Nel [portale di Azure](https://portal.azure.com), vai a **Utenti** e cerca l'utente tramite indirizzo email.</span><span class="sxs-lookup"><span data-stu-id="c1e98-154">In the [Azure portal](https://portal.azure.com), go to **Users**, and search for the user by email address.</span></span>
    2. <span data-ttu-id="c1e98-155">Seleziona il nome dell'utente.</span><span class="sxs-lookup"><span data-stu-id="c1e98-155">Select the user's name.</span></span>
    3. <span data-ttu-id="c1e98-156">Copia il valore di **ID oggetto**.</span><span class="sxs-lookup"><span data-stu-id="c1e98-156">Copy the **Object ID** value.</span></span>

### <a name="use-azure-cloud-shell-to-set-up-finance-insights-data-lake-resources"></a><span data-ttu-id="c1e98-157">Utilizzare Azure Cloud Shell per configurare le risorse Data Lake di Finance Insights</span><span class="sxs-lookup"><span data-stu-id="c1e98-157">Use Azure Cloud Shell to set up Finance insights Data Lake resources</span></span>

# <a name="use-a-windows-powershell-script"></a>[<span data-ttu-id="c1e98-158">Utilizzare uno script di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c1e98-158">Use a Windows PowerShell script</span></span>](#tab/use-a-powershell-script)

<span data-ttu-id="c1e98-159">È stato fornito uno script di Windows PowerShell, in modo da poter configurare facilmente le risorse di Azure descritte in [Configurare l'esportazione in Azure Data Lake](../../fin-ops-core/dev-itpro/data-entities/configure-export-data-lake.md).</span><span class="sxs-lookup"><span data-stu-id="c1e98-159">A Windows PowerShell script has been provided, so that you can easily set up the Azure resources that are described in [Configure export to Azure Data Lake](../../fin-ops-core/dev-itpro/data-entities/configure-export-data-lake.md).</span></span> <span data-ttu-id="c1e98-160">Se preferisci eseguire la configurazione manuale, salta questa procedura e continua con la procedura della sezione [Configurazione manuale](#manual-setup).</span><span class="sxs-lookup"><span data-stu-id="c1e98-160">If you prefer to do manual setup, skip this procedure, and continue with the procedure in the [Manual setup](#manual-setup) section.</span></span>

> [!NOTE]
> <span data-ttu-id="c1e98-161">Segui i passaggi seguenti per eseguire lo script di PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c1e98-161">Follow the steps below to run the PowerShell script.</span></span> <span data-ttu-id="c1e98-162">L'opzione "Provalo" dell'interfaccia della riga di comando di Azure o l'esecuzione dello script sul PC potrebbe non funzionare.</span><span class="sxs-lookup"><span data-stu-id="c1e98-162">The Azure CLI "Try it" option, or running the script on your PC may not work.</span></span>

<span data-ttu-id="c1e98-163">Attieniti alla seguente procedura per configurare Azure utilizzando lo script di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c1e98-163">Follow these steps to configure Azure by using the Windows PowerShell script.</span></span> <span data-ttu-id="c1e98-164">Devi disporre dei diritti per creare un gruppo di risorse di Azure, risorse di Azure e un'applicazione Azure AD.</span><span class="sxs-lookup"><span data-stu-id="c1e98-164">You must have rights to create an Azure resource group, Azure resources, and an Azure AD application.</span></span> <span data-ttu-id="c1e98-165">Per informazioni sulle autorizzazioni obbligatorie, vedi [Controllare le autorizzazioni di Azure AD](/azure/active-directory/develop/howto-create-service-principal-portal#permissions-required-for-registering-an-app).</span><span class="sxs-lookup"><span data-stu-id="c1e98-165">For information about the required permissions, see [Check Azure AD permissions](/azure/active-directory/develop/howto-create-service-principal-portal#permissions-required-for-registering-an-app).</span></span>

1. <span data-ttu-id="c1e98-166">Nel [portale di Azure](https://portal.azure.com), vai alla sottoscrizione di Azure di destinazione.</span><span class="sxs-lookup"><span data-stu-id="c1e98-166">In the [Azure portal](https://portal.azure.com), go to your target Azure subscription.</span></span> <span data-ttu-id="c1e98-167">Seleziona il pulsante **Cloud Shell** a destra del campo **Cerca**.</span><span class="sxs-lookup"><span data-stu-id="c1e98-167">Select the **Cloud Shell** button to the right of the **Search** field.</span></span>
2. <span data-ttu-id="c1e98-168">Seleziona **PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="c1e98-168">Select **PowerShell**.</span></span>
3. <span data-ttu-id="c1e98-169">Crea lo spazio di archiviazione, se ti viene chiesto di farlo.</span><span class="sxs-lookup"><span data-stu-id="c1e98-169">Create storage if you're prompted to do so.</span></span>
4. <span data-ttu-id="c1e98-170">Vai alla scheda **Interfaccia della riga di comando di Azure** e seleziona **Copia**.</span><span class="sxs-lookup"><span data-stu-id="c1e98-170">Go to the **Azure CLI** tab and select **Copy**.</span></span>  
5. <span data-ttu-id="c1e98-171">Apri Blocco note e incolla lo script di PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c1e98-171">Open Notepad and paste the PowerShell script.</span></span> <span data-ttu-id="c1e98-172">Salva il file come ConfigureDataLake.ps1.</span><span class="sxs-lookup"><span data-stu-id="c1e98-172">Save the file as ConfigureDataLake.ps1.</span></span>
6. <span data-ttu-id="c1e98-173">Carica lo script di Windows PowerShell nella sessione utilizzando l'opzione di menu per il caricamento in Cloud Shell.</span><span class="sxs-lookup"><span data-stu-id="c1e98-173">Upload the Windows PowerShell script to the session using the menu option for upload in Cloud Shell.</span></span>
7. <span data-ttu-id="c1e98-174">Esegui lo script .\ConfigureDataLake.ps1.</span><span class="sxs-lookup"><span data-stu-id="c1e98-174">Run the script .\ConfigureDataLake.ps1.</span></span>
8. <span data-ttu-id="c1e98-175">Segui le istruzioni per eseguire lo script.</span><span class="sxs-lookup"><span data-stu-id="c1e98-175">Follow the prompts to run the script.</span></span>
9. <span data-ttu-id="c1e98-176">Utilizza le informazioni dall'output dello script per installare il componente aggiuntivo **Esporta in Data Lake** in LCS.</span><span class="sxs-lookup"><span data-stu-id="c1e98-176">Use the information from the script output to install the **Export to Data Lake** add-in in LCS.</span></span>
10. <span data-ttu-id="c1e98-177">Utilizza le informazioni dall'output dello script per abilitare l'archivio entità nella pagina **Connessioni dati** in Finanza (**Amministrazione di sistema \> Parametri di sistema \> Connessioni dati**).</span><span class="sxs-lookup"><span data-stu-id="c1e98-177">Use the information from the script output to enable the entity store on the **Data connections** page in Finance (**System administration \> System parameters \> Data connections**).</span></span>

### <a name="manual-setup"></a><span data-ttu-id="c1e98-178">Configurazione manuale</span><span class="sxs-lookup"><span data-stu-id="c1e98-178">Manual setup</span></span>

#### <a name="add-applications-to-the-azure-ad-tenant"></a><span data-ttu-id="c1e98-179">Aggiungere applicazioni al tenant Azure AD</span><span class="sxs-lookup"><span data-stu-id="c1e98-179">Add applications to the Azure AD tenant</span></span>

1. <span data-ttu-id="c1e98-180">Nel [portale di Azure](https://portal.azure.com), passa a **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="c1e98-180">In the [Azure portal](https://portal.azure.com), go to **Azure Active Directory**.</span></span>
2. <span data-ttu-id="c1e98-181">Seleziona **Gestisci \> Applicazioni aziendali**.</span><span class="sxs-lookup"><span data-stu-id="c1e98-181">Select **Manage \> Enterprise applications**.</span></span>
3. <span data-ttu-id="c1e98-182">Cerca le seguenti applicazioni per ID app.</span><span class="sxs-lookup"><span data-stu-id="c1e98-182">Search for the following applications by app ID.</span></span>

    | <span data-ttu-id="c1e98-183">Domanda di lavoro</span><span class="sxs-lookup"><span data-stu-id="c1e98-183">Application</span></span>                              | <span data-ttu-id="c1e98-184">ID app</span><span class="sxs-lookup"><span data-stu-id="c1e98-184">App ID</span></span>                               |
    |------------------------------------------|--------------------------------------|
    | <span data-ttu-id="c1e98-185">Microservizi ERP Microsoft Dynamics</span><span class="sxs-lookup"><span data-stu-id="c1e98-185">Microsoft Dynamics ERP Microservices</span></span>     | <span data-ttu-id="c1e98-186">0cdb527f-a8d1-4bf8-9436-b352c68682b2</span><span class="sxs-lookup"><span data-stu-id="c1e98-186">0cdb527f-a8d1-4bf8-9436-b352c68682b2</span></span> |
    | <span data-ttu-id="c1e98-187">CDS microservizi ERP Microsoft Dynamics</span><span class="sxs-lookup"><span data-stu-id="c1e98-187">Microsoft Dynamics ERP Microservices CDS</span></span> | <span data-ttu-id="c1e98-188">703e2651-d3fc-48f5-942c-74274233dba8</span><span class="sxs-lookup"><span data-stu-id="c1e98-188">703e2651-d3fc-48f5-942c-74274233dba8</span></span> |
    | <span data-ttu-id="c1e98-189">Servizio di autorizzazione di AI Builder</span><span class="sxs-lookup"><span data-stu-id="c1e98-189">AI Builder Authorization Service</span></span>         | <span data-ttu-id="c1e98-190">ad40333e-9910-4b61-b281-e3aeeb8c3ef3</span><span class="sxs-lookup"><span data-stu-id="c1e98-190">ad40333e-9910-4b61-b281-e3aeeb8c3ef3</span></span> |

<span data-ttu-id="c1e98-191">Se non riesci a trovare nessuna delle applicazioni precedenti, prova i seguenti passaggi.</span><span class="sxs-lookup"><span data-stu-id="c1e98-191">If you can't find any of the preceding applications, try the following steps.</span></span>

1. <span data-ttu-id="c1e98-192">Sul tuo computer locale, seleziona il menu **Start** e cerca **powershell**.</span><span class="sxs-lookup"><span data-stu-id="c1e98-192">On your local machine, select the **Start** menu, and search for **powershell**.</span></span>
2. <span data-ttu-id="c1e98-193">Seleziona e tieni premuto (o fai clic con il pulsante destro del mouse su) **Windows PowerShell** e quindi seleziona **Esegui come amministratore**.</span><span class="sxs-lookup"><span data-stu-id="c1e98-193">Select and hold (or right-click) **Windows PowerShell**, and then select **Run as administrator**.</span></span>
3. <span data-ttu-id="c1e98-194">Esegui il comando seguente per installare il modulo **AzureAD**.</span><span class="sxs-lookup"><span data-stu-id="c1e98-194">Run the following command to install the **AzureAD** module.</span></span>

    `Install-Module -Name AzureAD`

4. <span data-ttu-id="c1e98-195">Se è necessario un provider NuGet per continuare, seleziona **Y** per installarlo.</span><span class="sxs-lookup"><span data-stu-id="c1e98-195">If a NuGet provider is required to continue, select **Y** to install it.</span></span>
5. <span data-ttu-id="c1e98-196">Se viene visualizzato il messaggio "Repository non attendibile", seleziona **Y** per continuare.</span><span class="sxs-lookup"><span data-stu-id="c1e98-196">If an "Untrusted repository" message appears, select **Y** to continue.</span></span>
6. <span data-ttu-id="c1e98-197">Per ciascuna applicazione che deve essere aggiunta, esegui i seguenti comandi per aggiungere l'applicazione ad Azure AD.</span><span class="sxs-lookup"><span data-stu-id="c1e98-197">For each application that must be added, run the following commands to add the application to Azure AD.</span></span> <span data-ttu-id="c1e98-198">Quando ti viene richiesto, accedi come amministratore Azure AD.</span><span class="sxs-lookup"><span data-stu-id="c1e98-198">When you're prompted, sign in as the Azure AD administrator.</span></span>

    `Connect-AzureAD`

    `New-AzureADServicePrincipal –AppId <AppId>`

#### <a name="create-azure-resources"></a><span data-ttu-id="c1e98-199">Creare risorse Azure</span><span class="sxs-lookup"><span data-stu-id="c1e98-199">Create Azure resources</span></span>

> [!NOTE]
> <span data-ttu-id="c1e98-200">Assicurati di creare le seguenti risorse nella stessa istanza di Azure AD come l'ambiente Dataverse.</span><span class="sxs-lookup"><span data-stu-id="c1e98-200">Make sure that you create the following resources in the same Azure AD instance as the Dataverse environment.</span></span> <span data-ttu-id="c1e98-201">Non puoi utilizzare risorse da un'altra istanza di Azure AD.</span><span class="sxs-lookup"><span data-stu-id="c1e98-201">You can't use resources from a different Azure AD instance.</span></span>

1. <span data-ttu-id="c1e98-202">Creare un nuovo account di archiviazione:</span><span class="sxs-lookup"><span data-stu-id="c1e98-202">Create a new storage account:</span></span>

    1. <span data-ttu-id="c1e98-203">Nel [portale di Azure](https://portal.azure.com), crea un account di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="c1e98-203">In the [Azure portal](https://portal.azure.com), create a storage account.</span></span>
    2. <span data-ttu-id="c1e98-204">Nella finestra di dialogo **Crea account di archiviazione**, imposta i seguenti campi:</span><span class="sxs-lookup"><span data-stu-id="c1e98-204">In the **Create storage account** dialog box, set the following fields:</span></span>

        - <span data-ttu-id="c1e98-205">**Posizione**: seleziona il data center in cui si trova il tuo ambiente.</span><span class="sxs-lookup"><span data-stu-id="c1e98-205">**Location** – Select the data center where your environment is located.</span></span>
        - <span data-ttu-id="c1e98-206">**Prestazioni**: è compatibile selezionare **Standard**.</span><span class="sxs-lookup"><span data-stu-id="c1e98-206">**Performance** – We recommend that you select **Standard**.</span></span>
        - <span data-ttu-id="c1e98-207">**Tipo di account**: devi selezionare **StorageV2**.</span><span class="sxs-lookup"><span data-stu-id="c1e98-207">**Account kind** – You must select **StorageV2**.</span></span>

    3. <span data-ttu-id="c1e98-208">Nella finestra di dialogo **Opzioni avanzate**, per l'opzione **Data Lake Storage Gen2**, seleziona **Abilita** nella funzionalità **Spazi dei nomi gerarchici**.</span><span class="sxs-lookup"><span data-stu-id="c1e98-208">In the **Advanced options** dialog box, for the **Data Lake storage Gen2** option, select **Enable** under the **Hierarchical namespaces** feature.</span></span> <span data-ttu-id="c1e98-209">Se disabiliti questa funzionalità, non puoi utilizzare i dati che le app Finance and Operations scrivono utilizzando servizi come i flussi di dati di Power BI.</span><span class="sxs-lookup"><span data-stu-id="c1e98-209">If you disable this feature, you can't consume data that Finance and Operations apps write by using services such as Power BI data flows.</span></span>
    4. <span data-ttu-id="c1e98-210">Seleziona **Rivedi e crea**.</span><span class="sxs-lookup"><span data-stu-id="c1e98-210">Select **Review and create**.</span></span> <span data-ttu-id="c1e98-211">Al termine della distribuzione, la nuova risorsa verrà visualizzata nel portale di Azure.</span><span class="sxs-lookup"><span data-stu-id="c1e98-211">When the deployment is completed, the new resource will be shown in the Azure portal.</span></span>
    5. <span data-ttu-id="c1e98-212">Vai all'account di archiviazione che hai creato.</span><span class="sxs-lookup"><span data-stu-id="c1e98-212">Go to the storage account that you created.</span></span>
    6. <span data-ttu-id="c1e98-213">Nel menu a sinistra, seleziona **Chiavi di accesso**.</span><span class="sxs-lookup"><span data-stu-id="c1e98-213">On the left menu, select **Access keys**.</span></span>
    7. <span data-ttu-id="c1e98-214">Copia e salva la stringa di connessione per entrambe **Chiave 1** o **Chiave 2**.</span><span class="sxs-lookup"><span data-stu-id="c1e98-214">Copy and save the connection string for either **Key1** or **Key2**.</span></span>
    8. <span data-ttu-id="c1e98-215">Copia e salva il nome dell'account di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="c1e98-215">Copy and save the storage account name.</span></span>

2. <span data-ttu-id="c1e98-216">Crea un nuovo Key Vault:</span><span class="sxs-lookup"><span data-stu-id="c1e98-216">Create a new key vault:</span></span>

    1. <span data-ttu-id="c1e98-217">Nel [portale di Azure](https://portal.azure.com), crea un Key Vault.</span><span class="sxs-lookup"><span data-stu-id="c1e98-217">In the [Azure portal](https://portal.azure.com), create a key vault.</span></span>
    2. <span data-ttu-id="c1e98-218">Nella finestra di dialogo **Crea Key Vault**, nel campo **Posizione**, seleziona il data center in cui si trova il tuo ambiente.</span><span class="sxs-lookup"><span data-stu-id="c1e98-218">In the **Create key vault** dialog box, in the **Location** field, select the data center where your environment is located.</span></span>
    3. <span data-ttu-id="c1e98-219">Dopo aver creato il Key Vault, selezionalo nell'elenco, quindi seleziona **Segreti**.</span><span class="sxs-lookup"><span data-stu-id="c1e98-219">After key vault is created, select it in the list, and then select **Secrets**.</span></span>
    4. <span data-ttu-id="c1e98-220">Seleziona **Genera/Importa**.</span><span class="sxs-lookup"><span data-stu-id="c1e98-220">Select **Generate/Import**.</span></span>
    5. <span data-ttu-id="c1e98-221">Nella finestra di dialogo **Crea un segreto**, nel campo **Opzioni di caricamento**, seleziona **Manuale**.</span><span class="sxs-lookup"><span data-stu-id="c1e98-221">In the **Create a secret** dialog box, in the **Upload options** field, select **Manual**.</span></span>
    6. <span data-ttu-id="c1e98-222">Immetti un nome per il segreto.</span><span class="sxs-lookup"><span data-stu-id="c1e98-222">Enter a name for the secret.</span></span> <span data-ttu-id="c1e98-223">Prendi nota del nome, perché dovrai specificarlo in seguito.</span><span class="sxs-lookup"><span data-stu-id="c1e98-223">Make a note of the name, because you will have to provide it later.</span></span>
    7. <span data-ttu-id="c1e98-224">Nel campo **Valore** immetti la stringa di connessione ottenuta dall'account di archiviazione nella procedura precedente.</span><span class="sxs-lookup"><span data-stu-id="c1e98-224">In the **Value** field, enter the connection string that you obtained from the storage account in the previous procedure.</span></span>
    8. <span data-ttu-id="c1e98-225">Seleziona **Abilitato** e quindi **Crea**.</span><span class="sxs-lookup"><span data-stu-id="c1e98-225">Select **Enabled**, and then select **Create**.</span></span> <span data-ttu-id="c1e98-226">Il segreto viene creato e aggiunto al Key Vault.</span><span class="sxs-lookup"><span data-stu-id="c1e98-226">The secret is created and added to Key Vault.</span></span>
    9. <span data-ttu-id="c1e98-227">Vai a **Panoramica del Key Vault** e prendi nota del nome DNS.</span><span class="sxs-lookup"><span data-stu-id="c1e98-227">Go to the **Key Vault Overview**, and make a note of the DNS name.</span></span>

3. <span data-ttu-id="c1e98-228">Crea e registra un'applicazione Azure AD:</span><span class="sxs-lookup"><span data-stu-id="c1e98-228">Create and register an Azure AD application:</span></span>

    1. <span data-ttu-id="c1e98-229">Nel [portale di Azure](https://portal.azure.com), passa ad **Azure Active Directory**, quindi seleziona **Registrazioni app**.</span><span class="sxs-lookup"><span data-stu-id="c1e98-229">In the [Azure portal](https://portal.azure.com), go to **Azure Active Directory**, and then select **App registrations**.</span></span>
    2. <span data-ttu-id="c1e98-230">Seleziona **Nuova registrazione dell'applicazione** e imposta i seguenti campi:</span><span class="sxs-lookup"><span data-stu-id="c1e98-230">Select **New application registration**, and set the following fields:</span></span>

        - <span data-ttu-id="c1e98-231">**Nome**: immetti il nome dell'app.</span><span class="sxs-lookup"><span data-stu-id="c1e98-231">**Name** – Enter the name of the app.</span></span>
        - <span data-ttu-id="c1e98-232">**Tipo di applicazione**: seleziona **API Web**.</span><span class="sxs-lookup"><span data-stu-id="c1e98-232">**Application type** – Select **Web API**.</span></span>
        - <span data-ttu-id="c1e98-233">**Configurazione URI reindirizzamento**: immetti l'URL per la tua istanza di Dynamics 365, ad esempio, `https://yourdynamicsinstance.dynamics.com/auth`.</span><span class="sxs-lookup"><span data-stu-id="c1e98-233">**Redirect URI setup** – Enter the URL for your Dynamics 365 instance, such as, `https://yourdynamicsinstance.dynamics.com/auth`.</span></span>

    3. <span data-ttu-id="c1e98-234">Vai all'app che hai appena creato e copia e salva il suo valore **ID applicazione (client)**.</span><span class="sxs-lookup"><span data-stu-id="c1e98-234">Go to the app that you just created, and copy and save its **Application (client) ID** value.</span></span> <span data-ttu-id="c1e98-235">Dovrai fornire questo valore in un secondo momento, quando configuri il Key Vault.</span><span class="sxs-lookup"><span data-stu-id="c1e98-235">You will have to provide this value later, when you set up the key vault.</span></span>
    4. <span data-ttu-id="c1e98-236">Vai ad **Autorizzazioni API** e segui questi passaggi:</span><span class="sxs-lookup"><span data-stu-id="c1e98-236">Go to **API permissions**, and follow these steps:</span></span>

        1. <span data-ttu-id="c1e98-237">Seleziona **Aggiungi un'autorizzazione**.</span><span class="sxs-lookup"><span data-stu-id="c1e98-237">Select **Add a permission**.</span></span>
        2. <span data-ttu-id="c1e98-238">Seleziona **Azure Key Vault**.</span><span class="sxs-lookup"><span data-stu-id="c1e98-238">Select **Azure Key vault**.</span></span>
        3. <span data-ttu-id="c1e98-239">Dopo aver selezionato le autorizzazioni delegate, seleziona **utente\_impersonificazione**.</span><span class="sxs-lookup"><span data-stu-id="c1e98-239">After you select delegated permissions, select **user\_impersonation**.</span></span>
        4. <span data-ttu-id="c1e98-240">Seleziona **Aggiungi autorizzazioni**.</span><span class="sxs-lookup"><span data-stu-id="c1e98-240">Select **Add permissions**.</span></span>

    5. <span data-ttu-id="c1e98-241">Nel menu dell'app, seleziona **Certificati \& segreti** e quindi segui questi passaggi per creare segreti di Key Vault:</span><span class="sxs-lookup"><span data-stu-id="c1e98-241">On the menu for the app, select **Certificates \& secrets**, and then follow these steps to create Key Vault secrets:</span></span>

        1. <span data-ttu-id="c1e98-242">Seleziona **Nuovo segreto client**.</span><span class="sxs-lookup"><span data-stu-id="c1e98-242">Select **New client secret**.</span></span>
        2. <span data-ttu-id="c1e98-243">Nel campo **Descrizione chiave** immetti un nome.</span><span class="sxs-lookup"><span data-stu-id="c1e98-243">In the **Key Description** field, enter a name.</span></span>
        3. <span data-ttu-id="c1e98-244">Seleziona una durata e quindi seleziona **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="c1e98-244">Select a duration, and then select **Add**.</span></span> <span data-ttu-id="c1e98-245">Un segreto viene generato nel campo **Valore**.</span><span class="sxs-lookup"><span data-stu-id="c1e98-245">A secret is generated in the **Value** field.</span></span>
        4. <span data-ttu-id="c1e98-246">Copia e salva il valore del segreto.</span><span class="sxs-lookup"><span data-stu-id="c1e98-246">Copy and save the secret value.</span></span>

4. <span data-ttu-id="c1e98-247">Crea segreti Key Vault:</span><span class="sxs-lookup"><span data-stu-id="c1e98-247">Create Key Vault secrets:</span></span>

    1. <span data-ttu-id="c1e98-248">Vai al Key Vault creato in precedenza e seleziona **Segreti**.</span><span class="sxs-lookup"><span data-stu-id="c1e98-248">Go to the key vault that you created earlier, and select **Secrets**.</span></span>
    2. <span data-ttu-id="c1e98-249">Per ogni nome segreto nella tabella seguente, segui questi passaggi:</span><span class="sxs-lookup"><span data-stu-id="c1e98-249">For each secret name in the following table, follow these steps:</span></span>

        1. <span data-ttu-id="c1e98-250">Seleziona **Genera/Importa**.</span><span class="sxs-lookup"><span data-stu-id="c1e98-250">Select **Generate/Import**.</span></span>
        2. <span data-ttu-id="c1e98-251">Nella finestra di dialogo **Crea un segreto**, nel campo **Opzioni di caricamento**, seleziona **Manuale**.</span><span class="sxs-lookup"><span data-stu-id="c1e98-251">In the **Create a secret** dialog box, in the **Upload options** field, select **Manual**.</span></span>
        3. <span data-ttu-id="c1e98-252">Crea il nome e il valore del segreto dalla seguente tabella.</span><span class="sxs-lookup"><span data-stu-id="c1e98-252">Create the secret name and value from the following table.</span></span>
        4. <span data-ttu-id="c1e98-253">Seleziona **Abilitato** e quindi **Crea**.</span><span class="sxs-lookup"><span data-stu-id="c1e98-253">Select **Enabled**, and then select **Create**.</span></span> <span data-ttu-id="c1e98-254">Il segreto viene creato e aggiunto al Key Vault.</span><span class="sxs-lookup"><span data-stu-id="c1e98-254">The secret is created and added to Key Vault.</span></span>

        | <span data-ttu-id="c1e98-255">Nome segreto</span><span class="sxs-lookup"><span data-stu-id="c1e98-255">Secret name</span></span>                       | <span data-ttu-id="c1e98-256">Valore segreto</span><span class="sxs-lookup"><span data-stu-id="c1e98-256">Secret value</span></span>                                                                                |
        |-----------------------------------|---------------------------------------------------------------------------------------------|
        | <span data-ttu-id="c1e98-257">app-id</span><span class="sxs-lookup"><span data-stu-id="c1e98-257">app-id</span></span>                            | <span data-ttu-id="c1e98-258">L'ID app dell'applicazione che hai creato in precedenza</span><span class="sxs-lookup"><span data-stu-id="c1e98-258">The app ID of the application that you created earlier</span></span>                                      |
        | <span data-ttu-id="c1e98-259">app-secret</span><span class="sxs-lookup"><span data-stu-id="c1e98-259">app-secret</span></span>                        | <span data-ttu-id="c1e98-260">Il segreto client che hai salvato in precedenza</span><span class="sxs-lookup"><span data-stu-id="c1e98-260">The client secret that you saved earlier</span></span>                                                    |
        | <span data-ttu-id="c1e98-261">storage-account-name</span><span class="sxs-lookup"><span data-stu-id="c1e98-261">storage-account-name</span></span>              | <span data-ttu-id="c1e98-262">Il nome dell'account di archiviazione creato in precedenza, ad esempio **storageaccount1**</span><span class="sxs-lookup"><span data-stu-id="c1e98-262">The name of the storage account that you created earlier, such as **storageaccount1**</span></span>       |
        | <span data-ttu-id="c1e98-263">storage-account-connection-string</span><span class="sxs-lookup"><span data-stu-id="c1e98-263">storage-account-connection-string</span></span> | <span data-ttu-id="c1e98-264">La stringa di connessione che hai copiato dalla pagina **Chiavi di accesso** per l'account di archiviazione</span><span class="sxs-lookup"><span data-stu-id="c1e98-264">The connection string that you copied from the **Access keys** page for the storage account</span></span> |

5. <span data-ttu-id="c1e98-265">Autorizza l'applicazione ad accedere al Key Vault:</span><span class="sxs-lookup"><span data-stu-id="c1e98-265">Authorize the application to access the key vault:</span></span>

    1. <span data-ttu-id="c1e98-266">Nel [portale di Azure](https://portal.azure.com), apri il Key Vault creato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="c1e98-266">In the [Azure portal](https://portal.azure.com), open the key vault that you created earlier.</span></span>
    2. <span data-ttu-id="c1e98-267">Seleziona i criteri di accesso.</span><span class="sxs-lookup"><span data-stu-id="c1e98-267">Select the access policies.</span></span>
    3. <span data-ttu-id="c1e98-268">Per ogni applicazione nella tabella seguente, segui questi passaggi:</span><span class="sxs-lookup"><span data-stu-id="c1e98-268">For each application in the following table, follow these steps:</span></span>

        1. <span data-ttu-id="c1e98-269">Seleziona **Aggiungi criteri di accesso** per creare un criterio di accesso.</span><span class="sxs-lookup"><span data-stu-id="c1e98-269">Select **Add Access Policy** to create an access policy.</span></span>
        2. <span data-ttu-id="c1e98-270">Nel campo **Autorizzazioni segreto**, seleziona le autorizzazioni dalla tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="c1e98-270">In the **Secret permissions** field, select the permissions from the following table.</span></span>
        3. <span data-ttu-id="c1e98-271">Nel campo **Seleziona entità di sicurezza**, cerca il nome visualizzato dell'applicazione dalla tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="c1e98-271">In the **Select principal** field, search for the application display name from the following table.</span></span>
        4. <span data-ttu-id="c1e98-272">Selezionare **Select**.</span><span class="sxs-lookup"><span data-stu-id="c1e98-272">Select **Select**.</span></span>
        5. <span data-ttu-id="c1e98-273">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="c1e98-273">Select **Add**.</span></span>
        6. <span data-ttu-id="c1e98-274">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="c1e98-274">Select **Save**.</span></span>

        | <span data-ttu-id="c1e98-275">Domanda di lavoro</span><span class="sxs-lookup"><span data-stu-id="c1e98-275">Application</span></span>                                              | <span data-ttu-id="c1e98-276">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="c1e98-276">Permissions</span></span> |
        |----------------------------------------------------------|-------------|
        | <span data-ttu-id="c1e98-277">Il nome visualizzato della nuova applicazione che hai creato</span><span class="sxs-lookup"><span data-stu-id="c1e98-277">The display name of the new application that you created</span></span> | <span data-ttu-id="c1e98-278">Get, List</span><span class="sxs-lookup"><span data-stu-id="c1e98-278">Get, List</span></span>   |
        | <span data-ttu-id="c1e98-279">**Microservizi ERP Microsoft Dynamics**</span><span class="sxs-lookup"><span data-stu-id="c1e98-279">**Microsoft Dynamics ERP Microservices**</span></span>                 | <span data-ttu-id="c1e98-280">Get, List</span><span class="sxs-lookup"><span data-stu-id="c1e98-280">Get, List</span></span>   |

6. <span data-ttu-id="c1e98-281">Assegna ruoli per accedere all'account di archiviazione:</span><span class="sxs-lookup"><span data-stu-id="c1e98-281">Assign roles to access the storage account:</span></span>

    1. <span data-ttu-id="c1e98-282">Nel [portale di Azure](https://portal.azure.com), apri l'account di archiviazione creato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="c1e98-282">In the [Azure portal](https://portal.azure.com), open the storage account that you created earlier.</span></span>
    2. <span data-ttu-id="c1e98-283">Seleziona **Controllo dei diritti di accesso (IAM)** e quindi seleziona **Assegnazioni di ruolo**.</span><span class="sxs-lookup"><span data-stu-id="c1e98-283">Select **Access Control (IAM)**, and then select **Role Assignments**.</span></span>
    3. <span data-ttu-id="c1e98-284">Seleziona **Aggiungi, Aggiungi assegnazione di ruolo**.</span><span class="sxs-lookup"><span data-stu-id="c1e98-284">Select **Add, Add Role Assignment**.</span></span>
    4. <span data-ttu-id="c1e98-285">Per ogni applicazione nella tabella seguente, segui questi passaggi:</span><span class="sxs-lookup"><span data-stu-id="c1e98-285">For each application in the following table, follow these steps:</span></span>

        1. <span data-ttu-id="c1e98-286">Seleziona il ruolo dalla tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="c1e98-286">Select the role from the following table.</span></span>
        2. <span data-ttu-id="c1e98-287">Lascia il campo **Assegna accesso a** impostato su **Utente, gruppo o entità servizio Azure AD**.</span><span class="sxs-lookup"><span data-stu-id="c1e98-287">Leave the **Assign access to** field set to **Azure AD user, group, or service principal**.</span></span>
        3. <span data-ttu-id="c1e98-288">Nel campo **Seleziona**, immetti l'applicazione dalla tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="c1e98-288">In the **Select** field, enter the application from the following table.</span></span>
        4. <span data-ttu-id="c1e98-289">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="c1e98-289">Select **Save**.</span></span>

        | <span data-ttu-id="c1e98-290">Domanda di lavoro</span><span class="sxs-lookup"><span data-stu-id="c1e98-290">Application</span></span>                                              | <span data-ttu-id="c1e98-291">Ruolo</span><span class="sxs-lookup"><span data-stu-id="c1e98-291">Role</span></span>                        |
        |----------------------------------------------------------|-----------------------------|
        | <span data-ttu-id="c1e98-292">Il nome visualizzato della nuova applicazione che hai creato</span><span class="sxs-lookup"><span data-stu-id="c1e98-292">The display name of the new application that you created</span></span> | <span data-ttu-id="c1e98-293">Proprietario</span><span class="sxs-lookup"><span data-stu-id="c1e98-293">Owner</span></span>                       |
        | <span data-ttu-id="c1e98-294">Il nome visualizzato della nuova applicazione che hai creato</span><span class="sxs-lookup"><span data-stu-id="c1e98-294">The display name of the new application that you created</span></span> | <span data-ttu-id="c1e98-295">Collaboratore</span><span class="sxs-lookup"><span data-stu-id="c1e98-295">Contributor</span></span>                 |
        | <span data-ttu-id="c1e98-296">Il nome visualizzato della nuova applicazione che hai creato</span><span class="sxs-lookup"><span data-stu-id="c1e98-296">The display name of the new application that you created</span></span> | <span data-ttu-id="c1e98-297">Collaboratore account di archiviazione</span><span class="sxs-lookup"><span data-stu-id="c1e98-297">Storage Account Contributor</span></span> |
        | <span data-ttu-id="c1e98-298">Il nome visualizzato della nuova applicazione che hai creato</span><span class="sxs-lookup"><span data-stu-id="c1e98-298">The display name of the new application that you created</span></span> | <span data-ttu-id="c1e98-299">Proprietario dei dati del BLOB di archiviazione</span><span class="sxs-lookup"><span data-stu-id="c1e98-299">Storage Blob Data Owner</span></span>     |
        | <span data-ttu-id="c1e98-300">**Servizio di autorizzazione di AI Builder**</span><span class="sxs-lookup"><span data-stu-id="c1e98-300">**AI Builder Authorization Service**</span></span>                     | <span data-ttu-id="c1e98-301">Lettore dati del BLOB di archiviazione</span><span class="sxs-lookup"><span data-stu-id="c1e98-301">Storage Blob Data Reader</span></span>    |

# <a name="azure-cli"></a>[<span data-ttu-id="c1e98-302">Azure CLI</span><span class="sxs-lookup"><span data-stu-id="c1e98-302">Azure CLI</span></span>](#tab/azure-azure-cli)

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



## <a name="configure-the-data-lake"></a><span data-ttu-id="c1e98-303">Configurare il data lake</span><span class="sxs-lookup"><span data-stu-id="c1e98-303">Configure the data lake</span></span>

<span data-ttu-id="c1e98-304">Segui questi passaggi per utilizzare LCS per aggiungere il componente aggiuntivo Azure Data Lake all'ambiente.</span><span class="sxs-lookup"><span data-stu-id="c1e98-304">Follow these steps to use LCS to add the Azure Data Lake add-in to the environment.</span></span>

1. <span data-ttu-id="c1e98-305">Accedi a LCS, quindi, sotto il nome dell'ambiente sul lato destro della pagina, seleziona **Dettagli completi**.</span><span class="sxs-lookup"><span data-stu-id="c1e98-305">Sign in to LCS, and then, under the environment name on the right side of the page, select **Full Details**.</span></span>
2. <span data-ttu-id="c1e98-306">Nella sezione **Componenti aggiuntivi per l'ambiente**, selezionare **Installa un nuovo componente aggiuntivo**.</span><span class="sxs-lookup"><span data-stu-id="c1e98-306">In the **Environment add-ins** section, select **Install a new add-in**.</span></span>
3. <span data-ttu-id="c1e98-307">Seleziona il componente aggiunti **Esporta in Data Lake**.</span><span class="sxs-lookup"><span data-stu-id="c1e98-307">Select the **Export to Data Lake** add-in.</span></span>
4. <span data-ttu-id="c1e98-308">Immetti i valori seguenti.</span><span class="sxs-lookup"><span data-stu-id="c1e98-308">Enter the following values.</span></span>

    | <span data-ttu-id="c1e98-309">Valore</span><span class="sxs-lookup"><span data-stu-id="c1e98-309">Value</span></span>                                                              | <span data-ttu-id="c1e98-310">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c1e98-310">Description</span></span> |
    |--------------------------------------------------------------------|-------------|
    | <span data-ttu-id="c1e98-311">ID tenant della sottoscrizione di Azure in cui si trova il Key Vault</span><span class="sxs-lookup"><span data-stu-id="c1e98-311">Tenant ID of the Azure Subscription where the Key Vault is located</span></span> | <span data-ttu-id="c1e98-312">L'ID tenant in cui si trovano l'account di archiviazione, le app e i Key Vault.</span><span class="sxs-lookup"><span data-stu-id="c1e98-312">The tenant ID where the storage account, apps, and key vaults are located.</span></span> <span data-ttu-id="c1e98-313">Per trovare questo valore, apri il [portale di Azure](https://portal.azure.com), vai ad **Azure Active Directory** e copia il valore **ID tenant**.</span><span class="sxs-lookup"><span data-stu-id="c1e98-313">To find this value, open the [Azure portal](https://portal.azure.com), go to **Azure Active Directory**, and copy the **Tenant ID** value.</span></span> |
    | <span data-ttu-id="c1e98-314">Specificare il nome DNS del Key Vault</span><span class="sxs-lookup"><span data-stu-id="c1e98-314">Provide the DNS name of your Key Vault</span></span>                             | <span data-ttu-id="c1e98-315">Il nome DNS del Key Vault, ad esempio `https://customkeyvault.vault.azure.net/`.</span><span class="sxs-lookup"><span data-stu-id="c1e98-315">The DNS name of the key vault, such as `https://customkeyvault.vault.azure.net/`.</span></span> <span data-ttu-id="c1e98-316">Questo valore corrisponde al nome DNS utilizzato nell'archivio entità.</span><span class="sxs-lookup"><span data-stu-id="c1e98-316">(This value matches the DNS name that is used in the entity store.)</span></span> |
    | <span data-ttu-id="c1e98-317">Fornire il segreto contenente il nome dell'account di archiviazione</span><span class="sxs-lookup"><span data-stu-id="c1e98-317">Provide the secret that contains the name of the storage account</span></span>   | <span data-ttu-id="c1e98-318">**storage-account-name**</span><span class="sxs-lookup"><span data-stu-id="c1e98-318">**storage-account-name**</span></span> |
    | <span data-ttu-id="c1e98-319">Nome segreto per l'ID app da utilizzare per accedere al data lake</span><span class="sxs-lookup"><span data-stu-id="c1e98-319">Secret Name for App ID to be used for accessing Data Lake</span></span>          | <span data-ttu-id="c1e98-320">**app-id**</span><span class="sxs-lookup"><span data-stu-id="c1e98-320">**app-id**</span></span> |
    | <span data-ttu-id="c1e98-321">Nome segreto da utilizzare con l'ID app</span><span class="sxs-lookup"><span data-stu-id="c1e98-321">Secret name to be used with App ID</span></span>                                 | <span data-ttu-id="c1e98-322">**app-secret**</span><span class="sxs-lookup"><span data-stu-id="c1e98-322">**app-secret**</span></span> |

5. <span data-ttu-id="c1e98-323">Accetta le condizioni e seleziona **Installa**.</span><span class="sxs-lookup"><span data-stu-id="c1e98-323">Agree to the terms, and select **Install**.</span></span>

<span data-ttu-id="c1e98-324">Il componente aggiuntivo verrà installato in pochi minuti.</span><span class="sxs-lookup"><span data-stu-id="c1e98-324">The add-in will be installed within a few minutes.</span></span>

## <a name="configure-ai-builder"></a><span data-ttu-id="c1e98-325">Configurare AI Builder</span><span class="sxs-lookup"><span data-stu-id="c1e98-325">Configure AI Builder</span></span>

1. <span data-ttu-id="c1e98-326">Accedi a LCS e apri la pagina **Dettagli ambiente**.</span><span class="sxs-lookup"><span data-stu-id="c1e98-326">Sign in to LCS, and open the **Environment details** page.</span></span>
2. <span data-ttu-id="c1e98-327">Scorrere fino alla sezione **Componenti aggiuntivi dell'ambiente**.</span><span class="sxs-lookup"><span data-stu-id="c1e98-327">Scroll to the **Environment add-ins** section.</span></span> <span data-ttu-id="c1e98-328">Dovresti vedere i componenti aggiuntivi già installati in questo ambiente.</span><span class="sxs-lookup"><span data-stu-id="c1e98-328">You should see the add-ins that are already installed in this environment.</span></span> <span data-ttu-id="c1e98-329">Se il componente aggiuntivo **Esporta in Data Lake** non è tra questi, configuralo.</span><span class="sxs-lookup"><span data-stu-id="c1e98-329">If the **Export to Data Lake** add-in isn't among them, configure this add-in.</span></span>
3. <span data-ttu-id="c1e98-330">Seleziona il componente aggiuntivo **Ottieni informazioni dettagliate**.</span><span class="sxs-lookup"><span data-stu-id="c1e98-330">Select the **Get insights** add-in.</span></span>
4. <span data-ttu-id="c1e98-331">Nella pagina dei dettagli del componente aggiuntivo **Ottieni informazioni dettagliate**, immetti i seguenti valori.</span><span class="sxs-lookup"><span data-stu-id="c1e98-331">On the **Get insights** add-in details page, enter the following values.</span></span>

    | <span data-ttu-id="c1e98-332">Valore</span><span class="sxs-lookup"><span data-stu-id="c1e98-332">Value</span></span>                                                    | <span data-ttu-id="c1e98-333">descrizione</span><span class="sxs-lookup"><span data-stu-id="c1e98-333">Description</span></span> |
    |----------------------------------------------------------|-------------|
    | <span data-ttu-id="c1e98-334">URL organizzazione CDS</span><span class="sxs-lookup"><span data-stu-id="c1e98-334">CDS Organization URL</span></span>                                     | <span data-ttu-id="c1e98-335">Il URL dell'organizzazione Dataverse copiato da sopra.</span><span class="sxs-lookup"><span data-stu-id="c1e98-335">The Dataverse organization URL copied from above.</span></span> |
    | <span data-ttu-id="c1e98-336">ID org CDS</span><span class="sxs-lookup"><span data-stu-id="c1e98-336">CDS Org ID</span></span>                                               | <span data-ttu-id="c1e98-337">L'ID dell'organizzazione Dataverse copiato da sopra.</span><span class="sxs-lookup"><span data-stu-id="c1e98-337">The Dataverse organization ID copied from above.</span></span> |
5. <span data-ttu-id="c1e98-338">Abilita **È questo l'ambiente predefinito per il tenant?**.</span><span class="sxs-lookup"><span data-stu-id="c1e98-338">Enable **Is this the default environment for you Tenant**.</span></span>
    
## <a name="configure-the-entity-store"></a><span data-ttu-id="c1e98-339">Configurare l'archivio entità</span><span class="sxs-lookup"><span data-stu-id="c1e98-339">Configure the entity store</span></span>

<span data-ttu-id="c1e98-340">Segui questi passaggi per configurare l'archivio entità nel tuo ambiente Finance.</span><span class="sxs-lookup"><span data-stu-id="c1e98-340">Follow these steps to set up the entity store in your Finance environment.</span></span>

1. <span data-ttu-id="c1e98-341">Vai ad **Amministrazione sistema \> Imposta \> Parametri di sistema \> Connessioni dati**.</span><span class="sxs-lookup"><span data-stu-id="c1e98-341">Go to **System administration \> Setup \> System parameters \> Data connections**.</span></span>
2. <span data-ttu-id="c1e98-342">Imposta i seguenti campi di Key Vault:</span><span class="sxs-lookup"><span data-stu-id="c1e98-342">Set the following key vault fields:</span></span>

    - <span data-ttu-id="c1e98-343">**ID applicazione (client)**: immetti l'ID client dell'applicazione creato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="c1e98-343">**Application (client) ID** – Enter the application client ID that you created earlier.</span></span>
    - <span data-ttu-id="c1e98-344">**Segreto applicazione**: immetti il segreto che hai salvato per l'applicazione che hai creato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="c1e98-344">**Application Secret** – Enter the secret that you saved for the application that you created earlier.</span></span>
    - <span data-ttu-id="c1e98-345">**Nome DNS**: puoi trovare il nome DNS (Domain Name System) nella pagina dei dettagli dell'applicazione per l'applicazione creata in precedenza.</span><span class="sxs-lookup"><span data-stu-id="c1e98-345">**DNS name** – You can find the Domain Name System (DNS) name on the application details page for the application that you created earlier.</span></span>
    - <span data-ttu-id="c1e98-346">**Nome segreto**: immetti **storage-account-connection-string**.</span><span class="sxs-lookup"><span data-stu-id="c1e98-346">**Secret name** – Enter **storage-account-connection-string**.</span></span>
3. <span data-ttu-id="c1e98-347">Abilita **Abilita l'integrazione di Data Lake**.</span><span class="sxs-lookup"><span data-stu-id="c1e98-347">Enable **Enable Data Lake integration**.</span></span>
4. <span data-ttu-id="c1e98-348">Selezionare **Testa Azure Key Vault** e verificare che non ci siano errori.</span><span class="sxs-lookup"><span data-stu-id="c1e98-348">Select **Test Azure Key Vault** and verify there are no errors.</span></span>
5. <span data-ttu-id="c1e98-349">Selezionare **Testa Archiviazione di Azure** e verificare che non ci siano errori.</span><span class="sxs-lookup"><span data-stu-id="c1e98-349">Select **Test Azure storage** and verify there are no errors.</span></span>

## <a name="feedback-and-support"></a><span data-ttu-id="c1e98-350">Feedback e supporto</span><span class="sxs-lookup"><span data-stu-id="c1e98-350">Feedback and support</span></span>

<span data-ttu-id="c1e98-351">Invia un messaggio e-mail a [Informazioni dettagliate sui pagamenti dei clienti (anteprima)](mailto:fiap@microsoft.com) se sei interessato a fornire feedback o hai bisogno di supporto.</span><span class="sxs-lookup"><span data-stu-id="c1e98-351">Please send an email to [Customer payment insights (Preview)](mailto:fiap@microsoft.com) if you are interested in providing feedback or need support.</span></span>

## <a name="privacy-notice"></a><span data-ttu-id="c1e98-352">Informativa sulla privacy</span><span class="sxs-lookup"><span data-stu-id="c1e98-352">Privacy notice</span></span>

<span data-ttu-id="c1e98-353">Le anteprime (1) potrebbero utilizzare meno misure di sicurezza e di privacy rispetto al servizio Dynamics 365 Finance and Operations, (2) non sono incluse nel contratto di servizio di questo servizio, (3) non devono essere utilizzate per elaborare i dati personali o altri dati soggetti a requisiti legati e normativi, e (4) hanno supporto limitato.</span><span class="sxs-lookup"><span data-stu-id="c1e98-353">Previews (1) might use less privacy and fewer security measures than the Dynamics 365 Finance and Operations service, (2) aren't included in the service level agreement (SLA) for this service, (3) should not be used to process personal data or other data that is subject to legal or regulatory compliance requirements, and (4) have limited support.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
