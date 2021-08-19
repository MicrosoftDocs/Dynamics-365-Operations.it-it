---
title: Impossibile confermare una spedizione perché il cliente è in attesa
description: Impossibile confermare una spedizione perché il cliente è in attesa.
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
ms.openlocfilehash: 82b28e7cfd8c88e453cdd09398f5a92f605eab15a17d33defa0b9729a53c05b6
ms.sourcegitcommit: fa5ff2a0822aac16b518a2aea0d3389f79793390
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2021
ms.locfileid: "7012181"
---
# <a name="you-cant-confirm-a-shipment-because-the-customer-is-on-hold"></a>Impossibile confermare una spedizione perché il cliente è in attesa

Codice di errore: WAX:CustomerOnHoldShipmentCannotBeConfirmed

## <a name="symptoms"></a>Sintomi

Quando si tenta di confermare una spedizione, il sistema mostra il seguente messaggio di errore:

> Impossibile confermare la spedizione %1 perché il cliente è in attesa di %2.

Pertanto, non è possibile confermare la spedizione per il carico.

## <a name="cause"></a>Causa

Il conto cliente del carico o della spedizione è in attesa. Pertanto, lo stato del cliente impedisce la conferma della spedizione.

## <a name="resolution"></a>Risoluzione

Utilizza la seguente procedura per sbloccare il conto cliente.

1. Andare a **Contabilità clienti \> Clienti \> Tutti i clienti**.
1. Apri il conto cliente per il quale non è possibile confermare la spedizione.
1. Nella scheda dettaglio **Credito e riscossioni** imposta il campo **Fatturazione e consegna in attesa** su *No*.
1. Ripeti questa procedura per tutti i clienti bloccati per il carico.
