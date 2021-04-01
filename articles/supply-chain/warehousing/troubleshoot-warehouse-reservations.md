---
title: Risolvere i problemi delle prenotazioni in Gestione magazzino
description: Questo argomento descrive come risolvere i problemi comuni che si possono verificare quando si utilizzano le prenotazioni dei magazzini in Microsoft Dynamics 365 Supply Chain Management.
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
ms.openlocfilehash: a9a5d20732a802fc58c392853af8334bbc07de73
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5248717"
---
# <a name="troubleshoot-reservations-in-warehouse-management"></a><span data-ttu-id="ab9cd-103">Risolvere i problemi delle prenotazioni in Gestione magazzino</span><span class="sxs-lookup"><span data-stu-id="ab9cd-103">Troubleshoot reservations in warehouse management</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ab9cd-104">Questo argomento descrive come risolvere i problemi comuni che si possono verificare quando si utilizzano le prenotazioni dei magazzini in Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="ab9cd-104">This topic describes how to fix common issues that you might encounter while you work with warehouse reservations in Microsoft Dynamics 365 Supply Chain Management.</span></span>

## <a name="i-receive-the-following-error-message-reservations-cannot-be-removed-because-there-is-work-created-which-relies-on-the-reservations"></a><span data-ttu-id="ab9cd-105">Viene visualizzato il seguente messaggio di errore "Impossibile rimuovere le prenotazioni perché è presente lavoro creato che si basa sulle prenotazioni".</span><span class="sxs-lookup"><span data-stu-id="ab9cd-105">I receive the following error message: "Reservations cannot be removed because there is work created which relies on the reservations."</span></span>

### <a name="issue-description"></a><span data-ttu-id="ab9cd-106">Descrizione del problema</span><span class="sxs-lookup"><span data-stu-id="ab9cd-106">Issue description</span></span>

<span data-ttu-id="ab9cd-107">Non è possibile annullare la prenotazione dell'inventario su una riga di vendita, perché c'è lavoro aperto per la riga.</span><span class="sxs-lookup"><span data-stu-id="ab9cd-107">You can't unreserve inventory on a sales line, because there is open work against the line.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="ab9cd-108">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="ab9cd-108">Issue resolution</span></span>

<span data-ttu-id="ab9cd-109">Verificare se esiste un lavoro di gruppo di imballaggio aperto per portare l'articolo da una stazione di imballaggio a un'altra ubicazione (ad esempio *Portellone*).</span><span class="sxs-lookup"><span data-stu-id="ab9cd-109">Investigate whether open packing group work exists to bring the item from a packing station to another location (such as *Baydoor*).</span></span> <span data-ttu-id="ab9cd-110">Rivedere i record delle pagine **Registro della cronologia di creazione del lavoro** e **Dettagli del lavoro** per determinare cosa sta fisicamente prenotando l'inventario, quindi completare o eliminare il lavoro per liberare la prenotazione.</span><span class="sxs-lookup"><span data-stu-id="ab9cd-110">Review the records on the **Work creation history log** and **Work details** pages to determine what is physically reserving the inventory, and then complete or delete the work to free up the reservation.</span></span>

## <a name="i-receive-the-following-error-message-inventory-quantity--1-could-not-be-updated-due-to-insufficient-inventory-transactions-for-item-2"></a><span data-ttu-id="ab9cd-111">Viene visualizzato il seguente messaggio di errore: "Impossibile aggiornare la quantità inventario -%1 a causa di transazioni di magazzino insufficienti per l'articolo %2."</span><span class="sxs-lookup"><span data-stu-id="ab9cd-111">I receive the following error message: "Inventory quantity -%1 could not be updated due to insufficient inventory transactions for item %2...."</span></span>

### <a name="issue-description"></a><span data-ttu-id="ab9cd-112">Descrizione del problema</span><span class="sxs-lookup"><span data-stu-id="ab9cd-112">Issue description</span></span>

<span data-ttu-id="ab9cd-113">Questo problema può verificarsi se il sistema non è in grado di aggiornare una quantità di inventario perché non ci sono sufficienti transazioni di inventario con le dimensioni specificate.</span><span class="sxs-lookup"><span data-stu-id="ab9cd-113">This issue can occur if the system can't update an inventory quantity because there aren't enough inventory transactions that have the specified dimensions.</span></span> <span data-ttu-id="ab9cd-114">Di seguito è riportato il messaggio di errore completo:</span><span class="sxs-lookup"><span data-stu-id="ab9cd-114">Here is the full text of the full error message:</span></span>

