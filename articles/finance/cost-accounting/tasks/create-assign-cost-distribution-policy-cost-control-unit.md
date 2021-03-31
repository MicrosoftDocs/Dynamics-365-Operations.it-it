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
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 946d188652e8f5b45d5c31a5aa0640d5362ef554
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5208681"
---
# <a name="create-and-assign-a-cost-distribution-policy-to-a-cost-control-unit"></a><span data-ttu-id="ef4da-103">Creare e assegnare i criteri di distribuzione costi a un'unità di controllo costi</span><span class="sxs-lookup"><span data-stu-id="ef4da-103">Create and assign a cost distribution policy to a cost control unit</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="ef4da-104">Le regole di distribuzione costi vengono utilizzate per distribuire i costi conteggiati finanziariamente in un centro di costo collettivo.</span><span class="sxs-lookup"><span data-stu-id="ef4da-104">Cost distribution rules are used to distribute costs that have been financially counted on a collective cost center.</span></span> <span data-ttu-id="ef4da-105">Il contabile deve verificare che il costo sia distribuito ai centri di costo a seconda della base di allocazione selezionata.</span><span class="sxs-lookup"><span data-stu-id="ef4da-105">The cost accountant makes sure that the cost is distributed to the cost centers, based on the selected allocation base.</span></span> <span data-ttu-id="ef4da-106">I criteri e le regole corrispondenti vengono assegnati a un'unità di controllo dei costi.</span><span class="sxs-lookup"><span data-stu-id="ef4da-106">A policy and the corresponding rules are assigned to a cost control unit.</span></span> <span data-ttu-id="ef4da-107">In questa guida attività viene utilizzato un esempio per mostrare come creare criteri di distribuzione dei costi e le regole corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="ef4da-107">This task guide uses an example to show how to create a cost distribution policy and the corresponding rules.</span></span>


## <a name="create-a-policy"></a><span data-ttu-id="ef4da-108">Creare un criterio</span><span class="sxs-lookup"><span data-stu-id="ef4da-108">Create a policy</span></span>
1. <span data-ttu-id="ef4da-109">Andare a Contabilità industriale > Criteri > Criteri di distribuzione costi.</span><span class="sxs-lookup"><span data-stu-id="ef4da-109">Go to Cost accounting > Policies > Cost distribution policies.</span></span>
2. <span data-ttu-id="ef4da-110">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="ef4da-110">Click New.</span></span>
3. <span data-ttu-id="ef4da-111">Digitare un valore nel campo Nome criteri.</span><span class="sxs-lookup"><span data-stu-id="ef4da-111">In the Policy name field, type a value.</span></span>
4. <span data-ttu-id="ef4da-112">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="ef4da-112">In the Description field, type a value.</span></span>
5. <span data-ttu-id="ef4da-113">Nel campo Gerarchia dimensioni di oggetto di costo immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="ef4da-113">In the Cost object dimension hierarchy field, enter or select a value.</span></span>
    * <span data-ttu-id="ef4da-114">Selezionare Organizzazione.</span><span class="sxs-lookup"><span data-stu-id="ef4da-114">Select Organization.</span></span>  
6. <span data-ttu-id="ef4da-115">Nel campo Gerarchia dimensioni di elemento di costo immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="ef4da-115">In the Cost element dimension hierarchy field, enter or select a value.</span></span>
    * <span data-ttu-id="ef4da-116">Selezionare CDS P/L.</span><span class="sxs-lookup"><span data-stu-id="ef4da-116">Select CDS P/L.</span></span>  
7. <span data-ttu-id="ef4da-117">Nel campo Dimensione statistica immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="ef4da-117">In the Statistical dimension field, enter or select a value.</span></span>
    * <span data-ttu-id="ef4da-118">Selezionare Elementi statistici.</span><span class="sxs-lookup"><span data-stu-id="ef4da-118">Select Statistical elements.</span></span>  
8. <span data-ttu-id="ef4da-119">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="ef4da-119">Click Save.</span></span>

