---
title: Non puoi confermare una spedizione perché la quantità supera la percentuale di limite massimo di fornitura
description: Non puoi confermare una spedizione perché la quantità supera la percentuale di limite massimo di fornitura
author: perlynne
ms.date: 04/21/2021
ms.topic: troubleshooting
ms.search.form: WHSLoadTable_WHSShipConfirm,WHSLoadPlanningListPage_WHSShipConfirm,WHSLoadPlanningWorkbench_WHSShipConfirm,WHSTransportLoad_WHSShipConfirm,WHSShipPlanningListPage_WHSShipConfirm,WHSShipmentDetails_WHSShipConfirm,WHSWorkTable_WHSShipConfirm,WHSWorkTableListPage_WHSShipConfirm,Dialog_WHSOutboundShipConfirmController_WHSOutboundShipConfirm
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: lbc
ms.search.validFrom: 2021-04-21
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: c9b5ba8dedb927ee049d7e53e9a666902f563f49
ms.sourcegitcommit: cd9016e9787169cb800889d335b9c5919ddbe4af
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2021
ms.locfileid: "5938500"
---
# <a name="you-cant-confirm-a-shipment-because-the-quantity-exceeds-the-overdelivery-percentage"></a><span data-ttu-id="dbdb6-103">Non puoi confermare una spedizione perché la quantità supera la percentuale di limite massimo di fornitura</span><span class="sxs-lookup"><span data-stu-id="dbdb6-103">You can't confirm a shipment because the quantity exceeds the overdelivery percentage</span></span>

<span data-ttu-id="dbdb6-104">Codice errore: WAX1687</span><span class="sxs-lookup"><span data-stu-id="dbdb6-104">Error code: WAX1687</span></span>

## <a name="symptoms"></a><span data-ttu-id="dbdb6-105">Sintomi</span><span class="sxs-lookup"><span data-stu-id="dbdb6-105">Symptoms</span></span>

<span data-ttu-id="dbdb6-106">Quando si tenta di confermare una spedizione, il sistema mostra il seguente messaggio di errore:</span><span class="sxs-lookup"><span data-stu-id="dbdb6-106">When you try to confirm a shipment, the system shows the following error message:</span></span>

> <span data-ttu-id="dbdb6-107">La spedizione per il carico %1 non è stata confermata perché la quantità dell'articolo %2 supera la percentuale definita per il limite massimo di fornitura.</span><span class="sxs-lookup"><span data-stu-id="dbdb6-107">The shipment for load %1 could not be confirmed because the quantity for item %2 exceeds the percentage that is defined for overdelivery.</span></span>

<span data-ttu-id="dbdb6-108">Pertanto, non è possibile confermare la spedizione per il carico.</span><span class="sxs-lookup"><span data-stu-id="dbdb6-108">Therefore, you can't confirm the shipment for the load.</span></span>

## <a name="cause"></a><span data-ttu-id="dbdb6-109">Causa</span><span class="sxs-lookup"><span data-stu-id="dbdb6-109">Cause</span></span>

<span data-ttu-id="dbdb6-110">La quantità del carico o della spedizione è stata prelevata solo parzialmente.</span><span class="sxs-lookup"><span data-stu-id="dbdb6-110">The quantity of the load or shipment has been only partially picked.</span></span> <span data-ttu-id="dbdb6-111">La quantità è attualmente superiore alla quantità prelevata di una percentuale che non rientra nella percentuale consentita di limite massimo di fornitura.</span><span class="sxs-lookup"><span data-stu-id="dbdb6-111">The quantity currently exceeds the picked quantity by a percentage that is outside the allowed overdelivery percentage.</span></span>

## <a name="resolution"></a><span data-ttu-id="dbdb6-112">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="dbdb6-112">Resolution</span></span>

<span data-ttu-id="dbdb6-113">Per risolvere il problema, completare una o più delle attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="dbdb6-113">To fix this issue, complete one of the following tasks:</span></span>

- <span data-ttu-id="dbdb6-114">Imposta la quantità della riga di carico.</span><span class="sxs-lookup"><span data-stu-id="dbdb6-114">Set the load line quantity.</span></span>
- <span data-ttu-id="dbdb6-115">Impostare la percentuale di limite massimo di fornitura</span><span class="sxs-lookup"><span data-stu-id="dbdb6-115">Set the overdelivery percentage.</span></span>

