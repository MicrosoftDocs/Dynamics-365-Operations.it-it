---
title: Creare elenchi di attività e aggiungere attività
description: Questo argomento descrive come creare elenchi di attività e aggiungervi le attività in Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
manager: annbe
ms.date: 02/10/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.search.industry: ''
ms.author: gmohanv
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Release 10.0.9
ms.openlocfilehash: 1cab31784db9f3242dce20e98762088436a5a8f8
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4413519"
---
# <a name="create-task-lists-and-add-tasks"></a><span data-ttu-id="e4d65-103">Creare elenchi di attività e aggiungere attività</span><span class="sxs-lookup"><span data-stu-id="e4d65-103">Create task lists and add tasks</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="e4d65-104">Questo argomento descrive come creare elenchi di attività e aggiungervi le attività in Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="e4d65-104">This topic describes how to create task lists and add tasks to them in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="e4d65-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="e4d65-105">Overview</span></span>

<span data-ttu-id="e4d65-106">Un'*attività* definisce un lavoro specifico o un'azione che qualcuno deve completare entro una data di scadenza specificata.</span><span class="sxs-lookup"><span data-stu-id="e4d65-106">A *task* defines a specific piece of work or an action that someone must complete on or before a specified due date.</span></span> <span data-ttu-id="e4d65-107">In Dynamics 365 Commerce, un'attività può includere istruzioni dettagliate e informazioni su una persona di contatto.</span><span class="sxs-lookup"><span data-stu-id="e4d65-107">In Dynamics 365 Commerce, a task can include detailed instructions and information about a contact person.</span></span> <span data-ttu-id="e4d65-108">Può anche includere i collegamenti a operazioni di back-office, operazioni di punti vendita (POS) o pagine del sito, per contribuire a migliorare la produttività e fornire il contesto richiesto dal proprietario dell'attività per completare l'attività in modo efficiente.</span><span class="sxs-lookup"><span data-stu-id="e4d65-108">It can also include links to back-office operations, point of sale (POS) operations, or site pages, to help improve productivity and provide the context that the task owner requires to complete the task efficiently.</span></span>

<span data-ttu-id="e4d65-109">Un *elenco delle attività* è una raccolta di attività che devono essere completate come parte di un processo aziendale.</span><span class="sxs-lookup"><span data-stu-id="e4d65-109">A *task list* is a collection of tasks that must be completed as part of a business process.</span></span> <span data-ttu-id="e4d65-110">Ad esempio, potrebbe esserci un elenco di attività che un nuovo lavoratore deve completare durante l'inserimento, un elenco di attività per cassieri che lavorano in turni serali o un elenco di attività che devono essere completate per preparare il negozio per le prossime festività.</span><span class="sxs-lookup"><span data-stu-id="e4d65-110">For example, there might be a task list that a new worker must complete during onboarding, a task list for cashiers who work evening shifts, or a task list that must be completed to prepare the store for an upcoming holiday season.</span></span> <span data-ttu-id="e4d65-111">In Commerce, ogni elenco di attività che ha una data stabilita può essere assegnata a un numero qualsiasi di negozi o dipendenti e può essere configurata come ricorrente.</span><span class="sxs-lookup"><span data-stu-id="e4d65-111">In Commerce, every task list that has a target date can be assigned to any number of stores or employees, and it can be configured to recur.</span></span>

<span data-ttu-id="e4d65-112">Sia i manager che i lavoratori possono creare elenchi di attività nel back office di Commerce e quindi assegnarli a un set di negozi.</span><span class="sxs-lookup"><span data-stu-id="e4d65-112">Both managers and workers can create task lists in Commerce back office, and then assign them to a set of stores.</span></span>

## <a name="create-a-task-list"></a><span data-ttu-id="e4d65-113">Creare un elenco di attività</span><span class="sxs-lookup"><span data-stu-id="e4d65-113">Create a task list</span></span>

<span data-ttu-id="e4d65-114">Per creare un elenco di attività, completare i passaggi che seguono.</span><span class="sxs-lookup"><span data-stu-id="e4d65-114">To create a task list, follow these steps.</span></span>

1. <span data-ttu-id="e4d65-115">Andare a **Retail e Commerce \> Gestione delle attività \> Amministrazione gestione delle attività**.</span><span class="sxs-lookup"><span data-stu-id="e4d65-115">Go to **Retail and Commerce \> Task management \> Task management administration**.</span></span>
1. <span data-ttu-id="e4d65-116">Selezionare **Nuovo**, quindi immettere i valori nei campi **Nome**, **Descrizione** e **Proprietario**.</span><span class="sxs-lookup"><span data-stu-id="e4d65-116">Select **New**, and then enter values in the **Name**, **Description**, and **Owner** fields.</span></span>
1. <span data-ttu-id="e4d65-117">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="e4d65-117">Select **Save**.</span></span>

