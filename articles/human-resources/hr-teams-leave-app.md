---
title: Gestire le richieste di congedo in Teams
description: Questo argomento mostra come richiedere tempo libero nell'app Dynamics 365 Human Resources in Microsoft Teams.
author: andreabichsel
manager: AnnBe
ms.date: 09/30/2020
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
ms.openlocfilehash: c6856e417ee47f8f582f797c5bcedcff23a1432f
ms.sourcegitcommit: b6ab46f6e5ce60e2c3d70a348827eaf60c84cae2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2020
ms.locfileid: "3929995"
---
# <a name="manage-leave-requests-in-teams"></a><span data-ttu-id="c94bf-103">Gestire le richieste di congedo in Teams</span><span class="sxs-lookup"><span data-stu-id="c94bf-103">Manage leave requests in Teams</span></span>

[!include [banner](includes/preview-feature.md)]

<span data-ttu-id="c94bf-104">L'app Microsoft Dynamics 365 Human Resources in Microsoft Teams ti consente di richiedere rapidamente permessi e di visualizzare le informazioni sul loro saldo permessi direttamente in Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="c94bf-104">The Microsoft Dynamics 365 Human Resources app in Microsoft Teams lets you quickly request time off and view your time-off balance information right in Microsoft Teams.</span></span> <span data-ttu-id="c94bf-105">Puoi interagire con un bot per richiedere informazioni e avviare una richiesta di congedo.</span><span class="sxs-lookup"><span data-stu-id="c94bf-105">You can interact with a bot to request information and start a leave request.</span></span> <span data-ttu-id="c94bf-106">La scheda **Tempo libero** fornisce informazioni più dettagliate.</span><span class="sxs-lookup"><span data-stu-id="c94bf-106">The **Time off** tab provides more detailed information.</span></span> <span data-ttu-id="c94bf-107">Inoltre, puoi inviare alle persone informazioni sulla tua imminente indisponibilità in team e chat al di fuori dell'app Human Resources.</span><span class="sxs-lookup"><span data-stu-id="c94bf-107">In addition, you can send people information about your upcoming time off in teams and chats outside the Human Resources app.</span></span>

## <a name="install-the-app"></a><span data-ttu-id="c94bf-108">Installa l'app</span><span class="sxs-lookup"><span data-stu-id="c94bf-108">Install the app</span></span>

<span data-ttu-id="c94bf-109">Puoi trovare l'app Human Resources nello store di Teams.</span><span class="sxs-lookup"><span data-stu-id="c94bf-109">You can find the Human Resources app in the Teams store.</span></span>

