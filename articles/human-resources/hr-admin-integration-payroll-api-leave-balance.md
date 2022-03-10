---
title: Saldo di congedo
description: Questo argomento fornisce dettagli e una query di esempio per l'entità Saldo di congedo in Dynamics 365 Human Resources.
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
ms.openlocfilehash: 7d26d9624ae8d99b208f77d12137262983499c51
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/31/2022
ms.locfileid: "8064818"
---
# <a name="leave-balance"></a>Saldo di congedo


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Questo argomento descrive l'entità Saldo di congedo per Dynamics 365 Human Resources.

### <a name="description"></a>descrizione

Questa entità fornisce il saldo di congedo per tipo di congedo per un determinato dipendente.

Nome fisico: mshr_essleavebalanceentities.

## <a name="properties"></a>Proprietà

| Proprietà</br>**Nome fisico**</br>**_Tipo_** | Utilizza | descrizione |
| --- | --- | --- |
| **Numero dipendente**</br>mshr_personnelnumber</br>*String* | Sola lettura | Il numero personale univoco del dipendente. |
| **Saldo corrente**</br>mshr_balanceavailable</br>*Decimali* | Sola lettura | Saldo corrente del dipendente. |
| **Tipo**</br>mshr_balanceavailable</br>*String* | Sola lettura | ID tipo di congedo. |
| **Coefficiente di accumulo**</br>mshr_accrualratedescription</br> | Sola lettura | Coefficiente di accumulo. |
| **Ultimo importo riportabile in avanti**</br>mshr_lastcarryforwardamount</br>*Decimali* | Sola lettura | Ultimo riporto. |
| **Acquisito quest'anno**</br>mshr_takenthisyear</br>*Decimali* | Sola lettura | Tutti i congedi presi quest'anno. |
| **Totale anno in corso**</br>mshr_totalthisyear</br>*Decimali* | Sola lettura | Importo totale per quest'anno. |
| **ID area dati**</br>mshr_dataareaid_id</br>*String* | Sola lettura | Specifica la persona giuridica (società). |
| **Campo principale**</br>mshr_primaryfield</br>*GUID* | Sola lettura</br>Generato dal sistema | |
| **ID tipo di congedo**</br>_mshr_fk_leavetype_id_value</br>*GUID* | Sola lettura</br>Chiave esterna: mshr_essleavetypeentityid of mshr_essleavetypeentity entity  | ID tipo di congedo |
| **Entità saldo di congedo**</br>mshr_essleavebalanceentityid</br>*GUID* | Generato dal sistema | Un valore GUID generato dal sistema per identificare in modo univoco il saldo. |

## <a name="example-query"></a>Query di esempio

**Richiesta**

```http
GET [Organizaton URI]/api/data/v9.1/mshr_essleavebalanceentities?$filter=mshr_personnelnumber eq '000013'
```

**Risposta**

```json
{
    "mshr_personnelnumber": "000013",
    "mshr_balanceavailable": 67.76,
    "mshr_leavetypeid": "PTO",
    "mshr_accrualratedescription": "6.16 hrs / Semimonthly",
    "mshr_lastcarryforwardamount": 0,
    "mshr_takenthisyear": 0,
    "mshr_totalthisyear": 67.76,
    "mshr_dataareaid": "usmf",
    "mshr_primaryfield": "000013 | PTO",
    "_mshr_fk_leavetype_id_value": "00000a6c-0000-0000-0000-005001000000",
    "mshr_essleavebalanceentityid": "0000091f-0000-0000-2703-005001000000",
    "_mshr_dataareaid_id_value": null
},
{
    "mshr_personnelnumber": "000013",
    "mshr_balanceavailable": 80,
    "mshr_leavetypeid": "Sick",
    "mshr_accrualratedescription": "80.00 hrs / Annually",
    "mshr_lastcarryforwardamount": 0,
    "mshr_takenthisyear": 0,
    "mshr_totalthisyear": 80,
    "mshr_dataareaid": "usmf",
    "mshr_primaryfield": "000013 | Sick",
    "_mshr_fk_leavetype_id_value": "00000a6c-0000-0000-ee02-005001000000",
    "mshr_essleavebalanceentityid": "0000091f-0000-0000-3003-005001000000",
    "_mshr_dataareaid_id_value": null
},
{
    "mshr_personnelnumber": "000013",
    "mshr_balanceavailable": 0,
    "mshr_leavetypeid": "Bereavement",
    "mshr_accrualratedescription": "0.00 hrs / Annually",
    "mshr_lastcarryforwardamount": 0,
    "mshr_takenthisyear": 0,
    "mshr_totalthisyear": 0,
    "mshr_dataareaid": "usmf",
    "mshr_primaryfield": "000013 | Bereavement",
    "_mshr_fk_leavetype_id_value": "00000a6c-0000-0000-f402-005001000000",
    "mshr_essleavebalanceentityid": "0000091f-0000-0000-4403-005001000000",
    "_mshr_dataareaid_id_value": null
},
{
    "mshr_personnelnumber": "000013",
    "mshr_balanceavailable": 66.65,
    "mshr_leavetypeid": "Vacation",
    "mshr_accrualratedescription": "13.33 hrs / Monthly",
    "mshr_lastcarryforwardamount": 0,
    "mshr_takenthisyear": 0,
    "mshr_totalthisyear": 66.65,
    "mshr_dataareaid": "usmf",
    "mshr_primaryfield": "000013 | Vacation",
    "_mshr_fk_leavetype_id_value": "00000a6c-0000-0000-f502-005001000000",
    "mshr_essleavebalanceentityid": "0000091f-0000-0000-1009-005001000000",
    "_mshr_dataareaid_id_value": null
}
```

## <a name="see-also"></a>Vedere anche

[Introduzione all'API di integrazione retribuzioni](hr-admin-integration-payroll-api-introduction.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
