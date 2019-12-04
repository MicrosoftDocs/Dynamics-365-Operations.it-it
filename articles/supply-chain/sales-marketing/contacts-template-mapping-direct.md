---
title: Sincronizzare contatti direttamente da Sales con contatti o clienti in Supply Chain Management
description: Questo argomento descrive i modelli e le attività sottostanti utilizzati per sincronizzare le entità Contatto (Contatti) e Contatto (Clienti) da Dynamics 365 Sales in Dynamics 365 Supply Chain Management.
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
ms.openlocfilehash: 141464f2ce7cb4ccfd2a8fb7a266e657e8f52015
ms.sourcegitcommit: 57bc7e17682e2edb5e1766496b7a22f4621819dd
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/18/2019
ms.locfileid: "2814123"
---
# <a name="synchronize-contacts-directly-from-sales-to-contacts-or-customers-in-supply-chain-management"></a><span data-ttu-id="73075-103">Sincronizzare contatti direttamente da Sales con contatti o clienti in Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="73075-103">Synchronize contacts directly from Sales to contacts or customers in Supply Chain Management</span></span>

[!include [banner](../includes/banner.md)]

> [!NOTE]
> <span data-ttu-id="73075-104">Prima di utilizzare la soluzione Prospect to cash, è necessario acquisire familiarità con [Integrare i dati in Common Data Service per le app](https://docs.microsoft.com/powerapps/administrator/data-integrator).</span><span class="sxs-lookup"><span data-stu-id="73075-104">Before you can use the Prospect to cash solution, you should be familiar with [Integrate data into Common Data Service for Apps](https://docs.microsoft.com/powerapps/administrator/data-integrator).</span></span>

<span data-ttu-id="73075-105">Questo argomento descrive i modelli e le attività sottostanti utilizzati per sincronizzare direttamente le entità Contatto (Contatti) e Contatto (Clienti) da Dynamics 365 Sales in Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="73075-105">This topic discusses the templates and underlying tasks that are used to synchronize Contact (Contacts) and Contact (Customers) entities directly from Dynamics 365 Sales to Dynamics 365 Supply Chain Management.</span></span>

## <a name="data-flow-in-prospect-to-cash"></a><span data-ttu-id="73075-106">Flusso di dati in Prospect to cash</span><span class="sxs-lookup"><span data-stu-id="73075-106">Data flow in Prospect to cash</span></span>

<span data-ttu-id="73075-107">La soluzione Prospect to cash utilizza la funzionalità Integrazione dati per sincronizzare i dati tra istanze di Supply Chain Management e Sales.</span><span class="sxs-lookup"><span data-stu-id="73075-107">The Prospect to cash solution uses the Data integration feature to synchronize data across instances of Supply Chain Management and Sales.</span></span> <span data-ttu-id="73075-108">I modelli Prospect to cash disponibili con la funzionalità Integrazione dati consentono il flusso di dati relativo a conti, contatti, prodotti, offerte di vendita, ordini cliente e fatture di vendita tra Supply Chain Management e Sales.</span><span class="sxs-lookup"><span data-stu-id="73075-108">The Prospect to cash templates that are available with the Data integration feature enable the flow of data about accounts, contacts, products, sales quotations, sales orders, and sales invoices between Supply Chain Management and Sales.</span></span> <span data-ttu-id="73075-109">La figura seguente mostra il modo in cui i dati vengono sincronizzati tra Supply Chain Management e Sales.</span><span class="sxs-lookup"><span data-stu-id="73075-109">The following illustration shows how the data is synchronized between Supply Chain Management and Sales.</span></span>

<span data-ttu-id="73075-110">[![Flusso di dati in Prospect to cash](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)</span><span class="sxs-lookup"><span data-stu-id="73075-110">[![Data flow in Prospect to cash](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="73075-111">Modelli e attività</span><span class="sxs-lookup"><span data-stu-id="73075-111">Templates and tasks</span></span>

<span data-ttu-id="73075-112">Per accedere ai modelli disponibili, aprire l'[Interfaccia di amministrazione di PowerApps](https://preview.admin.powerapps.com/dataintegration).</span><span class="sxs-lookup"><span data-stu-id="73075-112">To access the available templates, open [PowerApps Admin Center](https://preview.admin.powerapps.com/dataintegration).</span></span> <span data-ttu-id="73075-113">Selezionare **Progetti**, quindi nell'angolo superiore destro, selezionare **Nuovo progetto** per selezionare i modelli pubblici.</span><span class="sxs-lookup"><span data-stu-id="73075-113">Select **Projects**, and then, in the upper-right corner, select **New project** to select public templates.</span></span>

<span data-ttu-id="73075-114">I seguenti modelli e attività sottostanti vengono utilizzati per sincronizzare entità Contatto (Contatti) in Sales a entità Contatto (Clienti) in Supply Chain Management:</span><span class="sxs-lookup"><span data-stu-id="73075-114">The following templates and underlying tasks are used to synchronize Contact (Contacts) entities in Sales to Contact (Customers) entities in Supply Chain Management.</span></span>

- <span data-ttu-id="73075-115">**Nomi dei modelli in Integrazione dati**</span><span class="sxs-lookup"><span data-stu-id="73075-115">**Names of the templates in Data integration**</span></span>

    - <span data-ttu-id="73075-116">Contatti (da Sales in Supply Chain Management) - Diretto</span><span class="sxs-lookup"><span data-stu-id="73075-116">Contacts (Sales to Supply Chain Management) - Direct</span></span>
    - <span data-ttu-id="73075-117">Da Contatti a Cliente (da Sales in Supply Chain Management) - Diretto</span><span class="sxs-lookup"><span data-stu-id="73075-117">Contacts to Customer (Sales to Supply Chain Management) - Direct</span></span>

- <span data-ttu-id="73075-118">**Nomi delle attività nel progetto di Integrazione dati**</span><span class="sxs-lookup"><span data-stu-id="73075-118">**Names of the tasks in the Data integration project**</span></span>

    - <span data-ttu-id="73075-119">Contatti</span><span class="sxs-lookup"><span data-stu-id="73075-119">Contacts</span></span>
    - <span data-ttu-id="73075-120">ContactToCustomer</span><span class="sxs-lookup"><span data-stu-id="73075-120">ContactToCustomer</span></span>

<span data-ttu-id="73075-121">La seguente attività di sincronizzazione è necessaria prima della sincronizzazione dei contatti: Conti (da Sales in Supply Chain Management)</span><span class="sxs-lookup"><span data-stu-id="73075-121">The following synchronization task is required before contact synchronization can occur: Accounts (Sales to Supply Chain Management)</span></span>

## <a name="entity-sets"></a><span data-ttu-id="73075-122">Insiemi di entità</span><span class="sxs-lookup"><span data-stu-id="73075-122">Entity sets</span></span>

| <span data-ttu-id="73075-123">Vendite</span><span class="sxs-lookup"><span data-stu-id="73075-123">Sales</span></span>    | <span data-ttu-id="73075-124">Gestione della supply chain</span><span class="sxs-lookup"><span data-stu-id="73075-124">Supply Chain Management</span></span> |
|----------|------------------------|
| <span data-ttu-id="73075-125">Contatti</span><span class="sxs-lookup"><span data-stu-id="73075-125">Contacts</span></span> | <span data-ttu-id="73075-126">Contatti CDS</span><span class="sxs-lookup"><span data-stu-id="73075-126">CDS Contacts</span></span>           |
| <span data-ttu-id="73075-127">Contatti</span><span class="sxs-lookup"><span data-stu-id="73075-127">Contacts</span></span> | <span data-ttu-id="73075-128">Clienti V2</span><span class="sxs-lookup"><span data-stu-id="73075-128">Customers V2</span></span>           |

## <a name="entity-flow"></a><span data-ttu-id="73075-129">Flusso di entità</span><span class="sxs-lookup"><span data-stu-id="73075-129">Entity flow</span></span>

<span data-ttu-id="73075-130">I contatti vengono gestiti in Sales e sincronizzati in Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="73075-130">Contacts are managed in Sales and synchronized to Supply Chain Management.</span></span>

<span data-ttu-id="73075-131">Un contatto in Sales può diventare un contatto o un cliente in Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="73075-131">A contact in Sales can become either a contact or a customer in Supply Chain Management.</span></span> <span data-ttu-id="73075-132">Per stabilire se un contatto in Sales deve essere sincronizzato in Supply Chain Management come contatto o cliente, il sistema esamina le seguenti proprietà del contatto in Sales:</span><span class="sxs-lookup"><span data-stu-id="73075-132">To determine whether a contact in Sales should be synchronized to Supply Chain Management as a contact or a customer, the system looks at the following properties on the contact in Sales:</span></span>

- <span data-ttu-id="73075-133">**Sincronizzazione a un cliente in Supply Chain Management:** Contatti dove l'opzione **Si tratta del cliente attivo** è impostata su **Sì**</span><span class="sxs-lookup"><span data-stu-id="73075-133">**Synchronization to a customer in Supply Chain Management:** Contacts where **Is Active Customer** is set to **Yes**</span></span>
- <span data-ttu-id="73075-134">**Sincronizzazione a un contatto in Supply Chain Management:** Contatti dove l'opzione **Si tratta del cliente attivo** è impostata su **No** e **Società** (conto/contatto principale) punta a un conto (non a un contatto)</span><span class="sxs-lookup"><span data-stu-id="73075-134">**Synchronization to a contact in Supply Chain Management:** Contacts where **Is Active Customer** is set to **No** and **Company** (parent account/contact) points to an account (not a contact)</span></span>

## <a name="prospect-to-cash-solution-for-sales"></a><span data-ttu-id="73075-135">Soluzione Prospect to cash per Sales</span><span class="sxs-lookup"><span data-stu-id="73075-135">Prospect to cash solution for Sales</span></span>

<span data-ttu-id="73075-136">Un nuovo campo **Si tratta del cliente attivo** è stato aggiunto al contatto.</span><span class="sxs-lookup"><span data-stu-id="73075-136">A new **Is Active Customer** field has been added to the contact.</span></span> <span data-ttu-id="73075-137">Questo campo viene utilizzato per distinguere i contatti che hanno attività di vendita dai contatti che non ne hanno.</span><span class="sxs-lookup"><span data-stu-id="73075-137">This field is used to differentiate contacts that have sales activity and contacts that don't have sales activity.</span></span> <span data-ttu-id="73075-138">L'opzione **Si tratta del cliente attivo** è impostata su **Sì** solo per i contatti con offerte, ordini o fatture correlate.</span><span class="sxs-lookup"><span data-stu-id="73075-138">**Is Active Customer** is set to **Yes** only for contacts that have related quotations, orders, or invoices.</span></span> <span data-ttu-id="73075-139">Solo tali contatti vengono sincronizzati in Supply Chain Management come clienti.</span><span class="sxs-lookup"><span data-stu-id="73075-139">Only those contacts are synchronized to Supply Chain Management as customers.</span></span>

<span data-ttu-id="73075-140">Un nuovo campo **IsCompanyAnAccount** è stato aggiunto al contatto.</span><span class="sxs-lookup"><span data-stu-id="73075-140">A new **IsCompanyAnAccount** field has been added to the contact.</span></span> <span data-ttu-id="73075-141">Questo campo indica se un contatto è collegato a una società (conto/contatto principale) di tipo **Conto**.</span><span class="sxs-lookup"><span data-stu-id="73075-141">This field indicates whether a contact is linked to a company (parent account/contact) of the **Account** type.</span></span> <span data-ttu-id="73075-142">Queste informazioni vengono utilizzate per identificare i contatti che devono essere sincronizzati in Supply Chain Management come contatti.</span><span class="sxs-lookup"><span data-stu-id="73075-142">This information is used to identify contacts that should be synchronized to Supply Chain Management as contacts.</span></span>

<span data-ttu-id="73075-143">Un nuovo campo **Numero del contatto** è stato aggiunto al contatto per assicurare una chiave naturale e univoca per l'integrazione.</span><span class="sxs-lookup"><span data-stu-id="73075-143">A new **Contact Number** field has been added to the contact to help guarantee a natural and unique key for the integration.</span></span> <span data-ttu-id="73075-144">Quando si crea un nuovo contatto, viene generato automaticamente un valore **Numero del contatto** utilizzando una sequenza numerica.</span><span class="sxs-lookup"><span data-stu-id="73075-144">When a new contact is created, a **Contact Number** value is automatically generated by using a number sequence.</span></span> <span data-ttu-id="73075-145">Il valore consiste di **CON**, seguito da una sequenza numerica crescente, quindi da un suffisso di sei caratteri.</span><span class="sxs-lookup"><span data-stu-id="73075-145">The value consists of **CON**, followed by an increasing number sequence and then a suffix of six characters.</span></span> <span data-ttu-id="73075-146">Ecco un esempio: **CON-01000-BVRCPS**</span><span class="sxs-lookup"><span data-stu-id="73075-146">Here is an example: **CON-01000-BVRCPS**</span></span>

<span data-ttu-id="73075-147">Quando la soluzione di integrazione per Sales viene applicata, uno script di aggiornamento imposta il campo **Numero del contatto** per i contatti esistenti utilizzando la sequenza numerica menzionata in precedenza.</span><span class="sxs-lookup"><span data-stu-id="73075-147">When the integration solution for Sales is applied, an upgrade script sets the **Contact Number** field for existing contacts by using the number sequence that was mentioned earlier.</span></span> <span data-ttu-id="73075-148">Lo script di aggiornamento imposta inoltre il campo **Si tratta del cliente attivo** su **Sì** per qualsiasi contatto con attività di vendita.</span><span class="sxs-lookup"><span data-stu-id="73075-148">The upgrade script also sets the **Is Active Customer** field to **Yes** for any contacts that have sales activity.</span></span>

## <a name="in-supply-chain-management"></a><span data-ttu-id="73075-149">In Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="73075-149">In Supply Chain Management</span></span>

<span data-ttu-id="73075-150">AI Contatti vengono assegnati tag tramite l'utilizzo della proprietà **IsContactPersonExternallyMaintained**.</span><span class="sxs-lookup"><span data-stu-id="73075-150">Contacts are tagged by using the **IsContactPersonExternallyMaintained** property.</span></span> <span data-ttu-id="73075-151">Questa proprietà indica che un contatto specifico viene gestito esternamente.</span><span class="sxs-lookup"><span data-stu-id="73075-151">This property indicates that a given contact is maintained externally.</span></span> <span data-ttu-id="73075-152">In questo caso, i contatti gestiti esternamente vengono gestiti in Sales.</span><span class="sxs-lookup"><span data-stu-id="73075-152">In this case, externally maintained contacts are maintained in Sales.</span></span>

## <a name="preconditions-and-mapping-setup"></a><span data-ttu-id="73075-153">Prerequisiti e impostazioni di mapping</span><span class="sxs-lookup"><span data-stu-id="73075-153">Preconditions and mapping setup</span></span>

### <a name="contact-to-customer"></a><span data-ttu-id="73075-154">Da contatto a cliente</span><span class="sxs-lookup"><span data-stu-id="73075-154">Contact to customer</span></span>

- <span data-ttu-id="73075-155">**CustomerGroup** è obbligatorio in Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="73075-155">**CustomerGroup** is required in Supply Chain Management.</span></span> <span data-ttu-id="73075-156">Per prevenire errori di sincronizzazione, è possibile specificare un valore predefinito nel mapping.</span><span class="sxs-lookup"><span data-stu-id="73075-156">To help prevent synchronization errors, you can specify a default value in the mapping.</span></span> <span data-ttu-id="73075-157">Tale valore predefinito viene quindi utilizzato se il campo viene lasciato vuoto in Sales.</span><span class="sxs-lookup"><span data-stu-id="73075-157">That default value is then used if the field is left blank in Sales.</span></span>

    <span data-ttu-id="73075-158">Il valore del modello predefinito è **10**.</span><span class="sxs-lookup"><span data-stu-id="73075-158">The default template value is **10**.</span></span>

- <span data-ttu-id="73075-159">Aggiungendo i seguenti mapping, è possibile consentire una riduzione del numero degli aggiornamenti manuali necessari in Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="73075-159">By adding the following mappings, you can help reduce the number of manual updates that are required in Supply Chain Management.</span></span> <span data-ttu-id="73075-160">È possibile utilizzare un valore predefinito o una mappa di valori da, ad esempio, **Paese** o **Città**.</span><span class="sxs-lookup"><span data-stu-id="73075-160">You can use a default value or a value map from, for example, **Country/Region** or **City**.</span></span>

    - <span data-ttu-id="73075-161">**SiteId** - Un sito predefinito può inoltre essere definito per i prodotti in Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="73075-161">**SiteId** – A default site can also be defined on products in Supply Chain Management.</span></span> <span data-ttu-id="73075-162">Un sito è obbligatorio per la generazione di offerte e ordini cliente in Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="73075-162">A site is required in order to generate quotations and sales orders in Supply Chain Management.</span></span>

        <span data-ttu-id="73075-163">Un modello di valore per **SiteId** non è definito.</span><span class="sxs-lookup"><span data-stu-id="73075-163">A template value for **SiteId** isn't defined.</span></span>

    - <span data-ttu-id="73075-164">**WarehouseId** - Un magazzino predefinito può inoltre essere definito per i prodotti in Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="73075-164">**WarehouseId** – A default warehouse can also be defined on products in Supply Chain Management.</span></span> <span data-ttu-id="73075-165">Un magazzino è obbligatorio per la generazione di offerte e ordini cliente in Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="73075-165">A warehouse is required in order to generate quotations and sales orders in Supply Chain Management.</span></span>

        <span data-ttu-id="73075-166">Un modello di valore per **WarehouseId** non è definito.</span><span class="sxs-lookup"><span data-stu-id="73075-166">A template value for **WarehouseId** isn't defined.</span></span>

    - <span data-ttu-id="73075-167">**LanguageId** - Una lingua è obbligatoria per la generazione di offerte e ordini cliente in Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="73075-167">**LanguageId** – A language is required in order to generate quotations and sales orders in Supply Chain Management.</span></span>
    
        <span data-ttu-id="73075-168">Il valore di modello predefinito è **en-us**.</span><span class="sxs-lookup"><span data-stu-id="73075-168">The default template value for is **en-us**.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="73075-169">Mapping dei modelli in Integrazione dati</span><span class="sxs-lookup"><span data-stu-id="73075-169">Template mapping in Data integration</span></span>

<span data-ttu-id="73075-170">Nelle figure seguenti viene illustrato un esempio di mapping di modelli in Integrazione dati.</span><span class="sxs-lookup"><span data-stu-id="73075-170">The following illustrations show an example of a template mapping in Data integration.</span></span> 

> [!NOTE]
> <span data-ttu-id="73075-171">Il mapping mostra quali informazioni sui campi verranno sincronizzate da Sales in Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="73075-171">The mapping shows which field information will be synchronized from Sales to Supply Chain Management.</span></span>

### <a name="contact-to-contact"></a><span data-ttu-id="73075-172">Da contatto a contatto</span><span class="sxs-lookup"><span data-stu-id="73075-172">Contact to contact</span></span>

![Mapping dei modelli nell'integratore di dati](./media/contacts-direct-template-mapping-data-integrator-1.png)

### <a name="contact-to-customer"></a><span data-ttu-id="73075-174">Da contatto a cliente</span><span class="sxs-lookup"><span data-stu-id="73075-174">Contact to customer</span></span>

![Mapping dei modelli nell'integratore di dati](./media/contacts-direct-template-mapping-data-integrator-2.png)


## <a name="related-topics"></a><span data-ttu-id="73075-176">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="73075-176">Related topics</span></span>

[<span data-ttu-id="73075-177">Prospect per uno scenario di liquidazione</span><span class="sxs-lookup"><span data-stu-id="73075-177">Prospect to cash</span></span>](prospect-to-cash.md)

[<span data-ttu-id="73075-178">Sincronizzare conti direttamente da Sales con clienti in Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="73075-178">Synchronize accounts directly from Sales to customers in Supply Chain Management</span></span>](accounts-template-mapping-direct.md)

[<span data-ttu-id="73075-179">Sincronizzare prodotti direttamente da Supply Chain Management con prodotti in Sales</span><span class="sxs-lookup"><span data-stu-id="73075-179">Synchronize products directly from Supply Chain Management to products in Sales</span></span>](products-template-mapping-direct.md)

[<span data-ttu-id="73075-180">Sincronizzazione degli ordini cliente direttamente tra Sales e Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="73075-180">Synchronization of sales orders directly between Sales and Supply Chain Management</span></span>](sales-order-template-mapping-direct-two-ways.md)

[<span data-ttu-id="73075-181">Sincronizzare intestazioni e righe di fatture di vendita direttamente da Supply Chain Management in Sales</span><span class="sxs-lookup"><span data-stu-id="73075-181">Synchronize sales invoice headers and lines directly from Supply Chain Management to Sales</span></span>](sales-invoice-template-mapping-direct.md)


