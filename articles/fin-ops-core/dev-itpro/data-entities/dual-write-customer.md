---
title: Gestione integrata dei dati dei clienti
description: In questo argomento viene descritta l'integrazione dei dati dei clienti tra Finance and Operations e Common Data Service.
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
ms.openlocfilehash: 6c8c94eb8ff04d489eb24b7e0f4642aef20a3b18
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/27/2019
ms.locfileid: "2182050"
---
## <a name="integrated-customer-master"></a>Gestione integrata dei dati dei clienti

[!include [banner](../includes/banner.md)]

[!include [preview](../includes/preview-banner.md)]

Tipicamente i record cliente sono gestiti in più applicazioni. Ad esempio, l'attività di vendita può usare record cliente commerciali tramite un'applicazione Sales e attività di e-Commerce o vendita al dettaglio possono usare i record cliente tramite un'applicazione Finance and Operations. Indipendentemente dall'origine dei record cliente, questi vengono integrati in background tra applicazioni e nonostante le differenze dell'infrastruttura. La gestione integrata dei dati cliente consente di gestire scenari complessi e offre una visione completa del cliente nella suite applicativa di Dynamics 365.

## <a name="customer-data-flow"></a>Flusso dei dati dei clienti

*Cliente* è un concetto ben definito nelle applicazioni. Di conseguenza, l'integrazione dei dati dei clienti implica solo armonizzare il concetto di cliente tra due applicazioni. L'illustrazione seguente mostra il flusso dei dati dei clienti.

![Flusso dei dati dei clienti](media/dual-write-customer-data-flow.png)

I clienti possono essere classificati largamente in due tipi: clienti commerciali/aziendali e consumatori/utenti finali. Questi due tipi di clienti vengono archiviati e gestiti in modo diverso in Finance and Operations e Common Data Service.

In Finance and Operations, sia i clienti commerciali/aziendali che i consumatori/utenti finali vengono gestiti in un'unica tabella denominata **CustTable** (CustomerCustomerV3Entity) e vengono classificati in base all'attributo **Tipo**. Se **Tipo** è impostato su **Organizzazione**, il cliente è cliente commerciale/aziendale e se **Tipo** è impostato su **Persona**, il cliente è un consumatore/utente finale. Le informazioni principali del contatto vengono gestite tramite l'entità SMMContactPersonEntity.

In Common Data Service, i clienti commerciali/aziendali sono gestiti nell'entità Conto e vengono identificati come clienti quando l'attributo **RelationshipType** è impostato su **Cliente**. Sia i consumatori/utenti finali che il contatto sono rappresentati dall'entità Contatto. Per fornire una netta separazione tra un consumatore/utente finale e un contatto, l'entità **Contatto** include un flag booleano **Di vendita**. Se **Di vendita** è **True**, il contatto è un consumatore/utente finale e offerte e gli ordini possono essere creati per quel contatto. Se **Di vendita** è **False**, il contatto è solo un contatto principale di un cliente.

Quando un contatto non di vendita partecipa a un processo di ordine o offerta, **Di vendita** è impostato su **True** per contrassegnare il contatto come contatto di vendita. Un contatto che è diventato un contatto di vendita rimane tale.

## <a name="templates"></a>Modelli

I dati dei clienti includono tutte le informazioni sul cliente, ad esempio il gruppo di clienti, indirizzi, informazioni di contatto, il profilo di pagamento, il profilo fattura e lo stato del programma fedeltà. Una raccolta di mappe di entità funziona in combinazione durante l'interazione con i dati dei clienti, come illustrato nella seguente tabella.

App Finance and Operations    | Altre app Dynamics 365
--------------------------|---------------------------------
Cliente V3               | Account
Cliente V3               | Contatto
Contatti CDS V2           | Contatto
Gruppi di clienti           | Msdyn\_customergroups
Metodo di pagamento clienti   | Msdyn\_customerpaymentmethods
Carta fedeltà              | Msdyn\_loyaltycards
Scadenzario pagamenti          | Msdyn\_paymentschedules
Scadenzario pagamenti          | Msdyn\_paymentschedulelines
Giorno di pagamento - CDS           | Msdyn\_paymentdays
Righe giorno di pagamento - CDS     | Msdyn\_paymentdaylines
Termini di pagamento          | Msdyn\_paymentterms
Affissi nome              | Msdyn\_nameaffixes

