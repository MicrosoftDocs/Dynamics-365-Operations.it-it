---
title: Creare un flusso di lavoro di richieste di acquisto e vendita di congedi
description: Creare un flusso di lavoro di richieste di acquisto e vendita di congedi per acquistare e vendere richieste di congedo in modo coerente in Dynamics 365 Human Resources.
author: andreabichsel
manager: tfehr
ms.date: 08/20/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: LeavePlanFormPart, LeaveAbsenceWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-08-20
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 16260c66c2e92fb06664a8f20a5fc3ed4a964609
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/17/2021
ms.locfileid: "5468133"
---
# <a name="create-a-buy-and-sell-leave-request-workflow"></a><span data-ttu-id="fb3d4-103">Creare un flusso di lavoro di richieste di acquisto e vendita di congedi</span><span class="sxs-lookup"><span data-stu-id="fb3d4-103">Create a buy and sell leave request workflow</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="fb3d4-104">È possibile creare un flusso di lavoro in Dynamics 365 Human Resources per gestire richieste di acquisto e vendita di congedi in modo coerente.</span><span class="sxs-lookup"><span data-stu-id="fb3d4-104">You can create a workflow in Dynamics 365 Human Resources to consistently manage your buy and sell leave requests.</span></span> <span data-ttu-id="fb3d4-105">Un flusso di lavoro **Acquista e vendi congedo** consente di:</span><span class="sxs-lookup"><span data-stu-id="fb3d4-105">A **Buy and sell leave** workflow lets you:</span></span>

- <span data-ttu-id="fb3d4-106">Definire attività</span><span class="sxs-lookup"><span data-stu-id="fb3d4-106">Define tasks</span></span>
- <span data-ttu-id="fb3d4-107">Determinare chi deve completare le attività</span><span class="sxs-lookup"><span data-stu-id="fb3d4-107">Determine who must complete the tasks</span></span>
- <span data-ttu-id="fb3d4-108">Specificare chi può approvare o rifiutare le richieste</span><span class="sxs-lookup"><span data-stu-id="fb3d4-108">Specify who can approve or reject requests</span></span>

## <a name="create-a-buy-and-sell-leave-request-workflow"></a><span data-ttu-id="fb3d4-109">Creare un flusso di lavoro di richieste di acquisto e vendita di congedi</span><span class="sxs-lookup"><span data-stu-id="fb3d4-109">Create a buy and sell leave request workflow</span></span>

1. <span data-ttu-id="fb3d4-110">Nella pagina **Congedo e assenza**, selezionare la scheda **Collegamenti**.</span><span class="sxs-lookup"><span data-stu-id="fb3d4-110">On the **Leave and absence** page, select the **Links** tab.</span></span>

2. <span data-ttu-id="fb3d4-111">Sotto **Impostazione**, selezionare **Flussi di lavoro risorse umane**.</span><span class="sxs-lookup"><span data-stu-id="fb3d4-111">Under **Setup**, select **Human resource workflows**.</span></span>

3. <span data-ttu-id="fb3d4-112">Selezionare **Nuovo**, quindi selezionare **Richiesta di acquisto e vendita di congedi**.</span><span class="sxs-lookup"><span data-stu-id="fb3d4-112">Select **New**, and then select **Buy and sell leave request**.</span></span> 

4. <span data-ttu-id="fb3d4-113">Quando viene visualizzato il messaggio **Aprire questo file?**, selezionare **Apri** e accedi con le credenziali dell'azienda.</span><span class="sxs-lookup"><span data-stu-id="fb3d4-113">When the **Open this file?** message box appears, select **Open** and sign in with your company credentials.</span></span>

5. <span data-ttu-id="fb3d4-114">Utilizzare l'editor di flusso di lavoro per creare un flusso di lavoro per le richieste di congedo.</span><span class="sxs-lookup"><span data-stu-id="fb3d4-114">Use the workflow editor to create a workflow for your leave requests.</span></span> <span data-ttu-id="fb3d4-115">Per ulteriori informazioni sull'uso dei flussi di lavoro, consultare [Panoramica di creazione di flussi di lavoro](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/create-workflow?toc=/dynamics365/commerce/toc.json.)</span><span class="sxs-lookup"><span data-stu-id="fb3d4-115">For more information about working with workflows, see [Create workflows overview](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/create-workflow?toc=/dynamics365/commerce/toc.json.)</span></span>

## <a name="leave-and-absence-request-workflow-data-elements"></a><span data-ttu-id="fb3d4-116">Elementi dati di flusso di lavoro di richieste di congedo e assenza</span><span class="sxs-lookup"><span data-stu-id="fb3d4-116">Leave and absence request workflow data elements</span></span>

<span data-ttu-id="fb3d4-117">È possibile utilizzare i seguenti elementi dati per creare approvazioni condizionali o automatiche nei flussi di lavoro per le richieste di acquisto e vendita di congedi:</span><span class="sxs-lookup"><span data-stu-id="fb3d4-117">You can use the following data elements to create conditional or automatic approvals in workflows for buy and sell leave requests:</span></span>

