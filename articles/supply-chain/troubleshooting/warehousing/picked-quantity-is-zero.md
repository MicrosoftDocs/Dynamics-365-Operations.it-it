---
title: Non è possibile confermare una spedizione perché la quantità è pari a zero
description: Non è possibile confermare una spedizione perché la quantità è pari a zero
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
ms.openlocfilehash: b2f9f8deaca30e318d0393fb1d7911eebf63060ccca83dc6f1de9b04b9e30e11
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6712888"
---
# <a name="you-cant-confirm-a-shipment-because-there-is-zero-quantity"></a>Non è possibile confermare una spedizione perché la quantità è pari a zero

Codice di errore: LoadLineWarningUpdatedToZero

## <a name="symptoms"></a>Sintomi

Quando si tenta di confermare una spedizione, il sistema mostra il seguente messaggio di errore:

> La riga di carico per l'articolo %1 e la spedizione %2 è stata aggiornata in modo da avere una quantità pari a zero a causa dell'impostazione del limite minimo di fornitura che consente di non spedire quantità per questo articolo.

Pertanto, non è possibile confermare la spedizione per il carico.

## <a name="cause"></a>Causa

Il sistema valuta se la quantità prelevata rientra nei limiti previsti, in base alla quantità prelevata, alla quantità della riga di carico e alla percentuale di limite minimo di fornitura. Se il sistema rileva che la quantità prelevata nella riga di carico è 0 (zero), non è possibile confermare la spedizione. Ad esempio, questo problema potrebbe verificarsi se il lavoro è stato annullato e la percentuale di limite minimo di fornitura sulla riga di carico è del 100%.

## <a name="resolution"></a>Risoluzione

Controlla le tue righe di carico per assicurarti che la percentuale e le quantità di limite minimo di fornitura siano allineate al lavoro prelevato.

1. Passare a **Gestione magazzino \> Carichi \> Tutti i carichi**.
1. Seleziona il carico per cui la spedizione non può essere confermata.
1. Nella scheda dettaglio **Righe di carico**, seleziona la riga di carico dell'articolo che supera la percentuale di limite minimo di fornitura.
1. Regola il valore del campo **Limite minimo di fornitura** o il campo **Quantità** come richiesto.

> [!TIP]
> Se il problema persiste, potrebbe essere necessario completare più operazioni di prelievo per gli ordini cliente o di trasferimento correlati fino a quando la quantità disponibile non è allineata al carico o alla spedizione.
