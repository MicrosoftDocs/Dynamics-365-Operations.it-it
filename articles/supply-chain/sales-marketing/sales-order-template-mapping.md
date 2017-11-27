---
title: Sincronizzare intestazioni e righe di ordini cliente da Finance and Operations in Sales
description: "L'argomento descrive i modelli e le attività sottostanti che vengono utilizzati per sincronizzare le righe e le intestazioni degli ordini cliente da Microsoft Dynamics 365 for Finance and Operations, Enterprise edition in Microsoft Dynamics 365 for Sales."
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
ms.dyn365.ops.intro: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: c7b2ff6430e99661ee284f65089086df9fa5a1ad
ms.contentlocale: it-it
ms.lasthandoff: 11/03/2017

---

# <a name="synchronize-sales-order-headers-and-lines-from-finance-and-operations-to-sales"></a><span data-ttu-id="0bd47-103">Sincronizzare intestazioni e righe di ordini cliente da Finance and Operations in Sales</span><span class="sxs-lookup"><span data-stu-id="0bd47-103">Synchronize sales order headers and lines from Finance and Operations to Sales</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="0bd47-104">L'argomento descrive i modelli e le attività sottostanti che vengono utilizzati per sincronizzare le righe e le intestazioni degli ordini cliente da Microsoft Dynamics 365 for Finance and Operations, Enterprise edition in Microsoft Dynamics 365 for Sales.</span><span class="sxs-lookup"><span data-stu-id="0bd47-104">The topic discusses the templates and underlying tasks that are used to synchronize sales order headers and lines from Microsoft Dynamics 365 for Finance and Operations, Enterprise edition to Microsoft Dynamics 365 for Sales.</span></span> 

## <a name="template-and-tasks"></a><span data-ttu-id="0bd47-105">Modello e attività</span><span class="sxs-lookup"><span data-stu-id="0bd47-105">Template and tasks</span></span>

<span data-ttu-id="0bd47-106">I seguenti modelli e attività sottostanti vengono utilizzati per sincronizzare le intestazioni e le righe degli ordini cliente da Finance and Operations in Sales:</span><span class="sxs-lookup"><span data-stu-id="0bd47-106">The following templates and underlying tasks are used to synchronize sales order headers and lines from Finance and Operations to Sales:</span></span>

- <span data-ttu-id="0bd47-107">**Nome del modello in Integrazione dati**</span><span class="sxs-lookup"><span data-stu-id="0bd47-107">**Name of template in Data integration**</span></span> 

    - <span data-ttu-id="0bd47-108">Ordini cliente (da Fin and Ops in Sales)</span><span class="sxs-lookup"><span data-stu-id="0bd47-108">Sales Orders (Fin and Ops to Sales)</span></span>
    
- <span data-ttu-id="0bd47-109">**Nomi delle attività nel progetto di Integrazione dati**</span><span class="sxs-lookup"><span data-stu-id="0bd47-109">**Names of tasks in Data integration project**</span></span>

    - <span data-ttu-id="0bd47-110">OrderHeader</span><span class="sxs-lookup"><span data-stu-id="0bd47-110">OrderHeader</span></span>
    - <span data-ttu-id="0bd47-111">OrderLine</span><span class="sxs-lookup"><span data-stu-id="0bd47-111">OrderLine</span></span>

<span data-ttu-id="0bd47-112">Le attività di sincronizzazione necessarie prima di sincronizzare righe e intestazione della fattura di vendita:</span><span class="sxs-lookup"><span data-stu-id="0bd47-112">Sync tasks required prior to Sales invoice header and lines sync:</span></span>

- <span data-ttu-id="0bd47-113">Prodotti (da Fin and Ops in Sales)</span><span class="sxs-lookup"><span data-stu-id="0bd47-113">Products (Fin and Ops to Sales)</span></span>
- <span data-ttu-id="0bd47-114">Conti (da Sales in Fin and Ops) (se utilizzata)</span><span class="sxs-lookup"><span data-stu-id="0bd47-114">Accounts (Sales to Fin and Ops) (if used)</span></span>
- <span data-ttu-id="0bd47-115">Da Contatti a Clienti (da Sales in Fin and Ops) (se utilizzata)</span><span class="sxs-lookup"><span data-stu-id="0bd47-115">Contacts to Customers (Sales to Fin and Ops) (if used)</span></span>

