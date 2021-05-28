---
title: Il cumulo degli sconti cliente non riesce quando vengono utilizzati gruppi di sconti articolo
description: Quando utilizzi accordi sugli sconti cliente in combinazione con gruppi di sconti articolo, gli sconti vengono calcolati, ma il cumulo non riesce.
author: sherry-zheng
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: PdsRebateTableListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 5222d5a52a34ecfa4a1eac96a2cb561f257f17ea
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026633"
---
# <a name="cumulation-of-customer-rebates-fails-when-item-rebate-groups-are-used"></a>Il cumulo degli sconti cliente non riesce quando vengono utilizzati gruppi di sconti articolo

Numero KB: 4611372

## <a name="symptoms"></a>Sintomi

Quando utilizzi accordi sugli sconti cliente (di tipo *importo*) in combinazione con gruppi di sconti articolo, gli sconti vengono calcolati, ma il cumulo non riesce.

## <a name="resolution"></a>Risoluzione

Il sistema si comporta come previsto. I gruppi di articoli raggruppano solo gli articoli che hanno la stessa condizione di soglia. La condizione di sconto (soglia) viene impostata in base all'importo di ciascun articolo e non all'importo cumulato per qualsiasi articolo nel gruppo di articoli.
