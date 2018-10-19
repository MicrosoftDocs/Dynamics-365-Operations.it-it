---
title: Gestisci ordini pianificati
description: "Questo argomento fornisce informazioni sulla modalità di gestione degli ordini pianificati. Viene descritto come aggiornare lo stato degli ordini pianificati, stabilizzarli e filtrare gli ordini pianificati con lo stesso stato dell'ordine pianificato selezionato."
author: roxanadiaconu
manager: AnnBe
ms.date: 10/02/2018
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
ms.sourcegitcommit: 657c19896b20a514dc5308bf7fb086085b482fec
ms.openlocfilehash: bf578d98abc4825c5607ec031da6ab6737c3183a
ms.contentlocale: it-it
ms.lasthandoff: 10/16/2018

---

# <a name="maintain-planned-orders"></a><span data-ttu-id="3b2c1-104">Gestisci ordini pianificati</span><span class="sxs-lookup"><span data-stu-id="3b2c1-104">Maintain planned orders</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="3b2c1-105">Questo argomento fornisce informazioni sulla modalità di gestione degli ordini pianificati.</span><span class="sxs-lookup"><span data-stu-id="3b2c1-105">This topic provides information about how to manage planned orders.</span></span> <span data-ttu-id="3b2c1-106">Viene descritto come aggiornare lo stato degli ordini pianificati, stabilizzarli e filtrare gli ordini pianificati con lo stesso stato dell'ordine pianificato selezionato.</span><span class="sxs-lookup"><span data-stu-id="3b2c1-106">It describes how you can update the status of planned orders, firm them, and filter for planned orders that have the same status as a selected planned order.</span></span>

<span data-ttu-id="3b2c1-107">È possibile gestire gli ordini pianificati nell'area di lavoro **Pianificazione generale**, nell'elenco **Ordine pianificato** o negli elenchi **Ordini di produzione pianificati**, **Ordini fornitore pianificati** e **Trasferimento pianificato**.</span><span class="sxs-lookup"><span data-stu-id="3b2c1-107">You can manage planned orders from the **Master planning** workspace, the **Planned order** list, or the **Planned production orders**, **Planned purchase orders**, and **Planned transfer** lists.</span></span> <span data-ttu-id="3b2c1-108">È possibile utilizzare il campo **Stato** per tenere facilmente traccia dell'avanzamento.</span><span class="sxs-lookup"><span data-stu-id="3b2c1-108">You can use the **Status** field to help track your progress.</span></span> <span data-ttu-id="3b2c1-109">Vengono utilizzati i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="3b2c1-109">The following values are used:</span></span>

-   <span data-ttu-id="3b2c1-110">Agli ordini pianificati generati mediante la pianificazione generale viene assegnato uno stato di **Inevaso**.</span><span class="sxs-lookup"><span data-stu-id="3b2c1-110">When master planning generates planned orders, the planned orders have a status of **Unprocessed**.</span></span>
-   <span data-ttu-id="3b2c1-111">A un ordine pianificato che si sceglie di non stabilizzare è possibile assegnare uno stato di **Completato**.</span><span class="sxs-lookup"><span data-stu-id="3b2c1-111">If you decide not to firm a planned order, you can give it a status of **Completed**.</span></span>
-   <span data-ttu-id="3b2c1-112">A un ordine pianificato che si sceglie di non stabilizzare è possibile assegnare uno stato di **Approvato**.</span><span class="sxs-lookup"><span data-stu-id="3b2c1-112">When you decide to firm a planned order, you can give it a status of **Approved**.</span></span> <span data-ttu-id="3b2c1-113">Questo stato indica che si approva la stabilizzazione dell'ordine pianificato, ma che questa operazione non è ancora stata effettuata.</span><span class="sxs-lookup"><span data-stu-id="3b2c1-113">This status indicates that you approve firming of the planned order, but it isn't firmed yet.</span></span>

<span data-ttu-id="3b2c1-114">**Nota:** un ordine pianificato approvato viene trasferito con lo stato corrente al calcolo successivo della pianificazione generale.</span><span class="sxs-lookup"><span data-stu-id="3b2c1-114">**Note:** An approved planned order is transferred, in its current state, to the next master planning calculation.</span></span> <span data-ttu-id="3b2c1-115">È possibile stabilizzare gli ordini pianificati facendo clic su **Stabilizza**.</span><span class="sxs-lookup"><span data-stu-id="3b2c1-115">You can firm planned orders by clicking **Firm**.</span></span> <span data-ttu-id="3b2c1-116">Di seguito sono riportati gli ordini pianificati che è possibile stabilizzare:</span><span class="sxs-lookup"><span data-stu-id="3b2c1-116">You can firm the following planned orders:</span></span>

-   <span data-ttu-id="3b2c1-117">L'ordine pianificato selezionato.</span><span class="sxs-lookup"><span data-stu-id="3b2c1-117">The planned order that is selected.</span></span>
-   <span data-ttu-id="3b2c1-118">Più ordini pianificati.</span><span class="sxs-lookup"><span data-stu-id="3b2c1-118">Multiple planned orders.</span></span>
-   <span data-ttu-id="3b2c1-119">Ordini pianificati generati da un'esplosione nella pagina **Esplosione**.</span><span class="sxs-lookup"><span data-stu-id="3b2c1-119">Planned orders that are generated by an explosion from the **Explosion** page.</span></span> <span data-ttu-id="3b2c1-120">Fare clic su **Ordini pianificati**, selezionare l'ordine pianificato, quindi fare clic su **Stabilizza**.</span><span class="sxs-lookup"><span data-stu-id="3b2c1-120">Click **Planned orders**, select the planned order, and then click **Firm**.</span></span>

<span data-ttu-id="3b2c1-121">Quando un ordine pianificato viene stabilizzato, viene spostato nella sezione relativa agli ordini del modulo rilevante.</span><span class="sxs-lookup"><span data-stu-id="3b2c1-121">When a planned order is firmed, it's moved to the orders section of the relevant module.</span></span> 

<a name="additional-resources"></a><span data-ttu-id="3b2c1-122">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="3b2c1-122">Additional resources</span></span>
--------

[<span data-ttu-id="3b2c1-123">Piani generali</span><span class="sxs-lookup"><span data-stu-id="3b2c1-123">Master plans</span></span>](master-plans.md)




