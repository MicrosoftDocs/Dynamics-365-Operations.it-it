---
title: Area di lavoro Approvazione ordine fornitore
description: "In questo argomento vengono fornite informazioni sull'area di lavoro mobile Approvazione ordine fornitore, in cui è possibile visualizzare gli ordini fornitore ed effettuare le relative operazioni. Ad esempio, è possibile approvare o rifiutare un ordine fornitore."
author: mkirknel
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PurchTable, PurchVendorPortalRequests
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, Operations, Retail
ms.custom: 30211
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 60744c2b90e64ac77155ba28cdc4fcf65fee1bb6
ms.contentlocale: it-it
ms.lasthandoff: 11/03/2017

---

# <a name="purchase-order-approval-mobile-workspace"></a><span data-ttu-id="b0c50-104">Area di lavoro Approvazione ordine fornitore</span><span class="sxs-lookup"><span data-stu-id="b0c50-104">Purchase order approval mobile workspace</span></span>

[!include[banner](../includes/banner.md)]

[!include[retail name](../includes/retail-name.md)]

<span data-ttu-id="b0c50-105">In questo argomento vengono fornite informazioni sull'area di lavoro mobile **Approvazione ordine fornitore**.</span><span class="sxs-lookup"><span data-stu-id="b0c50-105">This topic provides information about the **Purchase order approval** mobile workspace.</span></span> <span data-ttu-id="b0c50-106">Questa area di lavoro consente di visualizzare gli ordini fornitore ed effettuare le relative operazioni.</span><span class="sxs-lookup"><span data-stu-id="b0c50-106">This workspace lets you view purchase orders and respond to them through actions.</span></span> <span data-ttu-id="b0c50-107">Ad esempio, è possibile approvare o rifiutare un ordine fornitore.</span><span class="sxs-lookup"><span data-stu-id="b0c50-107">For example, you can approve or reject a purchase order.</span></span>
 
## <a name="overview"></a><span data-ttu-id="b0c50-108">Panoramica</span><span class="sxs-lookup"><span data-stu-id="b0c50-108">Overview</span></span> 
<span data-ttu-id="b0c50-109">Gli ordini fornitore che richiedono l'approvazione devono passare attraverso un flusso di lavoro di approvazione.</span><span class="sxs-lookup"><span data-stu-id="b0c50-109">Purchase orders that requires approval go through an approval workflow.</span></span> <span data-ttu-id="b0c50-110">Il flusso di lavoro può includere vari passaggi che richiedono l'esecuzione di operazioni da parte di una o più persone.</span><span class="sxs-lookup"><span data-stu-id="b0c50-110">The workflow can include various steps that require that one or more people take action.</span></span> <span data-ttu-id="b0c50-111">Ad esempio, una persona potrebbe dover completare un'attività o approvare l'ordine fornitore.</span><span class="sxs-lookup"><span data-stu-id="b0c50-111">For example, a person might have to complete a task or approve the purchase order.</span></span> 

<span data-ttu-id="b0c50-112">L'area di lavoro mobile **Approvazione di ordine fornitore** consente di visualizzare in modo semplice e rispondere agli ordini fornitore dal dispositivo mobile.</span><span class="sxs-lookup"><span data-stu-id="b0c50-112">The **Purchase order approval** mobile workspace lets you easily view and respond to purchase orders from your mobile device.</span></span> <span data-ttu-id="b0c50-113">Questa area di lavoro consente inoltre di effettuare le stesse azioni del flusso di lavoro che è possibile effettuare da Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition, client Web.</span><span class="sxs-lookup"><span data-stu-id="b0c50-113">This workspace also lets you take the same workflow actions that you can take from the Microsoft Dynamics 365 for Finance and Operations, Enterprise edition, web client.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b0c50-114">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="b0c50-114">Prerequisites</span></span>
<span data-ttu-id="b0c50-115">I prerequisiti variano a seconda della versione di Finance and Operations che è stata installata nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="b0c50-115">The prerequisites vary, depending on the version of Finance and Operations that has been deployed for your organization.</span></span>

