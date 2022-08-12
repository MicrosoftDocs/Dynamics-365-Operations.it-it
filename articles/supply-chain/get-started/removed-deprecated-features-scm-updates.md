---
title: Funzionalità rimosse o deprecate in Dynamics 365 Supply Chain Management
description: In questo articolo vengono descritte le funzionalità rimosse, o di cui è stata progettata la rimozione in Dynamics 365 Supply Chain Management.
author: kamaybac
ms.date: 04/27/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2020-03-03
ms.dyn365.ops.version: Platform update 33
ms.openlocfilehash: 7c7dd90fea79ae83d238ed51b9ec1fc42e9e36b2
ms.sourcegitcommit: f2501d93ffc1c7bf4e0daa78e63bc37528ef2358
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/18/2022
ms.locfileid: "9171517"
---
# <a name="removed-or-deprecated-features-in-dynamics-365-supply-chain-management"></a>Funzionalità rimosse o deprecate in Dynamics 365 Supply Chain Management

[!include [banner](../includes/banner.md)]

Questo articolo verrà aggiornato man mano che vengono documentate le nuove funzionalità rimosse o deprecate in Dynamics 365 Supply Chain Management.

- Una funzionalità *rimossa* non è più disponibile nel prodotto.
- Una funzionalità *deprecata* non si trova nella fase attiva di sviluppo e potrebbe essere rimossa in un aggiornamento futuro.

Questo elenco ha lo scopo di aiutare a tenere in considerazione queste rimozioni e deprecazioni per la pianificazione.

> [!NOTE]
> Informazioni dettagliate sugli oggetti nelle app per la finanza e le operazioni sono disponibili nei [Report tecnici di riferimento](/dynamics/s-e/). È possibile confrontare le diverse versioni dei report per ottenere informazioni sugli oggetti che sono stati modificati o rimossi in ogni versione delle app per la finanza e le operazioni.


## <a name="features-removed-or-deprecated-in-the-supply-chain-management-10019-release"></a>Funzionalità rimosse o deprecate nella versione Supply Chain Management 10.0.19

### <a name="job-card-device"></a>Dispositivo schede processo

| &nbsp;  | &nbsp;  |
|---|---|
| **Motivo della deprecazione/rimozione** | Il [dispositivo scheda processo](../production-control/config-job-card-device.md) viene sostituito dalla nuova [interfaccia di esecuzione dell'area di produzione](../production-control/production-floor-execution-configure.md). |
| **Sostituita da un'altra funzionalità?**   | Sì, il [dispositivo scheda processo](../production-control/config-job-card-device.md) viene sostituito dalla nuova [interfaccia di esecuzione dell'area di produzione](../production-control/production-floor-execution-configure.md). |
| **Aree del prodotto interessate** | Supply Chain Management - controllo della produzione |
| **Opzione di distribuzione** | Cloud e locale |
| **Stato** | Deprecato. Il dispositivo scheda di processo riceverà supporto con correzioni di bug e sicurezza, ma non verranno più forniti miglioramenti delle funzionalità. Dopo aprile 2022, il dispositivo scheda di processo non sarà più supportato e ai clienti verrà chiesto di passare alla nuova interfaccia di esecuzione dell'area di produzione. |

## <a name="features-removed-or-deprecated-in-the-supply-chain-management-10018-release"></a>Funzionalità rimosse o deprecate nella versione Supply Chain Management 10.0.18

### <a name="supply-chain-management--warehousing-the-warehouse-app"></a><a name="wma"></a>Supply Chain Management- Warehousing (app di magazzino)

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo della deprecazione/rimozione** | A partire da aprile 2021, *Supply Chain Management - Warehousing* (app di magazzino) è deprecata e non sarà supportata dopo aprile 2022. È ora sostituita dall'*App per dispositivi mobili Gestione magazzino*, rilasciata con la versione 10.0.17 di Supply Chain Management. La nuova app è una sostituzione completa ma utilizza lo stesso framework sottostante, il che semplifica la migrazione. Se necessario, le due app possono essere utilizzate contemporaneamente per aiutare gli utenti ad adattarsi gradualmente mentre imparano a utilizzare la nuova app.<br><br>Per ulteriori informazioni sulla nuova app per dispositivi mobili Gestione magazzino vedi [Applicazione per dispositivi mobili per la gestione del magazzino](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/warehouse-management-mobile-application) e [Installare e connettere l'app per dispositivi mobili Gestione magazzino](../warehousing/install-configure-warehouse-management-app.md). |
| **Sostituita da un'altra funzionalità?**   | Sì, sostituita dalla nuova app per dispositivi mobili Gestione magazzino. |
| **Aree del prodotto interessate**         | Supply Chain Management - app di magazzino |
| **Opzione di distribuzione**              | Cloud e locale |
| **Stato**                         | Deprecato. L'app di magazzino riceverà supporto con correzioni di bug e sicurezza, ma non verranno più forniti miglioramenti delle funzionalità. Dopo l'aprile 2022, la vecchia app di magazzino non sarà più supportata e ai clienti verrà chiesto di passare alla nuova app per dispositivi mobili Gestione magazzino. La vecchia app di magazzino verrà quindi rimossa da Microsoft Store e Google Play Store.  |

## <a name="features-removed-or-deprecated-in-the-supply-chain-management-10015-release"></a>Funzionalità rimosse o deprecate nella versione Supply Chain Management 10.0.15

