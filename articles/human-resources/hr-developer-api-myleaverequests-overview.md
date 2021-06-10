---
title: Panoramica di MyLeaveRequests
description: L'entità MyLeaveRequests in Microsoft Dynamics 365 Human Resources fornisce l'elenco delle richieste di congedo nel sistema, con ambito (limitato) alle richieste accessibili all'utente corrente che interroga l'entità.
author: andreabichsel
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: f29d5cf1469b58b4ea1837dc82b9513f5c002609
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/18/2021
ms.locfileid: "6054958"
---
# <a name="myleaverequests-overview"></a><span data-ttu-id="eebd4-103">Panoramica di MyLeaveRequests</span><span class="sxs-lookup"><span data-stu-id="eebd4-103">MyLeaveRequests overview</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="eebd4-104">L'entità MyLeaveRequests in Microsoft Dynamics 365 Human Resources fornisce l'elenco delle richieste di congedo nel sistema, con ambito (limitato) alle richieste accessibili all'utente corrente che interroga l'entità.</span><span class="sxs-lookup"><span data-stu-id="eebd4-104">The MyLeaveRequests entity in Microsoft Dynamics 365 Human Resources provides the list of Leave Requests in the system, scoped (limited) to the requests accessible to the current user querying the entity.</span></span>

## <a name="key"></a><span data-ttu-id="eebd4-105">Chiave</span><span class="sxs-lookup"><span data-stu-id="eebd4-105">Key</span></span>

  | <span data-ttu-id="eebd4-106">Nome proprietà</span><span class="sxs-lookup"><span data-stu-id="eebd4-106">Property Name</span></span> | <span data-ttu-id="eebd4-107">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="eebd4-107">Data Type</span></span> |
  |---------------|-----------|
  | <span data-ttu-id="eebd4-108">dataAreaId</span><span class="sxs-lookup"><span data-stu-id="eebd4-108">dataAreaId</span></span>    | <span data-ttu-id="eebd4-109">Stringa</span><span class="sxs-lookup"><span data-stu-id="eebd4-109">String</span></span>    |
  | <span data-ttu-id="eebd4-110">RequestId</span><span class="sxs-lookup"><span data-stu-id="eebd4-110">RequestId</span></span>     | <span data-ttu-id="eebd4-111">Stringa</span><span class="sxs-lookup"><span data-stu-id="eebd4-111">String</span></span>    |
  | <span data-ttu-id="eebd4-112">LeaveType</span><span class="sxs-lookup"><span data-stu-id="eebd4-112">LeaveType</span></span>     | <span data-ttu-id="eebd4-113">Stringa</span><span class="sxs-lookup"><span data-stu-id="eebd4-113">String</span></span>    |
  | <span data-ttu-id="eebd4-114">LeaveDate</span><span class="sxs-lookup"><span data-stu-id="eebd4-114">LeaveDate</span></span>     | <span data-ttu-id="eebd4-115">Data</span><span class="sxs-lookup"><span data-stu-id="eebd4-115">Date</span></span>      |
  
