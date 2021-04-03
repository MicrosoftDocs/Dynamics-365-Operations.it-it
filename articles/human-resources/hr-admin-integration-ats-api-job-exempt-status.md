---
title: Stato esenzione mansione
description: Questo argomento descrive il set di opzioni Stato esenzione mansione impostato per Dynamics 365 Human Resources.
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
ms.openlocfilehash: 1f211002468384227acb2343ed6cbc6ae2a215d1
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/17/2021
ms.locfileid: "5464454"
---
# <a name="job-exempt-status"></a><span data-ttu-id="50fbb-103">Stato esenzione mansione</span><span class="sxs-lookup"><span data-stu-id="50fbb-103">Job exempt status</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="50fbb-104">Questo argomento descrive il set di opzioni Stato esenzione mansione impostato per Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="50fbb-104">This topic describes the Job exempt status option set for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="50fbb-105">Nome fisico: cdm_jobexemptstatus</span><span class="sxs-lookup"><span data-stu-id="50fbb-105">Physical name: cdm_jobexemptstatus</span></span>

<span data-ttu-id="50fbb-106">Questa enumerazione descrive il set di opzioni per i valori relativi allo stato dell'esenzione mansione FLSA.</span><span class="sxs-lookup"><span data-stu-id="50fbb-106">This enumeration specifies the option set for FLSA job exempt status values.</span></span> <span data-ttu-id="50fbb-107">Viene fornito nel set di opzioni cdm_jobexemptstatus esistente.</span><span class="sxs-lookup"><span data-stu-id="50fbb-107">This is provided in the existing cdm_jobexemptstatus option set.</span></span>

| <span data-ttu-id="50fbb-108">Valore</span><span class="sxs-lookup"><span data-stu-id="50fbb-108">Value</span></span> | <span data-ttu-id="50fbb-109">Etichetta</span><span class="sxs-lookup"><span data-stu-id="50fbb-109">Label</span></span> | <span data-ttu-id="50fbb-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="50fbb-110">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="50fbb-111">200000000</span><span class="sxs-lookup"><span data-stu-id="50fbb-111">200000000</span></span> | <span data-ttu-id="50fbb-112">Esenzione</span><span class="sxs-lookup"><span data-stu-id="50fbb-112">Exempt</span></span> | <span data-ttu-id="50fbb-113">Il lavoro ha uno stato di esenzione in base alle linee guida FLSA.</span><span class="sxs-lookup"><span data-stu-id="50fbb-113">The job has an exempt status based on FLSA guidelines.</span></span> |
| <span data-ttu-id="50fbb-114">200000001</span><span class="sxs-lookup"><span data-stu-id="50fbb-114">200000001</span></span> | <span data-ttu-id="50fbb-115">NonExempt</span><span class="sxs-lookup"><span data-stu-id="50fbb-115">NonExempt</span></span> | <span data-ttu-id="50fbb-116">Il lavoro ha uno stato di non esenzione in base alle linee guida FLSA.</span><span class="sxs-lookup"><span data-stu-id="50fbb-116">The job has a non-exempt status based on FLSA guidelines.</span></span> |
| <span data-ttu-id="50fbb-117">200000002</span><span class="sxs-lookup"><span data-stu-id="50fbb-117">200000002</span></span> | <span data-ttu-id="50fbb-118">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="50fbb-118">Does Not Apply</span></span> | <span data-ttu-id="50fbb-119">Le linee guida sullo stato FLSA non si applicano al lavoro.</span><span class="sxs-lookup"><span data-stu-id="50fbb-119">FLSA status guidelines do not apply to the job.</span></span> |

## <a name="see-also"></a><span data-ttu-id="50fbb-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="50fbb-120">See also</span></span>

[<span data-ttu-id="50fbb-121">Introduzione all'API di integrazione del sistema di tracciabilità dei candidati</span><span class="sxs-lookup"><span data-stu-id="50fbb-121">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="50fbb-122">Query di esempio per la richiesta di selezione</span><span class="sxs-lookup"><span data-stu-id="50fbb-122">Example query for Recruiting request</span></span>](hr-admin-integration-ats-api-recruiting-request-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]