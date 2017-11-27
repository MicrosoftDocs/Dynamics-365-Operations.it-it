---
title: Sincronizzare intestazioni e righe di offerte di vendita direttamente da Sales in Finance and Operations
description: "L'argomento descrive i modelli e le attività sottostanti che vengono utilizzati per sincronizzare le righe e le intestazioni delle offerte di vendita direttamente da Microsoft Dynamics 365 for Sales in Microsoft Dynamics 365 for Finance and Operations, Enterprise edition."
author: ChristianRytt
manager: AnnBe
ms.date: 11/14/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User, IT Pro
ms.reviewer: yuyus
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: crytt
ms.dyn365.ops.intro: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: 674d2e1f2c5cdbccf43618a9083ca01abed0735a
ms.openlocfilehash: 8a75c6dd91020ab3e676e2bb40d5c822731e244f
ms.contentlocale: it-it
ms.lasthandoff: 11/14/2017

---

# <a name="synchronize-sales-quotation-headers-and-lines-directly-from-sales-to-finance-and-operations"></a><span data-ttu-id="6a90c-103">Sincronizzare intestazioni e righe di offerte di vendita direttamente da Sales in Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="6a90c-103">Synchronize sales quotation headers and lines directly from Sales to Finance and Operations</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="6a90c-104">L'argomento descrive i modelli e le attività sottostanti che vengono utilizzati per sincronizzare le righe e le intestazioni delle offerte di vendita direttamente da Microsoft Dynamics 365 for Sales in Microsoft Dynamics 365 for Finance and Operations, Enterprise edition.</span><span class="sxs-lookup"><span data-stu-id="6a90c-104">The topic discusses the templates and underlying tasks that are used to synchronize sales quotation headers and lines directly from Microsoft Dynamics 365 for Sales to Microsoft Dynamics 365 for Finance and Operations, Enterprise edition.</span></span>

> [!NOTE]
> <span data-ttu-id="6a90c-105">Prima di utilizzare la soluzione Prospect to cash, è necessario acquisire familiarità con [Integrazione dati di Dynamics 365](/common-data-service/entity-reference/dynamics-365-integration).</span><span class="sxs-lookup"><span data-stu-id="6a90c-105">Before you can use the Prospect to cash solution, you should be familiar with [Dynamics 365 Data integration](/common-data-service/entity-reference/dynamics-365-integration).</span></span>

## <a name="template-and-tasks"></a><span data-ttu-id="6a90c-106">Modello e attività</span><span class="sxs-lookup"><span data-stu-id="6a90c-106">Template and tasks</span></span>

<span data-ttu-id="6a90c-107">Il seguente modello e le attività sottostanti vengono utilizzati per sincronizzare le intestazioni e le righe delle offerte di vendita direttamente da Sales in Finance and Operations:</span><span class="sxs-lookup"><span data-stu-id="6a90c-107">The following template and underlying tasks are used to synchronize sales quotation headers and lines directly from Sales to Finance and Operations:</span></span>

- <span data-ttu-id="6a90c-108">**Nome del modello in Integrazione dati:** Offerte di vendita (da Sales in Fin and Ops) - Diretto</span><span class="sxs-lookup"><span data-stu-id="6a90c-108">**Name of the template in Data integration:** Sales Quotes (Sales to Fin and Ops) - Direct</span></span>
- <span data-ttu-id="6a90c-109">**Nomi delle attività nel progetto di Integrazione dati:**</span><span class="sxs-lookup"><span data-stu-id="6a90c-109">**Names of the tasks in the Data integration project:**</span></span>

    - <span data-ttu-id="6a90c-110">QuoteHeader</span><span class="sxs-lookup"><span data-stu-id="6a90c-110">QuoteHeader</span></span>
    - <span data-ttu-id="6a90c-111">QuoteLine</span><span class="sxs-lookup"><span data-stu-id="6a90c-111">QuoteLine</span></span>

<span data-ttu-id="6a90c-112">Le attività di sincronizzazione seguenti sono necessarie prima di eseguire la sincronizzazione delle intestazioni e delle righe di un'offerta di vendita:</span><span class="sxs-lookup"><span data-stu-id="6a90c-112">The following synchronization tasks are required before synchronization of sales quotation headers and lines can occur:</span></span>

