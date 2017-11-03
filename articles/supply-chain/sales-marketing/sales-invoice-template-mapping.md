---
title: Sincronizzare intestazioni e righe di fatture di vendita da Finance and Operations in Sales
description: "L'argomento descrive i modelli e le attività sottostanti che vengono utilizzati per sincronizzare le righe e le intestazioni delle fatture di vendita da Microsoft Dynamics 365 for Finance and Operations, Enterprise edition in Microsoft Dynamics 365 for Sales."
author: ChristianRytt
manager: AnnBe
ms.date: 08/28/2017
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
ms.dyn365.ops.intro: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 22ab02555dcac850b18aac9564af41d6c627eade
ms.contentlocale: it-it
ms.lasthandoff: 11/03/2017

---

# <a name="synchronize-sales-invoice-headers-and-lines-from-finance-and-operations-to-sales"></a><span data-ttu-id="bf83d-103">Sincronizzare intestazioni e righe di fatture di vendita da Finance and Operations in Sales</span><span class="sxs-lookup"><span data-stu-id="bf83d-103">Synchronize sales invoice headers and lines from Finance and Operations to Sales</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="bf83d-104">L'argomento descrive i modelli e le attività sottostanti che vengono utilizzati per sincronizzare le righe e le intestazioni delle fatture di vendita da Microsoft Dynamics 365 for Finance and Operations, Enterprise edition in Microsoft Dynamics 365 for Sales.</span><span class="sxs-lookup"><span data-stu-id="bf83d-104">The topic discusses the templates and underlying tasks that are used to synchronize sales invoice headers and lines from Microsoft Dynamics 365 for Finance and Operations, Enterprise edition to Microsoft Dynamics 365 for Sales.</span></span> 

## <a name="templates-and-tasks"></a><span data-ttu-id="bf83d-105">Modelli e attività</span><span class="sxs-lookup"><span data-stu-id="bf83d-105">Templates and tasks</span></span>

<span data-ttu-id="bf83d-106">I seguenti modelli e attività sottostanti vengono utilizzati per sincronizzare le intestazioni e le righe delle fatture di vendita da Finance and Operations in Sales:</span><span class="sxs-lookup"><span data-stu-id="bf83d-106">The following templates and underlying tasks are used to synchronize sales invoice headers and lines from Finance and Operations to Sales:</span></span>

- <span data-ttu-id="bf83d-107">**Nome del modello in Integrazione dati**</span><span class="sxs-lookup"><span data-stu-id="bf83d-107">**Name of the template in Data integration**</span></span> 

     - <span data-ttu-id="bf83d-108">Fatture di vendita (da Fin and Ops in Sales)</span><span class="sxs-lookup"><span data-stu-id="bf83d-108">Sales Invoices (Fin and Ops to Sales)</span></span>

- <span data-ttu-id="bf83d-109">**Nomi delle attività nel progetto di Integrazione dati**</span><span class="sxs-lookup"><span data-stu-id="bf83d-109">**Names of the tasks in the Data integration project**</span></span>

    - <span data-ttu-id="bf83d-110">SalesInvoiceHeader</span><span class="sxs-lookup"><span data-stu-id="bf83d-110">SalesInvoiceHeader</span></span>
    - <span data-ttu-id="bf83d-111">SalesInvoiceLine</span><span class="sxs-lookup"><span data-stu-id="bf83d-111">SalesInvoiceLine</span></span>

<span data-ttu-id="bf83d-112">Le attività di sincronizzazione necessarie prima di sincronizzare righe e intestazione della fattura di vendita:</span><span class="sxs-lookup"><span data-stu-id="bf83d-112">Sync tasks required prior to Sales invoice header and lines synchronization:</span></span>
-   <span data-ttu-id="bf83d-113">Prodotti (da Fin and Ops in Sales)</span><span class="sxs-lookup"><span data-stu-id="bf83d-113">Products (Fin and Ops to Sales)</span></span>
-   <span data-ttu-id="bf83d-114">Conti (da Sales in Fin and Ops) (se utilizzata)</span><span class="sxs-lookup"><span data-stu-id="bf83d-114">Accounts (Sales to Fin and Ops) (if used)</span></span>
-   <span data-ttu-id="bf83d-115">Contatti (da Sales in Fin and Ops) (se utilizzata)</span><span class="sxs-lookup"><span data-stu-id="bf83d-115">Contacts (Sales to Fin and Ops) (if used)</span></span>
-   <span data-ttu-id="bf83d-116">Intestazione e righe dell'ordine cliente (da Fin and Ops in Sales)</span><span class="sxs-lookup"><span data-stu-id="bf83d-116">Sales order header and lines (Fin and Ops to Sales)</span></span>

