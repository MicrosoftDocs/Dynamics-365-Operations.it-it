---
title: Candidato da assumere
description: Questo argomento descrive il candidato all'assunzione dell'entità per Dynamics 365 Human Resources.
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
ms.openlocfilehash: eb16f9f46e3f5c58854ec06c3b89ec72dd7bae00
ms.sourcegitcommit: 33b5c8bc4f9461e290513aa22de1ec1fba3b0742
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/05/2021
ms.locfileid: "5125739"
---
# <a name="candidate-to-hire"></a>Candidato da assumere

Questo argomento descrive il candidato all'assunzione dell'entità per Dynamics 365 Human Resources.

Nome fisico: mshr_hcmcandidatetohireentity

## <a name="description"></a>descrizione

Questa entità fornisce i dettagli del candidato utilizzati per creare un lavoratore in Dynamics 365 Human Resources. Viene utilizzato per leggere tutti i record del candidato e creare record del candidato interno ed esterno, consentendo di creare dettagli personali per il nuovo candidato.

Quando si crea un record candidato esterno che sarà un nuovo record di persona nel sistema, non è necessario definire un numero di parte (persona) per inserire un nuovo record di candidato. Il nuovo record dell'entità persona viene creato con il nuovo record candidato.

Quando crei un record candidato interno (un candidato per la posizione che ha già un record di dipendente con l'azienda), definisci il numero della parte (persona) del record che esiste già per la persona per la proprietà mshr_partynumber sul record del candidato piuttosto che definire informazioni personali (come nome, sesso o data di nascita) che verrebbero utilizzate per creare un nuovo record di persona.

## <a name="json-representation"></a>Rappresentazione JSON

```json
        {
            "mshr_candidateid": "String",
            "mshr_partynumber": "String",
            "mshr_partytype": "String",
            "mshr_recruitingrequestid": "String",
            "mshr_positionid": "String",
            "mshr_firstname": "String",
            "mshr_middlename": "String",
            "mshr_lastnameprefix": "String",
            "mshr_lastname": "String",
            "mshr_gender": Int,
            "mshr_birthdate": "Date",
            "mshr_citizenshipcountrycode": "String",
            "mshr_veteranstatusid": "String",
            "mshr_isdisabledveteran": Int,
            "mshr_availabilitydate": "Date",
            "mshr_iswillingtorelocate": Int,
            "mshr_comments": "String",
            "mshr_applicantintegrationresult": Int,
            "mshr_donothirereasoncodeid": "String",
            "mshr_dataareaid": "String",
            "_mshr_dataareaid_id_value": "Guid",
            "_mshr_fk_person_id_value": "Guid",
            "_mshr_fk_recruitingrequest_id_value": "Guid",
            "_mshr_fk_position_id_value": "Guid",
            "mshr_hcmcandidatetohireentityid": "Guid",
            "_mshr_fk_veteranstatus_id_value": "Guid",
            "_mshr_fk_reasoncode_id_value": "Guid",
            "mshr_militaryserviceenddate": "Guid",
            "mshr_militaryservicestartdate": "Guid"
        }
```

## <a name="properties"></a>Proprietà

| Proprietà<br>**Nome fisico**<br>**_Tipo_** | Utilizza | descrizione |
| --- | --- | --- |
| **Candidato ad assumere l'ID entità**<br>mshr_hcmcandidatetohireentityid<br>GUID | Sola lettura<br>Richiesto<br>Generato dal sistema | Un identificatore univoco generato dal sistema per il record dell'entità. |
| **ID candidato**<br>mshr_candidateid<br>String | Sola lettura<br>Richiesto<br>Generato dal sistema | Identificatore univoco per l'entità. |
| **Numero parte**<br>mshr_partynumber<br>String | Sola lettura<br>Richiesto | Il numero della parte (persona) del record della persona del candidato. |
| **Valore ID persona**<br>_mshr_fk_person_id_value<br>GUID | Sola lettura<br>Richiesto<br>Chiave esterna: mshr_dirpersonentityid di mshr_direpersonentity | L'identificatore univoco generato dal sistema per il record della parte (persona) del candidato. |
| **Tipo parte**<br>mshr_partytype<br>Set di opzioni mshr_dirpartytype | Sola lettura<br>Richiesto | Il tipo di parte del record, come definito nel set di opzioni mshr_dirpartytype. Per questa entità, il tipo sarà sempre "Persona". |
| **ID richiesta di selezione**<br>mshr_recruitingrequestid<br>String | Scrivi una volta<br>Facoltativo | Riferimenti alla richiesta di selezione che questo candidato soddisfa. |
| **Valore ID richiesta di selezione**<br>_mshr_fk_recruitingrequest_id_value<br>GUID | Lettura/scrittura<br>Facoltativo<br>Chiave esterna: mshr_hcmrecruitingrequestentityid di mshr_hcmrecruitingrequestentity | L'identificatore univoco generato dal sistema della richiesta di selezione che questo candidato soddisfa. |
| **ID posizione**<br>mshr_positionid<br>String | Lettura/scrittura<br>Facoltativo | L'ID della posizione per la quale il candidato viene considerato. |
| **Valore ID posizione**<br>_mshr_fk_position_if_value<br>GUID | Sola lettura<br>Facoltativo<br>Chiave esterna: mshr_hcmpositionv2entityid di mshr_hcmpositionv2entity | Identificatore generato dal sistema della posizione per la quale il candidato viene considerato. |
| **Nome**<br>mshr_firstname<br>String | Lettura/scrittura<br>Richiesto | Nome del candidato. |
| **Secondo nome**<br>mshr_middlename<br>String | Lettura/scrittura<br>Facoltativo | Secondo nome candidato. |
| **Prefisso cognome**<br>mshr_lastnameprefix<br>String | Lettura/scrittura<br>Facoltativo | Prefisso cognome candidato. |
| **Cognome**<br>mshr_lastname<br>String | Lettura/scrittura<br>Facoltativo | Cognome del candidato. |
| **Genere**<br>mshr_gender<br>set di opzioni mshr_hcmpersongender | Lettura/scrittura<br>Facoltativo | Il sesso del candidato. |
| **Data di nascita**<br>mshr_birthdate<br>Data/Ora | Lettura/scrittura<br>Facoltativo | La data di nascita del candidato. |
| **Codice paese cittadinanza**<br>mshr_citizenshipcountrycode<br>String | Lettura/scrittura<br>Facoltativo | Specifica il paese in cui il candidato ha la cittadinanza. I codici paese validi sono in mshr_logisticaddresscountryregionentity. |
| **ID stato veterano**<br>mshr_veteranstatusid<br>String | Lettura/scrittura<br>Facoltativo | Indica lo stato veterano del candidato. |
| **Valore ID stato veterano**<br>_mshr_fk_veteranstatus_id_value<br>GUID | Sola lettura<br>Facoltativo<br>Chiave esterna: mshr_hcmveteranstatusentityid di mshr_hcmveteranstatusentity | Identificatore univoco generato dal sistema per il record dell'entità dello stato veterano. |
| **Data di inizio servizio militare**<br>mshr_militaryservicestartdate<br>Data/Ora | Lettura/scrittura<br>Facoltativo | La data di inizio del servizio militare del candidato. |
| **Data di fine servizio militare**<br>mshr_militaryserviceenddate<br>Data/Ora | Lettura/scrittura<br>Facoltativo | La data di fine del servizio militare del candidato. |
| **Veterano disabile**<br>mshr_isdisabledveteran<br>set di opzioni mshr_noyes | Lettura/scrittura<br>Facoltativo | Indica se il candidato ha disabilitato lo stato veterano. |
| **Data disponibilità**<br>mshr_availabilitydate<br>Data/Ora | Lettura/scrittura<br>Facoltativo | La prima data in cui il candidato sarà disponibile per lavorare. |
| **È disposto al trasferimento**<br>mshr_iswillingtorelocate<br>set di opzioni mshr_noyes | Lettura/scrittura<br>Facoltativo | Indica se il candidato è disposto a trasferirsi per la posizione. |
| **Commenti**<br>mshr_comments<br>String | Lettura/scrittura<br>Facoltativo | Commenti che devono essere utilizzati dal reclutatore o dal responsabile delle assunzioni. |
| **Risultato integrazione applicazione**<br>mshr_applcantintegrationresult<br>Set di opzioni mshr_applicantintegrationresult | Lettura/scrittura<br>Richiesto | Lo stato del candidato nel processo di assunzione relativo all'integrazione. |
| **ID codice motivo Non assumere**<br>mshr_donothirereasoncodeid<br>String | Lettura/scrittura<br>Facoltativo | Un codice motivo facoltativamente fornito quando lo stato (risultato dell'integrazione dell'applicazione) è impostato su "Non assunto". |
| **Valore ID codice motivo**<br>_mshr_fk_reasoncode_id_value<br>GUID | Sola lettura<br>Facoltativo<br>Chiave esterna: mshr_hcmreasoncodeentityid dell'entità mshr_hcmreasoncodeentity | Identificatore univoco generato dal sistema per codice motivo **Non assumere**. |
| **ID area dati**<br>mshr_dataareaid<br>String | Lettura/scrittura<br>Facoltativo |  Specifica la persona giuridica (società). |
| **Valore ID area dati**<br>_mshr_dataareaid_id_value<br>GUID | Sola lettura<br>Facoltativo<br>Chiave esterna: cdm_companyid dell'entità cdm_company | Valore GUID generato dal sistema che identifica la persona giuridica (società). |

## <a name="see-also"></a>Vedere anche

[Introduzione all'API di integrazione del sistema di tracciabilità dei candidati](hr-admin-integration-ats-api-introduction.md)<br>
[Query di esempio per il candidato da assumere](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]