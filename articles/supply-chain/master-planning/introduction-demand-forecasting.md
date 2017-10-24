---
title: Cenni preliminari sulla previsione della domanda
description: La previsione della domanda viene utilizzata per prevedere la domanda indipendente da ordini cliente e la domanda dipendente in qualsiasi punto di disaccoppiamento per gli ordini cliente. Le regole avanzate di riduzione della previsione della domanda forniscono una soluzione ideale per la personalizzazione in massa.
author: roxanadiaconu
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ReqDemPlanCreateForecastDialog
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 72004
ms.assetid: 916707c9-1333-460f-a0fa-4e95f6fda2ad
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 5a651fcd386e9f976559a1fc540c5d9191ab632b
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---

# <a name="demand-forecasting-overview"></a>Cenni preliminari sulla previsione della domanda

[!include[banner](../includes/banner.md)]


La previsione della domanda viene utilizzata per prevedere la domanda indipendente da ordini cliente e la domanda dipendente in qualsiasi punto di disaccoppiamento per gli ordini cliente. Le regole avanzate di riduzione della previsione della domanda forniscono una soluzione ideale per la personalizzazione in massa.

Per generare la previsione di base, viene trasmesso un riepilogo delle transazioni storiche a un servizio Microsoft Azure Machine Learning ospitato in Azure. Poiché il servizio non è condiviso tra gli utenti, può essere facilmente personalizzato per soddisfare i requisiti di settore specifici. È possibile utilizzare Finance and Operations per visualizzare la previsione, modificarla e per visualizzare gli indicatori di prestazione chiave (KPI) relativi all'accuratezza di previsione.

## <a name="key-features-of-demand-forecasting"></a>Funzionalità principali della previsione della domanda
Di seguito vengono descritte alcune delle funzionalità principali della previsione della domanda:

-   Generazione dei una previsione di base statistica basata sui dati transazione storici.
-   Utilizzo di un set dinamico di dimensioni di previsione.
-   Visualizzazione di tendenze nella domanda, intervalli valori di fiducia e correzioni della previsione.
-   Autorizzazione della previsione corretta per l'utilizzo nei processi di pianificazione.
-   Rimozione outlier.
-   Creazione di misurazioni della precisione di previsione.

## <a name="major-themes-in-demand-forecasting"></a>Temi principali nella previsione della domanda
Nella previsione della domanda sono implementati tre temi principali:

