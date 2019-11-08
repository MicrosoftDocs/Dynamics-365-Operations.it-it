---
title: Stati del ciclo di vita delle richieste di intervento di manutenzione
description: In questo argomento viene descritto come impostare gli stati del ciclo di vita delle richieste di intervento di manutenzione in Gestione cespiti.
author: josaw1
manager: AnnBe
ms.date: 07/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 151db9ca8a121759e39b690ec296b36a18dc1729
ms.sourcegitcommit: d37fb09101c30858bcb975931b3d8f947d72017b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/10/2019
ms.locfileid: "2571164"
---
# <a name="maintenance-request-lifecycle-states"></a><span data-ttu-id="c38e7-103">Stati del ciclo di vita delle richieste di intervento di manutenzione</span><span class="sxs-lookup"><span data-stu-id="c38e7-103">Maintenance request lifecycle states</span></span>

[!include [banner](../../includes/banner.md)]

 


<span data-ttu-id="c38e7-104">Gli stato del ciclo di vita delle richieste di intervento di manutenzione definiscono le fasi in cui può trovarsi una richiesta.</span><span class="sxs-lookup"><span data-stu-id="c38e7-104">Maintenance request lifecycle states define the stages that a request can go through.</span></span> <span data-ttu-id="c38e7-105">Esempi includono **Creato**, **Attivo** e **Finito**.</span><span class="sxs-lookup"><span data-stu-id="c38e7-105">Examples include **Created**, **Active**, and **Ended**.</span></span> <span data-ttu-id="c38e7-106">Quando una richiesta di intervento di manutenzione viene convertita in ordine di lavoro, lo stato del ciclo di vita della richiesta deve essere aggiornato a **Finito** o **Chiuso** per indicare che la richiesta non è più attiva.</span><span class="sxs-lookup"><span data-stu-id="c38e7-106">When a maintenance request is converted to a work order, the maintenance request lifecycle state should be updated to **Ended** or **Closed** to indicate that the maintenance request is no longer active.</span></span> <span data-ttu-id="c38e7-107">Nella pagina elenco **Tutte le richieste di intervento di manutenzione**, vengono visualizzate tutte le richieste di intervento di manutenzione, indipendentemente dallo stato del ciclo di vita.</span><span class="sxs-lookup"><span data-stu-id="c38e7-107">On the **All maintenance requests** list page, you can view all maintenance requests, regardless of their lifecycle state.</span></span>

## <a name="set-up-maintenance-request-lifecycle-states"></a><span data-ttu-id="c38e7-108">Imposta gli stati del ciclo di vita della richiesta di intervento di manutenzione</span><span class="sxs-lookup"><span data-stu-id="c38e7-108">Set up maintenance request lifecycle states</span></span>

1. <span data-ttu-id="c38e7-109">Selezionare **Gestione cespiti** \> **Impostazione** \> **Richieste di intervento di manutenzione** \> **Stati del ciclo di vita**.</span><span class="sxs-lookup"><span data-stu-id="c38e7-109">Select **Asset management** \> **Setup** \> **Maintenance requests** \> **Lifecycle states**.</span></span>
2. <span data-ttu-id="c38e7-110">Selezionare **Nuovo** per creare un nuovo stato del ciclo di vita delle richieste di intervento di manutenzione.</span><span class="sxs-lookup"><span data-stu-id="c38e7-110">Select **New** to create a maintenance request lifecycle state.</span></span>
3. <span data-ttu-id="c38e7-111">Nel campo **Stato del ciclo di vita**, immettere l'ID dello stato del ciclo di vita.</span><span class="sxs-lookup"><span data-stu-id="c38e7-111">In the **Lifecycle state** field, enter an ID for the lifecycle state.</span></span>
4. <span data-ttu-id="c38e7-112">Nel campo **Nome** immettere un nome.</span><span class="sxs-lookup"><span data-stu-id="c38e7-112">In the **Name** field, enter a name.</span></span>

    <span data-ttu-id="c38e7-113">Nella Scheda dettaglio **Dettagli** il campo **Modelli del ciclo di vita** mostra il numero di modelli del ciclo di vita delle richieste di intervento di manutenzione che utilizzano lo stato del ciclo di vita del cespite.</span><span class="sxs-lookup"><span data-stu-id="c38e7-113">On the **Details** FastTab, the **Lifecycle models** field shows the number of maintenance request lifecycle models that use this lifecycle state.</span></span>

