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
ms.openlocfilehash: c2c14a0cc935ad166a2c6600f1e96c3e09ab16ca
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/17/2021
ms.locfileid: "5465512"
---
# <a name="myleaverequests-overview"></a><span data-ttu-id="1d6fd-103">Panoramica di MyLeaveRequests</span><span class="sxs-lookup"><span data-stu-id="1d6fd-103">MyLeaveRequests overview</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="1d6fd-104">L'entità MyLeaveRequests in Microsoft Dynamics 365 Human Resources fornisce l'elenco delle richieste di congedo nel sistema, con ambito (limitato) alle richieste accessibili all'utente corrente che interroga l'entità.</span><span class="sxs-lookup"><span data-stu-id="1d6fd-104">The MyLeaveRequests entity in Microsoft Dynamics 365 Human Resources provides the list of Leave Requests in the system, scoped (limited) to the requests accessible to the current user querying the entity.</span></span>

## <a name="key"></a><span data-ttu-id="1d6fd-105">Chiave</span><span class="sxs-lookup"><span data-stu-id="1d6fd-105">Key</span></span>

  | <span data-ttu-id="1d6fd-106">Nome proprietà</span><span class="sxs-lookup"><span data-stu-id="1d6fd-106">Property Name</span></span> | <span data-ttu-id="1d6fd-107">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="1d6fd-107">Data Type</span></span> |
  |---------------|-----------|
  | <span data-ttu-id="1d6fd-108">dataAreaId</span><span class="sxs-lookup"><span data-stu-id="1d6fd-108">dataAreaId</span></span>    | <span data-ttu-id="1d6fd-109">Stringa</span><span class="sxs-lookup"><span data-stu-id="1d6fd-109">String</span></span>    |
  | <span data-ttu-id="1d6fd-110">RequestId</span><span class="sxs-lookup"><span data-stu-id="1d6fd-110">RequestId</span></span>     | <span data-ttu-id="1d6fd-111">Stringa</span><span class="sxs-lookup"><span data-stu-id="1d6fd-111">String</span></span>    |
  | <span data-ttu-id="1d6fd-112">LeaveType</span><span class="sxs-lookup"><span data-stu-id="1d6fd-112">LeaveType</span></span>     | <span data-ttu-id="1d6fd-113">Stringa</span><span class="sxs-lookup"><span data-stu-id="1d6fd-113">String</span></span>    |
  | <span data-ttu-id="1d6fd-114">LeaveDate</span><span class="sxs-lookup"><span data-stu-id="1d6fd-114">LeaveDate</span></span>     | <span data-ttu-id="1d6fd-115">Data</span><span class="sxs-lookup"><span data-stu-id="1d6fd-115">Date</span></span>      |
  
