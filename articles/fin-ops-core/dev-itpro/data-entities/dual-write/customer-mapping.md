---
title: Gestione integrata dei dati dei clienti
description: In questo argomento viene descritta l'integrazione dei dati dei clienti tra Finance and Operations e Dataverse.
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
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: b7e9cd27bb918dc3a6088b45803329deb01a864e
ms.sourcegitcommit: 7e1be696894731e1c58074d9b5e9c5b3acf7e52a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/17/2020
ms.locfileid: "4744403"
---
# <a name="integrated-customer-master"></a>Dati master clienti integrati

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]


I dati dei clienti possono essere masterizzati in più di un'applicazione Dynamics 365. Ad esempio, una riga del cliente può avere origine dall'attività di vendita in Dynamics 365 Sales (un'app basata su modello in Dynamics 365) o una riga può avere origine dall'attività di vendita al dettaglio in Dynamics 365 Commerce (un'app Finance and Operations). Indipendentemente da dove provengano i dati dei clienti, questi vengono integrati in background. Dati master clienti integrati ti offre la flessibilità di gestire i dati dei clienti in qualsiasi applicazione Dynamics 365 e offre una visione completa del cliente con la suite di applicazioni Dynamics 365.

## <a name="customer-data-flow"></a>Flusso dei dati dei clienti

*Cliente* è un concetto ben definito nelle applicazioni. Di conseguenza, l'integrazione dei dati dei clienti implica solo armonizzare il concetto di cliente tra due applicazioni. L'illustrazione seguente mostra il flusso dei dati dei clienti.

![Flusso dei dati dei clienti](media/dual-write-customer-data-flow.png)

I clienti possono essere classificati largamente in due tipi: clienti commerciali/aziendali e consumatori/utenti finali. Questi due tipi di clienti vengono archiviati e gestiti in modo diverso in Finance and Operations e Dataverse.

In Finance and Operations, sia i clienti commerciali/aziendali che i consumatori/utenti finali vengono gestiti in un'unica tabella denominata **CustTable** (CustCustomerV3Entity) e vengono classificati in base all'attributo **Tipo**. Se **Tipo** è impostato su **Organizzazione**, il cliente è cliente commerciale/aziendale e se **Tipo** è impostato su **Persona**, il cliente è un consumatore/utente finale. Le informazioni principali del contatto vengono gestite tramite la tabella SMMContactPersonEntity.

In Dataverse, i clienti commerciali/aziendali sono gestiti nella tabella Conto e vengono identificati come clienti quando l'attributo **RelationshipType** è impostato su **Cliente**. Sia i consumatori/utenti finali che il contatto sono rappresentati dalla tabella Contatto. Per fornire una netta separazione tra un consumatore/utente finale e un contatto, la tabella **Contatto** include un flag booleano **Di vendita**. Se **Di vendita** è **True**, il contatto è un consumatore/utente finale e offerte e gli ordini possono essere creati per quel contatto. Se **Di vendita** è **False**, il contatto è solo un contatto principale di un cliente.

Quando un contatto non di vendita partecipa a un processo di ordine o offerta, **Di vendita** è impostato su **True** per contrassegnare il contatto come contatto di vendita. Un contatto che è diventato un contatto di vendita rimane tale.

## <a name="templates"></a>Modelli

I dati dei clienti includono tutte le informazioni sul cliente, ad esempio il gruppo di clienti, indirizzi, informazioni di contatto, il profilo di pagamento, il profilo fattura e lo stato del programma fedeltà. Una raccolta di mappe della tabella funziona in combinazione durante l'interazione con i dati dei clienti, come illustrato nella seguente tabella.

App di Finance and Operations | Altre app Dynamics 365         | Descrizione
----------------------------|---------------------------------|------------
Contatti CDS V2             | contatti                        | Questo modello sincronizza tutte le informazioni di contatto primarie, secondarie e terziarie, sia per i clienti che per i fornitori.
Gruppi di clienti             | msdyn_customergroups            | Questo modello sincronizza le informazioni del gruppo di clienti.
Metodo di pagamento clienti     | msdyn_customerpaymentmethods    | Questo modello sincronizza le informazioni del metodo di pagamento dei clienti.
Clienti V3                | conti                        | Questo modello sincronizza le informazioni sui dati master i clienti commerciali e aziendali.
Clienti V3                | contatti                        | Questo modello sincronizza i dati master per i clienti e gli utenti finali.
Affissi nome                | msdyn_nameaffixes               | Questo modello sincronizza i dati di riferimento degli affissi nome per clienti e fornitori.
Righe giorno di pagamento - CDS V2    | msdyn_paymentdaylines           | Questo modello sincronizza i dati di riferimento delle righe giorni di pagamento per clienti e fornitori.
Giorni di pagamento - CDS            | msdyn_paymentdays               | Questo modello sincronizza i dati di riferimento dei giorni di pagamento per clienti e fornitori.
Righe scadenzario pagamenti      | msdyn_paymentschedulelines      | Sincronizza i dati di riferimento delle righe scadenzario pagamenti per clienti e fornitori.
Scadenzario pagamenti            | msdyn_paymentschedules          | Questo modello sincronizza i dati di riferimento dello scadenzario pagamenti per clienti e fornitori.
Termini di pagamento            | msdyn_paymentterms              | Questo modello sincronizza i dati di riferimento dei termini di pagamento per clienti e fornitori.

[!include [banner](../../includes/dual-write-symbols.md)]

[!include [mapping contacts contacts](includes/CDSContactsV2-contacts.md)]

[!include [mapping customer group](includes/CustCustomerGroup-msdyn-customergroups.md)]

[!include [mapping customer payment method](includes/CustomerPaymentMethod-msdyn-customerpaymentmethods.md)]

[!include [mapping customer accounts](includes/CustomersV3-accounts.md)]

[!include [mapping customer contacts](includes/CustomersV3-contacts.md)]

[!include [mapping name affixes](includes/NameAffixes-msdyn-nameaffixes.md)]

[!include [mapping payment day lines](includes/PaymentDayLinesCdsV2-msdyn-paymentdaylines.md)]

[!include [mapping payment days](includes/PaymentDaysCds-msdyn-paymentdays.md)]

[!include [mapping payment schedule lines](includes/PaymentScheduleLines-msdyn-paymentschedulelines.md)]

[!include [mapping payment schedules](includes/PaymentSchedules-msdyn-paymentschedules.md)]

[!include [mapping terms of payment](includes/TermsofPayment-msdyn-paymentterms.md)]


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]