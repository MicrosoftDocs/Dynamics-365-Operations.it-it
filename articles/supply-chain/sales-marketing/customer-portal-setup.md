---
title: Installare, configurare e aggiornare il portale clienti
description: Questo argomento fornisce dettagli sulle licenze e istruzioni per la configurazione del portale clienti.
author: dasani-madipalli
manager: tfehr
ms.date: 04/22/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: damadipa
ms.search.validFrom: 2020-04-22
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: b9d1e742f78254d949dc49fda008d63b8bff4d65
ms.sourcegitcommit: 713b5dfc76a6875d0ba6d86c5cbd585ea502cf9d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/01/2020
ms.locfileid: "3413978"
---
# <a name="install-set-up-and-update-the-customer-portal"></a><span data-ttu-id="2bdfb-103">Installare, configurare e aggiornare il portale clienti</span><span class="sxs-lookup"><span data-stu-id="2bdfb-103">Install, set up, and update the Customer portal</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="2bdfb-104">Requisiti di licenza</span><span class="sxs-lookup"><span data-stu-id="2bdfb-104">Licensing requirements</span></span>

<span data-ttu-id="2bdfb-105">Per implementare il portale clienti, è necessario disporre delle seguenti licenze:</span><span class="sxs-lookup"><span data-stu-id="2bdfb-105">To implement the Customer portal, you must have the following licenses:</span></span>

- <span data-ttu-id="2bdfb-106">**Portali Power Apps** - Questa licenza è richiesta per ospitare il portale clienti.</span><span class="sxs-lookup"><span data-stu-id="2bdfb-106">**Power Apps portals** – This license is required to host the Customer portal.</span></span> <span data-ttu-id="2bdfb-107">I portali sono concessi in licenza in base all'utilizzo.</span><span class="sxs-lookup"><span data-stu-id="2bdfb-107">Portals are licensed based on usage.</span></span> <span data-ttu-id="2bdfb-108">Per ulteriori informazioni, consultare [Requisiti di licenza per portali Power Apps](https://docs.microsoft.com/power-platform/admin/powerapps-flow-licensing-faq#portals).</span><span class="sxs-lookup"><span data-stu-id="2bdfb-108">For more information, see the [Power Apps portals licensing requirements](https://docs.microsoft.com/power-platform/admin/powerapps-flow-licensing-faq#portals).</span></span>
- <span data-ttu-id="2bdfb-109">**Doppia scrittura** - È necessario disporre delle licenze necessarie per abilitare la doppia scrittura per le entità Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="2bdfb-109">**Dual-write** – You must have the necessary licenses to enable dual-write for Supply Chain Management entities.</span></span> <span data-ttu-id="2bdfb-110">Per ulteriori informazioni, vedere i [Requisiti di sistema per la doppia scrittura](../../fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-system-req.md).</span><span class="sxs-lookup"><span data-stu-id="2bdfb-110">For more information, see the [system requirements for dual-write](../../fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-system-req.md).</span></span>

## <a name="dependencies-on-dual-write-and-power-apps-portals"></a><span data-ttu-id="2bdfb-111">Dipendenze da doppia scrittura e portali Power Apps</span><span class="sxs-lookup"><span data-stu-id="2bdfb-111">Dependencies on dual-write and Power Apps portals</span></span>

<span data-ttu-id="2bdfb-112">Il portale clienti dipende dai portali Power Apps e dalla doppia scrittura, come mostrato nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="2bdfb-112">The Customer portal depends on Power Apps portals and dual-write, as shown in the following illustration.</span></span>

![![Dipendenze del portale clienti](media/customer-portal-elements.png "Dipendenze del portale clienti")](media/customer-portal-elements.png "Customer portal dependencies")

<span data-ttu-id="2bdfb-114">A differenza di altre funzionalità di Supply Chain Management, il modello di portale clienti risiede nei portali Power Apps.</span><span class="sxs-lookup"><span data-stu-id="2bdfb-114">Unlike other features from Supply Chain Management, the Customer portal template resides in Power Apps portals.</span></span> <span data-ttu-id="2bdfb-115">Pertanto, il portale clienti è limitato dalle funzionalità fornite dai portali  Power Apps e dalle entità in doppia scrittura.</span><span class="sxs-lookup"><span data-stu-id="2bdfb-115">Therefore, the Customer portal is limited by the functionality and capabilities that are provided by Power Apps portals and the entities in dual-write.</span></span>

## <a name="required-setup-to-enable-the-customer-portal"></a><a name="required-setup"></a><span data-ttu-id="2bdfb-116">Configurazione richiesta per abilitare il portale clienti</span><span class="sxs-lookup"><span data-stu-id="2bdfb-116">Required setup to enable the Customer portal</span></span>

