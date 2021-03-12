---
title: Impostare un tenant B2C in Commerce
description: Questo argomento descrive come configurare il tenant Azure Active Directory (Azure AD) business-to-consumer (B2C) per l'autenticazione del sito dell'utente in Dynamics 365 Commerce.
author: BrianShook
manager: annbe
ms.date: 06/22/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: retail
ms.author: brshoo
ms.search.validFrom: 2020-02-13
ms.dyn365.ops.version: ''
ms.openlocfilehash: 68e72bc17005c11f28f572114357f906098cc045
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4993346"
---
# <a name="set-up-a-b2c-tenant-in-commerce"></a>Impostare un tenant B2C in Commerce

[!include [banner](includes/banner.md)]

Questo argomento descrive come configurare il tenant Azure Active Directory (Azure AD) business-to-consumer (B2C) per l'autenticazione del sito dell'utente in Dynamics 365 Commerce.

## <a name="overview"></a>Panoramica

Dynamics 365 Commerce utilizza Azure AD B2C per supportare le credenziali dell'utente e i flussi di autenticazione. Un utente può registrarsi, accedere e reimpostare la propria password attraverso questi flussi. Azure AD B2C memorizza le informazioni di autenticazione sensibili di un utente, ad esempio il nome utente e la password. Il record utente nel tenant B2C memorizza un record dell'account locale B2C o un record del provider di identità social B2C. Questi record B2C rimandano al record del cliente nell'ambiente Commerce.

## <a name="create-or-link-to-an-existing-aad-b2c-tenant-in-the-azure-portal"></a>Creare o collegare un tenant AAD B2C esistente nel portale di Azure

