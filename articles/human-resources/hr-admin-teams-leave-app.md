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
ms.openlocfilehash: a022f8297066793080d254baa01410884a3fafd9
ms.sourcegitcommit: 55b729361ea852e38531c51972c6730e3d9c2b45
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/08/2020
ms.locfileid: "3776310"
---
# <a name="human-resources-app-in-teams"></a><span data-ttu-id="caf51-103">App Human Resources in Teams</span><span class="sxs-lookup"><span data-stu-id="caf51-103">Human Resources app in Teams</span></span>

[!include [banner](includes/preview-feature.md)]

<span data-ttu-id="caf51-104">L'app Microsoft Dynamics 365 Human Resources in Microsoft Teams consente ai dipendenti di richiedere rapidamente permessi e di visualizzare le informazioni sul loro saldo permessi in Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="caf51-104">The Microsoft Dynamics 365 Human Resources app in Microsoft Teams lets employees quickly request time off and view their time-off balance information in Microsoft Teams.</span></span> <span data-ttu-id="caf51-105">I dipendenti possono interagire con un bot per richiedere informazioni.</span><span class="sxs-lookup"><span data-stu-id="caf51-105">Employees can interact with a bot to request information.</span></span> <span data-ttu-id="caf51-106">La scheda **Tempo libero** fornisce informazioni più dettagliate.</span><span class="sxs-lookup"><span data-stu-id="caf51-106">The **Time off** tab provides more detailed information.</span></span>

