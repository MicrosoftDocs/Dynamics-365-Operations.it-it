---
title: La quantità di un ordine di quarantena avviato non viene aggiornata quando l'ordine viene diviso
description: Quando crei un ordine di quarantena e provi a dividerlo, la quantità dell'ordine non viene aggiornata alla quantità rimanente divisa.
author: niwang
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: InventQuarantineOrder
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: shawan
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: a8af535257ce217629d5ba92e624623c3ea39345
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026656"
---
# <a name="quantity-on-a-started-quarantine-order-isnt-updated-when-the-order-is-split"></a><span data-ttu-id="59385-103">La quantità di un ordine di quarantena avviato non viene aggiornata quando l'ordine viene diviso</span><span class="sxs-lookup"><span data-stu-id="59385-103">Quantity on a started quarantine order isn't updated when the order is split</span></span>

<span data-ttu-id="59385-104">Numero KB: 4613113</span><span class="sxs-lookup"><span data-stu-id="59385-104">KB number: 4613113</span></span>

## <a name="symptoms"></a><span data-ttu-id="59385-105">Sintomi</span><span class="sxs-lookup"><span data-stu-id="59385-105">Symptoms</span></span>

<span data-ttu-id="59385-106">Quando crei un ordine di quarantena e provi a dividerlo, la quantità dell'ordine non viene aggiornata alla quantità rimanente dopo la divisione.</span><span class="sxs-lookup"><span data-stu-id="59385-106">When you create a quarantine order and try to split it, the order quantity isn't updated to the remaining quantity after the split.</span></span>

## <a name="resolution"></a><span data-ttu-id="59385-107">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="59385-107">Resolution</span></span>

<span data-ttu-id="59385-108">Il sistema non modifica la quantità originale di un ordine di quarantena per garantire che sia possibile tenere traccia della quantità originale creata per tale ordine di quarantena.</span><span class="sxs-lookup"><span data-stu-id="59385-108">The system doesn't change the original quantity from a quarantine order to ensure that you can track the original quantity that was created for that quarantine order.</span></span> <span data-ttu-id="59385-109">Tuttavia, il sistema tiene traccia della quantità divisa di un ordine di quarantena.</span><span class="sxs-lookup"><span data-stu-id="59385-109">However, the system does track the quantity that is split from a quarantine order.</span></span> <span data-ttu-id="59385-110">Per eseguire questo rilevamento, il sistema utilizza un campo di database denominato `QuantityThatHasSplitIntoOtherQuarantineOrders`.</span><span class="sxs-lookup"><span data-stu-id="59385-110">To do this tracking, it uses a database field that is named `QuantityThatHasSplitIntoOtherQuarantineOrders`.</span></span> <span data-ttu-id="59385-111">Tuttavia, questo campo non è visibile nell'interfaccia utente (UI).</span><span class="sxs-lookup"><span data-stu-id="59385-111">However, this field isn't visible in the user interface (UI).</span></span>
