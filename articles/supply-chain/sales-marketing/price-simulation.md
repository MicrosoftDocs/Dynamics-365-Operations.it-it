---
title: Simulazione prezzo
description: In questo articolo vengono fornite informazioni sulla simulazione di prezzo per le offerte. La simulazione di prezzo consente di valutare l'effetto delle detrazioni sul prezzo di vendita futuro durante il processo di offerta, prima di stabilire un prezzo specifico.
author: omulvad
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SalesQuotationPriceSimulation
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, Operations
ms.custom: 12254
ms.assetid: 92be7c85-73cf-4f77-833c-d37ce779a031
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 6df840de688975b9fa11b866361d88a730426bd0
ms.contentlocale: it-it
ms.lasthandoff: 05/08/2018

---

# <a name="price-simulation"></a>Simulazione prezzo

[!include [banner](../includes/banner.md)]

In questo articolo vengono fornite informazioni sulla simulazione di prezzo per le offerte. La simulazione di prezzo consente di valutare l'effetto delle detrazioni sul prezzo di vendita futuro durante il processo di offerta, prima di stabilire un prezzo specifico.

In una simulazione di prezzo per un'offerta viene mostrato il nuovo importo totale in base a un nuovo prezzo proposto. È inoltre possibile visualizzare un nuovo importo per una riga specifica, creato per un'offerta già esistente. È possibile inserire una simulazione di prezzo e applicarla in un secondo momento. In alternativa, è possibile utilizzare l'offerta originale, senza alcuna simulazione di prezzo, apportandovi ulteriori modifiche durante il processo di vendita in collaborazione con il cliente.  

Una simulazione di prezzo non modifica il prezzo nell'offerta. Se la simulazione di prezzo viene applicata a un'intera offerta, verrà trattata come sconto speciale nell'intestazione dell'offerta. Se la simulazione di prezzo viene applicata ad articoli specifici, verrà trattata come sconto speciale nelle righe offerta. Quando si applica una simulazione di prezzo, il prezzo unitario di vendita nella riga dell'offerta che viene creata non cambia. Viene invece applicata una percentuale di sconto corrispondente alla riduzione di prezzo della riga dell'offerta. Quando si applica una simulazione di prezzo, il prezzo unitario di vendita e la percentuale di sconto vengono trasferiti nella riga o nell'intestazione dell'offerta.  

>[Nota!] Quando si esegue una simulazione di prezzo, per creare la simulazione viene utilizzata solo la valuta di vendita corrente. Per la visualizzazione dei totali dell'offerta, tuttavia, viene utilizzata una combinazione di valuta società e di valuta di vendita.  

Gli articoli supplementari aggiunti alle righe dell'offerta possono attivare sconti riga o plurimi. È possibile che attivino sconti totali in grado di modificare i margini e i rapporti di contribuzione delle righe dell'offerta e lo sconto complessivo.  

È inoltre possibile eseguire più simulazioni di prezzi e tenere traccia degli effetti delle rettifiche di prezzo sugli obiettivi dell'offerta. Tali simulazioni consentono di rettificare il prezzo complessivo dell'offerta o il prezzo di una o più righe specifiche all'interno dell'offerta stessa e di applicare quindi la simulazione che garantisce la maggiore probabilità di chiudere la vendita.  

Quando si crea un'offerta è possibile impostare un avviso. Di seguito sono indicate alcune modalità di utilizzo degli avvisi:

-   Mantenere l'utente al corrente dello stato delle offerte all'interno dell'organizzazione.
-   Attivare la revisione di un'offerta specifica o informare l'utente del superamento dei limiti di sconto.

## <a name="price-simulation-and-discounts"></a>Simulazione di prezzo e sconti
Per assicurarsi che gli sconti e i prezzi vengano calcolati correttamente, prestare attenzione quando si eseguono le simulazioni del prezzo su offerte con sconti. Poiché tutte le simulazioni del prezzo vengono considerate come sconti speciali relativi alla riga attiva oppure all'intera offerta, è necessario identificare le differenze negli sconti.

### <a name="types-of-discounts-in-trade-agreements"></a>Tipi di sconti negli accordi commerciali

Per gli accordi commerciali in Microsoft Dynamics 365 for Finance and Operations sono previsti quattro tipi di sconti sui prezzi. Tali sconti possono essere impostati per articoli, clienti o gruppi di prezzi diversi e possono avere un'applicazione limitata in base alla data. Per evitare calcoli errati, durante il processo di simulazione del prezzo è necessario considerare gli accordi commerciali. I quattro tipi di sconti previsti negli accordi commerciali sono i seguenti:

