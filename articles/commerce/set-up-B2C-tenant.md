---
title: Impostare un tenant B2C in Commerce
description: Questo articolo descrive come configurare il tenant Azure Active Directory (Azure AD) business-to-consumer (B2C) per l'autenticazione del sito dell'utente in Microsoft Dynamics 365 Commerce.
author: BrianShook
ms.date: 11/15/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2020-02-13
ms.openlocfilehash: 3421dd3d67198a99ac236a56cbb4f300cb591a03
ms.sourcegitcommit: 774f8f97a0b14cf1199bd1802178ccf536a25ade
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/17/2022
ms.locfileid: "9785139"
---
# <a name="set-up-a-b2c-tenant-in-commerce"></a>Impostare un tenant B2C in Commerce

[!include [banner](includes/banner.md)]

Questo articolo descrive come configurare il tenant Azure Active Directory (Azure AD) business-to-consumer (B2C) per l'autenticazione del sito dell'utente in Dynamics 365 Commerce.

Dynamics 365 Commerce utilizza Azure AD B2C per supportare le credenziali dell'utente e i flussi di autenticazione. Un utente può registrarsi, accedere e reimpostare la propria password attraverso questi flussi. Azure AD B2C memorizza le informazioni di autenticazione sensibili di un utente, ad esempio il nome utente e la password. Il record utente nel tenant B2C memorizza un record dell'account locale B2C o un record del provider di identità social B2C. Questi record B2C rimandano al record del cliente nell'ambiente Commerce.

> [!WARNING] 
> Azure AD B2C ritirerà i vecchi flussi di utenti (legacy) entro il 1° agosto 2021. Pertanto, è necessario pianificare la migrazione dei flussi utente alla nuova versione consigliata. La nuova versione fornisce funzionalità uguali e nuove funzionalità. La libreria del modulo per Commerce versione 10.0.15 o successiva deve essere utilizzata con i flussi utente B2C consigliati. Per ulteriori informazioni, vedi [Flussi utente in Azure Active Directory B2C](/azure/active-directory-b2c/user-flow-overview).
 
 > [!NOTE]
 > Gli ambienti di valutazione di Commerce vengono forniti con un tenant Azure AD B2C a scopo dimostrativo. Il caricamento del tuo tenant Azure AD B2C tramite i passaggi seguenti non è richiesto per gli ambienti di valutazione.

> [!TIP]
> Puoi proteggere ulteriormente gli utenti del tuo sito e migliorare la sicurezza dei tuoi inquilini Azure AD B2C con Azure AD Identity Protection e Conditional Access. Per rivedere le funzionalità disponibili per i tenant Azure AD B2C Premium P1 e Premium P2, vedere [Protezione dell'identità e accesso condizionato per Azure AD B2C](/azure/active-directory-b2c/conditional-access-identity-protection-overview).

## <a name="dynamics-environment-prerequisites"></a>Prerequisiti dell'ambiente Dynamics

Prima di iniziare, assicurati che il tuo ambiente e canale e-commerce Dynamics 365 Commerce siano opportunamente configurati soddisfacendo i seguenti prerequisiti.

- Imposta il valore operazioni POS **AllowAnonymousAccess** su "1" in Commerce headquarters:
    1. Vai a **Operazioni POS**.
    1. Nella griglia operazioni fare clic con il pulsante destro del mouse e selezionare **Personalizza**.
    1. Selezionare **Aggiungi un campo**.
    1. Nell'elenco delle colonne disponibili, seleziona la colonna **AllowAnonymousAccess** per aggiungerlo.
    1. Selezionare **Aggiornamento**.
    1. Per il **612** operazione "Aggiunta cliente", modifica **AllowAnonymousAccess** su "1."
    1. Esegui il processo **1090 (Registri)**.
- Imposta l'attributo /**Manuale/** dell'account cliente della sequenza numerica su /**No/** in Commerce Headquarters:
    1. Accedere a **Retail e Commerce \> Impostazione sedi centrali \> Parametri \> Parametri contabilità clienti**.
    1. Selezionare **Sequenze numeriche**.
    1. Nella riga **Conto cliente**, fare doppio clic sul valore **Codice sequenza numerica**.
    1. Nella Scheda dettaglio /**Generale/** della sequenza numerica, impostare /**Manuale/** su /**No/**.

Dopo la distribuzione del tuo ambiente Dynamics 365 Commerce, si consiglia inoltre di [Inizializzare i dati iniziali](enable-configure-retail-functionality.md) nell'ambiente.

## <a name="next-steps"></a>Passaggi successivi

Per continuare il processo di configurazione di un tenant B2C in Commerce, procedi a [Creare o collegare a un tenant Azure AD B2C esistente nel portale di Azure](create-link-aad-b2c-tenant.md).

## <a name="additional-resources"></a>Risorse aggiuntive

[Creare o collegare un tenant Azure AD B2C esistente nel portale di Azure](create-link-aad-b2c-tenant.md)

[Creare l'applicazione B2C](create-b2c-app.md)

[Creare criteri di flusso utente](create-user-flow-policies.md)

[Aggiungere provider di identità social (facoltativo)](add-social-identity-providers.md)

[Aggiornare Commerce headquarters con le nuove informazioni di Azure AD B2C](update-hq-aad-b2c-info.md)

[Configurare il tenant B2C in Creazione di siti Web di Commerce](config-b2c-tenant-site-builder.md)

[Ulteriori informazioni su B2C](additional-b2c-info.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
