---
title: Non puoi confermare una spedizione perché la quantità supera la percentuale di limite minimo di fornitura
description: Non puoi confermare una spedizione perché la quantità supera la percentuale di limite minimo di fornitura
author: perlynne
ms.date: 04/21/2021
ms.topic: troubleshooting
ms.search.form: WHSLoadTable_WHSShipConfirm,WHSLoadPlanningListPage_WHSShipConfirm,WHSLoadPlanningWorkbench_WHSShipConfirm,WHSTransportLoad_WHSShipConfirm,WHSShipPlanningListPage_WHSShipConfirm,WHSShipmentDetails_WHSShipConfirm,WHSWorkTable_WHSShipConfirm,WHSWorkTableListPage_WHSShipConfirm,Dialog_WHSOutboundShipConfirmController_WHSOutboundShipConfirm,WHSContainerCloseDiag_WHSShipConfirm
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: lbc
ms.search.validFrom: 2021-04-21
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: a6a5b1140d1bc5d09a1bc582fb1d2ac9446fae0920cbb9957797dbdea4c684e6
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6760324"
---
# <a name="you-cant-confirm-a-shipment-because-the-quantity-exceeds-the-underdelivery-percentage"></a>Non puoi confermare una spedizione perché la quantità supera la percentuale di limite minimo di fornitura

Codice errore: WAX1686

## <a name="symptoms"></a>Sintomi

Quando si tenta di confermare una spedizione, il sistema mostra il seguente messaggio di errore:

> La spedizione per il carico %1 non è stata confermata perché la quantità dell'articolo %2 supera la percentuale definita per il limite minimo di fornitura.

Pertanto, non è possibile confermare la spedizione per il carico.

## <a name="cause"></a>Causa

La quantità del carico o della spedizione è stata prelevata solo parzialmente. La quantità è attualmente inferiore alla quantità prelevata di una percentuale che non rientra nella percentuale consentita di limite minimo di fornitura.

## <a name="resolution"></a>Risoluzione

Per risolvere il problema, completare una o più delle attività seguenti:

- Imposta la quantità della riga di carico.
- Imposta la percentuale di limite minimo di fornitura.

### <a name="set-the-load-line-quantity"></a>Impostare la quantità della riga di carico

Per impostare la quantità della riga di carico, segui questi passaggi.

1. Passare a **Gestione magazzino \> Carichi \> Tutti i carichi**.
1. Seleziona il carico per cui la spedizione non può essere confermata.
1. Nella scheda dettaglio **Righe di carico**, seleziona la riga di carico dell'articolo che supera la percentuale di limite minimo di fornitura.
1. Nella Scheda dettaglio **Dettagli riga** seleziona **Ordine**.
1. Nel campo **Quantità** impostare il valore sulla quantità prelevata (ovvero, il valore **Quantità di lavoro creata**), in modo che possa verificarsi la conferma della spedizione.

### <a name="set-the-underdelivery-percentage"></a>Impostare la percentuale di limite minimo di fornitura

Per impostare il limite minimo di fornitura, segui questi passaggi.

1. Passare a **Gestione magazzino \> Carichi \> Tutti i carichi**.
1. Seleziona il carico per cui la spedizione non può essere confermata.
1. Nella scheda dettaglio **Righe di carico**, seleziona la riga di carico dell'articolo che supera la percentuale di limite minimo di fornitura.
1. Nella Scheda dettaglio **Dettagli riga** seleziona **Generale**.
1. Nel campo **Limite minimo di fornitura** impostare il valore su una percentuale maggiore che tiene conto della quantità prelevata rispetto alla quantità di carico, in modo che possa verificarsi la conferma della spedizione.
