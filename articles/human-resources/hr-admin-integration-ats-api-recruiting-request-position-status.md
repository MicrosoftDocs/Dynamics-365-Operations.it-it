---
title: Stato della posizione della richiesta di selezione
description: Questo argomento descrive l'opzione Stato posizione richiesta di selezione impostata per Dynamics 365 Human Resources.
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
ms.openlocfilehash: 01e8aa5157d0ad1c01f996886e7845e49ab97603
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/17/2021
ms.locfileid: "5464720"
---
# <a name="recruiting-request-position-status"></a><span data-ttu-id="e9b7c-103">Stato della posizione della richiesta di selezione</span><span class="sxs-lookup"><span data-stu-id="e9b7c-103">Recruiting request position status</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="e9b7c-104">Questo argomento descrive l'opzione Stato posizione richiesta di selezione impostata per Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="e9b7c-104">This topic describes the Recruiting request position status option set for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="e9b7c-105">Nome fisico: mshr_hcmrecruitingrequestpositionstatus</span><span class="sxs-lookup"><span data-stu-id="e9b7c-105">Physical name: mshr_hcmrecruitingrequestpositionstatus</span></span>

<span data-ttu-id="e9b7c-106">Questa enumerazione fornisce l'opzione impostata per i valori di stato di ciascuna posizione una richiesta di selezione nell'entità RecruitingRequestPosition.</span><span class="sxs-lookup"><span data-stu-id="e9b7c-106">This enumeration provides the option set for the status values of each position a recruiting request in the RecruitingRequestPosition entity.</span></span>

| <span data-ttu-id="e9b7c-107">Valore</span><span class="sxs-lookup"><span data-stu-id="e9b7c-107">Value</span></span> | <span data-ttu-id="e9b7c-108">Etichetta</span><span class="sxs-lookup"><span data-stu-id="e9b7c-108">Label</span></span> | <span data-ttu-id="e9b7c-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e9b7c-109">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="e9b7c-110">200000000</span><span class="sxs-lookup"><span data-stu-id="e9b7c-110">200000000</span></span> | <span data-ttu-id="e9b7c-111">Scadenze aperte</span><span class="sxs-lookup"><span data-stu-id="e9b7c-111">Open</span></span> | <span data-ttu-id="e9b7c-112">La posizione nella richiesta di reclutamento è aperta alla selezione.</span><span class="sxs-lookup"><span data-stu-id="e9b7c-112">The position in the recruiting request is open for recruiting.</span></span> <span data-ttu-id="e9b7c-113">Ciò non indica che non esiste un'assegnazione di posizione attualmente attiva per la posizione.</span><span class="sxs-lookup"><span data-stu-id="e9b7c-113">This does not indicate that there is no currently active position assignment for the position.</span></span> <span data-ttu-id="e9b7c-114">Potrebbe esserci un dipendente nella posizione al momento dell'assunzione.</span><span class="sxs-lookup"><span data-stu-id="e9b7c-114">There may be an employee in the position at the time of recruiting.</span></span> <span data-ttu-id="e9b7c-115">Indica solo che la posizione è disponibile per la selezione nel contesto della richiesta di selezione.</span><span class="sxs-lookup"><span data-stu-id="e9b7c-115">It indicates only that the position is available for recruiting in the context of the recruiting request.</span></span> |
| <span data-ttu-id="e9b7c-116">200000001</span><span class="sxs-lookup"><span data-stu-id="e9b7c-116">200000001</span></span> | <span data-ttu-id="e9b7c-117">Chiusa</span><span class="sxs-lookup"><span data-stu-id="e9b7c-117">Filled</span></span> | <span data-ttu-id="e9b7c-118">È stato selezionato un lavoratore per l'assegnazione alla posizione.</span><span class="sxs-lookup"><span data-stu-id="e9b7c-118">A worker has been selected for assignment to the position.</span></span> |
| <span data-ttu-id="e9b7c-119">200000002</span><span class="sxs-lookup"><span data-stu-id="e9b7c-119">200000002</span></span> | <span data-ttu-id="e9b7c-120">Annullate</span><span class="sxs-lookup"><span data-stu-id="e9b7c-120">Canceled</span></span> | <span data-ttu-id="e9b7c-121">La richiesta di selezione per questa posizione è stata annullata.</span><span class="sxs-lookup"><span data-stu-id="e9b7c-121">The request to recruit for this position has been canceled.</span></span> |

## <a name="see-also"></a><span data-ttu-id="e9b7c-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e9b7c-122">See also</span></span>

[<span data-ttu-id="e9b7c-123">Introduzione all'API di integrazione del sistema di tracciabilità dei candidati</span><span class="sxs-lookup"><span data-stu-id="e9b7c-123">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="e9b7c-124">Query di esempio per la richiesta di selezione</span><span class="sxs-lookup"><span data-stu-id="e9b7c-124">Example query for Recruiting request</span></span>](hr-admin-integration-ats-api-recruiting-request-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]