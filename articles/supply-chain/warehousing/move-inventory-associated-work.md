---
title: Movimento di magazzino e lavoro associato in Gestione magazzino
description: In questo argomento viene descritto come impostare e applicare la conferma di prelievo dei pezzi da un dispositivo mobile.
author: Mirzaab
manager: AnnBe
ms.date: 05/26/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, Operations
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 7b330d6aa8e972d3c35bb7783ec0a39f09775011
ms.contentlocale: it-it
ms.lasthandoff: 11/03/2017

---

# <a name="movement-of-inventory-with-associated-work-in-warehouse-management"></a><span data-ttu-id="ff9c3-103">Movimento di magazzino e lavoro associato in Gestione magazzino</span><span class="sxs-lookup"><span data-stu-id="ff9c3-103">Movement of inventory with associated work in Warehouse management</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="ff9c3-104">Utilizzo il movimento dell'inventario, è possibile decidere quali lavoratori del magazzino sono autorizzati a spostare le scorte prenotate.</span><span class="sxs-lookup"><span data-stu-id="ff9c3-104">Using movement of inventory, you can decide which warehouse workers are allowed to move reserved inventory.</span></span> <span data-ttu-id="ff9c3-105">In questo modo si ottiene una flessibilità nei magazzini regolamentati in cui è possibile scegliere di non consentire a un lavoratore di selezionare una nuova ubicazione di prelievo per il lavoro del prelievo che è già creato.</span><span class="sxs-lookup"><span data-stu-id="ff9c3-105">This provides a flexibility in regulated warehouses where you can decide to not allow a worker to choose a new pick location for pick work that is already created.</span></span> <span data-ttu-id="ff9c3-106">Consente inoltre a un responsabile del magazzino di verificare quali competenze dovrebbero avere alcuni lavoratori con meno esperienza.</span><span class="sxs-lookup"><span data-stu-id="ff9c3-106">It also allows a warehouse manager to control which capabilities some less experienced workers should have.</span></span>

<span data-ttu-id="ff9c3-107">La flessibilità di gestire le operazioni giornaliere dei lavoratori di magazzino può essere utile in scenari come i seguenti:</span><span class="sxs-lookup"><span data-stu-id="ff9c3-107">The flexibility to manage the daily operations of warehouse workers can be useful in scenarios such as these:</span></span>

## <a name="scenario-1"></a><span data-ttu-id="ff9c3-108">Scenario 1</span><span class="sxs-lookup"><span data-stu-id="ff9c3-108">Scenario 1</span></span>
<span data-ttu-id="ff9c3-109">Una società ha un'area di ricevimenti relativamente piccola, congestionata con pallet e scatole in attesa di stoccaggio.</span><span class="sxs-lookup"><span data-stu-id="ff9c3-109">A company has a relatively small receiving area, and it’s congested with pallets and boxes awaiting put away.</span></span> <span data-ttu-id="ff9c3-110">Una spedizione consistente è programmata per il giorno corrente, pertanto l'addetto al ricevimento decide di sistemare l'area di ricevimento spostando alcuni dei pallet in un'area di gestione temporanea.</span><span class="sxs-lookup"><span data-stu-id="ff9c3-110">A large shipment is expected on the current day, so the receiving clerk decides to clear up the receiving area by moving some of the pallets to a secondary inbound staging area.</span></span>

## <a name="scenario-2"></a><span data-ttu-id="ff9c3-111">Scenario 2</span><span class="sxs-lookup"><span data-stu-id="ff9c3-111">Scenario 2</span></span>
<span data-ttu-id="ff9c3-112">Un lavoratore di magazzino esperto nota che in un magazzino vi è l'opportunità di consolidare gli articoli in un'ubicazione invece di doverli ripartire in 3 ubicazioni vicine con poca quantità ciascuno.</span><span class="sxs-lookup"><span data-stu-id="ff9c3-112">An experienced warehouse worker notices an opportunity in a warehouse to consolidate items in one location instead of having them divided across 3 nearby locations with little quantity on each.</span></span> <span data-ttu-id="ff9c3-113">Il lavoratore desidera consolidare la quantità spostando gli articoli da ciascuna di queste ubicazioni nella stessa ubicazione con la stessa targa.</span><span class="sxs-lookup"><span data-stu-id="ff9c3-113">The worker wants to consolidate the quantity by moving items from each of these locations into the same location and onto the same license plate.</span></span>

## <a name="scenario-3"></a><span data-ttu-id="ff9c3-114">Scenario 3</span><span class="sxs-lookup"><span data-stu-id="ff9c3-114">Scenario 3</span></span>
<span data-ttu-id="ff9c3-115">Un pallet è in attesa della spedizione in'ubicazione di gestione temporanea, ad esempio STAGE01, vicina a BAYDOOR01.</span><span class="sxs-lookup"><span data-stu-id="ff9c3-115">A pallet is awaiting shipment in a staging location, such as STAGE01, which is near BAYDOOR01.</span></span> <span data-ttu-id="ff9c3-116">Tuttavia, a causa di una modifica dei piani il camion dovrebbe arrivare presso l'ubicazione BAYDOOR04.</span><span class="sxs-lookup"><span data-stu-id="ff9c3-116">However, due to a change of plans the truck is scheduled to arrive at BAYDOOR04.</span></span> <span data-ttu-id="ff9c3-117">L'addetto alle spedizioni è consapevole di questo e deve fare in modo che il camion non debba attendere per essere caricato da STAGE01.</span><span class="sxs-lookup"><span data-stu-id="ff9c3-117">The shipping clerk is aware of this and needs to ensure that the truck does not have to wait to be loaded from STAGE01.</span></span> <span data-ttu-id="ff9c3-118">L'addetto alle spedizioni decide di spostare gli articoli della spedizione da STAGE01 a STAGE04, ovvero più vicina alla nuova destinazione.</span><span class="sxs-lookup"><span data-stu-id="ff9c3-118">The shipping clerk decides to move the items in that shipment from STAGE01 to STAGE04, which is closer to the new destination.</span></span>

