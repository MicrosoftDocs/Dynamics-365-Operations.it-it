---
title: Distribuire unità di scala nella rete perimetrale su hardware personalizzato utilizzando LBD
description: Questo argomento spiega come eseguire il provisioning di unità di scala edge locali utilizzando hardware personalizzato e distribuzione basata su dati aziendali locali (LBD).
author: cabeln
ms.date: 11/29/2021
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: cabeln
ms.search.validFrom: 2021-04-13
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 8913debd614827ef66ded88e0da61663ca9c6b3d
ms.sourcegitcommit: 29d34f2fd509e2bb27d8572cd57c397d014a8e38
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/07/2021
ms.locfileid: "7894720"
---
# <a name="deploy-edge-scale-units-on-custom-hardware-using-lbd"></a>Distribuire unità di scala nella rete perimetrale su hardware personalizzato utilizzando LBD

[!include [banner](../includes/banner.md)]

Le unità di scala edge svolgono un ruolo importante nella topologia ibrida distribuita per la gestione della supply chain. Nella topologia ibrida puoi distribuire i carichi di lavoro tra il tuo hub cloud di Supply Chain Management e unità di scala aggiuntive nel cloud o sull'edge.

Le unità di scala edge possono essere implementate creando dati aziendali locale(LBD) [ambiente locale](../../fin-ops-core/dev-itpro/deployment/on-premises-deployment-landing-page.md) e quindi configurandolo per operare come un'unità di scala nella topologia ibrida distribuita per la gestione della supply chain. Ciò si ottiene associando l'ambiente LBD locale con un ambiente Supply Chain Management nel cloud, che è stato configurato per funzionare come hub.  

Questo argomento descrive come configurare un ambiente LBD locale come unità di scala edge e quindi associarlo a un hub.

## <a name="deployment-overview"></a>Panoramica distribuzione

Ecco una panoramica del processo di distribuzione.

1. **Abilita uno slot LBD nel tuo progetto LBD in Microsoft Dynamics Lifecycle Services (LCS).**

1. **Configura e distribuisci un ambiente LBD con un database *vuoto*.**

    Usa LCS per distribuire l'ambiente LBD con la topologia più recente e un database vuoto. Per ulteriori informazioni, vedi la sezione [Configura e distribuisci un ambiente LBD con database vuoto](#set-up-deploy) più avanti in questo argomento. È necessario utilizzare Supply Chain Management versione 10.0.21 o successive nell'hub e negli ambienti di unità di scala.

