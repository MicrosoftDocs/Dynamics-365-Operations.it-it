---
title: Risorse interne per la manutenzione
description: In questo argomento viene descritto come utilizzare Microsoft Dtnamics 365 Field Service per servire le risorse dei clienti e le risorse interne.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-01-27
ms.openlocfilehash: 1e423199d0639db5e403e280880036b590149095
ms.sourcegitcommit: 68f1485de7d64a6c9eba1088af63bd07992d972d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/27/2020
ms.locfileid: "3172948"
---
# <a name="in-house-assets-for-servicing"></a><span data-ttu-id="647c7-103">Risorse interne per la manutenzione</span><span class="sxs-lookup"><span data-stu-id="647c7-103">In-house assets for servicing</span></span>

[!include [banner](../../includes/banner.md)]



<span data-ttu-id="647c7-104">Microsoft Dynamics 365 Field Service è progettato per servire le risorse dei clienti.</span><span class="sxs-lookup"><span data-stu-id="647c7-104">Microsoft Dynamics 365 Field Service is designed to service customer assets.</span></span> <span data-ttu-id="647c7-105">La gestione dei cespiti per Dynamics 365 Supply Chain Management è progettata per mantenere le risorse interne.</span><span class="sxs-lookup"><span data-stu-id="647c7-105">Asset management for Dynamics 365 Supply Chain Management is designed to maintain in-house assets.</span></span> <span data-ttu-id="647c7-106">L'integrazione di queste due app consente di utilizzare Field Service per servire sia le risorse dei clienti sia le risorse interne.</span><span class="sxs-lookup"><span data-stu-id="647c7-106">Integration of these two apps lets you use Field Service to service both customer assets and in-house assets.</span></span> <span data-ttu-id="647c7-107">Inoltre, è possibile classificare i cespiti, in base alla posizione funzionale o alla gerarchia, e tenere traccia della manutenzione a livello dettagliato.</span><span class="sxs-lookup"><span data-stu-id="647c7-107">You can also classify the assets, based on functional location or hierarchy, and track the servicing at a detailed level.</span></span>

