---
title: Linee guida su come impostare la doppia scrittura
description: Questo argomento descrive gli scenari supportati per l'impostazione della doppia scrittura.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 10/12/2020
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
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: 2d77a1458f3f4c79b231e6a6d7cc320b8ee1fad9
ms.sourcegitcommit: ee643d651d57560bccae2f99238faa39881f5c64
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/21/2020
ms.locfileid: "4088508"
---
# <a name="guidance-for-how-to-set-up-dual-write"></a><span data-ttu-id="d1900-103">Linee guida su come impostare la doppia scrittura</span><span class="sxs-lookup"><span data-stu-id="d1900-103">Guidance for how to set up dual-write</span></span>

[!include [banner](../../includes/banner.md)]

[!include [preview-banner](../../includes/preview-banner.md)]

<span data-ttu-id="d1900-104">È possibile impostare una connessione di doppia scrittura tra un ambiente Finance and Operations e un ambiente Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="d1900-104">You can set up a dual-write connection between a Finance and Operations environment and a Common Data Service environment.</span></span>

+ <span data-ttu-id="d1900-105">Un **ambiente Finance and Operations** fornisce la piattaforma sottostante per le **app Finance and Operations** (ad esempio Microsoft Dynamics 365 Finance, Dynamics 365 Supply Chain Management e Dynamics 365 Retail).</span><span class="sxs-lookup"><span data-stu-id="d1900-105">A **Finance and Operations environment** provides the underlying platform for **Finance and Operations apps** (for example, Microsoft Dynamics 365 Finance, Dynamics 365 Supply Chain Management, and Dynamics 365 Retail).</span></span>
+ <span data-ttu-id="d1900-106">Un **ambiente Common Data Service** fornisce la piattaforma sottostante per le **app Customer Engagement** (Dynamics 365 Sales, Dynamics 365 Customer Service, Dynamics 365 Field Service, Dynamics 365 Marketing e Dynamics 365 Project Service Automation).</span><span class="sxs-lookup"><span data-stu-id="d1900-106">A **Common Data Service environment** provides the underlying platform for **customer engagement apps** (Dynamics 365 Sales, Dynamics 365 Customer Service, Dynamics 365 Field Service, Dynamics 365 Marketing, and Dynamics 365 Project Service Automation).</span></span>

>[!IMPORTANT]
><span data-ttu-id="d1900-107">Human Resources in Finance and Operations supporta le connessioni a doppia scrittura, al contrario dell'app Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="d1900-107">Human Resources in Finance and Operations supports dual-write connections, but the Dynamics 365 Human Resources app doesn't.</span></span>

<span data-ttu-id="d1900-108">Il meccanismo di impostazione varia in base alla sottoscrizione e all'ambiente.</span><span class="sxs-lookup"><span data-stu-id="d1900-108">The setup mechanism varies, depending on your subscription and the environment.</span></span>

+ <span data-ttu-id="d1900-109">Per le nuove istanze di app Finance and Operations, la configurazione di una connessione a doppia scrittura inizia in Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="d1900-109">For new instances of Finance and Operations apps, the setup of a dual-write connection begins in Microsoft Dynamics Lifecycle Services (LCS).</span></span> <span data-ttu-id="d1900-110">Se è disponibile una licenza per Power Platform, si ottiene uno nuovo ambiente Common Data Service se il tenant ne è privo.</span><span class="sxs-lookup"><span data-stu-id="d1900-110">If you have a license for Power Platform, you will get a new Common Data Service environment if your tenant doesn't have one.</span></span>
+ <span data-ttu-id="d1900-111">Per le istanze esistenti di app Finance and Operations, la configurazione di una connessione a doppia scrittura inizia nell'ambiente Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="d1900-111">For existing instances Finance and Operations apps, the setup of a dual-write connection begins in the Finance and Operations environment.</span></span>

