---
title: Processo di rilascio di Ottimizzazione pianificazione e cronologia dei rilasci
description: Questo articolo fornisce informazioni sul processo di rilascio e sulla cronologia dei rilasci per Ottimizzazione pianificazione.
author: t-benebo
ms.date: 10/14/2022
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2021-07-28
ms.dyn365.ops.version: 10.0.31
ms.openlocfilehash: e2437214b4a2a850f121bb86272bf7dc3d313507
ms.sourcegitcommit: b3579ac62e1ea15664a114abcc2409cad76d4f19
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/14/2022
ms.locfileid: "9682562"
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
| <p>[Codici smaltimento batch](../../inventory/batch-disposition-codes.md)</p><p>Includere i parametri delle scorte disponibili e delle transazioni di magazzini nei piani generali</p><p>Miglioramenti generali di prestazioni, qualità e stabilità</p> | Non è richiesta alcuna gestione delle funzionalità | 10-14 ottobre 2022 |
| <p>[Programmazione delle risorse con capacità limitata](finite-capacity.md)</p><p>Miglioramenti generali di prestazioni, qualità e stabilità</p> | Non è richiesta alcuna gestione delle funzionalità | 19-23 settembre 2022 |
| Miglioramenti generali di prestazioni, qualità e stabilità | Non è richiesta alcuna gestione delle funzionalità | 29 agosto - 3 settembre 2022 |
| <p>[Manutenzione centralizzata del calendario](../supply-chain-calendars-master-planning.md)</p><p>[Suggerimenti per ottimizzare l'approvvigionamento esistente](../action-messages.md)</p><p>[Support per conto lavoro](../../production-control/manage-subcontract-work-production.md)</p><p>Miglioramenti generali di prestazioni, qualità e stabilità</p> | Non è richiesta alcuna gestione delle funzionalità | 7-11 marzo 2022 |
| Supporto per la priorità di pianificazione per gli ordini di produzione | Disponibile con la versione 10.0.25 come parte della funzionalità denominata *Supporto MRP basato sulla priorità per Ottimizzazione pianificazione*. | 12-18 novembre 2021 |
| Miglioramenti generali di prestazioni, qualità e stabilità | Non è richiesta alcuna gestione delle funzionalità | 12-18 novembre 2021 |
| <p>Supporto per le formule di calcolo del tempo di processo, il percorso di produzione con sovrapposizione e il numero dell'operazione di produzione sulle transazioni del fabbisogno</p><p>Messaggi di errore avanzati per la pianificazione della produzione relativi a timeout, capacità non trovata e percorso ciclico</p><p>Maggiore coerenza durante il calcolo delle date di ricevimento e di emissione sia per gli ordini pianificati che per gli ordini stabilizzati</p><p>Miglioramenti generali di prestazioni, qualità e stabilità</p> | Nome della funzionalità: *Programmazione capacità infinita per Ottimizzazione pianificazione* | 22-27 ottobre 2021 |
| <p>Supporto per considerare la percentuale di scarto nel calcolo del tempo di elaborazione</p><p>Supporto per il numero di operazioni e l'utilizzo dei materiali durante la pianificazione</p> | Nome della funzionalità: *Programmazione capacità infinita per Ottimizzazione pianificazione* | 5-7 ottobre 2021 |
| <p>Supporto per i tipi di processo del ciclo di produzione: **Coda prima**, **Coda dopo** e **Tempo di trasporto**</p><p>Miglioramenti generali di prestazioni, qualità e stabilità</p> | Nome della funzionalità: *Programmazione capacità infinita per Ottimizzazione pianificazione* | 25-30 settembre 2021 |
| <p>Supporto per piani generali con **Metodo di programmazione** impostato su *Programmazione operazioni*</p><p>Nella pagina **Gruppi di ciclo** rispetta le impostazioni delle caselle di controllo **Attivazione**, **Orario di lavoro**, e **Capacità** per le righe con un **Tipo ciclo di lavorazione/processo** di *Impostazione* o *Processo* </p><p>Miglioramenti generali di prestazioni, qualità e stabilità</p> | <p>Programmazione operazioni è disponibile nella gestione delle funzionalità a partire dalla versione 10.0.20</p><p>Nome della funzionalità: *Programmazione capacità infinita per Ottimizzazione pianificazione*</p> | 9-17 settembre 2021 |
| Miglioramenti generali di prestazioni, qualità e stabilità | Non è richiesta alcuna gestione delle funzionalità | 25-30 agosto 2021 |
| <p>Aggiunto il campo **Lead time** agli ordini pianificati.</p><p>Miglioramenti generali di prestazioni, qualità e stabilità.</p> | Non è richiesta alcuna gestione delle funzionalità | 12-17 agosto 2021 |
| <p>Aggiunti i requisiti del tipo di risorsa per la programmazione a capacità infinita</p><p>Miglioramento dell'efficienza delle risorse e del calendario per la programmazione a capacità infinita</p><p>Per ulteriori informazioni, vedi [Programmazione con capacità infinita](infinite-capacity-planning.md)</p> | <p>Disponibile nella gestione delle funzionalità a partire dalla versione 10.0.20</p><p>Nome della funzionalità: *Programmazione capacità infinita per Ottimizzazione pianificazione*</p> | 6-12 luglio 2021 |
| Miglioramenti generali della qualità | Non è richiesta alcuna gestione delle funzionalità | 6-12 luglio 2021 |

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
