---
title: Sincronizzare la gestione delle attività tra POS di Microsoft Teams e Dynamics 365 Commerce
description: Questo argomento descrive come sincronizzare la gestione delle attività tra i POS Microsoft Teams e Dynamics 365 Commerce.
author: gvrmohanreddy
manager: annbe
ms.date: 03/31/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2021-01-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: ca0cb32ac3ee508ddcd5346a895fb9904fa92517
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5842692"
---
# <a name="synchronize-task-management-between-microsoft-teams-and-dynamics-365-commerce-pos"></a><span data-ttu-id="5acfa-103">Sincronizzare la gestione delle attività tra POS di Microsoft Teams e Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="5acfa-103">Synchronize task management between Microsoft Teams and Dynamics 365 Commerce POS</span></span>

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

<span data-ttu-id="5acfa-104">Questo argomento descrive come sincronizzare la gestione delle attività tra i POS Microsoft Teams e Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="5acfa-104">This topic describes how to synchronize task management between Microsoft Teams and Dynamics 365 Commerce point of sale (POS).</span></span>

<span data-ttu-id="5acfa-105">Uno degli scopi principali dell'integrazione di Teams è abilitare la sincronizzazione della gestione delle attività tra l'applicazione POS e Teams.</span><span class="sxs-lookup"><span data-stu-id="5acfa-105">One of the main purposes of Teams integration is to enable the synchronization of task management between the POS application and Teams.</span></span> <span data-ttu-id="5acfa-106">In questo modo, i dipendenti del negozio possono utilizzare l'applicazione POS o Teams per gestire le attività e non devono cambiare applicazione.</span><span class="sxs-lookup"><span data-stu-id="5acfa-106">In this way, store employees can use either the POS application or Teams to manage tasks, and don't have to switch applications.</span></span>

<span data-ttu-id="5acfa-107">Poiché Planner viene usato come repository per le attività in Teams, deve esserci un collegamento tra Teams e Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="5acfa-107">Because Planner is used as a repository for tasks in Teams, there must be a link between Teams and Dynamics 365 Commerce.</span></span> <span data-ttu-id="5acfa-108">Questo collegamento viene stabilito utilizzando un ID piano specifico per un determinato team del negozio.</span><span class="sxs-lookup"><span data-stu-id="5acfa-108">This link is established by using a specific plan ID for a given store team.</span></span>

<span data-ttu-id="5acfa-109">Le procedure seguenti mostrano come configurare la sincronizzazione della gestione delle attività tra le applicazioni POS e Teams.</span><span class="sxs-lookup"><span data-stu-id="5acfa-109">The following procedures show how to set up task management synchronization between the POS and Teams applications.</span></span>

## <a name="publish-a-test-task-list-in-teams"></a><span data-ttu-id="5acfa-110">Pubblicare un elenco di attività di test in Teams</span><span class="sxs-lookup"><span data-stu-id="5acfa-110">Publish a test task list in Teams</span></span>

<span data-ttu-id="5acfa-111">La procedura seguente presuppone che i team del tuo negozio stiano utilizzando l'integrazione della gestione delle attività di Microsoft Teams con Commerce per la prima volta.</span><span class="sxs-lookup"><span data-stu-id="5acfa-111">The following procedure assumes that your store teams are using Microsoft Teams task management integration with Commerce for the first time.</span></span>

<span data-ttu-id="5acfa-112">Per pubblicare un elenco di attività di test in Teams, attieniti alla seguente procedura.</span><span class="sxs-lookup"><span data-stu-id="5acfa-112">To publish a test task list in Teams, follow these steps.</span></span>

