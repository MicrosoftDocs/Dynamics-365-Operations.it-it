---
title: Risolvere i problemi di allestimento del carico e spedizioni
description: Questo argomento descrive come risolvere i problemi comuni che si possono verificare quando si utilizza l'allestimento del carico e le spedizioni in Microsoft Dynamics 365 Supply Chain Management.
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
ms.openlocfilehash: e9964376a794661058da78152879d2142dd7ec51
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5828204"
---
# <a name="troubleshoot-load-building-and-shipments"></a><span data-ttu-id="80e7d-103">Risolvere i problemi di allestimento del carico e spedizioni</span><span class="sxs-lookup"><span data-stu-id="80e7d-103">Troubleshoot load building and shipments</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="80e7d-104">Questo argomento descrive come risolvere i problemi comuni che si possono verificare quando si utilizza l'allestimento del carico e le spedizioni in Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="80e7d-104">This topic describes how to fix common issues that you might encounter while you work with load building and shipments in Microsoft Dynamics 365 Supply Chain Management.</span></span>

## <a name="i-receive-the-following-error-message-you-cant-create-a-load-line-for-this-order-line-because-it-contains-inventory-dimensions-that-are-invalid"></a><span data-ttu-id="80e7d-105">Viene visualizzato il seguente messaggio di errore: "Impossibile creare una riga di carico per questa riga ordine perché contiene dimensioni di inventario non valide."</span><span class="sxs-lookup"><span data-stu-id="80e7d-105">I receive the following error message: "You can't create a load line for this order line because it contains inventory dimensions that are invalid..."</span></span>

### <a name="issue-description"></a><span data-ttu-id="80e7d-106">Descrizione del problema</span><span class="sxs-lookup"><span data-stu-id="80e7d-106">Issue description</span></span>

<span data-ttu-id="80e7d-107">Quando si tenta di rilasciare un ordine di reso cliente al magazzino, viene visualizzato il seguente messaggio di errore:</span><span class="sxs-lookup"><span data-stu-id="80e7d-107">You receive the following error message when you try to release a return sales order to the warehouse:</span></span>

> <span data-ttu-id="80e7d-108">Impossibile creare una riga di carico per questa riga ordine perché contiene dimensioni di inventario non valide.</span><span class="sxs-lookup"><span data-stu-id="80e7d-108">You can't create a load line for this order line because it contains inventory dimensions that are invalid.</span></span> <span data-ttu-id="80e7d-109">Non è possibile fare riferimento a dimensioni di inventario che si trovano sotto la dimensione di ubicazione nella gerarchia di prenotazione.</span><span class="sxs-lookup"><span data-stu-id="80e7d-109">You can't reference inventory dimensions that are located below the location dimension in the reservation hierarchy.</span></span> <span data-ttu-id="80e7d-110">Rimuovere le dimensioni non valide dalla riga ordine.</span><span class="sxs-lookup"><span data-stu-id="80e7d-110">Remove the invalid dimensions from the order line.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="80e7d-111">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="80e7d-111">Issue resolution</span></span>

<span data-ttu-id="80e7d-112">Il prodotto non supporta l'elaborazione del carico per un processo di reso cliente.</span><span class="sxs-lookup"><span data-stu-id="80e7d-112">Unfortunately, the product doesn't support load processing for a sales return process.</span></span> <span data-ttu-id="80e7d-113">Pertanto, non è possibile rilasciare l'ordine di reso cliente al magazzino.</span><span class="sxs-lookup"><span data-stu-id="80e7d-113">Therefore, you can't release the return sales order to the warehouse.</span></span>

<span data-ttu-id="80e7d-114">Nelle transazioni di ordini cliente, non è possibile fare riferimento a dimensioni di inventario che si trovano sotto la dimensione di **ubicazione** nella gerarchia di prenotazione.</span><span class="sxs-lookup"><span data-stu-id="80e7d-114">On sales order transactions, you can't reference inventory dimensions that are located below the **Location** dimension in the reservation hierarchy.</span></span> <span data-ttu-id="80e7d-115">La risoluzione consiste nel rimuovere le dimensioni non valide dalla riga ordine.</span><span class="sxs-lookup"><span data-stu-id="80e7d-115">The resolution is to remove the invalid dimensions from the order line.</span></span>

## <a name="i-receive-the-following-error-message-one-of-the-lines-is-already-on-a-load-unable-to-release-to-warehouse"></a><span data-ttu-id="80e7d-116">Viene visualizzato il seguente messaggio di errore: "Una delle righe è già caricata.</span><span class="sxs-lookup"><span data-stu-id="80e7d-116">I receive the following error message: "One of the lines is already on a load.</span></span> <span data-ttu-id="80e7d-117">Impossibile rilasciare al magazzino."</span><span class="sxs-lookup"><span data-stu-id="80e7d-117">Unable to release to warehouse."</span></span>

### <a name="issue-description"></a><span data-ttu-id="80e7d-118">Descrizione del problema</span><span class="sxs-lookup"><span data-stu-id="80e7d-118">Issue description</span></span>

