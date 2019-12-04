---
title: Sincronizzare intestazioni e righe di fatture di vendita direttamente da Supply Chain Management in Sales
description: L'argomento descrive i modelli e le attività sottostanti che vengono utilizzati per sincronizzare le righe e le intestazioni delle fatture di vendita direttamente da Dynamics 365 Supply Chain Management a Dynamics 365 Sales.
author: ChristianRytt
manager: AnnBe
ms.date: 10/26/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: crytt
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.openlocfilehash: fb5073fe8db0b51c4ea378cac57097e15e88bf83
ms.sourcegitcommit: 57bc7e17682e2edb5e1766496b7a22f4621819dd
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/18/2019
ms.locfileid: "2814054"
---
# <a name="synchronize-sales-invoice-headers-and-lines-directly-from-finance-and-operations-to-sales"></a><span data-ttu-id="19ea5-103">Sincronizzare intestazioni e righe di fatture di vendita direttamente da Finance and Operations in Sales</span><span class="sxs-lookup"><span data-stu-id="19ea5-103">Synchronize sales invoice headers and lines directly from Finance and Operations to Sales</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="19ea5-104">L'argomento descrive i modelli e le attività sottostanti che vengono utilizzati per sincronizzare le righe e le intestazioni delle fatture di vendita direttamente da Dynamics 365 Supply Chain Management a Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="19ea5-104">This topic discusses the templates and underlying tasks that are used to synchronize sales invoice headers and lines directly from Dynamics 365 Supply Chain Management to Dynamics 365 Sales.</span></span>

## <a name="data-flow-in-prospect-to-cash"></a><span data-ttu-id="19ea5-105">Flusso di dati in Prospect to cash</span><span class="sxs-lookup"><span data-stu-id="19ea5-105">Data flow in Prospect to cash</span></span>

<span data-ttu-id="19ea5-106">La soluzione Prospect to cash utilizza la funzionalità Integrazione dati per sincronizzare i dati tra istanze di Supply Chain Management e Sales.</span><span class="sxs-lookup"><span data-stu-id="19ea5-106">The Prospect to cash solution uses the Data integration feature to synchronize data across instances of Supply Chain Management and Sales.</span></span> <span data-ttu-id="19ea5-107">I modelli Prospect to cash disponibili con la funzionalità Integrazione dati consentono il flusso di dati relativo a conti, contatti, prodotti, offerte di vendita, ordini cliente e fatture di vendita tra Supply Chain Management e Sales.</span><span class="sxs-lookup"><span data-stu-id="19ea5-107">The Prospect to cash templates that are available with the Data integration feature enable the flow of data about accounts, contacts, products, sales quotations, sales orders, and sales invoices between Supply Chain Management and Sales.</span></span> <span data-ttu-id="19ea5-108">La figura seguente mostra il modo in cui i dati vengono sincronizzati tra Supply Chain Management e Sales.</span><span class="sxs-lookup"><span data-stu-id="19ea5-108">The following illustration shows how the data is synchronized between Supply Chain Management and Sales.</span></span>

