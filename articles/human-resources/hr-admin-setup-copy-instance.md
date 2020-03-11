---
title: Copiare un'istanza
description: ''
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
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
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 0bbe325edb65cad0c1912e0a6ade559e5675dc58
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2020
ms.locfileid: "3009496"
---
# <a name="copy-an-instance"></a><span data-ttu-id="15534-102">Copiare un'istanza</span><span class="sxs-lookup"><span data-stu-id="15534-102">Copy an instance</span></span>

<span data-ttu-id="15534-103">È possibile utilizzare Microsoft Dynamics Lifecycle Services (LCS) per copiare un database di Microsoft Dynamics 365 Human Resources in un ambiente sandbox.</span><span class="sxs-lookup"><span data-stu-id="15534-103">You can use Microsoft Dynamics Lifecycle Services (LCS) to copy a Microsoft Dynamics 365 Human Resources database to a sandbox environment.</span></span> <span data-ttu-id="15534-104">Se è disponibile un altro ambiente sandbox, è anche possibile copiare il database da tale ambiente in un ambiente sandbox di destinazione.</span><span class="sxs-lookup"><span data-stu-id="15534-104">If you have another sandbox environment, you can also copy the database from that environment to a targeted sandbox environment.</span></span>

<span data-ttu-id="15534-105">Per copiare un'istanza:</span><span class="sxs-lookup"><span data-stu-id="15534-105">To copy an instance, you need to ensure the following:</span></span>

- <span data-ttu-id="15534-106">L'istanza di Human Resources che si desidera sovrascrivere deve essere un ambiente sandbox.</span><span class="sxs-lookup"><span data-stu-id="15534-106">The Human Resources instance you want to overwrite must be a sandbox environment.</span></span>

- <span data-ttu-id="15534-107">Gli ambienti utilizzati per la copia devono essere nella stessa area.</span><span class="sxs-lookup"><span data-stu-id="15534-107">The environments you are copying from and to must be in the same region.</span></span> <span data-ttu-id="15534-108">Non è possibile copiare da un'area in un'altra area.</span><span class="sxs-lookup"><span data-stu-id="15534-108">You can't copy across regions.</span></span>

- <span data-ttu-id="15534-109">È necessario essere un amministratore nell'ambiente di destinazione in modo da potervi accedere dopo aver copiato l'istanza.</span><span class="sxs-lookup"><span data-stu-id="15534-109">You must be an Administrator in the target environment so you can sign into it after copying the instance.</span></span>

