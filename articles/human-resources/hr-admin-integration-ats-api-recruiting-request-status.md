---
title: Stato della richiesta di selezione
description: Questo argomento descrive l'opzione Stato richiesta di selezione impostata per Dynamics 365 Human Resources.
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
ms.openlocfilehash: 55ed9c391a1b5f86c3c443b9fceeee5c2301444d
ms.sourcegitcommit: 33b5c8bc4f9461e290513aa22de1ec1fba3b0742
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/05/2021
ms.locfileid: "5125956"
---
# <a name="recruiting-request-status"></a>Stato della richiesta di selezione

Questo argomento descrive l'opzione Stato richiesta di selezione impostata per Dynamics 365 Human Resources.

Nome fisico: mshr_hcmrecruitingrequeststatus

Questa enumerazione fornisce il set di opzioni per i valori di stato per la richiesta di selezione.

| Valore | Etichetta | descrizione |
| --- | --- | --- |
| 200000000 | Bozze | La richiesta è in bozza e non è pronta per la selezione attiva. |
| 200000001 | In revisione | La richiesta è stata inviata e viene instradata per l'approvazione dal flusso di lavoro. Disponibile solo quando il flusso di lavoro è abilitato. |
| 200000002 | In sospeso | La richiesta è in attesa di azione del flusso di lavoro. Disponibile solo quando il flusso di lavoro è abilitato. |
| 200000003 | Annullate | La richiesta è stata annullata. Disponibile solo quando il flusso di lavoro è abilitato. |
| 200000004 | Negate | La richiesta è stata rifiutata. Disponibile solo quando il flusso di lavoro è abilitato. |
| 200000005 | Attive | Qualsiasi flusso di lavoro viene completato e approvato e la richiesta è pronta per la selezione attiva. |
| 200000006 | Chiuse | La richiesta di selezione è chiusa. |

## <a name="see-also"></a>Vedere anche

[Introduzione all'API di integrazione del sistema di tracciabilità dei candidati](hr-admin-integration-ats-api-introduction.md)<br>
[Query di esempio per la richiesta di selezione](hr-admin-integration-ats-api-recruiting-request-example-query.md)
