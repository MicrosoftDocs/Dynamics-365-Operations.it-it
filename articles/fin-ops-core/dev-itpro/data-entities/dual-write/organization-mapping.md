---
title: Gerarchia organizzativa in Common Data Service
description: In questo argomento viene descritta l'integrazione dei dati dell'organizzazione tra le app Finance and Operations e Common Data Service.
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
ms.openlocfilehash: fbf7cc33d12fb54d2ff02acc46ba2e284b2a2b3f
ms.sourcegitcommit: 54baab2a04e5c534fc2d1fd67b67e23a152d4e57
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "3019858"
---
# <a name="organization-hierarchy-in-common-data-service"></a><span data-ttu-id="e3f68-103">Gerarchia organizzativa in Common Data Service</span><span class="sxs-lookup"><span data-stu-id="e3f68-103">Organization hierarchy in Common Data Service</span></span>

[!include [banner](../../includes/banner.md)]

[!include [preview-banner](../../includes/preview-banner.md)]

<span data-ttu-id="e3f68-104">Poiché Dynamics 365 Finance è un sistema finanziario, *organizzazione* è un concetto base e l'impostazione del sistema inizia con la configurazione di una gerarchia organizzativa.</span><span class="sxs-lookup"><span data-stu-id="e3f68-104">Because Dynamics 365 Finance is a financial system, *organization* is a core concept, and system setup starts with the configuration of an organization hierarchy.</span></span> <span data-ttu-id="e3f68-105">I dati finanziari aziendali possono quindi essere tracciati a livello di organizzazione e anche a qualsiasi livello della gerarchia organizzativa.</span><span class="sxs-lookup"><span data-stu-id="e3f68-105">Business financials can then be tracked at the organization level and also at any level in the organization hierarchy.</span></span>

<span data-ttu-id="e3f68-106">Sebbene In Common Data Service non esiste il concetto di una gerarchia organizzativa, vi sono alcuni concetti isolati, come i ricavi di vendita totali.</span><span class="sxs-lookup"><span data-stu-id="e3f68-106">Although Common Data Service doesn't have the concept of an organization hierarchy, it does have a few loose concepts, such as total sales revenue.</span></span> <span data-ttu-id="e3f68-107">Come parte dell'integrazione con Common Data Service, , la struttura dati della gerarchia organizzativa viene aggiunta a Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="e3f68-107">As part of Common Data Service integration, the organization hierarchy data structure is added to Common Data Service.</span></span>

## <a name="data-flow"></a><span data-ttu-id="e3f68-108">Flusso di dati</span><span class="sxs-lookup"><span data-stu-id="e3f68-108">Data flow</span></span>

<span data-ttu-id="e3f68-109">Un ecosistema aziendale composto dalle app Finance and Operations e Common Data Service continuerà a avere una gerarchia organizzativa.</span><span class="sxs-lookup"><span data-stu-id="e3f68-109">A business ecosystem that consists of Finance and Operations apps and Common Data Service will continue to have an organization hierarchy.</span></span> <span data-ttu-id="e3f68-110">Questa gerarchia organizzativa si basa sulle app Finance and Operations, ma viene esposta in Common Data Service per scopi di informazione ed estendibilità.</span><span class="sxs-lookup"><span data-stu-id="e3f68-110">This organization hierarchy is built on Finance and Operations apps, but it's exposed in Common Data Service for informational and extensibility purposes.</span></span> <span data-ttu-id="e3f68-111">La figura di seguito mostra le informazioni di gerarchia organizzativa che vengono esposte in Common Data Service come flusso di dati unidirezionale dalle app Finance and Operations a Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="e3f68-111">The following illustration shows the organization hierarchy information that is exposed in Common Data Service as a one-way data flow from Finance and Operations apps to Common Data Service.</span></span>

