---
title: Opzioni per le transazioni cespiti
description: Questo articolo descrive i metodi diversi disponibili per creare le transazioni cespiti.
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AssetTable, PurchCreateOrder
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 23061
ms.assetid: 338c495b-a4d8-461e-b85b-a83faf673730
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 2a7fa7a28437e29f390efdf566e946c6a1082370
ms.contentlocale: it-it
ms.lasthandoff: 04/13/2018

---

# <a name="fixed-asset-transaction-options"></a><span data-ttu-id="cde1b-103">Opzioni per le transazioni cespiti</span><span class="sxs-lookup"><span data-stu-id="cde1b-103">Fixed asset transaction options</span></span>

[!INCLUDE [banner](../includes/banner.md)]

<span data-ttu-id="cde1b-104">Questo articolo descrive i metodi diversi disponibili per creare le transazioni cespiti.</span><span class="sxs-lookup"><span data-stu-id="cde1b-104">This article describes the different methods available to create fixed asset transactions.</span></span>

<span data-ttu-id="cde1b-105">È possibile impostare i cespiti in modo da integrarli con la contabilità fornitori, la contabilità clienti, l'approvvigionamento e la contabilità generale.</span><span class="sxs-lookup"><span data-stu-id="cde1b-105">You can set up Fixed assets for integration with Accounts payable, Accounts receivable, Procurement and sourcing, and General ledger.</span></span> <span data-ttu-id="cde1b-106">È inoltre possibile trasferire gli articoli in Gestione articoli ai cespiti se si desidera utilizzare gli articoli internamente.</span><span class="sxs-lookup"><span data-stu-id="cde1b-106">You can also transfer items in Inventory management to Fixed assets if you want to use those items internally.</span></span>

## <a name="accounts-payable"></a><span data-ttu-id="cde1b-107">Contabilità fornitori</span><span class="sxs-lookup"><span data-stu-id="cde1b-107">Accounts payable</span></span>
<span data-ttu-id="cde1b-108">È possibile immettere le transazioni cespiti nella pagina Giustificativo giornale di registrazione.</span><span class="sxs-lookup"><span data-stu-id="cde1b-108">You can enter Fixed assets transactions in the Journal voucher page.</span></span> <span data-ttu-id="cde1b-109">È possibile aprire questa pagina dalla pagina Giornale di registrazione fatture.</span><span class="sxs-lookup"><span data-stu-id="cde1b-109">This page can be opened from the Invoice journal page.</span></span> <span data-ttu-id="cde1b-110">È inoltre possibile aprire la pagina Giornale di registrazione fatture dalla pagina Giornale di approvazione fatture.</span><span class="sxs-lookup"><span data-stu-id="cde1b-110">You can also open the Journal voucher page from the Invoice approval journal page.</span></span> <span data-ttu-id="cde1b-111">Nel campo Tipo di conto di contropartita selezionare Cespiti.</span><span class="sxs-lookup"><span data-stu-id="cde1b-111">In the Offset account type field, select Fixed assets.</span></span> <span data-ttu-id="cde1b-112">Quindi, nel campo Conto di contropartita selezionare un numero cespiti.</span><span class="sxs-lookup"><span data-stu-id="cde1b-112">Then, in the Offset account field, select a fixed asset number.</span></span> <span data-ttu-id="cde1b-113">Nella scheda Cespiti immettere i valori nei campi Tipo di transazione e Libro.</span><span class="sxs-lookup"><span data-stu-id="cde1b-113">On the Fixed assets tab, enter values in the Transaction type and Book fields.</span></span>

## <a name="accounts-receivable"></a><span data-ttu-id="cde1b-114">Contabilità clienti</span><span class="sxs-lookup"><span data-stu-id="cde1b-114">Accounts receivable</span></span>
<span data-ttu-id="cde1b-115">È possibile immettere le transazioni cespiti nella pagina Fattura a testo libero.</span><span class="sxs-lookup"><span data-stu-id="cde1b-115">You can enter Fixed assets transactions in the Free text invoice page.</span></span>  <span data-ttu-id="cde1b-116">Nella pagina Fattura a testo libero, nella griglia Righe fattura, selezionare una voce.</span><span class="sxs-lookup"><span data-stu-id="cde1b-116">In the Free text invoice page, in the Invoice lines grid, select a line item.</span></span> <span data-ttu-id="cde1b-117">Fare clic sulla scheda dettaglio Dettagli riga.</span><span class="sxs-lookup"><span data-stu-id="cde1b-117">Click the Line details FastTab.</span></span> <span data-ttu-id="cde1b-118">Immettere il numero cespite e il libro per la transazione di dismissione.</span><span class="sxs-lookup"><span data-stu-id="cde1b-118">Enter the fixed asset number and book for the disposal transaction.</span></span> <span data-ttu-id="cde1b-119">Nelle fatture a testo libero il tipo di transazione cespiti è sempre Vendita di dismissione.</span><span class="sxs-lookup"><span data-stu-id="cde1b-119">For free text invoices, the fixed asset transaction type is always Disposal - sale.</span></span>

