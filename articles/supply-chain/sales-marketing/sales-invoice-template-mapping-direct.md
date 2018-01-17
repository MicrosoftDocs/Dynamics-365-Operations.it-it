---
title: Sincronizzare intestazioni e righe di fatture di vendita direttamente da Finance and Operations in Sales
description: "Questo argomento descrive i modelli e le attività sottostanti che vengono utilizzati per sincronizzare le righe e le intestazioni di fatture di vendita direttamente da Microsoft Dynamics 365 for Finance and Operations, Enterprise edition in Microsoft Dynamics 365 for Sales."
author: ChristianRytt
manager: AnnBe
ms.date: 10/26/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User, IT Pro
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: crytt
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: 029511634e56aec7fdd91bad9441cd12951fbd8d
ms.openlocfilehash: 534279eb0f139950a4bb568c8da04383b88e6db2
ms.contentlocale: it-it
ms.lasthandoff: 01/17/2018

---

# <a name="synchronize-sales-invoice-headers-and-lines-directly-from-finance-and-operations-to-sales"></a><span data-ttu-id="48a24-103">Sincronizzare intestazioni e righe di fatture di vendita direttamente da Finance and Operations in Sales</span><span class="sxs-lookup"><span data-stu-id="48a24-103">Synchronize sales invoice headers and lines directly from Finance and Operations to Sales</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="48a24-104">Questo argomento descrive i modelli e le attività sottostanti che vengono utilizzati per sincronizzare le righe e le intestazioni di fatture di vendita direttamente da Microsoft Dynamics 365 for Finance and Operations, Enterprise edition in Microsoft Dynamics 365 for Sales.</span><span class="sxs-lookup"><span data-stu-id="48a24-104">This topic discusses the templates and underlying tasks that are used to synchronize sales invoice headers and lines directly from Microsoft Dynamics 365 for Finance and Operations, Enterprise edition, to Microsoft Dynamics 365 for Sales.</span></span>

## <a name="data-flow-in-prospect-to-cash"></a><span data-ttu-id="48a24-105">Flusso di dati in Prospect to cash</span><span class="sxs-lookup"><span data-stu-id="48a24-105">Data flow in Prospect to cash</span></span>

<span data-ttu-id="48a24-106">La soluzione Prospect to cash utilizza la funzionalità Integrazione dati per sincronizzare i dati tra istanze di Finance and Operations e Sales.</span><span class="sxs-lookup"><span data-stu-id="48a24-106">The Prospect to cash solution uses the Data integration feature to synchronize data across instances of Finance and Operations and Sales.</span></span> <span data-ttu-id="48a24-107">I modelli Prospect to cash disponibili con la funzionalità Integrazione dati consentono il flusso di dati relativo a conti, contatti, prodotti, offerte di vendita, ordini cliente e fatture di vendita tra Finance and Operations e Sales.</span><span class="sxs-lookup"><span data-stu-id="48a24-107">The Prospect to cash templates that are available with the Data integration feature enable the flow of data about accounts, contacts, products, sales quotations, sales orders, and sales invoices between Finance and Operations and Sales.</span></span> <span data-ttu-id="48a24-108">La figura seguente mostra il modo in cui i dati vengono sincronizzati tra Finance and Operations e Sales.</span><span class="sxs-lookup"><span data-stu-id="48a24-108">The following illustration shows how the data is synchronized between Finance and Operations and Sales.</span></span>

