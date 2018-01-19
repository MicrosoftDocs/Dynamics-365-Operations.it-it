---
title: Standard supportati per la fatturazione elettronica in Europa
description: In questo argomento viene descritto il livello di copertura della fatturazione elettronica in Microsoft Dynamics 365 or electronic invoicing in Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition nella regione europea.
author: mrolecki
manager: AnnBe
ms.date: 07/11/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 10274
ms.search.region: Austria, Denmark, Italy, Norway, Spain, France, Belgium, Netherlands
ms.search.industry: 
ms.author: mrolecki
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.translationtype: HT
ms.sourcegitcommit: ceea24519d641c676521771cee274feb64ca7783
ms.openlocfilehash: 80f83c2ae75dd4cb16d62f7cd8dcdad16b38ed1d
ms.contentlocale: it-it
ms.lasthandoff: 01/19/2018

---

# <a name="supported-standards-for-electronic-invoicing-in-europe"></a><span data-ttu-id="1428b-103">Standard supportati per la fatturazione elettronica in Europa</span><span class="sxs-lookup"><span data-stu-id="1428b-103">Supported standards for electronic invoicing in Europe</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="1428b-104">In questo argomento viene descritto il livello di copertura della fatturazione elettronica per l'Europa.</span><span class="sxs-lookup"><span data-stu-id="1428b-104">This topic explains the level of coverage that exists for electronic invoicing for Europe.</span></span> 

