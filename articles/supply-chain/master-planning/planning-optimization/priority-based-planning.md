---
title: Pianificazione basata sulle priorità
description: Questo argomento descrive la funzionalità di pianificazione basata sulle priorità di Microsoft Dynamics 365 Supply Chain Management.
author: t-benebo
ms.date: 10/15/2021
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2021-10-15
ms.dyn365.ops.version: 10.0.23
ms.openlocfilehash: bdca7ef99716cebee5c4eb41d1e51793b9468dd4
ms.sourcegitcommit: ad1afc6893a8dc32d1363395666b0fe1d50e983a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2022
ms.locfileid: "8468302"
---
# <a name="priority-based-planning"></a>Pianificazione basata sulle priorità

[!include [banner](../../includes/banner.md)]

Questo argomento descrive la funzionalità di pianificazione basata sulle priorità di Microsoft Dynamics 365 Supply Chain Management. La funzionalità aggiunge il supporto per la pianificazione basata sulla domanda, che è una fase della pianificazione del fabbisogno di materiale basato sulla domanda (DDMRP). La pianificazione basata sulle priorità consente a Ottimizzazione pianificazione di generare ordini pianificati basati sulle priorità di pianificazione anziché sulle date dei requisiti.

La pianificazione basata sulle priorità consente di assegnare la priorità agli ordini di rifornimento per garantire che la domanda urgente abbia la priorità rispetto alla domanda meno importante. Ad esempio, un ordine di rifornimento per esaurimento scorte avrà la priorità rispetto a un ordine di rifornimento di rifornimento standard. Il sistema può dividere automaticamente gli ordini più grandi in ordini più piccoli separati in cui le righe dell'ordine sono raggruppate per priorità. Può quindi elaborare prima tutti gli ordini ad alta priorità.

