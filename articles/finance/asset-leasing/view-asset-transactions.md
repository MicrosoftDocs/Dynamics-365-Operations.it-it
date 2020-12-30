---
title: Visualizzare le transazioni relative a passività, attività e spese
description: Questo argomento spiega come visualizzare le transazioni per un asset in leasing. Queste transazioni includono transazioni di obbligazione sul leasing e transazioni di spese di esecuzione che sono state registrate.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations, Retail
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 7008891d194dc990d13a9f56db155c6990aae0c0
ms.sourcegitcommit: aeee39c01d3f93a6dfcf2013965fa975a740596a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/28/2020
ms.locfileid: "4444997"
---
# <a name="view-liability-asset-and-expense-transactions"></a><span data-ttu-id="82649-104">Visualizzare le transazioni relative a passività, attività e spese</span><span class="sxs-lookup"><span data-stu-id="82649-104">View liability, asset, and expense transactions</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="82649-105">Questo argomento spiega come visualizzare le transazioni per un asset in leasing.</span><span class="sxs-lookup"><span data-stu-id="82649-105">This topic explains how to view transactions for a leased asset.</span></span> <span data-ttu-id="82649-106">Queste transazioni includono transazioni di obbligazione sul leasing e transazioni di spese di esecuzione che sono state registrate.</span><span class="sxs-lookup"><span data-stu-id="82649-106">These transactions include lease liability transactions and executory expense transactions that have been posted.</span></span> <span data-ttu-id="82649-107">I valori contabili dell'passività e dell'asset ROU sono utilizzati in diversi report.</span><span class="sxs-lookup"><span data-stu-id="82649-107">The carrying values of the liability and right-of-use (ROU) asset are used on several reports.</span></span> <span data-ttu-id="82649-108">Sono anche utilizzati per calcolare i valori di rettifica.</span><span class="sxs-lookup"><span data-stu-id="82649-108">They are also used to calculate adjustment values.</span></span>

## <a name="liability-transactions"></a><span data-ttu-id="82649-109">Transazioni di passività</span><span class="sxs-lookup"><span data-stu-id="82649-109">Liability transactions</span></span>

<span data-ttu-id="82649-110">Per visualizzare le transazioni di obbligazione sul leasing, seleziona un leasing nella pagina **Riepilogo leasing**, quindi seleziona **Libri** per aprire i libri allegati al record di leasing.</span><span class="sxs-lookup"><span data-stu-id="82649-110">To view the lease liability transactions, select a lease on the **Lease summary** page, and then select **Books** to open the books that are attached to the lease record.</span></span> <span data-ttu-id="82649-111">Dopo aver registrato un riconoscimento iniziale, una fattura o un giornale di registrazione interessi, seleziona **Transazioni di passività**.</span><span class="sxs-lookup"><span data-stu-id="82649-111">After an initial recognition, an invoice, or an interest journal has been posted, select **Liability transactions**.</span></span>

<span data-ttu-id="82649-112">La pagina **Transazioni di passività** mostra le transazioni che aumentano o diminuiscono l'obbligazione sul leasing.</span><span class="sxs-lookup"><span data-stu-id="82649-112">The **Liability transactions** page shows the transactions that either increase or decrease the lease liability.</span></span> <span data-ttu-id="82649-113">Gli importi negativi in questa pagina rappresentano le transazioni di credito nell'applicazione standard.</span><span class="sxs-lookup"><span data-stu-id="82649-113">Negative amounts on this page represent credit transactions in the standard application.</span></span> <span data-ttu-id="82649-114">Eventuali ratei di interessi sono indicati come valori negativi e aumentano l'obbligazione sul leasing totale.</span><span class="sxs-lookup"><span data-stu-id="82649-114">Any interest accruals are shown as negative values and increase the total lease liability.</span></span> <span data-ttu-id="82649-115">Eventuali rettifiche di leasing sono indicate come valori positivi o negativi, a seconda della natura e dell'impatto del libro di leasing.</span><span class="sxs-lookup"><span data-stu-id="82649-115">Any lease adjustments are shown as positive or negative values, depending on the nature and impact of the lease book.</span></span> <span data-ttu-id="82649-116">L'attuale saldo netto totale dell'obbligazione sul leasing per il leasing selezionato è mostrato in basso a sinistra nella pagina.</span><span class="sxs-lookup"><span data-stu-id="82649-116">The current net total balance of the lease liability for the selected lease is shown at the bottom left of the page.</span></span>

## <a name="asset-transactions"></a><span data-ttu-id="82649-117">Transazioni di cespite</span><span class="sxs-lookup"><span data-stu-id="82649-117">Asset transactions</span></span>

<span data-ttu-id="82649-118">Per visualizzare le transazioni di cespite del leasing, seleziona un leasing nella pagina **Riepilogo leasing**, quindi seleziona **Libri** per aprire i libri cespite allegati al record di leasing.</span><span class="sxs-lookup"><span data-stu-id="82649-118">To view the lease asset transactions, select a lease on the **Lease summary** page, and then select **Books** to open the lease books that are attached to the lease record.</span></span> <span data-ttu-id="82649-119">Seleziona quindi **Transazioni cespiti**.</span><span class="sxs-lookup"><span data-stu-id="82649-119">Then select **Asset transactions**.</span></span>

<span data-ttu-id="82649-120">La pagina **Transazione cespiti** mostra le transazioni che aumentano o diminuiscono il cespite del leasing e i conti di ammortamento accumulato.</span><span class="sxs-lookup"><span data-stu-id="82649-120">The **Asset transaction** page shows the transactions that either increase or decrease the lease asset and accumulated depreciation accounts.</span></span> <span data-ttu-id="82649-121">Gli addebiti vengono visualizzati come valori positivi e gli accrediti come valori negativi, come nella pagina **Transazioni di passività**.</span><span class="sxs-lookup"><span data-stu-id="82649-121">Debits are shown as positive values, and credits are shown as negative values, as on the **Liability transactions** page.</span></span> <span data-ttu-id="82649-122">Il riconoscimento iniziale registrato e il successivo ammortamento accumulato vengono visualizzati in basso a sinistra nella pagina come saldo del cespite.</span><span class="sxs-lookup"><span data-stu-id="82649-122">The posted initial recognition and the next of accumulated depreciation are shown at the bottom left of the page as the asset balance.</span></span> 

## <a name="expenses-transactions"></a><span data-ttu-id="82649-123">Transazioni di spesa</span><span class="sxs-lookup"><span data-stu-id="82649-123">Expenses transactions</span></span>

<span data-ttu-id="82649-124">Per visualizzare le transazioni di spesa del leasing, seleziona un leasing nella pagina **Riepilogo leasing**, quindi seleziona **Libri** per aprire i libri cespite allegati al record di leasing.</span><span class="sxs-lookup"><span data-stu-id="82649-124">To view the lease expense transactions, select a lease on the **Lease summary** page, and then select **Books** to open the lease books that are attached to the lease record.</span></span> <span data-ttu-id="82649-125">Quindi, seleziona **Transazioni di spesa**.</span><span class="sxs-lookup"><span data-stu-id="82649-125">Then select **Expense transactions**.</span></span>

<span data-ttu-id="82649-126">La pagina **Transazioni di spesa** mostra tutte le spese che sono state registrate a fronte del leasing, come gli interessi passivi, le spese di ammortamento e gli eventuali costi di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="82649-126">The **Expense transactions** page shows all the expenses that have been posted against the lease, such as interest expenses, depreciation expenses, and any executory costs.</span></span>