1. <span data-ttu-id="c94bf-110">In Microsoft Teams, seleziona i puntini di sospensione.</span><span class="sxs-lookup"><span data-stu-id="c94bf-110">In Microsoft Teams, select the ellipses.</span></span>

   ![Puntini di sospensione dell'app per i permessi Human Resources in Teams](./media/hr-teams-leave-app-ellipses.png)
 
2. <span data-ttu-id="c94bf-112">Cerca Dynamics 365 Human Resources, quindi seleziona il riquadro **Human Resources**.</span><span class="sxs-lookup"><span data-stu-id="c94bf-112">Search for Dynamics 365 Human Resources, and then select the **Human Resources** tile.</span></span>

   ![Riquadro HR dell'app per i permessi Human Resources in Teams](./media/hr-teams-leave-app-human-resources-tile.png)

3. <span data-ttu-id="c94bf-114">Seleziona il pulsante **Aggiungi** per installare l'app.</span><span class="sxs-lookup"><span data-stu-id="c94bf-114">Select the **Add** button to install the app.</span></span>

   ![Installazione dell'app per i permessi Human Resources in Teams](./media/hr-teams-leave-app-in-store.png)

<span data-ttu-id="c94bf-116">Se l'app non ti consente di accede automaticamente, seleziona la scheda **impostazioni** per accedere.</span><span class="sxs-lookup"><span data-stu-id="c94bf-116">If the app doesn't automatically sign you in, select the **Settings** tab to sign in.</span></span>

![Scheda Impostazioni dell'app per i permessi Human Resources in Teams](./media/hr-teams-leave-app-settings-tab.png)

> [!NOTE]
> <span data-ttu-id="c94bf-118">Se non vedi una finestra di accesso, controlla le impostazioni del browser per consentire i popup.</span><span class="sxs-lookup"><span data-stu-id="c94bf-118">If you don’t see a sign-in dialog box, check your browser settings to allow pop-ups.</span></span> 

<span data-ttu-id="c94bf-119">Se hai accesso a più di un'istanza di Human Resources, puoi selezionare a quale ambiente vuoi connetterti nella scheda **Impostazioni**.</span><span class="sxs-lookup"><span data-stu-id="c94bf-119">If you have access to more than one instance of Human Resources, you can select which environment you want to connect to in the **Settings** tab.</span></span>

> [!NOTE]
> <span data-ttu-id="c94bf-120">L'app ora supporta il ruolo di sicurezza Amministratore di sistema.</span><span class="sxs-lookup"><span data-stu-id="c94bf-120">The app now supports the System Administrator security role.</span></span>
 
## <a name="use-the-bot"></a><span data-ttu-id="c94bf-121">Usa il bot</span><span class="sxs-lookup"><span data-stu-id="c94bf-121">Use the bot</span></span>

<span data-ttu-id="c94bf-122">Dopo l'installazione dell'app, viene visualizzato un messaggio di benvenuto che ti informa sui tipi di azioni che il bot può eseguire per tuo conto.</span><span class="sxs-lookup"><span data-stu-id="c94bf-122">After the app installs, a welcome message appears, letting you know the types of actions the bot can take on your behalf.</span></span>

![Messaggio di benvenuto del bot dell'app per i permessi Human Resources in Teams](./media/hr-teams-leave-app-bot.png)
 
> [!NOTE]
> <span data-ttu-id="c94bf-124">Quando interagisci per la prima volta con il bot, potresti dover eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="c94bf-124">When first interacting with the bot, you might need to sign in.</span></span> <span data-ttu-id="c94bf-125">Se non vedi una finestra di accesso, controlla le impostazioni del browser per consentire i popup.</span><span class="sxs-lookup"><span data-stu-id="c94bf-125">If you don’t see a sign-in dialog box, check your browser settings to allow pop-ups.</span></span>

<span data-ttu-id="c94bf-126">Puoi chiedere al bot di:</span><span class="sxs-lookup"><span data-stu-id="c94bf-126">You can ask the bot to:</span></span>

- <span data-ttu-id="c94bf-127">Mostra le informazioni sul saldo dei permessi per ciascun tipo di congedo a cui sei registrato.</span><span class="sxs-lookup"><span data-stu-id="c94bf-127">Show time-off balance information for each leave type you're enrolled in.</span></span>

   ![Visualizzazione saldi dell'app per i permessi Human Resources in Teams](./media/hr-teams-leave-app-bot-balances.png)
 
- <span data-ttu-id="c94bf-129">Mostra ulteriori dettagli su un tipo di congedo specifico.</span><span class="sxs-lookup"><span data-stu-id="c94bf-129">Show additional details about a specific leave type.</span></span>

   ![Visualizzazione dettagli dell'app per i permessi Human Resources in Teams](./media/hr-teams-leave-app-bot-details.png)

- <span data-ttu-id="c94bf-131">Inizia una richiesta di ferie per te.</span><span class="sxs-lookup"><span data-stu-id="c94bf-131">Start a leave request for you.</span></span>

   ![Richiesta permesso dell'app per i permessi Human Resources in Teams](./media/hr-teams-leave-app-bot-request.png)
 
<span data-ttu-id="c94bf-133">Dopo aver avviato una richiesta di congedo, è possibile modificare i giorni direttamente nella scheda.</span><span class="sxs-lookup"><span data-stu-id="c94bf-133">After you start a leave request, you can adjust the days right within the card.</span></span>

![Modifica richiesta dell'app per i permessi Human Resources in Teams](./media/hr-teams-leave-app-bot-edit.png)
 
<span data-ttu-id="c94bf-135">Al termine dell'immissione delle informazioni, selezionare **Invia** per inviarle per l'approvazione.</span><span class="sxs-lookup"><span data-stu-id="c94bf-135">When you're done entering information, select **Submit** to submit it for approval.</span></span> <span data-ttu-id="c94bf-136">Puoi anche selezionare **Salva come bozza** per tornare più tardi.</span><span class="sxs-lookup"><span data-stu-id="c94bf-136">You can also select **Save as draft** to come back to it later.</span></span>

![Invio richiesta nell'app per i permessi Human Resources in Teams](./media/hr-teams-leave-app-bot-submit.png)

## <a name="manage-your-leave-in-teams"></a><span data-ttu-id="c94bf-138">Gestire i congedi in Teams</span><span class="sxs-lookup"><span data-stu-id="c94bf-138">Manage your leave in Teams</span></span>

<span data-ttu-id="c94bf-139">La scheda **Tempo libero** ti consente di visualizzare:</span><span class="sxs-lookup"><span data-stu-id="c94bf-139">The **Time off** tab allows you to view:</span></span>

- <span data-ttu-id="c94bf-140">Informazioni sul saldo per ciascun tipo di congedo a cui sei registrato</span><span class="sxs-lookup"><span data-stu-id="c94bf-140">Balance information for each leave type you're enrolled in</span></span>

- <span data-ttu-id="c94bf-141">Prossime richieste di congedo</span><span class="sxs-lookup"><span data-stu-id="c94bf-141">Upcoming leave requests</span></span>

- <span data-ttu-id="c94bf-142">Richieste di tempo libero</span><span class="sxs-lookup"><span data-stu-id="c94bf-142">Time-off requests</span></span>

- <span data-ttu-id="c94bf-143">Bozza di richieste di congedo</span><span class="sxs-lookup"><span data-stu-id="c94bf-143">Draft leave requests</span></span>

![Scheda Tempo libero dell'app per i permessi Human Resources in Teams](./media/hr-teams-leave-app-timeoff-tab.png)
 
### <a name="create-a-new-request"></a><span data-ttu-id="c94bf-145">Crea una nuova richiesta</span><span class="sxs-lookup"><span data-stu-id="c94bf-145">Create a new request</span></span>

1. <span data-ttu-id="c94bf-146">Per creare una nuova richiesta di congedo, seleziona **Nuova richiesta**.</span><span class="sxs-lookup"><span data-stu-id="c94bf-146">To create a new leave request, select **New request**.</span></span>

   ![Nuova richiesta dell'app per i permessi Human Resources in Teams](./media/hr-teams-leave-app-timeoff-tab-new.png)

2. <span data-ttu-id="c94bf-148">Immetti il giorno o i giorni che desideri prendere come congedo, quindi seleziona **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="c94bf-148">Enter the day or days you want to take off, and then select **Add**.</span></span>

   ![Aggiungi congedo app per i permessi Human Resources in Teams](./media/hr-teams-leave-app-timeoff-tab-add.png)

3. <span data-ttu-id="c94bf-150">Se applicabile, inserisci un codice motivo.</span><span class="sxs-lookup"><span data-stu-id="c94bf-150">If applicable, enter a reason code.</span></span> <span data-ttu-id="c94bf-151">Inserisci anche eventuali commenti e aggiungi eventuali allegati.</span><span class="sxs-lookup"><span data-stu-id="c94bf-151">Also enter any comments and add any attachments.</span></span>

4. <span data-ttu-id="c94bf-152">Al termine dell'immissione delle informazioni, digita **Invia** per inviarle per l'approvazione.</span><span class="sxs-lookup"><span data-stu-id="c94bf-152">When you're done entering information, type **Submit** to submit it for approval.</span></span> <span data-ttu-id="c94bf-153">Puoi anche digitare **Salva come bozza** per tornare più tardi.</span><span class="sxs-lookup"><span data-stu-id="c94bf-153">You can also type **Save as draft** to come back to it later.</span></span>

### <a name="manage-draft-requests"></a><span data-ttu-id="c94bf-154">Gestisci bozze di richiesta</span><span class="sxs-lookup"><span data-stu-id="c94bf-154">Manage draft requests</span></span>

1. <span data-ttu-id="c94bf-155">Seleziona la scheda **Bozze**.</span><span class="sxs-lookup"><span data-stu-id="c94bf-155">Select the **Drafts** tab.</span></span>

   ![Scheda Bozze dell'app per i permessi Human Resources in Teams](./media/hr-teams-leave-app-drafts-tab.png)

2. <span data-ttu-id="c94bf-157">Seleziona la matita per modificare la richiesta o seleziona il cestino per eliminare la richiesta.</span><span class="sxs-lookup"><span data-stu-id="c94bf-157">Select the pencil to edit the request, or select the trash can to delete the request.</span></span>

3. <span data-ttu-id="c94bf-158">Apporta le modifiche necessarie.</span><span class="sxs-lookup"><span data-stu-id="c94bf-158">Make any necessary changes.</span></span> <span data-ttu-id="c94bf-159">Al termine dell'immissione delle informazioni, digita **Invia** per inviarle per l'approvazione.</span><span class="sxs-lookup"><span data-stu-id="c94bf-159">When you're done entering information, type **Submit** to submit it for approval.</span></span> <span data-ttu-id="c94bf-160">Puoi anche selezionare **Salva come bozza** per tornare più tardi.</span><span class="sxs-lookup"><span data-stu-id="c94bf-160">You can also select **Save as draft** to come back to it later.</span></span>

   ![Modifica bozza dell'app per i permessi Human Resources in Teams](./media/hr-teams-leave-app-drafts-edit.png)
   
### <a name="respond-to-teams-notifications"></a><span data-ttu-id="c94bf-162">Rispondere alle notifiche di Teams</span><span class="sxs-lookup"><span data-stu-id="c94bf-162">Respond to Teams notifications</span></span>

<span data-ttu-id="c94bf-163">Quando l'utente o un lavoratore per cui l'utente è un approvatore invia una richiesta di congedo, viene ricevuta una notifica nell'app Human Resources in Teams.</span><span class="sxs-lookup"><span data-stu-id="c94bf-163">When you or a worker you're an approver for submits a leave request, you'll receive a notification in the Human Resources app in Teams.</span></span> <span data-ttu-id="c94bf-164">È possibile selezionare la notifica per visualizzarla.</span><span class="sxs-lookup"><span data-stu-id="c94bf-164">You can select the notification to view it.</span></span> <span data-ttu-id="c94bf-165">Le notifiche vengono visualizzate anche nell'area **Chat**.</span><span class="sxs-lookup"><span data-stu-id="c94bf-165">Notifications also appear in the **Chat** area.</span></span>

<span data-ttu-id="c94bf-166">Se l'utente è un approvatore, è possibile selezionare **Approva** o **Rifiuta** nella notifica.</span><span class="sxs-lookup"><span data-stu-id="c94bf-166">If you're an approver, you can select **Approve** or **Deny** in the notification.</span></span> <span data-ttu-id="c94bf-167">È anche possibile fornire un messaggio opzionale.</span><span class="sxs-lookup"><span data-stu-id="c94bf-167">You can also provide an optional message.</span></span>

![Notifica della richiesta di congedo nell'app Human Resources in Teams](./media/hr-teams-leave-app-notification.png)

## <a name="send-upcoming-time-off-information-to-your-coworkers"></a><span data-ttu-id="c94bf-169">Inviare le informazioni sulla prossima indisponibilità ai tuoi colleghi</span><span class="sxs-lookup"><span data-stu-id="c94bf-169">Send upcoming time-off information to your coworkers</span></span>

<span data-ttu-id="c94bf-170">Dopo aver installato l'app Human Resources per Teams, puoi inviare facilmente informazioni sulla tua imminente indisponibilità ai tuoi colleghi in team o chat.</span><span class="sxs-lookup"><span data-stu-id="c94bf-170">After you install the Human Resources app for Teams, you can easily send information about your upcoming time off to your coworkers in teams or chats.</span></span>

1. <span data-ttu-id="c94bf-171">In un team o in una chat in Teams seleziona il pulsante Human Resources sotto la finestra della chat.</span><span class="sxs-lookup"><span data-stu-id="c94bf-171">In a team or chat in Teams, select the Human Resources button below the chat window.</span></span>

   ![Pulsante Human Resources sotto la finestra della chat](./media/hr-teams-leave-app-chat-button.png)

2. <span data-ttu-id="c94bf-173">Seleziona la richiesta di congedo che desideri condividere.</span><span class="sxs-lookup"><span data-stu-id="c94bf-173">Select the leave request you want to share.</span></span> <span data-ttu-id="c94bf-174">Se desideri condividere una bozza di richiesta di congedo, seleziona prima **Bozza**.</span><span class="sxs-lookup"><span data-stu-id="c94bf-174">If you want to share a draft leave request, select **Drafts** first.</span></span>

   ![Selezionare una richiesta di congedo imminente da condividere](./media/hr-teams-leave-app-chat-search.png)

<span data-ttu-id="c94bf-176">La tua richiesta di congedo verrà visualizzata nella chat.</span><span class="sxs-lookup"><span data-stu-id="c94bf-176">Your leave request will display in the chat.</span></span>

![Scheda richiesta di congedo per Human Resources](./media/hr-teams-leave-app-chat-card.png)

<span data-ttu-id="c94bf-178">Se hai condiviso una bozza di richiesta, verrà visualizzata come bozza:</span><span class="sxs-lookup"><span data-stu-id="c94bf-178">If you shared a draft request, it will display as a draft:</span></span>

![Scheda richiesta di congedo per Human Resources](./media/hr-teams-leave-app-chat-draft-card.png)

## <a name="view-your-teams-leave-calendar"></a><span data-ttu-id="c94bf-180">Visualizzare un calendario di congedo del team</span><span class="sxs-lookup"><span data-stu-id="c94bf-180">View your team's leave calendar</span></span>

<span data-ttu-id="c94bf-181">Se l'utente è un responsabile con diretti subalterni può visualizzare i congedi approvati e in sospeso del team.</span><span class="sxs-lookup"><span data-stu-id="c94bf-181">If you're a manager with direct reports, you can view your team's approved and pending time off.</span></span>

1. <span data-ttu-id="c94bf-182">Nell'app Human Resources in Teams selezionare **Permesso**.</span><span class="sxs-lookup"><span data-stu-id="c94bf-182">In the Human Resources app in Teams, select **Time off**.</span></span>

2. <span data-ttu-id="c94bf-183">Selezionare **Calendario del team**.</span><span class="sxs-lookup"><span data-stu-id="c94bf-183">Select **Team calendar**.</span></span>

   ![Visualizzare il calendario nell'app Human Resources in Teams](./media/hr-teams-leave-app-view-calendar.png)

<span data-ttu-id="c94bf-185">Il calendario mostra i permessi approvati e in attesa di approvazione dei diretti subalterni.</span><span class="sxs-lookup"><span data-stu-id="c94bf-185">The calendar displays your direct reports' approved and pending time off.</span></span>

![Calendario dei permessi nell'app Human Resources in Teams](./media/hr-teams-leave-app-calendar.png)

## <a name="troubleshooting"></a><span data-ttu-id="c94bf-187">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="c94bf-187">Troubleshooting</span></span>

<span data-ttu-id="c94bf-188">Se hai problemi ad accedere o utilizzare l'app Human Resources in Teams, prova a seguire queste istruzioni per la risoluzione dei problemi.</span><span class="sxs-lookup"><span data-stu-id="c94bf-188">If you're having trouble signing into or using the Human Resources Teams app, try following these troubleshooting instructions.</span></span> <span data-ttu-id="c94bf-189">Se i problemi persistono dopo la risoluzione dei problemi, contatta il supporto.</span><span class="sxs-lookup"><span data-stu-id="c94bf-189">If you're still having problems after troubleshooting, contact Support.</span></span> <span data-ttu-id="c94bf-190">Per ulteriori informazioni, vedere [Ottenere supporto](hr-admin-troubleshooting-support.md).</span><span class="sxs-lookup"><span data-stu-id="c94bf-190">For more information, see [Get support](hr-admin-troubleshooting-support.md).</span></span>

### <a name="cant-sign-into-the-human-resources-app-in-teams"></a><span data-ttu-id="c94bf-191">Non è possibile accedere all'app Human Resources in Teams</span><span class="sxs-lookup"><span data-stu-id="c94bf-191">Can't sign into the Human Resources app in Teams</span></span>

<span data-ttu-id="c94bf-192">Se non riesci ad accedere all'app, è possibile che l'account che stai utilizzando per accedere a Microsoft Teams non è associato a un record dipendente in Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="c94bf-192">If you can't sign into the app, it's possible that the account you're using to sign into Microsoft Teams isn't associated with an employee record in Dynamics 365 Human Resources.</span></span> <span data-ttu-id="c94bf-193">Contatta l'amministratore di sistema per assicurarti che il record dipendente sia associato correttamente.</span><span class="sxs-lookup"><span data-stu-id="c94bf-193">Contact your system administrator to ensure your employee record is correctly associated.</span></span>

### <a name="error-when-approving-leave-requests-in-the-human-resources-app-in-teams"></a><span data-ttu-id="c94bf-194">Errore durante l'approvazione delle richieste di congedo nell'app Human Resources in Teams</span><span class="sxs-lookup"><span data-stu-id="c94bf-194">Error when approving leave requests in the Human Resources app in Teams</span></span>

<span data-ttu-id="c94bf-195">Se viene visualizzato un errore quando si tenta di approvare le richieste di congedo nell'app Teams, esegui i seguenti passaggi di risoluzione dei problemi:</span><span class="sxs-lookup"><span data-stu-id="c94bf-195">If you receive an error when you're trying to approve leave requests in the Teams app, perform the following troubleshooting steps:</span></span>

1. <span data-ttu-id="c94bf-196">Verifica che l'account che stai utilizzando per accedere a Microsoft Teams sia quello utilizzato per accedere a Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="c94bf-196">Verify that the account you're using to sign into Microsoft Teams is the same one you use for accessing Dynamics 365 Human Resources.</span></span>

2. <span data-ttu-id="c94bf-197">Verifica di essere un responsabile approvazione valido per la richiesta controllando le impostazioni del flusso di lavoro per l'approvazione del congedo.</span><span class="sxs-lookup"><span data-stu-id="c94bf-197">Verify that you're a valid approver for the request by checking the workflow settings for leave approval.</span></span> <span data-ttu-id="c94bf-198">Per ulteriori informazioni sui flussi di lavoro delle richieste di congedo, vedi [Creare un flusso di lavoro di richieste di congedo](hr-leave-and-absence-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="c94bf-198">For more information about leave request workflows, see [Create a leave request workflow](hr-leave-and-absence-workflow.md).</span></span>

## <a name="privacy-notice"></a><span data-ttu-id="c94bf-199">Informativa sulla privacy</span><span class="sxs-lookup"><span data-stu-id="c94bf-199">Privacy notice</span></span>

### <a name="microsoft-language-understanding-intelligent-service-luis"></a><span data-ttu-id="c94bf-200">Microsoft Language Understanding Intelligent Service (LUIS)</span><span class="sxs-lookup"><span data-stu-id="c94bf-200">Microsoft Language Understanding Intelligent Service (LUIS)</span></span>

<span data-ttu-id="c94bf-201">Con il bot Dynamics 365 Human Resources in Microsoft Teams, gli input di testo dell'utente vengono analizzati per comprendere la query/l'intento sottostanti.</span><span class="sxs-lookup"><span data-stu-id="c94bf-201">With the Dynamics 365 Human Resources bot in Microsoft Teams, the user’s text inputs are analyzed for understanding the underlying query/intent.</span></span> <span data-ttu-id="c94bf-202">L'input dell'utente, ad esempio "Cerca account Contoso", viene indirizzato a uno dei servizi cognitivi di Microsoft chiamato Language Understanding Intelligent Service (LUIS).</span><span class="sxs-lookup"><span data-stu-id="c94bf-202">The user’s input such as “Search account Contoso” is routed to one of Microsoft’s Cognitive Service called Language Understanding Intelligent Service (LUIS).</span></span> <span data-ttu-id="c94bf-203">Ulteriori informazioni su LUIS [qui](https://www.luis.ai/).</span><span class="sxs-lookup"><span data-stu-id="c94bf-203">Read more about LUIS [here](https://www.luis.ai/).</span></span> <span data-ttu-id="c94bf-204">Il servizio LUIS disambigua o comprende l'intento dell'input dell'utente (in questo caso, l'intento è quello di trovare informazioni) e l'entità di destinazione (in questo caso, l'entità desiderata è un account chiamato Contoso).</span><span class="sxs-lookup"><span data-stu-id="c94bf-204">The LUIS service disambiguates or understands the intent of user input (in this case, the intent is to find information) and the target entity (in this case, the intended entity is an account named Contoso).</span></span> <span data-ttu-id="c94bf-205">Queste informazioni vengono quindi trasmesse al  [Bot Framework di Azure](https://azure.microsoft.com/services/bot-service/) di Microsoft che interagisce con i dati da Dynamics 365 Human Resources e recupera le informazioni desiderate per la query dell'utente.</span><span class="sxs-lookup"><span data-stu-id="c94bf-205">This information is then passed on to Microsoft’s [Azure bot framework](https://azure.microsoft.com/services/bot-service/), which interacts with data from Dynamics 365 Human Resources and retrieves the desired information for the user query.</span></span> 

<span data-ttu-id="c94bf-206">Installando e consentendo l'accesso all'uso del bot, l'utente accetta di consentire al servizio LUIS e al framework del bot di Azure di elaborare l'intento dietro l'input, il che si traduce in un'esperienza utente conversazionale migliorata.</span><span class="sxs-lookup"><span data-stu-id="c94bf-206">By installing and allowing access to use of the bot, you agree to allow the LUIS service and Azure bot framework to process the intent behind the input,  which results in an enhanced conversational user experience.</span></span> <span data-ttu-id="c94bf-207">Il servizio LUIS e il framework dei bot di Azure possono presentare livelli di conformità diversi rispetto a Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="c94bf-207">The LUIS service and Azure bot framework may have varying levels of compliance compared to Dynamics 365 Human Resources.</span></span> <span data-ttu-id="c94bf-208">Mentre il servizio LUIS ha accesso solo alle query dell'utente e non è progettato per essere collegato ai dati o all'account Dynamics 365 Human Resources dell'utente, un utente del bot Dynamics 365 Human Resources potrebbe inserire volontariamente una query contenente dati del cliente, dati personali o altri dati e tale contenuto della query potrebbe essere inviato al servizio LUIS e al framework del bot di Azure.</span><span class="sxs-lookup"><span data-stu-id="c94bf-208">While the LUIS service has access to only the user queries and is not designed to be connected to the user’s Dynamics 365 Human Resources data or account, a user of the Dynamics 365 Human Resources bot could voluntarily enter a query containing Customer Data, Personal Data, or other data and such query content could get sent to the LUIS service and the Azure bot framework.</span></span> 

<span data-ttu-id="c94bf-209">Il contenuto delle query e dei messaggi dell'utente viene conservato nel sistema LUIS per un massimo di 30 giorni, viene crittografato a riposo e non viene utilizzato per migliorare la formazione o il servizio.</span><span class="sxs-lookup"><span data-stu-id="c94bf-209">The content of user’s queries and messages is retained in LUIS system for a maximum of 30 days, is encrypted at rest, and is not used for training or service improvement.</span></span> <span data-ttu-id="c94bf-210">Ulteriori informazioni sui servizi cognitivi [qui](https://azure.microsoft.com/services/cognitive-services/language-understanding-intelligent-service/).</span><span class="sxs-lookup"><span data-stu-id="c94bf-210">Read more about Cognitive Services [here](https://azure.microsoft.com/services/cognitive-services/language-understanding-intelligent-service/).</span></span> 

<span data-ttu-id="c94bf-211">Per gestire le impostazioni di amministrazione per le app in Microsoft Teams, vai all'[interfaccia di amministrazione di Microsoft Teams](https://admin.teams.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="c94bf-211">To manage admin settings for apps in Microsoft Teams, go to the [Microsoft Teams admin center](https://admin.teams.microsoft.com/).</span></span>

### <a name="microsoft-teams-azure-event-grid-and-azure-cosmos-db"></a><span data-ttu-id="c94bf-212">Microsoft Teams, Griglia di eventi di Azure e Azure Cosmos DB</span><span class="sxs-lookup"><span data-stu-id="c94bf-212">Microsoft Teams, Azure Event Grid, and Azure Cosmos DB</span></span>

<span data-ttu-id="c94bf-213">Quando si utilizza l'app Dynamics 365 Human Resources in Microsoft Teams, alcuni dati dei clienti passeranno al di fuori dell'area geografica in cui è distribuito il servizio Human Resources del tenant.</span><span class="sxs-lookup"><span data-stu-id="c94bf-213">When using the Dynamics 365 Human Resources app in Microsoft Teams, certain customer data may flow outside of the geographic region where your tenant’s Human Resources service is deployed.</span></span>

<span data-ttu-id="c94bf-214">Dynamics 365 Human Resources trasmette la richiesta di congedo del dipendente e i dettagli dell'attività del flusso di lavoro alla Griglia di eventi di Microsoft Azure e Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="c94bf-214">Dynamics 365 Human Resources transmits the employee’s leave request and workflow task details to Microsoft Azure Event Grid and Microsoft Teams.</span></span> <span data-ttu-id="c94bf-215">Questi dati possono essere archiviati in Griglia di eventi di Microsoft Azure per un massimo di 24 ore e verranno elaborati negli Stati Uniti, vengono crittografati i dati in transito e inattivi e non vengono utilizzati da Microsoft o dai collaboratori di elaborazione per la formazione o il miglioramento del servizio.</span><span class="sxs-lookup"><span data-stu-id="c94bf-215">This data may be stored in Microsoft Azure Event Grid for up to 24 hours and will be processed in the United States, is encrypted in transit and at rest, and is not used by Microsoft or its subprocessors for training or service improvements.</span></span> <span data-ttu-id="c94bf-216">Per capire dove sono archiviati i dati in Teams, vedi: [Posizione dei dati in Microsoft Teams](https://docs.microsoft.com/microsoftteams/location-of-data-in-teams?view=o365-worldwide&preserve-view=true).</span><span class="sxs-lookup"><span data-stu-id="c94bf-216">To understand where your data is stored in Teams, please see: [Location of data in Microsoft Teams](https://docs.microsoft.com/microsoftteams/location-of-data-in-teams?view=o365-worldwide&preserve-view=true).</span></span>

<span data-ttu-id="c94bf-217">Durante la conversazione con il chat bot nell'app Human Resources, il contenuto della conversazione può essere archiviato in Azure Cosmos DB e trasmesso a Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="c94bf-217">While conversing with the chat bot in the Human Resources app, the conversation content may be stored in Azure Cosmos DB and transmitted to Microsoft Teams.</span></span> <span data-ttu-id="c94bf-218">Questi dati possono essere archiviati in Azure Cosmos DB per un massimo di 24 ore e possono essere elaborati al di fuori dell'area geografica in cui è distribuito il servizio Human Resources del tenant, vengono crittografati i dati in transito e inattivi e non vengono utilizzati da Microsoft o dai collaboratori di elaborazione per la formazione o il miglioramento del servizio.</span><span class="sxs-lookup"><span data-stu-id="c94bf-218">This data may be stored in Azure Cosmos DB for up to 24 hours and may be processed outside of the geographic region where your tenant's Human Resources service is deployed, is encrypted in transit and at rest, and is not used by Microsoft or its subprocessors for training or service improvements.</span></span> <span data-ttu-id="c94bf-219">Per capire dove sono archiviati i dati in Teams, vedi: [Posizione dei dati in Microsoft Teams](https://docs.microsoft.com/microsoftteams/location-of-data-in-teams?view=o365-worldwide&preserve-view=true).</span><span class="sxs-lookup"><span data-stu-id="c94bf-219">To understand where your data is stored in Teams, please see: [Location of data in Microsoft Teams](https://docs.microsoft.com/microsoftteams/location-of-data-in-teams?view=o365-worldwide&preserve-view=true).</span></span>
 
<span data-ttu-id="c94bf-220">Per limitare l'accesso all'app Human Resources in Microsoft Teams per la tua organizzazione o per gli utenti all'interno della tua organizzazione, vedi [Gestisci i criteri di autorizzazione delle app in Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/teams-app-permission-policies).</span><span class="sxs-lookup"><span data-stu-id="c94bf-220">To restrict access to the Human Resources app in Microsoft Teams for your organization or users within your organization, see [Manage app permission policies in Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/teams-app-permission-policies).</span></span>

## <a name="see-also"></a><span data-ttu-id="c94bf-221">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c94bf-221">See also</span></span>

[<span data-ttu-id="c94bf-222">Scaricare e installare Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c94bf-222">Download and install Microsoft Teams</span></span>](https://support.office.com/article/download-and-install-microsoft-teams-422bf3aa-9ae8-46f1-83a2-e65720e1a34d)</br>
[<span data-ttu-id="c94bf-223">Centro assistenza di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c94bf-223">Microsoft Teams help center</span></span>](https://support.office.com/teams)</br>
[<span data-ttu-id="c94bf-224">App Human Resources in Teams</span><span class="sxs-lookup"><span data-stu-id="c94bf-224">Human Resources app in Teams</span></span>](hr-admin-teams-leave-app.md)
