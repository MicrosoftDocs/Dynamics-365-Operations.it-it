---
title: Piano di retribuzione fissa retribuzioni
description: Questo argomento fornisce dettagli e una query di esempio per l'entità Piano di retribuzione fissa retribuzioni in Dynamics 365 Human Resources.
author: jcart
ms.date: 08/25/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2021-04-07
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: dcb253fabbb183003048119c7a627bf0ab960050
ms.sourcegitcommit: 4d11061f5de0ddba1f968bd5c3fd694a8b104ccc
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "7429233"
---
# <a name="payroll-fixed-compensation-plan"></a>Piano di retribuzione fissa retribuzioni

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Questo argomento descrive l'entità piano di retribuzione fissa retribuzioni per Dynamics 365 Human Resources.

### <a name="description"></a>descrizione

Questa entità fornisce il piano di retribuzione fissa assegnato per una determinata posizione di un dipendente.

Nome fisico: mshr_payrollfixedcompensationplanentity.

## <a name="properties"></a>Proprietà

| Proprietà</br>**Nome fisico**</br>**_Tipo_** | Utilizza | descrizione |
| --- | --- | --- |
| **ID piano**</br>mshr_planid</br>*String* | Sola lettura | Specifica il piano di retribuzione.  |
| **Numero dipendente**</br>mshr_personnelnumber</br>*String* | Sola lettura | Il numero personale univoco del dipendente. |
| **Retribuzione**</br>mshr_payrate</br>*Decimali* | Sola lettura | La tariffa retributiva definita nel piano di retribuzione fissa. |
| **ID posizione**</br>mshr_positionid</br>*String* | Sola lettura | ID posizione associato al dipendente e l'iscrizione al piano di retribuzione fissa. |
| **Data di inizio validità**</br>mshr_validfrom</br>*Offset data/ora* |  Sola lettura | La data di inizio validità della retribuzione fissa del dipendente.  |
| **Data di fine validità**</br>mshr_validto</br>*Offset data/ora* | Sola lettura | La data di fine validità della retribuzione fissa del dipendente. |
| **Frequenza retribuzione**</br>mshr_payfrequency</br>*String* | Sola lettura | La frequenza alla quale verrà retribuito il dipendente.  |
| **Valuta**</br>mshr_currency</br>*String* | Sola lettura | La valuta definita per il piano di retribuzione fissa. |
| **Entità piano di retribuzione fissa retribuzioni**</br>mshr_payrollfixedcompensationplanentityid</br>*GUID* | Generato dal sistema | Un valore GUID generato dal sistema per identificare in modo univoco il piano di retribuzione. |

## <a name="relations"></a>Relazioni

|Valore proprietà | Entità correlata | Proprietà di navigazione | Tipo di raccolta |
| --- | --- | --- | --- |
| _mshr_fk_employee_id_value | [mshr_payrollemployeeentity](hr-admin-integration-payroll-api-payroll-employee.md) | mshr_FK_Employee_id | mshr_FK_PayrollEmployeeEntity_FixedCompPlan |
| _mshr_fk_job_id_value | [mshr_payrollpositionjobentity](hr-admin-integration-payroll-api-payroll-position-job.md) | mshr_FK_Job_id | mshr_FK_PayrollPositionJobEntity_FixedCompPlan |
| _mshr_fk_payrollposition_id_value | [mshr_payrollpositionentity](hr-admin-integration-payroll-api-payroll-position.md) | mshr_FK_PayrollPosition_id | mshr_FK_PayrollPositionEntity_FixedCompPlan |
| _mshr_fk_plan_id_value | mshr_hcmcompfixedplantableentity | mshr_FK_Plan_id | - |
| _mshr_fk_variablecompaward_id_value | [mshr_payrollvariablecompensationawardentity](hr-admin-integration-payroll-api-payroll-variable-compensation-plan.md) | mshr_FK_VariableCompAward_id | mshr_FK_PayrollVariableCompensationAwardEntity_FixedComp |

## <a name="example-query"></a>Query di esempio

**Richiesta**

```http
GET [Organizaton URI]/api/data/v9.1/mshr_payrollfixedcompensationplanentities?$filter=mshr_personnelnumber eq @personnelnumber and mshr_validfrom le @asofdate and mshr_validto ge @asofdate&@personnelnumber='000041'&@asofdate=2021-04-01
```

**Risposta**

```json
{
    "mshr_planid": "GradeC",
    "mshr_personnelnumber": "000041",
    "mshr_payrate": 75200,
    "mshr_positionid": "000276",
    "mshr_validfrom": "2011-04-05T00:00:00Z",
    "mshr_validto": "2154-12-31T00:00:00Z",
    "mshr_payfrequency": "Annual",
    "mshr_currency": "USD",
    "_mshr_fk_employee_id_value": "00000d3c-0000-0000-d5ff-004105000000",
    "_mshr_fk_plan_id_value": "0000070c-0000-0000-b328-fef003000000",
    "_mshr_fk_job_id_value": "00010094-0000-0000-df00-014105000000",
    "mshr_payrollfixedcompensationplanentityid": "0000029f-0000-0000-d5ff-004105000000",
    "_mshr_fk_payroll_id_value": null
}
```

## <a name="see-also"></a>Vedere anche

[Introduzione all'API di integrazione retribuzioni](hr-admin-integration-payroll-api-introduction.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
