---
title: Configurare la gestione delle attività
description: Questo argomento descrive come configurare le funzionalità di gestione delle attività in Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
manager: annbe
ms.date: 02/10/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: gmohanv
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Release 10.0.9
ms.openlocfilehash: ba2283bbfa2fdce75d3fbef6fcff47dd872c7998
ms.sourcegitcommit: c88b54ba13a4dfe39b844ffaced4dc435560c47d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2021
ms.locfileid: "5478046"
---
# <a name="configure-task-management"></a><span data-ttu-id="bc767-103">Configurare la gestione delle attività</span><span class="sxs-lookup"><span data-stu-id="bc767-103">Configure task management</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="bc767-104">Questo argomento descrive come configurare le funzionalità di gestione delle attività in Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="bc767-104">This topic describes how to configure task management features in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="bc767-105">Prima che i manager e i dipendenti Dynamics 365 Commerce possano utilizzare le funzionalità di gestione delle attività in Commerce, la gestione delle attività deve essere configurata.</span><span class="sxs-lookup"><span data-stu-id="bc767-105">Before Dynamics 365 Commerce managers and employees can use the task management features in Commerce, task management must be configured.</span></span> <span data-ttu-id="bc767-106">I passaggi della configurazione includono la concessione di autorizzazioni a manager e dipendenti, la distribuzione delle autorizzazioni ai clienti del punto vendita (POS), l'impostazione delle notifiche POS e la configurazione del riquadro **Attività** sulla home page di un'applicazione POS.</span><span class="sxs-lookup"><span data-stu-id="bc767-106">Configuration steps include granting permissions to managers and employees, distributing permissions to point of sale (POS) clients, setting up POS notifications, and configuring the **Tasks** tile on the home page of a POS application.</span></span>

## <a name="configure-permissions-for-store-managers"></a><span data-ttu-id="bc767-107">Configurare le autorizzazioni per i responsabili punto vendita</span><span class="sxs-lookup"><span data-stu-id="bc767-107">Configure permissions for store managers</span></span>

<span data-ttu-id="bc767-108">Ogni addetto in un determinato negozio può visualizzare tutte le attività assegnate a quel negozio.</span><span class="sxs-lookup"><span data-stu-id="bc767-108">Every worker in a given store can view all tasks that are assigned to that store.</span></span> <span data-ttu-id="bc767-109">Possono anche aggiornare lo stato delle attività loro assegnate.</span><span class="sxs-lookup"><span data-stu-id="bc767-109">They can also update the status of the tasks that are assigned to them.</span></span> <span data-ttu-id="bc767-110">Tuttavia, i gestori di negozi devono disporre delle autorizzazioni di gestione delle attività per gestire le attività assegnate al negozio e per creare attività con unico scopo.</span><span class="sxs-lookup"><span data-stu-id="bc767-110">However, personas such as store managers must have task management permissions to manage tasks that are assigned to the store and to create single-purpose tasks.</span></span>

<span data-ttu-id="bc767-111">Per configurare le autorizzazioni di gestione delle attività per i gestori del negozio, attenersi alla seguente procedura.</span><span class="sxs-lookup"><span data-stu-id="bc767-111">To configure task management permissions for store managers, follow these steps.</span></span>

