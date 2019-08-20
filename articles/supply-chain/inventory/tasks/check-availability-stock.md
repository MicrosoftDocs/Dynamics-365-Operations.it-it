---
title: Controllare la disponibilità scorte
description: Nella procedura viene illustrato come controllare le scorte disponibili e fisiche disponibili per un numero articolo specifico.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventOnHandItemListPage, SysQueryForm, InventDimParmFixed, InventSupply, DefaultDashboard, WHSInventPhysicalOnhand, WHSOnHand
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5b78b2e4ec3179450d635857353846c9bcb23eed
ms.sourcegitcommit: ef08bf1258aefb525d56bf85ef19311be26ab94c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/30/2019
ms.locfileid: "1795174"
---
# <a name="check-the-availability-of-stock"></a><span data-ttu-id="64098-103">Controllare la disponibilità scorte</span><span class="sxs-lookup"><span data-stu-id="64098-103">Check the availability of stock</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="64098-104">Nella procedura viene illustrato come controllare le scorte disponibili e fisiche disponibili per un numero articolo specifico.</span><span class="sxs-lookup"><span data-stu-id="64098-104">This procedure shows you how to check on-hand and physical on-hand inventory for a specific item number.</span></span> <span data-ttu-id="64098-105">Viene inoltre illustrato come ottenere informazioni sulla fornitura correlate a un articolo.</span><span class="sxs-lookup"><span data-stu-id="64098-105">It also shows you how to get supply information related to an item.</span></span> <span data-ttu-id="64098-106">Le scorte fisiche disponibili sono le scorte disponibili, ovvero che sono state acquistate, ricevute e registrate.</span><span class="sxs-lookup"><span data-stu-id="64098-106">Physical on-hand inventory is the on-hand inventory that’s available – that is, it’s purchased, received and registered.</span></span> <span data-ttu-id="64098-107">Le scorte disponibili includono le scorte disponibili, ma anche le scorte ordinate e previste, ma non ancora ricevute o registrate.</span><span class="sxs-lookup"><span data-stu-id="64098-107">On-hand inventory includes the available on-hand inventory, but also the inventory that’s been ordered and is expected, but not yet received or registered.</span></span> <span data-ttu-id="64098-108">È possibile eseguire questa procedura nella società di dati dimostrativi USMF oppure utilizzando i propri dati.</span><span class="sxs-lookup"><span data-stu-id="64098-108">You can walk through this procedure in demo data company USMF, or using your own data.</span></span> <span data-ttu-id="64098-109">Se si utilizza USMF è possibile utilizzare i valori di esempio visualizzati.</span><span class="sxs-lookup"><span data-stu-id="64098-109">If you are using USMF you can use the example values that are shown.</span></span> <span data-ttu-id="64098-110">Queste attività in genere verranno svolte da un addetto al magazzino.</span><span class="sxs-lookup"><span data-stu-id="64098-110">These tasks would typically be carried out by a warehouse worker.</span></span>


## <a name="check-on-hand-inventory-for-an-item"></a><span data-ttu-id="64098-111">Selezionare le scorte disponibili di un articolo</span><span class="sxs-lookup"><span data-stu-id="64098-111">Check on-hand inventory for an item</span></span>
1. <span data-ttu-id="64098-112">Passare a Gestione articoli > Richieste di informazioni e report > Scorte disponibili.</span><span class="sxs-lookup"><span data-stu-id="64098-112">Go to Inventory management > Inquiries and reports > On-hand inventory.</span></span>
2. <span data-ttu-id="64098-113">Selezionare la riga numero articolo.</span><span class="sxs-lookup"><span data-stu-id="64098-113">Select the Item number row.</span></span>
    * <span data-ttu-id="64098-114">Per eseguire query sulle scorte disponibili per numero articolo, selezionare la riga in cui la Tabella è impostata su Scorte disponibili e il campo è impostato su Numero articolo.</span><span class="sxs-lookup"><span data-stu-id="64098-114">To query the on-hand inventory by item number, select the row where the Table is set to On-hand inventory and Field is set to Item number.</span></span>  
3. <span data-ttu-id="64098-115">Nel campo Criteri selezionare l'articolo su cui si desidera eseguire una query.</span><span class="sxs-lookup"><span data-stu-id="64098-115">In the Criteria field, select the item you want to query.</span></span>
    * <span data-ttu-id="64098-116">Se si utilizza la società di dati dimostrativi USMF, è possibile selezionare 'M9201'.</span><span class="sxs-lookup"><span data-stu-id="64098-116">If you're using the USMF demo data company, you can select 'M9201'.</span></span>  
4. <span data-ttu-id="64098-117">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="64098-117">Click OK.</span></span>
5. <span data-ttu-id="64098-118">Fare clic su Dimensioni.</span><span class="sxs-lookup"><span data-stu-id="64098-118">Click Dimensions.</span></span>
    * <span data-ttu-id="64098-119">La scheda Dimensioni consente di selezionare la quantità di dettagli che si desidera visualizzare sulle scorte disponibili.</span><span class="sxs-lookup"><span data-stu-id="64098-119">The Dimensions tab allows you select how much detail you want to see about your on-hand inventory.</span></span> <span data-ttu-id="64098-120">Se sono necessari dei dati relativi alla prenotazione, è necessario visualizzare tutte le dimensioni inventariali per gli articoli che utilizzano i processi avanzati di magazzino (WHS).</span><span class="sxs-lookup"><span data-stu-id="64098-120">If you need data related to reservation, you must display all inventory dimensions for the items that use advanced warehouse (WHS) processes.</span></span>  
