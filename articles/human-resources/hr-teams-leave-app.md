---
title: Gestire le richieste di congedo in Teams
description: Questo argomento mostra come richiedere tempo libero nell'app Dynamics 365 Human Resources in Microsoft Teams.
author: andreabichsel
manager: tfehr
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: LeaveAbsenceWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-05-18
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 342106ad09db3a5d9c2dec8ab18e824d70e0f6bf
ms.sourcegitcommit: f8bac7ca2803913fd236adbc3806259a17a110f4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2021
ms.locfileid: "5128163"
---
# <a name="manage-leave-requests-in-teams"></a>Gestire le richieste di congedo in Teams

[!include [banner](includes/preview-feature.md)]

L'app Microsoft Dynamics 365 Human Resources in Microsoft Teams ti consente di richiedere rapidamente permessi e di visualizzare le informazioni sul loro saldo permessi direttamente in Microsoft Teams. Puoi interagire con un bot per richiedere informazioni e avviare una richiesta di congedo. La scheda **Tempo libero** fornisce informazioni più dettagliate. È inoltre possibile inviare alle persone informazioni sulla imminente indisponibilità in team e chat al di fuori dell'app Human Resources.

## <a name="install-the-app"></a>Installa l'app

Puoi trovare l'app Human Resources nello store di Teams.

