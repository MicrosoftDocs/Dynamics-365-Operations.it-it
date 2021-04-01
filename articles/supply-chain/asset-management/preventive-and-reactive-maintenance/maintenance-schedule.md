---
title: Programma di manutenzione
description: In questo argomento viene descritto il programma di manutenzione in Gestione cespiti.
author: josaw1
manager: tfehr
ms.date: 08/27/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetObjectCalendarCreateWO, EntAssetObjectCalendarListPagePoolsOpen, EntAssetObjectCalendarListPage, EntAssetObjectCalendarListPagePreviewPart, EntAssetObjectCalendarEdit, EntAssetObjectCalendarAdjust, EntAssetObjectCalendarDiscard, EntAssetObjectCalendarInfoPart
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 89938a4c5fd9a520c6582215a438670f73085228
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5252944"
---
# <a name="maintenance-schedule"></a><span data-ttu-id="cbf0a-103">Programma di manutenzione</span><span class="sxs-lookup"><span data-stu-id="cbf0a-103">Maintenance schedule</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="cbf0a-104">Il processo di manutenzione contiene un elenco di tutti i piani di manutenzione preventiva previsti, le richiesta di intervento di manutenzione e i cicli di manutenzione da eseguire. Alcune righe di programmazione possono essere state convertite in ordini di lavoro.</span><span class="sxs-lookup"><span data-stu-id="cbf0a-104">The maintenance schedule contains a list of all the expected preventive maintenance plans, maintenance requests, and maintenance rounds to be carried out. Some schedule lines may have been converted to work orders.</span></span>

<span data-ttu-id="cbf0a-105">Le quattro visualizzazioni del programma di manutenzione sono leggermente differenti, a seconda delle righe di programma di manutenzione che si desidera visualizzare.</span><span class="sxs-lookup"><span data-stu-id="cbf0a-105">The four maintenance schedule views are slightly different, depending on which maintenance schedule lines you want to see.</span></span>

| <span data-ttu-id="cbf0a-106">Voce di menu</span><span class="sxs-lookup"><span data-stu-id="cbf0a-106">Menu item</span></span>                  | <span data-ttu-id="cbf0a-107">Descrizione del contenuto</span><span class="sxs-lookup"><span data-stu-id="cbf0a-107">Description of contents</span></span>                                                                                                                                             |
|----------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="cbf0a-108">Tutto il programma di manutenzione</span><span class="sxs-lookup"><span data-stu-id="cbf0a-108">All maintenance schedule</span></span>       | <span data-ttu-id="cbf0a-109">Sono visualizzate tutte le righe di programma di manutenzione.</span><span class="sxs-lookup"><span data-stu-id="cbf0a-109">All maintenance schedule lines are shown.</span></span>     |
| <span data-ttu-id="cbf0a-110">Programmazione del cespite personale</span><span class="sxs-lookup"><span data-stu-id="cbf0a-110">My asset schedule</span></span>        | <span data-ttu-id="cbf0a-111">Tutte le righe di programma di manutenzione contenenti cespiti installati in unità funzionali a cui si è correlati in quanto lavoratore (impostazione in [Addetti e gruppi di addetti alla manutenzione](../setup-for-objects/workers-and-worker-groups.md)) sono visualizzate in questo elenco.</span><span class="sxs-lookup"><span data-stu-id="cbf0a-111">All maintenance schedule lines containing assets installed on functional locations to which you are related as a worker (set up in [Maintenance workers and worker groups](../setup-for-objects/workers-and-worker-groups.md)) are shown in this list.</span></span> |
| <span data-ttu-id="cbf0a-112">Apri le righe di programma di manutenzione</span><span class="sxs-lookup"><span data-stu-id="cbf0a-112">Open maintenance schedule lines</span></span> | <span data-ttu-id="cbf0a-113">Le righe di programma di manutenzione il cui stato è "Creata", a indicare che non sono ancora state convertite in un ordine di lavoro o sono state eliminate, sono visualizzate in questo elenco.</span><span class="sxs-lookup"><span data-stu-id="cbf0a-113">Maintenance schedule lines with status "Created" - meaning they have not yet been converted to a work order or discarded - are shown in this list.</span></span>                                            |
| <span data-ttu-id="cbf0a-114">Apri i pool di programmi di manutenzione</span><span class="sxs-lookup"><span data-stu-id="cbf0a-114">Open maintenance schedule pools</span></span> | <span data-ttu-id="cbf0a-115">Le righe di programma di manutenzione correlate a un pool di ordini di lavoro sono visualizzate in questo elenco.</span><span class="sxs-lookup"><span data-stu-id="cbf0a-115">Maintenance schedule lines related to a work order pool are shown in this list.</span></span>                                                                                                                  |

