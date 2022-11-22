---
title: Aggiungere provider di identità social
description: Questo articolo descrive come aggiungere provider di identità social nel portale di Microsoft Azure.
author: BrianShook
ms.date: 11/15/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2020-02-13
ms.openlocfilehash: 5596097a5484acafda54adcfffa68fb59c8fbc65
ms.sourcegitcommit: 774f8f97a0b14cf1199bd1802178ccf536a25ade
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/17/2022
ms.locfileid: "9785284"
---
# <a name="add-social-identity-providers"></a>Aggiungere provider di identità social

[!include [banner](includes/banner.md)]

Questo articolo descrive come aggiungere provider di identità social nel portale di Microsoft Azure.

I provider di identità social consentono agli utenti di utilizzare i propri account social per l'autenticazione. L'aggiunta dell'autenticazione del provider di identità social è facoltativa in Dynamics 365 Commerce. 

Se non viene aggiunta l'autenticazione del provider di identità social, i profili predefiniti Azure Active Directory (Azure AD) B2C saranno i profili principali per la base di utenti. Gli utenti selezioneranno il proprio nome utente (l'indirizzo e-mail preferito) e imposteranno una password. Azure AD B2C autenticherà direttamente gli utenti. 

Se viene aggiunta l'autenticazione del provider di identità social e un utente sceglie uno dei provider di identità social offerti, un'entità viene comunque creata nel tenant Azure AD B2C. Azure AD B2C autenticherà quindi le credenziali dell'utente con il provider di identità social.

> [!NOTE]
> L'accesso del provider di identità crea un record nel tenant B2C, ma in un formato diverso rispetto agli account locali poiché chiamerà il riferimento del provider di identità social esterno per l'autenticazione. L'utente può utilizzare lo stesso indirizzo e-mail tra i provider di identità social, il che significa che il nome utente e-mail utilizzato per l'autenticazione potrebbe non essere univoco per il tenant. Azure AD B2C richiede solo che gli utenti dispongano di un indirizzo e-mail univoco sugli account B2C locali.

Prima di poter aggiungere un provider di identità social per l'autenticazione, è necessario accedere al portale del provider di identità e configurare un'applicazione del provider di identità come indicato nella documentazione di Azure AD B2C. Di seguito viene fornito un elenco di collegamenti alla documentazione.

- [Amazon](/azure/active-directory-b2c/active-directory-b2c-setup-amzn-app)
- [Azure AD (Tenant singolo)](/azure/active-directory-b2c/active-directory-b2c-setup-oidc-azure-active-directory)
- [Account Microsoft](/azure/active-directory-b2c/active-directory-b2c-setup-msa-app)
- [Facebook](/azure/active-directory-b2c/active-directory-b2c-setup-fb-app)
- [GitHub](/azure/active-directory-b2c/active-directory-b2c-setup-github-app)
- [Google](/azure/active-directory-b2c/active-directory-b2c-setup-goog-app)
- [LinkedIn](/azure/active-directory-b2c/active-directory-b2c-setup-li-app)
- [OpenID Connect](/azure/active-directory-b2c/active-directory-b2c-setup-oidc-idp)
- [Twitter](/azure/active-directory-b2c/active-directory-b2c-setup-twitter-app)

### <a name="add-and-set-up-a-social-identity-provider"></a>Aggiungere e impostare un provider di identità social

> [!NOTE]
> L'aggiunta di provider di identità social è un passaggio facoltativo durante la configurazione di un tenant business-to-consumer (B2C) in Microsoft Dynamics 365 Commerce.

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
1. Per allegare il criterio di flusso utente di accesso/iscrizione, selezionare ciascun provider di identità impostato per l'account. Per testare i flussi, selezionare **Esegui flusso utente** per ciascun provider di identità. Una nuova scheda visualizza la pagina di accesso con la casella di selezione del nuovo provider di identità.

L'immagine seguente mostra esempi delle schermate **Aggiungi provider di identità** e **Imposta il provider di identità social** in Azure AD B2C.

![Aggiunta di un provider di identità social all'applicazione.](./media/B2CImage_14.png)

L'immagine seguente mostra un esempio di come selezionare i provider di identità nella pagina **Provider di identità** di Azure AD B2C.

![Selezionare ciascun provider di identità social da abilitare per i criteri.](./media/B2CImage_16.png)

L'immagine seguente mostra un esempio di schermata di accesso predefinita con un pulsante di accesso del provider di identità social visualizzato.

> [!NOTE]
> Se usi le pagine personalizzate create in Commerce per i flussi utente, sarà necessario aggiungere i pulsanti per i provider di identità social utilizzando le funzionalità di estensibilità della libreria del modulo Commerce. Inoltre, quando si configurano le applicazioni con uno specifico provider di identità social, in alcuni casi l'URL o le stringhe di configurazione potrebbero fare distinzione tra maiuscole e minuscole. Fai riferimento alle istruzioni di connessione del provider di identità social per ulteriori informazioni.
 
![Esempio di schermata di accesso predefinita con il pulsante di accesso al provider di identità social visualizzato.](./media/B2CImage_17.png)

## <a name="next-steps"></a>Passaggi successivi

Per continuare il processo di configurazione di un tenant B2C in Commerce, passa a [Aggiornare Commerce headquarters con le nuove informazioni di Azure AD B2C](update-hq-aad-b2c-info.md).

## <a name="additional-resources"></a>Risorse aggiuntive

[Impostare un tenant B2C in Commerce](set-up-b2c-tenant.md)

[Creare o collegare un tenant Azure AD B2C esistente nel portale di Azure](create-link-aad-b2c-tenant.md)

[Creare l'applicazione B2C](create-b2c-app.md)

[Creare criteri di flusso utente](create-user-flow-policies.md)

[Aggiornare Commerce headquarters con le nuove informazioni di Azure AD B2C](update-hq-aad-b2c-info.md)

[Configurare il tenant B2C in Creazione di siti Web di Commerce](config-b2c-tenant-site-builder.md)

[Ulteriori informazioni su B2C](additional-b2c-info.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