## <a name="entity-set"></a><span data-ttu-id="bf83d-117">Insieme di entità</span><span class="sxs-lookup"><span data-stu-id="bf83d-117">Entity set</span></span>

| <span data-ttu-id="bf83d-118">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="bf83d-118">Finance and Operations</span></span>                               | <span data-ttu-id="bf83d-119">Common Data Service (CDS)</span><span class="sxs-lookup"><span data-stu-id="bf83d-119">Common Data Service (CDS)</span></span>              | <span data-ttu-id="bf83d-120">Vendite</span><span class="sxs-lookup"><span data-stu-id="bf83d-120">Sales</span></span>          |
|------------------------------------------------------|------------------|----------------|
| <span data-ttu-id="bf83d-121">Intestazioni fatture di vendita cliente gestite esternamente</span><span class="sxs-lookup"><span data-stu-id="bf83d-121">Externally maintained customer sales invoice headers</span></span> | <span data-ttu-id="bf83d-122">SalesInvoice</span><span class="sxs-lookup"><span data-stu-id="bf83d-122">SalesInvoice</span></span>     | <span data-ttu-id="bf83d-123">Fatture</span><span class="sxs-lookup"><span data-stu-id="bf83d-123">Invoices</span></span>       |
| <span data-ttu-id="bf83d-124">Righe fatture di vendita cliente gestite esternamente</span><span class="sxs-lookup"><span data-stu-id="bf83d-124">Externally maintained customer sales invoice lines</span></span>   | <span data-ttu-id="bf83d-125">SalesInvoiceLine</span><span class="sxs-lookup"><span data-stu-id="bf83d-125">SalesInvoiceLine</span></span> | <span data-ttu-id="bf83d-126">InvoiceDetails</span><span class="sxs-lookup"><span data-stu-id="bf83d-126">InvoiceDetails</span></span> |

## <a name="entity-flow"></a><span data-ttu-id="bf83d-127">Flusso di entità</span><span class="sxs-lookup"><span data-stu-id="bf83d-127">Entity flow</span></span>

<span data-ttu-id="bf83d-128">Le fatture di vendita vengono create in Finance and Operations e sincronizzate in Sales.</span><span class="sxs-lookup"><span data-stu-id="bf83d-128">Sales invoices are created in Finance and Operations and synchronized to Sales.</span></span>

> [!NOTE]
> <span data-ttu-id="bf83d-129">L'imposta relativa alle spese nell'**intestazione della fattura di vendita** non è attualmente inclusa nella sincronizzazione da Finance and Operations in Sales.</span><span class="sxs-lookup"><span data-stu-id="bf83d-129">Tax related to charges on the **Sales invoice header** is currently not included in synchronization from Finance and Operations to Sales.</span></span> <span data-ttu-id="bf83d-130">Questo perché Sales non supporta le informazioni fiscali a livello di intestazione.</span><span class="sxs-lookup"><span data-stu-id="bf83d-130">This is because Sales doesn't support tax information at the header level.</span></span> <span data-ttu-id="bf83d-131">È inclusa l'imposta relativa alle spese a livello di riga.</span><span class="sxs-lookup"><span data-stu-id="bf83d-131">Tax related to charges at the line level is included.</span></span>

## <a name="prospect-to-cash-solution-for-sales"></a><span data-ttu-id="bf83d-132">Soluzione Prospect to cash per Sales</span><span class="sxs-lookup"><span data-stu-id="bf83d-132">Prospect to cash solution for Sales</span></span>

-  <span data-ttu-id="bf83d-133">Un **campo per il numero di fattura** viene aggiunto all'entità **Fattura** e visualizzato nella pagina.</span><span class="sxs-lookup"><span data-stu-id="bf83d-133">An **Invoice number field** is added to the **Invoice** entity and displayed on the page.</span></span>
 