1. <span data-ttu-id="5acfa-113">Accedi a Teams come responsabile delle comunicazioni.</span><span class="sxs-lookup"><span data-stu-id="5acfa-113">Sign in to Teams as a communications manager.</span></span> <span data-ttu-id="5acfa-114">In genere, i responsabili delle comunicazioni sono utenti che hanno il ruolo **responsabile regionale** in Commerce.</span><span class="sxs-lookup"><span data-stu-id="5acfa-114">Typically, communications managers are users who have the **Regional manager** role in Commerce.</span></span>
1. <span data-ttu-id="5acfa-115">Nel riquadro di spostamento a sinistra, seleziona **Attività di Planner**.</span><span class="sxs-lookup"><span data-stu-id="5acfa-115">In the left navigation pane, select **Tasks by Planner**.</span></span>
1. <span data-ttu-id="5acfa-116">Nella scheda **Elenchi pubblicati** seleziona **Nuovo elenco** in basso a sinistra e assegna al nuovo elenco il nome **Elenco delle attività di test**.</span><span class="sxs-lookup"><span data-stu-id="5acfa-116">On the **Published lists** tab, select **New list** in the lower left, and name the new list **Test task list**.</span></span>
1. <span data-ttu-id="5acfa-117">Selezionare **Crea**.</span><span class="sxs-lookup"><span data-stu-id="5acfa-117">Select **Create**.</span></span> <span data-ttu-id="5acfa-118">Il nuovo elenco viene visualizzato sotto **Bozze**.</span><span class="sxs-lookup"><span data-stu-id="5acfa-118">The new list appears under **Drafts**.</span></span>
1. <span data-ttu-id="5acfa-119">Sotto **Titolo attività**, assegna alla prima attività il titolo **Integrazione di Teams di test**.</span><span class="sxs-lookup"><span data-stu-id="5acfa-119">Under **Task title**, give the first task the title **Testing Teams integration**.</span></span> <span data-ttu-id="5acfa-120">Quindi seleziona **Immetti**.</span><span class="sxs-lookup"><span data-stu-id="5acfa-120">Then select **Enter**.</span></span>
1. <span data-ttu-id="5acfa-121">Nell'elenco **Bozze** seleziona l'elenco delle attività.</span><span class="sxs-lookup"><span data-stu-id="5acfa-121">In the **Drafts** list, select the task list.</span></span> <span data-ttu-id="5acfa-122">Quindi seleziona  **Pubblica**  nell'angolo in alto a destra.</span><span class="sxs-lookup"><span data-stu-id="5acfa-122">Then select **Publish** in the upper-right corner.</span></span>
1. <span data-ttu-id="5acfa-123">Nella finestra di dialogo **Seleziona per chi pubblicare** seleziona i team che devono ricevere l'elenco delle attività di test.</span><span class="sxs-lookup"><span data-stu-id="5acfa-123">In the **Select who to publish to** dialog box, select the teams that should receive the test task list.</span></span>
1. <span data-ttu-id="5acfa-124">Seleziona **Avanti** per rivedere il tuo piano di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="5acfa-124">Select **Next** to review your publication plan.</span></span> <span data-ttu-id="5acfa-125">Se è necessario apportare modifiche, seleziona  **Indietro**.</span><span class="sxs-lookup"><span data-stu-id="5acfa-125">If you must make changes, select **Back**.</span></span> 
1. <span data-ttu-id="5acfa-126">Seleziona **Conferma per procedere** e quindi seleziona **Pubblica**.</span><span class="sxs-lookup"><span data-stu-id="5acfa-126">Select **Confirm to proceed**, and then select **Publish**.</span></span>
1. <span data-ttu-id="5acfa-127">Al termine della pubblicazione, viene visualizzato un messaggio nella parte superiore della scheda **Elenchi pubblicati** indica se l'elenco delle attività è stato consegnato correttamente.</span><span class="sxs-lookup"><span data-stu-id="5acfa-127">After publishing is completed, a message at the top of the **Published lists** tab indicates whether your task list was successfully delivered.</span></span>

