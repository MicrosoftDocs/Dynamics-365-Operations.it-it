---
title: Sincronizzare contatti da Sales a contatti o clienti in Finance and Operations
description: "Questo argomento descrive i modelli e le attività sottostanti che vengono utilizzati per sincronizzare Contatto (Contatti) e Contatto (Clienti) da Microsoft Dynamics 365 for Sales in Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition."
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
ms.openlocfilehash: c838fef502f643c764fade9cd79ae770ffc36974
ms.contentlocale: it-it
ms.lasthandoff: 11/03/2017

---

# <a name="synchronize-contacts-from-sales-to-contacts-or-customers-in-finance-and-operations"></a><span data-ttu-id="36727-103">Sincronizzare contatti da Sales a contatti o clienti in Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="36727-103">Synchronize contacts from Sales to contacts or customers in Finance and Operations</span></span>

[!include[banner](../includes/banner.md)]

> [!NOTE]
> <span data-ttu-id="36727-104">Prima di utilizzare la soluzione Prospect to cash, acquisisci familiarità con [Integrazione dei dati di Microsoft Dynamics 365](/common-data-service/entity-reference/dynamics-365-integration).</span><span class="sxs-lookup"><span data-stu-id="36727-104">Before you can use the Prospect to cash solution, be familiar with [Dynamics 365 Data Integration](/common-data-service/entity-reference/dynamics-365-integration).</span></span> 

<span data-ttu-id="36727-105">Questo argomento descrive i modelli e le attività sottostanti che vengono utilizzati per sincronizzare le entità Contatto (Contatti) e Contatto (Clienti) da Microsoft Dynamics 365 for Sales (Sales) in Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition (Finance and Operations).</span><span class="sxs-lookup"><span data-stu-id="36727-105">This topic discusses the templates and underlying tasks that are used to synchronize Contact (Contacts) entities and Contact (Customers) from Microsoft Dynamics 365 for Sales (Sales) to Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (Finance and Operations).</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="36727-106">Modelli e attività</span><span class="sxs-lookup"><span data-stu-id="36727-106">Templates and tasks</span></span>

<span data-ttu-id="36727-107">I modelli e le attività sottostanti che seguono vengono utilizzati per sincronizzare da Contatto (Contatti) in Sales a Contatto (Clienti) in Finance and Operations:</span><span class="sxs-lookup"><span data-stu-id="36727-107">The following templates and underlying tasks are used to synchronize Contact (Contacts) in Sales to Contact (Customers) in Finance and Operations:</span></span>

- <span data-ttu-id="36727-108">**Nomi dei modelli:**</span><span class="sxs-lookup"><span data-stu-id="36727-108">**Names of the templates:**</span></span>

    - <span data-ttu-id="36727-109">Contatti (da Sales in Fin and Ops)</span><span class="sxs-lookup"><span data-stu-id="36727-109">Contacts (Sales to Fin and Ops)</span></span>
    - <span data-ttu-id="36727-110">Da Contatti a Cliente (da Sales in Fin and Ops)</span><span class="sxs-lookup"><span data-stu-id="36727-110">Contacts to Customer (Sales to Fin and Ops)</span></span>

- <span data-ttu-id="36727-111">**Nomi delle attività del progetto:**</span><span class="sxs-lookup"><span data-stu-id="36727-111">**Names of the tasks in the project:**</span></span>

    - <span data-ttu-id="36727-112">Contatti</span><span class="sxs-lookup"><span data-stu-id="36727-112">Contacts</span></span>
    - <span data-ttu-id="36727-113">ContactToCustomer</span><span class="sxs-lookup"><span data-stu-id="36727-113">ContactToCustomer</span></span>

<span data-ttu-id="36727-114">La seguente attività di sincronizzazione è richiesta prima della sincronizzazione di Contatto: Conti (da Sales in Fin and Ops)</span><span class="sxs-lookup"><span data-stu-id="36727-114">The following synchronization task is required before Contact synchronization: Accounts (Sales to Fin and Ops)</span></span>

## <a name="entity-sets"></a><span data-ttu-id="36727-115">Insiemi di entità</span><span class="sxs-lookup"><span data-stu-id="36727-115">Entity sets</span></span>

