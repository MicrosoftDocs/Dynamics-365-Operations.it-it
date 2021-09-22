---
title: Gli ordini fornitore non riflettono le impostazioni della lingua della persona giuridica
description: Il nome del prodotto in un ordine fornitore viene visualizzato nella lingua del sistema anziché nella lingua impostata per la persona giuridica in cui è stato creato l'ordine fornitore.
author: kamaybac
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: PurchTable, PurchTablePart
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 4deec493b5480dc570ac82876243bc31a2ae87aa
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476757"
---
# <a name="purchase-orders-dont-reflect-the-language-settings-of-the-legal-entity"></a>Gli ordini fornitore non riflettono le impostazioni della lingua della persona giuridica


## <a name="symptoms"></a>Sintomi

Il nome del prodotto in un ordine fornitore viene visualizzato nella lingua del sistema anziché nella lingua impostata per la persona giuridica in cui è stato creato l'ordine fornitore.

## <a name="reproduce-the-issue"></a>Riprodurre il problema

La seguente procedura mostra un modo per riprodurre il problema.

1. Imposta la lingua del sistema su *EN-US* (Inglese americano).
1. Assicurati che ci sia un prodotto in cui le lingue *EN-US* e *DE* (tedesco) vengono mantenute per le traduzioni del nome del prodotto.
1. Cambia la lingua di una persona giuridica in *DE*.
1. Nella persona giuridica dove *DE* è impostata come lingua, crea un ordine fornitore che includa il prodotto.
1. Si noti che il nome del prodotto è ancora visualizzato in inglese americano (la lingua del sistema).

## <a name="resolution"></a>Risoluzione

Questo comportamento è predefinito. Negli ordini fornitore, il prodotto viene sempre mostrato nella lingua del sistema. La lingua dell'ordine fornitore viene utilizzata quando viene creato un giornale di registrazione conferme.
