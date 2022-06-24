---
title: Conversioni valuta interaziendale
description: Questo articolo spiega le conversioni di valuta per le transazioni interaziendali
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
ms.openlocfilehash: 41bfafc0dcb3bd356931b67dc63b717c0d098116
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8851480"
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
