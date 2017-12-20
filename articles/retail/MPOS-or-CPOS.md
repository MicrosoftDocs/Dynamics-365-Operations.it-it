---
title: Scegliere tra Modern POS e Cloud POS
description: "In questo argomento vengono illustrate le differenze chiave tra Retail Modern POS e Cloud POS. Sono inoltre descritti i diversi fattori che i rivenditori che implementano Microsoft Dynamics 365 for Retail devono considerare per operare la scelta più adatta alle proprie esigenze."
author: jblucher
manager: AnnBe
ms.date: 10/12/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations, Retail
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: Retail
ms.author: 
ms.search.validFrom: 2017-10-12
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 7efda507ad826b7765431e6cbdd78c3c9246bc7c
ms.openlocfilehash: 03b7b4d468e35c7b77cf2a2e52c038c0995c7f53
ms.contentlocale: it-it
ms.lasthandoff: 12/08/2017

---

# <a name="choose-between-modern-pos-and-cloud-pos"></a><span data-ttu-id="bb263-104">Scegliere tra Modern POS e Cloud POS</span><span class="sxs-lookup"><span data-stu-id="bb263-104">Choose between Modern POS and Cloud POS</span></span>

[!include[banner](includes/banner.md)]

<span data-ttu-id="bb263-105">In questo argomento vengono fornite agli implementatori contesto, suggerimenti e indicazioni supplementari per i fattori da considerare durante la distribuzione di Microsoft Dynamics 365 for Retail.</span><span class="sxs-lookup"><span data-stu-id="bb263-105">This topic gives implementers additional background, tips, and guidance for factors that they should consider when they deploy Microsoft Dynamics 365 for Retail.</span></span> <span data-ttu-id="bb263-106">Esaminando e seguendo queste indicazioni durante il processo di distribuzione, gli implementatori possono evitare eventuali problemi che potrebbero influire sulla soddisfazione dell'utente o sulle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="bb263-106">By reviewing and following this guidance as part of the deployment process, implementers can avoid issues that might affect user satisfaction or performance.</span></span>

## <a name="insights"></a><span data-ttu-id="bb263-107">Informazioni approfondite</span><span class="sxs-lookup"><span data-stu-id="bb263-107">Insights</span></span>
<span data-ttu-id="bb263-108">Retail offre un'ampia gamma di opzioni di distribuzione e topologia.</span><span class="sxs-lookup"><span data-stu-id="bb263-108">Retail provides a wide range of deployment and topology options.</span></span> <span data-ttu-id="bb263-109">Di conseguenza, i rivenditori possono scegliere i componenti e la configurazione che meglio si adattano ai propri requisiti aziendali e tecnologici.</span><span class="sxs-lookup"><span data-stu-id="bb263-109">Therefore, retailers can choose the components and configuration that best meet their business and technology requirements.</span></span> <span data-ttu-id="bb263-110">Un aspetto di implementazione che richiede un'attenta considerazione è la scelta della piattaforma e del fattore di forma per il componente POS.</span><span class="sxs-lookup"><span data-stu-id="bb263-110">One aspect of implementation that requires careful consideration is the choice of a platform and form factor for the point of sale (POS) component.</span></span>

### <a name="pos-platform-and-form-factor-considerations"></a><span data-ttu-id="bb263-111">Considerazioni sulla piattaforma e sul fattore di forma per il POS</span><span class="sxs-lookup"><span data-stu-id="bb263-111">POS platform and form factor considerations</span></span>
<span data-ttu-id="bb263-112">Retail supporta le opzioni POS seguenti:</span><span class="sxs-lookup"><span data-stu-id="bb263-112">Retail supports the following POS options:</span></span>

- <span data-ttu-id="bb263-113">Retail Modern POS (MPOS) per Microsoft Windows</span><span class="sxs-lookup"><span data-stu-id="bb263-113">Retail Modern POS (MPOS) for Microsoft Windows</span></span>
- <span data-ttu-id="bb263-114">MPOS per Microsoft Windows Phone</span><span class="sxs-lookup"><span data-stu-id="bb263-114">MPOS for Microsoft Windows Phone</span></span>
- <span data-ttu-id="bb263-115">MPOS per iPad di Apple o tablet Android di Google</span><span class="sxs-lookup"><span data-stu-id="bb263-115">MPOS for Apple iPad or Google Android tablet</span></span>
- <span data-ttu-id="bb263-116">Cloud POS (CPOS), che supporta i browser Microsoft Edge, Internet Explorer e Google Chrome</span><span class="sxs-lookup"><span data-stu-id="bb263-116">Cloud POS (CPOS), which supports the Microsoft Edge, Internet Explorer, and Google Chrome browsers</span></span>