## <a name="entity-set"></a><span data-ttu-id="0bd47-116">Insieme di entità</span><span class="sxs-lookup"><span data-stu-id="0bd47-116">Entity set</span></span>

| <span data-ttu-id="0bd47-117">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="0bd47-117">Finance and Operations</span></span> |    <span data-ttu-id="0bd47-118">Common Data Service (CDS)</span><span class="sxs-lookup"><span data-stu-id="0bd47-118">Common Data Service (CDS)</span></span>         |     <span data-ttu-id="0bd47-119">Vendite</span><span class="sxs-lookup"><span data-stu-id="0bd47-119">Sales</span></span>      |
|------------------------|----------------|----------------|
| <span data-ttu-id="0bd47-120">Intestazioni ordine cliente CDS</span><span class="sxs-lookup"><span data-stu-id="0bd47-120">CDS sales order headers</span></span>| <span data-ttu-id="0bd47-121">SalesOrder</span><span class="sxs-lookup"><span data-stu-id="0bd47-121">SalesOrder</span></span>     | <span data-ttu-id="0bd47-122">SalesOrders</span><span class="sxs-lookup"><span data-stu-id="0bd47-122">SalesOrders</span></span> |
| <span data-ttu-id="0bd47-123">Righe ordine cliente CDS</span><span class="sxs-lookup"><span data-stu-id="0bd47-123">CDS sales order lines</span></span>  | <span data-ttu-id="0bd47-124">SalesOrderLine</span><span class="sxs-lookup"><span data-stu-id="0bd47-124">SalesOrderLine</span></span> | <span data-ttu-id="0bd47-125">SalesOrderDetails</span><span class="sxs-lookup"><span data-stu-id="0bd47-125">SalesOrderDetails</span></span>|

## <a name="entity-flow"></a><span data-ttu-id="0bd47-126">Flusso di entità</span><span class="sxs-lookup"><span data-stu-id="0bd47-126">Entity flow</span></span>

<span data-ttu-id="0bd47-127">Gli ordini cliente vengono creati in Finance and Operations e sincronizzati in Sales.</span><span class="sxs-lookup"><span data-stu-id="0bd47-127">Sales orders are created in Finance and Operations and synchronized to Sales.</span></span>

<span data-ttu-id="0bd47-128">I filtri nel modello garantiscono che solo gli ordini cliente pertinenti sono inclusi nella sincronizzazione:</span><span class="sxs-lookup"><span data-stu-id="0bd47-128">Filters in the template ensure that only relevant sales orders are included in the synchronization:</span></span>

- <span data-ttu-id="0bd47-129">Il cliente che richiede l'ordine e quello che emette la fattura indicati nell'ordine cliente generato in Sales saranno inclusi nella sincronizzazione.</span><span class="sxs-lookup"><span data-stu-id="0bd47-129">Both ordering and invoicing customer on the sales order that originate from Sales will be included in the synchronization.</span></span> <span data-ttu-id="0bd47-130">In Finance and Operations, i campi **OrderingCustomerIsExternallyMaintained** e **InvoiceCustomerIsExternallyMaintained** sono utilizzati per tenere traccia della sincronizzazione nelle entità di dati.</span><span class="sxs-lookup"><span data-stu-id="0bd47-130">In Finance and Operations, the fields **OrderingCustomerIsExternallyMaintained** and **InvoiceCustomerIsExternallyMaintained** are used to track the synchronization in the data entities.</span></span>

- <span data-ttu-id="0bd47-131">L'**ordine cliente** in Finance and Operations deve essere confermato.</span><span class="sxs-lookup"><span data-stu-id="0bd47-131">The **Sales order** in Finance and Operations must be confirmed.</span></span> <span data-ttu-id="0bd47-132">Solo gli ordini cliente confermati o gli ordini cliente con stato di elaborazione più elevato, ad esempio Inviato o Fatturato vengono sincronizzati in Sales.</span><span class="sxs-lookup"><span data-stu-id="0bd47-132">Only the confirmed sales orders or sales orders with higher processing status, for example, Shipped or Invoiced status, are synchronized to Sales.</span></span>

