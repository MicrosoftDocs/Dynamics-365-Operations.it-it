---
title: Stato della posizione della richiesta di selezione
description: Questo argomento descrive l'opzione Stato posizione richiesta di selezione impostata per Dynamics 365 Human Resources.
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
ms.openlocfilehash: 3f7bae64f58f0bdc1603b3c1b5493f1ebcfa8de9
ms.sourcegitcommit: 33b5c8bc4f9461e290513aa22de1ec1fba3b0742
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/05/2021
ms.locfileid: "5126052"
---
# <a name="recruiting-request-position-status"></a>Stato della posizione della richiesta di selezione

Questo argomento descrive l'opzione Stato posizione richiesta di selezione impostata per Dynamics 365 Human Resources.

Nome fisico: mshr_hcmrecruitingrequestpositionstatus

Questa enumerazione fornisce l'opzione impostata per i valori di stato di ciascuna posizione una richiesta di selezione nell'entità RecruitingRequestPosition.

| Valore | Etichetta | descrizione |
| --- | --- | --- |
| 200000000 | Scadenze aperte | La posizione nella richiesta di reclutamento è aperta alla selezione. Ciò non indica che non esiste un'assegnazione di posizione attualmente attiva per la posizione. Potrebbe esserci un dipendente nella posizione al momento dell'assunzione. Indica solo che la posizione è disponibile per la selezione nel contesto della richiesta di selezione. |
| 200000001 | Chiusa | È stato selezionato un lavoratore per l'assegnazione alla posizione. |
| 200000002 | Annullate | La richiesta di selezione per questa posizione è stata annullata. |

## <a name="see-also"></a>Vedere anche

[Introduzione all'API di integrazione del sistema di tracciabilità dei candidati](hr-admin-integration-ats-api-introduction.md)<br>
[Query di esempio per la richiesta di selezione](hr-admin-integration-ats-api-recruiting-request-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]