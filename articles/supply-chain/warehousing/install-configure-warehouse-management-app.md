---
title: Installare e connettere l'app per dispositivi mobili Gestione magazzino
description: Questo argomento spiega come installare l'app per dispositivi mobili Gestione magazzino su ciascuno dei tuoi dispositivi mobili e come configurarla affinché si connetta all'ambiente Microsoft Dynamics 365 Supply Chain Management.
author: MarkusFogelberg
ms.date: 02/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SysAADClientTable, WHSMobileAppField, WHSMobileAppFieldPriority, WHSRFMenu, WHSRFMenuItem, WHSWorker
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.custom: 267694
ms.assetid: d95d43b2-13ff-4189-a71a-3a1fb57d55ed
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: mafoge
ms.search.validFrom: 2021-02-28
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 5aa67673fe05394f498d0844b8e58ba6f0ec1d85
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/06/2021
ms.locfileid: "6346084"
---
# <a name="install-and-connect-the-warehouse-management-mobile-app"></a>Installare e connettere l'app per dispositivi mobili Gestione magazzino

[!include [banner](../includes/banner.md)]

> [!NOTE]
> In questo argomento viene descritto come configurare la nuova app per dispositivi mobili Gestione magazzino. Se stai cercando informazioni su come configurare la vecchia app per il magazzino (ora deprecata), vedi [Installare e connettere l'app del magazzino](../../supply-chain/warehousing/install-configure-warehousing-app.md).

In questo argomento viene descritto come scaricare e installare l'app per dispositivi mobili Gestione magazzino in ciascuno dei tuoi dispositivi mobili e come configurarla per connetterla all'ambiente Supply Chain Management. Puoi configurare manualmente ciascun dispositivo oppure importare le impostazioni di connessione tramite un file o scansionando un codice QR.

## <a name="system-requirements"></a>Requisiti di sistema

L'app per dispositivi mobili Gestione magazzino è disponibile per i sistemi operativi Windows e Google Android. Per utilizzare l'app, uno dei sistemi operativi seguenti deve essere installato sui dispositivi mobili:

- Windows 10 (Universal Windows Platform \[UWP\]) ottobre 2018 aggiornamento 1809 (build 10.0.17763) o versione successiva
- Android 4.4 o versione successiva

## <a name="turn-on-the-feature"></a>Attivare la funzionalità

Prima di poter utilizzare l'app, è necessario attivare una funzionalità correlata nel sistema. Gli amministratori possono utilizzare l'area di lavoro [Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) per controllare lo stato della funzionalità e attivarla se necessario. Nell'area di lavoro, la funzionalità è elencata nel modo seguente:

- **Modulo:** *Gestione Magazzino*
- **Nome funzionalità:** *Impostazioni utente, icone e titoli dei passaggi per la nuova app di magazzino*

## <a name="get-the-warehouse-management-mobile-app"></a>Scarica l'app per dispositivi mobili Gestione magazzino

Per distribuzioni più piccole, potresti in genere installare l'app in ogni dispositivo dal relativo store e quindi configurare manualmente la connessione agli ambienti che stai utilizzando.

Per distribuzioni più importanti, puoi automatizzare la distribuzione e/o la configurazione dell'app, il che può essere più conveniente se si gestiscono molti dispositivi. Ad esempio, potresti utilizzare una soluzione per la gestione di dispositivi mobili e di applicazioni mobili come [Microsoft Intune](/mem/intune/fundamentals/what-is-intune). Per informazioni su come utilizzare Intune per aggiungere applicazioni, vedi [Aggiungere app in Microsoft Intune](/mem/intune/apps/apps-add).

### <a name="install-the-app-from-an-app-store"></a>Installare l'app da un app store

Il modo più semplice per installare l'app su un singolo dispositivo è installarla da un app store, che fornisce sempre l'ultima versione generalmente disponibile. Microsoft Intune può anche recuperare app da app store. Utilizza uno dei seguenti collegamenti per installare l'app da un app store:

- **Windows (UWP):** [Gestione magazzino in Microsoft Store](https://www.microsoft.com/store/apps/9pd35cdqcmg3)

- **Android:** [Gestione magazzino in Google Play Store](https://play.google.com/store/apps/details?id=com.Microsoft.WarehouseManagement)

### <a name="download-the-app-from-microsoft-app-center"></a>Scaricare l'app da Microsoft App Center

Come alternativa all'installazione da un app store, puoi invece scaricare l'app dal Microsoft App Center. L'App Center fornisce pacchetti installabili che è possibile trasferire localmente. Oltre alla versione corrente, l'App Center consente anche di scaricare versioni precedenti e può fornire versioni di anteprima con funzionalità imminenti che puoi provare. Per scaricare le versioni correnti, precedenti o in anteprima dell'app per dispositivi mobili Gestione magazzino da Microsoft App Center, utilizza uno dei collegamenti seguenti:

- **Windows (UWP):** [Gestione magazzino (Windows)](https://go.microsoft.com/fwlink/?linkid=2154406)  
    Per istruzioni su come installare un pacchetto scaricato in un dispositivo Windows e quindi configurare i certificati richiesti, vedi [Installare una build dall'App Center](/appcenter/distribution/installation).

- **Android:** [Gestione magazzino (Android)](https://go.microsoft.com/fwlink/?linkid=2154613)  
    Se scarichi una versione di anteprima, per installarla sono necessari alcuni passaggi aggiuntivi. Per i dettagli, vedere [Test di app Android](/appcenter/distribution/testers/testing-android).

## <a name="create-a-web-service-application-in-azure-active-directory"></a><a name="create-service"></a>Creare un'applicazione servizio Web in Azure Active Directory

Per abilitare l'app per dispositivi mobili Gestione magazzino per interagire con un server Supply Chain Management specifico, devi registrare un'applicazione servizio Web per il tenant di Supply Chain Management in Azure Active Directory (Azure AD). La seguente procedura mostra una modalità di completare questa attività. Per informazioni dettagliate e alternative, consulta i collegamenti dopo la procedura.

1. In un Web browser, vai a [https://portal.azure.com](https://portal.azure.com/).
1. Immetti il nome e la password dell'utente che ha accesso alla sottoscrizione Azure.
1. Nel portale di Azure, nel riquadro di spostamento a sinistra, fai clic su **Azure Active Directory**.

    ![Azure Active Directory.](media/app-connect-azure-aad.png "Azure Active Directory")

1. Assicurati di lavorare con l'istanza di Azure AD che viene utilizzata da Supply Chain Management.
1. Nell'elenco **Gestisci**, seleziona **Registrazioni app**.

    ![Registrazioni app.](media/app-connect-azure-register.png "Registrazioni app")

1. Sulla barra degli strumenti, seleziona **Nuova registrazione** per aprire la procedura guidata **Registra un'applicazione**.
1. Immetti un nome per l'applicazione, seleziona l'opzione **Solo account nella directory organizzativa**, quindi **Registra**.

    ![Procedura Registra un'applicazione.](media/app-connect-azure-register-wizard.png "Procedura Registra un'applicazione")

1. La nuova registrazione dell'app viene aperta. Annota il valore nel campo **ID applicazione (client)**, poiché sarà necessario in seguito. In seguito in questo argomento si farà riferimento a questo ID come *ID client*.

    ![ID applicazione (client).](media/app-connect-azure-app-id.png "ID applicazione (client)")

1. Nell'elenco **Gestisci**, seleziona **Certificato e segreti**. Quindi seleziona uno dei seguenti pulsanti, a seconda di come desideri configurare l'app per l'autenticazione. Per ulteriori informazioni, consulta la sezione [Autentica utilizzando un certificato o un segreto client](#authenticate) più avanti in questo argomento.

    - **Carica certificato**: carica un certificato da utilizzare come segreto. Consigliamo questo approccio, perché è più sicuro e può anche essere automatizzato in modo più completo. Se stai eseguendo l'app per dispositivi mobili Gestione magazzino su dispositivi Windows, prendi nota del valore **Identificazione personale** visualizzato dopo aver caricato il certificato. Questo valore sarà necessario quando configuri il certificato su dispositivi Windows.
    - **Nuovo segreto client**: crea una chiave inserendo una descrizione della chiave e una durata nella sezione **Password**, quindi seleziona **Aggiungi**. Crea una copia della chiave e conservala in modo sicuro.

    ![Certificato e segreti.](media/app-connect-azure-authentication.png "Certificato e segreti")

Per ulteriori informazioni su come impostare le applicazioni dei servizi Web in Azure AD, vedi le seguenti risorse:

- Per istruzioni che mostrano come utilizzare Windows PowerShell per configurare le applicazioni del servizio Web in Azure AD, vedi [Procedure: Usare Azure PowerShell per creare un'entità servizio con un certificato](/azure/active-directory/develop/howto-authenticate-service-principal-powershell).
- Per i dettagli completi su come creare manualmente un'applicazione di servizio Web in Azure AD, vedi i seguenti argomenti:

    - [Guida introduttiva: Registrare un'applicazione con Microsoft Identity Platform](/azure/active-directory/develop/quickstart-register-app)
    - [Procedure: Usare il portale per creare un'applicazione Azure AD e un'entità servizio che possano accedere alle risorse](/azure/active-directory/develop/howto-create-service-principal-portal)

## <a name="create-and-configure-a-user-account-in-supply-chain-management"></a>Creare e configurare un account utente in Supply Chain Management

Per consentire a Supply Chain Management di utilizzare la tua applicazione Azure AD, attieniti alla seguente procedura.

1. Crea un utente che corrisponde alle credenziali dell'utente per l'app per dispositivi mobili Gestione magazzino:

    1. In Supply Chain Management, vai a **Amministrazione sistema \> Utenti \> Utenti**.
    1. Crea un utente.
    1. Assegna l'utente del dispositivo mobile al magazzino.

    ![Assegna l'utente del dispositivo mobile al magazzino.](media/app-connect-app-users.png "Assegna l'utente del dispositivo mobile al magazzino")

1. Associa l'applicazione Azure AD all'utente dell'app per dispositivi mobili Gestione magazzino:

    1. Vai a **Amministrazione sistema \> Impostazioni \> Applicazioni Azure Active Directory**.
    1. Crea una riga.
    1. Inserisci l'ID client di cui hai preso nota nella sezione precedente, assegnagli un nome e seleziona l'utente che hai appena creato. Ti consigliamo di taggare tutti i tuoi dispositivi. Quindi, se un dispositivo viene perso, puoi rimuovere facilmente il suo accesso a Supply Chain Management da questa pagina.

    ![Applicazioni di Azure Active Directory.](media/app-connect-aad-apps.png "Applicazioni di Azure Active Directory")

## <a name="authenticate-by-using-a-certificate-or-client-secret"></a><a name="authenticate"></a>Autenticazione utilizzando un certificato o un segreto client

L'autenticazione con Azure AD fornisce un modo sicuro per connettere un dispositivo mobile a Supply Chain Management. Puoi eseguire l'autenticazione utilizzando un segreto client o un certificato. Se importerai le impostazioni di connessione, ti consigliamo di utilizzare un certificato anziché un segreto client. Poiché il segreto client deve essere sempre archiviato in modo sicuro, non è possibile importarlo da un file delle impostazioni di connessione o da un codice QR, come descritto più avanti in questo argomento.

I certificati possono essere utilizzati come segreti per dimostrare l'identità dell'applicazione quando viene richiesto un token. La parte pubblica del certificato viene caricata nella registrazione dell'app nel portale di Azure, mentre il certificato completo deve essere distribuito su ogni dispositivo in cui è installata l'app per dispositivi mobili Gestione magazzino. La tua organizzazione è responsabile della gestione del certificato in termini di rotazione e così via. Puoi utilizzare certificati autofirmati, ma è sempre necessario utilizzare certificati non esportabili.

Devi rendere il certificato disponibile localmente su ciascun dispositivo su cui viene eseguita l'app per dispositivi mobili Gestione magazzino. Per informazioni su come gestire i certificati per i dispositivi controllati da Intune se utilizzi Intune, vedi [Usare i certificati per l'autenticazione in Microsoft Intune](/mem/intune/protect/certificates-configure).

## <a name="configure-the-application-by-importing-connection-settings"></a>Configurare l'applicazione importando le impostazioni di connessione

Per semplificare la gestione e la distribuzione dell'applicazione su molti dispositivi mobili, puoi importare le impostazioni di connessione anziché immetterle manualmente su ciascun dispositivo. Questa sezione spiega come creare e importare le impostazioni.

### <a name="create-a-connection-settings-file-or-qr-code"></a>Creare un file delle impostazioni di connessione o un codice QR

Puoi importare le impostazioni di connessione da un file o da un codice QR. Per entrambi gli approcci, devi innanzitutto creare un file di impostazioni che utilizza il formato e la sintassi JavaScript Object Notation (JSON). Il file deve includere un elenco di connessioni che contiene le singole connessioni che devono essere aggiunte. La tabella seguente riepiloga i parametri che è necessario specificare nel file delle impostazioni di connessione.

| Parametro | Descrizione |
|---|---|
| ConnectionName | Specificare il nome dell'impostazione della connessione. La lunghezza massima consentita è di 20 caratteri. Poiché questo valore è l'identificatore univoco per un'impostazione di connessione, assicurati che sia univoco nell'elenco. Se sul dispositivo esiste già una connessione con lo stesso nome, verrà sovrascritta dalle impostazioni del file importato. |
| ActiveDirectoryClientAppId | Specifica l'ID client di cui hai preso nota durante la configurazione di Azure AD nella sezione [Creare un'applicazione del servizio Web in Azure Active Directory](#create-service). |
| ActiveDirectoryResource | Specifica l'URL principale di Supply Chain Management. |
| ActiveDirectoryTenant | Specificare il tenant di Azure AD che stai utilizzando con il server Supply Chain Management. Questo valore ha la forma `https://login.windows.net/<your-Azure-AD-tenant-ID>`. Ecco un esempio: `https://login.windows.net/contosooperations.onmicrosoft.com`. |
| Società | Specifica la persona giuridica in Supply Chain Management a cui si desidera connettere l'applicazione. |
| ConnectionType | (Facoltativo) Specificare se l'impostazione di connessione deve utilizzare un certificato o un segreto client per connettersi a un ambiente. I valori validi sono *"certificato"* e *"clientsecret"*. Il valore predefinito è *"certificato"*.<p>**Nota:** i segreti client non possono essere importati.</p> |
| IsEditable | (Facoltativo) Specifica se l'utente dell'app deve essere in grado di modificare le impostazioni di connessione. I valori validi sono *"true"* e *"false"*. Il valore predefinito è *"true"*. |
| IsDefault | (Facoltativo) Specificare se la connessione è la connessione predefinita. Una connessione impostata come connessione predefinita verrà automaticamente preselezionata all'apertura dell'app. È possibile impostare come connessione predefinita una sola connessione. I valori validi sono *"true"* e *"false"*. Il valore predefinito è *"false"*. |
| CertificateThumbprint | (Facoltativo) Per i dispositivi Windows, puoi specificare l'identificazione personale del certificato per la connessione. Per i dispositivi Android, l'utente dell'app deve selezionare il certificato la prima volta che viene utilizzata una connessione. |

L'esempio seguente mostra un file di impostazioni di connessione valido che contiene due connessioni. Come puoi vedere, l'elenco delle connessioni (denominato *"ConnectionList"* nel file) è un oggetto che ha un array che memorizza ogni connessione come oggetto. Ogni oggetto deve essere racchiuso tra parentesi graffe ({}) e separate da virgole e l'array deve essere racchiuso tra parentesi (\[\]).

```json
{
    "ConnectionList": [
        {
            "ActiveDirectoryClientAppId":"aaaaaaaa-bbbb-ccccc-dddd-eeeeeeeeeeee",
            "ConnectionName": "Connection1",
            "ActiveDirectoryResource": "https://yourenvironment.cloudax.dynamics.com",
            "ActiveDirectoryTenant": "https://login.windows.net/contosooperations.onmicrosoft.com",
            "Company": "USMF",
            "IsEditable": false,
            "IsDefaultConnection": true,
            "CertificateThumbprint": "aaaabbbbcccccdddddeeeeefffffggggghhhhiiiii",
            "ConnectionType": "certificate"
        },
        {
            "ActiveDirectoryClientAppId":"aaaaaaaa-bbbb-ccccc-dddd-eeeeeeeeeeee",
            "ConnectionName": "Connection2",
            "ActiveDirectoryResource": "https://yourenvironment2.cloudax.dynamics.com",
            "ActiveDirectoryTenant": "https://login.windows.net/contosooperations.onmicrosoft.com",
            "Company": "USMF",
            "IsEditable": true,
            "IsDefaultConnection": false,
            "ConnectionType": "clientsecret"
        }
    ]
}
```

Puoi salvare le informazioni come file JSON o generare un codice QR con lo stesso contenuto. Se salvi le informazioni come file, ti consigliamo di salvarle utilizzando il nome predefinito, *connections.json*, soprattutto se lo memorizzerai nella posizione predefinita su ciascun dispositivo mobile.

### <a name="save-the-connection-settings-file-on-each-device"></a>Salva il file delle impostazioni di connessione su ciascun dispositivo

In genere, utilizzerai uno strumento o uno script di gestione dei dispositivi per distribuire i file delle impostazioni di connessione a ciascun dispositivo che stai gestendo. Se utilizzi il nome e il percorso predefiniti quando salvi il file delle impostazioni di connessione su ciascun dispositivo, l'app per dispositivi mobili Gestione magazzino lo importerà automaticamente, anche durante la prima esecuzione dopo l'installazione dell'app. Se utilizzi un nome o un percorso personalizzato per il file, l'utente dell'app deve specificare i valori durante la prima esecuzione. Tuttavia, l'app continuerà a utilizzare il nome e la posizione specificati in seguito.

Ogni volta che l'app viene avviata, reimporta le impostazioni di connessione dalla posizione precedente per determinare se sono state apportate modifiche. L'app aggiornerà solo le connessioni con gli stessi nomi delle connessioni nel file delle impostazioni di connessione. Le connessioni create dall'utente che utilizzano altri nomi non verranno aggiornate.

Non puoi rimuovere una connessione utilizzando il file delle impostazioni di connessione.

Come menzionato, il nome file predefinito è *connections.json*. Il percorso predefinito del file dipende dal fatto che si stia utilizzando un dispositivo Windows o un dispositivo Android:

- **Windows:** `C:\Users\<User>\AppData\Local\Packages\Microsoft.WarehouseManagement_8wekyb3d8bbwe\LocalState`
- **Android:** `Android\data\com.Microsoft.WarehouseManagement\files`

Di solito, i percorsi vengono creati automaticamente dopo la prima esecuzione dell'app. Tuttavia, è possibile crearli manualmente se è necessario trasferire il file delle impostazioni di connessione sul dispositivo prima dell'installazione.

> [!NOTE]
> Se l'app viene disinstallata, il percorso predefinito e i relativi contenuti vengono rimossi.

### <a name="import-the-connection-settings"></a>Importa le impostazioni di connessione

Segui questa procedura per importare le impostazioni di connessione da un file o da un codice QR.

1. Avvia l'app per dispositivi mobili Gestione magazzino sul tuo dispositivo mobile. La prima volta che avvii l'app, viene visualizzato un messaggio di benvenuto. Selezionare **Seleziona una connessione**.

    ![Messaggio di benvenuto.](media/app-configure-welcome-screen.png "Messaggio di benvenuto")

1. Se stai importando le impostazioni di connessione da un file, l'app potrebbe aver già trovato il file se il nome e la posizione predefiniti sono stati utilizzati al momento del salvataggio. In questo caso, vai al passaggio 4. Altrimenti, seleziona **Configura connessione** e quindi continua con il passaggio 3.

    ![Imposta connessione.](media/app-configure-set-up-connection.png "Imposta connessione")

1. Nella finestra di dialogo **Configurazione connessione**, selezionare **Aggiungi da file** o **Aggiungi da codice a matrice**, a seconda di come si desidera importare le impostazioni:

    - Se stai importando le impostazioni di connessione da un file, seleziona **Aggiungi da file**, cerca il file sul tuo dispositivo locale e selezionalo. Se selezioni una posizione personalizzata, l'app la memorizzerà e la utilizzerà automaticamente la volta successiva.
    - Se stai importando le impostazioni di connessione scansionando un codice QR, seleziona **Aggiungi da codice a matrice**. L'app richiede l'autorizzazione per utilizzare la fotocamera del dispositivo. Dopo aver concesso l'autorizzazione, la fotocamera viene avviata, in modo da poterla utilizzare per la scansione. A seconda della qualità della fotocamera del dispositivo e della complessità del codice QR, potrebbe essere difficile ottenere una scansione corretta. In tal caso, prova a ridurre la complessità del codice QR generando una sola connessione per codice QR. Attualmente, è possibile utilizzare solo la fotocamera del dispositivo per scansionare il codice QR.

    ![Menu di configurazione della connessione.](media/app-configure-connection-setup-flyout.png "Menu di configurazione della connessione")

1. Quando le impostazioni di connessione vengono caricate correttamente, viene visualizzata la connessione selezionata.

    ![Impostazioni di connessione caricate.](media/app-configure-select-connection.png "Impostazioni di connessione caricate")

1. Se stai usando un dispositivo Android e stai utilizzando un certificato per l'autenticazione, il dispositivo richiede di selezionare il certificato.

    ![Selezionare il certificato richiesto su un dispositivo Android.](media/app-configure-select-certificate.png "Selezionare il certificato richiesto su un dispositivo Android")

1. L'app si collega al server Supply Chain Management e visualizza la pagina di accesso.

    ![Pagina di accesso.](media/app-configure-sign-in-page.png "Pagina di accesso")

## <a name="manually-configure-the-application"></a><a name="config-manually"></a>Configurare l'applicazione manualmente

Se non disponi di un file o codice a matrice, puoi configurare manualmente l'app sul dispositivo affinché si connetta al server Supply Chain Management tramite l'applicazione Azure AD.

1. Avvia l'app per dispositivi mobili Gestione magazzino sul tuo dispositivo mobile.
1. Se l'app viene avviata in **Modalità demo**, Selezionare **Impostazioni di connessione**. Se viene visualizzata la pagina **Accedi** quando si avvia l'app, selezionare **Cambia connessione**.
1. Selezionare **Configura connessione**.

    ![Imposta connessione.](media/app-configure-set-up-connection.png "Imposta connessione")

1. Selezionare **Inserisci manualmente**.

    ![Menu di configurazione della connessione.](media/app-configure-connection-setup-flyout.png "Menu di configurazione della connessione")

    Viene visualizzata la pagina **Nuova connessione** che mostra le impostazioni richieste per inserire manualmente i dettagli della connessione.

    ![Campi di connessione manuale.](media/app-configure-input-manually.png "Campi di connessione manuale")

1. Immettere le seguenti informazioni:

    - **Usa il segreto del client**: imposta questa opzione su _Sì_ per utilizzare un segreto client per l'autenticazione con Supply Chain Management. Impostala su _No_ per utilizzare un certificato per l'autenticazione. Per ulteriori informazioni, vedere la sezione [Creare un'applicazione di servizio Web in Azure Active Directory](#create-service) precedente in questo argomento.
    - **Nome connessione**: immetti un nome per la nuova connessione. Questo nome verrà visualizzato nel campo **Seleziona connessione** alla successiva apertura delle impostazioni di connessione. Il nome inserito deve essere unico. In altre parole, deve differire da tutti gli altri nomi di connessione memorizzati sul dispositivo, se in questo spazio sono memorizzati altri nomi di connessione.
    - **ID client Active directory**: immetti l'ID client di cui hai preso nota durante la configurazione di Azure AD nella sezione [Creare un'applicazione servizio Web in Azure Active Directory](#create-service) section.
    - **Segreto client di Active Directory**: questo campo è disponibile solo quando l'opzione **Usa segreto client** è impostata su _Sì_. Immetti il segreto client di cui hai preso nota durante la configurazione di Azure AD nella sezione [Creare un'applicazione del servizio Web in Azure Active Directory](#create-service).
    - **Identificazione digitale del certificato di Active Directory**: questo campo è disponibile solo per i dispositivi Windows e solo quando l'opzione **Usa segreto client** è impostata su _No_. Immetti l'identificazione del certificato di cui hai preso nota durante la configurazione di Azure AD nella sezione [Creare un'applicazione del servizio Web in Azure Active Directory](#create-service).
    - **Risorsa di Active Directory**: specifica l'URL principale di Supply Chain Management.

        > [!IMPORTANT]
        > Non terminare questo valore con una barra (/).

    - **Tenant di Active directory**: immetti il tenant di Azure AD che stai usando per il server Supply Chain Management. Questo valore ha la forma `https://login.windows.net/<your-Azure-AD-tenant-ID>`. Ecco un esempio: `https://login.windows.net/contosooperations.onmicrosoft.com`.

        > [!IMPORTANT]
        > Non terminare questo valore con una barra (/).

    - **Società**: immetti la persona giuridica (azienda) in Supply Chain Management a cui desideri connettere l'applicazione.

1. Selezionare il pulsante **Salva** nell'angolo superiore destro della pagina.
1. Se stai usando un dispositivo Android e stai utilizzando un certificato per l'autenticazione, il dispositivo richiede di selezionare il certificato.
1. L'app si collega al server Supply Chain Management e visualizza la pagina di accesso.

## <a name="remove-access-for-a-device"></a>Rimuovere l'accesso per un dispositivo

Se un dispositivo è perso o compromesso, è necessario rimuovere l'accesso a Supply Chain Management dello stesso. Nei passaggi seguenti viene descritto il processo consigliato per la rimozione dell'accesso.

1. Vai a **Amministrazione sistema \> Impostazioni \> Applicazioni Azure Active Directory**.
1. Elimina la riga corrispondente al dispositivo a cui desideri rimuovere l'accesso. Prendi nota dell'ID client utilizzato per il dispositivo, poiché sarà necessario in un secondo momento.

    Se hai registrato un solo ID client e più dispositivi utilizzano lo stesso ID client, devi inviare nuove impostazioni di connessione a tali dispositivi. Altrimenti, perderanno l'accesso.

1. Accedi al portale di Azure all'indirizzo [https://portal.azure.com](https://portal.azure.com/).
1. Nel riquadro di navigazione sinistro, seleziona **Active Directory** e assicurati di essere nella directory corretta.
1. Nell'elenco **Gestisci**, seleziona **Registrazioni app** quindi seleziona l'applicazione da configurare. Viene visualizzata la pagina **Impostazioni** con informazioni di configurazione.
1. Assicurati che l'ID client dell'applicazione corrisponda all'ID client annotato nel passaggio 2.
1. Sulla barra degli strumenti, seleziona **Elimina**.
1. Nel messaggio di conferma visualizzato, seleziona **Sì**.

## <a name="additional-resources"></a>Risorse aggiuntive

- [Impostazioni utente dispositivo mobile](mobile-device-user-settings.md)
- [Assegnare icone e titoli dei passaggi per l'app per dispositivi mobili Warehouse Management](step-icons-titles.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]