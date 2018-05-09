---
title: Stima dei costi degli ordini di produzione
description: "In questo articolo vengono fornite informazioni sulla stima dei costi di produzione. Tale stima consente di ottenere i costi relativi al consumo di materiali e alla capacità previsti per la produzione della quantità di un articolo indicata nell'ordine di produzione pianificato."
author: AndersGirke
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BOMCalcTrans, InventCostTrans, ProdCalcTrans, ProdTableJour, ProdTableListPage
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 80633
ms.assetid: b4625d10-c852-4fda-b718-79df458de0d4
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: fe938a0b728205da56aa006583c6be7a44537ff4
ms.contentlocale: it-it
ms.lasthandoff: 05/08/2018

---

# <a name="production-order-cost-estimation"></a><span data-ttu-id="4587c-104">Stima dei costi degli ordini di produzione</span><span class="sxs-lookup"><span data-stu-id="4587c-104">Production order cost estimation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="4587c-105">In questo articolo vengono fornite informazioni sulla stima dei costi di produzione.</span><span class="sxs-lookup"><span data-stu-id="4587c-105">This article provides information about production cost estimation.</span></span> <span data-ttu-id="4587c-106">Tale stima consente di ottenere i costi relativi al consumo di materiali e alla capacità previsti per la produzione della quantità di un articolo indicata nell'ordine di produzione pianificato.</span><span class="sxs-lookup"><span data-stu-id="4587c-106">Production cost estimation provides the projected material and capacity consumption costs of producing an item in the planned production order quantity.</span></span> 

<span data-ttu-id="4587c-107">Dopo avere creato un ordine di produzione, è necessario stimare i costi di produzione.</span><span class="sxs-lookup"><span data-stu-id="4587c-107">After you create a production order, you must estimate production costs.</span></span> <span data-ttu-id="4587c-108">Lo scopo è quello di stimare il consumo dell'articolo e del ciclo di lavorazione per il processo di produzione, in quanto queste stime rappresentano la base per i successivi processi di programmazione e produzione.</span><span class="sxs-lookup"><span data-stu-id="4587c-108">The purpose is to estimate item and route consumption for the production process, because these estimates are used as the basis for subsequent scheduling and production processes.</span></span>

## <a name="production-cost-estimation"></a><span data-ttu-id="4587c-109">Stima dei costi di produzione</span><span class="sxs-lookup"><span data-stu-id="4587c-109">Production cost estimation</span></span>
<span data-ttu-id="4587c-110">Le stime dei costi di produzione si basano sulle seguenti informazioni:</span><span class="sxs-lookup"><span data-stu-id="4587c-110">Estimates of production costs are based on the following information:</span></span>

-   <span data-ttu-id="4587c-111">Quantità nell'ordine di produzione</span><span class="sxs-lookup"><span data-stu-id="4587c-111">The quantity on the production order</span></span>
-   <span data-ttu-id="4587c-112">Componenti nelle distinte basi (DBA)</span><span class="sxs-lookup"><span data-stu-id="4587c-112">The components on the production bills of materials (BOMs)</span></span>
-   <span data-ttu-id="4587c-113">Operazioni dei percorsi di trasferimento nel ciclo di lavorazione produzione</span><span class="sxs-lookup"><span data-stu-id="4587c-113">The routing operations in the production route</span></span>
-   <span data-ttu-id="4587c-114">Costi indiretti applicabili ai componenti e alle operazioni</span><span class="sxs-lookup"><span data-stu-id="4587c-114">The indirect costs that apply to the components and operations</span></span>
-   <span data-ttu-id="4587c-115">Dati dei costi attivi alla data di calcolo</span><span class="sxs-lookup"><span data-stu-id="4587c-115">The active cost data as of the calculation date</span></span>

<span data-ttu-id="4587c-116">Se è presente una voce fittizia nella DBA di produzione, i calcoli riflettono i componenti e le operazioni dei cicli di lavorazione dell'articolo fittizio.</span><span class="sxs-lookup"><span data-stu-id="4587c-116">If there is a phantom line item on the production BOMs, the calculations reflect the phantom’s components and route operations.</span></span> <span data-ttu-id="4587c-117">L'attività di stima può essere utilizzata per ricalcolare i costi stimati in modo da riflettere le informazioni aggiornate.</span><span class="sxs-lookup"><span data-stu-id="4587c-117">You can use the estimation task to recalculate estimated costs so that they reflect updated information.</span></span> <span data-ttu-id="4587c-118">Le informazioni aggiornate possono essere ad esempio variazioni nella quantità dell'ordine di produzione, componenti della DBA di produzione, operazioni dei percorsi di trasferimento del ciclo di lavorazione produzione, costi indiretti applicabili a tali componenti e operazioni o dati di costi attivi al momento del ricalcolo.</span><span class="sxs-lookup"><span data-stu-id="4587c-118">For example, the updated information might be changes to the quantity on the production order, the components on the production BOMs, the routing operations in the production route, the indirect costs that apply to these components and operations, or the active cost data as of the recalculation date.</span></span> <span data-ttu-id="4587c-119">Con i calcoli dei costi stimati è inoltre possibile consigliare un prezzo di vendita per l'articolo di produzione sulla base di un approccio comprendente una percentuale di ricarico.</span><span class="sxs-lookup"><span data-stu-id="4587c-119">The calculations of estimated cost also suggest a sales price for the production item, based on a cost-plus-markup approach.</span></span> <span data-ttu-id="4587c-120">I calcoli dei costi stimati possono facoltativamente applicarsi a ordini di riferimento che riflettono ordini di produzione collegati all'ordine di produzione.</span><span class="sxs-lookup"><span data-stu-id="4587c-120">The calculations of estimated cost can optionally apply to reference orders that reflect other production orders that are linked to the production order.</span></span>

