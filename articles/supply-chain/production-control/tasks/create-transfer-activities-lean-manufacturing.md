---
title: Creare le attività di trasferimento per la lean manufacturing
description: Creare un'attività di trasferimento per lean manufacturing
author: cvocph
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LeanProductionFlow, PlanActivity, PlanActivityWizard, LeanWorkCellLookup, InventLocationIdLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2925833aceba0cffe46b3a44c5d19c87cd3736e7
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4430859"
---
# <a name="create-transfer-activities-for-lean-manufacturing"></a><span data-ttu-id="290f2-103">Creare le attività di trasferimento per la lean manufacturing</span><span class="sxs-lookup"><span data-stu-id="290f2-103">Create transfer activities for lean manufacturing</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="290f2-104">Creare un'attività di trasferimento per lean manufacturing</span><span class="sxs-lookup"><span data-stu-id="290f2-104">Create a transfer activity for lean manufacturing.</span></span> 

<span data-ttu-id="290f2-105">Prerequisiti:</span><span class="sxs-lookup"><span data-stu-id="290f2-105">Prerequisites:</span></span> 

1. <span data-ttu-id="290f2-106">Un flusso di produzione e una versione non attiva devono essere creati.</span><span class="sxs-lookup"><span data-stu-id="290f2-106">A production flow and version that is not active must be created.</span></span>

2. <span data-ttu-id="290f2-107">Il magazzino e le ubicazioni di origine e di destinazione devono essere creati.</span><span class="sxs-lookup"><span data-stu-id="290f2-107">The from and to warehouse and locations must be created.</span></span> <span data-ttu-id="290f2-108">Facoltativamente, la cella di lavoro di rifornimento o rifornita deve essere creata.</span><span class="sxs-lookup"><span data-stu-id="290f2-108">Optionally, the replenishing or the replenished work cell should be created.</span></span>


## <a name="find-the-production-flow-version"></a><span data-ttu-id="290f2-109">Trovare la versione del flusso di produzione</span><span class="sxs-lookup"><span data-stu-id="290f2-109">Find the production flow version</span></span>
1. <span data-ttu-id="290f2-110">Andare a Controllo produzione > Impostazioni > Flusso di produzione snella > Flussi di produzione.</span><span class="sxs-lookup"><span data-stu-id="290f2-110">Go to Production control > Setup > Lean production flow > Production flows.</span></span>
2. <span data-ttu-id="290f2-111">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="290f2-111">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="290f2-112">Si noti che il flusso di produzione deve avere una versione in stato bozza.</span><span class="sxs-lookup"><span data-stu-id="290f2-112">Note that the production flow must have a version in draft status.</span></span>  
3. <span data-ttu-id="290f2-113">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="290f2-113">In the list, click the link in the selected row.</span></span>

## <a name="create-a-new-activity"></a><span data-ttu-id="290f2-114">Creare una nuova attività</span><span class="sxs-lookup"><span data-stu-id="290f2-114">Create a new activity</span></span>
1. <span data-ttu-id="290f2-115">Fare clic su Attività.</span><span class="sxs-lookup"><span data-stu-id="290f2-115">Click Activities.</span></span>
    * <span data-ttu-id="290f2-116">Verificare che il flusso di produzione selezionato abbia una versione in bozza e selezionare tale versione.</span><span class="sxs-lookup"><span data-stu-id="290f2-116">Ensure that the selected production flow has a version in draft and select that version.</span></span>  
2. <span data-ttu-id="290f2-117">Fare clic su Crea nuova attività piano.</span><span class="sxs-lookup"><span data-stu-id="290f2-117">Click Create new plan activity.</span></span>
3. <span data-ttu-id="290f2-118">Scegliere Avanti.</span><span class="sxs-lookup"><span data-stu-id="290f2-118">Click Next.</span></span>
4. <span data-ttu-id="290f2-119">Digitare un valore nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="290f2-119">In the Name field, type a value.</span></span>
5. <span data-ttu-id="290f2-120">Selezionare 'Trasferimento' nel campo Tipo di attività.</span><span class="sxs-lookup"><span data-stu-id="290f2-120">In the Activity type field, select 'Transfer'.</span></span>
6. <span data-ttu-id="290f2-121">Nel campo Quantità di lavorazione immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="290f2-121">In the Process quantity field, enter a number.</span></span>
7. <span data-ttu-id="290f2-122">Scegliere Avanti.</span><span class="sxs-lookup"><span data-stu-id="290f2-122">Click Next.</span></span>

