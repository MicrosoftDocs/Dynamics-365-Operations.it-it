---
title: Media mobile
description: La media mobile è un metodo di determinazione dei costi soggetti a variazioni basato sul principio della media, in cui i costi delle uscite di magazzino non cambiano quando cambia il costo di acquisto. La differenza viene capitalizzata e basata su un calcolo proporzionale. L'importo che rimane viene calcolato come spesa.
author: AndersGirke
ms.date: 08/28/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventModelGroup
audience: Application User
ms.reviewer: kamaybac
ms.custom: 65531
ms.assetid: dfd10099-8f7f-44b1-917e-df37c2fe8773
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: aevengir
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6721c01fd0ad3eec30de99dee3b5e98de6bd3b52
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/29/2021
ms.locfileid: "7567537"
---
# <a name="moving-average"></a>Media mobile

[!include [banner](../includes/banner.md)]

La media mobile è un metodo di determinazione dei costi soggetti a variazioni basato sul principio della media, in cui i costi delle uscite di magazzino non cambiano quando cambia il costo di acquisto. La differenza viene capitalizzata e basata su un calcolo proporzionale. L'importo che rimane viene calcolato come spesa.

Quando si utilizza la media mobile, non sono supportati le liquidazioni magazzino e il contrassegno scorte. La chiusura dell'inventario non influisce sui prodotti che dispongono di media mobile come il gruppo di modelli inventariali e non genera alcuni accordi tra le transazioni.

Di seguito sono riportati i prerequisiti di quando si utilizza il costo a media mobile come metodo di determinazione dei costi.

1. Nella pagina **Gruppi di modelli di articoli** impostare un gruppo di modelli di articoli con la **media mobile** selezionata nel campo **Modello inventariale**.

    > [!NOTE]
    > Per impostazione predefinita, quando la **media mobile** è selezionata, sono selezionati anche i campi **Registra inventario fisico** e **Registra inventario finanziario**.

1. Nella pagina **Registrazione** assegnare i conti a **Differenza di prezzo per media mobile**. Il conto **Differenza di prezzo per media mobile** viene utilizzato quando il costo è speso in modo proporzionale. Ciò si verifica nei seguenti due scenari:
    - C'è una differenza di costo tra il ricevimento dell'ordine fornitore e l'emissione della fattura di acquisto e c'è una differenza tra la quantità originale del magazzino e la quantità disponibile al momento.
    - Le transazioni portano l'inventario da negativo a zero e c'è una differenza tra il costo della transazione e il costo della media mobile corrente.

1. Nella pagina **Registrazione**, assegnare i conti **Rivalutazione costo per media mobile** nella scheda **Inventario**. Il conto **Rivalutazione costo per media mobile** viene utilizzato quando si desidera rettificare il costo della media mobile per un prodotto su un nuovo prezzo unitario.

1. Nel modulo **Prodotti rilasciati** assegnare il gruppo di modelli articolo con media mobile al prodotto.

    > [!NOTE]
    > Il processo di chiusura dell'inventario chiude solo il periodo di conteggio. Non influisce sui prodotti che hanno una media mobile assegnata loro come gruppo di modelli articolo.

## <a name="convert-to-the-moving-average-costing-method"></a>Conversione al metodo di determinazione dei costi a media mobile

I prodotti possono essere convertiti per utilizzare il metodo di valutazione magazzino a media mobile. Questo tipo di conversione viene in genere eseguita a chiusura d'anno, dopo la chiusura dell'ultimo giorno dell'anno corrente. Viene eseguito utilizzando il modello di determinazione dei costi corrente del prodotto. È possibile modificare il metodo di determinazione costi di magazzino da un metodo basato sul costo medio o costo standard a un metodo basato su media mobile.

Se si modifica il metodo di determinazione costi da un metodo basato su costi standard a un metodo a media mobile, è necessario completare le seguenti attività:

1. Eseguire le rettifiche per ridurre le quantità e i valori di magazzino a 0 (zero).
1. Dopo che la quantità e il valore di magazzino corrispondono a 0 (zero), spostare il gruppo di modelli articolo alla media mobile.
1. Eseguire le rettifiche per reinserire le quantità e i valori nuovamente nel magazzino.

Non è possibile modificare il metodo di determinazione costi di magazzino da un metodo a media mobile a un metodo FIFO (First In, First Out), LIFO (Last In, First Out) o a media ponderata.

