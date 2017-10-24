---
title: Allineare le competenze della forza lavoro alle esigenze
description: "È possibile tenere traccia delle competenze che hanno o dovranno avere i lavoratori, i candidati o le persone di contatto per svolgere i loro ruoli in modo efficace. È inoltre possibile specificare le competenze necessarie per una posizione lavorativa specifica."
author: kherr75
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
ms.search.form: HcmSkill, HcmSkillGapProfile, HcmSkillMapping, HcmSkillType
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 3361
ms.assetid: c2ce94c0-933d-4edb-822c-7f0e7b49e4ee
ms.search.region: Global
ms.author: kherr
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Talent July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 2b76064049daccdcdff04c9f2fdde9a8b9c9e8e0
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---

# <a name="align-workforce-skills-with-business-needs"></a><span data-ttu-id="25690-104">Allineare le competenze della forza lavoro alle esigenze</span><span class="sxs-lookup"><span data-stu-id="25690-104">Align workforce skills with business needs</span></span>

[!include[banner](includes/banner.md)]


<span data-ttu-id="25690-105">È possibile tenere traccia delle competenze che hanno o dovranno avere i lavoratori, i candidati o le persone di contatto per svolgere i loro ruoli in modo efficace.</span><span class="sxs-lookup"><span data-stu-id="25690-105">You can track the skills that workers, applicants, or contact persons have, or should have, to fulfill their roles effectively.</span></span> <span data-ttu-id="25690-106">È inoltre possibile specificare le competenze necessarie per una posizione lavorativa specifica.</span><span class="sxs-lookup"><span data-stu-id="25690-106">You can also specify the skills that are required for a specific job.</span></span>

<span data-ttu-id="25690-107">Esempi di competenze di cui è possibile tenere traccia includono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="25690-107">Examples of skills you can track include the following:</span></span>
-   <span data-ttu-id="25690-108">Supervisione: capacità di supervisionare il lavoro svolto da altre persone.</span><span class="sxs-lookup"><span data-stu-id="25690-108">Supervisory – Ability to supervise the work of others.</span></span>
-   <span data-ttu-id="25690-109">Leadership: capacità di guidare dipendenti e reparti di un'azienda.</span><span class="sxs-lookup"><span data-stu-id="25690-109">Leadership – Ability to lead employees and business domains.</span></span>
-   <span data-ttu-id="25690-110">Pianificazione: capacità di adattarsi a nuovi scenari, di formulare visioni e di vedere oltre queste.</span><span class="sxs-lookup"><span data-stu-id="25690-110">Planning – Ability to look ahead, to form visions, and to see them through.</span></span>
-   <span data-ttu-id="25690-111">HTML: capacità di scrivere codice HTML.</span><span class="sxs-lookup"><span data-stu-id="25690-111">HTML – Ability to write HTML code.</span></span>

<span data-ttu-id="25690-112">Prima di poter assegnare una competenza a una persona o a una posizione lavorativa, creare una ricerca nel mapping delle competenze o un profilo competenze, è necessario immettere informazioni sulle competenze nella pagina **Competenze**.</span><span class="sxs-lookup"><span data-stu-id="25690-112">Before you can assign a skill to a person or a job, create a skill-mapping search, or create a skill profile, you must enter information about the skills on the **Skills** page.</span></span> <span data-ttu-id="25690-113">Per ogni competenza, è possibile selezionare un tipo e un modello di valutazione.</span><span class="sxs-lookup"><span data-stu-id="25690-113">For each skill, you can select a skill type and a rating model.</span></span>

