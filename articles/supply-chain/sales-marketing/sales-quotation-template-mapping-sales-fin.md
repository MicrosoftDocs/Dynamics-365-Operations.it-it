---
title: Sincronizzare intestazioni e righe di offerte di vendita direttamente da Sales in Supply Chain Management…
description: L'argomento descrive i modelli e le attività sottostanti che vengono utilizzati per sincronizzare le righe e le intestazioni delle offerte di vendita direttamente da Dynamics 365 Sales in Dynamics 365 Supply Chain Management.
author: ChristianRytt
ms.date: 10/25/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: crytt
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.openlocfilehash: 848464cbc62623502b9b87b9b41dcc17150e85ba
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5839007"
---
# <a name="synchronize-sales-quotation-headers-and-lines-directly-from-sales-to-supply-chain-management"></a><span data-ttu-id="0d338-103">Sincronizzare intestazioni e righe di offerte di vendita direttamente da Sales in Supply Chain Management…</span><span class="sxs-lookup"><span data-stu-id="0d338-103">Synchronize sales quotation headers and lines directly from Sales to Supply Chain Management</span></span>

[!include [banner](../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="0d338-104">L'argomento descrive i modelli e le attività sottostanti che vengono utilizzati per sincronizzare le righe e le intestazioni delle offerte di vendita direttamente da Dynamics 365 Sales in Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="0d338-104">The topic discusses the templates and underlying tasks that are used to synchronize sales quotation headers and lines directly from Dynamics 365 Sales to Dynamics 365 Supply Chain Management.</span></span>

> [!NOTE]
> <span data-ttu-id="0d338-105">Prima di utilizzare la soluzione Prospect to cash, è necessario acquisire familiarità con [Integrare i dati in Microsoft Dataverse per le app](https://docs.microsoft.com/powerapps/administrator/data-integrator).</span><span class="sxs-lookup"><span data-stu-id="0d338-105">Before you can use the Prospect to cash solution, you should be familiar with [Integrate data into Microsoft Dataverse for Apps](https://docs.microsoft.com/powerapps/administrator/data-integrator).</span></span>

## <a name="data-flow-in-prospect-to-cash"></a><span data-ttu-id="0d338-106">Flusso di dati in Prospect to cash</span><span class="sxs-lookup"><span data-stu-id="0d338-106">Data flow in Prospect to cash</span></span>

<span data-ttu-id="0d338-107">La soluzione Prospect to cash utilizza la funzionalità Integrazione dati per sincronizzare i dati tra istanze di Supply Chain Management e Sales.</span><span class="sxs-lookup"><span data-stu-id="0d338-107">The Prospect to cash solution uses the Data integration feature to synchronize data across instances of Supply Chain Management and Sales.</span></span> <span data-ttu-id="0d338-108">I modelli Prospect to cash disponibili con la funzionalità Integrazione dati consentono il flusso di dati per conti, contatti, prodotti, offerte di vendita, ordini cliente e fatture di vendita tra Supply Chain Management e Sales.</span><span class="sxs-lookup"><span data-stu-id="0d338-108">The Prospect to cash templates that are available with the Data integration feature enable the flow of data for accounts, contacts, products, sales quotations, sales orders, and sales invoices between Supply Chain Management and Sales.</span></span> <span data-ttu-id="0d338-109">La figura seguente mostra il modo in cui i dati vengono sincronizzati tra Supply Chain Management e Sales.</span><span class="sxs-lookup"><span data-stu-id="0d338-109">The following illustration shows how the data is synchronized between Supply Chain Management and Sales.</span></span>

<span data-ttu-id="0d338-110">[![Flusso di dati in Prospect to cash](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)</span><span class="sxs-lookup"><span data-stu-id="0d338-110">[![Data flow in Prospect to cash](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)</span></span>

## <a name="template-and-tasks"></a><span data-ttu-id="0d338-111">Modello e attività</span><span class="sxs-lookup"><span data-stu-id="0d338-111">Template and tasks</span></span>

<span data-ttu-id="0d338-112">Il seguente modello e le attività sottostanti vengono utilizzati per sincronizzare le intestazioni e le righe delle offerte di vendita direttamente da Sales in Supply Chain Management:</span><span class="sxs-lookup"><span data-stu-id="0d338-112">The following template and underlying tasks are used to synchronize sales quotation headers and lines directly from Sales to Supply Chain Management:</span></span>

- <span data-ttu-id="0d338-113">**Nome del modello in Integrazione dati:** Offerte di vendita (da Sales in Supply Chain Management) - Diretto</span><span class="sxs-lookup"><span data-stu-id="0d338-113">**Name of the template in Data integration:** Sales Quotes (Sales to Supply Chain Management) - Direct</span></span>
- <span data-ttu-id="0d338-114">**Nomi delle attività nel progetto di Integrazione dati:**</span><span class="sxs-lookup"><span data-stu-id="0d338-114">**Names of the tasks in the Data integration project:**</span></span>

    - <span data-ttu-id="0d338-115">QuoteHeader</span><span class="sxs-lookup"><span data-stu-id="0d338-115">QuoteHeader</span></span>
    - <span data-ttu-id="0d338-116">QuoteLine</span><span class="sxs-lookup"><span data-stu-id="0d338-116">QuoteLine</span></span>

<span data-ttu-id="0d338-117">Le attività di sincronizzazione seguenti sono necessarie prima di eseguire la sincronizzazione delle intestazioni e delle righe di un'offerta di vendita:</span><span class="sxs-lookup"><span data-stu-id="0d338-117">The following synchronization tasks are required before synchronization of sales quotation headers and lines can occur:</span></span>

- <span data-ttu-id="0d338-118">Prodotti (da Supply Chain Management in Sales) - Diretto</span><span class="sxs-lookup"><span data-stu-id="0d338-118">Products (Supply Chain Management to Sales) - Direct</span></span>
- <span data-ttu-id="0d338-119">Conti (da Sales in Supply Chain Management) - Diretto (se utilizzato)</span><span class="sxs-lookup"><span data-stu-id="0d338-119">Accounts (Sales to Supply Chain Management) - Direct (if used)</span></span>
- <span data-ttu-id="0d338-120">Da Contatti a Clienti (da Sales in Supply Chain Management) - Diretto (se utilizzato)</span><span class="sxs-lookup"><span data-stu-id="0d338-120">Contacts to Customers (Sales to Supply Chain Management) - Direct (if used)</span></span>

## <a name="entity-set"></a><span data-ttu-id="0d338-121">Insieme di entità</span><span class="sxs-lookup"><span data-stu-id="0d338-121">Entity set</span></span>

| <span data-ttu-id="0d338-122">Vendite</span><span class="sxs-lookup"><span data-stu-id="0d338-122">Sales</span></span>        | <span data-ttu-id="0d338-123">Gestione della supply chain</span><span class="sxs-lookup"><span data-stu-id="0d338-123">Supply Chain Management</span></span>     |
|--------------|----------------------------|
| <span data-ttu-id="0d338-124">Citazioni</span><span class="sxs-lookup"><span data-stu-id="0d338-124">Quotes</span></span>       | <span data-ttu-id="0d338-125">Intestazione offerta di vendita Dataverse</span><span class="sxs-lookup"><span data-stu-id="0d338-125">Dataverse sales quotation header</span></span> |
| <span data-ttu-id="0d338-126">QuoteDetails</span><span class="sxs-lookup"><span data-stu-id="0d338-126">QuoteDetails</span></span> | <span data-ttu-id="0d338-127">Righe di offerta di vendita Dataverse</span><span class="sxs-lookup"><span data-stu-id="0d338-127">Dataverse sales quotation lines</span></span>  |

## <a name="entity-flow"></a><span data-ttu-id="0d338-128">Flusso di entità</span><span class="sxs-lookup"><span data-stu-id="0d338-128">Entity flow</span></span>

<span data-ttu-id="0d338-129">Le offerte di vendita vengono create in Sales e sincronizzate in Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="0d338-129">Sales quotations are created in Sales and synchronized to Supply Chain Management.</span></span>

<span data-ttu-id="0d338-130">Le offerte di vendita da Sales vengono sincronizzate solo se vengono soddisfatte le condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="0d338-130">Sales quotations from Sales are synchronized only if the following conditions are met:</span></span>

- <span data-ttu-id="0d338-131">Tutti i prodotti offerta nelle righe dell'offerta di vendita sono gestiti esternamente.</span><span class="sxs-lookup"><span data-stu-id="0d338-131">All quote products on the sales quotation are externally maintained.</span></span>
- <span data-ttu-id="0d338-132">Dopo aver fatto clic su **Attiva offerta**, l'offerta di vendita è attiva.</span><span class="sxs-lookup"><span data-stu-id="0d338-132">After you click **Activate quote**, the sales quotation is active.</span></span>

## <a name="prospect-to-cash-solution-for-sales"></a><span data-ttu-id="0d338-133">Soluzione Prospect to cash per Sales</span><span class="sxs-lookup"><span data-stu-id="0d338-133">Prospect to cash solution for Sales</span></span>

<span data-ttu-id="0d338-134">È stato aggiunto il campo **Solo prodotti gestiti esternamente** all'entità **Offerta** per rilevare in modo coerente se l'offerta di vendita consiste interamente di prodotti gestiti esternamente.</span><span class="sxs-lookup"><span data-stu-id="0d338-134">The **Has Externally Maintained Products Only** field has been added to the **Quote** entity to consistently track whether the sales quotation consists entirely of externally maintained products.</span></span> <span data-ttu-id="0d338-135">Se un'offerta di vendita include solo prodotti gestiti esternamente, i prodotti vengono gestiti in Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="0d338-135">If a sales quotation has only externally maintained products, the products are maintained in Supply Chain Management.</span></span> <span data-ttu-id="0d338-136">Questo comportamento impedisce il tentativo di sincronizzare righe di offerta di vendita che hanno prodotti sconosciuti in Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="0d338-136">This behavior helps guarantee that you don't try to synchronize sales quotation lines that have products that are unknown to Supply Chain Management.</span></span>

<span data-ttu-id="0d338-137">Tutti i prodotti offerta e l'offerta di vendita vengono aggiornati con le informazioni **Solo prodotti gestiti esternamente** derivate dall'intestazione dell'offerta di vendita.</span><span class="sxs-lookup"><span data-stu-id="0d338-137">All quote products on the sales quotation are updated with the **Has Externally Maintained Products Only** information from the sales quotation header.</span></span> <span data-ttu-id="0d338-138">Queste informazioni sono disponibili nel campo **L'offerta ha solo prodotti gestiti esternamente** nell'entità **QuoteDetails**.</span><span class="sxs-lookup"><span data-stu-id="0d338-138">This information is found in the **Quote Has Externally Maintained Products Only** field on the **QuoteDetails** entity.</span></span>

<span data-ttu-id="0d338-139">Uno sconto può essere aggiunto al prodotto offerta e verrà sincronizzato con Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="0d338-139">A discount can be added to the quote product and will be synchronized to Supply Chain Management.</span></span> <span data-ttu-id="0d338-140">I campi **Sconto**, **Spese** e **Imposta** nell'intestazione sono controllati da un'impostazione in Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="0d338-140">The **Discount**, **Charges**, and **Tax** fields on the header are controlled by a setup in Supply Chain Management.</span></span> <span data-ttu-id="0d338-141">Questa impostazione al momento non supporta il mapping di integrazione.</span><span class="sxs-lookup"><span data-stu-id="0d338-141">Currently, this setup doesn't support integration mapping.</span></span> <span data-ttu-id="0d338-142">Nella progettazione attuale, i campi **Prezzo**, **Sconto**, **Spese** e **Imposta** sono gestiti in Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="0d338-142">In the current design, the **Price**, **Discount**, **Charge**, and **Tax** fields are maintained and handled in FSupply Chain Management.</span></span>

<span data-ttu-id="0d338-143">In Sales, la soluzione rende i campi seguenti di sola lettura, perché i valori non vengono sincronizzati con Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="0d338-143">In Sales, the solution makes the following fields read-only, because the values aren't synchronized to Supply Chain Management:</span></span>

- <span data-ttu-id="0d338-144">Campi di sola lettura nell'intestazione dell'offerta di vendita: **% sconto**, **Sconto**, **Importo trasporto**</span><span class="sxs-lookup"><span data-stu-id="0d338-144">Read-only fields on the sales quotation header: **Discount %**, **Discount**, and **Freight Amount**</span></span>
- <span data-ttu-id="0d338-145">Campi di sola lettura nei prodotti offerta: **Imposta**</span><span class="sxs-lookup"><span data-stu-id="0d338-145">Read-only fields on quote products: **Tax**</span></span>

## <a name="preconditions-and-mapping-setup"></a><span data-ttu-id="0d338-146">Prerequisiti e impostazioni di mapping</span><span class="sxs-lookup"><span data-stu-id="0d338-146">Preconditions and mapping setup</span></span>

<span data-ttu-id="0d338-147">Prima di sincronizzare le offerte di vendita, è importante aggiornare le seguenti impostazioni.</span><span class="sxs-lookup"><span data-stu-id="0d338-147">Before sales quotations are synchronized, it's important that you update the following settings.</span></span>

### <a name="setup-in-sales"></a><span data-ttu-id="0d338-148">Impostazione in Sales</span><span class="sxs-lookup"><span data-stu-id="0d338-148">Setup in Sales</span></span>

- <span data-ttu-id="0d338-149">Assicurarsi che le autorizzazioni siano impostate per il team a cui l'utente nel set di connessione in Sales viene assegnato.</span><span class="sxs-lookup"><span data-stu-id="0d338-149">Make sure that permissions are set up for the team that the user from your connection set in Sales is assigned to.</span></span> <span data-ttu-id="0d338-150">Se si utilizzano dati dimostrativi, in genere l'utente ha privilegi di amministratore, ma non il team.</span><span class="sxs-lookup"><span data-stu-id="0d338-150">If you're using demo data, the user usually has admin access, but the team doesn't have admin access.</span></span> <span data-ttu-id="0d338-151">Se il team non dispone di privilegi di amministratore quando si esegue il progetto da Integrazione dati, verrà visualizzato un messaggio di errore in cui viene indicato che il team principale è mancante.</span><span class="sxs-lookup"><span data-stu-id="0d338-151">If the team doesn't have admin access when you run the project from Data integration, you will receive an error message that states that the Principal team is missing.</span></span>

    <span data-ttu-id="0d338-152">Per impostare le autorizzazioni per il team, andare a **Impostazioni** &gt; **Sicurezza** &gt; **Team** e selezionare il team pertinente.</span><span class="sxs-lookup"><span data-stu-id="0d338-152">To set up permissions for the team, go to **Settings** &gt; **Security** &gt; **Teams**, and select the relevant team.</span></span> <span data-ttu-id="0d338-153">Selezionare **Gestisci ruoli** e quindi selezionare un ruolo che dispone delle autorizzazioni appropriate, ad esempio **Amministratore di sistema**.</span><span class="sxs-lookup"><span data-stu-id="0d338-153">Select **Manage Roles**, and then select a role that has the desired permissions, such as **System Administrator**.</span></span>

- <span data-ttu-id="0d338-154">Andare a **Impostazioni** &gt; **Amministrazione** &gt; **Impostazioni di sistema** &gt; **Vendite** e assicurarsi che:</span><span class="sxs-lookup"><span data-stu-id="0d338-154">Go to **Settings** &gt; **Administration** &gt; **System settings** &gt; **Sales**, and make sure that the following settings are used:</span></span>

    - <span data-ttu-id="0d338-155">L'opzione **Usa sistema di calcolo prezzi sistema** sia impostata su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="0d338-155">The **Use system prizing calculation system** option is set to **Yes**.</span></span>
    - <span data-ttu-id="0d338-156">Il campo **Metodo di calcolo sconto** sia impostato su **Voce**.</span><span class="sxs-lookup"><span data-stu-id="0d338-156">The **Discount calculation method** field is set to **Line item**.</span></span>

### <a name="setup-in-the-data-integration-project"></a><span data-ttu-id="0d338-157">Impostazione nel progetto di Integrazione dati</span><span class="sxs-lookup"><span data-stu-id="0d338-157">Setup in the Data integration project</span></span>

#### <a name="quoteheader"></a><span data-ttu-id="0d338-158">QuoteHeader</span><span class="sxs-lookup"><span data-stu-id="0d338-158">QuoteHeader</span></span>

- <span data-ttu-id="0d338-159">Assicurarsi che il mapping necessario esista per **Shipto\_country** a **DeliveryAddressCountryRegionISOCode**.</span><span class="sxs-lookup"><span data-stu-id="0d338-159">Make sure that the required mapping exists for **Shipto\_country** to **DeliveryAddressCountryRegionISOCode**.</span></span> <span data-ttu-id="0d338-160">Nella mappa di valori, è possibile definire un valore predefinito utilizzato se il valore è vuoto.</span><span class="sxs-lookup"><span data-stu-id="0d338-160">In the value map, you can define a default value that is used if the value is left blank.</span></span> <span data-ttu-id="0d338-161">Lasciare la parte sinistra vuota e impostare la parte destra sul paese desiderato.</span><span class="sxs-lookup"><span data-stu-id="0d338-161">Just leave the left side blank, and set the right side to the desired country or region.</span></span> <span data-ttu-id="0d338-162">In questo modo, non sarà necessario immettere il paese per gli ordini nazionali.</span><span class="sxs-lookup"><span data-stu-id="0d338-162">In this way, you don't have to type the country or region for national orders.</span></span>

    <span data-ttu-id="0d338-163">Il valore di modello è una mappa di valori dove vari paesi vengono mappati e dove un valore vuoto equivale a **Stati Uniti**.</span><span class="sxs-lookup"><span data-stu-id="0d338-163">The template value is a value map where several countries or regions are mapped, and where a blank value equals a value of **US**.</span></span>

#### <a name="quoteline"></a><span data-ttu-id="0d338-164">QuoteLine</span><span class="sxs-lookup"><span data-stu-id="0d338-164">QuoteLine</span></span>

- <span data-ttu-id="0d338-165">Assicurarsi che la mappa valori richiesta esista per **SalesUnitSymbol** in Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="0d338-165">Make sure that the required value map exists for **SalesUnitSymbol** in Supply Chain Management.</span></span>
- <span data-ttu-id="0d338-166">Assicurarsi che le unità richieste siano definite in Sales.</span><span class="sxs-lookup"><span data-stu-id="0d338-166">Make sure that the required units are defined in Sales.</span></span>

    <span data-ttu-id="0d338-167">Un valore di modello con una mappa di valori viene definito per **oumid.name** a **SalesUnitSymbol**.</span><span class="sxs-lookup"><span data-stu-id="0d338-167">A template value that has a value map is defined for **oumid.name** to **SalesUnitSymbol**.</span></span>

- <span data-ttu-id="0d338-168">Facoltativo: è possibile aggiungere i mapping seguenti in modo da garantire che le righe dell'offerta di vendita vengano importate in Supply Chain Management se non sono disponibili informazioni predefinite dal cliente o dal prodotto:</span><span class="sxs-lookup"><span data-stu-id="0d338-168">Optional: You can add the following mappings to help guarantee that sales quotation lines are imported into Supply Chain Management if there is no default information from either the customer or the product:</span></span>

    - <span data-ttu-id="0d338-169">**SiteId** - Un sito è obbligatorio per la generazione di offerte e righe di ordine cliente in Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="0d338-169">**SiteId** – A site is required in order to generate quotations and sales order lines in Supply Chain Management.</span></span> <span data-ttu-id="0d338-170">Non è disponibile alcun valore del modello predefinito per **SiteId**.</span><span class="sxs-lookup"><span data-stu-id="0d338-170">There is no default template value for **SiteId**.</span></span>
    - <span data-ttu-id="0d338-171">**WarehouseId** - Un magazzino è obbligatorio per l'elaborazione di offerte e righe di ordine cliente in Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="0d338-171">**WarehouseId** – A warehouse is required in order to process quotations and sales order lines in Supply Chain Management.</span></span> <span data-ttu-id="0d338-172">Non è disponibile alcun valore del modello predefinito per **WarehouseId**.</span><span class="sxs-lookup"><span data-stu-id="0d338-172">There is no default template value for **WarehouseId**.</span></span>

## <a name="template-mapping-in-data-integrator"></a><span data-ttu-id="0d338-173">Mapping dei modelli nell'integratore di dati</span><span class="sxs-lookup"><span data-stu-id="0d338-173">Template mapping in data integrator</span></span>

> [!NOTE]
> - <span data-ttu-id="0d338-174">I campi **Sconto**, **Spese** e **Imposta** sono controllati da un'impostazione complessa in Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="0d338-174">The **Discount**, **Charges**, and **Tax** fields are controlled by a complex setup in Supply Chain Management.</span></span> <span data-ttu-id="0d338-175">Questa impostazione al momento non supporta il mapping di integrazione.</span><span class="sxs-lookup"><span data-stu-id="0d338-175">Currently, this setup doesn't support integration mapping.</span></span> <span data-ttu-id="0d338-176">Nella progettazione attuale, i campi relativi a **Prezzo**, **Sconto**, **Spese** e **Imposta** sono gestiti da Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="0d338-176">In the current design, the **Price**, **Discount**, **Charge**, and **Tax** fields are handled by Supply Chain Management.</span></span>
> - <span data-ttu-id="0d338-177">I campi **Termini di pagamento**, **Termini di trasporto**, **Termini di consegna**, **Metodo di spedizione** e **Modalità di consegna** non sono inclusi nei mapping predefiniti.</span><span class="sxs-lookup"><span data-stu-id="0d338-177">The **Payment terms**, **Freight terms**, **Delivery terms**, **Shipping method**, and **Delivery mode** fields aren't part of the default mappings.</span></span> <span data-ttu-id="0d338-178">Per mappare questi campi, è necessario impostare un mapping di valori che sia specifico ai dati delle organizzazioni tra cui l'entità viene sincronizzata.</span><span class="sxs-lookup"><span data-stu-id="0d338-178">To map these fields, you must set up a value mapping that is specific to the data in the organizations that the entity is synchronized between.</span></span>

<span data-ttu-id="0d338-179">Nelle figure seguenti viene illustrato un esempio di un modello di mapping nell'integratore di dati.</span><span class="sxs-lookup"><span data-stu-id="0d338-179">The following illustrations show an example of a template mapping in data integrator.</span></span>

### <a name="quoteheader"></a><span data-ttu-id="0d338-180">QuoteHeader</span><span class="sxs-lookup"><span data-stu-id="0d338-180">QuoteHeader</span></span>

![Mapping dei modelli nell'integratore di dati](./media/sales-quotation-direct-template-mapping-data-integrator-1.png)

### <a name="quoteline"></a><span data-ttu-id="0d338-182">QuoteLine</span><span class="sxs-lookup"><span data-stu-id="0d338-182">QuoteLine</span></span>

![Mapping dei modelli nell'integratore di dati](./media/sales-quotation-direct-template-mapping-data-integrator-2.png)

## <a name="related-topics"></a><span data-ttu-id="0d338-184">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="0d338-184">Related topics</span></span>

[<span data-ttu-id="0d338-185">Prospect to cash</span><span class="sxs-lookup"><span data-stu-id="0d338-185">Prospect to cash</span></span>](prospect-to-cash.md)



[!INCLUDE[footer-include](../../includes/footer-banner.md)]