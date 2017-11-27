---
title: Sincronizzare i prodotti da Finance and Operations ai prodotti In Sales
description: "Questo argomento descrive i modelli e le attività sottostanti che vengono utilizzati per sincronizzare i prodotti da Microsoft Dynamics 365 for Finance and Operations, Enterprise edition in Microsoft Dynamics 365 for Sales."
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
ms.openlocfilehash: 405a6cf9f3e6cc52925ff7d9f10836196343c36b
ms.contentlocale: it-it
ms.lasthandoff: 11/03/2017

---

# <a name="synchronize-products-from-finance-and-operations-to-products-in-sales"></a><span data-ttu-id="bbda1-103">Sincronizzare i prodotti da Finance and Operations ai prodotti In Sales</span><span class="sxs-lookup"><span data-stu-id="bbda1-103">Synchronize products from Finance and Operations to products in Sales</span></span>

[!include[banner](../includes/banner.md)]

> [!NOTE]
> <span data-ttu-id="bbda1-104">Prima di utilizzare la soluzione Prospect to cash, acquisisci familiarità con [Integrazione dei dati di Microsoft Dynamics 365](/common-data-service/entity-reference/dynamics-365-integration).</span><span class="sxs-lookup"><span data-stu-id="bbda1-104">Before you can use the Prospect to cash solution, be familiar with [Dynamics 365 Data Integration](/common-data-service/entity-reference/dynamics-365-integration).</span></span> 

<span data-ttu-id="bbda1-105">Questo argomento descrive i modelli e le attività sottostanti che vengono utilizzati per sincronizzare i prodotti da Microsoft Dynamics 365 for Finance and Operations, Enterprise edition in Microsoft Dynamics 365 for Sales.</span><span class="sxs-lookup"><span data-stu-id="bbda1-105">This topic discusses the templates and underlying tasks that are used to synchronize products from Microsoft Dynamics 365 for Finance and Operations, Enterprise edition to Microsoft Dynamics 365 for Sales.</span></span>

## <a name="template-and-task"></a><span data-ttu-id="bbda1-106">Modello e attività</span><span class="sxs-lookup"><span data-stu-id="bbda1-106">Template and task</span></span>

<span data-ttu-id="bbda1-107">I seguenti modelli e le seguenti attività sottostanti vengono utilizzati per sincronizzare i prodotti da Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (Finance and Operations) in Microsoft Dynamics 365 for Sales (Sales).</span><span class="sxs-lookup"><span data-stu-id="bbda1-107">The following templates and underlying tasks are used to synchronize products from Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (Finance and Operations) to Microsoft Dynamics 365 for Sales (Sales).</span></span>

-   <span data-ttu-id="bbda1-108">Nome del modello: Prodotti (da Fin and Ops in Sales)</span><span class="sxs-lookup"><span data-stu-id="bbda1-108">Name of template: Products (Fin and Ops to Sales)</span></span>

-   <span data-ttu-id="bbda1-109">Nome dell'attività del progetto: Prodotti</span><span class="sxs-lookup"><span data-stu-id="bbda1-109">Name of task in project: Products</span></span>

<span data-ttu-id="bbda1-110">Attività di sincronizzazione richieste prima di sincronizzare i prodotti: nessuna</span><span class="sxs-lookup"><span data-stu-id="bbda1-110">Sync tasks required prior to Product sync: None</span></span>

## <a name="entity-set"></a><span data-ttu-id="bbda1-111">Insieme di entità</span><span class="sxs-lookup"><span data-stu-id="bbda1-111">Entity set</span></span>

| <span data-ttu-id="bbda1-112">**Finance and Operations**</span><span class="sxs-lookup"><span data-stu-id="bbda1-112">**Finance and Operations**</span></span> | <span data-ttu-id="bbda1-113">**CDS**</span><span class="sxs-lookup"><span data-stu-id="bbda1-113">**CDS**</span></span> | <span data-ttu-id="bbda1-114">**Vendite**</span><span class="sxs-lookup"><span data-stu-id="bbda1-114">**Sales**</span></span>  |
|----------------------------|---------|------------|
| <span data-ttu-id="bbda1-115">Prodotti rilasciati di vendita</span><span class="sxs-lookup"><span data-stu-id="bbda1-115">Sellable released products</span></span> | <span data-ttu-id="bbda1-116">Prodotto</span><span class="sxs-lookup"><span data-stu-id="bbda1-116">Product</span></span> | <span data-ttu-id="bbda1-117">Prodotti</span><span class="sxs-lookup"><span data-stu-id="bbda1-117">Products</span></span>   |

