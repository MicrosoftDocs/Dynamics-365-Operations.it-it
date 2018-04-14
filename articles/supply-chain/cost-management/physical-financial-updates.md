---
title: Aggiornamenti fisici e finanziari
description: "In questo argomento viene fornita una panoramica dei tipi di transazioni che aumentano e riducono le quantità delle scorte."
author: AndersGirke
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventTrans, InventTransVoucher
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 75023
ms.assetid: 128340e1-c573-48e6-b835-6c350d8dd0fb
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 08a04b3c80aaac25177f92b250e8dc287ae76c28
ms.contentlocale: it-it
ms.lasthandoff: 04/13/2018

---

# <a name="physical-and-financial-updates"></a><span data-ttu-id="5d0d3-103">Aggiornamenti fisici e finanziari</span><span class="sxs-lookup"><span data-stu-id="5d0d3-103">Physical and financial updates</span></span>

[!INCLUDE [banner](../includes/banner.md)]

<span data-ttu-id="5d0d3-104">In questo argomento viene fornita una panoramica dei tipi di transazioni che aumentano e riducono le quantità delle scorte.</span><span class="sxs-lookup"><span data-stu-id="5d0d3-104">This topic provides an overview of which types of transactions increase or decrease inventory quantities.</span></span> 

<span data-ttu-id="5d0d3-105">In Microsoft Dynamics 365 for Finance and Operations le transazioni di magazzino possono essere aggiornate fisicamente e finanziariamente.</span><span class="sxs-lookup"><span data-stu-id="5d0d3-105">Inventory transactions can be physically updated and financially updated in Microsoft Dynamics 365 for Finance and Operations.</span></span> <span data-ttu-id="5d0d3-106">Alcuni tipi di transazioni di magazzino e di transazioni finanziarie determinano un incremento delle quantità di scorte, altre una riduzione.</span><span class="sxs-lookup"><span data-stu-id="5d0d3-106">Some types of physical and financial transactions increase inventory quantities, whereas others decrease the quantity.</span></span>

## <a name="physical-increases"></a><span data-ttu-id="5d0d3-107">Aumenti fisici</span><span class="sxs-lookup"><span data-stu-id="5d0d3-107">Physical increases</span></span>
<span data-ttu-id="5d0d3-108">Quando viene registrata una transazione fisica, lo stato del record di transazione è **Ricevuto**.</span><span class="sxs-lookup"><span data-stu-id="5d0d3-108">When a physical transaction is posted, the status of the transaction record is **Received**.</span></span> <span data-ttu-id="5d0d3-109">Vengono considerate aumenti fisici le seguenti transazioni:</span><span class="sxs-lookup"><span data-stu-id="5d0d3-109">The following transactions are considered physical increases:</span></span>

-   <span data-ttu-id="5d0d3-110">Ricevimento ordini fornitore</span><span class="sxs-lookup"><span data-stu-id="5d0d3-110">Purchase order receipt</span></span>
-   <span data-ttu-id="5d0d3-111">Reso documento di trasporto di ordine cliente</span><span class="sxs-lookup"><span data-stu-id="5d0d3-111">Sales order packing slip return</span></span>
-   <span data-ttu-id="5d0d3-112">Dichiarazione di un ordine di produzione come finito</span><span class="sxs-lookup"><span data-stu-id="5d0d3-112">Reporting a production order as finished</span></span>
-   <span data-ttu-id="5d0d3-113">Per prodotto su una distinta di prelievo dell'ordine di produzione</span><span class="sxs-lookup"><span data-stu-id="5d0d3-113">By-product on a production order picking list</span></span>

## <a name="financial-increases"></a><span data-ttu-id="5d0d3-114">Aumenti finanziari</span><span class="sxs-lookup"><span data-stu-id="5d0d3-114">Financial increases</span></span>
<span data-ttu-id="5d0d3-115">Quando viene registrata una transazione in entrata finanziaria, lo stato del record di transazione che aumenta la quantità è **Acquistato**.</span><span class="sxs-lookup"><span data-stu-id="5d0d3-115">When a financial receipt transaction is posted, the status of the transaction record that increases the quantity is **Purchased**.</span></span> <span data-ttu-id="5d0d3-116">Vengono considerate aumenti finanziari le seguenti transazioni:</span><span class="sxs-lookup"><span data-stu-id="5d0d3-116">The following transactions are considered financial increases:</span></span>

