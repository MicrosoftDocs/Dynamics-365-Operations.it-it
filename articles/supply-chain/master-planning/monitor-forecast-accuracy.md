---
title: Monitorare la precisione previsione
description: In questo articolo vengono descritti i tipi di previsione di previsione calcolati in Microsoft Dynamics 365 for Finance and Operations e viene illustrato come è possibile visualizzare i valori di previsione.
author: roxanadiaconu
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqDemPlanForecastDetails
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 72863
ms.assetid: 810a0d63-f4c6-4167-b2b3-a178b74ead89
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d7070c15f9ee23cfdba871af68d1fc5954735651
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2019
ms.locfileid: "356417"
---
# <a name="monitor-forecast-accuracy"></a>Monitorare la precisione previsione

[!include [banner](../includes/banner.md)]

In questo articolo vengono descritti i tipi di previsione di previsione calcolati in Microsoft Dynamics 365 for Finance and Operations e viene illustrato come è possibile visualizzare i valori di previsione.

Finance and Operations calcola i seguenti tipi di precisione della previsione:

-   Previsione di precisione storica, confrontando la previsione storica utilizzata nella pianificazione generale con la domanda storica. Per visualizzare i valori (sia i valori assoluti che i valori percentuali) per la precisione di previsione storica, fare clic su **Visualizza precisione** nella pagina **Dettagli previsione della domanda**.
-   Precisione stimata del modello previsionale utilizzato per generare previsioni. È possibile visualizzare la percentuale di previsione in **Dettagli modello - Errore medio assoluto percentuale** nella pagina **Dettagli previsione della domanda**. 

**Nota:** se si utilizza il servizio Microsoft Azure Machine Learning per la previsione della domanda in Finance and Operations, il calcolo della previsione del modello interno si basa sul set di dati di prova. Per specificare le dimensioni del set di dati di prova, impostare il parametro **TEST\_SET\_SIZE\_PERCENT** nella pagina **Parametri di previsione della domanda**. Ad esempio, se si imposta il valore su **20**, l'ultimo 20% dei dati storici verrà utilizzato per calcolare la previsione del modello interno.


<a name="additional-resources"></a>Risorse aggiuntive
--------

[Autorizzazione della previsione rettificata](authorize-adjusted-forecast.md)

[Eliminare gli outlier dai dati di transazione storici quando si calcolo una previsione della domanda](remove-historical-outliers-calculating-demand-forecast.md)