-  <span data-ttu-id="bf83d-134">Il pulsante **Crea fattura** nella pagina **Ordine cliente** è nascosto perché le fatture verranno create in Finance and Operations e sincronizzate in Sales.</span><span class="sxs-lookup"><span data-stu-id="bf83d-134">The **Create invoice** button on the **Sales order** page is hidden because invoices will be created in Finance and Operations and synced to Sales.</span></span> <span data-ttu-id="bf83d-135">La pagina **Fattura** non è modificabile poiché le fatture verranno sincronizzate da Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="bf83d-135">The **Invoice** page is non-editable because invoices will be synced from Finance and Operations.</span></span>
 
-  <span data-ttu-id="bf83d-136">Lo **stato dell'ordine cliente** diventa automaticamente **Fatturato** dopo la sincronizzazione della fattura correlata da Finance and Operations in Sales.</span><span class="sxs-lookup"><span data-stu-id="bf83d-136">The **Sales order status** changes automatically to **Invoiced** when the related invoice from Finance and Operations has been  synchronized to Sales.</span></span> <span data-ttu-id="bf83d-137">Inoltre, il proprietario dell'ordine cliente da cui la fattura è stata creata viene assegnato come proprietario della fattura.</span><span class="sxs-lookup"><span data-stu-id="bf83d-137">Also, the owner of the sales order from which the invoice was created is assigned as the owner of the invoice.</span></span> <span data-ttu-id="bf83d-138">Il proprietario dell'ordine cliente ha quindi la possibilità di visualizzare la fattura.</span><span class="sxs-lookup"><span data-stu-id="bf83d-138">This gives the owner of the sales order the ability to view the invoice.</span></span>
 
## <a name="preconditions-and-mapping-setup"></a><span data-ttu-id="bf83d-139">Prerequisiti e impostazioni di mapping</span><span class="sxs-lookup"><span data-stu-id="bf83d-139">Preconditions and mapping setup</span></span>

<span data-ttu-id="bf83d-140">Prima di sincronizzare le fatture di vendita, è importante aggiornare i sistemi con la seguente impostazione:</span><span class="sxs-lookup"><span data-stu-id="bf83d-140">Before synchronizing sales invoices, it is important to update the systems with the following setting:</span></span>

### <a name="setup-in-sales"></a><span data-ttu-id="bf83d-141">Impostazione in Sales</span><span class="sxs-lookup"><span data-stu-id="bf83d-141">Setup in Sales</span></span>

- <span data-ttu-id="bf83d-142">In **Impostazioni** > **Amministrazione** > **Impostazioni di sistema** > **Vendite**, verificare che **Usa sistema di calcolo prezzi sistema** sia impostato su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="bf83d-142">Under **Settings** > **Administration** > **System settings** > **Sales**, ensure that **Use system prizing calculation system** is set to **Yes**.</span></span> 

- <span data-ttu-id="bf83d-143">In **Impostazioni** > **Amministrazione** > **Impostazioni di sistema** > **Vendite**, verificare che **Metodo di calcolo sconto** sia impostato su **Voce**.</span><span class="sxs-lookup"><span data-stu-id="bf83d-143">Under **Settings** > **Administration** > **System settings** > **Sales**, ensure that **Discount calculation method** is set to **Line item**.</span></span> 

### <a name="setup-in-the-data-integration-project"></a><span data-ttu-id="bf83d-144">Impostazione nel progetto di Integrazione dati</span><span class="sxs-lookup"><span data-stu-id="bf83d-144">Setup in the Data integration project</span></span>

#### <a name="salesinvoiceheader-task"></a><span data-ttu-id="bf83d-145">Attività SalesInvoiceHeader</span><span class="sxs-lookup"><span data-stu-id="bf83d-145">SalesInvoiceHeader task</span></span>

