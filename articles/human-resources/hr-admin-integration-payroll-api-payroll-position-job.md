---
title: Mansione posizione di retribuzione
description: Questo argomento fornisce dettagli e una query di esempio per l'entità Mansione posizione di retribuzione in Dynamics 365 Human Resources.
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
ms.openlocfilehash: 62b9caf94f1c9aa8bb5758e62565fe57dfdd245a
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/18/2021
ms.locfileid: "6055030"
---
# <a name="payroll-position-job"></a>Mansione posizione di retribuzione

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Questo argomento fornisce dettagli e una query di esempio per l'entità Mansione posizione di retribuzione in Dynamics 365 Human Resources.

## <a name="properties"></a>Proprietà

| Proprietà<br>**Nome fisico**<br>**_Tipo_** | Utilizza | descrizione |
| --- | --- | --- |
| **ID lavoro**<br>mshr_jobid<br>*String* | Sola lettura<br>Richiesto |L'ID della mansione. |
| **Data di inizio validità**<br>mshr_validto<br>*Offset data/ora* | Sola lettura <br>Richiesto | La data di inizio validità della relazione tra posizione e mansione. |
| **Data di fine validità**<br>mshr_validto<br>*Offset data/ora* | Sola lettura <br>Richiesto | La data di fine validità della relazione tra posizione e mansione.  |
| **ID posizione**<br>mshr_positionid<br>*String* | Sola lettura<br>Richiesto | L'ID della posizione. |
| **Campo principale**<br>mshr_primaryfield<br>*String* | Richiesto<br>Generato dal sistema |  |
| **Valore ID mansione posizione**<br>_mshr_fk_positionjob_id_value<br>*GUID* | Sola lettura<br>Richiesto<br>Chiave esterna:mshr_PayrollPositionJobEntity of the mshr_payrollpositionjobentity |L'ID della mansione associata alla posizione.|
| **Valore ID piano di retribuzione fissa**<br>_mshr_fk_fixedcompplan_id_value<br>*GUID* | Sola lettura<br>Richiesto<br>Chiave esterna: mshr_FixedCompPlan_id of mshr_payrollfixedcompensationplanentity  | L'ID del piano di retribuzione fissa associato alla posizione. |
| **ID entità mansione posizione di retribuzione**<br>mshr_payrollpositionjobentityid<br>*GUID* | Richiesto<br>Generato dal sistema. | Un valore GUID generato dal sistema per identificare in modo univoco la mansione.  |

