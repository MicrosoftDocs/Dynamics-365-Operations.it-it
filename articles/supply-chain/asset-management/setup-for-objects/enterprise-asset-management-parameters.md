---
title: Parametri di Gestione cespiti
description: In Gestione cespiti, i parametri generali relativi ai cespiti, gli ordini di lavoro e la programmazione degli ordini di lavoro devono essere impostati.
author: josaw1
manager: tfehr
ms.date: 02/18/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetParameters
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5e4b76ba90ab03cd35e72eff8acc89f780659fa5
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/16/2021
ms.locfileid: "5020656"
---
# <a name="asset-management-parameters"></a>Parametri di Gestione cespiti

[!include [banner](../../includes/banner.md)]

In Gestione cespiti, i parametri generali relativi ai cespiti, gli ordini di lavoro e la programmazione degli ordini di lavoro devono essere impostati. In questo argomento viene illustrato come impostarli. Selezionare **Gestione cespiti** > **Impostazione** > **Parametri di gestione cespiti** per aprire la pagina.

> [!NOTE]
> Per configurare un sistema che includa dati dimostrativi per il test delle funzionalità di Gestione risorse, consultare [Distribuire un ambiente demo](../../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) per le istruzioni.

## <a name="the-assets-tab"></a>Scheda Cespiti

La scheda **Cespiti** fornisce le seguenti impostazioni:

- **Unità funzionale predefinita** rappresenta l'unità funzionale standard, che viene selezionata automaticamente per i cespiti quando si creano nuovi cespiti.  
- Nel campo **Calendario standard**, selezionare un calendario da utilizzare per calcolare i KPI del cespite, se nessuna risorsa è selezionata per un cespite.  
- Nel campo **Visualizzazione**, selezionare la visualizzazione predefinita che viene visualizzata quando si apre **Visualizzazione cespiti** (**Gestione cespiti** > **Comune** > **Cespiti** > **Visualizzazione cespiti**).
- **Tipo di richiesta predefinito** è il tipo predefinito di richiesta di intervento di manutenzione, che viene selezionato automaticamente quando si crea una nuova richiesta.  
- Le previsioni relative ai tipi di processo vengono archiviate nel progetto selezionato nel campo **Previsione progetto**. Per ciascun tipo di processo, una nuova attività viene creata automaticamente nel progetto di previsione. Le previsioni del tipo di processo vengono salvate nel progetto di previsione.  
- Nel campo **Modello**, selezionare il modello previsionale utilizzato nelle previsioni di tipo di processo e ordine di lavoro.

## <a name="the-work-orders-tab"></a>Scheda Ordini di lavoro

La scheda **Ordini di lavoro** fornisce le seguenti impostazioni:

- **Tipo di ordine di lavoro predefinito** definisce le impostazioni standard quando si crea un ordine di lavoro.  
- **Tipo di ordine di lavoro preventivo** definisce il tipo di ordine di lavoro utilizzato per la creazione degli ordini di lavoro per i piani di manutenzione. Se questo campo viene lasciato vuoto, il tipo di ordine di lavoro nel campo **Tipo di ordine di lavoro predefinito** viene utilizzato.  
- Nel campo **Maschera ordini di lavoro correlati**, definire il numero massimo di ordini di lavoro che possono essere correlati a un ordine di lavoro. Esempio, ## consente di avere fino a 99 ordini di lavoro correlati. Se si definisce una maschera come descritto qui, gli ordini di lavoro correlati vengono numerati [ID dell'ordine di lavoro a cui un ordine di lavoro è correlato] -01, -02, -03, e così via. Se non si definisce una maschera in questo campo, un ordine di lavoro correlato otterrà l'ID ordine di lavoro sequenziale seguente.  
- Selezionare **Sì** per **Copia errori** per copiare automaticamente gli errori registrati in ordini di lavoro nelle richieste di intervento di manutenzione correlate. 
- Nel campo **Livello**, definire il livello di unità funzionale che viene inserito automaticamente in un ordine di lavoro se tutti i processi di ordini di lavoro correlati fanno riferimento alla stessa unità funzionale. Se i processi di ordine di lavoro non sono tutti relativi alla stessa unità funzionale del livello definito, il campo **Unità funzionale** è lasciato vuoto nell'ordine di lavoro. Ad esempio, se si inserisce il numero "1" in questo campo, quello è il livello principale di una struttura di unità funzionali. Se si inserisce il numero "0" in questo campo, non è stato definito un livello specifico di unità funzionale, solo che tutti i processi di ordine di lavoro in un ordine di lavoro devono essere correlati alla stessa unità funzionale per l'unità funzionale da aggiungere all'ordine di lavoro.  
- I giornali di registrazione utilizzati per la registrazione del consumo in un ordine di lavoro possono essere selezionati nella Scheda dettaglio **Generale** nei campi **Ora**, **Articolo** e **Spese**.  
- Nel campo **Origine lingua prodotto**, selezionare la lingua da utilizzare per i nomi di prodotti nei report di Gestione cespiti. È possibile selezionare la lingua impostata nel conto della società o quella impostata per l'utente attualmente connesso.  
- Selezionare **Sì** per **Aggiornamento in tempo reale** se si desidera aggiornare automaticamente le modifiche ai valori predefiniti del tipo di processo, ai piani di manutenzione e ai cicli di manutenzione.
  - Se si seleziona **No**, le modifiche ai valori predefiniti del tipo di processo, ai piani di manutenzione e ai cicli di manutenzione non vengono aggiornate automaticamente in Gestione cespiti.
  - Selezionare **No** sull'interruttore se si dispone di grandi quantità di dati da sincronizzare, ad esempio, numerosi cespiti o unità funzionali impostate nei piani di manutenzione o cicli di manutenzione, o un numero elevato di piani o cicli di manutenzione.  
  - Se si apportano modifiche ai valori predefiniti del tipo di processo, ai piani di manutenzione o ai cicli di manutenzione e si è selezionato **No** all'aggiornamento in tempo reale, un'avvertenza potrebbe non essere visualizzato se le modifiche influenzano:
    - Unità funzionali impostate in piani o cicli di manutenzione  
    - Oggetti impostati in piani o cicli di manutenzione  
    - Impostazione di piani di manutenzione  
    - Impostazione di cicli di manutenzione  
