---
title: Gestire le richieste di congedo in Teams
description: Questo argomento mostra come richiedere tempo libero nell'app Dynamics 365 Human Resources in Microsoft Teams.
author: andreabichsel
manager: AnnBe
ms.date: 09/03/2020
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
ms.openlocfilehash: 0fbf44fe35af3147fd5fb478b6cbfc5a5d0b109d
ms.sourcegitcommit: 5b620f670ac0f403a0fdcdeb9c3f970b163191ee
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2020
ms.locfileid: "3766762"
---
# <a name="manage-leave-requests-in-teams"></a><span data-ttu-id="cf2c3-103">Gestire le richieste di congedo in Teams</span><span class="sxs-lookup"><span data-stu-id="cf2c3-103">Manage leave requests in Teams</span></span>

[!include [banner](includes/preview-feature.md)]

<span data-ttu-id="cf2c3-104">L'app Microsoft Dynamics 365 Human Resources in Microsoft Teams ti consente di richiedere rapidamente permessi e di visualizzare le informazioni sul loro saldo permessi direttamente in Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="cf2c3-104">The Microsoft Dynamics 365 Human Resources app in Microsoft Teams lets you quickly request time off and view your time-off balance information right in Microsoft Teams.</span></span> <span data-ttu-id="cf2c3-105">Puoi interagire con un bot per richiedere informazioni.</span><span class="sxs-lookup"><span data-stu-id="cf2c3-105">You can interact with a bot to request information.</span></span> <span data-ttu-id="cf2c3-106">La scheda **Tempo libero** fornisce informazioni più dettagliate.</span><span class="sxs-lookup"><span data-stu-id="cf2c3-106">The **Time off** tab provides more detailed information.</span></span>

## <a name="install-the-app"></a><span data-ttu-id="cf2c3-107">Installa l'app</span><span class="sxs-lookup"><span data-stu-id="cf2c3-107">Install the app</span></span>

<span data-ttu-id="cf2c3-108">Puoi trovare l'app Human Resources nello store di Teams.</span><span class="sxs-lookup"><span data-stu-id="cf2c3-108">You can find the Human Resources app in the Teams store.</span></span>

