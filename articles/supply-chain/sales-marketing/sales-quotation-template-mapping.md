---
title: Sincronizzare le intestazioni e le righe di offerte di vendita da Sales a Finance and Operations
description: "L'argomento descrive i modelli e le attività sottostanti che vengono utilizzati per sincronizzare le righe e le intestazioni delle offerte di vendita da Microsoft Dynamics 365 for Sales a Microsoft Dynamics 365 for Finance and Operations, Enterprise edition."
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
ms.openlocfilehash: c8cfc484eed02423dbf0c7caaf8ac2337b6ac38d
ms.contentlocale: it-it
ms.lasthandoff: 11/03/2017

---

# <a name="synchronize-sales-quotation-headers-and-lines-from-sales-to-finance-and-operations"></a><span data-ttu-id="3fe73-103">Sincronizzare le intestazioni e le righe di offerte di vendita da Sales a Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="3fe73-103">Synchronize sales quotation headers and lines from Sales to Finance and Operations</span></span>

[!include[banner](../includes/banner.md)]

> [!NOTE]
> <span data-ttu-id="3fe73-104">Prima di utilizzare la soluzione Prospect to cash, acquisisci familiarità con [Integrazione dei dati di Microsoft Dynamics 365](/common-data-service/entity-reference/dynamics-365-integration).</span><span class="sxs-lookup"><span data-stu-id="3fe73-104">Before you can use the Prospect to cash solution, be familiar with [Dynamics 365 Data Integration](/common-data-service/entity-reference/dynamics-365-integration).</span></span> 

<span data-ttu-id="3fe73-105">L'argomento descrive i modelli e le attività sottostanti che vengono utilizzati per sincronizzare le righe e le intestazioni delle offerte di vendita da Microsoft Dynamics 365 for Sales (Sales) a Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (Finance and Operations).</span><span class="sxs-lookup"><span data-stu-id="3fe73-105">The topic discusses the templates and underlying tasks that are used to synchronize sales quotation headers and lines from Microsoft Dynamics 365 for Sales (Sales) to Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (Finance and Operations).</span></span> 

## <a name="template-and-tasks"></a><span data-ttu-id="3fe73-106">Modello e attività</span><span class="sxs-lookup"><span data-stu-id="3fe73-106">Template and tasks</span></span>

<span data-ttu-id="3fe73-107">I seguenti modelli e le attività sottostanti vengono utilizzati per sincronizzare le intestazioni e le righe delle offerte di vendita da Sales a Finance and Operations:</span><span class="sxs-lookup"><span data-stu-id="3fe73-107">The following templates and underlying tasks are used to synchronize sales quotation headers and lines from Sales to Finance and Operations:</span></span>

- <span data-ttu-id="3fe73-108">**Nome del modello:** Offerte di vendita (Sales a Fin and Ops)</span><span class="sxs-lookup"><span data-stu-id="3fe73-108">**Name of the template:** Sales Quotes (Sales to Fin and Ops)</span></span>
- <span data-ttu-id="3fe73-109">**Nomi delle attività del progetto:**</span><span class="sxs-lookup"><span data-stu-id="3fe73-109">**Names of the tasks in the project:**</span></span>

    - <span data-ttu-id="3fe73-110">QuoteHeader</span><span class="sxs-lookup"><span data-stu-id="3fe73-110">QuoteHeader</span></span>
    - <span data-ttu-id="3fe73-111">QuoteLine</span><span class="sxs-lookup"><span data-stu-id="3fe73-111">QuoteLine</span></span>

<span data-ttu-id="3fe73-112">Le attività di sincronizzazione seguenti sono necessarie prima di eseguire la sincronizzazione delle intestazioni e delle righe di un'offerta di vendita:</span><span class="sxs-lookup"><span data-stu-id="3fe73-112">The following synchronization tasks are required before synchronization of sales quotation headers and lines can occur:</span></span>

