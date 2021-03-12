---
title: Distribuire un nuovo tenant di e-commerce
description: In questo argomento viene descritto come distribuire un nuovo sito di e-commerce Dynamics 365 Commerce utilizzando Microsoft Dynamics Lifecycle Services.
author: psimolin
manager: annbe
ms.date: 07/02/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 3b750ee89a85688dcebe673f9c3ff13693e9fcad
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4976740"
---
# <a name="deploy-a-new-e-commerce-tenant"></a><span data-ttu-id="74497-103">Distribuire un nuovo tenant di e-commerce</span><span class="sxs-lookup"><span data-stu-id="74497-103">Deploy a new e-commerce tenant</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="74497-104">In questo argomento viene descritto come distribuire un nuovo sito di e-commerce Dynamics 365 Commerce utilizzando Microsoft Dynamics Lifecycle Services.</span><span class="sxs-lookup"><span data-stu-id="74497-104">This topic describes how to deploy a new Dynamics 365 Commerce e-commerce site by using Microsoft Dynamics Lifecycle Services (LCS).</span></span>

## <a name="overview"></a><span data-ttu-id="74497-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="74497-105">Overview</span></span>

<span data-ttu-id="74497-106">Microsoft Dynamics Lifecycle Services (LCS) è un'area di lavoro collaborativa basata su cloud che i partner e i clienti possono utilizzare per gestire progetti e ambienti, visualizzare le informazioni più recenti su prodotti e funzionalità di Microsoft Dynamics nonché per creare, tenere traccia ed esaminare richieste di supporto.</span><span class="sxs-lookup"><span data-stu-id="74497-106">Microsoft Dynamics Lifecycle Services (LCS) is a cloud-based collaborative workspace that partners and customers can use to manage their projects and environments, view the latest information about Microsoft Dynamics products and features, and create, track, and browse support incidents.</span></span> <span data-ttu-id="74497-107">Le funzionalità di gestione di e-commerce sono integrate in LCS.</span><span class="sxs-lookup"><span data-stu-id="74497-107">E-commerce management features are integrated into LCS.</span></span>