<span data-ttu-id="5acfa-128">Per ulteriori informazioni, vedi [Pubblicare gli elenchi di attività per creare e monitorare il lavoro nell'organizzazione](https://support.microsoft.com/office/publish-task-lists-to-create-and-track-work-in-your-organization-095409b3-f5af-40aa-9f9e-339b54e705df).</span><span class="sxs-lookup"><span data-stu-id="5acfa-128">For more information, see [Publish task lists to create and track work in your organization](https://support.microsoft.com/office/publish-task-lists-to-create-and-track-work-in-your-organization-095409b3-f5af-40aa-9f9e-339b54e705df).</span></span>

## <a name="link-pos-and-teams-for-task-management"></a><span data-ttu-id="5acfa-129">Collegare POS e Teams per la gestione delle attività</span><span class="sxs-lookup"><span data-stu-id="5acfa-129">Link POS and Teams for task management</span></span>

<span data-ttu-id="5acfa-130">Per collegare le applicazioni POS e Microsoft Teams per la gestione delle attività in Commerce headquarters, segui questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="5acfa-130">To link the POS and Microsoft Teams applications for task management in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="5acfa-131">Vai a **Retail e Commerce \> Gestione delle attività \> Integrazione di attività con Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="5acfa-131">Go to **Retail and Commerce \> Task management \> Tasks integration with Microsoft Teams**.</span></span>
1. <span data-ttu-id="5acfa-132">Nel riquadro azioni, seleziona **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="5acfa-132">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="5acfa-133">Imposta l'opzione **Abilita l'integrazione di gestione delle attività** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="5acfa-133">Set the **Enable Task Management Integration** option to **Yes**.</span></span>
1. <span data-ttu-id="5acfa-134">Nel riquadro azioni selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="5acfa-134">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="5acfa-135">Nel riquadro azioni seleziona **Imposta gestione delle attività**.</span><span class="sxs-lookup"><span data-stu-id="5acfa-135">On the Action Pane, select **Setup task management**.</span></span> <span data-ttu-id="5acfa-136">Ricevi una notifica che indica che un processo batch denominato **Provisioning di Team** è in fase di creazione.</span><span class="sxs-lookup"><span data-stu-id="5acfa-136">You should receive a notification that indicates that a batch job that is named **Teams provision** is being created.</span></span>
1. <span data-ttu-id="5acfa-137">Vai a **Amministrazione sistema \> Richieste di informazioni \> Processi batch** e trova il processo più recente con la descrizione **Provisioning di Team**.</span><span class="sxs-lookup"><span data-stu-id="5acfa-137">Go to **System administration \> Inquiries \> Batch jobs**, and find the most recent job that has the description **Teams provision**.</span></span> <span data-ttu-id="5acfa-138">Attendi fino al termine dell'esecuzione di questo processo.</span><span class="sxs-lookup"><span data-stu-id="5acfa-138">Wait until this job has finished running.</span></span>
1. <span data-ttu-id="5acfa-139">Corri il **processo CDX 1070** per pubblicare l'ID del piano e memorizzare i riferimenti a Retail Server.</span><span class="sxs-lookup"><span data-stu-id="5acfa-139">Run the **CDX job 1070** to publish the plan ID and store references to Retail Server.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="5acfa-140">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="5acfa-140">Additional resources</span></span>

[<span data-ttu-id="5acfa-141">Panoramica dell'integrazione di Dynamics 365 Commerce e Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5acfa-141">Dynamics 365 Commerce and Microsoft Teams integration overview</span></span>](commerce-teams-integration.md)

[<span data-ttu-id="5acfa-142">Abilitare l'integrazione di Dynamics 365 Commerce e Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5acfa-142">Enable Dynamics 365 Commerce and Microsoft Teams integration</span></span>](enable-teams-integration.md)

[<span data-ttu-id="5acfa-143">Provisioning di Microsoft Teams da Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="5acfa-143">Provision Microsoft Teams from Dynamics 365 Commerce</span></span>](provision-teams-from-commerce.md)

[<span data-ttu-id="5acfa-144">Gestire i ruoli utente in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5acfa-144">Manage user roles in Microsoft Teams</span></span>](manage-user-roles-teams.md)

[<span data-ttu-id="5acfa-145">Mappare negozi e team se ci sono team preesistenti in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5acfa-145">Map stores and teams if there are pre-existing teams in Microsoft Teams</span></span>](map-stores-existing-teams.md)

[<span data-ttu-id="5acfa-146">Domande frequenti sull'integrazione di Dynamics 365 Commerce e Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5acfa-146">Dynamics 365 Commerce and Microsoft Teams integration FAQ</span></span>](teams-integration-faq.md)