## <a name="rating-models"></a><span data-ttu-id="25690-114">Modelli di valutazione</span><span class="sxs-lookup"><span data-stu-id="25690-114">Rating models</span></span>
<span data-ttu-id="25690-115">La valutazione dei modelli contribuisce a valutare l'effettivo livello di competenza di una persona, il livello per cui deve lavorare o il livello di competenza necessario per una posizione lavorativa.</span><span class="sxs-lookup"><span data-stu-id="25690-115">Rating models help evaluate a person's actual level of skill, the level they should work to achieve, or the level of skill that is required for a job.</span></span> <span data-ttu-id="25690-116">È possibile immettere fino a 10 livelli per un modello di valutazione.</span><span class="sxs-lookup"><span data-stu-id="25690-116">You can enter up to 10 levels for a rating model.</span></span>  <span data-ttu-id="25690-117">Ogni livello in un modello di valutazione viene assegnato a un fattore.</span><span class="sxs-lookup"><span data-stu-id="25690-117">Each level in a rating model is assigned a factor.</span></span>  <span data-ttu-id="25690-118">Il valore del fattore verrà utilizzato per normalizzare i punteggi di competenze che utilizzano modelli di valutazione diversi.</span><span class="sxs-lookup"><span data-stu-id="25690-118">The factor value will be used to normalize the scores of skills that use different rating models.</span></span>  <span data-ttu-id="25690-119">Il fattore deve essere un numero compreso tra 0 e 9 e ogni livello deve avere un fattore univoco.</span><span class="sxs-lookup"><span data-stu-id="25690-119">The factor must be a number between 0-9 and each level must have a unique factor.</span></span>  <span data-ttu-id="25690-120">Livelli con valori del fattore maggiori hanno più peso in modello di valutazione.</span><span class="sxs-lookup"><span data-stu-id="25690-120">Levels with higher factor values carry more weight in a rating model.</span></span>

## <a name="specify-job-skills"></a><span data-ttu-id="25690-121">Specificare le competenze della posizione lavorativa</span><span class="sxs-lookup"><span data-stu-id="25690-121">Specify job skills</span></span>
<span data-ttu-id="25690-122">Quando si immettono informazioni su una mansione, è possibile specificare le competenze che una persona deve avere per poter svolgere tale mansione.</span><span class="sxs-lookup"><span data-stu-id="25690-122">When you enter information about a job, you can specify the skills that a person should have to perform the work required for the job.</span></span>  <span data-ttu-id="25690-123">È inoltre possibile specificare il livello desiderato per ogni competenza, nonché il livello di importanza della competenza.</span><span class="sxs-lookup"><span data-stu-id="25690-123">In addition you can specify the desired level for each skill as well the level of importance of the skill.</span></span> <span data-ttu-id="25690-124">Il livello di importanza richiesto per una determinata competenza varia in base alle diverse posizioni lavorative.</span><span class="sxs-lookup"><span data-stu-id="25690-124">Different jobs can require different levels of importance for the same skill.</span></span>

## <a name="enter-skills-for-workers-applicants-or-contacts"></a><span data-ttu-id="25690-125">Immettere le competenze per i lavoratori, i candidati o i contatti</span><span class="sxs-lookup"><span data-stu-id="25690-125">Enter skills for workers, applicants, or contacts</span></span>
<span data-ttu-id="25690-126">È possibile immettere le competenze di destinazione o le competenze effettive per i lavoratori, i candidati o i contatti.</span><span class="sxs-lookup"><span data-stu-id="25690-126">You can enter target skills or actual skills for workers, applicants, or contacts.</span></span> <span data-ttu-id="25690-127">Una competenza prevista è una competenza che la persona intende raggiungere.</span><span class="sxs-lookup"><span data-stu-id="25690-127">A target skill is a skill that a person plans to achieve.</span></span> <span data-ttu-id="25690-128">Una competenza effettiva è una competenza che la persona ha attualmente.</span><span class="sxs-lookup"><span data-stu-id="25690-128">An actual skill is a skill that a person currently has.</span></span>

## <a name="skill-mapping-and-skill-mapping-profiles"></a><span data-ttu-id="25690-129"> Mapping delle competenze e profili di mapping delle competenze</span><span class="sxs-lookup"><span data-stu-id="25690-129">Skill mapping and Skill mapping profiles</span></span>
<span data-ttu-id="25690-130">È possibile creare una ricerca del mapping delle competenze per individuare un lavoratore, un candidato o un contatto che sia qualificato a svolgere un tipo specifico di attività.</span><span class="sxs-lookup"><span data-stu-id="25690-130">You can create a skill-mapping search to find a worker, applicant, or contact person who is qualified to perform a specific type of task.</span></span> <span data-ttu-id="25690-131">Le ricerche di mapping delle competenze cercano tra competenze, istruzione, certificati, posizioni di fiducia ed esperienze di progetto e restituiscono i risultati che corrispondono ai criteri immessi.</span><span class="sxs-lookup"><span data-stu-id="25690-131">Skill-mapping searches look across skills, education, certificates, positions of trust and project experience and return a results that match the criteria entered.</span></span>  <span data-ttu-id="25690-132">Ad esempio, potrebbe essere utile conoscere i lavoratori nell'organizzazione che hanno ottenuto la Canadian Payments Association (CPA).</span><span class="sxs-lookup"><span data-stu-id="25690-132">For example, it might be useful to know which workers in your organization earned their CPA.</span></span>