1. <span data-ttu-id="cf2c3-109">In Microsoft Teams, seleziona i puntini di sospensione.</span><span class="sxs-lookup"><span data-stu-id="cf2c3-109">In Microsoft Teams, select the ellipses.</span></span>

   ![Puntini di sospensione dell'app per i permessi Human Resources in Teams](./media/hr-teams-leave-app-ellipses.png)
 
2. <span data-ttu-id="cf2c3-111">Cerca Dynamics 365 Human Resources, quindi seleziona il riquadro **Human Resources**.</span><span class="sxs-lookup"><span data-stu-id="cf2c3-111">Search for Dynamics 365 Human Resources, and then select the **Human Resources** tile.</span></span>

   ![Riquadro HR dell'app per i permessi Human Resources in Teams](./media/hr-teams-leave-app-human-resources-tile.png)

3. <span data-ttu-id="cf2c3-113">Seleziona il pulsante **Aggiungi** per installare l'app.</span><span class="sxs-lookup"><span data-stu-id="cf2c3-113">Select the **Add** button to install the app.</span></span>

   ![Installazione dell'app per i permessi Human Resources in Teams](./media/hr-teams-leave-app-in-store.png)

<span data-ttu-id="cf2c3-115">Se l'app non ti consente di accede automaticamente, seleziona la scheda **impostazioni** per accedere.</span><span class="sxs-lookup"><span data-stu-id="cf2c3-115">If the app doesn't automatically sign you in, select the **Settings** tab to sign in.</span></span>

![Scheda Impostazioni dell'app per i permessi Human Resources in Teams](./media/hr-teams-leave-app-settings-tab.png)

> [!NOTE]
> <span data-ttu-id="cf2c3-117">Se non vedi una finestra di accesso, controlla le impostazioni del browser per consentire i popup.</span><span class="sxs-lookup"><span data-stu-id="cf2c3-117">If you don’t see a sign-in dialog box, check your browser settings to allow pop-ups.</span></span> 

<span data-ttu-id="cf2c3-118">Se hai accesso a più di un'istanza di Human Resources, puoi selezionare a quale ambiente vuoi connetterti nella scheda **Impostazioni**.</span><span class="sxs-lookup"><span data-stu-id="cf2c3-118">If you have access to more than one instance of Human Resources, you can select which environment you want to connect to in the **Settings** tab.</span></span>

> [!WARNING]
> <span data-ttu-id="cf2c3-119">L'app al momento non supporta il ruolo di sicurezza dell'amministratore di sistema e visualizzerà un messaggio di errore se accedi con un account dell'amministratore di sistema.</span><span class="sxs-lookup"><span data-stu-id="cf2c3-119">The app doesn't currently support the System Administrator security role, and will display an error message if you sign in with a System Administrator account.</span></span> <span data-ttu-id="cf2c3-120">Per accedere con un altro account, nella scheda **Impostazioni**, seleziona il pulsante **Cambia account**, quindi accedi con un account utente che non dispone dei privilegi di amministratore di sistema.</span><span class="sxs-lookup"><span data-stu-id="cf2c3-120">To sign in with a different account, on the **Settings** tab, select the **Switch accounts** button, and then sign in with a user account that doesn’t have System Administrator privileges.</span></span>
 
## <a name="use-the-bot"></a><span data-ttu-id="cf2c3-121">Usa il bot</span><span class="sxs-lookup"><span data-stu-id="cf2c3-121">Use the bot</span></span>

<span data-ttu-id="cf2c3-122">Dopo l'installazione dell'app, viene visualizzato un messaggio di benvenuto che ti informa sui tipi di azioni che il bot può eseguire per tuo conto.</span><span class="sxs-lookup"><span data-stu-id="cf2c3-122">After the app installs, a welcome message appears, letting you know the types of actions the bot can take on your behalf.</span></span>

![Messaggio di benvenuto del bot dell'app per i permessi Human Resources in Teams](./media/hr-teams-leave-app-bot.png)
 
> [!NOTE]
> <span data-ttu-id="cf2c3-124">Quando interagisci per la prima volta con il bot, potresti dover eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="cf2c3-124">When first interacting with the bot, you might need to sign in.</span></span> <span data-ttu-id="cf2c3-125">Se non vedi una finestra di accesso, controlla le impostazioni del browser per consentire i popup.</span><span class="sxs-lookup"><span data-stu-id="cf2c3-125">If you don’t see a sign-in dialog box, check your browser settings to allow pop-ups.</span></span>

<span data-ttu-id="cf2c3-126">Puoi chiedere al bot di:</span><span class="sxs-lookup"><span data-stu-id="cf2c3-126">You can ask the bot to:</span></span>

- <span data-ttu-id="cf2c3-127">Mostra le informazioni sul saldo dei permessi per ciascun tipo di congedo a cui sei registrato.</span><span class="sxs-lookup"><span data-stu-id="cf2c3-127">Show time-off balance information for each leave type you're enrolled in.</span></span>

   ![Visualizzazione saldi dell'app per i permessi Human Resources in Teams](./media/hr-teams-leave-app-bot-balances.png)
 
- <span data-ttu-id="cf2c3-129">Mostra ulteriori dettagli su un tipo di congedo specifico.</span><span class="sxs-lookup"><span data-stu-id="cf2c3-129">Show additional details about a specific leave type.</span></span>

   ![Visualizzazione dettagli dell'app per i permessi Human Resources in Teams](./media/hr-teams-leave-app-bot-details.png)

- <span data-ttu-id="cf2c3-131">Inizia una richiesta di ferie per te.</span><span class="sxs-lookup"><span data-stu-id="cf2c3-131">Start a leave request for you.</span></span>

   ![Richiesta permesso dell'app per i permessi Human Resources in Teams](./media/hr-teams-leave-app-bot-request.png)
 
<span data-ttu-id="cf2c3-133">Dopo aver avviato una richiesta di congedo, è possibile modificare i giorni direttamente nella scheda.</span><span class="sxs-lookup"><span data-stu-id="cf2c3-133">After you start a leave request, you can adjust the days right within the card.</span></span>

![Modifica richiesta dell'app per i permessi Human Resources in Teams](./media/hr-teams-leave-app-bot-edit.png)
 
<span data-ttu-id="cf2c3-135">Al termine dell'immissione delle informazioni, selezionare **Invia** per inviarle per l'approvazione.</span><span class="sxs-lookup"><span data-stu-id="cf2c3-135">When you're done entering information, select **Submit** to submit it for approval.</span></span> <span data-ttu-id="cf2c3-136">Puoi anche selezionare **Salva come bozza** per tornare più tardi.</span><span class="sxs-lookup"><span data-stu-id="cf2c3-136">You can also select **Save as draft** to come back to it later.</span></span>

![Invio richiesta nell'app per i permessi Human Resources in Teams](./media/hr-teams-leave-app-bot-submit.png)

## <a name="manage-your-leave-in-teams"></a><span data-ttu-id="cf2c3-138">Gestire i congedi in Teams</span><span class="sxs-lookup"><span data-stu-id="cf2c3-138">Manage your leave in Teams</span></span>

<span data-ttu-id="cf2c3-139">La scheda **Tempo libero** ti consente di visualizzare:</span><span class="sxs-lookup"><span data-stu-id="cf2c3-139">The **Time off** tab allows you to view:</span></span>

- <span data-ttu-id="cf2c3-140">Informazioni sul saldo per ciascun tipo di congedo a cui sei registrato</span><span class="sxs-lookup"><span data-stu-id="cf2c3-140">Balance information for each leave type you're enrolled in</span></span>

- <span data-ttu-id="cf2c3-141">Prossime richieste di congedo</span><span class="sxs-lookup"><span data-stu-id="cf2c3-141">Upcoming leave requests</span></span>

- <span data-ttu-id="cf2c3-142">Richieste di tempo libero</span><span class="sxs-lookup"><span data-stu-id="cf2c3-142">Time-off requests</span></span>

- <span data-ttu-id="cf2c3-143">Bozza di richieste di congedo</span><span class="sxs-lookup"><span data-stu-id="cf2c3-143">Draft leave requests</span></span>

![Scheda Tempo libero dell'app per i permessi Human Resources in Teams](./media/hr-teams-leave-app-timeoff-tab.png)
 
### <a name="create-a-new-request"></a><span data-ttu-id="cf2c3-145">Crea una nuova richiesta</span><span class="sxs-lookup"><span data-stu-id="cf2c3-145">Create a new request</span></span>

1. <span data-ttu-id="cf2c3-146">Per creare una nuova richiesta di congedo, seleziona **Nuova richiesta**.</span><span class="sxs-lookup"><span data-stu-id="cf2c3-146">To create a new leave request, select **New request**.</span></span>

   ![Nuova richiesta dell'app per i permessi Human Resources in Teams](./media/hr-teams-leave-app-timeoff-tab-new.png)

2. <span data-ttu-id="cf2c3-148">Immetti il giorno o i giorni che desideri prendere come congedo, quindi seleziona **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="cf2c3-148">Enter the day or days you want to take off, and then select **Add**.</span></span>

   ![Aggiungi congedo app per i permessi Human Resources in Teams](./media/hr-teams-leave-app-timeoff-tab-add.png)

3. <span data-ttu-id="cf2c3-150">Se applicabile, inserisci un codice motivo.</span><span class="sxs-lookup"><span data-stu-id="cf2c3-150">If applicable, enter a reason code.</span></span> <span data-ttu-id="cf2c3-151">Inserisci anche eventuali commenti e aggiungi eventuali allegati.</span><span class="sxs-lookup"><span data-stu-id="cf2c3-151">Also enter any comments and add any attachments.</span></span>

4. <span data-ttu-id="cf2c3-152">Al termine dell'immissione delle informazioni, digita **Invia** per inviarle per l'approvazione.</span><span class="sxs-lookup"><span data-stu-id="cf2c3-152">When you're done entering information, type **Submit** to submit it for approval.</span></span> <span data-ttu-id="cf2c3-153">Puoi anche digitare **Salva come bozza** per tornare più tardi.</span><span class="sxs-lookup"><span data-stu-id="cf2c3-153">You can also type **Save as draft** to come back to it later.</span></span>

### <a name="manage-draft-requests"></a><span data-ttu-id="cf2c3-154">Gestisci bozze di richiesta</span><span class="sxs-lookup"><span data-stu-id="cf2c3-154">Manage draft requests</span></span>

1. <span data-ttu-id="cf2c3-155">Seleziona la scheda **Bozze**.</span><span class="sxs-lookup"><span data-stu-id="cf2c3-155">Select the **Drafts** tab.</span></span>

   ![Scheda Bozze dell'app per i permessi Human Resources in Teams](./media/hr-teams-leave-app-drafts-tab.png)

2. <span data-ttu-id="cf2c3-157">Seleziona la matita per modificare la richiesta o seleziona il cestino per eliminare la richiesta.</span><span class="sxs-lookup"><span data-stu-id="cf2c3-157">Select the pencil to edit the request, or select the trash can to delete the request.</span></span>

3. <span data-ttu-id="cf2c3-158">Apporta le modifiche necessarie.</span><span class="sxs-lookup"><span data-stu-id="cf2c3-158">Make any necessary changes.</span></span> <span data-ttu-id="cf2c3-159">Al termine dell'immissione delle informazioni, digita **Invia** per inviarle per l'approvazione.</span><span class="sxs-lookup"><span data-stu-id="cf2c3-159">When you're done entering information, type **Submit** to submit it for approval.</span></span> <span data-ttu-id="cf2c3-160">Puoi anche selezionare **Salva come bozza** per tornare più tardi.</span><span class="sxs-lookup"><span data-stu-id="cf2c3-160">You can also select **Save as draft** to come back to it later.</span></span>

   ![Modifica bozza dell'app per i permessi Human Resources in Teams](./media/hr-teams-leave-app-drafts-edit.png)
   
### <a name="teams-notifications"></a><span data-ttu-id="cf2c3-162">Notifiche di Teams</span><span class="sxs-lookup"><span data-stu-id="cf2c3-162">Teams notifications</span></span>

<span data-ttu-id="cf2c3-163">Quando l'utente o un lavoratore per cui l'utente è un approvatore invia una richiesta di congedo, viene ricevuta una notifica nell'app Human Resources in Teams.</span><span class="sxs-lookup"><span data-stu-id="cf2c3-163">When you or a worker you're an approver for submits a leave request, you'll receive a notification in the Human Resources app in Teams.</span></span> <span data-ttu-id="cf2c3-164">È possibile selezionare la notifica per visualizzarla.</span><span class="sxs-lookup"><span data-stu-id="cf2c3-164">You can select the notification to view it.</span></span> <span data-ttu-id="cf2c3-165">Le notifiche vengono visualizzate anche nell'area **Chat**.</span><span class="sxs-lookup"><span data-stu-id="cf2c3-165">Notifications also appear in the **Chat** area.</span></span>

<span data-ttu-id="cf2c3-166">Se l'utente è un approvatore, è possibile selezionare **Approva** o **Rifiuta** nella notifica.</span><span class="sxs-lookup"><span data-stu-id="cf2c3-166">If you're an approver, you can select **Approve** or **Deny** in the notification.</span></span> <span data-ttu-id="cf2c3-167">È anche possibile fornire un messaggio opzionale.</span><span class="sxs-lookup"><span data-stu-id="cf2c3-167">You can also provide an optional message.</span></span>

![Notifica della richiesta di congedo nell'app Human Resources in Teams](./media/hr-teams-leave-app-notification.png)

## <a name="view-your-teams-leave-calendar"></a><span data-ttu-id="cf2c3-169">Visualizzare un calendario di congedo del team</span><span class="sxs-lookup"><span data-stu-id="cf2c3-169">View your team's leave calendar</span></span>

<span data-ttu-id="cf2c3-170">Se l'utente è un responsabile con diretti subalterni può visualizzare i congedi approvati e in sospeso del team.</span><span class="sxs-lookup"><span data-stu-id="cf2c3-170">If you're a manager with direct reports, you can view your team's approved and pending time off.</span></span>

1. <span data-ttu-id="cf2c3-171">Nell'app Human Resources in Teams selezionare **Permesso**.</span><span class="sxs-lookup"><span data-stu-id="cf2c3-171">In the Human Resources app in Teams, select **Time off**.</span></span>

2. <span data-ttu-id="cf2c3-172">Selezionare **Calendario del team**.</span><span class="sxs-lookup"><span data-stu-id="cf2c3-172">Select **Team calendar**.</span></span>

   ![Visualizzare il calendario nell'app Human Resources in Teams](./media/hr-teams-leave-app-view-calendar.png)

<span data-ttu-id="cf2c3-174">Il calendario mostra i permessi approvati e in attesa di approvazione dei diretti subalterni.</span><span class="sxs-lookup"><span data-stu-id="cf2c3-174">The calendar displays your direct reports' approved and pending time off.</span></span>

![Calendario dei permessi nell'app Human Resources in Teams](./media/hr-teams-leave-app-calendar.png)

## <a name="privacy-notice"></a><span data-ttu-id="cf2c3-176">Informativa sulla privacy</span><span class="sxs-lookup"><span data-stu-id="cf2c3-176">Privacy notice</span></span>

### <a name="microsoft-language-understanding-intelligent-service-luis"></a><span data-ttu-id="cf2c3-177">Microsoft Language Understanding Intelligent Service (LUIS)</span><span class="sxs-lookup"><span data-stu-id="cf2c3-177">Microsoft Language Understanding Intelligent Service (LUIS)</span></span>

<span data-ttu-id="cf2c3-178">Con il bot Dynamics 365 Human Resources in Microsoft Teams, gli input di testo dell'utente vengono analizzati per comprendere la query/l'intento sottostanti.</span><span class="sxs-lookup"><span data-stu-id="cf2c3-178">With the Dynamics 365 Human Resources bot in Microsoft Teams, the user’s text inputs are analyzed for understanding the underlying query/intent.</span></span> <span data-ttu-id="cf2c3-179">L'input dell'utente, ad esempio "Cerca account Contoso", viene indirizzato a uno dei servizi cognitivi di Microsoft chiamato Language Understanding Intelligent Service (LUIS).</span><span class="sxs-lookup"><span data-stu-id="cf2c3-179">The user’s input such as “Search account Contoso” is routed to one of Microsoft’s Cognitive Service called Language Understanding Intelligent Service (LUIS).</span></span> <span data-ttu-id="cf2c3-180">Ulteriori informazioni su LUIS [qui](https://www.luis.ai/).</span><span class="sxs-lookup"><span data-stu-id="cf2c3-180">Read more about LUIS [here](https://www.luis.ai/).</span></span> <span data-ttu-id="cf2c3-181">Il servizio LUIS disambigua o comprende l'intento dell'input dell'utente (in questo caso, l'intento è quello di trovare informazioni) e l'entità di destinazione (in questo caso, l'entità desiderata è un account chiamato Contoso).</span><span class="sxs-lookup"><span data-stu-id="cf2c3-181">The LUIS service disambiguates or understands the intent of user input (in this case, the intent is to find information) and the target entity (in this case, the intended entity is an account named Contoso).</span></span> <span data-ttu-id="cf2c3-182">Queste informazioni vengono quindi trasmesse al  [Bot Framework di Azure](https://azure.microsoft.com/services/bot-service/) di Microsoft che interagisce con i dati da Dynamics 365 Human Resources e recupera le informazioni desiderate per la query dell'utente.</span><span class="sxs-lookup"><span data-stu-id="cf2c3-182">This information is then passed on to Microsoft’s [Azure bot framework](https://azure.microsoft.com/services/bot-service/), which interacts with data from Dynamics 365 Human Resources and retrieves the desired information for the user query.</span></span> 

<span data-ttu-id="cf2c3-183">Installando e consentendo l'accesso all'uso del bot, l'utente accetta di consentire al servizio LUIS e al framework del bot di Azure di elaborare l'intento dietro l'input, il che si traduce in un'esperienza utente conversazionale migliorata.</span><span class="sxs-lookup"><span data-stu-id="cf2c3-183">By installing and allowing access to use of the bot, you agree to allow the LUIS service and Azure bot framework to process the intent behind the input,  which results in an enhanced conversational user experience.</span></span> <span data-ttu-id="cf2c3-184">Il servizio LUIS e il framework dei bot di Azure possono presentare livelli di conformità diversi rispetto a Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="cf2c3-184">The LUIS service and Azure bot framework may have varying levels of compliance compared to Dynamics 365 Human Resources.</span></span> <span data-ttu-id="cf2c3-185">Mentre il servizio LUIS ha accesso solo alle query dell'utente e non è progettato per essere collegato ai dati o all'account Dynamics 365 Human Resources dell'utente, un utente del bot Dynamics 365 Human Resources potrebbe inserire volontariamente una query contenente dati del cliente, dati personali o altri dati e tale contenuto della query potrebbe essere inviato al servizio LUIS e al framework del bot di Azure.</span><span class="sxs-lookup"><span data-stu-id="cf2c3-185">While the LUIS service has access to only the user queries and is not designed to be connected to the user’s Dynamics 365 Human Resources data or account, a user of the Dynamics 365 Human Resources bot could voluntarily enter a query containing Customer Data, Personal Data, or other data and such query content could get sent to the LUIS service and the Azure bot framework.</span></span> 

<span data-ttu-id="cf2c3-186">Il contenuto delle query e dei messaggi dell'utente viene conservato nel sistema LUIS per un massimo di 30 giorni, viene crittografato a riposo e non viene utilizzato per migliorare la formazione o il servizio.</span><span class="sxs-lookup"><span data-stu-id="cf2c3-186">The content of user’s queries and messages is retained in LUIS system for a maximum of 30 days, is encrypted at rest, and is not used for training or service improvement.</span></span> <span data-ttu-id="cf2c3-187">Ulteriori informazioni sui servizi cognitivi [qui](https://azure.microsoft.com/services/cognitive-services/language-understanding-intelligent-service/).</span><span class="sxs-lookup"><span data-stu-id="cf2c3-187">Read more about Cognitive Services [here](https://azure.microsoft.com/services/cognitive-services/language-understanding-intelligent-service/).</span></span> 

<span data-ttu-id="cf2c3-188">Per gestire le impostazioni di amministrazione per le app in Microsoft Teams, vai all'[interfaccia di amministrazione di Microsoft Teams](https://admin.teams.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="cf2c3-188">To manage admin settings for apps in Microsoft Teams, go to the [Microsoft Teams admin center](https://admin.teams.microsoft.com/).</span></span>

### <a name="microsoft-azure-event-grid-and-microsoft-teams"></a><span data-ttu-id="cf2c3-189">Griglia di eventi Microsoft Azure e Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="cf2c3-189">Microsoft Azure Event Grid and Microsoft Teams</span></span>

<span data-ttu-id="cf2c3-190">Quando si utilizza la funzione di notifica per l'app Dynamics 365 Human Resources in Teams, alcuni dati dei clienti passeranno al di fuori dell'area geografica in cui è distribuito il servizio Human Resources del tenant.</span><span class="sxs-lookup"><span data-stu-id="cf2c3-190">When using the notifications feature for the Dynamics 365 Human Resources app in Teams, certain customer data will flow outside of the geographic region where your tenant’s Human Resources service is deployed.</span></span> <span data-ttu-id="cf2c3-191">Dynamics 365 Human Resources trasmette la richiesta di congedo del dipendente e i dettagli dell'attività del flusso di lavoro alla Griglia di eventi di Microsoft Azure e Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="cf2c3-191">Dynamics 365 Human Resources transmits the employee’s leave request and workflow task details to Microsoft Azure Event Grid and Microsoft Teams.</span></span> <span data-ttu-id="cf2c3-192">Questi dati possono essere archiviati per un massimo di 24 ore ed elaborati negli Stati Uniti, vengono crittografati i dati in transito e inattivi e non vengono utilizzati da Microsoft o dai collaboratori di elaborazione per la formazione o il miglioramento del servizio.</span><span class="sxs-lookup"><span data-stu-id="cf2c3-192">This data may be stored for up to 24 hours and processed in the United States, is encrypted in transit and at rest, and is not used by Microsoft or its subprocessors for training or service improvements.</span></span>

## <a name="see-also"></a><span data-ttu-id="cf2c3-193">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cf2c3-193">See also</span></span>

[<span data-ttu-id="cf2c3-194">Scaricare e installare Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="cf2c3-194">Download and install Microsoft Teams</span></span>](https://support.office.com/article/download-and-install-microsoft-teams-422bf3aa-9ae8-46f1-83a2-e65720e1a34d)</br>
[<span data-ttu-id="cf2c3-195">Centro assistenza di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="cf2c3-195">Microsoft Teams help center</span></span>](https://support.office.com/teams)</br>
[<span data-ttu-id="cf2c3-196">App Human Resources in Teams</span><span class="sxs-lookup"><span data-stu-id="cf2c3-196">Human Resources app in Teams</span></span>](hr-admin-teams-leave-app.md)
