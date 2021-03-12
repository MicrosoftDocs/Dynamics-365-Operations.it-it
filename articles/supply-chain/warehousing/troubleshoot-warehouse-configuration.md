---
title: Risolvere i problemi della configurazione del magazzino
description: Questo argomento descrive come risolvere i problemi comuni che si possono verificare durante la configurazione di Microsoft Dynamics 365 Supply Chain Management.
author: perlynne
manager: tfehr
ms.date: 10/19/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
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
ms.openlocfilehash: 09b5770190fea9591f422b61ce6deedb2b9fa790
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4994005"
---
# <a name="troubleshoot-warehouse-configuration"></a><span data-ttu-id="5fb68-103">Risolvere i problemi della configurazione del magazzino</span><span class="sxs-lookup"><span data-stu-id="5fb68-103">Troubleshoot warehouse configuration</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5fb68-104">Questo argomento descrive come risolvere i problemi comuni che si possono verificare durante la configurazione di Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="5fb68-104">This topic describes how to fix common issues that you might encounter while you configure Microsoft Dynamics 365 Supply Chain Management.</span></span>

## <a name="i-receive-the-following-error-message-the-license-plate-or-location-is-not-valid"></a><span data-ttu-id="5fb68-105">Viene visualizzato il seguente messaggio di errore: "La targa o l'ubicazione non è valida."</span><span class="sxs-lookup"><span data-stu-id="5fb68-105">I receive the following error message: "The license plate or location is not valid."</span></span>

### <a name="issue-description"></a><span data-ttu-id="5fb68-106">Descrizione del problema</span><span class="sxs-lookup"><span data-stu-id="5fb68-106">Issue description</span></span>

<span data-ttu-id="5fb68-107">Viene visualizzato questo messaggio di errore quando si esegue la scansione di un ID targa o un'ubicazione.</span><span class="sxs-lookup"><span data-stu-id="5fb68-107">You receive this error message when you scan a license plate ID or location.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="5fb68-108">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="5fb68-108">Issue resolution</span></span>

<span data-ttu-id="5fb68-109">Assicurarsi che l'ID targa non sia prenotato da qualcos'altro.</span><span class="sxs-lookup"><span data-stu-id="5fb68-109">Make sure that the license plate ID isn't reserved by something else.</span></span> <span data-ttu-id="5fb68-110">Questo problema si verificava quando il valore scansionato da un utente nell'app del magazzino era sia un'ubicazione valida che un ID targa valido.</span><span class="sxs-lookup"><span data-stu-id="5fb68-110">This issue used to occur when the value that a user scanned in the warehouse app was both a valid location and a valid license plate ID.</span></span> <span data-ttu-id="5fb68-111">Tuttavia, questo problema è stato risolto nella versione 10.0.11.</span><span class="sxs-lookup"><span data-stu-id="5fb68-111">However, this issue was resolved in version 10.0.11.</span></span>

## <a name="i-receive-the-following-error-message-license-plate-must-be-specified-for-this-location"></a><span data-ttu-id="5fb68-112">Viene visualizzato il seguente messaggio di errore: "La targa deve essere specificata per questa ubicazione."</span><span class="sxs-lookup"><span data-stu-id="5fb68-112">I receive the following error message: "License plate must be specified for this location."</span></span>

### <a name="issue-description"></a><span data-ttu-id="5fb68-113">Descrizione del problema</span><span class="sxs-lookup"><span data-stu-id="5fb68-113">Issue description</span></span>

<span data-ttu-id="5fb68-114">Viene visualizzato questo messaggio di errore se si crea un ordine di trasferimento utilizzando un magazzino abilitato per la gestione avanzata del magazzino (WMS) e quindi, al termine del lavoro, si tenta di confermare la spedizione.</span><span class="sxs-lookup"><span data-stu-id="5fb68-114">You receive this error message if you create a transfer order by using a warehouse that is enabled for advanced warehouse management (WMS), and then, after the work is completed, you try to confirm the shipment.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="5fb68-115">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="5fb68-115">Issue resolution</span></span>

