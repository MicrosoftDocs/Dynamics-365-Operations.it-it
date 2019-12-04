---
title: Annullare un processo di pianificazione
description: In questo argomento viene descritto come annullare un processo attivo di pianificazione che utilizza la funzionalità di ottimizzazione di pianificazione.
author: ChristianRytt
manager: AnnBe
ms.date: 10/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: a2d90f04985fdd66ca83582ee676100fffb26981
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/06/2019
ms.locfileid: "2773992"
---
[!include [banner](../../includes/banner.md)]
[!include [banner](../../includes/preview-banner.md)]

# <a name="cancel-a-planning-job"></a>Annullare un processo di pianificazione

In Microsoft Dynamics 365 Supply Chain Management è possibile annullare un processo attivo di pianificazione che utilizza la funzionalità di ottimizzazione di pianificazione.

Per annullare un processo attivo di pianificazione, effettuare le seguenti operazioni.

> [!NOTE]
> Solo i processi attivo possono essere annullati.

1. Passare a **Pianificazione generale \> Impostazione \> Piani**.
2. Selezionare un piano appropriato per l'esecuzione di pianificazione.
3. Selezionare **Storico**.
4. Selezionare il processo di pianificazione da annullare.
5. Selezionare **Annulla**.

Lo stato del processo sarà **Annullamento in corso** finché il servizio di ottimizzazione di pianificazione non conferma che il processo è stato annullato. Lo stato quindi diventa **Annullato**.

> [!NOTE]
> Per visualizzare le modifiche di stato, è necessario aggiornare la pagina facendo clic sul pulsante **Aggiorna**.

## <a name="related-resources"></a>Risorse correlate

[Panoramica dell'ottimizzazione di pianificazione](planning-optimization-overview.md)

[Introduzione all'ottimizzazione di pianificazione](get-started.md)

[Analisi di adeguatezza dell'ottimizzazione di pianificazione](planning-optimization-fit-analysis.md)

[Visualizzare la cronologia del piano e i log di pianificazione](plan-history-logs.md)

[Applicare i filtri a un piano](plan-filters.md)
