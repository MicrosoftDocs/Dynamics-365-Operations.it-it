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
# <a name="configuration-for-finance-insights-for-public-preview-preview---version-10020-and-later"></a>Configurazione di Finance Insights per l'anteprima pubblica (anteprima) - Versione 10.0.20 e successive

[!include [banner](../includes/banner.md)]

[!include [preview banner](../includes/preview-banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Finance Insights combina le funzionalità di Microsoft Dynamics 365 Finance con Dataverse, Azure e AI Builder per fornire potenti strumenti di previsione per la tua organizzazione. Questo argomento spiega come configurare Dynamics 365 Finance version 10.0.20 in modo che il sistema possa usare le funzionalità disponibili in Finance Insights per l'anteprima pubblica.

> [!NOTE]
> I passaggi di configurazione descritti in questo argomento si applicano solo a Finance versione 10.0.20 e successive. 'Per impostare Finance Insight sulla versione 10.0.19 e precedenti, vedi [Configurazione per Finance Insights - Versioni fino a 10.0.18](configure-for-fin-insites.md).

## <a name="deploy-finance"></a>Distribuzione di Finance

Attieniti a questa procedura per distribuire gli ambienti.

1. In Microsoft Dynamics Lifecycle Services (LCS), crea o aggiorna un ambiente Finance. L'ambiente richiede la versione dell'app 10.0.20 o successiva delle app Finance and Operations.
2. L'ambiente deve essere un ambiente ad alta disponibilità (HA) in Sandbox. (Questo tipo di ambiente è noto anche come ambiente Tier-2). Per altre informazioni, vedi [Pianificazione ambientale](../../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md).
3. Se stai configurando Finance Insights in un ambiente sandbox, potresti dover copiare i dati di produzione in tale ambiente affinché le stime funzionino. Il modello di stima utilizza più anni di dati per creare previsioni. I dati della demo di Contoso non contengono dati storici sufficienti per addestrare adeguatamente il modello di stima. 

## <a name="configure-dataverse"></a>Configura Dataverse

Segui questa procedura per configurare Dataverse per Finance insights.

1. In LCS, apri la pagina dell'ambiente e verifica che la sezione **Integrazione di Power Platform** sia già configurata.

    - Se è già configurata, il nome dell'ambiente Dataverse collegato all'ambiente Finance dovrebbe essere incluso nell'elenco.
    - In caso contrario, segui questi passaggi:

        1. Nella sezione **Integrazione di Power Platform**, seleziona **Configurazione**. La configurazione dell'ambiente potrebbe richiedere fino a un'ora.
        2. Se l'ambiente Dataverse è correttamente configurato, il nome dell'ambiente Dataverse collegato all'ambiente Finance dovrebbe essere incluso nell'elenco.

        > [!NOTE]
        > Dopo aver completato la configurazione dell'ambiente, **non** selezionare **Collegamento a CDS per le app**. Questo pulsante non è necessario per Finance Insights. Se lo selezioni, non sarai in grado di configurare i componenti aggiuntivi dell'ambiente richiesti in LCS.

## <a name="configure-azure"></a>Configurazione di Azure

### <a name="use-azure-cloud-shell-to-set-up-finance-insights-data-lake-resources"></a>Utilizzare Azure Cloud Shell per configurare le risorse Data Lake di Finance Insights

# <a name="use-a-windows-powershell-script"></a>[Utilizzare uno script di Windows PowerShell](#tab/use-a-powershell-script)

È stato fornito uno script di Windows PowerShell, in modo da poter configurare facilmente le risorse di Azure descritte in [Configurare l'esportazione in Azure Data Lake](../../fin-ops-core/dev-itpro/data-entities/configure-export-data-lake.md). Se preferisci eseguire la configurazione manualmente, salta questa procedura e continua con la procedura della sezione [Configurazione manuale](#manual-setup).

> [!NOTE]
> Utilizza la procedura seguente per eseguire lo script di Windows PowerShell. La configurazione potrebbe non funzionare se utilizzi l'opzione **Prova** nell'interfaccia della riga di comando di Azure o se esegui lo script nel computer.

Attieniti alla seguente procedura per usare lo script Windows PowerShell per configurare Azure. Devi disporre dei diritti per creare un gruppo di risorse di Azure, risorse di Azure e un'applicazione Azure AD. Per informazioni sulle autorizzazioni obbligatorie, vedi [Controllare le autorizzazioni di Azure AD](/azure/active-directory/develop/howto-create-service-principal-portal#permissions-required-for-registering-an-app).

1. Nel [portale di Azure](https://portal.azure.com), vai alla sottoscrizione di Azure di destinazione.
2. Seleziona **Cloud Shell** a destra del campo **Cerca**.
3. Seleziona **PowerShell**.
4. Crea lo spazio di archiviazione, se ti viene chiesto di farlo.
5. Nella scheda **Interfaccia della riga di comando di Azure**, seleziona **Copia**.
6. In Blocco note, apri un nuovo file e incolla lo script di Windows PowerShell.
7. Salva il file come **ConfigureDataLake.ps1**.
8. Carica lo script di Windows PowerShell nella sessione utilizzando l'opzione di menu per il caricamento in Cloud Shell.
9. Esegui lo script **.\ConfigureDataLake.ps1**.
10. Segui le istruzioni per eseguire lo script.
11. Utilizza le informazioni dall'output dello script per installare il componente aggiuntivo Esporta in Data Lake in LCS.

### <a name="manual-setup"></a>Configurazione manuale

#### <a name="add-applications-to-the-azure-ad-tenant"></a>Aggiungere applicazioni al tenant Azure AD

1. Nel [portale di Azure](https://portal.azure.com), passa a **Azure Active Directory**.
2. Seleziona **Gestisci \> Applicazioni aziendali**.
3. Cerca le seguenti applicazioni per ID app.

    | Domanda di lavoro                              | ID app                               |
    |------------------------------------------|--------------------------------------|
    | Microservizi ERP Microsoft Dynamics     | 0cdb527f-a8d1-4bf8-9436-b352c68682b2 |
    | CDS microservizi ERP Microsoft Dynamics | 703e2651-d3fc-48f5-942c-74274233dba8 |
    | Servizio di autorizzazione di AI Builder         | ad40333e-9910-4b61-b281-e3aeeb8c3ef3 |

Se non riesci a trovare nessuna delle applicazioni precedenti, prova i seguenti passaggi.

1. Sul tuo computer locale, nel menu **Start**, cerca **powershell**.
2. Seleziona e tieni premuto (o fai clic con il pulsante destro del mouse su) **Windows PowerShell** e quindi seleziona **Esegui come amministratore**.
3. Esegui il comando seguente per installare il modulo **AzureAD**.

    `Install-Module -Name AzureAD`

4. Se è necessario un provider NuGet per continuare, seleziona **Y** per installarlo.
5. Se ricevi il messaggio "Repository non attendibile", seleziona **Y** per continuare.
6. Per ciascuna applicazione che deve essere aggiunta, esegui i seguenti comandi per aggiungere l'applicazione ad Azure AD. Quando ti viene richiesto, accedi come amministratore Azure AD.

    `Connect-AzureAD`

    `New-AzureADServicePrincipal –AppId <AppId>`

#### <a name="create-azure-resources"></a>Creare risorse Azure

> [!NOTE]
> Assicurati di creare le seguenti risorse nella stessa istanza di Azure AD in cui si trova l'ambiente Dataverse. Non puoi utilizzare risorse da un'altra istanza di Azure AD.

1. Crea un account di archiviazione:

    1. Nel [portale di Azure](https://portal.azure.com), crea un account di archiviazione.
    2. Nella finestra di dialogo **Crea account di archiviazione**, imposta i seguenti campi:

        - **Posizione**: seleziona il data center in cui si trova il tuo ambiente.
        - **Prestazioni**: è compatibile selezionare **Standard**.
        - **Tipo di account**: devi selezionare **StorageV2**.

    3. Nella finestra di dialogo **Opzioni avanzate**, per l'opzione **Data Lake Storage Gen2**, seleziona **Abilita** nella funzionalità **Spazi dei nomi gerarchici**. Se non abiliti questa funzionalità, non puoi utilizzare i dati che le app Finance and Operations scrivono utilizzando servizi come i flussi di dati di Power BI.
    4. Seleziona **Rivedi e crea**. Al termine della distribuzione, la nuova risorsa verrà visualizzata nel portale di Azure.
    5. Vai all'account di archiviazione che hai creato.
    6. Nel menu a sinistra, seleziona **Chiavi di accesso**.
    7. Copia e salva il nome il nome dell'account di archiviazione. Dovrai fornire questo valore in un secondo momento, quando configuri i segreti del Key Vault.

2. Crea un Key Vault:

    1. Nel [portale di Azure](https://portal.azure.com), crea un Key Vault.
    2. Nella finestra di dialogo **Crea Key Vault**, nel campo **Posizione**, seleziona il data center in cui si trova il tuo ambiente.
    3. Dopo aver creato il Key Vault, vai a **Panoramica di Key Vault**, quindi copia e salva il nome DNS. Dovrai fornire questo valore in un secondo momento, quando configuri il componente aggiuntivo Data Lake.

3. Crea e registra un'applicazione Azure AD:

    1. Nel [portale di Azure](https://portal.azure.com), passa ad **Azure Active Directory**, quindi seleziona **Registrazioni app**.
    2. Seleziona **Nuova registrazione dell'applicazione** e imposta i seguenti campi:

        - **Nome**: immetti il nome dell'app.
        - **Tipo di applicazione**: seleziona **API Web**.
        - **Configurazione URI reindirizzamento**: immetti l'URL per la tua istanza di Dynamics 365, ad esempio, `https://yourdynamicsinstance.dynamics.com/auth`.

    3. Vai all'app che hai appena creato e copia e salva il suo valore **ID applicazione (client)**. Dovrai fornire questo valore in un secondo momento, quando configuri i segreti del Key Vault.
    4. Vai ad **Autorizzazioni API** e segui questi passaggi:

        1. Seleziona **Aggiungi un'autorizzazione**.
        2. Seleziona **Azure Key Vault**.
        3. Dopo aver selezionato le autorizzazioni delegate, seleziona **utente\_impersonificazione**.
        4. Seleziona **Aggiungi autorizzazioni**.

    5. Nel menu dell'app, seleziona **Certificati \& segreti** e quindi segui questi passaggi per creare segreti di Key Vault:

        1. Seleziona **Nuovo segreto client**.
        2. Nel campo **Descrizione chiave** immetti un nome.
        3. Seleziona una durata e quindi seleziona **Aggiungi**. Un segreto viene generato nel campo **Valore**.
        4. Copia e salva il valore del segreto client. Dovrai fornire questo valore in un secondo momento, quando configuri i segreti del Key Vault.

4. Crea segreti Key Vault:

    1. Vai al Key Vault creato in precedenza e seleziona **Segreti**.
    2. Per ogni nome segreto nella tabella seguente, segui questi passaggi:

        1. Seleziona **Genera/Importa**.
        2. Nella finestra di dialogo **Crea un segreto**, nel campo **Opzioni di caricamento**, seleziona **Manuale**.
        3. Crea il nome e il valore del segreto dalla tabella.
        4. Seleziona **Abilitato** e quindi **Crea**. Il segreto viene creato e aggiunto al Key Vault.

        | Nome segreto                       | Valore segreto                                                                                 |
        |-----------------------------------|----------------------------------------------------------------------------------------------|
        | app-id                            | L'ID app dell'applicazione che hai creato in precedenza.                                      |
        | app-secret                        | Il segreto client che hai salvato in precedenza.                                                    |
        | storage-account-name              | Il nome dell'account di archiviazione creato in precedenza, ad esempio **storageaccount1**.       |

5. Autorizza l'applicazione ad accedere al Key Vault:

    1. Nel [portale di Azure](https://portal.azure.com), apri il Key Vault creato in precedenza.
    2. Seleziona i criteri di accesso.
    3. Per ogni applicazione nella tabella seguente, segui questi passaggi:

        1. Seleziona **Aggiungi criteri di accesso** per creare un criterio di accesso.
        2. Nel campo **Autorizzazioni segreto**, seleziona le autorizzazioni dalla tabella.
        3. Nel campo **Seleziona entità di sicurezza**, cerca il nome visualizzato dell'applicazione dalla tabella.
        4. Seleziona **Seleziona**.
        5. Seleziona **Aggiungi**.
        6. Seleziona **Salva**.

        | Applicazione                                              | Autorizzazioni |
        |----------------------------------------------------------|-------------|
        | Il nome visualizzato della nuova applicazione che hai creato | Get, List   |
        | **Microservizi ERP Microsoft Dynamics**                 | Get, List   |

6. Assegna ruoli per accedere all'account di archiviazione:

    1. Nel [portale di Azure](https://portal.azure.com), apri l'account di archiviazione creato in precedenza.
    2. Seleziona **Controllo dei diritti di accesso (IAM)** e quindi seleziona **Assegnazioni di ruolo**.
    3. Seleziona **Aggiungi, Aggiungi assegnazione di ruolo**.
    4. Per ogni applicazione nella tabella seguente, segui questi passaggi:

        1. Seleziona il ruolo dalla tabella.
        2. Lascia il campo **Assegna accesso a** impostato su **Utente, gruppo o entità servizio Azure AD**.
        3. Nel campo **Seleziona**, immetti l'applicazione dalla tabella.
        4. Selezionare **Salva**.

        | Domanda di lavoro                                              | Ruolo                        |
        |----------------------------------------------------------|-----------------------------|
        | Il nome visualizzato della nuova applicazione che hai creato | Proprietario                       |
        | Il nome visualizzato della nuova applicazione che hai creato | Collaboratore                 |
        | Il nome visualizzato della nuova applicazione che hai creato | Collaboratore account di archiviazione |
        | Il nome visualizzato della nuova applicazione che hai creato | Proprietario dei dati del BLOB di archiviazione     |
        | **Servizio di autorizzazione di AI Builder**                     | Lettore dati del BLOB di archiviazione    |

# <a name="azure-cli"></a>[Azure CLI](#tab/azure-azure-cli)

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

## <a name="configure-the-export-to-data-lake-add-in"></a>Configurare l'esportazione nel componente aggiuntivo Data Lake

Segui questi passaggi per utilizzare LCS per aggiungere il componente aggiuntivo Esporta in Data Lake all'ambiente.

1. Accedi a LCS, quindi, sotto il nome dell'ambiente sul lato destro della pagina, seleziona **Dettagli completi**.
2. Nella sezione **Componenti aggiuntivi per l'ambiente**, selezionare **Installa un nuovo componente aggiuntivo**.
3. Seleziona il componente aggiunti **Esporta in Data Lake**.
4. Immetti i valori seguenti.

    | Valore                                                              | Descrizione |
    |--------------------------------------------------------------------|-------------|
    | ID tenant della sottoscrizione di Azure in cui si trova il Key Vault | L'ID tenant in cui si trovano l'account di archiviazione, le app e i Key Vault. Per ottenere questo valore, apri il [portale di Azure](https://portal.azure.com), vai ad **Azure Active Directory** e copia il valore **ID tenant**. |
    | Specificare il nome DNS del Key Vault                             | Il nome DNS del Key Vault, ad esempio `https://customkeyvault.vault.azure.net/`. |
    | Fornire il segreto contenente il nome dell'account di archiviazione   | **storage-account-name** |
    | Nome segreto per l'ID app da utilizzare per accedere al data lake          | **app-id** |
    | Nome del segreto per il segreto del client dell'app                                  | **app-secret** |

5. Accetta le condizioni e seleziona **Installa**.

Il componente aggiuntivo verrà installato in pochi minuti.

## <a name="configure-the-finance-insights-add-in"></a>Configurare il componente aggiuntivo Finance Insights

> [!NOTE]
> Se in precedenza hai installato il componente aggiuntivo Ottieni informazioni dettagliate, disinstallalo prima di completare la procedura seguente.

Segui questi passaggi per installare il componente aggiuntivo Finance Insights.

1. Accedi a LCS, quindi, sotto il nome dell'ambiente sul lato destro della pagina, seleziona **Dettagli completi**.
2. Nella sezione **Componenti aggiuntivi per l'ambiente**, selezionare **Installa un nuovo componente aggiuntivo**.
3. Seleziona il componente aggiuntivo **Finance Insights**.
4. Accetta le condizioni e seleziona **Installa**.

## <a name="feedback-and-support"></a>Feedback e supporto

Se vuoi fornire un feedback o hai bisogno di supporto, invia un'e-mail a [Finance Insights (anteprima)](mailto:fiap@microsoft.com).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
