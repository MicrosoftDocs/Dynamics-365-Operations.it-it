---
title: Stato esenzione mansione
description: Questo argomento descrive il set di opzioni Stato esenzione mansione impostato per Dynamics 365 Human Resources.
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
ms.openlocfilehash: 1c3996d8f693b6df0bf6230b25c9339b2aad1ceaf49a790fda90bbfc1b68be41
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6720446"
---
# <a name="job-exempt-status"></a>Stato esenzione mansione

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Questo argomento descrive il set di opzioni Stato esenzione mansione impostato per Dynamics 365 Human Resources.

Nome fisico: cdm_jobexemptstatus

Questa enumerazione descrive il set di opzioni per i valori relativi allo stato dell'esenzione mansione FLSA. Viene fornito nel set di opzioni cdm_jobexemptstatus esistente.

| Valore | Etichetta | Descrizione |
| --- | --- | --- |
| 200000000 | Esenzione | Il lavoro ha uno stato di esenzione in base alle linee guida FLSA. |
| 200000001 | NonExempt | Il lavoro ha uno stato di non esenzione in base alle linee guida FLSA. |
| 200000002 | Non applicabile | Le linee guida sullo stato FLSA non si applicano al lavoro. |

## <a name="see-also"></a>Vedere anche

[Introduzione all'API di integrazione del sistema di tracciabilità dei candidati](hr-admin-integration-ats-api-introduction.md)<br>
[Query di esempio per la richiesta di selezione](hr-admin-integration-ats-api-recruiting-request-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]