5. <span data-ttu-id="c38e7-114">Nella Scheda dettaglio **Generale**, impostare **Attivo** su **Sì** se la richiesta di intervento di manutenzione deve essere attiva mentre si trova in questo stato del ciclo di vita.</span><span class="sxs-lookup"><span data-stu-id="c38e7-114">On the **General** FastTab, set the **Active** option to **Yes** if a maintenance request should be active while it's in this lifecycle state.</span></span>
6. <span data-ttu-id="c38e7-115">Impostare **Imposta fine effettiva** su **Sì** se la data e ora di fine effettive devono essere immesse automaticamente in una richiesta di intervento di manutenzione che si trova in questo stato del ciclo di vita.</span><span class="sxs-lookup"><span data-stu-id="c38e7-115">Set he **Set actual end** option to **Yes** if an actual end date and time should automatically be entered on a maintenance request that is in this lifecycle state.</span></span>
7. <span data-ttu-id="c38e7-116">Impostare **Crea ordine di lavoro** su **Sì** se un ordine di lavoro può essere creato da una richiesta di intervento di manutenzione che si trova in questo stato del ciclo di vita.</span><span class="sxs-lookup"><span data-stu-id="c38e7-116">Set the **Create work order** option to **Yes** if a work order can be created from a maintenance request that is in this lifecycle state.</span></span>
8. <span data-ttu-id="c38e7-117">Impostare **Elimina** su **Sì** se la richiesta di intervento di manutenzione può essere eliminata mentre si trova in questo stato del ciclo di vita.</span><span class="sxs-lookup"><span data-stu-id="c38e7-117">Set the **Delete** option to **Yes** if a maintenance request can be deleted while it's in this lifecycle state.</span></span>
9. <span data-ttu-id="c38e7-118">Nella Scheda dettaglio **Aggiorna**, le opzioni **In entrata** e **In uscita** nella sezione **Cespite** sono pertinenti se si utilizza la riparazione in deposito. Impostare l'opzione appropriata su **Sì** se lo stato del ciclo di vita dei cespiti selezionati in una richiesta di intervento di manutenzione deve essere aggiornato automaticamente su **In entrata** o **In uscita** quando lo stato del ciclo di vita di quella richiesta di intervento di manutenzione è impostato su **In entrata** o **In uscita**.</span><span class="sxs-lookup"><span data-stu-id="c38e7-118">On the **Update** FastTab, the **Inbound** and **Outbound** options in the **Asset** section are relevant if you use depot repair.cSet the appropriate option to **Yes** if the asset lifecycle state of assets that are selected on a maintenance request should automatically be updated to **Inbound** or **Outbound** when the maintenance request lifecycle state of that maintenance request is set to **Inbound** or **Outbound**.</span></span>

<span data-ttu-id="c38e7-119">Nella figura seguente è illustrato un esempio della pagina **Stati del ciclo di vita delle richieste di intervento di manutenzione**.</span><span class="sxs-lookup"><span data-stu-id="c38e7-119">The follow illustration shows an example of the **Maintenance request lifecycle states** page.</span></span>

![Pagina Stati del ciclo di vita delle richieste di intervento di manutenzione](media/02-setup-for-requests.png)

> [!NOTE]
> <span data-ttu-id="c38e7-121">Gli stati del ciclo di vita , i gruppi di stati del ciclo di vita e i tipi delle richieste di intervento di manutenzione sono correlati a vengono utilizzati allo stesso modo degli stati del ciclo di vita , gruppi di stati del ciclo di vita e i tipi degli ordini di lavoro.</span><span class="sxs-lookup"><span data-stu-id="c38e7-121">Maintenance request lifecycle states, lifecycle state groups, and types are related to, and used in the same way as, work order lifecycle states, lifecycle state groups, and types.</span></span> 

