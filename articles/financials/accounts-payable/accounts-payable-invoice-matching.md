---
title: "Abbinamento fatture della contabilità fornitori"
description: "Il processo di abbinamento fatture della contabilità fornitori consente di abbinare le informazioni relative a fatture fornitore, ordini fornitore ed entrate prodotti."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: VendInvoicePostingHistory
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 27361
ms.assetid: 9f3dace7-05d8-4974-8f85-aca2e224876c
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: dc5e072f23cbb0dcc2d3d1d390070bb11a2d2f06
ms.contentlocale: it-it
ms.lasthandoff: 11/03/2017

---

# <a name="accounts-payable-invoice-matching"></a>Abbinamento fatture della contabilità fornitori

[!INCLUDE [banner](../includes/banner.md)]

Il processo di abbinamento fatture della contabilità fornitori consente di abbinare le informazioni relative a fatture fornitore, ordini fornitore ed entrate prodotti.

Quando si abbinano documenti, le differenze tra questi documenti sono dette discrepanze di abbinamento. Le discrepanze di abbinamento vengono confrontate con le tolleranze specificate. Se una discrepanza di abbinamento supera la percentuale o l'importo di tolleranza, nelle pagne Fattura fornitore e Dettagli cronologia e abbinamento fatture verranno visualizzate icone di scostamento relative all'abbinamento. 

Ad esempio, si immette un ordine fornitore con una voce relativa a 1.000 batterie con prezzo unitario 1,00. L'ordine fornitore viene approvato e inviato al fornitore. Quest'ultimo spedisce 1.000 batterie a fronte delle quali si immette un'entrata prodotti per 1.000 batterie con prezzo unitario 1,00. Il costo di magazzino per le batterie viene aggiornato con questo prezzo. 

Si riceve una fattura relativa a 1.000 batterie con prezzo unitario 1,10. Per questa categoria di articoli, i criteri relativi alla persona giuridica prevedono una tolleranza relativa al prezzo unitario netto pari al 5%. Un prezzo pari a 1,05 sarebbe accettabile, ma non un prezzo pari a 1,10. Al momento dell'immissione delle informazioni di fatturazione, viene identificata una discrepanza di abbinamento prezzi e, in attesa che venga risolta, è possibile salvare la fattura.

Sono disponibili i tipi di abbinamento fatture di contabilità fornitori indicati di seguito.

-   Abbinamento totali fatture: consente di abbinare gli importi totali della fattura agli importi totali dell'ordine fornitore. Questo tipo di abbinamento fatture include il livello minimo di dettaglio, questa opzione può essere utilizzata per ridurre al minimo il tempo impiegato dal personale per la verifica delle informazioni di abbinamento fatture.
-   Abbinamento a due elementi di verifica: consente di abbinare le informazioni sul prezzo presenti nella fattura a quelle presenti nell'ordine fornitore.
-   Abbinamento a tre elementi di verifica: consente di abbinare le informazioni sul prezzo presenti nella fattura a quelle presenti nell'ordine fornitore. Abbina inoltre le informazioni sulla quantità presenti nella fattura alle informazioni sulla quantità presenti nelle entrate prodotti selezionate per la fattura.
-   Abbinamento spese: consente di abbinare le informazioni sulle spese (importi) presenti nella fattura alle informazioni sulle spese (importi) presenti nell'ordine fornitore.

> [!NOTE]
> È possibile effettuare altre forme di convalida fattura tramite i criteri fatture fornitore. 

Tramite l'abbinamento a due e a tre elementi di verifica vengono abbinate sempre le informazioni sul prezzo in base al prezzo unitario. È inoltre possibile configurare questi criteri per abbinare le informazioni sul prezzo in base al totale dei prezzi.
-   Abbinamento prezzo unitario netto: consente di abbinare le informazioni sul prezzo per l'abbinamento a due o a tre elementi di verifica tramite il confronto tra il prezzo unitario netto per ogni riga fattura e il prezzo unitario netto corrispondente dell'ordine fornitore. Il prezzo unitario netto viene determinato in base alla formula seguente: importo netto riga / quantità riga.
-   Abbinamento totali dei prezzi: consente di abbinare le informazioni sul prezzo per l'abbinamento a due o a tre elementi di verifica tramite il confronto tra l'importo netto (totale dei prezzi) per ogni riga fattura e l'importo netto corrispondente dell'ordine fornitore. L'importo netto viene determinato in base alla formula seguente: (prezzo unitario \* quantità riga) + spese riga - sconti riga

