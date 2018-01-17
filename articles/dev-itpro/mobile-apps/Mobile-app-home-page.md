---
title: Home page app mobile
description: In questo argomento viene descritta l'app mobile Microsoft Dynamics 365 for Unified Operations e vengono forniti i collegamenti alle risorse necessarie per implementarla dell'organizzazione.
author: sericks007
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.scope: Operations
ms.custom: 272853
ms.assetid: c99f818f-27b3-4e45-92b4-74272dad0e17
ms.search.region: Global
ms.author: sericks
ms.dyn365.ops.version: Platform update 4
ms.search.validFrom: 2017-02-28
ms.translationtype: HT
ms.sourcegitcommit: 029511634e56aec7fdd91bad9441cd12951fbd8d
ms.openlocfilehash: c064aa3bc799c846af80d02550451e58ad6bf9f4
ms.contentlocale: it-it
ms.lasthandoff: 01/17/2018

---

# <a name="mobile-app-home-page"></a><span data-ttu-id="88a56-103">Home page app mobile</span><span class="sxs-lookup"><span data-stu-id="88a56-103">Mobile app home page</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="88a56-104">In questo argomento viene descritta l'app mobile Microsoft Dynamics 365 for Unified Operations e vengono forniti i collegamenti alle risorse necessarie per implementarla dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="88a56-104">This topic describes the Microsoft Dynamics 365 for Unified Operations mobile app and provides links to resources that can help you implement it in your organization.</span></span>

> [!NOTE]
> <span data-ttu-id="88a56-105">L'app mobile era denominata in precedenza *Microsoft Dynamics 365 for Finance and Operations*.</span><span class="sxs-lookup"><span data-stu-id="88a56-105">The mobile app was previously named *Microsoft Dynamics 365 for Finance and Operations*.</span></span>

<a name="overview"></a><span data-ttu-id="88a56-106">Panoramica</span><span class="sxs-lookup"><span data-stu-id="88a56-106">Overview</span></span>
--------

<span data-ttu-id="88a56-107">L'app mobile consente all'organizzazione di rendere disponibili i propri processi aziendali nei dispositivi mobili.</span><span class="sxs-lookup"><span data-stu-id="88a56-107">The mobile app enables your organization to make its business processes available on mobile devices.</span></span> <span data-ttu-id="88a56-108">Dopo che l'amministratore IT attiva le aree di lavoro mobile per l'organizzazione, gli utenti potranno accedere all'app e immediatamente iniziare a eseguire i processi aziendali dai dispositivi mobili.</span><span class="sxs-lookup"><span data-stu-id="88a56-108">After your IT admin enables the mobile workspaces for your organization, users can sign in to the app and immediately begin to run business processes from their mobile devices.</span></span> <span data-ttu-id="88a56-109">L'app mobile include le seguenti funzionalità che consentono di aumentare la produttività:</span><span class="sxs-lookup"><span data-stu-id="88a56-109">The mobile app includes the following features that can help increase productivity:</span></span>

- <span data-ttu-id="88a56-110">Gli utenti possono visualizzare, modificare ed eseguire azioni sui dati business, anche se invece dispongono di connettività di rete intermittente o se i dispositivi mobili sono completamente offline.</span><span class="sxs-lookup"><span data-stu-id="88a56-110">Users can view, edit, and act on business data, even if they have intermittent network connectivity or their mobile devices are completely offline.</span></span> <span data-ttu-id="88a56-111">Quando un'unità ristabilisce una connessione di rete, le operazioni dati offline vengono sincronizzate automaticamente con Dynamics 365 for Finance and Operations, Enterprise edition o Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="88a56-111">When a device reestablishes a network connection, offline data operations are automatically synchronized with Dynamics 365 for Finance and Operations, Enterprise edition, or Microsoft Dynamics 365 for Finance and Operations.</span></span>
- <span data-ttu-id="88a56-112">Gli amministratori IT o gli sviluppatori possono creare e pubblicare aree di lavoro mobili che sono state personalizzate per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="88a56-112">IT admins or developers can build and publish mobile workspaces that have been tailored to their organization.</span></span> <span data-ttu-id="88a56-113">L'app utilizza le risorse di codice esistenti.</span><span class="sxs-lookup"><span data-stu-id="88a56-113">The app uses your existing code assets.</span></span> <span data-ttu-id="88a56-114">Di conseguenza, non è necessario implementare di nuovo le procedure di convalida, la regola business o la configurazione di protezione.</span><span class="sxs-lookup"><span data-stu-id="88a56-114">Therefore, you don't have to re-implement your validation procedures, business logic, or security configuration.</span></span>
- <span data-ttu-id="88a56-115">Gli amministratori IT o gli sviluppatori possono progettare facilmente le aree di lavoro mediante la progettazione rapida per area di lavoro inclusa in nel client Web.</span><span class="sxs-lookup"><span data-stu-id="88a56-115">IT admins or developers can easily design mobile workspaces by using the point-and-click workspace designer that is included with the web client.</span></span>
- <span data-ttu-id="88a56-116">Gli amministratori IT o gli sviluppatori possono facoltativamente ottimizzare le capacità offline delle aree di lavoro utilizzando il framework dell'estensibilità della regola business.</span><span class="sxs-lookup"><span data-stu-id="88a56-116">IT admins or developers can optionally optimize the offline capabilities of workspaces by using the Business logic extensibility framework.</span></span> <span data-ttu-id="88a56-117">Poiché i dati continuano a essere elaborati offline anche mentre il dispositivo è offline, gli scenari mobili rimangono ricchi e fluidi anche se i dispositivi non hanno connettività di rete costante.</span><span class="sxs-lookup"><span data-stu-id="88a56-117">Because data continues to be processed while a device is offline, your mobile scenarios remain rich and fluid, even if devices don't have constant network connectivity.</span></span>

