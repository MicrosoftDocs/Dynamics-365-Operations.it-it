---
title: Area di lavoro mobile di controllo costi
description: In questo argomento vengono fornite informazioni sull'area di lavoro mobile Controllo costi. Questa area di lavoro consente ai responsabili del centro di costo visualizzare informazioni sulle prestazioni del centro di costo in qualsiasi momento e ovunque.
author: AndersGirke
manager: AnnBe
ms.date: 12/01/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CAMMobileCostObjectOverviewDetailsCurrentPeriod, CAMMobileCostObjectList, CAMMobileCostObjectOverviewDetailsPreviousPeriod, CAMMobileCostObjectOverview, CAMMobileCostObjectOverviewDetailsYearToDate, CAMMobileCostControlWorkspaceConfiguration
audience: Application User
ms.reviewer: roschlom
ms.custom: 267114
ms.assetid: 612f2988-b2b9-420d-9825-40b99dc0e204
ms.search.region: global
ms.author: aevengir
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: 58d86dbd2a3207b72d91165ede675bfe3ab8091e
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4990894"
---
# <a name="cost-controlling-mobile-workspace"></a><span data-ttu-id="4aa9d-104">Area di lavoro mobile di controllo costi</span><span class="sxs-lookup"><span data-stu-id="4aa9d-104">Cost controlling mobile workspace</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="4aa9d-105">In questo argomento vengono fornite informazioni sull'area di lavoro mobile **Controllo costi**.</span><span class="sxs-lookup"><span data-stu-id="4aa9d-105">This topic provides information about the **Cost controlling** mobile workspace.</span></span> <span data-ttu-id="4aa9d-106">Questa area di lavoro consente ai responsabili del centro di costo visualizzare informazioni sulle prestazioni del centro di costo in qualsiasi momento e ovunque.</span><span class="sxs-lookup"><span data-stu-id="4aa9d-106">This workspace lets cost center managers view information about cost center performance anytime and anywhere.</span></span>

<span data-ttu-id="4aa9d-107">Questa area di lavoro mobile può essere utilizzata con l'app Finance and Operations per dispositivi mobili.</span><span class="sxs-lookup"><span data-stu-id="4aa9d-107">This mobile workspace is intended to be used with the Finance and Operations mobile app.</span></span>

## <a name="overview"></a><span data-ttu-id="4aa9d-108">Panoramica</span><span class="sxs-lookup"><span data-stu-id="4aa9d-108">Overview</span></span>
<span data-ttu-id="4aa9d-109">L'area di lavoro mobile **Controllo costi** fornisce una visualizzazione immediata delle prestazioni correnti dei centri di costo confrontando i costi effettivi rispetto ai costi a budget.</span><span class="sxs-lookup"><span data-stu-id="4aa9d-109">The **Cost controlling** mobile workspace provides an instant view of the current performance of cost centers by comparing actual costs against the budgeted costs.</span></span> <span data-ttu-id="4aa9d-110">È possibile eseguire il drill-down per visualizzare lo stato dei singoli elementi di costo.</span><span class="sxs-lookup"><span data-stu-id="4aa9d-110">You can drill down to the status of individual cost elements.</span></span>

<span data-ttu-id="4aa9d-111">Ad esempio, un dipendente riceve un invito a una conferenza internazionale, ma l'organizzazione deve coprire tutte le spese di viaggio.</span><span class="sxs-lookup"><span data-stu-id="4aa9d-111">For example, an employee receives an invitation to an international conference, but the organization must cover all the travel expenses.</span></span> <span data-ttu-id="4aa9d-112">Il dipendente chiede al responsabile se può partecipare alla conferenza.</span><span class="sxs-lookup"><span data-stu-id="4aa9d-112">The employee asks their manager whether they can attend the conference.</span></span> <span data-ttu-id="4aa9d-113">Il responsabile apre rapidamente l'area di lavoro mobile **Controllo costi** sul dispositivo mobile per verificare se dispone del budget per consentire al dipendente di partecipare alla conferenza.</span><span class="sxs-lookup"><span data-stu-id="4aa9d-113">The manager opens the **Cost controlling** mobile workspace on their mobile device to see whether there is budget for the employee to attend the conference.</span></span>