## <a name="view-the-estimated-costs"></a><span data-ttu-id="4587c-121">Visualizzare i costi stimati</span><span class="sxs-lookup"><span data-stu-id="4587c-121">View the estimated costs</span></span>
<span data-ttu-id="4587c-122">Dopo aver eseguito una stima, è possibile visualizzare i risultati nella pagina **Calcolo dei prezzi**.</span><span class="sxs-lookup"><span data-stu-id="4587c-122">After you run estimation, you can view the results on the **Price calculation** page.</span></span> <span data-ttu-id="4587c-123">Durante l'esecuzione della stima vengono calcolati i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="4587c-123">The estimation calculates the following values:</span></span>

-   <span data-ttu-id="4587c-124">**Costo di produzione**: è la prima riga della stima.</span><span class="sxs-lookup"><span data-stu-id="4587c-124">**Production cost** – The production cost is the top line of the estimate.</span></span> <span data-ttu-id="4587c-125">Indica il costo completo dell'esecuzione dell'ordine di produzione e il prezzo di vendita totale per la produzione.</span><span class="sxs-lookup"><span data-stu-id="4587c-125">It shows the complete cost of running the production order and the total sales price for the production.</span></span> <span data-ttu-id="4587c-126">Corrisponde alla somma di tutte le righe dei costi nella stima.</span><span class="sxs-lookup"><span data-stu-id="4587c-126">It's the sum of all the cost lines on the estimate.</span></span>
-   <span data-ttu-id="4587c-127">**Costi di risorse o del ciclo di lavorazione**: i costi delle risorse o del ciclo di lavorazione sono i costi per le operazioni di produzione.</span><span class="sxs-lookup"><span data-stu-id="4587c-127">**Route or resource costs** – Route or resource costs are the costs for the production operations.</span></span> <span data-ttu-id="4587c-128">È incluso il costo degli elementi, ad esempio tempo di attrezzaggio, tempo di esecuzione e i costi generali.</span><span class="sxs-lookup"><span data-stu-id="4587c-128">They include the cost of elements such as setup time, run time, and overhead.</span></span>
-   <span data-ttu-id="4587c-129">**Costi relativi ai materiali**: sono i costi e i prezzi dei componenti della distinta base (DBA) necessari per produrre l'articolo.</span><span class="sxs-lookup"><span data-stu-id="4587c-129">**Material costs** – Material costs are the costs and prices of the BOM components that are required in order to produce the item.</span></span> <span data-ttu-id="4587c-130">Questi costi sono stati stabiliti e immessi nel sistema in precedenza.</span><span class="sxs-lookup"><span data-stu-id="4587c-130">These costs have previously been established and entered into the system.</span></span>

## <a name="other-uses-of-cost-estimation"></a><span data-ttu-id="4587c-131">Altri utilizzi di una stima dei costi</span><span class="sxs-lookup"><span data-stu-id="4587c-131">Other uses of cost estimation</span></span>
<span data-ttu-id="4587c-132">Una stima dei costi fornisce inoltre le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="4587c-132">A cost estimate also provides the following information:</span></span>

-   <span data-ttu-id="4587c-133">Quotazioni significative dei prezzi</span><span class="sxs-lookup"><span data-stu-id="4587c-133">Meaningful price quotations</span></span>
-   <span data-ttu-id="4587c-134">Stime della redditività dell'ordine</span><span class="sxs-lookup"><span data-stu-id="4587c-134">Estimates of the profitability of the order</span></span>
-   <span data-ttu-id="4587c-135">Stime dell'utilizzo delle materie prime</span><span class="sxs-lookup"><span data-stu-id="4587c-135">Estimates of raw material usage</span></span>
-   <span data-ttu-id="4587c-136">Confronti con informazioni sui costi relative a produzioni precedenti</span><span class="sxs-lookup"><span data-stu-id="4587c-136">Comparisons of cost information from previous productions</span></span>
-   <span data-ttu-id="4587c-137">Informazioni relative a budget e previsioni</span><span class="sxs-lookup"><span data-stu-id="4587c-137">Budget and forecasting information</span></span>
-   <span data-ttu-id="4587c-138">Stime del volume di produzione necessario per mantenere un costo a un determinato livello</span><span class="sxs-lookup"><span data-stu-id="4587c-138">Estimates of the production size that is required in order to maintain a particular cost</span></span>





