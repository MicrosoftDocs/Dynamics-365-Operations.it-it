---
title: Distribuire un nuovo tenant di e-Commerce
description: In questo argomento viene descritto come distribuire un nuovo tenant di e-Commerce utilizzando Microsoft Dynamics Lifecycle Services.
author: psimolin
manager: annbe
ms.date: 10/31/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 10dab1e62446ff7f60ad48fd0841bde5cfd29e12
ms.sourcegitcommit: ef3a1d7527311d00b69a1072ae5eb021ce68034c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2020
ms.locfileid: "2945515"
---
# <a name="deploy-a-new-e-commerce-tenant"></a><span data-ttu-id="1e33d-103">Distribuire un nuovo tenant di e-Commerce</span><span class="sxs-lookup"><span data-stu-id="1e33d-103">Deploy a new e-Commerce tenant</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="1e33d-104">In questo argomento viene descritto come distribuire un nuovo sito di e-Commerce utilizzando Microsoft Dynamics Lifecycle Services.</span><span class="sxs-lookup"><span data-stu-id="1e33d-104">This topic describes how to deploy a new e-Commerce site by using Microsoft Dynamics Lifecycle Services (LCS).</span></span>

## <a name="overview"></a><span data-ttu-id="1e33d-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="1e33d-105">Overview</span></span>
    
<span data-ttu-id="1e33d-106">Microsoft Dynamics Lifecycle Services (LCS) è un'area di lavoro collaborativa basata su cloud che i partner e i clienti possono utilizzare per gestire progetti e ambienti, visualizzare le informazioni più recenti su prodotti e funzionalità di Microsoft Dynamics nonché per creare, tenere traccia ed esaminare richieste di supporto.</span><span class="sxs-lookup"><span data-stu-id="1e33d-106">Microsoft Dynamics Lifecycle Services (LCS) is a cloud-based collaborative workspace that partners and customers can use to manage their projects and environments, view the latest information about Microsoft Dynamics products and features, and create, track, and browse support incidents.</span></span> <span data-ttu-id="1e33d-107">Le funzionalità di gestione di e-Commerce sono integrate in LCS.</span><span class="sxs-lookup"><span data-stu-id="1e33d-107">E-Commerce management features are integrated into LCS.</span></span>