- <span data-ttu-id="3fe73-113">Prodotti (da Fin and Ops in Sales)</span><span class="sxs-lookup"><span data-stu-id="3fe73-113">Products (Fin and Ops to Sales)</span></span>
- <span data-ttu-id="3fe73-114">Conti (da Sales in Fin and Ops) (se utilizzata)</span><span class="sxs-lookup"><span data-stu-id="3fe73-114">Accounts (Sales to Fin and Ops) (if used)</span></span>
- <span data-ttu-id="3fe73-115">Da Contatti a Clienti (da Sales in Fin and Ops) (se utilizzata)</span><span class="sxs-lookup"><span data-stu-id="3fe73-115">Contacts to Customers (Sales to Fin and Ops) (if used)</span></span>

## <a name="entity-set"></a><span data-ttu-id="3fe73-116">Insieme di entità</span><span class="sxs-lookup"><span data-stu-id="3fe73-116">Entity set</span></span>

| <span data-ttu-id="3fe73-117">Vendite</span><span class="sxs-lookup"><span data-stu-id="3fe73-117">Sales</span></span>        | <span data-ttu-id="3fe73-118">CDS</span><span class="sxs-lookup"><span data-stu-id="3fe73-118">CDS</span></span>           | <span data-ttu-id="3fe73-119">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="3fe73-119">Finance and Operations</span></span>    |
|--------------|---------------|---------------------------|
| <span data-ttu-id="3fe73-120">Citazioni</span><span class="sxs-lookup"><span data-stu-id="3fe73-120">Quotes</span></span>       | <span data-ttu-id="3fe73-121">Offerta</span><span class="sxs-lookup"><span data-stu-id="3fe73-121">Quotation</span></span>     | <span data-ttu-id="3fe73-122">Intestazioni offerta di vendita</span><span class="sxs-lookup"><span data-stu-id="3fe73-122">Sales quotation headers</span></span>   |
| <span data-ttu-id="3fe73-123">QuoteDetails</span><span class="sxs-lookup"><span data-stu-id="3fe73-123">QuoteDetails</span></span> | <span data-ttu-id="3fe73-124">QuotationLine</span><span class="sxs-lookup"><span data-stu-id="3fe73-124">QuotationLine</span></span> | <span data-ttu-id="3fe73-125">Righe di offerta di vendita CDS</span><span class="sxs-lookup"><span data-stu-id="3fe73-125">CDS sales quotation lines</span></span> |

## <a name="entity-flow"></a><span data-ttu-id="3fe73-126">Flusso di entità</span><span class="sxs-lookup"><span data-stu-id="3fe73-126">Entity flow</span></span>

<span data-ttu-id="3fe73-127">Le offerte di vendita vengono create in Sales e sincronizzate in Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="3fe73-127">Sales quotations are created in Sales and synchronized to Finance and Operations.</span></span>

<span data-ttu-id="3fe73-128">Le offerte di vendita da Sales vengono sincronizzate solo se vengono soddisfatte le condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="3fe73-128">Sales quotations from Sales are synchronized only if the following conditions are met:</span></span>

- <span data-ttu-id="3fe73-129">Tutti i prodotti nelle righe dell'offerta di vendita sono gestiti esternamente.</span><span class="sxs-lookup"><span data-stu-id="3fe73-129">All products on the sales quotation lines are externally maintained.</span></span>
- <span data-ttu-id="3fe73-130">L'offerta di vendita è attiva o attivata.</span><span class="sxs-lookup"><span data-stu-id="3fe73-130">The sales quotation is active or activated.</span></span>

## <a name="prospect-to-cash-solution-for-sales"></a><span data-ttu-id="3fe73-131">Soluzione Prospect to cash per Sales</span><span class="sxs-lookup"><span data-stu-id="3fe73-131">Prospect to cash solution for Sales</span></span>

<span data-ttu-id="3fe73-132">È stato aggiunto il campo **Solo prodotti gestiti esternamente** all'entità Offerta per tenere traccia in modo coerente se l'offerta di vendita consiste interamente di prodotti gestiti esternamente.</span><span class="sxs-lookup"><span data-stu-id="3fe73-132">The **Has Externally Maintained Products Only** field has been added to the Quote entity to consistently track whether the sales quotation consists entirely of externally maintained products.</span></span> <span data-ttu-id="3fe73-133">Se un'offerta di vendita include solo prodotti gestiti esternamente, i prodotti vengono gestiti in Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="3fe73-133">If a sales quotation has only externally maintained products, the products are maintained in Finance and Operations.</span></span> <span data-ttu-id="3fe73-134">Questo comportamento offre la garanzia di non provare a sincronizzare righe di offerta di vendita con prodotti che sono sconosciuti a Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="3fe73-134">This behavior helps guarantee that you don't try to synchronize sales quotation lines with products that are unknown to Finance and Operations.</span></span>

