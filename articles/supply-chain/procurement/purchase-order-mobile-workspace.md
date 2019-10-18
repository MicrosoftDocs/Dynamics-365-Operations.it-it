---
title: Area di lavoro Approvazione ordine fornitore
description: In questo argomento vengono fornite informazioni sull'area di lavoro mobile Approvazione ordine fornitore, in cui è possibile visualizzare gli ordini fornitore ed effettuare le relative operazioni. Ad esempio, è possibile approvare o rifiutare un ordine fornitore.
author: mkirknel
manager: AnnBe
ms.date: 12/01/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchVendorPortalRequests
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 30211
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: b7f5d61ade071e75d53d5036a47fea438d8afbe6
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/30/2019
ms.locfileid: "2249427"
---
# <a name="purchase-order-approval-mobile-workspace"></a><span data-ttu-id="5b1a8-104">Area di lavoro Approvazione ordine fornitore</span><span class="sxs-lookup"><span data-stu-id="5b1a8-104">Purchase order approval mobile workspace</span></span>

[!include [banner](../includes/banner.md)]

[!include [retail name](../includes/retail-name.md)]

<span data-ttu-id="5b1a8-105">In questo argomento vengono fornite informazioni sull'area di lavoro mobile **Approvazione ordine fornitore**.</span><span class="sxs-lookup"><span data-stu-id="5b1a8-105">This topic provides information about the **Purchase order approval** mobile workspace.</span></span> <span data-ttu-id="5b1a8-106">Questa area di lavoro consente di visualizzare gli ordini fornitore ed effettuare le relative operazioni.</span><span class="sxs-lookup"><span data-stu-id="5b1a8-106">This workspace lets you view purchase orders and respond to them through actions.</span></span> <span data-ttu-id="5b1a8-107">Ad esempio, è possibile approvare o rifiutare un ordine fornitore.</span><span class="sxs-lookup"><span data-stu-id="5b1a8-107">For example, you can approve or reject a purchase order.</span></span>
 
## <a name="overview"></a><span data-ttu-id="5b1a8-108">Panoramica</span><span class="sxs-lookup"><span data-stu-id="5b1a8-108">Overview</span></span> 
<span data-ttu-id="5b1a8-109">Gli ordini fornitore che richiedono l'approvazione devono passare attraverso un flusso di lavoro di approvazione.</span><span class="sxs-lookup"><span data-stu-id="5b1a8-109">Purchase orders that requires approval go through an approval workflow.</span></span> <span data-ttu-id="5b1a8-110">Il flusso di lavoro può includere vari passaggi che richiedono l'esecuzione di operazioni da parte di una o più persone.</span><span class="sxs-lookup"><span data-stu-id="5b1a8-110">The workflow can include various steps that require that one or more people take action.</span></span> <span data-ttu-id="5b1a8-111">Ad esempio, una persona potrebbe dover completare un'attività o approvare l'ordine fornitore.</span><span class="sxs-lookup"><span data-stu-id="5b1a8-111">For example, a person might have to complete a task or approve the purchase order.</span></span> 

<span data-ttu-id="5b1a8-112">L'area di lavoro mobile **Approvazione di ordine fornitore** consente di visualizzare in modo semplice e rispondere agli ordini fornitore dal dispositivo mobile.</span><span class="sxs-lookup"><span data-stu-id="5b1a8-112">The **Purchase order approval** mobile workspace lets you easily view and respond to purchase orders from your mobile device.</span></span> <span data-ttu-id="5b1a8-113">Questa area di lavoro consente inoltre di effettuare le stesse azioni del flusso di lavoro che è possibile effettuare dal client Web.</span><span class="sxs-lookup"><span data-stu-id="5b1a8-113">This workspace also lets you take the same workflow actions that you can take from the web client.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="5b1a8-114">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="5b1a8-114">Prerequisites</span></span>
<span data-ttu-id="5b1a8-115">I prerequisiti variano a seconda della versione di Supply Chain Management che è stata installata nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="5b1a8-115">The prerequisites vary, depending on the version of Supply Chain Management that has been deployed for your organization.</span></span>

