---
title: Ubicazione uscita produzione
description: Questo argomento descrive la gerarchia utilizzata per identificare l'ubicazione uscita produzione.
author: johanhoffmann
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 221264
ms.assetid: dde49743-1541-4353-a030-63ca3069cd7d
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 08c38aada355583c5a6872f75b57db95d9b81786
ms.openlocfilehash: e53c8e96579dba3b47bef0c00e55b8fa786fc55c
ms.contentlocale: it-it
ms.lasthandoff: 07/27/2017

---

# <a name="production-output-location"></a><span data-ttu-id="c6e9d-103">Ubicazione uscita produzione</span><span class="sxs-lookup"><span data-stu-id="c6e9d-103">Production output location</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="c6e9d-104">Questo argomento descrive la gerarchia utilizzata per identificare l'ubicazione uscita produzione.</span><span class="sxs-lookup"><span data-stu-id="c6e9d-104">This topic describes the hierarchy that is used to identify the production output location.</span></span>

<span data-ttu-id="c6e9d-105">L'ubicazione uscita produzione è l'ubicazione in cui un prodotto viene immagazzinato dopo la produzione.</span><span class="sxs-lookup"><span data-stu-id="c6e9d-105">The production output location is the location where a finished good is first stored after it's produced.</span></span> <span data-ttu-id="c6e9d-106">In genere l'ubicazione si trova vicino al processo di produzione che realizza il prodotto finito.</span><span class="sxs-lookup"><span data-stu-id="c6e9d-106">Usually, this location is close to the production process that produces the finished good.</span></span> <span data-ttu-id="c6e9d-107">L'ubicazione uscita produzione viene utilizzata come magazzino intermedio per il materiale prima che venga spostato nell'area di spedizione, un'ubicazione di immagazzinamento, un'ubicazione entrata produzione per un processo di produzione a valle e così via.</span><span class="sxs-lookup"><span data-stu-id="c6e9d-107">The production output location is used as intermediate storage for the material before it's moved on to the shipment area, a storage location, a production input location for a downstream production process, and so on.</span></span> 

<span data-ttu-id="c6e9d-108">Un'ubicazione uscita produzione predefinita viene impostata quando i prodotti finiti vengono dichiarati in un ordine di produzione o un ordine batch.</span><span class="sxs-lookup"><span data-stu-id="c6e9d-108">A default production output location is set when finished goods are reported on a production order or batch order.</span></span> <span data-ttu-id="c6e9d-109">La gerarchia seguente viene utilizzata per identificare questa ubicazione uscita:</span><span class="sxs-lookup"><span data-stu-id="c6e9d-109">The following hierarchy is used to identify this output location:</span></span>

1. <span data-ttu-id="c6e9d-110">Utilizzare l'ubicazione uscita definita nell'intestazione dell'ordine di produzione o dell'ordine batch.</span><span class="sxs-lookup"><span data-stu-id="c6e9d-110">Use the output location that is defined on the production order or batch order header.</span></span>
2. <span data-ttu-id="c6e9d-111">Se non è presente alcuna ubicazione, utilizzare l'ubicazione uscita definita nella risorsa utilizzata dall'ultima operazione definita nel ciclo di lavorazione produzione.</span><span class="sxs-lookup"><span data-stu-id="c6e9d-111">If no location is found there, use the output location that is defined on the resource that is used by the last operation that is defined in the production route.</span></span>
3. <span data-ttu-id="c6e9d-112">Se non è presente alcuna ubicazione, utilizzare l'ubicazione uscita definita nel gruppo di risorse utilizzato dalla risorsa per l'ultima operazione definita nel ciclo di lavorazione produzione.</span><span class="sxs-lookup"><span data-stu-id="c6e9d-112">If no location is found there, use the output location that is defined on the resource group that is used by the resource for the last operation that is defined in the production route.</span></span>
4. <span data-ttu-id="c6e9d-113">Se non è presente alcuna ubicazione, utilizzare l'ubicazione uscita definita nel magazzino definito per l'ordine di produzione.</span><span class="sxs-lookup"><span data-stu-id="c6e9d-113">If no location is found there, use the output location that is defined on the warehouse that is defined for the production order.</span></span>

<span data-ttu-id="c6e9d-114">L'ubicazione uscita produzione predefinita viene impostata solo per i prodotti che vengono impostati utilizzando i processi di magazzino avanzati.</span><span class="sxs-lookup"><span data-stu-id="c6e9d-114">A default production output location is set only for products that are set up by using advanced warehouse processes.</span></span> <span data-ttu-id="c6e9d-115">Quando questo tipo di articolo viene dichiarato finito, viene creato il lavoro magazzino di tipo **Stoccaggio prodotti finiti** o **Stoccaggio co-prodotti e sottoprodotti**.</span><span class="sxs-lookup"><span data-stu-id="c6e9d-115">When this type of item is reported as finished, warehouse work of the **Finished goods put away** or **Co-product and by-product put away** type is created.</span></span> <span data-ttu-id="c6e9d-116">Questo tipo di lavoro utilizza l'ubicazione uscita produzione come ubicazione di prelievo.</span><span class="sxs-lookup"><span data-stu-id="c6e9d-116">This type of work uses the production output location as the pick location.</span></span> <span data-ttu-id="c6e9d-117">L'ubicazione di stoccaggio è determinata dalle direttive ubicazione.</span><span class="sxs-lookup"><span data-stu-id="c6e9d-117">The put-away location is determined by the location directives.</span></span>

