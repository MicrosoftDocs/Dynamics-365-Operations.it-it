---
title: Importare dati storici per le previsioni della domanda
description: "Per ottenere le previsioni della domanda accurate, sono necessari i dati storici della domanda per singolo articolo o chiave di allocazione articolo. In questo argomento viene descritto come utilizzare le entità di dati per importare i dati storici della domanda da un sistema, in modo da disporre di uno storico più ampio dei dati di previsione della domanda."
author: roxanadiaconu
manager: AnnBe
ms.date: 05/10/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.assetid: 59c0d269-9db0-48e7-b8c7-9a388781a9ca
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 02daa312d74311432c0c468e3e691637dcf94157
ms.contentlocale: it-it
ms.lasthandoff: 11/03/2017

---

# <a name="import-historical-data-for-demand-forecasts"></a><span data-ttu-id="8c5da-104">Importare dati storici per le previsioni della domanda</span><span class="sxs-lookup"><span data-stu-id="8c5da-104">Import historical data for demand forecasts</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="8c5da-105">Per contribuire a garantire la correttezza delle previsioni della domanda, sono necessari tutti i dati storici della domanda che si possono ottenere per singolo articolo o chiave di allocazione articolo.</span><span class="sxs-lookup"><span data-stu-id="8c5da-105">To help guarantee the accuracy of demand forecasts, you must have as much historical demand data as you can get per item or item allocation key.</span></span> <span data-ttu-id="8c5da-106">Se i dati storici della domanda non sono stati ancora importati, utilizzare l'entità di dati **Domanda esterna storica** (ReqDemPlanHistoricalExternalDemandEntity) in Microsoft Dynamics 365 for Finance and Operations per importarli.</span><span class="sxs-lookup"><span data-stu-id="8c5da-106">If the historical demand data isn't already imported, use the **Historical external demand** (ReqDemPlanHistoricalExternalDemandEntity) data entity in Microsoft Dynamics 365 for Finance and Operations to import it.</span></span>

<span data-ttu-id="8c5da-107">Nell'area di lavoro **Gestione dei dati**, è possibile visualizzare una panoramica di tutti i campi relativi all'entità.</span><span class="sxs-lookup"><span data-stu-id="8c5da-107">In the **Data management** workspace, you can see an overview of all the fields in the entity.</span></span>

1. <span data-ttu-id="8c5da-108">Aprire l'area di lavoro **Gestione dei dati**.</span><span class="sxs-lookup"><span data-stu-id="8c5da-108">Open the **Data management** workspace.</span></span>
2. <span data-ttu-id="8c5da-109">Fare clic sul riquadro **Entità di dati**.</span><span class="sxs-lookup"><span data-stu-id="8c5da-109">Click the **Data entities** tile.</span></span>
3. <span data-ttu-id="8c5da-110">Ricercare nell'elenco delle entità **Domanda esterna storica**.</span><span class="sxs-lookup"><span data-stu-id="8c5da-110">Search the entity list for **Historical external demand**.</span></span>
4. <span data-ttu-id="8c5da-111">Fare clic su **Campi di destinazione**.</span><span class="sxs-lookup"><span data-stu-id="8c5da-111">Click **Target fields**.</span></span> <span data-ttu-id="8c5da-112">I seguenti campi di entità sono obbligatori: sito (**DeliveringSiteId**), data (**DemandDate**), quantità (**DemandQuantity**) e numero di articolo (**ItemNumber**) o chiave di allocazione articolo (**ProductAllocationKeyId**).</span><span class="sxs-lookup"><span data-stu-id="8c5da-112">The following entity fields are mandatory: site (**DeliveringSiteId**), date (**DemandDate**), quantity (**DemandQuantity**), and either item number (**ItemNumber**) or item allocation key (**ProductAllocationKeyId**).</span></span>

<span data-ttu-id="8c5da-113">Per utilizzare questa entità di dati, è necessario disporre di un file di Microsoft Excel o un file con valori separati da virgole (CSV) contenente i dati storici della domanda.</span><span class="sxs-lookup"><span data-stu-id="8c5da-113">To use the data entity, you must have a Microsoft Excel file or comma-separated values (CSV) file that contains the historical demand data.</span></span> <span data-ttu-id="8c5da-114">Nel seguente esempio viene illustrato come importare i dati da un file CSV.</span><span class="sxs-lookup"><span data-stu-id="8c5da-114">The following example shows how to import the data from a CSV file.</span></span>

## <a name="example"></a><span data-ttu-id="8c5da-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="8c5da-115">Example</span></span>

