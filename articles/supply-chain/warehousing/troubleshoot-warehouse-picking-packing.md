---
title: Risolvere i problemi di prelievo e imballaggio
description: Questo argomento descrive come risolvere i problemi comuni che si possono verificare durante il prelievo e l'imballaggio in Microsoft Dynamics 365 Supply Chain Management.
author: perlynne
ms.date: 10/19/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-19
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 1a54fa9dc21fb1691d74905a1215f4dfea31f136
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5828132"
---
# <a name="troubleshoot-picking-and-packing"></a><span data-ttu-id="e1e3b-103">Risolvere i problemi di prelievo e imballaggio</span><span class="sxs-lookup"><span data-stu-id="e1e3b-103">Troubleshoot picking and packing</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e1e3b-104">Questo argomento descrive come risolvere i problemi comuni che si possono verificare durante il prelievo e l'imballaggio in Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="e1e3b-104">This topic describes how to fix common issues that you might encounter while you pick and pack in Microsoft Dynamics 365 Supply Chain Management.</span></span>

## <a name="i-receive-the-following-error-message-dimension-location-cant-be-left-blank-if-dimension-serial-number-is-set"></a><span data-ttu-id="e1e3b-105">Viene visualizzato il seguente messaggio di errore: "Impossibile lasciare vuoto l'ubicazione della dimensione se è impostato il numero di serie della dimensione".</span><span class="sxs-lookup"><span data-stu-id="e1e3b-105">I receive the following error message: "Dimension location can't be left blank if dimension serial number is set."</span></span>

### <a name="issue-description"></a><span data-ttu-id="e1e3b-106">Descrizione del problema</span><span class="sxs-lookup"><span data-stu-id="e1e3b-106">Issue description</span></span>

<span data-ttu-id="e1e3b-107">Viene visualizzato questo messaggio di errore se si crea un ordine di trasferimento per un articolo con numero di serie utilizzando un magazzino abilitato per la gestione avanzata del magazzino (WMS) e quindi, al termine del lavoro, si tenta di confermare la spedizione.</span><span class="sxs-lookup"><span data-stu-id="e1e3b-107">You receive this error message if you create a transfer order for a serial item by using a warehouse that is enabled for advanced warehouse management (WMS), and then, after the work is completed, you try to confirm the shipment.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="e1e3b-108">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="e1e3b-108">Issue resolution</span></span>

<span data-ttu-id="e1e3b-109">Il campo **Ubicazione predefinita entrata** è vuoto per un magazzino di transito del magazzino di provenienza.</span><span class="sxs-lookup"><span data-stu-id="e1e3b-109">The **Default receipt location** field is blank for a transit warehouse of the "from" warehouse.</span></span> <span data-ttu-id="e1e3b-110">Per risolvere questo problema, specificare un'ubicazione di ricevimento predefinita nel magazzino di transito.</span><span class="sxs-lookup"><span data-stu-id="e1e3b-110">To fix this issue, specify a default receipt location in the transit warehouse.</span></span> <span data-ttu-id="e1e3b-111">Assicurarsi che questa ubicazione sia controllata dalla targa.</span><span class="sxs-lookup"><span data-stu-id="e1e3b-111">Make sure that this location is license plate–controlled.</span></span>

## <a name="i-receive-the-following-error-message-invalid-license-plate"></a><span data-ttu-id="e1e3b-112">Viene visualizzato il seguente messaggio di errore: "Targa non valida".</span><span class="sxs-lookup"><span data-stu-id="e1e3b-112">I receive the following error message: "Invalid license plate."</span></span>

### <a name="issue-description"></a><span data-ttu-id="e1e3b-113">Descrizione del problema</span><span class="sxs-lookup"><span data-stu-id="e1e3b-113">Issue description</span></span>

<span data-ttu-id="e1e3b-114">Viene visualizzato questo messaggio di errore nell'app per dispositivi mobili Gestione magazzino quando si esegue la scansione di un ID targa.</span><span class="sxs-lookup"><span data-stu-id="e1e3b-114">You receive this error message in the Warehouse Management mobile app when you scan a license plate ID.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="e1e3b-115">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="e1e3b-115">Issue resolution</span></span>