- <span data-ttu-id="6a90c-113">Prodotti (da Fin and Ops in Sales) - Diretto</span><span class="sxs-lookup"><span data-stu-id="6a90c-113">Products (Fin and Ops to Sales) - Direct</span></span>
- <span data-ttu-id="6a90c-114">Conti (da Sales in Fin and Ops) - Diretto (se utilizzata)</span><span class="sxs-lookup"><span data-stu-id="6a90c-114">Accounts (Sales to Fin and Ops) - Direct (if used)</span></span>
- <span data-ttu-id="6a90c-115">Da Contatti a Clienti (da Sales in Fin and Ops) - Diretto (se utilizzata)</span><span class="sxs-lookup"><span data-stu-id="6a90c-115">Contacts to Customers (Sales to Fin and Ops) - Direct (if used)</span></span>

## <a name="entity-set"></a><span data-ttu-id="6a90c-116">Insieme di entità</span><span class="sxs-lookup"><span data-stu-id="6a90c-116">Entity set</span></span>

| <span data-ttu-id="6a90c-117">Vendite</span><span class="sxs-lookup"><span data-stu-id="6a90c-117">Sales</span></span>        | <span data-ttu-id="6a90c-118">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="6a90c-118">Finance and Operations</span></span>     |
|--------------|----------------------------|
| <span data-ttu-id="6a90c-119">Citazioni</span><span class="sxs-lookup"><span data-stu-id="6a90c-119">Quotes</span></span>       | <span data-ttu-id="6a90c-120">Intestazione offerta di vendita CDS</span><span class="sxs-lookup"><span data-stu-id="6a90c-120">CDS sales quotation header</span></span> |
| <span data-ttu-id="6a90c-121">QuoteDetails</span><span class="sxs-lookup"><span data-stu-id="6a90c-121">QuoteDetails</span></span> | <span data-ttu-id="6a90c-122">Righe di offerta di vendita CDS</span><span class="sxs-lookup"><span data-stu-id="6a90c-122">CDS sales quotation lines</span></span>  |

## <a name="entity-flow"></a><span data-ttu-id="6a90c-123">Flusso di entità</span><span class="sxs-lookup"><span data-stu-id="6a90c-123">Entity flow</span></span>

<span data-ttu-id="6a90c-124">Le offerte di vendita vengono create in Sales e sincronizzate in Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="6a90c-124">Sales quotations are created in Sales and synchronized to Finance and Operations.</span></span>

<span data-ttu-id="6a90c-125">Le offerte di vendita da Sales vengono sincronizzate solo se vengono soddisfatte le condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="6a90c-125">Sales quotations from Sales are synchronized only if the following conditions are met:</span></span>

- <span data-ttu-id="6a90c-126">Tutti i prodotti offerta nelle righe dell'offerta di vendita sono gestiti esternamente.</span><span class="sxs-lookup"><span data-stu-id="6a90c-126">All quote products on the sales quotation are externally maintained.</span></span>
- <span data-ttu-id="6a90c-127">Dopo aver fatto clic su **Attiva offerta**, l'offerta di vendita è attiva.</span><span class="sxs-lookup"><span data-stu-id="6a90c-127">After you click **Activate quote**, the sales quotation is active.</span></span>

## <a name="prospect-to-cash-solution-for-sales"></a><span data-ttu-id="6a90c-128">Soluzione Prospect to cash per Sales</span><span class="sxs-lookup"><span data-stu-id="6a90c-128">Prospect to cash solution for Sales</span></span>

<span data-ttu-id="6a90c-129">È stato aggiunto il campo **Solo prodotti gestiti esternamente** all'entità **Offerta** per rilevare in modo coerente se l'offerta di vendita consiste interamente di prodotti gestiti esternamente.</span><span class="sxs-lookup"><span data-stu-id="6a90c-129">The **Has Externally Maintained Products Only** field has been added to the **Quote** entity to consistently track whether the sales quotation consists entirely of externally maintained products.</span></span> <span data-ttu-id="6a90c-130">Se un'offerta di vendita include solo prodotti gestiti esternamente, i prodotti vengono gestiti in Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="6a90c-130">If a sales quotation has only externally maintained products, the products are maintained in Finance and Operations.</span></span> <span data-ttu-id="6a90c-131">Questo comportamento impedisce il tentativo di sincronizzare righe di offerta di vendita che hanno prodotti sconosciuti in Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="6a90c-131">This behavior helps guarantee that you don't try to synchronize sales quotation lines that have products that are unknown to Finance and Operations.</span></span>

