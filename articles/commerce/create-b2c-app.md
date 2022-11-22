---
title: Creare un'applicazione B2C
description: Questo articolo descrive come creare un'applicazione business-to-consumer (B2C) nel portale di Microsoft Azure.
author: BrianShook
ms.date: 11/15/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2020-02-13
ms.openlocfilehash: d8956d51bac7bf2a162a370ae5ef1c7e7cdc1e2f
ms.sourcegitcommit: 774f8f97a0b14cf1199bd1802178ccf536a25ade
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/17/2022
ms.locfileid: "9785285"
---
# <a name="create-a-b2c-application"></a>Creare un'applicazione B2C

[!include [banner](includes/banner.md)]

Questo articolo descrive come creare un'applicazione business-to-consumer (B2C) nel portale di Microsoft Azure.

Una volta creato il tenant B2C, verrà creata un'applicazione B2C nel tuo nuovo tenant Azure Active Directory (Azure AD) per interagire con Commerce.

Per creare l'applicazione B2C, attenersi alla procedura seguente.

1. Nel portale di Azure, seleziona **Registrazioni app**, quindi seleziona **Nuova registrazione**.
1. Sotto **Nome**, inserisci il nome da assegnare a questa applicazione Azure AD B2C.
1. Sotto **Tipi di account supportati**, seleziona **Account in qualsiasi provider di identità o directory dell'organizzazione (per autenticare gli utenti con flussi utente)**.
1. Per **URI di reindirizzamento**, inserisci i tuoi URL di risposta dedicati come tipo **Web**. Per informazioni sugli URL di risposta e su come formattarli, vedi [URL di risposta](#reply-urls) di seguito. È necessario inserire un URI di reindirizzamento/URL di risposta per abilitare i reindirizzamenti da Azure AD B2C al tuo sito quando un utente si autentica. L'URL di risposta può essere aggiunto durante il processo di registrazione o può essere aggiunto in un secondo momento selezionando il collegamento **Aggiungi un URI di reindirizzamento** dal menu **Panoramica** nella sezione **Panoramica** dell'applicazione B2C.
1. Per **Autorizzazioni**, seleziona **Concedi il consenso dell'amministratore alle autorizzazioni openid e offline_access**.
1. Seleziona **Registro**.
1. Seleziona l'applicazione appena creata e vai al menu **Autenticazione**. 
1. Se viene inserito un URL di risposta, in **Concessione implicita e flussi ibridi** seleziona entrambe le opzioni **Token di accesso** e **Token ID** per abilitarle per l'applicazione, quindi seleziona **Salva**. Se durante la registrazione non è stato inserito un URL di risposta, è possibile aggiungerlo anche in questa pagina selezionando **Aggiungi una piattaforma**, selezionando **Web** e quindi immettendo l'URI di reindirizzamento dell'applicazione. La sezione **Concessione implicita e flussi ibridi** sarà quindi disponibile per selezionare entrambe le opzioni **Token di accesso** e **Token ID**.
1. Vai al menu **Panoramica** del portale di Azure e copia l'**ID applicazione (client)**. Prendi nota di questo ID per i passaggi di configurazione successivi (indicato in seguito come **GUID client**).

Per ulteriori riferimenti sulle registrazioni delle app in Azure AD B2C, vedi [La nuova esperienza di registrazione delle app per Azure Active Directory B2C](/azure/active-directory-b2c/app-registrations-training-guide)

### <a name="reply-urls"></a>URL di risposta

Gli URL di risposta sono importanti in quanto forniscono un elenco dei domini di ritorno consentiti quando il sito chiama Azure AD B2C per autenticare un utente. Ciò consente il ritorno dell'utente autenticato al dominio dal quale sta accedendo (dominio del sito). 

Nella casella **URL di risposta** nella schermata **Azure AD B2c - Applicazioni \> Nuova applicazione**, è necessario aggiungere righe separate per il dominio del sito e (una volta effettuato il provisioning dell'ambiente) per l'URL generato da Commerce. Questi URL devono sempre utilizzare un formato URL valido e devono essere solo URL di base (nessuna barra o percorso). La stringa ``/_msdyn365/authresp`` quindi deve essere aggiunta agli URL di base, come nei seguenti esempi.

- ``https://www.fabrikam.com/_msdyn365/authresp``(Il dominio dovrebbe corrispondere completamente al dominio e-commerce. Se hai più domini, devi aggiungere questo URL per ogni dominio.)
- ``https://fabrikam-prod.commerce.dynamics.com/_msdyn365/authresp``

## <a name="next-steps"></a>Passaggi successivi

Per continuare il processo di configurazione di un tenant B2C in Commerce, passa a [Creare criteri di flusso utente](create-user-flow-policies.md).

## <a name="additional-resources"></a>Risorse aggiuntive

[Impostare un tenant B2C in Commerce](set-up-b2c-tenant.md)

[Creare o collegare un tenant Azure AD B2C esistente nel portale di Azure](create-link-aad-b2c-tenant.md)

[Creare criteri di flusso utente](create-user-flow-policies.md)

[Aggiungere provider di identità social (facoltativo)](add-social-identity-providers.md)

[Aggiornare Commerce headquarters con le nuove informazioni di Azure AD B2C](update-hq-aad-b2c-info.md)

[Configurare il tenant B2C in Creazione di siti Web di Commerce](config-b2c-tenant-site-builder.md)

[Ulteriori informazioni su B2C](additional-b2c-info.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
