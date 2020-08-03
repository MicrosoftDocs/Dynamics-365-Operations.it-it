---
title: Provisioning di un ambiente di valutazione Dynamics 365 Commerce
description: Questo argomento illustra come eseguire il provisioning di un ambiente di valutazione Microsoft Dynamics 365 Commerce.
author: psimolin
manager: annbe
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: e5ce2002c66a1c36d5647d3c76684b394fc1ff79
ms.sourcegitcommit: 5175e3fae432016246244cf70fe05465f43de88c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/17/2020
ms.locfileid: "3599852"
---
# <a name="provision-a-dynamics-365-commerce-evaluation-environment"></a><span data-ttu-id="95b92-103">Provisioning di un ambiente di valutazione Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="95b92-103">Provision a Dynamics 365 Commerce evaluation environment</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="95b92-104">Questo argomento illustra come eseguire il provisioning di un ambiente di valutazione Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="95b92-104">This topic explains how to provision a Microsoft Dynamics 365 Commerce evaluation environment.</span></span>

<span data-ttu-id="95b92-105">Prima di iniziare, è consigliabile dare una rapida occhiata a questo argomento per avere un'idea di ciò che richiede il processo.</span><span class="sxs-lookup"><span data-stu-id="95b92-105">Before you begin, we recommend that you take a quick scan through this topic to get an idea of what the process requires.</span></span>

> [!NOTE]
> <span data-ttu-id="95b92-106">Gli ambienti di valutazione di Commerce non sono generalmente disponibili e sono concessi a partner e clienti in base alla richiesta.</span><span class="sxs-lookup"><span data-stu-id="95b92-106">Commerce evaluation environments aren't generally available, and are granted to partners and customers on a per-request basis.</span></span> <span data-ttu-id="95b92-107">Per ulteriori informazioni, contattare il partner Microsoft.</span><span class="sxs-lookup"><span data-stu-id="95b92-107">For more information, reach out to your Microsoft partner contact.</span></span>

## <a name="overview"></a><span data-ttu-id="95b92-108">Panoramica</span><span class="sxs-lookup"><span data-stu-id="95b92-108">Overview</span></span>

<span data-ttu-id="95b92-109">Per eseguire correttamente il provisioning di un ambiente di valutazione Commerce, è necessario creare un progetto con un nome e un tipo di prodotto specifici.</span><span class="sxs-lookup"><span data-stu-id="95b92-109">To successfully provision a Commerce evaluation environment, you must create a project that has a specific product name and type.</span></span> <span data-ttu-id="95b92-110">Anche l'ambiente e Commerce Scale Unit hanno alcuni parametri specifici che devono essere utilizzati quando si prevede di eseguire il provisioning di e-Commerce in seguito.</span><span class="sxs-lookup"><span data-stu-id="95b92-110">The environment and Commerce Scale Unit (CSU) also have some specific parameters that you must use when you expect to provision e-Commerce later.</span></span> <span data-ttu-id="95b92-111">Le istruzioni in questo argomento descrivono tutti i passaggi necessari per completare il provisioning e i parametri da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="95b92-111">The instructions in this topic describe all the steps that are required to complete provisioning and the parameters that you must use.</span></span>

<span data-ttu-id="95b92-112">Dopo aver completato il provisioning dell'ambiente di valutazione di Commerce, è necessario completare alcuni passaggi post-provisioning per prepararlo all'uso.</span><span class="sxs-lookup"><span data-stu-id="95b92-112">After you successfully provision your Commerce evaluation environment, you must complete a few post-provisioning steps to prepare it for use.</span></span> <span data-ttu-id="95b92-113">Alcuni passaggi sono facoltativi, a seconda degli aspetti del sistema che si desidera valutare.</span><span class="sxs-lookup"><span data-stu-id="95b92-113">Some steps are optional, depending on the aspects of the system that you want to evaluate.</span></span> <span data-ttu-id="95b92-114">È sempre possibile completare i passaggi facoltativi in seguito.</span><span class="sxs-lookup"><span data-stu-id="95b92-114">You can always complete the optional steps later.</span></span>