<span data-ttu-id="6a90c-132">Tutti i prodotti offerta e l'offerta di vendita vengono aggiornati con le informazioni **Solo prodotti gestiti esternamente** derivate dall'intestazione dell'offerta di vendita.</span><span class="sxs-lookup"><span data-stu-id="6a90c-132">All quote products on the sales quotation are updated with the **Has Externally Maintained Products Only** information from the sales quotation header.</span></span> <span data-ttu-id="6a90c-133">Queste informazioni sono disponibili nel campo **L'offerta ha solo prodotti gestiti esternamente** nell'entità **QuoteDetails**.</span><span class="sxs-lookup"><span data-stu-id="6a90c-133">This information is found in the **Quote Has Externally Maintained Products Only** field on the **QuoteDetails** entity.</span></span>

<span data-ttu-id="6a90c-134">Uno sconto può essere aggiunto al prodotto offerta e verrà sincronizzato con Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="6a90c-134">A discount can be added to the quote product and will be synchronized to Finance and Operations.</span></span> <span data-ttu-id="6a90c-135">I campi **Sconto**, **Spese** e **Imposta** nell'intestazione sono controllati da un'impostazione in Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="6a90c-135">The **Discount**, **Charges**, and **Tax** fields on the header are controlled by a setup in Finance and Operations.</span></span> <span data-ttu-id="6a90c-136">Questa impostazione al momento non supporta il mapping di integrazione.</span><span class="sxs-lookup"><span data-stu-id="6a90c-136">Currently, this setup doesn't support integration mapping.</span></span> <span data-ttu-id="6a90c-137">Nella progettazione attuale, i campi **Prezzo**, **Sconto**, **Spese** e **Imposta** sono gestiti in Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="6a90c-137">In the current design, the **Price**, **Discount**, **Charge**, and **Tax** fields are maintained and handled in Finance and Operations.</span></span>

<span data-ttu-id="6a90c-138">In Sales, la soluzione rende i campi seguenti di sola lettura, perché i valori non vengono sincronizzati con Finance and Operations:</span><span class="sxs-lookup"><span data-stu-id="6a90c-138">In Sales, the solution makes the following fields read-only, because the values aren't synchronized to Finance and Operations:</span></span>

- <span data-ttu-id="6a90c-139">Campi di sola lettura nell'intestazione dell'offerta di vendita: **% sconto**, **Sconto**, **Importo trasporto**</span><span class="sxs-lookup"><span data-stu-id="6a90c-139">Read-only fields on the sales quotation header: **Discount %**, **Discount**, and **Freight Amount**</span></span>
- <span data-ttu-id="6a90c-140">Campi di sola lettura nei prodotti offerta: **Imposta**</span><span class="sxs-lookup"><span data-stu-id="6a90c-140">Read-only fields on quote products: **Tax**</span></span>

## <a name="preconditions-and-mapping-setup"></a><span data-ttu-id="6a90c-141">Prerequisiti e impostazioni di mapping</span><span class="sxs-lookup"><span data-stu-id="6a90c-141">Preconditions and mapping setup</span></span>

<span data-ttu-id="6a90c-142">Prima di sincronizzare le offerte di vendita, è importante aggiornare le seguenti impostazioni.</span><span class="sxs-lookup"><span data-stu-id="6a90c-142">Before sales quotations are synchronized, it's important that you update the following settings.</span></span>

### <a name="setup-in-sales"></a><span data-ttu-id="6a90c-143">Impostazione in Sales</span><span class="sxs-lookup"><span data-stu-id="6a90c-143">Setup in Sales</span></span>

- <span data-ttu-id="6a90c-144">Assicurarsi che le autorizzazioni siano impostate per il team a cui l'utente nel set di connessione in Sales viene assegnato.</span><span class="sxs-lookup"><span data-stu-id="6a90c-144">Make sure that permissions are set up for the team that the user from your connection set in Sales is assigned to.</span></span> <span data-ttu-id="6a90c-145">Se si utilizzano dati dimostrativi, in genere l'utente ha privilegi di amministratore, ma non il team.</span><span class="sxs-lookup"><span data-stu-id="6a90c-145">If you're using demo data, the user usually has admin access, but the team doesn't have admin access.</span></span> <span data-ttu-id="6a90c-146">Se il team non dispone di privilegi di amministratore quando si esegue il progetto da Integrazione dati, verrà visualizzato un messaggio di errore in cui viene indicato che il team principale è mancante.</span><span class="sxs-lookup"><span data-stu-id="6a90c-146">If the team doesn't have admin access when you run the project from Data integration, you will receive an error message that states that the Principal team is missing.</span></span>

    <span data-ttu-id="6a90c-147">Per impostare le autorizzazioni per il team, andare a **Impostazioni** &gt; **Sicurezza** &gt; **Team** e selezionare il team pertinente.</span><span class="sxs-lookup"><span data-stu-id="6a90c-147">To set up permissions for the team, go to **Settings** &gt; **Security** &gt; **Teams**, and select the relevant team.</span></span> <span data-ttu-id="6a90c-148">Selezionare **Gestisci ruoli** e quindi selezionare un ruolo che dispone delle autorizzazioni appropriate, ad esempio **Amministratore di sistema**.</span><span class="sxs-lookup"><span data-stu-id="6a90c-148">Select **Manage Roles**, and then select a role that has the desired permissions, such as **System Administrator**.</span></span>

