---
title: Configurare il tenant B2C in Creazione di siti Web di Commerce
description: Questo articolo descrive come configurare il tenant business-to-consumer (B2C) nella creazione di siti di Microsoft Dynamics 365 Commerce.
author: BrianShook
ms.date: 11/15/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2020-02-13
ms.openlocfilehash: 181edf1570f1a9d071a7fae38ff9d73ff3c068fa
ms.sourcegitcommit: 774f8f97a0b14cf1199bd1802178ccf536a25ade
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/17/2022
ms.locfileid: "9785320"
---
# <a name="configure-your-b2c-tenant-in-commerce-site-builder"></a>Configurare il tenant B2C in Creazione di siti Web di Commerce

[!include [banner](includes/banner.md)]

Questo articolo descrive come configurare il tenant business-to-consumer (B2C) nella creazione di siti di Microsoft Dynamics 365 Commerce.

Una volta impostato il tenant Azure AD B2C, è necessario configurare il tenant B2C in Creazione di siti Web di Commerce. I passaggi della configurazione includono la raccolta di informazioni sull'applicazione B2C dal portale di Azure, l'inserimento di tali informazioni nell'applicazione B2C in Creazione di siti Web e quindi l'associazione dell'applicazione B2C al sito e al canale.

### <a name="collect-the-required-application-information"></a>Raccogliere le informazioni sull'applicazione richieste

Per raccogliere le informazioni sull'applicazione richieste, attenersi alla seguente procedura.

1. Nel portale di Azure, andare a **Home \> Azure AD B2C - Registrazioni app**.
1. Selezionare l'applicazione, quindi nel riquadro di navigazione a sinistra selezionare **Panoramica** per ottenere i dettagli dell'applicazione.
1. Dal riferimento **ID (client) applicazione**, raccogliere l'ID applicazione dell'applicazione B2C creata nel tenant B2C. Successivamente verrà inserito come **GUID client** in Creazione di siti Web.
1. Selezionare **Reindirizzare URI** e raccogli l'URL di risposta mostrato per il tuo sito (l'URL di risposta inserito durante l'installazione).
1. Andare a **Home \> Azure AD B2C - Flussi utente** e quindi raccogliere i nomi completi di ciascun criterio di flusso utente.

L'immagine seguente mostra un esempio di pagina di panoramica **Azure AD B2C - Registrazioni app**.

![La pagina di panoramica Azure AD B2C - Registrazioni app con l'ID dell'applicazione (client)](./media/ClientGUID_Application_AzurePortal.png)

L'immagine seguente mostra un esempio di criteri di flusso degli utenti nella pagina **Azure AD B2C - Flussi utente (criteri)**.

![Raccogliere i nomi di ciascun flusso di criteri B2C.](./media/B2CImage_22.png)

### <a name="enter-your-azure-ad-b2c-tenant-application-information-into-commerce"></a>Immettere le informazioni sull'applicazione del tenant Azure AD B2C in Commerce

È necessario inserire i dettagli del tenant Azure AD B2C in Creazione di siti Web di Commerce prima di associare il tenant B2C ai siti.

Per aggiungere le informazioni dell'applicazione tenant Azure AD B2C a Commerce, attieniti alla seguente procedura.

