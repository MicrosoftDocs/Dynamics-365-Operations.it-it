---
title: Sincronizzare i conti da Sales ai clienti in Finance and Operations
description: "L'argomento descrive i modelli e le attività sottostanti che vengono utilizzati per sincronizzare i conti da Microsoft Dynamics 365 for Sales in Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition."
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
ms.openlocfilehash: 1fdbeaaba53cd439d9872be78b1cf67cbc5a57b9
ms.contentlocale: it-it
ms.lasthandoff: 11/03/2017

---

# <a name="synchronize-accounts-from-sales-to-customers-in-finance-and-operations"></a><span data-ttu-id="83e44-103">Sincronizzare i conti da Sales ai clienti in Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="83e44-103">Synchronize accounts from Sales to customers in Finance and Operations</span></span>

[!include[banner](../includes/banner.md)]

> [!NOTE]
> <span data-ttu-id="83e44-104">Prima di utilizzare la soluzione Prospect to cash, acquisisci familiarità con [Integrazione dei dati di Microsoft Dynamics 365](/common-data-service/entity-reference/dynamics-365-integration).</span><span class="sxs-lookup"><span data-stu-id="83e44-104">Before you can use the Prospect to cash solution, be familiar with [Dynamics 365 Data Integration](/common-data-service/entity-reference/dynamics-365-integration).</span></span> 

<span data-ttu-id="83e44-105">L'argomento descrive i modelli e le attività sottostanti che vengono utilizzati per sincronizzare i conti da Microsoft Dynamics 365 for Sales (Sales) in Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition (Finance and Operations).</span><span class="sxs-lookup"><span data-stu-id="83e44-105">The topic discusses the templates and underlying tasks that are used to synchronize accounts from Microsoft Dynamics 365 for Sales (Sales) to Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (Finance and Operations).</span></span>

## <a name="template-and-task"></a><span data-ttu-id="83e44-106">Modello e attività</span><span class="sxs-lookup"><span data-stu-id="83e44-106">Template and task</span></span>

<span data-ttu-id="83e44-107">I modelli e le attività sottostanti che seguono vengono utilizzati per sincronizzare i conti da Sales in Finance and Operations:</span><span class="sxs-lookup"><span data-stu-id="83e44-107">The following templates and underlying tasks are used to synchronize accounts from Sales to Finance and Operations:</span></span>

- <span data-ttu-id="83e44-108">**Nome del modello:** account (da Sales in Fin and Ops)</span><span class="sxs-lookup"><span data-stu-id="83e44-108">**Name of the template:** Accounts (Sales to Fin and Ops)</span></span>
- <span data-ttu-id="83e44-109">**Nome dell'attività del progetto:** - Conti - Conto - Clienti</span><span class="sxs-lookup"><span data-stu-id="83e44-109">**Name of the task in the project:** Accounts - Account - Customers</span></span>

<span data-ttu-id="83e44-110">Attività di sincronizzazione richieste prima di sincronizzare Conto/Cliente: nessuna</span><span class="sxs-lookup"><span data-stu-id="83e44-110">Sync tasks required prior to Account / Customer sync: None</span></span>

## <a name="entity-set"></a><span data-ttu-id="83e44-111">Insieme di entità</span><span class="sxs-lookup"><span data-stu-id="83e44-111">Entity set</span></span>

| <span data-ttu-id="83e44-112">Vendite</span><span class="sxs-lookup"><span data-stu-id="83e44-112">Sales</span></span>    | <span data-ttu-id="83e44-113">CDS</span><span class="sxs-lookup"><span data-stu-id="83e44-113">CDS</span></span>     | <span data-ttu-id="83e44-114">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="83e44-114">Finance and Operations</span></span> |
|----------|---------|------------------------|
| <span data-ttu-id="83e44-115">Conti</span><span class="sxs-lookup"><span data-stu-id="83e44-115">Accounts</span></span> | <span data-ttu-id="83e44-116">Conto</span><span class="sxs-lookup"><span data-stu-id="83e44-116">Account</span></span> | <span data-ttu-id="83e44-117">Clienti</span><span class="sxs-lookup"><span data-stu-id="83e44-117">Customers</span></span>              |

## <a name="entity-flow"></a><span data-ttu-id="83e44-118">Flusso di entità</span><span class="sxs-lookup"><span data-stu-id="83e44-118">Entity flow</span></span>

