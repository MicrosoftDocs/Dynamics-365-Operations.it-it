---
title: Gestione integrata dei dati dei fornitori
description: In questo argomento viene descritta l'integrazione dei dati dei fornitori società tra le app Finance and Operations e Common Data Service.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 07/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: d33625b94e7611a256c389a6de4692ae8f4ff2a7
ms.sourcegitcommit: 6e0909e95f38b7487a4b7f68cc62b723f8b59bd4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/10/2019
ms.locfileid: "2572474"
---
# <a name="integrated-vendor-master"></a>Gestione integrata dei dati dei fornitori

[!include [banner](../includes/banner.md)]

[!include [preview](../includes/preview-banner.md)]

Il termine *fornitore* si riferisce a un'organizzazione fornitrice o a un titolare unico che fa parte del processo della supply chain e che fornisce merci per l'azienda. Sebbene *fornitore* sia un concetto cardine nelle app Finance and Operations, un concetto di fornitore non è presente in altre app Dynamics 365. Invece, alcune aziende sovraccaricano l'entità Conto per archiviare sia le informazioni relative ai clienti che ai fornitori. Altre aziende utilizzano un concetto personalizzato di fornitore. L'integrazione con Common Data Service supporta entrambi gli approcci. Di conseguenza, è possibile abilitare l'uno o l'altro, a seconda del scenario aziendali.

L'integrazione di dati fornitore tra le app Finance and Operations e altre applicazioni Dynamics 365 consente la gestione complessa di tutti i dati. Indipendentemente dall'origine dei dati fornitore, questi vengono integrati in background tra applicazioni e nonostante le differenze dell'infrastruttura. 

### <a name="vendor-data-flow"></a>Flusso di dati fornitore

Se si desidera utilizzare altre app Dynamics 365 per la gestione dei fornitori e si desidera isolare le informazioni sui fornitori da quelle sui cliente, è possibile utilizzare la nuova struttura fornitori.

![Flusso di dati fornitore](media/dual-write-vendor-data-flow.png)

Se si desidera utilizzare altre app Dynamics 365 per la gestione dei fornitori e si desidera continuare a usare l'entità Conto per archiviare le informazioni sui fornitori, è possibile utilizzare la nuova struttura fornitori estesa. In questa struttura, le informazioni estese del fornitore, ad esempio il gruppo di fornitori e il profilo di registrazione fornitore, vengono archiviate nei dettagli del fornitore.

![Flusso di dati esteso fornitore](media/dual-write-vendor-detail.jpg)

Le informazioni di contatto del fornitore somigliano alle informazioni di contatto del cliente. In background, le informazioni del contatto vengono archiviate e recuperate dalle stesse entità.

## <a name="templates"></a>Modelli

I dati dei fornitori includono tutte le informazioni sul fornitore, ad esempio il gruppo di fornitori, indirizzi, informazioni di contatto, il profilo di pagamento, il profilo fattura. Una raccolta di mappe di entità funziona in combinazione durante l'interazione con i dati dei fornitori, come illustrato nella seguente tabella.

App Finance and Operations  | Altre app Dynamics 365
------------------------|---------------------------------
Fornitore V2               | Account
Fornitore V2               | Msdyn\_vendors
Contatti CDS V2         | Contatto
Gruppi di fornitori           | Msdyn\_vendorgroups
Metodo di pagamento fornitore   | Msdyn\_vendorpaymentmethods
Scadenzario pagamenti        | Msdyn\_paymentschedules
Scadenzario pagamenti        | Msdyn\_paymentschedulelines
Giorno di pagamento - CDS         | Msdyn\_paymentdays
Righe giorno di pagamento - CDS   | Msdyn\_paymentdaylines
Termini di pagamento        | Msdyn\_paymentterms
Affissi nome            | Msdyn\_nameaffixes

[!include [banner](../includes/dual-write-symbols.md)]

## <a name="vendor-v2-and-account"></a>Fornitore V2 e Conto 

Le società che utilizzano l'entità Conto per archiviare le informazioni sui fornitori possono continuare a usarlo nello stesso modo. Possono inoltre sfruttare la funzionalità fornitore esplicita imminente con l'integrazione delle app Finance and Operations.

## <a name="vendor-v2-and-msdyn_vendors"></a>Fornitore V2 e Msdyn\_vendors

Le società che utilizzano una soluzione personalizzata per i fornitori possono sfruttare il concetto di fornitore predefinito introdotto in Common Data Service a causa dell'integrazione con le app Finance and Operations. 

<!-- ![vendor mappings](media/dual-write-vendors-1.png) -->

<!-- ![vendor mappings](media/dual-write-vendors-2.png) -->

<!-- ![vendor mappings](media/dual-write-vendors-3.png) -->

