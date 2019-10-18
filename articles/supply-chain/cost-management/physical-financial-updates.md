---
title: Aggiornamenti fisici e finanziari
description: In questo argomento viene fornita una panoramica dei tipi di transazioni che aumentano e riducono le quantità delle scorte.
author: AndersGirke
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventTrans, InventTransVoucher
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 75023
ms.assetid: 128340e1-c573-48e6-b835-6c350d8dd0fb
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4360f9132d31c9d0038f51c68c1f6c3fcaaa2025
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/30/2019
ms.locfileid: "2250870"
---
# <a name="physical-and-financial-updates"></a><span data-ttu-id="726f2-103">Aggiornamenti fisici e finanziari</span><span class="sxs-lookup"><span data-stu-id="726f2-103">Physical and financial updates</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="726f2-104">In questo argomento viene fornita una panoramica dei tipi di transazioni che aumentano e riducono le quantità delle scorte.</span><span class="sxs-lookup"><span data-stu-id="726f2-104">This topic provides an overview of which types of transactions increase or decrease inventory quantities.</span></span> 

<span data-ttu-id="726f2-105">In Dynamics 365 Supply Chain Management le transazioni di magazzino possono essere aggiornate fisicamente e finanziariamente.</span><span class="sxs-lookup"><span data-stu-id="726f2-105">Inventory transactions can be physically updated and financially updated in Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="726f2-106">Alcuni tipi di transazioni di magazzino e di transazioni finanziarie determinano un incremento delle quantità di scorte, altre una riduzione.</span><span class="sxs-lookup"><span data-stu-id="726f2-106">Some types of physical and financial transactions increase inventory quantities, whereas others decrease the quantity.</span></span>

## <a name="physical-increases"></a><span data-ttu-id="726f2-107">Aumenti fisici</span><span class="sxs-lookup"><span data-stu-id="726f2-107">Physical increases</span></span>
<span data-ttu-id="726f2-108">Quando viene registrata una transazione fisica, lo stato del record di transazione è **Ricevuto**.</span><span class="sxs-lookup"><span data-stu-id="726f2-108">When a physical transaction is posted, the status of the transaction record is **Received**.</span></span> <span data-ttu-id="726f2-109">Vengono considerate aumenti fisici le seguenti transazioni:</span><span class="sxs-lookup"><span data-stu-id="726f2-109">The following transactions are considered physical increases:</span></span>

-   <span data-ttu-id="726f2-110">Ricevimento ordini fornitore</span><span class="sxs-lookup"><span data-stu-id="726f2-110">Purchase order receipt</span></span>
-   <span data-ttu-id="726f2-111">Reso documento di trasporto di ordine cliente</span><span class="sxs-lookup"><span data-stu-id="726f2-111">Sales order packing slip return</span></span>
-   <span data-ttu-id="726f2-112">Dichiarazione di un ordine di produzione come finito</span><span class="sxs-lookup"><span data-stu-id="726f2-112">Reporting a production order as finished</span></span>
-   <span data-ttu-id="726f2-113">Per prodotto su una distinta di prelievo dell'ordine di produzione</span><span class="sxs-lookup"><span data-stu-id="726f2-113">By-product on a production order picking list</span></span>

## <a name="financial-increases"></a><span data-ttu-id="726f2-114">Aumenti finanziari</span><span class="sxs-lookup"><span data-stu-id="726f2-114">Financial increases</span></span>
<span data-ttu-id="726f2-115">Quando viene registrata una transazione in entrata finanziaria, lo stato del record di transazione che aumenta la quantità è **Acquistato**.</span><span class="sxs-lookup"><span data-stu-id="726f2-115">When a financial receipt transaction is posted, the status of the transaction record that increases the quantity is **Purchased**.</span></span> <span data-ttu-id="726f2-116">Vengono considerate aumenti finanziari le seguenti transazioni:</span><span class="sxs-lookup"><span data-stu-id="726f2-116">The following transactions are considered financial increases:</span></span>

-   <span data-ttu-id="726f2-117">Fattura fornitore</span><span class="sxs-lookup"><span data-stu-id="726f2-117">Vendor invoice</span></span>
-   <span data-ttu-id="726f2-118">Fatture ordine cliente per un reso</span><span class="sxs-lookup"><span data-stu-id="726f2-118">Sales order invoice for a return</span></span>
-   <span data-ttu-id="726f2-119">Determinazione costi ordine di produzione</span><span class="sxs-lookup"><span data-stu-id="726f2-119">Production order costing</span></span>
-   <span data-ttu-id="726f2-120">Giornali di registrazione magazzino di quantità positive, ad esempio movimenti, profitti e perdite, conteggio, distinta base e trasferimento</span><span class="sxs-lookup"><span data-stu-id="726f2-120">Positive quantity inventory journals, such as movement, profit and loss, counting, bill of materials, and transfer</span></span>

## <a name="transactions-that-increase-quantity"></a><span data-ttu-id="726f2-121">Transazioni che aumentano la quantità</span><span class="sxs-lookup"><span data-stu-id="726f2-121">Transactions that increase quantity</span></span>
<span data-ttu-id="726f2-122">Le transazioni che aumentano la quantità vengono registrate al prezzo di costo medio corrente.</span><span class="sxs-lookup"><span data-stu-id="726f2-122">Transactions that increase quantity are posted at the running average cost price.</span></span> <span data-ttu-id="726f2-123">Il prezzo di costo medio corrente calcolato si basa sul costo di ciascuna transazione per ogni dimensione inventariale tracciata finanziariamente.</span><span class="sxs-lookup"><span data-stu-id="726f2-123">The calculated running average cost price is based on the cost of each of these transactions for each inventory dimension that is being tracked financially.</span></span> <span data-ttu-id="726f2-124">Per informazioni sul prezzo di costo medio corrente, vedere [Informazioni sul prezzo di costo medio corrente](running-average-cost-price.md).</span><span class="sxs-lookup"><span data-stu-id="726f2-124">For information about running average cost prices, see [Running average cost price](running-average-cost-price.md).</span></span>

