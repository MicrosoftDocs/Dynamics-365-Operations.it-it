---
title: Gerarchia organizzativa in Dataverse
description: In questo argomento viene descritta l'integrazione dei dati dell'organizzazione tra le app Finance and Operations e Dataverse.
author: RamaKrishnamoorthy
ms.date: 07/15/2019
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
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: 8b147c27b9309b1b3597f1194c415fbb2e2b7ad2
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5750814"
---
# <a name="organization-hierarchy-in-dataverse"></a><span data-ttu-id="0da42-103">Gerarchia organizzativa in Dataverse</span><span class="sxs-lookup"><span data-stu-id="0da42-103">Organization hierarchy in Dataverse</span></span>

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="0da42-104">Poiché Dynamics 365 Finance è un sistema finanziario, *organizzazione* è un concetto base e l'impostazione del sistema inizia con la configurazione di una gerarchia organizzativa.</span><span class="sxs-lookup"><span data-stu-id="0da42-104">Because Dynamics 365 Finance is a financial system, *organization* is a core concept, and system setup starts with the configuration of an organization hierarchy.</span></span> <span data-ttu-id="0da42-105">I dati finanziari aziendali possono quindi essere tracciati a livello di organizzazione e anche a qualsiasi livello della gerarchia organizzativa.</span><span class="sxs-lookup"><span data-stu-id="0da42-105">Business financials can then be tracked at the organization level and also at any level in the organization hierarchy.</span></span>

<span data-ttu-id="0da42-106">Sebbene In Dataverse non esiste il concetto di una gerarchia organizzativa, vi sono alcuni concetti isolati, come i ricavi di vendita totali.</span><span class="sxs-lookup"><span data-stu-id="0da42-106">Although Dataverse doesn't have the concept of an organization hierarchy, it does have a few loose concepts, such as total sales revenue.</span></span> <span data-ttu-id="0da42-107">Come parte dell'integrazione con Dataverse, , la struttura dati della gerarchia organizzativa viene aggiunta a Dataverse.</span><span class="sxs-lookup"><span data-stu-id="0da42-107">As part of Dataverse integration, the organization hierarchy data structure is added to Dataverse.</span></span>

## <a name="data-flow"></a><span data-ttu-id="0da42-108">Flusso di dati</span><span class="sxs-lookup"><span data-stu-id="0da42-108">Data flow</span></span>

<span data-ttu-id="0da42-109">Un ecosistema aziendale composto dalle app Finance and Operations e Dataverse continuerà a avere una gerarchia organizzativa.</span><span class="sxs-lookup"><span data-stu-id="0da42-109">A business ecosystem that consists of Finance and Operations apps and Dataverse will continue to have an organization hierarchy.</span></span> <span data-ttu-id="0da42-110">Questa gerarchia organizzativa si basa sulle app Finance and Operations, ma viene esposta in Dataverse per scopi di informazione ed estendibilità.</span><span class="sxs-lookup"><span data-stu-id="0da42-110">This organization hierarchy is built on Finance and Operations apps, but it's exposed in Dataverse for informational and extensibility purposes.</span></span> <span data-ttu-id="0da42-111">La figura di seguito mostra le informazioni di gerarchia organizzativa che vengono esposte in Dataverse come flusso di dati unidirezionale dalle app Finance and Operations a Dataverse.</span><span class="sxs-lookup"><span data-stu-id="0da42-111">The following illustration shows the organization hierarchy information that is exposed in Dataverse as a one-way data flow from Finance and Operations apps to Dataverse.</span></span>

