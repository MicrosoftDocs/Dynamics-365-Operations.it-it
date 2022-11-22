---
title: Ulteriori informazioni su B2C
description: Questo articolo fornisce informazioni aggiuntive su come impostare il tenant business-to-consumer (B2C) in Microsoft Dynamics 365 Commerce.
author: BrianShook
ms.date: 11/14/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2020-02-13
ms.openlocfilehash: b60ef15544cd30c44968ee7a588a8a9fb08e8223
ms.sourcegitcommit: 774f8f97a0b14cf1199bd1802178ccf536a25ade
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/17/2022
ms.locfileid: "9785267"
---
# <a name="additional-b2c-information"></a>Ulteriori informazioni su B2C

[!include [banner](includes/banner.md)]

Questo articolo fornisce informazioni aggiuntive su come impostare il tenant business-to-consumer (B2C) in Microsoft Dynamics 365 Commerce.

### <a name="customer-migration"></a>Migrazione del cliente

Se si sta valutando la migrazione dei record dei clienti da una precedente piattaforma del provider di identità, è opportuno collaborare con il team Dynamics 365 Commerce per esaminare le esigenze di migrazione dei clienti.

Per altra documentazione Azure AD B2C sulla migrazione dei clienti, vedere [Migrare gli utenti ad Azure Active Directory B2C](/azure/active-directory-b2c/active-directory-b2c-user-migration).

### <a name="custom-policies"></a>Criteri personalizzati

Per ulteriori informazioni sulla personalizzazione dei flussi di criteri e delle interazioni Azure AD B2C oltre quanto offerto dai criteri standard B2C, vedere [Criteri personalizzati in Azure Active Directory B2C](/azure/active-directory-b2c/active-directory-b2c-overview-custom). 

### <a name="secondary-admin"></a>Amministratore secondario

Un account amministratore secondario facoltativo può essere aggiunto nella sezione **Utenti** del tenant B2C. Questo può essere un account diretto o un account generale. Se è necessario condividere un account tra le risorse del team, è anche possibile creare un account comune. A causa della sensibilità dei dati memorizzati in Azure AD B2C, un account comune deve essere attentamente monitorato secondo le procedure di sicurezza dell'azienda.

### <a name="set-up-a-custom-sign-in-domain"></a>Configurare un dominio di accesso personalizzato

Azure AD B2C consente di configurare un dominio di accesso personalizzato per il tenant Azure AD B2C. Per istruzioni, vedere [Abilitare domini personalizzati per Azure Active Directory B2C](/azure/active-directory-b2c/custom-domain). 

Se utilizzi un dominio di accesso personalizzato, il dominio deve essere inserito in Commerce Site Builder.

Per immettere un dominio di accesso personalizzato in Site Builder seguire questi passaggi.

1. Nell'angolo superiore destro di Site Builder, seleziona l'opzione per cambaire sito, quindi seleziona **Gestisci siti**.
1. Nel riquadro di spostamento sinistro, seleziona **Impostazioni tenant \> Configurazione autenticazione sito**.
1. Nella sezione **Profili di autenticazione sito**, seleziona **Gestisci**.
1. Nel menu a comparsa sulla destra, seleziona il pulsante **Modifica** (simbolo della matita) accanto al profilo di autenticazione del sito per il quale vuoi inserire un dominio personalizzato.
1. Nella finestra di dialogo **Modifica profilo di autenticazione sito**, in **Dominio personalizzato per l'accesso**, inserisci il tuo dominio di accesso personalizzato (ad esempio, "login.fabrikam.com").

> [!WARNING]
> Quando esegui l'aggiornamento a un dominio personalizzato per il tenant Azure AD B2C, la modifica ha impatto sui dettagli dell'emittente del tenant per il token generato. I dettagli dell'emittente includeranno quindi il dominio personalizzato anziché il dominio predefinito fornito da Azure AD B2C. Una diversa configurazione di **Emittente** in Commerce headquarters (**Retail e Commerce \> Impostazione sedi centrali \> Parametri \> Parametri condivisi di commercio \> Provider di identità**) modifica l'interazione del sistema con gli utenti del sito, creando potenzialmente un nuovo record cliente se un utente sta eseguendo l'autenticazione a fronte del nuovo emittente. Eventuali modifiche al dominio personalizzato devono essere testate a fondo prima di passare al dominio personalizzato in un ambiente Azure AD B2C live.

## <a name="additional-resources"></a>Risorse aggiuntive

[Impostare un tenant B2C in Commerce](set-up-b2c-tenant.md)

[Creare o collegare un tenant Azure AD B2C esistente nel portale di Azure](create-link-aad-b2c-tenant.md)

[Creare l'applicazione B2C](create-b2c-app.md)

[Creare criteri di flusso utente](create-user-flow-policies.md)

[Aggiungere provider di identità social (facoltativo)](add-social-identity-providers.md)

[Aggiornare Commerce headquarters con le nuove informazioni di Azure AD B2C](update-hq-aad-b2c-info.md)

[Configurare il tenant B2C in Creazione di siti Web di Commerce](config-b2c-tenant-site-builder.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
