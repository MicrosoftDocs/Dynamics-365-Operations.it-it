---
title: Le i valori oggetti
description: Questo articolo fornisce informazioni sul modo in cui vengono calcolati i valori di un oggetto di magazzino.
author: YuyuScheller
manager: AnnBe
ms.date: 2015-12-07 09 - 09 - 05
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: InventCostOnhandItem
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 19111
ms.assetid: 56a7c8ba-bf4a-4b1d-918d-56bb96926c4f
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 7a0a2af2094e3e5be757d3dd82255769677b96ea
ms.openlocfilehash: 8898d5d91ffb4f73ea68f1251e1a99440e81bcd4
ms.lasthandoff: 03/29/2017


---

# <a name="inventory-object-values"></a>Le i valori oggetti

Questo articolo fornisce informazioni sul modo in cui vengono calcolati i valori di un oggetto di magazzino. 

Una nuova funzionalità denominata ** quantità fisica ** consente di visualizzare i valori di un oggetto specifico di magazzino. Un oggetto di costo rappresenta il livello di entità in cui la contabilità inventario viene eseguita. Per ulteriori informazioni sugli oggetti di costo, vedere [Oggetti di costo](cost-object.md). Per visualizzare i valori di un magazzino specifico, fare clic sull'oggetto ** quantità fisica ** ** oggetto di costo ** nella pagina. Ecco come valore di un oggetto dell'inventario viene calcolato: Oggetto di magazzino. Oggetto di costo = di valore. Oggetto medio di l × di costo unitario. Quantità le seguenti in l esempio i valori di un oggetto e inventariali un oggetto di costo vengono calcolati. Due eventi di entrata prodotti vengono registrati nell'articolo A:

-   Entrata prodotti 1: Quantità = 100. pc, importo = $1,000.00 sito, = 1, =11 magazzino, lotto meno. = B1
-   Entrata prodotti 2: Quantità = 50. pc, importo = $800.00 sito, = 1, =11 magazzino, lotto meno. = B2

Nella seguente tabella viene visualizzato il risultato del calcolo per un oggetto di costo. È possibile visualizzare il risultato nella pagina **Oggetto di costo**.

<table style="width:100%;">
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

<table style="width:100%;">
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



<a name="see-also"></a>Vedere anche
--------

[Cost objects](cost-object.md)

[Cost entries](cost-entries.md)

[Novità e variabile in Microsoft Dynamics AX (/dynamics365/operations/dev-itpro/get-started/what] - nuova è variabile)


