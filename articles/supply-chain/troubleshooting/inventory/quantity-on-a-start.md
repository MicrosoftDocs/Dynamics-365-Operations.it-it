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
# <a name="quantity-on-a-started-quarantine-order-isnt-updated-when-the-order-is-split"></a>La quantità di un ordine di quarantena avviato non viene aggiornata quando l'ordine viene diviso

Numero KB: 4613113

## <a name="symptoms"></a>Sintomi

Quando crei un ordine di quarantena e provi a dividerlo, la quantità dell'ordine non viene aggiornata alla quantità rimanente dopo la divisione.

## <a name="resolution"></a>Risoluzione

Il sistema non modifica la quantità originale di un ordine di quarantena per garantire che sia possibile tenere traccia della quantità originale creata per tale ordine di quarantena. Tuttavia, il sistema tiene traccia della quantità divisa di un ordine di quarantena. Per eseguire questo rilevamento, il sistema utilizza un campo di database denominato `QuantityThatHasSplitIntoOtherQuarantineOrders`. Tuttavia, questo campo non è visibile nell'interfaccia utente (UI).
