---
title: Dipendente retribuzioni
description: Questo argomento fornisce dettagli e una query di esempio per l'entità Dipendente retribuzioni in Dynamics 365 Human Resources.
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
ms.openlocfilehash: 450872a38c833de9d37e2c6224839f2bca7cb4c6
ms.sourcegitcommit: 4d11061f5de0ddba1f968bd5c3fd694a8b104ccc
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "7429236"
---
# <a name="payroll-employee"></a>Dipendente retribuzioni

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Questo argomento descrive l'entità dipendente Retribuzioni per Dynamics 365 Human Resources.

Nome fisico: mshr_payrollemployeeentity.

### <a name="description"></a>descrizione

Questa entità fornisce informazioni sul dipendente. È necessario impostare i [parametri di integrazione retribuzioni](hr-admin-integration-payroll-api-parameters.md) prima di utilizzare questa entità.

>[!IMPORTANT] 
>I campi **FirstName**, **MiddleName**, **LastName**, **NameValidFrom**, e **NameValidTo** non saranno più disponibili in questa entità. Ciò garantisce che ci sia solo un'origine dati effettiva della data che supporta questa entità.
>Questi campi saranno disponibili in **DirPersonNameHistoricalEntity**, che è stata rilasciata nell'aggiornamento della piattaforma 43. Esiste una relazione OData da **PayrollEmployeeEntity** a **DirPersonNameHistoricalEntity**. 

## <a name="properties"></a>Proprietà

| Proprietà</br>**Nome fisico**</br>**_Tipo_** | Utilizza | descrizione |
| --- | --- | --- |
| **ID persona giuridica**</br>mshr_legalentityid</br>*String* | Sola lettura | Specifica la persona giuridica (società). |
| **Numero dipendente**</br>mshr_personnelnumber</br>*String* | Sola lettura | Il numero personale univoco del dipendente. |
| **Data di inizio impiego**</br>mshr_employmentstartdate</br>*Offset data/ora* | Sola lettura | La data di inizio dell'impiego del dipendente. |
| **Data di fine impiego**</br>mshr_employmentenddate</br>*Offset data/ora* | Sola lettura |La data di fine dell'impiego del dipendente.  |
| **Data di nascita**</br>mshr_birthdate</br>*Offset data/ora* | Sola lettura | La data di nascita del dipendente. |
| **Genere**</br>mshr_gender</br>[set di opzioni mshr_hcmpersongender](hr-admin-integration-payroll-api-gender.md) | Sola lettura | Il sesso del dipendente. |
| **Tipo di impiego**</br>mshr_employmenttype</br>[Set di opzioni mshr_hcmemploymenttype](hr-admin-integration-payroll-api-hcmemploymenttype.md) | Sola lettura | Il tipo di impiego. |
| **ID tipo di identificazione**</br>mshr_identificationtypeid</br>*String* |Sola lettura | Il tipo di identificazione definito per il dipendente. |
| **Numero di identificazione**</br>mshr_identificationnumber</br>*String* | Sola lettura |Il numero di identificazione definito per il dipendente. |
| **Pronto per il pagamento**</br>mshr_readytopay</br>[set di opzioni mshr_noyes](hr-admin-integration-payroll-api-no-yes.md) | Sola lettura | Indica se il dipendente è contrassegnato come Pronto per il pagamento. |
| **ID entità dipendente retribuzioni**</br>mshr_payrollemployeeentityid</br>*GUID* | Richiesto</br>Generato dal sistema | Un valore GUID generato dal sistema per identificare in modo univoco il dipendente. |

## <a name="relations"></a>Relazioni

|Valore proprietà | Entità correlata | Proprietà di navigazione | Tipo di raccolta |
| --- | --- | --- | --- |
| _mshr_fk_employment_id_value | mshr_hcmemploymentdetailentity | mshr_FK_Employment_id | - |
| _mshr_fk_fixedcompplan_id_value | [mshr_payrollfixedcompensationplanentity](hr-admin-integration-payroll-api-payroll-fixed-compensation-plan.md) | mshr_FK_FixedCompPlan_id | mshr_FK_PayrollFixedCompensationPlanEntity_Employee |
| _mshr_fk_name_id_value | mshr_dirpersonnamehistoricalentity | mshr_FK_Name_id | - |
| _mshr_fk_worker_id_value | mshr_hcmworkerbaseentity | mshr_FK_Worker_id | - |
| _mshr_fk_workerbankaccount_id_value | mshr_hcmworkerbankaccountentity | mshr_FK_WorkerBankAccount_id | - |
| _mshr_fk_variablecompaward_id_value | [mshr_payrollvariablecompensationawardentity](hr-admin-integration-payroll-api-payroll-variable-compensation-plan.md) | mshr_FK_VariableCompAward_id | mshr_FK_PayrollVariableCompensationAwardEntity_Employee |
| _mshr_fk_address_id_value | [mshr_payrollworkeraddressentity](hr-admin-integration-payroll-api-payroll-worker-address.md) | mshr_FK_Address_id | mshr_FK_PayrollWorkerAddressEntity_Worker |

## <a name="example-query-for-payroll-employee"></a>Query di esempio per Dipendente retribuzioni

**Richiesta**

```http
GET [Organizaton URI]/api/data/v9.1/mshr_payrollemployeeentities?$filter=mshr_personnelnumber eq '000041'
```

**Risposta**

```json
{
    "mshr_legalentityid": "USMF",
    "mshr_personnelnumber": "000041",
    "mshr_employmentstartdate": "2011-04-05T07:00:00Z",
    "mshr_employmentenddate": "2154-12-31T23:59:59Z",
    "mshr_birthdate": "1987-09-12T00:00:00Z",
    "mshr_gender": 200000002,
    "mshr_employmenttype": 200000000,
    "mshr_identificationtypeid": "SSN",
    "mshr_identificationnumber": "888-99-9342",
    "mshr_readytopay": 200000000,
    "mshr_dataareaid": "USMF",
    "mshr_primaryfield": "000041 | USMF | 4/5/2011 07:00:00 am",
    "_mshr_fk_employment_id_value": "00000d4e-0000-0000-0600-014105000000",
    "_mshr_fk_fixedcompplan_id_value": "00000598-0000-0000-4cd0-fda002000000",
    "_mshr_fk_name_id_value": "00000832-0000-0000-d700-014105000000",
    "_mshr_fk_worker_id_value": "000000af-0000-0000-d5ff-004105000000",
    "_mshr_fk_workerbankaccount_id_value": "000006f2-0000-0000-b7ff-004105000000",
    "mshr_payrollemployeeentityid": "00000666-0000-0000-d5ff-004105000000",
    "_mshr_fk_address_id_value": null,
    "_mshr_fk_variablecompaward_id_value": null,
    "_mshr_dataareaid_id_value": null
}
```

## <a name="see-also"></a>Vedere anche

[Introduzione all'API di integrazione retribuzioni](hr-admin-integration-payroll-api-introduction.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
