---
title: Creare un flusso di lavoro di richieste di congedo
description: Creare un flusso di lavoro di richieste di congedo e assenza per gestire richieste di congedo in modo coerente in Dynamics 365 Human Resources.
author: andreabichsel
manager: AnnBe
ms.date: 05/08/2020
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
ms.openlocfilehash: c985a0cb242fb6696b55a2514bd788ff4269f8ca
ms.sourcegitcommit: def66a9dc7feadd33411248af2545ee4a9e27c4f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "3385550"
---
# <a name="create-a-leave-request-workflow"></a><span data-ttu-id="ff462-103">Creare un flusso di lavoro di richieste di congedo</span><span class="sxs-lookup"><span data-stu-id="ff462-103">Create a leave request workflow</span></span>

<span data-ttu-id="ff462-104">È possibile creare un flusso di lavoro in Dynamics 365 Human Resources per gestire richieste di congedo e assenza in modo coerente.</span><span class="sxs-lookup"><span data-stu-id="ff462-104">You can create a workflow in Dynamics 365 Human Resources to consistently manage your leave and absence requests.</span></span> <span data-ttu-id="ff462-105">Un flusso di lavoro **Congedo e assenza** consente di:</span><span class="sxs-lookup"><span data-stu-id="ff462-105">A **Leave and absence** workflow lets you:</span></span>

- <span data-ttu-id="ff462-106">Definire attività</span><span class="sxs-lookup"><span data-stu-id="ff462-106">Define tasks</span></span>
- <span data-ttu-id="ff462-107">Determinare chi deve completare le attività</span><span class="sxs-lookup"><span data-stu-id="ff462-107">Determine who must complete the tasks</span></span>
- <span data-ttu-id="ff462-108">Specificare chi può approvare o rifiutare le richieste</span><span class="sxs-lookup"><span data-stu-id="ff462-108">Specify who can approve or reject requests</span></span>

## <a name="create-a-leave-and-absence-request-workflow"></a><span data-ttu-id="ff462-109">Creare un flusso di lavoro di richieste di congedo e assenza</span><span class="sxs-lookup"><span data-stu-id="ff462-109">Create a Leave and absence request workflow</span></span>

1. <span data-ttu-id="ff462-110">Nella pagina **Congedo e assenza**, selezionare la scheda **Collegamenti**.</span><span class="sxs-lookup"><span data-stu-id="ff462-110">On the **Leave and absence** page, select the **Links** tab.</span></span>

2. <span data-ttu-id="ff462-111">Sotto **Impostazione**, selezionare **Flussi di lavoro risorse umane**.</span><span class="sxs-lookup"><span data-stu-id="ff462-111">Under **Setup**, select **Human resource workflows**.</span></span>

3. <span data-ttu-id="ff462-112">Selezionare **Nuovo**, quindi selezionare **Richiesta di congedo e assenza**.</span><span class="sxs-lookup"><span data-stu-id="ff462-112">Select **New**, and then select **Leave and absence request**.</span></span> 

4. <span data-ttu-id="ff462-113">Quando viene visualizzato il messaggio **Aprire questo file?**, selezionare **Apri** e accedi con le credenziali dell'azienda.</span><span class="sxs-lookup"><span data-stu-id="ff462-113">When the **Open this file?** message box appears, select **Open** and sign in with your company credentials.</span></span>

5. <span data-ttu-id="ff462-114">Utilizzare l'editor di flusso di lavoro per creare un flusso di lavoro per le richieste di congedo.</span><span class="sxs-lookup"><span data-stu-id="ff462-114">Use the workflow editor to create a workflow for your leave requests.</span></span> <span data-ttu-id="ff462-115">Per ulteriori informazioni sull'uso dei flussi di lavoro, consultare [Panoramica di creazione di flussi di lavoro](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/create-workflow?toc=/dynamics365/commerce/toc.json.)</span><span class="sxs-lookup"><span data-stu-id="ff462-115">For more information about working with workflows, see [Create workflows overview](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/create-workflow?toc=/dynamics365/commerce/toc.json.)</span></span>

## <a name="leave-and-absence-request-workflow-data-elements"></a><span data-ttu-id="ff462-116">Elementi dati di flusso di lavoro di richieste di congedo e assenza</span><span class="sxs-lookup"><span data-stu-id="ff462-116">Leave and absence request workflow data elements</span></span>

<span data-ttu-id="ff462-117">È possibile utilizzare i seguenti elementi dati per creare approvazioni condizionali o automatiche nei flussi di lavoro per le richieste di congedo e assenza:</span><span class="sxs-lookup"><span data-stu-id="ff462-117">You can use the following data elements to create conditional or automatic approvals in workflows for leave and absence requests:</span></span>