## <a name="select-the-work-cells"></a><span data-ttu-id="290f2-123">Selezionare le celle di lavoro</span><span class="sxs-lookup"><span data-stu-id="290f2-123">Select the Work cells</span></span>
1. <span data-ttu-id="290f2-124">Nel campo Rifornimento fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="290f2-124">In the Replenishing field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="290f2-125">Per utilizzare l'ubicazione di uscita della cella di lavoro come ubicazione di origine nell'attività di trasferimento, selezionare una cella di lavoro.</span><span class="sxs-lookup"><span data-stu-id="290f2-125">To use the work cell output location as the from location in the transfer activity, select a work cell.</span></span> <span data-ttu-id="290f2-126">Lo stesso può essere effettuato con la cella di lavoro rifornita, che imposta l'ubicazione di destinazione dell'attività di trasferimento.</span><span class="sxs-lookup"><span data-stu-id="290f2-126">The same can be done with the replenished work cell, which sets the target location of the transfer activity.</span></span>  
2. <span data-ttu-id="290f2-127">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="290f2-127">In the list, click the link in the selected row.</span></span>

## <a name="define-the-inventory-updates"></a><span data-ttu-id="290f2-128">Definire gli aggiornamenti di inventario</span><span class="sxs-lookup"><span data-stu-id="290f2-128">Define the inventory updates</span></span>
1. <span data-ttu-id="290f2-129">Nel campo Tipo di prodotto selezionare un'opzione.</span><span class="sxs-lookup"><span data-stu-id="290f2-129">In the Product type field, select an option.</span></span>
    * <span data-ttu-id="290f2-130">Si noti che un trasferimento non modifica il tipo di prodotto.</span><span class="sxs-lookup"><span data-stu-id="290f2-130">Note that a transfer does not change the type of product.</span></span> <span data-ttu-id="290f2-131">È possibile trasferire i prodotti finiti o i prodotti semilavorati (trasferimento tra due attività del flusso di produzione ed eventualemnte un flusso kanban).</span><span class="sxs-lookup"><span data-stu-id="290f2-131">You can transfer finished products or semi-finished products (transfer between two activities of a production flow and possibly a kanban flow).</span></span>     <span data-ttu-id="290f2-132">Nel trasferimento dei prodotti finiti, è possibile scegliere se prelevare o ricevere i risultati in una transazione di magazzino.</span><span class="sxs-lookup"><span data-stu-id="290f2-132">When transferring finished products, you can select if picking or receiving results in an inventory transaction.</span></span>  

## <a name="define-the-transfer-locations"></a><span data-ttu-id="290f2-133">Definire le ubicazioni di trasferimento</span><span class="sxs-lookup"><span data-stu-id="290f2-133">Define the transfer locations</span></span>
1. <span data-ttu-id="290f2-134">Scegliere Avanti.</span><span class="sxs-lookup"><span data-stu-id="290f2-134">Click Next.</span></span>
2. <span data-ttu-id="290f2-135">Nel campo Magazzino fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="290f2-135">In the Warehouse field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="290f2-136">Trovare e selezionare il record desiderato nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="290f2-136">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="290f2-137">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="290f2-137">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="290f2-138">Nel campo Ubicazione fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="290f2-138">In the Location field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="290f2-139">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="290f2-139">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="290f2-140">Nel campo Noleggiato da, selezionare 'Spedizioniere'.</span><span class="sxs-lookup"><span data-stu-id="290f2-140">In the Freighted by field, select 'Shipper'.</span></span>
    * <span data-ttu-id="290f2-141">Le opzioni includono: Spedizioniere: l'organizzazione che gestisce il magazzino di spedizione, Destinatario: l'organizzazione che gestisce il magazzino ricevente, Vettore: un fornitore di terze parti.</span><span class="sxs-lookup"><span data-stu-id="290f2-141">Options include: Shipper - the organization operating the shipping warehouse, Recipient -  the organization operating the receiving warehouse, Carrier - a third party vendor.</span></span> <span data-ttu-id="290f2-142">Se l'organizzazione è un fornitore, l'attività di trasferimento richiede un contratto di conto lavoro.</span><span class="sxs-lookup"><span data-stu-id="290f2-142">If the operating organization is a vendor, the transfer activity requires a subcontracting agreement.</span></span>  