- <span data-ttu-id="bf83d-146">Aggiornare il mapping per **ID organizzazione CDS** in **Origine** > **CDS**.</span><span class="sxs-lookup"><span data-stu-id="bf83d-146">Update the mapping for **CDS Organization ID** in **Source** > **CDS**.</span></span> 

    -  <span data-ttu-id="bf83d-147">Il valore del modello predefinito per **SalesOrder_Organization_OrganizationId** è ORG001.</span><span class="sxs-lookup"><span data-stu-id="bf83d-147">Default template value for **SalesOrder_Organization_OrganizationId** is ORG001.</span></span>
    -  <span data-ttu-id="bf83d-148">Il valore del modello predefinito per **Account_Organization_OrganizationId** è ORG001.</span><span class="sxs-lookup"><span data-stu-id="bf83d-148">Default template value for **Account_Organization_OrganizationId** is ORG001.</span></span>
    -  <span data-ttu-id="bf83d-149">Il valore del modello predefinito per **Organization_OrganizationId** è ORG001.</span><span class="sxs-lookup"><span data-stu-id="bf83d-149">Default template value for **Organization_OrganizationId** is ORG001.</span></span>

- <span data-ttu-id="bf83d-150">Verificare che il mapping necessario esista in **Origine** > **CDS per InvoiceCountryRegionId** a **BillingAddress_Country**.</span><span class="sxs-lookup"><span data-stu-id="bf83d-150">Ensure that the needed mapping exists in **Source** > **CDS for InvoiceCountryRegionId** to **BillingAddress_Country**.</span></span>

    -  <span data-ttu-id="bf83d-151">Il valore del modello è **ValueMap** con un numero di paesi mappati.</span><span class="sxs-lookup"><span data-stu-id="bf83d-151">Template value is **ValueMap** with a number of countries mapped.</span></span>

- <span data-ttu-id="bf83d-152">Il **listino prezzi** è necessario per creare fatture in Sales.</span><span class="sxs-lookup"><span data-stu-id="bf83d-152">**Price list** is required to create invoices in Sales.</span></span> <span data-ttu-id="bf83d-153">Aggiornare **ValueMap** in **CDS** > **Destinazione per pricelevelid.name [nome listino prezzi]** al **listino prezzi** utilizzato in Sales per la valuta.</span><span class="sxs-lookup"><span data-stu-id="bf83d-153">Update the **ValueMap** in **CDS** > **Destination for pricelevelid.name [Price List Name]** to the **Price list** used in Sales per currency.</span></span> <span data-ttu-id="bf83d-154">È possibile utilizzare il **listino prezzi** predefinito per una singola valuta oppure **ValueMap** se si hanno **listini prezzi** in molteplici valute.</span><span class="sxs-lookup"><span data-stu-id="bf83d-154">You can either use the default **Price list** for single currency or use **ValueMap** if you have **Price lists** in multiple currencies.</span></span>

    -  <span data-ttu-id="bf83d-155">Il valore del modello per **pricelevelid.name [nome listino prezzi]** è **ValueMap** basato su **Valuta**.</span><span class="sxs-lookup"><span data-stu-id="bf83d-155">Template value for **pricelevelid.name [Price List Name]** is **ValueMap** based on **Currency**.</span></span>
    -  <span data-ttu-id="bf83d-156">usd: Servizio CRM USA (esempio).</span><span class="sxs-lookup"><span data-stu-id="bf83d-156">usd: CRM Service USA (sample).</span></span> 

#### <a name="salesinvoiceline-task"></a><span data-ttu-id="bf83d-157">Attività SalesInvoiceLine</span><span class="sxs-lookup"><span data-stu-id="bf83d-157">SalesInvoiceLine task</span></span>

- <span data-ttu-id="bf83d-158">Verificare che il mapping necessario esista in **Origine** > **CDS per unità di misura**.</span><span class="sxs-lookup"><span data-stu-id="bf83d-158">Ensure that the needed mapping exists in **Source** > **CDS for Unit of measure**.</span></span>

- <span data-ttu-id="bf83d-159">Assicurarsi che **ValueMap** per **SalesUnitSymbol** in Finance and Operations sia presente in **Origine** > **Mapping CDS**.</span><span class="sxs-lookup"><span data-stu-id="bf83d-159">Ensure that the needed **ValueMap** for **SalesUnitSymbol** in Finance and Operations exists in the **Source** > **CDS mapping**.</span></span> 
    
    - <span data-ttu-id="bf83d-160">Il valore del modello con **ValueMap** è definito per **SalesUnitSymbol a Quantity_UOM**.</span><span class="sxs-lookup"><span data-stu-id="bf83d-160">Template value with **ValueMap** is defined for **SalesUnitSymbol to Quantity_UOM**.</span></span>
    
