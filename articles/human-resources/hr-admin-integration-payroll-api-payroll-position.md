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
ms.openlocfilehash: 05e9d6441cf99dce3f4663b9d5ba57e2b386e8c2f3060f75550270083f3b98b3
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6741455"
---
# <a name="payroll-position"></a>Posizione di retribuzione

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Questo argomento descrive l'entità Posizioni Retribuzioni in Dynamics 365 Human Resources.

Nome fisico: mshr_payrollpositionentity.

### <a name="description"></a>descrizione

Questa entità fornisce informazioni correlate alla posizione per un determinato dipendente.

Nome fisico: 

## <a name="properties"></a>Proprietà

| Proprietà<br>**Nome fisico**<br>**_Tipo_** | Utilizza | descrizione |
| --- | --- | --- |
| **Ore regolari annuali**<br>annualregularhours<br>*Decimali* | Sola lettura<br>Richiesto | Ore regolari annuali definite per la posizione.  |
| **ID entità dettagli posizione di retribuzione**<br>payrollpositiondetailsentityid<br>*GUID* | Richiesto<br>Generato dal sistema. | Un valore GUID generato dal sistema per identificare in modo univoco la posizione.  |
| **Campo principale**<br>mshr_primaryfield<br>*String* | Richiesto<br>Generato dal sistema |  |
| **Valore ID mansione posizione**<br>_mshr_fk_positionjob_id_value<br>*GUID* | Sola lettura<br>Richiesto<br>Chiave esterna:mshr_PayrollPositionJobEntity of the mshr_payrollpositionjobentity |L'ID della mansione associata alla posizione.|
| **Valore ID piano di retribuzione fissa**<br>_mshr_fk_fixedcompplan_id_value<br>*GUID* | Sola lettura<br>Richiesto<br>Chiave esterna: mshr_FixedCompPlan_id of mshr_payrollfixedcompensationplanentity  | L'ID del piano di retribuzione fissa associato alla posizione. |
| **ID ciclo retributivo**<br>mshr_primaryfield<br>*String* | Sola lettura<br>Richiesto | Il ciclo retributivo definito per la posizione. |
| **Pagamento in base alla persona giuridica**<br>paidbylegalentity<br>*String* | Sola lettura<br>Richiesto | La persona giuridica definita nella posizione responsabile dell'emissione del pagamento. |
| **ID posizione**<br>mshr_positionid<br>*String* | Sola lettura<br>Richiesto | L'ID della posizione. |
| **Data di fine validità**<br>validto<br>*Offset data/ora* | Sola lettura<br>Richiesto |La data di inizio validità dei dettagli della posizione.  |
| **Data di inizio validità**<br>validfrom<br>*Offset data/ora* | Sola lettura<br>Richiesto |La data di fine validità dei dettagli della posizione.  |

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
