---
title: Percorso richieste di selezione
description: Questo argomento descrive l'entità Posizione richiesta di selezione per Dynamics 365 Human Resources.
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
ms.openlocfilehash: fa153b1cfcbb70294ed6da3618c83396df04f8db
ms.sourcegitcommit: 33b5c8bc4f9461e290513aa22de1ec1fba3b0742
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/05/2021
ms.locfileid: "5125235"
---
# <a name="recruiting-request-location"></a>Percorso richieste di selezione

Questo argomento descrive l'entità Posizione richiesta di selezione per Dynamics 365 Human Resources.

Nome fisico: mshr_hcmrecruitingrequestlocationentity

### <a name="description"></a>descrizione

L'elenco delle posizioni definite come posizioni in cui i dipendenti reclutati lavoreranno al momento dell'assunzione. Queste sono posizioni create da persone giuridiche.

### <a name="json-representation"></a>Rappresentazione JSON

```
{
    "mshr_recruitingrequestlocationid": "String",
    "mshr_locationid": "String",
    "mshr_description": "String",
    "mshr_countryregionid": "String",
    "mshr_zipcode": "String",
    "mshr_street": "String",
    "mshr_city": "String",
    "mshr_state": "String",
    "mshr_county": "String",
    "mshr_telephone": "String",
    "mshr_email": "String",
    "mshr_internetaddress": "String",
    "_mshr_dataareaid_id_value": "Guid",
    "mshr_dataareaid": "String",
    "_mshr_fk_countryregion_id_value": "Guid",
    "mshr_hcmrecruitingrequestlocationentityid": "Guid"
}
```

### <a name="properties"></a>Proprietà

| Proprietà<br>**Nome fisico**<br>**_Tipo_** | Utilizza | descrizione |
| --- | --- | --- |
| **ID ubicazione**<br>mshr_locationid<br>*String* | Scrivi una volta<br>Richiesto | L'identificatore generato dal sistema, leggibile dall'utente per la posizione di selezione. |
| **Percorso richieste di selezione**<br>mshr_recruitingrequestlocationid<br>*String* | Scrivi una volta<br>Richiesto | Identificatore univoco definito dall'utente per la posizione di selezione. |
| **ID entità posizione richiesta di selezione**<br>mshr_hcmrecruitingrequestlocationentityid<br>*GUID* | Sola lettura<br>Richiesto | Identificatore univoco generato dal sistema per il record della posizione della richiesta di selezione. |
| **Descrizione**<br>mshr_description<br>*String* | Lettura/scrittura<br>Richiesto | Descrizione dell'ubicazione. |
| **ID paese/area geografica**<br>mshr_countryregionid<br>*String* | Sola lettura<br>Facoltativo | Specifica il paese o l'area geografica in cui il candidato ha la cittadinanza. |
| **Valore ID paese/area geografica**<br>_mshr_fk_countriregion_id_value<br>*GUID* | Sola lettura<br>Facoltativo<br>Chiave esterna: mshr_logisticaddresscountryregionentityid di mshr_logisticsaddresscountryregionentity | Identificatore univoco generato dal sistema del paese/area geografica dell'indirizzo. |
| **ZipCode**<br>mshr_zipcode<br>*String* | Sola lettura<br>Facoltativo | CAP/Codice postale. |
| **Via**<br>mshr_street<br>*String* | Sola lettura<br>Facoltativo | Indirizzo via. |
| **Città**<br>mshr_city<br>*String* | Sola lettura<br>Facoltativo | Città. |
| **Stato/regione**<br>mshr_state<br>*String* | Sola lettura<br>Facoltativo | Stato o provincia. |
| **Regione**<br>mshr_county<br>*String* | Sola lettura<br>Facoltativo | Regione. |
| **Telefono**<br>mshr_telephone<br>*String* | Lettura/scrittura<br>Facoltativo | Numero di telefono per la posizione. |
| **Messaggio e-mail**<br>mshr_email<br>*String* | Lettura/scrittura<br>Facoltativo | Indirizzo e-mail. |
| **Indirizzo Internet**<br>mshr_internetaddress<br>*String* | Lettura/scrittura<br>Facoltativo | URL per il sito Web della posizione. |
| **ID area dati**<br>mshr_dataareaid<br>*String* | Lettura/scrittura<br>Facoltativo | Specifica la persona giuridica (società). |
| **Valore ID area dati**<br>_mshr_dataareaid_id_value<br>*GUID* | Sola lettura<br>Facoltativo<br>Chiave esterna: cdm_companyid dell'entità cdm_company | Valore GUID generato dal sistema che identifica la persona giuridica (società). |

## <a name="see-also"></a>Vedere anche

[Introduzione all'API di integrazione del sistema di tracciabilità dei candidati](hr-admin-integration-ats-api-introduction.md)<br>
[Query di esempio per la richiesta di selezione](hr-admin-integration-ats-api-recruiting-request-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]