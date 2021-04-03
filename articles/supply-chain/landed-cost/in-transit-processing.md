---
title: Elaborazione merci in transito
description: In questo argomento viene descritto come utilizzare gli ordini merci in transito. Quando un ordine o un viaggio viene configurato per utilizzare l'elaborazione merci in transito, le merci possono essere fatturate prima di essere ricevute nel magazzino per l'utilizzo.
author: sherry-zheng
manager: tfehr
ms.date: 01/13/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DeliveryTerms, InventLocation, InventPosting, ITMGoodsInTransitOrder, ITMTableListPage, ITMTable, ITMContainersListPage, ITMContainers, ITMFolioTableListPage, ITMFolioTable, ITMGoodsInTransitOrderEditLines, SysOperationTemplateForm, WHSRFMenuItem, WHSLocDirTable, WHSWorkTemplateTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-01-13
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: 77e30f8679c9422e895432c023997b5ff4768ebd
ms.sourcegitcommit: 2b4809e60974e72df9476ffd62706b1bfc8da4a7
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/04/2021
ms.locfileid: "5500406"
---
# <a name="goods-in-transit-processing"></a><span data-ttu-id="02cc4-104">Elaborazione merci in transito</span><span class="sxs-lookup"><span data-stu-id="02cc4-104">Goods-in-transit processing</span></span>

