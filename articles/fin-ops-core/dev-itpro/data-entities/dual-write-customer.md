---
title: Gestione integrata dei dati dei clienti
description: In questo argomento viene descritta l'integrazione dei dati dei clienti tra Finance and Operations e Common Data Service.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 07/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: 09d985e5c6816ec0c718aaf418f4e85fb828f1c6
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/06/2019
ms.locfileid: "2769685"
---
# <a name="integrated-customer-master"></a><span data-ttu-id="5ecf1-103">Gestione integrata dei dati dei clienti</span><span class="sxs-lookup"><span data-stu-id="5ecf1-103">Integrated customer master</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5ecf1-104">Tipicamente i record cliente sono gestiti in più applicazioni.</span><span class="sxs-lookup"><span data-stu-id="5ecf1-104">It's typical for customer records to be mastered in more than one application.</span></span> <span data-ttu-id="5ecf1-105">Ad esempio, l'attività di vendita può usare record cliente commerciali tramite un'applicazione Sales e attività di e-Commerce o vendita al dettaglio possono usare i record cliente tramite un'applicazione Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="5ecf1-105">For example, sales activity can bring in commercial customer records through a Sales application, and e-Commerce or retail sales can bring in customer records through a Finance and Operations application.</span></span> <span data-ttu-id="5ecf1-106">Indipendentemente dall'origine dei record cliente, questi vengono integrati in background tra applicazioni e nonostante le differenze dell'infrastruttura.</span><span class="sxs-lookup"><span data-stu-id="5ecf1-106">Regardless of where the customer record originates, it's integrated behind the scenes across application boundaries and infrastructure differences.</span></span> <span data-ttu-id="5ecf1-107">La gestione integrata dei dati cliente consente di gestire scenari complessi e offre una visione completa del cliente nella suite applicativa di Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="5ecf1-107">Integrated customer mastering helps handle multi-mastering scenarios and provides a comprehensive view of the customer to the Dynamics 365 application suite.</span></span>

## <a name="customer-data-flow"></a><span data-ttu-id="5ecf1-108">Flusso dei dati dei clienti</span><span class="sxs-lookup"><span data-stu-id="5ecf1-108">Customer data flow</span></span>

<span data-ttu-id="5ecf1-109">*Cliente* è un concetto ben definito nelle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="5ecf1-109">*Customer* is a well-defined concept in applications.</span></span> <span data-ttu-id="5ecf1-110">Di conseguenza, l'integrazione dei dati dei clienti implica solo armonizzare il concetto di cliente tra due applicazioni.</span><span class="sxs-lookup"><span data-stu-id="5ecf1-110">Therefore, the integration of customer data just involves harmonizing the customer concept between the two applications.</span></span> <span data-ttu-id="5ecf1-111">L'illustrazione seguente mostra il flusso dei dati dei clienti.</span><span class="sxs-lookup"><span data-stu-id="5ecf1-111">The following illustration shows the customer data flow.</span></span>

![Flusso dei dati dei clienti](media/dual-write-customer-data-flow.png)

<span data-ttu-id="5ecf1-113">I clienti possono essere classificati largamente in due tipi: clienti commerciali/aziendali e consumatori/utenti finali.</span><span class="sxs-lookup"><span data-stu-id="5ecf1-113">Customers can be broadly classified into two types: commercial/organizational customers and consumers/end users.</span></span> <span data-ttu-id="5ecf1-114">Questi due tipi di clienti vengono archiviati e gestiti in modo diverso in Finance and Operations e Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="5ecf1-114">These two types of customers are stored and handled differently in Finance and Operations and Common Data Service.</span></span>

<span data-ttu-id="5ecf1-115">In Finance and Operations, sia i clienti commerciali/aziendali che i consumatori/utenti finali vengono gestiti in un'unica tabella denominata **CustTable** (CustomerCustomerV3Entity) e vengono classificati in base all'attributo **Tipo**.</span><span class="sxs-lookup"><span data-stu-id="5ecf1-115">In Finance and Operations, both commercial/organizational customers and consumers/end users are mastered in a single table that is named **CustTable** (CustomerCustomerV3Entity), and they are classified based on the **Type** attribute.</span></span> <span data-ttu-id="5ecf1-116">Se **Tipo** è impostato su **Organizzazione**, il cliente è cliente commerciale/aziendale e se **Tipo** è impostato su **Persona**, il cliente è un consumatore/utente finale. Le informazioni principali del contatto vengono gestite tramite l'entità SMMContactPersonEntity.</span><span class="sxs-lookup"><span data-stu-id="5ecf1-116">(If **Type** is set to **Organization**, the customer is a commercial/organizational customer, and if **Type** is set to **Person**, the customer is a consumer/end user.) The primary contact person information is handled through the SMMContactPersonEntity entity.</span></span>