- Nella Scheda dettaglio **Categoria**, le categorie predefinite correlate al consumo per gli ordini di lavoro possono essere definite.  

## <a name="the-work-order-scheduling-tab"></a>Scheda Programmazione ordine di lavoro

La scheda **Programmazione ordine di lavoro** fornisce le seguenti impostazioni nella Scheda dettaglio **Generale**:

- **Intervallo temporale programmazione** definisce il periodo in giorni, calcolato a partire dalla data di inizio prevista dell'ordine di lavoro, durante il quale i processi dell'ordine di lavoro sono pianificati.  
- Il **Piano generale** Riguarda le risorse del modulo **Amministrazione organizzazione**. Se si seleziona un piano generale in questo campo, sarà possibile visualizzare le prenotazioni di capacità correlate agli ordini di lavoro in **Prenotazioni capacità** (**Amministrazione organizzazione** > **Risorse** > **Risorse** > selezionare risorsa > scheda **Risorsa** > pulsante **Prenotazioni capacità** ). Se si lascia questo campo vuoto, sarà possibile visualizzare il carico di capacità correlato agli ordini di lavoro in **Carico di capacità** (**Amministrazione organizzazione** \> **Risorse** \> **Risorse** \> selezionare risorsa \> scheda **Risorsa** \> pulsante **Prenotazioni capacità**).  

>[!NOTE]
>La selezione riguardante l'uso di un piano generale nel modulo **Gestione cespiti** e il modulo correlato utilizzato per ottenere una panoramica delle prenotazioni di capacità o del carico di capacità è l'impostazione standard. A seconda delle impostazioni nel campo **Piano generale**, sarà possibile accedere alle informazioni di capacità in **Prenotazioni capacità** o **Carico di capacità** nel modulo **Amministrazione organizzazione**. Non è possibile creare un'impostazione in cui le prenotazioni di capacità vengono visualizzate in entrambe le visualizzazioni.  

I campi descritti nell'elenco seguente sono tutti relativi ai punteggi di valutazione calcolati, utilizzati per calcolare la priorità dell'ordine di lavoro durante la programmazione degli ordini di lavoro.

