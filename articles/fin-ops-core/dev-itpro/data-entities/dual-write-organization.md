---
title: Gerarchia organizzativa in Common Data Service
description: In questo argomento viene descritta l'integrazione dei dati organizzativi tra le app Finance and Operations e Common Data Service.
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
ms.openlocfilehash: 9a12ab249129dce24cdca5e29d737fa9f68c0eac
ms.sourcegitcommit: 6e0909e95f38b7487a4b7f68cc62b723f8b59bd4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/10/2019
ms.locfileid: "2572451"
---
# <a name="organization-hierarchy-in-common-data-service"></a><span data-ttu-id="32391-103">Gerarchia organizzativa in Common Data Service</span><span class="sxs-lookup"><span data-stu-id="32391-103">Organization hierarchy in Common Data Service</span></span>

[!include [banner](../includes/banner.md)]

[!include [preview](../includes/preview-banner.md)]

<span data-ttu-id="32391-104">Poiché Dynamics 365 Finance è un sistema finanziario, *organizzazione* è un concetto base e l'impostazione del sistema inizia con la configurazione di una gerarchia organizzativa.</span><span class="sxs-lookup"><span data-stu-id="32391-104">Because Dynamics 365 Finance is a financial system, *organization* is a core concept, and system setup starts with the configuration of an organization hierarchy.</span></span> <span data-ttu-id="32391-105">I dati finanziari aziendali possono quindi essere tracciati a livello di organizzazione e anche a qualsiasi livello della gerarchia organizzativa.</span><span class="sxs-lookup"><span data-stu-id="32391-105">Business financials can then be tracked at the organization level and also at any level in the organization hierarchy.</span></span>

<span data-ttu-id="32391-106">Sebbene In Common Data Service non esiste il concetto di una gerarchia organizzativa, vi sono alcuni concetti isolati, come i ricavi di vendita totali.</span><span class="sxs-lookup"><span data-stu-id="32391-106">Although Common Data Service doesn't have the concept of an organization hierarchy, it does have a few loose concepts, such as total sales revenue.</span></span> <span data-ttu-id="32391-107">Come parte dell'integrazione con Common Data Service, , la struttura dati della gerarchia organizzativa viene aggiunta a Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="32391-107">As part of Common Data Service integration, the organization hierarchy data structure is added to Common Data Service.</span></span>

## <a name="data-flow"></a><span data-ttu-id="32391-108">Flusso di dati</span><span class="sxs-lookup"><span data-stu-id="32391-108">Data flow</span></span>

<span data-ttu-id="32391-109">Un ecosistema aziendale composto dalle app Finance and Operations e Common Data Service continuerà a avere una gerarchia organizzativa.</span><span class="sxs-lookup"><span data-stu-id="32391-109">A business ecosystem that consists of Finance and Operations apps and Common Data Service will continue to have an organization hierarchy.</span></span> <span data-ttu-id="32391-110">Questa gerarchia organizzativa si basa sulle app Finance and Operations, ma viene esposta in Common Data Service per scopi di informazione ed estendibilità.</span><span class="sxs-lookup"><span data-stu-id="32391-110">This organization hierarchy is built on Finance and Operations apps, but it's exposed in Common Data Service for informational and extensibility purposes.</span></span> <span data-ttu-id="32391-111">La figura di seguito mostra le informazioni di gerarchia organizzativa che vengono esposte in Common Data Service come flusso di dati unidirezionale dalle app Finance and Operations a Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="32391-111">The following illustration shows the organization hierarchy information that is exposed in Common Data Service as a one-way data flow from Finance and Operations apps to Common Data Service.</span></span>

