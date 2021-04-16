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
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 44e23a076733bac782a0366aeba3456911522abe
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5803635"
---
# <a name="myleaverequests-overview"></a><span data-ttu-id="66fb1-103">Panoramica di MyLeaveRequests</span><span class="sxs-lookup"><span data-stu-id="66fb1-103">MyLeaveRequests overview</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="66fb1-104">L'entità MyLeaveRequests in Microsoft Dynamics 365 Human Resources fornisce l'elenco delle richieste di congedo nel sistema, con ambito (limitato) alle richieste accessibili all'utente corrente che interroga l'entità.</span><span class="sxs-lookup"><span data-stu-id="66fb1-104">The MyLeaveRequests entity in Microsoft Dynamics 365 Human Resources provides the list of Leave Requests in the system, scoped (limited) to the requests accessible to the current user querying the entity.</span></span>

## <a name="key"></a><span data-ttu-id="66fb1-105">Chiave</span><span class="sxs-lookup"><span data-stu-id="66fb1-105">Key</span></span>

  | <span data-ttu-id="66fb1-106">Nome proprietà</span><span class="sxs-lookup"><span data-stu-id="66fb1-106">Property Name</span></span> | <span data-ttu-id="66fb1-107">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="66fb1-107">Data Type</span></span> |
  |---------------|-----------|
  | <span data-ttu-id="66fb1-108">dataAreaId</span><span class="sxs-lookup"><span data-stu-id="66fb1-108">dataAreaId</span></span>    | <span data-ttu-id="66fb1-109">Stringa</span><span class="sxs-lookup"><span data-stu-id="66fb1-109">String</span></span>    |
  | <span data-ttu-id="66fb1-110">RequestId</span><span class="sxs-lookup"><span data-stu-id="66fb1-110">RequestId</span></span>     | <span data-ttu-id="66fb1-111">Stringa</span><span class="sxs-lookup"><span data-stu-id="66fb1-111">String</span></span>    |
  | <span data-ttu-id="66fb1-112">LeaveType</span><span class="sxs-lookup"><span data-stu-id="66fb1-112">LeaveType</span></span>     | <span data-ttu-id="66fb1-113">Stringa</span><span class="sxs-lookup"><span data-stu-id="66fb1-113">String</span></span>    |
  | <span data-ttu-id="66fb1-114">LeaveDate</span><span class="sxs-lookup"><span data-stu-id="66fb1-114">LeaveDate</span></span>     | <span data-ttu-id="66fb1-115">Data</span><span class="sxs-lookup"><span data-stu-id="66fb1-115">Date</span></span>      |
  
