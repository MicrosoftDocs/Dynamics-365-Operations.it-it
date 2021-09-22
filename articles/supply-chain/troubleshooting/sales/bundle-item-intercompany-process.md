---
title: Articolo in aggregazione non supportato in un processo interaziendale
description: L'articolo in aggregazione non è disponibile per l'acquisto. L'ordine cliente acquista solo i componenti dell'articolo in aggregazione, non l'articolo in aggregazione stesso.
author: SmithaNataraj
ms.date: 06/24/2021
ms.topic: troubleshooting
ms.search.form: SalesTable, SalesTableListPage, SalesTableListPage_SalesCancelOrder
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 21adc7d071837b762157364f6f8ed370c69c7fd3
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476770"
---
# <a name="a-bundle-item-isnt-supported-in-an-intercompany-process"></a>Un articolo in aggregazione non è supportato in un processo interaziendale

## <a name="symptoms"></a>Sintomi

L'articolo in aggregazione non è disponibile per l'ordine fornitore perché, se esamini le righe dell'ordine cliente per l'articolo aggregato, noterai che la quantità è *0* (zero) e lo stato è *Annullato*.

## <a name="resolution"></a>Risoluzione

Questo comportamento è predefinito. L'ordine cliente acquista solo i componenti dell'articolo in aggregazione. Non acquista l'articolo in aggregazione stesso. Se devi acquistare un'aggregazione, valuta se devi contrassegnarlo come articolo dell'aggregazione, perché questa funzionalità è progettata per scenari di riconoscimento dei ricavi. Per ulteriori informazioni su articoli e aggregazioni, vedi [Aggregazioni](/dynamics365/finance/accounts-receivable/revenue-recognition-setup).
