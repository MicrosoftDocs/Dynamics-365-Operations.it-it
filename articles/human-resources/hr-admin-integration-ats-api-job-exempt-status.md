---
title: Stato esenzione mansione
description: Questo articolo descrive il set di opzioni Stato esenzione mansione impostato per Dynamics 365 Human Resources.
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
ms.openlocfilehash: e59a71264d50cecce4d31dfa26ad7f05ef3f34e4
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8894674"
---
# <a name="job-exempt-status"></a>Stato esenzione mansione


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Questo articolo descrive il set di opzioni Stato esenzione mansione impostato per Dynamics 365 Human Resources.

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
