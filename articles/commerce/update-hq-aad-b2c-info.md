---
title: Aggiornare Commerce headquarters con le nuove informazioni Azure AD B2C
description: Questo articolo descrive come aggiornare Microsoft Dynamics 365 Commerce Commerce headquarters con nuove informazioni business-to-consumer (B2C) di Azure Active Directory (Azure AD).
author: BrianShook
ms.date: 11/15/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2020-02-13
ms.openlocfilehash: c65949ff97182d2692319ac2af00e3ef35a79580
ms.sourcegitcommit: 774f8f97a0b14cf1199bd1802178ccf536a25ade
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/17/2022
ms.locfileid: "9785321"
---
# <a name="update-commerce-headquarters-with-the-new-azure-ad-b2c-information"></a>Aggiornare Commerce headquarters con le nuove informazioni Azure AD B2C

[!include [banner](includes/banner.md)]

Questo articolo descrive come aggiornare Microsoft Dynamics 365 Commerce Commerce headquarters con nuove informazioni business-to-consumer (B2C) di Azure Active Directory (Azure AD).

Una volta completati i passaggi di provisioning di Azure AD B2C precedenti, l'applicazione Azure AD B2C deve essere registrata nell'ambiente Dynamics 365 Commerce.

Per aggiornare headquarters con le nuove informazioni Azure AD B2C, attenersi alla seguente procedura.

1. In Commerce, andare a **Parametri condivisi di Commerce** e selezionare **Provider di identità** nel menu a sinistra.
1. Sotto **Provider di identità**, effettuare quanto segue:
    1. Nella casella **Emittente**, inserire la stringa dell'emittente del provider di identità. Per trovare la stringa dell'emittente, vedere [Ottenere la stringa dell'emittente per l'impostazione delle sedi centrali](#obtain-issuer-string-for-headquarters-setup) qui di seguito.
    1. Nella casella **Nome** immettere un nome per il record emittente.
    1. Nella casella **Tipo**, immettere **Azure AD B2C (id_token)**.
1. Sotto **Parti affidabili**, con l'elemento del provider di identità B2C sopra selezionato selezionato, procedere come segue:
    1. Nella casella **ID client** casella, inserisci il tuo ID applicazione B2C, che puoi trovare nella casella **ID applicazione** della pagina delle proprietà dell'applicazione B2C.
    1. Nella casella **Tipo**, immettere **Pubblico**.
    1. Nella casella **Tipo utente**, immettere **Cliente**.
1. Nel riquadro azioni selezionare **Salva**.
1. Nella casella di ricerca Commerce, cercare **Programmazione di distribuzione**
1. Nel menu di navigazione a sinistra della pagina **Programmazioni di distribuzione**, selezionare il processo **1110 Configurazione globale**.
1. Nel riquadro azioni selezionare **Esegui adesso**.

### <a name="obtain-issuer-string-for-headquarters-setup"></a>Ottenere la stringa dell'emittente per l'impostazione delle sedi centrali

Per ottenere la stringa dell'emittente del provider di identità, attenersi alla seguente procedura.

1. Nella pagina Azure AD B2C del portale di Azure, vai al tuo flusso utente **Iscrizione e accesso**.
1. Seleziona **Layout di pagina** nel menu di spostamento a sinistra, sotto **Nome layout** seleziona **Pagina di iscrizione o accesso unificata** e quindi seleziona **Esegui flusso utente**.
1. Assicurati che la tua applicazione sia impostata sull'applicazione Azure AD B2C creata sopra, quindi seleziona il flusso utente visualizzato sotto l'intestazione **Esegui flusso utente** che include ``.../.well-known/openid-configuration?p=<B2CSIGN-INPOLICY>``. (Non selezionare **Esegui flusso utente**). Si aprirà una nuova scheda che mostra i metadati per il criterio di raccolta della stringa emittente.
1. Nella pagina dei metadati visualizzata nella scheda del browser, copia la stringa dell'emittente del provider di identità (il valore per **emittente** che inizia con "https://" e termina con "/v2.0/" ) simile al seguente esempio.
   - ``https://login.fabrikam.com/011115c3-0113-4f43-b5e2-df01266e24ae/v2.0/``.
 
**OPPURE**: Per creare manualmente lo stesso URL di metadati, esegui i passaggi seguenti.

1. Creare un URL di indirizzo metadati nel seguente formato usando il tenant e i criteri B2C: ``https://<B2CTENANTNAME>.b2clogin.com/<B2CTENANTNAME>.onmicrosoft.com/v2.0/.well-known/openid-configuration?p=<B2CSIGN-INPOLICY>``
    - Esempio: ``https://d365plc.b2clogin.com/d365plc.onmicrosoft.com/v2.0/.well-known/openid-configuration?p=B2C_1_signinup``.
1. Immettere l'URL dell'indirizzo dei metadati nella barra degli indirizzi del browser.
1. Nei metadati, copiare l'URL dell'emittente del provider di identità (il valore per **"emittente"**).
    - Esempio: ``https://login.fabrikam.com/011115c3-0113-4f43-b5e2-df01266e24ae/v2.0/``.

## <a name="next-steps"></a>Passaggi successivi

Per continuare il processo di configurazione di un tenant B2C in Commerce, procedi a [Configurare il tenant B2C in Commerce Site Builder](config-b2c-tenant-site-builder.md).

## <a name="additional-resources"></a>Risorse aggiuntive

[Impostare un tenant B2C in Commerce](set-up-b2c-tenant.md)

[Creare o collegare un tenant Azure AD B2C esistente nel portale di Azure](create-link-aad-b2c-tenant.md)

[Creare l'applicazione B2C](create-b2c-app.md)

[Creare criteri di flusso utente](create-user-flow-policies.md)

[Aggiungere provider di identità social (facoltativo)](add-social-identity-providers.md)

[Configurare il tenant B2C in Creazione di siti Web di Commerce](config-b2c-tenant-site-builder.md)

[Ulteriori informazioni su B2C](additional-b2c-info.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
