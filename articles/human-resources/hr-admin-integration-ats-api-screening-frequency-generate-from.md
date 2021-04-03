---
title: Frequenza di screening generata da
description: Questo argomento descrive la frequenza di screening generata dall'opzione impostata per Dynamics 365 Human Resources.
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
ms.openlocfilehash: 238cd5da750d815c904090cc9002e3d1a5d2bcc7
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/17/2021
ms.locfileid: "5464576"
---
# <a name="screening-frequency-generate-from"></a><span data-ttu-id="aecbc-103">Frequenza di screening generata da</span><span class="sxs-lookup"><span data-stu-id="aecbc-103">Screening frequency generate from</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="aecbc-104">Questo argomento descrive la frequenza di screening generata dall'opzione impostata per Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="aecbc-104">This topic describes the Screening frequency generate from option set for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="aecbc-105">Nome fisico: mshr_hcmfrequencygeneratefrom</span><span class="sxs-lookup"><span data-stu-id="aecbc-105">Physical name: mshr_hcmfrequencygeneratefrom</span></span>

<span data-ttu-id="aecbc-106">Questa enumerazione fornisce il set di opzioni di valori per determinare la data di inizio del calcolo per il successivo screening richiesto.</span><span class="sxs-lookup"><span data-stu-id="aecbc-106">This enumeration provides the option set of values for determining the start date of the calculation for the next required screening.</span></span>

| <span data-ttu-id="aecbc-107">Valore</span><span class="sxs-lookup"><span data-stu-id="aecbc-107">Value</span></span> | <span data-ttu-id="aecbc-108">Etichetta</span><span class="sxs-lookup"><span data-stu-id="aecbc-108">Label</span></span> | <span data-ttu-id="aecbc-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="aecbc-109">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="aecbc-110">200000000 non selezionato</span><span class="sxs-lookup"><span data-stu-id="aecbc-110">200000000 Not selected</span></span> | <span data-ttu-id="aecbc-111">Non è stato selezionato alcun valore.</span><span class="sxs-lookup"><span data-stu-id="aecbc-111">No value has been selected.</span></span> |
| <span data-ttu-id="aecbc-112">200000001 Data di completamento</span><span class="sxs-lookup"><span data-stu-id="aecbc-112">200000001 Date completed</span></span> | <span data-ttu-id="aecbc-113">Il calcolo viene eseguito dall'ultima data di screening completata.</span><span class="sxs-lookup"><span data-stu-id="aecbc-113">Calculation is done from the last screening date completed.</span></span> |
| <span data-ttu-id="aecbc-114">200000002 data richiesta</span><span class="sxs-lookup"><span data-stu-id="aecbc-114">200000002 Date required</span></span> | <span data-ttu-id="aecbc-115">Il calcolo viene eseguito dall'ultima data di screening necessaria.</span><span class="sxs-lookup"><span data-stu-id="aecbc-115">Calculation is done from the last screening date required.</span></span> |

## <a name="see-also"></a><span data-ttu-id="aecbc-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="aecbc-116">See also</span></span>

[<span data-ttu-id="aecbc-117">Introduzione all'API di integrazione del sistema di tracciabilità dei candidati</span><span class="sxs-lookup"><span data-stu-id="aecbc-117">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="aecbc-118">Query di esempio per il candidato da assumere</span><span class="sxs-lookup"><span data-stu-id="aecbc-118">Example query for Candidate to hire</span></span>](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]