-   <span data-ttu-id="5d0d3-117">Fattura fornitore</span><span class="sxs-lookup"><span data-stu-id="5d0d3-117">Vendor invoice</span></span>
-   <span data-ttu-id="5d0d3-118">Fatture ordine cliente per un reso</span><span class="sxs-lookup"><span data-stu-id="5d0d3-118">Sales order invoice for a return</span></span>
-   <span data-ttu-id="5d0d3-119">Determinazione costi ordine di produzione</span><span class="sxs-lookup"><span data-stu-id="5d0d3-119">Production order costing</span></span>
-   <span data-ttu-id="5d0d3-120">Giornali di registrazione magazzino di quantità positive, ad esempio movimenti, profitti e perdite, conteggio, distinta base e trasferimento</span><span class="sxs-lookup"><span data-stu-id="5d0d3-120">Positive quantity inventory journals, such as movement, profit and loss, counting, bill of materials, and transfer</span></span>

## <a name="transactions-that-increase-quantity"></a><span data-ttu-id="5d0d3-121">Transazioni che aumentano la quantità</span><span class="sxs-lookup"><span data-stu-id="5d0d3-121">Transactions that increase quantity</span></span>
<span data-ttu-id="5d0d3-122">Le transazioni che aumentano la quantità vengono registrate al prezzo di costo medio corrente.</span><span class="sxs-lookup"><span data-stu-id="5d0d3-122">Transactions that increase quantity are posted at the running average cost price.</span></span> <span data-ttu-id="5d0d3-123">Finance and Operations calcola un prezzo di costo medio corrente basato sul costo di ciascuna transazione per ogni dimensione inventariale tracciata finanziariamente.</span><span class="sxs-lookup"><span data-stu-id="5d0d3-123">Finance and Operations calculates a running average cost price that is based on the cost of each of these transactions for each inventory dimension that is being tracked financially.</span></span> <span data-ttu-id="5d0d3-124">Per informazioni sul prezzo di costo medio corrente, vedere [Informazioni sul prezzo di costo medio corrente](running-average-cost-price.md).</span><span class="sxs-lookup"><span data-stu-id="5d0d3-124">For information about running average cost prices, see [Running average cost price](running-average-cost-price.md).</span></span>

## <a name="transactions-that-decrease-quantity"></a><span data-ttu-id="5d0d3-125">Transazioni che riducono la quantità</span><span class="sxs-lookup"><span data-stu-id="5d0d3-125">Transactions that decrease quantity</span></span>
<span data-ttu-id="5d0d3-126">In Finance and Operations viene utilizzato il prezzo di costo medio corrente calcolato quando viene registrata una transazione che riduce la quantità, indipendentemente dal modello inventariale associato a quelle scorte,</span><span class="sxs-lookup"><span data-stu-id="5d0d3-126">Finance and Operations uses the calculated running average cost price when a transaction that decreases quantity is posted, regardless of the inventory model that is associated with that inventory.</span></span> <span data-ttu-id="5d0d3-127">purché la transazione che riduce la quantità non fosse precedentemente contrassegnata su un'altra transazione prima della registrazione.</span><span class="sxs-lookup"><span data-stu-id="5d0d3-127">The transaction that decreases quantity must not have been marked to another transaction before it was posted.</span></span> <span data-ttu-id="5d0d3-128">Se le scorte fisiche disponibili diventano negative, in Finance and Operations verrà utilizzato il costo di magazzino definito per l'articoloo nella pagina **Articolo**.</span><span class="sxs-lookup"><span data-stu-id="5d0d3-128">If the physical on-hand inventory becomes negative, Finance and Operations uses the inventory cost that is defined for the item on the **Item** page.</span></span> <span data-ttu-id="5d0d3-129">**Nota**: se è attivata la funzionalità multisito, il costo sarà invece il costo di magazzino definito per un sito nella pagina **Impostazioni ordine predefinite**.</span><span class="sxs-lookup"><span data-stu-id="5d0d3-129">**Note:** If multisite functionality is enabled, this cost will instead be the inventory cost that is defined for a site on the **Default order settings** page.</span></span>