- <span data-ttu-id="0bd47-133">Dopo la creazione o la modifica di un ordine cliente, è necessario eseguire il processo batch **Calcola totali vendite** in Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="0bd47-133">After creating or modifying a sales order, the batch job **Calculate sales totals** in Finance and Operations must be executed.</span></span> <span data-ttu-id="0bd47-134">Solo gli ordini cliente con totali delle vendite calcolati verranno sincronizzati in CDS e Sales.</span><span class="sxs-lookup"><span data-stu-id="0bd47-134">Only the sales orders with sales totals calculated will be synced to CDS and Sales.</span></span>

> [!NOTE]
> <span data-ttu-id="0bd47-135">L'imposta relativa alle spese nell'**intestazione dell'ordine cliente** non è attualmente inclusa nella sincronizzazione da Finance and Operations in Sales.</span><span class="sxs-lookup"><span data-stu-id="0bd47-135">Tax related to charges on the **Sales order header** is currently not included in synchronization from Finance and Operations to Sales.</span></span> <span data-ttu-id="0bd47-136">Questo perché Sales non supporta le informazioni fiscali a livello di intestazione.</span><span class="sxs-lookup"><span data-stu-id="0bd47-136">This is because Sales doesn't support tax information at the header level.</span></span> <span data-ttu-id="0bd47-137">È inclusa l'imposta relativa alle spese a livello di riga.</span><span class="sxs-lookup"><span data-stu-id="0bd47-137">Tax related to charges at the line level is included.</span></span>

## <a name="prospect-to-cash-solution-for-sales"></a><span data-ttu-id="0bd47-138">Soluzione Prospect to cash per Sales</span><span class="sxs-lookup"><span data-stu-id="0bd47-138">Prospect to cash solution for Sales</span></span>

<span data-ttu-id="0bd47-139">Nuovi campi sono stati aggiunti all'entità **Ordine** e visualizzati nella pagina:</span><span class="sxs-lookup"><span data-stu-id="0bd47-139">New fields are added to the **Order** entity and displayed on the page:</span></span>

- <span data-ttu-id="0bd47-140">**È gestito esternamente**: impostare su **Sì** se l'ordine proviene da Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="0bd47-140">**Is Maintained Externally** - Set to **Yes** when the order is coming from Finance and Operations.</span></span>

- <span data-ttu-id="0bd47-141">**Stato elaborazione**: utilizzato per visualizzare lo stato di elaborazione dell'ordine in Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="0bd47-141">**Processing status** - Used to show the processing status of the order in Finance and Operations.</span></span> <span data-ttu-id="0bd47-142">I valori sono:</span><span class="sxs-lookup"><span data-stu-id="0bd47-142">Values are:</span></span>

    - <span data-ttu-id="0bd47-143">Attive</span><span class="sxs-lookup"><span data-stu-id="0bd47-143">Active</span></span>
    - <span data-ttu-id="0bd47-144">Confermata</span><span class="sxs-lookup"><span data-stu-id="0bd47-144">Confirmed</span></span>
    - <span data-ttu-id="0bd47-145">Documento di trasporto</span><span class="sxs-lookup"><span data-stu-id="0bd47-145">Packing Slip</span></span>
    - <span data-ttu-id="0bd47-146">Fatturate</span><span class="sxs-lookup"><span data-stu-id="0bd47-146">Invoiced</span></span>
    - <span data-ttu-id="0bd47-147">Prelevato</span><span class="sxs-lookup"><span data-stu-id="0bd47-147">Picked</span></span>
    - <span data-ttu-id="0bd47-148">Prelevato in parte</span><span class="sxs-lookup"><span data-stu-id="0bd47-148">Partially Picked</span></span>
    - <span data-ttu-id="0bd47-149">Parzialmente imballato</span><span class="sxs-lookup"><span data-stu-id="0bd47-149">Partially Packed</span></span>
    - <span data-ttu-id="0bd47-150">Spedito</span><span class="sxs-lookup"><span data-stu-id="0bd47-150">Shipped</span></span>
    - <span data-ttu-id="0bd47-151">Parzialmente spedito</span><span class="sxs-lookup"><span data-stu-id="0bd47-151">Partially Shipped</span></span>
    - <span data-ttu-id="0bd47-152">Parzialmente fatturato</span><span class="sxs-lookup"><span data-stu-id="0bd47-152">Partially Invoiced</span></span>
    - <span data-ttu-id="0bd47-153">Operazione annullata</span><span class="sxs-lookup"><span data-stu-id="0bd47-153">Cancelled</span></span>

