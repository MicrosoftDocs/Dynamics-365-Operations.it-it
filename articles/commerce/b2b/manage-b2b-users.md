---
title: Gestisci gli utenti dei partner commerciali sui siti di e-commerce B2B
description: Questo argomento descrive come gli amministratori possono aggiungere, modificare ed eliminare gli utenti dei partner commerciali sui siti Web di e-commerce business-to-business (B2B).
author: josaw1
ms.date: 07/22/2021
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
ms.openlocfilehash: f6cc1d5dfeb48fd00216fc1908e9e8be24f07131b3e5f1eaeefb10396efbebc3
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6734945"
---
# <a name="manage-business-partner-users-on-b2b-e-commerce-websites"></a>Gestisci gli utenti dei partner commerciali sui siti di e-commerce B2B

[!include [banner](../../includes/banner.md)]

Questo argomento descrive come gli amministratori possono aggiungere, modificare ed eliminare gli utenti dei partner commerciali sui siti Web di e-commerce business-to-business (B2B).

I siti Web di e-commerce B2B richiedono che le organizzazioni si registrino per diventare partner commerciali. Dopo che un'organizzazione ha inviato i dettagli della registrazione a un sito Web di e-commerce B2B, passa attraverso un processo di qualifica. Se l'organizzazione è qualificata con successo, viene inserita come partner commerciale.

Dopo che un'organizzazione è stata inserita come partner commerciale, l'utente dell'organizzazione che ha avviato la richiesta di diventare partner commerciale viene identificato come utente amministratore e ottiene i privilegi per l'onboarding di ulteriori utenti autorizzati del sito Web di e-commerce B2B. Questi utenti autorizzati possono quindi effettuare ordini per conto del partner commerciale.

## <a name="turn-on-the-b2b-e-commerce-capabilities-feature-in-commerce-headquarters"></a>Attiva le funzionalità di e-commerce B2B in Commerce Headquarters

Le funzionalità di e-commerce B2B in Commerce Headquarters consente alle organizzazioni di integrare i partner commerciali e definire gli utenti amministratori. Questa funzione consente inoltre agli amministratori di creare e gestire utenti e team di partner commerciali e di assegnare loro ruoli specifici. Infine, consente agli utenti dei partner commerciali di creare modelli di ordine e utilizzare gli ordini esistenti per riordinare i prodotti.

Per attivare le funzionalità di e-commerce B2B in Commerce Headquarters, segui questa procedura.

1. Vai a **Aree di lavoro \> Gestione funzionalità**.
1. Nella scheda **Tutti**, filtra il campo **Modulo** utilizzando il termine **Vendita al dettaglio e commercio**.
1. Trova e seleziona l'elemento denominato **Abilita l'uso delle funzionalità di e-commerce B2B** e quindi seleziona **Abilita adesso**.

## <a name="create-a-number-sequence-and-add-it-to-commerce-shared-parameters"></a>Crea una sequenza numerica e aggiungila ai parametri condivisi di Commerce

Le sequenze numeriche vengono utilizzate per generare identificatori univoci leggibili per record transazioni e dati master che richiedono identificatori. Per ulteriori informazioni sulle sequenze numeriche, vedere [Panoramica delle sequenze numeriche](../../fin-ops-core/fin-ops/organization-administration/number-sequence-overview.md).

Per creare una sequenza numerica e aggiungerla ai parametri condivisi di Commerce in Commerce Headquarters, segui questi passaggi.

1. Vai a **Retail e Commerce \> Impostazione sedi centrali \> Sequenze numeriche \> Sequenze numeriche** e crea una sequenza numerica.
1. Vai a **Retail e Commerce \> Impostazione sedi centrali \> Parametri \> Parametri condivisi di Commerce** e aggiungi la nuova sequenza numerica al riferimento **ID gerarchia cliente**.

## <a name="set-up-the-administrator-user-for-a-new-business-partner"></a>Impostare l'utente amministratore per un nuovo partner commerciale

I potenziali partner commerciali possono avviare il processo di onboarding a un sito Web di e-commerce B2B inviando una richiesta di onboarding tramite un collegamento sul sito. Dopo che un potenziale utente partner commerciale seleziona il collegamento, può fornire i dettagli necessari per l'onboarding e la registrazione. Dopo che la richiesta è stata inviata, viene visualizzata una pagina di conferma dell'invio. Se l'invio viene approvato, il richiedente (ovvero l'utente che ha avviato la richiesta di onboarding) diventa l'utente amministratore del partner commerciale.

Per approvare e impostare un utente amministratore di partner commerciali nella sede in Commerce Headquarters, attieniti alla seguente procedura.