## <a name="physical-issues-vs-financial-issues"></a><span data-ttu-id="5d0d3-130">Uscite fisiche e finanziarie</span><span class="sxs-lookup"><span data-stu-id="5d0d3-130">Physical issues vs. financial issues</span></span>
<span data-ttu-id="5d0d3-131">Quando viene registrata una transazione fisica in uscita, lo stato del record di transazione è **Detratto**.</span><span class="sxs-lookup"><span data-stu-id="5d0d3-131">When a physical issue transaction is posted, the status of the transaction record is **Deducted**.</span></span> <span data-ttu-id="5d0d3-132">Vengono considerate uscite finanziarie le seguenti transazioni:</span><span class="sxs-lookup"><span data-stu-id="5d0d3-132">The following transactions are considered physical issues:</span></span>

-   <span data-ttu-id="5d0d3-133">Giornale di registrazione distinte di prelievo dell'ordine di produzione</span><span class="sxs-lookup"><span data-stu-id="5d0d3-133">Production order picking list journal</span></span>
-   <span data-ttu-id="5d0d3-134">Documento di trasporto ordine cliente</span><span class="sxs-lookup"><span data-stu-id="5d0d3-134">Sales order packing slip</span></span>
-   <span data-ttu-id="5d0d3-135">Reso documento di trasporto di ordine fornitore</span><span class="sxs-lookup"><span data-stu-id="5d0d3-135">Purchase order packing slip return</span></span>

<span data-ttu-id="5d0d3-136">Quando viene registrata una transazione finanziaria, lo stato del record di transazione è **Venduto**.</span><span class="sxs-lookup"><span data-stu-id="5d0d3-136">When a financial transaction is posted, the status of the transaction record is **Sold**.</span></span> <span data-ttu-id="5d0d3-137">Vengono considerate uscite finanziarie le seguenti transazioni</span><span class="sxs-lookup"><span data-stu-id="5d0d3-137">The following transactions are considered financial issues:</span></span>

-   <span data-ttu-id="5d0d3-138">Fine di un ordine di produzione</span><span class="sxs-lookup"><span data-stu-id="5d0d3-138">Ending a production order</span></span>
-   <span data-ttu-id="5d0d3-139">Fattura ordine cliente</span><span class="sxs-lookup"><span data-stu-id="5d0d3-139">Sales order invoice</span></span>
-   <span data-ttu-id="5d0d3-140">Reso fattura fornitore</span><span class="sxs-lookup"><span data-stu-id="5d0d3-140">Vendor invoice return</span></span>
-   <span data-ttu-id="5d0d3-141">Giornali di registrazione magazzino di quantità negative, ad esempio movimenti, profitti e perdite, conteggio, distinta base e trasferimento</span><span class="sxs-lookup"><span data-stu-id="5d0d3-141">Negative quantity inventory journals, such as movement, profit and loss, counting, bill of materials, and transfer</span></span>

<span data-ttu-id="5d0d3-142">Le transazioni che riducono la quantità vengono registrate al prezzo di costo medio corrente.</span><span class="sxs-lookup"><span data-stu-id="5d0d3-142">Transactions that decrease quantity are posted at the running average cost price.</span></span> <span data-ttu-id="5d0d3-143">La procedura di chiusura dell'inventario, pertanto, è necessaria per liquidare le transazioni in uscita a fronte delle transazioni in entrata in base al modello inventariale assegnato a ciascun articolo.</span><span class="sxs-lookup"><span data-stu-id="5d0d3-143">Therefore, the inventory close procedure is required in order to settle issue transactions to receipt transactions, based on the inventory model that is assigned to each item.</span></span>




