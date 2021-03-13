---
title: Descrizione e livello del servizio
description: In questo argomento vengono descritti il livello e la descrizione del servizio in Gestione cespiti.
author: josaw1
manager: tfehr
ms.date: 08/13/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetObjectServiceLevel, EntAssetWorkOrderStandardDescription, EntAssetWorkOrderServiceLevel, EntAssetServiceLevelLookup
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 8bb56e5103bd9e18e88c164cd308e55d48e64823
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/16/2021
ms.locfileid: "5019381"
---
# <a name="service-level-and-description"></a><span data-ttu-id="e3dd3-103">Descrizione e livello del servizio</span><span class="sxs-lookup"><span data-stu-id="e3dd3-103">Service level and description</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="e3dd3-104">Quando si crea un ordine di lavoro, è possibile che si voglia definire i relativi livelli del servizio e aggiungervi una descrizione generale.</span><span class="sxs-lookup"><span data-stu-id="e3dd3-104">When you create a work order, you might want to define the service levels for it and add a general description to it.</span></span> <span data-ttu-id="e3dd3-105">È possibile creare i livelli di servizio di ordine di lavoro nella pagina **Livelli di servizio ordine di lavoro** e le descrizioni nella pagina **Descrizione ordine di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="e3dd3-105">You can create work order service levels on the **Work order service levels** page and descriptions on the **Work order description** page.</span></span>

## <a name="create-a-service-level"></a><span data-ttu-id="e3dd3-106">Creare un livello del servizio</span><span class="sxs-lookup"><span data-stu-id="e3dd3-106">Create a service level</span></span>

1. <span data-ttu-id="e3dd3-107">Selezionare **Gestione cespiti** \> **Impostazione** \> **Ordini di lavoro** \> **Livello servizio**.</span><span class="sxs-lookup"><span data-stu-id="e3dd3-107">Select **Asset management** \> **Setup** \> **Work orders** \> **Service level**.</span></span>
2. <span data-ttu-id="e3dd3-108">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="e3dd3-108">Select **New**.</span></span>
3. <span data-ttu-id="e3dd3-109">Nel campo **Livello servizio**, immettere il livello del servizio (ad esempio, un numero).</span><span class="sxs-lookup"><span data-stu-id="e3dd3-109">In the **Service level** field, enter the service level (for example, a number).</span></span>
4. <span data-ttu-id="e3dd3-110">Nel campo **Nome** immettere un nome.</span><span class="sxs-lookup"><span data-stu-id="e3dd3-110">In the **Name** field, enter a name.</span></span>

    <span data-ttu-id="e3dd3-111">Nella Scheda dettaglio **Ordini di lavoro**, è possibile definire la data e l'ora di inizio e fine previste.</span><span class="sxs-lookup"><span data-stu-id="e3dd3-111">On the **Work orders** FastTab, you can define expected start and end dates and times.</span></span> <span data-ttu-id="e3dd3-112">I campi di questa Scheda dettaglio definiscono il periodo durante il quale gli ordini di lavoro devono essere iniziati e terminati.</span><span class="sxs-lookup"><span data-stu-id="e3dd3-112">The fields on this FastTab define the period that work orders should be started and ended during.</span></span> <span data-ttu-id="e3dd3-113">Questi sono utilizzati per gli ordini di lavoro creati manualmente e gli ordini di lavoro creati in base alle richieste di intervento di manutenzione.</span><span class="sxs-lookup"><span data-stu-id="e3dd3-113">They are used for work orders that are manually created and work orders that are created based on maintenance requests.</span></span> 

