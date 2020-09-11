---
title: Scenari supportati per l'impostazione della doppia scrittura
description: Questo argomento descrive gli scenari supportati per l'impostazione della doppia scrittura.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 08/17/2020
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
ms.openlocfilehash: 275d24d8f32fd1d2d15356d14c5c6591e8503c65
ms.sourcegitcommit: ec4df354602c20f48f8581bfe5be0c04c66d2927
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/19/2020
ms.locfileid: "3706254"
---
# <a name="supported-scenarios-for-dual-write-setup"></a><span data-ttu-id="b1fa0-103">Scenari supportati per l'impostazione della doppia scrittura</span><span class="sxs-lookup"><span data-stu-id="b1fa0-103">Supported scenarios for dual-write setup</span></span>

[!include [banner](../../includes/banner.md)]

[!include [preview-banner](../../includes/preview-banner.md)]

<span data-ttu-id="b1fa0-104">È possibile impostare una connessione di doppia scrittura tra un ambiente Finance and Operations e un ambiente Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="b1fa0-104">You can set up a dual-write connection between a Finance and Operations environment and a Common Data Service environment.</span></span>

+ <span data-ttu-id="b1fa0-105">Un **ambiente Finance and Operations** fornisce la piattaforma sottostante per le **app Finance and Operations** (ad esempio Microsoft Dynamics 365 Finance, Dynamics 365 Supply Chain Management e Dynamics 365 Retail).</span><span class="sxs-lookup"><span data-stu-id="b1fa0-105">A **Finance and Operations environment** provides the underlying platform for **Finance and Operations apps** (for example, Microsoft Dynamics 365 Finance, Dynamics 365 Supply Chain Management, and Dynamics 365 Retail).</span></span>
+ <span data-ttu-id="b1fa0-106">Un **ambiente Common Data Service** fornisce la piattaforma sottostante per le **app basate su modello in Dynamics 365** (Dynamics 365 Sales, Dynamics 365 Customer Service, Dynamics 365 Field Service, Dynamics 365 Marketing e Dynamics 365 Project Service Automation).</span><span class="sxs-lookup"><span data-stu-id="b1fa0-106">A **Common Data Service environment** provides the underlying platform for **model-driven apps in Dynamics 365** (Dynamics 365 Sales, Dynamics 365 Customer Service, Dynamics 365 Field Service, Dynamics 365 Marketing, and Dynamics 365 Project Service Automation).</span></span>

>[!IMPORTANT]
><span data-ttu-id="b1fa0-107">Human Resources in Finance and Operations supporta le connessioni a doppia scrittura, al contrario dell'app Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="b1fa0-107">Human Resources in Finance and Operations supports dual-write connections, but the Dynamics 365 Human Resources app doesn't.</span></span>

<span data-ttu-id="b1fa0-108">Il meccanismo di impostazione varia in base alla sottoscrizione e all'ambiente.</span><span class="sxs-lookup"><span data-stu-id="b1fa0-108">The setup mechanism varies, depending on your subscription and the environment.</span></span>

+ <span data-ttu-id="b1fa0-109">Per le nuove istanze di app Finance and Operations, la configurazione di una connessione a doppia scrittura inizia in Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="b1fa0-109">For new instances of Finance and Operations apps, the setup of a dual-write connection begins in Microsoft Dynamics Lifecycle Services (LCS).</span></span> <span data-ttu-id="b1fa0-110">Se è disponibile una licenza per Microsoft Power Platform, si ottiene uno nuovo ambiente Common Data Service se il tenant ne è privo.</span><span class="sxs-lookup"><span data-stu-id="b1fa0-110">If you have a license for Microsoft Power Platform, you will get a new Common Data Service environment if your tenant doesn't have one.</span></span>
+ <span data-ttu-id="b1fa0-111">Per le istanze esistenti di app Finance and Operations, la configurazione di una connessione a doppia scrittura inizia nell'ambiente Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="b1fa0-111">For existing instances Finance and Operations apps, the setup of a dual-write connection begins in the Finance and Operations environment.</span></span>

