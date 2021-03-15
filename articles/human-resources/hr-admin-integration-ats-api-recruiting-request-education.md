---
title: Istruzione richiesta di selezione
description: Questo argomento descrive l'entità Istruzione richiesta di selezione per Dynamics 365 Human Resources.
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
ms.openlocfilehash: 1767edfe67f9c3af4ac67eb5403d63a7f54dcac8
ms.sourcegitcommit: 33b5c8bc4f9461e290513aa22de1ec1fba3b0742
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/05/2021
ms.locfileid: "5126076"
---
# <a name="recruiting-request-education"></a>Istruzione richiesta di selezione

Questo argomento descrive l'entità Istruzione richiesta di selezione per Dynamics 365 Human Resources.

Nome fisico: mshr_hcmrecruitingrequesteducationentity

### <a name="description"></a>descrizione

Descrive i requisiti di istruzione per una richiesta di selezione.

### <a name="json-representation"></a>Rappresentazione JSON

```json
{
    "mshr_recruitingrequestid": "String",
    "mshr_educationdisciplineid": "String",
    "mshr_educationdisciplinedescription": "String",
    "mshr_educationlevelid": "String",
    "mshr_educationleveldescription": "String",
    "mshr_dataareaid": "String",
    "_mshr_dataareaid_id_value": "Guid",
    "mshr_primaryfield": "String",
    "_mshr_fk_recruitingrequest_id_value": "Guid",
    "_mshr_fk_educationdiscipline_id_value": "Guid",
    "_mshr_fk_educationlevel_id_value": "Guid",
    "mshr_hcmrecruitingrequesteducationentityid": "Guid"
}
```

### <a name="properties"></a>Proprietà

| Proprietà<br>**Nome fisico**<br>**_Tipo_** | Utilizza | descrizione |
| --- | --- | --- |
| **ID entità istruzione richiesta di selezione**<br>mshr_hcmrecruitingrequesteducationentityid<br>*GUID* | Sola lettura<br>Richiesto | Identificatore univoco generato dal sistema per il record dell'istruzione della richiesta di selezione. |
| **ID richiesta di selezione**<br>mshr_recruitingrequestid<br>*String* | Scrivi una volta<br>Richiesto | L'identificatore univoco leggibile dall'utente della richiesta di selezione correlata. |
| **Valore ID richiesta di selezione**<br>_mshr_fk_recruitingrequest_id_value<br>*GUID* | Sola lettura<br>Richiesto<br>Chiave esterna: mshr_hcmrecruitingrequestentityid di mshr_hcmrecruitingrequestentity | L'identificatore univoco generato dall'utente della richiesta di selezione correlata. |
| **ID livello di istruzione**<br>mshr_educationlevelid<br>*String* | Scrivi una volta<br>Richiesto | Il livello di istruzione richiesto. |
| **Valore ID livello di istruzione**<br>_mshr_fk_educationlevel_id_value<br>*GUID* | Sola lettura<br>Richiesto<br>Chiave esterna: mshr_hcmeducationlevelentityid di mshr_hcmeducationlevelentity | Identificatore univoco generato dal sistema per il livello di istruzione richiesto. |
| **Descrizione del livello di istruzione**<br>mshr_educationleveldescription<br>*String* | Sola lettura<br>Richiesto | La descrizione del livello richiesto per la competenza. |
| **ID discipline percorsi formativi**<br>mshr_educationdisciplinedescription<br>*String* | Scrivi una volta<br>Richiesto | L'area della disciplina educativa. |
| **Valore ID discipline percorsi formativi**<br>_mshr_fk_educationdiscipline_id_value<br>*GUID* | Sola lettura<br>Richiesto<br>Chiave esterna: mshr_hcmeducationdisciplineentityid di mshr_hcmeducationdisciplineentity | Identificatore univoco generato dal sistema per l'area della disciplina educativa. |
| **Descrizione discipline istruzione**<br>mshr_educationdisciplinedescription<br>String | Sola lettura<br>Richiesto | La descrizione dell'area della disciplina educativa. |
| **ID area dati**<br>mshr_dataareaid<br>*String* | Lettura/scrittura<br>Facoltativo | Specifica la persona giuridica (società).|
| **Valore ID area dati**<br>_mshr_dataareaid_id_value<br>*GUID* | Sola lettura<br>Facoltativo<br>Chiave esterna: cdm_companyid dell'entità cdm_company | Valore GUID generato dal sistema che identifica la persona giuridica (società). |
| **Campo principale**<br>mshr_primaryfield<br>*String* | Sola lettura<br>Richiesto | Concatenazione del valore della richiesta di selezione, dell'ID del livello di istruzione e dell'ID della disciplina educativa come un altro metodo per identificare in modo univoco il record. |

## <a name="see-also"></a>Vedere anche

[Introduzione all'API di integrazione del sistema di tracciabilità dei candidati](hr-admin-integration-ats-api-introduction.md)<br>
[Query di esempio per la richiesta di selezione](hr-admin-integration-ats-api-recruiting-request-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]