---
title: Panoramica di MyLeaveRequests
description: L'entità MyLeaveRequests in Microsoft Dynamics 365 Human Resources fornisce l'elenco delle richieste di congedo nel sistema, con ambito (limitato) alle richieste accessibili all'utente corrente che interroga l'entità.
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
ms.openlocfilehash: 4bf3b298af9eb39e03514a4005afb43a42908e47
ms.sourcegitcommit: f38302b9430f2ab3efe91d0a7beff946bc610e8f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2020
ms.locfileid: "3092039"
---
# <a name="myleaverequests-overview"></a><span data-ttu-id="0ca8e-103">Panoramica di MyLeaveRequests</span><span class="sxs-lookup"><span data-stu-id="0ca8e-103">MyLeaveRequests overview</span></span>

<span data-ttu-id="0ca8e-104">L'entità MyLeaveRequests in Microsoft Dynamics 365 Human Resources fornisce l'elenco delle richieste di congedo nel sistema, con ambito (limitato) alle richieste accessibili all'utente corrente che interroga l'entità.</span><span class="sxs-lookup"><span data-stu-id="0ca8e-104">The MyLeaveRequests entity in Microsoft Dynamics 365 Human Resources provides the list of Leave Requests in the system, scoped (limited) to the requests accessible to the current user querying the entity.</span></span>

## <a name="key"></a><span data-ttu-id="0ca8e-105">Chiave</span><span class="sxs-lookup"><span data-stu-id="0ca8e-105">Key</span></span>

  | <span data-ttu-id="0ca8e-106">Nome proprietà</span><span class="sxs-lookup"><span data-stu-id="0ca8e-106">Property Name</span></span> | <span data-ttu-id="0ca8e-107">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="0ca8e-107">Data Type</span></span> |
  |---------------|-----------|
  | <span data-ttu-id="0ca8e-108">dataAreaId</span><span class="sxs-lookup"><span data-stu-id="0ca8e-108">dataAreaId</span></span>    | <span data-ttu-id="0ca8e-109">Stringa</span><span class="sxs-lookup"><span data-stu-id="0ca8e-109">String</span></span>    |
  | <span data-ttu-id="0ca8e-110">RequestId</span><span class="sxs-lookup"><span data-stu-id="0ca8e-110">RequestId</span></span>     | <span data-ttu-id="0ca8e-111">Stringa</span><span class="sxs-lookup"><span data-stu-id="0ca8e-111">String</span></span>    |
  | <span data-ttu-id="0ca8e-112">LeaveType</span><span class="sxs-lookup"><span data-stu-id="0ca8e-112">LeaveType</span></span>     | <span data-ttu-id="0ca8e-113">Stringa</span><span class="sxs-lookup"><span data-stu-id="0ca8e-113">String</span></span>    |
  | <span data-ttu-id="0ca8e-114">LeaveDate</span><span class="sxs-lookup"><span data-stu-id="0ca8e-114">LeaveDate</span></span>     | <span data-ttu-id="0ca8e-115">Data</span><span class="sxs-lookup"><span data-stu-id="0ca8e-115">Date</span></span>      |
  