<span data-ttu-id="e1e3b-116">Assicurarsi che l'ID della targa sia presente nella tabella delle targhe e che gli articoli e le quantità sulla targa siano disponibili (in altre parole, non sono bloccati).</span><span class="sxs-lookup"><span data-stu-id="e1e3b-116">Make sure that the license plate ID exists in the license plates table, and that the items and quantities on the license plate are available (in other words, they aren't blocked).</span></span>

## <a name="i-receive-the-following-error-message-field-load-weight-1-can-only-contain-positive-numbers-update-has-been-canceled"></a><span data-ttu-id="e1e3b-117">Viene visualizzato il seguente messaggio di errore: "Il campo "Peso carico"(=-%1) può contenere solo numeri positivi.</span><span class="sxs-lookup"><span data-stu-id="e1e3b-117">I receive the following error message: "Field 'Load weight'(=-%1) can only contain positive numbers.</span></span> <span data-ttu-id="e1e3b-118">L'aggiornamento è stato annullato."</span><span class="sxs-lookup"><span data-stu-id="e1e3b-118">Update has been canceled."</span></span>

### <a name="issue-description"></a><span data-ttu-id="e1e3b-119">Descrizione del problema</span><span class="sxs-lookup"><span data-stu-id="e1e3b-119">Issue description</span></span>

<span data-ttu-id="e1e3b-120">Viene visualizzato questo messaggio di errore se è presente un lavoro aperto quando si elabora il lavoro da ubicazioni di imballaggio a ubicazioni di staging o da ubicazioni di staging a ubicazioni di ancoraggio.</span><span class="sxs-lookup"><span data-stu-id="e1e3b-120">You receive this error message if there is open work when you process work from packing locations to staging locations, or from staging locations to dock locations.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="e1e3b-121">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="e1e3b-121">Issue resolution</span></span>

<span data-ttu-id="e1e3b-122">Per risolvere questo problema, andare a **Amministrazione di sistema \> Attività periodiche \> Database \> Controllo coerenza** ed eseguire il processo **Controllo coerenza peso carico magazzino**.</span><span class="sxs-lookup"><span data-stu-id="e1e3b-122">To fix this issue, go to **System administration \> Periodic tasks \> Database \> Consistency check**, and run the process for **Warehouse load weight consistency check**.</span></span>

## <a name="i-receive-the-following-error-message-the-quantity-is-not-valid-for-unit-1"></a><span data-ttu-id="e1e3b-123">Viene visualizzato il seguente messaggio di errore: "La quantità non è valida per l'unità %1."</span><span class="sxs-lookup"><span data-stu-id="e1e3b-123">I receive the following error message: "The quantity is not valid for unit %1."</span></span>

### <a name="issue-description"></a><span data-ttu-id="e1e3b-124">Descrizione del problema</span><span class="sxs-lookup"><span data-stu-id="e1e3b-124">Issue description</span></span>

<span data-ttu-id="e1e3b-125">Viene visualizzato questo messaggio di errore quando si tenta di eseguire un *prelievo condiviso* su più batch.</span><span class="sxs-lookup"><span data-stu-id="e1e3b-125">You receive this error message when you try to perform a *split pick* across multiple batches.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="e1e3b-126">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="e1e3b-126">Issue resolution</span></span>

<span data-ttu-id="e1e3b-127">Il magazziniere deve utilizzare il processo *Prelievo breve* nell'app per dispositivi mobili Gestione magazzino.</span><span class="sxs-lookup"><span data-stu-id="e1e3b-127">The warehouse worker must use the *Short picking* process in the Warehouse Management mobile app.</span></span> <span data-ttu-id="e1e3b-128">Se tenti di prelevare più batch dalla stessa ubicazione, puoi anche utilizzare l'opzione **Completo** nell'app per dispositivi mobili Gestione magazzino.</span><span class="sxs-lookup"><span data-stu-id="e1e3b-128">If you're trying to pick multiple batches from the same location, you can also use the **Full** option in the app.</span></span>