<span data-ttu-id="3fe73-135">Tutti i prodotti e le righe nell'offerta vengono aggiornati con le informazioni **Solo prodotti gestiti esternamente** derivate dall'intestazione dell'offerta.</span><span class="sxs-lookup"><span data-stu-id="3fe73-135">All products and lines on the quotation are updated with the **Has Externally Maintained Products Only** information from the quotation header.</span></span> <span data-ttu-id="3fe73-136">Queste informazioni sono disponibili nel campo **La quota ha solo prodotti gestiti esternamente** nell'entità riga dell'offerta.</span><span class="sxs-lookup"><span data-stu-id="3fe73-136">This information can be found in the **Quote Has Externally Maintained Products Only** field on the Quote line entity.</span></span>

<span data-ttu-id="3fe73-137">I campi relativi a **Sconto**, **Spese** e **Imposta** sono controllati da un'impostazione complessa in Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="3fe73-137">The **Discount**, **Charges**, and **Tax** fields are controlled by a complex setup in Finance and Operations.</span></span> <span data-ttu-id="3fe73-138">Questa impostazione al momento non supporta il mapping di integrazione.</span><span class="sxs-lookup"><span data-stu-id="3fe73-138">This setup doesn't currently support integration mapping.</span></span> <span data-ttu-id="3fe73-139">Nella progettazione attuale, i campi relativi a **Prezzo**, **Sconto**, **Spese** e **Imposta** sono dei master e sono gestiti da Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="3fe73-139">In the current design, the **Price**, **Discount**, **Charge**, and **Tax** fields are mastered and handled by Finance and Operations.</span></span>

<span data-ttu-id="3fe73-140">In Sales, la soluzione rende i campi seguenti di sola lettura, perché i valori non vengono sincronizzati con Finance and Operations:</span><span class="sxs-lookup"><span data-stu-id="3fe73-140">In Sales, the solution makes the following fields read-only, because the values aren't synchronized to Finance and Operations:</span></span>

- <span data-ttu-id="3fe73-141">**Campi di sola lettura nell'intestazione dell'offerta di vendita:** % sconto, Sconto, Importo trasporto</span><span class="sxs-lookup"><span data-stu-id="3fe73-141">**Read-only fields on the sales quotation header:** Discount %, Discount, Freight Amount</span></span>
- <span data-ttu-id="3fe73-142">**Campi di sola lettura nelle righe dell'offerta di vendita:** Imposta</span><span class="sxs-lookup"><span data-stu-id="3fe73-142">**Read-only fields on sales quotation lines:** Tax</span></span>

## <a name="preconditions-and-mapping-setup"></a><span data-ttu-id="3fe73-143">Prerequisiti e impostazioni di mapping</span><span class="sxs-lookup"><span data-stu-id="3fe73-143">Preconditions and mapping setup</span></span>

<span data-ttu-id="3fe73-144">Prima di sincronizzare gli ordini cliente, è importante aggiornare i sistemi con la seguente impostazione:</span><span class="sxs-lookup"><span data-stu-id="3fe73-144">Before synchronizing sales orders, it is important to update the systems with the following setting:</span></span>

### <a name="setup-in-sales"></a><span data-ttu-id="3fe73-145">Impostazione in Sales</span><span class="sxs-lookup"><span data-stu-id="3fe73-145">Setup in Sales</span></span>