| <span data-ttu-id="36727-116">Vendite</span><span class="sxs-lookup"><span data-stu-id="36727-116">Sales</span></span>    | <span data-ttu-id="36727-117">CDS</span><span class="sxs-lookup"><span data-stu-id="36727-117">CDS</span></span>     | <span data-ttu-id="36727-118">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="36727-118">Finance and Operations</span></span> |
|----------|---------|------------------------|
| <span data-ttu-id="36727-119">Contatti</span><span class="sxs-lookup"><span data-stu-id="36727-119">Contacts</span></span> | <span data-ttu-id="36727-120">Contatto</span><span class="sxs-lookup"><span data-stu-id="36727-120">Contact</span></span> | <span data-ttu-id="36727-121">Contatti CDS</span><span class="sxs-lookup"><span data-stu-id="36727-121">CDS Contacts</span></span>           |
| <span data-ttu-id="36727-122">Contatti</span><span class="sxs-lookup"><span data-stu-id="36727-122">Contacts</span></span> | <span data-ttu-id="36727-123">Conto</span><span class="sxs-lookup"><span data-stu-id="36727-123">Account</span></span> | <span data-ttu-id="36727-124">Clienti V2</span><span class="sxs-lookup"><span data-stu-id="36727-124">Customers V2</span></span>           |

## <a name="entity-flow"></a><span data-ttu-id="36727-125">Flusso di entità</span><span class="sxs-lookup"><span data-stu-id="36727-125">Entity flow</span></span>

<span data-ttu-id="36727-126">I Contatti vengono gestiti in Sales e vengono sincronizzati con Common Data Service (CDS) e Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="36727-126">Contacts are managed in Sales, and are synchronized to Common Data Service (CDS) and Finance and Operations.</span></span>

<span data-ttu-id="36727-127">Un contatto in Sales può diventare un Contatto in CDS e Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="36727-127">A Contact in Sales can become a Contact in CDS and Finance and Operations.</span></span> <span data-ttu-id="36727-128">In alternativa, può diventare un Conto in CDS e un Cliente in Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="36727-128">Alternatively, it can become an Account in CDS and a Customer in Finance and Operations.</span></span> <span data-ttu-id="36727-129">Per stabilire se un contatto deve essere prelevato in Sales per la sincronizzazione con CDS e Finance and Operations (ad esempio Contatti in Sales &gt; Contatto in CDS &gt; Contatti in Finance and Operations), il sistema rivede le seguenti proprietà di Contatto in Sales:</span><span class="sxs-lookup"><span data-stu-id="36727-129">To determine whether a contact should be picked up in Sales for synchronization to CDS and Finance and Operations (for example, Contacts in Sales &gt; Contact in CDS &gt; Contacts in Finance and Operations), the system looks at the following properties on Contact in Sales:</span></span>

- <span data-ttu-id="36727-130">**Sincronizzazione con Conto in CDS e Cliente in Finance and Operations:** Contatti dove l'opzione **Si tratta del cliente attivo** è impostata su **Sì**</span><span class="sxs-lookup"><span data-stu-id="36727-130">**Sync to Account in CDS and Customer in Finance and Operations:** Contacts where **Is Active Customer** is set to **Yes**</span></span>
- <span data-ttu-id="36727-131">**Sincronizzazione con Contatti in CDS e Contatto in Finance and Operations:** Contatti dove l'opzione **Si tratta del cliente attivo** è impostata su **No** e **Società** (Conto/Contatto principale) punta a un Conto (non a un Contatto)</span><span class="sxs-lookup"><span data-stu-id="36727-131">**Sync to Contact in CDS and Contact in Finance and Operations:** Contacts where **Is Active Customer** is set to **No** and **Company** (Parent Account/Contact) points to an Account (not a Contact)</span></span>

## <a name="prospect-to-cash-solution-for-sales"></a><span data-ttu-id="36727-132">Soluzione Prospect to cash per Sales</span><span class="sxs-lookup"><span data-stu-id="36727-132">Prospect to cash solution for Sales</span></span> 