1. **Carica i pacchetti di destinazione nelle risorse del progetto LBD in LCS.**

    Preparare pacchetti di applicazioni, piattaforme e personalizzazione da utilizzare nell'hub e nell'unità di scala edge. Per ulteriori informazioni, vedi la sezione [Carica i pacchetti di destinazione nelle risorse del progetto LBD in LCS](#upload-packages) più avanti in questo argomento.

1. **Assistenza nell'ambiente LBD con i pacchetti di destinazione.**

    Questo passaggio garantisce che la stessa build e le stesse personalizzazioni vengano distribuite nell'hub e nello spoke. Per ulteriori informazioni, vedi la sezione [Assistenza nell'ambiente LBD con i pacchetti di destinazione](#service-target-packages) più avanti in questo argomento.

1. **Completa la configurazione dell'unità di scala e l'assegnazione del carico di lavoro.**

    Per ulteriori informazioni, vedi la sezione [Assegna la tua unità di scala edge LBD a un hub](#assign-edge-to-hub) più avanti in questo argomento.

Le altre sezioni di questo argomento forniscono ulteriori dettagli su come completare questi passaggi.

## <a name="set-up-and-deploy-an-lbd-environment-with-an-empty-database"></a><a name="set-up-deploy"></a>Configura e distribuisci un ambiente LBD con un database vuoto

Questo passaggio crea un ambiente LBD funzionale. Tuttavia, l'ambiente non ha necessariamente le stesse versioni dell'applicazione e della piattaforma dell'ambiente hub. Inoltre, mancano ancora le personalizzazioni e non è ancora stato abilitato per funzionare come unità di scala.

1. Segui le istruzioni in [Impostare e distribuire gli ambienti locali (Platform update 41 e successivi)](../../fin-ops-core/dev-itpro/deployment/setup-deploy-on-premises-pu41.md). È necessario utilizzare Supply Chain Management versione 10.0.21 o successive nell'hub e negli ambienti di unità di scala. Inoltre, è necessario utilizzare la versione 2.12.0 o successiva degli script di infrastruttura. 

    > [!IMPORTANT]
    > Leggi il resto di questa sezione **prima** di completare i passaggi in quell'argomento.

1. Prima di descrivere la configurazione nell'infrastruttura\\File ConfigTemplate.xml, esegui il seguente script:

    ```powershell
    .\Configure-ScriptsForEdgeScaleUnits.ps1 -ConfigurationFilePath .\ConfigTemplate.xml
    ```

    > [!NOTE]
    > Questo script rimuoverà qualsiasi configurazione non necessaria per la distribuzione di unità di scala edge.

1. Configura un database che contenga dati vuoti, come descritto in [Configura database](../../fin-ops-core/dev-itpro/deployment/setup-deploy-on-premises-pu41.md#configuredb). Utilizza il file data.bak vuoto per questo passaggio.
1. Dopo aver completato il passaggio [Configura database](../../fin-ops-core/dev-itpro/deployment/setup-deploy-on-premises-pu41.md#configuredb), esegui il seguente script per configurare il database Scale Unit Alm Orchestrator.

    > [!NOTE]
    > Non configurare il database di Financial Reporting durante il passaggio [Configura database](../../fin-ops-core/dev-itpro/deployment/setup-deploy-on-premises-pu41.md#configuredb).

    ```powershell
    .\Initialize-Database.ps1 -ConfigurationFilePath .\ConfigTemplate.xml -ComponentName EdgeScaleUnit
    ```

    Lo script Initialize-Database.ps1 esegue le seguenti azioni:

    1. Crea un database vuoto chiamato **ScaleUnitAlmDb**.
    2. Esegui il mapping degli utenti ai ruoli del database, in base alla tabella seguente.

        | Utente            | Tipo | Ruolo di database |
        |-----------------|------|---------------|
        | svc-LocalAgent$ | gMSA | db\_owner     |

1. Continua a seguire le istruzioni in [Impostare e distribuire gli ambienti locali (Platform update 41 e successivi)](../../fin-ops-core/dev-itpro/deployment/setup-deploy-on-premises-pu41.md).
1. Dopo aver completato il passaggio [Configura AD FS](../../fin-ops-core/dev-itpro/deployment/setup-deploy-on-premises-pu41.md#configuredb), segui questi passaggi:

    1. Crea una nuova applicazione Active Directory Federation Services (AD FS) che consentirà al servizio Alm Orchestration di comunicare con il tuo Application Object Server (AOS).

        ```powershell
        # Host URL is your DNS record\host name for accessing the AOS
        .\Create-ADFSServerApplicationForEdgeScaleUnits.ps1 -ConfigurationFilePath .\ConfigTemplate.xml -HostUrl 'https://ax.d365ffo.onprem.contoso.com'
        ```

    1. Crea una nuova applicazione Azure Active Directory (Azure AD) che consentirà al servizio Alm Orchestration di comunicare con il servizio Scale Unit Management.

        ```powershell
        # Example .\Create-SumAADApplication.ps1 -ConfigurationFilePath ..\ConfigTemplate.xml -TenantId '6240a19e-86f1-41af-91ab-dbe29dbcfb95' -ApplicationDisplayName 'EdgeAgent-SUMCommunication-EN01'
        .\Create-SumAADApplication.ps1 -ConfigurationFilePath '<Path of the ConfigTemplate.xml file>' `
                                       -TenantId '<ID of the tenant where your cloud hub is deployed>' `
                                       -ApplicationDisplayName '<Whichever name you want the Azure AD app to have>'
        ```

1. Continua a seguire le istruzioni in [Impostare e distribuire gli ambienti locali (Platform update 41 e successivi)](../../fin-ops-core/dev-itpro/deployment/setup-deploy-on-premises-pu41.md). Quando devi immettere la configurazione per l'agente locale, assicurati di abilitare le funzionalità di Edge Scale Unit e di fornire tutti i parametri richiesti.

    ![Abilitazione delle funzionalità Edge Scale Unit.](media/EnableEdgeScaleUnitFeatures.png "Abilitazione delle funzionalità Edge Scale Unit.")

1. Prima di distribuire il tuo ambiente da LCS, imposta lo script di pre-distribuzione. Per ulteriori informazioni, vedi [Script agente locale pre-distribuzione e post-distribuzione](../../fin-ops-core/dev-itpro/lifecycle-services/pre-post-scripts.md).

    1. Copia lo script Configure-CloudAndEdge.ps1 dalla cartella **ScaleUnit** in **Script di infrastruttura** nella cartella **Script** nella condivisione di archiviazione file dell'agente configurata nell'ambiente. Un percorso tipico è \\\\lbdiscsi01\\agente\\Script.
    2. Crea lo script **PreDeployment.ps1** che richiamerà gli script utilizzando i parametri richiesti. Lo script pre-distribuzione deve essere inserito nella cartella **Script** nella condivisione di archiviazione file dell'agente. In caso contrario, non può essere eseguito. Un percorso tipico è \\\\lbdiscsi01\\agent\\Scripts\\PreDeployment.ps1.

        Il contenuto dello script PreDeployment.ps1 sarà simile all'esempio seguente.

        ```powershell
        $agentShare = '\\lbdiscsi01\agent'
        
        Write-Output "AgentShare is set to $agentShare" 
        . $PSScriptRoot\Configure-CloudAndEdge.ps1 -AgentShare $agentShare -InstanceId '@A'
        ```

        > [!NOTE]
        > Il parametro InstanceId deve contenere solo due caratteri. Il primo carattere è @ e il secondo può essere qualsiasi lettera maiuscola dell'alfabeto inglese.
        >
        > - Valori validi:
        >   - @D
        >   - @X
        > - Valori non validi:
        >   - @a
        >   - @4
        >   - @#

1. Distribuire l'ambiente utilizzando la topologia di base più recente disponibile.
1. Dopo aver distribuito l'ambiente, segui questi passaggi:

    1. Esegui i seguenti comandi SQL sul tuo database aziendale (AXDB).

        ```sql
        ALTER TABLE dbo.NUMBERSEQUENCETABLE ENABLE CHANGE_TRACKING WITH (TRACK_COLUMNS_UPDATED = ON)
        delete from NumberSequenceTable
        delete from NumberSequenceReference
        delete from NumberSequenceScope
        delete from FeatureManagementMetadata
        delete from FeatureManagementState
        delete from SysFeatureStateV0
        ```

    1. Aumenta la sessione batch massima simultanea a un valore maggiore di 4.

        ```sql
        Update batchserverconfig set maxbatchsessions = '<Replace with number of concurrent batch tasks you want>'
        ```

    1. Verifica che il rilevamento delle modifiche sia stato abilitato sul database aziendale (AXDB).

        1. Apri SQL Server Management Studio (SSMS).
        1. Seleziona e tieni premuto (o fai clic con il tasto destro del mouse) sul database aziendale (AXDB), quindi seleziona **Proprietà**.
        1. Nella finestra che viene visualizzata, seleziona **Rilevamento modifiche** e imposta i valori seguenti:

            - **Rilevamento modifiche:** *True*
            - **Periodo di conservazione:** *7*
            - **Unità di conservazione:** *Giorni*
            - **Pulizia automatica:** *True*

    1. Aggiungi l'ID dell'applicazione AD FS creato in precedenza (usando lo script Create-ADFSServerApplicationForEdgeScaleUnits.ps1) alla tabella delle applicazioni Azure AD nell'unità di scala. Puoi completare manualmente questo passaggio tramite l'interfaccia utente (UI). In alternativa, puoi completarlo tramite il database utilizzando il seguente script.

        ```sql
        DECLARE @ALMOrchestratorId NVARCHAR(76) = '<Replace with the ADFS Application ID created in a previous step>';

        IF NOT EXISTS (SELECT TOP 1 1 FROM SysAADClientTable WHERE AADClientId = @ALMOrchestratorId)
        BEGIN
            INSERT INTO SysAADClientTable (AADClientId, UserId, Name, ModifiedBy, CreatedBy)
            VALUES (@ALMOrchestratorId, 'ScaleUnitManagement', 'Scale Unit Management', 'Admin', 'Admin');
        END
        ```

## <a name="set-up-an-azure-key-vault-and-an-azure-ad-application-to-enable-communication-between-scale-units"></a><a name="set-up-keyvault"></a>Configurare un Azure Key Vault e un'applicazione Azure AD per consentire la comunicazione tra le unità di scala

1. Dopo che il tuo ambiente è stato distribuito, crea un'altra applicazione Azure AD per consentire una comunicazione affidabile tra l'hub e l'unità di scala.

    ```powershell
    .\Create-SpokeToHubAADApplication.ps1 -ConfigurationFilePath '<Path of the ConfigTemplate.xml file>' `
                                          -TenantId '<ID of the tenant where your cloud hub is deployed>' `
                                          -ApplicationDisplayName '<Whichever name you want the Azure AD app to have>'
    ```

1. Dopo aver creato l'applicazione, devi creare un segreto client e salvare le informazioni in un Azure Key Vault. Inoltre, devi concedere l'accesso all'applicazione Azure AD creata, in modo che possa recuperare i segreti archiviati nel Key Vault. Per tua comodità, il seguente script eseguirà automaticamente tutte le azioni richieste.

    ```powershell
    .\Create-SpokeToHubAADAppSecrets.ps1 -ConfigurationFilePath '<Path of the ConfigTemplate.xml file>' `
                                         -TenantId '<ID of the tenant where your cloud hub is deployed>' `
                                         -SubscriptionName '<Any subscription within your tenant>' `
                                         -ResourceGroupName '<Any resource group within your subscription>' `
                                         -KeyVaultName '<Any key vault within your resource group>' `
                                         -Location '<Any Azure location where Azure Key Vault is available>' `
                                         -LCSEnvironmentId '<The LCS environment ID of your deployed scale unit>' `
    ```

    > [!NOTE]
    > Se nessun esiste alcun Key Vault con il valore **KeyVaultName** specificato, lo script ne crea automaticamente uno.

1. Aggiungi l'ID applicazione Azure AD appena creato (quando si utilizza lo script Create-SpokeToHubAADApplication.ps1) alla tabella delle applicazioni Azure AD nel tuo hub. Puoi completare manualmente questo passaggio tramite l'interfaccia utente.

## <a name="upload-target-packages-into-lbd-project-assets-in-lcs"></a><a name="upload-packages"></a>Caricare i pacchetti di destinazione nelle risorse del progetto LBD in LCS

Questo passaggio prepara la versione dell'applicazione, la versione della piattaforma e le personalizzazioni che verranno trasferite all'ambiente dell'unità di scala LBD.

1. Carica lo stesso pacchetto applicazione/piattaforma combinato che è stato applicato all'ambiente hub nella libreria di risorse del progetto LCS locale.
1. Ottieni una copia del pacchetto distribuibile personalizzato che è stato applicato all'ambiente hub e caricalo nella libreria di risorse del progetto LCS locale.

## <a name="service-the-lbd-environment-with-target-packages"></a><a name="service-target-packages"></a>Assistenza nell'ambiente LBD con i pacchetti di destinazione

Questo passaggio allinea la versione dell'applicazione, la versione della piattaforma e le personalizzazioni all'ambiente dell'unità di scala LBD con l'hub.

1. Fornisci supporto per l'ambiente LBD con il pacchetto applicazione/piattaforma combinato che hai caricato nel passaggio precedente.
1. Fornisci supporto per l'ambiente LBD con il pacchetto distribuibile personalizzato che hai caricato nel passaggio precedente.

    ![Applicazione degli aggiornamenti in LCS.](media/cloud_edge-LBD-LCS-ServiceLBDEnv1.png "Applicazione degli aggiornamenti in LCS")

    ![Selezione del pacchetto di personalizzazione.](media/cloud_edge-LBD-LCS-ServiceLBDEnv2.png "Selezione del pacchetto di personalizzazione")

## <a name="assign-your-lbd-edge-scale-unit-to-a-hub"></a><a name="assign-edge-to-hub"></a>Assegna la tua unità di scala edge LBD a un hub

Configura e gestisci la tua unità di scala perimetrale tramite il portale di gestione delle unità di scala. Per altre informazioni, vedi [Gestire unità di scala e carichi di lavoro utilizzando il portale di gestione delle unità di scala](./cloud-edge-landing-page.md#scale-unit-manager-portal).

[!INCLUDE [cloud-edge-privacy-notice](../../includes/cloud-edge-privacy-notice.md)]

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