### <a name="set-the-load-line-quantity"></a><span data-ttu-id="dbdb6-116">Impostare la quantità della riga di carico</span><span class="sxs-lookup"><span data-stu-id="dbdb6-116">Set the load line quantity</span></span>

<span data-ttu-id="dbdb6-117">Per impostare la quantità della riga di carico, segui questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="dbdb6-117">To set the load line quantity, follow these steps.</span></span>

1. <span data-ttu-id="dbdb6-118">Passare a **Gestione magazzino \> Carichi \> Tutti i carichi**.</span><span class="sxs-lookup"><span data-stu-id="dbdb6-118">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="dbdb6-119">Seleziona il carico per cui la spedizione non può essere confermata.</span><span class="sxs-lookup"><span data-stu-id="dbdb6-119">Select the load that the shipment can't be confirmed for.</span></span>
1. <span data-ttu-id="dbdb6-120">Nella scheda dettaglio **Righe di carico**, seleziona la riga di carico dell'articolo che supera la percentuale di limite massimo di fornitura.</span><span class="sxs-lookup"><span data-stu-id="dbdb6-120">On the **Load lines** FastTab, select the load line for the item that exceeds the overdelivery percentage.</span></span>
1. <span data-ttu-id="dbdb6-121">Nella Scheda dettaglio **Dettagli riga** seleziona **Ordine**.</span><span class="sxs-lookup"><span data-stu-id="dbdb6-121">On the **Line details** FastTab, select **Order**.</span></span>
1. <span data-ttu-id="dbdb6-122">Nel campo **Quantità** impostare il valore sulla quantità prelevata (ovvero, il valore **Quantità di lavoro creata**), in modo che possa verificarsi la conferma della spedizione.</span><span class="sxs-lookup"><span data-stu-id="dbdb6-122">In the **Quantity** field, set the value to the picked quantity (that is, to the **Work created quantity** value), so that shipment confirmation can occur.</span></span>

### <a name="set-the-overdelivery-percentage"></a><span data-ttu-id="dbdb6-123">Impostare la percentuale di limite massimo di fornitura</span><span class="sxs-lookup"><span data-stu-id="dbdb6-123">Set the overdelivery percentage</span></span>

<span data-ttu-id="dbdb6-124">Per impostare il limite minimo di fornitura, segui questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="dbdb6-124">To set the underdelivery percentage, follow these steps.</span></span>

1. <span data-ttu-id="dbdb6-125">Passare a **Gestione magazzino \> Carichi \> Tutti i carichi**.</span><span class="sxs-lookup"><span data-stu-id="dbdb6-125">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="dbdb6-126">Seleziona il carico per cui la spedizione non può essere confermata.</span><span class="sxs-lookup"><span data-stu-id="dbdb6-126">Select the load that the shipment can't be confirmed for.</span></span>
1. <span data-ttu-id="dbdb6-127">Nella scheda dettaglio **Righe di carico**, seleziona la riga di carico dell'articolo che supera la percentuale di limite massimo di fornitura.</span><span class="sxs-lookup"><span data-stu-id="dbdb6-127">On the **Load lines** FastTab, select the load line for the item that exceeds the overdelivery percentage.</span></span>
1. <span data-ttu-id="dbdb6-128">Nella Scheda dettaglio **Dettagli riga** seleziona **Generale**.</span><span class="sxs-lookup"><span data-stu-id="dbdb6-128">On the **Line details** FastTab, select **General**.</span></span>
1. <span data-ttu-id="dbdb6-129">Nel campo **Limite massimo di fornitura** impostare il valore su una percentuale maggiore che tiene conto della quantità prelevata rispetto alla quantità di carico, in modo che possa verificarsi la conferma della spedizione.</span><span class="sxs-lookup"><span data-stu-id="dbdb6-129">In the **Overdelivery** field, set the value to a larger percentage that accommodates the quantity that has been picked against the load quantity, so that shipment confirmation can occur.</span></span>