<span data-ttu-id="36727-133">Un nuovo campo **Si tratta del cliente attivo** è stato aggiunto al Contatto.</span><span class="sxs-lookup"><span data-stu-id="36727-133">A new **Is Active Customer** field has been added to the Contact.</span></span> <span data-ttu-id="36727-134">Questo campo viene utilizzato per distinguere i Contatti con attività di vendita dai Contatti privi di attività di vendita.</span><span class="sxs-lookup"><span data-stu-id="36727-134">This field is used to differentiate Contacts that have sales activity and Contacts that don't have sales activity.</span></span> <span data-ttu-id="36727-135">L'opzione **Si tratta del cliente attivo** è impostata su **Sì** solo per i Contatti con offerte, ordini o fatture correlate.</span><span class="sxs-lookup"><span data-stu-id="36727-135">**Is Active Customer** is set to **Yes** only for Contacts that have related quotations, orders, or invoices.</span></span> <span data-ttu-id="36727-136">Solo tali Contatti vengono sincronizzati con Finance and Operations come Clienti.</span><span class="sxs-lookup"><span data-stu-id="36727-136">Only those Contacts are synchronized to Finance and Operations as Customers.</span></span>

<span data-ttu-id="36727-137">Un nuovo campo **IsCompanyAnAccount** è stato aggiunto al Contatto.</span><span class="sxs-lookup"><span data-stu-id="36727-137">A new **IsCompanyAnAccount** field has been added to the Contact.</span></span> <span data-ttu-id="36727-138">Questo campo viene utilizzato per indicare se un Contatto è collegato a una Società (Conto o Contatto principale) del tipo **Conto**.</span><span class="sxs-lookup"><span data-stu-id="36727-138">This field is used to indicate whether a Contact is linked to a Company (Parent Account/Contact) of the **Account** type.</span></span> <span data-ttu-id="36727-139">Queste informazioni vengono utilizzate per identificare i Contatti che devono essere sincronizzati con Finance and Operations come Contatti.</span><span class="sxs-lookup"><span data-stu-id="36727-139">This information is used to identify Contacts that should be synchronized to Finance and Operations as Contacts.</span></span>

<span data-ttu-id="36727-140">Un nuovo campo **Numero del contatto** è stato aggiunto al Contatto per garantire una chiave naturale e univoca per l'integrazione.</span><span class="sxs-lookup"><span data-stu-id="36727-140">A new **Contact Number** field has been added to the Contact to help guarantee a natural and unique key for the integration.</span></span> <span data-ttu-id="36727-141">Quando si crea un nuovo Contatto, viene generato automaticamente un valore **Numero del contatto** utilizzando una sequenza numerica.</span><span class="sxs-lookup"><span data-stu-id="36727-141">When a new Contact is created, a **Contact Number** value is automatically generated by using a number sequence.</span></span> <span data-ttu-id="36727-142">Il valore consiste di **CON**, seguito da una sequenza numerica crescente, quindi da un suffisso di sei caratteri.</span><span class="sxs-lookup"><span data-stu-id="36727-142">The value consists of **CON**, followed by an increasing number sequence and then a suffix of six characters.</span></span> <span data-ttu-id="36727-143">Ecco un esempio: **CON-01000-BVRCPS**</span><span class="sxs-lookup"><span data-stu-id="36727-143">Here is an example: **CON-01000-BVRCPS**</span></span>

<span data-ttu-id="36727-144">Quando la soluzione di integrazione per Sales viene aggiunta a Sales, uno script di aggiornamento imposta il campo **Numero del contatto** per i Contatti esistenti utilizzando la sequenza numerica che è stata illustrata in precedenza.</span><span class="sxs-lookup"><span data-stu-id="36727-144">When the integration solution for Sales is added to Sales, an upgrade script sets the **Contact Number** field for existing Contacts by using the number sequence that was discussed earlier.</span></span> <span data-ttu-id="36727-145">Lo script di aggiornamento consente inoltre di impostare il campo **Si tratta del cliente attivo** su **Sì** per tutti i Contatti con attività di vendita.</span><span class="sxs-lookup"><span data-stu-id="36727-145">The upgrade script also sets the **Is Active Customer** field to **Yes** for any Contacts that have sales activity.</span></span>

## <a name="in-finance-and-operations"></a><span data-ttu-id="36727-146">In Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="36727-146">In Finance and Operations</span></span> 