- <span data-ttu-id="ff462-118">**Importo**</span><span class="sxs-lookup"><span data-stu-id="ff462-118">**Amount**</span></span>
- <span data-ttu-id="ff462-119">**Commento**</span><span class="sxs-lookup"><span data-stu-id="ff462-119">**Comment**</span></span>
- <span data-ttu-id="ff462-120">**Società**</span><span class="sxs-lookup"><span data-stu-id="ff462-120">**Company**</span></span>
- <span data-ttu-id="ff462-121">**Autore**</span><span class="sxs-lookup"><span data-stu-id="ff462-121">**Created by**</span></span>
- <span data-ttu-id="ff462-122">**Data e ora creazione**</span><span class="sxs-lookup"><span data-stu-id="ff462-122">**Created date and time**</span></span>
- <span data-ttu-id="ff462-123">**Data di fine**</span><span class="sxs-lookup"><span data-stu-id="ff462-123">**End date**</span></span>
- <span data-ttu-id="ff462-124">**Tipo di congedo**</span><span class="sxs-lookup"><span data-stu-id="ff462-124">**Leave type**</span></span>
- <span data-ttu-id="ff462-125">**Autore modifica**</span><span class="sxs-lookup"><span data-stu-id="ff462-125">**Modified by**</span></span>
- <span data-ttu-id="ff462-126">**Data e ora modifica**</span><span class="sxs-lookup"><span data-stu-id="ff462-126">**Modified date and time**</span></span>
- <span data-ttu-id="ff462-127">**Codice motivo**</span><span class="sxs-lookup"><span data-stu-id="ff462-127">**Reason code**</span></span>
- <span data-ttu-id="ff462-128">**ID richiesta**</span><span class="sxs-lookup"><span data-stu-id="ff462-128">**Request ID**</span></span>
- <span data-ttu-id="ff462-129">**Data di inizio**</span><span class="sxs-lookup"><span data-stu-id="ff462-129">**Start date**</span></span>
- <span data-ttu-id="ff462-130">**Stato**</span><span class="sxs-lookup"><span data-stu-id="ff462-130">**Status**</span></span> 
- <span data-ttu-id="ff462-131">**Data invio**</span><span class="sxs-lookup"><span data-stu-id="ff462-131">**Submission date**</span></span>
- <span data-ttu-id="ff462-132">**Inviata da**</span><span class="sxs-lookup"><span data-stu-id="ff462-132">**Submitted by**</span></span>
- <span data-ttu-id="ff462-133">**Inviata da Risorse umane**</span><span class="sxs-lookup"><span data-stu-id="ff462-133">**Submitted by Human resources**</span></span>
- <span data-ttu-id="ff462-134">**Inviata dal Responsabile**</span><span class="sxs-lookup"><span data-stu-id="ff462-134">**Submitted by Manager**</span></span>
- <span data-ttu-id="ff462-135">**Inviata per conto di**</span><span class="sxs-lookup"><span data-stu-id="ff462-135">**Submitted on behalf**</span></span>
- <span data-ttu-id="ff462-136">**Lavoro**</span><span class="sxs-lookup"><span data-stu-id="ff462-136">**Worker**</span></span>
- <span data-ttu-id="ff462-137">**Tipo di lavoratore**</span><span class="sxs-lookup"><span data-stu-id="ff462-137">**Worker type**</span></span>

<span data-ttu-id="ff462-138">Questi esempi mostrano come è possibile creare diversi tipi di condizioni di flusso di lavoro utilizzando questi elementi dati:</span><span class="sxs-lookup"><span data-stu-id="ff462-138">These examples show how you can create different types of workflow conditions by using these data elements:</span></span>

- <span data-ttu-id="ff462-139">Utilizzare **Codice motivo** in un'istruzione condizionale per instradare le richieste di congedo per malattia con il codice motivo **Chirurgia** alle Risorse umane ai fini dell'approvazione e instradare tutti gli altri codici motivo al responsabile.</span><span class="sxs-lookup"><span data-stu-id="ff462-139">Use **Reason code** in a conditional statement to route sick leave requests with the reason code **Surgery** to HR for approval, while routing all other reason codes to the manager.</span></span> <span data-ttu-id="ff462-140">Per ulteriori informazioni sulle istruzioni condizionali, vedere [Configurare le decisioni condizionali in un flusso di lavoro](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/configure-conditional-decision-workflow).</span><span class="sxs-lookup"><span data-stu-id="ff462-140">For more information about conditional statements, see [Configure conditional decisions in a workflow](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/configure-conditional-decision-workflow).</span></span> 

- <span data-ttu-id="ff462-141">Utilizzare **Inviata da Risorse umane** e **Inviata dal Responsabile** in un'azione automatica per approvare automaticamente le richieste di congedo inviate da questi ruoli per conto dei dipendenti.</span><span class="sxs-lookup"><span data-stu-id="ff462-141">Use **Submitted by Human resources** and **Submitted by manager** in an automatic action to automatically approve leave requests that these roles submit on behalf of employees.</span></span> <span data-ttu-id="ff462-142">Per ulteriori informazioni sulle azioni automatiche, vedere [Configurare i processi di approvazione in un flusso di lavoro](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/configure-approval-process-workflow).</span><span class="sxs-lookup"><span data-stu-id="ff462-142">For more information about automatic actions, see [Configure approval processes in a workflow](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/configure-approval-process-workflow).</span></span>

- <span data-ttu-id="ff462-143">Utilizzare **Tipo di congedo** in un'istruzione condizionale o in un'azione automatica per controllare il modo in cui il flusso di lavoro instrada le richieste con determinati tipi di congedo.</span><span class="sxs-lookup"><span data-stu-id="ff462-143">Use **Leave type** in a conditional statement or automatic action to control how the workflow routes requests with certain leave types.</span></span>

## <a name="see-also"></a><span data-ttu-id="ff462-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ff462-144">See also</span></span>

- [<span data-ttu-id="ff462-145">Panoramica di congedo e assenza</span><span class="sxs-lookup"><span data-stu-id="ff462-145">Leave and absence overview</span></span>](hr-leave-and-absence-overview.md)