[!include [banner](../includes/dual-write-symbols.md)]

## <a name="customer-v3-to-account"></a>Cliente V3 a conto

Questo modello sincronizza le informazioni sui dati master i clienti commerciali e aziendali tra le app Finance and Operations e Common Data Service.

<!-- ![](media/dual-write-account-1.png) -->

<!-- ![](media/dual-write-account-2.png) -->

Campo di origine | Tipo di mappa | Campo di destinazione
---|---|---
CUSTOMERACCOUNT | = | accountnumber
INVOICEADDRESSCITY | = | address2\_city
INVOICEADDRESSCOUNTRYREGIONISOCODE | = | address2\_country
INVOICEADDRESSCOUNTY | = | address2\_county
INVOICEADDRESSLATITUDE | \> | address2\_latitude
INVOICEADDRESSLONGITUDE | \> | address2\_longitude
INVOICEADDRESSSTATE | = | address2\_stateorprovince
INVOICEADDRESSSTREET | = | address2\_line1
INVOICEADDRESSZIPCODE | = | address2\_postalcode
CREDITLIMIT | = | creditlimit
DELIVERYADDRESSCITY | = | address1\_city
DELIVERYADDRESSCOUNTRYREGIONISOCODE | = | address1\_country
DELIVERYADDRESSCOUNTY | = | address1\_county
DELIVERYADDRESSLATITUDE | \> | address1\_latitude
DELIVERYADDRESSLONGITUDE | \> | address1\_longitude
DELIVERYADDRESSZIPCODE | = | address1\_postalcode
ORGANIZATIONNAME | = | name
ORGANIZATIONNUMBEROFEMPLOYEES | = | numberofemployees
PRIMARYCONTACTEMAIL | = | emailaddress1
PRIMARYCONTACTFAX | = | fax
PRIMARYCONTACTPHONE | = | telephone1
PRIMARYCONTACTTWITTER | = | primarytwitterid
PRIMARYCONTACTURL | = | websiteurl
SALESCURRENCYCODE | = | transactioncurrencyid.isocurrencycode
SALESMEMO | = | descrizione
CREDITLIMITISMANDATORY | \>\< | msdyn\_creditlimitismandatory
CREDITRATING | = | msdyn\_creditrating
CUSTOMERGROUPID | = | msdyn\_customergroupid.msdyn\_groupid
IDENTIFICATIONNUMBER | = | msdyn\_identificationnumber
INVOICEACCOUNT | = | msdyn\_billingaccount.accountnumber
INVOICEADDRESS | \>\< | msdyn\_invoiceaddress
ISONETIMECUSTOMER | \>\< | msdyn\_onetimecustomer
ONHOLDSTATUS | \>\< | msdyn\_onholdstatus
PARTYCOUNTRY | = | msdyn\_partycountry
PARTYSTATE | = | msdyn\_partystateprovince
PAYMENTDAY | = | msdyn\_paymentday.msdyn\_name
PAYMENTMETHOD | = | msdyn\_customerpaymentmethod.msdyn\_name
PAYMENTSCHEDULE | = | msdyn\_paymentschedule.msdyn\_name
PAYMENTTERMS | = | msdyn\_paymentterm.msdyn\_name
PAYMENTTERMSBASEDAYS | = | msdyn\_paymenttermsbasedays
PRIMARYCONTACTFACEBOOK | = | msdyn\_primaryfacebookid
PRIMARYCONTACTFAXEXTENSION | = | msdyn\_faxextension
PRIMARYCONTACTLINKEDIN | = | msdyn\_primarylinkedinid
TAXEXEMPTNUMBER | = | msdyn\_taxexemptnumber
VENDORACCOUNT | = | msdyn\_vendor.msdyn\_vendoraccountnumber
PRIMARYCONTACTEMAILDESCRIPTION | = | msdyn\_emailaddress1description
PRIMARYCONTACTFACEBOOKDESCRIPTION | = | msdyn\_primaryfacebookdescription
PRIMARYCONTACTFAXDESCRIPTION | = | msdyn\_faxdescription
PRIMARYCONTACTLINKEDINDESCRIPTION | = | msdyn\_primarylinkedindescrption
PRIMARYCONTACTPHONEDESCRIPTION | = | msdyn\_telephone1description
PRIMARYCONTACTPHONEEXTENSION | = | msdyn\_telephone1extension
PRIMARYCONTACTTWITTERDESCRIPTION | = | msdyn\_primarytwitteriddescription
PRIMARYCONTACTURLDESCRIPTION | = | msdyn\_websiteurldescription
LANGUAGEID | \<\< | nessuno
DELIVERYADDRESSSTREET | = | address1\_line1
DELIVERYADDRESSSTATE | = | address1\_stateorprovince
nessuno | \>\> | address1\_addresstypecode
nessuno | \>\> | customertypecode
PARTYTYPE | \<\< | nessuno
PARTYNUMBER | = | msdyn\_partynumber

