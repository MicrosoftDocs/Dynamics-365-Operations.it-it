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
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: f502519ba419cb8fa322eb1d22f06d2b805f5f05
ms.sourcegitcommit: afc43699c0edc4ff2be310cb37add2ab586b64c0
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/14/2020
ms.locfileid: "4000736"
---
# <a name="organization-hierarchy-in-common-data-service"></a><span data-ttu-id="38bd3-103">Gerarchia organizzativa in Common Data Service</span><span class="sxs-lookup"><span data-stu-id="38bd3-103">Organization hierarchy in Common Data Service</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="38bd3-104">Poiché Dynamics 365 Finance è un sistema finanziario, *organizzazione* è un concetto base e l'impostazione del sistema inizia con la configurazione di una gerarchia organizzativa.</span><span class="sxs-lookup"><span data-stu-id="38bd3-104">Because Dynamics 365 Finance is a financial system, *organization* is a core concept, and system setup starts with the configuration of an organization hierarchy.</span></span> <span data-ttu-id="38bd3-105">I dati finanziari aziendali possono quindi essere tracciati a livello di organizzazione e anche a qualsiasi livello della gerarchia organizzativa.</span><span class="sxs-lookup"><span data-stu-id="38bd3-105">Business financials can then be tracked at the organization level and also at any level in the organization hierarchy.</span></span>

<span data-ttu-id="38bd3-106">Sebbene In Common Data Service non esiste il concetto di una gerarchia organizzativa, vi sono alcuni concetti isolati, come i ricavi di vendita totali.</span><span class="sxs-lookup"><span data-stu-id="38bd3-106">Although Common Data Service doesn't have the concept of an organization hierarchy, it does have a few loose concepts, such as total sales revenue.</span></span> <span data-ttu-id="38bd3-107">Come parte dell'integrazione con Common Data Service, , la struttura dati della gerarchia organizzativa viene aggiunta a Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="38bd3-107">As part of Common Data Service integration, the organization hierarchy data structure is added to Common Data Service.</span></span>

## <a name="data-flow"></a><span data-ttu-id="38bd3-108">Flusso di dati</span><span class="sxs-lookup"><span data-stu-id="38bd3-108">Data flow</span></span>

<span data-ttu-id="38bd3-109">Un ecosistema aziendale composto dalle app Finance and Operations e Common Data Service continuerà a avere una gerarchia organizzativa.</span><span class="sxs-lookup"><span data-stu-id="38bd3-109">A business ecosystem that consists of Finance and Operations apps and Common Data Service will continue to have an organization hierarchy.</span></span> <span data-ttu-id="38bd3-110">Questa gerarchia organizzativa si basa sulle app Finance and Operations, ma viene esposta in Common Data Service per scopi di informazione ed estendibilità.</span><span class="sxs-lookup"><span data-stu-id="38bd3-110">This organization hierarchy is built on Finance and Operations apps, but it's exposed in Common Data Service for informational and extensibility purposes.</span></span> <span data-ttu-id="38bd3-111">La figura di seguito mostra le informazioni di gerarchia organizzativa che vengono esposte in Common Data Service come flusso di dati unidirezionale dalle app Finance and Operations a Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="38bd3-111">The following illustration shows the organization hierarchy information that is exposed in Common Data Service as a one-way data flow from Finance and Operations apps to Common Data Service.</span></span>

