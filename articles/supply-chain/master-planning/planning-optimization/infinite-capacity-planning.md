---
title: Programmazione con capacità infinita
description: In questo articolo sono riportate informazioni sulla programmazione della capacità infinita. Descrive inoltre le attuali limitazioni delle funzionalità.
author: t-benebo
ms.date: 08/09/2022
ms.topic: article
ms.search.form: RouteInventProd
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2021-06-09
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 7249734e5d2644145a36276dbc818a40b5962805
ms.sourcegitcommit: 491ab9ae2b6ed991b4eb0317e396fef542d3a21b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2022
ms.locfileid: "9740007"
---
# <a name="scheduling-with-infinite-capacity"></a>Programmazione con capacità infinita

[!include [banner](../../includes/banner.md)]

La funzionalità *Programmazione capacità infinita per l'ottimizzazione della pianificazione* introduzione la programmazione basata sulle informazioni sul ciclo di lavorazione. Consente di programmare i lavori in base a un'ampia gamma di impostazioni del percorso. La pianificazione copre le impostazioni del ciclo di lavorazione utilizzate di frequente, inclusa la sequenza dell'operazione del ciclo di lavorazione o i requisiti per le risorse dell'operazione del ciclo di lavorazione.

## <a name="turn-the-infinite-capacity-scheduling-feature-on-or-off"></a>Attivare o disattivare la funzionalità Programmazione capacità infinita

Per utilizzare questa funzionalità, è necessario attivarla per il sistema. A partire dalla versione 10.0.29 di Supply Chain Management, la funzionalità è attivata per impostazione predefinita. Gli amministratori possono attivare o disattivare questa funzionalità cercando la funzionalità *Programmazione capacità infinita per Ottimizzazione pianificazione* nell'area di lavoro [Gestione funzionalità](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

Per ulteriori informazioni su questa funzione, vedi [Pianificazione con selezione delle risorse in base alla capacità](capability-based-scheduling.md).

## <a name="added-functionality"></a>Funzionalità aggiunta

La funzionalità *Programmazione capacità infinita per l'ottimizzazione della pianificazione* consente la programmazione basata sulle informazioni sul ciclo di lavorazione. Pertanto, è possibile utilizzare un'impostazione del ciclo di lavorazione per pianificare i processi di produzione. Sebbene questa funzionalità presenti alcune limitazioni che il motore di pianificazione generale deprecato non ha, supporta le funzionalità più comuni necessarie per gli scenari di produzione.

La funzionalità considera i *cicli di lavorazione semplici* e le *reti di cicli di lavorazione*. Utilizzando il campo **Avanti** su un'operazione del ciclo di lavorazione, è possibile impostare cicli di lavorazione complessi con più punti di partenza e più operazioni eseguite in parallelo. Il sistema prenderà in considerazione strutture di cicli di lavorazione complessi di questo tipo durante la programmazione.

Inoltre, la funzionalità supporta *operazioni parallele* nei cicli di lavorazione. Utilizzando le opzioni *Primaria* e *Secondaria* nel campo **Priorità** sulle operazioni dei cicli di lavorazione, è possibile definire una struttura di cicli di lavorazione in cui un'operazione è quella primaria e un'altra è quella secondaria. In questo caso, il sistema prenderà in considerazione la struttura dei cicli di lavorazione durante la programmazione.

Durante il processo di programmazione, il sistema considera anche i *requisiti di risorse* specificati per un'operazione. Il sistema utilizza i requisiti di risorse per determinare quali risorse sono necessarie per eseguire l'operazione. Attualmente, la funzionalità *Programmazione capacità infinita per l'ottimizzazione della pianificazione* supporta i seguenti tipi di requisiti di risorse:

- Tipo di risorsa
- Risorsa
- Gruppo di risorse
- Capacità. Per ulteriori informazioni su questa funzione, vedi [Pianificazione con selezione delle risorse in base alla capacità](capability-based-scheduling.md).

> [!NOTE]
>
> - Se la risorsa e/o il gruppo di risorse sono impostati su capacità infinita, la pianificazione generale li considererà come capacità infinita.
> - I requisiti relativi alle risorse umane, ad esempio competenze o requisiti dei certificati, non sono ancora supportati.

La funzionalità supporta anche le proprietà operative **Tempo di preparazione** e **Tempo di esecuzione**. Quando si impostano queste proprietà su un'operazione del ciclo di lavorazione, il processo di programmazione creerà i lavori di impostazione e processo appropriati.

In sintesi, la programmazione supporta gli scenari di uso più comune. È possibile creare il ciclo di lavorazione, aggiungere operazioni primarie e secondarie, definire le operazioni successive, aggiungere requisiti di risorse e aggiungere tempi di preparazione e tempi di esecuzione. Il sistema prenderà in considerazione queste informazioni durante la programmazione.

## <a name="limitations"></a>Limiti

Le seguenti limitazioni si applicano quando si utilizza la funzionalità *Programmazione capacità infinita per Ottimizzazione pianificazione*:

- La funzionalità supporta solo la capacità infinita.
- La funzionalità non supporta la funzionalità del carico di risorse.
- La funzionalità non considera lo scarto del ciclo di lavorazione.
- La funzionalità supporta *Durata* solo come selezione della risorsa primaria.