## <a name="customer-v3-to-contact"></a>Cliente V3 a contatto

Questo modello sincronizza i dati master dei consumatori e gli utenti finali tra Finance and Operations e altre app Dynamics 365.

<!-- ![](media/dual-write-contact-1.png) -->
<!-- ![](media/dual-write-contact-2.png) -->

Campo di origine | Tipo di mappa | Campo di destinazione
---|---|---
nessuno | \>\> | msdyn\_sellable
PARTYTYPE | \<\< | nessuno
PARTYNUMBER | = | msdyn\_partynumber
CUSTOMERACCOUNT | = | msdyn\_contactpersonid
CUSTOMERGROUPID | = | msdyn\_customergroupid.msdyn\_groupid
PERSONFIRSTNAME | = | firstname
PERSONLASTNAME | = | lastname
PERSONMIDDLENAME | = | middlename
PERSONPROFESSIONALTITLE | = | jobtitle
PERSONGENDER | \>\< | gendercode
PERSONMARITALSTATUS | \>\< | familystatuscode
LANGUAGEID | \<\< | nessuno
ADDRESSCITY | = | address1\_city
ADDRESSCOUNTRYREGIONISOCODE | = | address1\_country
ADDRESSCOUNTY | = | address1\_county
ADDRESSLATITUDE | \> | address1\_latitude
ADDRESSLONGITUDE | \> | address1\_longitude
ADDRESSLOCATIONROLES | \<\< | nessuno
ADDRESSSTATE | = | address1\_stateorprovince
ADDRESSSTREET | = | address1\_line1
ADDRESSZIPCODE | = | address1\_postalcode
ADDRESSPOSTBOX | = | address1\_postofficebox
nessuno | \>\> | address1\_addresstypecode
INVOICEADDRESSCITY | = | address2\_city
INVOICEADDRESSCOUNTRYREGIONISOCODE | = | address2\_country
INVOICEADDRESSCOUNTY | = | address2\_county
INVOICEADDRESSLATITUDE | \> | address2\_latitude
INVOICEADDRESSLONGITUDE | \> | address2\_longitude
INVOICEADDRESSSTATE | = | address2\_stateorprovince
INVOICEADDRESSSTREET | = | address2\_line1
INVOICEADDRESSZIPCODE | = | address2\_postalcode
nessuno | \>\> | address2\_addresstypecode
DELIVERYADDRESSCITY | = | address3\_city
DELIVERYADDRESSCOUNTRYREGIONISOCODE | = | address3\_country
DELIVERYADDRESSCOUNTY | = | address3\_county
DELIVERYADDRESSLATITUDE | \> | address3\_latitude
DELIVERYADDRESSLONGITUDE | \>\> | address3\_longitude
DELIVERYADDRESSSTATE | = | address3\_stateorprovince
DELIVERYADDRESSSTREET | = | address3\_line1
DELIVERYADDRESSZIPCODE | = | address3\_postalcode
nessuno | \>\> | address3\_addresstypecode
PRIMARYCONTACTEMAIL | = | emailaddress1
PRIMARYCONTACTEMAILDESCRIPTION | = | msdyn\_emailaddress1description
PRIMARYCONTACTFAX | = | fax
PRIMARYCONTACTFAXDESCRIPTION | = | msdyn\_faxdescription
PRIMARYCONTACTFAXEXTENSION | = | msdyn\_faxextension
IDENTIFICATIONNUMBER | = | msdyn\_identificationnumber
PARTYCOUNTRY | = | msdyn\_partycountry
PARTYSTATE | = | msdyn\_partystateprovince
PRIMARYCONTACTFACEBOOK | = | msdyn\_primaryfacebookid
PRIMARYCONTACTFACEBOOKDESCRIPTION | = | msdyn\_primaryfacebookdescription
PRIMARYCONTACTLINKEDIN | = | msdyn\_primaryinkedinid
PRIMARYCONTACTLINKEDINDESCRIPTION | = | msdyn\_primarylinkedindescrption
PRIMARYCONTACTPHONE | = | telephone1
PRIMARYCONTACTPHONEDESCRIPTION | = | msdyn\_telephone1description
PRIMARYCONTACTPHONEEXTENSION | = | msdyn\_telephone1extension
PRIMARYCONTACTTWITTER | = | msdyn\_primarytwitterid
PRIMARYCONTACTTWITTERDESCRIPTION | = | msdyn\_primarytwitteriddescription
PRIMARYCONTACTURL | = | websiteurl
PRIMARYCONTACTURLDESCRIPTION | = | msdyn\_websiteurldescription
SALESCURRENCYCODE | = | transactioncurrencyid.isocurrencycode
SALESMEMO | = | descrizione

