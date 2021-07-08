---
title: Configurare l'autenticazione Azure Active Directory per l'accesso al POS
description: Questo argomento spiega come configurare Azure Active Directory come metodo di autenticazione nel POS di Microsoft Dynamics 365 Commerce.
author: boycezhu
ms.date: 04/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Core, Operations, Retail
ms.search.region: global
ms.author: boycez
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.11
ms.openlocfilehash: 63121a9b5f1b062b7ca927f6b9eb1689ce8aa698
ms.sourcegitcommit: dc4898aa32f381620c517bf89c7856e693563ace
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/17/2021
ms.locfileid: "6270685"
---
# <a name="configure-azure-active-directory-authentication-for-pos-sign-in"></a>Configurare l'autenticazione Azure Active Directory per l'accesso al POS

[!include [banner](includes/banner.md)]

Questo argomento spiega come configurare Azure Active Directory (Azure AD)come metodo di autenticazione nel POS di Microsoft Dynamics 365 Commerce.

Rivenditori che utilizzano Dynamics 365 Commerce insieme ad altri servizi cloud Microsoft come Microsoft Azure, Microsoft 365 e Microsoft Teams in genere desiderano utilizzare Azure AD per la gestione centralizzata delle credenziali utente per un'esperienza di accesso sicura e senza problemi per tutte le applicazioni. Per usare l'autenticazione Azure AD per il POS di Commerce, è necessario prima configurare Azure AD come metodo di autenticazione in Commerce Headquarters.

## <a name="configure-pos-authentication-method"></a>Configurare il metodo di autenticazione POS

Per configurare il metodo di autenticazione POS in Commerce Headquarters, seguire questi passaggi.
    
1. Accedere a **Retail e Commerce \> Impostazione canale \> Impostazioni POS \> Profili POS \> Profili funzionalità** e selezionare un profilo funzionalità che si desidera modificare.
1. Nella sezione **Accesso personale POS** della Scheda dettaglio **Funzioni**, selezionare un'opzione del metodo di autenticazione desiderata dall'elenco a discesa **Metodo di autenticazione di accesso**.

    Il **Metodo di autenticazione di accesso** ha tre opzioni:
    
    - **ID personale e password** - Questa opzione predefinita richiede agli utenti POS di inserire un ID personale e una password per accedere al POS e per accedere alla funzionalità di sostituzione del responsabile.
    - **Azure AD senza single sign-on** - Questa opzione richiede l'utilizzo da parte degli utenti POS delle credenziali Azure AD per accedere al POS e la funzionalità di sostituzione del responsabile. Quando il client POS viene aggiornato o riaperto, l'utente POS deve fornire le credenziali Azure AD per accedere nuovamente.
    - **Azure AD con single sign-on** - Quando questa opzione è selezionata, gli utenti POS possono accedere a Cloud POS (CPOS) utilizzando le credenziali Azure AD attive utilizzate da altre applicazioni Web nello stesso Web browser o accedere a Modern POS (MPOS) utilizzando le credenziali Azure AD di accesso a Windows. Entrambi i metodi consentono l'accesso senza bisogno di immettere le credenziali Azure AD nella schermata di accesso al POS. Tuttavia, l'accesso alla funzionalità di sostituzione del responsabile POS richiederà comunque l'accesso tramite credenziali Azure AD.

1. Vai a **Retail e Commerce >  Retail e Commerce IT  > Programmazione della distribuzione** ed esegui il processo **1070 (Configurazione canale)** per sincronizzare le ultime impostazioni del profilo di funzionalità con i client POS.

> [!NOTE]
> - Il metodo di autenticazione **Azure AD senza single sign-on** sostituisce l'opzione **Azure Active Directory** in Commerce versione 10.0.18 e precedenti.
> - L'autenticazione Azure AD richiede una connessione Internet attiva e non funzionerà quando il POS è offline.

## <a name="associate-azure-ad-accounts-with-pos-users"></a>Associare account Azure AD a utenti POS

Per Usare Azure AD come metodo di autenticazione POS, è necessario associare gli account Azure AD agli utenti POS in Commerce Headquarters. 

Per associare gli account Azure AD con utenti POS in Commerce Headquarters, segui questi passaggi.
    
1. Vai a **Retail e Commerce > Dipendenti > Lavoratori** e apri un record lavoratore.
1. Nel riquadro Azioni, selezionare la scheda **Commerce**, quindi in **Identità esterna**, selezionare **Associa identità esistente**. 
1. Nella finestra di dialogo **Usa identità esterna esistente**, selezionare **Cerca tramite e-mail**, inserire un indirizzo e-mail Azure AD, quindi selezionare **Cerca**.
1. Selezionare l'account Azure AD che viene restituito, quindi selezionare **OK**.