## <a name="set-up-maintenance-request-lifecycle-models"></a><span data-ttu-id="c38e7-122">Impostare i modelli del ciclo di vita della richiesta di intervento di manutenzione</span><span class="sxs-lookup"><span data-stu-id="c38e7-122">Set up maintenance request lifecycle models</span></span>

<span data-ttu-id="c38e7-123">Dopo aver creato gli stati del ciclo di vita necessari per le richieste di intervento di manutenzione, possono essere divisi in gruppi di stati del ciclo di vita, o modelli del ciclo di vita.</span><span class="sxs-lookup"><span data-stu-id="c38e7-123">After you've created the lifecycle states that are required for your maintenance requests, they can be divided into lifecycle state groups, or lifecycle models.</span></span> <span data-ttu-id="c38e7-124">I modelli del ciclo di vita delle richieste di intervento di manutenzione vengono utilizzati per creare il flusso che può essere utilizzato per i diversi tipi di richieste di intervento di manutenzione.</span><span class="sxs-lookup"><span data-stu-id="c38e7-124">Maintenance request lifecycle models are used to create the flow that can be used for different types of maintenance requests.</span></span> <span data-ttu-id="c38e7-125">Come minimo, un modello standard del ciclo di vita delle richieste di intervento di manutenzione deve essere creato.</span><span class="sxs-lookup"><span data-stu-id="c38e7-125">At a minimum, one standard maintenance request lifecycle model should be created.</span></span>

1. <span data-ttu-id="c38e7-126">Selezionare **Gestione cespiti** \> **Impostazione** \> **Richieste di intervento di manutenzione** \> **Modelli del ciclo di vita**.</span><span class="sxs-lookup"><span data-stu-id="c38e7-126">Select **Asset management** \> **Setup** \> **Maintenance requests** \> **Lifecycle models**.</span></span>
2. <span data-ttu-id="c38e7-127">Selezionare **Nuovo** per creare un modello del ciclo di vita delle richieste di intervento di manutenzione.</span><span class="sxs-lookup"><span data-stu-id="c38e7-127">Select **New** to create a maintenance request lifecycle model.</span></span>
3. <span data-ttu-id="c38e7-128">Nel campo **Modello del ciclo di vita**, immettere un ID del modello del ciclo di vita.</span><span class="sxs-lookup"><span data-stu-id="c38e7-128">In the **Lifecycle model** field, enter an ID for the lifecycle model.</span></span>
4. <span data-ttu-id="c38e7-129">Nel campo **Nome** immettere un nome.</span><span class="sxs-lookup"><span data-stu-id="c38e7-129">In the **Name** field, enter a name.</span></span>

    <span data-ttu-id="c38e7-130">Nella Scheda dettaglio **Dettagli**, **Stati del ciclo di vita** mostra il numero di stati del ciclo di vita del cespite selezionati in questo modello del ciclo di vita.</span><span class="sxs-lookup"><span data-stu-id="c38e7-130">On the **Details** FastTab, the **Lifecycle states** shows the number of lifecycle states that are selected in this lifecycle model.</span></span> <span data-ttu-id="c38e7-131">Nel campo **Tipi di richieste di intervento di manutenzione** viene visualizzato il numero di tipi di richieste di intervento di manutenzione che utilizzano questo modello del ciclo di vita.</span><span class="sxs-lookup"><span data-stu-id="c38e7-131">The **Maintenance request types** field shows the number of maintenance request types that use this lifecycle model.</span></span>

