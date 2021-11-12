---
title: Distribuire unità di scala nella rete perimetrale su hardware personalizzato utilizzando LBD (Anteprima)
description: Questo argomento spiega come eseguire il provisioning di unità di scala edge locali utilizzando hardware personalizzato e distribuzione basata su dati aziendali locali (LBD).
author: cabeln
ms.date: 04/22/2021
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: cabeln
ms.search.validFrom: 2021-04-13
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 0ebbdaab9d6f040497d3158db2712e102b6e9aa8
ms.sourcegitcommit: 1e5a46271bf7fae2f958d2b1b666a8d2583e04a8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/25/2021
ms.locfileid: "7678983"
---
# <a name="deploy-edge-scale-units-on-custom-hardware-using-lbd-preview"></a>Distribuire unità di scala nella rete perimetrale su hardware personalizzato utilizzando LBD (Anteprima)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)] <!--KFM: Until 11/1/2021 -->

Le unità di scala edge svolgono un ruolo importante nella topologia ibrida distribuita per la gestione della supply chain. Nella topologia ibrida puoi distribuire i carichi di lavoro tra il tuo hub cloud di Supply Chain Management e unità di scala aggiuntive nel cloud o sull'edge.

Le unità di scala edge possono essere implementate creando dati aziendali locale(LBD) [ambiente locale](../../fin-ops-core/dev-itpro/deployment/on-premises-deployment-landing-page.md) e quindi configurandolo per operare come un'unità di scala nella topologia ibrida distribuita per la gestione della supply chain. Ciò si ottiene associando l'ambiente LBD locale con un ambiente Supply Chain Management nel cloud, che è stato configurato per funzionare come hub.  

