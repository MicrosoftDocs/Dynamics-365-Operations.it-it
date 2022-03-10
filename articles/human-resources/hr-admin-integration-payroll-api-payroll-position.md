---
title: Dettagli retribuzione per posizioni
description: Questo argomento fornisce dettagli e una query di esempio per l'entità Dettagli retribuzione per posizioni in Dynamics 365 Human Resources.
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
ms.openlocfilehash: 2bbb234d2f51391ea65e3d6153d6cee250f3c6dc
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/31/2022
ms.locfileid: "8069809"
---
# <a name="payroll-position"></a>Posizione di retribuzione


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Questo argomento descrive l'entità Posizioni Retribuzioni in Dynamics 365 Human Resources.

Nome fisico: mshr_payrollpositionentity.

### <a name="description"></a>descrizione

Questa entità fornisce informazioni correlate alla posizione per un determinato dipendente.

Nome fisico: mshr_payrollpositionentity.

## <a name="properties"></a>Proprietà

| Proprietà</br>**Nome fisico**</br>**_Tipo_** | Utilizza | Descrizione |
| --- | --- | --- |
| **ID posizione**</br>mshr_positionid</br>*String* | Sola lettura | L'ID della posizione. |
| **ID ciclo retributivo**</br>mshr_paycycleid</br>*String* | Sola lettura | Il ciclo retributivo definito per la posizione. |
| **Ore regolari annuali**</br>annualregularhours</br>*Decimale* | Sola lettura | Ore regolari annuali definite per la posizione. |
| **Pagamento in base alla persona giuridica**</br>paidbylegalentity</br>*String* | Sola lettura | La persona giuridica definita nella posizione e responsabile dell'emissione del pagamento. |
| **Data di fine validità**</br>validto</br>*Offset data/ora* | Sola lettura | La data di fine validità dei dettagli della posizione. |
| **Data di inizio validità**</br>validfrom</br>*Offset data/ora* | Sola lettura | La data di inizio validità dei dettagli della posizione. |
| **Campo principale**</br>mshr_primaryfield</br>*String* | Generato dal sistema | Campo principale. |
| **ID entità dettagli posizione di retribuzione**</br>payrollpositiondetailsentityid</br>*GUID* | Obbligatorio</br>Generato dal sistema. | Un valore dell'identificatore univoco globale (GUID) generato dal sistema per identificare la posizione in modo univoco. |

## <a name="relations"></a>Relazioni

| Valore proprietà | Entità correlata | Proprietà di navigazione | Tipo di raccolta |
| --- | --- | --- | --- |
| _mshr_fk_fixedcompplan_id_value | [mshr_payrollfixedcompensationplanentity](hr-admin-integration-payroll-api-payroll-fixed-compensation-plan.md) | mshr_FK_FixedCompPlan_id | mshr_FK_PayrollFixedCompensationPlanEntity_PayrollPosition |
| _mshr_fk_hcmpositionhierarchy_id_value | mshr_hcmpositionhierarchyentity | mshr_FK_HcmPositionHierarchy_id | Non applicabile |
| _mshr_fk_job_id_value | mshr_payrollpositionjobentity | mshr_FK_Job_id | mshr_FK_PayrollPositionJobEntity_Payroll |
| _mshr_fk_positionassignmentv2_id_value | mshr_hcmpositionworkerassignmentv2entity | mshr_FK_PositionAssignmentV2_id | Non applicabile |

## <a name="example-query"></a>Query di esempio

**Richiesta**

```http
GET [Organizaton URI]/api/data/v9.1/mshr_payrollpositionentities?$filter=mshr_positionid eq @positionid and mshr_validfrom le @asofdate and mshr_validto ge @asofdate&@positionid='000276'&@asofdate=2021-04-01
```

**Risposta**

```json
{
    "mshr_positionid": "000276",
    "mshr_paycycleid": "w",
    "mshr_annualregularhours": 3000,
    "mshr_paidbylegalentity": "USMF",
    "mshr_validfrom": "2021-03-14T00:00:00Z",
    "mshr_validto": "2154-12-31T00:00:00Z",
    "mshr_primaryfield": "000276 | 3/14/2021",
    "_mshr_fk_job_id_value": "00010094-0000-0000-df00-014105000000",
    "_mshr_fk_fixedcompplan_id_value": "0000029f-0000-0000-d5ff-004105000000",
    "mshr_payrollpositionentityid": "00010097-0000-0000-df00-014105000000"
}
```

## <a name="see-also"></a>Vedere anche

[Introduzione all'API di integrazione retribuzioni](hr-admin-integration-payroll-api-introduction.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