## <a name="procurement-and-sourcing"></a><span data-ttu-id="cde1b-120">Approvvigionamento</span><span class="sxs-lookup"><span data-stu-id="cde1b-120">Procurement and sourcing</span></span>
<span data-ttu-id="cde1b-121">È possibile immettere le transazioni cespiti nella pagina Ordine acquisto.</span><span class="sxs-lookup"><span data-stu-id="cde1b-121">You can enter Fixed assets transactions in the Purchase order page.</span></span> <span data-ttu-id="cde1b-122">Immettere le informazioni necessarie per creare un ordine fornitore, quindi fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="cde1b-122">Enter the required information to create a purchase order, and then click OK.</span></span> <span data-ttu-id="cde1b-123">Nella pagina Ordine fornitore, fare clic sulla Scheda dettaglio Dettagli riga.</span><span class="sxs-lookup"><span data-stu-id="cde1b-123">In the Purchase order page, click the Line details FastTab.</span></span> <span data-ttu-id="cde1b-124">Quindi, nella scheda Cespiti, immettere le informazioni sui cespiti.</span><span class="sxs-lookup"><span data-stu-id="cde1b-124">Then, on the Fixed assets tab, enter information about the fixed asset.</span></span> 

<span data-ttu-id="cde1b-125">Per registrare una transazione di acquisizione di un cespite esistente, specificare il numero cespite, il libro e il tipo di transazione.</span><span class="sxs-lookup"><span data-stu-id="cde1b-125">To post an acquisition transaction for an existing fixed asset, specify the fixed asset number, book, and transaction type.</span></span> <span data-ttu-id="cde1b-126">Il cespite non può essere registrato se una di queste informazioni manca.</span><span class="sxs-lookup"><span data-stu-id="cde1b-126">The fixed asset cannot be posted if any of this information is missing.</span></span> <span data-ttu-id="cde1b-127">Per registrare una transazione di acquisizione per un nuovo cespite, selezionare l'opzione Nuovo cespite?, quindi selezionare il gruppo di cespiti a cui assegnare il nuovo cespite.</span><span class="sxs-lookup"><span data-stu-id="cde1b-127">To post an acquisition transaction for a new fixed asset, select the New fixed asset? option, and then select the fixed asset group to assign the new asset to.</span></span> <span data-ttu-id="cde1b-128">Se tuttavia l'articolo appartiene a un gruppo di modelli inventariali in cui viene utilizzato un modello inventariale Costo standard, non sarà disponibile alcun campo relativo a cespiti per una riga.</span><span class="sxs-lookup"><span data-stu-id="cde1b-128">However, no fixed asset fields are available for a line if the item is in an inventory model group that uses a standard cost inventory model.</span></span> <span data-ttu-id="cde1b-129">Inoltre, le opzioni definite nella pagina Parametri cespiti determinano se è possibile registrare transazioni di acquisizione dai moduli di acquisto.</span><span class="sxs-lookup"><span data-stu-id="cde1b-129">Additionally, the options that are defined in the Fixed assets parameters page determine whether you can post acquisition transactions from the purchasing modules.</span></span> 

<span data-ttu-id="cde1b-130">L'utilizzo del giornale di registrazione Ordine fornitore o Scorte a cespiti per l'acquisizione dei cespiti influisce sul valore di magazzino..</span><span class="sxs-lookup"><span data-stu-id="cde1b-130">When a purchase order or the Inventory to fixed assets journal is used to acquire fixed assets, the inventory value is affected.</span></span>

## <a name="general-ledger"></a><span data-ttu-id="cde1b-131">Contabilità generale</span><span class="sxs-lookup"><span data-stu-id="cde1b-131">General ledger</span></span>
<span data-ttu-id="cde1b-132">Nella pagina Giornale di registrazione generale può essere registrato qualsiasi tipo di transazione cespiti.</span><span class="sxs-lookup"><span data-stu-id="cde1b-132">Any fixed asset transaction type can be posted in the General journal page.</span></span> <span data-ttu-id="cde1b-133">È inoltre possibile utilizzare i giornali di registrazione in Cespiti per registrare le transazioni cespiti.</span><span class="sxs-lookup"><span data-stu-id="cde1b-133">You can also use journals in Fixed assets to post fixed asset transactions.</span></span>

## <a name="options-for-entering-fixed-asset-transaction-types"></a><span data-ttu-id="cde1b-134">Opzioni per l'immissione di tipi di transazioni cespiti</span><span class="sxs-lookup"><span data-stu-id="cde1b-134">Options for entering fixed asset transaction types</span></span>