>[!NOTE]
><span data-ttu-id="cbf0a-116">Se una riga di programma di manutenzione è inclusa in vari pool di ordini di lavoro (vedere [Pool di ordini di lavoro](../work-orders/work-order-pools.md)), un record viene visualizzato per ogni pool in **Apri pool di programmi di manutenzione**.</span><span class="sxs-lookup"><span data-stu-id="cbf0a-116">If a maintenance schedule line is included in several work order pools (refer to [Work order pools](../work-orders/work-order-pools.md)), one record is shown for each pool in **Open maintenance schedule pools**.</span></span> <span data-ttu-id="cbf0a-117">Questa operazione viene eseguita per ottimizzare le opzioni di filtro per i pool di ordini di lavoro.</span><span class="sxs-lookup"><span data-stu-id="cbf0a-117">This is done to optimize filtering options on work order pools.</span></span>

<span data-ttu-id="cbf0a-118">Per aprire un programma di manutenzione</span><span class="sxs-lookup"><span data-stu-id="cbf0a-118">To open a maintenance schedule:</span></span>

1. <span data-ttu-id="cbf0a-119">Fare clic su **Gestione cespiti** > **Comune** > **Programma di manutenzione** > **Tutti i programmi di manutenzione** o **Apri righe di programma di manutenzione** o **Apri pool di programmi di manutenzione**.</span><span class="sxs-lookup"><span data-stu-id="cbf0a-119">Click **Asset management** > **Common** > **Maintenance schedule** > **All maintenance schedule** or **Open maintenance schedule lines** or **Open maintenance schedule pools**.</span></span>

2. <span data-ttu-id="cbf0a-120">Per aggiornare il programma di manutenzione, fare clic su **Piano di manutenzione** o **Cicli di manutenzione**.</span><span class="sxs-lookup"><span data-stu-id="cbf0a-120">To update the maintenance schedule, click **Maintenance plan** or **Maintenance rounds**.</span></span> 

3. <span data-ttu-id="cbf0a-121">È possibile modificare una riga di programma di manutenzione selezionandola e facendo clic su **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="cbf0a-121">You can edit a maintenance schedule line by selecting it and clicking **Edit**.</span></span> <span data-ttu-id="cbf0a-122">Ad esempio, è possibile aggiornare facilmente il livello del servizio o il lavoratore responsabile del processo.</span><span class="sxs-lookup"><span data-stu-id="cbf0a-122">For example, you can easily update the service level or the worker responsible for the job.</span></span> <span data-ttu-id="cbf0a-123">È possibile modificare solo le righe di programma di manutenzione che non sono ancora state associate a un ordine di lavoro.</span><span class="sxs-lookup"><span data-stu-id="cbf0a-123">You can only edit maintenance schedule lines that have not yet been connected to a work order.</span></span>

4. <span data-ttu-id="cbf0a-124">È possibile eliminare una riga di programma di manutenzione selezionandola nella pagina elenco e facendo clic su **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="cbf0a-124">You can delete a maintenance schedule line by selecting it in the list page and clicking **Delete**.</span></span>

5. <span data-ttu-id="cbf0a-125">È possibile eliminare una riga di programma di manutenzione selezionandola nella pagina elenco e facendo clic su **Rimuovi**.</span><span class="sxs-lookup"><span data-stu-id="cbf0a-125">You can discard a maintenance schedule line by selecting it in the list page and clicking **Discard**.</span></span> <span data-ttu-id="cbf0a-126">Questa funzione è utile se, ad esempio, un cespite ha un piano di manutenzione di 2.000 chilometri e un piano di manutenzione di 10.000 chilometri.</span><span class="sxs-lookup"><span data-stu-id="cbf0a-126">This function is useful if, for example, an asset has a 2,000 km maintenance plan and a 10,000 km maintenance plan.</span></span> <span data-ttu-id="cbf0a-127">Quindi, è possibile che si intenda rimuovere la riga creata dal piano di manutenzione di 2.000 chilometri quando coincide con 10.000 km, 20.000 km, 30.000 km e così via.</span><span class="sxs-lookup"><span data-stu-id="cbf0a-127">Then, you may want to discard the line created from the 2,000 km maintenance plan when it coincides with 10,000 km, 20,000 km, 30,000 km, and so on.</span></span> <span data-ttu-id="cbf0a-128">Se si rimuove una riga di programma di manutenzione associata a un piano di manutenzione, quella riga non sarà più visualizzata quando il piano di manutenzione viene programmato.</span><span class="sxs-lookup"><span data-stu-id="cbf0a-128">If you discard a maintenance schedule line related to a maintenance plan, that line will never again appear when that maintenance plan is scheduled.</span></span>

