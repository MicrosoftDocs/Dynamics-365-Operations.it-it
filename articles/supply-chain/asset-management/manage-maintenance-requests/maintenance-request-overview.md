---
title: Richieste di intervento di manutenzione
description: In questo argomento viene fornita una panoramica sulla gestione delle richieste di intervento di manutenzione in Gestione cespiti
author: josaw1
manager: AnnBe
ms.date: 10/01/2019
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
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 56d4abee451e6e22b9b9cc2fd36a13648202e7df
ms.sourcegitcommit: 871b76f8808a48d282f151144829323258ffc912
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/02/2019
ms.locfileid: "1847438"
---
# <a name="maintenance-requests"></a><span data-ttu-id="ec55b-103">Richieste di intervento di manutenzione</span><span class="sxs-lookup"><span data-stu-id="ec55b-103">Maintenance requests</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

<span data-ttu-id="ec55b-104">Le richieste di intervento di manutenzione sono note o le dichiarazioni create per informare un responsabile o un responsabile della pianificazione che un cespite può richiedere un processo di riparazione o manutenzione, ma senza creare un ordine di lavoro.</span><span class="sxs-lookup"><span data-stu-id="ec55b-104">Maintenance requests are notes or declarations that are created to notify a manager or planner that an asset might require a maintenance or repair job, but without creating a work order.</span></span> <span data-ttu-id="ec55b-105">Se il contenuto di una richiesta di intervento di manutenzione viene considerato valido, un ordine di lavoro può quindi essere creato in base alla richiesta di intervento di manutenzione.</span><span class="sxs-lookup"><span data-stu-id="ec55b-105">If the contents of a maintenance request are considered valid, a work order can then be created based on the maintenance request.</span></span>

<span data-ttu-id="ec55b-106">Le richieste di intervento di manutenzione possono essere create per qualsiasi cespite in Gestione cespiti.</span><span class="sxs-lookup"><span data-stu-id="ec55b-106">Maintenance requests can be created for any asset in Asset Management.</span></span> <span data-ttu-id="ec55b-107">Diversi tipi di richieste di intervento di manutenzione possono essere creati, a seconda di come la società utilizza le richieste di intervento di manutenzione.</span><span class="sxs-lookup"><span data-stu-id="ec55b-107">Various types of maintenance requests can be created, depending on how your company uses maintenance requests.</span></span> <span data-ttu-id="ec55b-108">Di seguito sono riportati alcuni esempi.</span><span class="sxs-lookup"><span data-stu-id="ec55b-108">Here are some examples:</span></span>

