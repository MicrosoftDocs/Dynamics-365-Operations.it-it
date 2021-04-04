---
title: Configurare le tabelle virtuali di Dataverse
description: In questo argomento viene descritto come configurare le tabelle virtuali per Dynamics 365 Human Resources. Genera e aggiorna tabelle virtuali esistenti e analizza tabelle generate e disponibili.
author: andreabichsel
manager: tfehr
ms.date: 01/25/2021
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
ms.openlocfilehash: d8780be777c9a204fcb95950f5679a5711aee298
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/17/2021
ms.locfileid: "5465824"
---
# <a name="configure-dataverse-virtual-tables"></a><span data-ttu-id="a9303-104">Configurare le tabelle virtuali di Dataverse</span><span class="sxs-lookup"><span data-stu-id="a9303-104">Configure Dataverse virtual tables</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="a9303-105">Dynamics 365 Human Resources è un'origine dati virtuale in Microsoft Dataverse.</span><span class="sxs-lookup"><span data-stu-id="a9303-105">Dynamics 365 Human Resources is a virtual data source in Microsoft Dataverse.</span></span> <span data-ttu-id="a9303-106">Fornisce operazioni complete di creazione, lettura, aggiornamento ed eliminazione (CRUD) di Dataverse e Microsoft Power Platform.</span><span class="sxs-lookup"><span data-stu-id="a9303-106">It provides full create, read, update, and delete (CRUD) operations from Dataverse and Microsoft Power Platform.</span></span> <span data-ttu-id="a9303-107">I dati delle tabelle virtuali non sono archiviati in Dataverse, ma nel database dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="a9303-107">The data for virtual tables isn't stored in Dataverse, but in the application database.</span></span>

<span data-ttu-id="a9303-108">Per abilitare le operazioni CRUD nelle entità di Human Resources da Dataverse, devi rendere le entità disponibili come tabelle virtuali in Dataverse.</span><span class="sxs-lookup"><span data-stu-id="a9303-108">To enable CRUD operations on Human Resources entities from Dataverse, you must make the entities available as virtual tables in Dataverse.</span></span> <span data-ttu-id="a9303-109">Ciò consente di eseguire operazioni CRUD di Dataverse e Microsoft Power Platform sui dati presenti in Human Resources.</span><span class="sxs-lookup"><span data-stu-id="a9303-109">This lets you perform CRUD operations from Dataverse and Microsoft Power Platform on data that's in Human Resources.</span></span> <span data-ttu-id="a9303-110">Le operazioni supportano anche le convalide complete della logica aziendale di Human Resources per garantire l'integrità dei dati durante la scrittura degli stessi nelle entità.</span><span class="sxs-lookup"><span data-stu-id="a9303-110">The operations also support the full business logic validations of Human Resources to ensure data integrity when writing data to the entities.</span></span>

