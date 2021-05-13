---
title: Distribuire un nuovo tenant di e-commerce
description: In questo argomento viene descritto come distribuire un nuovo sito di e-commerce Dynamics 365 Commerce utilizzando Microsoft Dynamics Lifecycle Services.
author: psimolin
ms.date: 07/02/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 6b228babfd32a4191eeed2a6d924a8b99f1a5311
ms.sourcegitcommit: 9eadc7ca08e2db3fd208f5fc835551abe9d06dc8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/22/2021
ms.locfileid: "5936708"
---
# <a name="deploy-a-new-e-commerce-tenant"></a><span data-ttu-id="9afae-103">Distribuire un nuovo tenant di e-commerce</span><span class="sxs-lookup"><span data-stu-id="9afae-103">Deploy a new e-commerce tenant</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="9afae-104">In questo argomento viene descritto come distribuire un nuovo sito di e-commerce Dynamics 365 Commerce utilizzando Microsoft Dynamics Lifecycle Services.</span><span class="sxs-lookup"><span data-stu-id="9afae-104">This topic describes how to deploy a new Dynamics 365 Commerce e-commerce site by using Microsoft Dynamics Lifecycle Services (LCS).</span></span>

<span data-ttu-id="9afae-105">Microsoft Dynamics Lifecycle Services (LCS) è un'area di lavoro collaborativa basata su cloud che i partner e i clienti possono utilizzare per gestire progetti e ambienti, visualizzare le informazioni più recenti su prodotti e funzionalità di Microsoft Dynamics nonché per creare, tenere traccia ed esaminare richieste di supporto.</span><span class="sxs-lookup"><span data-stu-id="9afae-105">Microsoft Dynamics Lifecycle Services (LCS) is a cloud-based collaborative workspace that partners and customers can use to manage their projects and environments, view the latest information about Microsoft Dynamics products and features, and create, track, and browse support incidents.</span></span> <span data-ttu-id="9afae-106">Le funzionalità di gestione di e-commerce sono integrate in LCS.</span><span class="sxs-lookup"><span data-stu-id="9afae-106">E-commerce management features are integrated into LCS.</span></span>

