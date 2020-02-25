---
title: Distribuire un nuovo tenant di e-Commerce
description: In questo argomento viene descritto come distribuire un nuovo tenant di e-Commerce utilizzando Microsoft Dynamics Lifecycle Services.
author: psimolin
manager: annbe
ms.date: 01/23/2020
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
ms.openlocfilehash: 6d7dfcaf244260de5f39a1201ec1ea78e94351e7
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/01/2020
ms.locfileid: "3001785"
---
# <a name="deploy-a-new-e-commerce-tenant"></a><span data-ttu-id="953b3-103">Distribuire un nuovo tenant di e-Commerce</span><span class="sxs-lookup"><span data-stu-id="953b3-103">Deploy a new e-Commerce tenant</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="953b3-104">In questo argomento viene descritto come distribuire un nuovo sito di e-Commerce utilizzando Microsoft Dynamics Lifecycle Services.</span><span class="sxs-lookup"><span data-stu-id="953b3-104">This topic describes how to deploy a new e-Commerce site by using Microsoft Dynamics Lifecycle Services (LCS).</span></span>

## <a name="overview"></a><span data-ttu-id="953b3-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="953b3-105">Overview</span></span>

<span data-ttu-id="953b3-106">Microsoft Dynamics Lifecycle Services (LCS) è un'area di lavoro collaborativa basata su cloud che i partner e i clienti possono utilizzare per gestire progetti e ambienti, visualizzare le informazioni più recenti su prodotti e funzionalità di Microsoft Dynamics nonché per creare, tenere traccia ed esaminare richieste di supporto.</span><span class="sxs-lookup"><span data-stu-id="953b3-106">Microsoft Dynamics Lifecycle Services (LCS) is a cloud-based collaborative workspace that partners and customers can use to manage their projects and environments, view the latest information about Microsoft Dynamics products and features, and create, track, and browse support incidents.</span></span> <span data-ttu-id="953b3-107">Le funzionalità di gestione di e-Commerce sono integrate in LCS.</span><span class="sxs-lookup"><span data-stu-id="953b3-107">E-Commerce management features are integrated into LCS.</span></span>

