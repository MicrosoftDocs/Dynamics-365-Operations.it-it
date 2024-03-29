---
title: Query di esempio per il candidato da assumere
description: Questo articolo fornisce una query di esempio per l'entità Candidato da assumere in Dynamics 365 Human Resources.
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
ms.openlocfilehash: 2dd744665d4f0b6c64f4ee45a01c237081018514
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8848344"
---
# <a name="example-query-for-candidate-to-hire"></a>Query di esempio per il candidato da assumere


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Questo articolo fornisce una query di esempio per l'entità Candidato da assumere in Dynamics 365 Human Resources.

Questo articolo fornisce un esempio che dimostra come utilizzare *inserti profondi* per creare tutti i dettagli di un nuovo record candidato in una singola operazione API. Per ulteriori informazioni sugli inserti profondi, vedi [Crea record di entità correlate in un'unica operazione ](/powerapps/developer/data-platform/webapi/create-entity-web-api#create-related-entity-records-in-one-operation).

L'entità **mshr_hcmcandidatetohireentity** è unica a causa della sua relazione con l'entità **mshr_dirpersonentity**. Molte delle proprietà su **mshr_hcmcandidatetohireentity** (ad esempio,**mshr_firstname**, **mshr_lastname** e **mshr_birthdate**) sono derivati dal record **mshr_dirpersonentity**. Se pubblichi un nuovo record candidato in **mshr_hcmcandidatetohireentity** senza utilizzare inserti profondi, puoi definire i valori per queste proprietà direttamente nel record **mshr_hcmcandidatetohireentity**. Il record associato **mshr_dirpersonentity** viene creato implicitamente con i valori definiti per le proprietà. Puoi quindi creare qualsiasi altro record di entità correlato (ad esempio competenze o istruzione) come chiamate API separate.

Se, tuttavia, desideri utilizzare inserti profondi per creare tutte le entità correlate in un'unica operazione, le proprietà specifiche dell'entità **mshr_dirpersonentity** deve essere definita su quel livello annidato dell'operazione.

Questo esempio mostra come creare un record candidato, il record della persona associata e le competenze e l'istruzione della persona in tre livelli annidati utilizzando inserimenti profondi in una singola operazione API.

> [!NOTE]
> L'esempio non include tutte le proprietà di ciascuna delle entità API. Versione semplificata a solo scopo dimostrativo.

**Richiesta**

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

**Risposta**

```http

HTTP/1/1 204 No Content
OData-Version: 4.0
OData-EntityId: [Organization URI]/api/data/v9.1/mshr_hcmcandidatetohireentities(00000d2d-0000-0000-7317-005001000000)

```

## <a name="see-also"></a>Vedere anche

[Introduzione all'API di integrazione del sistema di tracciabilità dei candidati](hr-admin-integration-ats-api-introduction.md)<br>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
