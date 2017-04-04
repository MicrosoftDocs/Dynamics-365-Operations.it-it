---
title: Eliminare gli outlier dai dati di transazione storici quando si calcolo una previsione della domanda
description: "In questo articolo viene descritto come escludere gli outlier dai dati storici utilizzati per calcolare una previsione della domanda. Escludendo gli outlier, è possibile migliorare la precisione previsione."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: ReqDemPlanForecastParameters, ReqDemPlanOutlierQuerySetup
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 72621
ms.assetid: 88a964af-14eb-4c5c-945b-388e5908362c
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: 6f44e1ce566781f1586203528d55b13b28001a2c
ms.lasthandoff: 03/31/2017


---

# <a name="remove-outliers-from-historical-transaction-data-when-calculating-a-demand-forecast"></a>Eliminare gli outlier dai dati di transazione storici quando si calcolo una previsione della domanda

In questo articolo viene descritto come escludere gli outlier dai dati storici utilizzati per calcolare una previsione della domanda. Escludendo gli outlier, è possibile migliorare la precisione previsione.

È possibile escludere i valori erratici per migliorare l'accuratezza di previsione. Questa attività è facoltativa. Ecco una panoramica del processo:

1.  Fare clic su ** pianificazione generale ** &gt; ** impostazione ** &gt; ** previsione della domanda ** &gt; ** rimozione di valore erratico ** aprire ** rimozione di valore erratico ** la pagina, in cui è possibile utilizzare una query per selezionare le transazioni da escludere.
2.  Selezionare la società per la quale viene applicata la query, quindi immettere un nome e una descrizione. Il campo **Data query** viene impostato automaticamente sulla data corrente.
3.  Selezionare la casella di controllo **Attiva** per escludere le transazioni trovate dalla query dai i dati storici. Questa impostazione diventerà effettive quando si crea una previsione di base.
4.  Nella pagina **Query di rimozione outlier** è possibile aggiungere, rimuovere e selezionare i criteri che definiscono le transazioni che verranno escluse quando viene calcolata la previsione di base. Ad esempio, selezionare un articolo o una transazione di ordini specifici che si desidera escludere.
5.  Fare clic su **Visualizza transazioni**. Le pagine **Transazioni outlier** elenca le transazioni che soddisfano i criteri definiti nella query e che verranno esclusi dai dati storici quando viene calcolata la previsione della domanda.

**Nota:** È inoltre possibile creare una query in base a una query esistente. Selezionare la query da copiare, quindi fare clic su **Duplicato**. Nel campo **Data query** viene identifica la versione. È possibile utilizzare la query come è, oppure fare clic su **Modifica query** per modificare i criteri. Si può scegliere di modificare il nome e la descrizione della nuova query.

<a name="see-also"></a>Vedere anche
--------

[Introduction to demand forecasting](introduction-demand-forecasting.md)

[Monitoring forecast accuracy](monitor-forecast-accuracy.md)


