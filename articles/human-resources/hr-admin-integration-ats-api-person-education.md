---
title: Educazione della persona
description: Questo argomento descrive l'entità Educazione persona per Dynamics 365 Human Resources.
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
ms.openlocfilehash: cfa05fe6816c6b24034f8f015bf6e42d665ef1dc
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/17/2021
ms.locfileid: "5466498"
---
# <a name="person-education"></a>Educazione della persona

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Questo argomento descrive l'entità Educazione persona per Dynamics 365 Human Resources.

Nome fisico: mshr_hcmpersoneducationentity

## <a name="description"></a>Descrizione

Questa entità contiene la cronologia educativa della persona che è il candidato. L'istruzione è collegata al record della persona che consente di associare l'istruzione a qualsiasi altro ruolo creato per la persona oltre al record del candidato (lavoratore, appaltatore e così via).

## <a name="json-representation"></a>Rappresentazione JSON

```json
{
    "mshr_creditbasis": Int,
    "mshr_creditscompleted": Decimal,
    "mshr_creditsearned": Decimal,
    "mshr_creditsneeded": Decimal,
    "mshr_description": "String",
    "mshr_duration": Decimal,
    "mshr_durationunit": Int,
    "mshr_educationdisciplineid": "String",
    "mshr_educationinstitutionid": "String",
    "mshr_educationlevelid": "String",
    "mshr_enddate": "Date",
    "mshr_gradepointaverage": Decimal,
    "mshr_gradescale": "String",
    "mshr_notes": "String",
    "mshr_secondaryemphasis": "String",
    "mshr_startdate": "Date",
    "mshr_partynumber": "String",
    "mshr_primaryfield": "String",
    "_mshr_fk_educationdiscipline_id_value": "Guid",
    "_mshr_fk_person_id_value": "Guid",
    "_mshr_fk_educationinstitution_id_value": "Guid",
    "_mshr_fk_educationlevel_id_value": "Guid",
    "mshr_hcmpersoneducationentityid": "Guid"
}
```

## <a name="properties"></a>Proprietà

| Proprietà<br>**Nome fisico**<br>**_Tipo_** | Utilizza | Descrizione |
| --- | --- | --- |
| **ID entità educazione persona**<br>mshr_hcmpersoneducationentityid<br>*GUID* | Sola lettura<br>Richiesto | Identificatore univoco generato dal sistema per il record dell'entità dell'educazione della persona. |
| **Numero parte**<br>mshr_partynumber<br>*String* | Lettura/scrittura<br>Richiesto | L'identificatore univoco del record della parte (persona) per il candidato. |
| **Valore ID persona**<br>_mshr_fk_person_id_value<br>*GUID* | Sola lettura<br>Richiesto<br>Chiave esterna: mshr_dirpersonentityid di mshr_dirpersonentity | L'identificatore univoco generato dal sistema per il record della persona del candidato. |
| **Base di credito**<br>mshr_creditbasis<br>*set di opzioni mshr_hcmeducationcreditbasis* | Lettura/scrittura<br>Facoltativo | La base di credito del titolo di studio. |
| **Crediti completati**<br>mshr_creditscompleted<br>*Decimali* | Lettura/scrittura<br>Facoltativo | Il numero di crediti completati per l'istruzione. |
| **Crediti ottenuti**<br>mshr_creditsearned<br>*Decimali* | Lettura/scrittura<br>Facoltativo | Il numero di crediti guadagnati per il record relativo al percorso formativo per una laurea in corso. |
| **Crediti necessari**<br>mshr_creditsneeded<br>*Decimali* | Lettura/scrittura<br>Facoltativo | Il numero di crediti richiesti per una laurea in corso. |
| **Descrizione**<br>mshr_description<br>*String* | Lettura/scrittura<br>Facoltativo | Una descrizione del titolo di studio del candidato. |
| **ID livello di istruzione**<br>mshr_educationlevelid<br>*String* | Lettura/scrittura<br>Facoltativo | L'ID del livello di istruzione. | 
| **Valore ID livello di istruzione**<br>_mshr_fk_educationlevel_id_value<br>*GUID* | Sola lettura<br>Facoltativo<br>Chiave esterna: mshr_hcmeducationdegreeentityid dell'entità mshr_hcmeducationdegreeentity | Identificatore generato dal sistema per il record del titolo di studio. Questo identificatore fornisce i gradi e i livelli di istruzione definiti per l'organizzazione. |
| **ID Discipline percorsi formativi**<br>mshr_educationdisciplineid<br>*String* | Lettura/scrittura<br>Richiesto<br>Chiave straniera: EducationDiscipline | L'ID della disciplina del livello di istruzione. |
| **Valore ID discipline percorsi formativi**<br>_mshr_fk_educationdiscipline_id_value<br>*GUID* | Sola lettura<br>Richiesto<br>Chiave esterna: mshr_hcmeducationdisciplineentityid di mshr_hcmeducationdisciplineentity | L'identificatore univoco generato dal sistema per la disciplina formativa del record del percorso di formazione. |
| **Area secondaria**<br>mshr_secondaryemphasis<br>*String* | Lettura/scrittura<br>Facoltativo | L'enfasi secondaria del titolo di studio conseguito. |
| **ID istituto scolastico**<br>mshr_educationinstitutionid<br>*String* | Lettura/scrittura<br>Facoltativo | L'ID dell'istituto scolastico frequentato. |
| **Valore ID istituto scolastico**<br>_mshr_fk_educationinstitution_id_value<br>*GUID* | Sola lettura<br>Facoltativo<br>Chiave esterna: mshr_hcmeducationinstitutionentityid di mshr_hcmeducationinstitutionentity | Identificatore generato dal sistema dell'istituto scolastico. |
| **Data di inizio**<br>mshr_startdate<br>*Datetime* | Lettura/scrittura<br>Facoltativo | La data di inizio della formazione per il titolo conseguito. |
| **Data di fine**<br>mshr_enddate<br>*Datetime* | Lettura/scrittura<br>Richiesto | La data in cui è stata rilasciata la credenziale. |
| **Durata**<br>mshr_duration<br>*Decimali* | Lettura/scrittura<br>Facoltativo | La durata del record relativo al percorso formativo. |
| **Unità di durata**<br>mshr_durationunit<br>*set di opzioni mshr_periodunit* | Lettura/scrittura<br>Facoltativo | L'unità di tempo associata alla durata del record di istruzione. |
| **Media risultati valutazione**<br>mshr_gradepointaverage<br>*Decimali* | Lettura/scrittura<br>Facoltativo | Media dei risultati della valutazione per il titolo di studio. |
| **Scala dei voti**<br>mshr_gradescale<br>*String* | Lettura/scrittura<br>Facoltativo | La scala utilizzata per valutazione per il titolo di studio. |
| **Note**<br>mshr_notes<br>*String* | Lettura/scrittura<br>Facoltativo | Note per l'utilizzo da parte del reclutatore o del responsabile delle assunzioni. |
| **Campo primario**<br>mshr_primaryfield<br>*String* | Sola lettura<br>Richiesto | Campo utilizzato come un altro identificatore principale del record dell'entità. Combinazione di numero di parte, ID disciplina educativa, ID istituto di istruzione e ID livello di istruzione. |

## <a name="see-also"></a>Vedere anche

[Introduzione all'API di integrazione del sistema di tracciabilità dei candidati](hr-admin-integration-ats-api-introduction.md)<br>
[Query di esempio per il candidato da assumere](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]