---
title: Integrazione client Microsoft Project
description: La pianificazione e la gestione della programmazione di un progetto possono essere complesse, per questo i manager di progetto devono utilizzare strumenti che agevolano queste attività. L'integrazione con il client Microsoft Project offre supporto per aprire e gestire una struttura di suddivisione del lavoro del progetto.
author: KimANelson
manager: AnnBe
ms.date: 12/11/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjWbsTemplate
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 87983
ms.assetid: b454ad57-2fd6-46c9-a77e-646de4153067
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2017-12-04
ms.dyn365.ops.version: 7.2999999999999998
ms.openlocfilehash: 48feb0182c623714b2acffafc42016c0471ba6c1
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "1556577"
---
# <a name="microsoft-project-client-integration"></a><span data-ttu-id="fe46d-104">Integrazione client Microsoft Project</span><span class="sxs-lookup"><span data-stu-id="fe46d-104">Microsoft Project client integration</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="fe46d-105">La pianificazione e la gestione della programmazione di un progetto possono essere complesse, per questo i manager di progetto devono utilizzare strumenti che agevolano queste attività.</span><span class="sxs-lookup"><span data-stu-id="fe46d-105">Planning and maintaining a project schedule can be complex, so project managers need to use tools that help them manage this task.</span></span> <span data-ttu-id="fe46d-106">L'integrazione con il client Microsoft Project offre supporto per aprire e gestire una struttura di suddivisione del lavoro del progetto.</span><span class="sxs-lookup"><span data-stu-id="fe46d-106">Integration with Microsoft Project Client provides support to open and manage a project work breakdown structure.</span></span> <span data-ttu-id="fe46d-107">Il manager di progetto può pubblicare tutte le modifiche apportate nella struttura di suddivisione del lavoro di progetto di Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="fe46d-107">The project manager can publish any changes back to the Finance and Operations project work breakdown structure.</span></span>

> [!NOTE]
> <span data-ttu-id="fe46d-108">Se si utilizza l'aggiornamento di luglio di Microsoft Dynamics 365 for Finance and Operations, è necessario installare KB 4054797 e 4055884.</span><span class="sxs-lookup"><span data-stu-id="fe46d-108">If you are using Microsoft Dynamics 365 for Finance and Operations, July update, you must install KB 4054797 and 4055884.</span></span>

## <a name="configure-the-microsoft-project-client-add-in"></a><span data-ttu-id="fe46d-109">Configurare il componente aggiuntivo del client Microsoft Project</span><span class="sxs-lookup"><span data-stu-id="fe46d-109">Configure the Microsoft Project Client add-in</span></span>
<span data-ttu-id="fe46d-110">Per abilitare l'integrazione con il client Microsoft Project, è necessario istallare un componente aggiuntivo di Microsoft Dynamics 365 nell'applicazione client di Microsoft Project dell'utente.</span><span class="sxs-lookup"><span data-stu-id="fe46d-110">To enable the integration with Microsoft Project Client, a Microsoft Dynamics 365 add-in is required to be installed in the user’s client Microsoft Project application.</span></span> <span data-ttu-id="fe46d-111">A tale scopo, aprire l'area di lavoro **Gestione progetti**.</span><span class="sxs-lookup"><span data-stu-id="fe46d-111">This is done by opening the **Project management workspace**.</span></span>

<span data-ttu-id="fe46d-112">•   Fare clic su **Configurare il componente aggiuntivo del client Microsoft Project** nella sezione **Collegamenti** > **Impostazioni** dell'area di lavoro.</span><span class="sxs-lookup"><span data-stu-id="fe46d-112">•   Click **Configure project client add-in** from the **Links** > **Setup** section of the workspace.</span></span>

<span data-ttu-id="fe46d-113">•   Fare clic su **Apri**, quindi su **esegui** quando richiesto.</span><span class="sxs-lookup"><span data-stu-id="fe46d-113">•   Click **Open**, then click **Run** when prompted.</span></span>

