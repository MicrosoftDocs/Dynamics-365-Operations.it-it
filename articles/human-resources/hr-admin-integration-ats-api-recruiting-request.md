---
title: Richiesta di selezione
description: Questo articolo descrive l'entità della richiesta di selezione per Dynamics 365 Human Resources.
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
ms.openlocfilehash: 58e509a819e5cda650fddab8dd0c4d55d5148db1
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8872270"
---
# <a name="recruiting-request"></a>Richiesta di selezione


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Questo articolo descrive l'entità della richiesta di selezione per Dynamics 365 Human Resources.

Nome fisico: mshr_hcmrecruitingrequestentity

### <a name="description"></a>Descrizione

Descrive una richiesta di reclutamento per un lavoro.

### <a name="json-representation"></a>Rappresentazione JSON

```json
{
    "mshr_recruitingrequestid": "String",
    "mshr_hiringmanagerpersonnelnumber": "String",
    "mshr_recruiterpartynumber": "String",
    "mshr_status": Int,
    "mshr_description": "String",
    "mshr_recruitingrequestlocationid": "String",
    "mshr_comments": "String",
    "mshr_jobid": "String",
    "mshr_titleid": "String",
    "mshr_jobfunctionid": "String",
    "mshr_defaultfulltimeequivalency": Decimal,
    "mshr_regulatoryjobcategory": Int,
    "mshr_jobtypeid": "String",
    "mshr_exemptstatus": Int,
    "mshr_estimatedstartdate": "Date",
    "mshr_externaldescription": "String",
    "mshr_compensationlevelid": "String",
    "mshr_compensationlowthreshold": Decimal,
    "mshr_compensationcontrolpoint": Decimal,
    "mshr_compensationhighthreshold": Decimal,
    "mshr_dataareaid": "String",
    "_mshr_dataareaid_id_value": "Guid",
    "_mshr_fk_hiringmanager_id_value": "Guid",
    "_mshr_fk_recruiter_id_value": "Guid",
    "_mshr_fk_job_id_value": "Guid",
    "_mshr_fk_title_id_value": "Guid",
    "_mshr_fk_jobtype_id_value": "Guid",
    "_mshr_fk_compensationlevel_id_value": "Guid",
    "mshr_hcmrecruitingrequestentityid": "Guid",
    "_mshr_fk_recruitingrequestlocation_id_value": “Guid”
}
```

### <a name="properties"></a>Proprietà

