---
title: Panoramica di previsione della domanda
description: La previsione della domanda viene utilizzata per prevedere la domanda indipendente da ordini cliente e la domanda dipendente in qualsiasi punto di disaccoppiamento per gli ordini cliente. Le regole avanzate di riduzione di previsione della domanda viene fornita una soluzione ideale per la personalizzazione di massa.
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: ReqDemPlanCreateForecastDialog
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 72004
ms.assetid: 916707c9-1333-460f-a0fa-4e95f6fda2ad
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: 9152616b81e7873426f296376b5e57c94439379d
ms.lasthandoff: 03/31/2017


---

# <a name="demand-forecasting-overview"></a>Panoramica di previsione della domanda

La previsione della domanda viene utilizzata per prevedere la domanda indipendente da ordini cliente e la domanda dipendente in qualsiasi punto di disaccoppiamento per gli ordini cliente. Le regole avanzate di riduzione di previsione della domanda viene fornita una soluzione ideale per la personalizzazione di massa.

Per generare la previsione di base, viene trasmesso un riepilogo delle transazioni storiche a un servizio Microsoft Azure Machine Learning ospitato in Azure. Poiché il servizio non è condiviso tra gli utenti, può essere facilmente personalizzato per soddisfare i requisiti di settore specifici. È possibile utilizzare Dynamics 365 per le operazioni corrente della previsione, per rettificare la previsione e visualizzare indicatori di prestazioni chiave (KPIs) sull'accuratezza programmata.

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

-   **Modularità**: la previsioni della domanda è modulare e facile da configurare. È possibile attivare la funzionalità delle operazioni e di inattività cambiando la chiave di configurazione Commercio ** ** &gt; ** al magazzino previste ** &gt; ** previsione della domanda **.
-   ** Se per il riutilizzo della pila Microsoft ** - Microsoft ha avviato la presentazione di apprendimento automatico nel febbraio 2015. In apprendimento automatico, che ora fa parte di serie dell'analisi dei dati di Microsoft Cortana, selezionare un modo semplice e rapido creazione di esperimenti premonitori di analisi, ad esempio esperimenti di stima della domanda, utilizzare gli algoritmi R o i linguaggi di programmazione di pitone e un'interfaccia semplice di trascinamento della selezione.
    -   È possibile scaricare Dynamics 365 per gli esperimenti di previsione della domanda operazioni, modificarli per soddisfare i requisiti aziendali, pubblicare come servizio Web in azzurro e utilizzarli per generare previsioni della domanda. In esperimenti disponibili per il download se è stato acquistato Dynamics 365 per la sottoscrizione delle operazioni per un Pianificazione di produzione come utente del livello società.
    -   È possibile scaricare uno degli esperimenti di previsione della domanda attualmente disponibili dalla [raccolta di analisi dei dati Cortana](https://gallery.cortanaanalytics.com/). Benché che Dynamics 365 per gli esperimenti di previsione della domanda delle operazioni viene eseguita automaticamente con Dynamics 365 per le operazioni, clienti e partner devono utilizzare l'integrazione di esperimenti che del [] raccolta dell'analisi dei dati di Cortana (https://gallery.cortanaanalytics.com/). Di conseguenza, il esperimenti [raccolta dell'analisi dei dati di Cortana] (https://gallery.cortanaanalytics.com/) non è diretto utilizzare come Dynamics 365 per gli esperimenti di previsione della domanda delle operazioni. È necessario modificare il codice di esperimenti in modo che utilizzino Dynamics 365 per Application Programming Interface (API) delle operazioni.
    -   È possibile creare esperimenti personalizzati Microsoft Azure Machine Learning Studio, pubblicarli come servizi in Azure e utilizzarli per generare le previsioni della domanda.
    -   Se non sono richieste prestazioni elevate, o l'elaborazione di una grade quantità di dati, è possibile utilizzare la versione di prova gratuita di Machine Learning. Si consiglia di iniziare sempre da questo livello, in particolare durante le fasi di test e implementazione. Se sono richieste prestazioni elevate e spazio di archiviazione aggiuntivo, è possibile utilizzare il livello standard di Machine Learning. Questo livello richiede una sottoscrizione di Azure e comporta costi aggiuntivi. Per dettagli sui prezzi di Machine Learning, vedere <http://aka.ms/machine-learning-price-info>.
-   ** Riduzione di previsione in qualsiasi punto di disaccoppiamento ** - previsione della domanda di Dynamics 365 per le configurazioni di operazioni su queste funzionalità, che consente di programmare sia il dipendente che la domanda indipendente da qualsiasi punto di disaccoppiamento.

## <a name="basic-flow-in-demand-forecasting"></a>Flusso di base nella previsione della domanda
Nel seguente diagramma viene visualizzato il flusso di base nella previsione della domanda. 

[diagramma dell'introduzione di previsione della domanda![(]. /media/demand-forecasting-introduction.png)](. /media/demand-forecasting-introduction.png)

La generazione di previsione della domanda inizia in Dynamics 365 per le operazioni. I dati transazionali dello storico da Dynamics 365 per il database transazionale delle operazioni vengono raccolti e vengono immessi una tabella dell'organizzazione. In questa tabella dell'organizzazione successivamente viene immessa al servizio di apprendimento automatico. Realizzando la personalizzazione minima, è possibile inserire le varie origini dati della tabella dell'organizzazione. Le origini dati possono includere i file di Microsoft Excel, i valori separati da virgole di (CSV) di valore e dati di Microsoft Dynamics AX 2009 e da Microsoft Dynamics AX 2012. Di conseguenza, è possibile generare previsioni della domanda e vengono presi in considerazione i dati dello storico che sono sparsi tra i sistemi. Tuttavia, l'anagrafica, ad esempio i nomi degli articoli e le unità di misura, devono essere uguali tra le varie origini dati.

Se si utilizza Dynamics 365 per gli esperimenti di apprendimento automatico di previsione della domanda delle operazioni, cercare il il migliore rettifica tra cinque metodi di previsioni di serie cronologiche per calcolare una previsione di base. I parametri di questi metodi di previsioni vengono gestiti in Dynamics 365 per le operazioni. 

Le previsioni, i dati dello storico e le eventuali modifiche apportate alle previsioni della domanda nelle precedenti non saranno quindi disponibili in Dynamics 365 per le operazioni. 

È possibile utilizzare Dynamics 365 per le operazioni corrente e per modificare le previsioni di base. Le correzioni manuali devono essere autorizzate prima che le previsioni possano essere utilizzate per la programmazione.

## <a name="limitations"></a>Limiti
La previsione della domanda in Dynamics 365 per le operazioni è uno strumento che aiuti i clienti nel settore manufatturiera a creare i processi di previsioni. Offrono la funzionalità di base di una soluzione di previsione della domanda e vengono pianificati in modo che possa essere facilmente essere estesi. La previsione della domanda non sia il migliore rettifica per i clienti in settori ad esempio vendita al dettaglio, la vendita all'ingrosso, di immagazzinamento, il trasporto, o altri servizi professionali.

<a name="see-also"></a>Vedere anche
--------

[Demand forecasting setup](demand-forecasting-setup.md)

[Generating a statistical baseline forecast](generate-statistical-baseline-forecast.md)

[Making manual adjustments to the baseline forecast](manual-adjustments-baseline-forecast.md)

[Authorizing the adjusted forecast](authorize-adjusted-forecast.md)

[Monitoring forecast accuracy](monitor-forecast-accuracy.md)

[Remove outliers from historical transaction data when calculating a demand forecast](remove-historical-outliers-calculating-demand-forecast.md)


