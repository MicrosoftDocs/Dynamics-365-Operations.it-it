---
title: Stato esenzione mansione
description: Questo argomento descrive il set di opzioni Stato esenzione mansione impostato per Dynamics 365 Human Resources.
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
ms.openlocfilehash: 0cd6ffc01793c8ff12e36175c7c9feaf8a4b3cdf
ms.sourcegitcommit: 33b5c8bc4f9461e290513aa22de1ec1fba3b0742
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/05/2021
ms.locfileid: "5125571"
---
# <a name="job-exempt-status"></a>Stato esenzione mansione

Questo argomento descrive il set di opzioni Stato esenzione mansione impostato per Dynamics 365 Human Resources.

Nome fisico: cdm_jobexemptstatus

Questa enumerazione descrive il set di opzioni per i valori relativi allo stato dell'esenzione mansione FLSA. Viene fornito nel set di opzioni cdm_jobexemptstatus esistente.

| Valore | Etichetta | descrizione |
| --- | --- | --- |
| 200000000 | Esenzione | Il lavoro ha uno stato di esenzione in base alle linee guida FLSA. |
| 200000001 | NonExempt | Il lavoro ha uno stato di non esenzione in base alle linee guida FLSA. |
| 200000002 | Non applicabile | Le linee guida sullo stato FLSA non si applicano al lavoro. |

## <a name="see-also"></a>Vedere anche

[Introduzione all'API di integrazione del sistema di tracciabilità dei candidati](hr-admin-integration-ats-api-introduction.md)<br>
[Query di esempio per la richiesta di selezione](hr-admin-integration-ats-api-recruiting-request-example-query.md)
