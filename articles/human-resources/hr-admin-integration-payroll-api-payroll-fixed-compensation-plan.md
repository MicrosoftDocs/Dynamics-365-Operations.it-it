---
title: Piano di retribuzione fissa retribuzioni
description: Questo argomento fornisce dettagli e una query di esempio per l'entità Piano di retribuzione fissa retribuzioni in Dynamics 365 Human Resources.
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
ms.openlocfilehash: 24f8af4d691c3085c36018c574fa3b917a3d6953
ms.sourcegitcommit: 89bb2a7f402deed32998eddc1e56e75250e3d15e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314215"
---
# <a name="payroll-fixed-compensation-plan"></a>Piano di retribuzione fissa retribuzioni

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Questo argomento descrive l'entità piano di retribuzione fissa retribuzioni per Dynamics 365 Human Resources.

### <a name="description"></a>descrizione

Questa entità fornisce il piano di retribuzione fissa assegnato per una determinata posizione di un dipendente.

Nome fisico: mshr_payrollfixedcompensationplanentity.

## <a name="properties"></a>Proprietà

| Proprietà<br>**Nome fisico**<br>**_Tipo_** | Utilizza | descrizione |
| --- | --- | --- |
| **ID dipendente**<br>mshr_fk_employee_id_value<br>*GUID* | Sola lettura<br>Richiesto<br>Chiave esterna: mshr_Employee_id of mshr_payrollemployeeentity entity  | ID dipendente |
| **Retribuzione**<br>mshr_payrate<br>*Decimali* | Sola lettura<br>Richiesto | La tariffa retributiva definita nel piano di retribuzione fissa. |
| **ID piano**<br>mshr_planid<br>*String* | Sola lettura<br>Richiesto |Specifica il piano di retribuzione.  |
| **Data di inizio validità**<br>mshr_validfrom<br>*Offset data/ora* |  Sola lettura<br>Richiesto |La data di inizio validità della retribuzione fissa del dipendente.  |
| **Entità piano di retribuzione fissa retribuzioni**<br>mshr_payrollfixedcompensationplanentityid<br>*GUID* | Richiesto<br>Generato dal sistema | Un valore GUID generato dal sistema per identificare in modo univoco il piano di retribuzione. |
| **Frequenza retribuzione**<br>mshr_payfrequency<br>*String* | Sola lettura<br>Richiesto |La frequenza alla quale verrà retribuito il dipendente.  |
| **Data di fine validità**<br>mshr_validto<br>*Offset data/ora* | Sola lettura <br>Richiesto | La data di fine validità della retribuzione fissa del dipendente. |
| **ID posizione**<br>mshr_positionid<br>*String* | Sola lettura <br>Richiesto | ID posizione associato al dipendente e l'iscrizione al piano di retribuzione fissa. |
| **Valuta**<br>mshr_currency<br>*String* | Sola lettura <br>Richiesto |La valuta definita per il piano di retribuzione fissa   |
| **Numero dipendente**<br>mshr_personnelnumber<br>*String* | Sola lettura<br>Richiesto |Il numero personale univoco del dipendente.  |

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