6. <span data-ttu-id="cbf0a-129">È possibile selezionare un numero di righe di programma di manutenzione in **Tutti i programmi di manutenzione** e fare clic su **Pool di ordini di lavoro**, se tutte le righe selezionate devono essere incluse nello stesso pool di ordini di lavoro.</span><span class="sxs-lookup"><span data-stu-id="cbf0a-129">You can select a number of maintenance schedule lines in **All maintenance schedule** and click **Work order pool**, if you want all selected lines to be included in the same work order pool.</span></span>

7. <span data-ttu-id="cbf0a-130">È possibile selezionare un numero di righe di programma di manutenzione in **Tutti i programmi di manutenzione**, **Apri righe di programma di manutenzione** o **Apri pool di programmi di manutenzione** e fare clic su **Rettifica le programmazioni** se si intende eseguire le stesse rettifiche su più righe.</span><span class="sxs-lookup"><span data-stu-id="cbf0a-130">You can select a number of maintenance schedule lines in **All maintenance schedule** or **Open maintenance schedule lines** or **Open maintenance schedule pools** and click **Adjust schedule** if you want to make the same adjustments on several lines.</span></span> <span data-ttu-id="cbf0a-131">È possibile modificare le date di inizio e fine previste, il livello del servizio e il gruppo di addetti alla manutenzione responsabile o l'addetto alla manutenzione responsabile associato alle righe di programma di manutenzione selezionate.</span><span class="sxs-lookup"><span data-stu-id="cbf0a-131">You can change expected start and end dates, service level, and the responsible maintenance worker group or responsible maintenance worker related to the selected maintenance schedule lines.</span></span>

- <span data-ttu-id="cbf0a-132">Quando una riga di programma di manutenzione è associata a un ordine di lavoro, l'ID ordine di lavoro viene visualizzato nel campo **Ordine di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="cbf0a-132">When a maintenance schedule line has been related to a work order, the work order ID will be displayed in the **Work order** field.</span></span>  
- <span data-ttu-id="cbf0a-133">Nella visualizzazione dettagli **Tutti i cespiti** > Scheda dettaglio **Piani di manutenzione cespiti**, è possibile selezionare piani di manutenzione per il cespite.</span><span class="sxs-lookup"><span data-stu-id="cbf0a-133">In **All assets** details view > **Asset maintenance plans** FastTab, you can select maintenance plans for the asset.</span></span> <span data-ttu-id="cbf0a-134">Successivamente, se si elimina una riga di piano di manutenzione associata a un cespite in **Tutti i cespiti**, si eliminano automaticamente anche tutte le righe di programma di manutenzione con stato "Creata" che sono state create in base a quel piano di manutenzione.</span><span class="sxs-lookup"><span data-stu-id="cbf0a-134">Later, if you delete a maintenance plan line related to an asset in **All assets**, you also automatically delete all maintenance schedule lines with status "Created" that have been created based on that maintenance plan.</span></span> <span data-ttu-id="cbf0a-135">Vedere anche [Creare un cespite](../objects/create-an-object.md).</span><span class="sxs-lookup"><span data-stu-id="cbf0a-135">See also [Create an asset](../objects/create-an-object.md).</span></span>

<span data-ttu-id="cbf0a-136">L'illustrazione seguente mostra la pagina di elenco **Tutti i programmi di manutenzione**.</span><span class="sxs-lookup"><span data-stu-id="cbf0a-136">The illustration below shows the **All maintenance schedule** list page.</span></span>

![Figura 1](media/16-preventive-maintenance.png)



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]