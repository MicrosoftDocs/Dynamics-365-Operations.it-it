---
title: Standard supportati per la fatturazione elettronica in Europa
description: In questo argomento viene descritto il livello di copertura della fatturazione elettronica per l'Europa.
author: mrolecki
ms.date: 11/19/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 10274
ms.search.region: Austria, Denmark, Italy, Norway, Spain, France, Belgium, Netherlands
ms.search.industry: ''
ms.author: mrolecki
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 9aa3e1f6fc14d2c0c8f35307f1084d09399c08f5
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5832710"
---
# <a name="supported-standards-for-electronic-invoicing-in-europe"></a><span data-ttu-id="63fda-103">Standard supportati per la fatturazione elettronica in Europa</span><span class="sxs-lookup"><span data-stu-id="63fda-103">Supported standards for electronic invoicing in Europe</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="63fda-104">In questo argomento viene descritto il livello di copertura della fatturazione elettronica per l'Europa.</span><span class="sxs-lookup"><span data-stu-id="63fda-104">This topic explains the level of coverage that exists for electronic invoicing for Europe.</span></span> 

<span data-ttu-id="63fda-105">L'implementazione e l'adozione della fatturazione elettronica in scala comunitaria europea è disciplinata da [Direttiva del Consiglio 2010/45/UE](https://eur-lex.europa.eu/LexUriServ/LexUriServ.do?uri=OJ:L:2010:189:0001:0008:EN:PDF), che interessa tutti gli stati membri UE.</span><span class="sxs-lookup"><span data-stu-id="63fda-105">Implementation and adoption of European Union-wide electronic invoicing is regulated [Council Directive 2010/45/EU](https://eur-lex.europa.eu/LexUriServ/LexUriServ.do?uri=OJ:L:2010:189:0001:0008:EN:PDF), which affects all EU member states.</span></span> <span data-ttu-id="63fda-106">Le società che desiderano beneficiare della fatturazione elettronica devono inviare fatture di ordini cliente, fatture a testo libero, fatture di progetto, note di accredito ordini cliente e note di accredito delle fatture di progetto come file XML al governo o ad altre parti del settore che richiedono l'utilizzo della fatturazione elettronica.</span><span class="sxs-lookup"><span data-stu-id="63fda-106">Companies that want to benefit from electronic invoicing must submit sales order invoices, free text invoices, project invoices, sales order credit notes, and project invoice credit notes as .xml files to the government or other trading parties that mandate use of electronic invoicing.</span></span> <span data-ttu-id="63fda-107">Questi file XML devono rispondere a determinate regole.</span><span class="sxs-lookup"><span data-stu-id="63fda-107">These .xml files must comply with certain standards.</span></span> <span data-ttu-id="63fda-108">I requisiti specifici di un paese e la relativa implementazione possono differire tra gli stati membri UE, ma normalmente utilizzano sia Universal Business Language ([UBL](https://www.oasis-open.org/committees/tc_home.php?wg_abbrev=ubl)) nelle versioni diverse con personalizzazioni che le specifiche e i punti di accesso [PEPPOL](https://www.peppol.eu) per la convalida e il trasporto.</span><span class="sxs-lookup"><span data-stu-id="63fda-108">The country-specific requirements and their implementation may differ across EU member states but commonly they are using Universal Business Language ([UBL](https://www.oasis-open.org/committees/tc_home.php?wg_abbrev=ubl)) in different versions with customizations as well as [PEPPOL](https://www.peppol.eu) specifications and access points for validation and transportation.</span></span> <span data-ttu-id="63fda-109">Il vantaggio principale dell'UBL è che i documenti aziendali possono essere standardizzati per diversi scopi.</span><span class="sxs-lookup"><span data-stu-id="63fda-109">The primary advantage of UBL is that business documents can be standardized for different purposes.</span></span> <span data-ttu-id="63fda-110">Poiché l'UBL è uno standard internazionale flessibile che supporta numerosi requisiti aziendali, questi documenti aziendali possono essere scambiati tra paesi diversi.</span><span class="sxs-lookup"><span data-stu-id="63fda-110">Because UBL is a flexible, international standard that supports many business requirements, these business documents can be exchanged across national borders.</span></span>

## <a name="electronic-invoice-formats-currently-available-in-dynamics-365-finance"></a><span data-ttu-id="63fda-111">Formati di fattura elettronica sono attualmente disponibili in Dynamics 365 Finance</span><span class="sxs-lookup"><span data-stu-id="63fda-111">Electronic invoice formats currently available in Dynamics 365 Finance</span></span>

<span data-ttu-id="63fda-112">Sono disponibili i seguenti formati di fatture elettroniche specifici di ciascun paese:</span><span class="sxs-lookup"><span data-stu-id="63fda-112">The following country-specific formats of electronic invoices are available:</span></span>

-   <span data-ttu-id="63fda-113">OIOUBL v.2.02 per la Danimarca</span><span class="sxs-lookup"><span data-stu-id="63fda-113">OIOUBL v.2.02 for Denmark</span></span>
-   <span data-ttu-id="63fda-114">EHF v.3.0 per la Norvegia</span><span class="sxs-lookup"><span data-stu-id="63fda-114">EHF v.3.0 for Norway</span></span>
-   <span data-ttu-id="63fda-115">PEPPOL BIS v.2 per Austria, Francia e Belgio</span><span class="sxs-lookup"><span data-stu-id="63fda-115">PEPPOL BIS v.2 for Austria, France, and Belgium</span></span>
-   <span data-ttu-id="63fda-116">UBL-OHNL 1.9 per i Paesi Bassi</span><span class="sxs-lookup"><span data-stu-id="63fda-116">UBL-OHNL 1.9 for the Netherlands</span></span>
-   <span data-ttu-id="63fda-117">FacturaE v.3.2.1 per la Spagna</span><span class="sxs-lookup"><span data-stu-id="63fda-117">FacturaE v.3.2.1 for Spain</span></span>
-   <span data-ttu-id="63fda-118">FatturaPA v.1.2 per l'Italia</span><span class="sxs-lookup"><span data-stu-id="63fda-118">FatturaPA v.1.2 for Italy</span></span>
-   <span data-ttu-id="63fda-119">xRechnung v.1.2 per la Germania</span><span class="sxs-lookup"><span data-stu-id="63fda-119">xRechnung v.1.2 for Germany</span></span>
-   <span data-ttu-id="63fda-120">Aprire PEPPOL BIS Billing v.3.0 per Unione Europea</span><span class="sxs-lookup"><span data-stu-id="63fda-120">Open PEPPOL BIS Billing v.3.0 for European Union</span></span>
-   <span data-ttu-id="63fda-121">Formato specifico estone versione 1.2</span><span class="sxs-lookup"><span data-stu-id="63fda-121">Estonian specific format version 1.2</span></span>
-   <span data-ttu-id="63fda-122">Finvoice 3.0 per la Finlandia</span><span class="sxs-lookup"><span data-stu-id="63fda-122">Finvoice 3.0 for Finland</span></span>

<span data-ttu-id="63fda-123">La fatturazione elettronica è basata sulla [creazione di report elettronici (ER)](../../dev-itpro/analytics/general-electronic-reporting.md).</span><span class="sxs-lookup"><span data-stu-id="63fda-123">Electronic invoicing is based on [Electronic reporting (ER)](../../dev-itpro/analytics/general-electronic-reporting.md).</span></span> <span data-ttu-id="63fda-124">Un modello di dati **Modello di fattura**, un mapping modello di fattura e varie configurazioni di formati di report elettronici (ER) specifici di ciascun paese/area geografica sono state create per i seguenti paesi/aree geografiche:</span><span class="sxs-lookup"><span data-stu-id="63fda-124">An **Invoice model** data model, invoice model mapping, and several country/region-specific ER format configurations have been created for the following countries/regions:</span></span> 

- <span data-ttu-id="63fda-125">Austria (AT)</span><span class="sxs-lookup"><span data-stu-id="63fda-125">Austria (AT)</span></span>
- <span data-ttu-id="63fda-126">Danimarca (DK)</span><span class="sxs-lookup"><span data-stu-id="63fda-126">Denmark (DK)</span></span>
- <span data-ttu-id="63fda-127">Italia (IT)</span><span class="sxs-lookup"><span data-stu-id="63fda-127">Italy (IT)</span></span>
- <span data-ttu-id="63fda-128">Norvegia (NO)</span><span class="sxs-lookup"><span data-stu-id="63fda-128">Norway (NO)</span></span>
- <span data-ttu-id="63fda-129">Spagna (ES)</span><span class="sxs-lookup"><span data-stu-id="63fda-129">Spain (ES)</span></span>
- <span data-ttu-id="63fda-130">Francia (FR)</span><span class="sxs-lookup"><span data-stu-id="63fda-130">France (FR)</span></span>
- <span data-ttu-id="63fda-131">Belgio (BE)</span><span class="sxs-lookup"><span data-stu-id="63fda-131">Belgium (BE)</span></span>
- <span data-ttu-id="63fda-132">Paesi Bassi (NL)</span><span class="sxs-lookup"><span data-stu-id="63fda-132">The Netherlands (NL)</span></span>
- <span data-ttu-id="63fda-133">Germania (DE)</span><span class="sxs-lookup"><span data-stu-id="63fda-133">Germany (DE)</span></span>
- <span data-ttu-id="63fda-134">Estonia (EE)</span><span class="sxs-lookup"><span data-stu-id="63fda-134">Estonia (EE)</span></span>
- <span data-ttu-id="63fda-135">Finlandia (FI)</span><span class="sxs-lookup"><span data-stu-id="63fda-135">Finland (FI)</span></span>
- <span data-ttu-id="63fda-136">Unione Europea (UE)</span><span class="sxs-lookup"><span data-stu-id="63fda-136">The European Union (EU)</span></span>

<span data-ttu-id="63fda-137">Il modello di dati **Modello di fattura**, il mapping di modello di fattura e le configurazioni di formati di report elettronici (ER) specifici di ciascun paese/area geografica includono:</span><span class="sxs-lookup"><span data-stu-id="63fda-137">The **Invoice model** data model, invoice model mapping, and country/region-specific ER format configurations include:</span></span>

-   <span data-ttu-id="63fda-138">Fattura vendite OIOUBL - per AT, DK e NO</span><span class="sxs-lookup"><span data-stu-id="63fda-138">OIOUBL Sales invoice - for AT, DK, and NO</span></span>
-   <span data-ttu-id="63fda-139">Nota di accredito OIOUBL - per AT, DK e NO</span><span class="sxs-lookup"><span data-stu-id="63fda-139">OIOUBL Sales credit note - for AT, DK, and NO</span></span>
-   <span data-ttu-id="63fda-140">Fattura di progetto OIOUBL - per AT, DK e NO</span><span class="sxs-lookup"><span data-stu-id="63fda-140">OIOUBL Project invoice - for AT, DK, and NO</span></span>
-   <span data-ttu-id="63fda-141">Nota di accredito di progetto OIOUBL - per AT, DK e NO</span><span class="sxs-lookup"><span data-stu-id="63fda-141">OIOUBL Project credit note - for AT, DK, and NO</span></span>
-   <span data-ttu-id="63fda-142">Fattura di vendita UBL FR</span><span class="sxs-lookup"><span data-stu-id="63fda-142">UBL Sales Invoice FR</span></span>
-   <span data-ttu-id="63fda-143">Nota di accredito vendita UBL FR</span><span class="sxs-lookup"><span data-stu-id="63fda-143">UBL Sales Credit Note FR</span></span>
-   <span data-ttu-id="63fda-144">Fattura di progetto UBL FR</span><span class="sxs-lookup"><span data-stu-id="63fda-144">UBL Project Invoice FR</span></span>
-   <span data-ttu-id="63fda-145">Nota di accredito di progetto UBL FR</span><span class="sxs-lookup"><span data-stu-id="63fda-145">UBL Project Credit Note FR</span></span>
-   <span data-ttu-id="63fda-146">Fattura di vendita UBL BE</span><span class="sxs-lookup"><span data-stu-id="63fda-146">UBL Sales Invoice BE</span></span>
-   <span data-ttu-id="63fda-147">Nota di accredito vendita UBL BE</span><span class="sxs-lookup"><span data-stu-id="63fda-147">UBL Sales Credit Note BE</span></span>
-   <span data-ttu-id="63fda-148">Fattura di progetto UBL BE</span><span class="sxs-lookup"><span data-stu-id="63fda-148">UBL Project Invoice BE</span></span>
-   <span data-ttu-id="63fda-149">Nota di accredito di progetto UBL BE</span><span class="sxs-lookup"><span data-stu-id="63fda-149">UBL Project Credit Note BE</span></span>
-   <span data-ttu-id="63fda-150">Fattura di vendita UBL NL</span><span class="sxs-lookup"><span data-stu-id="63fda-150">UBL Sales Invoice NL</span></span>
-   <span data-ttu-id="63fda-151">Nota di accredito vendita UBL NL</span><span class="sxs-lookup"><span data-stu-id="63fda-151">UBL Sales Credit Note NL</span></span>
-   <span data-ttu-id="63fda-152">Fattura di progetto UBL NL</span><span class="sxs-lookup"><span data-stu-id="63fda-152">UBL Project Invoice NL</span></span>
-   <span data-ttu-id="63fda-153">Nota di accredito di progetto UBL NL</span><span class="sxs-lookup"><span data-stu-id="63fda-153">UBL Project Credit Note NL</span></span> 
-   <span data-ttu-id="63fda-154">Fattura di vendita (ES)</span><span class="sxs-lookup"><span data-stu-id="63fda-154">Sales invoice (ES)</span></span>
-   <span data-ttu-id="63fda-155">Fattura di vendita (IT)</span><span class="sxs-lookup"><span data-stu-id="63fda-155">Sales invoice (IT)</span></span>
-   <span data-ttu-id="63fda-156">Fattura di progetto (ES)</span><span class="sxs-lookup"><span data-stu-id="63fda-156">Project invoice (ES)</span></span>
-   <span data-ttu-id="63fda-157">Fattura di progetto (IT)</span><span class="sxs-lookup"><span data-stu-id="63fda-157">Project invoice (IT)</span></span>
-   <span data-ttu-id="63fda-158">Fattura di vendita DE</span><span class="sxs-lookup"><span data-stu-id="63fda-158">Sales Invoice DE</span></span>
-   <span data-ttu-id="63fda-159">Fattura progetto DE</span><span class="sxs-lookup"><span data-stu-id="63fda-159">Project Invoice DE</span></span>
-   <span data-ttu-id="63fda-160">Fattura di vendita Peppol - per l'UE</span><span class="sxs-lookup"><span data-stu-id="63fda-160">Peppol Sales Invoice - for EU</span></span>
-   <span data-ttu-id="63fda-161">Nota di credito vendita Peppol - per l'UE</span><span class="sxs-lookup"><span data-stu-id="63fda-161">Peppol Sales Credit Note - for EU</span></span>
-   <span data-ttu-id="63fda-162">Fattura progetto Peppol - per l'UE</span><span class="sxs-lookup"><span data-stu-id="63fda-162">Peppol Project Invoice - for EU</span></span>
-   <span data-ttu-id="63fda-163">Nota di credito progetto Peppol - per l'UE</span><span class="sxs-lookup"><span data-stu-id="63fda-163">Peppol Project Credit Note - for EU</span></span>
-   <span data-ttu-id="63fda-164">Fattura di vendita (EE)</span><span class="sxs-lookup"><span data-stu-id="63fda-164">Sales invoice (EE)</span></span>
-   <span data-ttu-id="63fda-165">Fattura di progetto (EE)</span><span class="sxs-lookup"><span data-stu-id="63fda-165">Project invoice (EE)</span></span>
-   <span data-ttu-id="63fda-166">Fattura di vendita (FI)</span><span class="sxs-lookup"><span data-stu-id="63fda-166">Sales invoice (FI)</span></span>
-   <span data-ttu-id="63fda-167">Fattura di progetto (FI)</span><span class="sxs-lookup"><span data-stu-id="63fda-167">Project invoice (FI)</span></span>

<span data-ttu-id="63fda-168">Le fatture e le note di accredito elettroniche che vengono generate includono informazioni obbligatorie, ad esempio un numero EAN (European Article Numbering), il contatto, il numero del conto dimensione e l'indirizzo dei cliente.</span><span class="sxs-lookup"><span data-stu-id="63fda-168">The electronic invoices and credit notes that you generate include required information, such as a European Article Numbering (EAN) number, contact person, dimension account number, and address information for the customer.</span></span> <span data-ttu-id="63fda-169">Le regole di convalida vengono applicate quando le fatture vengono generate in modo che sia possibile verificare la correttezza delle informazioni immesse.</span><span class="sxs-lookup"><span data-stu-id="63fda-169">Validation rules are applied when invoices are generated so you can verify that the correct information has been entered.</span></span> <span data-ttu-id="63fda-170">Il set di dati necessari può essere diverso da paese a paese.</span><span class="sxs-lookup"><span data-stu-id="63fda-170">The set of required information may differ from country to country.</span></span> <span data-ttu-id="63fda-171">Poiché i requisiti, così come i paesi e i formati supporti, sono soggetti a modifica, è necessario passare alla libreria Risorsa condivisa in Microsoft Dynamics Lifecycle Services (LCS) e visualizzare l'elenco più aggiornato di file disponibili con tipo di risorsa **Configurazione GER**.</span><span class="sxs-lookup"><span data-stu-id="63fda-171">Because the requirements, as well as supported countries and formats, is subject to change, you should always go to the Shared asset library on Microsoft Dynamics Lifecycle Services (LCS) and view the most up-to-date list of available files that have an asset type of **GER configuration**.</span></span>

## <a name="electronic-invoice-configuration"></a><span data-ttu-id="63fda-172">Configurazione fattura elettronica</span><span class="sxs-lookup"><span data-stu-id="63fda-172">Electronic invoice configuration</span></span>
<span data-ttu-id="63fda-173">La configurazione e le specifiche delle fatture elettroniche variano in base al paese/area geografica per cui sono implementate.</span><span class="sxs-lookup"><span data-stu-id="63fda-173">The setup and specifics of electronic invoices depend on the country/region that it's implemented for.</span></span> <span data-ttu-id="63fda-174">Per ulteriori informazioni su come configurare e utilizzare le fatture elettroniche dei clienti, vedere gli argomenti specifici del paese correlati:</span><span class="sxs-lookup"><span data-stu-id="63fda-174">For more information about how to set up and use customer electronic invoices, see the related country-specific topics:</span></span>

- [<span data-ttu-id="63fda-175">Italia</span><span class="sxs-lookup"><span data-stu-id="63fda-175">Italy</span></span>](emea-ita-e-invoices.md)
- [<span data-ttu-id="63fda-176">Norvegia</span><span class="sxs-lookup"><span data-stu-id="63fda-176">Norway</span></span>](emea-nor-e-invoices.md)
- [<span data-ttu-id="63fda-177">Germania</span><span class="sxs-lookup"><span data-stu-id="63fda-177">Germany</span></span>](emea-deu-e-invoices.md)
- [<span data-ttu-id="63fda-178">Finlandia</span><span class="sxs-lookup"><span data-stu-id="63fda-178">Finland</span></span>](https://support.microsoft.com/help/4559937)
- [<span data-ttu-id="63fda-179">Estonia</span><span class="sxs-lookup"><span data-stu-id="63fda-179">Estonia</span></span>](https://support.microsoft.com/help/4552679)
- [<span data-ttu-id="63fda-180">PEPPOL</span><span class="sxs-lookup"><span data-stu-id="63fda-180">PEPPOL</span></span>](https://support.microsoft.com/help/4490320)

## <a name="additional-resources"></a><span data-ttu-id="63fda-181">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="63fda-181">Additional resources</span></span>
<span data-ttu-id="63fda-182">Per ulteriori informazioni su come impostare le fatture elettroniche, è possibile riprodurre le seguenti [Guide attività](../../fin-and-ops/get-started/help-overview.md#task-guides) nel riquadro della Guida:</span><span class="sxs-lookup"><span data-stu-id="63fda-182">For more details about how to set up electronic invoices, you can play the following [Task guides](../../fin-and-ops/get-started/help-overview.md#task-guides) in the Help pane:</span></span>

 - <span data-ttu-id="63fda-183">Impostare la fatturazione elettronica OIOUBL</span><span class="sxs-lookup"><span data-stu-id="63fda-183">Set up OIOUBL electronic invoicing</span></span>
 - <span data-ttu-id="63fda-184">Importare le configurazioni della fatturazione elettronica OIOUBL</span><span class="sxs-lookup"><span data-stu-id="63fda-184">Import OIOUBL electronic invoicing configurations</span></span>
 - <span data-ttu-id="63fda-185">Impostare gli account cliente per la fatturazione elettronica OIOUBL</span><span class="sxs-lookup"><span data-stu-id="63fda-185">Set up customer accounts for OIOUBL electronic invoicing</span></span>

> [!NOTE] 
> <span data-ttu-id="63fda-186">Sebbene queste Guide attività vengano create per il formato di fatturazione elettronico *OIOUBL* specifico della Danimarca, sono applicabili agli altri paesi/aree geografiche supportati con piccole differenze.</span><span class="sxs-lookup"><span data-stu-id="63fda-186">Although these Task guides were created for Danish-specific e-invoice format *OIOUBL*, they are applicable for other supported countries/regions with minor deviations.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]