---
title: Assegnare icone e titoli dei passaggi per l'app per dispositivi mobili Warehouse Management
description: In questo argomento viene descritto come assegnare icone e titoli dei passaggi per flussi di attività nuovi o personalizzati per l'app per dispositivi mobili Warehouse Management.
author: MarkusFogelberg
ms.date: 05/17/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2021-05-17
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 9523492d766669e6c38579fba7b5ddd6b3d282fc
ms.sourcegitcommit: c53de2c09b9296b41653e739178edf29f79e0679
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/17/2021
ms.locfileid: "6049366"
---
# <a name="assign-step-icons-and-titles-for-the-warehouse-management-mobile-app"></a><span data-ttu-id="7effa-103">Assegnare icone e titoli dei passaggi per l'app per dispositivi mobili Warehouse Management</span><span class="sxs-lookup"><span data-stu-id="7effa-103">Assign step icons and titles for the Warehouse Management mobile app</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="7effa-104">In questo argomento viene descritto come assegnare icone e titoli dei passaggi per flussi di attività nuovi o personalizzati per l'app per dispositivi mobili Warehouse Management.</span><span class="sxs-lookup"><span data-stu-id="7effa-104">This topic describes how to assign step icons and step titles for new or customized task flows for the Warehouse Management mobile app.</span></span>

<span data-ttu-id="7effa-105">Le seguenti illustrazioni mostrano come vengono visualizzati i titoli e le icone dei passaggi nell'app per dispositivi mobili Warehouse Management.</span><span class="sxs-lookup"><span data-stu-id="7effa-105">The following illustrations shows how step icons and titles appear in the Warehouse Management mobile app.</span></span>

<span data-ttu-id="7effa-106">![Esempio di un'icona di passaggio e un titolo di passaggio nell'app per dispositivi mobili Warehouse Management](media/step-icon-example.png "Esempio di un'icona di passaggio e un titolo di passaggio nell'app per dispositivi mobili Warehouse Management")</span><span class="sxs-lookup"><span data-stu-id="7effa-106">![Example of a step icon and a step title in the Warehouse Management mobile app](media/step-icon-example.png "Example of a step icon and a step title in the Warehouse Management mobile app")</span></span>

## <a name="turn-on-this-feature-in-your-system"></a><span data-ttu-id="7effa-107">Attivare la funzionalità nel tuo sistema</span><span class="sxs-lookup"><span data-stu-id="7effa-107">Turn on this feature in your system</span></span>

