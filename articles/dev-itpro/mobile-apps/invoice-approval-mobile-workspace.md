---
title: Area di lavoro mobile Approvazioni fatture
description: In questo argomento vengono fornite informazioni sull'area di lavoro mobile Approvazioni fatture. Questa area di lavoro fornisce un elenco di fatture assegnate all'utente mediante il processo del flusso di lavoro di intestazione della fattura fornitore.
author: abruer
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: af673f076f684500b6ca84d04c01f7f773d65cd6
ms.contentlocale: it-it
ms.lasthandoff: 11/03/2017

---

# <a name="invoice-approvals-mobile-workspace"></a><span data-ttu-id="83b86-104">Area di lavoro mobile Approvazioni fatture</span><span class="sxs-lookup"><span data-stu-id="83b86-104">Invoice approvals mobile workspace</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="83b86-105">In questo argomento vengono fornite informazioni sull'area di lavoro mobile **Approvazioni fatture**.</span><span class="sxs-lookup"><span data-stu-id="83b86-105">This topic provides information about the **Invoice approvals** mobile workspace.</span></span> <span data-ttu-id="83b86-106">Questa area di lavoro fornisce un elenco di fatture assegnate all'utente mediante il processo del flusso di lavoro di intestazione della fattura fornitore.</span><span class="sxs-lookup"><span data-stu-id="83b86-106">This workspace provides a list of invoices that have been assigned to you through the vendor invoice header workflow process.</span></span> 

<span data-ttu-id="83b86-107">Questa area di lavoro mobile può essere utilizzata con l'app mobile Microsoft Dynamics 365 for Unified Operations.</span><span class="sxs-lookup"><span data-stu-id="83b86-107">This mobile workspace is intended to be used with the Microsoft Dynamics 365 for Unified Operations mobile app.</span></span>

## <a name="overview"></a><span data-ttu-id="83b86-108">Panoramica</span><span class="sxs-lookup"><span data-stu-id="83b86-108">Overview</span></span>

<span data-ttu-id="83b86-109">L'area di lavoro mobile **Approvazioni fatture** consente a funzionari e responsabili della contabilità fornitori di visualizzare le fatture che sono state loro assegnate durante il processo del flusso di lavoro di intestazione della fattura fornitore.</span><span class="sxs-lookup"><span data-stu-id="83b86-109">The **Invoice approvals** mobile workspace lets Accounts payable clerks and managers view invoices that have been assigned to them as part of the vendor invoice header workflow process.</span></span> <span data-ttu-id="83b86-110">È possibile visualizzare informazioni sulle fatture e persino i dettagli di distribuzione e riga, che consentono di prendere decisioni di approvazione informate.</span><span class="sxs-lookup"><span data-stu-id="83b86-110">You can view the invoice information, and even the line and distribution details, to help you make informed approval decisions.</span></span> <span data-ttu-id="83b86-111">Nell'area di lavoro, è possibile spostare la fattura nel processo del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="83b86-111">From the workspace, you can take action to move the invoice through the workflow process.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="83b86-112">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="83b86-112">Prerequisites</span></span>

