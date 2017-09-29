--- 
title: Attivare il processo di retribuzione per orario e presenze
description: In questa procedura viene illustrato come abilitare il processo di retribuzione per orario e presenze.
author: johanhoffmann
manager: AnnBe
ms.date: 02/12/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 22ce633f65847f10fbe507b71bfc2bb33f595501
ms.contentlocale: it-it
ms.lasthandoff: 08/29/2017

---
# <a name="enable-the-payroll-process-for-time-and-attendance"></a><span data-ttu-id="d4bbc-103">Attivare il processo di retribuzione per orario e presenze</span><span class="sxs-lookup"><span data-stu-id="d4bbc-103">Enable the payroll process for time and attendance</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="d4bbc-104">In questa procedura viene illustrato come abilitare il processo di retribuzione per orario e presenze.</span><span class="sxs-lookup"><span data-stu-id="d4bbc-104">This procedure shows how to enable the payroll process for time and attendance.</span></span> <span data-ttu-id="d4bbc-105">La società di dati dimostrativi utilizzata per creare questa procedura è USMF.</span><span class="sxs-lookup"><span data-stu-id="d4bbc-105">The demo data company used to create this procedure is USMF.</span></span>


## <a name="create-a-pay-type-with-a-related-pay-rate"></a><span data-ttu-id="d4bbc-106">Crea un tipo di retribuzione con una tariffa retributiva correlata</span><span class="sxs-lookup"><span data-stu-id="d4bbc-106">Create a pay type with a related pay rate</span></span>
1. <span data-ttu-id="d4bbc-107">Orario e presenze > Impostazioni > Retribuzioni > Tipi di retribuzione</span><span class="sxs-lookup"><span data-stu-id="d4bbc-107">Time and attendance > Setup > Payroll > Pay types</span></span>
2. <span data-ttu-id="d4bbc-108">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="d4bbc-108">Click New.</span></span>
3. <span data-ttu-id="d4bbc-109">Digitare un valore nel campo Tipo di retribuzione.</span><span class="sxs-lookup"><span data-stu-id="d4bbc-109">In the Pay type field, type a value.</span></span>
4. <span data-ttu-id="d4bbc-110">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="d4bbc-110">In the Description field, type a value.</span></span>
5. <span data-ttu-id="d4bbc-111">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="d4bbc-111">Click Save.</span></span>
6. <span data-ttu-id="d4bbc-112">Fare clic su Tariffe.</span><span class="sxs-lookup"><span data-stu-id="d4bbc-112">Click Rates.</span></span>
    * <span data-ttu-id="d4bbc-113">Le tariffe per i tipi di retribuzione vengono impostate per intervalli di tempo specifici ed è possibile definire tariffe specifiche per i lavoratori.</span><span class="sxs-lookup"><span data-stu-id="d4bbc-113">Rates for pay types are set up for specific time intervals, and individual rates can be created for workers.</span></span> <span data-ttu-id="d4bbc-114">Non è sempre necessario creare le tariffe per i tipi di retribuzione in Orario e presenze.</span><span class="sxs-lookup"><span data-stu-id="d4bbc-114">It is not always necessary to create rates for pay types in time and attendance.</span></span> <span data-ttu-id="d4bbc-115">È possibile infatti che questa informazione sia già disponibile nel sistema di gestione utilizzato per generare le retribuzioni.</span><span class="sxs-lookup"><span data-stu-id="d4bbc-115">This information may already exist in the payroll system that is used to generate wages.</span></span>  
7. <span data-ttu-id="d4bbc-116">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="d4bbc-116">Click New.</span></span>
8. <span data-ttu-id="d4bbc-117">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="d4bbc-117">In the list, mark the selected row.</span></span>
9. <span data-ttu-id="d4bbc-118">Nel campo Tariffa immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="d4bbc-118">In the Rate field, enter a number.</span></span>
10. <span data-ttu-id="d4bbc-119">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="d4bbc-119">Click Save.</span></span>

