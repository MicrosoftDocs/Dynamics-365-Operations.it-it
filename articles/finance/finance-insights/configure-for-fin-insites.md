---
title: Configurazione per Informazioni finanziarie dettagliate (anteprima)
description: In questo argomento vengono illustrati i passaggi di configurazione che consentiranno al sistema di utilizzare le funzionalità disponibili in Informazioni finanziarie dettagliate.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 11/25/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-07-20
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 38cdeb9110691e594b4b90fc5bc79e369c9f4707
ms.sourcegitcommit: 1cfd6e0c808341b0f5bafbde7d04b0255b27352f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2020
ms.locfileid: "4664092"
---
# <a name="configuration-for-finance-insights-preview"></a><span data-ttu-id="5ea62-103">Configurazione per Informazioni finanziarie dettagliate (anteprima)</span><span class="sxs-lookup"><span data-stu-id="5ea62-103">Configuration for Finance insights (preview)</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="5ea62-104">Informazioni finanziarie dettagliate combina le funzionalità di Microsoft Dynamics 365 Finance con Common Data Service, Azure e AI Builder per fornire potenti strumenti di previsione per la tua organizzazione.</span><span class="sxs-lookup"><span data-stu-id="5ea62-104">Finance insights combines functionality from Microsoft Dynamics 365 Finance with Common Data Service, Azure, and AI Builder to provide powerful forecasting tools for your organization.</span></span> <span data-ttu-id="5ea62-105">In questo argomento vengono illustrati i passaggi di configurazione che consentiranno al sistema di utilizzare le funzionalità disponibili in Informazioni finanziarie dettagliate.</span><span class="sxs-lookup"><span data-stu-id="5ea62-105">This topic explains the configuration steps that will enable your system to use the capabilities that are available in Finance insights.</span></span>

## <a name="deploy-dynamics-365-finance"></a><span data-ttu-id="5ea62-106">Distribuire Dynamics 365 Finance</span><span class="sxs-lookup"><span data-stu-id="5ea62-106">Deploy Dynamics 365 Finance</span></span>

<span data-ttu-id="5ea62-107">Distribuisci l'ambiente seguendo questa procedura.</span><span class="sxs-lookup"><span data-stu-id="5ea62-107">Deploy the environments by following these steps.</span></span>

1. <span data-ttu-id="5ea62-108">In Microsoft Dynamics Lifecycle Services (LCS), crea o aggiorna un ambiente Dynamics 365 Finance.</span><span class="sxs-lookup"><span data-stu-id="5ea62-108">In Microsoft Dynamics Lifecycle Services (LCS), create or update a Dynamics 365 Finance environment.</span></span> <span data-ttu-id="5ea62-109">L'ambiente richiede la versione dell'app 10.0.11/Platform update 35 o successive.</span><span class="sxs-lookup"><span data-stu-id="5ea62-109">The environment requires app version 10.0.11/Platform update 35 or later.</span></span>
2. <span data-ttu-id="5ea62-110">L'ambiente deve essere un ambiente ad alta disponibilità (HA) in Sandbox.</span><span class="sxs-lookup"><span data-stu-id="5ea62-110">The environment must be a high-availability (HA) environment in Sandbox.</span></span> <span data-ttu-id="5ea62-111">(Questo tipo di ambiente è noto anche come ambiente Tier-2). Per altre lteriori informazioni, vedi [Pianificazione ambientale](../../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md).</span><span class="sxs-lookup"><span data-stu-id="5ea62-111">(This type of environment is also known as a Tier-2 environment.) For more information, see [Environment planning](../../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md).</span></span>
3. <span data-ttu-id="5ea62-112">Se utilizzi i dati demo di Contoso, avrai bisogno di dati di esempio aggiuntivi per utilizzare le funzionalità Previsioni di pagamento del cliente, Previsioni di cassa e Previsioni di budget.</span><span class="sxs-lookup"><span data-stu-id="5ea62-112">If you're using Contoso demo data, you will require additional sample data to use the Customer payment predictions, Cash flow forecasts, and Budget forecasts features.</span></span> 

## <a name="configure-common-data-service"></a><span data-ttu-id="5ea62-113">Configura Common Data Service</span><span class="sxs-lookup"><span data-stu-id="5ea62-113">Configure Common Data Service</span></span>

<span data-ttu-id="5ea62-114">Puoi completare i passaggi di configurazione manuale che seguono oppure accelerare il processo di configurazione utilizzando lo script di Windows PowerShell fornito.</span><span class="sxs-lookup"><span data-stu-id="5ea62-114">You can complete the manual configuration steps that follow, or you can speed up the configuration process by using the Windows PowerShell script that is provided.</span></span> <span data-ttu-id="5ea62-115">Al termine dell'esecuzione dello script di PowerShell, verranno forniti i valori da utilizzare per configurare Informazioni finanziarie dettagliate.</span><span class="sxs-lookup"><span data-stu-id="5ea62-115">When the PowerShell script has finished running, it will give you values to use to configure Finance insights.</span></span> 

> [!NOTE]
> <span data-ttu-id="5ea62-116">Apri PowerShell sul tuo PC per eseguire lo script.</span><span class="sxs-lookup"><span data-stu-id="5ea62-116">Open PowerShell on your PC to run the script.</span></span> <span data-ttu-id="5ea62-117">Potrebbe essere necessario PowerShell versione 5.</span><span class="sxs-lookup"><span data-stu-id="5ea62-117">You may need PowerShell version 5.</span></span> <span data-ttu-id="5ea62-118">L'opzione "Prova" dell'interfaccia della riga di comando di Microsoft Azure potrebbe non funzionare.</span><span class="sxs-lookup"><span data-stu-id="5ea62-118">The Microsoft Azure CLI "Try it" option may not work.</span></span>

# <a name="manual-configuration-steps"></a>[<span data-ttu-id="5ea62-119">Passaggi di configurazione manuale</span><span class="sxs-lookup"><span data-stu-id="5ea62-119">Manual configuration steps</span></span>](#tab/configuration-steps)

1. <span data-ttu-id="5ea62-120">Apri l'[interfaccia di amministrazione di Power Platform](https://admin.powerplatform.microsoft.com/) e segui questi passaggi per creare un nuovo ambiente Common Data Service nello stesso tenant di Active Directory:</span><span class="sxs-lookup"><span data-stu-id="5ea62-120">Open the [Power Platform admin center](https://admin.powerplatform.microsoft.com/), and follow these steps to create a new Common Data Service environment in the same Active Directory tenant:</span></span>

    1. <span data-ttu-id="5ea62-121">Apri la pagina **Ambienti**.</span><span class="sxs-lookup"><span data-stu-id="5ea62-121">Open the **Environments** page.</span></span>

        <span data-ttu-id="5ea62-122">[![Pagina Ambienti](./media/power-pltfrm-admin-center.png)](./media/power-pltfrm-admin-center.png)</span><span class="sxs-lookup"><span data-stu-id="5ea62-122">[![Environments page](./media/power-pltfrm-admin-center.png)](./media/power-pltfrm-admin-center.png)</span></span>

    2. <span data-ttu-id="5ea62-123">Seleziona **Nuovo ambiente**.</span><span class="sxs-lookup"><span data-stu-id="5ea62-123">Select **New environment**.</span></span>
    3. <span data-ttu-id="5ea62-124">Nel campo **Tipo** seleziona **Sandbox**.</span><span class="sxs-lookup"><span data-stu-id="5ea62-124">In the **Type** field, select **Sandbox**.</span></span>
    4. <span data-ttu-id="5ea62-125">Imposta l'opzione **Crea database** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="5ea62-125">Set the **Create Database** option to **Yes**.</span></span>
    5. <span data-ttu-id="5ea62-126">Selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="5ea62-126">Select **Next**.</span></span>
    6. <span data-ttu-id="5ea62-127">Seleziona la lingua e la valuta per la tua organizzazione.</span><span class="sxs-lookup"><span data-stu-id="5ea62-127">Select the language and currency for your organization.</span></span>
    7. <span data-ttu-id="5ea62-128">Accetta i valori predefiniti per gli altri campi.</span><span class="sxs-lookup"><span data-stu-id="5ea62-128">Accept the default values for the other fields.</span></span>
    8. <span data-ttu-id="5ea62-129">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="5ea62-129">Select **Save**.</span></span>
    9. <span data-ttu-id="5ea62-130">Aggiorna la pagina **Ambienti**.</span><span class="sxs-lookup"><span data-stu-id="5ea62-130">Refresh the **Environments** page.</span></span>
    10. <span data-ttu-id="5ea62-131">Attendi fino a quando il valore del campo **Stato** viene aggiornato su **Pronto**.</span><span class="sxs-lookup"><span data-stu-id="5ea62-131">Wait until the value of the **State** field is updated to **Ready**.</span></span>
    11. <span data-ttu-id="5ea62-132">Prendi nota dell'ID organizzazione di Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="5ea62-132">Make a note of the Common Data Service organization ID.</span></span>
    12. <span data-ttu-id="5ea62-133">Seleziona l'ambiente, quindi selezionare **Impostazioni**.</span><span class="sxs-lookup"><span data-stu-id="5ea62-133">Select the environment, and then select **Settings**.</span></span>
    13. <span data-ttu-id="5ea62-134">Seleziona **Risorse \> Tutte le impostazioni legacy**.</span><span class="sxs-lookup"><span data-stu-id="5ea62-134">Select **Resources \> All Legacy Settings**.</span></span>
    14. <span data-ttu-id="5ea62-135">Nella barra di spostamento in alto, seleziona **Impostazioni** e quindi seleziona **Personalizzazioni**.</span><span class="sxs-lookup"><span data-stu-id="5ea62-135">On the top navigation bar, select **Settings**, and then select **Customizations**.</span></span>
    15. <span data-ttu-id="5ea62-136">Seleziona **Risorse per sviluppatori**.</span><span class="sxs-lookup"><span data-stu-id="5ea62-136">Select **Developer Resources**.</span></span>
    16. <span data-ttu-id="5ea62-137">Imposta il campo **ID informazioni di riferimento istanza** sull'ID organizzazione di Common Data Service di cui hai preso nota in precedenza.</span><span class="sxs-lookup"><span data-stu-id="5ea62-137">Set the **Instance Reference Information ID** field to the Common Data Service organization ID value that you made a note of earlier.</span></span>
    17. <span data-ttu-id="5ea62-138">Nella barra degli indirizzi del browser, prendi nota dell'URL dell'organizzazione Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="5ea62-138">In the browser's address bar, make a note of the URL for the Common Data Service organization.</span></span> <span data-ttu-id="5ea62-139">Ad esempio, l'URL potrebbe essere `https://org42b2b3d3.crm.dynamics.com`.</span><span class="sxs-lookup"><span data-stu-id="5ea62-139">For example, the URL might be `https://org42b2b3d3.crm.dynamics.com`.</span></span>

