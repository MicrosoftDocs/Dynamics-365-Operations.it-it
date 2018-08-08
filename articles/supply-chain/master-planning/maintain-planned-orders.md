---
title: Gestisci ordini pianificati
description: "Questo articolo fornisce informazioni sulla modalità di gestione degli ordini pianificati. Viene descritto come aggiornare lo stato degli ordini pianificati, stabilizzarli e filtrare gli ordini pianificati con lo stesso stato dell'ordine pianificato selezionato."
author: roxanadiaconu
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ReqTransPo
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 19151
ms.assetid: 54123f4c-b4ca-4ce4-9358-b067aa04c968
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: 1c764bb541b371cb2778040e7498c347ac9d7dfe
ms.contentlocale: it-it
ms.lasthandoff: 08/07/2018

---

# <a name="maintain-planned-orders"></a><span data-ttu-id="37503-104">Gestisci ordini pianificati</span><span class="sxs-lookup"><span data-stu-id="37503-104">Maintain planned orders</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="37503-105">Questo articolo fornisce informazioni sulla modalità di gestione degli ordini pianificati.</span><span class="sxs-lookup"><span data-stu-id="37503-105">This article provides information about how to manage planned orders.</span></span> <span data-ttu-id="37503-106">Viene descritto come aggiornare lo stato degli ordini pianificati, stabilizzarli e filtrare gli ordini pianificati con lo stesso stato dell'ordine pianificato selezionato.</span><span class="sxs-lookup"><span data-stu-id="37503-106">It describes how you can update the status of planned orders, firm them, and filter for planned orders that have the same status as a selected planned order.</span></span>

<span data-ttu-id="37503-107">È possibile gestire gli ordini pianificati nell'area di lavoro **Pianificazione generale**, nell'elenco **Ordine pianificato** o negli elenchi **Ordini di produzione pianificati**, **Ordini fornitore pianificati** e **Trasferimento pianificato**.</span><span class="sxs-lookup"><span data-stu-id="37503-107">You can manage planned orders from the **Master planning** workspace, the **Planned order** list, or the **Planned production orders**, **Planned purchase orders**, and **Planned transfer** lists.</span></span> <span data-ttu-id="37503-108">È possibile utilizzare il campo **Stato** per tenere facilmente traccia dell'avanzamento.</span><span class="sxs-lookup"><span data-stu-id="37503-108">You can use the **Status** field to help track your progress.</span></span> <span data-ttu-id="37503-109">Vengono utilizzati i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="37503-109">The following values are used:</span></span>

-   <span data-ttu-id="37503-110">Agli ordini pianificati generati mediante la pianificazione generale viene assegnato uno stato di **Inevaso**.</span><span class="sxs-lookup"><span data-stu-id="37503-110">When master planning generates planned orders, the planned orders have a status of **Unprocessed**.</span></span>
-   <span data-ttu-id="37503-111">A un ordine pianificato che si sceglie di non stabilizzare è possibile assegnare uno stato di **Completato**.</span><span class="sxs-lookup"><span data-stu-id="37503-111">If you decide not to firm a planned order, you can give it a status of **Completed**.</span></span>
-   <span data-ttu-id="37503-112">A un ordine pianificato che si sceglie di non stabilizzare è possibile assegnare uno stato di **Approvato**.</span><span class="sxs-lookup"><span data-stu-id="37503-112">When you decide to firm a planned order, you can give it a status of **Approved**.</span></span> <span data-ttu-id="37503-113">Questo stato indica che si approva la stabilizzazione dell'ordine pianificato, ma che questa operazione non è ancora stata effettuata.</span><span class="sxs-lookup"><span data-stu-id="37503-113">This status indicates that you approve firming of the planned order, but it isn't firmed yet.</span></span>

<span data-ttu-id="37503-114">**Nota:** un ordine pianificato approvato viene trasferito con lo stato corrente al calcolo successivo della pianificazione generale.</span><span class="sxs-lookup"><span data-stu-id="37503-114">**Note:** An approved planned order is transferred, in its current state, to the next master planning calculation.</span></span> <span data-ttu-id="37503-115">È possibile stabilizzare gli ordini pianificati facendo clic su **Stabilizza**.</span><span class="sxs-lookup"><span data-stu-id="37503-115">You can firm planned orders by clicking **Firm**.</span></span> <span data-ttu-id="37503-116">Di seguito sono riportati gli ordini pianificati che è possibile stabilizzare:</span><span class="sxs-lookup"><span data-stu-id="37503-116">You can firm the following planned orders:</span></span>

-   <span data-ttu-id="37503-117">L'ordine pianificato selezionato.</span><span class="sxs-lookup"><span data-stu-id="37503-117">The planned order that is selected.</span></span>
-   <span data-ttu-id="37503-118">Più ordini pianificati.</span><span class="sxs-lookup"><span data-stu-id="37503-118">Multiple planned orders.</span></span>
-   <span data-ttu-id="37503-119">Ordini pianificati generati da un'esplosione nella pagina **Esplosione**.</span><span class="sxs-lookup"><span data-stu-id="37503-119">Planned orders that are generated by an explosion from the **Explosion** page.</span></span> <span data-ttu-id="37503-120">Fare clic su **Ordini pianificati**, selezionare l'ordine pianificato, quindi fare clic su **Stabilizza**.</span><span class="sxs-lookup"><span data-stu-id="37503-120">Click **Planned orders**, select the planned order, and then click **Firm**.</span></span>

<span data-ttu-id="37503-121">Quando un ordine pianificato viene stabilizzato, viene spostato nella sezione relativa agli ordini del modulo rilevante.</span><span class="sxs-lookup"><span data-stu-id="37503-121">When a planned order is firmed, it's moved to the orders section of the relevant module.</span></span> <span data-ttu-id="37503-122">**Nota:** è possibile fare clic con il pulsante destro del mouse su un ordine pianificato che ha uno stato particolare e filtrare altri ordini pianificati con lo stesso stato.</span><span class="sxs-lookup"><span data-stu-id="37503-122">**Note:** You can right-click a planned order that has a particular status and filter for other planned orders that have the same status.</span></span> <span data-ttu-id="37503-123">Questa funzionalità è utile se, ad esempio, si desidera filtrare tutti gli ordini pianificati che hanno uno stato di **Approvato**, in modo da poterli stabilizzare.</span><span class="sxs-lookup"><span data-stu-id="37503-123">This functionality is useful if, for example, you want to filter for all planned orders that have a status of **Approved**, so that you can then firm them.</span></span>

<a name="additional-resources"></a><span data-ttu-id="37503-124">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="37503-124">Additional resources</span></span>
--------

[<span data-ttu-id="37503-125">Piani generali</span><span class="sxs-lookup"><span data-stu-id="37503-125">Master plans</span></span>](master-plans.md)




