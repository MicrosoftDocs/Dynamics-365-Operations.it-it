---
title: Configurare CPOS per utilizzare un'app Azure AD personalizzata
description: Questo articolo descrive come configurare il POS Cloud (CPOS) per l'utilizzo di un'applicazione Azure Active Directory (Azure AD) personalizzata.
author: boycez
ms.date: 08/02/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.region: global
ms.author: boycez
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: baa0c3da25308345037b5dd1b4c5907d6213e7f7
ms.sourcegitcommit: bd3b55e1af28e592c97b540de1e87cd8ba9c35a8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/03/2022
ms.locfileid: "9222969"
---
# <a name="configure-cpos-to-use-a-custom-azure-ad-app"></a>Configurare CPOS per utilizzare un'app Azure AD personalizzata

[!include [banner](includes/banner.md)]

Per impostazione predefinita, il POS Cloud (CPOS) in Microsoft Dynamics 365 Commerce punta a un'app Microsoft proprietaria registrata in Azure Active Directory (Azure AD). Pertanto, puoi utilizzare CPOS senza dover apportare modifiche in Azure AD. Tuttavia, potresti voler puntare la tua istanza di CPOS a un'app Azure AD personalizzata di cui hai il controllo. Questo articolo descrive come configurare CPOS per l'utilizzo di un'applicazione Azure AD personalizzata.

## <a name="set-up-a-custom-retail-server-app-in-azure-ad"></a>Configurare un'app Server vendita al dettaglio personalizzata in Azure AD

Per creare e configurare un'app Server vendita al dettaglio personalizzata in Azure AD, procedi come segue.

1. Accedi all'[interfaccia di amministrazione di Azure Active Directory](https://aad.portal.azure.com) utilizzando qualsiasi account utente Azure AD. L'account utente non deve disporre di autorizzazioni di amministratore.
1. Selezionare **Azure Active Directory**.
1. Seleziona **Registrazioni app**, quindi seleziona **Nuova registrazione** per aprire la finestra di dialogo **Registra un'applicazione**.
1. Impostare i seguenti campi:

    - **Nome**: immetti un nome personalizzato per l'app. Ad esempio, immetti **Server vendita al dettaglio personalizzato**.
    - **Tipi di account supportati**: seleziona l'opzione predefinita **Solo account in questa directory organizzativa (solo Microsoft - Tenant singolo)**.
    - **URI di reindirizzamento**: questo campo è facoltativo. Lascialo vuoto.
    - **ID struttura servizio**: questo campo è facoltativo. Lascialo vuoto.
    
1. Seleziona **Registro**. Viene visualizzata la pagina di configurazione dell'app appena registrata.
1. Nella sezione **Panoramica \> Funzionalità fondamentali**, seleziona **Aggiungi un URI ID applicazione**, quindi seleziona **Imposta** accanto a **URI ID applicazione**. Prendi nota del valore suggerito, quindi seleziona **Salva** per accettare quel valore. 
1. Seleziona **Aggiungi un ambito** e imposta i seguenti campi:

    - **Nome ambito**: immetti un nome personalizzato per l'ambito. Ad esempio, immetti **Legacy.Access.Full**.
    - **Utenti che possono fornire il consenso**: specifica se sia gli amministratori che gli utenti o solo gli amministratori possono fornire il consenso, in base ai criteri di sicurezza dell'organizzazione.
    - **Nome visualizzato per il consenso dell'amministratore**: immetti un nome visualizzato. Ad esempio, immetti **Accesso Server vendita al dettaglio**.
    - **Descrizione del consenso dell'amministratore**: immetti una descrizione. Ad esempio, immetti **Fornire accesso alle API di Server vendita al dettaglio**.

1. Seleziona **Aggiungi ambito** per completare il processo di creazione dell'ambito.

## <a name="set-up-a-custom-cpos-app-in-azure-ad"></a>Configurare un'app CPOS personalizzata in Azure AD

Per creare e configurare un'app CPOS personalizzata in Azure AD, procedi come segue.

1. Accedi all'[interfaccia di amministrazione di Azure Active Directory](https://aad.portal.azure.com) utilizzando qualsiasi account utente Azure AD. L'account utente non deve disporre di autorizzazioni di amministratore.
1. Selezionare **Azure Active Directory**.
1. Seleziona **Registrazioni app**, quindi seleziona **Nuova registrazione** per aprire la finestra di dialogo **Registra un'applicazione**.
1. Impostare i seguenti campi:

    - **Nome**: immetti un nome per l'app. Ad esempio, immetti **POS cloud personalizzato**.
    - **Tipi di account supportati**: seleziona l'opzione predefinita **Solo account in questa directory organizzativa (solo Microsoft - Tenant singolo)**.
    - **URI di reindirizzamento**: seleziona **Applicazione a pagina singola (SPA)** nell'elenco a discesa, quindi immetti il tuo URI CPOS.
    - **ID struttura servizio**: questo campo è facoltativo. Lascialo vuoto.