## <a name="open-and-edit-an-existing-draft-work-breakdown-structure-in-microsoft-project-client"></a><span data-ttu-id="fe46d-114">Aprire e modificare la bozza di una struttura di suddivisione del lavoro esistente nel client Microsoft Project</span><span class="sxs-lookup"><span data-stu-id="fe46d-114">Open and edit an existing draft work breakdown structure in Microsoft Project Client</span></span>
<span data-ttu-id="fe46d-115">Se in un progetto di Finance and Operations è già stata creata una struttura di suddivisione del lavoro, la struttura di suddivisione del lavoro può essere aperta nell'applicazione client Microsoft Project se la struttura di suddivisione del lavoro è in stato di bozza.</span><span class="sxs-lookup"><span data-stu-id="fe46d-115">If a project in Finance and Operations already has a work breakdown structure created, the work breakdown structure can be opened in the Microsoft Project Client application if the work breakdown structure is in a draft status.</span></span> <span data-ttu-id="fe46d-116">Per aprire la struttura dalla pagina **Project**, fare clic sul collegamento **Apri in Microsoft Project** nella scheda **Piano**. Questa pagina può anche essere aperta dall'interno dell'applicazione client di Microsoft Project facendo clic su **Apri** nella scheda **Microsoft Dynamics 365**. Selezionare la **persona giuridica** e il **progetto** dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="fe46d-116">To open from the **Project** page, click **Open in Microsoft Project** link from the **Plan** tab. This page can also be opened from within the Microsoft Project Client application by clicking **Open** in the **Microsoft Dynamics 365** tab. Select the **Legal entity** and **Project** from the list.</span></span>

> [!NOTE]
> <span data-ttu-id="fe46d-117">Se si utilizza Internet Explorer come browser, sarà necessario fare clic su **Salva** per aprire la struttura manualmente dalla posizione in cui il file viene scaricato.</span><span class="sxs-lookup"><span data-stu-id="fe46d-117">If you're using Internet Explorer as your browser, you will need to click **Save** to manually open from the location that the file is downloaded to.</span></span> <span data-ttu-id="fe46d-118">In alternativa, fare clic su **Salva e apri** per aprire il file nel client Microsoft Project.</span><span class="sxs-lookup"><span data-stu-id="fe46d-118">Or, click **Save and open** to open the file in Microsoft Project Client.</span></span> <span data-ttu-id="fe46d-119">Non rinominare il file durante il salvataggio.</span><span class="sxs-lookup"><span data-stu-id="fe46d-119">Do not rename the file name when saving.</span></span>

<span data-ttu-id="fe46d-120">Prima di apportare modifiche al file utilizzando il client Microsoft Project, è necessario estrarre il file. Fare clic su **Estrai** nella scheda **Microsoft Dynamics 365**. Ciò impedirà ad altri utenti di modificare la struttura di suddivisione del lavoro da Finance and Operations in contemporanea.</span><span class="sxs-lookup"><span data-stu-id="fe46d-120">Before making any edits to the file using Microsoft Project Client, you need to check it out. Click **Check out** in the **Microsoft Dynamics 365** tab. This will prevent other users from editing the work breakdown structure from within Finance and Operations at the same time.</span></span> <span data-ttu-id="fe46d-121">Per pubblicare la struttura di suddivisione del lavoro dopo il completamento delle eventuali modifiche, fare clic su **Archivia** nella scheda **Microsoft Dynamics 365**.</span><span class="sxs-lookup"><span data-stu-id="fe46d-121">To publish the work breakdown structure after completing any edits, click **Check in** on the **Microsoft Dynamics 365** tab.</span></span>

<span data-ttu-id="fe46d-122">Se un team di progetto è già stato aggiunto al progetto in Finance and Operations, l'elenco delle risorse verrà popolato con i membri del team.</span><span class="sxs-lookup"><span data-stu-id="fe46d-122">If a project team has already been added to the project in Finance and Operations, the resource list will be populated with the team members.</span></span> <span data-ttu-id="fe46d-123">Se un team di progetto non è stato ancora aggiunto al progetto, è possibile selezionare le risorse e creare il team all'interno del client Microsoft Project facendo clic sul pulsante **Risorse** nella scheda **Microsoft Dynamics 365**.</span><span class="sxs-lookup"><span data-stu-id="fe46d-123">If a project team has not yet been added to the project, you can select resources and build the team within Microsoft Project Client by clicking the **Resources** button on the **Microsoft Dynamics 365** tab.</span></span> 

<span data-ttu-id="fe46d-124">I seguenti dati verranno sincronizzati Finance and Operations come parte del processo di archiviazione:</span><span class="sxs-lookup"><span data-stu-id="fe46d-124">The following data will be synced back to Finance and Operations as part of the check in process:</span></span>

<span data-ttu-id="fe46d-125">•   Nome compito</span><span class="sxs-lookup"><span data-stu-id="fe46d-125">•   Task name</span></span>

