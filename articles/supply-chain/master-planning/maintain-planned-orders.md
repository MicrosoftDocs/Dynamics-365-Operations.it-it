---
title: Gestisci ordini pianificati
description: Questo argomento fornisce informazioni sulla modalità di gestione degli ordini pianificati. Viene descritto come aggiornare lo stato degli ordini pianificati, stabilizzarli e filtrare gli ordini pianificati con lo stesso stato dell'ordine pianificato selezionato.
author: roxanadiaconu
manager: tfehr
ms.date: 12/10/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqTransPo, ReqTransFirmLog
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 19151
ms.assetid: 54123f4c-b4ca-4ce4-9358-b067aa04c968
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b0becf73ddde6add4076bd5b47a49eb3a0976206
ms.sourcegitcommit: cde71bc7d14ea6cdff2c4e991057d39a6a0473d9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/24/2020
ms.locfileid: "3886898"
---
# <a name="maintain-planned-orders"></a><span data-ttu-id="8ddf8-104">Gestisci ordini pianificati</span><span class="sxs-lookup"><span data-stu-id="8ddf8-104">Maintain planned orders</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="8ddf8-105">Questo argomento fornisce informazioni sulla modalità di gestione degli ordini pianificati.</span><span class="sxs-lookup"><span data-stu-id="8ddf8-105">This topic provides information about how to manage planned orders.</span></span> <span data-ttu-id="8ddf8-106">Viene descritto come aggiornare lo stato degli ordini pianificati, stabilizzarli e filtrare gli ordini pianificati con lo stesso stato dell'ordine pianificato selezionato.</span><span class="sxs-lookup"><span data-stu-id="8ddf8-106">It describes how you can update the status of planned orders, firm them, and filter for planned orders that have the same status as a selected planned order.</span></span>

<span data-ttu-id="8ddf8-107">È possibile gestire gli ordini pianificati nell'area di lavoro **Pianificazione generale**, nell'elenco **Ordine pianificato** o negli elenchi **Ordini di produzione pianificati**, **Ordini fornitore pianificati** e **Trasferimento pianificato**.</span><span class="sxs-lookup"><span data-stu-id="8ddf8-107">You can manage planned orders from the **Master planning** workspace, the **Planned order** list, or the **Planned production orders**, **Planned purchase orders**, and **Planned transfer** lists.</span></span> 

## <a name="planned-order-status"></a><span data-ttu-id="8ddf8-108">Stato dell'ordine pianificato</span><span class="sxs-lookup"><span data-stu-id="8ddf8-108">Planned order status</span></span>
<span data-ttu-id="8ddf8-109">È possibile utilizzare il campo **Stato** per tenere facilmente traccia dell'avanzamento.</span><span class="sxs-lookup"><span data-stu-id="8ddf8-109">You can use the **Status** field to help track your progress.</span></span> <span data-ttu-id="8ddf8-110">Vengono utilizzati i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="8ddf8-110">The following values are used:</span></span>

-   <span data-ttu-id="8ddf8-111">Agli ordini pianificati generati mediante la pianificazione generale viene assegnato uno stato di **Inevaso**.</span><span class="sxs-lookup"><span data-stu-id="8ddf8-111">When master planning generates planned orders, the planned orders have a status of **Unprocessed**.</span></span>
-   <span data-ttu-id="8ddf8-112">A un ordine pianificato che si sceglie di non stabilizzare è possibile assegnare uno stato di **Completato**.</span><span class="sxs-lookup"><span data-stu-id="8ddf8-112">If you decide not to firm a planned order, you can give it a status of **Completed**.</span></span>
-   <span data-ttu-id="8ddf8-113">Se si desidera stabilizzare un ordine pianificato, è possibile modificare lo stato su **Approvato**.</span><span class="sxs-lookup"><span data-stu-id="8ddf8-113">If you want to firm a planned order, you can change the status to **Approved**.</span></span> <span data-ttu-id="8ddf8-114">Gli ordini pianificati con stato **Approvato** vengono rispettati dalla pianificazione generale, non vengono modificati né eliminati durante un'esecuzione di pianificazione generale successiva.</span><span class="sxs-lookup"><span data-stu-id="8ddf8-114">Planned orders with **Approved** status are respected by master planning, so they are not modified or deleted during a later master planning run.</span></span> <span data-ttu-id="8ddf8-115">Per raggiungere questo obiettivo, la logica di pianificazione copia gli ordini pianificati con stato **Approvato** dalla vecchia versione del piano alla nuova versione del piano durante la pianificazione generale.</span><span class="sxs-lookup"><span data-stu-id="8ddf8-115">To achieve this, the planning logic copies the **Approved** planned orders from the old plan version to the new plan version during master planning.</span></span>

## <a name="firming-planned-orders"></a><span data-ttu-id="8ddf8-116">Stabilizzazione degli ordini pianificati</span><span class="sxs-lookup"><span data-stu-id="8ddf8-116">Firming planned orders</span></span> 
<span data-ttu-id="8ddf8-117">La stabilizzazione degli ordini pianificati consente di creare gli ordini effettivi.</span><span class="sxs-lookup"><span data-stu-id="8ddf8-117">By firming planned orders, real orders are created.</span></span> <span data-ttu-id="8ddf8-118">Sono inoltre noti come *ordini rilasciati* o *aperti*.</span><span class="sxs-lookup"><span data-stu-id="8ddf8-118">These are also known as *released* or *open orders*.</span></span> <span data-ttu-id="8ddf8-119">Quando un ordine pianificato viene stabilizzato, viene spostato nella sezione relativa agli ordini del modulo rilevante.</span><span class="sxs-lookup"><span data-stu-id="8ddf8-119">When a planned order is firmed, it's moved to the orders section of the relevant module.</span></span>