-   **Prezzo di vendita** è possibile specificare prezzi di vendita distinti per gli articoli. Quando vengono create le righe dell'offerta, il programma cerca il prezzo di vendita corretto per un articolo e lo trasferisce nelle righe dell'offerta. Questo tipo di sconto negli accordi commerciali non influisce pertanto sul processo di simulazione del prezzo. Il prezzo di vendita utilizzato nella riga dell'offerta riflette l'accordo commerciale.
-   **Sconto riga**: a seconda della quantità ordinata, vengono specificati sconti speciali per gli articoli. Gli importi riga in genere vengono ridotti dello sconto riga prima che venga eseguita una simulazione del prezzo. Questo tipo di sconto negli accordi commerciali influisce pertanto sul processo di simulazione del prezzo.
-   **Sconto plurimo**: se le quantità combinate superano il limite specificato, combinazioni predefinite di articoli ordinati danno luogo a uno sconto sull'intero ordine. Gli importi riga in genere vengono ridotti dello sconto riga prima che venga eseguita una simulazione del prezzo. Questo tipo di sconto negli accordi commerciali influisce pertanto sul processo di simulazione del prezzo.
-   **Sconto totale**: se gli importi combinati superano il limite specificato, articoli ordinati predefiniti danno luogo a uno sconto sull'intero ordine. Lo sconto totale viene generato dalle righe dell'offerta. Tuttavia, poiché lo sconto totale viene applicato al totale dell'offerta come sconto, viene ridotto l'importo totale dell'offerta. Questo tipo di sconto negli accordi commerciali influisce pertanto sul processo di simulazione del prezzo.

### <a name="quotation-lines-and-trade-agreements"></a>Righe dell'offerta e accordi commerciali

Quando si crea o si rettifica una riga di un'offerta, gli sconti riga vengono calcolati automaticamente. Il prezzo di vendita pertinente per l'articolo viene determinato sulla base dell'accordo commerciale.

## <a name="price-simulation-examples"></a>Esempi di simulazione di prezzo
Nei seguenti esempi viene utilizzata la simulazione del prezzo per intestazioni delle offerte e singole voci.

### <a name="price-simulation-for-quotation-headers"></a>Simulazione del prezzo per intestazioni delle offerte

Creare un'offerta con le seguenti righe:

-   10 unità dell'articolo BR-12 (prezzo di costo unitario: EUR 9,52 e prezzo di vendita unitario: EUR 15,32)
-   12 unità dell'articolo BR-14 (prezzo di costo unitario: EUR 7,48 e prezzo di vendita unitario: EUR 13,75)

Nella seguente tabella vengono illustrate le righe dell'offerta.

|                            | Calcolo                          | Risultato   |
|----------------------------|--------------------------------------|----------|
| Quantità di vendita             | 10 unità + 12 unità                  | 22 unità |
| Valore netto di vendita in EUR         | (10 × 15,32) + (12 × 13,75)          | 318,20   |
| Valore di costo in EUR          | (10 × 9,52) + (12 × 7,48)            | 184,96   |
| Margine di contribuzione in EUR | 318,20 – 184,96                      | 133,24   |
| Rapporto di contribuzione         | (\[318.20 – 184.96\] ÷ 318.20) × 100 | 41,87%   |

Eseguire una simulazione di prezzo e applicare uno sconto totale del 15% per l'intera offerta o per l'intestazione dell'offerta. Nella tabella seguente vengono illustrati i nuovi totali dell'offerta dopo l'esecuzione della simulazione del prezzo.

|                                                      | Calcolo                               | Risultato   |
|------------------------------------------------------|-------------------------------------------|----------|
| Quantità di vendita                                       | 10 unità + 12 unità                       | 22 unità |
| Valore netto di vendita precedente in EUR                               | (10 × 15,32) + (12 × 13,75)               | 318,20   |
| Valore di costo precedente in EUR                                | (10 × 9,52) + (12 × 7,48)                 | 184,96   |
| Margine di contribuzione precedente in EUR                       | 318,20 – 184,96                           | 133,24   |
| Rapporto di contribuzione precedente                               | (\[318.20 – (10 × 9.52)\] ÷ 318.20) × 100 | 41,87%   |
| Simulazione del prezzo dello sconto totale del 15% in EUR | (15 × 318,2) ÷ 100                        | 47,73    |
| Nuovo valore netto di vendita in EUR                               | 318,20 – 47,73                            | 270,47   |
| Nuovo margine di contribuzione in EUR                       | 270,47 – 184,96                           | 85,51    |
| Nuovo rapporto di contribuzione                               | \[(270.47 – 184.96) ÷ 270.47\] × 100      | 31,61%   |

