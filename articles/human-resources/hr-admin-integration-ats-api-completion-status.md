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
ms.openlocfilehash: 67e464262897d89f80bd615156d56cc12a822dd4a0dfa6d5eb206c38ddd61ec5
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6732875"
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