2. <span data-ttu-id="5ea62-140">Se prevedi di utilizzare la funzionalità Previsioni di cassa o Previsioni di budget, segui questi passaggi per aggiornare il limite di annotazioni per la tua organizzazione ad almeno 50 megabyte (MB):</span><span class="sxs-lookup"><span data-stu-id="5ea62-140">If you plan to use the Cash flow forecasts or Budget forecasts feature, follow these steps to update the annotation limit for your organization to at least 50 megabytes (MB):</span></span>

    1. <span data-ttu-id="5ea62-141">Apri il [portale di Power Apps](https://make.powerapps.com).</span><span class="sxs-lookup"><span data-stu-id="5ea62-141">Open the [Power Apps portal](https://make.powerapps.com).</span></span>
    2. <span data-ttu-id="5ea62-142">Seleziona l'ambiente appena creato, quindi seleziona **Impostazioni avanzate**.</span><span class="sxs-lookup"><span data-stu-id="5ea62-142">Select the environment that you just created, and then select **Advanced settings**.</span></span>
    3. <span data-ttu-id="5ea62-143">Seleziona **Impostazioni \> Configurazione e-mail**.</span><span class="sxs-lookup"><span data-stu-id="5ea62-143">Select **Settings \> Email Configuration**.</span></span>
    4. <span data-ttu-id="5ea62-144">Modifica il valore del campo **Dimensioni massime file** su **51.200**.</span><span class="sxs-lookup"><span data-stu-id="5ea62-144">Change the value of the **Maximum file size** field to **51,200**.</span></span> <span data-ttu-id="5ea62-145">Il valore viene espresso in kilobytes \[KB\].</span><span class="sxs-lookup"><span data-stu-id="5ea62-145">(The value is expressed in kilobytes \[KB\].)</span></span>
    5. <span data-ttu-id="5ea62-146">Seleziona **OK** per salvare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="5ea62-146">Select **OK** to save your changes.</span></span>

# <a name="windows-powershell-configuration-script"></a>[<span data-ttu-id="5ea62-147">Script di configurazione di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="5ea62-147">Windows PowerShell configuration script</span></span>](#tab/powershell-configuration-script)

```azurecli-interactive
Write-Output 'The following modules need to be present for execution of this script:'
Write-Output '  Microsoft.PowerApps.Administration.PowerShell'
Write-Output '  Microsoft.PowerApps.PowerShell'
Write-Output '  Microsoft.Xrm.Tooling.CrmConnector.PowerShell'

try {
    $moduleConsent = Read-Host 'Is it ok to install or update these modules as needed? (yes/no)'
    if ($moduleConsent -ne 'yes' -and $moduleConsent -ne 'y') {
        Write-Warning 'User declined to install required modules.'
        return
    }

    $module = 'Microsoft.PowerApps.Administration.PowerShell'
    if (-not (Get-InstalledModule -Name $module -MinimumVersion '2.0.61' -ErrorAction SilentlyContinue)) {
        Install-Module -Name $module -MinimumVersion '2.0.61' -Force
        Write-Output ('Installed {0} module.' -f $module)
    }
    else {
        Write-Output ('{0} module found.' -f $module)
    }

    $module = 'Microsoft.PowerApps.PowerShell'
    if (-not (Get-InstalledModule -Name $module -MinimumVersion '1.0.9' -ErrorAction SilentlyContinue)) {
        Install-Module -Name $module -MinimumVersion '1.0.9' -AllowClobber -Force
        Write-Output ('Installed {0} module.' -f $module)
    }
    else {
        Write-Output ('{0} module found.' -f $module)
    }

    $module = 'Microsoft.Xrm.Tooling.CrmConnector.PowerShell'
    if (-not (Get-InstalledModule -Name $module -MinimumVersion '3.3.0.892' -ErrorAction SilentlyContinue)) {
        Install-Module -Name $module -MinimumVersion '3.3.0.892' -Force
        Write-Output ('Installed {0} module.' -f $module)
    }
    else {
        Write-Output ('{0} module found.' -f $module)
    }

    Write-Output '================================================================================='

    $useMfa = $false
    $useMfaPrompt = Read-Host "Does your organization require the use of multi-factor authentication? (yes/no)"
    if ($useMfaPrompt -eq 'yes' -or $useMfaPrompt -eq 'y') {
        $useMfa = $true
    }
    if(-not $useMfa) {
        $credential = Get-Credential -Message 'Power Apps Credential'
    }

    $orgFriendlyName = Read-Host "Enter the name of the CDS Organization to use or create: (blank for 'FinanceInsightsOrg')"
    if ($orgFriendlyName.Trim() -eq '') {
        $orgFriendlyName = 'FinanceInsightsOrg'
    }

    $isDefaultOrgPrompt = Read-Host ("Is '" + $orgFriendlyName + "' the default organization for your tenant? (yes/no)")
    if ($isDefaultOrgPrompt -eq 'yes' -or $isDefaultOrgPrompt -eq 'y') {
        $isDefaultOrg = $true
    }

    if ($credential) {
        Add-PowerAppsAccount -Username $credential.UserName -Password $credential.Password
    }
    else {
        Add-PowerAppsAccount
    }

    if ($isDefaultOrg) {
        $orgMatch = ('(default)')
        $environment = (Get-AdminPowerAppEnvironment | Where-Object { $_.IsDefault -eq $true })
    }
    else {
        $orgMatch = ('{0} (*)' -f $orgFriendlyName)
        $environment = (Get-AdminPowerAppEnvironment | Where-Object { ($_.IsDefault -eq $false -and ($_.DisplayName -eq $orgFriendlyName -or $_.DisplayName -like $orgMatch)) })
    }

    $getCrmOrgParams = @{ 'OnlineType' = 'Office365' }
    if ($credential) {
        $getCrmOrgParams.Credential = $credential
    }

    if ($null -eq $environment) {
        Write-Output '================================================================================='
        Write-Output 'PowerApps environment not found. A new one will be provisioned.'

        $invalid = 'invalid'

        $location = $invalid
        $cdsLocations = (Get-AdminPowerAppEnvironmentLocations | Select-Object LocationName).LocationName
        while (-not ($location -in $cdsLocations)) {
            $location = (Read-Host -Prompt "Enter the location in which to create the new PowerApps environment: ('help' to see values)")
            if ($location -eq 'help') {
                $cdsLocations
            }
        }

        $currency = $invalid
        $cdsCurrencies = (Get-AdminPowerAppCdsDatabaseCurrencies -Location $location | Select-Object CurrencyName).CurrencyName
        while ($currency -ne '' -and -not ($currency -in $cdsCurrencies)) {
            $currency = (Read-Host -Prompt "Enter the currency to use for the new PowerApps environment: ('help' to see values, blank for default)")
            if ($currency -eq 'help') {
                $cdsCurrencies
            }
        }

        $language = $invalid
        $cdsLanguages = (Get-AdminPowerAppCdsDatabaseLanguages -Location $location | Select-Object LanguageName, LanguageDisplayName)
        while ($language -ne '' -and -not ($language -in $cdsLanguages.LanguageName)) {
            $language = (Read-Host -Prompt "Enter the language name to use for the new PowerApps environment: ('help' to see values, blank for default)")
            if ($language -eq 'help') {
                $cdsLanguages | Format-Table -Property LanguageName, LanguageDisplayName
            }
        }

        Write-Output 'Provisioning PowerApps environment. This may take several minutes.'

        $sleep = 15

        $envParams = @{ 'DisplayName' = $orgFriendlyName; 'EnvironmentSku' = 'Sandbox'; 'ProvisionDatabase' = $true; 'Location' = $location; 'WaitUntilFinished' = $true }
        if ($language.Trim() -ne '') {
            $envParams.LanguageName = $language
        }
        if ($currency.Trim() -ne '') {
            $envParams.CurrencyName = $currency
        }
        $newEnvResult = New-AdminPowerAppEnvironment @envParams
        if (($null -eq $newEnvResult) -or ($newEnvResult.CommonDataServiceDatabaseProvisioningState -ne 'Succeeded')) {
            Write-Warning 'Failed to create to PowerApps environment'
            if ($null -ne $newEnvResult) {
                $newEnvResult
            }
        }
        else {
            $environment = $null
            $retryCount = 0
            while (($null -eq $environment) -and ($retryCount -lt 5)) {
                Start-Sleep -Seconds $sleep
                $environment = (Get-AdminPowerAppEnvironment | Where-Object { ($_.DisplayName -like $orgMatch) })
            }
            Write-Output ("Provisioned PowerApps environment with name: '" + $environment.DisplayName + "'")
        }

        Write-Output 'Waiting for CDS organization provisioning. This may take several minutes.'
        if (-not $credential) {
            $sleep = 120
            Write-Output 'You may be prompted for credentials multiple times while checking the status of the provisioning.'
        }

        while ($null -eq $crmOrg) {
            Start-Sleep -Seconds $sleep
            $crmOrg = (Get-CrmOrganizations @getCrmOrgParams) | Where-Object { $_.FriendlyName -eq $orgFriendlyName }
        }
    }
    else {
        $crmOrgs = Get-CrmOrganizations @getCrmOrgParams
        if ($UseDefaultOrganization -eq $true) {
            $crmOrg = $crmOrgs | Where-Object { $_.FriendlyName -match $orgMatch }
        }
        else {
            $crmOrg = $crmOrgs | Where-Object { $_.FriendlyName -eq $orgFriendlyName }
        }
    }

    Write-Output '================================================================================='
    Write-Output 'Values for PowerAI LCS Add-In:'
    Write-Output ("  CDS organization url:             " + $crmOrg.WebApplicationUrl)
    Write-Output ("  CDS organization ID:              " + $crmOrg.OrganizationId)
}
catch {
    Write-Error $_.Exception.Message
    Write-Warning $_.Exception.StackTrace
    $inner = $_.Exception.InnerException
    while ($null -ne $inner) {
        Write-Output 'Inner Exception:'
        Write-Error $_.Exception.Message
        Write-Warning $_.Exception.StackTrace
        $inner = $inner.InnerException
    }
}
```
---

## <a name="configure-the-azure-setup"></a><span data-ttu-id="5ea62-148">Configurare l'impostazione di Azure</span><span class="sxs-lookup"><span data-stu-id="5ea62-148">Configure the Azure setup</span></span>

### <a name="enter-the-common-data-service-directory-id-and-the-users-azure-ad-object-id"></a><span data-ttu-id="5ea62-149">Immettere l'ID directory di Common Data Service e l'iD oggetto Azure AD dell'utente</span><span class="sxs-lookup"><span data-stu-id="5ea62-149">Enter the Common Data Service directory ID and the user's Azure AD object ID</span></span>

1. <span data-ttu-id="5ea62-150">Immetti l'ID directory di Common Data Service :</span><span class="sxs-lookup"><span data-stu-id="5ea62-150">Enter the Common Data Service directory ID:</span></span>

    1. <span data-ttu-id="5ea62-151">Apri il [portale di Azure](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="5ea62-151">Open the [Azure portal](https://portal.azure.com).</span></span>
    2. <span data-ttu-id="5ea62-152">Accedi utilizzando l'ID utente utilizzato per creare l'ambiente Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="5ea62-152">Sign in by using the user ID that was used to create the Common Data Service environment.</span></span>
    3. <span data-ttu-id="5ea62-153">Accedere a **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="5ea62-153">Go to **Azure Active Directory**.</span></span>
    4. <span data-ttu-id="5ea62-154">Copia il valore di **ID tenant**.</span><span class="sxs-lookup"><span data-stu-id="5ea62-154">Copy the **Tenant ID** value.</span></span>

2. <span data-ttu-id="5ea62-155">Immettere l'ID oggetto Azure Active Directory (Azure AD) dell'utente:</span><span class="sxs-lookup"><span data-stu-id="5ea62-155">Enter the user's Azure Active Directory (Azure AD) object ID:</span></span>

    1. <span data-ttu-id="5ea62-156">Nel [portale di Azure](https://portal.azure.com), vai a **Utenti** e cerca l'utente tramite indirizzo email.</span><span class="sxs-lookup"><span data-stu-id="5ea62-156">In the [Azure portal](https://portal.azure.com), go to **Users**, and search for the user by email address.</span></span>
    2. <span data-ttu-id="5ea62-157">Seleziona il nome dell'utente.</span><span class="sxs-lookup"><span data-stu-id="5ea62-157">Select the user's name.</span></span>
    3. <span data-ttu-id="5ea62-158">Copia il valore di **ID oggetto**.</span><span class="sxs-lookup"><span data-stu-id="5ea62-158">Copy the **Object ID** value.</span></span>

### <a name="use-azure-cloud-shell-to-set-up-finance-insights-data-lake-resources"></a><span data-ttu-id="5ea62-159">Utilizzare Azure Cloud Shell per configurare le risorse Data Lake di Informazioni finanziarie dettagliate</span><span class="sxs-lookup"><span data-stu-id="5ea62-159">Use Azure Cloud Shell to set up Finance insights Data Lake resources</span></span>

# <a name="use-a-windows-powershell-script"></a>[<span data-ttu-id="5ea62-160">Utilizzare uno script di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="5ea62-160">Use a Windows PowerShell script</span></span>](#tab/use-a-powershell-script)

<span data-ttu-id="5ea62-161">È stato fornito uno script di Windows PowerShell, in modo da poter configurare facilmente le risorse di Azure descritte in [Configurare l'esportazione in Azure Data Lake](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/data-entities/configure-export-data-lake).</span><span class="sxs-lookup"><span data-stu-id="5ea62-161">A Windows PowerShell script has been provided, so that you can easily set up the Azure resources that are described in [Configure export to Azure Data Lake](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/data-entities/configure-export-data-lake).</span></span> <span data-ttu-id="5ea62-162">Se preferisci eseguire la configurazione manuale, salta questa procedura e continua con la procedura della sezione [Configurazione manuale](#manual-setup).</span><span class="sxs-lookup"><span data-stu-id="5ea62-162">If you prefer to do manual setup, skip this procedure, and continue with the procedure in the [Manual setup](#manual-setup) section.</span></span>

> [!NOTE]
> <span data-ttu-id="5ea62-163">Segui i passaggi seguenti per eseguire lo script di PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5ea62-163">Follow the steps below to run the PowerShell script.</span></span> <span data-ttu-id="5ea62-164">L'opzione "Provalo" dell'interfaccia della riga di comando di Azure o l'esecuzione dello script sul PC potrebbe non funzionare.</span><span class="sxs-lookup"><span data-stu-id="5ea62-164">The Azure CLI "Try it" option, or running the script on your PC may not work.</span></span>

<span data-ttu-id="5ea62-165">Attieniti alla seguente procedura per configurare Azure utilizzando lo script di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5ea62-165">Follow these steps to configure Azure by using the Windows PowerShell script.</span></span> <span data-ttu-id="5ea62-166">Devi disporre dei diritti per creare un gruppo di risorse di Azure, risorse di Azure e un'applicazione Azure AD.</span><span class="sxs-lookup"><span data-stu-id="5ea62-166">You must have rights to create an Azure resource group, Azure resources, and an Azure AD application.</span></span> <span data-ttu-id="5ea62-167">Per informazioni sulle autorizzazioni obbligatorie, vedi [Controllare le autorizzazioni di Azure AD](https://docs.microsoft.com/azure/active-directory/develop/howto-create-service-principal-portal#permissions-required-for-registering-an-app).</span><span class="sxs-lookup"><span data-stu-id="5ea62-167">For information about the required permissions, see [Check Azure AD permissions](https://docs.microsoft.com/azure/active-directory/develop/howto-create-service-principal-portal#permissions-required-for-registering-an-app).</span></span>

1. <span data-ttu-id="5ea62-168">Nel [portale di Azure](https://portal.azure.com), vai alla sottoscrizione di Azure di destinazione.</span><span class="sxs-lookup"><span data-stu-id="5ea62-168">In the [Azure portal](https://portal.azure.com), go to your target Azure subscription.</span></span> <span data-ttu-id="5ea62-169">Seleziona il pulsante **Cloud Shell** a destra del campo **Cerca**.</span><span class="sxs-lookup"><span data-stu-id="5ea62-169">Select the **Cloud Shell** button to the right of the **Search** field.</span></span>
2. <span data-ttu-id="5ea62-170">Seleziona **PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="5ea62-170">Select **PowerShell**.</span></span>
3. <span data-ttu-id="5ea62-171">Crea lo spazio di archiviazione, se ti viene chiesto di farlo.</span><span class="sxs-lookup"><span data-stu-id="5ea62-171">Create storage, if you're prompted to do so.</span></span> <span data-ttu-id="5ea62-172">Quindi carica lo script di Windows PowerShell nella sessione.</span><span class="sxs-lookup"><span data-stu-id="5ea62-172">Then upload the Windows PowerShell script to the session.</span></span>
4. <span data-ttu-id="5ea62-173">Esegui lo script.</span><span class="sxs-lookup"><span data-stu-id="5ea62-173">Run the script.</span></span>
5. <span data-ttu-id="5ea62-174">Segui le istruzioni per eseguire lo script.</span><span class="sxs-lookup"><span data-stu-id="5ea62-174">Follow the prompts to run the script.</span></span>
6. <span data-ttu-id="5ea62-175">Utilizza le informazioni dall'output dello script per installare il componente aggiuntivo **Esporta in Data Lake** in LCS.</span><span class="sxs-lookup"><span data-stu-id="5ea62-175">Use the information from the script output to install the **Export to Data Lake** add-in in LCS.</span></span>
7. <span data-ttu-id="5ea62-176">Utilizza le informazioni dall'output dello script per abilitare l'archivio entità nella pagina **Connessioni dati** in Finanza (**Amministrazione di sistema \> Parametri di sistema \> Connessioni dati**).</span><span class="sxs-lookup"><span data-stu-id="5ea62-176">Use the information from the script output to enable the entity store on the **Data connections** page in Finance (**System administration \> System parameters \> Data connections**).</span></span>

### <a name="manual-setup"></a><span data-ttu-id="5ea62-177">Configurazione manuale</span><span class="sxs-lookup"><span data-stu-id="5ea62-177">Manual setup</span></span>

#### <a name="add-applications-to-the-azure-ad-tenant"></a><span data-ttu-id="5ea62-178">Aggiungere applicazioni al tenant Azure AD</span><span class="sxs-lookup"><span data-stu-id="5ea62-178">Add applications to the Azure AD tenant</span></span>

1. <span data-ttu-id="5ea62-179">Nel [portale di Azure](https://portal.azure.com), passa a **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="5ea62-179">In the [Azure portal](https://portal.azure.com), go to **Azure Active Directory**.</span></span>
2. <span data-ttu-id="5ea62-180">Seleziona **Gestisci \> Applicazioni aziendali**.</span><span class="sxs-lookup"><span data-stu-id="5ea62-180">Select **Manage \> Enterprise applications**.</span></span>
3. <span data-ttu-id="5ea62-181">Cerca le seguenti applicazioni per ID app.</span><span class="sxs-lookup"><span data-stu-id="5ea62-181">Search for the following applications by app ID.</span></span>

    | <span data-ttu-id="5ea62-182">Domanda di lavoro</span><span class="sxs-lookup"><span data-stu-id="5ea62-182">Application</span></span>                              | <span data-ttu-id="5ea62-183">ID app</span><span class="sxs-lookup"><span data-stu-id="5ea62-183">App ID</span></span>                               |
    |------------------------------------------|--------------------------------------|
    | <span data-ttu-id="5ea62-184">Microservizi ERP Microsoft Dynamics</span><span class="sxs-lookup"><span data-stu-id="5ea62-184">Microsoft Dynamics ERP Microservices</span></span>     | <span data-ttu-id="5ea62-185">0cdb527f-a8d1-4bf8-9436-b352c68682b2</span><span class="sxs-lookup"><span data-stu-id="5ea62-185">0cdb527f-a8d1-4bf8-9436-b352c68682b2</span></span> |
    | <span data-ttu-id="5ea62-186">CDS microservizi ERP Microsoft Dynamics</span><span class="sxs-lookup"><span data-stu-id="5ea62-186">Microsoft Dynamics ERP Microservices CDS</span></span> | <span data-ttu-id="5ea62-187">703e2651-d3fc-48f5-942c-74274233dba8</span><span class="sxs-lookup"><span data-stu-id="5ea62-187">703e2651-d3fc-48f5-942c-74274233dba8</span></span> |
    | <span data-ttu-id="5ea62-188">Servizio di autorizzazione di AI Builder</span><span class="sxs-lookup"><span data-stu-id="5ea62-188">AI Builder Authorization Service</span></span>         | <span data-ttu-id="5ea62-189">ad40333e-9910-4b61-b281-e3aeeb8c3ef3</span><span class="sxs-lookup"><span data-stu-id="5ea62-189">ad40333e-9910-4b61-b281-e3aeeb8c3ef3</span></span> |

<span data-ttu-id="5ea62-190">Se non riesci a trovare nessuna delle applicazioni precedenti, prova i seguenti passaggi.</span><span class="sxs-lookup"><span data-stu-id="5ea62-190">If you can't find any of the preceding applications, try the following steps.</span></span>

1. <span data-ttu-id="5ea62-191">Sul tuo computer locale, seleziona il menu **Start** e cerca **powershell**.</span><span class="sxs-lookup"><span data-stu-id="5ea62-191">On your local machine, select the **Start** menu, and search for **powershell**.</span></span>
2. <span data-ttu-id="5ea62-192">Seleziona e tieni premuto (o fai clic con il pulsante destro del mouse su) **Windows PowerShell** e quindi seleziona **Esegui come amministratore**.</span><span class="sxs-lookup"><span data-stu-id="5ea62-192">Select and hold (or right-click) **Windows PowerShell**, and then select **Run as administrator**.</span></span>
3. <span data-ttu-id="5ea62-193">Esegui il comando seguente per installare il modulo **AzureAD**.</span><span class="sxs-lookup"><span data-stu-id="5ea62-193">Run the following command to install the **AzureAD** module.</span></span>

    `Install-Module -Name AzureAD`

4. <span data-ttu-id="5ea62-194">Se è necessario un provider NuGet per continuare, seleziona **Y** per installarlo.</span><span class="sxs-lookup"><span data-stu-id="5ea62-194">If a NuGet provider is required to continue, select **Y** to install it.</span></span>
5. <span data-ttu-id="5ea62-195">Se viene visualizzato il messaggio "Repository non attendibile", seleziona **Y** per continuare.</span><span class="sxs-lookup"><span data-stu-id="5ea62-195">If an "Untrusted repository" message appears, select **Y** to continue.</span></span>
6. <span data-ttu-id="5ea62-196">Per ciascuna applicazione che deve essere aggiunta, esegui i seguenti comandi per aggiungere l'applicazione ad Azure AD.</span><span class="sxs-lookup"><span data-stu-id="5ea62-196">For each application that must be added, run the following commands to add the application to Azure AD.</span></span> <span data-ttu-id="5ea62-197">Quando ti viene richiesto, accedi come amministratore Azure AD.</span><span class="sxs-lookup"><span data-stu-id="5ea62-197">When you're prompted, sign in as the Azure AD administrator.</span></span>

    `Connect-AzureAD`

    `New-AzureADServicePrincipal –AppId <AppId>`

#### <a name="create-azure-resources"></a><span data-ttu-id="5ea62-198">Creare risorse Azure</span><span class="sxs-lookup"><span data-stu-id="5ea62-198">Create Azure resources</span></span>

> [!NOTE]
> <span data-ttu-id="5ea62-199">Assicurati di creare le seguenti risorse nella stessa istanza di Azure AD come l'ambiente Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="5ea62-199">Make sure that you create the following resources in the same Azure AD instance as the Common Data Service environment.</span></span> <span data-ttu-id="5ea62-200">Non puoi utilizzare risorse da un'altra istanza di Azure AD.</span><span class="sxs-lookup"><span data-stu-id="5ea62-200">You can't use resources from a different Azure AD instance.</span></span>

1. <span data-ttu-id="5ea62-201">Creare un nuovo account di archiviazione:</span><span class="sxs-lookup"><span data-stu-id="5ea62-201">Create a new storage account:</span></span>

    1. <span data-ttu-id="5ea62-202">Nel [portale di Azure](https://portal.azure.com), crea un account di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="5ea62-202">In the [Azure portal](https://portal.azure.com), create a storage account.</span></span>
    2. <span data-ttu-id="5ea62-203">Nella finestra di dialogo **Crea account di archiviazione**, imposta i seguenti campi:</span><span class="sxs-lookup"><span data-stu-id="5ea62-203">In the **Create storage account** dialog box, set the following fields:</span></span>

        - <span data-ttu-id="5ea62-204">**Posizione**: seleziona il data center in cui si trova il tuo ambiente.</span><span class="sxs-lookup"><span data-stu-id="5ea62-204">**Location** – Select the data center where your environment is located.</span></span>
        - <span data-ttu-id="5ea62-205">**Prestazioni**: è compatibile selezionare **Standard**.</span><span class="sxs-lookup"><span data-stu-id="5ea62-205">**Performance** – We recommend that you select **Standard**.</span></span>
        - <span data-ttu-id="5ea62-206">**Tipo di account**: devi selezionare **StorageV2**.</span><span class="sxs-lookup"><span data-stu-id="5ea62-206">**Account kind** – You must select **StorageV2**.</span></span>

    3. <span data-ttu-id="5ea62-207">Nella finestra di dialogo **Opzioni avanzate**, per l'opzione **Data Lake Storage Gen2**, seleziona **Abilita** nella funzionalità **Spazi dei nomi gerarchici**.</span><span class="sxs-lookup"><span data-stu-id="5ea62-207">In the **Advanced options** dialog box, for the **Data Lake storage Gen2** option, select **Enable** under the **Hierarchical namespaces** feature.</span></span> <span data-ttu-id="5ea62-208">Se disabiliti questa funzionalità, non puoi utilizzare i dati che le app Finance and Operations scrivono utilizzando servizi come i flussi di dati di Power BI.</span><span class="sxs-lookup"><span data-stu-id="5ea62-208">If you disable this feature, you can't consume data that Finance and Operations apps write by using services such as Power BI data flows.</span></span>
    4. <span data-ttu-id="5ea62-209">Seleziona **Rivedi e crea**.</span><span class="sxs-lookup"><span data-stu-id="5ea62-209">Select **Review and create**.</span></span> <span data-ttu-id="5ea62-210">Al termine della distribuzione, la nuova risorsa verrà visualizzata nel portale di Azure.</span><span class="sxs-lookup"><span data-stu-id="5ea62-210">When the deployment is completed, the new resource will be shown in the Azure portal.</span></span>
    5. <span data-ttu-id="5ea62-211">Vai all'account di archiviazione che hai creato.</span><span class="sxs-lookup"><span data-stu-id="5ea62-211">Go to the storage account that you created.</span></span>
    6. <span data-ttu-id="5ea62-212">Nel menu a sinistra, seleziona **Chiavi di accesso**.</span><span class="sxs-lookup"><span data-stu-id="5ea62-212">On the left menu, select **Access keys**.</span></span>
    7. <span data-ttu-id="5ea62-213">Copia e salva la stringa di connessione per entrambe **Chiave 1** o **Chiave 2**.</span><span class="sxs-lookup"><span data-stu-id="5ea62-213">Copy and save the connection string for either **Key1** or **Key2**.</span></span>
    8. <span data-ttu-id="5ea62-214">Copia e salva il nome dell'account di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="5ea62-214">Copy and save the storage account name.</span></span>

2. <span data-ttu-id="5ea62-215">Crea un nuovo Key Vault:</span><span class="sxs-lookup"><span data-stu-id="5ea62-215">Create a new key vault:</span></span>

    1. <span data-ttu-id="5ea62-216">Nel [portale di Azure](https://portal.azure.com), crea un Key Vault.</span><span class="sxs-lookup"><span data-stu-id="5ea62-216">In the [Azure portal](https://portal.azure.com), create a key vault.</span></span>
    2. <span data-ttu-id="5ea62-217">Nella finestra di dialogo **Crea Key Vault**, nel campo **Posizione**, seleziona il data center in cui si trova il tuo ambiente.</span><span class="sxs-lookup"><span data-stu-id="5ea62-217">In the **Create key vault** dialog box, in the **Location** field, select the data center where your environment is located.</span></span>
    3. <span data-ttu-id="5ea62-218">Dopo aver creato il Key Vault, selezionalo nell'elenco, quindi seleziona **Segreti**.</span><span class="sxs-lookup"><span data-stu-id="5ea62-218">After key vault is created, select it in the list, and then select **Secrets**.</span></span>
    4. <span data-ttu-id="5ea62-219">Seleziona **Genera/Importa**.</span><span class="sxs-lookup"><span data-stu-id="5ea62-219">Select **Generate/Import**.</span></span>
    5. <span data-ttu-id="5ea62-220">Nella finestra di dialogo **Crea un segreto**, nel campo **Opzioni di caricamento**, seleziona **Manuale**.</span><span class="sxs-lookup"><span data-stu-id="5ea62-220">In the **Create a secret** dialog box, in the **Upload options** field, select **Manual**.</span></span>
    6. <span data-ttu-id="5ea62-221">Immetti un nome per il segreto.</span><span class="sxs-lookup"><span data-stu-id="5ea62-221">Enter a name for the secret.</span></span> <span data-ttu-id="5ea62-222">Prendi nota del nome, perché dovrai specificarlo in seguito.</span><span class="sxs-lookup"><span data-stu-id="5ea62-222">Make a note of the name, because you will have to provide it later.</span></span>
    7. <span data-ttu-id="5ea62-223">Nel campo **Valore** immetti la stringa di connessione ottenuta dall'account di archiviazione nella procedura precedente.</span><span class="sxs-lookup"><span data-stu-id="5ea62-223">In the **Value** field, enter the connection string that you obtained from the storage account in the previous procedure.</span></span>
    8. <span data-ttu-id="5ea62-224">Seleziona **Abilitato** e quindi **Crea**.</span><span class="sxs-lookup"><span data-stu-id="5ea62-224">Select **Enabled**, and then select **Create**.</span></span> <span data-ttu-id="5ea62-225">Il segreto viene creato e aggiunto al Key Vault.</span><span class="sxs-lookup"><span data-stu-id="5ea62-225">The secret is created and added to Key Vault.</span></span>
    9. <span data-ttu-id="5ea62-226">Vai a **Panoramica del Key Vault** e prendi nota del nome DNS.</span><span class="sxs-lookup"><span data-stu-id="5ea62-226">Go to the **Key Vault Overview**, and make a note of the DNS name.</span></span>

3. <span data-ttu-id="5ea62-227">Crea e registra un'applicazione Azure AD:</span><span class="sxs-lookup"><span data-stu-id="5ea62-227">Create and register an Azure AD application:</span></span>

    1. <span data-ttu-id="5ea62-228">Nel [portale di Azure](https://portal.azure.com), passa ad **Azure Active Directory**, quindi seleziona **Registrazioni app**.</span><span class="sxs-lookup"><span data-stu-id="5ea62-228">In the [Azure portal](https://portal.azure.com), go to **Azure Active Directory**, and then select **App registrations**.</span></span>
    2. <span data-ttu-id="5ea62-229">Seleziona **Nuova registrazione dell'applicazione** e imposta i seguenti campi:</span><span class="sxs-lookup"><span data-stu-id="5ea62-229">Select **New application registration**, and set the following fields:</span></span>

        - <span data-ttu-id="5ea62-230">**Nome**: immetti il nome dell'app.</span><span class="sxs-lookup"><span data-stu-id="5ea62-230">**Name** – Enter the name of the app.</span></span>
        - <span data-ttu-id="5ea62-231">**Tipo di applicazione**: seleziona **API Web**.</span><span class="sxs-lookup"><span data-stu-id="5ea62-231">**Application type** – Select **Web API**.</span></span>
        - <span data-ttu-id="5ea62-232">**Configurazione URI reindirizzamento**: immetti l'URL per la tua istanza di Dynamics 365, ad esempio, `https://yourdynamicsinstance.dynamics.com/auth`.</span><span class="sxs-lookup"><span data-stu-id="5ea62-232">**Redirect URI setup** – Enter the URL for your Dynamics 365 instance, such as, `https://yourdynamicsinstance.dynamics.com/auth`.</span></span>

    3. <span data-ttu-id="5ea62-233">Vai all'app che hai appena creato e copia e salva il suo valore **ID applicazione (client)**.</span><span class="sxs-lookup"><span data-stu-id="5ea62-233">Go to the app that you just created, and copy and save its **Application (client) ID** value.</span></span> <span data-ttu-id="5ea62-234">Dovrai fornire questo valore in un secondo momento, quando configuri il Key Vault.</span><span class="sxs-lookup"><span data-stu-id="5ea62-234">You will have to provide this value later, when you set up the key vault.</span></span>
    4. <span data-ttu-id="5ea62-235">Vai ad **Autorizzazioni API** e segui questi passaggi:</span><span class="sxs-lookup"><span data-stu-id="5ea62-235">Go to **API permissions**, and follow these steps:</span></span>

        1. <span data-ttu-id="5ea62-236">Seleziona **Aggiungi un'autorizzazione**.</span><span class="sxs-lookup"><span data-stu-id="5ea62-236">Select **Add a permission**.</span></span>
        2. <span data-ttu-id="5ea62-237">Seleziona **Azure Key Vault**.</span><span class="sxs-lookup"><span data-stu-id="5ea62-237">Select **Azure Key vault**.</span></span>
        3. <span data-ttu-id="5ea62-238">Dopo aver selezionato le autorizzazioni delegate, seleziona **utente\_impersonificazione**.</span><span class="sxs-lookup"><span data-stu-id="5ea62-238">After you select delegated permissions, select **user\_impersonation**.</span></span>
        4. <span data-ttu-id="5ea62-239">Seleziona **Aggiungi autorizzazioni**.</span><span class="sxs-lookup"><span data-stu-id="5ea62-239">Select **Add permissions**.</span></span>

    5. <span data-ttu-id="5ea62-240">Nel menu dell'app, seleziona **Certificati \& segreti** e quindi segui questi passaggi per creare segreti di Key Vault:</span><span class="sxs-lookup"><span data-stu-id="5ea62-240">On the menu for the app, select **Certificates \& secrets**, and then follow these steps to create Key Vault secrets:</span></span>

        1. <span data-ttu-id="5ea62-241">Seleziona **Nuovo segreto client**.</span><span class="sxs-lookup"><span data-stu-id="5ea62-241">Select **New client secret**.</span></span>
        2. <span data-ttu-id="5ea62-242">Nel campo **Descrizione chiave** immetti un nome.</span><span class="sxs-lookup"><span data-stu-id="5ea62-242">In the **Key Description** field, enter a name.</span></span>
        3. <span data-ttu-id="5ea62-243">Seleziona una durata e quindi seleziona **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="5ea62-243">Select a duration, and then select **Add**.</span></span> <span data-ttu-id="5ea62-244">Un segreto viene generato nel campo **Valore**.</span><span class="sxs-lookup"><span data-stu-id="5ea62-244">A secret is generated in the **Value** field.</span></span>
        4. <span data-ttu-id="5ea62-245">Copia e salva il valore del segreto.</span><span class="sxs-lookup"><span data-stu-id="5ea62-245">Copy and save the secret value.</span></span>

4. <span data-ttu-id="5ea62-246">Crea segreti Key Vault:</span><span class="sxs-lookup"><span data-stu-id="5ea62-246">Create Key Vault secrets:</span></span>

    1. <span data-ttu-id="5ea62-247">Vai al Key Vault creato in precedenza e seleziona **Segreti**.</span><span class="sxs-lookup"><span data-stu-id="5ea62-247">Go to the key vault that you created earlier, and select **Secrets**.</span></span>
    2. <span data-ttu-id="5ea62-248">Per ogni nome segreto nella tabella seguente, segui questi passaggi:</span><span class="sxs-lookup"><span data-stu-id="5ea62-248">For each secret name in the following table, follow these steps:</span></span>

        1. <span data-ttu-id="5ea62-249">Seleziona **Genera/Importa**.</span><span class="sxs-lookup"><span data-stu-id="5ea62-249">Select **Generate/Import**.</span></span>
        2. <span data-ttu-id="5ea62-250">Nella finestra di dialogo **Crea un segreto**, nel campo **Opzioni di caricamento**, seleziona **Manuale**.</span><span class="sxs-lookup"><span data-stu-id="5ea62-250">In the **Create a secret** dialog box, in the **Upload options** field, select **Manual**.</span></span>
        3. <span data-ttu-id="5ea62-251">Crea il nome e il valore del segreto dalla seguente tabella.</span><span class="sxs-lookup"><span data-stu-id="5ea62-251">Create the secret name and value from the following table.</span></span>
        4. <span data-ttu-id="5ea62-252">Seleziona **Abilitato** e quindi **Crea**.</span><span class="sxs-lookup"><span data-stu-id="5ea62-252">Select **Enabled**, and then select **Create**.</span></span> <span data-ttu-id="5ea62-253">Il segreto viene creato e aggiunto al Key Vault.</span><span class="sxs-lookup"><span data-stu-id="5ea62-253">The secret is created and added to Key Vault.</span></span>

        | <span data-ttu-id="5ea62-254">Nome segreto</span><span class="sxs-lookup"><span data-stu-id="5ea62-254">Secret name</span></span>                       | <span data-ttu-id="5ea62-255">Valore segreto</span><span class="sxs-lookup"><span data-stu-id="5ea62-255">Secret value</span></span>                                                                                |
        |-----------------------------------|---------------------------------------------------------------------------------------------|
        | <span data-ttu-id="5ea62-256">app-id</span><span class="sxs-lookup"><span data-stu-id="5ea62-256">app-id</span></span>                            | <span data-ttu-id="5ea62-257">L'ID app dell'applicazione che hai creato in precedenza</span><span class="sxs-lookup"><span data-stu-id="5ea62-257">The app ID of the application that you created earlier</span></span>                                      |
        | <span data-ttu-id="5ea62-258">app-secret</span><span class="sxs-lookup"><span data-stu-id="5ea62-258">app-secret</span></span>                        | <span data-ttu-id="5ea62-259">Il segreto client che hai salvato in precedenza</span><span class="sxs-lookup"><span data-stu-id="5ea62-259">The client secret that you saved earlier</span></span>                                                    |
        | <span data-ttu-id="5ea62-260">storage-account-name</span><span class="sxs-lookup"><span data-stu-id="5ea62-260">storage-account-name</span></span>              | <span data-ttu-id="5ea62-261">Il nome dell'account di archiviazione creato in precedenza, ad esempio **storageaccount1**</span><span class="sxs-lookup"><span data-stu-id="5ea62-261">The name of the storage account that you created earlier, such as **storageaccount1**</span></span>       |
        | <span data-ttu-id="5ea62-262">storage-account-connection-string</span><span class="sxs-lookup"><span data-stu-id="5ea62-262">storage-account-connection-string</span></span> | <span data-ttu-id="5ea62-263">La stringa di connessione che hai copiato dalla pagina **Chiavi di accesso** per l'account di archiviazione</span><span class="sxs-lookup"><span data-stu-id="5ea62-263">The connection string that you copied from the **Access keys** page for the storage account</span></span> |

5. <span data-ttu-id="5ea62-264">Autorizza l'applicazione ad accedere al Key Vault:</span><span class="sxs-lookup"><span data-stu-id="5ea62-264">Authorize the application to access the key vault:</span></span>

    1. <span data-ttu-id="5ea62-265">Nel [portale di Azure](https://portal.azure.com), apri il Key Vault creato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="5ea62-265">In the [Azure portal](https://portal.azure.com), open the key vault that you created earlier.</span></span>
    2. <span data-ttu-id="5ea62-266">Seleziona i criteri di accesso.</span><span class="sxs-lookup"><span data-stu-id="5ea62-266">Select the access policies.</span></span>
    3. <span data-ttu-id="5ea62-267">Per ogni applicazione nella tabella seguente, segui questi passaggi:</span><span class="sxs-lookup"><span data-stu-id="5ea62-267">For each application in the following table, follow these steps:</span></span>

        1. <span data-ttu-id="5ea62-268">Seleziona **Aggiungi criteri di accesso** per creare un criterio di accesso.</span><span class="sxs-lookup"><span data-stu-id="5ea62-268">Select **Add Access Policy** to create an access policy.</span></span>
        2. <span data-ttu-id="5ea62-269">Nel campo **Autorizzazioni segreto**, seleziona le autorizzazioni dalla tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="5ea62-269">In the **Secret permissions** field, select the permissions from the following table.</span></span>
        3. <span data-ttu-id="5ea62-270">Nel campo **Seleziona entità di sicurezza**, cerca il nome visualizzato dell'applicazione dalla tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="5ea62-270">In the **Select principal** field, search for the application display name from the following table.</span></span>
        4. <span data-ttu-id="5ea62-271">Selezionare **Select**.</span><span class="sxs-lookup"><span data-stu-id="5ea62-271">Select **Select**.</span></span>
        5. <span data-ttu-id="5ea62-272">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="5ea62-272">Select **Add**.</span></span>
        6. <span data-ttu-id="5ea62-273">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="5ea62-273">Select **Save**.</span></span>

        | <span data-ttu-id="5ea62-274">Domanda di lavoro</span><span class="sxs-lookup"><span data-stu-id="5ea62-274">Application</span></span>                                              | <span data-ttu-id="5ea62-275">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="5ea62-275">Permissions</span></span> |
        |----------------------------------------------------------|-------------|
        | <span data-ttu-id="5ea62-276">Il nome visualizzato della nuova applicazione che hai creato</span><span class="sxs-lookup"><span data-stu-id="5ea62-276">The display name of the new application that you created</span></span> | <span data-ttu-id="5ea62-277">Get, List</span><span class="sxs-lookup"><span data-stu-id="5ea62-277">Get, List</span></span>   |
        | <span data-ttu-id="5ea62-278">**Microservizi ERP Microsoft Dynamics**</span><span class="sxs-lookup"><span data-stu-id="5ea62-278">**Microsoft Dynamics ERP Microservices**</span></span>                 | <span data-ttu-id="5ea62-279">Get, List</span><span class="sxs-lookup"><span data-stu-id="5ea62-279">Get, List</span></span>   |

6. <span data-ttu-id="5ea62-280">Assegna ruoli per accedere all'account di archiviazione:</span><span class="sxs-lookup"><span data-stu-id="5ea62-280">Assign roles to access the storage account:</span></span>

    1. <span data-ttu-id="5ea62-281">Nel [portale di Azure](https://portal.azure.com), apri l'account di archiviazione creato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="5ea62-281">In the [Azure portal](https://portal.azure.com), open the storage account that you created earlier.</span></span>
    2. <span data-ttu-id="5ea62-282">Seleziona **Controllo dei diritti di accesso (IAM)** e quindi seleziona **Assegnazioni di ruolo**.</span><span class="sxs-lookup"><span data-stu-id="5ea62-282">Select **Access Control (IAM)**, and then select **Role Assignments**.</span></span>
    3. <span data-ttu-id="5ea62-283">Seleziona **Aggiungi, Aggiungi assegnazione di ruolo**.</span><span class="sxs-lookup"><span data-stu-id="5ea62-283">Select **Add, Add Role Assignment**.</span></span>
    4. <span data-ttu-id="5ea62-284">Per ogni applicazione nella tabella seguente, segui questi passaggi:</span><span class="sxs-lookup"><span data-stu-id="5ea62-284">For each application in the following table, follow these steps:</span></span>

        1. <span data-ttu-id="5ea62-285">Seleziona il ruolo dalla tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="5ea62-285">Select the role from the following table.</span></span>
        2. <span data-ttu-id="5ea62-286">Lascia il campo **Assegna accesso a** impostato su **Utente, gruppo o entità servizio Azure AD**.</span><span class="sxs-lookup"><span data-stu-id="5ea62-286">Leave the **Assign access to** field set to **Azure AD user, group, or service principal**.</span></span>
        3. <span data-ttu-id="5ea62-287">Nel campo **Seleziona**, immetti l'applicazione dalla tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="5ea62-287">In the **Select** field, enter the application from the following table.</span></span>
        4. <span data-ttu-id="5ea62-288">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="5ea62-288">Select **Save**.</span></span>

        | <span data-ttu-id="5ea62-289">Domanda di lavoro</span><span class="sxs-lookup"><span data-stu-id="5ea62-289">Application</span></span>                                              | <span data-ttu-id="5ea62-290">Ruolo</span><span class="sxs-lookup"><span data-stu-id="5ea62-290">Role</span></span>                        |
        |----------------------------------------------------------|-----------------------------|
        | <span data-ttu-id="5ea62-291">Il nome visualizzato della nuova applicazione che hai creato</span><span class="sxs-lookup"><span data-stu-id="5ea62-291">The display name of the new application that you created</span></span> | <span data-ttu-id="5ea62-292">Proprietario</span><span class="sxs-lookup"><span data-stu-id="5ea62-292">Owner</span></span>                       |
        | <span data-ttu-id="5ea62-293">Il nome visualizzato della nuova applicazione che hai creato</span><span class="sxs-lookup"><span data-stu-id="5ea62-293">The display name of the new application that you created</span></span> | <span data-ttu-id="5ea62-294">Collaboratore</span><span class="sxs-lookup"><span data-stu-id="5ea62-294">Contributor</span></span>                 |
        | <span data-ttu-id="5ea62-295">Il nome visualizzato della nuova applicazione che hai creato</span><span class="sxs-lookup"><span data-stu-id="5ea62-295">The display name of the new application that you created</span></span> | <span data-ttu-id="5ea62-296">Collaboratore account di archiviazione</span><span class="sxs-lookup"><span data-stu-id="5ea62-296">Storage Account Contributor</span></span> |
        | <span data-ttu-id="5ea62-297">Il nome visualizzato della nuova applicazione che hai creato</span><span class="sxs-lookup"><span data-stu-id="5ea62-297">The display name of the new application that you created</span></span> | <span data-ttu-id="5ea62-298">Proprietario dei dati del BLOB di archiviazione</span><span class="sxs-lookup"><span data-stu-id="5ea62-298">Storage Blob Data Owner</span></span>     |
        | <span data-ttu-id="5ea62-299">**Servizio di autorizzazione di AI Builder**</span><span class="sxs-lookup"><span data-stu-id="5ea62-299">**AI Builder Authorization Service**</span></span>                     | <span data-ttu-id="5ea62-300">Lettore dati del BLOB di archiviazione</span><span class="sxs-lookup"><span data-stu-id="5ea62-300">Storage Blob Data Reader</span></span>    |

# <a name="azure-cli"></a>[<span data-ttu-id="5ea62-301">Azure CLI</span><span class="sxs-lookup"><span data-stu-id="5ea62-301">Azure CLI</span></span>](#tab/azure-azure-cli)

```
function New-FinanceDataLakeAzureResources {
    $defaultSecretExpiryInYear = 1

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

    $subscriptionId = (Read-Host -Prompt "Enter the Azure Subscription ID: (blank for default)")
    if ($subscriptionId.Trim() -ne '') {
        $azSubscription = Select-AzSubscription -SubscriptionId $subscriptionId
    }

    $resourceGroupName = (Read-Host -Prompt "Enter the Azure Resource Group name: (blank for 'FinanceDataLake')")
    if ($null -eq $resourceGroupName -or $resourceGroupName.Trim() -eq '') {
        $resourceGroupName = 'FinanceDataLake'
    }
    $resourceGroup = Get-AzResourceGroup -Name $resourceGroupName -ErrorAction SilentlyContinue

    if (-not ($resourceGroup)) {
        $resourceLocation = ''
        $azResourceLocations = (Get-AzLocation | Select-Object Location).Location
        while ($resourceLocation.Trim() -eq '' -or (-not ($resourceLocation -in $azResourceLocations))) {
            $resourceLocation = (Read-Host -Prompt "Enter the location in which to create the Azure Resource Group: ('help' to see values)")
            if ($resourceLocation -eq 'help') {
                $azResourceLocations
                $resourceLocation = ''
            }
        }
        $resourceGroup = New-AzResourceGroup -Name $resourceGroupName -Location $resourceLocation
    }
    else {
        $resourceLocation = $resourceGroup.Location
    }

    $clientAppName = (Read-Host -Prompt "Enter the name of the application registration: (blank for 'Finance Data Lake Application')")
    if ($clientAppName.Trim() -eq '') {
        $clientAppName = 'Finance Data Lake Application'
    }

    Write-Output '================================================================================='

    $service = Get-AzureADServicePrincipal -Filter ("AppId eq '" + $MicrosoftDynamicsERPMicroservicesAppId + "'")
    if (-not $service) {
        New-AzureADServicePrincipal -AppId $MicrosoftDynamicsERPMicroservicesAppId | Format-Table -AutoSize
        $service = Get-AzureADServicePrincipal -Filter ("AppId eq '" + $MicrosoftDynamicsERPMicroservicesAppId + "'")
        Write-Output ("Added AAD Enterprise Application 'Microsoft Dynamics ERP Microservices' with Application ID {0}" -f $MicrosoftDynamicsERPMicroservicesAppId)
    }
    else {
        Write-Output ("Found AAD Enterprise Application 'Microsoft Dynamics ERP Microservices' with Application ID {0}" -f $MicrosoftDynamicsERPMicroservicesAppId)
    }
    $MicrosoftDynamicsERPMicroservicesAppObjectId = $service.ObjectId

    $service = Get-AzureADServicePrincipal -Filter ("AppId eq '" + $MicrosoftDynamicsERPMicroservicesCDSAppId + "'")
    if (-not $service) {
        New-AzureADServicePrincipal -AppId $MicrosoftDynamicsERPMicroservicesCDSAppId | Format-Table -AutoSize
        Write-Output ("Added AAD Enterprise Application 'Microsoft Dynamics ERP Microservices CDS' with Application ID {0}" -f $MicrosoftDynamicsERPMicroservicesCDSAppId)
    }
    else {
        Write-Output ("Found AAD Enterprise Application 'Microsoft Dynamics ERP Microservices CDS' with Application ID {0}" -f $MicrosoftDynamicsERPMicroservicesCDSAppId)
    }

    $service = Get-AzureADServicePrincipal -Filter ("AppId eq '" + $AIBuilderAuthorizationServiceAppId + "'")
    if (-not $service) {
        New-AzureADServicePrincipal -AppId $AIBuilderAuthorizationServiceAppId | Format-Table -AutoSize
        $service = Get-AzureADServicePrincipal -Filter ("AppId eq '" + $AIBuilderAuthorizationServiceAppId + "'")
        Write-Output ("Added AAD Enterprise Application 'AI Builder Authorization Service' with Application ID {0}" -f $AIBuilderAuthorizationServiceAppId)
    }
    else {
        Write-Output ("Found AAD Enterprise Application 'AI Builder Authorization Service' with Application ID {0}" -f $AIBuilderAuthorizationServiceAppId)
    }
    $aibuilderAuthorizationServiceObjectId = $service.ObjectId

    Write-Output '================================================================================='

    $clientAppSPN = Get-AzureADServicePrincipal -Filter ("DisplayName eq '" + $clientAppName + "'")
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

        $clientApp = New-AzureADApplication -DisplayName $clientAppName -RequiredResourceAccess @($keyVaultAccess, $graphAccess)
        $clientAppSPN = New-AzureADServicePrincipal -AppId $clientApp.AppId -Tags @($clientAppName)
        $clientAppId = $clientApp.AppId
        Write-Output ('Created App Registration "' + $clientAppName + '" with Application Id: ' + $clientAppId)
    }
    else {
        $clientApp = Get-AzureADApplication -Filter ("DisplayName eq '" + $clientAppName + "'")
        $clientAppId = $clientApp.AppId
        Write-Output ('Found App Registration "' + $clientAppName + '" with Application Id: ' + $clientAppId)
    }
            
    $clientAppSecretCredential = New-AzureADApplicationPasswordCredential -ObjectId $clientApp.ObjectId -CustomKeyIdentifier "ClientAppAccessKey" -EndDate (get-date).AddYears($defaultSecretExpiryInYear)
    $ClientAppSecret = $clientAppSecretCredential.Value
    $clientAppSpId = $clientAppSPN.ObjectId

    Write-Output ('Generated application secret: ' + $ClientAppSecret)
    Write-Output '================================================================================='

    $templateObject = ConvertFrom-Json $azureTemplate -AsHashtable
    $templateObject.{$schema} = "https://schema.management.azure.com/schemas/2019-04-01/deploymentTemplate.json#"
    Write-Output 'Provisioning Azure resources. This may take a few minutes.'
    $deployment = New-AzResourceGroupDeployment -ResourceGroupName $resourceGroupName -TemplateObject $templateObject -aibuilderAppObjectId $aibuilderAuthorizationServiceObjectId -clientAppId $clientAppId -clientAppSecret $ClientAppSecret -clientAppSpObjectId  $clientAppSpId -microserviceSpObjectId $MicrosoftDynamicsERPMicroservicesAppObjectId -userSpObjectId $user.ObjectId

    if ($deployment.ProvisioningState -eq 'Succeeded') {
        Write-Output "Successfully deployed the following resources to Azure:"
        Write-Output ("  Key Vault:                         " + $deployment.Outputs.keyVaultName.Value)
        Write-Output ("  Storage Account:                   " + $deployment.Outputs.storageAccountName.Value)
    }
    else {
        Write-Output ("Provisioning Azure resources failed with the following state: " + $deployment.ProvisioningState)
        Write-Output ("Some of the resources may have been created in resource group: " + $resourceGroupName)
    }

    Write-Output '================================================================================='

    $keyVault = Get-AzKeyVault -VaultName $deployment.Outputs.keyVaultName.Value
    Write-Output "Values for LCS Data Lake Add-In:"
    Write-Output ("  Tenant ID:                         " + $subscriptionContext.Context.Subscription.TenantId)
    Write-Output ("  DNS Name:                          " + $keyVault.VaultUri)
    Write-Output "  Storage account secret name:       storage-account-name"
    Write-Output "  Application ID secret name:        app-id"
    Write-Output "  Application Secret secret name:    app-secret"
    Write-Warning "Copy this information for the LCS Add-in as it is not saved. Azure Cloud Shell will eventually time out and close."

    Write-Output '================================================================================='
    Write-Output "Values for System parameters > Data connections:"
    Write-Output ("  Application ID:                    " + $clientAppId)
    Write-Output ("  Application Secret:                " + $ClientAppSecret)
    Write-Output ("  DNS name:                          " + $keyVault.VaultUri)
    Write-Output "  Secret name:                       storage-account-connection-string"
    Write-Warning "Copy this information for the System parameters as it is not saved. Azure Cloud Shell will eventually time out and close."
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
  New-FinanceDataLakeAzureResources
}
catch {
  Write-Error $_.Exception.Message
  Write-Warning $_.Exception.StackTrace
  $inner = $_.Exception.InnerException
  while ($null -ne $inner) {
    Write-Output 'Inner Exception:'
    Write-Error $_.Exception.Message
    Write-Warning $_.Exception.StackTrace
    $inner = $inner.InnerException
  }
}

```
---

## <a name="configure-the-entity-store"></a><span data-ttu-id="5ea62-302">Configurare l'archivio entità</span><span class="sxs-lookup"><span data-stu-id="5ea62-302">Configure the entity store</span></span>

<span data-ttu-id="5ea62-303">Segui questi passaggi per configurare l'archivio entità nel tuo ambiente Finance.</span><span class="sxs-lookup"><span data-stu-id="5ea62-303">Follow these steps to set up the entity store in your Finance environment.</span></span>

1. <span data-ttu-id="5ea62-304">Vai ad **Amministrazione sistema \> Imposta \> Parametri di sistema \> Connessioni dati**.</span><span class="sxs-lookup"><span data-stu-id="5ea62-304">Go to **System administration \> Setup \> System parameters \> Data connections**.</span></span>
2. <span data-ttu-id="5ea62-305">Imposta l'opzione **Abilita l'integrazione di Data Lake** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="5ea62-305">Set the **Enable Data Lake integration** option to **Yes**.</span></span>
3. <span data-ttu-id="5ea62-306">Imposta i seguenti campi di Key Vault:</span><span class="sxs-lookup"><span data-stu-id="5ea62-306">Set the following Key Vault fields:</span></span>

    - <span data-ttu-id="5ea62-307">**ID applicazione (client)**: immetti l'ID client dell'applicazione creato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="5ea62-307">**Application (client) ID** – Enter the application client ID that you created earlier.</span></span>
    - <span data-ttu-id="5ea62-308">**Segreto applicazione**: immetti il segreto che hai salvato per l'applicazione che hai creato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="5ea62-308">**Application Secret** – Enter the secret that you saved for the application that you created earlier.</span></span>
    - <span data-ttu-id="5ea62-309">**Nome DNS**: puoi trovare il nome DNS (Domain Name System) nella pagina dei dettagli dell'applicazione per l'applicazione creata in precedenza.</span><span class="sxs-lookup"><span data-stu-id="5ea62-309">**DNS name** – You can find the Domain Name System (DNS) name on the application details page for the application that you created earlier.</span></span>
    - <span data-ttu-id="5ea62-310">**Nome segreto**: immetti **storage-account-connection-string**.</span><span class="sxs-lookup"><span data-stu-id="5ea62-310">**Secret name** – Enter **storage-account-connection-string**.</span></span>

## <a name="configure-the-data-lake"></a><span data-ttu-id="5ea62-311">Configurare il data lake</span><span class="sxs-lookup"><span data-stu-id="5ea62-311">Configure the data lake</span></span>

<span data-ttu-id="5ea62-312">Segui questi passaggi per utilizzare LCS per aggiungere il componente aggiuntivo Azure Data Lake all'ambiente.</span><span class="sxs-lookup"><span data-stu-id="5ea62-312">Follow these steps to use LCS to add the Azure Data Lake add-in to the environment.</span></span>

1. <span data-ttu-id="5ea62-313">Accedi a LCS, quindi, sotto il nome dell'ambiente sul lato destro della pagina, seleziona **Dettagli completi**.</span><span class="sxs-lookup"><span data-stu-id="5ea62-313">Sign in to LCS, and then, under the environment name on the right side of the page, select **Full Details**.</span></span>
2. <span data-ttu-id="5ea62-314">Nella sezione **Componenti aggiuntivi per l'ambiente**, selezionare **Installa un nuovo componente aggiuntivo**.</span><span class="sxs-lookup"><span data-stu-id="5ea62-314">In the **Environment add-ins** section, select **Install a new add-in**.</span></span>
3. <span data-ttu-id="5ea62-315">Seleziona il componente aggiunti **Esporta in Data Lake**.</span><span class="sxs-lookup"><span data-stu-id="5ea62-315">Select the **Export to Data Lake** add-in.</span></span>
4. <span data-ttu-id="5ea62-316">Immetti i valori seguenti.</span><span class="sxs-lookup"><span data-stu-id="5ea62-316">Enter the following values.</span></span>

    | <span data-ttu-id="5ea62-317">Valore</span><span class="sxs-lookup"><span data-stu-id="5ea62-317">Value</span></span>                                                              | <span data-ttu-id="5ea62-318">descrizione</span><span class="sxs-lookup"><span data-stu-id="5ea62-318">Description</span></span> |
    |--------------------------------------------------------------------|-------------|
    | <span data-ttu-id="5ea62-319">ID tenant della sottoscrizione di Azure in cui si trova il Key Vault</span><span class="sxs-lookup"><span data-stu-id="5ea62-319">Tenant ID of the Azure Subscription where the Key Vault is located</span></span> | <span data-ttu-id="5ea62-320">L'ID tenant in cui si trovano l'account di archiviazione, le app e i Key Vault.</span><span class="sxs-lookup"><span data-stu-id="5ea62-320">The tenant ID where the storage account, apps, and key vaults are located.</span></span> <span data-ttu-id="5ea62-321">Per trovare questo valore, apri il [portale di Azure](https://portal.azure.com), vai ad **Azure Active Directory** e copia il valore **ID tenant**.</span><span class="sxs-lookup"><span data-stu-id="5ea62-321">To find this value, open the [Azure portal](https://portal.azure.com), go to **Azure Active Directory**, and copy the **Tenant ID** value.</span></span> |
    | <span data-ttu-id="5ea62-322">Specificare il nome DNS del Key Vault</span><span class="sxs-lookup"><span data-stu-id="5ea62-322">Provide the DNS name of your Key Vault</span></span>                             | <span data-ttu-id="5ea62-323">Il nome DNS del Key Vault, ad esempio `https://customkeyvault.vault.azure.net/`.</span><span class="sxs-lookup"><span data-stu-id="5ea62-323">The DNS name of the key vault, such as `https://customkeyvault.vault.azure.net/`.</span></span> <span data-ttu-id="5ea62-324">Questo valore corrisponde al nome DNS utilizzato nell'archivio entità.</span><span class="sxs-lookup"><span data-stu-id="5ea62-324">(This value matches the DNS name that is used in the entity store.)</span></span> |
    | <span data-ttu-id="5ea62-325">Fornire il segreto contenente il nome dell'account di archiviazione</span><span class="sxs-lookup"><span data-stu-id="5ea62-325">Provide the secret that contains the name of the storage account</span></span>   | <span data-ttu-id="5ea62-326">**storage-account-name**</span><span class="sxs-lookup"><span data-stu-id="5ea62-326">**storage-account-name**</span></span> |
    | <span data-ttu-id="5ea62-327">Nome segreto per l'ID app da utilizzare per accedere al data lake</span><span class="sxs-lookup"><span data-stu-id="5ea62-327">Secret Name for App ID to be used for accessing Data Lake</span></span>          | <span data-ttu-id="5ea62-328">**app-id**</span><span class="sxs-lookup"><span data-stu-id="5ea62-328">**app-id**</span></span> |
    | <span data-ttu-id="5ea62-329">Nome segreto da utilizzare con l'ID app</span><span class="sxs-lookup"><span data-stu-id="5ea62-329">Secret name to be used with App ID</span></span>                                 | <span data-ttu-id="5ea62-330">**app-secret**</span><span class="sxs-lookup"><span data-stu-id="5ea62-330">**app-secret**</span></span> |

5. <span data-ttu-id="5ea62-331">Accetta le condizioni e seleziona **Installa**.</span><span class="sxs-lookup"><span data-stu-id="5ea62-331">Agree to the terms, and select **Install**.</span></span>

<span data-ttu-id="5ea62-332">Il componente aggiuntivo verrà installato in pochi minuti.</span><span class="sxs-lookup"><span data-stu-id="5ea62-332">The add-in will be installed within a few minutes.</span></span>

## <a name="configure-ai-builder"></a><span data-ttu-id="5ea62-333">Configurare AI Builder</span><span class="sxs-lookup"><span data-stu-id="5ea62-333">Configure AI Builder</span></span>

1. <span data-ttu-id="5ea62-334">Accedi a LCS e apri la pagina **Dettagli ambiente**.</span><span class="sxs-lookup"><span data-stu-id="5ea62-334">Sign in to LCS, and open the **Environment details** page.</span></span>
2. <span data-ttu-id="5ea62-335">Scorrere fino alla sezione **Componenti aggiuntivi dell'ambiente**.</span><span class="sxs-lookup"><span data-stu-id="5ea62-335">Scroll to the **Environment add-ins** section.</span></span> <span data-ttu-id="5ea62-336">Dovresti vedere i componenti aggiuntivi già installati in questo ambiente.</span><span class="sxs-lookup"><span data-stu-id="5ea62-336">You should see the add-ins that are already installed in this environment.</span></span> <span data-ttu-id="5ea62-337">Se il componente aggiuntivo **Esporta in Data Lake** non è tra questi, configuralo.</span><span class="sxs-lookup"><span data-stu-id="5ea62-337">If the **Export to Data Lake** add-in isn't among them, configure this add-in.</span></span>
3. <span data-ttu-id="5ea62-338">Seleziona il componente aggiuntivo **Ottieni informazioni dettagliate**.</span><span class="sxs-lookup"><span data-stu-id="5ea62-338">Select the **Get insights** add-in.</span></span>
4. <span data-ttu-id="5ea62-339">Nella pagina dei dettagli del componente aggiuntivo **Ottieni informazioni dettagliate**, immetti i seguenti valori.</span><span class="sxs-lookup"><span data-stu-id="5ea62-339">On the **Get insights** add-in details page, enter the following values.</span></span>

    | <span data-ttu-id="5ea62-340">Valore</span><span class="sxs-lookup"><span data-stu-id="5ea62-340">Value</span></span>                                                    | <span data-ttu-id="5ea62-341">descrizione</span><span class="sxs-lookup"><span data-stu-id="5ea62-341">Description</span></span> |
    |----------------------------------------------------------|-------------|
    | <span data-ttu-id="5ea62-342">URL organizzazione CDS</span><span class="sxs-lookup"><span data-stu-id="5ea62-342">CDS Organization URL</span></span>                                     | <span data-ttu-id="5ea62-343">L'URL dell'organizzazione Common Data Service dell'istanza Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="5ea62-343">The Common Data Service organization URL of the Common Data Service instance.</span></span> <span data-ttu-id="5ea62-344">Per trovare questo valore, apri il [portale di Power Apps](https://make.powerapps.com), seleziona il pulsante **Impostazioni** (simbolo dell'ingranaggio) nell'angolo in alto a destra in alto, seleziona **Impostazioni avanzate** e copia l'URL.</span><span class="sxs-lookup"><span data-stu-id="5ea62-344">To find this value, open the [Power Apps portal](https://make.powerapps.com), select the **Settings** button (gear symbol) in the upper-right upper corner, select **Advanced settings**, and copy the URL.</span></span> <span data-ttu-id="5ea62-345">L'URL termina con "dynamics.com".</span><span class="sxs-lookup"><span data-stu-id="5ea62-345">(The URL ends with "dynamics.com.")</span></span> |
    | <span data-ttu-id="5ea62-346">ID org CDS</span><span class="sxs-lookup"><span data-stu-id="5ea62-346">CDS Org ID</span></span>                                               | <span data-ttu-id="5ea62-347">L'ID ambiente dell'istanza di Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="5ea62-347">The environment ID of the Common Data Service instance.</span></span> <span data-ttu-id="5ea62-348">Per trovare questo valore, apri il [portale di Power Apps](https://make.powerapps.com), seleziona il pulsante **Impostazioni** (simbolo dell'ingranaggio) nell'angolo in alto a destra in alto, seleziona **Personalizzazioni \> Risorse per sviluppatori \> Informazioni di riferimento sull'istanza** e copia il valore **ID**.</span><span class="sxs-lookup"><span data-stu-id="5ea62-348">To find this value, open the [Power Apps portal](https://make.powerapps.com), select the **Settings** button (gear symbol) in the upper-right upper corner, select **Customizations \> Developer resources \> Instance Reference Information**, and copy the **ID** value.</span></span> |
    | <span data-ttu-id="5ea62-349">ID tenant CDS (ID directory da AAD)</span><span class="sxs-lookup"><span data-stu-id="5ea62-349">CDS Tenant ID (Directory ID from AAD)</span></span>               | <span data-ttu-id="5ea62-350">L'ID tenant dell'istanza di Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="5ea62-350">The tenant ID of the Common Data Service instance.</span></span> <span data-ttu-id="5ea62-351">Per trovare questo valore, apri il [portale di Azure](https://portal.azure.com), vai ad **Azure Active Directory** e copia il valore **ID tenant**.</span><span class="sxs-lookup"><span data-stu-id="5ea62-351">To find this value, open the [Azure portal](https://portal.azure.com), go to **Azure Active Directory**, and copy the **Tenant ID** value.</span></span> |
    | <span data-ttu-id="5ea62-352">Specificare l'ID oggetto utente con ruolo di amministratore di sistema</span><span class="sxs-lookup"><span data-stu-id="5ea62-352">Provide user object ID who has system administrator role</span></span> | <span data-ttu-id="5ea62-353">L'ID oggetto utente Azure AD dell'utente in Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="5ea62-353">The Azure AD user object ID of the user in Common Data Service.</span></span> <span data-ttu-id="5ea62-354">Questo utente deve essere un amministratore di sistema dell'istanza di Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="5ea62-354">This user must be a system administrator of the Common Data Service instance.</span></span> <span data-ttu-id="5ea62-355">Per trovare questo valore, apri il [portale di Azure](https://portal.azure.com), vai ad **Azure Active Directory\> Utenti**, seleziona l'utente, quindi, nella sezione **Identità**, copia il valore **ID oggetto**.</span><span class="sxs-lookup"><span data-stu-id="5ea62-355">To find this value, open the [Azure portal](https://portal.azure.com), go to **Azure Active Directory \> Users**, select the user, and then, in the **Identity** section, copy the **Object ID** value.</span></span> |
    | <span data-ttu-id="5ea62-356">È questo l'ambiente CDS predefinito per il tenant?</span><span class="sxs-lookup"><span data-stu-id="5ea62-356">Is this the default CDS environment for the tenant?</span></span>      | <span data-ttu-id="5ea62-357">Se l'istanza di Common Data Service è stata la prima istanza di produzione creata, seleziona questa casella di controllo.</span><span class="sxs-lookup"><span data-stu-id="5ea62-357">If the Common Data Service instance was the first production instance that was created, select this check box.</span></span> <span data-ttu-id="5ea62-358">Se l'istanza di Common Data Service è stata creata manualmente, deseleziona questa casella di controllo.</span><span class="sxs-lookup"><span data-stu-id="5ea62-358">If the Common Data Service instance was manually created, clear this check box.</span></span> |

## <a name="feedback-and-support"></a><span data-ttu-id="5ea62-359">Feedback e supporto</span><span class="sxs-lookup"><span data-stu-id="5ea62-359">Feedback and support</span></span>

<span data-ttu-id="5ea62-360">Invia un messaggio e-mail a [Informazioni dettagliate sui pagamenti dei clienti (anteprima)](mailto:fiap@microsoft.com) se sei interessato a fornire feedback o hai bisogno di supporto.</span><span class="sxs-lookup"><span data-stu-id="5ea62-360">Please send an email to [Customer payment insights (Preview)](mailto:fiap@microsoft.com) if you are interested in providing feedback or need support.</span></span>

## <a name="privacy-notice"></a><span data-ttu-id="5ea62-361">Informativa sulla privacy</span><span class="sxs-lookup"><span data-stu-id="5ea62-361">Privacy notice</span></span>

<span data-ttu-id="5ea62-362">Le anteprime (1) potrebbero utilizzare meno misure di sicurezza e di privacy rispetto al servizio Dynamics 365 Finance and Operations, (2) non sono incluse nel contratto di servizio di questo servizio, (3) non devono essere utilizzate per elaborare i dati personali o altri dati soggetti a requisiti legati e normativi, e (4) hanno supporto limitato.</span><span class="sxs-lookup"><span data-stu-id="5ea62-362">Previews (1) might use less privacy and fewer security measures than the Dynamics 365 Finance and Operations service, (2) aren't included in the service level agreement (SLA) for this service, (3) should not be used to process personal data or other data that is subject to legal or regulatory compliance requirements, and (4) have limited support.</span></span>
