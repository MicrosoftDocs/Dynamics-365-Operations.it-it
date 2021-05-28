---
title: La selezione tardiva non viene rispettata quando gli ordini di produzione vengono reimpostato tramite un processo batch
description: Quando utilizzi un processo batch ricorrente per reimpostare lo stato di un ordine di produzione, le selezioni tardive non vengono rispettate.
author: johanhoffmann
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: ProdTableListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: e53198f427f4060421a4f0078277682c43db1320
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026637"
---
# <a name="late-selection-isnt-respected-when-production-orders-are-reset-via-a-batch-job"></a>La selezione tardiva non viene rispettata quando gli ordini di produzione vengono reimpostato tramite un processo batch

Numero KB: 4614634

## <a name="symptoms"></a>Sintomi

Quando utilizzi un processo batch ricorrente per reimpostare lo stato di un ordine di produzione, le selezioni tardive non vengono rispettate.

## <a name="resolution"></a>Risoluzione

Il design attuale non supporta l'uso di selezioni tardive per il processo *Reimposta stato*.