## <a name="entity-flow"></a><span data-ttu-id="bbda1-118">Flusso di entità</span><span class="sxs-lookup"><span data-stu-id="bbda1-118">Entity flow</span></span>

<span data-ttu-id="bbda1-119">I prodotti vengono gestiti in Finance and Operations e sincronizzati con Sales.</span><span class="sxs-lookup"><span data-stu-id="bbda1-119">Products are managed in Finance and Operations and synchronized to Sales.</span></span> <span data-ttu-id="bbda1-120">L'entità di dati **Prodotti rilasciati di vendita** in Finance and Operations esporta solo i prodotti che sono vendibili, ovvero i prodotti che hanno le informazioni necessarie per essere utilizzati in un ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="bbda1-120">The data entity **Sellable released products** in Finance and Operations only exports products that are sellable, which means that products have the information required to be used on a sales order.</span></span> <span data-ttu-id="bbda1-121">Le stesse regole valgono quando un prodotto viene convalidato con la funzione **Convalida** nella pagina **Prodotto rilasciato**.</span><span class="sxs-lookup"><span data-stu-id="bbda1-121">The same rules apply when a product is validated with the **Validate** function on the **Released product** page.</span></span>

<span data-ttu-id="bbda1-122">Il **Numero prodotto** viene utilizzato come chiave. Ciò significa che le varianti di prodotto vengono sincronizzate in CDS e Sales con **ID prodotto** singoli per **Variante prodotto**.</span><span class="sxs-lookup"><span data-stu-id="bbda1-122">The **Product number** is used as key, meaning that product variants are synchronized to CDS and Sales with individual **Product IDs** per **Product variant**.</span></span>

## <a name="prospect-to-cash-solution-for-sales"></a><span data-ttu-id="bbda1-123">Soluzione Prospect to cash per Sales</span><span class="sxs-lookup"><span data-stu-id="bbda1-123">Prospect to cash solution for Sales</span></span>

<span data-ttu-id="bbda1-124">In Sales viene aggiunto un nuovo campo nei prodotti **Gestito esternamente** per indicare che un determinato prodotto viene gestito esternamente.</span><span class="sxs-lookup"><span data-stu-id="bbda1-124">In Sales, a new field on the products **Is Externally Maintained** is added to indicate that a given product is maintained externally.</span></span> <span data-ttu-id="bbda1-125">Il valore è impostato su **Sì** per impostazione predefinita durante l'importazione in Sales.</span><span class="sxs-lookup"><span data-stu-id="bbda1-125">The value is set to **Yes** by default during import to Sales.</span></span>

-   <span data-ttu-id="bbda1-126">**Gestito esternamente = Sì**: il prodotto deriva da Finance and Operations e non sarà modificabile in Sales.</span><span class="sxs-lookup"><span data-stu-id="bbda1-126">**Is Externally Maintained = Yes**: Product originates from Finance and Operations and will not be editable in Sales.</span></span>

-   <span data-ttu-id="bbda1-127">**Gestito esternamente = No**: il prodotto viene immesso direttamente in Sales.</span><span class="sxs-lookup"><span data-stu-id="bbda1-127">**Is Externally Maintained = No**: Product is entered directly in Sales.</span></span>

-   <span data-ttu-id="bbda1-128">**Gestito esternamente = vuoto**: il prodotto esisteva in Sales prima di abilitare la soluzione Prospect to cash.</span><span class="sxs-lookup"><span data-stu-id="bbda1-128">**Is Externally Maintained = Blank**: Product exists in Sales prior to enabling the Prospect to cash solution.</span></span>

<span data-ttu-id="bbda1-129">Le informazioni di **Gestito esternamente** vengono utilizzate per garantire che solo **Quote** e **Ordini cliente** con **Prodotti gestiti esternamente** saranno sincronizzati in Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="bbda1-129">The **Is Externally Maintained** information is used to ensure that only **Quotes** and **Sales orders** with **Externally maintained products** will sync to Finance and Operations.</span></span>

