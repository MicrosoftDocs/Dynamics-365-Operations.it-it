---
title: Panoramica della doppia scrittura
description: Questo argomento fornisce una panoramica sulla doppia scrittura che fornisce interazione quasi in tempo reale tra le app Customer Engagement e le app Finance and Operations.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 02/06/2020
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
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: 6cc02b483a2975dd3be28032ea7e90b540945492
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2021
ms.locfileid: "5561280"
---
# <a name="dual-write-overview"></a><span data-ttu-id="a14a6-103">Panoramica della doppia scrittura</span><span class="sxs-lookup"><span data-stu-id="a14a6-103">Dual-write overview</span></span>

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]



## <a name="what-is-dual-write"></a><span data-ttu-id="a14a6-104">Che cos'è la doppia scrittura?</span><span class="sxs-lookup"><span data-stu-id="a14a6-104">What is dual-write?</span></span>

<span data-ttu-id="a14a6-105">La doppia scrittura è un'infrastruttura predefinita che fornisce interazione quasi in tempo reale tra le app Customer Engagement e le app Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="a14a6-105">Dual-write is an out-of-box infrastructure that provides near-real-time interaction between customer engagement apps and Finance and Operations apps.</span></span> <span data-ttu-id="a14a6-106">Quando i dati su clienti, prodotti, persone e operazioni scorrono oltre i confini delle applicazioni, tutti i reparti di un'organizzazione sono potenziati.</span><span class="sxs-lookup"><span data-stu-id="a14a6-106">When data about customers, products, people, and operations flows beyond application boundaries, all departments in an organization are empowered.</span></span>

<span data-ttu-id="a14a6-107">La doppia scrittura fornisce un'integrazione bidirezionale strettamente connessa tra le app Finance and Operations e Dataverse.</span><span class="sxs-lookup"><span data-stu-id="a14a6-107">Dual-write provides tightly coupled, bidirectional integration between Finance and Operations apps and Dataverse.</span></span> <span data-ttu-id="a14a6-108">Qualsiasi modifica dei dati nelle app Finance and Operations causa scritture in Dataverse e qualsiasi modifica dei dati in in Dataverse causa scritture nelle app Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="a14a6-108">Any data change in Finance and Operations apps causes writes to Dataverse, and any data change in Dataverse causes writes to Finance and Operations apps.</span></span> <span data-ttu-id="a14a6-109">Questo flusso di dati automatizzato offre un'esperienza utente integrata tra le app.</span><span class="sxs-lookup"><span data-stu-id="a14a6-109">This automated data flow provides an integrated user experience across the apps.</span></span>

![Rapporto dei dati tra le app](media/dual-write-overview.jpg)

<span data-ttu-id="a14a6-111">La doppia scrittura ha due aspetti: un aspetto *infrastruttura* e un aspetto *applicazione*.</span><span class="sxs-lookup"><span data-stu-id="a14a6-111">Dual-write has two aspects: an *infrastructure* aspect and an *application* aspect.</span></span>

### <a name="infrastructure"></a><span data-ttu-id="a14a6-112">Infrastruttura</span><span class="sxs-lookup"><span data-stu-id="a14a6-112">Infrastructure</span></span>

<span data-ttu-id="a14a6-113">L'infrastruttura a doppia scrittura è estensibile e affidabile e include le seguenti funzionalità chiave:</span><span class="sxs-lookup"><span data-stu-id="a14a6-113">The dual-write infrastructure is extensible and reliable, and includes the following key features:</span></span>

