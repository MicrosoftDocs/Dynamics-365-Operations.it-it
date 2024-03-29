---
title: Eliminare gli outlier dai dati di transazione storici quando si calcolo una previsione della domanda
description: In questo articolo viene descritto come escludere gli outlier dai dati storici utilizzati per calcolare una previsione della domanda. Escludendo gli outlier, è possibile migliorare la precisione previsione.
author: t-benebo
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqDemPlanForecastParameters, ReqDemPlanOutlierQuerySetup, ReqDemPlanOutlierQueryPreview
audience: Application User
ms.reviewer: kamaybac
ms.custom: 72621
ms.assetid: 88a964af-14eb-4c5c-945b-388e5908362c
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d4e42e566cef774c1a25cf48ec131b74924868d0
ms.sourcegitcommit: 491ab9ae2b6ed991b4eb0317e396fef542d3a21b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2022
ms.locfileid: "9741096"
---
# <a name="remove-outliers-from-historical-transaction-data-when-calculating-a-demand-forecast"></a>Eliminare gli outlier dai dati di transazione storici quando si calcolo una previsione della domanda

[!include [banner](../includes/banner.md)]

In questo articolo viene descritto come escludere gli outlier dai dati storici utilizzati per calcolare una previsione della domanda. Escludendo gli outlier, è possibile migliorare la precisione previsione.

È possibile escludere gli outlier per migliorare la precisione previsione. Questa attività è facoltativa. Ecco una panoramica del processo:

1.  Fare clic su **Pianificazione generale** &gt; **Impostazioni** &gt; **Previsione della domanda** &gt; **Rimozione outlier** per aprire la pagina **Rimozione outlier**, in cui è possibile utilizzare una query per selezionare le transazioni da escludere.
2.  Selezionare la società per la quale viene applicata la query, quindi immettere un nome e una descrizione. Il campo **Data query** viene impostato automaticamente sulla data corrente.
3.  Selezionare la casella di controllo **Attiva** per escludere le transazioni trovate dalla query dai i dati storici. Questa impostazione diventerà effettive quando si crea una previsione di base.
4.  Nella pagina **Query di rimozione outlier** è possibile aggiungere, rimuovere e selezionare i criteri che definiscono le transazioni che verranno escluse quando viene calcolata la previsione di base. Ad esempio, selezionare un articolo o una transazione di ordini specifici che si desidera escludere.
5.  Fare clic su **Visualizza transazioni**. Le pagine **Transazioni outlier** elenca le transazioni che soddisfano i criteri definiti nella query e che verranno esclusi dai dati storici quando viene calcolata la previsione della domanda.

**Nota:** È inoltre possibile creare una query in base a una query esistente. Selezionare la query da copiare, quindi fare clic su **Duplicato**. Nel campo **Data query** viene identifica la versione. È possibile utilizzare la query come è, oppure fare clic su **Modifica query** per modificare i criteri. Si può scegliere di modificare il nome e la descrizione della nuova query.

## <a name="additional-resources"></a>Risorse aggiuntive

- [Panoramica previsioni della domanda](introduction-demand-forecasting.md)
- [Monitorare la precisione della previsione](monitor-forecast-accuracy.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]