## <a name="properties"></a><span data-ttu-id="1d6fd-116">Proprietà</span><span class="sxs-lookup"><span data-stu-id="1d6fd-116">Properties</span></span>

  | <span data-ttu-id="1d6fd-117">Nome proprietà</span><span class="sxs-lookup"><span data-stu-id="1d6fd-117">Property Name</span></span>     | <span data-ttu-id="1d6fd-118">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="1d6fd-118">Data Type</span></span> | <span data-ttu-id="1d6fd-119">Obbligatorio</span><span class="sxs-lookup"><span data-stu-id="1d6fd-119">Required</span></span> |
  |-------------------|-----------|----------|
  | <span data-ttu-id="1d6fd-120">dataAreaId</span><span class="sxs-lookup"><span data-stu-id="1d6fd-120">dataAreaId</span></span>        | <span data-ttu-id="1d6fd-121">Stringa</span><span class="sxs-lookup"><span data-stu-id="1d6fd-121">String</span></span>    | <span data-ttu-id="1d6fd-122">X</span><span class="sxs-lookup"><span data-stu-id="1d6fd-122">X</span></span>        |
  | <span data-ttu-id="1d6fd-123">RequestId</span><span class="sxs-lookup"><span data-stu-id="1d6fd-123">RequestId</span></span>         | <span data-ttu-id="1d6fd-124">Stringa</span><span class="sxs-lookup"><span data-stu-id="1d6fd-124">String</span></span>    | <span data-ttu-id="1d6fd-125">X</span><span class="sxs-lookup"><span data-stu-id="1d6fd-125">X</span></span>        |
  | <span data-ttu-id="1d6fd-126">LeaveType</span><span class="sxs-lookup"><span data-stu-id="1d6fd-126">LeaveType</span></span>         | <span data-ttu-id="1d6fd-127">Stringa</span><span class="sxs-lookup"><span data-stu-id="1d6fd-127">String</span></span>    | <span data-ttu-id="1d6fd-128">X</span><span class="sxs-lookup"><span data-stu-id="1d6fd-128">X</span></span>        |
  | <span data-ttu-id="1d6fd-129">LeaveDate</span><span class="sxs-lookup"><span data-stu-id="1d6fd-129">LeaveDate</span></span>         | <span data-ttu-id="1d6fd-130">Data</span><span class="sxs-lookup"><span data-stu-id="1d6fd-130">Date</span></span>      | <span data-ttu-id="1d6fd-131">X</span><span class="sxs-lookup"><span data-stu-id="1d6fd-131">X</span></span>        |
  | <span data-ttu-id="1d6fd-132">ReasonCodeId</span><span class="sxs-lookup"><span data-stu-id="1d6fd-132">ReasonCodeId</span></span>      | <span data-ttu-id="1d6fd-133">Stringa</span><span class="sxs-lookup"><span data-stu-id="1d6fd-133">String</span></span>    |          |
  | <span data-ttu-id="1d6fd-134">PersonnelNumber</span><span class="sxs-lookup"><span data-stu-id="1d6fd-134">PersonnelNumber</span></span>   | <span data-ttu-id="1d6fd-135">Stringa</span><span class="sxs-lookup"><span data-stu-id="1d6fd-135">String</span></span>    | <span data-ttu-id="1d6fd-136">X</span><span class="sxs-lookup"><span data-stu-id="1d6fd-136">X</span></span>        |
  | <span data-ttu-id="1d6fd-137">RequestDate</span><span class="sxs-lookup"><span data-stu-id="1d6fd-137">RequestDate</span></span>       | <span data-ttu-id="1d6fd-138">Data</span><span class="sxs-lookup"><span data-stu-id="1d6fd-138">Date</span></span>      | <span data-ttu-id="1d6fd-139">X</span><span class="sxs-lookup"><span data-stu-id="1d6fd-139">X</span></span>        |
  | <span data-ttu-id="1d6fd-140">Commento</span><span class="sxs-lookup"><span data-stu-id="1d6fd-140">Comment</span></span>           | <span data-ttu-id="1d6fd-141">Stringa</span><span class="sxs-lookup"><span data-stu-id="1d6fd-141">String</span></span>    |          |
  | <span data-ttu-id="1d6fd-142">Stato</span><span class="sxs-lookup"><span data-stu-id="1d6fd-142">Status</span></span>            | <span data-ttu-id="1d6fd-143">Enumerazione</span><span class="sxs-lookup"><span data-stu-id="1d6fd-143">Enum</span></span>      | <span data-ttu-id="1d6fd-144">X</span><span class="sxs-lookup"><span data-stu-id="1d6fd-144">X</span></span>        |
  | <span data-ttu-id="1d6fd-145">Periodo</span><span class="sxs-lookup"><span data-stu-id="1d6fd-145">Amount</span></span>            | <span data-ttu-id="1d6fd-146">Reale</span><span class="sxs-lookup"><span data-stu-id="1d6fd-146">Real</span></span>      |          |
  | <span data-ttu-id="1d6fd-147">HalfDayDefinition</span><span class="sxs-lookup"><span data-stu-id="1d6fd-147">HalfDayDefinition</span></span> | <span data-ttu-id="1d6fd-148">Enumerazione</span><span class="sxs-lookup"><span data-stu-id="1d6fd-148">Enum</span></span>      |          |

## <a name="actions"></a><span data-ttu-id="1d6fd-149">Azioni</span><span class="sxs-lookup"><span data-stu-id="1d6fd-149">Actions</span></span>

 | <span data-ttu-id="1d6fd-150">Nome azione</span><span class="sxs-lookup"><span data-stu-id="1d6fd-150">Action Name</span></span>                               | <span data-ttu-id="1d6fd-151">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1d6fd-151">Description</span></span>                                     |
 |-------------------------------------------|-------------------------------------------------|
 | [<span data-ttu-id="1d6fd-152">Inoltra</span><span class="sxs-lookup"><span data-stu-id="1d6fd-152">submit</span></span>](hr-developer-api-myleaverequests-submit.md)   | <span data-ttu-id="1d6fd-153">Inoltrare la richiesta da elaborare per flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="1d6fd-153">Submit the request to be processed by workflow.</span></span> |

## <a name="see-also"></a><span data-ttu-id="1d6fd-154">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1d6fd-154">See also</span></span>

- [<span data-ttu-id="1d6fd-155">Inviare una richiesta di congedo a flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="1d6fd-155">Submit a leave request to workflow</span></span>](hr-developer-api-myleaverequests-submit.md)
- [<span data-ttu-id="1d6fd-156">Autenticazione</span><span class="sxs-lookup"><span data-stu-id="1d6fd-156">Authentication</span></span>](hr-developer-api-authentication.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]