<span data-ttu-id="95b92-115">Per informazioni relative a come configurare l'ambiente di valutazione di Commerce dopo il provisioning, consultare [Configurare un ambiente di valutazione di Commerce](cpe-post-provisioning.md).</span><span class="sxs-lookup"><span data-stu-id="95b92-115">For information about how to configure your Commerce evaluation environment after you provision it, see [Configure a Commerce evaluation environment](cpe-post-provisioning.md).</span></span> <span data-ttu-id="95b92-116">Per informazioni su come configurare funzionalità facoltative per l'ambiente di valutazione Commerce, vedere [Configurare le funzionalità facoltative per un ambiente di valutazione Commerce](cpe-optional-features.md).</span><span class="sxs-lookup"><span data-stu-id="95b92-116">For information about how to configure optional features for your Commerce evaluation environment, see [Configure optional features for a Commerce evaluation environment](cpe-optional-features.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="95b92-117">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="95b92-117">Prerequisites</span></span>

<span data-ttu-id="95b92-118">I seguenti prerequisiti devono essere presenti prima di poter eseguire il provisioning dell'ambiente di valutazione Commerce:</span><span class="sxs-lookup"><span data-stu-id="95b92-118">The following prerequisites must be in place before you can provision your Commerce evaluation environment:</span></span>

- <span data-ttu-id="95b92-119">Si dispone dell'accesso al portale di Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="95b92-119">You have access to the Microsoft Dynamics Lifecycle Services (LCS) portal.</span></span>
- <span data-ttu-id="95b92-120">Si è un partner o cliente di Microsoft Dynamics 365 e si è in grado di creare un progetto Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="95b92-120">You are an existing Microsoft Dynamics 365 partner or customer and are able to create a Dynamics 365 Commerce project.</span></span>
- <span data-ttu-id="95b92-121">Si dispone dell'accesso di amministratore alla sottoscrizione Microsoft Azure o si è in contatto con un amministratore della sottoscrizione che può fornire assistenza se necessario.</span><span class="sxs-lookup"><span data-stu-id="95b92-121">You have administrator access to your Microsoft Azure subscription, or you're in contact with a subscription administrator who can assist you if required.</span></span>
- <span data-ttu-id="95b92-122">Si ha a disposizione l'ID tenant di Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="95b92-122">You have your Azure Active Directory (Azure AD) tenant ID available.</span></span>
- <span data-ttu-id="95b92-123">È stato creato un gruppo di sicurezza Azure AD da utilizzare come gruppo Amministratori del sistema di e-Commerce e si dispone del relativo ID.</span><span class="sxs-lookup"><span data-stu-id="95b92-123">You've created an Azure AD security group that can be used as an e-Commerce system admin group, and you have its ID available.</span></span>
- <span data-ttu-id="95b92-124">È stato creato un gruppo di sicurezza Azure AD da utilizzare come gruppo di moderatori di Valutazioni e revisioni e devi disporre del relativo ID.</span><span class="sxs-lookup"><span data-stu-id="95b92-124">You've created an Azure AD security group that can be used as a Ratings and Reviews moderator group, and you have its ID available.</span></span> <span data-ttu-id="95b92-125">(Questo gruppo di sicurezza può essere lo stesso del gruppo di amministratori del sistema e-Commerce).</span><span class="sxs-lookup"><span data-stu-id="95b92-125">(This security group can be the same as the e-Commerce system admin group.)</span></span>

<span data-ttu-id="95b92-126">Si noti che questo elenco non è esaustivo.</span><span class="sxs-lookup"><span data-stu-id="95b92-126">Note that this list isn't exhaustive.</span></span> <span data-ttu-id="95b92-127">In caso di problemi, contattare il partner Microsoft.</span><span class="sxs-lookup"><span data-stu-id="95b92-127">If you experience any issues, reach out to your Microsoft partner contact for assistance.</span></span>

## <a name="provision-your-commerce-evaluation-environment"></a><span data-ttu-id="95b92-128">Eseguire il provisioning di un ambiente di valutazione Commerce</span><span class="sxs-lookup"><span data-stu-id="95b92-128">Provision your Commerce evaluation environment</span></span>

<span data-ttu-id="95b92-129">Queste procedure spiegano come eseguire il provisioning di un ambiente di valutazione Commerce.</span><span class="sxs-lookup"><span data-stu-id="95b92-129">These procedures explain how to provision a Commerce evaluation environment.</span></span> <span data-ttu-id="95b92-130">Dopo averle completate, l'ambiente di valutazione Commerce sarà pronto per la configurazione.</span><span class="sxs-lookup"><span data-stu-id="95b92-130">After you successfully complete them, the Commerce evaluation environment will be ready for configuration.</span></span> <span data-ttu-id="95b92-131">Tutte le attività descritte qui possono verificarsi nel portale di LCS.</span><span class="sxs-lookup"><span data-stu-id="95b92-131">All the activities that are described here occur in the LCS portal.</span></span>

### <a name="create-a-new-project"></a><span data-ttu-id="95b92-132">Crea un nuovo progetto</span><span class="sxs-lookup"><span data-stu-id="95b92-132">Create a new project</span></span>

<span data-ttu-id="95b92-133">Per creare un nuovo progetto in LCS, completare i passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="95b92-133">To create a new project in LCS, follow these steps.</span></span>

1. <span data-ttu-id="95b92-134">Nella home page di LCS, selezionare il segno più (**+**) per creare un progetto.</span><span class="sxs-lookup"><span data-stu-id="95b92-134">On the LCS home page, select the plus sign (**+**) to create a project.</span></span>
1. <span data-ttu-id="95b92-135">Nel riquadro destro, seguire uno di questi passaggi:</span><span class="sxs-lookup"><span data-stu-id="95b92-135">In the right pane, follow one of these steps:</span></span>

    - <span data-ttu-id="95b92-136">Se si è un partner, scegliere **Migrare, creare soluzioni e ottenere informazioni**.</span><span class="sxs-lookup"><span data-stu-id="95b92-136">If you're a partner, select **Migrate, create solutions, and learn**.</span></span>
    - <span data-ttu-id="95b92-137">Se si è un cliente, scegliere **Pre-vendite potenziali**.</span><span class="sxs-lookup"><span data-stu-id="95b92-137">If you're a customer, select **Prospective presales**.</span></span>

1. <span data-ttu-id="95b92-138">Immettere un nome, una descrizione e il settore.</span><span class="sxs-lookup"><span data-stu-id="95b92-138">Enter a name, description, and industry.</span></span>
1. <span data-ttu-id="95b92-139">Nel campo **Nome prodotto**, selezionare **Dynamics 365 Commerce**.</span><span class="sxs-lookup"><span data-stu-id="95b92-139">In the **Product name** field, select **Dynamics 365 Commerce**.</span></span>
1. <span data-ttu-id="95b92-140">Nel campo **Versione prodotto**, selezionare **Dynamics 365 Commerce**.</span><span class="sxs-lookup"><span data-stu-id="95b92-140">In the **Product version** field, select **Dynamics 365 Commerce**.</span></span>
1. <span data-ttu-id="95b92-141">Nel campo **Metodologia**, selezionare **Metodologia di implementazione di Dynamics Retail**.</span><span class="sxs-lookup"><span data-stu-id="95b92-141">In the **Methodology** field, select **Dynamics Retail implementation methodology**.</span></span>
1. <span data-ttu-id="95b92-142">Facoltativo, è possibile importare ruoli e utenti da un progetto esistente.</span><span class="sxs-lookup"><span data-stu-id="95b92-142">Optional: You can import roles and users from an existing project.</span></span>
1. <span data-ttu-id="95b92-143">Selezionare **Crea**.</span><span class="sxs-lookup"><span data-stu-id="95b92-143">Select **Create**.</span></span> <span data-ttu-id="95b92-144">Appare la visualizzazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="95b92-144">The project view appears.</span></span>

### <a name="add-the-azure-connector"></a><span data-ttu-id="95b92-145">Aggiungere il connettore di Azure</span><span class="sxs-lookup"><span data-stu-id="95b92-145">Add the Azure Connector</span></span>

<span data-ttu-id="95b92-146">Per aggiungere il connettore di Azure al progetto LCS, seguire i passaggi in [Completare il processo di onboarding di Azure Resource Manager (ARM)](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/deployment/arm-onboarding).</span><span class="sxs-lookup"><span data-stu-id="95b92-146">To add the Azure Connector to your LCS project, follow the steps in [Complete the Azure Resource Manager (ARM) onboarding process](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/deployment/arm-onboarding).</span></span>

### <a name="deploy-the-environment"></a><span data-ttu-id="95b92-147">Distribuire l'ambiente</span><span class="sxs-lookup"><span data-stu-id="95b92-147">Deploy the environment</span></span>

<span data-ttu-id="95b92-148">Per distribuire l'ambiente, attenersi a questa procedura.</span><span class="sxs-lookup"><span data-stu-id="95b92-148">To deploy the environment, follow these steps.</span></span>

> [!NOTE]
> <span data-ttu-id="95b92-149">Potrebbe non essere necessario completare i passaggi 6, 7 e/o 8, poiché le pagine con una singola opzione vengono ignorate.</span><span class="sxs-lookup"><span data-stu-id="95b92-149">You might not have to complete steps 6, 7, and/or 8, because pages that have a single option are skipped.</span></span> <span data-ttu-id="95b92-150">Nella visualizzazione **Parametri dell'ambiente**, confermare che il testo **Dynamics 365 Commerce - Demo (10.0.* x* con update *xx* della piattaforma)\*\* appaia direttamente sopra il campo **Nome ambiente**.</span><span class="sxs-lookup"><span data-stu-id="95b92-150">When you're in the **Environment parameters** view, confirm that the text **Dynamics 365 Commerce - Demo (10.0.* x* with Platform update *xx*)\*\* appears directly above the **Environment name** field.</span></span> <span data-ttu-id="95b92-151">Per dettagli, vedere l'illustrazione che appare dopo il passaggio 8.</span><span class="sxs-lookup"><span data-stu-id="95b92-151">For details, see the illustration that appears after step 8.</span></span>

1. <span data-ttu-id="95b92-152">Nel menu superiore, selezionare **Distribuzione ambienti ospitati nel cloud**.</span><span class="sxs-lookup"><span data-stu-id="95b92-152">On the top menu, select **Cloud-hosted environments**.</span></span>
1. <span data-ttu-id="95b92-153">Selezionare **Aggiungi** per aggiungere un ambiente.</span><span class="sxs-lookup"><span data-stu-id="95b92-153">Select **Add** to add an environment.</span></span>
1. <span data-ttu-id="95b92-154">Nel campo **Versione applicazione**, selezionare la versione più recente.</span><span class="sxs-lookup"><span data-stu-id="95b92-154">In the **Application version** field, select the most current version.</span></span> <span data-ttu-id="95b92-155">Se si ha la necessità di selezionare una versione dell'applicazione diversa dalla versione più recente, non selezionare una versione precedente alla versione **10.0.8**.</span><span class="sxs-lookup"><span data-stu-id="95b92-155">If you have a specific need to select an application version other than the most current version, do not select a version prior to **10.0.8**.</span></span>
1. <span data-ttu-id="95b92-156">Nel campo **Versione piattaforma**, utilizzare la versione della piattaforma che viene scelta automaticamente per la versione dell'applicazione selezionata.</span><span class="sxs-lookup"><span data-stu-id="95b92-156">In the **Platform version** field, use the platform version that is automatically chosen for the application version you selected.</span></span> 

    ![Selezione delle versioni della piattaforma e dell'applicazione](./media/project1.png)

1. <span data-ttu-id="95b92-158">Selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="95b92-158">Select **Next**.</span></span>
1. <span data-ttu-id="95b92-159">Selezionare **Demo** come topologia dell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="95b92-159">Select **Demo** as the environment topology.</span></span>

    ![Selezionare della topologia dell'ambiente 1](./media/project2.png)

1. <span data-ttu-id="95b92-161">Nella pagina **Ambiente di distribuzione**, inserire un nome di ambiente.</span><span class="sxs-lookup"><span data-stu-id="95b92-161">On the **Deploy environment** page, enter an environment name.</span></span> <span data-ttu-id="95b92-162">Non modificare le impostazioni avanzate.</span><span class="sxs-lookup"><span data-stu-id="95b92-162">Leave the advanced settings as they are.</span></span>

    ![Pagina dell'ambiente di distribuzione](./media/project4.png)

1. <span data-ttu-id="95b92-164">Regolare le dimensioni della VM come richiesto.</span><span class="sxs-lookup"><span data-stu-id="95b92-164">Adjust the VM size as required.</span></span> <span data-ttu-id="95b92-165">(Si consiglia un'unità di stockkeeping VM \[SKU\] **D13 v2** .)</span><span class="sxs-lookup"><span data-stu-id="95b92-165">(We recommend VM stock keeping unit \[SKU\] **D13 v2**.)</span></span>
1. <span data-ttu-id="95b92-166">Rivedere i termini relativi ai prezzi e alle licenze, quindi selezionare la casella di controllo per accettarli.</span><span class="sxs-lookup"><span data-stu-id="95b92-166">Review the pricing and licensing terms, and then select the check box to indicate that you agree to them.</span></span>
1. <span data-ttu-id="95b92-167">Selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="95b92-167">Select **Next**.</span></span>
1. <span data-ttu-id="95b92-168">Nella pagina di conferma della distribuzione, verificare che i dettagli siano corretti, quindi selezionare **Distribuisci**.</span><span class="sxs-lookup"><span data-stu-id="95b92-168">On the deployment confirmation page, verify that the details are correct, and then select **Deploy**.</span></span> <span data-ttu-id="95b92-169">Si ritorna alla visualizzazione **Distribuzione ambienti ospitati nel cloud** e il proprio l'ambiente deve essere visualizzato nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="95b92-169">You're returned to the **Cloud-hosted environments** view, and your environment should appear in the list.</span></span>

    <span data-ttu-id="95b92-170">L'ambiente richiesto viene visualizzato come accodato e quindi in fase di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="95b92-170">Your requested environment will appear as queued and then deploying.</span></span> <span data-ttu-id="95b92-171">Il completamento dei flussi di lavoro dell'ambiente richiederà del tempo.</span><span class="sxs-lookup"><span data-stu-id="95b92-171">The environment workflows will take some time to be completed.</span></span> <span data-ttu-id="95b92-172">Pertanto, ricontrollare dopo circa 6-9 ore.</span><span class="sxs-lookup"><span data-stu-id="95b92-172">Therefore, check back after approximately six to nine hours.</span></span>

1. <span data-ttu-id="95b92-173">Prima di procedere, assicurarsi che lo stato dell'ambiente sia **Distribuito**.</span><span class="sxs-lookup"><span data-stu-id="95b92-173">Before you continue, make sure that the status of your environment is **Deployed**.</span></span>

### <a name="initialize-the-commerce-scale-unit-cloud"></a><span data-ttu-id="95b92-174">Inizializzare Commerce Scale Unit (cloud)</span><span class="sxs-lookup"><span data-stu-id="95b92-174">Initialize the Commerce Scale Unit (cloud)</span></span>

<span data-ttu-id="95b92-175">Per inizializzare CSU, procedere come segue.</span><span class="sxs-lookup"><span data-stu-id="95b92-175">To initialize CSU, follow these steps.</span></span>

1. <span data-ttu-id="95b92-176">Nella visualizzazione **Distribuzione ambienti ospitati nel cloud**, selezionare l'ambiente nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="95b92-176">In the **Cloud-hosted environments** view, select your environment in the list.</span></span>
1. <span data-ttu-id="95b92-177">Nella visualizzazione dell'ambiente a destra, selezionare **Dettagli completi**.</span><span class="sxs-lookup"><span data-stu-id="95b92-177">In the environment view on the right, select **Full details**.</span></span> <span data-ttu-id="95b92-178">Vengono visualizzati i dettagli dell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="95b92-178">The environment details view appears.</span></span>
1. <span data-ttu-id="95b92-179">In **Funzionalità ambiente**, selezionare **Gestisci**.</span><span class="sxs-lookup"><span data-stu-id="95b92-179">Under **Environment features**, select **Manage**.</span></span>
1. <span data-ttu-id="95b92-180">Nella scheda **Commerce**, selezionare **Inizializza**.</span><span class="sxs-lookup"><span data-stu-id="95b92-180">On the **Commerce** tab, select **Initialize**.</span></span> <span data-ttu-id="95b92-181">Vengono visualizzati i parametri di inizializzazione della CSU.</span><span class="sxs-lookup"><span data-stu-id="95b92-181">The CSU initialization parameters view appears.</span></span>
1. <span data-ttu-id="95b92-182">Nel campo **Area**, selezionare la stessa area o l'area vicina a quella in cui è stato distribuito l'ambiente.</span><span class="sxs-lookup"><span data-stu-id="95b92-182">In the **Region** field, select the region that is the same or close to the region that you deployed the environment to.</span></span>
1. <span data-ttu-id="95b92-183">Lasciare invariato il campo **Versione**.</span><span class="sxs-lookup"><span data-stu-id="95b92-183">Leave the **Version** field as it is.</span></span>
1. <span data-ttu-id="95b92-184">Selezionare **Inizializza**.</span><span class="sxs-lookup"><span data-stu-id="95b92-184">Select **Initialize**.</span></span>
1. <span data-ttu-id="95b92-185">Nella pagina di conferma della distribuzione, verificare che i dettagli siano corretti, quindi selezionare **Sì**.</span><span class="sxs-lookup"><span data-stu-id="95b92-185">On the deployment confirmation page, verify that the details are correct, and then select **Yes**.</span></span> <span data-ttu-id="95b92-186">Viene visualizzato di nuovo **Gestione di Commerce** con la scheda **Commerce** selezionata.</span><span class="sxs-lookup"><span data-stu-id="95b92-186">The **Commerce management** view displays again, where the **Commerce** tab is selected.</span></span> <span data-ttu-id="95b92-187">La CSU è stata accodata per il provisioning.</span><span class="sxs-lookup"><span data-stu-id="95b92-187">Your CSU has been queued for provisioning.</span></span>
1. <span data-ttu-id="95b92-188">Prima di procedere, assicurarsi che lo stato dell'ambiente CSU sia **Completato**.</span><span class="sxs-lookup"><span data-stu-id="95b92-188">Before you continue, make sure that the status of your CSU is **Success**.</span></span> <span data-ttu-id="95b92-189">L'inizializzazione dura circa 2-5 ore.</span><span class="sxs-lookup"><span data-stu-id="95b92-189">Initialization takes approximately two to five hours.</span></span>

<span data-ttu-id="95b92-190">Se non si riesce a trovare il collegamento **Gestione** nella vista dei dettagli dell'ambiente, contattare il contatto Microsoft per assistenza.</span><span class="sxs-lookup"><span data-stu-id="95b92-190">If you can't find the **Manage** link in the environment details view, reach out to your Microsoft contact for assistance.</span></span>

### <a name="initialize-e-commerce"></a><span data-ttu-id="95b92-191">Inizializzare e-Commerce</span><span class="sxs-lookup"><span data-stu-id="95b92-191">Initialize e-Commerce</span></span>

<span data-ttu-id="95b92-192">Per inizializzare e-Commerce, procedere come segue.</span><span class="sxs-lookup"><span data-stu-id="95b92-192">To initialize e-Commerce, follow these steps.</span></span>

1. <span data-ttu-id="95b92-193">Nella scheda **e-Commerce**, rivedere il consenso di valutazione e quindi selezionare **Configura**.</span><span class="sxs-lookup"><span data-stu-id="95b92-193">On the **e-Commerce** tab, review the evaluation consent, and then select **Setup**.</span></span>
1. <span data-ttu-id="95b92-194">Immettere un nome per **Nome ambiente e-Commerce**.</span><span class="sxs-lookup"><span data-stu-id="95b92-194">In the **e-Commerce environment name** field, enter a name.</span></span> <span data-ttu-id="95b92-195">Da notare che ciò sarà visibile in alcuni degli URL che puntano all'istanza di e-Commerce.</span><span class="sxs-lookup"><span data-stu-id="95b92-195">Be aware that this name will appear in some of the URLs that point to your e-Commerce instance.</span></span>
1. <span data-ttu-id="95b92-196">Nel campo **Nome Commerce Scale Unit**, selezionare la CSU nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="95b92-196">In the **Commerce Scale Unit name** field, select your CSU in the list.</span></span> <span data-ttu-id="95b92-197">(L'elenco dovrebbe avere una sola opzione).</span><span class="sxs-lookup"><span data-stu-id="95b92-197">(The list should have only one option.)</span></span>

    <span data-ttu-id="95b92-198">Il campo **Geografia e-Commerce** viene impostato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="95b92-198">The **e-Commerce geography** field is set automatically.</span></span>

1. <span data-ttu-id="95b92-199">Selezionare **Avanti** per continuare.</span><span class="sxs-lookup"><span data-stu-id="95b92-199">Select **Next** to continue.</span></span>
1. <span data-ttu-id="95b92-200">Nel campo **Nomi host supportatiN**, immettere qualsiasi dominio valido, ad esempio `www.fabrikam.com`.</span><span class="sxs-lookup"><span data-stu-id="95b92-200">In the **Supported host names** field, enter any valid domain, such as `www.fabrikam.com`.</span></span>
1. <span data-ttu-id="95b92-201">Nel **Gruppo di sicurezza AAD per amministratore sistema**, immettere le prime lettere del nome del gruppo di sicurezza che si desidera utilizzare, quindi selezionare il simbolo della lente di ingrandimento per visualizzare i risultati della ricerca.</span><span class="sxs-lookup"><span data-stu-id="95b92-201">In the **AAD security group for system admin** field, enter the first few letters of the name of the security group that you want to use, and then select the magnifying glass symbol to view the search results.</span></span> <span data-ttu-id="95b92-202">Selezionare il gruppo di sicurezza corretto nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="95b92-202">Select the correct security group in the list.</span></span>
1.  <span data-ttu-id="95b92-203">Nel **Gruppo di sicurezza AAD per moderatore di valutazioni e recensioni**, immettere le prime lettere del nome del gruppo di sicurezza che si desidera utilizzare, quindi selezionare il simbolo della lente di ingrandimento per visualizzare i risultati della ricerca.</span><span class="sxs-lookup"><span data-stu-id="95b92-203">In the **AAD security group for ratings and review moderator** field, enter the first few letters of the name of the security group that you want to use, and then select the magnifying glass symbol to view the search results.</span></span> <span data-ttu-id="95b92-204">Selezionare il gruppo di sicurezza corretto nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="95b92-204">Select the correct security group in the list.</span></span>
1. <span data-ttu-id="95b92-205">Lasciare l'opzione **Abilita servizio Valutazioni e recensioni** impostata su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="95b92-205">Leave the **Enable ratings and review service** option set to **Yes**.</span></span>
1. <span data-ttu-id="95b92-206">Selezionare **Inizializza**.</span><span class="sxs-lookup"><span data-stu-id="95b92-206">Select **Initialize**.</span></span> <span data-ttu-id="95b92-207">Viene visualizzato di nuovo **Gestione di Commerce** con la scheda **e-Commerce** selezionata.</span><span class="sxs-lookup"><span data-stu-id="95b92-207">The **Commerce management** view displays again, where the **e-Commerce** tab is selected.</span></span> <span data-ttu-id="95b92-208">L'inizializzazione di e-Commerce è stata avviata.</span><span class="sxs-lookup"><span data-stu-id="95b92-208">E-Commerce initialization has started.</span></span>
1. <span data-ttu-id="95b92-209">Prima di procedere, attendere che lo stato dell'inizializzazione di e-Commerce sia **Inizializzazione riuscita**.</span><span class="sxs-lookup"><span data-stu-id="95b92-209">Before you continue, wait until the status of e-Commerce initialization is **Initialization successful**.</span></span>
1. <span data-ttu-id="95b92-210">In **Collegamenti** in basso a destra, prendi nota degli URL per i seguenti collegamenti:</span><span class="sxs-lookup"><span data-stu-id="95b92-210">Under **Links** in the lower right, make a note of the URLs for the following links:</span></span>

    * <span data-ttu-id="95b92-211">**Sito di e-Commerce**: il collegamento alla radice del tuo sito di e-Commerce.</span><span class="sxs-lookup"><span data-stu-id="95b92-211">**e-Commerce site** – The link to the root of your e-Commerce site.</span></span>
    * <span data-ttu-id="95b92-212">**Creazione di siti Web di Commerce**: il collegamento allo strumento di gestione del sito.</span><span class="sxs-lookup"><span data-stu-id="95b92-212">**Commerce site builder** – The link to the site management tool.</span></span>

## <a name="next-steps"></a><span data-ttu-id="95b92-213">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="95b92-213">Next steps</span></span>

<span data-ttu-id="95b92-214">Per proseguire il processo di provisioning e configurazione dell'ambiente di valutazione Commerce, consultare [Configurare un ambiente di valutazione Commerce](cpe-post-provisioning.md).</span><span class="sxs-lookup"><span data-stu-id="95b92-214">To continue the process of provisioning and configuring your Commerce evaluation environment, see [Configure a Commerce evaluation environment](cpe-post-provisioning.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="95b92-215">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="95b92-215">Additional resources</span></span>

[<span data-ttu-id="95b92-216">Panoramica dell'ambiente di valutazione Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="95b92-216">Dynamics 365 Commerce evaluation environment overview</span></span>](cpe-overview.md)

[<span data-ttu-id="95b92-217">Configurare un ambiente di valutazione Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="95b92-217">Configure a Dynamics 365 Commerce evaluation environment</span></span>](cpe-post-provisioning.md)

[<span data-ttu-id="95b92-218">Configurare uno scenario BOPIS in un ambiente di valutazione Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="95b92-218">Configure BOPIS in a Dynamics 365 Commerce evaluation environment</span></span>](cpe-bopis.md)

[<span data-ttu-id="95b92-219">Configurare le funzioni facoltative per un ambiente di valutazione Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="95b92-219">Configure optional features for a Dynamics 365 Commerce evaluation environment</span></span>](cpe-optional-features.md)

[<span data-ttu-id="95b92-220">Domande frequenti sull'ambiente di valutazione Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="95b92-220">Dynamics 365 Commerce evaluation environment FAQ</span></span>](cpe-faq.md)

[<span data-ttu-id="95b92-221">Microsoft Lifecycle Services (LCS)</span><span class="sxs-lookup"><span data-stu-id="95b92-221">Microsoft Lifecycle Services (LCS)</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide)

[<span data-ttu-id="95b92-222">Commerce Scale Unit (cloud)</span><span class="sxs-lookup"><span data-stu-id="95b92-222">Commerce Scale Unit (cloud)</span></span>](https://docs.microsoft.com/business-applications-release-notes/october18/dynamics365-retail/retail-cloud-scale-unit)

[<span data-ttu-id="95b92-223">Portale di Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="95b92-223">Microsoft Azure portal</span></span>](https://azure.microsoft.com/features/azure-portal)

[<span data-ttu-id="95b92-224">Sito Web di Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="95b92-224">Dynamics 365 Commerce website</span></span>](https://aka.ms/Dynamics365CommerceWebsite)
