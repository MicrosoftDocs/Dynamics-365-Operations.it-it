---
title: Ordini di quarantena
description: In questo argomento viene descritto il modo in cui gli ordini di quarantena vengono utilizzati per bloccare il magazzino.
author: perlynne
manager: AnnBe
ms.date: 11/02/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventLocation, InventModelGroup, InventQuarantineOrder, InventQuarantineParmEnd, InventQuarantineParmReportFinished, InventQuarantineParmStartUp, InventTrans
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 30021
ms.assetid: d5047727-653c-49da-b489-6fd3fe50445e
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: 523e51c705d76b6e8624887292395f8f239bcb65
ms.contentlocale: it-it
ms.lasthandoff: 08/07/2018

---

# <a name="quarantine-orders"></a><span data-ttu-id="1eeec-103">Ordini di quarantena</span><span class="sxs-lookup"><span data-stu-id="1eeec-103">Quarantine orders</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="1eeec-104">In questo argomento viene descritto il modo in cui gli ordini di quarantena vengono utilizzati per bloccare il magazzino.</span><span class="sxs-lookup"><span data-stu-id="1eeec-104">This topic describes how quarantine orders are used to block inventory.</span></span>

<span data-ttu-id="1eeec-105">Gli ordini di quarantena possono essere utilizzati per bloccare il magazzino.</span><span class="sxs-lookup"><span data-stu-id="1eeec-105">Quarantine orders can be used to block inventory.</span></span> <span data-ttu-id="1eeec-106">Ad esempio, è possibile che si desideri mettere in quarantena gli articoli per motivi di controllo qualità.</span><span class="sxs-lookup"><span data-stu-id="1eeec-106">For example, you might want to quarantine items for quality control reasons.</span></span> <span data-ttu-id="1eeec-107">L'inventario messo in quarantena viene trasferito a un magazzino di quarantena.</span><span class="sxs-lookup"><span data-stu-id="1eeec-107">Inventory that has been quarantined is transferred to a quarantine warehouse.</span></span> <span data-ttu-id="1eeec-108">**Nota:** se si utilizzano processi di gestione avanzata del magazzino (in Gestione magazzino), l'elaborazione degli ordini di quarantena viene utilizzata solo per gli ordini cliente resi.</span><span class="sxs-lookup"><span data-stu-id="1eeec-108">**Note:** If you're using advanced warehouse management processes (in Warehouse management), quarantine order processing is used only for return sales orders.</span></span>

## <a name="quarantine-on-hand-inventory-items"></a><span data-ttu-id="1eeec-109">Quarantena degli articoli di magazzino disponibili</span><span class="sxs-lookup"><span data-stu-id="1eeec-109">Quarantine on-hand inventory items</span></span>
<span data-ttu-id="1eeec-110">Quando si mettono articoli in quarantena, è possibile creare ordini di quarantena manualmente o impostare il sistema in modo da creare ordini di quarantena automaticamente durante l'elaborazione in entrata.</span><span class="sxs-lookup"><span data-stu-id="1eeec-110">When you quarantine items, you can either create the quarantine orders manually or set up the system to create the quarantine orders automatically during inbound processing.</span></span> <span data-ttu-id="1eeec-111">Per creare automaticamente ordini di quarantena, selezionare l'opzione **Gestione quarantena** nella scheda **Criteri di inventario** nella pagina **Gruppi di modelli di articoli**.</span><span class="sxs-lookup"><span data-stu-id="1eeec-111">To create quarantine orders automatically, select the **Quarantine management** option on the **Inventory policies** tab on the **Item model groups** page.</span></span> <span data-ttu-id="1eeec-112">È anche necessario specificare un magazzino di quarantena predefinito nel campo **Magazzino di quarantena** per i magazzini riceventi.</span><span class="sxs-lookup"><span data-stu-id="1eeec-112">You must also specify a default quarantine warehouse in the **Quarantine warehouse** field for the receiving warehouses.</span></span> <span data-ttu-id="1eeec-113">Quando gli articoli di magazzino fisicamente disponibili vengono registrati in un ordine fornitore o di produzione, gli articoli in quarantena vengono spostati automaticamente in un magazzino di quarantena in Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="1eeec-113">When the physically on-hand inventory is recorded in a purchase order or production order, quarantined items are automatically moved to a quarantine warehouse in Microsoft Dynamics 365 for Finance and Operations.</span></span> <span data-ttu-id="1eeec-114">Il movimento si verifica perché lo stato dell'ordine di quarantena viene modificato su **Iniziato**.</span><span class="sxs-lookup"><span data-stu-id="1eeec-114">This movement occurs because the status of the quarantine order is changed to **Started**.</span></span> <span data-ttu-id="1eeec-115">Quando si creano manualmente ordini di quarantena, non è necessario che l'articolo venga impostato per la gestione della quarantena nel gruppo di modelli dell'articolo associato.</span><span class="sxs-lookup"><span data-stu-id="1eeec-115">When you create quarantine orders manually, the item doesn't have to be set up for quarantine management in the associated item model group.</span></span> <span data-ttu-id="1eeec-116">Per questo processo, è necessario specificare il magazzino disponibile che deve essere messo in quarantena e il magazzino di quarantena che deve essere utilizzato.</span><span class="sxs-lookup"><span data-stu-id="1eeec-116">For this process, you must specify the on-hand inventory that should be quarantined and the quarantine warehouse that should be used.</span></span> <span data-ttu-id="1eeec-117">È possibile utilizzare gli stati dell'ordine di quarantena per pianificare il processo.</span><span class="sxs-lookup"><span data-stu-id="1eeec-117">You can use the quarantine order statuses to help plan the process.</span></span>

