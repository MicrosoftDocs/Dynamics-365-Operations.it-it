---
title: Creare una domanda chiusa
description: Le domande chiuse consentono di fornire opzioni tra cui l'intervistato può scegliere.
author: andreabichsel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KMAnswerCollection, KMAnswer, KMQuestion
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 55a41ae639970eb3324a5760af7f6dd5fb8f2ad5
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2020
ms.locfileid: "3009587"
---
# <a name="create-a-closed-ended-question"></a><span data-ttu-id="4d2be-103">Creare una domanda chiusa</span><span class="sxs-lookup"><span data-stu-id="4d2be-103">Create a closed ended question</span></span>



<span data-ttu-id="4d2be-104">Le domande chiuse consentono di fornire opzioni tra cui l'intervistato può scegliere.</span><span class="sxs-lookup"><span data-stu-id="4d2be-104">Closed-ended questions allow you to provide options for the respondent to choose from.</span></span> <span data-ttu-id="4d2be-105">È necessario innanzitutto creare il gruppo di risposte, quindi creare la domanda che utilizzerà il gruppo di risposte.</span><span class="sxs-lookup"><span data-stu-id="4d2be-105">First, you need to create the Answer group with the answers, then create the question that will use the answer group.</span></span> <span data-ttu-id="4d2be-106">La società di dati dimostrativi utilizzata per creare questa procedura è USMF.</span><span class="sxs-lookup"><span data-stu-id="4d2be-106">The demo data company used to create this procedure is USMF.</span></span>


## <a name="create-an-answer-group"></a><span data-ttu-id="4d2be-107">Creare un gruppo di risposte</span><span class="sxs-lookup"><span data-stu-id="4d2be-107">Create an answer group</span></span>
1. <span data-ttu-id="4d2be-108">Andare a Questionario > Progettazione > Gruppi di risposte.</span><span class="sxs-lookup"><span data-stu-id="4d2be-108">Go to Questionnaire > Design > Answer groups.</span></span>
2. <span data-ttu-id="4d2be-109">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="4d2be-109">Click New.</span></span>
3. <span data-ttu-id="4d2be-110">Digitare un valore nel campo Gruppo di risposte.</span><span class="sxs-lookup"><span data-stu-id="4d2be-110">In the Answer group field, type a value.</span></span>
4. <span data-ttu-id="4d2be-111">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="4d2be-111">In the Description field, type a value.</span></span>
    * <span data-ttu-id="4d2be-112">Utilizzare la funzionalità dei parametri casuali per posizionare in modo casuale le risposte un ordine diverso ogni volta che il gruppo di risposte viene utilizzato per una domanda.</span><span class="sxs-lookup"><span data-stu-id="4d2be-112">Use the Randomize functionality to randomly place the answers in a different order each time the answer group is used for a question.</span></span>  
5. <span data-ttu-id="4d2be-113">Fare clic su Risposta.</span><span class="sxs-lookup"><span data-stu-id="4d2be-113">Click Answer.</span></span>
6. <span data-ttu-id="4d2be-114">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="4d2be-114">Click New.</span></span>
    * <span data-ttu-id="4d2be-115">Un numero progressivo controlla l'ordine in cui le risposte vengono visualizzate, a meno che l'opzione Parametri casuali non sia selezionata per il gruppo di risposte.</span><span class="sxs-lookup"><span data-stu-id="4d2be-115">Sequence number controls the order in which the answers are displayed, unless Randomize is selected for the Answer group.</span></span>  
    * <span data-ttu-id="4d2be-116">Alle risposte possono essere assegnati punti da utilizzare per l'assegnazione di punteggio nel questionario.</span><span class="sxs-lookup"><span data-stu-id="4d2be-116">Points can be awarded to answers for use in scoring the questionnaire.</span></span>  
7. <span data-ttu-id="4d2be-117">Nel campo Punti immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="4d2be-117">In the Points field, enter a number.</span></span>
    * <span data-ttu-id="4d2be-118">La risposta corretta può essere contrassegnata per indicare che la risposta selezionata è quella corretta.</span><span class="sxs-lookup"><span data-stu-id="4d2be-118">The correct answer can be marked to indicate that the selected answer is the correct one.</span></span> <span data-ttu-id="4d2be-119">Questo può essere utilizzato per assegnare punteggio nel questionario.</span><span class="sxs-lookup"><span data-stu-id="4d2be-119">This can be used for scoring the questionnaire.</span></span>  