![Bot dell'app per i permessi Human Resources in Teams](./media/hr-admin-teams-leave-app-bot.png)

![Scheda Tempo libero dell'app per i permessi Human Resources in Teams](./media/hr-teams-leave-app-timeoff-tab.png)

## <a name="install-and-setup"></a><span data-ttu-id="caf51-109">Installa e configura</span><span class="sxs-lookup"><span data-stu-id="caf51-109">Install and setup</span></span>

<span data-ttu-id="caf51-110">Puoi trovare l'app Human Resources nello store di Teams.</span><span class="sxs-lookup"><span data-stu-id="caf51-110">You can find the Human Resources app in the Teams store.</span></span> <span data-ttu-id="caf51-111">Per informazioni sull'installazione dell'app Teams, vedi [Gestisci richieste di permessi in Teams](hr-teams-leave-app.md).</span><span class="sxs-lookup"><span data-stu-id="caf51-111">For information about installing the Teams app, see [Manage leave requests in Teams](hr-teams-leave-app.md).</span></span>

<span data-ttu-id="caf51-112">Per informazioni sulla gestione delle autorizzazioni delle app in Teams, vedi [Gestire i criteri delle autorizzazioni delle app in Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/teams-app-permission-policies).</span><span class="sxs-lookup"><span data-stu-id="caf51-112">For information about managing app permissions in Teams, see [Manage app permission policies in Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/teams-app-permission-policies).</span></span>

## <a name="enable-notifications-for-the-human-resources-app-in-teams"></a><span data-ttu-id="caf51-113">Abilitare le notifiche per l'app Human Resources in Teams</span><span class="sxs-lookup"><span data-stu-id="caf51-113">Enable notifications for the Human Resources app in Teams</span></span>

<span data-ttu-id="caf51-114">Se si desidera che gli utenti ricevano le notifiche delle richieste di congedo nell'app Teams, è necessario abilitare le notifiche in Human Resources.</span><span class="sxs-lookup"><span data-stu-id="caf51-114">If you want users to receive leave request notifications in the Teams app, you must enable notifications in Human Resources.</span></span>

>[!NOTE]
><span data-ttu-id="caf51-115">Solo gli utenti che hanno effettuato l'accesso a Teams e usano l'app Human Resources in Teams riceveranno le notifiche.</span><span class="sxs-lookup"><span data-stu-id="caf51-115">Only users who are signed into Teams and using the Human Resources Teams app will receive notifications.</span></span>

1. <span data-ttu-id="caf51-116">In Risorse umane, selezionare **Amministrazione sistema**.</span><span class="sxs-lookup"><span data-stu-id="caf51-116">In Human Resources, select **System administration**.</span></span>

2. <span data-ttu-id="caf51-117">Selezionare **Collegamenti**.</span><span class="sxs-lookup"><span data-stu-id="caf51-117">Select **Links**.</span></span>

3. <span data-ttu-id="caf51-118">Sotto **Impostazione**, selezionare **Parametri di sistema**.</span><span class="sxs-lookup"><span data-stu-id="caf51-118">Under **Setup**, select **System parameters**.</span></span>

4. <span data-ttu-id="caf51-119">Nella scheda **Generale** impostare **Abilita notifiche per l'app Teams** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="caf51-119">On the **General** tab, set **Enable notifications for Teams app** to **Yes**.</span></span>

   ![Abilitare le notifiche dell'app Teams nei parametri di sistema](./media/hr-admin-teams-leave-app-enable-notifications.png)

5. <span data-ttu-id="caf51-121">Per attivare le notifiche di Teams per tutti gli utenti, selezionare **Sì** alla richiesta.</span><span class="sxs-lookup"><span data-stu-id="caf51-121">To turn on Teams notifications for all users, select **Yes** at the prompt.</span></span>

   ![Abilitare le notifiche di Teams per tutti gli utenti](./media/hr-admin-teams-leave-app-notifications-all-users.png)

### <a name="turn-teams-notifications-on-or-off-for-individual-users"></a><span data-ttu-id="caf51-123">Attivare o disattivare le notifiche di Teams per i singoli utenti</span><span class="sxs-lookup"><span data-stu-id="caf51-123">Turn Teams notifications on or off for individual users</span></span>

<span data-ttu-id="caf51-124">Dopo aver abilitato le notifiche per l'app Human Resources in Teams, è possibile attivare o disattivare le notifiche per i singoli utenti.</span><span class="sxs-lookup"><span data-stu-id="caf51-124">After you've enabled notifications for the Human Resources Teams app, you can turn notifications on or off for individual users.</span></span>

1. <span data-ttu-id="caf51-125">In Risorse umane, selezionare **Amministrazione sistema**.</span><span class="sxs-lookup"><span data-stu-id="caf51-125">In Human Resources, select **System administration**.</span></span>

2. <span data-ttu-id="caf51-126">Selezionare **Collegamenti**.</span><span class="sxs-lookup"><span data-stu-id="caf51-126">Select **Links**.</span></span>

3. <span data-ttu-id="caf51-127">Sotto **Utenti**, selezionare **Opzioni utente**.</span><span class="sxs-lookup"><span data-stu-id="caf51-127">Under **Users**, select **User options**.</span></span>

4. <span data-ttu-id="caf51-128">Selezionare la scheda **Flusso di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="caf51-128">Select the **Workflow** tab.</span></span>

5. <span data-ttu-id="caf51-129">Impostare **Abilita le notifiche per l'app Teams** su **Sì** per abilitare le notifiche per l'utente o su **No** per disabilitare le notifiche per l'utente.</span><span class="sxs-lookup"><span data-stu-id="caf51-129">Set **Enable notifications for Teams app** to **Yes** to enable notifications for the user or **No** to disable notifications for the user.</span></span>

   ![Abilitare le notifiche dell'app Teams nella scheda Flusso di lavoro delle opzioni utente](./media/hr-admin-teams-leave-app-notifications.png)

6. <span data-ttu-id="caf51-131">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="caf51-131">Select **Save**.</span></span>

## <a name="known-issues"></a><span data-ttu-id="caf51-132">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="caf51-132">Known issues</span></span>

| <span data-ttu-id="caf51-133">Uscita</span><span class="sxs-lookup"><span data-stu-id="caf51-133">Issue</span></span> | <span data-ttu-id="caf51-134">Stato</span><span class="sxs-lookup"><span data-stu-id="caf51-134">Status</span></span> |
| --- | --- |
| <span data-ttu-id="caf51-135">Lo scorrimento orizzontale non funziona su telefoni Android</span><span class="sxs-lookup"><span data-stu-id="caf51-135">Horizontal scrolling doesn't work on Android phones</span></span> | <span data-ttu-id="caf51-136">Lo scorrimento orizzontale non è un problema su iOS o su dispositivi desktop.</span><span class="sxs-lookup"><span data-stu-id="caf51-136">Horizontal scrolling isn't an issue on iOS or desktop devices.</span></span> <span data-ttu-id="caf51-137">Stiamo lavorando a una correzione per Android.</span><span class="sxs-lookup"><span data-stu-id="caf51-137">We're working on a fix for Android.</span></span> |
| <span data-ttu-id="caf51-138">Errore: si è verificato un problema durante la ricerca di un ambiente a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="caf51-138">Error: There is an issue finding an environment to connect to.</span></span> | <span data-ttu-id="caf51-139">Questo errore potrebbe essere visualizzato anche se hai verificato che l'utente può accedere a uno o più ambienti di Human Resources.</span><span class="sxs-lookup"><span data-stu-id="caf51-139">You might receive this error even if you've verified that the user can access one or more Human Resources environments.</span></span> <span data-ttu-id="caf51-140">Inoltre, potresti non vedere tutti gli ambienti previsti.</span><span class="sxs-lookup"><span data-stu-id="caf51-140">Also, you might not see all the environments you expect.</span></span> <span data-ttu-id="caf51-141">Fino a quando questo problema non vine risolto, elimina l'utente e quindi importalo di nuovo per risolvere il problema.</span><span class="sxs-lookup"><span data-stu-id="caf51-141">Until we fix this issue, delete the user and then import them in again to resolve the problem.</span></span> |
| <span data-ttu-id="caf51-142">Il saldo non è corretto quando richiedi permessi per una data futura.</span><span class="sxs-lookup"><span data-stu-id="caf51-142">The balance is incorrect when submitting time off for a future date.</span></span> | <span data-ttu-id="caf51-143">Le previsioni non sono ancora disponibili.</span><span class="sxs-lookup"><span data-stu-id="caf51-143">Forecasting isn't yet available.</span></span> <span data-ttu-id="caf51-144">Il saldo visualizza la data corrente.</span><span class="sxs-lookup"><span data-stu-id="caf51-144">The balance displays for the current date.</span></span> |
| <span data-ttu-id="caf51-145">Impossibile annullare una richiesta **In revisione**.</span><span class="sxs-lookup"><span data-stu-id="caf51-145">Unable to cancel an **In review** request.</span></span> | <span data-ttu-id="caf51-146">Questa funzionalità non è attualmente supportata e verrà aggiunta in una versione futura.</span><span class="sxs-lookup"><span data-stu-id="caf51-146">This functionality isn't currently supported and will be added in a future release.</span></span> |
| <span data-ttu-id="caf51-147">Le informazioni sul saldo sono calcolate a partire da oggi.</span><span class="sxs-lookup"><span data-stu-id="caf51-147">Balance information is calculated as of today.</span></span> | <span data-ttu-id="caf51-148">Il sistema al momento non visualizza i saldi al momento del periodo di competenza, anche se configurato nei parametri congedo e assenza.</span><span class="sxs-lookup"><span data-stu-id="caf51-148">The system currently doesn't display balances as of the accrual period, even if it's configured in Leave and absence parameters.</span></span> |

## <a name="privacy-notice"></a><span data-ttu-id="caf51-149">Informativa sulla privacy</span><span class="sxs-lookup"><span data-stu-id="caf51-149">Privacy notice</span></span>

### <a name="microsoft-language-understanding-intelligent-service-luis"></a><span data-ttu-id="caf51-150">Microsoft Language Understanding Intelligent Service (LUIS)</span><span class="sxs-lookup"><span data-stu-id="caf51-150">Microsoft Language Understanding Intelligent Service (LUIS)</span></span>

<span data-ttu-id="caf51-151">Con il bot Dynamics 365 Human Resources in Microsoft Teams, gli input di testo dell'utente vengono analizzati per comprendere la query/l'intento sottostanti.</span><span class="sxs-lookup"><span data-stu-id="caf51-151">With the Dynamics 365 Human Resources bot in Microsoft Teams, the user’s text inputs are analyzed for understanding the underlying query/intent.</span></span> <span data-ttu-id="caf51-152">L'input dell'utente, ad esempio "Cerca account Contoso", viene indirizzato a uno dei servizi cognitivi di Microsoft chiamato Language Understanding Intelligent Service (LUIS).</span><span class="sxs-lookup"><span data-stu-id="caf51-152">The user’s input such as “Search account Contoso” is routed to one of Microsoft’s Cognitive Service called Language Understanding Intelligent Service (LUIS).</span></span> <span data-ttu-id="caf51-153">Ulteriori informazioni su LUIS [qui](https://www.luis.ai/).</span><span class="sxs-lookup"><span data-stu-id="caf51-153">Read more about LUIS [here](https://www.luis.ai/).</span></span> <span data-ttu-id="caf51-154">Il servizio LUIS disambigua o comprende l'intento dell'input dell'utente (in questo caso, l'intento è quello di trovare informazioni) e l'entità di destinazione (in questo caso, l'entità desiderata è un account chiamato Contoso).</span><span class="sxs-lookup"><span data-stu-id="caf51-154">The LUIS service disambiguates or understands the intent of user input (in this case, the intent is to find information) and the target entity (in this case, the intended entity is an account named Contoso).</span></span> <span data-ttu-id="caf51-155">Queste informazioni vengono quindi trasmesse al  [Bot Framework di Azure](https://azure.microsoft.com/services/bot-service/) di Microsoft che interagisce con i dati da Dynamics 365 Human Resources e recupera le informazioni desiderate per la query dell'utente.</span><span class="sxs-lookup"><span data-stu-id="caf51-155">This information is then passed on to Microsoft’s [Azure bot framework](https://azure.microsoft.com/services/bot-service/), which interacts with data from Dynamics 365 Human Resources and retrieves the desired information for the user query.</span></span> 

<span data-ttu-id="caf51-156">Installando e consentendo l'accesso all'uso del bot, l'utente accetta di consentire al servizio LUIS e al framework del bot di Azure di elaborare l'intento dietro l'input, il che si traduce in un'esperienza utente conversazionale migliorata.</span><span class="sxs-lookup"><span data-stu-id="caf51-156">By installing and allowing access to use of the bot, you agree to allow the LUIS service and Azure bot framework to process the intent behind the input,  which results in an enhanced conversational user experience.</span></span> <span data-ttu-id="caf51-157">Il servizio LUIS e il framework dei bot di Azure possono presentare livelli di conformità diversi rispetto a Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="caf51-157">The LUIS service and Azure bot framework may have varying levels of compliance compared to Dynamics 365 Human Resources.</span></span> <span data-ttu-id="caf51-158">Mentre il servizio LUIS ha accesso solo alle query dell'utente e non è progettato per essere collegato ai dati o all'account Dynamics 365 Human Resources dell'utente, un utente del bot Dynamics 365 Human Resources potrebbe inserire volontariamente una query contenente dati del cliente, dati personali o altri dati e tale contenuto della query potrebbe essere inviato al servizio LUIS e al framework del bot di Azure.</span><span class="sxs-lookup"><span data-stu-id="caf51-158">While the LUIS service has access to only the user queries and is not designed to be connected to the user’s Dynamics 365 Human Resources data or account, a user of the Dynamics 365 Human Resources bot could voluntarily enter a query containing Customer Data, Personal Data, or other data and such query content could get sent to the LUIS service and the Azure bot framework.</span></span> 

<span data-ttu-id="caf51-159">Il contenuto delle query e dei messaggi dell'utente viene conservato nel sistema LUIS per un massimo di 30 giorni, viene crittografato a riposo e non viene utilizzato per migliorare la formazione o il servizio.</span><span class="sxs-lookup"><span data-stu-id="caf51-159">The content of user’s queries and messages is retained in LUIS system for a maximum of 30 days, is encrypted at rest, and is not used for training or service improvement.</span></span> <span data-ttu-id="caf51-160">Ulteriori informazioni sui servizi cognitivi [qui](https://azure.microsoft.com/services/cognitive-services/language-understanding-intelligent-service/).</span><span class="sxs-lookup"><span data-stu-id="caf51-160">Read more about Cognitive Services [here](https://azure.microsoft.com/services/cognitive-services/language-understanding-intelligent-service/).</span></span> 

<span data-ttu-id="caf51-161">Per gestire le impostazioni di amministrazione per le app in Microsoft Teams, vai all'[interfaccia di amministrazione di Microsoft Teams](https://admin.teams.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="caf51-161">To manage admin settings for apps in Microsoft Teams, go to the [Microsoft Teams admin center](https://admin.teams.microsoft.com/).</span></span>

### <a name="microsoft-azure-event-grid-and-microsoft-teams"></a><span data-ttu-id="caf51-162">Griglia di eventi Microsoft Azure e Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="caf51-162">Microsoft Azure Event Grid and Microsoft Teams</span></span>

<span data-ttu-id="caf51-163">Quando si utilizza la funzione di notifica per l'app Dynamics 365 Human Resources in Teams, alcuni dati dei clienti passeranno al di fuori dell'area geografica in cui è distribuito il servizio Human Resources del tenant.</span><span class="sxs-lookup"><span data-stu-id="caf51-163">When using the notifications feature for the Dynamics 365 Human Resources app in Teams, certain customer data will flow outside of the geographic region where your tenant’s Human Resources service is deployed.</span></span> <span data-ttu-id="caf51-164">Dynamics 365 Human Resources trasmette la richiesta di congedo del dipendente e i dettagli dell'attività del flusso di lavoro alla Griglia di eventi di Microsoft Azure e Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="caf51-164">Dynamics 365 Human Resources transmits the employee’s leave request and workflow task details to Microsoft Azure Event Grid and Microsoft Teams.</span></span> <span data-ttu-id="caf51-165">Questi dati possono essere archiviati per un massimo di 24 ore ed elaborati negli Stati Uniti, vengono crittografati i dati in transito e inattivi e non vengono utilizzati da Microsoft o dai collaboratori di elaborazione per la formazione o il miglioramento del servizio.</span><span class="sxs-lookup"><span data-stu-id="caf51-165">This data may be stored for up to 24 hours and processed in the United States, is encrypted in transit and at rest, and is not used by Microsoft or its subprocessors for training or service improvements.</span></span>

## <a name="see-also"></a><span data-ttu-id="caf51-166">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="caf51-166">See also</span></span> 

[<span data-ttu-id="caf51-167">Scaricare e installare Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="caf51-167">Download and install Microsoft Teams</span></span>](https://support.office.com/article/download-and-install-microsoft-teams-422bf3aa-9ae8-46f1-83a2-e65720e1a34d)</br>
[<span data-ttu-id="caf51-168">Centro assistenza di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="caf51-168">Microsoft Teams help center</span></span>](https://support.office.com/teams)</br>
[<span data-ttu-id="caf51-169">Gestire le richieste di congedo in Teams</span><span class="sxs-lookup"><span data-stu-id="caf51-169">Manage leave requests in Teams</span></span>](hr-teams-leave-app.md)