+ <span data-ttu-id="a14a6-114">Flusso di dati sincrono e bidirezionale tra le applicazioni</span><span class="sxs-lookup"><span data-stu-id="a14a6-114">Synchronous and bidirectional data flow between applications</span></span>
+ <span data-ttu-id="a14a6-115">Sincronizzazione, insieme alle modalità di riproduzione, pausa e ammortamento per supportare il sistema in modalità online e offline/asincrona.</span><span class="sxs-lookup"><span data-stu-id="a14a6-115">Synchronization, together with play, pause, and catchup modes to support the system during online and offline/asynchronous modes.</span></span>
+ <span data-ttu-id="a14a6-116">Possibilità di sincronizzare i dati iniziali tra le applicazioni</span><span class="sxs-lookup"><span data-stu-id="a14a6-116">Ability to sync initial data between the applications</span></span>
+ <span data-ttu-id="a14a6-117">Visualizzazione combinata dei log di attività ed errori per gli amministratori dei dati</span><span class="sxs-lookup"><span data-stu-id="a14a6-117">Combined view of activity and error logs for data admins</span></span>
+ <span data-ttu-id="a14a6-118">Possibilità di configurare allarmi e soglie personalizzate e di iscriversi alle notifiche</span><span class="sxs-lookup"><span data-stu-id="a14a6-118">Ability to configure custom alerts and thresholds, and to subscribe to notifications</span></span>
+ <span data-ttu-id="a14a6-119">Interfaccia utente intuitiva per filtraggio e trasformazioni</span><span class="sxs-lookup"><span data-stu-id="a14a6-119">Intuitive user interface (UI) for filtering and transformations</span></span>
+ <span data-ttu-id="a14a6-120">Capacità di impostare e visualizzare le dipendenze e le relazioni tra tabelle</span><span class="sxs-lookup"><span data-stu-id="a14a6-120">Ability to set and view table dependencies and relationships</span></span>
+ <span data-ttu-id="a14a6-121">Estensibilità per tabelle e mappe standard e personalizzate</span><span class="sxs-lookup"><span data-stu-id="a14a6-121">Extensibility for both standard and custom tables and maps</span></span>
+ <span data-ttu-id="a14a6-122">Gestione affidabile del ciclo di vita delle applicazioni</span><span class="sxs-lookup"><span data-stu-id="a14a6-122">Reliable application lifecycle management</span></span>
+ <span data-ttu-id="a14a6-123">Esperienza di installazione predefinita per i nuovi clienti</span><span class="sxs-lookup"><span data-stu-id="a14a6-123">Out-of-box setup experience for new customers</span></span>

### <a name="application"></a><span data-ttu-id="a14a6-124">Richiesta</span><span class="sxs-lookup"><span data-stu-id="a14a6-124">Application</span></span>

<span data-ttu-id="a14a6-125">La doppia scrittura crea una mappatura tra i concetti nelle app Finance and Operations e concetti nelle app in Customer Engagement.</span><span class="sxs-lookup"><span data-stu-id="a14a6-125">Dual-write creates a mapping between concepts in Finance and Operations apps and concepts in customer engagement apps.</span></span> <span data-ttu-id="a14a6-126">Questa integrazione supporta i seguenti scenari:</span><span class="sxs-lookup"><span data-stu-id="a14a6-126">This integration supports the following scenarios:</span></span>

