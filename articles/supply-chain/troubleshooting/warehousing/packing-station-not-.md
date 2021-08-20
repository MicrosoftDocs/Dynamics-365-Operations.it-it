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
ms.openlocfilehash: 18c8d2d392b7950ee2d5fc388fc3f365b52a6795c908f9ed8cac12dc7b481c60
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6760348"
---
# <a name="packing-station-doesnt-show-product-notes"></a>La stazione di imballaggio non mostra le note sul prodotto

Numero KB: 4614615

## <a name="symptoms"></a>Sintomi

Le note di imballaggio non vengono visualizzate nel modulo di imballaggio quando le istruzioni di imballaggio sono aggiunte come allegato a una rappresentazione generale prodotto o a una variante prodotto.

## <a name="resolution"></a>Risoluzione

Il sistema si comporta come previsto.

L'attuale logica per mostrare le note di imballaggio nel modulo di imballaggio richiede che le note siano associate alle spedizioni.
