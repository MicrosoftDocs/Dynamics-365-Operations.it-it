---
title: Area di lavoro mobile per immissione ora progetto
description: In questo argomento vengono fornite informazioni sull'area di lavoro mobile per l'immissione di ore progetto. Questa area di lavoro consente agli utenti di immettere e salvare le ore dedicate a un progetto utilizzando il dispositivo mobile.
author: KimANelson
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 272101
ms.assetid: 4505f021-b9bb-4b87-be24-6bf0bd88ee60
ms.search.region: Global
ms.search.industry: Service industries
ms.author: knelson
ms.dyn365.ops.intro: Version 1611
ms.search.validFrom: 2016-11-30
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 8185be069a552105073958d5144ad402ddae6b9f
ms.contentlocale: it-it
ms.lasthandoff: 11/03/2017

---

# <a name="project-time-entry-mobile-workspace"></a><span data-ttu-id="e6456-104">Area di lavoro mobile per immissione ora progetto</span><span class="sxs-lookup"><span data-stu-id="e6456-104">Project time entry mobile workspace</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="e6456-105">In questo argomento vengono fornite informazioni sull'area di lavoro mobile **Immissione ora progetto**.</span><span class="sxs-lookup"><span data-stu-id="e6456-105">This topic provides information about the **Project time entry** mobile workspace.</span></span> <span data-ttu-id="e6456-106">Questa area di lavoro consente agli utenti di immettere e salvare le ore dedicate a un progetto utilizzando il dispositivo mobile.</span><span class="sxs-lookup"><span data-stu-id="e6456-106">This workspace lets users enter and save time against a project by using their mobile device.</span></span>

<span data-ttu-id="e6456-107">Questa area di lavoro mobile può essere utilizzata con l'app mobile Microsoft Dynamics 365 for Unified Operations.</span><span class="sxs-lookup"><span data-stu-id="e6456-107">This mobile workspace is intended to be used with the Microsoft Dynamics 365 for Unified Operations mobile app.</span></span> 

## <a name="overview"></a><span data-ttu-id="e6456-108">Panoramica</span><span class="sxs-lookup"><span data-stu-id="e6456-108">Overview</span></span>
<span data-ttu-id="e6456-109">Durante il lavoro giornaliero, le risorse di progetto si trovano spesso sul campo o in viaggio.</span><span class="sxs-lookup"><span data-stu-id="e6456-109">As part of their daily work, project resources are often on-site or traveling.</span></span> <span data-ttu-id="e6456-110">L'area di lavoro mobile **immissione ora progetto** consente agli utenti di immettere le relative ore fatturabili o non fatturabili a fronte di un progetto nel dispositivo mobile scelto.</span><span class="sxs-lookup"><span data-stu-id="e6456-110">The **Project time entry** mobile workspace lets users enter their billable or non-billable time against a project on the mobile device of their choice.</span></span> <span data-ttu-id="e6456-111">Di conseguenza, le risorse di progetto possono registrare voci ore in qualsiasi momento e ovunque.</span><span class="sxs-lookup"><span data-stu-id="e6456-111">Therefore, project resources can record time entries anytime and anywhere.</span></span> <span data-ttu-id="e6456-112">È inoltre possibile visualizzare le voci ore già registrate.</span><span class="sxs-lookup"><span data-stu-id="e6456-112">They can also view time entries that have already been recorded.</span></span> 

<span data-ttu-id="e6456-113">In particolare, nell'area di lavoro mobile **Immissione ora progetto**, gli utenti possono eseguire queste attività:</span><span class="sxs-lookup"><span data-stu-id="e6456-113">Specifically, in the **Project time entry** mobile workspace, users can perform these tasks:</span></span>

