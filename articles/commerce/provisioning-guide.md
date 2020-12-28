---
title: Provisioning di un ambiente di valutazione Dynamics 365 Commerce
description: Questo argomento illustra come eseguire il provisioning di un ambiente di valutazione Microsoft Dynamics 365 Commerce.
author: psimolin
manager: annbe
ms.date: 11/05/2020
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
ms.openlocfilehash: b54216a565c264dfcfe821581fee9df7b5e22323
ms.sourcegitcommit: 715508547f9a71a89a138190e8540686556c753d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/05/2020
ms.locfileid: "4413611"
---
# <a name="provision-a-dynamics-365-commerce-evaluation-environment"></a><span data-ttu-id="c50fd-103">Provisioning di un ambiente di valutazione Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="c50fd-103">Provision a Dynamics 365 Commerce evaluation environment</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="c50fd-104">Questo argomento illustra come eseguire il provisioning di un ambiente di valutazione Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="c50fd-104">This topic explains how to provision a Microsoft Dynamics 365 Commerce evaluation environment.</span></span>

<span data-ttu-id="c50fd-105">Prima di iniziare, è consigliabile dare una rapida occhiata a questo argomento per avere un'idea di ciò che richiede il processo.</span><span class="sxs-lookup"><span data-stu-id="c50fd-105">Before you begin, we recommend that you take a quick scan through this topic to get an idea of what the process requires.</span></span>

> [!NOTE]
> <span data-ttu-id="c50fd-106">Gli ambienti di valutazione di Commerce non sono generalmente disponibili e sono concessi a partner e clienti in base alla richiesta.</span><span class="sxs-lookup"><span data-stu-id="c50fd-106">Commerce evaluation environments aren't generally available, and are granted to partners and customers on a per-request basis.</span></span> <span data-ttu-id="c50fd-107">Per ulteriori informazioni, contattare il partner Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c50fd-107">For more information, reach out to your Microsoft partner contact.</span></span>

## <a name="overview"></a><span data-ttu-id="c50fd-108">Panoramica</span><span class="sxs-lookup"><span data-stu-id="c50fd-108">Overview</span></span>

<span data-ttu-id="c50fd-109">Per eseguire correttamente il provisioning di un ambiente di valutazione Commerce, è necessario creare un progetto con un nome e un tipo di prodotto specifici.</span><span class="sxs-lookup"><span data-stu-id="c50fd-109">To successfully provision a Commerce evaluation environment, you must create a project that has a specific product name and type.</span></span> <span data-ttu-id="c50fd-110">Anche l'ambiente e Commerce Scale Unit hanno alcuni parametri specifici che devono essere utilizzati quando si prevede di eseguire il provisioning di e-Commerce in seguito.</span><span class="sxs-lookup"><span data-stu-id="c50fd-110">The environment and Commerce Scale Unit (CSU) also have some specific parameters that you must use when you expect to provision e-Commerce later.</span></span> <span data-ttu-id="c50fd-111">Le istruzioni in questo argomento descrivono tutti i passaggi necessari per completare il provisioning e i parametri da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="c50fd-111">The instructions in this topic describe all the steps that are required to complete provisioning and the parameters that you must use.</span></span>

<span data-ttu-id="c50fd-112">Dopo aver completato il provisioning dell'ambiente di valutazione di Commerce, è necessario completare alcuni passaggi post-provisioning per prepararlo all'uso.</span><span class="sxs-lookup"><span data-stu-id="c50fd-112">After you successfully provision your Commerce evaluation environment, you must complete a few post-provisioning steps to prepare it for use.</span></span> <span data-ttu-id="c50fd-113">Alcuni passaggi sono facoltativi, a seconda degli aspetti del sistema che si desidera valutare.</span><span class="sxs-lookup"><span data-stu-id="c50fd-113">Some steps are optional, depending on the aspects of the system that you want to evaluate.</span></span> <span data-ttu-id="c50fd-114">È sempre possibile completare i passaggi facoltativi in seguito.</span><span class="sxs-lookup"><span data-stu-id="c50fd-114">You can always complete the optional steps later.</span></span>

