---
title: Piano di benefit lavoratore per retribuzioni
description: Questo articolo fornisce dettagli e una query di esempio per l'entità Piano di benefit lavoratore per retribuzioni in Dynamics 365 Human Resources.
author: twheeloc
ms.date: 07/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2021-07-28
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: ef45855d9e60131ac065ae6e2769b71ae3f69537
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8902287"
---
# <a name="payroll-worker-benefit-plan"></a>Piano di benefit lavoratore per retribuzioni


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Questo articolo l'entità Piano di benefit lavoratore per retribuzioni per Dynamics 365 Human Resources.

Nome fisico: mshr_payrollworkerbenefitplanentities.

### <a name="description"></a>descrizione

Questa entità fornisce informazioni sul piano di benefit per un determinato lavoratore.

## <a name="properties"></a>Proprietà

| Proprietà</br>**Nome fisico**</br>**_Tipo_** | Utilizza | descrizione |
| --- | --- | --- |
| **Numero dipendente**</br>mshr_personnelnumber</br>*String* | Sola lettura</br>Richiesto | Il numero personale univoco del dipendente. |
| **ID persona giuridica**</br>mshr_legalentityID</br>*String* | Sola lettura | Specifica la persona giuridica (società). |
| **ID periodo**</br>mshr_periodid</br>*String* | Sola lettura | Identificatore del periodo. |
| **ID piano**</br>mshr_planid</br>*String* | Sola lettura | Identificatore del piano. |
| **Opzione di copertura**</br>mshr_coverageoptionid</br>*String* | Sola lettura | Identificazione dell'opzione di copertura. |
| **Data di inizio detrazione**</br>mshr_deductionstartdatetime</br>*Offset data/ora* | Sola lettura | Data di inizio detrazione. |
| **Data di fine detrazione**</br>mshr_deductionenddatetime</br>*Offset data/ora* | Sola lettura | Data di fine detrazione. |
| **Stato**</br>mshr_status</br>*[Opzione Stato del piano di benefit per dipendenti impostata](hr-admin-integration-payroll-api-benefit-employee-plan-status.md)* | Sola lettura | Stato del piano di benefit. |
| **Data di inizio validità**</br>mshr_validfrom</br>*Offset data/ora* | Sola lettura | Ora a partire dalla quale questo record è valido. |
| **Data di fine validità**</br>mshr_validto</br>*Offset data/ora* |  Sola lettura | Ora fino alla quale questo record è valido. |
| **ID tipo di piano**</br>mshr_plantypeid</br>*String* | Sola lettura | Identificatore del tipo di piano. |
| **Codice tipo di piano**</br>mshr_plantypecode</br>*[Opzione Tipo di copertura del piano di benefit impostata](hr-admin-integration-payroll-api-benefit-plan-type-cover.md)* | Sola lettura | Specifica del tipo di piano. |
| **Numero di periodi retributivi**</br>mshr_payperiod</br>*Integer* | Sola lettura | Il numero di periodi retributivi che rappresenta la frequenza alla quale il prestatore di benefit o i dipendenti sono pagati. Questo importo verrà utilizzato per calcolare l'importo della retribuzione benefit annuale del dipendente. |
| **Importo dipendente**</br>mshr_amountemployee</br>*Decimali* | Sola lettura | Percentuale o importo del dipendente. |
| **Importo datore di lavoro**</br>mshr_amountemployer</br>*Decimali* | Sola lettura | Percentuale o importo del datore di lavoro. |
| **Campo principale**</br>mshr_primaryfield</br>*String* | Generato dal sistema | Campo principale. |
| **Valore ID lavoratore** </br>_mshr_fk_worker_id_value</br>*GUID* | Chiave esterna: mshr_hcmworkerbaseentityid dell'entità mshr_hcmworkerbaseentity. | Identificatore univoco generato dal sistema per il lavoratore. |
| **Valore ID periodo**</br> _mshr_fk_period_id_value</br>*GUID* | Chiave esterna: mshr_benefitperiodentityid dell'entità mshr_benefitperiodentity. | Identificatore univoco generato dal sistema per il periodo. |
| **Valore ID piano**</br> _mshr_fk_plan_id_value</br>*GUID* | Chiave esterna: mshr_benefitplanentityid dell'entità mshr_benefitplanentity. | Identificatore univoco generato dal sistema per il piano. |
| **Valore ID tipo di piano**</br> _mshr_fk_plantype_id_value</br>*GUID* | Chiave esterna: mshr_benefitplantypeentityid dell'entità mshr_benefitplantypeentity. | Identificatore univoco generato dal sistema per il piano. |
| **Valore ID opzione di copertura**</br> _mshr_fk_coverageoption_id_value</br>*GUID* | Chiave esterna: mshr_benefitcoverageoptionentityid dell'entità mshr_benefitcoverageoptionentity. | Identificatore univoco generato dal sistema per il piano. |
| **Valore ID del piano di benefit lavoratore per retribuzioni**</br> mshr_payrollworkerbenefitplanentityid</br>*GUID* | Sola lettura </br> Generato dal sistema | Identificatore univoco generato dal sistema per il record. |

## <a name="example-query-for-payroll-worker-benefit-plan"></a>Esempio di query per Piano di benefit lavoratore per retribuzioni

**Richiesta**

```http
GET [Organization URI]/api/data/v9.1/mshr_payrollworkerbenefitplanentities?$filter=mshr_personnelnumber eq '000020'
```

**Risposta**

```json
{
    "mshr_personnelnumber": "000020",
    "mshr_legalentityid": "USMF",
    "mshr_periodid": "2021",
    "mshr_planid": "Dental plan",
    "mshr_coverageoptionid": "Emp Only",
    "mshr_deductionstartdatetime": "2021-01-01T06:00:00Z",
    "mshr_deductionenddatetime": "2021-12-31T06:00:00Z",
    "mshr_status": 200000001,
    "mshr_validfrom": "2021-01-01T06:00:00Z",
    "mshr_validto": "2021-12-31T06:00:00Z",
    "mshr_plantypeid": "Dental",
    "mshr_plantypecode": 200000001,
    "mshr_payperiod": 12,
    "mshr_amountemployee": 47,
    "mshr_amountemployer": 57,
    "mshr_primaryfield": "000020 | USMF | 2021 | Dental plan",
    "_mshr_fk_worker_id_value": "000000ae-0000-0000-bfff-004105000000",
    "_mshr_fk_period_id_value": "00000807-0000-0000-ee02-005001000000",
    "_mshr_fk_plan_id_value": "00000c61-0000-0000-0200-005001000000",
    "_mshr_fk_plantype_id_value": "0000057c-0000-0000-0200-005001000000",
    "_mshr_fk_coverageoption_id_value": "00000391-0000-0000-0b00-005001000000",
    "mshr_payrollworkerbenefitplanentityid": "000006c4-0000-0000-bfff-004105000000"
}
```
## <a name="see-also"></a>Vedere anche

[Introduzione all'API di integrazione retribuzioni](hr-admin-integration-payroll-api-introduction.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
