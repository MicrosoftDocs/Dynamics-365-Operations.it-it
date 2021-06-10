---
title: Risultati integrazione candidato
description: Questo argomento descrive l'opzione Risultato integrazione richiedente impostata per Dynamics 365 Human Resources.
author: jaredha
ms.date: 02/05/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2021-02-05
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 8bef974abff18d7c07ecd679b7e01b31ea1459c4
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/18/2021
ms.locfileid: "6053901"
---
# <a name="applicant-integration-result"></a><span data-ttu-id="960a8-103">Risultati integrazione candidato</span><span class="sxs-lookup"><span data-stu-id="960a8-103">Applicant integration result</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="960a8-104">Questo argomento descrive l'opzione Risultato integrazione richiedente impostata per Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="960a8-104">This topic describes the Applicant integration result option set for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="960a8-105">Nome fisico: mshr_hcmapplicantintegrationresult</span><span class="sxs-lookup"><span data-stu-id="960a8-105">Physical name: mshr_hcmapplicantintegrationresult</span></span>

<span data-ttu-id="960a8-106">Questa enumerazione fornisce lo stato di un record candidato.</span><span class="sxs-lookup"><span data-stu-id="960a8-106">This enumeration provides status for a candidate record.</span></span>

| <span data-ttu-id="960a8-107">Valore</span><span class="sxs-lookup"><span data-stu-id="960a8-107">Value</span></span> | <span data-ttu-id="960a8-108">Etichetta</span><span class="sxs-lookup"><span data-stu-id="960a8-108">Label</span></span> | <span data-ttu-id="960a8-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="960a8-109">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="960a8-110">200000000</span><span class="sxs-lookup"><span data-stu-id="960a8-110">200000000</span></span> | <span data-ttu-id="960a8-111">Non elaborato</span><span class="sxs-lookup"><span data-stu-id="960a8-111">Not processed</span></span> | <span data-ttu-id="960a8-112">Il candidato è ancora allo studio.</span><span class="sxs-lookup"><span data-stu-id="960a8-112">Candidate is still under consideration.</span></span> |
| <span data-ttu-id="960a8-113">200000001</span><span class="sxs-lookup"><span data-stu-id="960a8-113">200000001</span></span> | <span data-ttu-id="960a8-114">Assunto</span><span class="sxs-lookup"><span data-stu-id="960a8-114">Hired</span></span> | <span data-ttu-id="960a8-115">Il candidato è stato assunto.</span><span class="sxs-lookup"><span data-stu-id="960a8-115">The candidate has been hired.</span></span> |
| <span data-ttu-id="960a8-116">200000002</span><span class="sxs-lookup"><span data-stu-id="960a8-116">200000002</span></span> | <span data-ttu-id="960a8-117">Non assunto</span><span class="sxs-lookup"><span data-stu-id="960a8-117">Not hired</span></span> | <span data-ttu-id="960a8-118">È stata presa la decisione di non assumere il candidato.</span><span class="sxs-lookup"><span data-stu-id="960a8-118">Decision was made to not hire the candidate.</span></span> |
| <span data-ttu-id="960a8-119">200000003</span><span class="sxs-lookup"><span data-stu-id="960a8-119">200000003</span></span> | <span data-ttu-id="960a8-120">Chiuso</span><span class="sxs-lookup"><span data-stu-id="960a8-120">Dismissed</span></span> | <span data-ttu-id="960a8-121">Il candidato non viene più tenuto in considerazione.</span><span class="sxs-lookup"><span data-stu-id="960a8-121">The candidate was dismissed from consideration.</span></span> |

## <a name="see-also"></a><span data-ttu-id="960a8-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="960a8-122">See also</span></span>

[<span data-ttu-id="960a8-123">Introduzione all'API di integrazione del sistema di tracciabilità dei candidati</span><span class="sxs-lookup"><span data-stu-id="960a8-123">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="960a8-124">Query di esempio per il candidato da assumere</span><span class="sxs-lookup"><span data-stu-id="960a8-124">Example query for Candidate to hire</span></span>](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]