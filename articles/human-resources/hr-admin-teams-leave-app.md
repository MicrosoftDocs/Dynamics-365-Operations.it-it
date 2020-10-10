---
title: App Human Resources in Teams
description: Questo argomento introduce l'app Microsoft Dynamics 365 Human Resources in Microsoft Teams.
author: andreabichsel
manager: AnnBe
ms.date: 09/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: FeatureManagementWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-05-18
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 33322b9b553076125695f257b201463e9d8275c6
ms.sourcegitcommit: e27510ba52623c801353eed4853f8c0aeea3bb2d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/22/2020
ms.locfileid: "3828916"
---
# <a name="human-resources-app-in-teams"></a>App Human Resources in Teams

[!include [banner](includes/preview-feature.md)]

L'app Microsoft Dynamics 365 Human Resources in Microsoft Teams consente ai dipendenti di richiedere rapidamente permessi e di visualizzare le informazioni sul loro saldo permessi in Microsoft Teams. I dipendenti possono interagire con un bot per richiedere informazioni. La scheda **Indisponibilità** fornisce informazioni più dettagliate. Inoltre, può inviare alle persone informazioni sull'imminente indisponibilità nei team e nelle chat al di fuori dell'app Human Resources.

![Bot dell'app per i permessi Human Resources in Teams](./media/hr-admin-teams-leave-app-bot.png)

![Scheda Tempo libero dell'app per i permessi Human Resources in Teams](./media/hr-teams-leave-app-timeoff-tab.png)

![Scheda richiesta di congedo per Human Resources](./media/hr-teams-leave-app-chat-card.png)

## <a name="install-and-setup"></a>Installa e configura

Puoi trovare l'app Human Resources nello store di Teams. Per informazioni sull'installazione dell'app Teams, vedi [Gestisci richieste di permessi in Teams](hr-teams-leave-app.md).

Per informazioni sulla gestione delle autorizzazioni delle app in Teams, vedi [Gestire i criteri delle autorizzazioni delle app in Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/teams-app-permission-policies).

## <a name="enable-notifications-for-the-human-resources-app-in-teams"></a>Abilitare le notifiche per l'app Human Resources in Teams

Se si desidera che gli utenti ricevano le notifiche delle richieste di congedo nell'app Teams, è necessario abilitare le notifiche in Human Resources.

>[!NOTE]
>Solo gli utenti che hanno effettuato l'accesso a Teams e usano l'app Human Resources in Teams riceveranno le notifiche.

1. In Risorse umane, selezionare **Amministrazione sistema**.

2. Selezionare **Collegamenti**.

3. Sotto **Impostazione**, selezionare **Parametri di sistema**.

4. Nella scheda **Generale** impostare **Abilita notifiche per l'app Teams** su **Sì**.

   ![Abilitare le notifiche dell'app Teams nei parametri di sistema](./media/hr-admin-teams-leave-app-enable-notifications.png)

5. Per attivare le notifiche di Teams per tutti gli utenti, selezionare **Sì** alla richiesta.

   ![Abilitare le notifiche di Teams per tutti gli utenti](./media/hr-admin-teams-leave-app-notifications-all-users.png)

### <a name="turn-teams-notifications-on-or-off-for-individual-users"></a>Attivare o disattivare le notifiche di Teams per i singoli utenti

Dopo aver abilitato le notifiche per l'app Human Resources in Teams, è possibile attivare o disattivare le notifiche per i singoli utenti.

1. In Risorse umane, selezionare **Amministrazione sistema**.

2. Selezionare **Collegamenti**.

3. Sotto **Utenti**, selezionare **Opzioni utente**.

4. Selezionare la scheda **Flusso di lavoro**.

5. Impostare **Abilita le notifiche per l'app Teams** su **Sì** per abilitare le notifiche per l'utente o su **No** per disabilitare le notifiche per l'utente.

   ![Abilitare le notifiche dell'app Teams nella scheda Flusso di lavoro delle opzioni utente](./media/hr-admin-teams-leave-app-notifications.png)

6. Selezionare **Salva**.

## <a name="known-issues"></a>Problemi noti

| Uscita | Stato |
| --- | --- |
| Lo scorrimento orizzontale non funziona su telefoni Android | Lo scorrimento orizzontale non è un problema su iOS o su dispositivi desktop. Stiamo lavorando a una correzione per Android. |
| Il saldo non è corretto quando richiedi permessi per una data futura. | Le previsioni non sono ancora disponibili. Il saldo visualizza la data corrente. |
| Impossibile annullare una richiesta **In revisione**. | Questa funzionalità non è attualmente supportata e verrà aggiunta in una versione futura. |
| Le informazioni sul saldo sono calcolate a partire da oggi. | Il sistema al momento non visualizza i saldi al momento del periodo di competenza, anche se configurato nei parametri congedo e assenza. |

## <a name="privacy-notice"></a>Informativa sulla privacy

### <a name="microsoft-language-understanding-intelligent-service-luis"></a>Microsoft Language Understanding Intelligent Service (LUIS)

Con il bot Dynamics 365 Human Resources in Microsoft Teams, gli input di testo dell'utente vengono analizzati per comprendere la query/l'intento sottostanti. L'input dell'utente, ad esempio "Cerca account Contoso", viene indirizzato a uno dei servizi cognitivi di Microsoft chiamato Language Understanding Intelligent Service (LUIS). Ulteriori informazioni su LUIS [qui](https://www.luis.ai/). Il servizio LUIS disambigua o comprende l'intento dell'input dell'utente (in questo caso, l'intento è quello di trovare informazioni) e l'entità di destinazione (in questo caso, l'entità desiderata è un account chiamato Contoso). Queste informazioni vengono quindi trasmesse al  [Bot Framework di Azure](https://azure.microsoft.com/services/bot-service/) di Microsoft che interagisce con i dati da Dynamics 365 Human Resources e recupera le informazioni desiderate per la query dell'utente. 

Installando e consentendo l'accesso all'uso del bot, l'utente accetta di consentire al servizio LUIS e al framework del bot di Azure di elaborare l'intento dietro l'input, il che si traduce in un'esperienza utente conversazionale migliorata. Il servizio LUIS e il framework dei bot di Azure possono presentare livelli di conformità diversi rispetto a Dynamics 365 Human Resources. Mentre il servizio LUIS ha accesso solo alle query dell'utente e non è progettato per essere collegato ai dati o all'account Dynamics 365 Human Resources dell'utente, un utente del bot Dynamics 365 Human Resources potrebbe inserire volontariamente una query contenente dati del cliente, dati personali o altri dati e tale contenuto della query potrebbe essere inviato al servizio LUIS e al framework del bot di Azure. 

Il contenuto delle query e dei messaggi dell'utente viene conservato nel sistema LUIS per un massimo di 30 giorni, viene crittografato a riposo e non viene utilizzato per migliorare la formazione o il servizio. Ulteriori informazioni sui servizi cognitivi [qui](https://azure.microsoft.com/services/cognitive-services/language-understanding-intelligent-service/). 

Per gestire le impostazioni di amministrazione per le app in Microsoft Teams, vai all'[interfaccia di amministrazione di Microsoft Teams](https://admin.teams.microsoft.com/).

### <a name="microsoft-teams-azure-event-grid-and-azure-cosmos-db"></a>Microsoft Teams, Griglia di eventi di Azure e Azure Cosmos DB

Quando si utilizza l'app Dynamics 365 Human Resources in Microsoft Teams, alcuni dati dei clienti passeranno al di fuori dell'area geografica in cui è distribuito il servizio Human Resources del tenant.

Dynamics 365 Human Resources trasmette la richiesta di congedo del dipendente e i dettagli dell'attività del flusso di lavoro alla Griglia di eventi di Microsoft Azure e Microsoft Teams. Questi dati possono essere archiviati in Griglia di eventi di Microsoft Azure per un massimo di 24 ore e verranno elaborati negli Stati Uniti, vengono crittografati i dati in transito e inattivi e non vengono utilizzati da Microsoft o dai collaboratori di elaborazione per la formazione o il miglioramento del servizio. Per capire dove sono archiviati i dati in Teams, vedi: [Posizione dei dati in Microsoft Teams](https://docs.microsoft.com/microsoftteams/location-of-data-in-teams?view=o365-worldwide&preserve-view=true).

Durante la conversazione con il chat bot nell'app Human Resources, il contenuto della conversazione può essere archiviato in Azure Cosmos DB e trasmesso a Microsoft Teams. Questi dati possono essere archiviati in Azure Cosmos DB per un massimo di 24 ore e possono essere elaborati al di fuori dell'area geografica in cui è distribuito il servizio Human Resources del tenant, vengono crittografati i dati in transito e inattivi e non vengono utilizzati da Microsoft o dai collaboratori di elaborazione per la formazione o il miglioramento del servizio. Per capire dove sono archiviati i dati in Teams, vedi: [Posizione dei dati in Microsoft Teams](https://docs.microsoft.com/microsoftteams/location-of-data-in-teams?view=o365-worldwide&preserve-view=true).
 
Per limitare l'accesso all'app Human Resources in Microsoft Teams per la tua organizzazione o per gli utenti all'interno della tua organizzazione, vedi [Gestisci i criteri di autorizzazione delle app in Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/teams-app-permission-policies).

## <a name="see-also"></a>Vedere anche 

[Scaricare e installare Microsoft Teams](https://support.office.com/article/download-and-install-microsoft-teams-422bf3aa-9ae8-46f1-83a2-e65720e1a34d)</br>
[Centro assistenza di Microsoft Teams](https://support.office.com/teams)</br>
[Gestire le richieste di congedo in Teams](hr-teams-leave-app.md)

