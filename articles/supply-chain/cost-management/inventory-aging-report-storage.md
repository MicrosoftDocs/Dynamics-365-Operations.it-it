---
title: Report aging delle scorte
description: Questo argomento descrive la funzionalità che consente di eseguire un report di aging dell'inventario e di rendere disponibile l'output come modulo e grafico.
author: AndersGirke
manager: tfehr
ms.date: 11/11/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CostAdminWorkspace, CostAnalysisWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: aevengir
ms.search.validFrom: 2019-01-10
ms.dyn365.ops.version: ''
ms.openlocfilehash: 790c8fe3a52bce652227f1cef97eff6496476100
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2020
ms.locfileid: "3201623"
---
# <a name="inventory-aging-report"></a><span data-ttu-id="af394-103">Report aging delle scorte</span><span class="sxs-lookup"><span data-stu-id="af394-103">Inventory aging report</span></span>


[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

<span data-ttu-id="af394-104">In Microsoft Dynamics 365 Supply Chain Management, è possibile eseguire un report **Aging delle scorte** e rendere l'output disponibile come modulo e grafico.</span><span class="sxs-lookup"><span data-stu-id="af394-104">In Microsoft Dynamics 365 Supply Chain Management, you can run an **Inventory aging** report and make the output available as a form and a chart.</span></span> <span data-ttu-id="af394-105">Nel modulo, le colonne e i saldi aggregati vengono modificati in modo dinamico, a seconda del layout configurato.</span><span class="sxs-lookup"><span data-stu-id="af394-105">In the form, columns and aggregate balances are dynamically adjusted, depending on the layout that is configured.</span></span> <span data-ttu-id="af394-106">Il grafico offre una panoramica visiva che supporta il filtro e consente di approfondire i dettagli.</span><span class="sxs-lookup"><span data-stu-id="af394-106">The chart provides a visual overview that supports filtering and lets you drill down into details.</span></span> <span data-ttu-id="af394-107">Inoltre, un'entità dati denominata **Report aging delle scorte** consente di esportare i risultati di un report **Aging delle scorte** eseguito in un formato come un file Microsoft Excel o un file PDF.</span><span class="sxs-lookup"><span data-stu-id="af394-107">Additionally, a data entity that is named **Inventory aging report** lets you export the results of an **Inventory aging** report run to a format such as a Microsoft Excel file or a PDF file.</span></span>

<span data-ttu-id="af394-108">Questo metodo di esecuzione del report **Aging delle scorte** è utile nei casi in cui l'output contiene più righe.</span><span class="sxs-lookup"><span data-stu-id="af394-108">This method of running an **Inventory aging** report is helpful in cases where the output contains many lines.</span></span> <span data-ttu-id="af394-109">Ad esempio, l'output contiene molte righe se si dispone di 50.000 articoli e 300 negozi creati come magazzini e si richiede l'aging delle scorte per articolo, sito e magazzino.</span><span class="sxs-lookup"><span data-stu-id="af394-109">For example, the output will contain many lines if you have 50,000 items and 300 stores that are created as warehouses, and you request inventory aging by item, site, and warehouse.</span></span>

## <a name="run-an-inventory-aging-report"></a><span data-ttu-id="af394-110">Eseguire un report aging delle scorte</span><span class="sxs-lookup"><span data-stu-id="af394-110">Run an Inventory aging report</span></span>

1. <span data-ttu-id="af394-111">Passare **Gestione costi \> Richieste di informazioni e report \> Archiviazione del report di aging delle scorte**.</span><span class="sxs-lookup"><span data-stu-id="af394-111">Go to **Cost management \> Inquiries and reports \> Inventory aging report storage**.</span></span>
1. <span data-ttu-id="af394-112">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="af394-112">Select **New**.</span></span>
1. <span data-ttu-id="af394-113">Nel campo **Identificatore processo - Nome** immettere un nome univoco per il report.</span><span class="sxs-lookup"><span data-stu-id="af394-113">In the **Process Identifier – Name** field, enter a unique name for the report.</span></span>
1. <span data-ttu-id="af394-114">Selezionare il report **Identificazione - ID** e filtrarlo come necessario.</span><span class="sxs-lookup"><span data-stu-id="af394-114">Select the **Identification – ID** report, and filter it as you require.</span></span>

    <span data-ttu-id="af394-115">L'esecuzione del report è sempre effettuata in un processo batch.</span><span class="sxs-lookup"><span data-stu-id="af394-115">Report execution is always done in a batch job.</span></span>

1. <span data-ttu-id="af394-116">Al termine del processo batch, l'output viene visualizzato nella pagina **Archiviazione del report di aging delle scorte**.</span><span class="sxs-lookup"><span data-stu-id="af394-116">After the batch job is completed, the output is shown on the **Inventory aging report storage** page.</span></span>
1. <span data-ttu-id="af394-117">Per visualizzare l'output come modulo con un layout tradizionale a griglia, selezionare **Visualizza dettagli**.</span><span class="sxs-lookup"><span data-stu-id="af394-117">To view the output as a form that has a traditional grid layout, select **View details**.</span></span> <span data-ttu-id="af394-118">Per visualizzare l'output sotto forma di grafico aggregato, selezionare **Visualizza grafico**.</span><span class="sxs-lookup"><span data-stu-id="af394-118">To view the output as an aggregated chart, select **View chart**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="af394-119">Nel modulo non vengono inclusi i subtotali che sono definiti nel layout del report.</span><span class="sxs-lookup"><span data-stu-id="af394-119">The form won't include subtotals that are defined in the report layout.</span></span>

<span data-ttu-id="af394-120">L'entità di dati **Report di aging delle scorte** consente di esportare l'output di un report **Aging delle scorte** applicando un filtro per il campo **Identificatore di processo - Nome** in qualsiasi formato supportato della gestione dei dati.</span><span class="sxs-lookup"><span data-stu-id="af394-120">The **Inventory aging report** data entity lets you export the output of an **Inventory aging** report by applying a filter for the **Process Identifier – Name** field to any format that Data management supports.</span></span>
