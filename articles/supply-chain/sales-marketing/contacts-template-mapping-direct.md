---
title: Sincronizzare contatti direttamente da Sales con contatti o clienti in Finance and Operations
description: "Questo argomento descrive i modelli e le attività sottostanti che vengono utilizzati per sincronizzare entità Contatto (Contatti) e Contatto (Clienti) da Microsoft Dynamics 365 for Sales in Microsoft Dynamics 365 for Finance and Operations, Enterprise edition."
author: ChristianRytt
manager: AnnBe
ms.date: 10/25/2017
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
ms.openlocfilehash: 8de9a920f384b69c9b3764a0431208bbdcb395bf
ms.contentlocale: it-it
ms.lasthandoff: 11/03/2017

---

# <a name="synchronize-contacts-directly-from-sales-to-contacts-or-customers-in-finance-and-operations"></a><span data-ttu-id="bd67b-103">Sincronizzare contatti direttamente da Sales con contatti o clienti in Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="bd67b-103">Synchronize contacts directly from Sales to contacts or customers in Finance and Operations</span></span>

[!include[banner](../includes/banner.md)]

> [!NOTE]
> <span data-ttu-id="bd67b-104">Prima di utilizzare la soluzione Prospect to cash, è necessario acquisire familiarità con [Integrazione dati di Dynamics 365](/common-data-service/entity-reference/dynamics-365-integration).</span><span class="sxs-lookup"><span data-stu-id="bd67b-104">Before you can use the Prospect to cash solution, you should be familiar with [Dynamics 365 Data integration](/common-data-service/entity-reference/dynamics-365-integration).</span></span>

<span data-ttu-id="bd67b-105">Questo argomento descrive i modelli e le attività sottostanti che vengono utilizzati per sincronizzare entità Contatto (Contatti) e Contatto (Clienti) direttamente da Microsoft Dynamics 365 for Sales in Microsoft Dynamics 365 for Finance and Operations, Enterprise edition.</span><span class="sxs-lookup"><span data-stu-id="bd67b-105">This topic discusses the templates and underlying tasks that are used to synchronize Contact (Contacts) and Contact (Customers) entities directly from Microsoft Dynamics 365 for Sales to Microsoft Dynamics 365 for Finance and Operations, Enterprise edition.</span></span>

## <a name="data-flow-in-prospect-to-cash"></a><span data-ttu-id="bd67b-106">Flusso di dati in Prospect to cash</span><span class="sxs-lookup"><span data-stu-id="bd67b-106">Data flow in Prospect to cash</span></span>

<span data-ttu-id="bd67b-107">La soluzione Prospect to cash utilizza la funzionalità Integrazione dati per sincronizzare i dati tra istanze di Finance and Operations e Sales.</span><span class="sxs-lookup"><span data-stu-id="bd67b-107">The Prospect to cash solution uses the Data integration feature to synchronize data across instances of Finance and Operations and Sales.</span></span> <span data-ttu-id="bd67b-108">I modelli Prospect to cash disponibili con la funzionalità Integrazione dati consentono il flusso di dati relativo a conti, contatti, prodotti, offerte di vendita, ordini cliente e fatture di vendita tra Finance and Operations e Sales.</span><span class="sxs-lookup"><span data-stu-id="bd67b-108">The Prospect to cash templates that are available with the Data integration feature enable the flow of data about accounts, contacts, products, sales quotations, sales orders, and sales invoices between Finance and Operations and Sales.</span></span> <span data-ttu-id="bd67b-109">La figura seguente mostra il modo in cui i dati vengono sincronizzati tra Finance and Operations e Sales.</span><span class="sxs-lookup"><span data-stu-id="bd67b-109">The following illustration shows how the data is synchronized between Finance and Operations and Sales.</span></span>

