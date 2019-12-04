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
ms.openlocfilehash: da451c63c23444da564307505d38699faf9df19a
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/06/2019
ms.locfileid: "2770989"
---
# <a name="integrated-vendor-master"></a>Gestione integrata dei dati dei fornitori

[!include [banner](../includes/banner.md)]

Il termine *fornitore* si riferisce a un'organizzazione fornitrice o a un titolare unico che fa parte del processo della supply chain e che fornisce merci per l'azienda. Sebbene *fornitore* sia un concetto cardine nelle app Finance and Operations, un concetto di fornitore non è presente in altre app Dynamics 365. Invece, alcune aziende sovraccaricano l'entità Conto per archiviare sia le informazioni relative ai clienti che ai fornitori. Altre aziende utilizzano un concetto personalizzato di fornitore. L'integrazione con Common Data Service supporta entrambi gli approcci. Di conseguenza, è possibile abilitare l'uno o l'altro, a seconda del scenario aziendali.

L'integrazione di dati fornitore tra le app Finance and Operations e altre app Dynamics 365 consente la gestione complessa di tutti i dati. Indipendentemente dall'origine dei dati fornitore, questi vengono integrati in background tra applicazioni e nonostante le differenze dell'infrastruttura. 

### <a name="vendor-data-flow"></a>Flusso di dati fornitore

Se si desidera utilizzare altre app Dynamics 365 per la gestione dei fornitori e si desidera isolare le informazioni sui fornitori da quelle sui cliente, è possibile utilizzare la nuova struttura fornitori.

![Flusso di dati fornitore](media/dual-write-vendor-data-flow.png)

Se si desidera utilizzare altre app Dynamics 365 per la gestione dei fornitori e si desidera continuare a usare l'entità Conto per archiviare le informazioni sui fornitori, è possibile utilizzare la nuova struttura fornitori estesa. In questa struttura, le informazioni estese del fornitore, ad esempio il gruppo di fornitori e il profilo di registrazione fornitore, vengono archiviate nei dettagli del fornitore.

![Flusso di dati esteso fornitore](media/dual-write-vendor-detail.jpg)

Le informazioni di contatto del fornitore somigliano alle informazioni di contatto del cliente. In background, le informazioni del contatto vengono archiviate e recuperate dalle stesse entità.

## <a name="templates"></a>Modelli

I dati dei fornitori includono tutte le informazioni sul fornitore, ad esempio il gruppo di fornitori, indirizzi, informazioni di contatto, il profilo di pagamento, il profilo fattura. Una raccolta di mappe di entità funziona in combinazione durante l'interazione con i dati dei fornitori, come illustrato nella seguente tabella.

App Finance and Operations | Altre app Dynamics 365         | Descrizione
----------------------------|---------------------------------|------------
Fornitore V2               | Account | Le società che utilizzano l'entità Conto per archiviare le informazioni sui fornitori possono continuare a usarlo nello stesso modo. Possono inoltre sfruttare la funzionalità fornitore esplicita imminente con l'integrazione delle app Finance and Operations.
Fornitore V2               | Msdyn\_vendors | Le società che utilizzano una soluzione personalizzata per i fornitori possono sfruttare il concetto di fornitore predefinito introdotto in Common Data Service a causa dell'integrazione con le app Finance and Operations. 
Gruppi di fornitori | msdyn_vendorgroups | Questo modello sincronizza le informazioni del gruppo di fornitori.
Metodo di pagamento fornitore | msdyn_vendorpaymentmethods | Questo modello sincronizza le informazioni del metodo di pagamento dei fornitori.
Contatti CDS V2             | contatti                        | Il modello [contatti](dual-write-customer.md#cds-contacts-v2-to-contacts) sincronizza tutte le informazioni di contatto primarie, secondarie e terziarie, sia per i clienti che per i fornitori.
Righe scadenzario pagamenti      | msdyn_paymentschedulelines      | Il modello [righe scadenzario pagamenti](dual-write-customer.md#payment-schedule-lines-to-msdyn_paymentschedulelines) sincronizza i dati di riferimento per clienti e fornitori.
Scadenzario pagamenti            | msdyn_paymentschedules          | Il modello [scadenziari pagamenti](dual-write-customer.md#payment-schedule-to-msdyn_paymentschedules) sincronizza i dati di riferimento degli scadenziari pagamenti per clienti e fornitori.
Righe giorno di pagamento - CDS V2    | msdyn_paymentdaylines           | Il modello [righe giorno di pagamento](dual-write-customer.md#payment-day-lines-cds-v2-to-msdyn_paymentdaylines) sincronizza i dati di riferimento delle righe giorno di pagamento per clienti e fornitori.
Giorni di pagamento - CDS            | msdyn_paymentdays               | Il modello [giorni di pagamento](dual-write-customer.md#payment-days-cds-to-msdyn_paymentdays) sincronizza i dati di riferimento dei giorni di pagamento per clienti e fornitori.
Termini di pagamento            | msdyn_paymentterms              | Il modello [termini di pagamento](dual-write-customer.md#terms-of-payment-to-msdyn_paymentterms) sincronizza i dati di riferimento dei termini di pagamento per clienti e fornitori.
Affissi nome                | msdyn_nameaffixes               | Il modello [affissi nome](dual-write-customer.md#name-affixes-to-msdyn_nameaffixes) sincronizza i dati di riferimento degli affissi nome per clienti e fornitori.

[!include [symbols](../includes/dual-write-symbols.md)]

[!include [Vendors](dual-write/VendorsV2-msdyn-vendors.md)]

[!include [Vendor groups](dual-write/VendVendorGroup-msdyn-vendorgroups.md)]

[!include [Vendor payment methods](dual-write/VendorPaymentMethod-msdyn-vendorpaymentmethods.md)]
