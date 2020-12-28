---
title: Assegnare elenchi di attività a punti vendita o dipendenti
description: Questo argomento descrive come assegnare elenchi di attività a negozi o dipendenti in Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
manager: annbe
ms.date: 02/10/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.search.industry: ''
ms.author: gmohanv
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Release 10.0.9
ms.openlocfilehash: 82cec9861b759037f40315fb2e6f36002a0ac059
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4413522"
---
# <a name="assign-task-lists-to-stores-or-employees"></a><span data-ttu-id="35220-103">Assegnare elenchi di attività a punti vendita o dipendenti</span><span class="sxs-lookup"><span data-stu-id="35220-103">Assign task lists to stores or employees</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="35220-104">Questo argomento descrive come assegnare elenchi di attività a negozi o dipendenti in Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="35220-104">This topic describes how to assign task lists to stores or employees in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="35220-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="35220-105">Overview</span></span>

<span data-ttu-id="35220-106">La gestione delle attività in Dynamics 365 Commerce consente di assegnare un elenco di attività a più negozi o dipendenti o a una combinazione di negozi e dipendenti.</span><span class="sxs-lookup"><span data-stu-id="35220-106">Task management in Dynamics 365 Commerce lets you assign a task list to multiple stores or employees, or to a combination of stores and employees.</span></span> <span data-ttu-id="35220-107">Ad esempio, un responsabile regionale di 20 negozi potrebbe voler assegnare l'elenco attività **Preparazione delle festività** per tutti e 20 i negozi.</span><span class="sxs-lookup"><span data-stu-id="35220-107">For example, a regional manager for 20 stores might want to assign the **Holiday season preparation** task list to all 20 stores.</span></span>

## <a name="start-the-task-list-assignment-process"></a><span data-ttu-id="35220-108">Avviare il processo di assegnazione dell'elenco attività</span><span class="sxs-lookup"><span data-stu-id="35220-108">Start the task list assignment process</span></span>

<span data-ttu-id="35220-109">Per avviare il processo di assegnazione di un elenco di attività, attenersi alla seguente procedura.</span><span class="sxs-lookup"><span data-stu-id="35220-109">To start the process of assigning a task list, follow these steps.</span></span>

1. <span data-ttu-id="35220-110">Andare a **Retail e Commerce \> Gestione delle attività \> Amministrazione gestione delle attività**.</span><span class="sxs-lookup"><span data-stu-id="35220-110">Go to **Retail and Commerce \> Task management \> Task management administration**.</span></span>
1. <span data-ttu-id="35220-111">Selezionare l'elenco delle attività da assegnare.</span><span class="sxs-lookup"><span data-stu-id="35220-111">Select the task list to assign.</span></span>
1. <span data-ttu-id="35220-112">Selezionare **Avvia processo**.</span><span class="sxs-lookup"><span data-stu-id="35220-112">Select **Start process**.</span></span>
1. <span data-ttu-id="35220-113">Nella finestra di dialogo **Avvia processo**, nella scheda **Generale**, nel campo **Nome processo**, inserire un nome (ad esempio, **Negozi area orientale**).</span><span class="sxs-lookup"><span data-stu-id="35220-113">In the **Start process** dialog box, on the **General** tab, in the **Process name** field, enter a name (for example, **East region stores**).</span></span>
1. <span data-ttu-id="35220-114">Nel campo **Data stabilita** specificare una data.</span><span class="sxs-lookup"><span data-stu-id="35220-114">In the **Target date** field, specify a date.</span></span>
1. <span data-ttu-id="35220-115">Per assegnare l'elenco delle attività ai negozi, nella scheda **Punti vendita**, utilizzare il filtro **Gerarchia organizzativa** per trovare e selezionare i negozi.</span><span class="sxs-lookup"><span data-stu-id="35220-115">To assign the task list to stores, on the **Stores** tab, use the **Organization hierarchy** filter to find and select the stores.</span></span>

    <span data-ttu-id="35220-116">Per assegnare l'elenco delle attività ai dipendenti, nella scheda **Lavoratori** trovare e selezionare i dipendenti.</span><span class="sxs-lookup"><span data-stu-id="35220-116">To assign the task list to employees, on the **Workers** tab, find and select the employees.</span></span>

