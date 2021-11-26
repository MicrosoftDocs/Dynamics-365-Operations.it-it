---
title: Esempi e logica di report sul valore di magazzino
description: Questo argomento fornisce alcuni esempi di risultati presentati su ogni tipo di report sul valore di magazzino. I report sul valore di magazzino forniscono dettagli sulle quantità e sugli importi fisici e finanziari del magazzino.
author: banluo-ms
ms.date: 10/19/2021
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: banluo
ms.search.validFrom: 2021-10-19
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 4ad85058c8743895185d3da2e8975711f1e3bc2c
ms.sourcegitcommit: ba10ba2cd4fb4267afb5aacae4f6a52aa2456e7e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/11/2021
ms.locfileid: "7798393"
---
# <a name="inventory-value-report-examples-and-logic"></a>Esempi e logica di report sul valore di magazzino

[!include [banner](../includes/banner.md)]

I report sul valore di magazzino forniscono dettagli sulle quantità e sugli importi fisici e finanziari del magazzino. Questo argomento fornisce alcuni esempi di risultati presentati su ogni tipo di report sul valore di magazzino.

Per altre informazioni su come generare e utilizzare ciascun tipo di report sul valore di magazzino, vedi [Report sul valore di magazzino](inventory-value-report-storage.md).

## <a name="sample-data-that-is-used-in-these-examples"></a>Dati di esempio utilizzati in questi esempi

Gli esempi in questo argomento si basano sui dati di transazione delle scorte di esempio descritti in questa sezione.

### <a name="storage-dimension-setup"></a>Configurazione delle dimensioni di immagazzinamento

Il sistema di esempio contiene la seguente configurazione delle dimensioni di immagazzinamento.

| Nome | Attive | Inventario fisico | Inventario finanziario |
|---|---|---|---|
| Sito | Sì | Sì | Sì |
| Magazzino | Sì | Sì | No |

### <a name="inventory-model"></a>Modello inventariale

Per il sistema di esempio, il modello inventariale per i prodotti rilasciati è *FIFO* e il campo **Prezzo di costo** per il modello inventariale è impostato su *Includi valore fisico*.

### <a name="inventory-transactions"></a>Transazioni di inventario

Il sistema di esempio contiene le seguenti transazioni di inventario per un prodotto rilasciato con il numero di articolo *B0001*.

| Riferimento | Sito | Magazzino | Ricevimento | Problema | Data effettiva | Data finanziaria | Quantità | Importo costo | Importo costi fisico |
|---|---|---|---|---|---|---|---|---|---|
| Ordine fornitore | 1 | 11 | Acquistato | | 15 marzo | 15 marzo | 10 | 1.000 | 1.000 |
| Ordine fornitore | 2 | 21 | Acquistato | | 15 marzo | 15 marzo | 10 | 2,000 | 2,000 |
| Ordine fornitore | 1 | 11 | Ricevuti | | 15 aprile | | 5 | | 375 |
| Ordine di trasferimento | 1 | 11 | | Venduto | 2° maggio | 2° maggio | -5 | -458,33 | -458,33 |
| Ordine di trasferimento | 1 | 12 | Acquistato | | 2° maggio | 2° maggio | 5 | 458.33 | 458.33 |
| Ordine cliente | 1 | 12 | | Venduta | 3° maggio | 3° maggio | -1 | -91,67 | -91,67 |

### <a name="inventory-value-report-configuration"></a>Configurazione del report sul valore di magazzino

Il sistema di esempio include una configurazione di report sul valore di magazzino con le seguenti impostazioni:

- **Intervallo:**  *Data di registrazione*
- **Magazzino:** *Sì*
- **Calcola il costo medio unitario:** *Sì*
- **Quantità totale e valore:** *Sì*
- **Sito, Visualizza:** *Selezionato*
- **ID risorsa, visualizzazione:** *Sì*
- **Livello:** *Totali*

## <a name="inventory-value-report-example-1"></a>Esempio 1 di archiviazione report valori di magazzino

La tabella e le illustrazioni seguenti mostrano i risultati quando si utilizzano i dati di esempio e la configurazione del report descritti in precedenza in questo argomento.

| Tipo di risorsa | Risorsa | Sito | Riferimento | Inventario: quantità finanziaria | Inventario: importo finanziario | Inventario: quantità fisica registrata | Inventario: importo fisico registrato | Inventario: quantità | Inventario: importo | Costo unitario medio |
|---|---|---|---|---|---|---|---|---|---|---|
| Materiale | B0001 | 1 | Saldo finale | 9.00 | 908.33 | 5.00 | 375.00 | 14,00 | 1,283.33 | 91.67 |
| Materiale | B0001 | 2 | Saldo finale | 10.00 | 2,000.00 | 0,00 | 0,00 | 10.00 | 2,000.00 | 200.00 |

### <a name="standard-inventory-value-report-for-example-1"></a>Report sul valore di magazzino standard per l'esempio 1

La seguente illustrazione mostra il report **Valore di magazzino** standard per l'esempio 1. Seleziona l'illustrazione per aprire una versione più grande.

