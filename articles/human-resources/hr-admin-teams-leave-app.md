---
title: App Human Resources in Teams
description: Questo argomento introduce l'app Microsoft Dynamics 365 Human Resources in Microsoft Teams.
author: andreabichsel
ms.date: 02/23/2021
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 9cc15c33c7efdd515121db67331477baa4bdacaf
ms.sourcegitcommit: e3f11fc9a9dae416a490437678bb482a0094f9a9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/27/2021
ms.locfileid: "5953390"
---
# <a name="human-resources-app-in-teams"></a><span data-ttu-id="054ca-103">App Human Resources in Teams</span><span class="sxs-lookup"><span data-stu-id="054ca-103">Human Resources app in Teams</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="054ca-104">L'app Microsoft Dynamics 365 Human Resources in Microsoft Teams consente ai dipendenti di richiedere rapidamente permessi e di visualizzare le informazioni sul loro saldo permessi in Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="054ca-104">The Microsoft Dynamics 365 Human Resources app in Microsoft Teams lets employees quickly request time off and view their time-off balance information in Microsoft Teams.</span></span> <span data-ttu-id="054ca-105">I dipendenti possono interagire con un bot per richiedere informazioni.</span><span class="sxs-lookup"><span data-stu-id="054ca-105">Employees can interact with a bot to request information.</span></span> <span data-ttu-id="054ca-106">La scheda **Tempo libero** fornisce informazioni più dettagliate.</span><span class="sxs-lookup"><span data-stu-id="054ca-106">The **Time off** tab provides more detailed information.</span></span> <span data-ttu-id="054ca-107">Inoltre, possono inviare alle persone informazioni sull'imminente indisponibilità in team e chat al di fuori dell'app Human Resources.</span><span class="sxs-lookup"><span data-stu-id="054ca-107">In addition, they can send people information about upcoming time off in teams and chats outside the Human Resources app.</span></span>

