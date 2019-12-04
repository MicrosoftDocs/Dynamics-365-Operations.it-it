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
ms.openlocfilehash: 09d985e5c6816ec0c718aaf418f4e85fb828f1c6
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/06/2019
ms.locfileid: "2769685"
---
# <a name="integrated-customer-master"></a>Gestione integrata dei dati dei clienti

[!include [banner](../includes/banner.md)]

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

App Finance and Operations | Altre app Dynamics 365         | Descrizione
----------------------------|---------------------------------|------------
Contatti CDS V2             | contatti                        | Questo modello sincronizza tutte le informazioni di contatto primarie, secondarie e terziarie, sia per i clienti che per i fornitori.
Gruppi di clienti             | msdyn_customergroups            | Questo modello sincronizza le informazioni del gruppo di clienti.
Metodo di pagamento clienti     | msdyn_customerpaymentmethods    | Questo modello sincronizza le informazioni del metodo di pagamento dei clienti.
Clienti V3                | conti                        | Questo modello sincronizza le informazioni sui dati master i clienti commerciali e aziendali.
Clienti V3                | contatti                        | Questo modello sincronizza i dati master per i clienti e gli utenti finali.
Carta fedeltà                | msdyn_loyaltycards              | Questo modello sincronizza le informazioni della carta fedeltà.
Affissi nome                | msdyn_nameaffixes               | Questo modello sincronizza i dati di riferimento degli affissi nome per clienti e fornitori.
Righe giorno di pagamento - CDS V2    | msdyn_paymentdaylines           | Questo modello sincronizza i dati di riferimento delle righe giorni di pagamento per clienti e fornitori.
Giorni di pagamento - CDS            | msdyn_paymentdays               | Questo modello sincronizza i dati di riferimento dei giorni di pagamento per clienti e fornitori.
Righe scadenzario pagamenti      | msdyn_paymentschedulelines      | Sincronizza i dati di riferimento delle righe scadenzario pagamenti per clienti e fornitori.
Scadenzario pagamenti            | msdyn_paymentschedules          | Questo modello sincronizza i dati di riferimento dello scadenzario pagamenti per clienti e fornitori.
Termini di pagamento            | msdyn_paymentterms              | Questo modello sincronizza i dati di riferimento dei termini di pagamento per clienti e fornitori.

[!include [banner](../includes/dual-write-symbols.md)]

[!include [mapping contacts contacts](dual-write/CDSContactsV2-contacts.md)]

[!include [mapping customer group](dual-write/CustCustomerGroup-msdyn-customergroups.md)]

[!include [mapping customer payment method](dual-write/CustomerPaymentMethod-msdyn-customerpaymentmethods.md)]

[!include [mapping customer accounts](dual-write/CustomersV3-accounts.md)]

[!include [mapping customer contacts](dual-write/CustomersV3-contacts.md)]

[!include [mapping loyalty card](dual-write/LoyaltyCard-msdyn-loyaltycards.md)]

[!include [mapping name affixes](dual-write/NameAffixes-msdyn-nameaffixes.md)]

[!include [mapping payment day lines](dual-write/PaymentDayLinesCdsV2-msdyn-paymentdaylines.md)]

[!include [mapping payment days](dual-write/PaymentDaysCds-msdyn-paymentdays.md)]

[!include [mapping payment schedule lines](dual-write/PaymentScheduleLines-msdyn-paymentschedulelines.md)]

[!include [mapping payment schedules](dual-write/PaymentSchedules-msdyn-paymentschedules.md)]

[!include [mapping terms of payment](dual-write/TermsofPayment-msdyn-paymentterms.md)]
