---
title: Ammortizzare i costi costanti per un articolo prodotto
description: "I costi costanti di un articolo prodotto riflettono i tempi di impostazione delle operazioni e i componenti con una quantità o un importo di scarto costante."
author: AndersGirke
manager: AnnBe
ms.date: 04/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BOMCalcDialog, BOMCalcTable, BOMCalcTrans
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 274503
ms.assetid: 535ab25d-a031-4e8c-84ec-478f2987a1ad
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: aevengir
ms.dyn365.ops.version: AX 7.0.0
ms.search.validFrom: 2016-02-28
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 2e9d15e35661d37036af48d4d1183e4f25012e57
ms.contentlocale: it-it
ms.lasthandoff: 04/13/2018

---

# <a name="amortize-constant-costs-for-a-manufactured-item"></a><span data-ttu-id="fb5a0-103">Ammortizzare i costi costanti per un articolo prodotto</span><span class="sxs-lookup"><span data-stu-id="fb5a0-103">Amortize constant costs for a manufactured item</span></span>

[!INCLUDE [banner](../includes/banner.md)]

<span data-ttu-id="fb5a0-104">I costi costanti di un articolo prodotto riflettono i tempi di impostazione delle operazioni e i componenti con una quantità o un importo di scarto costante.</span><span class="sxs-lookup"><span data-stu-id="fb5a0-104">A manufactured item’s constant costs reflect the operation setup times and the components that have a constant quantity or a constant scrap amount.</span></span> 

<span data-ttu-id="fb5a0-105">Il concetto di dimensioni lotto per determinazione dei costi viene utilizzato per ammortizzare questi costi costanti nel costo calcolato di un articolo prodotto.</span><span class="sxs-lookup"><span data-stu-id="fb5a0-105">The concept of a costing lot size is used to amortize these constant costs in the calculated cost of a manufactured item.</span></span> <span data-ttu-id="fb5a0-106">Questo concetto può avere diversi sinonimi, tra cui dimensioni lotto per contabilità.</span><span class="sxs-lookup"><span data-stu-id="fb5a0-106">This concept has several synonyms, one of which is accounting lot size.</span></span> <span data-ttu-id="fb5a0-107">Anche il concetto di costi costanti di ammortamento può avere diversi sinonimi, tra cui costi costanti proporzionali.</span><span class="sxs-lookup"><span data-stu-id="fb5a0-107">The concept of amortizing constant costs also has several synonyms, one of which is proportional constant costs.</span></span>

<span data-ttu-id="fb5a0-108">La quantità di dimensioni lotto per determinazione dei costi per un articolo prodotto viene utilizzata nel calcolo DBA.</span><span class="sxs-lookup"><span data-stu-id="fb5a0-108">The quantity of a costing lot size for a manufactured item is used in a bill of material (BOM) calculation.</span></span> <span data-ttu-id="fb5a0-109">La quantità dipende dalla modalità di avvio ed esecuzione del calcolo DBA, come illustrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="fb5a0-109">The quantity depends on how you initiate and perform the BOM calculation, as illustrated by the following:</span></span>