![Bot dell'app per i permessi Human Resources in Teams](./media/hr-teams-leave-app-bot.png)

![Scheda Tempo libero dell'app per i permessi Human Resources in Teams](./media/hr-teams-leave-app-timeoff-tab.png)

![Scheda richiesta di congedo per Human Resources](./media/hr-teams-leave-app-chat-card.png)

## <a name="install-and-setup"></a><span data-ttu-id="054ca-111">Installa e configura</span><span class="sxs-lookup"><span data-stu-id="054ca-111">Install and setup</span></span>

<span data-ttu-id="054ca-112">Puoi trovare l'app Dynamics 365 Human Resources nello store di Teams.</span><span class="sxs-lookup"><span data-stu-id="054ca-112">You can find the Dynamics 365 Human Resources app in the Teams store.</span></span> <span data-ttu-id="054ca-113">Per informazioni sull'installazione dell'app Teams, vedi [Gestisci richieste di permessi in Teams](hr-teams-leave-app.md).</span><span class="sxs-lookup"><span data-stu-id="054ca-113">For information about installing the Teams app, see [Manage leave requests in Teams](hr-teams-leave-app.md).</span></span>

<span data-ttu-id="054ca-114">Per informazioni sulla gestione delle autorizzazioni delle app in Teams, vedi [Gestire i criteri delle autorizzazioni delle app in Microsoft Teams](/MicrosoftTeams/teams-app-permission-policies).</span><span class="sxs-lookup"><span data-stu-id="054ca-114">For information about managing app permissions in Teams, see [Manage app permission policies in Microsoft Teams](/MicrosoftTeams/teams-app-permission-policies).</span></span>

<span data-ttu-id="054ca-115">Se desideri che i tuoi utenti visualizzino il calendario Congedo e assenza nell'app, devi abilitare il **calendario Congedo e assenze di Teams** in Gestione funzionalità.</span><span class="sxs-lookup"><span data-stu-id="054ca-115">If you want your users to view the Leave and absence calendar in the app, you'll need to enable the **Leave and absence calendar in Teams** in Feature management.</span></span> <span data-ttu-id="054ca-116">Per ulteriori informazioni sull'abilitazione delle funzionalità, vedi [Gestire le funzionalità](hr-admin-manage-features.md).</span><span class="sxs-lookup"><span data-stu-id="054ca-116">For more information about enabling features, see [Manage features](hr-admin-manage-features.md).</span></span>

## <a name="enable-notifications-for-the-human-resources-app-in-teams"></a><span data-ttu-id="054ca-117">Abilitare le notifiche per l'app Human Resources in Teams</span><span class="sxs-lookup"><span data-stu-id="054ca-117">Enable notifications for the Human Resources app in Teams</span></span>

<span data-ttu-id="054ca-118">Se si desidera che gli utenti ricevano le notifiche delle richieste di congedo nell'app Teams, è necessario abilitare le notifiche in Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="054ca-118">If you want users to receive leave request notifications in the Teams app, you must enable notifications in Dynamics 365 Human Resources.</span></span>

>[!NOTE]
><span data-ttu-id="054ca-119">Solo gli utenti che hanno effettuato l'accesso a Teams e usano l'app Dynamics 365 Human Resources in Teams riceveranno le notifiche.</span><span class="sxs-lookup"><span data-stu-id="054ca-119">Only users who are signed into Teams and using the Dynamics 365 Human Resources Teams app will receive notifications.</span></span>

1. <span data-ttu-id="054ca-120">In Risorse umane, selezionare **Amministrazione sistema**.</span><span class="sxs-lookup"><span data-stu-id="054ca-120">In Human Resources, select **System administration**.</span></span>

2. <span data-ttu-id="054ca-121">Selezionare **Collegamenti**.</span><span class="sxs-lookup"><span data-stu-id="054ca-121">Select **Links**.</span></span>

3. <span data-ttu-id="054ca-122">Sotto **Impostazione**, selezionare **Parametri di sistema**.</span><span class="sxs-lookup"><span data-stu-id="054ca-122">Under **Setup**, select **System parameters**.</span></span>

4. <span data-ttu-id="054ca-123">Nella scheda **Generale** impostare **Abilita notifiche per l'app Teams** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="054ca-123">On the **General** tab, set **Enable notifications for Teams app** to **Yes**.</span></span>

   ![Abilitare le notifiche dell'app Teams nei parametri di sistema](./media/hr-admin-teams-leave-app-enable-notifications.png)

5. <span data-ttu-id="054ca-125">Per attivare le notifiche di Teams per tutti gli utenti, selezionare **Sì** alla richiesta.</span><span class="sxs-lookup"><span data-stu-id="054ca-125">To turn on Teams notifications for all users, select **Yes** at the prompt.</span></span>

   ![Abilitare le notifiche di Teams per tutti gli utenti](./media/hr-admin-teams-leave-app-notifications-all-users.png)

### <a name="turn-teams-notifications-on-or-off-for-individual-users"></a><span data-ttu-id="054ca-127">Attivare o disattivare le notifiche di Teams per i singoli utenti</span><span class="sxs-lookup"><span data-stu-id="054ca-127">Turn Teams notifications on or off for individual users</span></span>

<span data-ttu-id="054ca-128">Dopo aver abilitato le notifiche per l'app Dynamics 365 Human Resources in Teams, è possibile attivare o disattivare le notifiche per i singoli utenti.</span><span class="sxs-lookup"><span data-stu-id="054ca-128">After you've enabled notifications for the Dynamics 365 Human Resources Teams app, you can turn notifications on or off for individual users.</span></span>

1. <span data-ttu-id="054ca-129">In Risorse umane, selezionare **Amministrazione sistema**.</span><span class="sxs-lookup"><span data-stu-id="054ca-129">In Human Resources, select **System administration**.</span></span>

2. <span data-ttu-id="054ca-130">Selezionare **Collegamenti**.</span><span class="sxs-lookup"><span data-stu-id="054ca-130">Select **Links**.</span></span>

3. <span data-ttu-id="054ca-131">Sotto **Utenti**, selezionare **Opzioni utente**.</span><span class="sxs-lookup"><span data-stu-id="054ca-131">Under **Users**, select **User options**.</span></span>

4. <span data-ttu-id="054ca-132">Selezionare la scheda **Flusso di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="054ca-132">Select the **Workflow** tab.</span></span>

5. <span data-ttu-id="054ca-133">Impostare **Abilita le notifiche per l'app Teams** su **Sì** per abilitare le notifiche per l'utente o su **No** per disabilitare le notifiche per l'utente.</span><span class="sxs-lookup"><span data-stu-id="054ca-133">Set **Enable notifications for Teams app** to **Yes** to enable notifications for the user or **No** to disable notifications for the user.</span></span>

   ![Abilitare le notifiche dell'app Teams nella scheda Flusso di lavoro delle opzioni utente](./media/hr-admin-teams-leave-app-notifications.png)

6. <span data-ttu-id="054ca-135">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="054ca-135">Select **Save**.</span></span>

## <a name="supported-languages"></a><span data-ttu-id="054ca-136">Lingue supportate</span><span class="sxs-lookup"><span data-stu-id="054ca-136">Supported languages</span></span>

<span data-ttu-id="054ca-137">L'app Dynamics 365 Human Resources in Teams supporta le lingue seguenti:</span><span class="sxs-lookup"><span data-stu-id="054ca-137">The Dynamics 365 Human Resources app in Teams supports the following languages:</span></span>

| <span data-ttu-id="054ca-138">ID locale</span><span class="sxs-lookup"><span data-stu-id="054ca-138">Locale ID</span></span> | <span data-ttu-id="054ca-139">Lingua</span><span class="sxs-lookup"><span data-stu-id="054ca-139">Language</span></span> |
| --- | --- |
| <span data-ttu-id="054ca-140">de-DE</span><span class="sxs-lookup"><span data-stu-id="054ca-140">de-DE</span></span> | <span data-ttu-id="054ca-141">Tedesco (Germania)</span><span class="sxs-lookup"><span data-stu-id="054ca-141">German (Germany)</span></span> |
| <span data-ttu-id="054ca-142">es-ES</span><span class="sxs-lookup"><span data-stu-id="054ca-142">es-ES</span></span> | <span data-ttu-id="054ca-143">Spagnolo (Spagna)</span><span class="sxs-lookup"><span data-stu-id="054ca-143">Spanish (Spain)</span></span> |
| <span data-ttu-id="054ca-144">es-MX</span><span class="sxs-lookup"><span data-stu-id="054ca-144">es-MX</span></span> | <span data-ttu-id="054ca-145">Spagnolo (Messico)</span><span class="sxs-lookup"><span data-stu-id="054ca-145">Spanish (Mexico)</span></span> |
| <span data-ttu-id="054ca-146">fr-CA</span><span class="sxs-lookup"><span data-stu-id="054ca-146">fr-CA</span></span> | <span data-ttu-id="054ca-147">Francese (Canada)</span><span class="sxs-lookup"><span data-stu-id="054ca-147">French (Canada)</span></span> |
| <span data-ttu-id="054ca-148">fr-FR</span><span class="sxs-lookup"><span data-stu-id="054ca-148">fr-FR</span></span> | <span data-ttu-id="054ca-149">Francese (Francia)</span><span class="sxs-lookup"><span data-stu-id="054ca-149">French (France)</span></span> |
| <span data-ttu-id="054ca-150">it-IT</span><span class="sxs-lookup"><span data-stu-id="054ca-150">it-IT</span></span> | <span data-ttu-id="054ca-151">Italiano (Italia)</span><span class="sxs-lookup"><span data-stu-id="054ca-151">Italian (Italy)</span></span> |
| <span data-ttu-id="054ca-152">nl-NL</span><span class="sxs-lookup"><span data-stu-id="054ca-152">nl-NL</span></span> | <span data-ttu-id="054ca-153">Olandese (Paesi Bassi)</span><span class="sxs-lookup"><span data-stu-id="054ca-153">Dutch (Netherlands)</span></span> |
| <span data-ttu-id="054ca-154">pt-BR</span><span class="sxs-lookup"><span data-stu-id="054ca-154">pt-BR</span></span> | <span data-ttu-id="054ca-155">Portoghese (Brasile)</span><span class="sxs-lookup"><span data-stu-id="054ca-155">Portuguese (Brazil)</span></span> |
| <span data-ttu-id="054ca-156">tr-TR</span><span class="sxs-lookup"><span data-stu-id="054ca-156">tr-TR</span></span> | <span data-ttu-id="054ca-157">Turco (Turchia)</span><span class="sxs-lookup"><span data-stu-id="054ca-157">Turkish (Turkey)</span></span> |
| <span data-ttu-id="054ca-158">zh-CN</span><span class="sxs-lookup"><span data-stu-id="054ca-158">zh-CN</span></span> | <span data-ttu-id="054ca-159">Cinese (semplificato)</span><span class="sxs-lookup"><span data-stu-id="054ca-159">Chinese (Simplified)</span></span> |

## <a name="notes"></a><span data-ttu-id="054ca-160">Note</span><span class="sxs-lookup"><span data-stu-id="054ca-160">Notes</span></span>

<span data-ttu-id="054ca-161">I seguenti elementi di lavoro sono previsti per le versioni future:</span><span class="sxs-lookup"><span data-stu-id="054ca-161">The following work items are slated for future releases:</span></span>

| <span data-ttu-id="054ca-162">Elemento di lavoro</span><span class="sxs-lookup"><span data-stu-id="054ca-162">Work item</span></span> | <span data-ttu-id="054ca-163">Stato</span><span class="sxs-lookup"><span data-stu-id="054ca-163">Status</span></span> |
| --- | --- |
| <span data-ttu-id="054ca-164">Il saldo non è corretto quando richiedi permessi per una data futura.</span><span class="sxs-lookup"><span data-stu-id="054ca-164">The balance is incorrect when submitting time off for a future date.</span></span> | <span data-ttu-id="054ca-165">Le previsioni non sono ancora disponibili.</span><span class="sxs-lookup"><span data-stu-id="054ca-165">Forecasting isn't yet available.</span></span> <span data-ttu-id="054ca-166">Il saldo visualizza la data corrente.</span><span class="sxs-lookup"><span data-stu-id="054ca-166">The balance displays for the current date.</span></span> |
| <span data-ttu-id="054ca-167">Impossibile annullare una richiesta **In revisione**.</span><span class="sxs-lookup"><span data-stu-id="054ca-167">Unable to cancel an **In review** request.</span></span> | <span data-ttu-id="054ca-168">Questa funzionalità non è attualmente supportata e verrà aggiunta in una versione futura.</span><span class="sxs-lookup"><span data-stu-id="054ca-168">This functionality isn't currently supported and will be added in a future release.</span></span> |
| <span data-ttu-id="054ca-169">Le informazioni sul saldo sono calcolate a partire da oggi.</span><span class="sxs-lookup"><span data-stu-id="054ca-169">Balance information is calculated as of today.</span></span> | <span data-ttu-id="054ca-170">Il sistema al momento non visualizza i saldi al momento del periodo di competenza, anche se configurato nei parametri congedo e assenza.</span><span class="sxs-lookup"><span data-stu-id="054ca-170">The system currently doesn't display balances as of the accrual period, even if it's configured in Leave and absence parameters.</span></span> |

## <a name="troubleshooting"></a><span data-ttu-id="054ca-171">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="054ca-171">Troubleshooting</span></span>

<span data-ttu-id="054ca-172">Se un utente ha problemi ad accedere o utilizzare l'app Human Resources in Teams, prova a seguire queste istruzioni per la risoluzione dei problemi.</span><span class="sxs-lookup"><span data-stu-id="054ca-172">If a user is having trouble signing into or using the Human Resources Teams app, try following these troubleshooting instructions.</span></span> <span data-ttu-id="054ca-173">Se i problemi persistono dopo la risoluzione dei problemi, contatta il supporto.</span><span class="sxs-lookup"><span data-stu-id="054ca-173">If you're still having problems after troubleshooting, contact Support.</span></span> <span data-ttu-id="054ca-174">Per ulteriori informazioni, vedere [Ottenere supporto](../fin-ops-core/dev-itpro/lifecycle-services/lcs-support.md).</span><span class="sxs-lookup"><span data-stu-id="054ca-174">For more information, see [Get support](../fin-ops-core/dev-itpro/lifecycle-services/lcs-support.md).</span></span>

### <a name="cant-sign-into-the-human-resources-app-in-teams"></a><span data-ttu-id="054ca-175">Non è possibile accedere all'app Human Resources in Teams</span><span class="sxs-lookup"><span data-stu-id="054ca-175">Can't sign into the Human Resources app in Teams</span></span>

<span data-ttu-id="054ca-176">Se un utente ti contatta perché non può accedere all'app, verifica che disponga di un record dipendente associato in Human Resources.</span><span class="sxs-lookup"><span data-stu-id="054ca-176">If a user contacts you because they can't sign into the app, verify that they have an associated employee record in Human Resources.</span></span>

### <a name="error-when-approving-leave-requests-in-the-human-resources-app-in-teams"></a><span data-ttu-id="054ca-177">Errore durante l'approvazione delle richieste di congedo nell'app Human Resources in Teams</span><span class="sxs-lookup"><span data-stu-id="054ca-177">Error when approving leave requests in the Human Resources app in Teams</span></span>

<span data-ttu-id="054ca-178">Se un utente vede un errore quando tenta di approvare le richieste di congedo nell'app Teams, esegui i seguenti passaggi di risoluzione dei problemi:</span><span class="sxs-lookup"><span data-stu-id="054ca-178">If a user receives an error while trying to approve,  leave requests in the Teams app, try the following troubleshooting steps:</span></span>

1. <span data-ttu-id="054ca-179">Verifica che il suo account Teams sia quello che utilizza per accedere a Human Resources.</span><span class="sxs-lookup"><span data-stu-id="054ca-179">Verify that their Teams account is the same one they use for accessing Human Resources.</span></span>

2. <span data-ttu-id="054ca-180">Verifica che sia un responsabile approvazione valido per la richiesta controllando le impostazioni del flusso di lavoro per l'approvazione del congedo.</span><span class="sxs-lookup"><span data-stu-id="054ca-180">Verify that they're a valid approver for the request by checking the workflow settings for leave approval.</span></span> <span data-ttu-id="054ca-181">Per ulteriori informazioni sui flussi di lavoro delle richieste di congedo, vedi [Creare un flusso di lavoro di richieste di congedo](hr-leave-and-absence-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="054ca-181">For more information about leave request workflows, see [Create a leave request workflow](hr-leave-and-absence-workflow.md).</span></span>

### <a name="leave-approvers-dont-receive-teams-chat-messages-to-approve-leave-requests"></a><span data-ttu-id="054ca-182">I responsabili dell'approvazione congedo non ricevono i messaggi di chat di Teams per approvare le richieste di congedo</span><span class="sxs-lookup"><span data-stu-id="054ca-182">Leave approvers don't receive Teams chat messages to approve leave requests</span></span>

1. <span data-ttu-id="054ca-183">Assicurati che le notifiche siano abilitate per l'ambiente e per l'utente.</span><span class="sxs-lookup"><span data-stu-id="054ca-183">Ensure notifications are enabled for the environment and the user.</span></span> <span data-ttu-id="054ca-184">Per ulteriori informazioni, vedere [Abilitare le notifiche per l'app Human Resources in Teams](hr-admin-teams-leave-app.md#enable-notifications-for-the-human-resources-app-in-teams) e [Attivare o disattivare le notifiche di Teams per i singoli utenti](hr-admin-teams-leave-app.md#turn-teams-notifications-on-or-off-for-individual-users).</span><span class="sxs-lookup"><span data-stu-id="054ca-184">For more information, see [Enable notifications for the Human Resources app in Teams](hr-admin-teams-leave-app.md#enable-notifications-for-the-human-resources-app-in-teams) and [Turn Teams notifications on or off for individual users](hr-admin-teams-leave-app.md#turn-teams-notifications-on-or-off-for-individual-users).</span></span>

2. <span data-ttu-id="054ca-185">Assicurati che gli utenti abbiano effettuato l'accesso alla scheda **Chat** con le stesse credenziali che utilizzano per approvare le richieste di congedo.</span><span class="sxs-lookup"><span data-stu-id="054ca-185">Ensure users are signed into the **Chats** tab with the same credentials they use for approving leave requests.</span></span> <span data-ttu-id="054ca-186">Utilizzare i messaggi "disconnettersi" e quindi "accedere" per accedere con le credenziali corrette.</span><span class="sxs-lookup"><span data-stu-id="054ca-186">Use the messages "sign out" and then "sign in" to sign in with the correct credentials.</span></span>

3. <span data-ttu-id="054ca-187">Se il problema persiste, controllare lo stato del processo batch di sistema Eventi aziendali come amministratore di sistema.</span><span class="sxs-lookup"><span data-stu-id="054ca-187">If the issue persists, check the status of the Business Events system batch job as a system administrator.</span></span> <span data-ttu-id="054ca-188">Se è in una fase di attesa o di esecuzione, ricontrolla tra qualche minuto.</span><span class="sxs-lookup"><span data-stu-id="054ca-188">If it's in a waiting or executing stage, check back in a few minutes.</span></span> <span data-ttu-id="054ca-189">Se lo stato rimane invariato, registra un ticket di supporto in modo che il nostro team possa aiutare a risolvere il problema.</span><span class="sxs-lookup"><span data-stu-id="054ca-189">If the status remains unchanged, log a support ticket so our team can help resolve the issue.</span></span>

## <a name="privacy-notice"></a><span data-ttu-id="054ca-190">Informativa sulla privacy</span><span class="sxs-lookup"><span data-stu-id="054ca-190">Privacy notice</span></span>

### <a name="microsoft-language-understanding-intelligent-service-luis"></a><span data-ttu-id="054ca-191">Microsoft Language Understanding Intelligent Service (LUIS)</span><span class="sxs-lookup"><span data-stu-id="054ca-191">Microsoft Language Understanding Intelligent Service (LUIS)</span></span>

<span data-ttu-id="054ca-192">Con il bot Dynamics 365 Human Resources in Microsoft Teams, gli input di testo dell'utente vengono analizzati per comprendere la query/l'intento sottostanti.</span><span class="sxs-lookup"><span data-stu-id="054ca-192">With the Dynamics 365 Human Resources bot in Microsoft Teams, the user’s text inputs are analyzed for understanding the underlying query/intent.</span></span> <span data-ttu-id="054ca-193">L'input dell'utente, ad esempio "Cerca account Contoso", viene indirizzato a uno dei servizi cognitivi di Microsoft chiamato Language Understanding Intelligent Service (LUIS).</span><span class="sxs-lookup"><span data-stu-id="054ca-193">The user’s input such as “Search account Contoso” is routed to one of Microsoft’s Cognitive Service called Language Understanding Intelligent Service (LUIS).</span></span> <span data-ttu-id="054ca-194">Ulteriori informazioni su LUIS [qui](https://www.luis.ai/).</span><span class="sxs-lookup"><span data-stu-id="054ca-194">Read more about LUIS [here](https://www.luis.ai/).</span></span> <span data-ttu-id="054ca-195">Il servizio LUIS disambigua o comprende l'intento dell'input dell'utente (in questo caso, l'intento è quello di trovare informazioni) e l'entità di destinazione (in questo caso, l'entità desiderata è un account chiamato Contoso).</span><span class="sxs-lookup"><span data-stu-id="054ca-195">The LUIS service disambiguates or understands the intent of user input (in this case, the intent is to find information) and the target entity (in this case, the intended entity is an account named Contoso).</span></span> <span data-ttu-id="054ca-196">Queste informazioni vengono quindi trasmesse al  [Bot Framework di Azure](https://azure.microsoft.com/services/bot-service/) di Microsoft che interagisce con i dati da Dynamics 365 Human Resources e recupera le informazioni desiderate per la query dell'utente.</span><span class="sxs-lookup"><span data-stu-id="054ca-196">This information is then passed on to Microsoft’s [Azure bot framework](https://azure.microsoft.com/services/bot-service/), which interacts with data from Dynamics 365 Human Resources and retrieves the desired information for the user query.</span></span>

<span data-ttu-id="054ca-197">Installando e consentendo l'accesso all'uso del bot, l'utente accetta di consentire al servizio LUIS e al framework del bot di Azure di elaborare l'intento dietro l'input, il che si traduce in un'esperienza utente conversazionale migliorata.</span><span class="sxs-lookup"><span data-stu-id="054ca-197">By installing and allowing access to use of the bot, you agree to allow the LUIS service and Azure bot framework to process the intent behind the input,  which results in an enhanced conversational user experience.</span></span> <span data-ttu-id="054ca-198">Il servizio LUIS e il framework dei bot di Azure possono presentare livelli di conformità diversi rispetto a Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="054ca-198">The LUIS service and Azure bot framework may have varying levels of compliance compared to Dynamics 365 Human Resources.</span></span> <span data-ttu-id="054ca-199">Mentre il servizio LUIS ha accesso solo alle query dell'utente e non è progettato per essere collegato ai dati o all'account Dynamics 365 Human Resources dell'utente, un utente del bot Dynamics 365 Human Resources potrebbe inserire volontariamente una query contenente dati del cliente, dati personali o altri dati e tale contenuto della query potrebbe essere inviato al servizio LUIS e al framework del bot di Azure.</span><span class="sxs-lookup"><span data-stu-id="054ca-199">While the LUIS service has access to only the user queries and is not designed to be connected to the user’s Dynamics 365 Human Resources data or account, a user of the Dynamics 365 Human Resources bot could voluntarily enter a query containing Customer Data, Personal Data, or other data and such query content could get sent to the LUIS service and the Azure bot framework.</span></span> 

<span data-ttu-id="054ca-200">Il contenuto delle query e dei messaggi dell'utente viene conservato nel sistema LUIS per un massimo di 30 giorni, viene crittografato a riposo e non viene utilizzato per migliorare la formazione o il servizio.</span><span class="sxs-lookup"><span data-stu-id="054ca-200">The content of user’s queries and messages is retained in LUIS system for a maximum of 30 days, is encrypted at rest, and is not used for training or service improvement.</span></span> <span data-ttu-id="054ca-201">Ulteriori informazioni sui servizi cognitivi [qui](https://azure.microsoft.com/services/cognitive-services/language-understanding-intelligent-service/).</span><span class="sxs-lookup"><span data-stu-id="054ca-201">Read more about Cognitive Services [here](https://azure.microsoft.com/services/cognitive-services/language-understanding-intelligent-service/).</span></span> 

<span data-ttu-id="054ca-202">Per gestire le impostazioni di amministrazione per le app in Microsoft Teams, vai all'[interfaccia di amministrazione di Microsoft Teams](https://admin.teams.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="054ca-202">To manage admin settings for apps in Microsoft Teams, go to the [Microsoft Teams admin center](https://admin.teams.microsoft.com/).</span></span>

### <a name="microsoft-teams-azure-event-grid-and-azure-cosmos-db"></a><span data-ttu-id="054ca-203">Microsoft Teams, Griglia di eventi di Azure e Azure Cosmos DB</span><span class="sxs-lookup"><span data-stu-id="054ca-203">Microsoft Teams, Azure Event Grid, and Azure Cosmos DB</span></span>

<span data-ttu-id="054ca-204">Quando si utilizza l'app Dynamics 365 Human Resources in Microsoft Teams, alcuni dati dei clienti passeranno al di fuori dell'area geografica in cui è distribuito il servizio Human Resources del tenant.</span><span class="sxs-lookup"><span data-stu-id="054ca-204">When using the Dynamics 365 Human Resources app in Microsoft Teams, certain customer data may flow outside of the geographic region where your tenant’s Human Resources service is deployed.</span></span>

<span data-ttu-id="054ca-205">Dynamics 365 Human Resources trasmette la richiesta di congedo del dipendente e i dettagli dell'attività del flusso di lavoro alla Griglia di eventi di Microsoft Azure e Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="054ca-205">Dynamics 365 Human Resources transmits the employee’s leave request and workflow task details to Microsoft Azure Event Grid and Microsoft Teams.</span></span> <span data-ttu-id="054ca-206">Questi dati possono essere archiviati in Griglia di eventi di Microsoft Azure per un massimo di 24 ore e verranno elaborati negli Stati Uniti, vengono crittografati i dati in transito e inattivi e non vengono utilizzati da Microsoft o dai collaboratori di elaborazione per la formazione o il miglioramento del servizio.</span><span class="sxs-lookup"><span data-stu-id="054ca-206">This data may be stored in Microsoft Azure Event Grid for up to 24 hours and will be processed in the United States, is encrypted in transit and at rest, and is not used by Microsoft or its subprocessors for training or service improvements.</span></span> <span data-ttu-id="054ca-207">Per capire dove sono archiviati i dati in Teams, vedi: [Posizione dei dati in Microsoft Teams](/microsoftteams/location-of-data-in-teams?preserve-view=true&view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="054ca-207">To understand where your data is stored in Teams, please see: [Location of data in Microsoft Teams](/microsoftteams/location-of-data-in-teams?preserve-view=true&view=o365-worldwide).</span></span>

<span data-ttu-id="054ca-208">Durante la conversazione con il chat bot nell'app Human Resources, il contenuto della conversazione può essere archiviato in Azure Cosmos DB e trasmesso a Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="054ca-208">While conversing with the chat bot in the Human Resources app, the conversation content may be stored in Azure Cosmos DB and transmitted to Microsoft Teams.</span></span> <span data-ttu-id="054ca-209">Questi dati possono essere archiviati in Azure Cosmos DB per un massimo di 24 ore e possono essere elaborati al di fuori dell'area geografica in cui è distribuito il servizio Human Resources del tenant, vengono crittografati i dati in transito e inattivi e non vengono utilizzati da Microsoft o dai collaboratori di elaborazione per la formazione o il miglioramento del servizio.</span><span class="sxs-lookup"><span data-stu-id="054ca-209">This data may be stored in Azure Cosmos DB for up to 24 hours and may be processed outside of the geographic region where your tenant's Human Resources service is deployed, is encrypted in transit and at rest, and is not used by Microsoft or its subprocessors for training or service improvements.</span></span> <span data-ttu-id="054ca-210">Per capire dove sono archiviati i dati in Teams, vedi: [Posizione dei dati in Microsoft Teams](/microsoftteams/location-of-data-in-teams?preserve-view=true&view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="054ca-210">To understand where your data is stored in Teams, please see: [Location of data in Microsoft Teams](/microsoftteams/location-of-data-in-teams?preserve-view=true&view=o365-worldwide).</span></span>
 
<span data-ttu-id="054ca-211">Per limitare l'accesso all'app Human Resources in Microsoft Teams per la tua organizzazione o per gli utenti all'interno della tua organizzazione, vedi [Gestisci i criteri di autorizzazione delle app in Microsoft Teams](/MicrosoftTeams/teams-app-permission-policies).</span><span class="sxs-lookup"><span data-stu-id="054ca-211">To restrict access to the Human Resources app in Microsoft Teams for your organization or users within your organization, see [Manage app permission policies in Microsoft Teams](/MicrosoftTeams/teams-app-permission-policies).</span></span>

## <a name="see-also"></a><span data-ttu-id="054ca-212">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="054ca-212">See also</span></span> 

[<span data-ttu-id="054ca-213">Scaricare e installare Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="054ca-213">Download and install Microsoft Teams</span></span>](https://support.office.com/article/download-and-install-microsoft-teams-422bf3aa-9ae8-46f1-83a2-e65720e1a34d)</br>
[<span data-ttu-id="054ca-214">Centro assistenza di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="054ca-214">Microsoft Teams help center</span></span>](https://support.office.com/teams)</br>
[<span data-ttu-id="054ca-215">Gestire le richieste di congedo in Teams</span><span class="sxs-lookup"><span data-stu-id="054ca-215">Manage leave requests in Teams</span></span>](hr-teams-leave-app.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]