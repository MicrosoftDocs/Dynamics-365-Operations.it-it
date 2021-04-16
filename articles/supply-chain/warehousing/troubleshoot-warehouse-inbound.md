---
title: Risolvere i problemi relativi alle operazioni di magazzino in entrata
description: Questo argomento descrive come risolvere i problemi comuni che si possono verificare quando si utilizzano le operazioni di magazzino in entrata in Microsoft Dynamics 365 Supply Chain Management.
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
ms.openlocfilehash: f0ea2ee208cdbb8f9fa6668bbcb6e15252a7c1b1
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5828228"
---
# <a name="troubleshoot-inbound-warehouse-operations"></a><span data-ttu-id="1ba65-103">Risolvere i problemi relativi alle operazioni di magazzino in entrata</span><span class="sxs-lookup"><span data-stu-id="1ba65-103">Troubleshoot inbound warehouse operations</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="1ba65-104">Questo argomento descrive come risolvere i problemi comuni che si possono verificare quando si utilizzano le operazioni di magazzino in entrata in Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="1ba65-104">This topic describes how to fix common issues that you might encounter while you work with inbound warehouse operations in Microsoft Dynamics 365 Supply Chain Management.</span></span>

## <a name="i-receive-the-following-error-message-quality-order-1-has-been-generated-cluster-profile-could-not-be-found-please-check-your-configuration"></a><span data-ttu-id="1ba65-105">Viene visualizzato il seguente messaggio di errore: "Ordine di controllo qualità %1 è stato generato.</span><span class="sxs-lookup"><span data-stu-id="1ba65-105">I receive the following error message: "Quality order %1 has been generated.</span></span> <span data-ttu-id="1ba65-106">Impossibile trovare il profilo cluster per verificare la configurazione."</span><span class="sxs-lookup"><span data-stu-id="1ba65-106">Cluster profile could not be found please check your configuration."</span></span>

### <a name="issue-description"></a><span data-ttu-id="1ba65-107">Descrizione del problema</span><span class="sxs-lookup"><span data-stu-id="1ba65-107">Issue description</span></span>

<span data-ttu-id="1ba65-108">Questo messaggio di errore è correlato a un processo di ricezione in cui è attivata la gestione della qualità (QMS).</span><span class="sxs-lookup"><span data-stu-id="1ba65-108">This error message is related to a receiving process where quality management (QMS) is turned on.</span></span> <span data-ttu-id="1ba65-109">A seconda delle configurazioni nel proprio ambiente, ulteriori dettagli sulla transazione che sta generando il messaggio di errore potrebbero aiutare a risolvere il problema.</span><span class="sxs-lookup"><span data-stu-id="1ba65-109">Depending on the configurations in your environment, additional details about the transaction that is generating the error message might help fix the issue.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="1ba65-110">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="1ba65-110">Issue resolution</span></span>

<span data-ttu-id="1ba65-111">Innanzitutto, esaminare l'impostazione di [prelievo cluster](set-up-cluster-picking.md) e assicurarsi che i profili del cluster siano impostati correttamente.</span><span class="sxs-lookup"><span data-stu-id="1ba65-111">First, review the [cluster picking](set-up-cluster-picking.md) setup, and make sure that your cluster profiles are set up correctly.</span></span> <span data-ttu-id="1ba65-112">Non è possibile utilizzare una voce di menu del dispositivo mobile per la selezione del cluster a meno che non siano stati configurati i profili del cluster.</span><span class="sxs-lookup"><span data-stu-id="1ba65-112">You can't use a mobile device menu item for cluster picking unless cluster profiles are set up.</span></span> <span data-ttu-id="1ba65-113">A seconda del proprio ambiente, potrebbe essere necessario rivedere anche altre configurazioni correlate.</span><span class="sxs-lookup"><span data-stu-id="1ba65-113">Depending on your environment, you might also have to review other related configurations.</span></span>

## <a name="mixed-license-plate-receiving-doesnt-work-for-any-disposition-code-except-credit"></a><span data-ttu-id="1ba65-114">La ricezione di targhe miste non funziona per nessun codice smaltimento eccetto il credito.</span><span class="sxs-lookup"><span data-stu-id="1ba65-114">Mixed license plate receiving doesn't work for any disposition code except Credit.</span></span>

### <a name="issue-description"></a><span data-ttu-id="1ba65-115">Descrizione del problema</span><span class="sxs-lookup"><span data-stu-id="1ba65-115">Issue description</span></span>