## <a name="add-tasks-to-a-task-list"></a><span data-ttu-id="e4d65-118">Aggiungere attività a un elenco di attività</span><span class="sxs-lookup"><span data-stu-id="e4d65-118">Add tasks to a task list</span></span>

<span data-ttu-id="e4d65-119">Per aggiungere attività a un elenco di attività, effettuare le operazioni indicate di seguito.</span><span class="sxs-lookup"><span data-stu-id="e4d65-119">To add tasks to a task list, follow these steps.</span></span>
 
1. <span data-ttu-id="e4d65-120">Nella scheda dettaglio **Attività** di un elenco attività esistente, selezionare **Nuovo** per aggiungere un'attività.</span><span class="sxs-lookup"><span data-stu-id="e4d65-120">On the **Tasks** FastTab of an existing task list, select **New** to add a task.</span></span>
1. <span data-ttu-id="e4d65-121">Nella finestra di dialogo **Crea una nuova attività**, nel campo **Nome** immettere un nome per l'attività.</span><span class="sxs-lookup"><span data-stu-id="e4d65-121">In the **Create a new task** dialog box, in the **Name** field, enter a name for the task.</span></span>
1. <span data-ttu-id="e4d65-122">Nel campo **Offset data di scadenza da data stabilita**, immettere un valore intero positivo o negativo.</span><span class="sxs-lookup"><span data-stu-id="e4d65-122">In the **Due data offset from target date** field, enter a positive or negative integer value.</span></span> <span data-ttu-id="e4d65-123">Ad esempio, immettere **-2** se l'attività deve essere completata due giorni prima della data di scadenza dell'elenco attività.</span><span class="sxs-lookup"><span data-stu-id="e4d65-123">For example, enter **-2** if the task should be completed two days before the task list's due date.</span></span>
1. <span data-ttu-id="e4d65-124">Nel campo **Note** inserire le istruzioni dettagliate.</span><span class="sxs-lookup"><span data-stu-id="e4d65-124">In the **Notes** field, enter detailed instructions.</span></span>
1. <span data-ttu-id="e4d65-125">Nel campo **Contatto** immettere il nome di un esperto in materia che il proprietario dell'attività può contattare se ha bisogno di aiuto.</span><span class="sxs-lookup"><span data-stu-id="e4d65-125">In the **Contact person** field, enter the name of a subject matter expert that the task owner can contact if he or she needs help.</span></span>
1. <span data-ttu-id="e4d65-126">Nel campo **Collegamento attività** immettere un collegamento, in base alla natura dell'attività.</span><span class="sxs-lookup"><span data-stu-id="e4d65-126">In the **Task link** field, enter a link, based on the nature of the task.</span></span>

> [!TIP]
> <span data-ttu-id="e4d65-127">Sebbene sia possibile utilizzare il campo **Assegnato a** per assegnare l'attività a qualcuno durante la creazione di un elenco di attività, si consiglia di evitare di assegnare l'attività durante la creazione dell'elenco di attività.</span><span class="sxs-lookup"><span data-stu-id="e4d65-127">Although you can use the **Assigned to** field to assign tasks to someone while you're creating a task list, we recommend that you avoid assigning tasks during task list creation.</span></span> <span data-ttu-id="e4d65-128">Assegnare invece le attività dopo che è stata creata un'istanza dell'elenco per i singoli negozi.</span><span class="sxs-lookup"><span data-stu-id="e4d65-128">Instead, assign the tasks after the list is instantiated for individual stores.</span></span>

## <a name="use-task-links-to-help-improve-worker-productivity"></a><span data-ttu-id="e4d65-129">Utilizzare i collegamenti delle attività per migliorare la produttività dei lavoratori</span><span class="sxs-lookup"><span data-stu-id="e4d65-129">Use task links to help improve worker productivity</span></span>

<span data-ttu-id="e4d65-130">Commerce consente di collegare attività a specifiche operazioni POS, come l'esecuzione del report sulle vendite, la visualizzazione di un video di formazione online per l'orientamento di nuovi dipendenti o l'esecuzione di un'operazione di back-office.</span><span class="sxs-lookup"><span data-stu-id="e4d65-130">Commerce lets you link tasks to specific POS operations, such as running a sales report, viewing an online training video for new employee orientation, or performing a back-office operation.</span></span> <span data-ttu-id="e4d65-131">Questa funzione consente ai proprietari di attività di ottenere le informazioni necessarie per completare un'attività in modo efficiente.</span><span class="sxs-lookup"><span data-stu-id="e4d65-131">This feature helps task owners get the information that they need to complete a task efficiently.</span></span>