- <span data-ttu-id="3fe73-146">Passare a **Impostazioni** &gt; **Amministrazione** &gt; **Impostazioni di sistema** &gt; **Vendite** e verificare che il campo **Metodo di calcolo sconto** sia impostato su **Per unità**.</span><span class="sxs-lookup"><span data-stu-id="3fe73-146">Go to **Settings** &gt; **Administration** &gt; **System settings** &gt; **Sales**, and make sure that the **Discount calculation method** field is set to **Per unit**.</span></span> <span data-ttu-id="3fe73-147">Questa impostazione assicura che lo sconto della voce da Sales corrisponda all'impostazione in Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="3fe73-147">This setting helps guarantee that the line item discount from Sales matches the setting in Finance and Operations.</span></span> <span data-ttu-id="3fe73-148">In caso contrario, lo sconto non risulterà corretto in Finance and Operations, poiché Finance and Operations lo leggerà come sconto unitario anche se in Sales è uno sconto per riga di vendita.</span><span class="sxs-lookup"><span data-stu-id="3fe73-148">Otherwise, the discount won't be correct in Finance and Operations, because Finance and Operations will read the discount as a per-unit discount even if it was a per-line discount in Sales.</span></span>

### <a name="setup-in-finance-and-operations"></a><span data-ttu-id="3fe73-149">Impostazione in Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="3fe73-149">Setup in Finance and Operations</span></span>

- <span data-ttu-id="3fe73-150">Passare a **Contabilità clienti** &gt; **Impostazioni** &gt; **Parametri contabilità clienti**.</span><span class="sxs-lookup"><span data-stu-id="3fe73-150">Go to **Accounts receivable** &gt; **Setup** &gt; **Account receivable parameters**.</span></span> <span data-ttu-id="3fe73-151">Nella scheda **Sequenza numerica** selezionare la sequenza per le offerte di vendita e quindi fare clic su **Visualizza dettagli**.</span><span class="sxs-lookup"><span data-stu-id="3fe73-151">On the **Number sequence** tab, select the number sequence for sales quotations, and then click **View details**.</span></span> <span data-ttu-id="3fe73-152">In **Impostazione generale** impostare il campo **Manuale** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="3fe73-152">Then, under **General Setup**, set the **Manual** field to **Yes**.</span></span>
- <span data-ttu-id="3fe73-153">Passare a **Contabilità clienti** &gt; **Impostazioni** &gt; **Parametri contabilità clienti**.</span><span class="sxs-lookup"><span data-stu-id="3fe73-153">Go to **Accounts receivable** &gt; **Setup** &gt; **Accounts receivable parameters**.</span></span> <span data-ttu-id="3fe73-154">Nella scheda **Spedizioni** impostare il campo **Controllo data di consegna** su **Nessuno**.</span><span class="sxs-lookup"><span data-stu-id="3fe73-154">Then, on the **Shipments** tab, set the **Delivery date control** field to **None**.</span></span> <span data-ttu-id="3fe73-155">Questa impostazione aiuta a evitare errori di sincronizzazione per le offerte di vendita.</span><span class="sxs-lookup"><span data-stu-id="3fe73-155">This setting helps prevent synchronization from failing for sales quotations.</span></span>

### <a name="setup-in-the-data-integration-project"></a><span data-ttu-id="3fe73-156">Impostazione nel progetto di Integrazione dati</span><span class="sxs-lookup"><span data-stu-id="3fe73-156">Setup in the Data integration project</span></span>

#### <a name="quoteheader"></a><span data-ttu-id="3fe73-157">QuoteHeader</span><span class="sxs-lookup"><span data-stu-id="3fe73-157">QuoteHeader</span></span>

