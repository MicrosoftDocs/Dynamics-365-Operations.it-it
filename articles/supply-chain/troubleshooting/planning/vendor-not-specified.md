---
title: Il fornitore non è specificato quando gli ordini pianificati vengono stabilizzati
description: Quando si tenta di stabilizzare gli ordini pianificati, viene visualizzato un messaggio di errore che indica che non è specificato alcun fornitore.
author: ankubik
ms.date: 06/10/2021
ms.topic: troubleshooting
ms.search.form: ReqTrans
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ankubik
ms.search.validFrom: 2021-06-10
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: cf41295045211f8a714194494028922d573c9e9e
ms.sourcegitcommit: 18ca2df785e9656fdd4e8c0734eca2b2624fda10
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/22/2021
ms.locfileid: "6294107"
---
# <a name="vendor-isnt-specified-when-planned-orders-are-firmed"></a>Il fornitore non è specificato quando gli ordini pianificati vengono stabilizzati

Codice errore: SYS23532

## <a name="symptoms"></a>Sintomi

Quando tenti di stabilizzare gli ordini pianificati viene visualizzato il seguente messaggio di errore:

> Il fornitore non è specificato

## <a name="resolution"></a>Risoluzione

Per specificare un fornitore effettua le operazioni indicate di seguito.

1. Apri l'ordine pianificato a cui manca un fornitore.
1. Nella scheda dettaglio **Fornitura pianificata** seleziona un fornitore nel campo **Fornitore**.