<span data-ttu-id="5fb68-116">Il campo **Ubicazione predefinita entrata** è vuoto per un magazzino di transito del magazzino di provenienza.</span><span class="sxs-lookup"><span data-stu-id="5fb68-116">The **Default receipt location** field is blank for a transit warehouse of the "from" warehouse.</span></span> <span data-ttu-id="5fb68-117">Per risolvere questo problema, specificare un'ubicazione di ricevimento predefinita nel magazzino di transito.</span><span class="sxs-lookup"><span data-stu-id="5fb68-117">To fix this issue, specify a default receipt location in the transit warehouse.</span></span> <span data-ttu-id="5fb68-118">Assicurarsi che questa ubicazione sia controllata dalla targa.</span><span class="sxs-lookup"><span data-stu-id="5fb68-118">Make sure that this location is license plate–controlled.</span></span>

## <a name="i-receive-the-following-error-message-you-cant-create-a-work-template-line-for-inventory-status-change-because-the-work-type-is-not-valid-select-a-different-work-type"></a><span data-ttu-id="5fb68-119">Viene visualizzato il seguente messaggio di errore: "Impossibile creare una riga del modello di lavoro per la modifica dello stato dell'inventario perché il tipo di lavoro non è valido.</span><span class="sxs-lookup"><span data-stu-id="5fb68-119">I receive the following error message: "You can't create a work template line for Inventory status change because the work type is not valid.</span></span> <span data-ttu-id="5fb68-120">Selezionare un tipo di lavoro diverso."</span><span class="sxs-lookup"><span data-stu-id="5fb68-120">Select a different work type."</span></span>

### <a name="issue-description"></a><span data-ttu-id="5fb68-121">Descrizione del problema</span><span class="sxs-lookup"><span data-stu-id="5fb68-121">Issue description</span></span>

<span data-ttu-id="5fb68-122">Per un modello di lavoro, non è possibile selezionare *Modifica stato inventario* nella colonna **Tipo di lavoro** della sezione **Dettagli modello di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="5fb68-122">For a work template, you can't select *Inventory status change* in the **Work type** column of the **Work template details** section.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="5fb68-123">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="5fb68-123">Issue resolution</span></span>

<span data-ttu-id="5fb68-124">Questo comportamento è predefinito.</span><span class="sxs-lookup"><span data-stu-id="5fb68-124">This behavior is by design.</span></span> <span data-ttu-id="5fb68-125">Il tipo di lavoro *Modifica stato inventario* viene utilizzato solo dai processi di sistema.</span><span class="sxs-lookup"><span data-stu-id="5fb68-125">The *Inventory status change* work type is used only by system processes.</span></span> <span data-ttu-id="5fb68-126">Non può essere configurato.</span><span class="sxs-lookup"><span data-stu-id="5fb68-126">It can't be configured.</span></span> <span data-ttu-id="5fb68-127">Poiché l'elenco dei tipi di lavoro è fisso come un'enumerazione, le voci aggiuntive non possono essere filtrate dal menu a discesa **Tipo di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="5fb68-127">Because the list of work types is fixed as an enumeration, the extra entries can't be filtered out of the **Work type** drop-down menu.</span></span>

## <a name="i-receive-the-following-error-message-the-quantity-is-not-valid-for-unit-1"></a><span data-ttu-id="5fb68-128">Viene visualizzato il seguente messaggio di errore: "La quantità non è valida per l'unità 1%."</span><span class="sxs-lookup"><span data-stu-id="5fb68-128">I receive the following error message: "The Quantity is not valid for unit 1%."</span></span>

### <a name="issue-description"></a><span data-ttu-id="5fb68-129">Descrizione del problema</span><span class="sxs-lookup"><span data-stu-id="5fb68-129">Issue description</span></span>

<span data-ttu-id="5fb68-130">La quantità non è valida per l'unitp *ea* quando è in corso un lavoro di prelievo con più targhe in un'unica ubicazione.</span><span class="sxs-lookup"><span data-stu-id="5fb68-130">The quantity isn't valid for the *ea* unit when there is picking work that has multiple license plates in one location.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="5fb68-131">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="5fb68-131">Issue resolution</span></span>

