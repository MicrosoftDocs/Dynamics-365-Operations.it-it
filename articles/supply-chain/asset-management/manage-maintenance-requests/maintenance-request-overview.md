---
title: Richieste di intervento di manutenzione
description: In questo argomento viene fornita una panoramica sulla gestione delle richieste di intervento di manutenzione in Gestione cespiti
author: josaw1
manager: tfehr
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetRequestTable, EntAssetRequestWorkspace, EntAssetRequestActivePart, EntAssetRequestWorkOrderActive, EntAssetRequestType, EntAssetRequestTableCreateWO, EntAssetRequestTableLookup, EntAssetRequestTableActivePart, EntAssetMobileRequestDetails
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: d81fed34c1eb9ff0347c67086ceb08c038d8eb08
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5253376"
---
# <a name="maintenance-requests"></a><span data-ttu-id="0bf2d-103">Richieste di intervento di manutenzione</span><span class="sxs-lookup"><span data-stu-id="0bf2d-103">Maintenance requests</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="0bf2d-104">Le richieste di intervento di manutenzione sono note o le dichiarazioni create per informare un responsabile o un responsabile della pianificazione che un cespite può richiedere un processo di riparazione o manutenzione, ma senza creare un ordine di lavoro.</span><span class="sxs-lookup"><span data-stu-id="0bf2d-104">Maintenance requests are notes or declarations that are created to notify a manager or planner that an asset might require a maintenance or repair job, but without creating a work order.</span></span> <span data-ttu-id="0bf2d-105">Se il contenuto di una richiesta di intervento di manutenzione viene considerato valido, un ordine di lavoro può quindi essere creato in base alla richiesta di intervento di manutenzione.</span><span class="sxs-lookup"><span data-stu-id="0bf2d-105">If the contents of a maintenance request are considered valid, a work order can then be created based on the maintenance request.</span></span>

<span data-ttu-id="0bf2d-106">Le richieste di intervento di manutenzione possono essere create per qualsiasi cespite in Gestione cespiti.</span><span class="sxs-lookup"><span data-stu-id="0bf2d-106">Maintenance requests can be created for any asset in Asset Management.</span></span> <span data-ttu-id="0bf2d-107">Diversi tipi di richieste di intervento di manutenzione possono essere creati, a seconda di come la società utilizza le richieste di intervento di manutenzione.</span><span class="sxs-lookup"><span data-stu-id="0bf2d-107">Various types of maintenance requests can be created, depending on how your company uses maintenance requests.</span></span> <span data-ttu-id="0bf2d-108">Di seguito sono riportati alcuni esempi.</span><span class="sxs-lookup"><span data-stu-id="0bf2d-108">Here are some examples:</span></span>

