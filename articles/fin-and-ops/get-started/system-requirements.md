---
title: Requisiti di sistema per le distribuzioni cloud
description: In questo argomento vengono elencati i requisiti di sistema per la versione corrente di Microsoft Dynamics 365 for Finance and Operations, Enterprise edition per le distribuzioni nel cloud.
author: sericks007
manager: AnnBe
ms.date: 08/02/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 55651
ms.assetid: e564d51d-42d3-47c5-b388-93b8219c692a
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-08-30
ms.dyn365.ops.version: Platform update 8
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 83637b4b2ccc01950e68569b3b8bee1a7cd69855
ms.contentlocale: it-it
ms.lasthandoff: 11/03/2017

---

# <a name="system-requirements-for-cloud-deployments"></a><span data-ttu-id="d1045-103">Requisiti di sistema per le distribuzioni cloud</span><span class="sxs-lookup"><span data-stu-id="d1045-103">System requirements for cloud deployments</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="d1045-104">In questo argomento vengono elencati i requisiti di sistema per la versione corrente di Microsoft Dynamics 365 for Finance and Operations, Enterprise edition per le distribuzioni nel cloud.</span><span class="sxs-lookup"><span data-stu-id="d1045-104">This topic lists the system requirements for the current version of Microsoft Dynamics 365 for Finance and Operations, Enterprise edition, for cloud deployments.</span></span> <span data-ttu-id="d1045-105">Prima di installare Finance and Operations, laddove appropriato, verificare che il sistema su cui si sta lavorando soddisfi almeno i requisiti minimi di rete, hardware e software.</span><span class="sxs-lookup"><span data-stu-id="d1045-105">Before you install Finance and Operations, when this step is appropriate, verify that the system that you're working with meets or exceeds the minimum network, hardware, and software requirements.</span></span>

## <a name="supported-web-browsers"></a><span data-ttu-id="d1045-106">Web browser supportati</span><span class="sxs-lookup"><span data-stu-id="d1045-106">Supported web browsers</span></span>
<span data-ttu-id="d1045-107">L'applicazione Web può essere eseguita in uno dei seguenti Web browser eseguiti sui sistemi operativi specificati:</span><span class="sxs-lookup"><span data-stu-id="d1045-107">The web application can run in any of the following web browsers that run on the specified operating systems:</span></span>

-   <span data-ttu-id="d1045-108">Microsoft Edge (ultima versione pubblicamente disponibile) su Windows 10</span><span class="sxs-lookup"><span data-stu-id="d1045-108">Microsoft Edge (latest publicly available version) on Windows 10</span></span>
-   <span data-ttu-id="d1045-109">Internet Explorer 11 in Windows 10, Windows 8.1 o Windows 7</span><span class="sxs-lookup"><span data-stu-id="d1045-109">Internet Explorer 11 on Windows 10, Windows 8.1, or Windows 7</span></span>
-   <span data-ttu-id="d1045-110">Google Chrome (ultima versione pubblicamente disponibile) su Windows 10, Windows 8.1, Windows 8, Windows 7 o tablet Google Nexus 10</span><span class="sxs-lookup"><span data-stu-id="d1045-110">Google Chrome (latest publicly available version) on Windows 10, Windows 8.1, Windows 8, Windows 7, or Google Nexus 10 tablet</span></span>
-   <span data-ttu-id="d1045-111">Apple Safari (ultima versione pubblicamente disponibile) su Mac OS X 10.10 (Yosemite), 10.11 (El Capitan), 10.12 (Sierra) o Apple iPad</span><span class="sxs-lookup"><span data-stu-id="d1045-111">Apple Safari (latest publicly available version) on Mac OS X 10.10 (Yosemite), 10.11 (El Capitan) or 10.12 (Sierra), or Apple iPad</span></span>

