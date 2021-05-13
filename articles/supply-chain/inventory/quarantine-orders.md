---
title: Ordini di quarantena
description: In questo argomento viene descritto come usare gli ordini di quarantena per bloccare il magazzino.
author: perlynne
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventLocation, InventModelGroup, InventQuarantineOrder, InventQuarantineParmEnd, InventQuarantineParmReportFinished, InventQuarantineParmStartUp, InventTrans
audience: Application User
ms.reviewer: kamaybac
ms.custom: 30021
ms.assetid: d5047727-653c-49da-b489-6fd3fe50445e
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5e1eed14b7d38cf569af7192dec9580e771f06df
ms.sourcegitcommit: 8362f3bd32ce8b9a5af93c8e57daef732a93b19e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2021
ms.locfileid: "5956184"
---
# <a name="quarantine-orders"></a><span data-ttu-id="c9df6-103">Ordini di quarantena</span><span class="sxs-lookup"><span data-stu-id="c9df6-103">Quarantine orders</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c9df6-104">In questo argomento viene descritto come usare gli ordini di quarantena per bloccare il magazzino.</span><span class="sxs-lookup"><span data-stu-id="c9df6-104">This topic describes how to use quarantine orders to block inventory.</span></span>

<span data-ttu-id="c9df6-105">Gli ordini di quarantena ti consentono di bloccare il magazzino.</span><span class="sxs-lookup"><span data-stu-id="c9df6-105">Quarantine orders let you block inventory.</span></span> <span data-ttu-id="c9df6-106">Ad esempio, è possibile che si desideri mettere in quarantena gli articoli per motivi di controllo qualità.</span><span class="sxs-lookup"><span data-stu-id="c9df6-106">For example, you might want to quarantine items for quality control reasons.</span></span> <span data-ttu-id="c9df6-107">L'inventario messo in quarantena viene trasferito a un magazzino di quarantena.</span><span class="sxs-lookup"><span data-stu-id="c9df6-107">Inventory that has been quarantined is transferred to a quarantine warehouse.</span></span>

> [!NOTE]
> <span data-ttu-id="c9df6-108">Se si utilizzano processi di gestione avanzata del magazzino (in Gestione magazzino), l'elaborazione degli ordini di quarantena viene utilizzata solo per gli ordini cliente resi.</span><span class="sxs-lookup"><span data-stu-id="c9df6-108">If you're using advanced warehouse management processes (in Warehouse management), quarantine order processing is used only for return sales orders.</span></span>

## <a name="quarantine-on-hand-inventory-items"></a><span data-ttu-id="c9df6-109">Quarantena degli articoli di magazzino disponibili</span><span class="sxs-lookup"><span data-stu-id="c9df6-109">Quarantine on-hand inventory items</span></span>

<span data-ttu-id="c9df6-110">Quando si mettono articoli in quarantena, è possibile creare ordini di quarantena manualmente o impostare il sistema in modo da creare ordini di quarantena automaticamente durante l'elaborazione in entrata.</span><span class="sxs-lookup"><span data-stu-id="c9df6-110">When you quarantine items, you can either manually create the quarantine orders or set up the system to automatically create them during inbound processing.</span></span>

<span data-ttu-id="c9df6-111">Per configurare il sistema in modo che generi automaticamente ordini di quarantena, segui questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="c9df6-111">To set up the system to automatically generate quarantine orders, follow these steps.</span></span>

1. <span data-ttu-id="c9df6-112">Andare a **Gestione articoli \> Impostazioni \> Scorte \> Gruppi di modelli di articoli**.</span><span class="sxs-lookup"><span data-stu-id="c9df6-112">Go to **Inventory management \> Setup \> Inventory \> Item model groups**.</span></span>
1. <span data-ttu-id="c9df6-113">Selezionare un gruppo di modelli pertinente nel riquadro elenco o creare un nuovo gruppo di modelli.</span><span class="sxs-lookup"><span data-stu-id="c9df6-113">Select a relevant model group in the list pane, or create a new model group.</span></span>
1. <span data-ttu-id="c9df6-114">Nella Scheda dettaglio **Criteri di inventario**, selezionare la casella di controllo **Gestione quarantena**.</span><span class="sxs-lookup"><span data-stu-id="c9df6-114">On the **Inventory policies** FastTab, select the **Quarantine management** check box.</span></span>
1. <span data-ttu-id="c9df6-115">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="c9df6-115">Close the page.</span></span>
1. <span data-ttu-id="c9df6-116">Specificare un magazzino di quarantena predefinito nel campo **Magazzino di quarantena**.</span><span class="sxs-lookup"><span data-stu-id="c9df6-116">In the **Quarantine warehouse** field for the receiving warehouses, specify a default quarantine warehouse.</span></span>

