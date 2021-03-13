---
title: Query di esempio per il candidato da assumere
description: Questo argomento fornisce una query di esempio per l'entità Candidato da assumere in Dynamics 365 Human Resources.
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
ms.openlocfilehash: 963e12e9114664a995b92ffe22063c14f904da35
ms.sourcegitcommit: 33b5c8bc4f9461e290513aa22de1ec1fba3b0742
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/05/2021
ms.locfileid: "5125763"
---
# <a name="example-query-for-candidate-to-hire"></a><span data-ttu-id="033b2-103">Query di esempio per il candidato da assumere</span><span class="sxs-lookup"><span data-stu-id="033b2-103">Example query for Candidate to hire</span></span>

<span data-ttu-id="033b2-104">Questo argomento fornisce una query di esempio per l'entità Candidato da assumere in Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="033b2-104">This topic provides an example query for the Candidate to hire entity in Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="033b2-105">Questo argomento fornisce un esempio che dimostra come utilizzare *inserti profondi* per creare tutti i dettagli di un nuovo record candidato in una singola operazione API.</span><span class="sxs-lookup"><span data-stu-id="033b2-105">This topic provides an example demonstrating how you can use *deep inserts* to create all the detail of a new candidate record in a single API operation.</span></span> <span data-ttu-id="033b2-106">Per ulteriori informazioni sugli inserti profondi, vedi [Crea record di entità correlate in un'unica operazione ](https://docs.microsoft.com/powerapps/developer/data-platform/webapi/create-entity-web-api#create-related-entity-records-in-one-operation).</span><span class="sxs-lookup"><span data-stu-id="033b2-106">For more information about deep inserts, see [Create related entity records in one operation](https://docs.microsoft.com/powerapps/developer/data-platform/webapi/create-entity-web-api#create-related-entity-records-in-one-operation).</span></span>

<span data-ttu-id="033b2-107">L'entità **mshr_hcmcandidatetohireentity** è unica a causa della sua relazione con l'entità **mshr_dirpersonentity**.</span><span class="sxs-lookup"><span data-stu-id="033b2-107">The **mshr_hcmcandidatetohireentity** entity is unique because of its relationship to the **mshr_dirpersonentity** entity.</span></span> <span data-ttu-id="033b2-108">Molte delle proprietà su **mshr_hcmcandidatetohireentity** (ad esempio,**mshr_firstname**, **mshr_lastname** e **mshr_birthdate**) sono derivati dal record **mshr_dirpersonentity**.</span><span class="sxs-lookup"><span data-stu-id="033b2-108">Many of the properties on the **mshr_hcmcandidatetohireentity** (for example, **mshr_firstname**, **mshr_lastname**, and **mshr_birthdate**) are derived from the **mshr_dirpersonentity** record.</span></span> <span data-ttu-id="033b2-109">Se pubblichi un nuovo record candidato in **mshr_hcmcandidatetohireentity** senza utilizzare inserti profondi, puoi definire i valori per queste proprietà direttamente nel record **mshr_hcmcandidatetohireentity**.</span><span class="sxs-lookup"><span data-stu-id="033b2-109">If you post a new candidate record to **mshr_hcmcandidatetohireentity** without using deep inserts, you can define values for these properties directly on the **mshr_hcmcandidatetohireentity** record.</span></span> <span data-ttu-id="033b2-110">Il record associato **mshr_dirpersonentity** viene creato implicitamente con i valori definiti per le proprietà.</span><span class="sxs-lookup"><span data-stu-id="033b2-110">The associated **mshr_dirpersonentity** record is created implicitly with the defined values for the properties.</span></span> <span data-ttu-id="033b2-111">Puoi quindi creare qualsiasi altro record di entità correlato (ad esempio competenze o istruzione) come chiamate API separate.</span><span class="sxs-lookup"><span data-stu-id="033b2-111">You can then create any other related entity records (such as skills or education) as separate API calls.</span></span>

<span data-ttu-id="033b2-112">Se, tuttavia, desideri utilizzare inserti profondi per creare tutte le entità correlate in un'unica operazione, le proprietà specifiche dell'entità **mshr_dirpersonentity** deve essere definita su quel livello annidato dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="033b2-112">If, however, you want to use deep inserts to create all related entities in one operation, the properties specific to the **mshr_dirpersonentity** entity must be defined on that nested level of the operation.</span></span>

<span data-ttu-id="033b2-113">Questo esempio mostra come creare un record candidato, il record della persona associata e le competenze e l'istruzione della persona in tre livelli annidati utilizzando inserimenti profondi in una singola operazione API.</span><span class="sxs-lookup"><span data-stu-id="033b2-113">This example shows how you can create a candidate record, the associated person record, and the person's skills and education in three nested levels using deep inserts in a single API operation.</span></span>

> [!NOTE]
> <span data-ttu-id="033b2-114">L'esempio non include tutte le proprietà di ciascuna delle entità API.</span><span class="sxs-lookup"><span data-stu-id="033b2-114">The example does not include all properties of each of the API entities.</span></span> <span data-ttu-id="033b2-115">Versione semplificata a solo scopo dimostrativo.</span><span class="sxs-lookup"><span data-stu-id="033b2-115">It is simplified for demonstration purposes.</span></span>

<span data-ttu-id="033b2-116">**Richiesta**</span><span class="sxs-lookup"><span data-stu-id="033b2-116">**Request**</span></span>

```http

POST [Organization URI]/api/data/v9.1/mshr_hcmcandidatetohireentities
Content-Type: application/json; charset=utf-8
OData-MaxVersion: 4.0
OData-Version: 4.0
Accept: application/json

{
    "mshr_dataareaid": "usmf",
    "mshr_recruitingrequestid": "USMF-000141",
    "mshr_positionid": "000601",
    "mshr_iswillingtorelocate": 200000000,
    "mshr_availabilitydate": "2021-03-18",
    "mshr_comments": "Evelyn's experience is exactly what we need for this position.",
    "mshr_FK_Person_id":
        {
            "mshr_firstname": "Evelyn",
            "mshr_lastname": "Chambers",
            "mshr_namesequencedisplayas": "FirstMiddleLast",
            "mshr_FK_HcmPersonSkillEntity_Person":
            [
                {
                    "mshr_skillid": "CustFocus",
                    "mshr_ratingid": "Skills",
                    "mshr_levelid": "4",
                    "mshr_ratinglevelexaminer": "",
                    "mshr_leveltype": 200000000,
                    "mshr_yearsofexperience": 0,
                    "mshr_verified": 200000000,
                    "mshr_leveldate": "2013-01-01T00:00:00Z"
                },
                {
                    "mshr_skillid": "CashFlow",
                    "mshr_ratingid": "Skills",
                    "mshr_levelid": "4",
                    "mshr_ratinglevelexaminer": "",
                    "mshr_leveltype": 200000000,
                    "mshr_yearsofexperience": 0,
                    "mshr_verified": 200000000,
                    "mshr_leveldate": "2013-01-01T00:00:00Z"
                }
            ],
            "mshr_FK_HcmPersonEducationEntity_Person": [
                {
                    "mshr_creditbasis": 200000000,
                    "mshr_enddate": "2021-02-22T00:00:00Z",
                    "mshr_educationlevelid": "Bachelor",
                    "mshr_creditsearned": 0,
                    "mshr_startdate": "2017-02-21T00:00:00Z",
                    "mshr_creditscompleted": 0,
                    "mshr_educationinstitutionid": "Cottonwood Univ",
                    "mshr_educationdisciplineid": "Business Mgmt",
                    "mshr_durationunit": 200000000
                }              
            ]
        }
}
```

<span data-ttu-id="033b2-117">**Risposta**</span><span class="sxs-lookup"><span data-stu-id="033b2-117">**Response**</span></span>

```http

HTTP/1/1 204 No Content
OData-Version: 4.0
OData-EntityId: [Organization URI]/api/data/v9.1/mshr_hcmcandidatetohireentities(00000d2d-0000-0000-7317-005001000000)

```

## <a name="see-also"></a><span data-ttu-id="033b2-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="033b2-118">See also</span></span>

[<span data-ttu-id="033b2-119">Introduzione all'API di integrazione del sistema di tracciabilità dei candidati</span><span class="sxs-lookup"><span data-stu-id="033b2-119">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
