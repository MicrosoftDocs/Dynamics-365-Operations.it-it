---
title: La quantità supera la percentuale di limite minimo di fornitura durante la generazione del documento di trasporto
description: Quando si genera un documento di trasporto, il carico in uscita contiene una quantità che supera la percentuale di limite minimo di fornitura.
author: GalynaFedorova
ms.date: 5/31/2021
ms.topic: troubleshooting
ms.search.form: WHSLoadTable_WHSSalesPackingSlipPost,WHSLoadPlanningListPage_WHSSalesPackingSlipPost,WHSLoadPlanningWorkbench_WHSSalesPackingSlipPost
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: ecdd377d12faf40f64736e93671dcf42ff132403
ms.sourcegitcommit: e6437d994c3be0c5bb4a9263af3aa8351020d83a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/14/2021
ms.locfileid: "6249122"
---
# <a name="quantity-exceeds-under-delivery-percentage-during-packing-slip-generation"></a><span data-ttu-id="89781-103">La quantità supera la percentuale di limite minimo di fornitura durante la generazione del documento di trasporto</span><span class="sxs-lookup"><span data-stu-id="89781-103">Quantity exceeds under-delivery percentage during packing slip generation</span></span>

<span data-ttu-id="89781-104">Codice errore: SYS24921</span><span class="sxs-lookup"><span data-stu-id="89781-104">Error code: SYS24921</span></span>

## <a name="symptoms"></a><span data-ttu-id="89781-105">Sintomi</span><span class="sxs-lookup"><span data-stu-id="89781-105">Symptoms</span></span>

<span data-ttu-id="89781-106">Quando si genera un documento di trasporto, il carico in uscita contiene una quantità che supera la percentuale di limite minimo di fornitura.</span><span class="sxs-lookup"><span data-stu-id="89781-106">When you generate a packing slip, the outbound load contains a quantity that exceeds the under-delivery percentage.</span></span>

<span data-ttu-id="89781-107">Quando si tenta di generare il documento di trasporto, il sistema mostra il seguente messaggio di errore:</span><span class="sxs-lookup"><span data-stu-id="89781-107">When you try to generate a packing slip, the system shows the following error message:</span></span>

> <span data-ttu-id="89781-108">Il limite minimo di fornitura della riga è pari al %1 percento, mentre quello consentito è solo del %2 percento.</span><span class="sxs-lookup"><span data-stu-id="89781-108">Underdelivery of line is %1 percent, but the allowed underdelivery is only %2 percent.</span></span>

<span data-ttu-id="89781-109">Pertanto, non è possibile generare il documento di trasporto per il carico.</span><span class="sxs-lookup"><span data-stu-id="89781-109">Therefore, you can't generate the packing slip for the load.</span></span>

## <a name="cause"></a><span data-ttu-id="89781-110">Causa</span><span class="sxs-lookup"><span data-stu-id="89781-110">Cause</span></span>

<span data-ttu-id="89781-111">La quantità prelevata per il carico o la spedizione è minore della quantità ordinata e non rientra nell'intervallo della percentuale di limite minimo di fornitura.</span><span class="sxs-lookup"><span data-stu-id="89781-111">The picked quantity for the load or shipment is less than the ordered quantity and isn't within the range of the under-delivery percentage.</span></span>

## <a name="resolution"></a><span data-ttu-id="89781-112">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="89781-112">Resolution</span></span>

<span data-ttu-id="89781-113">Il carico o la spedizione si trova attualmente in uno stato in cui la generazione del documento di trasporto non riesce.</span><span class="sxs-lookup"><span data-stu-id="89781-113">The load or shipment is currently in a state where packing slip generation fails.</span></span> <span data-ttu-id="89781-114">Per risolvere il problema, completare una o più delle attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="89781-114">To fix this issue, complete one of the following tasks:</span></span>

- <span data-ttu-id="89781-115">Rettifica la percentuale di limite minimo di fornitura.</span><span class="sxs-lookup"><span data-stu-id="89781-115">Adjust the under-delivery percentage.</span></span>
- <span data-ttu-id="89781-116">Storna e apporta rettifiche.</span><span class="sxs-lookup"><span data-stu-id="89781-116">Reverse and make adjustments.</span></span>

### <a name="adjust-the-under-delivery-percentage"></a><span data-ttu-id="89781-117">Rettifica la percentuale di limite minimo di fornitura</span><span class="sxs-lookup"><span data-stu-id="89781-117">Adjust the under-delivery percentage</span></span>

<span data-ttu-id="89781-118">Utilizza la seguente procedura per rettificare la percentuale di limite minimo di fornitura.</span><span class="sxs-lookup"><span data-stu-id="89781-118">Use the following procedure to adjust the under-delivery percentage.</span></span>

