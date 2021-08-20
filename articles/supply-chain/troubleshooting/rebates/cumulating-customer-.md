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
ms.openlocfilehash: fc3381dab77cf80c0fd65f3bc27c11b814e72368631bd0e2145aac0be4f4fba4
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6760372"
---
# <a name="cumulation-of-customer-rebates-fails-when-item-rebate-groups-are-used"></a>Il cumulo degli sconti cliente non riesce quando vengono utilizzati gruppi di sconti articolo

Numero KB: 4611372

## <a name="symptoms"></a>Sintomi

Quando utilizzi accordi sugli sconti cliente (di tipo *importo*) in combinazione con gruppi di sconti articolo, gli sconti vengono calcolati, ma il cumulo non riesce.

## <a name="resolution"></a>Risoluzione

Il sistema si comporta come previsto. I gruppi di articoli raggruppano solo gli articoli che hanno la stessa condizione di soglia. La condizione di sconto (soglia) viene impostata in base all'importo di ciascun articolo e non all'importo cumulato per qualsiasi articolo nel gruppo di articoli.
