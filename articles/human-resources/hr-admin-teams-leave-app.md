---
title: App Human Resources in Teams
description: Questo argomento introduce l'app Microsoft Dynamics 365 Human Resources in Microsoft Teams.
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
ms.openlocfilehash: 423ec36a73e8af9d915c5cfe16bd4d552448e2b6
ms.sourcegitcommit: d1541831d556b722a71aed442043ffb4a4576d87
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2020
ms.locfileid: "3388118"
---
# <a name="human-resources-app-in-teams"></a><span data-ttu-id="f743e-103">App Human Resources in Teams</span><span class="sxs-lookup"><span data-stu-id="f743e-103">Human Resources app in Teams</span></span>

[!include [banner](includes/preview-feature.md)]

<span data-ttu-id="f743e-104">L'app Microsoft Dynamics 365 Human Resources in Microsoft Teams consente ai dipendenti di richiedere rapidamente permessi e di visualizzare le informazioni sul loro saldo permessi in Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="f743e-104">The Microsoft Dynamics 365 Human Resources app in Microsoft Teams lets employees quickly request time off and view their time-off balance information in Microsoft Teams.</span></span> <span data-ttu-id="f743e-105">I dipendenti possono interagire con un bot per richiedere informazioni.</span><span class="sxs-lookup"><span data-stu-id="f743e-105">Employees can interact with a bot to request information.</span></span> <span data-ttu-id="f743e-106">La scheda **Tempo libero** fornisce informazioni più dettagliate.</span><span class="sxs-lookup"><span data-stu-id="f743e-106">The **Time off** tab provides more detailed information.</span></span>