-   <span data-ttu-id="e6456-114">Per qualsiasi data selezionata, immettere il numero di ore impiegate in un'attività specifica.</span><span class="sxs-lookup"><span data-stu-id="e6456-114">For any selected date, enter the number of hours that you spent on a specific task.</span></span>
-   <span data-ttu-id="e6456-115">Ricerca per nome o cliente del progetto per individuare il progetto per cui si desidera specificare l'orario.</span><span class="sxs-lookup"><span data-stu-id="e6456-115">Search by project name or customer to find the project to enter time for.</span></span>
-   <span data-ttu-id="e6456-116">Specificare la categoria e l'attività delle ore dedicate.</span><span class="sxs-lookup"><span data-stu-id="e6456-116">Specify the category and activity for the time that you spent.</span></span>
-   <span data-ttu-id="e6456-117">Registrare le ore come fatturabili o non fatturabili per il progetto.</span><span class="sxs-lookup"><span data-stu-id="e6456-117">Record the time as billable or non-billable for the project.</span></span>
-   <span data-ttu-id="e6456-118">Immettere qualsiasi commento interno o esterno facoltativo.</span><span class="sxs-lookup"><span data-stu-id="e6456-118">Optionally enter any external or internal comments.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e6456-119">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="e6456-119">Prerequisites</span></span>
<span data-ttu-id="e6456-120">I prerequisiti variano a seconda della versione di Microsoft Dynamics 365 che è stata installata nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="e6456-120">The prerequisites differ, based on the version of Microsoft Dynamics 365 that has been deployed for your organization.</span></span>

### <a name="prerequisites-if-you-use-microsoft-dynamics-365-for-finance-and-operations-enterprise-edition-july-2017"></a><span data-ttu-id="e6456-121">Prerequisiti se si usa l'Aggiornamento di Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (luglio 2017)</span><span class="sxs-lookup"><span data-stu-id="e6456-121">Prerequisites if you use Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (July 2017)</span></span> 
<span data-ttu-id="e6456-122">Se nell'organizzazione è stato distribuito Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (luglio 2017), l'amministratore di sistema deve pubblicare l'area di lavoro mobile **Immissione ora progetto**.</span><span class="sxs-lookup"><span data-stu-id="e6456-122">If Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (July 2017) has been deployed for your organization, the system administrator must publish the **Project time entry** mobile workspace.</span></span> <span data-ttu-id="e6456-123">Per istruzioni, vedere [Pubblicare un'area di lavoro mobile](../../dev-itpro/mobile-apps/publish-mobile-workspace.md).</span><span class="sxs-lookup"><span data-stu-id="e6456-123">For instructions, see [Publish a mobile workspace](../../dev-itpro/mobile-apps/publish-mobile-workspace.md).</span></span>

### <a name="prerequisites-if-you-use-microsoft-dynamics-365-for-operations-version-1611-with-platform-update-3-or-later"></a><span data-ttu-id="e6456-124">Prerequisiti se si usa Microsoft Dynamics 365 for Operations versione 1611 con Aggiornamento piattaforma 3 o versione successiva</span><span class="sxs-lookup"><span data-stu-id="e6456-124">Prerequisites if you use Microsoft Dynamics 365 for Operations version 1611 with platform update 3 or later</span></span>
<span data-ttu-id="e6456-125">Se nell'organizzazione è stato distribuito Microsoft Dynamics 365 for Operations versione 1611 con Aggiornamento piattaforma 3 o versione successiva, l'amministratore di sistema deve soddisfare i prerequisiti seguenti.</span><span class="sxs-lookup"><span data-stu-id="e6456-125">If Microsoft Dynamics 365 for Operations version 1611 with platform update 3 or later has been deployed for your organization, the system administrator must complete the following prerequisites.</span></span> 

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="e6456-126">Prerequisito</span><span class="sxs-lookup"><span data-stu-id="e6456-126">Prerequisite</span></span></th>
<th><span data-ttu-id="e6456-127">Ruolo</span><span class="sxs-lookup"><span data-stu-id="e6456-127">Role</span></span></th>
<th><span data-ttu-id="e6456-128">descrizione</span><span class="sxs-lookup"><span data-stu-id="e6456-128">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">

