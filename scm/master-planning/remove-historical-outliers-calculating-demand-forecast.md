---
title: Eliminare gli outlier dai dati di transazione storici quando si calcolo una previsione della domanda
description: "In questo articolo viene descritto come escludere gli outlier dai dati storici utilizzati per calcolare una previsione della domanda. Escludendo gli outlier, è possibile migliorare la precisione previsione."
author: roxanadiaconu
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ReqDemPlanForecastParameters, ReqDemPlanOutlierQuerySetup
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 72621
ms.assetid: 88a964af-14eb-4c5c-945b-388e5908362c
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: ea3f08b20e25af6ebb738c2373b65532d74a0c80
ms.contentlocale: it-it
ms.lasthandoff: 08/29/2017

---

# <a name="remove-outliers-from-historical-transaction-data-when-calculating-a-demand-forecast"></a><span data-ttu-id="98cc7-104">Eliminare gli outlier dai dati di transazione storici quando si calcolo una previsione della domanda</span><span class="sxs-lookup"><span data-stu-id="98cc7-104">Remove outliers from historical transaction data when calculating a demand forecast</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="98cc7-105">In questo articolo viene descritto come escludere gli outlier dai dati storici utilizzati per calcolare una previsione della domanda.</span><span class="sxs-lookup"><span data-stu-id="98cc7-105">This article describes how to exclude outliers from the historical data that is used to calculate a demand forecast.</span></span> <span data-ttu-id="98cc7-106">Escludendo gli outlier, è possibile migliorare la precisione previsione.</span><span class="sxs-lookup"><span data-stu-id="98cc7-106">By excluding outliers, you can improve forecast accuracy.</span></span>

<span data-ttu-id="98cc7-107">È possibile escludere gli outlier per migliorare la precisione previsione.</span><span class="sxs-lookup"><span data-stu-id="98cc7-107">You can exclude outliers to improve forecast accuracy.</span></span> <span data-ttu-id="98cc7-108">Questa attività è facoltativa.</span><span class="sxs-lookup"><span data-stu-id="98cc7-108">This is an optional task.</span></span> <span data-ttu-id="98cc7-109">Ecco una panoramica del processo:</span><span class="sxs-lookup"><span data-stu-id="98cc7-109">Here is an overview of the process:</span></span>

1.  <span data-ttu-id="98cc7-110">Fare clic su **Pianificazione generale** &gt; **Impostazioni** &gt; **Previsione della domanda** &gt; **Rimozione outlier** per aprire la pagina **Rimozione outlier**, in cui è possibile utilizzare una query per selezionare le transazioni da escludere.</span><span class="sxs-lookup"><span data-stu-id="98cc7-110">Click **Master planning** &gt; **Setup** &gt; **Demand forecasting** &gt; **Outlier removal** to open the **Outlier removal** page, where you can use a query to select the transactions to exclude.</span></span>
2.  <span data-ttu-id="98cc7-111">Selezionare la società per la quale viene applicata la query, quindi immettere un nome e una descrizione.</span><span class="sxs-lookup"><span data-stu-id="98cc7-111">Select the company that the query applies to, and then enter a name and description.</span></span> <span data-ttu-id="98cc7-112">Il campo **Data query** viene impostato automaticamente sulla data corrente.</span><span class="sxs-lookup"><span data-stu-id="98cc7-112">The **Query date** field is automatically set to the current date.</span></span>
3.  <span data-ttu-id="98cc7-113">Selezionare la casella di controllo **Attiva** per escludere le transazioni trovate dalla query dai i dati storici.</span><span class="sxs-lookup"><span data-stu-id="98cc7-113">Select the **Active** check box to exclude the transactions that the query finds from the historical data.</span></span> <span data-ttu-id="98cc7-114">Questa impostazione diventerà effettive quando si crea una previsione di base.</span><span class="sxs-lookup"><span data-stu-id="98cc7-114">This setting will take effect when you create a baseline forecast.</span></span>
4.  <span data-ttu-id="98cc7-115">Nella pagina **Query di rimozione outlier** è possibile aggiungere, rimuovere e selezionare i criteri che definiscono le transazioni che verranno escluse quando viene calcolata la previsione di base.</span><span class="sxs-lookup"><span data-stu-id="98cc7-115">On the **Outlier removal query** page, you can add, remove, and select the criteria that define which transactions will be excluded when the baseline forecast is calculated.</span></span> <span data-ttu-id="98cc7-116">Ad esempio, selezionare un articolo o una transazione di ordini specifici che si desidera escludere.</span><span class="sxs-lookup"><span data-stu-id="98cc7-116">For example, select a specific item or order transaction to exclude.</span></span>
5.  <span data-ttu-id="98cc7-117">Fare clic su **Visualizza transazioni**.</span><span class="sxs-lookup"><span data-stu-id="98cc7-117">Click **Display transactions**.</span></span> <span data-ttu-id="98cc7-118">Le pagine **Transazioni outlier** elenca le transazioni che soddisfano i criteri definiti nella query e che verranno esclusi dai dati storici quando viene calcolata la previsione della domanda.</span><span class="sxs-lookup"><span data-stu-id="98cc7-118">The **Outlier transactions** page lists the transactions that meet the criteria that you defined in the query, and that will be excluded from the historical data when the demand forecast is calculated.</span></span>

<span data-ttu-id="98cc7-119">**Nota:** È inoltre possibile creare una query in base a una query esistente.</span><span class="sxs-lookup"><span data-stu-id="98cc7-119">**Note:** You can also create a query that is based on an existing query.</span></span> <span data-ttu-id="98cc7-120">Selezionare la query da copiare, quindi fare clic su **Duplicato**.</span><span class="sxs-lookup"><span data-stu-id="98cc7-120">Select the query to copy, and then click **Duplicate**.</span></span> <span data-ttu-id="98cc7-121">Nel campo **Data query** viene identifica la versione.</span><span class="sxs-lookup"><span data-stu-id="98cc7-121">The **Query date** field identifies the version.</span></span> <span data-ttu-id="98cc7-122">È possibile utilizzare la query come è, oppure fare clic su **Modifica query** per modificare i criteri.</span><span class="sxs-lookup"><span data-stu-id="98cc7-122">You can use the query as it is, or you can click **Edit query** to modify the criteria.</span></span> <span data-ttu-id="98cc7-123">Si può scegliere di modificare il nome e la descrizione della nuova query.</span><span class="sxs-lookup"><span data-stu-id="98cc7-123">You can optionally modify the name and description of the new query.</span></span>

<a name="see-also"></a><span data-ttu-id="98cc7-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="98cc7-124">See also</span></span>
--------

[<span data-ttu-id="98cc7-125">Introduzione alla previsione della domanda</span><span class="sxs-lookup"><span data-stu-id="98cc7-125">Introduction to demand forecasting</span></span>](introduction-demand-forecasting.md)

[<span data-ttu-id="98cc7-126">Monitoraggio della precisione previsione</span><span class="sxs-lookup"><span data-stu-id="98cc7-126">Monitoring forecast accuracy</span></span>](monitor-forecast-accuracy.md)




