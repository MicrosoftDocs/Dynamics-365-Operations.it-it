---
title: Non è possibile confermare una spedizione a causa di lavoro incompleto o mancante
description: Non è possibile confermare una spedizione a causa di lavoro incompleto o mancante
author: perlynne
ms.date: 04/21/2021
ms.topic: troubleshooting
ms.search.form: WHSLoadTable_WHSShipConfirm,WHSLoadPlanningListPage_WHSShipConfirm,WHSLoadPlanningWorkbench_WHSShipConfirm,WHSTransportLoad_WHSShipConfirm,WHSShipPlanningListPage_WHSShipConfirm,WHSShipmentDetails_WHSShipConfirm,WHSWorkTable_WHSShipConfirm,WHSWorkTableListPage_WHSShipConfirm,Dialog_WHSOutboundShipConfirmController_WHSOutboundShipConfirm, WHSContainerCloseDiag_WHSShipConfirm
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: lbc
ms.search.validFrom: 2021-04-21
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: beef0909d41e69f3e7bcc1021527be35b7e6fd44
ms.sourcegitcommit: c2c6d687a89bc1534c029109315c23e92865b63b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/31/2021
ms.locfileid: "6123845"
---
# <a name="you-cant-confirm-a-shipment-because-of-incomplete-or-missing-work"></a>Non è possibile confermare una spedizione a causa di lavoro incompleto o mancante

Codice errore: WAX515

## <a name="symptoms"></a>Sintomi

Quando si tenta di confermare una spedizione, il sistema mostra il seguente messaggio di errore:

> Impossibile confermare la spedizione per il carico %1 perché tutto il lavoro per il carico deve essere completato.

Pertanto, non è possibile confermare la spedizione per il carico.

## <a name="cause"></a>Causa

Il carico o la spedizione si trova attualmente in uno stato in cui la conferma della spedizione non riesce. Prima di poter confermare la spedizione, deve esistere almeno del lavoro per il carico e tutto quel lavoro deve avere uno stato di *Chiuso* o *Annullato*.

## <a name="resolution"></a>Risoluzione

Controllare gli ordini cliente o gli ordini di trasferimento correlati per il carico o la spedizione e assicurarsi che tutto il lavoro correlato sia stato completato o annullato.

Puoi lavorare con spedizioni e carichi su più pagine. Le seguenti sottosezioni forniscono alcuni esempi.

### <a name="all-loads-page"></a>Pagina Tutti i carichi

1. Passare a **Gestione magazzino \> Carichi \> Tutti i carichi**.
1. Seleziona il carico per cui la spedizione non può essere confermata.
1. Nella scheda **Carichi** del riquadro azioni, nel gruppo **Informazioni correlate**, selezionare **Lavoro**.
1. Controlla lo stato di ogni ID lavoro. Esegui il follow-up su ogni ID lavoro che non ha uno stato di *Chiuso* o *Annullato*.
1. Quando ogni ID lavoro ha uno stato di *Chiuso* o *Annullato*, riprova per confermare la spedizione.

### <a name="all-shipments-page"></a>Pagina Tutte le spedizioni

1. Vai a **Gestione magazzino \> Spedizioni \> Tutte le spedizioni**.
1. Seleziona la spedizione che non può essere confermata.
1. Nella scheda **Spedizioni** del riquadro azioni, nel gruppo **Lavoro**, selezionare **Dettagli lavoro**.
1. Controlla lo stato di ogni ID lavoro. Esegui il follow-up su ogni ID lavoro che non ha uno stato di *Chiuso* o *Annullato*.
1. Quando ogni ID lavoro ha uno stato di *Chiuso* o *Annullato*, riprova per confermare la spedizione.

### <a name="all-work-page"></a>Pagina Tutti i lavori

1. Vai a **Gestione magazzino \> Lavoro \> Tutti i lavori**.
1. Seleziona il lavoro per il numero d'ordine per cui la spedizione non può essere confermata.
1. Nel riquadro azioni, nella scheda **Spedizione**, nel gruppo **Spedizione** selezionare **Conferma spedizione**.
1. Controlla lo stato di ogni ID lavoro. Esegui il follow-up su ogni ID lavoro che non ha uno stato di *Chiuso* o *Annullato*.
1. Quando ogni ID lavoro ha uno stato di *Chiuso* o *Annullato*, riprova per confermare la spedizione.