<span data-ttu-id="5ecf1-117">In Common Data Service, i clienti commerciali/aziendali sono gestiti nell'entità Conto e vengono identificati come clienti quando l'attributo **RelationshipType** è impostato su **Cliente**.</span><span class="sxs-lookup"><span data-stu-id="5ecf1-117">In Common Data Service, commercial/organizational customers are mastered in the Account entity and are identified as customers when the **RelationshipType** attribute is set to **Customer**.</span></span> <span data-ttu-id="5ecf1-118">Sia i consumatori/utenti finali che il contatto sono rappresentati dall'entità Contatto.</span><span class="sxs-lookup"><span data-stu-id="5ecf1-118">Both consumers/end users and the contact person are represented by the Contact entity.</span></span> <span data-ttu-id="5ecf1-119">Per fornire una netta separazione tra un consumatore/utente finale e un contatto, l'entità **Contatto** include un flag booleano **Di vendita**.</span><span class="sxs-lookup"><span data-stu-id="5ecf1-119">To provide a clear separation between a consumer/end user and a contact person, the **Contact** entity has a Boolean flag that is named **Sellable**.</span></span> <span data-ttu-id="5ecf1-120">Se **Di vendita** è **True**, il contatto è un consumatore/utente finale e offerte e gli ordini possono essere creati per quel contatto.</span><span class="sxs-lookup"><span data-stu-id="5ecf1-120">When **Sellable** is **True**, the contact is a consumer/end user, and quotations and orders can be created for that contact.</span></span> <span data-ttu-id="5ecf1-121">Se **Di vendita** è **False**, il contatto è solo un contatto principale di un cliente.</span><span class="sxs-lookup"><span data-stu-id="5ecf1-121">When **Sellable** is **False**, the contact is just a primary contact person of a customer.</span></span>

<span data-ttu-id="5ecf1-122">Quando un contatto non di vendita partecipa a un processo di ordine o offerta, **Di vendita** è impostato su **True** per contrassegnare il contatto come contatto di vendita.</span><span class="sxs-lookup"><span data-stu-id="5ecf1-122">When a non-sellable contact participates in a quotation or order process, **Sellable** is set to **True** to flag the contact as a sellable contact.</span></span> <span data-ttu-id="5ecf1-123">Un contatto che è diventato un contatto di vendita rimane tale.</span><span class="sxs-lookup"><span data-stu-id="5ecf1-123">A contact that has become a sellable contact remains a sellable contact.</span></span>

## <a name="templates"></a><span data-ttu-id="5ecf1-124">Modelli</span><span class="sxs-lookup"><span data-stu-id="5ecf1-124">Templates</span></span>

<span data-ttu-id="5ecf1-125">I dati dei clienti includono tutte le informazioni sul cliente, ad esempio il gruppo di clienti, indirizzi, informazioni di contatto, il profilo di pagamento, il profilo fattura e lo stato del programma fedeltà.</span><span class="sxs-lookup"><span data-stu-id="5ecf1-125">Customer data includes all information about the customer, such as the customer group, addresses, contact information, payment profile, invoice profile, and loyalty status.</span></span> <span data-ttu-id="5ecf1-126">Una raccolta di mappe di entità funziona in combinazione durante l'interazione con i dati dei clienti, come illustrato nella seguente tabella.</span><span class="sxs-lookup"><span data-stu-id="5ecf1-126">A collection of entity maps works together during customer data interaction, as shown in the following table.</span></span>