### <a name="data-security"></a><span data-ttu-id="4aa9d-114">Sicurezza dei dati</span><span class="sxs-lookup"><span data-stu-id="4aa9d-114">Data security</span></span>
<span data-ttu-id="4aa9d-115">I dati nell'area di lavoro **Controllo costi** sono protetti mediante l'uso di credenziali dell'utente.</span><span class="sxs-lookup"><span data-stu-id="4aa9d-115">The data in the **Cost controlling** mobile workspace is secured through user credentials.</span></span> <span data-ttu-id="4aa9d-116">I responsabili del centro di costo possono visualizzare solo i dati relativi al proprio centro di costo.</span><span class="sxs-lookup"><span data-stu-id="4aa9d-116">Cost center managers are allowed to see data only for their own cost center.</span></span> <span data-ttu-id="4aa9d-117">La protezione a livello di accesso viene gestita nel modulo **Contabilità industriale**.</span><span class="sxs-lookup"><span data-stu-id="4aa9d-117">The access-level security is managed in the **Cost accounting** module.</span></span>

<span data-ttu-id="4aa9d-118">I contabili definiscono la configurazione dell'area di lavoro mobile **Controllo costi** nel modulo **Contabilità industriale**.</span><span class="sxs-lookup"><span data-stu-id="4aa9d-118">Cost accountants define the configuration of the **Cost controlling** mobile workspace in the **Cost accounting** module.</span></span> <span data-ttu-id="4aa9d-119">Una volta che l'area di lavoro è stata pubblicata nell'app mobile, sarà disponibile nell'app.</span><span class="sxs-lookup"><span data-stu-id="4aa9d-119">After the workspace is published to the mobile app, it's available in the app.</span></span> <span data-ttu-id="4aa9d-120">Pertanto, tutti i responsabili del centro di costo dell'organizzazione visualizzano i dati nello stesso formato.</span><span class="sxs-lookup"><span data-stu-id="4aa9d-120">Therefore, all cost center managers in the organization can view data in the same format.</span></span>

### <a name="actions-views-and-links"></a><span data-ttu-id="4aa9d-121">Azioni, visualizzazioni e collegamenti</span><span class="sxs-lookup"><span data-stu-id="4aa9d-121">Actions, views, and links</span></span>
<span data-ttu-id="4aa9d-122">L'area di lavoro mobile **Controllo costi** fornisce le azioni, le visualizzazioni e i collegamenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="4aa9d-122">The **Cost controlling** mobile workspace provides the following actions, views, and links:</span></span>

-   <span data-ttu-id="4aa9d-123">**Azioni**:</span><span class="sxs-lookup"><span data-stu-id="4aa9d-123">**Actions:**</span></span>

    -   <span data-ttu-id="4aa9d-124">Utilizzare **Seleziona configurazione** per selezionare un layout.</span><span class="sxs-lookup"><span data-stu-id="4aa9d-124">Use **Select configuration** to select a layout.</span></span>
    -   <span data-ttu-id="4aa9d-125">Utilizzare **Seleziona oggetto di costo** per selezionare i centri di costo in base a cui filtrare i dati.</span><span class="sxs-lookup"><span data-stu-id="4aa9d-125">Use **Select cost object** to select the cost centers to filter data on.</span></span>
    
        > [!NOTE]
        > <span data-ttu-id="4aa9d-126">I centri di costo visualizzati nell'elenco dipendono dall'accesso assegnato nel modulo **Contabilità industriale**.</span><span class="sxs-lookup"><span data-stu-id="4aa9d-126">The cost centers that appear in the list depend on the access that is granted in the **Cost accounting** module.</span></span>

