---
title: Integrazione con LinkedIn Talent Hub
description: In questo argomento viene descritto come impostare l'integrazione tra Microsoft Dynamics 365 Human Resources e LinkedIn Talent Hub.
author: jaredha
manager: tfehr
ms.date: 10/20/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-10-20
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 6f70e3a6ccf9770c75334d355db5e9df9ee912dd
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/17/2020
ms.locfileid: "4527887"
---
# <a name="integrate-with-linkedin-talent-hub"></a><span data-ttu-id="81d2f-103">Integrazione con LinkedIn Talent Hub</span><span class="sxs-lookup"><span data-stu-id="81d2f-103">Integrate with LinkedIn Talent Hub</span></span>

[!include [banner](includes/preview-feature.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="81d2f-104">[LinkedIn Talent Hub](https://business.linkedin.com/talent-solutions/talent-hub) è una piattaforma ATS (applicant tracking system).</span><span class="sxs-lookup"><span data-stu-id="81d2f-104">[LinkedIn Talent Hub](https://business.linkedin.com/talent-solutions/talent-hub) is an applicant tracking system (ATS) platform.</span></span> <span data-ttu-id="81d2f-105">Consente di reperire, gestire e assumere dipendenti in un unico posto.</span><span class="sxs-lookup"><span data-stu-id="81d2f-105">It lets you source, manage, and hire employees all in one place.</span></span> <span data-ttu-id="81d2f-106">Integrando Microsoft Dynamics 365 Human Resources con LinkedIn Talent Hub, è possibile creare facilmente i record dei dipendenti in Human Resources per i candidati che sono stati assunti per una posizione.</span><span class="sxs-lookup"><span data-stu-id="81d2f-106">By integrating Microsoft Dynamics 365 Human Resources with LinkedIn Talent Hub, you can easily create employee records in Human Resources for applicants who have been hired for a position.</span></span>

## <a name="setup"></a><span data-ttu-id="81d2f-107">Attrezzaggio</span><span class="sxs-lookup"><span data-stu-id="81d2f-107">Setup</span></span>

<span data-ttu-id="81d2f-108">Un amministratore di sistema deve completare le attività di configurazione per abilitare l'integrazione con LinkedIn Talent Hub.</span><span class="sxs-lookup"><span data-stu-id="81d2f-108">A system administrator must complete setup tasks to enable integration with LinkedIn Talent Hub.</span></span> <span data-ttu-id="81d2f-109">Innanzitutto, nell'ambiente Power Apps, è necessario configurare un utente e un ruolo di sicurezza per concedere a LinkedIn Talent Hub le autorizzazioni appropriate per scrivere i dati in Human Resources.</span><span class="sxs-lookup"><span data-stu-id="81d2f-109">First, in the Power Apps environment, you must set up a user and security role to grant LinkedIn Talent Hub the appropriate permissions to write data into Human Resources.</span></span>

### <a name="link-your-environment-to-linkedin-talent-hub"></a><span data-ttu-id="81d2f-110">Collegare l'ambiente a LinkedIn Talent Hub</span><span class="sxs-lookup"><span data-stu-id="81d2f-110">Link your environment to LinkedIn Talent Hub</span></span>

1. <span data-ttu-id="81d2f-111">Aprire [LinkedIn Talent Hub](https://business.linkedin.com/talent-solutions/talent-hub).</span><span class="sxs-lookup"><span data-stu-id="81d2f-111">Open [LinkedIn Talent Hub](https://business.linkedin.com/talent-solutions/talent-hub).</span></span>

2. <span data-ttu-id="81d2f-112">Nel menu a discesa dell'utente, selezionare **Impostazioni del prodotto**.</span><span class="sxs-lookup"><span data-stu-id="81d2f-112">On the user drop-down menu, select **Product Settings**.</span></span>

3. <span data-ttu-id="81d2f-113">Nel riquadro di spostamento a sinistra, nella sezione **Avanzate** selezionare **Integrazioni**.</span><span class="sxs-lookup"><span data-stu-id="81d2f-113">In the left navigation pane, in the **Advanced** section, select **Integrations**.</span></span>

4. <span data-ttu-id="81d2f-114">Selezionare **Autorizza** per l'integrazione di Microsoft Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="81d2f-114">Select **Authorize** for the Microsoft Dynamics 365 Human Resources integration.</span></span>

5. <span data-ttu-id="81d2f-115">Nella pagina **Dynamics 365 Human Resources** selezionare l'ambiente a cui collegare LinkedIn Talent Hub, quindi selezionare **Collega**.</span><span class="sxs-lookup"><span data-stu-id="81d2f-115">On the **Dynamics 365 Human Resources** page, select the environment to link LinkedIn Talent Hub to, and then select **Link**.</span></span>

    ![Onboarding di LinkedIn Talent Hub](./media/hr-admin-integration-talent-hub-onboarding.jpg)

    > [!NOTE]
    > <span data-ttu-id="81d2f-117">È possibile collegarsi solo ad ambienti in cui l'account utente dispone dell'accesso come amministratore sia all'ambiente Human Resources che a quello Power Apps associato.</span><span class="sxs-lookup"><span data-stu-id="81d2f-117">You can link only to environments where your user account has administrator access to both the Human Resources environment and the associated Power Apps environment.</span></span> <span data-ttu-id="81d2f-118">Se nessun ambiente è elencato nella pagina di collegamento di Human Resources, assicurarsi di disporre di ambienti Human Resources con licenza nel tenant e che l'utente che ha effettuato l'accesso alla pagina di collegamento disponga delle autorizzazioni di amministratore sia per l'ambiente Human Resources che per quello Power Apps.</span><span class="sxs-lookup"><span data-stu-id="81d2f-118">If no environments are listed on the Human Resources link page, make sure that you have licensed Human Resources environments on the tenant, and that the user that you signed in to the link page as has administrator permissions to both the Human Resources environment and the Power Apps environment.</span></span>

### <a name="create-a-power-apps-security-role"></a><span data-ttu-id="81d2f-119">Creare un ruolo di sicurezza Power Apps</span><span class="sxs-lookup"><span data-stu-id="81d2f-119">Create a Power Apps security role</span></span>

1. <span data-ttu-id="81d2f-120">Apri l'[interfaccia di amministrazione di Power Platform](https://admin.powerplatform.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="81d2f-120">Open the [Power Platform admin center](https://admin.powerplatform.microsoft.com).</span></span>

2. <span data-ttu-id="81d2f-121">Nell'elenco **Ambienti** selezionare l'ambiente associato all'ambiente Human Resources a cui si desidera collegare l'istanza di LinkedIn Talent Hub.</span><span class="sxs-lookup"><span data-stu-id="81d2f-121">In the **Environments** list, select the environment that is associated with the Human Resources environment that you want to link your instance of LinkedIn Talent Hub to.</span></span>

3. <span data-ttu-id="81d2f-122">Selezionare **Impostazioni**.</span><span class="sxs-lookup"><span data-stu-id="81d2f-122">Select **Settings**.</span></span>

4. <span data-ttu-id="81d2f-123">Espandere il nodo **Utenti + Autorizzazioni** e selezionare **Ruoli di sicurezza**.</span><span class="sxs-lookup"><span data-stu-id="81d2f-123">Expand the **Users + Permissions** node, and select **Security Roles**.</span></span>

5. <span data-ttu-id="81d2f-124">Nella pagina **Ruoli di sicurezza** sulla barra degli strumenti selezionare **Nuovo ruolo**.</span><span class="sxs-lookup"><span data-stu-id="81d2f-124">On the **Security Roles** page, on the toolbar, select **New role**.</span></span>

6. <span data-ttu-id="81d2f-125">Nella scheda **Dettagli** immettere un nome per il ruolo, ad esempio **Integrazione HRIS LinkedIn Talent Hub**.</span><span class="sxs-lookup"><span data-stu-id="81d2f-125">On the **Details** tab, enter a name for the role, such as **LinkedIn Talent Hub HRIS Integration**.</span></span>

7. <span data-ttu-id="81d2f-126">Nella scheda **Personalizzazione** selezionare l'autorizzazione **Lettura** del livello di organizzazione per le seguenti entità:</span><span class="sxs-lookup"><span data-stu-id="81d2f-126">On the **Customization** tab, select organization-level **Read** permission for the following entities:</span></span>

    - <span data-ttu-id="81d2f-127">Entità</span><span class="sxs-lookup"><span data-stu-id="81d2f-127">Entity</span></span>
    - <span data-ttu-id="81d2f-128">Campo</span><span class="sxs-lookup"><span data-stu-id="81d2f-128">Field</span></span>
    - <span data-ttu-id="81d2f-129">Rapporto</span><span class="sxs-lookup"><span data-stu-id="81d2f-129">Relationship</span></span>

8. <span data-ttu-id="81d2f-130">Salvare e chiudere il ruolo di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="81d2f-130">Save and close the security role.</span></span>

### <a name="create-a-power-apps-application-user"></a><span data-ttu-id="81d2f-131">Creare un utente dell'applicazione Power Apps</span><span class="sxs-lookup"><span data-stu-id="81d2f-131">Create a Power Apps application user</span></span>

<span data-ttu-id="81d2f-132">È necessario creare un utente dell'applicazione affinché l'adattatore LinkedIn Talent Hub conceda le autorizzazioni all'adattatore per scrivere i record dei candidati nell'ambiente Power Apps.</span><span class="sxs-lookup"><span data-stu-id="81d2f-132">An application user must be created for the LinkedIn Talent Hub adapter to grant permissions to the adapter to write candidate records into the Power Apps environment.</span></span>

1. <span data-ttu-id="81d2f-133">Apri l'[interfaccia di amministrazione di Power Platform](https://admin.powerplatform.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="81d2f-133">Open the [Power Platform admin center](https://admin.powerplatform.microsoft.com).</span></span>

2. <span data-ttu-id="81d2f-134">Nell'elenco **Ambienti** selezionare l'ambiente associato all'ambiente Human Resources a cui si desidera collegare l'istanza di LinkedIn Talent Hub.</span><span class="sxs-lookup"><span data-stu-id="81d2f-134">In the **Environments** list, select the environment that is associated with the Human Resources environment that you want to link your instance of LinkedIn Talent Hub to.</span></span>

3. <span data-ttu-id="81d2f-135">Selezionare **Impostazioni**.</span><span class="sxs-lookup"><span data-stu-id="81d2f-135">Select **Settings**.</span></span>

4. <span data-ttu-id="81d2f-136">Espandere il nodo **Utenti + Autorizzazioni** e selezionare **Utenti**.</span><span class="sxs-lookup"><span data-stu-id="81d2f-136">Expand the **Users + Permissions** node, and select **Users**.</span></span>

5. <span data-ttu-id="81d2f-137">Selezionare **Gestisci utenti in Dynamics 365**.</span><span class="sxs-lookup"><span data-stu-id="81d2f-137">Select **Manage users in Dynamics 365**.</span></span>

6. <span data-ttu-id="81d2f-138">Utilizzare il menu a discesa sopra l'elenco per modificare la visualizzazione da quella predefinita **Utenti abilitati** a **Utenti dell'applicazione**.</span><span class="sxs-lookup"><span data-stu-id="81d2f-138">Use the drop-down menu above the list to change the view from the default **Enabled Users** view to **Application Users**.</span></span>

    ![Visualizzazione Utenti di applicazioni](./media/hr-admin-integration-power-apps-application-users.jpg)

7. <span data-ttu-id="81d2f-140">Sulla barra degli strumenti selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="81d2f-140">On the toolbar, select **New**.</span></span>

8. <span data-ttu-id="81d2f-141">Nella pagina **Nuovo utente** effettuare i seguenti passaggi:</span><span class="sxs-lookup"><span data-stu-id="81d2f-141">On the **New user** page, follow these steps:</span></span>

    1. <span data-ttu-id="81d2f-142">Cambiare il valore del campo **Tipo di utente** su **Utente dell'applicazione**.</span><span class="sxs-lookup"><span data-stu-id="81d2f-142">Change the value of the **User type** field to **Application User**.</span></span>
    2. <span data-ttu-id="81d2f-143">Impostare il campo **Nome utente** su **Integrazione HRIS Dynamics365 HR LinkedIn**.</span><span class="sxs-lookup"><span data-stu-id="81d2f-143">Set the **User Name** field to **Dynamics365 HR LinkedIn HRIS Integration**.</span></span>
    3. <span data-ttu-id="81d2f-144">Impostare il campo **ID applicazione** su **3a225c96-d62a-44ce-b3ec-bd4e8e9befef**.</span><span class="sxs-lookup"><span data-stu-id="81d2f-144">Set the **Application ID** field to **3a225c96-d62a-44ce-b3ec-bd4e8e9befef**.</span></span>
    4. <span data-ttu-id="81d2f-145">Immettere un valore nei campi **Nome**, **Cognome** e **Indirizzo di posta elettronica principale**.</span><span class="sxs-lookup"><span data-stu-id="81d2f-145">Enter any value in the **First Name**, **Last Name**, and **Primary Email** fields.</span></span>
    5. <span data-ttu-id="81d2f-146">Nella barra degli strumenti selezionare **Salva \& chiudi**.</span><span class="sxs-lookup"><span data-stu-id="81d2f-146">On the toolbar, select **Save \& Close**.</span></span>

### <a name="assign-a-security-role-to-the-new-user"></a><span data-ttu-id="81d2f-147">Assegnare un ruolo di sicurezza al nuovo utente</span><span class="sxs-lookup"><span data-stu-id="81d2f-147">Assign a security role to the new user</span></span>

<span data-ttu-id="81d2f-148">Dopo aver salvato e chiuso il nuovo utente dell'applicazione nella sezione precedente, si torna alla pagina **Elenco utenti**.</span><span class="sxs-lookup"><span data-stu-id="81d2f-148">After you save and close the new application user in the previous section, you're returned to the **Users list** page.</span></span>

1. <span data-ttu-id="81d2f-149">Nella pagina **Elenco utenti** cambiare la visualizzazione in **Utenti dell'applicazione**.</span><span class="sxs-lookup"><span data-stu-id="81d2f-149">On the **Users list** page, change the view to **Application Users**.</span></span>

2. <span data-ttu-id="81d2f-150">Selezionare l'utente dell'applicazione creato nella sezione precedente.</span><span class="sxs-lookup"><span data-stu-id="81d2f-150">Select the application user that you created in the previous section.</span></span>

3. <span data-ttu-id="81d2f-151">Nella barra degli strumenti selezionare **Gestisci ruoli**.</span><span class="sxs-lookup"><span data-stu-id="81d2f-151">On the toolbar, select **Manage Roles**.</span></span>

4. <span data-ttu-id="81d2f-152">Selezionare il ruolo di sicurezza creato in precedenza per l'integrazione.</span><span class="sxs-lookup"><span data-stu-id="81d2f-152">Select the security role that you created earlier for the integration.</span></span>

5. <span data-ttu-id="81d2f-153">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="81d2f-153">Select **OK**.</span></span>

### <a name="add-an-azure-active-directory-app-in-human-resources"></a><span data-ttu-id="81d2f-154">Aggiungere un'app Azure Active Directory in Human Resources</span><span class="sxs-lookup"><span data-stu-id="81d2f-154">Add an Azure Active Directory app in Human Resources</span></span>

1. <span data-ttu-id="81d2f-155">In Dynamics 365 Human Resources, aprire la pagina **Applicazioni Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="81d2f-155">In Dynamics 365 Human Resources, open the **Azure Active Directory applications** page.</span></span>
2. <span data-ttu-id="81d2f-156">Aggiungere un nuovo record all'elenco e impostare i seguenti campi:</span><span class="sxs-lookup"><span data-stu-id="81d2f-156">Add a new record to the list, and set the following fields:</span></span>

    - <span data-ttu-id="81d2f-157">**ID client**: immettere **3a225c96-d62a-44ce-b3ec-bd4e8e9befef**.</span><span class="sxs-lookup"><span data-stu-id="81d2f-157">**Client ID**: Enter **3a225c96-d62a-44ce-b3ec-bd4e8e9befef**.</span></span>
    - <span data-ttu-id="81d2f-158">**Nome**: immettere il nome del ruolo di sicurezza Power Apps creato in precedenza, ad esempio **Integrazione HRIS LinkedIn Talent Hub**.</span><span class="sxs-lookup"><span data-stu-id="81d2f-158">**Name**: Enter the name of the Power Apps security role that you created earlier, such as **LinkedIn Talent Hub HRIS Integration**.</span></span>
    - <span data-ttu-id="81d2f-159">**ID utente**: selezionare un utente che dispone delle autorizzazioni per scrivere dati in Gestione del personale.</span><span class="sxs-lookup"><span data-stu-id="81d2f-159">**User ID**: Select a user who has permissions to write data in Personnel Management.</span></span>

### <a name="create-the-entity-in-common-data-service"></a><span data-ttu-id="81d2f-160">Creare l'entità in Common Data Service</span><span class="sxs-lookup"><span data-stu-id="81d2f-160">Create the entity in Common Data Service</span></span>

> [!IMPORTANT]
> <span data-ttu-id="81d2f-161">L'integrazione con LinkedIn Talent Hub dipende dalle entità virtuali in Common Data Service per Human Resources.</span><span class="sxs-lookup"><span data-stu-id="81d2f-161">The integration with LinkedIn Talent Hub depends on virtual entities in Common Data Service for Human Resources.</span></span> <span data-ttu-id="81d2f-162">Come prerequisito per questo passaggio della configurazione, è necessario configurare le entità virtuali.</span><span class="sxs-lookup"><span data-stu-id="81d2f-162">As a prerequisite for this step in the setup, you must configure virtual entities.</span></span> <span data-ttu-id="81d2f-163">Per informazioni su come configurare le entità virtuali, vedere [Configurare entità virtuali Common Data Service](https://docs.microsoft.com/dynamics365/human-resources/hr-admin-integration-common-data-service-virtual-entities).</span><span class="sxs-lookup"><span data-stu-id="81d2f-163">For information about how to configure virtual entities, see [Configure Common Data Service virtual entities](https://docs.microsoft.com/dynamics365/human-resources/hr-admin-integration-common-data-service-virtual-entities).</span></span>

1. <span data-ttu-id="81d2f-164">In Human Resources, aprire la pagina **Integrazione di Common Data Service (CDS)**.</span><span class="sxs-lookup"><span data-stu-id="81d2f-164">In Human Resources, open the **Common Data Service (CDS) integration** page.</span></span>

2. <span data-ttu-id="81d2f-165">Selezionare la scheda **Entità virtuali**.</span><span class="sxs-lookup"><span data-stu-id="81d2f-165">Select the **Virtual entities** tab.</span></span>

3. <span data-ttu-id="81d2f-166">Filtrare l'elenco di entità in base all'etichetta di entità per trovare **Candidato esportato LinkedIn**.</span><span class="sxs-lookup"><span data-stu-id="81d2f-166">Filter the entity list by entity label to find **LinkedIn exported candidate**.</span></span>

4. <span data-ttu-id="81d2f-167">Selezionare l'entità, quindi **Genera/Aggiorna**.</span><span class="sxs-lookup"><span data-stu-id="81d2f-167">Select the entity, and then select **Generate/refresh**.</span></span>

## <a name="exporting-candidate-records"></a><span data-ttu-id="81d2f-168">Esportazione dei record di candidato</span><span class="sxs-lookup"><span data-stu-id="81d2f-168">Exporting candidate records</span></span>

<span data-ttu-id="81d2f-169">Al termine della configurazione, i selezionatori e i professionisti di Human Resources (HR) possono utilizzare la funzione **Esporta in HRIS** in LinkedIn Talent Hub per esportare i record dei candidati assunti da LinkedIn Talent Hub in Human Resources.</span><span class="sxs-lookup"><span data-stu-id="81d2f-169">After the setup is completed, recruiters and Human resources (HR) professionals can use the **Export to HRIS** function in LinkedIn Talent Hub to export hired candidate records from LinkedIn Talent Hub to Human Resources.</span></span>

### <a name="export-records-from-linkedin-talent-hub"></a><span data-ttu-id="81d2f-170">Esportare record da LinkedIn Talent Hub</span><span class="sxs-lookup"><span data-stu-id="81d2f-170">Export records from LinkedIn Talent Hub</span></span>

<span data-ttu-id="81d2f-171">Dopo che un candidato ha completato il processo di selezione ed è stato assunto, è possibile esportare il record del candidato da LinkedIn Talent Hub in Human Resources.</span><span class="sxs-lookup"><span data-stu-id="81d2f-171">After a candidate has moved through the recruiting process and has been hired, you can export the candidate record from LinkedIn Talent Hub to Human Resources.</span></span>

1. <span data-ttu-id="81d2f-172">In LinkedIn Talent Hub, aprire il progetto per il quale è stato assunto il nuovo dipendente.</span><span class="sxs-lookup"><span data-stu-id="81d2f-172">In LinkedIn Talent Hub, open the project that you hired the new employee for.</span></span>

2. <span data-ttu-id="81d2f-173">Selezionare un record di candidato.</span><span class="sxs-lookup"><span data-stu-id="81d2f-173">Select a candidate record.</span></span>

3. <span data-ttu-id="81d2f-174">Selezionare **Cambia fase**, quindi selezionare **Assunto**.</span><span class="sxs-lookup"><span data-stu-id="81d2f-174">Select **Change stage**, and then select **Hired**.</span></span>

4. <span data-ttu-id="81d2f-175">Nel menu con i puntini di sospensione (**...**) per il candidato, selezionare **Esporta in HRIS**.</span><span class="sxs-lookup"><span data-stu-id="81d2f-175">On the ellipsis menu (**...**) for the candidate, select **Export to HRIS**.</span></span>

5. <span data-ttu-id="81d2f-176">Nel riquadro **Esporta in HRIS** immettere le informazioni che devono essere esportate:</span><span class="sxs-lookup"><span data-stu-id="81d2f-176">In the **Export to HRIS** pane, enter the information that must be exported:</span></span>

    - <span data-ttu-id="81d2f-177">Nel campo **Provider HRIS** selezionare **Microsoft Dynamics 365 Human Resources**.</span><span class="sxs-lookup"><span data-stu-id="81d2f-177">In the **HRIS provider** field, select **Microsoft Dynamics 365 Human Resources**.</span></span>
    - <span data-ttu-id="81d2f-178">Selezionare un valore per il nuovo dipendente nel campo **Data di inizio**.</span><span class="sxs-lookup"><span data-stu-id="81d2f-178">In the **Start date** field, select a value for the new employee.</span></span>
    - <span data-ttu-id="81d2f-179">Nel campo **Posizione lavorativa** immettere una posizione lavorativa per il nuovo dipendente.</span><span class="sxs-lookup"><span data-stu-id="81d2f-179">In the **Job title** field, enter a job title for the new employee's job.</span></span>
    - <span data-ttu-id="81d2f-180">Nel campo **Posizione** immettere la sede di lavoro del dipendente.</span><span class="sxs-lookup"><span data-stu-id="81d2f-180">In the **Location** field, enter the location where the employee will be based.</span></span>
    - <span data-ttu-id="81d2f-181">Immettere o verificare l'indirizzo e-mail del dipendente.</span><span class="sxs-lookup"><span data-stu-id="81d2f-181">Enter or verify the employee's email address.</span></span>

![Esportare nel riquadro HRIS in LinkedIn Talent Hub](./media/hr-admin-integration-linkedin-talent-hub-export.jpg)

## <a name="complete-onboarding-in-human-resources"></a><span data-ttu-id="81d2f-183">Completare l'onboarding in Human Resources</span><span class="sxs-lookup"><span data-stu-id="81d2f-183">Complete onboarding in Human Resources</span></span>

<span data-ttu-id="81d2f-184">I record dei candidati esportati da LinkedIn Talent Hub a Human Resources vengono visualizzati nella sezione **Candidati da assumere** della pagina **Gestione personale**.</span><span class="sxs-lookup"><span data-stu-id="81d2f-184">Candidate records that are exported from LinkedIn Talent Hub to Human Resources appear in the **Candidates to hire** section of the **Personnel management** page.</span></span>

1. <span data-ttu-id="81d2f-185">In Human Resources, aprire la pagina **Gestione personale**.</span><span class="sxs-lookup"><span data-stu-id="81d2f-185">In Human Resources, open the **Personnel management** page.</span></span>

2. <span data-ttu-id="81d2f-186">Nella sezione **Candidati da assumere** selezionare **Assumi** per il candidato selezionato.</span><span class="sxs-lookup"><span data-stu-id="81d2f-186">In the **Candidates to hire** section, select **Hire** for the selected candidate.</span></span>

3. <span data-ttu-id="81d2f-187">Nella finestra di dialogo **Assumi nuovo lavoratore** rivedere il record e aggiungere le informazioni richieste.</span><span class="sxs-lookup"><span data-stu-id="81d2f-187">In the **Hire new worker** dialog box, review the record, and add any required information.</span></span> <span data-ttu-id="81d2f-188">È possibile anche selezionare il numero di posizione per cui il candidato è stato assunto.</span><span class="sxs-lookup"><span data-stu-id="81d2f-188">You can also select the position number that the candidate has been hired for.</span></span>

<span data-ttu-id="81d2f-189">Dopo aver immesso le informazioni richieste, è possibile continuare con i processi standard per la creazione dei record dei dipendenti e l'onboarding dei dipendenti.</span><span class="sxs-lookup"><span data-stu-id="81d2f-189">After the required information has been entered, you can continue with your standard processes for creating employee records and onboarding employees.</span></span>

<span data-ttu-id="81d2f-190">I seguenti dettagli vengono importati e inclusi nel record del nuovo dipendente:</span><span class="sxs-lookup"><span data-stu-id="81d2f-190">The following details are imported and included on the new employee record:</span></span>

- <span data-ttu-id="81d2f-191">Nome</span><span class="sxs-lookup"><span data-stu-id="81d2f-191">First name</span></span>
- <span data-ttu-id="81d2f-192">Cognome</span><span class="sxs-lookup"><span data-stu-id="81d2f-192">Last name</span></span>
- <span data-ttu-id="81d2f-193">Data di inizio impiego</span><span class="sxs-lookup"><span data-stu-id="81d2f-193">Employment start date</span></span>
- <span data-ttu-id="81d2f-194">Indirizzo di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="81d2f-194">Email address</span></span>
- <span data-ttu-id="81d2f-195">Numero di telefono</span><span class="sxs-lookup"><span data-stu-id="81d2f-195">Phone number</span></span>

## <a name="see-also"></a><span data-ttu-id="81d2f-196">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="81d2f-196">See also</span></span>

[<span data-ttu-id="81d2f-197">Configurare le entità virtuali di Common Data Service</span><span class="sxs-lookup"><span data-stu-id="81d2f-197">Configure Common Data Service virtual entities</span></span>](./hr-admin-integration-common-data-service-virtual-entities.md)<br>
[<span data-ttu-id="81d2f-198">Che cos'è Common Data Service?</span><span class="sxs-lookup"><span data-stu-id="81d2f-198">What is Common Data Service?</span></span>](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro)
