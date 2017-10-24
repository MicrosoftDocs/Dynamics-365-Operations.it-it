---
title: Utilizzare i flussi di lavoro per gestire le informazioni sui dipendenti
description: "In questo argomento viene descritto come utilizzare la funzionalità del flusso di lavoro per le risorse umane per gestire le informazioni sui dipendenti. Ad esempio, è possibile associare un flusso di lavoro a una posizione e configurare un flusso di lavoro di approvazione che viene avviato quando i dipendenti modificano i propri record."
author: rschloma
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 269074
ms.assetid: 426c6127-42ee-4163-8dd0-b2867f95581d
ms.search.region: Global
ms.author: shielas
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 2dc4671e0b68dffe30fe73d8c95113481673a27a
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---

# <a name="use-workflows-to-manage-employee-information"></a><span data-ttu-id="7a08b-104">Utilizzare i flussi di lavoro per gestire le informazioni sui dipendenti</span><span class="sxs-lookup"><span data-stu-id="7a08b-104">Use workflows to manage employee information</span></span>

[!include[banner](includes/banner.md)]


<span data-ttu-id="7a08b-105">In questo argomento viene descritto come utilizzare la funzionalità del flusso di lavoro per le risorse umane per gestire le informazioni sui dipendenti.</span><span class="sxs-lookup"><span data-stu-id="7a08b-105">This topic explains how you can use the workflow capability for Human resources to manage employee information.</span></span> <span data-ttu-id="7a08b-106">Ad esempio, è possibile associare un flusso di lavoro a una posizione e configurare un flusso di lavoro di approvazione che viene avviato quando i dipendenti modificano i propri record.</span><span class="sxs-lookup"><span data-stu-id="7a08b-106">For example, you can associate a workflow with a position and configure an approval workflow that is started when employees change their record.</span></span>

<span data-ttu-id="7a08b-107">La funzionalità del flusso di lavoro per le risorse umane fornisce numerosi flussi di lavoro per la gestione delle attività delle risorse umane.</span><span class="sxs-lookup"><span data-stu-id="7a08b-107">The workflow capability for Human resources provides numerous workflows for managing human resources activities.</span></span> <span data-ttu-id="7a08b-108">Sono inoltre disponibili numerose opzioni per poter modificare flussi di lavoro specifici e associarli a una gerarchia di reporting.</span><span class="sxs-lookup"><span data-stu-id="7a08b-108">Additionally, numerous options are available so that you can modify specific workflows and associate them with a reporting hierarchy.</span></span> <span data-ttu-id="7a08b-109">I flussi di lavoro sono disponibili per agevolare la gestione delle modifiche a vari tipi standard di informazioni sui dipendenti.</span><span class="sxs-lookup"><span data-stu-id="7a08b-109">Workflows are available to help manage changes to several standard types of employee information.</span></span> <span data-ttu-id="7a08b-110">È possibile associare un flusso di lavoro a una posizione.</span><span class="sxs-lookup"><span data-stu-id="7a08b-110">You can associate a workflow with a position.</span></span> <span data-ttu-id="7a08b-111">Quindi, se i dipendenti modificano i propri record dipendente, viene avviato un flusso di lavoro che richiede l'approvazione prima che le nuove informazioni vengano salvate.</span><span class="sxs-lookup"><span data-stu-id="7a08b-111">Then, if employees change their employee record, a workflow is started that requires approval before the new information is saved.</span></span> <span data-ttu-id="7a08b-112">I flussi di lavoro sono predefiniti per i seguenti tipi di informazioni per consentire di gestire le modifiche in modo efficiente e garantire la precisione dei dati dei dipendenti.</span><span class="sxs-lookup"><span data-stu-id="7a08b-112">Workflows are predefined for the following types of information to help you efficiently manage changes and keep your employees’ data accurate:</span></span>