<span data-ttu-id="d1045-112">Per trovare l'ultima versione rilasciata di ogni Web browser, andare al sito Web del produttore software.</span><span class="sxs-lookup"><span data-stu-id="d1045-112">To find the latest release for each web browser, go to the software manufacturer’s website.</span></span> 

> [!NOTE]
> -   <span data-ttu-id="d1045-113">Per acquisire screenshot con Registrazione attività e includerli nei documenti di Microsoft Word generati, è necessario installare un'estensione Chrome pre-release.</span><span class="sxs-lookup"><span data-stu-id="d1045-113">You must install a pre-release Chrome extension to enable Task Recorder to capture screenshots and include them in Microsoft Word documents that are generated.</span></span> <!---For instructions about how to install the extension, see [Screenshot Extension setup](../../dev-itpro/user-interface/task-recorder).-->
> -   <span data-ttu-id="d1045-114">L'editor flusso di lavoro viene avviato come un'applicazione ClickOnce.</span><span class="sxs-lookup"><span data-stu-id="d1045-114">The Workflow Editor is started as a ClickOnce application.</span></span> <span data-ttu-id="d1045-115">Solo Microsoft Edge e Internet Explorer (su una versione supportata di Microsoft Windows) supportano le applicazioni ClickOnce.</span><span class="sxs-lookup"><span data-stu-id="d1045-115">Only Microsoft Edge and Internet Explorer (on a supported version of Microsoft Windows) support ClickOnce applications.</span></span> <span data-ttu-id="d1045-116">L'applicazione ClickOnce dell'editor flusso di lavoro richiede un sistema operativo compatibile a 64 bit.</span><span class="sxs-lookup"><span data-stu-id="d1045-116">The Workflow Editor ClickOnce application requires a 64-bit-compatible operating system.</span></span>
> -   <span data-ttu-id="d1045-117">La funzionalità Progettazione report per i report finanziari viene avviata come un'applicazione ClickOnce.</span><span class="sxs-lookup"><span data-stu-id="d1045-117">The Report Designer for Financial reporting is started as a ClickOnce application.</span></span> <span data-ttu-id="d1045-118">Richiede un sistema operativo compatibile a 64 bit.</span><span class="sxs-lookup"><span data-stu-id="d1045-118">It requires a 64-bit-compatible operating system.</span></span> <span data-ttu-id="d1045-119">Se si utilizza Chrome, è necessario installare un'estensione ClickOnce per scaricare il client di progettazione report.</span><span class="sxs-lookup"><span data-stu-id="d1045-119">If you’re using Chrome, you must install a ClickOnce extension to download the Report Designer client.</span></span> <span data-ttu-id="d1045-120">Se si utilizza Chrome con la modalità in incognito, assicurarsi che l'estensione ClickOnce sia abilitata anche per tale modalità.</span><span class="sxs-lookup"><span data-stu-id="d1045-120">If you use Chrome in Incognito mode, make sure that the ClickOnce extension is also enabled for Incognito mode.</span></span>
> -   <span data-ttu-id="d1045-121">Per visualizzare l'anteprima dei file PDF, si consiglia di utilizzare browser come Microsoft Edge (versione pubblica più recente) su Windows 10 o Google Chrome (versione pubblica più recente) su Windows 10, Windows 8.1, Windows 8, Windows 7 o tablet Google Nexus 10.</span><span class="sxs-lookup"><span data-stu-id="d1045-121">To preview PDF files, we recommend that you use browsers such as Microsoft Edge (latest publicly available version) on Windows 10, or Google Chrome (latest publicly available version) on Windows 10, Windows 8.1, Windows 8, Windows 7, or Google Nexus 10 tablet.</span></span>

### <a name="supported-web-browsers-for-retail-cloud-pos"></a><span data-ttu-id="d1045-122">Web browser supportati per POS cloud vendita al dettaglio</span><span class="sxs-lookup"><span data-stu-id="d1045-122">Supported web browsers for Retail Cloud POS</span></span>