## <a name="i-cant-move-inventory-to-a-location-that-is-license-platecontrolled"></a><span data-ttu-id="e1e3b-129">Non èpossibile spostare l'inventario in un'ubicazione controllata dalla targa.</span><span class="sxs-lookup"><span data-stu-id="e1e3b-129">I can't move inventory to a location that is license plate–controlled.</span></span>

### <a name="issue-description"></a><span data-ttu-id="e1e3b-130">Descrizione del problema</span><span class="sxs-lookup"><span data-stu-id="e1e3b-130">Issue description</span></span>

<span data-ttu-id="e1e3b-131">Non è possibile ridurre le quantità prelevate su un carico.</span><span class="sxs-lookup"><span data-stu-id="e1e3b-131">You can't reduce picked quantities on a load.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="e1e3b-132">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="e1e3b-132">Issue resolution</span></span>

<span data-ttu-id="e1e3b-133">Nelle versioni precedenti, non è possibile ridurre le quantità prelevate su un carico.</span><span class="sxs-lookup"><span data-stu-id="e1e3b-133">In earlier versions, you can't reduce picked quantities on a load.</span></span> <span data-ttu-id="e1e3b-134">Tuttavia, ora è possibile annullare il prelievo in un'ubicazione controllata dalla targa.</span><span class="sxs-lookup"><span data-stu-id="e1e3b-134">However, you can now unpick to a license plate–controlled location.</span></span> <span data-ttu-id="e1e3b-135">È necessario specificare un valore **Ubicazione** e un valore **Targa** per la riga di carico nella pagina **Riduci la quantità prelevata**.</span><span class="sxs-lookup"><span data-stu-id="e1e3b-135">You must specify both a **Location** value and a **License plate** value for the load line on the **Reduce picked quantity** page.</span></span>

## <a name="can-i-print-a-delivery-note-or-packing-content-by-warehouse"></a><span data-ttu-id="e1e3b-136">È possibile stampare una bolla di consegna o il contenuto di un imballaggio per magazzino?</span><span class="sxs-lookup"><span data-stu-id="e1e3b-136">Can I print a delivery note or packing content by warehouse?</span></span>

### <a name="issue-description"></a><span data-ttu-id="e1e3b-137">Descrizione del problema</span><span class="sxs-lookup"><span data-stu-id="e1e3b-137">Issue description</span></span>

<span data-ttu-id="e1e3b-138">Si desidera stampare una bolla di consegna o il contenuto di un imballaggio per magazzino o sito nella pagina **Aggiornamento della riga del modello di controllo di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="e1e3b-138">You want to print a delivery note or packing content by warehouse or site on the **Work audit template line update** page.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="e1e3b-139">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="e1e3b-139">Issue resolution</span></span>

<span data-ttu-id="e1e3b-140">Quando si stampa un documento utilizzando le impostazioni di gestione della stampa, limitare l'ambito (sito/magazzino) tramite la gestione della stampa anziché selezionando **Modifica impostazioni di stampa** nella pagina **Aggiornamento della riga del modello di controllo di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="e1e3b-140">When you print a document by using Print management settings, limit the scope (site/warehouse) through Print management instead of by selecting **Edit print settings** on the **Work audit template line update** page.</span></span>

## <a name="i-cant-cancel-a-packing-slip-after-its-posted-from-a-sales-order"></a><span data-ttu-id="e1e3b-141">Impossibile annullare un documento di trasporto dopo che è stato registrato da un ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="e1e3b-141">I can't cancel a packing slip after it's posted from a sales order.</span></span>

### <a name="issue-description"></a><span data-ttu-id="e1e3b-142">Descrizione del problema</span><span class="sxs-lookup"><span data-stu-id="e1e3b-142">Issue description</span></span>

<span data-ttu-id="e1e3b-143">Quando i processi di prelievo e spedizione sono abilitati per WMS, non è possibile annullare un documento di trasporto dopo che è stato registrato da un ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="e1e3b-143">When picking and shipping processes are enabled for WMS, you can't cancel a packing slip after it's posted from a sales order.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="e1e3b-144">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="e1e3b-144">Issue resolution</span></span>

