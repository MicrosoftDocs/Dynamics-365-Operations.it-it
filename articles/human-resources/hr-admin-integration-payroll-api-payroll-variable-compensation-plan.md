---
title: Piano di retribuzione variabile retribuzioni
description: Questo articolo fornisce dettagli e una query di esempio per l'entità Piano di retribuzione variabile retribuzioni in Dynamics 365 Human Resources.
author: twheeloc
ms.date: 06/15/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2021-06-15
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 5c6190084c3f1ce15d6a4ab8f13843a5da801dd3
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8868132"
---
# <a name="payroll-variable-compensation-plan"></a>Piano di retribuzione variabile retribuzioni


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Questo articolo descrive l'entità piano di retribuzione variabile retribuzioni per Dynamics 365 Human Resources.

### <a name="description"></a>descrizione

Questa entità fornisce il piano di retribuzione variabile assegnato per una determinata posizione di un dipendente.

Nome fisico: mshr_payrollvariablecompensationawardentity.

## <a name="properties"></a>Proprietà

| Proprietà</br>**Nome fisico**</br>**_Tipo_** | Utilizza | descrizione |
| --- | --- | --- |
| **Numero dipendente**</br>mshr_personnelnumber</br>*String* | Sola lettura | Il numero personale univoco del dipendente.  |
| **Data premio**</br>mshr_awarddate</br>*Offset data/ora* | Sola lettura | Data del premio. |
| **Tipo di premio**</br>mshr_awardtype</br>*[set di opzioni mshr_HrmCompVarAwardEmplType](hr-admin-integration-payroll-api-award-type.md)* | Sola lettura | Tipo di premio definito per il piano di retribuzione variabile. |
| **Valuta**</br>mshr_unitcurrencycode</br>*String* | Sola lettura |La valuta definita per il piano di retribuzione variabile.   |
| **ID piano di retribuzione fissa**</br>mshr_fixedplanid</br>*String* | Sola lettura | Il piano di retribuzione fissa utilizzato come base per il calcolo del premio. |
| **Valore unitario**</br>mshr_awardamount</br>*Decimali* | Sola lettura | Valore dell'unità |
| **Tipo di processo**</br>mshr_processtype</br>*[set di opzioni mshr_hrmCompProcessType](hr-admin-integration-payroll-api-process-type.md)* | Sola lettura | Tipo di processo. |
| **Tipo di piano di retribuzione variabile**</br>String</br>*mshr_typeid* | Sola lettura | Tipo di piano di retribuzione variabile. |
| **ID piano di retribuzione variabile**</br>String</br>*mshr_planid* | Sola lettura | ID piano di retribuzione variabile. |
| **Numero di unità**</br>Decimali</br>*mshr_numberofunits* | Sola lettura | Il numero di unità del premio. |
| **Campo principale**</br>mshr_primaryfield</br>*GUID* | Sola lettura</br>Generato dal sistema. | |
| **Entità piano di retribuzione variabile retribuzioni**</br>mshr_payrollvariablecompensationawardentityid</br>*GUID* | Generato dal sistema | Un valore GUID generato dal sistema per identificare in modo univoco il piano di retribuzione. |

## <a name="relations"></a>Relazioni 

|Valore proprietà | Entità correlata | Proprietà di navigazione | Tipo di raccolta |
| --- | --- | --- | --- |
| _mshr_fk_employee_id_value | [mshr_payrollemployeeentity](hr-admin-integration-payroll-api-payroll-employee.md) | mshr_FK_Employee_id | mshr_FK_PayrollEmployeeEntity_VariableCompAward |
| _mshr_fk_fixedcomp_id_value | [mshr_payrollfixedcompensationplanentity](hr-admin-integration-payroll-api-payroll-fixed-compensation-plan.md) | mshr_FK_FixedComp_id | mshr_FK_PayrollFixedCompensationPlanEntity_VariableCompAward |

## <a name="example-query"></a>Query di esempio

**Richiesta**

```http
GET [Organizaton URI]/api/data/v9.1/mshr_payrollvariablecompensationawardentities?$filter=mshr_personnelnumber eq '000046'
```

**Risposta**

```json
{
    "mshr_personnelnumber": "000046",
    "mshr_awarddate": "2015-01-15T00:00:00Z",
    "mshr_awardtype": 200000000,
    "mshr_unitcurrencycode": "USD",
    "mshr_fixedplanid": "",
    "mshr_unitvalue": 1,
    "mshr_processtype": 200000003,
    "mshr_typeid": "Bonus",
    "mshr_planid": "MgBonus",
    "mshr_numberofunits": 1500,
    "mshr_primaryfield": "000046 | MgBonus | Bonus | 1/15/2015",
    "_mshr_fk_employee_id_value": "00000666-0000-0000-daff-004105000000",
    "mshr_payrollvariablecompensationawardentityid": "000001a4-0000-0000-0d00-005001000000",
    "_mshr_fk_fixedcomp_id_value": null
}
```

## <a name="see-also"></a>Vedere anche

[Introduzione all'API di integrazione retribuzioni](hr-admin-integration-payroll-api-introduction.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