<span data-ttu-id="d1045-123">Retail Cloud POS può essere eseguito in uno dei seguenti Web browser eseguiti sui sistemi operativi specificati:</span><span class="sxs-lookup"><span data-stu-id="d1045-123">Retail Cloud POS can run in any of the following web browsers that run on the specified operating systems:</span></span>

-   <span data-ttu-id="d1045-124">Microsoft Edge (ultima versione pubblicamente disponibile) su Windows 10</span><span class="sxs-lookup"><span data-stu-id="d1045-124">Microsoft Edge (latest publicly available version) on Windows 10</span></span>
-   <span data-ttu-id="d1045-125">Internet Explorer 11 in Windows 10, Windows 8.1 o Windows 7</span><span class="sxs-lookup"><span data-stu-id="d1045-125">Internet Explorer 11 on Windows 10, Windows 8.1, or Windows 7</span></span>
-   <span data-ttu-id="d1045-126">Chrome (ultima versione pubblicamente disponibile) su Windows 10, Windows 8.1 o Windows 7</span><span class="sxs-lookup"><span data-stu-id="d1045-126">Chrome (latest publicly available version) on Windows 10, Windows 8.1, or Windows 7</span></span>

## <a name="network-requirements"></a><span data-ttu-id="d1045-127">Requisiti di rete</span><span class="sxs-lookup"><span data-stu-id="d1045-127">Network requirements</span></span>
-   <span data-ttu-id="d1045-128">Finance and Operations è progettato per reti con latenza pari a 250-300 millisecondi (ms) o inferiore.</span><span class="sxs-lookup"><span data-stu-id="d1045-128">Finance and Operations is designed for networks that have a latency of 250–300 milliseconds (ms) or less.</span></span> <span data-ttu-id="d1045-129">Questa è la latenza da un client browser al data center di Microsoft Azure che ospita Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="d1045-129">This latency is the latency from a browser client to the Microsoft Azure datacenter that hosts Finance and Operations.</span></span> <span data-ttu-id="d1045-130">Si consiglia di verificare la latenza di rete all'indirizzo <http://www.azurespeed.com>.</span><span class="sxs-lookup"><span data-stu-id="d1045-130">We recommend that you test network latency at <http://www.azurespeed.com>.</span></span>
-   <span data-ttu-id="d1045-131">I requisiti di larghezza di banda per Finance and Operations dipendono dallo scenario.</span><span class="sxs-lookup"><span data-stu-id="d1045-131">Bandwidth requirements for Finance and Operations depend on your scenario.</span></span> <span data-ttu-id="d1045-132">La maggior parte degli scenari tipici richiede una larghezza di banda superiore a 50 kilobyte al secondo (Kbps).</span><span class="sxs-lookup"><span data-stu-id="d1045-132">Most typical scenarios require a bandwidth of more than 50 kilobytes per second (KBps).</span></span> <span data-ttu-id="d1045-133">Tuttavia, per scenari con requisiti di carico utile elevati, che implicano ad esempio aree di lavoro o personalizzazioni estese, è consigliabile disporre di maggiore larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="d1045-133">However, we recommend more bandwidth for scenarios that have high payload requirements, such as scenarios that involve workspaces or extensive customization.</span></span>

<span data-ttu-id="d1045-134">In genere, Finance and Operations è ottimizzato per Internet.</span><span class="sxs-lookup"><span data-stu-id="d1045-134">In general, Finance and Operations is optimized for the internet.</span></span> <span data-ttu-id="d1045-135">Il numero di round trip da un client del browser al data center di Azure è esiguo e l'intero carico utile è compresso.</span><span class="sxs-lookup"><span data-stu-id="d1045-135">The number of round trips from a browser client to the Azure datacenter is very small, and the whole payload is compressed.</span></span> 