-   **Modularità**: la previsioni della domanda è modulare e facile da configurare. È possibile attivare o disattivare la funzionalità modificando la chiave di configurazione in **Commercio** &gt; **Previsione di magazzino** &gt; **Previsione della domanda**.
-   **Riutilizzo dello stack Microsoft**: nel febbraio 2015 Microsoft ha lanciato la piattaforma Machine Learning. Machine Learning, che ora fa parte di Analytics Suite di Microsoft Cortana, consente di creare in modo facile e rapido esperimenti di analisi predittive, ad esempio esperimenti di stima della domanda, tramite l'uso di algoritmi R o linguaggi di programmazione Python e una semplice interfaccia basata sul trascinamento della selezione.
    -   È possibile scaricare gli esperimenti di previsione della domanda di Finance and Operations, modificarli in base ai requisiti aziendali, pubblicarli come servizio Web in Azure e utilizzarli per generare previsioni della domanda. Gli esperimenti sono disponibili per il download se si dispone di una sottoscrizione di Finance and Operations destinata a un responsabile di pianificazione come utente di livello di aziendale.
    -   È possibile scaricare uno degli esperimenti di previsione della domanda attualmente disponibili dalla [raccolta di analisi dei dati Cortana](https://gallery.cortanaanalytics.com/). Mentre gli esperimenti di previsione della domanda di Finance and Operations vengono automaticamente integrati in Finance and Operations, l'integrazione degli esperimenti scaricati dalla [raccolta di analisi dei dati di Cortana](https://gallery.cortanaanalytics.com/) deve essere gestita dai clienti e dai partner. Di conseguenza, gli esperimenti della [raccolta di analisi dei dati di Cortana](https://gallery.cortanaanalytics.com/) non risultano immediati da utilizzare come gli esperimenti di previsione della domanda di Finance and Operations. È necessario modificare il codice degli esperimenti in modo che utilizzino l'API di Finance and Operations.
    -   È possibile creare esperimenti personalizzati Microsoft Azure Machine Learning Studio, pubblicarli come servizi in Azure e utilizzarli per generare le previsioni della domanda.
    -   Se non sono richieste prestazioni elevate, o l'elaborazione di una grade quantità di dati, è possibile utilizzare la versione di prova gratuita di Machine Learning. Si consiglia di iniziare sempre da questo livello, in particolare durante le fasi di test e implementazione. Se sono richieste prestazioni elevate e spazio di archiviazione aggiuntivo, è possibile utilizzare il livello standard di Machine Learning. Questo livello richiede una sottoscrizione di Azure e comporta costi aggiuntivi. Per dettagli sui prezzi di Machine Learning, vedere <http://aka.ms/machine-learning-price-info>.
-   **Riduzione della previsione in qualsiasi punto di disaccoppiamento**: la previsione della domanda in Finance and Operations è basata su questa funzionalità, che consente di prevedere la domanda dipendente e indipendente da qualsiasi punto di disaccoppiamento.

## <a name="basic-flow-in-demand-forecasting"></a>Flusso di base nella previsione della domanda
Nel seguente diagramma viene visualizzato il flusso di base nella previsione della domanda. 

[![diagramma di introduzione alla previsione della domanda](./media/demand-forecasting-introduction.png)](./media/demand-forecasting-introduction.png)

La generazione della previsione della domanda inizia in Finance and Operations. I dati transazionali storici del database transazionale di Finance and Operations vengono raccolti e usati per popolare una tabella di gestione temporanea. Questa tabella viene successivamente immessa nel servizio di Machine Learning. Con una personalizzazione minima, è possibile inserire le varie origini dati nella tabella di gestione temporanea. Le origini dati possono includere file di Microsoft Excel, file CSV e dati di Microsoft Dynamics AX 2009 e di Microsoft Dynamics AX 2012. È di conseguenza possibile generare previsioni della domanda che considerino i dati storici che sono sparsi in più sistemi. Tuttavia, l'anagrafica, ad esempio i nomi degli articoli e le unità di misura, devono essere uguali tra le varie origini dati.

Se si utilizzano gli esperimenti di Machine Learning della previsione della domanda di Finance and Operations, questi cercano il metodo più adatto tra i cinque metodi di previsione disponibili per calcolare una previsione di base. I parametri per i metodi di previsione vengono gestiti in Finance and Operations. 

Le previsioni, i dati storici e tutte le modifiche effettuate nelle previsioni della domanda in iterazioni precedenti sono quindi disponibili in Finance and Operations. 

È possibile utilizzare Finance and Operations per visualizzare e modificare le previsioni di base. Le correzioni manuali devono essere autorizzate prima che le previsioni possano essere utilizzate per la programmazione.

## <a name="limitations"></a>Limiti
La previsione della domanda in Finance and Operations è uno strumento che consente ai clienti del settore manifatturiero di creare processi di previsione. Questo strumento offre le funzionalità di base di una soluzione di previsione della domanda ed è progettato in modo che possa essere facilmente esteso. La previsione della domanda potrebbe non essere la soluzione migliore per i clienti di settori come la vendita al dettaglio, la vendita all'ingrosso, l'immagazzinamento, il trasporto o altri servizi professionali.

<a name="see-also"></a>Vedere anche
--------

[Impostazione della previsione della domanda](demand-forecasting-setup.md)

[Generazione di una previsione di base statistica](generate-statistical-baseline-forecast.md)

[Implementazione di correzioni manuali nella previsione di base](manual-adjustments-baseline-forecast.md)

[Autorizzazione della previsione rettificata](authorize-adjusted-forecast.md)

[Monitoraggio della precisione previsione](monitor-forecast-accuracy.md)

[Eliminare gli outlier dai dati di transazione storici quando si calcola una previsione della domanda](remove-historical-outliers-calculating-demand-forecast.md)




