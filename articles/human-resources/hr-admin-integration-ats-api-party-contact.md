---
title: Contatto parte
description: Questo argomento descrive l'entità Contatto parte per Dynamics 365 Human Resources.
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
ms.openlocfilehash: 38f53d402ebe9f9f358281dd3996797a20923056
ms.sourcegitcommit: 33b5c8bc4f9461e290513aa22de1ec1fba3b0742
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/05/2021
ms.locfileid: "5125475"
---
# <a name="party-contact"></a>Contatto parte

Questo argomento descrive l'entità Contatto parte per Dynamics 365 Human Resources.

Nome fisico: mshr_dirpartycontactentities

## <a name="description"></a>descrizione

Questa entità descrive le informazioni di contatto del candidato, inclusi gli account di telefono, e-mail e social media.

## <a name="json-representation"></a>Rappresentazione JSON

```json
{
    "mshr_partynumber": "String",
    "mshr_locationid": "String",
    "mshr_description": "String",
    "mshr_type": Int,
    "mshr_countryregioncode": "String",
    "mshr_locator": "String",
    "mshr_locatorextension": "String",
    "mshr_purpose": "String",
    "mshr_ismobilephone": Int,
    "mshr_isinstantmessage": Int,
    "mshr_isprimary": Int,
    "mshr_isprivate": Int,
    "mshr_primaryfield": "String",
    "_mshr_fk_person_id_value": "String",
    "mshr_dirpartycontactentityid": "String"
}
```

## <a name="properties"></a>Proprietà

| Proprietà<br>**Nome fisico**<br>**_Tipo_** | Utilizza | descrizione |
| --- | --- | --- |
| **ID entità contatto della parte**<br>mshr_dirpartycontactentityid<br>*String* | Sola lettura<br>Richiesto | Identificatore univoco generato dal sistema per il record dell'entità. |
| **Numero parte**<br>mshr_partynumber<br>*String* | Lettura/scrittura<br>Richiesto | L'ID del record della parte associata (persona). |
| **Valore ID persona**<br>_mshr_fk_person_id_value<br>*GUID* | Sola lettura<br>Richiesto<br>Chiave esterna: mshr_dirpersonentityid di mshr_dirpersonentity | L'identificatore generato dal sistema per il record dell'entità della parte (persona). |
| **ID ubicazione**<br>mshr_locationid<br>*String* | Lettura/scrittura<br>Richiesto | L'ID posizione del record dell'indirizzo. Configurazione nell'entità mshr_logisticspostaladdresslocationcdsentity. |
| **Descrizione**<br>mshr_description<br>*String* | Lettura/scrittura<br>Richiesto | La descrizione dei dettagli di contatto. |
| **Tipo**<br>mshr_type<br>*Set di opzioni mshr_logisticselectronicaddressmethodtype* | Lettura/scrittura<br>Richiesto | Il tipo di dettagli del contatto. |
| **Codice paese/area geografica**<br>mshr_countryregioncode<br>*String* | Lettura/scrittura<br>Facoltativo | Paese dell'indirizzo. |
| **Localizzatore**<br>mshr_locator<br>*String* | Lettura/scrittura<br>Facoltativo | I dettagli di contatto. Ad esempio, se il tipo è **Indirizzo e-mail**, questo campo contiene l'indirizzo e-mail del candidato. |
| **Estensione del localizzatore**<br>mshr_locatorextension<br>*String* | Lettura/scrittura<br>Facoltativo | L'estensione del localizzatore. Ad esempio, se il tipo è **Telefono**, quindi questa proprietà conterrebbe l'estensione del numero di telefono. |
| **È mobile**<br>mshr_ismobile<br>*set di opzioni mshr_noyes* | Lettura/scrittura<br>Richiesto | Specifica se il telefono è un numero di telefono cellulare. |
| **È un messaggio istantaneo**<br>mshr_isinstantmessage<br>*set di opzioni mshr_noyes* | Lettura/scrittura<br>Richiesto | Specifica se il telefono è abilitato per la messaggistica istantanea. |
| **Primario**<br>mshr_isprimary<br>*set di opzioni mshr_noyes* | Lettura/scrittura<br>Richiesto | Determina il contatto primario del tipo di contatto. Deve essere presente un solo record principale per tipo di contatto. |
| **È privato**<br>mshr_isprivate<br>*set di opzioni mshr_noyes* | Lettura/scrittura<br>Richiesto | Identifica se questo indirizzo è un indirizzo privato per la persona. |
| **Scopo**<br>mshr_purpose<br>*String* | Lettura/scrittura<br>Facoltativo | Il ruolo o lo scopo dei dettagli di contatto. |
| **Campo principale**<br>mshr_primaryfield<br>*String* | Sola lettura<br>Richiesto | Campo utilizzato come un identificatore principale del record dell'entità. Combinazione di numero, tipo, descrizione e localizzatore della parte. |

## <a name="see-also"></a>Vedere anche

[Introduzione all'API di integrazione del sistema di tracciabilità dei candidati](hr-admin-integration-ats-api-introduction.md)<br>
[Query di esempio per il candidato da assumere](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)

