---
title: Dati master fornitori integrati
description: In questo argomento viene descritta l'integrazione dei dati dei fornitori tra le app Finance and Operations e Dataverse.
author: RamaKrishnamoorthy
ms.date: 07/15/2019
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: fce5e072d39533fa5d54fe34e90c7aca9d01d67e
ms.sourcegitcommit: 9acfb9ddba9582751f53501b82a7e9e60702a613
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/10/2021
ms.locfileid: "7782479"
---
# <a name="integrated-vendor-master"></a>Dati master fornitori integrati

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Il termine *fornitore* si riferisce a un'organizzazione fornitore o a un unico proprietario che fornisce beni o servizi a un'azienda. Sebbene *fornitore* sia un concetto cardine in Microsoft Dynamics 365 Supply Chain Management, non esiste un concetto di fornitore nelle app customer engagement. Tuttavia, è possibile sovraccaricare la tabella **Account/Contatto** per memorizzare le informazioni sul fornitore. Il master fornitore integrato introduce un concetto di fornitore esplicito nelle app customer engagement. È possibile utilizzare il nuovo progetto del fornitore o archiviare i dati del fornitore nella tabella **Account/Contatto**. La doppia scrittura supporta entrambi gli approcci.

In entrambi gli approcci, i dati del fornitore sono integrati in Dynamics 365 Supply Chain Management, Dynamics 365 Sales, Dynamics 365 Field Service e nei portali Power Apps. In Supply Chain Management, i dati sono disponibili per flussi di lavoro come richieste di acquisto e ordini di acquisto.

## <a name="vendor-data-flow"></a>Flusso di dati fornitore

È possibile utilizzare il nuovo progetto del fornitore se non si desidera archiviare i dati del fornitore nella tabella **Account/Contatto** in Dataverse.

![Flusso di dati fornitore.](media/dual-write-vendor-data-flow.png)

È possibile utilizzare il progetto del fornitore esteso se si desidera continuare ad archiviare i dati del fornitore nella tabella **Account/Contatto**. Per utilizzare il progetto esteso del fornitore, è necessario configurare i flussi di lavoro del fornitore nel pacchetto della soluzione di doppia scrittura. Per ulteriori informazioni, vedere [Passare da un progetto del fornitore all'altro](vendor-switch.md).

![Flusso di dati esteso fornitore.](media/dual-write-vendor-detail.jpg)

> [!TIP]
> Se si usano i portali Power Apps per i fornitori self-service, le informazioni sui fornitori possono essere inviate direttamente alle app Finance and Operations.

## <a name="templates"></a>Modelli

I dati dei fornitori includono tutte le informazioni sul fornitore, ad esempio il gruppo di fornitori, indirizzi, informazioni di contatto, il profilo di pagamento, il profilo fattura. Una raccolta di mappe della tabella funziona in combinazione durante l'interazione con i dati dei fornitori, come illustrato nella seguente tabella.

App Finance and Operations | App di interazione con i clienti     | descrizione
----------------------------|-----------------------------|------------
[Contatti CDS V2](mapping-reference.md#115) | contatti | Questo modello sincronizza tutte le informazioni di contatto primarie, secondarie e terziarie, sia per i clienti che per i fornitori.
[Affissi nome](mapping-reference.md#155) | msdyn_nameaffixes | Questo modello sincronizza i dati di riferimento degli affissi nome per clienti e fornitori.
[Righe giorno di pagamento - CDS V2](mapping-reference.md#157) | msdyn_paymentdaylines | Questo modello sincronizza i dati di riferimento delle righe giorni di pagamento per clienti e fornitori.
[Giorni di pagamento - CDS](mapping-reference.md#158) | msdyn_paymentdays | Questo modello sincronizza i dati di riferimento dei giorni di pagamento per clienti e fornitori.
[Righe scadenzario pagamenti](mapping-reference.md#159) | msdyn_paymentschedulelines | Sincronizza i dati di riferimento delle righe scadenzario pagamenti per clienti e fornitori.
[Scadenzario pagamenti](mapping-reference.md#160) | msdyn_paymentschedules | Questo modello sincronizza i dati di riferimento dello scadenzario pagamenti per clienti e fornitori.
[Termini di pagamento](mapping-reference.md#161) | msdyn_paymentterms | Questo modello sincronizza i dati di riferimento dei termini di pagamento per clienti e fornitori.
[Fornitori V2](mapping-reference.md#202) | msdyn_vendors | Le società che utilizzano una soluzione personalizzata per i fornitori possono sfruttare il concetto di fornitore predefinito introdotto in Dataverse a causa dell'integrazione con le app Finance and Operations.
[Gruppi di fornitori](mapping-reference.md#200) | msdyn_vendorgroups | Questo modello sincronizza le informazioni del gruppo di fornitori.
[Metodo di pagamento fornitore](mapping-reference.md#201) | msdyn_vendorpaymentmethods | Questo modello sincronizza le informazioni del metodo di pagamento dei fornitori.

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