8. <span data-ttu-id="4d2be-120">Digitare un valore nel campo Risposta.</span><span class="sxs-lookup"><span data-stu-id="4d2be-120">In the Answer field, type a value.</span></span>
    * <span data-ttu-id="4d2be-121">Continuare a creare opzioni di selezione della risposta per il gruppo di risposte.</span><span class="sxs-lookup"><span data-stu-id="4d2be-121">Continue to create answer selection options for the answer group.</span></span>  
9. <span data-ttu-id="4d2be-122">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="4d2be-122">Click New.</span></span>
10. <span data-ttu-id="4d2be-123">Nel campo Punti immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="4d2be-123">In the Points field, enter a number.</span></span>
11. <span data-ttu-id="4d2be-124">Digitare un valore nel campo Risposta.</span><span class="sxs-lookup"><span data-stu-id="4d2be-124">In the Answer field, type a value.</span></span>
12. <span data-ttu-id="4d2be-125">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="4d2be-125">Click New.</span></span>
13. <span data-ttu-id="4d2be-126">Nel campo Punti immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="4d2be-126">In the Points field, enter a number.</span></span>
14. <span data-ttu-id="4d2be-127">Digitare un valore nel campo Risposta.</span><span class="sxs-lookup"><span data-stu-id="4d2be-127">In the Answer field, type a value.</span></span>
15. <span data-ttu-id="4d2be-128">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="4d2be-128">Click New.</span></span>
16. <span data-ttu-id="4d2be-129">Nel campo Punti immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="4d2be-129">In the Points field, enter a number.</span></span>
17. <span data-ttu-id="4d2be-130">Digitare un valore nel campo Risposta.</span><span class="sxs-lookup"><span data-stu-id="4d2be-130">In the Answer field, type a value.</span></span>
18. <span data-ttu-id="4d2be-131">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="4d2be-131">Click New.</span></span>
19. <span data-ttu-id="4d2be-132">Nel campo Punti immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="4d2be-132">In the Points field, enter a number.</span></span>
20. <span data-ttu-id="4d2be-133">Digitare un valore nel campo Risposta.</span><span class="sxs-lookup"><span data-stu-id="4d2be-133">In the Answer field, type a value.</span></span>
21. <span data-ttu-id="4d2be-134">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="4d2be-134">Close the page.</span></span>
22. <span data-ttu-id="4d2be-135">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="4d2be-135">Close the page.</span></span>

## <a name="create-the-question"></a><span data-ttu-id="4d2be-136">Creare la domanda</span><span class="sxs-lookup"><span data-stu-id="4d2be-136">Create the question</span></span>
1. <span data-ttu-id="4d2be-137">Andare a Questionario > Progettazione > Domande.</span><span class="sxs-lookup"><span data-stu-id="4d2be-137">Go to Questionnaire > Design > Questions.</span></span>
2. <span data-ttu-id="4d2be-138">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="4d2be-138">Click New.</span></span>
3. <span data-ttu-id="4d2be-139">Utilizzare il campo Tipo per raggruppare domande correlate.</span><span class="sxs-lookup"><span data-stu-id="4d2be-139">Use the Type field to group related questions together.</span></span>
    * <span data-ttu-id="4d2be-140">È possibile utilizzare i tipi di input casella di controllo, pulsante alternativo o casella combinata per le domande chiuse.</span><span class="sxs-lookup"><span data-stu-id="4d2be-140">You can use input types of Check box, Alternative button, or Combo box for closed-ended questions.</span></span>  
4. <span data-ttu-id="4d2be-141">Nel campo Tipo di input selezionare un'opzione.</span><span class="sxs-lookup"><span data-stu-id="4d2be-141">In the Input type field, select an option.</span></span>
5. <span data-ttu-id="4d2be-142">Nel campo Gruppo di risposte immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="4d2be-142">In the Answer group field, enter or select a value.</span></span>
6. <span data-ttu-id="4d2be-143">Digitare un valore nel campo Testo.</span><span class="sxs-lookup"><span data-stu-id="4d2be-143">In the Text field, type a value.</span></span>
