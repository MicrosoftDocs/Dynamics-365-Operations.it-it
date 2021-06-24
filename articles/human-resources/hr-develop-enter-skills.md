---
title: Immettere le competenze
description: Lavori e manager possono inserire competenze in Dynamics 365 Human Resources.
author: andreabichsel
manager: tfehr
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmSkill, HcmSkillGapProfile, HcmSkillMapping, HcmSkillType, HcmEmployeeDevelopmentWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 3361
ms.assetid: c2ce94c0-933d-4edb-822c-7f0e7b49e4ee
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: 5a65f1884ea87bbf2519cc94e4c52a40ac1a91bd
ms.sourcegitcommit: 74e47075eab2b0b28f82b0d57f439719847ecb01
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/07/2021
ms.locfileid: "6193979"
---
# <a name="enter-skills"></a><span data-ttu-id="8ed2f-103">Immettere le competenze</span><span class="sxs-lookup"><span data-stu-id="8ed2f-103">Enter skills</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="8ed2f-104">È possibile immettere le competenze di destinazione o le competenze effettive per i lavoratori, i candidati o i contatti in Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="8ed2f-104">You can enter target skills or actual skills for workers, applicants, or contacts in Dynamics 365 Human Resources.</span></span> <span data-ttu-id="8ed2f-105">Una competenza prevista è una competenza che la persona intende raggiungere.</span><span class="sxs-lookup"><span data-stu-id="8ed2f-105">A target skill is a skill that a person plans to achieve.</span></span> <span data-ttu-id="8ed2f-106">Una competenza effettiva è una competenza che la persona ha attualmente.</span><span class="sxs-lookup"><span data-stu-id="8ed2f-106">An actual skill is a skill that a person currently has.</span></span>

## <a name="create-a-workflow-to-auto-approve-skills"></a><span data-ttu-id="8ed2f-107">Creare un flusso di lavoro per l'approvazione automatica delle competenze</span><span class="sxs-lookup"><span data-stu-id="8ed2f-107">Create a workflow to auto-approve skills</span></span>

<span data-ttu-id="8ed2f-108">Per immettere le competenze senza richiedere l'approvazione, è necessario creare un flusso di lavoro per l'approvazione automatica delle competenze.</span><span class="sxs-lookup"><span data-stu-id="8ed2f-108">To enter skills without requiring approval, you must create a workflow to auto-approve skills.</span></span>

> [!NOTE]
> <span data-ttu-id="8ed2f-109">Le competenze inserite dai lavoratori richiedono sempre l'approvazione del responsabile.</span><span class="sxs-lookup"><span data-stu-id="8ed2f-109">Skills entered by workers always require manager approval.</span></span> <span data-ttu-id="8ed2f-110">Questo flusso di lavoro approva automaticamente solo le competenze immesse dai manager per conto dei loro lavoratori.</span><span class="sxs-lookup"><span data-stu-id="8ed2f-110">This workflow only auto-approves skills entered by managers on behalf of their workers.</span></span>

1. <span data-ttu-id="8ed2f-111">Nell'area di lavoro **Gestione personale** selezionare **Collegamenti**.</span><span class="sxs-lookup"><span data-stu-id="8ed2f-111">In the **Personnel management** workspace, select **Links**.</span></span>

2. <span data-ttu-id="8ed2f-112">Sotto **Impostazione**, selezionare **Flussi di lavoro risorse umane**.</span><span class="sxs-lookup"><span data-stu-id="8ed2f-112">Under **Setup**, select **Human resources workflows**.</span></span>

3. <span data-ttu-id="8ed2f-113">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="8ed2f-113">Select **New**.</span></span>