## <a name="properties"></a><span data-ttu-id="eebd4-116">Proprietà</span><span class="sxs-lookup"><span data-stu-id="eebd4-116">Properties</span></span>

  | <span data-ttu-id="eebd4-117">Nome proprietà</span><span class="sxs-lookup"><span data-stu-id="eebd4-117">Property Name</span></span>     | <span data-ttu-id="eebd4-118">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="eebd4-118">Data Type</span></span> | <span data-ttu-id="eebd4-119">Obbligatorio</span><span class="sxs-lookup"><span data-stu-id="eebd4-119">Required</span></span> |
  |-------------------|-----------|----------|
  | <span data-ttu-id="eebd4-120">dataAreaId</span><span class="sxs-lookup"><span data-stu-id="eebd4-120">dataAreaId</span></span>        | <span data-ttu-id="eebd4-121">Stringa</span><span class="sxs-lookup"><span data-stu-id="eebd4-121">String</span></span>    | <span data-ttu-id="eebd4-122">X</span><span class="sxs-lookup"><span data-stu-id="eebd4-122">X</span></span>        |
  | <span data-ttu-id="eebd4-123">RequestId</span><span class="sxs-lookup"><span data-stu-id="eebd4-123">RequestId</span></span>         | <span data-ttu-id="eebd4-124">Stringa</span><span class="sxs-lookup"><span data-stu-id="eebd4-124">String</span></span>    | <span data-ttu-id="eebd4-125">X</span><span class="sxs-lookup"><span data-stu-id="eebd4-125">X</span></span>        |
  | <span data-ttu-id="eebd4-126">LeaveType</span><span class="sxs-lookup"><span data-stu-id="eebd4-126">LeaveType</span></span>         | <span data-ttu-id="eebd4-127">Stringa</span><span class="sxs-lookup"><span data-stu-id="eebd4-127">String</span></span>    | <span data-ttu-id="eebd4-128">X</span><span class="sxs-lookup"><span data-stu-id="eebd4-128">X</span></span>        |
  | <span data-ttu-id="eebd4-129">LeaveDate</span><span class="sxs-lookup"><span data-stu-id="eebd4-129">LeaveDate</span></span>         | <span data-ttu-id="eebd4-130">Data</span><span class="sxs-lookup"><span data-stu-id="eebd4-130">Date</span></span>      | <span data-ttu-id="eebd4-131">X</span><span class="sxs-lookup"><span data-stu-id="eebd4-131">X</span></span>        |
  | <span data-ttu-id="eebd4-132">ReasonCodeId</span><span class="sxs-lookup"><span data-stu-id="eebd4-132">ReasonCodeId</span></span>      | <span data-ttu-id="eebd4-133">Stringa</span><span class="sxs-lookup"><span data-stu-id="eebd4-133">String</span></span>    |          |
  | <span data-ttu-id="eebd4-134">PersonnelNumber</span><span class="sxs-lookup"><span data-stu-id="eebd4-134">PersonnelNumber</span></span>   | <span data-ttu-id="eebd4-135">Stringa</span><span class="sxs-lookup"><span data-stu-id="eebd4-135">String</span></span>    | <span data-ttu-id="eebd4-136">X</span><span class="sxs-lookup"><span data-stu-id="eebd4-136">X</span></span>        |
  | <span data-ttu-id="eebd4-137">RequestDate</span><span class="sxs-lookup"><span data-stu-id="eebd4-137">RequestDate</span></span>       | <span data-ttu-id="eebd4-138">Data</span><span class="sxs-lookup"><span data-stu-id="eebd4-138">Date</span></span>      | <span data-ttu-id="eebd4-139">X</span><span class="sxs-lookup"><span data-stu-id="eebd4-139">X</span></span>        |
  | <span data-ttu-id="eebd4-140">Commento</span><span class="sxs-lookup"><span data-stu-id="eebd4-140">Comment</span></span>           | <span data-ttu-id="eebd4-141">Stringa</span><span class="sxs-lookup"><span data-stu-id="eebd4-141">String</span></span>    |          |
  | <span data-ttu-id="eebd4-142">Stato</span><span class="sxs-lookup"><span data-stu-id="eebd4-142">Status</span></span>            | <span data-ttu-id="eebd4-143">Enumerazione</span><span class="sxs-lookup"><span data-stu-id="eebd4-143">Enum</span></span>      | <span data-ttu-id="eebd4-144">X</span><span class="sxs-lookup"><span data-stu-id="eebd4-144">X</span></span>        |
  | <span data-ttu-id="eebd4-145">Periodo</span><span class="sxs-lookup"><span data-stu-id="eebd4-145">Amount</span></span>            | <span data-ttu-id="eebd4-146">Reale</span><span class="sxs-lookup"><span data-stu-id="eebd4-146">Real</span></span>      |          |
  | <span data-ttu-id="eebd4-147">HalfDayDefinition</span><span class="sxs-lookup"><span data-stu-id="eebd4-147">HalfDayDefinition</span></span> | <span data-ttu-id="eebd4-148">Enumerazione</span><span class="sxs-lookup"><span data-stu-id="eebd4-148">Enum</span></span>      |          |

## <a name="actions"></a><span data-ttu-id="eebd4-149">Azioni</span><span class="sxs-lookup"><span data-stu-id="eebd4-149">Actions</span></span>

 | <span data-ttu-id="eebd4-150">Nome azione</span><span class="sxs-lookup"><span data-stu-id="eebd4-150">Action Name</span></span>                               | <span data-ttu-id="eebd4-151">Descrizione</span><span class="sxs-lookup"><span data-stu-id="eebd4-151">Description</span></span>                                     |
 |-------------------------------------------|-------------------------------------------------|
 | [<span data-ttu-id="eebd4-152">Inoltra</span><span class="sxs-lookup"><span data-stu-id="eebd4-152">submit</span></span>](hr-developer-api-myleaverequests-submit.md)   | <span data-ttu-id="eebd4-153">Inoltrare la richiesta da elaborare per flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="eebd4-153">Submit the request to be processed by workflow.</span></span> |

## <a name="see-also"></a><span data-ttu-id="eebd4-154">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="eebd4-154">See also</span></span>

- [<span data-ttu-id="eebd4-155">Inviare una richiesta di congedo a flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="eebd4-155">Submit a leave request to workflow</span></span>](hr-developer-api-myleaverequests-submit.md)
- [<span data-ttu-id="eebd4-156">Autenticazione</span><span class="sxs-lookup"><span data-stu-id="eebd4-156">Authentication</span></span>](hr-developer-api-authentication.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]