---
title: Panoramica della doppia scrittura
description: Questo argomento fornisce una panoramica della doppia scrittura. La doppia scrittura è un'infrastruttura che fornisce interazione quasi in tempo reale tra le app Microsoft Dynamics 365 basate su modelli e le app Finance and Operations.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 02/06/2020
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
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: 12c6a39700a260c138fab67ed370f94b3aa04213
ms.sourcegitcommit: a688c864fc609e35072ad8fd2c01d71f6a5ee7b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/20/2020
ms.locfileid: "3075990"
---
# <a name="dual-write-overview"></a><span data-ttu-id="324e9-104">Panoramica della doppia scrittura</span><span class="sxs-lookup"><span data-stu-id="324e9-104">Dual-write overview</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

## <a name="what-is-dual-write"></a><span data-ttu-id="324e9-105">Che cos'è la doppia scrittura?</span><span class="sxs-lookup"><span data-stu-id="324e9-105">What is dual-write?</span></span>

<span data-ttu-id="324e9-106">La doppia scrittura è un'infrastruttura predefinita che fornisce interazione quasi in tempo reale tra le app in Microsoft Dynamics 365 e le app Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="324e9-106">Dual-write is an out-of-box infrastructure that provides near-real-time interaction between model-driven apps in Microsoft Dynamics 365 and Finance and Operations apps.</span></span> <span data-ttu-id="324e9-107">Quando i dati su clienti, prodotti, persone e operazioni scorrono oltre i confini delle applicazioni, tutti i reparti di un'organizzazione sono potenziati.</span><span class="sxs-lookup"><span data-stu-id="324e9-107">When data about customers, products, people, and operations flows beyond application boundaries, all departments in an organization are empowered.</span></span>

<span data-ttu-id="324e9-108">La doppia scrittura fornisce un'integrazione bidirezionale strettamente connessa tra le app Finance and Operations e Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="324e9-108">Dual-write provides tightly coupled, bidirectional integration between Finance and Operations apps and Common Data Service.</span></span> <span data-ttu-id="324e9-109">Qualsiasi modifica dei dati nelle app Finance and Operations causa scritture in Common Data Service e qualsiasi modifica dei dati in in Common Data Service causa scritture nelle app Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="324e9-109">Any data change in Finance and Operations apps causes writes to Common Data Service, and any data change in Common Data Service causes writes to Finance and Operations apps.</span></span> <span data-ttu-id="324e9-110">Questo flusso di dati automatizzato offre un'esperienza utente integrata tra le app.</span><span class="sxs-lookup"><span data-stu-id="324e9-110">This automated data flow provides an integrated user experience across the apps.</span></span>

![Rapporto dei dati tra le app](media/dual-write-overview.jpg)

<span data-ttu-id="324e9-112">La doppia scrittura ha due aspetti: un aspetto *infrastruttura* e un aspetto *applicazione*.</span><span class="sxs-lookup"><span data-stu-id="324e9-112">Dual-write has two aspects: an *infrastructure* aspect and an *application* aspect.</span></span>

### <a name="infrastructure"></a><span data-ttu-id="324e9-113">Infrastruttura</span><span class="sxs-lookup"><span data-stu-id="324e9-113">Infrastructure</span></span>

<span data-ttu-id="324e9-114">L'infrastruttura a doppia scrittura è estensibile e affidabile e include le seguenti funzionalità chiave:</span><span class="sxs-lookup"><span data-stu-id="324e9-114">The dual-write infrastructure is extensible and reliable, and includes the following key features:</span></span>

