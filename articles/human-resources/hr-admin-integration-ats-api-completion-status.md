---
title: Stato di completamento
description: Questo argomento descrive il set di opzioni Stato di completamento impostato per Dynamics 365 Human Resources.
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
ms.openlocfilehash: d8ea90785f303301a21a4ac799578b08cabd0e3d
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/17/2021
ms.locfileid: "5468205"
---
# <a name="completion-status"></a><span data-ttu-id="9ab4a-103">Stato di completamento</span><span class="sxs-lookup"><span data-stu-id="9ab4a-103">Completion status</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="9ab4a-104">Questo argomento descrive il set di opzioni Stato di completamento impostato per Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="9ab4a-104">This topic describes the Completion status option set for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="9ab4a-105">Nome fisico: mshr_hcmcompletionstatus</span><span class="sxs-lookup"><span data-stu-id="9ab4a-105">Physical name: mshr_hcmcompletionstatus</span></span>

<span data-ttu-id="9ab4a-106">Questa enumerazione fornisce il set di opzioni dei valori di stato per gli screening dei candidati.</span><span class="sxs-lookup"><span data-stu-id="9ab4a-106">This enumeration provides the option set of status values for candidate screenings.</span></span> 

| <span data-ttu-id="9ab4a-107">Valore</span><span class="sxs-lookup"><span data-stu-id="9ab4a-107">Value</span></span> | <span data-ttu-id="9ab4a-108">Etichetta</span><span class="sxs-lookup"><span data-stu-id="9ab4a-108">Label</span></span> | <span data-ttu-id="9ab4a-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9ab4a-109">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="9ab4a-110">200000000</span><span class="sxs-lookup"><span data-stu-id="9ab4a-110">200000000</span></span> | <span data-ttu-id="9ab4a-111">Non completato</span><span class="sxs-lookup"><span data-stu-id="9ab4a-111">Not Complete</span></span> | <span data-ttu-id="9ab4a-112">Il candidato non ha ancora completato lo screening.</span><span class="sxs-lookup"><span data-stu-id="9ab4a-112">The candidate has not yet completed the screening.</span></span> |
| <span data-ttu-id="9ab4a-113">200000001</span><span class="sxs-lookup"><span data-stu-id="9ab4a-113">200000001</span></span> | <span data-ttu-id="9ab4a-114">Superato</span><span class="sxs-lookup"><span data-stu-id="9ab4a-114">Pass</span></span> | <span data-ttu-id="9ab4a-115">Il candidato ha superato lo screening.</span><span class="sxs-lookup"><span data-stu-id="9ab4a-115">The candidate has passed the screening.</span></span> |
| <span data-ttu-id="9ab4a-116">200000002</span><span class="sxs-lookup"><span data-stu-id="9ab4a-116">200000002</span></span> | <span data-ttu-id="9ab4a-117">Errore</span><span class="sxs-lookup"><span data-stu-id="9ab4a-117">Fail</span></span> | <span data-ttu-id="9ab4a-118">Il candidato non ha superato lo screening.</span><span class="sxs-lookup"><span data-stu-id="9ab4a-118">The candidate has failed the screening.</span></span> |

## <a name="see-also"></a><span data-ttu-id="9ab4a-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9ab4a-119">See also</span></span>

[<span data-ttu-id="9ab4a-120">Introduzione all'API di integrazione del sistema di tracciabilità dei candidati</span><span class="sxs-lookup"><span data-stu-id="9ab4a-120">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="9ab4a-121">Query di esempio per il candidato da assumere</span><span class="sxs-lookup"><span data-stu-id="9ab4a-121">Example query for Candidate to hire</span></span>](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]