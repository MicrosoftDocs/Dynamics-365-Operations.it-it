---
title: L'arrotondamento decimale della quantità di aggiornamento fisico non è corretto
description: Quando si genera un documento di trasporto, il carico in uscita contiene una quantità che non corrisponde alla precisione decimale definita nell'unità.
author: GalynaFedorova
ms.date: 5/31/2021
ms.topic: troubleshooting
ms.search.form: WHSLoadPlanningListPage_WHSSalesPackingSlipPost, WHSLoadTable_WHSSalesPackingSlipPost
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 1e63440834f516879aa8ad711bd789e62b0ee993
ms.sourcegitcommit: e6437d994c3be0c5bb4a9263af3aa8351020d83a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/14/2021
ms.locfileid: "6248789"
---
# <a name="decimal-rounding-of-the-physical-updating-quantity-is-incorrect"></a><span data-ttu-id="95c75-103">L'arrotondamento decimale della quantità di aggiornamento fisico non è corretto</span><span class="sxs-lookup"><span data-stu-id="95c75-103">Decimal rounding of the physical updating quantity is incorrect</span></span>

<span data-ttu-id="95c75-104">Codice errore: SYS19589</span><span class="sxs-lookup"><span data-stu-id="95c75-104">Error code: SYS19589</span></span>

## <a name="symptoms"></a><span data-ttu-id="95c75-105">Sintomi</span><span class="sxs-lookup"><span data-stu-id="95c75-105">Symptoms</span></span>

<span data-ttu-id="95c75-106">Quando si genera un documento di trasporto, il carico in uscita contiene una quantità che non corrisponde alla precisione decimale definita nell'unità.</span><span class="sxs-lookup"><span data-stu-id="95c75-106">When you generate a packing slip, the outbound load contains a quantity that doesn't match the decimal precision that is defined in the unit.</span></span>

<span data-ttu-id="95c75-107">Quando si tenta di generare il documento di trasporto, il sistema mostra il seguente messaggio di errore:</span><span class="sxs-lookup"><span data-stu-id="95c75-107">When you try to generate a packing slip, the system shows the following error message:</span></span>

> <span data-ttu-id="95c75-108">L'arrotondamento decimale della quantità di aggiornamento fisico nell'unità %1 è errato.</span><span class="sxs-lookup"><span data-stu-id="95c75-108">Decimal rounding of the physical updating quantity in the unit %1 is incorrect.</span></span>

<span data-ttu-id="95c75-109">Pertanto, non è possibile generare il documento di trasporto per il carico.</span><span class="sxs-lookup"><span data-stu-id="95c75-109">Therefore, you can't generate the packing slip for the load.</span></span>

## <a name="cause"></a><span data-ttu-id="95c75-110">Causa</span><span class="sxs-lookup"><span data-stu-id="95c75-110">Cause</span></span>

<span data-ttu-id="95c75-111">Il sistema valuta se l'arrotondamento decimale della quantità di spedizione corrisponde alla precisione decimale definita per l'unità di spedizione.</span><span class="sxs-lookup"><span data-stu-id="95c75-111">The system evaluates whether the decimal rounding of the shipping quantity corresponds to the decimal precision that is defined for the shipping unit.</span></span> <span data-ttu-id="95c75-112">Quando il sistema arrotonda la quantità di spedizione al numero specificato di cifre decimali, se rileva che la quantità di spedizione arrotondata non corrisponde alla quantità di spedizione effettiva, non è possibile generare il documento di trasporto.</span><span class="sxs-lookup"><span data-stu-id="95c75-112">When the system rounds the shipping quantity to the specified number of decimal places, if it finds that the rounded shipping quantity doesn't match the actual shipping quantity, you can't generate the packing slip.</span></span> <span data-ttu-id="95c75-113">Ad esempio, questo problema potrebbe verificarsi se la quantità di vendita è 1,75 chilogrammi (kg), ma la precisione decimale è impostata su *1*.</span><span class="sxs-lookup"><span data-stu-id="95c75-113">For example, this issue might occur if the sales quantity is 1.75 kilograms (kg), but the decimal precision is set to *1*.</span></span>

## <a name="resolution"></a><span data-ttu-id="95c75-114">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="95c75-114">Resolution</span></span>

<span data-ttu-id="95c75-115">Il carico o la spedizione si trova attualmente in uno stato in cui la generazione del documento di trasporto non riesce.</span><span class="sxs-lookup"><span data-stu-id="95c75-115">The load or shipment is currently in a state where packing slip generation fails.</span></span> <span data-ttu-id="95c75-116">Per risolvere il problema, completare una o più delle attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="95c75-116">To fix this issue, complete one of the following tasks:</span></span>

- <span data-ttu-id="95c75-117">Rivedere le righe di carico e apportare le modifiche per garantire che la quantità possa essere convertita in modo pulito senza numeri decimali e altri problemi di arrotondamento.</span><span class="sxs-lookup"><span data-stu-id="95c75-117">Review your load lines, and make adjustments to ensure that the quantity can be cleanly converted without decimal numbers and any other rounding issues.</span></span>
- <span data-ttu-id="95c75-118">Rivedere le linee di carico e apportare le modifiche per garantire che l'unità e la quantità siano allineate con la precisione decimale dell'unità.</span><span class="sxs-lookup"><span data-stu-id="95c75-118">Review your load lines, and make adjustments to ensure that the unit and quantity are aligned with the decimal precision of the unit.</span></span>

