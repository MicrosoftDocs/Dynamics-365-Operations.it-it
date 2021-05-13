---
title: Non è possibile confermare una spedizione perché la quantità è pari a zero
description: Non è possibile confermare una spedizione perché la quantità è pari a zero
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
ms.openlocfilehash: 7a06f0651db741a867e1e9fe7dbab841a928c22b
ms.sourcegitcommit: cd9016e9787169cb800889d335b9c5919ddbe4af
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2021
ms.locfileid: "5938496"
---
# <a name="you-cant-confirm-a-shipment-because-there-is-zero-quantity"></a><span data-ttu-id="7ea7c-103">Non è possibile confermare una spedizione perché la quantità è pari a zero</span><span class="sxs-lookup"><span data-stu-id="7ea7c-103">You can't confirm a shipment because there is zero quantity</span></span>

<span data-ttu-id="7ea7c-104">Codice di errore: LoadLineWarningUpdatedToZero</span><span class="sxs-lookup"><span data-stu-id="7ea7c-104">Error code: LoadLineWarningUpdatedToZero</span></span>

## <a name="symptoms"></a><span data-ttu-id="7ea7c-105">Sintomi</span><span class="sxs-lookup"><span data-stu-id="7ea7c-105">Symptoms</span></span>

<span data-ttu-id="7ea7c-106">Quando si tenta di confermare una spedizione, il sistema mostra il seguente messaggio di errore:</span><span class="sxs-lookup"><span data-stu-id="7ea7c-106">When you try to confirm a shipment, the system shows the following error message:</span></span>

> <span data-ttu-id="7ea7c-107">La riga di carico per l'articolo %1 e la spedizione %2 è stata aggiornata in modo da avere una quantità pari a zero a causa dell'impostazione del limite minimo di fornitura che consente di non spedire quantità per questo articolo.</span><span class="sxs-lookup"><span data-stu-id="7ea7c-107">Load line for item %1 and shipment %2 has been updated to have zero quantity due to underdelivery setup allowing not to ship any quantities for this item.</span></span>

<span data-ttu-id="7ea7c-108">Pertanto, non è possibile confermare la spedizione per il carico.</span><span class="sxs-lookup"><span data-stu-id="7ea7c-108">Therefore, you can't confirm the shipment for the load.</span></span>

## <a name="cause"></a><span data-ttu-id="7ea7c-109">Causa</span><span class="sxs-lookup"><span data-stu-id="7ea7c-109">Cause</span></span>

<span data-ttu-id="7ea7c-110">Il sistema valuta se la quantità prelevata rientra nei limiti previsti, in base alla quantità prelevata, alla quantità della riga di carico e alla percentuale di limite minimo di fornitura.</span><span class="sxs-lookup"><span data-stu-id="7ea7c-110">The system evaluates whether the picked quantity is within the expected limits, based on the picked quantity, load line quantity, and underdelivery percentage.</span></span> <span data-ttu-id="7ea7c-111">Se il sistema rileva che la quantità prelevata nella riga di carico è 0 (zero), non è possibile confermare la spedizione.</span><span class="sxs-lookup"><span data-stu-id="7ea7c-111">If the system finds that the picked quantity on the load line is 0 (zero), you can't confirm the shipment.</span></span> <span data-ttu-id="7ea7c-112">Ad esempio, questo problema potrebbe verificarsi se il lavoro è stato annullato e la percentuale di limite minimo di fornitura sulla riga di carico è del 100%.</span><span class="sxs-lookup"><span data-stu-id="7ea7c-112">For example, this issue might occur if work has been canceled, and the underdelivery percentage on the load line is 100 percent.</span></span>

## <a name="resolution"></a><span data-ttu-id="7ea7c-113">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="7ea7c-113">Resolution</span></span>

<span data-ttu-id="7ea7c-114">Controlla le tue righe di carico per assicurarti che la percentuale e le quantità di limite minimo di fornitura siano allineate al lavoro prelevato.</span><span class="sxs-lookup"><span data-stu-id="7ea7c-114">Check your load lines to make sure that the underdelivery percentage and quantities are aligned with the picked work.</span></span>

1. <span data-ttu-id="7ea7c-115">Passare a **Gestione magazzino \> Carichi \> Tutti i carichi**.</span><span class="sxs-lookup"><span data-stu-id="7ea7c-115">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="7ea7c-116">Seleziona il carico per cui la spedizione non può essere confermata.</span><span class="sxs-lookup"><span data-stu-id="7ea7c-116">Select the load that the shipment can't be confirmed for.</span></span>
1. <span data-ttu-id="7ea7c-117">Nella scheda dettaglio **Righe di carico**, seleziona la riga di carico dell'articolo che supera la percentuale di limite minimo di fornitura.</span><span class="sxs-lookup"><span data-stu-id="7ea7c-117">On the **Load lines** FastTab, select the load line for the item that exceeds the underdelivery percentage.</span></span>
1. <span data-ttu-id="7ea7c-118">Regola il valore del campo **Limite minimo di fornitura** o il campo **Quantità** come richiesto.</span><span class="sxs-lookup"><span data-stu-id="7ea7c-118">Adjust the value of the **Underdelivery** field or the **Quantity** field as required.</span></span>

> [!TIP]
> <span data-ttu-id="7ea7c-119">Se il problema persiste, potrebbe essere necessario completare più operazioni di prelievo per gli ordini cliente o di trasferimento correlati fino a quando la quantità disponibile non è allineata al carico o alla spedizione.</span><span class="sxs-lookup"><span data-stu-id="7ea7c-119">If the issue still isn't fixed, you might have to complete more picking work for the related sales orders or transfer orders until the available quantity is aligned with the load or shipment.</span></span>
