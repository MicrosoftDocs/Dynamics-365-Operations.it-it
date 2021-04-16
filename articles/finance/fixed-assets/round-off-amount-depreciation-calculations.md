---
title: Importo per l'arrotondamento dei calcoli di ammortamento
description: Questo articolo illustra il campo Arrotonda ammortamento presente nelle pagine Impostazione libro.
author: ShylaThompson
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetBookTable, AssetDepBookTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 13931
ms.assetid: faf7db87-046f-41d1-9baf-0df66e373e97
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0bf7cf68c98b14fb6c206c99673168153b32a449
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5830425"
---
# <a name="round-off-amount-for-depreciation-calculations"></a><span data-ttu-id="cc1b1-103">Importo per l'arrotondamento dei calcoli di ammortamento</span><span class="sxs-lookup"><span data-stu-id="cc1b1-103">Round-off amount for depreciation calculations</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="cc1b1-104">Questo articolo illustra il campo Arrotonda ammortamento presente nelle pagine Impostazione libro.</span><span class="sxs-lookup"><span data-stu-id="cc1b1-104">This article discusses the Round-off depreciation field that is found on the Book setup pages.</span></span>

<span data-ttu-id="cc1b1-105">Gli importi di arrotondamento per l'ammortamento vengono impostati per ogni libro.</span><span class="sxs-lookup"><span data-stu-id="cc1b1-105">Round-off depreciation amounts are set for each book.</span></span> <span data-ttu-id="cc1b1-106">Gli importi di arrotondamento per l'ammortamento vengono utilizzati nel profilo di ammortamento cespiti che mostra l'ammortamento e il valore futuri del cespite e anche nelle proposte di ammortamento.</span><span class="sxs-lookup"><span data-stu-id="cc1b1-106">Round-off depreciation amounts are used in the fixed asset depreciation profile that shows the future depreciation and value of the fixed asset, and also in depreciation proposals.</span></span> <span data-ttu-id="cc1b1-107">Immettere l'importo minimo dell'ammortamento consentito per il libro.</span><span class="sxs-lookup"><span data-stu-id="cc1b1-107">Enter the lowest depreciation amount that is allowed for the book.</span></span> 

<span data-ttu-id="cc1b1-108">Indipendentemente dall'arrotondamento che viene impostato, l'importo di ammortamento nell'ultimo periodo di ammortamento non viene arrotondato.</span><span class="sxs-lookup"><span data-stu-id="cc1b1-108">Regardless of the rounding that is set up, the depreciation amount in the last depreciation period isn't rounded.</span></span> <span data-ttu-id="cc1b1-109">Alla fine dell'ultimo periodo di ammortamento, il valore del cespite deve essere 0 (zero) o il valore di scarto, se il valore di scarto viene utilizzato.</span><span class="sxs-lookup"><span data-stu-id="cc1b1-109">At the end of the last depreciation period, the value of the fixed asset must be 0 (zero) or the scrap value, if scrap value is used.</span></span>

### <a name="example"></a><span data-ttu-id="cc1b1-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="cc1b1-110">Example</span></span>

<span data-ttu-id="cc1b1-111">L'ammortamento senza arrotondamento ammonta a 2.444,44.</span><span class="sxs-lookup"><span data-stu-id="cc1b1-111">Depreciation without rounding is calculated as 2,444.44.</span></span> <span data-ttu-id="cc1b1-112">Come indicato nella tabella seguente, gli importi suggeriti variano a seconda del modo in cui l'arrotondamento viene impostato.</span><span class="sxs-lookup"><span data-stu-id="cc1b1-112">As the following table shows, the amounts that are suggested vary, depending on how rounding is set up.</span></span>

| <span data-ttu-id="cc1b1-113">Metodo di arrotondamento</span><span class="sxs-lookup"><span data-stu-id="cc1b1-113">Rounding method</span></span> | <span data-ttu-id="cc1b1-114">Importo di ammortamento</span><span class="sxs-lookup"><span data-stu-id="cc1b1-114">Depreciation amount</span></span> |
|-----------------|---------------------|
| <span data-ttu-id="cc1b1-115">Arrotondamento 0,1</span><span class="sxs-lookup"><span data-stu-id="cc1b1-115">Rounding 0.1</span></span>    | <span data-ttu-id="cc1b1-116">2.444,40</span><span class="sxs-lookup"><span data-stu-id="cc1b1-116">2,444.40</span></span>            |
| <span data-ttu-id="cc1b1-117">Arrotondamento 1,00</span><span class="sxs-lookup"><span data-stu-id="cc1b1-117">Rounding 1.00</span></span>   | <span data-ttu-id="cc1b1-118">2.444,00</span><span class="sxs-lookup"><span data-stu-id="cc1b1-118">2,444.00</span></span>            |
| <span data-ttu-id="cc1b1-119">Arrotondamento 10,00</span><span class="sxs-lookup"><span data-stu-id="cc1b1-119">Rounding 10.00</span></span>  | <span data-ttu-id="cc1b1-120">2.440,00</span><span class="sxs-lookup"><span data-stu-id="cc1b1-120">2,440.00</span></span>            |
| <span data-ttu-id="cc1b1-121">Arrotondamento 100,00</span><span class="sxs-lookup"><span data-stu-id="cc1b1-121">Rounding 100.00</span></span> | <span data-ttu-id="cc1b1-122">2.400,00</span><span class="sxs-lookup"><span data-stu-id="cc1b1-122">2,400.00</span></span>            |







[!INCLUDE[footer-include](../../includes/footer-banner.md)]