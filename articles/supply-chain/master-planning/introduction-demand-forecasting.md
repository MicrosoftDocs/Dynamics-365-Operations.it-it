---
title: Cenni preliminari sulla previsione della domanda
description: La previsione della domanda viene utilizzata per prevedere la domanda indipendente da ordini cliente e la domanda dipendente in qualsiasi punto di disaccoppiamento per gli ordini cliente. Le regole avanzate di riduzione della previsione della domanda forniscono una soluzione ideale per la personalizzazione in massa.
author: roxanadiaconu
manager: tfehr
ms.date: 07/07/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqDemPlanCreateForecastDialog
audience: Application User
ms.reviewer: kamaybac
ms.custom: 72004
ms.assetid: 916707c9-1333-460f-a0fa-4e95f6fda2ad
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5b285b973f0fee3b253f63f49e3f5b4893d9dd86
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5207041"
---
# <a name="demand-forecasting-overview"></a>Cenni preliminari sulla previsione della domanda

[!include [banner](../includes/banner.md)]

La previsione della domanda viene utilizzata per prevedere la domanda indipendente da ordini cliente e la domanda dipendente in qualsiasi punto di disaccoppiamento per gli ordini cliente. Le regole avanzate di riduzione della previsione della domanda forniscono una soluzione ideale per la personalizzazione in massa.

Per generare la previsione di base, viene trasmesso un riepilogo delle transazioni storiche a Microsoft Azure Machine Learning ospitato in Azure. Poiché il servizio non è condiviso tra gli utenti, può essere facilmente personalizzato per soddisfare i requisiti di settore specifici. È possibile utilizzare Supply Chain Management per visualizzare la previsione, modificarla e per visualizzare gli indicatori di prestazione chiave (KPI) relativi all'accuratezza di previsione.

> [!NOTE]
> Microsoft Azure Machine Learning Studio (classico) è necessario per la generazione di previsioni con l'apprendimento automatico. A partire da gennaio 2021, è disponibile in Giappone orientale, Stati Uniti centro-meridionali, Asia sud-orientale, Stati Uniti centro-occidentali ed Europa occidentale. Per informazioni aggiornate sulla disponibilità corrente, vedere [Prodotti Azure per area geografica.](https://azure.microsoft.com/global-infrastructure/services/?regions=all&products=machine-learning-studio)

## <a name="key-features-of-demand-forecasting"></a>Funzionalità principali della previsione della domanda

Di seguito vengono descritte alcune delle funzionalità principali della previsione della domanda:

- Generazione dei una previsione di base statistica basata sui dati transazione storici.
- Utilizzo di un set dinamico di dimensioni di previsione.
- Visualizzazione di tendenze nella domanda, intervalli valori di fiducia e correzioni della previsione.
- Autorizzazione della previsione corretta per l'utilizzo nei processi di pianificazione.
- Rimozione outlier.
- Creazione di misure della precisione di previsione.

## <a name="major-themes-in-demand-forecasting"></a>Temi principali nella previsione della domanda

Nella previsione della domanda sono implementati tre temi principali:

