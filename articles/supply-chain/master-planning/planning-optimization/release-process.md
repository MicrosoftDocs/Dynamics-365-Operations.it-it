---
title: Processo di rilascio di Ottimizzazione pianificazione e cronologia dei rilasci
description: Questo argomento fornisce informazioni sul processo di rilascio e sulla cronologia dei rilasci per Ottimizzazione pianificazione.
author: crytt
ms.date: 7/28/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2021-07-28
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 64c8cd3ed6ff522a9ef90831ae502c5d50fbc05816aaa764d2a8e122934fc2bb
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6722393"
---
# <a name="planning-optimization-release-process-and-release-history"></a>Processo di rilascio di Ottimizzazione pianificazione e cronologia dei rilasci

[!include [banner](../../includes/banner.md)]

Microsoft aggiorna Ottimizzazione pianificazione su base mensile. Tuttavia, in base ai requisiti aziendali, occasionalmente rilasciamo aggiornamenti aggiuntivi tra le versioni pianificate.

Ogni versione viene pubblicata nelle singole aree in cui è disponibile Ottimizzazione pianificazione. Il processo richiede in genere tre giorni.

Durante l'aggiornamento di Ottimizzazione pianificazione la pianificazione generale potrebbe essere un po' più lenta del solito.

Gli ambienti che utilizzano Ottimizzazione pianificazione ricevono automaticamente la versione più recente. Non è richiesta alcuna azione da parte dell'utente: il servizio viene aggiornato automaticamente. Tuttavia, nessuna funzionalità di modifica sostanziale viene mai automaticamente inviata agli ambienti. Per impostazione predefinita, tutte le modifiche considerate sostanziali sono disattivate e devono essere attivate esplicitamente utilizzando la [gestione delle funzionalità](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md). Pertanto, tali modifiche non verranno visualizzate negli ambienti finché non si sceglie di abilitarle.

Poiché le notifiche non vengono visualizzate quando Ottimizzazione pianificazione viene aggiornato nel tuo ambiente, puoi rivedere le note sulla versione nella tabella seguente per determinare quando sono state rilasciate le modifiche e quali funzionalità hanno introdotto. Questa tabella mostra le modifiche rilasciate per Ottimizzazione pianificazione, se tali modifiche sono associate a una funzionalità della gestione delle funzionalità e la data di rilascio.

| Modifiche | Dettagli della gestione funzionalità | Data rilascio |
|---|---|---|
| <p>Requisiti del tipo di risorsa per la pianificazione della capacità infinita</p><p>Efficienza delle risorse ed efficienza del calendario per una pianificazione della capacità infinita</p><p>Per ulteriori informazioni, vedi [Programmazione con capacità infinita](infinite-capacity-planning.md). | <p>Disponibile nella gestione delle funzionalità a partire dalla versione 10.0.20.</p><p>Nome della funzionalità: *Programmazione capacità infinita per Ottimizzazione pianificazione*</p> | 6 luglio 2021 |
| Miglioramenti generali della qualità | Non è richiesta alcuna gestione delle funzionalità. | 6 luglio 2021 |

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
