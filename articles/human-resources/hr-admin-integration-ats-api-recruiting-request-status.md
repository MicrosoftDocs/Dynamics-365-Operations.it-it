---
title: Stato della richiesta di selezione
description: Questo argomento descrive l'opzione Stato richiesta di selezione impostata per Dynamics 365 Human Resources.
author: jaredha
manager: tfehr
ms.date: 02/05/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2021-02-05
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 0032e6bfdbfd2792dafda8bf24a1b0cbc551740d
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/17/2021
ms.locfileid: "5464648"
---
# <a name="recruiting-request-status"></a><span data-ttu-id="7e58b-103">Stato della richiesta di selezione</span><span class="sxs-lookup"><span data-stu-id="7e58b-103">Recruiting request status</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="7e58b-104">Questo argomento descrive l'opzione Stato richiesta di selezione impostata per Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="7e58b-104">This topic describes the Recruiting request status option set for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="7e58b-105">Nome fisico: mshr_hcmrecruitingrequeststatus</span><span class="sxs-lookup"><span data-stu-id="7e58b-105">Physical name: mshr_hcmrecruitingrequeststatus</span></span>

<span data-ttu-id="7e58b-106">Questa enumerazione fornisce il set di opzioni per i valori di stato per la richiesta di selezione.</span><span class="sxs-lookup"><span data-stu-id="7e58b-106">This enumeration provides the option set for the status values of a RecruitingRequest.</span></span>

| <span data-ttu-id="7e58b-107">Valore</span><span class="sxs-lookup"><span data-stu-id="7e58b-107">Value</span></span> | <span data-ttu-id="7e58b-108">Etichetta</span><span class="sxs-lookup"><span data-stu-id="7e58b-108">Label</span></span> | <span data-ttu-id="7e58b-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7e58b-109">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="7e58b-110">200000000</span><span class="sxs-lookup"><span data-stu-id="7e58b-110">200000000</span></span> | <span data-ttu-id="7e58b-111">Bozze</span><span class="sxs-lookup"><span data-stu-id="7e58b-111">Draft</span></span> | <span data-ttu-id="7e58b-112">La richiesta è in bozza e non è pronta per la selezione attiva.</span><span class="sxs-lookup"><span data-stu-id="7e58b-112">The request is in draft and isn't ready for active recruiting.</span></span> |
| <span data-ttu-id="7e58b-113">200000001</span><span class="sxs-lookup"><span data-stu-id="7e58b-113">200000001</span></span> | <span data-ttu-id="7e58b-114">In revisione</span><span class="sxs-lookup"><span data-stu-id="7e58b-114">In Review</span></span> | <span data-ttu-id="7e58b-115">La richiesta è stata inviata e viene instradata per l'approvazione dal flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="7e58b-115">The request has been submitted and is being routed for approval by workflow.</span></span> <span data-ttu-id="7e58b-116">Disponibile solo quando il flusso di lavoro è abilitato.</span><span class="sxs-lookup"><span data-stu-id="7e58b-116">Only available when workflow is enabled.</span></span> |
| <span data-ttu-id="7e58b-117">200000002</span><span class="sxs-lookup"><span data-stu-id="7e58b-117">200000002</span></span> | <span data-ttu-id="7e58b-118">In sospeso</span><span class="sxs-lookup"><span data-stu-id="7e58b-118">Pending</span></span> | <span data-ttu-id="7e58b-119">La richiesta è in attesa di azione del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="7e58b-119">The request is pending workflow action.</span></span> <span data-ttu-id="7e58b-120">Disponibile solo quando il flusso di lavoro è abilitato.</span><span class="sxs-lookup"><span data-stu-id="7e58b-120">Only available when workflow is enabled.</span></span> |
| <span data-ttu-id="7e58b-121">200000003</span><span class="sxs-lookup"><span data-stu-id="7e58b-121">200000003</span></span> | <span data-ttu-id="7e58b-122">Annullate</span><span class="sxs-lookup"><span data-stu-id="7e58b-122">Canceled</span></span> | <span data-ttu-id="7e58b-123">La richiesta è stata annullata.</span><span class="sxs-lookup"><span data-stu-id="7e58b-123">The request has been canceled.</span></span> <span data-ttu-id="7e58b-124">Disponibile solo quando il flusso di lavoro è abilitato.</span><span class="sxs-lookup"><span data-stu-id="7e58b-124">Only available when workflow is enabled.</span></span> |
| <span data-ttu-id="7e58b-125">200000004</span><span class="sxs-lookup"><span data-stu-id="7e58b-125">200000004</span></span> | <span data-ttu-id="7e58b-126">Negate</span><span class="sxs-lookup"><span data-stu-id="7e58b-126">Denied</span></span> | <span data-ttu-id="7e58b-127">La richiesta è stata rifiutata.</span><span class="sxs-lookup"><span data-stu-id="7e58b-127">The request has been denied.</span></span> <span data-ttu-id="7e58b-128">Disponibile solo quando il flusso di lavoro è abilitato.</span><span class="sxs-lookup"><span data-stu-id="7e58b-128">Only available when workflow is enabled.</span></span> |
| <span data-ttu-id="7e58b-129">200000005</span><span class="sxs-lookup"><span data-stu-id="7e58b-129">200000005</span></span> | <span data-ttu-id="7e58b-130">Attive</span><span class="sxs-lookup"><span data-stu-id="7e58b-130">Active</span></span> | <span data-ttu-id="7e58b-131">Qualsiasi flusso di lavoro viene completato e approvato e la richiesta è pronta per la selezione attiva.</span><span class="sxs-lookup"><span data-stu-id="7e58b-131">Any workflow is completed and approved, and the request is ready for active recruiting.</span></span> |
| <span data-ttu-id="7e58b-132">200000006</span><span class="sxs-lookup"><span data-stu-id="7e58b-132">200000006</span></span> | <span data-ttu-id="7e58b-133">Chiuse</span><span class="sxs-lookup"><span data-stu-id="7e58b-133">Closed</span></span> | <span data-ttu-id="7e58b-134">La richiesta di selezione è chiusa.</span><span class="sxs-lookup"><span data-stu-id="7e58b-134">The recruiting request is closed.</span></span> |

## <a name="see-also"></a><span data-ttu-id="7e58b-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7e58b-135">See also</span></span>

[<span data-ttu-id="7e58b-136">Introduzione all'API di integrazione del sistema di tracciabilità dei candidati</span><span class="sxs-lookup"><span data-stu-id="7e58b-136">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="7e58b-137">Query di esempio per la richiesta di selezione</span><span class="sxs-lookup"><span data-stu-id="7e58b-137">Example query for Recruiting request</span></span>](hr-admin-integration-ats-api-recruiting-request-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]