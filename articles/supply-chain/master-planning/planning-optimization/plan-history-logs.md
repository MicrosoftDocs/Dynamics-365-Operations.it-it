---
title: Visualizzare la cronologia del piano e i log di pianificazione
description: In questo argomento viene descritto come visualizzare lo storico dei processi di pianificazione generati dalla funzionalità di ottimizzazione di pianificazione.
author: ChristianRytt
ms.date: 10/30/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: MPSPlanRegenerationJobList, MPSPlanRegenerationJobLogs
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: d7bba084b03f8698c8bf31d171d5e4e486ed06ad
ms.sourcegitcommit: a7649b361ec54b49c0e9ee1c1c63a8815f320225
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2021
ms.locfileid: "6187249"
---
# <a name="view-plan-history-and-planning-logs"></a>Visualizzare la cronologia del piano e i log di pianificazione

[!include [banner](../../includes/banner.md)]

In questo argomento viene descritto come visualizzare lo storico dei processi di pianificazione generati dalla funzionalità di ottimizzazione di pianificazione in Microsoft Dynamics 365 Supply Chain Management.

Per visualizzare lo storico per un piano, aprire il piano andando a **Pianificazione generale** \> **Impostazione** \> **Piani** \> **Piani generali** e **Storico**. Lo storico elenca tutti i processi per il piano selezionato. L'elenco include i processi attivi e completati.

La cronologia dei processi per le esecuzioni della pianificazione principale di Ottimizzazione pianificazione conserva solo fino a 60 record per piano generale. Ogni volta che si esegue un nuovo calcolo della pianificazione generale, il primo record cronologico di quel piano viene eliminato.

Oltre a visualizzare l'ora di inizio e lo stato dei processi, è possibile visualizzare il log per un processo specifico. Il log include ulteriori informazioni e gli avvisi. Non tutti i processi hanno un log. Per visualizzare il log per un processo, selezionare **Log**. Le voci del registro vengono archiviate solo per 30 giorni dopo la data di completamento del processo, dopodiché vengono eliminate automaticamente.

## <a name="related-resources"></a>Risorse correlate

- [Panoramica sull'ottimizzazione della pianificazione](planning-optimization-overview.md)
- [Introduzione all'ottimizzazione della pianificazione](get-started.md)
- [Analisi di adeguatezza dell'ottimizzazione di pianificazione](planning-optimization-fit-analysis.md)
- [Applicare i filtri a un piano](plan-filters.md)
- [Annullare un processo di pianificazione](cancel-planning-job.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]