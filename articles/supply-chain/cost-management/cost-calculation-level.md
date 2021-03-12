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
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2020-04-23
ms.dyn365.ops.version: Release 10.0.12
ms.openlocfilehash: 42088d8c005cf3fc04e768f1b8e8c8ca0b8c6993
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4967733"
---
# <a name="cost-calculation-level"></a><span data-ttu-id="5a779-104">Livello di calcolo costi</span><span class="sxs-lookup"><span data-stu-id="5a779-104">Cost calculation level</span></span>

<span data-ttu-id="5a779-105">Il livello della distinta materiali (DBA) denominato **Livello di calcolo dei costi** esclude gli ordini di produzione e batch dai calcoli.</span><span class="sxs-lookup"><span data-stu-id="5a779-105">The bill of materials (BOM) level that is named **Cost calculation level** excludes production orders and batch orders from its calculations.</span></span> <span data-ttu-id="5a779-106">Il sistema utilizza questo livello quando esegue i calcoli dei costi nelle versioni di determinazione dei costi.</span><span class="sxs-lookup"><span data-stu-id="5a779-106">The system uses this level when it runs cost calculations in costing versions.</span></span> <span data-ttu-id="5a779-107">In processi come il ricalcolo e la chiusura dell'inventario, il sistema utilizza invece il livello DBS **Livello di determinazione costi**.</span><span class="sxs-lookup"><span data-stu-id="5a779-107">In processes such as recalculation and inventory close, the system uses the **Costing level** BOM level instead.</span></span>

<span data-ttu-id="5a779-108">Il seguente semplice scenario mostra le differenze tra il livello DBS **Livello di calcolo dei costi** e il livello DBS **Livello di determinazione costi** Livello DBA.</span><span class="sxs-lookup"><span data-stu-id="5a779-108">The following simple scenario shows the differences between the **Cost calculation level** BOM level and the **Costing level** BOM level.</span></span>

<span data-ttu-id="5a779-109">Sono disponibili tre prodotti: A, B e C. Il prodotto C è il componente del prodotto B e il prodotto B è il componente del prodotto A.</span><span class="sxs-lookup"><span data-stu-id="5a779-109">You have three products: A, B, and C. Product C is the component of product B, and product B is the component of product A.</span></span>

- <span data-ttu-id="5a779-110">**Livello di detyerminazione costi** assegna i seguenti livelli DBA:</span><span class="sxs-lookup"><span data-stu-id="5a779-110">**Costing level** assigns the following BOM levels:</span></span>

    - <span data-ttu-id="5a779-111">**Prodotto A:** 0</span><span class="sxs-lookup"><span data-stu-id="5a779-111">**Product A:** 0</span></span>
    - <span data-ttu-id="5a779-112">**Prodotto B:** 1</span><span class="sxs-lookup"><span data-stu-id="5a779-112">**Product B:** 1</span></span>
    - <span data-ttu-id="5a779-113">**Prodotto C:** 2</span><span class="sxs-lookup"><span data-stu-id="5a779-113">**Product C:** 2</span></span>

- <span data-ttu-id="5a779-114">**Livello di detyerminazione costi** assegna i seguenti livelli DBA:</span><span class="sxs-lookup"><span data-stu-id="5a779-114">**Cost calculation level** assigns the following BOM levels:</span></span>

    - <span data-ttu-id="5a779-115">**Prodotto A:** 0</span><span class="sxs-lookup"><span data-stu-id="5a779-115">**Product A:** 0</span></span>
    - <span data-ttu-id="5a779-116">**Prodotto B:** 1</span><span class="sxs-lookup"><span data-stu-id="5a779-116">**Product B:** 1</span></span>
    - <span data-ttu-id="5a779-117">**Prodotto C:** 2</span><span class="sxs-lookup"><span data-stu-id="5a779-117">**Product C:** 2</span></span>

<span data-ttu-id="5a779-118">Un ordine di produzione per il prodotto C viene quindi creato e il prodotto A è aggiunto alla DBA dell'ordine di produzione.</span><span class="sxs-lookup"><span data-stu-id="5a779-118">A production order for product C is then created, and product A is added to the production order BOM.</span></span> <span data-ttu-id="5a779-119">Dopo la stima dell'ordine, i livelli DBA vengono aggiornati nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="5a779-119">After the order is estimated, BOM levels are updated in the following way:</span></span>

- <span data-ttu-id="5a779-120">**Livello di detyerminazione costi** assegna i seguenti livelli DBA:</span><span class="sxs-lookup"><span data-stu-id="5a779-120">**Costing level** assigns the following BOM levels:</span></span>

    - <span data-ttu-id="5a779-121">**Prodotto B:** 1</span><span class="sxs-lookup"><span data-stu-id="5a779-121">**Product B:** 1</span></span>
    - <span data-ttu-id="5a779-122">**Prodotto C:** 2</span><span class="sxs-lookup"><span data-stu-id="5a779-122">**Product C:** 2</span></span>
    - <span data-ttu-id="5a779-123">**Prodotto A:** 3</span><span class="sxs-lookup"><span data-stu-id="5a779-123">**Product A:** 3</span></span>

- <span data-ttu-id="5a779-124">**Livello di detyerminazione costi** assegna i seguenti livelli DBA:</span><span class="sxs-lookup"><span data-stu-id="5a779-124">**Cost calculation level** assigns the following BOM levels:</span></span>

    - <span data-ttu-id="5a779-125">**Prodotto A:** 0</span><span class="sxs-lookup"><span data-stu-id="5a779-125">**Product A:** 0</span></span>
    - <span data-ttu-id="5a779-126">**Prodotto B:** 1</span><span class="sxs-lookup"><span data-stu-id="5a779-126">**Product B:** 1</span></span>
    - <span data-ttu-id="5a779-127">**Prodotto C:** 2</span><span class="sxs-lookup"><span data-stu-id="5a779-127">**Product C:** 2</span></span>

<span data-ttu-id="5a779-128">Questo comportamento garantisce che le modifiche alle DBA dell'ordine di produzione non influiscano sui calcoli dei costi successivi.</span><span class="sxs-lookup"><span data-stu-id="5a779-128">This behavior ensures that changes to production order BOMs don't affect subsequent cost calculations.</span></span>