Campo di origine | Tipo di mappa | Campo di destinazione
---|---|---
VENDORACCOUNTNUMBER | = | msdyn\_vendoraccountnumber
VENDORGROUPID | = | msdyn\_vendorgroupid.msdyn\_vendorgroup
VENDORORGANIZATIONNAME | = | msdyn\_name
VENDORPARTYTYPE | \>\< | msdyn\_isperson
PERSONFIRSTNAME | = | msdyn\_firstname
PERSONLASTNAME | = | msdyn\_lastname
CREDITLIMIT | = | msdyn\_vendorcreditlimit
ISFOREIGNENTITY | \>\< | msdyn\_isforeignentity
ISONETIMEVENDOR | \>\< | msdyn\_isonetimevendor
ADDRESSBUILDINGCOMPLIMENT | = | msdyn\_addressbuildingcompliment
PERSONCHILDRENNAMES | = | msdyn\_childrennames
ADDRESSCITY | = | msdyn\_addresscity
ADDRESSCOUNTRYREGIONID | = | msdyn\_addresscountryregionid
ADDRESSCOUNTRYREGIONISOCODE | = | msdyn\_addresscountryregionisocode
ADDRESSCOUNTYID | = | msdyn\_addresscountyid
CREDITRATING | = | msdyn\_creditrating
ADDRESSDESCRIPTION | = | msdyn\_addressdescription
ADDRESSDISTRICTNAME | = | msdyn\_addressdistrictname
DUNSNUMBER | = | msdyn\_dunsnumber
ETHNICORIGINID | = | msdyn\_ethnicorigin
FORMATTEDPRIMARYADDRESS | = | msdyn\_formattedprimaryaddress
PERSONHOBBIES | = | msdyn\_hobbies
PERSONINITIALS | = | msdyn\_initials
LANGUAGEID | = | msdyn\_languageid
PERSONLASTNAMEPREFIX | = | msdyn\_lastnameprefix
PERSONMIDDLENAME | = | msdyn\_middlename
ORGANIZATIONNUMBER | = | msdyn\_organizationnumber
OURACCOUNTNUMBER | = | msdyn\_ourvendoraccountnumber
PAYMENTID | = | msdyn\_paymentid
PERSONPHONETICFIRSTNAME | = | msdyn\_phoneticfirstname
PERSONPHONETICMIDDLENAME | = | msdyn\_phoneticmiddlename
PERSONPHONETICLASTNAME | = | msdyn\_phoneticlastname
ORGANIZATIONPHONETICNAME | = | msdyn\_organizationphoneticname
ADDRESSPOSTBOX | = | msdyn\_addresspostbox
PRIMARYURL | = | msdyn\_primarycontacturl
PRIMARYEMAILADDRESS | = | msdyn\_primaryemailaddress
PRIMARYEMAILADDRESSDESCRIPTION | = | msdyn\_primaryemailaddressdescription
PRIMARYFACEBOOK | = | msdyn\_primaryfacebook
PRIMARYFACEBOOKDESCRIPTION | = | msdyn\_primaryfacebookdescription
PRIMARYFAXNUMBER | = | msdyn\_primaryfaxnumber
PRIMARYFAXNUMBERDESCRIPTION | = | msdyn\_primaryfaxnumberdescription
PRIMARYFAXNUMBEREXTENSION | = | msdyn\_primaryfaxnumberextension
PRIMARYLINKEDIN | = | msdyn\_primarylinkedin
PRIMARYLINKEDINDESCRIPTION | = | msdyn\_primarylinkedindescription
PRIMARYPHONENUMBER | = | msdyn\_pimaryphonenumber
PRIMARYPHONENUMBERDESCRIPTION | = | msdyn\_primaryphonenumberdescription
PRIMARYPHONENUMBEREXTENSION | = | msdyn\_primaryphonenumberextension
PRIMARYTELEX | = | msdyn\_primarytelex
PRIMARYTELEXDESCRIPTION | = | msdyn\_primarytelexdescription
PRIMARYTWITTER | = | msdyn\_primarytwitter
PRIMARYTWITTERDESCRIPTION | = | msdyn\_primarytwitterdescription
PRIMARYURLDESCRIPTION | = | msdyn\_primaryurldescription
PERSONPROFESSIONALSUFFIX | = | msdyn\_professionalsuffix
PERSONPROFESSIONALTITLE | = | msdyn\_professionatitle
ADDRESSSTATEID | = | msdyn\_addressstateid
ADDRESSSTREET | = | msdyn\_addressstreet
ADDRESSSTREETNUMBER | = | msdyn\_addressstreetnumber
VENDORKNOWNASNAME | = | msdyn\_vendorknownasname
ADDRESSZIPCODE | = | msdyn\_addresszipcode
DEFAULTPAYMENTDAYNAME | = | msdyn\_defaultpaymentdayname.msdyn\_name
DEFAULTPAYMENTSCHEDULENAME | = | msdyn\_paymentschedule.msdyn\_name
DEFAULTPAYMENTTERMSNAME | = | msdyn\_paymentterms.msdyn\_name
HASONLYTAKENBIDS | \>\< | msdyn\_hasonlytakenbids
ISMINORITYOWNED | \>\< | msdyn\_isminorityowned
ISVENDORLOCALLYOWNED | \>\< | msdyn\_isvendorlocallyowned
ISSERVICEVETERANOWNED | \>\< | msdyn\_isserviceveteranowned
ISOWNERDISABLED | \>\< | msdyn\_ownerisdisabled
ISWOMANOWNER | \>\< | msdyn\_womanowner
PERSONANNIVERSARYDAY | = | msdyn\_personanniversaryday
PERSONANNIVERSARYYEAR | = | msdyn\_anniversaryyear
PERSONBIRTHDAY | = | msdyn\_birthday
PERSONBIRTHYEAR | = | msdyn\_birthyear
ORGANIZATIONEMPLOYEEAMOUNT | = | msdyn\_numberofemployees
VENDORHOLDRELEASEDATE | = | msdyn\_vendoronholdreleasedate
VENDORPARTYNUMBER | = | msdyn\_vendorpartynumber
ADDRESSLOCATIONID | = | msdyn\_addresslocationid
PERSONANNIVERSARYMONTH | = | msdyn\_vendorpersonanniversarymonth
PERSONBIRTHMONTH | = | msdyn\_vendorpersonbirthmonth
PERSONMARITALSTATUS | \>\< | msdyn\_maritalstatus
ADDRESSLATITUDE | \>\> | msdyn\_addresslatitude
ADDRESSLONGITUDE | \>\> | msdyn\_addresslongitude
ONHOLDSTATUS | \>\< | msdyn\_onholdstatus
CURRENCYCODE | = | msdyn\_currencycode.isocurrencycode
ISVENDORLOCATEDINHUBZONE | \>\< | msdyn\_isvendorlocatedinhubzone
DEFAULTVENDORPAYMENTMETHODNAME | = | msdyn\_vendorpaymentmethod.msdyn\_name
INVOICEVENDORACCOUNTNUMBER | = | msdyn\_invoicevendoraccountnumber.msdyn\_vendoraccountnumber
PERSONGENDER | \>\< | msdyn\_gender
AREPRICESINCLUDINGSALESTAX | \>\< | msdyn\_priceincludessalestax
SALESTAXGROUPCODE | = | msdyn\_taxgroup.msdyn\_name
VENDORPRICETOLERANCEGROUPID | = | msdyn\_pricetolerancegroup.msdyn\_groupid

