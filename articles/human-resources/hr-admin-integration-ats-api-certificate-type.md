---
title: Tipo di certificato
description: Questo argomento descrive l'entità Tipo di certificato per Dynamics 365 Human Resources.
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
ms.openlocfilehash: 1d2d53a628ef43d50bd83fd6b62807f44eddd653
ms.sourcegitcommit: 33b5c8bc4f9461e290513aa22de1ec1fba3b0742
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/05/2021
ms.locfileid: "5125715"
---
# <a name="certificate-type"></a>Tipo di certificato

Questo argomento descrive l'entità Tipo di certificato per Dynamics 365 Human Resources.

Nome fisico: mshr_hcmcertificatetypeentity

## <a name="description"></a>descrizione

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

| Proprietà<br>**Nome fisico**<br>**_Tipo_** | Utilizza | descrizione |
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