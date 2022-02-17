---
title: Panoramica di MyLeaveRequests
description: L'entità MyLeaveRequests in Microsoft Dynamics 365 Human Resources fornisce l'elenco delle richieste di congedo nel sistema, con ambito (limitato) alle richieste accessibili all'utente corrente che interroga l'entità.
author: andreabichsel
ms.date: 02/03/2020
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 41ef8c6fc0e896e7f2cefd94801abab610083b81
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/31/2022
ms.locfileid: "8070857"
---
# <a name="myleaverequests-overview"></a>Panoramica di MyLeaveRequests


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

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

[!INCLUDE[footer-include](../includes/footer-banner.md)]
