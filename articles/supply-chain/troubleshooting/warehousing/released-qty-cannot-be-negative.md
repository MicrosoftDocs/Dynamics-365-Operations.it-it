---
title: Impossibile aggiornare una riga di carico perché la quantità rilasciata sarebbe negativa
description: Questo problema si verifica quando l'aggiornamento o l'eliminazione di una riga di carico determina una quantità rilasciata negativa.
author: GalynaFedorova
ms.date: 6/30/2021
ms.topic: troubleshooting
ms.search.form: WHSLoadPlanningListPage_WHSLoadLineUnShipQty,WHSLoadTable_WHSLoadLineUnShipQty,WHSLoadPlanningWorkbench_WHSLoadLineUnShipQty,WHSShipmentDetails_WHSLoadLineUnShipQty,WHSLoadPlanningListPage_DeleteButtonLoadLine,WHSLoadTable_DeleteButtonLoadLine,WHSLoadPlanningWorkbench_DeleteButtonLoadLine,WHSShipmentDetails_DeleteButtonShipment
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-06-30
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: a6325a632e1f68a0a3a9cb6b6091c48da014a405e8ce9ad69ea841f5cceb216f
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6728461"
---
# <a name="cant-update-a-load-line-because-the-released-quantity-would-be-negative"></a>Impossibile aggiornare una riga di carico perché la quantità rilasciata sarebbe negativa

Codice di errore: @WAX:ReleasedQtyCannotBeNegative

## <a name="symptoms"></a>Sintomi

Questo problema si verifica quando l'aggiornamento o l'eliminazione di una riga di carico determina una quantità rilasciata negativa. In questo caso, quando tenti di aggiornare o eliminare la linea di carico, il sistema mostra il seguente messaggio di errore:

> La quantità rilasciata non può essere negativa per l'articolo %1, lotto %2.

Pertanto, non è possibile aggiornare o eliminare la riga di carico.

## <a name="cause"></a>Causa

Dopo aver aggiornato o eliminato una riga di carico, il sistema aggiorna la quantità rilasciata della riga di vendita correlata (*whsSalesLine.ReleaseQty*). Il sistema valuta la quantità rilasciata e, se rileva che la quantità rilasciata della riga sarebbe negativa dopo l'aggiornamento, non consentirà di aggiornare o eliminare la riga. Questa convalida si verifica ogni volta che tenti di aggiornare la quantità della riga di carico o l'unità di misura tramite varie azioni, ad esempio l'eliminazione di una riga di carico, l'eliminazione di una spedizione, la modifica della quantità di una riga di carico, la riduzione della quantità prelevata e il prelievo breve.

La causa principale più comune di questo problema è una modifica nella conversione dell'unità utilizzata per le righe di carico aperte. Ad esempio, la conversione dell'unità quando è stato rilasciato un ordine di vendita era *50 Ea = 1 PL*. Tuttavia, prima che la relativa spedizione del carico fosse finalizzata, la conversione dell'unità è stata modificata in *100 Ea = 1 PL*.

## <a name="resolution"></a>Risoluzione

La soluzione è ripristinare le modifiche alla conversione dell'unità, aggiornare o eliminare la riga di carico e quindi implementare nuovamente la conversione. Devi impedire l'elaborazione di altri carichi che includono l'articolo che ha causato il problema finché il problema non viene risolto. In caso contrario, le nuove conversioni potrebbero essere utilizzate per altri carichi già aperti.

Per risolvere il problema, completare le attività seguenti:

1. Rivedi la conversione dell'unità utilizzata per la riga di carico.
2. Rivedi la conversione dell'unità corrente per l'articolo e apporta le modifiche che consentiranno l'aggiornamento o l'eliminazione della riga di carico.
3. Aggiorna o elimina la riga di carico e ripristina le rettifiche di conversione dell'unità.

### <a name="review-the-unit-conversion-that-was-used-for-the-load-line"></a>Rivedere la conversione dell'unità utilizzata per la riga di carico

Utilizza la seguente procedura per rivedere le righe di carico e prendi nota della conversione dell'unità utilizzata per la riga di carico.

1. Passare a **Gestione magazzino \> Carichi \> Tutti i carichi**.
1. Seleziona il carico che include la riga di carico che non può essere eliminata o aggiornata.
1. Nella scheda **Carichi** del riquadro azioni, nel gruppo **Informazioni correlate**, selezionare **Lavoro**.
1. Nella griglia superiore, seleziona l'ID lavoro pertinente.
1. Nella scheda **Generale** in fondo alla pagina, calcola il tasso di conversione tra il valore **Quantità inventario lavoro** e il valore **Quantità lavoro**. Prendi nota del tasso.
1. Ripeti questa procedura per tutti gli ID lavoro pertinenti per assicurarti che sia stata utilizzata la stessa conversione.

### <a name="review-the-current-unit-conversion-for-the-item-and-make-adjustments"></a>Rivedere la conversione dell'unità corrente per l'articolo e apportare rettifiche

Usa la seguente procedura per rivedere la conversione di unità del prodotto e apportare le rettifiche per garantire che la conversione di unità sia allinea alla riga di carico.

1. Fai clic su **Gestione informazioni sul prodotto \> Prodotti \> Prodotti rilasciati**.
1. Apri il prodotto rilevante per andare alla sua pagina **Prodotto rilasciato**.
1. Nel riquadro azioni, scheda **Prodotto**, nel gruppo **Imposta**, seleziona **Conversioni unità**.
1. Seleziona la conversione tra le unità e apporta le rettifiche utilizzando la conversione che hai trovato nella sezione precedente.

### <a name="update-or-delete-the-load-line-and-revert-the-unit-conversion-adjustments"></a>Aggiornare o eliminare la riga di carico e ripristina le rettifiche di conversione dell'unità

Utilizza la seguente procedura per elaborare la riga di carico come richiesto e ripristinare le conversioni di unità.

1. Passare a **Gestione magazzino \> Carichi \> Tutti i carichi**.
1. Apri il carico che include la riga di carico che non può essere eliminata o aggiornata.
1. Nella scheda dettaglio **Righe di carico** seleziona la riga di carico.
1. Prosegui con le azioni richieste secondo le necessità. (Ad esempio, elimina la riga di carico o modificane la quantità.)
1. Fai clic su **Gestione informazioni sul prodotto \> Prodotti \> Prodotti rilasciati**.
1. Apri il prodotto rilevante per andare alla sua pagina **Prodotto rilasciato**.
1. Nel riquadro azioni, scheda **Prodotto**, nel gruppo **Imposta**, seleziona **Conversioni unità**.
1. Seleziona la conversione tra le unità e ripristina le rettifiche apportate nella sezione precedente.
