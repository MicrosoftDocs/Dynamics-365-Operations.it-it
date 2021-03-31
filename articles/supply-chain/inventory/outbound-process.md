---
title: Panoramica del processo in uscita
description: In questo argomento viene fornita una panoramica del processo in uscita in Gestione articoli.
author: perlynne
manager: tfehr
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WMSOrder, WMSShipment, MCRPickingWorkbench, WMSPickingRegistration, CustomFilterGroup
audience: Application User
ms.reviewer: kamaybac
ms.custom: 274363
ms.assetid: 375807b2-a426-4f1b-bc1f-2fe00fd48413
ms.search.region: global
ms.search.industry: Distribution
ms.author: perlynne
ms.dyn365.ops.version: AX 7.0.0
ms.search.validFrom: 2016-02-28
ms.openlocfilehash: 24406f107d796891c315b39d3eff4351ae0aa5be
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5209685"
---
# <a name="outbound-process-overview"></a><span data-ttu-id="52840-103">Panoramica del processo in uscita</span><span class="sxs-lookup"><span data-stu-id="52840-103">Outbound process overview</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="52840-104">In questo argomento viene fornita una panoramica del processo in uscita in Gestione articoli.</span><span class="sxs-lookup"><span data-stu-id="52840-104">This topic provides an overview of the outbound process in Inventory management.</span></span>

## <a name="output-orders"></a><span data-ttu-id="52840-105">Ordini di uscita</span><span class="sxs-lookup"><span data-stu-id="52840-105">Output orders</span></span>

<span data-ttu-id="52840-106">Gli ordini di uscita vengono utilizzati per collegare righe di ordini cliente e righe di ordini di trasferimento ai processi di prelievo in uscita che utilizzano le distinte di prelievo.</span><span class="sxs-lookup"><span data-stu-id="52840-106">Output orders are used to link sales order lines and transfer order lines with the outbound picking processes that use picking lists.</span></span>

<span data-ttu-id="52840-107">Quando le distinte di prelievo vengono generate a partire da ordini cliente o ordini di trasferimento, gli ordini di uscita e le spedizioni vengono creati automaticamente.</span><span class="sxs-lookup"><span data-stu-id="52840-107">When picking lists are generated from either sales orders or transfer orders, output orders and shipments are automatically created.</span></span> <span data-ttu-id="52840-108">Una distinta di prelievo ha una relazione uno-a-uno con una spedizione.</span><span class="sxs-lookup"><span data-stu-id="52840-108">A picking list has a one-to-one relationship with a shipment.</span></span> <span data-ttu-id="52840-109">La spedizione degli ordini di trasferimento o il documento di trasporto degli ordini cliente possono essere elaborati dalla spedizione.</span><span class="sxs-lookup"><span data-stu-id="52840-109">The transfer order shipment or the sales order packing slip can be processed from the shipment.</span></span> 

<span data-ttu-id="52840-110">Il diagramma seguente mostra una panoramica del processo per gli ordini di uscita.</span><span class="sxs-lookup"><span data-stu-id="52840-110">The following diagram shows an overview of the process for outbound orders.</span></span> 

