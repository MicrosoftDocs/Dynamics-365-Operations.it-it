---
title: Identificare e distribuire strumenti per la selezione dei candidati
description: Individuare un pool qualificato di candidati per coprire le posizioni aperte può essere difficile, in particolare quando una posizione richiede un set univoco di competenze.
author: andreabichsel
manager: AnnBe
ms.date: 11/20/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: HcmSkillMapping, HcmJobLookup, HcmSkillMappingLine, HcmPersonCertificate, CCHTMLPrintPreview
audience: Application User
ms.reviewer: anbichse
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f4e7ed6feaa1b5b27fcfc0ec99a2d75415fe7d6a
ms.sourcegitcommit: f5e31c34640add6d40308ac1365cc0ee60e60e24
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/08/2020
ms.locfileid: "4693066"
---
# <a name="identify-and-deploy-candidate-selection-tools"></a><span data-ttu-id="7aa78-103">Identificare e distribuire strumenti per la selezione dei candidati</span><span class="sxs-lookup"><span data-stu-id="7aa78-103">Identify and deploy candidate selection tools</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="7aa78-104">Individuare un pool qualificato di candidati per coprire le posizioni aperte può essere difficile, in particolare quando una posizione richiede un set univoco di competenze.</span><span class="sxs-lookup"><span data-stu-id="7aa78-104">Finding a qualified pool of candidates to fill vacancies can be difficult, especially when a position requires a unique set of skills.</span></span>  <span data-ttu-id="7aa78-105">Tuttavia, i candidati con le competenze necessarie possono essere già dipendenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="7aa78-105">However, candidates with the skills you need might already be employed in your organization.</span></span> <span data-ttu-id="7aa78-106">È possibile trovare un set di competenze specifico tra i dipendenti esistenti o i nuovi candidati.</span><span class="sxs-lookup"><span data-stu-id="7aa78-106">You can search for a specific skill set among existing employees, or new applicants.</span></span> <span data-ttu-id="7aa78-107">Ciò consente al selezionatore di riunire e fare velocemente lo screening dei candidati che si sono proposti per la posizione aperta ora o in passato oppure di trovare i potenziali candidati dal pool di dipendenti esistente.</span><span class="sxs-lookup"><span data-stu-id="7aa78-107">This allows a recruiter to quickly gather and screen applicants who have applied for open position now or in the past, or to find potential candidates from their existing pool of employees.</span></span> <span data-ttu-id="7aa78-108">Utilizzare questa registrazione dell'attività per scoprire come la funzionalità di mapping delle competenze consenta di individuare la persona giusta per una posizione aperta.</span><span class="sxs-lookup"><span data-stu-id="7aa78-108">Use this task recording to learn how the skill mapping functionality can help you find the right person for an open position.</span></span> <span data-ttu-id="7aa78-109">La società di dati dimostrativi utilizzata per creare questa procedura è USMF.</span><span class="sxs-lookup"><span data-stu-id="7aa78-109">The demo data company used to create this procedure is USMF.</span></span>

1. <span data-ttu-id="7aa78-110">Andare a Risorse umane > Competenze > Analisi competenze > Profili mapping competenze.</span><span class="sxs-lookup"><span data-stu-id="7aa78-110">Go to Human resources > Competencies > Skill analysis > Skill mapping profiles.</span></span>
2. <span data-ttu-id="7aa78-111">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="7aa78-111">Click New.</span></span>
3. <span data-ttu-id="7aa78-112">Nel campo Mapping competenze, immettere un nome per il mapping delle competenze.</span><span class="sxs-lookup"><span data-stu-id="7aa78-112">In the Skill mapping field, enter a name for your skill mapping.</span></span>  <span data-ttu-id="7aa78-113">Esempio: Ragioniere.</span><span class="sxs-lookup"><span data-stu-id="7aa78-113">Example: Accountant.</span></span>
4. <span data-ttu-id="7aa78-114">Nel campo Descrizione immettere una descrizione del mapping delle competenze.</span><span class="sxs-lookup"><span data-stu-id="7aa78-114">In the Description field, enter a description of the skill mapping..</span></span>
5. <span data-ttu-id="7aa78-115">Nel campo Data immettere una data.</span><span class="sxs-lookup"><span data-stu-id="7aa78-115">In the Date field, enter a date.</span></span>
6. <span data-ttu-id="7aa78-116">Fare clic su Recupera profilo.</span><span class="sxs-lookup"><span data-stu-id="7aa78-116">Click Retrieve profile.</span></span>
    * <span data-ttu-id="7aa78-117">Utilizzare Recupera profilo per estrarre i dati relativi ai certificati, alle competenze e all'istruzione da una persona, una mansione o un corso selezionato come base per la ricerca.</span><span class="sxs-lookup"><span data-stu-id="7aa78-117">Use Retrieve profile to pull in the Certificate, Skill, and Education data from a selected Person, Job or Course as the basis for your search.</span></span>   <span data-ttu-id="7aa78-118">È possibile aggiungere o rimuovere i criteri, lo stato se i criteri sono facoltativi e classificare l'importanza dei criteri.</span><span class="sxs-lookup"><span data-stu-id="7aa78-118">You can then add or remove criteria, state if the criteria is optional and rank the importance of the criteria.</span></span>  