-   <span data-ttu-id="fb5a0-110">Quantità di calcolo predefinita nel calcolo DBA di un articolo: la quantità ordine standard di un articolo per il magazzino funge da dimensioni lotto per determinazione dei costi, ma il valore predefinito potrebbe essere di una quantità maggiore che riflette il multiplo della quantità dell'ordine dell'articolo.</span><span class="sxs-lookup"><span data-stu-id="fb5a0-110">Default calculation quantity in an item’s BOM calculation − The item’s standard order quantity for inventory acts as the costing lot size, but the default value might be a greater quantity to reflect the item’s order quantity multiple.</span></span> <span data-ttu-id="fb5a0-111">La quantità dell'ordine standard dell'articolo e il multiplo possono essere definiti all'interno delle impostazioni di ordine predefinite o delle impostazioni di ordine specifiche del sito.</span><span class="sxs-lookup"><span data-stu-id="fb5a0-111">The item’s standard order quantity and multiple can be defined within its default order settings or site-specific order settings.</span></span>
-   <span data-ttu-id="fb5a0-112">Quantità di calcolo specificata nel calcolo DBA di un articolo: la quantità di calcolo specificata funge da dimensioni lotto per determinazione dei costi per l'articolo.</span><span class="sxs-lookup"><span data-stu-id="fb5a0-112">Specified calculation quantity in an item’s BOM calculation − The specified calculation quantity acts as the costing lot size for the item.</span></span> <span data-ttu-id="fb5a0-113">La quantità di calcolo utilizza inizialmente la quantità ordine standard dell'articolo, ma il valore predefinito può essere sostituito manualmente.</span><span class="sxs-lookup"><span data-stu-id="fb5a0-113">The calculation quantity initially uses the item’s standard order quantity, but the default value can be manually overridden.</span></span> <span data-ttu-id="fb5a0-114">La quantità di calcolo specificata rappresenta le dimensioni lotto per determinazione dei costi per l'articolo specificato e per i componenti prodotti con un tipo di riga DBA di produzione,</span><span class="sxs-lookup"><span data-stu-id="fb5a0-114">The specified calculation quantity represents the costing lot size for the specified item, and for manufactured components that have a BOM line type of production.</span></span> <span data-ttu-id="fb5a0-115">in quanto si presume che il componente verrà prodotto nella quantità esatta.</span><span class="sxs-lookup"><span data-stu-id="fb5a0-115">This is because it is assumed that the component will be produced to the exact quantity.</span></span> <span data-ttu-id="fb5a0-116">Le dimensioni lotto per determinazione dei costi per altri componenti prodotti con un tipo di riga DBA di articolo corrisponderanno alla quantità ordine standard.</span><span class="sxs-lookup"><span data-stu-id="fb5a0-116">The costing lot size for other manufactured components that have a BOM line type of item will reflect their standard order quantity.</span></span>
-   <span data-ttu-id="fb5a0-117">Quantità di calcolo Produzione su ordine specificata nel calcolo DBA di un articolo: la quantità di calcolo specificata funge da dimensioni lotto per determinazione dei costi per l'articolo e i relativi componenti prodotti quando i calcoli DBA utilizzano come modalità di esplosione Produzione su ordine.</span><span class="sxs-lookup"><span data-stu-id="fb5a0-117">Specified make-to-order calculation quantity in an item’s BOM calculation − The specified calculation quantity acts as the costing lot size for the item and its manufactured components when BOM calculations use a make-to-order explosion mode.</span></span> <span data-ttu-id="fb5a0-118">Si presume che i componenti fabbricati verranno prodotti nella quantità esatta, proprio come un componente fabbricato con un tipo di riga DBA di produzione.</span><span class="sxs-lookup"><span data-stu-id="fb5a0-118">It is assumed that the manufactured components will be produced to the exact quantity, just like a manufactured component that has a BOM line type of production.</span></span>
-   <span data-ttu-id="fb5a0-119">Quantità di calcolo in un calcolo DBA specifico dell'ordine: un calcolo DBA specifico dell'ordine può essere eseguito per una voce su un ordine cliente, un'offerta di vendita o un ordine di assistenza.</span><span class="sxs-lookup"><span data-stu-id="fb5a0-119">Specified calculation quantity in an order-specific BOM calculation − An order-specific BOM calculation can be performed for a line item on a sales order, sales quotation, or service order.</span></span> <span data-ttu-id="fb5a0-120">La quantità di calcolo specificata utilizza la quantità riportata nella voce di origine, ma la quantità predefinita può essere sovrascritta.</span><span class="sxs-lookup"><span data-stu-id="fb5a0-120">The specified calculation quantity uses the quantity on the originating line item, but the default quantity can be overridden.</span></span> <span data-ttu-id="fb5a0-121">È possibile scegliere se il calcolo DBA specifico dell'ordine debba utilizzare una modalità di esplosione Produzione su ordine o multilivello.</span><span class="sxs-lookup"><span data-stu-id="fb5a0-121">You can select whether the order-specific BOM calculation uses a make-to-order or multilevel explosion mode.</span></span>

<span data-ttu-id="fb5a0-122">L'importo calcolato dei costi costanti ammortizzati di un articolo prodotto viene indicato con il termine spese.</span><span class="sxs-lookup"><span data-stu-id="fb5a0-122">The calculated amount of a manufactured item’s amortized constant costs is termed charges.</span></span>