+ <span data-ttu-id="324e9-115">Flusso di dati sincrono e bidirezionale tra le applicazioni</span><span class="sxs-lookup"><span data-stu-id="324e9-115">Synchronous and bidirectional data flow between applications</span></span>
+ <span data-ttu-id="324e9-116">Sincronizzazione, insieme alle modalità di riproduzione, pausa e ammortamento per supportare il sistema in modalità online e offline/asincrona.</span><span class="sxs-lookup"><span data-stu-id="324e9-116">Synchronization, together with play, pause, and catchup modes to support the system during online and offline/asynchronous modes.</span></span>
+ <span data-ttu-id="324e9-117">Possibilità di sincronizzare i dati iniziali tra le applicazioni</span><span class="sxs-lookup"><span data-stu-id="324e9-117">Ability to sync initial data between the applications</span></span>
+ <span data-ttu-id="324e9-118">Visualizzazione consolidata dei log di attività ed errori per gli amministratori dei dati</span><span class="sxs-lookup"><span data-stu-id="324e9-118">Consolidated view of activity and error logs for data admins</span></span>
+ <span data-ttu-id="324e9-119">Possibilità di configurare allarmi e soglie personalizzate e di iscriversi alle notifiche</span><span class="sxs-lookup"><span data-stu-id="324e9-119">Ability to configure custom alerts and thresholds, and to subscribe to notifications</span></span>
+ <span data-ttu-id="324e9-120">Interfaccia utente intuitiva per filtraggio e trasformazioni</span><span class="sxs-lookup"><span data-stu-id="324e9-120">Intuitive user interface (UI) for filtering and transformations</span></span>
+ <span data-ttu-id="324e9-121">Capacità di impostare e visualizzare le dipendenze e le relazioni tra entità</span><span class="sxs-lookup"><span data-stu-id="324e9-121">Ability to set and view entity dependencies and relationships</span></span>
+ <span data-ttu-id="324e9-122">Estensibilità per entità e mappe standard e personalizzate</span><span class="sxs-lookup"><span data-stu-id="324e9-122">Extensibility for both standard and custom entities and maps</span></span>
+ <span data-ttu-id="324e9-123">Gestione affidabile del ciclo di vita delle applicazioni</span><span class="sxs-lookup"><span data-stu-id="324e9-123">Reliable application lifecycle management</span></span>
+ <span data-ttu-id="324e9-124">Esperienza di installazione predefinita per i nuovi clienti</span><span class="sxs-lookup"><span data-stu-id="324e9-124">Out-of-box setup experience for new customers</span></span>

### <a name="application"></a><span data-ttu-id="324e9-125">Richiesta</span><span class="sxs-lookup"><span data-stu-id="324e9-125">Application</span></span>

<span data-ttu-id="324e9-126">La doppia scrittura crea una mappatura tra i concetti nelle app Finance and Operations e concetti nelle app basate su modelli in Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="324e9-126">Dual-write creates a mapping between concepts in Finance and Operations apps and concepts in model-driven apps in Dynamics 365.</span></span> <span data-ttu-id="324e9-127">Questa integrazione supporta i seguenti scenari:</span><span class="sxs-lookup"><span data-stu-id="324e9-127">This integration supports the following scenarios:</span></span>