Le unità di scala edge sono attualmente in anteprima. Pertanto, è possibile utilizzare un ambiente di questo tipo solo in base ai [termini di anteprima](https://aka.ms/scmcnepreviewterms).

Questo argomento descrive come configurare un ambiente LBD locale come unità di scala edge e quindi associarlo a un hub.

## <a name="deployment-overview"></a>Panoramica distribuzione

Ecco una panoramica del processo di distribuzione.

1. **Abilita uno slot LBD nel tuo progetto LBD in Microsoft Dynamics Lifecycle Services (LCS).**

    Durante l'anteprima, le unità di scala edge LBD si rivolgono ai clienti LBD esistenti. Uno slot sandbox LBD aggiuntivo di 60 giorni verrà fornito solo in situazioni specifiche del cliente.

1. **Configura e distribuisci un ambiente LBD con un database *vuoto*.**

    Usa LCS per distribuire l'ambiente LBD con la topologia più recente e un database vuoto. Per ulteriori informazioni, vedi la sezione [Configura e distribuisci un ambiente LBD con database vuoto](#set-up-deploy) più avanti in questo argomento. È necessario utilizzare Supply Chain Management versione 10.0.19 con l'aggiornamento della piattaforma 43 o successivo nell'hub e negli ambienti di unità di scala.

1. **Carica i pacchetti di destinazione nelle risorse del progetto LBD in LCS.**

    Preparare pacchetti di applicazioni, piattaforme e personalizzazione da utilizzare nell'hub e nell'unità di scala edge. Per ulteriori informazioni, vedi la sezione [Carica i pacchetti di destinazione nelle risorse del progetto LBD in LCS](#upload-packages) più avanti in questo argomento.

1. **Assistenza nell'ambiente LBD con i pacchetti di destinazione.**

    Questo passaggio garantisce che la stessa build e le stesse personalizzazioni vengano distribuite nell'hub e nello spoke. Per ulteriori informazioni, vedi la sezione [Assistenza nell'ambiente LBD con i pacchetti di destinazione](#service-target-packages) più avanti in questo argomento.

1. **Completa la configurazione dell'unità di scala e l'assegnazione del carico di lavoro.**

    Per ulteriori informazioni, vedi la sezione [Assegna la tua unità di scala edge LBD a un hub](#assign-edge-to-hub) più avanti in questo argomento.

Le altre sezioni di questo argomento forniscono ulteriori dettagli su come completare questi passaggi.

## <a name="set-up-and-deploy-an-lbd-environment-with-an-empty-database"></a><a name="set-up-deploy"></a>Configura e distribuisci un ambiente LBD con un database vuoto

Questo passaggio crea un ambiente LBD funzionale. Tuttavia, l'ambiente non ha necessariamente le stesse versioni dell'applicazione e della piattaforma dell'ambiente hub. Inoltre, mancano ancora le personalizzazioni e non è ancora stato abilitato per funzionare come unità di scala.

1. Segui le istruzioni in [Impostare e distribuire gli ambienti locali (Platform update 41 e successivi)](../../fin-ops-core/dev-itpro/deployment/setup-deploy-on-premises-pu41.md). Devi utilizzare Supply Chain Management versione 10.0.19 con l'aggiornamento della piattaforma 43 o successivo nell'hub e negli ambienti di unità di scala

    > [!IMPORTANT]
    > Leggi il resto di questa sezione **prima** di completare i passaggi in quell'argomento.

1. Prima di descrivere la configurazione nell'infrastruttura\\File ConfigTemplate.xml, esegui il seguente script:

    ```powershell
    .\Configure-ScriptsForEdgeScaleUnits.ps1 -ConfigurationFilePath .\ConfigTemplate.xml
    ```

    > [!NOTE]
    > Questo script rimuoverà qualsiasi configurazione non necessaria per la distribuzione di unità di scala edge.

1. Configura un database che contenga dati vuoti, come descritto in [Configura database](../../fin-ops-core/dev-itpro/deployment/setup-deploy-on-premises-pu41.md#configuredb). Utilizza il file data.bak vuoto per questo passaggio.
1. Imposta lo script pre-distribuzione. Per ulteriori informazioni, vedi [Script agente locale pre-distribuzione e post-distribuzione](../../fin-ops-core/dev-itpro/lifecycle-services/pre-post-scripts.md).

    1. Copia il contenuto dalla cartella **ScaleUnit** in **Script di infrastruttura** nella cartella **Script** nella condivisione di archiviazione file dell'agente configurata nell'ambiente. Un percorso tipico è \\\\lbdiscsi01\\agente\\Script.
    2. Crea lo script **PreDeployment.ps1** che richiamerà gli script utilizzando i parametri richiesti. Lo script pre-distribuzione deve essere inserito nella cartella **Script** nella condivisione di archiviazione file dell'agente. In caso contrario, non può essere eseguito. Un percorso tipico è \\\\lbdiscsi01\\agent\\Scripts\\PreDeployment.ps1.

        Il contenuto dello script PreDeployment.ps1 sarà simile all'esempio seguente.

        ```powershell
        $agentShare = '\\lbdiscsi01\agent'
        
        Write-Output "AgentShare is set to $agentShare" 
        & $agentShare\Scripts\Configure-CloudandEdge.ps1 -AgentShare $agentShare -InstanceId '@A' -DatabaseServer 'lbdsqla01.contoso.com' -DatabaseName 'AXDB'
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

## <a name="upload-target-packages-into-lbd-project-assets-in-lcs"></a><a name="upload-packages"></a>Caricare i pacchetti di destinazione nelle risorse del progetto LBD in LCS

Questo passaggio prepara la versione dell'applicazione, la versione della piattaforma e le personalizzazioni che verranno trasferite all'ambiente dell'unità di scala LBD.

1. Carica lo stesso pacchetto applicazione/piattaforma combinato che è stato applicato all'ambiente hub nella libreria di risorse del progetto LCS locale.
1. Ottieni una copia del pacchetto distribuibile personalizzato che è stato applicato all'ambiente hub e caricalo nella libreria di risorse del progetto LCS locale.

## <a name="service-the-lbd-environment-with-target-packages"></a><a name="service-target-packages"></a>Assistenza nell'ambiente LBD con i pacchetti di destinazione

Questo passaggio allinea la versione dell'applicazione, la versione della piattaforma e le personalizzazioni all'ambiente dell'unità di scala LBD con l'hub.

1. Fornisci supporto per l'ambiente LBD con il pacchetto applicazione/piattaforma combinato che hai caricato nel passaggio precedente.
1. Fornisci supporto per l'ambiente LBD con il pacchetto distribuibile personalizzato che hai caricato nel passaggio precedente.

    ![Selezione di Mantieni > Applica aggiornamenti in LCS.](media/cloud_edge-LBD-LCS-ServiceLBDEnv1.png "Selezione di Mantieni > Applica aggiornamenti in LCS")

    ![Selezione del pacchetto di personalizzazione.](media/cloud_edge-LBD-LCS-ServiceLBDEnv2.png "Selezione del pacchetto di personalizzazione")

## <a name="assign-your-lbd-edge-scale-unit-to-a-hub"></a><a name="assign-edge-to-hub"></a>Assegna la tua unità di scala edge LBD a un hub

Mentre le unità di scala edge sono ancora in anteprima, è necessario utilizzare gli [strumenti di configurazione e distribuzione delle unità di scala](https://github.com/microsoft/SCMScaleUnitDevTools) che sono disponibili su GitHub per assegnare l'unità di scala edge LBD a un hub. Il processo consente a una configurazione LBD di funzionare come unità di scala edge e la associa all'hub. Il processo è simile alla configurazione di un ambiente di sviluppo one-box.

1. Scarica l'ultima versione di [SCMScaleUnitDevTools](https://github.com/microsoft/SCMScaleUnitDevTools/releases) e decomprimi il contenuto del file.
1. Crea una copia del file `UserConfig.sample.xml` e nominalo `UserConfig.xml`.
1. Crea un'applicaizone Microsoft Azure Active Directory (Azure AD) nel tuo tenant Azure AD, come menzionato in [Guida alla distribuzione per unità di scala e carichi di lavoro](https://github.com/microsoft/SCMScaleUnitDevTools/wiki/Step-by-step-usage-guide#aad-application-registrations).
    1. Una volta creato, vai al modulo delle applicazioni Azure AD (SysAADClientTable) sull'hub.
    1. Crea una nuova voce e imposta l'**ID del client** sull'ID dell'applicazione creata. Impostare **Nome** su *ScaleUnits* e **ID utente** su *Amministratore*.

1. Creare un'applicazione Active Directory Federation Service (AD FS) come indicato in [Guida alla distribuzione per unità di scala e carichi di lavoro](https://github.com/microsoft/SCMScaleUnitDevTools/wiki/Step-by-step-usage-guide#adfs-application-registrations).
    1. Una volta creato, vai al modulo delle applicazioni Azure AD (SysAADClientTable) sull'unità di scala edge.
    1. Crea una nuova voce e imposta l'**ID del client** sull'ID dell'applicazione creata. Impostare **ID utente** su *Amministratore*.

1. Modifica il file `UserConfig.xml`.
    1. Nella sezione `InterAOSAADConfiguration`, inserire le informazioni dall'applicazione Azure AD creata in precedenza.
        - Nell'elemento `AppId`, immettere l'ID applicazione dell'applicazione Azure.
        - Nell'elemento `AppSecret`, immetti il segreto applicazione dell'applicazione Azure.
        - L'elemento `Authority` deve contenere l'URL che specifica l'autorità di sicurezza per il tenant.

        ```xml
        <InterAOSAADConfiguration>
            <AppId>8dab14f6-97b1-48e3-b51b-350b45f6ede5</AppId>
            <AppSecret>k6em-_7.lopty56TGUedDTVhtER-j_6anY1</AppSecret>
            <Authority>https://login.windows.net/contoso.onmicrosoft.com</Authority>
        </InterAOSAADConfiguration>
        ```

    1. Nella sezione `ScaleUnitConfiguration`, per la prima `ScaleUnitInstance`, modifica la sezione `AuthConfiguration`.
        - Nell'elemento `AppId`, immettere l'ID applicazione dell'applicazione Azure.
        - Nell'elemento `AppSecret`, immetti il segreto applicazione dell'applicazione Azure.
        - L'elemento `Authority` deve contenere l'URL che specifica l'autorità di sicurezza per il tenant.

        ```xml
        <AuthConfiguration>
            <AppId>8dab14f6-97b1-48e3-b51b-350b45f6ede5</AppId>
            <AppSecret>k6em-_7.lopdz.6d3DTVOtf9Lo-j_6anY1</AppSecret>
            <Authority>https://login.windows.net/contoso.onmicrosoft.com</Authority>
        </AuthConfiguration>
        ```

    1. Inoltre, per questa stessa `ScaleUnitInstance`, impostare i seguenti valori:
        - Nell'elemento `Domain`, specifica l'URL del tuo hub. Ad esempio: `https://cloudhub.sandbox.operations.dynamics.com/`
        - Nell'elemento `EnvironmentType`, verificare che il valore `LCSHosted` sia impostato.

    1. Nella sezione `ScaleUnitConfiguration`, per la seconda `ScaleUnitInstance`, modifica la sezione `AuthConfiguration`.
        - Nell'elemento `AppId`, immettere l'ID applicazione dell'applicazione AD FS.
        - Nell'elemento `AppSecret`, immetti il segreto applicazione dell'applicazione ADFS.
        - L'elemento `Authority` deve contenere l'URL dell'istanza di AD FS.

        ```xml
        <AuthConfiguration>
            <AppId>26b16f25-21d8-4d36-987b-62df292895aa</AppId>
            <AppSecret>iZFfObgI6lLtY9kEbBjEFV98NqI5_YZ0e5SBcWER</AppSecret>
            <Authority>https://adfs.contoso.com/adfs</Authority>
        </AuthConfiguration>
        ```

    1. Inoltre, per questa stessa `ScaleUnitInstance`, impostare i seguenti valori:
        - Nell'elemento `Domain`, specifica l'URL della tua unità di scala edge. Ad esempio: https://ax.contoso.com/
        - Nell'elemento `EnvironmentType`, verificare che il valore LBD sia impostato.
        - Nell'elemento `ScaleUnitId`, inserisci lo stesso valore che hai specificato per `InstanceId` durante la configurazione dello script `Configure-CloudandEdge.ps1` pre-distribuzione.

        > [!NOTE]
        > Se non usi l'ID predefinito (@A), assicurati di aggiornare ScaleUnitId per ogni ConfiguredWorkload nella sezione Carichi di lavoro.

1. Apri PowerShell e vai alla cartella contenente il file `UserConfig.xml`.

1. Esegui lo strumento con questo comando.

    ```powershell
    .\CLI.exe
    ```

    > [!NOTE]
    > Dopo ogni azione dovrai riavviare lo strumento.

1. Nello strumento, seleziona **2. Preparare gli ambienti per l'installazione del carico di lavoro**. Quindi eseguire i seguenti passaggi:
    1. Seleziona **1. Prepara l'hub**.
    1. Seleziona **2. Prepara l'unità di scala**.

    > [!NOTE]
    > Se non stai eseguendo questo comando da un'installazione pulita e non riesce, esegui le seguenti azioni:
    >
    > - Rimuovi tutte le cartelle dalla cartella `aos-storage` (tranne per `GACAssemblies`).
    > - Esegui il seguente comando SQL sul tuo database aziendale (AXDB):
    >
    > ```sql 
    > delete from storagefoler
    > ```

1. Esegui i seguenti comandi SQL sul tuo database aziendale (AXDB):

    ```sql
    delete from FEATUREMANAGEMENTMETADATA
    delete from FEATUREMANAGEMENTSTATE
    delete from NUMBERSEQUENCESCOPE
    ```

1. Verifica che il rilevamento delle modifiche sia stato abilitato sul database aziendale (AXDB)
    1. Avvia SQL Server Management Studio (SSMS).
    1. Fai clic con il pulsante destro del mouse sul database aziendale (AXDB) e seleziona proprietà.
    1. Nella finestra che si apre, seleziona **Rilevamento modifiche** ed effettua le seguenti impostazioni:

        - **Rilevamento modifiche:** *True*
        - **Periodo di conservazione:** *7*
        - **Unità di conservazione:** *Giorni*
        - **Pulizia automatica:** *True*

1. Nello strumento, seleziona **3. Installa i carichi di lavoro**. Quindi eseguire i seguenti passaggi:
    1. Seleziona **1. Installa su Hub**.
    1. Seleziona **2. Installa su bilancia**.

[!INCLUDE [cloud-edge-privacy-notice](../../includes/cloud-edge-privacy-notice.md)]

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