### <a name="prerequisites-if-you-use-supply-chain-management"></a><span data-ttu-id="5b1a8-116">Prerequisiti si utilizza Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="5b1a8-116">Prerequisites if you use Supply Chain Management</span></span> 
<span data-ttu-id="5b1a8-117">Se nell'organizzazione è stato distribuito Finance and Operations, l'amministratore di sistema deve pubblicare l'area di lavoro mobile **Approvazione ordine fornitore**.</span><span class="sxs-lookup"><span data-stu-id="5b1a8-117">If Finance and Operations has been deployed for your organization, the system administrator must publish the **Purchase order approval** mobile workspace.</span></span> <span data-ttu-id="5b1a8-118">Per istruzioni, vedere [Pubblicare un'area di lavoro mobile](../../dev-itpro/mobile-apps/publish-mobile-workspace.md).</span><span class="sxs-lookup"><span data-stu-id="5b1a8-118">For instructions, see [Publish a mobile workspace](../../dev-itpro/mobile-apps/publish-mobile-workspace.md).</span></span>

### <a name="prerequisites-if-you-use-microsoft-dynamics-365-for-operations-version-1611-with-platform-update-3-or-later"></a><span data-ttu-id="5b1a8-119">Prerequisiti se si usa Microsoft Dynamics 365 for Operations versione 1611 con Aggiornamento piattaforma 3 o versione successiva</span><span class="sxs-lookup"><span data-stu-id="5b1a8-119">Prerequisites if you use Microsoft Dynamics 365 for Operations version 1611 with Platform update 3 or later</span></span>
<span data-ttu-id="5b1a8-120">Se nell'organizzazione è stato distribuito Microsoft Dynamics 365 for Operations versione 1611 con Aggiornamento piattaforma 3 o versione successiva, l'amministratore di sistema deve soddisfare i prerequisiti seguenti.</span><span class="sxs-lookup"><span data-stu-id="5b1a8-120">If Microsoft Dynamics 365 for Operations version 1611 with Platform update 3 or later has been deployed for your organization, the system administrator must complete the following prerequisites.</span></span> 

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="5b1a8-121">Prerequisito</span><span class="sxs-lookup"><span data-stu-id="5b1a8-121">Prerequisite</span></span></th>
<th><span data-ttu-id="5b1a8-122">Ruolo</span><span class="sxs-lookup"><span data-stu-id="5b1a8-122">Role</span></span></th>
<th><span data-ttu-id="5b1a8-123">descrizione</span><span class="sxs-lookup"><span data-stu-id="5b1a8-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="5b1a8-124">Implementare l'articoloo KB 4017918.</span><span class="sxs-lookup"><span data-stu-id="5b1a8-124">Implement KB 4017918.</span></span></td>
<td><span data-ttu-id="5b1a8-125">Amministratore di sistema</span><span class="sxs-lookup"><span data-stu-id="5b1a8-125">System administrator</span></span></td>
<td><span data-ttu-id="5b1a8-126">l'articoloo KB 4017918 è un aggiornamento X++ o aggiornamento rapido dei metadati contenente l'area di lavoro mobile <strong>Approvazione ordine fornitore</strong>.</span><span class="sxs-lookup"><span data-stu-id="5b1a8-126">KB 4017918 is an X++ update or metadata hotfix that contains the <strong>Purchase order approval</strong> mobile workspace.</span></span> <span data-ttu-id="5b1a8-127">Per implementare l'articolo KB 4017918, l'amministratore di sistema deve completare i passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="5b1a8-127">To implement KB 4017918, your system administrator must follow these steps.</span></span>
<ol>
<li><span data-ttu-id="5b1a8-128"><a href="../../dev-itpro/migration-upgrade/download-hotfix-lcs.md">Scaricare l'hotfix metadati da Microsoft Dynamics Lifecycle Services (LCS)</a>.</span><span class="sxs-lookup"><span data-stu-id="5b1a8-128"><a href="../../dev-itpro/migration-upgrade/download-hotfix-lcs.md">Download the metadata hotfix from Microsoft Dynamics Lifecycle Services (LCS)</a>.</span></span></li>
<li><span data-ttu-id="5b1a8-129"><a href="../../dev-itpro/migration-upgrade/install-metadata-hotfix-package.md">Installare l'aggiornamento rapido dei metadati</a>.</span><span class="sxs-lookup"><span data-stu-id="5b1a8-129"><a href="../../dev-itpro/migration-upgrade/install-metadata-hotfix-package.md">Install the metadata hotfix</a>.</span></span></li>
<li><span data-ttu-id="5b1a8-130"><a href="../../dev-itpro/deployment/create-apply-deployable-package.md">Creare un pacchetto distribuibile</a> contenente il modello <strong>SCMMobile</strong> e quindi caricare il pacchetto distribuibile in LCS.</span><span class="sxs-lookup"><span data-stu-id="5b1a8-130"><a href="../../dev-itpro/deployment/create-apply-deployable-package.md">Create a deployable package</a> that contains the <strong>SCMMobile</strong> model, and then upload the deployable package to LCS.</span></span></li>
<li><span data-ttu-id="5b1a8-131"><a href="../../dev-itpro/deployment/apply-deployable-package-system.md">Applicare il pacchetto distribuibile</a>.</span><span class="sxs-lookup"><span data-stu-id="5b1a8-131"><a href="../../dev-itpro/deployment/apply-deployable-package-system.md">Apply the deployable package</a>.</span></span></li>
</ol></td>
</tr>
<tr class="even">
<td><span data-ttu-id="5b1a8-132">Pubblicare l'area di lavoro mobile <strong>Approvazione ordine fornitore</strong>.</span><span class="sxs-lookup"><span data-stu-id="5b1a8-132">Publish the <strong>Purchase order approval</strong> mobile workspace.</span></span></td>
<td><span data-ttu-id="5b1a8-133">Amministratore di sistema</span><span class="sxs-lookup"><span data-stu-id="5b1a8-133">System administrator</span></span></td>
<td><span data-ttu-id="5b1a8-134">Vedere <a href="../../dev-itpro/mobile-apps/publish-mobile-workspace.md">Pubblicare un'area di lavoro mobile</a>.</span><span class="sxs-lookup"><span data-stu-id="5b1a8-134">See <a href="../../dev-itpro/mobile-apps/publish-mobile-workspace.md">Publish a mobile workspace</a>.</span></span></td>
</tr>
</tbody>
</table>

