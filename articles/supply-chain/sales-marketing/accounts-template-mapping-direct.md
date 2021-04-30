---
title: Sincronizzare conti direttamente da Sales con clienti in Supply Chain Management
description: Questo argomento descrive i modelli e le attività sottostanti che vengono utilizzati per sincronizzare i conti da Dynamics 365 Sales in Supply Chain Management.
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
ms.openlocfilehash: fff9171966045e9dad5f2c70087a568cfa075e43
ms.sourcegitcommit: 34b478f175348d99df4f2f0c2f6c0c21b6b2660a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/16/2021
ms.locfileid: "5908134"
---
# <a name="synchronize-accounts-directly-from-sales-to-customers-in-supply-chain-management"></a><span data-ttu-id="c53f2-103">Sincronizzare conti direttamente da Sales con clienti in Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="c53f2-103">Synchronize accounts directly from Sales to customers in Supply Chain Management</span></span>

[!include [banner](../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

> [!NOTE]
> <span data-ttu-id="c53f2-104">Prima di utilizzare la soluzione Prospect to cash, è necessario acquisire familiarità con [Integrare i dati in Microsoft Dataverse per le app](/powerapps/administrator/data-integrator).</span><span class="sxs-lookup"><span data-stu-id="c53f2-104">Before you can use the Prospect to cash solution, you should be familiar with [Integrate data into Microsoft Dataverse for Apps](/powerapps/administrator/data-integrator).</span></span>

<span data-ttu-id="c53f2-105">Questo argomento descrive i modelli e le attività sottostanti che vengono utilizzati per sincronizzare i conti direttamente da Dynamics 365 Sales in Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="c53f2-105">This topic discusses the templates and underlying tasks that are used to synchronize accounts directly from Dynamics 365 Sales to Dynamics 365 Supply Chain Management.</span></span>

## <a name="data-flow-in-prospect-to-cash"></a><span data-ttu-id="c53f2-106">Flusso di dati in Prospect to cash</span><span class="sxs-lookup"><span data-stu-id="c53f2-106">Data flow in Prospect to cash</span></span>

<span data-ttu-id="c53f2-107">La soluzione Prospect to cash utilizza la funzionalità Integrazione dati per sincronizzare i dati tra istanze di Supply Chain Management e Sales.</span><span class="sxs-lookup"><span data-stu-id="c53f2-107">The Prospect to cash solution uses the Data integration feature to synchronize data across instances of Supply Chain Management and Sales.</span></span>  <span data-ttu-id="c53f2-108">I modelli Prospect to cash disponibili con la funzionalità Integrazione dati consentono il flusso di dati relativo a conti, contatti, prodotti, offerte di vendita, ordini cliente e fatture di vendita tra Supply Chain Management e Sales.</span><span class="sxs-lookup"><span data-stu-id="c53f2-108">The Prospect to cash templates that are available with the Data integration feature enable the flow of data about accounts, contacts, products, sales quotations, sales orders, and sales invoices between Supply Chain Management and Sales.</span></span> <span data-ttu-id="c53f2-109">La figura seguente mostra il modo in cui i dati vengono sincronizzati tra Supply Chain Management e Sales.</span><span class="sxs-lookup"><span data-stu-id="c53f2-109">The following illustration shows how the data is synchronized between Supply Chain Management and Sales.</span></span>

<span data-ttu-id="c53f2-110">[![Flusso di dati in Prospect to cash](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)</span><span class="sxs-lookup"><span data-stu-id="c53f2-110">[![Data flow in Prospect to cash](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="c53f2-111">Modelli e attività</span><span class="sxs-lookup"><span data-stu-id="c53f2-111">Templates and tasks</span></span>

<span data-ttu-id="c53f2-112">Per accedere ai modelli disponibili, aprire l'[Interfaccia di amministrazione di Power Apps](https://preview.admin.powerapps.com/dataintegration).</span><span class="sxs-lookup"><span data-stu-id="c53f2-112">To access the available templates, open [Power Apps Admin Center](https://preview.admin.powerapps.com/dataintegration).</span></span> <span data-ttu-id="c53f2-113">Selezionare **Progetti**, quindi nell'angolo superiore destro, selezionare **Nuovo progetto** per selezionare i modelli pubblici.</span><span class="sxs-lookup"><span data-stu-id="c53f2-113">Select **Projects**, and then, in the upper-right corner, select **New project** to select public templates.</span></span>

<span data-ttu-id="c53f2-114">Il modello e l'attività sottostanti seguenti vengono utilizzati per sincronizzare i conti da Sales in Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="c53f2-114">The following template and underlying task are used to synchronize accounts from Sales to Supply Chain Management:</span></span>

- <span data-ttu-id="c53f2-115">**Nome del modello in Integrazione dati:** Conti (da Sales in Fin and Ops) - Diretto</span><span class="sxs-lookup"><span data-stu-id="c53f2-115">**Name of the template in Data integration:** Accounts (Sales to Fin and Ops) - Direct</span></span>
- <span data-ttu-id="c53f2-116">**Nome dell'attività del progetto:** Conti - Clienti</span><span class="sxs-lookup"><span data-stu-id="c53f2-116">**Name of the task in the project:** Accounts - Customers</span></span>

<span data-ttu-id="c53f2-117">Nessuna attività di sincronizzazione è necessaria prima della sincronizzazione Conto/Cliente.</span><span class="sxs-lookup"><span data-stu-id="c53f2-117">No synchronization tasks are required before Account/Customer synchronization can occur.</span></span>

## <a name="entity-set"></a><span data-ttu-id="c53f2-118">Insieme di entità</span><span class="sxs-lookup"><span data-stu-id="c53f2-118">Entity set</span></span>

| <span data-ttu-id="c53f2-119">Vendite</span><span class="sxs-lookup"><span data-stu-id="c53f2-119">Sales</span></span>    | <span data-ttu-id="c53f2-120">Gestione della supply chain</span><span class="sxs-lookup"><span data-stu-id="c53f2-120">Supply Chain Management</span></span> |
|----------|------------------------|
| <span data-ttu-id="c53f2-121">Account</span><span class="sxs-lookup"><span data-stu-id="c53f2-121">Accounts</span></span> | <span data-ttu-id="c53f2-122">Clienti V2</span><span class="sxs-lookup"><span data-stu-id="c53f2-122">Customers V2</span></span>           |

## <a name="entity-flow"></a><span data-ttu-id="c53f2-123">Flusso di entità</span><span class="sxs-lookup"><span data-stu-id="c53f2-123">Entity flow</span></span>

<span data-ttu-id="c53f2-124">I conti vengono gestiti in Sales e sincronizzati in Supply Chain Management come clienti.</span><span class="sxs-lookup"><span data-stu-id="c53f2-124">Accounts are managed in Sales and synchronized to Supply Chain Management as customers.</span></span> <span data-ttu-id="c53f2-125">La proprietà **Gestito esternamente** per tali clienti è impostata su **Sì** per tenere traccia dei clienti che hanno origine da Sales.</span><span class="sxs-lookup"><span data-stu-id="c53f2-125">The **Is Externally Maintained** property on these customers is set to **Yes** to track customers that originate from Sales.</span></span> <span data-ttu-id="c53f2-126">Durante la fatturazione queste informazioni vengono utilizzate per filtrare le fatture che vengono sincronizzate in Sales.</span><span class="sxs-lookup"><span data-stu-id="c53f2-126">During invoicing, this information is used to filter invoices that are synchronized to Sales.</span></span>

## <a name="prospect-to-cash-solution-for-sales"></a><span data-ttu-id="c53f2-127">Soluzione Prospect to cash per Sales</span><span class="sxs-lookup"><span data-stu-id="c53f2-127">Prospect to cash solution for Sales</span></span>

<span data-ttu-id="c53f2-128">La colonna **Numero di conto** è disponibile nella pagina **Conto**.</span><span class="sxs-lookup"><span data-stu-id="c53f2-128">The **Account Number** column is available on the **Account** page.</span></span> <span data-ttu-id="c53f2-129">È stata generata una chiave naturale e univoca per supportare l'integrazione.</span><span class="sxs-lookup"><span data-stu-id="c53f2-129">It has been made a natural and unique key in order to support the integration.</span></span> <span data-ttu-id="c53f2-130">Questa funzionalità di chiave naturale della soluzione Customer Relationship Management (CRM) potrebbe influire sui clienti che utilizzano già la colonna **Numero di conto**, ma che non utilizzano i valori univoci **Numero di conto** per conto.</span><span class="sxs-lookup"><span data-stu-id="c53f2-130">The natural key feature of the Customer Relationship Management (CRM) solution might affect customers who already use the **Account Number** column, but who don't use unique **Account Number** values per account.</span></span> <span data-ttu-id="c53f2-131">Attualmente la soluzione di integrazione non supporta questo caso.</span><span class="sxs-lookup"><span data-stu-id="c53f2-131">Currently, the integration solution doesn't support this case.</span></span>

<span data-ttu-id="c53f2-132">Quando un nuovo conto viene creato, se un valore **Numero di conto** non è già presente, viene generato automaticamente utilizzando una sequenza numerica.</span><span class="sxs-lookup"><span data-stu-id="c53f2-132">When a new account is created, if an **Account Number** value doesn't already exist, it's automatically generated by using a number sequence.</span></span> <span data-ttu-id="c53f2-133">Il valore consiste di **ACC**, seguito da una sequenza numerica crescente, quindi da un suffisso di sei caratteri.</span><span class="sxs-lookup"><span data-stu-id="c53f2-133">The value consists of **ACC**, followed by an increasing number sequence and then a suffix of six characters.</span></span> <span data-ttu-id="c53f2-134">Ecco un esempio: **ACC-01000-BVRCPS**</span><span class="sxs-lookup"><span data-stu-id="c53f2-134">Here is an example: **ACC-01000-BVRCPS**</span></span>

<span data-ttu-id="c53f2-135">Quando viene applicata la soluzione di integrazione per Sales, uno script di aggiornamento imposta la colonna **Numero di conto** per i conti esistenti in Sales.</span><span class="sxs-lookup"><span data-stu-id="c53f2-135">When the integration solution for Sales is applied, an upgrade script sets the **Account Number** column for existing accounts in Sales.</span></span> <span data-ttu-id="c53f2-136">Se non sono presenti valori **Numero di conto**, viene utilizzata la sequenza numerica menzionata in precedenza.</span><span class="sxs-lookup"><span data-stu-id="c53f2-136">If there are no **Account Number** values, the number sequence that was mentioned earlier is used.</span></span>

## <a name="preconditions-and-mapping-setup"></a><span data-ttu-id="c53f2-137">Prerequisiti e impostazioni di mapping</span><span class="sxs-lookup"><span data-stu-id="c53f2-137">Preconditions and mapping setup</span></span>

- <span data-ttu-id="c53f2-138">Il mapping **CustomerGroupId** deve essere aggiornato a un valore valido in Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="c53f2-138">The **CustomerGroupId** mapping must be updated to a valid value in Supply Chain Management.</span></span> <span data-ttu-id="c53f2-139">È possibile specificare un valore predefinito oppure è possibile impostare il valore utilizzando una mappa di valori.</span><span class="sxs-lookup"><span data-stu-id="c53f2-139">You can specify a default value, or you can set the value by using a value map.</span></span>

    <span data-ttu-id="c53f2-140">Il valore del modello predefinito è **10**.</span><span class="sxs-lookup"><span data-stu-id="c53f2-140">The default template value is **10**.</span></span>

- <span data-ttu-id="c53f2-141">Aggiungendo i seguenti mapping, è possibile consentire una riduzione del numero degli aggiornamenti manuali necessari in Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="c53f2-141">By adding the following mappings, you can help reduce the number of manual updates that are required in Supply Chain Management.</span></span> <span data-ttu-id="c53f2-142">È possibile utilizzare un valore predefinito o una mappa di valori da, ad esempio, **Paese** o **Città**.</span><span class="sxs-lookup"><span data-stu-id="c53f2-142">You can use a default value or a value map from, for example, **Country/Region** or **City**.</span></span>

    - <span data-ttu-id="c53f2-143">**SiteId** - Un sito è obbligatorio per la generazione di offerte e righe di ordine cliente in Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="c53f2-143">**SiteId** – A site is required in order to generate quotations and sales order lines in Supply Chain Management.</span></span> <span data-ttu-id="c53f2-144">Un sito predefinito può essere preso sia dal prodotto che dall'intestazione ordine del cliente.</span><span class="sxs-lookup"><span data-stu-id="c53f2-144">A default site can be taken either from the product, or from the customer from the order header.</span></span>

        <span data-ttu-id="c53f2-145">Il valore del modello predefinito è **1**.</span><span class="sxs-lookup"><span data-stu-id="c53f2-145">The default template value is **1**.</span></span>

    - <span data-ttu-id="c53f2-146">**WarehouseId** - Un magazzino è obbligatorio per l'elaborazione di offerte e righe di ordine cliente in Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="c53f2-146">**WarehouseId** – A warehouse is required in order to process quotations and sales order lines in Supply Chain Management.</span></span> <span data-ttu-id="c53f2-147">Un sito predefinito può essere preso sia dal prodotto che dall'intestazione ordine del cliente in Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="c53f2-147">A default warehouse can be taken either from the product, or from the customer from the order header in Supply Chain Management.</span></span>

        <span data-ttu-id="c53f2-148">Il valore del modello predefinito è **13**.</span><span class="sxs-lookup"><span data-stu-id="c53f2-148">The default template value is **13**.</span></span>

    - <span data-ttu-id="c53f2-149">**LanguageId** - Una lingua è obbligatoria per la generazione di offerte e ordini cliente in Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="c53f2-149">**LanguageId** – A language is required in order to generate quotations and sales orders in Supply Chain Management.</span></span> <span data-ttu-id="c53f2-150">Per impostazione predefinita, viene utilizzata la lingua dell'intestazione ordine del cliente.</span><span class="sxs-lookup"><span data-stu-id="c53f2-150">By default, the language from the order header from the customer is used.</span></span>

        <span data-ttu-id="c53f2-151">Il valore di modello predefinito è **en-us**.</span><span class="sxs-lookup"><span data-stu-id="c53f2-151">The default template value is **en-us**.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="c53f2-152">Mapping dei modelli in Integrazione dati</span><span class="sxs-lookup"><span data-stu-id="c53f2-152">Template mapping in Data integration</span></span>

> [!NOTE]
> <span data-ttu-id="c53f2-153">Le colonne **Termini di pagamento**, **Termini di trasporto**, **Termini di consegna**, **Metodo di spedizione** e **Modalità di consegna** non vengono inclusi nei mapping predefiniti.</span><span class="sxs-lookup"><span data-stu-id="c53f2-153">The **Payment terms**, **Freight terms**, **Delivery terms**, **Shipping method**, and **Delivery mode** columns aren't included in the default mappings.</span></span> <span data-ttu-id="c53f2-154">Per mappare queste colonne, è necessario impostare un mapping di valori che sia specifico ai dati delle organizzazioni tra cui la tabella viene sincronizzata.</span><span class="sxs-lookup"><span data-stu-id="c53f2-154">To map these columns, you must set up a value mapping that is specific to the data in the organizations that the table is synchronized between.</span></span>

<span data-ttu-id="c53f2-155">Nelle figure seguenti viene illustrato un esempio di mapping di modelli in Integrazione dati.</span><span class="sxs-lookup"><span data-stu-id="c53f2-155">The following illustrations show an example of a template mapping in Data integration.</span></span> 

> [!NOTE]
> <span data-ttu-id="c53f2-156">Il mapping mostra quali informazioni sulle colonne verranno sincronizzate da Sales in Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="c53f2-156">The mapping shows which column information will be synchronized from Sales to Supply Chain Management.</span></span>

![Mapping dei modelli in Integrazione dati](./media/accounts-direct-template-mapping-data-integrator-1.png)

## <a name="related-topics"></a><span data-ttu-id="c53f2-158">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="c53f2-158">Related topics</span></span>


[<span data-ttu-id="c53f2-159">Prospect per uno scenario di liquidazione</span><span class="sxs-lookup"><span data-stu-id="c53f2-159">Prospect to cash</span></span>](prospect-to-cash.md)

[<span data-ttu-id="c53f2-160">Sincronizzare conti direttamente da Sales con clienti in Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="c53f2-160">Synchronize accounts directly from Sales to customers in Supply Chain Management</span></span>](accounts-template-mapping-direct.md)

[<span data-ttu-id="c53f2-161">Sincronizzare contatti direttamente da Sales con contatti o clienti in Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="c53f2-161">Synchronize contacts directly from Sales to contacts or customers in Supply Chain Management</span></span>](contacts-template-mapping-direct.md)

[<span data-ttu-id="c53f2-162">Sincronizzazione degli ordini cliente direttamente tra Sales e Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="c53f2-162">Synchronization of sales orders directly between Sales and Supply Chain Management</span></span>](sales-order-template-mapping-direct-two-ways.md)

[<span data-ttu-id="c53f2-163">Sincronizzare intestazioni e righe di fatture di vendita direttamente da Supply Chain Management in Sales</span><span class="sxs-lookup"><span data-stu-id="c53f2-163">Synchronize sales invoice headers and lines directly from Supply Chain Management to Sales</span></span>](sales-invoice-template-mapping-direct.md)



[!INCLUDE[footer-include](../../includes/footer-banner.md)]