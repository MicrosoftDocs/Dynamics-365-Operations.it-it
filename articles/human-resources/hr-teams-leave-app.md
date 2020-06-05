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
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-05-18
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 67501a1fa65493a1a23eb6176ece5be98d6e4659
ms.sourcegitcommit: 7fc0726c0a93ce6f4dafaad3232b4687f61cdc88
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/21/2020
ms.locfileid: "3393010"
---
# <a name="manage-leave-requests-in-teams"></a><span data-ttu-id="497d8-103">Gestire le richieste di congedo in Teams</span><span class="sxs-lookup"><span data-stu-id="497d8-103">Manage leave requests in Teams</span></span>

[!include [banner](includes/preview-feature.md)]

<span data-ttu-id="497d8-104">L'app Microsoft Dynamics 365 Human Resources in Microsoft Teams ti consente di richiedere rapidamente permessi e di visualizzare le informazioni sul loro saldo permessi direttamente in Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="497d8-104">The Microsoft Dynamics 365 Human Resources app in Microsoft Teams lets you quickly request time off and view your time-off balance information right in Microsoft Teams.</span></span> <span data-ttu-id="497d8-105">Puoi interagire con un bot per richiedere informazioni.</span><span class="sxs-lookup"><span data-stu-id="497d8-105">You can interact with a bot to request information.</span></span> <span data-ttu-id="497d8-106">La scheda **Tempo libero** fornisce informazioni più dettagliate.</span><span class="sxs-lookup"><span data-stu-id="497d8-106">The **Time off** tab provides more detailed information.</span></span>

## <a name="install-the-app"></a><span data-ttu-id="497d8-107">Installa l'app</span><span class="sxs-lookup"><span data-stu-id="497d8-107">Install the app</span></span>

<span data-ttu-id="497d8-108">Puoi trovare l'app Human Resources nello store di Teams.</span><span class="sxs-lookup"><span data-stu-id="497d8-108">You can find the Human Resources app in the Teams store.</span></span>