<span data-ttu-id="9afae-107">Per ulteriori informazioni su LCS, vedere [Manuale dell'utente di Lifecycle Services](/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide).</span><span class="sxs-lookup"><span data-stu-id="9afae-107">To learn more about LCS, see the [Lifecycle Services User Guide](/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide).</span></span>
    
## <a name="get-started"></a><span data-ttu-id="9afae-108">Attività iniziali</span><span class="sxs-lookup"><span data-stu-id="9afae-108">Get started</span></span>

<span data-ttu-id="9afae-109">Prima di inizializzare e-commerce, è necessario inizializzare un progetto, un ambiente e Retail Cloud Scale Unit (RCSU).</span><span class="sxs-lookup"><span data-stu-id="9afae-109">Before you can initialize e-commerce, you must initialize a project, an environment, and a Retail Cloud Scale Unit (RCSU).</span></span> <span data-ttu-id="9afae-110">Per eseguire l'inizializzazione in LCS, è necessario disporre delle autorizzazioni per il ruolo Proprietario progetto o Responsabile ambiente.</span><span class="sxs-lookup"><span data-stu-id="9afae-110">To do the initialization in LCS, you must have permissions for either the Project Owner or Environment manager role.</span></span> <span data-ttu-id="9afae-111">Le topologie dell'ambiente di produzione e sandbox sono supportate.</span><span class="sxs-lookup"><span data-stu-id="9afae-111">The production and sandbox environment topologies are supported.</span></span>

<span data-ttu-id="9afae-112">Per ulteriori informazioni sugli ambienti, vedere [Pianificazione ambiente](/dynamics365/unified-operations/fin-and-ops/imp-lifecycle/environment-planning).</span><span class="sxs-lookup"><span data-stu-id="9afae-112">For more information about environments, see [Environment planning](/dynamics365/unified-operations/fin-and-ops/imp-lifecycle/environment-planning).</span></span> <span data-ttu-id="9afae-113">Per ulteriori informazioni su RCSU, vedere [Inizializzare Retail Cloud Scale Unit](/dynamics365/unified-operations/dev-itpro/deployment/initialize-retail-channels).</span><span class="sxs-lookup"><span data-stu-id="9afae-113">For more information about RCSU, see [Initialize Retail Cloud Scale Unit](/dynamics365/unified-operations/dev-itpro/deployment/initialize-retail-channels).</span></span>

## <a name="initialize-e-commerce"></a><span data-ttu-id="9afae-114">Inizializzare e-commerce</span><span class="sxs-lookup"><span data-stu-id="9afae-114">Initialize e-commerce</span></span>

<span data-ttu-id="9afae-115">Utilizzare questa procedura per inizializzare la funzionalità e-commerce in un ambiente esistente.</span><span class="sxs-lookup"><span data-stu-id="9afae-115">Use this procedure to initialize the e-commerce feature in an existing environment.</span></span>

<span data-ttu-id="9afae-116">Prima di iniziare, verificare di disporre delle informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="9afae-116">Before you begin, make sure that you have the following required information:</span></span>

- <span data-ttu-id="9afae-117">L'unità RCSU che verrà utilizzata.</span><span class="sxs-lookup"><span data-stu-id="9afae-117">The RCSU that will be used.</span></span>
- <span data-ttu-id="9afae-118">Il gruppo di sicurezza di Microsoft Azure Active Directory che verrà utilizzato per gli amministratori del sistema di e-commerce.</span><span class="sxs-lookup"><span data-stu-id="9afae-118">The Microsoft Azure Active Directory security group that will be used for e-commerce system admins.</span></span>
- <span data-ttu-id="9afae-119">Il gruppo di sicurezza di Microsoft Azure Active Directory che verrà utilizzato per i moderatori di valutazioni e recensioni.</span><span class="sxs-lookup"><span data-stu-id="9afae-119">The Microsoft Azure Active Directory security group that will be used for ratings and reviews moderators.</span></span>
- <span data-ttu-id="9afae-120">I domini che verranno associati all'ambiente.</span><span class="sxs-lookup"><span data-stu-id="9afae-120">The domains that will be associated with the environment.</span></span>

<span data-ttu-id="9afae-121">Inoltre, è possibile raccogliere le seguenti informazioni facoltative:</span><span class="sxs-lookup"><span data-stu-id="9afae-121">In addition, you can collect the following optional information:</span></span>

- <span data-ttu-id="9afae-122">informazioni business-to-consumer (B2C) di Azure AD:</span><span class="sxs-lookup"><span data-stu-id="9afae-122">Azure AD business-to-consumer (B2C) information:</span></span>

    - <span data-ttu-id="9afae-123">Nome tenant</span><span class="sxs-lookup"><span data-stu-id="9afae-123">Tenant Name.</span></span>
    - <span data-ttu-id="9afae-124">ID client</span><span class="sxs-lookup"><span data-stu-id="9afae-124">Client ID.</span></span>
    - <span data-ttu-id="9afae-125">Dominio personalizzato per l'accesso</span><span class="sxs-lookup"><span data-stu-id="9afae-125">Login Custom Domain.</span></span>
    - <span data-ttu-id="9afae-126">URL di risposta</span><span class="sxs-lookup"><span data-stu-id="9afae-126">Reply URL.</span></span>
    - <span data-ttu-id="9afae-127">ID criteri di iscrizione/accesso</span><span class="sxs-lookup"><span data-stu-id="9afae-127">SignUp SignIn Policy ID.</span></span>
    - <span data-ttu-id="9afae-128">ID criteri di reimpostazione password</span><span class="sxs-lookup"><span data-stu-id="9afae-128">Reset password Policy ID.</span></span>
    - <span data-ttu-id="9afae-129">ID criteri di modifica del profilo</span><span class="sxs-lookup"><span data-stu-id="9afae-129">Edit Profile Policy ID.</span></span>

> [!NOTE]
> <span data-ttu-id="9afae-130">Queste informazioni possono essere aggiunte successivamente, mediante una richiesta di assistenza.</span><span class="sxs-lookup"><span data-stu-id="9afae-130">This information can be added later, through a service request.</span></span>

<span data-ttu-id="9afae-131">Dopo aver raccolto le informazioni necessarie, attenersi alla procedura seguente per inizializzare e-commerce.</span><span class="sxs-lookup"><span data-stu-id="9afae-131">After you've collected the required information, follow these steps to initialize e-commerce.</span></span>

1. <span data-ttu-id="9afae-132">Accedere a [LCS](https://lcs.dynamics.com).</span><span class="sxs-lookup"><span data-stu-id="9afae-132">Sign in to [LCS](https://lcs.dynamics.com).</span></span>
1. <span data-ttu-id="9afae-133">Aprire il progetto contenente l'ambiente in cui si desidera inizializzare e-commerce.</span><span class="sxs-lookup"><span data-stu-id="9afae-133">Open the project that contains the environment where you want to initialize e-commerce.</span></span>
1. <span data-ttu-id="9afae-134">Nella sezione **Ambienti**, selezionare l'ambiente.</span><span class="sxs-lookup"><span data-stu-id="9afae-134">In the **Environments** section, select the environment.</span></span>
1. <span data-ttu-id="9afae-135">In **Funzionalità ambiente**, selezionare il collegamento **Gestione vendita al dettaglio**.</span><span class="sxs-lookup"><span data-stu-id="9afae-135">Under **Environment features**, select the **Retail manage** link.</span></span>
1. <span data-ttu-id="9afae-136">Nella scheda **e-Commerce**, selezionare **Imposta**.</span><span class="sxs-lookup"><span data-stu-id="9afae-136">On the **e-Commerce** tab, select **Setup**.</span></span> <span data-ttu-id="9afae-137">Viene visualizzata una finestra di dialogo, in cui è necessario immettere le informazioni richieste per il provisioning.</span><span class="sxs-lookup"><span data-stu-id="9afae-137">A dialog box appears, where you must enter the information that is required for provisioning.</span></span>
1. <span data-ttu-id="9afae-138">Immettere le informazioni necessarie e passare alla pagina successiva.</span><span class="sxs-lookup"><span data-stu-id="9afae-138">Fill in the required information, and then go to the next page.</span></span>
1. <span data-ttu-id="9afae-139">Nella pagina successiva, immettere le informazioni necessarie e inviare il modulo.</span><span class="sxs-lookup"><span data-stu-id="9afae-139">On the next page, fill in the required information, and then submit the form.</span></span> <span data-ttu-id="9afae-140">Viene visualizzata di nuovo la scheda **e-Commerce**, che dovrebbe indicare l'avvio dell'inizializzazione.</span><span class="sxs-lookup"><span data-stu-id="9afae-140">You're returned to the **e-Commerce** tab, where you should see that initialization has been started.</span></span>
1. <span data-ttu-id="9afae-141">Per visualizzare lo stato dell'inizializzazione, selezionare **Aggiorna** o ritornare in seguito alla scheda **e-Commerce**.</span><span class="sxs-lookup"><span data-stu-id="9afae-141">To view the initialization status, either **Refresh** or return to the **e-Commerce** tab later.</span></span>
    
<span data-ttu-id="9afae-142">Quando e-commerce viene inizializzato da LCs, il sistema esegue il provisioning di vari componenti necessari per e-commerce e li associa all'ambiente.</span><span class="sxs-lookup"><span data-stu-id="9afae-142">When e-commerce is initialized from LCS, the system provisions several components that are required for e-commerce and associates them with the environment.</span></span> <span data-ttu-id="9afae-143">Al termine del provisioning, la scheda **e-Commerce** nella pagina **Gestione vendita al dettaglio** viene aggiornata in base al provisioning.</span><span class="sxs-lookup"><span data-stu-id="9afae-143">After provisioning is complete, the **e-Commerce** tab on the **Retail management** page is updated to reflect the provisioning.</span></span> <span data-ttu-id="9afae-144">Nella pagina sono indicate le distribuzioni di personalizzazioni più recenti e lo stato di qualsiasi altra distribuzione in corso.</span><span class="sxs-lookup"><span data-stu-id="9afae-144">The page shows the latest customization deployments and the status of any other ongoing deployments.</span></span> <span data-ttu-id="9afae-145">Include inoltre collegamenti al sito di e-commerce e a Creazione di siti di Commerce dove i siti vengono creati.</span><span class="sxs-lookup"><span data-stu-id="9afae-145">It also includes links to the e-commerce site and the Commerce site builder where sites are authored.</span></span>

## <a name="access-commerce-site-builder"></a><span data-ttu-id="9afae-146">Accedere a Creazione di siti di Commerce</span><span class="sxs-lookup"><span data-stu-id="9afae-146">Access Commerce site builder</span></span>

<span data-ttu-id="9afae-147">Per accedere a Creazione di siti di Commerce, selezionare la scheda **e-Commerce** nella pagina **Gestione vendita al dettaglio** in LCS e selezionare il collegamento **Strumento di gestione del sito e-Commerce**.</span><span class="sxs-lookup"><span data-stu-id="9afae-147">To access Commerce site builder, go to the **e-Commerce** tab on the **Retail management** page in LCS and select the **e-Commerce site management tool** link.</span></span> <span data-ttu-id="9afae-148">La pagina di destinazione di Creazione di siti Web visualizza una vista a livello di tenant.</span><span class="sxs-lookup"><span data-stu-id="9afae-148">The site builder landing page displays a tenant-level view.</span></span> <span data-ttu-id="9afae-149">In questa pagina è possibile:</span><span class="sxs-lookup"><span data-stu-id="9afae-149">From this page, you can:</span></span>

- <span data-ttu-id="9afae-150">Modificare le impostazioni a livello di tenant.</span><span class="sxs-lookup"><span data-stu-id="9afae-150">Modify tenant-level settings.</span></span>
- <span data-ttu-id="9afae-151">Accedere a qualsiasi sito creato e disporre dell'autorizzazione per visualizzare.</span><span class="sxs-lookup"><span data-stu-id="9afae-151">Navigate to any site you have created, and have permission to view.</span></span> 
- <span data-ttu-id="9afae-152">Accedere alle funzionalità di verifica come Moderazione e Report.</span><span class="sxs-lookup"><span data-stu-id="9afae-152">Access Reviews features such as moderation and reporting.</span></span>
- <span data-ttu-id="9afae-153">Creare un nuovo sito.</span><span class="sxs-lookup"><span data-stu-id="9afae-153">Create a new site.</span></span> <span data-ttu-id="9afae-154">Per ulteriori informazioni su come creare un nuovo sito, vedere [Creare un sito di e-commerce](create-ecommerce-site.md).</span><span class="sxs-lookup"><span data-stu-id="9afae-154">For more information about how to create a new site, see [Create an e-commerce site](create-ecommerce-site.md) .</span></span> 

## <a name="additional-resources"></a><span data-ttu-id="9afae-155">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="9afae-155">Additional resources</span></span>

[<span data-ttu-id="9afae-156">Configurare il proprio nome di dominio</span><span class="sxs-lookup"><span data-stu-id="9afae-156">Configure your domain name</span></span>](configure-your-domain-name.md)

[<span data-ttu-id="9afae-157">Creare un sito di e-commerce</span><span class="sxs-lookup"><span data-stu-id="9afae-157">Create an e-commerce site</span></span>](create-ecommerce-site.md)

[<span data-ttu-id="9afae-158">Associare un sito Dynamics 365 Commerce a un canale online</span><span class="sxs-lookup"><span data-stu-id="9afae-158">Associate a Dynamics 365 Commerce site with an online channel</span></span>](associate-site-online-store.md)

[<span data-ttu-id="9afae-159">Gestire i file robots.txt</span><span class="sxs-lookup"><span data-stu-id="9afae-159">Manage robots.txt files</span></span>](manage-robots-txt-files.md)

[<span data-ttu-id="9afae-160">Caricare reindirizzamenti URL in blocco</span><span class="sxs-lookup"><span data-stu-id="9afae-160">Upload URL redirects in bulk</span></span>](upload-bulk-redirects.md)

[<span data-ttu-id="9afae-161">Impostare un tenant B2C in Commerce</span><span class="sxs-lookup"><span data-stu-id="9afae-161">Set up a B2C tenant in Commerce</span></span>](set-up-B2C-tenant.md)

[<span data-ttu-id="9afae-162">Impostare pagine personalizzate per l'accesso degli utenti</span><span class="sxs-lookup"><span data-stu-id="9afae-162">Set up custom pages for user logins</span></span>](custom-pages-user-logins.md)

[<span data-ttu-id="9afae-163">Configurare più tenant B2C in un ambiente Commerce</span><span class="sxs-lookup"><span data-stu-id="9afae-163">Configure multiple B2C tenants in a Commerce environment</span></span>](configure-multi-B2C-tenants.md)

[<span data-ttu-id="9afae-164">Aggiungere il supporto per una rete per la distribuzione di contenuti (CDN)</span><span class="sxs-lookup"><span data-stu-id="9afae-164">Add support for a content delivery network (CDN)</span></span>](add-cdn-support.md)

[<span data-ttu-id="9afae-165">Abilitare il rilevamento del punto vendita basato sull'ubicazione</span><span class="sxs-lookup"><span data-stu-id="9afae-165">Enable location-based store detection</span></span>](enable-store-detection.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]