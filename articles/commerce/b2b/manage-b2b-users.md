---
title: Gestire utenti partner commerciali nei siti di e-commerce B2B
description: Questo argomento descrive come aggiungere, modificare ed eliminare gli utenti partner commerciali nei siti Web di e-commerce business-to-business (B2B) di Microsoft Dynamics 365 Commerce e in Commerce headquarters.
author: josaw1
ms.date: 02/17/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: retail
ms.author: brshoo
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: def8d4de082ceb4be77ed7e8898cbef82d52b749
ms.sourcegitcommit: 68114cc54af88be9a3a1a368d5964876e68e8c60
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/17/2022
ms.locfileid: "8323457"
---
# <a name="manage-business-partner-users-on-b2b-e-commerce-websites"></a>Gestire utenti partner commerciali nei siti di e-commerce B2B

[!include [banner](../../includes/banner.md)]

Questo argomento descrive come aggiungere, modificare ed eliminare gli utenti partner commerciali nei siti Web di e-commerce business-to-business (B2B) di Microsoft Dynamics 365 Commerce e in Commerce headquarters.

> [!NOTE]
> L'argomento [Gestire partner commerciali B2B utilizzando gerarchie dei clienti](partners-customer-hierarchies.md) è un prerequisito per questo documento. 

I siti Web di e-commerce B2B richiedono che le organizzazioni si registrino per diventare partner commerciali. Dopo che un'organizzazione ha inviato i dettagli della registrazione a un sito Web di e-commerce B2B, la richiesta di registrazione passa attraverso un processo di qualifica. Se l'organizzazione è qualificata con successo, viene inserita come partner commerciale.

Dopo che un'organizzazione è stata inserita come partner commerciale, l'utente dell'organizzazione che ha avviato la richiesta di diventare partner commerciale viene identificato come utente amministratore e ottiene i privilegi per l'onboarding di ulteriori utenti autorizzati del sito Web di e-commerce B2B. Questi utenti autorizzati possono quindi effettuare ordini per conto del partner commerciale.

## <a name="set-up-the-administrator-user-for-a-new-business-partner"></a>Impostare l'utente amministratore per un nuovo partner commerciale

I potenziali partner commerciali possono avviare il processo di onboarding a un sito Web di e-commerce B2B inviando una richiesta di onboarding tramite un collegamento nel sito Web B2B. Possono quindi utilizzare il modulo personalizzabile per fornire i dettagli necessari per l'onboarding e la registrazione. Dopo che la richiesta è stata inviata, viene visualizzata una pagina di conferma dell'invio. Se l'invio viene approvato, la società per la quale la richiesta è stata inviata diventa un partner commerciale e il richiedente (ovvero l'utente che ha avviato la richiesta di onboarding) diventa l'utente amministratore del partner commerciale.

Per approvare una richiesta di partner commerciale in Commerce Headquarters, attieniti alla seguente procedura.

1. Vai a **Retail e Commerce IT \> Programmazione della distribuzione**.
1. Esegui il processo **P-0001** per effettuare il pull di tutte le richieste di onboarding del partner commerciale in Commerce Headquarters.
1. Dopo che il processo **P-0001** è stato eseguito correttamente, vai a **Retail e Commerce IT \> Cliente** ed esegui il processo **Sincronizza clienti e richieste di canale**. Dopo la corretta esecuzione di questo processo, le richieste di onboarding vengono create come prospect del tipo **prospect B2B** in Commerce Headquarters. 
1. Vai a **Clienti \> Tutti i prospect** e seleziona il record prospect del nuovo partner commerciale per aprire la pagina dei dettagli del prospect.
1. Nella scheda **Generale**, seleziona **Converti \> Approva/Rifiuta** per approvare la richiesta di onboarding. Quando viene visualizzato un messaggio di conferma, conferma che desideri continuare con il processo e quindi approva la richiesta. Dopo aver approvato la richiesta, il campo **Stato** del record prospect viene impostato su **Approvato**. Viene quindi inviata un'e-mail all'indirizzo e-mail del richiedente per confermare che la sua organizzazione è stata approvata come partner commerciale. Viene inoltre creata una gerarchia di clienti, in cui il richiedente viene aggiunto come amministratore per il partner commerciale.

    > [!NOTE]
    > Attualmente, l'e-mail di conferma viene inviata immediatamente dopo l'approvazione. Tuttavia, la funzionalità futura di Commerce consentirà all'amministratore di attivare manualmente le e-mail.

1. Vai a **Retail e Commerce IT \> Programmazione della distribuzione** ed esegui il processo **1010 (Clienti)** per eseguire il push dei nuovi record gerarchia di clienti e cliente nel database del canale.

