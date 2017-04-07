---
title: Autorizzare un importo di previsioni
description: "Non tutti i dati di previsione devono essere autorizzati immediatamente. In questo articolo viene illustrato come è possibile specificare il periodo per cui una previsione viene autorizzata. Viene inoltre illustrato come è possibile autorizzare la previsione per le società e i modelli previsionali specifici."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: ReqDemPlanImportForecastDialog
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 72734
ms.assetid: cb8fd809-605a-4a8b-a390-636edfec21f9
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: f151f4b4290df0b2bf1b5d1159654bd248a439b1
ms.lasthandoff: 03/31/2017


---

# <a name="authorize-an-adjusted-forecast"></a>Autorizzare un importo di previsioni

Non tutti i dati di previsione devono essere autorizzati immediatamente. In questo articolo viene illustrato come è possibile specificare il periodo per cui una previsione viene autorizzata. Viene inoltre illustrato come è possibile autorizzare la previsione per le società e i modelli previsionali specifici.

Non tutti i dati di previsione devono essere autorizzati immediatamente. È possibile specificare la data di inizio e di fine del periodo per cui la previsione viene autorizzata. Questa funzionalità consente di bloccare intervalli specifici. 

Le date di inizio e di fine specificata devono corrispondere alle date di inizio e di fine dell'intervallo che la previsione viene generata. Il sistema applicata questa restrizione automaticamente e rettificare le date, se la correzione è obbligatoria. 

Nella scheda **Dettagli** della pagina **Autorizzazione** è possibile visualizzare i dettagli sull'ultima previsione generata. 

È possibile selezionare le società e i modelli previsionali per autorizzare la previsione da utilizzare. Per impostazione predefinita, la griglia include tutte le società per cui la domanda di previsione è stata creata. Per ogni società, il modello previsionale che corrisponde al piano previsionale corrente impostato nei parametri di pianificazione generale è precompilato. Tuttavia, è possibile modificare questo modello previsionale impostandolo su qualsiasi modello previsionale che appartiene alla società. Se non è stato generato alcun dato di domanda della previsione per una società selezionata, verrà visualizzato un messaggio di avviso al momento dell'importazione. 

È molto importante capire il funzionamento della casella di controllo **Salva le rettifiche manuali apportate alla previsione della domanda di base**. Se è stata proceduto rettifiche manuali alla previsione di base statistiche, i valori rettificati autorizzati ad uso, anche se questa casella di controllo è deselezionata. Tuttavia, le modifiche vengono rimosse dopo l'autorizzazione. Di conseguenza, alla successiva generazione di una previsione, quest'ultima è solo una previsione statistica e non dispone di sostituzione manuali, anche se l'opzione **Trasferisci correzioni manuali alla previsione della domanda** è selezionata. Di conseguenza, è possibile considerare la casella di controllo **Salva le rettifiche manuali apportate alla previsione della domanda di base** come un meccanismo che consente di mantenere o rimuovere tutte le modifiche manuali.

<a name="see-also"></a>Vedere anche
--------

[Making manual adjustments to the baseline forecast](manual-adjustments-baseline-forecast.md)

[Monitoring forecast accuracy](monitor-forecast-accuracy.md)


