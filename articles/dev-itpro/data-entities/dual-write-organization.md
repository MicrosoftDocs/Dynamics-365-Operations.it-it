---
title: Gerarchia organizzativa in Common Data Service
description: In questo argomento viene descritta l'integrazione dei dati organizzativi tra Finance and Operations e Common Data Service.
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
ms.openlocfilehash: ca2ac0f9dbb8544b12f23a271423a43b0e601272
ms.sourcegitcommit: 02c223b44ac7196df675afac61c6783f467d1983
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/24/2019
ms.locfileid: "1789208"
---
## <a name="organization-hierarchy-in-common-data-service"></a><span data-ttu-id="1cfe1-103">Gerarchia organizzativa in Common Data Service</span><span class="sxs-lookup"><span data-stu-id="1cfe1-103">Organization hierarchy in Common Data Service</span></span>

[!include [banner](../includes/banner.md)]

[!include [preview](../includes/preview-banner.md)]

<span data-ttu-id="1cfe1-104">Poiché Microsoft Dynamics 365 for Finance and Operations è un sistema finanziario, *organizzazione* è un concetto base e l'impostazione del sistema inizia con la configurazione di una gerarchia organizzativa.</span><span class="sxs-lookup"><span data-stu-id="1cfe1-104">Because Microsoft Dynamics 365 for Finance and Operations is a financial system, *organization* is a core concept, and system setup starts with the configuration of an organization hierarchy.</span></span> <span data-ttu-id="1cfe1-105">I dati finanziari e operazioni aziendali possono quindi essere tracciati a livello di organizzazione e anche a qualsiasi livello della gerarchia organizzativa.</span><span class="sxs-lookup"><span data-stu-id="1cfe1-105">Business financials and operations can then be tracked at the organization level and also at any level in the organization hierarchy.</span></span>

<span data-ttu-id="1cfe1-106">Sebbene In Common Data Service non esiste il concetto di una gerarchia organizzativa, vi sono alcuni concetti isolati, come i ricavi di vendita totali.</span><span class="sxs-lookup"><span data-stu-id="1cfe1-106">Although Common Data Service doesn't have the concept of an organization hierarchy, it does have a few loose concepts, such as total sales revenue.</span></span> <span data-ttu-id="1cfe1-107">Come parte dell'integrazione con Common Data Service, , la struttura dati della gerarchia organizzativa viene aggiunta a Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="1cfe1-107">As part of Common Data Service integration, the organization hierarchy data structure is added to Common Data Service.</span></span>

## <a name="data-flow"></a><span data-ttu-id="1cfe1-108">Flusso di dati</span><span class="sxs-lookup"><span data-stu-id="1cfe1-108">Data flow</span></span>

<span data-ttu-id="1cfe1-109">Un ecosistema aziendale composto da Finance and Operations e Common Data Service continuerà a avere una gerarchia organizzativa.</span><span class="sxs-lookup"><span data-stu-id="1cfe1-109">A business ecosystem that consists of Finance and Operations and Common Data Service will continue to have an organization hierarchy.</span></span> <span data-ttu-id="1cfe1-110">Questa gerarchia organizzativa si basa su Finance and Operations, ma viene esposta in Common Data Service per scopi di informazione ed estendibilità.</span><span class="sxs-lookup"><span data-stu-id="1cfe1-110">This organization hierarchy is built on Finance and Operations, but it's exposed in Common Data Service for informational and extensibility purposes.</span></span> <span data-ttu-id="1cfe1-111">La figura di seguito mostra le informazioni di gerarchia organizzativa che vengono esposte in Common Data Service come flusso di dati unidirezionale da Finance and Operations a Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="1cfe1-111">The following illustration shows the organization hierarchy information that is exposed in Common Data Service as a one-way data flow from Finance and Operations to Common Data Service.</span></span>