- <span data-ttu-id="6a90c-149">Andare a **Impostazioni** &gt; **Amministrazione** &gt; **Impostazioni di sistema** &gt; **Vendite** e assicurarsi che:</span><span class="sxs-lookup"><span data-stu-id="6a90c-149">Go to **Settings** &gt; **Administration** &gt; **System settings** &gt; **Sales**, and make sure that the following settings are used:</span></span>

    - <span data-ttu-id="6a90c-150">L'opzione **Usa sistema di calcolo prezzi sistema** sia impostata su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="6a90c-150">The **Use system prizing calculation system** option is set to **Yes**.</span></span>
    - <span data-ttu-id="6a90c-151">Il campo **Metodo di calcolo sconto** sia impostato su **Voce**.</span><span class="sxs-lookup"><span data-stu-id="6a90c-151">The **Discount calculation method** field is set to **Line item**.</span></span>

### <a name="setup-in-the-data-integration-project"></a><span data-ttu-id="6a90c-152">Impostazione nel progetto di Integrazione dati</span><span class="sxs-lookup"><span data-stu-id="6a90c-152">Setup in the Data integration project</span></span>

#### <a name="quoteheader"></a><span data-ttu-id="6a90c-153">QuoteHeader</span><span class="sxs-lookup"><span data-stu-id="6a90c-153">QuoteHeader</span></span>

- <span data-ttu-id="6a90c-154">Assicurarsi che il mapping necessario esista per **Shipto\_country** a **DeliveryAddressCountryRegionISOCode**.</span><span class="sxs-lookup"><span data-stu-id="6a90c-154">Make sure that the required mapping exists for **Shipto\_country** to **DeliveryAddressCountryRegionISOCode**.</span></span> <span data-ttu-id="6a90c-155">Nella mappa di valori, è possibile definire un valore predefinito utilizzato se il valore è vuoto.</span><span class="sxs-lookup"><span data-stu-id="6a90c-155">In the value map, you can define a default value that is used if the value is left blank.</span></span> <span data-ttu-id="6a90c-156">Lasciare la parte sinistra vuota e impostare la parte destra sul paese desiderato.</span><span class="sxs-lookup"><span data-stu-id="6a90c-156">Just leave the left side blank, and set the right side to the desired country or region.</span></span> <span data-ttu-id="6a90c-157">In questo modo, non sarà necessario immettere il paese per gli ordini nazionali.</span><span class="sxs-lookup"><span data-stu-id="6a90c-157">In this way, you don't have to type the country or region for national orders.</span></span>

    <span data-ttu-id="6a90c-158">Il valore di modello è una mappa di valori dove vari paesi vengono mappati e dove un valore vuoto equivale a **Stati Uniti**.</span><span class="sxs-lookup"><span data-stu-id="6a90c-158">The template value is a value map where several countries or regions are mapped, and where a blank value equals a value of **US**.</span></span>

#### <a name="quoteline"></a><span data-ttu-id="6a90c-159">QuoteLine</span><span class="sxs-lookup"><span data-stu-id="6a90c-159">QuoteLine</span></span>

- <span data-ttu-id="6a90c-160">Assicurarsi che la mappa valori richiesta esista per **SalesUnitSymbol** in Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="6a90c-160">Make sure that the required value map exists for **SalesUnitSymbol** in Finance and Operations.</span></span>
- <span data-ttu-id="6a90c-161">Assicurarsi che le unità richieste siano definite in Sales.</span><span class="sxs-lookup"><span data-stu-id="6a90c-161">Make sure that the required units are defined in Sales.</span></span>

    <span data-ttu-id="6a90c-162">Un valore di modello con una mappa di valori viene definito per **oumid.name** a **SalesUnitSymbol**.</span><span class="sxs-lookup"><span data-stu-id="6a90c-162">A template value that has a value map is defined for **oumid.name** to **SalesUnitSymbol**.</span></span>