- <span data-ttu-id="3fe73-158">Il campo **Data di consegna richiesta** è obbligatorio in Finance and Operations e la sincronizzazione avrà esito negativo se il campo è lasciato vuoto.</span><span class="sxs-lookup"><span data-stu-id="3fe73-158">The **Requested delivery date** field is required in Finance and Operations, and synchronization will fail if the field is left blank.</span></span> <span data-ttu-id="3fe73-159">Per evitare questo problema, se il campo è vuoto, viene automaticamente compilato con una data predefinita derivante da **Origine &gt; CDS**.</span><span class="sxs-lookup"><span data-stu-id="3fe73-159">To prevent this issue, if the field is blank, a default date is taken from **Source &gt; CDS**.</span></span> <span data-ttu-id="3fe73-160">È consigliabile aggiornare il campo con una data preferita.</span><span class="sxs-lookup"><span data-stu-id="3fe73-160">The date should be updated to a preferred value.</span></span> <span data-ttu-id="3fe73-161">Al momento non è possibile immettere un valore come **Oggi** per rappresentare la data corrente.</span><span class="sxs-lookup"><span data-stu-id="3fe73-161">Currently, you can't enter a value such as **Today** to represent today's date.</span></span> <span data-ttu-id="3fe73-162">È necessario immettere una data specifica.</span><span class="sxs-lookup"><span data-stu-id="3fe73-162">You must enter a specific date.</span></span> <span data-ttu-id="3fe73-163">Il valore del modello predefinito per **Data di consegna richiesta** è **1/1/2020**.</span><span class="sxs-lookup"><span data-stu-id="3fe73-163">The default template value for **Requested delivery date** is **1/1/2020**.</span></span>
- <span data-ttu-id="3fe73-164">Il campo **Indirizzo Codice paese** è obbligatorio in Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="3fe73-164">The **Address Country region code** field is required in Finance and Operations.</span></span> <span data-ttu-id="3fe73-165">Per evitare errori durante la sincronizzazione, è possibile specificare un valore predefinito che viene utilizzato se il campo viene lasciato vuoto in Sales.</span><span class="sxs-lookup"><span data-stu-id="3fe73-165">To help prevent synchronization errors, you can specify a default value that is used if the field is left blank in Sales.</span></span> <span data-ttu-id="3fe73-166">Il valore predefinito è anche utile, in quanto non è necessario immettere manualmente un valore nel campo **Paese** per gli indirizzi locali.</span><span class="sxs-lookup"><span data-stu-id="3fe73-166">This default value is also useful, because you don't have to manually enter a value in the **Country region** field for local addresses.</span></span> <span data-ttu-id="3fe73-167">Non è disponibile alcun valore di modello predefinito per **DeliveryAddressCountryRegionISOCode**.</span><span class="sxs-lookup"><span data-stu-id="3fe73-167">There is no default template value for **DeliveryAddressCountryRegionISOCode**.</span></span>
- <span data-ttu-id="3fe73-168">Aggiornare il mapping per il campo relativo all'**ID organizzazione CDS** in **Origine &gt; CDS** in modo che corrisponda all'**organizzazione CDS** nell'entità Organizzazione:</span><span class="sxs-lookup"><span data-stu-id="3fe73-168">Update the mapping for **CDS Organization ID** in **Source &gt; CDS** so that it matches **CDS organization** in the Organization entity:</span></span>

    - <span data-ttu-id="3fe73-169">Il valore del modello predefinito per **Organization_OrganizationId** è **ORG001**.</span><span class="sxs-lookup"><span data-stu-id="3fe73-169">The default template value for **Organization_OrganizationId** is **ORG001**.</span></span>
    - <span data-ttu-id="3fe73-170">Il valore del modello predefinito per **Account_Organization_OrganizationId** è **ORG001**.</span><span class="sxs-lookup"><span data-stu-id="3fe73-170">The default template value for **Account_Organization_OrganizationId** is **ORG001**.</span></span>
    - <span data-ttu-id="3fe73-171">Il valore del modello predefinito per **InvoiceAccount_OrganizationId** è **ORG001**.</span><span class="sxs-lookup"><span data-stu-id="3fe73-171">The default template value for **InvoiceAccount_OrganizationId** is **ORG001**.</span></span>

#### <a name="quoteline"></a><span data-ttu-id="3fe73-172">QuoteLine</span><span class="sxs-lookup"><span data-stu-id="3fe73-172">QuoteLine</span></span>

- <span data-ttu-id="3fe73-173">Aggiornare il mapping per il campo relativo all'**ID organizzazione CDS** in **Origine &gt; CDS** in modo che corrisponda all'**organizzazione CDS** nell'entità Organizzazione:</span><span class="sxs-lookup"><span data-stu-id="3fe73-173">Update the mapping for **CDS Organization ID** in **Source &gt; CDS** so that it matches **CDS organization** in the Organization entity:</span></span>

    - <span data-ttu-id="3fe73-174">Il valore del modello predefinito per **Organization_OrganizationId** è **ORG001**.</span><span class="sxs-lookup"><span data-stu-id="3fe73-174">The default template value for **Organization_OrganizationId** is **ORG001**.</span></span>
    - <span data-ttu-id="3fe73-175">Il valore del modello predefinito per **Product_Organization_Organization_OrganizationId** è **ORG001**.</span><span class="sxs-lookup"><span data-stu-id="3fe73-175">The default template value for **Product_Organization_Organization_OrganizationId** is **ORG001**.</span></span>
    - <span data-ttu-id="3fe73-176">Il valore del modello predefinito per **Quotation_Organization_Organization_OrganizationId** è **ORG001**.</span><span class="sxs-lookup"><span data-stu-id="3fe73-176">The default template value for **Quotation_Organization_Organization_OrganizationId** is **ORG001**.</span></span>