+ <span data-ttu-id="a14a6-127">Dati master clienti integrati</span><span class="sxs-lookup"><span data-stu-id="a14a6-127">Integrated customer master</span></span>
+ <span data-ttu-id="a14a6-128">Accesso alle carte fedeltà dei clienti e ai punti premio</span><span class="sxs-lookup"><span data-stu-id="a14a6-128">Access to customer loyalty cards and reward points</span></span>
+ <span data-ttu-id="a14a6-129">Esperienza di gestione del prodotto unificata</span><span class="sxs-lookup"><span data-stu-id="a14a6-129">Unified product mastering experience</span></span>
+ <span data-ttu-id="a14a6-130">Consapevolezza della gerarchia organizzativa</span><span class="sxs-lookup"><span data-stu-id="a14a6-130">Awareness of organization hierarchy</span></span>
+ <span data-ttu-id="a14a6-131">Dati master fornitori integrati</span><span class="sxs-lookup"><span data-stu-id="a14a6-131">Integrated vendor master</span></span>
+ <span data-ttu-id="a14a6-132">Accesso ai dati finanziari e di riferimento imposte</span><span class="sxs-lookup"><span data-stu-id="a14a6-132">Access to finance and tax reference data</span></span>
+ <span data-ttu-id="a14a6-133">Esperienza del motore dei prezzi su richiesta</span><span class="sxs-lookup"><span data-stu-id="a14a6-133">On-demand price engine experience</span></span>
+ <span data-ttu-id="a14a6-134">Esperienza integrata da prospect a contanti</span><span class="sxs-lookup"><span data-stu-id="a14a6-134">Integrated prospect-to-cash experience</span></span>
+ <span data-ttu-id="a14a6-135">Capacità di servire sia beni interni che beni dei clienti attraverso agenti sul campo</span><span class="sxs-lookup"><span data-stu-id="a14a6-135">Ability to serve both in-house assets and customer assets through field agents</span></span>
+ <span data-ttu-id="a14a6-136">Esperienza approvvigionamento per pagamento integrata</span><span class="sxs-lookup"><span data-stu-id="a14a6-136">Integrated procure-to-pay experience</span></span>
+ <span data-ttu-id="a14a6-137">Attività integrate e note per dati e documenti dei clienti</span><span class="sxs-lookup"><span data-stu-id="a14a6-137">Integrated activities and notes for customer data and documents</span></span>
+ <span data-ttu-id="a14a6-138">Capacità di cercare le scorte disponibili e i dettagli</span><span class="sxs-lookup"><span data-stu-id="a14a6-138">Ability to look up on-hand inventory availability and details</span></span>
+ <span data-ttu-id="a14a6-139">Esperienza da progetto a contanti</span><span class="sxs-lookup"><span data-stu-id="a14a6-139">Project-to-cash experience</span></span>
+ <span data-ttu-id="a14a6-140">Capacità di gestire più indirizzi e ruoli attraverso il concetto di parte</span><span class="sxs-lookup"><span data-stu-id="a14a6-140">Ability to handle multiple addresses and roles through the party concept</span></span>
+ <span data-ttu-id="a14a6-141">Gestione di un'unica origine per gli utenti</span><span class="sxs-lookup"><span data-stu-id="a14a6-141">Single source management for users</span></span>
+ <span data-ttu-id="a14a6-142">Canali integrati per la vendita al dettaglio e il marketing</span><span class="sxs-lookup"><span data-stu-id="a14a6-142">Integrated channels for retailing and marketing</span></span>
+ <span data-ttu-id="a14a6-143">Visibilità di promozioni e sconti</span><span class="sxs-lookup"><span data-stu-id="a14a6-143">Visibility into promotions and discounts</span></span>
+ <span data-ttu-id="a14a6-144">Funzioni di richiesta di assistenza</span><span class="sxs-lookup"><span data-stu-id="a14a6-144">Request-for-service functions</span></span>
+ <span data-ttu-id="a14a6-145">Operazioni di servizio semplificate</span><span class="sxs-lookup"><span data-stu-id="a14a6-145">Streamlined service operations</span></span>

## <a name="top-reasons-to-use-dual-write"></a><span data-ttu-id="a14a6-146">Principali motivi per utilizzare la doppia scrittura</span><span class="sxs-lookup"><span data-stu-id="a14a6-146">Top reasons to use dual-write</span></span>

<span data-ttu-id="a14a6-147">La doppia scrittura fornisce l'integrazione dei dati tra le applicazioni Microsoft Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="a14a6-147">Dual-write provides data integration across Microsoft Dynamics 365 applications.</span></span> <span data-ttu-id="a14a6-148">Questa solido framework collega gli ambienti e consente a diverse applicazioni aziendali di lavorare insieme.</span><span class="sxs-lookup"><span data-stu-id="a14a6-148">This robust framework links environments and enables different business applications to work together.</span></span> <span data-ttu-id="a14a6-149">Ecco i motivi principali per cui usare la doppia scrittura:</span><span class="sxs-lookup"><span data-stu-id="a14a6-149">Here are the top reasons why you should use dual-write:</span></span>