1. Accedere al [portale Azure](https://portal.azure.com/).
1. Dal menu del portale di Azure, selezionare **Crea una risorsa**. Assicurarsi di utilizzare la sottoscrizione e la directory che saranno collegati al tuo ambiente Commerce.

    ![Creare una risorsa nel portale di Azure](./media/B2CImage_1.png)

1. Andare a **Identità \> Azure Active Directory B2C**.
1. Una volta nella pagina **Crea nuovo tenant B2C o collegamento a tenant esistente**, utilizzare una delle opzioni seguenti più adatta alle esigenze dell'azienda:

    - **Creare uno nuovo tenant Azure AD B2C**: utilizzare questa opzione per creare un nuovo tenant AAD B2C.
        1. Selezionare **Crea un nuovo tenant Azure AD B2C**.
        1. In **Nome organizzazione**, immettere il nome dell'organizzazione.
        1. In **Nome di dominio iniziale**, immettere il nome del dominio iniziale.
        1. Per **Paese o area geografica**, selezionare il paese o l'area geografica.
        1. Selezionare **Crea** per creare il tenant.

     ![Creare un nuovo tenant Azure AD](./media/B2CImage_2.png)

     - **Collega un tenant Azure AD B2C esistente alla sottoscrizione di Azure**: utilizzare questa opzione se si dispone già di un tenant Azure AD B2C che si desidera collegare.
        1. Selezionare **Collega un tenant Azure AD B2C esistente alla sottoscrizione di Azure**.
        1. Per **Tenant Azure AD B2C**, selezionare il tenant B2C appropriato. Se nella casella di selezione viene visualizzato il messaggio "Nessun tenant B2C idoneo trovato", non si dispone di un tenant B2C idoneo esistente e sarà necessario crearne uno nuovo.
        1. Per **Gruppo di risorse**, selezionare **Crea nuovo**. Immettere un **nome** per il gruppo di risorse che conterrà il tenant, selezionare **Ubicazione del gruppo di risorse**, quindi selezionare **Crea**.

    ![Collegare un tenant Azure AD B2C esistente alla sottoscrizione di Azure](./media/B2CImage_3.png)

1. Una volta creata la nuova directory Azure AD B2C (l'operazione potrebbe richiedere alcuni istanti) sul dashboard verrà visualizzato un collegamento alla nuova directory. Questo collegamento indirizzerà alla pagina di "Benvenuto in Azure Active Directory B2C".

    ![Collegare alla nuova directory AAD](./media/B2CImage_4.png)

> [!NOTE]
> Se sono presenti più sottoscrizioni nell'account Azure o è stato impostato il tenant B2C senza collegamento a una sottoscrizione attiva, un banner **Risoluzione dei problemi** esegue il reindirizzamento al collegamento del tenant a una sottoscrizione. Selezionare il messaggio della risoluzione dei problemi e seguire le istruzioni per risolvere il problema di sottoscrizione.

L'immagine seguente mostra un esempio di banner **Risoluzione dei problemi** Azure AD B2C.

![Avviso indicante che la directory non ha una sottoscrizione attiva](./media/B2CImage_5.png)

## <a name="create-the-b2c-application"></a>Creare l'applicazione B2C

Una volta creato il tenant B2C, all'interno del tenant verrà creata un'applicazione B2C per interagire con le azioni di Commerce.

Per creare l'applicazione B2C, attenersi alla procedura seguente.

1. Nel portale di Azure selezionare **Applicazioni (Legacy)** e quindi selezionare **Aggiungi**.
1. In **Nome**, immettere il nome dell'applicazione AAD B2C desiderata.
1. In **App Web/API Web**, per **Includi app Web/API Web**, selezionare **Sì**.
1. Per **Consenti flusso implicito**, selezionare **Sì** (valore predefinito).
1. In **URL di risposta**, immettere gli URL di risposta dedicati. Vedere [URL di risposta](#reply-urls) di seguito per informazioni sugli URL di risposta e su come formattarli.
1. Per **Includi client nativo**, Selezionare **No** (valore predefinito).
1. Selezionare **Crea**.

### <a name="reply-urls"></a>URL di risposta

Gli URL di risposta sono importanti in quanto forniscono un elenco dei domini di ritorno consentiti quando il sito chiama Azure AD B2C per autenticare un utente. Ciò consente il ritorno dell'utente autenticato al dominio dal quale sta accedendo (dominio del sito). 

Nella casella **URL di risposta** nella schermata **Azure AD B2c - Applicazioni \> Nuova applicazione**, è necessario aggiungere righe separate per il dominio del sito e (una volta effettuato il provisioning dell'ambiente) per l'URL generato da Commerce. Questi URL devono sempre utilizzare un formato URL valido e devono essere solo URL di base (nessuna barra o percorso). La stringa ``/_msdyn365/authresp`` quindi deve essere aggiunta agli URL di base, come nei seguenti esempi.

- ``https://www.fabrikam.com/_msdyn365/authresp``(Il dominio dovrebbe corrispondere completamente al dominio e-commerce. Se hai più domini, devi aggiungere questo URL per ogni dominio.)
- ``https://fabrikam-prod.commerce.dynamics.com/_msdyn365/authresp``

## <a name="create-user-flow-policies"></a>Creare criteri di flusso utente

I flussi di utenti sono i criteri utilizzati da Azure AD B2C per fornire le esperienze utente di accesso sicuro, registrazione, modifica del profilo e password dimenticata. Dynamics 365 Commerce utilizza questi flussi per eseguire le azioni dei criteri per interagire con il tenant Azure AD B2C. Quando un utente interagisce con questi criteri, vengono reindirizzati al tenant Azure AD B2C per eseguire le azioni.

Azure AD B2C offre tre tipi di flusso utente di base:
- Iscrizione e accesso
- Modifica del profilo
- Password reimpostata

È possibile scegliere di utilizzare i flussi utente predefiniti forniti da Azure AD, che visualizzano una pagina ospitata da AAD B2C. In alternativa, è possibile creare una pagina HTML per controllare l'aspetto di queste esperienze di flusso utente. 

Per personalizzare le pagine dei criteri utente per Dynamics 365 Commerce vedere [Impostare pagine personalizzate per gli accessi utente](custom-pages-user-logins.md). Per ulteriori informazioni, vedere [Personalizzare l'interfaccia delle esperienze utente in Azure Active Directory B2C](https://docs.microsoft.com/azure/active-directory-b2c/tutorial-customize-ui).

### <a name="create-a-sign-up-and-sign-in-user-flow-policy"></a>Creare criteri di accesso e iscrizione nel flusso utente

Per creare i criteri di accesso e iscrizione nel flusso utente, effettuare le seguenti operazioni.

1. Nel portale di Azure selezionare **Flussi utente (criteri)** nel pannello di navigazione a sinistra.
1. Nella pagina **Azure AD B2C - Flussi utente (criteri)**, selezionare **Nuovo flusso utente**.
1. Nella scheda **Consigliato**, selezionare **Iscrizione e accesso**.
1. Sotto **Nome**, immettere un nome per i criteri. Questo nome verrà visualizzato in seguito con un prefisso assegnato dal portale (ad esempio "B2C_1_").
1. Sotto **Provider di identità**, selezionare la casella di controllo appropriata.
1. Sotto **Autenticazione a più fattori**, selezionare la scelta appropriata per l'azienda. 
1. Sotto **Attributi e attestazioni dell'utente**, selezionare le opzioni per raccogliere gli attributi o restituire le attestazioni, a seconda dei casi. Commerce richiede le seguenti opzioni predefinite:

    | **Raccogli attributo** | **Restituisci attestazione** |
    | ---------------------- | ----------------- |
    | Indirizzo di posta elettronica          | Indirizzi di posta elettronica   |
    | Nome specificato             | Nome specificato        |
    |                        | Provider di identità |
    | Cognome                | Cognome           |
    |                        | ID oggetto dell'utente  |

1. Selezionare **Crea**.

L'immagine seguente è un esempio di criteri di accesso e iscrizione Azure AD B2C nel flusso utente.

![Impostazioni dei criteri di iscrizione e accesso](./media/B2CImage_11.png)

L'immagine seguente mostra l'opzione **Esegui flusso utente** nell'iscrizione e accesso Azure AD B2C nel flusso utente.

![Eseguire l'opzione flusso utente nel flusso dei criteri](./media/B2CImage_23.png)
   
### <a name="create-a-profile-editing-user-flow-policy"></a>Creare i criteri di flusso utente per la modifica del profilo

Per creare i criteri di flusso utente per la modifica del profilo, effettuare le seguenti operazioni.

1. Nel portale di Azure selezionare **Flussi utente (criteri)** nel pannello di navigazione a sinistra.
1. Nella pagina **Azure AD B2C - Flussi utente (criteri)**, selezionare **Nuovo flusso utente**.
1. Nella scheda **Consigliato**, selezionare **Modifica del profilo**.
1. Sotto **Nome**, immettere il flusso utente per la modifica del profilo. Questo nome verrà visualizzato in seguito con un prefisso assegnato dal portale (ad esempio "B2C_1_").
1. Sotto **Provider di identità**, selezionare **Accesso all'account locale**.
1. In **Attributi utente** selezionare una delle seguenti caselle di controllo:
    - **Indirizzi e-mail** (solo **Restituisci attestazione**)
    - **Nome specificato** (**Raccogli attributo** e **Restituisci attestazione**)
    - **Provider di identità** (solo **Restituisci attestazione**)
    - **Cognome** (**Raccogli attributo** e **Restituisci attestazione**)
    - **ID oggetto dell'utente** (solo **Restituisci attestazione**)
1. Selezionare **Crea**.

L'immagine seguente mostra un esempio di flusso utente per la modifica del profilo Azure AD B2C.

![Creare il flusso utente per la modifica del profilo](./media/B2CImage_12.png)

### <a name="create-a-password-reset-user-flow-policy"></a>Creare un flusso utente per la reimpostazione della password

Per creare i criteri di flusso utente per la reimpostazione della password, effettuare le seguenti operazioni.

1. Nel portale di Azure selezionare **Flussi utente (criteri)** nel pannello di navigazione a sinistra.
1. Nella pagina **Azure AD B2C - Flussi utente (criteri)**, selezionare **Nuovo flusso utente**.
1. Nella scheda **Consigliato**, selezionare **Reimpostazione password**.
1. Sotto **Nome**, immettere un nome per il flusso utente di reimpostazione della password.
1. In **Provider di identità**, selezionare **Reimposta password utilizzando l'indirizzo di posta elettronica**.
1. Selezionare **Crea**.
1. In **Richieste applicazione** selezionare una delle seguenti caselle di controllo:
    - **Indirizzi di posta elettronica**
    - **Nome specificato**
    - **Cognome**
    - **ID oggetto dell'utente**
1. Selezionare **Crea**.

L'immagine seguente mostra dove impostare **Reimposta password utilizzando l'indirizzo e-mail** nel flusso utente per il ripristino della password Azure AD B2C.

![Impostare "Reimposta password utilizzando l'indirizzo e-mail" nei criteri per la reimpostazione della password](./media/B2CImage_13.png)

## <a name="add-social-identity-providers-optional"></a>Aggiungere provider di identità social (facoltativo)

I provider di identità social consentono agli utenti di utilizzare i propri account social per l'autenticazione. L'aggiunta dell'autenticazione del provider di identità social è facoltativa in Dynamics 365 Commerce. 

Se non viene aggiunta l'autenticazione del provider di identità social, i profili predefiniti Azure AD B2C saranno i profili principali per la base di utenti. Gli utenti selezioneranno il proprio nome utente (l'indirizzo e-mail preferito) e imposteranno una password. Azure AD B2C autenticherà direttamente gli utenti. 

Se viene aggiunta l'autenticazione del provider di identità social e un utente sceglie uno dei provider di identità social offerti, un'entità viene comunque creata nel tenant Azure AD B2C. Azure AD B2C autenticherà quindi le credenziali dell'utente con il provider di identità social.

> [!NOTE]
> L'accesso del provider di identità crea un record nel tenant B2C, ma in un formato diverso rispetto agli account locali poiché chiamerà il riferimento del provider di identità social esterno per l'autenticazione. L'utente può utilizzare lo stesso indirizzo e-mail tra i provider di identità social, il che significa che il nome utente e-mail utilizzato per l'autenticazione potrebbe non essere univoco per il tenant. Azure AD B2C richiede solo che gli utenti dispongano di un indirizzo e-mail univoco sugli account B2C locali.

Prima di poter aggiungere un provider di identità social per l'autenticazione, è necessario accedere al portale del provider di identità e configurare un'applicazione del provider di identità come indicato nella documentazione di Azure AD B2C. Di seguito viene fornito un elenco di collegamenti alla documentazione.

- [Amazon](https://docs.microsoft.com/azure/active-directory-b2c/active-directory-b2c-setup-amzn-app)
- [Azure AD (Tenant singolo)](https://docs.microsoft.com/azure/active-directory-b2c/active-directory-b2c-setup-oidc-azure-active-directory)
- [Account Microsoft](https://docs.microsoft.com/azure/active-directory-b2c/active-directory-b2c-setup-msa-app)
- [Facebook](https://docs.microsoft.com/azure/active-directory-b2c/active-directory-b2c-setup-fb-app)
- [GitHub](https://docs.microsoft.com/azure/active-directory-b2c/active-directory-b2c-setup-github-app)
- [Google](https://docs.microsoft.com/azure/active-directory-b2c/active-directory-b2c-setup-goog-app)
- [LinkedIn](https://docs.microsoft.com/azure/active-directory-b2c/active-directory-b2c-setup-li-app)
- [OpenID Connect](https://docs.microsoft.com/azure/active-directory-b2c/active-directory-b2c-setup-oidc-idp)
- [Twitter](https://docs.microsoft.com/azure/active-directory-b2c/active-directory-b2c-setup-twitter-app)

### <a name="add-and-set-up-a-social-identity-provider"></a>Aggiungere e impostare un provider di identità social

Per aggiungere e configurare un provider di identità social, attenersi alla seguente procedura.  

1. Nel portale di Azure, accedere a **Provider di identità**.
1. Selezionare **Aggiungi**. Viene visualizzata la schermata **Aggiungi provider di identità**.
1. Sotto **Nome**, immettere il nome da mostrare agli utenti nella schermata di accesso.
1. Sotto **Tipo di provider di identità**, selezionare un provider di identità dall'elenco.
1. Selezionare **OK**.
1. Selezionare **Imposta questo provider di identità** per accedere alla schermata **Imposta il provider di identità social**.
1. Sotto **ID client**, inserisci l'ID client come ottenuto dall'impostazione dell'applicazione del provider di identità.
1. Sotto **Segreto client**, inserisci il segreto client come ottenuto dall'impostazione dell'applicazione del provider di identità.
1. Allegare il flusso utente per i criteri di iscrizione e accesso:
1. Andare a **Azure AD B2C - Flussi utente (criteri) \> {criteri di accesso} \> provider di identità**.
1. Per allegare il criterio di flusso utente di accesso/iscrizione, selezionare ciascun provider di identità impostato per l'account. Per testarli, selezionare **Esegui flusso utente** per ciascun provider di identità. Una nuova scheda visualizzerà la pagina di accesso con la casella di selezione del nuovo provider di identità.

L'immagine seguente mostra esempi delle schermate **Aggiungi provider di identità** e **Imposta il provider di identità social** in Azure AD B2C.

![Aggiunta di un provider di identità social all'applicazione](./media/B2CImage_14.png)

L'immagine seguente mostra un esempio di come selezionare i provider di identità nella pagina **Provider di identità** di Azure AD B2C.

![Selezionare ciascun provider di identità social da abilitare per i criteri](./media/B2CImage_16.png)

L'immagine seguente mostra un esempio di schermata di accesso predefinita con un pulsante di accesso del provider di identità social visualizzato.

![Esempio di schermata di accesso predefinita con il pulsante di accesso al provider di identità social visualizzato](./media/B2CImage_17.png)

## <a name="update-commerce-headquarters-with-the-new-azure-ad-b2c-information"></a>Aggiornare Commerce headquarters con le nuove informazioni Azure AD B2C

Una volta completati i passaggi di provisioning di Azure AD B2C precedenti, l'applicazione Azure AD B2C deve essere registrata nell'ambiente Dynamics 365 Commerce.

Per aggiornare headquarters con le nuove informazioni Azure AD B2C, attenersi alla seguente procedura.

1. In Commerce, andare a **Parametri condivisi di Commerce** e selezionare **Provider di identità** nel menu a sinistra.
1. Sotto **Provider di identità**, effettuare quanto segue:
    1. Nella casella **Emittente**, inserire l'URL dell'emittente del provider di identità. Per trovare l'URL dell'emittente, vedere [Ottenere l'URL dell'emittente](#obtain-issuer-url) di seguito.
    1. Nella casella **Nome** immettere un nome per il record emittente.
    1. Nella casella **Tipo**, immettere **Azure AD B2C (id_token)**.
1. Sotto **Parti affidabili**, con l'elemento del provider di identità B2C sopra selezionato selezionato, procedere come segue:
    1. Nella casella **ClientID**, immettere l'ID applicazione B2C. È possibile trovarlo nella casella **ID applicazione** della pagina delle proprietà dell'applicazione B2C.
    1. Nella casella **Tipo**, immettere **Pubblico**.
    1. Nella casella **Tipo utente**, immettere **Cliente**.
1. Nel riquadro azioni selezionare **Salva**.
1. Nella casella di ricerca Commerce, cercare **Programmazione di distribuzione**
1. Nel menu di navigazione a sinistra della pagina **Programmazioni di distribuzione**, selezionare il processo **1110 Configurazione globale**.
1. Nel riquadro azioni selezionare **Esegui adesso**.

### <a name="obtain-issuer-url"></a>Ottenere l'URL dell'emittente

Per ottenere l'URL dell'emittente del provider di identità, attenersi alla seguente procedura.

1. Creare un URL di indirizzo metadati nel seguente formato usando il tenant e i criteri B2C: ``https://<B2CTENANTNAME>.b2clogin.com/<B2CTENANTNAME>.onmicrosoft.com/v2.0/.well-known/openid-configuration?p=<B2CSIGN-INPOLICY>``
    - Esempio: ``https://d365plc.b2clogin.com/d365plc.onmicrosoft.com/v2.0/.well-known/openid-configuration?p=B2C_1_signinup``.
1. Immettere l'URL dell'indirizzo dei metadati nella barra degli indirizzi del browser.
1. Nei metadati, copiare l'URL dell'emittente del provider di identità (il valore per **"emittente"**).
    - Esempio: ``https://login.fabrikam.com/073405c3-0113-4f43-b5e2-df01266e24ae/v2.0/``.

## <a name="configure-your-b2c-tenant-in-commerce-site-builder"></a>Configurare il tenant B2C in Creazione di siti Web di Commerce

Una volta impostato il tenant Azure AD B2C, è necessario configurare il tenant B2C in Creazione di siti Web di Commerce. I passaggi della configurazione includono la raccolta di informazioni sull'applicazione B2C dal portale di Azure, l'inserimento di tali informazioni nell'applicazione B2C in Creazione di siti Web e quindi l'associazione dell'applicazione B2C al sito e al canale.

### <a name="collect-the-required-application-information"></a>Raccogliere le informazioni sull'applicazione richieste

Per raccogliere le informazioni sull'applicazione richieste, attenersi alla seguente procedura.

1. Nel portale di Azure, andare a **Home \> Azure AD B2C - Applicazioni**.
1. Selezionare l'applicazione, quindi nel riquadro di navigazione a sinistra selezionare **Proprietà** per ottenere i dettagli dell'applicazione.
1. Nella casella **ID applicazione**, raccogliere l'ID applicazione dell'applicazione B2C creata nel tenant B2C. Successivamente verrà inserito come **GUID client** in Creazione di siti Web.
1. Sotto **URL di risposta**, raccogliere l'URL di risposta.
1. Andare a **Home \> Azure AD B2C - Flussi utente (criteri)** e quindi raccogliere i nomi di ciascun criterio di flusso utente.

L'immagine seguente mostra un esempio di pagina **Azure AD B2C - Applicazioni**.

![Passare all'applicazione B2C all'interno del tenant](./media/B2CImage_19.png)

L'immagine seguente mostra un esempio di pagina **Proprietà** dell'applicazione in Azure AD B2C. 

![Copiare l'ID applicazione dalle proprietà dell'applicazione B2C](./media/B2CImage_21.png)

L'immagine seguente mostra un esempio di criteri di flusso degli utenti nella pagina **Azure AD B2C - Flussi utente (criteri)**.

![Raccogliere i nomi di ciascun flusso di criteri B2C](./media/B2CImage_22.png)

### <a name="enter-your-aad-b2c-tenant-application-information-into-commerce"></a>Immettere le informazioni sull'applicazione del tenant AAD B2C in Commerce

È necessario inserire i dettagli del tenant Azure AD B2C in Creazione di siti Web di Commerce prima di associare il tenant B2C ai siti.

Per aggiungere le informazioni dell'applicazione tenant AAD B2C a Commerce, attenersi alla seguente procedura.

1. Accedere come amministratore a Creazione di siti Web di Commerce per l'ambiente.
1. Nel riquadro di spostamento a sinistra, selezionare **Impostazioni tenant** per espanderlo.
1. In **Impostazioni tenant**, selezionare **Impostazioni B2C**. 
1. Nella finestra principale accanto ad **Applicazioni B2C**, selezionare **Gestisci**. (Se il tenant viene visualizzato nell'elenco Applicazioni B2C, è stato già aggiunto da un amministratore. Verificare che gli elementi nel passaggio 6 di seguito corrispondano all'applicazione B2C).
1. Selezionare **Aggiungi applicazione B2C**.
1. Immettere i seguenti elementi richiesti nel modulo visualizzato, utilizzando i valori del tenant e dell'applicazione B2C. I campi non obbligatori (quelli senza asterisco) possono essere lasciati vuoti.

    - **Nome applicazione**: il nome dell'applicazione B2C, ad esempio "Fabrikam B2C".
    - **Nome tenant**: il nome del tenant B2C, ad esempio utilizzare "fabrikam" se il dominio è "fabrikam.onmicrosoft.com" per il tenant B2C. 
    - **ID criteri password dimenticata**: l'ID criteri flusso utente password dimenticata, ad esempio "B2C_1_PasswordReset".
    - **ID criteri di iscrizione e accesso**: l'ID dei criteri del flusso utente di iscrizione e accesso, ad esempio "B2C_1_signup_signin".
    - **GUID client**: l'ID applicazione B2C, ad esempio "22290eb2-c52e-42e9-8b35-a2b0a3bcb9e6".
    - **ID criteri modifica del profilo**: l'ID criteri flusso utente di modifica del profilo, ad esempio "B2C_1A_ProfileEdit".

1. Selezionare **OK**. Ora il nome dell'applicazione B2C appare nell'elenco.
1. Selezionare **Salva** per salvare le modifiche.

### <a name="associate-the-b2c-application-to-your-site-and-channel"></a>Associare l'applicazione B2C al sito e al canale

> [!WARNING]
> Se il sito è già associato a un'applicazione B2C, la modifica in un'altra applicazione B2C rimuoverà i riferimenti correnti stabiliti per gli utenti già registrati in questo ambiente. Se modificato, le credenziali associate all'applicazione B2C attualmente assegnata non saranno disponibili per gli utenti. 
> 
> Aggiornare l'applicazione B2C solo se si sta configurando l'applicazione B2C del canale per la prima volta o se si intende far iscrivere gli utenti con nuove credenziali a questo canale con la nuova applicazione B2C. Prestare attenzione quando si associano i canali alle applicazioni B2C e denominare chiaramente le applicazioni. Se un canale non viene associato a un'applicazione B2C nei passaggi seguenti, gli utenti che accedono a quel canale per il sito verranno inseriti nell'applicazione B2C mostrando **predefinito** nell'elenco **Impostazioni tenant \> Impostazioni B2C** di applicazioni B2C.

Per associare l'applicazione B2C al sito e al canale, seguire questi passaggi.

1. Andare al sito in Creazione di siti Web di Commerce.
1. Nel riquadro di spostamento sinistro, selezionare **Impostazioni sito** per espanderlo.
1. Sotto **Impostazioni del sito**, selezionare **Canali**.
1. Nella finestra principale sotto **Canali**, selezionare il canale.
1. Nel riquadro delle proprietà del canale a destra, selezionare il nome dell'applicazione B2C nel menu a discesa **Seleziona applicazione B2C**.
1. Selezionare **Chiudi**, quindi selezionare **Salva e pubblica**.

## <a name="additional-b2c-information"></a>Ulteriori informazioni su B2C

### <a name="customer-migration"></a>Migrazione del cliente

Se si sta valutando la migrazione dei record dei clienti da una precedente piattaforma del provider di identità, è opportuno collaborare con il team Dynamics 365 Commerce per esaminare le esigenze di migrazione dei clienti.

Per altra documentazione Azure AD B2C sulla migrazione dei clienti, vedere [Migrare gli utenti ad Azure Active Directory B2C](https://docs.microsoft.com/azure/active-directory-b2c/active-directory-b2c-user-migration).

### <a name="custom-policies"></a>Criteri personalizzati

Per ulteriori informazioni sulla personalizzazione dei flussi di criteri e delle interazioni Azure AD B2C oltre quanto offerto dai criteri standard B2C, vedere [Criteri personalizzati in Azure Active Directory B2C](https://docs.microsoft.com/azure/active-directory-b2c/active-directory-b2c-overview-custom). 

### <a name="secondary-admin"></a>Amministratore secondario

Un account amministratore secondario facoltativo può essere aggiunto nella sezione **Utenti** del tenant B2C. Questo può essere un account diretto o un account generale. Se è necessario condividere un account tra le risorse del team, è anche possibile creare un account comune. A causa della sensibilità dei dati memorizzati in Azure AD B2C, un account comune deve essere attentamente monitorato secondo le procedure di sicurezza dell'azienda.

## <a name="additional-resources"></a>Risorse aggiuntive

[Configurare il proprio nome di dominio](configure-your-domain-name.md)

[Distribuire un nuovo tenant di e-commerce](deploy-ecommerce-site.md)

[Creare un sito di e-commerce](create-ecommerce-site.md)

[Associare un sito Dynamics 365 Commerce a un canale online](associate-site-online-store.md)

[Gestire i file robots.txt](manage-robots-txt-files.md)

[Caricare i reindirizzamenti URL in blocco](upload-bulk-redirects.md)Associare un sito Dynamics 365 Commerce a un canale online

[Impostare pagine personalizzate per l'accesso degli utenti](custom-pages-user-logins.md)

[Configurare più tenant B2C in un ambiente Commerce](configure-multi-B2C-tenants.md)

[Aggiungere il supporto per una rete per la distribuzione di contenuti (CDN)](add-cdn-support.md)

[Abilitare il rilevamento del punto vendita basato sull'ubicazione](enable-store-detection.md)