<span data-ttu-id="bbda1-130">I **Prodotti gestiti esternamente** vengono aggiunti automaticamente al primo **Listino prezzi** valido con la stessa valuta.</span><span class="sxs-lookup"><span data-stu-id="bbda1-130">**Externally maintained products** are automatically added to the first valid **Price list** with the same currency.</span></span> <span data-ttu-id="bbda1-131">Notare che il listino è organizzato alfabeticamente in base al **Nome**,</span><span class="sxs-lookup"><span data-stu-id="bbda1-131">Note that the list is organized alphabetically by **Name**.</span></span> <span data-ttu-id="bbda1-132">Il prezzo di vendita di un prodotto da Finance and Operations viene utilizzato come prezzo nel **Listino prezzi**.</span><span class="sxs-lookup"><span data-stu-id="bbda1-132">The product sales price from Finance and Operations is used as price on the **Price list**.</span></span> <span data-ttu-id="bbda1-133">Ciò significa che è necessario disporre di un **Listino prezzi** in Sales per ogni **Valuta di vendita di prodotti** in Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="bbda1-133">This means that it is required to have a **Price list** in Sales for each **Product sales currency** in Finance and Operations.</span></span> <span data-ttu-id="bbda1-134">La valuta sui prodotti vendibili rilasciati viene impostata sulla valuta di contabilità nella persona giuridica da cui il prodotto viene esportato.</span><span class="sxs-lookup"><span data-stu-id="bbda1-134">Currency on the released sellable products is set to the accounting currency in the legal entity, from which the product is exported.</span></span>

> [!NOTE]
> <span data-ttu-id="bbda1-135">La sincronizzazione del prodotto non riuscirà senza un **Listino prezzi** con valuta corrispondente.</span><span class="sxs-lookup"><span data-stu-id="bbda1-135">Product sync will not succeed without a **Price list** with the matching currency.</span></span>

## <a name="preconditions-and-mapping-setup"></a><span data-ttu-id="bbda1-136">Prerequisiti e impostazioni di mapping</span><span class="sxs-lookup"><span data-stu-id="bbda1-136">Preconditions and mapping setup</span></span>

-   <span data-ttu-id="bbda1-137">Prima di eseguire la primissima sincronizzazione, è necessario compilare la **Tabella dei prodotti specifici** per i prodotti esistenti in Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="bbda1-137">Before you run the very first sync, you must populate the **Distinct product table** for existing products in Finance and Operations.</span></span> <span data-ttu-id="bbda1-138">I prodotti esistenti non saranno sincronizzati fino al completamento del processo.</span><span class="sxs-lookup"><span data-stu-id="bbda1-138">Existing products will not be synchronized until this job is completed.</span></span>

    -   <span data-ttu-id="bbda1-139">In Finance and Operations utilizzare la ricerca per cercare **Compila tabella dei prodotti specifici**.</span><span class="sxs-lookup"><span data-stu-id="bbda1-139">In Finance and Operations, use Search to search for **Populate distinct product table**.</span></span>

    -   <span data-ttu-id="bbda1-140">Fare clic su **Compila tabella dei prodotti specifici** per eseguire il processo.</span><span class="sxs-lookup"><span data-stu-id="bbda1-140">Click the **Populate distinct product table** to run the job.</span></span> <span data-ttu-id="bbda1-141">Il processo deve essere eseguito una sola volta.</span><span class="sxs-lookup"><span data-stu-id="bbda1-141">This job only needs to be run once.</span></span>

-   <span data-ttu-id="bbda1-142">Assicurarsi che la **ValueMap** necessaria per l'**Unità di misura** (UDM) di vendita in Finance and Operations sia presente in **Origine -\> Mapping CDS SalesUnitSymbol/DefaultSellingUnitOfMeasure**.</span><span class="sxs-lookup"><span data-stu-id="bbda1-142">Ensure that the needed **ValueMap** for selling **Unit of measure** (UOM) in Finance and Operations exists in the **Source -\> CDS mapping SalesUnitSymbol / DefaultSellingUnitOfMeasure**.</span></span>

-   <span data-ttu-id="bbda1-143">Aggiornare **ID organizzazione CDS Organization_OrganizationId** in **Origine -\> CDS**.</span><span class="sxs-lookup"><span data-stu-id="bbda1-143">Update the **CDS Organization ID Organization_OrganizationId** in **Source -\> CDS**.</span></span>

    -   <span data-ttu-id="bbda1-144">Il valore predefinito del modello è ORG001.</span><span class="sxs-lookup"><span data-stu-id="bbda1-144">Template value is defaulted to ORG001.</span></span>

