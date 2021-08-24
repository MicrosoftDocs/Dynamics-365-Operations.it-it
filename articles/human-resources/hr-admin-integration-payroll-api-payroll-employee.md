---
title: Dipendente retribuzioni
description: Questo argomento fornisce dettagli e una query di esempio per l'entità Dipendente retribuzioni in Dynamics 365 Human Resources.
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
ms.openlocfilehash: 20e74e97f98d0bc0fd454d54cbf969d4f1b46c7c98b2949b0ed8cfe671312dd2
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6768193"
---
# <a name="payroll-employee"></a>Dipendente retribuzioni

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Questo argomento descrive l'entità dipendente Retribuzioni per Dynamics 365 Human Resources.

Nome fisico: mshr_payrollemployeeentity.

### <a name="description"></a>descrizione

Questa entità fornisce informazioni sul dipendente. È necessario impostare i [parametri di integrazione retribuzioni](hr-admin-integration-payroll-api-parameters.md) prima di utilizzare questa entità.

>[!IMPORTANT] 
>I campi **FirstName**, **MiddleName**, **LastName**, **NameValidFrom**, e **NameValidTo** non saranno più disponibili in questa entità. Ciò garantisce che ci sia solo un'origine dati effettiva della data che supporta questa entità.
>Questi campi saranno disponibili in **DirPersonNameHistoricalEntity**, che è stata rilasciata nell'aggiornamento della piattaforma 43. Esiste una relazione OData da **PayrollEmployeeEntity** a **DirPersonNameHistoricalEntity** nel campo **Persona**. 

## <a name="properties"></a>Proprietà

| Proprietà<br>**Nome fisico**<br>**_Tipo_** | Utilizza | descrizione |
| --- | --- | --- |
| **Numero dipendente**<br>mshr_personnelnumber<br>*String* | Sola lettura | Il numero personale univoco del dipendente. |
| **Campo principale**<br>mshr_primaryfield<br>*String* | Sola lettura<br>Generato dal sistema |  |
| **ID persona giuridica**<br>mshr_legalentityID<br>*String* | Sola lettura | Specifica la persona giuridica (società). |
| **Genere**<br>mshr_gender<br>[set di opzioni mshr_hcmpersongender](hr-admin-integration-payroll-api-gender.md) | Sola lettura | Il sesso del dipendente. |
| **ID entità dipendente retribuzioni**<br>mshr_payrollemployeeentityid<br>*GUID* | Richiesto<br>Generato dal sistema | Un valore GUID generato dal sistema per identificare in modo univoco il dipendente. |
| **Data di inizio impiego**<br>mshr_employmentstartdate<br>*Offset data/ora* | Sola lettura | La data di inizio dell'impiego del dipendente. |
| **ID tipo di identificazione**<br>mshr_identificationtypeid<br>*String* |Sola lettura | Il tipo di identificazione definito per il dipendente. |
| **Data di fine impiego**<br>mshr_employmentenddate<br>*Offset data/ora* | Sola lettura |La data di fine dell'impiego del dipendente.  |
| **ID area dati**<br>mshr_dataareaid_id<br>*GUID* | Sola lettura <br>Generato dal sistema | Valore GUID generato dal sistema che identifica la persona giuridica (società). |
| **Data di fine validità**<br>mshr_namevalidto<br>*Offset data/ora* |  Sola lettura | La data di fine validità delle informazioni sul dipendente. |
| **Data di nascita**<br>mshr_birthdate<br>*Offset data/ora* | Sola lettura | La data di nascita del dipendente |
| **Numero di identificazione**<br>mshr_identificationnumber<br>*String* | Sola lettura |Il numero di identificazione definito per il dipendente.  |

## <a name="example-query-for-payroll-employee"></a>Query di esempio per Dipendente retribuzioni

**Richiesta**

```http
GET [Organizaton URI]/api/data/v9.1/mshr_payrollemployeeentities?$filter=mshr_personnelnumber eq @personnelnumber and mshr_identificationtypeid eq @idtype and mshr_namevalidfrom le @asofdate and mshr_namevalidto ge @asofdate&@personnelnumber='000041'&@idtype='SSN'&@asofdate=2021-04-01
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
    "mshr_identificationtypeid": "SSN",
    "mshr_identificationnumber": "888-99-9342",
    "mshr_dataareaid": "USMF",
    "mshr_primaryfield": "000041 | USMF | 4/5/2011 07:00:00 am",
    "_mshr_fk_worker_id_value": "000000ad-0000-0000-d5ff-004105000000",
    "_mshr_fk_employment_id_value": "00000d0d-0000-0000-0600-014105000000",
    "_mshr_fk_fixedcompplan_id_value": "0000029f-0000-0000-d5ff-004105000000",
    "mshr_payrollemployeeentityid": "00000d3c-0000-0000-d5ff-004105000000",
    "_mshr_dataareaid_id_value": null
}
```
## <a name="see-also"></a>Vedere anche

[Introduzione all'API di integrazione retribuzioni](hr-admin-integration-payroll-api-introduction.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
