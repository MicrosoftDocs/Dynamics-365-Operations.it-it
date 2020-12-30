---
title: ammortamento straordinario
description: Questo articolo fornisce una panoramica delle funzionalità di ammortamento straordinario.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetBonus
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 3621
ms.assetid: 835ec594-744e-461c-a676-1b9abc094173
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 687ba57042ad65d3a1ff4ad92f0da774c6751eac
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4444663"
---
# <a name="bonus-depreciation"></a><span data-ttu-id="54628-103">ammortamento straordinario</span><span class="sxs-lookup"><span data-stu-id="54628-103">Bonus depreciation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="54628-104">Questo articolo fornisce una panoramica delle funzionalità di ammortamento straordinario.</span><span class="sxs-lookup"><span data-stu-id="54628-104">This article provides an overview of the bonus depreciation functionality.</span></span>

<span data-ttu-id="54628-105">La funzionalità di ammortamento aggiuntivo consente di applicare importi di ammortamento straordinari durante il primo anno in cui il cespite viene messo in servizio e ammortizzato.</span><span class="sxs-lookup"><span data-stu-id="54628-105">For bonus depreciation, you can take extra or bonus depreciation amounts during the first year that the asset is put in service and depreciated.</span></span> <span data-ttu-id="54628-106">L'ammortamento aggiuntivo deve essere applicato prima di qualsiasi altro calcolo dell'ammortamento.</span><span class="sxs-lookup"><span data-stu-id="54628-106">Bonus depreciation must be taken before any other depreciation calculations.</span></span> <span data-ttu-id="54628-107">Di conseguenza, è preferibile utilizzare l'ammortamento straordinario con i libri in cui la funzionalità Registra nella contabilità generale è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="54628-107">Therefore, it's best to use bonus depreciation with books where the Post to general ledger functionality is disabled.</span></span> <span data-ttu-id="54628-108">È possibile utilizzare l'opzione **Elimina transazioni non registrate nella contabilità generale** per eliminare lo storico transazioni per i libri che non registrano nella contabilità generale.</span><span class="sxs-lookup"><span data-stu-id="54628-108">You can use the **Delete transactions not posted to general ledger** option to delete historical transactions for books that don't post to the general ledger.</span></span> <span data-ttu-id="54628-109">È quindi possibile inserire successivamente l'ammortamento aggiuntivo nel ciclo di vita del cespite eliminando le transazioni di ammortamento precedentemente registrate.</span><span class="sxs-lookup"><span data-stu-id="54628-109">You can then accommodate bonus depreciation later in the asset life cycle by deleting depreciation transactions that were previously posted.</span></span> 

<span data-ttu-id="54628-110">È possibile calcolare l'ammortamento aggiuntivo utilizzando il processo di proposta o creando transazioni di ammortamento aggiuntivo manuali.</span><span class="sxs-lookup"><span data-stu-id="54628-110">You can calculate bonus depreciation by using the proposal process, or you can create manual bonus depreciation transactions.</span></span> <span data-ttu-id="54628-111">Non è possibile creare transazioni di ammortamento straordinario se per un determinato libro cespiti sono presenti transazioni di ammortamento o transazioni di rettifica ammortamento.</span><span class="sxs-lookup"><span data-stu-id="54628-111">You can't create bonus depreciation transactions if depreciation transactions or depreciation adjustment transactions exist for that asset book.</span></span>

<span data-ttu-id="54628-112">Quando si utilizza il processo di proposta per calcolare l'ammortamento aggiuntivo, tutte le transazioni di ammortamento aggiuntivo esistenti saranno incluse nel calcolo della base,</span><span class="sxs-lookup"><span data-stu-id="54628-112">When you use the proposal process to calculate bonus depreciation, all existing bonus transactions are included in the calculation of the basis.</span></span> <span data-ttu-id="54628-113">compresi eventuali ammortamenti aggiuntivi precedenti immessi manualmente per il cespite.</span><span class="sxs-lookup"><span data-stu-id="54628-113">The calculation also includes any previous bonus depreciations that you manually entered for the asset.</span></span> 

<span data-ttu-id="54628-114">La priorità viene considerata quando è necessario applicare più ammortamenti straordinari per un singolo cespite.</span><span class="sxs-lookup"><span data-stu-id="54628-114">If more than one bonus depreciation will be taken for an asset, the priority is considered.</span></span> <span data-ttu-id="54628-115">Ciascun ammortamento aggiuntivo contribuisce alla riduzione della base di ammortamento del cespite per il successivo ammortamento aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="54628-115">Each bonus reduces the asset basis for the next bonus.</span></span> <span data-ttu-id="54628-116">Il valore di realizzo non viene considerato nella base di ammortamento per i calcoli di ammortamento straordinario e la convenzione di ammortamento non viene applicata per questo tipo di ammortamento.</span><span class="sxs-lookup"><span data-stu-id="54628-116">Salvage value isn't considered in the asset basis for bonus depreciation calculations, and the depreciation convention doesn't apply for bonus depreciation.</span></span> 

