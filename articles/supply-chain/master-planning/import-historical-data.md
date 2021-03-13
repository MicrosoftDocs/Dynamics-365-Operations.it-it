---
title: Importare dati storici per le previsioni della domanda
description: Per ottenere le previsioni della domanda accurate, sono necessari i dati storici della domanda per singolo articolo o chiave di allocazione articolo. In questo argomento viene descritto come utilizzare le entità di dati per importare i dati storici della domanda da un sistema, in modo da disporre di uno storico più ampio dei dati di previsione della domanda.
author: roxanadiaconu
manager: tfehr
ms.date: 05/10/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqDemPlanCreateForecastDialog
audience: Application User
ms.reviewer: kamaybac
ms.assetid: 59c0d269-9db0-48e7-b8c7-9a388781a9ca
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d6ba2e1a3a884d29bff491f914aa2d5f9ece2b84
ms.sourcegitcommit: 79621e667cd7f48ba3bdbf2731f6f33d8e9f57f6
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/10/2021
ms.locfileid: "5154229"
---
# <a name="import-historical-data-for-demand-forecasts"></a><span data-ttu-id="0e236-104">Importare dati storici per le previsioni della domanda</span><span class="sxs-lookup"><span data-stu-id="0e236-104">Import historical data for demand forecasts</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0e236-105">Per contribuire a garantire la correttezza delle previsioni della domanda, sono necessari tutti i dati storici della domanda che si possono ottenere per singolo articolo o chiave di allocazione articolo.</span><span class="sxs-lookup"><span data-stu-id="0e236-105">To help guarantee the accuracy of demand forecasts, you must have as much historical demand data as you can get per item or item allocation key.</span></span> <span data-ttu-id="0e236-106">Se i dati storici della domanda non sono stati ancora importati, utilizzare l'entità di dati **Domanda esterna storica** (ReqDemPlanHistoricalExternalDemandEntity) in Dynamics 365 Supply Chain Management per importarli.</span><span class="sxs-lookup"><span data-stu-id="0e236-106">If the historical demand data isn't already imported, use the **Historical external demand** (ReqDemPlanHistoricalExternalDemandEntity) data entity in Dynamics 365 Supply Chain Management to import it.</span></span>

<span data-ttu-id="0e236-107">Nell'area di lavoro **Gestione dei dati**, è possibile visualizzare una panoramica di tutti i campi relativi all'entità.</span><span class="sxs-lookup"><span data-stu-id="0e236-107">In the **Data management** workspace, you can see an overview of all the fields in the entity.</span></span>

1. <span data-ttu-id="0e236-108">Aprire l'area di lavoro **Gestione dei dati**.</span><span class="sxs-lookup"><span data-stu-id="0e236-108">Open the **Data management** workspace.</span></span>
2. <span data-ttu-id="0e236-109">Selezionare il riquadro **Entità di dati**.</span><span class="sxs-lookup"><span data-stu-id="0e236-109">Select the **Data entities** tile.</span></span>
3. <span data-ttu-id="0e236-110">Ricercare nell'elenco delle entità **Domanda esterna storica**.</span><span class="sxs-lookup"><span data-stu-id="0e236-110">Search the entity list for **Historical external demand**.</span></span>
4. <span data-ttu-id="0e236-111">Selezionare **Campi di destinazione**.</span><span class="sxs-lookup"><span data-stu-id="0e236-111">Select **Target fields**.</span></span> <span data-ttu-id="0e236-112">I seguenti campi di entità sono obbligatori: sito (**DeliveringSiteId**), data (**DemandDate**), quantità (**DemandQuantity**) e numero di articolo (**ItemNumber**) o chiave di allocazione articolo (**ProductAllocationKeyId**).</span><span class="sxs-lookup"><span data-stu-id="0e236-112">The following entity fields are mandatory: site (**DeliveringSiteId**), date (**DemandDate**), quantity (**DemandQuantity**), and either item number (**ItemNumber**) or item allocation key (**ProductAllocationKeyId**).</span></span>

<span data-ttu-id="0e236-113">Per utilizzare questa entità di dati, è necessario disporre di un file di Microsoft Excel o un file con valori separati da virgole (CSV) contenente i dati storici della domanda.</span><span class="sxs-lookup"><span data-stu-id="0e236-113">To use the data entity, you must have a Microsoft Excel file or comma-separated values (CSV) file that contains the historical demand data.</span></span> <span data-ttu-id="0e236-114">Nel seguente esempio viene illustrato come importare i dati da un file CSV.</span><span class="sxs-lookup"><span data-stu-id="0e236-114">The following example shows how to import the data from a CSV file.</span></span>