![Immagine dell'architettura](media/dual-write-data-flow.png)

## <a name="templates"></a><span data-ttu-id="1cfe1-113">Modelli</span><span class="sxs-lookup"><span data-stu-id="1cfe1-113">Templates</span></span>

<span data-ttu-id="1cfe1-114">Le mappe delle entità della gerarchia organizzativa sono disponibili per la sincronizzazione unidirezionale dei dati da Finance and Operations a Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="1cfe1-114">Organization hierarchy entity maps are available for one-way synchronization of data from Finance and Operations to Common Data Service.</span></span>

[!include [banner](../includes/dual-write-symbols.md)]

## <a name="internal-organization-hierarchy-purpose"></a><span data-ttu-id="1cfe1-115">Scopo gerarchia organizzativa interna</span><span class="sxs-lookup"><span data-stu-id="1cfe1-115">Internal Organization Hierarchy Purpose</span></span>

<span data-ttu-id="1cfe1-116">Questo modello consente la sincronizzazione unidirezionale dell'entità Scopo di gerarchia organizzativa da Finance and Operations a Dynamics 365 for Customer Engagement.</span><span class="sxs-lookup"><span data-stu-id="1cfe1-116">This template provides one-way synchronization of the Organization Hierarchy Purpose entity from Finance and Operations to Dynamics 365 for Customer Engagement.</span></span>

<!-- ![architecture image](media/dual-write-purpose.png) -->

<span data-ttu-id="1cfe1-117">Campo di origine</span><span class="sxs-lookup"><span data-stu-id="1cfe1-117">Source field</span></span> | <span data-ttu-id="1cfe1-118">Tipo di mappa</span><span class="sxs-lookup"><span data-stu-id="1cfe1-118">Map type</span></span> | <span data-ttu-id="1cfe1-119">Campo di destinazione</span><span class="sxs-lookup"><span data-stu-id="1cfe1-119">Destination field</span></span>
---|---|---
<span data-ttu-id="1cfe1-120">HIERARCHYTYPE</span><span class="sxs-lookup"><span data-stu-id="1cfe1-120">HIERARCHYTYPE</span></span> | \> | <span data-ttu-id="1cfe1-121">msdyn\_hierarchypurposetypename</span><span class="sxs-lookup"><span data-stu-id="1cfe1-121">msdyn\_hierarchypurposetypename</span></span>
<span data-ttu-id="1cfe1-122">HIERARCHYTYPE</span><span class="sxs-lookup"><span data-stu-id="1cfe1-122">HIERARCHYTYPE</span></span> | \> | <span data-ttu-id="1cfe1-123">msdyn\_hierarchytype.msdyn\_name</span><span class="sxs-lookup"><span data-stu-id="1cfe1-123">msdyn\_hierarchytype.msdyn\_name</span></span>
<span data-ttu-id="1cfe1-124">HIERARCHYPURPOSE</span><span class="sxs-lookup"><span data-stu-id="1cfe1-124">HIERARCHYPURPOSE</span></span> | \>\> | <span data-ttu-id="1cfe1-125">msdyn\_hierarchypurpose</span><span class="sxs-lookup"><span data-stu-id="1cfe1-125">msdyn\_hierarchypurpose</span></span>
<span data-ttu-id="1cfe1-126">IMMUTABLE</span><span class="sxs-lookup"><span data-stu-id="1cfe1-126">IMMUTABLE</span></span> | \>\> | <span data-ttu-id="1cfe1-127">msdyn\_immutable</span><span class="sxs-lookup"><span data-stu-id="1cfe1-127">msdyn\_immutable</span></span>
<span data-ttu-id="1cfe1-128">SETASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="1cfe1-128">SETASDEFAULT</span></span> | \>\> | <span data-ttu-id="1cfe1-129">msdyn\_setasdefault</span><span class="sxs-lookup"><span data-stu-id="1cfe1-129">msdyn\_setasdefault</span></span>

## <a name="internal-organization-hierarchy-type"></a><span data-ttu-id="1cfe1-130">Tipo di gerarchia organizzativa interna</span><span class="sxs-lookup"><span data-stu-id="1cfe1-130">Internal Organization Hierarchy Type</span></span>

<span data-ttu-id="1cfe1-131">Questo modello consente la sincronizzazione unidirezionale dell'entità Tipo di gerarchia organizzativa da Finance and Operations a Customer Engagement.</span><span class="sxs-lookup"><span data-stu-id="1cfe1-131">Tihs template provides one-way synchronization of the Organization Hierarchy Type entity from Finance and Operations to Customer Engagement.</span></span>

<!-- ![architecture image](media/dual-write-type.png) -->

<span data-ttu-id="1cfe1-132">Campo di origine</span><span class="sxs-lookup"><span data-stu-id="1cfe1-132">Source field</span></span> | <span data-ttu-id="1cfe1-133">Tipo di mappa</span><span class="sxs-lookup"><span data-stu-id="1cfe1-133">Map type</span></span> | <span data-ttu-id="1cfe1-134">Campo di destinazione</span><span class="sxs-lookup"><span data-stu-id="1cfe1-134">Destination field</span></span>
---|---|---
<span data-ttu-id="1cfe1-135">NOME</span><span class="sxs-lookup"><span data-stu-id="1cfe1-135">NAME</span></span> | \> | <span data-ttu-id="1cfe1-136">msdyn\_name</span><span class="sxs-lookup"><span data-stu-id="1cfe1-136">msdyn\_name</span></span>

## <a name="internal-organization-hierarchy"></a><span data-ttu-id="1cfe1-137">Gerarchia organizzativa interna</span><span class="sxs-lookup"><span data-stu-id="1cfe1-137">Internal Organization Hierarchy</span></span>

<span data-ttu-id="1cfe1-138">Questo modello consente la sincronizzazione unidirezionale dell'entità Gerarchia organizzativa pubblicata da Finance and Operations a Customer Engagement.</span><span class="sxs-lookup"><span data-stu-id="1cfe1-138">This template provides one-way synchronization of the Organization Hierarchy Published entity from Finance and Operations to Customer Engagement.</span></span>

<!-- ![architecture image](media/dual-write-organization.png) -->

<span data-ttu-id="1cfe1-139">Campo di origine</span><span class="sxs-lookup"><span data-stu-id="1cfe1-139">Source field</span></span> | <span data-ttu-id="1cfe1-140">Tipo di mappa</span><span class="sxs-lookup"><span data-stu-id="1cfe1-140">Map type</span></span> | <span data-ttu-id="1cfe1-141">Campo di destinazione</span><span class="sxs-lookup"><span data-stu-id="1cfe1-141">Destination field</span></span>
---|---|---
<span data-ttu-id="1cfe1-142">VALIDTO</span><span class="sxs-lookup"><span data-stu-id="1cfe1-142">VALIDTO</span></span> | \> | <span data-ttu-id="1cfe1-143">msdyn\_validto</span><span class="sxs-lookup"><span data-stu-id="1cfe1-143">msdyn\_validto</span></span>
<span data-ttu-id="1cfe1-144">VALIDFROM</span><span class="sxs-lookup"><span data-stu-id="1cfe1-144">VALIDFROM</span></span> | \> | <span data-ttu-id="1cfe1-145">msdyn\_validfrom</span><span class="sxs-lookup"><span data-stu-id="1cfe1-145">msdyn\_validfrom</span></span>
<span data-ttu-id="1cfe1-146">HIERARCHYTYPE</span><span class="sxs-lookup"><span data-stu-id="1cfe1-146">HIERARCHYTYPE</span></span> | \> | <span data-ttu-id="1cfe1-147">msdyn\_hierarchytypename</span><span class="sxs-lookup"><span data-stu-id="1cfe1-147">msdyn\_hierarchytypename</span></span>
<span data-ttu-id="1cfe1-148">PARENTORGANIZATIONPARTYNUMBER</span><span class="sxs-lookup"><span data-stu-id="1cfe1-148">PARENTORGANIZATIONPARTYNUMBER</span></span> | \> | <span data-ttu-id="1cfe1-149">msdyn\_parentpartyid</span><span class="sxs-lookup"><span data-stu-id="1cfe1-149">msdyn\_parentpartyid</span></span>
<span data-ttu-id="1cfe1-150">CHILDORGANIZATIONPARTYNUMBER</span><span class="sxs-lookup"><span data-stu-id="1cfe1-150">CHILDORGANIZATIONPARTYNUMBER</span></span> | \> | <span data-ttu-id="1cfe1-151">msdyn\_childpartyid</span><span class="sxs-lookup"><span data-stu-id="1cfe1-151">msdyn\_childpartyid</span></span>
<span data-ttu-id="1cfe1-152">HIERARCHYTYPE</span><span class="sxs-lookup"><span data-stu-id="1cfe1-152">HIERARCHYTYPE</span></span> | \> | <span data-ttu-id="1cfe1-153">msdyn\_hierarchytypeid.msdyn\_name</span><span class="sxs-lookup"><span data-stu-id="1cfe1-153">msdyn\_hierarchytypeid.msdyn\_name</span></span>
<span data-ttu-id="1cfe1-154">CHILDORGANIZATIONPARTYNUMBER</span><span class="sxs-lookup"><span data-stu-id="1cfe1-154">CHILDORGANIZATIONPARTYNUMBER</span></span> | \> | <span data-ttu-id="1cfe1-155">msdyn\_childid.msdyn\_partynumber</span><span class="sxs-lookup"><span data-stu-id="1cfe1-155">msdyn\_childid.msdyn\_partynumber</span></span>
<span data-ttu-id="1cfe1-156">PARENTORGANIZATIONPARTYNUMBER</span><span class="sxs-lookup"><span data-stu-id="1cfe1-156">PARENTORGANIZATIONPARTYNUMBER</span></span> | \> | <span data-ttu-id="1cfe1-157">msdyn\_parentid.msdyn\_partynumber</span><span class="sxs-lookup"><span data-stu-id="1cfe1-157">msdyn\_parentid.msdyn\_partynumber</span></span>

## <a name="internal-organization"></a><span data-ttu-id="1cfe1-158">Organizzazione interna</span><span class="sxs-lookup"><span data-stu-id="1cfe1-158">Internal Organization</span></span>

<span data-ttu-id="1cfe1-159">Le informazioni sull'organizzazione interna in Common Data Service vengono recuperate da due entità di Finance and Operations, **unità operativa** e **persone giuridiche**.</span><span class="sxs-lookup"><span data-stu-id="1cfe1-159">Internal organization information in Common Data Service comes from two Finance and Operations entities, **operating unit** and **legal entities**.</span></span>

<!-- ![architecture image](media/dual-write-operating-unit.png) -->

<!-- ![architecture image](media/dual-write-legal-entities.png) -->

### <a name="operating-unit"></a><span data-ttu-id="1cfe1-160">Unità operativa</span><span class="sxs-lookup"><span data-stu-id="1cfe1-160">Operating unit</span></span>

<span data-ttu-id="1cfe1-161">Campo di origine</span><span class="sxs-lookup"><span data-stu-id="1cfe1-161">Source field</span></span> | <span data-ttu-id="1cfe1-162">Tipo di mappa</span><span class="sxs-lookup"><span data-stu-id="1cfe1-162">Map type</span></span> | <span data-ttu-id="1cfe1-163">Campo di destinazione</span><span class="sxs-lookup"><span data-stu-id="1cfe1-163">Destination field</span></span>
---|---|---
<span data-ttu-id="1cfe1-164">LANGUAGEID</span><span class="sxs-lookup"><span data-stu-id="1cfe1-164">LANGUAGEID</span></span> | \> | <span data-ttu-id="1cfe1-165">msdyn\_languageid</span><span class="sxs-lookup"><span data-stu-id="1cfe1-165">msdyn\_languageid</span></span>
<span data-ttu-id="1cfe1-166">NAMEALIAS</span><span class="sxs-lookup"><span data-stu-id="1cfe1-166">NAMEALIAS</span></span> | \> | <span data-ttu-id="1cfe1-167">msdyn\_namealias</span><span class="sxs-lookup"><span data-stu-id="1cfe1-167">msdyn\_namealias</span></span>
<span data-ttu-id="1cfe1-168">NOME</span><span class="sxs-lookup"><span data-stu-id="1cfe1-168">NAME</span></span> | \> | <span data-ttu-id="1cfe1-169">msdyn\_name</span><span class="sxs-lookup"><span data-stu-id="1cfe1-169">msdyn\_name</span></span>
<span data-ttu-id="1cfe1-170">PARTYNUMBER</span><span class="sxs-lookup"><span data-stu-id="1cfe1-170">PARTYNUMBER</span></span> | \> | <span data-ttu-id="1cfe1-171">msdyn\_partynumber</span><span class="sxs-lookup"><span data-stu-id="1cfe1-171">msdyn\_partynumber</span></span>
<span data-ttu-id="1cfe1-172">OPERATINGUNITTYPE</span><span class="sxs-lookup"><span data-stu-id="1cfe1-172">OPERATINGUNITTYPE</span></span> | \>\> | <span data-ttu-id="1cfe1-173">msdyn\_type</span><span class="sxs-lookup"><span data-stu-id="1cfe1-173">msdyn\_type</span></span>

### <a name="legal-entity"></a><span data-ttu-id="1cfe1-174">Persona giuridica</span><span class="sxs-lookup"><span data-stu-id="1cfe1-174">Legal entity</span></span>

<span data-ttu-id="1cfe1-175">Campo di origine</span><span class="sxs-lookup"><span data-stu-id="1cfe1-175">Source field</span></span> | <span data-ttu-id="1cfe1-176">Tipo di mappa</span><span class="sxs-lookup"><span data-stu-id="1cfe1-176">Map type</span></span> | <span data-ttu-id="1cfe1-177">Campo di destinazione</span><span class="sxs-lookup"><span data-stu-id="1cfe1-177">Destination field</span></span>
---|---|---
<span data-ttu-id="1cfe1-178">NAMEALIAS</span><span class="sxs-lookup"><span data-stu-id="1cfe1-178">NAMEALIAS</span></span> | \> | <span data-ttu-id="1cfe1-179">msdyn\_namealias</span><span class="sxs-lookup"><span data-stu-id="1cfe1-179">msdyn\_namealias</span></span>
<span data-ttu-id="1cfe1-180">LANGUAGEID</span><span class="sxs-lookup"><span data-stu-id="1cfe1-180">LANGUAGEID</span></span> | \> | <span data-ttu-id="1cfe1-181">msdyn\_languageid</span><span class="sxs-lookup"><span data-stu-id="1cfe1-181">msdyn\_languageid</span></span>
<span data-ttu-id="1cfe1-182">NOME</span><span class="sxs-lookup"><span data-stu-id="1cfe1-182">NAME</span></span> | \> | <span data-ttu-id="1cfe1-183">msdyn\_name</span><span class="sxs-lookup"><span data-stu-id="1cfe1-183">msdyn\_name</span></span>
<span data-ttu-id="1cfe1-184">PARTYNUMBER</span><span class="sxs-lookup"><span data-stu-id="1cfe1-184">PARTYNUMBER</span></span> | \> | <span data-ttu-id="1cfe1-185">msdyn\_partynumber</span><span class="sxs-lookup"><span data-stu-id="1cfe1-185">msdyn\_partynumber</span></span>
<span data-ttu-id="1cfe1-186">nessuno</span><span class="sxs-lookup"><span data-stu-id="1cfe1-186">none</span></span> | \>\> | <span data-ttu-id="1cfe1-187">msdyn\_type</span><span class="sxs-lookup"><span data-stu-id="1cfe1-187">msdyn\_type</span></span>
<span data-ttu-id="1cfe1-188">LEGALENTITYID</span><span class="sxs-lookup"><span data-stu-id="1cfe1-188">LEGALENTITYID</span></span> | \> | <span data-ttu-id="1cfe1-189">msdyn\_companycode</span><span class="sxs-lookup"><span data-stu-id="1cfe1-189">msdyn\_companycode</span></span>

## <a name="company"></a><span data-ttu-id="1cfe1-190">Società</span><span class="sxs-lookup"><span data-stu-id="1cfe1-190">Company</span></span>

<span data-ttu-id="1cfe1-191">Fornisce la sincronizzazione bidirezionale delle informazioni sulla persona giuridica (società) tra Finance and Operations e Customer Engagement.</span><span class="sxs-lookup"><span data-stu-id="1cfe1-191">Provides bidirectional synchronization of legal entity (company) information between Finance and Operations and Customer Engagement.</span></span>

<!-- ![architecture image](media/dual-write-company.png) -->

<span data-ttu-id="1cfe1-192">Campo di origine</span><span class="sxs-lookup"><span data-stu-id="1cfe1-192">Source field</span></span> | <span data-ttu-id="1cfe1-193">Tipo di mappa</span><span class="sxs-lookup"><span data-stu-id="1cfe1-193">Map type</span></span> | <span data-ttu-id="1cfe1-194">Campo di destinazione</span><span class="sxs-lookup"><span data-stu-id="1cfe1-194">Destination field</span></span>
---|---|---
<span data-ttu-id="1cfe1-195">NOME</span><span class="sxs-lookup"><span data-stu-id="1cfe1-195">NAME</span></span> | = | <span data-ttu-id="1cfe1-196">cdm\_name</span><span class="sxs-lookup"><span data-stu-id="1cfe1-196">cdm\_name</span></span>
<span data-ttu-id="1cfe1-197">LEGALENTITYID</span><span class="sxs-lookup"><span data-stu-id="1cfe1-197">LEGALENTITYID</span></span> | = | <span data-ttu-id="1cfe1-198">cdm\_companycode</span><span class="sxs-lookup"><span data-stu-id="1cfe1-198">cdm\_companycode</span></span>
