---
title: Competenza della persona
description: Questo articolo descrive l'entità Competenza persona per Dynamics 365 Human Resources.
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
ms.openlocfilehash: 713fde6d05904f96f7b17721e15805e07159cf78
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8891323"
---
# <a name="person-skill"></a>Competenza della persona


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Questo articolo descrive l'entità Competenza persona per Dynamics 365 Human Resources.

Nome fisico: mshr_hcmpersonskillentity

## <a name="description"></a>Descrizione

Questa entità descrive le competenze di un candidato.

## <a name="json-representation"></a>Rappresentazione JSON

```json
{
    "mshr_certifier": "String",
    "mshr_partynumber": "String",
    "mshr_levelid": "String",
    "mshr_ratinglevelexaminer": "String",
    "mshr_skillid": "String",
    "mshr_ratingid": "String",
    "mshr_leveltype": Int,
    "mshr_yearsofexperience": Decimal,
    "mshr_verified": Int,
    "mshr_leveldate": "Date",
    "mshr_primaryfield": "String",
    "_mshr_fk_certifier_id_value": "Guid",
    "_mshr_fk_person_id_value": "Guid",
    "_mshr_fk_ratinglevel_id_value": "Guid",
    "_mshr_fk_ratinglevelexaminer_id_value": "Guid",
    "_mshr_fk_skill_id_value": "Guid",
    "mshr_hcmpersonskillentityid": "Guid"
}
```

## <a name="properties"></a>Proprietà

| Proprietà<br>**Nome fisico**<br>**_Tipo_** | Utilizza | Descrizione |
| --- | --- | --- |
| **ID entità competenza persona**<br>mshr_hcmpersonskillentityid<br>*GUID* | Sola lettura<br>Richiesto | Identificatore univoco generato dal sistema per il record dell'entità. |
| **Numero parte**<br>mshr_partynumber<br>*String* | Lettura/scrittura<br>Richiesto |   L'ID del record della parte associata (persona). |
| **Valore ID persona**<br>_mshr_fk_person_id_value<br>*GUID* | Sola lettura<br>Richiesto<br>Chiave esterna: mshr_dirpersonentityid di mshr_dirpersonentity | L'identificatore generato dal sistema per il record dell'entità della parte (persona). |
| **Certificatore**<br>mshr_certifier<br>*String* | Lettura/scrittura<br>Facoltativo | Il numero del personale del lavoratore che ha certificato questa competenza. |
| **Valore ID certificatore**<br>_mshr_fk_certifier_id_value<br>*GUID* | Sola lettura<br>Facoltativo<br>Chiave esterna: mshr_hcmworkerentityid di mshr_hcmworkerentity | Identificatore univoco generato dal sistema del record del lavoratore per il lavoratore che ha certificato la competenza. |
| **ID competenza**<br>mshr_skillid<br>*String* | Lettura/scrittura<br>Richiesto | L'identificatore della competenza definito in Human Resources. |
| **Valore ID competenza**<br>_mshr_fk_skill_id_value<br>*GUID* | Sola lettura<br>Richiesto<br>Chiave esterna: mshr_hcmskillentityid di mshr_hcmskillentity | L'identificatore generato dal sistema della competenza selezionata. |
| **Anni di esperienza**<br>mshr_yearsofexperience<br>*Decimali* | Lettura/scrittura<br>Facoltativo | Gli anni di esperienza che il candidato possiede per questa competenza. |
| **ID valutazione**<br>mshr_ratingid<br>*String* | Lettura/scrittura<br>Richiesto | Il tipo di scala di valutazione. Per questa entità, il valore è **Competenze**. |
| **Tipo di livello**<br>mshr_leveltype<br>*set di opzioni mshr_hrmskillleveltype* | Lettura/scrittura<br>Richiesto | Una classificazione per tipo per il livello assegnato all'abilità. |
| **ID livello**<br>mshr_levelid<br>*String* | Lettura/scrittura<br>Richiesto | L'ID del livello di valutazione che il candidato ha per questa competenza. |
| **Valore ID livello di valutazione**<br>_mshr_fk_ratinglevel_id_value<br>*GUID* | Sola lettura<br>Richiesto<br>Chiave esterna: mshr_hcmratinglevelentityid di mshr_hcmratinglevelentity | L'identificatore generato dal sistema del livello di valutazione. |
| **Data del livello**<br>mshr_leveldate<br>*Datetime* | Lettura/scrittura<br>Richiesto | La data in cui il candidato è stato valutato nella competenza. |
| **Esaminatore del livello di valutazione**<br>mshr_ratinglevelexaminer<br>*String* | Lettura/scrittura<br>Facoltativo | Il numero del personale del lavoratore che ha valutato il candidato. |
| **Valore ID esaminatore del livello di valutazione**<br>_mshr_fk_ratinglevelexaminer_id_value<br>*GUID* | Sola lettura<br>Facoltativo<br>Chiave esterna: mshr_hcmworkerentityid di mshr_hcmworkerentity | L'identificatore generato dal sistema del lavoratore che ha esaminato il livello di competenza del candidato. |
| **Verificata**<br>mshr_verified<br>*set di opzioni mshr_noyes* | Lettura/scrittura<br>Richiesto | Indica se il livello di competenza indicato è stato verificato. |
| **Campo principale**<br>mshr_primaryfield<br>*String* | Sola lettura<br>Richiesto | Campo da utilizzare come un identificatore principale del record dell'entità. Combinazione di numero di parte, tipo di livello, ID competenza e data di livello. |

## <a name="see-also"></a>Vedere anche

[Introduzione all'API di integrazione del sistema di tracciabilità dei candidati](hr-admin-integration-ats-api-introduction.md)<br>
[Query di esempio per il candidato da assumere](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
