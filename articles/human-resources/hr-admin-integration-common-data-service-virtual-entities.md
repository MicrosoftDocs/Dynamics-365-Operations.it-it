---
title: Configurare le entità virtuali di Common Data Service
description: In questo argomento viene descritto come configurare le entità virtuali di Dynamics 365 Human Resources. Genera e aggiorna entità virtuali esistenti e analizza entità generate e disponibili.
author: andreabichsel
manager: tfehr
ms.date: 10/05/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: CDSIntegrationAdministration
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-10-05
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 0d6f79ea569a7a9b0d25e73e8666bf9ba19095d0
ms.sourcegitcommit: a8665c47696028d371cdc4671db1fd8fcf9e1088
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/21/2020
ms.locfileid: "4058156"
---
# <a name="configure-common-data-service-virtual-entities"></a><span data-ttu-id="e640a-104">Configurare le entità virtuali di Common Data Service</span><span class="sxs-lookup"><span data-stu-id="e640a-104">Configure Common Data Service virtual entities</span></span>

[!include [banner](includes/preview-feature.md)]

<span data-ttu-id="e640a-105">Dynamics 365 Human Resources è un'origine dati virtuale in Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="e640a-105">Dynamics 365 Human Resources is a virtual data source in Common Data Service.</span></span> <span data-ttu-id="e640a-106">Fornisce operazioni complete di creazione, lettura, aggiornamento ed eliminazione (CRUD) di Common Data Service e Microsoft Power Platform.</span><span class="sxs-lookup"><span data-stu-id="e640a-106">It provides full create, read, update, and delete (CRUD) operations from Common Data Service and Microsoft Power Platform.</span></span> <span data-ttu-id="e640a-107">I dati delle entità virtuali non sono archiviati in Common Data Service, ma nel database dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="e640a-107">The data for virtual entities isn't stored in Common Data Service, but in the application database.</span></span> 

<span data-ttu-id="e640a-108">Per abilitare le operazioni CRUD nelle entità di Human Resources da Common Data Service, devi rendere le entità disponibili come entità virtuali in Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="e640a-108">To enable CRUD operations on Human Resources entities from Common Data Service, you must make the entities available as virtual entities in Common Data Service.</span></span> <span data-ttu-id="e640a-109">Ciò consente di eseguire operazioni CRUD di Common Data Service e Microsoft Power Platform sui dati presenti in Human Resources.</span><span class="sxs-lookup"><span data-stu-id="e640a-109">This lets you perform CRUD operations from Common Data Service and Microsoft Power Platform on data that's in Human Resources.</span></span> <span data-ttu-id="e640a-110">Le operazioni supportano anche le convalide complete della logica aziendale di Human Resources per garantire l'integrità dei dati durante la scrittura degli stessi nelle entità.</span><span class="sxs-lookup"><span data-stu-id="e640a-110">The operations also support the full business logic validations of Human Resources to ensure data integrity when writing data to the entities.</span></span>

## <a name="available-virtual-entities-for-human-resources"></a><span data-ttu-id="e640a-111">Entità virtuali disponibili per Human Resources</span><span class="sxs-lookup"><span data-stu-id="e640a-111">Available virtual entities for Human Resources</span></span>

<span data-ttu-id="e640a-112">Tutte le entità Open Data Protocol (OData) di Human Resources sono disponibili come entità virtuali in Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="e640a-112">All Open Data Protocol (OData) entities in Human Resources are available as virtual entities in Common Data Service.</span></span> <span data-ttu-id="e640a-113">Sono inoltre disponibili in Power Platform.</span><span class="sxs-lookup"><span data-stu-id="e640a-113">They're also available in Power Platform.</span></span> <span data-ttu-id="e640a-114">Ora puoi creare app ed esperienze con dati direttamente da Human Resources mediante funzionalità CRUD complete, senza copiare o sincronizzare i dati in Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="e640a-114">You can now build apps and experiences with data directly from Human Resources with full CRUD capability, without copying or synchronizing data to Common Data Service.</span></span> <span data-ttu-id="e640a-115">Puoi usare i portali Power Apps per creare siti Web rivolti all'esterno che consentono scenari di collaborazione per processi aziendali in Human Resources.</span><span class="sxs-lookup"><span data-stu-id="e640a-115">You can use Power Apps portals to build external-facing websites that enable collaboration scenarios for business processes in Human Resources.</span></span>