-   <span data-ttu-id="7a08b-113">Numeri di identificazione</span><span class="sxs-lookup"><span data-stu-id="7a08b-113">Identification numbers</span></span>
-   <span data-ttu-id="7a08b-114">Corsi</span><span class="sxs-lookup"><span data-stu-id="7a08b-114">Courses</span></span>
-   <span data-ttu-id="7a08b-115">Percorso formativo</span><span class="sxs-lookup"><span data-stu-id="7a08b-115">Education</span></span>
-   <span data-ttu-id="7a08b-116">Immagine</span><span class="sxs-lookup"><span data-stu-id="7a08b-116">Image</span></span>
-   <span data-ttu-id="7a08b-117">Articoli prestati</span><span class="sxs-lookup"><span data-stu-id="7a08b-117">Loaned items</span></span>
-   <span data-ttu-id="7a08b-118">Esperienza professionale</span><span class="sxs-lookup"><span data-stu-id="7a08b-118">Professional experience</span></span>
-   <span data-ttu-id="7a08b-119">Esperienza nel progetto</span><span class="sxs-lookup"><span data-stu-id="7a08b-119">Project experience</span></span>
-   <span data-ttu-id="7a08b-120">Competenze</span><span class="sxs-lookup"><span data-stu-id="7a08b-120">Skills</span></span>
-   <span data-ttu-id="7a08b-121">Posizioni di fiducia</span><span class="sxs-lookup"><span data-stu-id="7a08b-121">Positions of trust</span></span>
-   <span data-ttu-id="7a08b-122">Azioni Risorse umane</span><span class="sxs-lookup"><span data-stu-id="7a08b-122">Human resources actions</span></span>
-   <span data-ttu-id="7a08b-123">Registrazione di corsi</span><span class="sxs-lookup"><span data-stu-id="7a08b-123">Course registration</span></span>

<span data-ttu-id="7a08b-124">Quando i dipendenti vengono assunti, trasferiti o licenziati, il flusso di lavoro può includere un processo di revisione.</span><span class="sxs-lookup"><span data-stu-id="7a08b-124">When employees are hired, transferred, or terminated, the workflow can include a review process.</span></span> <span data-ttu-id="7a08b-125">In questo modo, un documento può essere rivisto o i termini di un'azione possono essere definiti come parte del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="7a08b-125">In this way, a document can be revised or the terms of an action can be defined as part of the workflow.</span></span> <span data-ttu-id="7a08b-126">Una volta completato il processo di revisione, l'azione o il documento viene completato e il flusso di lavoro passa a una fase di approvazione finale.</span><span class="sxs-lookup"><span data-stu-id="7a08b-126">When the review process is completed, the document or action is completed, and the workflow moves to a final approval step.</span></span>

## <a name="associate-a-workflow-with-a-position-hierarchy"></a><span data-ttu-id="7a08b-127">Associare un flusso di lavoro a una gerarchia posizioni</span><span class="sxs-lookup"><span data-stu-id="7a08b-127">Associate a workflow with a position hierarchy</span></span>
<span data-ttu-id="7a08b-128">È possibile associare un flusso di lavoro con qualsiasi gerarchia che si configura.</span><span class="sxs-lookup"><span data-stu-id="7a08b-128">You can associate a workflow with any hierarchy that you configure.</span></span> <span data-ttu-id="7a08b-129">Ad esempio, se una posizione è associata una gerarchia di report di matrice, è possibile configurare un flusso di lavoro che indirizza le spese per un progetto specifico a un responsabile di progetto anziché al responsabile del dipendente associato alla posizione.</span><span class="sxs-lookup"><span data-stu-id="7a08b-129">For example, if a position is associated with a matrix reporting hierarchy, you might configure a workflow that routes expenses for a specific project to the project lead instead of the manager of the employee who is associated with that position.</span></span> <span data-ttu-id="7a08b-130">Per creare un nuovo flusso di lavoro o modificare un flusso di lavoro esistente, nella pagina **Flusso di lavoro risorse umane**, fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="7a08b-130">To create a new workflow or modify an existing workflow, on the **Human resources workflow** page, click **New**.</span></span> <span data-ttu-id="7a08b-131">Selezionare un flusso di lavoro nell'elenco per avviare la finestra di progettazione del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="7a08b-131">Select a workflow in the list to start the Workflow designer.</span></span> <span data-ttu-id="7a08b-132">È possibile utilizzare la finestra di progettazione per creare un nuovo flusso di lavoro o per modificare i passaggi in un flusso di lavoro esistente.</span><span class="sxs-lookup"><span data-stu-id="7a08b-132">You can use the designer to create a new workflow or change the steps in an existing workflow.</span></span> <span data-ttu-id="7a08b-133">Quando si modifica un flusso di lavoro esistente, le modifiche vengono salvate come una nuova versione.</span><span class="sxs-lookup"><span data-stu-id="7a08b-133">When you change an existing workflow, your changes are saved as a new version.</span></span> <span data-ttu-id="7a08b-134">Di conseguenza, è possibile tornare sempre alla versione precedente, se necessario.</span><span class="sxs-lookup"><span data-stu-id="7a08b-134">Therefore, you can always go back to a previous version if you have to.</span></span>