<span data-ttu-id="647c7-108">Per ulteriori informazioni, vedere [Integrare Dynamics 365 Field Service e Supply Chain Management](https://docs.microsoft.com/dynamics365/field-service/supply-chain-field-service-integration).</span><span class="sxs-lookup"><span data-stu-id="647c7-108">For more information, see [Integrate Dynamics 365 Field Service and Supply Chain Management](https://docs.microsoft.com/dynamics365/field-service/supply-chain-field-service-integration).</span></span>

## <a name="templates"></a><span data-ttu-id="647c7-109">Modelli</span><span class="sxs-lookup"><span data-stu-id="647c7-109">Templates</span></span>

<span data-ttu-id="647c7-110">Le risorse interne includono una raccolta di mappe di entità di base che funzionano in combinazione durante l'interazione con i dati, come illustrato nella seguente tabella.</span><span class="sxs-lookup"><span data-stu-id="647c7-110">In-house-assets include a collection of core entity maps that work together during data interaction, as shown in the following table.</span></span>

| <span data-ttu-id="647c7-111">App di Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="647c7-111">Finance and Operations apps</span></span> | <span data-ttu-id="647c7-112">App basate su modello in Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="647c7-112">Model-driven apps in Dynamics 365</span></span> | <span data-ttu-id="647c7-113">descrizione</span><span class="sxs-lookup"><span data-stu-id="647c7-113">Description</span></span> |
|-----------------------------|-----------------------------------|-------------|
| <span data-ttu-id="647c7-114">Modelli del ciclo di vita cespiti nella Gestione cespiti</span><span class="sxs-lookup"><span data-stu-id="647c7-114">Asset management asset lifecycle models</span></span> | <span data-ttu-id="647c7-115">msdyn\_assetlifecyclemodels</span><span class="sxs-lookup"><span data-stu-id="647c7-115">msdyn\_assetlifecyclemodels</span></span> | |
| <span data-ttu-id="647c7-116">Stati del ciclo di vita cespiti nella Gestione cespiti</span><span class="sxs-lookup"><span data-stu-id="647c7-116">Asset management asset lifecycle states</span></span> | <span data-ttu-id="647c7-117">msdyn\_assetlifecyclestates</span><span class="sxs-lookup"><span data-stu-id="647c7-117">msdyn\_assetlifecyclestates</span></span> | |
| <span data-ttu-id="647c7-118">Cespiti della Gestione cespiti</span><span class="sxs-lookup"><span data-stu-id="647c7-118">Asset management assets</span></span> | <span data-ttu-id="647c7-119">msdyn\_customerassets</span><span class="sxs-lookup"><span data-stu-id="647c7-119">msdyn\_customerassets</span></span> | |
| <span data-ttu-id="647c7-120">Tipi di cespite della Gestione cespiti</span><span class="sxs-lookup"><span data-stu-id="647c7-120">Asset management asset types</span></span> | <span data-ttu-id="647c7-121">msdyn\_customerassetcategories</span><span class="sxs-lookup"><span data-stu-id="647c7-121">msdyn\_customerassetcategories</span></span> | |
| <span data-ttu-id="647c7-122">Modelli del ciclo di vita unità funzionali della Gestione cespiti</span><span class="sxs-lookup"><span data-stu-id="647c7-122">Asset management functional location lifecycle models</span></span> | <span data-ttu-id="647c7-123">msdyn\_functionallocationlifecyclemodels</span><span class="sxs-lookup"><span data-stu-id="647c7-123">msdyn\_functionallocationlifecyclemodels</span></span> | |
| <span data-ttu-id="647c7-124">Stati del ciclo di vita unità funzionali della Gestione cespiti</span><span class="sxs-lookup"><span data-stu-id="647c7-124">Asset management functional location lifecycle states</span></span> | <span data-ttu-id="647c7-125">msdyn\_functionallocationlifecyclestates</span><span class="sxs-lookup"><span data-stu-id="647c7-125">msdyn\_functionallocationlifecyclestates</span></span> | |
| <span data-ttu-id="647c7-126">Unità funzionali della Gestione cespiti</span><span class="sxs-lookup"><span data-stu-id="647c7-126">Asset management functional locations</span></span> | <span data-ttu-id="647c7-127">msdyn\_functionallocations</span><span class="sxs-lookup"><span data-stu-id="647c7-127">msdyn\_functionallocations</span></span> | |
| <span data-ttu-id="647c7-128">Tipi di unità funzionali della Gestione cespiti</span><span class="sxs-lookup"><span data-stu-id="647c7-128">Asset management functional location types</span></span> | <span data-ttu-id="647c7-129">msdyn\_functionallocationtypes</span><span class="sxs-lookup"><span data-stu-id="647c7-129">msdyn\_functionallocationtypes</span></span> | |
| <span data-ttu-id="647c7-130">Produttori della Gestione cespiti</span><span class="sxs-lookup"><span data-stu-id="647c7-130">Asset management manufacturers</span></span> | <span data-ttu-id="647c7-131">msdyn\_manufacturers</span><span class="sxs-lookup"><span data-stu-id="647c7-131">msdyn\_manufacturers</span></span> | |
| <span data-ttu-id="647c7-132">Modelli della Gestione cespiti</span><span class="sxs-lookup"><span data-stu-id="647c7-132">Asset management models</span></span> | <span data-ttu-id="647c7-133">msdyn\_models</span><span class="sxs-lookup"><span data-stu-id="647c7-133">msdyn\_models</span></span> | |
| <span data-ttu-id="647c7-134">Garanzia della gestione cespiti</span><span class="sxs-lookup"><span data-stu-id="647c7-134">Asset management warranty</span></span> | <span data-ttu-id="647c7-135">msdyn\_warranties</span><span class="sxs-lookup"><span data-stu-id="647c7-135">msdyn\_warranties</span></span> | |

[!include [symbols](../../includes/dual-write-symbols.md)]

[!include [lifecycle models](includes/AssetManagementAssetLifecycleModels-msdyn-assetlifecyclemodels.md)]

[!include [lifecycle states](includes/AssetManagementAssetLifecycleStates-msdyn-assetlifecyclestates.md)]

[!include [assets](includes/AssetManagementAssets-msdyn-customerassets.md)]

[!include [asset types](includes/AssetManagementAssetTypes-msdyn-customerassetcategories.md)]

[!include [functional location lifecycle models](includes/AssetManagementFunctionalLocationLifecycleModels-msdyn-functionallocationlifecyclemodels.md)]

[!include [functional location lifecycle states](includes/AssetManagementFunctionalLocationLifecycleStates-msdyn-functionallocationlifecyclestates.md)]

[!include [functional locations](includes/AssetManagementFunctionalLocations-msdyn-functionallocations.md)]

[!include [functional location types](includes/AssetManagementFunctionalLocationTypes-msdyn-functionallocationtypes.md)]

[!include [manufacturers](includes/AssetManagementManufacturers-msdyn-manufacturers.md)]

[!include [models](includes/AssetManagementModels-msdyn-models.md)]

[!include [warranty](includes/AssetManagementWarranty-msdyn-warranties.md)]