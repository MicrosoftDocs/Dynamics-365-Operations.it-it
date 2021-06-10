---
title: Configurare le competenze
description: Puoi tener traccia delle competenze del lavoratore in Dynamics 365 Human Resources. È inoltre possibile specificare le competenze necessarie per una posizione lavorativa specifica.
author: andreabichsel
manager: tfehr
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmSkill, HcmSkillGapProfile, HcmSkillMapping, HcmSkillType, HcmEmployeeDevelopmentWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: 3361
ms.assetid: c2ce94c0-933d-4edb-822c-7f0e7b49e4ee
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: 816822d1f3d365b4c5571c13e9f596e1c5d5e59c
ms.sourcegitcommit: 48528233e0f02dbd47e96e030254ef65f2bb899e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2021
ms.locfileid: "6076561"
---
# <a name="configure-skills"></a><span data-ttu-id="e3aae-104">Configurare le competenze</span><span class="sxs-lookup"><span data-stu-id="e3aae-104">Configure skills</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="e3aae-105">Puoi tener traccia delle competenze del lavoratore in Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="e3aae-105">You can track your worker's skills in Dynamics 365 Human Resources.</span></span> <span data-ttu-id="e3aae-106">È inoltre possibile specificare le competenze necessarie per una posizione lavorativa specifica.</span><span class="sxs-lookup"><span data-stu-id="e3aae-106">You can also specify the skills that are required for a specific job.</span></span>

<span data-ttu-id="e3aae-107">Esempi di competenze di cui è possibile tenere traccia includono:</span><span class="sxs-lookup"><span data-stu-id="e3aae-107">Examples of skills you can track include:</span></span>

- <span data-ttu-id="e3aae-108">Supervisione: capacità di supervisionare il lavoro svolto da altre persone.</span><span class="sxs-lookup"><span data-stu-id="e3aae-108">Supervisory – Ability to supervise the work of others.</span></span>
- <span data-ttu-id="e3aae-109">Leadership: capacità di guidare dipendenti e reparti di un'azienda.</span><span class="sxs-lookup"><span data-stu-id="e3aae-109">Leadership – Ability to lead employees and business domains.</span></span>
- <span data-ttu-id="e3aae-110">Pianificazione: capacità di adattarsi a nuovi scenari, di formulare dichiarazioni di visioni e di vedere oltre queste.</span><span class="sxs-lookup"><span data-stu-id="e3aae-110">Planning – Ability to look ahead, to form vision statements, and to see them through.</span></span>
- <span data-ttu-id="e3aae-111">HTML: capacità di scrivere codice HTML.</span><span class="sxs-lookup"><span data-stu-id="e3aae-111">HTML – Ability to write HTML code.</span></span>

<span data-ttu-id="e3aae-112">Se non hai già impostato tipi di competenze e modelli di valutazione, dovrai aggiungerne alcuni prima di creare competenze.</span><span class="sxs-lookup"><span data-stu-id="e3aae-112">If you haven't already set up skill types and rating models, you'll need to add some before creating skills.</span></span>

<span data-ttu-id="e3aae-113">Le seguenti persone possono inserire le competenze per un lavoratore:</span><span class="sxs-lookup"><span data-stu-id="e3aae-113">The following people can enter skills for a worker:</span></span>

- <span data-ttu-id="e3aae-114">I lavoratori possono inserire autonomamente le competenze nel self-service dei dipendenti.</span><span class="sxs-lookup"><span data-stu-id="e3aae-114">Workers can enter skills for themselves in Employee self-service.</span></span> <span data-ttu-id="e3aae-115">Queste competenze richiedono l'approvazione del manager.</span><span class="sxs-lookup"><span data-stu-id="e3aae-115">These skills require manager approval.</span></span>
- <span data-ttu-id="e3aae-116">I manager possono inserire le competenze per i propri lavoratori.</span><span class="sxs-lookup"><span data-stu-id="e3aae-116">Managers can enter skills for their workers.</span></span> <span data-ttu-id="e3aae-117">Puoi creare un flusso di lavoro che approva automaticamente queste competenze.</span><span class="sxs-lookup"><span data-stu-id="e3aae-117">You can create a workflow that auto-approves these skills.</span></span>

## <a name="create-a-skill-type"></a><span data-ttu-id="e3aae-118">Creare un tipo di competenza</span><span class="sxs-lookup"><span data-stu-id="e3aae-118">Create a skill type</span></span>

<span data-ttu-id="e3aae-119">I tipi di competenze sono categorie in cui rientrano le competenze individuali, come Amministrazione o Vendite.</span><span class="sxs-lookup"><span data-stu-id="e3aae-119">Skill types are categories that individual skills fall under, such as Administration or Sales.</span></span>

