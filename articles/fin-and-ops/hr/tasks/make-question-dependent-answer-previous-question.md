--- 
title: Fare una domanda in base alla risposta della domanda precedente
description: Le domande condizionali consentono di specificare la domanda successiva da presentare a un intervistato, in base alla risposta alla domanda precedente.
author: twheeloc
manager: AnnBe
ms.date: 02/12/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Operations, Talent
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: d3221a62079e719c1d9d6f2df8edf8c5ed5584b7
ms.contentlocale: it-it
ms.lasthandoff: 04/13/2018

---
# <a name="make-a-question-dependent-on-the-answer-of-the-previous-question"></a><span data-ttu-id="5da7e-103">Fare una domanda in base alla risposta della domanda precedente</span><span class="sxs-lookup"><span data-stu-id="5da7e-103">Make a question dependent on the answer of the previous question</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="5da7e-104">Le domande condizionali consentono di specificare la domanda successiva da presentare a un intervistato, in base alla risposta alla domanda precedente.</span><span class="sxs-lookup"><span data-stu-id="5da7e-104">Conditional questions allow you to specify what follow-up question will be presented to a respondent, based on the answer to the preceding question.</span></span> <span data-ttu-id="5da7e-105">Ad esempio, se si chiede "Preferisce caffè o tè?", una domanda successiva logica può essere determinata dalla scelta della risposta caffè o tè da parte dell'intervistato.</span><span class="sxs-lookup"><span data-stu-id="5da7e-105">For example, if you ask "Do you prefer coffee or tea," a logical follow-up question can be determined depending on whether the respondent selects coffee or tea as their answer.</span></span> <span data-ttu-id="5da7e-106">La società di dati dimostrativi utilizzata per creare questa procedura è USMF.</span><span class="sxs-lookup"><span data-stu-id="5da7e-106">The demo data company used to create this procedure is USMF.</span></span>


## <a name="find-the-existing-questionnaire"></a><span data-ttu-id="5da7e-107">Individuare il questionario esistente</span><span class="sxs-lookup"><span data-stu-id="5da7e-107">Find the existing questionnaire</span></span>
1. <span data-ttu-id="5da7e-108">Andare a Questionario > Progettazione > Questionari.</span><span class="sxs-lookup"><span data-stu-id="5da7e-108">Go to Questionnaire > Design > Questionnaires.</span></span>
2. <span data-ttu-id="5da7e-109">Nell'elenco selezionare il questionario WorkFH.</span><span class="sxs-lookup"><span data-stu-id="5da7e-109">In the list, select the WorkFH questionnaire.</span></span>

## <a name="add-all-questions-and-sub-questions-to-the-questionnaire"></a><span data-ttu-id="5da7e-110">Aggiungere tutte le domande e le domande secondarie al questionario</span><span class="sxs-lookup"><span data-stu-id="5da7e-110">Add all questions and sub-questions to the Questionnaire</span></span>
1. <span data-ttu-id="5da7e-111">Fare clic su Domande.</span><span class="sxs-lookup"><span data-stu-id="5da7e-111">Click Questions.</span></span>
2. <span data-ttu-id="5da7e-112">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="5da7e-112">Click New.</span></span>
3. <span data-ttu-id="5da7e-113">Nel campo Domanda selezionare il numero di domanda 00016.</span><span class="sxs-lookup"><span data-stu-id="5da7e-113">In the Question field, select question number 00016.</span></span>
4. <span data-ttu-id="5da7e-114">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="5da7e-114">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="5da7e-115">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="5da7e-115">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="5da7e-116">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="5da7e-116">Click Save.</span></span>
7. <span data-ttu-id="5da7e-117">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="5da7e-117">Close the page.</span></span>

## <a name="set-the-questionnaire-sequence-to-conditional-and-make-the-question-dependent-on-the-appropriate-question"></a><span data-ttu-id="5da7e-118">Impostare la sequenza del questionario su Condizionale e rendere la domanda dipendente dalla domanda appropriata</span><span class="sxs-lookup"><span data-stu-id="5da7e-118">Set the Questionnaire Sequence to Conditional and make the question dependent on the appropriate question</span></span>
1. <span data-ttu-id="5da7e-119">Fare clic su Modifica.</span><span class="sxs-lookup"><span data-stu-id="5da7e-119">Click Edit.</span></span>
2. <span data-ttu-id="5da7e-120">Espandere la sezione Impostazione.</span><span class="sxs-lookup"><span data-stu-id="5da7e-120">Expand the Setup section.</span></span>
3. <span data-ttu-id="5da7e-121">Nel campo Ordine domande selezionare "Condizionale".</span><span class="sxs-lookup"><span data-stu-id="5da7e-121">In the Question order field, select 'Conditional'.</span></span>
4. <span data-ttu-id="5da7e-122">Fare clic su Domanda condizionale.</span><span class="sxs-lookup"><span data-stu-id="5da7e-122">Click Conditional question.</span></span>
5. <span data-ttu-id="5da7e-123">Nella struttura selezionare "Domande\Spiegare i motivi della risposta precedente".</span><span class="sxs-lookup"><span data-stu-id="5da7e-123">In the tree, select 'Questions\Explain why you answered the previous question the way you did?'.</span></span>
6. <span data-ttu-id="5da7e-124">Nel campo Domanda primaria il numero di domanda 00009.</span><span class="sxs-lookup"><span data-stu-id="5da7e-124">In the Primary question field, select question 00009</span></span>
7. <span data-ttu-id="5da7e-125">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="5da7e-125">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="5da7e-126">Nel campo Risposta immettere l'ID della sequenza di risposta dell'opzione di risposta da cui si desidera che la domanda sia dipendente.</span><span class="sxs-lookup"><span data-stu-id="5da7e-126">In the Answer field, enter the answer sequence ID of the answer option you want to make the question dependent on.</span></span> <span data-ttu-id="5da7e-127">Ad esempio, immettere 1 per la prima opzione di risposta.</span><span class="sxs-lookup"><span data-stu-id="5da7e-127">For example, enter 1 for the first answer option.</span></span>
9. <span data-ttu-id="5da7e-128">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="5da7e-128">Click Save.</span></span>
10. <span data-ttu-id="5da7e-129">Nella struttura selezionare "Domande\Sono pagato equamente per il lavoro che svolgo".</span><span class="sxs-lookup"><span data-stu-id="5da7e-129">In the tree, select 'Questions\I am paid fairly for the work I do.'.</span></span>
    * <span data-ttu-id="5da7e-130">Si noti che la struttura delle domande viene aggiornata per visualizzare la dipendenza.</span><span class="sxs-lookup"><span data-stu-id="5da7e-130">Note that the question tree updated to show the dependency.</span></span>  


