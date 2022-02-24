---
title: Panoramica dell'ottimizzazione di pianificazione
description: Questo argomento fornisce una panoramica della funzionalità di ottimizzazione di pianificazione.
author: ChristianRytt
manager: tfehr
ms.date: 10/31/2019
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
ms.openlocfilehash: 110045d4c7e4f32c29b73096dd4df3a09b5434ac
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4430929"
---
# <a name="planning-optimization-overview"></a>Panoramica dell'ottimizzazione di pianificazione

[!include [banner](../../includes/banner.md)]

Il componente aggiuntivo di ottimizzazione della pianificazione per Microsoft Dynamics 365 Supply Chain Management consente il calcolo della pianificazione principale al di fuori di Dynamics 365 Supply Chain Management e del relativo database SQL. I vantaggi associati alla funzionalità di ottimizzazione di pianificazione includono prestazioni migliorate e un impatto minimo sul database SQL durante le esecuzioni della pianificazione generale. Le esecuzioni di pianificazione rapide possono essere eseguite anche durante le ore d'ufficio, in modo che i pianificatori possano reagire immediatamente alla modifica della domanda o dei parametri.

Per utilizzare l'ottimizzazione di pianificazione, è necessario installare il componente aggiuntivo di ottimizzazione della pianificazione dal progetto in Microsoft Dynamics Lifecycle Services (LCS) e attivare la funzionalità di ottimizzazione di pianificazione in Supply Chain Management. Per ulteriori informazioni, vedere [Introduzione all'ottimizzazione di pianificazione](get-started.md).

La seguente illustrazione mostra il vantaggio di eseguire l'ottimizzazione di pianificazione durante l'orario di ufficio.

![Vantaggio dell'esecuzione dell'ottimizzazione di pianificazione durante l'orario di ufficio](media/PlanningOptimization1.png)

## <a name="improved-performance"></a>Prestazioni migliorate

L'ottimizzazione di pianificazione può essere utilizzata negli scenari che includono i piani generali a esecuzione prolungata. È specificamente progettata per calcoli molto veloci che coinvolgono volumi di dati molto grandi. Poiché è concepita come un servizio multi-tenant iperscalabile, più istanze possono lavorare contemporaneamente per calcolare il piano. Inoltre, il servizio di pianificazione rimuove il carico della pianificazione generale dal sistema e funziona con un flusso di dati che riduce al minimo il carico del server.

L'ottimizzazione di pianificazione consente di raggiungere i seguenti obiettivi:

- Migliorare le prestazioni di pianificazione con un tempo di esecuzione più breve.
- Ridurre l'impatto su altri processi durante l'esecuzione della pianificazione generale.
- Avviare esecuzioni di pianificazione più frequenti. Non c'è limite alle esecuzioni giornaliere.
- Essere sicuri che la crescita futura dell'azienda non sovraccaricherà il sistema di pianificazione.

## <a name="architecture-and-data-flow"></a>Architettura e flusso di dati

Quando il componente aggiuntivo di ottimizzazione di pianificazione viene installato da LCS, viene stabilita una connessione sicura al servizio di ottimizzazione di pianificazione. Il servizio si trova nello stesso paese del data center dell'istanza di Supply Chain Management. Dopo aver impostato l'ottimizzazione di pianificazione, quando viene eseguita la pianificazione generale, i dati principali e i dati transazionali vengono inviati da Supply Chain Management al servizio di ottimizzazione di pianificazione.

Se il componente aggiuntivo ottimizzazione di pianificazione viene disinstallato, tutti i dati correlati nel servizio ottimizzazione di pianificazione vengono rimossi.

### <a name="high-level-data-flow-for-regeneration-runs"></a>Flusso di dati di alto livello per le esecuzioni di rigenerazione

1. Il client di Supply Chain Management invia un segnale per richiedere l'esecuzione di una pianificazione dall'ottimizzazione di pianificazione.
2. L'ottimizzazione di pianificazione richiede i dati necessari tramite il connettore integrato.
3. Il database SQL invia le informazioni richieste sui dati di installazione, master e transazionali all'ottimizzazione di pianificazione tramite il connettore. Il connettore traduce le informazioni tra Supply Chain Management e il servizio di ottimizzazione di pianificazione.
4. Il servizio di ottimizzazione di pianificazione conserva in memoria i dati relativi alla pianificazione ed esegue i calcoli richiesti.
5. Il risultato della pianificazione viene inviato al database di Supply Chain Management tramite il connettore. I risultati includono informazioni come ordini pianificati e informazioni di pegging. L'ottimizzazione di pianificazione invia un segnale a Supply Chain Management per indicare che l'esecuzione di pianificazione è stata completata. Invia inoltre eventuali messaggi e avvisi pertinenti.

L'illustrazione seguente mostra il flusso dei dati.

![Flusso di dati per le esecuzioni di rigenerazione](media/PlanningOptimization2.png)

## <a name="related-resources"></a>Risorse correlate

[Introduzione all'ottimizzazione di pianificazione](get-started.md)

[Analisi di adeguatezza dell'ottimizzazione di pianificazione](planning-optimization-fit-analysis.md)

[Visualizzare la cronologia del piano e i log di pianificazione](plan-history-logs.md)

[Applicare i filtri a un piano](plan-filters.md)

[Annullare un processo di pianificazione](cancel-planning-job.md)