## <a name="download-and-install-the-mobile-app"></a><span data-ttu-id="5b1a8-135">Scaricare e installare l'app per dispositivi mobili</span><span class="sxs-lookup"><span data-stu-id="5b1a8-135">Download and install the mobile app</span></span>
<span data-ttu-id="5b1a8-136">Scaricare e installare l'app Finance and Operations per dispositivi mobili:</span><span class="sxs-lookup"><span data-stu-id="5b1a8-136">Download and install the Finance and Operations mobile app:</span></span>

- [<span data-ttu-id="5b1a8-137">Per telefoni Android</span><span class="sxs-lookup"><span data-stu-id="5b1a8-137">For Android phones</span></span>](https://go.microsoft.com/fwlink/?linkid=850662)
- [<span data-ttu-id="5b1a8-138">Per iPhone</span><span class="sxs-lookup"><span data-stu-id="5b1a8-138">For iPhones</span></span>](https://go.microsoft.com/fwlink/?linkid=850663)


## <a name="sign-in-to-the-mobile-app"></a><span data-ttu-id="5b1a8-139">Accedere all'app mobile</span><span class="sxs-lookup"><span data-stu-id="5b1a8-139">Sign in to the mobile app</span></span>

1. <span data-ttu-id="5b1a8-140">Avviare l'app sul dispositivo mobile.</span><span class="sxs-lookup"><span data-stu-id="5b1a8-140">Start the app on your mobile device.</span></span>
2. <span data-ttu-id="5b1a8-141">Immettere il proprio URL Microsoft Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="5b1a8-141">Enter your Microsoft Dynamics 365 URL.</span></span>
3. <span data-ttu-id="5b1a8-142">La prima volta che si accede viene richiesto di inserire il proprio nome utente e la password.</span><span class="sxs-lookup"><span data-stu-id="5b1a8-142">The first time that you sign in, you're prompted for your user name and password.</span></span> <span data-ttu-id="5b1a8-143">Immettere le proprie credenziali.</span><span class="sxs-lookup"><span data-stu-id="5b1a8-143">Enter your credentials.</span></span>
4. <span data-ttu-id="5b1a8-144">Dopo avere effettuato l'accesso, vengono visualizzate le aree di lavoro disponibili per la società.</span><span class="sxs-lookup"><span data-stu-id="5b1a8-144">After you sign in, the available workspaces for your company are shown.</span></span> <span data-ttu-id="5b1a8-145">Nota: se l'amministratore di sistema pubblica una nuova area di lavoro in seguito, è necessario aggiornare l'elenco delle aree di lavoro mobili.</span><span class="sxs-lookup"><span data-stu-id="5b1a8-145">Note that if your system administrator publishes a new workspace later, you will have to refresh the list of mobile workspaces.</span></span>

![Area di lavoro Approvazione ordine fornitore nell'elenco delle aree di lavoro disponibili](./media/po-workspaces.png)

## <a name="view-orders-that-are-assigned-to-you"></a><span data-ttu-id="5b1a8-147">Visualizzare gli ordini assegnati all'utente</span><span class="sxs-lookup"><span data-stu-id="5b1a8-147">View orders that are assigned to you</span></span>
1. <span data-ttu-id="5b1a8-148">Sul dispositivo mobile, selezionare l'area di lavoro **Approvazione ordine fornitore**.</span><span class="sxs-lookup"><span data-stu-id="5b1a8-148">On your mobile device, select the **Purchase order approval** workspace.</span></span>
2. <span data-ttu-id="5b1a8-149">Selezionare **Ordini assegnati all'utente** per visualizzare tutti gli ordini fornitore per cui all'utente è stato richiesto di eseguire azioni del flusso di lavoro di approvazione dell'ordine fornitore.</span><span class="sxs-lookup"><span data-stu-id="5b1a8-149">Select **Orders assigned to me** to view all the purchase orders for which you've been asked to take action in the purchase order approval workflow.</span></span>
3. <span data-ttu-id="5b1a8-150">Selezionare un ordine.</span><span class="sxs-lookup"><span data-stu-id="5b1a8-150">Select an order.</span></span> <span data-ttu-id="5b1a8-151">Nella pagina **Dettagli ordine**, sarà possibile visualizzare le informazioni e le righe dell'intestazione dell'ordine.</span><span class="sxs-lookup"><span data-stu-id="5b1a8-151">On the **Order details** page, you will see the order header information and lines.</span></span> <span data-ttu-id="5b1a8-152">È inoltre possibile trovare le linee guida all'attività del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="5b1a8-152">You can also find guidelines from the workflow task.</span></span>
4. <span data-ttu-id="5b1a8-153">Selezionare **Distribuzioni contabili** per aprire la pagina **Distribuzione contabile intestazione**.</span><span class="sxs-lookup"><span data-stu-id="5b1a8-153">Select **Accounting distributions** to open the **Header accounting distributions** page.</span></span>
5. <span data-ttu-id="5b1a8-154">Tornare alla pagina **Dettagli ordine** e selezionare una riga.</span><span class="sxs-lookup"><span data-stu-id="5b1a8-154">Return to the **Order details** page, and select a line.</span></span> <span data-ttu-id="5b1a8-155">Dai dettagli della riga ordine, è possibile esplorare le distribuzioni contabili specifiche della riga.</span><span class="sxs-lookup"><span data-stu-id="5b1a8-155">From the order line details, you can also explore the line-specific accounting distributions.</span></span>

## <a name="complete-an-action-on-the-purchase-order"></a><span data-ttu-id="5b1a8-156">Completare un'azione sull'ordine fornitore</span><span class="sxs-lookup"><span data-stu-id="5b1a8-156">Complete an action on the purchase order</span></span>
<span data-ttu-id="5b1a8-157">Dopo avere visualizzato l'ordine fornitore assegnato all'utente e letto le istruzioni relative al flusso di lavoro, s è pronti per eseguire un'azione.</span><span class="sxs-lookup"><span data-stu-id="5b1a8-157">After you've viewed the purchase order that is assigned to you and read the workflow instructions, you should be ready to take action.</span></span>

1. <span data-ttu-id="5b1a8-158">Sul dispositivo mobile, selezionare l'area di lavoro **Approvazione ordine fornitore**.</span><span class="sxs-lookup"><span data-stu-id="5b1a8-158">On your mobile device, select the **Purchase order approval** workspace.</span></span>
2. <span data-ttu-id="5b1a8-159">Selezionare **Ordini assegnati all'utente** per visualizzare tutti gli ordini fornitore per cui all'utente è stato richiesto di eseguire azioni del flusso di lavoro di approvazione dell'ordine fornitore.</span><span class="sxs-lookup"><span data-stu-id="5b1a8-159">Select **Orders assigned to me** to view all the purchase orders for which you've been asked to take action in the purchase order approval workflow.</span></span>
3. <span data-ttu-id="5b1a8-160">Selezionare un ordine e visualizzare la pagina dei dettagli.</span><span class="sxs-lookup"><span data-stu-id="5b1a8-160">Select an order, and view the details page.</span></span>
4. <span data-ttu-id="5b1a8-161">Selezionare **Azioni** per visualizzare le azioni disponibili.</span><span class="sxs-lookup"><span data-stu-id="5b1a8-161">Select **Actions** to show the available actions.</span></span> <span data-ttu-id="5b1a8-162">Le azioni disponibili variano a seconda dell'attività assegnata all'utente.</span><span class="sxs-lookup"><span data-stu-id="5b1a8-162">The actions that are available depend on the task that has been assigned to you.</span></span>

    | <span data-ttu-id="5b1a8-163">Azione di attività</span><span class="sxs-lookup"><span data-stu-id="5b1a8-163">Task action</span></span>    | <span data-ttu-id="5b1a8-164">Azione approvazione</span><span class="sxs-lookup"><span data-stu-id="5b1a8-164">Approval action</span></span>  |
    |----------------|------------------|
    | <span data-ttu-id="5b1a8-165">Completata</span><span class="sxs-lookup"><span data-stu-id="5b1a8-165">Complete</span></span>       | <span data-ttu-id="5b1a8-166">Approva</span><span class="sxs-lookup"><span data-stu-id="5b1a8-166">Approve</span></span>          |
    | <span data-ttu-id="5b1a8-167">Restituita</span><span class="sxs-lookup"><span data-stu-id="5b1a8-167">Return</span></span>         | <span data-ttu-id="5b1a8-168">Rifiuta</span><span class="sxs-lookup"><span data-stu-id="5b1a8-168">Reject</span></span>           |
    | <span data-ttu-id="5b1a8-169">Richiedi modifica</span><span class="sxs-lookup"><span data-stu-id="5b1a8-169">Request change</span></span> | <span data-ttu-id="5b1a8-170">Richiedi modifica</span><span class="sxs-lookup"><span data-stu-id="5b1a8-170">Request change</span></span>   |
    | <span data-ttu-id="5b1a8-171">Delegata</span><span class="sxs-lookup"><span data-stu-id="5b1a8-171">Delegate</span></span>       | <span data-ttu-id="5b1a8-172">Delegata</span><span class="sxs-lookup"><span data-stu-id="5b1a8-172">Delegate</span></span>         |

5. <span data-ttu-id="5b1a8-173">Selezionare l'azione appropriata.</span><span class="sxs-lookup"><span data-stu-id="5b1a8-173">Select the appropriate action.</span></span>
6. <span data-ttu-id="5b1a8-174">Nella pagina **Completa attività**, immettere un commento.</span><span class="sxs-lookup"><span data-stu-id="5b1a8-174">On the **Complete task** page, enter a comment.</span></span> <span data-ttu-id="5b1a8-175">Se si seleziona l'azione **Delega**, è necessario selezionare un utente a cui delegare l'attività.</span><span class="sxs-lookup"><span data-stu-id="5b1a8-175">Note that if you select the **Delegate** action, you must select a user to delegate the task to.</span></span>
7. <span data-ttu-id="5b1a8-176">Selezionare **Fine**.</span><span class="sxs-lookup"><span data-stu-id="5b1a8-176">Select **Done**.</span></span> <span data-ttu-id="5b1a8-177">Dopo aver aggiornato l'area di lavoro, l'ordine fornitore non sarà più in elenco.</span><span class="sxs-lookup"><span data-stu-id="5b1a8-177">After you refresh your workspace, the purchase order will no longer be in your list.</span></span> 
