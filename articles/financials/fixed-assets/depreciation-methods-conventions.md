---
title: Metodi e convenzioni di ammortamento
description: Questo articolo fornisce una panoramica delle convenzioni e dei metodi di ammortamento che sono supportati da Microsoft Dynamics 365 for Finance and Operations.
author: twheeloc
manager: AnnBe
ms.date: 04/25/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AssetDepreciationProfile, AssetGroupBookSetup, AssetGroupDepBookSetup
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 3441
ms.assetid: 1d8267b1-86a8-44bf-8814-f56b5d45a0ae
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: eb38de1e7e39cb66d15bfe344f6f5fcd5d4fccd7
ms.contentlocale: it-it
ms.lasthandoff: 03/26/2018

---

# <a name="depreciation-methods-and-conventions"></a><span data-ttu-id="5c5dd-103">Metodi e convenzioni di ammortamento</span><span class="sxs-lookup"><span data-stu-id="5c5dd-103">Depreciation methods and conventions</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="5c5dd-104">Questo articolo fornisce una panoramica delle convenzioni e dei metodi di ammortamento che sono supportati da Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="5c5dd-104">This article provides an overview of the depreciation conventions and depreciation methods that are supported by Microsoft Dynamics 365 for Finance and Operations.</span></span>

<span data-ttu-id="5c5dd-105">È possibile selezionare diversi metodi e convenzioni di ammortamento.</span><span class="sxs-lookup"><span data-stu-id="5c5dd-105">You can select various depreciation methods and conventions.</span></span> <span data-ttu-id="5c5dd-106">Scopo dei metodi è l'allocazione del valore ammortizzabile del cespite ai periodi fiscali.</span><span class="sxs-lookup"><span data-stu-id="5c5dd-106">The purpose of the methods is to allocate the depreciable value of the fixed asset into fiscal periods.</span></span> <span data-ttu-id="5c5dd-107">Tale valore corrisponde al prezzo di acquisizione da cui viene dedotto un valore di scarto, se presente.</span><span class="sxs-lookup"><span data-stu-id="5c5dd-107">The depreciable value of the fixed asset is the acquisition price, reduced by a scrap value, if any.</span></span> 

<span data-ttu-id="5c5dd-108">Se si utilizzano le convenzioni di ammortamento e si modifica la data di esecuzione dell'ultimo ammortamento di un cespite, determinando l'annullamento di alcuni ammortamenti, l'ammortamento relativo all'ultimo anno può risultare maggiore o minore del previsto.</span><span class="sxs-lookup"><span data-stu-id="5c5dd-108">If you are using depreciation conventions and you modify the last depreciation run date for an asset, which then causes some depreciations to be skipped, the depreciation for the last year might be more than or less than is expected.</span></span> <span data-ttu-id="5c5dd-109">L'ammortamento viene rettificato in base al numero di periodi di ammortamento interessati dalla modifica della data di esecuzione dell'ultimo ammortamento.</span><span class="sxs-lookup"><span data-stu-id="5c5dd-109">The depreciation is adjusted by the number of depreciation periods affected by the modification of the last depreciation run date.</span></span>

<span data-ttu-id="5c5dd-110">Ad esempio, se si utilizza la convenzione di ammortamento semestrale su tre anni, l'ammortamento viene in genere eseguito su 3 anni e mezzo.</span><span class="sxs-lookup"><span data-stu-id="5c5dd-110">For example, if you are using the Half year depreciation convention over three years, depreciation ordinarily occurs over 3 1/2 years.</span></span> <span data-ttu-id="5c5dd-111">Se durante questo intervallo di tempo la data di esecuzione dell'ultimo ammortamento viene modificata, il numero di periodi interessati nell'ultimo anno di ammortamento viene esteso.</span><span class="sxs-lookup"><span data-stu-id="5c5dd-111">If you change the last depreciation run date during the 3 1/2 years, the last year of depreciation moves out the number of periods affected.</span></span> <span data-ttu-id="5c5dd-112">Se si sposta la data di tre mesi, nell'ultimo anno verranno considerati nove mesi di ammortamento, mentre normalmente dovrebbero essere solo sei.</span><span class="sxs-lookup"><span data-stu-id="5c5dd-112">If you move the date by three months, the last year will have nine months’ worth of depreciation, when ordinarily there would be six months’ worth of depreciation.</span></span>

<span data-ttu-id="5c5dd-113">È possibile selezionare una delle convenzioni di ammortamento riportate di seguito.</span><span class="sxs-lookup"><span data-stu-id="5c5dd-113">You can select from the following depreciation conventions.</span></span>


-   <span data-ttu-id="5c5dd-114">Semestre</span><span class="sxs-lookup"><span data-stu-id="5c5dd-114">Half year</span></span>
-   <span data-ttu-id="5c5dd-115">Mese intero</span><span class="sxs-lookup"><span data-stu-id="5c5dd-115">Full month</span></span>
-   <span data-ttu-id="5c5dd-116">Metà trimestre</span><span class="sxs-lookup"><span data-stu-id="5c5dd-116">Mid quarter</span></span>
-   <span data-ttu-id="5c5dd-117">Metà mese (giorno 1 del mese)</span><span class="sxs-lookup"><span data-stu-id="5c5dd-117">Mid month (1st of month)</span></span>
-   <span data-ttu-id="5c5dd-118">Metà mese (giorno 15 del mese)</span><span class="sxs-lookup"><span data-stu-id="5c5dd-118">Mid month (15th of month)</span></span>
-   <span data-ttu-id="5c5dd-119">Semestre (inizio anno)</span><span class="sxs-lookup"><span data-stu-id="5c5dd-119">Half year (start of year)</span></span>
-   <span data-ttu-id="5c5dd-120">Semestre (prossimo anno)</span><span class="sxs-lookup"><span data-stu-id="5c5dd-120">Half year (next year)</span></span>

