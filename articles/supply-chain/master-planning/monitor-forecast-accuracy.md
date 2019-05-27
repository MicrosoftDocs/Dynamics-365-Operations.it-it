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
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "1556808"
---
# <a name="monitor-forecast-accuracy"></a><span data-ttu-id="276db-103">Monitorare la precisione previsione</span><span class="sxs-lookup"><span data-stu-id="276db-103">Monitor forecast accuracy</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="276db-104">In questo articolo vengono descritti i tipi di previsione di previsione calcolati in Microsoft Dynamics 365 for Finance and Operations e viene illustrato come è possibile visualizzare i valori di previsione.</span><span class="sxs-lookup"><span data-stu-id="276db-104">This article describes the types of forecast accuracy that Microsoft Dynamics 365 for Finance and Operations calculates, and explains how you can view the accuracy values.</span></span>

<span data-ttu-id="276db-105">Finance and Operations calcola i seguenti tipi di precisione della previsione:</span><span class="sxs-lookup"><span data-stu-id="276db-105">Finance and Operations calculates the following types of forecast accuracy:</span></span>

-   <span data-ttu-id="276db-106">Previsione di precisione storica, confrontando la previsione storica utilizzata nella pianificazione generale con la domanda storica.</span><span class="sxs-lookup"><span data-stu-id="276db-106">Historical forecast accuracy, by comparing the historical forecast that Master Planning uses with the historical demand.</span></span> <span data-ttu-id="276db-107">Per visualizzare i valori (sia i valori assoluti che i valori percentuali) per la precisione di previsione storica, fare clic su **Visualizza precisione** nella pagina **Dettagli previsione della domanda**.</span><span class="sxs-lookup"><span data-stu-id="276db-107">To view the values (both absolute values and percentage values) for historical forecast accuracy, click **Show accuracy** on the **Demand forecast details** page.</span></span>
-   <span data-ttu-id="276db-108">Precisione stimata del modello previsionale utilizzato per generare previsioni.</span><span class="sxs-lookup"><span data-stu-id="276db-108">The estimated accuracy of the forecasting model that is used to generate the predictions.</span></span> <span data-ttu-id="276db-109">È possibile visualizzare la percentuale di previsione in **Dettagli modello - Errore medio assoluto percentuale** nella pagina **Dettagli previsione della domanda**.</span><span class="sxs-lookup"><span data-stu-id="276db-109">You can view the accuracy percentage under **Model details - MAPE** on the **Demand forecast details** page.</span></span> 

<span data-ttu-id="276db-110">**Nota:** se si utilizza il servizio Microsoft Azure Machine Learning per la previsione della domanda in Finance and Operations, il calcolo della previsione del modello interno si basa sul set di dati di prova.</span><span class="sxs-lookup"><span data-stu-id="276db-110">**Note:** If you use the Finance and Operations Demand forecasting Microsoft Azure Machine Learning service, the calculation of internal model accuracy is based on the test data set.</span></span> <span data-ttu-id="276db-111">Per specificare le dimensioni del set di dati di prova, impostare il parametro **TEST\_SET\_SIZE\_PERCENT** nella pagina **Parametri di previsione della domanda**.</span><span class="sxs-lookup"><span data-stu-id="276db-111">To specify the size of the test data set, set the **TEST\_SET\_SIZE\_PERCENT** parameter on the **Demand forecasting parameters** page.</span></span> <span data-ttu-id="276db-112">Ad esempio, se si imposta il valore su **20**, l'ultimo 20% dei dati storici verrà utilizzato per calcolare la previsione del modello interno.</span><span class="sxs-lookup"><span data-stu-id="276db-112">For example, if you set the value to **20**, the last 20 percent of the historical data will be used to calculate the internal model accuracy.</span></span>


<a name="additional-resources"></a><span data-ttu-id="276db-113">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="276db-113">Additional resources</span></span>
--------

[<span data-ttu-id="276db-114">Autorizzazione della previsione rettificata</span><span class="sxs-lookup"><span data-stu-id="276db-114">Authorizing the adjusted forecast</span></span>](authorize-adjusted-forecast.md)

[<span data-ttu-id="276db-115">Eliminare gli outlier dai dati di transazione storici quando si calcolo una previsione della domanda</span><span class="sxs-lookup"><span data-stu-id="276db-115">Remove outliers from historical transaction data when calculating a demand forecast</span></span>](remove-historical-outliers-calculating-demand-forecast.md)