## <a name="configure-a-human-resources-workflow"></a><span data-ttu-id="7a08b-135">Configurare un flusso di lavoro delle risorse umane</span><span class="sxs-lookup"><span data-stu-id="7a08b-135">Configure a Human resources workflow</span></span>
<span data-ttu-id="7a08b-136">Per configurare un flusso di lavoro di base che viene avviato quando i dipendenti richiedono modifiche alla propria identificazione personale, effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="7a08b-136">To configure a basic workflow that is started when employees request changes to their personal identification, follow these steps.</span></span>

1.  <span data-ttu-id="7a08b-137">Nella pagina **Flussi di lavoro risorse umane**, fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="7a08b-137">On the **Human resources workflows** page, click **New**.</span></span>
2.  <span data-ttu-id="7a08b-138">Nell'elenco di flussi di lavoro disponibili, selezionare **Numeri di identificazione**.</span><span class="sxs-lookup"><span data-stu-id="7a08b-138">In the list of available workflows, select **Identification numbers**.</span></span>
3.  <span data-ttu-id="7a08b-139">Fare clic su **Esegui** per avviare la finestra di progettazione del flusso di lavoro, quindi immettere il nome utente e la password quando richiesto.</span><span class="sxs-lookup"><span data-stu-id="7a08b-139">Click **Run** to start the Workflow designer, and then enter your user name and password when you're prompted.</span></span>
4.  <span data-ttu-id="7a08b-140">Trascinare l'elemento **Approva numero di identificazione** dall'elenco degli elementi del flusso di lavoro nella canvas della finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="7a08b-140">Drag the **Approve identification number** element from the list of workflow elements to the designer canvas.</span></span>
5.  <span data-ttu-id="7a08b-141">Collegare l'elemento di approvazione a **Inizio** e **Fine**.</span><span class="sxs-lookup"><span data-stu-id="7a08b-141">Connect the approval element to **Start** and **Finish**.</span></span>
6.  <span data-ttu-id="7a08b-142">Fare doppio clic su **Approva elemento**, quindi fare clic con il pulsante destro del mouse e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="7a08b-142">Double-click **Approve element**, and then right-click, and select **Properties**.</span></span>
7.  <span data-ttu-id="7a08b-143">Per aggiungere istruzioni dell'elemento di lavoro, effettuare le operazioni indicate di seguito:</span><span class="sxs-lookup"><span data-stu-id="7a08b-143">Follow these steps to add work item instructions:</span></span>
    1.  <span data-ttu-id="7a08b-144">Selezionare **Assegnazione**, quindi selezionare **Gerarchia** nel tipo di assegnazione.</span><span class="sxs-lookup"><span data-stu-id="7a08b-144">Select **Assignment**, and then select **Hierarchy** under the assignment type.</span></span>
    2.  <span data-ttu-id="7a08b-145">Nella selezione **Gerarchia**, selezionare **Gerarchia configurabile**.</span><span class="sxs-lookup"><span data-stu-id="7a08b-145">Under the **Hierarchy** selection, select **Configurable hierarchy**.</span></span>
    3.  <span data-ttu-id="7a08b-146">Aggiungere una condizione di interruzione, quindi chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="7a08b-146">Add a stop condition, and close the page.</span></span>

8.  <span data-ttu-id="7a08b-147">Completare le eventuali istruzioni aggiuntive (non deve essere presente alcun avviso aggiuntivo).</span><span class="sxs-lookup"><span data-stu-id="7a08b-147">Complete any additional instructions (no additional warnings should exist).</span></span>
9.  <span data-ttu-id="7a08b-148">Fare clic su **Salva e chiudi**.</span><span class="sxs-lookup"><span data-stu-id="7a08b-148">Click **Save and close**.</span></span> <span data-ttu-id="7a08b-149">Attivare il nuovo flusso di lavoro quando verrà visualizzata la finestra di dialogo, quindi selezionare **Rendi attivo**.</span><span class="sxs-lookup"><span data-stu-id="7a08b-149">Activate the new workflow when the dialog box opens, and select **Make active**.</span></span>
10. <span data-ttu-id="7a08b-150">Passare a **Risorse umane** &gt; **Posizioni** &gt; **Tipi di gerarchia posizioni**.</span><span class="sxs-lookup"><span data-stu-id="7a08b-150">Go to **Human Resources** &gt; **Positions** &gt; **Position hierarchy types**.</span></span>
11. <span data-ttu-id="7a08b-151">Selezionare **Matrice**.</span><span class="sxs-lookup"><span data-stu-id="7a08b-151">Select **Matrix**.</span></span>
12. <span data-ttu-id="7a08b-152">Aggiungere il flusso di lavoro **Numero di identificazione lavoratore** all'elenco.</span><span class="sxs-lookup"><span data-stu-id="7a08b-152">Add the **Worker identification number** workflow to the list.</span></span>





