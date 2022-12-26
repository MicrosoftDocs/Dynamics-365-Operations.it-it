---
title: Certificato della persona
description: Questo articolo descrive l'entità Certificato della persona per Dynamics 365 Human Resources.
author: jaredha
ms.date: 12/15/2022
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
ms.openlocfilehash: 1f9d5a8c83d9714a4d10dec16e66ab87b794b074
ms.sourcegitcommit: 69d7dd6a2d0dc7f2661c7d1f61e8874c7bde1448
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/19/2022
ms.locfileid: "9887319"
---
# <a name="person-certificate"></a>Certificato della persona


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Questo articolo descrive l'entità Certificato della persona per Dynamics 365 Human Resources.

Nome fisico: mshr_hcmpersoncertificateentity

## <a name="description"></a>Descrizione

Questa entità descrive i certificati professionali di un candidato.

## <a name="json-representation"></a>Rappresentazione JSON

```json
{
    "mshr_certificatetypeid": "String",
    "mshr_startdate": "Date",
    "mshr_enddate": "Date",
    "mshr_notes": "String",
    "mshr_partynumber": "String",
    "mshr_primaryfield": "String",
    "_mshr_fk_certificatetype_id_value": "Guid",
    "_mshr_fk_person_id_value": "Guid",
    "mshr_hcmpersoncertificateentityid": "Guid"
}
```

## <a name="properties"></a>Proprietà

| Proprietà<br>**Nome fisico**<br>**_Tipo_** | Utilizza | Description |
| --- | --- | --- |
| **ID tipo di certificato**<br>mshr_certificatetypeid<br>*String* | Lettura/scrittura<br>Richiesto |  L'identificatore del tipo di certificato definito in Human Resources. |
| **Data di inizio**<br>mshr_startdate<br>*Datetime* | Lettura/scrittura<br>Richiesto | La data in cui è stato rilasciato il certificato. |
| **Data di fine**<br>mshr_enddate<br>*Datetime* | Lettura/scrittura<br>Facoltativo | La data in cui scadrà il certificato. |
| **Note**<br>mshr_notes<br>*String* | Lettura/scrittura<br>Facoltativo | Note per l'utilizzo da parte di responsabili delle assunzioni e reclutatori. |
| **Numero parte**<br>mshr_partynumber<br>*String* | Lettura/scrittura<br>Richiesto | L'ID della parte (persona) associata al candidato. |
| **Campo principale**<br>mshr_primaryfield<br>*String* | Sola lettura<br>Richiesto |  Campo da utilizzare come un identificatore principale del record dell'entità. Combinazione di numero di parte, ID tipo di certificato e data di inizio. |
| **Valore ID tipo di certificato**<br>_mshr_fk_certificatetype_id_value<br>*GUID* | Sola lettura<br>Richiesto<br>Chiave esterna: mshr_hcmcertificatetypeentityid di mshr_hcmcertificatetypeentity | Identificatore univoco generato dal sistema del tipo di certificato dell'entità associata. |
| **Valore ID persona**<br>_mshr_fk_person_id_value<br>*GUID* | Sola lettura<br>Richiesto<br>Chiave esterna: mshr_dirpersonentityid di mshr_dirpersonentity | L'identificatore generato dal sistema per il record dell'entità della parte (persona). |
| **ID entità certificato persona**<br>mshr_hcmpersoncertificateentityid<br>*GUID* | Sola lettura<br>Richiesto | Identificatore univoco generato dal sistema per il record dell'entità del certificato della persona. |




## <a name="see-also"></a>Vedere anche

[Introduzione all'API di integrazione del sistema di tracciabilità dei candidati](hr-admin-integration-ats-api-introduction.md)<br>
[Query di esempio per il candidato da assumere](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
