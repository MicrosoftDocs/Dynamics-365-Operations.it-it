--- 
title: Creare fatture ordine cliente
description: "Questa guida attività descrive la fatturazione di un ordine cliente, inclusa l'unione delle fatture e l'elaborazione batch."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: 7b5c7419e1f8a775ce4b5b9ba46f582c9be23ad0
ms.contentlocale: it-it
ms.lasthandoff: 08/07/2018

---
# <a name="create-sales-order-invoices"></a><span data-ttu-id="8183d-103">Creare fatture ordine cliente</span><span class="sxs-lookup"><span data-stu-id="8183d-103">Create sales order invoices</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="8183d-104">Questa guida attività descrive la fatturazione di un ordine cliente, inclusa l'unione delle fatture e l'elaborazione batch.</span><span class="sxs-lookup"><span data-stu-id="8183d-104">This task guide describes invoicing a sales order, including merging invoices and batch processing.</span></span> <span data-ttu-id="8183d-105">Questa procedura utilizza la società dimostrativa USMF.</span><span class="sxs-lookup"><span data-stu-id="8183d-105">This procedure uses the USMF demo company.</span></span>


## <a name="create-an-invoice-from-a-sales-order"></a><span data-ttu-id="8183d-106">Creare una fattura da un ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="8183d-106">Create an invoice from a sales order</span></span>
1. <span data-ttu-id="8183d-107">Fare clic su Contabilità clienti > Ordini > Ordini cliente spediti ma non fatturati.</span><span class="sxs-lookup"><span data-stu-id="8183d-107">Go to Accounts receivable > Orders > Shipped but not invoiced sales orders.</span></span>
2. <span data-ttu-id="8183d-108">Selezionare un ordine cliente nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="8183d-108">Select a sales order in the list.</span></span> 
3. <span data-ttu-id="8183d-109">Nel riquadro azioni fare clic su Fattura.</span><span class="sxs-lookup"><span data-stu-id="8183d-109">On the Action Pane, click Invoice.</span></span>
4. <span data-ttu-id="8183d-110">Fare clic su Fattura.</span><span class="sxs-lookup"><span data-stu-id="8183d-110">Click Invoice.</span></span>
    * <span data-ttu-id="8183d-111">Si noti che all'ordine cliente sono associati più documenti di trasporto.</span><span class="sxs-lookup"><span data-stu-id="8183d-111">Note that this sales order has multiple packing slips associated with it.</span></span> <span data-ttu-id="8183d-112">Verrà visualizzata solo la parola <multiple> anziché il numero del documento di trasporto.</span><span class="sxs-lookup"><span data-stu-id="8183d-112">It will only show the word <multiple> instead of the packing slip number.</span></span>  
5. <span data-ttu-id="8183d-113">Espandere la sezione Parametri.</span><span class="sxs-lookup"><span data-stu-id="8183d-113">Expand the Parameters section.</span></span>
    * <span data-ttu-id="8183d-114">La registrazione deve essere impostata su Sì per registrare la fattura.</span><span class="sxs-lookup"><span data-stu-id="8183d-114">Posting must be set to Yes to post the invoice.</span></span> <span data-ttu-id="8183d-115">È inoltre possibile disabilitare la registrazione e stampare solo la fattura.</span><span class="sxs-lookup"><span data-stu-id="8183d-115">You can also turn off posting and just print the invoice.</span></span> <span data-ttu-id="8183d-116">Tuttavia, è possibile ottenere lo stesso risultato creando una fattura proforma anziché una fattura.</span><span class="sxs-lookup"><span data-stu-id="8183d-116">However, you can accomplish the same result by creating a proforma invoice instead of an invoice.</span></span>  
    * <span data-ttu-id="8183d-117">Questa opzione viene utilizzata per i processi batch.</span><span class="sxs-lookup"><span data-stu-id="8183d-117">This option is used for batch jobs.</span></span> <span data-ttu-id="8183d-118">La query viene eseguita quando viene eseguito il processo batch.</span><span class="sxs-lookup"><span data-stu-id="8183d-118">The query is run when the batch job is run.</span></span>    
6. <span data-ttu-id="8183d-119">Selezionare "Dopo" nel campo Stampa.</span><span class="sxs-lookup"><span data-stu-id="8183d-119">In the Print field, select 'After'.</span></span>
7. <span data-ttu-id="8183d-120">Selezionare Sì per Stampa fattura.</span><span class="sxs-lookup"><span data-stu-id="8183d-120">Select Yes for Print invoice.</span></span>
    * <span data-ttu-id="8183d-121">Gestione stampa consente di stampare più copie della fattura, nonché di inviare la fattura tramite posta elettronica come file PDF.</span><span class="sxs-lookup"><span data-stu-id="8183d-121">Print management can print  multiple copies of the invoice and also send the invoice via email as a PDF file.</span></span>  
8. <span data-ttu-id="8183d-122">Selezionare "Riepiloga" nel campo Stampa addebiti.</span><span class="sxs-lookup"><span data-stu-id="8183d-122">In the Print charges field, select 'Summarize'.</span></span>
9. <span data-ttu-id="8183d-123">Nel campo Verifica limite di credito, selezionare "saldo".</span><span class="sxs-lookup"><span data-stu-id="8183d-123">In the Check credit limit field, select 'Balance'.</span></span>
10. <span data-ttu-id="8183d-124">Scegliere Annulla.</span><span class="sxs-lookup"><span data-stu-id="8183d-124">Click Cancel.</span></span>