<span data-ttu-id="b1fa0-112">Sono supportati gli scenari di impostazione che seguono:</span><span class="sxs-lookup"><span data-stu-id="b1fa0-112">The following setup scenarios are supported:</span></span>

+ [<span data-ttu-id="b1fa0-113">Una nuova istanza di app Finance and Operations e una nuova istanza di app basata su modello</span><span class="sxs-lookup"><span data-stu-id="b1fa0-113">A new Finance and Operations app instance and a new model-driven app instance</span></span>](#new-new)
+ [<span data-ttu-id="b1fa0-114">Una nuova istanza di app Finance and Operations e un'istanza di app basata su modello esistente</span><span class="sxs-lookup"><span data-stu-id="b1fa0-114">A new Finance and Operations app instance and an existing model-driven app instance</span></span>](#new-existing)
+ [<span data-ttu-id="b1fa0-115">Una nuova istanza di app Finance and Operations con dati dimostrativi e una nuova istanza di app basata su modello</span><span class="sxs-lookup"><span data-stu-id="b1fa0-115">A new Finance and Operations app instance that has demo data and a new model-driven app instance</span></span>](#new-demo-new)
+ [<span data-ttu-id="b1fa0-116">Una nuova istanza di app Finance and Operations con dati dimostrativi e un'istanza di app basata su modello esistente</span><span class="sxs-lookup"><span data-stu-id="b1fa0-116">A new Finance and Operations app instance that has demo data and an existing model-driven app instance</span></span>](#new-demo-existing)
+ [<span data-ttu-id="b1fa0-117">Un'istanza di app Finance and Operations esistente e un'istanza di app basata su modello nuova o esistente</span><span class="sxs-lookup"><span data-stu-id="b1fa0-117">An existing Finance and Operations app instance and a new or existing model-driven app instance</span></span>](#existing-existing)

## <a name="a-new-finance-and-operations-app-instance-and-a-new-model-driven-app-instance"></a><a id="new-new"></a><span data-ttu-id="b1fa0-118">Una nuova istanza di app Finance and Operations e una nuova istanza di app basata su modello</span><span class="sxs-lookup"><span data-stu-id="b1fa0-118">A new Finance and Operations app instance and a new model-driven app instance</span></span>

<span data-ttu-id="b1fa0-119">Per impostare una connessione a doppia scrittura tra una nuova istanza di app Finance and Operations che non contiene dati e una nuova istanza di un'app basata su modello in Dynamics 365, seguire i passaggi in [Configurazione della doppia scrittura da Lifecycle Services](lcs-setup.md).</span><span class="sxs-lookup"><span data-stu-id="b1fa0-119">To set up a dual-write connection between a new instance of a Finance and Operations app that has no data and a new instance of a model-driven app in Dynamics 365, follow the steps in [Dual-write setup from Lifecycle Services](lcs-setup.md).</span></span> <span data-ttu-id="b1fa0-120">Al termine della configurazione della connessione, si verificano automaticamente le seguenti azioni:</span><span class="sxs-lookup"><span data-stu-id="b1fa0-120">When the connection setup is completed, the following actions occur automatically:</span></span>

- <span data-ttu-id="b1fa0-121">Viene eseguito il provisioning di un nuovo ambiente vuoto Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="b1fa0-121">A new, empty Finance and Operations environment is provisioned.</span></span>
- <span data-ttu-id="b1fa0-122">Viene eseguito il provisioning di una nuova istanza vuota di un'app basata su modello in cui è installata la soluzione principale CRM.</span><span class="sxs-lookup"><span data-stu-id="b1fa0-122">A new, empty instance of a model-driven app is provisioned, where the CRM prime solution is installed.</span></span>
- <span data-ttu-id="b1fa0-123">Viene stabilita una connessione a doppia scrittura per i dati dell'azienda DAT.</span><span class="sxs-lookup"><span data-stu-id="b1fa0-123">A dual-write connection is established for DAT company data.</span></span>
- <span data-ttu-id="b1fa0-124">Vengono abilitate le mappe entità per la sincronizzazione in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="b1fa0-124">Entity maps are enabled for live synchronization.</span></span>

<span data-ttu-id="b1fa0-125">Entrambi gli ambienti sono quindi pronti per la sincronizzazione dei dati in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="b1fa0-125">Both environments are then ready for live data synchronization.</span></span>

## <a name="a-new-finance-and-operations-app-instance-and-an-existing-model-driven-app-instance"></a><a id="new-existing"></a><span data-ttu-id="b1fa0-126">Una nuova istanza di app Finance and Operations e un'istanza di app basata su modello esistente</span><span class="sxs-lookup"><span data-stu-id="b1fa0-126">A new Finance and Operations app instance and an existing model-driven app instance</span></span>

<span data-ttu-id="b1fa0-127">Per impostare una connessione a doppia scrittura tra una nuova istanza di app Finance and Operations che non contiene dati e un'istanza di un'app basata su modello esistente in Dynamics 365, seguire i passaggi in [Configurazione della doppia scrittura da Lifecycle Services](lcs-setup.md).</span><span class="sxs-lookup"><span data-stu-id="b1fa0-127">To set up a dual-write connection between a new instance of a Finance and Operations app that has no data and an existing instance of a model-driven app in Dynamics 365, follow the steps in [Dual-write setup from Lifecycle Services](lcs-setup.md).</span></span> <span data-ttu-id="b1fa0-128">Al termine della configurazione della connessione, si verificano automaticamente le seguenti azioni:</span><span class="sxs-lookup"><span data-stu-id="b1fa0-128">When the connection setup is completed, the following actions occur automatically:</span></span>

- <span data-ttu-id="b1fa0-129">Viene eseguito il provisioning di un nuovo ambiente vuoto Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="b1fa0-129">A new, empty Finance and Operations environment is provisioned.</span></span>
- <span data-ttu-id="b1fa0-130">Viene stabilita una connessione a doppia scrittura per i dati dell'azienda DAT.</span><span class="sxs-lookup"><span data-stu-id="b1fa0-130">A dual-write connection is established for DAT company data.</span></span>
- <span data-ttu-id="b1fa0-131">Vengono abilitate le mappe entità per la sincronizzazione in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="b1fa0-131">Entity maps are enabled for live synchronization.</span></span>

<span data-ttu-id="b1fa0-132">Entrambi gli ambienti sono quindi pronti per la sincronizzazione dei dati in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="b1fa0-132">Both environments are then ready for live data synchronization.</span></span>

<span data-ttu-id="b1fa0-133">Per sincronizzare i dati Common Data Service esistenti nell'app Finance and Operations, seguire questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="b1fa0-133">To sync the existing Common Data Service data to the Finance and Operations app, follow these steps.</span></span>

1. <span data-ttu-id="b1fa0-134">Creare una nuova società nell'app Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="b1fa0-134">Create a new company in the Finance and Operations app.</span></span>
2. <span data-ttu-id="b1fa0-135">Aggiungere la società alla configurazione della connessione a doppia scrittura.</span><span class="sxs-lookup"><span data-stu-id="b1fa0-135">Add the company to the dual-write connection setup.</span></span>
3. <span data-ttu-id="b1fa0-136">[Avviare](bootstrap-company-data.md) i dati Common Data Service utilizzando un codice aziendale di tre lettere International Organization for Standardization (ISO).</span><span class="sxs-lookup"><span data-stu-id="b1fa0-136">[Bootstrap](bootstrap-company-data.md) the Common Data Service data by using a three-letter International Organization for Standardization (ISO) company code.</span></span>

<span data-ttu-id="b1fa0-137">Poiché la doppia scrittura è in modalità di sincronizzazione in tempo reale, i dati di Common Data Service iniziano automaticamente a essere inviati all'app Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="b1fa0-137">Because dual-write is in live synchronization mode, the data from Common Data Service automatically starts to flow to the Finance and Operations app.</span></span>

## <a name="a-new-finance-and-operations-app-instance-that-has-demo-data-and-a-new-model-driven-app-instance"></a><a id="new-demo-new"></a><span data-ttu-id="b1fa0-138">Una nuova istanza di app Finance and Operations con dati dimostrativi e una nuova istanza di app basata su modello</span><span class="sxs-lookup"><span data-stu-id="b1fa0-138">A new Finance and Operations app instance that has demo data and a new model-driven app instance</span></span>

<span data-ttu-id="b1fa0-139">Per impostare una connessione a doppia scrittura tra una nuova istanza di app Finance and Operations con dati dimostrativi e una nuova istanza di un'app basata su modello in Dynamics 365, seguire i passaggi nella sezione [Una nuova istanza di app Finance and Operations e una nuova istanza di app basata su modello](#new-new) precedente in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="b1fa0-139">To set up a dual-write connection between a new instance of a Finance and Operations app that has demo data and a new instance of a model-driven app in Dynamics 365, follow the steps in the [A new Finance and Operations app instance and a new model-driven app instance](#new-new) section earlier in this topic.</span></span> <span data-ttu-id="b1fa0-140">Al termine della configurazione della connessione, se si desidera sincronizzare i dati dimostrativi con l'app basata su modello, attenersi alla seguente procedura.</span><span class="sxs-lookup"><span data-stu-id="b1fa0-140">When the connection setup is completed, if you want to sync the demo data to the model-driven app, follow these steps.</span></span>

1. <span data-ttu-id="b1fa0-141">Aprire l'app Finance and Operations dalla pagina LCS, accedere e passare a **Gestione dati \> Doppia scrittura**.</span><span class="sxs-lookup"><span data-stu-id="b1fa0-141">Open the Finance and Operations app from the LCS page, sign in, and then go to **Data Management \> Dual-write**.</span></span>
2. <span data-ttu-id="b1fa0-142">Eseguire la funzionalità **Sincronizzazione iniziale** per le entità per cui si desidera sincronizzare i dati.</span><span class="sxs-lookup"><span data-stu-id="b1fa0-142">Run the **Initial sync** functionality for the entities that you want to sync data for.</span></span>

## <a name="a-new-finance-and-operations-app-instance-that-has-demo-data-and-an-existing-model-driven-app-instance"></a><a id="new-demo-existing"></a><span data-ttu-id="b1fa0-143">Una nuova istanza di app Finance and Operations con dati dimostrativi e un'istanza di app basata su modello esistente</span><span class="sxs-lookup"><span data-stu-id="b1fa0-143">A new Finance and Operations app instance that has demo data and an existing model-driven app instance</span></span>

<span data-ttu-id="b1fa0-144">Per impostare una connessione a doppia scrittura tra una nuova istanza di app Finance and Operations con dati dimostrativi e un'istanza di un'app basata su modello esistente in Dynamics 365, seguire i passaggi nella sezione [Una nuova istanza di app Finance and Operations e un'istanza di app basata su modello esistente](#new-existing) precedente in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="b1fa0-144">To set up a dual-write connection between a new instance of a Finance and Operations app that has demo data and an existing instance of a model-driven app in Dynamics 365, follow the steps in the [A new Finance and Operations app instance and an existing model-driven app instance](#new-existing) section earlier in this topic.</span></span> <span data-ttu-id="b1fa0-145">Al termine della configurazione della connessione, se si desidera sincronizzare i dati dimostrativi con l'app basata su modello, attenersi alla seguente procedura.</span><span class="sxs-lookup"><span data-stu-id="b1fa0-145">When the connection setup is completed, if you want to sync the demo data to the model-driven app, follow these steps.</span></span>

1. <span data-ttu-id="b1fa0-146">Aprire l'app Finance and Operations dalla pagina LCS, accedere e passare a **Gestione dati \> Doppia scrittura**.</span><span class="sxs-lookup"><span data-stu-id="b1fa0-146">Open the Finance and Operations app from the LCS page, sign in, and then go to **Data Management \> Dual-write**.</span></span>
2. <span data-ttu-id="b1fa0-147">Eseguire la funzionalità **Sincronizzazione iniziale** per le entità per cui si desidera sincronizzare i dati.</span><span class="sxs-lookup"><span data-stu-id="b1fa0-147">Run the **Initial sync** functionality for the entities that you want to sync data for.</span></span>

<span data-ttu-id="b1fa0-148">Per sincronizzare i dati Common Data Service esistenti nell'app Finance and Operations, seguire questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="b1fa0-148">To sync the existing Common Data Service data to the Finance and Operations app, follow these steps.</span></span>

1. <span data-ttu-id="b1fa0-149">Creare una nuova società nell'app Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="b1fa0-149">Create a new company in the Finance and Operations app.</span></span>
2. <span data-ttu-id="b1fa0-150">Aggiungere la società alla configurazione della connessione a doppia scrittura.</span><span class="sxs-lookup"><span data-stu-id="b1fa0-150">Add the company to the dual-write connection setup.</span></span>
3. <span data-ttu-id="b1fa0-151">[Avviare](bootstrap-company-data.md) i dati Common Data Service utilizzando un codice aziendale di tre lettere ISO.</span><span class="sxs-lookup"><span data-stu-id="b1fa0-151">[Bootstrap](bootstrap-company-data.md) the Common Data Service data by using a three-letter ISO company code.</span></span>

<span data-ttu-id="b1fa0-152">Poiché la doppia scrittura è in modalità di sincronizzazione in tempo reale, i dati di Common Data Service iniziano automaticamente a essere inviati all'app Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="b1fa0-152">Because dual-write is in live synchronization mode, the data from Common Data Service automatically starts to flow to the Finance and Operations app.</span></span>

## <a name="an-existing-finance-and-operations-app-instance-and-a-new-or-existing-model-driven-app-instance"></a><a id="existing-existing"></a><span data-ttu-id="b1fa0-153">Un'istanza di app Finance and Operations esistente e un'istanza di app basata su modello nuova o esistente</span><span class="sxs-lookup"><span data-stu-id="b1fa0-153">An existing Finance and Operations app instance and a new or existing model-driven app instance</span></span>

<span data-ttu-id="b1fa0-154">L'impostazione di una connessione a doppia scrittura tra un'istanza esistente di un'app Finance and Operations e un'istanza nuova o esistente di un'app basata su modello in Dynamics 365 si verifica nell'ambiente Finance and Operation.</span><span class="sxs-lookup"><span data-stu-id="b1fa0-154">The setup of a dual-write connection between an existing instance of a Finance and Operations app and a new or existing instance of a model-driven app in Dynamics 365 occurs in the Finance and Operation environment.</span></span>

1. <span data-ttu-id="b1fa0-155">Impostare la connessione dall'app Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="b1fa0-155">Set up the connection from the Finance and Operations app.</span></span>
2. <span data-ttu-id="b1fa0-156">Per sincronizzare i dati Common Data Service esistenti nell'app Finance and Operations, [avviare](bootstrap-company-data.md) i dati Common Data Service utilizzando un codice azienda ISO di tre lettere.</span><span class="sxs-lookup"><span data-stu-id="b1fa0-156">To sync the existing Common Data Service data to the Finance and Operations app, [bootstrap](bootstrap-company-data.md) the Common Data Service data by using a three-letter ISO company code.</span></span>

<span data-ttu-id="b1fa0-157">Poiché la doppia scrittura è in modalità di sincronizzazione in tempo reale, i dati di Common Data Service iniziano automaticamente a essere inviati all'app Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="b1fa0-157">Because dual-write is in live synchronization mode, the data from Common Data Service automatically starts to flow to the Finance and Operations app.</span></span>