<span data-ttu-id="bb263-117">In tutti i casi, il POS (MPOS e CPOS) condivide lo stesso codice applicazione di base.</span><span class="sxs-lookup"><span data-stu-id="bb263-117">In all cases, the POS (MPOS and CPOS) shares the same core application code.</span></span> <span data-ttu-id="bb263-118">Questo punto è importante per i motivi seguenti:</span><span class="sxs-lookup"><span data-stu-id="bb263-118">This point is important for the following reasons:</span></span>

- <span data-ttu-id="bb263-119">L'interfaccia utente (UI) è coerente, indipendentemente dalla piattaforma o dal fattore di forma.</span><span class="sxs-lookup"><span data-stu-id="bb263-119">The user interface (UI) is consistent, regardless of the platform or form factor.</span></span>
- <span data-ttu-id="bb263-120">La maggior parte delle capacità funzionali è uguale, indipendentemente dalla piattaforma o dal fattore di forma.</span><span class="sxs-lookup"><span data-stu-id="bb263-120">Most of the functional capabilities are the same, regardless of the platform or form factor.</span></span> <span data-ttu-id="bb263-121">Tuttavia, esistono delle differenze importanti.</span><span class="sxs-lookup"><span data-stu-id="bb263-121">However, there are some important differences.</span></span> <span data-ttu-id="bb263-122">Le differenze sono descritte in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="bb263-122">These differences are noted in this topic.</span></span>
- <span data-ttu-id="bb263-123">In un punto vendita specifico, le variazioni POS possono essere combinate e possono essere eseguite simultaneamente.</span><span class="sxs-lookup"><span data-stu-id="bb263-123">In a given store, the POS variations can be combined and can run concurrently.</span></span> <span data-ttu-id="bb263-124">Ad esempio, per i registri principali, un rivenditore può utilizzare MPOS in computer che eseguono Windows.</span><span class="sxs-lookup"><span data-stu-id="bb263-124">For example, for its main registers, a retailer can use MPOS on computers that run Windows.</span></span> <span data-ttu-id="bb263-125">Tuttavia, il rivenditore può completare questi registri con terminali basati su browser o dispositivi mobili.</span><span class="sxs-lookup"><span data-stu-id="bb263-125">However, the retailer can supplement those registers with browser-based terminals or mobile devices.</span></span>
- <span data-ttu-id="bb263-126">Le personalizzazioni e le estensioni possono essere facilmente essere utilizzate su più piattaforme e più fattori di forma.</span><span class="sxs-lookup"><span data-stu-id="bb263-126">Customizations and extensions can easily be used across platforms and form factors.</span></span> <span data-ttu-id="bb263-127">Poiché il codice applicazione di base è condiviso, le personalizzazioni possono essere implementate una volta anziché più volte.</span><span class="sxs-lookup"><span data-stu-id="bb263-127">Because the core application code is shared, most customizations can be implemented one time instead of multiple times.</span></span>

### <a name="mpos-vs-cpos"></a><span data-ttu-id="bb263-128">MPOS rispetto a CPOS</span><span class="sxs-lookup"><span data-stu-id="bb263-128">MPOS vs. CPOS</span></span>
<span data-ttu-id="bb263-129">Sebbene MPOS e CPOS siano in gran parte uguali, esistono delle differenze importanti con cui sarà necessario acquisire familiarità.</span><span class="sxs-lookup"><span data-stu-id="bb263-129">Although MPOS and CPOS are largely the same, there are some important differences that you must understand.</span></span>

#### <a name="mpos"></a><span data-ttu-id="bb263-130">MPOS</span><span class="sxs-lookup"><span data-stu-id="bb263-130">MPOS</span></span>

<span data-ttu-id="bb263-131">MPOS in un dispositivo Windows, iOS o Android è un'applicazione in pacchetto che viene installato e supportato nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="bb263-131">MPOS on a Windows, iOS, or Android device is an application that is packaged, installed, and serviced on that device.</span></span>

