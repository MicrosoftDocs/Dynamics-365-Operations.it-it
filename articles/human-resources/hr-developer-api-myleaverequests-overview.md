---
title: Panoramica di MyLeaveRequests
description: ''
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
ms.openlocfilehash: 66f161d6736b1bb544d02871d9d51b2949b1cfa0
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2020
ms.locfileid: "3009539"
---
# <a name="myleaverequests-overview"></a><span data-ttu-id="c0ea8-102">Panoramica di MyLeaveRequests</span><span class="sxs-lookup"><span data-stu-id="c0ea8-102">MyLeaveRequests overview</span></span>

<span data-ttu-id="c0ea8-103">L'entità MyLeaveRequests in Microsoft Dynamics 365 Human Resources fornisce l'elenco delle richieste di congedo nel sistema, con ambito (limitato) alle richieste accessibili all'utente corrente che interroga l'entità.</span><span class="sxs-lookup"><span data-stu-id="c0ea8-103">The MyLeaveRequests entity in Microsoft Dynamics 365 Human Resources provides the list of Leave Requests in the system, scoped (limited) to the requests accessible to the current user querying the entity.</span></span>

## <a name="key"></a><span data-ttu-id="c0ea8-104">Chiave</span><span class="sxs-lookup"><span data-stu-id="c0ea8-104">Key</span></span>

  | <span data-ttu-id="c0ea8-105">Nome proprietà</span><span class="sxs-lookup"><span data-stu-id="c0ea8-105">Property Name</span></span> | <span data-ttu-id="c0ea8-106">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="c0ea8-106">Data Type</span></span> |
  |---------------|-----------|
  | <span data-ttu-id="c0ea8-107">dataAreaId</span><span class="sxs-lookup"><span data-stu-id="c0ea8-107">dataAreaId</span></span>    | <span data-ttu-id="c0ea8-108">Stringa</span><span class="sxs-lookup"><span data-stu-id="c0ea8-108">String</span></span>    |
  | <span data-ttu-id="c0ea8-109">RequestId</span><span class="sxs-lookup"><span data-stu-id="c0ea8-109">RequestId</span></span>     | <span data-ttu-id="c0ea8-110">Stringa</span><span class="sxs-lookup"><span data-stu-id="c0ea8-110">String</span></span>    |
  | <span data-ttu-id="c0ea8-111">LeaveType</span><span class="sxs-lookup"><span data-stu-id="c0ea8-111">LeaveType</span></span>     | <span data-ttu-id="c0ea8-112">Stringa</span><span class="sxs-lookup"><span data-stu-id="c0ea8-112">String</span></span>    |
  | <span data-ttu-id="c0ea8-113">LeaveDate</span><span class="sxs-lookup"><span data-stu-id="c0ea8-113">LeaveDate</span></span>     | <span data-ttu-id="c0ea8-114">Data</span><span class="sxs-lookup"><span data-stu-id="c0ea8-114">Date</span></span>      |
  
