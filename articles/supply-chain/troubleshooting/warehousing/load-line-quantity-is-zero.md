---
title: Impossibile confermare una spedizione perché la quantità delle righe di carico è pari a zero
description: Impossibile confermare una spedizione perché la quantità delle righe di carico è pari a zero.
author: GalynaFedorova
ms.date: 07/30/2021
ms.topic: troubleshooting
ms.search.form: WHSLoadTable_WHSShipConfirm,WHSLoadPlanningListPage_WHSShipConfirm,WHSLoadPlanningWorkbench_WHSShipConfirm,WHSTransportLoad_WHSShipConfirm,WHSShipPlanningListPage_WHSShipConfirm,WHSShipmentDetails_WHSShipConfirm,WHSWorkTable_WHSShipConfirm,WHSWorkTableListPage_WHSShipConfirm,Dialog_WHSOutboundShipConfirmController_WHSOutboundShipConfirm
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-07-30
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 15aa7f5e72ff8f2c027b5b020a23328978aa02b0
ms.sourcegitcommit: b9c2798aa994e1526d1c50726f807e6335885e1a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/13/2021
ms.locfileid: "7344236"
---
# <a name="you-cant-confirm-a-shipment-because-load-lines-have-zero-quantity"></a>Impossibile confermare una spedizione perché la quantità delle righe di carico è pari a zero

Codice di errore: WAX:LoadTableWarningAllLinesZero, WAX2543

## <a name="symptoms"></a>Sintomi

Quando si tenta di confermare una spedizione, il sistema mostra il seguente messaggio di errore:

> Tutte le righe del carico %1 hanno una quantità pari a zero.  
> Impossibile confermare la spedizione per il carico %1.

Pertanto, non è possibile confermare la spedizione per il carico.

## <a name="cause"></a>Causa

Il sistema valuta se la riga di carico può essere confermata per la spedizione, in base agli ID lavoro creati, alla quantità della riga di carico e alla percentuale del limite minimo di fornitura. Se il sistema rileva che non sono presenti ID lavoro e se la percentuale del limite minimo di fornitura è impostata su 100%, non è possibile confermare la spedizione.

Ad esempio, questo problema può verificarsi se il lavoro è stato annullato e la percentuale di limite minimo di fornitura sulla riga di carico è del 100%.

## <a name="resolution"></a>Risoluzione

Il carico o la spedizione si trova attualmente in uno stato in cui la conferma della spedizione non riesce. Per risolvere il problema, completare una o più delle attività seguenti:

- Esamina le righe di carico e assicurati che tutto il lavoro correlato sia stato completato nell'ubicazione di spedizione finale e che le quantità corrispondano.
- Esamina le tue righe di carico per assicurarti che la percentuale e le quantità di limite minimo di fornitura siano allineate al lavoro prelevato.

### <a name="review-your-load-lines-to-make-sure-that-all-the-related-work-has-been-completed-at-the-final-shipping-location-and-that-the-quantities-match"></a>Esamina le righe di carico e assicurati che tutto il lavoro correlato sia stato completato nell'ubicazione di spedizione finale e che le quantità corrispondano

Usa la seguente procedura per esaminare le righe di carico e assicurati che tutto il lavoro correlato sia stato completato nell'ubicazione di spedizione finale e che le quantità corrispondano.

1. Passare a **Gestione magazzino \> Carichi \> Tutti i carichi**.
1. Apri il carico per cui la spedizione non può essere confermata.
1. Nella scheda dettaglio **Righe di carico** seleziona la riga di carico.
1. Prendi nota del valore del campo **Quantità di lavoro creata**.
1. Nella scheda **Carichi** del riquadro azioni, nel gruppo **Informazioni correlate**, selezionare **Lavoro**.
1. Verificare che il lavoro sia stato completato nell'ubicazione di spedizione finale e che la quantità di lavoro prelevata corrisponda alla quantità di lavoro creata sulla riga di carico.
1. Se trovi una mancata corrispondenza, annulla il lavoro pertinente, riconfigura la direttiva di posizione e rilascia nuovamente il carico. Per istruzioni, vedi [Impossibile confermare una spedizione perché gli articoli non sono stati prelevati](picked-quantity-is-not-on-final.md).
1. Ripetere questa procedura per tutte le righe di carico per assicurarsi che tutti i criteri siano soddisfatti.

### <a name="review-your-load-lines-to-make-sure-that-the-underdelivery-percentage-and-quantities-are-aligned-with-the-picked-work"></a>Esamina le tue righe di carico per assicurarti che la percentuale e le quantità di limite minimo di fornitura siano allineate al lavoro prelevato

Usa la seguente procedura per esaminare le tue righe di carico per assicurarti che la percentuale e le quantità di limite minimo di fornitura siano allineate al lavoro prelevato.

1. Passare a **Gestione magazzino \> Carichi \> Tutti i carichi**.
1. Apri il carico per cui la spedizione non può essere confermata.
1. Nella scheda dettaglio **Righe di carico**, seleziona la riga di carico dell'articolo che supera la percentuale di limite minimo di fornitura.
1. Regola il valore del campo **Limite minimo di fornitura** o il campo **Quantità** come richiesto.

> [!TIP]
> Se il problema persiste, potrebbe essere necessario completare più operazioni di prelievo per gli ordini cliente o di trasferimento correlati fino a quando la quantità disponibile non è allineata al carico o alla spedizione.
