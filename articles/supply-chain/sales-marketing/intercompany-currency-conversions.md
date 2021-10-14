---
title: Conversioni valuta interaziendale
description: Questo argomento spiega le conversioni di valuta per le transazioni interaziendali
author: GalynaFedorova
ms.date: 09/01/2021
ms.topic: article
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 540849003d532ef2f0905c18332d9cb82a04cf7c
ms.sourcegitcommit: fcfd85a508c0de52cfe11d1986892219e39ef406
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2021
ms.locfileid: "7548364"
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
