---
title: Creare e assegnare i criteri di comportamento costi a un'unità di controllo costi
description: Il comportamento costo è la classificazione del costo come fisso o variabile.
author: ShylaThompson
manager: AnnBe
ms.date: 06/27/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c7b39b7649aaef0d354b61e3d70b6cac887282ed
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2019
ms.locfileid: "313821"
---
# <a name="create-and-assign-a-cost-behavior-policy-to-a-cost-control-unit"></a><span data-ttu-id="7e3c4-103">Creare e assegnare i criteri di comportamento costi a un'unità di controllo costi</span><span class="sxs-lookup"><span data-stu-id="7e3c4-103">Create and assign a cost behavior policy to a cost control unit</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="7e3c4-104">Il comportamento costo è la classificazione del costo come fisso o variabile.</span><span class="sxs-lookup"><span data-stu-id="7e3c4-104">Cost behavior is the classification of costs as either fixed or variable.</span></span> <span data-ttu-id="7e3c4-105">Affinché i criteri diventino effettivi, i criteri e le regole corrispondenti devono essere assegnati a un'unità di controllo costi.</span><span class="sxs-lookup"><span data-stu-id="7e3c4-105">A policy and the corresponding rules have to be assigned to a cost control unit for the policy to become effective.</span></span> <span data-ttu-id="7e3c4-106">Utilizzare questa procedura per creare i criteri e quindi per assegnarli a un'unità di controllo costi.</span><span class="sxs-lookup"><span data-stu-id="7e3c4-106">Use this procedure to create a policy and then assign the policy to a cost control unit.</span></span>


## <a name="create-a-cost-behavior-hierarchy"></a><span data-ttu-id="7e3c4-107">Creare una gerarchia di comportamento costo</span><span class="sxs-lookup"><span data-stu-id="7e3c4-107">Create a cost behavior hierarchy</span></span>
1. <span data-ttu-id="7e3c4-108">Andare a Contabilità industriale > Dimensioni > Gerarchie di dimensioni.</span><span class="sxs-lookup"><span data-stu-id="7e3c4-108">Go to Cost accounting > Dimensions > Dimension hierarchies.</span></span>
2. <span data-ttu-id="7e3c4-109">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="7e3c4-109">Click New.</span></span>
3. <span data-ttu-id="7e3c4-110">Fare clic su Crea.</span><span class="sxs-lookup"><span data-stu-id="7e3c4-110">Click Create.</span></span>
4. <span data-ttu-id="7e3c4-111">Nel campo Nome gerarchia dimensioni digitare "Gerarchia di comportamenti costo".</span><span class="sxs-lookup"><span data-stu-id="7e3c4-111">In the Dimension hierarchy name field, type 'Cost behavior hierarchy'.</span></span>
5. <span data-ttu-id="7e3c4-112">Nel campo Dimensione immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="7e3c4-112">In the Dimension field, enter or select a value.</span></span>
    * <span data-ttu-id="7e3c4-113">Selezionare Elementi di costo.</span><span class="sxs-lookup"><span data-stu-id="7e3c4-113">Select Cost elements.</span></span>  
6. <span data-ttu-id="7e3c4-114">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="7e3c4-114">Click Save.</span></span>
7. <span data-ttu-id="7e3c4-115">Fare clic su Visualizza gerarchia.</span><span class="sxs-lookup"><span data-stu-id="7e3c4-115">Click View hierarchy.</span></span>
8. <span data-ttu-id="7e3c4-116">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="7e3c4-116">Click New.</span></span>
9. <span data-ttu-id="7e3c4-117">Digitare un valore nel campo Nome nodo.</span><span class="sxs-lookup"><span data-stu-id="7e3c4-117">In the Node name field, type a value.</span></span>
    * <span data-ttu-id="7e3c4-118">Immettere il costo fisso.</span><span class="sxs-lookup"><span data-stu-id="7e3c4-118">Enter Fixed cost.</span></span>  