<span data-ttu-id="80e7d-119">Se si creano manualmente i carichi o se si imposta il processo in modo che i carichi siano già creati prima che avvenga l'immissione della riga dell'ordine cliente, si presume che il rilascio successivo verrà eseguito manualmente e che verranno utilizzati il percorso e la classificazione dal carico.</span><span class="sxs-lookup"><span data-stu-id="80e7d-119">If you manually create loads, or if you set up the process so that loads are already created before sales order line entry occurs, the assumption is that the subsequent release will be done manually, and that the route and rating from the load will be used.</span></span>

<span data-ttu-id="80e7d-120">In un altro possibile scenario, si tenta di eseguire un rilascio automatico al magazzino, ma il processo del ciclo non è riuscito a creare lavoro.</span><span class="sxs-lookup"><span data-stu-id="80e7d-120">In another possible scenario, you're trying to do an automatic release to the warehouse, but the wave process failed to create work.</span></span> <span data-ttu-id="80e7d-121">Pertanto, viene comunque creata una spedizione o un carico aperto.</span><span class="sxs-lookup"><span data-stu-id="80e7d-121">Therefore, an open shipment or load is still created.</span></span> <span data-ttu-id="80e7d-122">Questa spedizione o carico aperto blocca quindi i tentativi successivi di rilasciare automaticamente l'ordine fino a quando non si elimina la spedizione o il carico aperto oppure si rielabora manualmente il ciclo.</span><span class="sxs-lookup"><span data-stu-id="80e7d-122">This open shipment or load then blocks subsequent attempts to automatically release the order until you either delete the open shipment or load, or manually reprocess the wave.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="80e7d-123">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="80e7d-123">Issue resolution</span></span>

<span data-ttu-id="80e7d-124">È possibile rilasciare dalla pagina dell'ordine cliente oppure è possibile eseguire il rilascio automatico dalla pagina di rilascio dell'ordine cliente, solo se non esiste alcun carico prima del rilascio al magazzino.</span><span class="sxs-lookup"><span data-stu-id="80e7d-124">You can release from the sales order page, or automatic release can be done from the release sales order page, only if no load exists before the release to the warehouse.</span></span> <span data-ttu-id="80e7d-125">Il carico verrà creato automaticamente dopo l'elaborazione del ciclo.</span><span class="sxs-lookup"><span data-stu-id="80e7d-125">The load will automatically be created after the wave is processed.</span></span>

## <a name="i-receive-the-following-error-message-the-delivery-note-correction-cant-be-processed-the-delivery-note-only-contains-items-that-are-subject-to-warehouse-management-processes-as-these-are-not-supported-by-delivery-note-correction"></a><span data-ttu-id="80e7d-126">Viene visualizzato il seguente messaggio di errore: "Impossibile elaborare la correzione della bolla di consegna.</span><span class="sxs-lookup"><span data-stu-id="80e7d-126">I receive the following error message: "The delivery note correction can't be processed.</span></span> <span data-ttu-id="80e7d-127">La bolla di consegna contiene solo articoli soggetti a processi di gestione del magazzino, in quanto non sono supportati dalla correzione della bolla di consegna."</span><span class="sxs-lookup"><span data-stu-id="80e7d-127">The delivery note only contains items that are subject to warehouse management processes, as these are not supported by Delivery Note correction."</span></span>

### <a name="issue-description"></a><span data-ttu-id="80e7d-128">Descrizione del problema</span><span class="sxs-lookup"><span data-stu-id="80e7d-128">Issue description</span></span>

<span data-ttu-id="80e7d-129">Dopo aver registrato una bolla di consegna, non è possibile annullarla, perché il pulsante **Annulla** non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="80e7d-129">After you post a delivery note, you can't cancel it, because the **Cancel** button is unavailable.</span></span> <span data-ttu-id="80e7d-130">Inoltre, non è possibile correggere la bolla di consegna.</span><span class="sxs-lookup"><span data-stu-id="80e7d-130">You also can't correct the delivery note.</span></span> <span data-ttu-id="80e7d-131">Se si tenta viene visualizzato questo messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="80e7d-131">If you try, you receive this error message.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="80e7d-132">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="80e7d-132">Issue resolution</span></span>

<span data-ttu-id="80e7d-133">Per correggere i documenti di trasporto registrati per gli articoli abilitati per la gestione avanzata del magazzino (WMS), è necessario che la avvenga dal carico, non dall'ordine.</span><span class="sxs-lookup"><span data-stu-id="80e7d-133">To correct posted packing slips for items that are enabled for advanced warehouse management (WMS), you must do the posting from the load, not directly from the order.</span></span>

## <a name="how-can-i-create-work-from-outbound-loads-instead-of-waves"></a><span data-ttu-id="80e7d-134">Come si può creare lavoro da carichi in uscita invece che da cicli?</span><span class="sxs-lookup"><span data-stu-id="80e7d-134">How can I create work from outbound loads instead of waves?</span></span>