-   <span data-ttu-id="bbda1-145">Aggiornare **ValueMap** per **Gruppo unità** (**defaultuomscheduleid.name**) in **CDS -\> destinazione** in modo che corrisponda **Gruppi unità** in Sales.</span><span class="sxs-lookup"><span data-stu-id="bbda1-145">Update **ValueMap** for **Unit group** (**defaultuomscheduleid.name**) in **CDS -\> Destination** to match the **Unit groups** in Sales.</span></span>

    -   <span data-ttu-id="bbda1-146">Il valore predefinito del modello è **Unità predefinita**.</span><span class="sxs-lookup"><span data-stu-id="bbda1-146">Template value is defaulted to **Default unit**.</span></span>

-   <span data-ttu-id="bbda1-147">Assicurarsi che tutte le UDM di vendita dei prodotti da Finance and Operations esistano in Sales con il valore **Distinte di prelievo CDS**.</span><span class="sxs-lookup"><span data-stu-id="bbda1-147">Ensure that all products selling UOMs from Finance and Operations exist in Sales with the **CDS picklists** value.</span></span>

-   <span data-ttu-id="bbda1-148">Assicurarsi che **Listini prezzi** sia presente in Sales per ogni valuta di vendita prodotti in Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="bbda1-148">Ensure that **Price lists** exist in Sales for each product sales currency in Finance and Operations.</span></span>

-   <span data-ttu-id="bbda1-149">I prodotti possono essere creati in Sales con stato **Bozza** o **Attivo**.</span><span class="sxs-lookup"><span data-stu-id="bbda1-149">Products can be created in Sales with status **Draft** or **Active**.</span></span> <span data-ttu-id="bbda1-150">Tale opzione è controllata in **Impostazioni di sistema** in **Sales** in Sales.</span><span class="sxs-lookup"><span data-stu-id="bbda1-150">This is controlled in **System settings** under **Sales** in Sales.</span></span>

    -   <span data-ttu-id="bbda1-151">I prodotti creati con lo stato di bozza devono essere attivati prima di potere essere aggiunti a **Quota** o **Ordine cliente**.</span><span class="sxs-lookup"><span data-stu-id="bbda1-151">Products created with draft status need to be activated before they can be added to **Quote** or **Sales order**.</span></span>

## <a name="template-mapping-in-data-integrator"></a><span data-ttu-id="bbda1-152">Mapping dei modelli nell'integratore di dati</span><span class="sxs-lookup"><span data-stu-id="bbda1-152">Template mapping in data integrator</span></span>

<span data-ttu-id="bbda1-153">Nelle figure seguenti viene illustrato un esempio di un modello di mapping nell'integratore di dati.</span><span class="sxs-lookup"><span data-stu-id="bbda1-153">The following illustrations show an example of a template mapping in data integrator.</span></span>

![Mapping dei modelli nell'integratore di dati](./media/products-template-mapping-data-integrator-1.png)

![Mapping dei modelli per prodotti nell'integratore di dati](./media/products-template-mapping-data-integrator-2.png)

## <a name="related-topics"></a><span data-ttu-id="bbda1-156">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="bbda1-156">Related topics</span></span>

[<span data-ttu-id="bbda1-157">Sincronizzare conti da Sales a clienti in Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="bbda1-157">Synchronize accounts from Sales to customers in Finance and Operations</span></span>](accounts-template-mapping.md)

[<span data-ttu-id="bbda1-158">Sincronizzare contatti da Sales con contatti o clienti in Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="bbda1-158">Synchronize contacts from Sales to contacts or customers in Finance and Operations</span></span>](contacts-template-mapping.md)

[<span data-ttu-id="bbda1-159">Sincronizzare intestazioni e righe di offerte di vendita da Sales in Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="bbda1-159">Synchronize sales quotation headers and lines from Sales to Finance and Operations</span></span>](sales-quotation-template-mapping.md)

[<span data-ttu-id="bbda1-160">Sincronizzare intestazioni e righe di ordini cliente da Finance and Operations in Sales</span><span class="sxs-lookup"><span data-stu-id="bbda1-160">Synchronize sales order headers and lines from Finance and Operations to Sales</span></span>](sales-order-template-mapping.md)

[<span data-ttu-id="bbda1-161">Sincronizzare intestazioni e righe di fatture di vendita da Finance and Operations in Sales</span><span class="sxs-lookup"><span data-stu-id="bbda1-161">Synchronize sales invoice headers and lines from Finance and Operations to Sales</span></span>](sales-invoice-template-mapping.md)


