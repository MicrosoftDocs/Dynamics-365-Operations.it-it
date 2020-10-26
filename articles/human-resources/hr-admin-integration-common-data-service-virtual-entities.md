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
ms.openlocfilehash: 0848b7556100fba38fcab0aa2a1a109e2e055fc9
ms.sourcegitcommit: b89baab13e530b5b1f079231619c628309a4742d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/05/2020
ms.locfileid: "3959577"
---
# <a name="configure-common-data-service-virtual-entities"></a><span data-ttu-id="13c66-104">Configurare le entità virtuali di Common Data Service</span><span class="sxs-lookup"><span data-stu-id="13c66-104">Configure Common Data Service virtual entities</span></span>

[!include [banner](includes/preview-feature.md)]

<span data-ttu-id="13c66-105">Dynamics 365 Human Resources è un'origine dati virtuale in Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="13c66-105">Dynamics 365 Human Resources is a virtual data source in Common Data Service.</span></span> <span data-ttu-id="13c66-106">Fornisce operazioni complete di creazione, lettura, aggiornamento ed eliminazione (CRUD) di Common Data Service e Microsoft Power Platform.</span><span class="sxs-lookup"><span data-stu-id="13c66-106">It provides full create, read, update, and delete (CRUD) operations from Common Data Service and Microsoft Power Platform.</span></span> <span data-ttu-id="13c66-107">I dati delle entità virtuali non sono archiviati in Common Data Service, ma nel database dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="13c66-107">The data for virtual entities isn't stored in Common Data Service, but in the application database.</span></span> 

<span data-ttu-id="13c66-108">Per abilitare le operazioni CRUD nelle entità di Human Resources da Common Data Service, devi rendere le entità disponibili come entità virtuali in Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="13c66-108">To enable CRUD operations on Human Resources entities from Common Data Service, you must make the entities available as virtual entities in Common Data Service.</span></span> <span data-ttu-id="13c66-109">Ciò consente di eseguire operazioni CRUD di Common Data Service e Microsoft Power Platform sui dati presenti in Human Resources.</span><span class="sxs-lookup"><span data-stu-id="13c66-109">This lets you perform CRUD operations from Common Data Service and Microsoft Power Platform on data that's in Human Resources.</span></span> <span data-ttu-id="13c66-110">Le operazioni supportano anche le convalide complete della logica aziendale di Human Resources per garantire l'integrità dei dati durante la scrittura degli stessi nelle entità.</span><span class="sxs-lookup"><span data-stu-id="13c66-110">The operations also support the full business logic validations of Human Resources to ensure data integrity when writing data to the entities.</span></span>

## <a name="available-virtual-entities-for-human-resources"></a><span data-ttu-id="13c66-111">Entità virtuali disponibili per Human Resources</span><span class="sxs-lookup"><span data-stu-id="13c66-111">Available virtual entities for Human Resources</span></span>

<span data-ttu-id="13c66-112">Tutte le entità Open Data Protocol (OData) di Human Resources sono disponibili come entità virtuali in Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="13c66-112">All Open Data Protocol (OData) entities in Human Resources are available as virtual entities in Common Data Service.</span></span> <span data-ttu-id="13c66-113">Sono inoltre disponibili in Power Platform.</span><span class="sxs-lookup"><span data-stu-id="13c66-113">They're also available in Power Platform.</span></span> <span data-ttu-id="13c66-114">Ora puoi creare app ed esperienze con dati direttamente da Human Resources mediante funzionalità CRUD complete, senza copiare o sincronizzare i dati in Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="13c66-114">You can now build apps and experiences with data directly from Human Resources with full CRUD capability, without copying or synchronizing data to Common Data Service.</span></span> <span data-ttu-id="13c66-115">Puoi usare i portali Power Apps per creare siti Web rivolti all'esterno che consentono scenari di collaborazione per processi aziendali in Human Resources.</span><span class="sxs-lookup"><span data-stu-id="13c66-115">You can use Power Apps portals to build external-facing websites that enable collaboration scenarios for business processes in Human Resources.</span></span>

