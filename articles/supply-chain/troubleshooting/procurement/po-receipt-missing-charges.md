---
title: Una ricevuta dell'ordine fornitore non include tutti gli addebiti
description: Una ricevuta dell'ordine fornitore non include tutti gli addebiti
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
ms.openlocfilehash: bb567e00ef52269db0dc866148a37c73f0a9827c
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476726"
---
# <a name="a-purchase-order-receipt-doesnt-include-all-charges"></a>Una ricevuta dell'ordine fornitore non include tutti gli addebiti

## <a name="symptoms"></a>Sintomi

Quando si riceve un ordine fornitore, non tutti gli addebiti sono inclusi nella ricevuta.

### <a name="reproduce-the-issue"></a>Riprodurre il problema

La seguente procedura mostra un modo per riprodurre il problema.

1. Nella pagina **Parametri di approvvigionamento**, nella scheda **Consegna**, assicurati che l'opzione **Genera spese sull'entrata prodotti** sia impostata su *Sì*.
1. Crea un ordine fornitore che includa le spese.
1. Conferma l'ordine fornitore.
1. Ricevi l'ordine fornitore.
1. Guarda il totale dell'entrata e confrontalo con il totale previsto.
1. Si noti che non tutte le spese sono incluse nella ricevuta dell'ordine fornitore.

## <a name="resolution"></a>Risoluzione

La risoluzione dipende dal modo in cui sono state configurate le spese varie. Per informazioni su come configurare le spese varie per soddisfare le tue esigenze, consulta il seguente post del blog: [Pubblicare spese varie al momento dell'entrata del prodotto](https://cloudblogs.microsoft.com/dynamics365/no-audience/2014/11/11/post-misc-charges-at-time-of-product-receipt/).
