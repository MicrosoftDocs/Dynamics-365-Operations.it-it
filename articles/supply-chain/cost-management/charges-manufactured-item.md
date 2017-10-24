---
title: Visualizzazione di spese per un articolo prodotto
description: "I costi costanti di un articolo prodotto riflettono i tempi di impostazione delle operazioni e i componenti con una quantità o un importo di scarto costante."
author: AndersGirke
manager: AnnBe
ms.date: 04/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CostingVersion, InventItemPrice
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 274483
ms.assetid: 6f5b851b-c5a7-43ef-b380-0d316667c1ef
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.dyn365.ops.intro: AX 7.0.0
ms.search.validFrom: 2016-02-28
ms.translationtype: HT
ms.sourcegitcommit: a61761a5c9d98befd67682e1790af5377b7a55e1
ms.openlocfilehash: f0ce01b21f62ee91c861b45e92f87b95be0476de
ms.contentlocale: it-it
ms.lasthandoff: 10/13/2017

---

# <a name="display-charges-for-a-manufactured-item"></a><span data-ttu-id="ef8a8-103">Visualizzazione di spese per un articolo prodotto</span><span class="sxs-lookup"><span data-stu-id="ef8a8-103">Display charges for a manufactured item</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="ef8a8-104">I costi costanti di un articolo prodotto riflettono i tempi di impostazione delle operazioni e i componenti con una quantità o un importo di scarto costante.</span><span class="sxs-lookup"><span data-stu-id="ef8a8-104">The constant costs of a manufactured item reflect the operation setup times and the components that have a constant quantity or a constant scrap amount.</span></span>

<span data-ttu-id="ef8a8-105">È possibile visualizzare l'importo calcolato delle spese di un articolo con i costi unitari dell'articolo.</span><span class="sxs-lookup"><span data-stu-id="ef8a8-105">The calculated amount of an item's charges can be displayed with the item's unit costs.</span></span> <span data-ttu-id="ef8a8-106">Tuttavia, le spese vengono talvolta visualizzate come due campi separati e non vengono incluse nei costi unitari dell'articolo.</span><span class="sxs-lookup"><span data-stu-id="ef8a8-106">However, the charges are sometimes displayed as separate fields, and they are not included in the item's unit costs.</span></span> <span data-ttu-id="ef8a8-107">Quando le spese vengono visualizzate come campi separati, un campo indica l'importo totale delle varie e l'altro le dimensioni lotto di determinazione costi utilizzate per ammortizzare l'importo.</span><span class="sxs-lookup"><span data-stu-id="ef8a8-107">When the charges appear as separate fields, one field displays the total amount of charges, and another field displays the costing lot size that is used to amortize the amount.</span></span> <span data-ttu-id="ef8a8-108">Nella Pagina Prezzo articolo, ad esempio, le spese vengono visualizzate come due campi separati.</span><span class="sxs-lookup"><span data-stu-id="ef8a8-108">The Item price page, for example, displays the charges as two separate fields.</span></span> <span data-ttu-id="ef8a8-109">Tuttavia, nella pagina Completo viene visualizzato il costo totale dell'articolo per unità e i costi ammortizzati vengono inclusi nei costi unitari.</span><span class="sxs-lookup"><span data-stu-id="ef8a8-109">However, the Complete page displays the item's total cost per unit, and the amortized costs are included in the unit costs.</span></span>

<span data-ttu-id="ef8a8-110">Le spese per un articolo prodotto vengono sempre incluse nel costo unitario dell'articolo ai fini dei costi standard,</span><span class="sxs-lookup"><span data-stu-id="ef8a8-110">The charges for a manufactured item are always included in the item's unit cost for standard cost purposes.</span></span> <span data-ttu-id="ef8a8-111">mentre possono essere incluse facoltativamente nel caso di costi pianificati.</span><span class="sxs-lookup"><span data-stu-id="ef8a8-111">They can optionally be included for planned cost purposes.</span></span> <span data-ttu-id="ef8a8-112">La decisione di includere le spese nel costo di un articolo prodotto viene applicata da criteri in una versione di determinazione costi.</span><span class="sxs-lookup"><span data-stu-id="ef8a8-112">A policy in the costing version enforces the inclusion of charges in the cost of a manufactured item.</span></span> <span data-ttu-id="ef8a8-113">Quando si attiva il record di costo di un articolo, le spese vengono aggiornate per le informazioni di costo di base dell'articolo visualizzate nella pagina Prezzo articolo.</span><span class="sxs-lookup"><span data-stu-id="ef8a8-113">When you activate an item's cost record, you update the charges for the item's base cost information, which is displayed in the Item price page.</span></span> <span data-ttu-id="ef8a8-114">Le spese vengono visualizzate come due campi separati e non vengono incluse nel costo unitario dell'articolo.</span><span class="sxs-lookup"><span data-stu-id="ef8a8-114">The charges are displayed as two separate fields, and they are not included in the item's unit cost.</span></span> <span data-ttu-id="ef8a8-115">Le informazioni di costo di base dell'articolo vengono aggiornate a ogni attivazione, anche se quest'ultima riguarda siti diversi.</span><span class="sxs-lookup"><span data-stu-id="ef8a8-115">Each activation updates the item's base cost information, even if the activation reflects different sites.</span></span> <span data-ttu-id="ef8a8-116">Tali informazioni devono pertanto essere considerate come informazioni di riferimento.</span><span class="sxs-lookup"><span data-stu-id="ef8a8-116">Therefore, you should view the base cost information as reference information.</span></span>