1. In Microsoft Teams, seleziona i puntini di sospensione.

   ![Puntini di sospensione dell'app per i permessi Human Resources in Teams](./media/hr-teams-leave-app-ellipses.png)
 
2. Cerca Dynamics 365 Human Resources, quindi seleziona il riquadro **Human Resources**.

   ![Riquadro HR dell'app per i permessi Human Resources in Teams](./media/hr-teams-leave-app-human-resources-tile.png)

3. Seleziona il pulsante **Aggiungi** per installare l'app.

   ![Installazione dell'app per i permessi Human Resources in Teams](./media/hr-teams-leave-app-in-store.png)

Se l'app non ti consente di accede automaticamente, seleziona la scheda **impostazioni** per accedere.

![Scheda Impostazioni dell'app per i permessi Human Resources in Teams](./media/hr-teams-leave-app-settings-tab.png)

> [!NOTE]
> Se non vedi una finestra di accesso, controlla le impostazioni del browser per consentire i popup. 

Se hai accesso a più di un'istanza di Human Resources, puoi selezionare a quale ambiente vuoi connetterti nella scheda **Impostazioni**.

> [!NOTE]
> L'app ora supporta il ruolo di sicurezza Amministratore di sistema.
 
## <a name="use-the-bot"></a>Usa il bot

Dopo l'installazione dell'app, viene visualizzato un messaggio di benvenuto che ti informa sui tipi di azioni che il bot può eseguire per tuo conto.

![Messaggio di benvenuto del bot dell'app per i permessi Human Resources in Teams](./media/hr-teams-leave-app-bot.png)
 
> [!NOTE]
> Quando interagisci per la prima volta con il bot, potresti dover eseguire l'accesso. Se non vedi una finestra di accesso, controlla le impostazioni del browser per consentire i popup.

Puoi chiedere al bot di:

- Mostra le informazioni sul saldo dei permessi per ciascun tipo di congedo a cui sei registrato.

   ![Visualizzazione saldi dell'app per i permessi Human Resources in Teams](./media/hr-teams-leave-app-bot-balances.png)
 
- Mostra ulteriori dettagli su un tipo di congedo specifico.

   ![Visualizzazione dettagli dell'app per i permessi Human Resources in Teams](./media/hr-teams-leave-app-bot-details.png)

- Inizia una richiesta di ferie per te.

   ![Richiesta permesso dell'app per i permessi Human Resources in Teams](./media/hr-teams-leave-app-bot-request.png)
 
Dopo aver avviato una richiesta di congedo, è possibile modificare i giorni direttamente nella scheda.

![Modifica richiesta dell'app per i permessi Human Resources in Teams](./media/hr-teams-leave-app-bot-edit.png)
 
Al termine dell'immissione delle informazioni, selezionare **Invia** per inviarle per l'approvazione. Puoi anche selezionare **Salva come bozza** per tornare più tardi.

![Invio richiesta nell'app per i permessi Human Resources in Teams](./media/hr-teams-leave-app-bot-submit.png)

## <a name="manage-your-leave-in-teams"></a>Gestire i congedi in Teams

La scheda **Tempo libero** ti consente di visualizzare:

- Informazioni sul saldo per ciascun tipo di congedo a cui sei registrato

- Prossime richieste di congedo

- Richieste di tempo libero

- Bozza di richieste di congedo

![Scheda Tempo libero dell'app per i permessi Human Resources in Teams](./media/hr-teams-leave-app-timeoff-tab.png)
 
### <a name="create-a-new-request"></a>Crea una nuova richiesta

1. Per creare una nuova richiesta di congedo, seleziona **Nuova richiesta**.

   ![Nuova richiesta dell'app per i permessi Human Resources in Teams](./media/hr-teams-leave-app-timeoff-tab-new.png)

2. Immetti il giorno o i giorni che desideri prendere come congedo, quindi seleziona **Aggiungi**.

   ![Aggiungi congedo app per i permessi Human Resources in Teams](./media/hr-teams-leave-app-timeoff-tab-add.png)

3. Se applicabile, inserisci un codice motivo. Inserisci anche eventuali commenti e aggiungi eventuali allegati.

4. Al termine dell'immissione delle informazioni, digita **Invia** per inviarle per l'approvazione. Puoi anche digitare **Salva come bozza** per tornare più tardi.

### <a name="manage-draft-requests"></a>Gestisci bozze di richiesta

1. Seleziona la scheda **Bozze**.

   ![Scheda Bozze dell'app per i permessi Human Resources in Teams](./media/hr-teams-leave-app-drafts-tab.png)

2. Seleziona la matita per modificare la richiesta o seleziona il cestino per eliminare la richiesta.

3. Apporta le modifiche necessarie. Al termine dell'immissione delle informazioni, digita **Invia** per inviarle per l'approvazione. Puoi anche selezionare **Salva come bozza** per tornare più tardi.

   ![Modifica bozza dell'app per i permessi Human Resources in Teams](./media/hr-teams-leave-app-drafts-edit.png)
   
### <a name="respond-to-teams-notifications"></a>Rispondere alle notifiche di Teams

Quando l'utente o un lavoratore per cui l'utente è un approvatore invia una richiesta di congedo, viene ricevuta una notifica nell'app Human Resources in Teams. È possibile selezionare la notifica per visualizzarla. Le notifiche vengono visualizzate anche nell'area **Chat**.

Se l'utente è un approvatore, è possibile selezionare **Approva** o **Rifiuta** nella notifica. È anche possibile fornire un messaggio opzionale.

![Notifica della richiesta di congedo nell'app Human Resources in Teams](./media/hr-teams-leave-app-notification.png)

## <a name="send-upcoming-time-off-information-to-your-coworkers"></a>Inviare le informazioni sulla prossima indisponibilità ai tuoi colleghi

Dopo aver installato l'app Human Resources per Teams, puoi inviare facilmente informazioni sulla tua imminente indisponibilità ai tuoi colleghi in team o chat.

1. In un team o in una chat in Teams seleziona il pulsante Human Resources sotto la finestra della chat.

   ![Pulsante Human Resources sotto la finestra della chat](./media/hr-teams-leave-app-chat-button.png)

2. Seleziona la richiesta di congedo che desideri condividere. Se desideri condividere una bozza di richiesta di congedo, seleziona prima **Bozza**.

   ![Selezionare una richiesta di congedo imminente da condividere](./media/hr-teams-leave-app-chat-search.png)

La tua richiesta di congedo verrà visualizzata nella chat.

![Scheda richiesta di congedo per Human Resources](./media/hr-teams-leave-app-chat-card.png)

Se hai condiviso una bozza di richiesta, verrà visualizzata come bozza:

![Scheda richiesta di congedo per Human Resources](./media/hr-teams-leave-app-chat-draft-card.png)

## <a name="view-your-teams-leave-calendar"></a>Visualizzare un calendario di congedo del team

Se l'utente è un responsabile con diretti subalterni può visualizzare i congedi approvati e in sospeso del team.

1. Nell'app Human Resources in Teams selezionare **Permesso**.

2. Selezionare **Calendario del team**.

   ![Visualizzare il calendario nell'app Human Resources in Teams](./media/hr-teams-leave-app-view-calendar.png)

Il calendario mostra i permessi approvati e in attesa di approvazione dei diretti subalterni.

![Calendario dei permessi nell'app Human Resources in Teams](./media/hr-teams-leave-app-calendar.png)

## <a name="troubleshooting"></a>Risoluzione dei problemi

Se hai problemi ad accedere o utilizzare l'app Human Resources in Teams, prova a seguire queste istruzioni per la risoluzione dei problemi. Se i problemi persistono dopo la risoluzione dei problemi, contatta il supporto. Per ulteriori informazioni, vedere [Ottenere supporto](hr-admin-troubleshooting-support.md).

### <a name="cant-sign-into-the-human-resources-app-in-teams"></a>Non è possibile accedere all'app Human Resources in Teams

Se non riesci ad accedere all'app, è possibile che l'account che stai utilizzando per accedere a Microsoft Teams non è associato a un record dipendente in Dynamics 365 Human Resources. Contatta l'amministratore di sistema per assicurarti che il record dipendente sia associato correttamente.

### <a name="error-when-approving-leave-requests-in-the-human-resources-app-in-teams"></a>Errore durante l'approvazione delle richieste di congedo nell'app Human Resources in Teams

Se viene visualizzato un errore quando si tenta di approvare le richieste di congedo nell'app Teams, eseguire i seguenti passaggi di risoluzione dei problemi:

1. Verifica che l'account che stai utilizzando per accedere a Microsoft Teams sia quello utilizzato per accedere a Dynamics 365 Human Resources.

2. Verifica di essere un responsabile approvazione valido per la richiesta controllando le impostazioni del flusso di lavoro per l'approvazione del congedo. Per ulteriori informazioni sui flussi di lavoro delle richieste di congedo, vedi [Creare un flusso di lavoro di richieste di congedo](hr-leave-and-absence-workflow.md).

## <a name="known-accessibility-issues"></a>Problemi di accessibilità noti

L'app Human Resources in Teams presenta i seguenti problemi di accessibilità che stiamo cercando di risolvere nelle versioni future.

| Uscita | Soluzione o spiegazione |
| --- | --- |
| Lo zoom al 400% sul desktop nasconde alla vista alcuni pulsanti di azione. | Consigliamo di utilizzare invece una lente d'ingrandimento fino a quando non saremo in grado di supportare questo livello di zoom. |
| Nella scheda **Permesso**, VoiceOver annuncia l'azione di un pulsante durante la lettura dell'intestazione per la griglia del permesso. | L'intestazione e gli elementi all'interno della griglia sono raggruppati per anno e sono comprimibili. VoiceOver lo interpreta come un elemento utilizzabile, ma non lo è. |
| Nella scheda **Permesso** c'è un ulteriore gesto di scorrimento per la navigazione verso **Codice motivo** in una nuova richiesta. | Non ci sono controlli nascosti che la navigazione a scorrimento sta cercando di raggiungere. |
| Nella scheda **Permesso** se si scorre mentre il calendario è aperto, si esce dal controllo invece che all'inizio di una nuova richiesta o durante la modifica di una richiesta. | Quando si raggiunge **Vai a oggi**, considerarlo come la fine del controllo e scorrere nella direzione opposta per tornare all'inizio. |
| VoiceOver non legge le etichette per le date. | Le date rilevate in coppia sono sempre **Data d'inizio** e **Data di fine**. |
| Nella scheda **Chat**, lo stato attivo torna all'inizio quando si immette una data mentre si utilizza lo strumento di assistenza o la navigazione da tastiera. | Premere TAB fino a raggiungere nuovamente l'area di immissione. |

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
[App Human Resources in Teams](hr-admin-teams-leave-app.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]