## <a name="contacts"></a>Contatti

Questo modello sincronizza tutte le informazioni del contatto principale, secondario e terziario sia dei clienti che dei fornitori tra Finance and Operations e altre app Dynamics 365.

<!-- ![](media/dual-write-contacts.png) -->

Campo di origine | Tipo di mappa | Campo di destinazione
---|---|---
CONTACTPERSONPARTYNUMBER | = | msdyn\_partynumber
ASSOCIATEDCONTACTTYPE | \<\< | nessuno
FIRSTNAME | = | firstname
MIDDLENAME | = | middlename
LASTNAME | = | lastname
ASSOCIATEDCONTACTNUMBER | = | msdyn\_vendorcontactid.msdyn\_vendoraccountnumber
PRIMARYADDRESSCITY | = | address1\_city
PRIMARYADDRESSCOUNTRYREGIONID | = | address1\_country
PRIMARYADDRESSCOUNTYID | = | address1\_county
PRIMARYFAXNUMBER | = | fax
PRIMARYADDRESSSTATEID | = | address1\_stateorprovince
PRIMARYADDRESSSTREET | = | address1\_line1
PRIMARYADDRESSZIPCODE | = | address1\_postalcode
PRIMARYPHONENUMBER | = | telephone1
PRIMARYEMAILADDRESS | = | emailaddress1
EMPLOYMENTDEPARTMENT | = | reparto
NOTES | = | descrizione
GENDER | \>\< | gendercode
GOVERNMENTIDENTIFICATIONNUMBER | = | governmentid
PRIMARYURL | = | websiteurl
MARITALSTATUS | \>\< | familystatuscode
ISRECEIVINGDIRECTMAIL | \>\< | donotemail
EMPLOYMENTPROFESSION | = | jobtitle
SPOUSENAME | = | spousesname
nessuno | \>\> | msdyn\_contactforvendor
nessuno | \>\> | msdyn\_contactpersonid

## <a name="customer-groups"></a>Gruppi di clienti

Questo modello sincronizza le informazioni sui gruppi di clienti tra Finance and Operations e altre app Dynamics 365.

