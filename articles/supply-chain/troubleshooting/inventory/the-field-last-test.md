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
# <a name="the-last-tested-date-field-isnt-updated-when-multiple-quality-orders-are-created"></a><span data-ttu-id="6333c-103">Il campo Ultima data di test non viene aggiornato quando vengono creati più ordini di controllo qualità</span><span class="sxs-lookup"><span data-stu-id="6333c-103">The Last tested date field isn't updated when multiple quality orders are created</span></span>

<span data-ttu-id="6333c-104">Numero KB: 4612803</span><span class="sxs-lookup"><span data-stu-id="6333c-104">KB number: 4612803</span></span>

## <a name="symptoms"></a><span data-ttu-id="6333c-105">Sintomi</span><span class="sxs-lookup"><span data-stu-id="6333c-105">Symptoms</span></span>

<span data-ttu-id="6333c-106">Il campo **Ultima data di test** non viene aggiornato quando vengono creati più ordini di controllo qualità.</span><span class="sxs-lookup"><span data-stu-id="6333c-106">The **Last tested date** field isn't updated when multiple quality orders are created.</span></span>

## <a name="resolution"></a><span data-ttu-id="6333c-107">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="6333c-107">Resolution</span></span>

<span data-ttu-id="6333c-108">Il sistema si comporta come previsto.</span><span class="sxs-lookup"><span data-stu-id="6333c-108">The system is behaving as designed.</span></span> <span data-ttu-id="6333c-109">L'ultima data di test non è correlata agli ordini di controllo qualità.</span><span class="sxs-lookup"><span data-stu-id="6333c-109">The last tested date isn't related to quality orders.</span></span> <span data-ttu-id="6333c-110">Memorizza la data alla quale i prodotti finiti sono stati acquistati o prodotti per la prima volta.</span><span class="sxs-lookup"><span data-stu-id="6333c-110">It stores the date when the finished goods were first purchased or manufactured.</span></span> <span data-ttu-id="6333c-111">Questa data viene utilizzata per calcolare la data di durata a scaffale consigliata.</span><span class="sxs-lookup"><span data-stu-id="6333c-111">This date is used to calculate the shelf life advice date.</span></span>