+ <span data-ttu-id="a14a6-150">La doppia scrittura fornisce un'integrazione strettamente collegata, quasi in tempo reale e bidirezionale tra le app Finance and Operations e le app basate su modello in Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="a14a6-150">Dual-write provides tightly coupled, near-real-time, and bidirectional integration between Finance and Operations apps and model-driven apps in Dynamics 365.</span></span> <span data-ttu-id="a14a6-151">Questa integrazione rende Microsoft Dynamics 365 il punto principale per tutte le soluzioni aziendali.</span><span class="sxs-lookup"><span data-stu-id="a14a6-151">This integration makes Microsoft Dynamics 365 the one-stop shop for all your business solutions.</span></span> <span data-ttu-id="a14a6-152">I clienti che usano Dynamics 365 Finance e Dynamics 365 Supply Chain Management, ma che utilizzano soluzioni non Microsoft per la gestione delle relazioni con i clienti (CRM), si stanno muovendo verso Dynamics 365 per il supporto della doppia scrittura.</span><span class="sxs-lookup"><span data-stu-id="a14a6-152">Customers who use Dynamics 365 Finance and Dynamics 365 Supply Chain Management, but who use non-Microsoft solutions for customer relationship management (CRM), are moving toward Dynamics 365 for its dual-write support.</span></span>
+ <span data-ttu-id="a14a6-153">I dati provenienti da clienti, prodotti, operazioni, progetti e Internet of Things (IoT) passano automaticamente a Dataverse attraverso la doppia scrittura.</span><span class="sxs-lookup"><span data-stu-id="a14a6-153">Data from customers, products, operations, projects, and the Internet of Things (IoT) automatically flows to Dataverse through dual-write.</span></span> <span data-ttu-id="a14a6-154">Questa connessione è utile per le aziende interessate alle espansioni Power Platform.</span><span class="sxs-lookup"><span data-stu-id="a14a6-154">This connection is useful for businesses that are interested in Power Platform expansions.</span></span>
+ <span data-ttu-id="a14a6-155">L'infrastruttura a doppia scrittura segue il principio senza codice/poco codice.</span><span class="sxs-lookup"><span data-stu-id="a14a6-155">The dual-write infrastructure follows the no-code/low-code principle.</span></span> <span data-ttu-id="a14a6-156">È necessario un minimo sforzo di progettazione per estendere le mappe da tabella a tabella standard e per includere mappe personalizzate.</span><span class="sxs-lookup"><span data-stu-id="a14a6-156">Minimal engineering effort is required to extend the standard table-to-table maps and to include custom maps.</span></span>
+ <span data-ttu-id="a14a6-157">La doppia scrittura supporta sia la modalità online che la modalità offline.</span><span class="sxs-lookup"><span data-stu-id="a14a6-157">Dual-write supports both online mode and offline mode.</span></span> <span data-ttu-id="a14a6-158">Microsoft è l'unica azienda che offre supporto per le modalità online e offline.</span><span class="sxs-lookup"><span data-stu-id="a14a6-158">Microsoft is the only company that offers support for online and offline modes.</span></span>

## <a name="what-does-dual-write-mean-for-developers-and-architects-of-customer-engagement-apps"></a><a id="developer-architect"></a><span data-ttu-id="a14a6-159">Cosa significa la doppia scrittura per sviluppatori e architetti di app Customer Engagement?</span><span class="sxs-lookup"><span data-stu-id="a14a6-159">What does dual-write mean for developers and architects of customer engagement apps?</span></span>

<span data-ttu-id="a14a6-160">La doppia scrittura automatizza il flusso di dati tra le app Finance and Operations e Customer Engagement.</span><span class="sxs-lookup"><span data-stu-id="a14a6-160">Dual-write automates the data flow between Finance and Operations apps and customer engagement apps.</span></span> <span data-ttu-id="a14a6-161">La doppia scrittura è composta da due soluzioni AppSource installate su Dataverse.</span><span class="sxs-lookup"><span data-stu-id="a14a6-161">Dual-write consists of two AppSource solutions that are installed on Dataverse.</span></span> <span data-ttu-id="a14a6-162">Le soluzioni espandono lo schema delle tabelle, i plug-in e i flussi di lavoro in Dataverse in modo che possano scalare alla dimensione ERP.</span><span class="sxs-lookup"><span data-stu-id="a14a6-162">The solutions expand the table schema, plugins, and workflows on Dataverse so that they can scale to ERP size.</span></span> <span data-ttu-id="a14a6-163">Per un'implementazione corretta, gli sviluppatori e gli architetti delle app Customer Engagement devono comprendere questi cambiamenti e collaborare con le loro controparti delle app Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="a14a6-163">For a successful implementation, developers and architects of customer engagement apps must understand these changes and collaborate with their counterparts on Finance and Operations apps.</span></span>

<span data-ttu-id="a14a6-164">Per creare parità con le applicazioni Finance and Operations, la doppia scrittura apporta alcune modifiche cruciali nello schema Dataverse.</span><span class="sxs-lookup"><span data-stu-id="a14a6-164">To create parity with Finance and Operations applications, dual-write makes some crucial changes in the Dataverse schema.</span></span> <span data-ttu-id="a14a6-165">Se si comprende il piano, è possibile evitare alcune modifiche di progettazione e sviluppo in futuro.</span><span class="sxs-lookup"><span data-stu-id="a14a6-165">If you understand the plan, you can avoid some design and development rework in the future.</span></span>

