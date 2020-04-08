---
title: Creare fatture ordine cliente
description: Questa guida attività descrive la fatturazione di un ordine cliente, inclusa l'unione delle fatture e l'elaborazione batch.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 06/25/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesTableListPage, SalesEditLines,  SysQueryForm, SysRecurrence
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c504ef36f61613c7aa7db5a1e5ddba6e69cd7285
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/18/2020
ms.locfileid: "3140274"
---
# <a name="create-sales-order-invoices"></a><span data-ttu-id="beaf1-103">Creare fatture ordine cliente</span><span class="sxs-lookup"><span data-stu-id="beaf1-103">Create sales order invoices</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="beaf1-104">Questa guida attività descrive la fatturazione di un ordine cliente, inclusa l'unione delle fatture e l'elaborazione batch.</span><span class="sxs-lookup"><span data-stu-id="beaf1-104">This task guide describes invoicing a sales order, including merging invoices and batch processing.</span></span> <span data-ttu-id="beaf1-105">Questa procedura utilizza la società dimostrativa USMF.</span><span class="sxs-lookup"><span data-stu-id="beaf1-105">This procedure uses the USMF demo company.</span></span>


## <a name="create-an-invoice-from-a-sales-order"></a><span data-ttu-id="beaf1-106">Creare una fattura da un ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="beaf1-106">Create an invoice from a sales order</span></span>
1. <span data-ttu-id="beaf1-107">Selezionare **Pannello di navigazione > Moduli > Contabilità clienti > Ordini > Ordini cliente spediti ma non fatturati**.</span><span class="sxs-lookup"><span data-stu-id="beaf1-107">Go to **Navigation pane > Modules > Accounts receivable > Orders > Shipped but not invoiced sales orders**.</span></span>
2. <span data-ttu-id="beaf1-108">Selezionare un ordine cliente nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="beaf1-108">Select a sales order in the list.</span></span> 
3. <span data-ttu-id="beaf1-109">Nel **riquadro azioni**, fare clic su **Fattura > Gnera > Fattura**.</span><span class="sxs-lookup"><span data-stu-id="beaf1-109">On the **Action Pane**, click **Invoice > Generate > Invoice**.</span></span> <span data-ttu-id="beaf1-110">Si noti che all'ordine cliente sono associati più documenti di trasporto.</span><span class="sxs-lookup"><span data-stu-id="beaf1-110">Note that this sales order has multiple packing slips associated with it.</span></span> <span data-ttu-id="beaf1-111">Verrà visualizzata solo la parola <multiple> anziché il numero del documento di trasporto.</span><span class="sxs-lookup"><span data-stu-id="beaf1-111">It will only show the word <multiple> instead of the packing slip number.</span></span>  
4. <span data-ttu-id="beaf1-112">Espandere la sezione **Parametri**.</span><span class="sxs-lookup"><span data-stu-id="beaf1-112">Expand the **Parameters** section.</span></span>
    - <span data-ttu-id="beaf1-113">La registrazione deve essere impostata su Sì per registrare la fattura.</span><span class="sxs-lookup"><span data-stu-id="beaf1-113">Posting must be set to Yes to post the invoice.</span></span> <span data-ttu-id="beaf1-114">È inoltre possibile disabilitare la registrazione e stampare solo la fattura.</span><span class="sxs-lookup"><span data-stu-id="beaf1-114">You can also turn off posting and just print the invoice.</span></span> <span data-ttu-id="beaf1-115">Tuttavia, è possibile ottenere lo stesso risultato creando una fattura proforma anziché una fattura.</span><span class="sxs-lookup"><span data-stu-id="beaf1-115">However, you can accomplish the same result by creating a proforma invoice instead of an invoice.</span></span>  
    - <span data-ttu-id="beaf1-116">Questa opzione viene utilizzata per i processi batch.</span><span class="sxs-lookup"><span data-stu-id="beaf1-116">This option is used for batch jobs.</span></span> <span data-ttu-id="beaf1-117">La query viene eseguita quando viene eseguito il processo batch.</span><span class="sxs-lookup"><span data-stu-id="beaf1-117">The query is run when the batch job is run.</span></span>
5. <span data-ttu-id="beaf1-118">Selezionare "Dopo" nel campo **Stampa**.</span><span class="sxs-lookup"><span data-stu-id="beaf1-118">In the **Print** field, select 'After'.</span></span>
6. <span data-ttu-id="beaf1-119">Selezionare **Sì** per **Stampa fattura**.</span><span class="sxs-lookup"><span data-stu-id="beaf1-119">Select **Yes** for **Print invoice**.</span></span> <span data-ttu-id="beaf1-120">Gestione stampa consente di stampare più copie della fattura, nonché di inviare la fattura tramite posta elettronica come file PDF.</span><span class="sxs-lookup"><span data-stu-id="beaf1-120">Print management can print  multiple copies of the invoice and also send the invoice via email as a PDF file.</span></span>  
7. <span data-ttu-id="beaf1-121">Selezionare "Riepiloga" nel campo **Stampa addebiti**.</span><span class="sxs-lookup"><span data-stu-id="beaf1-121">In the **Print charges** field, select 'Summarize'.</span></span>
8. <span data-ttu-id="beaf1-122">Nel campo **Verifica limite di credito**, selezionare "Saldo".</span><span class="sxs-lookup"><span data-stu-id="beaf1-122">In the **Check credit limit** field, select 'Balance'.</span></span>
9. <span data-ttu-id="beaf1-123">Fare clic su **Annulla**.</span><span class="sxs-lookup"><span data-stu-id="beaf1-123">Click **Cancel**.</span></span>