1. Seleziona **Registro**. Viene visualizzata la pagina di configurazione dell'app appena registrata.
1. Nella sezione **Manifesto**, imposta i parametri **oauth2AllowIdTokenImplicitFlow** e **oauth2AllowImplicitFlow** su **true**, quindi seleziona **Salva**.
1. Nella sezione **Configurazione token**, attieniti alla procedura seguente per aggiungere due attestazioni:

    - Seleziona **Aggiungi un'attestazione facoltativa**. Imposta il campo **Tipo di token** su **ID**, quindi seleziona l'attestazione **sid**. Seleziona **Aggiungi**.
    - Seleziona **Aggiungi un'attestazione facoltativa**. Imposta il campo **Tipo di token** su **Accesso**, quindi seleziona l'attestazione **sid**. Seleziona **Aggiungi**.

1. Nella sezione **Autorizzazioni API**, seleziona **Aggiungi un'autorizzazione**.
1. Nella scheda **API utilizzate dalla mia organizzazione**, cerca l'app Server vendita al dettaglio che hai creato nella sezione [Configurare un'app Server vendita al dettaglio personalizzata in Azure AD](#set-up-a-custom-retail-server-app-in-azure-ad). Quindi seleziona **Aggiungi autorizzazioni**.
1. Nella sezione **Panoramica**, prendi nota del valore nel campo **ID applicazione (client)**.

## <a name="update-the-cpos-configuration-file"></a>Aggiornare il file di configurazione CPOS

Apri il file CPOS config.json e apporta i seguenti aggiornamenti.

1. Sostituisci il valore della chiave **AADClientId** con il valore **ID applicazione (client)** dell'app CPOS personalizzata che hai creato nella sezione [Configurare un'app CPOS personalizzata in Azure AD](#set-up-a-custom-cpos-app-in-azure-ad).
1. Sostituisci il valore della chiave **AADRetailServerResourceId** con il valore **URI ID applicazione** dell'app Server vendita al dettaglio personalizzata che hai creato nella sezione [Configurare un'app Server vendita al dettaglio personalizzata in Azure AD](#set-up-a-custom-retail-server-app-in-azure-ad).

CPOS utilizzerà entrambi i parametri quando invia le richieste ad Azure AD per acquisire un token di sicurezza.

## <a name="update-identity-providers-settings-in-commerce-headquarters"></a>Aggiornare le impostazioni dei provider di identità in Commerce headquarters

Ora devi aggiornare le impostazioni dei provider di identità in Commerce headquarters.

1. In Commerce Headquarters, apri la pagina **Parametri condivisi di Commerce**.
1. Nella scheda **Provider di identità**, nella sezione **Provider di identità**, seleziona la riga in cui il campo **Tipo** è impostato su **Azure Active Directory** e il campo **Emittente** punta al tuo tenant Azure AD. Questa impostazione dichiara che lavorerai con griglie figlio che contengono i dati relativi al provider di identità che corrisponde al tuo tenant Azure AD.
1. Nella sezione **Relying party**, seleziona **Aggiungi** per aggiungere una riga.
1. Impostare i seguenti campi:

    - **ClientId**: immetti il valore **ID applicazione (client)** dell'app CPOS personalizzata che hai creato nella sezione [Configurare un'app CPOS personalizzata in Azure AD](#set-up-a-custom-cpos-app-in-azure-ad).
    - **Tipo**: seleziona **Pubblico**.
    - **Tipo utente**: seleziona **Lavoratore**.

1. Seleziona la riga da aggiungere. La sezione **ID risorsa server** sotto la sezione **Relying party** mostra gli ID dell'app Server vendita al dettaglio a cui è possibile accedere dall'app selezionata nella griglia **Relying party**.
1. Nella sezione **ID risorsa server**, seleziona **Aggiungi** per aggiungere una riga.
1. Nel campo **ID risorsa server**, immetti il valore **URI ID applicazione** dell'app Server vendita al dettaglio personalizzata che hai creato nella sezione [Configurare un'app Server vendita al dettaglio personalizzata in Azure AD](#set-up-a-custom-retail-server-app-in-azure-ad).

    > [!IMPORTANT]
    > Tutti i campi citati nei passaggi precedenti fanno la distinzione tra maiuscole e minuscole. I valori che hai immesso devono corrispondere esattamente ai valori configurati nell'interfaccia di amministrazione di Azure AD.

1. Vai a **Vendita al dettaglio e commercio IT \> Programmazione della distribuzione** ed esegui il processo **1110** (**Configurazione globale**).

Ora puoi attivare i dispositivi CPOS utilizzando le tue app Azure AD.

## <a name="additional-resources"></a>Risorse aggiuntive

[Attivazione del dispositivo POS](dev-itpro/retail-device-activation.md)

[Gestire gli account di attivazione e convalidare i dispositivi](set-up-activation-accounts-validate-devices-hq.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