<span data-ttu-id="52840-111">[![Panoramica del processo dell'ordine di uscita](./media/outbound-order.png)](./media/outbound-order.png)</span><span class="sxs-lookup"><span data-stu-id="52840-111">[![Overview of the outbound order process](./media/outbound-order.png)](./media/outbound-order.png)</span></span>

<span data-ttu-id="52840-112">È possibile impostare regole in uscita per definire la modalità con cui il programma deve gestire il processo in uscita.</span><span class="sxs-lookup"><span data-stu-id="52840-112">You can set up outbound rules to define how the program should handle the outbound process.</span></span> <span data-ttu-id="52840-113">È possibile utilizzare queste regole per controllare il processo di spedizione.</span><span class="sxs-lookup"><span data-stu-id="52840-113">You can use these rules to control the shipment process.</span></span> <span data-ttu-id="52840-114">In particolare, è possibile utilizzare le regole per determinare durante quale fase del processo è possibile inviare le spedizioni.</span><span class="sxs-lookup"><span data-stu-id="52840-114">In particular, you can use the rules to control which stage in the process a shipment can be sent during.</span></span> <span data-ttu-id="52840-115">Le impostazioni seguenti definiscono il modo in cui i processi in uscita sono gestiti.</span><span class="sxs-lookup"><span data-stu-id="52840-115">The following settings define how the outbound processes are handled.</span></span>

## <a name="picking-route-status-for-sales-and-transfer-orders"></a><span data-ttu-id="52840-116">Stato ciclo di prelievo per ordini cliente e di trasferimento</span><span class="sxs-lookup"><span data-stu-id="52840-116">Picking route status for sales and transfer orders</span></span> 

<span data-ttu-id="52840-117">Andare a **Contabilità clienti** \> **Impostazioni** \> **Parametri contabilità clienti**, quindi nella scheda **Aggiornamenti**, selezionare un valore nel campo **Stato ciclo di prelievo**.</span><span class="sxs-lookup"><span data-stu-id="52840-117">Go to **Account receivable** \> **Setup** \> **Account receivable parameters**, and then, on the **Updates** tab, select a value in the **Picking route status** field.</span></span>

<span data-ttu-id="52840-118">[![Campo Stato ciclo di prelievo per ordini cliente](./media/picking-route-status-sales-order.png)](./media/picking-route-status-sales-order.png)</span><span class="sxs-lookup"><span data-stu-id="52840-118">[![Picking route status field for sales orders](./media/picking-route-status-sales-order.png)](./media/picking-route-status-sales-order.png)</span></span>

<span data-ttu-id="52840-119">Se il campo **Stato ciclo di prelievo** è impostato su **Completato**, il processo di prelievo viene eseguito automaticamente durante il processo di generazione delle distinte di prelievo.</span><span class="sxs-lookup"><span data-stu-id="52840-119">If the **Picking route status** field is set to **Completed**, the picking process occurs automatically as part of the process of generating picking lists.</span></span> <span data-ttu-id="52840-120">Se il campo è impostato su **Attivato**, le righe della distinta di prelievo devono essere aggiornate manualmente.</span><span class="sxs-lookup"><span data-stu-id="52840-120">If the field is set to **Activated**, the picking list lines must be manually updated.</span></span>

<span data-ttu-id="52840-121">La stessa impostazione si applica agli ordini di trasferimento.</span><span class="sxs-lookup"><span data-stu-id="52840-121">The same setup applies to transfer orders.</span></span> <span data-ttu-id="52840-122">Andare a **Gestione articoli** \> **Impostazioni** \> **Parametri di gestione articoli e magazzino**, quindi nella scheda **Trasporto**, selezionare un valore nel campo **Stato ciclo di prelievo**.</span><span class="sxs-lookup"><span data-stu-id="52840-122">Go to **Inventory management** \> **Setup** \> **Inventory and warehouse management parameters**, and then, on the **Transport** tab, select a value in the **Picking route status** field.</span></span>

<span data-ttu-id="52840-123">[![Campo Stato ciclo di prelievo per ordini di trasferimento](./media/picking-route-status-transfer-order.png)](./media/picking-route-status-transfer-order.png)</span><span class="sxs-lookup"><span data-stu-id="52840-123">[![Picking route status field for transfer orders](./media/picking-route-status-transfer-order.png)](./media/picking-route-status-transfer-order.png)</span></span>

## <a name="end-output-inventory-orders"></a><span data-ttu-id="52840-124">Termina ordine di magazzino in uscita</span><span class="sxs-lookup"><span data-stu-id="52840-124">End output inventory orders</span></span>

<span data-ttu-id="52840-125">Andare a **Gestione articoli** \> **Impostazioni** \> **Parametri di gestione articoli e magazzino**, quindi nella scheda **Generale**, impostare l'opzione **Termina ordine di magazzino in uscita**.</span><span class="sxs-lookup"><span data-stu-id="52840-125">Go to **Inventory management** \> **Setup** \> **Inventory and warehouse management parameters**, and then, on the **General** tab, set the **End output inventory order** option.</span></span>

<span data-ttu-id="52840-126">[![Opzione Termina ordine di magazzino in uscita](./media//end-output-inventory-order.png)](./media//end-output-inventory-order.png)</span><span class="sxs-lookup"><span data-stu-id="52840-126">[![End output inventory order option](./media//end-output-inventory-order.png)](./media//end-output-inventory-order.png)</span></span>

<span data-ttu-id="52840-127">Quando il lavoratore di magazzino riduce le quantità della distinta di prelievo, le quantità dell'ordine di magazzino corrispondenti verranno rimosse dalla spedizione.</span><span class="sxs-lookup"><span data-stu-id="52840-127">When the warehouse worker reduces the picking list quantities, then the corresponding inventory order quantities will be removed from the shipment.</span></span> <span data-ttu-id="52840-128">Quando la distinta di prelievo viene aggiornata, le quantità rimanenti vengono registrate di nuovo nell'ordine se l'opzione **Termina ordine di magazzino in uscita** è impostata su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="52840-128">When the picking list is updated at a point in time, the remaining quantities get reported back to the order if the **End output inventory order** option is set to **Yes**.</span></span> <span data-ttu-id="52840-129">Se l'opzione **Termina ordine di magazzino in uscita** è impostata su **No**, le quantità rimanenti vengono mantenute come quantità dell'ordine di uscita aperto e devono essere aggiunte a una nuova distinta di prelievo come parte della funzionalità **Ordini di uscita aperti**.</span><span class="sxs-lookup"><span data-stu-id="52840-129">If the **End output inventory order** option is set to **No**, the remaining quantities are kept as an open output order quantity and must be added to a new picking list as part of the **Open output orders** functionality.</span></span> 

<span data-ttu-id="52840-130">[![Comando Ordini di uscita aperti nel menu Funzioni](./media/open-output-order.png)](./media/open-output-order.png)</span><span class="sxs-lookup"><span data-stu-id="52840-130">[![Open output orders command on the Functions menu](./media/open-output-order.png)](./media/open-output-order.png)</span></span>

<span data-ttu-id="52840-131">[![Menu Funzioni nella pagina Ordini di uscita aperti](./media/open-output-order-function.png)](./media/open-output-order-function.png)</span><span class="sxs-lookup"><span data-stu-id="52840-131">[![Functions menu on the Open output orders page](./media/open-output-order-function.png)](./media/open-output-order-function.png)</span></span>

## <a name="reduce-quantity"></a><span data-ttu-id="52840-132">Riduci quantità</span><span class="sxs-lookup"><span data-stu-id="52840-132">Reduce quantity</span></span>

<span data-ttu-id="52840-133">Il terzo parametro che è possibile utilizzare durante il processo di generazione di distinte di prelievo è **Riduci quantità**.</span><span class="sxs-lookup"><span data-stu-id="52840-133">The third parameter that you can use as part of the process of generating picking lists is the **Reduce quantity** parameter.</span></span> <span data-ttu-id="52840-134">Questo parametro viene utilizzato con l'impostazione **Prenotazione** che attiva un processo di prenotazione durante il rilascio al magazzino.</span><span class="sxs-lookup"><span data-stu-id="52840-134">The setting of this parameter works together with the **Reservation** setting that triggers a reservation process as part of the release to the warehouse.</span></span>

<span data-ttu-id="52840-135">[![Parametro Riduci quantità](./media/reduce-quantity.png)](./media/reduce-quantity.png)</span><span class="sxs-lookup"><span data-stu-id="52840-135">[![Reduce quantity parameter](./media/reduce-quantity.png)](./media/reduce-quantity.png)</span></span>

## <a name="example-of-an-outbound-process-for-a-sales-order"></a><span data-ttu-id="52840-136">Esempio di un processo in uscita per un ordine cliente</span><span class="sxs-lookup"><span data-stu-id="52840-136">Example of an outbound process for a sales order</span></span>

<span data-ttu-id="52840-137">Per questo esempio, si ha un ordine cliente per due articoli.</span><span class="sxs-lookup"><span data-stu-id="52840-137">For this example, there is a sales order for two items.</span></span> <span data-ttu-id="52840-138">Durante la generazione della distinta di prelievo, si seleziona il parametro **Riduci quantità**.</span><span class="sxs-lookup"><span data-stu-id="52840-138">During picking list generation, you select the **Reduce quantity** parameter.</span></span> <span data-ttu-id="52840-139">Pertanto, si rilasciano e si creano righe di prelievo solo per le scorte disponibili.</span><span class="sxs-lookup"><span data-stu-id="52840-139">Therefore, you release and create picking lines only for available on-hand inventory.</span></span> <span data-ttu-id="52840-140">Il prelievo deve essere registrato mediante un processo di registrazione per le distinte di prelievo (**Stato ciclo di prelievo** = **Attivato**).</span><span class="sxs-lookup"><span data-stu-id="52840-140">The picking must be reported via a registration process for picking lists (**Picking route status** = **Activated**).</span></span>

<span data-ttu-id="52840-141">Le scorte che non sono ancora state prenotate lo sono durante la generazione della distinta di prelievo.</span><span class="sxs-lookup"><span data-stu-id="52840-141">The inventory that hasn't already been reserved is reserved during picking list generation.</span></span> <span data-ttu-id="52840-142">Le scorte non disponibili possono essere eliminate dall'ordine cliente o rilasciate al magazzino per l'elaborazione in uscita in seguito, quando le scorte sono disponibili per il prelievo.</span><span class="sxs-lookup"><span data-stu-id="52840-142">The unavailable inventory can be either removed from the sales order or released to the warehouse for outbound processing later, when inventory is available for picking.</span></span>

<span data-ttu-id="52840-143">[![Aggiornare la distinta di prelievo](./media/update-picking-list.png)](./media/update-picking-list.png)</span><span class="sxs-lookup"><span data-stu-id="52840-143">[![Update the picking list](./media/update-picking-list.png)](./media/update-picking-list.png)</span></span>

<span data-ttu-id="52840-144">Non appena tutte le righe di prelievo sono state selezionate nella pagina **Registrazione distinta di prelievo**, la spedizione associata viene completata.</span><span class="sxs-lookup"><span data-stu-id="52840-144">As soon as all the picking lines have been picked on the **Picking list registration** page, the associated shipment is completed.</span></span> <span data-ttu-id="52840-145">Il processo per i documenti di trasporto degli ordini cliente può quindi essere inizializzato in base alle scorte prelevate.</span><span class="sxs-lookup"><span data-stu-id="52840-145">The process for sales order packing slips can then be initialized based on the picked inventory.</span></span>

<span data-ttu-id="52840-146">[![Aggiornare spedizioni in uscita](./media/outbound-shipments.png)](./media/outbound-shipments.png)</span><span class="sxs-lookup"><span data-stu-id="52840-146">[![Update outbound shipments](./media/outbound-shipments.png)](./media/outbound-shipments.png)</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]