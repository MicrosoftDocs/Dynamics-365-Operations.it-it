---
title: Creare e assegnare i criteri di distribuzione costi a un'unità di controllo costi
description: Le regole di distribuzione costi vengono utilizzate per distribuire i costi conteggiati finanziariamente in un centro di costo collettivo.
author: ShylaThompson
manager: AnnBe
ms.date: 06/27/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CAMCostDistributionRule
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Operations
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 66921d5eddb31ffba0946c41f634719a684e4ad1
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/10/2020
ms.locfileid: "3976189"
---
# <a name="create-and-assign-a-cost-distribution-policy-to-a-cost-control-unit"></a><span data-ttu-id="5f75c-103">Creare e assegnare i criteri di distribuzione costi a un'unità di controllo costi</span><span class="sxs-lookup"><span data-stu-id="5f75c-103">Create and assign a cost distribution policy to a cost control unit</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="5f75c-104">Le regole di distribuzione costi vengono utilizzate per distribuire i costi conteggiati finanziariamente in un centro di costo collettivo.</span><span class="sxs-lookup"><span data-stu-id="5f75c-104">Cost distribution rules are used to distribute costs that have been financially counted on a collective cost center.</span></span> <span data-ttu-id="5f75c-105">Il contabile deve verificare che il costo sia distribuito ai centri di costo a seconda della base di allocazione selezionata.</span><span class="sxs-lookup"><span data-stu-id="5f75c-105">The cost accountant makes sure that the cost is distributed to the cost centers, based on the selected allocation base.</span></span> <span data-ttu-id="5f75c-106">I criteri e le regole corrispondenti vengono assegnati a un'unità di controllo dei costi.</span><span class="sxs-lookup"><span data-stu-id="5f75c-106">A policy and the corresponding rules are assigned to a cost control unit.</span></span> <span data-ttu-id="5f75c-107">In questa guida attività viene utilizzato un esempio per mostrare come creare criteri di distribuzione dei costi e le regole corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="5f75c-107">This task guide uses an example to show how to create a cost distribution policy and the corresponding rules.</span></span>


## <a name="create-a-policy"></a><span data-ttu-id="5f75c-108">Creare un criterio</span><span class="sxs-lookup"><span data-stu-id="5f75c-108">Create a policy</span></span>
1. <span data-ttu-id="5f75c-109">Andare a Contabilità industriale > Criteri > Criteri di distribuzione costi.</span><span class="sxs-lookup"><span data-stu-id="5f75c-109">Go to Cost accounting > Policies > Cost distribution policies.</span></span>
2. <span data-ttu-id="5f75c-110">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="5f75c-110">Click New.</span></span>
3. <span data-ttu-id="5f75c-111">Digitare un valore nel campo Nome criteri.</span><span class="sxs-lookup"><span data-stu-id="5f75c-111">In the Policy name field, type a value.</span></span>
4. <span data-ttu-id="5f75c-112">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="5f75c-112">In the Description field, type a value.</span></span>
5. <span data-ttu-id="5f75c-113">Nel campo Gerarchia dimensioni di oggetto di costo immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="5f75c-113">In the Cost object dimension hierarchy field, enter or select a value.</span></span>
    * <span data-ttu-id="5f75c-114">Selezionare Organizzazione.</span><span class="sxs-lookup"><span data-stu-id="5f75c-114">Select Organization.</span></span>  
6. <span data-ttu-id="5f75c-115">Nel campo Gerarchia dimensioni di elemento di costo immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="5f75c-115">In the Cost element dimension hierarchy field, enter or select a value.</span></span>
    * <span data-ttu-id="5f75c-116">Selezionare CDS P/L.</span><span class="sxs-lookup"><span data-stu-id="5f75c-116">Select CDS P/L.</span></span>  
7. <span data-ttu-id="5f75c-117">Nel campo Dimensione statistica immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="5f75c-117">In the Statistical dimension field, enter or select a value.</span></span>
    * <span data-ttu-id="5f75c-118">Selezionare Elementi statistici.</span><span class="sxs-lookup"><span data-stu-id="5f75c-118">Select Statistical elements.</span></span>  
8. <span data-ttu-id="5f75c-119">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="5f75c-119">Click Save.</span></span>