## <a name="create-rules-for-the-policy"></a><span data-ttu-id="ef4da-120">Creare regole per i criteri</span><span class="sxs-lookup"><span data-stu-id="ef4da-120">Create rules for the policy</span></span>
1. <span data-ttu-id="ef4da-121">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="ef4da-121">Click New.</span></span>
2. <span data-ttu-id="ef4da-122">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="ef4da-122">In the list, mark the selected row.</span></span>
3. <span data-ttu-id="ef4da-123">Nel campo Nodo gerarchia dimensioni di oggetto di costo immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="ef4da-123">In the Cost object dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="ef4da-124">Espande la gerarchia per selezionare 094.</span><span class="sxs-lookup"><span data-stu-id="ef4da-124">Expand the hierarchy to select 094.</span></span>  
4. <span data-ttu-id="ef4da-125">Nel campo Nodo gerarchia dimensioni di elemento di costo immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="ef4da-125">In the Cost element dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="ef4da-126">Selezionare Altri costi operativi, quindi selezionare 605110 Pulizia.</span><span class="sxs-lookup"><span data-stu-id="ef4da-126">Select Other operating expenses and then select 605110 Cleaning.</span></span>  
5. <span data-ttu-id="ef4da-127">Nel campo Comportamento costo selezionare un'opzione.</span><span class="sxs-lookup"><span data-stu-id="ef4da-127">In the Cost behavior field, select an option.</span></span>
    * <span data-ttu-id="ef4da-128">Selezionare Costo fisso</span><span class="sxs-lookup"><span data-stu-id="ef4da-128">Select Fixed cost.</span></span>  
6. <span data-ttu-id="ef4da-129">Nel campo Base di allocazione immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="ef4da-129">In the Allocation base field, enter or select a value.</span></span>
7. <span data-ttu-id="ef4da-130">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="ef4da-130">Click New.</span></span>
8. <span data-ttu-id="ef4da-131">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="ef4da-131">In the list, mark the selected row.</span></span>
9. <span data-ttu-id="ef4da-132">Nel campo Nodo gerarchia dimensioni di oggetto di costo immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="ef4da-132">In the Cost object dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="ef4da-133">Espande la gerarchia per selezionare 094.</span><span class="sxs-lookup"><span data-stu-id="ef4da-133">Expand the hierarchy to select 094.</span></span>  
10. <span data-ttu-id="ef4da-134">Nel campo Nodo gerarchia dimensioni di elemento di costo immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="ef4da-134">In the Cost element dimension hierarchy node field, enter or select a value.</span></span>
    * <span data-ttu-id="ef4da-135">Selezionare Altri costi operativi, quindi selezionare 605150 Affitto.</span><span class="sxs-lookup"><span data-stu-id="ef4da-135">Select Other operating expenses and then select 605150 Rent.</span></span>  
11. <span data-ttu-id="ef4da-136">Nel campo Comportamento costo selezionare un'opzione.</span><span class="sxs-lookup"><span data-stu-id="ef4da-136">In the Cost behavior field, select an option.</span></span>
    * <span data-ttu-id="ef4da-137">Selezionare Costo fisso</span><span class="sxs-lookup"><span data-stu-id="ef4da-137">Select Fixed cost.</span></span>  
12. <span data-ttu-id="ef4da-138">Nel campo Base di allocazione immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="ef4da-138">In the Allocation base field, enter or select a value.</span></span>
13. <span data-ttu-id="ef4da-139">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="ef4da-139">Click Save.</span></span>

## <a name="assign-rules-to-a-cost-control-unit"></a><span data-ttu-id="ef4da-140">Assegnare regole a un'unità di controllo costi</span><span class="sxs-lookup"><span data-stu-id="ef4da-140">Assign rules to a cost control unit</span></span>
1. <span data-ttu-id="ef4da-141">Fare clic su Assegnazioni criteri per unità di controllo costi.</span><span class="sxs-lookup"><span data-stu-id="ef4da-141">Click Policy assignments for cost control unit.</span></span>
2. <span data-ttu-id="ef4da-142">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="ef4da-142">Click New.</span></span>
3. <span data-ttu-id="ef4da-143">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="ef4da-143">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="ef4da-144">Immettere una data nel campo Valido dalla data di registrazione.</span><span class="sxs-lookup"><span data-stu-id="ef4da-144">In the Valid from accounting date field, enter a date.</span></span>
    * <span data-ttu-id="ef4da-145">Selezionare il 1° settembre nell'anno fiscale valido.</span><span class="sxs-lookup"><span data-stu-id="ef4da-145">Select September 1 in the valid fiscal year.</span></span>  
5. <span data-ttu-id="ef4da-146">Nel campo Unità di controllo costi immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="ef4da-146">In the Cost control unit field, enter or select a value.</span></span>
6. <span data-ttu-id="ef4da-147">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="ef4da-147">Click Save.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]