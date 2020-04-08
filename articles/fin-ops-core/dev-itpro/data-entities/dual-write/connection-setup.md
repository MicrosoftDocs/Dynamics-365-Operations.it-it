---
title: Scenari supportati per l'impostazione della doppia scrittura
description: Questo argomento descrive gli scenari supportati per l'impostazione della doppia scrittura.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 01/06/2020
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
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: d7ff514768ee8e4797b591da89e190a855385885
ms.sourcegitcommit: 68f1485de7d64a6c9eba1088af63bd07992d972d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/27/2020
ms.locfileid: "3172856"
---
# <a name="supported-scenarios-for-dual-write-setup"></a><span data-ttu-id="21b28-103">Scenari supportati per l'impostazione della doppia scrittura</span><span class="sxs-lookup"><span data-stu-id="21b28-103">Supported scenarios for dual-write setup</span></span>

[!include [banner](../../includes/banner.md)]

[!include [preview-banner](../../includes/preview-banner.md)]

<span data-ttu-id="21b28-104">È possibile impostare una connessione di doppia scrittura tra un ambiente Finance and Operations e un ambiente Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="21b28-104">You can set up a dual-write connection between a Finance and Operations environment and a Common Data Service environment.</span></span>

+ <span data-ttu-id="21b28-105">Un **ambiente Finance and Operations** fornisce la piattaforma sottostante per le **app Finance and Operations** (ad esempio, Microsoft Dynamics 365 Finance, Dynamics 365 Supply Chain Management, Dynamics 365 Retail e Dynamics 365 Human Resources).</span><span class="sxs-lookup"><span data-stu-id="21b28-105">A **Finance and Operations environment** provides the underlying platform for **Finance and Operations apps** (for example, Microsoft Dynamics 365 Finance, Dynamics 365 Supply Chain Management, Dynamics 365 Retail, and Dynamics 365 Human Resources).</span></span>
+ <span data-ttu-id="21b28-106">Un **ambiente Common Data Service** fornisce la piattaforma sottostante per le **app basate su modello in Dynamics 365** (Dynamics 365 Sales, Dynamics 365 Customer Service, Dynamics 365 Field Service, Dynamics 365 Marketing e Dynamics 365 Project Service Automation).</span><span class="sxs-lookup"><span data-stu-id="21b28-106">A **Common Data Service environment** provides the underlying platform for **model-driven apps in Dynamics 365** (Dynamics 365 Sales, Dynamics 365 Customer Service, Dynamics 365 Field Service, Dynamics 365 Marketing, and Dynamics 365 Project Service Automation).</span></span>

<span data-ttu-id="21b28-107">Il meccanismo di impostazione varia in base alla sottoscrizione e all'ambiente.</span><span class="sxs-lookup"><span data-stu-id="21b28-107">The setup mechanism varies, depending on your subscription and the environment.</span></span>

+ <span data-ttu-id="21b28-108">Per le nuove istanze di app Finance and Operations, la configurazione di una connessione a doppia scrittura inizia in Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="21b28-108">For new instances of Finance and Operations apps, the setup of a dual-write connection begins in Microsoft Dynamics Lifecycle Services (LCS).</span></span> <span data-ttu-id="21b28-109">Se è disponibile una licenza per Microsoft Power Platform, si ottiene uno nuovo ambiente Common Data Service se il tenant ne è privo.</span><span class="sxs-lookup"><span data-stu-id="21b28-109">If you have a license for Microsoft Power Platform, you will get a new Common Data Service environment if your tenant doesn't have one.</span></span>
+ <span data-ttu-id="21b28-110">Per le istanze esistenti di app Finance and Operations, la configurazione di una connessione a doppia scrittura inizia nell'ambiente Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="21b28-110">For existing instances Finance and Operations apps, the setup of a dual-write connection begins in the Finance and Operations environment.</span></span>

<span data-ttu-id="21b28-111">Sono supportati gli scenari di impostazione che seguono:</span><span class="sxs-lookup"><span data-stu-id="21b28-111">The following setup scenarios are supported:</span></span>