<span data-ttu-id="83e44-119">I conti vengono gestiti in Sales e sincronizzati in Finance and Operations come clienti.</span><span class="sxs-lookup"><span data-stu-id="83e44-119">Accounts are managed in Sales and synchronized to Finance and Operations as Customers.</span></span> <span data-ttu-id="83e44-120">La proprietà **Gestito esternamente** per tali clienti è impostata su **Sì** per tenere traccia dei clienti che hanno origine da Sales.</span><span class="sxs-lookup"><span data-stu-id="83e44-120">The **Is Externally Maintained** property on these Customers is set to **Yes** to track Customers that originate from Sales.</span></span> <span data-ttu-id="83e44-121">Durante la fatturazione queste informazioni vengono utilizzate per filtrare le fatture che vengono sincronizzate in Sales.</span><span class="sxs-lookup"><span data-stu-id="83e44-121">During invoicing, this information is used to filter invoices that are synchronized to Sales.</span></span>

## <a name="prospect-to-cash-solution-for-sales"></a><span data-ttu-id="83e44-122">Soluzione Prospect to cash per Sales</span><span class="sxs-lookup"><span data-stu-id="83e44-122">Prospect to cash solution for Sales</span></span>

<span data-ttu-id="83e44-123">Il campo **Numero di conto** è disponibile nella pagina **Conto**.</span><span class="sxs-lookup"><span data-stu-id="83e44-123">The **Account Number** field is available on the **Account** page.</span></span> <span data-ttu-id="83e44-124">È stata creata una chiave naturale e univoca per supportare l'integrazione.</span><span class="sxs-lookup"><span data-stu-id="83e44-124">It has been made a natural and unique key to support the integration.</span></span> <span data-ttu-id="83e44-125">Questa funzionalità di chiave naturale della soluzione Customer Relationship Management (CRM) potrebbe influire sui clienti che utilizzano già il campo **Numero di conto**, ma che non utilizzano i valori univoci **Numero di conto** per conto.</span><span class="sxs-lookup"><span data-stu-id="83e44-125">The natural key feature of the Customer Relationship Management (CRM) solution might affect customers who already use the **Account Number** field, but who don't use unique **Account Number** values per account.</span></span> <span data-ttu-id="83e44-126">Attualmente la soluzione di integrazione non supporta questo caso.</span><span class="sxs-lookup"><span data-stu-id="83e44-126">Currently, the integration solution doesn't support this case.</span></span>

<span data-ttu-id="83e44-127">Quando un nuovo conto viene creato, se un valore **Numero di conto** non è già presente, viene generato automaticamente utilizzando una sequenza numerica.</span><span class="sxs-lookup"><span data-stu-id="83e44-127">When a new account is created, if an **Account Number** value doesn't already exist, it's automatically generated by using a number sequence.</span></span> <span data-ttu-id="83e44-128">Il valore consiste di **ACC**, seguito da una sequenza numerica crescente, quindi da un suffisso di sei caratteri.</span><span class="sxs-lookup"><span data-stu-id="83e44-128">The value consists of **ACC**, followed by an increasing number sequence and then a suffix of six characters.</span></span> <span data-ttu-id="83e44-129">Ecco un esempio: **ACC-01000-BVRCPS**</span><span class="sxs-lookup"><span data-stu-id="83e44-129">Here is an example: **ACC-01000-BVRCPS**</span></span>

<span data-ttu-id="83e44-130">Quando viene applicata la soluzione di integrazione per Sales, uno script di aggiornamento imposta il campo **Numero di conto** per i conti esistenti in Sales.</span><span class="sxs-lookup"><span data-stu-id="83e44-130">When the integration solution for Sales is applied, an upgrade script sets the **Account Number** field for existing accounts in Sales.</span></span> <span data-ttu-id="83e44-131">Se non sono presenti i valori **Numero di conto**, la sequenza numerica che è stata descritta in precedenza viene utilizzata.</span><span class="sxs-lookup"><span data-stu-id="83e44-131">If there are no **Account Number** values, the number sequence that was described earlier is used.</span></span>

## <a name="preconditions-and-mapping-setup"></a><span data-ttu-id="83e44-132">Prerequisiti e impostazioni di mapping</span><span class="sxs-lookup"><span data-stu-id="83e44-132">Preconditions and mapping setup</span></span>