-   <span data-ttu-id="4aa9d-127">**Visualizzazioni**: in base alle azioni selezionate e alla configurazione nel modulo **Contabilità industriale**, è possibile visualizzare le seguenti informazioni nelle schede:</span><span class="sxs-lookup"><span data-stu-id="4aa9d-127">**Views:** Based on the actions that are selected and the configuration in the **Cost accounting** module, you can view the following information on the cards:</span></span>

    -   <span data-ttu-id="4aa9d-128">Effettivi rispetto al budget (periodo corrente)</span><span class="sxs-lookup"><span data-stu-id="4aa9d-128">Actual vs budget (current period)</span></span>
    -   <span data-ttu-id="4aa9d-129">Effettivi rispetto al budget rivisto (periodo corrente)</span><span class="sxs-lookup"><span data-stu-id="4aa9d-129">Actual vs revised budget (current period)</span></span>
    -   <span data-ttu-id="4aa9d-130">Effettivo rispetto al budget (periodo precedente)</span><span class="sxs-lookup"><span data-stu-id="4aa9d-130">Actual vs budget (previous period)</span></span>
    -   <span data-ttu-id="4aa9d-131">Effettivo rispetto al budget rivisto (periodo precedente)</span><span class="sxs-lookup"><span data-stu-id="4aa9d-131">Actual vs revised budget (previous period)</span></span>
    -   <span data-ttu-id="4aa9d-132">Effettivo rispetto al budget (da inizio anno a oggi)</span><span class="sxs-lookup"><span data-stu-id="4aa9d-132">Actual vs budget (year to date)</span></span>
    -   <span data-ttu-id="4aa9d-133">Effettivo rispetto al budget rivisto (da inizio anno a oggi)</span><span class="sxs-lookup"><span data-stu-id="4aa9d-133">Actual vs revised budget (year to date)</span></span>

    <span data-ttu-id="4aa9d-134">Gli importi verranno visualizzati in tutte le schede: Effettivo, Budget, Scostamento e % scostamento.</span><span class="sxs-lookup"><span data-stu-id="4aa9d-134">The following amounts are shown on every card: Actual, Budget, Variance, and Variance %.</span></span>

-   <span data-ttu-id="4aa9d-135">**Collegamenti**:</span><span class="sxs-lookup"><span data-stu-id="4aa9d-135">**Links:**</span></span>

    -   <span data-ttu-id="4aa9d-136">Dettagli per periodo corrente</span><span class="sxs-lookup"><span data-stu-id="4aa9d-136">Details for current period</span></span>
    -   <span data-ttu-id="4aa9d-137">Dettagli per periodo precedente</span><span class="sxs-lookup"><span data-stu-id="4aa9d-137">Details for previous period</span></span>
    -   <span data-ttu-id="4aa9d-138">Dettagli per anno fino a oggi</span><span class="sxs-lookup"><span data-stu-id="4aa9d-138">Details for year to date</span></span>

    <span data-ttu-id="4aa9d-139">Quando si seleziona un collegamento, viene visualizzata una scheda per ciascun elemento di costo.</span><span class="sxs-lookup"><span data-stu-id="4aa9d-139">When you select a link, a card is shown for each cost element.</span></span> <span data-ttu-id="4aa9d-140">In ogni scheda vengono visualizzati i seguenti importi: Effettivo, Budget, Scostamento budget, % scostamento budget, Budget rivisto, Scostamento budget rivisto e % scostamento budget rivisto.</span><span class="sxs-lookup"><span data-stu-id="4aa9d-140">The following amounts are shown on every card: Actual, Budget, Budget variance, Budget variance %, Revised budget, Revised budget variance, and Revised budget variance %.</span></span>
    
    <span data-ttu-id="4aa9d-141">[![Scheda per un elemento costo ](./media/Cost-controlling.png)](./media/Cost-controlling.png)</span><span class="sxs-lookup"><span data-stu-id="4aa9d-141">[![Card for a cost element](./media/Cost-controlling.png)](./media/Cost-controlling.png)</span></span>

## <a name="prerequisites"></a><span data-ttu-id="4aa9d-142">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="4aa9d-142">Prerequisites</span></span>
<span data-ttu-id="4aa9d-143">I prerequisiti variano a seconda della versione di Microsoft Dynamics 365 che è stata installata nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="4aa9d-143">The prerequisites differ, based on the version of Microsoft Dynamics 365 that has been deployed for your organization.</span></span>