+ <span data-ttu-id="324e9-128">Dati master clienti integrati</span><span class="sxs-lookup"><span data-stu-id="324e9-128">Integrated customer master</span></span>
+ <span data-ttu-id="324e9-129">Accesso alle carte fedeltà dei clienti e ai punti premio</span><span class="sxs-lookup"><span data-stu-id="324e9-129">Access to customer loyalty cards and reward points</span></span>
+ <span data-ttu-id="324e9-130">Esperienza di gestione del prodotto unificata</span><span class="sxs-lookup"><span data-stu-id="324e9-130">Unified product mastering experience</span></span>
+ <span data-ttu-id="324e9-131">Consapevolezza della gerarchia organizzativa</span><span class="sxs-lookup"><span data-stu-id="324e9-131">Awareness of organization hierarchy</span></span>
+ <span data-ttu-id="324e9-132">Dati master fornitori integrati</span><span class="sxs-lookup"><span data-stu-id="324e9-132">Integrated vendor master</span></span>
+ <span data-ttu-id="324e9-133">Accesso ai dati finanziari e di riferimento imposte</span><span class="sxs-lookup"><span data-stu-id="324e9-133">Access to finance and tax reference data</span></span>
+ <span data-ttu-id="324e9-134">Esperienza del motore dei prezzi su richiesta</span><span class="sxs-lookup"><span data-stu-id="324e9-134">On-demand price engine experience</span></span>
+ <span data-ttu-id="324e9-135">Esperienza integrata da prospect a contanti</span><span class="sxs-lookup"><span data-stu-id="324e9-135">Integrated prospect-to-cash experience</span></span>
+ <span data-ttu-id="324e9-136">Capacità di servire sia beni interni che beni dei clienti attraverso agenti sul campo</span><span class="sxs-lookup"><span data-stu-id="324e9-136">Ability to serve both in-house assets and customer assets through field agents</span></span>
+ <span data-ttu-id="324e9-137">Esperienza approvvigionamento per pagamento integrata</span><span class="sxs-lookup"><span data-stu-id="324e9-137">Integrated procure-to-pay experience</span></span>
+ <span data-ttu-id="324e9-138">Attività integrate e note per dati e documenti dei clienti</span><span class="sxs-lookup"><span data-stu-id="324e9-138">Integrated activities and notes for customer data and documents</span></span>
+ <span data-ttu-id="324e9-139">Capacità di cercare le scorte disponibili e i dettagli</span><span class="sxs-lookup"><span data-stu-id="324e9-139">Ability to look up on-hand inventory availability and details</span></span>
+ <span data-ttu-id="324e9-140">Esperienza da progetto a contanti</span><span class="sxs-lookup"><span data-stu-id="324e9-140">Project-to-cash experience</span></span>
+ <span data-ttu-id="324e9-141">Capacità di gestire più indirizzi e ruoli attraverso il concetto di parte</span><span class="sxs-lookup"><span data-stu-id="324e9-141">Ability to handle multiple addresses and roles through the party concept</span></span>
+ <span data-ttu-id="324e9-142">Gestione di un'unica origine per gli utenti</span><span class="sxs-lookup"><span data-stu-id="324e9-142">Single source management for users</span></span>
+ <span data-ttu-id="324e9-143">Canali integrati per la vendita al dettaglio e il marketing</span><span class="sxs-lookup"><span data-stu-id="324e9-143">Integrated channels for retailing and marketing</span></span>
+ <span data-ttu-id="324e9-144">Visibilità di promozioni e sconti</span><span class="sxs-lookup"><span data-stu-id="324e9-144">Visibility into promotions and discounts</span></span>
+ <span data-ttu-id="324e9-145">Funzioni di richiesta di assistenza</span><span class="sxs-lookup"><span data-stu-id="324e9-145">Request-for-service functions</span></span>
+ <span data-ttu-id="324e9-146">Operazioni di servizio semplificate</span><span class="sxs-lookup"><span data-stu-id="324e9-146">Streamlined service operations</span></span>

## <a name="top-reasons-to-use-dual-write"></a><span data-ttu-id="324e9-147">Principali motivi per utilizzare la doppia scrittura</span><span class="sxs-lookup"><span data-stu-id="324e9-147">Top reasons to use dual-write</span></span>

<span data-ttu-id="324e9-148">La doppia scrittura fornisce l'integrazione dei dati tra le applicazioni Microsoft Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="324e9-148">Dual-write provides data integration across Microsoft Dynamics 365 applications.</span></span> <span data-ttu-id="324e9-149">Questa solido framework collega gli ambienti e consente a diverse applicazioni aziendali di lavorare insieme.</span><span class="sxs-lookup"><span data-stu-id="324e9-149">This robust framework links environments and enables different business applications to work together.</span></span> <span data-ttu-id="324e9-150">Ecco i motivi principali per cui usare la doppia scrittura:</span><span class="sxs-lookup"><span data-stu-id="324e9-150">Here are the top reasons why you should use dual-write:</span></span>