## <a name="transactions-that-decrease-quantity"></a><span data-ttu-id="726f2-125">Transazioni che riducono la quantità</span><span class="sxs-lookup"><span data-stu-id="726f2-125">Transactions that decrease quantity</span></span>
<span data-ttu-id="726f2-126">Viene utilizzato il prezzo di costo medio corrente calcolato quando viene registrata una transazione che riduce la quantità, indipendentemente dal modello inventariale associato a quelle scorte,</span><span class="sxs-lookup"><span data-stu-id="726f2-126">The calculated running average cost price is used  when a transaction that decreases quantity is posted, regardless of the inventory model that is associated with that inventory.</span></span> <span data-ttu-id="726f2-127">purché la transazione che riduce la quantità non fosse precedentemente contrassegnata su un'altra transazione prima della registrazione.</span><span class="sxs-lookup"><span data-stu-id="726f2-127">The transaction that decreases quantity must not have been marked to another transaction before it was posted.</span></span> <span data-ttu-id="726f2-128">Se le scorte fisiche disponibili diventano negative, verrà utilizzato il costo di magazzino definito per l'articolo nella pagina **Articolo**.</span><span class="sxs-lookup"><span data-stu-id="726f2-128">If the physical on-hand inventory becomes negative, the inventory cost that is defined for the item on the **Item** page is used.</span></span> 

> [!NOTE]
> <span data-ttu-id="726f2-129">Se è attivata la funzionalità multisito, il costo sarà invece il costo di magazzino definito per un sito nella pagina **Impostazioni ordine predefinite**.</span><span class="sxs-lookup"><span data-stu-id="726f2-129">If multisite functionality is enabled, this cost will instead be the inventory cost that is defined for a site on the **Default order settings** page.</span></span>

## <a name="physical-issues-vs-financial-issues"></a><span data-ttu-id="726f2-130">Uscite fisiche e finanziarie</span><span class="sxs-lookup"><span data-stu-id="726f2-130">Physical issues vs. financial issues</span></span>
<span data-ttu-id="726f2-131">Quando viene registrata una transazione fisica in uscita, lo stato del record di transazione è **Detratto**.</span><span class="sxs-lookup"><span data-stu-id="726f2-131">When a physical issue transaction is posted, the status of the transaction record is **Deducted**.</span></span> <span data-ttu-id="726f2-132">Vengono considerate uscite finanziarie le seguenti transazioni:</span><span class="sxs-lookup"><span data-stu-id="726f2-132">The following transactions are considered physical issues:</span></span>

-   <span data-ttu-id="726f2-133">Giornale di registrazione distinte di prelievo dell'ordine di produzione</span><span class="sxs-lookup"><span data-stu-id="726f2-133">Production order picking list journal</span></span>
-   <span data-ttu-id="726f2-134">Documento di trasporto ordine cliente</span><span class="sxs-lookup"><span data-stu-id="726f2-134">Sales order packing slip</span></span>
-   <span data-ttu-id="726f2-135">Reso documento di trasporto di ordine fornitore</span><span class="sxs-lookup"><span data-stu-id="726f2-135">Purchase order packing slip return</span></span>

<span data-ttu-id="726f2-136">Quando viene registrata una transazione finanziaria, lo stato del record di transazione è **Venduto**.</span><span class="sxs-lookup"><span data-stu-id="726f2-136">When a financial transaction is posted, the status of the transaction record is **Sold**.</span></span> <span data-ttu-id="726f2-137">Vengono considerate uscite finanziarie le seguenti transazioni</span><span class="sxs-lookup"><span data-stu-id="726f2-137">The following transactions are considered financial issues:</span></span>

-   <span data-ttu-id="726f2-138">Fine di un ordine di produzione</span><span class="sxs-lookup"><span data-stu-id="726f2-138">Ending a production order</span></span>
-   <span data-ttu-id="726f2-139">Fattura ordine cliente</span><span class="sxs-lookup"><span data-stu-id="726f2-139">Sales order invoice</span></span>
-   <span data-ttu-id="726f2-140">Reso fattura fornitore</span><span class="sxs-lookup"><span data-stu-id="726f2-140">Vendor invoice return</span></span>
-   <span data-ttu-id="726f2-141">Giornali di registrazione magazzino di quantità negative, ad esempio movimenti, profitti e perdite, conteggio, distinta base e trasferimento</span><span class="sxs-lookup"><span data-stu-id="726f2-141">Negative quantity inventory journals, such as movement, profit and loss, counting, bill of materials, and transfer</span></span>

<span data-ttu-id="726f2-142">Le transazioni che riducono la quantità vengono registrate al prezzo di costo medio corrente.</span><span class="sxs-lookup"><span data-stu-id="726f2-142">Transactions that decrease quantity are posted at the running average cost price.</span></span> <span data-ttu-id="726f2-143">La procedura di chiusura dell'inventario, pertanto, è necessaria per liquidare le transazioni in uscita a fronte delle transazioni in entrata in base al modello inventariale assegnato a ciascun articolo.</span><span class="sxs-lookup"><span data-stu-id="726f2-143">Therefore, the inventory close procedure is required in order to settle issue transactions to receipt transactions, based on the inventory model that is assigned to each item.</span></span>