1. <span data-ttu-id="35220-117">Selezionare **OK** per avviare il processo.</span><span class="sxs-lookup"><span data-stu-id="35220-117">Select **OK** to start the process.</span></span> <span data-ttu-id="35220-118">L'elenco delle attività viene assegnato ai negozi o ai dipendenti selezionati.</span><span class="sxs-lookup"><span data-stu-id="35220-118">The tasks list is assigned to the selected stores or employees.</span></span>

<span data-ttu-id="35220-119">La seguente illustrazione mostra un esempio di come trovare e selezionare i negozi nella finestra di dialogo **Avvia processo**.</span><span class="sxs-lookup"><span data-stu-id="35220-119">The following illustration shows an example of how to find and select stores in the **Start process** dialog box.</span></span>

![Ricerca e selezione di punti vendita nella finestra di dialogo Avvia processo](media/HQ-Assign-Tasks-Lists.png)

## <a name="assign-task-lists-on-a-recurring-basis"></a><span data-ttu-id="35220-121">Assegnare gli elenchi attività su base ricorrente</span><span class="sxs-lookup"><span data-stu-id="35220-121">Assign task lists on a recurring basis</span></span>

<span data-ttu-id="35220-122">A volte i rivenditori hanno attività ricorrenti, come "Elenco di controllo per la chiusura di giovedì" o "Elenco di controllo per il primo giorno del mese".</span><span class="sxs-lookup"><span data-stu-id="35220-122">Retailer sometimes have recurrent tasks, such as "Thursday closure checklist" or "First day of the month checklist."</span></span> <span data-ttu-id="35220-123">Pertanto, potrebbero voler assegnare l'elenco delle attività su base ricorrente.</span><span class="sxs-lookup"><span data-stu-id="35220-123">Therefore, they might want to assign the task list on a recurring basis.</span></span>

1. <span data-ttu-id="35220-124">Andare a **Retail e Commerce \> Gestione delle attività \> Amministrazione gestione delle attività**.</span><span class="sxs-lookup"><span data-stu-id="35220-124">Go to **Retail and Commerce \> Task management \> Task management administration**.</span></span>
1. <span data-ttu-id="35220-125">Selezionare l'elenco delle attività da assegnare.</span><span class="sxs-lookup"><span data-stu-id="35220-125">Select the task list to assign.</span></span>
1. <span data-ttu-id="35220-126">Selezionare **Avvia processo**.</span><span class="sxs-lookup"><span data-stu-id="35220-126">Select **Start process**.</span></span>
1. <span data-ttu-id="35220-127">Nella finestra di dialogo **Avvia processo**, nella scheda **Generale**, nel campo **Nome processo**, inserire un nome.</span><span class="sxs-lookup"><span data-stu-id="35220-127">In the **Start process** dialog box, on the **General** tab, in the **Process name** field, enter a name.</span></span>
1. <span data-ttu-id="35220-128">Impostare l'opzione **Ricorrenza** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="35220-128">Set the **Recurrence** option to **Yes**.</span></span>
1. <span data-ttu-id="35220-129">Nel campo **Offset data destinazione ricorrenza in giorni**, immettere un numero di giorni.</span><span class="sxs-lookup"><span data-stu-id="35220-129">In the **Recurrence target date offset in days** field, enter a number of days.</span></span> <span data-ttu-id="35220-130">Ad esempio, se si immette **4**, la data stabilita è la data di ricorrenza più quattro giorni.</span><span class="sxs-lookup"><span data-stu-id="35220-130">For example, if you enter **4**, the target date is the recurrence date plus four days.</span></span>
1. <span data-ttu-id="35220-131">Nella scheda **Esecuzione in background** selezionare **Ricorrenza**.</span><span class="sxs-lookup"><span data-stu-id="35220-131">On the **Run in the background** tab, select **Recurrence**.</span></span>
1. <span data-ttu-id="35220-132">Nella finestra di dialogo **Definisci ricorrenza**, immettere i criteri di frequenza, quindi selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="35220-132">In the **Define recurrence** dialog box, enter the frequency criteria, and then select **OK**.</span></span>

<span data-ttu-id="35220-133">La seguente illustrazione mostra un esempio di come inserire i criteri di frequenza nella finestra di dialogo **Definisci ricorrenza**.</span><span class="sxs-lookup"><span data-stu-id="35220-133">The following illustration shows an example of how to enter frequency criteria in the **Define recurrence** dialog box.</span></span>