<span data-ttu-id="5fb68-132">Verificare che i campi **ID gruppo sequenza unità** e **Conversioni unità** del prodotto o della variante di prodotto rilasciato siano impostati correttamente.</span><span class="sxs-lookup"><span data-stu-id="5fb68-132">Verify that the **Unit sequence group ID** and **Unit conversions** fields on the released product or product variant are set correctly.</span></span>

<span data-ttu-id="5fb68-133">Notare che il messaggio di errore è stato migliorato nella versione 10.0.15 (vedere [KB 4581627](https://fix.lcs.dynamics.com/Issue/Details/?bugId=486531)).</span><span class="sxs-lookup"><span data-stu-id="5fb68-133">Note that the error message has been improved in version 10.0.15 (see [KB 4581627](https://fix.lcs.dynamics.com/Issue/Details/?bugId=486531)).</span></span> <span data-ttu-id="5fb68-134">Il nuovo messaggio di errore è "La quantità non è valida.</span><span class="sxs-lookup"><span data-stu-id="5fb68-134">The new error message is, "The quantity is not valid.</span></span> <span data-ttu-id="5fb68-135">Previsto %1 %2."</span><span class="sxs-lookup"><span data-stu-id="5fb68-135">Expected %1 %2."</span></span>

## <a name="in-location-directives-for-sales-order-put-work-the-multiple-sku-option-doesnt-evaluate-multiple-location-directive-actions"></a><span data-ttu-id="5fb68-136">Nelle direttive di ubicazione per il lavoro di stoccaggio degli ordini cliente, l'opzione più SKU non valuta più azioni delle direttive di ubicazione.</span><span class="sxs-lookup"><span data-stu-id="5fb68-136">In location directives for sales order put work, the multiple SKU option doesn't evaluate multiple location directive actions.</span></span>

### <a name="issue-description"></a><span data-ttu-id="5fb68-137">Descrizione del problema</span><span class="sxs-lookup"><span data-stu-id="5fb68-137">Issue description</span></span>

<span data-ttu-id="5fb68-138">Le direttive di ubicazione del tipo di ordine di lavoro *Ordini cliente* e il tipo di lavoro *Stoccaggio* non valutano più azioni della direttiva di ubicazione quando l'opzione **Più SKU** è selezionata.</span><span class="sxs-lookup"><span data-stu-id="5fb68-138">Location directives of the *Sales orders* work order type and the *Put* work type don't evaluate multiple location directive actions when the **Multiple SKU** option is selected.</span></span> <span data-ttu-id="5fb68-139">Viene valutata solo la prima azione della direttiva di ubicazione.</span><span class="sxs-lookup"><span data-stu-id="5fb68-139">Only the first location directive action is evaluated.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="5fb68-140">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="5fb68-140">Issue resolution</span></span>

<span data-ttu-id="5fb68-141">Una nuova funzionalità, *Valuta tutte le azioni per le direttive di ubicazione per più SKU*, è stato aggiunta nella versione 10.0.15 (vedere [KB 4579866](https://fix.lcs.dynamics.com/Issue/Details?kb=4579866&bugId=475946&dbType=3&qc=1bc41a56de7a3ee419fa76397a6bf282fce5be9b93e427c08a6d916d1dfa3091)).</span><span class="sxs-lookup"><span data-stu-id="5fb68-141">A new feature, *Evaluate all actions for Multi SKU location directives*, has been added in version 10.0.15 (see [KB 4579866](https://fix.lcs.dynamics.com/Issue/Details?kb=4579866&bugId=475946&dbType=3&qc=1bc41a56de7a3ee419fa76397a6bf282fce5be9b93e427c08a6d916d1dfa3091)).</span></span> <span data-ttu-id="5fb68-142">Questa funzionalità valuta tutte le azioni per le direttive di ubicazioni per più SKU.</span><span class="sxs-lookup"><span data-stu-id="5fb68-142">This feature evaluates all actions for multi-SKU location directives.</span></span> <span data-ttu-id="5fb68-143">Se è necessaria questa funzione, usare [Gestione delle funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) per attivarla.</span><span class="sxs-lookup"><span data-stu-id="5fb68-143">If you require this feature, use [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) to turn it on.</span></span>

## <a name="i-cant-use-the-warehouse-app-to-do-partial-picking"></a><span data-ttu-id="5fb68-144">Impossibile utilizzare l'app del magazzino per effettuare prelievi parziali.</span><span class="sxs-lookup"><span data-stu-id="5fb68-144">I can't use the warehouse app to do partial picking.</span></span>

### <a name="issue-description"></a><span data-ttu-id="5fb68-145">Descrizione del problema</span><span class="sxs-lookup"><span data-stu-id="5fb68-145">Issue description</span></span>

<span data-ttu-id="5fb68-146">Per gli ordini cliente e di trasferimento, non è possibile ignorare gli articoli ed eseguire prelievi parziali.</span><span class="sxs-lookup"><span data-stu-id="5fb68-146">For sales and transfer orders, you can't skip items and do partial picking.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="5fb68-147">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="5fb68-147">Issue resolution</span></span>

<span data-ttu-id="5fb68-148">Nella pagina **Voci di menu del dispositivo mobile**, per ciascuna voce di menu impostata per elaborare ordini cliente o ordini di trasferimento, impostare l'opzione **Consenti suddivisione del lavoro** nella scheda dettaglio **Generale** su *Sì*.</span><span class="sxs-lookup"><span data-stu-id="5fb68-148">On the **Mobile device menu items** page, for each menu item that is set up to process sales orders or transfer orders, set the **Allow splitting of work** option on the **General** FastTab to *Yes*.</span></span>

## <a name="how-can-i-do-an-inventory-status-change-for-partial-quantity-work"></a><span data-ttu-id="5fb68-149">Come si modifica lo stato dell'inventario per il lavoro con quantità parziale?</span><span class="sxs-lookup"><span data-stu-id="5fb68-149">How can I do an inventory status change for partial quantity work?</span></span>

### <a name="issue-description"></a><span data-ttu-id="5fb68-150">Descrizione del problema</span><span class="sxs-lookup"><span data-stu-id="5fb68-150">Issue description</span></span>

<span data-ttu-id="5fb68-151">Si desidera modificare lo stato dell'inventario per una quantità parziale di un batch.</span><span class="sxs-lookup"><span data-stu-id="5fb68-151">You want to do an inventory status change for a partial quantity of a batch.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="5fb68-152">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="5fb68-152">Issue resolution</span></span>

<span data-ttu-id="5fb68-153">Per consentire ai lavoratori di apportare questa modifica, è possibile creare una voce di menu per l'app del magazzino.</span><span class="sxs-lookup"><span data-stu-id="5fb68-153">To enable workers to make this change, you can create a menu item for the warehouse app.</span></span> <span data-ttu-id="5fb68-154">Creare o modificare una voce di menu per una delle seguenti impostazioni nella pagina **Voci di menu del dispositivo mobile**:</span><span class="sxs-lookup"><span data-stu-id="5fb68-154">On the **Mobile device menu items** page, create (or edit) a menu item that has the following settings:</span></span>

- <span data-ttu-id="5fb68-155">**Modalità:** *Lavoro*</span><span class="sxs-lookup"><span data-stu-id="5fb68-155">**Mode:** *Work*</span></span>
- <span data-ttu-id="5fb68-156">**Utilizza lavoro esistente:** *No*</span><span class="sxs-lookup"><span data-stu-id="5fb68-156">**Use existing work:** *No*</span></span>
- <span data-ttu-id="5fb68-157">**Processo di creazione lavoro:** *Spostamento*</span><span class="sxs-lookup"><span data-stu-id="5fb68-157">**Work creation process:** *Movement*</span></span>
- <span data-ttu-id="5fb68-158">**Visualizza stato inventario:** *Sì*</span><span class="sxs-lookup"><span data-stu-id="5fb68-158">**Display inventory status:** *Yes*</span></span>

<span data-ttu-id="5fb68-159">È possibile impostare altri campi nella pagina in base alle proprie esigenze.</span><span class="sxs-lookup"><span data-stu-id="5fb68-159">You can set other fields on the page as you require.</span></span>
