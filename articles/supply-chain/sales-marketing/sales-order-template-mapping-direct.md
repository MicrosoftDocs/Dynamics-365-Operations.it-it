---
title: Sincronizzare intestazioni e righe di ordini cliente direttamente da Finance and Operations in Sales
description: "Questo argomento descrive i modelli e le attività sottostanti che vengono utilizzati per sincronizzare le righe e le intestazioni degli ordini cliente direttamente da Microsoft Dynamics 365 for Finance and Operations, Enterprise edition in Microsoft Dynamics 365 for Sales."
author: ChristianRytt
manager: AnnBe
ms.date: 10/25/2017
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
ms.openlocfilehash: cc0be50552ae680ba5291e72b7c482ee67e1e70e
ms.contentlocale: it-it
ms.lasthandoff: 11/03/2017

---

# <a name="synchronize-sales-order-headers-and-lines-directly-from-finance-and-operations-to-sales"></a><span data-ttu-id="22fe8-103">Sincronizzare intestazioni e righe di ordini cliente direttamente da Finance and Operations in Sales</span><span class="sxs-lookup"><span data-stu-id="22fe8-103">Synchronize sales order headers and lines directly from Finance and Operations to Sales</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="22fe8-104">Questo argomento descrive i modelli e le attività sottostanti che vengono utilizzati per sincronizzare le righe e le intestazioni degli ordini cliente direttamente da Microsoft Dynamics 365 for Finance and Operations, Enterprise edition in Microsoft Dynamics 365 for Sales.</span><span class="sxs-lookup"><span data-stu-id="22fe8-104">This topic discusses the templates and underlying tasks that are used to synchronize sales order headers and lines directly from Microsoft Dynamics 365 for Finance and Operations, Enterprise edition, to Microsoft Dynamics 365 for Sales.</span></span>

## <a name="data-flow-in-prospect-to-cash"></a><span data-ttu-id="22fe8-105">Flusso di dati in Prospect to cash</span><span class="sxs-lookup"><span data-stu-id="22fe8-105">Data flow in Prospect to cash</span></span>

<span data-ttu-id="22fe8-106">La soluzione Prospect to cash utilizza la funzionalità Integrazione dati per sincronizzare i dati tra istanze di Finance and Operations e Sales.</span><span class="sxs-lookup"><span data-stu-id="22fe8-106">The Prospect to cash solution uses the Data integration feature to synchronize data across instances of Finance and Operations and Sales.</span></span> <span data-ttu-id="22fe8-107">I modelli Prospect to cash disponibili con la funzionalità Integrazione dati consentono il flusso di dati relativo a conti, contatti, prodotti, offerte di vendita, ordini cliente e fatture di vendita tra Finance and Operations e Sales.</span><span class="sxs-lookup"><span data-stu-id="22fe8-107">The Prospect to cash templates that are available with the Data integration feature enable the flow of data about accounts, contacts, products, sales quotations, sales orders, and sales invoices between Finance and Operations and Sales.</span></span> <span data-ttu-id="22fe8-108">La figura seguente mostra il modo in cui i dati vengono sincronizzati tra Finance and Operations e Sales.</span><span class="sxs-lookup"><span data-stu-id="22fe8-108">The following illustration shows how the data is synchronized between Finance and Operations and Sales.</span></span>

