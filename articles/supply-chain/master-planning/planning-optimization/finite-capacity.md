---
title: Programmazione e pianificazione della capacità finita
description: La programmazione e la pianificazione della capacità finita ti aiutano a capire quanto lavoro può essere prodotto durante un periodo specifico quando vengono prese in considerazione le limitazioni sulle diverse risorse.
author: t-benebo
ms.date: 09/19/2022
ms.topic: article
ms.search.form: ReqParameters, ReqPlanSched, WrkCtrTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2022-09-19
ms.dyn365.ops.version: 10.0.29
ms.openlocfilehash: c5eebe9ef6258b43daa7c7007ee28b0278fe5b09
ms.sourcegitcommit: 1a7729a6ce4f3fcf68bdc4cfdad746a5553da3c5
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/22/2022
ms.locfileid: "9573136"
---
# <a name="finite-capacity-planning-and-scheduling"></a>Programmazione e pianificazione della capacità finita

[!include [banner](../../includes/banner.md)]

La capacità finita è un approccio che ti aiuta a capire quanto lavoro può essere prodotto durante un periodo specifico quando vengono prese in considerazione le limitazioni sulle diverse risorse. Lo scopo della programmazione con capacità finita è garantire che il lavoro proceda a un ritmo uniforme ed efficiente in tutto l'impianto.

La programmazione e la pianificazione della capacità finita crea una pianificazione più realistica per i processi di produzione rispetto a quella creata dall'approccio di caricamento infinito. Se la capacità delle risorse non è sufficiente, la data di consegna verrà eliminata e il processo verrà pianificato quando la capacità sarà sufficiente.

## <a name="planning-optimization-support-for-finite-capacity-planning"></a>Supporto di Ottimizzazione pianificazione per la pianificazione della capacità finita

La programmazione e la pianificazione della capacità finita funziona pressoché allo stesso modo, indipendentemente dal fatto che tu stia utilizzando l'ottimizzazione della pianificazione o il motore di pianificazione principale integrato. Tuttavia, Ottimizzazione pianificazione non utilizza il parametro limite **Tempo collo di bottiglia**. Quando usi Ottimizzazione pianificazione, le risorse del collo di bottiglia vengono sempre pianificate utilizzando lo stesso intervallo di tempo delle risorse non del collo di bottiglia (come indicato dall'intervallo di tempo della capacità finita).

## <a name="set-up-finite-capacity-functionality"></a>Configurare la funzionalità di capacità finita

Per utilizzare la funzionalità di capacità finita, è necessario abilitare la pianificazione della capacità a livello globale e abilitare la pianificazione della capacità finita sia per il piano generale in cui si desidera utilizzarlo sia per ciascuna risorsa a cui si applica. Per piani e risorse in cui è abilitata la capacità finita, la programmazione degli ordini di produzione pianificati verrà considerata la capacità già prenotata. Gli ordini di produzione pianificati vengono programmati a ritroso a partire dalla data fabbisogno. Se la capacità non è disponibile per soddisfare la pianificazione ottimale, il sistema tenterà di richiedere gli elementi dei componenti in una data precedente. Se la tua capacità può cambiare in funzione del fabbisogno (ad esempio, quando lavori con turni), non dovresti utilizzare la funzionalità di capacità finita, perché i tempi di elaborazione calcolati non saranno corretti. Nella programmazione viene considerata solo la capacità già prenotata per le risorse con la capacità finita abilitata. Abilitando la capacità finita per una risorsa, è possibile modificare la barriera temporale della capacità finita.

### <a name="activate-master-planning-parameters"></a>Attivare i parametri della pianificazione generale

Per utilizzare la funzionalità di capacità finita, è necessario abilitare la pianificazione della capacità nella pagina **Parametri pianificazione generale**.

1. Andare a **Pianificazione generale \> Impostazioni \>Parametri di pianificazione generale**.
1. Nella scheda **Ordini pianificati**, nella sezione **Pianificazione capacità** imposta l'opzione **Produzione** su *sì*.

### <a name="activate-a-master-plan"></a>Attivare un piano generale

