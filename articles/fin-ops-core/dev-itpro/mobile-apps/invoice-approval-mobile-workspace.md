---
title: Area di lavoro mobile Approvazioni fatture
description: In questo argomento vengono fornite informazioni sull'area di lavoro mobile Approvazioni fatture.
author: abruer
ms.date: 12/01/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: c3414d6ef5f2df62f37f1ef2e7e2ff43ce040e5e
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5752252"
---
# <a name="invoice-approvals-mobile-workspace"></a><span data-ttu-id="d5a29-103">Area di lavoro mobile Approvazioni fatture</span><span class="sxs-lookup"><span data-stu-id="d5a29-103">Invoice approvals mobile workspace</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d5a29-104">In questo argomento vengono fornite informazioni sull'area di lavoro mobile **Approvazioni fatture**.</span><span class="sxs-lookup"><span data-stu-id="d5a29-104">This topic provides information about the **Invoice approvals** mobile workspace.</span></span> <span data-ttu-id="d5a29-105">Questa area di lavoro fornisce un elenco di fatture assegnate all'utente mediante il processo del flusso di lavoro di intestazione della fattura fornitore.</span><span class="sxs-lookup"><span data-stu-id="d5a29-105">This workspace provides a list of invoices that have been assigned to you through the vendor invoice header workflow process.</span></span> 

<span data-ttu-id="d5a29-106">Questa area di lavoro mobile può essere utilizzata con l'app Finance and Operations per dispositivi mobili.</span><span class="sxs-lookup"><span data-stu-id="d5a29-106">This mobile workspace is intended to be used with the Finance and Operations mobile app.</span></span>

## <a name="overview"></a><span data-ttu-id="d5a29-107">Panoramica</span><span class="sxs-lookup"><span data-stu-id="d5a29-107">Overview</span></span>

<span data-ttu-id="d5a29-108">L'area di lavoro mobile **Approvazioni fatture** consente a funzionari e responsabili della contabilità fornitori di visualizzare le fatture che sono state loro assegnate durante il processo del flusso di lavoro di intestazione della fattura fornitore.</span><span class="sxs-lookup"><span data-stu-id="d5a29-108">The **Invoice approvals** mobile workspace lets Accounts payable clerks and managers view invoices that have been assigned to them as part of the vendor invoice header workflow process.</span></span> <span data-ttu-id="d5a29-109">È possibile visualizzare informazioni sulle fatture e persino i dettagli di distribuzione e riga, che consentono di prendere decisioni di approvazione informate.</span><span class="sxs-lookup"><span data-stu-id="d5a29-109">You can view the invoice information, and even the line and distribution details, to help you make informed approval decisions.</span></span> <span data-ttu-id="d5a29-110">Nell'area di lavoro, è possibile spostare la fattura nel processo del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="d5a29-110">From the workspace, you can take action to move the invoice through the workflow process.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="d5a29-111">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="d5a29-111">Prerequisites</span></span>

<span data-ttu-id="d5a29-112">Per poter utilizzare questa area di lavoro mobile è necessario soddisfare i seguenti requisiti.</span><span class="sxs-lookup"><span data-stu-id="d5a29-112">Before you can use this mobile workspace, the following prerequisites must be met.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="d5a29-113">Prerequisito</span><span class="sxs-lookup"><span data-stu-id="d5a29-113">Prerequisite</span></span></th>
<th><span data-ttu-id="d5a29-114">Ruolo</span><span class="sxs-lookup"><span data-stu-id="d5a29-114">Role</span></span></th>
<th><span data-ttu-id="d5a29-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d5a29-115">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="d5a29-116">Microsoft Dynamics 365 Finance deve essere distribuito nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="d5a29-116">Microsoft Dynamics 365 Finance must be deployed in your organization.</span></span></td>
<td><span data-ttu-id="d5a29-117">Amministratore di sistema</span><span class="sxs-lookup"><span data-stu-id="d5a29-117">System administrator</span></span></td>
<td><span data-ttu-id="d5a29-118">Vedere <a href="../deployment/deploy-demo-environment.md">Distribuire un ambiente di dimostrazione</a>.</span><span class="sxs-lookup"><span data-stu-id="d5a29-118">See <a href="../deployment/deploy-demo-environment.md">Deploy a demo environment</a>.</span></span>
</td>
</tr>
<tr class="even">
<td><span data-ttu-id="d5a29-119">L'area di lavoro mobile <strong>Approvazioni fatture</strong> deve essere pubblicata.</span><span class="sxs-lookup"><span data-stu-id="d5a29-119">The <strong>Invoice approvals</strong> mobile workspace must be published.</span></span></td>
<td><span data-ttu-id="d5a29-120">Amministratore di sistema</span><span class="sxs-lookup"><span data-stu-id="d5a29-120">System administrator</span></span></td>
<td><span data-ttu-id="d5a29-121">Vedere <a href="publish-mobile-workspace.md">Pubblicare un'area di lavoro mobile</a>.</span><span class="sxs-lookup"><span data-stu-id="d5a29-121">See <a href="publish-mobile-workspace.md">Publish a mobile workspace</a>.</span></span></td>
</tr>
</tbody>
</table>