- <span data-ttu-id="15534-110">Quando si copia il database di Human Resources, non si copiano gli elementi (app o dati) contenuti in un ambiente Microsoft PowerApps.</span><span class="sxs-lookup"><span data-stu-id="15534-110">When you copy the Human Resources database, you don't copy the elements (apps or data) that are contained in a Microsoft PowerApps environment.</span></span> <span data-ttu-id="15534-111">Per informazioni su come copiare elementi in un ambiente PowerApps, vedere [Copiare un ambiente](https://docs.microsoft.com/power-platform/admin/copy-environment).</span><span class="sxs-lookup"><span data-stu-id="15534-111">For information about how to copy elements in a PowerApps environment, see [Copy an environment](https://docs.microsoft.com/power-platform/admin/copy-environment).</span></span> <span data-ttu-id="15534-112">L'ambiente PowerApps che si desidera sovrascrivere deve essere un ambiente sandbox.</span><span class="sxs-lookup"><span data-stu-id="15534-112">The PowerApps environment you want to overwrite must be a sandbox environment.</span></span> <span data-ttu-id="15534-113">È necessario essere un amministratore tenant globale per modificare un ambiente di produzione PowerApps in un ambiente sandbox.</span><span class="sxs-lookup"><span data-stu-id="15534-113">You must be a global tenant admin to change a PowerApps production environment to a sandbox environment.</span></span> <span data-ttu-id="15534-114">Per ulteriori informazioni sulla modifica di un ambiente PowerApps, vedere [Passare a un'altra istanza](https://docs.microsoft.com/dynamics365/admin/switch-instance).</span><span class="sxs-lookup"><span data-stu-id="15534-114">For more information about changing a PowerApps environment, see [Switch an instance](https://docs.microsoft.com/dynamics365/admin/switch-instance).</span></span>

## <a name="effects-of-copying-a-human-resources-database"></a><span data-ttu-id="15534-115">Effetti della copia di un database di Human Resources</span><span class="sxs-lookup"><span data-stu-id="15534-115">Effects of copying a Human Resources database</span></span>

<span data-ttu-id="15534-116">I seguenti eventi si verificano quando si copia un database di Human Resources:</span><span class="sxs-lookup"><span data-stu-id="15534-116">The following events occur when you copy a Human Resources database:</span></span>

- <span data-ttu-id="15534-117">Il processo di copia cancella il database esistente nell'ambiente di destinazione.</span><span class="sxs-lookup"><span data-stu-id="15534-117">The copy process erases the existing database in the target environment.</span></span> <span data-ttu-id="15534-118">Una volta completato il processo di copia, non è possibile ripristinare il database esistente.</span><span class="sxs-lookup"><span data-stu-id="15534-118">After the copy process is completed, you can't recover the existing database.</span></span>

- <span data-ttu-id="15534-119">L'ambiente di destinazione non sarà disponibile fino al completamento del processo di copia.</span><span class="sxs-lookup"><span data-stu-id="15534-119">The target environment will be unavailable until the copy process is completed.</span></span>

- <span data-ttu-id="15534-120">I documenti nell'archivio Blob di Microsoft Azure non vengono copiati da un ambiente all'altro.</span><span class="sxs-lookup"><span data-stu-id="15534-120">Documents in Microsoft Azure Blob storage aren't copied from one environment to another.</span></span> <span data-ttu-id="15534-121">Pertanto, tutti i documenti e i modelli allegati non verranno copiati e rimarranno nell'ambiente di origine.</span><span class="sxs-lookup"><span data-stu-id="15534-121">Therefore, any documents and templates that are attached won't be copied and will remain in the source environment.</span></span>

- <span data-ttu-id="15534-122">Tutti gli utenti tranne l'utente amministratore e altri account utente del servizio interno non saranno disponibili.</span><span class="sxs-lookup"><span data-stu-id="15534-122">All users except the Admin user and other internal service user accounts will be unavailable.</span></span> <span data-ttu-id="15534-123">Pertanto, l'utente amministratore può eliminare o offuscare i dati prima di autorizzare altri utenti nel sistema.</span><span class="sxs-lookup"><span data-stu-id="15534-123">Therefore, the Admin user can delete or obfuscate data before other users are allowed back into the system.</span></span>

- <span data-ttu-id="15534-124">L'utente amministratore deve apportare le modifiche alla configurazione necessarie, come la riconnessione di endpoint di integrazione a servizi o URL specifici.</span><span class="sxs-lookup"><span data-stu-id="15534-124">The Admin user must make required configuration changes, such as reconnecting integration endpoints to specific services or URLs.</span></span>

## <a name="copy-the-human-resources-database"></a><span data-ttu-id="15534-125">Copiare il database di Human Resources</span><span class="sxs-lookup"><span data-stu-id="15534-125">Copy the Human Resources database</span></span>

<span data-ttu-id="15534-126">Per completare questa attività, innanzi tutto copiare un'istanza, quindi accedere all'interfaccia di amministrazione di Microsoft Power Platform per copiare il proprio ambiente PowerApps.</span><span class="sxs-lookup"><span data-stu-id="15534-126">To complete this task, you first copy an instance, and then sign in to the Microsoft Power Platform Admin Center to copy your PowerApps environment.</span></span>

> [!WARNING]
> <span data-ttu-id="15534-127">Quando si copia un'istanza, il database viene cancellato nell'istanza di destinazione.</span><span class="sxs-lookup"><span data-stu-id="15534-127">When you copy an instance, the database is erased in the target instance.</span></span> <span data-ttu-id="15534-128">L'istanza di destinazione non è disponibile durante questo processo.</span><span class="sxs-lookup"><span data-stu-id="15534-128">The target instance is unavailable during this process.</span></span>

1. <span data-ttu-id="15534-129">Accedere a LCS e selezionare il progetto LCS che contiene l'istanza che si desidera copiare.</span><span class="sxs-lookup"><span data-stu-id="15534-129">Sign in to LCS, and select the LCS project that contains the instance that you want to copy.</span></span>

2. <span data-ttu-id="15534-130">Nel progetto LCS selezionare il riquadro **Gestione app Human Resources**.</span><span class="sxs-lookup"><span data-stu-id="15534-130">In your LCS project, select the **Human Resources App Management** tile.</span></span>

3. <span data-ttu-id="15534-131">Selezionare l'istanza da copiare, quindi selezionare **Copia**.</span><span class="sxs-lookup"><span data-stu-id="15534-131">Select the instance to copy, and then select **Copy**.</span></span>

4. <span data-ttu-id="15534-132">Nel riquadro attività **Copia un'istanza**, selezionare l'istanza da sovrascrivere, quindi selezionare **Copia**.</span><span class="sxs-lookup"><span data-stu-id="15534-132">In the **Copy an instance** task pane, select the instance to overwrite, and then select **Copy**.</span></span> <span data-ttu-id="15534-133">Attendere che il valore di **Stato copia** diventi **Completata**.</span><span class="sxs-lookup"><span data-stu-id="15534-133">Wait for the value of the **Copy status** field to be updated to **Completed**.</span></span>

   ![[<span data-ttu-id="15534-134">Selezionare l'istanza da sovrascrivere</span><span class="sxs-lookup"><span data-stu-id="15534-134">Select instance to overwrite</span></span>](./media/copy-instance-select-target-instance.png)](./media/copy-instance-select-target-instance.png)

5. <span data-ttu-id="15534-135">Selezionare **Power Platform** e accedere all'interfaccia di amministrazione di Microsoft Power Platform.</span><span class="sxs-lookup"><span data-stu-id="15534-135">Select **Power Platform**, and sign in to the Microsoft Power Platform Admin Center.</span></span>

   ![[<span data-ttu-id="15534-136">Selezionare Power Platform</span><span class="sxs-lookup"><span data-stu-id="15534-136">Select Power Platform</span></span>](./media/copy-instance-select-power-platform.png)](./media/copy-instance-select-power-platform.png)

6. <span data-ttu-id="15534-137">Selezionare l'ambiente PowerApps da copiare, quindi selezionare **Copia**.</span><span class="sxs-lookup"><span data-stu-id="15534-137">Select the PowerApps environment to copy, and then select **Copy**.</span></span>

7. <span data-ttu-id="15534-138">Al termine del processo di copia, accedere all'istanza di destinazione e abilitare l'integrazione di Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="15534-138">When the copy process is completed, sign in to the target instance, and enable Common Data Service integration.</span></span> <span data-ttu-id="15534-139">Per ulteriori informazioni e istruzioni, vedere [Configurare l'integrazione di Common Data Service](https://docs.microsoft.com/dynamics365/talent/hr-common-data-service-integration).</span><span class="sxs-lookup"><span data-stu-id="15534-139">For more information and instructions, see [Configure Common Data Service integration](https://docs.microsoft.com/dynamics365/talent/hr-common-data-service-integration).</span></span>

## <a name="data-elements-and-statuses"></a><span data-ttu-id="15534-140">Stati ed elementi di dati</span><span class="sxs-lookup"><span data-stu-id="15534-140">Data elements and statuses</span></span>

<span data-ttu-id="15534-141">I seguenti elementi di dati non vengono copiati quando si copia un'istanza di Human Resources.</span><span class="sxs-lookup"><span data-stu-id="15534-141">The following data elements aren't copied when you copy a Human Resources instance:</span></span>

- <span data-ttu-id="15534-142">Indirizzi e-mail nella tabella **LogisticsElectronicAddress**</span><span class="sxs-lookup"><span data-stu-id="15534-142">Email addresses in the **LogisticsElectronicAddress** table</span></span>

- <span data-ttu-id="15534-143">Lo storico dei processi batch nelle tabelle **BatchJobHistory**, **BatchHistory** e **BatchConstraintHistory**</span><span class="sxs-lookup"><span data-stu-id="15534-143">The batch job history in the **BatchJobHistory**, **BatchHistory**, and **BatchConstraintHistory** tables</span></span>

- <span data-ttu-id="15534-144">La password SMTP (Simple Mail Transfer Protocol) nella tabella **SysEmailSMTPPassword**</span><span class="sxs-lookup"><span data-stu-id="15534-144">The Simple Mail Transfer Protocol (SMTP) password in the **SysEmailSMTPPassword** table</span></span>

- <span data-ttu-id="15534-145">Il relay server SMTP nella tabella **SysEmailParameters**</span><span class="sxs-lookup"><span data-stu-id="15534-145">The SMTP Relay server in the **SysEmailParameters** table</span></span>

- <span data-ttu-id="15534-146">Impostazioni di Gestione stampa nelle tabelle **PrintMgmtSettings** e **PrintMgmtDocInstance**</span><span class="sxs-lookup"><span data-stu-id="15534-146">Print Management settings in the **PrintMgmtSettings** and **PrintMgmtDocInstance** tables</span></span>

- <span data-ttu-id="15534-147">Record specifici dell'ambiente nelle tabelle **SysServerConfig**, **SysServerSessions**, **SysCorpNetPrinters**, **SysClientSessions**, **BatchServerConfig** e **BatchServerGroup**</span><span class="sxs-lookup"><span data-stu-id="15534-147">Environment-specific records in the **SysServerConfig**, **SysServerSessions**, **SysCorpNetPrinters**, **SysClientSessions**, **BatchServerConfig**, and **BatchServerGroup** tables</span></span>

- <span data-ttu-id="15534-148">Allegati a documenti nella tabella DocuValue.</span><span class="sxs-lookup"><span data-stu-id="15534-148">Document attachments in the DocuValue table.</span></span> <span data-ttu-id="15534-149">Questi allegati includono qualsiasi modello Microsoft Office che è stato sovrascritto nell'ambiente di origine</span><span class="sxs-lookup"><span data-stu-id="15534-149">These attachments include any Microsoft Office templates that were overwritten in the source environment</span></span>

- <span data-ttu-id="15534-150">La stringa di connessione nella tabella **PersonnelIntegrationConfiguration**</span><span class="sxs-lookup"><span data-stu-id="15534-150">The connection string in the **PersonnelIntegrationConfiguration** table</span></span>

<span data-ttu-id="15534-151">Alcuni di questi elementi non vengono copiati perché sono specifici dell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="15534-151">Some of these elements aren't copied because they are environment-specific.</span></span> <span data-ttu-id="15534-152">Alcuni esempi sono i record **BatchServerConfig** e **SysCorpNetPrinters**.</span><span class="sxs-lookup"><span data-stu-id="15534-152">Examples include **BatchServerConfig** and **SysCorpNetPrinters** records.</span></span> <span data-ttu-id="15534-153">Altri elementi non vengono copiati a causa del volume dei ticket di supporto.</span><span class="sxs-lookup"><span data-stu-id="15534-153">Other elements aren't copied because of the volume of support tickets.</span></span> <span data-ttu-id="15534-154">Ad esempio, messaggi e-mail duplicati potrebbero essere inviati in quanto SMTP è ancora abilitato nell'ambiente di test di accettazione utenti (sandbox), messaggi di integrazione non validi potrebbero essere inviati in quanto i processi batch sono ancora abilitati e gli utenti potrebbero essere abilitati prima che gli amministratori possano eseguire azioni di pulizia post aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="15534-154">For example, duplicate emails might be sent because SMTP is still enabled in the user acceptance testing (sandbox) environment, invalid integration messages might be sent because batch jobs are still enabled, and users might be enabled before admins can perform post-refresh cleanup actions.</span></span>

<span data-ttu-id="15534-155">Inoltre, i seguenti stati cambiano quando si copia un'istanza:</span><span class="sxs-lookup"><span data-stu-id="15534-155">In addition, the following statuses change when you copy an instance:</span></span>

- <span data-ttu-id="15534-156">Tutti gli utenti tranne l'utente amministratore sono impostati su **Disabilitato**.</span><span class="sxs-lookup"><span data-stu-id="15534-156">All users except Admin are set to **Disabled**.</span></span>

- <span data-ttu-id="15534-157">Tutti i processi batch, ad eccezione di alcuni processi di sistema, sono impostati su **Trattenuto**.</span><span class="sxs-lookup"><span data-stu-id="15534-157">All batch jobs, except for some system jobs, are set to **Withhold**.</span></span>

## <a name="environment-admin"></a><span data-ttu-id="15534-158">Amministratore di ambiente</span><span class="sxs-lookup"><span data-stu-id="15534-158">Environment admin</span></span>

<span data-ttu-id="15534-159">Tutti gli utenti nell'ambiente sandbox di destinazione, inclusi gli amministratori, vengono sostituiti dagli utenti dell'ambiente di origine.</span><span class="sxs-lookup"><span data-stu-id="15534-159">All users in the target sandbox environment, including Administrators, are replaced by the users of the source environment.</span></span> <span data-ttu-id="15534-160">Prima di copiare un'istanza, assicurarsi di essere un amministratore nell'ambiente di destinazione.</span><span class="sxs-lookup"><span data-stu-id="15534-160">Before you copy an instance, be sure that you're an Administrator in the target environment.</span></span> <span data-ttu-id="15534-161">In caso contrario, non sarà possibile accedere all'ambiente sandbox di destinazione al termine della copia.</span><span class="sxs-lookup"><span data-stu-id="15534-161">If you aren't, you won't be able to sign in to the target sandbox environment after the copy has completed.</span></span>

<span data-ttu-id="15534-162">Tutti gli utenti non amministratori nell'ambiente sandbox di destinazione sono disabilitati per impedire accessi indesiderati nell'ambiente sandbox.</span><span class="sxs-lookup"><span data-stu-id="15534-162">All non-Administrator users in the target sandbox environment are disabled to prevent unwanted sign-ins in the sandbox environment.</span></span> <span data-ttu-id="15534-163">Gli amministratori possono riabilitare gli utenti se necessario.</span><span class="sxs-lookup"><span data-stu-id="15534-163">Administrators can reenable users if needed.</span></span>