Per ottenere una rapida panoramica di questa funzionalità, vedi il seguente video: [Supporto all'ottimizzazione della pianificazione per la pianificazione basata sulle priorità in Dynamics 365 Supply Chain Management](https://youtu.be/GmMHzFETTQc).

## <a name="turn-on-priority-based-planning-in-your-system"></a>Attivare la pianificazione basata sulle priorità nel tuo sistema

Prima di poter utilizzare questa funzione, è necessario attivarla nel sistema. Gli amministratori possono utilizzare le impostazioni della [gestione delle funzionalità](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) per controllare lo stato della funzione e abilitarla. Nell'area di lavoro **Gestione funzionalità**, la funzione è elencata nel modo seguente:

- **Modulo:** *Pianificazione generale*
- **Nome funzionalità:** *Supporto MRP basato sulla priorità per Ottimizzazione pianificazione*

## <a name="where-and-how-planning-priorities-are-assigned"></a>Dove e come vengono assegnate le priorità di pianificazione

Le informazioni relative alla *priorità di pianificazione* su domanda e offerta sono la struttura di base della pianificazione basata sulle priorità. La pianificazione delle priorità definisce l'importanza di una linea di domanda o offerta. L'ottimizzazione della pianificazione lo utilizza quando il campo **Codice copertura** è impostato su *Priorità*.

La priorità di pianificazione è in genere un numero compreso tra 0 (zero) e 100, dove 0 rappresenta l'importanza più elevata. È mostrato e impostato nel campo **Priorità di pianificazione**. Puoi trovare questo campo nelle seguenti pagine: **Righe di previsione della domanda**, **Dettagli ordini cliente**, **Dettagli ordine fornitore**, **Dettagli ordine di trasferimento** e **Dettagli ordine pianificato**.

Quando il campo **Codice copertura** per l'articolo o il gruppo di copertura in questione è impostato su *Priorità*, Ottimizzazione pianificazione bilancia l'offerta con la domanda utilizzando un approccio basato sulla domanda in quanto calcola la priorità di pianificazione e, per ogni prodotto rilasciato, considera i valori impostati per i campi **Minimo**, **Punto di riordino** e **Massimo** nella pagina **Copertura articoli**.

> [!NOTE]
> Il valore *Priorità* è disponibile per il campo **Codice di copertura** solo quando è abilitata l'ottimizzazione della pianificazione.

I *modelli di priorità di pianificazione* correlati controllano la priorità di pianificazione e suddividono gli ordini pianificati per intervallo di priorità. Consentono inoltre di impostare valori di priorità di pianificazione predefiniti per ogni tipo di domanda o offerta e definire il metodo di calcolo della priorità.

## <a name="types-of-priority-calculation-methods"></a>Tipi di metodi del calcolo priorità

Ogni modello di priorità di pianificazione ha un'impostazione **Metodo di calcolo priorità** che controlla il modo in cui la pianificazione generale applica la priorità agli ordini pianificati. I valori disponibili sono *Percentuale della quantità massima in magazzino* e *Intervalli di priorità*. *Intervalli di priorità* rappresenta una versione più avanzata del metodo *Percentuale della quantità massima in magazzino*.

### <a name="percent-of-maximum-inventory-quantity"></a>Percentuale della quantità massima in magazzino

Nel metodo di calcolo *Percentuale della quantità massima in magazzino*, il calcolo della priorità di fornitura trova le *scorte disponibili totali* (portata netta) in percentuale del valore **Quantità massima in magazzino** impostato per un elemento. Viene quindi creato un singolo ordine pianificato per articolo e fornitore (a meno che non venga utilizzata la quantità massima dell'ordine per forzare una suddivisione). La priorità di pianificazione dell'ordine viene calcolata come percentuale del massimo.

Viene utilizzata la seguente formula:

*Percentuale del massimo* = (*Posizione portata netta* × 100) ÷ *Valore massimo della quantità di scorte dalla copertura dell'articolo*

In questa formula, *Posizione portata netta* viene calcolata nel modo seguente:

*Posizione portata netta* = *Disponibili* + *Su ordine* – *Domanda qualificata*

- *Su ordine* è la fornitura prevista.
- *Domanda qualificata* rappresenta il fabbisogno netto che ha la data del fabbisogno all'interno dell'intervallo temporale di pianificazione.

Durante l'esecuzione della pianificazione generale, vengono creati nuovi ordini pianificati quando la posizione della portata netta è inferiore alla quantità del punto di riordino per un articolo. La quantità dell'ordine pianificato è la differenza tra il valore **Quantità massima in magazzino** impostato a livello di articolo e la posizione della portata netta. La priorità dell'ordine pianificato viene calcolata come una percentuale di *posizione portata netta* del valore **Quantità massima in magazzino**.

> [!NOTE]
> La priorità calcolata non può essere negativa, anche se la domanda supera l'offerta totale. Se la domanda supera l'offerta totale, la priorità calcolata viene impostata su 0 (zero).

### <a name="priority-ranges"></a>Intervalli di priorità

Il metodo di calcolo *Intervalli di priorità* è più avanzato del metodo *Percentuale della quantità massima in magazzino* ed è configurato a livello del modello di priorità di pianificazione. È possibile creare diversi nuovi ordini di fornitura pianificati per soddisfare la domanda per articolo. Le priorità della fornitura pianificata seguono i valori che sono definiti nella griglia **Intervalli di priorità della pianificazione** sulla pagina **Modelli di priorità della pianificazione**.

Le seguenti regole aggiuntive entrano in vigore quando il campo **Metodo di calcolo priorità** è impostato su *Intervalli di priorità*:

- Se l'opzione **Considera la priorità della domanda** per il modello di priorità pianificato è impostata su *Sì*, la priorità impostata su ciascuna riga della domanda limiterà il bucket dell'intervallo di priorità. La priorità di qualsiasi nuovo ordine pianificato per l'offerta non sarà inferiore alla priorità della domanda. Il valore superiore dell'intervallo è considerato una soglia con cui viene confrontato il valore di priorità della domanda. Se la priorità della domanda è esattamente a metà tra i valori di soglia superiori di due intervalli, verrà selezionato l'intervallo con la priorità più alta (ovvero, il valore di priorità più basso).
- Se il campo **Creazione ordine pianificato** per il modello di priorità pianificato è impostato su *Offerta singola con priorità più importante*, verrà creata una sola offerta per soddisfare fino al massimo. La priorità sarà impostata sulla priorità del primo intervallo che attiverà un'offerta.
- Se non ci sono scorte disponibili, nessuna offerta e nessuna domanda, la riga nella griglia **Intervalli di priorità della pianificazione** dove il campo **Da quantità** è impostato su *Zero* verrà utilizzato.
- Se c'è domanda, ma non ci sono scorte disponibili o un'offerta prevista, la riga nella griglia **Intervalli di priorità della pianificazione** dove il campo **Da quantità** è impostato su *Zero* verrà utilizzato.
- Quando viene valutato l'intervallo di cui fa parte la domanda, l'impostazione dell'opzione **Considera la priorità della domanda** avrà comunque effetto.

## <a name="differences-between-traditional-timeline-calculations-and-priority-based-planning"></a>Differenze tra i calcoli della sequenza temporale tradizionali e la pianificazione basata sulle priorità

La pianificazione basata sulle priorità differisce dai calcoli della sequenza temporale tradizionali nei seguenti modi:

- Tutti i normali processori di pianificazione preliminare sono ancora attivi. Questi pre-processori includono il pegging degli ordini pianificati approvati rispetto alla domanda di vendita, il mapping delle richieste di acquisto e la logica di prenotazione. Viene elaborata solo la domanda che non viene soddisfatta da questi pre-processori.
- Durante il pegging, viene considerata tutta l'offerta, indipendentemente dalla sua priorità. Questa offerta include le scorte disponibili, l'offerta rilasciata e la parte senza pegging degli ordini pianificati approvati.
- Nessuna domanda di "giorni negativi" può essere collegata all'offerta durante l'intero periodo di copertura.
- Quando viene eseguito il pegging dell'offerta a fronte della domanda, l'offerta con la priorità più alta (ovvero il valore di priorità più basso) viene utilizzata per prima. Si considera che l'offerta disponibile abbia un valore di priorità pari a 0 (zero). Pertanto, verrà consumata come primissima origine.
- Le nuove righe di offerta pianificate verranno create in base alle normali regole per la dimensione minima dell'ordine, la dimensione massima dell'ordine, la quantità multipla e così via.

## <a name="planning-priority-models"></a>Modelli di priorità della pianificazione

*Modelli di priorità di pianificazione* vengono assegnati ai gruppi di copertura e controllano la priorità di pianificazione per gli ordini pianificati. Definiscono la logica che determina come viene calcolato il valore della priorità di pianificazione per ogni ordine pianificato e come viene assegnata la priorità agli ordini pianificati, alle righe di offerta e alle righe di domanda.

Per lavorare con i modelli di priorità di pianificazione, vai a **Pianificazione generale \> Imposta \> Modelli di priorità della pianificazione**. Come è stato discusso in precedenza, una delle impostazioni più importanti di un modello è il valore **Metodo di calcolo priorità**. Questa impostazione controlla il metodo di calcolo utilizzato quando la pianificazione generale assegna un valore di priorità agli ordini pianificati.

> [!NOTE]
> I modelli di priorità di pianificazione si applicano a tutta l'organizzazione, a tutte le persone giuridiche.

### <a name="coverage-group"></a>Gruppo di copertura

Imposta un nuovo gruppo di copertura che prevedi di utilizzare per la pianificazione basata sulle priorità, come descritto in [Definire le regole di copertura per gli articoli](../tasks/define-coverage-rules-items.md). Dopo aver creato il gruppo di copertura, imposta i seguenti campi aggiuntivi:

- **Codice di copertura**: seleziona *Priorità* se il gruppo di copertura utilizzerà la pianificazione basata sulle priorità.
- **Modello di priorità della pianificazione**: seleziona qualsiasi modello di priorità di pianificazione a livello di organizzazione.

### <a name="item-coverage"></a>Copertura articoli

Configura le impostazioni di copertura dell'articolo come descritto in [Impostazioni di copertura](../coverage-settings.md). Per impostazione predefinita, il valore **Codice di copertura** selezionato per il gruppo di copertura viene copiato nelle impostazioni di copertura dell'articolo. Tuttavia, è possibile sostituire il valore predefinito in base alle esigenze. In alcuni casi, il campo **Codice di copertura** per un record di copertura dell'articolo è impostato su *Pianificazione*, ma non è definito alcun modello di priorità di pianificazione per il gruppo di copertura correlato. In questi casi, qualsiasi modello in cui il campo **Metodo di calcolo delle priorità** è impostato su *Percentuale della quantità massima in magazzino* e il campo **Creazione ordine pianificato** è impostato su *Offerta singola con priorità più importante* verrà applicato per impostazione predefinita.

Imposta il campo **Codice di copertura** su *Priorità* per rendere disponibile il campo **Punto di riordino** nelle impostazioni di copertura dell'articolo. In questo campo, inserisci la quantità del punto di riordino che il sistema dovrebbe utilizzare per determinare quando inserire gli ordini pianificati che hanno un valore **Codice di copertura** di tipo *Priorità*.

La quantità del punto di riordino viene spesso calcolata come la domanda durante il lead time più un valore minimo (stock di sicurezza). Deve essere un valore compreso tra i valori **Minimo** e **Massimo**.

Ad esempio, è consigliabile impostare i campi nel modo seguente:

- **Minimo:** *10*
- **Punto di riordino:** *45*
- **Massimo:** *60*

Per questo esempio, la quantità del punto di riordino si basa su un lead time di sette giorni e un utilizzo medio giornaliero di 5. Pertanto, la domanda durante il lead time è 35. Il valore minimo di 10 (stock di sicurezza) viene quindi aggiunto per ottenere un punto di riordino di 45. Quando si utilizza questa configurazione, l'offerta verrà suggerita quando il livello di scorte disponibili previsto è inferiore a 45. La priorità dell'ordine sarà basata sull'impostazione della priorità di pianificazione.

### <a name="manage-planning-priority-models"></a>Gestire modelli di priorità della pianificazione

Per utilizzare i modelli di priorità di pianificazione. segui questi passaggi:

1. Vai a **Pianificazione generale \> Imposta \> Modelli di priorità di pianificazione**.
1. Seleziona un modello esistente nel riquadro dell'elenco oppure selezionare **Nuovo** nel riquadro azioni per creare un nuovo modello.
1. Nell'intestazione del record, impostare i seguenti campi:

    - **Nome**: immetti un nome per il modello. Il nome deve essere univoco per tutte le persone giuridiche dell'organizzazione.
    - **Descrizione** - Immetti una descrizione del modello.
    - **Metodo di calcolo priorità** – seleziona uno dei valori seguenti:

        - *Intervalli di priorità* – Quando selezioni questo valore, la griglia **Intervalli di priorità della pianificazione** diventa disponibile. Qui è necessario stabilire diversi intervalli di priorità per definire il valore della priorità di pianificazione.
        - *Percentuale della quantità massima in magazzino* – Calcola il valore della priorità di pianificazione come percentuale, in base al livello di scorte previsto rispetto alla quantità di scorte massima.

    - **Creazione ordine pianificato** – Questo campo è disponibile quando il campo **Metodo di calcolo delle priorità** è impostato su *Intervalli di priorità*. Selezionare uno dei seguenti valori:

        - *Offerta singola con priorità più importante* – Non dividere gli ordini pianificati in base all'intervallo di priorità. La priorità di pianificazione per un ordine pianificato si basa sull'intervallo di priorità più importante (ovvero, il valore di priorità di pianificazione più basso).
        - *Dividi in base agli intervalli di priorità* – Suddividi la domanda in più ordini pianificati, in base agli intervalli di priorità di pianificazione. La priorità di pianificazione per i singoli ordini pianificati è definita dalla priorità di pianificazione dell'intervallo di priorità di pianificazione correlato.

    - **Considera la priorità della domanda** – Imposta questa opzione su *Sì* per limitare la priorità di un nuovo ordine pianificato creato per l'offerta. (La priorità non sarà inferiore alla priorità della relativa domanda.) Se imposti questa opzione su *No*, la priorità dell'ordine di domanda non verrà considerata quando viene calcolata la priorità dell'ordine di offerta.

1. Se imposti il campo **Metodo di calcolo delle priorità** su *Intervalli di priorità*, utilizza i pulsanti **Aggiungi** e **Rimuovi** sulla barra degli strumenti della Scheda dettaglio **Intervalli di priorità della pianificazione** per aggiungere o rimuovere le righe dell'intervallo di priorità in base alle esigenze. Se esistono più righe e si inserisce una nuova riga, la priorità di pianificazione verrà impostata automaticamente sulla media della riga selezionata e della riga sopra di essa. Per ciascuna riga, imposta i seguenti campi:

    - **Priorità di pianificazione** – Immetti qualsiasi valore compreso tra 0,00 e 100,00. Questo valore rappresenta la priorità di pianificazione utilizzata per la riga. Il valore di priorità più basso corrisponde alla priorità più elevata. Viene assegnato un valore predefinito, ma puoi modificarlo in base alle esigenze. Lo stesso valore **Priorità di pianificazione** non può essere utilizzato per più di un intervallo di priorità di pianificazione nello stesso modello di priorità di pianificazione.
    - **Descrizione** – Immetti una descrizione dell'intervallo di priorità di pianificazione (ad esempio *Da punto di riordino a massimo*).
    - **Dalla quantità** – Il limite inferiore dell'intervallo di priorità di pianificazione. Questo valore è di sola lettura e si basa sui valori **Alla quantità** e **Percentuale quantità finale** per l'intervallo di priorità di pianificazione precedente.
    - **Alla quantità** – Seleziona il campo dalla copertura dell'articolo da utilizzare per definire il limite superiore dell'intervallo. I seguenti valori sono supportati e influenzeranno il valore **Dalla quantità** dell'intervallo successivo:

        - *Zero* – Questo valore rappresenta un intervallo da negativo a zero (*Zero o meno* a *Zero*). Per le righe in cui è selezionato questo valore, il campo **Percentuale quantità finale** è di sola lettura ed è sempre impostato su *100* per cento.
        - *Quantità minima in magazzino* – Questo valore rappresenta il valore **Minimo** per un articolo nella pagina **Copertura dell'articolo**. Per le righe in cui è selezionato questo valore, il campo **Percentuale quantità finale** è modificabile e viene utilizzato per impostare il valore **Dalla quantità** dell'intervallo successivo (ad esempio, su *80% della quantità minima di magazzino*).
        - *Punto di riordino* – Questo valore rappresenta il valore **Punto riordino** per un articolo nella pagina **Copertura dell'articolo**. Per le righe in cui è selezionato questo valore, il campo **Percentuale quantità finale** è modificabile e viene utilizzato per impostare il valore **Dalla quantità** per l'intervallo successivo (ad esempio, su *80% del punto di riordino*).
        - *Quantità massimo in magazzino* – Questo valore rappresenta il valore **Massimo** per un articolo nella pagina **Copertura dell'articolo**. Per le righe in cui è selezionato questo valore, il campo **Percentuale quantità finale** è modificabile e viene utilizzato per impostare il valore **Dalla quantità** dell'intervallo successivo (ad esempio, su *80% della quantità minima di magazzino*).
        - *Infinito* – Questo valore rappresenta un livello superiore infinito dell'intervallo (da *Infinito o meno* a *Infinito*). Per le righe in cui è selezionato questo valore, il campo **Percentuale quantità finale** è di sola lettura ed è sempre impostato su *100* per cento.

    - **Percentuale quantità finale** – Immetti un valore percentuale utilizzato per calcolare il limite superiore dell'intervallo di priorità di pianificazione, in base al valore selezionato nel campo **A quantità**. Ad esempio, se il campo **Alla quantità** è impostato su *Quantità minima di magazzino*, e il campo **Percentuale quantità finale** è impostato su *50*, il limite superiore sarà il 50 percento della quantità minima di magazzino dalla copertura dell'articolo correlato.

1. Nella Scheda dettaglio **Impostazioni predefinite priorità di pianificazione**, imposta i campi in base alle esigenze per definire le priorità di pianificazione predefinite per ogni tipo di riga di domanda o offerta (ordine di vendita, ordine di acquisto, ordine di trasferimento o previsione della domanda). Si possono immettere solo valori positivi.

## <a name="view-and-maintain-planning-priority"></a>Visualizzare e gestire la priorità della pianificazione

La priorità di pianificazione è mostrata e impostata nel campo **Priorità di pianificazione**. Puoi trovare questo campo nelle pagine elencate nella tabella seguente. La priorità è in genere un numero compreso tra 0 (zero) e 100, dove 0 rappresenta l'importanza più elevata.

| Pagina | Posizione del campo | Origine del valore |
|---|---|---|
| Righe di previsione della domanda | <p>Scheda **Articolo**</p><p>(Seleziona una riga nella sezione superiore, quindi seleziona la scheda **Articolo**).</p> | Valore predefinito o valore impostato manualmente |
| Dettagli ordini cliente | <p>Scheda **Consegna** nella Scheda dettaglio **Dettagli riga**</p><p>(Seleziona una riga nella Scheda dettaglio **Righe ordine cliente**, quindi, nella Scheda dettaglio **Dettagli riga**, seleziona la scheda **Consegna**).</p> | Valore predefinito, valore interaziendale o valore impostato manualmente |
| Dettagli ordine fornitore | <p>Scheda **Consegna** nella Scheda dettaglio **Dettagli riga**</p><p>(Seleziona una riga nella Scheda dettaglio **Righe ordine fornitore**, quindi, nella Scheda dettaglio **Dettagli riga**, seleziona la scheda **Consegna**).</p> | Valore impostato durante il consolidamento da ordini pianificati, valore interaziendale o valore impostato manualmente |
| Dettagli ordine di trasferimento | <p>Scheda **Consegna** nella Scheda dettaglio **Dettagli riga**</p><p>(Seleziona una riga nella Scheda dettaglio **Righe ordine trasferimento**, quindi, nella Scheda dettaglio **Dettagli riga**, seleziona la scheda **Consegna**).</p> | Valore impostato durante il consolidamento da ordini pianificati o valore impostato manualmente |
| Dettagli ordine pianificato | Scheda dettaglio **Generale** | Valore calcolato durante la pianificazione generale o valore impostato manualmente |

### <a name="intercompany-trade"></a>Commercio interaziendale

Il valore **Priorità di pianificazione** sulle righe domanda e offerta interaziendali è condiviso tra le entità collegate. La modifica su entrambi i lati si rifletterà sulla riga dell'ordine collegata.

Di seguito sono riportati alcuni esempi.

- Un utente modifica la priorità di pianificazione per una riga ordine cliente interaziendale da 20 a 30. Questa modifica si riflette sulla riga dell'ordine fornitore interaziendale collegata.
- Un utente modifica la priorità di pianificazione per una riga ordine fornitore interaziendale da 40 a 50. Questa modifica si riflette sulla riga dell'ordine cliente interaziendale collegata.