<span data-ttu-id="1ba65-116">Quando il campo **Azione** per un codice smaltimento è impostato su *Credito* o *Scarti*, è possibile usare solo la voce di menu [Ricevimento targa mista](mixed-license-plate-receiving.md) per elaborare gli articoli restituiti.</span><span class="sxs-lookup"><span data-stu-id="1ba65-116">When the **Action** field for a disposition code is set to *Credit* or *Scrap*, you can use only the [Mixed license plate receiving](mixed-license-plate-receiving.md) menu item to process returned items.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="1ba65-117">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="1ba65-117">Issue resolution</span></span>

<span data-ttu-id="1ba65-118">Microsoft ha valutato questo problema e ha stabilito che si tratta di una limitazione delle funzionalità.</span><span class="sxs-lookup"><span data-stu-id="1ba65-118">Microsoft has evaluated this issue and has determined that it's a feature limitation.</span></span> <span data-ttu-id="1ba65-119">Attualmente solo i [codici smaltimento](../service-management/set-up-disposition-codes.md) dove il campo **Azione** è impostato su *Credito* o *Scarti* sono supportati per la ricezione di targhe miste.</span><span class="sxs-lookup"><span data-stu-id="1ba65-119">Currently, only [disposition codes](../service-management/set-up-disposition-codes.md) where the **Action** field is set to *Credit* or *Scrap* are supported for mixed license plate receiving.</span></span>

## <a name="when-i-run-the-update-product-receipts-periodic-task-unconfirmed-purchase-orders-are-confirmed"></a><span data-ttu-id="1ba65-120">Quando si esegue l'attività periodica Aggiorna entrate prodotti, vengono confermati gli ordini fornitore non confermati.</span><span class="sxs-lookup"><span data-stu-id="1ba65-120">When I run the Update product receipts periodic task, unconfirmed purchase orders are confirmed.</span></span>

### <a name="issue-description"></a><span data-ttu-id="1ba65-121">Descrizione del problema</span><span class="sxs-lookup"><span data-stu-id="1ba65-121">Issue description</span></span>

<span data-ttu-id="1ba65-122">Dopo aver eseguito l'attività periodica *Aggiorna entrate prodotti*, il sistema conferma automaticamente gli ordini fornitore non confermati con stato di transazione di magazzino *Registrato*.</span><span class="sxs-lookup"><span data-stu-id="1ba65-122">After you run the *Update product receipts* periodic task, the system automatically confirms unconfirmed purchase orders that have an inventory transaction status of *Registered*.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="1ba65-123">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="1ba65-123">Issue resolution</span></span>

<span data-ttu-id="1ba65-124">Una nuova funzione di gestione del carico in entrata, *Entrata in eccesso di quantità di carico*, risolve questo problema.</span><span class="sxs-lookup"><span data-stu-id="1ba65-124">A new inbound load handling feature, *Over receipt of load quantities*, fixes this issue.</span></span> <span data-ttu-id="1ba65-125">Per attivare questa funzionalità andare in [Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) per attivare le seguenti funzionalità (in questo ordine):</span><span class="sxs-lookup"><span data-stu-id="1ba65-125">To turn on this feature, go to [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), and turn on the following features (in the order that they are listed in):</span></span>

1. <span data-ttu-id="1ba65-126">Associa operazioni di magazzino ordine fornitore con carico</span><span class="sxs-lookup"><span data-stu-id="1ba65-126">Associate purchase order inventory transactions with load</span></span>
1. <span data-ttu-id="1ba65-127">Entrata in eccesso di quantità di carico</span><span class="sxs-lookup"><span data-stu-id="1ba65-127">Over receipt of load quantities</span></span>

