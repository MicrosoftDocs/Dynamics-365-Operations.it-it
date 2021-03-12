---
title: Archiviazione report di aging delle scorte
description: Questo argomento descrive la funzionalità che consente di eseguire un report di aging dell'inventario e di rendere disponibile l'output come modulo e grafico.
author: AndersGirke
manager: tfehr
ms.date: 11/11/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventAgingStorage, InventAgingStorageChart, InventAgingStorageDetails
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: aevengir
ms.search.validFrom: 2019-01-10
ms.dyn365.ops.version: ''
ms.openlocfilehash: 8a292bd7a7ccbb09af1955e1e253b45e230c1009
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "5005429"
---
# <a name="inventory-aging-report-storage"></a><span data-ttu-id="ad04f-103">Archiviazione report di aging delle scorte</span><span class="sxs-lookup"><span data-stu-id="ad04f-103">Inventory aging report storage</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ad04f-104">In Microsoft Dynamics 365 Supply Chain Management, è possibile eseguire un report **Archiviazione report di aging delle scorte** e rendere l'output disponibile come modulo e grafico.</span><span class="sxs-lookup"><span data-stu-id="ad04f-104">In Microsoft Dynamics 365 Supply Chain Management, you can run an **Inventory aging report storage** report and make the output available as a form and a chart.</span></span> <span data-ttu-id="ad04f-105">Nel modulo, le colonne e i saldi aggregati vengono modificati in modo dinamico, a seconda del layout configurato.</span><span class="sxs-lookup"><span data-stu-id="ad04f-105">In the form, columns and aggregate balances are dynamically adjusted, depending on the layout that is configured.</span></span> <span data-ttu-id="ad04f-106">Il grafico offre una panoramica visiva che supporta il filtro e consente di approfondire i dettagli.</span><span class="sxs-lookup"><span data-stu-id="ad04f-106">The chart provides a visual overview that supports filtering and lets you drill down into details.</span></span> <span data-ttu-id="ad04f-107">Inoltre, un'entità dati denominata **Report aging delle scorte** consente di esportare i risultati di un report **Archiviazione report di aging delle scorte** eseguito in un formato file Microsoft Excel o un file PDF.</span><span class="sxs-lookup"><span data-stu-id="ad04f-107">Additionally, a data entity that is named **Inventory aging report** lets you export the results of an **Inventory aging report storage** report run to a format such as a Microsoft Excel file or a PDF file.</span></span>

<span data-ttu-id="ad04f-108">Questo metodo di esecuzione del report **Archiviazione report di aging delle scorte** è utile nei casi in cui l'output contiene più righe.</span><span class="sxs-lookup"><span data-stu-id="ad04f-108">This method of running an **Inventory aging report storage** report is helpful in cases where the output contains many lines.</span></span> <span data-ttu-id="ad04f-109">Ad esempio, l'output contiene molte righe se si dispone di 50.000 articoli e 300 negozi creati come magazzini e si richiede l'aging delle scorte per articolo, sito e magazzino.</span><span class="sxs-lookup"><span data-stu-id="ad04f-109">For example, the output will contain many lines if you have 50,000 items and 300 stores that are created as warehouses, and you request inventory aging by item, site, and warehouse.</span></span>

## <a name="enable-the-inventory-value-storage-report-feature"></a><span data-ttu-id="ad04f-110">Abilitare la funzione report di archiviazione valori di magazzino</span><span class="sxs-lookup"><span data-stu-id="ad04f-110">Enable the Inventory value storage report feature</span></span>

