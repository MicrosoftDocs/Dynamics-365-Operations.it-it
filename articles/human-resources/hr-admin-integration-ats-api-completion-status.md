---
title: Stato di completamento
description: Questo argomento descrive il set di opzioni Stato di completamento impostato per Dynamics 365 Human Resources.
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
ms.openlocfilehash: 54ad5cc8f5f18d57b6713304cceb985acfdc93d1
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/18/2021
ms.locfileid: "6055366"
---
# <a name="completion-status"></a>Stato di completamento

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Questo argomento descrive il set di opzioni Stato di completamento impostato per Dynamics 365 Human Resources.

Nome fisico: mshr_hcmcompletionstatus

Questa enumerazione fornisce il set di opzioni dei valori di stato per gli screening dei candidati. 

| Valore | Etichetta | Descrizione |
| --- | --- | --- |
| 200000000 | Non completato | Il candidato non ha ancora completato lo screening. |
| 200000001 | Superato | Il candidato ha superato lo screening. |
| 200000002 | Errore | Il candidato non ha superato lo screening. |

## <a name="see-also"></a>Vedere anche

[Introduzione all'API di integrazione del sistema di tracciabilità dei candidati](hr-admin-integration-ats-api-introduction.md)<br>
[Query di esempio per il candidato da assumere](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]