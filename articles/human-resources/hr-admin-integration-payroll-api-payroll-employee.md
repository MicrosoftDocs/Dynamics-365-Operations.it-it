---
title: Dipendente retribuzioni
description: Questo argomento fornisce dettagli e una query di esempio per l'entità Dipendente retribuzioni in Dynamics 365 Human Resources.
author: jcart
manager: tfehr
ms.date: 04/07/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2021-04-07
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: d3977b758f65875a36749a49459c2a81459a7b69
ms.sourcegitcommit: d18d9cdb175c9d42eafbed66352c24b2aa94258b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2021
ms.locfileid: "5882018"
---
# <a name="payroll-employee"></a>Dipendente retribuzioni

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Questo argomento fornisce dettagli e una query di esempio per l'entità Dipendente retribuzioni in Dynamics 365 Human Resources.

## <a name="properties"></a>Proprietà

| Proprietà<br>**Nome fisico**<br>**_Tipo_** | Utilizza | descrizione |
| --- | --- | --- |
| **Numero dipendente**<br>mshr_personnelnumber<br>*String* | Sola lettura<br>Richiesto | Il numero personale univoco del dipendente. |
| **Campo principale**<br>mshr_primaryfield<br>*String* | Richiesto<br>Generato dal sistema |  |
| **Cognome**<br>mshr_lastname<br>*String* | Sola lettura<br>Richiesto | Il cognome del dipendente. |
| **ID persona giuridica**<br>mshr_legalentityID<br>*String* | Sola lettura<br>Richiesto | Specifica la persona giuridica (società). |
| **Data di inizio validità**<br>mshr_namevalidfrom<br>*Offset data/ora* | Sola lettura <br>Richiesto | La data di inizio validità delle informazioni sul dipendente.  |
| **Genere**<br>mshr_gender<br>*Int32* | Sola lettura<br>Richiesto | Il sesso del dipendente. |
| **ID entità dipendente retribuzioni**<br>mshr_payrollemployeeentityid<br>*GUID* | Richiesto<br>Generato dal sistema | Un valore GUID generato dal sistema per identificare in modo univoco il dipendente. |
| **Data di inizio impiego**<br>mshr_employmentstartdate<br>*Offset data/ora* | Sola lettura<br>Richiesto | La data di inizio dell'impiego del dipendente. |
| **ID tipo di identificazione**<br>mshr_identificationtypeid<br>*String* |Sola lettura<br>Richiesto | Il tipo di identificazione definito per il dipendente. |
| **Data di fine impiego**<br>mshr_employmentenddate<br>*Offset data/ora* | Sola lettura<br>Richiesto |La data di fine dell'impiego del dipendente.  |
| **ID area dati**<br>mshr_dataareaid_id<br>*GUID* | Richiesto <br>Generato dal sistema | Valore GUID generato dal sistema che identifica la persona giuridica (società). |
| **Data di fine validità**<br>mshr_namevalidto<br>*Offset data/ora* |  Sola lettura<br>Richiesto | La data di fine validità delle informazioni sul dipendente. |
| **Data di nascita**<br>mshr_birthdate<br>*Offset data/ora* | Sola lettura <br>Richiesto | La data di nascita del dipendente |
| **Numero di identificazione**<br>mshr_identificationnumber<br>*String* | Sola lettura <br>Richiesto |Il numero di identificazione definito per il dipendente.  |
| **Nome**<br>mshr_firstname<br>*String* | Sola lettura<br>Richiesto | Il nome del dipendente. |
| **Secondo nome**<br>mshr_middlename<br>*String* | Sola lettura<br>Richiesto |Il secondo nome del dipendente.  |

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
            "mshr_firstname": "Cassie",
            "mshr_middlename": "Lassie",
            "mshr_lastname": "Hicks",
            "mshr_namevalidfrom": "2021-03-12T20:34:25Z",
            "mshr_namevalidto": "2154-12-31T23:59:59Z",
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