<!-- ![](media/dual-write-customer-groups.png) -->

Campo di origine | Tipo di mappa | Campo di destinazione
---|---|---
CUSTOMERGROUPID | = | msdyn\_groupid
DESCRIZIONE | = | msdyn\_description
ISSALESTAXINCLUDEDINPRICE | \>\< | msdyn\_issalestaxincludedinprice
PAYMENTTERMID | = | msdyn\_paymenttermid.msdyn\_name
CLEARINGPERIODPAYMENTTERMNAME | = | msdyn\_clearingperiodpaymenttermname.msdyn\_name

## <a name="customer-payment-methods"></a>Metodi di pagamento clienti

Questo modello sincronizza le informazioni sul metodo di pagamento clienti tra Finance and Operations e altre app Dynamics 365.

<!-- ![](media/dual-write-customer-payment-methods.png) -->

Campo di origine | Tipo di mappa | Campo di destinazione
---|---|---
NOME | = | msdyn\_name
ACCOUNTTYPE | \>\< | msdyn\_accounttype
DISCOUNTGRACEPERIODDAYS | = | msdyn\_discountgraceperioddays
BRIDGINGPOSTINGENABLED | \>\< | msdyn\_bridgingpostingenabled
ISSEPA | \>\< | msdyn\_issepa
LASTFILENUMBER | = | msdyn\_lastfilenumber
LASTFILENUMBERTODAY | = | msdyn\_lastfilenumbertoday
DESCRIZIONE | = | msdyn\_description
PAYMENTTYPE | \>\< | msdyn\_paymenttype
CREATEANDDRAWBILLOFEXCHANGEDURINGINVOICEPOSTING | \>\< | msdyn\_invoiceupdate
PAYMENTSTATUS | \>\< | msdyn\_paymentstatus
SUMBYPERIOD | \>\< | msdyn\_sumbyperiod
ENABLEPOSTDATEDCHECKCLEARINGPOSTING | \>\< | msdyn\_enablepostdatescheckclearingposting
BILLOFEXCHANGEDRAFTTYPE | \>\< | msdyn\_billofexchangedrafttype
DIRECTDEBIT | \>\< | msdyn\_directdebit

## <a name="loyalty-cards"></a>Carte fedeltà

Questo modello sincronizza le informazioni sulle carte fedeltà dei clienti tra Finance and Operations e altre app Dynamics 365.

<!-- ![](media/dual-write-loyalty-cards.png) -->

Campo di origine | Tipo di mappa | Campo di destinazione
---|---|---
CARDNUMBER | = | msdyn\_cardnumber
CARDTENDERTYPE | \>\< | msdyn\_cardtendertype
PARTYNUMBER | = | msdyn\_partynumber
REPLACEMENTCARDNUMBER | \> | msdyn\_replacementcardnumber
OMOPERATINGUNITNUMBER | = | msdyn\_operatingunitnumber
LOYALTYENROLLMENTDATE | = | msdyn\_enrollmentdate

## <a name="payment-schedules"></a>Scadenzari pagamenti

Questo modello sincronizza i dati di riferimento degli scadenzari pagamenti sia dei clienti che dei fornitori tra Finance and Operations e altre app Dynamics 365.

<!-- ![](media/dual-write-payment-schedules.png) -->

Campo di origine | Tipo di mappa | Campo di destinazione
---|---|---
NOME | = | msdyn\_name
DESCRIZIONE | = | msdyn\_description
ALLOCATIONMETHOD | \>\< | msdyn\_allocationmethod
PAYMENTFREQUENCYUNITS | \>\< | msdyn\_paymentfrequencyunit
PAYMENTFREQUENCY | = | msdyn\_paymentfrequency
NUMBEROFPAYMENTS | = | msdyn\_numberofpayments
FIXEDPAYMENTAMOUNT | = | msdyn\_fixedpaymentamount
MINIMUMPAYMENTAMOUNT | = | msdyn\_minimumpaymentamount
SALESTAXALLOCATIONMETHOD | \>\< | msdyn\_salestaxallocationmethod
NOTES | = | msdyn\_note