> [!NOTE]
> La conversione dal costo standard a una media ponderata mobile è un processo manuale.

Gli esempi riportati di seguito illustrano l'effetto del metodo di determinazione dei costi a media mobile. Sono disponibili quattro configurazioni:

- Ordine fornitore e differenza di costo convertita in spesa in maniera proporzionale.
- Rettifica del prodotto e magazzino a media mobile
- Media mobile con produzione
- Media mobile con una transazione retrodatata

## <a name="purchase-order-and-proportionally-expensed-cost-difference"></a>Ordine fornitore e differenza di costo convertita in spesa in maniera proporzionale.

Con la media mobile, il costo del prodotto viene determinato dal ricevimento dell'acquisto. Quando si registra la fattura di acquisto, se esiste una differenza di costo tra il ricevimento dell'acquisto e la fattura di acquisto, la differenza viene rettificata in maniera proporzionale ai prodotti attualmente in magazzino e qualsiasi importo rimanente viene creato come spesa.

In questo esempio, è stato creato un ordine fornitore e ricevuto a un determinato costo e la fattura di acquisto è registrata con un costo diverso.

1. Creare un ordine fornitore per una quantità pari a 2 e un prezzo unitario di 10,00.
1. Creare una ricevuta di acquisto del prodotto.
1. Creare un ordine cliente per una quantità pari a 1 e un prezzo unitario di 10,00.
1. Creare una fattura di acquisto per una quantità pari a 2 e un prezzo unitario di 12,00.

La differenza nel prezzo unitario, 2,00, viene registrata al conto Differenza di prezzo per media mobile al momento della registrazione della fattura di acquisto. Il motivo è che i due prodotti sono stati acquistati per un costo di 20,00. Uno dei prodotti è stato venduto per un prezzo unitario di 10,00. La fattura di acquisto è stata registrata con un prezzo unitario di 12,,00 e una quantità pari a 2. Il prezzo unitario del prodotto non può essere registrato a 14,00.

## <a name="moving-average-product-and-inventory-adjustment"></a>Rettifica del prodotto e magazzino a media mobile

Se è necessario rettificare il costo a media mobile di un prodotto, le rettifiche magazzino sono consentite a partire dalla data odierna. Non è consentita la retrodatazione di una rettifica magazzino per correggere il costo a media mobile di un prodotto. Non è possibile trasmettere il costo su transazioni successive.

In questo esempio, verrà rettificato il costo a media mobile per un prodotto.

1. Selezionare il prodotto per il quale si desidera rettificare la media mobile. 

 > [!NOTE]
 > Nella pagina **Rivalutazione per media mobile** vengono esaminate le scorte disponibili per un prodotto. Il prodotto selezionato ha una quantità registrata di 1, un valore registrato di 12,00, un costo unitario registrato di 12,00 e un costo unitario di 12,00.
    
1. Aggiornare il campo **Costo unitario** su 16,00. il sistema calcola i campi rimanenti.
1. La rettifica viene registrata.

> [!NOTE]
> È possibile modificare solo il costo a media mobile a partire dalla data odierna.

Nella pagina **Liquidazioni per giustificativo** è possibile visualizzare una rettifica di 4,00 registrati nel conto Rivalutazione costo per la media mobile.

## <a name="moving-average-with-production"></a>Media mobile con produzione

La media mobile supporta gli articoli prodotti. Se si prevede di utilizzare la media mobile in un ambiente di produzione, selezionare **Utilizza prezzo di costo stimato** nella pagina **Parametri di controllo produzione**. Ciò significa che il prezzo di costo che viene calcolato durante la stima viene utilizzato invece del prezzo di costo del calcolo DBA.

## <a name="moving-average-with-a-backdated-transaction"></a>Media mobile con una transazione retrodatata

Le transazioni retrodatate sono assegnate al costo a media mobile corrente e la quantità fisica del prodotto viene aggiornata, ma il costo a media mobile prodotto rimane invariato. In questo esempio con media mobile, viene registrata una transazione retrodatata per un prodotto a media mobile.

