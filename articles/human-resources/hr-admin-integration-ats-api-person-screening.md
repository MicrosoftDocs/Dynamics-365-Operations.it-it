---
title: Screening persona
description: Questo argomento descrive l'entità Screening persona per Dynamics 365 Human Resources.
author: jaredha
manager: tfehr
ms.date: 02/05/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2021-02-05
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: d76bb57d85ee16f4faa0bb9cfec77047feb7df5f
ms.sourcegitcommit: 33b5c8bc4f9461e290513aa22de1ec1fba3b0742
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/05/2021
ms.locfileid: "5125379"
---
# <a name="person-screening"></a>Screening persona

Questo argomento descrive l'entità Screening persona per Dynamics 365 Human Resources.

Nome fisico: mshr_hcmpersonscreeningentity

## <a name="description"></a>descrizione

Questa entità descrive gli screening che un candidato ha superato o deve passare per un impiego.

## <a name="json-representation"></a>Rappresentazione JSON

```json
{
    "mshr_note": "String",
    "mshr_requiredby": "Date",
    "mshr_status": Int,
    "mshr_partynumber": "String",
    "mshr_screeningtypeid": "String",
    "mshr_primaryfield": "String",
    "_mshr_fk_person_id_value": "Guid",
    "mshr_hcmpersonscreeningentityid": "Guid",
    "mshr_completeddate": "Date"
}
```

## <a name="properties"></a>Proprietà

| Proprietà<br>**Nome fisico**<br>**_Tipo_** | Utilizza | descrizione |
| --- | --- | --- |
| **ID entità screening persona**<br>mshr_hcmpersonscreeningentityid<br>*GUID* | Sola lettura<br>Richiesto<br>Generato dal sistema | Identificatore primario univoco per il record di screening della persona. |
| **Numero parte**<br>mshr_partynumber<br>*String* | Lettura/scrittura<br>Richiesto | Il numero della parte (persona) associato al candidato. |
| **Valore ID persona**<br>_mshr_fk_person_id_value<br>*GUID* | Sola lettura<br>Richiesto<br>Chiave esterna: mshr_dirpersonentityid di mshr_dirpersonentity | L'identificatore generato dal sistema per il record dell'entità della parte (persona). |
| **ID tipo di screening**<br>mshr_screeningtypeid<br>*String* | Lettura/scrittura<br>Richiesto<br>Chiave esterna: ScreeningType | L'identificatore del tipo di screening definito in Human Resources. |
| **Valore ID tipo di screening**<br>_mshr_fk_screeningtype_id_value<br>*GUID* | Sola lettura<br>Richiesto<br>Chiave esterna: mshr_hcmscreeningtypeentityid di mshr_hcmscreeningtypeentity | Identificatore generato dal sistema per il record del tipo di screening dell'entità associata. |
| **Richiesto entro il**<br>mshr_requiredby<br>*Datetime* | Lettura/scrittura<br>Facoltativo | La data entro la quale lo screening deve essere completato. |
| **Stato**<br>mshr_status<br>*set di opzioni mshr_hcmcompletionstatus*<br>Lettura/scrittura<br>Richiesto | Fornisce lo stato del candidato per lo screening. |
| **Data di completamento**<br>mshr_completeddate<br>*Datetime* | Lettura/scrittura<br>Facoltativo | Data in cui lo screening è stato completato. |
| **Note**<br>mshr_note<br>*String* | Lettura/scrittura<br>Facoltativo | Note per l'utilizzo da parte di responsabili delle assunzioni e reclutatori. |

## <a name="see-also"></a>Vedere anche

[Introduzione all'API di integrazione del sistema di tracciabilità dei candidati](hr-admin-integration-ats-api-introduction.md)<br>
[Query di esempio per il candidato da assumere](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]