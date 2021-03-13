---
title: Panoramica di MyLeaveRequests
description: L'entità MyLeaveRequests in Microsoft Dynamics 365 Human Resources fornisce l'elenco delle richieste di congedo nel sistema, con ambito (limitato) alle richieste accessibili all'utente corrente che interroga l'entità.
author: andreabichsel
manager: tfehr
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
ms.openlocfilehash: 0ca5bc225400338e76faee41a279e91fc00ce570
ms.sourcegitcommit: 18e626c49ccfdb12c1484b985e3a275e51f61320
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2021
ms.locfileid: "5115538"
---
# <a name="myleaverequests-overview"></a><span data-ttu-id="0ae7e-103">Panoramica di MyLeaveRequests</span><span class="sxs-lookup"><span data-stu-id="0ae7e-103">MyLeaveRequests overview</span></span>

<span data-ttu-id="0ae7e-104">L'entità MyLeaveRequests in Microsoft Dynamics 365 Human Resources fornisce l'elenco delle richieste di congedo nel sistema, con ambito (limitato) alle richieste accessibili all'utente corrente che interroga l'entità.</span><span class="sxs-lookup"><span data-stu-id="0ae7e-104">The MyLeaveRequests entity in Microsoft Dynamics 365 Human Resources provides the list of Leave Requests in the system, scoped (limited) to the requests accessible to the current user querying the entity.</span></span>

## <a name="key"></a><span data-ttu-id="0ae7e-105">Chiave</span><span class="sxs-lookup"><span data-stu-id="0ae7e-105">Key</span></span>

  | <span data-ttu-id="0ae7e-106">Nome proprietà</span><span class="sxs-lookup"><span data-stu-id="0ae7e-106">Property Name</span></span> | <span data-ttu-id="0ae7e-107">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="0ae7e-107">Data Type</span></span> |
  |---------------|-----------|
  | <span data-ttu-id="0ae7e-108">dataAreaId</span><span class="sxs-lookup"><span data-stu-id="0ae7e-108">dataAreaId</span></span>    | <span data-ttu-id="0ae7e-109">Stringa</span><span class="sxs-lookup"><span data-stu-id="0ae7e-109">String</span></span>    |
  | <span data-ttu-id="0ae7e-110">RequestId</span><span class="sxs-lookup"><span data-stu-id="0ae7e-110">RequestId</span></span>     | <span data-ttu-id="0ae7e-111">Stringa</span><span class="sxs-lookup"><span data-stu-id="0ae7e-111">String</span></span>    |
  | <span data-ttu-id="0ae7e-112">LeaveType</span><span class="sxs-lookup"><span data-stu-id="0ae7e-112">LeaveType</span></span>     | <span data-ttu-id="0ae7e-113">Stringa</span><span class="sxs-lookup"><span data-stu-id="0ae7e-113">String</span></span>    |
  | <span data-ttu-id="0ae7e-114">LeaveDate</span><span class="sxs-lookup"><span data-stu-id="0ae7e-114">LeaveDate</span></span>     | <span data-ttu-id="0ae7e-115">Data</span><span class="sxs-lookup"><span data-stu-id="0ae7e-115">Date</span></span>      |
  