10. <span data-ttu-id="7e3c4-119">Nella struttura selezionare "Cost behavior hierarchy".</span><span class="sxs-lookup"><span data-stu-id="7e3c4-119">In the tree, select 'Cost behavior hierarchy'.</span></span>
11. <span data-ttu-id="7e3c4-120">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="7e3c4-120">Click New.</span></span>
12. <span data-ttu-id="7e3c4-121">Digitare un valore nel campo Nome nodo.</span><span class="sxs-lookup"><span data-stu-id="7e3c4-121">In the Node name field, type a value.</span></span>
    * <span data-ttu-id="7e3c4-122">Immettere il costo variabile.</span><span class="sxs-lookup"><span data-stu-id="7e3c4-122">Enter Variable cost.</span></span>  
13. <span data-ttu-id="7e3c4-123">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="7e3c4-123">Click Save.</span></span>
14. <span data-ttu-id="7e3c4-124">Nella struttura selezionare "Gerarchia di comportamenti costo\Costo fisso".</span><span class="sxs-lookup"><span data-stu-id="7e3c4-124">In the tree, select 'Cost behavior hierarchy\Fixed cost'.</span></span>
15. <span data-ttu-id="7e3c4-125">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="7e3c4-125">Click New.</span></span>
16. <span data-ttu-id="7e3c4-126">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="7e3c4-126">In the list, mark the selected row.</span></span>
17. <span data-ttu-id="7e3c4-127">Nel campo Membro di dimensione di inizio immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="7e3c4-127">In the From dimension member field, enter or select a value.</span></span>
    * <span data-ttu-id="7e3c4-128">L'intervallo dei membri di dimensione può non essere continuo, ma i membri non possono sovrapporsi.</span><span class="sxs-lookup"><span data-stu-id="7e3c4-128">The range of dimension members can contain gaps, but the members cannot overlap.</span></span>  
18. <span data-ttu-id="7e3c4-129">Nel campo Membro di dimensione di fine immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="7e3c4-129">In the To dimension member field, enter or select a value.</span></span>
    * <span data-ttu-id="7e3c4-130">L'intervallo dei membri di dimensione può non essere continuo, ma i membri non possono sovrapporsi.</span><span class="sxs-lookup"><span data-stu-id="7e3c4-130">The range of dimension members can contain gaps, but the members cannot overlap.</span></span>  
19. <span data-ttu-id="7e3c4-131">Nella struttura selezionare "Gerarchia di comportamenti costo\Costo variabile".</span><span class="sxs-lookup"><span data-stu-id="7e3c4-131">In the tree, select 'Cost behavior hierarchy\Variable cost'.</span></span>
20. <span data-ttu-id="7e3c4-132">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="7e3c4-132">Click New.</span></span>
21. <span data-ttu-id="7e3c4-133">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="7e3c4-133">In the list, mark the selected row.</span></span>
22. <span data-ttu-id="7e3c4-134">Nel campo Membro di dimensione di inizio immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="7e3c4-134">In the From dimension member field, enter or select a value.</span></span>
    * <span data-ttu-id="7e3c4-135">L'intervallo dei membri di dimensione può non essere continuo, ma i membri non possono sovrapporsi.</span><span class="sxs-lookup"><span data-stu-id="7e3c4-135">The range of dimension members can contain gaps, but the members cannot overlap.</span></span>  
23. <span data-ttu-id="7e3c4-136">Nel campo Membro di dimensione di fine immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="7e3c4-136">In the To dimension member field, enter or select a value.</span></span>
    * <span data-ttu-id="7e3c4-137">L'intervallo dei membri di dimensione può non essere continuo, ma i membri non possono sovrapporsi.</span><span class="sxs-lookup"><span data-stu-id="7e3c4-137">The range of dimension members can contain gaps, but the members cannot overlap.</span></span>  
24. <span data-ttu-id="7e3c4-138">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="7e3c4-138">Click Save.</span></span>

