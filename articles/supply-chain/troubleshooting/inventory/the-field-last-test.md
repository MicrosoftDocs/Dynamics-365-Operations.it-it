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
ms.openlocfilehash: 46523c55f4fd42b0985397752f0c62a3e1a55e177f2308e20b7064e339758269
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6742030"
---
# <a name="the-last-tested-date-field-isnt-updated-when-multiple-quality-orders-are-created"></a>Il campo Ultima data di test non viene aggiornato quando vengono creati più ordini di controllo qualità

Numero KB: 4612803

## <a name="symptoms"></a>Sintomi

Il campo **Ultima data di test** non viene aggiornato quando vengono creati più ordini di controllo qualità.

## <a name="resolution"></a>Risoluzione

Il sistema si comporta come previsto. L'ultima data di test non è correlata agli ordini di controllo qualità. Memorizza la data alla quale i prodotti finiti sono stati acquistati o prodotti per la prima volta. Questa data viene utilizzata per calcolare la data di durata a scaffale consigliata.