<span data-ttu-id="0bd47-154">L'impostazione **Ha solo prodotti gestiti esternamente** viene utilizzata in altri scenari (sincronizzazione da Sales in Finance and Operation) per determinare se l'ordine cliente è composto interamente di **prodotti gestiti esternamente**, nel qual caso i prodotti vengono gestiti in Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="0bd47-154">The **Has Externally Maintained Products Only** setting is used in other sales order scenarios (from Sales to Finance and Operation sync) to consistently keep track of whether the sales order is made up entirely of **Externally Maintained Products**, in which case products are maintained in Finance and Operations.</span></span> <span data-ttu-id="0bd47-155">In questo modo, si impedisce la sincronizzazione delle righe degli ordini cliente con prodotti sconosciuti in Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="0bd47-155">This ensures that you don't try to sync sales order lines with products that are unknown to Finance and Operations.</span></span>
 
<span data-ttu-id="0bd47-156">I pulsanti **Crea fattura**, **Annulla ordine**, **Ricalcola**, **Ottieni prodotti** e **Cerca indirizzo** della pagina **Ordine cliente** sono nascosti per gli ordini gestiti esternamente poiché le fatture verranno create in Finance and Operations e sincronizzate in Sales.</span><span class="sxs-lookup"><span data-stu-id="0bd47-156">The **Create Invoice**, **Cancel Order**, **Recalculate**, **Get Products** and **Lookup Address** buttons on the **Sales order** page are hidden for externally maintained orders because invoices will be created in Finance and Operations and synced to Sales.</span></span> <span data-ttu-id="0bd47-157">La pagina dell'ordine non è modificabile poiché le informazioni dell'ordine cliente verranno sincronizzate da Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="0bd47-157">The order page is non-editable because sales order information will be synced from Finance and Operations.</span></span>
 
<span data-ttu-id="0bd47-158">Lo **stato dell'ordine cliente** rimarrà attivo per garantire che le modifiche da Finance and Operations possano essere applicate all'**ordine cliente** in Sales.</span><span class="sxs-lookup"><span data-stu-id="0bd47-158">The **Sales order status** will remain active to ensure that changes from Finance and Operations can flow to the **Sales order** in Sales.</span></span> <span data-ttu-id="0bd47-159">Questo comportamento viene definito impostando il **codice di stato [stato]** su **Attivo** nel progetto di integrazione dei dati.</span><span class="sxs-lookup"><span data-stu-id="0bd47-159">This is controlled by setting the default **Statecode [Status]** to **Active** in the Data integration project.</span></span>

## <a name="preconditions-and-mapping-setup"></a><span data-ttu-id="0bd47-160">Prerequisiti e impostazioni di mapping</span><span class="sxs-lookup"><span data-stu-id="0bd47-160">Preconditions and mapping setup</span></span> 

<span data-ttu-id="0bd47-161">Prima di sincronizzare gli ordini cliente, è importante aggiornare i sistemi con la seguente impostazione:</span><span class="sxs-lookup"><span data-stu-id="0bd47-161">Before synchronizing sales orders, it is important to update the systems with the following setting:</span></span>

### <a name="setup-in-sales"></a><span data-ttu-id="0bd47-162">Impostazione in Sales</span><span class="sxs-lookup"><span data-stu-id="0bd47-162">Setup in Sales</span></span>