1. <span data-ttu-id="e3aae-120">Nell'area di lavoro **Sviluppo dipendenti**, seleziona **Collegamenti**.</span><span class="sxs-lookup"><span data-stu-id="e3aae-120">In the **Employee development** workspace, select **Links**.</span></span>

2. <span data-ttu-id="e3aae-121">In **Configurazione delle competenze**, seleziona **Tipi di competenze**.</span><span class="sxs-lookup"><span data-stu-id="e3aae-121">Under **Competency setup**, select **Skill types**.</span></span>

3. <span data-ttu-id="e3aae-122">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="e3aae-122">Select **New**.</span></span>

4. <span data-ttu-id="e3aae-123">Completa i seguenti campi:</span><span class="sxs-lookup"><span data-stu-id="e3aae-123">Complete the following fields:</span></span>

   - <span data-ttu-id="e3aae-124">**Tipo di competenza**: immetti un nome univoco per il tipo di competenza.</span><span class="sxs-lookup"><span data-stu-id="e3aae-124">**Skill type**: Enter a name for the skill type.</span></span>
   - <span data-ttu-id="e3aae-125">**Descrizione**: immetti una descrizione per il tipo di competenza.</span><span class="sxs-lookup"><span data-stu-id="e3aae-125">**Description**: Enter a description for the skill type.</span></span>

5. <span data-ttu-id="e3aae-126">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="e3aae-126">Select **Save**.</span></span>

## <a name="create-a-rating-model"></a><span data-ttu-id="e3aae-127">Creare un modello di valutazione</span><span class="sxs-lookup"><span data-stu-id="e3aae-127">Create a rating model</span></span>

<span data-ttu-id="e3aae-128">La valutazione dei modelli contribuisce a valutare l'effettivo livello di competenza di una persona, il livello per cui deve lavorare o il livello di competenza necessario per una posizione lavorativa.</span><span class="sxs-lookup"><span data-stu-id="e3aae-128">Rating models help evaluate a person's actual level of skill, the level they should work to achieve, or the level of skill required for a job.</span></span> <span data-ttu-id="e3aae-129">Ogni livello in un modello di valutazione viene assegnato a un fattore.</span><span class="sxs-lookup"><span data-stu-id="e3aae-129">Each level in a rating model is assigned a factor.</span></span>

1. <span data-ttu-id="e3aae-130">Nell'area di lavoro **Sviluppo dipendenti**, seleziona **Collegamenti**.</span><span class="sxs-lookup"><span data-stu-id="e3aae-130">In the **Employee development** workspace, select **Links**.</span></span>

2. <span data-ttu-id="e3aae-131">In **Configurazione competenza**, seleziona **Modelli di valutazione**.</span><span class="sxs-lookup"><span data-stu-id="e3aae-131">Under **Competency setup**, select **Rating models**.</span></span>

3. <span data-ttu-id="e3aae-132">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="e3aae-132">Select **New**.</span></span>

4. <span data-ttu-id="e3aae-133">Completa i seguenti campi:</span><span class="sxs-lookup"><span data-stu-id="e3aae-133">Complete the following fields:</span></span>

   - <span data-ttu-id="e3aae-134">**Valutazione**: immetti un nome per il modello di valutazione, ad esempio **Competenze**.</span><span class="sxs-lookup"><span data-stu-id="e3aae-134">**Rating**: Enter a name for the rating model, such as **Skills**.</span></span>
   - <span data-ttu-id="e3aae-135">**Descrizione**: immetti una descrizione per il modello di valutazione, ad esempio **Valutazioni delle competenze**.</span><span class="sxs-lookup"><span data-stu-id="e3aae-135">**Description**: Enter a description for the rating model, such as **Skill ratings**.</span></span>