- <span data-ttu-id="bb263-132">**Windows** - L'applicazione MPOS per Windows contiene tutto il codice applicazione e il runtime di Commerce (CRT) incorporato.</span><span class="sxs-lookup"><span data-stu-id="bb263-132">**Windows** – The MPOS for Windows application contains all the application code and the embedded commerce runtime (CRT).</span></span> 
- <span data-ttu-id="bb263-133">**iOS/Android** - In queste piattaforme, l'applicazione agisce da host per il codice applicazione CPOS.</span><span class="sxs-lookup"><span data-stu-id="bb263-133">**iOS/Android** – On these platforms, the application acts as a host for the CPOS application code.</span></span> <span data-ttu-id="bb263-134">In altre parole, il codice applicazione deriva dal server CPOS in Microsoft Azure o Retail Store Scale Unit (RSSU).</span><span class="sxs-lookup"><span data-stu-id="bb263-134">In other words, the application code comes from the CPOS server on Microsoft Azure or the Retail Store Scale Unit (RSSU).</span></span> <span data-ttu-id="bb263-135">Per ulteriori informazioni, vedere [Panoramica di Retail Store Scale Unit](https://docs.microsoft.com/en-us/dynamics365/unified-operations/retail/dev-itpro/retail-store-system-begin) (in lingua inglese).</span><span class="sxs-lookup"><span data-stu-id="bb263-135">For more information, see [Retail Store Scale Unit overview](https://docs.microsoft.com/en-us/dynamics365/unified-operations/retail/dev-itpro/retail-store-system-begin).</span></span>

#### <a name="cpos"></a><span data-ttu-id="bb263-136">CPOS</span><span class="sxs-lookup"><span data-stu-id="bb263-136">CPOS</span></span>

<span data-ttu-id="bb263-137">Poiché CPOS viene eseguito in un browser, l'applicazione non viene installata nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="bb263-137">Because CPOS runs in a browser, the application isn't installed on the device.</span></span> <span data-ttu-id="bb263-138">Il browser accede invece al codice applicazione dal server CPOS.</span><span class="sxs-lookup"><span data-stu-id="bb263-138">Instead, the browser accesses the application code from the CPOS server.</span></span> <span data-ttu-id="bb263-139">Di conseguenza, CPOS non può accedere direttamente all'hardware POS o lavorare in uno stato offline.</span><span class="sxs-lookup"><span data-stu-id="bb263-139">Therefore, CPOS can't directly access POS hardware or work in an offline state.</span></span>

### <a name="store-deployment-considerations"></a><span data-ttu-id="bb263-140">Considerazioni sulla distribuzione in punti vendita</span><span class="sxs-lookup"><span data-stu-id="bb263-140">Store deployment considerations</span></span>
<span data-ttu-id="bb263-141">Oltre alla piattaforma e al fattore di forma, i rivenditori devono scegliere anche un'opzione di distribuzione presso il punto vendita.</span><span class="sxs-lookup"><span data-stu-id="bb263-141">In addition to a platform and form factor, retailers must also choose a deployment option at the store.</span></span> <span data-ttu-id="bb263-142">Nella seguente tabella sono descritte le configurazioni disponibili per ogni opzione POS.</span><span class="sxs-lookup"><span data-stu-id="bb263-142">The following table shows the configurations that are available for each POS option.</span></span>

| <span data-ttu-id="bb263-143">Applicazione POS</span><span class="sxs-lookup"><span data-stu-id="bb263-143">POS application</span></span>         | <span data-ttu-id="bb263-144">Server Retail</span><span class="sxs-lookup"><span data-stu-id="bb263-144">Retail server</span></span> | <span data-ttu-id="bb263-145">Disponibile offline</span><span class="sxs-lookup"><span data-stu-id="bb263-145">Available offline</span></span> |
|-------------------------|---------------|-------------------|
| <span data-ttu-id="bb263-146">MPOS per Windows</span><span class="sxs-lookup"><span data-stu-id="bb263-146">MPOS for Windows</span></span>        | <span data-ttu-id="bb263-147">Cloud o RSSU</span><span class="sxs-lookup"><span data-stu-id="bb263-147">Cloud or RSSU</span></span> | <span data-ttu-id="bb263-148">Sì</span><span class="sxs-lookup"><span data-stu-id="bb263-148">Yes</span></span>               |
| <span data-ttu-id="bb263-149">MPOS per iOS o Android</span><span class="sxs-lookup"><span data-stu-id="bb263-149">MPOS for iOS or Android</span></span> | <span data-ttu-id="bb263-150">Cloud o RSSU</span><span class="sxs-lookup"><span data-stu-id="bb263-150">Cloud or RSSU</span></span> | <span data-ttu-id="bb263-151">No</span><span class="sxs-lookup"><span data-stu-id="bb263-151">No</span></span>                |
| <span data-ttu-id="bb263-152">POS cloud</span><span class="sxs-lookup"><span data-stu-id="bb263-152">Cloud POS</span></span>               | <span data-ttu-id="bb263-153">Cloud o RSSU</span><span class="sxs-lookup"><span data-stu-id="bb263-153">Cloud or RSSU</span></span> | <span data-ttu-id="bb263-154">No</span><span class="sxs-lookup"><span data-stu-id="bb263-154">No</span></span>                |