1. <span data-ttu-id="bc767-112">Passare a **Retail e Commerce \> Dipendenti \> Gruppi di autorizzazioni**.</span><span class="sxs-lookup"><span data-stu-id="bc767-112">Go to **Retail and Commerce \> Employees \> Permission groups**.</span></span>
1. <span data-ttu-id="bc767-113">Selezionare un gruppo di autorizzazioni specifico (ad esempio, **Manager**), quindi selezionare **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="bc767-113">Select a specific permission group (for example, **Manager**), and then select **Edit**.</span></span>
1. <span data-ttu-id="bc767-114">Nella scheda dettaglio **Autorizzazioni**, impostare l'opzione **Consenti gestione attività** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="bc767-114">On the **Permissions** FastTab, set the **Allow task management** option to **Yes**.</span></span>
1. <span data-ttu-id="bc767-115">Nella scheda dettaglio **Notifiche** aggiungere l'operazione **Gestione attività** e immettere un valore nel campo **Ordine di visualizzazione**.</span><span class="sxs-lookup"><span data-stu-id="bc767-115">On the **Notifications** FastTab, add the **Task management** operation, and enter a value in the **Display order** field.</span></span> <span data-ttu-id="bc767-116">Ad esempio, inserire **2** se l'operazione **Evasione ordine** ha già un valore **Ordine di visualizzazione** di **1**.</span><span class="sxs-lookup"><span data-stu-id="bc767-116">For example, enter **2** if the **Order fulfillment** operation already has a **Display order** value of **1**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="bc767-117">Se una persona non responsabile deve disporre delle autorizzazioni di gestione attività nel POS, è possibile concedere l'autorizzazione alla persona.</span><span class="sxs-lookup"><span data-stu-id="bc767-117">If a non-manager persona must have task management permissions in the POS, you can grant permission to the individual.</span></span> <span data-ttu-id="bc767-118">In alternativa, è possibile creare un nuovo gruppo di autorizzazioni per i non gestori e impostare l'opzione **Consenti gestione attività** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="bc767-118">Alternatively, you can create a new permission group for non-managers and set the **Allow task management** option to **Yes**.</span></span>

<span data-ttu-id="bc767-119">La seguente illustrazione mostra come configurare le autorizzazioni di gestione delle attività per i gestori del negozio.</span><span class="sxs-lookup"><span data-stu-id="bc767-119">The following illustration shows how to configure task management permissions for store managers.</span></span>

![Configurazione delle autorizzazioni di gestione delle attività per i gestori del negozio](media/HQ-POS-Tasks-Notifications-User-Permission.png)

## <a name="configure-permissions-for-employees"></a><span data-ttu-id="bc767-121">Configurare le autorizzazioni per i dipendenti</span><span class="sxs-lookup"><span data-stu-id="bc767-121">Configure permissions for employees</span></span>

<span data-ttu-id="bc767-122">I dipendenti devono disporre delle autorizzazioni per creare elenchi di attività, gestire criteri di assegnazione e configurare la ricorrenza di qualsiasi elenco di attività.</span><span class="sxs-lookup"><span data-stu-id="bc767-122">Employees must have permissions to create task lists, manage assignment criteria, and configure the recurrence of any task list.</span></span> <span data-ttu-id="bc767-123">Per configurare queste autorizzazioni, si assegnano i dipendenti al ruolo **Responsabile attività vendita al dettaglio**.</span><span class="sxs-lookup"><span data-stu-id="bc767-123">To configure these permissions, you assign employees to the **Retail task manager** role.</span></span>

<span data-ttu-id="bc767-124">Per configurare le autorizzazioni per un dipendente, effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="bc767-124">To configure permissions for an employee, follow these steps.</span></span>

1. <span data-ttu-id="bc767-125">Passare a **Retail e Commerce \> Dipendenti \> Utenti**.</span><span class="sxs-lookup"><span data-stu-id="bc767-125">Go to **Retail and Commerce \> Employees \> Users**.</span></span>
1. <span data-ttu-id="bc767-126">Selezionare un dipendente.</span><span class="sxs-lookup"><span data-stu-id="bc767-126">Select an employee.</span></span>
1. <span data-ttu-id="bc767-127">Nella scheda dettaglio **Ruoli utente**, selezionare **Assegna ruoli**.</span><span class="sxs-lookup"><span data-stu-id="bc767-127">On the **User's roles** FastTab, select **Assign roles**.</span></span>
1. <span data-ttu-id="bc767-128">Nella finestra di dialogo **Assegna ruoli all'utente** selezionare il ruolo **Responsabile attività vendita al dettaglio**, quindi selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="bc767-128">In the **Assign roles to user** dialog box, select the **Retail task manager** role, and then select **OK**.</span></span>

