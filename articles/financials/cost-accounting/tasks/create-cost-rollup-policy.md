--- 
title: Creare criteri di rollup costi
description: In questa procedura viene illustrato come creare i criteri di rollup dei costi e le regole per i criteri.
author: YuyuScheller
manager: AnnBe
ms.date: 06/27/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 42656cbf445fd3f79844884d7d35243c5b051a4a
ms.contentlocale: it-it
ms.lasthandoff: 08/29/2017

---
# <a name="create-a-cost-rollup-policy"></a><span data-ttu-id="599d7-103">Creare criteri di rollup costi</span><span class="sxs-lookup"><span data-stu-id="599d7-103">Create a cost rollup policy</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="599d7-104">In questa procedura viene illustrato come creare i criteri di rollup dei costi e le regole per i criteri.</span><span class="sxs-lookup"><span data-stu-id="599d7-104">This procedure shows how to create a cost rollup policy and create rules for the policy.</span></span> <span data-ttu-id="599d7-105">La società di dati dimostrativi utilizzata per creare questa procedura è USP2.</span><span class="sxs-lookup"><span data-stu-id="599d7-105">The demo data used to create this procedure is USP2.</span></span>


## <a name="create-a-policy"></a><span data-ttu-id="599d7-106">Creare un criterio</span><span class="sxs-lookup"><span data-stu-id="599d7-106">Create a policy</span></span>
1. <span data-ttu-id="599d7-107">Andare a Contabilità industriale > Criteri > Criteri rollup costi.</span><span class="sxs-lookup"><span data-stu-id="599d7-107">Go to Cost accounting > Policies > Cost rollup policies.</span></span>
2. <span data-ttu-id="599d7-108">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="599d7-108">Click New.</span></span>
3. <span data-ttu-id="599d7-109">Digitare un valore nel campo Nome criteri.</span><span class="sxs-lookup"><span data-stu-id="599d7-109">In the Policy name field, type a value.</span></span>
4. <span data-ttu-id="599d7-110">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="599d7-110">In the Description field, type a value.</span></span>
5. <span data-ttu-id="599d7-111">Nel campo Gerarchia dimensioni di oggetto di costo immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="599d7-111">In the Cost object dimension hierarchy field, enter or select a value.</span></span>
    * <span data-ttu-id="599d7-112">Selezionare Rollup costi CC.</span><span class="sxs-lookup"><span data-stu-id="599d7-112">Select Cost rollup CC.</span></span>  
6. <span data-ttu-id="599d7-113">Nel campo Gerarchia dimensioni di elemento di costo immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="599d7-113">In the Cost element dimension hierarchy field, enter or select a value.</span></span>
    * <span data-ttu-id="599d7-114">Selezionare Rollup costi CC.</span><span class="sxs-lookup"><span data-stu-id="599d7-114">Select Cost rollup CC.</span></span>  
7. <span data-ttu-id="599d7-115">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="599d7-115">Click Save.</span></span>

## <a name="create-rules-for-the-cost-rollup-policy"></a><span data-ttu-id="599d7-116">Creare regole per i criteri di rollup costi</span><span class="sxs-lookup"><span data-stu-id="599d7-116">Create rules for the cost rollup policy</span></span>
1. <span data-ttu-id="599d7-117">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="599d7-117">Click New.</span></span>
2. <span data-ttu-id="599d7-118">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="599d7-118">In the list, mark the selected row.</span></span>
3. <span data-ttu-id="599d7-119">Nel campo Nodo gerarchia dimensioni di oggetto di costo immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="599d7-119">In the Cost object dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="599d7-120">Selezionare 007.</span><span class="sxs-lookup"><span data-stu-id="599d7-120">Select 007.</span></span>  
4. <span data-ttu-id="599d7-121">Nel campo Nodo gerarchia dimensioni di elemento di costo immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="599d7-121">In the Cost element dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="599d7-122">Selezionare Rollup costi CE.</span><span class="sxs-lookup"><span data-stu-id="599d7-122">Select Cost rollup CE.</span></span>  
5. <span data-ttu-id="599d7-123">Nel campo Elemento di costo secondario immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="599d7-123">In the Secondary cost element field, enter or select a value.</span></span>
    * <span data-ttu-id="599d7-124">Per questo esempio, mappare l'elemento di costo secondario CC-007 al centro di costo.</span><span class="sxs-lookup"><span data-stu-id="599d7-124">For this example, map the secondary cost element CC-007 to the cost center.</span></span>  
6. <span data-ttu-id="599d7-125">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="599d7-125">Click New.</span></span>
7. <span data-ttu-id="599d7-126">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="599d7-126">In the list, mark the selected row.</span></span>
8. <span data-ttu-id="599d7-127">Nel campo Nodo gerarchia dimensioni di oggetto di costo immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="599d7-127">In the Cost object dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="599d7-128">Selezionare 008.</span><span class="sxs-lookup"><span data-stu-id="599d7-128">Select 008.</span></span>  
9. <span data-ttu-id="599d7-129">Nel campo Nodo gerarchia dimensioni di elemento di costo immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="599d7-129">In the Cost element dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="599d7-130">Selezionare Rollup costi CE.</span><span class="sxs-lookup"><span data-stu-id="599d7-130">Select Cost rollup CE.</span></span>  
10. <span data-ttu-id="599d7-131">Nel campo Elemento di costo secondario immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="599d7-131">In the Secondary cost element field, enter or select a value.</span></span>
    * <span data-ttu-id="599d7-132">Per questo esempio, mappare l'elemento di costo secondario CC-008 al centro di costo.</span><span class="sxs-lookup"><span data-stu-id="599d7-132">For this example, map the secondary cost element CC-008 to the cost center.</span></span>  
11. <span data-ttu-id="599d7-133">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="599d7-133">Click New.</span></span>
12. <span data-ttu-id="599d7-134">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="599d7-134">In the list, mark the selected row.</span></span>
13. <span data-ttu-id="599d7-135">Nel campo Nodo gerarchia dimensioni di oggetto di costo immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="599d7-135">In the Cost object dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="599d7-136">Selezionare 009.</span><span class="sxs-lookup"><span data-stu-id="599d7-136">Select 009.</span></span>  
14. <span data-ttu-id="599d7-137">Nel campo Nodo gerarchia dimensioni di elemento di costo immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="599d7-137">In the Cost element dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="599d7-138">Selezionare Rollup costi CE.</span><span class="sxs-lookup"><span data-stu-id="599d7-138">Select Cost rollup CE.</span></span>  
15. <span data-ttu-id="599d7-139">Nel campo Elemento di costo secondario immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="599d7-139">In the Secondary cost element field, enter or select a value.</span></span>
    * <span data-ttu-id="599d7-140">Per questo esempio, mappare l'elemento di costo secondario CC-009 al centro di costo.</span><span class="sxs-lookup"><span data-stu-id="599d7-140">For this example, map the secondary cost element CC-009 to the cost center.</span></span>  
    * <span data-ttu-id="599d7-141">Continuare finché tutti i centri di costo sono mappati agli elementi di costo secondari corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="599d7-141">Continue until all cost centers are mapped to their corresponding secondary cost elements.</span></span>  
16. <span data-ttu-id="599d7-142">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="599d7-142">Click Save.</span></span>