8. <span data-ttu-id="290f2-143">Scegliere Avanti.</span><span class="sxs-lookup"><span data-stu-id="290f2-143">Click Next.</span></span>

## <a name="define-the-activity-times"></a><span data-ttu-id="290f2-144">Definire gli orari per le attività</span><span class="sxs-lookup"><span data-stu-id="290f2-144">Define the activity times</span></span>
1. <span data-ttu-id="290f2-145">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="290f2-145">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="290f2-146">La definizione di un runtime è richiesta.</span><span class="sxs-lookup"><span data-stu-id="290f2-146">The definition of a Runtime is required.</span></span> <span data-ttu-id="290f2-147">Il runtime viene utilizzato per calcolare i costi e i tempi di lavorazione dei processi kanban.</span><span class="sxs-lookup"><span data-stu-id="290f2-147">The Runtime is used to calculate cost and the throughput times of the kanban jobs.</span></span> <span data-ttu-id="290f2-148">I runtime non vengono utilizzati per calcolare il carico di capacità e il consumo, che viene calcolato in base alla durata ciclo, derivata dall'attività della versione del flusso di produzione.</span><span class="sxs-lookup"><span data-stu-id="290f2-148">Runtimes are not used to calculate capacity load and consumption, which is calculated by cycle time, derived from the production flow version task.</span></span>  
2. <span data-ttu-id="290f2-149">Immettere un numero nel campo Tempo.</span><span class="sxs-lookup"><span data-stu-id="290f2-149">In the Time field, enter a number.</span></span>
3. <span data-ttu-id="290f2-150">Digitare un valore nel campo Unità.</span><span class="sxs-lookup"><span data-stu-id="290f2-150">In the Unit field, type a value.</span></span>
4. <span data-ttu-id="290f2-151">Selezionare l'unità di tempo.</span><span class="sxs-lookup"><span data-stu-id="290f2-151">Select the Time unit.</span></span>
5. <span data-ttu-id="290f2-152">Nel campo Per quantità immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="290f2-152">In the Per quantity field, enter a number.</span></span>
6. <span data-ttu-id="290f2-153">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="290f2-153">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="290f2-154">I tempi di attesa sono facoltativi.</span><span class="sxs-lookup"><span data-stu-id="290f2-154">Queue times are optional.</span></span>  
7. <span data-ttu-id="290f2-155">Immettere un numero nel campo Tempo.</span><span class="sxs-lookup"><span data-stu-id="290f2-155">In the Time field, enter a number.</span></span>
8. <span data-ttu-id="290f2-156">Digitare un valore nel campo Unità.</span><span class="sxs-lookup"><span data-stu-id="290f2-156">In the Unit field, type a value.</span></span>
9. <span data-ttu-id="290f2-157">Selezionare l'unità di tempo.</span><span class="sxs-lookup"><span data-stu-id="290f2-157">Select the Time unit.</span></span>
10. <span data-ttu-id="290f2-158">Nel campo Per quantità immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="290f2-158">In the Per quantity field, enter a number.</span></span>
11. <span data-ttu-id="290f2-159">Scegliere Avanti.</span><span class="sxs-lookup"><span data-stu-id="290f2-159">Click Next.</span></span>
12. <span data-ttu-id="290f2-160">Scegliere Fine.</span><span class="sxs-lookup"><span data-stu-id="290f2-160">Click Finish.</span></span>
13. <span data-ttu-id="290f2-161">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="290f2-161">Close the page.</span></span>

