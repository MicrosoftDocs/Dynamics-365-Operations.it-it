---
title: Problemi di conversione di valuta accordi commerciali
description: I prezzi degli accordi commerciali non vengono ricalcolati in base alla valuta quando la valuta è diversa in un ordine fornitore
author: kamaybac
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: PurchTable, PurchTablePart, PurchRFQTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 1b6dc36c5f5ee6b611eebd81f378399ce1748c63
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476732"
---
# <a name="trade-agreement-currency-conversion-issues"></a>Problemi di conversione di valuta accordi commerciali

## <a name="symptoms"></a>Sintomi

I prezzi degli accordi commerciali non vengono ricalcolati in base alla valuta quando la valuta è diversa in un ordine fornitore.

## <a name="resolution"></a>Risoluzione

La funzionalità *Valuta generica* consente di definire prezzi e sconti in una sola valuta. È quindi possibile convertire in altre valute come richiesto. Inoltre, al termine della conversione, la funzionalità può applicare automaticamente l'arrotondamento psicologico.
