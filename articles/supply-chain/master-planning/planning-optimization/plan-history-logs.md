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
ms.openlocfilehash: 757d2103bd629c0107a3f29599196a56ea56d431a66cf1e69c7b3cf3d817c087
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6724822"
---
# <a name="view-plan-history-and-planning-logs"></a>Visualizzare la cronologia del piano e i log di pianificazione

[!include [banner](../../includes/banner.md)]

In questo argomento viene descritto come visualizzare lo storico dei processi di pianificazione generati dalla funzionalità di ottimizzazione di pianificazione in Microsoft Dynamics 365 Supply Chain Management.

Per visualizzare lo storico per un piano, aprire il piano andando a **Pianificazione generale** \> **Impostazione** \> **Piani** \> **Piani generali** e **Storico**. Lo storico elenca tutti i processi per il piano selezionato. L'elenco include i processi attivi e completati.

La cronologia dei processi per le esecuzioni della pianificazione principale di Ottimizzazione pianificazione conserva solo fino a 60 record per piano generale. Ogni volta che si esegue un nuovo calcolo della pianificazione generale, il primo record cronologico di quel piano viene eliminato.

Oltre a visualizzare l'ora di inizio e lo stato dei processi, è possibile visualizzare il log per un processo specifico. Il log include ulteriori informazioni e gli avvisi. Non tutti i processi hanno un log. Per visualizzare il log per un processo, selezionare **Log**. Le voci del registro vengono archiviate solo per 30 giorni dopo la data di completamento del processo, dopodiché vengono eliminate automaticamente.

Se l'opzione **Elaborazione batch** nella scheda dettaglio **Esegui in background** è stata abilitata quando è stata impostata l'elaborazione della pianificazione principale, il registro del processo batch mostra ulteriori informazioni su eventuali avvisi ed errori generati durante l'esecuzione della pianificazione principale. Ad esempio, gli errori di stabilizzazione automatica vengono acquisiti solo nel registro del processo batch. Non vengono mostrati nei registri della pagina **Cronologia**.

Per visualizzare gli errori di stabilizzazione automatica e altri avvisi o errori che si sono verificati durante un'esecuzione della pianificazione generale, segui questi passaggi.

1. Andare a **Amministrazione sistema \> Richieste di informazioni \> Processi batch**.
1. Trova e seleziona il record che rappresenta l'esecuzione della pianificazione generale che ti interessa. (Ad esempio, il valore del campo **Descrizione processo** può iniziare con *Pianificazione generale*.)
1. Segui uno di questi passaggi, a seconda che tu stia utilizzando il *modulo avanzato* o il *modulo legacy (non avanzato)* per la pagina **Processi batch**:

    - Se stai utilizzando il modulo avanzato: nel riquadro azioni, seleziona **Cronologia processi batch**. Quindi nella pagina **Cronologia processi batch** nel riquadro azioni, seleziona **Registro**.
    - Se stai utilizzando il modulo legacy: nel riquadro azioni, seleziona **Registro** nella scheda **Processo batch**.

1. Seleziona **Dettagli messaggio** per aprire il riquadro **Dettagli messaggio** in cui è possibile visualizzare tutti gli avvisi e gli errori acquisiti durante l'elaborazione.

## <a name="related-resources"></a>Risorse correlate

- [Panoramica sull'ottimizzazione della pianificazione](planning-optimization-overview.md)
- [Introduzione all'ottimizzazione della pianificazione](get-started.md)
- [Analisi di adeguatezza dell'ottimizzazione di pianificazione](planning-optimization-fit-analysis.md)
- [Applicare i filtri a un piano](plan-filters.md)
- [Annullare un processo di pianificazione](cancel-planning-job.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