<td><span data-ttu-id="e6456-129">Implementare l'articoloo KB 4018050.</span><span class="sxs-lookup"><span data-stu-id="e6456-129">Implement KB 4018050.</span></span></td>
<td><span data-ttu-id="e6456-130">Amministratore di sistema</span><span class="sxs-lookup"><span data-stu-id="e6456-130">System administrator</span></span></td>
<td><span data-ttu-id="e6456-131">L'articolo KB 4018050 è un aggiornamento X++ o aggiornamento rapido dei metadati contenente l'area di lavoro mobile <strong>Immissione ora progetto</strong>.</span><span class="sxs-lookup"><span data-stu-id="e6456-131">KB 4018050 is an X++ update or metadata hotfix that contains the <strong>Project time entry</strong> mobile workspace.</span></span> <span data-ttu-id="e6456-132">Per implementare l'articolo KB 4018050, l'amministratore di sistema deve completare i passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="e6456-132">To implement KB 4018050, your system administrator must follow these steps.</span></span>
<ol>
<li><span data-ttu-id="e6456-133"><a href="../../dev-itpro/migration-upgrade/download-hotfix-lcs.md">Scaricare l'hotfix metadati da Microsoft Dynamics Lifecycle Services (LCS)</a>.</span><span class="sxs-lookup"><span data-stu-id="e6456-133"><a href="../../dev-itpro/migration-upgrade/download-hotfix-lcs.md">Download the metadata hotfix from Microsoft Dynamics Lifecycle Services (LCS)</a>.</span></span></li>
<li><span data-ttu-id="e6456-134"><a href="../../dev-itpro/migration-upgrade/install-metadata-hotfix-package.md">Installare l'aggiornamento rapido dei metadati</a>.</span><span class="sxs-lookup"><span data-stu-id="e6456-134"><a href="../../dev-itpro/migration-upgrade/install-metadata-hotfix-package.md">Install the metadata hotfix</a>.</span></span></li>
<li><span data-ttu-id="e6456-135"><a href="../../dev-itpro/deployment/create-apply-deployable-package.md">Creare un pacchetto distribuibile</a> contenente i modelli <strong>ApplicationSuite</strong> e <strong>ProjectMobile</strong> e quindi caricare il pacchetto distribuibile in LCS.</span><span class="sxs-lookup"><span data-stu-id="e6456-135"><a href="../../dev-itpro/deployment/create-apply-deployable-package.md">Create a deployable package</a> that contains the <strong>ApplicationSuite</strong> and <strong>ProjectMobile</strong> models, and then upload the deployable package to LCS.</span></span></li>
<li><span data-ttu-id="e6456-136"><a href="../../dev-itpro/deployment/apply-deployable-package-system.md">Applicare il pacchetto distribuibile</a>.</span><span class="sxs-lookup"><span data-stu-id="e6456-136"><a href="../../dev-itpro/deployment/apply-deployable-package-system.md">Apply the deployable package</a>.</span></span></li>

</ol></td>
</tr>
<tr class="even">
<td><span data-ttu-id="e6456-137">Pubblicare l'area di lavoro mobile <strong>Immissione ora progetto</strong>.</span><span class="sxs-lookup"><span data-stu-id="e6456-137">Publish the <strong>Project time entry</strong> mobile workspace.</span></span></td>
<td><span data-ttu-id="e6456-138">Amministratore di sistema</span><span class="sxs-lookup"><span data-stu-id="e6456-138">System administrator</span></span></td>
<td><span data-ttu-id="e6456-139">Vedere <a href="../../dev-itpro/mobile-apps/publish-mobile-workspace.md">Pubblicare un'area di lavoro mobile</a>.</span><span class="sxs-lookup"><span data-stu-id="e6456-139">See <a href="../../dev-itpro/mobile-apps/publish-mobile-workspace.md">Publish a mobile workspace</a>.</span></span></td>
</tr>
</tbody>
</table>

## <a name="download-and-install-the-mobile-app"></a><span data-ttu-id="e6456-140">Scaricare e installare l'app mobile</span><span class="sxs-lookup"><span data-stu-id="e6456-140">Download and install the mobile app</span></span>

<span data-ttu-id="e6456-141">Scaricare e installare l'app mobile Dynamics 365 for Unified Operations:</span><span class="sxs-lookup"><span data-stu-id="e6456-141">Download and install the Dynamics 365 for Unified Operations mobile app:</span></span>