<span data-ttu-id="5ecf1-127">App Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="5ecf1-127">Finance and Operations apps</span></span> | <span data-ttu-id="5ecf1-128">Altre app Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="5ecf1-128">Other Dynamics 365 apps</span></span>         | <span data-ttu-id="5ecf1-129">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5ecf1-129">Description</span></span>
----------------------------|---------------------------------|------------
<span data-ttu-id="5ecf1-130">Contatti CDS V2</span><span class="sxs-lookup"><span data-stu-id="5ecf1-130">CDS Contacts V2</span></span>             | <span data-ttu-id="5ecf1-131">contatti</span><span class="sxs-lookup"><span data-stu-id="5ecf1-131">contacts</span></span>                        | <span data-ttu-id="5ecf1-132">Questo modello sincronizza tutte le informazioni di contatto primarie, secondarie e terziarie, sia per i clienti che per i fornitori.</span><span class="sxs-lookup"><span data-stu-id="5ecf1-132">This template synchronizes all primary, secondary, and tertiary contact information, for both customers and vendors.</span></span>
<span data-ttu-id="5ecf1-133">Gruppi di clienti</span><span class="sxs-lookup"><span data-stu-id="5ecf1-133">Customer groups</span></span>             | <span data-ttu-id="5ecf1-134">msdyn_customergroups</span><span class="sxs-lookup"><span data-stu-id="5ecf1-134">msdyn_customergroups</span></span>            | <span data-ttu-id="5ecf1-135">Questo modello sincronizza le informazioni del gruppo di clienti.</span><span class="sxs-lookup"><span data-stu-id="5ecf1-135">This template synchronizes customer group information.</span></span>
<span data-ttu-id="5ecf1-136">Metodo di pagamento clienti</span><span class="sxs-lookup"><span data-stu-id="5ecf1-136">Customer payment method</span></span>     | <span data-ttu-id="5ecf1-137">msdyn_customerpaymentmethods</span><span class="sxs-lookup"><span data-stu-id="5ecf1-137">msdyn_customerpaymentmethods</span></span>    | <span data-ttu-id="5ecf1-138">Questo modello sincronizza le informazioni del metodo di pagamento dei clienti.</span><span class="sxs-lookup"><span data-stu-id="5ecf1-138">This template synchronizes customer payment method information.</span></span>
<span data-ttu-id="5ecf1-139">Clienti V3</span><span class="sxs-lookup"><span data-stu-id="5ecf1-139">Customers V3</span></span>                | <span data-ttu-id="5ecf1-140">conti</span><span class="sxs-lookup"><span data-stu-id="5ecf1-140">accounts</span></span>                        | <span data-ttu-id="5ecf1-141">Questo modello sincronizza le informazioni sui dati master i clienti commerciali e aziendali.</span><span class="sxs-lookup"><span data-stu-id="5ecf1-141">This template synchronizes customer master information for commercial and organizational customers.</span></span>
<span data-ttu-id="5ecf1-142">Clienti V3</span><span class="sxs-lookup"><span data-stu-id="5ecf1-142">Customers V3</span></span>                | <span data-ttu-id="5ecf1-143">contatti</span><span class="sxs-lookup"><span data-stu-id="5ecf1-143">contacts</span></span>                        | <span data-ttu-id="5ecf1-144">Questo modello sincronizza i dati master per i clienti e gli utenti finali.</span><span class="sxs-lookup"><span data-stu-id="5ecf1-144">This template synchronizes customer master data for consumers and end users.</span></span>
<span data-ttu-id="5ecf1-145">Carta fedeltà</span><span class="sxs-lookup"><span data-stu-id="5ecf1-145">Loyalty card</span></span>                | <span data-ttu-id="5ecf1-146">msdyn_loyaltycards</span><span class="sxs-lookup"><span data-stu-id="5ecf1-146">msdyn_loyaltycards</span></span>              | <span data-ttu-id="5ecf1-147">Questo modello sincronizza le informazioni della carta fedeltà.</span><span class="sxs-lookup"><span data-stu-id="5ecf1-147">This template synchronizes customer loyalty card information.</span></span>
<span data-ttu-id="5ecf1-148">Affissi nome</span><span class="sxs-lookup"><span data-stu-id="5ecf1-148">Name affixes</span></span>                | <span data-ttu-id="5ecf1-149">msdyn_nameaffixes</span><span class="sxs-lookup"><span data-stu-id="5ecf1-149">msdyn_nameaffixes</span></span>               | <span data-ttu-id="5ecf1-150">Questo modello sincronizza i dati di riferimento degli affissi nome per clienti e fornitori.</span><span class="sxs-lookup"><span data-stu-id="5ecf1-150">This template synchronizes name affixes reference data, for both customers and vendors.</span></span>
<span data-ttu-id="5ecf1-151">Righe giorno di pagamento - CDS V2</span><span class="sxs-lookup"><span data-stu-id="5ecf1-151">Payment day lines CDS V2</span></span>    | <span data-ttu-id="5ecf1-152">msdyn_paymentdaylines</span><span class="sxs-lookup"><span data-stu-id="5ecf1-152">msdyn_paymentdaylines</span></span>           | <span data-ttu-id="5ecf1-153">Questo modello sincronizza i dati di riferimento delle righe giorni di pagamento per clienti e fornitori.</span><span class="sxs-lookup"><span data-stu-id="5ecf1-153">This template synchronizes payment day lines reference data, for both customers and vendors.</span></span>
<span data-ttu-id="5ecf1-154">Giorni di pagamento - CDS</span><span class="sxs-lookup"><span data-stu-id="5ecf1-154">Payment days CDS</span></span>            | <span data-ttu-id="5ecf1-155">msdyn_paymentdays</span><span class="sxs-lookup"><span data-stu-id="5ecf1-155">msdyn_paymentdays</span></span>               | <span data-ttu-id="5ecf1-156">Questo modello sincronizza i dati di riferimento dei giorni di pagamento per clienti e fornitori.</span><span class="sxs-lookup"><span data-stu-id="5ecf1-156">This template synchronizes payment days reference data, for both customers and vendors.</span></span>
<span data-ttu-id="5ecf1-157">Righe scadenzario pagamenti</span><span class="sxs-lookup"><span data-stu-id="5ecf1-157">Payment schedule lines</span></span>      | <span data-ttu-id="5ecf1-158">msdyn_paymentschedulelines</span><span class="sxs-lookup"><span data-stu-id="5ecf1-158">msdyn_paymentschedulelines</span></span>      | <span data-ttu-id="5ecf1-159">Sincronizza i dati di riferimento delle righe scadenzario pagamenti per clienti e fornitori.</span><span class="sxs-lookup"><span data-stu-id="5ecf1-159">Syncs payment schedule lines reference data, for both customers and vendors.</span></span>
<span data-ttu-id="5ecf1-160">Scadenzario pagamenti</span><span class="sxs-lookup"><span data-stu-id="5ecf1-160">Payment schedule</span></span>            | <span data-ttu-id="5ecf1-161">msdyn_paymentschedules</span><span class="sxs-lookup"><span data-stu-id="5ecf1-161">msdyn_paymentschedules</span></span>          | <span data-ttu-id="5ecf1-162">Questo modello sincronizza i dati di riferimento dello scadenzario pagamenti per clienti e fornitori.</span><span class="sxs-lookup"><span data-stu-id="5ecf1-162">This template synchronizes payment schedule reference data, for both customers and vendors.</span></span>
<span data-ttu-id="5ecf1-163">Termini di pagamento</span><span class="sxs-lookup"><span data-stu-id="5ecf1-163">Terms of payment</span></span>            | <span data-ttu-id="5ecf1-164">msdyn_paymentterms</span><span class="sxs-lookup"><span data-stu-id="5ecf1-164">msdyn_paymentterms</span></span>              | <span data-ttu-id="5ecf1-165">Questo modello sincronizza i dati di riferimento dei termini di pagamento per clienti e fornitori.</span><span class="sxs-lookup"><span data-stu-id="5ecf1-165">This template synchronizes payment terms (terms of payment) reference data, for both customers and vendors.</span></span>