![Immagine dell'architettura](media/dual-write-data-flow.png)

## <a name="templates"></a><span data-ttu-id="32391-113">Modelli</span><span class="sxs-lookup"><span data-stu-id="32391-113">Templates</span></span>

<span data-ttu-id="32391-114">Le mappe delle entità della gerarchia organizzativa sono disponibili per la sincronizzazione unidirezionale dei dati dalle app Finance and Operations a Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="32391-114">Organization hierarchy entity maps are available for one-way synchronization of data from Finance and Operations apps to Common Data Service.</span></span>

[!include [banner](../includes/dual-write-symbols.md)]

## <a name="internal-organization-hierarchy-purpose"></a><span data-ttu-id="32391-115">Scopo gerarchia organizzativa interna</span><span class="sxs-lookup"><span data-stu-id="32391-115">Internal Organization Hierarchy Purpose</span></span>

<span data-ttu-id="32391-116">Questo modello consente la sincronizzazione unidirezionale dell'entità Scopo di gerarchia organizzativa da Finance and Operations a altre app Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="32391-116">This template provides one-way synchronization of the Organization Hierarchy Purpose entity from Finance and Operations to other Dynamics 365 apps.</span></span>

<!-- ![architecture image](media/dual-write-purpose.png) -->

<span data-ttu-id="32391-117">Campo di origine</span><span class="sxs-lookup"><span data-stu-id="32391-117">Source field</span></span> | <span data-ttu-id="32391-118">Tipo di mappa</span><span class="sxs-lookup"><span data-stu-id="32391-118">Map type</span></span> | <span data-ttu-id="32391-119">Campo di destinazione</span><span class="sxs-lookup"><span data-stu-id="32391-119">Destination field</span></span>
---|---|---
<span data-ttu-id="32391-120">HIERARCHYTYPE</span><span class="sxs-lookup"><span data-stu-id="32391-120">HIERARCHYTYPE</span></span> | \> | <span data-ttu-id="32391-121">msdyn\_hierarchypurposetypename</span><span class="sxs-lookup"><span data-stu-id="32391-121">msdyn\_hierarchypurposetypename</span></span>
<span data-ttu-id="32391-122">HIERARCHYTYPE</span><span class="sxs-lookup"><span data-stu-id="32391-122">HIERARCHYTYPE</span></span> | \> | <span data-ttu-id="32391-123">msdyn\_hierarchytype.msdyn\_name</span><span class="sxs-lookup"><span data-stu-id="32391-123">msdyn\_hierarchytype.msdyn\_name</span></span>
<span data-ttu-id="32391-124">HIERARCHYPURPOSE</span><span class="sxs-lookup"><span data-stu-id="32391-124">HIERARCHYPURPOSE</span></span> | \>\> | <span data-ttu-id="32391-125">msdyn\_hierarchypurpose</span><span class="sxs-lookup"><span data-stu-id="32391-125">msdyn\_hierarchypurpose</span></span>
<span data-ttu-id="32391-126">IMMUTABLE</span><span class="sxs-lookup"><span data-stu-id="32391-126">IMMUTABLE</span></span> | \>\> | <span data-ttu-id="32391-127">msdyn\_immutable</span><span class="sxs-lookup"><span data-stu-id="32391-127">msdyn\_immutable</span></span>
<span data-ttu-id="32391-128">SETASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="32391-128">SETASDEFAULT</span></span> | \>\> | <span data-ttu-id="32391-129">msdyn\_setasdefault</span><span class="sxs-lookup"><span data-stu-id="32391-129">msdyn\_setasdefault</span></span>

## <a name="internal-organization-hierarchy-type"></a><span data-ttu-id="32391-130">Tipo di gerarchia organizzativa interna</span><span class="sxs-lookup"><span data-stu-id="32391-130">Internal Organization Hierarchy Type</span></span>

<span data-ttu-id="32391-131">Questo modello consente la sincronizzazione unidirezionale dell'entità Tipo di gerarchia organizzativa da Finance and Operations a altre app Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="32391-131">Tihs template provides one-way synchronization of the Organization Hierarchy Type entity from Finance and Operations to other Dynamics 365 apps.</span></span>

<!-- ![architecture image](media/dual-write-type.png) -->

<span data-ttu-id="32391-132">Campo di origine</span><span class="sxs-lookup"><span data-stu-id="32391-132">Source field</span></span> | <span data-ttu-id="32391-133">Tipo di mappa</span><span class="sxs-lookup"><span data-stu-id="32391-133">Map type</span></span> | <span data-ttu-id="32391-134">Campo di destinazione</span><span class="sxs-lookup"><span data-stu-id="32391-134">Destination field</span></span>
---|---|---
<span data-ttu-id="32391-135">NOME</span><span class="sxs-lookup"><span data-stu-id="32391-135">NAME</span></span> | \> | <span data-ttu-id="32391-136">msdyn\_name</span><span class="sxs-lookup"><span data-stu-id="32391-136">msdyn\_name</span></span>

## <a name="internal-organization-hierarchy"></a><span data-ttu-id="32391-137">Gerarchia organizzativa interna</span><span class="sxs-lookup"><span data-stu-id="32391-137">Internal Organization Hierarchy</span></span>

<span data-ttu-id="32391-138">Questo modello consente la sincronizzazione unidirezionale dell'entità Gerarchia organizzativa pubblicata da Finance and Operations a altre app Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="32391-138">This template provides one-way synchronization of the Organization Hierarchy Published entity from Finance and Operations to other Dynamics 365 apps.</span></span>

<!-- ![architecture image](media/dual-write-organization.png) -->

<span data-ttu-id="32391-139">Campo di origine</span><span class="sxs-lookup"><span data-stu-id="32391-139">Source field</span></span> | <span data-ttu-id="32391-140">Tipo di mappa</span><span class="sxs-lookup"><span data-stu-id="32391-140">Map type</span></span> | <span data-ttu-id="32391-141">Campo di destinazione</span><span class="sxs-lookup"><span data-stu-id="32391-141">Destination field</span></span>
---|---|---
<span data-ttu-id="32391-142">VALIDTO</span><span class="sxs-lookup"><span data-stu-id="32391-142">VALIDTO</span></span> | \> | <span data-ttu-id="32391-143">msdyn\_validto</span><span class="sxs-lookup"><span data-stu-id="32391-143">msdyn\_validto</span></span>
<span data-ttu-id="32391-144">VALIDFROM</span><span class="sxs-lookup"><span data-stu-id="32391-144">VALIDFROM</span></span> | \> | <span data-ttu-id="32391-145">msdyn\_validfrom</span><span class="sxs-lookup"><span data-stu-id="32391-145">msdyn\_validfrom</span></span>
<span data-ttu-id="32391-146">HIERARCHYTYPE</span><span class="sxs-lookup"><span data-stu-id="32391-146">HIERARCHYTYPE</span></span> | \> | <span data-ttu-id="32391-147">msdyn\_hierarchytypename</span><span class="sxs-lookup"><span data-stu-id="32391-147">msdyn\_hierarchytypename</span></span>
<span data-ttu-id="32391-148">PARENTORGANIZATIONPARTYNUMBER</span><span class="sxs-lookup"><span data-stu-id="32391-148">PARENTORGANIZATIONPARTYNUMBER</span></span> | \> | <span data-ttu-id="32391-149">msdyn\_parentpartyid</span><span class="sxs-lookup"><span data-stu-id="32391-149">msdyn\_parentpartyid</span></span>
<span data-ttu-id="32391-150">CHILDORGANIZATIONPARTYNUMBER</span><span class="sxs-lookup"><span data-stu-id="32391-150">CHILDORGANIZATIONPARTYNUMBER</span></span> | \> | <span data-ttu-id="32391-151">msdyn\_childpartyid</span><span class="sxs-lookup"><span data-stu-id="32391-151">msdyn\_childpartyid</span></span>
<span data-ttu-id="32391-152">HIERARCHYTYPE</span><span class="sxs-lookup"><span data-stu-id="32391-152">HIERARCHYTYPE</span></span> | \> | <span data-ttu-id="32391-153">msdyn\_hierarchytypeid.msdyn\_name</span><span class="sxs-lookup"><span data-stu-id="32391-153">msdyn\_hierarchytypeid.msdyn\_name</span></span>
<span data-ttu-id="32391-154">CHILDORGANIZATIONPARTYNUMBER</span><span class="sxs-lookup"><span data-stu-id="32391-154">CHILDORGANIZATIONPARTYNUMBER</span></span> | \> | <span data-ttu-id="32391-155">msdyn\_childid.msdyn\_partynumber</span><span class="sxs-lookup"><span data-stu-id="32391-155">msdyn\_childid.msdyn\_partynumber</span></span>
<span data-ttu-id="32391-156">PARENTORGANIZATIONPARTYNUMBER</span><span class="sxs-lookup"><span data-stu-id="32391-156">PARENTORGANIZATIONPARTYNUMBER</span></span> | \> | <span data-ttu-id="32391-157">msdyn\_parentid.msdyn\_partynumber</span><span class="sxs-lookup"><span data-stu-id="32391-157">msdyn\_parentid.msdyn\_partynumber</span></span>

## <a name="internal-organization"></a><span data-ttu-id="32391-158">Organizzazione interna</span><span class="sxs-lookup"><span data-stu-id="32391-158">Internal Organization</span></span>

<span data-ttu-id="32391-159">Le informazioni sull'organizzazione interna in Common Data Service vengono recuperate da due entità, **unità operativa** e **persone giuridiche**.</span><span class="sxs-lookup"><span data-stu-id="32391-159">Internal organization information in Common Data Service comes from two entities, **operating unit** and **legal entities**.</span></span>

<!-- ![architecture image](media/dual-write-operating-unit.png) -->

<!-- ![architecture image](media/dual-write-legal-entities.png) -->

### <a name="operating-unit"></a><span data-ttu-id="32391-160">Unità operativa</span><span class="sxs-lookup"><span data-stu-id="32391-160">Operating unit</span></span>

<span data-ttu-id="32391-161">Campo di origine</span><span class="sxs-lookup"><span data-stu-id="32391-161">Source field</span></span> | <span data-ttu-id="32391-162">Tipo di mappa</span><span class="sxs-lookup"><span data-stu-id="32391-162">Map type</span></span> | <span data-ttu-id="32391-163">Campo di destinazione</span><span class="sxs-lookup"><span data-stu-id="32391-163">Destination field</span></span>
---|---|---
<span data-ttu-id="32391-164">LANGUAGEID</span><span class="sxs-lookup"><span data-stu-id="32391-164">LANGUAGEID</span></span> | \> | <span data-ttu-id="32391-165">msdyn\_languageid</span><span class="sxs-lookup"><span data-stu-id="32391-165">msdyn\_languageid</span></span>
<span data-ttu-id="32391-166">NAMEALIAS</span><span class="sxs-lookup"><span data-stu-id="32391-166">NAMEALIAS</span></span> | \> | <span data-ttu-id="32391-167">msdyn\_namealias</span><span class="sxs-lookup"><span data-stu-id="32391-167">msdyn\_namealias</span></span>
<span data-ttu-id="32391-168">NOME</span><span class="sxs-lookup"><span data-stu-id="32391-168">NAME</span></span> | \> | <span data-ttu-id="32391-169">msdyn\_name</span><span class="sxs-lookup"><span data-stu-id="32391-169">msdyn\_name</span></span>
<span data-ttu-id="32391-170">PARTYNUMBER</span><span class="sxs-lookup"><span data-stu-id="32391-170">PARTYNUMBER</span></span> | \> | <span data-ttu-id="32391-171">msdyn\_partynumber</span><span class="sxs-lookup"><span data-stu-id="32391-171">msdyn\_partynumber</span></span>
<span data-ttu-id="32391-172">OPERATINGUNITTYPE</span><span class="sxs-lookup"><span data-stu-id="32391-172">OPERATINGUNITTYPE</span></span> | \>\> | <span data-ttu-id="32391-173">msdyn\_type</span><span class="sxs-lookup"><span data-stu-id="32391-173">msdyn\_type</span></span>

### <a name="legal-entity"></a><span data-ttu-id="32391-174">Persona giuridica</span><span class="sxs-lookup"><span data-stu-id="32391-174">Legal entity</span></span>

<span data-ttu-id="32391-175">Campo di origine</span><span class="sxs-lookup"><span data-stu-id="32391-175">Source field</span></span> | <span data-ttu-id="32391-176">Tipo di mappa</span><span class="sxs-lookup"><span data-stu-id="32391-176">Map type</span></span> | <span data-ttu-id="32391-177">Campo di destinazione</span><span class="sxs-lookup"><span data-stu-id="32391-177">Destination field</span></span>
---|---|---
<span data-ttu-id="32391-178">NAMEALIAS</span><span class="sxs-lookup"><span data-stu-id="32391-178">NAMEALIAS</span></span> | \> | <span data-ttu-id="32391-179">msdyn\_namealias</span><span class="sxs-lookup"><span data-stu-id="32391-179">msdyn\_namealias</span></span>
<span data-ttu-id="32391-180">LANGUAGEID</span><span class="sxs-lookup"><span data-stu-id="32391-180">LANGUAGEID</span></span> | \> | <span data-ttu-id="32391-181">msdyn\_languageid</span><span class="sxs-lookup"><span data-stu-id="32391-181">msdyn\_languageid</span></span>
<span data-ttu-id="32391-182">NOME</span><span class="sxs-lookup"><span data-stu-id="32391-182">NAME</span></span> | \> | <span data-ttu-id="32391-183">msdyn\_name</span><span class="sxs-lookup"><span data-stu-id="32391-183">msdyn\_name</span></span>
<span data-ttu-id="32391-184">PARTYNUMBER</span><span class="sxs-lookup"><span data-stu-id="32391-184">PARTYNUMBER</span></span> | \> | <span data-ttu-id="32391-185">msdyn\_partynumber</span><span class="sxs-lookup"><span data-stu-id="32391-185">msdyn\_partynumber</span></span>
<span data-ttu-id="32391-186">nessuno</span><span class="sxs-lookup"><span data-stu-id="32391-186">none</span></span> | \>\> | <span data-ttu-id="32391-187">msdyn\_type</span><span class="sxs-lookup"><span data-stu-id="32391-187">msdyn\_type</span></span>
<span data-ttu-id="32391-188">LEGALENTITYID</span><span class="sxs-lookup"><span data-stu-id="32391-188">LEGALENTITYID</span></span> | \> | <span data-ttu-id="32391-189">msdyn\_companycode</span><span class="sxs-lookup"><span data-stu-id="32391-189">msdyn\_companycode</span></span>

## <a name="company"></a><span data-ttu-id="32391-190">Società</span><span class="sxs-lookup"><span data-stu-id="32391-190">Company</span></span>

<span data-ttu-id="32391-191">Fornisce la sincronizzazione bidirezionale delle informazioni sulla persona giuridica (società) tra Finance and Operations e altre app Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="32391-191">Provides bidirectional synchronization of legal entity (company) information between Finance and Operations and other Dynamics 365 apps.</span></span>

<!-- ![architecture image](media/dual-write-company.png) -->

<span data-ttu-id="32391-192">Campo di origine</span><span class="sxs-lookup"><span data-stu-id="32391-192">Source field</span></span> | <span data-ttu-id="32391-193">Tipo di mappa</span><span class="sxs-lookup"><span data-stu-id="32391-193">Map type</span></span> | <span data-ttu-id="32391-194">Campo di destinazione</span><span class="sxs-lookup"><span data-stu-id="32391-194">Destination field</span></span>
---|---|---
<span data-ttu-id="32391-195">NOME</span><span class="sxs-lookup"><span data-stu-id="32391-195">NAME</span></span> | = | <span data-ttu-id="32391-196">cdm\_name</span><span class="sxs-lookup"><span data-stu-id="32391-196">cdm\_name</span></span>
<span data-ttu-id="32391-197">LEGALENTITYID</span><span class="sxs-lookup"><span data-stu-id="32391-197">LEGALENTITYID</span></span> | = | <span data-ttu-id="32391-198">cdm\_companycode</span><span class="sxs-lookup"><span data-stu-id="32391-198">cdm\_companycode</span></span>
