---
title: Creare criteri di rollup costi
description: In questa procedura viene illustrato come creare i criteri di rollup dei costi e le regole per i criteri.
author: ShylaThompson
manager: AnnBe
ms.date: 06/27/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c0a648984a8b4aaa314707e72a615f516116a193
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4990744"
---
# <a name="create-a-cost-rollup-policy"></a><span data-ttu-id="00938-103">Creare criteri di rollup costi</span><span class="sxs-lookup"><span data-stu-id="00938-103">Create a cost rollup policy</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="00938-104">In questa procedura viene illustrato come creare i criteri di rollup dei costi e le regole per i criteri.</span><span class="sxs-lookup"><span data-stu-id="00938-104">This procedure shows how to create a cost rollup policy and create rules for the policy.</span></span> <span data-ttu-id="00938-105">La società di dati dimostrativi utilizzata per creare questa procedura è USP2.</span><span class="sxs-lookup"><span data-stu-id="00938-105">The demo data used to create this procedure is USP2.</span></span>


## <a name="create-a-policy"></a><span data-ttu-id="00938-106">Creare un criterio</span><span class="sxs-lookup"><span data-stu-id="00938-106">Create a policy</span></span>
1. <span data-ttu-id="00938-107">Andare a Contabilità industriale > Criteri > Criteri rollup costi.</span><span class="sxs-lookup"><span data-stu-id="00938-107">Go to Cost accounting > Policies > Cost rollup policies.</span></span>
2. <span data-ttu-id="00938-108">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="00938-108">Click New.</span></span>
3. <span data-ttu-id="00938-109">Digitare un valore nel campo Nome criteri.</span><span class="sxs-lookup"><span data-stu-id="00938-109">In the Policy name field, type a value.</span></span>
4. <span data-ttu-id="00938-110">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="00938-110">In the Description field, type a value.</span></span>
5. <span data-ttu-id="00938-111">Nel campo Gerarchia dimensioni di oggetto di costo immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="00938-111">In the Cost object dimension hierarchy field, enter or select a value.</span></span>
    * <span data-ttu-id="00938-112">Selezionare Rollup costi CC.</span><span class="sxs-lookup"><span data-stu-id="00938-112">Select Cost rollup CC.</span></span>  
6. <span data-ttu-id="00938-113">Nel campo Gerarchia dimensioni di elemento di costo immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="00938-113">In the Cost element dimension hierarchy field, enter or select a value.</span></span>
    * <span data-ttu-id="00938-114">Selezionare Rollup costi CC.</span><span class="sxs-lookup"><span data-stu-id="00938-114">Select Cost rollup CC.</span></span>  
7. <span data-ttu-id="00938-115">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="00938-115">Click Save.</span></span>

## <a name="create-rules-for-the-cost-rollup-policy"></a><span data-ttu-id="00938-116">Creare regole per i criteri di rollup costi</span><span class="sxs-lookup"><span data-stu-id="00938-116">Create rules for the cost rollup policy</span></span>
1. <span data-ttu-id="00938-117">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="00938-117">Click New.</span></span>
2. <span data-ttu-id="00938-118">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="00938-118">In the list, mark the selected row.</span></span>
3. <span data-ttu-id="00938-119">Nel campo Nodo gerarchia dimensioni di oggetto di costo immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="00938-119">In the Cost object dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="00938-120">Selezionare 007.</span><span class="sxs-lookup"><span data-stu-id="00938-120">Select 007.</span></span>  
4. <span data-ttu-id="00938-121">Nel campo Nodo gerarchia dimensioni di elemento di costo immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="00938-121">In the Cost element dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="00938-122">Selezionare Rollup costi CE.</span><span class="sxs-lookup"><span data-stu-id="00938-122">Select Cost rollup CE.</span></span>  
5. <span data-ttu-id="00938-123">Nel campo Elemento di costo secondario immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="00938-123">In the Secondary cost element field, enter or select a value.</span></span>
    * <span data-ttu-id="00938-124">Per questo esempio, mappare l'elemento di costo secondario CC-007 al centro di costo.</span><span class="sxs-lookup"><span data-stu-id="00938-124">For this example, map the secondary cost element CC-007 to the cost center.</span></span>  
6. <span data-ttu-id="00938-125">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="00938-125">Click New.</span></span>
7. <span data-ttu-id="00938-126">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="00938-126">In the list, mark the selected row.</span></span>
8. <span data-ttu-id="00938-127">Nel campo Nodo gerarchia dimensioni di oggetto di costo immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="00938-127">In the Cost object dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="00938-128">Selezionare 008.</span><span class="sxs-lookup"><span data-stu-id="00938-128">Select 008.</span></span>  
9. <span data-ttu-id="00938-129">Nel campo Nodo gerarchia dimensioni di elemento di costo immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="00938-129">In the Cost element dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="00938-130">Selezionare Rollup costi CE.</span><span class="sxs-lookup"><span data-stu-id="00938-130">Select Cost rollup CE.</span></span>  
10. <span data-ttu-id="00938-131">Nel campo Elemento di costo secondario immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="00938-131">In the Secondary cost element field, enter or select a value.</span></span>
    * <span data-ttu-id="00938-132">Per questo esempio, mappare l'elemento di costo secondario CC-008 al centro di costo.</span><span class="sxs-lookup"><span data-stu-id="00938-132">For this example, map the secondary cost element CC-008 to the cost center.</span></span>  
11. <span data-ttu-id="00938-133">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="00938-133">Click New.</span></span>
12. <span data-ttu-id="00938-134">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="00938-134">In the list, mark the selected row.</span></span>
13. <span data-ttu-id="00938-135">Nel campo Nodo gerarchia dimensioni di oggetto di costo immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="00938-135">In the Cost object dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="00938-136">Selezionare 009.</span><span class="sxs-lookup"><span data-stu-id="00938-136">Select 009.</span></span>  
14. <span data-ttu-id="00938-137">Nel campo Nodo gerarchia dimensioni di elemento di costo immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="00938-137">In the Cost element dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="00938-138">Selezionare Rollup costi CE.</span><span class="sxs-lookup"><span data-stu-id="00938-138">Select Cost rollup CE.</span></span>  
15. <span data-ttu-id="00938-139">Nel campo Elemento di costo secondario immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="00938-139">In the Secondary cost element field, enter or select a value.</span></span>
    * <span data-ttu-id="00938-140">Per questo esempio, mappare l'elemento di costo secondario CC-009 al centro di costo.</span><span class="sxs-lookup"><span data-stu-id="00938-140">For this example, map the secondary cost element CC-009 to the cost center.</span></span>  
    * <span data-ttu-id="00938-141">Continuare finché tutti i centri di costo sono mappati agli elementi di costo secondari corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="00938-141">Continue until all cost centers are mapped to their corresponding secondary cost elements.</span></span>  
16. <span data-ttu-id="00938-142">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="00938-142">Click Save.</span></span>

