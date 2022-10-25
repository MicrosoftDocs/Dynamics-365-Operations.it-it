---
title: Home page di Intelligence dei dati del sensore
description: Questo articolo fornisce una panoramica di Intelligence dei dati del sensore. Le organizzazioni possono utilizzare questa funzionalità per guidare i processi aziendali in Microsoft Dynamics 365 Supply Chain Management, basato sui segnali Internet delle cose (IoT) provenienti da macchine e apparecchiature nell'area di produzione.
author: johanhoffmann
ms.date: 09/02/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2022-09-02
ms.dyn365.ops.version: 10.0.30
ms.openlocfilehash: ba030364056db8b0524de22aacbc6528ef77813b
ms.sourcegitcommit: 3e04f7e4bc0c29c936dc177d5fa11761a58e9a02
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2022
ms.locfileid: "9689859"
---
# <a name="sensor-data-intelligence-home-page"></a>Home page di Intelligence dei dati del sensore

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]
<!-- KFM: Preview until further notice -->

Intelligence dei dati del sensore per Microsoft Dynamics 365 Supply Chain Management consente alle organizzazioni di guidare i processi aziendali nella gestione della catena di approvvigionamento, sulla base dei segnali Internet delle cose (IoT) provenienti da macchine e apparecchiature nell'area di produzione. È una versione aggiornata e rinominata della funzionalità *Intelligenza IoT* precedentemente disponibile per Supply Chain Management.

Intelligence dei dati del sensore consente di svolgere le attività seguenti:

- Raccogli i dettagli da macchine e attrezzature per aggiornare i valori dei contatori dei cespiti in manutenzione in Supply Chain Management e promuovere la manutenzione predittiva.
- Configura la soluzione utilizzando una semplice procedura guidata di onboarding invece di installare e configurare manualmente i componenti in Microsoft Dynamics Lifecycle Services (LCS).
- Distribuisci i componenti nella tua sottoscrizione, in modo da avere maggiore flessibilità per gestire i componenti di Azure.
- Configura, ridimensiona ed estendi la soluzione come logica aziendale che viene eseguita nei componenti di Azure. Questi componenti sono ora gestiti nella tua sottoscrizione. Pertanto, puoi personalizzarli secondo necessità per soddisfare le tue esigenze aziendali specifiche.

## <a name="business-scenarios"></a>Scenari aziendali

Intelligence dei dati del sensore abilita diversi tipi di funzionalità, ognuna delle quali è rappresentata da uno specifico *scenario* nel sistema. Ciascuno scenario fornisce un insieme specializzato di opzioni di configurazione nel sistema, come dettagliato nella tabella seguente.

| Scenario | Description |
|---|---|
| [Tempo di inattività cespite](sdi-scenario-asset-downtime.md) | Tieni traccia con precisione dell'efficienza dei cespiti macchina utilizzando i dati del sensore per tenere traccia dei tempi di inattività della macchina. |
| [Manutenzione del cespite](sdi-scenario-asset-maintenance.md) | Riduci al minimo i costi di manutenzione e prolunga la durata dei cespiti migliorando i piani di manutenzione basati sulle letture dei sensori dei punti di controllo critici per i cespiti macchina. |
| [Stato macchina](sdi-scenario-equipment-downtime.md) | Garantisci l'efficienza operativa utilizzando le letture dei sensori per notificare ai pianificatori le interruzioni delle macchine e fornire opzioni per mitigare potenziali ritardi. |
| [Qualità prodotto](sdi-scenario-product-quality.md) | Garantisci la qualità dei batch di prodotti confrontando le letture dei sensori per le proprietà effettive di ciascun batch di prodotti, come umidità, temperatura o metriche di qualità personalizzate. Il sistema avviserà gli utenti quando si verificano deviazioni. |
| [Ritardi produzione](sdi-scenario-production-delays.md) | Utilizza le letture dei sensori per confrontare il tempo di ciclo effettivo con il tempo di ciclo pianificato e avvisa i supervisori quando la produzione non è nei tempi previsti. I supervisori possono quindi intervenire secondo necessità per garantire la massima efficienza operativa. |

## <a name="architecture"></a>Architettura

Il diagramma dell'architettura seguente fornisce una panoramica della soluzione e dei suoi componenti.

![Diagramma dell'architettura di Intelligence dei dati del sensore.](media/sdi-architecture.png "Diagramma dell'architettura di Intelligence dei dati del sensore")