### <a name="issue-description"></a><span data-ttu-id="80e7d-135">Descrizione del problema</span><span class="sxs-lookup"><span data-stu-id="80e7d-135">Issue description</span></span>

<span data-ttu-id="80e7d-136">Ecco un modo per riprodurre questo problema.</span><span class="sxs-lookup"><span data-stu-id="80e7d-136">Here is one way to reproduce this issue.</span></span>

1. <span data-ttu-id="80e7d-137">Creare un carico in uscita utilizzando una riga ciclo o un ordine di trasferimento.</span><span class="sxs-lookup"><span data-stu-id="80e7d-137">Create an outbound load by using a sales order or transfer order.</span></span>
2. <span data-ttu-id="80e7d-138">Rilascia il carico al magazzino.</span><span class="sxs-lookup"><span data-stu-id="80e7d-138">Release the load to the warehouse.</span></span>
3. <span data-ttu-id="80e7d-139">Notare che non è stato ancora generato alcun lavoro di prelievo.</span><span class="sxs-lookup"><span data-stu-id="80e7d-139">Notice that no picking work has yet been generated.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="80e7d-140">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="80e7d-140">Issue resolution</span></span>

<span data-ttu-id="80e7d-141">Se il lavoro deve essere generato immediatamente quando il carico viene rilasciato, è necessario configurare il modello di ciclo di conseguenza.</span><span class="sxs-lookup"><span data-stu-id="80e7d-141">If work must be generated immediately when the load is released, you must configure the wave template accordingly.</span></span> <span data-ttu-id="80e7d-142">Sul modello di ciclo, impostare le seguenti opzioni su *Sì*:</span><span class="sxs-lookup"><span data-stu-id="80e7d-142">On the wave template, set the following options to *Yes*:</span></span>

- <span data-ttu-id="80e7d-143">Automatizza creazione ondata</span><span class="sxs-lookup"><span data-stu-id="80e7d-143">Automate wave creation</span></span>
- <span data-ttu-id="80e7d-144">Elabora ondata al rilascio in magazzino</span><span class="sxs-lookup"><span data-stu-id="80e7d-144">Process wave at release to warehouse</span></span>
- <span data-ttu-id="80e7d-145">Automatizza rilascio ondata</span><span class="sxs-lookup"><span data-stu-id="80e7d-145">Automate wave release</span></span>

## <a name="i-cant-re-release-a-partially-shipped-load"></a><span data-ttu-id="80e7d-146">Impossibile rilasciare nuovamente un carico spedito parzialmente.</span><span class="sxs-lookup"><span data-stu-id="80e7d-146">I can't re-release a partially shipped load.</span></span>

### <a name="issue-description"></a><span data-ttu-id="80e7d-147">Descrizione del problema</span><span class="sxs-lookup"><span data-stu-id="80e7d-147">Issue description</span></span>

<span data-ttu-id="80e7d-148">Non è possibile rilasciare un carico spedito parzialmente al magazzino.</span><span class="sxs-lookup"><span data-stu-id="80e7d-148">You can't release a partially shipped load to the warehouse.</span></span> <span data-ttu-id="80e7d-149">Quando si effettua il rilascio al magazzino, viene visualizzato il messaggio "Operazione completata", ma non accade nulla e non viene creato alcun lavoro per la quantità rimanente.</span><span class="sxs-lookup"><span data-stu-id="80e7d-149">When you do the release to the warehouse, an "Operation complete" message appears, but nothing happens, and no work is created for the remaining quantity.</span></span> <span data-ttu-id="80e7d-150">Questo problema si verifica quando si utilizza la funzionalità di carico di trasporto e c'è una prenotazione incompleta.</span><span class="sxs-lookup"><span data-stu-id="80e7d-150">This issue occurs when you use transport load functionality and there is an incomplete reservation.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="80e7d-151">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="80e7d-151">Issue resolution</span></span>

<span data-ttu-id="80e7d-152">[Il problema KB 470069](https://fix.lcs.dynamics.com/Issue/Details?kb=4574490&bugId=470069&dbType=3&qc=84ce1e09d7032d8b8ef86f5a0c68b86badf3dfaf29686c5ebbe97c53c0957b5f) ("I carichi parzialmente spediti possono essere nuovamente elaborati e inclusi nel ciclo") è stato corretto nel [rilascio 10.0.15](../get-started/whats-new-scm-10-0-15.md).</span><span class="sxs-lookup"><span data-stu-id="80e7d-152">[KB issue 470069](https://fix.lcs.dynamics.com/Issue/Details?kb=4574490&bugId=470069&dbType=3&qc=84ce1e09d7032d8b8ef86f5a0c68b86badf3dfaf29686c5ebbe97c53c0957b5f) ("Partially shipped loads can be re-waved and re-processed") is fixed in [release 10.0.15](../get-started/whats-new-scm-10-0-15.md).</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]