+ <span data-ttu-id="324e9-151">La doppia scrittura fornisce un'integrazione strettamente collegata, quasi in tempo reale e bidirezionale tra le app Finance and Operations e le app basate su modello in Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="324e9-151">Dual-write provides tightly coupled, near-real-time, and bidirectional integration between Finance and Operations apps and model-driven apps in Dynamics 365.</span></span> <span data-ttu-id="324e9-152">Questa integrazione rende Microsoft Dynamics 365 il punto principale per tutte le soluzioni aziendali.</span><span class="sxs-lookup"><span data-stu-id="324e9-152">This integration makes Microsoft Dynamics 365 the one-stop shop for all your business solutions.</span></span> <span data-ttu-id="324e9-153">I clienti che usano Dynamics 365 Finance e Dynamics 365 Supply Chain Management, ma che utilizzano soluzioni non Microsoft per la gestione delle relazioni con i clienti (CRM), si stanno muovendo verso Dynamics 365 per il supporto della doppia scrittura.</span><span class="sxs-lookup"><span data-stu-id="324e9-153">Customers who use Dynamics 365 Finance and Dynamics 365 Supply Chain Management, but who use non-Microsoft solutions for customer relationship management (CRM), are moving toward Dynamics 365 for its dual-write support.</span></span>
+ <span data-ttu-id="324e9-154">I dati provenienti da clienti, prodotti, operazioni, progetti e Internet of Things (IoT) passano automaticamente a Common Data Service attraverso la doppia scrittura.</span><span class="sxs-lookup"><span data-stu-id="324e9-154">Data from customers, products, operations, projects, and the Internet of Things (IoT) automatically flows to Common Data Service through dual-write.</span></span> <span data-ttu-id="324e9-155">Questa connessione è molto utile per le aziende interessate alle espansioni Microsoft Power Platform.</span><span class="sxs-lookup"><span data-stu-id="324e9-155">This connection is very useful for businesses that are interested in Microsoft Power Platform expansions.</span></span>
+ <span data-ttu-id="324e9-156">L'infrastruttura a doppia scrittura segue il principio senza codice/poco codice.</span><span class="sxs-lookup"><span data-stu-id="324e9-156">The dual-write infrastructure follows the no-code/low-code principle.</span></span> <span data-ttu-id="324e9-157">È necessario un minimo sforzo di progettazione per estendere le mappe da tabella a tabella standard e per includere mappe personalizzate.</span><span class="sxs-lookup"><span data-stu-id="324e9-157">Minimal engineering effort is required to extend the standard table-to-table maps and to include custom maps.</span></span>
+ <span data-ttu-id="324e9-158">La doppia scrittura supporta sia la modalità online che la modalità offline.</span><span class="sxs-lookup"><span data-stu-id="324e9-158">Dual-write supports both online mode and offline mode.</span></span> <span data-ttu-id="324e9-159">Microsoft è l'unica azienda che offre supporto per le modalità online e offline.</span><span class="sxs-lookup"><span data-stu-id="324e9-159">Microsoft is the only company that offers support for online and offline modes.</span></span>

## <a name="what-does-dual-write-mean-for-users-and-architects-of-crm-products"></a><span data-ttu-id="324e9-160">Cosa significa la doppia scrittura per gli utenti e gli architetti dei prodotti CRM?</span><span class="sxs-lookup"><span data-stu-id="324e9-160">What does dual-write mean for users and architects of CRM products?</span></span>

<span data-ttu-id="324e9-161">La doppia scrittura automatizza il flusso di dati tra le app Finance and Operations e Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="324e9-161">Dual-write automates the data flow between Finance and Operations apps and Common Data Service.</span></span> <span data-ttu-id="324e9-162">Nelle versioni future, i concetti nelle app basate su modelli in Dynamics 365 (ad esempio, cliente, contatto, preventivo e ordine) verranno ridimensionati per i clienti di fascia media e medio-alta.</span><span class="sxs-lookup"><span data-stu-id="324e9-162">In future releases, concepts in model-driven apps in Dynamics 365 (for example, customer, contact, quotation, and order) will be scaled to mid-market and upper-mid-market customers.</span></span>

