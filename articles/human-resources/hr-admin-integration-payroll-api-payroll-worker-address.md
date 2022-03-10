---
title: Indirizzo lavoratore retribuzioni
description: Questo argomento fornisce dettagli e una query di esempio per l'entità Indirizzo lavoratore retribuzioni in Dynamics 365 Human Resources.
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
ms.openlocfilehash: 70e42cbf657a28327699d927731edd36de7c4a64
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/31/2022
ms.locfileid: "8069759"
---
# <a name="payroll-worker-address"></a>Indirizzo lavoratore retribuzioni


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Questo argomento descrive l'entità indirizzo lavoratore Retribuzioni per Dynamics 365 Human Resources.

Nome fisico: mshr_payrollworkeraddressentity.

### <a name="description"></a>descrizione

Questa entità fornisce il luogo di residenza retribuzioni e il luogo di lavoro retribuzioni per un determinato dipendente.

## <a name="properties"></a>Proprietà

| Proprietà</br>**Nome fisico**</br>**_Tipo_** | Utilizza | Descrizione |
| --- | --- | --- |
| **Numero dipendente**</br>mshr_personnelnumber</br>*String* | Sola lettura | Il numero personale univoco del dipendente. |
| **ID ubicazione**</br>mshr_locationidbr>*String* | Sola lettura | L'ID dell'indirizzo. |
| **Indirizzo domicilio**</br>mshr_islivedinaddressbr </br> *[set di opzioni mshr_NoYes](hr-admin-integration-payroll-api-no-yes.md)* | Sola lettura | Un valore che indica se l'indirizzo è il luogo di residenza del dipendente. |
| **Indirizzo lavoro** </br> mshr_isworkedinaddressbr </br>*[set di opzioni mshr_NoYes](hr-admin-integration-payroll-api-no-yes.md)* | Sola lettura | Un valore che indica se l'indirizzo è il luogo di lavoro del dipendente. |
| **Paese**</br>mshr_countryregionid</br>*String* | Sola lettura</br>Obbligatorio | Il paese/area geografica o l'area definito per l'indirizzo. |
| **Codice postale**</br>mshr_zipcode<br>*String* | Sola lettura | Il numero di identificazione definito per il dipendente. |
| **Via**</br>mshr_street</br>*String* | Sola lettura | La via definita per l'indirizzo. |
| **Città**</br>mshr_city</br>*String* | Sola lettura | La città definita per l'indirizzo. |
| **Stato**</br>mshr_state</br>*String* | Sola lettura | Lo stato o la provincia definito per l'indirizzo. |
| **Provincia**</br>mshr_county</br>*String* | Sola lettura | La provincia definita per l'indirizzo. |
| **Data di inizio validità**</br>mshr_postaladdressvalidfrom</br>*Offset data/ora* | Sola lettura | La data di inizio validità dell'indirizzo. |
| **Data di fine validità**</br>mshr_postaladdressvalidto</br>*Offset data/ora* | Sola lettura | La data di fine validità dell'indirizzo. |
| **Campo principale**</br>mshr_primaryfield</br>*String* | Sola lettura | Campo principale. |
| **ID Indirizzo lavoratore retribuzioni**</br>mshr_payrollworkeraddressentityid</br>*GUID* | Generato dal sistema | Un valore dell'identificatore univoco globale (GUID) generato dal sistema per identificare l'indirizzo in modo univoco. |

## <a name="relations"></a>Relazioni

| Valore proprietà | Entità correlata | Proprietà di navigazione | Tipo di raccolta |
| --- | --- | --- | --- |
| _mshr_fk_worker_id_value | [mshr_payrollemployeeentity](hr-admin-integration-payroll-api-payroll-employee.md) | mshr_FK_Worker_id | mshr_FK_PayrollEmployeeEntity_Address |

## <a name="example-query"></a>Query di esempio

**Richiesta**

```http
GET [Organizaton URI]/api/data/v9.1/mshr_payrollworkeraddressentities?$filter=mshr_personnelnumber eq @personnelnumber and mshr_postaladdressvalidfrom le @asofdate and mshr_postaladdressvalidto ge @asofdate&@personnelnumber='000041'&@asofdate=2021-04-01
```

**Risposta**

```json
{
    "mshr_personnelnumber": "000041",
    "mshr_locationid": "000000538",
    "mshr_islivedinaddress": 200000001,
    "mshr_isworkedinaddress": 200000000,
    "mshr_countryregionid": "USA",
    "mshr_zipcode": "99025",
    "mshr_street": "6543 Cypress Ave",
    "mshr_city": "Tacoma",
    "mshr_state": "WA",
    "mshr_county": "KING",
    "mshr_postaladdressvalidfrom": "2012-09-20T20:14:27Z",
    "mshr_postaladdressvalidto": "2154-12-31T23:59:59Z",
    "mshr_primaryfield": "000041 | 000000538 | 9/20/2012 08:14:27 pm",
    "_mshr_fk_worker_id_value": "00000d3c-0000-0000-d5ff-004105000000",
    "mshr_payrollworkeraddressentityid": "000006f0-0000-0000-f90f-014105000000"

}
```

## <a name="see-also"></a>Vedere anche

[Introduzione all'API di integrazione retribuzioni](hr-admin-integration-payroll-api-introduction.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