### <a name="current-limitations"></a><span data-ttu-id="ff9c3-119">Limitazioni correnti</span><span class="sxs-lookup"><span data-stu-id="ff9c3-119">Current limitations</span></span>

<span data-ttu-id="ff9c3-120">Le prenotazioni di lavoro che è possibile spostare sono limitate alle attività relative a Ordine cliente, Invio ordine di trasferimento, Ricezione ordine di trasferimento, Ordine fornitore e Rifornimento.</span><span class="sxs-lookup"><span data-stu-id="ff9c3-120">The work reservations that you can move are limited to Sales order, Transfer order issue, Transfer order receipt, Purchase order, and Replenishment work.</span></span>

<span data-ttu-id="ff9c3-121">Lo spostamento di articoli è limitato per impedire la divisione delle righe di lavoro.</span><span class="sxs-lookup"><span data-stu-id="ff9c3-121">Moving items is restricted to prevent splitting of work lines.</span></span> <span data-ttu-id="ff9c3-122">Ciò significa che se si dispone di una riga di lavoro per 100 pezzi dell'articoloo A dall'ubicazione Loc1, non sarà possibile spostare solo 30 pezzi dell'articoloo A da quella a un'altra ubicazione.</span><span class="sxs-lookup"><span data-stu-id="ff9c3-122">This means that if you have a work line for 100 pcs of item A from location Loc1, you won’t be able to move only 30 pcs of item A from there to another location.</span></span> <span data-ttu-id="ff9c3-123">Questo comporterebbe una divisione della riga esistente di lavoro a 30 e 70, poiché le ubicazioni sono ora differenti.</span><span class="sxs-lookup"><span data-stu-id="ff9c3-123">This would lead to a split of the existing work line to 30 and 70, because the locations are now different.</span></span>

<span data-ttu-id="ff9c3-124">Per gli scenari di gestione temporanea, in cui la targa da cui si spostano le merci o la targa in cui vengono spostate vengono impostate come Targa destinazione per un ordine di lavoro, solo lo spostamento dell'intera targa è consentito, in modo da non dover smembrare la targa di destinazione.</span><span class="sxs-lookup"><span data-stu-id="ff9c3-124">For staging scenarios, where the license plate you move the goods from or the license plate you move the goods to, are set as a Target LP for a work order, only movement of the entire LP is allowed, so as not to break up the Target LP.</span></span>
<span data-ttu-id="ff9c3-125">Attualmente è supportato solo lo spostamento ad hoc.</span><span class="sxs-lookup"><span data-stu-id="ff9c3-125">Only the ad hoc movement is currently supported.</span></span> <span data-ttu-id="ff9c3-126">Questo significa che non sarà possibile spostare le scorte prenotate mediante lo spostamento per voci di menu del dispositivo mobile del modello.</span><span class="sxs-lookup"><span data-stu-id="ff9c3-126">That means that you will not be able to move reserved inventory through the movement by template mobile device menu items.</span></span>

### <a name="set-up-permission-to-move-reserved-inventory-for-individual-workers"></a><span data-ttu-id="ff9c3-127">Configurare l'autorizzazione per spostare le scorte prenotate per singoli lavoratori</span><span class="sxs-lookup"><span data-stu-id="ff9c3-127">Set up permission to move reserved inventory for individual workers</span></span>

<span data-ttu-id="ff9c3-128">Per il lavoratore a cui dovrà essere consentito di spostare le scorte prenotate, selezionare la casella di controllo **Consenti movimento di magazzino e lavoro associato** in **Gestione magazzino** > **Impostazioni** > **Lavoratore**.</span><span class="sxs-lookup"><span data-stu-id="ff9c3-128">For the worker who should be allowed to move reserved inventory, select the **Allow movement of inventory with work associated** check box under **Warehouse management** > **Setup** > **Worker**.</span></span>  

### <a name="backported"></a><span data-ttu-id="ff9c3-129">Backporting</span><span class="sxs-lookup"><span data-stu-id="ff9c3-129">Backported</span></span>

<span data-ttu-id="ff9c3-130">Per questa funzionalità è stato effettuato il backporting a Microsoft Dynamics AX 2012 R3 e sarà disponibile come parte di CU12.</span><span class="sxs-lookup"><span data-stu-id="ff9c3-130">This feature has also been back-ported to Microsoft Dynamics AX 2012 R3 and will be available as part of CU12.</span></span>
<span data-ttu-id="ff9c3-131">Può inoltre essere scaricata singolarmente con il numero di KB 3192548.</span><span class="sxs-lookup"><span data-stu-id="ff9c3-131">It can also be downloaded individually through KB number 3192548.</span></span> 