<span data-ttu-id="1428b-105">L'implementazione e l'adozione della fatturazione elettronica in scala comunitaria europea è disciplinata da [Direttiva del Consiglio 2010/45/UE](http://eur-lex.europa.eu/LexUriServ/LexUriServ.do?uri=OJ:L:2010:189:0001:0008:EN:PDF), che interessa tutti gli stati membri UE.</span><span class="sxs-lookup"><span data-stu-id="1428b-105">Implementation and adoption of European Union-wide electronic invoicing is regulated [Council Directive 2010/45/EU](http://eur-lex.europa.eu/LexUriServ/LexUriServ.do?uri=OJ:L:2010:189:0001:0008:EN:PDF), which affects all EU member states.</span></span> <span data-ttu-id="1428b-106">Le società che desiderano beneficiare della fatturazione elettronica devono inviare fatture di ordini cliente, fatture a testo libero, fatture di progetto, note di accredito ordini cliente e note di accredito delle fatture di progetto come file XML al governo o ad altre parti del settore che richiedono l'utilizzo della fatturazione elettronica.</span><span class="sxs-lookup"><span data-stu-id="1428b-106">Companies that want to benefit from electronic invoicing must submit sales order invoices, free text invoices, project invoices, sales order credit notes, and project invoice credit notes as .xml files to the government or other trading parties that mandate use of electronic invoicing.</span></span> <span data-ttu-id="1428b-107">Questi file XML devono rispondere a determinate regole.</span><span class="sxs-lookup"><span data-stu-id="1428b-107">These .xml files must comply with certain standards.</span></span> <span data-ttu-id="1428b-108">I requisiti specifici di un paese e la relativa implementazione possono differire tra gli stati membri UE, ma normalmente utilizzano sia Universal Business Language ([UBL](https://www.oasis-open.org/committees/tc_home.php?wg_abbrev=ubl)) nelle versioni diverse con personalizzazioni che le specifiche e i punti di accesso [PEPPOL](http://www.peppol.eu) per la convalida e il trasporto.</span><span class="sxs-lookup"><span data-stu-id="1428b-108">The country-specific requirements and their implementation may differ across EU member states but commonly they are using Universal Business Language ([UBL](https://www.oasis-open.org/committees/tc_home.php?wg_abbrev=ubl)) in different versions with customizations as well as [PEPPOL](http://www.peppol.eu) specifications and access points for validation and transportation.</span></span> <span data-ttu-id="1428b-109">Il vantaggio principale dell'UBL è che i documenti aziendali possono essere standardizzati per diversi scopi.</span><span class="sxs-lookup"><span data-stu-id="1428b-109">The primary advantage of UBL is that business documents can be standardized for different purposes.</span></span> <span data-ttu-id="1428b-110">Poiché l'UBL è uno standard internazionale flessibile che supporta numerosi requisiti aziendali, questi documenti aziendali possono essere scambiati tra paesi diversi.</span><span class="sxs-lookup"><span data-stu-id="1428b-110">Because UBL is a flexible, international standard that supports many business requirements, these business documents can be exchanged across national borders.</span></span>

## <a name="what-electronic-invoice-formats-are-currently-available-in-finance-and-operations"></a><span data-ttu-id="1428b-111">Quali formati di fattura elettronica sono attualmente disponibili in Finance and Operations?</span><span class="sxs-lookup"><span data-stu-id="1428b-111">What electronic invoice formats are currently available in Finance and Operations?</span></span>

<span data-ttu-id="1428b-112">Sono disponibili i seguenti formati di fatture elettroniche specifici di ciascun paese:</span><span class="sxs-lookup"><span data-stu-id="1428b-112">The following country-specific formats of electronic invoices are available:</span></span>

-   <span data-ttu-id="1428b-113">OIOUBL v.2.02 per la Danimarca</span><span class="sxs-lookup"><span data-stu-id="1428b-113">OIOUBL v.2.02 for Denmark</span></span>
-   <span data-ttu-id="1428b-114">EHF v.2.0.8 per la Norvegia</span><span class="sxs-lookup"><span data-stu-id="1428b-114">EHF v.2.0.8 for Norway</span></span>
-   <span data-ttu-id="1428b-115">PEPPOL BIS v.2 per Austria, Francia e Belgio</span><span class="sxs-lookup"><span data-stu-id="1428b-115">PEPPOL BIS v.2 for Austria, France, and Belgium</span></span>
-   <span data-ttu-id="1428b-116">UBL-OHNL 1.9 per i Paesi Bassi</span><span class="sxs-lookup"><span data-stu-id="1428b-116">UBL-OHNL 1.9 for the Netherlands</span></span>
-   <span data-ttu-id="1428b-117">FacturaE v.3.2.1 per la Spagna</span><span class="sxs-lookup"><span data-stu-id="1428b-117">FacturaE v.3.2.1 for Spain</span></span>
-   <span data-ttu-id="1428b-118">FatturaPA v.1.2 per l'Italia</span><span class="sxs-lookup"><span data-stu-id="1428b-118">FatturaPA v.1.2 for Italy</span></span>

<span data-ttu-id="1428b-119">La fatturazione elettronica è basata su [report elettronici](../../dev-itpro/analytics/general-electronic-reporting.md).</span><span class="sxs-lookup"><span data-stu-id="1428b-119">Electronic invoicing is based on [electronic reporting](../../dev-itpro/analytics/general-electronic-reporting.md).</span></span> <span data-ttu-id="1428b-120">Esistono un modello dati **Modello fattura cliente** e una serie di configurazioni di formati di report elettronici specifici di ciascun paese create per Austria (AT), Danimarca (DK), Italia (IT), Norvegia (NO), Spagna (ES), Francia (FR), Belgio (BE) e Paesi Bassi (NL).</span><span class="sxs-lookup"><span data-stu-id="1428b-120">There is a **Customer invoice model** data model and a number of country-specific electronic reporting format configurations created for Austria (AT), Denmark (DK), Italy (IT), Norway (NO), Spain (ES), France (FR), Belgium (BE), and the Netherlands (NL).</span></span>

-   <span data-ttu-id="1428b-121">Fattura vendite OIOUBL - per AT, DK e NO</span><span class="sxs-lookup"><span data-stu-id="1428b-121">OIOUBL Sales invoice - for AT, DK, and NO</span></span>
-   <span data-ttu-id="1428b-122">Nota di accredito OIOUBL - per AT, DK e NO</span><span class="sxs-lookup"><span data-stu-id="1428b-122">OIOUBL Sales credit note - for AT, DK, and NO</span></span>
-   <span data-ttu-id="1428b-123">Fattura di progetto OIOUBL - per AT, DK e NO</span><span class="sxs-lookup"><span data-stu-id="1428b-123">OIOUBL Project invoice - for AT, DK, and NO</span></span>
-   <span data-ttu-id="1428b-124">Nota di accredito di progetto OIOUBL - per AT, DK e NO</span><span class="sxs-lookup"><span data-stu-id="1428b-124">OIOUBL Project credit note - for AT, DK, and NO</span></span>
-   <span data-ttu-id="1428b-125">Fattura di vendita UBL FR</span><span class="sxs-lookup"><span data-stu-id="1428b-125">UBL Sales Invoice FR</span></span>
-   <span data-ttu-id="1428b-126">Nota di accredito vendita UBL FR</span><span class="sxs-lookup"><span data-stu-id="1428b-126">UBL Sales Credit Note FR</span></span>
-   <span data-ttu-id="1428b-127">Fattura di progetto UBL FR</span><span class="sxs-lookup"><span data-stu-id="1428b-127">UBL Project Invoice FR</span></span>
-   <span data-ttu-id="1428b-128">Nota di accredito di progetto UBL FR</span><span class="sxs-lookup"><span data-stu-id="1428b-128">UBL Project Credit Note FR</span></span>
-   <span data-ttu-id="1428b-129">Fattura di vendita UBL BE</span><span class="sxs-lookup"><span data-stu-id="1428b-129">UBL Sales Invoice BE</span></span>
-   <span data-ttu-id="1428b-130">Nota di accredito vendita UBL BE</span><span class="sxs-lookup"><span data-stu-id="1428b-130">UBL Sales Credit Note BE</span></span>
-   <span data-ttu-id="1428b-131">Fattura di progetto UBL BE</span><span class="sxs-lookup"><span data-stu-id="1428b-131">UBL Project Invoice BE</span></span>
-   <span data-ttu-id="1428b-132">Nota di accredito di progetto UBL BE</span><span class="sxs-lookup"><span data-stu-id="1428b-132">UBL Project Credit Note BE</span></span>
-   <span data-ttu-id="1428b-133">Fattura di vendita UBL NL</span><span class="sxs-lookup"><span data-stu-id="1428b-133">UBL Sales Invoice NL</span></span>
-   <span data-ttu-id="1428b-134">Nota di accredito vendita UBL NL</span><span class="sxs-lookup"><span data-stu-id="1428b-134">UBL Sales Credit Note NL</span></span>
-   <span data-ttu-id="1428b-135">Fattura di progetto UBL NL</span><span class="sxs-lookup"><span data-stu-id="1428b-135">UBL Project Invoice NL</span></span>
-   <span data-ttu-id="1428b-136">Nota di accredito di progetto UBL NL</span><span class="sxs-lookup"><span data-stu-id="1428b-136">UBL Project Credit Note NL</span></span> 
-   <span data-ttu-id="1428b-137">Fattura di vendita (ES)</span><span class="sxs-lookup"><span data-stu-id="1428b-137">Sales invoice (ES)</span></span>
-   <span data-ttu-id="1428b-138">Fattura di vendita (IT)</span><span class="sxs-lookup"><span data-stu-id="1428b-138">Sales invoice (IT)</span></span>
-   <span data-ttu-id="1428b-139">Fattura di progetto (ES)</span><span class="sxs-lookup"><span data-stu-id="1428b-139">Project invoice (ES)</span></span>
-   <span data-ttu-id="1428b-140">Fattura di progetto (IT)</span><span class="sxs-lookup"><span data-stu-id="1428b-140">Project invoice (IT)</span></span>

<span data-ttu-id="1428b-141">Le fatture e le note di accredito elettroniche che vengono generate includono informazioni obbligatorie, ad esempio un numero EAN (European Article Numbering), il contatto, il numero del conto dimensione e l'indirizzo dei cliente.</span><span class="sxs-lookup"><span data-stu-id="1428b-141">The electronic invoices and credit notes that you generate include required information, such as a European Article Numbering (EAN) number, contact person, dimension account number, and address information for the customer.</span></span> <span data-ttu-id="1428b-142">Le regole di convalida vengono applicate quando le fatture vengono generate in modo che sia possibile verificare la correttezza delle informazioni immesse.</span><span class="sxs-lookup"><span data-stu-id="1428b-142">Validation rules are applied when invoices are generated so you can verify that the correct information has been entered.</span></span> <span data-ttu-id="1428b-143">Il set di dati necessari può essere diverso da paese a paese.</span><span class="sxs-lookup"><span data-stu-id="1428b-143">The set of required information may differ from country to country.</span></span> <span data-ttu-id="1428b-144">Poiché i requisiti, così come i paesi e i formati supporti, sono soggetti a modifica, è necessario passare alla libreria Risorsa condivisa in Microsoft Dynamics Lifecycle Services (LCS) e visualizzare l'elenco più aggiornato di file disponibili con tipo di risorsa **Configurazione GER**.</span><span class="sxs-lookup"><span data-stu-id="1428b-144">Because the requirements, as well as supported countries and formats, is subject to change, you should always go to the Shared asset library on Microsoft Dynamics Lifecycle services (LCS) and view the most up-to-date list of available files that have an asset type of **GER configuration**.</span></span>

## <a name="additional-information"></a><span data-ttu-id="1428b-145">Informazioni aggiuntive</span><span class="sxs-lookup"><span data-stu-id="1428b-145">Additional information</span></span>
<span data-ttu-id="1428b-146">Per ulteriori informazioni su come impostare le fatture elettroniche, è possibile riprodurre le seguenti [Guide attività](../../fin-and-ops/get-started/help-overview.md#task-guides) nel riquadro della Guida:</span><span class="sxs-lookup"><span data-stu-id="1428b-146">For more details about how to set up electronic invoices, you can play the following [Task guides](../../fin-and-ops/get-started/help-overview.md#task-guides) in the Help pane:</span></span>

 - <span data-ttu-id="1428b-147">Impostare la fatturazione elettronica OIOUBL</span><span class="sxs-lookup"><span data-stu-id="1428b-147">Set up OIOUBL electronic invoicing</span></span>
 - <span data-ttu-id="1428b-148">Importare le configurazioni della fatturazione elettronica OIOUBL</span><span class="sxs-lookup"><span data-stu-id="1428b-148">Import OIOUBL electronic invoicing configurations</span></span>
 - <span data-ttu-id="1428b-149">Impostare gli account cliente per la fatturazione elettronica OIOUBL</span><span class="sxs-lookup"><span data-stu-id="1428b-149">Set up customer accounts for OIOUBL electronic invoicing</span></span>

> [!NOTE] 
> <span data-ttu-id="1428b-150">Sebbene queste Guide attività vengano create per il formato di fatturazione elettronico *OIOUBL* specifico della Danimarca, sono applicabili agli altri paesi supportati con piccole differenze.</span><span class="sxs-lookup"><span data-stu-id="1428b-150">Although these Task guides were created for Danish-specific e-invoice format *OIOUBL*, they are applicable for other supported countries with minor deviations.</span></span>

