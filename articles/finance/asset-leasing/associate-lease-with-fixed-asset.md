---
title: Associare cespiti a leasing
description: L'argomento spiega come associare un cespite esistente a un nuovo leasing.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations, Retail
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: d627633e43c2e6f5cad90dfe4100ff95a71541f7
ms.sourcegitcommit: aeee39c01d3f93a6dfcf2013965fa975a740596a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/28/2020
ms.locfileid: "4444989"
---
# <a name="associate-fixed-assets-with-leases"></a>Associare cespiti a leasing

[!include [banner](../includes/banner.md)]

L'argomento spiega come associare un cespite esistente a un nuovo leasing. Quando si associa un cespite a un leasing, il valore dell'Asset Right of use al riconoscimento iniziale sarà il costo di acquisizione del cespite.

Prima di poter associare un cespite a un leasing, è necessario creare un record per il cespite in Cespiti. Quindi, nella pagina **Riepilogo leasing**, devi creare un leasing e collegare il cespite a tale leasing.

1. Aggiungi un leasing seguendo i passaggi in [Aggiungere o copiare leasing](add-lease.md). Nella pagina **Aggiungi leasing**, nel campi **Numero cespite** seleziona il cespite non è stato ancora acquisito.
2. Seleziona **Libri** e conferma lo scadenziario pagamenti.
3. Seleziona **Riconoscimento iniziale**.
4. Seleziona **Giornale di registrazione leasing cespite**.

    La scrittura contabile di riconoscimento iniziale per il leasing addebita il cespite per l'importo che di solito viene addebitato al conto Asset ROU.

    Ora puoi visualizzare il tipo di transazione e registrare il cespite.

5. Seleziona **Dettagli gironale di registrazione**.
6. Seleziona **Righe** per visualizzare le singole righe per la scrittura contabile.
7. Seleziona la riga del giornale di registrazione che contiene il cespite, quindi seleziona la scheda **Cespiti**.

    La scheda **Cespiti** mostra il tipo di transazione e il libro. Per impostazione predefinita, il campo **Tipo di transazione** è impostato su **Acquisizione** e il campo **Libro** è impostato sul libro corrente per il cespite.

Dopo aver registrato la scrittura contabile di riconoscimento iniziale, la transazione viene visualizzata come transazione di acquisizione per il cespite. Per visualizzare la tabella delle transazioni, vai a **Cespiti \> Cespiti \> Immobilizzazioni**, seleziona il cespite appropriato, quindi seleziona **Valutazioni**. Dovrebbe essere visibile che la scrittura contabile di riconoscimento iniziale ha creato una transazione di acquisizione per il cespite specificato.

Il cespite può ora essere ammortizzato utilizzando la funzionalità di ammortamento standard in Cespiti. Per ulteriori informazioni sull'ammortamento, vedi [Metodi e convenzioni di ammortamento](../fixed-assets/depreciation-methods-conventions.md).

> [!NOTE]
> Se associ un cespite a un leasing, i pulsanti **Ammortamento dei cespiti** e **Riduzione del valore del leasing** sono disabilitati in Leasing cespite. Puoi visualizzare l'ammortamento dei cespiti e le transazioni di riduzione del leasing da Cespiti. Anche il pulsante **Transazioni cespiti** che apre un modulo di richiesta è disabilitato. Puoi anche aprire il modulo di richiesta **Transazioni cespiti** in Cespiti.  