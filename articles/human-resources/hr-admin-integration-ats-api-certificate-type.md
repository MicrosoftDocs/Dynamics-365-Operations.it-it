---
title: Tipo di certificato
description: Questo articolo descrive l'entità Tipo di certificato per Dynamics 365 Human Resources.
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
ms.openlocfilehash: bfe7f06176098a504f8d2ad1c1431a6f60fe059c
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8886191"
---
# <a name="certificate-type"></a>Tipo di certificato


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Questo articolo descrive l'entità Tipo di certificato per Dynamics 365 Human Resources.

Nome fisico: mshr_hcmcertificatetypeentity

## <a name="description"></a>Descrizione

Questa entità definisce l'elenco dei tipi di certificati professionali impostati in Human Resources. L'entità non è specifica di una persona giuridica (società).

## <a name="json-representation"></a>Rappresentazione JSON

```json
{
    "mshr_certificatetype": "String",
    "mshr_description": "String",
    "mshr_requirerenewal": Int,
    "mshr_hcmcertificatetypeentityid": "Guid"
}
```

## <a name="properties"></a>Proprietà

| Proprietà<br>**Nome fisico**<br>**_Tipo_** | Utilizza | Descrizione |
| --- | --- | --- |
| **ID entità tipo certificato**<br>mshr_hcmcertificatetypeentityid<br>*GUID* | Sola lettura<br>Richiesto 
Generato dal sistema | Identificatore univoco principale per il tipo di certificato. |
| **Tipo di certificato**<br>mshr_certificatetype<br>*String* | Lettura/scrittura<br>Richiesto | Identificatore univoco leggibile dall'utente per il tipo di certificato. |
| **Descrizione**<br>mshr_description<br>*String* | Lettura/scrittura<br>Richiesto | Descrizione del tipo di certificato. |
| **Richiedi rinnovo**<br>mshr_requirerenewal<br>*set di opzioni mshr_noyes* | Lettura/scrittura<br>Facoltativo | Indica se è necessario il rinnovo del certificato. |

## <a name="see-also"></a>Vedere anche

[Introduzione all'API di integrazione del sistema di tracciabilità dei candidati](hr-admin-integration-ats-api-introduction.md)<br>
[Query di esempio per il candidato da assumere](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