+ <span data-ttu-id="a14a6-166">Quando il il pacchetto AppSource di doppia scrittura è installato, Dataverse avrà nuovi concetti come società e parte.</span><span class="sxs-lookup"><span data-stu-id="a14a6-166">When the dual-write AppSource package is installed, Dataverse will have new concepts such as company and party.</span></span> <span data-ttu-id="a14a6-167">Questi concetti aiutano le applicazioni basate su Dataverse, inclusi Dynamics 365 Sales, Dynamics 365 Marketing, Dynamics 365 Customer Service e Dynamics 365 Field Service, a interagire perfettamente con le app Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="a14a6-167">These concepts help applications built on Dataverse, including Dynamics 365 Sales, Dynamics 365 Marketing, Dynamics 365 Customer Service, and Dynamics 365 Field Service, to interact seamlessly with Finance and Operations apps.</span></span>

+ <span data-ttu-id="a14a6-168">Le attività e le note sono unificate e ampliate per supportare sia i C1 (utenti del sistema) che i C2 (clienti del sistema).</span><span class="sxs-lookup"><span data-stu-id="a14a6-168">Activities and notes are unified and expanded to support both C1s (users of the system) and C2s (customers of the system).</span></span>

+ <span data-ttu-id="a14a6-169">Per evitare la perdita di dati durante la trasmissione di valuta tra le app Finance and Operations e Dataverse, è possibile estendere il numero di cifre decimali nel tipo di dati di valuta delle app Customer Engagement.</span><span class="sxs-lookup"><span data-stu-id="a14a6-169">To prevent data loss during currency transmission between Finance and Operations apps and the Dataverse, you'll be able to extend the number of decimal places in the currency data type of customers engagement apps.</span></span> <span data-ttu-id="a14a6-170">La funzione converte automaticamente le righe esistenti nel nuovo stato esteso a livello dei metadati.</span><span class="sxs-lookup"><span data-stu-id="a14a6-170">The feature autotranslates existing rows to the new extended state at the metadata layer.</span></span> <span data-ttu-id="a14a6-171">Durante questo processo, il valore della valuta viene convertito in dati decimali anziché in dati monetari e il valore della valuta supporta 10 cifre decimali.</span><span class="sxs-lookup"><span data-stu-id="a14a6-171">During this process, the currency value is translated to decimal data rather than money data, and the currency value supports 10 decimal places.</span></span> <span data-ttu-id="a14a6-172">Questa funzione richiede il consenso esplicito e le organizzazioni che non richiedono più di 4 cifre decimali di precisione non hanno bisogno di aderire.</span><span class="sxs-lookup"><span data-stu-id="a14a6-172">This feature is opt-in, and organizations that don't need more than 4 decimal places of precision do not need to opt in.</span></span> <span data-ttu-id="a14a6-173">Per ulteriori informazioni, vedere [Migrazione del tipo di dati valuta per la doppia scrittura](currrency-decimal-places.md).</span><span class="sxs-lookup"><span data-stu-id="a14a6-173">For more information, see [Currency data-type migration for dual-write](currrency-decimal-places.md).</span></span>

+ <span data-ttu-id="a14a6-174">[Validità della data](../../dev-tools/date-effectivity.md) sarà aggiunta a Dataverse.</span><span class="sxs-lookup"><span data-stu-id="a14a6-174">[Date effectivity](../../dev-tools/date-effectivity.md) will be added to Dataverse.</span></span> <span data-ttu-id="a14a6-175">Supporterà i dati passati, presenti e futuri nella stessa tabella.</span><span class="sxs-lookup"><span data-stu-id="a14a6-175">It will support past, present, and future data on the same table.</span></span>

+ <span data-ttu-id="a14a6-176">Le [conversioni di unità](../../../../supply-chain/pim/tasks/manage-unit-measure.md) del prodotto sono supportate per prodotti, offerte, ordini e fatture.</span><span class="sxs-lookup"><span data-stu-id="a14a6-176">Product [unit conversions](../../../../supply-chain/pim/tasks/manage-unit-measure.md) are supported for products, quotes, orders, and invoices.</span></span>

<span data-ttu-id="a14a6-177">Per ulteriori informazioni sulle modifiche imminenti, vedere [Novità o modifiche della doppia scrittura](whats-new-dual-write.md).</span><span class="sxs-lookup"><span data-stu-id="a14a6-177">For more information about upcoming changes, see [What's new or changed in dual-write](whats-new-dual-write.md).</span></span>



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]