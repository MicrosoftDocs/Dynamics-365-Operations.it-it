---
title: Persona
description: Questo argomento descrive l'entità Persona per Dynamics 365 Human Resources.
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
ms.openlocfilehash: a13222317ba59868686be5ce24c970d6a068f8bc
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/17/2021
ms.locfileid: "5464180"
---
# <a name="person"></a>Persona

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Questo argomento descrive l'entità Persona per Dynamics 365 Human Resources.

Nome fisico: mshr_dirpersonentity

### <a name="description"></a>Descrizione

Questa entità fornisce le informazioni personali per l'individuo che è il candidato.

## <a name="json-representation"></a>Rappresentazione JSON

```json
{
    "mshr_partynumber": "String",
    "mshr_name": "String",
    "mshr_namealias": "String",
    "mshr_knownas": "String",
    "mshr_languageid": "String",
    "mshr_addressbooks": "String",
    "mshr_anniversaryday": Int,
    "mshr_anniversarymonth": Int,
    "mshr_anniversaryyear": Int,
    "mshr_birthday": Int,
    "mshr_birthmonth": Int,
    "mshr_birthyear": Int,
    "mshr_childrennames": "String",
    "mshr_gender": Int,
    "mshr_hobbies": "String",
    "mshr_initials": "String",
    "mshr_maritalstatus": Int,
    "mshr_phoneticfirstname": "String",
    "mshr_phoneticlastname": "String",
    "mshr_phoneticmiddlename": "String",
    "mshr_personalsuffix": "String",
    "mshr_personaltitle": "String",
    "mshr_professionalsuffix": "String",
    "mshr_professionaltitle": "String",
    "mshr_fullprimaryaddress": "String",
    "mshr_addresscity": "String",
    "mshr_addresscountryregionid": "String",
    "mshr_addresscountryregionisocode": "String",
    "mshr_addresscounty": "String",
    "mshr_addressdistrictname": "String",
    "mshr_addresslatitude": Decimal,
    "mshr_addresslocationid": "000003212",
    "mshr_addresslocationroles": "Home",
    "mshr_addresslongitude": Decimal,
    "mshr_addressstate": "String",
    "mshr_addressstreet": "String",
    "mshr_addressvalidfrom": "Date",
    "mshr_addressvalidto": "Date",
    "mshr_addresszipcode": "String",
    "mshr_addressisprivate": Int,
    "mshr_addressdescription": "String",
    "mshr_primarycontactemail": "String",
    "mshr_primarycontactemaildescription": "String",
    "mshr_primarycontactemailisim": Int,
    "mshr_primarycontactemailpurpose": "String",
    "mshr_primarycontactfax": "String",
    "mshr_primarycontactfaxdescription": "String",
    "mshr_primarycontactfaxextension": "String",
    "mshr_primarycontactfaxpurpose": "String",
    "mshr_primarycontactphone": "String",
    "mshr_primarycontactphonedescription": "String",
    "mshr_primarycontactphoneextension": "String",
    "mshr_primarycontactphoneismobile": Int,
    "mshr_primarycontactphonepurpose": "String",
    "mshr_primarycontacttelex": "String",
    "mshr_primarycontacttelexdescription": "String",
    "mshr_primarycontacttelexpurpose": "String",
    "mshr_primarycontacturl": "String",
    "mshr_primarycontacturldescription": "String",
    "mshr_primarycontacturlpurpose": "String",
    "mshr_primarycontactfacebook": "String",
    "mshr_primarycontactfacebookdescription": "String",
    "mshr_primarycontactfacebookisprivate": Int,
    "mshr_primarycontactfacebookpurpose": "String",
    "mshr_primarycontactlinkedin": "String",
    "mshr_primarycontactlinkedindescription": "String",
    "mshr_primarycontactlinkedinisprivate": Int,
    "mshr_primarycontactlinkedinpurpose": "String",
    "mshr_primarycontacttwitter": "String",
    "mshr_primarycontacttwitterdescription": "String",
    "mshr_primarycontacttwitterisprivate": Int,
    "mshr_primarycontacttwitterpurpose": "String",
    "mshr_partytype": "String",
    "mshr_namesequencedisplayas": "String",
    "mshr_firstname": "String",
    "mshr_lastnameprefix": "String",
    "mshr_lastname": "String",
    "mshr_middlename": "String",
    "mshr_electroniclocationid": "String",
    "mshr_dirpersonentityid": "Guid",
    "mshr_addresstimezone": Int
}
```