<span data-ttu-id="83b86-113">Per poter utilizzare questa area di lavoro mobile è necessario soddisfare i seguenti requisiti.</span><span class="sxs-lookup"><span data-stu-id="83b86-113">Before you can use this mobile workspace, the following prerequisites must be met.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="83b86-114">Prerequisito</span><span class="sxs-lookup"><span data-stu-id="83b86-114">Prerequisite</span></span></th>
<th><span data-ttu-id="83b86-115">Ruolo</span><span class="sxs-lookup"><span data-stu-id="83b86-115">Role</span></span></th>
<th><span data-ttu-id="83b86-116">descrizione</span><span class="sxs-lookup"><span data-stu-id="83b86-116">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="83b86-117">Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (luglio 2017) deve essere distribuito nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="83b86-117">Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (July 2017) must be deployed in your organization.</span></span></td>
<td><span data-ttu-id="83b86-118">Amministratore di sistema</span><span class="sxs-lookup"><span data-stu-id="83b86-118">System administrator</span></span></td>
<td><span data-ttu-id="83b86-119">Vedere <a href="../deployment/deploy-demo-environment.md">Distribuire un ambiente di dimostrazione</a>.</span><span class="sxs-lookup"><span data-stu-id="83b86-119">See <a href="../deployment/deploy-demo-environment.md">Deploy a demo environment</a>.</span></span>
</td>
</tr>
<tr class="even">
<td><span data-ttu-id="83b86-120">L'area di lavoro mobile <strong>Approvazioni fatture</strong> deve essere pubblicata.</span><span class="sxs-lookup"><span data-stu-id="83b86-120">The <strong>Invoice approvals</strong> mobile workspace must be published.</span></span></td>
<td><span data-ttu-id="83b86-121">Amministratore di sistema</span><span class="sxs-lookup"><span data-stu-id="83b86-121">System administrator</span></span></td>
<td><span data-ttu-id="83b86-122">Vedere <a href="publish-mobile-workspace.md">Pubblicare un'area di lavoro mobile</a>.</span><span class="sxs-lookup"><span data-stu-id="83b86-122">See <a href="publish-mobile-workspace.md">Publish a mobile workspace</a>.</span></span></td>
</tr>
</tbody>
</table>

## <a name="download-and-install-the-mobile-app"></a><span data-ttu-id="83b86-123">Scaricare e installare l'app mobile</span><span class="sxs-lookup"><span data-stu-id="83b86-123">Download and install the mobile app</span></span>

<span data-ttu-id="83b86-124">Scaricare e installare l'app mobile Dynamics 365 for Unified Operations:</span><span class="sxs-lookup"><span data-stu-id="83b86-124">Download and install the Dynamics 365 for Unified Operations mobile app:</span></span>

