---
title: Non puoi confermare una spedizione perché gli articoli non sono stati prelevati
description: Non puoi confermare una spedizione perché gli articoli non sono stati prelevati
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
ms.openlocfilehash: 23a517e7769dc86ebec30e4f17c62172a6ad8801
ms.sourcegitcommit: cd9016e9787169cb800889d335b9c5919ddbe4af
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2021
ms.locfileid: "5938497"
---
# <a name="you-cant-confirm-a-shipment-because-items-havent-been-picked"></a><span data-ttu-id="0468b-103">Non puoi confermare una spedizione perché gli articoli non sono stati prelevati</span><span class="sxs-lookup"><span data-stu-id="0468b-103">You can't confirm a shipment because items haven't been picked</span></span>

<span data-ttu-id="0468b-104">Codice di errore: LoadNotPickedAndMovedToFinalShippingLocation</span><span class="sxs-lookup"><span data-stu-id="0468b-104">Error code: LoadNotPickedAndMovedToFinalShippingLocation</span></span>

## <a name="symptoms"></a><span data-ttu-id="0468b-105">Sintomi</span><span class="sxs-lookup"><span data-stu-id="0468b-105">Symptoms</span></span>

<span data-ttu-id="0468b-106">Quando si tenta di confermare una spedizione, il sistema mostra il seguente messaggio di errore:</span><span class="sxs-lookup"><span data-stu-id="0468b-106">When you try to confirm a shipment, the system shows the following error message:</span></span>

> <span data-ttu-id="0468b-107">Alcuni articoli necessari per il carico %1 non sono stati ancora prelevati e spostati nell'ubicazione di spedizione finale.</span><span class="sxs-lookup"><span data-stu-id="0468b-107">Some of the items that are needed for load %1 have not yet been picked and moved to the final shipping location.</span></span>

<span data-ttu-id="0468b-108">Pertanto, non è possibile confermare la spedizione per il carico.</span><span class="sxs-lookup"><span data-stu-id="0468b-108">Therefore, you can't confirm the shipment for the load.</span></span>

## <a name="cause"></a><span data-ttu-id="0468b-109">Causa</span><span class="sxs-lookup"><span data-stu-id="0468b-109">Cause</span></span>

<span data-ttu-id="0468b-110">Il carico o la spedizione non possono essere confermati nello stato attuale perché potrebbe sussistere una delle seguenti condizioni:</span><span class="sxs-lookup"><span data-stu-id="0468b-110">The load or shipment can't be confirmed in its current state because one of the following conditions might exist:</span></span>

- <span data-ttu-id="0468b-111">Il lavoro correlato non è stato ancora prelevato e spostato nell'ubicazione di spedizione finale.</span><span class="sxs-lookup"><span data-stu-id="0468b-111">The related work hasn't yet been picked and moved to the final shipping location.</span></span>
- <span data-ttu-id="0468b-112">La quantità di lavoro prelevata non corrisponde alla quantità di lavoro creata nella riga di carico.</span><span class="sxs-lookup"><span data-stu-id="0468b-112">The picked work quantity doesn't match the created work quantity on the load line.</span></span>

## <a name="resolution"></a><span data-ttu-id="0468b-113">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="0468b-113">Resolution</span></span>

<span data-ttu-id="0468b-114">Controllare i relativi ordini cliente o ordini di trasferimento per il carico o la spedizione.</span><span class="sxs-lookup"><span data-stu-id="0468b-114">Check the related sales orders or transfer orders for the load or shipment.</span></span> <span data-ttu-id="0468b-115">Assicurati che tutto il lavoro correlato sia stato completato nell'ubicazione di spedizione finale e che le quantità corrispondano.</span><span class="sxs-lookup"><span data-stu-id="0468b-115">Make sure that all the related work has been completed at the final shipping location, and that the quantities match.</span></span>

1. <span data-ttu-id="0468b-116">Passare a **Gestione magazzino \> Carichi \> Tutti i carichi**.</span><span class="sxs-lookup"><span data-stu-id="0468b-116">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="0468b-117">Seleziona il carico per cui la spedizione non può essere confermata.</span><span class="sxs-lookup"><span data-stu-id="0468b-117">Select the load that the shipment can't be confirmed for.</span></span>
1. <span data-ttu-id="0468b-118">Nella scheda dettaglio **Righe di carico** seleziona la riga di carico.</span><span class="sxs-lookup"><span data-stu-id="0468b-118">On the **Load lines** FastTab, select the load line.</span></span>
1. <span data-ttu-id="0468b-119">Prendi nota del valore del campo **Quantità di lavoro creata**.</span><span class="sxs-lookup"><span data-stu-id="0468b-119">Make a note of the value of the **Work created quantity** field.</span></span>
1. <span data-ttu-id="0468b-120">Nella scheda **Carichi** del riquadro azioni, nel gruppo **Informazioni correlate**, selezionare **Lavoro**.</span><span class="sxs-lookup"><span data-stu-id="0468b-120">On the Action Pane, on the **Loads** tab, in the **Related information** group, select **Work**.</span></span>
1. <span data-ttu-id="0468b-121">Verificare che il lavoro sia stato completato nell'ubicazione di spedizione finale e che la quantità di lavoro prelevata corrisponda alla quantità di lavoro creata sulla riga di carico.</span><span class="sxs-lookup"><span data-stu-id="0468b-121">Verify that the work has been completed at the final shipping location, and that the picked work quantity matches the created work quantity on the load line.</span></span>
1. <span data-ttu-id="0468b-122">Ripetere questa procedura per tutte le righe di carico per assicurarsi che tutti i criteri siano soddisfatti.</span><span class="sxs-lookup"><span data-stu-id="0468b-122">Repeat this procedure for all load lines to make sure that all criteria are met.</span></span>