È necessario abilitare la pianificazione e la programmazione della capacità finita per ogni piano principale in cui desideri utilizzarle.

1. Andare a **Pianificazione generale \> Impostazioni \> Piani \> Piani generali**.
1. Nel riquadro elenco seleziona un piano principale che vuoi configurare per utilizzare la pianificazione e la programmazione della capacità finita.
1. Nella scheda dettaglio **Generale**, nella sezione **Ordini di produzione pianificati** imposta l'opzione **Capacità finita** su *sì*.
1. Ripetere i passaggi 2 e 3 per ogni piano generale aggiuntivo che vuoi configurare.

### <a name="activate-resources"></a>Attivare le risorse

È necessario abilitare la pianificazione e la programmazione della capacità finita per ogni risorsa in cui desideri utilizzarle.

1. Vai a **Controllo produzione \> Impostazioni \> Risorse \> Risorse**.
1. Nel riquadro elenco seleziona una risorsa che vuoi configurare per utilizzare la pianificazione e la programmazione della capacità finita.
1. Nella scheda dettaglio **Operazioni**, nella sezione **Capacità**, imposta l'opzione **Capacità finita** su *Sì*.
1. Ripetere i passaggi 2 e 3 per ogni risorsa aggiuntiva che vuoi configurare.

## <a name="examples"></a>Esempi

Questa sezione fornisce i seguenti esempi che mostrano come lavorare con la pianificazione e la programmazione della capacità sia infinita che finita:

- Esempio 1 – Pianificazione della capacità infinita
- Esempio 2 – Pianificazione della capacità finita con un intervallo di tempo di un giorno
- Esempio 3 – Pianificazione della capacità finita con un intervallo di tempo di due giorni

### <a name="preconditions"></a>Condizioni preliminari

Tutti e tre gli esempi presuppongono le condizioni preliminari descritte in questa sezione.

Il prodotto *Product1* ha un percorso che contiene le seguenti operazioni.

| Numero operazione | Nome operazione | Risorsa        | Tempo di esecuzione | Qtà lavorazione | Successivo |
|---------------|----------------|-----------------|----------|--------------|------|
| 10            | Saldatura        | Linea di saldatura    | 1        | 2            | 20   |
| 20            | Assemblaggio     | Linea di assemblaggio | 1        | 4            |      |

I lavoratori della tua azienda lavorano in un turno di otto ore (8:00–16:00).

C'è un ordine di produzione programmato per *24 pezzi* di *Product1*. Ha una data di consegna di *Oggi + 3 giorni*.

Come risultato della pianificazione, il sistema carica le risorse nel modo seguente:

- **Linea di saldatura:** Questa risorsa viene caricata da *Oggi alle 8:00* fino a *Oggi + 1 alle 12:00*.
- **Linea di assemblaggio:** Questa risorsa viene caricata da *Oggi + 1 alle 12:00* fino a *Oggi + 2 alle 10:00*.

L'illustrazione seguente mostra il diagramma di Gantt risultante (selezionalo per ingrandirlo).

[![Diagramma di Gantt che mostra le condizioni preliminari.](media/finite-examples-conditions-small.png "Diagramma di Gantt che mostra le condizioni preliminari")](media/finite-examples-conditions.png)

### <a name="example-1--infinite-capacity-planning"></a>Esempio 1 – Pianificazione della capacità infinita

Questo esempio mostra i risultati della pianificazione quando si utilizza la pianificazione della capacità infinita anziché la pianificazione della capacità finita.

Il piano generale ha la seguente impostazione pertinente, che disabilita la pianificazione della capacità finita per il piano:

- **Capacità finita:** *No*

L'opzione **Capacità finita** è impostata su *No* per entrambe le risorse rilevanti per disabilitare la pianificazione della capacità finita:

- Linea di saldatura
- Linea di assemblaggio

Ora aggiungi un nuovo ordine cliente per *8 pezzi* di *Product1* ed eseguire il piano. Di conseguenza, il sistema carica la linea di saldatura da *Oggi alle 8:00* fino a *Oggi alle 12:00*. Al termine delle operazioni sulla linea di saldatura, il sistema caricherà la linea di assemblaggio da *Oggi alle 12:00* fino a *Oggi alle 14:00*.