-   [<span data-ttu-id="e6456-142">Per telefoni Android</span><span class="sxs-lookup"><span data-stu-id="e6456-142">For Android phones</span></span>](https://go.microsoft.com/fwlink/?linkid=850662)
-   [<span data-ttu-id="e6456-143">Per iPhone</span><span class="sxs-lookup"><span data-stu-id="e6456-143">For iPhones</span></span>](https://go.microsoft.com/fwlink/?linkid=850663)

## <a name="sign-in-to-the-mobile-app"></a><span data-ttu-id="e6456-144">Accedere all'app mobile</span><span class="sxs-lookup"><span data-stu-id="e6456-144">Sign in to the mobile app</span></span>
1.  <span data-ttu-id="e6456-145">Avviare l'app sul dispositivo mobile.</span><span class="sxs-lookup"><span data-stu-id="e6456-145">Start the app on your mobile device.</span></span>
2.  <span data-ttu-id="e6456-146">Immettere il proprio URL Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="e6456-146">Enter your Dynamics 365 URL.</span></span>
3.  <span data-ttu-id="e6456-147">La prima volta che si accede viene richiesto di inserire il proprio nome utente e la password.</span><span class="sxs-lookup"><span data-stu-id="e6456-147">The first time that you sign in, you're prompted for your user name and password.</span></span> <span data-ttu-id="e6456-148">Immettere le proprie credenziali.</span><span class="sxs-lookup"><span data-stu-id="e6456-148">Enter your credentials.</span></span>
4.  <span data-ttu-id="e6456-149">Dopo avere effettuato l'accesso, vengono visualizzate le aree di lavoro disponibili per la società.</span><span class="sxs-lookup"><span data-stu-id="e6456-149">After you sign in, the available workspaces for your company are shown.</span></span> <span data-ttu-id="e6456-150">Nota: se l'amministratore di sistema pubblica una nuova area di lavoro in seguito, è necessario aggiornare l'elenco delle aree di lavoro mobili.</span><span class="sxs-lookup"><span data-stu-id="e6456-150">Note that if your system administrator publishes a new workspace later, you will have to refresh the list of mobile workspaces.</span></span>

<span data-ttu-id="e6456-151">[![Effettuare il pull per l'aggiornamento](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)</span><span class="sxs-lookup"><span data-stu-id="e6456-151">[![Pull to refresh](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)</span></span>

## <a name="enter-time-by-using-the-project-time-entry-mobile-workspace"></a><span data-ttu-id="e6456-152">Immettere l'ora utilizzando l'area di lavoro mobile per immissione ora progetto</span><span class="sxs-lookup"><span data-stu-id="e6456-152">Enter time by using the Project time entry mobile workspace</span></span>
1.  <span data-ttu-id="e6456-153">Sul dispositivo mobile, selezionare l'area di lavoro **Immissione ora progetto**.</span><span class="sxs-lookup"><span data-stu-id="e6456-153">On your mobile device, select the **Project time entry** workspace.</span></span>
2.  <span data-ttu-id="e6456-154">Selezionare **Immissione ora**.</span><span class="sxs-lookup"><span data-stu-id="e6456-154">Select **Time entry**.</span></span> <span data-ttu-id="e6456-155">Vengono visualizzate le date di calendario per la settimana corrente.</span><span class="sxs-lookup"><span data-stu-id="e6456-155">The calendar dates for the current week are shown.</span></span>
3.  <span data-ttu-id="e6456-156">Per una data selezionata, selezionare &gt; **Azioni**. **Nuova voce**.</span><span class="sxs-lookup"><span data-stu-id="e6456-156">For a selected date, select **Actions** &gt; **New entry**.</span></span>
4.  <span data-ttu-id="e6456-157">Immettere il numero di ore da registrare.</span><span class="sxs-lookup"><span data-stu-id="e6456-157">Enter the number of hours to record.</span></span>
5.  <span data-ttu-id="e6456-158">Selezionare il progetto per la voce ora.</span><span class="sxs-lookup"><span data-stu-id="e6456-158">Select the project for the time entry.</span></span> <span data-ttu-id="e6456-159">Viene visualizzato un elenco dei progetti caricati nell'app per l'utilizzo offline.</span><span class="sxs-lookup"><span data-stu-id="e6456-159">A list shows the projects that are loaded into your app for offline use.</span></span> <span data-ttu-id="e6456-160">Per impostazione predefinita, vengono caricati 50 articoli, ma è possibile cambiare questo numero.</span><span class="sxs-lookup"><span data-stu-id="e6456-160">By default, 50 items are loaded, but a developer can change this number.</span></span> <span data-ttu-id="e6456-161">Per ulteriori informazioni, vedere [Piattaforma mobile](../../dev-itpro/mobile-apps/platform/mobile-platform-home-page.md).</span><span class="sxs-lookup"><span data-stu-id="e6456-161">For more information, see [Mobile platform](../../dev-itpro/mobile-apps/platform/mobile-platform-home-page.md).</span></span>
6.  <span data-ttu-id="e6456-162">Se il progetto non è in elenco, selezionare **Cerca altro**.</span><span class="sxs-lookup"><span data-stu-id="e6456-162">If your project isn't in the list, select **Search**.</span></span> <span data-ttu-id="e6456-163">Ricercare per nome o selezionare la ricerca per nome progetto o cliente.</span><span class="sxs-lookup"><span data-stu-id="e6456-163">Search by name, or switch to search by project name or customer.</span></span>
7.  <span data-ttu-id="e6456-164">Consente di selezionare una categoria.</span><span class="sxs-lookup"><span data-stu-id="e6456-164">Select a category.</span></span> <span data-ttu-id="e6456-165">Viene visualizzato un elenco delle categorie caricate nell'app per l'utilizzo offline.</span><span class="sxs-lookup"><span data-stu-id="e6456-165">A list shows the categories that are loaded into your app for offline use.</span></span> <span data-ttu-id="e6456-166">Per impostazione predefinita, vengono caricati 50 articoli, ma è possibile cambiare questo numero.</span><span class="sxs-lookup"><span data-stu-id="e6456-166">By default, 50 items are loaded, but a developer can change this number.</span></span> <span data-ttu-id="e6456-167">Per ulteriori informazioni, vedere [Piattaforma mobile](../../dev-itpro/mobile-apps/platform/mobile-platform-home-page.md).</span><span class="sxs-lookup"><span data-stu-id="e6456-167">For more information, see [Mobile platform](../../dev-itpro/mobile-apps/platform/mobile-platform-home-page.md).</span></span>
8.  <span data-ttu-id="e6456-168">Se la categoria non è in elenco, selezionare **Cerca altro**.</span><span class="sxs-lookup"><span data-stu-id="e6456-168">If your category isn't in the list, select **Search**.</span></span> <span data-ttu-id="e6456-169">Ricerca in base alla categoria o ricerca per nome categoria.</span><span class="sxs-lookup"><span data-stu-id="e6456-169">Search by category, or switch to search by category name.</span></span>
9.  <span data-ttu-id="e6456-170">Selezionare un'attività.</span><span class="sxs-lookup"><span data-stu-id="e6456-170">Select an activity.</span></span> <span data-ttu-id="e6456-171">Viene visualizzato un elenco delle attività caricate nell'app per l'utilizzo offline.</span><span class="sxs-lookup"><span data-stu-id="e6456-171">A list shows the activities that are loaded into your app for offline use.</span></span> <span data-ttu-id="e6456-172">Per impostazione predefinita, vengono caricati 50 articoli, ma è possibile cambiare questo numero.</span><span class="sxs-lookup"><span data-stu-id="e6456-172">By default, 50 items are loaded, but a developer can change this number.</span></span> <span data-ttu-id="e6456-173">Per ulteriori informazioni, vedere [Piattaforma mobile](../../dev-itpro/mobile-apps/platform/mobile-platform-home-page.md).</span><span class="sxs-lookup"><span data-stu-id="e6456-173">For more information, see [Mobile platform](../../dev-itpro/mobile-apps/platform/mobile-platform-home-page.md).</span></span>
10. <span data-ttu-id="e6456-174">Se l'attività non è in elenco, selezionare **Cerca altro**.</span><span class="sxs-lookup"><span data-stu-id="e6456-174">If your activity isn't in the list, select **Search**.</span></span> <span data-ttu-id="e6456-175">Ricerca in base al numero dell'attività o ricerca per scopo.</span><span class="sxs-lookup"><span data-stu-id="e6456-175">Search by activity number, or switch to search by purpose.</span></span>

11. <span data-ttu-id="e6456-176">Selezionare la proprietà riga.</span><span class="sxs-lookup"><span data-stu-id="e6456-176">Select the line property.</span></span>
12. <span data-ttu-id="e6456-177">Facoltativo: immettere qualsiasi commento interno o esterno.</span><span class="sxs-lookup"><span data-stu-id="e6456-177">Optional: Enter any external and internal comments.</span></span>
13. <span data-ttu-id="e6456-178">Selezionare **Fine**.</span><span class="sxs-lookup"><span data-stu-id="e6456-178">Select **Done**.</span></span>