| <span data-ttu-id="cde1b-135">Tipo di transazione</span><span class="sxs-lookup"><span data-stu-id="cde1b-135">Transaction type</span></span>                    | <span data-ttu-id="cde1b-136">Modulo</span><span class="sxs-lookup"><span data-stu-id="cde1b-136">Module</span></span>                   | <span data-ttu-id="cde1b-137">Opzioni</span><span class="sxs-lookup"><span data-stu-id="cde1b-137">Options</span></span>                                   |
|-------------------------------------|--------------------------|-------------------------------------------|
| <span data-ttu-id="cde1b-138">Acquisizione, Rettifica acquisizione</span><span class="sxs-lookup"><span data-stu-id="cde1b-138">Acquisition, Acquisition adjustment</span></span> | <span data-ttu-id="cde1b-139">Cespiti</span><span class="sxs-lookup"><span data-stu-id="cde1b-139">Fixed assets</span></span>             | <span data-ttu-id="cde1b-140">Cespiti, Scorte a cespiti</span><span class="sxs-lookup"><span data-stu-id="cde1b-140">Fixed assets, Inventory to fixed assets</span></span>   |
|                                     | <span data-ttu-id="cde1b-141">Contabilità generale</span><span class="sxs-lookup"><span data-stu-id="cde1b-141">General ledger</span></span>           | <span data-ttu-id="cde1b-142">Giornale di registrazione generale</span><span class="sxs-lookup"><span data-stu-id="cde1b-142">General journal</span></span>                           |
|                                     | <span data-ttu-id="cde1b-143">Contabilità fornitori</span><span class="sxs-lookup"><span data-stu-id="cde1b-143">Accounts payable</span></span>         | <span data-ttu-id="cde1b-144">Giornale di registrazione fatture, Giornale di approvazione fatture</span><span class="sxs-lookup"><span data-stu-id="cde1b-144">Invoice journal, Invoice approval journal</span></span> |
|                                     | <span data-ttu-id="cde1b-145">Approvvigionamento</span><span class="sxs-lookup"><span data-stu-id="cde1b-145">Procurement and sourcing</span></span> | <span data-ttu-id="cde1b-146">Ordine acquisto</span><span class="sxs-lookup"><span data-stu-id="cde1b-146">Purchase order</span></span>                            |
| <span data-ttu-id="cde1b-147">Ammortamento</span><span class="sxs-lookup"><span data-stu-id="cde1b-147">Depreciation</span></span>                        | <span data-ttu-id="cde1b-148">Cespiti</span><span class="sxs-lookup"><span data-stu-id="cde1b-148">Fixed assets</span></span>             | <span data-ttu-id="cde1b-149">Cespiti</span><span class="sxs-lookup"><span data-stu-id="cde1b-149">Fixed assets</span></span>                              |
|                                     | <span data-ttu-id="cde1b-150">Contabilità generale</span><span class="sxs-lookup"><span data-stu-id="cde1b-150">General ledger</span></span>           | <span data-ttu-id="cde1b-151">Giornale di registrazione generale</span><span class="sxs-lookup"><span data-stu-id="cde1b-151">General journal</span></span>                           |
| <span data-ttu-id="cde1b-152">Gestione dismissione</span><span class="sxs-lookup"><span data-stu-id="cde1b-152">Disposal</span></span>                            | <span data-ttu-id="cde1b-153">Cespiti</span><span class="sxs-lookup"><span data-stu-id="cde1b-153">Fixed assets</span></span>             | <span data-ttu-id="cde1b-154">Cespiti</span><span class="sxs-lookup"><span data-stu-id="cde1b-154">Fixed assets</span></span>                              |
| <span data-ttu-id="cde1b-155">** **</span><span class="sxs-lookup"><span data-stu-id="cde1b-155">** **</span></span>                               | <span data-ttu-id="cde1b-156">Contabilità generale</span><span class="sxs-lookup"><span data-stu-id="cde1b-156">General ledger</span></span>           | <span data-ttu-id="cde1b-157">Giornale di registrazione generale</span><span class="sxs-lookup"><span data-stu-id="cde1b-157">General journal</span></span>                           |
| <span data-ttu-id="cde1b-158">** **</span><span class="sxs-lookup"><span data-stu-id="cde1b-158">** **</span></span>                               | <span data-ttu-id="cde1b-159">Contabilità clienti</span><span class="sxs-lookup"><span data-stu-id="cde1b-159">Accounts receivable</span></span>      | <span data-ttu-id="cde1b-160">Fattura a testo libero</span><span class="sxs-lookup"><span data-stu-id="cde1b-160">Free text invoice</span></span>                         |



<span data-ttu-id="cde1b-161">Per ulteriori informazioni, vedere [Integrazione dei cespiti](fixed-asset-integration.md).</span><span class="sxs-lookup"><span data-stu-id="cde1b-161">For more information, see [Fixed assets integration](fixed-asset-integration.md).</span></span>