## <a name="quarantine-order-statuses"></a><span data-ttu-id="1eeec-118">Stati dell'ordine di quarantena</span><span class="sxs-lookup"><span data-stu-id="1eeec-118">Quarantine order statuses</span></span>
<span data-ttu-id="1eeec-119">Agli ordini di quarantena possono essere assegnati i seguenti stati:</span><span class="sxs-lookup"><span data-stu-id="1eeec-119">Quarantine orders can have the following statuses:</span></span>

-   <span data-ttu-id="1eeec-120">Creata</span><span class="sxs-lookup"><span data-stu-id="1eeec-120">Created</span></span>
-   <span data-ttu-id="1eeec-121">Avviato</span><span class="sxs-lookup"><span data-stu-id="1eeec-121">Started</span></span>
-   <span data-ttu-id="1eeec-122">Dichiarato finito</span><span class="sxs-lookup"><span data-stu-id="1eeec-122">Reported as finished</span></span>
-   <span data-ttu-id="1eeec-123">Operazione terminata</span><span class="sxs-lookup"><span data-stu-id="1eeec-123">Ended</span></span>

### <a name="created"></a><span data-ttu-id="1eeec-124">Creata</span><span class="sxs-lookup"><span data-stu-id="1eeec-124">Created</span></span>

<span data-ttu-id="1eeec-125">Quando un ordine di quarantena viene creato manualmente ma l'articolo non è ancora nel magazzino di quarantena, l'ordine di quarantena presenta lo stato **Creato**.</span><span class="sxs-lookup"><span data-stu-id="1eeec-125">When a quarantine order has been created manually, but the item isn't yet in the quarantine warehouse, the quarantine order has a status of **Created**.</span></span> <span data-ttu-id="1eeec-126">Vengono generate due transazioni di magazzino.</span><span class="sxs-lookup"><span data-stu-id="1eeec-126">Two inventory transactions are generated.</span></span> <span data-ttu-id="1eeec-127">Una transazione è una transazione di uscita con lo stato **In ordinazione**, **Fisico prenotato** o **Prelevata**.</span><span class="sxs-lookup"><span data-stu-id="1eeec-127">One transaction is an issue transaction that can have a status of **On order**, **Reserved physical**, or **Picked**.</span></span> <span data-ttu-id="1eeec-128">L'altra transazione è una transazione di entrata con lo stato **Ordinato** o **Registrato** presso il magazzino in quarantena.</span><span class="sxs-lookup"><span data-stu-id="1eeec-128">The other transaction is a receipt transaction that can have a status of **Ordered** or **Registered** at the quarantine warehouse.</span></span> <span data-ttu-id="1eeec-129">È possibile prenotare, prelevare e registrare aggiornamenti al magazzino utilizzando i soliti processi.</span><span class="sxs-lookup"><span data-stu-id="1eeec-129">You can reserve, pick, and register updates to the inventory by using the usual processes.</span></span>

### <a name="started"></a><span data-ttu-id="1eeec-130">Avviato</span><span class="sxs-lookup"><span data-stu-id="1eeec-130">Started</span></span>

