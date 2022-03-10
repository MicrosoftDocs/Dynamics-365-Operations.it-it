---
title: Programmazione con capacità infinita
description: Questo argomento fornisce informazioni sulla programmazione della capacità infinita per l'ottimizzazione della pianificazione. Descrive inoltre le attuali limitazioni delle funzionalità.
author: ChristianRytt
ms.date: 09/21/2021
ms.topic: article
ms.search.form: RouteInventProd
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2021-06-09
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 6ea27f4e38697d517b1520176eb5dfeee651a598
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2022
ms.locfileid: "7982152"
---
# <a name="scheduling-with-infinite-capacity"></a>Programmazione con capacità infinita

[!include [banner](../../includes/banner.md)]

La funzionalità *Programmazione capacità infinita per l'ottimizzazione della pianificazione* introduzione la programmazione basata sulle informazioni sul ciclo di lavorazione. Consente di programmare i lavori in base a un'ampia gamma di impostazioni del percorso. Pianificazione per l'ottimizzazione della pianificazione copre le impostazioni del ciclo di lavorazione utilizzate di frequente, inclusa la sequenza dell'operazione del ciclo di lavorazione o i requisiti per le risorse dell'operazione del ciclo di lavorazione.

## <a name="turn-on-the-infinite-capacity-scheduling-feature"></a>Attivare la funzionalità Programmazione capacità infinita

Prima di poter utilizzare questa funzione, è necessario attivarla nel sistema. Gli amministratori possono utilizzare le impostazioni della [gestione delle funzionalità](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) per controllare lo stato della funzione e abilitarla. Nell'area di lavoro **Gestione funzionalità**, la funzione è elencata nel modo seguente:

- **Modulo:** *Pianificazione generale*
- **Nome della funzionalità:** *Programmazione capacità infinita per Ottimizzazione pianificazione*

Per ulteriori informazioni su questa funzione, vedi [Pianificazione con selezione delle risorse in base alla capacità](capability-based-scheduling.md).

## <a name="added-functionality"></a>Funzionalità aggiunta

La funzionalità *Programmazione capacità infinita per l'ottimizzazione della pianificazione* consente la programmazione basata sulle informazioni sul ciclo di lavorazione. Pertanto, è possibile utilizzare un'impostazione del ciclo di lavorazione per pianificare i processi di produzione. Sebbene questa funzionalità presenti alcune limitazioni che la pianificazione generale incorporata non ha, supporta le funzionalità più comuni necessarie per gli scenari di produzione.

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

In sintesi, la programmazione per l'ottimizzazione della pianificazione supporta gli scenari di uso più comune. È possibile creare il ciclo di lavorazione, aggiungere operazioni primarie e secondarie, definire le operazioni successive, aggiungere requisiti di risorse e aggiungere tempi di preparazione e tempi di esecuzione. Il sistema prenderà in considerazione queste informazioni durante la programmazione.

## <a name="limitations"></a>Limiti

Le seguenti limitazioni si applicano quando si utilizza la programmazione per l'ottimizzazione della pianificazione:

- La funzionalità supporta solo la capacità infinita.
- La funzionalità non supporta la funzionalità del carico di risorse.
- La funzionalità non considera lo scarto del ciclo di lavorazione.
- La funzionalità supporta *Durata* solo come selezione della risorsa primaria.

Si noti che la funzionalità *Programmazione della capacità infinita per l'ottimizzazione della pianificazione* viene costantemente migliorata. Microsoft prevede di introdurre il supporto per ulteriori impostazioni di programmazione nelle versioni future.