1. Vai a **Retail e Commerce IT \> Programmazione della distribuzione**.
1. Esegui il processo **P-0001** per effettuare il pull di tutte le richieste di onboarding del partner commerciale in Commerce Headquarters.
1. Dopo che il processo **P-0001** è stato eseguito correttamente, vai a **Retail e Commerce IT  \> Cliente** ed esegui il processo **Sincronizza clienti e partner commerciali dalla modalità asincrona**. Dopo che questo processo è stato eseguito con successo, le richieste di onboarding vengono create come record dei potenziali clienti in Commerce Headquarters. Il campo **Digita ID** di questi record è impostato su **Prospect B2B**.
1. Vai a **Clienti \> Tutti i prospect** e apri la pagina dei potenziali prospect.
1. Seleziona il record del potenziale prospect per il nuovo partner commerciale per aprire la pagina dei dettagli del potenziale prospect.
1. Nella scheda **Generale**, seleziona **Converti \> Approva/Rifiuta** per approvare o rifiutare la richiesta di onboarding. Quando viene visualizzato un messaggio di conferma, confermare che si desidera continuare con il processo e approvare la richiesta. Viene quindi inviata un'e-mail all'indirizzo e-mail del richiedente per confermare che la sua organizzazione è stata approvata come partner commerciale.

    Dopo aver approvato la richiesta, il campo **Stato** del record del potenziale prospect è impostato su **Approvato**. Inoltre, nel sistema vengono creati due nuovi record cliente: un record del cliente **Digita organizzazione** per l'organizzazione del partner commerciale e un record del cliente **Digita persona** per il richiedente. Viene inoltre creato un record della gerarchia del cliente per il partner commerciale. <!--(Please refer to the Org modeling of B2B customer section in this document for more information)-->

1. Vai a **Retail e Commerce IT \> Programmazione della distribuzione** ed esegui il processo **1010** (**Clienti**) per eseguire il push dei record della gerarchia di clienti e clienti appena creati nel database del canale.

Dopo che la richiesta è stata approvata e i record del cliente e della gerarchia del cliente sono stati sincronizzati con il database del canale, il richiedente può accedere al sito Web di e-commerce B2B utilizzando l'indirizzo e-mail fornito quando ha inviato la richiesta. Gli utenti possono utilizzare il flusso di registrazione per definire la password per il proprio account. Per abilitare il record del provider di identità (Azure AD B2C) da collegare al record del cliente B2B che è stato creato al momento della registrazione o dell'accesso, segui le istruzioni in [Abilitare il collegamento automatico dei record di identità agli account dei clienti](../identity-record-linking.md).

## <a name="onboard-additional-business-partner-users"></a>Eseguire l'onboarding aggiuntivo degli utenti dei partner commerciali

L'utente amministratore del partner commerciale può caricare ulteriori utenti partner commerciali nel sito Web di e-commerce B2B, come richiesto.

Per eseguire l'onboarding di altri utenti di partner commerciali in un sito Web di e-commerce B2B, segui questi passaggi.

1. Accedi al sito Web e-commerce B2B come amministratore.
1. Vai a **Account personale \> Utenti organizzazione \> Visualizza dettagli** e seleziona **Aggiungi utente**.
1. Immetti le informazioni richieste, quindi seleziona **Salva**. Lo stato del nuovo utente è impostato su **In sospeso**.

    Dopo che i processi **P-0001** e **Sincronizza clienti e partner commerciali dalla modalità asincrona** sono stati eseguiti, un record cliente **Digita persona** per il nuovo utente viene creato in Commerce Headquarters. Questo record cliente è anche associato al record della gerarchia clienti del relativo partner commerciale. Inoltre, viene inviata un'e-mail all'indirizzo e-mail del nuovo utente per informarlo che è stato aggiunto come utente dell'organizzazione del partner commerciale e che ora può accedere al sito Web di e-commerce B2B.

1. Esegui il processo **1010** (**Clienti**) per sincronizzare il nuovo utente del partner commerciale con il database del canale.

Dopo che il record del cliente è stato sincronizzato, lo stato dell'utente sul sito Web di e-commerce B2B viene impostato su **Attivo** e il nuovo utente può accedere al sito Web di e-commerce B2B utilizzando il proprio indirizzo e-mail. Gli utenti possono utilizzare il flusso di registrazione per definire la password per il proprio account. Per abilitare il record del provider di identità (Azure AD B2C) da collegare al record del cliente B2B che è stato creato al momento della registrazione o dell'accesso, segui le istruzioni in [Abilitare il collegamento automatico dei record di identità agli account dei clienti](../identity-record-linking.md).

## <a name="edit-business-partner-user-details"></a>Modifica i dettagli dell'utente del partner commerciale

