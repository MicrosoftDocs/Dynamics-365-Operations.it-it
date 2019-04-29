---
title: Ritardi
description: Questo argomento fornisce informazioni sulle date ritardate nella pianificazione generale. Una data ritardata è una data di scadenza realistica che una transazione riceve se la prima data di evasione che la pianificazione generale calcola è successiva alla data richiesta.
author: roxanadiaconu
manager: AnnBe
ms.date: 03/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqTransFuturesListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 19311
ms.assetid: 5ffb1486-2e08-4cdc-bd34-b47ae795ef0f
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7c26fedf15118a304469604527c33a25871356be
ms.sourcegitcommit: 8eac5eee94bb32143df44c82a2dfdbe903967af8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/20/2019
ms.locfileid: "878312"
---
# <a name="delays"></a><span data-ttu-id="21b5a-104">Ritardi</span><span class="sxs-lookup"><span data-stu-id="21b5a-104">Delays</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="21b5a-105">Questo argomento fornisce informazioni sulle date ritardate nella pianificazione generale.</span><span class="sxs-lookup"><span data-stu-id="21b5a-105">This topic provides information about delayed dates in master planning.</span></span> <span data-ttu-id="21b5a-106">Una data ritardata è una data di scadenza realistica che una transazione riceve se la prima data di evasione che la pianificazione generale calcola è successiva alla data richiesta.</span><span class="sxs-lookup"><span data-stu-id="21b5a-106">A delayed date is a realistic due date that a transaction receives if the earliest fulfillment date that master planning calculates is later than the requested date.</span></span>

<span data-ttu-id="21b5a-107">La pianificazione generale può calcolare la prima data di evasione possibile per una transazione, in base ai lead time, alla disponibilità del materiale, alla disponibilità della capacità e a vari parametri di pianificazione.</span><span class="sxs-lookup"><span data-stu-id="21b5a-107">Master planning can calculate the earliest fulfillment date for a transaction, based on lead times, material availability, capacity availability, and various planning parameters.</span></span> 

<span data-ttu-id="21b5a-108">Se la pianificazione generale calcola una data dell'ordine che precede la data corrente, l'ordine non può essere evaso in tempo.</span><span class="sxs-lookup"><span data-stu-id="21b5a-108">If master planning calculates an order date that precedes the current date, the order can't be fulfilled on time.</span></span> <span data-ttu-id="21b5a-109">Di conseguenza, l'ordine viene ritardato.</span><span class="sxs-lookup"><span data-stu-id="21b5a-109">Therefore, the order is delayed.</span></span> <span data-ttu-id="21b5a-110">In questo caso, la pianificazione generale pianifica in anticipo l'ordine a partire dalla data corrente e include i lead time.</span><span class="sxs-lookup"><span data-stu-id="21b5a-110">In this case, master planning forward-plans the order from the current date and includes lead times.</span></span> <span data-ttu-id="21b5a-111">Questi lead time cominciano con qualsiasi articolo componente di livello inferiore.</span><span class="sxs-lookup"><span data-stu-id="21b5a-111">These lead times start with any lower-level component items.</span></span> <span data-ttu-id="21b5a-112">L'ordine riceve quindi una data ritardata.</span><span class="sxs-lookup"><span data-stu-id="21b5a-112">The order then receives a delayed date.</span></span> <span data-ttu-id="21b5a-113">Una data ritardata è una data di scadenza realistica basata sui dati correnti.</span><span class="sxs-lookup"><span data-stu-id="21b5a-113">A delayed date is a realistic due date, based on the current data.</span></span> <span data-ttu-id="21b5a-114">La pianificazione generale calcola anche il numero di giorni di ritardo.</span><span class="sxs-lookup"><span data-stu-id="21b5a-114">Master planning also calculates the number of delay days.</span></span> 

<span data-ttu-id="21b5a-115">In alcune situazioni, è possibile scegliere di non calcolare i ritardi, ad esempio quando gli utenti sanno che possono velocizzare i lead time selezionando modalità di consegna alternative.</span><span class="sxs-lookup"><span data-stu-id="21b5a-115">In some situations, you might choose not to calculate delays, such as when users know that they can expedite lead times by selecting alternative modes of delivery.</span></span> 

<span data-ttu-id="21b5a-116">È possibile configurare la modalità di calcolo dei ritardi per un gruppo di copertura.</span><span class="sxs-lookup"><span data-stu-id="21b5a-116">You can configure how delays are calculated for a coverage group.</span></span> <span data-ttu-id="21b5a-117">È quindi possibile collegare il gruppo di copertura a un articolo successivamente.</span><span class="sxs-lookup"><span data-stu-id="21b5a-117">You can then attach the coverage group to an item later.</span></span> 

<span data-ttu-id="21b5a-118">Nella pagina **Parametri di pianificazione generale**, è possibile impostare l'ora di inizio per il calcolo dei ritardi.</span><span class="sxs-lookup"><span data-stu-id="21b5a-118">On the **Master planning parameters** page, you can set the start time for the calculation of delays.</span></span> <span data-ttu-id="21b5a-119">Se un ordine viene evaso dopo questo orario, viene aggiunto un ritardo di un giorno alla data di ritardo dell'ordine.</span><span class="sxs-lookup"><span data-stu-id="21b5a-119">If an order is fulfilled after this time, a delay of one day is added to the delay date of the order.</span></span> 

> <span data-ttu-id="21b5a-120">[!NOTE} nelle versioni precedenti, i ritardi calcolati erano denominati *messaggi di ritardo*, la data di ritardo era denominata *data ritardo* e una transazione ritardata era definita *una transazione impostata su una data futura*.</span><span class="sxs-lookup"><span data-stu-id="21b5a-120">[!NOTE} In earlier versions, calculated delays were known as *futures messages*, the delayed date was known as the *futures date*, and a delayed transaction was referred to as *a transaction that was future set*.</span></span>

## <a name="desired-date"></a><span data-ttu-id="21b5a-121">Data desiderata</span><span class="sxs-lookup"><span data-stu-id="21b5a-121">Desired date</span></span>

<span data-ttu-id="21b5a-122">Nella pagina **Ordine pianificato**, sotto la scheda **Ritardi** è visualizzata la **data desiderata** per l'ordine pianificato.</span><span class="sxs-lookup"><span data-stu-id="21b5a-122">On the **Planned order** page, under the **Delays** tab is the **Desired date** for the planned order.</span></span> <span data-ttu-id="21b5a-123">La data desiderata di un ordine pianificato è la data di base per i ritardi, ovvero una data calcolata uguale alla **data richiesta** calcolata a partire dal **fabbisogno netto**.</span><span class="sxs-lookup"><span data-stu-id="21b5a-123">The desired date of a planned order is the base date for delays, which is a computed date that equals the **Requested date** calculated from the **Net Requirement**.</span></span> <span data-ttu-id="21b5a-124">Se l'ordine pianificato è una riga DBA, una riga di produzione o una riga kanban, la data desiderata si basa sulla **data fabbisogno** e la data desiderata non verrà visualizzata nella pagina **Ordine pianificato**.</span><span class="sxs-lookup"><span data-stu-id="21b5a-124">If the planned order is a BOM line, production line or kanban line, the desired date is based on the **Requirement date** and the desired date will not be shown on the **Planned order** page.</span></span>

<a name="additional-resources"></a><span data-ttu-id="21b5a-125">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="21b5a-125">Additional resources</span></span>
--------

[<span data-ttu-id="21b5a-126">Impostazioni della copertura</span><span class="sxs-lookup"><span data-stu-id="21b5a-126">Coverage settings</span></span>](coverage-settings.md)