<span data-ttu-id="fe46d-126">•   Data di inizio</span><span class="sxs-lookup"><span data-stu-id="fe46d-126">•   Start date</span></span>

<span data-ttu-id="fe46d-127">•   Data di completamento</span><span class="sxs-lookup"><span data-stu-id="fe46d-127">•   Finish date</span></span>

<span data-ttu-id="fe46d-128">•   Attività precedenti</span><span class="sxs-lookup"><span data-stu-id="fe46d-128">•   Predecessors</span></span>

<span data-ttu-id="fe46d-129">•   Nomi risorse</span><span class="sxs-lookup"><span data-stu-id="fe46d-129">•   Resource names</span></span>

<span data-ttu-id="fe46d-130">•   Categoria:</span><span class="sxs-lookup"><span data-stu-id="fe46d-130">•   Category</span></span>

<span data-ttu-id="fe46d-131">•   Categoria di risorsa</span><span class="sxs-lookup"><span data-stu-id="fe46d-131">•   Resource category</span></span>

<span data-ttu-id="fe46d-132">•   Ore lavorate</span><span class="sxs-lookup"><span data-stu-id="fe46d-132">•   Work hours</span></span>

<span data-ttu-id="fe46d-133">•   Note</span><span class="sxs-lookup"><span data-stu-id="fe46d-133">•   Notes</span></span>

<span data-ttu-id="fe46d-134">•   Priorità</span><span class="sxs-lookup"><span data-stu-id="fe46d-134">•   Priority</span></span>

> [!NOTE]
> <span data-ttu-id="fe46d-135">Se si aggiungono altre colonne al file del client Microsoft Project, non verranno salvate nel file e non verranno visualizzate quando il file viene nuovamente aperto.</span><span class="sxs-lookup"><span data-stu-id="fe46d-135">If you add any other columns to your Microsoft Project Client file, they will not be saved to the file and will not be displayed when the file is opened again.</span></span>

## <a name="create-the-work-breakdown-structure-for-an-existing-project-using-microsoft-project-client"></a><span data-ttu-id="fe46d-136">Creare la struttura di suddivisione del lavoro per un progetto esistente utilizzando il client Microsoft Project</span><span class="sxs-lookup"><span data-stu-id="fe46d-136">Create the work breakdown structure for an existing project using Microsoft Project Client</span></span>
<span data-ttu-id="fe46d-137">Per creare una nuova struttura di suddivisione del lavoro utilizzando il client Microsoft Project, , attenersi alla seguente procedura:</span><span class="sxs-lookup"><span data-stu-id="fe46d-137">To create a new work breakdown structure using Microsoft Project Client, follow these steps:</span></span>


1.  <span data-ttu-id="fe46d-138">Aprire il client Microsoft Project.</span><span class="sxs-lookup"><span data-stu-id="fe46d-138">Open Microsoft Project Client.</span></span>

2.  <span data-ttu-id="fe46d-139">Nella scheda **Microsoft Dynamics 365**, fare clic su **Apri**.</span><span class="sxs-lookup"><span data-stu-id="fe46d-139">On the **Microsoft Dynamics 365** tab, click **Open**.</span></span>

3.  <span data-ttu-id="fe46d-140">Selezionare la **persona giuridica** per il progetto</span><span class="sxs-lookup"><span data-stu-id="fe46d-140">Select the **Legal entity** for the project.</span></span>

4.  <span data-ttu-id="fe46d-141">Selezionare il **progetto**.</span><span class="sxs-lookup"><span data-stu-id="fe46d-141">Select the **Project**.</span></span>

5.  <span data-ttu-id="fe46d-142">Nella scheda **Microsoft Dynamics 365** fare clic su **Estrai**.</span><span class="sxs-lookup"><span data-stu-id="fe46d-142">Click **Check out** on the **Microsoft Dynamics 365** tab.</span></span>

6.  <span data-ttu-id="fe46d-143">Quando si è pronti a pubblicare in Finance and Operations, fare clic su **Archivia** nella scheda **Microsoft Dynamics 365**.</span><span class="sxs-lookup"><span data-stu-id="fe46d-143">When ready to publish to Finance and Operations, click **Check in** on the **Microsoft Dynamics 365** tab.</span></span>