[!include [banner](../../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="02cc4-105">In questo argomento viene descritto come utilizzare gli ordini merci in transito.</span><span class="sxs-lookup"><span data-stu-id="02cc4-105">This topic describes how to work with goods-in-transit orders.</span></span> <span data-ttu-id="02cc4-106">Questo tipo di ordine viene utilizzato solo nel modulo **Costo sbarcato**.</span><span class="sxs-lookup"><span data-stu-id="02cc4-106">This type of order is used only by the **Landed cost** module.</span></span> <span data-ttu-id="02cc4-107">Quando un ordine o un viaggio viene configurato per utilizzare l'elaborazione merci in transito, non è necessario attendere il ricevimento delle merci per fatturarle.</span><span class="sxs-lookup"><span data-stu-id="02cc4-107">When an order or voyage is set up to use goods-in-transit processing, you don't have to wait until goods are received in the warehouse before you can invoice them.</span></span> <span data-ttu-id="02cc4-108">Le merci vengono invece fatturate quando lasciano il magazzino o il porto di origine del fornitore e i costi finanziari vengono riconosciuti quando ha inizio il viaggio.</span><span class="sxs-lookup"><span data-stu-id="02cc4-108">Instead, the goods are invoiced when they leave the vendor's warehouse or port of origin, and the financial costs are recognized when the voyage begins.</span></span> <span data-ttu-id="02cc4-109">Questa funzionalità consente di assumere correttamente la proprietà delle merci in quanto queste spesso diventano di proprietà della propria organizzazione quando lasciano il porto di spedizione.</span><span class="sxs-lookup"><span data-stu-id="02cc4-109">This functionality lets you correctly take ownership of inventory, because goods often become the property of your organization when they leave the shipping port.</span></span>

<span data-ttu-id="02cc4-110">Quando vengono utilizzati ordini merci in transito, gli articoli aggiornati finanziariamente vengono ricevuti in un magazzino provvisorio noto come magazzino merci in transito.</span><span class="sxs-lookup"><span data-stu-id="02cc4-110">When goods-in-transit orders are used, the financially updated items are received in an interim warehouse that is known as a goods-in-transit warehouse.</span></span> <span data-ttu-id="02cc4-111">Le merci rimangono quindi in questo magazzino fino a quando non possono essere ricevute nel magazzino di destinazione finale (ovvero il magazzino definito nella riga di acquisto).</span><span class="sxs-lookup"><span data-stu-id="02cc4-111">The goods then stay in this warehouse until they can be received at the final destination warehouse (that is, the warehouse that is defined on the purchase line).</span></span> <span data-ttu-id="02cc4-112">Non possono essere rimosse manualmente.</span><span class="sxs-lookup"><span data-stu-id="02cc4-112">They can't be manually removed.</span></span>

<span data-ttu-id="02cc4-113">Fino a che gli articoli sono in transito, non sono disponibili nell'inventario e non possono essere prelevati per una consegna.</span><span class="sxs-lookup"><span data-stu-id="02cc4-113">As long as the items are in transit, they aren't available in inventory and can't be picked from inventory for a delivery.</span></span> <span data-ttu-id="02cc4-114">Tuttavia, è possibile visualizzare l'inventario merci in transito.</span><span class="sxs-lookup"><span data-stu-id="02cc4-114">However, you can view the goods-in-transit inventory.</span></span> <span data-ttu-id="02cc4-115">È anche possibile utilizzare le merci per la pianificazione generale.</span><span class="sxs-lookup"><span data-stu-id="02cc4-115">You can also use the goods for master planning.</span></span> <span data-ttu-id="02cc4-116">In questo caso, utilizzare la data di consegna confermata nella riga di ordine fornitore come data prevista in cui le merci in magazzino saranno disponibili per il consumo.</span><span class="sxs-lookup"><span data-stu-id="02cc4-116">In this case, use the confirmed delivery date on the purchase order line as the expected date when the inventory will be available for consumption.</span></span>

<span data-ttu-id="02cc4-117">Le sezioni seguenti descrivono la configurazione necessaria per elaborare l'inventario e i viaggi utilizzando il concetto e la funzionalità merci in transito.</span><span class="sxs-lookup"><span data-stu-id="02cc4-117">The following sections describe the setup that is required to process inventory and voyages by using the goods-in-transit concept and functionality.</span></span>

## <a name="terms-of-delivery"></a><span data-ttu-id="02cc4-118">Termini di consegna</span><span class="sxs-lookup"><span data-stu-id="02cc4-118">Terms of delivery</span></span>

<span data-ttu-id="02cc4-119">Quando si abilita il modulo **Costo sbarcato**, l'entità *termini di consegna* standard viene migliorata per supportare la funzionalità merci in transito.</span><span class="sxs-lookup"><span data-stu-id="02cc4-119">When you enable the **Landed cost** module, the standard *terms of delivery* entity is enhanced to support the goods-in-transit feature.</span></span>

<span data-ttu-id="02cc4-120">Quando l'opzione **Gestione merci in transito** è impostata su *Sì* per i termini di consegna applicabili, le merci vengono integrate nel magazzino merci in transito.</span><span class="sxs-lookup"><span data-stu-id="02cc4-120">When the **Goods in transit management** option is set to *Yes* for the applicable terms of delivery record, the goods are put into the goods-in-transit warehouse.</span></span> <span data-ttu-id="02cc4-121">Questa azione viene attivata solo se l'entrata in magazzino non viene elaborata prima dell'elaborazione di una fattura.</span><span class="sxs-lookup"><span data-stu-id="02cc4-121">This action is triggered only if the inventory receipt isn't processed before an invoice is processed.</span></span> <span data-ttu-id="02cc4-122">Quando i termini di consegna di un ordine sono impostati per utilizzare le merci in transito, gli utenti non possono più registrare un'entrata prodotti per l'ordine fornitore.</span><span class="sxs-lookup"><span data-stu-id="02cc4-122">When the delivery terms for an order are set to use goods in transit, users can no longer post a product receipt for the purchase order.</span></span> <span data-ttu-id="02cc4-123">Se ci provano, si verifica un errore.</span><span class="sxs-lookup"><span data-stu-id="02cc4-123">If they try, an error occurs.</span></span> <span data-ttu-id="02cc4-124">Il messaggio di errore indica che devono utilizzare la funzionalità merci in transito per procedere.</span><span class="sxs-lookup"><span data-stu-id="02cc4-124">The error message states that they must use the goods-in-transit functionality to proceed.</span></span>

<span data-ttu-id="02cc4-125">Per utilizzare le informazioni sui termini di consegna per le merci in transito, selezionare **Approvvigionamento \> Impostazioni \> Distribuzione \> Termini di consegna**.</span><span class="sxs-lookup"><span data-stu-id="02cc4-125">To work with delivery terms information for goods in transit, go to **Procurement and Sourcing \> Setup \> Distribution \> Terms of delivery**.</span></span> <span data-ttu-id="02cc4-126">La tabella seguente descrive i campi che il modulo **Costo sbarcato** aggiunge alla pagina **Termini di consegna** per supportare la funzionalità merci in transito.</span><span class="sxs-lookup"><span data-stu-id="02cc4-126">The following table describes the fields that the **Landed cost** module adds to the **Terms of delivery** page to support the goods-in-transit functionality.</span></span> <span data-ttu-id="02cc4-127">Entrambi i campi sono nella Scheda dettaglio **Generale**.</span><span class="sxs-lookup"><span data-stu-id="02cc4-127">Both fields are on the **General** FastTab.</span></span> <span data-ttu-id="02cc4-128">Per ulteriori informazioni sugli altri campi in questa pagina, vedere [Termini di consegna (modulo)](https://technet.microsoft.com/library/aa575567.aspx).</span><span class="sxs-lookup"><span data-stu-id="02cc4-128">For more information about the other fields on this page, see [Terms of delivery (form)](https://technet.microsoft.com/library/aa575567.aspx).</span></span>

| <span data-ttu-id="02cc4-129">Campo</span><span class="sxs-lookup"><span data-stu-id="02cc4-129">Field</span></span> | <span data-ttu-id="02cc4-130">Descrizione</span><span class="sxs-lookup"><span data-stu-id="02cc4-130">Description</span></span> |
|---|---|
| <span data-ttu-id="02cc4-131">Porto di spedizione obbligatorio</span><span class="sxs-lookup"><span data-stu-id="02cc4-131">Shipping port mandatory</span></span> | <span data-ttu-id="02cc4-132">Impostare questa opzione su *Sì* se un porto di spedizione è obbligatorio quando si applicano i termini di consegna.</span><span class="sxs-lookup"><span data-stu-id="02cc4-132">Set this option to *Yes* if a shipping port is mandatory when the delivery terms apply.</span></span> |
| <span data-ttu-id="02cc4-133">Gestione merci in transito</span><span class="sxs-lookup"><span data-stu-id="02cc4-133">Goods in transit management</span></span> | <span data-ttu-id="02cc4-134">Impostare questa opzione su *Sì* per utilizzare la gestione delle merci in transito quando si applicano i termini di consegna.</span><span class="sxs-lookup"><span data-stu-id="02cc4-134">Set this option to *Yes* to use goods-in-transit management when the delivery terms apply.</span></span> |

## <a name="warehouses-for-goods-in-transit-and-under-delivery"></a><span data-ttu-id="02cc4-135">Magazzini per merci in transito e consegna in difetto</span><span class="sxs-lookup"><span data-stu-id="02cc4-135">Warehouses for goods in transit and under-delivery</span></span>

<span data-ttu-id="02cc4-136">Quando si abilita il modulo **Costo sbarcato**, l'entità *magazzini* standard viene migliorata per abilitare la fatturazione degli ordini fornitore quando le merci si trovano in un magazzino merci in transito.</span><span class="sxs-lookup"><span data-stu-id="02cc4-136">When you enable the **Landed cost** module, the standard *warehouses* entity is enhanced to enable purchase orders to be invoiced while the goods are in a goods-in-transit warehouse.</span></span>

<span data-ttu-id="02cc4-137">Il modulo Costo sbarcato aggiunge due nuovi tipi di magazzino: *merci in transito* e *consegna in difetto*.</span><span class="sxs-lookup"><span data-stu-id="02cc4-137">Landed cost adds two new types of warehouse: *goods in transit* and *under-delivery*.</span></span> <span data-ttu-id="02cc4-138">I magazzini di entrambi i tipi possono essere selezionati come magazzini predefiniti.</span><span class="sxs-lookup"><span data-stu-id="02cc4-138">Warehouses of both types can be selected as default warehouses.</span></span> <span data-ttu-id="02cc4-139">Per un'elaborazione corretta degli ordini merci in transito, sia il magazzino merci in transito che il magazzino consegna in difetto devono essere configurati nella pagina **Magazzini**.</span><span class="sxs-lookup"><span data-stu-id="02cc4-139">Successful processing of goods-in-transit orders requires that both the goods-in-transit warehouse and the under-delivery warehouse be configured on the **Warehouses** page.</span></span> <span data-ttu-id="02cc4-140">Quindi, per ogni magazzino predefinito che verrà utilizzato con Costo sbarcato e merci in transito, è necessario selezionare il magazzino merci in transito e il magazzino consegna in difetto per i magazzini disponibili di ciascun tipo.</span><span class="sxs-lookup"><span data-stu-id="02cc4-140">Then, for each default warehouse that will be used with Landed cost and goods in transit, the goods-in-transit warehouse and under-delivery warehouse must be selected for the available warehouses of each type.</span></span>

<span data-ttu-id="02cc4-141">Il tipo di magazzino *merci in transito* verrà associato al magazzino merci in transito e tale magazzino verrà utilizzato per elaborare le merci negli ordini merci in transito prima che vengano ricevute nel magazzino di destinazione finale.</span><span class="sxs-lookup"><span data-stu-id="02cc4-141">The *goods in transit* warehouse type will be associated with your goods-in-transit warehouse, and that warehouse will be used to process the goods on goods-in-transit orders before they are received at the final destination warehouse.</span></span> <span data-ttu-id="02cc4-142">In generale, un magazzino merci in transito è sufficiente per ogni sito se Sito e Magazzino sono le uniche dimensioni inventariali utilizzate per la gestione degli articoli.</span><span class="sxs-lookup"><span data-stu-id="02cc4-142">In general, one goods-in-transit warehouse is enough for each site if Site and Warehouse are the only inventory dimensions that are used for inventory management.</span></span> <span data-ttu-id="02cc4-143">Se viene utilizzata anche la dimensione inventariale Ubicazione, è necessario impostare un magazzino merci in transito per ciascuna combinazione di sito e magazzino, in modo da poter specificare anche l'ubicazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="02cc4-143">If the Location inventory dimension is also used, a goods-in-transit warehouse must be set up for each combination of a site and warehouse, so that the default location can also be specified.</span></span>

<span data-ttu-id="02cc4-144">Per utilizzare le impostazioni relative alle merci in transito per i magazzini in uso, selezionare **Gestione articoli \> Impostazioni \> Suddivisione scorte \> Magazzini**.</span><span class="sxs-lookup"><span data-stu-id="02cc4-144">To work with goods-in-transit settings for your warehouses, go to **Inventory management \> Setup \> Inventory breakdown \> Warehouses**.</span></span> <span data-ttu-id="02cc4-145">La tabella seguente descrive i campi che il modulo **Costo sbarcato** aggiunge alla pagina **Magazzini** per supportare la funzionalità merci in transito.</span><span class="sxs-lookup"><span data-stu-id="02cc4-145">The following table describes the fields that the **Landed cost** module adds to the **Warehouses** page to support the goods-in-transit functionality.</span></span> <span data-ttu-id="02cc4-146">Entrambi i campi sono visualizzati nella Scheda dettaglio **Generale**.</span><span class="sxs-lookup"><span data-stu-id="02cc4-146">Both fields appear on the **General** FastTab.</span></span> <span data-ttu-id="02cc4-147">Per informazioni sugli altri campi nella pagina, vedere [Magazzini (modulo)](https://technet.microsoft.com/library/aa620570.aspx).</span><span class="sxs-lookup"><span data-stu-id="02cc4-147">For information about the other fields on the page, see [Warehouses (form)](https://technet.microsoft.com/library/aa620570.aspx).</span></span>

| <span data-ttu-id="02cc4-148">Campo</span><span class="sxs-lookup"><span data-stu-id="02cc4-148">Field</span></span> | <span data-ttu-id="02cc4-149">Descrizione</span><span class="sxs-lookup"><span data-stu-id="02cc4-149">Description</span></span> |
|---|---|
| <span data-ttu-id="02cc4-150">Magazzino merci in transito</span><span class="sxs-lookup"><span data-stu-id="02cc4-150">Goods in transit warehouse</span></span> | <span data-ttu-id="02cc4-151">Consente di identificare il magazzino merci in transito correlato al magazzino principale.</span><span class="sxs-lookup"><span data-stu-id="02cc4-151">Identify the goods-in-transit warehouse that is related to the main warehouse.</span></span> |
| <span data-ttu-id="02cc4-152">Magazzino consegna in difetto</span><span class="sxs-lookup"><span data-stu-id="02cc4-152">Under delivery warehouse</span></span> | <span data-ttu-id="02cc4-153">Consente di identificare il magazzino consegna in difetto correlato al magazzino principale.</span><span class="sxs-lookup"><span data-stu-id="02cc4-153">Identify the under-delivery warehouse that is related to the main warehouse.</span></span> |

## <a name="posting-rules-for-landed-cost"></a><span data-ttu-id="02cc4-154">Regole di registrazione per costo sbarcato</span><span class="sxs-lookup"><span data-stu-id="02cc4-154">Posting rules for landed cost</span></span>

<span data-ttu-id="02cc4-155">Costo sbarcato aggiunge due nuove regole di registrazione che è possibile configurare.</span><span class="sxs-lookup"><span data-stu-id="02cc4-155">Landed cost adds two new posting rules that you can configure.</span></span> <span data-ttu-id="02cc4-156">Queste regole di registrazione sono utilizzate per registrare finanziariamente gli importi diretti della fattura di ordine fornitore per identificare la proprietà delle merci quando lasciano il punto di origine.</span><span class="sxs-lookup"><span data-stu-id="02cc4-156">These posting rules are used to financially post the direct purchase order invoice amounts to identify ownership of the goods when they leave the point of origin.</span></span> <span data-ttu-id="02cc4-157">Questo processo sostituisce il concetto di *merce ricevuta non fatturata* poiché le merci vengono fatturate prima di essere ricevute.</span><span class="sxs-lookup"><span data-stu-id="02cc4-157">This process replaces the concept of *goods received not invoiced*, because the goods are invoiced before they are received.</span></span> <!-- KFM: Add a link to the related scenario when available. -->

<span data-ttu-id="02cc4-158">Per utilizzare i profili di registrazione, selezionare **Gestione articoli \> Impostazioni \> Registrazione \> Registrazione**.</span><span class="sxs-lookup"><span data-stu-id="02cc4-158">To work with posting profiles, go to **Inventory management \> Setup \> Posting \> Posting**.</span></span> <span data-ttu-id="02cc4-159">Nella scheda **Ordine fornitore**, sono disponibili le seguenti nuove regole di registrazione:</span><span class="sxs-lookup"><span data-stu-id="02cc4-159">On the **Purchase Order** tab, the following new posting rules are available:</span></span>

- <span data-ttu-id="02cc4-160">**Costo sbarcato, merci in transito** - Specificare le regole di registrazione per la gestione merci in transito.</span><span class="sxs-lookup"><span data-stu-id="02cc4-160">**Landed cost, goods in transit** – Specify the posting rules for goods-in-transit management.</span></span>
- <span data-ttu-id="02cc4-161">**Costo sbarcato, rateo addebito costi** - Specificare le regole di registrazione per il rateo del conto di addebito.</span><span class="sxs-lookup"><span data-stu-id="02cc4-161">**Landed cost, cost charge accrual** – Specify the posting rules for charge account accrual.</span></span>

## <a name="goods-in-transit-orders"></a><span data-ttu-id="02cc4-162">Ordini merci in transito</span><span class="sxs-lookup"><span data-stu-id="02cc4-162">Goods-in-transit orders</span></span>

<span data-ttu-id="02cc4-163">È possibile esaminare e gestire ordini merci in transito direttamente nel modulo **Costo sbarcato**.</span><span class="sxs-lookup"><span data-stu-id="02cc4-163">You can review and manage goods-in-transit orders directly in the **Landed cost** module.</span></span> <span data-ttu-id="02cc4-164">È possibile elaborare ordini merci in transito direttamente dalla pagina **Ordini merci in transito**.</span><span class="sxs-lookup"><span data-stu-id="02cc4-164">You can process goods-in-transit orders directly from the **Goods in transit orders** page.</span></span> <span data-ttu-id="02cc4-165">In alternativa, è possibile accedere al viaggio associato agli ordini merci in transito ed elaborare l'intero viaggio, contenitore di spedizione o registrazione.</span><span class="sxs-lookup"><span data-stu-id="02cc4-165">Alternatively, you can go to the voyage that is associated with the goods-in-transit orders, and process the whole voyage, shipping container, or folio.</span></span> <span data-ttu-id="02cc4-166">Quando si fattura un viaggio e si creano ordini merci in transito, viene creato un nuovo ordine merci in transito per ogni combinazione di inventario e dimensioni inventariali associata alla riga di ordine fornitore.</span><span class="sxs-lookup"><span data-stu-id="02cc4-166">When you invoice a voyage and create goods-in-transit orders, a new goods-in-transit order is created for each combination of inventory and inventory dimensions that is associated with the purchase order line.</span></span>

<span data-ttu-id="02cc4-167">Per gestire merci in transito, Costo sbarcato utilizza una procedura in due fasi:</span><span class="sxs-lookup"><span data-stu-id="02cc4-167">To manage goods in transit, Landed cost uses a two-step procedure:</span></span>

1. <span data-ttu-id="02cc4-168">Un articolo viene ricevuto quando viene elaborata una fattura delle scorte e le viene assegnato lo stato *In transito*.</span><span class="sxs-lookup"><span data-stu-id="02cc4-168">An item is received when a stock invoice is processed and assigned a status of *In transit*.</span></span>
1. <span data-ttu-id="02cc4-169">L'ordine merci in transito viene elaborato nella pagina **Ordini merci in transito** e viene quindi ricevuto nel magazzino specificato nell'ordine fornitore.</span><span class="sxs-lookup"><span data-stu-id="02cc4-169">The goods-in-transit order is processed on the **Goods in transit orders** page and then received in the warehouse that is specified on the purchase order.</span></span> <span data-ttu-id="02cc4-170">A quel punto, lo stato diventa *Ricevuto*.</span><span class="sxs-lookup"><span data-stu-id="02cc4-170">At that point, the status is changed to *Received*.</span></span>

<span data-ttu-id="02cc4-171">Per utilizzare gli ordini merci in transito, selezionare **Costo sbarcato \> Attività periodiche \> Ordini merci in transito**.</span><span class="sxs-lookup"><span data-stu-id="02cc4-171">To work with goods-in-transit orders, go to **Landed cost \> Periodic tasks \> Goods in transit orders**.</span></span>

## <a name="receiving-stock-from-the-goods-in-transit-warehouse"></a><span data-ttu-id="02cc4-172">Ricevimento delle scorte dal magazzino merci in transito</span><span class="sxs-lookup"><span data-stu-id="02cc4-172">Receiving stock from the goods-in-transit warehouse</span></span>

<span data-ttu-id="02cc4-173">È possibile ricevere merci da un ordine merci in transito in molti modi, a seconda della configurazione del sistema.</span><span class="sxs-lookup"><span data-stu-id="02cc4-173">You can receive goods from a goods-in-transit order in many ways, depending on the setup of your system.</span></span>

### <a name="in-transit-receiving"></a><span data-ttu-id="02cc4-174">Ricevimento in transito</span><span class="sxs-lookup"><span data-stu-id="02cc4-174">In-transit receiving</span></span>

<span data-ttu-id="02cc4-175">È possibile eseguire un ricevimento in transito in una qualsiasi delle seguenti pagine:</span><span class="sxs-lookup"><span data-stu-id="02cc4-175">You can do in-transit receiving from any of the following pages:</span></span>

- <span data-ttu-id="02cc4-176">Nella pagina **Ordini merci in transito**, selezionare la riga e quindi, nel riquadro Azioni, selezionare **Ricevi**.</span><span class="sxs-lookup"><span data-stu-id="02cc4-176">On the **Goods in transit orders** page, select the line, and then, on the Action Pane, select **Receive**.</span></span>
- <span data-ttu-id="02cc4-177">Nella pagina **Tutti i viaggi**, selezionare o aprire un viaggio.</span><span class="sxs-lookup"><span data-stu-id="02cc4-177">On the **All voyages** page, select or open a voyage.</span></span> <span data-ttu-id="02cc4-178">Quindi, nel riquadro Azioni, nella scheda **Gestisci**, nel gruppo **Merci in transito**, selezionare **Ricevi merci in transito**.</span><span class="sxs-lookup"><span data-stu-id="02cc4-178">Then, on the Action Pane, on the **Manage** tab, in the **Goods in transit** group, select **Receive goods in transit**.</span></span>
- <span data-ttu-id="02cc4-179">Nella pagina **Tutti i contenitori di spedizione**, selezionare o aprire un contenitore di spedizione.</span><span class="sxs-lookup"><span data-stu-id="02cc4-179">On the **All shipping containers** page, select or open a shipping container.</span></span> <span data-ttu-id="02cc4-180">Quindi, nel riquadro Azioni, nella scheda **Gestisci**, nel gruppo **Merci in transito**, selezionare **Ricevi merci in transito**.</span><span class="sxs-lookup"><span data-stu-id="02cc4-180">Then, on the Action Pane, on the **Manage** tab, in the **Goods in transit** group, select **Receive goods in transit**.</span></span>
- <span data-ttu-id="02cc4-181">Nella pagina **Tutte le registrazioni**, selezionare o aprire una registrazione.</span><span class="sxs-lookup"><span data-stu-id="02cc4-181">On the **All folios** page, select or open a folio.</span></span> <span data-ttu-id="02cc4-182">Quindi, nel riquadro Azioni, nella scheda **Gestisci**, nel gruppo **Merci in transito**, selezionare **Ricevi merci in transito**.</span><span class="sxs-lookup"><span data-stu-id="02cc4-182">Then, on the Action Pane, on the **Manage** tab, in the **Goods in transit** group, select **Receive goods in transit**.</span></span>

> [!NOTE]
> <span data-ttu-id="02cc4-183">La ricezione in transito viene generalmente utilizzata in situazioni in cui le ubicazioni e la tracciabilità seriale/batch non sono utilizzate.</span><span class="sxs-lookup"><span data-stu-id="02cc4-183">In-transit receiving is generally used in situations where locations and batch/serial tracking aren't used.</span></span>

### <a name="arrival-journal"></a><span data-ttu-id="02cc4-184">Giornale di registrazione arrivi</span><span class="sxs-lookup"><span data-stu-id="02cc4-184">Arrival journal</span></span>

<span data-ttu-id="02cc4-185">È anche possibile ricevere merci creando un giornale di registrazione arrivi.</span><span class="sxs-lookup"><span data-stu-id="02cc4-185">You can also receive goods by creating an arrival journal.</span></span> <span data-ttu-id="02cc4-186">È possibile creare un giornale di registrazione arrivi direttamente dalla pagina del viaggio.</span><span class="sxs-lookup"><span data-stu-id="02cc4-186">You can create an arrival journal directly from the voyage page.</span></span> <span data-ttu-id="02cc4-187">Le procedure consigliate stabilite dall'organizzazione determinano se il giornale di registrazione arrivi viene utilizzato per ricevere le merci.</span><span class="sxs-lookup"><span data-stu-id="02cc4-187">The best practices that your organization has established determine whether the arrival journal is used to receive goods.</span></span>

1. <span data-ttu-id="02cc4-188">Aprire il viaggio, il contenitore o la registrazione.</span><span class="sxs-lookup"><span data-stu-id="02cc4-188">Open the voyage, container, or folio.</span></span>
1. <span data-ttu-id="02cc4-189">Nel riquadro azioni della scheda **Gestisci** del gruppo **Funzioni**, selezionare **Crea giornale di registrazione arrivi**.</span><span class="sxs-lookup"><span data-stu-id="02cc4-189">On the Action Pane, on the **Manage** tab, in the **Functions** group, select **Create arrival journal**.</span></span>
1. <span data-ttu-id="02cc4-190">Nella finestra di dialogo **Crea giornale di registrazione arrivi**, impostare i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="02cc4-190">In the **Create arrival journal** dialog box, set the following values:</span></span>
    - <span data-ttu-id="02cc4-191">**Inizializza quantità** - Impostare questa opzione su *Sì* per impostare la quantità in base alla quantità in transito.</span><span class="sxs-lookup"><span data-stu-id="02cc4-191">**Initialize quantity** – Set this option to *Yes* to set the quantity from the in-transit quantity.</span></span> <span data-ttu-id="02cc4-192">Se questa opzione è impostata su *No*, non viene impostata alcuna quantità predefinita in base alle righe merci in transito.</span><span class="sxs-lookup"><span data-stu-id="02cc4-192">If this option is set to *No*, no default quantity is set from the goods-in-transit lines.</span></span>
    - <span data-ttu-id="02cc4-193">**Crea da merci in transito** - Impostare questa opzione su *Sì* per prelevare quantità dalle righe in transito selezionate per il viaggio, il contenitore o il folio selezionato.</span><span class="sxs-lookup"><span data-stu-id="02cc4-193">**Create from goods in transit** - Set this option to *Yes* to take quantities from the selected in-transit lines for the selected voyage, container, or folio.</span></span>
    - <span data-ttu-id="02cc4-194">**Crea da righe ordine** - Impostare questa opzione su *Sì* per impostare la quantità predefinita nel giornale di registrazione arrivi in base alle righe di ordine fornitore.</span><span class="sxs-lookup"><span data-stu-id="02cc4-194">**Create from order lines** – Set this option to *Yes* to set the default quantity in the arrival journal from the purchase order lines.</span></span> <span data-ttu-id="02cc4-195">La quantità predefinita nel giornale di registrazione arrivi può essere impostata in questo modo solo se la quantità nella riga di ordine fornitore corrisponde alla quantità nell'ordine merci in transito.</span><span class="sxs-lookup"><span data-stu-id="02cc4-195">The default quantity in the arrival journal can be set in this way only if the quantity on the purchase order line matches the quantity on the goods-in-transit order.</span></span>

1. <span data-ttu-id="02cc4-196">Elaborare il giornale di registrazione arrivi come descritto in [Registrare le entrate articoli con un giornale di registrazione arrivi articoli](https://technet.microsoft.com/library/aa571129.aspx).</span><span class="sxs-lookup"><span data-stu-id="02cc4-196">Process the arrival journal as described in [Register item receipts with an item arrival journal](https://technet.microsoft.com/library/aa571129.aspx).</span></span>

> [!NOTE]
> <span data-ttu-id="02cc4-197">Il giornale di registrazione arrivi è generalmente utilizzato in situazioni in cui vengono utilizzate ubicazioni e tracciabilità batch/seriale, ma non la gestione del magazzino.</span><span class="sxs-lookup"><span data-stu-id="02cc4-197">The arrival journal is generally used in situations where locations and batch/serial tracking are used, but warehouse management isn't used.</span></span>
>
> <span data-ttu-id="02cc4-198">Le ubicazioni di ricevimento predefinite non devono essere specificate nelle righe ordine se verrà specificata un'ubicazione di stoccaggio nel giornale di registrazione arrivi.</span><span class="sxs-lookup"><span data-stu-id="02cc4-198">Default receipt locations should not be specified on the order lines if a putaway location will be specified in the arrival journal.</span></span>

## <a name="warehouse-management"></a><span data-ttu-id="02cc4-199">Gestione magazzino</span><span class="sxs-lookup"><span data-stu-id="02cc4-199">Warehouse management</span></span>

<span data-ttu-id="02cc4-200">Quando si abilita il modulo **Costo sbarcato**, diverse pagine nel modulo **Gestione magazzino** vengono modificate di modo che l'elaborazione degli ordini (in particolare, l'elaborazione merci in transito) possa essere eseguita tramite il modulo **Costo sbarcato**.</span><span class="sxs-lookup"><span data-stu-id="02cc4-200">When you enable the **Landed cost** module, several pages in the **Warehouse management** module are modified so that order processing (specifically, goods-in-transit processing) can be done through the **Landed cost** module.</span></span> <span data-ttu-id="02cc4-201">Questa sezione descrive i campi e i processi aggiunti nel modulo **Gestione magazzino**.</span><span class="sxs-lookup"><span data-stu-id="02cc4-201">This section outlines the fields and processes that are added in the **Warehouse management** module.</span></span>

### <a name="mobile-device-menu-items"></a><span data-ttu-id="02cc4-202">Voci di menu del dispositivo mobile</span><span class="sxs-lookup"><span data-stu-id="02cc4-202">Mobile device menu items</span></span>

<span data-ttu-id="02cc4-203">Le merci possono essere ricevute utilizzando un dispositivo mobile, a condizione che il menu del dispositivo mobile e il modulo **Gestione magazzino** siano stati impostati per ricevere merci su un ordine merci in transito.</span><span class="sxs-lookup"><span data-stu-id="02cc4-203">Goods can be received by using a mobile device, provided that the mobile device menu and **Warehouse management** module have been set up to receive goods on a goods-in-transit order.</span></span> <span data-ttu-id="02cc4-204">Questa sezione descrive l'impostazione associata al ricevimento merci in transito.</span><span class="sxs-lookup"><span data-stu-id="02cc4-204">This section describes the setup that is associated with goods-in-transit receiving.</span></span>

<span data-ttu-id="02cc4-205">Per configurare i dispositivi mobili per l'elaborazione merci in transito, selezionare **Gestione magazzino \> Impostazioni \> Dispositivo mobile \> Voci di menu del dispositivo mobile**.</span><span class="sxs-lookup"><span data-stu-id="02cc4-205">To set up mobile devices for goods-in-transit processing, go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu items**.</span></span>

<span data-ttu-id="02cc4-206">Costo sbarcato aggiunge i seguenti processi di creazione di lavoro alle voci di menu del dispositivo mobile per supportare l'elaborazione merci in transito:</span><span class="sxs-lookup"><span data-stu-id="02cc4-206">Landed cost adds the following work creation processes to the mobile device menu items to support goods-in-transit processing:</span></span>

- <span data-ttu-id="02cc4-207">Ricevimento articoli merci in transito</span><span class="sxs-lookup"><span data-stu-id="02cc4-207">Goods in transit item receiving</span></span>
- <span data-ttu-id="02cc4-208">Ricevimento e stoccaggio articoli merci in transito</span><span class="sxs-lookup"><span data-stu-id="02cc4-208">Goods in transit item receiving and putaway</span></span>

<span data-ttu-id="02cc4-209">Le impostazioni di configurazione per questi processi sono simili alle impostazioni per i [processi di creazione lavoro: ricevimento e stoccaggio ordine fornitore](https://technet.microsoft.com/library/dn553216.aspx).</span><span class="sxs-lookup"><span data-stu-id="02cc4-209">The configuration settings for these processes resemble the settings for the [purchase order receive and putaway work creation processes](https://technet.microsoft.com/library/dn553216.aspx).</span></span> <span data-ttu-id="02cc4-210">Tuttavia, il processo *Ricevimento e stoccaggio articoli merci in transito* aggiunge anche il seguente campo.</span><span class="sxs-lookup"><span data-stu-id="02cc4-210">However, the *Goods in transit item receiving and putaway* process also adds the following field.</span></span>

- <span data-ttu-id="02cc4-211">**Abilita contenitore di spedizione completo** - Se questa opzione è impostata su *Sì*, quando il lavoro di stoccaggio è completato, l'app di magazzino fornirà un'opzione aggiuntiva denominata **Contenitore di spedizione completo**.</span><span class="sxs-lookup"><span data-stu-id="02cc4-211">**Enable shipping container complete** – If this option is set to *Yes*, when the putaway work is completed, the warehouse app will provide an additional option that is named **Shipping container complete**.</span></span> <span data-ttu-id="02cc4-212">Quando questa opzione è selezionata, al lavoratore verrà chiesto di confermare che il contenitore è completo.</span><span class="sxs-lookup"><span data-stu-id="02cc4-212">When that option is selected, the worker will be asked to confirm that the container is complete.</span></span> <span data-ttu-id="02cc4-213">A quel punto, tutte le entrate incomplete verranno elaborate come transazione in difetto.</span><span class="sxs-lookup"><span data-stu-id="02cc4-213">At that point, all short receipts will be processed as an under transaction.</span></span>

### <a name="location-directives"></a><span data-ttu-id="02cc4-214">Direttive ubicazione</span><span class="sxs-lookup"><span data-stu-id="02cc4-214">Location directives</span></span>

<span data-ttu-id="02cc4-215">Costo sbarcato aggiunge un nuovo tipo di ordine di lavoro denominato *Merci in transito* alla pagina **Direttive ubicazione**.</span><span class="sxs-lookup"><span data-stu-id="02cc4-215">Landed cost adds a new work order type that is named *Goods in transit* to the **Location directives** page.</span></span> <span data-ttu-id="02cc4-216">Questo tipo di ordine di lavoro deve essere configurato allo stesso modo dei [tipi di ordine di lavoro di ordine fornitore](https://technet.microsoft.com/library/dn553184.aspx).</span><span class="sxs-lookup"><span data-stu-id="02cc4-216">This work order type should be configured in the same manner as the [purchase order work order types](https://technet.microsoft.com/library/dn553184.aspx).</span></span>

### <a name="work-templates"></a><span data-ttu-id="02cc4-217">Modelli di lavoro</span><span class="sxs-lookup"><span data-stu-id="02cc4-217">Work templates</span></span>

<span data-ttu-id="02cc4-218">Costo sbarcato aggiunge un nuovo tipo di ordine di lavoro denominato *Merci in transito* alla pagina **Modelli di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="02cc4-218">Landed cost adds a new work order type that is named *Goods in transit* to the **Work templates** page.</span></span> <span data-ttu-id="02cc4-219">Questo tipo di ordine di lavoro deve essere configurato allo stesso modo dei [modelli di lavoro di ordine fornitore](https://technet.microsoft.com/library/dn553184.aspx).</span><span class="sxs-lookup"><span data-stu-id="02cc4-219">This work order type should be configured in the same manner as the [purchase order work templates](https://technet.microsoft.com/library/dn553184.aspx).</span></span>