<span data-ttu-id="25690-133">I profili di mapping delle competenze consentono di trovare i dipendenti o i candidati con qualifiche che corrispondono direttamente alle esigenze dell'azienda.</span><span class="sxs-lookup"><span data-stu-id="25690-133">Skill-mapping profiles allow you to find current employees or candidates with qualifications that directly correspond to business needs.</span></span>  <span data-ttu-id="25690-134">È possibile ad esempio creare un profilo di mapping delle competenze per una posizione aperta nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="25690-134">For example, you could create a skill-mapping profile for an open position in your organization.</span></span> <span data-ttu-id="25690-135">Creando un profilo per una posizione lavorativa specifica e copiando le competenze, il tipo di formazione e i certificati adatti a quella posizione nel profilo, è possibile trovare rapidamente lavoratori, candidati o persone di contatto che soddisfino uno o più dei criteri immessi nel profilo e visualizzare un elenco di candidati le cui competenze corrispondano il più possibile a quelle necessarie per la posizione lavorativa richiesta.</span><span class="sxs-lookup"><span data-stu-id="25690-135">By creating a profile for a particular job and copying the skills, education and certificates from that job to the profile, you can quickly search workers, applicants and contact persons who match one or more of the criteria entered on the profile and view a list of the candidates whose skills most closely match the skills required for the job.</span></span>

><span data-ttu-id="25690-136">**Nota**: solo i lavoratori, i candidati o le persone di contatto selezionate per essere incluse nelle ricerche del mapping delle competenze possono essere visualizzate in un elenco di risultati del mapping delle competenze o essere incluse in un profilo competenze.</span><span class="sxs-lookup"><span data-stu-id="25690-136">**Note** Only workers, applicants, and contact persons who are selected to be included in skill mapping searches can be displayed in a skill-mapping results list, or included in a skill profile.</span></span> <span data-ttu-id="25690-137">Per includere un lavoratore, un candidato o una persona di contatto nelle ricerche del mapping delle competenze, impostare la selezione **Includi nel mapping competenze** su Sì nelle pagine seguenti:</span><span class="sxs-lookup"><span data-stu-id="25690-137">To include a worker, applicant, or contact person in skill mapping searches, set the **Include in skill mapping** selection to Yes in the following pages:</span></span>

> + <span data-ttu-id="25690-138">Lavoro</span><span class="sxs-lookup"><span data-stu-id="25690-138">Worker</span></span>
> + <span data-ttu-id="25690-139">Dipendente</span><span class="sxs-lookup"><span data-stu-id="25690-139">Employee</span></span>
> + <span data-ttu-id="25690-140">Richiedente</span><span class="sxs-lookup"><span data-stu-id="25690-140">Applicant</span></span>
> + <span data-ttu-id="25690-141">Contatti</span><span class="sxs-lookup"><span data-stu-id="25690-141">Contacts</span></span>

## <a name="skill-gap-analysis-and-skill-profile-analysis"></a><span data-ttu-id="25690-142">Analisi della lacuna competenze e del profilo competenze</span><span class="sxs-lookup"><span data-stu-id="25690-142">Skill gap analysis and skill profile analysis</span></span>
<span data-ttu-id="25690-143">È possibile creare un'analisi profilo competenze per visualizzare un elenco di competenze di un lavoratore, un candidato o una persona di contatto a partire da una data specifica.</span><span class="sxs-lookup"><span data-stu-id="25690-143">You can create a skill profile analysis to view a list of the competencies of a worker, applicant, or contact person as of a specific date.</span></span> <span data-ttu-id="25690-144">È possibile creare un'analisi della lacuna competenze per confrontare le competenze di una persona con le competenze richieste per una posizione lavorativa specifica.</span><span class="sxs-lookup"><span data-stu-id="25690-144">You can create a skill gap analysis to compare a person’s skills and the skills that are required for a specific job.</span></span>  



<a name="see-also"></a><span data-ttu-id="25690-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="25690-145">See also</span></span>
--------

[<span data-ttu-id="25690-146">Risorse umane</span><span class="sxs-lookup"><span data-stu-id="25690-146">Human resources</span></span>](index.md)