<span data-ttu-id="bd67b-110">[![Flusso di dati in Prospect to cash](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)</span><span class="sxs-lookup"><span data-stu-id="bd67b-110">[![Data flow in Prospect to cash](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="bd67b-111">Modelli e attività</span><span class="sxs-lookup"><span data-stu-id="bd67b-111">Templates and tasks</span></span>

<span data-ttu-id="bd67b-112">Per accedere ai modelli disponibili, aprire l'[Interfaccia di amministrazione di PowerApps](https://preview.admin.powerapps.com/dataintegration).</span><span class="sxs-lookup"><span data-stu-id="bd67b-112">To access the available templates, open [PowerApps Admin Center](https://preview.admin.powerapps.com/dataintegration).</span></span> <span data-ttu-id="bd67b-113">Selezionare **Progetti**, quindi nell'angolo superiore destro, selezionare **Nuovo progetto** per selezionare i modelli pubblici.</span><span class="sxs-lookup"><span data-stu-id="bd67b-113">Select **Projects**, and then, in the upper-right corner, select **New project** to select public templates.</span></span>

<span data-ttu-id="bd67b-114">I seguenti modelli e attività sottostanti vengono utilizzati per sincronizzare entità Contatto (Contatti) in Sales a entità Contatto (Clienti) in Finance and Operations:</span><span class="sxs-lookup"><span data-stu-id="bd67b-114">The following templates and underlying tasks are used to synchronize Contact (Contacts) entities in Sales to Contact (Customers) entities in Finance and Operations:</span></span>

- <span data-ttu-id="bd67b-115">**Nomi dei modelli in Integrazione dati:**</span><span class="sxs-lookup"><span data-stu-id="bd67b-115">**Names of the templates in Data integration:**</span></span>

    - <span data-ttu-id="bd67b-116">Contatti (da Sales in Fin and Ops) - Diretto</span><span class="sxs-lookup"><span data-stu-id="bd67b-116">Contacts (Sales to Fin and Ops) - Direct</span></span>
    - <span data-ttu-id="bd67b-117">Da Contatti a Cliente (da Sales in Fin and Ops) - Diretto</span><span class="sxs-lookup"><span data-stu-id="bd67b-117">Contacts to Customer (Sales to Fin and Ops) - Direct</span></span>

- <span data-ttu-id="bd67b-118">**Nomi delle attività nel progetto di Integrazione dati:**</span><span class="sxs-lookup"><span data-stu-id="bd67b-118">**Names of the tasks in the Data integration project:**</span></span>

    - <span data-ttu-id="bd67b-119">Contatti</span><span class="sxs-lookup"><span data-stu-id="bd67b-119">Contacts</span></span>
    - <span data-ttu-id="bd67b-120">ContactToCustomer</span><span class="sxs-lookup"><span data-stu-id="bd67b-120">ContactToCustomer</span></span>

<span data-ttu-id="bd67b-121">La seguente attività di sincronizzazione è necessaria prima della sincronizzazione dei contatti: Conti (da Sales in Fin and Ops)</span><span class="sxs-lookup"><span data-stu-id="bd67b-121">The following synchronization task is required before contact synchronization can occur: Accounts (Sales to Fin and Ops)</span></span>

## <a name="entity-sets"></a><span data-ttu-id="bd67b-122">Insiemi di entità</span><span class="sxs-lookup"><span data-stu-id="bd67b-122">Entity sets</span></span>

| <span data-ttu-id="bd67b-123">Vendite</span><span class="sxs-lookup"><span data-stu-id="bd67b-123">Sales</span></span>    | <span data-ttu-id="bd67b-124">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="bd67b-124">Finance and Operations</span></span> |
|----------|------------------------|
| <span data-ttu-id="bd67b-125">Contatti</span><span class="sxs-lookup"><span data-stu-id="bd67b-125">Contacts</span></span> | <span data-ttu-id="bd67b-126">Contatti CDS</span><span class="sxs-lookup"><span data-stu-id="bd67b-126">CDS Contacts</span></span>           |
| <span data-ttu-id="bd67b-127">Contatti</span><span class="sxs-lookup"><span data-stu-id="bd67b-127">Contacts</span></span> | <span data-ttu-id="bd67b-128">Clienti V2</span><span class="sxs-lookup"><span data-stu-id="bd67b-128">Customers V2</span></span>           |

## <a name="entity-flow"></a><span data-ttu-id="bd67b-129">Flusso di entità</span><span class="sxs-lookup"><span data-stu-id="bd67b-129">Entity flow</span></span>

<span data-ttu-id="bd67b-130">I contatti vengono gestiti in Sales e sincronizzati in Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="bd67b-130">Contacts are managed in Sales and synchronized to Finance and Operations.</span></span>

<span data-ttu-id="bd67b-131">Un contatto in Sales può diventare un contatto o un cliente in Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="bd67b-131">A contact in Sales can become either a contact or a customer in Finance and Operations.</span></span> <span data-ttu-id="bd67b-132">Per stabilire se un contatto in Sales deve essere sincronizzato in Finance and Operations come contatto o cliente, il sistema esamina le seguenti proprietà del contatto in Sales:</span><span class="sxs-lookup"><span data-stu-id="bd67b-132">To determine whether a contact in Sales should be synchronized to Finance and Operations as a contact or a customer, the system looks at the following properties on the contact in Sales:</span></span>

- <span data-ttu-id="bd67b-133">**Sincronizzazione a un cliente in Finance and Operations:** Contatti dove l'opzione **Si tratta del cliente attivo** è impostata su **Sì**</span><span class="sxs-lookup"><span data-stu-id="bd67b-133">**Synchronization to a customer in Finance and Operations:** Contacts where **Is Active Customer** is set to **Yes**</span></span>
- <span data-ttu-id="bd67b-134">**Sincronizzazione a un contatto in Finance and Operations:** Contatti dove l'opzione **Si tratta del cliente attivo** è impostata su **No** e **Società** (conto/contatto principale) punta a un conto (non a un contatto)</span><span class="sxs-lookup"><span data-stu-id="bd67b-134">**Synchronization to a contact in Finance and Operations:** Contacts where **Is Active Customer** is set to **No** and **Company** (parent account/contact) points to an account (not a contact)</span></span>

## <a name="prospect-to-cash-solution-for-sales"></a><span data-ttu-id="bd67b-135">Soluzione Prospect to cash per Sales</span><span class="sxs-lookup"><span data-stu-id="bd67b-135">Prospect to cash solution for Sales</span></span>

<span data-ttu-id="bd67b-136">Un nuovo campo **Si tratta del cliente attivo** è stato aggiunto al contatto.</span><span class="sxs-lookup"><span data-stu-id="bd67b-136">A new **Is Active Customer** field has been added to the contact.</span></span> <span data-ttu-id="bd67b-137">Questo campo viene utilizzato per distinguere i contatti che hanno attività di vendita dai contatti che non ne hanno.</span><span class="sxs-lookup"><span data-stu-id="bd67b-137">This field is used to differentiate contacts that have sales activity and contacts that don't have sales activity.</span></span> <span data-ttu-id="bd67b-138">L'opzione **Si tratta del cliente attivo** è impostata su **Sì** solo per i contatti con offerte, ordini o fatture correlate.</span><span class="sxs-lookup"><span data-stu-id="bd67b-138">**Is Active Customer** is set to **Yes** only for contacts that have related quotations, orders, or invoices.</span></span> <span data-ttu-id="bd67b-139">Solo tali contatti vengono sincronizzati in Finance and Operations come clienti.</span><span class="sxs-lookup"><span data-stu-id="bd67b-139">Only those contacts are synchronized to Finance and Operations as customers.</span></span>

<span data-ttu-id="bd67b-140">Un nuovo campo **IsCompanyAnAccount** è stato aggiunto al contatto.</span><span class="sxs-lookup"><span data-stu-id="bd67b-140">A new **IsCompanyAnAccount** field has been added to the contact.</span></span> <span data-ttu-id="bd67b-141">Questo campo indica se un contatto è collegato a una società (conto/contatto principale) di tipo **Conto**.</span><span class="sxs-lookup"><span data-stu-id="bd67b-141">This field indicates whether a contact is linked to a company (parent account/contact) of the **Account** type.</span></span> <span data-ttu-id="bd67b-142">Queste informazioni vengono utilizzate per identificare i contatti che devono essere sincronizzati in Finance and Operations come contatti.</span><span class="sxs-lookup"><span data-stu-id="bd67b-142">This information is used to identify contacts that should be synchronized to Finance and Operations as contacts.</span></span>

<span data-ttu-id="bd67b-143">Un nuovo campo **Numero del contatto** è stato aggiunto al contatto per assicurare una chiave naturale e univoca per l'integrazione.</span><span class="sxs-lookup"><span data-stu-id="bd67b-143">A new **Contact Number** field has been added to the contact to help guarantee a natural and unique key for the integration.</span></span> <span data-ttu-id="bd67b-144">Quando si crea un nuovo contatto, viene generato automaticamente un valore **Numero del contatto** utilizzando una sequenza numerica.</span><span class="sxs-lookup"><span data-stu-id="bd67b-144">When a new contact is created, a **Contact Number** value is automatically generated by using a number sequence.</span></span> <span data-ttu-id="bd67b-145">Il valore consiste di **CON**, seguito da una sequenza numerica crescente, quindi da un suffisso di sei caratteri.</span><span class="sxs-lookup"><span data-stu-id="bd67b-145">The value consists of **CON**, followed by an increasing number sequence and then a suffix of six characters.</span></span> <span data-ttu-id="bd67b-146">Ecco un esempio: **CON-01000-BVRCPS**</span><span class="sxs-lookup"><span data-stu-id="bd67b-146">Here is an example: **CON-01000-BVRCPS**</span></span>

<span data-ttu-id="bd67b-147">Quando la soluzione di integrazione per Sales viene applicata, uno script di aggiornamento imposta il campo **Numero del contatto** per i contatti esistenti utilizzando la sequenza numerica menzionata in precedenza.</span><span class="sxs-lookup"><span data-stu-id="bd67b-147">When the integration solution for Sales is applied, an upgrade script sets the **Contact Number** field for existing contacts by using the number sequence that was mentioned earlier.</span></span> <span data-ttu-id="bd67b-148">Lo script di aggiornamento imposta inoltre il campo **Si tratta del cliente attivo** su **Sì** per qualsiasi contatto con attività di vendita.</span><span class="sxs-lookup"><span data-stu-id="bd67b-148">The upgrade script also sets the **Is Active Customer** field to **Yes** for any contacts that have sales activity.</span></span>

## <a name="in-finance-and-operations"></a><span data-ttu-id="bd67b-149">In Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="bd67b-149">In Finance and Operations</span></span>

<span data-ttu-id="bd67b-150">AI Contatti vengono assegnati tag tramite l'utilizzo della proprietà **IsContactPersonExternallyMaintained**.</span><span class="sxs-lookup"><span data-stu-id="bd67b-150">Contacts are tagged by using the **IsContactPersonExternallyMaintained** property.</span></span> <span data-ttu-id="bd67b-151">Questa proprietà indica che un contatto specifico viene gestito esternamente.</span><span class="sxs-lookup"><span data-stu-id="bd67b-151">This property indicates that a given contact is maintained externally.</span></span> <span data-ttu-id="bd67b-152">In questo caso, i contatti gestiti esternamente vengono gestiti in Sales.</span><span class="sxs-lookup"><span data-stu-id="bd67b-152">In this case, externally maintained contacts are maintained in Sales.</span></span>

## <a name="preconditions-and-mapping-setup"></a><span data-ttu-id="bd67b-153">Prerequisiti e impostazioni di mapping</span><span class="sxs-lookup"><span data-stu-id="bd67b-153">Preconditions and mapping setup</span></span>

### <a name="contact-to-customer"></a><span data-ttu-id="bd67b-154">Da contatto a cliente</span><span class="sxs-lookup"><span data-stu-id="bd67b-154">Contact to customer</span></span>

- <span data-ttu-id="bd67b-155">**CustomerGroup** è obbligatorio in Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="bd67b-155">**CustomerGroup** is required in Finance and Operations.</span></span> <span data-ttu-id="bd67b-156">Per prevenire errori di sincronizzazione, è possibile specificare un valore predefinito nel mapping.</span><span class="sxs-lookup"><span data-stu-id="bd67b-156">To help prevent synchronization errors, you can specify a default value in the mapping.</span></span> <span data-ttu-id="bd67b-157">Tale valore predefinito viene quindi utilizzato se il campo viene lasciato vuoto in Sales.</span><span class="sxs-lookup"><span data-stu-id="bd67b-157">That default value is then used if the field is left blank in Sales.</span></span>

    <span data-ttu-id="bd67b-158">Il valore del modello predefinito è **10**.</span><span class="sxs-lookup"><span data-stu-id="bd67b-158">The default template value is **10**.</span></span>

- <span data-ttu-id="bd67b-159">Aggiungendo i seguenti mapping, è possibile consentire una riduzione del numero degli aggiornamenti manuali necessari in Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="bd67b-159">By adding the following mappings, you can help reduce the number of manual updates that are required in Finance and Operations.</span></span> <span data-ttu-id="bd67b-160">È possibile utilizzare un valore predefinito o una mappa di valori da, ad esempio, **Paese** o **Città**.</span><span class="sxs-lookup"><span data-stu-id="bd67b-160">You can use a default value or a value map from, for example, **Country/Region** or **City**.</span></span>

    - <span data-ttu-id="bd67b-161">**SiteId** - Un sito predefinito può inoltre essere definito per i prodotti in Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="bd67b-161">**SiteId** – A default site can also be defined on products in Finance and Operations.</span></span> <span data-ttu-id="bd67b-162">Un sito è obbligatorio per la generazione di offerte e ordini cliente in Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="bd67b-162">A site is required in order to generate quotations and sales orders in Finance and Operations.</span></span>

        <span data-ttu-id="bd67b-163">Un modello di valore per **SiteId** non è definito.</span><span class="sxs-lookup"><span data-stu-id="bd67b-163">A template value for **SiteId** isn't defined.</span></span>

    - <span data-ttu-id="bd67b-164">**WarehouseId** - Un magazzino predefinito può inoltre essere definito per i prodotti in Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="bd67b-164">**WarehouseId** – A default warehouse can also be defined on products in Finance and Operations.</span></span> <span data-ttu-id="bd67b-165">Un magazzino è obbligatorio per la generazione di offerte e ordini cliente in Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="bd67b-165">A warehouse is required in order to generate quotations and sales orders in Finance and Operations.</span></span>

        <span data-ttu-id="bd67b-166">Un modello di valore per **WarehouseId** non è definito.</span><span class="sxs-lookup"><span data-stu-id="bd67b-166">A template value for **WarehouseId** isn't defined.</span></span>

    - <span data-ttu-id="bd67b-167">**LanguageId** - Una lingua è obbligatoria per la generazione di offerte e ordini cliente in Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="bd67b-167">**LanguageId** – A language is required in order to generate quotations and sales orders in Finance and Operations.</span></span>
    
        <span data-ttu-id="bd67b-168">Il valore di modello predefinito è **en-us**.</span><span class="sxs-lookup"><span data-stu-id="bd67b-168">The default template value for is **en-us**.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="bd67b-169">Mapping dei modelli in Integrazione dati</span><span class="sxs-lookup"><span data-stu-id="bd67b-169">Template mapping in Data integration</span></span>

<span data-ttu-id="bd67b-170">Nelle figure seguenti viene illustrato un esempio di mapping di modelli in Integrazione dati.</span><span class="sxs-lookup"><span data-stu-id="bd67b-170">The following illustrations show an example of a template mapping in Data integration.</span></span> 

> [!NOTE]
> <span data-ttu-id="bd67b-171">Il mapping mostra quali informazioni sui campi verranno sincronizzate da Sales in Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="bd67b-171">The mapping shows which field information will be synchronized from Sales to Finance and Operations.</span></span>

### <a name="contact-to-contact"></a><span data-ttu-id="bd67b-172">Da contatto a contatto</span><span class="sxs-lookup"><span data-stu-id="bd67b-172">Contact to contact</span></span>

![Mapping dei modelli nell'integratore di dati](./media/contacts-direct-template-mapping-data-integrator-1.png)

### <a name="contact-to-customer"></a><span data-ttu-id="bd67b-174">Da contatto a cliente</span><span class="sxs-lookup"><span data-stu-id="bd67b-174">Contact to customer</span></span>

![Mapping dei modelli nell'integratore di dati](./media/contacts-direct-template-mapping-data-integrator-2.png)


## <a name="related-topics"></a><span data-ttu-id="bd67b-176">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="bd67b-176">Related topics</span></span>

[<span data-ttu-id="bd67b-177">Prospect to cash</span><span class="sxs-lookup"><span data-stu-id="bd67b-177">Prospect to cash</span></span>](prospect-to-cash.md)

[<span data-ttu-id="bd67b-178">Sincronizzare conti direttamente da Sales con clienti in Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="bd67b-178">Synchronize accounts directly from Sales to customers in Finance and Operations</span></span>](accounts-template-mapping-direct.md)

[<span data-ttu-id="bd67b-179">Sincronizzare prodotti direttamente da Finance and Operations con prodotti in Sales</span><span class="sxs-lookup"><span data-stu-id="bd67b-179">Synchronize products directly from Finance and Operations to products in Sales</span></span>](products-template-mapping-direct.md)

[<span data-ttu-id="bd67b-180">Sincronizzare intestazioni e righe di ordini cliente direttamente da Finance and Operations in Sales</span><span class="sxs-lookup"><span data-stu-id="bd67b-180">Synchronize sales order headers and lines directly from Finance and Operations to Sales</span></span>](sales-order-template-mapping-direct.md)

[<span data-ttu-id="bd67b-181">Sincronizzare intestazioni e righe di fatture di vendita direttamente da Finance and Operations in Sales</span><span class="sxs-lookup"><span data-stu-id="bd67b-181">Synchronize sales invoice headers and lines directly from Finance and Operations to Sales</span></span>](sales-invoice-template-mapping-direct.md)



