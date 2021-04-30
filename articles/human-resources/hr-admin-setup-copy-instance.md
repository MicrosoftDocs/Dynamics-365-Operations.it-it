---
title: Copiare un'istanza
description: È possibile utilizzare Microsoft Dynamics Lifecycle Services (LCS) per copiare un database di Microsoft Dynamics 365 Human Resources in un ambiente sandbox.
author: andreabichsel
ms.date: 07/22/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SystemAdministrationWorkspaceForm
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 44df05083cd3c91e5dcbdb3062665c2145d92a7e
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2021
ms.locfileid: "5889814"
---
# <a name="copy-an-instance"></a><span data-ttu-id="123da-103">Copiare un'istanza</span><span class="sxs-lookup"><span data-stu-id="123da-103">Copy an instance</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="123da-104">È possibile utilizzare Microsoft Dynamics Lifecycle Services (LCS) per copiare un database di Microsoft Dynamics 365 Human Resources in un ambiente sandbox.</span><span class="sxs-lookup"><span data-stu-id="123da-104">You can use Microsoft Dynamics Lifecycle Services (LCS) to copy a Microsoft Dynamics 365 Human Resources database to a sandbox environment.</span></span> <span data-ttu-id="123da-105">Se è disponibile un altro ambiente sandbox, è anche possibile copiare il database da tale ambiente in un ambiente sandbox di destinazione.</span><span class="sxs-lookup"><span data-stu-id="123da-105">If you have another sandbox environment, you can also copy the database from that environment to a targeted sandbox environment.</span></span>

<span data-ttu-id="123da-106">Per copiare un'istanza, tenere presente i seguenti suggerimenti:</span><span class="sxs-lookup"><span data-stu-id="123da-106">To copy an instance, keep the following tips in mind:</span></span>

- <span data-ttu-id="123da-107">L'istanza di Human Resources che si desidera sovrascrivere deve essere un ambiente sandbox.</span><span class="sxs-lookup"><span data-stu-id="123da-107">The Human Resources instance you want to overwrite must be a sandbox environment.</span></span>

- <span data-ttu-id="123da-108">Gli ambienti utilizzati per la copia devono essere nella stessa area.</span><span class="sxs-lookup"><span data-stu-id="123da-108">The environments you're copying from and to must be in the same region.</span></span> <span data-ttu-id="123da-109">Non è possibile copiare da un'area in un'altra area.</span><span class="sxs-lookup"><span data-stu-id="123da-109">You can't copy across regions.</span></span>

- <span data-ttu-id="123da-110">È necessario essere un amministratore nell'ambiente di destinazione in modo da potervi accedere dopo aver copiato l'istanza.</span><span class="sxs-lookup"><span data-stu-id="123da-110">You must be an Administrator in the target environment so you can sign into it after copying the instance.</span></span>

