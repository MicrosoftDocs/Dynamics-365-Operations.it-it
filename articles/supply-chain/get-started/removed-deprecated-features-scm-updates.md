---
title: Funzionalità rimosse o deprecate in Dynamics 365 Supply Chain Management
description: In questo argomento vengono descritte le funzionalità rimosse, o di cui è stata progettata la rimozione in Dynamics 365 Supply Chain Management.
author: kamaybac
manager: tfehr
ms.date: 12/07/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2020-03-03
ms.dyn365.ops.version: Platform update 33
ms.openlocfilehash: 9c91ffcb03793db2f2ef3a9631ab549ace3f735d
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5259093"
---
# <a name="removed-or-deprecated-features-in-dynamics-365-supply-chain-management"></a>Funzionalità rimosse o deprecate in Dynamics 365 Supply Chain Management

[!include [banner](../includes/banner.md)]

Questo argomento verrà aggiornato man mano che vengono documentate le nuove funzionalità rimosse o deprecate in Dynamics 365 Supply Chain Management.

- Una funzionalità *rimossa* non è più disponibile nel prodotto.
- Una funzionalità *deprecata* non si trova nella fase attiva di sviluppo e potrebbe essere rimossa in un aggiornamento futuro.

Questo elenco ha lo scopo di aiutare a tenere in considerazione queste rimozioni e deprecazioni per la pianificazione.

> [!NOTE]
> Informazioni dettagliate sugli oggetti nella app Finance and Operations sono disponibili nei [Report tecnici di riferimento](https://docs.microsoft.com/dynamics/s-e/). È possibile confrontare le diverse versioni dei report per ottenere informazioni sugli oggetti che sono stati modificati o rimossi in ogni versione delle app Finance and Operations.

## <a name="features-removed-or-deprecated-in-the-supply-chain-management-10015-release"></a>Funzionalità rimosse o deprecate nella versione Supply Chain Management 10.0.15

### <a name="internet-explorer-11-support-for-dynamics-365-is-deprecated"></a>Il supporto di Internet Explorer 11 per Dynamics 365 è deprecato

|   |  |
|------------|--------------------|
| **Motivo del deprecamento/rimozione** | A partire da dicembre 2020, il supporto di Microsoft Internet Explorer 11 per tutti i prodotti Dynamics 365 è deprecato e Internet Explorer 11 non sarà supportato dopo agosto 2021.<br><br>Ciò avrà un impatto sui clienti che utilizzano prodotti Dynamics 365 progettati per essere utilizzati tramite un'interfaccia Internet Explorer 11. Dopo agosto 2021, Internet Explorer 11 non sarà supportato per questi prodotti Dynamics 365. |
| **Sostituita da un'altra funzionalità?**   | Consigliamo ai clienti di passare a Microsoft Edge.|
| **Aree del prodotto interessate**         | Tutti i prodotti Dynamics 365 |
| **Opzione di distribuzione**              | Tutti|
| **Stato**                         | Deprecato. Internet Explorer 11 non sarà supportato dopo agosto 2021.|

### <a name="use-of-built-in-supply-chain-management-master-planning-engine-for-manufacturing-scenarios"></a>Utilizzare il motore di pianificazione generale di Supply Chain Management incorporato per gli scenari di produzione

|   |  |
|------------|--------------------|
| **Motivo del deprecamento/rimozione** | Per migliorare le prestazioni e ridurre al minimo il carico del database SQL durante le esecuzioni di pianificazione generale, il motore di pianificazione generale di Supply Chain Management incorporato viene sostituito dall'ottimizzazione pianificazione. L'ottimizzazione di pianificazione consente le esecuzioni di pianificazione rapide anche durante l'orario di ufficio. I pianificatori possono in questo modo rispondere immediatamente ai cambiamenti nella domanda e nei parametri di pianificazione. |
| **Sostituita da un'altra funzionalità?**   | Sì, l'ottimizzazione di pianificazione sostituirà l'attuale motore di pianificazione generale di Supply Chain Management incorporato. |
| **Aree del prodotto interessate**         | Supply Chain Management - Pianificazione master |
| **Opzione di distribuzione**              | Solo cloud. L'ottimizzazione di pianificazione non è supportata con le distribuzioni locali. |
| **Stato**                         | Deprecato. Entro il 1° ottobre 2021 gli scenari di produzione non saranno più supportati con il motore di pianificazione generale Dynamics 365 Supply Chain Management. Per gli scenari di produzione, i clienti devono utilizzare l'ottimizzazione di pianificazione per i calcoli della pianificazione generale. Per ulteriori informazioni, vedere [Panoramica dell'ottimizzazione di pianificazione](https://go.microsoft.com/fwlink/?linkid=2105830). I clienti con implementazioni locali di Dynamics 365 Supply Chain Management possono continuare a utilizzare il motore di pianificazione generale di Supply Chain Management per gli scenari di produzione dopo il mese di ottobre 2021. Non verranno tuttavia forniti ulteriori miglioramenti delle funzionalità. |

## <a name="features-removed-or-deprecated-in-the-supply-chain-management-10011-release"></a>Funzionalità rimosse o deprecate nella versione Supply Chain Management 10.0.11

### <a name="use-of-built-in-supply-chain-management-master-planning-engine-for-distribution-scenarios"></a>Utilizzare il motore di pianificazione generale di Supply Chain Management incorporato per gli scenari di distribuzione

|   |  |
|------------|--------------------|
| **Motivo del deprecamento/rimozione** | Per migliorare le prestazioni e ridurre al minimo il carico del database SQL durante le esecuzioni di pianificazione generale, il motore di pianificazione generale di Supply Chain Management incorporato viene sostituito dall'ottimizzazione pianificazione. L'ottimizzazione di pianificazione consente le esecuzioni di pianificazione rapide anche durante l'orario di ufficio. I pianificatori possono in questo modo rispondere immediatamente ai cambiamenti nella domanda e nei parametri di pianificazione. |
| **Sostituita da un'altra funzionalità?**   | Sì, l'ottimizzazione di pianificazione sostituirà l'attuale motore di pianificazione generale di Supply Chain Management incorporato. |
| **Aree del prodotto interessate**         | Supply Chain Management - Pianificazione master |
| **Opzione di distribuzione**              | Solo cloud. L'ottimizzazione di pianificazione non è supportata con le distribuzioni locali. |
| **Stato**                         | Deprecato. Entro il 1° aprile 2021 gli scenari di distribuzione non saranno più supportati con il motore di pianificazione generale Dynamics 365 Supply Chain Management. Per gli scenari di distribuzione, i clienti devono utilizzare l'ottimizzazione di pianificazione per i calcoli della pianificazione generale. Per ulteriori informazioni, vedere [Panoramica dell'ottimizzazione di pianificazione](https://go.microsoft.com/fwlink/?linkid=2105830). I clienti con implementazioni locali di Dynamics 365 Supply Chain Management possono continuare a utilizzare il motore di pianificazione generale di Supply Chain Management per gli scenari di distribuzione dopo il mese di aprile 2021. Non verranno tuttavia forniti ulteriori miglioramenti delle funzionalità. |

## <a name="previous-announcements-about-removed-or-deprecated-features"></a>Annunci precedenti sulle funzionalità rimosse o deprecate

Per ulteriori informazioni sulle funzionalità che sono state rimosse o deprecate nelle versioni precedenti, vedere [Funzionalità rimosse o deprecate nelle versioni precedenti](../../fin-ops-core/dev-itpro/migration-upgrade/deprecated-features.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]