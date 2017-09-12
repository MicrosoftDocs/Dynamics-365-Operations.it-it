---
title: Sincronizzare i prodotti da Finance and Operations ai prodotti In Sales
description: "Questo argomento descrive i modelli e le attività sottostanti che vengono utilizzati per sincronizzare i prodotti da Microsoft Dynamics 365 for Finance and Operations, Enterprise edition a Microsoft Dynamics 365 for Sales."
author: ChristianRytt
manager: AnnBe
ms.date: 07/03/2017
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
ms.author: ChristianRytt
ms.dyn365.ops.intro: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: 08c38aada355583c5a6872f75b57db95d9b81786
ms.openlocfilehash: 2f14b06b57930256f9211f2085512aa589df083e
ms.contentlocale: it-it
ms.lasthandoff: 07/27/2017

---

# <a name="synchronize-products-from-finance-and-operations-to-products-in-sales"></a><span data-ttu-id="51979-103">Sincronizzare i prodotti da Finance and Operations ai prodotti In Sales</span><span class="sxs-lookup"><span data-stu-id="51979-103">Synchronize products from Finance and Operations to products in Sales</span></span>

[!include[banner](../includes/banner.md)]

> [!NOTE]
> <span data-ttu-id="51979-104">Prima di utilizzare la soluzione Prospect to cash, acquisisci familiarità con [Integrazione dei dati di Microsoft Dynamics 365](https://docs.microsoft.com/en-us/common-data-service/entity-reference/dynamics-365-integration).</span><span class="sxs-lookup"><span data-stu-id="51979-104">Before you can use the Prospect to cash solution, be familiar with [Dynamics 365 Data Integration](https://docs.microsoft.com/en-us/common-data-service/entity-reference/dynamics-365-integration).</span></span> 

<span data-ttu-id="51979-105">Questo argomento descrive i modelli e le attività sottostanti che vengono utilizzati per sincronizzare i prodotti da Microsoft Dynamics 365 for Finance and Operations, Enterprise edition a Microsoft Dynamics 365 for Sales.</span><span class="sxs-lookup"><span data-stu-id="51979-105">This topic discusses the templates and underlying tasks that are used to synchronize products from Microsoft Dynamics 365 for Finance and Operations, Enterprise edition to Microsoft Dynamics 365 for Sales.</span></span>

## <a name="template-and-task"></a><span data-ttu-id="51979-106">Modello e attività</span><span class="sxs-lookup"><span data-stu-id="51979-106">Template and task</span></span>

<span data-ttu-id="51979-107">I seguenti modelli e le seguenti attività sottostanti vengono utilizzati per sincronizzare i prodotti da Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (Finance and Operations) a Microsoft Dynamics 365 for Sales (Sales).</span><span class="sxs-lookup"><span data-stu-id="51979-107">The following templates and underlying tasks are used to synchronize products from Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (Finance and Operations) to Microsoft Dynamics 365 for Sales (Sales).</span></span>

-   <span data-ttu-id="51979-108">Nome del modello: Prodotti (Fin and Ops a Sales)</span><span class="sxs-lookup"><span data-stu-id="51979-108">Name of template: Products (Fin and Ops to Sales)</span></span>

-   <span data-ttu-id="51979-109">Nome dell'attività del progetto: Prodotti</span><span class="sxs-lookup"><span data-stu-id="51979-109">Name of task in project: Products</span></span>

<span data-ttu-id="51979-110">Attività di sincronizzazione richieste prima di sincronizzare i prodotti: nessuna</span><span class="sxs-lookup"><span data-stu-id="51979-110">Sync tasks required prior to Product sync: None</span></span>

## <a name="entity-set"></a><span data-ttu-id="51979-111">Insieme di entità</span><span class="sxs-lookup"><span data-stu-id="51979-111">Entity set</span></span>

| <span data-ttu-id="51979-112">**Finance and Operations**</span><span class="sxs-lookup"><span data-stu-id="51979-112">**Finance and Operations**</span></span> | <span data-ttu-id="51979-113">**CDS**</span><span class="sxs-lookup"><span data-stu-id="51979-113">**CDS**</span></span> | <span data-ttu-id="51979-114">**Vendite**</span><span class="sxs-lookup"><span data-stu-id="51979-114">**Sales**</span></span>  |
|----------------------------|---------|------------|
| <span data-ttu-id="51979-115">Prodotti rilasciati di vendita</span><span class="sxs-lookup"><span data-stu-id="51979-115">Sellable released products</span></span> | <span data-ttu-id="51979-116">Prodotto</span><span class="sxs-lookup"><span data-stu-id="51979-116">Product</span></span> | <span data-ttu-id="51979-117">Prodotti</span><span class="sxs-lookup"><span data-stu-id="51979-117">Products</span></span>   |

## <a name="entity-flow"></a><span data-ttu-id="51979-118">Flusso di entità</span><span class="sxs-lookup"><span data-stu-id="51979-118">Entity flow</span></span>

<span data-ttu-id="51979-119">I prodotti vengono gestiti in Finance and Operations e sincronizzati con Sales.</span><span class="sxs-lookup"><span data-stu-id="51979-119">Products are managed in Finance and Operations and synchronized to Sales.</span></span> <span data-ttu-id="51979-120">L'entità di dati **Prodotti rilasciati di vendita** in Finance and Operations esporta solo i prodotti che sono vendibili, ovvero i prodotti che hanno le informazioni necessarie per essere utilizzati in un ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="51979-120">The data entity **Sellable released products** in Finance and Operations only exports products that are sellable, which means that products have the information required to be used on a sales order.</span></span> <span data-ttu-id="51979-121">Le stesse regole valgono quando un prodotto viene convalidato con la funzione **Convalida** nella pagina **Prodotto rilasciato**.</span><span class="sxs-lookup"><span data-stu-id="51979-121">The same rules apply when a product is validated with the **Validate** function on the **Released product** page.</span></span>

<span data-ttu-id="51979-122">Il **Numero prodotto** viene utilizzato come chiave. Ciò significa che le varianti di prodotto vengono sincronizzate in CDS e Sales con **ID prodotto** singoli per **Variante prodotto**.</span><span class="sxs-lookup"><span data-stu-id="51979-122">The **Product number** is used as key, meaning that product variants are synchronized to CDS and Sales with individual **Product IDs** per **Product variant**.</span></span>

## <a name="prospect-to-cash-solution-for-sales"></a><span data-ttu-id="51979-123">Soluzione Prospect to cash per Sales</span><span class="sxs-lookup"><span data-stu-id="51979-123">Prospect to cash solution for Sales</span></span>

<span data-ttu-id="51979-124">In Sales viene aggiunto un nuovo campo nei prodotti **Gestito esternamente** per indicare che un determinato prodotto viene gestito esternamente.</span><span class="sxs-lookup"><span data-stu-id="51979-124">In Sales, a new field on the products **Is Externally Maintained** is added to indicate that a given product is maintained externally.</span></span> <span data-ttu-id="51979-125">Il valore è impostato su **Sì** per impostazione predefinita durante l'importazione in Sales.</span><span class="sxs-lookup"><span data-stu-id="51979-125">The value is set to **Yes** by default during import to Sales.</span></span>

-   <span data-ttu-id="51979-126">**Gestito esternamente = Sì**: il prodotto deriva da Finance and Operations e non sarà modificabile in Sales.</span><span class="sxs-lookup"><span data-stu-id="51979-126">**Is Externally Maintained = Yes**: Product originates from Finance and Operations and will not be editable in Sales.</span></span>

-   <span data-ttu-id="51979-127">**Gestito esternamente = No**: il prodotto viene immesso direttamente in Sales.</span><span class="sxs-lookup"><span data-stu-id="51979-127">**Is Externally Maintained = No**: Product is entered directly in Sales.</span></span>

-   <span data-ttu-id="51979-128">**Gestito esternamente = vuoto**: il prodotto esisteva in Sales prima di abilitare la soluzione Prospect to cash.</span><span class="sxs-lookup"><span data-stu-id="51979-128">**Is Externally Maintained = Blank**: Product exists in Sales prior to enabling the Prospect to cash solution.</span></span>

<span data-ttu-id="51979-129">Le informazioni di **Gestito esternamente** vengono utilizzate per garantire che solo **Quote** e **Ordini cliente** con **Prodotti gestiti esternamente** saranno sincronizzati in Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="51979-129">The **Is Externally Maintained** information is used to ensure that only **Quotes** and **Sales orders** with **Externally maintained products** will sync to Finance and Operations.</span></span>

<span data-ttu-id="51979-130">I **Prodotti gestiti esternamente** vengono aggiunti automaticamente al primo **Listino prezzi** valido con la stessa valuta.</span><span class="sxs-lookup"><span data-stu-id="51979-130">**Externally maintained products** are automatically added to the first valid **Price list** with the same currency.</span></span> <span data-ttu-id="51979-131">Notare che il listino è organizzato alfabeticamente in base al **Nome**,</span><span class="sxs-lookup"><span data-stu-id="51979-131">Note that the list is organized alphabetically by **Name**.</span></span> <span data-ttu-id="51979-132">Il prezzo di vendita di un prodotto da Finance and Operations viene utilizzato come prezzo nel **Listino prezzi**.</span><span class="sxs-lookup"><span data-stu-id="51979-132">The product sales price from Finance and Operations is used as price on the **Price list**.</span></span> <span data-ttu-id="51979-133">Ciò significa che è necessario disporre di un **Listino prezzi** in Sales per ogni **Valuta di vendita di prodotti** in Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="51979-133">This means that it is required to have a **Price list** in Sales for each **Product sales currency** in Finance and Operations.</span></span> <span data-ttu-id="51979-134">La valuta sui prodotti vendibili rilasciati viene impostata sulla valuta di contabilità nella persona giuridica da cui il prodotto viene esportato.</span><span class="sxs-lookup"><span data-stu-id="51979-134">Currency on the released sellable products is set to the accounting currency in the legal entity, from which the product is exported.</span></span>

> [!NOTE]
> <span data-ttu-id="51979-135">La sincronizzazione del prodotto non riuscirà senza un **Listino prezzi** con valuta corrispondente.</span><span class="sxs-lookup"><span data-stu-id="51979-135">Product sync will not succeed without a **Price list** with the matching currency.</span></span>

## <a name="preconditions-and-mapping-setup"></a><span data-ttu-id="51979-136">Prerequisiti e impostazioni di mapping</span><span class="sxs-lookup"><span data-stu-id="51979-136">Preconditions and mapping setup</span></span>

-   <span data-ttu-id="51979-137">Prima di eseguire la primissima sincronizzazione, è necessario compilare la **Tabella dei prodotti specifici** per i prodotti esistenti in Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="51979-137">Before you run the very first sync, you must populate the **Distinct product table** for existing products in Finance and Operations.</span></span> <span data-ttu-id="51979-138">I prodotti esistenti non saranno sincronizzati fino al completamento del processo.</span><span class="sxs-lookup"><span data-stu-id="51979-138">Existing products will not be synchronized until this job is completed.</span></span>

    -   <span data-ttu-id="51979-139">In Finance and Operations utilizzare la ricerca per cercare **Compila tabella dei prodotti specifici**.</span><span class="sxs-lookup"><span data-stu-id="51979-139">In Finance and Operations, use Search to search for **Populate distinct product table**.</span></span>

    -   <span data-ttu-id="51979-140">Fare clic su **Compila tabella dei prodotti specifici** per eseguire il processo.</span><span class="sxs-lookup"><span data-stu-id="51979-140">Click the **Populate distinct product table** to run the job.</span></span> <span data-ttu-id="51979-141">Il processo deve essere eseguito una sola volta.</span><span class="sxs-lookup"><span data-stu-id="51979-141">This job only needs to be run once.</span></span>

-   <span data-ttu-id="51979-142">Assicurarsi che la **ValueMap** necessaria per l'**Unità di misura** (UDM) di vendita in Finance and Operations sia presente in **Origine -\> Mapping CDS SalesUnitSymbol/DefaultSellingUnitOfMeasure**.</span><span class="sxs-lookup"><span data-stu-id="51979-142">Ensure that the needed **ValueMap** for selling **Unit of measure** (UOM) in Finance and Operations exists in the **Source -\> CDS mapping SalesUnitSymbol / DefaultSellingUnitOfMeasure**.</span></span>

-   <span data-ttu-id="51979-143">Assicurarsi che i **Decimali supportati** per l'UDM corrispondano ai requisiti in **CDS -\> destinazione**.</span><span class="sxs-lookup"><span data-stu-id="51979-143">Ensure that **Decimals supported** for UOM match your requirements in **CDS -\> Destination**.</span></span> <span data-ttu-id="51979-144">Se occorrono valori diversi per UDM, è possibile impostarli con **ValueMap** da Unità, ad esempio [Ogni: 0] & [Sterlina: 2].</span><span class="sxs-lookup"><span data-stu-id="51979-144">If you require different values per UOM, this can be done with **ValueMap** from Unit, for example, [Each : 0] & [Pound : 2].</span></span>

    -   <span data-ttu-id="51979-145">Il valore predefinito del modello è 0.</span><span class="sxs-lookup"><span data-stu-id="51979-145">Template value is defaulted to 0.</span></span>

-   <span data-ttu-id="51979-146">Aggiornare **ID organizzazione CDS Organization_OrganizationId** in **Origine -\> CDS**.</span><span class="sxs-lookup"><span data-stu-id="51979-146">Update the **CDS Organization ID Organization_OrganizationId** in **Source -\> CDS**.</span></span>

    -   <span data-ttu-id="51979-147">Il valore predefinito del modello è ORG001.</span><span class="sxs-lookup"><span data-stu-id="51979-147">Template value is defaulted to ORG001.</span></span>

-   <span data-ttu-id="51979-148">Aggiornare **ValueMap** per **Gruppo unità** (**defaultuomscheduleid.name**) in **CDS -\> destinazione** in modo che corrisponda **Gruppi unità** in Sales.</span><span class="sxs-lookup"><span data-stu-id="51979-148">Update **ValueMap** for **Unit group** (**defaultuomscheduleid.name**) in **CDS -\> Destination** to match the **Unit groups** in Sales.</span></span>

    -   <span data-ttu-id="51979-149">Il valore predefinito del modello è **Unità predefinita**.</span><span class="sxs-lookup"><span data-stu-id="51979-149">Template value is defaulted to **Default unit**.</span></span>

-   <span data-ttu-id="51979-150">Assicurarsi che tutte le UDM di vendita dei prodotti da Finance and Operations esistano in Sales con il valore **Distinte di prelievo CDS**.</span><span class="sxs-lookup"><span data-stu-id="51979-150">Ensure that all products selling UOMs from Finance and Operations exist in Sales with the **CDS picklists** value.</span></span>

-   <span data-ttu-id="51979-151">Assicurarsi che **Listini prezzi** sia presente in Sales per ogni valuta di vendita prodotti in Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="51979-151">Ensure that **Price lists** exist in Sales for each product sales currency in Finance and Operations.</span></span>

-   <span data-ttu-id="51979-152">I prodotti possono essere creati in Sales con stato **Bozza** o **Attivo**.</span><span class="sxs-lookup"><span data-stu-id="51979-152">Products can be created in Sales with status **Draft** or **Active**.</span></span> <span data-ttu-id="51979-153">Tale opzione è controllata in **Impostazioni di sistema** in **Sales** in Sales.</span><span class="sxs-lookup"><span data-stu-id="51979-153">This is controlled in **System settings** under **Sales** in Sales.</span></span>

    -   <span data-ttu-id="51979-154">I prodotti creati con lo stato di bozza devono essere attivati prima di potere essere aggiunti a **Quota** o **Ordine cliente**.</span><span class="sxs-lookup"><span data-stu-id="51979-154">Products created with draft status need to be activated before they can be added to **Quote** or **Sales order**.</span></span>

## <a name="template-mapping-in-data-integrator"></a><span data-ttu-id="51979-155">Mapping dei modelli nell'integratore di dati</span><span class="sxs-lookup"><span data-stu-id="51979-155">Template mapping in data integrator</span></span>

<span data-ttu-id="51979-156">Nelle figure seguenti viene illustrato un esempio di un modello di mapping nell'integratore di dati.</span><span class="sxs-lookup"><span data-stu-id="51979-156">The following illustrations show an example of a template mapping in data integrator.</span></span>

![Mapping dei modelli nell'integratore di dati](./media/products-template-mapping-data-integrator-1.png)

![Mapping dei modelli per prodotti nell'integratore di dati](./media/products-template-mapping-data-integrator-2.png)

## <a name="related-topics"></a><span data-ttu-id="51979-159">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="51979-159">Related topics</span></span>

[<span data-ttu-id="51979-160">Sincronizzare conti da Sales a clienti in Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="51979-160">Synchronize accounts from Sales to customers in Finance and Operations</span></span>](accounts-template-mapping.md)

[<span data-ttu-id="51979-161">Sincronizzare i contatti da Sales ai contatti o ai clienti in Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="51979-161">Synchronize contacts from Sales to contacts or customers in Finance and Operations</span></span>](contacts-template-mapping.md)

[<span data-ttu-id="51979-162">Sincronizzare le intestazioni e le righe di offerte di vendita da Sales a Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="51979-162">Synchronize sales quotation headers and lines from Sales to Finance and Operations</span></span>](sales-quotation-template-mapping.md)


