---
title: Uno sconto fornitore non viene accumulato in base alle fatture
description: Uno sconto fornitore non viene accumulato in base alle fatture
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
ms.openlocfilehash: 9d4596a7351969bf181982a24ea1dcc6f5732831
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476811"
---
# <a name="a-vendor-rebate-isnt-cumulated-based-on-invoices"></a>Uno sconto fornitore non viene accumulato in base alle fatture

## <a name="symptoms"></a>Sintomi

Se le fatture registrate hanno date di scadenza diverse, tali fatture non vengono riflesse negli sconti fornitore generati da esse.

## <a name="resolution"></a>Risoluzione

La data di scadenza non viene considerata quando viene calcolato lo sconto fornitore. Valuta la possibilità di personalizzare il sistema in modo che la data di scadenza e la relazione con la fattura siano più evidenti rispetto all'effettivo sconto fornitore.
