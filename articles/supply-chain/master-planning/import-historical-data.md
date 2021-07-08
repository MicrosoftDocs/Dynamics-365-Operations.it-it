---
title: Importare dati storici per le previsioni della domanda
description: Per ottenere le previsioni della domanda accurate, sono necessari i dati storici della domanda per singolo articolo o chiave di allocazione articolo. In questo argomento viene descritto come utilizzare le entità di dati per importare i dati storici della domanda da un sistema, in modo da disporre di uno storico più ampio dei dati di previsione della domanda.
author: roxanadiaconu
ms.date: 05/10/2017
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 0b04ee246d4c28e934407ccb92d792692cc4347d
ms.sourcegitcommit: cbbb35c71ab4ff1ae08fa4f7cc97019b207246be
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2021
ms.locfileid: "6301652"
---
# <a name="import-historical-data-for-demand-forecasts"></a><span data-ttu-id="b2299-104">Importare dati storici per le previsioni della domanda</span><span class="sxs-lookup"><span data-stu-id="b2299-104">Import historical data for demand forecasts</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b2299-105">Per contribuire a garantire la correttezza delle previsioni della domanda, sono necessari tutti i dati storici della domanda che si possono ottenere per singolo articolo o chiave di allocazione articolo.</span><span class="sxs-lookup"><span data-stu-id="b2299-105">To help guarantee the accuracy of demand forecasts, you must have as much historical demand data as you can get per item or item allocation key.</span></span> <span data-ttu-id="b2299-106">Se i dati storici della domanda non sono stati ancora importati, utilizzare l'entità di dati **Domanda esterna storica** (ReqDemPlanHistoricalExternalDemandEntity) in Dynamics 365 Supply Chain Management per importarli.</span><span class="sxs-lookup"><span data-stu-id="b2299-106">If the historical demand data isn't already imported, use the **Historical external demand** (ReqDemPlanHistoricalExternalDemandEntity) data entity in Dynamics 365 Supply Chain Management to import it.</span></span>

<span data-ttu-id="b2299-107">Nell'area di lavoro **Gestione dei dati**, è possibile visualizzare una panoramica di tutti i campi relativi all'entità.</span><span class="sxs-lookup"><span data-stu-id="b2299-107">In the **Data management** workspace, you can see an overview of all the fields in the entity.</span></span>

1. <span data-ttu-id="b2299-108">Aprire l'area di lavoro **Gestione dei dati**.</span><span class="sxs-lookup"><span data-stu-id="b2299-108">Open the **Data management** workspace.</span></span>
2. <span data-ttu-id="b2299-109">Selezionare il riquadro **Entità di dati**.</span><span class="sxs-lookup"><span data-stu-id="b2299-109">Select the **Data entities** tile.</span></span>
3. <span data-ttu-id="b2299-110">Ricercare nell'elenco delle entità **Domanda esterna storica**.</span><span class="sxs-lookup"><span data-stu-id="b2299-110">Search the entity list for **Historical external demand**.</span></span>
4. <span data-ttu-id="b2299-111">Selezionare **Campi di destinazione**.</span><span class="sxs-lookup"><span data-stu-id="b2299-111">Select **Target fields**.</span></span> <span data-ttu-id="b2299-112">I seguenti campi di entità sono obbligatori: sito (**DeliveringSiteId**), data (**DemandDate**), quantità (**DemandQuantity**) e numero di articolo (**ItemNumber**) o chiave di allocazione articolo (**ProductAllocationKeyId**).</span><span class="sxs-lookup"><span data-stu-id="b2299-112">The following entity fields are mandatory: site (**DeliveringSiteId**), date (**DemandDate**), quantity (**DemandQuantity**), and either item number (**ItemNumber**) or item allocation key (**ProductAllocationKeyId**).</span></span>

<span data-ttu-id="b2299-113">Per utilizzare questa entità di dati, è necessario disporre di un file di Microsoft Excel o un file con valori separati da virgole (CSV) contenente i dati storici della domanda.</span><span class="sxs-lookup"><span data-stu-id="b2299-113">To use the data entity, you must have a Microsoft Excel file or comma-separated values (CSV) file that contains the historical demand data.</span></span> <span data-ttu-id="b2299-114">Nel seguente esempio viene illustrato come importare i dati da un file CSV.</span><span class="sxs-lookup"><span data-stu-id="b2299-114">The following example shows how to import the data from a CSV file.</span></span>

<span data-ttu-id="b2299-115">Per ulteriori informazioni su come importare i dati, incluso come pulire i dati dopo un'importazione, vedere [Panoramica dei processi di importazione ed esportazione dei dati](../../fin-ops-core/dev-itpro/data-entities/data-import-export-job.md) ed argomenti correlati.</span><span class="sxs-lookup"><span data-stu-id="b2299-115">For more information about how to import data, including how to clean up data after an import, see [Data import and export jobs overview](../../fin-ops-core/dev-itpro/data-entities/data-import-export-job.md) and its related topics.</span></span>

<span data-ttu-id="b2299-116">Vedi anche [Generare una previsione di base statistica](generate-statistical-baseline-forecast.md).</span><span class="sxs-lookup"><span data-stu-id="b2299-116">See also [Generate a statistical baseline forecast](generate-statistical-baseline-forecast.md).</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]