- <span data-ttu-id="6a90c-163">Facoltativo: è possibile aggiungere i mapping seguenti in modo da garantire che le righe dell'offerta di vendita vengano importate in Finance and Operations se non sono disponibili informazioni predefinite dal cliente o dal prodotto:</span><span class="sxs-lookup"><span data-stu-id="6a90c-163">Optional: You can add the following mappings to help guarantee that sales quotation lines are imported into Finance and Operations if there is no default information from either the customer or the product:</span></span>

    - <span data-ttu-id="6a90c-164">**SiteId** - Un sito è obbligatorio per la generazione di offerte e righe di ordine cliente in Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="6a90c-164">**SiteId** – A site is required in order to generate quotations and sales order lines in Finance and Operations.</span></span> <span data-ttu-id="6a90c-165">Non è disponibile alcun valore del modello predefinito per **SiteId**.</span><span class="sxs-lookup"><span data-stu-id="6a90c-165">There is no default template value for **SiteId**.</span></span>
    - <span data-ttu-id="6a90c-166">**WarehouseId** - Un magazzino è obbligatorio per l'elaborazione di offerte e righe di ordine cliente in Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="6a90c-166">**WarehouseId** – A warehouse is required in order to process quotations and sales order lines in Finance and Operations.</span></span> <span data-ttu-id="6a90c-167">Non è disponibile alcun valore del modello predefinito per **WarehouseId**.</span><span class="sxs-lookup"><span data-stu-id="6a90c-167">There is no default template value for **WarehouseId**.</span></span>

## <a name="template-mapping-in-data-integrator"></a><span data-ttu-id="6a90c-168">Mapping dei modelli nell'integratore di dati</span><span class="sxs-lookup"><span data-stu-id="6a90c-168">Template mapping in data integrator</span></span>

> [!NOTE]
> - <span data-ttu-id="6a90c-169">I campi relativi a **Sconto**, **Spese** e **Imposta** sono controllati da un'impostazione complessa in Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="6a90c-169">The **Discount**, **Charges**, and **Tax** fields are controlled by a complex setup in Finance and Operations.</span></span> <span data-ttu-id="6a90c-170">Questa impostazione al momento non supporta il mapping di integrazione.</span><span class="sxs-lookup"><span data-stu-id="6a90c-170">Currently, this setup doesn't support integration mapping.</span></span> <span data-ttu-id="6a90c-171">Nella progettazione attuale, i campi relativi a **Prezzo**, **Sconto**, **Spese** e **Imposta** sono gestiti da Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="6a90c-171">In the current design, the **Price**, **Discount**, **Charge**, and **Tax** fields are handled by Finance and Operations.</span></span>
> - <span data-ttu-id="6a90c-172">I campi **Termini di pagamento**, **Termini di trasporto**, **Termini di consegna**, **Metodo di spedizione** e **Modalità di consegna** non sono inclusi nei mapping predefiniti.</span><span class="sxs-lookup"><span data-stu-id="6a90c-172">The **Payment terms**, **Freight terms**, **Delivery terms**, **Shipping method**, and **Delivery mode** fields aren't part of the default mappings.</span></span> <span data-ttu-id="6a90c-173">Per mappare questi campi, è necessario impostare un mapping di valori che sia specifico ai dati delle organizzazioni tra cui l'entità viene sincronizzata.</span><span class="sxs-lookup"><span data-stu-id="6a90c-173">To map these fields, you must set up a value mapping that is specific to the data in the organizations that the entity is synchronized between.</span></span>

<span data-ttu-id="6a90c-174">Nelle figure seguenti viene illustrato un esempio di un modello di mapping nell'integratore di dati.</span><span class="sxs-lookup"><span data-stu-id="6a90c-174">The following illustrations show an example of a template mapping in data integrator.</span></span>

### <a name="quoteheader"></a><span data-ttu-id="6a90c-175">QuoteHeader</span><span class="sxs-lookup"><span data-stu-id="6a90c-175">QuoteHeader</span></span>

![Mapping dei modelli nell'integratore di dati](./media/sales-quotation-direct-template-mapping-data-integrator-1.png)

### <a name="quoteline"></a><span data-ttu-id="6a90c-177">QuoteLine</span><span class="sxs-lookup"><span data-stu-id="6a90c-177">QuoteLine</span></span>

![Mapping dei modelli nell'integratore di dati](./media/sales-quotation-direct-template-mapping-data-integrator-2.png)

## <a name="related-topics"></a><span data-ttu-id="6a90c-179">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="6a90c-179">Related topics</span></span>

[<span data-ttu-id="6a90c-180">Prospect to cash</span><span class="sxs-lookup"><span data-stu-id="6a90c-180">Prospect to cash</span></span>](prospect-to-cash.md)


