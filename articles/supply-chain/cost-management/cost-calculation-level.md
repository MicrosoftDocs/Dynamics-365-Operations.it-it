---
title: Livello di calcolo dei costi
description: Questo argomento descrive il livello di distinta materiali (DBA) denominato Livello di calcolo dei costi. Questo livello DBA esclude gli ordini di produzione e batch dai calcoli.
author: AndersGirke
ms.date: 04/23/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2020-04-23
ms.dyn365.ops.version: Release 10.0.12
ms.openlocfilehash: f7cde239107528a6bc2aeb0e424d024d4f3fb2a6
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5839489"
---
# <a name="cost-calculation-level"></a><span data-ttu-id="765d8-104">Livello di calcolo costi</span><span class="sxs-lookup"><span data-stu-id="765d8-104">Cost calculation level</span></span>

<span data-ttu-id="765d8-105">Il livello della distinta materiali (DBA) denominato **Livello di calcolo dei costi** esclude gli ordini di produzione e batch dai calcoli.</span><span class="sxs-lookup"><span data-stu-id="765d8-105">The bill of materials (BOM) level that is named **Cost calculation level** excludes production orders and batch orders from its calculations.</span></span> <span data-ttu-id="765d8-106">Il sistema utilizza questo livello quando esegue i calcoli dei costi nelle versioni di determinazione dei costi.</span><span class="sxs-lookup"><span data-stu-id="765d8-106">The system uses this level when it runs cost calculations in costing versions.</span></span> <span data-ttu-id="765d8-107">In processi come il ricalcolo e la chiusura dell'inventario, il sistema utilizza invece il livello DBS **Livello di determinazione costi**.</span><span class="sxs-lookup"><span data-stu-id="765d8-107">In processes such as recalculation and inventory close, the system uses the **Costing level** BOM level instead.</span></span>

<span data-ttu-id="765d8-108">Il seguente semplice scenario mostra le differenze tra il livello DBS **Livello di calcolo dei costi** e il livello DBS **Livello di determinazione costi** Livello DBA.</span><span class="sxs-lookup"><span data-stu-id="765d8-108">The following simple scenario shows the differences between the **Cost calculation level** BOM level and the **Costing level** BOM level.</span></span>

<span data-ttu-id="765d8-109">Sono disponibili tre prodotti: A, B e C. Il prodotto C è il componente del prodotto B e il prodotto B è il componente del prodotto A.</span><span class="sxs-lookup"><span data-stu-id="765d8-109">You have three products: A, B, and C. Product C is the component of product B, and product B is the component of product A.</span></span>

- <span data-ttu-id="765d8-110">**Livello di detyerminazione costi** assegna i seguenti livelli DBA:</span><span class="sxs-lookup"><span data-stu-id="765d8-110">**Costing level** assigns the following BOM levels:</span></span>

    - <span data-ttu-id="765d8-111">**Prodotto A:** 0</span><span class="sxs-lookup"><span data-stu-id="765d8-111">**Product A:** 0</span></span>
    - <span data-ttu-id="765d8-112">**Prodotto B:** 1</span><span class="sxs-lookup"><span data-stu-id="765d8-112">**Product B:** 1</span></span>
    - <span data-ttu-id="765d8-113">**Prodotto C:** 2</span><span class="sxs-lookup"><span data-stu-id="765d8-113">**Product C:** 2</span></span>

- <span data-ttu-id="765d8-114">**Livello di detyerminazione costi** assegna i seguenti livelli DBA:</span><span class="sxs-lookup"><span data-stu-id="765d8-114">**Cost calculation level** assigns the following BOM levels:</span></span>

    - <span data-ttu-id="765d8-115">**Prodotto A:** 0</span><span class="sxs-lookup"><span data-stu-id="765d8-115">**Product A:** 0</span></span>
    - <span data-ttu-id="765d8-116">**Prodotto B:** 1</span><span class="sxs-lookup"><span data-stu-id="765d8-116">**Product B:** 1</span></span>
    - <span data-ttu-id="765d8-117">**Prodotto C:** 2</span><span class="sxs-lookup"><span data-stu-id="765d8-117">**Product C:** 2</span></span>

<span data-ttu-id="765d8-118">Un ordine di produzione per il prodotto C viene quindi creato e il prodotto A è aggiunto alla DBA dell'ordine di produzione.</span><span class="sxs-lookup"><span data-stu-id="765d8-118">A production order for product C is then created, and product A is added to the production order BOM.</span></span> <span data-ttu-id="765d8-119">Dopo la stima dell'ordine, i livelli DBA vengono aggiornati nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="765d8-119">After the order is estimated, BOM levels are updated in the following way:</span></span>

- <span data-ttu-id="765d8-120">**Livello di detyerminazione costi** assegna i seguenti livelli DBA:</span><span class="sxs-lookup"><span data-stu-id="765d8-120">**Costing level** assigns the following BOM levels:</span></span>

    - <span data-ttu-id="765d8-121">**Prodotto B:** 1</span><span class="sxs-lookup"><span data-stu-id="765d8-121">**Product B:** 1</span></span>
    - <span data-ttu-id="765d8-122">**Prodotto C:** 2</span><span class="sxs-lookup"><span data-stu-id="765d8-122">**Product C:** 2</span></span>
    - <span data-ttu-id="765d8-123">**Prodotto A:** 3</span><span class="sxs-lookup"><span data-stu-id="765d8-123">**Product A:** 3</span></span>

- <span data-ttu-id="765d8-124">**Livello di detyerminazione costi** assegna i seguenti livelli DBA:</span><span class="sxs-lookup"><span data-stu-id="765d8-124">**Cost calculation level** assigns the following BOM levels:</span></span>

    - <span data-ttu-id="765d8-125">**Prodotto A:** 0</span><span class="sxs-lookup"><span data-stu-id="765d8-125">**Product A:** 0</span></span>
    - <span data-ttu-id="765d8-126">**Prodotto B:** 1</span><span class="sxs-lookup"><span data-stu-id="765d8-126">**Product B:** 1</span></span>
    - <span data-ttu-id="765d8-127">**Prodotto C:** 2</span><span class="sxs-lookup"><span data-stu-id="765d8-127">**Product C:** 2</span></span>

<span data-ttu-id="765d8-128">Questo comportamento garantisce che le modifiche alle DBA dell'ordine di produzione non influiscano sui calcoli dei costi successivi.</span><span class="sxs-lookup"><span data-stu-id="765d8-128">This behavior ensures that changes to production order BOMs don't affect subsequent cost calculations.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]