5. <span data-ttu-id="e3aae-136">Nella sezione **Livelli**, seleziona **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="e3aae-136">In the **Levels** section, select **New**.</span></span> <span data-ttu-id="e3aae-137">Per ogni livello che desideri aggiungere, completa i seguenti campi:</span><span class="sxs-lookup"><span data-stu-id="e3aae-137">For each level you want to add, complete the following fields:</span></span>

   - <span data-ttu-id="e3aae-138">**Livello**: immetti un nome per il livello.</span><span class="sxs-lookup"><span data-stu-id="e3aae-138">**Level**: Enter a name for the level.</span></span>
   - <span data-ttu-id="e3aae-139">**Descrizione**: immetti una descrizione per il livello.</span><span class="sxs-lookup"><span data-stu-id="e3aae-139">**Description**: Enter a description for the level.</span></span>
   - <span data-ttu-id="e3aae-140">**Fattore**: immetti un valore di fattore compreso tra 0 e 9.</span><span class="sxs-lookup"><span data-stu-id="e3aae-140">**Factor**: Enter a factor value from 0-9.</span></span> <span data-ttu-id="e3aae-141">I fattori contribuiscono a normalizzare i punteggi di competenze che utilizzano modelli di valutazione diversi.</span><span class="sxs-lookup"><span data-stu-id="e3aae-141">Factors help normalize the scores of skills that use different rating models.</span></span> <span data-ttu-id="e3aae-142">Ogni livello deve avere un fattore univoco.</span><span class="sxs-lookup"><span data-stu-id="e3aae-142">Each level must have a unique factor.</span></span> <span data-ttu-id="e3aae-143">Livelli con valori del fattore maggiori hanno più peso in modello di valutazione.</span><span class="sxs-lookup"><span data-stu-id="e3aae-143">Levels with higher factor values carry more weight in a rating model.</span></span>

   <span data-ttu-id="e3aae-144">Continua ad aggiungere livelli se necessario.</span><span class="sxs-lookup"><span data-stu-id="e3aae-144">Continue adding levels as necessary.</span></span> <span data-ttu-id="e3aae-145">È possibile immettere fino a 10 livelli per ogni modello di valutazione.</span><span class="sxs-lookup"><span data-stu-id="e3aae-145">You can enter up to 10 levels for each rating model.</span></span>

6. <span data-ttu-id="e3aae-146">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="e3aae-146">Select **Save**.</span></span>

## <a name="create-a-skill"></a><span data-ttu-id="e3aae-147">Creare una competenza</span><span class="sxs-lookup"><span data-stu-id="e3aae-147">Create a skill</span></span>

<span data-ttu-id="e3aae-148">Prima di poter assegnare una competenza o creare una ricerca nel mapping delle competenze o un profilo competenze, è necessario immettere informazioni sulle competenze nella pagina **Competenze**.</span><span class="sxs-lookup"><span data-stu-id="e3aae-148">Before you can assign a skill, or create a skill-mapping search or skill profile, you must enter information about the skills on the **Skills** page.</span></span> <span data-ttu-id="e3aae-149">Per ogni competenza, è possibile selezionare un tipo e un modello di valutazione.</span><span class="sxs-lookup"><span data-stu-id="e3aae-149">For each skill, you can select a skill type and a rating model.</span></span>

1. <span data-ttu-id="e3aae-150">Nell'area di lavoro **Sviluppo dipendenti**, seleziona **Collegamenti**.</span><span class="sxs-lookup"><span data-stu-id="e3aae-150">In the **Employee development** workspace, select **Links**.</span></span>

2. <span data-ttu-id="e3aae-151">In **Configurazione delle competenze**, seleziona **Competenze**.</span><span class="sxs-lookup"><span data-stu-id="e3aae-151">Under **Competency setup**, select **Skills**.</span></span>

3. <span data-ttu-id="e3aae-152">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="e3aae-152">Select **New**.</span></span>

4. <span data-ttu-id="e3aae-153">Completa i seguenti campi:</span><span class="sxs-lookup"><span data-stu-id="e3aae-153">Complete the following fields:</span></span>

   - <span data-ttu-id="e3aae-154">**Competenza**: immetti un nome univoco per la competenza.</span><span class="sxs-lookup"><span data-stu-id="e3aae-154">**Skill**: Enter a name for the skill.</span></span>
   - <span data-ttu-id="e3aae-155">**Descrizione**: immetti una descrizione per la competenza.</span><span class="sxs-lookup"><span data-stu-id="e3aae-155">**Description**: Enter a description for the skill.</span></span>
   - <span data-ttu-id="e3aae-156">**Valutazione**: seleziona il modello di valutazione che vuoi utilizzare per la competenza.</span><span class="sxs-lookup"><span data-stu-id="e3aae-156">**Rating**: Select the rating model you want to use for this skill.</span></span>
   - <span data-ttu-id="e3aae-157">**Tipo di competenza**: seleziona dall'elenco dei tipi di competenza.</span><span class="sxs-lookup"><span data-stu-id="e3aae-157">**Skill type**: Select from the list of skill types.</span></span>

5. <span data-ttu-id="e3aae-158">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="e3aae-158">Select **Save**.</span></span>

## <a name="see-also"></a><span data-ttu-id="e3aae-159">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e3aae-159">See also</span></span>

[<span data-ttu-id="e3aae-160">Immettere le competenze</span><span class="sxs-lookup"><span data-stu-id="e3aae-160">Enter skills</span></span>](hr-develop-enter-skills.md)<br>
[<span data-ttu-id="e3aae-161">Mappare le competenze</span><span class="sxs-lookup"><span data-stu-id="e3aae-161">Map skills</span></span>](hr-develop-map-skills.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]