+ [<span data-ttu-id="21b28-112">Una nuova istanza di app Finance and Operations e una nuova istanza di app basata su modello</span><span class="sxs-lookup"><span data-stu-id="21b28-112">A new Finance and Operations app instance and a new model-driven app instance</span></span>](#new-new)
+ [<span data-ttu-id="21b28-113">Una nuova istanza di app Finance and Operations e un'istanza di app basata su modello esistente</span><span class="sxs-lookup"><span data-stu-id="21b28-113">A new Finance and Operations app instance and an existing model-driven app instance</span></span>](#new-existing)
+ [<span data-ttu-id="21b28-114">Una nuova istanza di app Finance and Operations con dati dimostrativi e una nuova istanza di app basata su modello</span><span class="sxs-lookup"><span data-stu-id="21b28-114">A new Finance and Operations app instance that has demo data and a new model-driven app instance</span></span>](#new-demo-new)
+ [<span data-ttu-id="21b28-115">Una nuova istanza di app Finance and Operations con dati dimostrativi e un'istanza di app basata su modello esistente</span><span class="sxs-lookup"><span data-stu-id="21b28-115">A new Finance and Operations app instance that has demo data and an existing model-driven app instance</span></span>](#new-demo-existing)
+ [<span data-ttu-id="21b28-116">Un'istanza di app Finance and Operations esistente e un'istanza di app basata su modello nuova o esistente</span><span class="sxs-lookup"><span data-stu-id="21b28-116">An existing Finance and Operations app instance and a new or existing model-driven app instance</span></span>](#existing-existing)

## <a name="a-new-finance-and-operations-app-instance-and-a-new-model-driven-app-instance"></a><a id="new-new"></a><span data-ttu-id="21b28-117">Una nuova istanza di app Finance and Operations e una nuova istanza di app basata su modello</span><span class="sxs-lookup"><span data-stu-id="21b28-117">A new Finance and Operations app instance and a new model-driven app instance</span></span>

<span data-ttu-id="21b28-118">Per impostare una connessione a doppia scrittura tra una nuova istanza di app Finance and Operations che non contiene dati e una nuova istanza di un'app basata su modello in Dynamics 365, seguire i passaggi in [Configurazione della doppia scrittura da Lifecycle Services](lcs-setup.md).</span><span class="sxs-lookup"><span data-stu-id="21b28-118">To set up a dual-write connection between a new instance of a Finance and Operations app that has no data and a new instance of a model-driven app in Dynamics 365, follow the steps in [Dual-write setup from Lifecycle Services](lcs-setup.md).</span></span> <span data-ttu-id="21b28-119">Al termine della configurazione della connessione, si verificano automaticamente le seguenti azioni:</span><span class="sxs-lookup"><span data-stu-id="21b28-119">When the connection setup is completed, the following actions occur automatically:</span></span>

- <span data-ttu-id="21b28-120">Viene eseguito il provisioning di un nuovo ambiente vuoto Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="21b28-120">A new, empty Finance and Operations environment is provisioned.</span></span>
- <span data-ttu-id="21b28-121">Viene eseguito il provisioning di una nuova istanza vuota di un'app basata su modello in cui è installata la soluzione principale CRM.</span><span class="sxs-lookup"><span data-stu-id="21b28-121">A new, empty instance of a model-driven app is provisioned, where the CRM prime solution is installed.</span></span>
- <span data-ttu-id="21b28-122">Viene stabilita una connessione a doppia scrittura per i dati dell'azienda DAT.</span><span class="sxs-lookup"><span data-stu-id="21b28-122">A dual-write connection is established for DAT company data.</span></span>
- <span data-ttu-id="21b28-123">Vengono abilitate le mappe entità per la sincronizzazione in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="21b28-123">Entity maps are enabled for live synchronization.</span></span>

<span data-ttu-id="21b28-124">Entrambi gli ambienti sono quindi pronti per la sincronizzazione dei dati in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="21b28-124">Both environments are then ready for live data synchronization.</span></span>

## <a name="a-new-finance-and-operations-app-instance-and-an-existing-model-driven-app-instance"></a><a id="new-existing"></a><span data-ttu-id="21b28-125">Una nuova istanza di app Finance and Operations e un'istanza di app basata su modello esistente</span><span class="sxs-lookup"><span data-stu-id="21b28-125">A new Finance and Operations app instance and an existing model-driven app instance</span></span>

<span data-ttu-id="21b28-126">Per impostare una connessione a doppia scrittura tra una nuova istanza di app Finance and Operations che non contiene dati e un'istanza di un'app basata su modello esistente in Dynamics 365, seguire i passaggi in [Configurazione della doppia scrittura da Lifecycle Services](lcs-setup.md).</span><span class="sxs-lookup"><span data-stu-id="21b28-126">To set up a dual-write connection between a new instance of a Finance and Operations app that has no data and an existing instance of a model-driven app in Dynamics 365, follow the steps in [Dual-write setup from Lifecycle Services](lcs-setup.md).</span></span> <span data-ttu-id="21b28-127">Al termine della configurazione della connessione, si verificano automaticamente le seguenti azioni:</span><span class="sxs-lookup"><span data-stu-id="21b28-127">When the connection setup is completed, the following actions occur automatically:</span></span>

- <span data-ttu-id="21b28-128">Viene eseguito il provisioning di un nuovo ambiente vuoto Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="21b28-128">A new, empty Finance and Operations environment is provisioned.</span></span>
- <span data-ttu-id="21b28-129">Viene stabilita una connessione a doppia scrittura per i dati dell'azienda DAT.</span><span class="sxs-lookup"><span data-stu-id="21b28-129">A dual-write connection is established for DAT company data.</span></span>
- <span data-ttu-id="21b28-130">Vengono abilitate le mappe entità per la sincronizzazione in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="21b28-130">Entity maps are enabled for live synchronization.</span></span>

<span data-ttu-id="21b28-131">Entrambi gli ambienti sono quindi pronti per la sincronizzazione dei dati in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="21b28-131">Both environments are then ready for live data synchronization.</span></span>

<span data-ttu-id="21b28-132">Per sincronizzare i dati Common Data Service esistenti nell'app Finance and Operations, seguire questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="21b28-132">To sync the existing Common Data Service data to the Finance and Operations app, follow these steps.</span></span>

1. <span data-ttu-id="21b28-133">Creare una nuova società nell'app Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="21b28-133">Create a new company in the Finance and Operations app.</span></span>
2. <span data-ttu-id="21b28-134">Aggiungere la società alla configurazione della connessione a doppia scrittura.</span><span class="sxs-lookup"><span data-stu-id="21b28-134">Add the company to the dual-write connection setup.</span></span>
3. <span data-ttu-id="21b28-135">[Avviare](bootstrap-company-data.md) i dati Common Data Service utilizzando un codice aziendale di tre lettere International Organization for Standardization (ISO).</span><span class="sxs-lookup"><span data-stu-id="21b28-135">[Bootstrap](bootstrap-company-data.md) the Common Data Service data by using a three-letter International Organization for Standardization (ISO) company code.</span></span>

<span data-ttu-id="21b28-136">Poiché la doppia scrittura è in modalità di sincronizzazione in tempo reale, i dati di Common Data Service iniziano automaticamente a essere inviati all'app Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="21b28-136">Because dual-write is in live synchronization mode, the data from Common Data Service automatically starts to flow to the Finance and Operations app.</span></span>

## <a name="a-new-finance-and-operations-app-instance-that-has-demo-data-and-a-new-model-driven-app-instance"></a><a id="new-demo-new"></a><span data-ttu-id="21b28-137">Una nuova istanza di app Finance and Operations con dati dimostrativi e una nuova istanza di app basata su modello</span><span class="sxs-lookup"><span data-stu-id="21b28-137">A new Finance and Operations app instance that has demo data and a new model-driven app instance</span></span>

<span data-ttu-id="21b28-138">Per impostare una connessione a doppia scrittura tra una nuova istanza di app Finance and Operations con dati dimostrativi e una nuova istanza di un'app basata su modello in Dynamics 365, seguire i passaggi nella sezione [Una nuova istanza di app Finance and Operations e una nuova istanza di app basata su modello](#new-new) precedente in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="21b28-138">To set up a dual-write connection between a new instance of a Finance and Operations app that has demo data and a new instance of a model-driven app in Dynamics 365, follow the steps in the [A new Finance and Operations app instance and a new model-driven app instance](#new-new) section earlier in this topic.</span></span> <span data-ttu-id="21b28-139">Al termine della configurazione della connessione, se si desidera sincronizzare i dati dimostrativi con l'app basata su modello, attenersi alla seguente procedura.</span><span class="sxs-lookup"><span data-stu-id="21b28-139">When the connection setup is completed, if you want to sync the demo data to the model-driven app, follow these steps.</span></span>

1. <span data-ttu-id="21b28-140">Aprire l'app Finance and Operations dalla pagina LCS, accedere e passare a **Gestione dati \> Doppia scrittura**.</span><span class="sxs-lookup"><span data-stu-id="21b28-140">Open the Finance and Operations app from the LCS page, sign in, and then go to **Data Management \> Dual-write**.</span></span>
2. <span data-ttu-id="21b28-141">Eseguire la funzionalità **Sincronizzazione iniziale** per le entità per cui si desidera sincronizzare i dati.</span><span class="sxs-lookup"><span data-stu-id="21b28-141">Run the **Initial sync** functionality for the entities that you want to sync data for.</span></span>

## <a name="a-new-finance-and-operations-app-instance-that-has-demo-data-and-an-existing-model-driven-app-instance"></a><a id="new-demo-existing"></a><span data-ttu-id="21b28-142">Una nuova istanza di app Finance and Operations con dati dimostrativi e un'istanza di app basata su modello esistente</span><span class="sxs-lookup"><span data-stu-id="21b28-142">A new Finance and Operations app instance that has demo data and an existing model-driven app instance</span></span>

<span data-ttu-id="21b28-143">Per impostare una connessione a doppia scrittura tra una nuova istanza di app Finance and Operations con dati dimostrativi e un'istanza di un'app basata su modello esistente in Dynamics 365, seguire i passaggi nella sezione [Una nuova istanza di app Finance and Operations e un'istanza di app basata su modello esistente](#new-existing) precedente in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="21b28-143">To set up a dual-write connection between a new instance of a Finance and Operations app that has demo data and an existing instance of a model-driven app in Dynamics 365, follow the steps in the [A new Finance and Operations app instance and an existing model-driven app instance](#new-existing) section earlier in this topic.</span></span> <span data-ttu-id="21b28-144">Al termine della configurazione della connessione, se si desidera sincronizzare i dati dimostrativi con l'app basata su modello, attenersi alla seguente procedura.</span><span class="sxs-lookup"><span data-stu-id="21b28-144">When the connection setup is completed, if you want to sync the demo data to the model-driven app, follow these steps.</span></span>

1. <span data-ttu-id="21b28-145">Aprire l'app Finance and Operations dalla pagina LCS, accedere e passare a **Gestione dati \> Doppia scrittura**.</span><span class="sxs-lookup"><span data-stu-id="21b28-145">Open the Finance and Operations app from the LCS page, sign in, and then go to **Data Management \> Dual-write**.</span></span>
2. <span data-ttu-id="21b28-146">Eseguire la funzionalità **Sincronizzazione iniziale** per le entità per cui si desidera sincronizzare i dati.</span><span class="sxs-lookup"><span data-stu-id="21b28-146">Run the **Initial sync** functionality for the entities that you want to sync data for.</span></span>

<span data-ttu-id="21b28-147">Per sincronizzare i dati Common Data Service esistenti nell'app Finance and Operations, seguire questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="21b28-147">To sync the existing Common Data Service data to the Finance and Operations app, follow these steps.</span></span>

1. <span data-ttu-id="21b28-148">Creare una nuova società nell'app Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="21b28-148">Create a new company in the Finance and Operations app.</span></span>
2. <span data-ttu-id="21b28-149">Aggiungere la società alla configurazione della connessione a doppia scrittura.</span><span class="sxs-lookup"><span data-stu-id="21b28-149">Add the company to the dual-write connection setup.</span></span>
3. <span data-ttu-id="21b28-150">[Avviare](bootstrap-company-data.md) i dati Common Data Service utilizzando un codice aziendale di tre lettere ISO.</span><span class="sxs-lookup"><span data-stu-id="21b28-150">[Bootstrap](bootstrap-company-data.md) the Common Data Service data by using a three-letter ISO company code.</span></span>

<span data-ttu-id="21b28-151">Poiché la doppia scrittura è in modalità di sincronizzazione in tempo reale, i dati di Common Data Service iniziano automaticamente a essere inviati all'app Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="21b28-151">Because dual-write is in live synchronization mode, the data from Common Data Service automatically starts to flow to the Finance and Operations app.</span></span>

## <a name="an-existing-finance-and-operations-app-instance-and-a-new-or-existing-model-driven-app-instance"></a><a id="existing-existing"></a><span data-ttu-id="21b28-152">Un'istanza di app Finance and Operations esistente e un'istanza di app basata su modello nuova o esistente</span><span class="sxs-lookup"><span data-stu-id="21b28-152">An existing Finance and Operations app instance and a new or existing model-driven app instance</span></span>

<span data-ttu-id="21b28-153">L'impostazione di una connessione a doppia scrittura tra un'istanza esistente di un'app Finance and Operations e un'istanza nuova o esistente di un'app basata su modello in Dynamics 365 si verifica nell'ambiente Finance and Operation.</span><span class="sxs-lookup"><span data-stu-id="21b28-153">The setup of a dual-write connection between an existing instance of a Finance and Operations app and a new or existing instance of a model-driven app in Dynamics 365 occurs in the Finance and Operation environment.</span></span>

1. <span data-ttu-id="21b28-154">Impostare la connessione dall'app Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="21b28-154">Set up the connection from the Finance and Operations app.</span></span>
2. <span data-ttu-id="21b28-155">Per sincronizzare i dati Common Data Service esistenti nell'app Finance and Operations, [avviare](bootstrap-company-data.md) i dati Common Data Service utilizzando un codice azienda ISO di tre lettere.</span><span class="sxs-lookup"><span data-stu-id="21b28-155">To sync the existing Common Data Service data to the Finance and Operations app, [bootstrap](bootstrap-company-data.md) the Common Data Service data by using a three-letter ISO company code.</span></span>

<span data-ttu-id="21b28-156">Poiché la doppia scrittura è in modalità di sincronizzazione in tempo reale, i dati di Common Data Service iniziano automaticamente a essere inviati all'app Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="21b28-156">Because dual-write is in live synchronization mode, the data from Common Data Service automatically starts to flow to the Finance and Operations app.</span></span>
