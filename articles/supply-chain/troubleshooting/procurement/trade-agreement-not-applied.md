---
title: Le condizioni dell'accordo commerciale non vengono applicate alle righe ordine importate
description: I prezzi e gli sconti degli accordi commerciali non vengono applicati alle righe dell'ordine fornitore o cliente importate tramite la gestione dei dati
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
ms.openlocfilehash: fef38819efaff2f2a927cf09fc7f469490149574
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476796"
---
# <a name="trade-agreement-conditions-arent-applied-to-imported-order-lines"></a>Le condizioni dell'accordo commerciale non vengono applicate alle righe ordine importate

## <a name="symptoms"></a>Sintomi

Gli accordi commerciali applicabili alle righe dell'ordine fornitore o cliente non vengono applicate alle righe importate tramite la gestione dei dati. Tuttavia, gli stessi accordi commerciali vengono applicati alle righe dell'ordine fornitore o cliente create manualmente.

## <a name="cause"></a>Causa

Se le righe dell'ordine fornitore importate tramite la gestione dei dati includono già informazioni sui prezzi, l'accordo commerciale non verrà rivalutato per tali righe. Ad esempio, se **Percentuale sconto riga** o uno qualsiasi dei valori di prezzo e sconto è impostata per una riga, gli accordi commerciali non verranno cercati per quella riga.

## <a name="workaround"></a>Soluzione alternativa

Questo comportamento è previsto ed è simile sia per gli ordini cliente che per gli ordini fornitore.

Come soluzione alternativa, importa le righe dell'ordine fornitore senza impostare alcuna informazione sul prezzo. Gli accordi commerciali verranno quindi applicati e le righe dell'ordine fornitore verranno aggiornate in base agli accordi commerciali definiti.