- <span data-ttu-id="83e44-133">Il mapping **CustomerGroupId** da **CDS &gt; Destinazione** deve essere aggiornato con un valore valido in Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="83e44-133">**CustomerGroupId** mapping from **CDS &gt; Destination** must be updated to a valid value in Finance and Operations.</span></span> <span data-ttu-id="83e44-134">È possibile specificare un valore predefinito oppure è possibile impostare il valore utilizzando una mappa di valori.</span><span class="sxs-lookup"><span data-stu-id="83e44-134">You can specify a default value, or you can set the value by using a value map.</span></span> <span data-ttu-id="83e44-135">Il valore del modello predefinito è **10**.</span><span class="sxs-lookup"><span data-stu-id="83e44-135">The default template value is **10**.</span></span>
- <span data-ttu-id="83e44-136">**Codice paese-regione indirizzo** è obbligatorio in Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="83e44-136">**Address country region code** is required in Finance and Operations.</span></span> <span data-ttu-id="83e44-137">Per evitare errori di sincronizzazione, è possibile specificare un valore predefinito nel mapping da **CDS &gt; Destinazione**.</span><span class="sxs-lookup"><span data-stu-id="83e44-137">To avoid synchronization errors, you can specify a default value in the mapping from **CDS &gt; Destination**.</span></span> <span data-ttu-id="83e44-138">Tale valore predefinito viene quindi utilizzato se il campo viene lasciato vuoto in Sales.</span><span class="sxs-lookup"><span data-stu-id="83e44-138">That default value is then used if the field is left blank in Sales.</span></span>

    - <span data-ttu-id="83e44-139">Il valore del modello predefinito per **AddressCountryRegionISOCode** è **Stati Uniti.**</span><span class="sxs-lookup"><span data-stu-id="83e44-139">The default template value for **AddressCountryRegionISOCode** is **USA**.</span></span>
    - <span data-ttu-id="83e44-140">Il valore del modello predefinito per **DeliveryAddressCountryRegionISOCode** è **Stati Uniti.**</span><span class="sxs-lookup"><span data-stu-id="83e44-140">The default template value for **DeliveryAddressCountryRegionISOCode** is **USA**.</span></span>

- <span data-ttu-id="83e44-141">Aggiungendo i seguenti mapping da **CDS &gt; Destinazione**, è possibile consentire una riduzione del numero degli aggiornamenti manuali necessari in Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="83e44-141">By adding the following mappings from **CDS &gt; Destination**, you can help reduce the number of manual updates that are required in Finance and Operations.</span></span> <span data-ttu-id="83e44-142">È possibile utilizzare un valore predefinito o una mappa di valori da, ad esempio, **Paese** o **Città**.</span><span class="sxs-lookup"><span data-stu-id="83e44-142">You can use a default value or a value map from, for example, **Country/Region** or **City**.</span></span>

    - <span data-ttu-id="83e44-143">**SiteId** - Un sito è obbligatorio per la generazione di offerte e righe di ordine cliente in Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="83e44-143">**SiteId** – A site is required in order to generate quotations and sales order lines in Finance and Operations.</span></span> <span data-ttu-id="83e44-144">Un sito predefinito può essere preso sia dal prodotto che dall'intestazione ordine del cliente.</span><span class="sxs-lookup"><span data-stu-id="83e44-144">A default site can be taken either from the product, or from the customer from the order header.</span></span> <span data-ttu-id="83e44-145">Il valore del modello predefinito per **SiteId** è **1**.</span><span class="sxs-lookup"><span data-stu-id="83e44-145">The default template value for **SiteId** is **1**.</span></span>
    - <span data-ttu-id="83e44-146">**WarehouseId** - Un magazzino è obbligatorio per l'elaborazione di offerte e righe di ordine cliente in Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="83e44-146">**WarehouseId** – A warehouse is required in order to process quotations and sales order lines in Finance and Operations.</span></span> <span data-ttu-id="83e44-147">Un sito predefinito può essere preso sia dal prodotto che dall'intestazione ordine del cliente in Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="83e44-147">A default warehouse can be taken either from the product, or from the customer from the order header in Finance and Operations.</span></span> <span data-ttu-id="83e44-148">Il valore del modello predefinito per **WarehouseId** è **13**.</span><span class="sxs-lookup"><span data-stu-id="83e44-148">The default template value for **WarehouseId** is **13**.</span></span>
    - <span data-ttu-id="83e44-149">**LanguageId** - Una lingua è obbligatoria per la generazione di offerte e ordini cliente in Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="83e44-149">**LanguageId** – A language is required in order to generate quotations and sales orders in Finance and Operations.</span></span> <span data-ttu-id="83e44-150">Per impostazione predefinita, viene utilizzata la lingua dell'intestazione ordine del cliente.</span><span class="sxs-lookup"><span data-stu-id="83e44-150">By default, the language from the order header from the customer is used.</span></span> <span data-ttu-id="83e44-151">Il valore del modello predefinito per **LanguageId** è **en-us**.</span><span class="sxs-lookup"><span data-stu-id="83e44-151">The default template value for **LanguageId** is **en-us**.</span></span>