- <span data-ttu-id="fb3d4-118">**Importo**</span><span class="sxs-lookup"><span data-stu-id="fb3d4-118">**Amount**</span></span>
- <span data-ttu-id="fb3d4-119">**Criteri di acquisto e vendita congedo**</span><span class="sxs-lookup"><span data-stu-id="fb3d4-119">**Buy and sell leave policy**</span></span>
- <span data-ttu-id="fb3d4-120">**Società**</span><span class="sxs-lookup"><span data-stu-id="fb3d4-120">**Company**</span></span>
- <span data-ttu-id="fb3d4-121">**Creato da**</span><span class="sxs-lookup"><span data-stu-id="fb3d4-121">**Created by**</span></span>
- <span data-ttu-id="fb3d4-122">**Data e ora creazione**</span><span class="sxs-lookup"><span data-stu-id="fb3d4-122">**Created date and time**</span></span>
- <span data-ttu-id="fb3d4-123">**Data di fine**</span><span class="sxs-lookup"><span data-stu-id="fb3d4-123">**End date**</span></span>
- <span data-ttu-id="fb3d4-124">**Tipo di congedo**</span><span class="sxs-lookup"><span data-stu-id="fb3d4-124">**Leave type**</span></span>
- <span data-ttu-id="fb3d4-125">**Autore modifica**</span><span class="sxs-lookup"><span data-stu-id="fb3d4-125">**Modified by**</span></span>
- <span data-ttu-id="fb3d4-126">**Data e ora modifica**</span><span class="sxs-lookup"><span data-stu-id="fb3d4-126">**Modified date and time**</span></span>
- <span data-ttu-id="fb3d4-127">**ID richiesta**</span><span class="sxs-lookup"><span data-stu-id="fb3d4-127">**Request ID**</span></span>
- <span data-ttu-id="fb3d4-128">**Data di inizio**</span><span class="sxs-lookup"><span data-stu-id="fb3d4-128">**Start date**</span></span>
- <span data-ttu-id="fb3d4-129">**Stato**</span><span class="sxs-lookup"><span data-stu-id="fb3d4-129">**Status**</span></span> 
- <span data-ttu-id="fb3d4-130">**Data invio**</span><span class="sxs-lookup"><span data-stu-id="fb3d4-130">**Submission date**</span></span>
- <span data-ttu-id="fb3d4-131">**Inviata da**</span><span class="sxs-lookup"><span data-stu-id="fb3d4-131">**Submitted by**</span></span>
- <span data-ttu-id="fb3d4-132">**Inviata da Risorse umane**</span><span class="sxs-lookup"><span data-stu-id="fb3d4-132">**Submitted by Human resources**</span></span>
- <span data-ttu-id="fb3d4-133">**Inviata dal Responsabile**</span><span class="sxs-lookup"><span data-stu-id="fb3d4-133">**Submitted by Manager**</span></span>
- <span data-ttu-id="fb3d4-134">**Inviata per conto di**</span><span class="sxs-lookup"><span data-stu-id="fb3d4-134">**Submitted on behalf**</span></span>
- <span data-ttu-id="fb3d4-135">**Lavoro**</span><span class="sxs-lookup"><span data-stu-id="fb3d4-135">**Worker**</span></span>

## <a name="workflow-examples"></a><span data-ttu-id="fb3d4-136">Esempi di flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="fb3d4-136">Workflow examples</span></span>

<span data-ttu-id="fb3d4-137">Questi esempi mostrano come è possibile creare diversi tipi di condizioni di flusso di lavoro utilizzando questi elementi dati:</span><span class="sxs-lookup"><span data-stu-id="fb3d4-137">These examples show how you can create different types of workflow conditions by using these data elements:</span></span>

- <span data-ttu-id="fb3d4-138">Utilizzare **Inviata da Risorse umane** e **Inviata dal Responsabile** in un'azione automatica per approvare automaticamente le richieste di acquisto e vendita di congedi inviate da questi ruoli per conto dei dipendenti.</span><span class="sxs-lookup"><span data-stu-id="fb3d4-138">Use **Submitted by Human resources** and **Submitted by manager** in an automatic action to automatically approve buy and sell leave requests that these roles submit on behalf of employees.</span></span> <span data-ttu-id="fb3d4-139">Per ulteriori informazioni sulle azioni automatiche, vedere [Configurare i processi di approvazione in un flusso di lavoro](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/configure-approval-process-workflow).</span><span class="sxs-lookup"><span data-stu-id="fb3d4-139">For more information about automatic actions, see [Configure approval processes in a workflow](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/configure-approval-process-workflow).</span></span>

- <span data-ttu-id="fb3d4-140">Utilizzare **Tipo di congedo** in un'istruzione condizionale o in un'azione automatica per controllare il modo in cui il flusso di lavoro instrada le richieste con determinati tipi di congedo.</span><span class="sxs-lookup"><span data-stu-id="fb3d4-140">Use **Leave type** in a conditional statement or automatic action to control how the workflow routes requests with certain leave types.</span></span>

## <a name="see-also"></a><span data-ttu-id="fb3d4-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fb3d4-141">See also</span></span>

[<span data-ttu-id="fb3d4-142">Panoramica di congedo e assenza</span><span class="sxs-lookup"><span data-stu-id="fb3d4-142">Leave and absence overview</span></span>](hr-leave-and-absence-overview.md)<br>
[<span data-ttu-id="fb3d4-143">Gestire i criteri di acquisto e vendita congedo</span><span class="sxs-lookup"><span data-stu-id="fb3d4-143">Manage buy and sell leave policies</span></span>](hr-leave-and-absence-manage-buy-and-sell-leave-policies.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]