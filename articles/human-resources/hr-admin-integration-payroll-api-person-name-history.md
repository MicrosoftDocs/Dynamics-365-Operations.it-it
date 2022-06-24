---
title: Storico nome della persona
description: Questo articolo fornisce dettagli e una query di esempio per l'entità Storico nomi della persona in Dynamics 365 Human Resources.
author: twheeloc
ms.date: 09/01/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: e34b0d7bebd1c4037347161087ff3a4485a58878
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8875773"
---
# <a name="person-name-history"></a>Storico nome della persona


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Questo articolo descrive l'entità Storico nomi della persona in Dynamics 365 Human Resources.

Nome fisico: mshr_dirpersonnamehistoricalentity.

### <a name="description"></a>Descrizione

Questa entità fornisce informazioni sullo storico nomi per una determinata persona.

> [!IMPORTANT] 
> I campi **FirstName**, **MiddleName**, **LastName**, **NameValidFrom**, e **NameValidTo** non saranno più disponibili nell'entità Dipendente retribuzioni. Sono stati rimossi per garantire che una sola origine dati della data di validità supporti questa entità.

## <a name="properties"></a>Proprietà

| Proprietà</br>**Nome fisico**</br>**_Tipo_** | Utilizza | Descrizione |
| --- | --- | --- |
| **Nome**</br>mshr_firstname</br>*String* | Sola lettura | Nome. |
| **Prefisso cognome**</br>mshr_lastnameprefix</br>*Stringa*) | Sola lettura | Prefisso cognome. |
| **Cognome**</br>mshr_lastname</br>*Stringa*) | Sola lettura | Cognome. |
| **Secondo nome**</br>mshr_middlename</br>*Stringa*) | Sola lettura | Secondo nome. |
| **Data di fine validità**</br>mshr_validto</br>*Stringa*) | Sola lettura | La data di fine validità del nome. |
| **Numero parte**</br>mshr_partynumber</br>*String* | Sola lettura | Un identificatore univoco generato dal sistema leggibile dall'utente per il record della persona. |
| **Campo principale**</br>mshr_primaryfield</br>*String* | Sola lettura | Identificatore univoco del record. |
| **ID entità Storico nomi persona**</br>mshr_dirpersonnamehistoricalentityid</br>*GUID* | Generato dal sistema | Un valore dell'identificatore univoco globale (GUID) generato dal sistema per identificare il record in modo univoco. |

## <a name="relations"></a>Relazioni

| Valore proprietà | Entità correlata | Proprietà di navigazione | Tipo di raccolta |
| --- | --- | --- | --- |
| Non applicabile | [mshr_payrollemployeeentity](hr-admin-integration-payroll-api-payroll-employee.md) | Non applicabile | mshr_FK_PayrollEmployeeEntity_Name |

## <a name="example-query-for-payroll-employee"></a>Query di esempio per Dipendente retribuzioni

**Richiesta**

```http
GET [Organizaton URI]/api/data/v9.1/mshr_dirpersonnamehistoricalentities?$filter=mshr_partynumber eq 'HR000001606'
```

**Risposta**

```json
{
    "mshr_firstname": "Agustina",
    "mshr_lastnameprefix": "",
    "mshr_lastname": "Fierro",
    "mshr_middlename": "middle",
    "mshr_validto": "2021-09-10T21:23:53Z",
    "mshr_partynumber": "HR000001606",
    "mshr_primaryfield": "HR000001606 | ",
    "mshr_dirpersonnamehistoricalentityid": "00000832-0000-0000-c12b-014105000000",
    "mshr_validfrom": null
},
{
    "mshr_firstname": "Agustina",
    "mshr_lastnameprefix": "",
    "mshr_lastname": "Fierro",
    "mshr_middlename": "",
    "mshr_validto": "2154-12-31T23:59:59Z",
    "mshr_partynumber": "HR000001606",
    "mshr_primaryfield": "HR000001606 | 9/10/2021 09:23:54 pm",
    "mshr_dirpersonnamehistoricalentityid": "00000832-0000-0000-d20b-000010000000",
    "mshr_validfrom": "2021-09-10T21:23:54Z"
}
```

## <a name="see-also"></a>Vedere anche

[Introduzione all'API di integrazione retribuzioni](hr-admin-integration-payroll-api-introduction.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