<span data-ttu-id="36727-147">AI Contatti vengono assegnati tag tramite l'utilizzo della proprietà **IsContactPersonExternallyMaintained**.</span><span class="sxs-lookup"><span data-stu-id="36727-147">Contacts are tagged by using the **IsContactPersonExternallyMaintained** property.</span></span> <span data-ttu-id="36727-148">Questa proprietà indica che un contatto specifico viene gestito esternamente.</span><span class="sxs-lookup"><span data-stu-id="36727-148">This property indicates that a given Contact is maintained externally.</span></span> <span data-ttu-id="36727-149">In questo caso, i Contatti gestiti esternamente vengono gestiti in Sales.</span><span class="sxs-lookup"><span data-stu-id="36727-149">In this case, externally maintained Contacts are maintained in Sales.</span></span>

## <a name="preconditions-and-mapping-setup"></a><span data-ttu-id="36727-150">Prerequisiti e impostazioni di mapping</span><span class="sxs-lookup"><span data-stu-id="36727-150">Preconditions and mapping setup</span></span>

### <a name="contact-to-contact"></a><span data-ttu-id="36727-151">Da Contatto a Contatto</span><span class="sxs-lookup"><span data-stu-id="36727-151">Contact to Contact</span></span>

- <span data-ttu-id="36727-152">Aggiornare **ID organizzazione CDS** nel mapping **Origine &gt; CDS**.</span><span class="sxs-lookup"><span data-stu-id="36727-152">Update **CDS Organization ID** in the **Source &gt; CDS** mapping.</span></span>

    - <span data-ttu-id="36727-153">Il valore del modello predefinito per **Organization_OrganizationId [ID organizzazione]** è **ORG001**.</span><span class="sxs-lookup"><span data-stu-id="36727-153">The default template value for **Organization_OrganizationId [Organization ID]** is **ORG001**.</span></span>
    - <span data-ttu-id="36727-154">Il valore del modello predefinito per **PrimaryAccount_Organization_OrganizationId [ID organizzazione]** è **ORG001**.</span><span class="sxs-lookup"><span data-stu-id="36727-154">The default template value for **PrimaryAccount_Organization_OrganizationId [Organization ID]** is **ORG001**.</span></span>

- <span data-ttu-id="36727-155">Il **Codice paese-regione indirizzo** è obbligatorio in Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="36727-155">**Address Country region code** is required in Finance and Operations.</span></span> <span data-ttu-id="36727-156">Per evitare errori di sincronizzazione, è possibile specificare un valore predefinito nel mapping **CDS &gt; Operazioni**.</span><span class="sxs-lookup"><span data-stu-id="36727-156">To avoid synchronization errors, you can specify a default value in the **CDS &gt; Operations** mapping.</span></span> <span data-ttu-id="36727-157">Tale valore predefinito viene quindi utilizzato se il campo viene lasciato vuoto in Sales.</span><span class="sxs-lookup"><span data-stu-id="36727-157">That default value is then used if the field is left blank in Sales.</span></span> <span data-ttu-id="36727-158">Il valore del modello predefinito per **PrimaryAddressCountryRegionISOCode** è **Stati Uniti.**</span><span class="sxs-lookup"><span data-stu-id="36727-158">The default template value for **PrimaryAddressCountryRegionISOCode** is **USA**.</span></span>
- <span data-ttu-id="36727-159">Assicurarsi che un valore per il campo successivo esista in Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="36727-159">Make sure that a value for the following field exists in Finance and Operations.</span></span> <span data-ttu-id="36727-160">Se le informazioni non sono necessarie in Finance and Operations, è possibile rimuovere il mapping dal mapping **CDS &gt; Destinazione**.</span><span class="sxs-lookup"><span data-stu-id="36727-160">If the information isn't required in Finance and Operations, you can remove the mapping from the **CDS &gt; Destination** mapping.</span></span>

    - <span data-ttu-id="36727-161">**Nome campo in Finance and Operations:** Decisione</span><span class="sxs-lookup"><span data-stu-id="36727-161">**Field name in Finance and Operations:** Decision</span></span>
    - <span data-ttu-id="36727-162">**Mapping:** PrimaryAccountRole = DecisionMakingRole</span><span class="sxs-lookup"><span data-stu-id="36727-162">**Mapping:** PrimaryAccountRole = DecisionMakingRole</span></span>

