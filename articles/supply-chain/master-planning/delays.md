---
title: Ritardi
description: Questo argomento fornisce informazioni sulle date ritardate nella pianificazione generale. Una data ritardata è una data di scadenza realistica che una transazione riceve se la prima data di evasione che la pianificazione generale calcola è successiva alla data richiesta.
author: roxanadiaconu
ms.date: 03/31/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqTransFuturesListPage
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19311
ms.assetid: 5ffb1486-2e08-4cdc-bd34-b47ae795ef0f
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4216ed1d9b981eee94cfd4c621abd1da99111512
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5813677"
---
# <a name="delays"></a><span data-ttu-id="3eb1c-104">Ritardi</span><span class="sxs-lookup"><span data-stu-id="3eb1c-104">Delays</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="3eb1c-105">Questo argomento fornisce informazioni sulle date ritardate nella pianificazione generale.</span><span class="sxs-lookup"><span data-stu-id="3eb1c-105">This topic provides information about delayed dates in master planning.</span></span> <span data-ttu-id="3eb1c-106">Una data ritardata è una data di scadenza realistica che una transazione riceve se la prima data di evasione che la pianificazione generale calcola è successiva alla data richiesta.</span><span class="sxs-lookup"><span data-stu-id="3eb1c-106">A delayed date is a realistic due date that a transaction receives if the earliest fulfillment date that master planning calculates is later than the requested date.</span></span>

<span data-ttu-id="3eb1c-107">La pianificazione generale può calcolare la prima data di evasione possibile per una transazione, in base ai lead time, alla disponibilità del materiale, alla disponibilità della capacità e a vari parametri di pianificazione.</span><span class="sxs-lookup"><span data-stu-id="3eb1c-107">Master planning can calculate the earliest fulfillment date for a transaction, based on lead times, material availability, capacity availability, and various planning parameters.</span></span> 

<span data-ttu-id="3eb1c-108">Se la pianificazione generale calcola una data dell'ordine che precede la data corrente, l'ordine non può essere evaso in tempo.</span><span class="sxs-lookup"><span data-stu-id="3eb1c-108">If master planning calculates an order date that precedes the current date, the order can't be fulfilled on time.</span></span> <span data-ttu-id="3eb1c-109">Di conseguenza, l'ordine viene ritardato.</span><span class="sxs-lookup"><span data-stu-id="3eb1c-109">Therefore, the order is delayed.</span></span> <span data-ttu-id="3eb1c-110">In questo caso, la pianificazione generale pianifica in anticipo l'ordine a partire dalla data corrente e include i lead time.</span><span class="sxs-lookup"><span data-stu-id="3eb1c-110">In this case, master planning forward-plans the order from the current date and includes lead times.</span></span> <span data-ttu-id="3eb1c-111">Questi lead time cominciano con qualsiasi articolo componente di livello inferiore.</span><span class="sxs-lookup"><span data-stu-id="3eb1c-111">These lead times start with any lower-level component items.</span></span> <span data-ttu-id="3eb1c-112">L'ordine riceve quindi una data ritardata.</span><span class="sxs-lookup"><span data-stu-id="3eb1c-112">The order then receives a delayed date.</span></span> <span data-ttu-id="3eb1c-113">Una data ritardata è una data di scadenza realistica basata sui dati correnti.</span><span class="sxs-lookup"><span data-stu-id="3eb1c-113">A delayed date is a realistic due date, based on the current data.</span></span> <span data-ttu-id="3eb1c-114">La pianificazione generale calcola anche il numero di giorni di ritardo.</span><span class="sxs-lookup"><span data-stu-id="3eb1c-114">Master planning also calculates the number of delay days.</span></span> 

<span data-ttu-id="3eb1c-115">In alcune situazioni, è possibile scegliere di non calcolare i ritardi, ad esempio quando gli utenti sanno che possono velocizzare i lead time selezionando modalità di consegna alternative.</span><span class="sxs-lookup"><span data-stu-id="3eb1c-115">In some situations, you might choose not to calculate delays, such as when users know that they can expedite lead times by selecting alternative modes of delivery.</span></span> 

<span data-ttu-id="3eb1c-116">È possibile configurare la modalità di calcolo dei ritardi per un gruppo di copertura.</span><span class="sxs-lookup"><span data-stu-id="3eb1c-116">You can configure how delays are calculated for a coverage group.</span></span> <span data-ttu-id="3eb1c-117">È quindi possibile collegare il gruppo di copertura a un articolo successivamente.</span><span class="sxs-lookup"><span data-stu-id="3eb1c-117">You can then attach the coverage group to an item later.</span></span> 

<span data-ttu-id="3eb1c-118">Nella pagina **Parametri di pianificazione generale**, è possibile impostare l'ora di inizio per il calcolo dei ritardi.</span><span class="sxs-lookup"><span data-stu-id="3eb1c-118">On the **Master planning parameters** page, you can set the start time for the calculation of delays.</span></span> <span data-ttu-id="3eb1c-119">Se un ordine viene evaso dopo questo orario, viene aggiunto un ritardo di un giorno alla data di ritardo dell'ordine.</span><span class="sxs-lookup"><span data-stu-id="3eb1c-119">If an order is fulfilled after this time, a delay of one day is added to the delay date of the order.</span></span> 