<span data-ttu-id="953b3-108">Per ulteriori informazioni su LCS, vedere [Manuale dell'utente di Lifecycle Services](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide).</span><span class="sxs-lookup"><span data-stu-id="953b3-108">To learn more about LCS, see the [Lifecycle Services User Guide](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide).</span></span>
    
## <a name="get-started"></a><span data-ttu-id="953b3-109">Inizia subito</span><span class="sxs-lookup"><span data-stu-id="953b3-109">Get started</span></span>

<span data-ttu-id="953b3-110">Prima di inizializzare e-Commerce, è necessario inizializzare un progetto, un ambiente e Retail Cloud Scale Unit (RCSU).</span><span class="sxs-lookup"><span data-stu-id="953b3-110">Before you can initialize e-Commerce, you must initialize a project, an environment, and a Retail Cloud Scale Unit (RCSU).</span></span> <span data-ttu-id="953b3-111">Per eseguire l'inizializzazione in LCS, è necessario disporre delle autorizzazioni per il ruolo Proprietario progetto o Responsabile ambiente.</span><span class="sxs-lookup"><span data-stu-id="953b3-111">To do the initialization in LCS, you must have permissions for either the Project Owner or Environment manager role.</span></span> <span data-ttu-id="953b3-112">Le topologie dell'ambiente di produzione e sandbox sono supportate.</span><span class="sxs-lookup"><span data-stu-id="953b3-112">The production and sandbox environment topologies are supported.</span></span>

<span data-ttu-id="953b3-113">Per ulteriori informazioni sugli ambienti, vedere [Pianificazione ambiente](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/imp-lifecycle/environment-planning).</span><span class="sxs-lookup"><span data-stu-id="953b3-113">For more information about environments, see [Environment planning](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/imp-lifecycle/environment-planning).</span></span> <span data-ttu-id="953b3-114">Per ulteriori informazioni su RCSU, vedere [Inizializzare Retail Cloud Scale Unit](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/deployment/initialize-retail-channels).</span><span class="sxs-lookup"><span data-stu-id="953b3-114">For more information about RCSU, see [Initialize Retail Cloud Scale Unit](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/deployment/initialize-retail-channels).</span></span>

## <a name="initialize-e-commerce"></a><span data-ttu-id="953b3-115">Inizializzare e-Commerce</span><span class="sxs-lookup"><span data-stu-id="953b3-115">Initialize e-Commerce</span></span>

<span data-ttu-id="953b3-116">Utilizzare questa procedura per inizializzare la funzionalità e-Commerce in un ambiente esistente.</span><span class="sxs-lookup"><span data-stu-id="953b3-116">Use this procedure to initialize the e-Commerce feature in an existing environment.</span></span>

<span data-ttu-id="953b3-117">Prima di iniziare, verificare di disporre delle informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="953b3-117">Before you begin, make sure that you have the following required information:</span></span>

- <span data-ttu-id="953b3-118">L'unità RCSU che verrà utilizzata.</span><span class="sxs-lookup"><span data-stu-id="953b3-118">The RCSU that will be used.</span></span>
- <span data-ttu-id="953b3-119">Il gruppo di sicurezza di Microsoft Azure Active Directory che verrà utilizzato per gli amministratori del sistema di e-Commerce.</span><span class="sxs-lookup"><span data-stu-id="953b3-119">The Microsoft Azure Active Directory security group that will be used for e-Commerce system admins.</span></span>
- <span data-ttu-id="953b3-120">Il gruppo di sicurezza di Microsoft Azure Active Directory che verrà utilizzato per i moderatori di valutazioni e recensioni.</span><span class="sxs-lookup"><span data-stu-id="953b3-120">The Microsoft Azure Active Directory security group that will be used for ratings and reviews moderators.</span></span>
- <span data-ttu-id="953b3-121">I domini che verranno associati all'ambiente.</span><span class="sxs-lookup"><span data-stu-id="953b3-121">The domains that will be associated with the environment.</span></span>

<span data-ttu-id="953b3-122">Inoltre, è possibile raccogliere le seguenti informazioni facoltative:</span><span class="sxs-lookup"><span data-stu-id="953b3-122">In addition, you can collect the following optional information:</span></span>

- <span data-ttu-id="953b3-123">informazioni business-to-consumer (B2C) di Azure AD:</span><span class="sxs-lookup"><span data-stu-id="953b3-123">Azure AD business-to-consumer (B2C) information:</span></span>

    - <span data-ttu-id="953b3-124">Nome tenant</span><span class="sxs-lookup"><span data-stu-id="953b3-124">Tenant Name.</span></span>
    - <span data-ttu-id="953b3-125">ID client</span><span class="sxs-lookup"><span data-stu-id="953b3-125">Client ID.</span></span>
    - <span data-ttu-id="953b3-126">Dominio personalizzato per l'accesso</span><span class="sxs-lookup"><span data-stu-id="953b3-126">Login Custom Domain.</span></span>
    - <span data-ttu-id="953b3-127">URL di risposta</span><span class="sxs-lookup"><span data-stu-id="953b3-127">Reply URL.</span></span>
    - <span data-ttu-id="953b3-128">ID criteri di iscrizione/accesso</span><span class="sxs-lookup"><span data-stu-id="953b3-128">SignUp SignIn Policy ID.</span></span>
    - <span data-ttu-id="953b3-129">ID criteri di reimpostazione password</span><span class="sxs-lookup"><span data-stu-id="953b3-129">Reset password Policy ID.</span></span>
    - <span data-ttu-id="953b3-130">ID criteri di modifica del profilo</span><span class="sxs-lookup"><span data-stu-id="953b3-130">Edit Profile Policy ID.</span></span>

[!NOTE]
<span data-ttu-id="953b3-131">Queste informazioni possono essere aggiunte successivamente, mediante una richiesta di assistenza.</span><span class="sxs-lookup"><span data-stu-id="953b3-131">This information can be added later, through a service request.</span></span>

<span data-ttu-id="953b3-132">Dopo aver raccolto le informazioni necessarie, attenersi alla procedura seguente per inizializzare e-Commerce.</span><span class="sxs-lookup"><span data-stu-id="953b3-132">After you've collected the required information, follow these steps to initialize e-Commerce.</span></span>

1. <span data-ttu-id="953b3-133">Accedere a [LCS](https://lcs.dynamics.com).</span><span class="sxs-lookup"><span data-stu-id="953b3-133">Sign in to [LCS](https://lcs.dynamics.com).</span></span>
1. <span data-ttu-id="953b3-134">Aprire il progetto contenente l'ambiente in cui si desidera inizializzare e-Commerce.</span><span class="sxs-lookup"><span data-stu-id="953b3-134">Open the project that contains the environment where you want to initialize e-Commerce.</span></span>
1. <span data-ttu-id="953b3-135">Nella sezione **Ambienti**, selezionare l'ambiente.</span><span class="sxs-lookup"><span data-stu-id="953b3-135">In the **Environments** section, select the environment.</span></span>
1. <span data-ttu-id="953b3-136">In **Funzionalità ambiente**, selezionare il collegamento **Gestione vendita al dettaglio**.</span><span class="sxs-lookup"><span data-stu-id="953b3-136">Under **Environment features**, select the **Retail manage** link.</span></span>
1. <span data-ttu-id="953b3-137">Nella scheda **e-Commerce**, selezionare **Imposta**.</span><span class="sxs-lookup"><span data-stu-id="953b3-137">On the **e-Commerce** tab, select **Setup**.</span></span> <span data-ttu-id="953b3-138">Viene visualizzata una finestra di dialogo, in cui è necessario immettere le informazioni richieste per il provisioning.</span><span class="sxs-lookup"><span data-stu-id="953b3-138">A dialog box appears, where you must enter the information that is required for provisioning.</span></span>
1. <span data-ttu-id="953b3-139">Immettere le informazioni necessarie e passare alla pagina successiva.</span><span class="sxs-lookup"><span data-stu-id="953b3-139">Fill in the required information, and then go to the next page.</span></span>
1. <span data-ttu-id="953b3-140">Nella pagina successiva, immettere le informazioni necessarie e inviare il modulo.</span><span class="sxs-lookup"><span data-stu-id="953b3-140">On the next page, fill in the required information, and then submit the form.</span></span> <span data-ttu-id="953b3-141">Viene visualizzata di nuovo la scheda **e-Commerce**, che dovrebbe indicare l'avvio dell'inizializzazione.</span><span class="sxs-lookup"><span data-stu-id="953b3-141">You're returned to the **e-Commerce** tab, where you should see that initialization has been started.</span></span>
1. <span data-ttu-id="953b3-142">Per visualizzare lo stato dell'inizializzazione, selezionare **Aggiorna** o ritornare in seguito alla scheda **e-Commerce**.</span><span class="sxs-lookup"><span data-stu-id="953b3-142">To view the initialization status, either **Refresh** or return to the **e-Commerce** tab later.</span></span>
    
<span data-ttu-id="953b3-143">Quando e-Commerce viene inizializzato da LCs, il sistema esegue il provisioning di vari componenti necessari per e-Commerce e li associa all'ambiente.</span><span class="sxs-lookup"><span data-stu-id="953b3-143">When e-Commerce is initialized from LCS, the system provisions several components that are required for e-Commerce and associates them with the environment.</span></span> <span data-ttu-id="953b3-144">Al termine del provisioning, la scheda **e-Commerce** nella pagina **Gestione vendita al dettaglio** viene aggiornata in base al provisioning.</span><span class="sxs-lookup"><span data-stu-id="953b3-144">After provisioning is complete, the **e-Commerce** tab on the **Retail management** page is updated to reflect the provisioning.</span></span> <span data-ttu-id="953b3-145">Nella pagina sono indicate le distribuzioni di personalizzazioni più recenti e lo stato di qualsiasi altra distribuzione in corso.</span><span class="sxs-lookup"><span data-stu-id="953b3-145">The page shows the latest customization deployments and the status of any other ongoing deployments.</span></span> <span data-ttu-id="953b3-146">Include inoltre collegamenti al sito di e-Commerce e a Creazione di siti di e-Commerce dove i siti vengono creati.</span><span class="sxs-lookup"><span data-stu-id="953b3-146">It also includes links to the e-Commerce site and the e-Commerce site builder where sites are authored.</span></span>

## <a name="access-site-builder"></a><span data-ttu-id="953b3-147">Accedere a Creazione di siti Web</span><span class="sxs-lookup"><span data-stu-id="953b3-147">Access site builder</span></span>

<span data-ttu-id="953b3-148">Per accedere a Creazione di siti Web, selezionare la scheda **e-Commerce** nella pagina **Gestione vendita al dettaglio** in LCS e selezionare il collegamento **Strumento di gestione del sito e-Commerce**.</span><span class="sxs-lookup"><span data-stu-id="953b3-148">To access site builder, go to the **e-Commerce** tab on the **Retail management** page in LCS and select the **e-Commerce site management tool** link.</span></span> <span data-ttu-id="953b3-149">La pagina di destinazione di Creazione di siti Web visualizza una vista a livello di tenant.</span><span class="sxs-lookup"><span data-stu-id="953b3-149">The site builder landing page displays a tenant-level view.</span></span> <span data-ttu-id="953b3-150">In questa pagina è possibile:</span><span class="sxs-lookup"><span data-stu-id="953b3-150">From this page, you can:</span></span>

- <span data-ttu-id="953b3-151">Modificare le impostazioni a livello di tenant.</span><span class="sxs-lookup"><span data-stu-id="953b3-151">Modify tenant-level settings.</span></span>
- <span data-ttu-id="953b3-152">Accedere a qualsiasi sito creato e disporre dell'autorizzazione per visualizzare.</span><span class="sxs-lookup"><span data-stu-id="953b3-152">Navigate to any site you have created, and have permission to view.</span></span> 
- <span data-ttu-id="953b3-153">Accedere alle funzionalità di verifica come Moderazione e Report.</span><span class="sxs-lookup"><span data-stu-id="953b3-153">Access Reviews features such as moderation and reporting.</span></span>
- <span data-ttu-id="953b3-154">Creare un nuovo sito.</span><span class="sxs-lookup"><span data-stu-id="953b3-154">Create a new site.</span></span> <span data-ttu-id="953b3-155">Per ulteriori informazioni su come creare un nuovo sito, vedere [Creare un sito di e-commerce](create-ecommerce-site.md).</span><span class="sxs-lookup"><span data-stu-id="953b3-155">For more information about how to create a new site, see [Create an e-Commerce site](create-ecommerce-site.md) .</span></span> 

## <a name="additional-resources"></a><span data-ttu-id="953b3-156">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="953b3-156">Additional resources</span></span>

[<span data-ttu-id="953b3-157">Configurare il proprio nome di dominio</span><span class="sxs-lookup"><span data-stu-id="953b3-157">Configure your domain name</span></span>](configure-your-domain-name.md)

[<span data-ttu-id="953b3-158">Creare un sito di e-commerce</span><span class="sxs-lookup"><span data-stu-id="953b3-158">Create an e-Commerce site</span></span>](create-ecommerce-site.md)

[<span data-ttu-id="953b3-159">Associare un sito online a un canale</span><span class="sxs-lookup"><span data-stu-id="953b3-159">Associate an online site with a channel</span></span>](associate-site-online-store.md)

[<span data-ttu-id="953b3-160">Gestire i file robots.txt</span><span class="sxs-lookup"><span data-stu-id="953b3-160">Manage robots.txt files</span></span>](manage-robots-txt-files.md)

[<span data-ttu-id="953b3-161">Impostare pagine personalizzate per l'accesso degli utenti</span><span class="sxs-lookup"><span data-stu-id="953b3-161">Set up custom pages for user logins</span></span>](custom-pages-user-logins.md)

[<span data-ttu-id="953b3-162">Aggiungere il supporto per una rete per la distribuzione di contenuti (CDN)</span><span class="sxs-lookup"><span data-stu-id="953b3-162">Add support for a content delivery network (CDN)</span></span>](add-cdn-support.md)

[<span data-ttu-id="953b3-163">Abilitare il rilevamento del punto vendita basato sull'ubicazione</span><span class="sxs-lookup"><span data-stu-id="953b3-163">Enable location-based store detection</span></span>](enable-store-detection.md)