![Immagine dell'architettura](media/dual-write-data-flow.png)

<span data-ttu-id="38bd3-113">Le mappe delle entità della gerarchia organizzativa sono disponibili per la sincronizzazione unidirezionale dei dati dalle app Finance and Operations a Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="38bd3-113">Organization hierarchy entity maps are available for one-way synchronization of data from Finance and Operations apps to Common Data Service.</span></span>

## <a name="templates"></a><span data-ttu-id="38bd3-114">Modelli</span><span class="sxs-lookup"><span data-stu-id="38bd3-114">Templates</span></span>

<span data-ttu-id="38bd3-115">Le informazioni di prodotto contengono tutte le informazioni sul prodotto e sulla relativa definizione, come le dimensioni prodotto o le dimensioni di tracciabilità e di immagazzinamento.</span><span class="sxs-lookup"><span data-stu-id="38bd3-115">Product information contains all the information related to the product and its definition, such as the product dimensions or the tracking and storage dimensions.</span></span> <span data-ttu-id="38bd3-116">Come mostrato nella tabella seguente, una raccolta di mappe di entità viene creata per sincronizzare i prodotti e le informazioni correlate.</span><span class="sxs-lookup"><span data-stu-id="38bd3-116">As the following table shows, a collection of entity maps is created to sync products and related information.</span></span>

<span data-ttu-id="38bd3-117">App di Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="38bd3-117">Finance and Operations apps</span></span> | <span data-ttu-id="38bd3-118">Altre app Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="38bd3-118">Other Dynamics 365 apps</span></span> | <span data-ttu-id="38bd3-119">descrizione</span><span class="sxs-lookup"><span data-stu-id="38bd3-119">Description</span></span>
-----------------------|--------------------------------|---
<span data-ttu-id="38bd3-120">Scopi gerarchia organizzativa</span><span class="sxs-lookup"><span data-stu-id="38bd3-120">Organization hierarchy purposes</span></span> | <span data-ttu-id="38bd3-121">msdyn_internalorganizationhierarchypurposes</span><span class="sxs-lookup"><span data-stu-id="38bd3-121">msdyn_internalorganizationhierarchypurposes</span></span> | <span data-ttu-id="38bd3-122">Questo modello consente la sincronizzazione unidirezionale di entità scopo gerarchia organizzativa.</span><span class="sxs-lookup"><span data-stu-id="38bd3-122">This template provides one-way synchronization of the Organization Hierarchy Purpose entity.</span></span>
<span data-ttu-id="38bd3-123">Tipo di gerarchia organizzativa</span><span class="sxs-lookup"><span data-stu-id="38bd3-123">Organization hierarchy type</span></span> | <span data-ttu-id="38bd3-124">msdyn_internalorganizationhierarchytypes</span><span class="sxs-lookup"><span data-stu-id="38bd3-124">msdyn_internalorganizationhierarchytypes</span></span> | <span data-ttu-id="38bd3-125">Questo modello consente la sincronizzazione unidirezionale di entità tipo di gerarchia organizzativa.</span><span class="sxs-lookup"><span data-stu-id="38bd3-125">This template provides one-way synchronization of the Organization Hierarchy Type entity.</span></span>
<span data-ttu-id="38bd3-126">Gerarchia organizzativa - pubblicata</span><span class="sxs-lookup"><span data-stu-id="38bd3-126">Organization hierarchy - published</span></span> | <span data-ttu-id="38bd3-127">msdyn_internalorganizationhierarchies</span><span class="sxs-lookup"><span data-stu-id="38bd3-127">msdyn_internalorganizationhierarchies</span></span> | <span data-ttu-id="38bd3-128">Questo modello consente la sincronizzazione unidirezionale di entità gerarchia organizzativa pubblicata.</span><span class="sxs-lookup"><span data-stu-id="38bd3-128">This template provides one-way synchronization of the Organization Hierarchy Published entity.</span></span>
<span data-ttu-id="38bd3-129">Unità operativa</span><span class="sxs-lookup"><span data-stu-id="38bd3-129">Operating unit</span></span> | <span data-ttu-id="38bd3-130">msdyn_internalorganizations</span><span class="sxs-lookup"><span data-stu-id="38bd3-130">msdyn_internalorganizations</span></span> |
<span data-ttu-id="38bd3-131">Persone giuridiche</span><span class="sxs-lookup"><span data-stu-id="38bd3-131">Legal entities</span></span> | <span data-ttu-id="38bd3-132">msdyn_internalorganizations</span><span class="sxs-lookup"><span data-stu-id="38bd3-132">msdyn_internalorganizations</span></span> |
<span data-ttu-id="38bd3-133">Persone giuridiche</span><span class="sxs-lookup"><span data-stu-id="38bd3-133">Legal entities</span></span> | <span data-ttu-id="38bd3-134">cdm_companies</span><span class="sxs-lookup"><span data-stu-id="38bd3-134">cdm_companies</span></span> | <span data-ttu-id="38bd3-135">Fornisce la sincronizzazione bidirezionale delle informazioni della persona giuridica (società).</span><span class="sxs-lookup"><span data-stu-id="38bd3-135">Provides bidirectional synchronization of legal entity (company) information.</span></span>

[!include [banner](../../includes/dual-write-symbols.md)]

[!include [Organization hierarchy purposes](includes/OrganizationHierarchyPurpose-msdyn-internalorganizationhierarchypurposes.md)]

[!include [Organization hierarchy type](includes/OrganizationHierarchyType-msdyn-internalorganizationhierarchytypes.md)]

[!include [Organization hierarchy - published](includes/OrganizationHierarchyPublished-msdyn-internalorganizationhierarchies.md)]

## <a name="internal-organization"></a><span data-ttu-id="38bd3-136">Organizzazione interna</span><span class="sxs-lookup"><span data-stu-id="38bd3-136">Internal Organization</span></span>

<span data-ttu-id="38bd3-137">Le informazioni sull'organizzazione interna in Common Data Service vengono recuperate da due entità, **unità operativa** e **persone giuridiche**.</span><span class="sxs-lookup"><span data-stu-id="38bd3-137">Internal organization information in Common Data Service comes from two entities, **operating unit** and **legal entities**.</span></span>

[!include [Operating unit](includes/OperatingUnit-msdyn-internalorganizations.md)]

[!include [Legal entities](includes/LegalEntities-msdyn-internalorganizations.md)]

[!include [Legal entities](includes/LegalEntities-Companies.md)]