- <span data-ttu-id="3fe73-177">Il campo **Data di consegna richiesta** è obbligatorio in Finance and Operations e la sincronizzazione avrà esito negativo se il campo è lasciato vuoto.</span><span class="sxs-lookup"><span data-stu-id="3fe73-177">The **Requested delivery date** field is required in Finance and Operations, and synchronization will fail if the field is left blank.</span></span> <span data-ttu-id="3fe73-178">Per evitare questo problema, se il campo è vuoto, viene automaticamente compilato con una data predefinita derivante da **Origine &gt; CDS**.</span><span class="sxs-lookup"><span data-stu-id="3fe73-178">To prevent this issue, if the field is blank, a default date is taken from **Source &gt; CDS**.</span></span> <span data-ttu-id="3fe73-179">È consigliabile aggiornare il campo con una data preferita.</span><span class="sxs-lookup"><span data-stu-id="3fe73-179">The date should be updated to a preferred value.</span></span> <span data-ttu-id="3fe73-180">Al momento non è possibile immettere un valore come **Oggi** per rappresentare la data corrente.</span><span class="sxs-lookup"><span data-stu-id="3fe73-180">Currently, you can't enter a value such as **Today** to represent today's date.</span></span> <span data-ttu-id="3fe73-181">È necessario immettere una data specifica.</span><span class="sxs-lookup"><span data-stu-id="3fe73-181">You must enter a specific date.</span></span> <span data-ttu-id="3fe73-182">Il valore del modello predefinito per **Data di consegna richiesta** è **1/1/2020**.</span><span class="sxs-lookup"><span data-stu-id="3fe73-182">The default template value for **Requested delivery date** is **1/1/2020**.</span></span>
- <span data-ttu-id="3fe73-183">È possibile aggiungere i mapping seguenti da **CDS &gt; Destinazione** in modo da garantire che le righe di offerta vengano importate in Finance and Operations se non sono disponibili informazioni predefinite dal cliente o dal prodotto:</span><span class="sxs-lookup"><span data-stu-id="3fe73-183">You can add the following mappings from **CDS &gt; Destination** to help guarantee that quotation lines are imported into Finance and Operations if there is no default information from either the customer or the product:</span></span>

    - <span data-ttu-id="3fe73-184">**SiteId** - Un sito è obbligatorio per la generazione di offerte e righe di ordine cliente in Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="3fe73-184">**SiteId** – A site is required in order to generate quotations and sales order lines in Finance and Operations.</span></span> <span data-ttu-id="3fe73-185">Non è disponibile alcun valore del modello predefinito per **SiteId**.</span><span class="sxs-lookup"><span data-stu-id="3fe73-185">There is no default template value for **SiteId**.</span></span>
    - <span data-ttu-id="3fe73-186">**WarehouseId** - Un magazzino è obbligatorio per l'elaborazione di offerte e righe di ordine cliente in Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="3fe73-186">**WarehouseId** – A warehouse is required in order to process quotations and sales order lines in Finance and Operations.</span></span> <span data-ttu-id="3fe73-187">Non è disponibile alcun valore del modello predefinito per **WarehouseId**.</span><span class="sxs-lookup"><span data-stu-id="3fe73-187">There is no default template value for **WarehouseId**.</span></span>

- <span data-ttu-id="3fe73-188">Assicurarsi che la mappa dei valori richiesti per le unità di misura (UdM) di vendita in Finance and Operations sia presente nel mapping **CDS &gt; Destinazione** per **Quantity_UOM** su **SALESUNITSYMBOL**.</span><span class="sxs-lookup"><span data-stu-id="3fe73-188">Make sure that the required value map for the selling unit of measure (UOM) in Finance and Operations exists in the **CDS &gt; Destination** mapping for **Quantity_UOM** to **SALESUNITSYMBOL**.</span></span>