6. <span data-ttu-id="64098-121">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="64098-121">Click OK.</span></span>
7. <span data-ttu-id="64098-122">Nel riquadro azioni, fare clic su Informazioni correlate.</span><span class="sxs-lookup"><span data-stu-id="64098-122">On the Action Pane, click Related information.</span></span>
    * <span data-ttu-id="64098-123">Se non si vedono, può essere necessario fare clic sul pulsante con i puntini di sospensione (…) per visualizzare le opzioni aggiuntive del riquadro azioni.</span><span class="sxs-lookup"><span data-stu-id="64098-123">If you don’t see this, you may need to click on the Ellipsis button (…) to see additional action pane options.</span></span>  
8. <span data-ttu-id="64098-124">Fare clic su Panoramica fornitura.</span><span class="sxs-lookup"><span data-stu-id="64098-124">Click Supply overview.</span></span>
    * <span data-ttu-id="64098-125">La scheda Panoramica della fornitura fornisce informazioni sulla fornitura di un articolo specifico, ad esempio la quantità disponibile, il lead time e informazioni sul fornitore.</span><span class="sxs-lookup"><span data-stu-id="64098-125">The Supply overview tab provides supply information for a specific item, such as the quantity on-hand, the lead time, and vendor information.</span></span>  
9. <span data-ttu-id="64098-126">Espandere la sezione Disponibilità.</span><span class="sxs-lookup"><span data-stu-id="64098-126">Expand the On-hand section.</span></span>
10. <span data-ttu-id="64098-127">Espandere la sezione Fornitori.</span><span class="sxs-lookup"><span data-stu-id="64098-127">Expand the Vendors section.</span></span>
11. <span data-ttu-id="64098-128">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="64098-128">Close the page.</span></span>
12. <span data-ttu-id="64098-129">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="64098-129">Close the page.</span></span>

## <a name="check-physical-on-hand-inventory"></a><span data-ttu-id="64098-130">Selezionare le scorte fisiche disponibili</span><span class="sxs-lookup"><span data-stu-id="64098-130">Check physical on-hand inventory</span></span>
1. <span data-ttu-id="64098-131">Andare a Gestione magazzino > Richieste di informazioni e report > Scorte fisiche disponibili.</span><span class="sxs-lookup"><span data-stu-id="64098-131">Go to Warehouse management > Inquiries and reports > Physical on-hand inventory.</span></span>
2. <span data-ttu-id="64098-132">Nel campo Numero articolo, digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="64098-132">In the Item number field, type a value.</span></span>
    * <span data-ttu-id="64098-133">È possibile utilizzare i campi Sito e Magazzino per filtrare l'elenco di articoli.</span><span class="sxs-lookup"><span data-stu-id="64098-133">You can use the Site and Warehouse fields to filter the list of items.</span></span>  
3. <span data-ttu-id="64098-134">Aggiorna la pagina.</span><span class="sxs-lookup"><span data-stu-id="64098-134">Refresh the page.</span></span>
4. <span data-ttu-id="64098-135">Fare clic su Visualizza dimensioni.</span><span class="sxs-lookup"><span data-stu-id="64098-135">Click Display Dimensions.</span></span>
    * <span data-ttu-id="64098-136">La scheda Visualizzazione consente di selezionare la quantità di dettagli che si desidera visualizzare sulle scorte disponibili.</span><span class="sxs-lookup"><span data-stu-id="64098-136">The Dimensions Display tab allows you select how much detail you want to see about your on-hand inventory.</span></span>  
5. <span data-ttu-id="64098-137">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="64098-137">Click OK.</span></span>
6. <span data-ttu-id="64098-138">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="64098-138">Close the page.</span></span>

## <a name="check-on-hand-inventory-by-location"></a><span data-ttu-id="64098-139">Selezionare le scorte disponibili in base all'ubicazione</span><span class="sxs-lookup"><span data-stu-id="64098-139">Check on-hand inventory by location</span></span>
1. <span data-ttu-id="64098-140">Andare a Gestione magazzino > Richieste di informazioni e report > Disponibili per ubicazione.</span><span class="sxs-lookup"><span data-stu-id="64098-140">Go to Warehouse management > Inquiries and reports > On hand by location.</span></span>
2. <span data-ttu-id="64098-141">Digitare un valore nel campo Magazzino.</span><span class="sxs-lookup"><span data-stu-id="64098-141">In the Warehouse field, type a value.</span></span>
    * <span data-ttu-id="64098-142">Se si utilizza la società di dati dimostrativi USMF, è possibile utilizzare "51".</span><span class="sxs-lookup"><span data-stu-id="64098-142">If you're using the USMF demo data company, you can use '51'.</span></span>  
3. <span data-ttu-id="64098-143">Aggiorna la pagina.</span><span class="sxs-lookup"><span data-stu-id="64098-143">Refresh the page.</span></span>
4. <span data-ttu-id="64098-144">Fare clic su Visualizza dimensioni.</span><span class="sxs-lookup"><span data-stu-id="64098-144">Click Display Dimensions.</span></span>
5. <span data-ttu-id="64098-145">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="64098-145">Click OK.</span></span>
6. <span data-ttu-id="64098-146">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="64098-146">Close the page.</span></span>

