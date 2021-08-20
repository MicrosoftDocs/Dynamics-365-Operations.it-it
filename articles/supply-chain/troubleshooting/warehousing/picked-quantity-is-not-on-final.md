---
title: Non puoi confermare una spedizione perché gli articoli non sono stati prelevati
description: Non puoi confermare una spedizione perché gli articoli non sono stati prelevati
author: perlynne
ms.date: 04/21/2021
ms.topic: troubleshooting
ms.search.form: WHSLoadTable_WHSShipConfirm,WHSLoadPlanningListPage_WHSShipConfirm,WHSLoadPlanningWorkbench_WHSShipConfirm,WHSTransportLoad_WHSShipConfirm,WHSShipPlanningListPage_WHSShipConfirm,WHSShipmentDetails_WHSShipConfirm,WHSWorkTable_WHSShipConfirm,WHSWorkTableListPage_WHSShipConfirm,Dialog_WHSOutboundShipConfirmController_WHSOutboundShipConfirm
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: lbc
ms.search.validFrom: 2021-04-21
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 7b57d3151852c9a2880185b7d9414e4246b7efb6429fcfce04c7cdae4ee00e37
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6760926"
---
# <a name="you-cant-confirm-a-shipment-because-items-havent-been-picked"></a>Non puoi confermare una spedizione perché gli articoli non sono stati prelevati

Codice di errore: LoadNotPickedAndMovedToFinalShippingLocation

## <a name="symptoms"></a>Sintomi

Quando si tenta di confermare una spedizione, il sistema mostra il seguente messaggio di errore:

> Alcuni articoli necessari per il carico %1 non sono stati ancora prelevati e spostati nell'ubicazione di spedizione finale.

Pertanto, non è possibile confermare la spedizione per il carico.

## <a name="cause"></a>Causa

Il carico o la spedizione non possono essere confermati nello stato attuale perché potrebbe sussistere una delle seguenti condizioni:

- Il lavoro correlato non è stato ancora prelevato e spostato nell'ubicazione di spedizione finale.
- La quantità di lavoro prelevata non corrisponde alla quantità di lavoro creata nella riga di carico.
- La direttiva ubicazione è stata configurata con l'ubicazione di imballaggio come ubicazione di spedizione finale durante l'utilizzo della containerizzazione del modello ciclo.

## <a name="resolution"></a>Risoluzione

Il carico o la spedizione si trova attualmente in uno stato in cui la conferma della spedizione non riesce. Per risolvere il problema, completare una o più delle attività seguenti:

- Esamina le righe di carico e assicurati che tutto il lavoro correlato sia stato completato nell'ubicazione di spedizione finale e che le quantità corrispondano.
- Annulla gli ID lavoro che sono stati creati con l'ubicazione di imballaggio come ubicazione di spedizione finale, riconfigura la direttiva ubicazione e rilascia nuovamente il carico.

### <a name="review-your-load-lines-and-make-sure-that-all-the-related-work-has-been-completed-at-the-final-shipping-location-and-that-the-quantities-match"></a>Esamina le righe di carico e assicurati che tutto il lavoro correlato sia stato completato nell'ubicazione di spedizione finale e che le quantità corrispondano

Usa la seguente procedura per esaminare le righe di carico e assicurati che tutto il lavoro correlato sia stato completato nell'ubicazione di spedizione finale e che le quantità corrispondano.

1. Passare a **Gestione magazzino \> Carichi \> Tutti i carichi**.
1. Seleziona il carico per cui la spedizione non può essere confermata.
1. Nella scheda dettaglio **Righe di carico** seleziona la riga di carico.
1. Prendi nota del valore del campo **Quantità di lavoro creata**.
1. Nella scheda **Carichi** del riquadro azioni, nel gruppo **Informazioni correlate**, selezionare **Lavoro**.
1. Verificare che il lavoro sia stato completato nell'ubicazione di spedizione finale e che la quantità di lavoro prelevata corrisponda alla quantità di lavoro creata sulla riga di carico.
1. Ripetere questa procedura per tutte le righe di carico per assicurarsi che tutti i criteri siano soddisfatti.

### <a name="cancel-the-work-ids-that-have-been-created-with-the-packing-location-as-the-final-shipping-location-reconfigure-the-location-directive-and-rerelease-the-load"></a>Annulla gli ID lavoro che sono stati creati con l'ubicazione di imballaggio come ubicazione di spedizione finale, riconfigura la direttiva ubicazione e rilascia nuovamente il carico

Utilizza la seguente procedura per annullare gli ID lavoro che hanno l'ubicazione di imballaggio come ubicazione di stoccaggio finale con la containerizzazione automatizzata in atto.

1. Vai a **Gestione magazzino \> Attività periodiche \> Pulitura \> Annulla lavoro**.
1. Viene visualizzata la finestra di dialogo **Annulla lavoro**. Nel campo **ID lavoro** specificare l'ID del lavoro che si desidera annullare. L'ID lavoro selezionato deve avere un valore **Stato lavoro** di *Aperto*, *In corso*, *Annullato*, *Combinato*, o *Chiuso*.
1. Selezionare **OK**.
1. Seleziona **Sì** per confermare che desideri annullare il lavoro.
1. Ripeti questa procedura per gli altri ID lavoro, se necessario.

Per ulteriori informazioni, vedere [Annullare il lavoro di magazzino per la gestione delle eccezioni](../../warehousing/cancel-warehouse-work.md).

Utilizza la procedura seguente per riconfigurare la direttiva ubicazione in modo che non utilizzi l'ubicazione di imballaggio come ubicazione di spedizione finale quando viene impostata la containerizzazione automatica per il modello ciclo.

1. Vai a **Gestione magazzino \> Impostazioni \> Direttiva ubicazione**.
1. Nel campo **Tipo ordine di lavoro** selezionare *Ordini cliente*.
1. Seleziona la direttiva ubicazione che stai utilizzando per la containerizzazione automatizzata.
1. Nella barra degli strumenti della Scheda dettaglio **Azioni direttiva ubicazione**, seleziona **Modifica query**.
1. Nella finestra di dialogo dell'editor di query, nella scheda **Intervallo**, trova la riga in cui **Campo** è impostato su *Profilo ubicazione*, e verifica che il campo **Criteri** per quella riga non sia impostato su un profilo ubicazione che ha un **Tipo di ubicazione** di *Imballaggio*. Rettifica il campo **Criteri** per correggere l'ubicazione di stoccaggio finale.

Utilizza la seguente procedura per rilasciare nuovamente il carico e creare gli ID lavoro con l'ubicazione di spedizione finale corretta.

1. Vai a **Gestione magazzino \> Carichi \> Workbench pianificazione carico**.
1. Nella sezione **Carichi** trova il carico che deve essere rilasciato.
1. Nella barra degli strumenti della sezione **Carichi** seleziona **Rilascia \> Rilascia in magazzino** per rilasciare il carico selezionato nel magazzino.
1. Ripeti questa procedura per gli altri carichi, se necessario.