## <a name="combine-orders-into-a-single-invoice"></a><span data-ttu-id="8183d-125">Combina gli ordini in un'unica fattura</span><span class="sxs-lookup"><span data-stu-id="8183d-125">Combine orders into a single invoice</span></span>
1. <span data-ttu-id="8183d-126">Andare a Contabilità clienti > Ordini > Tutti gli ordini cliente.</span><span class="sxs-lookup"><span data-stu-id="8183d-126">Go to Accounts receivable > Orders > All sales orders.</span></span>
2. <span data-ttu-id="8183d-127">Individuare un cliente con più fatture aperte.</span><span class="sxs-lookup"><span data-stu-id="8183d-127">Locate a customer that has multiple invoices open.</span></span>
3. <span data-ttu-id="8183d-128">Selezionare un ordine cliente aperto.</span><span class="sxs-lookup"><span data-stu-id="8183d-128">Select an open sales order.</span></span>
4. <span data-ttu-id="8183d-129">Selezionare un altro ordine cliente aperto per lo stesso cliente.</span><span class="sxs-lookup"><span data-stu-id="8183d-129">Select another open sales order for the same customer.</span></span>
5. <span data-ttu-id="8183d-130">Nel riquadro azioni fare clic su Fattura.</span><span class="sxs-lookup"><span data-stu-id="8183d-130">On the Action Pane, click Invoice.</span></span>
6. <span data-ttu-id="8183d-131">Fare clic su Fattura.</span><span class="sxs-lookup"><span data-stu-id="8183d-131">Click Invoice.</span></span>
7. <span data-ttu-id="8183d-132">Espandere la sezione Parametri.</span><span class="sxs-lookup"><span data-stu-id="8183d-132">Expand the Parameters section.</span></span>
8. <span data-ttu-id="8183d-133">Nel campo Quantità selezionare "Tutto".</span><span class="sxs-lookup"><span data-stu-id="8183d-133">In the Quantity field, select 'All'.</span></span>
    * <span data-ttu-id="8183d-134">Si noti che nella sezione relativa alla panoramica vengono elencate due fatture.</span><span class="sxs-lookup"><span data-stu-id="8183d-134">Note that there are two invoices listed in the overview section.</span></span> <span data-ttu-id="8183d-135">Ora uniamole in una singola fattura.</span><span class="sxs-lookup"><span data-stu-id="8183d-135">Now let's merge them into a single invoice.</span></span>  
9. <span data-ttu-id="8183d-136">Nell'aggiornamento riepilogativo del campo, selezionare "Conto fatture".</span><span class="sxs-lookup"><span data-stu-id="8183d-136">In the Summary update for field, select 'Invoice account'.</span></span>
10. <span data-ttu-id="8183d-137">Fare clic su Disponi per unire gli ordini cliente in una singola fattura.</span><span class="sxs-lookup"><span data-stu-id="8183d-137">Click Arrange to merge the sales orders into a single invoice.</span></span>
    * <span data-ttu-id="8183d-138">I due ordini cliente sono ora uniti in una singola fattura.</span><span class="sxs-lookup"><span data-stu-id="8183d-138">The two sales orders are now merged into a single invoice.</span></span>   
11. <span data-ttu-id="8183d-139">Scegliere Annulla.</span><span class="sxs-lookup"><span data-stu-id="8183d-139">Click Cancel.</span></span>
12. <span data-ttu-id="8183d-140">Fare clic su Sì.</span><span class="sxs-lookup"><span data-stu-id="8183d-140">Click Yes.</span></span>

## <a name="post-invoices-in-a-batch"></a><span data-ttu-id="8183d-141">Registra le fatture in un batch</span><span class="sxs-lookup"><span data-stu-id="8183d-141">Post invoices in a batch</span></span>
1. <span data-ttu-id="8183d-142">Fare clic su Contabilità clienti > Fatture > Fatturazione batch > Fattura.</span><span class="sxs-lookup"><span data-stu-id="8183d-142">Go to Accounts receivable > Invoices > Batch invoicing > Invoice.</span></span>
2. <span data-ttu-id="8183d-143">Fare clic su Seleziona.</span><span class="sxs-lookup"><span data-stu-id="8183d-143">Click Select.</span></span>
3. <span data-ttu-id="8183d-144">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="8183d-144">Click OK.</span></span>
4. <span data-ttu-id="8183d-145">Fare clic su Batch.</span><span class="sxs-lookup"><span data-stu-id="8183d-145">Click Batch.</span></span>
5. <span data-ttu-id="8183d-146">Fare clic su Sì cui per abilitare l'elaborazione batch.</span><span class="sxs-lookup"><span data-stu-id="8183d-146">Click on Yes to turn on batch processing.</span></span>
6. <span data-ttu-id="8183d-147">Fare clic su Ricorrenza.</span><span class="sxs-lookup"><span data-stu-id="8183d-147">Click Recurrence.</span></span>
7. <span data-ttu-id="8183d-148">Selezionare Giorni</span><span class="sxs-lookup"><span data-stu-id="8183d-148">Select Days</span></span>
8. <span data-ttu-id="8183d-149">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="8183d-149">Click OK.</span></span>
9. <span data-ttu-id="8183d-150">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="8183d-150">Click OK.</span></span>
10. <span data-ttu-id="8183d-151">Scegliere Annulla.</span><span class="sxs-lookup"><span data-stu-id="8183d-151">Click Cancel.</span></span>
11. <span data-ttu-id="8183d-152">Fare clic su Sì.</span><span class="sxs-lookup"><span data-stu-id="8183d-152">Click Yes.</span></span>