[!include [banner](../includes/dual-write-symbols.md)]

[!include [mapping contacts contacts](dual-write/CDSContactsV2-contacts.md)]

[!include [mapping customer group](dual-write/CustCustomerGroup-msdyn-customergroups.md)]

[!include [mapping customer payment method](dual-write/CustomerPaymentMethod-msdyn-customerpaymentmethods.md)]

[!include [mapping customer accounts](dual-write/CustomersV3-accounts.md)]

[!include [mapping customer contacts](dual-write/CustomersV3-contacts.md)]

[!include [mapping loyalty card](dual-write/LoyaltyCard-msdyn-loyaltycards.md)]

[!include [mapping name affixes](dual-write/NameAffixes-msdyn-nameaffixes.md)]

[!include [mapping payment day lines](dual-write/PaymentDayLinesCdsV2-msdyn-paymentdaylines.md)]

[!include [mapping payment days](dual-write/PaymentDaysCds-msdyn-paymentdays.md)]

[!include [mapping payment schedule lines](dual-write/PaymentScheduleLines-msdyn-paymentschedulelines.md)]

[!include [mapping payment schedules](dual-write/PaymentSchedules-msdyn-paymentschedules.md)]

[!include [mapping terms of payment](dual-write/TermsofPayment-msdyn-paymentterms.md)]