<span data-ttu-id="c9df6-117">Quando un articolo registrato come ricevuto in magazzino appartiene a un gruppo di modelli in cui la casella di controllo **Gestione quarantena** è selezionata, il sistema genera un ordine di quarantena per esso.</span><span class="sxs-lookup"><span data-stu-id="c9df6-117">When an item that is registered as received at the warehouse belongs to a model group where the **Quarantine management** check box is selected, the system generates a quarantine order for it.</span></span> <span data-ttu-id="c9df6-118">L'ordine di quarantena indica ai lavoratori di spostare l'articolo nel magazzino di quarantena.</span><span class="sxs-lookup"><span data-stu-id="c9df6-118">The quarantine order instructs workers to move the item to the quarantine warehouse.</span></span>

<span data-ttu-id="c9df6-119">Quando si creano manualmente ordini di quarantena nella pagina **Ordini di quarantena**, non è necessario che l'articolo venga impostato per la gestione della quarantena nel gruppo di modelli di articoli associato.</span><span class="sxs-lookup"><span data-stu-id="c9df6-119">When you manually create quarantine orders on the **Quarantine orders** page, the item doesn't have to be set up for quarantine management in the associated item model group.</span></span> <span data-ttu-id="c9df6-120">Per questo processo, è necessario specificare il magazzino disponibile che deve essere messo in quarantena e il magazzino di quarantena che deve essere utilizzato.</span><span class="sxs-lookup"><span data-stu-id="c9df6-120">For this process, you must specify the on-hand inventory that should be quarantined and the quarantine warehouse that should be used.</span></span> <span data-ttu-id="c9df6-121">È possibile utilizzare gli stati dell'ordine di quarantena per pianificare il processo.</span><span class="sxs-lookup"><span data-stu-id="c9df6-121">You can use the quarantine order statuses to help plan the process.</span></span>

## <a name="quarantine-order-statuses"></a><span data-ttu-id="c9df6-122">Stati dell'ordine di quarantena</span><span class="sxs-lookup"><span data-stu-id="c9df6-122">Quarantine order statuses</span></span>

<span data-ttu-id="c9df6-123">Agli ordini di quarantena possono essere assegnati i seguenti stati:</span><span class="sxs-lookup"><span data-stu-id="c9df6-123">Quarantine orders can have the following statuses:</span></span>

- <span data-ttu-id="c9df6-124">Creata</span><span class="sxs-lookup"><span data-stu-id="c9df6-124">Created</span></span>
- <span data-ttu-id="c9df6-125">Avviato</span><span class="sxs-lookup"><span data-stu-id="c9df6-125">Started</span></span>
- <span data-ttu-id="c9df6-126">Dichiarato finito</span><span class="sxs-lookup"><span data-stu-id="c9df6-126">Reported as finished</span></span>
- <span data-ttu-id="c9df6-127">Operazione terminata</span><span class="sxs-lookup"><span data-stu-id="c9df6-127">Ended</span></span>

### <a name="created"></a><span data-ttu-id="c9df6-128">Creata</span><span class="sxs-lookup"><span data-stu-id="c9df6-128">Created</span></span>

<span data-ttu-id="c9df6-129">Quando un ordine di quarantena viene creato manualmente ma l'articolo non è ancora nel magazzino di quarantena, l'ordine di quarantena presenta lo stato **Creato**.</span><span class="sxs-lookup"><span data-stu-id="c9df6-129">When a quarantine order has been created manually, but the item isn't yet in the quarantine warehouse, the quarantine order has a status of **Created**.</span></span> <span data-ttu-id="c9df6-130">Vengono generate due transazioni di magazzino.</span><span class="sxs-lookup"><span data-stu-id="c9df6-130">Two inventory transactions are generated.</span></span> <span data-ttu-id="c9df6-131">Una transazione è una transazione di uscita con lo stato **In ordinazione**, **Fisico prenotato** o **Prelevata**.</span><span class="sxs-lookup"><span data-stu-id="c9df6-131">One transaction is an issue transaction that can have a status of **On order**, **Reserved physical**, or **Picked**.</span></span> <span data-ttu-id="c9df6-132">L'altra transazione è una transazione di entrata con lo stato **Ordinato** o **Registrato** presso il magazzino in quarantena.</span><span class="sxs-lookup"><span data-stu-id="c9df6-132">The other transaction is a receipt transaction that can have a status of **Ordered** or **Registered** at the quarantine warehouse.</span></span> <span data-ttu-id="c9df6-133">È possibile prenotare, prelevare e registrare aggiornamenti al magazzino utilizzando i soliti processi.</span><span class="sxs-lookup"><span data-stu-id="c9df6-133">You can reserve, pick, and register updates to the inventory by using the usual processes.</span></span>

### <a name="started"></a><span data-ttu-id="c9df6-134">Avviato</span><span class="sxs-lookup"><span data-stu-id="c9df6-134">Started</span></span>

