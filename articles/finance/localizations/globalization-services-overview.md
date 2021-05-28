---
title: Servizi di globalizzazione di Dynamics 365
description: In questo argomento viene fornita una panoramica dei servizi di globalizzazione di Microsoft Dynamics 365.
author: JaneA07
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RCS, Regulatory Configuration Services, Localization, Electronic invoicing, Tax calculation
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-02-01
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: 2ef942f7f6dac2c321a51800ade0bf25f2162304
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2021
ms.locfileid: "6018809"
---
# <a name="dynamics-365-globalization-services"></a><span data-ttu-id="24469-103">Servizi di globalizzazione di Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="24469-103">Dynamics 365 globalization services</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="24469-104">I seguenti servizi di globalizzazione possono essere configurati per estendere le funzionalità esistenti in alcuni servizi di Microsoft Dynamics 365 Online:</span><span class="sxs-lookup"><span data-stu-id="24469-104">The following globalization services can be configured to extend the capabilities that exist in some Microsoft Dynamics 365 online services:</span></span>

- <span data-ttu-id="24469-105">**Regulatory Configuration Service (RCS)** supporta la configurazione di diversi tipi di report e documenti elettronici.</span><span class="sxs-lookup"><span data-stu-id="24469-105">**Regulatory Configuration Service (RCS)** supports the configuration of different types of electronic documents and reports.</span></span> <span data-ttu-id="24469-106">RCS fornisce una versione avanzata del designer Creazione di report elettronici (ER) in cui il repository di configurazione è un servizio autonomo.</span><span class="sxs-lookup"><span data-stu-id="24469-106">RCS provides an enhanced version of the Electronic reporting (ER) designer where the configuration repository is a standalone service.</span></span> <span data-ttu-id="24469-107">Per ulteriori informazioni, vedere [Regulatory Configuration Service](rcs-overview.md).</span><span class="sxs-lookup"><span data-stu-id="24469-107">For more information, see [Regulatory Configuration Service](rcs-overview.md).</span></span>
- <span data-ttu-id="24469-108">**Fatturazione elettronica** raggruppa formati configurabili per trasformazioni, firme digitali e integrazioni configurabili per la connettività con servizi Web esterni, inclusa la certificazione e la gestione delle risposte.</span><span class="sxs-lookup"><span data-stu-id="24469-108">**Electronic Invoicing** brings together configurable formats for transformations, digital signatures, and configurable integrations for connectivity with external web services, including certification and response handling.</span></span> <span data-ttu-id="24469-109">Per ulteriori informazioni, vedere [Fatturazione elettronica](e-invoicing-service-overview.md).</span><span class="sxs-lookup"><span data-stu-id="24469-109">For more information, see [Electronic Invoicing](e-invoicing-service-overview.md).</span></span>
- <span data-ttu-id="24469-110">**Calcolo imposte** fornisce una maggiore flessibilità supportando più ID fiscali, determinazione del codice fiscale, designer del calcolo delle imposte e un motore di runtime per conformarsi a normative fiscali complesse in tutto il mondo.</span><span class="sxs-lookup"><span data-stu-id="24469-110">**Tax Calculation** provides enhanced flexibility by supporting multiple tax IDs, tax code determination, the tax calculation designer, and a runtime engine to comply with complex tax regulations worldwide.</span></span> <span data-ttu-id="24469-111">Per ulteriori informazioni, vedere [Calcolo imposte](global-tax-calcuation-service-overview.md).</span><span class="sxs-lookup"><span data-stu-id="24469-111">For more information, see [Tax Calculation](global-tax-calcuation-service-overview.md).</span></span>

<span data-ttu-id="24469-112">Questi servizi di globalizzazione forniscono un'integrazione immediata con i seguenti servizi online di Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="24469-112">These globalization services provide out-of-box integration with the following Dynamics 365 online services.</span></span>

| <span data-ttu-id="24469-113">Servizio online</span><span class="sxs-lookup"><span data-stu-id="24469-113">Online service</span></span> | <span data-ttu-id="24469-114">RCS</span><span class="sxs-lookup"><span data-stu-id="24469-114">RCS</span></span> | <span data-ttu-id="24469-115">Fatturazione elettronica</span><span class="sxs-lookup"><span data-stu-id="24469-115">Electronic Invoicing</span></span> | <span data-ttu-id="24469-116">Calcolo imposte (anteprima)</span><span class="sxs-lookup"><span data-stu-id="24469-116">Tax Calculation (Preview)</span></span> |
|----------------|-----|----------------------|---------------------------|
| <span data-ttu-id="24469-117">Dynamics 365 Finance</span><span class="sxs-lookup"><span data-stu-id="24469-117">Dynamics 365 Finance</span></span> | <span data-ttu-id="24469-118">Sì</span><span class="sxs-lookup"><span data-stu-id="24469-118">Yes</span></span> | <span data-ttu-id="24469-119">Sì</span><span class="sxs-lookup"><span data-stu-id="24469-119">Yes</span></span> | <span data-ttu-id="24469-120">Sì</span><span class="sxs-lookup"><span data-stu-id="24469-120">Yes</span></span> | 
| <span data-ttu-id="24469-121">Dynamics 365 Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="24469-121">Dynamics 365 Supply Chain Management</span></span> | <span data-ttu-id="24469-122">Sì</span><span class="sxs-lookup"><span data-stu-id="24469-122">Yes</span></span> | <span data-ttu-id="24469-123">Sì</span><span class="sxs-lookup"><span data-stu-id="24469-123">Yes</span></span> | <span data-ttu-id="24469-124">Sì</span><span class="sxs-lookup"><span data-stu-id="24469-124">Yes</span></span> | 
| <span data-ttu-id="24469-125">Dynamics 365 Project Operations</span><span class="sxs-lookup"><span data-stu-id="24469-125">Dynamics 365 Project Operations</span></span> | <span data-ttu-id="24469-126">Sì</span><span class="sxs-lookup"><span data-stu-id="24469-126">Yes</span></span> | <span data-ttu-id="24469-127">Sì</span><span class="sxs-lookup"><span data-stu-id="24469-127">Yes</span></span> | <span data-ttu-id="24469-128">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="24469-128">Not applicable</span></span> | 
| <span data-ttu-id="24469-129">Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="24469-129">Dynamics 365 Commerce</span></span> | <span data-ttu-id="24469-130">Sì</span><span class="sxs-lookup"><span data-stu-id="24469-130">Yes</span></span> | <span data-ttu-id="24469-131">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="24469-131">Not applicable</span></span> | <span data-ttu-id="24469-132">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="24469-132">Not applicable</span></span> | 

> [!NOTE]
> <span data-ttu-id="24469-133">A causa delle differenze nella disponibilità delle posizioni geografiche di Azure (aree geografiche) per RCS, la configurazione di questo servizio potrebbe causare il trasferimento dei dati del cliente al di fuori dell'area geografica selezionata per il servizio online Dynamics 365 applicabile.</span><span class="sxs-lookup"><span data-stu-id="24469-133">Because of differences in the availability of Azure geographic locations (geos) for RCS, configuration of this service might cause customer data to be transferred outside the geo that is selected for the applicable Dynamics 365 online service.</span></span> <span data-ttu-id="24469-134">Per ulteriori informazioni, vedere [Dynamics 365 e Power Platform: disponibilità, posizione dei dati, lingua e localizzazione](https://aka.ms/rcs/D365Productavailabilityguide).</span><span class="sxs-lookup"><span data-stu-id="24469-134">For more information, see [Dynamics 365 and Power Platform: Availability, data location, language, and localization](https://aka.ms/rcs/D365Productavailabilityguide).</span></span>