- <span data-ttu-id="83e44-152">Aggiornare l'ID dell'organizzazione CDS (**Organization_OrganizationId**) nel mapping **Origine &gt; CDS**.</span><span class="sxs-lookup"><span data-stu-id="83e44-152">Update the CDS organization ID (**Organization_OrganizationId**) in the **Source &gt; CDS** mapping.</span></span> <span data-ttu-id="83e44-153">Il valore del modello predefinito è **ORG001**.</span><span class="sxs-lookup"><span data-stu-id="83e44-153">The default template value is **ORG001**.</span></span>

## <a name="template-mapping-in-data-integrator"></a><span data-ttu-id="83e44-154">Mapping dei modelli nell'integratore di dati</span><span class="sxs-lookup"><span data-stu-id="83e44-154">Template mapping in data integrator</span></span>

> [!NOTE]
> <span data-ttu-id="83e44-155">I campi **Termini di pagamento**, **Termini di trasporto**, **Termini di consegna**, **Metodo di spedizione** e **Modalità di consegna** non vengono inclusi nei mapping predefiniti.</span><span class="sxs-lookup"><span data-stu-id="83e44-155">The **Payment terms**, **Freight terms**, **Delivery terms**, **Shipping method**, and **Delivery mode** fields aren't included in the default mappings.</span></span> <span data-ttu-id="83e44-156">Per mappare questi campi, è necessario impostare un mapping di valori.</span><span class="sxs-lookup"><span data-stu-id="83e44-156">To map these fields, you must set up a value mapping.</span></span> <span data-ttu-id="83e44-157">I mapping di valori sono specifici dei dati delle organizzazioni tra le quali avviene la sincronizzazione dell'entità.</span><span class="sxs-lookup"><span data-stu-id="83e44-157">Value mappings are specific to the data in the organizations that the entity is synchronized between.</span></span>

<span data-ttu-id="83e44-158">Nelle figure seguenti viene illustrato un esempio di un modello di mapping nell'integratore di dati.</span><span class="sxs-lookup"><span data-stu-id="83e44-158">The following illustrations show an example of a template mapping in data integrator.</span></span>

![Mapping dei modelli nell'integratore di dati](./media/accounts-template-mapping-data-integrator-1.png)

![Mapping dei modelli per i conti nell'integratore di dati](./media/accounts-template-mapping-data-integrator-2.png)

## <a name="related-topics"></a><span data-ttu-id="83e44-161">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="83e44-161">Related topics</span></span>

[<span data-ttu-id="83e44-162">Sincronizzare i prodotti da Finance and Operations ai prodotti in Sales</span><span class="sxs-lookup"><span data-stu-id="83e44-162">Synchronize products from Finance and Operations to products in Sales</span></span>](products-template-mapping.md)

[<span data-ttu-id="83e44-163">Sincronizzare i contatti da Sales ai contatti o ai clienti in Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="83e44-163">Synchronize contacts from Sales to contacts or customers in Finance and Operations</span></span>](contacts-template-mapping.md)

[<span data-ttu-id="83e44-164">Sincronizzare intestazioni e righe di offerte di vendita da Sales in Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="83e44-164">Synchronize sales quotation headers and lines from Sales to Finance and Operations</span></span>](sales-quotation-template-mapping.md)

[<span data-ttu-id="83e44-165">Sincronizzare intestazioni e righe di ordini di vendita da Finance and Operations in Sales</span><span class="sxs-lookup"><span data-stu-id="83e44-165">Synchronize sales order headers and lines from Finance and Operations to Sales</span></span>](sales-order-template-mapping.md)

[<span data-ttu-id="83e44-166">Sincronizzare intestazioni e righe di fatture di vendita da Finance and Operations in Sales</span><span class="sxs-lookup"><span data-stu-id="83e44-166">Synchronize sales invoice headers and lines from Finance and Operations to Sales</span></span>](sales-invoice-template-mapping.md)




