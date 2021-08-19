---
title: L'arrotondamento decimale della quantità di aggiornamento fisico non è corretto
description: Quando si genera un documento di trasporto, il carico in uscita contiene una quantità che non corrisponde alla precisione decimale definita nell'unità.
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
ms.openlocfilehash: ddfac7106eb0e8b934516ca10e3950891d10910a2ccdef1868faf25812243159
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6726563"
---
# <a name="decimal-rounding-of-the-physical-updating-quantity-is-incorrect"></a>L'arrotondamento decimale della quantità di aggiornamento fisico non è corretto

Codice errore: SYS19589

## <a name="symptoms"></a>Sintomi

Quando si genera un documento di trasporto, il carico in uscita contiene una quantità che non corrisponde alla precisione decimale definita nell'unità.

Quando si tenta di generare il documento di trasporto, il sistema mostra il seguente messaggio di errore:

> L'arrotondamento decimale della quantità di aggiornamento fisico nell'unità %1 è errato.

Pertanto, non è possibile generare il documento di trasporto per il carico.

## <a name="cause"></a>Causa

Il sistema valuta se l'arrotondamento decimale della quantità di spedizione corrisponde alla precisione decimale definita per l'unità di spedizione. Quando il sistema arrotonda la quantità di spedizione al numero specificato di cifre decimali, se rileva che la quantità di spedizione arrotondata non corrisponde alla quantità di spedizione effettiva, non è possibile generare il documento di trasporto. Ad esempio, questo problema potrebbe verificarsi se la quantità di vendita è 1,75 chilogrammi (kg), ma la precisione decimale è impostata su *1*.

## <a name="resolution"></a>Risoluzione

Il carico o la spedizione si trova attualmente in uno stato in cui la generazione del documento di trasporto non riesce. Per risolvere il problema, completare una o più delle attività seguenti:

- Rivedere le righe di carico e apportare le modifiche per garantire che la quantità possa essere convertita in modo pulito senza numeri decimali e altri problemi di arrotondamento.
- Rivedere le linee di carico e apportare le modifiche per garantire che l'unità e la quantità siano allineate con la precisione decimale dell'unità.

### <a name="review-your-load-lines-and-make-adjustments-to-ensure-that-the-quantity-can-be-cleanly-converted-without-decimal-numbers-and-any-other-rounding-issues"></a>Rivedere le righe di carico e apportare le modifiche per garantire che la quantità possa essere convertita in modo pulito senza numeri decimali e altri problemi di arrotondamento

Usare la seguente procedura per rivedere le righe di carico e apportare le modifiche per garantire che la quantità possa essere convertita in modo pulito senza numeri decimali e altri problemi di arrotondamento.

1. Passare a **Gestione magazzino \> Carichi \> Tutti i carichi**.
1. Seleziona il carico per il quale non è possibile generare il documento di trasporto.
1. Nel riquadro azioni, nella scheda  **Spedisci e ricevi** nel gruppo  **Storna** seleziona  **Storna conferma spedizione**.
1. Nella scheda  **Righe carico** seleziona la riga di carico per l'articolo che causa il problema.
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
