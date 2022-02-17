---
title: Tipi di screening
description: Questo argomento descrive l'entità Tipi di screening per Dynamics 365 Human Resources.
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
ms.openlocfilehash: bcbf22aac78f1ff96edb7dd927721453f8d10fa5
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/31/2022
ms.locfileid: "8067756"
---
# <a name="screening-types"></a>Tipi di screening


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Questo argomento descrive l'entità Tipi di screening per Dynamics 365 Human Resources.

Nome fisico: mshr_hcmscreeningtypeentity

## <a name="description"></a>Descrizione

Questa entità descrive i tipi di screening impostati dall'azienda per i processi preliminari all'impiego e di screening dei dipendenti in corso.

## <a name="json-representation"></a>Rappresentazione JSON

```json
{
    "mshr_description": "String",
    "mshr_frequencyunit": Int,
    "mshr_generatefrom": Int,
    "mshr_frequencyinterval": Int,
    "mshr_screeningtypeid": "String",
    "mshr_hcmscreeningtypeentityid": "Guid"
}
```

## <a name="properties"></a>Proprietà

| Proprietà<br>**Nome fisico**<br>**_Tipo_** | Utilizza | Descrizione |
| --- | --- | --- |
| **ID entità tipo di screening**<br>mshr_hcmscreeningtypeentityid<br>*GUID* | Sola lettura<br>Richiesto<br>Generato dal sistema | Identificatore primario univoco per il record del tipo di screening. |
| **ID tipo di screening**<br>mshr_screeningtypeid<br>*String* | Lettura/scrittura<br>Richiesto | Identificatore univoco definito dall'utente per il tipo di screening. |
| **Descrizione**<br>mshr_description<br>*String* | Lettura/scrittura<br>Richiesto | Descrizione del tipo di screening. |
| **Unità frequenza**<br>mshr_frequencyunit<br>*set di opzioni mshr_hcmfrequencyunit* | Lettura/scrittura<br>Richiesto | Descrive la frequenza con cui lo screening deve essere completato per la persona assegnata. |
| **Genera da**<br>mshr_generatefrom<br>*set di opzioni mshr_hcmfrequencygeneratefrom* | Lettura/scrittura<br>Richiesto | Se il valore Frequenza è un valore diverso da "Solo una volta", il valore GenerateFrom determina la data a partire dalla quale calcolare il successivo evento di screening. |
| **Intervallo di frequenza**<br>mshr_frequencyinterval<br>*Integer* | Lettura/scrittura<br>Richiesto | Se il valore Frequenza è un valore diverso da "Solo una volta", è necessario definire un intervallo per le unità di tempo tra ogni evento di screening. |

## <a name="see-also"></a>Vedere anche

[Introduzione all'API di integrazione del sistema di tracciabilità dei candidati](hr-admin-integration-ats-api-introduction.md)<br>
[Query di esempio per il candidato da assumere](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
