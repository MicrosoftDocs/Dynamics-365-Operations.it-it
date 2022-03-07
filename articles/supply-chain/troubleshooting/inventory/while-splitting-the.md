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
# <a name="when-a-catch-weight-quantity-is-split-minimum-quantity-is-used-instead-of-nominal-quantity"></a>Quando una quantità a peso variabile viene suddivisa, viene utilizzata la quantità minima anziché la quantità nominale

Numero KB: 4612073

## <a name="symptoms"></a>Sintomi

Quando una quantità a peso variabile viene suddivisa in batch, il campo **Qtà prelievo** utilizza la quantità minima impostata per l'articolo, non la quantità nominale.

## <a name="resolution"></a>Risoluzione

Il sistema si comporta come previsto. Il sistema utilizza l'impostazione della quantità minima di ogni articolo per il prelievo.
