---
title: Livello di calcolo dei costi
description: Questo argomento descrive il livello di distinta materiali (DBA) denominato Livello di calcolo dei costi. Questo livello DBA esclude gli ordini di produzione e batch dai calcoli.
author: AndersGirke
manager: tfehr
ms.date: 04/23/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2020-04-23
ms.dyn365.ops.version: Release 10.0.12
ms.openlocfilehash: 52b77e794ee38add556ac01d62c973b38c48a548
ms.sourcegitcommit: a3cd2783ae120ac6681431c010b9b126a9ca7d94
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/29/2020
ms.locfileid: "3410960"
---
# <a name="cost-calculation-level"></a><span data-ttu-id="771f7-104">Livello di calcolo costi</span><span class="sxs-lookup"><span data-stu-id="771f7-104">Cost calculation level</span></span>

<span data-ttu-id="771f7-105">Il livello della distinta materiali (DBA) denominato **Livello di calcolo dei costi** esclude gli ordini di produzione e batch dai calcoli.</span><span class="sxs-lookup"><span data-stu-id="771f7-105">The bill of materials (BOM) level that is named **Cost calculation level** excludes production orders and batch orders from its calculations.</span></span> <span data-ttu-id="771f7-106">Il sistema utilizza questo livello quando esegue i calcoli dei costi nelle versioni di determinazione dei costi.</span><span class="sxs-lookup"><span data-stu-id="771f7-106">The system uses this level when it runs cost calculations in costing versions.</span></span> <span data-ttu-id="771f7-107">In processi come il ricalcolo e la chiusura dell'inventario, il sistema utilizza invece il livello DBS **Livello di determinazione costi**.</span><span class="sxs-lookup"><span data-stu-id="771f7-107">In processes such as recalculation and inventory close, the system uses the **Costing level** BOM level instead.</span></span>

<span data-ttu-id="771f7-108">Il seguente semplice scenario mostra le differenze tra il livello DBS **Livello di calcolo dei costi** e il livello DBS **Livello di determinazione costi**Livello DBA.</span><span class="sxs-lookup"><span data-stu-id="771f7-108">The following simple scenario shows the differences between the **Cost calculation level** BOM level and the **Costing level** BOM level.</span></span>

<span data-ttu-id="771f7-109">Sono disponibili tre prodotti: A, B e C. Il prodotto C è il componente del prodotto B e il prodotto B è il componente del prodotto A.</span><span class="sxs-lookup"><span data-stu-id="771f7-109">You have three products: A, B, and C. Product C is the component of product B, and product B is the component of product A.</span></span>

- <span data-ttu-id="771f7-110">**Livello di detyerminazione costi** assegna i seguenti livelli DBA:</span><span class="sxs-lookup"><span data-stu-id="771f7-110">**Costing level** assigns the following BOM levels:</span></span>

    - <span data-ttu-id="771f7-111">**Prodotto A:** 0</span><span class="sxs-lookup"><span data-stu-id="771f7-111">**Product A:** 0</span></span>
    - <span data-ttu-id="771f7-112">**Prodotto B:** 1</span><span class="sxs-lookup"><span data-stu-id="771f7-112">**Product B:** 1</span></span>
    - <span data-ttu-id="771f7-113">**Prodotto C:** 2</span><span class="sxs-lookup"><span data-stu-id="771f7-113">**Product C:** 2</span></span>

- <span data-ttu-id="771f7-114">**Livello di detyerminazione costi** assegna i seguenti livelli DBA:</span><span class="sxs-lookup"><span data-stu-id="771f7-114">**Cost calculation level** assigns the following BOM levels:</span></span>

    - <span data-ttu-id="771f7-115">**Prodotto A:** 0</span><span class="sxs-lookup"><span data-stu-id="771f7-115">**Product A:** 0</span></span>
    - <span data-ttu-id="771f7-116">**Prodotto B:** 1</span><span class="sxs-lookup"><span data-stu-id="771f7-116">**Product B:** 1</span></span>
    - <span data-ttu-id="771f7-117">**Prodotto C:** 2</span><span class="sxs-lookup"><span data-stu-id="771f7-117">**Product C:** 2</span></span>

<span data-ttu-id="771f7-118">Un ordine di produzione per il prodotto C viene quindi creato e il prodotto A è aggiunto alla DBA dell'ordine di produzione.</span><span class="sxs-lookup"><span data-stu-id="771f7-118">A production order for product C is then created, and product A is added to the production order BOM.</span></span> <span data-ttu-id="771f7-119">Dopo la stima dell'ordine, i livelli DBA vengono aggiornati nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="771f7-119">After the order is estimated, BOM levels are updated in the following way:</span></span>

- <span data-ttu-id="771f7-120">**Livello di detyerminazione costi** assegna i seguenti livelli DBA:</span><span class="sxs-lookup"><span data-stu-id="771f7-120">**Costing level** assigns the following BOM levels:</span></span>

    - <span data-ttu-id="771f7-121">**Prodotto B:** 1</span><span class="sxs-lookup"><span data-stu-id="771f7-121">**Product B:** 1</span></span>
    - <span data-ttu-id="771f7-122">**Prodotto C:** 2</span><span class="sxs-lookup"><span data-stu-id="771f7-122">**Product C:** 2</span></span>
    - <span data-ttu-id="771f7-123">**Prodotto A:** 3</span><span class="sxs-lookup"><span data-stu-id="771f7-123">**Product A:** 3</span></span>

- <span data-ttu-id="771f7-124">**Livello di detyerminazione costi** assegna i seguenti livelli DBA:</span><span class="sxs-lookup"><span data-stu-id="771f7-124">**Cost calculation level** assigns the following BOM levels:</span></span>

    - <span data-ttu-id="771f7-125">**Prodotto A:** 0</span><span class="sxs-lookup"><span data-stu-id="771f7-125">**Product A:** 0</span></span>
    - <span data-ttu-id="771f7-126">**Prodotto B:** 1</span><span class="sxs-lookup"><span data-stu-id="771f7-126">**Product B:** 1</span></span>
    - <span data-ttu-id="771f7-127">**Prodotto C:** 2</span><span class="sxs-lookup"><span data-stu-id="771f7-127">**Product C:** 2</span></span>

<span data-ttu-id="771f7-128">Questo comportamento garantisce che le modifiche alle DBA dell'ordine di produzione non influiscano sui calcoli dei costi successivi.</span><span class="sxs-lookup"><span data-stu-id="771f7-128">This behavior ensures that changes to production order BOMs don't affect subsequent cost calculations.</span></span>