<span data-ttu-id="7effa-108">Prima di poter utilizzare questa funzione, è necessario attivarla nel sistema.</span><span class="sxs-lookup"><span data-stu-id="7effa-108">Before you can use this feature, it must be turned on in your system.</span></span> <span data-ttu-id="7effa-109">Gli amministratori possono utilizzare le impostazioni della [gestione delle funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) per controllare lo stato della funzione e abilitarla.</span><span class="sxs-lookup"><span data-stu-id="7effa-109">Admins can use the [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the status of the feature and turn it on.</span></span> <span data-ttu-id="7effa-110">Nell'area di lavoro **Gestione funzionalità**, la funzione è elencata nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="7effa-110">In the **Feature management** workspace, the feature is listed in the following way:</span></span>

- <span data-ttu-id="7effa-111">**Modulo:** *Gestione magazzino*</span><span class="sxs-lookup"><span data-stu-id="7effa-111">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="7effa-112">**Nome funzionalità:** *Impostazioni utente, icone e titoli dei passaggi per la nuova app di magazzino*</span><span class="sxs-lookup"><span data-stu-id="7effa-112">**Feature name:** *User settings, icons, and step titles for the new warehouse app*</span></span>

## <a name="standard-step-ids-classes-and-icons"></a><span data-ttu-id="7effa-113">ID, classi e icone del passaggio standard</span><span class="sxs-lookup"><span data-stu-id="7effa-113">Standard step IDs, classes, and icons</span></span>

<span data-ttu-id="7effa-114">Ogni passaggio in un flusso di attività è identificato da un ID passaggio e ogni ID passaggio ha una classe di passaggio corrispondente.</span><span class="sxs-lookup"><span data-stu-id="7effa-114">Each step in a task flow is identified by a step ID, and each step ID has a corresponding step class.</span></span> <span data-ttu-id="7effa-115">L'icona e il titolo del passaggio sono specificati in ciascuna classe di passaggio.</span><span class="sxs-lookup"><span data-stu-id="7effa-115">The step icon and title are specified in each step class.</span></span>

### <a name="step-ids-and-step-classes"></a><a name="step-ids-classes"></a><span data-ttu-id="7effa-116">ID passaggio e classi di passaggio</span><span class="sxs-lookup"><span data-stu-id="7effa-116">Step IDs and step classes</span></span>

<span data-ttu-id="7effa-117">La tabella seguente elenca tutti gli ID passaggio attualmente disponibili e la classe di passaggio corrispondente.</span><span class="sxs-lookup"><span data-stu-id="7effa-117">The following table lists every step ID that is currently available, and its corresponding step class.</span></span> <span data-ttu-id="7effa-118">Il nome di controllo del campo di input principale viene utilizzato come ID passaggio.</span><span class="sxs-lookup"><span data-stu-id="7effa-118">The control name of the primary input field is used as the step ID.</span></span>

<span data-ttu-id="7effa-119">Per un esempio che mostra come vengono utilizzati questi ID e classi di passaggio, vedi l'implementazione del metodo `WHSMobileAppStepInfoBuilder.stepId()` nella sezione [ Esempio: assegnare icone e titoli dei passaggi per un flusso personalizzato](#example) più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="7effa-119">For an example that shows how these step IDs and classes are used, see the implementation of the `WHSMobileAppStepInfoBuilder.stepId()` method in the [Example: Assign step icons and titles for a custom flow](#example) section later in this topic.</span></span>

| <span data-ttu-id="7effa-120">ID fase</span><span class="sxs-lookup"><span data-stu-id="7effa-120">Step ID</span></span> | <span data-ttu-id="7effa-121">Classe di passaggio</span><span class="sxs-lookup"><span data-stu-id="7effa-121">Step Class</span></span> |
|-|-|
| <span data-ttu-id="7effa-122">BatchDisposition</span><span class="sxs-lookup"><span data-stu-id="7effa-122">BatchDisposition</span></span> | <span data-ttu-id="7effa-123">WHSMobileAppStepBatchDisposition</span><span class="sxs-lookup"><span data-stu-id="7effa-123">WHSMobileAppStepBatchDisposition</span></span> |
| <span data-ttu-id="7effa-124">Vettore</span><span class="sxs-lookup"><span data-stu-id="7effa-124">Carrier</span></span> | <span data-ttu-id="7effa-125">WHSMobileAppStepCarrier</span><span class="sxs-lookup"><span data-stu-id="7effa-125">WHSMobileAppStepCarrier</span></span> |
| <span data-ttu-id="7effa-126">CatchWeight</span><span class="sxs-lookup"><span data-stu-id="7effa-126">CatchWeight</span></span> | <span data-ttu-id="7effa-127">WHSMobileAppStepCatchWeight</span><span class="sxs-lookup"><span data-stu-id="7effa-127">WHSMobileAppStepCatchWeight</span></span> |
| <span data-ttu-id="7effa-128">CatchWeightQtyOutboundWeight</span><span class="sxs-lookup"><span data-stu-id="7effa-128">CatchWeightQtyOutboundWeight</span></span> | <span data-ttu-id="7effa-129">WHSMobileAppStepCatchWeight</span><span class="sxs-lookup"><span data-stu-id="7effa-129">WHSMobileAppStepCatchWeight</span></span> |
| <span data-ttu-id="7effa-130">CatchWeightTag</span><span class="sxs-lookup"><span data-stu-id="7effa-130">CatchWeightTag</span></span> | <span data-ttu-id="7effa-131">WHSMobileAppStepCatchWeightTag</span><span class="sxs-lookup"><span data-stu-id="7effa-131">WHSMobileAppStepCatchWeightTag</span></span> |
| <span data-ttu-id="7effa-132">CatchWeightTagWeight</span><span class="sxs-lookup"><span data-stu-id="7effa-132">CatchWeightTagWeight</span></span> | <span data-ttu-id="7effa-133">WHSMobileAppStepCatchWeightTagWeight</span><span class="sxs-lookup"><span data-stu-id="7effa-133">WHSMobileAppStepCatchWeightTagWeight</span></span> |
| <span data-ttu-id="7effa-134">ChangeWarehouseSuccess</span><span class="sxs-lookup"><span data-stu-id="7effa-134">ChangeWarehouseSuccess</span></span> | <span data-ttu-id="7effa-135">WHSMobileAppStepChangeWarehouseSuccess</span><span class="sxs-lookup"><span data-stu-id="7effa-135">WHSMobileAppStepChangeWarehouseSuccess</span></span> |
| <span data-ttu-id="7effa-136">CheckDigit</span><span class="sxs-lookup"><span data-stu-id="7effa-136">CheckDigit</span></span> | <span data-ttu-id="7effa-137">WHSMobileAppStepCheckDigit</span><span class="sxs-lookup"><span data-stu-id="7effa-137">WHSMobileAppStepCheckDigit</span></span> |
| <span data-ttu-id="7effa-138">ClusterId</span><span class="sxs-lookup"><span data-stu-id="7effa-138">ClusterId</span></span> | <span data-ttu-id="7effa-139">WHSMobileAppStepClusterId</span><span class="sxs-lookup"><span data-stu-id="7effa-139">WHSMobileAppStepClusterId</span></span> |
| <span data-ttu-id="7effa-140">ClusterPickQtyVerification</span><span class="sxs-lookup"><span data-stu-id="7effa-140">ClusterPickQtyVerification</span></span> | <span data-ttu-id="7effa-141">WHSMobileAppStepQtyVerification</span><span class="sxs-lookup"><span data-stu-id="7effa-141">WHSMobileAppStepQtyVerification</span></span> |
| <span data-ttu-id="7effa-142">ClusterPosition</span><span class="sxs-lookup"><span data-stu-id="7effa-142">ClusterPosition</span></span> | <span data-ttu-id="7effa-143">WHSMobileAppStepClusterPosition</span><span class="sxs-lookup"><span data-stu-id="7effa-143">WHSMobileAppStepClusterPosition</span></span> |
| <span data-ttu-id="7effa-144">ConfigId</span><span class="sxs-lookup"><span data-stu-id="7effa-144">ConfigId</span></span> | <span data-ttu-id="7effa-145">WHSMobileAppStepConfigId</span><span class="sxs-lookup"><span data-stu-id="7effa-145">WHSMobileAppStepConfigId</span></span> |
| <span data-ttu-id="7effa-146">Conferma</span><span class="sxs-lookup"><span data-stu-id="7effa-146">Confirmation</span></span> | <span data-ttu-id="7effa-147">WHSMobileAppStepConfirmation</span><span class="sxs-lookup"><span data-stu-id="7effa-147">WHSMobileAppStepConfirmation</span></span> |
| <span data-ttu-id="7effa-148">ConsolidateFromLicensePlateId</span><span class="sxs-lookup"><span data-stu-id="7effa-148">ConsolidateFromLicensePlateId</span></span> | <span data-ttu-id="7effa-149">WHSMobileAppStepConsolidateFromLicensePlateId</span><span class="sxs-lookup"><span data-stu-id="7effa-149">WHSMobileAppStepConsolidateFromLicensePlateId</span></span> |
| <span data-ttu-id="7effa-150">ConsolidateLPConfirmation</span><span class="sxs-lookup"><span data-stu-id="7effa-150">ConsolidateLPConfirmation</span></span> | <span data-ttu-id="7effa-151">WHSMobileAppStepConsolidateLPConfirmation</span><span class="sxs-lookup"><span data-stu-id="7effa-151">WHSMobileAppStepConsolidateLPConfirmation</span></span> |
| <span data-ttu-id="7effa-152">ConsolidateToLicensePlateId</span><span class="sxs-lookup"><span data-stu-id="7effa-152">ConsolidateToLicensePlateId</span></span> | <span data-ttu-id="7effa-153">WHSMobileAppStepConsolidateToLicensePlateId</span><span class="sxs-lookup"><span data-stu-id="7effa-153">WHSMobileAppStepConsolidateToLicensePlateId</span></span> |
| <span data-ttu-id="7effa-154">ContainerType</span><span class="sxs-lookup"><span data-stu-id="7effa-154">ContainerType</span></span> | <span data-ttu-id="7effa-155">WHSMobileAppStepContainerType</span><span class="sxs-lookup"><span data-stu-id="7effa-155">WHSMobileAppStepContainerType</span></span> |
| <span data-ttu-id="7effa-156">CountingReasonCode</span><span class="sxs-lookup"><span data-stu-id="7effa-156">CountingReasonCode</span></span> | <span data-ttu-id="7effa-157">WHSMobileAppStepCountingReasonCode</span><span class="sxs-lookup"><span data-stu-id="7effa-157">WHSMobileAppStepCountingReasonCode</span></span> |
| <span data-ttu-id="7effa-158">CycleCountingAddLPOrFinish</span><span class="sxs-lookup"><span data-stu-id="7effa-158">CycleCountingAddLPOrFinish</span></span> | <span data-ttu-id="7effa-159">WHSMobileAppStepCycleCountingAddLPOrFinish</span><span class="sxs-lookup"><span data-stu-id="7effa-159">WHSMobileAppStepCycleCountingAddLPOrFinish</span></span> |
| <span data-ttu-id="7effa-160">CycleCountQty1</span><span class="sxs-lookup"><span data-stu-id="7effa-160">CycleCountQty1</span></span> | <span data-ttu-id="7effa-161">WHSMobileAppStepCycleCountQty</span><span class="sxs-lookup"><span data-stu-id="7effa-161">WHSMobileAppStepCycleCountQty</span></span> |
| <span data-ttu-id="7effa-162">CycleCountQty2</span><span class="sxs-lookup"><span data-stu-id="7effa-162">CycleCountQty2</span></span> | <span data-ttu-id="7effa-163">WHSMobileAppStepCycleCountQty</span><span class="sxs-lookup"><span data-stu-id="7effa-163">WHSMobileAppStepCycleCountQty</span></span> |
| <span data-ttu-id="7effa-164">CycleCountQty3</span><span class="sxs-lookup"><span data-stu-id="7effa-164">CycleCountQty3</span></span> | <span data-ttu-id="7effa-165">WHSMobileAppStepCycleCountQty</span><span class="sxs-lookup"><span data-stu-id="7effa-165">WHSMobileAppStepCycleCountQty</span></span> |
| <span data-ttu-id="7effa-166">CycleCountQty4</span><span class="sxs-lookup"><span data-stu-id="7effa-166">CycleCountQty4</span></span> | <span data-ttu-id="7effa-167">WHSMobileAppStepCycleCountQty</span><span class="sxs-lookup"><span data-stu-id="7effa-167">WHSMobileAppStepCycleCountQty</span></span> |
| <span data-ttu-id="7effa-168">Disposition</span><span class="sxs-lookup"><span data-stu-id="7effa-168">Disposition</span></span> | <span data-ttu-id="7effa-169">WHSMobileAppStepDisposition</span><span class="sxs-lookup"><span data-stu-id="7effa-169">WHSMobileAppStepDisposition</span></span> |
| <span data-ttu-id="7effa-170">DriverCheckInConfirmation</span><span class="sxs-lookup"><span data-stu-id="7effa-170">DriverCheckInConfirmation</span></span> | <span data-ttu-id="7effa-171">WHSMobileAppStepDriverCheckInConfirmation</span><span class="sxs-lookup"><span data-stu-id="7effa-171">WHSMobileAppStepDriverCheckInConfirmation</span></span> |
| <span data-ttu-id="7effa-172">DriverCheckInId</span><span class="sxs-lookup"><span data-stu-id="7effa-172">DriverCheckInId</span></span> | <span data-ttu-id="7effa-173">WHSMobileAppStepDriverCheckInId</span><span class="sxs-lookup"><span data-stu-id="7effa-173">WHSMobileAppStepDriverCheckInId</span></span> |
| <span data-ttu-id="7effa-174">DriverCheckOutConfirmation</span><span class="sxs-lookup"><span data-stu-id="7effa-174">DriverCheckOutConfirmation</span></span> | <span data-ttu-id="7effa-175">WHSMobileAppStepDriverCheckOutConfirmation</span><span class="sxs-lookup"><span data-stu-id="7effa-175">WHSMobileAppStepDriverCheckOutConfirmation</span></span> |
| <span data-ttu-id="7effa-176">DriverCheckOutId</span><span class="sxs-lookup"><span data-stu-id="7effa-176">DriverCheckOutId</span></span> | <span data-ttu-id="7effa-177">WHSMobileAppStepDriverCheckOutId</span><span class="sxs-lookup"><span data-stu-id="7effa-177">WHSMobileAppStepDriverCheckOutId</span></span> |
| <span data-ttu-id="7effa-178">ExpDate</span><span class="sxs-lookup"><span data-stu-id="7effa-178">ExpDate</span></span> | <span data-ttu-id="7effa-179">WHSMobileAppStepExpDate</span><span class="sxs-lookup"><span data-stu-id="7effa-179">WHSMobileAppStepExpDate</span></span> |
| <span data-ttu-id="7effa-180">FromBatchDisposition</span><span class="sxs-lookup"><span data-stu-id="7effa-180">FromBatchDisposition</span></span> | <span data-ttu-id="7effa-181">WHSMobileAppStepFromBatchDisposition</span><span class="sxs-lookup"><span data-stu-id="7effa-181">WHSMobileAppStepFromBatchDisposition</span></span> |
| <span data-ttu-id="7effa-182">FromInventoryStatus</span><span class="sxs-lookup"><span data-stu-id="7effa-182">FromInventoryStatus</span></span> | <span data-ttu-id="7effa-183">WHSMobileAppStepInventoryStatusFrom</span><span class="sxs-lookup"><span data-stu-id="7effa-183">WHSMobileAppStepInventoryStatusFrom</span></span> |
| <span data-ttu-id="7effa-184">FullQty</span><span class="sxs-lookup"><span data-stu-id="7effa-184">FullQty</span></span> | <span data-ttu-id="7effa-185">WHSMobileAppStepFullQty</span><span class="sxs-lookup"><span data-stu-id="7effa-185">WHSMobileAppStepFullQty</span></span> |
| <span data-ttu-id="7effa-186">InboundPut</span><span class="sxs-lookup"><span data-stu-id="7effa-186">InboundPut</span></span> | <span data-ttu-id="7effa-187">WHSMobileAppStepInboundPut</span><span class="sxs-lookup"><span data-stu-id="7effa-187">WHSMobileAppStepInboundPut</span></span> |
| <span data-ttu-id="7effa-188">InventBatchId</span><span class="sxs-lookup"><span data-stu-id="7effa-188">InventBatchId</span></span> | <span data-ttu-id="7effa-189">WHSMobileAppStepBatch</span><span class="sxs-lookup"><span data-stu-id="7effa-189">WHSMobileAppStepBatch</span></span> |
| <span data-ttu-id="7effa-190">InventColorId</span><span class="sxs-lookup"><span data-stu-id="7effa-190">InventColorId</span></span> | <span data-ttu-id="7effa-191">WHSMobileAppStepInventColorId</span><span class="sxs-lookup"><span data-stu-id="7effa-191">WHSMobileAppStepInventColorId</span></span> |
| <span data-ttu-id="7effa-192">InventLocation</span><span class="sxs-lookup"><span data-stu-id="7effa-192">InventLocation</span></span> | <span data-ttu-id="7effa-193">WHSMobileAppStepInventLocation</span><span class="sxs-lookup"><span data-stu-id="7effa-193">WHSMobileAppStepInventLocation</span></span> |
| <span data-ttu-id="7effa-194">InventLocationId</span><span class="sxs-lookup"><span data-stu-id="7effa-194">InventLocationId</span></span> | <span data-ttu-id="7effa-195">WHSMobileAppStepWarehouse</span><span class="sxs-lookup"><span data-stu-id="7effa-195">WHSMobileAppStepWarehouse</span></span> |
| <span data-ttu-id="7effa-196">InventSerialId</span><span class="sxs-lookup"><span data-stu-id="7effa-196">InventSerialId</span></span> | <span data-ttu-id="7effa-197">WHSMobileAppStepInventSerialId</span><span class="sxs-lookup"><span data-stu-id="7effa-197">WHSMobileAppStepInventSerialId</span></span> |
| <span data-ttu-id="7effa-198">InventSizeId</span><span class="sxs-lookup"><span data-stu-id="7effa-198">InventSizeId</span></span> | <span data-ttu-id="7effa-199">WHSMobileAppStepInventSizeId</span><span class="sxs-lookup"><span data-stu-id="7effa-199">WHSMobileAppStepInventSizeId</span></span> |
| <span data-ttu-id="7effa-200">InventStatusId</span><span class="sxs-lookup"><span data-stu-id="7effa-200">InventStatusId</span></span> | <span data-ttu-id="7effa-201">WHSMobileAppStepInventStatus</span><span class="sxs-lookup"><span data-stu-id="7effa-201">WHSMobileAppStepInventStatus</span></span> |
| <span data-ttu-id="7effa-202">InventStyleId</span><span class="sxs-lookup"><span data-stu-id="7effa-202">InventStyleId</span></span> | <span data-ttu-id="7effa-203">WHSMobileAppStepInventStyleId</span><span class="sxs-lookup"><span data-stu-id="7effa-203">WHSMobileAppStepInventStyleId</span></span> |
| <span data-ttu-id="7effa-204">InventVersionId</span><span class="sxs-lookup"><span data-stu-id="7effa-204">InventVersionId</span></span> | <span data-ttu-id="7effa-205">WHSMobileAppStepInventVersionId</span><span class="sxs-lookup"><span data-stu-id="7effa-205">WHSMobileAppStepInventVersionId</span></span> |
| <span data-ttu-id="7effa-206">ItemId</span><span class="sxs-lookup"><span data-stu-id="7effa-206">ItemId</span></span> | <span data-ttu-id="7effa-207">WHSMobileAppStepItem</span><span class="sxs-lookup"><span data-stu-id="7effa-207">WHSMobileAppStepItem</span></span> |
| <span data-ttu-id="7effa-208">ITMContainerID</span><span class="sxs-lookup"><span data-stu-id="7effa-208">ITMContainerID</span></span> | <span data-ttu-id="7effa-209">ITMMobileAppStepContainerId</span><span class="sxs-lookup"><span data-stu-id="7effa-209">ITMMobileAppStepContainerId</span></span> |
| <span data-ttu-id="7effa-210">ITMShipmentID</span><span class="sxs-lookup"><span data-stu-id="7effa-210">ITMShipmentID</span></span> | <span data-ttu-id="7effa-211">ITMMobileAppStepShipmentId</span><span class="sxs-lookup"><span data-stu-id="7effa-211">ITMMobileAppStepShipmentId</span></span> |
| <span data-ttu-id="7effa-212">KanbanCardId</span><span class="sxs-lookup"><span data-stu-id="7effa-212">KanbanCardId</span></span> | <span data-ttu-id="7effa-213">WHSMobileAppStepKanbanCard</span><span class="sxs-lookup"><span data-stu-id="7effa-213">WHSMobileAppStepKanbanCard</span></span> |
| <span data-ttu-id="7effa-214">KanbanCardToEmpty</span><span class="sxs-lookup"><span data-stu-id="7effa-214">KanbanCardToEmpty</span></span> | <span data-ttu-id="7effa-215">WHSMobileAppStepKanbanCardToEmpty</span><span class="sxs-lookup"><span data-stu-id="7effa-215">WHSMobileAppStepKanbanCardToEmpty</span></span> |
| <span data-ttu-id="7effa-216">KanbanOrCardId</span><span class="sxs-lookup"><span data-stu-id="7effa-216">KanbanOrCardId</span></span> | <span data-ttu-id="7effa-217">WHSMobileAppStepKanbanCard</span><span class="sxs-lookup"><span data-stu-id="7effa-217">WHSMobileAppStepKanbanCard</span></span> |
| <span data-ttu-id="7effa-218">LicensePlateId</span><span class="sxs-lookup"><span data-stu-id="7effa-218">LicensePlateId</span></span> | <span data-ttu-id="7effa-219">WHSMobileAppStepLicensePlate</span><span class="sxs-lookup"><span data-stu-id="7effa-219">WHSMobileAppStepLicensePlate</span></span> |
| <span data-ttu-id="7effa-220">LoadId</span><span class="sxs-lookup"><span data-stu-id="7effa-220">LoadId</span></span> | <span data-ttu-id="7effa-221">WHSMobileAppStepLoadId</span><span class="sxs-lookup"><span data-stu-id="7effa-221">WHSMobileAppStepLoadId</span></span> |
| <span data-ttu-id="7effa-222">LocationLicensePlatePosition</span><span class="sxs-lookup"><span data-stu-id="7effa-222">LocationLicensePlatePosition</span></span> | <span data-ttu-id="7effa-223">WHSMobileAppStepLocationLicensePlatePosition</span><span class="sxs-lookup"><span data-stu-id="7effa-223">WHSMobileAppStepLocationLicensePlatePosition</span></span> |
| <span data-ttu-id="7effa-224">LocOrLP</span><span class="sxs-lookup"><span data-stu-id="7effa-224">LocOrLP</span></span> | <span data-ttu-id="7effa-225">WHSMobileAppStepLocOrLP</span><span class="sxs-lookup"><span data-stu-id="7effa-225">WHSMobileAppStepLocOrLP</span></span> |
| <span data-ttu-id="7effa-226">LocOrLP_From</span><span class="sxs-lookup"><span data-stu-id="7effa-226">LocOrLP_From</span></span> | <span data-ttu-id="7effa-227">WHSMobileAppStepLocOrLPFrom</span><span class="sxs-lookup"><span data-stu-id="7effa-227">WHSMobileAppStepLocOrLPFrom</span></span> |
| <span data-ttu-id="7effa-228">LocOrLP_To</span><span class="sxs-lookup"><span data-stu-id="7effa-228">LocOrLP_To</span></span> | <span data-ttu-id="7effa-229">WHSMobileAppStepLocOrLPTo</span><span class="sxs-lookup"><span data-stu-id="7effa-229">WHSMobileAppStepLocOrLPTo</span></span> |
| <span data-ttu-id="7effa-230">LocOrLPCheck</span><span class="sxs-lookup"><span data-stu-id="7effa-230">LocOrLPCheck</span></span> | <span data-ttu-id="7effa-231">WHSMobileAppStepLocOrLPCheck</span><span class="sxs-lookup"><span data-stu-id="7effa-231">WHSMobileAppStepLocOrLPCheck</span></span> |
| <span data-ttu-id="7effa-232">LocVerification</span><span class="sxs-lookup"><span data-stu-id="7effa-232">LocVerification</span></span> | <span data-ttu-id="7effa-233">WHSMobileAppStepLocVerification</span><span class="sxs-lookup"><span data-stu-id="7effa-233">WHSMobileAppStepLocVerification</span></span> |
| <span data-ttu-id="7effa-234">LPAdjustIn</span><span class="sxs-lookup"><span data-stu-id="7effa-234">LPAdjustIn</span></span> | <span data-ttu-id="7effa-235">WHSMobileAppStepLPAdjustIn</span><span class="sxs-lookup"><span data-stu-id="7effa-235">WHSMobileAppStepLPAdjustIn</span></span> |
| <span data-ttu-id="7effa-236">LPBreakChildLP</span><span class="sxs-lookup"><span data-stu-id="7effa-236">LPBreakChildLP</span></span> | <span data-ttu-id="7effa-237">WHSMobileAppStepLPBreakChildLP</span><span class="sxs-lookup"><span data-stu-id="7effa-237">WHSMobileAppStepLPBreakChildLP</span></span> |
| <span data-ttu-id="7effa-238">LPBreakParentLP</span><span class="sxs-lookup"><span data-stu-id="7effa-238">LPBreakParentLP</span></span> | <span data-ttu-id="7effa-239">WHSMobileAppStepLPBreakParentLP</span><span class="sxs-lookup"><span data-stu-id="7effa-239">WHSMobileAppStepLPBreakParentLP</span></span> |
| <span data-ttu-id="7effa-240">LPBuildChildLP</span><span class="sxs-lookup"><span data-stu-id="7effa-240">LPBuildChildLP</span></span> | <span data-ttu-id="7effa-241">WHSMobileAppStepLPBuildChildLP</span><span class="sxs-lookup"><span data-stu-id="7effa-241">WHSMobileAppStepLPBuildChildLP</span></span> |
| <span data-ttu-id="7effa-242">LPBuildParentLP</span><span class="sxs-lookup"><span data-stu-id="7effa-242">LPBuildParentLP</span></span> | <span data-ttu-id="7effa-243">WHSMobileAppStepLPBuildParentLP</span><span class="sxs-lookup"><span data-stu-id="7effa-243">WHSMobileAppStepLPBuildParentLP</span></span> |
| <span data-ttu-id="7effa-244">LPVerification</span><span class="sxs-lookup"><span data-stu-id="7effa-244">LPVerification</span></span> | <span data-ttu-id="7effa-245">WHSMobileAppStepLPVerification</span><span class="sxs-lookup"><span data-stu-id="7effa-245">WHSMobileAppStepLPVerification</span></span> |
| <span data-ttu-id="7effa-246">MergeContainerId</span><span class="sxs-lookup"><span data-stu-id="7effa-246">MergeContainerId</span></span> | <span data-ttu-id="7effa-247">WHSMobileAppStepMergeContainerId</span><span class="sxs-lookup"><span data-stu-id="7effa-247">WHSMobileAppStepMergeContainerId</span></span> |
| <span data-ttu-id="7effa-248">MixedLPLineNum</span><span class="sxs-lookup"><span data-stu-id="7effa-248">MixedLPLineNum</span></span> | <span data-ttu-id="7effa-249">WHSMobileAppStepMixedLPLineNum</span><span class="sxs-lookup"><span data-stu-id="7effa-249">WHSMobileAppStepMixedLPLineNum</span></span> |
| <span data-ttu-id="7effa-250">MobileDeviceQueueMessageCollectionIdentifierId</span><span class="sxs-lookup"><span data-stu-id="7effa-250">MobileDeviceQueueMessageCollectionIdentifierId</span></span> | <span data-ttu-id="7effa-251">WHSMobileAppStepSelectOrder</span><span class="sxs-lookup"><span data-stu-id="7effa-251">WHSMobileAppStepSelectOrder</span></span> |
| <span data-ttu-id="7effa-252">MovementConfirmCancel</span><span class="sxs-lookup"><span data-stu-id="7effa-252">MovementConfirmCancel</span></span> | <span data-ttu-id="7effa-253">WHSMobileAppStepMovementConfirmCancel</span><span class="sxs-lookup"><span data-stu-id="7effa-253">WHSMobileAppStepMovementConfirmCancel</span></span> |
| <span data-ttu-id="7effa-254">NewCaptureWeight</span><span class="sxs-lookup"><span data-stu-id="7effa-254">NewCaptureWeight</span></span> | <span data-ttu-id="7effa-255">WHSMobileAppStepCatchWeight</span><span class="sxs-lookup"><span data-stu-id="7effa-255">WHSMobileAppStepCatchWeight</span></span> |
| <span data-ttu-id="7effa-256">NewQty</span><span class="sxs-lookup"><span data-stu-id="7effa-256">NewQty</span></span> | <span data-ttu-id="7effa-257">WHSMobileAppStepNewQty</span><span class="sxs-lookup"><span data-stu-id="7effa-257">WHSMobileAppStepNewQty</span></span> |
| <span data-ttu-id="7effa-258">OutboundCatchWeightTag</span><span class="sxs-lookup"><span data-stu-id="7effa-258">OutboundCatchWeightTag</span></span> | <span data-ttu-id="7effa-259">WHSMobileAppStepCatchWeightTag</span><span class="sxs-lookup"><span data-stu-id="7effa-259">WHSMobileAppStepCatchWeightTag</span></span> |
| <span data-ttu-id="7effa-260">OutboundPut</span><span class="sxs-lookup"><span data-stu-id="7effa-260">OutboundPut</span></span> | <span data-ttu-id="7effa-261">WHSMobileAppStepOutboundPut</span><span class="sxs-lookup"><span data-stu-id="7effa-261">WHSMobileAppStepOutboundPut</span></span> |
| <span data-ttu-id="7effa-262">OutboundWeight</span><span class="sxs-lookup"><span data-stu-id="7effa-262">OutboundWeight</span></span> | <span data-ttu-id="7effa-263">WHSMobileAppStepCatchWeight</span><span class="sxs-lookup"><span data-stu-id="7effa-263">WHSMobileAppStepCatchWeight</span></span> |
| <span data-ttu-id="7effa-264">OverridePutNewLocation</span><span class="sxs-lookup"><span data-stu-id="7effa-264">OverridePutNewLocation</span></span> | <span data-ttu-id="7effa-265">WHSMobileAppStepOverridePutNewLocation</span><span class="sxs-lookup"><span data-stu-id="7effa-265">WHSMobileAppStepOverridePutNewLocation</span></span> |
| <span data-ttu-id="7effa-266">PieceByPieceConfirmation</span><span class="sxs-lookup"><span data-stu-id="7effa-266">PieceByPieceConfirmation</span></span> | <span data-ttu-id="7effa-267">WHSMobileAppStepQtyVerification</span><span class="sxs-lookup"><span data-stu-id="7effa-267">WHSMobileAppStepQtyVerification</span></span> |
| <span data-ttu-id="7effa-268">POLineNum</span><span class="sxs-lookup"><span data-stu-id="7effa-268">POLineNum</span></span> | <span data-ttu-id="7effa-269">WHSMobileAppStepPOLineNum</span><span class="sxs-lookup"><span data-stu-id="7effa-269">WHSMobileAppStepPOLineNum</span></span> |
| <span data-ttu-id="7effa-270">Numero ordine fornitore</span><span class="sxs-lookup"><span data-stu-id="7effa-270">PONum</span></span> | <span data-ttu-id="7effa-271">WHSMobileAppStepPONum</span><span class="sxs-lookup"><span data-stu-id="7effa-271">WHSMobileAppStepPONum</span></span> |
| <span data-ttu-id="7effa-272">PositionFull</span><span class="sxs-lookup"><span data-stu-id="7effa-272">PositionFull</span></span> | <span data-ttu-id="7effa-273">WHSMobileAppStepPositionFull</span><span class="sxs-lookup"><span data-stu-id="7effa-273">WHSMobileAppStepPositionFull</span></span> |
| <span data-ttu-id="7effa-274">PositionFullQty</span><span class="sxs-lookup"><span data-stu-id="7effa-274">PositionFullQty</span></span> | <span data-ttu-id="7effa-275">WHSMobileAppStepPositionFullQty</span><span class="sxs-lookup"><span data-stu-id="7effa-275">WHSMobileAppStepPositionFullQty</span></span> |
| <span data-ttu-id="7effa-276">Potenza</span><span class="sxs-lookup"><span data-stu-id="7effa-276">Potency</span></span> | <span data-ttu-id="7effa-277">WHSMobileAppStepPotency</span><span class="sxs-lookup"><span data-stu-id="7effa-277">WHSMobileAppStepPotency</span></span> |
| <span data-ttu-id="7effa-278">PrinterName</span><span class="sxs-lookup"><span data-stu-id="7effa-278">PrinterName</span></span> | <span data-ttu-id="7effa-279">WHSMobileAppStepPrinterName</span><span class="sxs-lookup"><span data-stu-id="7effa-279">WHSMobileAppStepPrinterName</span></span> |
| <span data-ttu-id="7effa-280">ProdId</span><span class="sxs-lookup"><span data-stu-id="7effa-280">ProdId</span></span> | <span data-ttu-id="7effa-281">WHSMobileAppStepProdId</span><span class="sxs-lookup"><span data-stu-id="7effa-281">WHSMobileAppStepProdId</span></span> |
| <span data-ttu-id="7effa-282">ProdLastPalletConfirmation</span><span class="sxs-lookup"><span data-stu-id="7effa-282">ProdLastPalletConfirmation</span></span> | <span data-ttu-id="7effa-283">WHSMobileAppStepProdLastPalletConfirmation</span><span class="sxs-lookup"><span data-stu-id="7effa-283">WHSMobileAppStepProdLastPalletConfirmation</span></span> |
| <span data-ttu-id="7effa-284">ProductConfirmation</span><span class="sxs-lookup"><span data-stu-id="7effa-284">ProductConfirmation</span></span> | <span data-ttu-id="7effa-285">WHSMobileAppStepProductConfirmation</span><span class="sxs-lookup"><span data-stu-id="7effa-285">WHSMobileAppStepProductConfirmation</span></span> |
| <span data-ttu-id="7effa-286">ProductionScrapConfirmation</span><span class="sxs-lookup"><span data-stu-id="7effa-286">ProductionScrapConfirmation</span></span> | <span data-ttu-id="7effa-287">WHSMobileAppStepProductionScrapConfirmation</span><span class="sxs-lookup"><span data-stu-id="7effa-287">WHSMobileAppStepProductionScrapConfirmation</span></span> |
| <span data-ttu-id="7effa-288">Inserisci</span><span class="sxs-lookup"><span data-stu-id="7effa-288">Put</span></span> | <span data-ttu-id="7effa-289">WHSMobileAppStepPut</span><span class="sxs-lookup"><span data-stu-id="7effa-289">WHSMobileAppStepPut</span></span> |
| <span data-ttu-id="7effa-290">PutawayClusterId</span><span class="sxs-lookup"><span data-stu-id="7effa-290">PutawayClusterId</span></span> | <span data-ttu-id="7effa-291">WHSMobileAppStepPutawayClusterId</span><span class="sxs-lookup"><span data-stu-id="7effa-291">WHSMobileAppStepPutawayClusterId</span></span> |
| <span data-ttu-id="7effa-292">Quantità</span><span class="sxs-lookup"><span data-stu-id="7effa-292">Qty</span></span> | <span data-ttu-id="7effa-293">WHSMobileAppStepQty</span><span class="sxs-lookup"><span data-stu-id="7effa-293">WHSMobileAppStepQty</span></span> |
| <span data-ttu-id="7effa-294">QtyAdjust</span><span class="sxs-lookup"><span data-stu-id="7effa-294">QtyAdjust</span></span> | <span data-ttu-id="7effa-295">WHSMobileAppStepQtyAdjust</span><span class="sxs-lookup"><span data-stu-id="7effa-295">WHSMobileAppStepQtyAdjust</span></span> |
| <span data-ttu-id="7effa-296">QtyShort</span><span class="sxs-lookup"><span data-stu-id="7effa-296">QtyShort</span></span> | <span data-ttu-id="7effa-297">WHSMobileAppStepQtyShort</span><span class="sxs-lookup"><span data-stu-id="7effa-297">WHSMobileAppStepQtyShort</span></span> |
| <span data-ttu-id="7effa-298">QtyToConsume</span><span class="sxs-lookup"><span data-stu-id="7effa-298">QtyToConsume</span></span> | <span data-ttu-id="7effa-299">WHSMobileAppStepQtyToConsume</span><span class="sxs-lookup"><span data-stu-id="7effa-299">WHSMobileAppStepQtyToConsume</span></span> |
| <span data-ttu-id="7effa-300">QtyToPick</span><span class="sxs-lookup"><span data-stu-id="7effa-300">QtyToPick</span></span> | <span data-ttu-id="7effa-301">WHSMobileAppStepQtyToPick</span><span class="sxs-lookup"><span data-stu-id="7effa-301">WHSMobileAppStepQtyToPick</span></span> |
| <span data-ttu-id="7effa-302">QtyToPut</span><span class="sxs-lookup"><span data-stu-id="7effa-302">QtyToPut</span></span> | <span data-ttu-id="7effa-303">WHSMobileAppStepQtyToPut</span><span class="sxs-lookup"><span data-stu-id="7effa-303">WHSMobileAppStepQtyToPut</span></span> |
| <span data-ttu-id="7effa-304">QtyToScrap</span><span class="sxs-lookup"><span data-stu-id="7effa-304">QtyToScrap</span></span> | <span data-ttu-id="7effa-305">WHSMobileAppStepQtyToScrap</span><span class="sxs-lookup"><span data-stu-id="7effa-305">WHSMobileAppStepQtyToScrap</span></span> |
| <span data-ttu-id="7effa-306">QtyVerification</span><span class="sxs-lookup"><span data-stu-id="7effa-306">QtyVerification</span></span> | <span data-ttu-id="7effa-307">WHSMobileAppStepQtyVerification</span><span class="sxs-lookup"><span data-stu-id="7effa-307">WHSMobileAppStepQtyVerification</span></span> |
| <span data-ttu-id="7effa-308">QtyWithScanningLimit</span><span class="sxs-lookup"><span data-stu-id="7effa-308">QtyWithScanningLimit</span></span> | <span data-ttu-id="7effa-309">WHSMobileAppStepQtyAdjust</span><span class="sxs-lookup"><span data-stu-id="7effa-309">WHSMobileAppStepQtyAdjust</span></span> |
| <span data-ttu-id="7effa-310">ReasonString</span><span class="sxs-lookup"><span data-stu-id="7effa-310">ReasonString</span></span> | <span data-ttu-id="7effa-311">WHSMobileAppStepReasonString</span><span class="sxs-lookup"><span data-stu-id="7effa-311">WHSMobileAppStepReasonString</span></span> |
| <span data-ttu-id="7effa-312">RecvLocationId</span><span class="sxs-lookup"><span data-stu-id="7effa-312">RecvLocationId</span></span> | <span data-ttu-id="7effa-313">WHSMobileAppStepRecvLocationId</span><span class="sxs-lookup"><span data-stu-id="7effa-313">WHSMobileAppStepRecvLocationId</span></span> |
| <span data-ttu-id="7effa-314">RemoveContainerId</span><span class="sxs-lookup"><span data-stu-id="7effa-314">RemoveContainerId</span></span> | <span data-ttu-id="7effa-315">WHSMobileAppStepRemoveContainerId</span><span class="sxs-lookup"><span data-stu-id="7effa-315">WHSMobileAppStepRemoveContainerId</span></span> |
| <span data-ttu-id="7effa-316">ReprintLabelConfirmation</span><span class="sxs-lookup"><span data-stu-id="7effa-316">ReprintLabelConfirmation</span></span> | <span data-ttu-id="7effa-317">WHSMobileAppStepReprintLabelConfirmation</span><span class="sxs-lookup"><span data-stu-id="7effa-317">WHSMobileAppStepReprintLabelConfirmation</span></span> |
| <span data-ttu-id="7effa-318">RMANum</span><span class="sxs-lookup"><span data-stu-id="7effa-318">RMANum</span></span> | <span data-ttu-id="7effa-319">WHSMobileAppStepRMANum</span><span class="sxs-lookup"><span data-stu-id="7effa-319">WHSMobileAppStepRMANum</span></span> |
| <span data-ttu-id="7effa-320">ShortPickReason</span><span class="sxs-lookup"><span data-stu-id="7effa-320">ShortPickReason</span></span> | <span data-ttu-id="7effa-321">WHSMobileAppStepShortPickReason</span><span class="sxs-lookup"><span data-stu-id="7effa-321">WHSMobileAppStepShortPickReason</span></span> |
| <span data-ttu-id="7effa-322">SortConOrLP</span><span class="sxs-lookup"><span data-stu-id="7effa-322">SortConOrLP</span></span> | <span data-ttu-id="7effa-323">WHSMobileAppStepSortConOrLP</span><span class="sxs-lookup"><span data-stu-id="7effa-323">WHSMobileAppStepSortConOrLP</span></span> |
| <span data-ttu-id="7effa-324">SortLicensePlateId</span><span class="sxs-lookup"><span data-stu-id="7effa-324">SortLicensePlateId</span></span> | <span data-ttu-id="7effa-325">WHSMobileAppStepSortLicensePlateId</span><span class="sxs-lookup"><span data-stu-id="7effa-325">WHSMobileAppStepSortLicensePlateId</span></span> |
| <span data-ttu-id="7effa-326">SortPositionId</span><span class="sxs-lookup"><span data-stu-id="7effa-326">SortPositionId</span></span> | <span data-ttu-id="7effa-327">WHSMobileAppStepSortPositionId</span><span class="sxs-lookup"><span data-stu-id="7effa-327">WHSMobileAppStepSortPositionId</span></span> |
| <span data-ttu-id="7effa-328">SortVerification</span><span class="sxs-lookup"><span data-stu-id="7effa-328">SortVerification</span></span> | <span data-ttu-id="7effa-329">WHSMobileAppStepSortVerification</span><span class="sxs-lookup"><span data-stu-id="7effa-329">WHSMobileAppStepSortVerification</span></span> |
| <span data-ttu-id="7effa-330">StartLocationId</span><span class="sxs-lookup"><span data-stu-id="7effa-330">StartLocationId</span></span> | <span data-ttu-id="7effa-331">WHSMobileAppStepStartLocationId</span><span class="sxs-lookup"><span data-stu-id="7effa-331">WHSMobileAppStepStartLocationId</span></span> |
| <span data-ttu-id="7effa-332">StartProdOrderConfirmation</span><span class="sxs-lookup"><span data-stu-id="7effa-332">StartProdOrderConfirmation</span></span> | <span data-ttu-id="7effa-333">WHSMobileAppStepStartProdOrderConfirmation</span><span class="sxs-lookup"><span data-stu-id="7effa-333">WHSMobileAppStepStartProdOrderConfirmation</span></span> |
| <span data-ttu-id="7effa-334">TargetLicensePlateId</span><span class="sxs-lookup"><span data-stu-id="7effa-334">TargetLicensePlateId</span></span> | <span data-ttu-id="7effa-335">WHSMobileAppStepTargetLicensePlateId</span><span class="sxs-lookup"><span data-stu-id="7effa-335">WHSMobileAppStepTargetLicensePlateId</span></span> |
| <span data-ttu-id="7effa-336">TOLineNum</span><span class="sxs-lookup"><span data-stu-id="7effa-336">TOLineNum</span></span> | <span data-ttu-id="7effa-337">WHSMobileAppStepTOLineNum</span><span class="sxs-lookup"><span data-stu-id="7effa-337">WHSMobileAppStepTOLineNum</span></span> |
| <span data-ttu-id="7effa-338">ToLocation</span><span class="sxs-lookup"><span data-stu-id="7effa-338">ToLocation</span></span> | <span data-ttu-id="7effa-339">WHSMobileAppStepToLocation</span><span class="sxs-lookup"><span data-stu-id="7effa-339">WHSMobileAppStepToLocation</span></span> |
| <span data-ttu-id="7effa-340">N. OT</span><span class="sxs-lookup"><span data-stu-id="7effa-340">TONum</span></span> | <span data-ttu-id="7effa-341">WHSMobileAppStepTONum</span><span class="sxs-lookup"><span data-stu-id="7effa-341">WHSMobileAppStepTONum</span></span> |
| <span data-ttu-id="7effa-342">ToWarehouse</span><span class="sxs-lookup"><span data-stu-id="7effa-342">ToWarehouse</span></span> | <span data-ttu-id="7effa-343">WHSMobileAppStepWarehouseTo</span><span class="sxs-lookup"><span data-stu-id="7effa-343">WHSMobileAppStepWarehouseTo</span></span> |
| <span data-ttu-id="7effa-344">TransportLoadId</span><span class="sxs-lookup"><span data-stu-id="7effa-344">TransportLoadId</span></span> | <span data-ttu-id="7effa-345">WHSMobileAppStepTransportLoadId</span><span class="sxs-lookup"><span data-stu-id="7effa-345">WHSMobileAppStepTransportLoadId</span></span> |
| <span data-ttu-id="7effa-346">WaveLabelId</span><span class="sxs-lookup"><span data-stu-id="7effa-346">WaveLabelId</span></span> | <span data-ttu-id="7effa-347">WHSMobileAppStepWaveLabelId</span><span class="sxs-lookup"><span data-stu-id="7effa-347">WHSMobileAppStepWaveLabelId</span></span> |
| <span data-ttu-id="7effa-348">WaveLblQty</span><span class="sxs-lookup"><span data-stu-id="7effa-348">WaveLblQty</span></span> | <span data-ttu-id="7effa-349">WHSMobileAppStepWaveLblQty</span><span class="sxs-lookup"><span data-stu-id="7effa-349">WHSMobileAppStepWaveLblQty</span></span> |
| <span data-ttu-id="7effa-350">Peso</span><span class="sxs-lookup"><span data-stu-id="7effa-350">Weight</span></span> | <span data-ttu-id="7effa-351">WHSMobileAppStepWeight</span><span class="sxs-lookup"><span data-stu-id="7effa-351">WHSMobileAppStepWeight</span></span> |
| <span data-ttu-id="7effa-352">WeightToConsume</span><span class="sxs-lookup"><span data-stu-id="7effa-352">WeightToConsume</span></span> | <span data-ttu-id="7effa-353">WHSMobileAppStepWeightToConsume</span><span class="sxs-lookup"><span data-stu-id="7effa-353">WHSMobileAppStepWeightToConsume</span></span> |
| <span data-ttu-id="7effa-354">WHSAdjustmentType</span><span class="sxs-lookup"><span data-stu-id="7effa-354">WHSAdjustmentType</span></span> | <span data-ttu-id="7effa-355">WHSMobileAppStepWHSAdjustmentType</span><span class="sxs-lookup"><span data-stu-id="7effa-355">WHSMobileAppStepWHSAdjustmentType</span></span> |
| <span data-ttu-id="7effa-356">WHSReceivingException</span><span class="sxs-lookup"><span data-stu-id="7effa-356">WHSReceivingException</span></span> | <span data-ttu-id="7effa-357">WHSMobileAppStepWHSReceivingException</span><span class="sxs-lookup"><span data-stu-id="7effa-357">WHSMobileAppStepWHSReceivingException</span></span> |
| <span data-ttu-id="7effa-358">WHSWorkException</span><span class="sxs-lookup"><span data-stu-id="7effa-358">WHSWorkException</span></span> | <span data-ttu-id="7effa-359">WHSMobileAppStepWHSWorkException</span><span class="sxs-lookup"><span data-stu-id="7effa-359">WHSMobileAppStepWHSWorkException</span></span> |
| <span data-ttu-id="7effa-360">WHSWorkLicensePlateId</span><span class="sxs-lookup"><span data-stu-id="7effa-360">WHSWorkLicensePlateId</span></span> | <span data-ttu-id="7effa-361">WHSMobileAppStepWorkLicensePlateId</span><span class="sxs-lookup"><span data-stu-id="7effa-361">WHSMobileAppStepWorkLicensePlateId</span></span> |
| <span data-ttu-id="7effa-362">WMSLocationId</span><span class="sxs-lookup"><span data-stu-id="7effa-362">WMSLocationId</span></span> | <span data-ttu-id="7effa-363">WHSMobileAppStepLocation</span><span class="sxs-lookup"><span data-stu-id="7effa-363">WHSMobileAppStepLocation</span></span> |
| <span data-ttu-id="7effa-364">WorkId</span><span class="sxs-lookup"><span data-stu-id="7effa-364">WorkId</span></span> | <span data-ttu-id="7effa-365">WHSMobileAppStepWorkId</span><span class="sxs-lookup"><span data-stu-id="7effa-365">WHSMobileAppStepWorkId</span></span> |
| <span data-ttu-id="7effa-366">WorkIdToCancel</span><span class="sxs-lookup"><span data-stu-id="7effa-366">WorkIdToCancel</span></span> | <span data-ttu-id="7effa-367">WHSMobileAppStepWorkIdToCancel</span><span class="sxs-lookup"><span data-stu-id="7effa-367">WHSMobileAppStepWorkIdToCancel</span></span> |
| <span data-ttu-id="7effa-368">WorkLPIdPutawayCluster</span><span class="sxs-lookup"><span data-stu-id="7effa-368">WorkLPIdPutawayCluster</span></span> | <span data-ttu-id="7effa-369">WHSMobileAppStepWorkLPIdPutawayCluster</span><span class="sxs-lookup"><span data-stu-id="7effa-369">WHSMobileAppStepWorkLPIdPutawayCluster</span></span> |
| <span data-ttu-id="7effa-370">WorkPoolId</span><span class="sxs-lookup"><span data-stu-id="7effa-370">WorkPoolId</span></span> | <span data-ttu-id="7effa-371">WHSMobileAppStepWorkPoolId</span><span class="sxs-lookup"><span data-stu-id="7effa-371">WHSMobileAppStepWorkPoolId</span></span> |
| <span data-ttu-id="7effa-372">ZoneId</span><span class="sxs-lookup"><span data-stu-id="7effa-372">ZoneId</span></span> | <span data-ttu-id="7effa-373">WHSMobileAppStepZoneId</span><span class="sxs-lookup"><span data-stu-id="7effa-373">WHSMobileAppStepZoneId</span></span> |

### <a name="available-step-icons"></a><a name="step-icons"></a><span data-ttu-id="7effa-374">Icone dei passaggi disponibili</span><span class="sxs-lookup"><span data-stu-id="7effa-374">Available step icons</span></span>

<span data-ttu-id="7effa-375">Il sistema include una raccolta di icone dei passaggi standard che è possibile utilizzare anche per i passaggi personalizzati.</span><span class="sxs-lookup"><span data-stu-id="7effa-375">The system includes a collection of standard step icons that you can also use for your custom steps.</span></span> <span data-ttu-id="7effa-376">Al momento non puoi caricare icone di passaggio personalizzate.</span><span class="sxs-lookup"><span data-stu-id="7effa-376">You can't currently upload custom step icons.</span></span> <span data-ttu-id="7effa-377">Pertanto, è sempre necessario selezionare una delle icone dei passaggi standard.</span><span class="sxs-lookup"><span data-stu-id="7effa-377">Therefore, you must always select one of the standard step icons.</span></span>

<span data-ttu-id="7effa-378">La tabella seguente mostra tutte le icone dei passaggi standard attualmente disponibili e il relativo nome.</span><span class="sxs-lookup"><span data-stu-id="7effa-378">The following table shows every standard step icon that is currently available, and its name.</span></span>

<table>
<tbody>
<tr>
<td><img src="media/step-icons-about.png" alt="About step icon" title="Informazioni sull'icona di passaggio"><br><span data-ttu-id="7effa-380">Informazioni</span><span class="sxs-lookup"><span data-stu-id="7effa-380">About</span></span></td>
<td><img src="media/step-icons-add-lp.png" alt="Add license plate or item step icon" title="Aggiungere la targa o icona passaggio dell'articolo"><br><span data-ttu-id="7effa-382">AddLpOrItem</span><span class="sxs-lookup"><span data-stu-id="7effa-382">AddLpOrItem</span></span></td>
<td><img src="media/step-icons-batch-disposition.png" alt="Batch disposition step icon" title="Icona del passaggio di smaltimento batch"><br><span data-ttu-id="7effa-384">BatchDisposition</span><span class="sxs-lookup"><span data-stu-id="7effa-384">BatchDisposition</span></span></td>
<td><img src="media/step-icons-carrier.png" alt="Carrier step icon" title="Icona del passaggio del vettore"><br><span data-ttu-id="7effa-386">Vettore</span><span class="sxs-lookup"><span data-stu-id="7effa-386">Carrier</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-cw-tag.png" alt="Catch weight tag step icon" title="Icona del passaggio dell'etichetta di peso variabile"><br><span data-ttu-id="7effa-388">CatchWeightTag</span><span class="sxs-lookup"><span data-stu-id="7effa-388">CatchWeightTag</span></span></td>
<td><img src="media/step-icons-cw-tag-weight.png" alt="Catch weight tag weight step icon" title="Icona del passaggio del peso dell'etichetta di peso variabile"><br><span data-ttu-id="7effa-390">CatchWeightTagWeight</span><span class="sxs-lookup"><span data-stu-id="7effa-390">CatchWeightTagWeight</span></span></td>
<td><img src="media/step-icons-check-digit.png" alt="Check digit step icon" title="Icona del passaggio della cifra di controllo"><br><span data-ttu-id="7effa-392">CheckDigit</span><span class="sxs-lookup"><span data-stu-id="7effa-392">CheckDigit</span></span></td>
<td><img src="media/step-icons-check-in-out.png" alt="Check in or out ID step icon" title="Icona del passaggiodi controllo dell'ID di entrata o di uscita"><br><span data-ttu-id="7effa-394">CheckInOutId</span><span class="sxs-lookup"><span data-stu-id="7effa-394">CheckInOutId</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-child-lp.png" alt="Child license plate step icon" title="Icona del passaggio della targa figlio"><br><span data-ttu-id="7effa-396">ChildLP</span><span class="sxs-lookup"><span data-stu-id="7effa-396">ChildLP</span></span></td>
<td><img src="media/step-icons-cluster-id.png" alt="Cluster ID step icon" title="Icona del passaggio ID cluster"><br><span data-ttu-id="7effa-398">ClusterId</span><span class="sxs-lookup"><span data-stu-id="7effa-398">ClusterId</span></span></td>
<td><img src="media/step-icons-cluster-position.png" alt="Cluster position step icon" title="Icona del passaggio posizione cluster"><br><span data-ttu-id="7effa-400">ClusterPosition</span><span class="sxs-lookup"><span data-stu-id="7effa-400">ClusterPosition</span></span></td>
<td><img src="media/step-icons-config-id.png" alt="Config ID step icon" title="Icona del passaggio ID configurazione"><br><span data-ttu-id="7effa-402">ConfigId</span><span class="sxs-lookup"><span data-stu-id="7effa-402">ConfigId</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-configured-field.png" alt="Configured field step icon" title="Icona del passaggio del campo configurato"><br><span data-ttu-id="7effa-404">ConfiguredField</span><span class="sxs-lookup"><span data-stu-id="7effa-404">ConfiguredField</span></span></td>
<td><img src="media/step-icons-con-lp.png" alt="Con or LP step icon" title="Icona del passaggio configurazione o targa"><br><span data-ttu-id="7effa-406">ConOrLP</span><span class="sxs-lookup"><span data-stu-id="7effa-406">ConOrLP</span></span></td>
<td><img src="media/step-icons-consolidate-from-LP.png" alt="Consolidate from license plate ID step icon" title="Icona del passaggio di consolidamento dall'ID targa"><br><span data-ttu-id="7effa-408">ConsolidateFromLicensePlateID</span><span class="sxs-lookup"><span data-stu-id="7effa-408">ConsolidateFromLicensePlateID</span></span></td>
<td><img src="media/step-icons-consolidate-to-LP.png" alt="Consolidate to license plate ID step icon" title="Icona del passaggio di consolidamento sull'ID targa"><br><span data-ttu-id="7effa-410">ConsolidateToLicensePlateID</span><span class="sxs-lookup"><span data-stu-id="7effa-410">ConsolidateToLicensePlateID</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-container-type.png" alt="Container type step icon" title="Icona del passaggio del tipo di contenitore"><br><span data-ttu-id="7effa-412">ContainerType</span><span class="sxs-lookup"><span data-stu-id="7effa-412">ContainerType</span></span></td>
<td><img src="media/step-icons-counting.png" alt="Counting step icon" title="Icona del passaggio di conteggio"><br><span data-ttu-id="7effa-414">Conteggio</span><span class="sxs-lookup"><span data-stu-id="7effa-414">Counting</span></span></td>
<td><img src="media/step-icons-counting-reason.png" alt="Counting reason code step icon" title="Icona del passagio di conteggio del codice motivo"><br><span data-ttu-id="7effa-416">CountingReasonCode</span><span class="sxs-lookup"><span data-stu-id="7effa-416">CountingReasonCode</span></span></td>
<td><img src="media/step-icons-country-origin.png" alt="Country of origin code step icon" title="Icona del passaggio del codice del paese di origine"><br><span data-ttu-id="7effa-418">CountryOfOrigin</span><span class="sxs-lookup"><span data-stu-id="7effa-418">CountryOfOrigin</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-disposition.png" alt="Disposition step icon" title="Icona del passaggio di smaltimento"><br><span data-ttu-id="7effa-420">Disposition</span><span class="sxs-lookup"><span data-stu-id="7effa-420">Disposition</span></span></td>
<td><img src="media/step-icons-done.png" alt="Done step icon" title="Icona del passaggio Fatto"><br><span data-ttu-id="7effa-422">Fatto</span><span class="sxs-lookup"><span data-stu-id="7effa-422">Done</span></span></td>
<td><img src="media/step-icons-driver-check-in-confirmation.png" alt="Driver check in confirmation step icon" title="Icona del passaggio di conferma del check in del conducente"><br><span data-ttu-id="7effa-424">DriverCheckInConfirmation</span><span class="sxs-lookup"><span data-stu-id="7effa-424">DriverCheckInConfirmation</span></span></td>
<td><img src="media/step-icons-driver-check-in-id.png" alt="Driver check in ID step icon" title="Icona del passaggio dell'ID di check in del conducente"><br><span data-ttu-id="7effa-426">DriverCheckInId</span><span class="sxs-lookup"><span data-stu-id="7effa-426">DriverCheckInId</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-driver-check-out-id.png" alt="Driver check out ID step icon" title="Icona del passaggio dell'ID di check out del conducente"><br><span data-ttu-id="7effa-428">DriverCheckOutId</span><span class="sxs-lookup"><span data-stu-id="7effa-428">DriverCheckOutId</span></span></td>
<td><img src="media/step-icons-exp-date.png" alt="Expiration date step icon" title="Icona del passaggio della data di scadenza"><br><span data-ttu-id="7effa-430">ExpDate</span><span class="sxs-lookup"><span data-stu-id="7effa-430">ExpDate</span></span></td>
<td><img src="media/step-icons-field.png" alt="Field step icon" title="Icona del passaggio del campo"><br><span data-ttu-id="7effa-432">Campo</span><span class="sxs-lookup"><span data-stu-id="7effa-432">Field</span></span></td>
<td><img src="media/step-icons-from-batch.png" alt="From batch disposition step icon" title="Icona del passaggio da smaltimento batch"><br><span data-ttu-id="7effa-434">FromBatchDisposition</span><span class="sxs-lookup"><span data-stu-id="7effa-434">FromBatchDisposition</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-from-inventory-status.png" alt="From inventory status step icon" title="Icona del passaggio da stato inventario"><br><span data-ttu-id="7effa-436">FromInventoryStatus</span><span class="sxs-lookup"><span data-stu-id="7effa-436">FromInventoryStatus</span></span></td>
<td><img src="media/step-icons-id-attribute.png" alt="ID attribute step icon" title="Icona del passaggio attributo ID"><br><span data-ttu-id="7effa-438">IdAttribute</span><span class="sxs-lookup"><span data-stu-id="7effa-438">IdAttribute</span></span></td>
<td><img src="media/step-icons-invent-batch-id.png" alt="Inventory batch ID step icon" title="Icona del passaggio dell'ID batch dell'inventario"><br><span data-ttu-id="7effa-440">InventBatchID</span><span class="sxs-lookup"><span data-stu-id="7effa-440">InventBatchID</span></span></td>
<td><img src="media/step-icons-invent-color-id.png" alt="Inventory color ID step icon" title="Icona del passaggio dell'ID colore inventario"><br><span data-ttu-id="7effa-442">InventColorID</span><span class="sxs-lookup"><span data-stu-id="7effa-442">InventColorID</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-invent-location.png" alt="Inventory location step icon" title="Icona del passaggio posizione inventario"><br><span data-ttu-id="7effa-444">InventLocation</span><span class="sxs-lookup"><span data-stu-id="7effa-444">InventLocation</span></span></td>
<td><img src="media/step-icons-invent-serial-id.png" alt="Inventory serial ID step icon" title="Icona del passaggio dell'ID seriale inventario"><br><span data-ttu-id="7effa-446">InventSerialID</span><span class="sxs-lookup"><span data-stu-id="7effa-446">InventSerialID</span></span></td>
<td><img src="media/step-icons-invent-size-id.png" alt="Inventory size ID step icon" title="Icona del passaggio ID dimensioni inventario"><br><span data-ttu-id="7effa-448">InventSizeID</span><span class="sxs-lookup"><span data-stu-id="7effa-448">InventSizeID</span></span></td>
<td><img src="media/step-icons-invent-status-id.png" alt="Inventory status ID step icon" title="Icona del passaggio ID stato inventario"><br><span data-ttu-id="7effa-450">InventStatusID</span><span class="sxs-lookup"><span data-stu-id="7effa-450">InventStatusID</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-invent-style-id.png" alt="Inventory style ID step icon" title="Icona del passaggio ID stile inventario"><br><span data-ttu-id="7effa-452">InventStyleID</span><span class="sxs-lookup"><span data-stu-id="7effa-452">InventStyleID</span></span></td>
<td><img src="media/step-icons-invent-version-id.png" alt="Inventory version ID step icon" title="Icona del passaggio ID versione inventario"><br><span data-ttu-id="7effa-454">InventVersionID</span><span class="sxs-lookup"><span data-stu-id="7effa-454">InventVersionID</span></span></td>
<td><img src="media/step-icons-item-id.png" alt="Item ID step icon" title="Icona del passaggio ID articolo"><br><span data-ttu-id="7effa-456">ItemID</span><span class="sxs-lookup"><span data-stu-id="7effa-456">ItemID</span></span></td>
<td><img src="media/step-icons-itm-contianer-id.png" alt="ITM container ID step icon" title="Icona del passaggio ID contenitore ITM"><br><span data-ttu-id="7effa-458">ITMContainerID</span><span class="sxs-lookup"><span data-stu-id="7effa-458">ITMContainerID</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-itm-shipment-id.png" alt="ITM shipment ID step icon" title="Icona del passaggio ID spedizione ITM"><br><span data-ttu-id="7effa-460">ITMShipmentID</span><span class="sxs-lookup"><span data-stu-id="7effa-460">ITMShipmentID</span></span></td>
<td><img src="media/step-icons-kanban-card-id.png" alt="Kanban card ID step icon" title="Icona del passaggio ID scheda kanban"><br><span data-ttu-id="7effa-462">KanbanCardID</span><span class="sxs-lookup"><span data-stu-id="7effa-462">KanbanCardID</span></span></td>
<td><img src="media/step-icons-kanban-or-card-id.png" alt="Kanban or card ID step icon" title="Icona del passaggio ID scheda o kanban"><br><span data-ttu-id="7effa-464">KanbanOrCardID</span><span class="sxs-lookup"><span data-stu-id="7effa-464">KanbanOrCardID</span></span></td>
<td><img src="media/step-icons-license-plate-id.png" alt="License plate ID step icon" title="Icona del passaggio ID targa"><br><span data-ttu-id="7effa-466">LicensePlateID</span><span class="sxs-lookup"><span data-stu-id="7effa-466">LicensePlateID</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-load-id.png" alt="Load ID step icon" title="Icona del passaggio ID carico"><br><span data-ttu-id="7effa-468">LoadId</span><span class="sxs-lookup"><span data-stu-id="7effa-468">LoadId</span></span></td>
<td><img src="media/step-icons-location-lp-pos.png" alt="Location license plate position step icon" title="Icona del passaggio posizionamento targa ubicazione"><br><span data-ttu-id="7effa-470">LocationLicensePlatePosition</span><span class="sxs-lookup"><span data-stu-id="7effa-470">LocationLicensePlatePosition</span></span></td>
<td><img src="media/step-icons-location-or-lp.png" alt="Location or license plate step icon" title="Icona del passaggio targa o ubicazione"><br><span data-ttu-id="7effa-472">LocOrLP</span><span class="sxs-lookup"><span data-stu-id="7effa-472">LocOrLP</span></span></td>
<td><img src="media/step-icons-location-or-lp-check.png" alt="Location or license plate check step icon" title="Icona del passaggio di controllo della targa o dell'ubicazione"><br><span data-ttu-id="7effa-474">LocOrLPCheck</span><span class="sxs-lookup"><span data-stu-id="7effa-474">LocOrLPCheck</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-location-or-lp-from.png" alt="Location or license plate from step icon" title="Icona del passaggio dalla targa o ubicazione"><br><span data-ttu-id="7effa-476">LocOrLPFrom</span><span class="sxs-lookup"><span data-stu-id="7effa-476">LocOrLPFrom</span></span></td>
<td><img src="media/step-icons-location-or-lp-to.png" alt="Location or license plate to step icon" title="Icona del passaggio a targa o ubicazione"><br><span data-ttu-id="7effa-478">LocOrLPTo</span><span class="sxs-lookup"><span data-stu-id="7effa-478">LocOrLPTo</span></span></td>
<td><img src="media/step-icons-long-process-complete.png" alt="Long process completed step icon" title="Icona del passaggio di processo lungo completato"><br><span data-ttu-id="7effa-480">LongProcessCompleted</span><span class="sxs-lookup"><span data-stu-id="7effa-480">LongProcessCompleted</span></span></td>
<td><img src="media/step-icons-lp-break-parent.png" alt="LP break parent LP step icon" title="Icona del passaggio targa padre di interruzione targa"><br><span data-ttu-id="7effa-482">LPBreakParentLP</span><span class="sxs-lookup"><span data-stu-id="7effa-482">LPBreakParentLP</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-merge-container.png" alt="Merge container ID step icon" title="Icona del passaggio ID contenitore unione"><br><span data-ttu-id="7effa-484">MergeContainerId</span><span class="sxs-lookup"><span data-stu-id="7effa-484">MergeContainerId</span></span></td>
<td><img src="media/step-icons-mixed-lp-line.png" alt="Mixed license plate line number step icon" title="Icona del passaggio del numero di riga di targa mista"><br><span data-ttu-id="7effa-486">MixedLPLineNum</span><span class="sxs-lookup"><span data-stu-id="7effa-486">MixedLPLineNum</span></span></td>
<td><img src="media/step-icons-outbound-weight.png" alt="Outbound weight step icon" title="Icona del passo di peso in uscita"><br><span data-ttu-id="7effa-488">OutboundWeight</span><span class="sxs-lookup"><span data-stu-id="7effa-488">OutboundWeight</span></span></td>
<td><img src="media/step-icons-owner.png" alt="Owner step icon" title="Icona del passaggio del proprietario"><br><span data-ttu-id="7effa-490">Proprietario</span><span class="sxs-lookup"><span data-stu-id="7effa-490">Owner</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-parent-lp.png" alt="Parent license plate step icon" title="Icona del passaggio della targa padre"><br><span data-ttu-id="7effa-492">ParentLP</span><span class="sxs-lookup"><span data-stu-id="7effa-492">ParentLP</span></span></td>
<td><img src="media/step-icons-please-confirm.png" alt="Please confirm step icon" title="Icona del passaggio Conferma"><br><span data-ttu-id="7effa-494">PleaseConfirm</span><span class="sxs-lookup"><span data-stu-id="7effa-494">PleaseConfirm</span></span></td>
<td><img src="media/step-icons-po-line-num.png" alt="Purchase order line number step icon" title="Icona del passaggio numero di riga ordine fornitore"><br><span data-ttu-id="7effa-496">POLineNum</span><span class="sxs-lookup"><span data-stu-id="7effa-496">POLineNum</span></span></td>
<td><img src="media/step-icons-po-num.png" alt="Purchase order number step icon" title="Icona del passaggio numero ordine fornitore"><br><span data-ttu-id="7effa-498">Numero ordine fornitore</span><span class="sxs-lookup"><span data-stu-id="7effa-498">PONum</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-position-full.png" alt="Position full step icon" title="Icona del passaggio Posizione piena"><br><span data-ttu-id="7effa-500">PositionFull</span><span class="sxs-lookup"><span data-stu-id="7effa-500">PositionFull</span></span></td>
<td><img src="media/step-icons-potency.png" alt="Potency step icon" title="Icona del passaggio di potenza"><br><span data-ttu-id="7effa-502">Potenza</span><span class="sxs-lookup"><span data-stu-id="7effa-502">Potency</span></span></td>
<td><img src="media/step-icons-printer-name.png" alt="Printer name step icon" title="Icona del passaggio del nome della stampante"><br><span data-ttu-id="7effa-504">PrinterName</span><span class="sxs-lookup"><span data-stu-id="7effa-504">PrinterName</span></span></td>
<td><img src="media/step-icons-prod-id.png" alt="Prod ID step icon" title="Icona del passaggio ID produzione"><br><span data-ttu-id="7effa-506">ProdId</span><span class="sxs-lookup"><span data-stu-id="7effa-506">ProdId</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-product-confirm.png" alt="Product confirmation step icon" title="Icona del passaggio di conferma del prodotto"><br><span data-ttu-id="7effa-508">ProductConfirmation</span><span class="sxs-lookup"><span data-stu-id="7effa-508">ProductConfirmation</span></span></td>
<td><img src="media/step-icons-put.png" alt="Put step icon" title="Icona del passaggio Put"><br><span data-ttu-id="7effa-510">Inserisci</span><span class="sxs-lookup"><span data-stu-id="7effa-510">Put</span></span></td>
<td><img src="media/step-icons-putaway-cluster-id.png" alt="Putaway cluster ID step icon" title="Icona del passaggio ID cluster stoccaggio"><br><span data-ttu-id="7effa-512">PutawayClusterId</span><span class="sxs-lookup"><span data-stu-id="7effa-512">PutawayClusterId</span></span></td>
<td><img src="media/step-icons-qty.png" alt="Quantity step icon" title="Icona del passaggio di quantità"><br><span data-ttu-id="7effa-514">Quantità</span><span class="sxs-lookup"><span data-stu-id="7effa-514">Qty</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-qty-adjust-in.png" alt="Quantity adjust in step icon" title="Icona del passaggio regolazione della quantità in entrata"><br><span data-ttu-id="7effa-516">QtyAdjustIn</span><span class="sxs-lookup"><span data-stu-id="7effa-516">QtyAdjustIn</span></span></td>
<td><img src="media/step-icons-qty-short.png" alt="Quantity short step icon" title="Icona del passaggio di quantità scarsa"><br><span data-ttu-id="7effa-518">QtyShort</span><span class="sxs-lookup"><span data-stu-id="7effa-518">QtyShort</span></span></td>
<td><img src="media/step-icons-qty-to-consume.png" alt="Quantity to consume step icon" title="Icona del passaggio Quantità da consumare"><br><span data-ttu-id="7effa-520">QtyToConsume</span><span class="sxs-lookup"><span data-stu-id="7effa-520">QtyToConsume</span></span></td>
<td><img src="media/step-icons-qty-to-put.png" alt="Quantity to put step icon" title="Icona del passaggio Quantità da stoccare"><br><span data-ttu-id="7effa-522">QtyToPut</span><span class="sxs-lookup"><span data-stu-id="7effa-522">QtyToPut</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-qty-to-scrap.png" alt="Quantity to scrap step icon" title="Icona del passaggio Quantità da scartare"><br><span data-ttu-id="7effa-524">QtyToScrap</span><span class="sxs-lookup"><span data-stu-id="7effa-524">QtyToScrap</span></span></td>
<td><img src="media/step-icons-qty-confirmation.png" alt="Quantity confirmation step icon" title="Icona del passaggio di conferma della quantità"><br><span data-ttu-id="7effa-526">QuantityConfirmation</span><span class="sxs-lookup"><span data-stu-id="7effa-526">QuantityConfirmation</span></span></td>
<td><img src="media/step-icons-raf-end-job.png" alt="Report as finished end job step icon" title="Icona del passaggio Segnala come processo finito"><br><span data-ttu-id="7effa-528">RAFEndJob</span><span class="sxs-lookup"><span data-stu-id="7effa-528">RAFEndJob</span></span></td>
<td><img src="media/step-icons-recv-loc-id.png" alt="Receive location ID step icon" title="Icona del passaggio ID della posizione di ricevimento"><br><span data-ttu-id="7effa-530">RecvLocationID</span><span class="sxs-lookup"><span data-stu-id="7effa-530">RecvLocationID</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-remove-container-id.png" alt="Remove container ID step icon" title="Icona del passaggio rimuovi ID contenitore"><br><span data-ttu-id="7effa-532">RemoveContainerID</span><span class="sxs-lookup"><span data-stu-id="7effa-532">RemoveContainerID</span></span></td>
<td><img src="media/step-icons-rma-no.png" alt="RMA number step icon" title="Icona del passaggio del numero RMA"><br><span data-ttu-id="7effa-534">RMANum</span><span class="sxs-lookup"><span data-stu-id="7effa-534">RMANum</span></span></td>
<td><img src="media/step-icons-select-order.png" alt="Select order step icon" title="Icona del passaggio Seleziona ordine"><br><span data-ttu-id="7effa-536">SelectOrder</span><span class="sxs-lookup"><span data-stu-id="7effa-536">SelectOrder</span></span></td>
<td><img src="media/step-icons-short-pick-reason.png" alt="Short pick reason step icon" title="Icona del passaggio del motivo del prelievo in difetto"><br><span data-ttu-id="7effa-538">ShortPickReason</span><span class="sxs-lookup"><span data-stu-id="7effa-538">ShortPickReason</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-sort-position-id.png" alt="Sort position ID step icon" title="Icona del passaggio ID posizione ordinamento"><br><span data-ttu-id="7effa-540">SortPositionId</span><span class="sxs-lookup"><span data-stu-id="7effa-540">SortPositionId</span></span></td>
<td><img src="media/step-icons-target-lp-id.png" alt="Target license plate ID step icon" title="Icona del passaggio ID targa di destinazione"><br><span data-ttu-id="7effa-542">TargetLicensePlateId</span><span class="sxs-lookup"><span data-stu-id="7effa-542">TargetLicensePlateId</span></span></td>
<td><img src="media/step-icons-to-line-no.png" alt="To line number step icon" title="Icona del passaggio numero di riga di destinazione"><br><span data-ttu-id="7effa-544">ToLineNum</span><span class="sxs-lookup"><span data-stu-id="7effa-544">ToLineNum</span></span></td>
<td><img src="media/step-icons-to-location.png" alt="To location step icon" title="Icona del passaggio posizione destinazione"><br><span data-ttu-id="7effa-546">ToLocation</span><span class="sxs-lookup"><span data-stu-id="7effa-546">ToLocation</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-to-number.png" alt="To number step icon" title="Icona del passaggio del numero destinazione"><br><span data-ttu-id="7effa-548">ToNum</span><span class="sxs-lookup"><span data-stu-id="7effa-548">ToNum</span></span></td>
<td><img src="media/step-icons-to-warehouse.png" alt="To warehouse step icon" title="Icona del passaggio Al magazzino"><br><span data-ttu-id="7effa-550">ToWarehouse</span><span class="sxs-lookup"><span data-stu-id="7effa-550">ToWarehouse</span></span></td>
<td><img src="media/step-icons-tranport-load-id.png" alt="Transport load ID step icon" title="Icona del passaggio ID carico trasporto"><br><span data-ttu-id="7effa-552">TransportLoadId</span><span class="sxs-lookup"><span data-stu-id="7effa-552">TransportLoadId</span></span></td>
<td><img src="media/step-icons-vendor-batch-id.png" alt="Vendor batch ID step icon" title="Icona del passaggio dell'ID batch fornitore"><br><span data-ttu-id="7effa-554">VendBatchId</span><span class="sxs-lookup"><span data-stu-id="7effa-554">VendBatchId</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-wave-label-id.png" alt="Wave label ID step icon" title="Icona del passaggio ID etichetta ondata"><br><span data-ttu-id="7effa-556">WaveLabelId</span><span class="sxs-lookup"><span data-stu-id="7effa-556">WaveLabelId</span></span></td>
<td><img src="media/step-icons-wave-label-qty.png" alt="Wave label quantity step icon" title="Icona del passaggio quantità etichetta ondata"><br><span data-ttu-id="7effa-558">WaveLblQty</span><span class="sxs-lookup"><span data-stu-id="7effa-558">WaveLblQty</span></span></td>
<td><img src="media/step-icons-weight.png" alt="Weight step icon" title="Icona del passo del peso"><br><span data-ttu-id="7effa-560">Peso</span><span class="sxs-lookup"><span data-stu-id="7effa-560">Weight</span></span></td>
<td><img src="media/step-icons-weight-to-consume.png" alt="Weight to consume step icon" title="Icona del passaggio Peso da consumare"><br><span data-ttu-id="7effa-562">WeightToConsume</span><span class="sxs-lookup"><span data-stu-id="7effa-562">WeightToConsume</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-whs-adjustment-type.png" alt="WHS adjustment type step icon" title="Icona del passaggio del tipo di rettifica magazzino"><br><span data-ttu-id="7effa-564">WHSAdjustmentType</span><span class="sxs-lookup"><span data-stu-id="7effa-564">WHSAdjustmentType</span></span></td>
<td><img src="media/step-icons-whs-receiving-exception.png" alt="WHS receiving exception step icon" title="Icona del passaggio di eccezione ricezione magazzino"><br><span data-ttu-id="7effa-566">WHSReceivingException</span><span class="sxs-lookup"><span data-stu-id="7effa-566">WHSReceivingException</span></span></td>
<td><img src="media/step-icons-wms-location-id.png" alt="WMS location ID step icon" title="Icona del passaggio ID ubicazione magazzino"><br><span data-ttu-id="7effa-568">WMSLocationID</span><span class="sxs-lookup"><span data-stu-id="7effa-568">WMSLocationID</span></span></td>
<td><img src="media/step-icons-work-id.png" alt="Work ID step icon" title="Icona del passaggio ID lavoro"><br><span data-ttu-id="7effa-570">WorkId</span><span class="sxs-lookup"><span data-stu-id="7effa-570">WorkId</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-work-id-to-cancel.png" alt="Work ID to cancel step icon" title="Icona del passaggio ID lavoro da annullare"><br><span data-ttu-id="7effa-572">WorkIdToCancel</span><span class="sxs-lookup"><span data-stu-id="7effa-572">WorkIdToCancel</span></span></td>
<td><img src="media/step-icons-work-lp-id.png" alt="Work license plate ID step icon" title="Icona del passaggio ID targa lavoro"><br><span data-ttu-id="7effa-574">WorkLicensePlateId</span><span class="sxs-lookup"><span data-stu-id="7effa-574">WorkLicensePlateId</span></span></td>
<td><img src="media/step-icons-work-lp-putaway-cluster.png" alt="Work license plate ID putaway cluster step icon" title="Icona del passaggio cluster di stocccaggio ID targa lavoro"><br><span data-ttu-id="7effa-576">WorkLPIDPutawayCluster</span><span class="sxs-lookup"><span data-stu-id="7effa-576">WorkLPIDPutawayCluster</span></span></td>
<td><img src="media/step-icons-work-pool-id.png" alt="Work pool ID step icon" title="Icona del passaggio ID pool lavoro"><br><span data-ttu-id="7effa-578">WorkPoolID</span><span class="sxs-lookup"><span data-stu-id="7effa-578">WorkPoolID</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-zone-pool-id.png" alt="Zone ID step icon" title="Icona del passaggio ID zona"><br><span data-ttu-id="7effa-580">ZoneID</span><span class="sxs-lookup"><span data-stu-id="7effa-580">ZoneID</span></span></td>
<td></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>

## <a name="example-assign-step-icons-and-titles-for-a-custom-flow"></a><a name="example"></a><span data-ttu-id="7effa-581">Esempio: assegnare icone e titoli dei passaggi per un flusso personalizzato</span><span class="sxs-lookup"><span data-stu-id="7effa-581">Example: Assign step icons and titles for a custom flow</span></span>

<span data-ttu-id="7effa-582">Questo esempio spiega come configurare le icone e i titoli dei passaggi per un flusso di attività personalizzato.</span><span class="sxs-lookup"><span data-stu-id="7effa-582">This example explains how to set up step icons and titles for a custom task flow.</span></span> <span data-ttu-id="7effa-583">Lo scenario si basa su un esempio di un flusso di attività personalizzato che viene presentato ed esplorato in modo più dettagliato nel seguente post del blog: [Personalizzazione dell'app per dispositivi mobili Warehousing](https://cloudblogs.microsoft.com/dynamics365/it/2017/07/06/customizing-the-warehousing-mobile-app).</span><span class="sxs-lookup"><span data-stu-id="7effa-583">The scenario is built on an example of a custom task flow that is presented and explored in more detail in the following blog post: [Customizing the Warehousing Mobile App](https://cloudblogs.microsoft.com/dynamics365/it/2017/07/06/customizing-the-warehousing-mobile-app).</span></span> <span data-ttu-id="7effa-584">Il flusso delle attività funziona nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="7effa-584">The task flow works in the following way:</span></span>

1. <span data-ttu-id="7effa-585">L'app mostra una pagina che richiede al lavoratore di fornire un ID contenitore (ad esempio, effettuando la scansione di un codice a barre).</span><span class="sxs-lookup"><span data-stu-id="7effa-585">The app shows a page that prompts the worker to provide a container ID (for example, by scanning a bar code).</span></span>
1. <span data-ttu-id="7effa-586">Se l'ID contenitore è valido, l'app apre una nuova pagina che richiede al lavoratore il peso.</span><span class="sxs-lookup"><span data-stu-id="7effa-586">If the container ID is valid, the app opens a new page that prompts the worker for the weight.</span></span> <span data-ttu-id="7effa-587">(Se l'ID contenitore non è valido, il lavoratore viene indirizzato nuovamente alla prima pagina.)</span><span class="sxs-lookup"><span data-stu-id="7effa-587">(If the container ID isn't valid, the worker is returned to the first page.)</span></span>
1. <span data-ttu-id="7effa-588">Quando il lavoratore immette un peso valido, il sistema memorizza il peso e riporta il lavoratore alla prima pagina.</span><span class="sxs-lookup"><span data-stu-id="7effa-588">When the worker enters a valid weight, the system stores the weight and returns the worker to the first page.</span></span>

<span data-ttu-id="7effa-589">Nella figura seguente viene illustrato questo flusso di attività.</span><span class="sxs-lookup"><span data-stu-id="7effa-589">The following illustration shows this task flow.</span></span>

<span data-ttu-id="7effa-590">![Diagramma del flusso di attività](media/step-icons-example-task-flow.png "Diagramma del flusso di attività")</span><span class="sxs-lookup"><span data-stu-id="7effa-590">![Task flow diagram](media/step-icons-example-task-flow.png "Task flow diagram")</span></span>

### <a name="create-a-step-class-for-the-container-input-page"></a><span data-ttu-id="7effa-591">Creare una classe di passaggio per la pagina di input del contenitore</span><span class="sxs-lookup"><span data-stu-id="7effa-591">Create a step class for the container input page</span></span>

<span data-ttu-id="7effa-592">La pagina di input del contenitore consente all'operatore di eseguire la scansione o di inserire un ID contenitore.</span><span class="sxs-lookup"><span data-stu-id="7effa-592">The container input page lets the worker scan or enter a container ID.</span></span>

<span data-ttu-id="7effa-593">![Pagina di input del contenitore](media/step-icons-example-container-input.png "Pagina di input del contenitore")</span><span class="sxs-lookup"><span data-stu-id="7effa-593">![Container input page](media/step-icons-example-container-input.png "Container input page")</span></span>

<span data-ttu-id="7effa-594">Nella pagina di input del contenitore, il nome del controllo del campo di input è `ContainerId`.</span><span class="sxs-lookup"><span data-stu-id="7effa-594">On the container input page, the control name of the input field is `ContainerId`.</span></span> <span data-ttu-id="7effa-595">Poiché questo nome di controllo non è nell'[elenco di ID passaggio](#step-ids-classes), non troverai un passaggio esistente basato su di esso.</span><span class="sxs-lookup"><span data-stu-id="7effa-595">Because this control name isn't in the [list of step IDs](#step-ids-classes), you won't find an existing step that is based on it.</span></span> <span data-ttu-id="7effa-596">Pertanto, è necessario creare una classe di passaggio che rappresenti il passaggio.</span><span class="sxs-lookup"><span data-stu-id="7effa-596">Therefore, you must create a step class that represents the step.</span></span> <span data-ttu-id="7effa-597">Ecco un esempio.</span><span class="sxs-lookup"><span data-stu-id="7effa-597">Here is an example.</span></span>

```xpp
[WHSMobileAppStepId('ContainerId')]
final internal class WHSMobileAppStepContainerId extends WHSMobileAppStep
{
    private const WHSMobileAppStepIcon PopulationIcon = 'InventBatchID';
    private const WHSMobileAppStepTitle InputNotFilledTitle = "@WAX:WHSMobileAppStepContainerID_InputNotFilled"; //Scan a container
    protected void initValues()
    {
        defaultStepIcon = PopulationIcon;
        defaultStepTitle = InputNotFilledTitle;
    }
}
```

<span data-ttu-id="7effa-598">L'identificatore dell'icona del passaggio è archiviato nel membro della classe `defaultStepIcon` e il titolo del passaggio viene archiviato nel membro della classe `defaultStepTitle`.</span><span class="sxs-lookup"><span data-stu-id="7effa-598">The identifier of the step icon is stored in the `defaultStepIcon` class member, and the step title is stored in the `defaultStepTitle` class member.</span></span>

<span data-ttu-id="7effa-599">Per assegnare un'icona di passaggio, imposta `defaultStepIcon` su uno degli ID icona elencati nella sezione [Icone dei passaggi disponibili](#step-icons) precedente in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="7effa-599">To assign a step icon, set `defaultStepIcon` to one of the icon IDs that are listed in the [Available step icons](#step-icons) section earlier in this topic.</span></span>

### <a name="use-a-standard-or-custom-step-icon-and-title-for-the-weight-input"></a><span data-ttu-id="7effa-600">Utilizzare un'icona di passaggio standard o personalizzata e un titolo per l'immissione del peso</span><span class="sxs-lookup"><span data-stu-id="7effa-600">Use a standard or custom step icon and title for the weight input</span></span>

<span data-ttu-id="7effa-601">La pagina di input del peso consente al lavoratore di inserire un peso.</span><span class="sxs-lookup"><span data-stu-id="7effa-601">The weight input page lets the worker enter a weight.</span></span>

<span data-ttu-id="7effa-602">![Pagina di input del peso](media/step-icons-example-weight-input.png "Pagina di input del peso")</span><span class="sxs-lookup"><span data-stu-id="7effa-602">![Weight input page](media/step-icons-example-weight-input.png "Weight input page")</span></span>

<span data-ttu-id="7effa-603">Nella pagina di input del peso, il nome del controllo del campo di input è `Weight`, che si trova nell'[elenco di ID di passaggio](#step-ids-classes).</span><span class="sxs-lookup"><span data-stu-id="7effa-603">On the weight input page, the control name of the input field is `Weight`, which is in the [list of step IDs](#step-ids-classes).</span></span> <span data-ttu-id="7effa-604">Pertanto, se l'icona e il titolo del passaggio definiti nella classe `WHSMobileAppStepWeight` sono accettabili per te, non devi cambiare nulla per questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="7effa-604">Therefore, if the step icon and title that are defined in the `WHSMobileAppStepWeight` class are acceptable to you, you don't have to change anything for this step.</span></span>

<span data-ttu-id="7effa-605">Tuttavia, se preferisci utilizzare un'icona o un titolo diverso per questo passaggio, è possibile sostituire il metodo `stepId()` o il metodo `stepInfo()` nella classe builder.</span><span class="sxs-lookup"><span data-stu-id="7effa-605">However, if you prefer to use a different icon or title for this step, you can override either the `stepId()` method or the `stepInfo()` method in the builder class.</span></span> <span data-ttu-id="7effa-606">Ogni flusso di attività ha il proprio generatore di informazioni sui passaggi.</span><span class="sxs-lookup"><span data-stu-id="7effa-606">Each task flow has its own step info builder.</span></span>

#### <a name="override-the-stepid-method"></a><span data-ttu-id="7effa-607">Sostituire il metodo stepId()</span><span class="sxs-lookup"><span data-stu-id="7effa-607">Override the stepId() method</span></span>

<span data-ttu-id="7effa-608">L'esempio seguente mostra un modo in cui è possibile modificare una classe builder sovrascrivendo il metodo `stepId()`.</span><span class="sxs-lookup"><span data-stu-id="7effa-608">The following example shows one way that you can modify a builder class by overriding the `stepId()` method.</span></span>

```xpp
[WHSWorkExecuteMode(WHSWorkExecuteMode:: WeighContainer)]
public class WHSMobileAppStepInfoBuilderWeighContainer extends WHSMobileAppStepInfoBuilder
{
    protected WHSMobileAppStepId stepId()
    {
        WHSMobileAppStepId stepIdLocal = super();
        if (stepIdLocal == 'Weight')
        {
            return 'NewWeight';
        }
        return stepIdLocal;
    }
}
```

<span data-ttu-id="7effa-609">Quindi crei una classe di passaggi per il passaggio `NewWeight`.</span><span class="sxs-lookup"><span data-stu-id="7effa-609">You then create a step class for the `NewWeight` step.</span></span> <span data-ttu-id="7effa-610">Il codice dovrebbe essere simile al codice per l'esempio `ContainerId` mostrato in precedenza in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="7effa-610">The code should resemble the code for the `ContainerId` example that was shown earlier in this topic.</span></span>

#### <a name="override-the-stepinfo-method"></a><span data-ttu-id="7effa-611">Sostituire il metodo stepInfo()</span><span class="sxs-lookup"><span data-stu-id="7effa-611">Override the stepInfo() method</span></span>

<span data-ttu-id="7effa-612">L'esempio seguente mostra un modo in cui è possibile modificare una classe builder sovrascrivendo il metodo `stepInfo()`.</span><span class="sxs-lookup"><span data-stu-id="7effa-612">The following example shows one way that you can modify a builder class by overriding the `stepInfo()` method.</span></span>

```xpp
[WHSWorkExecuteMode(WHSWorkExecuteMode:: WeighContainer)]
public class WHSMobileAppStepInfoBuilderWeighContainer extends WHSMobileAppStepInfoBuilder
{
    protected WHSMobileAppStepInfo stepInfo()
    {
        if (stepId != 'Weight')
        {
            return super();
        }
        WHSMobileAppStepInfo stepInfo = WHSMobileAppStepInfo::construct();
        stepInfo.parmStepIcon('NewIcon');
        stepInfo.parmStepTitle('NewTitle');
        return stepInfo;
    }
}
```

<span data-ttu-id="7effa-613">Quindi costruisci un oggetto `WHSMobileAppStepInfo` e imposti direttamente l'icona e/o il titolo.</span><span class="sxs-lookup"><span data-stu-id="7effa-613">You then construct a `WHSMobileAppStepInfo` object, and set the icon and/or title directly.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="7effa-614">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="7effa-614">Additional resources</span></span>

- [<span data-ttu-id="7effa-615">Installare e connettere l'app per dispositivi mobili Gestione magazzino</span><span class="sxs-lookup"><span data-stu-id="7effa-615">Install and connect the Warehouse Management mobile app</span></span>](install-configure-warehouse-management-app.md)
- [<span data-ttu-id="7effa-616">Impostazioni utente dispositivo mobile</span><span class="sxs-lookup"><span data-stu-id="7effa-616">Mobile device user settings</span></span>](mobile-device-user-settings.md)