#### <a name="retail-server"></a><span data-ttu-id="bb263-155">Server Retail</span><span class="sxs-lookup"><span data-stu-id="bb263-155">Retail server</span></span>

<span data-ttu-id="bb263-156">Il server Retail è un componente che ospita il CRT.</span><span class="sxs-lookup"><span data-stu-id="bb263-156">The Retail server is a component that hosts the CRT.</span></span> <span data-ttu-id="bb263-157">Il CRT contiene tutta la logica di business utilizzata dal POS e offre accesso al database di canale.</span><span class="sxs-lookup"><span data-stu-id="bb263-157">The CRT contains all the business logic that the POS uses, and it provides access to the channel database.</span></span> <span data-ttu-id="bb263-158">Man mano che si connettono, tutti i client POS nel punto vendita utilizzano il server Retail.</span><span class="sxs-lookup"><span data-stu-id="bb263-158">While they are online, all POS clients in the store use the Retail server.</span></span> <span data-ttu-id="bb263-159">Il server Retail può essere distribuito nel cloud o nel punto vendita (RSSU).</span><span class="sxs-lookup"><span data-stu-id="bb263-159">The Retail server can be deployed either in the cloud or in the store (RSSU).</span></span>

#### <a name="offline-mode"></a><span data-ttu-id="bb263-160">Modalità offline</span><span class="sxs-lookup"><span data-stu-id="bb263-160">Offline mode</span></span>

<span data-ttu-id="bb263-161">MPOS per Windows supporta la modalità offline.</span><span class="sxs-lookup"><span data-stu-id="bb263-161">MPOS for Windows supports offline mode.</span></span> <span data-ttu-id="bb263-162">In questa modalità, il POS può continuare a elaborare le vendite anche se è disconnesso dal server Retail.</span><span class="sxs-lookup"><span data-stu-id="bb263-162">In offline mode, the POS can continue to process sales even if it's disconnected from the Retail server.</span></span> <span data-ttu-id="bb263-163">Può quindi essere sincronizzato con il database del canale quando viene ripristinata la connessione.</span><span class="sxs-lookup"><span data-stu-id="bb263-163">It can then be synchronized with the channel database when connectivity is restored.</span></span> <span data-ttu-id="bb263-164">MPOS utilizza la propria istanza integrata del CRT e al contempo utilizza la propria origine dati locale (database SQL Server offline).</span><span class="sxs-lookup"><span data-stu-id="bb263-164">MPOS uses its own embedded instance of the CRT and temporarily uses its own local data source (offline SQL Server database).</span></span> <span data-ttu-id="bb263-165">Per ulteriori informazioni sul funzionamento offline, vedere [Funzionamento offline di POS](https://docs.microsoft.com/en-us/dynamics365/unified-operations/retail/pos-offline-functionality) (in lingua inglese).</span><span class="sxs-lookup"><span data-stu-id="bb263-165">For more information about offline functionality, see [POS offline functionality](https://docs.microsoft.com/en-us/dynamics365/unified-operations/retail/pos-offline-functionality).</span></span>