In genere, i calcoli di abbinamento fatture vengono eseguiti automaticamente al momento della modifica delle fatture fornitore nella pagina Fattura fornitore. In alternativa, l'abbinamento fatture può essere eseguito su richiesta, se necessario. L'abbinamento fatture nella richiesta viene controllato per la persona giuridica dallo stato Aggiorna automaticamente intestazione fattura a nella pagina dei parametri di contabilità fornitori nella scheda Convalida fattura. L'abbinamento fatture può essere eseguito come parte di un processo di revisione della fattura. È possibile visualizzare i risultati di abbinamento fatture automatico sulla pagina Fattura fornitore e nelle pagine di abbinamento fatture correlate.

## <a name="invoice-totals-matching"></a>Abbinamento totali fatture
È possibile utilizzare l'abbinamento totali fatture per assicurarsi che gli importi totali fattura non si discostino dagli importi previsti oltre un livello accettabile. Sei totali vengono confrontati nella pagina dei dettagli di abbinamento totali fatture, come illustrato nella seguente tabella. Se la tolleranza consentita per l'abbinamento totali fatture è pari al 20%, la percentuale di scostamento 100% per l'importo totale degli sconti verrà considerata una discrepanza di abbinamento.

| Campo totale    | Totale fattura effettivo | Totale fattura previsto | Percentuale di scostamento | Stato abbinamento |
|----------------|----------------------|------------------------|---------------------|--------------|
| Saldo        | 495,00               | 495,00                 | 0%                  | Superata       |
| Sconto totale | 0,00                 | 9,90                   | 100%                | Non riuscita       |
| Addebiti        | 64,90                | 64,90                  | 0%                  | Superata       |
| IVA      | 139,98               | 137,50                 | 2%                  | Superata       |
| Arrotondamento      | 0,00                 | 0,00                   | 0%                  | Superata       |
| Importo fattura | 699,88               | 687,50                 | 2%                  | Superata       |

L'abbinamento totali fatture è controllato per la persona giuridica da Abbina totali fatture nella pagina dei parametri di contabilità fornitori. L'abbinamento viene effettuato tra i totali fatture previsti e i totali fatture effettivi. I totali fatture previsti vengono calcolati in base alle informazioni su prezzi, spese e IVA dell'ordine fornitore e sulle quantità della fattura.

## <a name="two-way-price-totals-matching"></a>Due elementi di verifica, abbinamento totali dei prezzi
Utilizzare l'abbinamento a due elementi di verifica per assicurarsi che lo scostamento tra le informazioni sul prezzo nell'ordine fornitore e nella fattura rientri nelle tolleranze accettabili. È possibile confrontare le informazioni sul prezzo per l'importo netto di ogni riga fattura, e tutte le righe fattura precedentemente registrate e in sospeso, con l'importo netto della riga ordine fornitore corrispondente. Questo tipo di abbinamento è noto come abbinamento totali dei prezzi. 

L'abbinamento totali dei prezzi può essere basato su una percentuale, un importo oppure una percentuale e un importo. 

Se è specificata una percentuale di tolleranza relativa al totale del prezzo di acquisto, verrà eseguito il confronto tra cinque campi, come illustrato nella tabella riportata di seguito. Poiché la percentuale di tolleranza relativa al totale del prezzo di acquisto è pari al 10%, la percentuale di scostamento relativa al totale dei prezzi pari al 50% rappresenta una discrepanza di abbinamento.

| Stato abbinamento | Importo netto fattura | Importo netto previsto | Totale del prezzo di acquisto non corrispondente (importo scostamento) | Percentuale totale del prezzo di acquisto non corrispondente (percentuale scostamento) | Percentuale di tolleranza del prezzo di acquisto totale |
|--------------|--------------------|---------------------|--------------------------------------------------|-----------------------------------------------------------------|----------------------------------------|
| Superata       | 105,00             | 100,00              | 5,00                                             | 5%                                                              | 10%                                    |
| Non riuscita       | 150,00             | 100,00              | 50,00                                            | 50%                                                             | 10%                                    |

Se è specificato un importo di tolleranza relativo al totale del prezzo di acquisto, verrà eseguito il confronto tra cinque campi, come illustrato nella tabella riportata di seguito. Poiché l'importo di tolleranza relativo al totale del prezzo di acquisto è pari a 100,00, l'importo di scostamento relativo al totale dei prezzi pari a 105,00 rappresenta una discrepanza di abbinamento.

| Stato abbinamento | Importo netto fattura | Importo netto previsto | Totale del prezzo di acquisto non corrispondente (importo scostamento) | Totale del prezzo di acquisto non corrispondente in valuta di contabilizzazione (importo scostamento) | Tolleranza del prezzo di acquisto totale |
|--------------|--------------------|---------------------|--------------------------------------------------|-------------------------------------------------------------------------|--------------------------------|
| Superata       | 150,00             | 100,00              | 50,00                                            | 50,00                                                                   | 100,00                         |
| Non riuscita       | 205,00             | 100,00              | 105,00                                           | 105,00                                                                  | 100,00                         |

