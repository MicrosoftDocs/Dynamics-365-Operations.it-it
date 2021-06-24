---
title: Non è possibile confermare una spedizione a causa di lavoro incompleto o mancante
description: Non è possibile confermare una spedizione a causa di lavoro incompleto o mancante
author: perlynne
ms.date: 04/21/2021
ms.topic: troubleshooting
ms.search.form: WHSLoadTable_WHSShipConfirm,WHSLoadPlanningListPage_WHSShipConfirm,WHSLoadPlanningWorkbench_WHSShipConfirm,WHSTransportLoad_WHSShipConfirm,WHSShipPlanningListPage_WHSShipConfirm,WHSShipmentDetails_WHSShipConfirm,WHSWorkTable_WHSShipConfirm,WHSWorkTableListPage_WHSShipConfirm,Dialog_WHSOutboundShipConfirmController_WHSOutboundShipConfirm, WHSContainerCloseDiag_WHSShipConfirm
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: lbc
ms.search.validFrom: 2021-04-21
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: beef0909d41e69f3e7bcc1021527be35b7e6fd44
ms.sourcegitcommit: c2c6d687a89bc1534c029109315c23e92865b63b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/31/2021
ms.locfileid: "6123845"
---
# <a name="you-cant-confirm-a-shipment-because-of-incomplete-or-missing-work"></a><span data-ttu-id="e1159-103">Non è possibile confermare una spedizione a causa di lavoro incompleto o mancante</span><span class="sxs-lookup"><span data-stu-id="e1159-103">You can't confirm a shipment because of incomplete or missing work</span></span>

<span data-ttu-id="e1159-104">Codice errore: WAX515</span><span class="sxs-lookup"><span data-stu-id="e1159-104">Error code: WAX515</span></span>

## <a name="symptoms"></a><span data-ttu-id="e1159-105">Sintomi</span><span class="sxs-lookup"><span data-stu-id="e1159-105">Symptoms</span></span>

<span data-ttu-id="e1159-106">Quando si tenta di confermare una spedizione, il sistema mostra il seguente messaggio di errore:</span><span class="sxs-lookup"><span data-stu-id="e1159-106">When you try to confirm a shipment, the system shows the following error message:</span></span>

> <span data-ttu-id="e1159-107">Impossibile confermare la spedizione per il carico %1 perché tutto il lavoro per il carico deve essere completato.</span><span class="sxs-lookup"><span data-stu-id="e1159-107">The shipment for load %1 could not be confirmed because all work for the load must be complete.</span></span>

<span data-ttu-id="e1159-108">Pertanto, non è possibile confermare la spedizione per il carico.</span><span class="sxs-lookup"><span data-stu-id="e1159-108">Therefore, you can't confirm the shipment for the load.</span></span>

## <a name="cause"></a><span data-ttu-id="e1159-109">Causa</span><span class="sxs-lookup"><span data-stu-id="e1159-109">Cause</span></span>

<span data-ttu-id="e1159-110">Il carico o la spedizione si trova attualmente in uno stato in cui la conferma della spedizione non riesce.</span><span class="sxs-lookup"><span data-stu-id="e1159-110">The load or shipment is currently in a state where shipment confirmation fails.</span></span> <span data-ttu-id="e1159-111">Prima di poter confermare la spedizione, deve esistere almeno del lavoro per il carico e tutto quel lavoro deve avere uno stato di *Chiuso* o *Annullato*.</span><span class="sxs-lookup"><span data-stu-id="e1159-111">Before you can confirm the shipment, at least some work must exist for the load, and all that work must have a status of *Closed* or *Canceled*.</span></span>

## <a name="resolution"></a><span data-ttu-id="e1159-112">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="e1159-112">Resolution</span></span>

<span data-ttu-id="e1159-113">Controllare gli ordini cliente o gli ordini di trasferimento correlati per il carico o la spedizione e assicurarsi che tutto il lavoro correlato sia stato completato o annullato.</span><span class="sxs-lookup"><span data-stu-id="e1159-113">Check the related sales orders or transfer orders for the load or shipment, and make sure that all the related work has been completed or canceled.</span></span>

<span data-ttu-id="e1159-114">Puoi lavorare con spedizioni e carichi su più pagine.</span><span class="sxs-lookup"><span data-stu-id="e1159-114">You can work with shipments and loads on several pages.</span></span> <span data-ttu-id="e1159-115">Le seguenti sottosezioni forniscono alcuni esempi.</span><span class="sxs-lookup"><span data-stu-id="e1159-115">The following subsections provide a few examples.</span></span>

### <a name="all-loads-page"></a><span data-ttu-id="e1159-116">Pagina Tutti i carichi</span><span class="sxs-lookup"><span data-stu-id="e1159-116">All loads page</span></span>