## <a name="properties"></a><span data-ttu-id="0ca8e-116">Proprietà</span><span class="sxs-lookup"><span data-stu-id="0ca8e-116">Properties</span></span>

  | <span data-ttu-id="0ca8e-117">Nome proprietà</span><span class="sxs-lookup"><span data-stu-id="0ca8e-117">Property Name</span></span>     | <span data-ttu-id="0ca8e-118">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="0ca8e-118">Data Type</span></span> | <span data-ttu-id="0ca8e-119">Obbligatorio</span><span class="sxs-lookup"><span data-stu-id="0ca8e-119">Required</span></span> |
  |-------------------|-----------|----------|
  | <span data-ttu-id="0ca8e-120">dataAreaId</span><span class="sxs-lookup"><span data-stu-id="0ca8e-120">dataAreaId</span></span>        | <span data-ttu-id="0ca8e-121">Stringa</span><span class="sxs-lookup"><span data-stu-id="0ca8e-121">String</span></span>    | <span data-ttu-id="0ca8e-122">X</span><span class="sxs-lookup"><span data-stu-id="0ca8e-122">X</span></span>        |
  | <span data-ttu-id="0ca8e-123">RequestId</span><span class="sxs-lookup"><span data-stu-id="0ca8e-123">RequestId</span></span>         | <span data-ttu-id="0ca8e-124">Stringa</span><span class="sxs-lookup"><span data-stu-id="0ca8e-124">String</span></span>    | <span data-ttu-id="0ca8e-125">X</span><span class="sxs-lookup"><span data-stu-id="0ca8e-125">X</span></span>        |
  | <span data-ttu-id="0ca8e-126">LeaveType</span><span class="sxs-lookup"><span data-stu-id="0ca8e-126">LeaveType</span></span>         | <span data-ttu-id="0ca8e-127">Stringa</span><span class="sxs-lookup"><span data-stu-id="0ca8e-127">String</span></span>    | <span data-ttu-id="0ca8e-128">X</span><span class="sxs-lookup"><span data-stu-id="0ca8e-128">X</span></span>        |
  | <span data-ttu-id="0ca8e-129">LeaveDate</span><span class="sxs-lookup"><span data-stu-id="0ca8e-129">LeaveDate</span></span>         | <span data-ttu-id="0ca8e-130">Data</span><span class="sxs-lookup"><span data-stu-id="0ca8e-130">Date</span></span>      | <span data-ttu-id="0ca8e-131">X</span><span class="sxs-lookup"><span data-stu-id="0ca8e-131">X</span></span>        |
  | <span data-ttu-id="0ca8e-132">ReasonCodeId</span><span class="sxs-lookup"><span data-stu-id="0ca8e-132">ReasonCodeId</span></span>      | <span data-ttu-id="0ca8e-133">Stringa</span><span class="sxs-lookup"><span data-stu-id="0ca8e-133">String</span></span>    |          |
  | <span data-ttu-id="0ca8e-134">PersonnelNumber</span><span class="sxs-lookup"><span data-stu-id="0ca8e-134">PersonnelNumber</span></span>   | <span data-ttu-id="0ca8e-135">Stringa</span><span class="sxs-lookup"><span data-stu-id="0ca8e-135">String</span></span>    | <span data-ttu-id="0ca8e-136">X</span><span class="sxs-lookup"><span data-stu-id="0ca8e-136">X</span></span>        |
  | <span data-ttu-id="0ca8e-137">RequestDate</span><span class="sxs-lookup"><span data-stu-id="0ca8e-137">RequestDate</span></span>       | <span data-ttu-id="0ca8e-138">Data</span><span class="sxs-lookup"><span data-stu-id="0ca8e-138">Date</span></span>      | <span data-ttu-id="0ca8e-139">X</span><span class="sxs-lookup"><span data-stu-id="0ca8e-139">X</span></span>        |
  | <span data-ttu-id="0ca8e-140">Commento</span><span class="sxs-lookup"><span data-stu-id="0ca8e-140">Comment</span></span>           | <span data-ttu-id="0ca8e-141">Stringa</span><span class="sxs-lookup"><span data-stu-id="0ca8e-141">String</span></span>    |          |
  | <span data-ttu-id="0ca8e-142">Stato</span><span class="sxs-lookup"><span data-stu-id="0ca8e-142">Status</span></span>            | <span data-ttu-id="0ca8e-143">Enumerazione</span><span class="sxs-lookup"><span data-stu-id="0ca8e-143">Enum</span></span>      | <span data-ttu-id="0ca8e-144">X</span><span class="sxs-lookup"><span data-stu-id="0ca8e-144">X</span></span>        |
  | <span data-ttu-id="0ca8e-145">Periodo</span><span class="sxs-lookup"><span data-stu-id="0ca8e-145">Amount</span></span>            | <span data-ttu-id="0ca8e-146">Reale</span><span class="sxs-lookup"><span data-stu-id="0ca8e-146">Real</span></span>      |          |
  | <span data-ttu-id="0ca8e-147">HalfDayDefinition</span><span class="sxs-lookup"><span data-stu-id="0ca8e-147">HalfDayDefinition</span></span> | <span data-ttu-id="0ca8e-148">Enumerazione</span><span class="sxs-lookup"><span data-stu-id="0ca8e-148">Enum</span></span>      |          |

## <a name="actions"></a><span data-ttu-id="0ca8e-149">Azioni</span><span class="sxs-lookup"><span data-stu-id="0ca8e-149">Actions</span></span>

 | <span data-ttu-id="0ca8e-150">Nome azione</span><span class="sxs-lookup"><span data-stu-id="0ca8e-150">Action Name</span></span>                               | <span data-ttu-id="0ca8e-151">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0ca8e-151">Description</span></span>                                     |
 |-------------------------------------------|-------------------------------------------------|
 | [<span data-ttu-id="0ca8e-152">Inoltra</span><span class="sxs-lookup"><span data-stu-id="0ca8e-152">submit</span></span>](hr-developer-api-myleaverequests-submit.md)   | <span data-ttu-id="0ca8e-153">Inoltrare la richiesta da elaborare per flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="0ca8e-153">Submit the request to be processed by workflow.</span></span> |

## <a name="see-also"></a><span data-ttu-id="0ca8e-154">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0ca8e-154">See also</span></span>

- [<span data-ttu-id="0ca8e-155">Inviare una richiesta di congedo a flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="0ca8e-155">Submit a leave request to workflow</span></span>](hr-developer-api-myleaverequests-submit.md)
- [<span data-ttu-id="0ca8e-156">Autenticazione</span><span class="sxs-lookup"><span data-stu-id="0ca8e-156">Authentication</span></span>](hr-developer-api-authentication.md)