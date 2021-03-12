---
title: Metodi e convenzioni di ammortamento
description: Questo articolo fornisce una panoramica delle convenzioni e dei metodi di ammortamento che sono supportati da Microsoft Dynamics 365 Finance.
author: ShylaThompson
manager: AnnBe
ms.date: 04/25/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetDepreciationProfile, AssetGroupBookSetup, AssetGroupDepBookSetup
audience: Application User
ms.reviewer: roschlom
ms.custom: 3441
ms.assetid: 1d8267b1-86a8-44bf-8814-f56b5d45a0ae
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: af1c1a222981a0bcf9d7341cde5b83dd720da802
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4994967"
---
# <a name="depreciation-methods-and-conventions"></a><span data-ttu-id="8ebc5-103">Metodi e convenzioni di ammortamento</span><span class="sxs-lookup"><span data-stu-id="8ebc5-103">Depreciation methods and conventions</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="8ebc5-104">Questo articolo fornisce una panoramica delle convenzioni e dei metodi di ammortamento supportati.</span><span class="sxs-lookup"><span data-stu-id="8ebc5-104">This article provides an overview of the supported depreciation conventions and depreciation methods.</span></span>

<span data-ttu-id="8ebc5-105">È possibile selezionare diversi metodi e convenzioni di ammortamento.</span><span class="sxs-lookup"><span data-stu-id="8ebc5-105">You can select various depreciation methods and conventions.</span></span> <span data-ttu-id="8ebc5-106">Scopo dei metodi è l'allocazione del valore ammortizzabile del cespite ai periodi fiscali.</span><span class="sxs-lookup"><span data-stu-id="8ebc5-106">The purpose of the methods is to allocate the depreciable value of the fixed asset into fiscal periods.</span></span> <span data-ttu-id="8ebc5-107">Tale valore corrisponde al prezzo di acquisizione da cui viene dedotto un valore di scarto, se presente.</span><span class="sxs-lookup"><span data-stu-id="8ebc5-107">The depreciable value of the fixed asset is the acquisition price, reduced by a scrap value, if any.</span></span> 

<span data-ttu-id="8ebc5-108">Se si utilizzano le convenzioni di ammortamento e si modifica la data di esecuzione dell'ultimo ammortamento di un cespite, determinando l'annullamento di alcuni ammortamenti, l'ammortamento relativo all'ultimo anno può risultare maggiore o minore del previsto.</span><span class="sxs-lookup"><span data-stu-id="8ebc5-108">If you are using depreciation conventions and you modify the last depreciation run date for an asset, which then causes some depreciations to be skipped, the depreciation for the last year might be more than or less than is expected.</span></span> <span data-ttu-id="8ebc5-109">L'ammortamento viene rettificato in base al numero di periodi di ammortamento interessati dalla modifica della data di esecuzione dell'ultimo ammortamento.</span><span class="sxs-lookup"><span data-stu-id="8ebc5-109">The depreciation is adjusted by the number of depreciation periods affected by the modification of the last depreciation run date.</span></span>

<span data-ttu-id="8ebc5-110">Ad esempio, se si utilizza la convenzione di ammortamento semestrale su tre anni, l'ammortamento viene in genere eseguito su 3 anni e mezzo.</span><span class="sxs-lookup"><span data-stu-id="8ebc5-110">For example, if you are using the Half year depreciation convention over three years, depreciation ordinarily occurs over 3 1/2 years.</span></span> <span data-ttu-id="8ebc5-111">Se durante questo intervallo di tempo la data di esecuzione dell'ultimo ammortamento viene modificata, il numero di periodi interessati nell'ultimo anno di ammortamento viene esteso.</span><span class="sxs-lookup"><span data-stu-id="8ebc5-111">If you change the last depreciation run date during the 3 1/2 years, the last year of depreciation moves out the number of periods affected.</span></span> <span data-ttu-id="8ebc5-112">Se si sposta la data di tre mesi, nell'ultimo anno verranno considerati nove mesi di ammortamento, mentre normalmente dovrebbero essere solo sei.</span><span class="sxs-lookup"><span data-stu-id="8ebc5-112">If you move the date by three months, the last year will have nine months’ worth of depreciation, when ordinarily there would be six months’ worth of depreciation.</span></span>

<span data-ttu-id="8ebc5-113">È possibile selezionare una delle convenzioni di ammortamento riportate di seguito.</span><span class="sxs-lookup"><span data-stu-id="8ebc5-113">You can select from the following depreciation conventions.</span></span>


-   <span data-ttu-id="8ebc5-114">Semestre</span><span class="sxs-lookup"><span data-stu-id="8ebc5-114">Half year</span></span>
-   <span data-ttu-id="8ebc5-115">Mese intero</span><span class="sxs-lookup"><span data-stu-id="8ebc5-115">Full month</span></span>
-   <span data-ttu-id="8ebc5-116">Metà trimestre</span><span class="sxs-lookup"><span data-stu-id="8ebc5-116">Mid quarter</span></span>
-   <span data-ttu-id="8ebc5-117">Metà mese (giorno 1 del mese)</span><span class="sxs-lookup"><span data-stu-id="8ebc5-117">Mid month (1st of month)</span></span>
-   <span data-ttu-id="8ebc5-118">Metà mese (giorno 15 del mese)</span><span class="sxs-lookup"><span data-stu-id="8ebc5-118">Mid month (15th of month)</span></span>
-   <span data-ttu-id="8ebc5-119">Semestre (inizio anno)</span><span class="sxs-lookup"><span data-stu-id="8ebc5-119">Half year (start of year)</span></span>
-   <span data-ttu-id="8ebc5-120">Semestre (prossimo anno)</span><span class="sxs-lookup"><span data-stu-id="8ebc5-120">Half year (next year)</span></span>