## <a name="download-and-install-the-mobile-app"></a><span data-ttu-id="d5a29-122">Scaricare e installare l'app per dispositivi mobili</span><span class="sxs-lookup"><span data-stu-id="d5a29-122">Download and install the mobile app</span></span>

<span data-ttu-id="d5a29-123">Scaricare e installare l'app Finance and Operations per dispositivi mobili:</span><span class="sxs-lookup"><span data-stu-id="d5a29-123">Download and install the Finance and Operations mobile app:</span></span>

-   [<span data-ttu-id="d5a29-124">Per telefoni Android</span><span class="sxs-lookup"><span data-stu-id="d5a29-124">For Android phones</span></span>](https://go.microsoft.com/fwlink/?linkid=850662)
-   [<span data-ttu-id="d5a29-125">Per iPhone</span><span class="sxs-lookup"><span data-stu-id="d5a29-125">For iPhones</span></span>](https://go.microsoft.com/fwlink/?linkid=850663)

## <a name="sign-in-to-the-mobile-app"></a><span data-ttu-id="d5a29-126">Accedere all'app mobile</span><span class="sxs-lookup"><span data-stu-id="d5a29-126">Sign in to the mobile app</span></span>

1.  <span data-ttu-id="d5a29-127">Avviare l'app sul dispositivo mobile.</span><span class="sxs-lookup"><span data-stu-id="d5a29-127">Start the app on your mobile device.</span></span>
2.  <span data-ttu-id="d5a29-128">Immettere il proprio URL Microsoft Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="d5a29-128">Enter your Microsoft Dynamics 365 URL.</span></span>
3.  <span data-ttu-id="d5a29-129">La prima volta che si accede viene richiesto di inserire il proprio nome utente e la password.</span><span class="sxs-lookup"><span data-stu-id="d5a29-129">The first time that you sign in, you're prompted for your user name and password.</span></span> <span data-ttu-id="d5a29-130">Immettere le proprie credenziali.</span><span class="sxs-lookup"><span data-stu-id="d5a29-130">Enter your credentials.</span></span>
4.  <span data-ttu-id="d5a29-131">Dopo avere effettuato l'accesso, vengono visualizzate le aree di lavoro disponibili per la società.</span><span class="sxs-lookup"><span data-stu-id="d5a29-131">After you sign in, the available workspaces for your company are shown.</span></span> <span data-ttu-id="d5a29-132">Nota: se l'amministratore di sistema pubblica una nuova area di lavoro in seguito, è necessario aggiornare l'elenco delle aree di lavoro mobili.</span><span class="sxs-lookup"><span data-stu-id="d5a29-132">Note that if your system administrator publishes a new workspace later, you will have to refresh the list of mobile workspaces.</span></span>

    <span data-ttu-id="d5a29-133">[![Effettuare il pull per l'aggiornamento](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)</span><span class="sxs-lookup"><span data-stu-id="d5a29-133">[![Pull to refresh](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)</span></span>

## <a name="approve-invoices-by-using-the-invoice-approvals-mobile-workspace"></a><span data-ttu-id="d5a29-134">Approvare fatture tramite l'area di lavoro Approvazioni fatture</span><span class="sxs-lookup"><span data-stu-id="d5a29-134">Approve invoices by using the Invoice approvals mobile workspace</span></span>
1.  <span data-ttu-id="d5a29-135">Sul dispositivo mobile, selezionare l'area di lavoro **Approvazioni fatture**.</span><span class="sxs-lookup"><span data-stu-id="d5a29-135">On your mobile device, select the **Invoice approvals** workspace.</span></span>
2.  <span data-ttu-id="d5a29-136">Selezionare la fattura assegnata dal processo del flusso di lavoro di intestazione della fattura fornitore.</span><span class="sxs-lookup"><span data-stu-id="d5a29-136">Select the invoice that has been assigned to you by the vendor invoice header workflow process.</span></span>
3.  <span data-ttu-id="d5a29-137">Nella pagina **Dettagli fattura**, rivedere le informazioni nell'intestazione della fattura, ad esempio informazioni sul fornitore e sulla data.</span><span class="sxs-lookup"><span data-stu-id="d5a29-137">On the **Invoice details** page, review the invoice header information, such as the vendor and date information.</span></span>
4.  <span data-ttu-id="d5a29-138">Selezionare una riga della fattura per visualizzare informazioni più dettagliate nella visualizzazione **Dettagli riga fattura**.</span><span class="sxs-lookup"><span data-stu-id="d5a29-138">Select a line on the invoice to view more detailed information about it in the **Invoice line details** view.</span></span>
5.  <span data-ttu-id="d5a29-139">Nella visualizzazione **Dettagli riga fattura**, selezionare **Distribuzioni** per mostrare le distribuzioni riga.</span><span class="sxs-lookup"><span data-stu-id="d5a29-139">In the **Invoice line details** view, select **Distributions** to show the line distributions.</span></span> <span data-ttu-id="d5a29-140">Qui, è possibile visualizzare la contabilità per la riga fattura.</span><span class="sxs-lookup"><span data-stu-id="d5a29-140">Here, you can view the accounting for the invoice line.</span></span> <span data-ttu-id="d5a29-141">Le informazioni visualizzate includono le dimensioni finanziarie e il conto principale.</span><span class="sxs-lookup"><span data-stu-id="d5a29-141">The information that is shown includes the financial dimensions and the main account.</span></span>
6.  <span data-ttu-id="d5a29-142">Nella pagina **Dettagli fattura**, selezionare **Distribuzioni** per mostrare tutte le distribuzioni.</span><span class="sxs-lookup"><span data-stu-id="d5a29-142">On the **Invoice details** page, select **Distributions** to show all distributions.</span></span> <span data-ttu-id="d5a29-143">Qui, è possibile visualizzare la contabilità per l'intera fattura.</span><span class="sxs-lookup"><span data-stu-id="d5a29-143">Here, you can view the accounting for the whole invoice.</span></span> <span data-ttu-id="d5a29-144">Le informazioni visualizzate includono le dimensioni finanziarie e i conti principali.</span><span class="sxs-lookup"><span data-stu-id="d5a29-144">The information that is shown includes the financial dimensions and the main accounts.</span></span> 
7.  <span data-ttu-id="d5a29-145">Selezionare **Allegati** per visualizzare tutti i file o note associati alla fattura.</span><span class="sxs-lookup"><span data-stu-id="d5a29-145">Select **Attachments** to view any notes or files that are attached to the invoice.</span></span>
8.  <span data-ttu-id="d5a29-146">Nella pagina **Dettagli fattura**, selezionare l'azione del flusso di lavoro appropriata per completare il processo di revisione.</span><span class="sxs-lookup"><span data-stu-id="d5a29-146">On the **Invoice details** page, select the appropriate workflow action to complete your review process.</span></span>
9.  <span data-ttu-id="d5a29-147">Selezionare **Fine**.</span><span class="sxs-lookup"><span data-stu-id="d5a29-147">Select **Done**.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]