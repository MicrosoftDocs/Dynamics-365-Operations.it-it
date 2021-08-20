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
ms.openlocfilehash: 424ad46281612f6a3e8cb4c90478a39f757d5416c3ce1d77ed6ff6dba7b20dcb
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6723457"
---
# <a name="when-a-catch-weight-quantity-is-split-minimum-quantity-is-used-instead-of-nominal-quantity"></a>Quando una quantità a peso variabile viene suddivisa, viene utilizzata la quantità minima anziché la quantità nominale

Numero KB: 4612073

## <a name="symptoms"></a>Sintomi

Quando una quantità a peso variabile viene suddivisa in batch, il campo **Qtà prelievo** utilizza la quantità minima impostata per l'articolo, non la quantità nominale.

## <a name="resolution"></a>Risoluzione

Il sistema si comporta come previsto. Il sistema utilizza l'impostazione della quantità minima di ogni articolo per il prelievo.