<span data-ttu-id="74497-108">Per ulteriori informazioni su LCS, vedere [Manuale dell'utente di Lifecycle Services](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide).</span><span class="sxs-lookup"><span data-stu-id="74497-108">To learn more about LCS, see the [Lifecycle Services User Guide](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide).</span></span>
    
## <a name="get-started"></a><span data-ttu-id="74497-109">Attività iniziali</span><span class="sxs-lookup"><span data-stu-id="74497-109">Get started</span></span>

<span data-ttu-id="74497-110">Prima di inizializzare e-commerce, è necessario inizializzare un progetto, un ambiente e Retail Cloud Scale Unit (RCSU).</span><span class="sxs-lookup"><span data-stu-id="74497-110">Before you can initialize e-commerce, you must initialize a project, an environment, and a Retail Cloud Scale Unit (RCSU).</span></span> <span data-ttu-id="74497-111">Per eseguire l'inizializzazione in LCS, è necessario disporre delle autorizzazioni per il ruolo Proprietario progetto o Responsabile ambiente.</span><span class="sxs-lookup"><span data-stu-id="74497-111">To do the initialization in LCS, you must have permissions for either the Project Owner or Environment manager role.</span></span> <span data-ttu-id="74497-112">Le topologie dell'ambiente di produzione e sandbox sono supportate.</span><span class="sxs-lookup"><span data-stu-id="74497-112">The production and sandbox environment topologies are supported.</span></span>

<span data-ttu-id="74497-113">Per ulteriori informazioni sugli ambienti, vedere [Pianificazione ambiente](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/imp-lifecycle/environment-planning).</span><span class="sxs-lookup"><span data-stu-id="74497-113">For more information about environments, see [Environment planning](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/imp-lifecycle/environment-planning).</span></span> <span data-ttu-id="74497-114">Per ulteriori informazioni su RCSU, vedere [Inizializzare Retail Cloud Scale Unit](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/deployment/initialize-retail-channels).</span><span class="sxs-lookup"><span data-stu-id="74497-114">For more information about RCSU, see [Initialize Retail Cloud Scale Unit](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/deployment/initialize-retail-channels).</span></span>

## <a name="initialize-e-commerce"></a><span data-ttu-id="74497-115">Inizializzare e-commerce</span><span class="sxs-lookup"><span data-stu-id="74497-115">Initialize e-commerce</span></span>

<span data-ttu-id="74497-116">Utilizzare questa procedura per inizializzare la funzionalità e-commerce in un ambiente esistente.</span><span class="sxs-lookup"><span data-stu-id="74497-116">Use this procedure to initialize the e-commerce feature in an existing environment.</span></span>

<span data-ttu-id="74497-117">Prima di iniziare, verificare di disporre delle informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="74497-117">Before you begin, make sure that you have the following required information:</span></span>

- <span data-ttu-id="74497-118">L'unità RCSU che verrà utilizzata.</span><span class="sxs-lookup"><span data-stu-id="74497-118">The RCSU that will be used.</span></span>
- <span data-ttu-id="74497-119">Il gruppo di sicurezza di Microsoft Azure Active Directory che verrà utilizzato per gli amministratori del sistema di e-commerce.</span><span class="sxs-lookup"><span data-stu-id="74497-119">The Microsoft Azure Active Directory security group that will be used for e-commerce system admins.</span></span>
- <span data-ttu-id="74497-120">Il gruppo di sicurezza di Microsoft Azure Active Directory che verrà utilizzato per i moderatori di valutazioni e recensioni.</span><span class="sxs-lookup"><span data-stu-id="74497-120">The Microsoft Azure Active Directory security group that will be used for ratings and reviews moderators.</span></span>
- <span data-ttu-id="74497-121">I domini che verranno associati all'ambiente.</span><span class="sxs-lookup"><span data-stu-id="74497-121">The domains that will be associated with the environment.</span></span>

<span data-ttu-id="74497-122">Inoltre, è possibile raccogliere le seguenti informazioni facoltative:</span><span class="sxs-lookup"><span data-stu-id="74497-122">In addition, you can collect the following optional information:</span></span>

- <span data-ttu-id="74497-123">informazioni business-to-consumer (B2C) di Azure AD:</span><span class="sxs-lookup"><span data-stu-id="74497-123">Azure AD business-to-consumer (B2C) information:</span></span>

    - <span data-ttu-id="74497-124">Nome tenant</span><span class="sxs-lookup"><span data-stu-id="74497-124">Tenant Name.</span></span>
    - <span data-ttu-id="74497-125">ID client</span><span class="sxs-lookup"><span data-stu-id="74497-125">Client ID.</span></span>
    - <span data-ttu-id="74497-126">Dominio personalizzato per l'accesso</span><span class="sxs-lookup"><span data-stu-id="74497-126">Login Custom Domain.</span></span>
    - <span data-ttu-id="74497-127">URL di risposta</span><span class="sxs-lookup"><span data-stu-id="74497-127">Reply URL.</span></span>
    - <span data-ttu-id="74497-128">ID criteri di iscrizione/accesso</span><span class="sxs-lookup"><span data-stu-id="74497-128">SignUp SignIn Policy ID.</span></span>
    - <span data-ttu-id="74497-129">ID criteri di reimpostazione password</span><span class="sxs-lookup"><span data-stu-id="74497-129">Reset password Policy ID.</span></span>
    - <span data-ttu-id="74497-130">ID criteri di modifica del profilo</span><span class="sxs-lookup"><span data-stu-id="74497-130">Edit Profile Policy ID.</span></span>

> [!NOTE]
> <span data-ttu-id="74497-131">Queste informazioni possono essere aggiunte successivamente, mediante una richiesta di assistenza.</span><span class="sxs-lookup"><span data-stu-id="74497-131">This information can be added later, through a service request.</span></span>

<span data-ttu-id="74497-132">Dopo aver raccolto le informazioni necessarie, attenersi alla procedura seguente per inizializzare e-commerce.</span><span class="sxs-lookup"><span data-stu-id="74497-132">After you've collected the required information, follow these steps to initialize e-commerce.</span></span>

1. <span data-ttu-id="74497-133">Accedere a [LCS](https://lcs.dynamics.com).</span><span class="sxs-lookup"><span data-stu-id="74497-133">Sign in to [LCS](https://lcs.dynamics.com).</span></span>
1. <span data-ttu-id="74497-134">Aprire il progetto contenente l'ambiente in cui si desidera inizializzare e-commerce.</span><span class="sxs-lookup"><span data-stu-id="74497-134">Open the project that contains the environment where you want to initialize e-commerce.</span></span>
1. <span data-ttu-id="74497-135">Nella sezione **Ambienti**, selezionare l'ambiente.</span><span class="sxs-lookup"><span data-stu-id="74497-135">In the **Environments** section, select the environment.</span></span>
1. <span data-ttu-id="74497-136">In **Funzionalità ambiente**, selezionare il collegamento **Gestione vendita al dettaglio**.</span><span class="sxs-lookup"><span data-stu-id="74497-136">Under **Environment features**, select the **Retail manage** link.</span></span>
1. <span data-ttu-id="74497-137">Nella scheda **e-Commerce**, selezionare **Imposta**.</span><span class="sxs-lookup"><span data-stu-id="74497-137">On the **e-Commerce** tab, select **Setup**.</span></span> <span data-ttu-id="74497-138">Viene visualizzata una finestra di dialogo, in cui è necessario immettere le informazioni richieste per il provisioning.</span><span class="sxs-lookup"><span data-stu-id="74497-138">A dialog box appears, where you must enter the information that is required for provisioning.</span></span>
1. <span data-ttu-id="74497-139">Immettere le informazioni necessarie e passare alla pagina successiva.</span><span class="sxs-lookup"><span data-stu-id="74497-139">Fill in the required information, and then go to the next page.</span></span>
1. <span data-ttu-id="74497-140">Nella pagina successiva, immettere le informazioni necessarie e inviare il modulo.</span><span class="sxs-lookup"><span data-stu-id="74497-140">On the next page, fill in the required information, and then submit the form.</span></span> <span data-ttu-id="74497-141">Viene visualizzata di nuovo la scheda **e-Commerce**, che dovrebbe indicare l'avvio dell'inizializzazione.</span><span class="sxs-lookup"><span data-stu-id="74497-141">You're returned to the **e-Commerce** tab, where you should see that initialization has been started.</span></span>
1. <span data-ttu-id="74497-142">Per visualizzare lo stato dell'inizializzazione, selezionare **Aggiorna** o ritornare in seguito alla scheda **e-Commerce**.</span><span class="sxs-lookup"><span data-stu-id="74497-142">To view the initialization status, either **Refresh** or return to the **e-Commerce** tab later.</span></span>
    
<span data-ttu-id="74497-143">Quando e-commerce viene inizializzato da LCs, il sistema esegue il provisioning di vari componenti necessari per e-commerce e li associa all'ambiente.</span><span class="sxs-lookup"><span data-stu-id="74497-143">When e-commerce is initialized from LCS, the system provisions several components that are required for e-commerce and associates them with the environment.</span></span> <span data-ttu-id="74497-144">Al termine del provisioning, la scheda **e-Commerce** nella pagina **Gestione vendita al dettaglio** viene aggiornata in base al provisioning.</span><span class="sxs-lookup"><span data-stu-id="74497-144">After provisioning is complete, the **e-Commerce** tab on the **Retail management** page is updated to reflect the provisioning.</span></span> <span data-ttu-id="74497-145">Nella pagina sono indicate le distribuzioni di personalizzazioni più recenti e lo stato di qualsiasi altra distribuzione in corso.</span><span class="sxs-lookup"><span data-stu-id="74497-145">The page shows the latest customization deployments and the status of any other ongoing deployments.</span></span> <span data-ttu-id="74497-146">Include inoltre collegamenti al sito di e-commerce e a Creazione di siti di Commerce dove i siti vengono creati.</span><span class="sxs-lookup"><span data-stu-id="74497-146">It also includes links to the e-commerce site and the Commerce site builder where sites are authored.</span></span>

## <a name="access-commerce-site-builder"></a><span data-ttu-id="74497-147">Accedere a Creazione di siti di Commerce</span><span class="sxs-lookup"><span data-stu-id="74497-147">Access Commerce site builder</span></span>

<span data-ttu-id="74497-148">Per accedere a Creazione di siti di Commerce, selezionare la scheda **e-Commerce** nella pagina **Gestione vendita al dettaglio** in LCS e selezionare il collegamento **Strumento di gestione del sito e-Commerce**.</span><span class="sxs-lookup"><span data-stu-id="74497-148">To access Commerce site builder, go to the **e-Commerce** tab on the **Retail management** page in LCS and select the **e-Commerce site management tool** link.</span></span> <span data-ttu-id="74497-149">La pagina di destinazione di Creazione di siti Web visualizza una vista a livello di tenant.</span><span class="sxs-lookup"><span data-stu-id="74497-149">The site builder landing page displays a tenant-level view.</span></span> <span data-ttu-id="74497-150">In questa pagina è possibile:</span><span class="sxs-lookup"><span data-stu-id="74497-150">From this page, you can:</span></span>

- <span data-ttu-id="74497-151">Modificare le impostazioni a livello di tenant.</span><span class="sxs-lookup"><span data-stu-id="74497-151">Modify tenant-level settings.</span></span>
- <span data-ttu-id="74497-152">Accedere a qualsiasi sito creato e disporre dell'autorizzazione per visualizzare.</span><span class="sxs-lookup"><span data-stu-id="74497-152">Navigate to any site you have created, and have permission to view.</span></span> 
- <span data-ttu-id="74497-153">Accedere alle funzionalità di verifica come Moderazione e Report.</span><span class="sxs-lookup"><span data-stu-id="74497-153">Access Reviews features such as moderation and reporting.</span></span>
- <span data-ttu-id="74497-154">Creare un nuovo sito.</span><span class="sxs-lookup"><span data-stu-id="74497-154">Create a new site.</span></span> <span data-ttu-id="74497-155">Per ulteriori informazioni su come creare un nuovo sito, vedere [Creare un sito di e-commerce](create-ecommerce-site.md).</span><span class="sxs-lookup"><span data-stu-id="74497-155">For more information about how to create a new site, see [Create an e-commerce site](create-ecommerce-site.md) .</span></span> 

## <a name="additional-resources"></a><span data-ttu-id="74497-156">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="74497-156">Additional resources</span></span>

[<span data-ttu-id="74497-157">Configurare il proprio nome di dominio</span><span class="sxs-lookup"><span data-stu-id="74497-157">Configure your domain name</span></span>](configure-your-domain-name.md)

[<span data-ttu-id="74497-158">Creare un sito di e-commerce</span><span class="sxs-lookup"><span data-stu-id="74497-158">Create an e-commerce site</span></span>](create-ecommerce-site.md)

[<span data-ttu-id="74497-159">Associare un sito Dynamics 365 Commerce a un canale online</span><span class="sxs-lookup"><span data-stu-id="74497-159">Associate a Dynamics 365 Commerce site with an online channel</span></span>](associate-site-online-store.md)

[<span data-ttu-id="74497-160">Gestire i file robots.txt</span><span class="sxs-lookup"><span data-stu-id="74497-160">Manage robots.txt files</span></span>](manage-robots-txt-files.md)

[<span data-ttu-id="74497-161">Caricare reindirizzamenti URL in blocco</span><span class="sxs-lookup"><span data-stu-id="74497-161">Upload URL redirects in bulk</span></span>](upload-bulk-redirects.md)

[<span data-ttu-id="74497-162">Impostare un tenant B2C in Commerce</span><span class="sxs-lookup"><span data-stu-id="74497-162">Set up a B2C tenant in Commerce</span></span>](set-up-B2C-tenant.md)

[<span data-ttu-id="74497-163">Impostare pagine personalizzate per l'accesso degli utenti</span><span class="sxs-lookup"><span data-stu-id="74497-163">Set up custom pages for user logins</span></span>](custom-pages-user-logins.md)

[<span data-ttu-id="74497-164">Configurare più tenant B2C in un ambiente Commerce</span><span class="sxs-lookup"><span data-stu-id="74497-164">Configure multiple B2C tenants in a Commerce environment</span></span>](configure-multi-B2C-tenants.md)

[<span data-ttu-id="74497-165">Aggiungere il supporto per una rete per la distribuzione di contenuti (CDN)</span><span class="sxs-lookup"><span data-stu-id="74497-165">Add support for a content delivery network (CDN)</span></span>](add-cdn-support.md)

[<span data-ttu-id="74497-166">Abilitare il rilevamento del punto vendita basato sull'ubicazione</span><span class="sxs-lookup"><span data-stu-id="74497-166">Enable location-based store detection</span></span>](enable-store-detection.md)
