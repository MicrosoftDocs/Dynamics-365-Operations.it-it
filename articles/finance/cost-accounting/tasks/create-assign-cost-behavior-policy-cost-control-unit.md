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
ms.search.form: CAMCostBehaviorRule
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 58f888a373af33832c24518fbb5483c3de2d1a58
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5208705"
---
# <a name="create-and-assign-a-cost-behavior-policy-to-a-cost-control-unit"></a><span data-ttu-id="7adfe-103">Creare e assegnare i criteri di comportamento costi a un'unità di controllo costi</span><span class="sxs-lookup"><span data-stu-id="7adfe-103">Create and assign a cost behavior policy to a cost control unit</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="7adfe-104">Il comportamento costo è la classificazione del costo come fisso o variabile.</span><span class="sxs-lookup"><span data-stu-id="7adfe-104">Cost behavior is the classification of costs as either fixed or variable.</span></span> <span data-ttu-id="7adfe-105">Affinché i criteri diventino effettivi, i criteri e le regole corrispondenti devono essere assegnati a un'unità di controllo costi.</span><span class="sxs-lookup"><span data-stu-id="7adfe-105">A policy and the corresponding rules have to be assigned to a cost control unit for the policy to become effective.</span></span> <span data-ttu-id="7adfe-106">Utilizzare questa procedura per creare i criteri e quindi per assegnarli a un'unità di controllo costi.</span><span class="sxs-lookup"><span data-stu-id="7adfe-106">Use this procedure to create a policy and then assign the policy to a cost control unit.</span></span>


## <a name="create-a-cost-behavior-hierarchy"></a><span data-ttu-id="7adfe-107">Creare una gerarchia di comportamento costo</span><span class="sxs-lookup"><span data-stu-id="7adfe-107">Create a cost behavior hierarchy</span></span>
1. <span data-ttu-id="7adfe-108">Andare a Contabilità industriale > Dimensioni > Gerarchie di dimensioni.</span><span class="sxs-lookup"><span data-stu-id="7adfe-108">Go to Cost accounting > Dimensions > Dimension hierarchies.</span></span>
2. <span data-ttu-id="7adfe-109">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="7adfe-109">Click New.</span></span>
3. <span data-ttu-id="7adfe-110">Fare clic su Crea.</span><span class="sxs-lookup"><span data-stu-id="7adfe-110">Click Create.</span></span>
4. <span data-ttu-id="7adfe-111">Nel campo Nome gerarchia dimensioni digitare "Gerarchia di comportamenti costo".</span><span class="sxs-lookup"><span data-stu-id="7adfe-111">In the Dimension hierarchy name field, type 'Cost behavior hierarchy'.</span></span>
5. <span data-ttu-id="7adfe-112">Nel campo Dimensione immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="7adfe-112">In the Dimension field, enter or select a value.</span></span>
    * <span data-ttu-id="7adfe-113">Selezionare Elementi di costo.</span><span class="sxs-lookup"><span data-stu-id="7adfe-113">Select Cost elements.</span></span>  
6. <span data-ttu-id="7adfe-114">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="7adfe-114">Click Save.</span></span>
7. <span data-ttu-id="7adfe-115">Fare clic su Visualizza gerarchia.</span><span class="sxs-lookup"><span data-stu-id="7adfe-115">Click View hierarchy.</span></span>
8. <span data-ttu-id="7adfe-116">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="7adfe-116">Click New.</span></span>
9. <span data-ttu-id="7adfe-117">Digitare un valore nel campo Nome nodo.</span><span class="sxs-lookup"><span data-stu-id="7adfe-117">In the Node name field, type a value.</span></span>
    * <span data-ttu-id="7adfe-118">Immettere il costo fisso.</span><span class="sxs-lookup"><span data-stu-id="7adfe-118">Enter Fixed cost.</span></span>  
10. <span data-ttu-id="7adfe-119">Nella struttura selezionare "Cost behavior hierarchy".</span><span class="sxs-lookup"><span data-stu-id="7adfe-119">In the tree, select 'Cost behavior hierarchy'.</span></span>
11. <span data-ttu-id="7adfe-120">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="7adfe-120">Click New.</span></span>
12. <span data-ttu-id="7adfe-121">Digitare un valore nel campo Nome nodo.</span><span class="sxs-lookup"><span data-stu-id="7adfe-121">In the Node name field, type a value.</span></span>
    * <span data-ttu-id="7adfe-122">Immettere il costo variabile.</span><span class="sxs-lookup"><span data-stu-id="7adfe-122">Enter Variable cost.</span></span>  
13. <span data-ttu-id="7adfe-123">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="7adfe-123">Click Save.</span></span>
14. <span data-ttu-id="7adfe-124">Nella struttura selezionare "Gerarchia di comportamenti costo\Costo fisso".</span><span class="sxs-lookup"><span data-stu-id="7adfe-124">In the tree, select 'Cost behavior hierarchy\Fixed cost'.</span></span>
15. <span data-ttu-id="7adfe-125">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="7adfe-125">Click New.</span></span>
16. <span data-ttu-id="7adfe-126">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="7adfe-126">In the list, mark the selected row.</span></span>
17. <span data-ttu-id="7adfe-127">Nel campo Membro di dimensione di inizio immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="7adfe-127">In the From dimension member field, enter or select a value.</span></span>
    * <span data-ttu-id="7adfe-128">L'intervallo dei membri di dimensione può non essere continuo, ma i membri non possono sovrapporsi.</span><span class="sxs-lookup"><span data-stu-id="7adfe-128">The range of dimension members can contain gaps, but the members cannot overlap.</span></span>  