5. <span data-ttu-id="c38e7-132">Nella Scheda dettaglio **Stati del ciclo di vita**, selezionare gli stati del ciclo di vita che devono essere inclusi nel modello:</span><span class="sxs-lookup"><span data-stu-id="c38e7-132">On the **Lifecycle states** FastTab, select the lifecycle states that should be included in the lifecycle model:</span></span>

    - <span data-ttu-id="c38e7-133">Per includere uno stato del ciclo di vita nel modello, selezionarlo nella sezione **Stati del ciclo di vita rimanenti** e quindi fare clic sul pulsante freccia destra ![Freccia destra](media/03-setup-for-requests.png) per spostarlo nella sezione **Stati del ciclo di vita selezionati**.</span><span class="sxs-lookup"><span data-stu-id="c38e7-133">To include a lifecycle state in the lifecycle model, select it in the **Lifecycle states remaining** section, and then select the right arrow button ![Right arrow](media/03-setup-for-requests.png) to move it to the **Lifecycle states selected** section.</span></span>
    - <span data-ttu-id="c38e7-134">Per includere tutti gli stati del ciclo di vita disponibili nel modello, selezionare il pulsante **Seleziona tutti gli stati disponibili** ![Seleziona tutti gli stati disponibili](media/04-setup-for-requests.png).</span><span class="sxs-lookup"><span data-stu-id="c38e7-134">To include all the available lifecycle states in the lifecycle model, select the **Select all available states** button ![Select all available states](media/04-setup-for-requests.png).</span></span> <span data-ttu-id="c38e7-135">Tutti gli stati del ciclo di vita verranno spostati nella sezione **Stati del ciclo di vita selezionati**.</span><span class="sxs-lookup"><span data-stu-id="c38e7-135">All lifecycle states are moved to the **Lifecycle states selected** section.</span></span>
    - <span data-ttu-id="c38e7-136">Per rimuovere uno stato del ciclo di vita dal modello, selezionarlo nella sezione **Stati del ciclo di vita selezionati** e quindi fare clic sul pulsante freccia sinistra ![Freccia sinistra](media/05-setup-for-requests.png) per spostarlo nella sezione **Stati del ciclo di vita rimanenti**.</span><span class="sxs-lookup"><span data-stu-id="c38e7-136">To remove a lifecycle state from the lifecycle model, select it in the **Lifecycle states selected** section, and then select the left arrow button ![Left arrow](media/05-setup-for-requests.png) to move it to the **Lifecycle states remaining** section.</span></span>

6. <span data-ttu-id="c38e7-137">Nella Scheda dettaglio **Generale**, i campi della sezione **Aggiornamenti** sono pertinenti se si utilizza la riparazione in deposito.</span><span class="sxs-lookup"><span data-stu-id="c38e7-137">On the **General** FastTab, the fields in the **Updates** section are relevant if you use depot repair.</span></span>

    - <span data-ttu-id="c38e7-138">Nel campo **Stato del ciclo di vita per cespite ricevuto**, selezionare lo stato del ciclo di vita del cespite a cui i cespiti selezionati in una richiesta di intervento di manutenzione devono essere aggiornati automaticamente quando vengono ricevuti per la riparazione in deposito.</span><span class="sxs-lookup"><span data-stu-id="c38e7-138">In the **Lifecycle state for asset received** field, select the asset lifecycle state that assets that are selected on a maintenance request should automatically be updated to when they are received for depot repair.</span></span>
    - <span data-ttu-id="c38e7-139">Nel campo **Stato del ciclo di vita per cespite consegnato**, selezionare lo stato del ciclo di vita del cespite a cui i cespiti selezionati in una richiesta di intervento di manutenzione devono essere aggiornati automaticamente quando vengono restituiti dopo la riparazione.</span><span class="sxs-lookup"><span data-stu-id="c38e7-139">In the **Lifecycle state for asset delivered** field, select the lifecycle state that assets that are selected on a maintenance request should automatically be updated to when they are returned after repair.</span></span>

<span data-ttu-id="c38e7-140">Nella figura seguente è illustrato un esempio della pagina **Modelli del ciclo di vita delle richieste di intervento di manutenzione**.</span><span class="sxs-lookup"><span data-stu-id="c38e7-140">The following illustration shows an example of the **Maintenance request lifecycle models** page.</span></span>

![Pagina Modelli del ciclo di vita delle richieste di intervento di manutenzione](media/06-setup-for-requests.png)
