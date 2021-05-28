---
title: La stazione di imballaggio non mostra le note sul prodotto
description: La stazione di imballaggio non mostra le note sul prodotto.
author: perlynne
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: WHSPack
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: bf64de3e67c1000dad9d5b37fffe622ae0e300b3
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026640"
---
# <a name="packing-station-doesnt-show-product-notes"></a>La stazione di imballaggio non mostra le note sul prodotto

Numero KB: 4614615

## <a name="symptoms"></a>Sintomi

Le note di imballaggio non vengono visualizzate nel modulo di imballaggio quando le istruzioni di imballaggio sono aggiunte come allegato a una rappresentazione generale prodotto o a una variante prodotto.

## <a name="resolution"></a>Risoluzione

Il sistema si comporta come previsto.

L'attuale logica per mostrare le note di imballaggio nel modulo di imballaggio richiede che le note siano associate alle spedizioni.