## <a name="create-a-pay-agreement"></a><span data-ttu-id="d4bbc-120">Creare un accordo salariale</span><span class="sxs-lookup"><span data-stu-id="d4bbc-120">Create a pay agreement</span></span>
1. <span data-ttu-id="d4bbc-121">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="d4bbc-121">Close the page.</span></span>
2. <span data-ttu-id="d4bbc-122">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="d4bbc-122">Close the page.</span></span>
3. <span data-ttu-id="d4bbc-123">Fare clic su Accordi salariali.</span><span class="sxs-lookup"><span data-stu-id="d4bbc-123">Go to Pay agreements.</span></span>
    * <span data-ttu-id="d4bbc-124">Orario e presenze > Impostazioni > Accordi salariali</span><span class="sxs-lookup"><span data-stu-id="d4bbc-124">Time and attendance > Setup > Pay agreements</span></span>  
4. <span data-ttu-id="d4bbc-125">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="d4bbc-125">Click New.</span></span>
5. <span data-ttu-id="d4bbc-126">Nel campo Accordo salariale digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="d4bbc-126">In the Pay agreement field, type a value.</span></span>
6. <span data-ttu-id="d4bbc-127">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="d4bbc-127">In the Description field, type a value.</span></span>
7. <span data-ttu-id="d4bbc-128">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="d4bbc-128">Click Save.</span></span>
8. <span data-ttu-id="d4bbc-129">Fare clic su Righe accordo.</span><span class="sxs-lookup"><span data-stu-id="d4bbc-129">Click Agreement lines.</span></span>
9. <span data-ttu-id="d4bbc-130">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="d4bbc-130">Click New.</span></span>
10. <span data-ttu-id="d4bbc-131">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="d4bbc-131">In the list, mark the selected row.</span></span>
11. <span data-ttu-id="d4bbc-132">Nel campo Tipo profilo immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="d4bbc-132">In the Profile type field, enter or select a value.</span></span>
12. <span data-ttu-id="d4bbc-133">Nel campo Tipo di retribuzione immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="d4bbc-133">In the Pay type field, enter or select a value.</span></span>

## <a name="set-up-pay-agreement-for-time-and-registration-worker"></a><span data-ttu-id="d4bbc-134">Impostare l'accordo salariale per il lavoratore per la registrazione e le ore</span><span class="sxs-lookup"><span data-stu-id="d4bbc-134">Set up pay agreement for time and registration worker</span></span>
1. <span data-ttu-id="d4bbc-135">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="d4bbc-135">Close the page.</span></span>
2. <span data-ttu-id="d4bbc-136">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="d4bbc-136">Close the page.</span></span>
3. <span data-ttu-id="d4bbc-137">Fare clic su Lavoratori per registrazione ore.</span><span class="sxs-lookup"><span data-stu-id="d4bbc-137">Go to Time registration workers.</span></span>
    * <span data-ttu-id="d4bbc-138">Orario e presenze > Impostazioni > Lavoratori per registrazione ore</span><span class="sxs-lookup"><span data-stu-id="d4bbc-138">Time and attendance > Setup > Time registration workers</span></span>  
4. <span data-ttu-id="d4bbc-139">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="d4bbc-139">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="d4bbc-140">Fare clic sulla scheda Impiego.</span><span class="sxs-lookup"><span data-stu-id="d4bbc-140">Click the Employment tab.</span></span>
6. <span data-ttu-id="d4bbc-141">Espandere la sezione Registrazione ore.</span><span class="sxs-lookup"><span data-stu-id="d4bbc-141">Expand the Time registration section.</span></span>
7. <span data-ttu-id="d4bbc-142">Fare clic su Modifica.</span><span class="sxs-lookup"><span data-stu-id="d4bbc-142">Click Edit.</span></span>
8. <span data-ttu-id="d4bbc-143">Nel campo Accordo salariale immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="d4bbc-143">In the Pay agreement field, enter or select a value.</span></span>


