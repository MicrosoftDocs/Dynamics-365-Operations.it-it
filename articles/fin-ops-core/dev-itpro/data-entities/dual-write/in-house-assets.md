---
title: Cespiti interni per l'assistenza
description: Questo articolo descrive come puoi usare Microsoft Dynamics 365 Field Service per l'assistenza sia delle risorse dei clienti che quelle interne.
author: RamaKrishnamoorthy
ms.date: 01/27/2020
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-01-27
ms.openlocfilehash: b3e741c85fcad2abc18879280ef7332ae091c984
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9289252"
---
# <a name="in-house-assets-for-servicing"></a>Cespiti interni per l'assistenza

[!include [banner](../../includes/banner.md)]

Microsoft Dynamics 365 Field Service è progettato per servire le risorse dei clienti. La gestione dei cespiti per Dynamics 365 Supply Chain Management è progettata per mantenere le risorse interne. L'integrazione di queste due app consente di utilizzare Field Service per servire sia le risorse dei clienti sia le risorse interne. Inoltre, è possibile classificare i cespiti, in base alla posizione funzionale o alla gerarchia, e tenere traccia della manutenzione a livello dettagliato.

Per ulteriori informazioni, vedere [Integrare Dynamics 365 Field Service e Supply Chain Management](/dynamics365/field-service/supply-chain-field-service-integration).

## <a name="templates"></a>Modelli

Le risorse interne includono una raccolta di mappe della tabella di base che funzionano in combinazione durante l'interazione con i dati, come illustrato nella seguente tabella.

| App Finance and Operations | App di interazione con i clienti | descrizione |
|-----------------------------|-----------------------------------|-------------|
[Modelli del ciclo di vita cespiti nella Gestione cespiti](mapping-reference.md#119) | msdyn_assetlifecyclemodels | |
[Stati del ciclo di vita cespiti nella Gestione cespiti](mapping-reference.md#120) | msdyn_assetlifecyclestates | |
[Tipi di cespite della Gestione cespiti](mapping-reference.md#124) | msdyn_customerassetcategories | |
[Cespiti della Gestione cespiti](mapping-reference.md#125) | msdyn_customerassets | |
[Modelli del ciclo di vita unità funzionali della Gestione cespiti](mapping-reference.md#134) | msdyn_functionallocationlifecyclemodels | |
[Stati del ciclo di vita unità funzionali della Gestione cespiti](mapping-reference.md#135) | msdyn_functionallocationlifecyclestates | |
[Tipi di unità funzionali della Gestione cespiti](mapping-reference.md#137) | msdyn_functionallocationtypes | |
[Unità funzionali della Gestione cespiti](mapping-reference.md#136) | msdyn_functionallocations | |
[Produttori della Gestione cespiti](mapping-reference.md#153) | msdyn_manufacturers | |
[Modelli della Gestione cespiti](mapping-reference.md#154) | msdyn_models | |
[Garanzia della gestione cespiti](mapping-reference.md#209) | msdyn_warranties | |

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