1. <span data-ttu-id="89781-119">Vai a **Contabilità clienti \> Ordini \> Tutti gli ordini**.</span><span class="sxs-lookup"><span data-stu-id="89781-119">Go to **Accounts receivable \> Orders \> All orders**.</span></span>
1. <span data-ttu-id="89781-120">Selezionare l'ordine cliente per il quale non è possibile registrare un documento di trasporto per il carico.</span><span class="sxs-lookup"><span data-stu-id="89781-120">Select the sales order for which you can't post a packing slip for the load.</span></span>
1. <span data-ttu-id="89781-121">Nella scheda  **Righe ordine cliente**, seleziona la riga ordine cliente dell'articolo che supera la percentuale di limite minimo di fornitura.</span><span class="sxs-lookup"><span data-stu-id="89781-121">On the **Sales order lines** tab, select the sales order line for the item that exceeds the under-delivery percentage.</span></span>
1. <span data-ttu-id="89781-122">Nella scheda  **Dettagli riga** seleziona **Consegna**.</span><span class="sxs-lookup"><span data-stu-id="89781-122">On the  **Line details** tab, select **Delivery**.</span></span>
1. <span data-ttu-id="89781-123">Imposta il campo **Limite minimo di fornitura** su una percentuale maggiore che tiene conto della quantità prelevata rispetto alla quantità di carico, in modo che possa procedere la generazione del documento di trasporto.</span><span class="sxs-lookup"><span data-stu-id="89781-123">Set the **Underdelivery** field to a larger percentage that accommodates the quantity that was picked against the load quantity, so that packing slip generation can proceed.</span></span>

### <a name="reverse-and-make-adjustments"></a><span data-ttu-id="89781-124">Storna e apporta rettifiche</span><span class="sxs-lookup"><span data-stu-id="89781-124">Reverse and make adjustments</span></span>

<span data-ttu-id="89781-125">Storna tutto ciò che è stato registrato per il carico (ad esempio, documento di trasporto, conferma di spedizione e lavoro), apporta le rettifiche all'ordine di vendita, rilascia nuovamente l'ordine al magazzino e completa la procedura di spedizione.</span><span class="sxs-lookup"><span data-stu-id="89781-125">Reverse everything that has been posted for the load (for example, the packing slip, shipment confirmation, and work), make sales order adjustments, re-release the order to the warehouse, and complete the shipment procedure.</span></span>

<span data-ttu-id="89781-126">Utilizza la seguente procedura per annullare un documento di trasporto.</span><span class="sxs-lookup"><span data-stu-id="89781-126">Use the following procedure to cancel a packing slip.</span></span>

1. <span data-ttu-id="89781-127">Passare a **Gestione magazzino \> Carichi \> Tutti i carichi**.</span><span class="sxs-lookup"><span data-stu-id="89781-127">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="89781-128">Nel riquadro azioni, nella scheda  **Spedisci e ricevi** nel gruppo  **Storna** seleziona  **Annulla documenti di trasporto**.</span><span class="sxs-lookup"><span data-stu-id="89781-128">On the Action Pane, on the **Ship and receive** tab, in the **Reverse** group, select **Cancel packing slips**.</span></span>

<span data-ttu-id="89781-129">Utilizza la seguente procedura per stornare una conferma di spedizione.</span><span class="sxs-lookup"><span data-stu-id="89781-129">Use the following procedure to reverse a shipment confirmation.</span></span>

1. <span data-ttu-id="89781-130">Passare a **Gestione magazzino \> Carichi \> Tutti i carichi**.</span><span class="sxs-lookup"><span data-stu-id="89781-130">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="89781-131">Nel riquadro azioni, nella scheda  **Spedisci e ricevi** nel gruppo  **Storna** seleziona  **Storna conferma spedizione**.</span><span class="sxs-lookup"><span data-stu-id="89781-131">On the Action Pane, on the **Ship and receive** tab, in the **Reverse** group, select **Reverse shipment confirmation**.</span></span>

<span data-ttu-id="89781-132">Utilizza la seguente procedura per stornare il lavoro.</span><span class="sxs-lookup"><span data-stu-id="89781-132">Use the following procedure to reverse work.</span></span>

1. <span data-ttu-id="89781-133">Passare a **Gestione magazzino \> Carichi \> Tutti i carichi**.</span><span class="sxs-lookup"><span data-stu-id="89781-133">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="89781-134">Nella scheda  **Lavoro** del riquadro azioni, nel gruppo  **Carichi**, seleziona  **Storna lavoro**.</span><span class="sxs-lookup"><span data-stu-id="89781-134">On the Action Pane, on the **Loads** tab, in the **Work** group, select **Reverse work**.</span></span>