![Bot dell'app per i permessi Human Resources in Teams](./media/hr-admin-teams-leave-app-bot.png)

![Scheda Tempo libero dell'app per i permessi Human Resources in Teams](./media/hr-teams-leave-app-timeoff-tab.png)

## <a name="install-and-setup"></a><span data-ttu-id="f743e-109">Installa e configura</span><span class="sxs-lookup"><span data-stu-id="f743e-109">Install and setup</span></span>

<span data-ttu-id="f743e-110">Puoi trovare l'app Human Resources nello store di Teams.</span><span class="sxs-lookup"><span data-stu-id="f743e-110">You can find the Human Resources app in the Teams store.</span></span> <span data-ttu-id="f743e-111">Per informazioni sull'installazione dell'app Teams, vedi [Gestisci richieste di permessi in Teams](hr-teams-leave-app.md).</span><span class="sxs-lookup"><span data-stu-id="f743e-111">For information about installing the Teams app, see [Manage leave requests in Teams](hr-teams-leave-app.md).</span></span>

<span data-ttu-id="f743e-112">Per informazioni sulla gestione delle autorizzazioni delle app in Teams, vedi [Gestire i criteri delle autorizzazioni delle app in Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/teams-app-permission-policies).</span><span class="sxs-lookup"><span data-stu-id="f743e-112">For information about managing app permissions in Teams, see [Manage app permission policies in Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/teams-app-permission-policies).</span></span>

## <a name="known-issues"></a><span data-ttu-id="f743e-113">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="f743e-113">Known issues</span></span>

| <span data-ttu-id="f743e-114">Uscita</span><span class="sxs-lookup"><span data-stu-id="f743e-114">Issue</span></span> | <span data-ttu-id="f743e-115">Stato</span><span class="sxs-lookup"><span data-stu-id="f743e-115">Status</span></span> |
| --- | --- |
| <span data-ttu-id="f743e-116">Il saldo non è corretto quando richiedi permessi per una data futura.</span><span class="sxs-lookup"><span data-stu-id="f743e-116">The balance is incorrect when submitting time off for a future date.</span></span> | <span data-ttu-id="f743e-117">Le previsioni non sono ancora disponibili.</span><span class="sxs-lookup"><span data-stu-id="f743e-117">Forecasting isn't yet available.</span></span> <span data-ttu-id="f743e-118">Il saldo visualizza la data corrente.</span><span class="sxs-lookup"><span data-stu-id="f743e-118">The balance displays for the current date.</span></span> |
| <span data-ttu-id="f743e-119">Quando si riduce il numero di ore impiegate in una richiesta esistente, il **Saldo restante** scende invece di salire.</span><span class="sxs-lookup"><span data-stu-id="f743e-119">When reducing the number of hours taken in an existing request, the **Remaining balance** goes down instead of up.</span></span> | <span data-ttu-id="f743e-120">Affronteremo questo problema noto in futuro.</span><span class="sxs-lookup"><span data-stu-id="f743e-120">We'll address this known issue in the future.</span></span> <span data-ttu-id="f743e-121">La visualizzazione non è corretta, ma gli importi corretti vengono adeguati al momento dell'invio.</span><span class="sxs-lookup"><span data-stu-id="f743e-121">The display is incorrect, but the correct amounts are adjusted upon submission.</span></span> |
| <span data-ttu-id="f743e-122">Vengono visualizzate due schede **Tempo libero imminente** per le stesse date.</span><span class="sxs-lookup"><span data-stu-id="f743e-122">Two **Upcoming time off** cards display for the same dates.</span></span> | <span data-ttu-id="f743e-123">Le schede rappresentano singoli invii.</span><span class="sxs-lookup"><span data-stu-id="f743e-123">The cards represent individual submissions.</span></span> <span data-ttu-id="f743e-124">Continueremo a ricevere feedback e ad apportare modifiche.</span><span class="sxs-lookup"><span data-stu-id="f743e-124">We'll continue to take feedback and make adjustments.</span></span> |
| <span data-ttu-id="f743e-125">Impossibile annullare una richiesta **In revisione**.</span><span class="sxs-lookup"><span data-stu-id="f743e-125">Unable to cancel an **In review** request.</span></span> | <span data-ttu-id="f743e-126">Questa funzionalità non è attualmente supportata e verrà aggiunta in una versione futura.</span><span class="sxs-lookup"><span data-stu-id="f743e-126">This functionality isn't currently supported and will be added in a future release.</span></span> |
| <span data-ttu-id="f743e-127">Le informazioni sul saldo sono calcolate a partire da oggi.</span><span class="sxs-lookup"><span data-stu-id="f743e-127">Balance information is calculated as of today.</span></span> | <span data-ttu-id="f743e-128">Il sistema al momento non visualizza i saldi al momento del periodo di competenza, anche se configurato nei parametri congedo e assenza.</span><span class="sxs-lookup"><span data-stu-id="f743e-128">The system currently doesn't display balances as of the accrual period, even if it's configured in Leave and absence parameters.</span></span> |

## <a name="privacy-notice"></a><span data-ttu-id="f743e-129">Informativa sulla privacy</span><span class="sxs-lookup"><span data-stu-id="f743e-129">Privacy notice</span></span>

<span data-ttu-id="f743e-130">Con il bot Dynamics 365 Human Resources in Microsoft Teams, gli input di testo dell'utente vengono analizzati per comprendere la query/l'intento sottostanti.</span><span class="sxs-lookup"><span data-stu-id="f743e-130">With the Dynamics 365 Human Resources bot in Microsoft Teams, the user’s text inputs are analyzed for understanding the underlying query/intent.</span></span> <span data-ttu-id="f743e-131">L'input dell'utente, ad esempio "Cerca account Contoso", viene indirizzato a uno dei servizi cognitivi di Microsoft chiamato Language Understanding Intelligent Service (LUIS).</span><span class="sxs-lookup"><span data-stu-id="f743e-131">The user’s input such as “Search account Contoso” is routed to one of Microsoft’s Cognitive Service called Language Understanding Intelligent Service (LUIS).</span></span> <span data-ttu-id="f743e-132">Ulteriori informazioni su LUIS [qui](https://www.luis.ai/).</span><span class="sxs-lookup"><span data-stu-id="f743e-132">Read more about LUIS [here](https://www.luis.ai/).</span></span> <span data-ttu-id="f743e-133">Il servizio LUIS disambigua o comprende l'intento dell'input dell'utente (in questo caso, l'intento è quello di trovare informazioni) e l'entità di destinazione (in questo caso, l'entità desiderata è un account chiamato Contoso).</span><span class="sxs-lookup"><span data-stu-id="f743e-133">The LUIS service disambiguates or understands the intent of user input (in this case, the intent is to find information) and the target entity (in this case, the intended entity is an account named Contoso).</span></span> <span data-ttu-id="f743e-134">Queste informazioni vengono quindi trasmesse al [Framework bot di Azure](https://azure.microsoft.com/services/bot-service/) di Microsoft che interagisce con i dati da Dynamics 365 Human Resources e recupera le informazioni desiderate per la query dell'utente.</span><span class="sxs-lookup"><span data-stu-id="f743e-134">This information is then passed on to Microsoft’s [Azure bot framework](https://azure.microsoft.com/services/bot-service/) which interacts with data from Dynamics 365 Human Resources and retrieves the desired information for the user query.</span></span> 

<span data-ttu-id="f743e-135">Installando e consentendo l'accesso all'uso del bot, l'utente accetta di consentire al servizio LUIS e al framework del bot di Azure di elaborare l'intento dietro l'input, il che si traduce in un'esperienza utente conversazionale migliorata.</span><span class="sxs-lookup"><span data-stu-id="f743e-135">By installing and allowing access to use of the bot, you agree to allow the LUIS service and Azure bot framework to process the intent behind the input,  which results in an enhanced conversational user experience.</span></span> <span data-ttu-id="f743e-136">Il servizio LUIS e il framework dei bot di Azure possono presentare livelli di conformità diversi rispetto a Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="f743e-136">The LUIS service and Azure bot framework may have varying levels of compliance compared to Dynamics 365 Human Resources.</span></span> <span data-ttu-id="f743e-137">Mentre il servizio LUIS ha accesso solo alle query dell'utente e non è progettato per essere collegato ai dati o all'account Dynamics 365 Human Resources dell'utente, un utente del bot Dynamics 365 Human Resources potrebbe inserire volontariamente una query contenente dati del cliente, dati personali o altri dati e tale contenuto della query potrebbe essere inviato al servizio LUIS e al framework del bot di Azure.</span><span class="sxs-lookup"><span data-stu-id="f743e-137">While the LUIS service has access to only the user queries and is not designed to be connected to the user’s Dynamics 365 Human Resources data or account, a user of the Dynamics 365 Human Resources bot could voluntarily enter a query containing Customer Data, Personal Data, or other data and such query content could get sent to the LUIS service and the Azure bot framework.</span></span> 

<span data-ttu-id="f743e-138">Il contenuto delle query e dei messaggi dell'utente viene conservato nel sistema LUIS per un massimo di 30 giorni, viene crittografato a riposo e non viene utilizzato per migliorare la formazione o il servizio.</span><span class="sxs-lookup"><span data-stu-id="f743e-138">The content of user’s queries and messages is retained in LUIS system for a maximum of 30 days, is encrypted at rest, and is not used for training or service improvement.</span></span> <span data-ttu-id="f743e-139">Ulteriori informazioni sui servizi cognitivi [qui](https://azure.microsoft.com/services/cognitive-services/language-understanding-intelligent-service/).</span><span class="sxs-lookup"><span data-stu-id="f743e-139">Read more about Cognitive Services [here](https://azure.microsoft.com/services/cognitive-services/language-understanding-intelligent-service/).</span></span> 

<span data-ttu-id="f743e-140">Per gestire le impostazioni di amministrazione per le app in Microsoft Teams, vai all'[interfaccia di amministrazione di Microsoft Teams](https://admin.teams.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="f743e-140">To manage admin settings for apps in Microsoft Teams, go to the [Microsoft Teams admin center](https://admin.teams.microsoft.com/).</span></span> 

## <a name="see-also"></a><span data-ttu-id="f743e-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f743e-141">See also</span></span> 

[<span data-ttu-id="f743e-142">Scaricare e installare Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f743e-142">Download and install Microsoft Teams</span></span>](https://support.office.com/article/download-and-install-microsoft-teams-422bf3aa-9ae8-46f1-83a2-e65720e1a34d)</br>
[<span data-ttu-id="f743e-143">Centro assistenza di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f743e-143">Microsoft Teams help center</span></span>](https://support.office.com/teams)</br>
[<span data-ttu-id="f743e-144">Gestire le richieste di congedo in Teams</span><span class="sxs-lookup"><span data-stu-id="f743e-144">Manage leave requests in Teams</span></span>](hr-teams-leave-app.md)

