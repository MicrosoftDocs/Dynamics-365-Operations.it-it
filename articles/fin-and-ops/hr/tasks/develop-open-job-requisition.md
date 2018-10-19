--- 
title: Sviluppare e aprire richieste relative alla mansione lavorativa
description: I progetti di selezione consentono di gestire il processo di selezione.
author: kherr75
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: HRMRecruitingTable, HcmWorkerLookUp, HcmJobLookup, HRMRecruitingMedia, HRMRecruitingJobAd
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kherr
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: e2d0dcb2e64fa7b901cdc5e4a0469e5f6a76be58
ms.contentlocale: it-it
ms.lasthandoff: 10/16/2018

---
# <a name="develop-and-open-job-requisition"></a><span data-ttu-id="fe237-103">Sviluppare e aprire richieste relative alla mansione lavorativa</span><span class="sxs-lookup"><span data-stu-id="fe237-103">Develop and open job requisition</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="fe237-104">I progetti di selezione consentono di gestire il processo di selezione.</span><span class="sxs-lookup"><span data-stu-id="fe237-104">Recruitment projects help manage the recruiting process.</span></span> <span data-ttu-id="fe237-105">Per ciascun progetto di selezione, è possibile impostare informazioni, ad esempio la mansione per cui si effettua la selezione, il nome del responsabile della selezione, lo stato del progetto e il reparto che in cui la mansione verrà svolta.</span><span class="sxs-lookup"><span data-stu-id="fe237-105">For each recruitment project, you can set up information, such as the job that recruiting is for, the name of the recruiter, the status of the project and the department that the job will be located in.</span></span> <span data-ttu-id="fe237-106">Dopo avere creato un progetto di selezione, è possibile preparare un annuncio di lavoro per il progetto, pubblicare l'annuncio di lavoro nelle pagine Self Service, associare le domande di lavoro per l'impiego al progetto e tenere traccia delle attività del progetto.</span><span class="sxs-lookup"><span data-stu-id="fe237-106">After creating a recruitment project, you can write a job advertisement for the project, publish the ad on Employee self-service pages, associate applications for employment with the project, and track activities for that project.</span></span> <span data-ttu-id="fe237-107">La società di dati dimostrativi utilizzata per creare questa procedura è USMF.</span><span class="sxs-lookup"><span data-stu-id="fe237-107">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="fe237-108">Per avviare la procedura, fare clic su Risorse umane > Selezione del personale > Progetti di selezione > Progetti di selezione</span><span class="sxs-lookup"><span data-stu-id="fe237-108">To begin the procedure, go to Human resources > Recruitment > Recruitment projects > Recruitment projects</span></span>

1. <span data-ttu-id="fe237-109">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="fe237-109">Click New.</span></span>
2. <span data-ttu-id="fe237-110">Digitare un valore nel campo Progetto di selezione.</span><span class="sxs-lookup"><span data-stu-id="fe237-110">In the Recruitment project field, type a value.</span></span>
3. <span data-ttu-id="fe237-111">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="fe237-111">In the Description field, type a value.</span></span>
4. <span data-ttu-id="fe237-112">Nel campo Selezionatore fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="fe237-112">In the Recruiter field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="fe237-113">Trovare e selezionare il record desiderato nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="fe237-113">In the list, find and select the desired record.</span></span>
6. <span data-ttu-id="fe237-114">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="fe237-114">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="fe237-115">Fare clic su Seleziona.</span><span class="sxs-lookup"><span data-stu-id="fe237-115">Click Select.</span></span>
8. <span data-ttu-id="fe237-116">Nel campo Reparto fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="fe237-116">In the Department field, click the drop-down button to open the lookup.</span></span>
9. <span data-ttu-id="fe237-117">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="fe237-117">In the list, click the link in the selected row.</span></span>
10. <span data-ttu-id="fe237-118">Nel campo Mansione fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="fe237-118">In the Job field, click the drop-down button to open the lookup.</span></span>
11. <span data-ttu-id="fe237-119">Trovare e selezionare il record desiderato nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="fe237-119">In the list, find and select the desired record.</span></span>
12. <span data-ttu-id="fe237-120">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="fe237-120">In the list, click the link in the selected row.</span></span>
13. <span data-ttu-id="fe237-121">Nel campo Numero di opportunità di lavoro, immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="fe237-121">In the Number of openings field, enter a number.</span></span>
14. <span data-ttu-id="fe237-122">Nel campo Responsabile assunzioni fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="fe237-122">In the Hiring manager field, click the drop-down button to open the lookup.</span></span>
15. <span data-ttu-id="fe237-123">Trovare e selezionare il record desiderato nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="fe237-123">In the list, find and select the desired record.</span></span>
16. <span data-ttu-id="fe237-124">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="fe237-124">In the list, click the link in the selected row.</span></span>
17. <span data-ttu-id="fe237-125">Fare clic su Seleziona.</span><span class="sxs-lookup"><span data-stu-id="fe237-125">Click Select.</span></span>
18. <span data-ttu-id="fe237-126">Immettere una data nel campo Scadenza domanda.</span><span class="sxs-lookup"><span data-stu-id="fe237-126">In the Application deadline field, enter a date.</span></span>
19. <span data-ttu-id="fe237-127">Fare clic su Multimediale.</span><span class="sxs-lookup"><span data-stu-id="fe237-127">Click Media.</span></span>
    * <span data-ttu-id="fe237-128">Progetti di selezione includono l'opzione di specificare il mezzo di comunicazione da utilizzare per annunciare le posizioni aperte.</span><span class="sxs-lookup"><span data-stu-id="fe237-128">Recruitment projects include the option to specify media outlets to use to advertise open positions.</span></span>  
