---
title: Dati master fornitori integrati
description: In questo argomento viene descritta l'integrazione dei dati dei fornitori tra le app Finance and Operations e Dataverse.
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
ms.openlocfilehash: 636bc57b5ef09d605744f4857fd5fbefceac4875
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/05/2020
ms.locfileid: "4685487"
---
# <a name="integrated-vendor-master"></a>Dati master fornitori integrati

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]



Il termine *fornitore* si riferisce a un'organizzazione fornitore o a un unico proprietario che fornisce beni o servizi a un'azienda. Sebbene *fornitore* sia un concetto cardine in Microsoft Dynamics 365 Supply Chain Management, non esiste un concetto di fornitore nelle app basate su modello in Dynamics 365. Tuttavia, è possibile sovraccaricare l'entità **Account/Contatto** per memorizzare le informazioni sul fornitore. Il master fornitore integrato introduce un concetto di fornitore esplicito nelle app basate su modello in Dynamics 365. È possibile utilizzare il nuovo progetto del fornitore o archiviare i dati del fornitore nell'entità **Account/Contatto**. La doppia scrittura supporta entrambi gli approcci.

In entrambi gli approcci, i dati del fornitore sono integrati in Dynamics 365 Supply Chain Management, Dynamics 365 Sales, Dynamics 365 Field Service e nei portali Power Apps. In Supply Chain Management, i dati sono disponibili per flussi di lavoro come richieste di acquisto e ordini di acquisto.

## <a name="vendor-data-flow"></a>Flusso di dati fornitore

È possibile utilizzare il nuovo progetto del fornitore se non si desidera archiviare i dati del fornitore nell'entità **Account/Contatto** in Dataverse.

![Flusso di dati fornitore](media/dual-write-vendor-data-flow.png)

È possibile utilizzare il progetto del fornitore esteso se si desidera continuare ad archiviare i dati del fornitore nell'entità **Account/Contatto**. Per utilizzare il progetto esteso del fornitore, è necessario configurare i flussi di lavoro del fornitore nel pacchetto della soluzione di doppia scrittura. Per ulteriori informazioni, vedere [Passare da un progetto del fornitore all'altro](vendor-switch.md).

![Flusso di dati esteso fornitore](media/dual-write-vendor-detail.jpg)

> [!TIP]
> Se si usano i portali Power Apps per i fornitori self-service, le informazioni sui fornitori possono essere inviate direttamente alle app Finance and Operations.

## <a name="templates"></a>Modelli

I dati dei fornitori includono tutte le informazioni sul fornitore, ad esempio il gruppo di fornitori, indirizzi, informazioni di contatto, il profilo di pagamento, il profilo fattura. Una raccolta di mappe della tabella funziona in combinazione durante l'interazione con i dati dei fornitori, come illustrato nella seguente tabella.

App di Finance and Operations | Altre app Dynamics 365     | Descrizione
----------------------------|-----------------------------|------------
Fornitore V2                   | Account                     | Le società che utilizzano l'entità Conto per archiviare le informazioni sui fornitori possono continuare a usarlo nello stesso modo. Possono inoltre sfruttare la funzionalità fornitore esplicita imminente con l'integrazione delle app Finance and Operations.
Fornitore V2                   | Msdyn\_vendors              | Le società che utilizzano una soluzione personalizzata per i fornitori possono sfruttare il concetto di fornitore predefinito introdotto in Dataverse a causa dell'integrazione con le app Finance and Operations. 
Gruppi di fornitori               | msdyn\_vendorgroups         | Questo modello sincronizza le informazioni del gruppo di fornitori.
Metodo di pagamento fornitore       | msdyn\_vendorpaymentmethods | Questo modello sincronizza le informazioni del metodo di pagamento dei fornitori.
Contatti CDS V2             | contatti                    | Il modello [contatti](customer-mapping.md#cds-contacts-v2-to-contacts) sincronizza tutte le informazioni di contatto primarie, secondarie e terziarie, sia per i clienti che per i fornitori.
Righe scadenzario pagamenti      | msdyn\_paymentschedulelines | Il modello [righe scadenzario pagamenti](customer-mapping.md#payment-schedule-lines-to-msdyn_paymentschedulelines) sincronizza i dati di riferimento per clienti e fornitori.
Scadenzario pagamenti            | msdyn\_paymentschedules     | Il modello [scadenziari pagamenti](customer-mapping.md#payment-schedule-to-msdyn_paymentschedules) sincronizza i dati di riferimento degli scadenziari pagamenti per clienti e fornitori.
Righe giorno di pagamento - CDS V2    | msdyn\_paymentdaylines      | Il modello [righe giorno di pagamento](customer-mapping.md#payment-day-lines-cds-v2-to-msdyn_paymentdaylines) sincronizza i dati di riferimento delle righe giorno di pagamento per clienti e fornitori.
Giorni di pagamento - CDS            | msdyn\_paymentdays          | Il modello [giorni di pagamento](customer-mapping.md#payment-days-cds-to-msdyn_paymentdays) sincronizza i dati di riferimento dei giorni di pagamento per clienti e fornitori.
Termini di pagamento            | msdyn\_paymentterms         | Il modello [termini di pagamento](customer-mapping.md#terms-of-payment-to-msdyn_paymentterms) sincronizza i dati di riferimento dei termini di pagamento per clienti e fornitori.
Affissi nome                | msdyn\_nameaffixes          | Il modello [affissi nome](customer-mapping.md#name-affixes-to-msdyn_nameaffixes) sincronizza i dati di riferimento degli affissi nome per clienti e fornitori.

[!include [symbols](../../includes/dual-write-symbols.md)]

[!include [Vendors](includes/VendorsV2-msdyn-vendors.md)]

[!include [Vendor groups](includes/VendVendorGroup-msdyn-vendorgroups.md)]

[!include [Vendor payment methods](includes/VendorPaymentMethod-msdyn-vendorpaymentmethods.md)]


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]