> [!NOTE]
> Per garantire che i nuovi record cliente vengano inviati al database del canale, è necessario includere almeno una delle rubriche associate al cliente nella rubrica del cliente associata al punto vendita online. È possibile automatizzare questo processo configurando la rubrica sul cliente predefinito del punto vendita online di modo che il sistema copi il valore della rubrica in ogni nuovo cliente.

Dopo la sincronizzazione dei record rubrica con il database del canale, il richiedente può accedere al sito Web di e-commerce B2B utilizzando l'indirizzo e-mail fornito quando ha inviato la richiesta di onboarding. Gli utenti possono utilizzare il flusso di registrazione per definire la password per il proprio account. Per informazioni su come abilitare il record provider di identità BC2 di Azure Active Directory (Azure AD) da collegare al record cliente B2B creato all'approvazione del prospect, vedi [Abilitare il collegamento automatico](../identity-record-linking.md).

## <a name="notify-b2b-prospects-when-they-are-approved-or-rejected"></a>Notifica i prospect B2B quando vengono approvati o rifiutati

Quando approvi o rifiuti una richiesta di onboarding di un prospect B2B, puoi inviare automaticamente una notifica via e-mail al prospect.

Per impostare le notifiche e-mail in Commerce headquarters per eventi del tipo di notifica **prospect B2B approvato** o **prospect B2B rifiutato**, seguire questi passaggi.