<span data-ttu-id="22fe8-109">[![Flusso di dati in Prospect to cash](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)</span><span class="sxs-lookup"><span data-stu-id="22fe8-109">[![Data flow in Prospect to cash](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="22fe8-110">Modelli e attività</span><span class="sxs-lookup"><span data-stu-id="22fe8-110">Templates and tasks</span></span>

<span data-ttu-id="22fe8-111">Per accedere ai modelli disponibili, aprire l'[Interfaccia di amministrazione di PowerApps](https://preview.admin.powerapps.com/dataintegration).</span><span class="sxs-lookup"><span data-stu-id="22fe8-111">To access the available templates, open [PowerApps Admin Center](https://preview.admin.powerapps.com/dataintegration).</span></span> <span data-ttu-id="22fe8-112">Selezionare **Progetti**, quindi nell'angolo superiore destro, selezionare **Nuovo progetto** per selezionare i modelli pubblici.</span><span class="sxs-lookup"><span data-stu-id="22fe8-112">Select **Projects**, and then, in the upper-right corner, select **New project** to select public templates.</span></span>

<span data-ttu-id="22fe8-113">I seguenti modelli e attività sottostanti vengono utilizzati per sincronizzare le intestazioni e le righe degli ordini cliente da Finance and Operations in Sales:</span><span class="sxs-lookup"><span data-stu-id="22fe8-113">The following template and underlying tasks are used to synchronize sales order headers and lines from Finance and Operations to Sales:</span></span>

- <span data-ttu-id="22fe8-114">**Nome del modello in Integrazione dati:** Ordini cliente (da Fin and Ops in Sales) - Diretto</span><span class="sxs-lookup"><span data-stu-id="22fe8-114">**Name of the template in Data integration:** Sales Orders (Fin and Ops to Sales) - Direct</span></span>
- <span data-ttu-id="22fe8-115">**Nomi delle attività nel progetto di Integrazione dati:**</span><span class="sxs-lookup"><span data-stu-id="22fe8-115">**Names of the tasks in the Data integration project:**</span></span>

    - <span data-ttu-id="22fe8-116">OrderHeader</span><span class="sxs-lookup"><span data-stu-id="22fe8-116">OrderHeader</span></span>
    - <span data-ttu-id="22fe8-117">OrderLine</span><span class="sxs-lookup"><span data-stu-id="22fe8-117">OrderLine</span></span>

<span data-ttu-id="22fe8-118">Le attività di sincronizzazione seguenti sono necessarie prima di eseguire la sincronizzazione delle intestazioni e delle righe di fatture di vendita:</span><span class="sxs-lookup"><span data-stu-id="22fe8-118">The following synchronization tasks are required before synchronization of sales invoice headers and lines can occur:</span></span>

- <span data-ttu-id="22fe8-119">Prodotti (da Fin and Ops in Sales) - Diretto</span><span class="sxs-lookup"><span data-stu-id="22fe8-119">Products (Fin and Ops to Sales) - Direct</span></span>
- <span data-ttu-id="22fe8-120">Conti (da Sales in Fin and Ops) - Diretto (se utilizzata)</span><span class="sxs-lookup"><span data-stu-id="22fe8-120">Accounts (Sales to Fin and Ops) - Direct (if used)</span></span>
- <span data-ttu-id="22fe8-121">Da Contatti a Clienti (da Sales in Fin and Ops) - Diretto (se utilizzata)</span><span class="sxs-lookup"><span data-stu-id="22fe8-121">Contacts to Customers (Sales to Fin and Ops) - Direct (if used)</span></span>

## <a name="entity-set"></a><span data-ttu-id="22fe8-122">Insieme di entità</span><span class="sxs-lookup"><span data-stu-id="22fe8-122">Entity set</span></span>

| <span data-ttu-id="22fe8-123">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="22fe8-123">Finance and Operations</span></span>  | <span data-ttu-id="22fe8-124">Vendite</span><span class="sxs-lookup"><span data-stu-id="22fe8-124">Sales</span></span>             |
|-------------------------|-------------------|
| <span data-ttu-id="22fe8-125">Intestazioni ordine cliente CDS</span><span class="sxs-lookup"><span data-stu-id="22fe8-125">CDS sales order headers</span></span> | <span data-ttu-id="22fe8-126">SalesOrders</span><span class="sxs-lookup"><span data-stu-id="22fe8-126">SalesOrders</span></span>       |
| <span data-ttu-id="22fe8-127">Righe ordine cliente CDS</span><span class="sxs-lookup"><span data-stu-id="22fe8-127">CDS sales order lines</span></span>   | <span data-ttu-id="22fe8-128">SalesOrderDetails</span><span class="sxs-lookup"><span data-stu-id="22fe8-128">SalesOrderDetails</span></span> |

## <a name="entity-flow"></a><span data-ttu-id="22fe8-129">Flusso di entità</span><span class="sxs-lookup"><span data-stu-id="22fe8-129">Entity flow</span></span>

<span data-ttu-id="22fe8-130">Gli ordini cliente vengono creati in Finance and Operations e sincronizzati in Sales.</span><span class="sxs-lookup"><span data-stu-id="22fe8-130">Sales orders are created in Finance and Operations and synchronized to Sales.</span></span>

<span data-ttu-id="22fe8-131">I filtri nel modello garantiscono che solo gli ordini cliente pertinenti sono inclusi nella sincronizzazione:</span><span class="sxs-lookup"><span data-stu-id="22fe8-131">Filters in the template help guarantee that only relevant sales orders are included in the synchronization:</span></span>

- <span data-ttu-id="22fe8-132">Nell'ordine cliente, il cliente che richiede l'ordine e quello che emette la fattura originati da Sales saranno inclusi nella sincronizzazione.</span><span class="sxs-lookup"><span data-stu-id="22fe8-132">On the sales order, both the ordering customer and the invoicing customer that originate from Sales will be included in the synchronization.</span></span> <span data-ttu-id="22fe8-133">In Finance and Operations, i campi **OrderingCustomerIsExternallyMaintained** e **InvoiceCustomerIsExternallyMaintained** sono utilizzati per tenere traccia della sincronizzazione nelle entità di dati.</span><span class="sxs-lookup"><span data-stu-id="22fe8-133">In Finance and Operations, the **OrderingCustomerIsExternallyMaintained** and **InvoiceCustomerIsExternallyMaintained** fields are used to track the synchronization in the data entities.</span></span>
- <span data-ttu-id="22fe8-134">L'ordine cliente in Finance and Operations deve essere confermato.</span><span class="sxs-lookup"><span data-stu-id="22fe8-134">The sales order in Finance and Operations must be confirmed.</span></span> <span data-ttu-id="22fe8-135">Solo gli ordini cliente confermati o gli ordini cliente con stato di elaborazione più elevato, ad esempio **Inviato** o **Fatturato** vengono sincronizzati in Sales.</span><span class="sxs-lookup"><span data-stu-id="22fe8-135">Only confirmed sales orders or sales orders that have a higher processing status, such as **Shipped** or **Invoiced**, are synchronized to Sales.</span></span>
- <span data-ttu-id="22fe8-136">Dopo la creazione o la modifica di un ordine cliente, è necessario eseguire il processo batch **Calcola totali vendite** in Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="22fe8-136">After a sales order is created or modified, the **Calculate sales totals** batch job in Finance and Operations must be run.</span></span> <span data-ttu-id="22fe8-137">Solo gli ordini cliente in cui vengono calcolati i totali delle vendite saranno sincronizzati in Sales.</span><span class="sxs-lookup"><span data-stu-id="22fe8-137">Only sales orders where sales totals are calculated will be synchronized to Sales.</span></span>

> [!NOTE]
> <span data-ttu-id="22fe8-138">L'imposta relativa alle spese nell'intestazione dell'ordine cliente non è attualmente inclusa nella sincronizzazione da Finance and Operations in Sales.</span><span class="sxs-lookup"><span data-stu-id="22fe8-138">Currently, tax that is related to charges on the sales order header isn't included in the synchronization from Finance and Operations to Sales.</span></span> <span data-ttu-id="22fe8-139">Sales non supporta le informazioni fiscali a livello di intestazione.</span><span class="sxs-lookup"><span data-stu-id="22fe8-139">Sales doesn't support tax information at the header level.</span></span> <span data-ttu-id="22fe8-140">Tuttavia, l'imposta relativa alle spese a livello di riga è inclusa nella sincronizzazione.</span><span class="sxs-lookup"><span data-stu-id="22fe8-140">However, tax that is related to charges at the line level is included in the synchronization.</span></span>

## <a name="prospect-to-cash-solution-for-sales"></a><span data-ttu-id="22fe8-141">Soluzione Prospect to cash per Sales</span><span class="sxs-lookup"><span data-stu-id="22fe8-141">Prospect to cash solution for Sales</span></span>

<span data-ttu-id="22fe8-142">Nuovi campi sono stati aggiunti all'entità **Ordine** e visualizzati nella pagina:</span><span class="sxs-lookup"><span data-stu-id="22fe8-142">New fields have been added to the **Order** entity and appear on the page:</span></span>

- <span data-ttu-id="22fe8-143">**Gestito esternamente** - Impostare questa opzione su **Sì** se l'ordine proviene da Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="22fe8-143">**Is Maintained Externally** – Set this option to **Yes** when the order is coming from Finance and Operations.</span></span>
- <span data-ttu-id="22fe8-144">**Stato elaborazione** - Questo campo mostra lo stato di elaborazione dell'ordine in Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="22fe8-144">**Processing status** – This field shows the processing status of the order in Finance and Operations.</span></span> <span data-ttu-id="22fe8-145">Sono disponibili i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="22fe8-145">The following values are available:</span></span>

    - <span data-ttu-id="22fe8-146">Attive</span><span class="sxs-lookup"><span data-stu-id="22fe8-146">Active</span></span>
    - <span data-ttu-id="22fe8-147">Confermata</span><span class="sxs-lookup"><span data-stu-id="22fe8-147">Confirmed</span></span>
    - <span data-ttu-id="22fe8-148">Documento di trasporto</span><span class="sxs-lookup"><span data-stu-id="22fe8-148">Packing Slip</span></span>
    - <span data-ttu-id="22fe8-149">Fatturate</span><span class="sxs-lookup"><span data-stu-id="22fe8-149">Invoiced</span></span>
    - <span data-ttu-id="22fe8-150">Prelevato</span><span class="sxs-lookup"><span data-stu-id="22fe8-150">Picked</span></span>
    - <span data-ttu-id="22fe8-151">Prelevato in parte</span><span class="sxs-lookup"><span data-stu-id="22fe8-151">Partially Picked</span></span>
    - <span data-ttu-id="22fe8-152">Parzialmente imballato</span><span class="sxs-lookup"><span data-stu-id="22fe8-152">Partially Packed</span></span>
    - <span data-ttu-id="22fe8-153">Spedito</span><span class="sxs-lookup"><span data-stu-id="22fe8-153">Shipped</span></span>
    - <span data-ttu-id="22fe8-154">Parzialmente spedito</span><span class="sxs-lookup"><span data-stu-id="22fe8-154">Partially Shipped</span></span>
    - <span data-ttu-id="22fe8-155">Parzialmente fatturato</span><span class="sxs-lookup"><span data-stu-id="22fe8-155">Partially Invoiced</span></span>
    - <span data-ttu-id="22fe8-156">Operazione annullata</span><span class="sxs-lookup"><span data-stu-id="22fe8-156">Cancelled</span></span>

<span data-ttu-id="22fe8-157">L'impostazione **Solo prodotti gestiti esternamente** viene utilizzata in altri scenari per ordini cliente (ad esempio, sincronizzazione da Sales in Finance and Operation) per rilevare in modo coerente se un ordine cliente è composto interamente di prodotti gestiti esternamente.</span><span class="sxs-lookup"><span data-stu-id="22fe8-157">The **Has Externally Maintained Products Only** setting is used in other sales order scenarios (for example, synchronization from Sales to Finance and Operation) to consistently track whether a sales order consists entirely of externally maintained products.</span></span> <span data-ttu-id="22fe8-158">Se un ordine cliente include solo prodotti gestiti esternamente, i prodotti vengono gestiti in Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="22fe8-158">If a sales order consists entirely of externally maintained products, the products are maintained in Finance and Operations.</span></span> <span data-ttu-id="22fe8-159">Questa impostazione impedisce il tentativo di sincronizzare righe dell'ordine cliente che hanno prodotti sconosciuti in Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="22fe8-159">This setting helps guarantee that you don't try to synchronize sales order lines that have products that are unknown to Finance and Operations.</span></span>

<span data-ttu-id="22fe8-160">I pulsanti **Crea fattura**, **Annulla ordine**, **Ricalcola**, **Ottieni prodotti** e **Cerca indirizzo** della pagina **Ordine cliente** sono nascosti per gli ordini gestiti esternamente poiché le fatture verranno create in Finance and Operations e sincronizzate in Sales.</span><span class="sxs-lookup"><span data-stu-id="22fe8-160">The **Create Invoice**, **Cancel Order**, **Recalculate**, **Get Products**, and **Lookup Address** buttons on the **Sales order** page are hidden for externally maintained orders, because invoices will be created in Finance and Operations and synchronized to Sales.</span></span> <span data-ttu-id="22fe8-161">La pagina degli ordini non è modificabile poiché le informazioni dell'ordine cliente verranno sincronizzate da Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="22fe8-161">The order page can't be edited, because sales order information will be synchronized from Finance and Operations.</span></span>

<span data-ttu-id="22fe8-162">Lo stato di un ordine cliente rimarrà **Attivo** per garantire che le modifiche da Finance and Operations possano essere applicate all'ordine cliente in Sales.</span><span class="sxs-lookup"><span data-stu-id="22fe8-162">The status of a sales order will remain **Active** to help guarantee that changes from Finance and Operations can flow to the sales order in Sales.</span></span> <span data-ttu-id="22fe8-163">Per controllare questo comportamento, impostare il valore **Codice stato \[Stato\]** su **Attivo** nel progetto di Integrazione dati.</span><span class="sxs-lookup"><span data-stu-id="22fe8-163">To control this behavior, set the default **Statecode \[Status\]** value to **Active** in the Data integration project.</span></span>

## <a name="preconditions-and-mapping-setup"></a><span data-ttu-id="22fe8-164">Prerequisiti e impostazioni di mapping</span><span class="sxs-lookup"><span data-stu-id="22fe8-164">Preconditions and mapping setup</span></span>

<span data-ttu-id="22fe8-165">Prima di sincronizzare gli ordini cliente, è importante aggiornare le impostazioni seguenti nei sistemi.</span><span class="sxs-lookup"><span data-stu-id="22fe8-165">Before you synchronize sales orders, it's important that you update the following settings in the systems.</span></span>

### <a name="setup-in-sales"></a><span data-ttu-id="22fe8-166">Impostazione in Sales</span><span class="sxs-lookup"><span data-stu-id="22fe8-166">Setup in Sales</span></span>

- <span data-ttu-id="22fe8-167">Assicurarsi che le autorizzazioni siano impostate per il team a cui l'utente dal set di connessione in Sales viene assegnato.</span><span class="sxs-lookup"><span data-stu-id="22fe8-167">Make sure that permissions are set up for the team that the user from your Sales connection set is assigned to.</span></span> <span data-ttu-id="22fe8-168">Se si utilizzano dati dimostrativi, in genere l'utente ha privilegi di amministratore, ma non il team.</span><span class="sxs-lookup"><span data-stu-id="22fe8-168">If you're using demo data, the user usually has admin access, but the team doesn't have admin access.</span></span> <span data-ttu-id="22fe8-169">Se il team non dispone anche di privilegi di amministratore, quando si esegue il progetto da Integrazione dati, verrà visualizzato un messaggio di errore in cui viene indicato che il team principale è mancante.</span><span class="sxs-lookup"><span data-stu-id="22fe8-169">If the team doesn't also have admin access, when you run the project from Data integration, you will receive an error message that states that Principal team is missing.</span></span>

    <span data-ttu-id="22fe8-170">Andare a **Impostazioni** > **Sicurezza** > **Team**, selezionare il team pertinente, selezionare **Gestisci ruoli** e selezionare un ruolo con le autorizzazioni desiderate, ad esempio **Amministratore di sistema**.</span><span class="sxs-lookup"><span data-stu-id="22fe8-170">Go to **Settings** > **Security** > **Teams**, select the relevant team, select **Manage Roles**, and select a role that has the desired permissions, such as **System Administrator**.</span></span>

- <span data-ttu-id="22fe8-171">Andare a **Impostazioni** > **Amministrazione** > **Impostazioni di sistema** > **Vendite** e assicurarsi che:</span><span class="sxs-lookup"><span data-stu-id="22fe8-171">Go to **Settings** > **Administration** > **System settings** > **Sales**, and makes sure that the following settings are used:</span></span>

    - <span data-ttu-id="22fe8-172">L'opzione **Usa sistema di calcolo prezzi sistema** sia impostata su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="22fe8-172">The **Use system prizing calculation system** option is set to **Yes**.</span></span>
    - <span data-ttu-id="22fe8-173">Il campo **Metodo di calcolo sconto** sia impostato su **Voce**.</span><span class="sxs-lookup"><span data-stu-id="22fe8-173">The **Discount calculation method** field is set to **Line item**.</span></span>

### <a name="setup-in-finance-and-operations"></a><span data-ttu-id="22fe8-174">Impostazione in Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="22fe8-174">Setup in Finance and Operations</span></span>

<span data-ttu-id="22fe8-175">Andare a **Vendite e marketing** > **Attività periodiche** > **Calcola totali vendite** e impostare il processo da eseguire come processo batch.</span><span class="sxs-lookup"><span data-stu-id="22fe8-175">Go to **Sales and marketing** > **Periodic tasks** > **Calculate sales totals**, and set the job to run as a batch job.</span></span> <span data-ttu-id="22fe8-176">Impostare l'opzione **Calcola totali per ordini cliente** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="22fe8-176">Set the **Calculate totals for sales orders** option to **Yes**.</span></span> <span data-ttu-id="22fe8-177">Questo passaggio è importante perché solo gli ordini cliente con totali vendite calcolati verranno sincronizzati in Sales.</span><span class="sxs-lookup"><span data-stu-id="22fe8-177">This step is important, because only sales orders where sales totals are calculated will be synchronized to Sales.</span></span> <span data-ttu-id="22fe8-178">La frequenza del processo batch deve essere in linea con la frequenza della sincronizzazione dell'ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="22fe8-178">The frequency of the batch job should be aligned with the frequency of sales order synchronization.</span></span>

### <a name="setup-in-the-data-integration-project"></a><span data-ttu-id="22fe8-179">Impostazione nel progetto di Integrazione dati</span><span class="sxs-lookup"><span data-stu-id="22fe8-179">Setup in the Data integration project</span></span>

#### <a name="salesheader-task"></a><span data-ttu-id="22fe8-180">Attività SalesHeader</span><span class="sxs-lookup"><span data-stu-id="22fe8-180">SalesHeader task</span></span>

- <span data-ttu-id="22fe8-181">Assicurarsi che il mapping necessario esista per **InvoiceCountryRegionId** a **BillingAddress\_Country** e per **DeliveryCountryRegionId** a **DeliveryAddress\_Country**.</span><span class="sxs-lookup"><span data-stu-id="22fe8-181">Make sure that the required mapping exists for **InvoiceCountryRegionId** to **BillingAddress\_Country** and for **DeliveryCountryRegionId** to **DeliveryAddress\_Country**.</span></span>

    <span data-ttu-id="22fe8-182">Il valore di modello è una mappa di valori dove vari paesi sono mappati.</span><span class="sxs-lookup"><span data-stu-id="22fe8-182">The template value is a value map where several countries or regions are mapped.</span></span>

- <span data-ttu-id="22fe8-183">Un listino prezzi è necessario per creare ordini in Sales.</span><span class="sxs-lookup"><span data-stu-id="22fe8-183">A price list is required in order to create orders in Sales.</span></span> <span data-ttu-id="22fe8-184">Aggiornare la mappa di valori per **pricelevelid.name \[nome listino prezzi\]** al listino prezzi utilizzato in Sales per la valuta.</span><span class="sxs-lookup"><span data-stu-id="22fe8-184">Update the value map for **pricelevelid.name \[Price list name\]** to the price list that is used in Sales per currency.</span></span> <span data-ttu-id="22fe8-185">È possibile utilizzare il listino prezzi predefinito per una singola valuta.</span><span class="sxs-lookup"><span data-stu-id="22fe8-185">You can use the default price list for a single currency.</span></span> <span data-ttu-id="22fe8-186">In alternativa, se si hanno listini prezzi in più valute, è possibile utilizzare una mappa di valori.</span><span class="sxs-lookup"><span data-stu-id="22fe8-186">Alternatively, if you have price lists in multiple currencies, you can use a value map.</span></span>

    <span data-ttu-id="22fe8-187">Il valore di modello predefinito per **pricelevelid.name \[nome listino prezzi\]** è **Servizio CRM USA (esempio)**.</span><span class="sxs-lookup"><span data-stu-id="22fe8-187">The default template value for **pricelevelid.name \[Price list name\]** is **CRM Service USA (sample)**.</span></span>

#### <a name="salesline-task"></a><span data-ttu-id="22fe8-188">Attività SalesLine</span><span class="sxs-lookup"><span data-stu-id="22fe8-188">SalesLine task</span></span>

- <span data-ttu-id="22fe8-189">Assicurarsi che il mapping necessario esista per **DeliveryCountryRegionId** a **DeliveryAddress\_Country**.</span><span class="sxs-lookup"><span data-stu-id="22fe8-189">Make sure that the required mapping exists for **DeliveryCountryRegionId** to **DeliveryAddress\_Country**.</span></span>

    <span data-ttu-id="22fe8-190">Il valore di modello è una mappa di valori dove vari paesi sono mappati.</span><span class="sxs-lookup"><span data-stu-id="22fe8-190">The template value is a value map where several countries or regions are mapped.</span></span>

- <span data-ttu-id="22fe8-191">Assicurarsi che la mappa di valori richiesta esista per **SalesUnitSymbol** in Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="22fe8-191">Make sure that the required value map for **SalesUnitSymbol** in Finance and Operations exists.</span></span>

    <span data-ttu-id="22fe8-192">Un valore di modello con una mappa di valori viene definito per **SalesUnitSymbol** a **Quantity\_UOM**.</span><span class="sxs-lookup"><span data-stu-id="22fe8-192">A template value that has a value map is defined for **SalesUnitSymbol** to **Quantity\_UOM**.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="22fe8-193">Mapping dei modelli in Integrazione dati</span><span class="sxs-lookup"><span data-stu-id="22fe8-193">Template mapping in Data integration</span></span>

> [!NOTE]
> <span data-ttu-id="22fe8-194">I campi **Termini di pagamento**, **Termini di trasporto**, **Termini di consegna**, **Metodo di spedizione** e **Modalità di consegna** non vengono inclusi nei mapping predefiniti.</span><span class="sxs-lookup"><span data-stu-id="22fe8-194">The **Payment terms**, **Freight terms**, **Delivery terms**, **Shipping method**, and **Delivery mode** fields aren't included in the default mappings.</span></span> <span data-ttu-id="22fe8-195">Per mappare questi campi, è necessario impostare un mapping di valori che sia specifico ai dati delle organizzazioni tra cui l'entità viene sincronizzata.</span><span class="sxs-lookup"><span data-stu-id="22fe8-195">To map these fields, you must set up a value mapping that is specific to the data in the organizations that the entity is synchronized between.</span></span>

<span data-ttu-id="22fe8-196">Nelle figure seguenti viene illustrato un esempio di mapping di modelli in Integrazione dati.</span><span class="sxs-lookup"><span data-stu-id="22fe8-196">The following illustrations show an example of a template mapping in Data integration.</span></span> 

> [!NOTE]
> <span data-ttu-id="22fe8-197">Il mapping mostra quali informazioni sui campi verranno sincronizzate da Sales in Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="22fe8-197">The mapping shows which field information will be synchronized from Sales to Finance and Operations.</span></span>

### <a name="orderheader"></a><span data-ttu-id="22fe8-198">OrderHeader</span><span class="sxs-lookup"><span data-stu-id="22fe8-198">OrderHeader</span></span>

![Mapping dei modelli nell'integratore di dati](./media/sales-order-direct-template-mapping-data-integrator-1.png)

### <a name="orderline"></a><span data-ttu-id="22fe8-200">OrderLine</span><span class="sxs-lookup"><span data-stu-id="22fe8-200">OrderLine</span></span>

![Mapping dei modelli nell'integratore di dati](./media/sales-order-direct-template-mapping-data-integrator-2.png)



## <a name="related-topics"></a><span data-ttu-id="22fe8-202">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="22fe8-202">Related topics</span></span>

[<span data-ttu-id="22fe8-203">Prospect to cash</span><span class="sxs-lookup"><span data-stu-id="22fe8-203">Prospect to cash</span></span>](prospect-to-cash.md)

[<span data-ttu-id="22fe8-204">Sincronizzare conti direttamente da Sales con clienti in Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="22fe8-204">Synchronize accounts directly from Sales to customers in Finance and Operations</span></span>](accounts-template-mapping-direct.md)

[<span data-ttu-id="22fe8-205">Sincronizzare prodotti direttamente da Finance and Operations con prodotti in Sales</span><span class="sxs-lookup"><span data-stu-id="22fe8-205">Synchronize products directly from Finance and Operations to products in Sales</span></span>](products-template-mapping-direct.md)

[<span data-ttu-id="22fe8-206">Sincronizzare contatti direttamente da Sales con contatti o clienti in Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="22fe8-206">Synchronize contacts directly from Sales to contacts or customers in Finance and Operations</span></span>](contacts-template-mapping-direct.md)

[<span data-ttu-id="22fe8-207">Sincronizzare intestazioni e righe di fatture di vendita direttamente da Finance and Operations in Sales</span><span class="sxs-lookup"><span data-stu-id="22fe8-207">Synchronize sales invoice headers and lines directly from Finance and Operations to Sales</span></span>](sales-invoice-template-mapping-direct.md)




