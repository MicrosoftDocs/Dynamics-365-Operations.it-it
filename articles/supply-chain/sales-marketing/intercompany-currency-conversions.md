---
title: Conversioni valuta interaziendale
description: Questo argomento spiega le conversioni di valuta per le transazioni interaziendali
author: Henrikan
ms.date: 09/01/2021
ms.topic: article
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: f0af05c324bb67744ba6650e3d7a4ba8b958040e
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2022
ms.locfileid: "8671900"
---
# <a name="intercompany-currency-conversions"></a>Conversioni valuta interaziendale

[!include [banner](../../includes/banner.md)]

Quando il codice valuta nell'ordine cliente originario è diverso da quello nell'ordine fornitore interaziendale, i campi seguenti vengono sottoposti a conversione valutaria se la sincronizzazione è abilitata:

- **Prezzo unitario**
- **Addebiti vendite** o **Spese su acquisti**
- **Sconto**
- **Sconto plurimo**

Questi campi vengono quindi sincronizzati con la riga dell'ordine cliente interaziendale.

Poiché, tuttavia, la valuta nell'ordine fornitore interaziendale viene sempre sincronizzata con quella nell'ordine cliente interaziendale, i seguenti campi vengono sincronizzati senza essere sottoposti a conversione valutaria:

- **Prezzo unitario**
- **Addebiti vendite** o **Spese su acquisti**
- **Sconto**
- **Percentuale sconto**
- **Sconto plurimo**
- **Percentuale sconto plurimo**

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