> [!WARNING]
> <span data-ttu-id="d1045-136">Non calcolare i requisiti di larghezza di banda da un'ubicazione client moltiplicando il numero di utenti per i requisiti minimi di larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="d1045-136">Don't calculate bandwidth requirements from a client location by multiplying the number of users by the minimum bandwidth requirements.</span></span> <span data-ttu-id="d1045-137">L'utilizzo simultaneo di una determinata ubicazione è molto difficile da calcolare.</span><span class="sxs-lookup"><span data-stu-id="d1045-137">The concurrent usage of a given location is very difficult to calculate.</span></span> <span data-ttu-id="d1045-138">I clienti con problemi relativi ai requisiti di larghezza di banda devono utilizzare una versione di anteprima di Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="d1045-138">Customers who are concerned about bandwidth requirements should use a preview version of Finance and Operations.</span></span>

## <a name="net-framework-requirements"></a><span data-ttu-id="d1045-139">Requisiti per .NET Framework</span><span class="sxs-lookup"><span data-stu-id="d1045-139">.NET Framework requirements</span></span>
<span data-ttu-id="d1045-140">Finance and Operations richiede Microsoft .NET Framework versione 4.6.2 per tutte le applicazioni ClickOnce, ad esempio l'agente di distribuzione documenti.</span><span class="sxs-lookup"><span data-stu-id="d1045-140">Finance and Operations requires the Microsoft .NET Framework version 4.6.2 for all ClickOnce applications, such as the document routing agent.</span></span> <span data-ttu-id="d1045-141">Per istruzioni relative all'installazione, vedere [Installazione di .NET Framework](https://msdn.microsoft.com/en-us/library/5a4x27ek(v=vs.110).aspx).</span><span class="sxs-lookup"><span data-stu-id="d1045-141">For installation instructions, see [Installing the .NET Framework](https://msdn.microsoft.com/en-us/library/5a4x27ek(v=vs.110).aspx).</span></span>

## <a name="supported-microsoft-office-applications"></a><span data-ttu-id="d1045-142">Applicazioni di Microsoft Office supportate</span><span class="sxs-lookup"><span data-stu-id="d1045-142">Supported Microsoft Office applications</span></span>
<span data-ttu-id="d1045-143">Le applicazioni di Microsoft Office seguenti sono supportate nelle distribuzioni locali e cloud di Finance and Operations:</span><span class="sxs-lookup"><span data-stu-id="d1045-143">The following Microsoft Office applications are supported in cloud and on-premises deployments of Finance and Operations:</span></span>

-   <span data-ttu-id="d1045-144">Per eseguire i componenti aggiuntivi di Microsoft Excel e Word, è necessario che sia installato Microsoft Office 2016 per Windows o Mac.</span><span class="sxs-lookup"><span data-stu-id="d1045-144">To run the Microsoft Excel and Word add-ins, you must have Microsoft Office 2016 for Windows or Mac installed.</span></span> <span data-ttu-id="d1045-145">Per ulteriori informazioni sui requisiti di versione, vedere [Risoluzione dei problemi di integrazione di Office](../../dev-itpro/office-integration/office-integration-troubleshooting.md).</span><span class="sxs-lookup"><span data-stu-id="d1045-145">For more information about version requirements, see [Office integration troubleshooting](../../dev-itpro/office-integration/office-integration-troubleshooting.md).</span></span>
-   <span data-ttu-id="d1045-146">Per visualizzare i documenti generati dalla funzionalità Esporta in Excel o Esporta in Word, è necessario che sia installato Microsoft Office 2007 o versioni successive.</span><span class="sxs-lookup"><span data-stu-id="d1045-146">To view documents that are generated by the Export to Excel or Export to Word functionality, you must have Microsoft Office 2007 or later installed.</span></span>

## <a name="retail-modern-pos-requirements"></a><span data-ttu-id="d1045-147">Requisiti per Retail Modern POS</span><span class="sxs-lookup"><span data-stu-id="d1045-147">Retail Modern POS requirements</span></span>

> [!NOTE]
> <span data-ttu-id="d1045-148">Se Retail Modern POS utilizza un database offline, il computer deve soddisfare tutte i requisiti di sistema per Microsoft SQL Server.</span><span class="sxs-lookup"><span data-stu-id="d1045-148">If Retail Modern POS will use an offline database, the computer must meet all system requirements for Microsoft SQL Server.</span></span> <span data-ttu-id="d1045-149">Un database offline di Retail Modern POS è compatibile con Microsoft SQL Server 2012 con Service Pack 3 o versione successiva, Microsoft SQL Server 2014 con Service Pack 2 o versione successiva e Microsoft SQL Server 2016.</span><span class="sxs-lookup"><span data-stu-id="d1045-149">A Retail Modern POS offline database will work on Microsoft SQL Server 2012 with Service Pack 3 or later, Microsoft SQL Server 2014 with Service Pack 2 or later, and Microsoft SQL Server 2016.</span></span> <span data-ttu-id="d1045-150">Si consiglia di utilizzare sempre l'ultima versione disponibile e di installare tutti i Service Pack più recenti.</span><span class="sxs-lookup"><span data-stu-id="d1045-150">We recommend that you always use the latest version that is available, and that you install all the latest service packs.</span></span>

### <a name="supported-operating-systems"></a><span data-ttu-id="d1045-151">Sistemi operativi supportati</span><span class="sxs-lookup"><span data-stu-id="d1045-151">Supported operating systems</span></span>

-   <span data-ttu-id="d1045-152">Retail Modern POS è un'applicazione a 32 bit, ma verrà eseguita su entrambe le architetture x86 e x64.</span><span class="sxs-lookup"><span data-stu-id="d1045-152">Retail Modern POS is a 32-bit application, but it will run on both x86 and x64 architectures.</span></span>
-   <span data-ttu-id="d1045-153">Retail Modern POS è supportato solo su Windows 10 edizioni Pro, Enterprise ed Enterprise Long Term Servicing Branch (LTSB).</span><span class="sxs-lookup"><span data-stu-id="d1045-153">Retail Modern POS is supported only on Windows 10 Pro, Enterprise, and Enterprise Long Term Servicing Branch (LTSB) editions.</span></span>

### <a name="minimum-system-requirements"></a><span data-ttu-id="d1045-154">Requisiti minimi di sistema</span><span class="sxs-lookup"><span data-stu-id="d1045-154">Minimum system requirements</span></span>

-   <span data-ttu-id="d1045-155">La risoluzione minima supportata è 1280 × 1024.</span><span class="sxs-lookup"><span data-stu-id="d1045-155">The minimum supported resolution is 1,280 × 1,024.</span></span>
-   <span data-ttu-id="d1045-156">Il computer su cui viene eseguito Retail Modern POS deve soddisfare i seguenti requisiti:</span><span class="sxs-lookup"><span data-stu-id="d1045-156">The computer that Retail Modern POS runs on must meet these requirements:</span></span>

    -   <span data-ttu-id="d1045-157">Deve disporre, come minimo, di un processore dual-core in esecuzione ad almeno 2 gigahertz (GHz).</span><span class="sxs-lookup"><span data-stu-id="d1045-157">It must have, at a minimum, a dual-core processor that runs at no less than 2 gigahertz (GHz).</span></span>
    -   <span data-ttu-id="d1045-158">Deve disporre, come minimo, di 3 gigabyte (GB) di RAM.</span><span class="sxs-lookup"><span data-stu-id="d1045-158">It must have, at a minimum, 3 gigabytes (GB) of random-access memory (RAM).</span></span>
    -   <span data-ttu-id="d1045-159">Deve disporre dell'accesso a Internet.</span><span class="sxs-lookup"><span data-stu-id="d1045-159">It must have internet access.</span></span>

## <a name="retail-hardware-station-requirements"></a><span data-ttu-id="d1045-160">Requisiti per Retail hardware station</span><span class="sxs-lookup"><span data-stu-id="d1045-160">Retail hardware station requirements</span></span>
### <a name="supported-operating-systems"></a><span data-ttu-id="d1045-161">Sistemi operativi supportati</span><span class="sxs-lookup"><span data-stu-id="d1045-161">Supported operating systems</span></span>

-   <span data-ttu-id="d1045-162">Retail hardware station è un'applicazione a 32 bit, ma verrà eseguita su entrambe le architetture x86 e x64.</span><span class="sxs-lookup"><span data-stu-id="d1045-162">Retail hardware station is a 32-bit application, but it will run on both x86 and x64 architectures.</span></span>
-   <span data-ttu-id="d1045-163">Retail hardware station è supportata sui seguenti sistemi operativi:</span><span class="sxs-lookup"><span data-stu-id="d1045-163">Retail hardware station is supported on the following operating systems:</span></span>

    -   <span data-ttu-id="d1045-164">Windows 7 edizioni Professional, Enterprise e Ultimate</span><span class="sxs-lookup"><span data-stu-id="d1045-164">Windows 7 Professional, Enterprise, and Ultimate editions</span></span> 
    
        > [!NOTE]
        > <span data-ttu-id="d1045-165">Windows 7 è supportato solo se Internet Explorer 11 viene installato manualmente nel sistema.</span><span class="sxs-lookup"><span data-stu-id="d1045-165">Windows 7 is supported only if Internet Explorer 11 is manually installed on the system.</span></span>

    -   <span data-ttu-id="d1045-166">Windows 8.1 Update 1 edizioni Professional, Enterprise ed Embedded</span><span class="sxs-lookup"><span data-stu-id="d1045-166">Windows 8.1 Update 1 Professional, Enterprise, and Embedded editions</span></span>
    -   <span data-ttu-id="d1045-167">Windows 10 edizioni Pro, Enterprise ed Enterprise LTSB</span><span class="sxs-lookup"><span data-stu-id="d1045-167">Windows 10 Pro, Enterprise, and Enterprise LTSB editions</span></span>

### <a name="minimum-system-requirements"></a><span data-ttu-id="d1045-168">Requisiti minimi di sistema</span><span class="sxs-lookup"><span data-stu-id="d1045-168">Minimum system requirements</span></span>

<span data-ttu-id="d1045-169">Il computer deve soddisfare tutti i requisiti di sistema per l'installazione e l'utilizzo dei seguenti elementi:</span><span class="sxs-lookup"><span data-stu-id="d1045-169">The computer must meet all system requirements for installing and using the following items:</span></span>

-   <span data-ttu-id="d1045-170">Internet Information Services (IIS)</span><span class="sxs-lookup"><span data-stu-id="d1045-170">Internet Information Services (IIS)</span></span>
-   <span data-ttu-id="d1045-171">Hardware di terze parti</span><span class="sxs-lookup"><span data-stu-id="d1045-171">Third-party hardware</span></span>

## <a name="retail-store-scale-unit-requirements"></a><span data-ttu-id="d1045-172">Requisiti per Retail Store Scale Unit</span><span class="sxs-lookup"><span data-stu-id="d1045-172">Retail Store Scale Unit requirements</span></span>
### <a name="supported-operating-systems"></a><span data-ttu-id="d1045-173">Sistemi operativi supportati</span><span class="sxs-lookup"><span data-stu-id="d1045-173">Supported operating systems</span></span>

-   <span data-ttu-id="d1045-174">Retail Store Scale Unit è un'applicazione a 32 bit, ma verrà eseguita su entrambe le architetture x86 e x64.</span><span class="sxs-lookup"><span data-stu-id="d1045-174">Retail Store Scale Unit is a 32-bit application, but it will run on both x86 and x64 architectures.</span></span>
-   <span data-ttu-id="d1045-175">Retail Store Scale Unit è supportata sui seguenti sistemi operativi:</span><span class="sxs-lookup"><span data-stu-id="d1045-175">Retail Store Scale Unit is supported on the following operating systems:</span></span>

    -   <span data-ttu-id="d1045-176">Windows 7 edizioni Professional, Enterprise e Ultimate</span><span class="sxs-lookup"><span data-stu-id="d1045-176">Windows 7 Professional, Enterprise, and Ultimate editions</span></span>
    -   <span data-ttu-id="d1045-177">Windows 8.1 Update 1 edizioni Professional, Enterprise ed Embedded</span><span class="sxs-lookup"><span data-stu-id="d1045-177">Windows 8.1 Update 1 Professional, Enterprise, and Embedded editions</span></span>
    -   <span data-ttu-id="d1045-178">Windows 10 edizioni Pro, Enterprise ed Enterprise LTSB</span><span class="sxs-lookup"><span data-stu-id="d1045-178">Windows 10 Pro, Enterprise, and Enterprise LTSB editions</span></span>

### <a name="minimum-system-requirements"></a><span data-ttu-id="d1045-179">Requisiti minimi di sistema</span><span class="sxs-lookup"><span data-stu-id="d1045-179">Minimum system requirements</span></span>

-   <span data-ttu-id="d1045-180">4 GB di RAM</span><span class="sxs-lookup"><span data-stu-id="d1045-180">4 GB of RAM</span></span>
-   <span data-ttu-id="d1045-181">CPU con velocità di picco da 1,6 GHz per core (minimo due core).</span><span class="sxs-lookup"><span data-stu-id="d1045-181">1.6 GHz peak CPU speed per core (Two cores are the minimum.)</span></span>
-   <span data-ttu-id="d1045-182">Almeno 10 GB di spazio libero (il database del canale può richiedere una quantità di spazio notevole).</span><span class="sxs-lookup"><span data-stu-id="d1045-182">At least 10 GB of free space (The channel database can require a large amount of space.)</span></span>

### <a name="recommended-system-requirements"></a><span data-ttu-id="d1045-183">Requisiti di sistema consigliati</span><span class="sxs-lookup"><span data-stu-id="d1045-183">Recommended system requirements</span></span>

-   <span data-ttu-id="d1045-184">6 GB di RAM</span><span class="sxs-lookup"><span data-stu-id="d1045-184">6 GB of RAM</span></span>
-   <span data-ttu-id="d1045-185">CPU con velocità di picco da 2,4 GHz i7 (o equivalente) per core (quattro core consigliati).</span><span class="sxs-lookup"><span data-stu-id="d1045-185">2.4 GHz i7 (or equivalent) peak CPU speed per core (Four cores are recommended.)</span></span>
-   <span data-ttu-id="d1045-186">Almeno 10 GB di spazio libero (il database del canale può richiedere una quantità di spazio notevole).</span><span class="sxs-lookup"><span data-stu-id="d1045-186">At least 10 GB of free space (The channel database can require a large amount of space.)</span></span>

## <a name="connector-requirements"></a><span data-ttu-id="d1045-187">Requisiti del connettore</span><span class="sxs-lookup"><span data-stu-id="d1045-187">Connector requirements</span></span>
### <a name="supported-operating-systems"></a><span data-ttu-id="d1045-188">Sistemi operativi supportati</span><span class="sxs-lookup"><span data-stu-id="d1045-188">Supported operating systems</span></span>

-   <span data-ttu-id="d1045-189">Il connettore per Microsoft Dynamics AX dispone di due programmi di installazione distinti, uno per Async Server Connector service e un altro per Real-time service for Dynamics AX 2012 R3.</span><span class="sxs-lookup"><span data-stu-id="d1045-189">The Connector for Microsoft Dynamics AX has two separate installers, one for Async Server Connector service and one for Real-time service for Dynamics AX 2012 R3.</span></span>
-   <span data-ttu-id="d1045-190">Entrambi i componenti sono applicazioni a 32 bit, ma vengono eseguiti sia su architetture x86 che x64.</span><span class="sxs-lookup"><span data-stu-id="d1045-190">Both components are 32-bit applications, but they will run on both x86 and x64 architectures.</span></span>
-   <span data-ttu-id="d1045-191">Entrambi i componenti sono supportati nei sistemi operativi seguenti:</span><span class="sxs-lookup"><span data-stu-id="d1045-191">Both components are supported on the following operating systems:</span></span>

    -   <span data-ttu-id="d1045-192">Windows 7 edizioni Professional, Enterprise e Ultimate</span><span class="sxs-lookup"><span data-stu-id="d1045-192">Windows 7 Professional, Enterprise, and Ultimate editions</span></span>
    -   <span data-ttu-id="d1045-193">Windows 8.1 Update 1 edizioni Professional, Enterprise ed Embedded</span><span class="sxs-lookup"><span data-stu-id="d1045-193">Windows 8.1 Update 1 Professional, Enterprise, and Embedded editions</span></span>
    -   <span data-ttu-id="d1045-194">Windows 10 edizioni Pro, Enterprise ed Enterprise LTSB</span><span class="sxs-lookup"><span data-stu-id="d1045-194">Windows 10 Pro, Enterprise, and Enterprise LTSB editions</span></span>
    -   <span data-ttu-id="d1045-195">Microsoft Windows Server 2012 R2 e Microsoft Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="d1045-195">Microsoft Windows Server 2012 R2 and Microsoft Windows Server 2016</span></span>

### <a name="minimum-system-requirements"></a><span data-ttu-id="d1045-196">Requisiti minimi di sistema</span><span class="sxs-lookup"><span data-stu-id="d1045-196">Minimum system requirements</span></span>
-   <span data-ttu-id="d1045-197">2 GB di RAM (4 GB di RAM consigliati)</span><span class="sxs-lookup"><span data-stu-id="d1045-197">2 GB of RAM (4 GB of RAM are recommended.)</span></span>
-   <span data-ttu-id="d1045-198">CPU con velocità di picco da 1,6 GHz per core (minimo due core).</span><span class="sxs-lookup"><span data-stu-id="d1045-198">1.6 GHz peak CPU speed per core (Two cores are the minimum.)</span></span>
-   <span data-ttu-id="d1045-199">Almeno 10 GB di spazio libero (il database del canale può richiedere una quantità di spazio notevole).</span><span class="sxs-lookup"><span data-stu-id="d1045-199">At least 10 GB of free space (The channel database can require a large amount of space.)</span></span>

## <a name="requirements-for-development-on-local-vms"></a><span data-ttu-id="d1045-200">Requisiti per sviluppo su VM locali</span><span class="sxs-lookup"><span data-stu-id="d1045-200">Requirements for development on local VMs</span></span>
<span data-ttu-id="d1045-201">Per ulteriori informazioni sui requisiti per lo sviluppo su macchine virtuali locali (VM), vedere [VM in esecuzione presso la sede](../../dev-itpro/dev-tools/access-instances.md).</span><span class="sxs-lookup"><span data-stu-id="d1045-201">For information about the requirements for development on local virtual machines (VMs), see [VM running on-premises](../../dev-itpro/dev-tools/access-instances.md).</span></span>


## <a name="see-also"></a><span data-ttu-id="d1045-202">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d1045-202">See also</span></span>

[<span data-ttu-id="d1045-203">Ottenere una copia di valutazione di Dynamics 365 for Finance and Operations, Enterprise edition</span><span class="sxs-lookup"><span data-stu-id="d1045-203">Get an evaluation copy of Dynamics 365 for Finance and Operations, Enterprise edition</span></span>](../../dev-itpro/dev-tools/get-evaluation-copy.md)