## <a name="properties"></a>Proprietà

| Proprietà<br>**Nome fisico**<br>**_Tipo_** | Utilizza | Descrizione |
| --- | --- | --- |
| **ID entità persona**<br>mshr_dirpersonentityid<br>*GUID* | Sola lettura<br>Richiesto<br>Generato dal sistema | Un identificatore univoco generato dal sistema per il record dell'entità. |
| **Numero parte**<br>mshr_partynumber<br>*String* | Sola lettura<br>Richiesto<br>Generato dal sistema | Un identificatore univoco generato dal sistema leggibile dall'utente per il record della persona.  |
| **Nome**<br>mshr_name<br>*String* | Sola lettura<br>Richiesto | Il valore del campo è una concatenazione di Nome, Secondo nome, Prefisso del cognome e Cognome nell'ordine definito nel campo **Visualizza sequenza nomi come**. |
| **Alias nomi**<br>mshr_namealias<br>*String* | Lettura/scrittura<br>Facoltativo | Un alias dei nomi che può essere fornito per la persona. |
| **Nome noto**<br>mshr_knownas<br>*String* | Lettura/scrittura<br>Facoltativo | Un nome che può essere utilizzato per la persona se generalmente nota con un altro nome. |
| **ID lingua**<br>mshr_languageid<br>*String* | Lettura/scrittura<br>Facoltativo | L'ID lingua della lingua principale della persona, come definito nel formato ISO 639-1. |
| **Rubriche**<br>mshr_addressbooks<br>*String* | Lettura/scrittura<br>Facoltativo | Rubrica a cui la persona può essere assegnata. Le rubriche che sono state impostate per l'organizzazione sono elencate nell'entità mshr_diraddressbooksentity. |
| **Giorno di anniversario**<br>mshr_anniversaryday<br>*Int* | Lettura/scrittura<br>Facoltativo | Il giorno della data dell'anniversario della persona. |
| **Mese di anniversario**<br>mshr_anniversarymonth<br>*set di opzioni mshr_monthsofyear* | Lettura/scrittura<br>Facoltativo | Il mese della data dell'anniversario della persona. |
| **Anno di anniversario**<br>mshr_anniversaryyear<br>*Int* | Lettura/scrittura<br>Facoltativo | L'anno della data dell'anniversario della persona. |
| **Giorno di nascita**<br>mshr_birthday<br>*Int* | Lettura/scrittura<br>Facoltativo | Il giorno della data del compleanno della persona. |
| **Mese di nascita**<br>mshr_birthmonth<br>*set di opzioni mshr_monthsofyear* | Lettura/scrittura<br>Facoltativo | Il mese della data del compleanno della persona. |
| **Anno di nascita**<br>mshr_birthyear<br>*Int* | Lettura/scrittura<br>Facoltativo | L'anno della data del compleanno della persona. |
| **Nomi di bambini**<br>mshr_childrennames<br>*String* | Lettura/scrittura<br>Facoltativo | Stringa per i nomi dei figli della persona. Non esistono delimitazioni. |
| **Genere**<br>mshr_gender<br>*set di opzioni mshr_hcmpersongender* | Lettura/scrittura<br>Facoltativo | Il genere della persona. |
| **Hobby**<br>mshr_hobbies<br>*String* | Lettura/scrittura<br>Facoltativo | Gli hobby del contatto. |
| **Iniziali**<br>mshr_initials<br>*String* | Lettura/scrittura<br>Facoltativo | Le iniziali del nome della persona. |
| **Stato civile**<br>mshr_maritalstatus<br>*set di opzioni mshr_hcmpersonmaritalstatus* | Lettura/scrittura<br>Facoltativo | Lo stato civile della persona. |
| **Nome fonetico**<br>mshr_phoneticfirstname<br>*String* | Lettura/scrittura<br>Facoltativo | La pronuncia fonetica del nome della persona. |
| **Cognome fonetico**<br>mshr_phoneticlastname<br>*String* | Lettura/scrittura<br>Facoltativo | La pronuncia fonetica del cognome della persona. |
| **Secondo nome fonetico**<br>mshr_phoneticmiddlename<br>*String* | Lettura/scrittura<br>Facoltativo | La pronuncia fonetica del cognome della persona. |
| **Suffisso personale**<br>mshr_personalsuffix<br>*String* | Lettura/scrittura<br>Facoltativo | Il suffisso personale della persona. Valori validi nell'entità mshr_dirnameaffixentity dove mshr_type è Suffisso (200000001). |
| **Posizione personale**<br>mshr_personaltitle<br>*String* | Lettura/scrittura<br>Facoltativo | La posizione personale della persona. Valori validi nell'entità mshr_dirnameaffixentity dove mshr_type è Posizione (200000000).
| **Suffisso professione**<br>mshr_professionalsuffix<br>*String* | Lettura/scrittura<br>Facoltativo | Un suffisso professionale. |
| **Posizione professionale**<br>mshr_professionaltitle<br>*String* | Lettura/scrittura<br>Facoltativo | Una posizione professionale. |
| **Indirizzo principale completo**<br>mshr_fullprimaryaddress<br>*String* | Lettura/scrittura<br>Facoltativo | L'indirizzo principale completo della persona, una concatenazione di campi dell'indirizzo principale. |
| **Città indirizzo**<br>mshr_addresscity<br>*String* | Lettura/scrittura<br>Facoltativo | La città dell'indirizzo principale della persona. Impostalo nell'entità mshr_logisticsaddresscityentity. |
| **Indirizzo Paese Area**<br>mshr_addresscountryregionid<br>*String* | Lettura/scrittura<br>Facoltativo | Il paese/area geografica dell'indirizzo principale della persona. Valori validi nell'entità mshr_logisticsaddresscountryregionentity. |
| **Codice ISO Indirizzo Paese Area**<br>mshr_addresscountryregionisocode<br>*String* | Lettura/scrittura<br>Facoltativo | Il codice ISO del paese/area geografica dell'indirizzo principale della persona. |
| **Indirizzo Paese**<br>mshr_addresscounty<br>*String* | Lettura/scrittura<br>Facoltativo | Il Paese dell'indirizzo principale della persona. Impostalo nell'entità mshr_logisticsaddresscountyentity. |
| **Indirizzo Nome distretto**<br>mshr_addressdistrictname<br>*String* | Lettura/scrittura<br>Facoltativo | Il distretto dell'indirizzo principale della persona. Impostalo nell'entità mshr_logisticsaddressdistrictentity. |
| **Latitudine indirizzo**<br>mshr_addresslatitude<br>*String* | Lettura/scrittura<br>Facoltativo | La latitudine dell'indirizzo principale della persona. |
| **ID posizione indirizzo**<br>mshr_addresslocationid<br>*String* | Lettura/scrittura<br>Facoltativo | L'identificatore univoco per la posizione dell'indirizzo principale della persona. Valori validi nell'entità mshr_logisticspostaladdresslocationcdsentity. |
| **Ruoli posizione indirizzo**<br>mshr_addresslocationroles<br>*String* | Lettura/scrittura<br>Facoltativo | Il ruolo della posizione dell'indirizzo principale della persona. Impostalo nell'entità mshr_logisticslocationrolecdsentity. |
| **Longitudine indirizzo**<br>mshr_addresslongitude<br>*String* |  Lettura/scrittura<br>Facoltativo | La longitudine dell'indirizzo principale della persona. |
| **Stato indirizzo**<br>mshr_addressstate<br>*String* | Lettura/scrittura<br>Facoltativo | Lo stato dell'indirizzo principale della persona. Impostalo nell'entità mshr_logisticsaddressstateentity. |
| **Via indirizzo**<br>mshr_addressstreet<br>*String* | Lettura/scrittura<br>Facoltativo | Il nome della via dell'indirizzo principale della persona. |
| **Indirizzo valido dal**<br>mshr_addressvalidfrom<br>*Data* | Lettura/scrittura<br>Facoltativo | La data a partire dalla quale è valido l'indirizzo principale della persona. |
| **Indirizzo valido fino a**<br>mshr_addressvalidto<br>*Data* | Lettura/scrittura<br>Facoltativo | La data fino alla quale è valido l'indirizzo principale della persona. |
| **CAP indirizzo**<br>mshr_addresszipcode<br>*String* | Lettura/scrittura<br>Facoltativo | Il CAP dell'indirizzo principale della persona. Impostalo nell'entità mshr_logisticsaddresspostalcodeentity. |
| **L'indirizzo è privato**<br>mshr_addressisprivate<br>*set di opzioni mshr_noyes* | Lettura/scrittura<br>Facoltativo | Determina se l'indirizzo principale della persona è condiviso con altri nell'organizzazione. |
| **Descrizione indirizzo**<br>mshr_addressdescription<br>*String* | Lettura/scrittura<br>Facoltativo | Descrizione dell'indirizzo principale della persona. |
| **E-mail contatto principale**<br>mshr_primarycontactemail<br>*String* | Lettura/scrittura<br>Facoltativo | L'indirizzo e-mail principale della persona. |
| **Descrizione e-mail di contatto principale**<br>mshr_primarycontactemaildescription<br>*String* | Lettura/scrittura<br>Facoltativo | Una descrizione fornita per l'indirizzo e-mail principale. |
| **E-mail contatto principale è IM**<br>mshr_primarycontactemailisim<br>*set di opzioni mshr_noyes* | Lettura/scrittura<br>Facoltativo | Determina se l'indirizzo e-mail principale è disponibile per i messaggi immediati. |
| **Scopo e-mail contatto principale**<br>mshr_primarycontactemailpurpose<br>*String* | Lettura/scrittura<br>Facoltativo | Lo scopo dell'indirizzo e-mail principale. Impostalo nell'entità mshr_logisticslocationroleentity. |
| **Fax del contatto principale**<br>mshr_primarycontactfax<br>*String* | Lettura/scrittura<br>Facoltativo | Numero di fax principale. |
| **Descrizione fax di contatto principale**<br>mshr_primarycontactfaxdescription<br>*String* | Lettura/scrittura<br>Facoltativo | Descrizione fornita per il numero di fax principale. |
| **Estensione fax di contatto principale**<br>mshr_primarycontactfaxextension<br>*String* | Lettura/scrittura<br>Facoltativo | L'estensione del numero di fax principale. |
| **Scopo fax contatto principale**<br>mshr_primarycontactfaxpurpose<br>*String* | Lettura/scrittura<br>Facoltativo | Lo scopo del numero di fax principale. Impostalo nell'entità mshr_logisticslocationroleentity.
| **Telefono contatto principale**<br>mshr_primarycontactphone<br>*String* | Lettura/scrittura<br>Facoltativo | Numero di telefono principale. |
| **Descrizione telefono di contatto principale**<br>mshr_primarycontactphonedescription<br>*String* | Lettura/scrittura<br>Facoltativo | Descrizione fornita per il numero di telefono principale. |
| **Estensione telefono di contatto principale**<br>mshr_primarycontactphoneextension<br>*String* | Lettura/scrittura<br>Facoltativo | L'estensione del numero di telefono principale. |
| **Telefono di contatto principale è Cellulare**<br>mshr_primarycontactphoneismobile<br>*set di opzioni mshr_noyes* | Lettura/scrittura<br>Facoltativo | Determina se il numero di telefono principale è un telefono cellulare. |
| **Scopo telefono contatto principale**<br>mshr_primarycontactphonepurpose<br>*String* | Lettura/scrittura<br>Facoltativo | Lo scopo del numero di telefono principale. Impostalo nell'entità mshr_logisticslocationroleentity. |
| **Telex contatto principale**<br>mshr_primarycontacttelex<br>*String* | Lettura/scrittura<br>Facoltativo | Numero di telex principale. |
| **Descrizione telex di contatto principale**<br>mshr_primarycontacttelexdescription<br>*String* | Lettura/scrittura<br>Facoltativo | Descrizione fornita per il numero di telex principale della persona. |
| **Scopo telex contatto principale**<br>mshr_primarycontacttelexpurpose<br>*String* | Lettura/scrittura<br>Facoltativo | Lo scopo del numero di telex principale della persona. Impostalo nell'entità mshr_logisticslocationroleentity. |
| **URL di contatto principale**<br>mshr_primarycontacturl<br>*String* | Lettura/scrittura<br>Facoltativo | L'URL principale. |
| **Descrizione URL del contatto principale**<br>mshr_primarycontacturldescription<br>*String* | Lettura/scrittura<br>Facoltativo | Descrizione fornita dell'URL principale della persona. |
| **Scopo URL contatto principale**<br>mshr_primarycontacturldescription<br>*String* | Lettura/scrittura<br>Facoltativo | Lo scopo dell'URL principale della persona. Impostalo nell'entità mshr_logisticslocationroleentity. |
| **Contatto principale di Facebook**<br>mshr_primarycontactfacebook<br>*String* | Lettura/scrittura<br>Facoltativo | Account Facebook principale. Identificato da ID utente. |
| **Descrizione contatto principale di Facebook**<br>mshr_primarycontactfacebookdescription<br>*String* | Lettura/scrittura<br>Facoltativo | Descrizione fornita dell'account principale della persona Facebook. |
| **Il contatto principale di Facebook è privato**<br>mshr_primarycontactfacebookisprivate<br>*set di opzioni mshr_noyes* | Lettura/scrittura<br>Facoltativo | Determina se l'account principale di Facebook è visibile ad altri utenti. |
| **Scopo del contatto principale di Facebook**<br>mshr_primarycontactfacebookpurpose<br>*String* | Lettura/scrittura<br>Facoltativo | Lo scopo dell'account principale della persona di Facebook. Impostalo nell'entità mshr_logisticslocationroleentity. |
| **Contatto principale di LinkedIn**<br>mshr_primarycontactlinkedin<br>*String* | Lettura/scrittura<br>Facoltativo | Account LinkedIn principale. Identificato da nome utente. |
| **Descrizione contatto LinkedIn principale**<br>mshr_primarycontactlinkedindescription<br>*String* | Lettura/scrittura<br>Facoltativo | Descrizione fornita dell'account LinkedIn principale della persona. |
| **Il contatto principale di LinkedIn è privato**<br>mshr_primarycontactlinkedinisprivate<br>*set di opzioni mshr_noyes* | Lettura/scrittura<br>Facoltativo | Determina se le informazioni dell'account LinkedIn principale della persona vengono condivise con altri utenti. |
| **Scopo contatto principale di LinkedIn**<br>mshr_primarycontactlinkedinpurpose<br>*String* | Lettura/scrittura<br>Facoltativo | Lo scopo dell'account principale di LinkedIn della persona principale. Impostalo nell'entità mshr_logisticslocationroleentity. |
| **Contatto principale di Twitter**<br>mshr_primarycontacttwitter<br>*String* | Lettura/scrittura<br>Facoltativo | L'account Twitter principale della persona. Identificato da @username. |
| **Descrizione contatto principale di Twitter**<br>mshr_primarycontacttwitterdescription<br>*String* | Lettura/scrittura<br>Facoltativo | Descrizione fornita dell'account Twitter principale della persona. |
| **Il contatto principale di Twitter è privato**<br>mshr_primarycontacttwitterisprivate<br>*set di opzioni mshr_noyes* | Lettura/scrittura<br>Facoltativo | Determina se le informazioni dell'account Twitter principale della persona vengono condivise con altri utenti. |
| **Scopo contatto principale di Twitter**<br>mshr_primarycontacttwitterpurpose<br>*String* | Lettura/scrittura<br>Facoltativo | Lo scopo dell'account principale di Twitter della persona principale. Impostalo nell'entità mshr_logisticslocationroleentity. |
| **Tipo parte**<br>mshr_partytype<br>*String* | Lettura/scrittura<br>Facoltativo | Il tipo di parte della persona. Sarà sempre **Persona** per i candidati. |
| **Visualizza sequenza nomi come**<br>mshr_namesequencedisplayas<br>*String* | Lettura/scrittura<br>Facoltativo | La sequenza in cui le proprietà del nome della persona vengono concatenate in modo da ottenere il valore della proprietà Name (mshr_name). |
| **Nome**<br>mshr_firstname<br>*String* | Lettura/scrittura<br>Richiesto | Il nome della persona. |
| **Secondo nome**<br>mshr_middlename<br>*String* | Lettura/scrittura<br>Facoltativo | Il secondo nome della persona. |
| **Prefisso cognome**<br>mshr_lastnameprefix<br>*String* | Lettura/scrittura<br>Facoltativo | Il prefisso del cognome della persona. |
| **Cognome**<br>mshr_lastname<br>*String* | Lettura/scrittura<br>Facoltativo | Il cognome della persona. |
| **ID posizione elettronico**<br>mshr_electroniclocationid<br>*String* | Lettura/scrittura<br>Facoltativo | L'ID della posizione elettronica della persona. |
| **Fuso orario indirizzo**<br>mshr_addresstimezone<br>*Int* | Lettura/scrittura<br>Facoltativo | Il fuso orario dell'indirizzo principale della persona. |

## <a name="see-also"></a>Vedere anche

[Introduzione all'API di integrazione del sistema di tracciabilità dei candidati](hr-admin-integration-ats-api-introduction.md)<br>
[Query di esempio per il candidato da assumere](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]