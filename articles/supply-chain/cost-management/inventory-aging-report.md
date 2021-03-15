---
title: Esempi e logica dei report di aging delle scorte
description: Questo argomento presenta alcuni esempi che mostrano come interpretare i risultati di un report di aging delle scorte.
author: RichardLuan
manager: tfehr
ms.date: 5/29/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventAgingStorage, InventAgingStorageChart, InventAgingStorageDetails
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: riluan
ms.search.validFrom: 2020-5-29
ms.dyn365.ops.version: ''
ms.openlocfilehash: b3822cf4c26d7ef9cd0d062d57fa909140d7e258
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4983927"
---
# <a name="inventory-aging-report-examples-and-logic"></a>Esempi e logica dei report di aging delle scorte

[!include [banner](../includes/banner.md)]

Questo argomento presenta alcuni esempi che mostrano come interpretare i risultati di un report di **aging delle scorte**. Questo report classifica i valori delle quantità e delle scorte disponibili per un articolo o un gruppo di articoli selezionati in diversi gruppi di periodi. Questo argomento mostra anche la logica interna del report.

Gli esempi in questo argomento mostrano i risultati presentati su un report **di aging delle scorte** standard. Tuttavia, in generale, si consiglia di utilizzare la versione [Archiviazione report di aging delle scorte](inventory-aging-report-storage.md) di questo report, soprattutto quando si hanno molti articoli e magazzini da elaborare. L'archiviazione report di aging delle scorte salva ogni report generato, mostra i risultati come una pagina interattiva e un grafico e consente di esportare qualsiasi rapporto salvato.

## <a name="sample-data-that-is-used-in-these-examples"></a>Dati di esempio utilizzati in questi esempi

Gli esempi in questo argomento si basano sui dati di transazione delle scorte di esempio descritti in questa sezione.

### <a name="storage-dimension-setup"></a>Configurazione delle dimensioni di immagazzinamento

Il sistema di esempio contiene la seguente configurazione delle dimensioni di immagazzinamento.

| Nome      | Attive | Inventario fisico | Inventario finanziario |
|-----------|--------|--------------------|---------------------|
| Sito      | Sì    | Sì                | Sì                 |
| Magazzino | Sì    | Sì                | Nessuna                  |

### <a name="inventory-model"></a>Modello inventariale

Per il sistema di esempio, il modello inventariale per i prodotti rilasciati è *FIFO* e l'impostazione **Prezzo di costo** per il modello inventariale è *Includi valore fisico*.

### <a name="inventory-transactions"></a>Operazioni di magazzino

Il sistema di esempio contiene le seguenti transazioni di inventario per un prodotto rilasciato con il numero di articolo *1.000*.

| Riferimento      | Sito | Magazzino | Ricevimento   | Uscita | Data effettiva | Data finanziaria | Quantità | Importo costo | Importo costi fisico |
|----------------|------|-----------|-----------|-------|---------------|----------------|----------|-------------|----------------------|
| Ordine fornitore | 1    | 11        | Acquistato |       | 15 marzo      | 15 marzo       | 10       | 1.000       | 1.000                |
| Ordine fornitore | 2    | 21        | Acquistato |       | 15 marzo      | 15 marzo       | 10       | 2,000       | 2,000                |
| Ordine fornitore | 1    | 11        | Ricevuti  |       | 15 aprile      |                | 5        |             | 375                  |
| Ordine di trasferimento | 1    | 11        |           | Venduto  | 2° maggio         | 2° maggio          | -5       | -458,33     | -458,33              |
| Ordine di trasferimento | 1    | 12        | Acquistato |       | 2° maggio         | 2° maggio          | 5        | 458.33      | 458.33               |
| Ordine cliente    | 1    | 12        |           | Venduto  | 3° maggio         | 3° maggio          | -1       | -91,67      | -91,67               |

## <a name="how-quantities-and-amounts-in-each-period-bucket-are-calculated"></a>Come vengono calcolate le quantità e gli importi in ciascun intervallo di periodi

Utilizzando i dati di esempio descritti nelle sezioni precedenti, puoi eseguire un report **di aging delle scorte** con le seguenti impostazioni:

- **Alla data:** *9 maggio 2020*
- **Sito:** *Visualizza*
- **Magazzino:** *No*
- **Numero articolo:** *Totale*
- **Periodo di aging:** imposta questo campo per generare bucket mensili.

In questo caso, il contenuto del report generato sarà simile al seguente esempio.

