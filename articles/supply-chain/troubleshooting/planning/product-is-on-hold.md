---
title: Il prodotto è in attesa per le transazioni
description: Dopo aver pianificato gli ordini, viene visualizzato un messaggio di errore che indica che un articolo è in sospeso per le transazioni.
author: ankubik
ms.date: 06/10/2021
ms.topic: troubleshooting
ms.search.form: ReqTransPo
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ankubik
ms.search.validFrom: 2021-06-10
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 6654e6437a088218db116b955631be4c7e62de5f
ms.sourcegitcommit: f9b145ef4a81cec81f420871b4130b05db4f4500
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2021
ms.locfileid: "6301281"
---
# <a name="product-is-on-hold-for-transactions"></a><span data-ttu-id="d331d-103">Il prodotto è in attesa per le transazioni</span><span class="sxs-lookup"><span data-stu-id="d331d-103">Product is on hold for transactions</span></span>

<span data-ttu-id="d331d-104">Codice errore: SYS13295</span><span class="sxs-lookup"><span data-stu-id="d331d-104">Error code: SYS13295</span></span>

## <a name="symptoms"></a><span data-ttu-id="d331d-105">Sintomi</span><span class="sxs-lookup"><span data-stu-id="d331d-105">Symptoms</span></span>

<span data-ttu-id="d331d-106">Dopo aver stabilizzato gli ordini pianificati, viene visualizzato il seguente messaggio di errore:</span><span class="sxs-lookup"><span data-stu-id="d331d-106">After you firm planned orders, you receive the following error message:</span></span>

> <span data-ttu-id="d331d-107">L'articolo %1 è in attesa per le transazioni in %2.</span><span class="sxs-lookup"><span data-stu-id="d331d-107">Item %1 is on hold for transactions in %2.</span></span>

## <a name="cause"></a><span data-ttu-id="d331d-108">Causa</span><span class="sxs-lookup"><span data-stu-id="d331d-108">Cause</span></span>

<span data-ttu-id="d331d-109">Quando si descrivono gli articoli bloccati, il sistema utilizza i termini *bloccato*, *interrotto*, e *in attesa* in modo intercambiabile.</span><span class="sxs-lookup"><span data-stu-id="d331d-109">When describing blocked items, system uses the terms *blocked*, *stopped*, and *on hold* interchangeably.</span></span> <span data-ttu-id="d331d-110">Questo errore significa che l'articolo è impostato come **Interrotto** nelle impostazioni di ordine predefinite.</span><span class="sxs-lookup"><span data-stu-id="d331d-110">This error means that the item is set as **Stopped** in its default order settings.</span></span>

<span data-ttu-id="d331d-111">Se un articolo è bloccato e lo si aggiunge a una riga di un ordine fornitore o di un ordine cliente, viene visualizzato un messaggio di avviso.</span><span class="sxs-lookup"><span data-stu-id="d331d-111">If an item is blocked, and you add it to a purchase order or sales order line, you receive a warning message.</span></span> <span data-ttu-id="d331d-112">Quando un articolo è bloccato, le transazioni di magazzino correlate alla riga dell'ordine fornitore o cliente non possono essere modificate, ad esempio durante la registrazione di un documento di trasporto o una fattura.</span><span class="sxs-lookup"><span data-stu-id="d331d-112">When an item is blocked, inventory transactions that are related to the purchase order or sales order line can't be modified (for example, when you post a packing slip or an invoice).</span></span> <span data-ttu-id="d331d-113">È possibile bloccare un articolo acquistato e contemporaneamente vendere l'articolo.</span><span class="sxs-lookup"><span data-stu-id="d331d-113">You can block a purchased item, and, at the same time, sell the item.</span></span> <span data-ttu-id="d331d-114">In tal caso, il campo **Interrotto** è selezionato nell'ordine fornitore, ma l'articolo non è bloccato nel magazzino o in un ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="d331d-114">In this case, the **Stopped** check box is selected on a purchase order, but the item isn't blocked in inventory or on a sales order.</span></span>

<span data-ttu-id="d331d-115">Ecco alcune delle condizioni che possono impedire la vendita di un numero di articolo:</span><span class="sxs-lookup"><span data-stu-id="d331d-115">Here are some of the conditions that can cause an item number to be blocked from being sold:</span></span>

- <span data-ttu-id="d331d-116">L'articolo è ancora in fase di sviluppo o produzione.</span><span class="sxs-lookup"><span data-stu-id="d331d-116">The item is still under development or manufacture.</span></span> <span data-ttu-id="d331d-117">Pertanto, non vuoi che venga venduto o prenotato.</span><span class="sxs-lookup"><span data-stu-id="d331d-117">Therefore, you don't want it to be sold or reserved.</span></span>
- <span data-ttu-id="d331d-118">Hai ricevuto molti articoli difettosi e i difetti devono essere corretti prima che l'articolo possa essere venduto.</span><span class="sxs-lookup"><span data-stu-id="d331d-118">You've received many defective items, and the defects must be corrected before the item can be sold.</span></span>

<span data-ttu-id="d331d-119">In casi di questo tipo, è possibile bloccare l'articolo finché il problema non viene risolto.</span><span class="sxs-lookup"><span data-stu-id="d331d-119">In cases of this type, you can block the item until the issue is resolved.</span></span>

<span data-ttu-id="d331d-120">Se un articolo è bloccato e si crea una riga di ordine di reso, viene visualizzato un messaggio.</span><span class="sxs-lookup"><span data-stu-id="d331d-120">If an item is blocked, and you create a return order line, you receive a message.</span></span> <span data-ttu-id="d331d-121">Non è possibile bloccare una serie o un lotto di un articolo.</span><span class="sxs-lookup"><span data-stu-id="d331d-121">You can't block a series or a lot of an item.</span></span> <span data-ttu-id="d331d-122">Se è necessario bloccare parti di un articolo, è possibile spostare le scorte o bloccare le scorte totali dell'articolo per il periodo.</span><span class="sxs-lookup"><span data-stu-id="d331d-122">If parts of an item must be blocked, you can block them by moving inventory or by blocking the full stock of the item for that period.</span></span>

## <a name="resolution"></a><span data-ttu-id="d331d-123">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="d331d-123">Resolution</span></span>

- <span data-ttu-id="d331d-124">Apri la pagina **Impostazioni ordine predefinite** per l'articolo e deseleziona la casella di controllo **Interrotto**.</span><span class="sxs-lookup"><span data-stu-id="d331d-124">Open the **Default order settings** page for the item, and clear the **Stopped** checkbox.</span></span>