### <a name="internet-explorer-11-support-for-dynamics-365-is-deprecated"></a>Il supporto di Internet Explorer 11 per Dynamics 365 è deprecato

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo della deprecazione/rimozione** | A partire da dicembre 2020, il supporto di Microsoft Internet Explorer 11 per tutti i prodotti Dynamics 365 è deprecato e Internet Explorer 11 non sarà supportato dopo agosto 2021.<br><br>Ciò avrà un impatto sui clienti che utilizzano prodotti Dynamics 365 progettati per essere utilizzati tramite un'interfaccia Internet Explorer 11. Dopo agosto 2021, Internet Explorer 11 non sarà supportato per questi prodotti Dynamics 365. |
| **Sostituita da un'altra funzionalità?**   | Consigliamo ai clienti di passare a Microsoft Edge.|
| **Aree del prodotto interessate**         | Tutti i prodotti Dynamics 365 |
| **Opzione di distribuzione**              | Tutti|
| **Stato**                         | Deprecato. Internet Explorer 11 non sarà supportato dopo agosto 2021.|

### <a name="use-of-built-in-supply-chain-management-master-planning-engine-for-manufacturing-scenarios"></a>Utilizzare il motore di pianificazione generale di Supply Chain Management incorporato per gli scenari di produzione

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo della deprecazione/rimozione** | Per migliorare le prestazioni e ridurre al minimo il carico del database SQL durante le esecuzioni di pianificazione generale, il motore di pianificazione generale di Supply Chain Management incorporato viene sostituito dall'ottimizzazione pianificazione. L'ottimizzazione di pianificazione consente le esecuzioni di pianificazione rapide anche durante l'orario di ufficio. I pianificatori possono in questo modo rispondere immediatamente ai cambiamenti nella domanda e nei parametri di pianificazione. |
| **Sostituita da un'altra funzionalità?**   | Sì, l'ottimizzazione di pianificazione sostituirà l'attuale motore di pianificazione generale di Supply Chain Management incorporato. |
| **Aree del prodotto interessate**         | Supply Chain Management - Pianificazione master |
| **Opzione di distribuzione**              | Solo cloud. L'ottimizzazione di pianificazione non è supportata con le distribuzioni locali. |
| **Stato**                         | Deprecato. Entro il 1° aprile 2022 gli scenari di produzione non saranno più supportati per il motore di pianificazione generale di Supply Chain Management integrato. Da quella data, Microsoft interromperà tutti gli sviluppi attivi negli scenari di produzione per il motore di pianificazione integrato, non rilascerà nuove funzionalità e rilascerà solo risoluzioni ai bug critici. Dopo tale data, tutte le aziende che necessitano di assistenza per gli scenari di produzione devono usare Ottimizzazione pianificazione per il calcolo della pianificazione master. Ottimizzazione pianificazione dovrà supportare completamente gli scenari di produzione da Ottobre 2022. Per ulteriori informazioni, vedi [Panoramica di Ottimizzazione pianificazione](../master-planning/planning-optimization/planning-optimization-overview.md).<br><br>Le aziende con implementazioni locali di Supply Chain Management possono continuare a utilizzare il motore di pianificazione integrato per gli scenari di produzione dopo il mese di aprile 2022. Non verranno tuttavia forniti ulteriori miglioramenti delle funzionalità. |

## <a name="features-removed-or-deprecated-in-the-supply-chain-management-10011-release"></a>Funzionalità rimosse o deprecate nella versione Supply Chain Management 10.0.11

### <a name="use-of-built-in-supply-chain-management-master-planning-engine-for-distribution-scenarios"></a>Utilizzare il motore di pianificazione generale di Supply Chain Management incorporato per gli scenari di distribuzione

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo della deprecazione/rimozione** | Per migliorare le prestazioni e ridurre al minimo il carico del database SQL durante le esecuzioni di pianificazione generale, il motore di pianificazione generale di Supply Chain Management incorporato viene sostituito dall'ottimizzazione pianificazione. L'ottimizzazione di pianificazione consente le esecuzioni di pianificazione rapide anche durante l'orario di ufficio. I pianificatori possono in questo modo rispondere immediatamente ai cambiamenti nella domanda e nei parametri di pianificazione. |
| **Sostituita da un'altra funzionalità?**   | Sì, l'ottimizzazione di pianificazione sostituirà l'attuale motore di pianificazione generale di Supply Chain Management incorporato. |
| **Aree del prodotto interessate**         | Supply Chain Management - Pianificazione master |
| **Opzione di distribuzione**              | Solo cloud. L'ottimizzazione di pianificazione non è supportata con le distribuzioni locali. |
| **Stato**                         | Deprecato. Entro il 1° aprile 2021 gli scenari di distribuzione non saranno più supportati con il motore di pianificazione generale Dynamics 365 Supply Chain Management. Per gli scenari di distribuzione, i clienti devono utilizzare l'ottimizzazione di pianificazione per i calcoli della pianificazione generale. Per ulteriori informazioni, vedere [Panoramica dell'ottimizzazione di pianificazione](../master-planning/planning-optimization/planning-optimization-overview.md). I clienti con implementazioni locali di Dynamics 365 Supply Chain Management possono continuare a utilizzare il motore di pianificazione generale di Supply Chain Management per gli scenari di distribuzione dopo il mese di aprile 2021. Non verranno tuttavia forniti ulteriori miglioramenti delle funzionalità. |

## <a name="previous-announcements-about-removed-or-deprecated-features"></a>Annunci precedenti sulle funzionalità rimosse o deprecate

Per ulteriori informazioni sulle funzionalità che sono state rimosse o deprecate nelle versioni precedenti, vedere [Funzionalità rimosse o deprecate nelle versioni precedenti](../../fin-ops-core/dev-itpro/migration-upgrade/deprecated-features.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]