| Proprietà<br>**Nome fisico**<br>**_Tipo_** | Utilizza | Descrizione |
| --- | --- | --- |
| **ID richiesta di selezione**<br>mshr_recruitingrequestid<br>*String* | Sola lettura<br>Richiesto<br>Generato dal sistema | Un identificatore univoco leggibile dall'utente per la richiesta visualizzata nell'applicazione HR. Sequenza numerica. |
| **ID entità richiesta di selezione**<br>mshr_hcmrecruitingrequestentityid<br>*GUID* | Sola lettura<br>Richiesto<br>Generato dal sistema | Un valore GUID generato dal sistema per identificare in modo univoco la richiesta di selezione. |
| **ID area dati**<br>mshr_dataareaid<br>*String* | Lettura/scrittura<br>Facoltativo<br> | Specifica la persona giuridica (società) per la richiesta di selezione. |
| **Valore ID area dati**<br>_mshr_dataareaid_id_value<br>*GUID*<br> | Sola lettura<br>Facoltativo<br>Chiave esterna: cdm_companyid dell'entità cdm_company | Valore GUID generato dal sistema che identifica la persona giuridica (società) per la richiesta di selezione. |
| **Numero dipendente responsabile assunzioni**<br>mshr_hiringmanagerpersonnelnumber<br>*String* | Lettura/scrittura<br>Facoltativo | Il numero di dipendente del responsabile delle assunzioni associato a questa richiesta di selezione. |
| **Valore ID responsabile delle assunzioni**<br>_mshr_fk_hiringmanager_id_value<br>*GUID* | Sola lettura<br>Facoltativo<br>Chiave esterna: mshr_hcmworkerbaseentityid dell'entità mshr_hcmworkerbaseentity | Valore GUID generato dal sistema per identificare il manager associato alla richiesta di selezione. |
| **Numero parte selezionatore**<br>mshr_recruiterpartynumber<br>*String* | Lettura/scrittura<br>Facoltativo | Il numero della persona (parte) del reclutatore selezionato per la richiesta. |
| **Valore ID reclutatore**<br>_mshr_fk_recruiter_id_value<br>*GUID* | Sola lettura<br>Facoltativo<br>Chiave esterna: mshr_dirpersonentityid dell'entità mshr_dirpersonentity | Valore GUID generato dal sistema per identificare il selezionatore associato alla richiesta di selezione. |
| **Stato**<br>mshr_status<br>Set di opzioni *RecruitingRequestStatus* | Lettura/scrittura<br>Richiesto<br> | Indica lo stato della richiesta di selezione. |
| **Descrizione**<br>mshr_description<br>*String* | Lettura/scrittura<br>Richiesto | Descrive la richiesta. |
| **ID percorso richieste di selezione**<br>mshr_recruitingrequestlocationid<br>*String* | Lettura/scrittura<br>Facoltativo | L'identificatore univoco leggibile dall'utente dell'ubicazione del lavoro associato a questa richiesta. |
| **Valore ID posizione selezione**<br>_mshr_fk_recruitinglocation_id_value<br>*GUID* | Sola lettura<br>Facoltativo<br>Chiave esterna: mshr_hcmrecruitingrequestlocationentityid dell'entità mshr_hcmrecruitingrequestlocationentity | Valore GUID generato dal sistema per identificare la posizione della richiesta di selezione selezionata per la richiesta. |
| **Commenti**<br>mshr_comments<br>*String* | Lettura/scrittura<br>Facoltativo | Commenti sulla richiesta di utilizzo da parte di responsabili delle assunzioni e reclutatori. |
| **ID lavoro**<br>mshr_jobid<br>*String* | Scrivi una volta<br>Richiesto |   L'identificatore univoco leggibile dall'utente del lavoro condiviso da tutte le posizioni associate a questa richiesta. |
| **Valore ID lavoro**<br>_mshr_fk_job_id_value<br>*GUID* | Sola lettura<br>Richiesto<br>Chiave esterna: mshr_hcmjobentityid dell'entità mshr_hcmjobentity | L'identificatore univoco generato dal sistema del lavoro condiviso da tutte le posizioni associate a questa richiesta di selezione. |
| **ID titolo**<br>mshr_titleid<br>*String* | Sola lettura<br>Richiesto | L'identificatore univoco leggibile dall'utente della posizione associata a questa richiesta. |
| **Valore ID titolo**<br>_mshr_fk_title_id_value<br>*GUID* | Sola lettura<br>Richiesto<br>Chiave esterna: mshr_hcmtitleid dell'entità mshr_hcmtitleentity | L'identificatore univoco generato dal sistema del titolo del lavoro selezionato per la richiesta di selezione. |
| **ID funzione lavorativa**<br>mshr_jobfunctionid<br>*String* | Sola lettura<br>Richiesto<br>Chiave esterna: mshr_jobfunctionid dell'entità mshr_hcmjobfunctionentity | L'identificatore univoco leggibile dall'utente della funzione lavorativa associato a questa richiesta. |
| **Equivalenza a tempo pieno predefinita**<br>mshr_defaultfulltimeequivalency<br>*Double* | Sola lettura<br>Richiesto | Il valore equivalente a tempo pieno per il lavoro, dove 1.0 rappresenta un lavoratore a tempo pieno. |
| **Categoria di lavoro normativa**<br>mshr_regulatoryjobcategory<br>Set di opzioni *RegulatoryJobCategory* | Sola lettura<br>Facoltativo | La categoria di lavoro EEO della funzione lavorativa selezionata per il lavoro. Valori validi inclusi nel set di opzioni HcmRegulatoryJobCatetory (mshr_hcmregulatoryjobcategory). |
| **ID tipo di posizione**<br>mshr_jobtypeid<br>*String* | Sola lettura<br>Facoltativo | Il tipo di mansione associata alla posizione. I tipi di lavoro sono valori definiti dall'utente, disponibili nell'entità mshr_hcmjobtypeentity. |
| **Valore ID tipo lavoro**<br>_mshr_fk_jobtype_id_value<br>*GUID* | Sola lettura<br>Facoltativo<br>Chiave esterna: mshr_hcmjobtypeentityid dell'entità mshr_hcmjobtypenentity | L'identificatore univoco generato dal sistema del tipo di lavoro associato al processo per la richiesta di selezione. |
| **Stato esenzione**<br>mshr_exemptstatus<br>Set di opzioni *JobExemptStatus* | Sola lettura<br>Facoltativo | Lo stato di esenzione FLSA in base al tipo di lavoro. |
| **La data di inizio stimata**<br>mshr_estimatedstartdate<br>*Data* | Lettura/scrittura<br>Richiesto | La data stimata in cui un candidato inizierà a lavorare. |
| **Descrizione esterna**<br>mshr_externaldescription<br>*String* | Lettura/scrittura<br>Facoltativo | Una descrizione dei candidati del lavoro/posizione. | 
| **Soglia bassa di retribuzione**<br>mshr_compensationlowthreshold<br>*Double* | Lettura/scrittura<br>Facoltativo | Limite inferiore per il livello di retribuzione. |
| **Punto di controllo della retribuzione**<br>mshr_compensationcontrolpoint<br>*Double* | Lettura/scrittura<br>Facoltativo | Punto di controllo per il livello di retribuzione. |
| **Soglia alta di retribuzione**<br>mshr_compensationhighthreshold<br>*Double* | Lettura/scrittura<br>Facoltativo | Limite superiore per il livello di retribuzione. |
| **Livello retributivo**<br>mshr_compensationlevelid<br>*String* | Lettura/scrittura<br>Facoltativo | Il livello di retribuzione del lavoro. Un lavoro può essere impostato con più livelli di retribuzione. Questo attributo indica il livello di retribuzione del lavoro selezionato per questa richiesta. |
| **ID retribuzione lavoro**<br>_mshr_fk_jobcompensation_id_value<br>*GUID* | Sola lettura<br>Facoltativo<br>Chiave esterna: mshr_hcmjobcompensationentityid dell'entità mshr_hcmjobcompensationentity | L'identificatore univoco generato dal sistema per il livello di retribuzione associato al lavoro della richiesta di selezione. |

## <a name="see-also"></a>Vedere anche

[Introduzione all'API di integrazione del sistema di tracciabilità dei candidati](hr-admin-integration-ats-api-introduction.md)<br>
[Query di esempio per la richiesta di selezione](hr-admin-integration-ats-api-recruiting-request-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