> [!NOTE]
> <span data-ttu-id="3eb1c-120">Nelle versioni precedenti, i ritardi calcolati erano denominati *messaggi di ritardo*, la data di ritardo era denominata *data ritardo* e una transazione ritardata era definita una *transazione impostata su una data futura*.</span><span class="sxs-lookup"><span data-stu-id="3eb1c-120">In earlier versions, calculated delays were known as *futures messages*, the delayed date was known as the *futures date*, and a delayed transaction was referred to as *a transaction that was future set*.</span></span>

## <a name="limited-delays-in-production-setup-with-multiple-bom-levels"></a><span data-ttu-id="3eb1c-121">Ritardi limitati nell'impostazione della produzione con più livelli DBA</span><span class="sxs-lookup"><span data-stu-id="3eb1c-121">Limited delays in production setup with multiple BOM levels</span></span>
<span data-ttu-id="3eb1c-122">Quando si lavora con ritardi in un'impostazione di produzione con più livelli DBA, è importante notare che solo gli articoli direttamente sopra l'articolo (nella struttura DBA) che causa il ritardo verranno aggiornati con un ritardo nell'ambito dell'esecuzione della pianificazione generale.</span><span class="sxs-lookup"><span data-stu-id="3eb1c-122">When you work with delays in a production setup that has multiple BOM levels, it is important to note that only the items directly above the item (in the BOM structure) causing the delay, will be updated with a delay as part of the master planning run.</span></span> <span data-ttu-id="3eb1c-123">Gli altri elementi nella struttura della DBA non vengono applicati al ritardo fino alla prima esecuzione della pianificazione generale, quando l'ordine pianificato per il livello superiore viene approvato o stabilizzato.</span><span class="sxs-lookup"><span data-stu-id="3eb1c-123">Other items in the BOM structure will not get the delay applied until the first master planning run, when the planned order for the top level is approved or firmed.</span></span> 

<span data-ttu-id="3eb1c-124">Per aggirare questa limitazione nota, gli ordini di produzione nella parte superiore della struttura DBA con ritardi possono essere approvati (o stabilizzati) prima della successiva esecuzione della pianificazione generale.</span><span class="sxs-lookup"><span data-stu-id="3eb1c-124">To work around this known limitation, the production orders on the top of the BOM structure with delays can be approved (or firmed) prior to the next master planning run.</span></span> <span data-ttu-id="3eb1c-125">In questo modo verrà mantenuto il ritardo dell'ordine di produzione pianificato ritardato approvato e tutti i componenti sottostanti verranno aggiornati di conseguenza.</span><span class="sxs-lookup"><span data-stu-id="3eb1c-125">This way the delay from the delayed approved planned production order will be kept and all underlying components will be updated accordingly.</span></span>
<span data-ttu-id="3eb1c-126">I messaggi di azione possono anche essere utilizzati per identificare gli ordini pianificati che possono essere spostati a una data successiva, a causa di altri ritardi nella struttura della DBA.</span><span class="sxs-lookup"><span data-stu-id="3eb1c-126">Action messages can also be used to identify planned orders that can be moved to a later date, due to other delays in the BOM structure.</span></span>

## <a name="desired-date"></a><span data-ttu-id="3eb1c-127">Data desiderata</span><span class="sxs-lookup"><span data-stu-id="3eb1c-127">Desired date</span></span>

<span data-ttu-id="3eb1c-128">Nella pagina **Ordine pianificato**, sotto la scheda **Ritardi** è visualizzata la **data desiderata** per l'ordine pianificato.</span><span class="sxs-lookup"><span data-stu-id="3eb1c-128">On the **Planned order** page, under the **Delays** tab is the **Desired date** for the planned order.</span></span> <span data-ttu-id="3eb1c-129">La data desiderata di un ordine pianificato è la data di base per i ritardi, ovvero una data calcolata uguale alla **data richiesta** calcolata a partire dal **fabbisogno netto**.</span><span class="sxs-lookup"><span data-stu-id="3eb1c-129">The desired date of a planned order is the base date for delays, which is a computed date that equals the **Requested date** calculated from the **Net Requirement**.</span></span> <span data-ttu-id="3eb1c-130">Se l'ordine pianificato è una riga DBA, una riga di produzione o una riga kanban, la data desiderata si basa sulla **data fabbisogno** e la data desiderata non verrà visualizzata nella pagina **Ordine pianificato**.</span><span class="sxs-lookup"><span data-stu-id="3eb1c-130">If the planned order is a BOM line, production line or kanban line, the desired date is based on the **Requirement date** and the desired date will not be shown on the **Planned order** page.</span></span>

<a name="additional-resources"></a><span data-ttu-id="3eb1c-131">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="3eb1c-131">Additional resources</span></span>
--------

[<span data-ttu-id="3eb1c-132">Impostazioni della copertura</span><span class="sxs-lookup"><span data-stu-id="3eb1c-132">Coverage settings</span></span>](coverage-settings.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]