<span data-ttu-id="8ddf8-120">È possibile selezionare due opzioni di stabilizzazione dalla pagina **Ordini pianificati**:</span><span class="sxs-lookup"><span data-stu-id="8ddf8-120">You can select two firming options from the **Planned orders** page:</span></span>

-   <span data-ttu-id="8ddf8-121">**Stabilizza** - Questa opzione stabilizza uno o più ordini pianificati selezionati.</span><span class="sxs-lookup"><span data-stu-id="8ddf8-121">**Firm** – This will firm one or multiple selected planned orders.</span></span>
-   <span data-ttu-id="8ddf8-122">**Stabilizza tutto** - Questa opzione stabilizza tutti gli ordini pianificati nel filtro.</span><span class="sxs-lookup"><span data-stu-id="8ddf8-122">**Firm all** – This will firm all planned orders in the filter.</span></span> <span data-ttu-id="8ddf8-123">Con **Stabilizza tutto** non è necessario selezionare l'ordine pianificato, tutti gli ordini pianificati nel filtro verranno stabilizzati.</span><span class="sxs-lookup"><span data-stu-id="8ddf8-123">Using **Firm all** you don’t have to select the planned order, all planned orders within the filter will be firmed.</span></span> <span data-ttu-id="8ddf8-124">Questa opzione può essere utile se stai stabilizzando un numero elevato di ordini pianificati.</span><span class="sxs-lookup"><span data-stu-id="8ddf8-124">This option can be useful if you are firming a high number of planned orders.</span></span>

> [!NOTE]
> <span data-ttu-id="8ddf8-125">È possibile tenere traccia di un ordine pianificato stabilizzato da **Cronologia stabilizzazione** in **Modulo ordini pianificati > Visualizza > Cronologia stabilizzazione**.</span><span class="sxs-lookup"><span data-stu-id="8ddf8-125">You can track a planned order that was firmed from **Firming history** under **Planned orders form > View > Firming history**.</span></span>

## <a name="parallelize-firming"></a><span data-ttu-id="8ddf8-126">Stabilizzazione parallela</span><span class="sxs-lookup"><span data-stu-id="8ddf8-126">Parallelize firming</span></span>
<span data-ttu-id="8ddf8-127">Se si prevede di stabilizzare più ordini contemporaneamente, parallelizzare l'esecuzione può migliorare il tempo di esecuzione o le prestazioni.</span><span class="sxs-lookup"><span data-stu-id="8ddf8-127">If you are planning to firm many orders at the same time, parallelizing the run can improve the run time or performance.</span></span> <span data-ttu-id="8ddf8-128">Questa opzione è disponibile per stabilizzare più ordini pianificati con **Stabilizza** o **Stabilizza tutto**.</span><span class="sxs-lookup"><span data-stu-id="8ddf8-128">This option is available when firming multiple planned orders with either **Firm** or **Firm all**.</span></span> <span data-ttu-id="8ddf8-129">Sono disponibili i parametri seguenti:</span><span class="sxs-lookup"><span data-stu-id="8ddf8-129">The following parameters are available:</span></span>

-   <span data-ttu-id="8ddf8-130">**Stabilizzazione parallela** – Se **Sì**, il processo di stabilizzazione sarà parallelizzato con il numero di thread definiti in **Numero di thread**.</span><span class="sxs-lookup"><span data-stu-id="8ddf8-130">**Parallelize firming** – If **Yes**, the firming process will be parallelized with the number of threads defined in **Number of threads**.</span></span>
-   <span data-ttu-id="8ddf8-131">**Numero di thread** – Consente di controllare il numero di thread utilizzati per mettere in parallelo il processo di stabilizzazione.</span><span class="sxs-lookup"><span data-stu-id="8ddf8-131">**Number of threads** – Controls the number of threads used to parallelize the firming process.</span></span> <span data-ttu-id="8ddf8-132">Questo parametro viene visualizzato solo se **Stabilizzazione parallela** è impostato su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="8ddf8-132">The parameter is only shown when **Parallelize firming** is set to **Yes**.</span></span>

> [!NOTE]
> <span data-ttu-id="8ddf8-133">L'opzione per **Stabilizzazione parallela** viene visualizzata solo quando sono stati selezionati più ordini pianificati per la stabilizzazione.</span><span class="sxs-lookup"><span data-stu-id="8ddf8-133">The option for **Parallelize firming** is only shown when you have more than one planned order selected for firming.</span></span>

<a name="additional-resources"></a><span data-ttu-id="8ddf8-134">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="8ddf8-134">Additional resources</span></span>
--------

[<span data-ttu-id="8ddf8-135">Panoramica piani generali</span><span class="sxs-lookup"><span data-stu-id="8ddf8-135">Master plans overview</span></span>](master-plans.md)



