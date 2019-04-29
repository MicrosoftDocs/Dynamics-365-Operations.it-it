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
ms.openlocfilehash: 92e4f9697fc00798d917db6f7f50d7e3b8739233
ms.sourcegitcommit: 608e68b603afef9eb98d8fb25e90109c2473ef87
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2019
ms.locfileid: "858654"
---
# <a name="create-a-closed-ended-question"></a><span data-ttu-id="05fe1-103">Creare una domanda chiusa</span><span class="sxs-lookup"><span data-stu-id="05fe1-103">Create a closed ended question</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="05fe1-104">Le domande chiuse consentono di fornire opzioni tra cui l'intervistato può scegliere.</span><span class="sxs-lookup"><span data-stu-id="05fe1-104">Closed-ended questions allow you to provide options for the respondent to choose from.</span></span> <span data-ttu-id="05fe1-105">È necessario innanzitutto creare il gruppo di risposte, quindi creare la domanda che utilizzerà il gruppo di risposte.</span><span class="sxs-lookup"><span data-stu-id="05fe1-105">First, you need to create the Answer group with the answers, then create the question that will use the answer group.</span></span> <span data-ttu-id="05fe1-106">La società di dati dimostrativi utilizzata per creare questa procedura è USMF.</span><span class="sxs-lookup"><span data-stu-id="05fe1-106">The demo data company used to create this procedure is USMF.</span></span>


## <a name="create-an-answer-group"></a><span data-ttu-id="05fe1-107">Creare un gruppo di risposte</span><span class="sxs-lookup"><span data-stu-id="05fe1-107">Create an answer group</span></span>
1. <span data-ttu-id="05fe1-108">Andare a Questionario > Progettazione > Gruppi di risposte.</span><span class="sxs-lookup"><span data-stu-id="05fe1-108">Go to Questionnaire > Design > Answer groups.</span></span>
2. <span data-ttu-id="05fe1-109">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="05fe1-109">Click New.</span></span>
3. <span data-ttu-id="05fe1-110">Digitare un valore nel campo Gruppo di risposte.</span><span class="sxs-lookup"><span data-stu-id="05fe1-110">In the Answer group field, type a value.</span></span>
4. <span data-ttu-id="05fe1-111">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="05fe1-111">In the Description field, type a value.</span></span>
    * <span data-ttu-id="05fe1-112">Utilizzare la funzionalità dei parametri casuali per posizionare in modo casuale le risposte un ordine diverso ogni volta che il gruppo di risposte viene utilizzato per una domanda.</span><span class="sxs-lookup"><span data-stu-id="05fe1-112">Use the Randomize functionality to randomly place the answers in a different order each time the answer group is used for a question.</span></span>  
5. <span data-ttu-id="05fe1-113">Fare clic su Risposta.</span><span class="sxs-lookup"><span data-stu-id="05fe1-113">Click Answer.</span></span>
6. <span data-ttu-id="05fe1-114">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="05fe1-114">Click New.</span></span>
    * <span data-ttu-id="05fe1-115">Un numero progressivo controlla l'ordine in cui le risposte vengono visualizzate, a meno che l'opzione Parametri casuali non sia selezionata per il gruppo di risposte.</span><span class="sxs-lookup"><span data-stu-id="05fe1-115">Sequence number controls the order in which the answers are displayed, unless Randomize is selected for the Answer group.</span></span>  
    * <span data-ttu-id="05fe1-116">Alle risposte possono essere assegnati punti da utilizzare per l'assegnazione di punteggio nel questionario.</span><span class="sxs-lookup"><span data-stu-id="05fe1-116">Points can be awarded to answers for use in scoring the questionnaire.</span></span>  
7. <span data-ttu-id="05fe1-117">Nel campo Punti immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="05fe1-117">In the Points field, enter a number.</span></span>
    * <span data-ttu-id="05fe1-118">La risposta corretta può essere contrassegnata per indicare che la risposta selezionata è quella corretta.</span><span class="sxs-lookup"><span data-stu-id="05fe1-118">The correct answer can be marked to indicate that the selected answer is the correct one.</span></span> <span data-ttu-id="05fe1-119">Questo può essere utilizzato per assegnare punteggio nel questionario.</span><span class="sxs-lookup"><span data-stu-id="05fe1-119">This can be used for scoring the questionnaire.</span></span>  
