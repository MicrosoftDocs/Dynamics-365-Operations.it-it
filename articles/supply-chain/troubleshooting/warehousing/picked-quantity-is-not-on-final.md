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
ms.openlocfilehash: 23a517e7769dc86ebec30e4f17c62172a6ad8801
ms.sourcegitcommit: cd9016e9787169cb800889d335b9c5919ddbe4af
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2021
ms.locfileid: "5938497"
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

## <a name="resolution"></a>Risoluzione

Controllare i relativi ordini cliente o ordini di trasferimento per il carico o la spedizione. Assicurati che tutto il lavoro correlato sia stato completato nell'ubicazione di spedizione finale e che le quantità corrispondano.

1. Passare a **Gestione magazzino \> Carichi \> Tutti i carichi**.
1. Seleziona il carico per cui la spedizione non può essere confermata.
1. Nella scheda dettaglio **Righe di carico** seleziona la riga di carico.
1. Prendi nota del valore del campo **Quantità di lavoro creata**.
1. Nella scheda **Carichi** del riquadro azioni, nel gruppo **Informazioni correlate**, selezionare **Lavoro**.
1. Verificare che il lavoro sia stato completato nell'ubicazione di spedizione finale e che la quantità di lavoro prelevata corrisponda alla quantità di lavoro creata sulla riga di carico.
1. Ripetere questa procedura per tutte le righe di carico per assicurarsi che tutti i criteri siano soddisfatti.