<span data-ttu-id="2bdfb-117">Dopo aver verificato di disporre delle licenze necessarie, è possibile configurare la doppia scrittura come descritto in [Istruzioni di sincronizzazione iniziale con doppia scrittura](../../fin-ops-core/dev-itpro/data-entities/dual-write/initial-sync.md).</span><span class="sxs-lookup"><span data-stu-id="2bdfb-117">After you've made sure that you have the required licenses, you can set up dual-write as described in the [dual-write initial synchronization instructions](../../fin-ops-core/dev-itpro/data-entities/dual-write/initial-sync.md).</span></span>

<span data-ttu-id="2bdfb-118">Assicurarsi di abilitare i seguenti mapping di entità in doppia scrittura:</span><span class="sxs-lookup"><span data-stu-id="2bdfb-118">Be sure to enable the following entity mappings in dual-write:</span></span>

- <span data-ttu-id="2bdfb-119">Intestazione ordine cliente</span><span class="sxs-lookup"><span data-stu-id="2bdfb-119">Sales Order Header</span></span>
- <span data-ttu-id="2bdfb-120">Dettagli ordini cliente</span><span class="sxs-lookup"><span data-stu-id="2bdfb-120">Sales Order Details</span></span>
- <span data-ttu-id="2bdfb-121">Conti</span><span class="sxs-lookup"><span data-stu-id="2bdfb-121">Accounts</span></span>
- <span data-ttu-id="2bdfb-122">Contatti</span><span class="sxs-lookup"><span data-stu-id="2bdfb-122">Contacts</span></span>
- <span data-ttu-id="2bdfb-123">Prodotti</span><span class="sxs-lookup"><span data-stu-id="2bdfb-123">Products</span></span>

<span data-ttu-id="2bdfb-124">Al termine della configurazione, è possibile eseguire il provisioning del modello di portale clienti.</span><span class="sxs-lookup"><span data-stu-id="2bdfb-124">After this setup is completed, you can provision the Customer portal template.</span></span>

## <a name="provision-the-customer-portal"></a><span data-ttu-id="2bdfb-125">Provisioning del portale clienti</span><span class="sxs-lookup"><span data-stu-id="2bdfb-125">Provision the Customer portal</span></span>