## <a name="properties"></a><span data-ttu-id="c0ea8-115">Proprietà</span><span class="sxs-lookup"><span data-stu-id="c0ea8-115">Properties</span></span>

  | <span data-ttu-id="c0ea8-116">Nome proprietà</span><span class="sxs-lookup"><span data-stu-id="c0ea8-116">Property Name</span></span>     | <span data-ttu-id="c0ea8-117">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="c0ea8-117">Data Type</span></span> | <span data-ttu-id="c0ea8-118">Obbligatorio</span><span class="sxs-lookup"><span data-stu-id="c0ea8-118">Required</span></span> |
  |-------------------|-----------|----------|
  | <span data-ttu-id="c0ea8-119">dataAreaId</span><span class="sxs-lookup"><span data-stu-id="c0ea8-119">dataAreaId</span></span>        | <span data-ttu-id="c0ea8-120">Stringa</span><span class="sxs-lookup"><span data-stu-id="c0ea8-120">String</span></span>    | <span data-ttu-id="c0ea8-121">X</span><span class="sxs-lookup"><span data-stu-id="c0ea8-121">X</span></span>        |
  | <span data-ttu-id="c0ea8-122">RequestId</span><span class="sxs-lookup"><span data-stu-id="c0ea8-122">RequestId</span></span>         | <span data-ttu-id="c0ea8-123">Stringa</span><span class="sxs-lookup"><span data-stu-id="c0ea8-123">String</span></span>    | <span data-ttu-id="c0ea8-124">X</span><span class="sxs-lookup"><span data-stu-id="c0ea8-124">X</span></span>        |
  | <span data-ttu-id="c0ea8-125">LeaveType</span><span class="sxs-lookup"><span data-stu-id="c0ea8-125">LeaveType</span></span>         | <span data-ttu-id="c0ea8-126">Stringa</span><span class="sxs-lookup"><span data-stu-id="c0ea8-126">String</span></span>    | <span data-ttu-id="c0ea8-127">X</span><span class="sxs-lookup"><span data-stu-id="c0ea8-127">X</span></span>        |
  | <span data-ttu-id="c0ea8-128">LeaveDate</span><span class="sxs-lookup"><span data-stu-id="c0ea8-128">LeaveDate</span></span>         | <span data-ttu-id="c0ea8-129">Data</span><span class="sxs-lookup"><span data-stu-id="c0ea8-129">Date</span></span>      | <span data-ttu-id="c0ea8-130">X</span><span class="sxs-lookup"><span data-stu-id="c0ea8-130">X</span></span>        |
  | <span data-ttu-id="c0ea8-131">ReasonCodeId</span><span class="sxs-lookup"><span data-stu-id="c0ea8-131">ReasonCodeId</span></span>      | <span data-ttu-id="c0ea8-132">Stringa</span><span class="sxs-lookup"><span data-stu-id="c0ea8-132">String</span></span>    |          |
  | <span data-ttu-id="c0ea8-133">PersonnelNumber</span><span class="sxs-lookup"><span data-stu-id="c0ea8-133">PersonnelNumber</span></span>   | <span data-ttu-id="c0ea8-134">Stringa</span><span class="sxs-lookup"><span data-stu-id="c0ea8-134">String</span></span>    | <span data-ttu-id="c0ea8-135">X</span><span class="sxs-lookup"><span data-stu-id="c0ea8-135">X</span></span>        |
  | <span data-ttu-id="c0ea8-136">RequestDate</span><span class="sxs-lookup"><span data-stu-id="c0ea8-136">RequestDate</span></span>       | <span data-ttu-id="c0ea8-137">Data</span><span class="sxs-lookup"><span data-stu-id="c0ea8-137">Date</span></span>      | <span data-ttu-id="c0ea8-138">X</span><span class="sxs-lookup"><span data-stu-id="c0ea8-138">X</span></span>        |
  | <span data-ttu-id="c0ea8-139">Commento</span><span class="sxs-lookup"><span data-stu-id="c0ea8-139">Comment</span></span>           | <span data-ttu-id="c0ea8-140">Stringa</span><span class="sxs-lookup"><span data-stu-id="c0ea8-140">String</span></span>    |          |
  | <span data-ttu-id="c0ea8-141">Stato</span><span class="sxs-lookup"><span data-stu-id="c0ea8-141">Status</span></span>            | <span data-ttu-id="c0ea8-142">Enumerazione</span><span class="sxs-lookup"><span data-stu-id="c0ea8-142">Enum</span></span>      | <span data-ttu-id="c0ea8-143">X</span><span class="sxs-lookup"><span data-stu-id="c0ea8-143">X</span></span>        |
  | <span data-ttu-id="c0ea8-144">Periodo</span><span class="sxs-lookup"><span data-stu-id="c0ea8-144">Amount</span></span>            | <span data-ttu-id="c0ea8-145">Reale</span><span class="sxs-lookup"><span data-stu-id="c0ea8-145">Real</span></span>      |          |
  | <span data-ttu-id="c0ea8-146">HalfDayDefinition</span><span class="sxs-lookup"><span data-stu-id="c0ea8-146">HalfDayDefinition</span></span> | <span data-ttu-id="c0ea8-147">Enumerazione</span><span class="sxs-lookup"><span data-stu-id="c0ea8-147">Enum</span></span>      |          |

## <a name="actions"></a><span data-ttu-id="c0ea8-148">Azioni</span><span class="sxs-lookup"><span data-stu-id="c0ea8-148">Actions</span></span>

 | <span data-ttu-id="c0ea8-149">Nome azione</span><span class="sxs-lookup"><span data-stu-id="c0ea8-149">Action Name</span></span>                               | <span data-ttu-id="c0ea8-150">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c0ea8-150">Description</span></span>                                     |
 |-------------------------------------------|-------------------------------------------------|
 | [<span data-ttu-id="c0ea8-151">Inoltra</span><span class="sxs-lookup"><span data-stu-id="c0ea8-151">submit</span></span>](hr-developer-api-myleaverequests-submit.md)   | <span data-ttu-id="c0ea8-152">Inoltrare la richiesta da elaborare per flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="c0ea8-152">Submit the request to be processed by workflow.</span></span> |

## <a name="see-also"></a><span data-ttu-id="c0ea8-153">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c0ea8-153">See also</span></span>

- [<span data-ttu-id="c0ea8-154">Inviare una richiesta di congedo a flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="c0ea8-154">Submit a leave request to workflow</span></span>](hr-developer-api-myleaverequests-submit.md)
- [<span data-ttu-id="c0ea8-155">Autenticazione</span><span class="sxs-lookup"><span data-stu-id="c0ea8-155">Authentication</span></span>](hr-developer-api-authentication.md)