## <a name="distribute-permissions-to-pos-clients"></a><span data-ttu-id="bc767-129">Distribuire le autorizzazioni ai client POS</span><span class="sxs-lookup"><span data-stu-id="bc767-129">Distribute permissions to POS clients</span></span>

<span data-ttu-id="bc767-130">Prima che i dipendenti possano utilizzare i client POS, le autorizzazioni devono essere distribuite e sincronizzate con i client.</span><span class="sxs-lookup"><span data-stu-id="bc767-130">Before employees can use POS clients, permissions must be distributed and synced to those clients.</span></span>

<span data-ttu-id="bc767-131">Per distribuire le autorizzazioni ai client POS, attenersi alla seguente procedura.</span><span class="sxs-lookup"><span data-stu-id="bc767-131">To distribute permissions to POS clients, follow these steps.</span></span>

1. <span data-ttu-id="bc767-132">Selezionare **Retail e Commerce \> Vendita al dettaglio e commercio IT \> Programmazione della distribuzione**.</span><span class="sxs-lookup"><span data-stu-id="bc767-132">Go to **Retail and Commerce \> Retail and Commerce IT \> Distribution schedule**.</span></span>
1. <span data-ttu-id="bc767-133">Selezionare la programmazione della distribuzione **1060** (**Personale**), quindi selezionare **Esegui adesso**.</span><span class="sxs-lookup"><span data-stu-id="bc767-133">Select the **1060** (**Staff**) distribution schedule, and then select **Run now**.</span></span>
1. <span data-ttu-id="bc767-134">Selezionare la programmazione della distribuzione **1070** (**Configurazione canale**), quindi selezionare **Esegui adesso**.</span><span class="sxs-lookup"><span data-stu-id="bc767-134">Select the **1070** (**Channel configuration**) distribution schedule, and then select **Run now**.</span></span>

## <a name="configure-pos-notifications-for-tasks"></a><span data-ttu-id="bc767-135">Configurare le notifiche POS per le attività</span><span class="sxs-lookup"><span data-stu-id="bc767-135">Configure POS notifications for tasks</span></span>

<span data-ttu-id="bc767-136">La gestione delle attività deve essere configurata in modo tale che le notifiche siano disponibili nell'applicazione POS.</span><span class="sxs-lookup"><span data-stu-id="bc767-136">Task management must be configured so that notifications are available in the POS application.</span></span>

<span data-ttu-id="bc767-137">Per configurare le notifiche POS per le attività, effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="bc767-137">To configure POS notifications for tasks, follow these steps.</span></span>

1. <span data-ttu-id="bc767-138">Passare a **Retail e Commerce \> Impostazione canale \> Impostazione POS \> POS \> Operazioni POS**.</span><span class="sxs-lookup"><span data-stu-id="bc767-138">Go to **Retail and Commerce \> Channel setup \> POS setup \> POS \> POS operations**.</span></span>
1. <span data-ttu-id="bc767-139">Trovare l'operazione **1400** (**Gestione delle attività**) e selezionare la casella di controllo **Abilita notifiche**.</span><span class="sxs-lookup"><span data-stu-id="bc767-139">Find operation **1400** (**Task management**), and select the **Enable notifications** check box for it.</span></span>

<span data-ttu-id="bc767-140">La seguente illustrazione mostra l'operazione **Gestione delle attività** nella pagina **Operazioni POS**.</span><span class="sxs-lookup"><span data-stu-id="bc767-140">The following illustration shows the **Task management** operation on the **POS operations** page.</span></span>

![Operazione di gestione delle attività nella pagina Operazioni POS](media/HQ-POS-Tasks-Notifications.png)

<span data-ttu-id="bc767-142">Per ulteriori informazioni su come configurare le notifiche POS, vedere [Visualizzare le notifiche degli ordini nel POS](notifications-pos.md).</span><span class="sxs-lookup"><span data-stu-id="bc767-142">For more information about how to configure POS notifications, see [Show order notifications in the point of sale (POS)](notifications-pos.md).</span></span>