1. Accedere come amministratore a Creazione di siti Web di Commerce per l'ambiente.
1. Nel riquadro di spostamento a sinistra, selezionare **Impostazioni tenant** per espanderlo.
1. In **Impostazioni tenant**, seleziona **Configurazione autenticazione sito**. 
1. Nella finestra principale accanto a **Profili di autenticazione sito**, seleziona **Gestisci**. (Se il tenant viene visualizzato nell'elenco dei profili di autenticazione del sito, è stato già aggiunto da un amministratore. Verifica che gli elementi nel passaggio 6 di seguito corrispondano alla configurazione B2C che hai scelto. È anche possibile creare un nuovo profilo utilizzando tenant Azure AD B2C simili o applicazioni per tenere conto di differenze minori, come ID criteri utente diversi.
1. Seleziona **Aggiungi profilo di autenticazione sito**
1. Immettere i seguenti elementi richiesti nel modulo visualizzato, utilizzando i valori del tenant e dell'applicazione B2C. I campi non obbligatori (quelli senza asterisco) possono essere lasciati vuoti.

    - **Nome applicazione**: il nome dell'applicazione B2C, ad esempio "Fabrikam B2C".
    - **Nome tenant**: il nome del tenant B2C, ad esempio utilizzare "fabrikam" se il dominio è "fabrikam.onmicrosoft.com" per il tenant B2C. 
    - **ID criteri password dimenticata**: l'ID criteri flusso utente password dimenticata, ad esempio "B2C_1_PasswordReset".
    - **ID criteri di iscrizione e accesso**: l'ID dei criteri del flusso utente di iscrizione e accesso, ad esempio "B2C_1_signup_signin".
    - **GUID client**: l'ID applicazione B2C, ad esempio "22290eb2-c52e-42e9-8b35-a2b0a3bcb9e6".
    - **ID criteri modifica del profilo**: l'ID criteri flusso utente di modifica del profilo, ad esempio "B2C_1A_ProfileEdit".

1. Selezionare **OK**. Ora il nome dell'applicazione B2C appare nell'elenco.
1. Selezionare **Salva** per salvare le modifiche.

Il campo **Dominio personalizzato per l'accesso** facoltativo deve essere utilizzato solo se stai configurando un dominio personalizzato per il tenant Azure AD B2C. Per ulteriori dettagli e considerazioni sull'utilizzo del campo **Dominio personalizzato per l'accesso**, vedi [Ulteriori informazioni su B2C](additional-b2c-info.md).

### <a name="associate-the-b2c-application-to-your-site-and-channel"></a>Associare l'applicazione B2C al sito e al canale

> [!WARNING]
> - Se il sito è già associato a un'applicazione B2C, la modifica in un'altra applicazione B2C rimuoverà i riferimenti correnti stabiliti per gli utenti già registrati in questo ambiente. Se modificato, le credenziali associate all'applicazione B2C attualmente assegnata non saranno disponibili per gli utenti. 
> - Aggiornare l'applicazione B2C solo se si sta configurando l'applicazione B2C del canale per la prima volta o se si intende far iscrivere gli utenti con nuove credenziali a questo canale con la nuova applicazione B2C. Prestare attenzione quando si associano i canali alle applicazioni B2C e denominare chiaramente le applicazioni. Se un canale non viene associato a un'applicazione B2C nei passaggi seguenti, gli utenti che accedono a quel canale per il sito verranno inseriti nell'applicazione B2C mostrando **predefinito** nell'elenco **Impostazioni tenant \> Impostazioni B2C** di applicazioni B2C.

Per associare l'applicazione B2C al sito e al canale, seguire questi passaggi.

1. Andare al sito in Creazione di siti Web di Commerce.
1. Nel riquadro di spostamento sinistro, selezionare **Impostazioni sito** per espanderlo.
1. Sotto **Impostazioni del sito**, selezionare **Canali**.
1. Nella finestra principale sotto **Canali**, selezionare il canale.
1. Nel riquadro delle proprietà del canale a destra, selezionare il nome dell'applicazione B2C nel menu a discesa **Seleziona applicazione B2C**.
1. Selezionare **Chiudi**, quindi selezionare **Salva e pubblica**.

## <a name="next-steps"></a>Passaggi successivi

Per continuare il processo di configurazione di un tenant B2C in Commerce, passa a [Ulteriori informazioni su B2C](additional-b2c-info.md).

## <a name="additional-resources"></a>Risorse aggiuntive

[Impostare un tenant B2C in Commerce](set-up-b2c-tenant.md)

[Creare o collegare un tenant Azure AD B2C esistente nel portale di Azure](create-link-aad-b2c-tenant.md)

[Creare l'applicazione B2C](create-b2c-app.md)

[Creare criteri di flusso utente](create-user-flow-policies.md)

[Aggiungere provider di identità social (facoltativo)](add-social-identity-providers.md)

[Aggiornare Commerce headquarters con le nuove informazioni di Azure AD B2C](update-hq-aad-b2c-info.md)

[Ulteriori informazioni su B2C](additional-b2c-info.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
