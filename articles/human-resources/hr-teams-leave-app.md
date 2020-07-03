---
title: Gestire le richieste di congedo in Teams
description: Questo argomento mostra come richiedere tempo libero nell'app Dynamics 365 Human Resources in Microsoft Teams.
author: andreabichsel
manager: AnnBe
ms.date: 05/18/2020
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
ms.openlocfilehash: b3daa76385518ad4c7150fa93ce33be0351bfd57
ms.sourcegitcommit: ba340f836e472f13f263dec46a49847c788fca44
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "3428830"
---
# <a name="manage-leave-requests-in-teams"></a>Gestire le richieste di congedo in Teams

[!include [banner](includes/preview-feature.md)]

L'app Microsoft Dynamics 365 Human Resources in Microsoft Teams ti consente di richiedere rapidamente permessi e di visualizzare le informazioni sul loro saldo permessi direttamente in Microsoft Teams. Puoi interagire con un bot per richiedere informazioni. La scheda **Tempo libero** fornisce informazioni più dettagliate.

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

> [!WARNING]
> L'app al momento non supporta il ruolo di sicurezza dell'amministratore di sistema e visualizzerà un messaggio di errore se accedi con un account dell'amministratore di sistema. Per accedere con un altro account, nella scheda **Impostazioni**, seleziona il pulsante **Cambia account**, quindi accedi con un account utente che non dispone dei privilegi di amministratore di sistema.
 
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
 
Dopo aver avviato una richiesta di ferie, è possibile modificare i giorni direttamente all'interno della carta oppure selezionare **Modifica dettagli** per aggiungere ulteriori informazioni alla tua richiesta.

![Modifica richiesta dell'app per i permessi Human Resources in Teams](./media/hr-teams-leave-app-bot-edit.png)
 
Al termine dell'immissione delle informazioni, digita **Invia** per inviarle per l'approvazione. Puoi anche digitare **Salva come bozza** per tornare più tardi.

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
   
## <a name="privacy-notice"></a>Informativa sulla privacy

Con il bot Dynamics 365 Human Resources in Microsoft Teams, gli input di testo dell'utente vengono analizzati per comprendere la query/l'intento sottostanti. L'input dell'utente, ad esempio "Cerca account Contoso", viene indirizzato a uno dei servizi cognitivi di Microsoft chiamato Language Understanding Intelligent Service (LUIS). Ulteriori informazioni su LUIS [qui](https://www.luis.ai/). Il servizio LUIS disambigua o comprende l'intento dell'input dell'utente (in questo caso, l'intento è quello di trovare informazioni) e l'entità di destinazione (in questo caso, l'entità desiderata è un account chiamato Contoso). Queste informazioni vengono quindi trasmesse al [Framework bot di Azure](https://azure.microsoft.com/services/bot-service/) di Microsoft che interagisce con i dati da Dynamics 365 Human Resources e recupera le informazioni desiderate per la query dell'utente. 

Installando e consentendo l'accesso all'uso del bot, l'utente accetta di consentire al servizio LUIS e al framework del bot di Azure di elaborare l'intento dietro l'input, il che si traduce in un'esperienza utente conversazionale migliorata. Il servizio LUIS e il framework dei bot di Azure possono presentare livelli di conformità diversi rispetto a Dynamics 365 Human Resources. Mentre il servizio LUIS ha accesso solo alle query dell'utente e non è progettato per essere collegato ai dati o all'account Dynamics 365 Human Resources dell'utente, un utente del bot Dynamics 365 Human Resources potrebbe inserire volontariamente una query contenente dati del cliente, dati personali o altri dati e tale contenuto della query potrebbe essere inviato al servizio LUIS e al framework del bot di Azure. 

Il contenuto delle query e dei messaggi dell'utente viene conservato nel sistema LUIS per un massimo di 30 giorni, viene crittografato a riposo e non viene utilizzato per migliorare la formazione o il servizio. Ulteriori informazioni sui servizi cognitivi [qui](https://azure.microsoft.com/services/cognitive-services/language-understanding-intelligent-service/). 

Per gestire le impostazioni di amministrazione per le app in Microsoft Teams, vai all'[interfaccia di amministrazione di Microsoft Teams](https://admin.teams.microsoft.com/). 

## <a name="see-also"></a>Vedere anche

[Scaricare e installare Microsoft Teams](https://support.office.com/article/download-and-install-microsoft-teams-422bf3aa-9ae8-46f1-83a2-e65720e1a34d)</br>
[Centro assistenza di Microsoft Teams](https://support.office.com/teams)</br>
[App Human Resources in Teams](hr-admin-teams-leave-app.md)