### <a name="prerequisites-if-you-use-microsoft-dynamics-365-for-finance-and-operations-enterprise-edition-july-2017"></a><span data-ttu-id="b0c50-116">Prerequisiti se si usa l'Aggiornamento di Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (luglio 2017)</span><span class="sxs-lookup"><span data-stu-id="b0c50-116">Prerequisites if you use Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (July 2017)</span></span> 
<span data-ttu-id="b0c50-117">Se nell'organizzazione è stato distribuito Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (luglio 2017), l'amministratore di sistema deve pubblicare l'area di lavoro mobile **Approvazione ordine fornitore**.</span><span class="sxs-lookup"><span data-stu-id="b0c50-117">If Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (July 2017), has been deployed for your organization, the system administrator must publish the **Purchase order approval** mobile workspace.</span></span> <span data-ttu-id="b0c50-118">Per istruzioni, vedere [Pubblicare un'area di lavoro mobile](../../dev-itpro/mobile-apps/publish-mobile-workspace.md).</span><span class="sxs-lookup"><span data-stu-id="b0c50-118">For instructions, see [Publish a mobile workspace](../../dev-itpro/mobile-apps/publish-mobile-workspace.md).</span></span>

### <a name="prerequisites-if-you-use-microsoft-dynamics-365-for-operations-version-1611-with-platform-update-3-or-later"></a><span data-ttu-id="b0c50-119">Prerequisiti se si usa Microsoft Dynamics 365 for Operations versione 1611 con Aggiornamento piattaforma 3 o versione successiva</span><span class="sxs-lookup"><span data-stu-id="b0c50-119">Prerequisites if you use Microsoft Dynamics 365 for Operations version 1611 with Platform update 3 or later</span></span>
<span data-ttu-id="b0c50-120">Se nell'organizzazione è stato distribuito Microsoft Dynamics 365 for Operations versione 1611 con Aggiornamento piattaforma 3 o versione successiva, l'amministratore di sistema deve soddisfare i prerequisiti seguenti.</span><span class="sxs-lookup"><span data-stu-id="b0c50-120">If Microsoft Dynamics 365 for Operations version 1611 with Platform update 3 or later has been deployed for your organization, the system administrator must complete the following prerequisites.</span></span> 

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="b0c50-121">Prerequisito</span><span class="sxs-lookup"><span data-stu-id="b0c50-121">Prerequisite</span></span></th>
<th><span data-ttu-id="b0c50-122">Ruolo</span><span class="sxs-lookup"><span data-stu-id="b0c50-122">Role</span></span></th>
<th><span data-ttu-id="b0c50-123">descrizione</span><span class="sxs-lookup"><span data-stu-id="b0c50-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="b0c50-124">Implementare l'articoloo KB 4017918.</span><span class="sxs-lookup"><span data-stu-id="b0c50-124">Implement KB 4017918.</span></span></td>
<td><span data-ttu-id="b0c50-125">Amministratore di sistema</span><span class="sxs-lookup"><span data-stu-id="b0c50-125">System administrator</span></span></td>
<td><span data-ttu-id="b0c50-126">l'articoloo KB 4017918 è un aggiornamento X++ o aggiornamento rapido dei metadati contenente l'area di lavoro mobile <strong>Approvazione ordine fornitore</strong>.</span><span class="sxs-lookup"><span data-stu-id="b0c50-126">KB 4017918 is an X++ update or metadata hotfix that contains the <strong>Purchase order approval</strong> mobile workspace.</span></span> <span data-ttu-id="b0c50-127">Per implementare l'articolo KB 4017918, l'amministratore di sistema deve completare i passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="b0c50-127">To implement KB 4017918, your system administrator must follow these steps.</span></span>
<ol>
<li><span data-ttu-id="b0c50-128"><a href="../../dev-itpro/migration-upgrade/download-hotfix-lcs.md">Scaricare l'hotfix metadati da Microsoft Dynamics Lifecycle Services (LCS)</a>.</span><span class="sxs-lookup"><span data-stu-id="b0c50-128"><a href="../../dev-itpro/migration-upgrade/download-hotfix-lcs.md">Download the metadata hotfix from Microsoft Dynamics Lifecycle Services (LCS)</a>.</span></span></li>
<li><span data-ttu-id="b0c50-129"><a href="../../dev-itpro/migration-upgrade/install-metadata-hotfix-package.md">Installare l'aggiornamento rapido dei metadati</a>.</span><span class="sxs-lookup"><span data-stu-id="b0c50-129"><a href="../../dev-itpro/migration-upgrade/install-metadata-hotfix-package.md">Install the metadata hotfix</a>.</span></span></li>
<li><span data-ttu-id="b0c50-130"><a href="../../dev-itpro/deployment/create-apply-deployable-package.md">Creare un pacchetto distribuibile</a> contenente il modello <strong>SCMMobile</strong> e quindi caricare il pacchetto distribuibile in LCS.</span><span class="sxs-lookup"><span data-stu-id="b0c50-130"><a href="../../dev-itpro/deployment/create-apply-deployable-package.md">Create a deployable package</a> that contains the <strong>SCMMobile</strong> model, and then upload the deployable package to LCS.</span></span></li>
<li><span data-ttu-id="b0c50-131"><a href="../../dev-itpro/deployment/apply-deployable-package-system.md">Applicare il pacchetto distribuibile</a>.</span><span class="sxs-lookup"><span data-stu-id="b0c50-131"><a href="../../dev-itpro/deployment/apply-deployable-package-system.md">Apply the deployable package</a>.</span></span></li>
</ol></td>
</tr>
<tr class="even">
<td><span data-ttu-id="b0c50-132">Pubblicare l'area di lavoro mobile <strong>Approvazione ordine fornitore</strong>.</span><span class="sxs-lookup"><span data-stu-id="b0c50-132">Publish the <strong>Purchase order approval</strong> mobile workspace.</span></span></td>
<td><span data-ttu-id="b0c50-133">Amministratore di sistema</span><span class="sxs-lookup"><span data-stu-id="b0c50-133">System administrator</span></span></td>
<td><span data-ttu-id="b0c50-134">Vedere <a href="../../dev-itpro/mobile-apps/publish-mobile-workspace.md">Pubblicare un'area di lavoro mobile</a>.</span><span class="sxs-lookup"><span data-stu-id="b0c50-134">See <a href="../../dev-itpro/mobile-apps/publish-mobile-workspace.md">Publish a mobile workspace</a>.</span></span></td>
</tr>
</tbody>
</table>

