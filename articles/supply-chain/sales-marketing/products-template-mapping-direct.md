---
title: Sincronizzare prodotti direttamente da Supply Chain Management con prodotti in Sales
description: Questo argomento descrive i modelli e le attività sottostanti che vengono utilizzati per sincronizzare i prodotti direttamente da Dynamics 365 Supply Chain Management in Dynamics 365 Sales.
author: ChristianRytt
manager: tfehr
ms.date: 06/10/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: crytt
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.openlocfilehash: 6ffd55585ff43f993876de6c669eb61e74a9fd79
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/17/2020
ms.locfileid: "4527316"
---
# <a name="synchronize-products-directly-from-supply-chain-management-to-products-in-sales"></a><span data-ttu-id="9dba9-103">Sincronizzare prodotti direttamente da Supply Chain Management con prodotti in Sales</span><span class="sxs-lookup"><span data-stu-id="9dba9-103">Synchronize products directly from Supply Chain Management to products in Sales</span></span>

[!include [banner](../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

> [!NOTE]
> <span data-ttu-id="9dba9-104">Prima di utilizzare la soluzione Prospect to cash, è necessario acquisire familiarità con [Integrare i dati in Common Data Service per le app](https://docs.microsoft.com/powerapps/administrator/data-integrator).</span><span class="sxs-lookup"><span data-stu-id="9dba9-104">Before you can use the Prospect to cash solution, you should be familiar with [Integrate data into Common Data Service for Apps](https://docs.microsoft.com/powerapps/administrator/data-integrator).</span></span>

<span data-ttu-id="9dba9-105">Questo argomento descrive i modelli e le attività sottostanti che vengono utilizzati per sincronizzare i prodotti direttamente da Dynamics 365 Supply Chain Management in Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="9dba9-105">This topic discusses the templates and underlying tasks that are used to synchronize products directly from Dynamics 365 Supply Chain Management to Dynamics 365 Sales.</span></span>

## <a name="data-flow-in-prospect-to-cash"></a><span data-ttu-id="9dba9-106">Flusso di dati in Prospect to cash</span><span class="sxs-lookup"><span data-stu-id="9dba9-106">Data flow in Prospect to cash</span></span>

<span data-ttu-id="9dba9-107">La soluzione Prospect to cash utilizza la funzionalità Integrazione dati per sincronizzare i dati tra istanze di Supply Chain Management e Sales.</span><span class="sxs-lookup"><span data-stu-id="9dba9-107">The Prospect to cash solution uses the Data integration feature to synchronize data across instances of Supply Chain Management and Sales.</span></span> <span data-ttu-id="9dba9-108">I modelli Prospect to cash disponibili con la funzionalità Integrazione dati consentono il flusso di dati relativo a conti, contatti, prodotti, offerte di vendita, ordini cliente e fatture di vendita tra Supply Chain Management e Sales.</span><span class="sxs-lookup"><span data-stu-id="9dba9-108">The Prospect to cash templates that are available with the Data integration feature enable the flow of data about accounts, contacts, products, sales quotations, sales orders, and sales invoices between Supply Chain Management and Sales.</span></span> <span data-ttu-id="9dba9-109">La figura seguente mostra il modo in cui i dati vengono sincronizzati tra Supply Chain Management e Sales.</span><span class="sxs-lookup"><span data-stu-id="9dba9-109">The following illustration shows how the data is synchronized between Supply Chain Management and Sales.</span></span>

<span data-ttu-id="9dba9-110">[![Flusso di dati in Prospect to cash](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)</span><span class="sxs-lookup"><span data-stu-id="9dba9-110">[![Data flow in Prospect to cash](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="9dba9-111">Modelli e attività</span><span class="sxs-lookup"><span data-stu-id="9dba9-111">Templates and tasks</span></span>

<span data-ttu-id="9dba9-112">Per accedere ai modelli disponibili, aprire l'[Interfaccia di amministrazione di Power Apps](https://admin.powerapps.com/dataintegration).</span><span class="sxs-lookup"><span data-stu-id="9dba9-112">To access the available templates, open [Power Apps Admin Center](https://admin.powerapps.com/dataintegration).</span></span> <span data-ttu-id="9dba9-113">Selezionare **Progetti**, quindi nell'angolo superiore destro, selezionare **Nuovo progetto** per selezionare i modelli pubblici.</span><span class="sxs-lookup"><span data-stu-id="9dba9-113">Select **Projects**, and then, in the upper-right corner, select **New project** to select public templates.</span></span>

<span data-ttu-id="9dba9-114">Il modello e le attività sottostanti seguenti vengono utilizzati per sincronizzare i prodotti da Supply Chain Management in Sales.</span><span class="sxs-lookup"><span data-stu-id="9dba9-114">The following template and underlying tasks are used to synchronize products from Supply Chain Management to Sales.</span></span>

- <span data-ttu-id="9dba9-115">**Nome del modello in Integrazione dati:** Prodotti (da Supply Chain Management in Sales) - Diretto</span><span class="sxs-lookup"><span data-stu-id="9dba9-115">**Name of the template in Data integration:** Products (Supply Chain Management to Sales) - Direct</span></span>
- <span data-ttu-id="9dba9-116">**Nome dell'attività nel progetto di Integrazione dati:** Prodotti</span><span class="sxs-lookup"><span data-stu-id="9dba9-116">**Name of the task in the Data integration project:** Products</span></span>

<span data-ttu-id="9dba9-117">Nessuna attività di sincronizzazione è necessaria prima della sincronizzazione dei prodotti.</span><span class="sxs-lookup"><span data-stu-id="9dba9-117">No synchronization tasks are required before product synchronization can occur.</span></span>

## <a name="entity-set"></a><span data-ttu-id="9dba9-118">Insieme di entità</span><span class="sxs-lookup"><span data-stu-id="9dba9-118">Entity set</span></span>

| <span data-ttu-id="9dba9-119">Gestione della supply chain</span><span class="sxs-lookup"><span data-stu-id="9dba9-119">Supply Chain Management</span></span>    | <span data-ttu-id="9dba9-120">Vendite</span><span class="sxs-lookup"><span data-stu-id="9dba9-120">Sales</span></span>    |
|----------------------------|----------|
| <span data-ttu-id="9dba9-121">Prodotti rilasciati di vendita</span><span class="sxs-lookup"><span data-stu-id="9dba9-121">Sellable released products</span></span> | <span data-ttu-id="9dba9-122">Prodotti</span><span class="sxs-lookup"><span data-stu-id="9dba9-122">Products</span></span> |

## <a name="entity-flow"></a><span data-ttu-id="9dba9-123">Flusso di entità</span><span class="sxs-lookup"><span data-stu-id="9dba9-123">Entity flow</span></span>

<span data-ttu-id="9dba9-124">I prodotti vengono gestiti in Supply Chain Management e sincronizzati in Sales.</span><span class="sxs-lookup"><span data-stu-id="9dba9-124">Products are managed in Supply Chain Management and synchronized to Sales.</span></span> <span data-ttu-id="9dba9-125">L'entità di dati **Prodotti rilasciati di vendita** in Supply Chain Management esporta solo prodotti *vendibili*.</span><span class="sxs-lookup"><span data-stu-id="9dba9-125">The **Sellable released products** data entity in Supply Chain Management exports only products that are *sellable*.</span></span> <span data-ttu-id="9dba9-126">I prodotti vendibili sono prodotti con le informazioni necessarie per essere utilizzati in un ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="9dba9-126">Sellable products are products that have the information that they require in order to be used on a sales order.</span></span> <span data-ttu-id="9dba9-127">Le stesse regole valgono quando un prodotto viene convalidato utilizzando la funzione **Convalida** nella pagina **Prodotto rilasciato**.</span><span class="sxs-lookup"><span data-stu-id="9dba9-127">The same rules apply when a product is validated by using the **Validate** function on the **Released product** page.</span></span>

<span data-ttu-id="9dba9-128">Il numero di prodotto viene utilizzato come una chiave.</span><span class="sxs-lookup"><span data-stu-id="9dba9-128">The product number is used as a key.</span></span> <span data-ttu-id="9dba9-129">Pertanto, quando le varianti di prodotto vengono sincronizzate in Sales, ogni variante prodotto ha un singolo ID prodotto.</span><span class="sxs-lookup"><span data-stu-id="9dba9-129">Therefore, when product variants are synchronized to Sales, each product variant has an individual product ID.</span></span>

## <a name="prospect-to-cash-solution-for-sales"></a><span data-ttu-id="9dba9-130">Soluzione Prospect to cash per Sales</span><span class="sxs-lookup"><span data-stu-id="9dba9-130">Prospect to cash solution for Sales</span></span>

<span data-ttu-id="9dba9-131">In Sales, un nuovo campo **Gestito esternamente** è stato aggiunto per i prodotti ad indicare che un determinato prodotto viene gestito esternamente.</span><span class="sxs-lookup"><span data-stu-id="9dba9-131">In Sales, a new **Is Externally Maintained** field has been added on products to indicate that a given product is maintained externally.</span></span> <span data-ttu-id="9dba9-132">Per impostazione predefinita, il valore è impostato su **Sì** durante un'importazione in Sales.</span><span class="sxs-lookup"><span data-stu-id="9dba9-132">By default, the value is set to **Yes** during an import to Sales.</span></span> <span data-ttu-id="9dba9-133">Sono disponibili i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="9dba9-133">The following values are available:</span></span>

- <span data-ttu-id="9dba9-134">**Sì** - Il prodotto deriva da Supply Chain Management e non sarà modificabile in Sales.</span><span class="sxs-lookup"><span data-stu-id="9dba9-134">**Yes** – The product originated from Supply Chain Management and won't be editable in Sales.</span></span>
- <span data-ttu-id="9dba9-135">**No** - Il prodotto è stato immesso direttamente in Sales.</span><span class="sxs-lookup"><span data-stu-id="9dba9-135">**No** – The product was entered directly in Sales.</span></span>
- <span data-ttu-id="9dba9-136">**Vuoto** - Il prodotto esisteva in Sales prima che la soluzione Prospect to cash fosse abilitata.</span><span class="sxs-lookup"><span data-stu-id="9dba9-136">**(Blank)** – The product existed in Sales before the Prospect to cash solution was enabled.</span></span>

<span data-ttu-id="9dba9-137">Il campo **Gestito esternamente** garantisce che solo le offerte e gli ordini cliente con prodotti gestiti esternamente saranno sincronizzati con Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="9dba9-137">The **Is Externally Maintained** field helps ensure that only quotations and sales orders that have externally maintained products will be synchronized to Supply Chain Management.</span></span>

<span data-ttu-id="9dba9-138">I prodotti gestiti esternamente vengono aggiunti automaticamente al primo listino prezzi valido con la stessa valuta.</span><span class="sxs-lookup"><span data-stu-id="9dba9-138">Externally maintained products are automatically added to the first valid price list that has the same currency.</span></span> <span data-ttu-id="9dba9-139">I listini prezzi sono organizzati alfabeticamente per nome.</span><span class="sxs-lookup"><span data-stu-id="9dba9-139">Price lists are organized alphabetically by name.</span></span> <span data-ttu-id="9dba9-140">Il prezzo di vendita di un prodotto da Supply Chain Management viene utilizzato come prezzo nel listino prezzi.</span><span class="sxs-lookup"><span data-stu-id="9dba9-140">The product sales price from Supply Chain Management is used as the price on the price list.</span></span> <span data-ttu-id="9dba9-141">Di conseguenza, un listino prezzi deve esistere in Sales per ogni valuta di vendita prodotti in Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="9dba9-141">Therefore, there must be a price list in Sales for every product sales currency in Supply Chain Management.</span></span> <span data-ttu-id="9dba9-142">La valuta sui prodotti vendibili rilasciati viene impostata sulla valuta di contabilità nella persona giuridica da cui il prodotto viene esportato.</span><span class="sxs-lookup"><span data-stu-id="9dba9-142">The currency on the released sellable products is set to the accounting currency in the legal entity that the product is exported from.</span></span>

> [!NOTE]
> - <span data-ttu-id="9dba9-143">La sincronizzazione del prodotto non riuscirà a meno che non sia presente un listino prezzi con una valuta corrispondente.</span><span class="sxs-lookup"><span data-stu-id="9dba9-143">Product synchronization will not succeed unless there is a price list that has a matching currency.</span></span>
> - <span data-ttu-id="9dba9-144">È possibile controllare il listino prezzi con l'integrazione mappando il pricelevelid.name [listino prezzi predefinito (nome)] nel progetto di integrazione dei dati.</span><span class="sxs-lookup"><span data-stu-id="9dba9-144">You can control the used price list with the integration by mapping the pricelevelid.name [Default Price List (Name)] in the Data Integration project.</span></span> <span data-ttu-id="9dba9-145">L'input deve essere in tutte lettere minuscole.</span><span class="sxs-lookup"><span data-stu-id="9dba9-145">The input has to be in all lowercase letters.</span></span> <span data-ttu-id="9dba9-146">Ad esempio, l'impostazione predefinita per un listino prezzi di vendita con il nome "standard" sarebbe: Campo di destinazione: pricelevelid.name [listino prezzi predefinito (nome)] e Tipo mappa: [ { "transformType": "Default", "defaultValue": "standard" } ].</span><span class="sxs-lookup"><span data-stu-id="9dba9-146">For example, the default for a price list in Sales named ‘Standard’ would be: Destination field: pricelevelid.name [Default Price List (Name)] and Map type: [ { "transformType": "Default", "defaultValue": "standard" } ].</span></span>

## <a name="preconditions-and-mapping-setup"></a><span data-ttu-id="9dba9-147">Prerequisiti e impostazioni di mapping</span><span class="sxs-lookup"><span data-stu-id="9dba9-147">Preconditions and mapping setup</span></span>

- <span data-ttu-id="9dba9-148">Prima di eseguire la prima sincronizzazione, è necessario compilare la tabella dei prodotti specifici per i prodotti esistenti in Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="9dba9-148">Before you run the synchronization for the first time, you must fill the Distinct product table for existing products in Supply Chain Management.</span></span> <span data-ttu-id="9dba9-149">I prodotti esistenti non saranno sincronizzati fino al completamento del processo.</span><span class="sxs-lookup"><span data-stu-id="9dba9-149">Existing products won't be synchronized until this job is completed.</span></span>

    1. <span data-ttu-id="9dba9-150">In Supply Chain Management utilizzare la ricerca per cercare **Compila tabella dei prodotti specifici**.</span><span class="sxs-lookup"><span data-stu-id="9dba9-150">In Supply Chain Management, use Search to search for **Populate distinct product table**.</span></span>
    2. <span data-ttu-id="9dba9-151">Selezionare **Compila tabella dei prodotti specifici** per eseguire il processo.</span><span class="sxs-lookup"><span data-stu-id="9dba9-151">Select **Populate distinct product table** to run the job.</span></span> <span data-ttu-id="9dba9-152">Questo processo deve essere eseguito una sola volta.</span><span class="sxs-lookup"><span data-stu-id="9dba9-152">This job must be run only one time.</span></span>

- <span data-ttu-id="9dba9-153">Assicurarsi che la mappa dei valori richiesti per le unità di misura (UdM) di vendita tra Supply Chain Management e Sales sia presente nel mapping di **SalesUnitSymbol** a **DefaultUnit (Name)**.</span><span class="sxs-lookup"><span data-stu-id="9dba9-153">Make sure that the required value map for the selling unit of measure (UOM) between Supply Chain Management and Sales exists in the mapping of **SalesUnitSymbol** to **DefaultUnit (Name)**.</span></span>
- <span data-ttu-id="9dba9-154">Aggiornare la mappa di valori per **Gruppo unità** (**defaultuomscheduleid.name**), di modo che corrisponda a **Gruppi unità** in Sales.</span><span class="sxs-lookup"><span data-stu-id="9dba9-154">Update the value map for **Unit group** (**defaultuomscheduleid.name**) so that it matches **Unit groups** in Sales.</span></span>

    <span data-ttu-id="9dba9-155">Il valore di modello predefinito è **Unità predefinita**.</span><span class="sxs-lookup"><span data-stu-id="9dba9-155">The default template value is **Default unit**.</span></span>

- <span data-ttu-id="9dba9-156">Assicurarsi che le UDM di vendita per tutti i prodotti da Supply Chain Management esistano in Sales.</span><span class="sxs-lookup"><span data-stu-id="9dba9-156">Make sure that the selling UOMs for all products from Supply Chain Management exist in Sales.</span></span>
- <span data-ttu-id="9dba9-157">Assicurarsi che i listini prezzi esistano in Sales per ogni valuta di vendita prodotti in Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="9dba9-157">Make sure that price lists exist in Sales for every product sales currency in Supply Chain Management.</span></span>
- <span data-ttu-id="9dba9-158">Quando i prodotti vengono creati in Sales, possono avere lo stato **Bozza** o **Attivo**.</span><span class="sxs-lookup"><span data-stu-id="9dba9-158">When products are created in Sales, they can have a status of **Draft** or **Active**.</span></span> <span data-ttu-id="9dba9-159">Il comportamento è controllato in **Impostazioni** > **Amministrazione** > **Impostazioni di sistema** > **Vendite** in Sales.</span><span class="sxs-lookup"><span data-stu-id="9dba9-159">The behavior is controlled at **Settings** > **Administration** > **System settings** > **Sales** in Sales.</span></span>

    <span data-ttu-id="9dba9-160">I prodotti il cui stato è **Bozza** quando vengono creati devono essere attivati per poter essere aggiunti alle offerte o agli ordini cliente.</span><span class="sxs-lookup"><span data-stu-id="9dba9-160">Products that have **Draft** status when they are created must be activated before they can be added to quotations or sales orders.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="9dba9-161">Mapping dei modelli in Integrazione dati</span><span class="sxs-lookup"><span data-stu-id="9dba9-161">Template mapping in Data integration</span></span>

<span data-ttu-id="9dba9-162">Nelle figure seguenti viene illustrato un esempio di un modello di mapping in Integrazione dati.</span><span class="sxs-lookup"><span data-stu-id="9dba9-162">The following illustration shows an example of a template mapping in Data integration.</span></span> 

> [!NOTE]
> <span data-ttu-id="9dba9-163">Il mapping mostra quali informazioni sui campi verranno sincronizzate da Sales in Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="9dba9-163">The mapping shows which field information will be synchronized from Sales to Supply Chain Management.</span></span>

![Mapping dei modelli nell'integratore di dati](./media/products-direct-template-mapping-data-integrator-1.png)


## <a name="related-topics"></a><span data-ttu-id="9dba9-165">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="9dba9-165">Related topics</span></span>

[<span data-ttu-id="9dba9-166">Prospect per uno scenario di liquidazione</span><span class="sxs-lookup"><span data-stu-id="9dba9-166">Prospect to cash</span></span>](prospect-to-cash.md)

[<span data-ttu-id="9dba9-167">Sincronizzare conti direttamente da Sales con clienti in Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="9dba9-167">Synchronize accounts directly from Sales to customers in Supply Chain Management</span></span>](accounts-template-mapping-direct.md)

[<span data-ttu-id="9dba9-168">Sincronizzare contatti direttamente da Sales con contatti o clienti in Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="9dba9-168">Synchronize contacts directly from Sales to contacts or customers in Supply Chain Management</span></span>](contacts-template-mapping-direct.md)

[<span data-ttu-id="9dba9-169">Sincronizzazione degli ordini cliente direttamente tra Sales e Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="9dba9-169">Synchronization of sales orders directly between Sales and Supply Chain Management</span></span>](sales-order-template-mapping-direct-two-ways.md)

[<span data-ttu-id="9dba9-170">Sincronizzare intestazioni e righe di fatture di vendita direttamente da Supply Chain Management in Sales</span><span class="sxs-lookup"><span data-stu-id="9dba9-170">Synchronize sales invoice headers and lines directly from Supply Chain Management to Sales</span></span>](sales-invoice-template-mapping-direct.md)