Per modificare i dettagli degli utenti dei partner commerciali, attenersi alla seguente procedura.

1. Accedi al sito Web e-commerce B2B come amministratore.
1. Vai a **Account personale \> Utenti dell'organizzazione \> Visualizza dettagli**, seleziona il pulsante **Modifica** (simbolo della matita), apporta le modifiche richieste, quindi seleziona **Salva**. Le modifiche avranno effetto solo dopo che i processi **P-0001**, **Sincronizza clienti e partner commerciali dalla modalità asincrona** e **1010** (**Clienti**) sono stati eseguiti.

## <a name="remove-a-business-partner-user"></a>Rimuovi un utente partner commerciale

Se necessario, un amministratore può rimuovere gli utenti esistenti di un'organizzazione di partner commerciali dall'elenco di utenti che possono accedere al sito Web di e-commerce B2B.

Per rimuovere un utente partner commerciale, segui questi passaggi.

1. Accedi al sito Web e-commerce B2B come amministratore.
1. Vai a **Account personale \> Utenti organizzazione \> Visualizza dettagli** e seleziona il pulsante **Rimuovi** (simbolo X). Quando viene visualizzato un messaggio di conferma, confermare che si desidera rimuovere l'utente. Le modifica avrà effetto solo dopo che i processi **P-0001**, **Sincronizza clienti e partner commerciali dalla modalità asincrona** e **1010** (**Clienti**) sono stati eseguiti.

> [!NOTE]
> Quando si rimuove un utente dall'elenco di utenti che possono accedere al sito Web di e-commerce B2B, il record del cliente corrispondente viene rimosso dal record della gerarchia dei clienti del partner commerciale. Tuttavia, il record del cliente stesso non viene eliminato in Commerce Headquarters.

## <a name="onboard-business-partner-and-users-in-commerce-headquarters"></a>Esegui l'onboarding dei partner commerciale e degli utenti in Commerce Headquarters

Gli amministratori possono eseguire l'onboarding di partner commerciali e degli utenti direttamente in Commerce Headquarters.

Per eseguire l'onboarding di partner commerciali e degli utenti in Commerce Headquarters, attieniti alla seguente procedura.

1. Crea un record del cliente **Digita organizzazione** per l'organizzazione del partner commerciale.
1. Crea record del cliente **Digita persona** per gli utenti dei partner commerciali. Assicurati di specificare un indirizzo e-mail principale per ogni cliente.
1. Per ciascun record del cliente **Digita persona** che deve essere designato come utente amministratore dell'organizzazione del partner commerciale, nella Scheda dettaglio **Retail**, imposta l'opzione **Amministratore B2B** su **Sì**.
1. Crea un ID gerarchia cliente. Nel campo **Nome** immettere un nome.
1. Nel campo **Organizzazione**, immetti il cliente dell'organizzazione dei partner commerciali.
1. Seleziona **Aggiungi**, quindi un cliente nel campo **Nome**.
1. Ripeti questo processo per aggiungere altri clienti alla gerarchia.

## <a name="additional-information"></a>Informazioni aggiuntive

- Tutti i processi menzionati in questo argomento possono essere configurati per essere eseguiti su una programmazione in un formato batch. L'aspettativa è che i partner commerciali configurino i lavori batch come richiesto.
- Attualmente, solo un record utente/cliente può essere designato come utente amministratore e tale ruolo può essere modificato solo in Commerce Headquarters. Non è disponibile alcun supporto per le funzionalità self-service che consentono ai partner commerciali di designare più amministratori o modificare gli amministratori dai siti Web di e-commerce B2B.
<!--- The modules and labels of the different fields referenced in the screenshots for e-commerce are only for illustration purposes. Customers have complete control on the placement of the B2B related modules and the labels.-->
- Sebbene i limiti di spesa possano essere definiti per gli utenti, l'applicazione dei limiti di spesa durante il processo di immissione degli ordini non è stata ancora implementata.
- Tutta la logica aziendale e la convalida per l'esperienza di un utente su un sito Web di e-commerce B2B si basano sulla configurazione del record del cliente che viene mappato all'utente in Commerce Headquarters.

## <a name="additional-resources"></a>Risorse aggiuntive

[Impostare un sito di e-commerce B2B](set-up-b2b-site.md)

[Creare gerarchie di modellazione per le organizzazioni B2B](org-model.md)

[Configura il metodo di pagamento dell'account cliente per i siti Web di e-commerce B2B](payment-method.md)

[Impostare limiti di quantità di prodotti per i siti di e-commerce B2B](quantity-limits.md)

[Panoramica delle sequenze numeriche](../../fin-ops-core/fin-ops/organization-administration/number-sequence-overview.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
