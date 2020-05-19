---
title: Funzionalità rimosse o deprecate in Dynamics 365 Commerce
description: In questo argomento vengono descritte le funzionalità rimosse, o di cui è stata progettata la rimozione da Dynamics 365 Commerce.
author: josaw
manager: AnnBe
ms.date: 05/04/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2020-04-30
ms.dyn365.ops.version: Platform update 33
ms.openlocfilehash: c47c5430a8f5d67e13c95db609a95d5ad66933ae
ms.sourcegitcommit: a8b6cd799eddaf5be9aec9ea3c2b55e2c3231652
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/05/2020
ms.locfileid: "3335278"
---
# <a name="removed-or-deprecated-features-in-dynamics-365-commerce"></a>Funzionalità rimosse o deprecate in Dynamics 365 Commerce

[!include [banner](../includes/banner.md)]

In questo argomento vengono descritte le funzionalità rimosse, o di cui è stata progettata la rimozione da Dynamics 365 Commerce.

- Una funzionalità *rimossa* non è più disponibile nel prodotto.
- Una funzionalità *deprecata* non si trova nella fase attiva di sviluppo e potrebbe essere rimossa in un aggiornamento futuro.

Questo elenco ha lo scopo di aiutare a tenere in considerazione queste rimozioni e deprecazioni per la pianificazione. 

> [!NOTE]
> Informazioni dettagliate sugli oggetti nella app Finance and Operations sono disponibili nei [Report tecnici di riferimento](https://mbs.microsoft.com/customersource/northamerica/AX/downloads/reports/axtechrefrep). È possibile confrontare le diverse versioni dei report per ottenere informazioni sugli oggetti che sono stati modificati o rimossi in ogni versione delle app Finance and Operations.

## <a name="features-removed-or-deprecated-in-the-commerce-10010-release"></a>Funzionalità rimosse o deprecate nella versione Commerce 10.0.10
### <a name="pos-operation-803---picking-and-receiving"></a>Operazione POS 803 - Fare clic su Prelievo e ricevimento
|   |  |
|------------|--------------------|
| **Motivo del deprecamento/rimozione** | Le operazioni di prelievo e ricevimento sono deprecate a causa della ridefinizione di nuove operazioni. |
| **Sostituita da un'altra funzionalità?**   | Sì. È sostituita da due nuove operazioni POS: operazione in entrata (804) e operazione in uscita (805).|
| **Aree del prodotto interessate**         | Applicazione POS (Point of sale) |
| **Opzione di distribuzione**              | Tutti |
| **Stato**                         | Deprecata: dalla versione 10.0.10 l'operazione di prelievo e ricevimento non riceverà più alcun nuovo aggiornamento delle funzionalità. Solo le correzioni di bug critici verranno eseguite per questa operazione nelle versioni future. Tutti i clienti sono incoraggiati a passare alle nuove [operazioni in entrata](https://docs.microsoft.com/dynamics365/commerce/pos-inbound-inventory-operation) e [operazioni in uscita](https://docs.microsoft.com/dynamics365/commerce/pos-outbound-inventory-operation), che continueranno a far parte della nostra roadmap di prodotti a lungo termine. |


## <a name="features-removed-or-deprecated-in-the-commerce-1007-release"></a>Funzionalità rimosse o deprecate nella versione Commerce 10.0.7
### <a name="commerce-getproductavailabilities-and-getavailableinventorynearby-apis"></a>API Commerce GetProductAvailabilities e GetAvailableInventoryNearby
|   |  |
|------------|--------------------|
| **Motivo del deprecamento/rimozione** | Nuove API ottimizzate sono state create per sostituire le API GetProductAvailabilities e GetAvailableInventoryNearby. |
| **Sostituita da un'altra funzionalità?**   | Sì: sostituzione tramite le API GetEstimatedAvailabilty e GetEstimatedProductWarehouseAvailability. |
| **Aree del prodotto interessate**         | SDK dell'applicazione e-Commerce |
| **Opzione di distribuzione**              | Tutti |
| **Stato**                         | Obsoleta: dalla versione 10.0.7 non verranno più eseguiti gli investimenti tecnici messi in atto per GetProductAvailabilities e GetAvailableInventoryNearby. Le organizzazioni che utilizzano queste API nelle loro distribuzioni e-Commerce devono passare alle nuove API GetEstimatedAvailability e GetEstimatedProductWarehouseAvailability e abilitare la [funzionalità di calcolo della disponibilità del prodotto ottimizzata](https://docs.microsoft.com/dynamics365/commerce/calculated-inventory-retail-channels).  |

## <a name="previous-announcements-about-removed-or-deprecated-features"></a>Annunci precedenti sulle funzionalità rimosse o deprecate
Per ulteriori informazioni sulle funzionalità che sono state rimosse o deprecate nelle versioni precedenti, vedere [Funzionalità rimosse o deprecate nelle versioni precedenti](../../fin-ops-core/dev-itpro/migration-upgrade/deprecated-features.md?toc=/dynamics365/commerce/toc.json).