### <a name="pos-peripheralhardware-considerations"></a><span data-ttu-id="bb263-166">Considerazioni sull'unità periferica/hardware POS</span><span class="sxs-lookup"><span data-stu-id="bb263-166">POS peripheral/hardware considerations</span></span>
<span data-ttu-id="bb263-167">I rivenditori devono inoltre considerare in che modo il POS accederà ai dispositivi e alle unità periferiche, ad esempio le stampanti, i cassetti della cassa e i terminali di pagamento.</span><span class="sxs-lookup"><span data-stu-id="bb263-167">Retailers must also consider how the POS will access devices and peripherals such as printers, cash drawers, and payment terminals.</span></span> <span data-ttu-id="bb263-168">Solo MPOS per Windows supporta la comunicazione diretta con tali dispositivi.</span><span class="sxs-lookup"><span data-stu-id="bb263-168">Only MPOS for Windows supports direct communication with these devices.</span></span> <span data-ttu-id="bb263-169">MPOS per Windows Phone, iOS o Android e Cloud POS richiedono l'utilizzo di una stazione hardware per accedere a questi dispositivi.</span><span class="sxs-lookup"><span data-stu-id="bb263-169">MPOS for Windows Phone, iOS, or Android, and Cloud POS require a hardware station in order to access these devices.</span></span> <span data-ttu-id="bb263-170">Le stazioni hardware possono essere dedicate a un registratore di cassa POS o essere suddivise tra i registratori di cassa in un punto vendita.</span><span class="sxs-lookup"><span data-stu-id="bb263-170">Hardware stations can be dedicated to a POS register or shared among the registers in a store.</span></span> <span data-ttu-id="bb263-171">Per ulteriori informazioni su come installare le stazioni hardware, vedere [Configurare e installare una stazione hardware per la vendita al dettaglio](https://docs.microsoft.com/en-us/dynamics365/unified-operations/retail/retail-hardware-station-configuration-installation).</span><span class="sxs-lookup"><span data-stu-id="bb263-171">For more information about hardware stations, see [Configure and install Retail hardware station](https://docs.microsoft.com/en-us/dynamics365/unified-operations/retail/retail-hardware-station-configuration-installation).</span></span>

## <a name="implementation-considerations"></a><span data-ttu-id="bb263-172">Considerazioni sull'implementazione</span><span class="sxs-lookup"><span data-stu-id="bb263-172">Implementation considerations</span></span>
<span data-ttu-id="bb263-173">Considerare le seguenti informazioni quando si pianifica l'implementazione di POS nei propri punti vendita:</span><span class="sxs-lookup"><span data-stu-id="bb263-173">Consider the following information as you plan your POS implementation in your retail stores:</span></span>

- <span data-ttu-id="bb263-174">**Requisiti funzionali** - I processi e le funzionalità aziendali di base sono gli stessi, indipendentemente dalla piattaforma, il fattore di forma o la topologia della distribuzione.</span><span class="sxs-lookup"><span data-stu-id="bb263-174">**Functional requirements** – The core business processes and capabilities are the same, regardless of the platform, form factor, or deployment topology.</span></span> <span data-ttu-id="bb263-175">Di conseguenza, la maggior parte dei rivenditori non deve considerare i requisiti funzionali nella pianificazione dell'implementazione.</span><span class="sxs-lookup"><span data-stu-id="bb263-175">Therefore, most retailers don't have to consider functional requirements when they plan their implementation.</span></span>
- <span data-ttu-id="bb263-176">**Connettività** - La disponibilità della rete (Wide Area Network \[WAN\] e rete locale \[LAN\]) è il principale fattore che richiede un'attenta considerazione.</span><span class="sxs-lookup"><span data-stu-id="bb263-176">**Connectivity** - Network availability (wide area network \[WAN\] and local area network \[LAN\]) is a major factor that requires careful consideration.</span></span> <span data-ttu-id="bb263-177">Tutti i vantaggi che una soluzione ospitata nel cloud e a emissione zero porta in termini di costi e di semplicità vengono persi se il sistema non è disponibile per i processi di rilevanza per l'azienda.</span><span class="sxs-lookup"><span data-stu-id="bb263-177">Any benefits that a zero-footprint, cloud-hosted solution brings in terms of cost and simplicity are lost if the system isn't available for business-critical processes.</span></span>

    <span data-ttu-id="bb263-178">A meno che la connettività per uno specifico dispositivo non sia molto credibile e resiliente o a meno che una certa quantità di inattività non sia accettabile per il rivenditore, è consigliabile utilizzare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="bb263-178">Unless the connectivity for a given device is very dependable and resilient, or unless a certain amount of downtime is acceptable to the retailer, we recommend one of the following options:</span></span>

    - <span data-ttu-id="bb263-179">Utilizzare MPOS in Windows e attivare la modalità offline.</span><span class="sxs-lookup"><span data-stu-id="bb263-179">Use MPOS in Windows, and enable offline mode.</span></span>
    - <span data-ttu-id="bb263-180">Distribuire una RSSU locale.</span><span class="sxs-lookup"><span data-stu-id="bb263-180">Deploy an on-premises RSSU.</span></span>

    <span data-ttu-id="bb263-181">Le due opzioni non si escludono a vicenda.</span><span class="sxs-lookup"><span data-stu-id="bb263-181">These two options aren't mutually exclusive.</span></span> <span data-ttu-id="bb263-182">Per la topologia più attendibile, i rivenditori possono distribuire una RSSU locale per ridurre la dipendenza dalla connettività Internet o la disponibilità di Azure e possono inoltre distribuire registratori POS dove è attivata la modalità offline se è presente un problema con il server locale o la rete.</span><span class="sxs-lookup"><span data-stu-id="bb263-182">For the most reliable topology, retailers can deploy a local RSSU to reduce the dependency on internet connectivity or Azure availability, and they can also deploy POS registers where offline mode is enabled if there is an issue with the local server or network.</span></span>