## <a name="configure-the-tasks-tile-on-a-pos-application-home-page"></a><span data-ttu-id="bc767-143">Configurare il riquadro Attività in una home page dell'applicazione POS</span><span class="sxs-lookup"><span data-stu-id="bc767-143">Configure the Tasks tile on a POS application home page</span></span>

<span data-ttu-id="bc767-144">Prima di configurare il riquadro **Attività** sulla home page di un'applicazione POS, vedere [Layout delle schermate per il POS](pos-screen-layouts.md) per informazioni su come configurare e aggiungere nuovi pulsanti a un layout di schermata POS.</span><span class="sxs-lookup"><span data-stu-id="bc767-144">Before you configure the **Tasks** tile on the home page of a POS application, see [Screen layouts for the point of sale (POS)](pos-screen-layouts.md) for information about how to configure and add new buttons to a POS screen layout.</span></span>

<span data-ttu-id="bc767-145">Per configurare il riquadro **Attività** in una home page dell'applicazione POS, attenersi alla procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="bc767-145">To configure the **Tasks** tile on a POS application home page, follow these steps.</span></span>

1. <span data-ttu-id="bc767-146">Passare a **Retail e Commerce \> Impostazione canale \> Impostazione POS \> POS \> Layout schermo**.</span><span class="sxs-lookup"><span data-stu-id="bc767-146">Go to **Retail and Commerce \> Channel setup \> POS setup \> POS \> Screen layouts**.</span></span>
1. <span data-ttu-id="bc767-147">Selezionare un layout dello schermo, selezionare una dimensione del layout e selezionare una griglia di pulsanti.</span><span class="sxs-lookup"><span data-stu-id="bc767-147">Select a screen layout, select a layout size, and select a button grid.</span></span>
1. <span data-ttu-id="bc767-148">Nella scheda dettaglio **Griglie dei pulsanti**, selezionare **Progettazione** per modificare la griglia dei pulsanti selezionata.</span><span class="sxs-lookup"><span data-stu-id="bc767-148">On the **Button grids** FastTab, select **Designer** to edit the selected button grid.</span></span>
1. <span data-ttu-id="bc767-149">Aggiungere un riquadro **Attività** alla sezione appropriata della home page.</span><span class="sxs-lookup"><span data-stu-id="bc767-149">Add a **Tasks** tile to the appropriate section of the home page.</span></span>

<span data-ttu-id="bc767-150">Nella figura seguente è illustrato un esempio di un riquadro **Attività** nella home page del POS.</span><span class="sxs-lookup"><span data-stu-id="bc767-150">The following illustration shows an example of a **Tasks** tile on a POS home page.</span></span>

![Riquadro attività in una home page del POS](media/POS-home-screen-tasks-button-image.png)

## <a name="additional-resources"></a><span data-ttu-id="bc767-152">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="bc767-152">Additional resources</span></span>

[<span data-ttu-id="bc767-153">Panoramica della gestione attività</span><span class="sxs-lookup"><span data-stu-id="bc767-153">Task management overview</span></span>](task-mgmt-overview.md)

[<span data-ttu-id="bc767-154">Creare elenchi di attività e aggiungere attività</span><span class="sxs-lookup"><span data-stu-id="bc767-154">Create task lists and add tasks</span></span>](task-mgmt-create-lists.md)

[<span data-ttu-id="bc767-155">Assegnare elenchi di attività a punti vendita o dipendenti</span><span class="sxs-lookup"><span data-stu-id="bc767-155">Assign task lists to stores or employees</span></span>](task-mgmt-assign-lists.md)

[<span data-ttu-id="bc767-156">Gestione delle attività in POS</span><span class="sxs-lookup"><span data-stu-id="bc767-156">Task management in POS</span></span>](task-mgmt-POS.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