20. <span data-ttu-id="fe237-129">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="fe237-129">Click New.</span></span>
21. <span data-ttu-id="fe237-130">Nel campo Multimediale fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="fe237-130">In the Media field, click the drop-down button to open the lookup.</span></span>
22. <span data-ttu-id="fe237-131">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="fe237-131">In the list, click the link in the selected row.</span></span>
23. <span data-ttu-id="fe237-132">Nel campo Data di inizio, immettere una data.</span><span class="sxs-lookup"><span data-stu-id="fe237-132">In the Start date field, enter a date.</span></span>
24. <span data-ttu-id="fe237-133">Immettere una data nel campo Data di fine.</span><span class="sxs-lookup"><span data-stu-id="fe237-133">In the End date field, enter a date.</span></span>
25. <span data-ttu-id="fe237-134">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="fe237-134">Click Save.</span></span>
26. <span data-ttu-id="fe237-135">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="fe237-135">Close the page.</span></span>
27. <span data-ttu-id="fe237-136">Fare clic su Annunci di lavoro.</span><span class="sxs-lookup"><span data-stu-id="fe237-136">Click Job ads.</span></span>
28. <span data-ttu-id="fe237-137">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="fe237-137">Click Save.</span></span>
29. <span data-ttu-id="fe237-138">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="fe237-138">Close the page.</span></span>
30. <span data-ttu-id="fe237-139">Selezionare o deselezionare la casella di controllo Visualizza per dipendente self-service.</span><span class="sxs-lookup"><span data-stu-id="fe237-139">Check or uncheck the Display on employee self service checkbox.</span></span>
    * <span data-ttu-id="fe237-140">Selezionare la casella di controllo Visualizza per dipendente self-service per rendere il progetto di selezione visibile ai dipendenti nelle pagine Self Service relative ai dipendenti.</span><span class="sxs-lookup"><span data-stu-id="fe237-140">Select the Display on employee self service check box to make the recruitment project visible to employees on their Employee self-service pages.</span></span>  
31. <span data-ttu-id="fe237-141">Fare clic su Stato progetto di selezione.</span><span class="sxs-lookup"><span data-stu-id="fe237-141">Click Recruitment project status.</span></span>
32. <span data-ttu-id="fe237-142">Fare clic su Inizia.</span><span class="sxs-lookup"><span data-stu-id="fe237-142">Click Start.</span></span>
    * <span data-ttu-id="fe237-143">Lo stato Avviato indica che il progetto è pronto per ricevere le domande di lavoro.</span><span class="sxs-lookup"><span data-stu-id="fe237-143">The Started status means that the project is ready to receive applications.</span></span>  
33. <span data-ttu-id="fe237-144">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="fe237-144">Click OK.</span></span>