> <span data-ttu-id="ab9cd-115">Impossibile aggiornare la quantità di inventario -%1 perché non ci sono sufficienti transazioni di inventario per l'articolo %2 con le dimensioni specificate=%3, Colore=%4, Aggiunte=%5, Sito=%6, Magazzino=%7, Ubicazione=%8, Stato inventario=Disponibile, Targa=%9, Numero batch=%10 per ID riferimento %11 in ID lotto %12.</span><span class="sxs-lookup"><span data-stu-id="ab9cd-115">Inventory quantity -%1 could not be updated due to insufficient inventory transactions for item %2 with dimensions Size=%3, Color=%4, Additions=%5, Site=%6, Warehouse=%7, Location=%8, Inventory status=Available, License plate=%9, Batch number=%10 for reference ID %11 on Lot ID %12.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="ab9cd-116">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="ab9cd-116">Issue resolution</span></span>

<span data-ttu-id="ab9cd-117">Assicurarsi che nessuna transazione di magazzino stia prenotando fisicamente la quantità.</span><span class="sxs-lookup"><span data-stu-id="ab9cd-117">Make sure that no inventory transactions are physically reserving the quantity.</span></span> <span data-ttu-id="ab9cd-118">Ad esempio, queste transazioni potrebbero aprire ordini di controllo qualità, record di blocco dell'inventario o ordini di uscita.</span><span class="sxs-lookup"><span data-stu-id="ab9cd-118">For example, these transactions might open quality orders, inventory blocking records, or output orders.</span></span>

## <a name="i-receive-the-following-error-message-physical-on-handcannot-be-reserved-because-only-000-are-available-in-the-inventory"></a><span data-ttu-id="ab9cd-119">Viene visualizzato il seguente messaggio di errore: "Impossibile prenotare le scorte fisiche perché nell'inventario sono disponibili solo 0,00".</span><span class="sxs-lookup"><span data-stu-id="ab9cd-119">I receive the following error message: "Physical on-hand...cannot be reserved because only 0.00 are available in the inventory."</span></span>

### <a name="issue-description"></a><span data-ttu-id="ab9cd-120">Descrizione del problema</span><span class="sxs-lookup"><span data-stu-id="ab9cd-120">Issue description</span></span>

<span data-ttu-id="ab9cd-121">Questo problema può verificarsi se il sistema non è in grado di aggiornare una quantità di inventario perché non ci sono sufficienti transazioni di inventario con le dimensioni specificate.</span><span class="sxs-lookup"><span data-stu-id="ab9cd-121">This issue can occur if the system can't update an inventory quantity because there aren't enough inventory transactions that have the specified dimensions.</span></span> <span data-ttu-id="ab9cd-122">Di seguito è riportato il messaggio di errore completo:</span><span class="sxs-lookup"><span data-stu-id="ab9cd-122">Here is the full text of the full error message:</span></span>

> <span data-ttu-id="ab9cd-123">Sito scorte fisiche=%1, Magazzino=%2, Stato inventario=Disponibile, Numero batch=%3, Proprietario=%4: %5 non può essere prenotato perché solo 0,00 sono disponibili nell'inventario.</span><span class="sxs-lookup"><span data-stu-id="ab9cd-123">Physical on-hand Site=%1, Warehouse=%2, Inventory status=Available, Batch number=%3, Owner=%4: %5 cannot be reserved because only 0.00 are available in the inventory.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="ab9cd-124">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="ab9cd-124">Issue resolution</span></span>

<span data-ttu-id="ab9cd-125">Questo problema è probabilmente causato da un lavoro aperto.</span><span class="sxs-lookup"><span data-stu-id="ab9cd-125">This issue is probably caused by open work.</span></span> <span data-ttu-id="ab9cd-126">Completare il lavoro o ricevere senza crearlo.</span><span class="sxs-lookup"><span data-stu-id="ab9cd-126">Either complete the work or receive without work creation.</span></span> <span data-ttu-id="ab9cd-127">Assicurarsi che nessuna transazione di magazzino stia prenotando fisicamente la quantità.</span><span class="sxs-lookup"><span data-stu-id="ab9cd-127">Make sure that no inventory transactions are physically reserving the quantity.</span></span> <span data-ttu-id="ab9cd-128">Ad esempio, queste transazioni potrebbero essere ordini di controllo qualità aperti, record di blocco dell'inventario o ordini di uscita.</span><span class="sxs-lookup"><span data-stu-id="ab9cd-128">For example, these transactions might be open quality orders, inventory blocking records, or output orders.</span></span>

