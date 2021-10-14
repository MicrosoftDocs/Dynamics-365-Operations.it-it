---
title: Processo di rilascio di Ottimizzazione pianificazione e cronologia dei rilasci
description: Questo argomento fornisce informazioni sul processo di rilascio e sulla cronologia dei rilasci per Ottimizzazione pianificazione.
author: ChristianRytt
ms.date: 09/21/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2021-07-28
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: ec1683554e389948a64aee68e4d069be1e93cc1a
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/29/2021
ms.locfileid: "7567345"
---
# <a name="planning-optimization-release-process-and-release-history"></a>Processo di rilascio di Ottimizzazione pianificazione e cronologia dei rilasci

[!include [banner](../../includes/banner.md)]

Microsoft aggiorna Ottimizzazione pianificazione su base mensile. Tuttavia, in base ai requisiti aziendali, occasionalmente rilasciamo aggiornamenti aggiuntivi tra le versioni pianificate.

Ogni versione viene pubblicata nelle singole aree in cui è disponibile Ottimizzazione pianificazione. Il processo richiede in genere tre giorni.

Durante l'aggiornamento di Ottimizzazione pianificazione la pianificazione generale potrebbe essere un po' più lenta del solito.

Gli ambienti che utilizzano Ottimizzazione pianificazione ricevono automaticamente la versione più recente. Non è richiesta alcuna azione da parte dell'utente: il servizio viene aggiornato automaticamente. Tuttavia, nessuna funzionalità di modifica sostanziale viene mai automaticamente inviata agli ambienti. Per impostazione predefinita, tutte le modifiche considerate sostanziali sono disattivate e devono essere attivate esplicitamente utilizzando la [gestione delle funzionalità](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md). Pertanto, tali modifiche non verranno visualizzate negli ambienti finché non si sceglie di abilitarle.

Poiché le notifiche non vengono visualizzate quando Ottimizzazione pianificazione viene aggiornato nel tuo ambiente, puoi rivedere le note sulla versione nella tabella seguente per determinare quando sono state rilasciate le modifiche e quali funzionalità hanno introdotto. Questa tabella mostra le modifiche rilasciate per Ottimizzazione pianificazione, se tali modifiche sono associate a una funzionalità della gestione delle funzionalità e la data di rilascio.

| Modifiche | Dettagli della gestione funzionalità | Date di rilascio |
|---|---|---|
| <p>Aggiunto supporto per piani generali con **Metodo di programmazione** impostato su *Programmazione operazioni*.</p><p>Nella pagina **Gruppi di ciclo** rispetta le impostazioni delle caselle di controllo **Attivazione**, **Orario di lavoro**, e **Capacità** per le righe con un **Tipo ciclo di lavorazione/processo** di *Impostazione* o *Processo*. </p><p>Miglioramenti generali di prestazioni, qualità e stabilità. | <p>Programmazione operazioni è disponibile nella gestione delle funzionalità a partire dalla versione 10.0.20.</p><p>Nome della funzionalità: *Programmazione capacità infinita per Ottimizzazione pianificazione*</p>  | 9-17 settembre 2021 |
| Miglioramenti generali di prestazioni, qualità e stabilità. | Non è richiesta alcuna gestione delle funzionalità. | 25-30 agosto 2021 |
| <p>Aggiunto il campo **Lead time** agli ordini pianificati.</p><p>Miglioramenti generali di prestazioni, qualità e stabilità.</p> | Non è richiesta alcuna gestione delle funzionalità. | 12-17 agosto 2021 |
| <p>Aggiunti i requisiti del tipo di risorsa per la programmazione a capacità infinita.</p><p>Miglioramento dell'efficienza delle risorse e del calendario per la programmazione a capacità infinita.</p><p>Per ulteriori informazioni, vedi [Programmazione con capacità infinita](infinite-capacity-planning.md). | <p>Disponibile nella gestione delle funzionalità a partire dalla versione 10.0.20.</p><p>Nome della funzionalità: *Programmazione capacità infinita per Ottimizzazione pianificazione*</p> | 6-12 luglio 2021 |
| Miglioramenti generali della qualità. | Non è richiesta alcuna gestione delle funzionalità. | 6-12 luglio 2021 |

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