<span data-ttu-id="e4d65-132">Per aggiungere i collegamenti di attività mentre si crea un'attività, attenersi alla seguente procedura.</span><span class="sxs-lookup"><span data-stu-id="e4d65-132">To add task links while you create a task, follow these steps.</span></span>

1. <span data-ttu-id="e4d65-133">Nella scheda dettaglio **Attività** di un elenco attività esistente, selezionare **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="e4d65-133">On the **Tasks** FastTab of an existing task list, select **Edit**.</span></span>
1. <span data-ttu-id="e4d65-134">Nella finestra di dialogo **Modifica attività**, nel campo **Collegamento attività**, selezionare una o più delle seguenti opzioni:</span><span class="sxs-lookup"><span data-stu-id="e4d65-134">In the **Edit task** dialog box, in the **Task link** field, select one or more of the following options:</span></span>

    - <span data-ttu-id="e4d65-135">Selezionare **Voce di menu** per configurare un'operazione di back-office, ad esempio "Kit di prodotti".</span><span class="sxs-lookup"><span data-stu-id="e4d65-135">Select **Menu item** to configure a back-office operation, such as "Product kits."</span></span>
    - <span data-ttu-id="e4d65-136">Selezionare **Operazione POS** per configurare un'operazione POS, ad esempio "Report sulle vendite".</span><span class="sxs-lookup"><span data-stu-id="e4d65-136">Select **POS Operation** to configure a POS operation, such as "Sales reports."</span></span>
    - <span data-ttu-id="e4d65-137">Selezionare **URL** per configurare un URL assoluto.</span><span class="sxs-lookup"><span data-stu-id="e4d65-137">Select **URL** to configure an absolute URL.</span></span>

<span data-ttu-id="e4d65-138">La seguente illustrazione mostra la selezione dei collegamenti delle attività nella finestra di dialogo **Modifica attività**.</span><span class="sxs-lookup"><span data-stu-id="e4d65-138">The following illustration shows the selection of task links in the **Edit task** dialog box.</span></span>

![Selezione dei collegamenti di attività nella finestra di dialogo Modifica attività](media/HQ-POS-Tasks-Linking.png)

### <a name="configure-a-pos-operation-so-that-it-can-be-linked-to-a-task"></a><span data-ttu-id="e4d65-140">Configurare un'operazione POS in modo che possa essere collegata a un'attività</span><span class="sxs-lookup"><span data-stu-id="e4d65-140">Configure a POS operation so that it can be linked to a task</span></span>

<span data-ttu-id="e4d65-141">Per configurare un'operazione POS in modo che possa essere collegata a un'attività, attenersi alla procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="e4d65-141">To configure a POS operation so that it can be linked to a task, follow these steps.</span></span>

1. <span data-ttu-id="e4d65-142">Passare a **Retail e Commerce \> Impostazione canale \> Impostazione POS \> POS \> Operazioni POS**.</span><span class="sxs-lookup"><span data-stu-id="e4d65-142">Go to **Retail and Commerce \> Channel setup \> POS setup \> POS \> POS operations**.</span></span>
1. <span data-ttu-id="e4d65-143">Selezionare **Modifica**, trovare l'operazione POS e selezionare la casella di controllo **Abilita gestione attività**.</span><span class="sxs-lookup"><span data-stu-id="e4d65-143">Select **Edit**, find the POS operation, and then select the **Enable Task Management** check box for it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="e4d65-144">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="e4d65-144">Additional resources</span></span>

[<span data-ttu-id="e4d65-145">Panoramica della gestione attività</span><span class="sxs-lookup"><span data-stu-id="e4d65-145">Task management overview</span></span>](task-mgmt-overview.md)

[<span data-ttu-id="e4d65-146">Configurare la gestione delle attività</span><span class="sxs-lookup"><span data-stu-id="e4d65-146">Configure task management</span></span>](task-mgmt-configure.md)

[<span data-ttu-id="e4d65-147">Assegnare elenchi di attività a punti vendita o dipendenti</span><span class="sxs-lookup"><span data-stu-id="e4d65-147">Assign task lists to stores or employees</span></span>](task-mgmt-assign-lists.md)

[<span data-ttu-id="e4d65-148">Gestione delle attività in POS</span><span class="sxs-lookup"><span data-stu-id="e4d65-148">Task management in POS</span></span>](task-mgmt-POS.md)