L'illustrazione seguente mostra il diagramma di Gantt risultante (selezionalo per ingrandirlo).

[![Diagramma di Gantt che mostra un esempio di pianificazione della capacità infinita.](media/finite-examples-example1-small.png "Diagramma di Gantt che mostra un esempio di pianificazione della capacità infinita")](media/finite-examples-example1.png)

### <a name="example-2--finite-capacity-planning-with-a-time-fence-of-one-day"></a>Esempio 2 – Pianificazione della capacità finita con un intervallo di tempo di un giorno

Questo esempio mostra i risultati della pianificazione quando si utilizza la pianificazione della capacità finita e un intervallo di tempo di un giorno.

Il piano generale ha le seguenti impostazioni pertinenti, che abilitano la pianificazione della capacità finita e impostano un intervallo di tempo per il piano:

- **Capacità finita:** *Sì*
- **Intervallo temporale capacità finita:** *1*

L'opzione **Capacità finita** è impostata su *Sì* per entrambe le risorse rilevanti per abilitare la pianificazione della capacità finita:

- Linea di saldatura
- Linea di assemblaggio

Ora aggiungi un nuovo ordine cliente per *8 pezzi* di *Product1* ed eseguire il piano. Di conseguenza, il sistema carica la linea di saldatura da *Oggi + 1 alle 8:00* fino a *Oggi + 1 alle 12:00*. Al termine delle operazioni sulla linea di saldatura, il sistema caricherà la linea di assemblaggio da *Oggi + 1 alle 12:00* fino a *Oggi + 1 alle 14:00*. Il sistema considera la capacità finita per un solo giorno.

L'illustrazione seguente mostra il diagramma di Gantt risultante (selezionalo per ingrandirlo).

[![Diagramma di Gantt che mostra la pianificazione della capacità finita con un intervallo di tempo di un giorno.](media/finite-examples-example2-small.png "Diagramma di Gantt che mostra la pianificazione della capacità finita con un intervallo di tempo di un giorno")](media/finite-examples-example2.png)

### <a name="example-3--finite-capacity-planning-with-a-time-fence-of-two-days"></a>Esempio 3 – Pianificazione della capacità finita con un intervallo di tempo di due giorni

Questo esempio mostra i risultati della pianificazione quando si utilizza la pianificazione della capacità finita e un intervallo di tempo di due giorni.

Il piano generale ha le seguenti impostazioni pertinenti, che abilitano la pianificazione della capacità finita e impostano un intervallo di tempo per il piano:

- **Capacità finita:** *Sì*
- **Intervallo temporale capacità finita:** *2*

L'opzione **Capacità finita** è impostata su *Sì* per entrambe le risorse rilevanti per abilitare la pianificazione della capacità finita:

- Linea di saldatura
- Linea di assemblaggio

Ora aggiungi un nuovo ordine cliente per *8 pezzi* di *Product1* ed eseguire il piano. Di conseguenza, il sistema carica la linea di saldatura da *Oggi + 1 alle 12:00* fino a *Oggi + 1 alle 16:00*. Al termine delle operazioni sulla linea di saldatura, il sistema caricherà la linea di assemblaggio da *Oggi + 2 alle 8:00* fino a *Oggi + 2 alle 10:00*. Il sistema considera la capacità finita per due soli giorni.

L'illustrazione seguente mostra il diagramma di Gantt risultante (selezionalo per ingrandirlo).

[![Diagramma di Gantt che mostra la pianificazione della capacità finita con un intervallo di tempo di due giorni.](media/finite-examples-example3-small.png "Diagramma di Gantt che mostra la pianificazione della capacità finita con un intervallo di tempo di due giorni")](media/finite-examples-example3.png)

> [!IMPORTANT]
> Dovresti sempre impostare l'intervallo di tempo della capacità finita come richiesto per soddisfare le tue esigenze aziendali. Gli esempi forniti in questo articolo illustrano semplicemente la funzionalità. In realtà, un intervallo di tempo di un solo giorno è probabilmente troppo basso per la maggior parte dei produttori che utilizzano la pianificazione della capacità finita.
