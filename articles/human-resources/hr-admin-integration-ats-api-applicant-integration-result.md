---
title: Risultati integrazione candidato
description: Questo argomento descrive l'opzione Risultato integrazione richiedente impostata per Dynamics 365 Human Resources.
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
ms.openlocfilehash: 157864cd0eee879013724615ce31306c99c5aa68
ms.sourcegitcommit: 33b5c8bc4f9461e290513aa22de1ec1fba3b0742
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/05/2021
ms.locfileid: "5125811"
---
# <a name="applicant-integration-result"></a>Risultati integrazione candidato

Questo argomento descrive l'opzione Risultato integrazione richiedente impostata per Dynamics 365 Human Resources.

Nome fisico: mshr_hcmapplicantintegrationresult

Questa enumerazione fornisce lo stato di un record candidato.

| Valore | Etichetta | descrizione |
| --- | --- | --- |
| 200000000 | Non elaborato | Il candidato è ancora allo studio. |
| 200000001 | Assunto | Il candidato è stato assunto. |
| 200000002 | Non assunto | È stata presa la decisione di non assumere il candidato. |
| 200000003 | Chiuso | Il candidato non viene più tenuto in considerazione. |

## <a name="see-also"></a>Vedere anche

[Introduzione all'API di integrazione del sistema di tracciabilità dei candidati](hr-admin-integration-ats-api-introduction.md)<br>
[Query di esempio per il candidato da assumere](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)
