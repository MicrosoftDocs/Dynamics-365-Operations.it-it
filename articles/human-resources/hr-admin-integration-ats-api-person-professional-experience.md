---
title: Esperienza professionale persona
description: Questo argomento descrive l'entità Esperienza professionale persona per Dynamics 365 Human Resources.
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
ms.openlocfilehash: 1defaff8397c41feedbd85893766106338a28941
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5798059"
---
# <a name="person-professional-experience"></a>Esperienza professionale persona

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Questo argomento descrive l'entità Esperienza professionale persona per Dynamics 365 Human Resources.

Nome fisico: mshr_hcmpersonprofessionalexperienceentity

## <a name="description"></a>Descrizione

Questa entità descrive l'esperienza professionale o lo storico di lavoro di un candidato.

## <a name="json-representation"></a>Rappresentazione JSON

```json
{
    "mshr_partynumber": "String",
    "mshr_employerposition": "String",
    "mshr_startdate": "Date",
    "mshr_allowcontactemployer": Int,
    "mshr_employerlocation": "String",
    "mshr_employername": "String",
    "mshr_enddate": "Date",
    "mshr_note": "String",
    "mshr_phone": "String",
    "mshr_url": "String",
    "mshr_primaryfield": "String",
    "_mshr_fk_person_id_value": "Guid",
    "mshr_hcmpersonprofessionalexperienceentityid": "Guid"
}
```

## <a name="properties"></a>Proprietà

| Proprietà<br>**Nome fisico**<br>**_Tipo_** | Utilizza | Descrizione |
| --- | --- | --- |
| **ID entità esperienza professionale persona**<br>mshr_hcmpersonprofessionalexperienceentityid<br>*GUID* | Sola lettura<br>Richiesto | Identificatore univoco generato dal sistema per il record dell'entità. |
| **Numero parte**<br>mshr_partynumber<br>*String* | Lettura/scrittura<br>Richiesto | Identificatore univoco del record della persona per il candidato. |
| **Valore ID persona**<br>_mshr_fk_person_id_value<br>*GUID* | Sola lettura<br>Richiesto<br>Chiave esterna: mshr_dirpersonentityid di mshr_dirpersonentity | Identificatore univoco generato dal sistema per il record dell'entità della persona. |
| **Posizione del datore di lavoro**<br>mshr_employerposition<br>*String* | Lettura/scrittura<br>Richiesto | Il titolo della posizione ricoperta dal candidato durante l'assunzione. |
| **Nome datore di lavoro**<br>mshr_employername<br>*String* | Lettura/scrittura<br>Richiesto | Il nome del datore di lavoro. |
| **Posizione del datore di lavoro**<br>mshr_employerlocation<br>*String* | Lettura/scrittura<br>Facoltativo | L'ubicazione del datore di lavoro. Lunghezza massima: 60. Nessun formato specifico definito o richiesto. |
| **Telefono**<br>mshr_phone<br>*String* | Lettura/scrittura<br>Facoltativo | Il numero di telefono del datore di lavoro. |
| **URL**<br>mshr_url<br>*String* | Lettura/scrittura<br>Facoltativo | L'URL del sito Web del datore di lavoro. |
| **Data di inizio**<br>mshr_startdate<br>*Datetime* | Lettura/scrittura<br>Richiesto | La data di inizio dell'impiego del candidato. |
| **Data di fine**<br>mshr_enddate<br>*Datetime* | Lettura/scrittura<br>Facoltativo | La data di fine del rapporto di lavoro del candidato o null se il candidato è ancora impiegato qui. |
| **Consenti Contatta il datore di lavoro**<br>mshr_allowcontactemployer<br>*set di opzioni mshr_hrmblankyesno* | Lettura/scrittura<br>Facoltativo | Indica se il candidato consente di contattare il precedente datore di lavoro. |
| **Note**<br>mshr_note<br>*String* | Lettura/scrittura<br>Facoltativo | Note per l'utilizzo da parte del reclutatore o del responsabile delle assunzioni. |
| **Campo primario**<br>mshr_primaryfield<br>*String* | Sola lettura<br>Richiesto | Campo utilizzato come un identificatore principale del record dell'entità. Combinazione di numero del partito, data di inizio, posizione del datore di lavoro e nome del datore di lavoro. |

## <a name="see-also"></a>Vedere anche

[Introduzione all'API di integrazione del sistema di tracciabilità dei candidati](hr-admin-integration-ats-api-introduction.md)<br>
[Query di esempio per il candidato da assumere](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]