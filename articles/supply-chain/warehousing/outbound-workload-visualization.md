---
title: Visualizzazione del carico di lavoro in uscita
description: Questo argomento fornisce informazioni sulla visualizzazione del carico di lavoro. Questa funzionalità consente ai responsabili del magazzino e ai supervisori di creare grafici del carico di lavoro personalizzati che possono essere utilizzati per monitorare lo stato di avanzamento del lavoro corrente e la quantità rimanente. I responsabili del magazzino possono creare più visualizzazioni e impostare l'aggiornamento automatico come richiesto.
author: Mirzaab
manager: tfehr
ms.date: 08/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-08-28
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: 2515a71297df7213f93a4c619f7eebf1c2411b39
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4965554"
---
# <a name="outbound-workload-visualization"></a>Visualizzazione del carico di lavoro in uscita

[!include [banner](../includes/banner.md)]

Le funzionalità di configurazione avanzate accessibili dalla pagina **Visualizzazione del carico di lavoro in uscita** consente ai responsabili del magazzino e ai supervisori di creare grafici del carico di lavoro personalizzati che possono essere utilizzati per monitorare lo stato di avanzamento del lavoro corrente e la quantità rimanente. I responsabili del magazzino possono creare più visualizzazioni e impostare l'aggiornamento automatico come richiesto. Le visualizzazioni del carico di lavoro in uscita sono adatte per la visualizzazione nelle pagine delle prestazioni del magazzino.

Questa funzionalità può essere utilizzata per tenere traccia dell'avanzamento del lavoro di prelievo. La funzionalità è integrata con la gestione di lavoro e, se è impostata la gestione di lavoro, le visualizzazioni del carico di lavoro in uscita possono mostrare un calcolo del numero di ore rimanenti per il lavoro di prelievo mostrato (filtrato).

## <a name="turn-on-the-outbound-workload-visualization-feature"></a>Attivare la funzionalità Visualizzazione del carico di lavoro in uscita

Prima di poter utilizzare questa funzione, è necessario attivarla nel sistema. Gli amministratori possono utilizzare le impostazioni della [gestione delle funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) per controllare lo stato della funzione e abilitarla. Nell'area di lavoro **Gestione funzionalità**, la funzione è elencata nel modo seguente:

- **Modulo:** *Gestione Magazzino*
- **Nome funzionalità:** *Visualizzazione del carico di lavoro in uscita*

## <a name="set-up-outbound-workload-visualizations"></a>Impostare le visualizzazioni del carico di lavoro in uscita

Per impostare le visualizzazioni, creare una raccolta di filtri (visualizzazioni) e progettare ogni filtro in modo che mostri un diverso tipo di analisi. Usare la pagina **Configura filtri** per progettare i filtri.

Per impostare una visualizzazione del carico di lavoro in uscita, seguire questi passaggi.

1. Andare a **Gestione magazzino \> Report monitoraggio magazzino \> Visualizzazione del carico di lavoro in uscita**.

    La pagina **Visualizzazione del carico di lavoro in uscita** viene visualizzata. Dopo aver creato alcuni filtri, questa pagina mostrerà la visualizzazione. È possibile creare il numero di filtri desiderato. Tutti i filtri creati vengono salvati nell'account utente, in modo da poterli utilizzare in seguito. In altre parole, ogni utente avrà il proprio set di filtri che ha creato. Questi filtri non verranno condivisi con altri utenti.

1. Nella pagina **Visualizzazione del carico di lavoro in uscita**, nel riquadro azioni, nella scheda **Filtri** selezionare **Configura filtri**.
1. Nella pagina **Configura filtri**, nel riquadro azioni selezionare **Nuovo** per aggiungere un filtro, quindi impostare i seguenti campi per il filtro:

    - **Tabella gruppo asse X** - Selezionare la tabella che contiene il campo da utilizzare per raggruppare i valori dell'asse X.
    - **Campo gruppo asse X** - Tra i campi della tabella selezionata nel campo **Tabella gruppo asse X** selezionare il campo da utilizzare per raggruppare i valori dell'asse X.
    - **Tabella valore asse X** - Selezionare la tabella che contiene il campo da utilizzare per analizzare ulteriormente i gruppi.
    - **Campo valore asse X** - Tra i campi della tabella selezionata nel campo **Tabella valore asse X** selezionare il campo che fornisce i valori da analizzare per ogni gruppo.
    - **Aggiornamento automatico** - Selezionare se la visualizzazione deve essere aggiornata automaticamente.
    - **Intervallo di aggiornamento (minuti)** - Immettere il numero di minuti tra gli aggiornamenti automatici.
    - **Livello di visualizzazione** - Selezionare se il grafico deve mostrare righe aperte o conteggi intestazioni aperte.
    - **Tipo di prelievo** - Se il campo **Livello di visualizzazione** è stato impostaro su _Righe aperte_, selezionare se il conteggio delle righe di lavoro aperte nel grafico deve includere i prelievi iniziali, i prelievi in fasi o sia i prelievi iniziali che i prelievi in fasi.
    - **Sito** - Selezionare il sito per cui caricare il grafico.
    - **Magazzino** - Selezionare il magazzino per cui caricare il grafico.
    - **Giorni da includere** - Immettere il numero di giorni nel passato per i quali il grafico deve essere generato.
    - **Tipo di ordine di lavoro** - Selezionare i tipi di ordini di lavoro in uscita da filtrare.

    ![Configurare la pagina dei filtri](media/work-viz-filters-1.png "Configurare la pagina dei filtri")

