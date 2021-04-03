---
title: Risultati integrazione candidato
description: Questo argomento descrive l'opzione Risultato integrazione richiedente impostata per Dynamics 365 Human Resources.
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
ms.openlocfilehash: dd25eca9cccf46ec4e4bb2a1d948ca98985e73e4
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/17/2021
ms.locfileid: "5467555"
---
# <a name="applicant-integration-result"></a><span data-ttu-id="02594-103">Risultati integrazione candidato</span><span class="sxs-lookup"><span data-stu-id="02594-103">Applicant integration result</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="02594-104">Questo argomento descrive l'opzione Risultato integrazione richiedente impostata per Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="02594-104">This topic describes the Applicant integration result option set for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="02594-105">Nome fisico: mshr_hcmapplicantintegrationresult</span><span class="sxs-lookup"><span data-stu-id="02594-105">Physical name: mshr_hcmapplicantintegrationresult</span></span>

<span data-ttu-id="02594-106">Questa enumerazione fornisce lo stato di un record candidato.</span><span class="sxs-lookup"><span data-stu-id="02594-106">This enumeration provides status for a candidate record.</span></span>

| <span data-ttu-id="02594-107">Valore</span><span class="sxs-lookup"><span data-stu-id="02594-107">Value</span></span> | <span data-ttu-id="02594-108">Etichetta</span><span class="sxs-lookup"><span data-stu-id="02594-108">Label</span></span> | <span data-ttu-id="02594-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="02594-109">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="02594-110">200000000</span><span class="sxs-lookup"><span data-stu-id="02594-110">200000000</span></span> | <span data-ttu-id="02594-111">Non elaborato</span><span class="sxs-lookup"><span data-stu-id="02594-111">Not processed</span></span> | <span data-ttu-id="02594-112">Il candidato è ancora allo studio.</span><span class="sxs-lookup"><span data-stu-id="02594-112">Candidate is still under consideration.</span></span> |
| <span data-ttu-id="02594-113">200000001</span><span class="sxs-lookup"><span data-stu-id="02594-113">200000001</span></span> | <span data-ttu-id="02594-114">Assunto</span><span class="sxs-lookup"><span data-stu-id="02594-114">Hired</span></span> | <span data-ttu-id="02594-115">Il candidato è stato assunto.</span><span class="sxs-lookup"><span data-stu-id="02594-115">The candidate has been hired.</span></span> |
| <span data-ttu-id="02594-116">200000002</span><span class="sxs-lookup"><span data-stu-id="02594-116">200000002</span></span> | <span data-ttu-id="02594-117">Non assunto</span><span class="sxs-lookup"><span data-stu-id="02594-117">Not hired</span></span> | <span data-ttu-id="02594-118">È stata presa la decisione di non assumere il candidato.</span><span class="sxs-lookup"><span data-stu-id="02594-118">Decision was made to not hire the candidate.</span></span> |
| <span data-ttu-id="02594-119">200000003</span><span class="sxs-lookup"><span data-stu-id="02594-119">200000003</span></span> | <span data-ttu-id="02594-120">Chiuso</span><span class="sxs-lookup"><span data-stu-id="02594-120">Dismissed</span></span> | <span data-ttu-id="02594-121">Il candidato non viene più tenuto in considerazione.</span><span class="sxs-lookup"><span data-stu-id="02594-121">The candidate was dismissed from consideration.</span></span> |

## <a name="see-also"></a><span data-ttu-id="02594-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="02594-122">See also</span></span>

[<span data-ttu-id="02594-123">Introduzione all'API di integrazione del sistema di tracciabilità dei candidati</span><span class="sxs-lookup"><span data-stu-id="02594-123">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="02594-124">Query di esempio per il candidato da assumere</span><span class="sxs-lookup"><span data-stu-id="02594-124">Example query for Candidate to hire</span></span>](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]