- **Priorità** - un punteggio di valutazione calcolato insieme al punteggio di valutazione nei campi **Criticità** e **Data di inizio**. Il numero specificato in questo campo viene diviso per il numero del campo **Priorità** in un ordine di lavoro. Ad esempio, se il valore "5,00" è immesso in questo campo e un ordine di lavoro ha priorità "20", il punteggio di valutazione della priorità è 0,25.  
- **Criticità** - un punteggio di valutazione calcolato insieme al punteggio di valutazione nei campi **Priorità** e **Data di inizio**. Il numero specificato in questo campo viene moltiplicato per il numero del campo **Criticità** in un ordine di lavoro. Ad esempio, se il valore "10,00" è immesso in questo campo e un ordine di lavoro ha criticità "5", il punteggio di valutazione della criticità è 50.  
- **Data di inizio** - un punteggio di valutazione calcolato insieme al punteggio di valutazione nei campi **Priorità** e **Criticità**. Questo campo indica il punteggio giornaliero come valore negativo e viene confrontato con il campo **Inizio previsto** di un ordine di lavoro. Ad esempio, se il valore "10,00" viene immesso in questo campo e la data di inizio prevista di un ordine di lavoro è tre giorni dalla data odierna, il risultato di valutazione è meno 30,00. La somma dei risultati di 0,25 e 50 dagli esempi nei campi **Priorità** e **Criticità** descritti in precedenza produce un totale di più 20,25. Il numero viene confrontato ai punteggi di valutazione di tutti gli altri ordini di lavoro durante la programmazione degli ordini di lavoro e i punteggi di valutazione pi alti vengono pianificati per primi.  
- **Lavoratore responsabile** - un punteggio di valutazione calcolato insieme ai valori dei punteggi di valutazione **Gruppo lavoratori responsabili**, **Lavoratore preferito**, **Gruppo lavoratori preferiti**, **Ubicazione cespiti** e **Data di inizio**. Se il valore "50,00" viene immesso in questo campo e un lavoratore responsabile è stato selezionato in un ordine di lavoro, il lavoratore ottiene 50 punti nel calcolo complessivo del lavoratore durante la programmazione degli ordini di lavoro.  
- **Gruppo lavoratori responsabili** - un punteggio di valutazione calcolato insieme ai valori dei punteggi di valutazione **Lavoratore responsabile**, **Lavoratore preferito**, **Gruppo lavoratori preferiti**, **Ubicazione cespiti** e **Data di inizio**. Se il valore "50,00" viene immesso in questo campo e un lavoratore responsabile è stato selezionato in un ordine di lavoro, il lavoratore ottiene 50 punti nel calcolo complessivo del lavoratore durante la programmazione degli ordini di lavoro.  
- **Limita al responsabile** - limita il numero di lavoratori disponibili per la programmazione degli ordini di lavoro. Selezionare **No** se si desidera calcolare un punteggio per tutti i lavoratori, indipendentemente da quelli impostati come lavoratori responsabili o parte di un gruppo di lavoratori responsabili. Selezionare **Sì** se si desidera calcolare un punteggio per i lavoratori impostati come lavoratore responsabile dell'ordine di lavoro e/o inclusi in un gruppo di lavoratori responsabili selezionato nell'ordine di lavoro.  
- **Lavoratore preferito** - un punteggio di valutazione calcolato insieme ai valori dei punteggi di valutazione **Lavoratore responsabile**, **Lavoratore preferito**, **Gruppo lavoratori preferiti**, **Ubicazione cespiti** e **Data di inizio**. I quattro punteggi di valutazione vengono calcolati e sommati per fornire un punteggio usato per selezionare quale lavoratore deve essere assegnato a quale ordine di lavoro durante la programmazione degli ordini di lavoro. Se il valore "10,00" viene immesso in questo campo e un lavoratore è stato selezionato come lavoratore preferito in un ordine di lavoro, il lavoratore ottiene 10 punti nel calcolo complessivo del lavoratore durante la programmazione degli ordini di lavoro.  
- **Gruppo lavoratori preferiti** - un punteggio di valutazione calcolato insieme ai valori dei punteggi di valutazione **Lavoratore responsabile**, **Lavoratore preferito**, **Gruppo lavoratori preferiti**, **Ubicazione cespiti** e **Data di inizio**. Se il valore "10,00" viene immesso in questo campo e un lavoratore è stato assegnato a un gruppo di lavoratori preferiti selezionato in un ordine di lavoro, il lavoratore ottiene 10 punti nel calcolo complessivo del lavoratore durante la programmazione degli ordini di lavoro.  
- **Limita al preferito** - limita il numero di lavoratori disponibili per la programmazione degli ordini di lavoro. Selezionare **No** se si desidera calcolare un punteggio per tutti i lavoratori, indipendentemente se siano impostati come lavoratori preferiti o parte di un gruppo di lavoratori preferiti. Selezionare **Sì** se si desidera solo calcolare un punteggio per i lavoratori impostati come lavoratori preferiti e/o inclusi in un gruppo di lavoratori preferiti.  
- **Ubicazione** - un punteggio di valutazione calcolato insieme ai valori dei punteggi di valutazione **Lavoratore responsabile**, **Lavoratore preferito**, **Gruppo lavoratori preferiti**, **Ubicazione cespiti** e **Data di inizio**. Se il valore "3.000,00" viene immesso in questo campo, un lavoratore ottiene 3.000 punti nel calcolo se il lavoratore è ubicato nella stessa fabbrica o struttura del cespite per cui un processo deve essere programmato.  
  - Se la società utilizza le unità funzionali, i lavoratori ottengono punteggio pieno se si trovano nell'unità funzionale correlata al cespite. Se l'unità funzionale del cespite ha un cespite padre, i lavoratori nell'ubicazione funzionale ottengono la metà del punteggio. Se anche l'ubicazione ha un padre, i lavoratori in tale ubicazione ottengono un terzo del punteggio. Se anche quell'ubicazione ha un padre, i lavoratori in tale ubicazione ottengono un quarto del punteggio e così via.  
  - Se la società utilizza l'ubicazione cespiti, che non è consigliabile, l'ubicazione, l'area e la zona vengono utilizzate per calcolare i punteggi dell'ubicazione. I lavoratori ottengono il punteggio pieno se si trovano nell'ubicazione e l'area e la zona correlate al cespite. Se l'ubicazione del lavoratore corrisponde solo a ubicazione e area, il punteggio di valutazione del lavoratore è 2/3 del punteggio pieno. Se l'ubicazione del lavoratore corrisponde solo a ubicazione, il punteggio di valutazione del lavoratore è 1/3 del punteggio pieno.  