Se per l'abbinamento totali dei prezzi vengono impostati una percentuale di tolleranza e un importo di tolleranza, talvolta detto anche importo da non superare, durante la valutazione di una riga per verificare la presenza di una discrepanza di abbinamento, verranno prese in considerazione entrambe le tolleranze. Se, come mostrato nelle righe 150,00 e 205,00 della tabella riportata di seguito, la percentuale o l'importo supera il valore di tolleranza, la riga include una discrepanza di abbinamento.

| Stato abbinamento | Importo netto fattura | Importo netto previsto | Percentuale totale del prezzo di acquisto non corrispondente (percentuale scostamento) | Percentuale di tolleranza del prezzo di acquisto totale | Totale del prezzo di acquisto non corrispondente in valuta di contabilizzazione (importo scostamento) | Tolleranza del prezzo di acquisto totale |
|--------------|--------------------|---------------------|-----------------------------------------------------------------|----------------------------------------|-------------------------------------------------------------------------|--------------------------------|
| Superata       | 105,00             | 100,00              | 5%                                                              | 10%                                    | 5,00                                                                    | 100,00                         |
| Non riuscita       | 150,00             | 100,00              | 50%                                                             | 10%                                    | 50,00                                                                   | 100,00                         |
| Non riuscita       | 205,00             | 100,00              | 105%                                                            | 10%                                    | 105,00                                                                  | 100,00                         |

Criteri di abbinamento a due vie controllati per la persona giuridica dal campo Criteri di abbinamento riga della pagina Parametri contabilità fornitori. A seconda della selezione effettuata nel campo Consenti di ignorare i criteri di abbinamento, nella pagina Criteri di abbinamento è possibile selezionare l'abbinamento a due elementi di verifica per un fornitore, un articolo o una combinazione di articolo e fornitore specifici. Nella pagina Ordine acquisto è possibile selezionare l'abbinamento a due elementi di verifica per un ordine fornitore specifico.

L'abbinamento totali prezzo è controllato per la persona giuridica da Abbina totali prezzo nella pagina dei parametri di contabilità fornitori. In tale pagina vengono inoltre specificati l'importo di tolleranza (importo da non superare) e la percentuale di tolleranza relativi al totale del prezzo di acquisto.

## <a name="two-way-net-unit-price-matching"></a>Due elementi di verifica, abbinamento prezzo unitario netto
Utilizzare l'abbinamento a due elementi di verifica per assicurarsi che lo scostamento tra le informazioni sul prezzo nell'ordine fornitore e nella fattura rientri nelle tolleranze accettabili. È possibile confrontare le informazioni sul prezzo per il prezzo unitario netto di ogni articolo in fattura. Questo tipo di abbinamento è noto come abbinamento prezzo unitario netto. 

Nove importi riga vengono confrontati nella pagina dei dettagli di abbinamento fatture, come illustrato nella seguente tabella. Se la tolleranza di prezzo consentita per l'abbinamento prezzo unitario netto è pari al 10%, la percentuale di scostamento pari al 22,61% per il prezzo unitario netto viene considerata una discrepanza di abbinamento.

| Campo della riga                    | Valore fattura | Valore ordine acquisto | Percentuale di scostamento | Stato abbinamento |
|-------------------------------|---------------|----------------------|---------------------|--------------|
| Prezzo unitario                    | 55,40         | 55,38                | 0%                  | Superata       |
| Unità di prezzo                    | 1,00          | 1,00                 | 0%                  | Superata       |
| Spese su acquisti          | 50,00         | 0,00                 | 100%                | Non riuscita       |
| Sconto                      | 0,00          | 0,00                 | 0%                  | Superata       |
| Percentuale sconto              | 0,00          | 0,00                 | 0%                  | Superata       |
| Sconto plurimo            | 0,00          | 0,00                 | 0%                  | Superata       |
| Percentuale sconto plurimo | 0,00          | 0,00                 | 0%                  | Superata       |
| Importo netto                    | 271,60        | 221,52               | 22,61%              | Non riuscita       |
| Prezzo unitario netto                | 67,9000       | 55,3800              | 22,61%              | Non riuscita       |

