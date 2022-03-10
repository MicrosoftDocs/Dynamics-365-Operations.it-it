---
title: La quantità che stai tentando di aggiornare supera la quantità ricevuta/consegnata.
description: Quando si genera un documento di trasporto, il carico in uscita contiene una quantità che supera la quantità di lavoro prelevata e prenotata per l'ordine cliente.
author: GalynaFedorova
ms.date: 5/31/2021
ms.topic: troubleshooting
ms.search.form: WHSLoadTable_WHSSalesPackingSlipPost,WHSLoadPlanningListPage_WHSSalesPackingSlipPost,WHSLoadPlanningWorkbench_WHSSalesPackingSlipPost
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: ec5e0ac8dd097e5ebf016683fc5c17df7ecb2305
ms.sourcegitcommit: 008779c530798f563fe216810d34b2d56f2c8d3c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/14/2021
ms.locfileid: "7920400"
---
# <a name="quantity-that-youre-trying-to-update-exceeds-the-receiveddelivered-quantity"></a>La quantità che stai tentando di aggiornare supera la quantità ricevuta/consegnata

Codice errore: SYS7676

## <a name="symptoms"></a>Sintomi

Quando si genera un documento di trasporto, il carico in uscita contiene una quantità che supera la quantità di lavoro prelevata e prenotata per l'ordine cliente.

Quando si tenta di generare il documento di trasporto, il sistema mostra il seguente messaggio di errore:

> La quantità che si sta tentando di aggiornare supera quella ricevuta/consegnata.

Pertanto, non è possibile generare il documento di trasporto per il carico.

## <a name="cause"></a>Causa

La quantità di lavoro prelevata non corrisponde alla quantità di lavoro creata nella riga di carico. Ad esempio, questo problema potrebbe verificarsi se la quantità della riga di carico, la quantità creata dal lavoro o la quantità prelevata non è accurata.

## <a name="resolution"></a>Risoluzione

Il carico o la spedizione si trova attualmente in uno stato in cui la generazione del documento di trasporto non riesce. Per risolvere il problema, completare una o più delle attività seguenti:

- Esamina le righe di carico e assicurati che tutto il lavoro correlato sia stato completato nell'ubicazione di spedizione finale e che le quantità corrispondano.
- Rettifica la quantità della riga di carico.
- Storna tutte le registrazioni di prelievo e ripeti il prelievo.

### <a name="review-your-load-lines-and-make-sure-that-all-the-related-work-has-been-completed-at-the-final-shipping-location-and-that-the-quantities-match"></a>Esaminare le righe di carico e assicurati che tutto il lavoro correlato sia stato completato nell'ubicazione di spedizione finale e che le quantità corrispondano

Usa la seguente procedura per esaminare le righe di carico e assicurati che tutto il lavoro correlato sia stato completato nell'ubicazione di spedizione finale e che le quantità corrispondano.

1. Passare a **Gestione magazzino \> Carichi \> Tutti i carichi**.
1. Seleziona il carico per cui la spedizione non può essere generata.
1. Nella scheda dettaglio **Righe di carico** seleziona la riga di carico.
1. Prendi nota del valore del campo **Quantità di lavoro creata**.
1. Nella scheda **Carichi** del riquadro azioni, nel gruppo **Informazioni correlate**, selezionare **Lavoro**.
1. Verificare che il lavoro sia stato completato nell'ubicazione di spedizione finale e che la quantità di lavoro prelevata corrisponda alla quantità di lavoro creata sulla riga di carico.
1. Ripetere questa procedura per tutte le righe di carico per assicurarsi che tutti i criteri siano soddisfatti.

### <a name="adjust-the-load-line-quantity"></a>Rettifica la quantità della riga di carico

Utilizza la seguente procedura per rettificare la quantità della riga di carico.

1. Passare a **Gestione magazzino \> Carichi \> Tutti i carichi**.
1. Seleziona il carico per il quale non è possibile generare il documento di trasporto.
1. Nel riquadro azioni, nella scheda **Spedisci e ricevi** nel gruppo **Storna** seleziona **Storna conferma spedizione**.
1. Nella scheda **Righe carico** seleziona la riga di carico per l'articolo che causa il problema.
1. Seleziona **Riduci quantità prelevata** per rettificare la quantità prelevata.
1. Imposta il campo **Riduci riga di carico** per riflettere le rettifiche sulla riga di carico.

### <a name="reverse-all-pick-registrations-and-redo-picking"></a>Storna tutte le registrazioni di prelievo e ripeti il prelievo

Se qualcuno ha utilizzato la registrazione del prelievo per chiudere una riga di carico senza lavoro, può verificarsi una discrepanza tra la quantità della riga di carico e la quantità prelevata. In questo caso, è necessario stornare la registrazione del prelievo manuale e completare il prelievo utilizzando l'app per dispositivi mobili Warehouse Management.

Utilizza la seguente procedura per stornare la registrazione del prelievo.

1. Vai a **Contabilità clienti \> Ordini \> Tutti gli ordini**.
1. Selezionare l'ordine cliente per il quale non è possibile registrare un documento di trasporto per il carico.
1. Nella scheda **Righe ordine cliente** seleziona la riga dell'ordine cliente per cui è stata eseguita la registrazione del prelievo.
1. Seleziona **Aggiorna riga \> Prelievo** per annullare il prelievo degli articoli.