- **Limita a ubicazione** - limita il numero di lavoratori disponibili per la programmazione degli ordini di lavoro. Selezionare **No** se si desidera calcolare un punteggio per tutti i lavoratori in tutte le unità funzionali. Selezionare **Sì** solo se si desidera calcolare un punteggio per i lavoratori associati alla unità funzionale dell'ordine di lavoro.

>[!NOTE]
>I tre campi "Limita a..." aumentano la velocità di programmazione degli ordini di lavoro limitando il numero dei punteggi calcolati per i lavoratori.

**Data di inizio del lavoratore** - un punteggio di valutazione calcolato insieme ai valori dei punteggi di valutazione **Lavoratore responsabile**, **Lavoratore preferito**, **Gruppo lavoratori preferiti**, **Ubicazione cespiti** e **Data di inizio**. Questo campo indica il punteggio giornaliero come valore negativo e viene confrontato con il campo **Inizio previsto** di un ordine di lavoro. Se il valore "10,00" viene immesso in questo campo e la data di inizio prevista di un ordine di lavoro è domani, il risultato di valutazione è meno 10,00.

  - Supponendo che nessun lavoratore responsabile e gruppo di lavoratori responsabili sono stati selezionati in un ordine di lavoro da programmare - si aggiungono e si sottraggono i valori di punteggio di valutazione negli esempi dei campi precedenti **Lavoratore preferito**, **Gruppo lavoratori preferiti**, **Ubicazione cespiti** e **Data di inizio**, si ottiene un totale di 3.010,00. Ciò significa un punteggio elevato per il lavoratore già selezionato come lavoratore preferito nonché incluso nel gruppo di lavoratori preferiti nell'ordine di lavoro e il lavoratore anche si trova nella stessa struttura del cespite per cui un processo deve essere programmato. Questo significa che esiste una buona probabilità che il lavoratore in questione verrà selezionato per completare il processo durante la programmazione degli ordini di lavoro.  
  - Se il valore "0,00" viene immesso in uno degli otto campi precedente, il punteggio di valutazione non verrà utilizzato durante la programmazione degli ordini di lavoro.  

## <a name="the-document-types-tab"></a>Scheda Tipi di documento

Selezionare i tipi di documento che devono essere disponibili per la stampa degli allegati correlati a un report dell'ordine di lavoro. Questa operazione può essere effettuata selezionando un tipo di documento nella sezione **Disponibili** e selezionando il pulsante ![freccia in avanti](media/15-setup-for-objects.png). Per rimuovere un tipo di documento selezionato, selezionare il tipo di documento nella sezione **Selezionati** e selezionare la ![freccia indietro](media/16-setup-for-objects.png).

## <a name="the-number-sequences-tab"></a>Scheda Sequenze numeriche

Selezionare le sequenze numeriche richieste in questa sezione. Sono disponibili due sequenze numeriche per i cespiti: Uno per i cespiti creati manualmente e un'altra per i cespiti creati tramite i cespiti in sospeso.