### <a name="price-simulation-for-single-line-items"></a>Simulazione del prezzo per singole voci

Creare un'offerta con le seguenti righe:

-   10 unità dell'articolo BR-12 (prezzo di costo unitario: EUR 9,52 e prezzo di vendita unitario: EUR 15,32)
-   12 unità dell'articolo BR-14 (prezzo di costo unitario: EUR 7,48 e prezzo di vendita unitario: EUR 13,75)

Nella seguente tabella vengono illustrate le righe dell'offerta.

|                                      | Calcolo                          | Risultato   |
|--------------------------------------|--------------------------------------|----------|
| Quantità di vendita                       | 10 unità + 12 unità                  | 22 unità |
| Valore netto di vendita in EUR per BR-12         | 10 × 15,32                           | 153,20   |
| Valore netto di vendita in EUR per BR-14         | 12 × 13,75                           | 165,00   |
| Valore di costo in EUR per BR-12          | 10 × 9,52                            | 95,20    |
| Valore di costo in EUR per BR-14          | 12 × 7,48                            | 89,76    |
| Margine di contribuzione in EUR per BR-12 | 153,20 – 95,20                       | 58,00    |
| Margine di contribuzione in EUR per BR-14 | 165,00 – 89,76                       | 75,24    |
| Rapporto di contribuzione in EUR per BR-12  | \[(153.20 – 95.20) ÷ 153.20\] × 100  | 37,86    |
| Rapporto di contribuzione in EUR per BR-14  | \[(165.00 – 89.76) ÷ 165.00\] × 100  | 45,60    |
| Valore vendite totali in EUR             | (10 × 15,32) + (12 × 13,75)          | 318,20   |
| Valore di costo totale in EUR              | (10 × 9,52) + (12 × 7,48)            | 184,96   |
| Margine di contribuzione totale in EUR     | 318,20 – 184,96                      | 133,24   |
| Rapporto di contribuzione totale             | \[(318.20 – 184.96) ÷ 318.20\] × 100 | 41,87%   |

Eseguire una simulazione di prezzo e applicare uno sconto totale del 10% alle unità BR-12. Nella tabella seguente vengono illustrati i nuovi totali dell'offerta dopo l'esecuzione della simulazione del prezzo per la singola voce.

|                                                   | Calcolo                             | Risultato   |
|---------------------------------------------------|-----------------------------------------|----------|
| Quantità di vendita                                    | 10 unità + 12 unità                     | 22 unità |
| Valore netto di vendita precedente in EUR per BR-12                  | 10 × 15,32                              | 153,20   |
| Simulazione del prezzo dello sconto del 10% per BR-12 | (10 × 153,2) ÷ 100                      | 15,32    |
| Nuovo valore netto di vendita in EUR per BR-12                  | (10 × 15,32) – 15,32                    | 137,88   |
| Valore netto di vendita in EUR per BR-14                      | 12 × 13,75                              | 165,00   |
| Valore di costo in EUR per BR-12                       | 10 × 9,52                               | 95,20    |
| Valore di costo in EUR per BR-14                       | 12 × 7,48                               | 89,76    |
| Nuovo margine di contribuzione in EUR per BR-12          | 137,88 – 95,20                          | 42,68    |
| Margine di contribuzione in EUR per BR-14              | 165,00 – 89,76                          | 75,24    |
| Nuovo rapporto di contribuzione in EUR per BR-12           | \[(137.88 – 95.20) ÷ 137.88\] × 100     | 30,95    |
| Rapporto di contribuzione in EUR per BR-14               | \[(165.00 – 89.76) ÷ 165.00\] × 100     | 45,60    |
| Nuovo valore di vendite totali in EUR                      | \[(10 × 15.32) – 15.32\] + (12 × 13.75) | 302,88   |
| Valore di costo totale in EUR                           | (10 × 9,52) + (12 × 7,48)               | 184,96   |
| Nuovo margine di contribuzione totale in EUR              | 302,88 – 184,96                         | 117,92   |
| Nuovo rapporto di contribuzione totale                      | \[(302.88 – 184.96) ÷ 302.88\] × 100    | 38,93%   |

La simulazione del prezzo ha effetto solo sulla riga a cui viene applicata e riduce il totale relativo a tale riga.