<span data-ttu-id="8ebc5-121">È possibile selezionare uno dei metodi di ammortamento riportate di seguito.</span><span class="sxs-lookup"><span data-stu-id="8ebc5-121">You can select from the following depreciation methods.</span></span>
-   <span data-ttu-id="8ebc5-122">Vita utile a quote costanti</span><span class="sxs-lookup"><span data-stu-id="8ebc5-122">Straight line service life</span></span>
-   <span data-ttu-id="8ebc5-123">A saldi decrescenti</span><span class="sxs-lookup"><span data-stu-id="8ebc5-123">Reducing balance</span></span>
-   <span data-ttu-id="8ebc5-124">Manuale</span><span class="sxs-lookup"><span data-stu-id="8ebc5-124">Manual</span></span>
-   <span data-ttu-id="8ebc5-125">Fattore</span><span class="sxs-lookup"><span data-stu-id="8ebc5-125">Factor</span></span>
-   <span data-ttu-id="8ebc5-126">Consumo</span><span class="sxs-lookup"><span data-stu-id="8ebc5-126">Consumption</span></span>
-   <span data-ttu-id="8ebc5-127">Vita utile rimanente a quote costanti</span><span class="sxs-lookup"><span data-stu-id="8ebc5-127">Straight line life remaining</span></span>
-   <span data-ttu-id="8ebc5-128">Saldo decrescente 200%</span><span class="sxs-lookup"><span data-stu-id="8ebc5-128">200% reducing balance</span></span>
-   <span data-ttu-id="8ebc5-129">Saldo decrescente 175%</span><span class="sxs-lookup"><span data-stu-id="8ebc5-129">175% reducing balance</span></span>
-   <span data-ttu-id="8ebc5-130">Saldo decrescente 150%</span><span class="sxs-lookup"><span data-stu-id="8ebc5-130">150% reducing balance</span></span>
-   <span data-ttu-id="8ebc5-131">Saldo decrescente 125%</span><span class="sxs-lookup"><span data-stu-id="8ebc5-131">125% reducing balance</span></span>





<a name="additional-resources"></a><span data-ttu-id="8ebc5-132">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="8ebc5-132">Additional resources</span></span>
--------

[<span data-ttu-id="8ebc5-133">Ammortamento dei cespiti</span><span class="sxs-lookup"><span data-stu-id="8ebc5-133">Fixed asset depreciation</span></span>](fixed-asset-depreciation.md)

[<span data-ttu-id="8ebc5-134">Ammortamento a quote costanti basato sulla vita utile</span><span class="sxs-lookup"><span data-stu-id="8ebc5-134">Straight line service life depreciation</span></span>](Straight-line-service-life-depreciation.md)

[<span data-ttu-id="8ebc5-135">Ammortamento a saldi decrescenti</span><span class="sxs-lookup"><span data-stu-id="8ebc5-135">Reduce balance depreciation</span></span>](reduce-balance-depreciation.md)

[<span data-ttu-id="8ebc5-136">Ammortamento manuale</span><span class="sxs-lookup"><span data-stu-id="8ebc5-136">Manual depreciation</span></span>](manual-depreciation.md)

[<span data-ttu-id="8ebc5-137">Ammortamento basato su coefficiente</span><span class="sxs-lookup"><span data-stu-id="8ebc5-137">Factor depreciation</span></span>](factor-depreciation.md)

[<span data-ttu-id="8ebc5-138">Ammortamento del consumo</span><span class="sxs-lookup"><span data-stu-id="8ebc5-138">Consumption depreciation</span></span>](consumption-depreciation.md)

[<span data-ttu-id="8ebc5-139">Ammortamento basato sulla vita utile rimanente a quote costanti</span><span class="sxs-lookup"><span data-stu-id="8ebc5-139">Straight line life remaining depreciation</span></span>](straight-line-life-remaining-depreciation.md)

[<span data-ttu-id="8ebc5-140">Riduzione del 125% dell'ammortamento del saldo</span><span class="sxs-lookup"><span data-stu-id="8ebc5-140">125 percent reducing balance depreciation</span></span>](125-percent-reducing-balance-depreciation.md)

[<span data-ttu-id="8ebc5-141">Riduzione del 150% dell'ammortamento del saldo</span><span class="sxs-lookup"><span data-stu-id="8ebc5-141">150 percent reducing balance depreciation</span></span>](150-percent-reducing-balance-depreciation.md)

[<span data-ttu-id="8ebc5-142">Riduzione del 175% dell'ammortamento del saldo</span><span class="sxs-lookup"><span data-stu-id="8ebc5-142">175 percent reducing balance depreciation</span></span>](175-percent-reducing-balance-depreciation.md)

[<span data-ttu-id="8ebc5-143">Riduzione del 200% dell'ammortamento del saldo</span><span class="sxs-lookup"><span data-stu-id="8ebc5-143">200 percent reducing balance depreciation</span></span>](200-percent-reducing-balance-depreciation.md)



