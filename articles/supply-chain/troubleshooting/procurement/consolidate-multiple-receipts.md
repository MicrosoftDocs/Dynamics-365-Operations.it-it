---
title: Non è possibile consolidare più entrate prodotto in un unico ordine fornitore
description: Non è possibile consolidare più entrate prodotti in un unico ordine fornitore se le diverse righe di entrata prodotti hanno date contabili diverse.
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
ms.openlocfilehash: 485306279281ceb55a140526f4216af35574af42
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476737"
---
# <a name="you-cant-consolidate-multiple-product-receipts-into-a-single-purchase-order"></a>Non è possibile consolidare più entrate prodotto in un unico ordine fornitore

## <a name="symptoms"></a>Sintomi

Non è possibile consolidare più entrate prodotti in un unico ordine fornitore se le diverse righe di entrata prodotti hanno date contabili diverse.

## <a name="resolution"></a>Risoluzione

Nelle versioni precedenti di Dynamics 365 Supply Chain Management, il consolidamento era consentito in questa situazione. Tuttavia, la procedura è soggetta a errori. La data contabile nelle righe ordine fornitore create non deve essere diversa dalla data contabile nelle righe entrata prodotti da cui sono state create tali righe ordine fornitore. (La data contabile nelle righe dell'ordine fornitore corrisponde alla data contabile nell'intestazione dell'ordine fornitore). Pertanto, il consolidamento di più entrate prodotti in un unico ordine fornitore non è più consentito.

La data contabile viene utilizzata, ad esempio, per le prenotazioni di budget e gli impegni di spesa. Pertanto, deve essere conservata durante il passaggio dall'entrata del prodotto all'ordine fornitore.
