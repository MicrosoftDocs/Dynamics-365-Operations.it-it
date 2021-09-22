---
title: Un gruppo fiscale e uno sconto di cassa predefiniti non vengono compilati dal conto fattura
description: Un gruppo fiscale predefinito e uno sconto di cassa predefinito non vengono compilati dal conto fattura
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
ms.openlocfilehash: bb984eb17209dc92e336df5ad475bb0f70c6e35c
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476761"
---
# <a name="default-tax-group-and-cash-discount-arent-filled-in-from-the-invoice-account"></a>Un gruppo fiscale e uno sconto di cassa predefiniti non vengono compilati dal conto fattura

## <a name="symptoms"></a>Sintomi

Se utilizzi un conto fattura diverso dal conto cliente, un gruppo fiscale predefinito e uno sconto di cassa predefinito non vengono compilati dal conto fattura quando viene creato un ordine fornitore.

## <a name="resolution"></a>Risoluzione

Questo comportamento è predefinito. I valori predefiniti per il gruppo IVA, sconti di cassa e altre informazioni sui prezzi si basano sul conto cliente, non sul conto fattura.