### <a name="review-your-load-lines-and-make-adjustments-to-ensure-that-the-quantity-can-be-cleanly-converted-without-decimal-numbers-and-any-other-rounding-issues"></a><span data-ttu-id="95c75-119">Rivedere le righe di carico e apportare le modifiche per garantire che la quantità possa essere convertita in modo pulito senza numeri decimali e altri problemi di arrotondamento</span><span class="sxs-lookup"><span data-stu-id="95c75-119">Review your load lines, and make adjustments to ensure that the quantity can be cleanly converted without decimal numbers and any other rounding issues</span></span>

<span data-ttu-id="95c75-120">Usare la seguente procedura per rivedere le righe di carico e apportare le modifiche per garantire che la quantità possa essere convertita in modo pulito senza numeri decimali e altri problemi di arrotondamento.</span><span class="sxs-lookup"><span data-stu-id="95c75-120">Use the following procedure to review your load lines and make adjustments to ensure that the quantity can be cleanly converted without decimal numbers and any other rounding issues.</span></span>

1. <span data-ttu-id="95c75-121">Passare a **Gestione magazzino \> Carichi \> Tutti i carichi**.</span><span class="sxs-lookup"><span data-stu-id="95c75-121">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="95c75-122">Seleziona il carico per il quale non è possibile generare il documento di trasporto.</span><span class="sxs-lookup"><span data-stu-id="95c75-122">Select the load that the packing slip can't be generated for.</span></span>
1. <span data-ttu-id="95c75-123">Nel riquadro azioni, nella scheda  **Spedisci e ricevi** nel gruppo  **Storna** seleziona  **Storna conferma spedizione**.</span><span class="sxs-lookup"><span data-stu-id="95c75-123">On the Action Pane, on the **Ship and receive** tab, in the **Reverse** group, select **Reverse shipment confirmation**.</span></span>
1. <span data-ttu-id="95c75-124">Nella scheda  **Righe carico** seleziona la riga di carico per l'articolo che causa il problema.</span><span class="sxs-lookup"><span data-stu-id="95c75-124">On the **Load lines** tab, select the load line for the item that causes an issue.</span></span>
1. <span data-ttu-id="95c75-125">Seleziona **Riduci quantità prelevata** per rettificare la quantità prelevata.</span><span class="sxs-lookup"><span data-stu-id="95c75-125">Select **Reduce picked quantity** to adjust the picked quantity.</span></span>
1. <span data-ttu-id="95c75-126">Nella scheda  **Dettagli riga** seleziona **Ordine**.</span><span class="sxs-lookup"><span data-stu-id="95c75-126">On the  **Line details** tab, select **Order**.</span></span>
1. <span data-ttu-id="95c75-127">Imposta il campo **Quantità** sulla quantità prelevata (ovvero, il valore del campo **Quantità di lavoro creata**), in modo che possa procedere la generazione del documento di trasporto.</span><span class="sxs-lookup"><span data-stu-id="95c75-127">Set the **Quantity** field to the picked quantity (that is, the value of the **Work created quantity** field), so that packing slip generation can proceed.</span></span>

### <a name="review-your-load-lines-and-make-adjustments-to-ensure-that-the-unit-and-quantity-are-aligned-with-the-decimal-precision-of-the-unit"></a><span data-ttu-id="95c75-128">Rivedere le linee di carico e apportare le modifiche per garantire che l'unità e la quantità siano allineate con la precisione decimale dell'unità</span><span class="sxs-lookup"><span data-stu-id="95c75-128">Review your load lines, and make adjustments to ensure that the unit and quantity are aligned with the decimal precision of the unit</span></span>

<span data-ttu-id="95c75-129">Usa la seguente procedura per rivedere le linee di carico e apportare le modifiche per garantire che l'unità e la quantità siano allineate con la precisione decimale dell'unità.</span><span class="sxs-lookup"><span data-stu-id="95c75-129">Use the following procedure to review your load lines and make adjustments to ensure that the unit and quantity are aligned with the decimal precision of the unit.</span></span>

1. <span data-ttu-id="95c75-130">Passare a **Gestione magazzino \> Carichi \> Tutti i carichi**.</span><span class="sxs-lookup"><span data-stu-id="95c75-130">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="95c75-131">Seleziona il carico per il quale non è possibile generare il documento di trasporto.</span><span class="sxs-lookup"><span data-stu-id="95c75-131">Select the load that the packing slip can't be generated for.</span></span>
1. <span data-ttu-id="95c75-132">Nella scheda dettaglio **Righe carico** seleziona la riga di carico per l'articolo che causa il problema.</span><span class="sxs-lookup"><span data-stu-id="95c75-132">On the **Load lines** FastTab, select the load line for the item that causes an issue.</span></span> <span data-ttu-id="95c75-133">Prendi nota del valore dei campi **Quantità** e **Unità**.</span><span class="sxs-lookup"><span data-stu-id="95c75-133">Make a note of the value of the **Quantity** and **Unit** fields.</span></span>
1. <span data-ttu-id="95c75-134">Vai a **Amministrazione organizzazione \> Unità \> Unità**.</span><span class="sxs-lookup"><span data-stu-id="95c75-134">Go to **Organization administration \> Units \> Units**.</span></span>
1. <span data-ttu-id="95c75-135">Seleziona l'unità per la quale non è possibile generare il documento di trasporto.</span><span class="sxs-lookup"><span data-stu-id="95c75-135">Select the unit that the packing slip can't be generated for.</span></span>
1. <span data-ttu-id="95c75-136">Rettifica il valore del campo **Precisione decimale** come richiesto.</span><span class="sxs-lookup"><span data-stu-id="95c75-136">Adjust the value of the **Decimal precision** field as required.</span></span>