[![Report sul valore di magazzino per l'esempio 1.](media/inventory-value-report-ex1-small.png "Report sul valore di magazzino per l'esempio 1")](media/inventory-value-report-ex1.png)

### <a name="inventory-value-report-storage-report-for-example-1"></a>Report di archiviazione valori di magazzino per l'esempio 1

La seguente illustrazione mostra il report **Archiviazione report valori di magazzino** per l'esempio 1. Seleziona l'illustrazione per aprire una versione più grande.

[![Report di archiviazione valori di magazzino per l'esempio 1.](media/inventory-value-report-storage-ex1-small.png "Report di archiviazione valori di magazzino per l'esempio 1")](media/inventory-value-report-storage-ex1.png)

## <a name="inventory-value-report-example-2"></a>Esempio 2 di archiviazione report valori di magazzino

La tabella e le illustrazioni seguenti mostrano i risultati quando si utilizzano i dati di esempio descritti in precedenza in questo argomento, ma si modifica il valore del campo **Livello** su *Transazioni* nella configurazione del report e si imposta il campo **Da data** campo su *15 marzo* quando esegui il report.

| Tipo di risorsa | Risorsa | Sito | Data | Numero | Riferimento | Inventario: quantità finanziaria | Inventario: importo finanziario | Inventario: quantità fisica registrata | Inventario: importo fisico registrato | Inventario: quantità | Inventario: importo |
|---|---|---|---|---|---|---|---|---|---|---|---|
| Materiale | B0001 | 1 | 3/15/2021 | 00000126 | Ordine fornitore | 0,00 | 0,00 | 10.00 | 1,000.00 | **10.00** | **1,000.00** |
| Materiale | B0001 | 1 | 3/15/2021 | 00000126 | Ordine fornitore | 10.00 | 1,000.00 | -10.00 | -1.000,00 | **0.00** | **0.00** |
| Materiale | B0001 | 1 | 4/15/2021 | 00000128 | Ordine fornitore | 0,00 | 0,00 | 5.00 | 375.00 | **5.00** | **375.00** |
| Materiale | B0001 | 1 | 5/2/2021 | 000003 | Spedizione ordine di trasferimento | -5,00 | -458,33 | 0,00 | 0,00 | **-5.00** | **-458.33** |
| Materiale | B0001 | 1 | 5/2/2021 | 000003 | Ricevimento ordine di trasferimento | 5.00 | 458.33 | 0,00 | 0,00 | **5.00** | **458.33** |
| Materiale | B0001 | 1 | 5/3/2021 | 000835 | Ordine cliente | 0,00 | 0,00 | -1,00 | -91,67 | **-1.00** | **-91.67** |
| Materiale | B0001 | 1 | 5/3/2021 | 000835 | Ordine cliente | -1,00 | -91,67 | 1.00 | 91.67 | **0.00** | **0.00** |
| Materiale | B0001 | 2 | 3/15/2021 | 00000127 | Ordine fornitore | 0,00 | 0,00 | 10.00 | 2,000.00 | **10.00** | **2,000.00** |
| Materiale | B0001 | 2 | 3/15/2021 | 00000127 | Ordine fornitore | 10.00 | 2,000.00 | -10.00 | -2.000,00 | **0.00** | **0.00** |
| Materiale | B0001 | 2 | 5/2/2021 | 000003 | Spedizione ordine di trasferimento | 5.00 | 458.33 | 0,00 | 0,00 | **5.00** | **458.33** |
| Materiale | B0001 | 2 | 5/2/2021 | 000003 | Ricevimento ordine di trasferimento | -5,00 | -458,33 | 0,00 | 0,00 | **-5.00** | **-458.33** |

### <a name="standard-inventory-value-report-for-example-2"></a>Report sul valore di magazzino standard per l'esempio 2

La seguente illustrazione mostra il report **Valore di magazzino** standard per l'esempio 2. Seleziona l'illustrazione per aprire una versione più grande.

[![Report sul valore di magazzino per l'esempio 2.](media/inventory-value-report-ex2-small.png "Report sul valore di magazzino per l'esempio 2")](media/inventory-value-report-ex2.png)

### <a name="inventory-value-report-storage-report-for-example-2"></a>Report di archiviazione valori di magazzino per l'esempio 2

La seguente illustrazione mostra il report **Archiviazione report valori di magazzino** per l'esempio 2. Seleziona l'illustrazione per aprire una versione più grande.

[![Report di archiviazione valori di magazzino per l'esempio 2.](media/inventory-value-report-storage-ex2-small.png "Report di archiviazione valori di magazzino per l'esempio 2")](media/inventory-value-report-storage-ex2.png)

## <a name="inventory-value-report-example-3"></a>Esempio 3 di archiviazione report valori di magazzino

Si consiglia di eseguire report sul valore di magazzino dopo il ricalcolo o la chiusura dell'inventario, in modo da disporre delle transazioni e degli importi interessati dal ricalcolo o dalla chiusura dell'inventario.

Le seguenti sottosezioni mostrano i report sul valore di magazzino generati dopo la chiusura dell'inventario fino al 30 maggio.

### <a name="example-3-when-the-totals-level-is-used"></a>Esempio 3 quando viene utilizzato il livello Totali

La tabella seguente mostra i risultati quando si utilizzano i dati di esempio e la configurazione del report descritti in precedenza in questo argomento. (In quella configurazione di report, il campo **Livello** è impostato su *Totali*.)

| Tipo di risorsa | Risorsa | Sito | Riferimento | Inventario: quantità finanziaria | Inventario: importo finanziario | Inventario: quantità fisica registrata | Inventario: importo fisico registrato | Inventario: quantità | Inventario: importo | Costo unitario medio |
|---|---|---|---|---|---|---|---|---|---|---|
| Materiale | B0001 | 1 | Saldo finale | 9.00 | 900.00 | 5.00 | 375.00 | 14,00 | 1,275.00 | 91.07 |
| Materiale | B0001 | 2 | Saldo finale | 10.00 | 2,000.00 | 0,00 | 0,00 | 10.00 | 2,000.00 | 200.00 |

### <a name="example-3-when-the-transactions-level-is-used"></a>Esempio 3 quando viene utilizzato il livello Transazioni

La tabella seguente mostra i risultati quando si utilizzano i dati di esempio descritti in precedenza in questo argomento, ma si modifica il valore del campo **Livello** su *Transazioni* nella configurazione del report.

| Tipo di risorsa | Risorsa | Sito | Data | Numero | Riferimento | Inventario: quantità finanziaria | Inventario: importo finanziario | Inventario: quantità fisica registrata | Inventario: importo fisico registrato | Inventario: quantità | Inventario: importo |
|---|---|---|---|---|---|---|---|---|---|---|---|
| Materiale | B0001 | 1 | 3/15/2021 | 00000126 | Ordine fornitore | 0,00 | 0,00 | 10.00 | 1,000.00 | 10.00 | 1,000.00 |
| Materiale | B0001 | 1 | 3/15/2021 | 00000126 | Ordine fornitore | 10.00 | 1,000.00 | -10.00 | -1.000,00 | 0,00 | 0,00 |
| Materiale | B0001 | 1 | 4/15/2021 | 00000128 | Ordine fornitore | 0,00 | 0,00 | 5.00 | 375.00 | 5.00 | 375.00 |
| Materiale | B0001 | 1 | 5/2/2021 | 000003 | Spedizione ordine di trasferimento | -5,00 | -458,33 | 0,00 | 0,00 | -5,00 | -458,33 |
| Materiale | B0001 | 1 | 5/2/2021 | 000003 | Ricevimento ordine di trasferimento | 5.00 | 458.33 | 0,00 | 0,00 | 5.00 | 458.33 |
| Materiale | B0001 | 1 | 5/3/2021 | 000835 | Ordine cliente | 0,00 | 0,00 | -1,00 | -91,67 | -1,00 | -91,67 |
| Materiale | B0001 | 1 | 5/3/2021 | 000835 | Ordine cliente | -1,00 | -91,67 | 1.00 | 91.67 | 0,00 | 0,00 |
| Materiale | B0001 | 1 | 5/31/2021 | 000835 | Ordine cliente | 0,00 | -8,33 | 0,00 | 0,00 | 0,00 | -8,33 |
| Materiale | B0001 | 1 | 5/31/2021 | 000003 | Spedizione ordine di trasferimento | 0,00 | -41,67 | 0,00 | 0,00 | 0,00 | -41,67 |
| Materiale | B0001 | 1 | 5/31/2021 | 000003 | Ricevimento ordine di trasferimento | 0,00 | 41.67 | 0,00 | 0,00 | 0,00 | 41.67 |
| Materiale | B0001 | 2 | 3/15/2021 | 00000127 | Ordine fornitore | 0,00 | 0,00 | 10.00 | 2,000.00 | 10.00 | 2,000.00 |
| Materiale | B0001 | 2 | 3/15/2021 | 00000127 | Ordine fornitore | 10.00 | 2,000.00 | -10.00 | -2.000,00 | 0,00 | 0,00 |
| Materiale | B0001 | 2 | 5/2/2021 | 000003 | Spedizione ordine di trasferimento | 5.00 | 458.33 | 0,00 | 0,00 | 5.00 | 458.33 |
| Materiale | B0001 | 2 | 5/2/2021 | 000003 | Ricevimento ordine di trasferimento | -5,00 | -458,33 | 0,00 | 0,00 | -5,00 | -458,33 |
| Materiale | B0001 | 2 | 5/31/2021 | 000003 | Spedizione ordine di trasferimento | 0,00 | 41.67 | 0,00 | 0,00 | 0,00 | 41.67 |
| Materiale | B0001 | 2 | 5/31/2021 | 000003 | Ricevimento ordine di trasferimento | 0,00 | -41,67 | 0,00 | 0,00 | 0,00 | -41,67 |
