---
title: La quantità fisica residua nell'unità non deve essere zero
description: Quando si genera un documento di trasporto, i dati forniti hanno una quantità di inventario diversa da zero e una quantità di vendita pari a zero.
author: GalynaFedorova
ms.date: 5/31/2021
ms.topic: troubleshooting
ms.search.form: WHSLoadPlanningListPage_WHSSalesPackingSlipPost, WHSLoadTable_WHSSalesPackingSlipPost
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: bfd381160bcfd1e6e5489e16cc22178b8a5142ee
ms.sourcegitcommit: e6437d994c3be0c5bb4a9263af3aa8351020d83a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/14/2021
ms.locfileid: "6248788"
---
# <a name="physical-remaining-quantity-in-the-unit-must-not-be-zero"></a>La quantità fisica residua nell'unità non deve essere zero

Codice errore: SYS19591

## <a name="symptoms"></a>Sintomi

Quando si genera un documento di trasporto, i dati forniti hanno una quantità di inventario diversa da zero e una quantità di vendita pari a zero.

Quando si tenta di generare il documento di trasporto, il sistema mostra il seguente messaggio di errore:

> La quantità fisica rimanente nell'unità %1 deve essere diversa da zero.

Pertanto, non è possibile generare il documento di trasporto per il carico.

## <a name="cause"></a>Causa

Il sistema valuta la quantità fisica rimanente nell'unità di magazzino e la quantità fisica rimanente nell'unità di spedizione. Se il sistema rileva che la quantità fisica rimanente nell'unità di spedizione è 0 (zero), ma la quantità fisica rimanente nell'unità di magazzino non è 0, non è possibile generare il documento di trasporto. Ad esempio, questo problema potrebbe verificarsi se l'unità di vendita e l'unità di magazzino per l'articolo differiscono e la conversione tra le unità non è accurata.

## <a name="resolution"></a>Risoluzione

Il carico o la spedizione si trova attualmente in uno stato in cui la generazione del documento di trasporto non riesce. Per risolvere il problema, completare una o più delle attività seguenti:

- Esamina le righe di carico e assicurati che tutto il lavoro correlato sia stato completato nell'ubicazione di spedizione finale e che le quantità corrispondano.
- Rivedi le righe di carico e apportare le modifiche per garantire che la quantità possa essere convertita in modo pulito senza problemi di arrotondamento.
- Rivedere le linee di carico e apportare le modifiche per garantire che l'unità e la quantità siano allineate con la precisione decimale dell'unità.
- Assicurati che l'unità di misura del magazzino sia inferiore all'unità di misura di vendita.

### <a name="review-your-load-lines-and-make-sure-that-all-the-related-work-has-been-completed-at-the-final-shipping-location-and-that-the-quantities-match"></a>Esaminare le righe di carico e assicurati che tutto il lavoro correlato sia stato completato nell'ubicazione di spedizione finale e che le quantità corrispondano

Usa la seguente procedura per esaminare le righe di carico e assicurati che tutto il lavoro correlato sia stato completato nell'ubicazione di spedizione finale e che le quantità corrispondano.

1. Passare a **Gestione magazzino \> Carichi \> Tutti i carichi**.
1. Seleziona il carico per cui la spedizione non può essere confermata.
1. Nella scheda dettaglio **Righe di carico** seleziona la riga di carico.
1. Prendi nota del valore del campo **Quantità di lavoro creata**.
1. Nella scheda **Carichi** del riquadro azioni, nel gruppo **Informazioni correlate**, selezionare **Lavoro**.
1. Verificare che il lavoro sia stato completato nell'ubicazione di spedizione finale e che la quantità di lavoro prelevata corrisponda alla quantità di lavoro creata sulla riga di carico.
1. Ripetere questa procedura per tutte le righe di carico per assicurarsi che tutti i criteri siano soddisfatti.

### <a name="review-your-load-lines-and-make-adjustments-to-ensure-that-the-quantity-can-be-cleanly-converted-without-rounding-issues"></a>Rivedere le righe di carico e apportare le modifiche per garantire che la quantità possa essere convertita in modo pulito senza problemi di arrotondamento

Usa la seguente procedura per rivedere le righe di carico e apportare le modifiche per garantire che la quantità possa essere convertita in modo pulito senza problemi di arrotondamento.

1. Passare a **Gestione magazzino \> Carichi \> Tutti i carichi**.
1. Seleziona il carico per il quale non è possibile generare il documento di trasporto.
1. Nel riquadro azioni, nella scheda  **Spedisci e ricevi** nel gruppo  **Storna** seleziona  **Storna conferma spedizione**.
1. Nella scheda  **Righe di carico**, seleziona la riga di carico dell'articolo che supera il limite massimo di fornitura.
1. Seleziona **Riduci quantità prelevata** per rettificare la quantità prelevata.
1. Nella scheda  **Dettagli riga** seleziona **Ordine**.
1. Imposta il campo **Quantità** sulla quantità prelevata (ovvero, il valore del campo **Quantità di lavoro creata**), in modo che possa procedere la generazione del documento di trasporto.

### <a name="review-your-load-lines-and-make-adjustments-to-ensure-that-the-unit-and-quantity-are-aligned-with-the-decimal-precision-of-the-unit"></a>Rivedere le linee di carico e apportare le modifiche per garantire che l'unità e la quantità siano allineate con la precisione decimale dell'unità

Usa la seguente procedura per rivedere le linee di carico e apportare le modifiche per garantire che l'unità e la quantità siano allineate con la precisione decimale dell'unità.

1. Passare a **Gestione magazzino \> Carichi \> Tutti i carichi**.
1. Seleziona il carico per il quale non è possibile generare il documento di trasporto.
1. Nella scheda dettaglio **Righe carico** seleziona la riga di carico per l'articolo che causa il problema. Prendi nota del valore dei campi **Quantità** e **Unità**.
1. Vai a **Amministrazione organizzazione \> Unità \> Unità**.
1. Seleziona l'unità per la quale non è possibile generare il documento di trasporto.
1. Rettifica il valore del campo **Precisione decimale** come richiesto.

### <a name="make-sure-that-the-inventory-unit-of-measure-is-smaller-than-the-sales-unit-of-measure"></a>Assicurarsi che l'unità di misura del magazzino sia inferiore all'unità di misura di vendita

Assicurati che l'unità di misura del magazzino sia inferiore all'unità di misura di vendita. Considera la riconfigurazione dell'unità di misura dell'articolo come richiesto.
