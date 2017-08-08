---
title: Area di lavoro gestione cespiti
description: Vengono fornite le informazioni sull'area di lavoro gestione cespiti. Questa area di lavoro visualizza le informazioni relative ai cespiti immessi nel sistema. Include una visualizzazione di riepilogo e una visualizzazione di analisi.
author: saraschi
manager: AnnBe
ms.date: 06/06/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations, UnifiedOperations
ms.assetid: 
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2017-06-30T00:00:00.000Z
ms.dyn365.ops.version: July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 08c38aada355583c5a6872f75b57db95d9b81786
ms.openlocfilehash: 69f728c5b5897d7210941643d2c7d0d7abf054fa
ms.contentlocale: it-it
ms.lasthandoff: 07/27/2017

---

# <a name="fixed-asset-management-workspace"></a>Area di lavoro gestione cespiti

[!include[banner](../includes/banner.md)]

L'area di lavoro **Gestione cespiti** visualizza le informazioni relative ai cespiti immessi nel sistema. Questa area di lavoro include una visualizzazione di riepilogo e una visualizzazione di analisi. Nella scheda **Lavoro personale** vengono visualizzati i riquadri di riepilogo, i dettagli dei cespiti e le informazioni correlate sui cespiti della società corrente. È inoltre possibile aggiungere l'analisi alla sezione dell'analisi di Power BI direttamente nell'area di lavoro. La scheda **Analisi - tutte le società** utilizza le funzionalità di Microsoft Power BI per visualizzare le rappresentazioni relative ai cespiti di tutte le società.

## <a name="my-work"></a>Lavoro personale

### <a name="summary"></a>Riepilogo

I riquadri nella sezione **Riepilogo** forniscono una panoramica dei cespiti. Queste informazioni includono le metriche relative ai cespiti che non sono stati acquistati, i cespiti che sono stati acquistati durante l'anno corrente e i cespiti dismessi durante l'anno corrente. Nella sezione **Riepilogo** è disponibile anche il collegamento rapido alla pagina elenco **Cespite**, alla proposta di ammortamento batch e al giornale di registrazione cespiti.

### <a name="find-fixed-assets"></a>Trova cespiti

La sezione **Trova cespiti** consente di individuare rapidamente i cespiti immettendo il numero di cespite, il nome di un gruppo, l'ubicazione o la persona responsabile. Tutti i cespiti che soddisfano i criteri di ricerca verranno visualizzati nell'elenco.

Nell'elenco è possibile visualizzare le pagine seguenti:

 - Pagina **Dettagli** per il cespite
 - Pagina **Libri** per tutti i libri associati al cespite
 - Pagina **Valutazioni cespiti**

### <a name="valuations"></a>Valutazioni

La pagina **Valutazioni cespiti** consente di vedere in una sola pagina, la maggior parte delle informazioni rilevanti su un cespite nonché i dettagli per tutti i libri associati al cespite. L'opzione **Saldi** nella parte superiore sinistra della pagina mostra la valutazione corrente per ciascun libro associato al cespite. È possibile eseguire il rollback dei valori per visualizzare le transazioni dettagliate che costituiscono il valore di riepilogo. L'opzione **Profilo** nella parte superiore sinistra della pagina mostra il piano di ammortamento per ciascun libro associato al cespite.

È possibile accedere alla pagina **Valutazioni cespiti** dall'area di lavoro **Gestione cespiti** o dalla pagina elenco **Cespite**.

### <a name="related-information"></a>Informazioni correlate

È possibile accedere direttamente alla pagina **Impostazione libri**, alla pagina **Richiesta di informazioni sulle transazioni cespiti** e a diversi report utilizzando i collegamenti nella sezione **Informazioni correlate** dell'area di lavoro.

### <a name="analytics--all-companies"></a>Analisi - tutte le società

La pagina **Analisi** fornisce le metriche importanti sui cespiti in tutte le persone giuridiche nel sistema. L'accesso alla scheda dipende dal privilegio di sicurezza Visualizza analisi cespite per tutte le società.

Nella seguente tabella vengono illustrate le visualizzazioni disponibili in ciascuna pagina del report.

| Pagina di report            | Visualizzazione        |
|------------------------|----------------------|
| Valutazioni cespiti | Totale valore contabile netto |
| Valutazioni cespiti | Valori contabili netti per gruppo cespiti |
| Valutazioni cespiti | Valori di acquisizione |
| Valutazioni cespiti | Valori di dismissione |
| Valutazioni cespiti | Dettagli cespite |
| Mappe valutazioni        | Totale valore contabile netto |
| Mappe valutazioni        | Ubicazioni cespiti |
| Mappe valutazioni        | Dettagli cespite |

Per visualizzare l'analisi con i dati, è necessario prima di tutto aggiornare la misura di aggregazione AssetTransactionMeasure nella pagina **Archivio entità**.

