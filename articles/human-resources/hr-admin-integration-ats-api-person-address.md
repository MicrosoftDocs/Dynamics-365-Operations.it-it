---
title: Indirizzo della persona
description: Questo argomento descrive l'entità Indirizzo persona per Dynamics 365 Human Resources.
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
ms.openlocfilehash: 14db209e420770234583add93fa72d086f1b5ea6
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/18/2021
ms.locfileid: "6053781"
---
# <a name="person-address"></a>Indirizzo della persona

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Questo argomento descrive l'entità Indirizzo persona per Dynamics 365 Human Resources.

Nome fisico: mshr_hcmpersonaddressentities

## <a name="description"></a>Descrizione

Questa entità contiene l'elenco degli indirizzi postali per i record dei candidati.

## <a name="json-representation"></a>Rappresentazione JSON

```json
{
    "mshr_partynumber": "String",
    "mshr_locationid": "String",
    "mshr_description": "String",
    "mshr_roles": "String",
    "mshr_countryregionid": "String",
    "mshr_zipcode": "String",
    "mshr_street": "String",
    "mshr_city": "String",
    "mshr_state": "String",
    "mshr_county": "String",
    "mshr_isprimary": Int,
    "mshr_isprivate": Int,
    "mshr_primaryfield": "String",
    "_mshr_fk_person_id_value": "Guid",
    "_mshr_fk_countryregion_id_value": "Guid",
    "mshr_hcmpersonaddressentityid": "Guid"
}
```

## <a name="properties"></a>Proprietà

| Proprietà<br>**Nome fisico**<br>**_Tipo_** | Utilizza | Descrizione |
| --- | --- | --- |
| **ID entità indirizzo persona**<br>mshr_hcmpersonaddressentityid<br>*String* | Sola lettura<br>Richiesto | Identificatore univoco generato dal sistema per il record dell'entità. |
| **Numero parte**<br>mshr_partynumber<br>*String* | Lettura/scrittura<br>Richiesto | L'ID del record della parte associata (persona). |
| **Valore ID persona**<br>_mshr_fk_person_id_value<br>*GUID* | Sola lettura<br>Richiesto<br>Chiave esterna: mshr_dirpersonentityid di mshr_dirpersonentity | L'identificatore generato dal sistema per il record dell'entità della parte (persona). |
| **ID ubicazione**<br>mshr_locationid<br>*String* | Lettura/scrittura<br>Richiesto | L'ID posizione del record dell'indirizzo. Configurazione nell'entità mshr_logisticspostaladdresslocationcdsentity. |
| **Descrizione**<br>mshr_description<br>*String* | Lettura/scrittura<br>Richiesto | Una descrizione dell'indirizzo del candidato. |
| **Ruoli**<br>mshr_roles<br>*String* | Lettura/scrittura<br>Richiesto | I ruoli assegnati per questo indirizzo. È possibile assegnare più di un ruolo. Ciascun ruolo dovrebbe essere separato da un punto e virgola. Valori validi contenuti nell'entità mshr_logisticslocationroleentity. |
| **Via**<br>mshr_street<br>*String* | Lettura/scrittura<br>Facoltativo | Il numero civico. |
| **Città**<br>mshr_city<br>*String* | Lettura/scrittura<br>Facoltativo | Città dell'indirizzo. Impostalo nell'entità mshr_logisticsaddresscityentity. |
| **Stato/regione**<br>mshr_state<br>*String* | Lettura/scrittura<br>Facoltativo | Lo stato dell'indirizzo. Impostalo nell'entità mshr_logisticsaddressstateentity. |
| **Regione**<br>mshr_county<br>*String* | Lettura/scrittura<br>Facoltativo | Regione dell'indirizzo. Impostalo nell'entità mshr_logisticsaddresscountyentity. |
| **Codice postale**<br>mshr_zipcode<br>*String* | Lettura/scrittura<br>Facoltativo | Il codice postale (CAP) dell'indirizzo. Impostalo nell'entità mshr_logisticsaddresspostalcodeentity. |
| **ID paese/area geografica**<br>mshr_countryregionid<br>*String* | Lettura/scrittura<br>Facoltativo | Paese dell'indirizzo. |
| **Valore ID paese/area geografica**<br>_mshr_fk_countriregion_id_value<br>*GUID* | Sola lettura<br>Facoltativo<br>Chiave esterna: mshr_logisticaddresscountryregionentityid di mshr_logisticsaddresscountryregionentity | Identificatore univoco generato dal sistema del paese/area geografica dell'indirizzo. |
| **Primario**<br>mshr_isprimary<br>*set di opzioni mshr_noyes* | Lettura/scrittura<br>Richiesto | Identifica se questo indirizzo è l'indirizzo principale per la persona del ruolo definito. |
| **È privato**<br>mshr_isprivate<br>*set di opzioni mshr_noyes* | Lettura/scrittura<br>Richiesto | Identifica se questo indirizzo è un indirizzo privato per la persona. |
| **Campo principale**<br>mshr_primaryfield<br>*String* | Sola lettura<br>Richiesto | Campo utilizzato come un identificatore principale del record dell'entità. Combinazione di numero parte e ID posizione. |

## <a name="see-also"></a>Vedere anche

[Introduzione all'API di integrazione del sistema di tracciabilità dei candidati](hr-admin-integration-ats-api-introduction.md)<br>
[Query di esempio per il candidato da assumere](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]