Criteri di abbinamento a due vie controllati per la persona giuridica dal campo Criteri di abbinamento riga della pagina Parametri contabilità fornitori. A seconda della selezione effettuata nel campo Consenti di ignorare i criteri di abbinamento, nella pagina Criteri di abbinamento è possibile selezionare l'abbinamento a due elementi di verifica per un fornitore, un articolo o una combinazione di articolo e fornitore specifici. Nella pagina Ordine acquisto è possibile selezionare l'abbinamento a due elementi di verifica per un ordine fornitore specifico. 

L'abbinamento Prezzo unitario netto è controllato per la persona giuridica da Abilita convalida abbinamento fatture nella pagina dei parametri di contabilità fornitori. È possibile configurare le percentuali di tolleranza relative al prezzo unitario netto per articoli, gruppi di articoli, fornitori, gruppi di fornitori, combinazioni di fornitore e articolo oppure per persona giuridica tramite la pagina Tolleranze prezzi.

## <a name="two-way-price-totals-matching-and-net-unit-price-matching"></a>Due elementi di verifica, abbinamento totali dei prezzi e abbinamento prezzo unitario netto
È possibile utilizzare l'abbinamento totali dei prezzi e l'abbinamento prezzo unitario netto insieme. Nell'esempio si presuppone la configurazione indicata di seguito.

-   La tolleranza di prezzo unitario netto per l'articolo Unità USB è pari al 10%.
-   Per la persona giuridica, la tolleranza di abbinamento totali dei prezzi è pari al 15% o a 500,00.

L'ordine fornitore include la riga indicata di seguito.

| Numero articolo | Quantità | Prezzo unitario | Importo netto |
|-------------|----------|------------|------------|
| Unità USB   | 1.000    | 10,00      | 10.000,00  |

Sono state registrate tre fatture, come illustrato nella tabella riportata di seguito. È presente una discrepanza di abbinamento fatture relativa alla fattura 3 poiché lo scostamento di 1.880,00 supera l'importo di tolleranza relativo al totale del prezzo di acquisto di 500,00. Per l'abbinamento totali dei prezzi, l'importo netto della fattura include tutte le fatture registrate in precedenza in aggiunta alla fattura che si sta attualmente utilizzando.

| Numero articolo          | Quantità | Prezzo unitario | Importo netto | Abbinamento prezzi | Abbinamento totale prezzo |
|----------------------|----------|------------|------------|-------------|-------------------|
| Fattura 1: Unità USB | 800      | 10,80      | 8.640,00   | Superata      | Superata            |
| Fattura 2: Unità USB | 100      | 10,80      | 1.080,00   | Superata      | Superata            |
| Fattura 3: Unità USB | 200      | 10,80      | 2.160,00   | Superata      | Non riuscita            |
| Totale                |          |            | 11.880,00  |             |                   |

## <a name="three-way-matching"></a>Criteri di abbinamento a tre elementi di verifica

Utilizzare l'abbinamento a tre elementi di verifica per assicurarsi che lo scostamento tra le informazioni sul prezzo nell'ordine fornitore e nella fattura rientri nelle tolleranze accettabili e per assicurarsi che la quantità della fattura corrisponda alla quantità delle entrate prodotti correlate.

Gli stessi importi riga vengono confrontati nella pagina dei dettagli abbinamento fatture come avviene per l'abbinamento a due elementi di verifica. Inoltre, la quantità della fattura viene abbinata alle quantità di entrata prodotti ricevute. Se la quantità della fattura è diversa dalla quantità di entrata prodotti abbinata, è presente un errore di abbinamento quantità.

| Campo della riga                    | Valore fattura | Valore ordine acquisto | Percentuale di scostamento | Stato abbinamento |
|-------------------------------|---------------|----------------------|---------------------|--------------|
| Prezzo unitario                    | 55,40         | 55,38                | 0%                  | Superata       |
| Unità di prezzo                    | 1,00          | 1,00                 | 0%                  | Superata       |
| Spese su acquisti          | 50,00         | 0,00                 | 100%                | Non riuscita       |
| Sconto                      | 0,00          | 0,00                 | 0%                  | Superata       |
| Percentuale sconto              | 0,00          | 0,00                 | 0%                  | Superata       |
| Sconto plurimo            | 0,00          | 0,00                 | 0%                  | Superata       |
| Percentuale sconto plurimo | 0,00          | 0,00                 | 0%                  | Superata       |
| Importo netto                    | 271,60        | 221,52               | 22,61%              | Non riuscita       |
| Prezzo unitario netto                | 67,9000       | 55,3800              | 22,61%              | Non riuscita       |

| Campo della riga                     | Valore fattura | Stato abbinamento |
|--------------------------------|---------------|--------------|
| Quantità in fattura               | 4,00          |              |
| Totale entrate prodotti associate | 0,00          | Non riuscita       |