## <a name="download-and-install-the-mobile-app"></a><span data-ttu-id="b0c50-135">Scaricare e installare l'app mobile</span><span class="sxs-lookup"><span data-stu-id="b0c50-135">Download and install the mobile app</span></span>
<span data-ttu-id="b0c50-136">Scaricare e installare l'app mobile Microsoft Dynamics 365 for Unified Operations:</span><span class="sxs-lookup"><span data-stu-id="b0c50-136">Download and install the Microsoft Dynamics 365 for Unified Operations mobile app:</span></span>

- [<span data-ttu-id="b0c50-137">Per telefoni Android</span><span class="sxs-lookup"><span data-stu-id="b0c50-137">For Android phones</span></span>](https://go.microsoft.com/fwlink/?linkid=850662)
- [<span data-ttu-id="b0c50-138">Per iPhone</span><span class="sxs-lookup"><span data-stu-id="b0c50-138">For iPhones</span></span>](https://go.microsoft.com/fwlink/?linkid=850663)


## <a name="sign-in-to-the-mobile-app"></a><span data-ttu-id="b0c50-139">Accedere all'app mobile</span><span class="sxs-lookup"><span data-stu-id="b0c50-139">Sign in to the mobile app</span></span>

1. <span data-ttu-id="b0c50-140">Avviare l'app sul dispositivo mobile.</span><span class="sxs-lookup"><span data-stu-id="b0c50-140">Start the app on your mobile device.</span></span>
2. <span data-ttu-id="b0c50-141">Immettere il proprio URL Microsoft Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="b0c50-141">Enter your Microsoft Dynamics 365 URL.</span></span>
3. <span data-ttu-id="b0c50-142">La prima volta che si accede viene richiesto di inserire il proprio nome utente e la password.</span><span class="sxs-lookup"><span data-stu-id="b0c50-142">The first time that you sign in, you're prompted for your user name and password.</span></span> <span data-ttu-id="b0c50-143">Immettere le proprie credenziali.</span><span class="sxs-lookup"><span data-stu-id="b0c50-143">Enter your credentials.</span></span>
4. <span data-ttu-id="b0c50-144">Dopo avere effettuato l'accesso, vengono visualizzate le aree di lavoro disponibili per la società.</span><span class="sxs-lookup"><span data-stu-id="b0c50-144">After you sign in, the available workspaces for your company are shown.</span></span> <span data-ttu-id="b0c50-145">Nota: se l'amministratore di sistema pubblica una nuova area di lavoro in seguito, è necessario aggiornare l'elenco delle aree di lavoro mobili.</span><span class="sxs-lookup"><span data-stu-id="b0c50-145">Note that if your system administrator publishes a new workspace later, you will have to refresh the list of mobile workspaces.</span></span>

![Area di lavoro Approvazione ordine fornitore nell'elenco delle aree di lavoro disponibili](./media/po-workspaces.png)

## <a name="view-orders-that-are-assigned-to-you"></a><span data-ttu-id="b0c50-147">Visualizzare gli ordini assegnati all'utente</span><span class="sxs-lookup"><span data-stu-id="b0c50-147">View orders that are assigned to you</span></span>
1. <span data-ttu-id="b0c50-148">Sul dispositivo mobile, selezionare l'area di lavoro **Approvazione ordine fornitore**.</span><span class="sxs-lookup"><span data-stu-id="b0c50-148">On your mobile device, select the **Purchase order approval** workspace.</span></span>
2. <span data-ttu-id="b0c50-149">Selezionare **Ordini assegnati all'utente** per visualizzare tutti gli ordini fornitore per cui all'utente è stato richiesto di eseguire azioni del flusso di lavoro di approvazione dell'ordine fornitore.</span><span class="sxs-lookup"><span data-stu-id="b0c50-149">Select **Orders assigned to me** to view all the purchase orders for which you've been asked to take action in the purchase order approval workflow.</span></span>
3. <span data-ttu-id="b0c50-150">Selezionare un ordine.</span><span class="sxs-lookup"><span data-stu-id="b0c50-150">Select an order.</span></span> <span data-ttu-id="b0c50-151">Nella pagina **Dettagli ordine**, sarà possibile visualizzare le informazioni e le righe dell'intestazione dell'ordine.</span><span class="sxs-lookup"><span data-stu-id="b0c50-151">On the **Order details** page, you will see the order header information and lines.</span></span> <span data-ttu-id="b0c50-152">È inoltre possibile trovare le linee guida all'attività del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="b0c50-152">You can also find guidelines from the workflow task.</span></span>
4. <span data-ttu-id="b0c50-153">Selezionare **Distribuzioni contabili** per aprire la pagina **Distribuzione contabile intestazione**.</span><span class="sxs-lookup"><span data-stu-id="b0c50-153">Select **Accounting distributions** to open the **Header accounting distributions** page.</span></span>
5. <span data-ttu-id="b0c50-154">Tornare alla pagina **Dettagli ordine** e selezionare una riga.</span><span class="sxs-lookup"><span data-stu-id="b0c50-154">Return to the **Order details** page, and select a line.</span></span> <span data-ttu-id="b0c50-155">Dai dettagli della riga ordine, è possibile esplorare le distribuzioni contabili specifiche della riga.</span><span class="sxs-lookup"><span data-stu-id="b0c50-155">From the order line details, you can also explore the line-specific accounting distributions.</span></span>

## <a name="complete-an-action-on-the-purchase-order"></a><span data-ttu-id="b0c50-156">Completare un'azione sull'ordine fornitore</span><span class="sxs-lookup"><span data-stu-id="b0c50-156">Complete an action on the purchase order</span></span>
<span data-ttu-id="b0c50-157">Dopo avere visualizzato l'ordine fornitore assegnato all'utente e letto le istruzioni relative al flusso di lavoro, s è pronti per eseguire un'azione.</span><span class="sxs-lookup"><span data-stu-id="b0c50-157">After you've viewed the purchase order that is assigned to you and read the workflow instructions, you should be ready to take action.</span></span>

1. <span data-ttu-id="b0c50-158">Sul dispositivo mobile, selezionare l'area di lavoro **Approvazione ordine fornitore**.</span><span class="sxs-lookup"><span data-stu-id="b0c50-158">On your mobile device, select the **Purchase order approval** workspace.</span></span>
2. <span data-ttu-id="b0c50-159">Selezionare **Ordini assegnati all'utente** per visualizzare tutti gli ordini fornitore per cui all'utente è stato richiesto di eseguire azioni del flusso di lavoro di approvazione dell'ordine fornitore.</span><span class="sxs-lookup"><span data-stu-id="b0c50-159">Select **Orders assigned to me** to view all the purchase orders for which you've been asked to take action in the purchase order approval workflow.</span></span>
3. <span data-ttu-id="b0c50-160">Selezionare un ordine e visualizzare la pagina dei dettagli.</span><span class="sxs-lookup"><span data-stu-id="b0c50-160">Select an order, and view the details page.</span></span>
4. <span data-ttu-id="b0c50-161">Selezionare **Azioni** per visualizzare le azioni disponibili.</span><span class="sxs-lookup"><span data-stu-id="b0c50-161">Select **Actions** to show the available actions.</span></span> <span data-ttu-id="b0c50-162">Le azioni disponibili variano a seconda dell'attività assegnata all'utente.</span><span class="sxs-lookup"><span data-stu-id="b0c50-162">The actions that are available depend on the task that has been assigned to you.</span></span>

    | <span data-ttu-id="b0c50-163">Azione di attività</span><span class="sxs-lookup"><span data-stu-id="b0c50-163">Task action</span></span>    | <span data-ttu-id="b0c50-164">Azione approvazione</span><span class="sxs-lookup"><span data-stu-id="b0c50-164">Approval action</span></span>  |
    |----------------|------------------|
    | <span data-ttu-id="b0c50-165">Completata</span><span class="sxs-lookup"><span data-stu-id="b0c50-165">Complete</span></span>       | <span data-ttu-id="b0c50-166">Approva</span><span class="sxs-lookup"><span data-stu-id="b0c50-166">Approve</span></span>          |
    | <span data-ttu-id="b0c50-167">Restituita</span><span class="sxs-lookup"><span data-stu-id="b0c50-167">Return</span></span>         | <span data-ttu-id="b0c50-168">Rifiuta</span><span class="sxs-lookup"><span data-stu-id="b0c50-168">Reject</span></span>           |
    | <span data-ttu-id="b0c50-169">Richiedi modifica</span><span class="sxs-lookup"><span data-stu-id="b0c50-169">Request change</span></span> | <span data-ttu-id="b0c50-170">Richiedi modifica</span><span class="sxs-lookup"><span data-stu-id="b0c50-170">Request change</span></span>   |
    | <span data-ttu-id="b0c50-171">Delegata</span><span class="sxs-lookup"><span data-stu-id="b0c50-171">Delegate</span></span>       | <span data-ttu-id="b0c50-172">Delegata</span><span class="sxs-lookup"><span data-stu-id="b0c50-172">Delegate</span></span>         |

5. <span data-ttu-id="b0c50-173">Selezionare l'azione appropriata.</span><span class="sxs-lookup"><span data-stu-id="b0c50-173">Select the appropriate action.</span></span>
6. <span data-ttu-id="b0c50-174">Nella pagina **Completa attività**, immettere un commento.</span><span class="sxs-lookup"><span data-stu-id="b0c50-174">On the **Complete task** page, enter a comment.</span></span> <span data-ttu-id="b0c50-175">Se si seleziona l'azione **Delega**, è necessario selezionare un utente a cui delegare l'attività.</span><span class="sxs-lookup"><span data-stu-id="b0c50-175">Note that if you select the **Delegate** action, you must select a user to delegate the task to.</span></span>
7. <span data-ttu-id="b0c50-176">Selezionare **Fine**.</span><span class="sxs-lookup"><span data-stu-id="b0c50-176">Select **Done**.</span></span> <span data-ttu-id="b0c50-177">Dopo aver aggiornato l'area di lavoro, l'ordine fornitore non sarà più in elenco.</span><span class="sxs-lookup"><span data-stu-id="b0c50-177">After you refresh your workspace, the purchase order will no longer be in your list.</span></span> 