- <span data-ttu-id="0bd47-163">Verificare le autorizzazioni per il team a cui l'utente viene assegnato (dal **set di connessione** in Sales).</span><span class="sxs-lookup"><span data-stu-id="0bd47-163">Ensure permissions for the team that the user (from your Sales **Connection set**) is assigned to.</span></span> <span data-ttu-id="0bd47-164">Se si utilizzano dati dimostrativi, in genere l'utente ha privilegi di amministratore, ma non il team.</span><span class="sxs-lookup"><span data-stu-id="0bd47-164">If you are using demo data, usually the user has admin access, but not the team.</span></span> <span data-ttu-id="0bd47-165">In tal caso, viene visualizzato un messaggio di errore indicante che il team principale è mancante quando si esegue il progetto dall'integratore di dati.</span><span class="sxs-lookup"><span data-stu-id="0bd47-165">Without this you will get an error that Principal team is missing when running the project from Data integrator.</span></span> 

    - <span data-ttu-id="0bd47-166">In **Impostazioni** > **Sicurezza** > **Team**, selezionare il team pertinente, fare clic su **Gestisci ruoli** e selezionare un ruolo con le autorizzazioni desiderate, ad esempio Amministratore di sistema.</span><span class="sxs-lookup"><span data-stu-id="0bd47-166">Under **Settings** > **Security** > **Teams**, select the relevant team, click **Manage Roles** and select a role with the desired permissions e.g. System Administrator.</span></span>

- <span data-ttu-id="0bd47-167">In **Impostazioni** > **Amministrazione** > **Impostazioni di sistema** > **Vendite**, verificare che **Usa sistema di calcolo prezzi sistema** sia impostato su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="0bd47-167">Under **Settings** > **Administration** > **System settings** > **Sales**, ensure that **Use system prizing calculation system** is set to **Yes**.</span></span> 

- <span data-ttu-id="0bd47-168">In **Impostazioni** > **Amministrazione** > **Impostazioni di sistema** > **Vendite**, verificare che **Metodo di calcolo sconto** sia impostato su **Voce**.</span><span class="sxs-lookup"><span data-stu-id="0bd47-168">Under **Settings** > **Administration** > **System settings** > **Sales**, ensure that **Discount calculation method** is set to **Line item**.</span></span> 

### <a name="setup-in-finance-and-operations"></a><span data-ttu-id="0bd47-169">Impostazione in Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="0bd47-169">Setup in Finance and Operations</span></span>

<span data-ttu-id="0bd47-170">Impostare **Vendite e marketing** > **Attività periodiche** > **Calcola totali vendite** per l'esecuzione come processo batch con **Calcola totali per ordini cliente** impostato su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="0bd47-170">Set **Sales and marketing** > **Periodic tasks** > **Calculate sales totals** to run as a batch job, with **Calculate totals for sales orders** set to **Yes**.</span></span> <span data-ttu-id="0bd47-171">Cio è importante perché solo gli ordini cliente con totali vendite calcolati verranno sincronizzati in CDS e Sales.</span><span class="sxs-lookup"><span data-stu-id="0bd47-171">This is important because only the sales orders with sales totals calculated will be synced to CDS and Sales.</span></span> <span data-ttu-id="0bd47-172">La frequenza del processo batch deve essere in linea con la frequenza della sincronizzazione dell'ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="0bd47-172">The frequency of the batch job should be alligned with the frequency of the sales order synchronization.</span></span>

### <a name="setup-in-the-data-integration-project"></a><span data-ttu-id="0bd47-173">Impostazione nel progetto di Integrazione dati</span><span class="sxs-lookup"><span data-stu-id="0bd47-173">Setup in the Data integration project</span></span>

#### <a name="salesheader-task"></a><span data-ttu-id="0bd47-174">Attività SalesHeader</span><span class="sxs-lookup"><span data-stu-id="0bd47-174">SalesHeader task</span></span>

- <span data-ttu-id="0bd47-175">Aggiornare il mapping per **ID organizzazione CDS in Origine** > **CDS**.</span><span class="sxs-lookup"><span data-stu-id="0bd47-175">Update the mapping for **CDS Organization ID in Source** > **CDS**.</span></span>

    - <span data-ttu-id="0bd47-176">Il valore del modello predefinito per **Account_Organization_OrganizationId** è ORG001.</span><span class="sxs-lookup"><span data-stu-id="0bd47-176">Default template value for **Account_Organization_OrganizationId** is ORG001.</span></span>
    - <span data-ttu-id="0bd47-177">Il valore del modello predefinito per **Account_Organization_OrganizationId** è ORG001.</span><span class="sxs-lookup"><span data-stu-id="0bd47-177">Default template value for **InvoiceAccount_Organization_OrganizationId** is ORG001.</span></span>
    - <span data-ttu-id="0bd47-178">Il valore del modello predefinito per **Organization_OrganizationId** è ORG001.</span><span class="sxs-lookup"><span data-stu-id="0bd47-178">Default template value for **Organization_OrganizationId** is ORG001.</span></span>