4. <span data-ttu-id="8ed2f-114">Nel riquadro **Crea flusso di lavoro**, seleziona **Competenze lavoratore**.</span><span class="sxs-lookup"><span data-stu-id="8ed2f-114">In the **Create workflow** pane, select **Worker skills**.</span></span>

   <span data-ttu-id="8ed2f-115">[![Selezionare Flusso di lavoro delle competenze del lavoratore](media/hr-develop-skills-new-workflow.png)](media/hr-develop-skills-new-workflow.png)</span><span class="sxs-lookup"><span data-stu-id="8ed2f-115">[![Select Worker skills workflow](media/hr-develop-skills-new-workflow.png)](media/hr-develop-skills-new-workflow.png)</span></span>

5. <span data-ttu-id="8ed2f-116">Nella finestra di dialogo **Aprire questo file?**, seleziona **Apri**.</span><span class="sxs-lookup"><span data-stu-id="8ed2f-116">In the **Open this file?** dialogue, select **Open**.</span></span> <span data-ttu-id="8ed2f-117">Quando viene richiesto, immetti le credenziali.</span><span class="sxs-lookup"><span data-stu-id="8ed2f-117">When prompted, enter your credentials.</span></span>

6. <span data-ttu-id="8ed2f-118">Nell'editor del flusso di lavoro, seleziona l'elemento del flusso di lavoro **Approva competenze** e trascinalo nel canvas.</span><span class="sxs-lookup"><span data-stu-id="8ed2f-118">In the workflow editor, select the **Approve skills** workflow element and drag it onto the canvas.</span></span>

   <span data-ttu-id="8ed2f-119">[![Selezionare Approva elemento del flusso di lavoro delle competenze](media/hr-develop-skills-element.png)](media/hr-develop-skills-element.png)</span><span class="sxs-lookup"><span data-stu-id="8ed2f-119">[![Select Approve skills workflow element](media/hr-develop-skills-element.png)](media/hr-develop-skills-element.png)</span></span>

7. <span data-ttu-id="8ed2f-120">Connetti l'elemento **Inizio** all'elemento **Approva competenze 1**, quindi connetti l'elemento **Approva competenze 1** all'elemento **Fine**.</span><span class="sxs-lookup"><span data-stu-id="8ed2f-120">Connect the **Start** element to the **Approve skills 1** element, and then connect the **Approve skills 1** element to the **End** element.</span></span> <span data-ttu-id="8ed2f-121">Potrebbe essere necessario scorrere verso il basso per visualizzare l'elemento **Fine**.</span><span class="sxs-lookup"><span data-stu-id="8ed2f-121">You might need to scroll down to see the **End** element.</span></span> <span data-ttu-id="8ed2f-122">Puoi trascinarlo più vicino agli altri elementi.</span><span class="sxs-lookup"><span data-stu-id="8ed2f-122">You can drag it closer to the other elements.</span></span>

   <span data-ttu-id="8ed2f-123">[![Connettere elementi del flusso di lavoro](media/hr-develop-skills-connect-elements.png)](media/hr-develop-skills-connect-elements.png)</span><span class="sxs-lookup"><span data-stu-id="8ed2f-123">[![Connect workflow elements](media/hr-develop-skills-connect-elements.png)](media/hr-develop-skills-connect-elements.png)</span></span>

8. <span data-ttu-id="8ed2f-124">Fai doppio clic sull'elemento del flusso di lavoro **Approva competenze 1**, quindi fai clic con il pulsante destro del mouse sull'elemento **Passaggio 1**.</span><span class="sxs-lookup"><span data-stu-id="8ed2f-124">Double-click the **Approve skills 1** workflow element, and then right-click the **Step 1** element.</span></span> <span data-ttu-id="8ed2f-125">Fare clic con il pulsante destro del mouse sull'elemento **Passaggio 1**, quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="8ed2f-125">Right-click the **Step 1** element, and then select **Properties**.</span></span>

9. <span data-ttu-id="8ed2f-126">Nella finestra **Proprietà**, seleziona **Condizione** sulla barra di spostamento a sinistra.</span><span class="sxs-lookup"><span data-stu-id="8ed2f-126">In the **Properties** window, select **Condition** on the left-hand nav bar.</span></span>