<span data-ttu-id="13c66-116">Puoi visualizzare l'elenco delle entità virtuali abilitate nell'ambiente e iniziare a lavorare con le entità in[Power Apps](https://make.powerapps.com), nella soluzione **Dynamics 365 HR Virtual Entities**.</span><span class="sxs-lookup"><span data-stu-id="13c66-116">You can view the list of virtual entities enabled in the environment, and begin working with the entities in [Power Apps](https://make.powerapps.com), in the **Dynamics 365 HR Virtual Entities** solution.</span></span>

![Dynamics 365 HR Virtual Entities in Power Apps](./media/hr-admin-integration-virtual-entities-power-apps.jpg)

## <a name="virtual-entities-versus-natural-entities"></a><span data-ttu-id="13c66-118">Entità virtuali e entità naturali</span><span class="sxs-lookup"><span data-stu-id="13c66-118">Virtual entities versus natural entities</span></span>

<span data-ttu-id="13c66-119">Le entità virtuali di Human Resources non sono uguali alle entità Common Data Service naturali create per Human Resources.</span><span class="sxs-lookup"><span data-stu-id="13c66-119">Virtual entities for Human Resources aren't the same as the natural Common Data Service entities created for Human Resources.</span></span> <span data-ttu-id="13c66-120">Le entità naturali per Human Resources vengono generate separatamente e gestite nella soluzione Gestione connessione ibrida comune in Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="13c66-120">The natural entities for Human Resources are generated separately and maintained in the HCM Common solution in Common Data Service.</span></span> <span data-ttu-id="13c66-121">Con le entità naturali, i dati vengono archiviati in Common Data Service e richiedono la sincronizzazione con il database dell'applicazione Human Resources.</span><span class="sxs-lookup"><span data-stu-id="13c66-121">With natural entities, the data is stored in Common Data Service and requires synchronization with the Human Resources application database.</span></span>

> [!NOTE]
> <span data-ttu-id="13c66-122">Per un elenco delle entità Common Data Service naturali per Human Resources, vedi [Entità di Common Data Service](https://docs.microsoft.com/dynamics365/human-resources/hr-developer-entities).</span><span class="sxs-lookup"><span data-stu-id="13c66-122">For a list of the natural Common Data Service entities for Human Resources, see [Common Data Service entities](https://docs.microsoft.com/dynamics365/human-resources/hr-developer-entities).</span></span>

## <a name="setup"></a><span data-ttu-id="13c66-123">Configurazione</span><span class="sxs-lookup"><span data-stu-id="13c66-123">Setup</span></span>

<span data-ttu-id="13c66-124">Segui questi passaggi di configurazione per abilitare le entità virtuali nel tuo ambiente.</span><span class="sxs-lookup"><span data-stu-id="13c66-124">Follow these setup steps to enable virtual entities in your environment.</span></span> 

### <a name="register-the-app-in-microsoft-azure"></a><span data-ttu-id="13c66-125">Registrare l'app in Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="13c66-125">Register the app in Microsoft Azure</span></span>

<span data-ttu-id="13c66-126">Innanzitutto, devi registrare l'app nel portale di Azure di modo che Microsoft Identity Platform possa fornire servizi di autenticazione e autorizzazione per l'app e gli utenti.</span><span class="sxs-lookup"><span data-stu-id="13c66-126">First, you need to register the app in the Azure portal so the Microsoft identity platform can provide authentication and authorization services for the app and users.</span></span> <span data-ttu-id="13c66-127">Per ulteriori informazioni sulla registrazione di app in Azure, vedi [Guida introduttiva: Registrare un'applicazione con Microsoft Identity Platform](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app).</span><span class="sxs-lookup"><span data-stu-id="13c66-127">For more information about registering apps in Azure, see [Quickstart: Register an application with the Microsoft identity platform](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app).</span></span>

1. <span data-ttu-id="13c66-128">Apri il [portale di Microsoft Azure](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="13c66-128">Open the [Microsoft Azure portal](https://portal.azure.com).</span></span>

2. <span data-ttu-id="13c66-129">Nell'elenco di servizi di Azure, seleziona **Registrazioni app**.</span><span class="sxs-lookup"><span data-stu-id="13c66-129">In the Azure services list, select **App registrations**.</span></span>

3. <span data-ttu-id="13c66-130">Seleziona **Nuova registrazione**.</span><span class="sxs-lookup"><span data-stu-id="13c66-130">Select **New registration**.</span></span>

4. <span data-ttu-id="13c66-131">Nel campo **Nome** immetti un nome descrittivo per l'app.</span><span class="sxs-lookup"><span data-stu-id="13c66-131">In the **Name** field, enter a descriptive name for the app.</span></span> <span data-ttu-id="13c66-132">Ad esempio, **Entità virtuali di Dynamics 365 Human Resources**.</span><span class="sxs-lookup"><span data-stu-id="13c66-132">For example, **Dynamics 365 Human Resources Virtual Entities**.</span></span>

5. <span data-ttu-id="13c66-133">Nel campo **URI di reindirizzamento**, immetti l'URL dello spazio dei nomi dell'istanza di Human Resources.</span><span class="sxs-lookup"><span data-stu-id="13c66-133">In the **Redirect URI** field, enter the namespace URL of your instance of Human Resources.</span></span>

6. <span data-ttu-id="13c66-134">Seleziona **Registro**.</span><span class="sxs-lookup"><span data-stu-id="13c66-134">Select **Register**.</span></span>

7. <span data-ttu-id="13c66-135">Al termine della registrazione, il portale di Azure visualizza il riquadro **Panoramica** della registrazione dell'app che include il relativo **ID applicazione (client)**.</span><span class="sxs-lookup"><span data-stu-id="13c66-135">When registration completes, the Azure portal displays the app registration's **Overview** pane, which includes its **Application (client) ID**.</span></span> <span data-ttu-id="13c66-136">Prendi nota adesso dell'**ID applicazione (client)**.</span><span class="sxs-lookup"><span data-stu-id="13c66-136">Take note of the **Application (client) ID** at this time.</span></span> <span data-ttu-id="13c66-137">Immetterai queste informazioni quando [configurerai l'origine dati delle entità virtuali](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-entity-data-source).</span><span class="sxs-lookup"><span data-stu-id="13c66-137">You'll enter this information when you [Configure the virtual entity data source](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-entity-data-source).</span></span>

8. <span data-ttu-id="13c66-138">Nel riquadro di spostamento a sinistra, seleziona **Certificati e segreti**.</span><span class="sxs-lookup"><span data-stu-id="13c66-138">In the left navigation pane, select **Certificates and secrets**.</span></span>

9. <span data-ttu-id="13c66-139">Nella sezione **Segreti client** della pagina, seleziona **Nuovo segreto client**.</span><span class="sxs-lookup"><span data-stu-id="13c66-139">In the **Client secrets** section of the page, select **New client secret**.</span></span>

10. <span data-ttu-id="13c66-140">Fornisci una descrizione, seleziona una durata e seleziona **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="13c66-140">Provide a description, select a duration, and select **Add**.</span></span>

11. <span data-ttu-id="13c66-141">Registra il valore del segreto.</span><span class="sxs-lookup"><span data-stu-id="13c66-141">Record the secret's value.</span></span> <span data-ttu-id="13c66-142">Immetterai queste informazioni quando [configurerai l'origine dati delle entità virtuali](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-entity-data-source).</span><span class="sxs-lookup"><span data-stu-id="13c66-142">You'll enter this information when you [Configure the virtual entity data source](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-entity-data-source).</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="13c66-143">Assicurati di prendere nota adesso del valore del segreto.</span><span class="sxs-lookup"><span data-stu-id="13c66-143">Be sure to take note of the secret's value at this time.</span></span> <span data-ttu-id="13c66-144">Il segreto non viene mai visualizzato dopo la chiusura di questa pagina.</span><span class="sxs-lookup"><span data-stu-id="13c66-144">The secret is never displayed again after you leave this page.</span></span>

### <a name="install-the-dynamics-365-hr-virtual-entity-app"></a><span data-ttu-id="13c66-145">Installare l'app Dynamics 365 HR Virtual Entity</span><span class="sxs-lookup"><span data-stu-id="13c66-145">Install the Dynamics 365 HR Virtual Entity app</span></span>

<span data-ttu-id="13c66-146">Installa l'app Dynamics 365 HR Virtual Entity nell'ambiente Power Apps per distribuire il pacchetto di soluzioni di entità virtuali in Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="13c66-146">Install the Dynamics 365 HR Virtual Entity app in your Power Apps environment to deploy the virtual entity solution package to Common Data Service.</span></span>

1. <span data-ttu-id="13c66-147">Apri l'[interfaccia di amministrazione di Power Platform](https://admin.powerplatform.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="13c66-147">Open the [Power Platform admin center](https://admin.powerplatform.microsoft.com).</span></span>

2. <span data-ttu-id="13c66-148">Nell'elenco **Ambienti**, seleziona l'ambiente Power Apps associato all'istanza di Human Resources.</span><span class="sxs-lookup"><span data-stu-id="13c66-148">In the **Environments** list, select the Power Apps environment associated with your Human Resources instance.</span></span>

3. <span data-ttu-id="13c66-149">Nella sezione **Risorse** della pagina, seleziona **App Dynamics 365**.</span><span class="sxs-lookup"><span data-stu-id="13c66-149">In the **Resources** section of the page, select **Dynamics 365 apps**.</span></span>

4. <span data-ttu-id="13c66-150">Seleziona l'azione **Installa app**.</span><span class="sxs-lookup"><span data-stu-id="13c66-150">Select the **Install app** action.</span></span>

5. <span data-ttu-id="13c66-151">Seleziona **Dynamics 365 HR Virtual Entity** e quindi **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="13c66-151">Select **Dynamics 365 HR Virtual Entity**, and select **Next**.</span></span>

6. <span data-ttu-id="13c66-152">Leggi le condizioni d'uso e accettale.</span><span class="sxs-lookup"><span data-stu-id="13c66-152">Review and mark to agree to the terms of service.</span></span>

7. <span data-ttu-id="13c66-153">Seleziona **Installa**.</span><span class="sxs-lookup"><span data-stu-id="13c66-153">Select **Install**.</span></span>

<span data-ttu-id="13c66-154">L'installazione richiede alcuni minuti.</span><span class="sxs-lookup"><span data-stu-id="13c66-154">The install takes a few minutes.</span></span> <span data-ttu-id="13c66-155">Al termine, continua con i passaggi successivi.</span><span class="sxs-lookup"><span data-stu-id="13c66-155">When it completes, continue to the next steps.</span></span>

![Installare l'app Dynamics 365 HR Virtual Entity dall'interfaccia di amministrazione di Power Platform](./media/hr-admin-integration-virtual-entities-power-platform-install.jpg)

### <a name="configure-the-virtual-entity-data-source"></a><span data-ttu-id="13c66-157">Configurare l'origine dati delle entità virtuali</span><span class="sxs-lookup"><span data-stu-id="13c66-157">Configure the virtual entity data source</span></span> 

<span data-ttu-id="13c66-158">Il passaggio successivo consiste nel configurare l'origine dati delle entità virtuali nell'ambiente Power Apps.</span><span class="sxs-lookup"><span data-stu-id="13c66-158">The next step is to configure the virtual entity data source in the Power Apps environment.</span></span> 

1. <span data-ttu-id="13c66-159">Apri l'[interfaccia di amministrazione di Power Platform](https://admin.powerplatform.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="13c66-159">Open the [Power Platform admin center](https://admin.powerplatform.microsoft.com).</span></span>

2. <span data-ttu-id="13c66-160">Nell'elenco **Ambienti**, seleziona l'ambiente Power Apps associato all'istanza di Human Resources.</span><span class="sxs-lookup"><span data-stu-id="13c66-160">In the **Environments** list, select the Power Apps environment associated with your Human Resources instance.</span></span>

3. <span data-ttu-id="13c66-161">Seleziona l'**URL ambiente** nella sezione **Dettagli** della pagina.</span><span class="sxs-lookup"><span data-stu-id="13c66-161">Select the **Environment URL** in the **Details** section of the page.</span></span>

4. <span data-ttu-id="13c66-162">In **Hub integrità soluzione**, seleziona l'icona **Ricerca avanzata** in alto a destra nella pagina dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="13c66-162">In the **Solution Health Hub**, select the **Advanced Find** icon in the top right of the application page.</span></span>

5. <span data-ttu-id="13c66-163">Nella pagina **Ricerca avanzata**, nell'elenco a discesa **Cerca**, seleziona **Configurazioni dell'origine dati virtuale di Finance and Operations**.</span><span class="sxs-lookup"><span data-stu-id="13c66-163">On the **Advanced Find** page, in the **Look for** dropdown list, select **Finance and Operations Virtual Data Source Configurations**.</span></span>

6. <span data-ttu-id="13c66-164">Seleziona **Risultati**.</span><span class="sxs-lookup"><span data-stu-id="13c66-164">Select **Results**.</span></span>

7. <span data-ttu-id="13c66-165">Seleziona il record **Origine dati Microsoft HR**.</span><span class="sxs-lookup"><span data-stu-id="13c66-165">Select the **Microsoft HR Data Source** record.</span></span>

8. <span data-ttu-id="13c66-166">Immetti le informazioni necessarie per la configurazione dell'origine dati.</span><span class="sxs-lookup"><span data-stu-id="13c66-166">Enter the required information for the data source configuration.</span></span>

   - <span data-ttu-id="13c66-167">**URL di destinazione**: l'URL dello spazio dei nomi di Human Resources.</span><span class="sxs-lookup"><span data-stu-id="13c66-167">**Target URL**: The URL of your Human Resources namespace.</span></span>
   - <span data-ttu-id="13c66-168">**ID tenant**: l'ID tenant di Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="13c66-168">**Tenant ID**: The Azure Active Directory (Azure AD) tenant ID.</span></span>
   - <span data-ttu-id="13c66-169">**ID applicazione AAD**: l'ID applicazione (client) creato per l'applicazione registrata nel portale di Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="13c66-169">**AAD Application ID**: The application (client) ID created for the application registered in the Microsoft Azure portal.</span></span> <span data-ttu-id="13c66-170">Hai ricevuto queste informazioni in precedenza durante il passaggio [Registrare l'app in Microsoft Azure](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure).</span><span class="sxs-lookup"><span data-stu-id="13c66-170">You received this information earlier during the step [Register the app in Microsoft Azure](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure).</span></span>
   - <span data-ttu-id="13c66-171">**ID applicazione AAD**: il segreto client creato per l'applicazione registrata nel portale di Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="13c66-171">**AAD Application Secret**: The client secret created for the application registered in the Microsoft Azure portal.</span></span> <span data-ttu-id="13c66-172">Hai ricevuto queste informazioni in precedenza durante il passaggio [Registrare l'app in Microsoft Azure](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure).</span><span class="sxs-lookup"><span data-stu-id="13c66-172">You received this information earlier during the step [Register the app in Microsoft Azure](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure).</span></span>

9. <span data-ttu-id="13c66-173">Seleziona **Salva e chiudi**.</span><span class="sxs-lookup"><span data-stu-id="13c66-173">Select **Save & Close**.</span></span>

   ![Origine dati di Microsoft HR](./media/hr-admin-integration-virtual-entities-hr-data-source.jpg)

### <a name="grant-app-permissions-in-human-resources"></a><span data-ttu-id="13c66-175">Concedere autorizzazioni dell'app in Human Resources</span><span class="sxs-lookup"><span data-stu-id="13c66-175">Grant app permissions in Human Resources</span></span>

<span data-ttu-id="13c66-176">Concedi autorizzazioni per due applicazioni Azure AD in Human Resources:</span><span class="sxs-lookup"><span data-stu-id="13c66-176">Grant permissions for the two Azure AD applications in Human Resources:</span></span>

- <span data-ttu-id="13c66-177">L'app creata per il tenant nel portale di Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="13c66-177">The app created for your tenant in the Microsoft Azure portal</span></span>
- <span data-ttu-id="13c66-178">L'app Dynamics 365 HR Virtual Entity installata nell'ambiente Power Apps</span><span class="sxs-lookup"><span data-stu-id="13c66-178">The Dynamics 365 HR Virtual Entity app installed in the Power Apps environment</span></span> 

1. <span data-ttu-id="13c66-179">In Human Resources, apri la pagina **Applicazioni di Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="13c66-179">In Human Resources, open the **Azure Active Directory applications** page.</span></span>

2. <span data-ttu-id="13c66-180">Seleziona **Nuovo** per creare un nuovo record di applicazione:</span><span class="sxs-lookup"><span data-stu-id="13c66-180">Select **New** to create a new application record:</span></span>

    - <span data-ttu-id="13c66-181">Nel campo **ID client**, inserisci l'ID client dell'app che hai registrato nel portale di Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="13c66-181">In the **Client ID** field, enter the client ID of the app you registered in the Microsoft Azure portal.</span></span>
    - <span data-ttu-id="13c66-182">Nel campo **Nome**, immetti il nome dell'app che hai registrato nel portale di Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="13c66-182">In the **Name** field, enter the name of the app you registered in the Microsoft Azure portal.</span></span>
    - <span data-ttu-id="13c66-183">Nel campo **ID utente** seleziona l'ID utente di un utente con autorizzazioni di amministratore in Human Resources e nell'ambiente Power Apps.</span><span class="sxs-lookup"><span data-stu-id="13c66-183">In the **User ID** field, select the user ID of a user with admin permissions in Human Resources and the Power Apps environment.</span></span>

3. <span data-ttu-id="13c66-184">Seleziona **Nuovo** per creare un secondo record di applicazione:</span><span class="sxs-lookup"><span data-stu-id="13c66-184">Select **New** to create a second application record:</span></span>

    - <span data-ttu-id="13c66-185">**ID client**: f9be0c49-aa22-4ec6-911a-c5da515226ff</span><span class="sxs-lookup"><span data-stu-id="13c66-185">**Client Id**: f9be0c49-aa22-4ec6-911a-c5da515226ff</span></span>
    - <span data-ttu-id="13c66-186">**Nome**: Dynamics 365 HR Virtual Entity</span><span class="sxs-lookup"><span data-stu-id="13c66-186">**Name**: Dynamics 365 HR Virtual Entity</span></span>
    - <span data-ttu-id="13c66-187">Nel campo **ID utente** seleziona l'ID utente di un utente con autorizzazioni di amministratore in Human Resources e nell'ambiente Power Apps.</span><span class="sxs-lookup"><span data-stu-id="13c66-187">In the **User ID** field, select the user ID of a user with admin permissions in Human Resources and the Power Apps environment.</span></span>

## <a name="generate-virtual-entities"></a><span data-ttu-id="13c66-188">Generare entità virtuali</span><span class="sxs-lookup"><span data-stu-id="13c66-188">Generate virtual entities</span></span>

<span data-ttu-id="13c66-189">Al termine della configurazione, puoi selezionare le entità virtuali che desideri generare e abilitare nell'istanza di Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="13c66-189">When setup completes, you can select the virtual entities you want to generate and enable in your Common Data Service instance.</span></span>

1. <span data-ttu-id="13c66-190">Apri l'[interfaccia di amministrazione di Power Platform](https://admin.powerplatform.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="13c66-190">Open the [Power Platform admin center](https://admin.powerplatform.microsoft.com).</span></span>

2. <span data-ttu-id="13c66-191">Nell'elenco **Ambienti**, seleziona l'ambiente Power Apps associato all'istanza di Human Resources.</span><span class="sxs-lookup"><span data-stu-id="13c66-191">In the **Environments** list, select the Power Apps environment associated with your Human Resources instance.</span></span>

3. <span data-ttu-id="13c66-192">Seleziona l'**URL ambiente** nella sezione **Dettagli** della pagina.</span><span class="sxs-lookup"><span data-stu-id="13c66-192">Select the **Environment URL** in the **Details** section of the page.</span></span>

4. <span data-ttu-id="13c66-193">In **Hub integrità soluzione**, seleziona l'icona **Ricerca avanzata** in alto a destra nella pagina.</span><span class="sxs-lookup"><span data-stu-id="13c66-193">In the **Solution Health Hub**, select the **Advanced Find** icon in the top right of the page.</span></span>

5. <span data-ttu-id="13c66-194">Nella pagina **Ricerca avanzata**, nell'elenco a discesa **Cerca**, seleziona **Entità HR disponibili**.</span><span class="sxs-lookup"><span data-stu-id="13c66-194">On the **Advanced Find** page, in the **Look for** dropdown list, select **Available HR Entities**.</span></span>

6. <span data-ttu-id="13c66-195">Utilizza le opzioni di filtro per trovare l'entità o le entità che desideri abilitare.</span><span class="sxs-lookup"><span data-stu-id="13c66-195">Use the filter options to find the entity or entities you want to enable.</span></span>

7. <span data-ttu-id="13c66-196">Seleziona un'entità nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="13c66-196">Select an entity from the list.</span></span>

8. <span data-ttu-id="13c66-197">Nella pagina delle entità, imposta la proprietà **Generato** su **Sì** per l'entità.</span><span class="sxs-lookup"><span data-stu-id="13c66-197">On the entity page, change the **Has Been Generated** property to **Yes** for the entity.</span></span>

9. <span data-ttu-id="13c66-198">Salva e chiudi la pagina delle entità.</span><span class="sxs-lookup"><span data-stu-id="13c66-198">Save and close the entity page.</span></span>

> [!NOTE]
> <span data-ttu-id="13c66-199">Puoi generare più entità virtuali contemporaneamente utilizzando la pagina **Cambia più record**.</span><span class="sxs-lookup"><span data-stu-id="13c66-199">You can generate multiple virtual entities at once by using the **Change Multiple Records** page.</span></span> <span data-ttu-id="13c66-200">Seleziona più record nella pagina e seleziona **Modifica** nella barra multifunzione.</span><span class="sxs-lookup"><span data-stu-id="13c66-200">Select multiple records on the page, and select **Edit** on the ribbon.</span></span> <span data-ttu-id="13c66-201">Puoi quindi modificare la proprietà **Generato** per tutti i record selezionati.</span><span class="sxs-lookup"><span data-stu-id="13c66-201">You can then change the **Has Been Generated** property for all selected records.</span></span>

![Entità HR disponibili](./media/hr-admin-integration-virtual-entities-available.jpg)

> [!NOTE]
> <span data-ttu-id="13c66-203">Per semplificare il processo di generazione di entità virtuali nelle versioni future, il processo verrà eseguito in una pagina di Human Resources.</span><span class="sxs-lookup"><span data-stu-id="13c66-203">To streamline the process of generating virtual entities in future releases, the process will occur in a page in Human Resources.</span></span>

## <a name="see-also"></a><span data-ttu-id="13c66-204">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="13c66-204">See also</span></span>

[<span data-ttu-id="13c66-205">Che cos'è Common Data Service?</span><span class="sxs-lookup"><span data-stu-id="13c66-205">What is Common Data Service?</span></span>](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro)<br>
[<span data-ttu-id="13c66-206">Panoramica delle entità</span><span class="sxs-lookup"><span data-stu-id="13c66-206">Entity overview</span></span>](https://docs.microsoft.com/powerapps/maker/common-data-service/entity-overview)<br>
[<span data-ttu-id="13c66-207">Panoramica delle relazioni tra entità</span><span class="sxs-lookup"><span data-stu-id="13c66-207">Entity relationships overview</span></span>](https://docs.microsoft.com/powerapps/maker/common-data-service/relationships-overview)<br>
[<span data-ttu-id="13c66-208">Creare e modificare entità virtuali che contengono dati di un'origine dati esterna</span><span class="sxs-lookup"><span data-stu-id="13c66-208">Create and edit virtual entities that contain data from an external data source</span></span>](https://docs.microsoft.com/powerapps/maker/common-data-service/create-edit-virtual-entities)<br>
[<span data-ttu-id="13c66-209">Cosa sono i portali di Power Apps?</span><span class="sxs-lookup"><span data-stu-id="13c66-209">What is Power Apps portals?</span></span>](https://docs.microsoft.com/powerapps/maker/portals/overview)<br>
[<span data-ttu-id="13c66-210">Panoramica sulla creazione di app in Power Apps</span><span class="sxs-lookup"><span data-stu-id="13c66-210">Overview of creating apps in Power Apps</span></span>](https://docs.microsoft.com/powerapps/maker/)