- <span data-ttu-id="0bd47-179">Verificare che il mapping necessario esista in **Origine** > **CDS per InvoiceCountryRegionId a BillingAddress_Country** e per **DeliveryCountryRegionId a DeliveryAddress_Country**.</span><span class="sxs-lookup"><span data-stu-id="0bd47-179">Ensure that the needed mapping exists in **Source** > **CDS for InvoiceCountryRegionId to BillingAddress_Country** and for **DeliveryCountryRegionId to DeliveryAddress_Country**.</span></span>

    - <span data-ttu-id="0bd47-180">Il valore del modello è **ValueMap** con un numero di paesi mappati.</span><span class="sxs-lookup"><span data-stu-id="0bd47-180">Template value is **ValueMap** with a number of countries mapped.</span></span>

- <span data-ttu-id="0bd47-181">Il **listino prezzi** è necessario per creare ordini in Sales.</span><span class="sxs-lookup"><span data-stu-id="0bd47-181">**Price list** is required to create orders in Sales.</span></span> <span data-ttu-id="0bd47-182">Aggiornare **ValueMap** in **CDS** > **Destinazione** per **pricelevelid.name [nome listino prezzi]** al **listino prezzi** utilizzato in Sales per la valuta.</span><span class="sxs-lookup"><span data-stu-id="0bd47-182">Update the **ValueMap** in **CDS** > **Destination** for **pricelevelid.name [Price List Name]** to the **Price list** used in Sales per currency.</span></span> <span data-ttu-id="0bd47-183">È possibile utilizzare il **listino prezzi** predefinito per una singola valuta oppure **ValueMap** se si hanno **listini prezzi** in molteplici valute.</span><span class="sxs-lookup"><span data-stu-id="0bd47-183">You can either used the default **Price list** for single currency or use **ValueMap** if you have **Price lists** in multiple currencies.</span></span>
    
    - <span data-ttu-id="0bd47-184">Il valore del modello predefinito per **pricelevelid.name [nome listino prezzi]** è Servizio CRM USA (esempio).</span><span class="sxs-lookup"><span data-stu-id="0bd47-184">Default template value for **pricelevelid.name [Price List Name]** is CRM Service USA (sample).</span></span> 

#### <a name="salesline-task"></a><span data-ttu-id="0bd47-185">Attività SalesLine</span><span class="sxs-lookup"><span data-stu-id="0bd47-185">SalesLine task</span></span>

- <span data-ttu-id="0bd47-186">Aggiornare il mapping per **ID organizzazione CDS in Origine** > **CDS**.</span><span class="sxs-lookup"><span data-stu-id="0bd47-186">Update the mapping for **CDS Organization ID in Source** > **CDS**.</span></span> 
    
    - <span data-ttu-id="0bd47-187">Il valore del modello predefinito per **SalesOrder_Organization_OrganizationId** è ORG001.</span><span class="sxs-lookup"><span data-stu-id="0bd47-187">Default template value for **SalesOrder_Organization_OrganizationId** is ORG001.</span></span>
    - <span data-ttu-id="0bd47-188">Il valore del modello predefinito per **Product_Organization_OrganizationId** è ORG001.</span><span class="sxs-lookup"><span data-stu-id="0bd47-188">Default template value for **Product_Organization_OrganizationId** is ORG001.</span></span>

- <span data-ttu-id="0bd47-189">Verificare che il mapping necessario esista in **Origine** > **CDS** per **DeliveryCountryRegionId** a **DeliveryAddress_Country**.</span><span class="sxs-lookup"><span data-stu-id="0bd47-189">Ensure that the needed mapping exists in **Source** > **CDS** for **DeliveryCountryRegionId** to **DeliveryAddress_Country**.</span></span>

    - <span data-ttu-id="0bd47-190">Il valore del modello è **ValueMap** con un numero di paesi mappati.</span><span class="sxs-lookup"><span data-stu-id="0bd47-190">Template value is **ValueMap** with a number of countries mapped.</span></span>
    
