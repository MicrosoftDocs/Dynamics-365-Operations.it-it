---
title: Non puoi confermare una spedizione a causa di un problema con il calendario
description: Non puoi confermare una spedizione a causa di un problema con il calendario
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
ms.openlocfilehash: 8aae45beeef1934760d620874897f46a1cf901995e2b83e148a1d56898d9c717
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6735946"
---
# <a name="you-cant-confirm-a-shipment-because-of-an-issue-with-the-calendar"></a>Non puoi confermare una spedizione a causa di un problema con il calendario

Codice errore: TRX2716

## <a name="symptoms"></a>Sintomi

Quando si tenta di confermare una spedizione, il sistema mostra il seguente messaggio di errore:

> Il tipo di calendario %1 richiede il check-in e il check-out per l'appuntamento %2.

Pertanto, non è possibile confermare la spedizione per il carico.

## <a name="cause"></a>Causa

Esistono appuntamenti attivi per il carico. Ad esempio, esiste una regola che richiede il check-in del conducente. Pertanto il carico si trova attualmente in uno stato in cui la conferma della spedizione non riesce.

## <a name="resolution"></a>Risoluzione

È necessario esaminare e risolvere eventuali problemi con gli appuntamenti attivi collegati al carico.

1. Passare a **Gestione magazzino \> Carichi \> Tutti i carichi**.
1. Seleziona il carico per cui la spedizione non può essere confermata.
1. Nel riquadro azioni, nel gruppo **Appuntamenti** della scheda **Trasporto**, selezionare **Programmazione appuntamenti**.
1. Eseguire uno dei passaggi riportati di seguito.

    - Assicurati che il check-in/check-out del conducente sia completato per l'appuntamento.
    - Completa o annulla l'appuntamento.
    - Disabilita l'opzione **Check-in conducente richiesto** per la regola dell'appuntamento correlato.