### <a name="prerequisites-if-you-use-microsoft-dynamics-365-finance"></a><span data-ttu-id="4aa9d-144">Prerequisiti per l'utilizzo di Microsoft Dynamics 365 Finance</span><span class="sxs-lookup"><span data-stu-id="4aa9d-144">Prerequisites if you use Microsoft Dynamics 365 Finance</span></span>
<span data-ttu-id="4aa9d-145">Se Finance è stato distribuito nell'organizzazione, l'amministratore di sistema deve pubblicare l'area di lavoro mobile **Controllo costi**.</span><span class="sxs-lookup"><span data-stu-id="4aa9d-145">If Finance has been deployed for your organization, the system administrator must publish the **Cost controlling** mobile workspace.</span></span> <span data-ttu-id="4aa9d-146">Per istruzioni, vedere [Pubblicare un'area di lavoro mobile](../../dev-itpro/mobile-apps/publish-mobile-workspace.md).</span><span class="sxs-lookup"><span data-stu-id="4aa9d-146">For instructions, see [Publish a mobile workspace](../../dev-itpro/mobile-apps/publish-mobile-workspace.md).</span></span>

### <a name="prerequisites-if-you-use-version-1611-with-platform-update-3-or-later"></a><span data-ttu-id="4aa9d-147">Prerequisiti se si usa la versione 1611 con Aggiornamento piattaforma 3 o versione successiva</span><span class="sxs-lookup"><span data-stu-id="4aa9d-147">Prerequisites if you use version 1611 with Platform update 3 or later</span></span>
<span data-ttu-id="4aa9d-148">Se nell'organizzazione è stato distribuita la versione 1611 con Aggiornamento piattaforma 3 o versione successiva, l'amministratore di sistema deve soddisfare i prerequisiti seguenti.</span><span class="sxs-lookup"><span data-stu-id="4aa9d-148">If version 1611 with Platform update 3 or later has been deployed for your organization, the system administrator must complete the following prerequisites.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="4aa9d-149">Prerequisito</span><span class="sxs-lookup"><span data-stu-id="4aa9d-149">Prerequisite</span></span></th>
<th><span data-ttu-id="4aa9d-150">Ruolo</span><span class="sxs-lookup"><span data-stu-id="4aa9d-150">Role</span></span></th>
<th><span data-ttu-id="4aa9d-151">descrizione</span><span class="sxs-lookup"><span data-stu-id="4aa9d-151">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="4aa9d-152">Implementare l'articoloo KB 4013633.</span><span class="sxs-lookup"><span data-stu-id="4aa9d-152">Implement KB 4013633.</span></span></td>
<td><span data-ttu-id="4aa9d-153">Amministratore di sistema</span><span class="sxs-lookup"><span data-stu-id="4aa9d-153">System administrator</span></span></td>

<td><span data-ttu-id="4aa9d-154">L'articolo KB 4013633 è un aggiornamento X++ o aggiornamento rapido dei metadati contenente l'area di lavoro mobile <strong>Controllo costi</strong>.</span><span class="sxs-lookup"><span data-stu-id="4aa9d-154">KB 4013633 is an X++ update or metadata hotfix that contains the <strong>Cost controlling</strong> mobile workspace.</span></span> <span data-ttu-id="4aa9d-155">Per implementare l'articolo KB 4013633, l'amministratore di sistema deve completare i passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="4aa9d-155">To implement KB 4013633, your system administrator must follow these steps.</span></span>
<ol>
<li><span data-ttu-id="4aa9d-156"><a href="../../dev-itpro/migration-upgrade/download-hotfix-lcs.md">Scaricare l'hotfix metadati da Microsoft Dynamics Lifecycle Services (LCS)</a>.</span><span class="sxs-lookup"><span data-stu-id="4aa9d-156"><a href="../../dev-itpro/migration-upgrade/download-hotfix-lcs.md">Download the metadata hotfix from Microsoft Dynamics Lifecycle Services (LCS)</a>.</span></span></li>
<li><span data-ttu-id="4aa9d-157"><a href="../../dev-itpro/migration-upgrade/install-metadata-hotfix-package.md">Installare l'aggiornamento rapido dei metadati</a>.</span><span class="sxs-lookup"><span data-stu-id="4aa9d-157"><a href="../../dev-itpro/migration-upgrade/install-metadata-hotfix-package.md">Install the metadata hotfix</a>.</span></span></li>
<li><span data-ttu-id="4aa9d-158"><a href="../../dev-itpro/deployment/create-apply-deployable-package.md">Creare un pacchetto distribuibile</a> contenente il modello <strong>SCMMobile</strong> e quindi caricare il pacchetto distribuibile in LCS.</span><span class="sxs-lookup"><span data-stu-id="4aa9d-158"><a href="../../dev-itpro/deployment/create-apply-deployable-package.md">Create a deployable package</a> that contains the <strong>SCMMobile</strong> model, and then upload the deployable package to LCS.</span></span></li>
<li><span data-ttu-id="4aa9d-159"><a href="../../dev-itpro/deployment/apply-deployable-package-system.md">Applicare il pacchetto distribuibile</a>.</span><span class="sxs-lookup"><span data-stu-id="4aa9d-159"><a href="../../dev-itpro/deployment/apply-deployable-package-system.md">Apply the deployable package</a>.</span></span></li>

