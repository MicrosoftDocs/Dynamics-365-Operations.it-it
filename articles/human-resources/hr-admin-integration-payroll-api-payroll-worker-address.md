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
ms.openlocfilehash: 1ff65a0518232275f7c5d0b4a70d04f77e4936c5
ms.sourcegitcommit: 89bb2a7f402deed32998eddc1e56e75250e3d15e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314115"
---
# <a name="payroll-worker-address"></a>Indirizzo lavoratore retribuzioni

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Questo argomento descrive l'entità indirizzo lavoratore Retribuzioni per Dynamics 365 Human Resources.

Nome fisico: mshr_payrollworkeraddressentity.

### <a name="description"></a>descrizione

Questa entità fornisce il luogo di residenza retribuzioni e il luogo di lavoro retribuzioni per un determinato dipendente.

## <a name="properties"></a>Proprietà

| Proprietà</br>**Nome fisico**</br>**_Tipo_** | Utilizza | descrizione |
| --- | --- | --- |
| **Città**</br>mshr_city</br>*String* | Sola lettura</br>Richiesto | La città definita per l'indirizzo.   |
| **Numero dipendente**</br>mshr_personnelnumber</br>*String* | Sola lettura</br>Richiesto | Il numero personale univoco del dipendente.  |
| **Paese**</br>mshr_countryregionid</br>*String* | Sola lettura</br>Richiesto | Il paese definito per l'indirizzo.  |
| **Data di inizio validità**</br>mshr_postaladdressvalidfrom</br>*Offset data/ora* | Sola lettura </br>Richiesto | La data di inizio validità dell'indirizzo. |
| **Indirizzo lavoro** </br> mshr_isworkedinaddressbr </br>*[set di opzioni mshr_NoYes](hr-admin-integration-payroll-api-no-yes.md)* | Sola lettura</br>Richiesto | Indica se l'indirizzo è dove lavora il dipendente. |
| **Regione**</br>mshr_county</br>*String* | Sola lettura</br>Richiesto | La regione definita per l'indirizzo.  |
| **ID Indirizzo lavoratore retribuzioni**</br>mshr_payrollworkeraddressentityid</br>*GUID* | Richiesto</br>Generato dal sistema | Un valore GUID generato dal sistema per identificare in modo univoco l'indirizzo.  |
| **Campo principale**</br>mshr_primaryfield</br>*String* | Sola lettura</br>Richiesto |  |
| **Via**</br>mshr_street</br>*String* | Sola lettura</br>Richiesto | La via definita per l'indirizzo. |
| **Data di fine validità**</br>mshr_postaladdressvalidto</br>*Offset data/ora* | Sola lettura </br>Richiesto | La data di fine validità dell'indirizzo.  |
| **ID ubicazione**</br>mshr_locationidbr>*String* | Sola lettura <br>Richiesto | L'ID dell'indirizzo.  |
| **CAP**</br>mshr_zipcode<br>*String* | Sola lettura <br>Richiesto |Il numero di identificazione definito per il dipendente.  |
| **Indirizzo domicilio**</br>mshr_islivedinaddressbr </br> *[set di opzioni mshr_NoYes](hr-admin-integration-payroll-api-no-yes.md)* | Sola lettura</br>Richiesto | Indica se l'indirizzo è dove vive il dipendente. |
| **Stato/regione**</br>mshr_state</br>*String* | Sola lettura</br>Richiesto | Lo stato definito per l'indirizzo.  |

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