<span data-ttu-id="1e33d-108">Per ulteriori informazioni su LCS, vedere [Manuale dell'utente di Lifecycle Services](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide).</span><span class="sxs-lookup"><span data-stu-id="1e33d-108">To learn more about LCS, see the [Lifecycle Services User Guide](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide).</span></span>
    
## <a name="get-started"></a><span data-ttu-id="1e33d-109">Inizia subito</span><span class="sxs-lookup"><span data-stu-id="1e33d-109">Get started</span></span>

<span data-ttu-id="1e33d-110">Prima di inizializzare e-Commerce, è necessario inizializzare un progetto, un ambiente e Retail Cloud Scale Unit (RCSU).</span><span class="sxs-lookup"><span data-stu-id="1e33d-110">Before you can initialize e-Commerce, you must initialize a project, an environment, and a Retail Cloud Scale Unit (RCSU).</span></span> <span data-ttu-id="1e33d-111">Per eseguire l'inizializzazione in LCS, è necessario disporre delle autorizzazioni per il ruolo Proprietario progetto o Responsabile ambiente.</span><span class="sxs-lookup"><span data-stu-id="1e33d-111">To do the initialization in LCS, you must have permissions for either the Project Owner or Environment manager role.</span></span> <span data-ttu-id="1e33d-112">Le topologie dell'ambiente di produzione e sandbox sono supportate.</span><span class="sxs-lookup"><span data-stu-id="1e33d-112">The production and sandbox environment topologies are supported.</span></span>

<span data-ttu-id="1e33d-113">Per ulteriori informazioni sugli ambienti, vedere [Pianificazione ambiente](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/imp-lifecycle/environment-planning).</span><span class="sxs-lookup"><span data-stu-id="1e33d-113">For more information about environments, see [Environment planning](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/imp-lifecycle/environment-planning).</span></span> <span data-ttu-id="1e33d-114">Per ulteriori informazioni su RCSU, vedere [Inizializzare Retail Cloud Scale Unit](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/deployment/initialize-retail-channels).</span><span class="sxs-lookup"><span data-stu-id="1e33d-114">For more information about RCSU, see [Initialize Retail Cloud Scale Unit](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/deployment/initialize-retail-channels).</span></span>

## <a name="initialize-e-commerce"></a><span data-ttu-id="1e33d-115">Inizializzare e-Commerce</span><span class="sxs-lookup"><span data-stu-id="1e33d-115">Initialize e-Commerce</span></span>

<span data-ttu-id="1e33d-116">Utilizzare questa procedura per inizializzare la funzionalità e-Commerce in un ambiente esistente.</span><span class="sxs-lookup"><span data-stu-id="1e33d-116">Use this procedure to initialize the e-Commerce feature in an existing environment.</span></span>

<span data-ttu-id="1e33d-117">Prima di iniziare, verificare di disporre delle informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="1e33d-117">Before you begin, make sure that you have the following required information:</span></span>

- <span data-ttu-id="1e33d-118">L'unità RCSU che verrà utilizzata.</span><span class="sxs-lookup"><span data-stu-id="1e33d-118">The RCSU that will be used.</span></span>
- <span data-ttu-id="1e33d-119">Il gruppo di sicurezza di Microsoft Azure Active Directory che verrà utilizzato per gli amministratori del sistema di e-Commerce.</span><span class="sxs-lookup"><span data-stu-id="1e33d-119">The Microsoft Azure Active Directory security group that will be used for e-Commerce system admins.</span></span>
- <span data-ttu-id="1e33d-120">Il gruppo di sicurezza di Microsoft Azure Active Directory che verrà utilizzato per i moderatori di valutazioni e recensioni.</span><span class="sxs-lookup"><span data-stu-id="1e33d-120">The Microsoft Azure Active Directory security group that will be used for ratings and reviews moderators.</span></span>
- <span data-ttu-id="1e33d-121">I domini che verranno associati all'ambiente.</span><span class="sxs-lookup"><span data-stu-id="1e33d-121">The domains that will be associated with the environment.</span></span>

<span data-ttu-id="1e33d-122">Inoltre, è possibile raccogliere le seguenti informazioni facoltative:</span><span class="sxs-lookup"><span data-stu-id="1e33d-122">In addition, you can collect the following optional information:</span></span>

- <span data-ttu-id="1e33d-123">informazioni business-to-consumer (B2C) di Azure AD:</span><span class="sxs-lookup"><span data-stu-id="1e33d-123">Azure AD business-to-consumer (B2C) information:</span></span>

    - <span data-ttu-id="1e33d-124">Nome tenant</span><span class="sxs-lookup"><span data-stu-id="1e33d-124">Tenant Name.</span></span>
    - <span data-ttu-id="1e33d-125">ID client</span><span class="sxs-lookup"><span data-stu-id="1e33d-125">Client ID.</span></span>
    - <span data-ttu-id="1e33d-126">Dominio personalizzato per l'accesso</span><span class="sxs-lookup"><span data-stu-id="1e33d-126">Login Custom Domain.</span></span>
    - <span data-ttu-id="1e33d-127">URL di risposta</span><span class="sxs-lookup"><span data-stu-id="1e33d-127">Reply URL.</span></span>
    - <span data-ttu-id="1e33d-128">ID criteri di iscrizione/accesso</span><span class="sxs-lookup"><span data-stu-id="1e33d-128">SignUp SignIn Policy ID.</span></span>
    - <span data-ttu-id="1e33d-129">ID criteri di reimpostazione password</span><span class="sxs-lookup"><span data-stu-id="1e33d-129">Reset password Policy ID.</span></span>
    - <span data-ttu-id="1e33d-130">ID criteri di modifica del profilo</span><span class="sxs-lookup"><span data-stu-id="1e33d-130">Edit Profile Policy ID.</span></span>

[!NOTE]
<span data-ttu-id="1e33d-131">Queste informazioni possono essere aggiunte successivamente, mediante una richiesta di assistenza.</span><span class="sxs-lookup"><span data-stu-id="1e33d-131">This information can be added later, through a service request.</span></span>

<span data-ttu-id="1e33d-132">Dopo aver raccolto le informazioni necessarie, attenersi alla procedura seguente per inizializzare e-Commerce.</span><span class="sxs-lookup"><span data-stu-id="1e33d-132">After you've collected the required information, follow these steps to initialize e-Commerce.</span></span>

1. <span data-ttu-id="1e33d-133">Accedere a [LCS](https://lcs.dynamics.com).</span><span class="sxs-lookup"><span data-stu-id="1e33d-133">Sign in to [LCS](https://lcs.dynamics.com).</span></span>
1. <span data-ttu-id="1e33d-134">Aprire il progetto contenente l'ambiente in cui si desidera inizializzare e-Commerce.</span><span class="sxs-lookup"><span data-stu-id="1e33d-134">Open the project that contains the environment where you want to initialize e-Commerce.</span></span>
1. <span data-ttu-id="1e33d-135">Nella sezione **Ambienti**, selezionare l'ambiente.</span><span class="sxs-lookup"><span data-stu-id="1e33d-135">In the **Environments** section, select the environment.</span></span>
1. <span data-ttu-id="1e33d-136">In **Funzionalità ambiente**, selezionare il collegamento **Gestione vendita al dettaglio**.</span><span class="sxs-lookup"><span data-stu-id="1e33d-136">Under **Environment features**, select the **Retail manage** link.</span></span>
1. <span data-ttu-id="1e33d-137">Nella scheda **e-Commerce**, selezionare **Imposta**.</span><span class="sxs-lookup"><span data-stu-id="1e33d-137">On the **e-Commerce** tab, select **Setup**.</span></span> <span data-ttu-id="1e33d-138">Viene visualizzata una finestra di dialogo, in cui è necessario immettere le informazioni richieste per il provisioning.</span><span class="sxs-lookup"><span data-stu-id="1e33d-138">A dialog box appears, where you must enter the information that is required for provisioning.</span></span>
1. <span data-ttu-id="1e33d-139">Immettere le informazioni necessarie e passare alla pagina successiva.</span><span class="sxs-lookup"><span data-stu-id="1e33d-139">Fill in the required information, and then go to the next page.</span></span>
1. <span data-ttu-id="1e33d-140">Nella pagina successiva, immettere le informazioni necessarie e inviare il modulo.</span><span class="sxs-lookup"><span data-stu-id="1e33d-140">On the next page, fill in the required information, and then submit the form.</span></span> <span data-ttu-id="1e33d-141">Viene visualizzata di nuovo la scheda **e-Commerce**, che dovrebbe indicare l'avvio dell'inizializzazione.</span><span class="sxs-lookup"><span data-stu-id="1e33d-141">You're returned to the **e-Commerce** tab, where you should see that initialization has been started.</span></span>
1. <span data-ttu-id="1e33d-142">Per visualizzare lo stato dell'inizializzazione, selezionare **Aggiorna** o ritornare in seguito alla scheda **e-Commerce**.</span><span class="sxs-lookup"><span data-stu-id="1e33d-142">To view the initialization status, either **Refresh** or return to the **e-Commerce** tab later.</span></span>
    
<span data-ttu-id="1e33d-143">Quando e-Commerce viene inizializzato da LCs, il sistema esegue il provisioning di vari componenti necessari per e-Commerce e li associa all'ambiente.</span><span class="sxs-lookup"><span data-stu-id="1e33d-143">When e-Commerce is initialized from LCS, the system provisions several components that are required for e-Commerce and associates them with the environment.</span></span> <span data-ttu-id="1e33d-144">Al termine del provisioning, la scheda **e-Commerce** nella pagina **Gestione vendita al dettaglio** viene aggiornata in base al provisioning.</span><span class="sxs-lookup"><span data-stu-id="1e33d-144">After provisioning is completed, the **e-Commerce** tab on the **Retail management** page is updated to reflect the provisioning.</span></span> <span data-ttu-id="1e33d-145">Nella pagina sono indicate le distribuzioni di personalizzazioni più recenti e lo stato di qualsiasi altra distribuzione in corso.</span><span class="sxs-lookup"><span data-stu-id="1e33d-145">The page shows the latest customization deployments and the status of any other ongoing deployments.</span></span> <span data-ttu-id="1e33d-146">Include inoltre collegamenti al sito di e-Commerce e lo strumento di gestione del sito di e-Commerce (strumento di creazione).</span><span class="sxs-lookup"><span data-stu-id="1e33d-146">It also includes links to the e-Commerce site and the e-Commerce site management tool (the authoring tool).</span></span>

## <a name="access-the-authoring-environment"></a><span data-ttu-id="1e33d-147">Accedere all'ambiente di creazione</span><span class="sxs-lookup"><span data-stu-id="1e33d-147">Access the authoring environment</span></span>

<span data-ttu-id="1e33d-148">Per accedere all'ambiente di creazione, passare alla scheda **e-Commerce** nella pagina **Gestione vendita al dettaglio**.</span><span class="sxs-lookup"><span data-stu-id="1e33d-148">To access the authoring environment, go to the **e-Commerce** tab on the **Retail management** page.</span></span> <span data-ttu-id="1e33d-149">La scheda include i collegamenti al sito di e-Commerce e lo strumento di gestione del sito.</span><span class="sxs-lookup"><span data-stu-id="1e33d-149">There, you will find links to your e-Commerce site and the site management tool.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="1e33d-150">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="1e33d-150">Additional resources</span></span>

[<span data-ttu-id="1e33d-151">Configurare il proprio nome di dominio</span><span class="sxs-lookup"><span data-stu-id="1e33d-151">Configure your domain name</span></span>](configure-your-domain-name.md)

[<span data-ttu-id="1e33d-152">Creare un sito di e-commerce</span><span class="sxs-lookup"><span data-stu-id="1e33d-152">Create an e-Commerce site</span></span>](create-ecommerce-site.md)

[<span data-ttu-id="1e33d-153">Associare un sito online a un canale</span><span class="sxs-lookup"><span data-stu-id="1e33d-153">Associate an online site with a channel</span></span>](associate-site-online-store.md)

[<span data-ttu-id="1e33d-154">Gestire i file robots.txt</span><span class="sxs-lookup"><span data-stu-id="1e33d-154">Manage robots.txt files</span></span>](manage-robots-txt-files.md)

[<span data-ttu-id="1e33d-155">Impostare pagine personalizzate per l'accesso degli utenti</span><span class="sxs-lookup"><span data-stu-id="1e33d-155">Set up custom pages for user logins</span></span>](custom-pages-user-logins.md)

[<span data-ttu-id="1e33d-156">Aggiungere il supporto per una rete per la distribuzione di contenuti (CDN)</span><span class="sxs-lookup"><span data-stu-id="1e33d-156">Add support for a content delivery network (CDN)</span></span>](add-cdn-support.md)

[<span data-ttu-id="1e33d-157">Abilitare il rilevamento del punto vendita basato sull'ubicazione</span><span class="sxs-lookup"><span data-stu-id="1e33d-157">Enable location-based store detection</span></span>](enable-store-detection.md)