## <a name="contacts"></a>Contatti

Questo modello sincronizza tutte le informazioni del contatto principale, secondario e terziario sia dei clienti che dei forntori tra le app Finance and Operations e altre app Dynamics 365. Per i dettagli della mappa delle entità, vedere [Gestione integrata dei dati dei clienti](dual-write-customer.md#contacts).

## <a name="vendor-groups"></a>Gruppi di fornitori

Questo modello sincronizza le informazioni sui gruppi di fornitori tra le app Finance and Operations e altre app Dynamics 365.

<!-- ![vendor groups mappings](media/dual-write-vendor-groups.png) -->

Campo di origine | Tipo di mappa | Campo di destinazione
---|---|---
DEFAULTPAYMENTTERMNAME | = | msdyn\_paymentterms.msdyn\_name
DESCRIZIONE | = | msdyn\_description
VENDORGROUPID | = | msdyn\_vendorgroup
CLEARINGPERIODPAYMENTTERMNAME | = | msdyn\_clearingperiodpaymentpermname.msdyn\_name

### <a name="vendor-payment-method"></a>Metodo di pagamento fornitore

Questo modello sincronizza le informazioni sul metodo di pagamento fornitori tra Finance and Operations e altre app Dynamics 365.

<!-- ![vendor payment method mappings](media/dual-write-vendor-payment-method.png) -->

Campo di origine | Tipo di mappa | Campo di destinazione
---|---|---
NOME | = | msdyn\_name
DESCRIZIONE | = | msdyn\_description
SUMBYPERIOD | \>\< | msdyn\_sumbyperiod
DISCOUNTGRACEPERIODDAYS | = | msdyn\_discountgraceperioddays
PAYMENTSTATUS | \>\< | msdyn\_paymentstatus
ALLOWPAYMENTCOPIES | \>\< | msdyn\_allowpaymentcopies
PAYMENTTYPE | \>\< | msdyn\_paymenttype
LASTFILENUMBER | = | msdyn\_lastfilenumber
LASTFILENUMBERTODAY | = | msdyn\_lastfilenumbertoday
ACCOUNTTYPE | \>\< | msdyn\_accounttype
BRIDGINGPOSTINGENABLED | \>\< | msdyn\_bridgingposting
ENABLEPOSTDATEDCHECKCLEARINGPOSTING | \>\< | msdyn\_postdatedcheckclearingposting
PROMISSORYNOTEDRAFTTYPE | \>\< | msdyn\_promissorynotedrafttype
DIRECTDEBIT | \>\< | msdyn\_directdebit