![Immagine dell'architettura](media/dual-write-data-flow.png)

<span data-ttu-id="0da42-113">Le mappe della tabella della gerarchia organizzativa sono disponibili per la sincronizzazione unidirezionale dei dati dalle Finance and Operations app a Dataverse.</span><span class="sxs-lookup"><span data-stu-id="0da42-113">Organization hierarchy table maps are available for one-way synchronization of data from Finance and Operations apps to Dataverse.</span></span>

## <a name="templates"></a><span data-ttu-id="0da42-114">Modelli</span><span class="sxs-lookup"><span data-stu-id="0da42-114">Templates</span></span>

<span data-ttu-id="0da42-115">Le informazioni di prodotto contengono tutte le informazioni sul prodotto e sulla relativa definizione, come le dimensioni prodotto o le dimensioni di tracciabilità e di immagazzinamento.</span><span class="sxs-lookup"><span data-stu-id="0da42-115">Product information contains all the information related to the product and its definition, such as the product dimensions or the tracking and storage dimensions.</span></span> <span data-ttu-id="0da42-116">Come mostrato nella tabella seguente, una raccolta di mappe della tabella viene creata per sincronizzare i prodotti e le informazioni correlate.</span><span class="sxs-lookup"><span data-stu-id="0da42-116">As the following table shows, a collection of table maps is created to sync products and related information.</span></span>

<span data-ttu-id="0da42-117">App di Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="0da42-117">Finance and Operations apps</span></span> | <span data-ttu-id="0da42-118">Altre app Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="0da42-118">Other Dynamics 365 apps</span></span> | <span data-ttu-id="0da42-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0da42-119">Description</span></span>
-----------------------|--------------------------------|---
<span data-ttu-id="0da42-120">Scopi gerarchia organizzativa</span><span class="sxs-lookup"><span data-stu-id="0da42-120">Organization hierarchy purposes</span></span> | <span data-ttu-id="0da42-121">msdyn_internalorganizationhierarchypurposes</span><span class="sxs-lookup"><span data-stu-id="0da42-121">msdyn_internalorganizationhierarchypurposes</span></span> | <span data-ttu-id="0da42-122">Questo modello consente la sincronizzazione unidirezionale di tabella scopo gerarchia organizzativa.</span><span class="sxs-lookup"><span data-stu-id="0da42-122">This template provides one-way synchronization of the Organization Hierarchy Purpose table.</span></span>
<span data-ttu-id="0da42-123">Tipo di gerarchia organizzativa</span><span class="sxs-lookup"><span data-stu-id="0da42-123">Organization hierarchy type</span></span> | <span data-ttu-id="0da42-124">msdyn_internalorganizationhierarchytypes</span><span class="sxs-lookup"><span data-stu-id="0da42-124">msdyn_internalorganizationhierarchytypes</span></span> | <span data-ttu-id="0da42-125">Questo modello consente la sincronizzazione unidirezionale di tabella tipo di gerarchia organizzativa.</span><span class="sxs-lookup"><span data-stu-id="0da42-125">This template provides one-way synchronization of the Organization Hierarchy Type table.</span></span>
<span data-ttu-id="0da42-126">Gerarchia organizzativa: pubblicata</span><span class="sxs-lookup"><span data-stu-id="0da42-126">Organization hierarchy - published</span></span> | <span data-ttu-id="0da42-127">msdyn_internalorganizationhierarchies</span><span class="sxs-lookup"><span data-stu-id="0da42-127">msdyn_internalorganizationhierarchies</span></span> | <span data-ttu-id="0da42-128">Questo modello consente la sincronizzazione unidirezionale di tabella gerarchia organizzativa pubblicata.</span><span class="sxs-lookup"><span data-stu-id="0da42-128">This template provides one-way synchronization of the Organization Hierarchy Published table.</span></span>
<span data-ttu-id="0da42-129">Unità operativa</span><span class="sxs-lookup"><span data-stu-id="0da42-129">Operating unit</span></span> | <span data-ttu-id="0da42-130">msdyn_internalorganizations</span><span class="sxs-lookup"><span data-stu-id="0da42-130">msdyn_internalorganizations</span></span> |
<span data-ttu-id="0da42-131">Persone giuridiche</span><span class="sxs-lookup"><span data-stu-id="0da42-131">Legal entities</span></span> | <span data-ttu-id="0da42-132">msdyn_internalorganizations</span><span class="sxs-lookup"><span data-stu-id="0da42-132">msdyn_internalorganizations</span></span> |
<span data-ttu-id="0da42-133">Persone giuridiche</span><span class="sxs-lookup"><span data-stu-id="0da42-133">Legal entities</span></span> | <span data-ttu-id="0da42-134">cdm_companies</span><span class="sxs-lookup"><span data-stu-id="0da42-134">cdm_companies</span></span> | <span data-ttu-id="0da42-135">Fornisce la sincronizzazione bidirezionale delle informazioni della persona giuridica (società).</span><span class="sxs-lookup"><span data-stu-id="0da42-135">Provides bidirectional synchronization of legal entity (company) information.</span></span>

[!include [banner](../../includes/dual-write-symbols.md)]

[!include [Organization hierarchy purposes](includes/OrganizationHierarchyPurpose-msdyn-internalorganizationhierarchypurposes.md)]

[!include [Organization hierarchy type](includes/OrganizationHierarchyType-msdyn-internalorganizationhierarchytypes.md)]

[!include [Organization hierarchy - published](includes/OrganizationHierarchyPublished-msdyn-internalorganizationhierarchies.md)]

## <a name="internal-organization"></a><span data-ttu-id="0da42-136">Organizzazione interna</span><span class="sxs-lookup"><span data-stu-id="0da42-136">Internal Organization</span></span>

<span data-ttu-id="0da42-137">Le informazioni sull'organizzazione interna in Dataverse vengono recuperate da due tabelle, **unità operativa** e **persone giuridiche**.</span><span class="sxs-lookup"><span data-stu-id="0da42-137">Internal organization information in Dataverse comes from two tables, **operating unit** and **legal entities**.</span></span>

[!include [Operating unit](includes/OperatingUnit-msdyn-internalorganizations.md)]

[!include [Legal entities](includes/LegalEntities-msdyn-internalorganizations.md)]

[!include [Legal entities](includes/LegalEntities-Companies.md)]


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]