- <span data-ttu-id="bb263-183">**Dispositivi hardware e periferiche** - Un aspetto importante di un sistema Retail POS è la capacità di utilizzare le periferiche POS, ad esempio le stampanti, i cassetti di cassa e i terminali di pagamento.</span><span class="sxs-lookup"><span data-stu-id="bb263-183">**Hardware devices/peripherals** – One important aspect of a Retail POS system is its ability to use POS peripherals such as printers, cash drawers, and payment terminals.</span></span> <span data-ttu-id="bb263-184">Sebbene tutte le opzioni disponibili di POS possano utilizzare le periferiche, solo MPOS per Windows le supporta direttamente.</span><span class="sxs-lookup"><span data-stu-id="bb263-184">Although all the available POS options can use peripheral devices, only MPOS for Windows supports them directly.</span></span> <span data-ttu-id="bb263-185">Per tutte le altre applicazioni, è necessario munirsi di una o più stazioni hardware.</span><span class="sxs-lookup"><span data-stu-id="bb263-185">For all other applications, one or more hardware stations are required.</span></span> <span data-ttu-id="bb263-186">Sebbene aggiunga flessibilità, questo approccio richiede l'aggiunta, la configurazione e il supporto di componenti aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="bb263-186">Although this approach adds flexibility, additional components must be deployed, configured, and serviced.</span></span>
- <span data-ttu-id="bb263-187">**Requisiti di sistema** - I requisiti di sistema dell'applicazione POS variano.</span><span class="sxs-lookup"><span data-stu-id="bb263-187">**System requirements** – The system requirements for the POS application vary.</span></span> <span data-ttu-id="bb263-188">Assicurarsi di controllare le informazioni più recenti prima di scegliere.</span><span class="sxs-lookup"><span data-stu-id="bb263-188">Be sure to check the latest information before you make your choice.</span></span> <span data-ttu-id="bb263-189">Ad esempio, poiché CPOS viene eseguito in un browser, supporta una gamma più ampia di sistemi operativi.</span><span class="sxs-lookup"><span data-stu-id="bb263-189">For example, because CPOS runs in a browser, it supports a wider range of operating systems.</span></span> <span data-ttu-id="bb263-190">Per ulteriori informazioni sui requisiti di sistema, vedere [Requisiti di sistema per le distribuzioni cloud](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/get-started/system-requirements).</span><span class="sxs-lookup"><span data-stu-id="bb263-190">For more information about system requirements, see [System requirements for cloud deployments](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/get-started/system-requirements).</span></span>
- <span data-ttu-id="bb263-191">**Distribuzione e assistenza** - La complessità di requisiti di assistenza e di distribuzione può variare, a seconda delle scelte di distribuzione e di applicazioni.</span><span class="sxs-lookup"><span data-stu-id="bb263-191">**Deployment and servicing** – The complexity of the deployment and servicing requirements can vary, depending on the application and deployment choices.</span></span> <span data-ttu-id="bb263-192">Ad esempio, per una distribuzione CPOS ospitata nel cloud, non è necessario installare e aggiornare in ogni dispositivo.</span><span class="sxs-lookup"><span data-stu-id="bb263-192">For example, for a cloud-hosted CPOS deployment, you don't have to install and update on every device.</span></span> <span data-ttu-id="bb263-193">Di conseguenza, tale approccio semplifica notevolmente la complessità e riduce i costi.</span><span class="sxs-lookup"><span data-stu-id="bb263-193">Therefore, this approach greatly reduces complexity and cost.</span></span> <span data-ttu-id="bb263-194">Tuttavia, se si distribuisce MPOS in ogni registratore e si attiva la modalità offline e si distribuiscono anche stazioni hardware condivise, si aumenta enormemente il numero di endpoint che devono essere gestiti.</span><span class="sxs-lookup"><span data-stu-id="bb263-194">However, if you deploy MPOS on every register and enable offline mode, and you also deploy shared hardware stations, you greatly increase the number of endpoints that must be managed.</span></span>
