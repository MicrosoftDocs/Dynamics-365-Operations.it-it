---
title: Origini comuni degli scostamenti di produzione
description: Questo articolo illustra le varie origini normali di ciascun tipo di scostamento produzione.
author: AndersGirke
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventCostTrans, ProdCalcVarianceTrans
audience: Application User
ms.reviewer: kamaybac
ms.custom: 79753
ms.assetid: 14ac7db4-fb40-43c1-bb0d-1d51fc91d24f
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f627cb1d15d0fa858abae588d149875967cff97c
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5813245"
---
# <a name="common-sources-of-production-variances"></a><span data-ttu-id="fd8fb-103">Origini comuni degli scostamenti di produzione</span><span class="sxs-lookup"><span data-stu-id="fd8fb-103">Common sources of production variances</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="fd8fb-104">Questo articolo illustra le varie origini normali di ciascun tipo di scostamento produzione.</span><span class="sxs-lookup"><span data-stu-id="fd8fb-104">This article explains various typical sources of each type of production variance.</span></span> 

<span data-ttu-id="fd8fb-105">Di seguito sono alcune origini tipiche di uno scostamento di **dimensioni lotto**:</span><span class="sxs-lookup"><span data-stu-id="fd8fb-105">Here are some typical sources of a **lot size** variance:</span></span>

-   <span data-ttu-id="fd8fb-106">La quantità idonea per un ordine di produzione è diversa dalla quantità utilizzata nel calcolo dei costi standard.</span><span class="sxs-lookup"><span data-stu-id="fd8fb-106">The good quantity for a production order differs from the calculation quantity that is used in the standard cost calculation.</span></span> <span data-ttu-id="fd8fb-107">La quantità costituisce la base per l'ammortamento dei costi costanti.</span><span class="sxs-lookup"><span data-stu-id="fd8fb-107">The quantity provides the basis for amortizing constant costs.</span></span>
-   <span data-ttu-id="fd8fb-108">Il valore dei costi costanti nell'ordine di produzione è diverso da quello dei costi costanti utilizzati nel calcolo dei costi standard.</span><span class="sxs-lookup"><span data-stu-id="fd8fb-108">The value of constant costs on the production order differs from the constant costs that are used in the standard cost calculation.</span></span> <span data-ttu-id="fd8fb-109">I costi costanti nell'ordine di produzione possono differire per diversi motivi.</span><span class="sxs-lookup"><span data-stu-id="fd8fb-109">The constant costs on the production order can differ for several reasons.</span></span> <span data-ttu-id="fd8fb-110">Ad esempio, i costi costanti potrebbero riflettere i fattori seguenti:</span><span class="sxs-lookup"><span data-stu-id="fd8fb-110">For example, the constant costs might reflect the following factors:</span></span>
    -   <span data-ttu-id="fd8fb-111">Modifiche manuali apportate alla distinta base (DBA) di produzione o al ciclo di produzione</span><span class="sxs-lookup"><span data-stu-id="fd8fb-111">Manual changes to the production bill of materials (BOM) or route</span></span>
    -   <span data-ttu-id="fd8fb-112">La selezione di una diversa versione DBA o versione del ciclo di lavorazione durante la creazione dell'ordine di produzione</span><span class="sxs-lookup"><span data-stu-id="fd8fb-112">The selection of a different BOM version or route version when you create the production order</span></span>
    -   <span data-ttu-id="fd8fb-113">Modifiche di progettazione pianificate apportate alla versione DBA o alla versione del ciclo di lavorazione assegnata all'articolo.</span><span class="sxs-lookup"><span data-stu-id="fd8fb-113">Planned engineering changes to the BOM version or route version that is assigned to the item</span></span>

<span data-ttu-id="fd8fb-114">Di seguito sono alcune origini tipiche di uno scostamento di **prezzi di produzione**:</span><span class="sxs-lookup"><span data-stu-id="fd8fb-114">Here are some typical sources of a **production price** variance:</span></span>

