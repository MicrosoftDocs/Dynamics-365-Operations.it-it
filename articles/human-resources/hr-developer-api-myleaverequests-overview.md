---
title: Panoramica di MyLeaveRequests
description: L'entità MyLeaveRequests in Microsoft Dynamics 365 Human Resources fornisce l'elenco delle richieste di congedo nel sistema, con ambito (limitato) alle richieste accessibili all'utente corrente che interroga l'entità.
author: andreabichsel
manager: tfehr
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 0ca5bc225400338e76faee41a279e91fc00ce570
ms.sourcegitcommit: 18e626c49ccfdb12c1484b985e3a275e51f61320
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2021
ms.locfileid: "5115538"
---
# <a name="myleaverequests-overview"></a>Panoramica di MyLeaveRequests

L'entità MyLeaveRequests in Microsoft Dynamics 365 Human Resources fornisce l'elenco delle richieste di congedo nel sistema, con ambito (limitato) alle richieste accessibili all'utente corrente che interroga l'entità.

## <a name="key"></a>Chiave

  | Nome proprietà | Tipo di dati |
  |---------------|-----------|
  | dataAreaId    | Stringa    |
  | RequestId     | Stringa    |
  | LeaveType     | Stringa    |
  | LeaveDate     | Data      |
  
## <a name="properties"></a>Proprietà

  | Nome proprietà     | Tipo di dati | Obbligatorio |
  |-------------------|-----------|----------|
  | dataAreaId        | Stringa    | X        |
  | RequestId         | Stringa    | X        |
  | LeaveType         | Stringa    | X        |
  | LeaveDate         | Data      | X        |
  | ReasonCodeId      | Stringa    |          |
  | PersonnelNumber   | Stringa    | X        |
  | RequestDate       | Data      | X        |
  | Commento           | Stringa    |          |
  | Stato            | Enumerazione      | X        |
  | Periodo            | Reale      |          |
  | HalfDayDefinition | Enumerazione      |          |

## <a name="actions"></a>Azioni

 | Nome azione                               | Descrizione                                     |
 |-------------------------------------------|-------------------------------------------------|
 | [Inoltra](hr-developer-api-myleaverequests-submit.md)   | Inoltrare la richiesta da elaborare per flusso di lavoro. |

## <a name="see-also"></a>Vedere anche

- [Inviare una richiesta di congedo a flusso di lavoro](hr-developer-api-myleaverequests-submit.md)
- [Autenticazione](hr-developer-api-authentication.md)