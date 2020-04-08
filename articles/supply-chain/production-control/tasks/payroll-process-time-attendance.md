---
title: Attivare il processo di retribuzione per orario e presenze
description: In questa procedura viene illustrato come abilitare il processo di retribuzione per orario e presenze.
author: johanhoffmann
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: JmgPayTable, JmgPayRate, JmgPayAgreementTable, JmgPayAgreementLine, HcmWorker
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2df4695b796b4e96e01fe5dac538b344cb76b910
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/18/2020
ms.locfileid: "3146723"
---
# <a name="enable-the-payroll-process-for-time-and-attendance"></a><span data-ttu-id="5d051-103">Attivare il processo di retribuzione per orario e presenze</span><span class="sxs-lookup"><span data-stu-id="5d051-103">Enable the payroll process for time and attendance</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="5d051-104">In questa procedura viene illustrato come abilitare il processo di retribuzione per orario e presenze.</span><span class="sxs-lookup"><span data-stu-id="5d051-104">This procedure shows how to enable the payroll process for time and attendance.</span></span> <span data-ttu-id="5d051-105">La società di dati dimostrativi utilizzata per creare questa procedura è USMF.</span><span class="sxs-lookup"><span data-stu-id="5d051-105">The demo data company used to create this procedure is USMF.</span></span>


## <a name="create-a-pay-type-with-a-related-pay-rate"></a><span data-ttu-id="5d051-106">Crea un tipo di retribuzione con una tariffa retributiva correlata</span><span class="sxs-lookup"><span data-stu-id="5d051-106">Create a pay type with a related pay rate</span></span>
1. <span data-ttu-id="5d051-107">Orario e presenze > Impostazioni > Retribuzioni > Tipi di retribuzione</span><span class="sxs-lookup"><span data-stu-id="5d051-107">Time and attendance > Setup > Payroll > Pay types</span></span>
2. <span data-ttu-id="5d051-108">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="5d051-108">Click New.</span></span>
3. <span data-ttu-id="5d051-109">Digitare un valore nel campo Tipo di retribuzione.</span><span class="sxs-lookup"><span data-stu-id="5d051-109">In the Pay type field, type a value.</span></span>
4. <span data-ttu-id="5d051-110">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="5d051-110">In the Description field, type a value.</span></span>
5. <span data-ttu-id="5d051-111">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="5d051-111">Click Save.</span></span>
6. <span data-ttu-id="5d051-112">Fare clic su Tariffe.</span><span class="sxs-lookup"><span data-stu-id="5d051-112">Click Rates.</span></span>
    * <span data-ttu-id="5d051-113">Le tariffe per i tipi di retribuzione vengono impostate per intervalli di tempo specifici ed è possibile definire tariffe specifiche per i lavoratori.</span><span class="sxs-lookup"><span data-stu-id="5d051-113">Rates for pay types are set up for specific time intervals, and individual rates can be created for workers.</span></span> <span data-ttu-id="5d051-114">Non è sempre necessario creare le tariffe per i tipi di retribuzione in Orario e presenze.</span><span class="sxs-lookup"><span data-stu-id="5d051-114">It is not always necessary to create rates for pay types in time and attendance.</span></span> <span data-ttu-id="5d051-115">È possibile infatti che questa informazione sia già disponibile nel sistema di gestione utilizzato per generare le retribuzioni.</span><span class="sxs-lookup"><span data-stu-id="5d051-115">This information may already exist in the payroll system that is used to generate wages.</span></span>  
7. <span data-ttu-id="5d051-116">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="5d051-116">Click New.</span></span>
8. <span data-ttu-id="5d051-117">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="5d051-117">In the list, mark the selected row.</span></span>
9. <span data-ttu-id="5d051-118">Nel campo Tariffa immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="5d051-118">In the Rate field, enter a number.</span></span>
10. <span data-ttu-id="5d051-119">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="5d051-119">Click Save.</span></span>

## <a name="create-a-pay-agreement"></a><span data-ttu-id="5d051-120">Creare un accordo salariale</span><span class="sxs-lookup"><span data-stu-id="5d051-120">Create a pay agreement</span></span>
1. <span data-ttu-id="5d051-121">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="5d051-121">Close the page.</span></span>
2. <span data-ttu-id="5d051-122">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="5d051-122">Close the page.</span></span>
3. <span data-ttu-id="5d051-123">Fare clic su Accordi salariali.</span><span class="sxs-lookup"><span data-stu-id="5d051-123">Go to Pay agreements.</span></span>
    * <span data-ttu-id="5d051-124">Orario e presenze > Impostazioni > Accordi salariali</span><span class="sxs-lookup"><span data-stu-id="5d051-124">Time and attendance > Setup > Pay agreements</span></span>  
4. <span data-ttu-id="5d051-125">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="5d051-125">Click New.</span></span>
5. <span data-ttu-id="5d051-126">Nel campo Accordo salariale digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="5d051-126">In the Pay agreement field, type a value.</span></span>
6. <span data-ttu-id="5d051-127">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="5d051-127">In the Description field, type a value.</span></span>
7. <span data-ttu-id="5d051-128">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="5d051-128">Click Save.</span></span>
8. <span data-ttu-id="5d051-129">Fare clic su Righe accordo.</span><span class="sxs-lookup"><span data-stu-id="5d051-129">Click Agreement lines.</span></span>
9. <span data-ttu-id="5d051-130">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="5d051-130">Click New.</span></span>
10. <span data-ttu-id="5d051-131">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="5d051-131">In the list, mark the selected row.</span></span>
11. <span data-ttu-id="5d051-132">Nel campo Tipo profilo immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="5d051-132">In the Profile type field, enter or select a value.</span></span>
12. <span data-ttu-id="5d051-133">Nel campo Tipo di retribuzione immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="5d051-133">In the Pay type field, enter or select a value.</span></span>

## <a name="set-up-pay-agreement-for-time-and-registration-worker"></a><span data-ttu-id="5d051-134">Impostare l'accordo salariale per il lavoratore per la registrazione e le ore</span><span class="sxs-lookup"><span data-stu-id="5d051-134">Set up pay agreement for time and registration worker</span></span>
1. <span data-ttu-id="5d051-135">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="5d051-135">Close the page.</span></span>
2. <span data-ttu-id="5d051-136">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="5d051-136">Close the page.</span></span>
3. <span data-ttu-id="5d051-137">Fare clic su Lavoratori per registrazione ore.</span><span class="sxs-lookup"><span data-stu-id="5d051-137">Go to Time registration workers.</span></span>
    * <span data-ttu-id="5d051-138">Orario e presenze > Impostazioni > Lavoratori per registrazione ore</span><span class="sxs-lookup"><span data-stu-id="5d051-138">Time and attendance > Setup > Time registration workers</span></span>  
4. <span data-ttu-id="5d051-139">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="5d051-139">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="5d051-140">Fare clic sulla scheda Impiego.</span><span class="sxs-lookup"><span data-stu-id="5d051-140">Click the Employment tab.</span></span>
6. <span data-ttu-id="5d051-141">Espandere la sezione Registrazione ore.</span><span class="sxs-lookup"><span data-stu-id="5d051-141">Expand the Time registration section.</span></span>
7. <span data-ttu-id="5d051-142">Fare clic su Modifica.</span><span class="sxs-lookup"><span data-stu-id="5d051-142">Click Edit.</span></span>
8. <span data-ttu-id="5d051-143">Nel campo Accordo salariale immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="5d051-143">In the Pay agreement field, enter or select a value.</span></span>