<span data-ttu-id="d1900-112">Prima di avviare la doppia scrittura su un'entità, è possibile eseguire una sincronizzazione iniziale per gestire i dati esistenti su entrambi i lati delle app Finance and Operations e delle app Customer Engagement.</span><span class="sxs-lookup"><span data-stu-id="d1900-112">Before you start dual-write on an entity, you can run an initial sync to handle existing data on both sides of Finance and Operations apps and customer engagement apps.</span></span> <span data-ttu-id="d1900-113">È possibile saltare la sincronizzazione iniziale se non è necessario sincronizzare i dati tra i due ambienti.</span><span class="sxs-lookup"><span data-stu-id="d1900-113">You can skip the initial sync if you don't need to synchronize data between the two environments.</span></span>

<span data-ttu-id="d1900-114">Una sincronizzazione iniziale consente di copiare i dati esistenti da un'app all'altra in modo bidirezionale.</span><span class="sxs-lookup"><span data-stu-id="d1900-114">An initial sync lets you copy existing data from one app to another bidirectionally.</span></span> <span data-ttu-id="d1900-115">Esistono diversi scenari di configurazione a seconda degli ambienti già presenti e del tipo di dati presenti negli ambienti.</span><span class="sxs-lookup"><span data-stu-id="d1900-115">There are several different setup scenarios depending on which environments you already have and what type of data is in the environments.</span></span>

<span data-ttu-id="d1900-116">Sono supportati gli scenari di impostazione che seguono:</span><span class="sxs-lookup"><span data-stu-id="d1900-116">The following setup scenarios are supported:</span></span>