> [!NOTE]
> <span data-ttu-id="a9303-111">Le entità di Human Resources corrispondono alle tabelle Dataverse.</span><span class="sxs-lookup"><span data-stu-id="a9303-111">Human Resources entities correspond to Dataverse tables.</span></span> <span data-ttu-id="a9303-112">Per ulteriori informazioni su Dataverse (in precedenza Common Data Service) e aggiornamenti terminologici, vedi [ Cosa è Microsoft Dataverse ?](https://docs.microsoft.com/powerapps/maker/data-platform/data-platform-intro)</span><span class="sxs-lookup"><span data-stu-id="a9303-112">For more information about Dataverse (formerly Common Data Service) and terminology updates, see [What is Microsoft Dataverse?](https://docs.microsoft.com/powerapps/maker/data-platform/data-platform-intro)</span></span>

## <a name="available-virtual-tables-for-human-resources"></a><span data-ttu-id="a9303-113">Tabelle virtuali disponibili per Human Resources</span><span class="sxs-lookup"><span data-stu-id="a9303-113">Available virtual tables for Human Resources</span></span>

<span data-ttu-id="a9303-114">Tutte le entità Open Data Protocol (OData) di Human Resources sono disponibili come tabelle virtuali in Dataverse.</span><span class="sxs-lookup"><span data-stu-id="a9303-114">All Open Data Protocol (OData) entities in Human Resources are available as virtual tables in Dataverse.</span></span> <span data-ttu-id="a9303-115">Sono inoltre disponibili in Power Platform.</span><span class="sxs-lookup"><span data-stu-id="a9303-115">They're also available in Power Platform.</span></span> <span data-ttu-id="a9303-116">Ora puoi creare app ed esperienze con dati direttamente da Human Resources mediante funzionalità CRUD complete, senza copiare o sincronizzare i dati in Dataverse.</span><span class="sxs-lookup"><span data-stu-id="a9303-116">You can now build apps and experiences with data directly from Human Resources with full CRUD capability, without copying or synchronizing data to Dataverse.</span></span> <span data-ttu-id="a9303-117">Puoi usare i portali Power Apps per creare siti Web rivolti all'esterno che consentono scenari di collaborazione per processi aziendali in Human Resources.</span><span class="sxs-lookup"><span data-stu-id="a9303-117">You can use Power Apps portals to build external-facing websites that enable collaboration scenarios for business processes in Human Resources.</span></span>

<span data-ttu-id="a9303-118">Puoi visualizzare l'elenco delle tabelle virtuali abilitate nell'ambiente e iniziare a lavorare con le tabelle in [Power Apps](https://make.powerapps.com), nella soluzione **Dynamics 365 HR Virtual Tables**.</span><span class="sxs-lookup"><span data-stu-id="a9303-118">You can view the list of virtual tables enabled in the environment, and begin working with the tables in [Power Apps](https://make.powerapps.com), in the **Dynamics 365 HR Virtual Tables** solution.</span></span>

![Tabelle virtuali di Dynamics 365 HR in Power Apps](./media/hr-admin-integration-virtual-entities-power-apps.jpg)

## <a name="virtual-tables-versus-native-tables"></a><span data-ttu-id="a9303-120">Tabelle virtuali contro tabelle native</span><span class="sxs-lookup"><span data-stu-id="a9303-120">Virtual tables versus native tables</span></span>

<span data-ttu-id="a9303-121">Le tabelle virtuali di Human Resources non sono uguali alle tabelle Dataverse native create per Human Resources.</span><span class="sxs-lookup"><span data-stu-id="a9303-121">Virtual tables for Human Resources aren't the same as the native Dataverse tables created for Human Resources.</span></span> 

<span data-ttu-id="a9303-122">Le tabelle native per Human Resources vengono generate separatamente e gestite nella soluzione Gestione connessione ibrida comune in Dataverse.</span><span class="sxs-lookup"><span data-stu-id="a9303-122">The native tables for Human Resources are generated separately and maintained in the HCM Common solution in Dataverse.</span></span> <span data-ttu-id="a9303-123">Con le tabelle native, i dati vengono archiviati in Dataverse e richiedono la sincronizzazione con il database dell'applicazione Human Resources.</span><span class="sxs-lookup"><span data-stu-id="a9303-123">With native tables, the data is stored in Dataverse and requires synchronization with the Human Resources application database.</span></span>

> [!NOTE]
> <span data-ttu-id="a9303-124">Per un elenco delle tabelle Dataverse native per Human Resources, vedi [Tabelle di Dataverse](https://docs.microsoft.com/dynamics365/human-resources/hr-developer-entities).</span><span class="sxs-lookup"><span data-stu-id="a9303-124">For a list of the native Dataverse tables for Human Resources, see [Dataverse tables](https://docs.microsoft.com/dynamics365/human-resources/hr-developer-entities).</span></span>

## <a name="setup"></a><span data-ttu-id="a9303-125">Attrezzaggio</span><span class="sxs-lookup"><span data-stu-id="a9303-125">Setup</span></span>

<span data-ttu-id="a9303-126">Segui questi passaggi di configurazione per abilitare le tabelle virtuali nel tuo ambiente.</span><span class="sxs-lookup"><span data-stu-id="a9303-126">Follow these setup steps to enable virtual tables in your environment.</span></span>

### <a name="enable-virtual-tables-in-human-resources"></a><span data-ttu-id="a9303-127">Abilitare le tabelle virtuali in Human Resources</span><span class="sxs-lookup"><span data-stu-id="a9303-127">Enable virtual tables in Human Resources</span></span>

<span data-ttu-id="a9303-128">Innanzitutto, è necessario abilitare le tabelle virtuali nell'area di lavoro **Gestione delle funzionalità**.</span><span class="sxs-lookup"><span data-stu-id="a9303-128">First, you must enable virtual tables in the **Feature management** workspace.</span></span>

1. <span data-ttu-id="a9303-129">In Risorse umane, selezionare **Amministrazione sistema**.</span><span class="sxs-lookup"><span data-stu-id="a9303-129">In Human Resources, select **System administration**.</span></span>

2. <span data-ttu-id="a9303-130">Selezionare il riquadro **Gestione funzionalità**.</span><span class="sxs-lookup"><span data-stu-id="a9303-130">Select the **Feature management** tile.</span></span>

3. <span data-ttu-id="a9303-131">Selezionare **Supporto per tabelle virtuali per HR in Dataverse** e quindi seleziona **Abilita**.</span><span class="sxs-lookup"><span data-stu-id="a9303-131">Select **Virtual table support for HR in Dataverse**, and then select **Enable**.</span></span>

<span data-ttu-id="a9303-132">Per ulteriori informazioni sull'abilitazione e sulla disabilitazione delle funzionalità di anteprima, vedere [Gestire le funzionalità](hr-admin-manage-features.md).</span><span class="sxs-lookup"><span data-stu-id="a9303-132">For more information about enabling and disabling features, see [Manage features](hr-admin-manage-features.md).</span></span>

### <a name="register-the-app-in-microsoft-azure"></a><span data-ttu-id="a9303-133">Registrare l'app in Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="a9303-133">Register the app in Microsoft Azure</span></span>

<span data-ttu-id="a9303-134">È necessario registrare l'istanza di Human Resources nel portale di Azure di modo che Microsoft Identity Platform possa fornire servizi di autenticazione e autorizzazione per l'app e gli utenti.</span><span class="sxs-lookup"><span data-stu-id="a9303-134">You must register your Human Resources instance in the Azure portal so the Microsoft identity platform can provide authentication and authorization services for the app and users.</span></span> <span data-ttu-id="a9303-135">Per ulteriori informazioni sulla registrazione di app in Azure, vedi [Guida introduttiva: Registrare un'applicazione con Microsoft Identity Platform](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app).</span><span class="sxs-lookup"><span data-stu-id="a9303-135">For more information about registering apps in Azure, see [Quickstart: Register an application with the Microsoft identity platform](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app).</span></span>

1. <span data-ttu-id="a9303-136">Apri il [portale di Microsoft Azure](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="a9303-136">Open the [Microsoft Azure portal](https://portal.azure.com).</span></span>

2. <span data-ttu-id="a9303-137">Nell'elenco di servizi di Azure, seleziona **Registrazioni app**.</span><span class="sxs-lookup"><span data-stu-id="a9303-137">In the Azure services list, select **App registrations**.</span></span>

3. <span data-ttu-id="a9303-138">Seleziona **Nuova registrazione**.</span><span class="sxs-lookup"><span data-stu-id="a9303-138">Select **New registration**.</span></span>

4. <span data-ttu-id="a9303-139">Nel campo **Nome** immetti un nome descrittivo per l'app.</span><span class="sxs-lookup"><span data-stu-id="a9303-139">In the **Name** field, enter a descriptive name for the app.</span></span> <span data-ttu-id="a9303-140">Ad esempio, **Tabelle virtuali di Dynamics 365 Human Resources**.</span><span class="sxs-lookup"><span data-stu-id="a9303-140">For example, **Dynamics 365 Human Resources Virtual Tables**.</span></span>

5. <span data-ttu-id="a9303-141">Nel campo **URI di reindirizzamento**, immetti l'URL dello spazio dei nomi dell'istanza di Human Resources.</span><span class="sxs-lookup"><span data-stu-id="a9303-141">In the **Redirect URI** field, enter the namespace URL of your instance of Human Resources.</span></span>

6. <span data-ttu-id="a9303-142">Seleziona **Registro**.</span><span class="sxs-lookup"><span data-stu-id="a9303-142">Select **Register**.</span></span>

7. <span data-ttu-id="a9303-143">Al termine della registrazione, il portale di Azure visualizza il riquadro **Panoramica** della registrazione dell'app che include il relativo **ID applicazione (client)**.</span><span class="sxs-lookup"><span data-stu-id="a9303-143">When registration completes, the Azure portal displays the app registration's **Overview** pane, which includes its **Application (client) ID**.</span></span> <span data-ttu-id="a9303-144">Prendi nota adesso dell'**ID applicazione (client)**.</span><span class="sxs-lookup"><span data-stu-id="a9303-144">Take note of the **Application (client) ID** at this time.</span></span> <span data-ttu-id="a9303-145">Immetterai queste informazioni quando si [configura l'origine dati delle tabelle virtuali](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-table-data-source).</span><span class="sxs-lookup"><span data-stu-id="a9303-145">You'll enter this information when you [Configure the virtual table data source](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-table-data-source).</span></span>

8. <span data-ttu-id="a9303-146">Nel riquadro di spostamento a sinistra, seleziona **Certificati e segreti**.</span><span class="sxs-lookup"><span data-stu-id="a9303-146">In the left navigation pane, select **Certificates and secrets**.</span></span>

9. <span data-ttu-id="a9303-147">Nella sezione **Segreti client** della pagina, seleziona **Nuovo segreto client**.</span><span class="sxs-lookup"><span data-stu-id="a9303-147">In the **Client secrets** section of the page, select **New client secret**.</span></span>

10. <span data-ttu-id="a9303-148">Fornisci una descrizione, seleziona una durata e seleziona **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="a9303-148">Provide a description, select a duration, and select **Add**.</span></span>

11. <span data-ttu-id="a9303-149">Registra il valore del segreto.</span><span class="sxs-lookup"><span data-stu-id="a9303-149">Record the secret's value.</span></span> <span data-ttu-id="a9303-150">Immetterai queste informazioni quando si [configura l'origine dati delle tabelle virtuali](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-table-data-source).</span><span class="sxs-lookup"><span data-stu-id="a9303-150">You'll enter this information when you [Configure the virtual table data source](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-table-data-source).</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="a9303-151">Assicurati di prendere nota adesso del valore del segreto.</span><span class="sxs-lookup"><span data-stu-id="a9303-151">Be sure to take note of the secret's value at this time.</span></span> <span data-ttu-id="a9303-152">Il segreto non viene mai visualizzato dopo la chiusura di questa pagina.</span><span class="sxs-lookup"><span data-stu-id="a9303-152">The secret is never displayed again after you leave this page.</span></span>

### <a name="install-the-dynamics-365-hr-virtual-table-app"></a><span data-ttu-id="a9303-153">Installare l'app Dynamics 365 HR Virtual Table</span><span class="sxs-lookup"><span data-stu-id="a9303-153">Install the Dynamics 365 HR Virtual Table app</span></span>

<span data-ttu-id="a9303-154">Installa l'app Dynamics 365 HR Virtual Table nell'ambiente Power Apps per distribuire il pacchetto di soluzioni di tabelle virtuali in Dataverse.</span><span class="sxs-lookup"><span data-stu-id="a9303-154">Install the Dynamics 365 HR Virtual Table app in your Power Apps environment to deploy the virtual table solution package to Dataverse.</span></span>

1. <span data-ttu-id="a9303-155">Apri l'[interfaccia di amministrazione di Power Platform](https://admin.powerplatform.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="a9303-155">Open the [Power Platform admin center](https://admin.powerplatform.microsoft.com).</span></span>

2. <span data-ttu-id="a9303-156">Nell'elenco **Ambienti**, seleziona l'ambiente Power Apps associato all'istanza di Human Resources.</span><span class="sxs-lookup"><span data-stu-id="a9303-156">In the **Environments** list, select the Power Apps environment associated with your Human Resources instance.</span></span>

3. <span data-ttu-id="a9303-157">Nella sezione **Risorse** della pagina, seleziona **App Dynamics 365**.</span><span class="sxs-lookup"><span data-stu-id="a9303-157">In the **Resources** section of the page, select **Dynamics 365 apps**.</span></span>

4. <span data-ttu-id="a9303-158">Seleziona l'azione **Installa app**.</span><span class="sxs-lookup"><span data-stu-id="a9303-158">Select the **Install app** action.</span></span>

5. <span data-ttu-id="a9303-159">Seleziona **Dynamics 365 HR Virtual Table** e quindi **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a9303-159">Select **Dynamics 365 HR Virtual Table**, and select **Next**.</span></span>

6. <span data-ttu-id="a9303-160">Leggi le condizioni d'uso e accettale.</span><span class="sxs-lookup"><span data-stu-id="a9303-160">Review and mark to agree to the terms of service.</span></span>

7. <span data-ttu-id="a9303-161">Seleziona **Installa**.</span><span class="sxs-lookup"><span data-stu-id="a9303-161">Select **Install**.</span></span>

<span data-ttu-id="a9303-162">L'installazione richiede alcuni minuti.</span><span class="sxs-lookup"><span data-stu-id="a9303-162">The install takes a few minutes.</span></span> <span data-ttu-id="a9303-163">Al termine, continua con i passaggi successivi.</span><span class="sxs-lookup"><span data-stu-id="a9303-163">When it completes, continue to the next steps.</span></span>

![Installare l'app Dynamics 365 HR Virtual Table dall'interfaccia di amministrazione di Power Platform](./media/hr-admin-integration-virtual-entities-power-platform-install.jpg)

### <a name="configure-the-virtual-table-data-source"></a><span data-ttu-id="a9303-165">Configurare l'origine dati delle tabelle virtuali</span><span class="sxs-lookup"><span data-stu-id="a9303-165">Configure the virtual table data source</span></span> 

<span data-ttu-id="a9303-166">Il passaggio successivo consiste nel configurare l'origine dati delle tabelle virtuali nell'ambiente Power Apps.</span><span class="sxs-lookup"><span data-stu-id="a9303-166">The next step is to configure the virtual table data source in the Power Apps environment.</span></span> 

1. <span data-ttu-id="a9303-167">Apri l'[interfaccia di amministrazione di Power Platform](https://admin.powerplatform.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="a9303-167">Open the [Power Platform admin center](https://admin.powerplatform.microsoft.com).</span></span>

2. <span data-ttu-id="a9303-168">Nell'elenco **Ambienti**, seleziona l'ambiente Power Apps associato all'istanza di Human Resources.</span><span class="sxs-lookup"><span data-stu-id="a9303-168">In the **Environments** list, select the Power Apps environment associated with your Human Resources instance.</span></span>

3. <span data-ttu-id="a9303-169">Seleziona l'**URL ambiente** nella sezione **Dettagli** della pagina.</span><span class="sxs-lookup"><span data-stu-id="a9303-169">Select the **Environment URL** in the **Details** section of the page.</span></span>

4. <span data-ttu-id="a9303-170">In **Hub integrità soluzione**, seleziona l'icona **Ricerca avanzata** in alto a destra nella pagina dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="a9303-170">In the **Solution Health Hub**, select the **Advanced Find** icon in the top right of the application page.</span></span>

5. <span data-ttu-id="a9303-171">Nella pagina **Ricerca avanzata**, nell'elenco a discesa **Cerca**, seleziona **Configurazioni dell'origine dati virtuale di Finance and Operations**.</span><span class="sxs-lookup"><span data-stu-id="a9303-171">On the **Advanced Find** page, in the **Look for** dropdown list, select **Finance and Operations Virtual Data Source Configurations**.</span></span>

6. <span data-ttu-id="a9303-172">Seleziona **Risultati**.</span><span class="sxs-lookup"><span data-stu-id="a9303-172">Select **Results**.</span></span>

7. <span data-ttu-id="a9303-173">Seleziona il record **Origine dati Microsoft HR**.</span><span class="sxs-lookup"><span data-stu-id="a9303-173">Select the **Microsoft HR Data Source** record.</span></span>

8. <span data-ttu-id="a9303-174">Immettere le informazioni necessarie per la configurazione dell'origine dati:</span><span class="sxs-lookup"><span data-stu-id="a9303-174">Enter the required information for the data source configuration:</span></span>

   - <span data-ttu-id="a9303-175">**URL di destinazione**: l'URL dello spazio dei nomi di Human Resources.</span><span class="sxs-lookup"><span data-stu-id="a9303-175">**Target URL**: The URL of your Human Resources namespace.</span></span> <span data-ttu-id="a9303-176">Il formato dell'URL di destinazione è:</span><span class="sxs-lookup"><span data-stu-id="a9303-176">The format of the target URL is:</span></span>
     
     <span data-ttu-id="a9303-177">https://\<hostname\>.hr.talent.dynamics.com/namespaces/\<namespaceID\>/</span><span class="sxs-lookup"><span data-stu-id="a9303-177">https://\<hostname\>.hr.talent.dynamics.com/namespaces/\<namespaceID\>/</span></span>

     <span data-ttu-id="a9303-178">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="a9303-178">For example:</span></span>
     
     `https://aos.rts-sf-5ea54e35c68-westus2.hr.talent.dynamics.com/namespaces/49d24c565-8f4d-4891-b174-bf83d948ed0c/`

     >[!NOTE]
     ><span data-ttu-id="a9303-179">Assicurarsi di includere il carattere "**/**" alla fine dell'URL per evitare di ricevere un errore.</span><span class="sxs-lookup"><span data-stu-id="a9303-179">Be sure to include the "**/**" character at the end of the URL to avoid receiving an error.</span></span>

   - <span data-ttu-id="a9303-180">**ID tenant**: l'ID tenant di Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="a9303-180">**Tenant ID**: The Azure Active Directory (Azure AD) tenant ID.</span></span>

   - <span data-ttu-id="a9303-181">**ID applicazione AAD**: l'ID applicazione (client) creato per l'applicazione registrata nel portale di Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="a9303-181">**AAD Application ID**: The application (client) ID created for the application registered in the Microsoft Azure portal.</span></span> <span data-ttu-id="a9303-182">Hai ricevuto queste informazioni in precedenza durante il passaggio [Registrare l'app in Microsoft Azure](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure).</span><span class="sxs-lookup"><span data-stu-id="a9303-182">You received this information earlier during the step [Register the app in Microsoft Azure](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure).</span></span>

   - <span data-ttu-id="a9303-183">**ID applicazione AAD**: il segreto client creato per l'applicazione registrata nel portale di Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="a9303-183">**AAD Application Secret**: The client secret created for the application registered in the Microsoft Azure portal.</span></span> <span data-ttu-id="a9303-184">Hai ricevuto queste informazioni in precedenza durante il passaggio [Registrare l'app in Microsoft Azure](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure).</span><span class="sxs-lookup"><span data-stu-id="a9303-184">You received this information earlier during the step [Register the app in Microsoft Azure](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure).</span></span>

   ![Origine dati di Microsoft HR](./media/hr-admin-integration-virtual-entities-hr-data-source.jpg)

9. <span data-ttu-id="a9303-186">Seleziona **Salva e chiudi**.</span><span class="sxs-lookup"><span data-stu-id="a9303-186">Select **Save & Close**.</span></span>

### <a name="grant-app-permissions-in-human-resources"></a><span data-ttu-id="a9303-187">Concedere autorizzazioni dell'app in Human Resources</span><span class="sxs-lookup"><span data-stu-id="a9303-187">Grant app permissions in Human Resources</span></span>

<span data-ttu-id="a9303-188">Concedi autorizzazioni per due applicazioni Azure AD in Human Resources:</span><span class="sxs-lookup"><span data-stu-id="a9303-188">Grant permissions for the two Azure AD applications in Human Resources:</span></span>

- <span data-ttu-id="a9303-189">L'app creata per il tenant nel portale di Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="a9303-189">The app created for your tenant in the Microsoft Azure portal</span></span>
- <span data-ttu-id="a9303-190">L'app Dynamics 365 HR Virtual Table installata nell'ambiente Power Apps</span><span class="sxs-lookup"><span data-stu-id="a9303-190">The Dynamics 365 HR Virtual Table app installed in the Power Apps environment</span></span> 

1. <span data-ttu-id="a9303-191">In Human Resources, apri la pagina **Applicazioni di Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="a9303-191">In Human Resources, open the **Azure Active Directory applications** page.</span></span>

2. <span data-ttu-id="a9303-192">Seleziona **Nuovo** per creare un nuovo record di applicazione:</span><span class="sxs-lookup"><span data-stu-id="a9303-192">Select **New** to create a new application record:</span></span>

    - <span data-ttu-id="a9303-193">Nel campo **ID client**, inserisci l'ID client dell'app che hai registrato nel portale di Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="a9303-193">In the **Client ID** field, enter the client ID of the app you registered in the Microsoft Azure portal.</span></span>
    - <span data-ttu-id="a9303-194">Nel campo **Nome**, immetti il nome dell'app che hai registrato nel portale di Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="a9303-194">In the **Name** field, enter the name of the app you registered in the Microsoft Azure portal.</span></span>
    - <span data-ttu-id="a9303-195">Nel campo **ID utente** seleziona l'ID utente di un utente con autorizzazioni di amministratore in Human Resources e nell'ambiente Power Apps.</span><span class="sxs-lookup"><span data-stu-id="a9303-195">In the **User ID** field, select the user ID of a user with admin permissions in Human Resources and the Power Apps environment.</span></span>

3. <span data-ttu-id="a9303-196">Seleziona **Nuovo** per creare un secondo record di applicazione:</span><span class="sxs-lookup"><span data-stu-id="a9303-196">Select **New** to create a second application record:</span></span>

    - <span data-ttu-id="a9303-197">**ID client**: f9be0c49-aa22-4ec6-911a-c5da515226ff</span><span class="sxs-lookup"><span data-stu-id="a9303-197">**Client Id**: f9be0c49-aa22-4ec6-911a-c5da515226ff</span></span>
    - <span data-ttu-id="a9303-198">**Nome**: Dynamics 365 HR Virtual Table</span><span class="sxs-lookup"><span data-stu-id="a9303-198">**Name**: Dynamics 365 HR Virtual Table</span></span>
    - <span data-ttu-id="a9303-199">Nel campo **ID utente** seleziona l'ID utente di un utente con autorizzazioni di amministratore in Human Resources e nell'ambiente Power Apps.</span><span class="sxs-lookup"><span data-stu-id="a9303-199">In the **User ID** field, select the user ID of a user with admin permissions in Human Resources and the Power Apps environment.</span></span>

## <a name="generate-virtual-tables"></a><span data-ttu-id="a9303-200">Generare tabelle virtuali</span><span class="sxs-lookup"><span data-stu-id="a9303-200">Generate virtual tables</span></span>

<span data-ttu-id="a9303-201">Al termine della configurazione, puoi selezionare le tabelle virtuali che desideri generare e abilitare nell'istanza di Dataverse.</span><span class="sxs-lookup"><span data-stu-id="a9303-201">When setup completes, you can select the virtual tables you want to generate and enable in your Dataverse instance.</span></span>

1. <span data-ttu-id="a9303-202">In Human Resources, aprire la pagina **Integrazione di Dataverse**.</span><span class="sxs-lookup"><span data-stu-id="a9303-202">In Human Resources, open the **Dataverse integration** page.</span></span>

2. <span data-ttu-id="a9303-203">Selezionare la scheda **Tabelle virtuali**.</span><span class="sxs-lookup"><span data-stu-id="a9303-203">Select the **Virtual tables** tab.</span></span>

> [!NOTE]
> <span data-ttu-id="a9303-204">L'interruttore **Abilita tabelle virtuale** sarà impostato su **Sì** automaticamente quando tutte le impostazioni richieste sono state completate.</span><span class="sxs-lookup"><span data-stu-id="a9303-204">The **Enable virtual tables** toggle will be set to **Yes** automatically when all required setup has been completed.</span></span> <span data-ttu-id="a9303-205">Se l'interruttore è impostato su **No**, rivedere i passaggi nelle sezioni precedenti di questo documento per assicurarsi che tutte le impostazioni dei prerequisiti siano state completate.</span><span class="sxs-lookup"><span data-stu-id="a9303-205">If the toggle is set to **No**, review the steps in previous sections of this document to ensure all prerequisite setup is completed.</span></span>

3. <span data-ttu-id="a9303-206">Seleziona la tabella o le tabelle da generare in Dataverse.</span><span class="sxs-lookup"><span data-stu-id="a9303-206">Select the table or tables you want to generate in Dataverse.</span></span>

4. <span data-ttu-id="a9303-207">Selezionare **Genera/Aggiorna**.</span><span class="sxs-lookup"><span data-stu-id="a9303-207">Select **Generate/refresh**.</span></span>

![Integrazione di Dataverse](./media/hr-admin-integration-common-data-service-integration.jpg)

## <a name="check-table-generation-status"></a><span data-ttu-id="a9303-209">Controllare lo stato di generazione della tabella</span><span class="sxs-lookup"><span data-stu-id="a9303-209">Check table generation status</span></span>

<span data-ttu-id="a9303-210">Le tabelle virtuali vengono generate in Dataverse attraverso un processo in background asincrono.</span><span class="sxs-lookup"><span data-stu-id="a9303-210">Virtual tables are generated in Dataverse through an asynchronous background process.</span></span> <span data-ttu-id="a9303-211">Aggiornamenti sulla visualizzazione del processo nel centro azioni.</span><span class="sxs-lookup"><span data-stu-id="a9303-211">Updates on the process display in the action center.</span></span> <span data-ttu-id="a9303-212">I dettagli sul processo, inclusi i log degli errori, vengono visualizzati nella pagina **Automazioni di processo**.</span><span class="sxs-lookup"><span data-stu-id="a9303-212">Details on the process, including error logs, appear in the **Process automations** page.</span></span>

1. <span data-ttu-id="a9303-213">In Human Resources, aprire la pagina **Automazioni di processo**.</span><span class="sxs-lookup"><span data-stu-id="a9303-213">In Human Resources, open the **Process automations** page.</span></span>

2. <span data-ttu-id="a9303-214">Selezionare la scheda **Processi in background**.</span><span class="sxs-lookup"><span data-stu-id="a9303-214">Select the **Background processes** tab.</span></span>

3. <span data-ttu-id="a9303-215">Seleziona **Processo in background dell'operazione asincrona di polling della tabella virtuale**.</span><span class="sxs-lookup"><span data-stu-id="a9303-215">Select **Virtual table poll async operation background process**.</span></span>

4. <span data-ttu-id="a9303-216">Selezionare **Visualizza risultati più recenti**.</span><span class="sxs-lookup"><span data-stu-id="a9303-216">Select **View most recent results**.</span></span>

<span data-ttu-id="a9303-217">Il riquadro scorrevole mostra i risultati di esecuzione più recenti per il processo.</span><span class="sxs-lookup"><span data-stu-id="a9303-217">The slideout pane displays the most recent execution results for the process.</span></span> <span data-ttu-id="a9303-218">È possibile visualizzare il registro del processo, inclusi eventuali errori restituiti da Dataverse.</span><span class="sxs-lookup"><span data-stu-id="a9303-218">You can view the log for the process, including any errors returned from Dataverse.</span></span>

## <a name="see-also"></a><span data-ttu-id="a9303-219">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a9303-219">See also</span></span>

[<span data-ttu-id="a9303-220">Che cos'è Dataverse?</span><span class="sxs-lookup"><span data-stu-id="a9303-220">What is Dataverse?</span></span>](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro)<br>
[<span data-ttu-id="a9303-221">Tabelle in Dataverse</span><span class="sxs-lookup"><span data-stu-id="a9303-221">Tables in Dataverse</span></span>](https://docs.microsoft.com/powerapps/maker/common-data-service/entity-overview)<br>
[<span data-ttu-id="a9303-222">Panoramica delle relazioni tra tabelle</span><span class="sxs-lookup"><span data-stu-id="a9303-222">Table relationships overview</span></span>](https://docs.microsoft.com/powerapps/maker/common-data-service/relationships-overview)<br>
[<span data-ttu-id="a9303-223">Creare e modificare tabelle virtuali che contengono dati di un'origine dati esterna</span><span class="sxs-lookup"><span data-stu-id="a9303-223">Create and edit virtual tables that contain data from an external data source</span></span>](https://docs.microsoft.com/powerapps/maker/common-data-service/create-edit-virtual-entities)<br>
[<span data-ttu-id="a9303-224">Cosa sono i portali di Power Apps?</span><span class="sxs-lookup"><span data-stu-id="a9303-224">What is Power Apps portals?</span></span>](https://docs.microsoft.com/powerapps/maker/portals/overview)<br>
[<span data-ttu-id="a9303-225">Panoramica sulla creazione di app in Power Apps</span><span class="sxs-lookup"><span data-stu-id="a9303-225">Overview of creating apps in Power Apps</span></span>](https://docs.microsoft.com/powerapps/maker/)


[!INCLUDE[footer-include](../includes/footer-banner.md)]