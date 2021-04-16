---
title: Gestione integrata dei dati dei clienti
description: In questo argomento viene descritta l'integrazione dei dati dei clienti tra Finance and Operations e Dataverse.
author: RamaKrishnamoorthy
ms.date: 07/15/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: 0015ca2ccbb0098a5a96bf56ff355fb2f9f8f626
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5748925"
---
# <a name="integrated-customer-master"></a><span data-ttu-id="12ebb-103">Dati master clienti integrati</span><span class="sxs-lookup"><span data-stu-id="12ebb-103">Integrated customer master</span></span>

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]


<span data-ttu-id="12ebb-104">I dati dei clienti possono essere masterizzati in più di un'applicazione Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="12ebb-104">Customer data can be mastered in more than one Dynamics 365 application.</span></span> <span data-ttu-id="12ebb-105">Ad esempio, una riga del cliente può avere origine dall'attività di vendita in Dynamics 365 Sales (un'app basata su modello in Dynamics 365) o una riga può avere origine dall'attività di vendita al dettaglio in Dynamics 365 Commerce (un'app Finance and Operations).</span><span class="sxs-lookup"><span data-stu-id="12ebb-105">For example, a customer row can originate though sales activity in Dynamics 365 Sales (a model-driven app in Dynamics 365), or a row can originate through retail activity in Dynamics 365 Commerce (a Finance and Operations app).</span></span> <span data-ttu-id="12ebb-106">Indipendentemente da dove provengano i dati dei clienti, questi vengono integrati in background.</span><span class="sxs-lookup"><span data-stu-id="12ebb-106">No matter where where the customer data originates, it is integrated behind the scenes.</span></span> <span data-ttu-id="12ebb-107">Dati master clienti integrati ti offre la flessibilità di gestire i dati dei clienti in qualsiasi applicazione Dynamics 365 e offre una visione completa del cliente con la suite di applicazioni Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="12ebb-107">Integrated customer master gives you the flexibility to master customer data in any Dynamics 365 application and provides a comprehensive view of the customer across the Dynamics 365 application suite.</span></span>

## <a name="customer-data-flow"></a><span data-ttu-id="12ebb-108">Flusso dei dati dei clienti</span><span class="sxs-lookup"><span data-stu-id="12ebb-108">Customer data flow</span></span>

<span data-ttu-id="12ebb-109">*Cliente* è un concetto ben definito nelle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="12ebb-109">*Customer* is a well-defined concept in applications.</span></span> <span data-ttu-id="12ebb-110">Di conseguenza, l'integrazione dei dati dei clienti implica solo armonizzare il concetto di cliente tra due applicazioni.</span><span class="sxs-lookup"><span data-stu-id="12ebb-110">Therefore, the integration of customer data just involves harmonizing the customer concept between the two applications.</span></span> <span data-ttu-id="12ebb-111">L'illustrazione seguente mostra il flusso dei dati dei clienti.</span><span class="sxs-lookup"><span data-stu-id="12ebb-111">The following illustration shows the customer data flow.</span></span>

![Flusso dei dati dei clienti](media/dual-write-customer-data-flow.png)

<span data-ttu-id="12ebb-113">I clienti possono essere classificati largamente in due tipi: clienti commerciali/aziendali e consumatori/utenti finali.</span><span class="sxs-lookup"><span data-stu-id="12ebb-113">Customers can be broadly classified into two types: commercial/organizational customers and consumers/end users.</span></span> <span data-ttu-id="12ebb-114">Questi due tipi di clienti vengono archiviati e gestiti in modo diverso in Finance and Operations e Dataverse.</span><span class="sxs-lookup"><span data-stu-id="12ebb-114">These two types of customers are stored and handled differently in Finance and Operations and Dataverse.</span></span>

<span data-ttu-id="12ebb-115">In Finance and Operations, sia i clienti commerciali/aziendali che i consumatori/utenti finali vengono gestiti in un'unica tabella denominata **CustTable** (CustCustomerV3Entity) e vengono classificati in base all'attributo **Tipo**.</span><span class="sxs-lookup"><span data-stu-id="12ebb-115">In Finance and Operations, both commercial/organizational customers and consumers/end users are mastered in a single table that is named **CustTable** (CustCustomerV3Entity), and they are classified based on the **Type** attribute.</span></span> <span data-ttu-id="12ebb-116">Se **Tipo** è impostato su **Organizzazione**, il cliente è cliente commerciale/aziendale e se **Tipo** è impostato su **Persona**, il cliente è un consumatore/utente finale. Le informazioni principali del contatto vengono gestite tramite la tabella SMMContactPersonEntity.</span><span class="sxs-lookup"><span data-stu-id="12ebb-116">(If **Type** is set to **Organization**, the customer is a commercial/organizational customer, and if **Type** is set to **Person**, the customer is a consumer/end user.) The primary contact person information is handled through the SMMContactPersonEntity table.</span></span>

<span data-ttu-id="12ebb-117">In Dataverse, i clienti commerciali/aziendali sono gestiti nella tabella Conto e vengono identificati come clienti quando l'attributo **RelationshipType** è impostato su **Cliente**.</span><span class="sxs-lookup"><span data-stu-id="12ebb-117">In Dataverse, commercial/organizational customers are mastered in the Account table and are identified as customers when the **RelationshipType** attribute is set to **Customer**.</span></span> <span data-ttu-id="12ebb-118">Sia i consumatori/utenti finali che il contatto sono rappresentati dalla tabella Contatto.</span><span class="sxs-lookup"><span data-stu-id="12ebb-118">Both consumers/end users and the contact person are represented by the Contact table.</span></span> <span data-ttu-id="12ebb-119">Per fornire una netta separazione tra un consumatore/utente finale e un contatto, la tabella **Contatto** include un flag booleano **Di vendita**.</span><span class="sxs-lookup"><span data-stu-id="12ebb-119">To provide a clear separation between a consumer/end user and a contact person, the **Contact** table has a Boolean flag that is named **Sellable**.</span></span> <span data-ttu-id="12ebb-120">Se **Di vendita** è **True**, il contatto è un consumatore/utente finale e offerte e gli ordini possono essere creati per quel contatto.</span><span class="sxs-lookup"><span data-stu-id="12ebb-120">When **Sellable** is **True**, the contact is a consumer/end user, and quotations and orders can be created for that contact.</span></span> <span data-ttu-id="12ebb-121">Se **Di vendita** è **False**, il contatto è solo un contatto principale di un cliente.</span><span class="sxs-lookup"><span data-stu-id="12ebb-121">When **Sellable** is **False**, the contact is just a primary contact person of a customer.</span></span>

<span data-ttu-id="12ebb-122">Quando un contatto non di vendita partecipa a un processo di ordine o offerta, **Di vendita** è impostato su **True** per contrassegnare il contatto come contatto di vendita.</span><span class="sxs-lookup"><span data-stu-id="12ebb-122">When a non-sellable contact participates in a quotation or order process, **Sellable** is set to **True** to flag the contact as a sellable contact.</span></span> <span data-ttu-id="12ebb-123">Un contatto che è diventato un contatto di vendita rimane tale.</span><span class="sxs-lookup"><span data-stu-id="12ebb-123">A contact that has become a sellable contact remains a sellable contact.</span></span>

## <a name="templates"></a><span data-ttu-id="12ebb-124">Modelli</span><span class="sxs-lookup"><span data-stu-id="12ebb-124">Templates</span></span>

<span data-ttu-id="12ebb-125">I dati dei clienti includono tutte le informazioni sul cliente, ad esempio il gruppo di clienti, indirizzi, informazioni di contatto, il profilo di pagamento, il profilo fattura e lo stato del programma fedeltà.</span><span class="sxs-lookup"><span data-stu-id="12ebb-125">Customer data includes all information about the customer, such as the customer group, addresses, contact information, payment profile, invoice profile, and loyalty status.</span></span> <span data-ttu-id="12ebb-126">Una raccolta di mappe della tabella funziona in combinazione durante l'interazione con i dati dei clienti, come illustrato nella seguente tabella.</span><span class="sxs-lookup"><span data-stu-id="12ebb-126">A collection of table maps works together during customer data interaction, as shown in the following table.</span></span>

<span data-ttu-id="12ebb-127">App di Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="12ebb-127">Finance and Operations apps</span></span> | <span data-ttu-id="12ebb-128">Altre app Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="12ebb-128">Other Dynamics 365 apps</span></span>         | <span data-ttu-id="12ebb-129">Descrizione</span><span class="sxs-lookup"><span data-stu-id="12ebb-129">Description</span></span>
----------------------------|---------------------------------|------------
<span data-ttu-id="12ebb-130">Contatti CDS V2</span><span class="sxs-lookup"><span data-stu-id="12ebb-130">CDS Contacts V2</span></span>             | <span data-ttu-id="12ebb-131">contatti</span><span class="sxs-lookup"><span data-stu-id="12ebb-131">contacts</span></span>                        | <span data-ttu-id="12ebb-132">Questo modello sincronizza tutte le informazioni di contatto primarie, secondarie e terziarie, sia per i clienti che per i fornitori.</span><span class="sxs-lookup"><span data-stu-id="12ebb-132">This template synchronizes all primary, secondary, and tertiary contact information, for both customers and vendors.</span></span>
<span data-ttu-id="12ebb-133">Gruppi di clienti</span><span class="sxs-lookup"><span data-stu-id="12ebb-133">Customer groups</span></span>             | <span data-ttu-id="12ebb-134">msdyn_customergroups</span><span class="sxs-lookup"><span data-stu-id="12ebb-134">msdyn_customergroups</span></span>            | <span data-ttu-id="12ebb-135">Questo modello sincronizza le informazioni del gruppo di clienti.</span><span class="sxs-lookup"><span data-stu-id="12ebb-135">This template synchronizes customer group information.</span></span>
<span data-ttu-id="12ebb-136">Metodo di pagamento clienti</span><span class="sxs-lookup"><span data-stu-id="12ebb-136">Customer payment method</span></span>     | <span data-ttu-id="12ebb-137">msdyn_customerpaymentmethods</span><span class="sxs-lookup"><span data-stu-id="12ebb-137">msdyn_customerpaymentmethods</span></span>    | <span data-ttu-id="12ebb-138">Questo modello sincronizza le informazioni del metodo di pagamento dei clienti.</span><span class="sxs-lookup"><span data-stu-id="12ebb-138">This template synchronizes customer payment method information.</span></span>
<span data-ttu-id="12ebb-139">Clienti V3</span><span class="sxs-lookup"><span data-stu-id="12ebb-139">Customers V3</span></span>                | <span data-ttu-id="12ebb-140">conti</span><span class="sxs-lookup"><span data-stu-id="12ebb-140">accounts</span></span>                        | <span data-ttu-id="12ebb-141">Questo modello sincronizza le informazioni sui dati master i clienti commerciali e aziendali.</span><span class="sxs-lookup"><span data-stu-id="12ebb-141">This template synchronizes customer master information for commercial and organizational customers.</span></span>
<span data-ttu-id="12ebb-142">Clienti V3</span><span class="sxs-lookup"><span data-stu-id="12ebb-142">Customers V3</span></span>                | <span data-ttu-id="12ebb-143">contatti</span><span class="sxs-lookup"><span data-stu-id="12ebb-143">contacts</span></span>                        | <span data-ttu-id="12ebb-144">Questo modello sincronizza i dati master per i clienti e gli utenti finali.</span><span class="sxs-lookup"><span data-stu-id="12ebb-144">This template synchronizes customer master data for consumers and end users.</span></span>
<span data-ttu-id="12ebb-145">Affissi nome</span><span class="sxs-lookup"><span data-stu-id="12ebb-145">Name affixes</span></span>                | <span data-ttu-id="12ebb-146">msdyn_nameaffixes</span><span class="sxs-lookup"><span data-stu-id="12ebb-146">msdyn_nameaffixes</span></span>               | <span data-ttu-id="12ebb-147">Questo modello sincronizza i dati di riferimento degli affissi nome per clienti e fornitori.</span><span class="sxs-lookup"><span data-stu-id="12ebb-147">This template synchronizes name affixes reference data, for both customers and vendors.</span></span>
<span data-ttu-id="12ebb-148">Righe giorno di pagamento - CDS V2</span><span class="sxs-lookup"><span data-stu-id="12ebb-148">Payment day lines CDS V2</span></span>    | <span data-ttu-id="12ebb-149">msdyn_paymentdaylines</span><span class="sxs-lookup"><span data-stu-id="12ebb-149">msdyn_paymentdaylines</span></span>           | <span data-ttu-id="12ebb-150">Questo modello sincronizza i dati di riferimento delle righe giorni di pagamento per clienti e fornitori.</span><span class="sxs-lookup"><span data-stu-id="12ebb-150">This template synchronizes payment day lines reference data, for both customers and vendors.</span></span>
<span data-ttu-id="12ebb-151">Giorni di pagamento - CDS</span><span class="sxs-lookup"><span data-stu-id="12ebb-151">Payment days CDS</span></span>            | <span data-ttu-id="12ebb-152">msdyn_paymentdays</span><span class="sxs-lookup"><span data-stu-id="12ebb-152">msdyn_paymentdays</span></span>               | <span data-ttu-id="12ebb-153">Questo modello sincronizza i dati di riferimento dei giorni di pagamento per clienti e fornitori.</span><span class="sxs-lookup"><span data-stu-id="12ebb-153">This template synchronizes payment days reference data, for both customers and vendors.</span></span>
<span data-ttu-id="12ebb-154">Righe scadenzario pagamenti</span><span class="sxs-lookup"><span data-stu-id="12ebb-154">Payment schedule lines</span></span>      | <span data-ttu-id="12ebb-155">msdyn_paymentschedulelines</span><span class="sxs-lookup"><span data-stu-id="12ebb-155">msdyn_paymentschedulelines</span></span>      | <span data-ttu-id="12ebb-156">Sincronizza i dati di riferimento delle righe scadenzario pagamenti per clienti e fornitori.</span><span class="sxs-lookup"><span data-stu-id="12ebb-156">Syncs payment schedule lines reference data, for both customers and vendors.</span></span>
<span data-ttu-id="12ebb-157">Scadenzario pagamenti</span><span class="sxs-lookup"><span data-stu-id="12ebb-157">Payment schedule</span></span>            | <span data-ttu-id="12ebb-158">msdyn_paymentschedules</span><span class="sxs-lookup"><span data-stu-id="12ebb-158">msdyn_paymentschedules</span></span>          | <span data-ttu-id="12ebb-159">Questo modello sincronizza i dati di riferimento dello scadenzario pagamenti per clienti e fornitori.</span><span class="sxs-lookup"><span data-stu-id="12ebb-159">This template synchronizes payment schedule reference data, for both customers and vendors.</span></span>
<span data-ttu-id="12ebb-160">Termini di pagamento</span><span class="sxs-lookup"><span data-stu-id="12ebb-160">Terms of payment</span></span>            | <span data-ttu-id="12ebb-161">msdyn_paymentterms</span><span class="sxs-lookup"><span data-stu-id="12ebb-161">msdyn_paymentterms</span></span>              | <span data-ttu-id="12ebb-162">Questo modello sincronizza i dati di riferimento dei termini di pagamento per clienti e fornitori.</span><span class="sxs-lookup"><span data-stu-id="12ebb-162">This template synchronizes payment terms (terms of payment) reference data, for both customers and vendors.</span></span>

[!include [banner](../../includes/dual-write-symbols.md)]

[!include [mapping contacts contacts](includes/CDSContactsV2-contacts.md)]

[!include [mapping customer group](includes/CustCustomerGroup-msdyn-customergroups.md)]

[!include [mapping customer payment method](includes/CustomerPaymentMethod-msdyn-customerpaymentmethods.md)]

[!include [mapping customer accounts](includes/CustomersV3-accounts.md)]

[!include [mapping customer contacts](includes/CustomersV3-contacts.md)]

[!include [mapping name affixes](includes/NameAffixes-msdyn-nameaffixes.md)]

[!include [mapping payment day lines](includes/PaymentDayLinesCdsV2-msdyn-paymentdaylines.md)]

[!include [mapping payment days](includes/PaymentDaysCds-msdyn-paymentdays.md)]

[!include [mapping payment schedule lines](includes/PaymentScheduleLines-msdyn-paymentschedulelines.md)]

[!include [mapping payment schedules](includes/PaymentSchedules-msdyn-paymentschedules.md)]

[!include [mapping terms of payment](includes/TermsofPayment-msdyn-paymentterms.md)]


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]