10. <span data-ttu-id="8ed2f-127">Seleziona **Esegui questo passaggio solo quando è soddisfatta la seguente condizione**.</span><span class="sxs-lookup"><span data-stu-id="8ed2f-127">Select **Run this step only when the following condition is met**.</span></span>

11. <span data-ttu-id="8ed2f-128">Seleziona **Aggiungi condizione**.</span><span class="sxs-lookup"><span data-stu-id="8ed2f-128">Select **Add condition**.</span></span> <span data-ttu-id="8ed2f-129">Dopo **Dove**, seleziona **Competenze self-service dipendenti** e quindi seleziona **Employee self service skills.Person**.</span><span class="sxs-lookup"><span data-stu-id="8ed2f-129">After **Where**, select **Employee self service skills**, and then select **Employee self service skills.Person**.</span></span> <span data-ttu-id="8ed2f-130">Dopo **è**, seleziona **campo** e quindi seleziona **User to person relationship.Person**.</span><span class="sxs-lookup"><span data-stu-id="8ed2f-130">After **is**, select **field**, and then select **User to person relationship.Person**.</span></span>

    <span data-ttu-id="8ed2f-131">[![Specificare la condizione](media/hr-develop-skills-condition.png)](media/hr-develop-skills-condition.png)</span><span class="sxs-lookup"><span data-stu-id="8ed2f-131">[![Specify condition](media/hr-develop-skills-condition.png)](media/hr-develop-skills-condition.png)</span></span>

12. <span data-ttu-id="8ed2f-132">Seleziona **Assegnazione** sulla barra di spostamento a sinistra.</span><span class="sxs-lookup"><span data-stu-id="8ed2f-132">Select **Assignment** on the left-hand nav bar.</span></span>

13. <span data-ttu-id="8ed2f-133">Nella scheda **Tipo di assegnazione**, seleziona **Gerarchia**.</span><span class="sxs-lookup"><span data-stu-id="8ed2f-133">On the **Assignment type** tab, select **Hierarchy**.</span></span>

14. <span data-ttu-id="8ed2f-134">Nella scheda **Selezione gerarchia**, nel campo **Tipo di gerarchia:**, seleziona **Gerarchia manageriale**.</span><span class="sxs-lookup"><span data-stu-id="8ed2f-134">On the **Hierarchy selection** tab, in the **Hierarchy type:** field, select **Managerial hierarchy**.</span></span>

    <span data-ttu-id="8ed2f-135">[![Specificare la gerarchia manageriale](media/hr-develop-skills-hierarchy.png)](media/hr-develop-skills-hierarchy.png)</span><span class="sxs-lookup"><span data-stu-id="8ed2f-135">[![Specify managerial hierarchy](media/hr-develop-skills-hierarchy.png)](media/hr-develop-skills-hierarchy.png)</span></span>

15. <span data-ttu-id="8ed2f-136">Seleziona **Chiudi**, seleziona **Flusso di lavoro** nel percorso del canvas, quindi seleziona **Salva e chiudi**.</span><span class="sxs-lookup"><span data-stu-id="8ed2f-136">Select **Close**, select **Workflow** in the canvas breadcrumb, and then select **Save and close**.</span></span>

<span data-ttu-id="8ed2f-137">Per ulteriori informazioni sulla creazione di flussi di lavoro, vedere [Panoramica del sistema del flusso di lavoro](../fin-ops-core/fin-ops/organization-administration/overview-workflow-system.md?toc=/dynamics365/human-resources/toc.json).</span><span class="sxs-lookup"><span data-stu-id="8ed2f-137">For more information about creating workflows, see [Workflow system overview](../fin-ops-core/fin-ops/organization-administration/overview-workflow-system.md?toc=/dynamics365/human-resources/toc.json).</span></span>

## <a name="enter-skills-for-a-worker"></a><span data-ttu-id="8ed2f-138">Immettere le competenze per un lavoratore</span><span class="sxs-lookup"><span data-stu-id="8ed2f-138">Enter skills for a worker</span></span>

