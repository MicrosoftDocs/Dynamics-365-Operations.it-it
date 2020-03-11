---
title: Aggiungere una voce al giornale di registrazione delle prestazioni e inviare complimento a un utente
description: Il giornale di registrazione delle prestazioni contiene informazioni correlate a come sono stati soddisfatti gli obiettivi o quali sono state le prestazioni durante un periodo.
author: andreabichsel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EssWorkspace, HcmPerfJournal, HcmPerfJournalAddLink, HcmPerfPraise, HcmWorkerLookUpByPerson, HcmPerfJournalAdd
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2a7c21c4a6aed5c53a78179e2139d50a146fdbc9
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2020
ms.locfileid: "3009593"
---
# <a name="add-to-your-performance-journal-and-send-praise-to-someone"></a><span data-ttu-id="9b5f6-103">Aggiungere una voce al giornale di registrazione delle prestazioni e inviare complimento a un utente</span><span class="sxs-lookup"><span data-stu-id="9b5f6-103">Add to your performance journal and send praise to someone</span></span>

<span data-ttu-id="9b5f6-104">Il giornale di registrazione delle prestazioni contiene informazioni correlate a come sono stati soddisfatti gli obiettivi o quali sono state le prestazioni durante un periodo.</span><span class="sxs-lookup"><span data-stu-id="9b5f6-104">The performance journal holds information that relates to how you met your goals or how you performed during a period.</span></span> <span data-ttu-id="9b5f6-105">È inoltre possibile fare un complimento per le azioni di un collega dal giornale di registrazione.</span><span class="sxs-lookup"><span data-stu-id="9b5f6-105">You can also praise the actions of a co-worker from the journal.</span></span> <span data-ttu-id="9b5f6-106">La società di dati dimostrativi utilizzata per creare questa procedura è USMF.</span><span class="sxs-lookup"><span data-stu-id="9b5f6-106">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="9b5f6-107">Questa procedura è per una funzionalità che è stata aggiunta in Dynamics 365 for Operations versione 1611.</span><span class="sxs-lookup"><span data-stu-id="9b5f6-107">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>

1. <span data-ttu-id="9b5f6-108">Passare a Tutte le aree di lavoro > Dipendente self-service.</span><span class="sxs-lookup"><span data-stu-id="9b5f6-108">Go to All workspaces > Employee self service.</span></span>
2. <span data-ttu-id="9b5f6-109">Fare clic su Giornale di registrazione prestazioni.</span><span class="sxs-lookup"><span data-stu-id="9b5f6-109">Click Performance journal.</span></span>
3. <span data-ttu-id="9b5f6-110">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="9b5f6-110">Click New.</span></span>
4. <span data-ttu-id="9b5f6-111">Digitare un valore nel campo Titolo.</span><span class="sxs-lookup"><span data-stu-id="9b5f6-111">In the Title field, type a value.</span></span>
5. <span data-ttu-id="9b5f6-112">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="9b5f6-112">In the Description field, type a value.</span></span>
    * <span data-ttu-id="9b5f6-113">La data del giornale di registrazione delle prestazioni corrisponde alla data in cui è stato creato il giornale di registrazione.</span><span class="sxs-lookup"><span data-stu-id="9b5f6-113">The performance journal date is the date that the journal was created.</span></span>  
    * <span data-ttu-id="9b5f6-114">L'Origine rappresenta da dove proviene il giornale di registrazione delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="9b5f6-114">The source represents where the performance journal came from.</span></span> <span data-ttu-id="9b5f6-115">Quando si crea uno, proviene da Giornale di registrazione personale.</span><span class="sxs-lookup"><span data-stu-id="9b5f6-115">When you create one, it comes from My journal.</span></span> <span data-ttu-id="9b5f6-116">Se il proprio responsabile ne crea uno, proviene da Giornale di registrazione responsabile.</span><span class="sxs-lookup"><span data-stu-id="9b5f6-116">If your manager creates one, it comes from the Manager journal.</span></span>  
    * <span data-ttu-id="9b5f6-117">È possibile condividere il giornale di registrazione con il responsabile o renderlo visibile solo all'utente.</span><span class="sxs-lookup"><span data-stu-id="9b5f6-117">You can share this journal with your manager or make it only visible to you.</span></span>  