![Immettere i criteri di frequenza nella finestra di dialogo Definisci ricorrenza](media/HQ-Assign-Tasks-Lists-Recurrently.png)

## <a name="track-task-list-status"></a><span data-ttu-id="35220-135">Tenere traccia dello stato dell'elenco attività</span><span class="sxs-lookup"><span data-stu-id="35220-135">Track task list status</span></span>

<span data-ttu-id="35220-136">Se si è un responsabile di area o un gestore del negozio, si potrebbe voler tenere traccia dello stato degli elenchi di attività che sono stati assegnati a più negozi o dipendenti.</span><span class="sxs-lookup"><span data-stu-id="35220-136">If you're a regional manager or store manager, you might want to track the status of task lists that have been assigned to multiple stores or employees.</span></span> <span data-ttu-id="35220-137">È quindi possibile seguire i negozi o i lavoratori che non hanno completato le attività assegnate in tempo.</span><span class="sxs-lookup"><span data-stu-id="35220-137">You can then follow up with stores or workers that didn't complete their assigned tasks on time.</span></span> <span data-ttu-id="35220-138">Il back office di Commerce ti consente di visualizzare lo stato degli elenchi di attività, riassegnare le attività o modificare lo stato di un'attività.</span><span class="sxs-lookup"><span data-stu-id="35220-138">Commerce back office lets you view the status of task lists, reassign tasks, or change the status of a task.</span></span>

<span data-ttu-id="35220-139">Per tenere traccia dello stato dell'elenco attività per tutte le attività, attenersi alla seguente procedura.</span><span class="sxs-lookup"><span data-stu-id="35220-139">To track the task list status for all tasks, follow these steps.</span></span>

1. <span data-ttu-id="35220-140">Andare a **Retail e Commerce \> Gestione delle attività \> Processi gestione delle attività**.</span><span class="sxs-lookup"><span data-stu-id="35220-140">Go to **Retail and Commerce \> Task management \> Task management processes**.</span></span>
1. <span data-ttu-id="35220-141">Selezionare la scheda **Tutti gli elenchi di attività** per visualizzare lo stato di tutti gli elenchi di attività assegnati a vari negozi.</span><span class="sxs-lookup"><span data-stu-id="35220-141">Select the **All task lists** tab to view the status of all task lists that are assigned to various stores.</span></span>

<span data-ttu-id="35220-142">Per tenere traccia dello stato dell'elenco attività per tutte le attività assegnate all'utente corrente, attenersi alla seguente procedura.</span><span class="sxs-lookup"><span data-stu-id="35220-142">To track the task list status for all tasks that are assigned to you, follow these steps.</span></span>

1. <span data-ttu-id="35220-143">Andare a **Retail e Commerce \> Gestione delle attività \> Processi gestione delle attività**.</span><span class="sxs-lookup"><span data-stu-id="35220-143">Go to **Retail and Commerce \> Task management \> Task management processes**.</span></span>
1. <span data-ttu-id="35220-144">Selezionare la scheda **Attività personali** o **Tutte le attività** per visualizzare o aggiornare lo stato delle attività assegnate all'utente corrente.</span><span class="sxs-lookup"><span data-stu-id="35220-144">Select the **My tasks** or **All tasks** tab to view or update the status of tasks that are assigned to you.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="35220-145">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="35220-145">Additional resources</span></span>

[<span data-ttu-id="35220-146">Panoramica della gestione attività</span><span class="sxs-lookup"><span data-stu-id="35220-146">Task management overview</span></span>](task-mgmt-overview.md)

[<span data-ttu-id="35220-147">Configurare la gestione delle attività</span><span class="sxs-lookup"><span data-stu-id="35220-147">Configure task management</span></span>](task-mgmt-configure.md)

[<span data-ttu-id="35220-148">Creare elenchi di attività e aggiungere attività</span><span class="sxs-lookup"><span data-stu-id="35220-148">Create task lists and add tasks</span></span>](task-mgmt-create-lists.md)

[<span data-ttu-id="35220-149">Gestione delle attività in POS</span><span class="sxs-lookup"><span data-stu-id="35220-149">Task management in POS</span></span>](task-mgmt-POS.md)