## <a name="elements-of-the-mobile-app"></a><span data-ttu-id="88a56-118">Elementi dell'app mobile</span><span class="sxs-lookup"><span data-stu-id="88a56-118">Elements of the mobile app</span></span>
<span data-ttu-id="88a56-119">La navigazione dell'app mobile è costituita si basa su quattro concetti di base: dashboard, aree di lavoro, pagine e azioni.</span><span class="sxs-lookup"><span data-stu-id="88a56-119">Navigation in the mobile app consists of four basic concepts: the dashboard, workspaces, pages, and actions.</span></span> 

<span data-ttu-id="88a56-120">[![Concetti di navigazione nell'app mobile](./media/mobilephoneapp1-1024x536.png)](./media/mobilephoneapp1.png)</span><span class="sxs-lookup"><span data-stu-id="88a56-120">[![Navigation concepts in the mobile app](./media/mobilephoneapp1-1024x536.png)](./media/mobilephoneapp1.png)</span></span>

1. <span data-ttu-id="88a56-121">All'avvio dell'app, passare al **dashboard**.</span><span class="sxs-lookup"><span data-stu-id="88a56-121">When you start the app, you go to the **dashboard**.</span></span>
2. <span data-ttu-id="88a56-122">Nel dashboard, è possibile visualizzare un elenco di **aree di lavoro** pubblicate.</span><span class="sxs-lookup"><span data-stu-id="88a56-122">On the dashboard, you can see a list of **workspaces** that have been published.</span></span>
3. <span data-ttu-id="88a56-123">In ciascuna area di lavoro, è possibile visualizzare un elenco **pagine** disponibile per tale area di lavoro.</span><span class="sxs-lookup"><span data-stu-id="88a56-123">In each workspace, you can see a list of **pages** that are available for that workspace.</span></span>
4. <span data-ttu-id="88a56-124">Una volta posizionati su una pagina, è possibile eseguire più azioni.</span><span class="sxs-lookup"><span data-stu-id="88a56-124">After you're on a page, you can perform several actions.</span></span> <span data-ttu-id="88a56-125">Di seguito sono riportati alcuni esempi.</span><span class="sxs-lookup"><span data-stu-id="88a56-125">Here are some examples:</span></span>

    - <span data-ttu-id="88a56-126">Visualizzare dati dettagliati.</span><span class="sxs-lookup"><span data-stu-id="88a56-126">View detailed data.</span></span>
    - <span data-ttu-id="88a56-127">Accedere ad altre pagine per i dati correlati, ad esempio i dettagli di entità oppure le righe.</span><span class="sxs-lookup"><span data-stu-id="88a56-127">Navigate to other pages for related data, such as entity details or lines.</span></span>
    - <span data-ttu-id="88a56-128">Visualizzare un elenco di **azioni** disponibile per tale pagina.</span><span class="sxs-lookup"><span data-stu-id="88a56-128">See a list of **actions** that are available for that page.</span></span> <span data-ttu-id="88a56-129">Le azioni consentono di creare o modificare i dati esistenti.</span><span class="sxs-lookup"><span data-stu-id="88a56-129">Actions let you create or edit existing data.</span></span>

## <a name="implementation-process"></a><span data-ttu-id="88a56-130">Processo di implementazione</span><span class="sxs-lookup"><span data-stu-id="88a56-130">Implementation process</span></span>
<span data-ttu-id="88a56-131">Nella figura seguente è illustrato il processo per implementare entrambe le aree di lavoro mobili fornite da Microsoft e le aree di lavoro mobili personalizzate.</span><span class="sxs-lookup"><span data-stu-id="88a56-131">The following illustration shows the process for implementing both mobile workspaces that are provided by Microsoft and custom mobile workspaces.</span></span> 

![Processo di implementazione app mobili](./media/Mobile-implementation-process-5.png)

<span data-ttu-id="88a56-133">Nella seguente tabella sono inclusi collegamenti alle risorse necessarie per implementare entrambe le aree di lavoro mobili fornite da Microsoft e le aree di lavoro mobili personalizzate.</span><span class="sxs-lookup"><span data-stu-id="88a56-133">The following table includes links to resources that can help you implement both mobile workspaces that are provided by Microsoft and custom mobile workspaces.</span></span> <span data-ttu-id="88a56-134">I numeri nella prima colonna corrispondono ai passaggi numerati nella precedente figura.</span><span class="sxs-lookup"><span data-stu-id="88a56-134">The numbers in the first column correspond to the numbered steps in the previous illustration.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="88a56-135">Graduale</span><span class="sxs-lookup"><span data-stu-id="88a56-135">Step</span></span></th>
<th><span data-ttu-id="88a56-136">Ruolo</span><span class="sxs-lookup"><span data-stu-id="88a56-136">Role</span></span></th>
<th><span data-ttu-id="88a56-137">Azione</span><span class="sxs-lookup"><span data-stu-id="88a56-137">Action</span></span></th>
<th><span data-ttu-id="88a56-138">Risorse che consentono di completare l'azione</span><span class="sxs-lookup"><span data-stu-id="88a56-138">Resources to help you complete the action</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="88a56-139">1</span><span class="sxs-lookup"><span data-stu-id="88a56-139">1</span></span></td>
<td><span data-ttu-id="88a56-140">Amministratore di sistema</span><span class="sxs-lookup"><span data-stu-id="88a56-140">System administrator</span></span></td>
<td><span data-ttu-id="88a56-141">Implementare Finance and Operations nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="88a56-141">Implement Finance and Operations in your organization.</span></span></td>
<td><ul><li><span data-ttu-id="88a56-142">Se non è stata distribuita una versione di Microsoft Dynamics 365, vedere <a href="../deployment/deploy-demo-environment.md">Distribuire un ambiente di dimostrazione</a>.</span><span class="sxs-lookup"><span data-stu-id="88a56-142">If you haven't yet deployed a version of Microsoft Dynamics 365, see <a href="../deployment/deploy-demo-environment.md">Deploy a demo environment</a>.</span></span></li><li><span data-ttu-id="88a56-143">Per visualizzare un elenco di aree di lavoro mobili da utilizzare, vedere <a href="mobile-workspaces-released.md">Aree di lavoro mobili rilasciate di recente</a>.</span><span class="sxs-lookup"><span data-stu-id="88a56-143">To see a list of mobile workspaces that can be used, see <a href="mobile-workspaces-released.md">Mobile workspaces recently released</a>.</span></span></li></ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="88a56-144">2</span><span class="sxs-lookup"><span data-stu-id="88a56-144">2</span></span></td>
<td><span data-ttu-id="88a56-145">Amministratore di sistema</span><span class="sxs-lookup"><span data-stu-id="88a56-145">System administrator</span></span></td>
<td><span data-ttu-id="88a56-146"><strong>Se si utilizza Microsoft Dynamics 365 for Finance and Operations versione 1611:</strong> Scaricare e installare gli articoli KB che abilitano le aree di lavoro mobili fornite da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="88a56-146"><strong>If you're using Microsoft Dynamics 365 for Finance and Operations version 1611:</strong> Download and install KBs that enable the mobile workspaces that are provided by Microsoft.</span></span></td>
<td><span data-ttu-id="88a56-147">Per ulteriori informazioni, vedere i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="88a56-147">See the following topics for more information:</span></span>
<ul>

<li><span data-ttu-id="88a56-148"><a href="../../financials/cost-accounting/cost-controlling-mobile-workspace.md">Aree di lavoro mobili di controllo costi</a></span><span class="sxs-lookup"><span data-stu-id="88a56-148"><a href="../../financials/cost-accounting/cost-controlling-mobile-workspace.md">Cost controlling mobile workspaces</a></span></span></li>
<li><span data-ttu-id="88a56-149"><a href="../../supply-chain/inventory/inventory-on-hand-mobile-workspace.md">Area di lavoro mobile per scorte disponibili</a></span><span class="sxs-lookup"><span data-stu-id="88a56-149"><a href="../../supply-chain/inventory/inventory-on-hand-mobile-workspace.md">Inventory on-hand mobile workspace</a></span></span></li>
<li><span data-ttu-id="88a56-150"><a href="../../supply-chain/sales-marketing/sales-orders-mobile-workspace.md">Aree di lavoro mobili per ordini cliente</a></span><span class="sxs-lookup"><span data-stu-id="88a56-150"><a href="../../supply-chain/sales-marketing/sales-orders-mobile-workspace.md">Sales orders mobile workspaces</a></span></span></li>
<li><span data-ttu-id="88a56-151"><a href="../../supply-chain/procurement/vendor-collaboration-mobile-workspace.md">Area di lavoro mobile di collaborazione fornitore</a></span><span class="sxs-lookup"><span data-stu-id="88a56-151"><a href="../../supply-chain/procurement/vendor-collaboration-mobile-workspace.md">Vendor collaboration mobile workspace</a></span></span></li>
<li><span data-ttu-id="88a56-152"><a href="../../financials/project-management/project-time-entry-mobile-workspace.md">Area di lavoro mobile per immissione ora progetto</a></span><span class="sxs-lookup"><span data-stu-id="88a56-152"><a href="../../financials/project-management/project-time-entry-mobile-workspace.md">Project time entry mobile workspace</a></span></span></li>
<li><span data-ttu-id="88a56-153"><a href="../../financials/expense-management/expense-management-mobile-workspace.md">Area di lavoro mobile di gestione spese</a></span><span class="sxs-lookup"><span data-stu-id="88a56-153"><a href="../../financials/expense-management/expense-management-mobile-workspace.md">Expense management mobile workspace</a></span></span></li>

</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="88a56-154">3</span><span class="sxs-lookup"><span data-stu-id="88a56-154">3</span></span></td>
<td><span data-ttu-id="88a56-155">Amministratore di sistema</span><span class="sxs-lookup"><span data-stu-id="88a56-155">System administrator</span></span></td>
<td><span data-ttu-id="88a56-156">Pubblicare le aree di lavoro mobili fornite da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="88a56-156">Publish the mobile workspaces that are provided by Microsoft.</span></span></td>
<td><span data-ttu-id="88a56-157"><a href="publish-mobile-workspace.md">Pubblicare un'area di lavoro mobile</a>
</span><span class="sxs-lookup"><span data-stu-id="88a56-157"><a href="publish-mobile-workspace.md">Publish a mobile workspace</a>
</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="88a56-158">4</span><span class="sxs-lookup"><span data-stu-id="88a56-158">4</span></span></td>
<td><span data-ttu-id="88a56-159">Sviluppatore o fornitore di software indipendente (ISV)</span><span class="sxs-lookup"><span data-stu-id="88a56-159">Developer or independent software vendor (ISV)</span></span></td>
<td><span data-ttu-id="88a56-160">Utilizzare la piattaforma mobile per creare aree di lavoro mobili personalizzate.</span><span class="sxs-lookup"><span data-stu-id="88a56-160">Use the mobile platform to create custom mobile workspaces.</span></span></td>
<td><span data-ttu-id="88a56-161"><a href="platform/mobile-platform-home-page.md">Piattaforma mobile</a></span><span class="sxs-lookup"><span data-stu-id="88a56-161"><a href="platform/mobile-platform-home-page.md">Mobile platform</a></span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="88a56-162">5</span><span class="sxs-lookup"><span data-stu-id="88a56-162">5</span></span></td>
<td><span data-ttu-id="88a56-163">ISV</span><span class="sxs-lookup"><span data-stu-id="88a56-163">ISV</span></span></td>
<td><span data-ttu-id="88a56-164">Creare un pacchetto distribuibile contenente le aree di lavoro mobili personalizzate e caricare il pacchetto in Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="88a56-164">Create a deployable package that contains custom mobile workspaces, and upload the package to Microsoft Dynamics Lifecycle Services (LCS).</span></span></td>
<td><span data-ttu-id="88a56-165"><a href="../deployment/create-apply-deployable-package.md">Creare un pacchetto distribuibile</a></span><span class="sxs-lookup"><span data-stu-id="88a56-165"><a href="../deployment/create-apply-deployable-package.md">Create a deployable package</a></span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="88a56-166">6</span><span class="sxs-lookup"><span data-stu-id="88a56-166">6</span></span></td>
<td><span data-ttu-id="88a56-167">Amministratore di sistema</span><span class="sxs-lookup"><span data-stu-id="88a56-167">System administrator</span></span></td>
<td><span data-ttu-id="88a56-168">Applicare il pacchetto distribuibile contenente le aree di lavoro personalizzate che vengono fornite dall'ISV.</span><span class="sxs-lookup"><span data-stu-id="88a56-168">Apply the deployable package that contains the custom workspaces that are provided by the independent software vendor (ISV).</span></span></td>
<td><span data-ttu-id="88a56-169"><a href="../deployment/apply-deployable-package-system.md">Applicare un pacchetto distribuibile</a></span><span class="sxs-lookup"><span data-stu-id="88a56-169"><a href="../deployment/apply-deployable-package-system.md">Apply a deployable package</a></span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="88a56-170">7</span><span class="sxs-lookup"><span data-stu-id="88a56-170">7</span></span></td>
<td><span data-ttu-id="88a56-171">Amministratore di sistema</span><span class="sxs-lookup"><span data-stu-id="88a56-171">System administrator</span></span></td>
<td><span data-ttu-id="88a56-172">Pubblicare le aree di lavoro mobili personalizzate fornite dall'ISV.</span><span class="sxs-lookup"><span data-stu-id="88a56-172">Publish the custom mobile workspaces that are provided by the ISV.</span></span></td>
<td><span data-ttu-id="88a56-173"><a href="publish-mobile-workspace.md">Pubblicare un'area di lavoro mobile</a></span><span class="sxs-lookup"><span data-stu-id="88a56-173"><a href="publish-mobile-workspace.md">Publish a mobile workspace</a></span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="88a56-174">8</span><span class="sxs-lookup"><span data-stu-id="88a56-174">8</span></span></td>
<td><span data-ttu-id="88a56-175">Utente</span><span class="sxs-lookup"><span data-stu-id="88a56-175">User</span></span></td>
<td><span data-ttu-id="88a56-176">Scaricare e installare l'app mobile.</span><span class="sxs-lookup"><span data-stu-id="88a56-176">Download and install the mobile app.</span></span></td>
<td><ul>
<li><span data-ttu-id="88a56-177"><a href="https://go.microsoft.com/fwlink/?linkid=850662">Per telefoni Android</a></span><span class="sxs-lookup"><span data-stu-id="88a56-177"><a href="https://go.microsoft.com/fwlink/?linkid=850662">For Android phones</a></span></span></li>
<li><span data-ttu-id="88a56-178"><a href="https://go.microsoft.com/fwlink/?linkid=850663">Per iPhone</a></span><span class="sxs-lookup"><span data-stu-id="88a56-178"><a href="https://go.microsoft.com/fwlink/?linkid=850663">For iPhones</a></span></span></li></ul>
</td>
</tr>
<tr class="odd">
<td><span data-ttu-id="88a56-179">9</span><span class="sxs-lookup"><span data-stu-id="88a56-179">9</span></span></td>
<td><span data-ttu-id="88a56-180">Utente</span><span class="sxs-lookup"><span data-stu-id="88a56-180">User</span></span></td>
<td><span data-ttu-id="88a56-181">Accedere all'app mobile ed utilizzarla.</span><span class="sxs-lookup"><span data-stu-id="88a56-181">Sign in, and use the mobile app.</span></span> <span data-ttu-id="88a56-182">L'app include le aree di lavoro mobili pubblicate dall'amministratore di sistema.</span><span class="sxs-lookup"><span data-stu-id="88a56-182">The app includes the mobile workspaces that have been published by the system administrator.</span></span></td>
<td><span data-ttu-id="88a56-183">Per visualizzare un elenco di aree di lavoro mobili fornite da Microsoft, vedere <a href="mobile-workspaces-released.md">Aree di lavoro mobili rilasciate di recente</a>.</span><span class="sxs-lookup"><span data-stu-id="88a56-183">To see a list of mobile workspaces that are provided by Microsoft, see <a href="mobile-workspaces-released.md">Mobile workspaces recently released</a>.</span></span>
</td>
</tr>
</tbody>
</table>