## <a name="properties"></a><span data-ttu-id="66fb1-116">Proprietà</span><span class="sxs-lookup"><span data-stu-id="66fb1-116">Properties</span></span>

  | <span data-ttu-id="66fb1-117">Nome proprietà</span><span class="sxs-lookup"><span data-stu-id="66fb1-117">Property Name</span></span>     | <span data-ttu-id="66fb1-118">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="66fb1-118">Data Type</span></span> | <span data-ttu-id="66fb1-119">Obbligatorio</span><span class="sxs-lookup"><span data-stu-id="66fb1-119">Required</span></span> |
  |-------------------|-----------|----------|
  | <span data-ttu-id="66fb1-120">dataAreaId</span><span class="sxs-lookup"><span data-stu-id="66fb1-120">dataAreaId</span></span>        | <span data-ttu-id="66fb1-121">Stringa</span><span class="sxs-lookup"><span data-stu-id="66fb1-121">String</span></span>    | <span data-ttu-id="66fb1-122">X</span><span class="sxs-lookup"><span data-stu-id="66fb1-122">X</span></span>        |
  | <span data-ttu-id="66fb1-123">RequestId</span><span class="sxs-lookup"><span data-stu-id="66fb1-123">RequestId</span></span>         | <span data-ttu-id="66fb1-124">Stringa</span><span class="sxs-lookup"><span data-stu-id="66fb1-124">String</span></span>    | <span data-ttu-id="66fb1-125">X</span><span class="sxs-lookup"><span data-stu-id="66fb1-125">X</span></span>        |
  | <span data-ttu-id="66fb1-126">LeaveType</span><span class="sxs-lookup"><span data-stu-id="66fb1-126">LeaveType</span></span>         | <span data-ttu-id="66fb1-127">Stringa</span><span class="sxs-lookup"><span data-stu-id="66fb1-127">String</span></span>    | <span data-ttu-id="66fb1-128">X</span><span class="sxs-lookup"><span data-stu-id="66fb1-128">X</span></span>        |
  | <span data-ttu-id="66fb1-129">LeaveDate</span><span class="sxs-lookup"><span data-stu-id="66fb1-129">LeaveDate</span></span>         | <span data-ttu-id="66fb1-130">Data</span><span class="sxs-lookup"><span data-stu-id="66fb1-130">Date</span></span>      | <span data-ttu-id="66fb1-131">X</span><span class="sxs-lookup"><span data-stu-id="66fb1-131">X</span></span>        |
  | <span data-ttu-id="66fb1-132">ReasonCodeId</span><span class="sxs-lookup"><span data-stu-id="66fb1-132">ReasonCodeId</span></span>      | <span data-ttu-id="66fb1-133">Stringa</span><span class="sxs-lookup"><span data-stu-id="66fb1-133">String</span></span>    |          |
  | <span data-ttu-id="66fb1-134">PersonnelNumber</span><span class="sxs-lookup"><span data-stu-id="66fb1-134">PersonnelNumber</span></span>   | <span data-ttu-id="66fb1-135">Stringa</span><span class="sxs-lookup"><span data-stu-id="66fb1-135">String</span></span>    | <span data-ttu-id="66fb1-136">X</span><span class="sxs-lookup"><span data-stu-id="66fb1-136">X</span></span>        |
  | <span data-ttu-id="66fb1-137">RequestDate</span><span class="sxs-lookup"><span data-stu-id="66fb1-137">RequestDate</span></span>       | <span data-ttu-id="66fb1-138">Data</span><span class="sxs-lookup"><span data-stu-id="66fb1-138">Date</span></span>      | <span data-ttu-id="66fb1-139">X</span><span class="sxs-lookup"><span data-stu-id="66fb1-139">X</span></span>        |
  | <span data-ttu-id="66fb1-140">Commento</span><span class="sxs-lookup"><span data-stu-id="66fb1-140">Comment</span></span>           | <span data-ttu-id="66fb1-141">Stringa</span><span class="sxs-lookup"><span data-stu-id="66fb1-141">String</span></span>    |          |
  | <span data-ttu-id="66fb1-142">Stato</span><span class="sxs-lookup"><span data-stu-id="66fb1-142">Status</span></span>            | <span data-ttu-id="66fb1-143">Enumerazione</span><span class="sxs-lookup"><span data-stu-id="66fb1-143">Enum</span></span>      | <span data-ttu-id="66fb1-144">X</span><span class="sxs-lookup"><span data-stu-id="66fb1-144">X</span></span>        |
  | <span data-ttu-id="66fb1-145">Periodo</span><span class="sxs-lookup"><span data-stu-id="66fb1-145">Amount</span></span>            | <span data-ttu-id="66fb1-146">Reale</span><span class="sxs-lookup"><span data-stu-id="66fb1-146">Real</span></span>      |          |
  | <span data-ttu-id="66fb1-147">HalfDayDefinition</span><span class="sxs-lookup"><span data-stu-id="66fb1-147">HalfDayDefinition</span></span> | <span data-ttu-id="66fb1-148">Enumerazione</span><span class="sxs-lookup"><span data-stu-id="66fb1-148">Enum</span></span>      |          |

## <a name="actions"></a><span data-ttu-id="66fb1-149">Azioni</span><span class="sxs-lookup"><span data-stu-id="66fb1-149">Actions</span></span>

 | <span data-ttu-id="66fb1-150">Nome azione</span><span class="sxs-lookup"><span data-stu-id="66fb1-150">Action Name</span></span>                               | <span data-ttu-id="66fb1-151">Descrizione</span><span class="sxs-lookup"><span data-stu-id="66fb1-151">Description</span></span>                                     |
 |-------------------------------------------|-------------------------------------------------|
 | [<span data-ttu-id="66fb1-152">Inoltra</span><span class="sxs-lookup"><span data-stu-id="66fb1-152">submit</span></span>](hr-developer-api-myleaverequests-submit.md)   | <span data-ttu-id="66fb1-153">Inoltrare la richiesta da elaborare per flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="66fb1-153">Submit the request to be processed by workflow.</span></span> |

## <a name="see-also"></a><span data-ttu-id="66fb1-154">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="66fb1-154">See also</span></span>

- [<span data-ttu-id="66fb1-155">Inviare una richiesta di congedo a flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="66fb1-155">Submit a leave request to workflow</span></span>](hr-developer-api-myleaverequests-submit.md)
- [<span data-ttu-id="66fb1-156">Autenticazione</span><span class="sxs-lookup"><span data-stu-id="66fb1-156">Authentication</span></span>](hr-developer-api-authentication.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]