<span data-ttu-id="19ea5-109">[![Flusso di dati in Prospect to cash](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)</span><span class="sxs-lookup"><span data-stu-id="19ea5-109">[![Data flow in Prospect to cash](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="19ea5-110">Modelli e attività</span><span class="sxs-lookup"><span data-stu-id="19ea5-110">Templates and tasks</span></span>

<span data-ttu-id="19ea5-111">Per accedere ai modelli disponibili, aprire l'[Interfaccia di amministrazione di Power Apps](https://preview.admin.powerapps.com/dataintegration).</span><span class="sxs-lookup"><span data-stu-id="19ea5-111">To access the available templates, open [Power Apps Admin Center](https://preview.admin.powerapps.com/dataintegration).</span></span> <span data-ttu-id="19ea5-112">Selezionare **Progetti**, quindi nell'angolo superiore destro, selezionare **Nuovo progetto** per selezionare i modelli pubblici.</span><span class="sxs-lookup"><span data-stu-id="19ea5-112">Select **Projects**, and then, in the upper-right corner, select **New project** to select public templates.</span></span>

<span data-ttu-id="19ea5-113">Il seguente modello e le attività sottostanti vengono utilizzati per sincronizzare le intestazioni e le righe delle fatture di vendita da Supply Chain Management in Sales:</span><span class="sxs-lookup"><span data-stu-id="19ea5-113">The following template and underlying tasks are used to synchronize sales invoice headers and lines from Supply Chain Management to Sales:</span></span>

- <span data-ttu-id="19ea5-114">**Nome del modello in Integrazione dati:** Fatture di vendita (da Fin and Ops in Sales) - Diretto</span><span class="sxs-lookup"><span data-stu-id="19ea5-114">**Name of the template in Data integration:** Sales Invoices (Fin and Ops to Sales) - Direct</span></span>
- <span data-ttu-id="19ea5-115">**Nomi delle attività nel progetto di Integrazione dati:**</span><span class="sxs-lookup"><span data-stu-id="19ea5-115">**Names of the tasks in the Data integration project:**</span></span>

    - <span data-ttu-id="19ea5-116">SalesInvoiceHeader</span><span class="sxs-lookup"><span data-stu-id="19ea5-116">SalesInvoiceHeader</span></span>
    - <span data-ttu-id="19ea5-117">SalesInvoiceLine</span><span class="sxs-lookup"><span data-stu-id="19ea5-117">SalesInvoiceLine</span></span>

<span data-ttu-id="19ea5-118">Le attività di sincronizzazione seguenti sono necessarie prima di eseguire la sincronizzazione delle intestazioni e delle righe di fatture di vendita:</span><span class="sxs-lookup"><span data-stu-id="19ea5-118">The following synchronization tasks are required before synchronization of sales invoice headers and lines can occur:</span></span>

- <span data-ttu-id="19ea5-119">Prodotti (da Supply Chain Management in Sales) - Diretto</span><span class="sxs-lookup"><span data-stu-id="19ea5-119">Products (Supply Chain Management to Sales) - Direct</span></span>
- <span data-ttu-id="19ea5-120">Conti (da Sales in Supply Chain Management) - Diretto (se utilizzato)</span><span class="sxs-lookup"><span data-stu-id="19ea5-120">Accounts (Sales to Supply Chain Management) - Direct (if used)</span></span>
- <span data-ttu-id="19ea5-121">Contatti (da Sales in Supply Chain Management) - Diretto (se utilizzato)</span><span class="sxs-lookup"><span data-stu-id="19ea5-121">Contacts (Sales to Supply Chain Management) - Direct (if used)</span></span>
- <span data-ttu-id="19ea5-122">Intestazione e righe ordine di vendita (da Supply Chain Management a Sales) - Diretto</span><span class="sxs-lookup"><span data-stu-id="19ea5-122">Sales order header and lines (Supply Chain Management to Sales) - Direct</span></span>

## <a name="entity-set"></a><span data-ttu-id="19ea5-123">Insieme di entità</span><span class="sxs-lookup"><span data-stu-id="19ea5-123">Entity set</span></span>

| <span data-ttu-id="19ea5-124">Gestione della supply chain</span><span class="sxs-lookup"><span data-stu-id="19ea5-124">Supply Chain Management</span></span>                              | <span data-ttu-id="19ea5-125">Vendite</span><span class="sxs-lookup"><span data-stu-id="19ea5-125">Sales</span></span>          |
|------------------------------------------------------|----------------|
| <span data-ttu-id="19ea5-126">Intestazioni fatture di vendita cliente gestite esternamente</span><span class="sxs-lookup"><span data-stu-id="19ea5-126">Externally maintained customer sales invoice headers</span></span> | <span data-ttu-id="19ea5-127">Fatture</span><span class="sxs-lookup"><span data-stu-id="19ea5-127">Invoices</span></span>       |
| <span data-ttu-id="19ea5-128">Righe fatture di vendita cliente gestite esternamente</span><span class="sxs-lookup"><span data-stu-id="19ea5-128">Externally maintained customer sales invoice lines</span></span>   | <span data-ttu-id="19ea5-129">InvoiceDetails</span><span class="sxs-lookup"><span data-stu-id="19ea5-129">InvoiceDetails</span></span> |

## <a name="entity-flow"></a><span data-ttu-id="19ea5-130">Flusso di entità</span><span class="sxs-lookup"><span data-stu-id="19ea5-130">Entity flow</span></span>

<span data-ttu-id="19ea5-131">Le fatture di vendita vengono create in Supply Chain Management e sincronizzate in Sales.</span><span class="sxs-lookup"><span data-stu-id="19ea5-131">Sales invoices are created in Supply Chain Management and synchronized to Sales.</span></span>

> [!NOTE]
> <span data-ttu-id="19ea5-132">L'imposta relativa alle spese nell'intestazione della fattura di vendita non è attualmente inclusa nella sincronizzazione da Supply Chain Management in Sales.</span><span class="sxs-lookup"><span data-stu-id="19ea5-132">Currently, tax that is related to charges on the sales invoice header isn't included in the synchronization from Supply Chain Managements to Sales.</span></span> <span data-ttu-id="19ea5-133">Sales non supporta le informazioni fiscali a livello di intestazione.</span><span class="sxs-lookup"><span data-stu-id="19ea5-133">Sales doesn't support tax information at the header level.</span></span> <span data-ttu-id="19ea5-134">Tuttavia, l'imposta relativa alle spese a livello di riga è inclusa nella sincronizzazione.</span><span class="sxs-lookup"><span data-stu-id="19ea5-134">However, tax that is related to charges at the line level is included in the synchronization.</span></span>

## <a name="prospect-to-cash-solution-for-sales"></a><span data-ttu-id="19ea5-135">Soluzione Prospect to cash per Sales</span><span class="sxs-lookup"><span data-stu-id="19ea5-135">Prospect to cash solution for Sales</span></span>

- <span data-ttu-id="19ea5-136">Un campo **Numero fattura** è stato aggiunto all'entità **Fattura** ed è visualizzato nella pagina.</span><span class="sxs-lookup"><span data-stu-id="19ea5-136">An **Invoice number** field has been added to the **Invoice** entity and appears on the page.</span></span>
- <span data-ttu-id="19ea5-137">Il pulsante **Crea fattura** nella pagina **Ordine cliente** è nascosto perché le fatture verranno create in Supply Chain Management e sincronizzate in Sales.</span><span class="sxs-lookup"><span data-stu-id="19ea5-137">The **Create invoice** button on the **Sales order** page is hidden, because invoices will be created in Supply Chain Management and synchronized to Sales.</span></span> <span data-ttu-id="19ea5-138">La pagina **Fattura** non è modificabile poiché le fatture verranno sincronizzate da Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="19ea5-138">The **Invoice** page can't be edited, because invoices will be synchronized from Supply Chain Management.</span></span>
- <span data-ttu-id="19ea5-139">Il valore **Stato dell'ordine cliente** diventa automaticamente **Fatturato** dopo la sincronizzazione della fattura correlata da Supply Chain Management in Sales.</span><span class="sxs-lookup"><span data-stu-id="19ea5-139">The **Sales order status** value is automatically changed to **Invoiced** when the related invoice from Supply Chain Management has been synchronized to Sales.</span></span> <span data-ttu-id="19ea5-140">Inoltre, il proprietario dell'ordine cliente da cui la fattura è stata creata viene assegnato come proprietario della fattura.</span><span class="sxs-lookup"><span data-stu-id="19ea5-140">Additionally, the owner of the sales order that the invoice was created from is assigned as the owner of the invoice.</span></span> <span data-ttu-id="19ea5-141">Di conseguenza, il proprietario dell'ordine cliente può visualizzare la fattura.</span><span class="sxs-lookup"><span data-stu-id="19ea5-141">Therefore, the owner of the sales order can view the invoice.</span></span>

## <a name="preconditions-and-mapping-setup"></a><span data-ttu-id="19ea5-142">Prerequisiti e impostazioni di mapping</span><span class="sxs-lookup"><span data-stu-id="19ea5-142">Preconditions and mapping setup</span></span>

<span data-ttu-id="19ea5-143">Prima di sincronizzare le fatture di vendita, è importante aggiornare le seguenti impostazioni nei sistemi:</span><span class="sxs-lookup"><span data-stu-id="19ea5-143">Before you synchronize sales invoices, it's important that you update the following settings in the systems.</span></span>

### <a name="setup-in-sales"></a><span data-ttu-id="19ea5-144">Impostazione in Sales</span><span class="sxs-lookup"><span data-stu-id="19ea5-144">Setup in Sales</span></span>

<span data-ttu-id="19ea5-145">Andare a **Impostazioni** > **Amministrazione** > **Impostazioni di sistema** > **Vendite** e assicurarsi che:</span><span class="sxs-lookup"><span data-stu-id="19ea5-145">Go to **Settings** > **Administration** > **System settings** > **Sales**, and make sure that the following settings are used:</span></span>

- <span data-ttu-id="19ea5-146">L'opzione **Usa sistema di calcolo prezzi sistema** sia impostata su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="19ea5-146">The **Use system prizing calculation system** option is set to **Yes**.</span></span>
- <span data-ttu-id="19ea5-147">Il campo **Metodo di calcolo sconto** sia impostato su **Voce**.</span><span class="sxs-lookup"><span data-stu-id="19ea5-147">The **Discount calculation method** field is set to **Line item**.</span></span>

### <a name="setup-in-the-data-integration-project"></a><span data-ttu-id="19ea5-148">Impostazione nel progetto di Integrazione dati</span><span class="sxs-lookup"><span data-stu-id="19ea5-148">Setup in the Data integration project</span></span>

#### <a name="salesinvoiceheader-task"></a><span data-ttu-id="19ea5-149">Attività SalesInvoiceHeader</span><span class="sxs-lookup"><span data-stu-id="19ea5-149">SalesInvoiceHeader task</span></span>

- <span data-ttu-id="19ea5-150">Assicurarsi che il mapping richiesto esista per **InvoiceCountryRegionId** a **BillingAddress\_Country**.</span><span class="sxs-lookup"><span data-stu-id="19ea5-150">Make sure that the required mapping exists for **InvoiceCountryRegionId** to **BillingAddress\_Country**.</span></span>

    <span data-ttu-id="19ea5-151">Il valore di modello è una mappa di valori dove vari paesi sono mappati.</span><span class="sxs-lookup"><span data-stu-id="19ea5-151">The template value is a value map where several countries or regions are mapped.</span></span>

- <span data-ttu-id="19ea5-152">Un listino prezzi è necessario per creare fatture in Sales.</span><span class="sxs-lookup"><span data-stu-id="19ea5-152">A price list is required in order to create invoices in Sales.</span></span> <span data-ttu-id="19ea5-153">Aggiornare la mappa di valori per **pricelevelid.name \[nome listino prezzi\]** al listino prezzi utilizzato in Sales per la valuta.</span><span class="sxs-lookup"><span data-stu-id="19ea5-153">Update the value map for **pricelevelid.name \[Price list name\]** to the price list that is used in Sales per currency.</span></span> <span data-ttu-id="19ea5-154">È possibile utilizzare il listino prezzi predefinito per una singola valuta.</span><span class="sxs-lookup"><span data-stu-id="19ea5-154">You can use the default price list for a single currency.</span></span> <span data-ttu-id="19ea5-155">In alternativa, se si hanno listini prezzi in più valute, è possibile utilizzare una mappa di valori.</span><span class="sxs-lookup"><span data-stu-id="19ea5-155">Alternatively, if you have price lists in multiple currencies, you can use a value map.</span></span>

    <span data-ttu-id="19ea5-156">Il valore di modello per **pricelevelid.name \[[nome listino prezzi\]** è una mappa di valori basata sulla valuta con USD = Servizio CRM USA (esempio).</span><span class="sxs-lookup"><span data-stu-id="19ea5-156">The template value for **pricelevelid.name \[Price list name\]** is a value map that is based on currency with USD = CRM Service USA (sample).</span></span>  
    
#### <a name="salesinvoiceline-task"></a><span data-ttu-id="19ea5-157">Attività SalesInvoiceLine</span><span class="sxs-lookup"><span data-stu-id="19ea5-157">SalesInvoiceLine task</span></span>

- <span data-ttu-id="19ea5-158">Assicurarsi che il mapping necessario esista per **Unità di misura**.</span><span class="sxs-lookup"><span data-stu-id="19ea5-158">Make sure that the required mapping exists for **Unit of measure**.</span></span>
- <span data-ttu-id="19ea5-159">Assicurarsi che la mappa valori richiesta esista per **SalesUnitSymbol** in Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="19ea5-159">Make sure that the required value map for **SalesUnitSymbol** in Supply Chain Management exists.</span></span>

    <span data-ttu-id="19ea5-160">Un valore di modello con una mappa di valori viene definito per **SalesUnitSymbol** a **Quantity\_UOM**.</span><span class="sxs-lookup"><span data-stu-id="19ea5-160">A template value that has a value map is defined for **SalesUnitSymbol** to **Quantity\_UOM**.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="19ea5-161">Mapping dei modelli in Integrazione dati</span><span class="sxs-lookup"><span data-stu-id="19ea5-161">Template mapping in Data integration</span></span>

> [!NOTE]
> <span data-ttu-id="19ea5-162">I campi **Termini di pagamento**, **Termini di trasporto**, **Termini di consegna**, **Metodo di spedizione** e **Modalità di consegna** non vengono inclusi nei mapping predefiniti.</span><span class="sxs-lookup"><span data-stu-id="19ea5-162">The **Payment terms**, **Freight terms**, **Delivery terms**, **Shipping method**, and **Delivery mode** fields aren't included in the default mappings.</span></span> <span data-ttu-id="19ea5-163">Per mappare questi campi, è necessario impostare un mapping di valori che sia specifico ai dati delle organizzazioni tra cui l'entità viene sincronizzata.</span><span class="sxs-lookup"><span data-stu-id="19ea5-163">To map these fields, you must set up a value mapping that is specific to the data in the organizations that the entity is synchronized between.</span></span>

<span data-ttu-id="19ea5-164">Nelle figure seguenti viene illustrato un esempio di mapping di modelli in Integrazione dati.</span><span class="sxs-lookup"><span data-stu-id="19ea5-164">The following illustrations show an example of a template mapping in Data integration.</span></span> 

> [!NOTE]
> <span data-ttu-id="19ea5-165">Il mapping mostra quali informazioni sui campi verranno sincronizzate da Sales in Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="19ea5-165">The mapping shows which field information will be synchronized from Sales to Supply Chain Management.</span></span>

### <a name="salesinvoiceheader"></a><span data-ttu-id="19ea5-166">SalesInvoiceHeader</span><span class="sxs-lookup"><span data-stu-id="19ea5-166">SalesInvoiceHeader</span></span>

![Mapping dei modelli in Integrazione dati](./media/sales-invoice-direct-template-mapping-data-integrator-1.png)

### <a name="salesinvoiceline"></a><span data-ttu-id="19ea5-168">SalesInvoiceLine</span><span class="sxs-lookup"><span data-stu-id="19ea5-168">SalesInvoiceLine</span></span>

![Mapping dei modelli in Integrazione dati](./media/sales-invoice-direct-template-mapping-data-integrator-2.png)



## <a name="related-topics"></a><span data-ttu-id="19ea5-170">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="19ea5-170">Related topics</span></span>

[<span data-ttu-id="19ea5-171">Prospect per uno scenario di liquidazione</span><span class="sxs-lookup"><span data-stu-id="19ea5-171">Prospect to cash</span></span>](prospect-to-cash.md)

[<span data-ttu-id="19ea5-172">Sincronizzare conti direttamente da Sales con clienti in Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="19ea5-172">Synchronize accounts directly from Sales to customers in Supply Chain Management</span></span>](accounts-template-mapping-direct.md)

[<span data-ttu-id="19ea5-173">Sincronizzare prodotti direttamente da Supply Chain Management con prodotti in Sales</span><span class="sxs-lookup"><span data-stu-id="19ea5-173">Synchronize products directly from Supply Chain Management to products in Sales</span></span>](products-template-mapping-direct.md)

[<span data-ttu-id="19ea5-174">Sincronizzare contatti direttamente da Sales con contatti o clienti in Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="19ea5-174">Synchronize contacts directly from Sales to contacts or customers in Supply Chain Management</span></span>](contacts-template-mapping-direct.md)

[<span data-ttu-id="19ea5-175">Sincronizzazione degli ordini cliente direttamente tra Sales e Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="19ea5-175">Synchronization of sales orders directly between Sales and Supply Chain Management</span></span>](sales-order-template-mapping-direct-two-ways.md)