## <a name="combine-orders-into-a-single-invoice"></a><span data-ttu-id="beaf1-124">Combina gli ordini in un'unica fattura</span><span class="sxs-lookup"><span data-stu-id="beaf1-124">Combine orders into a single invoice</span></span>
1. <span data-ttu-id="beaf1-125">Passare al **pannello di navigazione >Moduli > Contabilità clienti > Ordini > Tutti gli ordini cliente**.</span><span class="sxs-lookup"><span data-stu-id="beaf1-125">Go to **Navigation pane > Modules > Accounts receivable > Orders > All sales orders**.</span></span>
2. <span data-ttu-id="beaf1-126">Individuare un cliente con più fatture aperte.</span><span class="sxs-lookup"><span data-stu-id="beaf1-126">Locate a customer that has multiple invoices open.</span></span>
3. <span data-ttu-id="beaf1-127">Selezionare molteplici ordini cliente aperti dallo stesso cliente.</span><span class="sxs-lookup"><span data-stu-id="beaf1-127">Select multiple open sales orders from the same customer.</span></span>
4. <span data-ttu-id="beaf1-128">Nel **riquadro azioni**, fare clic su **Fattura > Gnera > Fattura**.</span><span class="sxs-lookup"><span data-stu-id="beaf1-128">On the **Action Pane**, click **Invoice > Generate > Invoice**.</span></span>
5. <span data-ttu-id="beaf1-129">Espandere la sezione **Parametri**.</span><span class="sxs-lookup"><span data-stu-id="beaf1-129">Expand the **Parameters** section.</span></span>
6. <span data-ttu-id="beaf1-130">Nel campo **Quantità** selezionare "Tutto".</span><span class="sxs-lookup"><span data-stu-id="beaf1-130">In the **Quantity** field, select 'All'.</span></span> <span data-ttu-id="beaf1-131">Si noti che nella sezione relativa alla panoramica vengono elencate due fatture.</span><span class="sxs-lookup"><span data-stu-id="beaf1-131">Note that there are two invoices listed in the overview section.</span></span> <span data-ttu-id="beaf1-132">Ora uniamole in una singola fattura.</span><span class="sxs-lookup"><span data-stu-id="beaf1-132">Now let's merge them into a single invoice.</span></span>  
7. <span data-ttu-id="beaf1-133">Nel campo **Aggiorna riepilogo per**, selezionare "Conto fatture".</span><span class="sxs-lookup"><span data-stu-id="beaf1-133">In the **Summary update for** field, select 'Invoice account'.</span></span>
8. <span data-ttu-id="beaf1-134">Fare clic su **Disponi** per unire gli ordini cliente in una singola fattura.</span><span class="sxs-lookup"><span data-stu-id="beaf1-134">Click **Arrange** to merge the sales orders into a single invoice.</span></span> <span data-ttu-id="beaf1-135">I due ordini cliente sono ora uniti in una singola fattura.</span><span class="sxs-lookup"><span data-stu-id="beaf1-135">The two sales orders are now merged into a single invoice.</span></span>   
9. <span data-ttu-id="beaf1-136">Fare clic su **Annulla**.</span><span class="sxs-lookup"><span data-stu-id="beaf1-136">Click **Cancel**.</span></span>
10. <span data-ttu-id="beaf1-137">Fare clic su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="beaf1-137">Click **Yes**.</span></span>

## <a name="post-invoices-in-a-batch"></a><span data-ttu-id="beaf1-138">Registra le fatture in un batch</span><span class="sxs-lookup"><span data-stu-id="beaf1-138">Post invoices in a batch</span></span>
1. <span data-ttu-id="beaf1-139">Selezionare **Pannello di navigazione > Moduli > Contabilità clienti > Fatture > Fatturazione batch > Fattura**.</span><span class="sxs-lookup"><span data-stu-id="beaf1-139">Go to **Navigation pane > Modules > Accounts receivable > Invoices > Batch invoicing > Invoice**.</span></span>
2. <span data-ttu-id="beaf1-140">Fare clic su **Seleziona**.</span><span class="sxs-lookup"><span data-stu-id="beaf1-140">Click **Select**.</span></span>
3. <span data-ttu-id="beaf1-141">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="beaf1-141">Click **OK**.</span></span>
4. <span data-ttu-id="beaf1-142">Fare clic su **Batch**.</span><span class="sxs-lookup"><span data-stu-id="beaf1-142">Click **Batch**.</span></span>
5. <span data-ttu-id="beaf1-143">Selezionare **Sì** in **Elaborazione batch**.</span><span class="sxs-lookup"><span data-stu-id="beaf1-143">Select **Yes** in **Batch processing**.</span></span>
6. <span data-ttu-id="beaf1-144">Fare clic su **Ricorrenza**.</span><span class="sxs-lookup"><span data-stu-id="beaf1-144">Click **Recurrence**.</span></span>
7. <span data-ttu-id="beaf1-145">Selezionare **Giorni**.</span><span class="sxs-lookup"><span data-stu-id="beaf1-145">Select **Days**.</span></span>
8. <span data-ttu-id="beaf1-146">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="beaf1-146">Click **OK**.</span></span>
9. <span data-ttu-id="beaf1-147">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="beaf1-147">Click **OK**.</span></span>
10. <span data-ttu-id="beaf1-148">Fare clic su **Annulla**.</span><span class="sxs-lookup"><span data-stu-id="beaf1-148">Click **Cancel**.</span></span>
11. <span data-ttu-id="beaf1-149">Fare clic su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="beaf1-149">Click **Yes**.</span></span>