<span data-ttu-id="48a24-109">[![Flusso di dati in Prospect to cash](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)</span><span class="sxs-lookup"><span data-stu-id="48a24-109">[![Data flow in Prospect to cash](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="48a24-110">Modelli e attività</span><span class="sxs-lookup"><span data-stu-id="48a24-110">Templates and tasks</span></span>

<span data-ttu-id="48a24-111">Per accedere ai modelli disponibili, aprire l'[Interfaccia di amministrazione di PowerApps](https://preview.admin.powerapps.com/dataintegration).</span><span class="sxs-lookup"><span data-stu-id="48a24-111">To access the available templates, open [PowerApps Admin Center](https://preview.admin.powerapps.com/dataintegration).</span></span> <span data-ttu-id="48a24-112">Selezionare **Progetti**, quindi nell'angolo superiore destro, selezionare **Nuovo progetto** per selezionare i modelli pubblici.</span><span class="sxs-lookup"><span data-stu-id="48a24-112">Select **Projects**, and then, in the upper-right corner, select **New project** to select public templates.</span></span>

<span data-ttu-id="48a24-113">Il seguente modello e le attività sottostanti vengono utilizzati per sincronizzare le intestazioni e le righe di fatture di vendita da Finance and Operations in Sales:</span><span class="sxs-lookup"><span data-stu-id="48a24-113">The following template and underlying tasks are used to synchronize sales invoice headers and lines from Finance and Operations to Sales:</span></span>

- <span data-ttu-id="48a24-114">**Nome del modello in Integrazione dati:** Fatture di vendita (da Fin and Ops in Sales) - Diretto</span><span class="sxs-lookup"><span data-stu-id="48a24-114">**Name of the template in Data integration:** Sales Invoices (Fin and Ops to Sales) - Direct</span></span>
- <span data-ttu-id="48a24-115">**Nomi delle attività nel progetto di Integrazione dati:**</span><span class="sxs-lookup"><span data-stu-id="48a24-115">**Names of the tasks in the Data integration project:**</span></span>

    - <span data-ttu-id="48a24-116">SalesInvoiceHeader</span><span class="sxs-lookup"><span data-stu-id="48a24-116">SalesInvoiceHeader</span></span>
    - <span data-ttu-id="48a24-117">SalesInvoiceLine</span><span class="sxs-lookup"><span data-stu-id="48a24-117">SalesInvoiceLine</span></span>

<span data-ttu-id="48a24-118">Le attività di sincronizzazione seguenti sono necessarie prima di eseguire la sincronizzazione delle intestazioni e delle righe di fatture di vendita:</span><span class="sxs-lookup"><span data-stu-id="48a24-118">The following synchronization tasks are required before synchronization of sales invoice headers and lines can occur:</span></span>

- <span data-ttu-id="48a24-119">Prodotti (da Fin and Ops in Sales) - Diretto</span><span class="sxs-lookup"><span data-stu-id="48a24-119">Products (Fin and Ops to Sales) - Direct</span></span>
- <span data-ttu-id="48a24-120">Conti (da Sales in Fin and Ops) - Diretto (se utilizzata)</span><span class="sxs-lookup"><span data-stu-id="48a24-120">Accounts (Sales to Fin and Ops) - Direct (if used)</span></span>
- <span data-ttu-id="48a24-121">Contatti (da Sales in Fin and Ops) - Diretto (se utilizzata)</span><span class="sxs-lookup"><span data-stu-id="48a24-121">Contacts (Sales to Fin and Ops) - Direct (if used)</span></span>
- <span data-ttu-id="48a24-122">Intestazione e righe ordine cliente (da Fin and Ops in Sales) - Diretto</span><span class="sxs-lookup"><span data-stu-id="48a24-122">Sales order header and lines (Fin and Ops to Sales) - Direct</span></span>

## <a name="entity-set"></a><span data-ttu-id="48a24-123">Insieme di entità</span><span class="sxs-lookup"><span data-stu-id="48a24-123">Entity set</span></span>

| <span data-ttu-id="48a24-124">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="48a24-124">Finance and Operations</span></span>                               | <span data-ttu-id="48a24-125">Vendite</span><span class="sxs-lookup"><span data-stu-id="48a24-125">Sales</span></span>          |
|------------------------------------------------------|----------------|
| <span data-ttu-id="48a24-126">Intestazioni fatture di vendita cliente gestite esternamente</span><span class="sxs-lookup"><span data-stu-id="48a24-126">Externally maintained customer sales invoice headers</span></span> | <span data-ttu-id="48a24-127">Fatture</span><span class="sxs-lookup"><span data-stu-id="48a24-127">Invoices</span></span>       |
| <span data-ttu-id="48a24-128">Righe fatture di vendita cliente gestite esternamente</span><span class="sxs-lookup"><span data-stu-id="48a24-128">Externally maintained customer sales invoice lines</span></span>   | <span data-ttu-id="48a24-129">InvoiceDetails</span><span class="sxs-lookup"><span data-stu-id="48a24-129">InvoiceDetails</span></span> |

## <a name="entity-flow"></a><span data-ttu-id="48a24-130">Flusso di entità</span><span class="sxs-lookup"><span data-stu-id="48a24-130">Entity flow</span></span>

<span data-ttu-id="48a24-131">Le fatture di vendita vengono create in Finance and Operations e sincronizzate in Sales.</span><span class="sxs-lookup"><span data-stu-id="48a24-131">Sales invoices are created in Finance and Operations and synchronized to Sales.</span></span>

> [!NOTE]
> <span data-ttu-id="48a24-132">L'imposta relativa alle spese nell'intestazione della fattura di vendita non è attualmente inclusa nella sincronizzazione da Finance and Operations in Sales.</span><span class="sxs-lookup"><span data-stu-id="48a24-132">Currently, tax that is related to charges on the sales invoice header isn't included in the synchronization from Finance and Operations to Sales.</span></span> <span data-ttu-id="48a24-133">Sales non supporta le informazioni fiscali a livello di intestazione.</span><span class="sxs-lookup"><span data-stu-id="48a24-133">Sales doesn't support tax information at the header level.</span></span> <span data-ttu-id="48a24-134">Tuttavia, l'imposta relativa alle spese a livello di riga è inclusa nella sincronizzazione.</span><span class="sxs-lookup"><span data-stu-id="48a24-134">However, tax that is related to charges at the line level is included in the synchronization.</span></span>

## <a name="prospect-to-cash-solution-for-sales"></a><span data-ttu-id="48a24-135">Soluzione Prospect to cash per Sales</span><span class="sxs-lookup"><span data-stu-id="48a24-135">Prospect to cash solution for Sales</span></span>

- <span data-ttu-id="48a24-136">Un campo **Numero fattura** è stato aggiunto all'entità **Fattura** ed è visualizzato nella pagina.</span><span class="sxs-lookup"><span data-stu-id="48a24-136">An **Invoice number** field has been added to the **Invoice** entity and appears on the page.</span></span>
- <span data-ttu-id="48a24-137">Il pulsante **Crea fattura** nella pagina **Ordine cliente** è nascosto perché le fatture verranno create in Finance and Operations e sincronizzate in Sales.</span><span class="sxs-lookup"><span data-stu-id="48a24-137">The **Create invoice** button on the **Sales order** page is hidden, because invoices will be created in Finance and Operations and synchronized to Sales.</span></span> <span data-ttu-id="48a24-138">La pagina **Fattura** non è modificabile poiché le fatture verranno sincronizzate da Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="48a24-138">The **Invoice** page can't be edited, because invoices will be synchronized from Finance and Operations.</span></span>
- <span data-ttu-id="48a24-139">Il valore **Stato dell'ordine cliente** diventa automaticamente **Fatturato** dopo la sincronizzazione della fattura correlata da Finance and Operations in Sales.</span><span class="sxs-lookup"><span data-stu-id="48a24-139">The **Sales order status** value is automatically changed to **Invoiced** when the related invoice from Finance and Operations has been synchronized to Sales.</span></span> <span data-ttu-id="48a24-140">Inoltre, il proprietario dell'ordine cliente da cui la fattura è stata creata viene assegnato come proprietario della fattura.</span><span class="sxs-lookup"><span data-stu-id="48a24-140">Additionally, the owner of the sales order that the invoice was created from is assigned as the owner of the invoice.</span></span> <span data-ttu-id="48a24-141">Di conseguenza, il proprietario dell'ordine cliente può visualizzare la fattura.</span><span class="sxs-lookup"><span data-stu-id="48a24-141">Therefore, the owner of the sales order can view the invoice.</span></span>

## <a name="preconditions-and-mapping-setup"></a><span data-ttu-id="48a24-142">Prerequisiti e impostazioni di mapping</span><span class="sxs-lookup"><span data-stu-id="48a24-142">Preconditions and mapping setup</span></span>

<span data-ttu-id="48a24-143">Prima di sincronizzare le fatture di vendita, è importante aggiornare le seguenti impostazioni nei sistemi:</span><span class="sxs-lookup"><span data-stu-id="48a24-143">Before you synchronize sales invoices, it's important that you update the following settings in the systems.</span></span>

### <a name="setup-in-sales"></a><span data-ttu-id="48a24-144">Impostazione in Sales</span><span class="sxs-lookup"><span data-stu-id="48a24-144">Setup in Sales</span></span>

<span data-ttu-id="48a24-145">Andare a **Impostazioni** > **Amministrazione** > **Impostazioni di sistema** > **Vendite** e assicurarsi che:</span><span class="sxs-lookup"><span data-stu-id="48a24-145">Go to **Settings** > **Administration** > **System settings** > **Sales**, and make sure that the following settings are used:</span></span>

- <span data-ttu-id="48a24-146">L'opzione **Usa sistema di calcolo prezzi sistema** sia impostata su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="48a24-146">The **Use system prizing calculation system** option is set to **Yes**.</span></span>
- <span data-ttu-id="48a24-147">Il campo **Metodo di calcolo sconto** sia impostato su **Voce**.</span><span class="sxs-lookup"><span data-stu-id="48a24-147">The **Discount calculation method** field is set to **Line item**.</span></span>

### <a name="setup-in-the-data-integration-project"></a><span data-ttu-id="48a24-148">Impostazione nel progetto di Integrazione dati</span><span class="sxs-lookup"><span data-stu-id="48a24-148">Setup in the Data integration project</span></span>

#### <a name="salesinvoiceheader-task"></a><span data-ttu-id="48a24-149">Attività SalesInvoiceHeader</span><span class="sxs-lookup"><span data-stu-id="48a24-149">SalesInvoiceHeader task</span></span>

- <span data-ttu-id="48a24-150">Assicurarsi che il mapping richiesto esista per **InvoiceCountryRegionId** a **BillingAddress\_Country**.</span><span class="sxs-lookup"><span data-stu-id="48a24-150">Make sure that the required mapping exists for **InvoiceCountryRegionId** to **BillingAddress\_Country**.</span></span>

    <span data-ttu-id="48a24-151">Il valore di modello è una mappa di valori dove vari paesi sono mappati.</span><span class="sxs-lookup"><span data-stu-id="48a24-151">The template value is a value map where several countries or regions are mapped.</span></span>

- <span data-ttu-id="48a24-152">Un listino prezzi è necessario per creare fatture in Sales.</span><span class="sxs-lookup"><span data-stu-id="48a24-152">A price list is required in order to create invoices in Sales.</span></span> <span data-ttu-id="48a24-153">Aggiornare la mappa di valori per **pricelevelid.name \[nome listino prezzi\]** al listino prezzi utilizzato in Sales per la valuta.</span><span class="sxs-lookup"><span data-stu-id="48a24-153">Update the value map for **pricelevelid.name \[Price list name\]** to the price list that is used in Sales per currency.</span></span> <span data-ttu-id="48a24-154">È possibile utilizzare il listino prezzi predefinito per una singola valuta.</span><span class="sxs-lookup"><span data-stu-id="48a24-154">You can use the default price list for a single currency.</span></span> <span data-ttu-id="48a24-155">In alternativa, se si hanno listini prezzi in più valute, è possibile utilizzare una mappa di valori.</span><span class="sxs-lookup"><span data-stu-id="48a24-155">Alternatively, if you have price lists in multiple currencies, you can use a value map.</span></span>

    <span data-ttu-id="48a24-156">Il valore di modello per **pricelevelid.name \[[nome listino prezzi\]** è una mappa di valori basata sulla valuta con USD = Servizio CRM USA (esempio).</span><span class="sxs-lookup"><span data-stu-id="48a24-156">The template value for **pricelevelid.name \[Price list name\]** is a value map that is based on currency with USD = CRM Service USA (sample).</span></span>  
    
#### <a name="salesinvoiceline-task"></a><span data-ttu-id="48a24-157">Attività SalesInvoiceLine</span><span class="sxs-lookup"><span data-stu-id="48a24-157">SalesInvoiceLine task</span></span>

- <span data-ttu-id="48a24-158">Assicurarsi che il mapping necessario esista per **Unità di misura**.</span><span class="sxs-lookup"><span data-stu-id="48a24-158">Make sure that the required mapping exists for **Unit of measure**.</span></span>
- <span data-ttu-id="48a24-159">Assicurarsi che la mappa di valori richiesta esista per **SalesUnitSymbol** in Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="48a24-159">Make sure that the required value map for **SalesUnitSymbol** in Finance and Operations exists.</span></span>

    <span data-ttu-id="48a24-160">Un valore di modello con una mappa di valori viene definito per **SalesUnitSymbol** a **Quantity\_UOM**.</span><span class="sxs-lookup"><span data-stu-id="48a24-160">A template value that has a value map is defined for **SalesUnitSymbol** to **Quantity\_UOM**.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="48a24-161">Mapping dei modelli in Integrazione dati</span><span class="sxs-lookup"><span data-stu-id="48a24-161">Template mapping in Data integration</span></span>

> [!NOTE]
> <span data-ttu-id="48a24-162">I campi **Termini di pagamento**, **Termini di trasporto**, **Termini di consegna**, **Metodo di spedizione** e **Modalità di consegna** non vengono inclusi nei mapping predefiniti.</span><span class="sxs-lookup"><span data-stu-id="48a24-162">The **Payment terms**, **Freight terms**, **Delivery terms**, **Shipping method**, and **Delivery mode** fields aren't included in the default mappings.</span></span> <span data-ttu-id="48a24-163">Per mappare questi campi, è necessario impostare un mapping di valori che sia specifico ai dati delle organizzazioni tra cui l'entità viene sincronizzata.</span><span class="sxs-lookup"><span data-stu-id="48a24-163">To map these fields, you must set up a value mapping that is specific to the data in the organizations that the entity is synchronized between.</span></span>

<span data-ttu-id="48a24-164">Nelle figure seguenti viene illustrato un esempio di mapping di modelli in Integrazione dati.</span><span class="sxs-lookup"><span data-stu-id="48a24-164">The following illustrations show an example of a template mapping in Data integration.</span></span> 

> [!NOTE]
> <span data-ttu-id="48a24-165">Il mapping mostra quali informazioni sui campi verranno sincronizzate da Sales in Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="48a24-165">The mapping shows which field information will be synchronized from Sales to Finance and Operations.</span></span>

### <a name="salesinvoiceheader"></a><span data-ttu-id="48a24-166">SalesInvoiceHeader</span><span class="sxs-lookup"><span data-stu-id="48a24-166">SalesInvoiceHeader</span></span>

![Mapping dei modelli in Integrazione dati](./media/sales-invoice-direct-template-mapping-data-integrator-1.png)

### <a name="salesinvoiceline"></a><span data-ttu-id="48a24-168">SalesInvoiceLine</span><span class="sxs-lookup"><span data-stu-id="48a24-168">SalesInvoiceLine</span></span>

![Mapping dei modelli in Integrazione dati](./media/sales-invoice-direct-template-mapping-data-integrator-2.png)



## <a name="related-topics"></a><span data-ttu-id="48a24-170">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="48a24-170">Related topics</span></span>

[<span data-ttu-id="48a24-171">Prospect to cash</span><span class="sxs-lookup"><span data-stu-id="48a24-171">Prospect to cash</span></span>](prospect-to-cash.md)

[<span data-ttu-id="48a24-172">Sincronizzare conti direttamente da Sales con clienti in Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="48a24-172">Synchronize accounts directly from Sales to customers in Finance and Operations</span></span>](accounts-template-mapping-direct.md)

[<span data-ttu-id="48a24-173">Sincronizzare prodotti direttamente da Finance and Operations con prodotti in Sales</span><span class="sxs-lookup"><span data-stu-id="48a24-173">Synchronize products directly from Finance and Operations to products in Sales</span></span>](products-template-mapping-direct.md)

[<span data-ttu-id="48a24-174">Sincronizzare contatti direttamente da Sales con contatti o clienti in Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="48a24-174">Synchronize contacts directly from Sales to contacts or customers in Finance and Operations</span></span>](contacts-template-mapping-direct.md)

[<span data-ttu-id="48a24-175">Sincronizzare intestazioni e righe di ordini cliente direttamente da Finance and Operations in Sales</span><span class="sxs-lookup"><span data-stu-id="48a24-175">Synchronize sales order headers and lines directly from Finance and Operations to Sales</span></span>](sales-order-template-mapping-direct.md)