+ [<span data-ttu-id="d1900-117">Una nuova istanza di app Finance and Operations e una nuova istanza di app Customer Engagement</span><span class="sxs-lookup"><span data-stu-id="d1900-117">A new Finance and Operations app instance and a new customer engagement app instance</span></span>](#new-new)
+ [<span data-ttu-id="d1900-118">Una nuova istanza di app Finance and Operations e un'istanza esistente di app Customer Engagement</span><span class="sxs-lookup"><span data-stu-id="d1900-118">A new Finance and Operations app instance and an existing customer engagement app instance</span></span>](#new-existing)
+ [<span data-ttu-id="d1900-119">Una nuova istanza di app Finance and Operations con dati e una nuova istanza di app Customer Engagement</span><span class="sxs-lookup"><span data-stu-id="d1900-119">A new Finance and Operations app instance that has data and a new customer engagement app instance</span></span>](#new-data-new)
+ [<span data-ttu-id="d1900-120">Una nuova istanza di app Finance and Operations con dati e un'istanza di app Customer Engagement esistente</span><span class="sxs-lookup"><span data-stu-id="d1900-120">A new Finance and Operations app instance that has data and an existing customer engagement app instance</span></span>](#new-data-existing)
+ [<span data-ttu-id="d1900-121">Un'istanza esistente di app Finance and Operations e una nuova istanza di app Customer Engagement</span><span class="sxs-lookup"><span data-stu-id="d1900-121">An existing Finance and Operations app instance and a new customer engagement app instance</span></span>](#existing-new)
+ [<span data-ttu-id="d1900-122">Un'istanza esistente di app Finance and Operations e un'istanza esistente di app Customer Engagement</span><span class="sxs-lookup"><span data-stu-id="d1900-122">An existing Finance and Operations app instance and an existing customer engagement app instance</span></span>](#existing-existing)

## <a name="a-new-finance-and-operations-app-instance-and-a-new-customer-engagement-app-instance"></a><a id="new-new"></a><span data-ttu-id="d1900-123">Una nuova istanza di app Finance and Operations e una nuova istanza di app Customer Engagement</span><span class="sxs-lookup"><span data-stu-id="d1900-123">A new Finance and Operations app instance and a new customer engagement app instance</span></span>

<span data-ttu-id="d1900-124">Per impostare una connessione a doppia scrittura tra una nuova istanza di app Finance and Operations che non contiene dati e una nuova istanza di un'app Customer Engagement, seguire i passaggi in [Configurazione della doppia scrittura da Lifecycle Services](lcs-setup.md).</span><span class="sxs-lookup"><span data-stu-id="d1900-124">To set up a dual-write connection between a new instance of a Finance and Operations app that has no data and a new instance of a customer engagement app, follow the steps in [Dual-write setup from Lifecycle Services](lcs-setup.md).</span></span> <span data-ttu-id="d1900-125">Al termine della configurazione della connessione, si verificano automaticamente le seguenti azioni:</span><span class="sxs-lookup"><span data-stu-id="d1900-125">When the connection setup is completed, the following actions occur automatically:</span></span>

- <span data-ttu-id="d1900-126">Viene eseguito il provisioning di un nuovo ambiente vuoto Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="d1900-126">A new, empty Finance and Operations environment is provisioned.</span></span>
- <span data-ttu-id="d1900-127">Viene eseguito il provisioning di una nuova istanza vuota di un'app Customer Engagement in cui è installata la soluzione principale CRM.</span><span class="sxs-lookup"><span data-stu-id="d1900-127">A new, empty instance of a customer engagement app is provisioned, where the CRM prime solution is installed.</span></span>
- <span data-ttu-id="d1900-128">Viene stabilita una connessione a doppia scrittura per i dati dell'azienda DAT.</span><span class="sxs-lookup"><span data-stu-id="d1900-128">A dual-write connection is established for DAT company data.</span></span>
- <span data-ttu-id="d1900-129">Vengono abilitate le mappe entità per la sincronizzazione in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="d1900-129">Entity maps are enabled for live synchronization.</span></span>

<span data-ttu-id="d1900-130">Entrambi gli ambienti sono quindi pronti per la sincronizzazione dei dati in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="d1900-130">Both environments are then ready for live data synchronization.</span></span>

## <a name="a-new-finance-and-operations-app-instance-and-an-existing-customer-engagement-app-instance"></a><a id="new-existing"></a><span data-ttu-id="d1900-131">Una nuova istanza di app Finance and Operations e un'istanza esistente di app Customer Engagement</span><span class="sxs-lookup"><span data-stu-id="d1900-131">A new Finance and Operations app instance and an existing customer engagement app instance</span></span>

<span data-ttu-id="d1900-132">Per impostare una connessione a doppia scrittura tra una nuova istanza di app Finance and Operations che non contiene dati e un'istanza esistente di un'app Customer Engagement, seguire i passaggi in [Configurazione della doppia scrittura da Lifecycle Services](lcs-setup.md).</span><span class="sxs-lookup"><span data-stu-id="d1900-132">To set up a dual-write connection between a new instance of a Finance and Operations app that has no data and an existing instance of a customer engagement app, follow the steps in [Dual-write setup from Lifecycle Services](lcs-setup.md).</span></span> <span data-ttu-id="d1900-133">Al termine della configurazione della connessione, si verificano automaticamente le seguenti azioni:</span><span class="sxs-lookup"><span data-stu-id="d1900-133">When the connection setup is completed, the following actions occur automatically:</span></span>

- <span data-ttu-id="d1900-134">Viene eseguito il provisioning di un nuovo ambiente vuoto Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="d1900-134">A new, empty Finance and Operations environment is provisioned.</span></span>
- <span data-ttu-id="d1900-135">Viene stabilita una connessione a doppia scrittura per i dati dell'azienda DAT.</span><span class="sxs-lookup"><span data-stu-id="d1900-135">A dual-write connection is established for DAT company data.</span></span>
- <span data-ttu-id="d1900-136">Vengono abilitate le mappe entità per la sincronizzazione in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="d1900-136">Entity maps are enabled for live synchronization.</span></span>

<span data-ttu-id="d1900-137">Entrambi gli ambienti sono quindi pronti per la sincronizzazione dei dati in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="d1900-137">Both environments are then ready for live data synchronization.</span></span>

<span data-ttu-id="d1900-138">Per sincronizzare i dati Common Data Service esistenti nell'app Finance and Operations, seguire questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="d1900-138">To sync the existing Common Data Service data to the Finance and Operations app, follow these steps.</span></span>

1. <span data-ttu-id="d1900-139">Creare una nuova società nell'app Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="d1900-139">Create a new company in the Finance and Operations app.</span></span>
2. <span data-ttu-id="d1900-140">Aggiungere la società alla configurazione della connessione a doppia scrittura.</span><span class="sxs-lookup"><span data-stu-id="d1900-140">Add the company to the dual-write connection setup.</span></span>
3. <span data-ttu-id="d1900-141">[Avviare](bootstrap-company-data.md) i dati Common Data Service utilizzando un codice aziendale di tre lettere International Organization for Standardization (ISO).</span><span class="sxs-lookup"><span data-stu-id="d1900-141">[Bootstrap](bootstrap-company-data.md) the Common Data Service data by using a three-letter International Organization for Standardization (ISO) company code.</span></span>
4. <span data-ttu-id="d1900-142">Eseguire la funzionalità **Sincronizzazione iniziale** per le entità per cui si desidera sincronizzare i dati.</span><span class="sxs-lookup"><span data-stu-id="d1900-142">Run the **Initial sync** functionality for the entities that you want to sync data for.</span></span>

<span data-ttu-id="d1900-143">Per un esempio e un approccio alternativo, vedere [Esempio](#example).</span><span class="sxs-lookup"><span data-stu-id="d1900-143">For an example and alternative approach, see [Example](#example).</span></span>

## <a name="a-new-finance-and-operations-app-instance-that-has-data-and-a-new-customer-engagement-app-instance"></a><a id="new-data-new"></a><span data-ttu-id="d1900-144">Una nuova istanza di app Finance and Operations con dati e una nuova istanza di app Customer Engagement</span><span class="sxs-lookup"><span data-stu-id="d1900-144">A new Finance and Operations app instance that has data and a new customer engagement app instance</span></span>

<span data-ttu-id="d1900-145">Per impostare una connessione a doppia scrittura tra una nuova istanza di app Finance and Operations con dati e una nuova istanza di un'app Customer Engagement, seguire i passaggi nella sezione [Una nuova istanza di app Finance and Operations e una nuova istanza di app Customer Engagement](#new-new) precedente in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="d1900-145">To set up a dual-write connection between a new instance of a Finance and Operations app that has data and a new instance of a customer engagement app, follow the steps in the [A new Finance and Operations app instance and a new customer engagement app instance](#new-new) section earlier in this topic.</span></span> <span data-ttu-id="d1900-146">Al termine della configurazione della connessione, se si desidera sincronizzare i dati con l'app Customer Engagement, attenersi alla seguente procedura.</span><span class="sxs-lookup"><span data-stu-id="d1900-146">When the connection setup is completed, if you want to sync the data to the customer engagement app, follow these steps.</span></span>

1. <span data-ttu-id="d1900-147">Aprire l'app Finance and Operations dalla pagina LCS, accedere e passare a **Gestione dati \> Doppia scrittura**.</span><span class="sxs-lookup"><span data-stu-id="d1900-147">Open the Finance and Operations app from the LCS page, sign in, and then go to **Data Management \> Dual-write**.</span></span>
2. <span data-ttu-id="d1900-148">Eseguire la funzionalità **Sincronizzazione iniziale** per le entità per cui si desidera sincronizzare i dati.</span><span class="sxs-lookup"><span data-stu-id="d1900-148">Run the **Initial sync** functionality for the entities that you want to sync data for.</span></span>

<span data-ttu-id="d1900-149">Per un esempio e un approccio alternativo, vedere [Esempio](#example).</span><span class="sxs-lookup"><span data-stu-id="d1900-149">For an example and alternative approach, see [Example](#example).</span></span>

## <a name="a-new-finance-and-operations-app-instance-that-has-data-and-an-existing-customer-engagement-app-instance"></a><a id="new-data-existing"></a><span data-ttu-id="d1900-150">Una nuova istanza di app Finance and Operations con dati e un'istanza di app Customer Engagement esistente</span><span class="sxs-lookup"><span data-stu-id="d1900-150">A new Finance and Operations app instance that has data and an existing customer engagement app instance</span></span>

<span data-ttu-id="d1900-151">Per impostare una connessione a doppia scrittura tra una nuova istanza di app Finance and Operations con dati e un'istanza esistente di un'app Customer Engagement, seguire i passaggi nella sezione [Una nuova istanza di app Finance and Operations e un'istanza esistente di app Customer Engagement](#new-existing) precedente in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="d1900-151">To set up a dual-write connection between a new instance of a Finance and Operations app that has data and an existing instance of a customer engagement app, follow the steps in the [A new Finance and Operations app instance and an existing customer engagement app instance](#new-existing) section earlier in this topic.</span></span> <span data-ttu-id="d1900-152">Al termine della configurazione della connessione, se si desidera sincronizzare i dati con l'app Customer Engagement, attenersi alla seguente procedura.</span><span class="sxs-lookup"><span data-stu-id="d1900-152">When the connection setup is completed, if you want to sync the data to the customer engagement app, follow these steps.</span></span>

1. <span data-ttu-id="d1900-153">Aprire l'app Finance and Operations dalla pagina LCS, accedere e passare a **Gestione dati \> Doppia scrittura**.</span><span class="sxs-lookup"><span data-stu-id="d1900-153">Open the Finance and Operations app from the LCS page, sign in, and then go to **Data Management \> Dual-write**.</span></span>
2. <span data-ttu-id="d1900-154">Eseguire la funzionalità **Sincronizzazione iniziale** per le entità per cui si desidera sincronizzare i dati.</span><span class="sxs-lookup"><span data-stu-id="d1900-154">Run the **Initial sync** functionality for the entities that you want to sync data for.</span></span>

<span data-ttu-id="d1900-155">Per sincronizzare i dati Common Data Service esistenti nell'app Finance and Operations, seguire questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="d1900-155">To sync the existing Common Data Service data to the Finance and Operations app, follow these steps.</span></span>

1. <span data-ttu-id="d1900-156">Creare una nuova società nell'app Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="d1900-156">Create a new company in the Finance and Operations app.</span></span>
2. <span data-ttu-id="d1900-157">Aggiungere la società alla configurazione della connessione a doppia scrittura.</span><span class="sxs-lookup"><span data-stu-id="d1900-157">Add the company to the dual-write connection setup.</span></span>
3. <span data-ttu-id="d1900-158">[Avviare](bootstrap-company-data.md) i dati Common Data Service utilizzando un codice aziendale di tre lettere ISO.</span><span class="sxs-lookup"><span data-stu-id="d1900-158">[Bootstrap](bootstrap-company-data.md) the Common Data Service data by using a three-letter ISO company code.</span></span>
4. <span data-ttu-id="d1900-159">Eseguire la funzionalità **Sincronizzazione iniziale** per le entità per cui si desidera sincronizzare i dati.</span><span class="sxs-lookup"><span data-stu-id="d1900-159">Run the **Initial sync** functionality for the entities that you want to sync data for.</span></span>

<span data-ttu-id="d1900-160">Per un esempio e un approccio alternativo, vedere [Esempio](#example).</span><span class="sxs-lookup"><span data-stu-id="d1900-160">For an example and alternative approach, see [Example](#example).</span></span>

## <a name="an-existing-finance-and-operations-app-instance-and-a-new-customer-engagement-app-instance"></a><a id="existing-new"></a><span data-ttu-id="d1900-161">Un'istanza esistente di app Finance and Operations e una nuova istanza di app Customer Engagement</span><span class="sxs-lookup"><span data-stu-id="d1900-161">An existing Finance and Operations app instance and a new customer engagement app instance</span></span>

<span data-ttu-id="d1900-162">L'impostazione di una connessione a doppia scrittura tra un'istanza esistente di un'app Finance and Operations e una nuova istanza di un'app Customer Engagement si verifica nell'ambiente Finance and Operation.</span><span class="sxs-lookup"><span data-stu-id="d1900-162">The setup of a dual-write connection between an existing instance of a Finance and Operations app and a new instance of a customer engagement app occurs in the Finance and Operation environment.</span></span>

1. <span data-ttu-id="d1900-163">[Impostare la connessione dall'app Finance and Operations](enable-dual-write.md).</span><span class="sxs-lookup"><span data-stu-id="d1900-163">[Set up the connection from the Finance and Operations app](enable-dual-write.md).</span></span>
2. <span data-ttu-id="d1900-164">Eseguire la funzionalità **Sincronizzazione iniziale** per le entità per cui si desidera sincronizzare i dati.</span><span class="sxs-lookup"><span data-stu-id="d1900-164">Run the **Initial sync** functionality for the entities that you want to sync data for.</span></span>

<span data-ttu-id="d1900-165">Per un esempio e un approccio alternativo, vedere [Esempio](#example).</span><span class="sxs-lookup"><span data-stu-id="d1900-165">For an example and alternative approach, see [Example](#example).</span></span>

## <a name="an-existing-finance-and-operations-app-instance-and-an-existing-customer-engagement-app-instance"></a><a id="existing-existing"></a><span data-ttu-id="d1900-166">Un'istanza esistente di app Finance and Operations e un'istanza esistente di app Customer Engagement</span><span class="sxs-lookup"><span data-stu-id="d1900-166">An existing Finance and Operations app instance and an existing customer engagement app instance</span></span>

<span data-ttu-id="d1900-167">L'impostazione di una connessione a doppia scrittura tra un'istanza esistente di un'app Finance and Operations e un'istanza esistente di un'app Customer Engagement si verifica nell'ambiente Finance and Operation.</span><span class="sxs-lookup"><span data-stu-id="d1900-167">The setup of a dual-write connection between an existing instance of a Finance and Operations app and an existing instance of a customer engagement app  occurs in the Finance and Operation environment.</span></span>

1. <span data-ttu-id="d1900-168">Impostare la connessione dall'app Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="d1900-168">Set up the connection from the Finance and Operations app.</span></span>
2. <span data-ttu-id="d1900-169">Per sincronizzare i dati Common Data Service esistenti nell'app Finance and Operations, [avviare](bootstrap-company-data.md) i dati Common Data Service utilizzando un codice azienda ISO di tre lettere.</span><span class="sxs-lookup"><span data-stu-id="d1900-169">To sync the existing Common Data Service data to the Finance and Operations app, [bootstrap](bootstrap-company-data.md) the Common Data Service data by using a three-letter ISO company code.</span></span>
3. <span data-ttu-id="d1900-170">Eseguire la funzionalità **Sincronizzazione iniziale** per le entità per cui si desidera sincronizzare i dati.</span><span class="sxs-lookup"><span data-stu-id="d1900-170">Run the **Initial sync** functionality for the entities that you want to sync data for.</span></span>

<span data-ttu-id="d1900-171">Per un esempio e un approccio alternativo, vedere [Esempio](#example).</span><span class="sxs-lookup"><span data-stu-id="d1900-171">For an example and alternative approach, see [Example](#example).</span></span>

## <a name="example"></a><span data-ttu-id="d1900-172">Esempio</span><span class="sxs-lookup"><span data-stu-id="d1900-172">Example</span></span>

<span data-ttu-id="d1900-173">Per un esempio, vedere [Abilitazione di Customers V3: mappa entità contatti](enable-entity-map.md#example-enabling-the-customers-v3contacts-entity-map)</span><span class="sxs-lookup"><span data-stu-id="d1900-173">For an example, see [Enabling the Customers V3—Contacts entity map](enable-entity-map.md#example-enabling-the-customers-v3contacts-entity-map)</span></span>

<span data-ttu-id="d1900-174">Per un approccio alternativo basato sui volumi di dati in ogni entità che deve eseguire la sincronizzazione iniziale, vedere [Considerazioni per la sincronizzazione iniziale](initial-sync-guidance.md).</span><span class="sxs-lookup"><span data-stu-id="d1900-174">For an alternative approach based on data volumes in each entity that need to run initial sync, see [Considerations for initial synchronization](initial-sync-guidance.md).</span></span>