<span data-ttu-id="324e9-163">Nella prima versione, la maggior parte dell'automazione è gestita da soluzioni a doppia scrittura.</span><span class="sxs-lookup"><span data-stu-id="324e9-163">In the first release, most of the automation is handled by dual-write solutions.</span></span> <span data-ttu-id="324e9-164">Nelle versioni future, tali soluzioni diventeranno parte di Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="324e9-164">In future releases, those solutions will become part of Common Data Service.</span></span> <span data-ttu-id="324e9-165">Comprendendo le imminenti modifiche a Common Data Service, è possibile risparmiare sforzi a lungo termine.</span><span class="sxs-lookup"><span data-stu-id="324e9-165">By understanding the upcoming changes to Common Data Service, you can save yourself effort in the long term.</span></span> <span data-ttu-id="324e9-166">Sono illustrate alcune di queste importanti modifiche:</span><span class="sxs-lookup"><span data-stu-id="324e9-166">Here are some of the crucial changes:</span></span>

+ <span data-ttu-id="324e9-167">Common Data Service avrà nuovi concetti, come società e parte.</span><span class="sxs-lookup"><span data-stu-id="324e9-167">Common Data Service will have new concepts, such as company and party.</span></span> <span data-ttu-id="324e9-168">Questi concetti riguardano tutte le app basate su Common Data Service, ad esempio Dynamics 365 Sales, Dynamics 365 Marketing, Dynamics 365 Customer Service e Dynamics 365 Field Service.</span><span class="sxs-lookup"><span data-stu-id="324e9-168">These concepts will affect all apps that are built on Common Data Service, such as Dynamics 365 Sales, Dynamics 365 Marketing, Dynamics 365 Customer Service, and Dynamics 365 Field Service.</span></span>
+ <span data-ttu-id="324e9-169">Le attività e le note sono unificate e ampliate per supportare sia i C1 (utenti del sistema) che i C2 (clienti del sistema).</span><span class="sxs-lookup"><span data-stu-id="324e9-169">Activities and notes are unified and expanded to support both C1s (users of the system) and C2s (customers of the system).</span></span>
+ <span data-ttu-id="324e9-170">Sono illustrate alcune di queste modifiche future di Common Data Service:</span><span class="sxs-lookup"><span data-stu-id="324e9-170">Here are some of the upcoming changes in Common Data Service:</span></span>

    - <span data-ttu-id="324e9-171">Il tipo di dati decimali sostituirà il tipo di dati monetari.</span><span class="sxs-lookup"><span data-stu-id="324e9-171">The decimal data type will replace the money data type.</span></span>
    - <span data-ttu-id="324e9-172">La validità della data supporterà i dati passati, presenti e futuri nello stesso posto.</span><span class="sxs-lookup"><span data-stu-id="324e9-172">Date effectivity will support past, present, and future data in the same place.</span></span>
    - <span data-ttu-id="324e9-173">Ci sarà un maggiore supporto per i tassi di cambio e valuta e l'API **Tasso di cambio** sarà rivisitata.</span><span class="sxs-lookup"><span data-stu-id="324e9-173">There will be more support for currency and exchange rates, and the **Exchange Rate** application programming interface (API) will be revised.</span></span>
    - <span data-ttu-id="324e9-174">Le conversioni di unità saranno supportate.</span><span class="sxs-lookup"><span data-stu-id="324e9-174">Unit conversions will be supported.</span></span>

<span data-ttu-id="324e9-175">Per ulteriori informazioni sulle modifiche imminenti, vedere [Dati in Common Data Service - fase 1 e 2](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/extensibility/extensibility-roadmap).</span><span class="sxs-lookup"><span data-stu-id="324e9-175">For more information about upcoming changes, see [Data in Common Data Service – phase 1 & 2](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/extensibility/extensibility-roadmap).</span></span>
