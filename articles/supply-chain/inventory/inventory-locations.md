---
title: Ubicazioni di magazzino
description: Le ubicazioni di magazzino vengono utilizzate con l'immagazzinaggio base (WMS I) per determinare dove vengono immagazzinati e dove vengono prelevati gli articoli in un magazzino WMS.
author: perlynne
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WMSLocation
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 2134
ms.assetid: 69bf6922-4151-447f-b678-4ba95637f54c
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 789272e1ee02c7f5dbab4e325cefe56425a3d1a7
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "1549957"
---
# <a name="inventory-locations"></a><span data-ttu-id="b9919-103">Ubicazioni di magazzino</span><span class="sxs-lookup"><span data-stu-id="b9919-103">Inventory locations</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b9919-104">Le ubicazioni di magazzino vengono utilizzate con l'immagazzinaggio base (WMS I) per determinare dove vengono immagazzinati e dove vengono prelevati gli articoli in un magazzino WMS.</span><span class="sxs-lookup"><span data-stu-id="b9919-104">Inventory locations are used with basic warehousing (WMS I) to determine where items are stored and where items are picked from in a WMS I warehouse.</span></span>

<span data-ttu-id="b9919-105">Questo argomento si applica alle funzionalità nel modulo Gestione inventario.</span><span class="sxs-lookup"><span data-stu-id="b9919-105">This topic applies to features in the Inventory management module.</span></span> <span data-ttu-id="b9919-106">Non si applica alle funzioni nel modulo Gestione magazzino.</span><span class="sxs-lookup"><span data-stu-id="b9919-106">It does not apply to features in the Warehouse management module.</span></span>

<span data-ttu-id="b9919-107">Il termine ubicazione identifica la posizione da cui vengono stoccati e prelevati gli articoli.</span><span class="sxs-lookup"><span data-stu-id="b9919-107">The term location refers to the place that items are stored and drawn from.</span></span>

<span data-ttu-id="b9919-108">Per ciascuna ubicazione è inoltre possibile specificare la posizione in cui vengono inseriti gli articoli.</span><span class="sxs-lookup"><span data-stu-id="b9919-108">For each location, the place where the item is inserted can also be specified.</span></span> <span data-ttu-id="b9919-109">Per impostazione predefinita, questi due valori sono corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="b9919-109">By default, they are the same.</span></span> <span data-ttu-id="b9919-110">Gli articoli in genere vengono inseriti e prelevati dallo stesso lato di un'ubicazione. Esistono tuttavia alcune eccezioni.</span><span class="sxs-lookup"><span data-stu-id="b9919-110">Items are usually inserted and drawn from the same side of a location, but not always.</span></span> <span data-ttu-id="b9919-111">Gli articoli immagazzinati in scaffali live storage ad esempio vengono inseriti da una sezione e prelevati da un'altra.</span><span class="sxs-lookup"><span data-stu-id="b9919-111">For example, items that are stored in live storage racks are inserted from one aisle and drawn from another.</span></span> <span data-ttu-id="b9919-112">L'input principale è costituito dal nome dell'ubicazione, in genere determinato in base alle coordinate magazzino, sezione, scaffale, ripiano e contenitore.</span><span class="sxs-lookup"><span data-stu-id="b9919-112">The main input is given by a location name, which is usually determined by its coordinates: warehouse, aisle, rack, shelf, and bin.</span></span> <span data-ttu-id="b9919-113">Il nome o ID può essere immesso manualmente o generato dalle coordinate dell'ubicazione, ad esempio 01-02-03-4 per sezione 1, scaffale 2, ripiano 3, contenitore 4 nella pagina Ubicazioni di magazzino.</span><span class="sxs-lookup"><span data-stu-id="b9919-113">This name or ID can be entered manually or generated from the location coordinates—for example, 01-02-03-4 for aisle 1, rack 2, shelf 3, bin 4 in the Inventory locations page.</span></span>
<span data-ttu-id="b9919-114">Proprietà dell'ubicazione</span><span class="sxs-lookup"><span data-stu-id="b9919-114">Location properties</span></span>

<span data-ttu-id="b9919-115">A un'ubicazione sono associate le seguenti caratteristiche:</span><span class="sxs-lookup"><span data-stu-id="b9919-115">A location has the following characteristics:</span></span>
-   <span data-ttu-id="b9919-116">Dimensione (altezza, larghezza, profondità e quindi volume)</span><span class="sxs-lookup"><span data-stu-id="b9919-116">Size (height, width, depth, and thereby volume)</span></span>
-   <span data-ttu-id="b9919-117">Magazzino, Sezione, Scaffale, Ripiano e Ubicazione contenitore</span><span class="sxs-lookup"><span data-stu-id="b9919-117">Warehouse, aisle, rack, shelf, and bin position</span></span>
-   <span data-ttu-id="b9919-118">Tipo di ubicazione (ubicazione di stoccaggio, prelevante ubicazione, banchina di entrata, banchina di uscita, ubicazioni di entrata produzione, ubicazioni di controllo, o area di deposito kanban)</span><span class="sxs-lookup"><span data-stu-id="b9919-118">Location type (bulk location, picking location, inbound dock, outbound dock, production input location, inspection location, or kanban supermarket)</span></span>

