---
title: Gli ordini stabilizzati derivati direttamente vengono elaborati da un flusso di lavoro in revisione
description: Gli ordini stabilizzati derivati direttamente vengono elaborati da un flusso di lavoro il cui stato è In revisione.
author: ChristianRytt
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: ReqTransPo
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ilebedev
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: d54985707d82df2b947a7cb615fc25f90aa31702
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026651"
---
# <a name="directly-derived-firmed-orders-are-processed-by-an-in-review-workflow"></a><span data-ttu-id="e1722-103">Gli ordini stabilizzati derivati direttamente vengono elaborati da un flusso di lavoro in revisione</span><span class="sxs-lookup"><span data-stu-id="e1722-103">Directly derived firmed orders are processed by an in-review workflow</span></span>

<span data-ttu-id="e1722-104">Numero KB: 4612450</span><span class="sxs-lookup"><span data-stu-id="e1722-104">KB number: 4612450</span></span>

## <a name="symptoms"></a><span data-ttu-id="e1722-105">Sintomi</span><span class="sxs-lookup"><span data-stu-id="e1722-105">Symptoms</span></span>

<span data-ttu-id="e1722-106">Gli ordini stabilizzati derivati direttamente vengono elaborati da un flusso di lavoro il cui stato è *In revisione*.</span><span class="sxs-lookup"><span data-stu-id="e1722-106">Directly derived firmed orders are processed by a workflow that has a status of *In-review*.</span></span>

## <a name="resolution"></a><span data-ttu-id="e1722-107">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="e1722-107">Resolution</span></span>

<span data-ttu-id="e1722-108">Quando il rilevamento delle modifiche è attivato, lo stato *In revisione* viene assegnato agli ordini stabilizzati derivati (ordini fornitore in conto lavoro).</span><span class="sxs-lookup"><span data-stu-id="e1722-108">When change tracking is enabled, a status of *In-review* is assigned to firmed derived orders (subcontract purchase orders).</span></span> <span data-ttu-id="e1722-109">Pertanto, se un ordine fornitore viene derivato (un ordine fornitore in conto lavoro), viene inviato solo a un flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="e1722-109">Therefore, if a purchase order is derived (a subcontract purchase order), it's only submitted to a workflow.</span></span> <span data-ttu-id="e1722-110">Se un ordine fornitore è un ordine fornitore pianificato stabilizzato, viene automaticamente approvato per garantire che il motore di pianificazione non crei nuovi ordini pianificati mentre lo stato dell'ordine fornitore è ancora *Bozza*.</span><span class="sxs-lookup"><span data-stu-id="e1722-110">If a purchase order is a firmed planned purchase order, it's automatically approved to ensure that the planning engine doesn't create new planned orders while the purchase order is still in *Draft* status.</span></span>
