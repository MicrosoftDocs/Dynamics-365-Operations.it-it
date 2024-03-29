---
title: Valori di un oggetto di magazzino
description: Questo articolo fornisce informazioni sul modo in cui vengono calcolati i valori di un oggetto di magazzino.
author: JennySong-SH
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventCostOnhandItem
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19111
ms.assetid: 56a7c8ba-bf4a-4b1d-918d-56bb96926c4f
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yanansong
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4a5dd487b9213f8f1289412a6a7b8112e6b57df6
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2022
ms.locfileid: "8670386"
---
# <a name="inventory-object-values"></a>Valori di un oggetto di magazzino

[!include [banner](../includes/banner.md)]

Questo articolo fornisce informazioni sul modo in cui vengono calcolati i valori di un oggetto di magazzino. 

Una nuova funzione denominata **quantità fisica** consente di visualizzare i valori di un oggetto specifico di magazzino. 

Un oggetto di costo rappresenta il livello di entità in cui la contabilità inventario viene eseguita. Per ulteriori informazioni sugli oggetti di costo, vedere [Oggetti di costo](cost-object.md). 

Per visualizzare i valori di un oggetto di magazzino specifico, fare clic su **Quantità fisica** nella pagina **Oggetto di costo**. Ecco viene calcolato il valore di un oggetto di magazzino: 

object.Value magazzino = Cost unitario object.Average × object.Quantity magazzino 

Il seguente esempio mostra come vengono calcolati i valori di un oggetto di magazzino e di un oggetto di costo. Due eventi di entrata prodotti vengono registrati nell'articolo A:

-   Entrata prodotti 1: Quantità = 100 pz, Importo = $ 1.000,00, Sito = 1, Magazzino =11 Batch n. = B1
-   Entrata prodotti 2: Quantità = 50. pz, Importo = $800,00, Sito = 1, Magazzino =11 Batch n. = B2

Nella seguente tabella viene visualizzato il risultato del calcolo per un oggetto di costo. È possibile visualizzare il risultato nella pagina **Oggetto di costo**.

<table>
<colgroup>
<col width="14%" />
<col width="14%" />
<col width="14%" />
<col width="14%" />
<col width="14%" />
<col width="14%" />
<col width="14%" />
</colgroup>
<thead>
<tr class="header">
<th>Tipo oggetto</th>
<th>Numero articolo</th>
<th>Sito</th>
<th>Quantità</th>
<th>Unità di magazzino</th>
<th>Valore</th>
<th>Costo unitario medio</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Oggetto di costo</td>
<td>A</td>
<td>1</td>
<td>150</td>
<td>Pzi</td>
<td><p>$1800,00</p></td>
<td><p>$12,00</p></td>
</tr>
</tbody>
</table>

Nella seguente tabella viene visualizzato il risultato del calcolo per un oggetto di magazzino. È possibile visualizzare il risultato facendo clic su **Quantità fisica** nella pagina **Oggetto di costo**.

<table>
<colgroup>
<col width="11%" />
<col width="11%" />
<col width="11%" />
<col width="11%" />
<col width="11%" />
<col width="11%" />
<col width="11%" />
<col width="11%" />
<col width="11%" />
</colgroup>
<thead>
<tr class="header">
<th>Tipo oggetto</th>
<th>Numero articolo</th>
<th>Sito</th>
<th>Magazzino</th>
<th>Batch n.</th>
<th>Quantità</th>
<th>Unità di magazzino</th>
<th>Valore</th>
<th>Costo unitario medio</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Oggetto di magazzino</td>
<td>A</td>
<td>1</td>
<td>11</td>
<td>B1</td>
<td>100</td>
<td>Pzi</td>
<td><p>$1200,00</p></td>
<td><p>$12,00</p></td>
</tr>
<tr class="even">
<td>Oggetto di magazzino</td>
<td>A</td>
<td>1</td>
<td>11</td>
<td>B2</td>
<td>50</td>
<td>Pzi</td>
<td><p>$600,00</p></td>
<td><p>$12,00</p></td>
</tr>
</tbody>
</table>



## <a name="additional-resources"></a>Risorse aggiuntive

[Oggetti di costo](cost-object.md)

[Voci di costo](cost-entries.md)

[Novità e modifiche](../../fin-ops-core/fin-ops/get-started/whats-new-changed.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]