6. <span data-ttu-id="9b5f6-118">Nel campo Data di inizio, immettere una data.</span><span class="sxs-lookup"><span data-stu-id="9b5f6-118">In the Start date field, enter a date.</span></span>
7. <span data-ttu-id="9b5f6-119">Immettere una data nel campo Data di completamento.</span><span class="sxs-lookup"><span data-stu-id="9b5f6-119">In the Date completed field, enter a date.</span></span>
8. <span data-ttu-id="9b5f6-120">Nel campo Piano di sviluppo selezionare Sì.</span><span class="sxs-lookup"><span data-stu-id="9b5f6-120">Select Yes in the Development plan field.</span></span>
9. <span data-ttu-id="9b5f6-121">Nel campo Parole chiave digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="9b5f6-121">In the Keywords field, type a value.</span></span>
10. <span data-ttu-id="9b5f6-122">Fare clic su Aggiungi collegamento esterno.</span><span class="sxs-lookup"><span data-stu-id="9b5f6-122">Click Add external link.</span></span>
11. <span data-ttu-id="9b5f6-123">Digitare 'Envision' nel campo Descrizione.</span><span class="sxs-lookup"><span data-stu-id="9b5f6-123">In the Description field, type 'Envision'.</span></span>
12. <span data-ttu-id="9b5f6-124">Nel campo Indirizzo Internet digitare "https://www.microsoft.com/en/envision/default".</span><span class="sxs-lookup"><span data-stu-id="9b5f6-124">In the Internet address field, type 'https://www.microsoft.com/en/envision/default'.</span></span>
13. <span data-ttu-id="9b5f6-125">Fare clic sul titolo sottostante il pulsante Salva denominato "Giornale di registrazione prestazioni" per tornare alla griglia.</span><span class="sxs-lookup"><span data-stu-id="9b5f6-125">Click on the caption below the Save button called "Performance journal" to return to the grid.</span></span>
    * <span data-ttu-id="9b5f6-126">È possibile aggiungere il giornale di registrazione o i giornali di registrazione selezionati a un obiettivo in modo che venga visualizzato quando si apre l'obiettivo.</span><span class="sxs-lookup"><span data-stu-id="9b5f6-126">You can add the selected journal or journals to a goal so that it appears when you open the goal.</span></span> <span data-ttu-id="9b5f6-127">Un collegamento verrà aggiunto nella scheda dettaglio Collegamenti. Se si aggiunge un giornale di registrazione a un obiettivo e quindi si aggiunge l'obiettivo a una revisione, il giornale di registrazione verrà visualizzato automaticamente nella revisione.</span><span class="sxs-lookup"><span data-stu-id="9b5f6-127">A link will be added in the Links fast tab.    If you add a journal to a goal and then add the goal to a review, the journal will appear on the review automatically.</span></span>  
    * <span data-ttu-id="9b5f6-128">È possibile aggiungere il giornale di registrazione o i giornali di registrazione selezionati a una revisione in modo che venga visualizzato quando si apre la revisione.</span><span class="sxs-lookup"><span data-stu-id="9b5f6-128">You can add the selected journal or journals to a review so that it appears when you open the review.</span></span>    <span data-ttu-id="9b5f6-129">Un collegamento verrà aggiunto nella scheda dettaglio Collegamenti.</span><span class="sxs-lookup"><span data-stu-id="9b5f6-129">A link will be added in the Links fast tab.</span></span>  
14. <span data-ttu-id="9b5f6-130">Fare clic su Aggiungi rapido.</span><span class="sxs-lookup"><span data-stu-id="9b5f6-130">Click Quick add.</span></span>
15. <span data-ttu-id="9b5f6-131">Digitare un valore nel campo Titolo.</span><span class="sxs-lookup"><span data-stu-id="9b5f6-131">In the Title field, type a value.</span></span>
16. <span data-ttu-id="9b5f6-132">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="9b5f6-132">In the Description field, type a value.</span></span>
17. <span data-ttu-id="9b5f6-133">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="9b5f6-133">Click Save.</span></span>
18. <span data-ttu-id="9b5f6-134">Fare clic su Invia complimento.</span><span class="sxs-lookup"><span data-stu-id="9b5f6-134">Click Send praise.</span></span>
19. <span data-ttu-id="9b5f6-135">Selezionare una persona dall'elenco dei dipendenti della società.</span><span class="sxs-lookup"><span data-stu-id="9b5f6-135">Select a person from the list of employees in the company.</span></span>
20. <span data-ttu-id="9b5f6-136">Nel campo Descrizione, immettere 'Grazie per tutto l'aiuto alla conferenza!'.</span><span class="sxs-lookup"><span data-stu-id="9b5f6-136">In the Description field, enter 'Thanks for all the help at the conference!'.</span></span>
21. <span data-ttu-id="9b5f6-137">Fare clic su Invia.</span><span class="sxs-lookup"><span data-stu-id="9b5f6-137">Click Send.</span></span>