- <span data-ttu-id="ec55b-109">Richieste di intervento di manutenzione</span><span class="sxs-lookup"><span data-stu-id="ec55b-109">Maintenance requests</span></span>
- <span data-ttu-id="ec55b-110">Note</span><span class="sxs-lookup"><span data-stu-id="ec55b-110">Notes</span></span>
- <span data-ttu-id="ec55b-111">Correzioni o miglioramenti</span><span class="sxs-lookup"><span data-stu-id="ec55b-111">Corrections or enhancements</span></span>
- <span data-ttu-id="ec55b-112">Investimenti</span><span class="sxs-lookup"><span data-stu-id="ec55b-112">Investments</span></span>
- <span data-ttu-id="ec55b-113">Riparazione in deposito (questo tipo viene utilizzato quando si ricevono i cespiti da un'altra ubicazione in modo da poter effettuare un processo di riparazione o di manutenzione e quindi restituire il cespite dopo che il processo è completato.)</span><span class="sxs-lookup"><span data-stu-id="ec55b-113">Depot repair (This type is used when you receive assets from another location so that you can do a maintenance or repair job, and you then return the asset after the job is completed.)</span></span>

## <a name="view-maintenance-requests"></a><span data-ttu-id="ec55b-114">Visualizza richieste di intervento di manutenzione</span><span class="sxs-lookup"><span data-stu-id="ec55b-114">View maintenance requests</span></span>

<span data-ttu-id="ec55b-115">Per visualizzare le richieste di intervento di manutenzione, selezionare **Gestione cespiti** \> **Comune** \> **Richieste di intervento di manutenzione** \>, **Tutte le richieste di intervento di manutenzione**, **Richieste di intervento di manutenzione attive** o **Richieste di intervento di manutenzione delle unità funzionali personali**.</span><span class="sxs-lookup"><span data-stu-id="ec55b-115">To view maintenance requests, select **Asset management** \> **Common** \> **Maintenance requests** \> **All maintenance requests**, **Active maintenance requests**, or **My functional location maintenance requests**.</span></span> <span data-ttu-id="ec55b-116">Ogni pagina elenco vengono visualizzate alcune informazioni correlate a una richiesta di intervento di manutenzione.</span><span class="sxs-lookup"><span data-stu-id="ec55b-116">Each list page shows some of the information that is related to a maintenance request.</span></span>

![Figura 1](media/01-manage-maintenance-requests.png)

> [!NOTE]
> <span data-ttu-id="ec55b-118">Usare la pagina elenco **Richieste di intervento di manutenzione delle unità funzionali personali** per visualizzare un elenco di richieste di intervento di manutenzione contenenti le unità funzionali a cui si è correlati come lavoratori o i cespiti installati nelle unità funzionali a cui si è correlati come lavoratore.</span><span class="sxs-lookup"><span data-stu-id="ec55b-118">Use the **My functional location maintenance requests** list page to view a list of maintenance requests that contain either functional locations that you're related to as a worker or assets that are installed on functional locations that you're related to as a worker.</span></span> <span data-ttu-id="ec55b-119">Per informazioni su come impostare le unità funzionali per gli addetti alla manutenzione, vedere [Addetti alla manutenzione e gruppi di lavoratori](../setup-for-objects/workers-and-worker-groups.md).</span><span class="sxs-lookup"><span data-stu-id="ec55b-119">(For information about how to set up functional locations on maintenance workers, see [Maintenance workers and worker groups](../setup-for-objects/workers-and-worker-groups.md).)</span></span>
> 
> <span data-ttu-id="ec55b-120">Sebbene le informazioni su un conto cliente siano disponibili in Gestione assistenza cespiti (manutenzione esterna), non sono disponibili in Gestione cespiti (manutenzione interna).</span><span class="sxs-lookup"><span data-stu-id="ec55b-120">Although customer account information is available in Asset Service Management (external maintenance), it isn't available in Asset Management (internal maintenance).</span></span>

<span data-ttu-id="ec55b-121">Per aprire la visualizzazione dettagli di un record, nella pagina elenco **Tutte le richieste di intervento di manutenzione**, in visualizzazione griglia, selezionare un collegamento nella colonna **Richiesta di intervento di manutenzione**.</span><span class="sxs-lookup"><span data-stu-id="ec55b-121">To open the details view of a record, on the **All maintenance requests** list page, in the grid view, select a link in the **Maintenance request** column.</span></span>

![Figura 2](media/02-manage-maintenance-requests.png)

<span data-ttu-id="ec55b-123">I pulsanti del riquadro azioni sono organizzati in schede.</span><span class="sxs-lookup"><span data-stu-id="ec55b-123">The buttons on the Action Pane are organized on tabs.</span></span> <span data-ttu-id="ec55b-124">Nella tabella seguente vengono brevemente descritte i pulsanti correlati a Gestione cespiti.</span><span class="sxs-lookup"><span data-stu-id="ec55b-124">The following table briefly describes the buttons that are related to Asset Management.</span></span>

| <span data-ttu-id="ec55b-125">Nome del pulsante</span><span class="sxs-lookup"><span data-stu-id="ec55b-125">Button name</span></span>                      | <span data-ttu-id="ec55b-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ec55b-126">Description</span></span> |
|----------------------------------|-------------|
| <span data-ttu-id="ec55b-127">Modifica</span><span class="sxs-lookup"><span data-stu-id="ec55b-127">Edit</span></span>                             | <span data-ttu-id="ec55b-128">Modifica la richiesta di intervento di manutenzione selezionata</span><span class="sxs-lookup"><span data-stu-id="ec55b-128">Edit the selected maintenance request.</span></span> |
| <span data-ttu-id="ec55b-129">Nuove</span><span class="sxs-lookup"><span data-stu-id="ec55b-129">New</span></span>                              | <span data-ttu-id="ec55b-130">Crea una nuova richiesta di intervento di manutenzione.</span><span class="sxs-lookup"><span data-stu-id="ec55b-130">Create a new maintenance request.</span></span> |
| <span data-ttu-id="ec55b-131">Eliminazione</span><span class="sxs-lookup"><span data-stu-id="ec55b-131">Delete</span></span>                           | <span data-ttu-id="ec55b-132">Elimina la richiesta di intervento di manutenzione selezionata.</span><span class="sxs-lookup"><span data-stu-id="ec55b-132">Delete the selected maintenance request.</span></span> |
| <span data-ttu-id="ec55b-133">Pool di ordini di lavoro</span><span class="sxs-lookup"><span data-stu-id="ec55b-133">Work order pool</span></span>                  | <span data-ttu-id="ec55b-134">Collega la richiesta di intervento di manutenzione a un pool di ordini di lavoro.</span><span class="sxs-lookup"><span data-stu-id="ec55b-134">Connect the selected maintenance request to a work order pool.</span></span> |
| <span data-ttu-id="ec55b-135">Ordine di lavoro</span><span class="sxs-lookup"><span data-stu-id="ec55b-135">Work order</span></span>                       | <span data-ttu-id="ec55b-136">Crea un ordine di lavoro basato sulla richiesta di intervento di manutenzione selezionata.</span><span class="sxs-lookup"><span data-stu-id="ec55b-136">Create a work order, based on the selected maintenance request.</span></span> |
| <span data-ttu-id="ec55b-137">Errore del cespite</span><span class="sxs-lookup"><span data-stu-id="ec55b-137">Asset fault</span></span>                      | <span data-ttu-id="ec55b-138">Fare clic su **Errori del cespite**, in cui è possibile creare una registrazione dei problemi per la richiesta di intervento di manutenzione selezionata.</span><span class="sxs-lookup"><span data-stu-id="ec55b-138">Click **Asset faults**, where you can create a fault registration on the selected maintenance request.</span></span> |
| <span data-ttu-id="ec55b-139">Ordini di lavoro</span><span class="sxs-lookup"><span data-stu-id="ec55b-139">Work orders</span></span>                      | <span data-ttu-id="ec55b-140">Consente di visualizzare un elenco di tutti gli ordini di lavoro collegati alla richiesta di intervento di manutenzione selezionata.</span><span class="sxs-lookup"><span data-stu-id="ec55b-140">Show a list of all work orders that are connected to the selected maintenance request.</span></span> |
| <span data-ttu-id="ec55b-141">Aggiorna stato della richiesta di intervento di manutenzione</span><span class="sxs-lookup"><span data-stu-id="ec55b-141">Update maintenance request state</span></span> | <span data-ttu-id="ec55b-142">Aggiorna lo stato della richiesta di intervento di manutenzione.</span><span class="sxs-lookup"><span data-stu-id="ec55b-142">Update the maintenance request state.</span></span> |
| <span data-ttu-id="ec55b-143">Registro dello stato del ciclo di vita</span><span class="sxs-lookup"><span data-stu-id="ec55b-143">Lifecycle state log</span></span>              | <span data-ttu-id="ec55b-144">Visualizza un registro contenente gli stati del ciclo di vita della richiesta di Aggiorna stato della richiesta di intervento di manutenzione selezionata.</span><span class="sxs-lookup"><span data-stu-id="ec55b-144">View a log that shows the lifecycle states of the selected maintenance request.</span></span> |
| <span data-ttu-id="ec55b-145">Dettagli richieste di intervento di manutenzione</span><span class="sxs-lookup"><span data-stu-id="ec55b-145">Maintenance request details</span></span>      | <span data-ttu-id="ec55b-146">Consente di stampare un report contenente i dettagli della richiesta di intervento di manutenzione selezionata.</span><span class="sxs-lookup"><span data-stu-id="ec55b-146">Print a report that shows details of the selected maintenance request.</span></span> |
| <span data-ttu-id="ec55b-147">Invia cespite in prestito</span><span class="sxs-lookup"><span data-stu-id="ec55b-147">Send loan asset</span></span>                  | <span data-ttu-id="ec55b-148">Seleziona un cespite di prestito che deve essere una sostituzione temporanea per il cespite selezionato nella richiesta di intervento di manutenzione selezionata.</span><span class="sxs-lookup"><span data-stu-id="ec55b-148">Select a loan asset that should be a temporary replacement for the asset that is selected on the selected maintenance request.</span></span> |
| <span data-ttu-id="ec55b-149">Restituisci cespite in prestito</span><span class="sxs-lookup"><span data-stu-id="ec55b-149">Return loan asset</span></span>                | <span data-ttu-id="ec55b-150">Registra il cespite in prestito come restituito.</span><span class="sxs-lookup"><span data-stu-id="ec55b-150">Register the loan asset as returned.</span></span> |
