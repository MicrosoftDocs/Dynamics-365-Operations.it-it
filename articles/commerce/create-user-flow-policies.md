---
title: Creare criteri di flusso utente
description: Questo articolo descrive come creare criteri di flusso utente nel portale di Microsoft Azure.
author: BrianShook
ms.date: 11/15/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2020-02-13
ms.openlocfilehash: 91b9d99dfd8c3d100ca197aa499ca86799bbffc8
ms.sourcegitcommit: 774f8f97a0b14cf1199bd1802178ccf536a25ade
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/17/2022
ms.locfileid: "9785303"
---
# <a name="create-user-flow-policies"></a>Creare criteri di flusso utente

[!include [banner](includes/banner.md)]

Questo articolo descrive come creare criteri di flusso utente nel portale di Microsoft Azure.

I flussi di utenti sono i criteri utilizzati da Azure Active Directory (Azure AD) B2C per fornire le esperienze utente di accesso sicuro, registrazione, modifica del profilo e password dimenticata. Dynamics 365 Commerce utilizza questi flussi per eseguire le azioni dei criteri per interagire con il tenant Azure AD B2C. Quando un utente interagisce con questi criteri, vengono reindirizzati al tenant Azure AD B2C per eseguire le azioni.

Azure AD B2C offre tre tipi di flusso utente di base:
- Iscrizione e accesso
- Modifica del profilo
- Password reimpostata

È possibile scegliere di utilizzare i flussi utente predefiniti forniti da Azure AD, che visualizzano una pagina ospitata da Azure AD B2C. In alternativa, è possibile creare una pagina HTML per controllare l'aspetto di queste esperienze di flusso utente. 

Per personalizzare le pagine dei criteri utente con le pagine create in Dynamics 365 Commerce vedi [Impostare pagine personalizzate per gli accessi utente](custom-pages-user-logins.md). Per altre informazioni, vedere [Personalizzare l'interfaccia delle esperienze utente in Azure Active Directory B2C](/azure/active-directory-b2c/tutorial-customize-ui).

### <a name="create-a-sign-up-and-sign-in-user-flow-policy"></a>Creare criteri di accesso e iscrizione nel flusso utente

Per creare i criteri di accesso e iscrizione nel flusso utente, effettuare le seguenti operazioni.

1. Nel portale di Azure selezionare **Flussi utente (criteri)** nel pannello di navigazione a sinistra.
1. Nella pagina **Azure AD B2C - Flussi utente (criteri)**, selezionare **Nuovo flusso utente**.
1. Seleziona il criterio **Iscrizione e accesso**, quindi seleziona la versione **Consigliato**.
1. Sotto **Nome**, immettere un nome per i criteri. Questo nome verrà visualizzato in seguito con un prefisso assegnato dal portale (ad esempio "B2C_1_").
1. Sotto **Provider di identità**, nella sezione **Account locali** seleziona **Iscrizione e-mail**. L'autenticazione e-mail viene utilizzata negli scenari più comuni per Commerce. Se stai utilizzando anche l'autenticazione del provider di identità social, puoi anche selezionarli in questo momento.
1. Sotto **Autenticazione a più fattori**, selezionare la scelta appropriata per l'azienda. 
1. Sotto **Attributi e attestazioni dell'utente**, selezionare le opzioni per raccogliere gli attributi o restituire le attestazioni, a seconda dei casi. Seleziona **Mostra altro...** per ottenere l'elenco completo degli attributi e delle opzioni di richiesta. Commerce richiede le seguenti opzioni predefinite:

    | **Raccogli attributo** | **Restituisci attestazione** |
    | ---------------------- | ----------------- |
    | Indirizzo di posta elettronica          | Indirizzi di posta elettronica   |
    | Nome specificato             | Nome specificato        |
    |                        | Provider di identità |
    | Cognome                | Cognome           |
    |                        | ID oggetto dell'utente  |

1. Selezionare **Crea**.

L'immagine seguente è un esempio di criteri di accesso e iscrizione Azure AD B2C nel flusso utente.

![Impostazioni dei criteri di iscrizione e accesso.](./media/B2CImage_11.png)

   
### <a name="create-a-profile-editing-user-flow-policy"></a>Creare i criteri di flusso utente per la modifica del profilo

Per creare i criteri di flusso utente per la modifica del profilo, effettuare le seguenti operazioni.

1. Nel portale di Azure selezionare **Flussi utente (criteri)** nel pannello di navigazione a sinistra.
1. Nella pagina **Azure AD B2C - Flussi utente (criteri)**, selezionare **Nuovo flusso utente**.
1. Seleziona **Modifica del profilo**, quindi seleziona la versione **Consigliato**.
1. Sotto **Nome**, immettere il flusso utente per la modifica del profilo. Questo nome verrà visualizzato in seguito con un prefisso assegnato dal portale (ad esempio "B2C_1_").
1. Sotto **Provider di identità**, nella sezione **Account locali** seleziona **Accesso e-mail**.
1. In **Attributi utente** selezionare una delle seguenti caselle di controllo:
    
    | **Raccogli attributo** | **Restituisci attestazione** |
    | ---------------------- | ----------------- |
    |                        | Indirizzi di posta elettronica   |
    | Nome specificato             | Nome specificato        |
    |                        | Provider di identità |
    | Cognome                | Cognome           |
    |                        | ID oggetto dell'utente  |
    
1. Selezionare **Crea**.

L'immagine seguente mostra un esempio di flusso utente per la modifica del profilo Azure AD B2C.

![Esempio del profilo Azure AD B2C che modifica il flusso utente](./media/B2CImage_12.png)

### <a name="create-a-password-reset-user-flow-policy"></a>Creare un flusso utente per la reimpostazione della password

Per creare i criteri di flusso utente per la reimpostazione della password, effettuare le seguenti operazioni.

1. Nel portale di Azure selezionare **Flussi utente (criteri)** nel pannello di navigazione a sinistra.
1. Nella pagina **Azure AD B2C - Flussi utente (criteri)**, selezionare **Nuovo flusso utente**.
1. Seleziona **Reimpostazione password**, quindi seleziona la versione **Consigliato**.
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

## <a name="next-steps"></a>Passaggi successivi

Per continuare il processo di configurazione di un tenant B2C in Commerce, passa a [Aggiungere provider di identità social](add-social-identity-providers.md).

## <a name="additional-resources"></a>Risorse aggiuntive

[Impostare un tenant B2C in Commerce](set-up-b2c-tenant.md)

[Creare o collegare un tenant Azure AD B2C esistente nel portale di Azure](create-link-aad-b2c-tenant.md)

[Creare l'applicazione B2C](create-b2c-app.md)

[Aggiungere provider di identità social (facoltativo)](add-social-identity-providers.md)

[Aggiornare Commerce headquarters con le nuove informazioni di Azure AD B2C](update-hq-aad-b2c-info.md)

[Configurare il tenant B2C in Creazione di siti Web di Commerce](config-b2c-tenant-site-builder.md)

[Ulteriori informazioni su B2C](additional-b2c-info.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
