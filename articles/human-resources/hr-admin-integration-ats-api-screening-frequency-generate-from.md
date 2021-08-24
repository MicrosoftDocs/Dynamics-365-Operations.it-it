---
title: Frequenza di screening generata da
description: Questo argomento descrive la frequenza di screening generata dall'opzione impostata per Dynamics 365 Human Resources.
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
ms.openlocfilehash: 7b87bff6925721a20ad9d8bf92e64113d30333defd2d6708b445bcd2126e485a
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6766244"
---
# <a name="screening-frequency-generate-from"></a>Frequenza di screening generata da

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Questo argomento descrive la frequenza di screening generata dall'opzione impostata per Dynamics 365 Human Resources.

Nome fisico: mshr_hcmfrequencygeneratefrom

Questa enumerazione fornisce il set di opzioni di valori per determinare la data di inizio del calcolo per il successivo screening richiesto.

| Valore | Etichetta | Descrizione |
| --- | --- | --- |
| 200000000 non selezionato | Non è stato selezionato alcun valore. |
| 200000001 Data di completamento | Il calcolo viene eseguito dall'ultima data di screening completata. |
| 200000002 data richiesta | Il calcolo viene eseguito dall'ultima data di screening necessaria. |

## <a name="see-also"></a>Vedere anche

[Introduzione all'API di integrazione del sistema di tracciabilità dei candidati](hr-admin-integration-ats-api-introduction.md)<br>
[Query di esempio per il candidato da assumere](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]