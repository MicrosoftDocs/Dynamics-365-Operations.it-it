---
title: I prezzi unitari sugli ordini fornitore non vengono calcolati in base alla conversione delle unità
description: I prezzi unitari sugli ordini fornitore non vengono calcolati in base alla conversione delle unità
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
ms.openlocfilehash: 4695f4661c3abb8ab38e3ca74b513e8529e37d20
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476763"
---
# <a name="unit-prices-on-purchase-orders-arent-calculated-based-on-the-unit-conversion"></a>I prezzi unitari sugli ordini fornitore non vengono calcolati in base alla conversione delle unità

## <a name="symptoms"></a>Sintomi

Quando un'unità viene modificata in un ordine fornitore, i prezzi degli accordi commerciali non vengono ricalcolati in base alle definizioni di conversione delle unità.

## <a name="cause"></a>Causa

I prezzi sono sempre ottenuti da accordi commerciali (o altre impostazioni di prezzo nel sistema, come accordi di vendita o prezzi degli articoli) e sono impostati per un'unità.

Se l'unità viene modificata in una riga ordine, il sistema cerca un prezzo per la nuova unità e lo applica. Se non viene trovato alcun prezzo per l'unità, il sistema non applica un prezzo. La conversione di unità non può essere utilizzata per ricalcolare il prezzo in un'altra unità. In teoria, il prezzo per una scatola da dieci potrebbe non essere uguale a dieci volte il prezzo di una scatola.

## <a name="workaround"></a>Soluzione alternativa

Un modo per risolvere questo problema è assicurarsi che siano presenti accordi commerciali per le unità che si prevede verranno utilizzate nelle righe ordine per l'articolo.