### <a name="contact-to-customer"></a><span data-ttu-id="36727-163">Da Contatto a Cliente</span><span class="sxs-lookup"><span data-stu-id="36727-163">Contact to Customer</span></span>

- <span data-ttu-id="36727-164">Aggiornare **ID organizzazione CDS** nel mapping **Origine &gt; CDS**.</span><span class="sxs-lookup"><span data-stu-id="36727-164">Update **CDS Organization ID** in the **Source &gt; CDS** mapping.</span></span> <span data-ttu-id="36727-165">Il valore del modello predefinito per **Organization_OrganizationId [ID organizzazione]** è **ORG001**.</span><span class="sxs-lookup"><span data-stu-id="36727-165">The default template value for **Organization_OrganizationId [Organization ID]** is **ORG001**.</span></span>
- <span data-ttu-id="36727-166">Il **Codice paese-regione indirizzo** è obbligatorio in Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="36727-166">**Address Country region code** is required in Finance and Operations.</span></span> <span data-ttu-id="36727-167">Per evitare errori di sincronizzazione, è possibile specificare un valore predefinito nel mapping **CDS &gt; Destinazione**.</span><span class="sxs-lookup"><span data-stu-id="36727-167">To avoid synchronization errors, you can specify a default value in the **CDS &gt; Destination** mapping.</span></span> <span data-ttu-id="36727-168">Tale valore predefinito viene quindi utilizzato se il campo viene lasciato vuoto in Sales.</span><span class="sxs-lookup"><span data-stu-id="36727-168">That default value is then used if the field is left blank in Sales.</span></span> <span data-ttu-id="36727-169">Il valore del modello predefinito per **PrimaryAddressCountryRegionISOCode** è **Stati Uniti.**</span><span class="sxs-lookup"><span data-stu-id="36727-169">The default template value for **PrimaryAddressCountryRegionISOCode** is **USA**.</span></span>
- <span data-ttu-id="36727-170">**CustomerGroup** è obbligatorio in Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="36727-170">**CustomerGroup** is required in Finance and Operations.</span></span> <span data-ttu-id="36727-171">Per evitare errori di sincronizzazione, è possibile specificare un valore predefinito nel mapping **CDS &gt; Destinazione**.</span><span class="sxs-lookup"><span data-stu-id="36727-171">To avoid synchronization errors, you can specify a default value in the **CDS &gt; Destination** mapping.</span></span> <span data-ttu-id="36727-172">Tale valore predefinito viene quindi utilizzato se il campo viene lasciato vuoto in Sales.</span><span class="sxs-lookup"><span data-stu-id="36727-172">That default value is then used if the field is left blank in Sales.</span></span> <span data-ttu-id="36727-173">Il valore del modello predefinito per **CustomerGroupId** è **10**.</span><span class="sxs-lookup"><span data-stu-id="36727-173">The default template value for **CustomerGroupId** is **10**.</span></span>
- <span data-ttu-id="36727-174">Aggiungendo i seguenti mapping da **CDS &gt; Destinazione**, è possibile consentire una riduzione del numero degli aggiornamenti manuali che sono in Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="36727-174">By adding the following mappings from **CDS &gt; Destination**, you can help reduce the number of manual updates that are in Finance and Operations.</span></span> <span data-ttu-id="36727-175">È possibile utilizzare un valore predefinito o una mappa di valori da, ad esempio, **Paese** o **Città**.</span><span class="sxs-lookup"><span data-stu-id="36727-175">You can use a default value or a value map from, for example, **Country/Region** or **City**.</span></span>

    - <span data-ttu-id="36727-176">**SiteId**: un sito predefinito può inoltre essere definito per i prodotti in Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="36727-176">**SiteId** - A default site can also be defined on products in Finance and Operations.</span></span> <span data-ttu-id="36727-177">Un sito è obbligatorio per la generazione di offerte e ordini cliente in Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="36727-177">A site is required in order to generate quotations and sales orders in Finance and Operations.</span></span> <span data-ttu-id="36727-178">Un modello di valore per **SiteId** non è definito.</span><span class="sxs-lookup"><span data-stu-id="36727-178">A template value for **SiteId** isn't defined.</span></span>
    - <span data-ttu-id="36727-179">**WarehouseId**: un magazzino predefinito può inoltre essere definito per i prodotti in Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="36727-179">**WarehouseId** - A default warehouse can also be defined on products in Finance and Operations.</span></span> <span data-ttu-id="36727-180">Un magazzino è obbligatorio per la generazione di offerte e ordini cliente in Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="36727-180">A warehouse is required in order to generate quotations and sales orders in Finance and Operations.</span></span> <span data-ttu-id="36727-181">Un modello di valore per **WarehouseId** non è definito.</span><span class="sxs-lookup"><span data-stu-id="36727-181">A template value for **WarehouseId** isn't defined.</span></span>
    - <span data-ttu-id="36727-182">**LanguageId**: una lingua è obbligatoria per la generazione di offerte e ordini cliente in Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="36727-182">**LanguageId** - A language is required in order to generate quotations and sales orders in Finance and Operations.</span></span> <span data-ttu-id="36727-183">Il valore del modello predefinito per **LanguageId** è **en-us**.</span><span class="sxs-lookup"><span data-stu-id="36727-183">The default template value for **LanguageId** is **en-us**.</span></span>