- **Modularità**: la previsioni della domanda è modulare e facile da configurare. È possibile attivare o disattivare la funzionalità modificando la chiave di configurazione in **Commercio** &gt; **Previsione di magazzino** &gt; **Previsione della domanda**.
- **Riutilizzo dello stack Microsoft** - Machine Learning, che ora fa parte di Analytics Suite di Microsoft Cortana, consente di creare in modo facile e rapido esperimenti di analisi predittive, ad esempio esperimenti di stima della domanda, tramite l'uso di algoritmi R o linguaggi di programmazione Python e una semplice interfaccia basata sul trascinamento della selezione.
  - È possibile scaricare gli esperimenti di previsione della domanda, modificarli per soddisfare i requisiti aziendali, pubblicarli come servizio Web in Azure e utilizzarli per generare previsioni della domanda. Gli esperimenti sono disponibili per il download se si dispone di una sottoscrizione di Supply Chain Management destinata a un responsabile di pianificazione come utente di livello di aziendale.
  - È possibile scaricare uno degli esperimenti di previsione della domanda attualmente disponibili dalla [raccolta di analisi dei dati Cortana](https://gallery.cortanaanalytics.com/). Mentre gli esperimenti di previsione della domanda vengono automaticamente integrati in Supply Chain Management, l'integrazione degli esperimenti scaricati dalla [raccolta di analisi dei dati di Cortana](https://gallery.cortanaanalytics.com/) deve essere gestita dai clienti e dai partner. Di conseguenza, gli esperimenti della [raccolta di analisi dei dati di Cortana](https://gallery.cortanaanalytics.com/) non risultano immediati da utilizzare come gli esperimenti di previsione della domanda di Finance and Operations. È necessario modificare il codice degli esperimenti in modo che venga utilizzata l'API di Finance and Operations.
  - È possibile creare esperimenti personalizzati in Microsoft Azure Machine Learning Studio (classico), pubblicarli come servizi in Azure e utilizzarli per generare le previsioni della domanda.
  - Se non sono richieste prestazioni elevate, o l'elaborazione di una grade quantità di dati, è possibile utilizzare la versione di prova gratuita di Machine Learning. Si consiglia di iniziare sempre da questo livello, in particolare durante le fasi di test e implementazione. Se sono richieste prestazioni elevate e spazio di archiviazione aggiuntivo, è possibile utilizzare il livello standard di Machine Learning. Questo livello richiede una sottoscrizione di Azure e comporta costi aggiuntivi. Per dettagli sui prezzi di Machine Learning, vedere [Prezzi di Machine Learning Studio](https://aka.ms/machine-learning-price-info).
- **Riduzione della previsione in qualsiasi punto di disaccoppiamento**: la previsione della domanda è basata su questa funzionalità, che consente di prevedere la domanda dipendente e indipendente da qualsiasi punto di disaccoppiamento.

## <a name="basic-flow-in-demand-forecasting"></a>Flusso di base nella previsione della domanda

Nel seguente diagramma viene visualizzato il flusso di base nella previsione della domanda.

[![diagramma di introduzione alla previsione della domanda](./media/demand-forecasting-introduction.png)](./media/demand-forecasting-introduction.png)

La generazione di previsione della domanda inizia in Supply Chain Management. I dati transazionali storici del database transazionale di Supply Chain Management vengono raccolti e usati per popolare una tabella di gestione temporanea. Questa tabella viene successivamente immessa nel servizio di Machine Learning. Con una personalizzazione minima, è possibile inserire le varie origini dati nella tabella di gestione temporanea. Le origini dati possono includere file di Microsoft Excel, file CSV e dati di Microsoft Dynamics AX 2009 e di Microsoft Dynamics AX 2012. È di conseguenza possibile generare previsioni della domanda che considerino i dati storici che sono sparsi in più sistemi. Tuttavia, l'anagrafica, ad esempio i nomi degli articoli e le unità di misura, devono essere uguali tra le varie origini dati.

Se si utilizzano gli esperimenti di Machine Learning di previsione della domanda questi cercano il metodo più adatto tra i cinque disponibili per calcolare una previsione di base. I parametri per i metodi di previsione vengono gestiti in Supply Chain Management.

Le previsioni, i dati storici e tutte le modifiche effettuate nelle previsioni della domanda in iterazioni precedenti sono quindi disponibili in Supply Chain Management.

È possibile utilizzare Supply Chain Management per visualizzare e modificare le previsioni di base. Le correzioni manuali devono essere autorizzate prima che le previsioni possano essere utilizzate per la programmazione.

## <a name="limitations"></a>Limiti

Le previsione della domanda è uno strumento che consente ai clienti del settore manifatturiero di creare i processi di previsioni. Questo strumento offre le funzionalità di base di una soluzione di previsione della domanda ed è progettato in modo che possa essere facilmente esteso. La previsione della domanda potrebbe non essere la soluzione migliore per i clienti di settori come commercio, vendita all'ingrosso, immagazzinamento, trasporto o altri servizi professionali.

### <a name="demand-forecast-variant-conversion-limitation"></a>Limitazione della conversione della variante di previsione della domanda

L'unità di misura (UOM) per conversione della variante non è completamente supportata quando si genera la previsione della domanda se l'UOM di inventario è diverso dall'UOM di previsione della domanda.

La generazione di previsioni ( **UOM inventario > UOM previsione domanda**) utilizza la conversione UOM di prodotto. Quando si caricano dati storici per la generazione della previsione della domanda, la conversione UOM a livello di prodotto verrà sempre utilizzata durante la conversione dall'UOM di inventario nell'UOM di previsione della domanda, anche se sono state definite conversioni a livello di variante.

La prima parte dell'autorizzazione della previsione (**UOM previsione domanda > UOM inventario**) utilizza la conversione UOM di prodotto. La seconda parte dell'autorizzazione della previsione (**UOM inventario > UOM vendite**) utilizza la conversione UOM variante. Quando viene autorizzata la previsione della domanda generata, la conversione dell'UOM di previsione della domanda in UOM di inventario verrà effettuata utilizzando la conversione UOM a livello di prodotto. Allo stesso tempo, la conversione tra l'unità di inventario e l'UOM di vendite rispetterà le conversioni definite a livello di variante.

Si noti che l'UOM di previsione della domanda non deve avere alcun significato specifico. Può essere definito come "Unità di previsione della domanda". Per ciascuno dei prodotti, è possibile specificare la conversione 1: 1 con l'UOM di inventario.

## <a name="additional-resources"></a>Risorse aggiuntive

[Impostazione della previsione della domanda](demand-forecasting-setup.md)

[Generare una previsione di base statistica](generate-statistical-baseline-forecast.md)

[Implementare correzioni manuali nella previsione di base](manual-adjustments-baseline-forecast.md)

[Autorizzare una previsione corretta](authorize-adjusted-forecast.md)

[Monitorare la precisione della previsione](monitor-forecast-accuracy.md)

[Eliminare gli outlier dai dati di transazione storici quando si calcolo una previsione della domanda](remove-historical-outliers-calculating-demand-forecast.md)

[Estendere la funzionalità di previsione della domanda](https://www.youtube.com/watch?v=4OIKIXLiNjI&feature=youtu.be)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]