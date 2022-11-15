---
title: Pianificazione con selezione delle risorse in base alla capacità
description: Questo articolo descrive la selezione delle risorse durante la pianificazione della capacità infinita quando si specificano le capacità come requisiti di risorse per un'operazione.
author: t-benebo
ms.date: 08/09/2022
ms.topic: article
ms.search.form: RouteInventProd, WrkCtrTable, WrkCtrCapability
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2021-09-03
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 176f40ad8cd1aa1831bbe50c0ebd91ec0cc3bc89
ms.sourcegitcommit: 491ab9ae2b6ed991b4eb0317e396fef542d3a21b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2022
ms.locfileid: "9739900"
---
# <a name="scheduling-with-resource-selection-based-on-capability"></a>Pianificazione con selezione delle risorse in base alla capacità

[!include [banner](../../includes/banner.md)]

Specificando i requisiti di risorse per un'operazione di un ciclo di produzione, si definisce cosa è necessario per eseguire tale operazione. Ad esempio, un'operazione potrebbe richiedere una risorsa specifica o un gruppo di risorse o una combinazione di competenze o capacità. Questo articolo descrive la selezione delle risorse durante la pianificazione della capacità infinita quando si specificano le capacità come requisiti di risorse per un'operazione.

## <a name="turn-the-capability-based-scheduling-feature-on-or-off"></a>Attivare o disattivare la funzionalità programmazione basata sulla capacità

Per utilizzare questa funzionalità, è necessario attivarla per il sistema. A partire dalla versione 10.0.29 di Supply Chain Management, la funzionalità è attivata per impostazione predefinita. Gli amministratori possono attivare o disattivare questa funzionalità cercando la funzionalità *Programmazione capacità infinita per Ottimizzazione pianificazione* nell'area di lavoro [Gestione funzionalità](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

Per ulteriori informazioni su questa funzionalità, vedi [Programmazione con capacità infinita](infinite-capacity-planning.md).

## <a name="capability-based-scheduling"></a>Programmazione basata sulla capacità

Si definisce capacità l'idoneità di una risorsa operativa di eseguire un'attività specifica. È possibile assegnare più capacità a una singola risorsa operativa e una singola capacità può essere assegnata più risorse. È possibile assegnare capacità a tutti i tipi di risorse ad esempio strumenti, fornitori, macchine, ubicazioni, strutture e risorse umane.

Quando specifichi le capacità come requisiti di risorse, puoi posticipare l'allocazione delle risorse fino alla pianificazione degli ordini. Invece di assegnare risorse o gruppi di risorse specifici a un'operazione di ciclo, puoi definire le capacità richieste per ciascuna operazione di ciclo. Quindi, durante la pianificazione, il sistema abbina le capacità richieste con le capacità definite per le risorse. Il sistema seleziona solo le risorse che soddisfano i requisiti.

Per assegnare funzionalità a una risorsa operativa, utilizza la scheda dettaglio **Capacità** della pagina **Risorse**. Per assegnare risorse a una capcità utilizza la scheda dettaglio **Risorse** della pagina **Capacità risorsa**. Entrambe le pagine sono accessibili da **Controllo produzione \> Impostazione \> Risorse** nel riquadro di spostamento. Entrambe le Schede dettaglio includono una griglia che elenca le risorse associate a una risorsa o capacità selezionata. Entrambe le Schede dettaglio includono anche una barra degli strumenti che puoi utilizzare per aggiungere, rimuovere e modificare le righe nella griglia. La griglia include le colonne seguenti:

- **Risorsa** o **Capacità** – Seleziona la risorsa o la capacità assegnata dalla riga.
- **Descrizione** - Immetti una breve descrizione della risorsa o capacità.
- **Validità** – Specifica la data di inizio applicazione dell'assegnazione della risorsa o della capacità. Durante la pianificazione, il sistema non utilizzerà una risorsa o una capacità con un'assegnazione di capacità scaduta, anche se tale risorsa soddisfa i requisiti.
- **Scadenza** – Specifica la data di fine applicazione dell'assegnazione della risorsa o della capacità. Durante la pianificazione, il sistema non utilizzerà una risorsa o una capacità con un'assegnazione di capacità scaduta, anche se tale risorsa soddisfa i requisiti.
- **Livello** – Specifica il livello di competenza che la risorsa deve avere per la capacità. Quindi, se specifichi un valore **Livello minimo richiesto** per il requisito della risorsa o capacità, il motore di pianificazione considera il livello di competenza durante la selezione delle risorse. Il sistema seleziona solo le risorse con la capacità richiesta a un livello uguale o superiore al livello minimo che è specificato nei requisiti delle risorse.
- **Priorità** – Questo campo non è ancora supportato da Ottimizzazione pianificazione. Tuttavia, se stai utilizzando il motore di pianificazione generale deprecato, puoi utilizzare il campo **Priorità** nell'assegnazione della risorsa o della capacità per definire la priorità della risorsa. Quindi, se è selezionata l'opzione *Priorità* nel campo **Selezione risorsa primaria** della pagina **Parametri di programmazione**, il sistema seleziona per prima la risorsa con la massima priorità (il valore numerico più basso nel campo **Priorità**) durante la programmazione.

## <a name="example"></a>Esempio

Questo esempio mostra come il motore di pianificazione seleziona le risorse, in base alla capacità.

Un ciclo di produzione ha cinque operazioni: *10*, *20*, *30*, *40*, e *50*. Ogni operazione di ciclo richiede una risorsa con capacità diverse. Ad esempio, operazione di ciclo *10* richiede una risorsa che abbia la capacità di assemblare un altoparlante (*0050 Assemblaggio altoparlante*) e la capacità di lavorare il legno (*1010 Capacità con legno*). L'operazione di ciclo *50* richiede una risorsa che abbia la capacità di imballare un prodotto (*0070 Capacità di imballaggio*).

![Capacità usata per la programmazione.](media/capability-based-scheduling.png "Capacità usata per la programmazione.")

Durante la pianificazione, il motore cerca le risorse che soddisfano i requisiti operativi. Ad esempio, il motore di pianificazione seleziona la risorsa *00101* per eseguire l'operazione *10*, perché questa risorsa è la prima risorsa trovata che dispone di entrambe le capacità richieste. Il motore di pianificazione seleziona la risorsa *00301* per eseguire l'operazione *50*, perché questa risorsa è l'unica risorsa trovata che dispone della capacità di imballaggio.

Quindi, considera come questo esempio viene influenzato quando vengono utilizzati i livelli di competenza:

- L'operazione *10* richiede un livello minimo di competenza di *7* per la capacità *0059 Assemblaggio*.
- La risorsa *00101* ha un livello di competenza di *5* per la capacità *0059 Assemblaggio*.
- La risorsa *00102* ha un livello di competenza di *10* per la capacità *0059 Assemblaggio*.

In questo caso, durante la pianificazione con capacità infinita, il motore di pianificazione seleziona la risorsa *00102* per eseguire l'operazione *10*, perché questa risorsa, a differenza della risorsa *00101*, ha il livello di competenza richiesto per la capacità.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