## <a name="template-mapping-in-data-integrator"></a><span data-ttu-id="36727-184">Mapping dei modelli nell'integratore di dati</span><span class="sxs-lookup"><span data-stu-id="36727-184">Template mapping in data integrator</span></span>

<span data-ttu-id="36727-185">Nelle figure seguenti viene illustrato un esempio di un modello di mapping nell'integratore di dati.</span><span class="sxs-lookup"><span data-stu-id="36727-185">The following illustrations show an example of a template mapping in data integrator.</span></span>

### <a name="contact-to-contact"></a><span data-ttu-id="36727-186">Da Contatto a Contatto</span><span class="sxs-lookup"><span data-stu-id="36727-186">Contact to Contact</span></span>

![Mapping dei modelli nell'integratore di dati](./media/contacts-template-mapping-data-integrator-1.png)

![Mapping dei modelli per i Contatti nell'integratore di dati](./media/contacts-template-mapping-data-integrator-2.png)

### <a name="contact-to-customer"></a><span data-ttu-id="36727-189">Da Contatto a Cliente</span><span class="sxs-lookup"><span data-stu-id="36727-189">Contact to Customer</span></span>

![Mapping dei modelli nell'integratore di dati](./media/contacts-template-mapping-data-integrator-3.png)

![Mapping dei modelli per i Contatti nell'integratore di dati](./media/contacts-template-mapping-data-integrator-4.png)


## <a name="related-topics"></a><span data-ttu-id="36727-192">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="36727-192">Related topics</span></span>

[<span data-ttu-id="36727-193">Sincronizzare i prodotti da Finance and Operations ai prodotti in Sales</span><span class="sxs-lookup"><span data-stu-id="36727-193">Synchronize products from Finance and Operations to products in Sales</span></span>](products-template-mapping.md)

[<span data-ttu-id="36727-194">Sincronizzare conti da Sales a clienti in Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="36727-194">Synchronize accounts from Sales to customers in Finance and Operations</span></span>](accounts-template-mapping.md)

[<span data-ttu-id="36727-195">Sincronizzare intestazioni e righe di offerte di vendita da Sales in Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="36727-195">Synchronize sales quotation headers and lines from Sales to Finance and Operations</span></span>](sales-quotation-template-mapping.md)

[<span data-ttu-id="36727-196">Sincronizzare intestazioni e righe di ordini di vendita da Finance and Operations in Sales</span><span class="sxs-lookup"><span data-stu-id="36727-196">Synchronize sales order headers and lines from Finance and Operations to Sales</span></span>](sales-order-template-mapping.md)

[<span data-ttu-id="36727-197">Sincronizzare intestazioni e righe di fatture di vendita da Finance and Operations in Sales</span><span class="sxs-lookup"><span data-stu-id="36727-197">Synchronize sales invoice headers and lines from Finance and Operations to Sales</span></span>](sales-invoice-template-mapping.md)

