---
title: Sincronizzare prodotti direttamente da Finance and Operations con prodotti in Sales
description: Questo argomento descrive i modelli e le attività sottostanti che vengono utilizzati per sincronizzare i prodotti da Microsoft Dynamics 365 for Finance and Operations in Microsoft Dynamics 365 for Sales.
author: ChristianRytt
manager: AnnBe
ms.date: 06/10/2019
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
ms.openlocfilehash: b4a6fab3a4831bc3d18313b351e453c615788843
ms.sourcegitcommit: 45f8cea6ac75bd2f4187380546a201c056072c59
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/12/2019
ms.locfileid: "1742426"
---
# <a name="synchronize-products-directly-from-finance-and-operations-to-products-in-sales"></a><span data-ttu-id="ad220-103">Sincronizzare prodotti direttamente da Finance and Operations con prodotti in Sales</span><span class="sxs-lookup"><span data-stu-id="ad220-103">Synchronize products directly from Finance and Operations to products in Sales</span></span>

[!include [banner](../includes/banner.md)]

> [!NOTE]
> <span data-ttu-id="ad220-104">Prima di utilizzare la soluzione Prospect to cash, è necessario acquisire familiarità con [Integrare i dati in Common Data Service per le app](https://docs.microsoft.com/powerapps/administrator/data-integrator).</span><span class="sxs-lookup"><span data-stu-id="ad220-104">Before you can use the Prospect to cash solution, you should be familiar with [Integrate data into Common Data Service for Apps](https://docs.microsoft.com/powerapps/administrator/data-integrator).</span></span>

<span data-ttu-id="ad220-105">Questo argomento descrive i modelli e le attività sottostanti che vengono utilizzati per sincronizzare i prodotti direttamente da Microsoft Dynamics 365 for Finance and Operations in Microsoft Dynamics 365 for Sales.</span><span class="sxs-lookup"><span data-stu-id="ad220-105">This topic discusses the templates and underlying tasks that are used to synchronize products directly from Microsoft Dynamics 365 for Finance and Operations, to Microsoft Dynamics 365 for Sales.</span></span>

## <a name="data-flow-in-prospect-to-cash"></a><span data-ttu-id="ad220-106">Flusso di dati in Prospect to cash</span><span class="sxs-lookup"><span data-stu-id="ad220-106">Data flow in Prospect to cash</span></span>

<span data-ttu-id="ad220-107">La soluzione Prospect to cash utilizza la funzionalità Integrazione dati per sincronizzare i dati tra istanze di Finance and Operations e Sales.</span><span class="sxs-lookup"><span data-stu-id="ad220-107">The Prospect to cash solution uses the Data integration feature to synchronize data across instances of Finance and Operations and Sales.</span></span> <span data-ttu-id="ad220-108">I modelli Prospect to cash disponibili con la funzionalità Integrazione dati consentono il flusso di dati relativo a conti, contatti, prodotti, offerte di vendita, ordini cliente e fatture di vendita tra Finance and Operations e Sales.</span><span class="sxs-lookup"><span data-stu-id="ad220-108">The Prospect to cash templates that are available with the Data integration feature enable the flow of data about accounts, contacts, products, sales quotations, sales orders, and sales invoices between Finance and Operations and Sales.</span></span> <span data-ttu-id="ad220-109">La figura seguente mostra il modo in cui i dati vengono sincronizzati tra Finance and Operations e Sales.</span><span class="sxs-lookup"><span data-stu-id="ad220-109">The following illustration shows how the data is synchronized between Finance and Operations and Sales.</span></span>

<span data-ttu-id="ad220-110">[![Flusso di dati in Prospect to cash](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)</span><span class="sxs-lookup"><span data-stu-id="ad220-110">[![Data flow in Prospect to cash](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="ad220-111">Modelli e attività</span><span class="sxs-lookup"><span data-stu-id="ad220-111">Templates and tasks</span></span>

<span data-ttu-id="ad220-112">Per accedere ai modelli disponibili, aprire l'[Interfaccia di amministrazione di PowerApps](https://admin.powerapps.com/dataintegration).</span><span class="sxs-lookup"><span data-stu-id="ad220-112">To access the available templates, open [PowerApps Admin Center](https://admin.powerapps.com/dataintegration).</span></span> <span data-ttu-id="ad220-113">Selezionare **Progetti**, quindi nell'angolo superiore destro, selezionare **Nuovo progetto** per selezionare i modelli pubblici.</span><span class="sxs-lookup"><span data-stu-id="ad220-113">Select **Projects**, and then, in the upper-right corner, select **New project** to select public templates.</span></span>

<span data-ttu-id="ad220-114">Il modello e le attività sottostanti seguenti vengono utilizzati per sincronizzare i prodotti da Finance and Operations in Sales.</span><span class="sxs-lookup"><span data-stu-id="ad220-114">The following template and underlying tasks are used to synchronize products from Finance and Operations to Sales.</span></span>

- <span data-ttu-id="ad220-115">**Nome del modello in Integrazione dati:** Prodotti (da Fin and Ops in Sales) - Diretto</span><span class="sxs-lookup"><span data-stu-id="ad220-115">**Name of the template in Data integration:** Products (Fin and Ops to Sales) - Direct</span></span>
- <span data-ttu-id="ad220-116">**Nome dell'attività nel progetto di Integrazione dati:** Prodotti</span><span class="sxs-lookup"><span data-stu-id="ad220-116">**Name of the task in the Data integration project:** Products</span></span>

<span data-ttu-id="ad220-117">Nessuna attività di sincronizzazione è necessaria prima della sincronizzazione dei prodotti.</span><span class="sxs-lookup"><span data-stu-id="ad220-117">No synchronization tasks are required before product synchronization can occur.</span></span>

## <a name="entity-set"></a><span data-ttu-id="ad220-118">Insieme di entità</span><span class="sxs-lookup"><span data-stu-id="ad220-118">Entity set</span></span>

| <span data-ttu-id="ad220-119">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="ad220-119">Finance and Operations</span></span>     | <span data-ttu-id="ad220-120">Vendite</span><span class="sxs-lookup"><span data-stu-id="ad220-120">Sales</span></span>    |
|----------------------------|----------|
| <span data-ttu-id="ad220-121">Prodotti rilasciati di vendita</span><span class="sxs-lookup"><span data-stu-id="ad220-121">Sellable released products</span></span> | <span data-ttu-id="ad220-122">Prodotti</span><span class="sxs-lookup"><span data-stu-id="ad220-122">Products</span></span> |

## <a name="entity-flow"></a><span data-ttu-id="ad220-123">Flusso di entità</span><span class="sxs-lookup"><span data-stu-id="ad220-123">Entity flow</span></span>

<span data-ttu-id="ad220-124">I prodotti vengono gestiti in Finance and Operations e sincronizzati in Sales.</span><span class="sxs-lookup"><span data-stu-id="ad220-124">Products are managed in Finance and Operations and synchronized to Sales.</span></span> <span data-ttu-id="ad220-125">L'entità di dati **Prodotti rilasciati di vendita** in Finance and Operations esporta solo prodotti *vendibili*.</span><span class="sxs-lookup"><span data-stu-id="ad220-125">The **Sellable released products** data entity in Finance and Operations exports only products that are *sellable*.</span></span> <span data-ttu-id="ad220-126">I prodotti vendibili sono prodotti con le informazioni necessarie per essere utilizzati in un ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="ad220-126">Sellable products are products that have the information that they require in order to be used on a sales order.</span></span> <span data-ttu-id="ad220-127">Le stesse regole valgono quando un prodotto viene convalidato utilizzando la funzione **Convalida** nella pagina **Prodotto rilasciato**.</span><span class="sxs-lookup"><span data-stu-id="ad220-127">The same rules apply when a product is validated by using the **Validate** function on the **Released product** page.</span></span>

<span data-ttu-id="ad220-128">Il numero di prodotto viene utilizzato come una chiave.</span><span class="sxs-lookup"><span data-stu-id="ad220-128">The product number is used as a key.</span></span> <span data-ttu-id="ad220-129">Pertanto, quando le varianti di prodotto vengono sincronizzate in Sales, ogni variante prodotto ha un singolo ID prodotto.</span><span class="sxs-lookup"><span data-stu-id="ad220-129">Therefore, when product variants are synchronized to Sales, each product variant has an individual product ID.</span></span>

## <a name="prospect-to-cash-solution-for-sales"></a><span data-ttu-id="ad220-130">Soluzione Prospect to cash per Sales</span><span class="sxs-lookup"><span data-stu-id="ad220-130">Prospect to cash solution for Sales</span></span>

<span data-ttu-id="ad220-131">In Sales, un nuovo campo **Gestito esternamente** è stato aggiunto per i prodotti ad indicare che un determinato prodotto viene gestito esternamente.</span><span class="sxs-lookup"><span data-stu-id="ad220-131">In Sales, a new **Is Externally Maintained** field has been added on products to indicate that a given product is maintained externally.</span></span> <span data-ttu-id="ad220-132">Per impostazione predefinita, il valore è impostato su **Sì** durante un'importazione in Sales.</span><span class="sxs-lookup"><span data-stu-id="ad220-132">By default, the value is set to **Yes** during an import to Sales.</span></span> <span data-ttu-id="ad220-133">Sono disponibili i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="ad220-133">The following values are available:</span></span>

- <span data-ttu-id="ad220-134">**Sì** - Il prodotto deriva da Finance and Operations e non sarà modificabile in Sales.</span><span class="sxs-lookup"><span data-stu-id="ad220-134">**Yes** – The product originated from Finance and Operations and won't be editable in Sales.</span></span>
- <span data-ttu-id="ad220-135">**No** - Il prodotto è stato immesso direttamente in Sales.</span><span class="sxs-lookup"><span data-stu-id="ad220-135">**No** – The product was entered directly in Sales.</span></span>
- <span data-ttu-id="ad220-136">**Vuoto** - Il prodotto esisteva in Sales prima che la soluzione Prospect to cash fosse abilitata.</span><span class="sxs-lookup"><span data-stu-id="ad220-136">**(Blank)** – The product existed in Sales before the Prospect to cash solution was enabled.</span></span>

<span data-ttu-id="ad220-137">Il campo **Gestito esternamente** garantisce che solo le offerte e gli ordini cliente con prodotti gestiti esternamente saranno sincronizzati con Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="ad220-137">The **Is Externally Maintained** field helps guarantee that only quotations and sales orders that have externally maintained products will be synchronized to Finance and Operations.</span></span>

<span data-ttu-id="ad220-138">I prodotti gestiti esternamente vengono aggiunti automaticamente al primo listino prezzi valido con la stessa valuta.</span><span class="sxs-lookup"><span data-stu-id="ad220-138">Externally maintained products are automatically added to the first valid price list that has the same currency.</span></span> <span data-ttu-id="ad220-139">I listini prezzi sono organizzati alfabeticamente per nome.</span><span class="sxs-lookup"><span data-stu-id="ad220-139">Price lists are organized alphabetically by name.</span></span> <span data-ttu-id="ad220-140">Il prezzo di vendita di un prodotto da Finance and Operations viene utilizzato come prezzo nel listino prezzi.</span><span class="sxs-lookup"><span data-stu-id="ad220-140">The product sales price from Finance and Operations is used as the price on the price list.</span></span> <span data-ttu-id="ad220-141">Di conseguenza, un listino prezzi deve esistere in Sales per ogni valuta di vendita prodotti in Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="ad220-141">Therefore, there must be a price list in Sales for every product sales currency in Finance and Operations.</span></span> <span data-ttu-id="ad220-142">La valuta sui prodotti vendibili rilasciati viene impostata sulla valuta di contabilità nella persona giuridica da cui il prodotto viene esportato.</span><span class="sxs-lookup"><span data-stu-id="ad220-142">The currency on the released sellable products is set to the accounting currency in the legal entity that the product is exported from.</span></span>

> [!NOTE]
> - <span data-ttu-id="ad220-143">La sincronizzazione del prodotto non riuscirà a meno che non sia presente un listino prezzi con una valuta corrispondente.</span><span class="sxs-lookup"><span data-stu-id="ad220-143">Product synchronization will not succeed unless there is a price list that has a matching currency.</span></span>
> - <span data-ttu-id="ad220-144">È possibile controllare il listino prezzi con l'integrazione mappando il pricelevelid.name [listino prezzi predefinito (nome)] nel progetto di integrazione dei dati.</span><span class="sxs-lookup"><span data-stu-id="ad220-144">You can control the used price list with the integration by mapping the pricelevelid.name [Default Price List (Name)] in the Data Integration project.</span></span> <span data-ttu-id="ad220-145">L'input deve essere in tutte lettere minuscole.</span><span class="sxs-lookup"><span data-stu-id="ad220-145">The input has to be in all lowercase letters.</span></span> <span data-ttu-id="ad220-146">Ad esempio, l'impostazione predefinita per un listino prezzi di vendita con il nome "standard" sarebbe: Campo di destinazione: pricelevelid.name [listino prezzi predefinito (nome)] e Tipo mappa: [ { "transformType": "Default", "defaultValue": "standard" } ].</span><span class="sxs-lookup"><span data-stu-id="ad220-146">For example, the default for a price list in Sales named ‘Standard’ would be: Destination field: pricelevelid.name [Default Price List (Name)] and Map type: [ { "transformType": "Default", "defaultValue": "standard" } ].</span></span>

## <a name="preconditions-and-mapping-setup"></a><span data-ttu-id="ad220-147">Prerequisiti e impostazioni di mapping</span><span class="sxs-lookup"><span data-stu-id="ad220-147">Preconditions and mapping setup</span></span>

- <span data-ttu-id="ad220-148">Prima di eseguire la prima sincronizzazione, è necessario compilare la tabella dei prodotti specifici per i prodotti esistenti in Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="ad220-148">Before you run the synchronization for the first time, you must fill the Distinct product table for existing products in Finance and Operations.</span></span> <span data-ttu-id="ad220-149">I prodotti esistenti non saranno sincronizzati fino al completamento del processo.</span><span class="sxs-lookup"><span data-stu-id="ad220-149">Existing products won't be synchronized until this job is completed.</span></span>

    1. <span data-ttu-id="ad220-150">In Finance and Operations utilizzare la ricerca per cercare **Compila tabella dei prodotti specifici**.</span><span class="sxs-lookup"><span data-stu-id="ad220-150">In Finance and Operations, use Search to search for **Populate distinct product table**.</span></span>
    2. <span data-ttu-id="ad220-151">Selezionare **Compila tabella dei prodotti specifici** per eseguire il processo.</span><span class="sxs-lookup"><span data-stu-id="ad220-151">Select **Populate distinct product table** to run the job.</span></span> <span data-ttu-id="ad220-152">Questo processo deve essere eseguito una sola volta.</span><span class="sxs-lookup"><span data-stu-id="ad220-152">This job must be run only one time.</span></span>

- <span data-ttu-id="ad220-153">Assicurarsi che la mappa dei valori richiesti per le unità di misura (UdM) di vendita tra Finance and Operations e Sales sia presente nel mapping di **SalesUnitSymbol** a **DefaultUnit (Name)**.</span><span class="sxs-lookup"><span data-stu-id="ad220-153">Make sure that the required value map for the selling unit of measure (UOM) between Finance and Operations and Sales exists in the mapping of **SalesUnitSymbol** to **DefaultUnit (Name)**.</span></span>
- <span data-ttu-id="ad220-154">Aggiornare la mappa di valori per **Gruppo unità** (**defaultuomscheduleid.name**), di modo che corrisponda a **Gruppi unità** in Sales.</span><span class="sxs-lookup"><span data-stu-id="ad220-154">Update the value map for **Unit group** (**defaultuomscheduleid.name**) so that it matches **Unit groups** in Sales.</span></span>

    <span data-ttu-id="ad220-155">Il valore di modello predefinito è **Unità predefinita**.</span><span class="sxs-lookup"><span data-stu-id="ad220-155">The default template value is **Default unit**.</span></span>

- <span data-ttu-id="ad220-156">Assicurarsi che le UDM di vendita per tutti i prodotti da Finance and Operations esistano in Sales.</span><span class="sxs-lookup"><span data-stu-id="ad220-156">Make sure that the selling UOMs for all products from Finance and Operations exist in Sales.</span></span>
- <span data-ttu-id="ad220-157">Assicurarsi che i listini prezzi esistano in Sales per ogni valuta di vendita prodotti in Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="ad220-157">Make sure that price lists exist in Sales for every product sales currency in Finance and Operations.</span></span>
- <span data-ttu-id="ad220-158">Quando i prodotti vengono creati in Sales, possono avere lo stato **Bozza** o **Attivo**.</span><span class="sxs-lookup"><span data-stu-id="ad220-158">When products are created in Sales, they can have a status of **Draft** or **Active**.</span></span> <span data-ttu-id="ad220-159">Il comportamento è controllato in **Impostazioni** > **Amministrazione** > **Impostazioni di sistema** > **Vendite** in Sales.</span><span class="sxs-lookup"><span data-stu-id="ad220-159">The behavior is controlled at **Settings** > **Administration** > **System settings** > **Sales** in Sales.</span></span>

    <span data-ttu-id="ad220-160">I prodotti il cui stato è **Bozza** quando vengono creati devono essere attivati per poter essere aggiunti alle offerte o agli ordini cliente.</span><span class="sxs-lookup"><span data-stu-id="ad220-160">Products that have **Draft** status when they are created must be activated before they can be added to quotations or sales orders.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="ad220-161">Mapping dei modelli in Integrazione dati</span><span class="sxs-lookup"><span data-stu-id="ad220-161">Template mapping in Data integration</span></span>

<span data-ttu-id="ad220-162">Nelle figure seguenti viene illustrato un esempio di un modello di mapping in Integrazione dati.</span><span class="sxs-lookup"><span data-stu-id="ad220-162">The following illustration shows an example of a template mapping in Data integration.</span></span> 

> [!NOTE]
> <span data-ttu-id="ad220-163">Il mapping mostra quali informazioni sui campi verranno sincronizzate da Sales in Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="ad220-163">The mapping shows which field information will be synchronized from Sales to Finance and Operations.</span></span>

![Mapping dei modelli nell'integratore di dati](./media/products-direct-template-mapping-data-integrator-1.png)


## <a name="related-topics"></a><span data-ttu-id="ad220-165">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="ad220-165">Related topics</span></span>

[<span data-ttu-id="ad220-166">Prospect to cash</span><span class="sxs-lookup"><span data-stu-id="ad220-166">Prospect to cash</span></span>](prospect-to-cash.md)

[<span data-ttu-id="ad220-167">Sincronizzare conti direttamente da Sales con clienti in Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="ad220-167">Synchronize accounts directly from Sales to customers in Finance and Operations</span></span>](accounts-template-mapping-direct.md)

[<span data-ttu-id="ad220-168">Sincronizzare contatti direttamente da Sales con contatti o clienti in Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="ad220-168">Synchronize contacts directly from Sales to contacts or customers in Finance and Operations</span></span>](contacts-template-mapping-direct.md)

[<span data-ttu-id="ad220-169">Sincronizzare intestazioni e righe di ordini di vendita direttamente da Finance and Operations in Sales</span><span class="sxs-lookup"><span data-stu-id="ad220-169">Synchronize sales order headers and lines directly from Finance and Operations to Sales</span></span>](sales-order-template-mapping-direct-two-ways.md)

[<span data-ttu-id="ad220-170">Sincronizzare intestazioni e righe di fatture di vendita direttamente da Finance and Operations in Sales</span><span class="sxs-lookup"><span data-stu-id="ad220-170">Synchronize sales invoice headers and lines directly from Finance and Operations to Sales</span></span>](sales-invoice-template-mapping-direct.md)



