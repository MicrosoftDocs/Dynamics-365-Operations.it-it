---
title: Piano di retribuzione variabile retribuzioni
description: Questo argomento fornisce dettagli e una query di esempio per l'entità Piano di retribuzione variabile retribuzioni in Dynamics 365 Human Resources.
author: marcelbf
ms.date: 06/15/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-06-15
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 96a644bf129de6dd3f78098bcb6415d17058d6decbd7d904a99bb6f050d3a9e0
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6730444"
---
# <a name="payroll-variable-compensation-plan"></a>Piano di retribuzione variabile retribuzioni

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Questo argomento descrive l'entità piano di retribuzione variabile retribuzioni per Dynamics 365 Human Resources.

### <a name="description"></a>descrizione

Questa entità fornisce il piano di retribuzione variabile assegnato per una determinata posizione di un dipendente.

Nome fisico: mshr_payrollvariablecompensationawardentity.

## <a name="properties"></a>Proprietà

| Proprietà</br>**Nome fisico**</br>**_Tipo_** | Utilizza | descrizione |
| --- | --- | --- |
| **Numero dipendente**</br>mshr_personnelnumber</br>*String* | Sola lettura</br>Richiesto |Il numero personale univoco del dipendente.  |
| **Data premio**</br>mshr_awarddate</br>*Offset data/ora* | Sola lettura</br>Richiesto | Data del premio. |
| **Tipo di premio**</br>mshr_awardtype</br>*[set di opzioni mshr_HrmCompVarAwardEmplType](hr-admin-integration-payroll-api-award-type.md)* | Sola lettura</br>Richiesto | Tipo di premio definito per il piano di retribuzione variabile. |
| **Valuta**</br>mshr_unitcurrencycode</br>*String* | Sola lettura </br>Richiesto |La valuta definita per il piano di retribuzione variabile.   |
| **ID piano di retribuzione fissa**</br>mshr_fixedplanid</br>*String* | Sola lettura | Il piano di retribuzione fissa utilizzato come base per il calcolo del premio. |
| **Valore unitario**</br>mshr_awardamount</br>*Decimali* | Sola lettura | Valore dell'unità |
| **Tipo di processo**</br>mshr_processtype</br>*[set di opzioni mshr_hrmCompProcessType](hr-admin-integration-payroll-api-process-type.md)* | Sola lettura | Tipo di processo. |
| **Tipo di piano di retribuzione variabile**</br>String</br>*mshr_typeid* | Sola lettura | Tipo di piano di retribuzione variabile. |
| **ID piano di retribuzione variabile**</br>String</br>*mshr_planid* | Sola lettura | ID piano di retribuzione variabile. |
| **Campo principale**</br>mshr_primaryfield</br>*GUID* | Sola lettura</br>Generato dal sistema. | |
| **ID dipendente**</br>mshr_fk_employee_id_value</br>*GUID* | Sola lettura</br>Richiesto</br>Chiave esterna: mshr_Employee_id of mshr_payrollemployeeentity entity  | ID dipendente. |
| **Entità piano di retribuzione variabile retribuzioni**</br>mshr_payrollvariablecompensationawardentityid</br>*GUID* | Richiesto</br>Generato dal sistema | Un valore GUID generato dal sistema per identificare in modo univoco il piano di retribuzione. |


## <a name="example-query"></a>Query di esempio

**Richiesta**

```http
GET [Organizaton URI]/api/data/v9.1/mshr_payrollvariablecompensationawardentities?$filter=mshr_personnelnumber eq '000001'
```

**Risposta**

```json
{
    "mshr_personnelnumber": "000001",
    "mshr_awarddate": "2015-01-15T00:00:00Z",
    "mshr_awardtype": 200000000,
    "mshr_unitcurrencycode": "USD",
    "mshr_fixedplanid": "",
    "mshr_awardamount": 1,
    "mshr_processtype": 200000003,
    "mshr_typeid": "Bonus",
    "mshr_planid": "MgBonus",
    "mshr_primaryfield": "000001 | MgBonus | Bonus | 1/15/2015",
    "_mshr_fk_employee_id_value": "00000655-0000-0000-adff-004105000000",
    "mshr_payrollvariablecompensationawardentityid": "000001a1-0000-0000-adff-004105000000",
    "_mshr_fk_fixedcomp_id_value": null
}
```

## <a name="see-also"></a>Vedere anche

[Introduzione all'API di integrazione retribuzioni](hr-admin-integration-payroll-api-introduction.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
