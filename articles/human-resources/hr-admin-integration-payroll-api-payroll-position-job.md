---
title: Mansione posizione di retribuzione
description: Questo argomento fornisce dettagli e una query di esempio per l'entità Mansione posizione di retribuzione in Dynamics 365 Human Resources.
author: jcart
ms.date: 04/07/2021
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
ms.openlocfilehash: 349479d9e77861b54d879bcfd93f7af0e38cff95
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/31/2022
ms.locfileid: "8069834"
---
# <a name="payroll-position-job"></a>Mansione posizione di retribuzione


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Questo argomento descrive l'entità mansione posizione Retribuzioni per Dynamics 365 Human Resources.

### <a name="description"></a>descrizione

Questa entità fornisce la relazione tra posizione e mansione per un determinato piano di retribuzione fissa.

Nome fisico: mshr_payrollpositionjobentity.

## <a name="properties"></a>Proprietà

| Proprietà</br>**Nome fisico**</br>**_Tipo_** | Utilizza | Descrizione |
| --- | --- | --- |
| **ID posizione**</br>mshr_positionid</br>*String* | Sola lettura | L'ID della posizione. |
| **Data di inizio validità**</br>mshr_validto</br>*Offset data/ora* | Sola lettura | La data di inizio validità della relazione tra posizione e mansione. |
| **Data di fine validità**</br>mshr_validto</br>*Offset data/ora* | Sola lettura | La data di fine validità della relazione tra posizione e mansione. |
| **ID lavoro**</br>mshr_jobid</br>*String* | Sola lettura | L'ID della mansione. |
| **Campo principale**</br>mshr_primaryfield</br>*String* | Generato dal sistema | Campo principale. |
| **ID entità mansione posizione di retribuzione**</br>mshr_payrollpositionjobentityid</br>*GUID* | Generato dal sistema. | Un valore dell'identificatore univoco globale (GUID) generato dal sistema per identificare la mansione in modo univoco. |

## <a name="relations"></a>Relazioni

| Valore proprietà | Entità correlata | Proprietà di navigazione | Tipo di raccolta |
| --- | --- | --- | --- |
| _mshr_fk_fixedcompplan_id_value | mshr_payrollfixedcompensationplanentity | mshr_FK_FixedCompPlan_id | mshr_FK_PayrollFixedCompensationPlanEntity_Job |
| _mshr_fk_jobdetail_id_value | mshr_hcmjobdetailentity | mshr_FK_JobDetail_id | Non applicabile |
| _mshr_fk_payroll_id_value | mshr_payrollpositionentity | mshr_FK_Payroll_id | mshr_FK_PayrollPositionEntity_Job |

## <a name="example-query"></a>Query di esempio

**Richiesta**

```http
GET [Organizaton URI]/api/data/v9.1/mshr_payrollpositionjobentities?$filter=mshr_positionid eq '000276'
```

**Risposta**

```json
{
    "mshr_positionid": "000276",
    "mshr_validfrom": "2016-07-06T18:11:33Z",
    "mshr_validto": "2154-12-31T23:59:59Z",
    "mshr_jobid": "Accountant",
    "mshr_primaryfield": "000276 | Accountant | 7/6/2016 06:11:33 pm",
    "_mshr_fk_jobdetail_id_value": "00000b8d-0000-0000-b0ff-004105000000",
    "_mshr_fk_fixedcompplan_id_value": "0000058a-0000-0000-d5ff-004105000000",
    "_mshr_fk_payroll_id_value": "00000427-0000-0000-df00-014105000000",
    "mshr_payrollpositionjobentityid": "00000906-0000-0000-df00-014105000000"
}
```

## <a name="see-also"></a>Vedere anche

[Introduzione all'API di integrazione retribuzioni](hr-admin-integration-payroll-api-introduction.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