-   <span data-ttu-id="fd8fb-115">La categoria costi (e il prezzo della categoria costi) per il consumo dichiarato di un'operazione relativa ai cicli di lavorazione è diversa dalla categoria costi utilizzata nel calcolo dei costi standard.</span><span class="sxs-lookup"><span data-stu-id="fd8fb-115">The cost category (and cost category price) for the reported consumption of a routing operation differs from the cost category that is used in standard cost calculation.</span></span>
-   <span data-ttu-id="fd8fb-116">Il costo attivo relativo al prezzo della categoria di costi è diverso dal prezzo della categoria di costi utilizzata nel calcolo di costo standard.</span><span class="sxs-lookup"><span data-stu-id="fd8fb-116">The active cost for the cost category price differs from the cost category price that is used in standard cost calculation.</span></span>

<span data-ttu-id="fd8fb-117">Di seguito sono alcune origini tipiche di uno scostamento di **quantità di produzione**:</span><span class="sxs-lookup"><span data-stu-id="fd8fb-117">Here are some typical sources of a **production quantity** variance:</span></span>

-   <span data-ttu-id="fd8fb-118">Uscita eccessiva o insufficiente di un componente del materiale.</span><span class="sxs-lookup"><span data-stu-id="fd8fb-118">You over-issue or under-issue a material component.</span></span>
-   <span data-ttu-id="fd8fb-119">Dichiarazione ore eccessiva o insufficiente per una operazione relativa ai percorsi di trasferimento.</span><span class="sxs-lookup"><span data-stu-id="fd8fb-119">You over-report or under-report the time for a routing operation.</span></span>
-   <span data-ttu-id="fd8fb-120">Ricezione eccessiva o insufficiente di quantità idonea dell'elemento padre, rispetto alla quantità ordine.</span><span class="sxs-lookup"><span data-stu-id="fd8fb-120">You over-receive or under-receive the good quantity of the parent item, relative to the order quantity.</span></span> <span data-ttu-id="fd8fb-121">Tuttavia, si verifica l'uscita completa di componenti e la dichiarazione completa di operazioni in base alla quantità dell'ordine di produzione.</span><span class="sxs-lookup"><span data-stu-id="fd8fb-121">However, you issue components and report operations completely, based on the order quantity for the production order.</span></span>

<span data-ttu-id="fd8fb-122">Di seguito sono alcune origini tipiche di uno scostamento **sostitutivo di produzione**:</span><span class="sxs-lookup"><span data-stu-id="fd8fb-122">Here are some typical sources of a **production substitution** variance:</span></span>

-   <span data-ttu-id="fd8fb-123">Uscita di un componente del materiale non presente nella DBA di produzione.</span><span class="sxs-lookup"><span data-stu-id="fd8fb-123">You issue a material component that isn't on the production BOM.</span></span>
-   <span data-ttu-id="fd8fb-124">Aggiunta manuale di un componente alla DBA di produzione e dichiarazione dello stesso come consumato.</span><span class="sxs-lookup"><span data-stu-id="fd8fb-124">You manually add a component to the production BOM and report that component as consumed.</span></span>
-   <span data-ttu-id="fd8fb-125">Dichiarare un articolo come consumato senza l'aggiunta manuale dello stesso alla DBA di produzione.</span><span class="sxs-lookup"><span data-stu-id="fd8fb-125">You report an item as consumed but don't manually add it to the production BOM.</span></span>
-   <span data-ttu-id="fd8fb-126">Aggiunta manuale di un'operazione al ciclo di lavorazione di produzione e dichiarazione della stessa come consumata.</span><span class="sxs-lookup"><span data-stu-id="fd8fb-126">You manually add an operation to the production route and report that operation as consumed.</span></span>
-   <span data-ttu-id="fd8fb-127">Quando si crea l'ordine di produzione, si seleziona una versione DBA diversa dalla versione DBA utilizzata nel calcolo di costo standard.</span><span class="sxs-lookup"><span data-stu-id="fd8fb-127">When you create the production order, you select a BOM version that differs from the BOM version that is used in the standard cost calculation.</span></span>
-   <span data-ttu-id="fd8fb-128">Quando si crea l'ordine di produzione, si seleziona una versione del ciclo di lavorazione diversa dalla versione del ciclo di lavorazione utilizzata nel calcolo di costo standard.</span><span class="sxs-lookup"><span data-stu-id="fd8fb-128">When you create the production order, you select a route version that differs from the route version that is used in the standard cost calculation.</span></span>






[!INCLUDE[footer-include](../../includes/footer-banner.md)]