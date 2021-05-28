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
# <a name="missing-field-settings-when-item-model-groups-are-copied-to-another-legal-entity"></a>Impostazioni di campi mancanti quando i gruppi di modelli di articoli vengono copiati in un'altra persona giuridica

Numero KB: 4612800

## <a name="symptoms"></a>Sintomi

Quando copi gruppi di modelli di articoli in un'altra persona giuridica (società) utilizzando l'entità *Criteri di inventario del gruppo di modelli di articoli*, alcune impostazioni di campi (ad esempio, il modello di inventario e la descrizione) risultano mancanti nel nuovo gruppo di modelli nella persona giuridica di destinazione.

## <a name="resolution"></a>Risoluzione

Per creare una copia completa di un gruppo di modelli di articoli in un'altra persona giuridica, devi anche selezionare i criteri di inventario del gruppo di modelli di articoli (`InventInventoryPolicyEntity`) e i criteri dei presupposti per flussi di costo (`InventCostFlowAssumptionPolicyEntity`) associati al gruppo di modelli di articoli.