<span data-ttu-id="54628-117">Attualmente negli Stati Uniti alcune proprietà sono classificate come proprietà regolamentate dalla sezione 179.</span><span class="sxs-lookup"><span data-stu-id="54628-117">Currently, in the United States, some property qualifies as Section 179 property.</span></span> <span data-ttu-id="54628-118">Per sezione 179 si intende la facoltà di recuperare totalmente o parzialmente il costo di determinate proprietà, fino a un certo limite,</span><span class="sxs-lookup"><span data-stu-id="54628-118">By using the Section 179 deduction, you can recover all or part of the cost of some property, up to a limit.</span></span> <span data-ttu-id="54628-119">detraendo tale costo nell'anno in cui la proprietà viene messa in servizio.</span><span class="sxs-lookup"><span data-stu-id="54628-119">You can recover the cost by deducting it in the year when you put the property in service.</span></span>

## <a name="example"></a><span data-ttu-id="54628-120">Esempio</span><span class="sxs-lookup"><span data-stu-id="54628-120">Example</span></span>
<span data-ttu-id="54628-121">Si supponga che i seguenti ammortamenti aggiuntivi siano associati a un libro cespiti:</span><span class="sxs-lookup"><span data-stu-id="54628-121">The following bonus depreciations are associated with an asset book:</span></span>

-   <span data-ttu-id="54628-122">**Sezione 179:** 1.000,00, priorità 1</span><span class="sxs-lookup"><span data-stu-id="54628-122">**Section 179:** 1,000.00, Priority 1</span></span>
-   <span data-ttu-id="54628-123">**Zona A:** 30%, priorità 2</span><span class="sxs-lookup"><span data-stu-id="54628-123">**Liberty Zone:** 30 percent, Priority 2</span></span>

<span data-ttu-id="54628-124">Il costo dell'acquisizione cespiti è di 5.000.</span><span class="sxs-lookup"><span data-stu-id="54628-124">The asset acquisition cost is 5,000.00.</span></span> <span data-ttu-id="54628-125">Quando viene calcolato l'ammortamento aggiuntivo, il primo importo sarà di 1.000 per l'ammortamento come da sezione 179.</span><span class="sxs-lookup"><span data-stu-id="54628-125">When bonus depreciation is calculated, the first bonus depreciation amount is 1,000.00 for the Section 179 depreciation.</span></span> 

<span data-ttu-id="54628-126">Il successivo importo di ammortamento aggiuntivo, per l'ammortamento relativo alla Zona A, viene calcolato come segue:</span><span class="sxs-lookup"><span data-stu-id="54628-126">The next bonus depreciation amount, for the Liberty Zone depreciation, is calculated as follows:</span></span> 

<span data-ttu-id="54628-127">Costo di acquisizione: 1.000 (ammortamento come da sezione 179) x 30% = 1.200</span><span class="sxs-lookup"><span data-stu-id="54628-127">Acquisition cost – 1,000 (Section 179 depreciation) × 30 percent = 1,200</span></span> 

<span data-ttu-id="54628-128">Se l'importo di ammortamento aggiuntivo è maggiore del costo di acquisizione rimanente, tale importo corrisponderà al calcolo dell'ammortamento aggiuntivo o al costo di acquisizione rimanente, a seconda dell'importo inferiore.</span><span class="sxs-lookup"><span data-stu-id="54628-128">If the bonus depreciation amount is more than the remaining acquisition cost, the bonus depreciation amount is either the result of the bonus depreciation calculation or the remaining acquisition cost, whichever amount is less.</span></span> 

<span data-ttu-id="54628-129">Se il costo di acquisizione rimanente è uguale o inferiore a 0 (zero), non verranno generate transazioni di ammortamento aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="54628-129">If the remaining acquisition cost is 0 (zero) or less, bonus depreciation transactions isn't generated.</span></span> 

<span data-ttu-id="54628-130">Quando l'ammortamento aggiuntivo viene calcolato mediante il processo di proposta, verrà creata una transazione di ammortamento aggiuntivo per tutti i record di ammortamento aggiuntivo applicabili associati al libro cespiti.</span><span class="sxs-lookup"><span data-stu-id="54628-130">When bonus depreciation is calculated by using the proposal process, a bonus depreciation transaction is created for all applicable bonus depreciation records that are associated with the asset book.</span></span> 

<span data-ttu-id="54628-131">È possibile creare un numero illimitato di record di ammortamento aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="54628-131">You can create an unlimited number of bonus depreciation records.</span></span> <span data-ttu-id="54628-132">Una volta assegnati tali record al libro gruppo cespite, questi record vengono applicati al libro cespiti.</span><span class="sxs-lookup"><span data-stu-id="54628-132">After you assign those records to the asset group book, they are applied to the asset book.</span></span> 

<span data-ttu-id="54628-133">L'ammortamento aggiuntivo viene immesso sotto forma di percentuale o di importo fisso.</span><span class="sxs-lookup"><span data-stu-id="54628-133">Bonus depreciation is entered as either a percentage or a fixed amount.</span></span> <span data-ttu-id="54628-134">Quando si registrano le proposte di ammortamento, le transazioni relative a questo tipo di ammortamento vengono registrate nel libro come transazioni distinte dalle altre.</span><span class="sxs-lookup"><span data-stu-id="54628-134">When you post depreciation proposals, bonus depreciation transactions are posted to the book as separate transactions from the depreciation transactions.</span></span>



