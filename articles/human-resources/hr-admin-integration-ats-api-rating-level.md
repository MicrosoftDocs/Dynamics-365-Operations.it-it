---
title: Livello di valutazione
description: Questo argomento descrive l'entità Livello di valutazione per Dynamics 365 Human Resources.
author: jaredha
ms.date: 02/05/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2021-02-05
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: eac80599de07a045aa233f1cdfd16fe0db8733a2
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5800335"
---
# <a name="rating-level"></a>Livello di valutazione

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Questo argomento descrive l'entità Livello di valutazione per Dynamics 365 Human Resources.

Nome fisico: mshr_hcmratinglevelentity

## <a name="description"></a>Descrizione

Questa entità fornisce i livelli di valutazione disponibili per le competenze. I livelli di valutazione si applicano a tutte le persone giuridiche.

## <a name="json-representation"></a>Rappresentazione JSON

```json
{
    "mshr_description": "String",
    "mshr_factor": Int,
    "mshr_note": "String",
    "mshr_ratinglevelid": "String",
    "mshr_ratingmodelid": "String",
    "mshr_primaryfield": "String",
    "_mshr_fk_ratingmodelentity_id_value": "Guid",
    "mshr_hcmratinglevelentityid": "Guid"
}
```

## <a name="properties"></a>Proprietà

| Proprietà<br>**Nome fisico**<br>**_Tipo_** | Utilizza | Descrizione |
| --- | --- | --- |
| **ID entità livello di valutazione**<br>mshr_hcmratinglevelentityid<br>*GUID* | Sola lettura<br>Richiesto<br>Generato dal sistema | L'identificatore univoco generato dal sistema per il livello. |
| **ID livello valutazione**<br>mshr_ratinglevelid<br>*String* | Lettura/scrittura<br>Richiesto | Identificatore univoco leggibile dall'utente per il livello. |
| **ID modello di valutazione**<br>mshr_ratingmodelid<br>*String* | Lettura/scrittura<br>Richiesto | Il modello di valutazione a cui appartiene il livello di valutazione. |
| **ID entità modello di valutazione**<br>_mshr_fk_ratingmodelentity_id_value<br>*GUID* | Sola lettura<br>Richiesto<br>Chiave esterna: mshr_hcmratingmodelentityid di mshr_hcmratingmodelentity | L'identificatore generato dal sistema per il modello di valutazione a cui appartiene il livello di valutazione. |
| **Descrizione**<br>mshr_description<br>*String* | Lettura/scrittura<br>Richiesto | La descrizione del livello di valutazione. |
| **Fattore**<br>mshr_factor<br>*Integer* | Lettura/scrittura<br>Richiesto | Il fattore per il livello di valutazione. Quando si confrontano gli articoli con un numero di livelli di valutazione diversi, il fattore viene utilizzato per normalizzare i punteggi. Il valore deve essere un numero intero compreso tra 0 e 9. |
| **Nota**<br>mshr_note<br>*String* | Lettura/scrittura<br>Facoltativo | Eventuali note associate al livello di valutazione. |
| **Campo principale**<br>mshr_primaryfield<br>*String* | Sola lettura<br>Richiesto | Campo da utilizzare come un identificatore principale del record dell'entità. Combinazione di ID livello di valutazione e ID modello di valutazione. |

## <a name="see-also"></a>Vedere anche

[Introduzione all'API di integrazione del sistema di tracciabilità dei candidati](hr-admin-integration-ats-api-introduction.md)<br>
[Query di esempio per il candidato da assumere](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]