1. <span data-ttu-id="8ed2f-139">Seleziona un lavoratore.</span><span class="sxs-lookup"><span data-stu-id="8ed2f-139">Select a worker.</span></span>

2. <span data-ttu-id="8ed2f-140">Nella barra delle azioni della pagina **Lavoratore**, seleziona **Persona** e quindi seleziona **Competenze**.</span><span class="sxs-lookup"><span data-stu-id="8ed2f-140">In the action bar of the **Worker** page, select **Person**, and then select **Skills**.</span></span>

3. <span data-ttu-id="8ed2f-141">Nella pagia **Competenze**, completa i seguenti campi per ciascuna competenze:</span><span class="sxs-lookup"><span data-stu-id="8ed2f-141">On the **Skills** page, complete the following fields for each skill:</span></span>

   - <span data-ttu-id="8ed2f-142">**Competenza**: seleziona una competenza.</span><span class="sxs-lookup"><span data-stu-id="8ed2f-142">**Skill**: Select a skill.</span></span>
   - <span data-ttu-id="8ed2f-143">**Tipo di livello**: seleziona **Effettivo** per una competenza che il lavoratore possiede già, oppure seleziona **Target** per una competenza verso la quale il lavoratore sta lavorando.</span><span class="sxs-lookup"><span data-stu-id="8ed2f-143">**Level type**: Select **Actual** for a skill the worker already has, or select **Target** for a skill the worker is working toward.</span></span>
   - <span data-ttu-id="8ed2f-144">**Livello**: seleziona un livello per la competenza del lavoratore.</span><span class="sxs-lookup"><span data-stu-id="8ed2f-144">**Level**: Select a level for the worker's skill.</span></span>
   - <span data-ttu-id="8ed2f-145">**Data di livello**: seleziona una data nello strumento calendario.</span><span class="sxs-lookup"><span data-stu-id="8ed2f-145">**Level date**: Select a date in the calendar tool.</span></span>
   - <span data-ttu-id="8ed2f-146">**Esaminatore**: se appropriato, seleziona un esaminatore dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="8ed2f-146">**Examiner**: If appropriate, select an examiner from the list.</span></span> <span data-ttu-id="8ed2f-147">Puoi filtrare la tua ricerca.</span><span class="sxs-lookup"><span data-stu-id="8ed2f-147">You can filter your search.</span></span>
   - <span data-ttu-id="8ed2f-148">**Anni di esperienza**: inserisci gli anni di esperienza.</span><span class="sxs-lookup"><span data-stu-id="8ed2f-148">**Years of experience**: Enter years of experience.</span></span>
   - <span data-ttu-id="8ed2f-149">**Verificato**: se la competenza è verificata, seleziona la casella.</span><span class="sxs-lookup"><span data-stu-id="8ed2f-149">**Verified**: If the skill is verified, check the box.</span></span>
   - <span data-ttu-id="8ed2f-150">**Verificato da**: inserisci il nome del verificatore.</span><span class="sxs-lookup"><span data-stu-id="8ed2f-150">**Verified by**: Enter the name of the verifier.</span></span>

4. <span data-ttu-id="8ed2f-151">Quando hai finito di inserire le competenze, seleziona **Salva**.</span><span class="sxs-lookup"><span data-stu-id="8ed2f-151">When you're done entering skills, select **Save**.</span></span>

## <a name="see-also"></a><span data-ttu-id="8ed2f-152">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8ed2f-152">See also</span></span>

[<span data-ttu-id="8ed2f-153">Configurare le abilità</span><span class="sxs-lookup"><span data-stu-id="8ed2f-153">Configure skills</span></span>](hr-develop-skills.md)<br>
[<span data-ttu-id="8ed2f-154">Mappare le competenze</span><span class="sxs-lookup"><span data-stu-id="8ed2f-154">Map skills</span></span>](hr-develop-map-skills.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]