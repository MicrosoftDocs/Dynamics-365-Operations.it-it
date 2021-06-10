---
title: Mappare le competenze
description: Puoi creare una ricerca di mapping delle competenze per trovare una persona qualificata in Dynamics 365 Human Resources.
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
ms.openlocfilehash: 03b7860fbde89097141cfe48f2c240dc127aa9c3
ms.sourcegitcommit: 48528233e0f02dbd47e96e030254ef65f2bb899e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2021
ms.locfileid: "6076599"
---
# <a name="map-skills"></a><span data-ttu-id="07f77-103">Mappare le competenze</span><span class="sxs-lookup"><span data-stu-id="07f77-103">Map skills</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="07f77-104">Puoi creare una ricerca di mapping delle competenze per trovare una persona qualificata in Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="07f77-104">You can create a skill-mapping search to find a qualified person in Dynamics 365 Human Resources.</span></span> <span data-ttu-id="07f77-105">Le ricerche di mapping delle competenze restituiscono risultati per i criteri immessi esaminando le seguenti informazioni:</span><span class="sxs-lookup"><span data-stu-id="07f77-105">Skill-mapping searches return results for criteria you enter by looking through the following information:</span></span>

- <span data-ttu-id="07f77-106">Competenze</span><span class="sxs-lookup"><span data-stu-id="07f77-106">Skills</span></span>
- <span data-ttu-id="07f77-107">Percorso formativo</span><span class="sxs-lookup"><span data-stu-id="07f77-107">Education</span></span>
- <span data-ttu-id="07f77-108">Attestati</span><span class="sxs-lookup"><span data-stu-id="07f77-108">Certificates</span></span>
- <span data-ttu-id="07f77-109">Posizioni</span><span class="sxs-lookup"><span data-stu-id="07f77-109">Positions</span></span>
- <span data-ttu-id="07f77-110">Esperienza nel progetto</span><span class="sxs-lookup"><span data-stu-id="07f77-110">Project experience</span></span>

<span data-ttu-id="07f77-111">Ad esempio, puoi trovare persone nella tua organizzazione che hanno guadagnato il loro CPA.</span><span class="sxs-lookup"><span data-stu-id="07f77-111">For example, you can find people in your organization who have earned their CPA.</span></span>

<span data-ttu-id="07f77-112">I profili di mapping delle competenze consentono di trovare i dipendenti o i candidati con qualifiche che corrispondono direttamente alle esigenze dell'azienda.</span><span class="sxs-lookup"><span data-stu-id="07f77-112">Skill-mapping profiles allow you to find current employees or candidates with qualifications that directly correspond to business needs.</span></span>

> [!NOTE]
> <span data-ttu-id="07f77-113">Solo i lavoratori, i candidati o le persone di contatto selezionate per essere incluse nelle ricerche di mapping delle competenze possono essere visualizzate in un elenco di risultati del mapping delle competenze o essere incluse in un profilo competenze.</span><span class="sxs-lookup"><span data-stu-id="07f77-113">Only workers, applicants, and contact persons who are selected to be included in skill-mapping searches will display in a skill-mapping results list, or be included in a skill profile.</span></span> <span data-ttu-id="07f77-114">Per includere un lavoratore, un candidato o una persona di contatto nelle ricerche del mapping delle competenze, imposta la selezione **Includi nel mapping competenze** su **Sì** nelle pagine seguenti:</span><span class="sxs-lookup"><span data-stu-id="07f77-114">To include a person in skill mapping searches, set the **Include in skill mapping** selection to **Yes** in the following pages:</span></span><br>
> - <span data-ttu-id="07f77-115">Lavoro</span><span class="sxs-lookup"><span data-stu-id="07f77-115">Worker</span></span><br>
> - <span data-ttu-id="07f77-116">Dipendente</span><span class="sxs-lookup"><span data-stu-id="07f77-116">Employee</span></span><br>
> - <span data-ttu-id="07f77-117">Richiedente</span><span class="sxs-lookup"><span data-stu-id="07f77-117">Applicant</span></span><br>
> - <span data-ttu-id="07f77-118">Contatti</span><span class="sxs-lookup"><span data-stu-id="07f77-118">Contacts</span></span><br>

<span data-ttu-id="07f77-119">Per creare un mapping delle competenze, vai a **Sviluppo del dipendente > Collegamenti> Mapping delle competenze**.</span><span class="sxs-lookup"><span data-stu-id="07f77-119">To create a skill mapping, go to **Employee development > Links > Skill mapping**.</span></span> <span data-ttu-id="07f77-120">Per creare un profilo di mapping delle competenze, vai a **Sviluppo del dipendente > Collegamenti> Profili di mapping delle competenze**.</span><span class="sxs-lookup"><span data-stu-id="07f77-120">To create a skill-mapping profile, go to **Employee development > Links > Skill mapping profiles**.</span></span>

## <a name="skill-gap-analysis-and-skill-profile-analysis"></a><span data-ttu-id="07f77-121">Analisi della lacuna competenze e del profilo competenze</span><span class="sxs-lookup"><span data-stu-id="07f77-121">Skill gap analysis and skill profile analysis</span></span>

<span data-ttu-id="07f77-122">Puoi creare un'analisi del profilo delle competenze per visualizzare un elenco delle competenze di una persona.</span><span class="sxs-lookup"><span data-stu-id="07f77-122">You can create a skill profile analysis to view a list of a person's competencies.</span></span> <span data-ttu-id="07f77-123">Puoi creare un'analisi della lacuna competenze per confrontare le competenze di una persona con le competenze richieste per una posizione lavorativa.</span><span class="sxs-lookup"><span data-stu-id="07f77-123">You can create a skill gap analysis to compare a person’s skills and the skills required for a job.</span></span>

<span data-ttu-id="07f77-124">Per creare un'analisi degli scostamenti, vai a **Sviluppo del dipendente > Collegamenti > Analisi lacuna competenze mansione lavorativa - persona**.</span><span class="sxs-lookup"><span data-stu-id="07f77-124">To create a gap analysis, go to **Employee development > Links > Skill gap analysis job - person**.</span></span> <span data-ttu-id="07f77-125">Per creare l'analisi di un profilo delle competenze, vai a **Sviluppo del dipendente > Collegamenti> Analisi profilo competenze**.</span><span class="sxs-lookup"><span data-stu-id="07f77-125">To create a skill profile analysis, go to **Employee development > Links > Skill profile analysis**.</span></span>

## <a name="see-also"></a><span data-ttu-id="07f77-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="07f77-126">See also</span></span>

[<span data-ttu-id="07f77-127">Configurare le abilità</span><span class="sxs-lookup"><span data-stu-id="07f77-127">Configure skills</span></span>](hr-develop-skills.md)<br>
[<span data-ttu-id="07f77-128">Immettere le competenze</span><span class="sxs-lookup"><span data-stu-id="07f77-128">Enter skills</span></span>](hr-develop-enter-skills.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]