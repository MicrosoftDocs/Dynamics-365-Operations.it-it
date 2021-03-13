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
ms.openlocfilehash: 3f7bae64f58f0bdc1603b3c1b5493f1ebcfa8de9
ms.sourcegitcommit: 33b5c8bc4f9461e290513aa22de1ec1fba3b0742
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/05/2021
ms.locfileid: "5126052"
---
# <a name="recruiting-request-position-status"></a><span data-ttu-id="fe1a4-103">Stato della posizione della richiesta di selezione</span><span class="sxs-lookup"><span data-stu-id="fe1a4-103">Recruiting request position status</span></span>

<span data-ttu-id="fe1a4-104">Questo argomento descrive l'opzione Stato posizione richiesta di selezione impostata per Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="fe1a4-104">This topic describes the Recruiting request position status option set for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="fe1a4-105">Nome fisico: mshr_hcmrecruitingrequestpositionstatus</span><span class="sxs-lookup"><span data-stu-id="fe1a4-105">Physical name: mshr_hcmrecruitingrequestpositionstatus</span></span>

<span data-ttu-id="fe1a4-106">Questa enumerazione fornisce l'opzione impostata per i valori di stato di ciascuna posizione una richiesta di selezione nell'entità RecruitingRequestPosition.</span><span class="sxs-lookup"><span data-stu-id="fe1a4-106">This enumeration provides the option set for the status values of each position a recruiting request in the RecruitingRequestPosition entity.</span></span>

| <span data-ttu-id="fe1a4-107">Valore</span><span class="sxs-lookup"><span data-stu-id="fe1a4-107">Value</span></span> | <span data-ttu-id="fe1a4-108">Etichetta</span><span class="sxs-lookup"><span data-stu-id="fe1a4-108">Label</span></span> | <span data-ttu-id="fe1a4-109">descrizione</span><span class="sxs-lookup"><span data-stu-id="fe1a4-109">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="fe1a4-110">200000000</span><span class="sxs-lookup"><span data-stu-id="fe1a4-110">200000000</span></span> | <span data-ttu-id="fe1a4-111">Scadenze aperte</span><span class="sxs-lookup"><span data-stu-id="fe1a4-111">Open</span></span> | <span data-ttu-id="fe1a4-112">La posizione nella richiesta di reclutamento è aperta alla selezione.</span><span class="sxs-lookup"><span data-stu-id="fe1a4-112">The position in the recruiting request is open for recruiting.</span></span> <span data-ttu-id="fe1a4-113">Ciò non indica che non esiste un'assegnazione di posizione attualmente attiva per la posizione.</span><span class="sxs-lookup"><span data-stu-id="fe1a4-113">This does not indicate that there is no currently active position assignment for the position.</span></span> <span data-ttu-id="fe1a4-114">Potrebbe esserci un dipendente nella posizione al momento dell'assunzione.</span><span class="sxs-lookup"><span data-stu-id="fe1a4-114">There may be an employee in the position at the time of recruiting.</span></span> <span data-ttu-id="fe1a4-115">Indica solo che la posizione è disponibile per la selezione nel contesto della richiesta di selezione.</span><span class="sxs-lookup"><span data-stu-id="fe1a4-115">It indicates only that the position is available for recruiting in the context of the recruiting request.</span></span> |
| <span data-ttu-id="fe1a4-116">200000001</span><span class="sxs-lookup"><span data-stu-id="fe1a4-116">200000001</span></span> | <span data-ttu-id="fe1a4-117">Chiusa</span><span class="sxs-lookup"><span data-stu-id="fe1a4-117">Filled</span></span> | <span data-ttu-id="fe1a4-118">È stato selezionato un lavoratore per l'assegnazione alla posizione.</span><span class="sxs-lookup"><span data-stu-id="fe1a4-118">A worker has been selected for assignment to the position.</span></span> |
| <span data-ttu-id="fe1a4-119">200000002</span><span class="sxs-lookup"><span data-stu-id="fe1a4-119">200000002</span></span> | <span data-ttu-id="fe1a4-120">Annullate</span><span class="sxs-lookup"><span data-stu-id="fe1a4-120">Canceled</span></span> | <span data-ttu-id="fe1a4-121">La richiesta di selezione per questa posizione è stata annullata.</span><span class="sxs-lookup"><span data-stu-id="fe1a4-121">The request to recruit for this position has been canceled.</span></span> |

## <a name="see-also"></a><span data-ttu-id="fe1a4-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fe1a4-122">See also</span></span>

[<span data-ttu-id="fe1a4-123">Introduzione all'API di integrazione del sistema di tracciabilità dei candidati</span><span class="sxs-lookup"><span data-stu-id="fe1a4-123">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="fe1a4-124">Query di esempio per la richiesta di selezione</span><span class="sxs-lookup"><span data-stu-id="fe1a4-124">Example query for Recruiting request</span></span>](hr-admin-integration-ats-api-recruiting-request-example-query.md)
