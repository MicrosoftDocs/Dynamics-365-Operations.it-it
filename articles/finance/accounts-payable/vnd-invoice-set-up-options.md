---
title: Opzioni di configurazione per l'automazione delle fatture fornitore (anteprima)
description: In questo argomento vengono descritte le opzioni disponibili per l'impostazione e la configurazione dell'automazione delle fatture fornitore.
author: abruer
manager: AnnBe
ms.date: 10/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.assetid: ''
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2017-08-30
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 40de7c378bff602fa3629bb190a7a89fe584d2a6
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4993206"
---
# <a name="setup-options-for-vendor-invoice-automation"></a>Opzioni di configurazione per l'automazione delle fatture fornitore

[!include [banner](../includes/banner.md)]

In questo argomento vengono descritte le opzioni disponibili per l'impostazione e la configurazione dell'automazione delle fatture fornitore. Le funzionalità di automazione delle fatture utilizzano i seguenti tipi di parametri di configurazione:

- Parametri per l'invio di fatture fornitore importate al sistema del flusso di lavoro e l'abbinamento delle righe di entrata prodotti registrate alle righe di fattura fornitore in sospeso.
- Parametri per le attività in background dell'automazione dell'elaborazione. Il framework di automazione del processo viene utilizzata per inviare le fatture fornitore importate al sistema del flusso di lavoro. Viene inoltre utilizzato per abbinare automaticamente le righe di entrata prodotti registrate alle righe di fattura fornitore in sospeso e per eseguire la convalida di abbinamento fatture per le fatture manuali che sono state abbinate automaticamente alle righe di entrata prodotti. Diversi processi aziendali utilizzano questo framework per definire la frequenza di esecuzione del processo selezionato. Le frequenze disponibili per i processi in background **Abbinare l'entrata prodotti a righe di fattura** e **Inviare fatture fornitore a flusso di lavoro** includono **Ora** e **Giornaliera**.

Per impostare o visualizzare le informazioni su un'attività in background, vai a **Amministrazione sistema \> Impostazione \> Automazioni processo** e seleziona la scheda **Attività in background**.

Per ottenere l'automazione senza contatto dal processo di importazione attraverso la registrazione delle fatture fornitore, devi configurare un flusso di lavoro fatture fornitore. Per configurare un flusso di lavoro, vai a **Contabilità fornitori > Impostazioni > Flussi di lavoro contabilità fornitori**. Per garantire che la fattura possa essere elaborata dall'inizio alla fine senza intervento manuale, devi includere un'attività di registrazione automatizzata nella configurazione del flusso di lavoro.

## <a name="parameters-for-submitting-imported-vendor-invoices-to-the-workflow-system"></a>Parametri per l'invio di fatture fornitore importate al sistema del flusso di lavoro

Per l'invio di fatture fornitore importate al sistema del flusso di lavoro vengono utilizzati specifici parametri. Inoltre, alcuni parametri sono utilizzati per abbinare righe di entrata prodotti registrate alle righe di fattura fornitore in sospeso. Nella scheda **Automazione fattura fornitore** della pagina **Parametri di contabilità fornitori**, i parametri che devi impostare sono suddivisi tra le seguenti sezioni:

- Flusso di lavoro fatture fornitore
- Abbina le entrate prodotti automaticamente

Sono disponibili i parametri seguenti:

- **Invia automaticamente fatture importate a flusso di lavoro** - Se imposti questa opzione su **Sì**, le fatture importate vengono inviate automaticamente al sistema del flusso di lavoro. Se questa opzione è impostata su **No**, le fatture devono essere inviate manualmente. Impostando questa opzione su **Sì**, abiliti un processo senza contatto dai risultati dell'importazione fino alla registrazione.

    Puoi impostare questa opzione su **Sì** solo se un flusso di lavoro di fatture fornitore attivo è configurato per la persona giuridica. Per configurare un flusso di lavoro, vai a **Contabilità fornitori \> Impostazioni \> Flusso di lavoro contabilità fornitori**.

- **Abbina entrate prodotti a righe di fattura prima dell'invio automatico** - Se imposti questa opzione su **Sì**, la fattura importata non può essere inviata automaticamente al sistema del flusso di lavoro fino a che la quantità delle entrate prodotti abbinata non è uguale alla quantità della fattura. Impostando questa opzione su **Sì**, abiliti l'abbinamento automatico delle entrate prodotti registrate alle righe di fattura per cui sono definiti criteri di abbinamento a tre elementi di verifica. Quel processo verrà eseguito fino a quando la quantità delle entrate prodotti abbinate non sarà uguale alla quantità della fattura. A quel punto, la fattura viene automaticamente inviata al sistema del flusso di lavoro.

    L'opzione "Abbina entrate prodotti a righe di fattura prima dell'invio automatico" è disponibile solo se l'opzione **Abilita convalida abbinamento fatture** è selezionata. Quando questa opzione è selezionata, l'opzione **Abbina automaticamente entrate prodotti a righe di fattura** viene selezionata automaticamente.

- **Richiedi che i totali calcolati siano uguali ai totali importati per l'invio automatico del flusso di lavoro** - Se imposti questa opzione su **Sì**, la fattura non può essere inviata automaticamente al sistema del flusso di lavoro fino a che i totali calcolati per la fattura non sono uguali ai totali importati. Se questa opzione è impostata su **No**, la fattura può essere inviata automaticamente al sistema del flusso di lavoro, ma non può essere registrata fino a che i totali calcolati non vengono corretti di modo che corrispondano ai totali importati. Se non importi l'importo della fattura o l'importo dell'IVA, questa opzione deve essere impostata su **No**.
- **Abbina automaticamente entrate prodotti a righe di fattura** - Se imposti questa opzione su **Sì**, l'elaborazione in background può essere utilizzata per eseguire l'abbinamento automatico delle entrate prodotto registrate a righe di fattura per cui sono definiti criteri di abbinamento a tre elementi di verifica. Quel processo verrà eseguito fino a quando la quantità di entrate prodotto abbinata non sarà uguale alla quantità della fattura o fino a quando non viene raggiunto il valore del campo **Numero di tentativi di abbinamento automatico**. Il processo può essere eseguito fino a quando la fattura non è stata inviata al sistema del flusso di lavoro.

    Questa opzione è disponibile solo se è selezionata l'opzione **Abilita convalida abbinamento fatture**.

    Se imposti l'opzione **Abbina entrate prodotti a righe di fattura prima dell'abbinamento automatico** su **Sì**, questa opzione non può essere impostata su **No**. Per impostare questa opzione su **No**, devi prima impostare **Abbina entrate prodotti a righe di fattura prima dell'abbinamento automatico** su **No**.

- **Numero di tentativi di abbinamento automatico** - Seleziona il numero di tentativi del sistema di abbinare le entrate prodotti a una riga di fattura prima di considerare il processo come non riuscito. Quando viene raggiunto il numero di tentativi specificato, la fattura viene rimossa dall'elaborazione dell'automazione.