1. Crea modelli e-mail per le e-mail che verranno inviate ai prospect quando viene attivato il tipo di notifica **prospect B2B approvato** o **prospect B2B rifiutato**. Per informazioni sui segnaposto supportati da questi tipi di notifica, vedi [Tipi di notifica](../email-templates-transactions.md#notification-types). Per informazioni su come creare modelli di posta elettronica, vedi [Crea un modello e-mail](../email-templates-transactions.md#create-an-email-template).
1. Aggiungi i tipi di notifica **prospect B2B approvato** e **prospect B2B rifiutato** al tuo profilo di notifica e-mail e quindi mappali ai modelli e-mail che hai creato. Per ulteriori informazioni sui profili di notifica e-mail, vedi [Configura un profilo di notifica e-mail](../email-notification-profiles.md).

## <a name="onboard-additional-business-partner-users"></a>Eseguire l'onboarding di ulteriori utenti partner commerciali

L'utente amministratore del partner commerciale può caricare ulteriori utenti partner commerciali nel sito Web di e-commerce B2B, come richiesto.

Per eseguire l'onboarding di ulteriori utenti partner commerciali in un sito Web di e-commerce B2B, segui questi passaggi.

1. Accedi al sito Web e-commerce B2B come amministratore.
1. Vai a **Account personale \> Utenti organizzazione \> Visualizza dettagli** e seleziona **Aggiungi utente**.
1. Immetti le informazioni richieste, quindi seleziona **Salva**. Lo stato del nuovo utente è impostato su **In sospeso**.

Dopo che i processi **P-0001** e **Sincronizza clienti e richieste di canale** sono stati eseguiti, un record cliente di tipo **Persona** per il nuovo utente viene creato in Commerce Headquarters. Questo record cliente è anche associato al record gerarchia clienti del relativo partner commerciale. Inoltre, viene inviata un'e-mail all'indirizzo e-mail del nuovo utente per informarlo che è stato aggiunto come utente dell'organizzazione del partner commerciale e che ora può accedere al sito Web di e-commerce B2B.

Successivamente, esegui il processo **1010 (Clienti)** per sincronizzare il nuovo utente partner commerciale con il database del canale.

Dopo che il record cliente è stato sincronizzato, lo stato dell'utente nel sito Web di e-commerce B2B viene impostato su **Attivo** e il nuovo utente può accedere al sito Web di e-commerce B2B utilizzando il proprio indirizzo e-mail. Gli utenti possono utilizzare il flusso di registrazione per definire la password per il proprio account. Per informazioni su come abilitare il record provider di identità B2C di Azure AD da collegare al record cliente B2B creato in Commerce headquarters, vedi [Abilitare il collegamento automatico](/dynamics365/commerce/identity-record-linking.md).

## <a name="edit-business-partner-user-details"></a>Modifica i dettagli dell'utente partner commerciale

Per modificare i dettagli degli utenti partner commerciali, attieniti alla seguente procedura.

1. Accedi al sito Web e-commerce B2B come amministratore.
1. Vai a **Account personale \> Utenti dell'organizzazione \> Visualizza dettagli**, seleziona il pulsante **Modifica** (simbolo della matita), apporta le modifiche richieste, quindi seleziona **Salva**. Le modifiche avranno effetto solo dopo che i processi **P-0001**, **Sincronizza clienti e richieste di canale** e **1010 (Clienti)** sono stati eseguiti.

## <a name="remove-a-business-partner-user"></a>Rimuovi un utente partner commerciale

Se necessario, un amministratore può rimuovere gli utenti esistenti di un'organizzazione di partner commerciali dall'elenco di utenti che possono accedere al sito Web di e-commerce B2B.
Per rimuovere un utente partner commerciale, segui questi passaggi.
- Accedi al sito Web e-commerce B2B come amministratore.
- Vai a **Account personale > Utenti organizzazione \> Visualizza dettagli** e seleziona il pulsante **Rimuovi** (simbolo X). Quando viene visualizzato un messaggio di conferma, confermare che si desidera rimuovere l'utente. La modifica ha effetto solo dopo che i processi **P-0001**, **Sincronizza clienti e richieste di canale** e **1010 (Clienti)** sono stati eseguiti.

> [!NOTE]
> Quando si rimuove un utente dall'elenco di utenti che possono accedere al sito Web di e-commerce B2B, il record del cliente corrispondente viene rimosso dal record della gerarchia dei clienti del partner commerciale. Tuttavia, il record del cliente stesso non viene eliminato in Commerce Headquarters.

## <a name="onboard-existing-customers-as-business-partners-on-the-b2b-e-commerce-website"></a>Eseguire l'onboarding di clienti esistenti come partner commerciali nel sito Web di e-commerce B2B

Gli amministratori possono eseguire l'onboarding di partner commerciali e degli utenti direttamente in Commerce Headquarters. Questa funzionalità è utile per l'onboarding dei partner commerciali esistenti nel sito Web di e-commerce B2B.

Per eseguire l'onboarding di partner commerciali e degli utenti in Commerce Headquarters, attieniti alla seguente procedura.

1. Crea o seleziona un cliente di tipo **Organizzazione** da aggiungere come partner commerciale.
1. Crea o seleziona un cliente di tipo **Persona** da aggiungere come amministratore o utente per il partner commerciale. Assicuati che gli indirizzi e-mail principali siano associati ai clienti. Questi indirizzi email vengono utilizzati per accedere al sito Web. 

    > [!NOTE]
    > Il sistema deve essere in grado di trovare un record cliente univoco per gli utenti che devono essere in grado di accedere al sito Web. Se il sistema rileva più di un cliente che ha lo stesso indirizzo e-mail principale nella persona giuridica, l'utente non sarà in grado di accedere al sito Web.

1. Crea un ID gerarchia cliente.
1. Nel campo **Nome** immettere un nome.
1. Nel campo **Organizzazione**, immetti il cliente dell'organizzazione dei partner commerciali.
1. Nella Scheda dettaglio **Gerarchia** seleziona **Aggiungi**.
1. Nel campo **Nome**, seleziona un cliente di tipo **Persona**.
1. Seleziona il ruolo **Amministratore** per il cliente che deve essere designato come amministratore.
1. Ripeti questo processo per aggiungere altri clienti alla gerarchia.

## <a name="additional-information"></a>Informazioni aggiuntive

- Tutti i processi menzionati in questo argomento possono essere configurati per essere eseguiti su una programmazione in un formato batch. L'aspettativa è che i partner commerciali configurino i lavori batch come richiesto.
- Attualmente, solo un record utente/cliente può essere designato come utente amministratore e tale ruolo può essere modificato solo in Commerce Headquarters. Non è disponibile alcun supporto per le funzionalità self-service che consentono ai partner commerciali di designare più amministratori o modificare gli amministratori dai siti Web di e-commerce B2B.
- Sebbene i limiti di spesa possano essere definiti per gli utenti, l'applicazione dei limiti di spesa durante il processo di immissione degli ordini non è stata ancora implementata.
- Tutta la logica aziendale e la convalida per l'esperienza di un utente su un sito Web di e-commerce B2B si basano sulla configurazione del record del cliente che viene mappato all'utente in Commerce Headquarters.

## <a name="additional-resources"></a>Risorse aggiuntive

[Creare un sito di e-commerce B2B](set-up-b2b-site.md)

[Gestire partner commerciali B2B utilizzando gerarchie di clienti](partners-customer-hierarchies.md)

[Configura il metodo di pagamento dell'account cliente per i siti Web di e-commerce B2B](payment-method.md)

[Impostare limiti di quantità di prodotti per i siti di e-commerce B2B](quantity-limits.md)

[Panoramica delle sequenze numeriche](../../fin-ops-core/fin-ops/organization-administration/number-sequence-overview.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