![Immagine dell'architettura](media/dual-write-data-flow.png)

## <a name="templates"></a><span data-ttu-id="e3f68-113">Modelli</span><span class="sxs-lookup"><span data-stu-id="e3f68-113">Templates</span></span>

<span data-ttu-id="e3f68-114">Le mappe delle entità della gerarchia organizzativa sono disponibili per la sincronizzazione unidirezionale dei dati dalle app Finance and Operations a Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="e3f68-114">Organization hierarchy entity maps are available for one-way synchronization of data from Finance and Operations apps to Common Data Service.</span></span>

## <a name="templates"></a><span data-ttu-id="e3f68-115">Modelli</span><span class="sxs-lookup"><span data-stu-id="e3f68-115">Templates</span></span>

<span data-ttu-id="e3f68-116">Le informazioni di prodotto contengono tutte le informazioni sul prodotto e sulla relativa definizione, come le dimensioni prodotto o le dimensioni di tracciabilità e di immagazzinamento.</span><span class="sxs-lookup"><span data-stu-id="e3f68-116">Product information contains all the information related to the product and its definition, such as the product dimensions or the tracking and storage dimensions.</span></span> <span data-ttu-id="e3f68-117">Come mostrato nella tabella seguente, una raccolta di mappe di entità viene creata per sincronizzare i prodotti e le informazioni correlate.</span><span class="sxs-lookup"><span data-stu-id="e3f68-117">As the following table shows, a collection of entity maps is created to sync products and related information.</span></span>

<span data-ttu-id="e3f68-118">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="e3f68-118">Finance and Operations</span></span> | <span data-ttu-id="e3f68-119">Altre app Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="e3f68-119">Other Dynamics 365 apps</span></span> | <span data-ttu-id="e3f68-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e3f68-120">Description</span></span>
-----------------------|--------------------------------|---
<span data-ttu-id="e3f68-121">Scopi gerarchia organizzativa</span><span class="sxs-lookup"><span data-stu-id="e3f68-121">Organization hierarchy purposes</span></span> | <span data-ttu-id="e3f68-122">msdyn_internalorganizationhierarchypurposes</span><span class="sxs-lookup"><span data-stu-id="e3f68-122">msdyn_internalorganizationhierarchypurposes</span></span> | <span data-ttu-id="e3f68-123">Questo modello consente la sincronizzazione unidirezionale di entità scopo gerarchia organizzativa.</span><span class="sxs-lookup"><span data-stu-id="e3f68-123">This template provides one-way synchronization of the Organization Hierarchy Purpose entity.</span></span>
<span data-ttu-id="e3f68-124">Tipo di gerarchia organizzativa</span><span class="sxs-lookup"><span data-stu-id="e3f68-124">Organization hierarchy type</span></span> | <span data-ttu-id="e3f68-125">msdyn_internalorganizationhierarchytypes</span><span class="sxs-lookup"><span data-stu-id="e3f68-125">msdyn_internalorganizationhierarchytypes</span></span> | <span data-ttu-id="e3f68-126">Questo modello consente la sincronizzazione unidirezionale di entità tipo di gerarchia organizzativa.</span><span class="sxs-lookup"><span data-stu-id="e3f68-126">This template provides one-way synchronization of the Organization Hierarchy Type entity.</span></span>
<span data-ttu-id="e3f68-127">Gerarchia organizzativa - pubblicata</span><span class="sxs-lookup"><span data-stu-id="e3f68-127">Organization hierarchy - published</span></span> | <span data-ttu-id="e3f68-128">msdyn_internalorganizationhierarchies</span><span class="sxs-lookup"><span data-stu-id="e3f68-128">msdyn_internalorganizationhierarchies</span></span> | <span data-ttu-id="e3f68-129">Questo modello consente la sincronizzazione unidirezionale di entità gerarchia organizzativa pubblicata.</span><span class="sxs-lookup"><span data-stu-id="e3f68-129">This template provides one-way synchronization of the Organization Hierarchy Published entity.</span></span>
<span data-ttu-id="e3f68-130">Unità operativa</span><span class="sxs-lookup"><span data-stu-id="e3f68-130">Operating unit</span></span> | <span data-ttu-id="e3f68-131">msdyn_internalorganizations</span><span class="sxs-lookup"><span data-stu-id="e3f68-131">msdyn_internalorganizations</span></span> | 
<span data-ttu-id="e3f68-132">Persone giuridiche</span><span class="sxs-lookup"><span data-stu-id="e3f68-132">Legal entities</span></span> | <span data-ttu-id="e3f68-133">msdyn_internalorganizations</span><span class="sxs-lookup"><span data-stu-id="e3f68-133">msdyn_internalorganizations</span></span> | 
<span data-ttu-id="e3f68-134">Persone giuridiche</span><span class="sxs-lookup"><span data-stu-id="e3f68-134">Legal entities</span></span> | <span data-ttu-id="e3f68-135">cdm_companies</span><span class="sxs-lookup"><span data-stu-id="e3f68-135">cdm_companies</span></span> | <span data-ttu-id="e3f68-136">Fornisce la sincronizzazione bidirezionale delle informazioni della persona giuridica (società).</span><span class="sxs-lookup"><span data-stu-id="e3f68-136">Provides bidirectional synchronization of legal entity (company) information.</span></span>


[!include [banner](../../includes/dual-write-symbols.md)]

[!include [Organization hierarchy purposes](includes/OrganizationHierarchyPurpose-msdyn-internalorganizationhierarchypurposes.md)]

[!include [Organization hierarchy type](includes/OrganizationHierarchyType-msdyn-internalorganizationhierarchytypes.md)]

[!include [Organization hierarchy - published](includes/OrganizationHierarchyPublished-msdyn-internalorganizationhierarchies.md)]

## <a name="internal-organization"></a><span data-ttu-id="e3f68-137">Organizzazione interna</span><span class="sxs-lookup"><span data-stu-id="e3f68-137">Internal Organization</span></span>

<span data-ttu-id="e3f68-138">Le informazioni sull'organizzazione interna in Common Data Service vengono recuperate da due entità, **unità operativa** e **persone giuridiche**.</span><span class="sxs-lookup"><span data-stu-id="e3f68-138">Internal organization information in Common Data Service comes from two entities, **operating unit** and **legal entities**.</span></span>

[!include [Operating unit](includes/OperatingUnit-msdyn-internalorganizations.md)]

[!include [Legal entities](includes/LegalEntities-msdyn-internalorganizations.md)]

[!include [Legal entities](includes/LegalEntities-Companies.md)]