-  <span data-ttu-id="bf83d-161">Aggiornare il mapping per **ID organizzazione CDS in Origine** > **CDS**.</span><span class="sxs-lookup"><span data-stu-id="bf83d-161">Update the mapping for **CDS Organization ID in Source** > **CDS**.</span></span> 

    -  <span data-ttu-id="bf83d-162">Il valore del modello predefinito per **SalesInvoicer_Organization_OrganizationId** è ORG001.</span><span class="sxs-lookup"><span data-stu-id="bf83d-162">Default template value for **SalesInvoicer_Organization_OrganizationId** is ORG001.</span></span>
    -  <span data-ttu-id="bf83d-163">Il valore del modello predefinito per **Product_Organization_OrganizationId** è ORG001.</span><span class="sxs-lookup"><span data-stu-id="bf83d-163">Default template value for **Product_Organization_OrganizationId** is ORG001.</span></span>
 
## <a name="template-mapping-in-data-integrator"></a><span data-ttu-id="bf83d-164">Mapping dei modelli nell'integratore di dati</span><span class="sxs-lookup"><span data-stu-id="bf83d-164">Template mapping in Data integrator</span></span>

> [!NOTE]
> <span data-ttu-id="bf83d-165">I campi **Termini di pagamento**, **Termini di trasporto**, **Termini di consegna**, **Metodo di spedizione** e **Modalità di consegna** non sono inclusi nei mapping predefiniti.</span><span class="sxs-lookup"><span data-stu-id="bf83d-165">**Payment terms**, **Freight terms**, **Delivery terms**, **Shipping method**, and **Delivery mode** are not part of the default mappings.</span></span> <span data-ttu-id="bf83d-166">Il mapping di questi campi richiede l'impostazione di un mapping di valori che sia specifico ai dati delle organizzazioni tra cui l'entità viene sincronizzata.</span><span class="sxs-lookup"><span data-stu-id="bf83d-166">Mapping of these fields requires value mapping to be set up, which is specific to the data in the organizations between which the entity is synchronized.</span></span>

<span data-ttu-id="bf83d-167">Nelle figure seguenti viene illustrato un esempio di un modello di mapping nell'integratore di dati.</span><span class="sxs-lookup"><span data-stu-id="bf83d-167">The following illustrations show an example of a template mapping in data integrator.</span></span>

![Mapping dei modelli nell'integratore di dati](./media/sales-invoice-template-mapping-data-integrator-1.png)

![Mapping dei modelli nell'integratore di dati](./media/sales-invoice-template-mapping-data-integrator-2.png)

![Mapping dei modelli nell'integratore di dati](./media/sales-invoice-template-mapping-data-integrator-3.png)

![Mapping dei modelli nell'integratore di dati](./media/sales-invoice-template-mapping-data-integrator-4.png)


## <a name="related-topics"></a><span data-ttu-id="bf83d-172">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="bf83d-172">Related topics</span></span>

[<span data-ttu-id="bf83d-173">Sincronizzare i prodotti da Finance and Operations ai prodotti in Sales</span><span class="sxs-lookup"><span data-stu-id="bf83d-173">Synchronize products from Finance and Operations to products in Sales</span></span>](products-template-mapping.md)

[<span data-ttu-id="bf83d-174">Sincronizzare conti da Sales con clienti in Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="bf83d-174">Synchronize accounts from Sales to customers in Finance and Operations</span></span>](accounts-template-mapping.md)

[<span data-ttu-id="bf83d-175">Sincronizzare contatti da Sales con contatti o clienti in Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="bf83d-175">Synchronize contacts from Sales to contacts or customers in Finance and Operations</span></span>](contacts-template-mapping.md)

[<span data-ttu-id="bf83d-176">Sincronizzare intestazioni e righe di offerte di vendita da Sales in Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="bf83d-176">Synchronize sales quotation headers and lines from Sales to Finance and Operations</span></span>](sales-quotation-template-mapping.md)

[<span data-ttu-id="bf83d-177">Sincronizzare intestazioni e righe di ordini di vendita da Finance and Operations in Sales</span><span class="sxs-lookup"><span data-stu-id="bf83d-177">Synchronize sales order headers and lines from Finance and Operations to Sales</span></span>](sales-order-template-mapping.md)