<span data-ttu-id="e640a-116">Puoi visualizzare l'elenco delle entità virtuali abilitate nell'ambiente e iniziare a lavorare con le entità in [Power Apps](https://make.powerapps.com), nella soluzione **Dynamics 365 HR Virtual Entities**.</span><span class="sxs-lookup"><span data-stu-id="e640a-116">You can view the list of virtual entities enabled in the environment, and begin working with the entities in [Power Apps](https://make.powerapps.com), in the **Dynamics 365 HR Virtual Entities** solution.</span></span>

![Dynamics 365 HR Virtual Entities in Power Apps](./media/hr-admin-integration-virtual-entities-power-apps.jpg)

## <a name="virtual-entities-versus-natural-entities"></a><span data-ttu-id="e640a-118">Entità virtuali e entità naturali</span><span class="sxs-lookup"><span data-stu-id="e640a-118">Virtual entities versus natural entities</span></span>

<span data-ttu-id="e640a-119">Le entità virtuali di Human Resources non sono uguali alle entità Common Data Service naturali create per Human Resources.</span><span class="sxs-lookup"><span data-stu-id="e640a-119">Virtual entities for Human Resources aren't the same as the natural Common Data Service entities created for Human Resources.</span></span> <span data-ttu-id="e640a-120">Le entità naturali per Human Resources vengono generate separatamente e gestite nella soluzione Gestione connessione ibrida comune in Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="e640a-120">The natural entities for Human Resources are generated separately and maintained in the HCM Common solution in Common Data Service.</span></span> <span data-ttu-id="e640a-121">Con le entità naturali, i dati vengono archiviati in Common Data Service e richiedono la sincronizzazione con il database dell'applicazione Human Resources.</span><span class="sxs-lookup"><span data-stu-id="e640a-121">With natural entities, the data is stored in Common Data Service and requires synchronization with the Human Resources application database.</span></span>

> [!NOTE]
> <span data-ttu-id="e640a-122">Per un elenco delle entità Common Data Service naturali per Human Resources, vedi [Entità di Common Data Service](https://docs.microsoft.com/dynamics365/human-resources/hr-developer-entities).</span><span class="sxs-lookup"><span data-stu-id="e640a-122">For a list of the natural Common Data Service entities for Human Resources, see [Common Data Service entities](https://docs.microsoft.com/dynamics365/human-resources/hr-developer-entities).</span></span>

## <a name="setup"></a><span data-ttu-id="e640a-123">Configurazione</span><span class="sxs-lookup"><span data-stu-id="e640a-123">Setup</span></span>

<span data-ttu-id="e640a-124">Segui questi passaggi di configurazione per abilitare le entità virtuali nel tuo ambiente.</span><span class="sxs-lookup"><span data-stu-id="e640a-124">Follow these setup steps to enable virtual entities in your environment.</span></span> 

### <a name="register-the-app-in-microsoft-azure"></a><span data-ttu-id="e640a-125">Registrare l'app in Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="e640a-125">Register the app in Microsoft Azure</span></span>

<span data-ttu-id="e640a-126">Innanzitutto, devi registrare l'app nel portale di Azure di modo che Microsoft Identity Platform possa fornire servizi di autenticazione e autorizzazione per l'app e gli utenti.</span><span class="sxs-lookup"><span data-stu-id="e640a-126">First, you need to register the app in the Azure portal so the Microsoft identity platform can provide authentication and authorization services for the app and users.</span></span> <span data-ttu-id="e640a-127">Per ulteriori informazioni sulla registrazione di app in Azure, vedi [Guida introduttiva: Registrare un'applicazione con Microsoft Identity Platform](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app).</span><span class="sxs-lookup"><span data-stu-id="e640a-127">For more information about registering apps in Azure, see [Quickstart: Register an application with the Microsoft identity platform](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app).</span></span>

1. <span data-ttu-id="e640a-128">Apri il [portale di Microsoft Azure](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="e640a-128">Open the [Microsoft Azure portal](https://portal.azure.com).</span></span>

2. <span data-ttu-id="e640a-129">Nell'elenco di servizi di Azure, seleziona **Registrazioni app**.</span><span class="sxs-lookup"><span data-stu-id="e640a-129">In the Azure services list, select **App registrations**.</span></span>

3. <span data-ttu-id="e640a-130">Seleziona **Nuova registrazione**.</span><span class="sxs-lookup"><span data-stu-id="e640a-130">Select **New registration**.</span></span>

4. <span data-ttu-id="e640a-131">Nel campo **Nome** immetti un nome descrittivo per l'app.</span><span class="sxs-lookup"><span data-stu-id="e640a-131">In the **Name** field, enter a descriptive name for the app.</span></span> <span data-ttu-id="e640a-132">Ad esempio, **Entità virtuali di Dynamics 365 Human Resources**.</span><span class="sxs-lookup"><span data-stu-id="e640a-132">For example, **Dynamics 365 Human Resources Virtual Entities**.</span></span>

5. <span data-ttu-id="e640a-133">Nel campo **URI di reindirizzamento** , immetti l'URL dello spazio dei nomi dell'istanza di Human Resources.</span><span class="sxs-lookup"><span data-stu-id="e640a-133">In the **Redirect URI** field, enter the namespace URL of your instance of Human Resources.</span></span>

6. <span data-ttu-id="e640a-134">Seleziona **Registro**.</span><span class="sxs-lookup"><span data-stu-id="e640a-134">Select **Register**.</span></span>

7. <span data-ttu-id="e640a-135">Al termine della registrazione, il portale di Azure visualizza il riquadro **Panoramica** della registrazione dell'app che include il relativo **ID applicazione (client)**.</span><span class="sxs-lookup"><span data-stu-id="e640a-135">When registration completes, the Azure portal displays the app registration's **Overview** pane, which includes its **Application (client) ID**.</span></span> <span data-ttu-id="e640a-136">Prendi nota adesso dell' **ID applicazione (client)**.</span><span class="sxs-lookup"><span data-stu-id="e640a-136">Take note of the **Application (client) ID** at this time.</span></span> <span data-ttu-id="e640a-137">Immetterai queste informazioni quando [configurerai l'origine dati delle entità virtuali](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-entity-data-source).</span><span class="sxs-lookup"><span data-stu-id="e640a-137">You'll enter this information when you [Configure the virtual entity data source](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-entity-data-source).</span></span>

8. <span data-ttu-id="e640a-138">Nel riquadro di spostamento a sinistra, seleziona **Certificati e segreti**.</span><span class="sxs-lookup"><span data-stu-id="e640a-138">In the left navigation pane, select **Certificates and secrets**.</span></span>

9. <span data-ttu-id="e640a-139">Nella sezione **Segreti client** della pagina, seleziona **Nuovo segreto client**.</span><span class="sxs-lookup"><span data-stu-id="e640a-139">In the **Client secrets** section of the page, select **New client secret**.</span></span>

10. <span data-ttu-id="e640a-140">Fornisci una descrizione, seleziona una durata e seleziona **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="e640a-140">Provide a description, select a duration, and select **Add**.</span></span>

11. <span data-ttu-id="e640a-141">Registra il valore del segreto.</span><span class="sxs-lookup"><span data-stu-id="e640a-141">Record the secret's value.</span></span> <span data-ttu-id="e640a-142">Immetterai queste informazioni quando [configurerai l'origine dati delle entità virtuali](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-entity-data-source).</span><span class="sxs-lookup"><span data-stu-id="e640a-142">You'll enter this information when you [Configure the virtual entity data source](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-entity-data-source).</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="e640a-143">Assicurati di prendere nota adesso del valore del segreto.</span><span class="sxs-lookup"><span data-stu-id="e640a-143">Be sure to take note of the secret's value at this time.</span></span> <span data-ttu-id="e640a-144">Il segreto non viene mai visualizzato dopo la chiusura di questa pagina.</span><span class="sxs-lookup"><span data-stu-id="e640a-144">The secret is never displayed again after you leave this page.</span></span>

### <a name="install-the-dynamics-365-hr-virtual-entity-app"></a><span data-ttu-id="e640a-145">Installare l'app Dynamics 365 HR Virtual Entity</span><span class="sxs-lookup"><span data-stu-id="e640a-145">Install the Dynamics 365 HR Virtual Entity app</span></span>

<span data-ttu-id="e640a-146">Installa l'app Dynamics 365 HR Virtual Entity nell'ambiente Power Apps per distribuire il pacchetto di soluzioni di entità virtuali in Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="e640a-146">Install the Dynamics 365 HR Virtual Entity app in your Power Apps environment to deploy the virtual entity solution package to Common Data Service.</span></span>

1. <span data-ttu-id="e640a-147">Apri l'[interfaccia di amministrazione di Power Platform](https://admin.powerplatform.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="e640a-147">Open the [Power Platform admin center](https://admin.powerplatform.microsoft.com).</span></span>

2. <span data-ttu-id="e640a-148">Nell'elenco **Ambienti** , seleziona l'ambiente Power Apps associato all'istanza di Human Resources.</span><span class="sxs-lookup"><span data-stu-id="e640a-148">In the **Environments** list, select the Power Apps environment associated with your Human Resources instance.</span></span>

3. <span data-ttu-id="e640a-149">Nella sezione **Risorse** della pagina, seleziona **App Dynamics 365**.</span><span class="sxs-lookup"><span data-stu-id="e640a-149">In the **Resources** section of the page, select **Dynamics 365 apps**.</span></span>

4. <span data-ttu-id="e640a-150">Seleziona l'azione **Installa app**.</span><span class="sxs-lookup"><span data-stu-id="e640a-150">Select the **Install app** action.</span></span>

5. <span data-ttu-id="e640a-151">Seleziona **Dynamics 365 HR Virtual Entity** e quindi **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="e640a-151">Select **Dynamics 365 HR Virtual Entity** , and select **Next**.</span></span>

6. <span data-ttu-id="e640a-152">Leggi le condizioni d'uso e accettale.</span><span class="sxs-lookup"><span data-stu-id="e640a-152">Review and mark to agree to the terms of service.</span></span>

7. <span data-ttu-id="e640a-153">Seleziona **Installa**.</span><span class="sxs-lookup"><span data-stu-id="e640a-153">Select **Install**.</span></span>

<span data-ttu-id="e640a-154">L'installazione richiede alcuni minuti.</span><span class="sxs-lookup"><span data-stu-id="e640a-154">The install takes a few minutes.</span></span> <span data-ttu-id="e640a-155">Al termine, continua con i passaggi successivi.</span><span class="sxs-lookup"><span data-stu-id="e640a-155">When it completes, continue to the next steps.</span></span>

![Installare l'app Dynamics 365 HR Virtual Entity dall'interfaccia di amministrazione di Power Platform](./media/hr-admin-integration-virtual-entities-power-platform-install.jpg)

### <a name="configure-the-virtual-entity-data-source"></a><span data-ttu-id="e640a-157">Configurare l'origine dati delle entità virtuali</span><span class="sxs-lookup"><span data-stu-id="e640a-157">Configure the virtual entity data source</span></span> 

<span data-ttu-id="e640a-158">Il passaggio successivo consiste nel configurare l'origine dati delle entità virtuali nell'ambiente Power Apps.</span><span class="sxs-lookup"><span data-stu-id="e640a-158">The next step is to configure the virtual entity data source in the Power Apps environment.</span></span> 

1. <span data-ttu-id="e640a-159">Apri l'[interfaccia di amministrazione di Power Platform](https://admin.powerplatform.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="e640a-159">Open the [Power Platform admin center](https://admin.powerplatform.microsoft.com).</span></span>

2. <span data-ttu-id="e640a-160">Nell'elenco **Ambienti** , seleziona l'ambiente Power Apps associato all'istanza di Human Resources.</span><span class="sxs-lookup"><span data-stu-id="e640a-160">In the **Environments** list, select the Power Apps environment associated with your Human Resources instance.</span></span>

3. <span data-ttu-id="e640a-161">Seleziona l' **URL ambiente** nella sezione **Dettagli** della pagina.</span><span class="sxs-lookup"><span data-stu-id="e640a-161">Select the **Environment URL** in the **Details** section of the page.</span></span>

4. <span data-ttu-id="e640a-162">In **Hub integrità soluzione** , seleziona l'icona **Ricerca avanzata** in alto a destra nella pagina dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="e640a-162">In the **Solution Health Hub** , select the **Advanced Find** icon in the top right of the application page.</span></span>

5. <span data-ttu-id="e640a-163">Nella pagina **Ricerca avanzata** , nell'elenco a discesa **Cerca** , seleziona **Configurazioni dell'origine dati virtuale di Finance and Operations**.</span><span class="sxs-lookup"><span data-stu-id="e640a-163">On the **Advanced Find** page, in the **Look for** dropdown list, select **Finance and Operations Virtual Data Source Configurations**.</span></span>

6. <span data-ttu-id="e640a-164">Seleziona **Risultati**.</span><span class="sxs-lookup"><span data-stu-id="e640a-164">Select **Results**.</span></span>

7. <span data-ttu-id="e640a-165">Seleziona il record **Origine dati Microsoft HR**.</span><span class="sxs-lookup"><span data-stu-id="e640a-165">Select the **Microsoft HR Data Source** record.</span></span>

8. <span data-ttu-id="e640a-166">Immetti le informazioni necessarie per la configurazione dell'origine dati.</span><span class="sxs-lookup"><span data-stu-id="e640a-166">Enter the required information for the data source configuration.</span></span>

   - <span data-ttu-id="e640a-167">**URL di destinazione** : l'URL dello spazio dei nomi di Human Resources.</span><span class="sxs-lookup"><span data-stu-id="e640a-167">**Target URL** : The URL of your Human Resources namespace.</span></span>
   - <span data-ttu-id="e640a-168">**ID tenant** : l'ID tenant di Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="e640a-168">**Tenant ID** : The Azure Active Directory (Azure AD) tenant ID.</span></span>
   - <span data-ttu-id="e640a-169">**ID applicazione AAD** : l'ID applicazione (client) creato per l'applicazione registrata nel portale di Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="e640a-169">**AAD Application ID** : The application (client) ID created for the application registered in the Microsoft Azure portal.</span></span> <span data-ttu-id="e640a-170">Hai ricevuto queste informazioni in precedenza durante il passaggio [Registrare l'app in Microsoft Azure](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure).</span><span class="sxs-lookup"><span data-stu-id="e640a-170">You received this information earlier during the step [Register the app in Microsoft Azure](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure).</span></span>
   - <span data-ttu-id="e640a-171">**ID applicazione AAD** : il segreto client creato per l'applicazione registrata nel portale di Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="e640a-171">**AAD Application Secret** : The client secret created for the application registered in the Microsoft Azure portal.</span></span> <span data-ttu-id="e640a-172">Hai ricevuto queste informazioni in precedenza durante il passaggio [Registrare l'app in Microsoft Azure](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure).</span><span class="sxs-lookup"><span data-stu-id="e640a-172">You received this information earlier during the step [Register the app in Microsoft Azure](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure).</span></span>

9. <span data-ttu-id="e640a-173">Seleziona **Salva e chiudi**.</span><span class="sxs-lookup"><span data-stu-id="e640a-173">Select **Save & Close**.</span></span>

   ![Origine dati di Microsoft HR](./media/hr-admin-integration-virtual-entities-hr-data-source.jpg)

### <a name="grant-app-permissions-in-human-resources"></a><span data-ttu-id="e640a-175">Concedere autorizzazioni dell'app in Human Resources</span><span class="sxs-lookup"><span data-stu-id="e640a-175">Grant app permissions in Human Resources</span></span>

<span data-ttu-id="e640a-176">Concedi autorizzazioni per due applicazioni Azure AD in Human Resources:</span><span class="sxs-lookup"><span data-stu-id="e640a-176">Grant permissions for the two Azure AD applications in Human Resources:</span></span>

- <span data-ttu-id="e640a-177">L'app creata per il tenant nel portale di Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="e640a-177">The app created for your tenant in the Microsoft Azure portal</span></span>
- <span data-ttu-id="e640a-178">L'app Dynamics 365 HR Virtual Entity installata nell'ambiente Power Apps</span><span class="sxs-lookup"><span data-stu-id="e640a-178">The Dynamics 365 HR Virtual Entity app installed in the Power Apps environment</span></span> 

1. <span data-ttu-id="e640a-179">In Human Resources, apri la pagina **Applicazioni di Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="e640a-179">In Human Resources, open the **Azure Active Directory applications** page.</span></span>

2. <span data-ttu-id="e640a-180">Seleziona **Nuovo** per creare un nuovo record di applicazione:</span><span class="sxs-lookup"><span data-stu-id="e640a-180">Select **New** to create a new application record:</span></span>

    - <span data-ttu-id="e640a-181">Nel campo **ID client** , inserisci l'ID client dell'app che hai registrato nel portale di Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="e640a-181">In the **Client ID** field, enter the client ID of the app you registered in the Microsoft Azure portal.</span></span>
    - <span data-ttu-id="e640a-182">Nel campo **Nome** , immetti il nome dell'app che hai registrato nel portale di Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="e640a-182">In the **Name** field, enter the name of the app you registered in the Microsoft Azure portal.</span></span>
    - <span data-ttu-id="e640a-183">Nel campo **ID utente** seleziona l'ID utente di un utente con autorizzazioni di amministratore in Human Resources e nell'ambiente Power Apps.</span><span class="sxs-lookup"><span data-stu-id="e640a-183">In the **User ID** field, select the user ID of a user with admin permissions in Human Resources and the Power Apps environment.</span></span>

3. <span data-ttu-id="e640a-184">Seleziona **Nuovo** per creare un secondo record di applicazione:</span><span class="sxs-lookup"><span data-stu-id="e640a-184">Select **New** to create a second application record:</span></span>

    - <span data-ttu-id="e640a-185">**ID client** : f9be0c49-aa22-4ec6-911a-c5da515226ff</span><span class="sxs-lookup"><span data-stu-id="e640a-185">**Client Id** : f9be0c49-aa22-4ec6-911a-c5da515226ff</span></span>
    - <span data-ttu-id="e640a-186">**Nome** : Dynamics 365 HR Virtual Entity</span><span class="sxs-lookup"><span data-stu-id="e640a-186">**Name** : Dynamics 365 HR Virtual Entity</span></span>
    - <span data-ttu-id="e640a-187">Nel campo **ID utente** seleziona l'ID utente di un utente con autorizzazioni di amministratore in Human Resources e nell'ambiente Power Apps.</span><span class="sxs-lookup"><span data-stu-id="e640a-187">In the **User ID** field, select the user ID of a user with admin permissions in Human Resources and the Power Apps environment.</span></span>

## <a name="generate-virtual-entities"></a><span data-ttu-id="e640a-188">Generare entità virtuali</span><span class="sxs-lookup"><span data-stu-id="e640a-188">Generate virtual entities</span></span>

<span data-ttu-id="e640a-189">Al termine della configurazione, puoi selezionare le entità virtuali che desideri generare e abilitare nell'istanza di Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="e640a-189">When setup completes, you can select the virtual entities you want to generate and enable in your Common Data Service instance.</span></span>

1. <span data-ttu-id="e640a-190">In Human Resources, aprire la pagina **Integrazione di Common Data Service (CDS)**.</span><span class="sxs-lookup"><span data-stu-id="e640a-190">In Human Resources, open the **Common Data Service (CDS) integration** page.</span></span>

2. <span data-ttu-id="e640a-191">Selezionare la scheda **Entità virtuali**.</span><span class="sxs-lookup"><span data-stu-id="e640a-191">Select the **Virtual entities** tab.</span></span>

> [!NOTE]
> <span data-ttu-id="e640a-192">L'interruttore **Abilita entità virtuale** sarà impostato su **Sì** automaticamente quando tutte le impostazioni richieste sono state completate.</span><span class="sxs-lookup"><span data-stu-id="e640a-192">The **Enable the virtual entity** toggle will be set to **Yes** automatically when all required setup has been completed.</span></span> <span data-ttu-id="e640a-193">Se l'interruttore è impostato su **No** , rivedere i passaggi nelle sezioni precedenti di questo documento per assicurarsi che tutte le impostazioni dei prerequisiti siano state completate.</span><span class="sxs-lookup"><span data-stu-id="e640a-193">If the toggle is set to **No** , review the steps in previous sections of this document to ensure all prerequisite setup is completed.</span></span>

3. <span data-ttu-id="e640a-194">Selezionare l'entità o le entità da generare in Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="e640a-194">Select the entity or entities you want to generate in Common Data Service.</span></span>

4. <span data-ttu-id="e640a-195">Selezionare **Genera/Aggiorna**.</span><span class="sxs-lookup"><span data-stu-id="e640a-195">Select **Generate/refresh**.</span></span>

![Integrazione di Common Data Service](./media/hr-admin-integration-common-data-service-integration.jpg)

## <a name="check-entity-generation-status"></a><span data-ttu-id="e640a-197">Controllare lo stato di generazione dell'entità</span><span class="sxs-lookup"><span data-stu-id="e640a-197">Check entity generation status</span></span>

<span data-ttu-id="e640a-198">Le entità virtuali vengono generate in Common Data Service attraverso un processo in background asincrono.</span><span class="sxs-lookup"><span data-stu-id="e640a-198">Virtual entities are generated in Common Data Service through an asynchronous background process.</span></span> <span data-ttu-id="e640a-199">Aggiornamenti sulla visualizzazione del processo nel centro azioni.</span><span class="sxs-lookup"><span data-stu-id="e640a-199">Updates on the process display in the action center.</span></span> <span data-ttu-id="e640a-200">I dettagli sul processo, inclusi i log degli errori, vengono visualizzati nella pagina **Automazioni di processo**.</span><span class="sxs-lookup"><span data-stu-id="e640a-200">Details on the process, including error logs, appear in the **Process automations** page.</span></span>

1. <span data-ttu-id="e640a-201">In Human Resources, aprire la pagina **Automazioni di processo**.</span><span class="sxs-lookup"><span data-stu-id="e640a-201">In Human Resources, open the **Process automations** page.</span></span>

2. <span data-ttu-id="e640a-202">Selezionare la scheda **Processi in background**.</span><span class="sxs-lookup"><span data-stu-id="e640a-202">Select the **Background processes** tab.</span></span>

3. <span data-ttu-id="e640a-203">Selezionare **Processo in background dell'operazione asincrona di polling dell'entità virtuale**.</span><span class="sxs-lookup"><span data-stu-id="e640a-203">Select **Virtual entity poll async operation background process**.</span></span>

4. <span data-ttu-id="e640a-204">Selezionare **Visualizza risultati più recenti**.</span><span class="sxs-lookup"><span data-stu-id="e640a-204">Select **View most recent results**.</span></span>

<span data-ttu-id="e640a-205">Il riquadro scorrevole mostra i risultati di esecuzione più recenti per il processo.</span><span class="sxs-lookup"><span data-stu-id="e640a-205">The slideout pane displays the most recent execution results for the process.</span></span> <span data-ttu-id="e640a-206">È possibile visualizzare il registro del processo, inclusi eventuali errori restituiti da Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="e640a-206">You can view the log for the process, including any errors returned from Common Data Service.</span></span>

## <a name="see-also"></a><span data-ttu-id="e640a-207">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e640a-207">See also</span></span>

[<span data-ttu-id="e640a-208">Che cos'è Common Data Service?</span><span class="sxs-lookup"><span data-stu-id="e640a-208">What is Common Data Service?</span></span>](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro)<br>
[<span data-ttu-id="e640a-209">Panoramica delle entità</span><span class="sxs-lookup"><span data-stu-id="e640a-209">Entity overview</span></span>](https://docs.microsoft.com/powerapps/maker/common-data-service/entity-overview)<br>
[<span data-ttu-id="e640a-210">Panoramica delle relazioni tra entità</span><span class="sxs-lookup"><span data-stu-id="e640a-210">Entity relationships overview</span></span>](https://docs.microsoft.com/powerapps/maker/common-data-service/relationships-overview)<br>
[<span data-ttu-id="e640a-211">Creare e modificare entità virtuali che contengono dati di un'origine dati esterna</span><span class="sxs-lookup"><span data-stu-id="e640a-211">Create and edit virtual entities that contain data from an external data source</span></span>](https://docs.microsoft.com/powerapps/maker/common-data-service/create-edit-virtual-entities)<br>
[<span data-ttu-id="e640a-212">Cosa sono i portali di Power Apps?</span><span class="sxs-lookup"><span data-stu-id="e640a-212">What is Power Apps portals?</span></span>](https://docs.microsoft.com/powerapps/maker/portals/overview)<br>
[<span data-ttu-id="e640a-213">Panoramica sulla creazione di app in Power Apps</span><span class="sxs-lookup"><span data-stu-id="e640a-213">Overview of creating apps in Power Apps</span></span>](https://docs.microsoft.com/powerapps/maker/)