<span data-ttu-id="8c5da-116">È possibile utilizzare il seguente file come esempio.</span><span class="sxs-lookup"><span data-stu-id="8c5da-116">You can use the following file as an example.</span></span> <span data-ttu-id="8c5da-117">Scaricare [HistoricalDemandData](https://mbs.microsoft.com/customersource/northamerica/AX/learning/documentation/how-to-articles/365OperationsDemandForecast).</span><span class="sxs-lookup"><span data-stu-id="8c5da-117">Download the [HistoricalDemandData](https://mbs.microsoft.com/customersource/northamerica/AX/learning/documentation/how-to-articles/365OperationsDemandForecast).</span></span> <span data-ttu-id="8c5da-118">Questo file contiene i dati storici della domanda per l'articolo D0001.</span><span class="sxs-lookup"><span data-stu-id="8c5da-118">This file contains the historical demand data for item D0001.</span></span> <span data-ttu-id="8c5da-119">Contiene solo i seguenti campi obbligatori: sito, quantità e data della domanda.</span><span class="sxs-lookup"><span data-stu-id="8c5da-119">It contains only the following mandatory fields: site, quantity, and the demand date.</span></span>

1. <span data-ttu-id="8c5da-120">Selezionare la società in cui importare i dati storici della domanda.</span><span class="sxs-lookup"><span data-stu-id="8c5da-120">Select the company to import the historical demand data into.</span></span>
2. <span data-ttu-id="8c5da-121">Aprire l'area di lavoro **Gestione dei dati**.</span><span class="sxs-lookup"><span data-stu-id="8c5da-121">Open the **Data management** workspace.</span></span>
3. <span data-ttu-id="8c5da-122">Fare clic sul riquadro **Importa**.</span><span class="sxs-lookup"><span data-stu-id="8c5da-122">Click the **Import** tile.</span></span>
4. <span data-ttu-id="8c5da-123">Immettere un nome per il progetto di importazione, ad esempio **Importare dati storici della domanda per l'articolo D0001**.</span><span class="sxs-lookup"><span data-stu-id="8c5da-123">Enter a name for the import project, such as **Import historical demand for item D0001**.</span></span>
5. <span data-ttu-id="8c5da-124">Nel campo **Formato dati di origine**, selezionare il formato del file da importare.</span><span class="sxs-lookup"><span data-stu-id="8c5da-124">In the **Source data format** field, select the file format of the file that you're importing.</span></span> <span data-ttu-id="8c5da-125">Per importare il file HistoricalDemandData per questo esempio, selezionare **CSV**.</span><span class="sxs-lookup"><span data-stu-id="8c5da-125">To import the HistoricalDemandData file for this example, select **CSV**.</span></span>
6. <span data-ttu-id="8c5da-126">Nel campo **Nome entità**, selezionare **Domanda esterna storica**.</span><span class="sxs-lookup"><span data-stu-id="8c5da-126">In the **Entity name** field, select **Historical external demand**.</span></span>
7. <span data-ttu-id="8c5da-127">Salvare il file nel computer e quindi caricarlo.</span><span class="sxs-lookup"><span data-stu-id="8c5da-127">Save the file to your computer, and then upload it.</span></span>
8. <span data-ttu-id="8c5da-128">Fare clic su **Importa**.</span><span class="sxs-lookup"><span data-stu-id="8c5da-128">Click **Import**.</span></span>
9. <span data-ttu-id="8c5da-129">La pagina **Riepilogo esecuzione** viene visualizzata automaticamente.</span><span class="sxs-lookup"><span data-stu-id="8c5da-129">The **Execution summary** page is opened automatically.</span></span> <span data-ttu-id="8c5da-130">Verificare i dati importati nella pagina.</span><span class="sxs-lookup"><span data-stu-id="8c5da-130">Verify the imported data on the page.</span></span>

<span data-ttu-id="8c5da-131">Dopo aver importato i dati storici della domanda, è possibile generare una previsione della domanda.</span><span class="sxs-lookup"><span data-stu-id="8c5da-131">After you've imported the historical demand data, you can generate a demand forecast.</span></span>

## <a name="see-also"></a><span data-ttu-id="8c5da-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8c5da-132">See also</span></span>

[<span data-ttu-id="8c5da-133">Generare una previsione di base statistica</span><span class="sxs-lookup"><span data-stu-id="8c5da-133">Generate a statistical baseline forecast</span></span>](generate-statistical-baseline-forecast.md)