- <span data-ttu-id="0bf2d-109">Richieste di intervento di manutenzione</span><span class="sxs-lookup"><span data-stu-id="0bf2d-109">Maintenance requests</span></span>
- <span data-ttu-id="0bf2d-110">Note</span><span class="sxs-lookup"><span data-stu-id="0bf2d-110">Notes</span></span>
- <span data-ttu-id="0bf2d-111">Correzioni o miglioramenti</span><span class="sxs-lookup"><span data-stu-id="0bf2d-111">Corrections or enhancements</span></span>
- <span data-ttu-id="0bf2d-112">Investimenti</span><span class="sxs-lookup"><span data-stu-id="0bf2d-112">Investments</span></span>
- <span data-ttu-id="0bf2d-113">Riparazione in deposito (questo tipo viene utilizzato quando si ricevono i cespiti da un'altra ubicazione in modo da poter effettuare un processo di riparazione o di manutenzione e quindi restituire il cespite dopo che il processo è completato.)</span><span class="sxs-lookup"><span data-stu-id="0bf2d-113">Depot repair (This type is used when you receive assets from another location so that you can do a maintenance or repair job, and you then return the asset after the job is completed.)</span></span>

## <a name="view-maintenance-requests"></a><span data-ttu-id="0bf2d-114">Visualizza richieste di intervento di manutenzione</span><span class="sxs-lookup"><span data-stu-id="0bf2d-114">View maintenance requests</span></span>

<span data-ttu-id="0bf2d-115">Per visualizzare le richieste di intervento di manutenzione, selezionare **Gestione cespiti** \> **Comune** \> **Richieste di intervento di manutenzione** \>, **Tutte le richieste di intervento di manutenzione**, **Richieste di intervento di manutenzione attive** o **Richieste di intervento di manutenzione delle unità funzionali personali**.</span><span class="sxs-lookup"><span data-stu-id="0bf2d-115">To view maintenance requests, select **Asset management** \> **Common** \> **Maintenance requests** \> **All maintenance requests**, **Active maintenance requests**, or **My functional location maintenance requests**.</span></span> <span data-ttu-id="0bf2d-116">Ogni pagina elenco vengono visualizzate alcune informazioni correlate a una richiesta di intervento di manutenzione.</span><span class="sxs-lookup"><span data-stu-id="0bf2d-116">Each list page shows some of the information that is related to a maintenance request.</span></span>

![Visualizza richieste di intervento di manutenzione](media/01-manage-maintenance-requests.png)

> [!NOTE]
> <span data-ttu-id="0bf2d-118">Usare la pagina elenco **Richieste di intervento di manutenzione delle unità funzionali personali** per visualizzare un elenco di richieste di intervento di manutenzione contenenti le unità funzionali a cui si è correlati come lavoratori o i cespiti installati nelle unità funzionali a cui si è correlati come lavoratore.</span><span class="sxs-lookup"><span data-stu-id="0bf2d-118">Use the **My functional location maintenance requests** list page to view a list of maintenance requests that contain either functional locations that you're related to as a worker or assets that are installed on functional locations that you're related to as a worker.</span></span> <span data-ttu-id="0bf2d-119">Per informazioni su come impostare le unità funzionali per gli addetti alla manutenzione, vedere [Addetti alla manutenzione e gruppi di lavoratori](../setup-for-objects/workers-and-worker-groups.md).</span><span class="sxs-lookup"><span data-stu-id="0bf2d-119">(For information about how to set up functional locations on maintenance workers, see [Maintenance workers and worker groups](../setup-for-objects/workers-and-worker-groups.md).)</span></span>
> 
> <span data-ttu-id="0bf2d-120">Sebbene le informazioni su un conto cliente siano disponibili in Gestione assistenza cespiti (manutenzione esterna), non sono disponibili in Gestione cespiti (manutenzione interna).</span><span class="sxs-lookup"><span data-stu-id="0bf2d-120">Although customer account information is available in Asset Service Management (external maintenance), it isn't available in Asset Management (internal maintenance).</span></span>

<span data-ttu-id="0bf2d-121">Per aprire la visualizzazione dettagli di un record, nella pagina elenco **Tutte le richieste di intervento di manutenzione**, in visualizzazione griglia, selezionare un collegamento nella colonna **Richiesta di intervento di manutenzione**.</span><span class="sxs-lookup"><span data-stu-id="0bf2d-121">To open the details view of a record, on the **All maintenance requests** list page, in the grid view, select a link in the **Maintenance request** column.</span></span>

![Visualizzare i dettagli della richiesta di intervento di manutenzione](media/02-manage-maintenance-requests.png)

<span data-ttu-id="0bf2d-123">I pulsanti del riquadro azioni sono organizzati in schede.</span><span class="sxs-lookup"><span data-stu-id="0bf2d-123">The buttons on the Action Pane are organized on tabs.</span></span> <span data-ttu-id="0bf2d-124">Nella tabella seguente vengono brevemente descritte i pulsanti correlati a Gestione cespiti.</span><span class="sxs-lookup"><span data-stu-id="0bf2d-124">The following table briefly describes the buttons that are related to Asset Management.</span></span>

| <span data-ttu-id="0bf2d-125">Nome del pulsante</span><span class="sxs-lookup"><span data-stu-id="0bf2d-125">Button name</span></span>                      | <span data-ttu-id="0bf2d-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0bf2d-126">Description</span></span> |
|----------------------------------|-------------|
| <span data-ttu-id="0bf2d-127">Modifica</span><span class="sxs-lookup"><span data-stu-id="0bf2d-127">Edit</span></span>                             | <span data-ttu-id="0bf2d-128">Modifica la richiesta di intervento di manutenzione selezionata</span><span class="sxs-lookup"><span data-stu-id="0bf2d-128">Edit the selected maintenance request.</span></span> |
| <span data-ttu-id="0bf2d-129">Nuove</span><span class="sxs-lookup"><span data-stu-id="0bf2d-129">New</span></span>                              | <span data-ttu-id="0bf2d-130">Crea una nuova richiesta di intervento di manutenzione.</span><span class="sxs-lookup"><span data-stu-id="0bf2d-130">Create a new maintenance request.</span></span> |
| <span data-ttu-id="0bf2d-131">Eliminazione</span><span class="sxs-lookup"><span data-stu-id="0bf2d-131">Delete</span></span>                           | <span data-ttu-id="0bf2d-132">Elimina la richiesta di intervento di manutenzione selezionata.</span><span class="sxs-lookup"><span data-stu-id="0bf2d-132">Delete the selected maintenance request.</span></span> |
| <span data-ttu-id="0bf2d-133">Pool di ordini di lavoro</span><span class="sxs-lookup"><span data-stu-id="0bf2d-133">Work order pool</span></span>                  | <span data-ttu-id="0bf2d-134">Collega la richiesta di intervento di manutenzione a un pool di ordini di lavoro.</span><span class="sxs-lookup"><span data-stu-id="0bf2d-134">Connect the selected maintenance request to a work order pool.</span></span> |
| <span data-ttu-id="0bf2d-135">Ordine di lavoro</span><span class="sxs-lookup"><span data-stu-id="0bf2d-135">Work order</span></span>                       | <span data-ttu-id="0bf2d-136">Crea un ordine di lavoro basato sulla richiesta di intervento di manutenzione selezionata.</span><span class="sxs-lookup"><span data-stu-id="0bf2d-136">Create a work order, based on the selected maintenance request.</span></span> |
| <span data-ttu-id="0bf2d-137">Errore del cespite</span><span class="sxs-lookup"><span data-stu-id="0bf2d-137">Asset fault</span></span>                      | <span data-ttu-id="0bf2d-138">Fare clic su **Errori del cespite**, in cui è possibile creare una registrazione dei problemi per la richiesta di intervento di manutenzione selezionata.</span><span class="sxs-lookup"><span data-stu-id="0bf2d-138">Click **Asset faults**, where you can create a fault registration on the selected maintenance request.</span></span> |
| <span data-ttu-id="0bf2d-139">Ordini di lavoro</span><span class="sxs-lookup"><span data-stu-id="0bf2d-139">Work orders</span></span>                      | <span data-ttu-id="0bf2d-140">Consente di visualizzare un elenco di tutti gli ordini di lavoro collegati alla richiesta di intervento di manutenzione selezionata.</span><span class="sxs-lookup"><span data-stu-id="0bf2d-140">Show a list of all work orders that are connected to the selected maintenance request.</span></span> |
| <span data-ttu-id="0bf2d-141">Aggiorna stato della richiesta di intervento di manutenzione</span><span class="sxs-lookup"><span data-stu-id="0bf2d-141">Update maintenance request state</span></span> | <span data-ttu-id="0bf2d-142">Aggiorna lo stato della richiesta di intervento di manutenzione.</span><span class="sxs-lookup"><span data-stu-id="0bf2d-142">Update the maintenance request state.</span></span> |
| <span data-ttu-id="0bf2d-143">Registro dello stato del ciclo di vita</span><span class="sxs-lookup"><span data-stu-id="0bf2d-143">Lifecycle state log</span></span>              | <span data-ttu-id="0bf2d-144">Visualizza un registro contenente gli stati del ciclo di vita della richiesta di Aggiorna stato della richiesta di intervento di manutenzione selezionata.</span><span class="sxs-lookup"><span data-stu-id="0bf2d-144">View a log that shows the lifecycle states of the selected maintenance request.</span></span> |
| <span data-ttu-id="0bf2d-145">Dettagli richieste di intervento di manutenzione</span><span class="sxs-lookup"><span data-stu-id="0bf2d-145">Maintenance request details</span></span>      | <span data-ttu-id="0bf2d-146">Consente di stampare un report contenente i dettagli della richiesta di intervento di manutenzione selezionata.</span><span class="sxs-lookup"><span data-stu-id="0bf2d-146">Print a report that shows details of the selected maintenance request.</span></span> |
| <span data-ttu-id="0bf2d-147">Invia cespite in prestito</span><span class="sxs-lookup"><span data-stu-id="0bf2d-147">Send loan asset</span></span>                  | <span data-ttu-id="0bf2d-148">Seleziona un cespite di prestito che deve essere una sostituzione temporanea per il cespite selezionato nella richiesta di intervento di manutenzione selezionata.</span><span class="sxs-lookup"><span data-stu-id="0bf2d-148">Select a loan asset that should be a temporary replacement for the asset that is selected on the selected maintenance request.</span></span> |
| <span data-ttu-id="0bf2d-149">Restituisci cespite in prestito</span><span class="sxs-lookup"><span data-stu-id="0bf2d-149">Return loan asset</span></span>                | <span data-ttu-id="0bf2d-150">Registra il cespite in prestito come restituito.</span><span class="sxs-lookup"><span data-stu-id="0bf2d-150">Register the loan asset as returned.</span></span> |



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]