<span data-ttu-id="ad04f-111">Prima di utilizzare questa funzionalità, è necessario abilitarla nel sistema.</span><span class="sxs-lookup"><span data-stu-id="ad04f-111">Before you can use this feature, you must enable it on your system.</span></span> <span data-ttu-id="ad04f-112">Gli amministratori possono utilizzare le impostazioni della [gestione delle funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) per controllare lo stato della funzione e abilitarla se necessario.</span><span class="sxs-lookup"><span data-stu-id="ad04f-112">Administrators can use the [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the feature status and enable it if needed.</span></span> <span data-ttu-id="ad04f-113">La funzione viene elencata come:</span><span class="sxs-lookup"><span data-stu-id="ad04f-113">Here, the feature is listed as:</span></span>

- <span data-ttu-id="ad04f-114">**Modulo** - Gestione costi</span><span class="sxs-lookup"><span data-stu-id="ad04f-114">**Module** - Cost management</span></span>
- <span data-ttu-id="ad04f-115">**Nome della funzione** - Archiviazione report di aging delle scorte</span><span class="sxs-lookup"><span data-stu-id="ad04f-115">**Feature name** - Inventory aging report storage</span></span>

## <a name="run-an-inventory-aging-report-storage"></a><span data-ttu-id="ad04f-116">Eseguire un'archiviazione report di aging delle scorte</span><span class="sxs-lookup"><span data-stu-id="ad04f-116">Run an Inventory aging report storage</span></span>

1. <span data-ttu-id="ad04f-117">Passare **Gestione costi \> Richieste di informazioni e report \> Archiviazione del report di aging delle scorte**.</span><span class="sxs-lookup"><span data-stu-id="ad04f-117">Go to **Cost management \> Inquiries and reports \> Inventory aging report storage**.</span></span>
1. <span data-ttu-id="ad04f-118">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="ad04f-118">Select **New**.</span></span>
1. <span data-ttu-id="ad04f-119">Nel campo **Identificatore processo - Nome** immettere un nome univoco per il report.</span><span class="sxs-lookup"><span data-stu-id="ad04f-119">In the **Process Identifier – Name** field, enter a unique name for the report.</span></span>
1. <span data-ttu-id="ad04f-120">Selezionare il report **Identificazione - ID** e filtrarlo come necessario.</span><span class="sxs-lookup"><span data-stu-id="ad04f-120">Select the **Identification – ID** report, and filter it as you require.</span></span>

    <span data-ttu-id="ad04f-121">L'esecuzione del report è sempre effettuata in un processo batch.</span><span class="sxs-lookup"><span data-stu-id="ad04f-121">Report execution is always done in a batch job.</span></span>

1. <span data-ttu-id="ad04f-122">Al termine del processo batch, l'output viene visualizzato nella pagina **Archiviazione del report di aging delle scorte**.</span><span class="sxs-lookup"><span data-stu-id="ad04f-122">After the batch job is completed, the output is shown on the **Inventory aging report storage** page.</span></span>
1. <span data-ttu-id="ad04f-123">Per visualizzare l'output come modulo con un layout tradizionale a griglia, selezionare **Visualizza dettagli**.</span><span class="sxs-lookup"><span data-stu-id="ad04f-123">To view the output as a form that has a traditional grid layout, select **View details**.</span></span> <span data-ttu-id="ad04f-124">Per visualizzare l'output sotto forma di grafico aggregato, selezionare **Visualizza grafico**.</span><span class="sxs-lookup"><span data-stu-id="ad04f-124">To view the output as an aggregated chart, select **View chart**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ad04f-125">Nel modulo non vengono inclusi i subtotali che sono definiti nel layout del report.</span><span class="sxs-lookup"><span data-stu-id="ad04f-125">The form won't include subtotals that are defined in the report layout.</span></span>

<span data-ttu-id="ad04f-126">L'entità di dati **Report di aging delle scorte** consente di esportare l'output di un report **Archiviazione report di aging delle scorte** applicando un filtro per il campo **Identificatore di processo - Nome** in qualsiasi formato supportato della gestione dei dati.</span><span class="sxs-lookup"><span data-stu-id="ad04f-126">The **Inventory aging report** data entity lets you export the output of an **Inventory aging report storage** report by applying a filter for the **Process Identifier – Name** field to any format that Data management supports.</span></span>
