---
title: Posizione richieste di selezione
description: Questo argomento descrive l'entità Posizione richiesta di selezione per Dynamics 365 Human Resources.
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
ms.openlocfilehash: cd19cce4b3e1d057585de3368076a5e7b913e50d
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5805204"
---
# <a name="recruiting-request-position"></a>Posizione richieste di selezione

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Questo argomento descrive l'entità Posizione richiesta di selezione per Dynamics 365 Human Resources.

Nome fisico: mshr_hcmrecruitingrequestpositionentity

### <a name="description"></a>Descrizione

Descrive la posizione o le posizioni da coprire per una richiesta di selezione. L'aggiunta di una posizione alla richiesta di selezione è facoltativa. Le proprietà della posizione sono di sola lettura, poiché le proprietà della posizione non dovrebbero essere diverse sulla richiesta di selezione rispetto a quelle del record anagrafico della posizione. Se le proprietà devono cambiare, dovrebbe essere fatto sul record anagrafico della posizione prima di aggiungere la posizione alla richiesta di reclutamento.

### <a name="json-representation"></a>Rappresentazione JSON
```json
{
    "mshr_recruitingrequestid": "String",
    "mshr_positionid": "String",
    "mshr_description": "String",
    "mshr_positiontypeid": "String",
    "mshr_status": Int,
    "mshr_departmentnumber": "String",
    "mshr_reportstopositionid": "String",
    "mshr_reportstopersonnelnumber": "String",
    "mshr_financialdimension": "String",
    "mshr_dataareaid": "String",
    "_mshr_dataareaid_id_value": "Guid",
    "mshr_primaryfield": "String",
    "_mshr_fk_recruitingrequest_id_value": "Guid",
    "_mshr_fk_position_id_value": "Guid",
    "_mshr_fk_positiontype_id_value": "Guid",
    "_mshr_fk_department_id_value": "Guid",
    "_mshr_fk_reportstoposition_id_value": "Guid",
    "_mshr_fk_reportstoworker_id_value": "Guid",
    "mshr_hcmrecruitingrequestpositionentityid": "Guid"
}
```

### <a name="properties"></a>Proprietà

| Proprietà<br>**Nome fisico**<br>**_Tipo_** | Utilizza | Descrizione |
| --- | --- | --- |
| **ID entità posizione richiesta di selezione**<br>mshr_hcmrecruitingrequestpositionentityid<br>*GUID* | Sola lettura<br>Richiesto |    L'identificatore univoco generato dall'utente del record della posizione della richiesta di selezione. |
| **ID richiesta di selezione**<br>mshr_recruitingrequestid<br>*String* | Scrivi una volta<br>Richiesto | L'identificatore univoco leggibile dall'utente della richiesta di selezione. |
| **Valore ID richiesta di selezione**<br>_mshr_fk_recruitingrequest_id_value<br>*GUID* | Sola lettura<br>Richiesto<br>Chiave esterna: mshr_hcmrecruitingrequestentityid dell'entità mshr_hcmrecruitingrequestentity | L'identificatore generato dal sistema della richiesta di selezione alla quale la posizione è assegnata. |
| **ID posizione**<br>mshr_positionid<br>*String* | Scrivi una volta<br>Richiesto | L'identificatore univoco leggibile dall'utente della posizione. |
| **Valore ID posizione**<br>_mshr_fk_position_id_value<br>*GUID* | Sola lettura<br>Richiesto<br>Chiave esterna: mshr_hcmpositionv2entityid di mshr_hcmpositionv2entity entity | Identificatore generato dal sistema della posizione. |
| **Descrizione**<br>mshr_description<br>*String* | Sola lettura<br>Richiesto | La descrizione della posizione. |
| **ID tipo di posizione**<br>mshr_positiontypeid<br>*String* | Sola lettura<br>Facoltativo | L'identificatore univoco leggibile dall'utente dal tipo di posizione per questa posizione. |
| **Valore ID tipo posizione**<br>_mshr_fk_positiontype_id_value<br>*GUID* | Sola lettura<br>Facoltativo<br>Chiave esterna: mshr_hcmpositiontypeentityid dell'entità mshr_hcmpositiontypeentity | L'identificatore univoco generato dal sistema del tipo di posizione per questa posizione. |
| **Stato**<br>mshr_status<br>Set di opzioni *RecruitingRequestPositionStatus* | Lettura/scrittura<br>Richiesto | Stato della posizione per la richiesta di selezione. |
| **Numero reparto**<br>mshr_departmentnumber<br>*String* | Sola lettura<br>Facoltativo<br> | Il numero del reparto della posizione. |
| **Valore ID reparto**<br>_mshr_fk_department_id_value<br>*GUID* | Sola lettura<br>Facoltativo<br>Chiave esterna: mshr_omdepartmententityid dell'entità mshr_omdepartmententity | L'identificatore univoco generato dal sistema del reparto della posizione. |
| **Subordinato a ID posizione**<br>mshr_reportstopositionid<br>*String* | Sola lettura<br>Richiesto | L'ID leggibile dall'utente della posizione alla quale la posizione reclutata riferisce nella gerarchia organizzativa. |
| **Subordinato a valore ID posizione**<br>_mshr_fk_reportstoposition_id_value<br>*GUID* | Sola lettura<br>Richiesto<br>Chiave esterna: mshr_hcmpositionv2entityid di mshr_hcmpositionv2entity entity | L'ID generato dal sistema della posizione a cui riferisce la posizione reclutata. |
| **Subordinato a numero dipendente**<br>mshr_reportstopersonnelnumber<br>*String* | Sola lettura<br>Richiesto | L'ID lavoratore del lavoratore a cui riferirà il candidato assunto. |
| **Subordinato a valore ID lavoratore**<br>_mshr_fk_reportstoworker_id_value<br>*GUID* | Sola lettura<br>Richiesto<br>Chiave esterna: mshr_hcmworkerbaseentityid dell'entità mshr_hcmworkerbaseentity | L'ID generato dal sistema del lavoratore a cui riferirà il candidato assunto. |
| **Dimensione finanziaria**<br>mshr_financialdimension<br>*String* | Sola lettura<br>Facoltativo | La dimensione finanziaria (ad esempio, centro di costo) assegnata alla posizione. La dimensione finanziaria viene assegnata a ciascuna posizione per persona giuridica. I centri di costo definiti nelle dimensioni sono accessibili tramite l'entità mshr_dimattributeomcostcenterentity. |
| **ID area dati**<br>mshr_dataareaid<br>*String* | Lettura/scrittura<br>Facoltativo | Specifica la persona giuridica (società) per la posizione della richiesta di selezione. |
| **Valore ID area dati**<br>_mshr_dataareaid_id_value<br>*GUID* | Sola lettura<br>Facoltativo<br>Chiave esterna: cdm_companyid dell'entità cdm_company | Valore GUID generato dal sistema che identifica la persona giuridica (società) per la posizione della richiesta di selezione. |
| **Campo principale**<br>mshr_primaryfield<br>*String* | Sola lettura<br>Richiesto | Concatenazione del valore della richiesta di selezione, dell'ID della posizione come altro metodo per identificare in modo univoco il record. |

## <a name="see-also"></a>Vedere anche

[Introduzione all'API di integrazione del sistema di tracciabilità dei candidati](hr-admin-integration-ats-api-introduction.md)<br>
[Query di esempio per la richiesta di selezione](hr-admin-integration-ats-api-recruiting-request-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]