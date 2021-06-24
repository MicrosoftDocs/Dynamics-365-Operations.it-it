---
title: Restrizioni per le versioni di determinazione costi per i costi standard
description: In questo argomento vengono elencate le restrizioni che sia applicano a una versione di determinazione costi per i costi standard.
author: AndersGirke
ms.date: 01/17/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CostingVersion
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.industry: Manufacturing
ms.author: aevengir
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d9d828e2413a20c4e61d162a31d3c2ed2b18718b
ms.sourcegitcommit: ff09736563d3cd2bc74c7664edd1767b218401cb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2021
ms.locfileid: "6187676"
---
#  <a name="restrictions-on-costing-versions-for-standard-costs"></a><span data-ttu-id="f87a1-103">Restrizioni per le versioni di determinazione costi per i costi standard</span><span class="sxs-lookup"><span data-stu-id="f87a1-103">Restrictions on costing versions for standard costs</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f87a1-104">In questo argomento vengono elencate le restrizioni che sia applicano a una versione di determinazione costi per i costi standard.</span><span class="sxs-lookup"><span data-stu-id="f87a1-104">This topic describes the restrictions that apply to a costing version for standard costs.</span></span> 

<span data-ttu-id="f87a1-105">Le restrizioni seguenti aiutano a garantire la conformità ai principi di determinazione costi standard:</span><span class="sxs-lookup"><span data-stu-id="f87a1-105">The following restrictions help guarantee adherence to standard costing principles:</span></span>

-  <span data-ttu-id="f87a1-106">Le spese devono essere incluse nel costo di un articolo.</span><span class="sxs-lookup"><span data-stu-id="f87a1-106">Charges must be included in an item's cost.</span></span> <span data-ttu-id="f87a1-107">Nel caso di un articolo prodotto, rappresentano i costi costanti ammortizzati nelle informazioni sulla distinta base (DBA) e sul ciclo di lavorazione.</span><span class="sxs-lookup"><span data-stu-id="f87a1-107">The charges for a manufactured item represent the amortized constant costs in the bill of materials (BOM) and route information.</span></span> <span data-ttu-id="f87a1-108">Pertanto, questi addebiti devono essere inclusi nel costo unitario.</span><span class="sxs-lookup"><span data-stu-id="f87a1-108">Therefore, the charges must be included in the unit cost.</span></span> <span data-ttu-id="f87a1-109">Nel caso di un articolo acquistato, vengono incluse anche nel costo unitario dell'articolo.</span><span class="sxs-lookup"><span data-stu-id="f87a1-109">The charges for a purchased item are also included in the item's unit cost.</span></span>

-  <span data-ttu-id="f87a1-110">Il calcolo dei costi standard per un articolo prodotto deve basarsi sui record dei costi in una versione di determinazione costi per costi standard.</span><span class="sxs-lookup"><span data-stu-id="f87a1-110">Calculation of standard costs for manufactured items must be based on the cost records in a costing version for standard costs.</span></span> <span data-ttu-id="f87a1-111">È possibile utilizzare origini di dati di costo alternative solo con una versione di determinazione costi per costi pianificati, ad esempio accordi commerciali sui prezzi di acquisto per gli articoli acquistati.</span><span class="sxs-lookup"><span data-stu-id="f87a1-111">Alternative sources of cost data can be used only with a costing version for planned costs, such as purchase price trade agreements for purchased items.</span></span> <span data-ttu-id="f87a1-112">Le origini di dati di costo alternative vengono definite dal gruppo di calcolo DBA.</span><span class="sxs-lookup"><span data-stu-id="f87a1-112">Alternative sources of cost data are defined by the BOM calculation group.</span></span>

-  <span data-ttu-id="f87a1-113">I calcoli DBA devono essere eseguiti nella modalità di esplosione a livello singolo.</span><span class="sxs-lookup"><span data-stu-id="f87a1-113">BOM calculations must be performed in a single-level explosion mode.</span></span>

<span data-ttu-id="f87a1-114">I dati relativi al costo dell'articolo per i costi standard possono essere copiati in un'altra versione di determinazione costi contenente costi standard o pianificati.</span><span class="sxs-lookup"><span data-stu-id="f87a1-114">The item cost data for standard costs can be copied to another costing version that contains standard costs or planned costs.</span></span> <span data-ttu-id="f87a1-115">Tali dati per i costi pianificati tuttavia non potranno essere copiati in una versione di determinazione costi contenente costi standard, in quanto le restrizioni indicate in precedenza in questo argomento non sono applicabili ai costi pianificati.</span><span class="sxs-lookup"><span data-stu-id="f87a1-115">However, the item cost data for planned costs can't be copied to a cost version that contains standard costs, because the restrictions that are listed earlier in this topic don't apply to planned costs.</span></span>

## <a name="related-topics"></a><span data-ttu-id="f87a1-116">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="f87a1-116">Related topics</span></span>

[<span data-ttu-id="f87a1-117">Panoramica versioni di determinazione costi</span><span class="sxs-lookup"><span data-stu-id="f87a1-117">Costing versions overview</span></span>](costing-versions.md)

[<span data-ttu-id="f87a1-118">Aggiornare i costi standard in un ambiente non di produzione</span><span class="sxs-lookup"><span data-stu-id="f87a1-118">Update standard costs in a non-manufacturing environment</span></span>](update-standard-costs-non-manufacturing-environment.md)

[<span data-ttu-id="f87a1-119">Eseguire le operazioni preliminari alla gestione dei costi standard per gli articoli prodotti</span><span class="sxs-lookup"><span data-stu-id="f87a1-119">Prepare to maintain standard costs for manufactured items</span></span>](update-standard-costs-manufacturing-environment.md)



[!INCLUDE[footer-include](../../includes/footer-banner.md)]