1. Chiudere la pagina **Configura filtri** per tornare alla pagina **Visualizzazioni del carico di lavoro in uscita**.

    La pagina **Visualizzazioni del carico di lavoro in uscita** ora mostra i dati in base alle nuove impostazioni del filtro. Il nuovo filtro è ora disponibile ed è selezionato nel campo **Filtro**. I seguenti campi sono disponibili nella parte superiore del grafico:

    - **Filtro** - Questo campo include tutti i filtri creati finora. Selezionare un filtro per visualizzarne i dati nel grafico.
    - **Ultimo aggiornamento** - Questo campo mostra la data e l'ora dell'ultimo aggiornamento delle informazioni nel grafico.
    - **Tempo stimato/effettivo** - Se gli standard di lavoro sono impostati nel sistema, impostare questa opzione su *Sì* per mostrare i tempi di prelievo stimati accumulati nella parte superiore di ogni colonna nel grafico. Se non si utilizzano gli standard di lavoro, questa opzione non è disponibile.

    ![Visualizzazione di esempio](media/work-viz-chart.png "Visualizzazione di esempio")

1. Selezionare una barra qualsiasi nel grafico per visualizzare i dettagli della riga di lavoro associata.

    ![Dettagli riga di lavoro](media/work-viz-work-details.png "Dettagli riga di lavoro")

## <a name="example-outbound-workload-visualization-for-zones"></a>Esempio: visualizzazione del carico di lavoro in uscita per le zone

Per questo esempio, si desidera impostare una visualizzazione che mostri le righe di lavoro per ciascuna zona e lo stato di ciascuna riga di lavoro (_Aperto_, _Chiuso_ o _Annullato_). In questo caso, è possibile configurare un filtro con le seguenti impostazioni:

- **Nome filtro** - Inserire un nome per questo filtro (come _Zona e stato di lavoro_).
- **Descrizione** - Inserire una breve descrizione per questo filtro (come _Zona e stato di lavoro_).
- **Tabella gruppo asse X** - Selezionare _Ubicazioni._
- **Gruppo asse X** - Selezionare _ID zona_.
- **Tabella valore asse X** - Selezionare _Lavoro_, per visualizzare il lavoro per zona.
- **Campo valore asse X** - Selezionare _Stato lavoro_, per visualizzare lo stato del lavoro.
- **Aggiornamento automatico** - Selezionare se la visualizzazione deve essere aggiornata automaticamente.
- **Tipo di prelievo** - Selezionare _Prelievi iniziali e prelievi in fasi_, per includere sia i prelievi iniziali che i prelievi dalle ubicazioni di staging. In altre parole, essenzialmente si desidera includere tutte le righe di lavoro di prelievo disponibili.
- **Livello di visualizzazione** - Selezionare _Righe aperte_, per visualizzare le informazioni per riga, non per intestazione di lavoro.

Nella figura seguente è illustrato un esempio del grafico risultante.

![Visualizzazione della zona e dello stato di lavoro](media/work-viz-chart.png "Visualizzazione della zona e dello stato di lavoro")

Questo grafico mostra due zone denominate **FLOOR** e **BULK**, più una zona denominata **Blank**. La zona **Blank** rappresenta tutte le righe di lavoro che non sono membri di nessuna zona. Il grafico mostra sempre tutti i dati filtrati non correlati come **Blank**, per fornire la massima visibilità possibile. Nella zona **FLOOR**, il grafico mostra tre righe chiuse e quattro righe aperte. Nella zona **BULK**, il grafico mostra quattro righe chiuse, una riga aperta e 24 righe annullate. Infine, il grafico mostra otto righe chiuse che non fanno parte di alcuna zona e sono quindi elencate come **Blank**.