1. <span data-ttu-id="497d8-109">In Microsoft Teams, seleziona i puntini di sospensione.</span><span class="sxs-lookup"><span data-stu-id="497d8-109">In Microsoft Teams, select the ellipses.</span></span>

   ![Puntini di sospensione dell'app per i permessi Human Resources in Teams](./media/hr-teams-leave-app-ellipses.png)
 
2. <span data-ttu-id="497d8-111">Cerca Dynamics 365 Human Resources, quindi seleziona il riquadro **Human Resources**.</span><span class="sxs-lookup"><span data-stu-id="497d8-111">Search for Dynamics 365 Human Resources, and then select the **Human Resources** tile.</span></span>

   ![Riquadro HR dell'app per i permessi Human Resources in Teams](./media/hr-teams-leave-app-human-resources-tile.png)

3. <span data-ttu-id="497d8-113">Seleziona il pulsante **Aggiungi** per installare l'app.</span><span class="sxs-lookup"><span data-stu-id="497d8-113">Select the **Add** button to install the app.</span></span>

   ![Installazione dell'app per i permessi Human Resources in Teams](./media/hr-teams-leave-app-in-store.png)

<span data-ttu-id="497d8-115">Se l'app non ti consente di accede automaticamente, seleziona la scheda **impostazioni** per accedere.</span><span class="sxs-lookup"><span data-stu-id="497d8-115">If the app doesn't automatically sign you in, select the **Settings** tab to sign in.</span></span>

![Scheda Impostazioni dell'app per i permessi Human Resources in Teams](./media/hr-teams-leave-app-settings-tab.png)

> [!NOTE]
> <span data-ttu-id="497d8-117">Se non vedi una finestra di accesso, controlla le impostazioni del browser per consentire i popup.</span><span class="sxs-lookup"><span data-stu-id="497d8-117">If you don’t see a sign-in dialog box, check your browser settings to allow pop-ups.</span></span> 

<span data-ttu-id="497d8-118">Se hai accesso a più di un'istanza di Human Resources, puoi selezionare a quale ambiente vuoi connetterti nella scheda **Impostazioni**.</span><span class="sxs-lookup"><span data-stu-id="497d8-118">If you have access to more than one instance of Human Resources, you can select which environment you want to connect to in the **Settings** tab.</span></span>

> [!WARNING]
> <span data-ttu-id="497d8-119">L'app al momento non supporta il ruolo di sicurezza dell'amministratore di sistema e visualizzerà un messaggio di errore se accedi con un account dell'amministratore di sistema.</span><span class="sxs-lookup"><span data-stu-id="497d8-119">The app doesn't currently support the System Administrator security role, and will display an error message if you sign in with a System Administrator account.</span></span> <span data-ttu-id="497d8-120">Per accedere con un altro account, nella scheda **Impostazioni**, seleziona il pulsante **Cambia account**, quindi accedi con un account utente che non dispone dei privilegi di amministratore di sistema.</span><span class="sxs-lookup"><span data-stu-id="497d8-120">To sign in with a different account, on the **Settings** tab, select the **Switch accounts** button, and then sign in with a user account that doesn’t have System Administrator privileges.</span></span>
 
## <a name="use-the-bot"></a><span data-ttu-id="497d8-121">Usa il bot</span><span class="sxs-lookup"><span data-stu-id="497d8-121">Use the bot</span></span>

<span data-ttu-id="497d8-122">Dopo l'installazione dell'app, viene visualizzato un messaggio di benvenuto che ti informa sui tipi di azioni che il bot può eseguire per tuo conto.</span><span class="sxs-lookup"><span data-stu-id="497d8-122">After the app installs, a welcome message appears, letting you know the types of actions the bot can take on your behalf.</span></span>

![Messaggio di benvenuto del bot dell'app per i permessi Human Resources in Teams](./media/hr-teams-leave-app-bot.png)
 
> [!NOTE]
> <span data-ttu-id="497d8-124">Quando interagisci per la prima volta con il bot, potresti dover eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="497d8-124">When first interacting with the bot, you might need to sign in.</span></span> <span data-ttu-id="497d8-125">Se non vedi una finestra di accesso, controlla le impostazioni del browser per consentire i popup.</span><span class="sxs-lookup"><span data-stu-id="497d8-125">If you don’t see a sign-in dialog box, check your browser settings to allow pop-ups.</span></span>

<span data-ttu-id="497d8-126">Puoi chiedere al bot di:</span><span class="sxs-lookup"><span data-stu-id="497d8-126">You can ask the bot to:</span></span>

- <span data-ttu-id="497d8-127">Mostra le informazioni sul saldo dei permessi per ciascun tipo di congedo a cui sei registrato.</span><span class="sxs-lookup"><span data-stu-id="497d8-127">Show time-off balance information for each leave type you're enrolled in.</span></span>

   ![Visualizzazione saldi dell'app per i permessi Human Resources in Teams](./media/hr-teams-leave-app-bot-balances.png)
 
- <span data-ttu-id="497d8-129">Mostra ulteriori dettagli su un tipo di congedo specifico.</span><span class="sxs-lookup"><span data-stu-id="497d8-129">Show additional details about a specific leave type.</span></span>

   ![Visualizzazione dettagli dell'app per i permessi Human Resources in Teams](./media/hr-teams-leave-app-bot-details.png)

- <span data-ttu-id="497d8-131">Inizia una richiesta di ferie per te.</span><span class="sxs-lookup"><span data-stu-id="497d8-131">Start a leave request for you.</span></span>

   ![Richiesta permesso dell'app per i permessi Human Resources in Teams](./media/hr-teams-leave-app-bot-request.png)
 
<span data-ttu-id="497d8-133">Dopo aver avviato una richiesta di ferie, è possibile modificare i giorni direttamente all'interno della carta oppure selezionare **Modifica dettagli** per aggiungere ulteriori informazioni alla tua richiesta.</span><span class="sxs-lookup"><span data-stu-id="497d8-133">After you start a leave request, you can adjust the days right within the card, or you can select **Edit details** to add additional information to your request.</span></span>

![Modifica richiesta dell'app per i permessi Human Resources in Teams](./media/hr-teams-leave-app-bot-edit.png)
 
<span data-ttu-id="497d8-135">Al termine dell'immissione delle informazioni, digita **Invia** per inviarle per l'approvazione.</span><span class="sxs-lookup"><span data-stu-id="497d8-135">When you're done entering information, type **Submit** to submit it for approval.</span></span> <span data-ttu-id="497d8-136">Puoi anche digitare **Salva come bozza** per tornare più tardi.</span><span class="sxs-lookup"><span data-stu-id="497d8-136">You can also type **Save as draft** to come back to it later.</span></span>

![Invio richiesta nell'app per i permessi Human Resources in Teams](./media/hr-teams-leave-app-bot-submit.png)

## <a name="manage-your-leave-in-teams"></a><span data-ttu-id="497d8-138">Gestire i congedi in Teams</span><span class="sxs-lookup"><span data-stu-id="497d8-138">Manage your leave in Teams</span></span>

<span data-ttu-id="497d8-139">La scheda **Tempo libero** ti consente di visualizzare:</span><span class="sxs-lookup"><span data-stu-id="497d8-139">The **Time off** tab allows you to view:</span></span>

- <span data-ttu-id="497d8-140">Informazioni sul saldo per ciascun tipo di congedo a cui sei registrato</span><span class="sxs-lookup"><span data-stu-id="497d8-140">Balance information for each leave type you're enrolled in</span></span>

- <span data-ttu-id="497d8-141">Prossime richieste di congedo</span><span class="sxs-lookup"><span data-stu-id="497d8-141">Upcoming leave requests</span></span>

- <span data-ttu-id="497d8-142">Richieste di tempo libero</span><span class="sxs-lookup"><span data-stu-id="497d8-142">Time-off requests</span></span>

- <span data-ttu-id="497d8-143">Bozza di richieste di congedo</span><span class="sxs-lookup"><span data-stu-id="497d8-143">Draft leave requests</span></span>

![Scheda Tempo libero dell'app per i permessi Human Resources in Teams](./media/hr-teams-leave-app-timeoff-tab.png)
 
### <a name="create-a-new-request"></a><span data-ttu-id="497d8-145">Crea una nuova richiesta</span><span class="sxs-lookup"><span data-stu-id="497d8-145">Create a new request</span></span>

1. <span data-ttu-id="497d8-146">Per creare una nuova richiesta di congedo, seleziona **Nuova richiesta**.</span><span class="sxs-lookup"><span data-stu-id="497d8-146">To create a new leave request, select **New request**.</span></span>

   ![Nuova richiesta dell'app per i permessi Human Resources in Teams](./media/hr-teams-leave-app-timeoff-tab-new.png)

2. <span data-ttu-id="497d8-148">Immetti il giorno o i giorni che desideri prendere come congedo, quindi seleziona **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="497d8-148">Enter the day or days you want to take off, and then select **Add**.</span></span>

   ![Aggiungi congedo app per i permessi Human Resources in Teams](./media/hr-teams-leave-app-timeoff-tab-add.png)

3. <span data-ttu-id="497d8-150">Se applicabile, inserisci un codice motivo.</span><span class="sxs-lookup"><span data-stu-id="497d8-150">If applicable, enter a reason code.</span></span> <span data-ttu-id="497d8-151">Inserisci anche eventuali commenti e aggiungi eventuali allegati.</span><span class="sxs-lookup"><span data-stu-id="497d8-151">Also enter any comments and add any attachments.</span></span>

4. <span data-ttu-id="497d8-152">Al termine dell'immissione delle informazioni, digita **Invia** per inviarle per l'approvazione.</span><span class="sxs-lookup"><span data-stu-id="497d8-152">When you're done entering information, type **Submit** to submit it for approval.</span></span> <span data-ttu-id="497d8-153">Puoi anche digitare **Salva come bozza** per tornare più tardi.</span><span class="sxs-lookup"><span data-stu-id="497d8-153">You can also type **Save as draft** to come back to it later.</span></span>

### <a name="manage-draft-requests"></a><span data-ttu-id="497d8-154">Gestisci bozze di richiesta</span><span class="sxs-lookup"><span data-stu-id="497d8-154">Manage draft requests</span></span>

1. <span data-ttu-id="497d8-155">Seleziona la scheda **Bozze**.</span><span class="sxs-lookup"><span data-stu-id="497d8-155">Select the **Drafts** tab.</span></span>

   ![Scheda Bozze dell'app per i permessi Human Resources in Teams](./media/hr-teams-leave-app-drafts-tab.png)

2. <span data-ttu-id="497d8-157">Seleziona la matita per modificare la richiesta o seleziona il cestino per eliminare la richiesta.</span><span class="sxs-lookup"><span data-stu-id="497d8-157">Select the pencil to edit the request, or select the trash can to delete the request.</span></span>

3. <span data-ttu-id="497d8-158">Apporta le modifiche necessarie.</span><span class="sxs-lookup"><span data-stu-id="497d8-158">Make any necessary changes.</span></span> <span data-ttu-id="497d8-159">Al termine dell'immissione delle informazioni, digita **Invia** per inviarle per l'approvazione.</span><span class="sxs-lookup"><span data-stu-id="497d8-159">When you're done entering information, type **Submit** to submit it for approval.</span></span> <span data-ttu-id="497d8-160">Puoi anche selezionare **Salva come bozza** per tornare più tardi.</span><span class="sxs-lookup"><span data-stu-id="497d8-160">You can also select **Save as draft** to come back to it later.</span></span>

   ![Modifica bozza dell'app per i permessi Human Resources in Teams](./media/hr-teams-leave-app-drafts-edit.png)
   
## <a name="privacy-notice"></a><span data-ttu-id="497d8-162">Informativa sulla privacy</span><span class="sxs-lookup"><span data-stu-id="497d8-162">Privacy notice</span></span>

<span data-ttu-id="497d8-163">Con il bot Dynamics 365 Human Resources in Microsoft Teams, gli input di testo dell'utente vengono analizzati per comprendere la query/l'intento sottostanti.</span><span class="sxs-lookup"><span data-stu-id="497d8-163">With the Dynamics 365 Human Resources bot in Microsoft Teams, the user’s text inputs are analyzed for understanding the underlying query/intent.</span></span> <span data-ttu-id="497d8-164">L'input dell'utente, ad esempio "Cerca account Contoso", viene indirizzato a uno dei servizi cognitivi di Microsoft chiamato Language Understanding Intelligent Service (LUIS).</span><span class="sxs-lookup"><span data-stu-id="497d8-164">The user’s input such as “Search account Contoso” is routed to one of Microsoft’s Cognitive Service called Language Understanding Intelligent Service (LUIS).</span></span> <span data-ttu-id="497d8-165">Ulteriori informazioni su LUIS [qui](https://www.luis.ai/).</span><span class="sxs-lookup"><span data-stu-id="497d8-165">Read more about LUIS [here](https://www.luis.ai/).</span></span> <span data-ttu-id="497d8-166">Il servizio LUIS disambigua o comprende l'intento dell'input dell'utente (in questo caso, l'intento è quello di trovare informazioni) e l'entità di destinazione (in questo caso, l'entità desiderata è un account chiamato Contoso).</span><span class="sxs-lookup"><span data-stu-id="497d8-166">The LUIS service disambiguates or understands the intent of user input (in this case, the intent is to find information) and the target entity (in this case, the intended entity is an account named Contoso).</span></span> <span data-ttu-id="497d8-167">Queste informazioni vengono quindi trasmesse al [Framework bot di Azure](https://azure.microsoft.com/services/bot-service/) di Microsoft che interagisce con i dati da Dynamics 365 Human Resources e recupera le informazioni desiderate per la query dell'utente.</span><span class="sxs-lookup"><span data-stu-id="497d8-167">This information is then passed on to Microsoft’s [Azure bot framework](https://azure.microsoft.com/services/bot-service/) which interacts with data from Dynamics 365 Human Resources and retrieves the desired information for the user query.</span></span> 

<span data-ttu-id="497d8-168">Installando e consentendo l'accesso all'uso del bot, l'utente accetta di consentire al servizio LUIS e al framework del bot di Azure di elaborare l'intento dietro l'input, il che si traduce in un'esperienza utente conversazionale migliorata.</span><span class="sxs-lookup"><span data-stu-id="497d8-168">By installing and allowing access to use of the bot, you agree to allow the LUIS service and Azure bot framework to process the intent behind the input,  which results in an enhanced conversational user experience.</span></span> <span data-ttu-id="497d8-169">Il servizio LUIS e il framework dei bot di Azure possono presentare livelli di conformità diversi rispetto a Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="497d8-169">The LUIS service and Azure bot framework may have varying levels of compliance compared to Dynamics 365 Human Resources.</span></span> <span data-ttu-id="497d8-170">Mentre il servizio LUIS ha accesso solo alle query dell'utente e non è progettato per essere collegato ai dati o all'account Dynamics 365 Human Resources dell'utente, un utente del bot Dynamics 365 Human Resources potrebbe inserire volontariamente una query contenente dati del cliente, dati personali o altri dati e tale contenuto della query potrebbe essere inviato al servizio LUIS e al framework del bot di Azure.</span><span class="sxs-lookup"><span data-stu-id="497d8-170">While the LUIS service has access to only the user queries and is not designed to be connected to the user’s Dynamics 365 Human Resources data or account, a user of the Dynamics 365 Human Resources bot could voluntarily enter a query containing Customer Data, Personal Data, or other data and such query content could get sent to the LUIS service and the Azure bot framework.</span></span> 

<span data-ttu-id="497d8-171">Il contenuto delle query e dei messaggi dell'utente viene conservato nel sistema LUIS per un massimo di 30 giorni, viene crittografato a riposo e non viene utilizzato per migliorare la formazione o il servizio.</span><span class="sxs-lookup"><span data-stu-id="497d8-171">The content of user’s queries and messages is retained in LUIS system for a maximum of 30 days, is encrypted at rest, and is not used for training or service improvement.</span></span> <span data-ttu-id="497d8-172">Ulteriori informazioni sui servizi cognitivi [qui](https://azure.microsoft.com/services/cognitive-services/language-understanding-intelligent-service/).</span><span class="sxs-lookup"><span data-stu-id="497d8-172">Read more about Cognitive Services [here](https://azure.microsoft.com/services/cognitive-services/language-understanding-intelligent-service/).</span></span> 

<span data-ttu-id="497d8-173">Per gestire le impostazioni di amministrazione per le app in Microsoft Teams, vai all'[interfaccia di amministrazione di Microsoft Teams](https://admin.teams.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="497d8-173">To manage admin settings for apps in Microsoft Teams, go to the [Microsoft Teams admin center](https://admin.teams.microsoft.com/).</span></span> 

## <a name="see-also"></a><span data-ttu-id="497d8-174">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="497d8-174">See also</span></span>

[<span data-ttu-id="497d8-175">Scaricare e installare Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="497d8-175">Download and install Microsoft Teams</span></span>](https://support.office.com/article/download-and-install-microsoft-teams-422bf3aa-9ae8-46f1-83a2-e65720e1a34d)</br>
[<span data-ttu-id="497d8-176">Centro assistenza di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="497d8-176">Microsoft Teams help center</span></span>](https://support.office.com/teams)</br>
[<span data-ttu-id="497d8-177">App Human Resources in Teams</span><span class="sxs-lookup"><span data-stu-id="497d8-177">Human Resources app in Teams</span></span>](hr-admin-teams-leave-app.md)