<span data-ttu-id="c9df6-135">Quando un ordine di quarantena presenta lo stato **Avviato**, gli articoli di magazzino vengono trasferiti dal normale magazzino al magazzino di quarantena e vengono generate due transazioni di magazzino.</span><span class="sxs-lookup"><span data-stu-id="c9df6-135">When a quarantine order has a status of **Started**, the inventory is transferred from the regular warehouse to the quarantine warehouse, and two inventory transactions are generated.</span></span> <span data-ttu-id="c9df6-136">Una transazione ha lo stato di **Detratto** e l'altra ha lo stato di **Ricevuto**.</span><span class="sxs-lookup"><span data-stu-id="c9df6-136">One transaction has a status of **Deducted**, and the other transaction has a status of **Received**.</span></span> <span data-ttu-id="c9df6-137">Contemporaneamente vengono generate due operazioni di magazzino per la gestione del trasferimento del reso.</span><span class="sxs-lookup"><span data-stu-id="c9df6-137">At the same time, two inventory transactions are created to handle the return transfer.</span></span> <span data-ttu-id="c9df6-138">Queste transazioni non sono datate.</span><span class="sxs-lookup"><span data-stu-id="c9df6-138">These transactions aren't dated.</span></span> <span data-ttu-id="c9df6-139">Una transazione ha lo stato di **Fisico prenotato** e l'altra ha lo stato di **Ordinato**.</span><span class="sxs-lookup"><span data-stu-id="c9df6-139">One transaction has a status of **Reserved physical**, and the other transaction has a status of **Ordered**.</span></span>

### <a name="reported-as-finished"></a><span data-ttu-id="c9df6-140">Dichiarato finito</span><span class="sxs-lookup"><span data-stu-id="c9df6-140">Reported as finished</span></span>

<span data-ttu-id="c9df6-141">Per segnalare un ordine di quarantena avviato come finito, apri l'ordine e seleziona **Dichiarato finito** nel riquadro azioni.</span><span class="sxs-lookup"><span data-stu-id="c9df6-141">To report a started quarantine order as finished, open the order, and select **Report as finished** on the Action Pane.</span></span> <span data-ttu-id="c9df6-142">L'articolo viene rilasciato dalla quarantena, ma non viene ancora ritrasferito al magazzino normale.</span><span class="sxs-lookup"><span data-stu-id="c9df6-142">The item is released from quarantine, but it isn't yet moved back to the regular warehouse.</span></span> <span data-ttu-id="c9df6-143">Il movimento al magazzino normale può essere elaborato tramite un giornale di registrazione arrivi articoli che può essere inizializzato durante il processo di dichiarazione finito.</span><span class="sxs-lookup"><span data-stu-id="c9df6-143">The movement back to the regular warehouse can be processed via an item arrival journal that can be initialized during the report as finished process.</span></span>

### <a name="ended"></a><span data-ttu-id="c9df6-144">Terminato</span><span class="sxs-lookup"><span data-stu-id="c9df6-144">Ended</span></span>

<span data-ttu-id="c9df6-145">Quando un ordine di quarantena viene terminato, l'articolo viene spostato dal magazzino di quarantena al magazzino normale.</span><span class="sxs-lookup"><span data-stu-id="c9df6-145">When a quarantine order is ended, the item is moved from the quarantine warehouse back to the regular warehouse.</span></span> <span data-ttu-id="c9df6-146">Lo stato della transazione dell'articolo viene impostato su *Venduto* nel magazzino di quarantena e su *Acquistato* nel magazzino normale.</span><span class="sxs-lookup"><span data-stu-id="c9df6-146">The status of the item transaction is set to *Sold* at the quarantine warehouse and *Purchased* at the regular warehouse.</span></span>

## <a name="quarantine-order-scrap"></a><span data-ttu-id="c9df6-147">Scarti ordine di quarantena</span><span class="sxs-lookup"><span data-stu-id="c9df6-147">Quarantine order scrap</span></span>

<span data-ttu-id="c9df6-148">Nell'ambito dell'elaborazione dell'ordine di quarantena è possibile scartare le scorte.</span><span class="sxs-lookup"><span data-stu-id="c9df6-148">As part of the quarantine order process, you can scrap inventory.</span></span> <span data-ttu-id="c9df6-149">In questa fase, lo stato degli articoli di magazzino è impostati su *Venduto* tramite una transazione di uscita dal magazzino di quarantena.</span><span class="sxs-lookup"><span data-stu-id="c9df6-149">When you process scrap, the status of the inventory is set to *Sold* by an issue transaction from the quarantine warehouse.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c9df6-150">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="c9df6-150">Additional resources</span></span>

- [<span data-ttu-id="c9df6-151">Blocco scorte</span><span class="sxs-lookup"><span data-stu-id="c9df6-151">Inventory blocking</span></span>](inventory-blocking.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