<span data-ttu-id="e1e3b-145">Per correggere i documenti di trasporto registrati per gli articoli abilitati per WMS, la registrazione deve avvenire dal carico, non dall'ordine.</span><span class="sxs-lookup"><span data-stu-id="e1e3b-145">To correct posted packing slips for items that are enabled for WMS, the posting must occur from the load, not from the order.</span></span> <span data-ttu-id="e1e3b-146">Microsoft ha valutato questo problema e ha stabilito che si tratta di una limitazione delle funzionalità.</span><span class="sxs-lookup"><span data-stu-id="e1e3b-146">Microsoft has evaluated this issue and has determined that it's a feature limitation.</span></span> <span data-ttu-id="e1e3b-147">In generale, un ordine cliente prelevato e spedito tramite i processi di gestione del magazzino può essere aggiornato dal documento di trasporto dal carico o dalla spedizione e dal documento dell'ordine cliente stesso.</span><span class="sxs-lookup"><span data-stu-id="e1e3b-147">In general, a sales order that has been picked and shipped through warehouse management processes can be packing slip–updated from the load or shipment and the sales order document itself.</span></span> <span data-ttu-id="e1e3b-148">Tuttavia, se si aggiorna l'ordine cliente dal documento dell'ordine cliente, lo storno del documento di trasporto non può ancora essere eseguito dal carico o dall'ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="e1e3b-148">However, if you packing slip–update the sales order from the sales order document, packing slip reversal still can't be done from the load or sales order.</span></span> <span data-ttu-id="e1e3b-149">Pertanto, si consiglia di utilizzare la registrazione della bolla di accompagnamento dal carico.</span><span class="sxs-lookup"><span data-stu-id="e1e3b-149">Therefore, we recommend that you use the packing slip posting from the load.</span></span> <span data-ttu-id="e1e3b-150">In questo caso verrà abilitato lo storno che deve essere eseguito dal carico.</span><span class="sxs-lookup"><span data-stu-id="e1e3b-150">In this case, the reversal that must be done from the load will be enabled.</span></span>

## <a name="i-receive-the-following-error-message-not-enough-work-can-be-found-for-cluster"></a><span data-ttu-id="e1e3b-151">Viene visualizzato il seguente messaggio di errore: "Impossibile trovare lavoro sufficiente per il cluster".</span><span class="sxs-lookup"><span data-stu-id="e1e3b-151">I receive the following error message: "Not enough work can be found for cluster."</span></span>

### <a name="issue-description"></a><span data-ttu-id="e1e3b-152">Descrizione del problema</span><span class="sxs-lookup"><span data-stu-id="e1e3b-152">Issue description</span></span>

<span data-ttu-id="e1e3b-153">Quando si usa il processo *Prelievo cluster diretto dal sistema*, se si configura un profilo cluster in cui, ad esempio, è possibile selezionare 10 ubicazioni, il processo funziona come pianificato quando c'è abbastanza lavoro per selezionare 10 ubicazioni.</span><span class="sxs-lookup"><span data-stu-id="e1e3b-153">When you use the *System directed cluster picking* process, if you configure a cluster profile where, for example, 10 positions can be picked, the process works as planned when there is enough work to pick to 10 positions.</span></span> <span data-ttu-id="e1e3b-154">Tuttavia, se sono presenti solo otto ubicazioni da selezionare, viene visualizzato questo messaggio di errore perché non c'è lavoro sufficiente per un cluster.</span><span class="sxs-lookup"><span data-stu-id="e1e3b-154">However, if there are only eight positions to pick, you receive this error message, because there isn't enough work for one cluster.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="e1e3b-155">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="e1e3b-155">Issue resolution</span></span>

<span data-ttu-id="e1e3b-156">Per risolvere questo problema, modificare il profilo del cluster e impostare l'opzione **Attiva posizioni** su *No*.</span><span class="sxs-lookup"><span data-stu-id="e1e3b-156">To fix this issue, edit the cluster profile, and set the **Activate positions** option to *No*.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]