- <span data-ttu-id="123da-111">Quando si copia il database di Human Resources, non si copiano gli elementi (app o dati) contenuti in un ambiente Microsoft Power Apps.</span><span class="sxs-lookup"><span data-stu-id="123da-111">When you copy the Human Resources database, you don't copy the elements (apps or data) that are contained in a Microsoft Power Apps environment.</span></span> <span data-ttu-id="123da-112">Per informazioni su come copiare elementi in un ambiente Power Apps, vedere [Copiare un ambiente](/power-platform/admin/copy-environment).</span><span class="sxs-lookup"><span data-stu-id="123da-112">For information about how to copy elements in a Power Apps environment, see [Copy an environment](/power-platform/admin/copy-environment).</span></span> <span data-ttu-id="123da-113">L'ambiente Power Apps che si desidera sovrascrivere deve essere un ambiente sandbox.</span><span class="sxs-lookup"><span data-stu-id="123da-113">The Power Apps environment you want to overwrite must be a sandbox environment.</span></span> <span data-ttu-id="123da-114">È necessario essere un amministratore tenant globale per modificare un ambiente di produzione Power Apps in un ambiente sandbox.</span><span class="sxs-lookup"><span data-stu-id="123da-114">You must be a global tenant admin to change a Power Apps production environment to a sandbox environment.</span></span> <span data-ttu-id="123da-115">Per ulteriori informazioni sulla modifica di un ambiente Power Apps, vedere [Passare a un'altra istanza](/dynamics365/admin/switch-instance).</span><span class="sxs-lookup"><span data-stu-id="123da-115">For more information about changing a Power Apps environment, see [Switch an instance](/dynamics365/admin/switch-instance).</span></span>

- <span data-ttu-id="123da-116">Se si copia un'istanza nell'ambiente sandbox e si desidera integrare l'ambiente sandbox con Dataverse, è necessario riapplicare i campi personalizzati alle tabelle Dataverse.</span><span class="sxs-lookup"><span data-stu-id="123da-116">If you copy an instance into your sandbox environment and want to integrate your sandbox environment with Dataverse, you must reapply custom fields to Dataverse tables.</span></span> <span data-ttu-id="123da-117">Vedere [Applicare campi personalizzati a Dataverse](hr-admin-setup-copy-instance.md?apply-custom-fields-to-common-data-service).</span><span class="sxs-lookup"><span data-stu-id="123da-117">See [Apply custom fields to Dataverse](hr-admin-setup-copy-instance.md?apply-custom-fields-to-common-data-service).</span></span>

## <a name="effects-of-copying-a-human-resources-database"></a><span data-ttu-id="123da-118">Effetti della copia di un database di Human Resources</span><span class="sxs-lookup"><span data-stu-id="123da-118">Effects of copying a Human Resources database</span></span>

<span data-ttu-id="123da-119">I seguenti eventi si verificano quando si copia un database di Human Resources:</span><span class="sxs-lookup"><span data-stu-id="123da-119">The following events occur when you copy a Human Resources database:</span></span>

- <span data-ttu-id="123da-120">Il processo di copia cancella il database esistente nell'ambiente di destinazione.</span><span class="sxs-lookup"><span data-stu-id="123da-120">The copy process erases the existing database in the target environment.</span></span> <span data-ttu-id="123da-121">Una volta completato il processo di copia, non è possibile ripristinare il database esistente.</span><span class="sxs-lookup"><span data-stu-id="123da-121">After the copy process is completed, you can't recover the existing database.</span></span>

- <span data-ttu-id="123da-122">L'ambiente di destinazione non sarà disponibile fino al completamento del processo di copia.</span><span class="sxs-lookup"><span data-stu-id="123da-122">The target environment will be unavailable until the copy process is completed.</span></span>

- <span data-ttu-id="123da-123">I documenti nell'archivio Blob di Microsoft Azure non vengono copiati da un ambiente all'altro.</span><span class="sxs-lookup"><span data-stu-id="123da-123">Documents in Microsoft Azure Blob storage aren't copied from one environment to another.</span></span> <span data-ttu-id="123da-124">Di conseguenza, tutti i documenti e i modelli allegati non verranno copiati e rimarranno nell'ambiente di origine.</span><span class="sxs-lookup"><span data-stu-id="123da-124">As a result, any documents and templates that are attached won't be copied and will remain in the source environment.</span></span>

- <span data-ttu-id="123da-125">Tutti gli utenti tranne l'utente amministratore e altri account utente del servizio interno non saranno disponibili.</span><span class="sxs-lookup"><span data-stu-id="123da-125">All users except the Admin user and other internal service user accounts will be unavailable.</span></span> <span data-ttu-id="123da-126">L'utente amministratore può eliminare o offuscare i dati prima di autorizzare altri utenti nel sistema.</span><span class="sxs-lookup"><span data-stu-id="123da-126">The Admin user can delete or obfuscate data before other users are allowed back into the system.</span></span>

- <span data-ttu-id="123da-127">L'utente amministratore deve apportare le modifiche alla configurazione necessarie, come la riconnessione di endpoint di integrazione a servizi o URL specifici.</span><span class="sxs-lookup"><span data-stu-id="123da-127">The Admin user must make required configuration changes, such as reconnecting integration endpoints to specific services or URLs.</span></span>

## <a name="copy-the-human-resources-database"></a><span data-ttu-id="123da-128">Copiare il database di Human Resources</span><span class="sxs-lookup"><span data-stu-id="123da-128">Copy the Human Resources database</span></span>

<span data-ttu-id="123da-129">Per completare questa attività, innanzi tutto copiare un'istanza, quindi accedere all'interfaccia di amministrazione di Microsoft Power Platform per copiare il proprio ambiente Power Apps.</span><span class="sxs-lookup"><span data-stu-id="123da-129">To complete this task, you first copy an instance, and then sign in to the Microsoft Power Platform Admin Center to copy your Power Apps environment.</span></span>

> [!WARNING]
> <span data-ttu-id="123da-130">Quando si copia un'istanza, il database viene cancellato nell'istanza di destinazione.</span><span class="sxs-lookup"><span data-stu-id="123da-130">When you copy an instance, the database is erased in the target instance.</span></span> <span data-ttu-id="123da-131">L'istanza di destinazione non è disponibile durante questo processo.</span><span class="sxs-lookup"><span data-stu-id="123da-131">The target instance is unavailable during this process.</span></span>

1. <span data-ttu-id="123da-132">Accedere a LCS e selezionare il progetto LCS che contiene l'istanza che si desidera copiare.</span><span class="sxs-lookup"><span data-stu-id="123da-132">Sign in to LCS, and select the LCS project that contains the instance that you want to copy.</span></span>

2. <span data-ttu-id="123da-133">Nel progetto LCS selezionare il riquadro **Gestione app Human Resources**.</span><span class="sxs-lookup"><span data-stu-id="123da-133">In your LCS project, select the **Human Resources App Management** tile.</span></span>

3. <span data-ttu-id="123da-134">Selezionare l'istanza da copiare, quindi selezionare **Copia**.</span><span class="sxs-lookup"><span data-stu-id="123da-134">Select the instance to copy, and then select **Copy**.</span></span>

4. <span data-ttu-id="123da-135">Nel riquadro attività **Copia un'istanza**, selezionare l'istanza da sovrascrivere, quindi selezionare **Copia**.</span><span class="sxs-lookup"><span data-stu-id="123da-135">In the **Copy an instance** task pane, select the instance to overwrite, and then select **Copy**.</span></span> <span data-ttu-id="123da-136">Attendere che il valore di **Stato copia** diventi **Completata**.</span><span class="sxs-lookup"><span data-stu-id="123da-136">Wait for the value of the **Copy status** field to be updated to **Completed**.</span></span>

   ![[<span data-ttu-id="123da-137">Selezionare l'istanza da sovrascrivere</span><span class="sxs-lookup"><span data-stu-id="123da-137">Select instance to overwrite</span></span>](./media/copy-instance-select-target-instance.png)](./media/copy-instance-select-target-instance.png)

5. <span data-ttu-id="123da-138">Selezionare **Power Platform** e accedere all'interfaccia di amministrazione di Microsoft Power Platform.</span><span class="sxs-lookup"><span data-stu-id="123da-138">Select **Power Platform**, and sign in to the Microsoft Power Platform Admin Center.</span></span>

   ![[<span data-ttu-id="123da-139">Selezionare Power Platform</span><span class="sxs-lookup"><span data-stu-id="123da-139">Select Power Platform</span></span>](./media/copy-instance-select-power-platform.png)](./media/copy-instance-select-power-platform.png)

6. <span data-ttu-id="123da-140">Selezionare l'ambiente Power Apps da copiare, quindi selezionare **Copia**.</span><span class="sxs-lookup"><span data-stu-id="123da-140">Select the Power Apps environment to copy, and then select **Copy**.</span></span>

7. <span data-ttu-id="123da-141">Al termine del processo di copia, accedere all'istanza di destinazione e abilitare l'integrazione di Dataverse.</span><span class="sxs-lookup"><span data-stu-id="123da-141">When the copy process is completed, sign in to the target instance, and enable Dataverse integration.</span></span> <span data-ttu-id="123da-142">Per ulteriori informazioni e istruzioni, vedere [Configurare l'integrazione di Dataverse](./hr-admin-integration-common-data-service.md).</span><span class="sxs-lookup"><span data-stu-id="123da-142">For more information and instructions, see [Configure Dataverse integration](./hr-admin-integration-common-data-service.md).</span></span>

## <a name="data-elements-and-statuses"></a><span data-ttu-id="123da-143">Stati ed elementi di dati</span><span class="sxs-lookup"><span data-stu-id="123da-143">Data elements and statuses</span></span>

<span data-ttu-id="123da-144">I seguenti elementi di dati non vengono copiati quando si copia un'istanza di Human Resources.</span><span class="sxs-lookup"><span data-stu-id="123da-144">The following data elements aren't copied when you copy a Human Resources instance:</span></span>

- <span data-ttu-id="123da-145">Indirizzi e-mail nella tabella **LogisticsElectronicAddress**</span><span class="sxs-lookup"><span data-stu-id="123da-145">Email addresses in the **LogisticsElectronicAddress** table</span></span>

- <span data-ttu-id="123da-146">Lo storico dei processi batch nelle tabelle **BatchJobHistory**, **BatchHistory** e **BatchConstraintHistory**</span><span class="sxs-lookup"><span data-stu-id="123da-146">The batch job history in the **BatchJobHistory**, **BatchHistory**, and **BatchConstraintHistory** tables</span></span>

- <span data-ttu-id="123da-147">La password SMTP (Simple Mail Transfer Protocol) nella tabella **SysEmailSMTPPassword**</span><span class="sxs-lookup"><span data-stu-id="123da-147">The Simple Mail Transfer Protocol (SMTP) password in the **SysEmailSMTPPassword** table</span></span>

- <span data-ttu-id="123da-148">Il relay server SMTP nella tabella **SysEmailParameters**</span><span class="sxs-lookup"><span data-stu-id="123da-148">The SMTP Relay server in the **SysEmailParameters** table</span></span>

- <span data-ttu-id="123da-149">Impostazioni di Gestione stampa nelle tabelle **PrintMgmtSettings** e **PrintMgmtDocInstance**</span><span class="sxs-lookup"><span data-stu-id="123da-149">Print Management settings in the **PrintMgmtSettings** and **PrintMgmtDocInstance** tables</span></span>

- <span data-ttu-id="123da-150">Record specifici dell'ambiente nelle tabelle **SysServerConfig**, **SysServerSessions**, **SysCorpNetPrinters**, **SysClientSessions**, **BatchServerConfig** e **BatchServerGroup**</span><span class="sxs-lookup"><span data-stu-id="123da-150">Environment-specific records in the **SysServerConfig**, **SysServerSessions**, **SysCorpNetPrinters**, **SysClientSessions**, **BatchServerConfig**, and **BatchServerGroup** tables</span></span>

- <span data-ttu-id="123da-151">Allegati a documenti nella tabella DocuValue.</span><span class="sxs-lookup"><span data-stu-id="123da-151">Document attachments in the DocuValue table.</span></span> <span data-ttu-id="123da-152">Questi allegati includono qualsiasi modello Microsoft Office che è stato sovrascritto nell'ambiente di origine</span><span class="sxs-lookup"><span data-stu-id="123da-152">These attachments include any Microsoft Office templates that were overwritten in the source environment</span></span>

- <span data-ttu-id="123da-153">La stringa di connessione nella tabella **PersonnelIntegrationConfiguration**</span><span class="sxs-lookup"><span data-stu-id="123da-153">The connection string in the **PersonnelIntegrationConfiguration** table</span></span>

<span data-ttu-id="123da-154">Alcuni di questi elementi non vengono copiati perché sono specifici dell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="123da-154">Some of these elements aren't copied because they're environment-specific.</span></span> <span data-ttu-id="123da-155">Alcuni esempi sono i record **BatchServerConfig** e **SysCorpNetPrinters**.</span><span class="sxs-lookup"><span data-stu-id="123da-155">Examples include **BatchServerConfig** and **SysCorpNetPrinters** records.</span></span> <span data-ttu-id="123da-156">Altri elementi non vengono copiati a causa del volume dei ticket di supporto.</span><span class="sxs-lookup"><span data-stu-id="123da-156">Other elements aren't copied because of the volume of support tickets.</span></span> <span data-ttu-id="123da-157">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="123da-157">For example:</span></span>

- <span data-ttu-id="123da-158">È possibile che vengano inviati messaggi di posta elettronica duplicati perché SMTP è ancora abilitato nell'ambiente di test di accettazione dell'utente (sandbox).</span><span class="sxs-lookup"><span data-stu-id="123da-158">Duplicate emails might be sent because SMTP is still enabled in the user acceptance testing (sandbox) environment.</span></span>

- <span data-ttu-id="123da-159">È possibile che vengano inviati messaggi di integrazione non validi perché i processi batch sono ancora abilitati.</span><span class="sxs-lookup"><span data-stu-id="123da-159">Invalid integration messages might be sent because batch jobs are still enabled.</span></span>

- <span data-ttu-id="123da-160">Gli utenti potrebbero essere abilitati prima che gli amministratori possano eseguire azioni di pulizia post-aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="123da-160">Users might be enabled before admins can perform post-refresh cleanup actions.</span></span>

<span data-ttu-id="123da-161">Inoltre, i seguenti stati cambiano quando si copia un'istanza:</span><span class="sxs-lookup"><span data-stu-id="123da-161">Also, the following statuses change when you copy an instance:</span></span>

- <span data-ttu-id="123da-162">Tutti gli utenti tranne l'utente amministratore sono impostati su **Disabilitato**.</span><span class="sxs-lookup"><span data-stu-id="123da-162">All users except Admin are set to **Disabled**.</span></span>

- <span data-ttu-id="123da-163">Tutti i processi batch, ad eccezione di alcuni processi di sistema, sono impostati su **Trattenuto**.</span><span class="sxs-lookup"><span data-stu-id="123da-163">All batch jobs, except for some system jobs, are set to **Withhold**.</span></span>

## <a name="environment-admin"></a><span data-ttu-id="123da-164">Amministratore di ambiente</span><span class="sxs-lookup"><span data-stu-id="123da-164">Environment admin</span></span>

<span data-ttu-id="123da-165">Tutti gli utenti nell'ambiente sandbox di destinazione, inclusi gli amministratori, vengono sostituiti dagli utenti dell'ambiente di origine.</span><span class="sxs-lookup"><span data-stu-id="123da-165">All users in the target sandbox environment, including Administrators, are replaced by the users of the source environment.</span></span> <span data-ttu-id="123da-166">Prima di copiare un'istanza, assicurarsi di essere un amministratore nell'ambiente di origine.</span><span class="sxs-lookup"><span data-stu-id="123da-166">Before you copy an instance, be sure that you're an Administrator in the source environment.</span></span> <span data-ttu-id="123da-167">In caso contrario, non è possibile accedere all'ambiente sandbox di destinazione al termine della copia.</span><span class="sxs-lookup"><span data-stu-id="123da-167">If you aren't, you can't sign in to the target sandbox environment after the copy has completed.</span></span>

<span data-ttu-id="123da-168">Tutti gli utenti non amministratori nell'ambiente sandbox di destinazione sono disabilitati per impedire accessi indesiderati nell'ambiente sandbox.</span><span class="sxs-lookup"><span data-stu-id="123da-168">All non-Administrator users in the target sandbox environment are disabled to prevent unwanted sign-ins in the sandbox environment.</span></span> <span data-ttu-id="123da-169">Gli amministratori possono riabilitare gli utenti se necessario.</span><span class="sxs-lookup"><span data-stu-id="123da-169">Administrators can reenable users if needed.</span></span>

## <a name="apply-custom-fields-to-dataverse"></a><span data-ttu-id="123da-170">Applicare campi personalizzati a Dataverse</span><span class="sxs-lookup"><span data-stu-id="123da-170">Apply custom fields to Dataverse</span></span>

<span data-ttu-id="123da-171">Se si copia un'istanza nell'ambiente sandbox e si desidera integrare l'ambiente sandbox con Dataverse, è necessario riapplicare i campi personalizzati alle tabelle Dataverse.</span><span class="sxs-lookup"><span data-stu-id="123da-171">If you copy an instance into your sandbox environment and want to integrate your sandbox environment with Dataverse, you must reapply custom fields to Dataverse tables.</span></span>

<span data-ttu-id="123da-172">Per ogni campo personalizzato esposto nelle tabelle Dataverse, eseguire le seguenti operazioni:</span><span class="sxs-lookup"><span data-stu-id="123da-172">For each custom field that's exposed on Dataverse tables, do the following steps:</span></span>

1. <span data-ttu-id="123da-173">Andare al campo personalizzato e selezionare **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="123da-173">Go to the custom field and select **Edit**.</span></span>

2. <span data-ttu-id="123da-174">Deselezionare il campo **Abilitato** per ogni entità cdm_\* in cui è abilitato il campo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="123da-174">Unselect the **Enabled** field for each cdm_\* entity that the custom field is enabled on.</span></span>

3. <span data-ttu-id="123da-175">Selezionare **Applica modifiche**.</span><span class="sxs-lookup"><span data-stu-id="123da-175">Select **Apply Changes**.</span></span>

4. <span data-ttu-id="123da-176">Selezionare **Modifica** nuovamente.</span><span class="sxs-lookup"><span data-stu-id="123da-176">Select **Edit** again.</span></span>

5. <span data-ttu-id="123da-177">Selezionare il campo **Abilitato** per ogni entità cdm_\* in cui è abilitato il campo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="123da-177">Select the **Enabled** field for each cdm_\* entity that the custom field is enabled on.</span></span>

6. <span data-ttu-id="123da-178">Selezionare di nuovo **Applica modifiche**.</span><span class="sxs-lookup"><span data-stu-id="123da-178">Select **Apply Changes** again.</span></span>

<span data-ttu-id="123da-179">Il processo di deselezione, applicazione delle modifiche, riselezione e riapplicazione delle modifiche richiede l'aggiornamento dello schema in Dataverse per includere i campi personalizzati.</span><span class="sxs-lookup"><span data-stu-id="123da-179">The process of unselecting, applying changes, reselecting, and reapplying changes prompts the schema to update in Dataverse to include the custom fields.</span></span>

<span data-ttu-id="123da-180">Per ulteriori informazioni sui campi personalizzati, vedere [Creare e utilizzare campi personalizzati](../fin-ops-core/fin-ops/get-started/user-defined-fields.md).</span><span class="sxs-lookup"><span data-stu-id="123da-180">For more information about custom fields, see [Create and work with custom fields](../fin-ops-core/fin-ops/get-started/user-defined-fields.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="123da-181">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="123da-181">See also</span></span>

[<span data-ttu-id="123da-182">Provisioning di Human Resources</span><span class="sxs-lookup"><span data-stu-id="123da-182">Provision Human Resources</span></span>](hr-admin-setup-provision.md)</br>
[<span data-ttu-id="123da-183">Rimuovere un'istanza</span><span class="sxs-lookup"><span data-stu-id="123da-183">Remove an instance</span></span>](hr-admin-setup-remove-instance.md)</br>
[<span data-ttu-id="123da-184">Aggiornare un processo</span><span class="sxs-lookup"><span data-stu-id="123da-184">Update process</span></span>](hr-admin-setup-update-process.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]