---
title: Richiesta di congedo
description: Questo argomento fornisce dettagli e una query di esempio per l'entità Richiesta di congedo in Dynamics 365 Human Resources.
author: marcelbf
ms.date: 06/25/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-06-25
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: c6c772c26e8a789a54c9eeb36c1cab576a7f94cb3ede547db46fe18a2e89c8ce
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6762024"
---
# <a name="leave-request"></a>Richiesta di congedo

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Questo argomento descrive l'entità Richiesta di congedo per Dynamics 365 Human Resources.

### <a name="description"></a>descrizione

Questa entità fornisce informazioni per una richiesta di congedo.

Nome fisico: mshr_essleaverequestentity.

## <a name="properties"></a>Proprietà

| Proprietà</br>**Nome fisico**</br>**_Tipo_** | Utilizza | descrizione |
| --- | --- | --- |
| **ID richiesta**</br>mshr_requestid</br>*String* | Sola lettura | ID richiesta. |
| **ID tipo di congedo**</br>mshr_leavetypeid</br>*String* | Sola lettura | ID tipo di congedo. |
| **Data**</br>mshr_leavedate</br>*Offset data/ora* | Sola lettura | Data della richiesta di congedo. |
| **Importo**</br>mshr_amount</br>*Decimali* | Sola lettura | Quantità richiesta di congedo. |
| **Tipo mezza giornata**</br>mshr_halfdaydefinition</br>*Set di opzioni mshr_LeaveHalfDayDefinition* | Sola lettura | Il tipo di congedo di mezza giornata. |
| **Commento**</br>mshr_comment</br>*String* | Sola lettura | Commento per la richiesta. |
| **Stato**</br>mshr_status</br>*set di opzioni mshr_status* | Sola lettura | Stato della richiesta. |
| **Data**</br>mshr_requestdate</br>*Offset data/ora* | Sola lettura | Data della richiesta. |
| **Numero dipendente**</br>mshr_personnelnumber</br>*String* | Sola lettura | Il numero personale univoco del dipendente. |
| **ID codice motivo**</br>mshr_reasoncodeid</br>*String* | Sola lettura | ID codice motivo. |
| **ID area dati**</br>mshr_dataareaid</br>*String* | Sola lettura | Specifica la persona giuridica (società). |
| **Campo principale**</br>mshr_primaryfield</br>*GUID* | Sola lettura</br>Generato dal sistema | |
| **Entità tipo di congedo**</br>mshr_essleaverequestentityid</br>*GUID* | Generato dal sistema | Un valore GUID generato dal sistema per identificare in modo univoco la richiesta di congedo. |

## <a name="example-query"></a>Query di esempio

**Richiesta**

```http
GET [Organizaton URI]/api/data/v9.1/mshr_essleaverequestentities?$filter=mshr_personnelnumber eq '000020'
```

**Risposta**

```json
{
    "mshr_requestid": "USMF-000001",
    "mshr_leavetype": "PTO",
    "mshr_leavedate": "2017-01-02T00:00:00Z",
    "mshr_amount": 8,
    "mshr_halfdaydefinition": 200000000,
    "mshr_comment": "Taking a week off to relax",
    "mshr_status": 200000009,
    "mshr_requestdate": "2017-07-31T00:00:00Z",
    "mshr_personnelnumber": "000020",
    "mshr_reasoncodeid": "",
    "mshr_dataareaid": "usmf",
    "mshr_primaryfield": "USMF-000001 | PTO | 1/2/2017",
    "mshr_essleaverequestentityid": "000004dd-0000-0000-0f00-005001000000",
    "_mshr_dataareaid_id_value": null
}
```

## <a name="see-also"></a>Vedere anche

[Introduzione all'API di integrazione retribuzioni](hr-admin-integration-payroll-api-introduction.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