## <a name="properties"></a><span data-ttu-id="0ae7e-116">Proprietà</span><span class="sxs-lookup"><span data-stu-id="0ae7e-116">Properties</span></span>

  | <span data-ttu-id="0ae7e-117">Nome proprietà</span><span class="sxs-lookup"><span data-stu-id="0ae7e-117">Property Name</span></span>     | <span data-ttu-id="0ae7e-118">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="0ae7e-118">Data Type</span></span> | <span data-ttu-id="0ae7e-119">Obbligatorio</span><span class="sxs-lookup"><span data-stu-id="0ae7e-119">Required</span></span> |
  |-------------------|-----------|----------|
  | <span data-ttu-id="0ae7e-120">dataAreaId</span><span class="sxs-lookup"><span data-stu-id="0ae7e-120">dataAreaId</span></span>        | <span data-ttu-id="0ae7e-121">Stringa</span><span class="sxs-lookup"><span data-stu-id="0ae7e-121">String</span></span>    | <span data-ttu-id="0ae7e-122">X</span><span class="sxs-lookup"><span data-stu-id="0ae7e-122">X</span></span>        |
  | <span data-ttu-id="0ae7e-123">RequestId</span><span class="sxs-lookup"><span data-stu-id="0ae7e-123">RequestId</span></span>         | <span data-ttu-id="0ae7e-124">Stringa</span><span class="sxs-lookup"><span data-stu-id="0ae7e-124">String</span></span>    | <span data-ttu-id="0ae7e-125">X</span><span class="sxs-lookup"><span data-stu-id="0ae7e-125">X</span></span>        |
  | <span data-ttu-id="0ae7e-126">LeaveType</span><span class="sxs-lookup"><span data-stu-id="0ae7e-126">LeaveType</span></span>         | <span data-ttu-id="0ae7e-127">Stringa</span><span class="sxs-lookup"><span data-stu-id="0ae7e-127">String</span></span>    | <span data-ttu-id="0ae7e-128">X</span><span class="sxs-lookup"><span data-stu-id="0ae7e-128">X</span></span>        |
  | <span data-ttu-id="0ae7e-129">LeaveDate</span><span class="sxs-lookup"><span data-stu-id="0ae7e-129">LeaveDate</span></span>         | <span data-ttu-id="0ae7e-130">Data</span><span class="sxs-lookup"><span data-stu-id="0ae7e-130">Date</span></span>      | <span data-ttu-id="0ae7e-131">X</span><span class="sxs-lookup"><span data-stu-id="0ae7e-131">X</span></span>        |
  | <span data-ttu-id="0ae7e-132">ReasonCodeId</span><span class="sxs-lookup"><span data-stu-id="0ae7e-132">ReasonCodeId</span></span>      | <span data-ttu-id="0ae7e-133">Stringa</span><span class="sxs-lookup"><span data-stu-id="0ae7e-133">String</span></span>    |          |
  | <span data-ttu-id="0ae7e-134">PersonnelNumber</span><span class="sxs-lookup"><span data-stu-id="0ae7e-134">PersonnelNumber</span></span>   | <span data-ttu-id="0ae7e-135">Stringa</span><span class="sxs-lookup"><span data-stu-id="0ae7e-135">String</span></span>    | <span data-ttu-id="0ae7e-136">X</span><span class="sxs-lookup"><span data-stu-id="0ae7e-136">X</span></span>        |
  | <span data-ttu-id="0ae7e-137">RequestDate</span><span class="sxs-lookup"><span data-stu-id="0ae7e-137">RequestDate</span></span>       | <span data-ttu-id="0ae7e-138">Data</span><span class="sxs-lookup"><span data-stu-id="0ae7e-138">Date</span></span>      | <span data-ttu-id="0ae7e-139">X</span><span class="sxs-lookup"><span data-stu-id="0ae7e-139">X</span></span>        |
  | <span data-ttu-id="0ae7e-140">Commento</span><span class="sxs-lookup"><span data-stu-id="0ae7e-140">Comment</span></span>           | <span data-ttu-id="0ae7e-141">Stringa</span><span class="sxs-lookup"><span data-stu-id="0ae7e-141">String</span></span>    |          |
  | <span data-ttu-id="0ae7e-142">Stato</span><span class="sxs-lookup"><span data-stu-id="0ae7e-142">Status</span></span>            | <span data-ttu-id="0ae7e-143">Enumerazione</span><span class="sxs-lookup"><span data-stu-id="0ae7e-143">Enum</span></span>      | <span data-ttu-id="0ae7e-144">X</span><span class="sxs-lookup"><span data-stu-id="0ae7e-144">X</span></span>        |
  | <span data-ttu-id="0ae7e-145">Periodo</span><span class="sxs-lookup"><span data-stu-id="0ae7e-145">Amount</span></span>            | <span data-ttu-id="0ae7e-146">Reale</span><span class="sxs-lookup"><span data-stu-id="0ae7e-146">Real</span></span>      |          |
  | <span data-ttu-id="0ae7e-147">HalfDayDefinition</span><span class="sxs-lookup"><span data-stu-id="0ae7e-147">HalfDayDefinition</span></span> | <span data-ttu-id="0ae7e-148">Enumerazione</span><span class="sxs-lookup"><span data-stu-id="0ae7e-148">Enum</span></span>      |          |

## <a name="actions"></a><span data-ttu-id="0ae7e-149">Azioni</span><span class="sxs-lookup"><span data-stu-id="0ae7e-149">Actions</span></span>

 | <span data-ttu-id="0ae7e-150">Nome azione</span><span class="sxs-lookup"><span data-stu-id="0ae7e-150">Action Name</span></span>                               | <span data-ttu-id="0ae7e-151">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0ae7e-151">Description</span></span>                                     |
 |-------------------------------------------|-------------------------------------------------|
 | [<span data-ttu-id="0ae7e-152">Inoltra</span><span class="sxs-lookup"><span data-stu-id="0ae7e-152">submit</span></span>](hr-developer-api-myleaverequests-submit.md)   | <span data-ttu-id="0ae7e-153">Inoltrare la richiesta da elaborare per flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="0ae7e-153">Submit the request to be processed by workflow.</span></span> |

## <a name="see-also"></a><span data-ttu-id="0ae7e-154">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0ae7e-154">See also</span></span>

- [<span data-ttu-id="0ae7e-155">Inviare una richiesta di congedo a flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="0ae7e-155">Submit a leave request to workflow</span></span>](hr-developer-api-myleaverequests-submit.md)
- [<span data-ttu-id="0ae7e-156">Autenticazione</span><span class="sxs-lookup"><span data-stu-id="0ae7e-156">Authentication</span></span>](hr-developer-api-authentication.md)