## <a name="create-the-policy-and-rules"></a><span data-ttu-id="7e3c4-139">Creare i criteri e le regole.</span><span class="sxs-lookup"><span data-stu-id="7e3c4-139">Create the policy and rules</span></span>
1. <span data-ttu-id="7e3c4-140">Andare a Contabilità industriale > Criteri > Criteri di comportamento costo.</span><span class="sxs-lookup"><span data-stu-id="7e3c4-140">Go to Cost accounting > Policies > Cost behavior policies.</span></span>
2. <span data-ttu-id="7e3c4-141">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="7e3c4-141">Click New.</span></span>
3. <span data-ttu-id="7e3c4-142">Digitare un valore nel campo Nome criteri.</span><span class="sxs-lookup"><span data-stu-id="7e3c4-142">In the Policy name field, type a value.</span></span>
4. <span data-ttu-id="7e3c4-143">Nel campo Gerarchia dimensioni di elemento di costo immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="7e3c4-143">In the Cost element dimension hierarchy field, enter or select a value.</span></span>
    * <span data-ttu-id="7e3c4-144">Selezionare la gerarchia di criteri creata.</span><span class="sxs-lookup"><span data-stu-id="7e3c4-144">Select the policy hierarchy that you just created.</span></span>  
5. <span data-ttu-id="7e3c4-145">Nel campo Gerarchia dimensioni di oggetto di costo immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="7e3c4-145">In the Cost object dimension hierarchy field, enter or select a value.</span></span>
    * <span data-ttu-id="7e3c4-146">Selezionare Organizzazione.</span><span class="sxs-lookup"><span data-stu-id="7e3c4-146">Select Organization.</span></span>  
6. <span data-ttu-id="7e3c4-147">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="7e3c4-147">Click Save.</span></span>
7. <span data-ttu-id="7e3c4-148">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="7e3c4-148">Click New.</span></span>
8. <span data-ttu-id="7e3c4-149">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="7e3c4-149">In the list, mark the selected row.</span></span>
9. <span data-ttu-id="7e3c4-150">Nel campo Nodo gerarchia dimensioni di elemento di costo immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="7e3c4-150">In the Cost element dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="7e3c4-151">Espande la gerarchia per selezionare il costo variabile.</span><span class="sxs-lookup"><span data-stu-id="7e3c4-151">Expand the hierarchy to select Variable cost.</span></span>  
10. <span data-ttu-id="7e3c4-152">Nel campo Nodo gerarchia dimensioni di oggetto di costo immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="7e3c4-152">In the Cost object dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="7e3c4-153">Per impostazione predefinita, la percentuale variabile è pari al 100%.</span><span class="sxs-lookup"><span data-stu-id="7e3c4-153">By default, the variable percentage is 100 percent.</span></span>  
11. <span data-ttu-id="7e3c4-154">Fare clic su Assegnazioni criteri per unità di controllo costi.</span><span class="sxs-lookup"><span data-stu-id="7e3c4-154">Click Policy assignments for cost control unit.</span></span>
12. <span data-ttu-id="7e3c4-155">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="7e3c4-155">Click New.</span></span>
13. <span data-ttu-id="7e3c4-156">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="7e3c4-156">In the list, mark the selected row.</span></span>
14. <span data-ttu-id="7e3c4-157">Immettere una data nel campo Valido dalla data di registrazione.</span><span class="sxs-lookup"><span data-stu-id="7e3c4-157">In the Valid from accounting date field, enter a date.</span></span>
    * <span data-ttu-id="7e3c4-158">Le regole hanno una data di validità e un utente o il sistema può farle scadere se ne viene creata una nuova versione.</span><span class="sxs-lookup"><span data-stu-id="7e3c4-158">The rules are date-effective, and a user or the system can expire a rule if a newer version is created.</span></span>  
15. <span data-ttu-id="7e3c4-159">Nel campo Unità di controllo costi immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="7e3c4-159">In the Cost control unit field, enter or select a value.</span></span>
16. <span data-ttu-id="7e3c4-160">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="7e3c4-160">Click Save.</span></span>