</ol></td>
</tr>
<tr class="even">
<td><span data-ttu-id="4aa9d-160">Pubblicare l'area di lavoro mobile <strong>Controllo costi</strong>.</span><span class="sxs-lookup"><span data-stu-id="4aa9d-160">Publish the <strong>Cost controlling</strong> mobile workspace.</span></span></td>
<td><span data-ttu-id="4aa9d-161">Amministratore di sistema</span><span class="sxs-lookup"><span data-stu-id="4aa9d-161">System administrator</span></span></td>
<td><span data-ttu-id="4aa9d-162">Vedere <a href="../../dev-itpro/mobile-apps/publish-mobile-workspace.md">Pubblicare un'area di lavoro mobile</a>.</span><span class="sxs-lookup"><span data-stu-id="4aa9d-162">See <a href="../../dev-itpro/mobile-apps/publish-mobile-workspace.md">Publish a mobile workspace</a>.</span></span></td>
</tr>
</tbody>
</table>


## <a name="download-and-install-the-mobile-app"></a><span data-ttu-id="4aa9d-163">Scaricare e installare l'app per dispositivi mobili</span><span class="sxs-lookup"><span data-stu-id="4aa9d-163">Download and install the mobile app</span></span>
<span data-ttu-id="4aa9d-164">Scaricare e installare l'app Finance and Operations per dispositivi mobili:</span><span class="sxs-lookup"><span data-stu-id="4aa9d-164">Download and install the Finance and Operations mobile app:</span></span>