1. Creare una rettifica magazzino per il prodotto a media mobile per una quantità pari a 1 e un costo di 20,00.
1. Lo storico transazioni di magazzino per il prodotto sarà simile a:
    - Una transazione di magazzino di 1, un costo di 16,00, una data di registrazione al 15 gennaio e di transazione al 15 gennaio.
    - Una rettifica magazzino di 1, un costo di 20,00, una data di registrazione al 1 gennaio e di transazione al 15 gennaio.
1. Registrare la rettifica.

Nel modulo **Operazioni di magazzino** è possibile notare che 4,00, convertito in spesa come media mobile corrente per il prodotto, corrisponde a 16,00. È possibile registrare nel passato, ma la differenza di costo viene convertita in spesa, in modo tale da non influenzare il costo a media mobile.

## <a name="negative-inventory-balances"></a>Saldi di magazzino negativi

Le transazioni vengono gestite in modo diverso a seconda che la nuova quantità disponibile dopo la transazione sia negativa, zero o positiva.

### <a name="new-balance-is-negative-or-zero"></a>Il nuovo saldo è negativo o zero

Se la nuova quantità disponibile è negativa o zero, la transazione viene preventivata in base ai costi medi correnti. Se c'è una differenza tra il prezzo di acquisto e i costi medi correnti, viene registrata in **Differenza di prezzo per media mobile**.

### <a name="new-balance-is-positive"></a>Il nuovo saldo è positivo

Se la nuova quantità disponibile è positiva dopo la transazione, la transazione viene suddivisa in due parti e preventivata diversamente, come riepilogato nella tabella seguente.

| Parte | Descrizione |
|---|---|
| Quantità da negativo a zero | L'inventario utilizza il costo medio mobile corrente dell'articolo anziché il costo di transazione per quella parte della quantità in entrata che aumenta il saldo disponibile da negativo a zero. La differenza tra il costo della transazione e il costo della media mobile corrente viene registrata in **Differenza di prezzo per media mobile**. |
| Quantità da zero a positiva | L'inventario utilizza il costo della transazione per quella parte della quantità in entrata che aumenta il saldo disponibile da zero a positivo.                                                  |

## <a name="inventory-value-report"></a>Report valori di inventario

In questo esempio di media mobile, il report del valore di magazzino viene stampato per supportare il calcolo corrente della media mobile per un prodotto. Il report Valore di magazzino può stampare le transazioni in ordine cronologico, insieme al costo per supportare il calcolo del costo a media mobile di un prodotto. Il report visualizza il costo a media mobile per il prodotto. Nella finestra di dialogo **Report valore di magazzino** un intervallo di date consente di selezionare l'ora **della transazione** e **della registrazione** in base a cui ordinare il report. L'opzione **Data di registrazione** consente di definire il modo in cui il report viene in genere stampato. L'opzione **Ora della transazione** è la data effettiva in cui la transazione viene dichiarata e il costo a media mobile per il prodotto viene aggiornato. È possibile stampare il report Valore di magazzino tramite l'opzione **Ora della transazione** se si desidera visualizzare il calcolo dei costi a media mobile nel tempo. Nella seguente tabella vengono visualizzate le transazioni per il prodotto stampato nel report quando si utilizza l'opzione di ordinamento **Ora della transazione**.

| Ora della transazione | Data         | Tipo di transazione           | Quantità | Importo | Costo unitario medio |
|------------------|--------------|----------------------------|----------|--------|-------------------|
|                  | 1 ottobre    | Saldo iniziale          | 0        | 0,00   | 0,00              |
| 8 ottobre        | 28 settembre | Entrata retrodatata          | 1        | 16,00  | 16,00             |
| 3 ottobre        | 3 ottobre    | Entrata acquisti           | 2        | 20,00  | 12,00             |
| 5 ottobre        | 5 ottobre    | ordine cliente                | -1       | -10.00 | 13,00             |
| 7 ottobre        | 7 ottobre    | Fattura acquisto           |          | 2,00   | 14,00             |
| 8 ottobre        | 8 ottobre    | Rivalutazione media mobile |          | 4.00   | 16.00             |
|                  | 31 ottobre   | Totale                      | 2        | 32.00  | 16.00             |

> [!NOTE]
> Non è possibile riconciliare la contabilità generale con il magazzino utilizzando l'opzione di ordinamento **Ora della transazione**. Il report deve essere stampato utilizzando l'opzione **Data di registrazione** .


[!INCLUDE[footer-include](../../includes/footer-banner.md)]