<span data-ttu-id="1eeec-131">Quando un ordine di quarantena presenta lo stato **Avviato**, gli articoli di magazzino vengono trasferiti dal normale magazzino al magazzino di quarantena e vengono generate due transazioni di magazzino.</span><span class="sxs-lookup"><span data-stu-id="1eeec-131">When a quarantine order has a status of **Started**, the inventory is transferred from the regular warehouse to the quarantine warehouse, and two inventory transactions are generated.</span></span> <span data-ttu-id="1eeec-132">Una transazione ha lo stato di **Detratto** e l'altra ha lo stato di **Ricevuto**.</span><span class="sxs-lookup"><span data-stu-id="1eeec-132">One transaction has a status of **Deducted**, and the other transaction has a status of **Received**.</span></span> <span data-ttu-id="1eeec-133">Contemporaneamente vengono generate due operazioni di magazzino per la gestione del trasferimento del reso.</span><span class="sxs-lookup"><span data-stu-id="1eeec-133">At the same time, two inventory transactions are created to handle the return transfer.</span></span> <span data-ttu-id="1eeec-134">Queste transazioni non sono datate.</span><span class="sxs-lookup"><span data-stu-id="1eeec-134">These transactions aren't dated.</span></span> <span data-ttu-id="1eeec-135">Una transazione ha lo stato di **Fisico prenotato** e l'altra ha lo stato di **Ordinato**.</span><span class="sxs-lookup"><span data-stu-id="1eeec-135">One transaction has a status of **Reserved physical**, and the other transaction has a status of **Ordered**.</span></span>

### <a name="reported-as-finished"></a><span data-ttu-id="1eeec-136">Dichiarato finito</span><span class="sxs-lookup"><span data-stu-id="1eeec-136">Reported as finished</span></span>

<span data-ttu-id="1eeec-137">Se si fa clic su **Dichiarazione di finito**, è possibile dichiarare che un ordine di quarantena avviato è finito.</span><span class="sxs-lookup"><span data-stu-id="1eeec-137">By clicking **Report as finished**, you can report a started quarantine order as finished.</span></span> <span data-ttu-id="1eeec-138">L'articolo viene rilasciato dalla quarantena, ma non viene ancora ritrasferito al magazzino normale.</span><span class="sxs-lookup"><span data-stu-id="1eeec-138">The item is released from quarantine but isn't yet moved back to the regular warehouse.</span></span> <span data-ttu-id="1eeec-139">Il movimento al magazzino normale può essere elaborato tramite un giornale di registrazione arrivi articoli che può essere inizializzato durante il processo di dichiarazione finito.</span><span class="sxs-lookup"><span data-stu-id="1eeec-139">The movement back to the regular warehouse can be processed via an Item arrival journal that can be initialized during the Report as finished process.</span></span>

### <a name="ended"></a><span data-ttu-id="1eeec-140">Operazione terminata</span><span class="sxs-lookup"><span data-stu-id="1eeec-140">Ended</span></span>

<span data-ttu-id="1eeec-141">Quando un ordine di quarantena viene terminato, l'articolo viene spostato dal magazzino di quarantena al magazzino normale.</span><span class="sxs-lookup"><span data-stu-id="1eeec-141">When a quarantine order is ended, the item is moved from the quarantine warehouse back to the regular warehouse.</span></span> <span data-ttu-id="1eeec-142">Lo stato della transazione dell'articolo viene impostato su **Venduto** nel magazzino di quarantena e su **Acquistato** nel magazzino normale.</span><span class="sxs-lookup"><span data-stu-id="1eeec-142">The status of the item transaction is set to **Sold** at the quarantine warehouse and **Purchased** at the regular warehouse.</span></span>

## <a name="quarantine-order-scrap"></a><span data-ttu-id="1eeec-143">Scarti ordine di quarantena</span><span class="sxs-lookup"><span data-stu-id="1eeec-143">Quarantine order scrap</span></span>
<span data-ttu-id="1eeec-144">Nell'ambito dell'elaborazione dell'ordine di quarantena è possibile scartare le scorte.</span><span class="sxs-lookup"><span data-stu-id="1eeec-144">As part of the quarantine order process, you can scrap inventory.</span></span> <span data-ttu-id="1eeec-145">In questa fase, lo stato degli articoli di magazzino sono impostati su **Venduto** tramite una transazione di uscita dal magazzino di quarantena.</span><span class="sxs-lookup"><span data-stu-id="1eeec-145">When you process scrap, the status of the inventory will be set to **Sold** by an issue transaction from the quarantine warehouse.</span></span>

<a name="additional-resources"></a><span data-ttu-id="1eeec-146">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="1eeec-146">Additional resources</span></span>
--------

[<span data-ttu-id="1eeec-147">Blocco scorte</span><span class="sxs-lookup"><span data-stu-id="1eeec-147">Inventory blocking</span></span>](inventory-blocking.md)

