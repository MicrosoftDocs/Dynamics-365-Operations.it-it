---
title: Sincronizzare conti direttamente da Sales con clienti in Finance and Operations
description: Questo argomento descrive i modelli e le attività sottostanti che vengono utilizzati per sincronizzare i conti da Microsoft Dynamics 365 for Sales in Microsoft Dynamics 365 for Finance and Operations.
author: ChristianRytt
manager: AnnBe
ms.date: 10/25/2018
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
ms.openlocfilehash: 036389a1a52fdf15b73ab90c0a37108871a1a15e
ms.sourcegitcommit: 45f8cea6ac75bd2f4187380546a201c056072c59
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/12/2019
ms.locfileid: "1743350"
---
# <a name="synchronize-accounts-directly-from-sales-to-customers-in-finance-and-operations"></a><span data-ttu-id="20ea9-103">Sincronizzare conti direttamente da Sales con clienti in Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="20ea9-103">Synchronize accounts directly from Sales to customers in Finance and Operations</span></span>

[!include [banner](../includes/banner.md)]

> [!NOTE]
> <span data-ttu-id="20ea9-104">Prima di utilizzare la soluzione Prospect to cash, è necessario acquisire familiarità con [Integrare i dati in Common Data Service per le app](https://docs.microsoft.com/powerapps/administrator/data-integrator).</span><span class="sxs-lookup"><span data-stu-id="20ea9-104">Before you can use the Prospect to cash solution, you should be familiar with [Integrate data into Common Data Service for Apps](https://docs.microsoft.com/powerapps/administrator/data-integrator).</span></span>

<span data-ttu-id="20ea9-105">Questo argomento descrive i modelli e le attività sottostanti che vengono utilizzati per sincronizzare i conti direttamente da Microsoft Dynamics 365 for Sales in Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="20ea9-105">This topic discusses the templates and underlying tasks that are used to synchronize accounts directly from Microsoft Dynamics 365 for Sales to Microsoft Dynamics 365 for Finance and Operations.</span></span>

## <a name="data-flow-in-prospect-to-cash"></a><span data-ttu-id="20ea9-106">Flusso di dati in Prospect to cash</span><span class="sxs-lookup"><span data-stu-id="20ea9-106">Data flow in Prospect to cash</span></span>

<span data-ttu-id="20ea9-107">La soluzione Prospect to cash utilizza la funzionalità Integrazione dati per sincronizzare i dati tra istanze di Finance and Operations e Sales.</span><span class="sxs-lookup"><span data-stu-id="20ea9-107">The Prospect to cash solution uses the Data integration feature to synchronize data across instances of Finance and Operations and Sales.</span></span>  <span data-ttu-id="20ea9-108">I modelli Prospect to cash disponibili con la funzionalità Integrazione dati consentono il flusso di dati relativo a conti, contatti, prodotti, offerte di vendita, ordini cliente e fatture di vendita tra Finance and Operations e Sales.</span><span class="sxs-lookup"><span data-stu-id="20ea9-108">The Prospect to cash templates that are available with the Data integration feature enable the flow of data about accounts, contacts, products, sales quotations, sales orders, and sales invoices between Finance and Operations and Sales.</span></span> <span data-ttu-id="20ea9-109">La figura seguente mostra il modo in cui i dati vengono sincronizzati tra Finance and Operations e Sales.</span><span class="sxs-lookup"><span data-stu-id="20ea9-109">The following illustration shows how the data is synchronized between Finance and Operations and Sales.</span></span>

<span data-ttu-id="20ea9-110">[![Flusso di dati in Prospect to cash](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)</span><span class="sxs-lookup"><span data-stu-id="20ea9-110">[![Data flow in Prospect to cash](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="20ea9-111">Modelli e attività</span><span class="sxs-lookup"><span data-stu-id="20ea9-111">Templates and tasks</span></span>

<span data-ttu-id="20ea9-112">Per accedere ai modelli disponibili, aprire l'[Interfaccia di amministrazione di PowerApps](https://preview.admin.powerapps.com/dataintegration).</span><span class="sxs-lookup"><span data-stu-id="20ea9-112">To access the available templates, open [PowerApps Admin Center](https://preview.admin.powerapps.com/dataintegration).</span></span> <span data-ttu-id="20ea9-113">Selezionare **Progetti**, quindi nell'angolo superiore destro, selezionare **Nuovo progetto** per selezionare i modelli pubblici.</span><span class="sxs-lookup"><span data-stu-id="20ea9-113">Select **Projects**, and then, in the upper-right corner, select **New project** to select public templates.</span></span>

<span data-ttu-id="20ea9-114">Il seguente modello e l'attività sottostante vengono utilizzati per sincronizzare i conti da Sales in Finance and Operations:</span><span class="sxs-lookup"><span data-stu-id="20ea9-114">The following template and underlying task are used to synchronize accounts from Sales to Finance and Operations:</span></span>

- <span data-ttu-id="20ea9-115">**Nome del modello in Integrazione dati:** Conti (da Sales in Fin and Ops) - Diretto</span><span class="sxs-lookup"><span data-stu-id="20ea9-115">**Name of the template in Data integration:** Accounts (Sales to Fin and Ops) - Direct</span></span>
- <span data-ttu-id="20ea9-116">**Nome dell'attività del progetto:** Conti - Clienti</span><span class="sxs-lookup"><span data-stu-id="20ea9-116">**Name of the task in the project:** Accounts - Customers</span></span>

<span data-ttu-id="20ea9-117">Nessuna attività di sincronizzazione è necessaria prima della sincronizzazione Conto/Cliente.</span><span class="sxs-lookup"><span data-stu-id="20ea9-117">No synchronization tasks are required before Account/Customer synchronization can occur.</span></span>

## <a name="entity-set"></a><span data-ttu-id="20ea9-118">Insieme di entità</span><span class="sxs-lookup"><span data-stu-id="20ea9-118">Entity set</span></span>

| <span data-ttu-id="20ea9-119">Vendite</span><span class="sxs-lookup"><span data-stu-id="20ea9-119">Sales</span></span>    | <span data-ttu-id="20ea9-120">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="20ea9-120">Finance and Operations</span></span> |
|----------|------------------------|
| <span data-ttu-id="20ea9-121">Conti</span><span class="sxs-lookup"><span data-stu-id="20ea9-121">Accounts</span></span> | <span data-ttu-id="20ea9-122">Clienti V2</span><span class="sxs-lookup"><span data-stu-id="20ea9-122">Customers V2</span></span>           |

## <a name="entity-flow"></a><span data-ttu-id="20ea9-123">Flusso di entità</span><span class="sxs-lookup"><span data-stu-id="20ea9-123">Entity flow</span></span>

<span data-ttu-id="20ea9-124">I conti vengono gestiti in Sales e sincronizzati in Finance and Operations come clienti.</span><span class="sxs-lookup"><span data-stu-id="20ea9-124">Accounts are managed in Sales and synchronized to Finance and Operations as customers.</span></span> <span data-ttu-id="20ea9-125">La proprietà **Gestito esternamente** per tali clienti è impostata su **Sì** per tenere traccia dei clienti che hanno origine da Sales.</span><span class="sxs-lookup"><span data-stu-id="20ea9-125">The **Is Externally Maintained** property on these customers is set to **Yes** to track customers that originate from Sales.</span></span> <span data-ttu-id="20ea9-126">Durante la fatturazione queste informazioni vengono utilizzate per filtrare le fatture che vengono sincronizzate in Sales.</span><span class="sxs-lookup"><span data-stu-id="20ea9-126">During invoicing, this information is used to filter invoices that are synchronized to Sales.</span></span>

## <a name="prospect-to-cash-solution-for-sales"></a><span data-ttu-id="20ea9-127">Soluzione Prospect to cash per Sales</span><span class="sxs-lookup"><span data-stu-id="20ea9-127">Prospect to cash solution for Sales</span></span>

<span data-ttu-id="20ea9-128">Il campo **Numero di conto** è disponibile nella pagina **Conto**.</span><span class="sxs-lookup"><span data-stu-id="20ea9-128">The **Account Number** field is available on the **Account** page.</span></span> <span data-ttu-id="20ea9-129">È stata generata una chiave naturale e univoca per supportare l'integrazione.</span><span class="sxs-lookup"><span data-stu-id="20ea9-129">It has been made a natural and unique key in order to support the integration.</span></span> <span data-ttu-id="20ea9-130">Questa funzionalità di chiave naturale della soluzione Customer Relationship Management (CRM) potrebbe influire sui clienti che utilizzano già il campo **Numero di conto**, ma che non utilizzano i valori univoci **Numero di conto** per conto.</span><span class="sxs-lookup"><span data-stu-id="20ea9-130">The natural key feature of the Customer Relationship Management (CRM) solution might affect customers who already use the **Account Number** field, but who don't use unique **Account Number** values per account.</span></span> <span data-ttu-id="20ea9-131">Attualmente la soluzione di integrazione non supporta questo caso.</span><span class="sxs-lookup"><span data-stu-id="20ea9-131">Currently, the integration solution doesn't support this case.</span></span>

<span data-ttu-id="20ea9-132">Quando un nuovo conto viene creato, se un valore **Numero di conto** non è già presente, viene generato automaticamente utilizzando una sequenza numerica.</span><span class="sxs-lookup"><span data-stu-id="20ea9-132">When a new account is created, if an **Account Number** value doesn't already exist, it's automatically generated by using a number sequence.</span></span> <span data-ttu-id="20ea9-133">Il valore consiste di **ACC**, seguito da una sequenza numerica crescente, quindi da un suffisso di sei caratteri.</span><span class="sxs-lookup"><span data-stu-id="20ea9-133">The value consists of **ACC**, followed by an increasing number sequence and then a suffix of six characters.</span></span> <span data-ttu-id="20ea9-134">Ecco un esempio: **ACC-01000-BVRCPS**</span><span class="sxs-lookup"><span data-stu-id="20ea9-134">Here is an example: **ACC-01000-BVRCPS**</span></span>

<span data-ttu-id="20ea9-135">Quando viene applicata la soluzione di integrazione per Sales, uno script di aggiornamento imposta il campo **Numero di conto** per i conti esistenti in Sales.</span><span class="sxs-lookup"><span data-stu-id="20ea9-135">When the integration solution for Sales is applied, an upgrade script sets the **Account Number** field for existing accounts in Sales.</span></span> <span data-ttu-id="20ea9-136">Se non sono presenti valori **Numero di conto**, viene utilizzata la sequenza numerica menzionata in precedenza.</span><span class="sxs-lookup"><span data-stu-id="20ea9-136">If there are no **Account Number** values, the number sequence that was mentioned earlier is used.</span></span>

## <a name="preconditions-and-mapping-setup"></a><span data-ttu-id="20ea9-137">Prerequisiti e impostazioni di mapping</span><span class="sxs-lookup"><span data-stu-id="20ea9-137">Preconditions and mapping setup</span></span>

- <span data-ttu-id="20ea9-138">Il mapping **CustomerGroupId** deve essere aggiornato a un valore valido in Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="20ea9-138">The **CustomerGroupId** mapping must be updated to a valid value in Finance and Operations.</span></span> <span data-ttu-id="20ea9-139">È possibile specificare un valore predefinito oppure è possibile impostare il valore utilizzando una mappa di valori.</span><span class="sxs-lookup"><span data-stu-id="20ea9-139">You can specify a default value, or you can set the value by using a value map.</span></span>

    <span data-ttu-id="20ea9-140">Il valore del modello predefinito è **10**.</span><span class="sxs-lookup"><span data-stu-id="20ea9-140">The default template value is **10**.</span></span>

- <span data-ttu-id="20ea9-141">Aggiungendo i seguenti mapping, è possibile consentire una riduzione del numero degli aggiornamenti manuali necessari in Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="20ea9-141">By adding the following mappings, you can help reduce the number of manual updates that are required in Finance and Operations.</span></span> <span data-ttu-id="20ea9-142">È possibile utilizzare un valore predefinito o una mappa di valori da, ad esempio, **Paese** o **Città**.</span><span class="sxs-lookup"><span data-stu-id="20ea9-142">You can use a default value or a value map from, for example, **Country/Region** or **City**.</span></span>

    - <span data-ttu-id="20ea9-143">**SiteId** - Un sito è obbligatorio per la generazione di offerte e righe di ordine cliente in Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="20ea9-143">**SiteId** – A site is required in order to generate quotations and sales order lines in Finance and Operations.</span></span> <span data-ttu-id="20ea9-144">Un sito predefinito può essere preso sia dal prodotto che dall'intestazione ordine del cliente.</span><span class="sxs-lookup"><span data-stu-id="20ea9-144">A default site can be taken either from the product, or from the customer from the order header.</span></span>

        <span data-ttu-id="20ea9-145">Il valore del modello predefinito è **1**.</span><span class="sxs-lookup"><span data-stu-id="20ea9-145">The default template value is **1**.</span></span>

    - <span data-ttu-id="20ea9-146">**WarehouseId** - Un magazzino è obbligatorio per l'elaborazione di offerte e righe di ordine cliente in Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="20ea9-146">**WarehouseId** – A warehouse is required in order to process quotations and sales order lines in Finance and Operations.</span></span> <span data-ttu-id="20ea9-147">Un sito predefinito può essere preso sia dal prodotto che dall'intestazione ordine del cliente in Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="20ea9-147">A default warehouse can be taken either from the product, or from the customer from the order header in Finance and Operations.</span></span>

        <span data-ttu-id="20ea9-148">Il valore del modello predefinito è **13**.</span><span class="sxs-lookup"><span data-stu-id="20ea9-148">The default template value is **13**.</span></span>

    - <span data-ttu-id="20ea9-149">**LanguageId** - Una lingua è obbligatoria per la generazione di offerte e ordini cliente in Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="20ea9-149">**LanguageId** – A language is required in order to generate quotations and sales orders in Finance and Operations.</span></span> <span data-ttu-id="20ea9-150">Per impostazione predefinita, viene utilizzata la lingua dell'intestazione ordine del cliente.</span><span class="sxs-lookup"><span data-stu-id="20ea9-150">By default, the language from the order header from the customer is used.</span></span>

        <span data-ttu-id="20ea9-151">Il valore di modello predefinito è **en-us**.</span><span class="sxs-lookup"><span data-stu-id="20ea9-151">The default template value is **en-us**.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="20ea9-152">Mapping dei modelli in Integrazione dati</span><span class="sxs-lookup"><span data-stu-id="20ea9-152">Template mapping in Data integration</span></span>

> [!NOTE]
> <span data-ttu-id="20ea9-153">I campi **Termini di pagamento**, **Termini di trasporto**, **Termini di consegna**, **Metodo di spedizione** e **Modalità di consegna** non vengono inclusi nei mapping predefiniti.</span><span class="sxs-lookup"><span data-stu-id="20ea9-153">The **Payment terms**, **Freight terms**, **Delivery terms**, **Shipping method**, and **Delivery mode** fields aren't included in the default mappings.</span></span> <span data-ttu-id="20ea9-154">Per mappare questi campi, è necessario impostare un mapping di valori che sia specifico ai dati delle organizzazioni tra cui l'entità viene sincronizzata.</span><span class="sxs-lookup"><span data-stu-id="20ea9-154">To map these fields, you must set up a value mapping that is specific to the data in the organizations that the entity is synchronized between.</span></span>

<span data-ttu-id="20ea9-155">Nelle figure seguenti viene illustrato un esempio di mapping di modelli in Integrazione dati.</span><span class="sxs-lookup"><span data-stu-id="20ea9-155">The following illustrations show an example of a template mapping in Data integration.</span></span> 

> [!NOTE]
> <span data-ttu-id="20ea9-156">Il mapping mostra quali informazioni sui campi verranno sincronizzate da Sales in Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="20ea9-156">The mapping shows which field information will be synchronized from Sales to Finance and Operations.</span></span>

![Mapping dei modelli in Integrazione dati](./media/accounts-direct-template-mapping-data-integrator-1.png)

## <a name="related-topics"></a><span data-ttu-id="20ea9-158">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="20ea9-158">Related topics</span></span>


[<span data-ttu-id="20ea9-159">Prospect to cash</span><span class="sxs-lookup"><span data-stu-id="20ea9-159">Prospect to cash</span></span>](prospect-to-cash.md)

[<span data-ttu-id="20ea9-160">Sincronizzare conti direttamente da Sales con clienti in Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="20ea9-160">Synchronize accounts directly from Sales to customers in Finance and Operations</span></span>](accounts-template-mapping-direct.md)

[<span data-ttu-id="20ea9-161">Sincronizzare contatti direttamente da Sales con contatti o clienti in Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="20ea9-161">Synchronize contacts directly from Sales to contacts or customers in Finance and Operations</span></span>](contacts-template-mapping-direct.md)

[<span data-ttu-id="20ea9-162">Sincronizzare intestazioni e righe di ordini di vendita direttamente da Finance and Operations in Sales</span><span class="sxs-lookup"><span data-stu-id="20ea9-162">Synchronize sales order headers and lines directly from Finance and Operations to Sales</span></span>](sales-order-template-mapping-direct-two-ways.md)

[<span data-ttu-id="20ea9-163">Sincronizzare intestazioni e righe di fatture di vendita direttamente da Finance and Operations in Sales</span><span class="sxs-lookup"><span data-stu-id="20ea9-163">Synchronize sales invoice headers and lines directly from Finance and Operations to Sales</span></span>](sales-invoice-template-mapping-direct.md)