<table>
<thead>
<tr>
    <th rowspan="2">Numero articolo</th>
    <th rowspan="2">Sito</th>
    <th rowspan="2">Quantità disponibile</th>
    <th rowspan="2">Valore disponibilità</th>
    <th rowspan="2">Quantità valore di magazzino</th>
    <th rowspan="2">Valore di magazzino</th>
    <th rowspan="2">Costo unitario medio</th>
    <th colspan="2">8/5/2020 - 1/5/2020</th>
    <th colspan="2">30/4/2020 -1/4/2020</th>
    <th colspan="2">31/3/2020 - 1/3/2020</th>
</tr>
<tr>
    <th>P1: Quantità</th>
    <th>P1: Importo</th>
    <th>P2: Quantità</th>
    <th>P2: Importo</th>
    <th>P3: Quantità</th>
    <th>P3: Importo</th>
</tr>
</thead>
<tbody>
<tr>
    <td>1000</td>
    <td>1</td>
    <td>14</td>
    <td>1,283.33</td>
    <td>14</td>
    <td>1,283.33</td>
    <td>91.67</td>
    <td></td>
    <td></td>
    <td>5.00</td>
    <td>458.33</td>
    <td>9.00</td>
    <td>825.00</td>
</tr>
<tr>
    <td>1000</td>
    <td>2</td>
    <td>10</td>
    <td>2,000.00</td>
    <td>10</td>
    <td>2,000.00</td>
    <td>200.00</td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td>10.00</td>
    <td>2,000.00</td>
</tr>
</tbody>
<tfoot>
<tr>
    <td><strong>1.000 totali</strong></td>
    <td></td>
    <td><strong>24.00</strong></td>
    <td><strong>3,283.33</strong></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td><strong>5.00</strong></td>
    <td><strong>458.33</strong></td>
    <td><strong>19</strong></td>
    <td><strong>2,825.00</strong></td>
</tr>
</tfoot>
</table>

Nota i seguenti dettagli in questo report di esempio:

- I valori **Quantità valore di inventario**, **Valore di inventario** e **Costo unitario medio** mostrati nel report sono valori per le dimensioni delle scorte finanziarie (**Sito**, in questo caso).

    Ad esempio, per il sito 1, il report mostra le seguenti informazioni:

    - Il valore **Quantità valore di inventario** è *14* (= 10 + 5 - 5 + 5 - 1).
    - Il valore **Valore di inventario** è *1.283,33* (= 1.000 + 375 - 458,33 + 458,33 - 91,67).
    - Il valore **Costo unitario medio** è *91,67*.
    - Il valore **Valore disponibilità** e il valore **Quantità** in ciascun bucket del periodo viene calcolato utilizzando il valore **Costo unitario medio**.

- Il report determina la quantità disponibile per ciascun bucket del periodo riassumendo la quantità di inventario totale ricevuta per ciascun bucket del periodo. Quindi applica il principio FIFO (first in, first out) per detrarre la quantità totale emessa, indipendentemente dal modello di inventario utilizzato dagli articoli.

Se esegui di nuovo lo stesso rapporto, ma questa volta hai impostato entrambi i campi **Sito** e **Magazzino** su *Visualizza*, il nuovo report sarà simile al seguente esempio.

<table>
<thead>
<tr>
    <th rowspan="2">Numero articolo</th>
    <th rowspan="2">Sito</th>
    <th rowspan="2">Magazzino</th>
    <th rowspan="2">Quantità disponibile</th>
    <th rowspan="2">Valore disponibilità</th>
    <th rowspan="2">Quantità valore di magazzino</th>
    <th rowspan="2">Valore di magazzino</th>
    <th rowspan="2">Costo unitario medio</th>
    <th colspan="2">8/5/2020 - 1/5/2020</th>
    <th colspan="2">30/4/2020 -1/4/2020</th>
    <th colspan="2">31/3/2020 - 1/3/2020</th>
</tr>
<tr>
    <th>P1: Quantità</th>
    <th>P1: Importo</th>
    <th>P2: Quantità</th>
    <th>P2: Importo</th>
    <th>P3: Quantità</th>
    <th>P3: Importo</th>
</tr>
</thead>
<tbody>
<tr>
    <td>1000</td>
    <td>1</td>
    <td>11</td>
    <td>10</td>
    <td>916.67</td>
    <td>14</td>
    <td>1,283.33</td>
    <td>91.67</td>
    <td></td>
    <td></td>
    <td>5.00</td>
    <td>458.33</td>
    <td>5.00</td>
    <td>458.33</td>
</tr>
<tr>
    <td>1000</td>
    <td>1</td>
    <td>12</td>
    <td>4</td>
    <td>366.67</td>
    <td>14</td>
    <td>1,283.33</td>
    <td>91.67</td>
    <td>4.00</td>
    <td>366.67</td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