1. <span data-ttu-id="e1159-117">Passare a **Gestione magazzino \> Carichi \> Tutti i carichi**.</span><span class="sxs-lookup"><span data-stu-id="e1159-117">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="e1159-118">Seleziona il carico per cui la spedizione non può essere confermata.</span><span class="sxs-lookup"><span data-stu-id="e1159-118">Select the load that the shipment can't be confirmed for.</span></span>
1. <span data-ttu-id="e1159-119">Nella scheda **Carichi** del riquadro azioni, nel gruppo **Informazioni correlate**, selezionare **Lavoro**.</span><span class="sxs-lookup"><span data-stu-id="e1159-119">On the Action Pane, on the **Loads** tab, in the **Related information** group, select **Work**.</span></span>
1. <span data-ttu-id="e1159-120">Controlla lo stato di ogni ID lavoro.</span><span class="sxs-lookup"><span data-stu-id="e1159-120">Inspect the status of each work ID.</span></span> <span data-ttu-id="e1159-121">Esegui il follow-up su ogni ID lavoro che non ha uno stato di *Chiuso* o *Annullato*.</span><span class="sxs-lookup"><span data-stu-id="e1159-121">Follow up on each work ID that doesn't have a status of *Closed* or *Canceled*.</span></span>
1. <span data-ttu-id="e1159-122">Quando ogni ID lavoro ha uno stato di *Chiuso* o *Annullato*, riprova per confermare la spedizione.</span><span class="sxs-lookup"><span data-stu-id="e1159-122">When every work ID has a status of *Closed* or *Canceled*, try again to confirm the shipment.</span></span>

### <a name="all-shipments-page"></a><span data-ttu-id="e1159-123">Pagina Tutte le spedizioni</span><span class="sxs-lookup"><span data-stu-id="e1159-123">All shipments page</span></span>

1. <span data-ttu-id="e1159-124">Vai a **Gestione magazzino \> Spedizioni \> Tutte le spedizioni**.</span><span class="sxs-lookup"><span data-stu-id="e1159-124">Go to **Warehouse management \> Shipments\> All shipments**.</span></span>
1. <span data-ttu-id="e1159-125">Seleziona la spedizione che non può essere confermata.</span><span class="sxs-lookup"><span data-stu-id="e1159-125">Select the shipment that can't be confirmed.</span></span>
1. <span data-ttu-id="e1159-126">Nella scheda **Spedizioni** del riquadro azioni, nel gruppo **Lavoro**, selezionare **Dettagli lavoro**.</span><span class="sxs-lookup"><span data-stu-id="e1159-126">On the Action Pane, on the **Shipments** tab, in the **Work** group, select **Work details**.</span></span>
1. <span data-ttu-id="e1159-127">Controlla lo stato di ogni ID lavoro.</span><span class="sxs-lookup"><span data-stu-id="e1159-127">Inspect the status of each work ID.</span></span> <span data-ttu-id="e1159-128">Esegui il follow-up su ogni ID lavoro che non ha uno stato di *Chiuso* o *Annullato*.</span><span class="sxs-lookup"><span data-stu-id="e1159-128">Follow up on each work ID that doesn't have a status of *Closed* or *Canceled*.</span></span>
1. <span data-ttu-id="e1159-129">Quando ogni ID lavoro ha uno stato di *Chiuso* o *Annullato*, riprova per confermare la spedizione.</span><span class="sxs-lookup"><span data-stu-id="e1159-129">When every work ID has a status of *Closed* or *Canceled*, try again to confirm the shipment.</span></span>

### <a name="all-work-page"></a><span data-ttu-id="e1159-130">Pagina Tutti i lavori</span><span class="sxs-lookup"><span data-stu-id="e1159-130">All work page</span></span>

1. <span data-ttu-id="e1159-131">Vai a **Gestione magazzino \> Lavoro \> Tutti i lavori**.</span><span class="sxs-lookup"><span data-stu-id="e1159-131">Go to **Warehouse management \> Work\> All work**.</span></span>
1. <span data-ttu-id="e1159-132">Seleziona il lavoro per il numero d'ordine per cui la spedizione non può essere confermata.</span><span class="sxs-lookup"><span data-stu-id="e1159-132">Select the work for the order number that the shipment can't be confirmed for.</span></span>
1. <span data-ttu-id="e1159-133">Nel riquadro azioni, nella scheda **Spedizione**, nel gruppo **Spedizione** selezionare **Conferma spedizione**.</span><span class="sxs-lookup"><span data-stu-id="e1159-133">On the Action Pane, on the **Shipment** tab, in the **Shipment** group, select **Confirm shipment**.</span></span>
1. <span data-ttu-id="e1159-134">Controlla lo stato di ogni ID lavoro.</span><span class="sxs-lookup"><span data-stu-id="e1159-134">Inspect the status of each work ID.</span></span> <span data-ttu-id="e1159-135">Esegui il follow-up su ogni ID lavoro che non ha uno stato di *Chiuso* o *Annullato*.</span><span class="sxs-lookup"><span data-stu-id="e1159-135">Follow up on each work ID that doesn't have a status of *Closed* or *Canceled*.</span></span>
1. <span data-ttu-id="e1159-136">Quando ogni ID lavoro ha uno stato di *Chiuso* o *Annullato*, riprova per confermare la spedizione.</span><span class="sxs-lookup"><span data-stu-id="e1159-136">When every work ID has a status of *Closed* or *Canceled*, try again to confirm the shipment.</span></span>
