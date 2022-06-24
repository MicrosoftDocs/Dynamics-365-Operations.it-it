---
title: Stato della posizione della richiesta di selezione
description: Questo articolo descrive l'opzione Stato posizione richiesta di selezione impostata per Dynamics 365 Human Resources.
author: jaredha
ms.date: 02/05/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2021-02-05
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 736bdbfb8759ab61202d1f17e3cdc8294be0ba84
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8846416"
---
# <a name="recruiting-request-position-status"></a>Stato della posizione della richiesta di selezione


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Questo articolo descrive l'opzione Stato posizione richiesta di selezione impostata per Dynamics 365 Human Resources.

Nome fisico: mshr_hcmrecruitingrequestpositionstatus

Questa enumerazione fornisce l'opzione impostata per i valori di stato di ciascuna posizione una richiesta di selezione nell'entità RecruitingRequestPosition.

| Valore | Etichetta | Descrizione |
| --- | --- | --- |
| 200000000 | Scadenze aperte | La posizione nella richiesta di reclutamento è aperta alla selezione. Ciò non indica che non esiste un'assegnazione di posizione attualmente attiva per la posizione. Potrebbe esserci un dipendente nella posizione al momento dell'assunzione. Indica solo che la posizione è disponibile per la selezione nel contesto della richiesta di selezione. |
| 200000001 | Chiusa | È stato selezionato un lavoratore per l'assegnazione alla posizione. |
| 200000002 | Annullate | La richiesta di selezione per questa posizione è stata annullata. |

## <a name="see-also"></a>Vedere anche

[Introduzione all'API di integrazione del sistema di tracciabilità dei candidati](hr-admin-integration-ats-api-introduction.md)<br>
[Query di esempio per la richiesta di selezione](hr-admin-integration-ats-api-recruiting-request-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