</tr>
<tr>
    <td>1000</td>
    <td>2</td>
    <td></td>
    <td>10</td>
    <td>2,000.00</td>
    <td>10</td>
    <td>2,000.00</td>
    <td>200.00</td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td>10.00</td>
    <td>2,000.00</td>
</tr>
</tbody>
<tfoot>
<tr>
    <td><strong>1.000 totali</strong></td>
    <td></td>
    <td></td>
    <td><strong>24.00</strong></td>
    <td><strong>3,283.33</strong></td>
    <td></td>
    <td></td>
    <td></td>
    <td><strong>4.00</strong></td>
    <td><strong>366.67</strong></td>
    <td><strong>5.00</strong></td>
    <td><strong>458.33</strong></td>
    <td><strong>15</strong></td>
    <td><strong>2,458.33</strong></td>
</tr>
</tfoot>
</table>

Questa volta, il sito 1 è diviso in due righe, una per il magazzino 11 e una per il magazzino 12. Tuttavia, i valori **Quantità valore di inventario**, **Valore di inventario** e **Costo unitario medio** sono gli stessi poiché **Magazzino** non è una dimensione dell'inventario finanziario.

Notare inoltre che la distribuzione della quantità del sito 1 è diversa. Nel primo report eseguito, il sistema ha ignorato l'ordine di trasferimento che si è verificato nello stesso sito e ha dedotto la quantità della fattura di vendita dal bucket del periodo **31/3/2020 - 1/3/2020** nel sito 1. Tuttavia, nel nuovo report, il sistema deduce la quantità della fattura di vendita dal bucket del periodo **8/5/2020 - 1/5/2020** nel magazzino 12.

## <a name="effects-of-inventory-closing"></a>Effetti della chiusura dell'inventario

Se esegui la chiusura dell'inventario per maggio e successivamente esegui nuovamente il report precedente, ma imposti il campo **Alla data** su *31 maggio 2020*, noterai i seguenti risultati:

- I valori **Valore di inventario** e **Costo unitario medio** vengono aggiornati.
- Il valore **Valore disponibilità** e tutti i valori **Importo** in ogni bucket del periodo vengono aggiornati di conseguenza.

Il nuovo report sarà simile all'esempio seguente.

<table>
<thead>
<tr>
    <th rowspan="2">Numero articolo</th>
    <th rowspan="2">Sito</th>
    <th rowspan="2">Magazzino</th>
    <th rowspan="2">Quantità disponibile</th>
    <th rowspan="2">Valore disponibilità</th>
    <th rowspan="2">Quantità valore di magazzino</th>
    <th rowspan="2">Valore di magazzino</th>
    <th rowspan="2">Costo unitario medio</th>
    <th colspan="2">31/5/2020 - 1/5/2020</th>
    <th colspan="2">30/4/2020 -1/4/2020</th>
    <th colspan="2">31/3/2020 - 1/3/2020</th>
</tr>
<tr>
    <th>P1: Quantità</th>
    <th>P1: Importo</th>
    <th>P2: Quantità</th>
    <th>P2: Importo</th>
    <th>P3: Quantità</th>
    <th>P3: Importo</th>
</tr>
</thead>
<tbody>
<tr>
    <td>1000</td>
    <td>1</td>
    <td>11</td>
    <td>10</td>
    <td>910.70</td>
    <td>14</td>
    <td>1,275.00</td>
    <td>91.07</td>
    <td>0,00</td>
    <td></td>
    <td>5.00</td>
    <td>455.36</td>
    <td>5.00</td>
    <td>455.36</td>
</tr>
<tr>
    <td>1000</td>
    <td>1</td>
    <td>12</td>
    <td>4</td>
    <td>364.29</td>
    <td>14</td>
    <td>1,275.00</td>
    <td>91.07</td>
    <td>4.00</td>
    <td>364.29</td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
</tr>
<tr>
    <td>1000</td>
    <td>2</td>
    <td></td>
    <td>10</td>
    <td>2,000.00</td>
    <td>10</td>
    <td>2,000.00</td>
    <td>200.00</td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td>10.00</td>
    <td>2,000.00</td>
</tr>
</tbody>
<tfoot>
<tr>
    <td><strong>1.000 totali</strong></td>
    <td></td>
    <td></td>
    <td><strong>24.00</strong></td>
    <td><strong>3,275.00</strong></td>
    <td></td>
    <td></td>
    <td></td>
    <td><strong>4.00</strong></td>
    <td><strong>364.29</strong></td>
    <td><strong>5.00</strong></td>
    <td><strong>455.36</strong></td>
    <td><strong>15</strong></td>
    <td><strong>2,455.36</strong></td>
</tr>
</tfoot>
</table>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]