5. <span data-ttu-id="e3dd3-114">Nel campo **Primo giorno**, immettere un numero di giorni per definire il periodo durante il quale l'ordine di lavoro deve iniziare.</span><span class="sxs-lookup"><span data-stu-id="e3dd3-114">In the **Start day** field, enter a number of days to define the period that the work order should start during.</span></span> <span data-ttu-id="e3dd3-115">Il numero di giorni viene calcolato a partire dalla data di creazione dell'ordine di lavoro.</span><span class="sxs-lookup"><span data-stu-id="e3dd3-115">The number of days is calculated from the creation date of the work order.</span></span> <span data-ttu-id="e3dd3-116">Ad esempio, se l'ordine di lavoro deve iniziare alla data di creazione, immettere **0**.</span><span class="sxs-lookup"><span data-stu-id="e3dd3-116">For example, if the work order should start when it's created, enter **0**.</span></span> <span data-ttu-id="e3dd3-117">Se l'ordine di lavoro deve iniziare una settimana dopo la data di creazione, immettere **7**.</span><span class="sxs-lookup"><span data-stu-id="e3dd3-117">If the work order should start within one week after it's created, enter **7**.</span></span>
6. <span data-ttu-id="e3dd3-118">Per impostare un'ora di inizio per l'ordine di lavoro, oltre a una data di inizio, impostare l'opzione **Imposta ora di inizio** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="e3dd3-118">To set a start time for the work order, in addition to a start date, set the **Set start time** option to **Yes**.</span></span> <span data-ttu-id="e3dd3-119">Quindi immettere l'ora di inizio nel campo **Ora di inizio**.</span><span class="sxs-lookup"><span data-stu-id="e3dd3-119">Then enter the start time in the **Start time** field.</span></span> <span data-ttu-id="e3dd3-120">Se si imposta l'opzione su **No**, viene visualizzata l'ora del giorno corrente.</span><span class="sxs-lookup"><span data-stu-id="e3dd3-120">If you set the option to **No**, the current time of day is used.</span></span>
7. <span data-ttu-id="e3dd3-121">Nel campo **Ultimo giorno**, immettere un numero di giorni per definire il periodo durante il quale l'ordine di lavoro deve terminare.</span><span class="sxs-lookup"><span data-stu-id="e3dd3-121">In the **End day** field, enter a number of days to define the period that the work order should end during.</span></span> <span data-ttu-id="e3dd3-122">Il numero di giorni viene calcolato a partire dalla data di inizio dell'ordine di lavoro.</span><span class="sxs-lookup"><span data-stu-id="e3dd3-122">The number of days is calculated from the start date of the work order.</span></span> <span data-ttu-id="e3dd3-123">Ad esempio, se l'ordine di lavoro deve terminare una settimana dopo la data di inizio, immettere **7**.</span><span class="sxs-lookup"><span data-stu-id="e3dd3-123">For example, if the work order should end within one week of its start date, enter **7**.</span></span>
8. <span data-ttu-id="e3dd3-124">Per impostare un'ora di fine per l'ordine di lavoro, oltre a una data di fine, impostare l'opzione **Imposta ora di fine** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="e3dd3-124">To set an end time for the work order, in addition to an end date, set the **Set end time** option to **Yes**.</span></span> <span data-ttu-id="e3dd3-125">Quindi immettere l'ora di fine nel campo **Ora di fine**.</span><span class="sxs-lookup"><span data-stu-id="e3dd3-125">Then enter the end time in the **End time** field.</span></span> <span data-ttu-id="e3dd3-126">Se si imposta l'opzione su **No**, viene visualizzata l'ora del giorno corrente.</span><span class="sxs-lookup"><span data-stu-id="e3dd3-126">If you set the option to **No**, the current time of day is used.</span></span>
9. <span data-ttu-id="e3dd3-127">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="e3dd3-127">Select **Save**.</span></span>

![Pagina Livello del servizio di ordine di lavoro](media/19-setup-for-work-orders.png)

## <a name="create-a-description"></a><span data-ttu-id="e3dd3-129">Creare una descrizione</span><span class="sxs-lookup"><span data-stu-id="e3dd3-129">Create a description</span></span>

1. <span data-ttu-id="e3dd3-130">Selezionare **Gestione cespiti** \> **Impostazione** \> **Ordini di lavoro** \> **Descrizioni**.</span><span class="sxs-lookup"><span data-stu-id="e3dd3-130">Select **Asset management** \> **Setup** \> **Work orders** \> **Descriptions**.</span></span>
2. <span data-ttu-id="e3dd3-131">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="e3dd3-131">Select **New**.</span></span>
3. <span data-ttu-id="e3dd3-132">Nel campo **Descrizione** immettere la descrizione.</span><span class="sxs-lookup"><span data-stu-id="e3dd3-132">In the **Description** field, enter the description.</span></span>
4. <span data-ttu-id="e3dd3-133">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="e3dd3-133">Select **Save**.</span></span>
