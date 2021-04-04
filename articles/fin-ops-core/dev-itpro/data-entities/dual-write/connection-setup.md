---
title: Linee guida per la configurazione della doppia scrittura
description: Questo argomento descrive gli scenari supportati per l'impostazione della doppia scrittura.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 10/12/2020
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
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: dee6bc52a0967dfd6134258d3a02dc18feb404a5
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2021
ms.locfileid: "5560227"
---
# <a name="guidance-for-dual-write-setup"></a><span data-ttu-id="6a05d-103">Linee guida per la configurazione della doppia scrittura</span><span class="sxs-lookup"><span data-stu-id="6a05d-103">Guidance for dual-write setup</span></span>

[!include [banner](../../includes/banner.md)]

[!include [preview-banner](../../includes/preview-banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="6a05d-104">È possibile impostare una connessione di doppia scrittura tra un ambiente Finance and Operations e un ambiente Dataverse.</span><span class="sxs-lookup"><span data-stu-id="6a05d-104">You can set up a dual-write connection between a Finance and Operations environment and a Dataverse environment.</span></span>

+ <span data-ttu-id="6a05d-105">Un **ambiente Finance and Operations** fornisce la piattaforma sottostante per le **app Finance and Operations** (ad esempio, Microsoft Dynamics 365 Finance, Dynamics 365 Supply Chain Management, Dynamics 365 Commerce e Dynamics 365 Human Resources).</span><span class="sxs-lookup"><span data-stu-id="6a05d-105">A **Finance and Operations environment** provides the underlying platform for **Finance and Operations apps** (for example, Microsoft Dynamics 365 Finance, Dynamics 365 Supply Chain Management, Dynamics 365 Commerce, and Dynamics 365 Human Resources).</span></span>
+ <span data-ttu-id="6a05d-106">Un **ambiente Dataverse** fornisce la piattaforma sottostante per le **app di interazione con i clienti** in Dynamics 365 (Dynamics 365 Sales, Dynamics 365 Customer Service, Dynamics 365, Dynamics 365 Marketing e Dynamics 365 Project Service Automation).</span><span class="sxs-lookup"><span data-stu-id="6a05d-106">A **Dataverse environment** provides the underlying platform for **customer engagement apps** (Dynamics 365 Sales, Dynamics 365 Customer Service, Dynamics 365 column Service, Dynamics 365 Marketing, and Dynamics 365 Project Service Automation).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6a05d-107">Il modulo Risorse umane in Dynamics 365 Finance supporta le connessioni a doppia scrittura, al contrario dell'app Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="6a05d-107">The Human Resources module in Dynamics 365 Finance supports dual-write connections, but the Dynamics 365 Human Resources app doesn't.</span></span>

<span data-ttu-id="6a05d-108">Il meccanismo di impostazione varia in base alla sottoscrizione e all'ambiente:</span><span class="sxs-lookup"><span data-stu-id="6a05d-108">The setup mechanism varies, depending on your subscription and the environment:</span></span>

+ <span data-ttu-id="6a05d-109">Per le nuove istanze di app Finance and Operations, la configurazione di una connessione a doppia scrittura inizia in Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="6a05d-109">For new instances of Finance and Operations apps, the setup of a dual-write connection begins in Microsoft Dynamics Lifecycle Services (LCS).</span></span> <span data-ttu-id="6a05d-110">Se è disponibile una licenza per Microsoft Power Platform, si ottiene uno nuovo ambiente Dataverse se il tenant ne è privo.</span><span class="sxs-lookup"><span data-stu-id="6a05d-110">If you have a license for Microsoft Power Platform, you will get a new Dataverse environment if your tenant doesn't have one.</span></span>
+ <span data-ttu-id="6a05d-111">Per le istanze esistenti di app Finance and Operations, la configurazione di una connessione a doppia scrittura inizia nell'ambiente Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="6a05d-111">For existing instances Finance and Operations apps, the setup of a dual-write connection begins in the Finance and Operations environment.</span></span>

<span data-ttu-id="6a05d-112">Prima di avviare la doppia scrittura su un'entità, è possibile eseguire una sincronizzazione iniziale per gestire i dati esistenti su entrambi i lati: delle app Finance and Operations e delle app Customer Engagement.</span><span class="sxs-lookup"><span data-stu-id="6a05d-112">Before you start dual-write on an entity, you can run an initial synchronization to handle existing data on both sides: Finance and Operations apps and customer engagement apps.</span></span> <span data-ttu-id="6a05d-113">È possibile saltare la sincronizzazione iniziale se non si devono sincronizzare i dati tra i due ambienti.</span><span class="sxs-lookup"><span data-stu-id="6a05d-113">You can skip the initial synchronization if you don't have to sync data between the two environments.</span></span>

<span data-ttu-id="6a05d-114">Una sincronizzazione iniziale consente di copiare i dati esistenti da un'app all'altra in modo bidirezionale.</span><span class="sxs-lookup"><span data-stu-id="6a05d-114">An initial synchronization lets you copy existing data from one app to another bidirectionally.</span></span> <span data-ttu-id="6a05d-115">Esistono diversi scenari di configurazione a seconda degli ambienti già presenti e del tipo di dati in essi presenti.</span><span class="sxs-lookup"><span data-stu-id="6a05d-115">There are several setup scenarios, depending on the environments that you already have and the type of data in them.</span></span>

<span data-ttu-id="6a05d-116">Sono supportati gli scenari di impostazione che seguono:</span><span class="sxs-lookup"><span data-stu-id="6a05d-116">The following setup scenarios are supported:</span></span>

+ [<span data-ttu-id="6a05d-117">Una nuova istanza di app Finance and Operations e una nuova istanza di app Customer Engagement</span><span class="sxs-lookup"><span data-stu-id="6a05d-117">A new Finance and Operations app instance and a new customer engagement app instance</span></span>](#new-new)
+ [<span data-ttu-id="6a05d-118">Una nuova istanza di app Finance and Operations e un'istanza esistente di app Customer Engagement</span><span class="sxs-lookup"><span data-stu-id="6a05d-118">A new Finance and Operations app instance and an existing customer engagement app instance</span></span>](#new-existing)
+ [<span data-ttu-id="6a05d-119">Una nuova istanza di app Finance and Operations con dati e una nuova istanza di app Customer Engagement</span><span class="sxs-lookup"><span data-stu-id="6a05d-119">A new Finance and Operations app instance that has data and a new customer engagement app instance</span></span>](#new-data-new)
+ [<span data-ttu-id="6a05d-120">Una nuova istanza di app Finance and Operations con dati e un'istanza di app Customer Engagement esistente</span><span class="sxs-lookup"><span data-stu-id="6a05d-120">A new Finance and Operations app instance that has data and an existing customer engagement app instance</span></span>](#new-data-existing)
+ [<span data-ttu-id="6a05d-121">Un'istanza esistente di app Finance and Operations e una nuova istanza di app Customer Engagement</span><span class="sxs-lookup"><span data-stu-id="6a05d-121">An existing Finance and Operations app instance and a new customer engagement app instance</span></span>](#existing-new)
+ [<span data-ttu-id="6a05d-122">Un'istanza esistente di app Finance and Operations e un'istanza esistente di app Customer Engagement</span><span class="sxs-lookup"><span data-stu-id="6a05d-122">An existing Finance and Operations app instance and an existing customer engagement app instance</span></span>](#existing-existing)

## <a name="a-new-finance-and-operations-app-instance-and-a-new-customer-engagement-app-instance"></a><a id="new-new"></a><span data-ttu-id="6a05d-123">Una nuova istanza di app Finance and Operations e una nuova istanza di app Customer Engagement</span><span class="sxs-lookup"><span data-stu-id="6a05d-123">A new Finance and Operations app instance and a new customer engagement app instance</span></span>

<span data-ttu-id="6a05d-124">Per impostare una connessione a doppia scrittura tra una nuova istanza di app Finance and Operations che non contiene dati e una nuova istanza di un'app Customer Engagement, seguire i passaggi in [Configurazione della doppia scrittura da Lifecycle Services](lcs-setup.md).</span><span class="sxs-lookup"><span data-stu-id="6a05d-124">To set up a dual-write connection between a new instance of a Finance and Operations app that has no data and a new instance of a customer engagement app, follow the steps in [Dual-write setup from Lifecycle Services](lcs-setup.md).</span></span> <span data-ttu-id="6a05d-125">Al termine della configurazione della connessione, si verificano automaticamente le seguenti azioni:</span><span class="sxs-lookup"><span data-stu-id="6a05d-125">When the connection setup is completed, the following actions automatically occur:</span></span>

- <span data-ttu-id="6a05d-126">Viene eseguito il provisioning di un nuovo ambiente vuoto Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="6a05d-126">A new, empty Finance and Operations environment is provisioned.</span></span>
- <span data-ttu-id="6a05d-127">Viene eseguito il provisioning di una nuova istanza vuota di un'app Customer Engagement in cui è installata la soluzione principale CRM.</span><span class="sxs-lookup"><span data-stu-id="6a05d-127">A new, empty instance of a customer engagement app is provisioned, where the CRM prime solution is installed.</span></span>
- <span data-ttu-id="6a05d-128">Viene stabilita una connessione a doppia scrittura per i dati dell'azienda DAT.</span><span class="sxs-lookup"><span data-stu-id="6a05d-128">A dual-write connection is established for DAT company data.</span></span>
- <span data-ttu-id="6a05d-129">Vengono abilitate le mappe della tabella per la sincronizzazione in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="6a05d-129">Table maps are enabled for live synchronization.</span></span>

<span data-ttu-id="6a05d-130">Entrambi gli ambienti sono quindi pronti per la sincronizzazione dei dati in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="6a05d-130">Both environments are then ready for live data synchronization.</span></span>

## <a name="a-new-finance-and-operations-app-instance-and-an-existing-customer-engagement-app-instance"></a><a id="new-existing"></a><span data-ttu-id="6a05d-131">Una nuova istanza di app Finance and Operations e un'istanza esistente di app Customer Engagement</span><span class="sxs-lookup"><span data-stu-id="6a05d-131">A new Finance and Operations app instance and an existing customer engagement app instance</span></span>

<span data-ttu-id="6a05d-132">Per impostare una connessione a doppia scrittura tra una nuova istanza di app Finance and Operations che non contiene dati e un'istanza esistente di un'app Customer Engagement, seguire i passaggi in [Configurazione della doppia scrittura da Lifecycle Services](lcs-setup.md).</span><span class="sxs-lookup"><span data-stu-id="6a05d-132">To set up a dual-write connection between a new instance of a Finance and Operations app that has no data and an existing instance of a customer engagement app, follow the steps in [Dual-write setup from Lifecycle Services](lcs-setup.md).</span></span> <span data-ttu-id="6a05d-133">Al termine della configurazione della connessione, si verificano automaticamente le seguenti azioni:</span><span class="sxs-lookup"><span data-stu-id="6a05d-133">When the connection setup is completed, the following actions automatically occur:</span></span>

- <span data-ttu-id="6a05d-134">Viene eseguito il provisioning di un nuovo ambiente vuoto Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="6a05d-134">A new, empty Finance and Operations environment is provisioned.</span></span>
- <span data-ttu-id="6a05d-135">Viene stabilita una connessione a doppia scrittura per i dati dell'azienda DAT.</span><span class="sxs-lookup"><span data-stu-id="6a05d-135">A dual-write connection is established for DAT company data.</span></span>
- <span data-ttu-id="6a05d-136">Vengono abilitate le mappe della tabella per la sincronizzazione in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="6a05d-136">Table maps are enabled for live synchronization.</span></span>

<span data-ttu-id="6a05d-137">Entrambi gli ambienti sono quindi pronti per la sincronizzazione dei dati in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="6a05d-137">Both environments are then ready for live data synchronization.</span></span>

<span data-ttu-id="6a05d-138">Per sincronizzare i dati Dataverse esistenti nell'app Finance and Operations, seguire questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="6a05d-138">To sync the existing Dataverse data to the Finance and Operations app, follow these steps.</span></span>

1. <span data-ttu-id="6a05d-139">Creare una nuova società nell'app Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="6a05d-139">Create a new company in the Finance and Operations app.</span></span>
2. <span data-ttu-id="6a05d-140">Aggiungere la società alla configurazione della connessione a doppia scrittura.</span><span class="sxs-lookup"><span data-stu-id="6a05d-140">Add the company to the dual-write connection setup.</span></span>
3. <span data-ttu-id="6a05d-141">[Avviare](bootstrap-company-data.md) i dati Dataverse utilizzando un codice aziendale di tre lettere International Organization for Standardization (ISO).</span><span class="sxs-lookup"><span data-stu-id="6a05d-141">[Bootstrap](bootstrap-company-data.md) the Dataverse data by using a three-letter International Organization for Standardization (ISO) company code.</span></span>
4. <span data-ttu-id="6a05d-142">Eseguire la funzionalità **Sincronizzazione iniziale** per le tabelle per cui si desidera sincronizzare i dati.</span><span class="sxs-lookup"><span data-stu-id="6a05d-142">Run the **Initial sync** functionality for the tables that you want to sync data for.</span></span>

<span data-ttu-id="6a05d-143">Per i collegamenti a un esempio e un approccio alternativo, consultare la sezione [Esempio](#example) più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="6a05d-143">For links to an example and an alternative approach, see the [Example](#example) section later in this topic.</span></span>

## <a name="a-new-finance-and-operations-app-instance-that-has-data-and-a-new-customer-engagement-app-instance"></a><a id="new-data-new"></a><span data-ttu-id="6a05d-144">Una nuova istanza di app Finance and Operations con dati e una nuova istanza di app Customer Engagement</span><span class="sxs-lookup"><span data-stu-id="6a05d-144">A new Finance and Operations app instance that has data and a new customer engagement app instance</span></span>

<span data-ttu-id="6a05d-145">Per impostare una connessione a doppia scrittura tra una nuova istanza di app Finance and Operations con dati e una nuova istanza di un'app Customer Engagement, seguire i passaggi nella sezione [Una nuova istanza di app Finance and Operations e una nuova istanza di app Customer Engagement](#new-new) precedente in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="6a05d-145">To set up a dual-write connection between a new instance of a Finance and Operations app that has data and a new instance of a customer engagement app, follow the steps in the [A new Finance and Operations app instance and a new customer engagement app instance](#new-new) section earlier in this topic.</span></span> <span data-ttu-id="6a05d-146">Al termine della configurazione della connessione, se si desidera sincronizzare i dati con l'app Customer Engagement, attenersi alla seguente procedura.</span><span class="sxs-lookup"><span data-stu-id="6a05d-146">When the connection setup is completed, if you want to sync the data to the customer engagement app, follow these steps.</span></span>

1. <span data-ttu-id="6a05d-147">Aprire l'app Finance and Operations dalla pagina LCS, accedere e passare a **Gestione dati \> Doppia scrittura**.</span><span class="sxs-lookup"><span data-stu-id="6a05d-147">Open the Finance and Operations app from the LCS page, sign in, and then go to **Data Management \> Dual-write**.</span></span>
2. <span data-ttu-id="6a05d-148">Eseguire la funzionalità **Sincronizzazione iniziale** per le tabelle per cui si desidera sincronizzare i dati.</span><span class="sxs-lookup"><span data-stu-id="6a05d-148">Run the **Initial sync** functionality for the tables that you want to sync data for.</span></span>

<span data-ttu-id="6a05d-149">Per i collegamenti a un esempio e un approccio alternativo, consultare la sezione [Esempio](#example).</span><span class="sxs-lookup"><span data-stu-id="6a05d-149">For links to an example and an alternative approach, see the [Example](#example) section.</span></span>

## <a name="a-new-finance-and-operations-app-instance-that-has-data-and-an-existing-customer-engagement-app-instance"></a><a id="new-data-existing"></a><span data-ttu-id="6a05d-150">Una nuova istanza di app Finance and Operations con dati e un'istanza di app Customer Engagement esistente</span><span class="sxs-lookup"><span data-stu-id="6a05d-150">A new Finance and Operations app instance that has data and an existing customer engagement app instance</span></span>

<span data-ttu-id="6a05d-151">Per impostare una connessione a doppia scrittura tra una nuova istanza di app Finance and Operations con dati e un'istanza esistente di un'app Customer Engagement, seguire i passaggi nella sezione [Una nuova istanza di app Finance and Operations e un'istanza esistente di app Customer Engagement](#new-existing) precedente in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="6a05d-151">To set up a dual-write connection between a new instance of a Finance and Operations app that has data and an existing instance of a customer engagement app, follow the steps in the [A new Finance and Operations app instance and an existing customer engagement app instance](#new-existing) section earlier in this topic.</span></span> <span data-ttu-id="6a05d-152">Al termine della configurazione della connessione, se si desidera sincronizzare i dati con l'app Customer Engagement, attenersi alla seguente procedura.</span><span class="sxs-lookup"><span data-stu-id="6a05d-152">When the connection setup is completed, if you want to sync the data to the customer engagement app, follow these steps.</span></span>

1. <span data-ttu-id="6a05d-153">Aprire l'app Finance and Operations dalla pagina LCS, accedere e passare a **Gestione dati \> Doppia scrittura**.</span><span class="sxs-lookup"><span data-stu-id="6a05d-153">Open the Finance and Operations app from the LCS page, sign in, and then go to **Data Management \> Dual-write**.</span></span>
2. <span data-ttu-id="6a05d-154">Eseguire la funzionalità **Sincronizzazione iniziale** per le tabelle per cui si desidera sincronizzare i dati.</span><span class="sxs-lookup"><span data-stu-id="6a05d-154">Run the **Initial sync** functionality for the tables that you want to sync data for.</span></span>

<span data-ttu-id="6a05d-155">Per sincronizzare i dati Dataverse esistenti nell'app Finance and Operations, seguire questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="6a05d-155">To sync the existing Dataverse data to the Finance and Operations app, follow these steps.</span></span>

1. <span data-ttu-id="6a05d-156">Creare una nuova società nell'app Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="6a05d-156">Create a new company in the Finance and Operations app.</span></span>
2. <span data-ttu-id="6a05d-157">Aggiungere la società alla configurazione della connessione a doppia scrittura.</span><span class="sxs-lookup"><span data-stu-id="6a05d-157">Add the company to the dual-write connection setup.</span></span>
3. <span data-ttu-id="6a05d-158">[Avviare](bootstrap-company-data.md) i dati Dataverse utilizzando un codice aziendale di tre lettere ISO.</span><span class="sxs-lookup"><span data-stu-id="6a05d-158">[Bootstrap](bootstrap-company-data.md) the Dataverse data by using a three-letter ISO company code.</span></span>
4. <span data-ttu-id="6a05d-159">Eseguire la funzionalità **Sincronizzazione iniziale** per le tabelle per cui si desidera sincronizzare i dati.</span><span class="sxs-lookup"><span data-stu-id="6a05d-159">Run the **Initial sync** functionality for the tables that you want to sync data for.</span></span>

<span data-ttu-id="6a05d-160">Per i collegamenti a un esempio e un approccio alternativo, consultare la sezione [Esempio](#example).</span><span class="sxs-lookup"><span data-stu-id="6a05d-160">For links to an example and an alternative approach, see the [Example](#example) section.</span></span>

## <a name="an-existing-finance-and-operations-app-instance-and-a-new-customer-engagement-app-instance"></a><a id="existing-new"></a><span data-ttu-id="6a05d-161">Un'istanza esistente di app Finance and Operations e una nuova istanza di app Customer Engagement</span><span class="sxs-lookup"><span data-stu-id="6a05d-161">An existing Finance and Operations app instance and a new customer engagement app instance</span></span>

<span data-ttu-id="6a05d-162">L'impostazione di una connessione a doppia scrittura tra un'istanza esistente di un'app Finance and Operations e una nuova istanza di un'app Customer Engagement si verifica nell'ambiente Finance and Operation.</span><span class="sxs-lookup"><span data-stu-id="6a05d-162">The setup of a dual-write connection between an existing instance of a Finance and Operations app and a new instance of a customer engagement app occurs in the Finance and Operation environment.</span></span>

1. <span data-ttu-id="6a05d-163">[Impostare la connessione dall'app Finance and Operations](enable-dual-write.md).</span><span class="sxs-lookup"><span data-stu-id="6a05d-163">[Set up the connection from the Finance and Operations app](enable-dual-write.md).</span></span>
2. <span data-ttu-id="6a05d-164">Eseguire la funzionalità **Sincronizzazione iniziale** per le tabelle per cui si desidera sincronizzare i dati.</span><span class="sxs-lookup"><span data-stu-id="6a05d-164">Run the **Initial sync** functionality for the tables that you want to sync data for.</span></span>

<span data-ttu-id="6a05d-165">Per i collegamenti a un esempio e un approccio alternativo, consultare la sezione [Esempio](#example).</span><span class="sxs-lookup"><span data-stu-id="6a05d-165">For links to an example and an alternative approach, see the [Example](#example) section.</span></span>

## <a name="an-existing-finance-and-operations-app-instance-and-an-existing-customer-engagement-app-instance"></a><a id="existing-existing"></a><span data-ttu-id="6a05d-166">Un'istanza esistente di app Finance and Operations e un'istanza esistente di app Customer Engagement</span><span class="sxs-lookup"><span data-stu-id="6a05d-166">An existing Finance and Operations app instance and an existing customer engagement app instance</span></span>

<span data-ttu-id="6a05d-167">L'impostazione di una connessione a doppia scrittura tra un'istanza esistente di un'app Finance and Operations e un'istanza esistente di un'app Customer Engagement si verifica nell'ambiente Finance and Operation.</span><span class="sxs-lookup"><span data-stu-id="6a05d-167">The setup of a dual-write connection between an existing instance of a Finance and Operations app and an existing instance of a customer engagement app occurs in the Finance and Operation environment.</span></span>

1. <span data-ttu-id="6a05d-168">[Impostare la connessione dall'app Finance and Operations](enable-dual-write.md).</span><span class="sxs-lookup"><span data-stu-id="6a05d-168">[Set up the connection from the Finance and Operations app](enable-dual-write.md).</span></span>
2. <span data-ttu-id="6a05d-169">Per sincronizzare i dati Dataverse esistenti nell'app Finance and Operations, [avviare](bootstrap-company-data.md) i dati Dataverse utilizzando un codice azienda ISO di tre lettere.</span><span class="sxs-lookup"><span data-stu-id="6a05d-169">To sync the existing Dataverse data to the Finance and Operations app, [bootstrap](bootstrap-company-data.md) the Dataverse data by using a three-letter ISO company code.</span></span>
3. <span data-ttu-id="6a05d-170">Eseguire la funzionalità **Sincronizzazione iniziale** per le tabelle per cui si desidera sincronizzare i dati.</span><span class="sxs-lookup"><span data-stu-id="6a05d-170">Run the **Initial sync** functionality for the tables that you want to sync data for.</span></span>

<span data-ttu-id="6a05d-171">Per i collegamenti a un esempio e un approccio alternativo, consultare la sezione [Esempio](#example).</span><span class="sxs-lookup"><span data-stu-id="6a05d-171">For links to an example and an alternative approach, see the [Example](#example) section.</span></span>

## <a name="example"></a><span data-ttu-id="6a05d-172">Esempio</span><span class="sxs-lookup"><span data-stu-id="6a05d-172">Example</span></span>

<span data-ttu-id="6a05d-173">Per un esempio, vedere [Abilitazione di Customers V3-mappa della tabella Contatti](enable-entity-map.md#enable-table-map)</span><span class="sxs-lookup"><span data-stu-id="6a05d-173">For an example, see [Enabling the Customers V3—Contacts table map](enable-entity-map.md#enable-table-map)</span></span>

<span data-ttu-id="6a05d-174">Per un approccio alternativo che si basa sui volumi di dati in ogni entità che deve eseguire una sincronizzazione iniziale, vedere [Considerazioni per la sincronizzazione iniziale](initial-sync-guidance.md).</span><span class="sxs-lookup"><span data-stu-id="6a05d-174">For an alternative approach that is based on data volumes in each entity that must run an initial synchronization, see [Considerations for initial synchronization](initial-sync-guidance.md).</span></span>


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]