Dopo i precedenti passaggi di configurazione, I campi **Alias**, **UPN** e **Identificatore secondario esterno** nella scheda **Commerce** della pagina dei dettagli del lavoratore verranno compilati.

Devi eseguire il processo **1060 (Personale)** in **Retail e Commerce > Retail e Commerce IT > Programmazione della distribuzione** per sincronizzare l'ultimo utente POS e i dati dell'account Azure AD con il canale.

> [!NOTE]
> Come procedura consigliata, dopo che le informazioni del lavoratore come password, autorizzazione POS, account Azure AD associato o la rubrica dei dipendenti vengono aggiornata in Commerce Headquarters, si consiglia vivamente di eseguire il processo **1060 (Personale)** per sincronizzare le ultime informazioni del lavoratore con il canale. Il client POS può quindi recuperare i dati corretti per l'autenticazione dell'utente e i controlli delle autorizzazioni.

## <a name="pos-lock-register-and-sign-out-with-azure-ad-authentication"></a>Bloccare il registratore di cassa POS e disconnettersi con autenticazione Azure AD

Quanto segue si verifica quando POS è configurato per utilizzare il  Metodo di autenticazione Azure AD:

- La funzione **Blocca registratore di casse** non sarà disponibile nell'applicazione POS. 
- La funzione **Blocco automatico** si comporterà come la funzione **Disconnessione automatica**.
- Se l'utente POS seleziona **Disconnetti**, all'utente verrà chiesto di accedere con le credenziali Azure AD al successivo avvio del POS, indipendentemente dal fatto che l'accesso Single Sign-on sia abilitato.

## <a name="manager-override-functionality-with-azure-ad-authentication"></a>Funzionalità di sostituzione del responsabile con le credenziali Azure AD

Quando il POS è configurato per utilizzare l'autenticazione Azure AD, la funzionalità di sostituzione del responsabile aprirà una finestra di dialogo che richiede le credenziali Azure AD dell'utente responsabile. Dopo che l'accesso del responsabile è stato approvato,  le credenziali Azure AD verranno eliminate e le credenziali Azure AD dell'utente precedente verranno utilizzate per le successive operazioni POS.

> [!NOTE]
> - Nelle versioni di Commerce 10.0.18 e precedenti, la funzione di sostituzione del responsabile non supporta Azure AD. Sono richiesti un ID personale e una password anche se il POS  è configurato per usare il metodo di autenticazione Azure AD.
> - Quando si utilizza CPOS con il browser web Safari su un dispositivo Apple iOS, è necessario prima disattivare **Blocca popup** nelle impostazioni di Safari perché la funzionalità di sostituzione del responsabile funzioni con l'autenticazione Azure AD. 

## <a name="security-best-practices-for-azure-ad-based-pos-authentication-on-shared-devices"></a>Procedure consigliate di sicurezza per l'autenticazione POS basata su Azure AD su dispositivi condivisi

Molti rivenditori configurano il proprio ambiente di punto vendita al dettaglio in modo che più utenti debbano accedere all'applicazione POS da un dispositivo fisico condiviso. In tale contesto, mentre il Single Sign-on fornisce un'esperienza di autenticazione comoda e integrata, può anche creare una falla nella sicurezza in cui l'utente POS corrente potrebbe non rendersi conto che le credenziali di un altro utente vengono utilizzate per eseguire transazioni o operazioni nel POS. Prima di configurare il POS per utilizzare il  metodo di autenticazione Azure AD, si consiglia vivamente di rivedere i criteri di sicurezza e le impostazioni di accesso del dispositivo condiviso per decidere quale opzione è la migliore.

- Se il tuo ambiente di vendita al dettaglio utilizza un account condiviso (ad esempio, un account locale) per l'accesso al dispositivo fisico, si consiglia di utilizzare l'opzione **Azure AD senza single sign-on**. Ciò garantisce che ogni utente POS fornisca esplicitamente credenziali Azure AD per accedere al POS.
- Se il tuo ambiente di vendita al dettaglio richiede ai dipendenti di utilizzare i propri account Azure ADper accedere al POS e al dispositivo fisico che lo ospita, si consiglia di utilizzare l'opzione **Azure AD con single sign-on**.

## <a name="additional-resources"></a>Risorse aggiuntive

[Configurare un lavoratore](tasks/worker.md)

[Creare un profilo funzionalità di vendita al dettaglio](retail-functionality-profile.md)


[Impostare la funzionalità di accesso esteso per MPOS e Cloud POS](extended-logon.md)

[Procedure consigliate di sicurezza per Cloud POS in ambienti condivisi](dev-itpro/secure-retail-cloud-pos.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