<span data-ttu-id="5c5dd-121">È possibile selezionare uno dei metodi di ammortamento riportate di seguito.</span><span class="sxs-lookup"><span data-stu-id="5c5dd-121">You can select from the following depreciation methods.</span></span>
-   <span data-ttu-id="5c5dd-122">Vita utile a quote costanti</span><span class="sxs-lookup"><span data-stu-id="5c5dd-122">Straight line service life</span></span>
-   <span data-ttu-id="5c5dd-123">A saldi decrescenti</span><span class="sxs-lookup"><span data-stu-id="5c5dd-123">Reducing balance</span></span>
-   <span data-ttu-id="5c5dd-124">Manuale</span><span class="sxs-lookup"><span data-stu-id="5c5dd-124">Manual</span></span>
-   <span data-ttu-id="5c5dd-125">Fattore</span><span class="sxs-lookup"><span data-stu-id="5c5dd-125">Factor</span></span>
-   <span data-ttu-id="5c5dd-126">Consumo</span><span class="sxs-lookup"><span data-stu-id="5c5dd-126">Consumption</span></span>
-   <span data-ttu-id="5c5dd-127">Vita utile rimanente a quote costanti</span><span class="sxs-lookup"><span data-stu-id="5c5dd-127">Straight line life remaining</span></span>
-   <span data-ttu-id="5c5dd-128">Saldo decrescente 200%</span><span class="sxs-lookup"><span data-stu-id="5c5dd-128">200% reducing balance</span></span>
-   <span data-ttu-id="5c5dd-129">Saldo decrescente 175%</span><span class="sxs-lookup"><span data-stu-id="5c5dd-129">175% reducing balance</span></span>
-   <span data-ttu-id="5c5dd-130">Saldo decrescente 150%</span><span class="sxs-lookup"><span data-stu-id="5c5dd-130">150% reducing balance</span></span>
-   <span data-ttu-id="5c5dd-131">Saldo decrescente 125%</span><span class="sxs-lookup"><span data-stu-id="5c5dd-131">125% reducing balance</span></span>

 



<a name="see-also"></a><span data-ttu-id="5c5dd-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5c5dd-132">See also</span></span>
--------

[<span data-ttu-id="5c5dd-133">Ammortamento cespiti</span><span class="sxs-lookup"><span data-stu-id="5c5dd-133">Fixed asset depreciation</span></span>](fixed-asset-depreciation.md)

[<span data-ttu-id="5c5dd-134">Ammortamento a quote costanti basato sulla vita utile</span><span class="sxs-lookup"><span data-stu-id="5c5dd-134">Straight line service life depreciation</span></span>](Straight-line-service-life-depreciation.md)

[<span data-ttu-id="5c5dd-135">Ammortamento a saldi decrescenti</span><span class="sxs-lookup"><span data-stu-id="5c5dd-135">Reducing balance depreciation</span></span>](reduce-balance-depreciation.md)

[<span data-ttu-id="5c5dd-136">Ammortamento manuale</span><span class="sxs-lookup"><span data-stu-id="5c5dd-136">Manual depreciation</span></span>](manual-depreciation.md)

[<span data-ttu-id="5c5dd-137">Ammortamento basato su coefficiente</span><span class="sxs-lookup"><span data-stu-id="5c5dd-137">Factor depreciation</span></span>](factor-depreciation.md)

[<span data-ttu-id="5c5dd-138">Ammortamento del consumo</span><span class="sxs-lookup"><span data-stu-id="5c5dd-138">Consumption depreciation</span></span>](consumption-depreciation.md)

[<span data-ttu-id="5c5dd-139">Ammortamento basato sulla vita utile rimanente a quote costanti</span><span class="sxs-lookup"><span data-stu-id="5c5dd-139">Straight line life remaining depreciation</span></span>](straight-line-life-remaining-depreciation.md)

[<span data-ttu-id="5c5dd-140">Riduzione del 125% dell'ammortamento del saldo</span><span class="sxs-lookup"><span data-stu-id="5c5dd-140">125 percent reducing balance depreciation</span></span>](125-percent-reducing-balance-depreciation.md)

[<span data-ttu-id="5c5dd-141">Riduzione del 150% dell'ammortamento del saldo</span><span class="sxs-lookup"><span data-stu-id="5c5dd-141">150 percent reducing balance depreciation</span></span>](150-percent-reducing-balance-depreciation.md)

[<span data-ttu-id="5c5dd-142">Riduzione del 175% dell'ammortamento del saldo</span><span class="sxs-lookup"><span data-stu-id="5c5dd-142">175 percent reducing balance depreciation</span></span>](175-percent-reducing-balance-depreciation.md)

[<span data-ttu-id="5c5dd-143">Riduzione del 200% dell'ammortamento del saldo</span><span class="sxs-lookup"><span data-stu-id="5c5dd-143">200 percent reducing balance depreciation</span></span>](200-percent-reducing-balance-depreciation.md)