<span data-ttu-id="c50fd-115">Per informazioni relative a come configurare l'ambiente di valutazione di Commerce dopo il provisioning, consultare [Configurare un ambiente di valutazione di Commerce](cpe-post-provisioning.md).</span><span class="sxs-lookup"><span data-stu-id="c50fd-115">For information about how to configure your Commerce evaluation environment after you provision it, see [Configure a Commerce evaluation environment](cpe-post-provisioning.md).</span></span> <span data-ttu-id="c50fd-116">Per informazioni su come configurare funzionalità facoltative per l'ambiente di valutazione Commerce, vedere [Configurare le funzionalità facoltative per un ambiente di valutazione Commerce](cpe-optional-features.md).</span><span class="sxs-lookup"><span data-stu-id="c50fd-116">For information about how to configure optional features for your Commerce evaluation environment, see [Configure optional features for a Commerce evaluation environment](cpe-optional-features.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="c50fd-117">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="c50fd-117">Prerequisites</span></span>

<span data-ttu-id="c50fd-118">I seguenti prerequisiti devono essere presenti prima di poter eseguire il provisioning dell'ambiente di valutazione Commerce:</span><span class="sxs-lookup"><span data-stu-id="c50fd-118">The following prerequisites must be in place before you can provision your Commerce evaluation environment:</span></span>

- <span data-ttu-id="c50fd-119">Essere inseriti nel programma di valutazione e aver ottenuto la capacità per un ambiente di valutazione.</span><span class="sxs-lookup"><span data-stu-id="c50fd-119">You have been onboarded into the evaluation program and granted capacity for an evaluation environment.</span></span>
- <span data-ttu-id="c50fd-120">Si dispone dell'accesso al portale di Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="c50fd-120">You have access to the Microsoft Dynamics Lifecycle Services (LCS) portal.</span></span>
- <span data-ttu-id="c50fd-121">Si è un partner o cliente di Microsoft Dynamics 365 e si è in grado di creare un progetto Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="c50fd-121">You are an existing Microsoft Dynamics 365 partner or customer and are able to create a Dynamics 365 Commerce project.</span></span>
- <span data-ttu-id="c50fd-122">Si dispone dell'accesso di amministratore alla sottoscrizione Microsoft Azure o si è in contatto con un amministratore della sottoscrizione che può fornire assistenza se necessario.</span><span class="sxs-lookup"><span data-stu-id="c50fd-122">You have administrator access to your Microsoft Azure subscription, or you're in contact with a subscription administrator who can assist you if required.</span></span>
- <span data-ttu-id="c50fd-123">Si ha a disposizione l'ID tenant di Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="c50fd-123">You have your Azure Active Directory (Azure AD) tenant ID available.</span></span>
- <span data-ttu-id="c50fd-124">È stato creato un gruppo di sicurezza Azure AD da utilizzare come gruppo Amministratori del sistema di e-Commerce e si dispone del relativo ID.</span><span class="sxs-lookup"><span data-stu-id="c50fd-124">You've created an Azure AD security group that can be used as an e-Commerce system admin group, and you have its ID available.</span></span>
- <span data-ttu-id="c50fd-125">È stato creato un gruppo di sicurezza Azure AD da utilizzare come gruppo di moderatori di Valutazioni e revisioni e devi disporre del relativo ID.</span><span class="sxs-lookup"><span data-stu-id="c50fd-125">You've created an Azure AD security group that can be used as a Ratings and Reviews moderator group, and you have its ID available.</span></span> <span data-ttu-id="c50fd-126">(Questo gruppo di sicurezza può essere lo stesso del gruppo di amministratori del sistema e-Commerce).</span><span class="sxs-lookup"><span data-stu-id="c50fd-126">(This security group can be the same as the e-Commerce system admin group.)</span></span>

<span data-ttu-id="c50fd-127">Si noti che questo elenco non è esaustivo.</span><span class="sxs-lookup"><span data-stu-id="c50fd-127">Note that this list isn't exhaustive.</span></span> <span data-ttu-id="c50fd-128">In caso di problemi, contattare il partner Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c50fd-128">If you experience any issues, reach out to your Microsoft partner contact for assistance.</span></span>

## <a name="provision-your-commerce-evaluation-environment"></a><span data-ttu-id="c50fd-129">Eseguire il provisioning di un ambiente di valutazione Commerce</span><span class="sxs-lookup"><span data-stu-id="c50fd-129">Provision your Commerce evaluation environment</span></span>

<span data-ttu-id="c50fd-130">Queste procedure spiegano come eseguire il provisioning di un ambiente di valutazione Commerce.</span><span class="sxs-lookup"><span data-stu-id="c50fd-130">These procedures explain how to provision a Commerce evaluation environment.</span></span> <span data-ttu-id="c50fd-131">Dopo averle completate, l'ambiente di valutazione Commerce sarà pronto per la configurazione.</span><span class="sxs-lookup"><span data-stu-id="c50fd-131">After you successfully complete them, the Commerce evaluation environment will be ready for configuration.</span></span> <span data-ttu-id="c50fd-132">Tutte le attività descritte qui possono verificarsi nel portale di LCS.</span><span class="sxs-lookup"><span data-stu-id="c50fd-132">All the activities that are described here occur in the LCS portal.</span></span>

### <a name="create-a-new-project"></a><span data-ttu-id="c50fd-133">Crea un nuovo progetto</span><span class="sxs-lookup"><span data-stu-id="c50fd-133">Create a new project</span></span>

<span data-ttu-id="c50fd-134">Per creare un nuovo progetto in LCS, completare i passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="c50fd-134">To create a new project in LCS, follow these steps.</span></span>

1. <span data-ttu-id="c50fd-135">Nella home page di LCS, selezionare il segno più (**+**) per creare un progetto.</span><span class="sxs-lookup"><span data-stu-id="c50fd-135">On the LCS home page, select the plus sign (**+**) to create a project.</span></span>
1. <span data-ttu-id="c50fd-136">Nel riquadro destro, seguire uno di questi passaggi:</span><span class="sxs-lookup"><span data-stu-id="c50fd-136">In the right pane, follow one of these steps:</span></span>

    - <span data-ttu-id="c50fd-137">Se si è un partner, scegliere **Migrare, creare soluzioni e ottenere informazioni**.</span><span class="sxs-lookup"><span data-stu-id="c50fd-137">If you're a partner, select **Migrate, create solutions, and learn**.</span></span>
    - <span data-ttu-id="c50fd-138">Se si è un cliente, scegliere **Pre-vendite potenziali**.</span><span class="sxs-lookup"><span data-stu-id="c50fd-138">If you're a customer, select **Prospective presales**.</span></span>

1. <span data-ttu-id="c50fd-139">Immettere un nome, una descrizione e il settore.</span><span class="sxs-lookup"><span data-stu-id="c50fd-139">Enter a name, description, and industry.</span></span>
1. <span data-ttu-id="c50fd-140">Nel campo **Nome prodotto**, selezionare **Dynamics 365 Commerce**.</span><span class="sxs-lookup"><span data-stu-id="c50fd-140">In the **Product name** field, select **Dynamics 365 Commerce**.</span></span>
1. <span data-ttu-id="c50fd-141">Nel campo **Versione prodotto**, selezionare **Dynamics 365 Commerce**.</span><span class="sxs-lookup"><span data-stu-id="c50fd-141">In the **Product version** field, select **Dynamics 365 Commerce**.</span></span>
1. <span data-ttu-id="c50fd-142">Nel campo **Metodologia**, selezionare **Metodologia di implementazione di Dynamics Retail**.</span><span class="sxs-lookup"><span data-stu-id="c50fd-142">In the **Methodology** field, select **Dynamics Retail implementation methodology**.</span></span>
1. <span data-ttu-id="c50fd-143">Facoltativo, è possibile importare ruoli e utenti da un progetto esistente.</span><span class="sxs-lookup"><span data-stu-id="c50fd-143">Optional: You can import roles and users from an existing project.</span></span>
1. <span data-ttu-id="c50fd-144">Selezionare **Crea**.</span><span class="sxs-lookup"><span data-stu-id="c50fd-144">Select **Create**.</span></span> <span data-ttu-id="c50fd-145">Appare la visualizzazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="c50fd-145">The project view appears.</span></span>

### <a name="add-the-azure-connector"></a><span data-ttu-id="c50fd-146">Aggiungere il connettore di Azure</span><span class="sxs-lookup"><span data-stu-id="c50fd-146">Add the Azure Connector</span></span>

<span data-ttu-id="c50fd-147">Per aggiungere il connettore di Azure al progetto LCS, seguire i passaggi in [Completare il processo di onboarding di Azure Resource Manager (ARM)](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/deployment/arm-onboarding).</span><span class="sxs-lookup"><span data-stu-id="c50fd-147">To add the Azure Connector to your LCS project, follow the steps in [Complete the Azure Resource Manager (ARM) onboarding process](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/deployment/arm-onboarding).</span></span>

### <a name="deploy-the-environment"></a><span data-ttu-id="c50fd-148">Distribuire l'ambiente</span><span class="sxs-lookup"><span data-stu-id="c50fd-148">Deploy the environment</span></span>

<span data-ttu-id="c50fd-149">Per distribuire l'ambiente, attenersi a questa procedura.</span><span class="sxs-lookup"><span data-stu-id="c50fd-149">To deploy the environment, follow these steps.</span></span>

> [!NOTE]
> <span data-ttu-id="c50fd-150">Potrebbe non essere necessario completare i passaggi 6, 7 e/o 8, poiché le pagine con una singola opzione vengono ignorate.</span><span class="sxs-lookup"><span data-stu-id="c50fd-150">You might not have to complete steps 6, 7, and/or 8, because pages that have a single option are skipped.</span></span> <span data-ttu-id="c50fd-151">Nella visualizzazione **Parametri dell'ambiente**, confermare che il testo **Dynamics 365 Commerce - Demo (10.0.* x* con update *xx* della piattaforma)\*\* appaia direttamente sopra il campo **Nome ambiente**.</span><span class="sxs-lookup"><span data-stu-id="c50fd-151">When you're in the **Environment parameters** view, confirm that the text **Dynamics 365 Commerce - Demo (10.0.* x* with Platform update *xx*)\*\* appears directly above the **Environment name** field.</span></span> <span data-ttu-id="c50fd-152">Per dettagli, vedere l'illustrazione che appare dopo il passaggio 8.</span><span class="sxs-lookup"><span data-stu-id="c50fd-152">For details, see the illustration that appears after step 8.</span></span>

1. <span data-ttu-id="c50fd-153">Nel menu superiore, selezionare **Distribuzione ambienti ospitati nel cloud**.</span><span class="sxs-lookup"><span data-stu-id="c50fd-153">On the top menu, select **Cloud-hosted environments**.</span></span>
1. <span data-ttu-id="c50fd-154">Selezionare **Aggiungi** per aggiungere un ambiente.</span><span class="sxs-lookup"><span data-stu-id="c50fd-154">Select **Add** to add an environment.</span></span>
1. <span data-ttu-id="c50fd-155">Nel campo **Versione applicazione**, selezionare la versione più recente.</span><span class="sxs-lookup"><span data-stu-id="c50fd-155">In the **Application version** field, select the most current version.</span></span> <span data-ttu-id="c50fd-156">Se si ha la necessità di selezionare una versione dell'applicazione diversa dalla versione più recente, non selezionare una versione precedente alla versione **10.0.14**.</span><span class="sxs-lookup"><span data-stu-id="c50fd-156">If you have a specific need to select an application version other than the most current version, do not select a version prior to **10.0.14**.</span></span>
1. <span data-ttu-id="c50fd-157">Nel campo **Versione piattaforma**, utilizzare la versione della piattaforma che viene scelta automaticamente per la versione dell'applicazione selezionata.</span><span class="sxs-lookup"><span data-stu-id="c50fd-157">In the **Platform version** field, use the platform version that is automatically chosen for the application version you selected.</span></span> 

    ![Selezione delle versioni della piattaforma e dell'applicazione](./media/project1.png)

1. <span data-ttu-id="c50fd-159">Selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="c50fd-159">Select **Next**.</span></span>
1. <span data-ttu-id="c50fd-160">Selezionare **Demo** come topologia dell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="c50fd-160">Select **Demo** as the environment topology.</span></span>

    ![Selezionare della topologia dell'ambiente 1](./media/project2.png)

1. <span data-ttu-id="c50fd-162">Nella pagina **Ambiente di distribuzione**, inserire un nome di ambiente.</span><span class="sxs-lookup"><span data-stu-id="c50fd-162">On the **Deploy environment** page, enter an environment name.</span></span> <span data-ttu-id="c50fd-163">Non modificare le impostazioni avanzate.</span><span class="sxs-lookup"><span data-stu-id="c50fd-163">Leave the advanced settings as they are.</span></span>

    ![Pagina dell'ambiente di distribuzione](./media/project4.png)

1. <span data-ttu-id="c50fd-165">Regolare le dimensioni della VM come richiesto.</span><span class="sxs-lookup"><span data-stu-id="c50fd-165">Adjust the VM size as required.</span></span> <span data-ttu-id="c50fd-166">(Si consiglia un'unità di stockkeeping VM \[SKU\] **D13 v2** .)</span><span class="sxs-lookup"><span data-stu-id="c50fd-166">(We recommend VM stock keeping unit \[SKU\] **D13 v2**.)</span></span>
1. <span data-ttu-id="c50fd-167">Rivedere i termini relativi ai prezzi e alle licenze, quindi selezionare la casella di controllo per accettarli.</span><span class="sxs-lookup"><span data-stu-id="c50fd-167">Review the pricing and licensing terms, and then select the check box to indicate that you agree to them.</span></span>
1. <span data-ttu-id="c50fd-168">Selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="c50fd-168">Select **Next**.</span></span>
1. <span data-ttu-id="c50fd-169">Nella pagina di conferma della distribuzione, verificare che i dettagli siano corretti, quindi selezionare **Distribuisci**.</span><span class="sxs-lookup"><span data-stu-id="c50fd-169">On the deployment confirmation page, verify that the details are correct, and then select **Deploy**.</span></span> <span data-ttu-id="c50fd-170">Si ritorna alla visualizzazione **Distribuzione ambienti ospitati nel cloud** e il proprio l'ambiente deve essere visualizzato nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="c50fd-170">You're returned to the **Cloud-hosted environments** view, and your environment should appear in the list.</span></span>

    <span data-ttu-id="c50fd-171">L'ambiente richiesto viene visualizzato come accodato e quindi in fase di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="c50fd-171">Your requested environment will appear as queued and then deploying.</span></span> <span data-ttu-id="c50fd-172">Il completamento dei flussi di lavoro dell'ambiente richiederà del tempo.</span><span class="sxs-lookup"><span data-stu-id="c50fd-172">The environment workflows will take some time to be completed.</span></span> <span data-ttu-id="c50fd-173">Pertanto, ricontrollare dopo circa 6-9 ore.</span><span class="sxs-lookup"><span data-stu-id="c50fd-173">Therefore, check back after approximately six to nine hours.</span></span>

1. <span data-ttu-id="c50fd-174">Prima di procedere, assicurarsi che lo stato dell'ambiente sia **Distribuito**.</span><span class="sxs-lookup"><span data-stu-id="c50fd-174">Before you continue, make sure that the status of your environment is **Deployed**.</span></span>

### <a name="initialize-the-commerce-scale-unit-cloud"></a><span data-ttu-id="c50fd-175">Inizializzare Commerce Scale Unit (cloud)</span><span class="sxs-lookup"><span data-stu-id="c50fd-175">Initialize the Commerce Scale Unit (cloud)</span></span>

<span data-ttu-id="c50fd-176">Per inizializzare CSU, procedere come segue.</span><span class="sxs-lookup"><span data-stu-id="c50fd-176">To initialize CSU, follow these steps.</span></span>

1. <span data-ttu-id="c50fd-177">Nella visualizzazione **Distribuzione ambienti ospitati nel cloud**, selezionare l'ambiente nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="c50fd-177">In the **Cloud-hosted environments** view, select your environment in the list.</span></span>
1. <span data-ttu-id="c50fd-178">Nella visualizzazione dell'ambiente a destra, selezionare **Dettagli completi**.</span><span class="sxs-lookup"><span data-stu-id="c50fd-178">In the environment view on the right, select **Full details**.</span></span> <span data-ttu-id="c50fd-179">Vengono visualizzati i dettagli dell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="c50fd-179">The environment details view appears.</span></span>
1. <span data-ttu-id="c50fd-180">In **Funzionalità ambiente**, selezionare **Gestisci**.</span><span class="sxs-lookup"><span data-stu-id="c50fd-180">Under **Environment features**, select **Manage**.</span></span>
1. <span data-ttu-id="c50fd-181">Nella scheda **Commerce**, selezionare **Inizializza**.</span><span class="sxs-lookup"><span data-stu-id="c50fd-181">On the **Commerce** tab, select **Initialize**.</span></span> <span data-ttu-id="c50fd-182">Vengono visualizzati i parametri di inizializzazione della CSU.</span><span class="sxs-lookup"><span data-stu-id="c50fd-182">The CSU initialization parameters view appears.</span></span>
1. <span data-ttu-id="c50fd-183">Nel campo **Area**, selezionare la stessa area o l'area vicina a quella in cui è stato distribuito l'ambiente.</span><span class="sxs-lookup"><span data-stu-id="c50fd-183">In the **Region** field, select the region that is the same or close to the region that you deployed the environment to.</span></span>
1. <span data-ttu-id="c50fd-184">Lasciare invariato il campo **Versione**.</span><span class="sxs-lookup"><span data-stu-id="c50fd-184">Leave the **Version** field as it is.</span></span>
1. <span data-ttu-id="c50fd-185">Selezionare **Inizializza**.</span><span class="sxs-lookup"><span data-stu-id="c50fd-185">Select **Initialize**.</span></span>
1. <span data-ttu-id="c50fd-186">Nella pagina di conferma della distribuzione, verificare che i dettagli siano corretti, quindi selezionare **Sì**.</span><span class="sxs-lookup"><span data-stu-id="c50fd-186">On the deployment confirmation page, verify that the details are correct, and then select **Yes**.</span></span> <span data-ttu-id="c50fd-187">Viene visualizzato di nuovo **Gestione di Commerce** con la scheda **Commerce** selezionata.</span><span class="sxs-lookup"><span data-stu-id="c50fd-187">The **Commerce management** view displays again, where the **Commerce** tab is selected.</span></span> <span data-ttu-id="c50fd-188">La CSU è stata accodata per il provisioning.</span><span class="sxs-lookup"><span data-stu-id="c50fd-188">Your CSU has been queued for provisioning.</span></span>
1. <span data-ttu-id="c50fd-189">Prima di procedere, assicurarsi che lo stato dell'ambiente CSU sia **Completato**.</span><span class="sxs-lookup"><span data-stu-id="c50fd-189">Before you continue, make sure that the status of your CSU is **Success**.</span></span> <span data-ttu-id="c50fd-190">L'inizializzazione dura circa 2-5 ore.</span><span class="sxs-lookup"><span data-stu-id="c50fd-190">Initialization takes approximately two to five hours.</span></span>

<span data-ttu-id="c50fd-191">Se non si riesce a trovare il collegamento **Gestione** nella vista dei dettagli dell'ambiente, contattare il contatto Microsoft per assistenza.</span><span class="sxs-lookup"><span data-stu-id="c50fd-191">If you can't find the **Manage** link in the environment details view, reach out to your Microsoft contact for assistance.</span></span>

### <a name="initialize-e-commerce"></a><span data-ttu-id="c50fd-192">Inizializzare e-Commerce</span><span class="sxs-lookup"><span data-stu-id="c50fd-192">Initialize e-Commerce</span></span>

<span data-ttu-id="c50fd-193">Per inizializzare e-Commerce, procedere come segue.</span><span class="sxs-lookup"><span data-stu-id="c50fd-193">To initialize e-Commerce, follow these steps.</span></span>

1. <span data-ttu-id="c50fd-194">Nella scheda **e-Commerce**, rivedere il consenso di valutazione e quindi selezionare **Configura**.</span><span class="sxs-lookup"><span data-stu-id="c50fd-194">On the **e-Commerce** tab, review the evaluation consent, and then select **Setup**.</span></span>
1. <span data-ttu-id="c50fd-195">Immettere un nome per **Nome ambiente e-Commerce**.</span><span class="sxs-lookup"><span data-stu-id="c50fd-195">In the **e-Commerce environment name** field, enter a name.</span></span> <span data-ttu-id="c50fd-196">Da notare che ciò sarà visibile in alcuni degli URL che puntano all'istanza di e-Commerce.</span><span class="sxs-lookup"><span data-stu-id="c50fd-196">Be aware that this name will appear in some of the URLs that point to your e-Commerce instance.</span></span>
1. <span data-ttu-id="c50fd-197">Nel campo **Nome Commerce Scale Unit**, selezionare la CSU nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="c50fd-197">In the **Commerce Scale Unit name** field, select your CSU in the list.</span></span> <span data-ttu-id="c50fd-198">(L'elenco dovrebbe avere una sola opzione).</span><span class="sxs-lookup"><span data-stu-id="c50fd-198">(The list should have only one option.)</span></span>

    <span data-ttu-id="c50fd-199">Il campo **Geografia e-Commerce** viene impostato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="c50fd-199">The **e-Commerce geography** field is set automatically.</span></span>

1. <span data-ttu-id="c50fd-200">Selezionare **Avanti** per continuare.</span><span class="sxs-lookup"><span data-stu-id="c50fd-200">Select **Next** to continue.</span></span>
1. <span data-ttu-id="c50fd-201">Nel campo **Nomi host supportatiN**, immettere qualsiasi dominio valido, ad esempio `www.fabrikam.com`.</span><span class="sxs-lookup"><span data-stu-id="c50fd-201">In the **Supported host names** field, enter any valid domain, such as `www.fabrikam.com`.</span></span>
1. <span data-ttu-id="c50fd-202">Nel **Gruppo di sicurezza AAD per amministratore sistema**, immettere le prime lettere del nome del gruppo di sicurezza che si desidera utilizzare, quindi selezionare il simbolo della lente di ingrandimento per visualizzare i risultati della ricerca.</span><span class="sxs-lookup"><span data-stu-id="c50fd-202">In the **AAD security group for system admin** field, enter the first few letters of the name of the security group that you want to use, and then select the magnifying glass symbol to view the search results.</span></span> <span data-ttu-id="c50fd-203">Selezionare il gruppo di sicurezza corretto nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="c50fd-203">Select the correct security group in the list.</span></span>
1.  <span data-ttu-id="c50fd-204">Nel **Gruppo di sicurezza AAD per moderatore di valutazioni e recensioni**, immettere le prime lettere del nome del gruppo di sicurezza che si desidera utilizzare, quindi selezionare il simbolo della lente di ingrandimento per visualizzare i risultati della ricerca.</span><span class="sxs-lookup"><span data-stu-id="c50fd-204">In the **AAD security group for ratings and review moderator** field, enter the first few letters of the name of the security group that you want to use, and then select the magnifying glass symbol to view the search results.</span></span> <span data-ttu-id="c50fd-205">Selezionare il gruppo di sicurezza corretto nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="c50fd-205">Select the correct security group in the list.</span></span>
1. <span data-ttu-id="c50fd-206">Lasciare l'opzione **Abilita servizio Valutazioni e recensioni** impostata su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="c50fd-206">Leave the **Enable ratings and review service** option set to **Yes**.</span></span>
1. <span data-ttu-id="c50fd-207">Selezionare **Inizializza**.</span><span class="sxs-lookup"><span data-stu-id="c50fd-207">Select **Initialize**.</span></span> <span data-ttu-id="c50fd-208">Viene visualizzato di nuovo **Gestione di Commerce** con la scheda **e-Commerce** selezionata.</span><span class="sxs-lookup"><span data-stu-id="c50fd-208">The **Commerce management** view displays again, where the **e-Commerce** tab is selected.</span></span> <span data-ttu-id="c50fd-209">L'inizializzazione di e-Commerce è stata avviata.</span><span class="sxs-lookup"><span data-stu-id="c50fd-209">E-Commerce initialization has started.</span></span>
1. <span data-ttu-id="c50fd-210">Prima di procedere, attendere che lo stato dell'inizializzazione di e-Commerce sia **Inizializzazione riuscita**.</span><span class="sxs-lookup"><span data-stu-id="c50fd-210">Before you continue, wait until the status of e-Commerce initialization is **Initialization successful**.</span></span>
1. <span data-ttu-id="c50fd-211">In **Collegamenti** in basso a destra, prendi nota degli URL per i seguenti collegamenti:</span><span class="sxs-lookup"><span data-stu-id="c50fd-211">Under **Links** in the lower right, make a note of the URLs for the following links:</span></span>

    * <span data-ttu-id="c50fd-212">**Sito di e-Commerce**: il collegamento alla radice del tuo sito di e-Commerce.</span><span class="sxs-lookup"><span data-stu-id="c50fd-212">**e-Commerce site** – The link to the root of your e-Commerce site.</span></span>
    * <span data-ttu-id="c50fd-213">**Creazione di siti Web di Commerce**: il collegamento allo strumento di gestione del sito.</span><span class="sxs-lookup"><span data-stu-id="c50fd-213">**Commerce site builder** – The link to the site management tool.</span></span>

## <a name="next-steps"></a><span data-ttu-id="c50fd-214">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="c50fd-214">Next steps</span></span>

<span data-ttu-id="c50fd-215">Per proseguire il processo di provisioning e configurazione dell'ambiente di valutazione Commerce, consultare [Configurare un ambiente di valutazione Commerce](cpe-post-provisioning.md).</span><span class="sxs-lookup"><span data-stu-id="c50fd-215">To continue the process of provisioning and configuring your Commerce evaluation environment, see [Configure a Commerce evaluation environment](cpe-post-provisioning.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c50fd-216">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="c50fd-216">Additional resources</span></span>

[<span data-ttu-id="c50fd-217">Panoramica dell'ambiente di valutazione Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="c50fd-217">Dynamics 365 Commerce evaluation environment overview</span></span>](cpe-overview.md)

[<span data-ttu-id="c50fd-218">Configurare un ambiente di valutazione Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="c50fd-218">Configure a Dynamics 365 Commerce evaluation environment</span></span>](cpe-post-provisioning.md)

[<span data-ttu-id="c50fd-219">Configurare uno scenario BOPIS in un ambiente di valutazione Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="c50fd-219">Configure BOPIS in a Dynamics 365 Commerce evaluation environment</span></span>](cpe-bopis.md)

[<span data-ttu-id="c50fd-220">Configurare le funzioni facoltative per un ambiente di valutazione Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="c50fd-220">Configure optional features for a Dynamics 365 Commerce evaluation environment</span></span>](cpe-optional-features.md)

[<span data-ttu-id="c50fd-221">Domande frequenti sull'ambiente di valutazione Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="c50fd-221">Dynamics 365 Commerce evaluation environment FAQ</span></span>](cpe-faq.md)

[<span data-ttu-id="c50fd-222">Microsoft Lifecycle Services (LCS)</span><span class="sxs-lookup"><span data-stu-id="c50fd-222">Microsoft Lifecycle Services (LCS)</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide)

[<span data-ttu-id="c50fd-223">Commerce Scale Unit (cloud)</span><span class="sxs-lookup"><span data-stu-id="c50fd-223">Commerce Scale Unit (cloud)</span></span>](https://docs.microsoft.com/business-applications-release-notes/october18/dynamics365-retail/retail-cloud-scale-unit)

[<span data-ttu-id="c50fd-224">Portale di Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="c50fd-224">Microsoft Azure portal</span></span>](https://azure.microsoft.com/features/azure-portal)

[<span data-ttu-id="c50fd-225">Sito Web di Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="c50fd-225">Dynamics 365 Commerce website</span></span>](https://aka.ms/Dynamics365CommerceWebsite)