-   [<span data-ttu-id="83b86-125">Per telefoni Android</span><span class="sxs-lookup"><span data-stu-id="83b86-125">For Android phones</span></span>](https://go.microsoft.com/fwlink/?linkid=850662)
-   [<span data-ttu-id="83b86-126">Per iPhone</span><span class="sxs-lookup"><span data-stu-id="83b86-126">For iPhones</span></span>](https://go.microsoft.com/fwlink/?linkid=850663)

## <a name="sign-in-to-the-mobile-app"></a><span data-ttu-id="83b86-127">Accedere all'app mobile</span><span class="sxs-lookup"><span data-stu-id="83b86-127">Sign in to the mobile app</span></span>

1.  <span data-ttu-id="83b86-128">Avviare l'app sul dispositivo mobile.</span><span class="sxs-lookup"><span data-stu-id="83b86-128">Start the app on your mobile device.</span></span>
2.  <span data-ttu-id="83b86-129">Immettere il proprio URL Microsoft Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="83b86-129">Enter your Microsoft Dynamics 365 URL.</span></span>
3.  <span data-ttu-id="83b86-130">La prima volta che si accede viene richiesto di inserire il proprio nome utente e la password.</span><span class="sxs-lookup"><span data-stu-id="83b86-130">The first time that you sign in, you're prompted for your user name and password.</span></span> <span data-ttu-id="83b86-131">Immettere le proprie credenziali.</span><span class="sxs-lookup"><span data-stu-id="83b86-131">Enter your credentials.</span></span>
4.  <span data-ttu-id="83b86-132">Dopo avere effettuato l'accesso, vengono visualizzate le aree di lavoro disponibili per la società.</span><span class="sxs-lookup"><span data-stu-id="83b86-132">After you sign in, the available workspaces for your company are shown.</span></span> <span data-ttu-id="83b86-133">Nota: se l'amministratore di sistema pubblica una nuova area di lavoro in seguito, è necessario aggiornare l'elenco delle aree di lavoro mobili.</span><span class="sxs-lookup"><span data-stu-id="83b86-133">Note that if your system administrator publishes a new workspace later, you will have to refresh the list of mobile workspaces.</span></span>

    <span data-ttu-id="83b86-134">[![Effettuare il pull per l'aggiornamento](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)</span><span class="sxs-lookup"><span data-stu-id="83b86-134">[![Pull to refresh](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)</span></span>

## <a name="approve-invoices-by-using-the-invoice-approvals-mobile-workspace"></a><span data-ttu-id="83b86-135">Approvare fatture tramite l'area di lavoro Approvazioni fatture</span><span class="sxs-lookup"><span data-stu-id="83b86-135">Approve invoices by using the Invoice approvals mobile workspace</span></span>
1.  <span data-ttu-id="83b86-136">Sul dispositivo mobile, selezionare l'area di lavoro **Approvazioni fatture**.</span><span class="sxs-lookup"><span data-stu-id="83b86-136">On your mobile device, select the **Invoice approvals** workspace.</span></span>
2.  <span data-ttu-id="83b86-137">Selezionare la fattura assegnata dal processo del flusso di lavoro di intestazione della fattura fornitore.</span><span class="sxs-lookup"><span data-stu-id="83b86-137">Select the invoice that has been assigned to you by the vendor invoice header workflow process.</span></span>
3.  <span data-ttu-id="83b86-138">Nella pagina **Dettagli fattura**, rivedere le informazioni nell'intestazione della fattura, ad esempio informazioni sul fornitore e sulla data.</span><span class="sxs-lookup"><span data-stu-id="83b86-138">On the **Invoice details** page, review the invoice header information, such as the vendor and date information.</span></span>
4.  <span data-ttu-id="83b86-139">Selezionare una riga della fattura per visualizzare informazioni più dettagliate nella visualizzazione **Dettagli riga fattura**.</span><span class="sxs-lookup"><span data-stu-id="83b86-139">Select a line on the invoice to view more detailed information about it in the **Invoice line details** view.</span></span>
5.  <span data-ttu-id="83b86-140">Nella visualizzazione **Dettagli riga fattura**, selezionare **Distribuzioni** per mostrare le distribuzioni riga.</span><span class="sxs-lookup"><span data-stu-id="83b86-140">In the **Invoice line details** view, select **Distributions** to show the line distributions.</span></span> <span data-ttu-id="83b86-141">Qui, è possibile visualizzare la contabilità per la riga fattura.</span><span class="sxs-lookup"><span data-stu-id="83b86-141">Here, you can view the accounting for the invoice line.</span></span> <span data-ttu-id="83b86-142">Le informazioni visualizzate includono le dimensioni finanziarie e il conto principale.</span><span class="sxs-lookup"><span data-stu-id="83b86-142">The information that is shown includes the financial dimensions and the main account.</span></span>
6.  <span data-ttu-id="83b86-143">Nella pagina **Dettagli fattura**, selezionare **Distribuzioni** per mostrare tutte le distribuzioni.</span><span class="sxs-lookup"><span data-stu-id="83b86-143">On the **Invoice details** page, select **Distributions** to show all distributions.</span></span> <span data-ttu-id="83b86-144">Qui, è possibile visualizzare la contabilità per l'intera fattura.</span><span class="sxs-lookup"><span data-stu-id="83b86-144">Here, you can view the accounting for the whole invoice.</span></span> <span data-ttu-id="83b86-145">Le informazioni visualizzate includono le dimensioni finanziarie e i conti principali.</span><span class="sxs-lookup"><span data-stu-id="83b86-145">The information that is shown includes the financial dimensions and the main accounts.</span></span> 
7.  <span data-ttu-id="83b86-146">Selezionare **Allegati** per visualizzare tutti i file o note associati alla fattura.</span><span class="sxs-lookup"><span data-stu-id="83b86-146">Select **Attachments** to view any notes or files that are attached to the invoice.</span></span>
8.  <span data-ttu-id="83b86-147">Nella pagina **Dettagli fattura**, selezionare l'azione del flusso di lavoro appropriata per completare il processo di revisione.</span><span class="sxs-lookup"><span data-stu-id="83b86-147">On the **Invoice details** page, select the appropriate workflow action to complete your review process.</span></span>
9.  <span data-ttu-id="83b86-148">Selezionare **Fine**.</span><span class="sxs-lookup"><span data-stu-id="83b86-148">Select **Done**.</span></span>