<span data-ttu-id="b9919-119">Nei sistemi in linea è possibile utilizzare un testo di verifica per controllare che l'operatore abbia selezionato l'ubicazione corretta per un articolo specifico.</span><span class="sxs-lookup"><span data-stu-id="b9919-119">Check text can be used in online systems to verify that the operator has selected the correct location for a specific item.</span></span> <span data-ttu-id="b9919-120">Questo testo di verifica può essere creato manualmente o per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="b9919-120">This check text can be created manually or by default.</span></span>

## <a name="sort-codes"></a><span data-ttu-id="b9919-121">Codici di ordinamento</span><span class="sxs-lookup"><span data-stu-id="b9919-121">Sort codes</span></span>
<span data-ttu-id="b9919-122">I codici di ordinamento consentono di ottimizzare la gestione delle righe di prelievo, in cui vengono fornite le informazioni richieste per il prelievo di articoli da magazzino, incluso l'ordine di prelievo.</span><span class="sxs-lookup"><span data-stu-id="b9919-122">Use sort codes to optimize the handling of picking lines, which describe the information that is required for picking items from inventory, including the picking order.</span></span> <span data-ttu-id="b9919-123">I codici di ordinamento possono essere specificati in base alla sezione e ad altre coordinate oppure possono essere assegnati manualmente per l'ubicazione.</span><span class="sxs-lookup"><span data-stu-id="b9919-123">Sort codes can be specified by the aisle and other coordinates, or assigned manually for the location.</span></span>

## <a name="blocked-locations"></a><span data-ttu-id="b9919-124">Ubicazioni bloccate</span><span class="sxs-lookup"><span data-stu-id="b9919-124">Blocked locations</span></span>
<span data-ttu-id="b9919-125">Talvolta è necessario bloccare un'ubicazione per un determinato periodo di tempo, ad esempio per consentire l'esecuzione di riparazioni.</span><span class="sxs-lookup"><span data-stu-id="b9919-125">Occasionally, you might want to indicate that a location is blocked for a period of time, for example, to allow for repairs.</span></span> <span data-ttu-id="b9919-126">Altre volte è possibile che l'utente desideri bloccare solo l'entrata o l'uscita</span><span class="sxs-lookup"><span data-stu-id="b9919-126">At other times, you may want to indicate blocking of only the input or only output.</span></span>

## <a name="tree-structure"></a><span data-ttu-id="b9919-127">Struttura ad albero</span><span class="sxs-lookup"><span data-stu-id="b9919-127">Tree structure</span></span>

<span data-ttu-id="b9919-128">Nella pagina delle ubicazioni di magazzino è possibile visualizzare il layout di magazzino in una struttura ad albero in base alle coordinate delle ubicazioni di magazzino, in un formato di visualizzazione definito.</span><span class="sxs-lookup"><span data-stu-id="b9919-128">In the Inventory locations page, you can view the warehouse layout in a tree structure based on the coordinates of inventory locations, in a defined display format.</span></span>

## <a name="maintain-inventory-locations-via-the-warehouse-form"></a><span data-ttu-id="b9919-129">Gestire le ubicazioni di magazzino tramite modulo di magazzino</span><span class="sxs-lookup"><span data-stu-id="b9919-129">Maintain inventory locations via the warehouse form</span></span>

<span data-ttu-id="b9919-130">È possibile copiare le ubicazioni da un magazzino a un altro e creare le ubicazioni tramite la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="b9919-130">It is possible to copy locations from one warehouse to another and to create locations via a wizard.</span></span> <span data-ttu-id="b9919-131">Prima di eseguire la procedura guidata è necessario verificare di aver definito i nomi di posizione predefinita nella pagina di magazzino.</span><span class="sxs-lookup"><span data-stu-id="b9919-131">Before you run the wizard you should make sure that you have defined the default location names on the Warehouse page.</span></span>



<a name="additional-resources"></a><span data-ttu-id="b9919-132">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="b9919-132">Additional resources</span></span>
--------

[<span data-ttu-id="b9919-133">Creare un nuovo layout di magazzino (guida attività)</span><span class="sxs-lookup"><span data-stu-id="b9919-133">Create a new warehouse layout (Task guide)</span></span>](tasks/create-new-warehouse-layout.md)
