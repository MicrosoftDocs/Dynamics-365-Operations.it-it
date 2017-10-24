---
title: Autorizzare una previsione modificata
description: "Non tutti i dati di previsione devono essere autorizzati immediatamente. In questo articolo viene illustrato come è possibile specificare il periodo per cui una previsione viene autorizzata. Viene inoltre illustrato come è possibile autorizzare la previsione per le società e i modelli previsionali specifici."
author: roxanadiaconu
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ReqDemPlanImportForecastDialog
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 72734
ms.assetid: cb8fd809-605a-4a8b-a390-636edfec21f9
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 399a7a21ec71fe50e280ccb24699cda76d571990
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---

# <a name="authorize-an-adjusted-forecast"></a>Autorizzare una previsione modificata

[!include[banner](../includes/banner.md)]


Non tutti i dati di previsione devono essere autorizzati immediatamente. In questo articolo viene illustrato come è possibile specificare il periodo per cui una previsione viene autorizzata. Viene inoltre illustrato come è possibile autorizzare la previsione per le società e i modelli previsionali specifici.

Non tutti i dati di previsione devono essere autorizzati immediatamente. È possibile specificare la data di inizio e di fine del periodo per cui la previsione viene autorizzata. Questa funzionalità consente di bloccare intervalli specifici. 

Le date di inizio e di fine specificate devono corrispondere alle date di inizio e di fine dell'intervallo in cui la previsione viene generata. Il sistema applica questa restrizione e rettifica automaticamente le date, se la rettifica è richiesta. 

Nella scheda **Dettagli** della pagina **Autorizzazione** è possibile visualizzare i dettagli sull'ultima previsione generata. 

È possibile selezionare le società e i modelli previsionali per autorizzare la previsione da utilizzare. Per impostazione predefinita, la griglia include tutte le società per cui la domanda di previsione è stata creata. Per ogni società, il modello previsionale che corrisponde al piano previsionale corrente impostato nei parametri di pianificazione generale è precompilato. Tuttavia, è possibile modificare questo modello previsionale impostandolo su qualsiasi modello previsionale che appartiene alla società. Se non è stato generato alcun dato di domanda della previsione per una società selezionata, verrà visualizzato un messaggio di avviso al momento dell'importazione. 

È molto importante capire il funzionamento della casella di controllo **Salva le rettifiche manuali apportate alla previsione della domanda di base**. Se sono state apportate rettifiche manuali alla previsione di base statistica, i valori rettificati vengono autorizzati per l'utilizzo anche se questa casella di controllo è deselezionata. Tuttavia, le modifiche vengono rimosse dopo l'autorizzazione. Di conseguenza, alla successiva generazione di una previsione, quest'ultima è solo una previsione statistica e non dispone di sostituzione manuali, anche se l'opzione **Trasferisci correzioni manuali alla previsione della domanda** è selezionata. Di conseguenza, è possibile considerare la casella di controllo **Salva le rettifiche manuali apportate alla previsione della domanda di base** come un meccanismo che consente di mantenere o rimuovere tutte le modifiche manuali.

<a name="see-also"></a>Vedere anche
--------

[Implementazione di correzioni manuali nella previsione di base](manual-adjustments-baseline-forecast.md)

[Monitoraggio della precisione previsione](monitor-forecast-accuracy.md)




