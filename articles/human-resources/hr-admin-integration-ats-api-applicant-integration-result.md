---
title: Risultati integrazione candidato
description: Questo argomento descrive l'opzione Risultato integrazione richiedente impostata per Dynamics 365 Human Resources.
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
ms.openlocfilehash: 3f173e15d5524dfd4d63113760760b2534cc8769456df621415a11e4053cc6fb
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6725916"
---
# <a name="applicant-integration-result"></a>Risultati integrazione candidato

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Questo argomento descrive l'opzione Risultato integrazione richiedente impostata per Dynamics 365 Human Resources.

Nome fisico: mshr_hcmapplicantintegrationresult

Questa enumerazione fornisce lo stato di un record candidato.

| Valore | Etichetta | Descrizione |
| --- | --- | --- |
| 200000000 | Non elaborato | Il candidato è ancora allo studio. |
| 200000001 | Assunto | Il candidato è stato assunto. |
| 200000002 | Non assunto | È stata presa la decisione di non assumere il candidato. |
| 200000003 | Chiuso | Il candidato non viene più tenuto in considerazione. |

## <a name="see-also"></a>Vedere anche

[Introduzione all'API di integrazione del sistema di tracciabilità dei candidati](hr-admin-integration-ats-api-introduction.md)<br>
[Query di esempio per il candidato da assumere](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]