<span data-ttu-id="0e236-115">Per ulteriori informazioni su come importare i dati, incluso come pulire i dati dopo un'importazione, vedere [Panoramica dei processi di importazione ed esportazione dei dati](../../fin-ops-core/dev-itpro/data-entities/data-import-export-job.md) ed argomenti correlati.</span><span class="sxs-lookup"><span data-stu-id="0e236-115">For more information about how to import data, including how to clean up data after an import, see [Data import and export jobs overview](../../fin-ops-core/dev-itpro/data-entities/data-import-export-job.md) and its related topics.</span></span>

## <a name="example"></a><span data-ttu-id="0e236-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="0e236-116">Example</span></span>

<span data-ttu-id="0e236-117">È possibile utilizzare il seguente file come esempio.</span><span class="sxs-lookup"><span data-stu-id="0e236-117">You can use the following file as an example.</span></span> <span data-ttu-id="0e236-118">Scaricare [HistoricalDemandData](https://docs.microsoft.com/dynamics/s-e/).</span><span class="sxs-lookup"><span data-stu-id="0e236-118">Download the [HistoricalDemandData](https://docs.microsoft.com/dynamics/s-e/).</span></span> <span data-ttu-id="0e236-119">Questo file contiene i dati storici della domanda per l'articolo D0001.</span><span class="sxs-lookup"><span data-stu-id="0e236-119">This file contains the historical demand data for item D0001.</span></span> <span data-ttu-id="0e236-120">Contiene solo i seguenti campi obbligatori: sito, quantità e data della domanda.</span><span class="sxs-lookup"><span data-stu-id="0e236-120">It contains only the following mandatory fields: site, quantity, and the demand date.</span></span>

1. <span data-ttu-id="0e236-121">Selezionare la società in cui importare i dati storici della domanda.</span><span class="sxs-lookup"><span data-stu-id="0e236-121">Select the company to import the historical demand data into.</span></span>
2. <span data-ttu-id="0e236-122">Aprire l'area di lavoro **Gestione dei dati**.</span><span class="sxs-lookup"><span data-stu-id="0e236-122">Open the **Data management** workspace.</span></span>
3. <span data-ttu-id="0e236-123">Selezionare il riquadro **Importa**.</span><span class="sxs-lookup"><span data-stu-id="0e236-123">Select the **Import** tile.</span></span>
4. <span data-ttu-id="0e236-124">Immettere un nome per il progetto di importazione, ad esempio **Importare dati storici della domanda per l'articolo D0001**.</span><span class="sxs-lookup"><span data-stu-id="0e236-124">Enter a name for the import project, such as **Import historical demand for item D0001**.</span></span>
5. <span data-ttu-id="0e236-125">Nel campo **Formato dati di origine**, selezionare il formato del file da importare.</span><span class="sxs-lookup"><span data-stu-id="0e236-125">In the **Source data format** field, select the file format of the file that you're importing.</span></span> <span data-ttu-id="0e236-126">Per importare il file HistoricalDemandData per questo esempio, selezionare **CSV**.</span><span class="sxs-lookup"><span data-stu-id="0e236-126">To import the HistoricalDemandData file for this example, select **CSV**.</span></span>
6. <span data-ttu-id="0e236-127">Nel campo **Nome entità**, selezionare **Domanda esterna storica**.</span><span class="sxs-lookup"><span data-stu-id="0e236-127">In the **Entity name** field, select **Historical external demand**.</span></span>
7. <span data-ttu-id="0e236-128">Salvare il file nel computer e quindi caricarlo.</span><span class="sxs-lookup"><span data-stu-id="0e236-128">Save the file to your computer, and then upload it.</span></span>
8. <span data-ttu-id="0e236-129">Selezionare **Importa**.</span><span class="sxs-lookup"><span data-stu-id="0e236-129">Select **Import**.</span></span>
9. <span data-ttu-id="0e236-130">La pagina **Riepilogo esecuzione** viene visualizzata automaticamente.</span><span class="sxs-lookup"><span data-stu-id="0e236-130">The **Execution summary** page is opened automatically.</span></span> <span data-ttu-id="0e236-131">Verificare i dati importati nella pagina.</span><span class="sxs-lookup"><span data-stu-id="0e236-131">Verify the imported data on the page.</span></span>

<span data-ttu-id="0e236-132">Dopo aver importato i dati storici della domanda, è possibile generare una previsione della domanda.</span><span class="sxs-lookup"><span data-stu-id="0e236-132">After you've imported the historical demand data, you can generate a demand forecast.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="0e236-133">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="0e236-133">Additional resources</span></span>

[<span data-ttu-id="0e236-134">Generare una previsione di base statistica</span><span class="sxs-lookup"><span data-stu-id="0e236-134">Generate a statistical baseline forecast</span></span>](generate-statistical-baseline-forecast.md)  
[<span data-ttu-id="0e236-135">Panoramica processi di importazione ed esportazione dati</span><span class="sxs-lookup"><span data-stu-id="0e236-135">Data import and export jobs overview</span></span>](../../fin-ops-core/dev-itpro/data-entities/data-import-export-job.md)