## <a name="template-mapping-in-data-integrator"></a><span data-ttu-id="3fe73-189">Mapping dei modelli nell'integratore di dati</span><span class="sxs-lookup"><span data-stu-id="3fe73-189">Template mapping in data integrator</span></span>

> [!NOTE]
> - <span data-ttu-id="3fe73-190">I campi relativi a **Sconto**, **Spese** e **Imposta** sono controllati da un'impostazione complessa in Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="3fe73-190">The **Discount**, **Charges**, and **Tax** fields are controlled by a complex setup in Finance and Operations.</span></span> <span data-ttu-id="3fe73-191">Questa impostazione al momento non supporta il mapping di integrazione.</span><span class="sxs-lookup"><span data-stu-id="3fe73-191">This setup doesn't currently support integration mapping.</span></span> <span data-ttu-id="3fe73-192">Nella progettazione attuale, i campi relativi a **Prezzo**, **Sconto**, **Spese** e **Imposta** sono gestiti da Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="3fe73-192">In the current design, the **Price**, **Discount**, **Charge**, and **Tax** fields are handled by Finance and Operations.</span></span>
> - <span data-ttu-id="3fe73-193">I campi **Termini di pagamento**, **Termini di trasporto**, **Termini di consegna**, **Metodo di spedizione** e **Modalità di consegna** non sono inclusi nei mapping predefiniti.</span><span class="sxs-lookup"><span data-stu-id="3fe73-193">The **Payment terms**, **Freight terms**, **Delivery terms**, **Shipping method**, and **Delivery mode** fields aren't part of the default mappings.</span></span> <span data-ttu-id="3fe73-194">Per mappare questi campi, è necessario impostare un mapping di valori che sia specifico ai dati delle organizzazioni tra cui l'entità viene sincronizzata.</span><span class="sxs-lookup"><span data-stu-id="3fe73-194">To map these fields, you must set up a value mapping that is specific to the data in the organizations that the entity is synchronized between.</span></span>

<span data-ttu-id="3fe73-195">Nelle figure seguenti viene illustrato un esempio di un modello di mapping nell'integratore di dati.</span><span class="sxs-lookup"><span data-stu-id="3fe73-195">The following illustrations show an example of a template mapping in data integrator.</span></span>

### <a name="quoteheader"></a><span data-ttu-id="3fe73-196">QuoteHeader</span><span class="sxs-lookup"><span data-stu-id="3fe73-196">QuoteHeader</span></span>

![Mapping dei modelli nell'integratore di dati](./media/sales-quotation-template-mapping-data-integrator-1.png)

![Mapping dei modelli nell'integratore di dati](./media/sales-quotation-template-mapping-data-integrator-2.png)

### <a name="quoteline"></a><span data-ttu-id="3fe73-199">QuoteLine</span><span class="sxs-lookup"><span data-stu-id="3fe73-199">QuoteLine</span></span>

![Mapping dei modelli nell'integratore di dati](./media/sales-quotation-template-mapping-data-integrator-3.png)

![Mapping dei modelli nell'integratore di dati](./media/sales-quotation-template-mapping-data-integrator-4.png)

## <a name="related-topics"></a><span data-ttu-id="3fe73-202">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="3fe73-202">Related topics</span></span>

[<span data-ttu-id="3fe73-203">Sincronizzare i prodotti da Finance and Operations ai prodotti in Sales</span><span class="sxs-lookup"><span data-stu-id="3fe73-203">Synchronize products from Finance and Operations to products in Sales</span></span>](products-template-mapping.md)

[<span data-ttu-id="3fe73-204">Sincronizzare conti da Sales con clienti in Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="3fe73-204">Synchronize accounts from Sales to customers in Finance and Operations</span></span>](accounts-template-mapping.md)

[<span data-ttu-id="3fe73-205">Sincronizzare i contatti da Sales ai contatti o ai clienti in Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="3fe73-205">Synchronize contacts from Sales to contacts or customers in Finance and Operations</span></span>](contacts-template-mapping.md)