8. <span data-ttu-id="05fe1-120">Digitare un valore nel campo Risposta.</span><span class="sxs-lookup"><span data-stu-id="05fe1-120">In the Answer field, type a value.</span></span>
    * <span data-ttu-id="05fe1-121">Continuare a creare opzioni di selezione della risposta per il gruppo di risposte.</span><span class="sxs-lookup"><span data-stu-id="05fe1-121">Continue to create answer selection options for the answer group.</span></span>  
9. <span data-ttu-id="05fe1-122">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="05fe1-122">Click New.</span></span>
10. <span data-ttu-id="05fe1-123">Nel campo Punti immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="05fe1-123">In the Points field, enter a number.</span></span>
11. <span data-ttu-id="05fe1-124">Digitare un valore nel campo Risposta.</span><span class="sxs-lookup"><span data-stu-id="05fe1-124">In the Answer field, type a value.</span></span>
12. <span data-ttu-id="05fe1-125">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="05fe1-125">Click New.</span></span>
13. <span data-ttu-id="05fe1-126">Nel campo Punti immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="05fe1-126">In the Points field, enter a number.</span></span>
14. <span data-ttu-id="05fe1-127">Digitare un valore nel campo Risposta.</span><span class="sxs-lookup"><span data-stu-id="05fe1-127">In the Answer field, type a value.</span></span>
15. <span data-ttu-id="05fe1-128">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="05fe1-128">Click New.</span></span>
16. <span data-ttu-id="05fe1-129">Nel campo Punti immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="05fe1-129">In the Points field, enter a number.</span></span>
17. <span data-ttu-id="05fe1-130">Digitare un valore nel campo Risposta.</span><span class="sxs-lookup"><span data-stu-id="05fe1-130">In the Answer field, type a value.</span></span>
18. <span data-ttu-id="05fe1-131">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="05fe1-131">Click New.</span></span>
19. <span data-ttu-id="05fe1-132">Nel campo Punti immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="05fe1-132">In the Points field, enter a number.</span></span>
20. <span data-ttu-id="05fe1-133">Digitare un valore nel campo Risposta.</span><span class="sxs-lookup"><span data-stu-id="05fe1-133">In the Answer field, type a value.</span></span>
21. <span data-ttu-id="05fe1-134">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="05fe1-134">Close the page.</span></span>
22. <span data-ttu-id="05fe1-135">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="05fe1-135">Close the page.</span></span>

## <a name="create-the-question"></a><span data-ttu-id="05fe1-136">Creare la domanda</span><span class="sxs-lookup"><span data-stu-id="05fe1-136">Create the question</span></span>
1. <span data-ttu-id="05fe1-137">Andare a Questionario > Progettazione > Domande.</span><span class="sxs-lookup"><span data-stu-id="05fe1-137">Go to Questionnaire > Design > Questions.</span></span>
2. <span data-ttu-id="05fe1-138">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="05fe1-138">Click New.</span></span>
3. <span data-ttu-id="05fe1-139">Utilizzare il campo Tipo per raggruppare domande correlate.</span><span class="sxs-lookup"><span data-stu-id="05fe1-139">Use the Type field to group related questions together.</span></span>
    * <span data-ttu-id="05fe1-140">È possibile utilizzare i tipi di input casella di controllo, pulsante alternativo o casella combinata per le domande chiuse.</span><span class="sxs-lookup"><span data-stu-id="05fe1-140">You can use input types of Check box, Alternative button, or Combo box for closed-ended questions.</span></span>  
4. <span data-ttu-id="05fe1-141">Nel campo Tipo di input selezionare un'opzione.</span><span class="sxs-lookup"><span data-stu-id="05fe1-141">In the Input type field, select an option.</span></span>
5. <span data-ttu-id="05fe1-142">Nel campo Gruppo di risposte immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="05fe1-142">In the Answer group field, enter or select a value.</span></span>
6. <span data-ttu-id="05fe1-143">Digitare un valore nel campo Testo.</span><span class="sxs-lookup"><span data-stu-id="05fe1-143">In the Text field, type a value.</span></span>