## <a name="create-rules-for-the-policy"></a><span data-ttu-id="5f75c-120">Creare regole per i criteri</span><span class="sxs-lookup"><span data-stu-id="5f75c-120">Create rules for the policy</span></span>
1. <span data-ttu-id="5f75c-121">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="5f75c-121">Click New.</span></span>
2. <span data-ttu-id="5f75c-122">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="5f75c-122">In the list, mark the selected row.</span></span>
3. <span data-ttu-id="5f75c-123">Nel campo Nodo gerarchia dimensioni di oggetto di costo immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="5f75c-123">In the Cost object dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="5f75c-124">Espande la gerarchia per selezionare 094.</span><span class="sxs-lookup"><span data-stu-id="5f75c-124">Expand the hierarchy to select 094.</span></span>  
4. <span data-ttu-id="5f75c-125">Nel campo Nodo gerarchia dimensioni di elemento di costo immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="5f75c-125">In the Cost element dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="5f75c-126">Selezionare Altri costi operativi, quindi selezionare 605110 Pulizia.</span><span class="sxs-lookup"><span data-stu-id="5f75c-126">Select Other operating expenses and then select 605110 Cleaning.</span></span>  
5. <span data-ttu-id="5f75c-127">Nel campo Comportamento costo selezionare un'opzione.</span><span class="sxs-lookup"><span data-stu-id="5f75c-127">In the Cost behavior field, select an option.</span></span>
    * <span data-ttu-id="5f75c-128">Selezionare Costo fisso</span><span class="sxs-lookup"><span data-stu-id="5f75c-128">Select Fixed cost.</span></span>  
6. <span data-ttu-id="5f75c-129">Nel campo Base di allocazione immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="5f75c-129">In the Allocation base field, enter or select a value.</span></span>
7. <span data-ttu-id="5f75c-130">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="5f75c-130">Click New.</span></span>
8. <span data-ttu-id="5f75c-131">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="5f75c-131">In the list, mark the selected row.</span></span>
9. <span data-ttu-id="5f75c-132">Nel campo Nodo gerarchia dimensioni di oggetto di costo immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="5f75c-132">In the Cost object dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="5f75c-133">Espande la gerarchia per selezionare 094.</span><span class="sxs-lookup"><span data-stu-id="5f75c-133">Expand the hierarchy to select 094.</span></span>  
10. <span data-ttu-id="5f75c-134">Nel campo Nodo gerarchia dimensioni di elemento di costo immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="5f75c-134">In the Cost element dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="5f75c-135">Selezionare Altri costi operativi, quindi selezionare 605150 Affitto.</span><span class="sxs-lookup"><span data-stu-id="5f75c-135">Select Other operating expenses and then select 605150 Rent.</span></span>  
11. <span data-ttu-id="5f75c-136">Nel campo Comportamento costo selezionare un'opzione.</span><span class="sxs-lookup"><span data-stu-id="5f75c-136">In the Cost behavior field, select an option.</span></span>
    * <span data-ttu-id="5f75c-137">Selezionare Costo fisso</span><span class="sxs-lookup"><span data-stu-id="5f75c-137">Select Fixed cost.</span></span>  
12. <span data-ttu-id="5f75c-138">Nel campo Base di allocazione immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="5f75c-138">In the Allocation base field, enter or select a value.</span></span>
13. <span data-ttu-id="5f75c-139">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="5f75c-139">Click Save.</span></span>

## <a name="assign-rules-to-a-cost-control-unit"></a><span data-ttu-id="5f75c-140">Assegnare regole a un'unità di controllo costi</span><span class="sxs-lookup"><span data-stu-id="5f75c-140">Assign rules to a cost control unit</span></span>
1. <span data-ttu-id="5f75c-141">Fare clic su Assegnazioni criteri per unità di controllo costi.</span><span class="sxs-lookup"><span data-stu-id="5f75c-141">Click Policy assignments for cost control unit.</span></span>
2. <span data-ttu-id="5f75c-142">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="5f75c-142">Click New.</span></span>
3. <span data-ttu-id="5f75c-143">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="5f75c-143">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="5f75c-144">Immettere una data nel campo Valido dalla data di registrazione.</span><span class="sxs-lookup"><span data-stu-id="5f75c-144">In the Valid from accounting date field, enter a date.</span></span>
    * <span data-ttu-id="5f75c-145">Selezionare il 1° settembre nell'anno fiscale valido.</span><span class="sxs-lookup"><span data-stu-id="5f75c-145">Select September 1 in the valid fiscal year.</span></span>  
5. <span data-ttu-id="5f75c-146">Nel campo Unità di controllo costi immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="5f75c-146">In the Cost control unit field, enter or select a value.</span></span>
6. <span data-ttu-id="5f75c-147">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="5f75c-147">Click Save.</span></span>