<span data-ttu-id="2bdfb-126">Prima di iniziare, assicurarsi di aver già completato la [configurazione richiesta](#required-setup).</span><span class="sxs-lookup"><span data-stu-id="2bdfb-126">Before you begin, make sure that you've already completed the [required setup](#required-setup).</span></span> <span data-ttu-id="2bdfb-127">Quindi seguire questi passaggi per eseguire il provisioning del portale clienti.</span><span class="sxs-lookup"><span data-stu-id="2bdfb-127">Then follow these steps to provision the Customer portal.</span></span>

1. <span data-ttu-id="2bdfb-128">Andare a [make.powerapps.com](https://make.powerapps.com/).</span><span class="sxs-lookup"><span data-stu-id="2bdfb-128">Go to [make.powerapps.com](https://make.powerapps.com/).</span></span>
2. <span data-ttu-id="2bdfb-129">Assicurarsi di utilizzare l'ambiente in cui la doppia scrittura è stata abilitata.</span><span class="sxs-lookup"><span data-stu-id="2bdfb-129">Make sure that you're using the environment where you enabled dual-write.</span></span>
3. <span data-ttu-id="2bdfb-130">Nella scheda **Crea**, scorrere verso il basso fino alla sezione **Inizia da modello** e selezionare il modello denominato **Cliente Supply Chain Management**.</span><span class="sxs-lookup"><span data-stu-id="2bdfb-130">On the **Create** tab, scroll down to the **Start from template** section, and select the template that is named **Supply Chain Management Customer**.</span></span>
4. <span data-ttu-id="2bdfb-131">Seguire le istruzioni visualizzate.</span><span class="sxs-lookup"><span data-stu-id="2bdfb-131">Follow the on-screen instructions.</span></span>

<span data-ttu-id="2bdfb-132">Una volta completato il provisioning, è possibile accedere al portale clienti nella sezione **App personali** della **Home page**.</span><span class="sxs-lookup"><span data-stu-id="2bdfb-132">After provisioning is completed, you can access the Customer portal in the **Your apps** section of the **Home** page.</span></span>

> [!NOTE]
> <span data-ttu-id="2bdfb-133">Se la soluzione di doppia scrittura non è installata nell'ambiente in cui si sta lavorando, verrà visualizzato un messaggio di errore e il provisioning del portale clienti non verrà eseguito.</span><span class="sxs-lookup"><span data-stu-id="2bdfb-133">If the dual-write solution isn't installed in the environment that you're working in, you will receive an error message, and the Customer portal won't be provisioned.</span></span>

## <a name="update-the-customer-portal"></a><span data-ttu-id="2bdfb-134">Aggiornare il portale clienti</span><span class="sxs-lookup"><span data-stu-id="2bdfb-134">Update the Customer portal</span></span>

<span data-ttu-id="2bdfb-135">Ulteriori funzionalità potrebbero essere aggiunte al portale clienti in seguito.</span><span class="sxs-lookup"><span data-stu-id="2bdfb-135">More functionality might be added to the Customer portal later.</span></span> <span data-ttu-id="2bdfb-136">Qualsiasi modifica apportata da Microsoft ai componenti della soluzione sottostante apparirà automaticamente nell'ambiente corrente.</span><span class="sxs-lookup"><span data-stu-id="2bdfb-136">Any changes that Microsoft makes to the underlying solution components will automatically appear in your environment.</span></span> <span data-ttu-id="2bdfb-137">Tuttavia, il sito Web di cui viene eseguito il provisioning nell'ambiente non rifletterà automaticamente le modifiche apportate ai dati di configurazione.</span><span class="sxs-lookup"><span data-stu-id="2bdfb-137">However, the website that is provisioned in your environment won't automatically reflect changes that are made to the configuration data.</span></span> <span data-ttu-id="2bdfb-138">Sarà necessario applicare manualmente tali modifiche ottenendo il codice dal nuovo modello ed eseguendone il merging con il sito Web di cui è stato eseguito il provisioning.</span><span class="sxs-lookup"><span data-stu-id="2bdfb-138">You will have to manually apply those changes by getting the code from the new template and merging it with the provisioned website.</span></span>

## <a name="resources"></a><span data-ttu-id="2bdfb-139">Risorse</span><span class="sxs-lookup"><span data-stu-id="2bdfb-139">Resources</span></span>

<span data-ttu-id="2bdfb-140">Per informazioni su come configurare e personalizzare il portale clienti, è necessario consultare la seguente documentazione per le tecnologie sottostanti:</span><span class="sxs-lookup"><span data-stu-id="2bdfb-140">To learn how you can set up and customize the Customer portal, you should start by reviewing the following documentation for the underlying technologies:</span></span>

- [<span data-ttu-id="2bdfb-141">Documentazione sui portali Power Apps</span><span class="sxs-lookup"><span data-stu-id="2bdfb-141">Power Apps portals documentation</span></span>](https://docs.microsoft.com/powerapps/maker/portals/overview)
- [<span data-ttu-id="2bdfb-142">Documentazione sulla doppia scrittura</span><span class="sxs-lookup"><span data-stu-id="2bdfb-142">Dual-write documentation</span></span>](../../fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-home-page.md)

<span data-ttu-id="2bdfb-143">Per gestire efficacemente i portali, è necessario acquisire familiarità con i portali Power Apps e il ciclo di vita di Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="2bdfb-143">To effectively manage your portals, you must understand the Power Apps portals and Common Data Service lifecycle.</span></span> <span data-ttu-id="2bdfb-144">Per ulteriori informazioni, vedi le seguenti risorse:</span><span class="sxs-lookup"><span data-stu-id="2bdfb-144">For more information, see the following resources:</span></span>

- [<span data-ttu-id="2bdfb-145">Informazioni sul ciclo di vita dei portali</span><span class="sxs-lookup"><span data-stu-id="2bdfb-145">About portal lifecycle</span></span>](https://docs.microsoft.com/powerapps/maker/portals/admin/portal-lifecycle)
- [<span data-ttu-id="2bdfb-146">Aggiornare un portale</span><span class="sxs-lookup"><span data-stu-id="2bdfb-146">Upgrade a portal</span></span>](https://docs.microsoft.com/powerapps/maker/portals/admin/upgrade-portal)
- [<span data-ttu-id="2bdfb-147">Migrare la configurazione del portale</span><span class="sxs-lookup"><span data-stu-id="2bdfb-147">Migrate portal configuration</span></span>](https://docs.microsoft.com/powerapps/maker/portals/admin/migrate-portal-configuration)
- [<span data-ttu-id="2bdfb-148">Gestione del ciclo di vita delle soluzioni: app Dynamics 365 for Customer Engagement</span><span class="sxs-lookup"><span data-stu-id="2bdfb-148">Solution Lifecycle Management: Dynamics 365 for Customer Engagement apps</span></span>](https://www.microsoft.com/download/details.aspx?id=57777)