<span data-ttu-id="1ba65-128">Per ulteriori informazioni, vedere [Registrare le quantità di prodotto registrate rispetto a ordini fornitore](inbound-load-handling.md#post-registered-quantities).</span><span class="sxs-lookup"><span data-stu-id="1ba65-128">For more information, see [Post registered product quantities against purchase orders](inbound-load-handling.md#post-registered-quantities).</span></span>

## <a name="when-i-register-inbound-orders-i-receive-the-following-error-message-the-quantity-is-not-valid"></a><span data-ttu-id="1ba65-129">Quando registro gli ordini in entrata, ricevo il seguente messaggio di errore: "La quantità non è valida".</span><span class="sxs-lookup"><span data-stu-id="1ba65-129">When I register inbound orders, I receive the following error message: "The quantity is not valid."</span></span>

### <a name="issue-description"></a><span data-ttu-id="1ba65-130">Descrizione del problema</span><span class="sxs-lookup"><span data-stu-id="1ba65-130">Issue description</span></span>

<span data-ttu-id="1ba65-131">Se il campo **Criteri di raggruppamento delle targhe** è impostato su *Definito dall'utente* per una voce di menu del dispositivo mobile utilizzata per registrare gli ordini in entrata, viene visualizzato un messaggio di errore ("La quantità non è valida") e non è possibile completare la registrazione.</span><span class="sxs-lookup"><span data-stu-id="1ba65-131">If the **License plate grouping policy** field is set to *User defined* for a mobile device menu item that is used to register inbound orders, you receive an error message ("The quantity is not valid"), and you can't complete the registration.</span></span>

### <a name="issue-cause"></a><span data-ttu-id="1ba65-132">Causa del problema</span><span class="sxs-lookup"><span data-stu-id="1ba65-132">Issue cause</span></span>

<span data-ttu-id="1ba65-133">Quando *Definito dall'utente* viene utilizzato come criterio di raggruppamento delle targhe, il sistema suddivide l'inventario in entrata in targhe separate, come indicato dal gruppo di sequenze unità.</span><span class="sxs-lookup"><span data-stu-id="1ba65-133">When *User defined* is used as a license plate grouping policy, the system splits the incoming inventory into separate license plates, as indicated by the unit sequence group.</span></span> <span data-ttu-id="1ba65-134">Se vengono utilizzati numeri di batch o di serie per tenere traccia dell'articolo ricevuto, le quantità di ciascun batch o serie devono essere specificate per targa registrata.</span><span class="sxs-lookup"><span data-stu-id="1ba65-134">If batch or serial numbers are used to track the item that is being received, the quantities of each batch or serial must be specified per license plate that is registered.</span></span> <span data-ttu-id="1ba65-135">Se la quantità specificata per una targa supera la quantità che deve ancora essere ricevuta per le dimensioni correnti, viene visualizzato il messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="1ba65-135">If the quantity that is specified for a license plate exceeds the quantity that must still be received for the current dimensions, you receive the error message.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="1ba65-136">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="1ba65-136">Issue resolution</span></span>

<span data-ttu-id="1ba65-137">Quando registri un artciolo utilizzando una voce di menu del dispositivo mobile in cui il campo **Criterio di raggruppamento delle targhe** è impostato su *Definito dall'utente*, il sistema potrebbe richiedere la conferma o l'immissione di numeri di targa, numeri di lotto o numeri di serie.</span><span class="sxs-lookup"><span data-stu-id="1ba65-137">When you register an item by using a mobile device menu item where the **License plate grouping policy** field is set to *User defined*, the system might require that you confirm or enter license plate numbers, batch numbers, or serial numbers.</span></span>

<span data-ttu-id="1ba65-138">Nella pagina di conferma della targa, il sistema mostrerà la quantità allocata per la targa corrente.</span><span class="sxs-lookup"><span data-stu-id="1ba65-138">On the license plate confirmation page, the system will show the quantity that is allocated for the current license plate.</span></span> <span data-ttu-id="1ba65-139">Sulle pagine di conferma del batch o della serie, il sistema mostrerà la quantità che deve ancora essere ricevuta sulla targa corrente.</span><span class="sxs-lookup"><span data-stu-id="1ba65-139">On the batch or serial confirmation pages, the system will show the quantity that must still be received on the current license plate.</span></span> <span data-ttu-id="1ba65-140">Comprenderà anche un campo in cui è possibile inserire la quantità da registrare per quella combinazione di targa e batch o numero di serie.</span><span class="sxs-lookup"><span data-stu-id="1ba65-140">It will also include a field where you can enter the quantity to register for that combination of license plate and batch or serial number.</span></span> <span data-ttu-id="1ba65-141">In questo caso, assicurati che la quantità che si sta registrando per la targa non superi la quantità che deve ancora essere ricevuta.</span><span class="sxs-lookup"><span data-stu-id="1ba65-141">In this case, make sure that the quantity that is being registered for the license plate doesn't exceed the quantity that must still be received.</span></span>

<span data-ttu-id="1ba65-142">In alternativa, se vengono generate troppe targhe durante la registrazione dell'ordine in entrata, il valore del campo **Criterio di raggruppamento delle targhe** può essere modificato in *Raggruppamento targhe*, è possibile assegnare un nuovo gruppo di sequenze di unità all'articolo o l'opzione **Raggruppamento targhe** per il gruppo di sequenze di unità può essere disattivata.</span><span class="sxs-lookup"><span data-stu-id="1ba65-142">Alternatively, if too many license plates are being generated on inbound order registration, the value of the **License plate grouping policy** field can be changed to *License plate grouping*, a new unit sequence group can be assigned to the item, or the **License plate grouping** option for the unit sequence group can be inactivated.</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