## <a name="replace-the-existing-work-breakdown-structure-for-an-existing-project-using-microsoft-project-client"></a><span data-ttu-id="fe46d-144">Sostituire la struttura di suddivisione del lavoro esistente per un progetto esistente utilizzando il client Microsoft Project</span><span class="sxs-lookup"><span data-stu-id="fe46d-144">Replace the existing work breakdown structure for an existing project using Microsoft Project Client</span></span>
<span data-ttu-id="fe46d-145">Per creare una nuova struttura di suddivisione del lavoro utilizzando il client Microsoft Project e sostituire una struttura di suddivisione del lavoro esistente per un progetto esistente, attenersi alla seguente procedura:</span><span class="sxs-lookup"><span data-stu-id="fe46d-145">To create a new work breakdown structure using Microsoft Project Client and replace an existing work breakdown structure for an existing project, follow these steps:</span></span>

1.  <span data-ttu-id="fe46d-146">Aprire il client Microsoft Project.</span><span class="sxs-lookup"><span data-stu-id="fe46d-146">Open the Microsoft Project Client.</span></span>

2.  <span data-ttu-id="fe46d-147">Creare la programmazione nel client Microsoft Project.</span><span class="sxs-lookup"><span data-stu-id="fe46d-147">Create the schedule in Microsoft Project Client.</span></span>

3.  <span data-ttu-id="fe46d-148">Nella scheda **Microsoft Dynamics 365**, fare clic su **Salva modifiche** > **Sostituisci progetto esistente**.</span><span class="sxs-lookup"><span data-stu-id="fe46d-148">On the **Microsoft Dynamics 365** tab, click **Save changes** > **Replace existing project**.</span></span>

4.  <span data-ttu-id="fe46d-149">Selezionare la **persona giuridica** per il progetto</span><span class="sxs-lookup"><span data-stu-id="fe46d-149">Select the **Legal entity** for the project.</span></span>

5.  <span data-ttu-id="fe46d-150">Selezionare il **progetto**.</span><span class="sxs-lookup"><span data-stu-id="fe46d-150">Select the **Project**.</span></span>

6.  <span data-ttu-id="fe46d-151">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="fe46d-151">Click **OK**.</span></span>

## <a name="create-a-new-project-from-within-microsoft-project-client"></a><span data-ttu-id="fe46d-152">Creare un nuovo progetto nel client Microsoft Project</span><span class="sxs-lookup"><span data-stu-id="fe46d-152">Create a new project from within Microsoft Project Client</span></span>


1.  <span data-ttu-id="fe46d-153">Aprire il client Microsoft Project.</span><span class="sxs-lookup"><span data-stu-id="fe46d-153">Open the Microsoft Project Client.</span></span>

2.  <span data-ttu-id="fe46d-154">Creare la programmazione nel client Microsoft Project.</span><span class="sxs-lookup"><span data-stu-id="fe46d-154">Create the schedule in Microsoft Project Client.</span></span>

3.  <span data-ttu-id="fe46d-155">Nella scheda **Microsoft Dynamics 365**, fare clic su **Salva modifiche** > **Salva in nuovo progetto**.</span><span class="sxs-lookup"><span data-stu-id="fe46d-155">On the **Microsoft Dynamics 365** tab, click **Save changes** > **Save to new Project**.</span></span>

4.  <span data-ttu-id="fe46d-156">Selezionare la **persona giuridica** per il progetto</span><span class="sxs-lookup"><span data-stu-id="fe46d-156">Select the **Legal entity** for the project.</span></span>

5.  <span data-ttu-id="fe46d-157">Se necessario, immettere l'**ID progetto**.</span><span class="sxs-lookup"><span data-stu-id="fe46d-157">Enter the **Project ID**, if necessary.</span></span>

6.  <span data-ttu-id="fe46d-158">Immettere il **Nome progetto**.</span><span class="sxs-lookup"><span data-stu-id="fe46d-158">Enter the **Project name**.</span></span>

7.  <span data-ttu-id="fe46d-159">Selezionare il **Tipo di progetto**, il **Gruppo di progetti** e l'**ID contratto di progetto**.</span><span class="sxs-lookup"><span data-stu-id="fe46d-159">Select the **Project type**, **Project group** and the **Project contract ID**.</span></span> <span data-ttu-id="fe46d-160">In alternativa, è possibile creare un nuovo contratto di progetto facendo clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="fe46d-160">Alternatively, you can create a new project contract by clicking **New**.</span></span>

8.  <span data-ttu-id="fe46d-161">Selezionare il **Calendario** da utilizzare per le risorse.</span><span class="sxs-lookup"><span data-stu-id="fe46d-161">Select the **Calendar** to be used for resourcing.</span></span>

11. <span data-ttu-id="fe46d-162">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="fe46d-162">Click **OK**.</span></span>
