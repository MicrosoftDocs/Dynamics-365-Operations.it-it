---
title: Includi valore fisico
description: Si utilizza la casella di controllo Includi valore fisico nella scheda dettaglio Modello inventariale della pagina Gruppi di modelli di articolo per specificare se nel calcolo del prezzo di costo medio corrente dell'articolo vengono considerate le transazioni aggiornate fisicamente.
author: JennySong-SH
ms.date: 10/31/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventModelGroup
audience: Application User
ms.reviewer: kamaybac
ms.custom: 79033
ms.assetid: 1928c145-bf82-436d-87ca-e7a173e31923
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yanansong
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6fb7a2a401bd7900555646c3ff0e1be9bf4a50d3
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2022
ms.locfileid: "8672404"
---
# <a name="include-physical-value"></a>Includi valore fisico

[!include [banner](../includes/banner.md)]

Si utilizza la casella di controllo Includi valore fisico nella scheda dettaglio Modello inventariale della pagina Gruppi di modelli di articolo per specificare se nel calcolo del prezzo di costo medio corrente dell'articolo vengono considerate le transazioni aggiornate fisicamente.

La casella di controllo **Includi valore fisico** ha i seguenti valori.

| Valore    | Risultato                                                                                                                          |
|----------|---------------------------------------------------------------------------------------------------------------------------------|
| Selezionata | Per calcolare il prezzo di costo medio corrente verranno utilizzate sia le transazioni aggiornate fisicamente sia le transazioni aggiornate finanziariamente. |
| Deselezionata  | Per calcolare il prezzo di costo medio corrente verranno utilizzate solo le transazioni aggiornate finanziariamente.                                     |

La casella di controllo ha effetti leggermente diversi a seconda del modello inventariale in uso.

-   Se si seleziona la casella di controllo **Includi valore fisico** quando si utilizza il modello inventariale FIFO (First in, first out), LIFO (Last in, first out) o Data LIFO, con la chiusura dell'inventario verranno apportate rettifiche anche alle transazioni aggiornate fisicamente.
-   Se non si seleziona la casella di controllo **Includi valore fisico** con questi modelli inventariali, con la chiusura dell'inventario verranno eseguite compensazioni solo per le transazioni aggiornate finanziariamente.
-   Se si utilizzano i modelli inventariali media ponderata o data media ponderata, la chiusura inventario determinerà la compensazione solo delle transazioni aggiornate finanziariamente, indipendentemente dalla selezione della casella di controllo **Includi valore fisico**.

**Esempio 1** È stata selezionata la casella di controllo **Includi valore fisico** e sono stati ricevuti i seguenti ordini fornitore:

-   È stato fatturato un ordine acquisto per una quantità 2 a un prezzo di costo di 10,00 EUR aggiornato nel documento di trasporto.
-   Un ordine acquisto per una quantità 3 a un prezzo di costo di 12,00 EUR aggiornato nella fattura.

In questo caso il prezzo di costo medio corrente sarà di 11,20 EUR = (2x10+3x12)/(2+3), poiché per calcolare il prezzo di costo verranno utilizzate sia le transazioni aggiornate fisicamente sia le transazioni aggiornate finanziariamente. 

**Esempio 2** Non è stata selezionata la casella di controllo **Includi valore fisico** e il prezzo di costo nell'impostazione dell'articolo è di 10,00 EUR. 

-   È stato ricevuto un ordine acquisto per una quantità 20 a un prezzo di costo di 12,00 EUR aggiornato nel documento di trasporto.

Quando viene registrato un ordine cliente, viene registrato automaticamente un importo costi di 10,00 EUR, poiché il prezzo di costo medio corrente non includerà transazioni registrate fisicamente. 

> [!NOTE]
> A fini di confronto, se si seleziona la casella di controllo **Includi valore fisico** per questo articolo, quando si registra un ordine cliente, l'importo costi registrato sarà 12,00 EUR.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]