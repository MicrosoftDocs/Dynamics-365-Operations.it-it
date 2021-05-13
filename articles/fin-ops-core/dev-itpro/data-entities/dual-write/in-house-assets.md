---
title: Cespiti interni per l'assistenza
description: Questo argomento descrive come puoi usare Microsoft Dynamics 365 Field Service per l'assistenza sia delle risorse dei clienti che quelle interne.
author: RamaKrishnamoorthy
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-01-27
ms.openlocfilehash: ebda6b5679ec601513fb6d046725b396e69fe0f3
ms.sourcegitcommit: a202bf67c3c2c054e2a47cb7b3145cb7c0ee635e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/25/2021
ms.locfileid: "5941416"
---
# <a name="in-house-assets-for-servicing"></a>Cespiti interni per l'assistenza

[!include [banner](../../includes/banner.md)]



Microsoft Dynamics 365 Field Service è progettato per servire le risorse dei clienti. La gestione dei cespiti per Dynamics 365 Supply Chain Management è progettata per mantenere le risorse interne. L'integrazione di queste due app consente di utilizzare Field Service per servire sia le risorse dei clienti sia le risorse interne. Inoltre, è possibile classificare i cespiti, in base alla posizione funzionale o alla gerarchia, e tenere traccia della manutenzione a livello dettagliato.

Per ulteriori informazioni, vedere [Integrare Dynamics 365 Field Service e Supply Chain Management](/dynamics365/field-service/supply-chain-field-service-integration).

## <a name="templates"></a>Modelli

Le risorse interne includono una raccolta di mappe della tabella di base che funzionano in combinazione durante l'interazione con i dati, come illustrato nella seguente tabella.

| App di Finance and Operations | App basate su modello in Dynamics 365 | Descrizione |
|-----------------------------|-----------------------------------|-------------|
| Modelli del ciclo di vita cespiti nella Gestione cespiti | msdyn\_assetlifecyclemodels | |
| Stati del ciclo di vita cespiti nella Gestione cespiti | msdyn\_assetlifecyclestates | |
| Cespiti della Gestione cespiti | msdyn\_customerassets | |
| Tipi di cespite della Gestione cespiti | msdyn\_customerassetcategories | |
| Modelli del ciclo di vita unità funzionali della Gestione cespiti | msdyn\_functionallocationlifecyclemodels | |
| Stati del ciclo di vita unità funzionali della Gestione cespiti | msdyn\_functionallocationlifecyclestates | |
| Unità funzionali della Gestione cespiti | msdyn\_functionallocations | |
| Tipi di unità funzionali della Gestione cespiti | msdyn\_functionallocationtypes | |
| Produttori della Gestione cespiti | msdyn\_manufacturers | |
| Modelli della Gestione cespiti | msdyn\_models | |
| Garanzia della gestione cespiti | msdyn\_warranties | |

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


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]