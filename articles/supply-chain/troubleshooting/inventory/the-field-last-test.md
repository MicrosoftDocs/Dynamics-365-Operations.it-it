---
title: Il campo Ultima data di test non viene aggiornato quando vengono creati più ordini di controllo qualità
description: Il campo Ultima data di test non viene aggiornato quando vengono creati più ordini di controllo qualità.
author: niwang
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: InventBatch
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 6f796bdaa88d32b1c58dd8a4bca19f0ce4f3943d
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026654"
---
# <a name="the-last-tested-date-field-isnt-updated-when-multiple-quality-orders-are-created"></a>Il campo Ultima data di test non viene aggiornato quando vengono creati più ordini di controllo qualità

Numero KB: 4612803

## <a name="symptoms"></a>Sintomi

Il campo **Ultima data di test** non viene aggiornato quando vengono creati più ordini di controllo qualità.

## <a name="resolution"></a>Risoluzione

Il sistema si comporta come previsto. L'ultima data di test non è correlata agli ordini di controllo qualità. Memorizza la data alla quale i prodotti finiti sono stati acquistati o prodotti per la prima volta. Questa data viene utilizzata per calcolare la data di durata a scaffale consigliata.
