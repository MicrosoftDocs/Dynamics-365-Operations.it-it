---
title: Numero di identificazione persona
description: Questo argomento descrive l'entità Numero di identificazione persona per Dynamics 365 Human Resources.
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
ms.openlocfilehash: 0991f5b2e17e64e23f78b346c451f7c43bc20378
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/31/2022
ms.locfileid: "8067153"
---
# <a name="person-identification-number"></a>Numero di identificazione persona


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Questo argomento descrive l'entità Numero di identificazione persona per Dynamics 365 Human Resources.

Nome fisico: mshr_hcmpersonidentificationnumberentity

## <a name="description"></a>Descrizione

Questa entità descrive i numeri di identificazione per il candidato. Consente al consumatore API di scrivere numeri di identificazione, come numeri di previdenza sociale o numeri di passaporto, nel record del candidato. I numeri di identificazione sono riportati sul record del lavoratore, ma non sul record del candidato. Un'applicazione di integrazione può scrivere i valori nel database di Human Resources, ma i numeri non saranno visibili in Human Resources finché non viene creato il record del lavoratore del candidato.

## <a name="json-representation"></a>Rappresentazione JSON

```json
{
    "mshr_entrytype": "String",
    "mshr_description": "String",
    "mshr_expirationdate": "Datetime",
    "mshr_isprimary": Int,
    "mshr_identificationnumber": "String",
    "mshr_partynumber": "String",
    "mshr_identificationtypeid": "String",
    "mshr_issuingagencyid": "String",
    "mshr_primaryfield": "String",
    "_mshr_fk_person_id_value": "Guid",
    "_mshr_fk_issuingagency_id_value": "Guid",
    "_mshr_fk_identificationtype_id_value": "Guid",
    "mshr_hcmpersonidentificationnumberentityid": "Guid",
    "mshr_issueddate": "Datetime"
}
```

## <a name="properties"></a>Proprietà

| Proprietà<br>**Nome fisico**<br>**_Tipo_** | Utilizza | Descrizione |
| --- | --- | --- |
| **ID entità numero di identificazione persona**<br>mshr_hcmpersonidentificationnumberentityid<br>*GUID* | Sola lettura<br>Richiesto<br>Generato dal sistema | Identificatore primario univoco per il record del numero di identificazione della persona. |
| **Tipo di voce**<br>mshr_entrytype<br>*String* | Lettura/scrittura<br>Facoltativo | Valore libero per fare riferimento al tipo di voce per il numero di identificazione. |
| **Descrizione**<br>mshr_description<br>*String* | Lettura/scrittura<br>Facoltativo | Descrizione del numero di identificazione. |
| **Data di scadenza**<br>mshr_expirationdate<br>*Datetime* | Lettura/scrittura<br>Facoltativo | La data di scadenza del numero di identificazione o del documento associato. |
| **Primario**<br>mshr_isprimary<br>*set di opzioni mshr_noyes* | Lettura/scrittura<br>Facoltativo | Definisce se il numero di identificazione è il record principale della persona per questo tipo di identificazione. |
| **Numero di identificazione**<br>mshr_identificationnumber<br>*String* | Lettura/scrittura<br>Richiesto | Numero di identificazione. |
| **Numero parte**<br>mshr_partynumber<br>*String* | Lettura/scrittura<br>Richiesto | L'identificatore della parte (persona) che possiede il numero di identificazione. |
| **Valore ID persona**<br>_mshr_fk_person_id_value<br>*GUID* | Sola lettura<br>Richiesto<br>Chiave esterna: mshr_dirpersonentityid dell'entità mshr_dirpersonentity | Identificatore univoco della parte (persona). |
| **ID tipo di identificazione**<br>mshr_identificationtypeid<br>*String* | Lettura/scrittura<br>Richiesto | Il tipo di numero di identificazione. |
| **Valore ID tipo di identificazione**<br>_mshr_fk_identificationtype_id_value<br>*GUID* | Sola lettura<br>Richiesto<br>Chiave esterna: mshr_hcmidentificationtypeentityid dell'entità mshr_hcmidentificationtypeentity | Identificatore univoco generato dal sistema del tipo di identificazione. |
| **ID agenzia emittente**<br>mshr_issuingagencyid<br>*String* | Lettura/scrittura<br>Facoltativo | L'agenzia o l'organizzazione che rilascia il numero di identificazione. |
| **Valore ID agenzia emittente**<br>_mshr_fk_issuingagency_id_value<br>*GUID* | Sola lettura<br>Facoltativo<br>Chiave esterna: mshr_hcmissuingagencyentityid dell'entità mshr_hcmissuingagencyentity | Identificatore univoco generato dal sistema dell'agenzia che ha emesso il numero di identificazione. |
| **Campo principale**<br>mshr_primaryfield<br>*String* | Sola lettura<br>Richiesto | Campo da utilizzare come un identificatore principale del record dell'entità. Combinazione di numero di parte, ID tipo di identificazione e numero di identificazione. |
| **Data di emissione**<br>mshr_issuedate<br>*Data* | Lettura/scrittura<br>Facoltativo | La data in cui è stato rilasciato il numero di identificazione. |

## <a name="see-also"></a>Vedere anche

[Introduzione all'API di integrazione del sistema di tracciabilità dei candidati](hr-admin-integration-ats-api-introduction.md)<br>
[Query di esempio per il candidato da assumere](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
