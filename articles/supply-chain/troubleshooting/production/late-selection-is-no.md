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
# <a name="late-selection-isnt-respected-when-production-orders-are-reset-via-a-batch-job"></a><span data-ttu-id="e83e2-103">La selezione tardiva non viene rispettata quando gli ordini di produzione vengono reimpostato tramite un processo batch</span><span class="sxs-lookup"><span data-stu-id="e83e2-103">Late selection isn't respected when production orders are reset via a batch job</span></span>

<span data-ttu-id="e83e2-104">Numero KB: 4614634</span><span class="sxs-lookup"><span data-stu-id="e83e2-104">KB number: 4614634</span></span>

## <a name="symptoms"></a><span data-ttu-id="e83e2-105">Sintomi</span><span class="sxs-lookup"><span data-stu-id="e83e2-105">Symptoms</span></span>

<span data-ttu-id="e83e2-106">Quando utilizzi un processo batch ricorrente per reimpostare lo stato di un ordine di produzione, le selezioni tardive non vengono rispettate.</span><span class="sxs-lookup"><span data-stu-id="e83e2-106">When you use a recurring batch job to reset the status of a production order, late selections aren't respected.</span></span>

## <a name="resolution"></a><span data-ttu-id="e83e2-107">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="e83e2-107">Resolution</span></span>

<span data-ttu-id="e83e2-108">Il design attuale non supporta l'uso di selezioni tardive per il processo *Reimposta stato*.</span><span class="sxs-lookup"><span data-stu-id="e83e2-108">The current design doesn't support the use of late selections for the *Reset status* process.</span></span>