## <a name="i-receive-the-following-error-message-to-be-assigned-to-wave-load-lines-must-specify-the-dimensions-above-the-location-to-assign-these-dimensions-reserve-and-recreate-the-load-line"></a><span data-ttu-id="ab9cd-129">Viene visualizzato il seguente messaggio di errore: "Per essere assegnate al ciclo, le righe di carico devono specificare le dimensioni sopra l'ubicazione.</span><span class="sxs-lookup"><span data-stu-id="ab9cd-129">I receive the following error message: "To be assigned to wave, load lines must specify the dimensions above the location.</span></span> <span data-ttu-id="ab9cd-130">Per assegnare queste dimensioni, prenotare e ricreare la riga di carico. "</span><span class="sxs-lookup"><span data-stu-id="ab9cd-130">To assign these dimensions, reserve and recreate the load line."</span></span>

### <a name="issue-description"></a><span data-ttu-id="ab9cd-131">Descrizione del problema</span><span class="sxs-lookup"><span data-stu-id="ab9cd-131">Issue description</span></span>

<span data-ttu-id="ab9cd-132">Quando si utilizza un articolo che ha una gerarchia di prenotazione "sopra il batch" (con la dimensione **Numero batch** posizionata *sopra* la dimensione **Ubicazione**), il comando **Rilascia in magazzino** nella pagina **Workbench di pianificazione del carico** per una quantità parziale non funziona.</span><span class="sxs-lookup"><span data-stu-id="ab9cd-132">When you use an item that has a "batch above" reservation hierarchy (with the **Batch number** dimension placed *above* the **Location** dimension), the **Release to warehouse** command on the **Load planning workbench** page for a partial quantity doesn't work.</span></span> <span data-ttu-id="ab9cd-133">Viene visualizzato questo messaggio di errore e non viene creato alcun lavoro per la quantità parziale.</span><span class="sxs-lookup"><span data-stu-id="ab9cd-133">You receive this error message, and no work is created for the partial quantity.</span></span>

<span data-ttu-id="ab9cd-134">Tuttavia se si utilizza un articolo che ha una gerarchia di prenotazione "sotto il batch" (con la dimensione **Numero batch** posizionata *sotto* la dimensione **Ubicazione**), è possibile rilasciare il carico dalla pagina **Workbench di pianificazione del carico** per una quantità parziale.</span><span class="sxs-lookup"><span data-stu-id="ab9cd-134">However, if you use an item that has a "batch below" reservation hierarchy (with the **Batch number** dimension placed *below* the **Location** dimension), you can release a load from the **Load planning workbench** page for a partial quantity.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="ab9cd-135">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="ab9cd-135">Issue resolution</span></span>

<span data-ttu-id="ab9cd-136">Questo comportamento è predefinito.</span><span class="sxs-lookup"><span data-stu-id="ab9cd-136">This behavior is by design.</span></span> <span data-ttu-id="ab9cd-137">Se si inserisce una dimensione sopra la dimensione **Ubicazione** nella gerarchia di prenotazione, deve essere specificata prima del rilascio al magazzino.</span><span class="sxs-lookup"><span data-stu-id="ab9cd-137">If you put a dimension above the **Location** dimension in the reservation hierarchy, it must be specified before the release to the warehouse.</span></span> <span data-ttu-id="ab9cd-138">Microsoft ha valutato questo problema e ha stabilito che si tratta di una limitazione della funzionalità durante i rilasci al magazzino dal workbench di pianificazione del carico.</span><span class="sxs-lookup"><span data-stu-id="ab9cd-138">Microsoft has evaluated this issue and has determined that it's a feature limitation during releases to the warehouse from the load planning workbench.</span></span> <span data-ttu-id="ab9cd-139">Le quantità parziali non possono essere rilasciate se una o più dimensioni sopra **Ubicazione** non sono specificate.</span><span class="sxs-lookup"><span data-stu-id="ab9cd-139">Partial quantities can't be released if one or more dimensions above **Location** aren't specified.</span></span>

<span data-ttu-id="ab9cd-140">Per ulteriori informazioni, vedere [Criteri flessibili di prenotazione delle dimensioni a livello di magazzino](flexible-warehouse-level-dimension-reservation.md)</span><span class="sxs-lookup"><span data-stu-id="ab9cd-140">For more information, see [Flexible warehouse-level dimension reservation policy](flexible-warehouse-level-dimension-reservation.md).</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]