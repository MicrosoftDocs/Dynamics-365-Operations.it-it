---
title: Impostazioni di campi mancanti quando i gruppi di modelli di articoli vengono copiati in un'altra persona giuridica
description: Alcune impostazioni di campi risultano mancanti quando i gruppi di modelli di articoli vengono copiati in un'altra persona giuridica.
author: niwang
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: InventModelGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 6f6fdfef0bc377418ed8a9c8830e74526a0b95eb
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026638"
---
# <a name="missing-field-settings-when-item-model-groups-are-copied-to-another-legal-entity"></a><span data-ttu-id="023f9-103">Impostazioni di campi mancanti quando i gruppi di modelli di articoli vengono copiati in un'altra persona giuridica</span><span class="sxs-lookup"><span data-stu-id="023f9-103">Missing field settings when item model groups are copied to another legal entity</span></span>

<span data-ttu-id="023f9-104">Numero KB: 4612800</span><span class="sxs-lookup"><span data-stu-id="023f9-104">KB number: 4612800</span></span>

## <a name="symptoms"></a><span data-ttu-id="023f9-105">Sintomi</span><span class="sxs-lookup"><span data-stu-id="023f9-105">Symptoms</span></span>

<span data-ttu-id="023f9-106">Quando copi gruppi di modelli di articoli in un'altra persona giuridica (società) utilizzando l'entità *Criteri di inventario del gruppo di modelli di articoli*, alcune impostazioni di campi (ad esempio, il modello di inventario e la descrizione) risultano mancanti nel nuovo gruppo di modelli nella persona giuridica di destinazione.</span><span class="sxs-lookup"><span data-stu-id="023f9-106">When you copy item model groups to another legal entity (company) by using the *Item model group inventory policies* entity, some field settings (for example, the inventory model and description) are missing in the new model group in the destination legal entity.</span></span>

## <a name="resolution"></a><span data-ttu-id="023f9-107">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="023f9-107">Resolution</span></span>

<span data-ttu-id="023f9-108">Per creare una copia completa di un gruppo di modelli di articoli in un'altra persona giuridica, devi anche selezionare i criteri di inventario del gruppo di modelli di articoli (`InventInventoryPolicyEntity`) e i criteri dei presupposti per flussi di costo (`InventCostFlowAssumptionPolicyEntity`) associati al gruppo di modelli di articoli.</span><span class="sxs-lookup"><span data-stu-id="023f9-108">To create a complete copy of an item model group to another legal entity, you must also select both the item model group inventory policies (`InventInventoryPolicyEntity`) and the cost flow assumption policies (`InventCostFlowAssumptionPolicyEntity`) that are associated with the item model group.</span></span>