## <a name="payment-schedule-lines"></a>Righe scadenzari pagamenti

Sincronizza i dati di riferimento delle righe degli scadenzari pagamenti sia dei clienti che dei fornitori tra Finance and Operations e altre app Dynamics 365.

<!-- ![](media/dual-write-payment-schedule-lines.png) -->

Campo di origine | Tipo di mappa | Campo di destinazione
---|---|---
PAYMENTSCHEDULENAME | = | msdyn\_paymentschedule.msdyn\_name
PAYMENTSCHEDULENAME | \> | msdyn\_name
LINENUMBER | = | msdyn\_linenumber
PERIODSAFTERDUEDATE | = | msdyn\_periodsafterduedate
PERCENTORAMOUNT | \>\< | msdyn\_percentoramount
PERCENTORAMOUNTVALUE | = | msdyn\_percentoramountvalue

## <a name="payment-days"></a>Giorni di pagamento

Questo modello sincronizza i dati di riferimento dei giorni di pagamento sia dei clienti che dei fornitori tra Finance and Operations e altre app Dynamics 365.

<!-- ![](media/dual-write-payment-days.png) -->

Campo di origine | Tipo di mappa | Campo di destinazione
---|---|---
NOME | = | msdyn\_name
DESCRIZIONE | = | msdyn\_description

## <a name="payment-day-lines"></a>Righe giorni di pagamento

Questo modello sincronizza i dati di riferimento delle righe dei giorni di pagamento sia dei clienti che dei fornitori tra Finance and Operations e altre app Dynamics 365.

<!-- ![](media/dual-write-payment-day-lines.png) -->

Campo di origine | Tipo di mappa | Campo di destinazione
---|---|---
CDSINTEGRATIONKEY | = | msdyn\_paymentdaylineid
FREQUENCY | \>\< | msdyn\_frequency
DAYOFWEEK | \>\< | msdyn\_dayofweek
DAYOFMONTH | = | msdyn\_dayofmonth
NOME | = | msdyn\_paymentday.msdyn\_name

## <a name="payment-terms"></a>Condizioni di pagamento

Questo modello sincronizza i dati di riferimento delle condizioni pagamento (termini di pagamento) sia dei clienti che dei fornitori tra Finance and Operations e altre app Dynamics 365.

<!-- ![](media/dual-write-payment-terms.png) -->

Campo di origine | Tipo di mappa | Campo di destinazione
---|---|---
DESCRIZIONE | = | msdyn\_description
NOME | = | msdyn\_name
NUMBEROFMONTHS | = | msdyn\_numberofmonth
CUTOFFDAYOFMONTH | = | msdyn\_cutoffdayofmonth
ISCASHPAYMENT | \>\< | msdyn\_iscashpayment
NUMBEROFDAYS | = | msdyn\_days
ISCERTIFIEDCOMPANYCHECK | \>\< | msdyn\_iscertifiedcompanycheck
ISDEFAULTPAYMENTTERM | \>\< | msdyn\_isdefaultpaymentterm
CREDITCARDPAYMENTTYPE | \>\< | msdyn\_creditcardpaymenttype
CREDITCARDCREDITCHECKTYPE | \>\< | msdyn\_creditcardcreditchecktype
PAYMENTDAYNAME | = | msdyn\_paymentdayname.msdyn\_name
PAYMENTMETHODTYPE | \>\< | msdyn\_paymentmethodtype
PAYMENTSCHEDULENAME | = | msdyn\_paymentschedulename.msdyn\_name

## <a name="name-affixes"></a>Affissi nome

Questo modello sincronizza i dati di riferimento degli affissi nome sia dei clienti che dei fornitori tra Finance and Operations e altre app Dynamics 365.

<!-- ![](media/dual-write-name-affixes.png) -->

Campo di origine | Tipo di mappa | Campo di destinazione
---|---|---
AFFIX | = | msdyn\_affix
TIPO | \>\< | msdyn\_affixtype
DESCRIZIONE | = | msdyn\_description