Criteri di abbinamento a tre vie controllati per la persona giuridica dal campo Criteri di abbinamento riga della pagina Parametri contabilità fornitori. A seconda della selezione effettuata nel campo Consenti di ignorare i criteri di abbinamento, nella pagina Criteri di abbinamento è possibile selezionare l'abbinamento a tre elementi di verifica per un fornitore, un articolo o una combinazione di articolo e fornitore specifici. Nella pagina Ordine acquisto è possibile selezionare l'abbinamento a due elementi di verifica per un ordine fornitore specifico.

## <a name="charges-matching"></a>Abbinamento spese
È possibile utilizzare l'abbinamento spese per assicurarsi gli importi spese non si discostino dagli importi previsti oltre una percentuale accettabile. Gli importi totali relativi a ogni codice spesa che si applica alla fattura e all'ordine fornitore vengono confrontati nella pagina Confronta valori spese - Fattura, come illustrato nella tabella riportata di seguito. Se la tolleranza consentita per il codice spese è pari al 25%, la percentuale di scostamento 99.999.999.999,99% per il codice spese Licenza viene considerata una discrepanza di abbinamento.

> [!NOTE] 
> Una percentuale di scostamento pari al 99.999.999.999,99% indica che l'importo previsto basato sull'ordine fornitore è pari a zero e l'importo effettivo della fattura corrisponde a un valore positivo. 

| Stato di abbinamento spese | Codice spese fattura | Valore calcolato totale effettivo | Valore calcolato totale previsto | Importo scostamento | Percentuale di scostamento | Percentuale di tolleranza |
|----------------------|----------------------|-------------------------------|---------------------------------|-----------------|---------------------|----------------------|
| Non riuscita               | Licenza              | 25                            | 0                               | 25              | 99.999.999.999,99%  | 25%                  |
| Superata               | Spese di trasporto              | 200                           | 200                             | 0               | 0%                  | 25%                  |
| Non riuscita               | Urgente             | 4                             | 2                               | 2               | 100%                | 25%                  |

L'abbinamento spese è controllato per la persona giuridica da Abbina spese nella pagina dei parametri di contabilità fornitori. È possibile impostare le percentuali di tolleranza scostamento nella pagina Tolleranze spese.

> [!NOTE]
> L'abbinamento spese viene eseguito solo sui codici spese per il quale l'ordine fornitore di confrontare e il cambio di stato operative di valori di fattura è selezionato nella pagina di codice spese.

## <a name="related-functionality"></a>Funzionalità correlate
Anziché sugli ordini fornitore, spesso le fatture fornitore si basano sulle entrate prodotti che rappresentano le spedizioni effettive. Talvolta, gli importi fatturati non corrispondono agli importi degli ordini fornitori e in alcuni casi le quantità spedite non corrispondono alle quantità fatturate. È possibile semplificare la gestione di queste informazioni nei modi indicati di seguito.
-   Creare una fattura fornitore basata sulle entrate prodotti. Le entrate prodotti vengono automaticamente suggerite per le fatture ed è possibile selezionare le entrate prodotti da utilizzare. Se necessario, è inoltre possibile selezionare specifiche voci entrate prodotti relative a più ordini fornitori.
-   Visualizzare e approvare le differenze tra le quantità fatturate della fattura e le quantità ricevute dell'entrata prodotti. Se è presente una differenza, è possibile salvare la fattura e abbinarla successivamente a un'entrata prodotti diversa, oppure modificare la quantità fatturata per adeguarla alla quantità ricevuta.
-   Immettere gli importi fattura che non erano stati inclusi nell'ordine fornitore originale, in modo che le informazioni della fattura corrispondano alla fattura ricevuta dal fornitore. È possibile confrontare le spese per gli ordini fornitore con le spese per le fatture. Se necessario, è possibile aggiungere spese alle fatture e allocarle alle righe fattura.
-   Visualizzare e approvare le eventuali discrepanze di abbinamento tra il prezzo unitario netto in fattura e il prezzo unitario netto nell'ordine fornitore. È possibile impostare le percentuali di tolleranza prezzi per persone giuridiche, fornitori e articoli. Se il prezzo delle righe fattura fornitore non rientra nella tolleranza di prezzo accettabile, è possibile salvare la fattura in attesa che venga approvata per la registrazione o che il fornitore faccia pervenire una rettifica.

Per ulteriori informazioni, vedere [Criteri di abbinamento a tre elementi di verifica](three-way-matching-policies.md) e [Impostare la convalida dell'abbinamento fatture della contabilità fornitori](tasks/set-up-accounts-payable-invoice-matching-validation.md). 





