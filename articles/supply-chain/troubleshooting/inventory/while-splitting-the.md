---
title: Quando una quantità a peso variabile viene suddivisa, viene utilizzata la quantità minima anziché la quantità nominale
description: Quando una quantità a peso variabile viene suddivisa in batch, il campo Qtà prelievo utilizza la quantità minima impostata per l'articolo, non la quantità nominale.
author: niwang
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: WMSPickingRegistration
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 185365ced5c4516d8fcdbdca88794d0078615888
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026652"
---
# <a name="when-a-catch-weight-quantity-is-split-minimum-quantity-is-used-instead-of-nominal-quantity"></a><span data-ttu-id="aac84-103">Quando una quantità a peso variabile viene suddivisa, viene utilizzata la quantità minima anziché la quantità nominale</span><span class="sxs-lookup"><span data-stu-id="aac84-103">When a catch-weight quantity is split, minimum quantity is used instead of nominal quantity</span></span>

<span data-ttu-id="aac84-104">Numero KB: 4612073</span><span class="sxs-lookup"><span data-stu-id="aac84-104">KB number: 4612073</span></span>

## <a name="symptoms"></a><span data-ttu-id="aac84-105">Sintomi</span><span class="sxs-lookup"><span data-stu-id="aac84-105">Symptoms</span></span>

<span data-ttu-id="aac84-106">Quando una quantità a peso variabile viene suddivisa in batch, il campo **Qtà prelievo** utilizza la quantità minima impostata per l'articolo, non la quantità nominale.</span><span class="sxs-lookup"><span data-stu-id="aac84-106">When a catch-weight quantity is being split into batches, the **Pick qty** field uses the minimum quantity that is set for the item, not the nominal quantity.</span></span>

## <a name="resolution"></a><span data-ttu-id="aac84-107">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="aac84-107">Resolution</span></span>

<span data-ttu-id="aac84-108">Il sistema si comporta come previsto.</span><span class="sxs-lookup"><span data-stu-id="aac84-108">The system is behaving as designed.</span></span> <span data-ttu-id="aac84-109">Il sistema utilizza l'impostazione della quantità minima di ogni articolo per il prelievo.</span><span class="sxs-lookup"><span data-stu-id="aac84-109">The system uses each item's minimum quantity setup for picking.</span></span>