- <span data-ttu-id="0bd47-191">Assicurarsi che **ValueMap** per **SalesUnitSymbol** in Finance and Operations sia presente in **Origine** > **Mapping CDS**.</span><span class="sxs-lookup"><span data-stu-id="0bd47-191">Ensure that the needed **ValueMap** for **SalesUnitSymbol** in Finance and Operations exists in the **Source** > **CDS mapping**.</span></span>

    - <span data-ttu-id="0bd47-192">Il valore del modello con **ValueMap** è definito per **SalesUnitSymbol a Quantity_UOM**.</span><span class="sxs-lookup"><span data-stu-id="0bd47-192">Template value with **ValueMap** is defined for **SalesUnitSymbol to Quantity_UOM**.</span></span>

## <a name="template-mapping-in-data-integrator"></a><span data-ttu-id="0bd47-193">Mapping dei modelli nell'integratore di dati</span><span class="sxs-lookup"><span data-stu-id="0bd47-193">Template mapping in data integrator</span></span>

> [!NOTE]
> <span data-ttu-id="0bd47-194">I campi **Termini di pagamento**, **Termini di trasporto**, **Termini di consegna**, **Metodo di spedizione** e **Modalità di consegna** non sono inclusi nei mapping predefiniti.</span><span class="sxs-lookup"><span data-stu-id="0bd47-194">The **Payment terms**, **Freight terms**, **Delivery terms**, **Shipping method**, and **Delivery mode** fields aren't part of the default mappings.</span></span> <span data-ttu-id="0bd47-195">Per mappare questi campi, è necessario impostare un mapping di valori che sia specifico ai dati delle organizzazioni tra cui l'entità viene sincronizzata.</span><span class="sxs-lookup"><span data-stu-id="0bd47-195">To map these fields, you must set up a value mapping that is specific to the data in the organizations that the entity is synchronized between.</span></span>

<span data-ttu-id="0bd47-196">Nelle figure seguenti viene illustrato un esempio di un modello di mapping nell'integratore di dati.</span><span class="sxs-lookup"><span data-stu-id="0bd47-196">The following illustrations show an example of a template mapping in data integrator.</span></span>

### <a name="orderheader"></a><span data-ttu-id="0bd47-197">OrderHeader</span><span class="sxs-lookup"><span data-stu-id="0bd47-197">OrderHeader</span></span>

![Mapping dei modelli nell'integratore di dati](./media/sales-order-template-mapping-data-integrator-1.png)

![Mapping dei modelli nell'integratore di dati](./media/sales-order-template-mapping-data-integrator-2.png)

### <a name="orderline"></a><span data-ttu-id="0bd47-200">OrderLine</span><span class="sxs-lookup"><span data-stu-id="0bd47-200">OrderLine</span></span>

![Mapping dei modelli nell'integratore di dati](./media/sales-order-template-mapping-data-integrator-3.png)

![Mapping dei modelli nell'integratore di dati](./media/sales-order-template-mapping-data-integrator-4.png)


## <a name="related-topics"></a><span data-ttu-id="0bd47-203">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="0bd47-203">Related topics</span></span>

[<span data-ttu-id="0bd47-204">Sincronizzare i prodotti da Finance and Operations ai prodotti in Sales</span><span class="sxs-lookup"><span data-stu-id="0bd47-204">Synchronize products from Finance and Operations to products in Sales</span></span>](products-template-mapping.md)

[<span data-ttu-id="0bd47-205">Sincronizzare conti da Sales con clienti in Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="0bd47-205">Synchronize accounts from Sales to customers in Finance and Operations</span></span>](accounts-template-mapping.md)

[<span data-ttu-id="0bd47-206">Sincronizzare contatti da Sales con contatti o clienti in Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="0bd47-206">Synchronize contacts from Sales to contacts or customers in Finance and Operations</span></span>](contacts-template-mapping.md)

[<span data-ttu-id="0bd47-207">Sincronizzare intestazioni e righe di offerte di vendita da Sales in Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="0bd47-207">Synchronize sales quotation headers and lines from Sales to Finance and Operations</span></span>](sales-quotation-template-mapping.md)

[<span data-ttu-id="0bd47-208">Sincronizzare intestazioni e righe di fatture di vendita da Finance and Operations in Sales</span><span class="sxs-lookup"><span data-stu-id="0bd47-208">Synchronize sales invoice headers and lines from Finance and Operations to Sales</span></span>](sales-invoice-template-mapping.md)