18. <span data-ttu-id="7adfe-129">Nel campo Membro di dimensione di fine immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="7adfe-129">In the To dimension member field, enter or select a value.</span></span>
    * <span data-ttu-id="7adfe-130">L'intervallo dei membri di dimensione può non essere continuo, ma i membri non possono sovrapporsi.</span><span class="sxs-lookup"><span data-stu-id="7adfe-130">The range of dimension members can contain gaps, but the members cannot overlap.</span></span>  
19. <span data-ttu-id="7adfe-131">Nella struttura selezionare "Gerarchia di comportamenti costo\Costo variabile".</span><span class="sxs-lookup"><span data-stu-id="7adfe-131">In the tree, select 'Cost behavior hierarchy\Variable cost'.</span></span>
20. <span data-ttu-id="7adfe-132">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="7adfe-132">Click New.</span></span>
21. <span data-ttu-id="7adfe-133">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="7adfe-133">In the list, mark the selected row.</span></span>
22. <span data-ttu-id="7adfe-134">Nel campo Membro di dimensione di inizio immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="7adfe-134">In the From dimension member field, enter or select a value.</span></span>
    * <span data-ttu-id="7adfe-135">L'intervallo dei membri di dimensione può non essere continuo, ma i membri non possono sovrapporsi.</span><span class="sxs-lookup"><span data-stu-id="7adfe-135">The range of dimension members can contain gaps, but the members cannot overlap.</span></span>  
23. <span data-ttu-id="7adfe-136">Nel campo Membro di dimensione di fine immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="7adfe-136">In the To dimension member field, enter or select a value.</span></span>
    * <span data-ttu-id="7adfe-137">L'intervallo dei membri di dimensione può non essere continuo, ma i membri non possono sovrapporsi.</span><span class="sxs-lookup"><span data-stu-id="7adfe-137">The range of dimension members can contain gaps, but the members cannot overlap.</span></span>  
24. <span data-ttu-id="7adfe-138">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="7adfe-138">Click Save.</span></span>

## <a name="create-the-policy-and-rules"></a><span data-ttu-id="7adfe-139">Creare i criteri e le regole.</span><span class="sxs-lookup"><span data-stu-id="7adfe-139">Create the policy and rules</span></span>
1. <span data-ttu-id="7adfe-140">Andare a Contabilità industriale > Criteri > Criteri di comportamento costo.</span><span class="sxs-lookup"><span data-stu-id="7adfe-140">Go to Cost accounting > Policies > Cost behavior policies.</span></span>
2. <span data-ttu-id="7adfe-141">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="7adfe-141">Click New.</span></span>
3. <span data-ttu-id="7adfe-142">Digitare un valore nel campo Nome criteri.</span><span class="sxs-lookup"><span data-stu-id="7adfe-142">In the Policy name field, type a value.</span></span>
4. <span data-ttu-id="7adfe-143">Nel campo Gerarchia dimensioni di elemento di costo immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="7adfe-143">In the Cost element dimension hierarchy field, enter or select a value.</span></span>
    * <span data-ttu-id="7adfe-144">Selezionare la gerarchia di criteri creata.</span><span class="sxs-lookup"><span data-stu-id="7adfe-144">Select the policy hierarchy that you just created.</span></span>  
5. <span data-ttu-id="7adfe-145">Nel campo Gerarchia dimensioni di oggetto di costo immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="7adfe-145">In the Cost object dimension hierarchy field, enter or select a value.</span></span>
    * <span data-ttu-id="7adfe-146">Selezionare Organizzazione.</span><span class="sxs-lookup"><span data-stu-id="7adfe-146">Select Organization.</span></span>  
6. <span data-ttu-id="7adfe-147">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="7adfe-147">Click Save.</span></span>
7. <span data-ttu-id="7adfe-148">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="7adfe-148">Click New.</span></span>
8. <span data-ttu-id="7adfe-149">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="7adfe-149">In the list, mark the selected row.</span></span>
9. <span data-ttu-id="7adfe-150">Nel campo Nodo gerarchia dimensioni di elemento di costo immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="7adfe-150">In the Cost element dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="7adfe-151">Espande la gerarchia per selezionare il costo variabile.</span><span class="sxs-lookup"><span data-stu-id="7adfe-151">Expand the hierarchy to select Variable cost.</span></span>  
10. <span data-ttu-id="7adfe-152">Nel campo Nodo gerarchia dimensioni di oggetto di costo immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="7adfe-152">In the Cost object dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="7adfe-153">Per impostazione predefinita, la percentuale variabile è pari al 100%.</span><span class="sxs-lookup"><span data-stu-id="7adfe-153">By default, the variable percentage is 100 percent.</span></span>  
11. <span data-ttu-id="7adfe-154">Fare clic su Assegnazioni criteri per unità di controllo costi.</span><span class="sxs-lookup"><span data-stu-id="7adfe-154">Click Policy assignments for cost control unit.</span></span>
12. <span data-ttu-id="7adfe-155">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="7adfe-155">Click New.</span></span>
13. <span data-ttu-id="7adfe-156">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="7adfe-156">In the list, mark the selected row.</span></span>
14. <span data-ttu-id="7adfe-157">Immettere una data nel campo Valido dalla data di registrazione.</span><span class="sxs-lookup"><span data-stu-id="7adfe-157">In the Valid from accounting date field, enter a date.</span></span>
    * <span data-ttu-id="7adfe-158">Le regole hanno una data di validità e un utente o il sistema può farle scadere se ne viene creata una nuova versione.</span><span class="sxs-lookup"><span data-stu-id="7adfe-158">The rules are date-effective, and a user or the system can expire a rule if a newer version is created.</span></span>  
15. <span data-ttu-id="7adfe-159">Nel campo Unità di controllo costi immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="7adfe-159">In the Cost control unit field, enter or select a value.</span></span>
16. <span data-ttu-id="7adfe-160">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="7adfe-160">Click Save.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]