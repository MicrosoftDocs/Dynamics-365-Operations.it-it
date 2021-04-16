---
title: Competenza di richiesta di selezione
description: Questo argomento descrive l'entità della competenza della richiesta di selezione per Dynamics 365 Human Resources.
author: jaredha
ms.date: 02/05/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2021-02-05
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 9e464ced904eb4358ba5d4e1c6c2c36089bfa0d8
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5801313"
---
# <a name="recruiting-request-skill"></a>Competenza di richiesta di selezione

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Questo argomento descrive l'entità della competenza della richiesta di selezione per Dynamics 365 Human Resources.

Nome fisico: mshr_hcmrecruitingrequestskillentity

### <a name="description"></a>Descrizione

Descrive i requisiti delle competenze per una richiesta di selezione.

### <a name="json-representation"></a>Rappresentazione JSON

```json
{
    "mshr_recruitingrequestid": "String",
    "mshr_skillid": "String",
    "mshr_skilldescription": "String",
    "mshr_ratinglevelid": "String",
    "mshr_ratingmodelid": "String",
    "mshr_ratingleveldescription": "String",
    "mshr_dataareaid": "String",
    "_mshr_dataareaid_id_value": "Guid",
    "mshr_primaryfield": "String",
    "_mshr_fk_recruitingrequest_id_value": "Guid",
    "_mshr_fk_skill_id_value": "Guid",
    "_mshr_fk_ratinglevel_id_value": "Guid",
    "_mshr_fk_ratingmodel_id_value": "Guid",
    "mshr_hcmrecruitingrequestskillentityid": "Guid"
}
```

### <a name="properties"></a>Proprietà

| Proprietà<br>**Nome fisico**<br>**_Tipo_** | Utilizza | Descrizione |
| --- | --- | --- |
| **ID entità competenza richiesta di selezione**<br>mshr_hcmrecruitingrequestskillentityid<br>*GUID* | Sola lettura<br>Richiesto | Identificatore univoco generato dal sistema per il record **Competenza di richiesta di selezione**. |
| **ID richiesta di selezione**<br>mshr_recruitingrequestid<br>*String* | Scrivi una volta<br>Richiesto | L'identificatore univoco leggibile dall'utente della richiesta di selezione associata. |
| **Valore ID richiesta di selezione**<br>_mshr_fk_recruitingrequest_id_value<br>*GUID* | Sola lettura<br>Richiesto<br> Chiave esterna: mshr_hcmrecruitingrequestentityid dell'entità mshr_hcmrecruitingrequestentity | L'identificatore univoco generato dall'utente della richiesta di selezione associata. |
| **ID competenza**<br>mshr_skillid<br>*String*<br> | Scrivi una volta<br>Richiesto | L'identificatore univoco leggibile dall'utente della competenza richiesta. |
| **Valore ID competenza**<br>_mshr_fk_skill_id_value<br>*GUID* | Sola lettura<br>Richiesto<br>Chiave esterna: mshr_hcmskillentityid dell'entità mshr_hcmskillentity | Identificatore univoco generato dal sistema della competenza richiesta. |
| **ID livello valutazione**<br>mshr_ratinglevelid<br>*String* | Scrivi una volta<br>Facoltativo | Il valore del livello di competenze richiesto selezionato per il lavoro, in base al modello di valutazione assegnato alla competenza. |
| **Valore ID livello di valutazione**<br>_mshr_fk_ratinglevel_id_value<br>*GUID* | Sola lettura<br>Facoltativo<br>Chiave esterna: mshr_hcmratinglevelentityid dell'entità mshr_hcmratinglevelentity | Identificatore univoco generato dal sistema per il livello. |
| **Descrizione competenze**<br>mshr_skilldescription<br>*String* | Sola lettura<br>Richiesto | La descrizione delle competenze. |
| **Descrizione del livello di valutazione**<br>mshr_ratingleveldescription<br>*String* | Sola lettura<br>Facoltativo | La descrizione del livello delle competenze selezionato. |
| **ID area dati**<br>mshr_dataareaid<br>*String* | Lettura/scrittura<br>Facoltativo | Specifica la persona giuridica (società). |
| **Valore ID area dati**<br>_mshr_dataareaid_id_value<br>*GUID* | Sola lettura<br>Facoltativo<br>Chiave esterna: cdm_companyid dell'entità cdm_company | Valore GUID generato dal sistema che identifica la persona giuridica (società). |
| **Campo principale**<br>mshr_primaryfield<br>*String* | Sola lettura<br>Richiesto | Concatenazione del valore della richiesta di selezione, dell'ID delle competenze come altro metodo per identificare in modo univoco il record. |
| **ID modello di valutazione**<br>mshr_ratingmodelid<br>*String* | Lettura/scrittura<br>Richiesto | Il modello di valutazione utilizzato per valutare la competenza. |
| **Valore ID del modello di valutazione**<br>_mshr_fk_hcmratingmodel_id_value<br>*GUID* | Sola lettura<br>Richiesto<br>Chiave esterna: mshr_hcmratingmodelentityid dell'entità mshr_hcmratingmodelentity | Identificatore univoco generato dal sistema del modello di valutazione utilizzato per valutare la competenza. |

## <a name="see-also"></a>Vedere anche

[Introduzione all'API di integrazione del sistema di tracciabilità dei candidati](hr-admin-integration-ats-api-introduction.md)<br>
[Query di esempio per la richiesta di selezione](hr-admin-integration-ats-api-recruiting-request-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]