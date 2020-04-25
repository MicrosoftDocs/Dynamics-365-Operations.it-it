---
title: Analisi di adeguatezza dell'ottimizzazione di pianificazione
description: Questo argomento spiega come verificare la configurazione e i dati correnti rispetto alle funzionalità della funzionalità di ottimizzazione di pianificazione.
author: ChristianRytt
manager: tfehr
ms.date: 10/30/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: 17114d4c0ef2c74ab1bb56d41e4a008150c21f36
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2020
ms.locfileid: "3208756"
---
# <a name="planning-optimization-fit-analysis"></a>Analisi di adeguatezza dell'ottimizzazione di pianificazione

[!include [banner](../../includes/preview-banner.md)]
[!include [banner](../../includes/banner.md)]

Per visualizzare la compatibilità dell'impostazione e dei dati correnti rispetto alla funzionalità di ottimizzazione di pianificazione, passare a **Pianificazione generale** \> **Impostazione** \> **Analisi di adeguatezza dell'ottimizzazione di pianificazione** e selezionare **Esegui analisi**. Se l'analisi rileva delle incoerenze, vengono elencate nella stessa pagina. L'esecuzione dell'analisi può richiedere alcuni minuti.

> [!NOTE]
> In caso di incongruenze, sarà comunque possibile utilizzare l'ottimizzazione di pianificazione. I risultati dell'analisi di adeguatezza indicano le posizioni in cui il servizio di pianificazione non onorerà la configurazione corrente. Ciò significa che indicano le posizioni in cui i processi potrebbero essere ignorati o non essere supportati.

## <a name="analysis-results-example-1"></a>Risultati dell'analisi: Esempio 1

- **Funzionalità:** Produzione
- **Problema:** Articoli con livello DBA maggiore di zero: 56
- **Descrizione:** L'analisi di adeguatezza ha rilevato 56 articoli con una distinta base (DBA) impostata per la produzione. Poiché l'attuale versione di ottimizzazione di pianificazione non supporta la produzione, ottimizzazione di pianificazione genera ordini fornitore pianificati anziché ordini di produzione pianificati. Mostra anche un avviso che elenca gli articoli interessati.

### <a name="analysis-results-example-2"></a>Risultati dell'analisi: Esempio 2

- **Funzionalità:** Azioni
- **Problema:** Gruppi di copertura con calcolo delle azioni abilitato: 6
- **Descrizione:** L'analisi di adeguatezza ha rilevato sei gruppi di copertura in cui il calcolo dell'azione è abilitato. Poiché la versione corrente dell'ottimizzazione di pianificazione non supporta le azioni, non viene generata alcuna azione durante la pianificazione generale.

## <a name="related-resources"></a>Risorse correlate

[Panoramica dell'ottimizzazione di pianificazione](planning-optimization-overview.md)

[Introduzione all'ottimizzazione di pianificazione](get-started.md)

[Visualizzare la cronologia del piano e i log di pianificazione](plan-history-logs.md)

[Applicare i filtri a un piano](plan-filters.md)

[Annullare un processo di pianificazione](cancel-planning-job.md)
