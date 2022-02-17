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
ms.openlocfilehash: da91084d30873b79033d789beab829da9fbdb010
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/31/2022
ms.locfileid: "8065548"
---
# <a name="completion-status"></a>Stato di completamento


[!INCLUDE [PEAP](../includes/peap-1.md)]

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