7. <span data-ttu-id="7aa78-119">Fare clic su Mansione.</span><span class="sxs-lookup"><span data-stu-id="7aa78-119">Click Job.</span></span>
8. <span data-ttu-id="7aa78-120">Nel campo Mansione immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="7aa78-120">In the Job field, enter or select a value.</span></span>
9. <span data-ttu-id="7aa78-121">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="7aa78-121">Click OK.</span></span>
10. <span data-ttu-id="7aa78-122">Espandere la Scheda dettaglio Intervallo e aggiungere eventuali informazioni aggiuntive, ad esempio il reparto.</span><span class="sxs-lookup"><span data-stu-id="7aa78-122">Expand the Range FastTab, and add any additional information, such as department.</span></span>
11. <span data-ttu-id="7aa78-123">Espandere la Scheda dettaglio Certificati per visualizzare o modificare i certificati.</span><span class="sxs-lookup"><span data-stu-id="7aa78-123">Expand the Certificates FastTab to view or edit the certificates.</span></span>
12. <span data-ttu-id="7aa78-124">Espandere la Scheda dettaglio Competenze per visualizzare o modificare le competenze.</span><span class="sxs-lookup"><span data-stu-id="7aa78-124">Expand the Skills FastTab to view or edit the skills.</span></span>
13. <span data-ttu-id="7aa78-125">Espandere la Scheda dettaglio Istruzione per visualizzare o modificare i criteri relativi all'istruzione.</span><span class="sxs-lookup"><span data-stu-id="7aa78-125">Expand the Education FastTab to view or edit the education criteria.</span></span>
14. <span data-ttu-id="7aa78-126">Fare clic su Esegui.</span><span class="sxs-lookup"><span data-stu-id="7aa78-126">Click Execute.</span></span>
15. <span data-ttu-id="7aa78-127">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="7aa78-127">Click OK.</span></span>
16. <span data-ttu-id="7aa78-128">Fare clic su Risultato.</span><span class="sxs-lookup"><span data-stu-id="7aa78-128">Click Result.</span></span>
17. <span data-ttu-id="7aa78-129">Fare clic su Risultato.</span><span class="sxs-lookup"><span data-stu-id="7aa78-129">Click Result.</span></span>
18. <span data-ttu-id="7aa78-130">Fare clic su Riprendi.</span><span class="sxs-lookup"><span data-stu-id="7aa78-130">Click Resume.</span></span>
19. <span data-ttu-id="7aa78-131">Fare clic su Certificati.</span><span class="sxs-lookup"><span data-stu-id="7aa78-131">Click Certificates.</span></span>
    * <span data-ttu-id="7aa78-132">È possibile esaminare più nel dettaglio ogni persona elencata e visualizzare i dettagli relativi all'istruzione, alle competenze e all'esperienza professionale.</span><span class="sxs-lookup"><span data-stu-id="7aa78-132">You can drill further into each person listed and see details regarding their education, skills, and professional experience.</span></span>  
20. <span data-ttu-id="7aa78-133">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="7aa78-133">Close the page.</span></span>
21. <span data-ttu-id="7aa78-134">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="7aa78-134">Close the page.</span></span>
22. <span data-ttu-id="7aa78-135">Selezionare di nuovo il risultato.</span><span class="sxs-lookup"><span data-stu-id="7aa78-135">Select result again.</span></span>
23. <span data-ttu-id="7aa78-136">Fare clic su Report.</span><span class="sxs-lookup"><span data-stu-id="7aa78-136">Click Report.</span></span>
    * <span data-ttu-id="7aa78-137">Le corrispondenze migliori verranno elencate nella parte superiore del report.</span><span class="sxs-lookup"><span data-stu-id="7aa78-137">The report will list the best matches at the top of the report.</span></span>  <span data-ttu-id="7aa78-138">È possibile vedere che viene elencato un elemento di lacuna.</span><span class="sxs-lookup"><span data-stu-id="7aa78-138">You can see that a gap element is listed.</span></span>  <span data-ttu-id="7aa78-139">È la differenza tra il livello elencato nel mapping competenze e il livello di competenza assegnato alla persona.</span><span class="sxs-lookup"><span data-stu-id="7aa78-139">This is the difference between the level that was listed on the skill mapping, and the level of the skill that is assigned to the person.</span></span>  
24. <span data-ttu-id="7aa78-140">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="7aa78-140">Close the page.</span></span>
25. <span data-ttu-id="7aa78-141">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="7aa78-141">Click Save.</span></span>

