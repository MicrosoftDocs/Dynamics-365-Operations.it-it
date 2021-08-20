---
title: Applicare i filtri a un piano
description: In questo argomento viene descritto come usare i filtri in un piano quando è utilizzata la funzionalità di ottimizzazione di pianificazione.
author: ChristianRytt
ms.date: 01/08/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: c2fbaa6945cf46b7ef09232e6004f09b487ea7c822e72225dc00d3d28ecb008e
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6780200"
---
# <a name="apply-filters-to-a-plan"></a>Applicare i filtri a un piano

[!include [banner](../../includes/banner.md)]

Quando la funzionalità di ottimizzazione di pianificazione viene utilizzata, è possibile applicare un filtro a un piano. Il **filtro del piano** viene sempre applicato durante un'esecuzione di pianificazione generale. Un **filtro del piano** è utile quando si desidera limitare un piano a un gruppo specifico di articoli e assicurarsi che nessun altro elemento sia incluso come parte della pianificazione generale risultante.

Se viene applicato un **filtro del piano** e viene applicato anche un filtro del runtime durante l'esecuzione della pianificazione generale, nell'esecuzione della pianificazione viene inclusa solo l'intersezione dei due filtri.

Il **filtro di piano** è accessibile da **Piani generali** quando viene utilizzata l'ottimizzazione della pianificazione.

## <a name="example-scenario"></a>Scenario di esempio

Viene impostato un filtro del piano che include gli articoli A, B e C. Le esecuzioni della pianificazione principale vengono quindi eseguite per lo stesso piano, ma vengono applicati diversi filtri del runtime:

- **Filtro del runtime che include l'articolo D:** Non sono previsti articoli, poiché non esiste intersezione tra il filtro del piano e il filtro del runtime.
- **Filtro del runtime che include l'articolo A e D:** Nell'esecuzione della pianificazione è incluso solo l'articolo A, poiché l'articolo D non fa parte del filtro del piano.
- **Filtro del runtime che include l'articolo B:** Nell'esecuzione della pianificazione è incluso solo l'articolo B e viene mantenuto l'output di pianificazione precedente per l'articolo A.
- **Filtro del runtime che include tutti gli articoli (filtro vuoto):** Gli articoli A, B e C sono inclusi nell'esecuzione della pianificazione e l'output di pianificazione precedente per gli articoli A e B viene sovrascritto.

> [!NOTE]
> È necessario evitare di impostare un filtro del piano sul piano selezionato come **Piano generale dinamico corrente** nella pagina **Parametri di pianificazione generale**. In caso contrario, la funzionalità del piano principale dinamico è limitata agli articoli filtrati. Ad esempio, se i requisiti netti vengono aggiornati per un articolo che non fa parte del filtro del piano, non verrà generato alcun risultato.

## <a name="related-resources"></a>Risorse correlate

[Panoramica dell'ottimizzazione di pianificazione](planning-optimization-overview.md)

[Introduzione all'ottimizzazione di pianificazione](get-started.md)

[Analisi di adeguatezza dell'ottimizzazione di pianificazione](planning-optimization-fit-analysis.md)

[Visualizzare la cronologia del piano e i log di pianificazione](plan-history-logs.md)

[Annullare un processo di pianificazione](cancel-planning-job.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]