-   [<span data-ttu-id="4aa9d-165">Per telefoni Android</span><span class="sxs-lookup"><span data-stu-id="4aa9d-165">For Android phones</span></span>](https://go.microsoft.com/fwlink/?linkid=850662)
-   [<span data-ttu-id="4aa9d-166">Per iPhone</span><span class="sxs-lookup"><span data-stu-id="4aa9d-166">For iPhones</span></span>](https://go.microsoft.com/fwlink/?linkid=850663)

## <a name="sign-in-to-the-mobile-app"></a><span data-ttu-id="4aa9d-167">Accedere all'app mobile</span><span class="sxs-lookup"><span data-stu-id="4aa9d-167">Sign in to the mobile app</span></span>

1.  <span data-ttu-id="4aa9d-168">Avviare l'app sul dispositivo mobile.</span><span class="sxs-lookup"><span data-stu-id="4aa9d-168">Start the app on your mobile device.</span></span>
2.  <span data-ttu-id="4aa9d-169">Immettere il proprio URL Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="4aa9d-169">Enter your Dynamics 365 URL.</span></span>
3.  <span data-ttu-id="4aa9d-170">La prima volta che si accede viene richiesto di inserire il proprio nome utente e la password.</span><span class="sxs-lookup"><span data-stu-id="4aa9d-170">The first time that you sign in, you're prompted for your user name and password.</span></span> <span data-ttu-id="4aa9d-171">Immettere le proprie credenziali.</span><span class="sxs-lookup"><span data-stu-id="4aa9d-171">Enter your credentials.</span></span>
4.  <span data-ttu-id="4aa9d-172">Dopo avere effettuato l'accesso, vengono visualizzate le aree di lavoro disponibili per la società.</span><span class="sxs-lookup"><span data-stu-id="4aa9d-172">After you sign in, the available workspaces for your company are shown.</span></span> <span data-ttu-id="4aa9d-173">Nota: se l'amministratore di sistema pubblica una nuova area di lavoro in seguito, è necessario aggiornare l'elenco delle aree di lavoro mobili.</span><span class="sxs-lookup"><span data-stu-id="4aa9d-173">Note that if your system administrator publishes a new workspace later, you will have to refresh the list of mobile workspaces.</span></span>

<span data-ttu-id="4aa9d-174">[![Effettuare il pull per l'aggiornamento](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)</span><span class="sxs-lookup"><span data-stu-id="4aa9d-174">[![Pull to refresh](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)</span></span>

## <a name="view-the-performance-of-your-cost-center-by-using-the-cost-controlling-mobile-workspace"></a><span data-ttu-id="4aa9d-175">Visualizzare le prestazioni del centro di costo tramite l'area di lavoro mobile Controllo costi</span><span class="sxs-lookup"><span data-stu-id="4aa9d-175">View the performance of your cost center by using the Cost controlling mobile workspace</span></span>

1.  <span data-ttu-id="4aa9d-176">Sul dispositivo mobile, selezionare l'area di lavoro **Controllo costi**.</span><span class="sxs-lookup"><span data-stu-id="4aa9d-176">On your mobile device, select the **Cost controlling** workspace.</span></span>
2.  <span data-ttu-id="4aa9d-177">Selezionare **Controllo oggetto di costo**.</span><span class="sxs-lookup"><span data-stu-id="4aa9d-177">Select **Cost object controlling**.</span></span>
3.  <span data-ttu-id="4aa9d-178">Selezionare **Azioni**.</span><span class="sxs-lookup"><span data-stu-id="4aa9d-178">Select **Actions**.</span></span>
4.  <span data-ttu-id="4aa9d-179">Selezionare **Seleziona configurazione** per selezionare un layout di controllo dei costi.</span><span class="sxs-lookup"><span data-stu-id="4aa9d-179">Select **Select configuration** to select a cost controlling layout.</span></span>
5.  <span data-ttu-id="4aa9d-180">Selezionare **Fine**.</span><span class="sxs-lookup"><span data-stu-id="4aa9d-180">Select **Done**.</span></span>
6.  <span data-ttu-id="4aa9d-181">Selezionare **Azioni**.</span><span class="sxs-lookup"><span data-stu-id="4aa9d-181">Select **Actions**.</span></span>
7.  <span data-ttu-id="4aa9d-182">Selezionare **Seleziona oggetto di costo** per selezionare i centri di costo a cui si ha accesso.</span><span class="sxs-lookup"><span data-stu-id="4aa9d-182">Select **Select cost object** to select the cost centers that you've been granted access to.</span></span>
8.  <span data-ttu-id="4aa9d-183">Selezionare **Fine**.</span><span class="sxs-lookup"><span data-stu-id="4aa9d-183">Select **Done**.</span></span>
9.  <span data-ttu-id="4aa9d-184">Visualizzare le prestazioni complessive del centro di costo.</span><span class="sxs-lookup"><span data-stu-id="4aa9d-184">View the overall performance of your cost center.</span></span>
10. <span data-ttu-id="4aa9d-185">Selezionare il collegamento **Dettagli per periodo corrente**.</span><span class="sxs-lookup"><span data-stu-id="4aa9d-185">Select the **Details for current period** link.</span></span>
11. <span data-ttu-id="4aa9d-186">Visualizzare le prestazioni dei singoli elementi di costo.</span><span class="sxs-lookup"><span data-stu-id="4aa9d-186">View the performance of individual cost elements.</span></span>
12. <span data-ttu-id="4aa9d-187">È inoltre possibile cercare elementi di costo specifici.</span><span class="sxs-lookup"><span data-stu-id="4aa9d-187">You can also search for specific cost elements.</span></span>

