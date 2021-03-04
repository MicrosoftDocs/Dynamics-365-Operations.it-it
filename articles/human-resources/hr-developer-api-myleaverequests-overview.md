---
title: Panoramica di MyLeaveRequests
description: L'entità MyLeaveRequests in Microsoft Dynamics 365 Human Resources fornisce l'elenco delle richieste di congedo nel sistema, con ambito (limitato) alle richieste accessibili all'utente corrente che interroga l'entità.
author: andreabichsel
manager: AnnBe
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
ms.openlocfilehash: 4bf3b298af9eb39e03514a4005afb43a42908e47
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4419129"
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

[!INCLUDE[footer-include](../includes/footer-banner.md)]