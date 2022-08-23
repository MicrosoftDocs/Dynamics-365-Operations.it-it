---
title: Funzionalità di griglia
description: Questo articolo descrive diverse potenti funzionalità del controllo griglia. La nuova funzionalità della griglia deve essere abilitata per avere accesso a queste funzionalità.
author: jasongre
ms.date: 08/09/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2020-02-29
ms.dyn365.ops.version: Platform update 33
ms.openlocfilehash: a8968a1263dfafd67b07b4beb78c51493e95756e
ms.sourcegitcommit: 47534a943f87a9931066e28f5d59323776e6ac65
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/11/2022
ms.locfileid: "9258949"
---
# <a name="grid-capabilities"></a>Funzionalità di griglia

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Il nuovo controllo griglia offre una serie di funzionalità utili e potenti che possono essere utilizzate per migliorare la produttività degli utenti, creare viste più interessanti dei dati e ottenere informazioni dettagliate significative sui dati. In questo articolo vengono illustrate le seguenti funzionalità: 

- Mostrare valori calcolati 
- Digitare prima del sistema
- Valutare espressioni matematiche 
- Raggruppamento di dati tabulari (abilitato separatamente utilizzando la funzionalità **Raggruppamento in griglie**)
- Blocco delle colonne (abilitato separatamente utilizzando la funzionalità **Congelamento delle colonne nelle griglie**)
- Adatta automaticamente larghezza colonna
- Colonne estensibili

## <a name="showing-calculated-values"></a>Mostrare valori calcolati
Nelle app per la finanza e le operazioni, gli utenti possono visualizzare un valore calcolato per ogni colonna numerica in una griglia. Questi valori calcolati sono visualizzati in una sezione di piè di pagina nella parte inferiore della griglia.

[![Visualizzare valori calcolati nelle griglie](./media/grids-aggregation.png)](./media/grids-aggregation.png)

Nelle versioni precedenti alla 10.0.29, il totale è l'unico valore calcolato supportato. Tuttavia, a partire dalla versione 10.0.29, dopo aver abilitato **Funzionalità di aggregazione griglia estese**, gli utenti possono selezionare uno dei seguenti quattro valori calcolati:

- Minimo
- Massimo
- Totale
- Medio

Una singola colonna può mostrare un solo tipo di valore calcolato. Tuttavia, ogni colonna della griglia può essere configurata per mostrare un tipo di valore calcolato differente.

### <a name="showing-the-grid-footer"></a>Visualizzare il piè di pagina della griglia
C'è un'area per i piè di pagina nella parte inferiore di ogni griglia tabulare nelle app per la finanza e le operazioni. Il piè di pagina può mostrare informazioni preziose correlate ai dati visualizzati nella griglia. Di seguito sono riportati alcuni esempi di queste informazioni:

- Il numero di righe selezionate nella tabella (quando è selezionato più di un record)
- I valori calcolati nella parte inferiore delle colonne numeriche configurate (ad esempio, totali complessivi)
- Il numero di righe nel set di dati 

Questo piè di pagina è nascosto per impostazione predefinita, ma può essere attivato. Per visualizzare il piè di pagina per una griglia, seleziona il pulsante **Opzioni griglia** nell'intestazione della griglia, quindi seleziona l'opzione **Mostra piè di pagina**. Dopo aver attivato il piè di pagina per una griglia particolare, tale impostazione verrà memorizzata fino a quando l'utente non sceglierà di nasconderlo. Per nascondere il piè di pagina, seleziona **Nascondi piè di pagina** nel menu **Opzioni griglia**.

### <a name="specifying-columns-with-calculated-values"></a>Specificare colonne con valori calcolati
Al momento, nessuna colonna mostra i valori calcolati per impostazione predefinita. La configurazione viene considerata come un'attività unica, simile alla regolazione delle larghezze delle colonne nelle griglie. Dopo aver specificato che vuoi visualizzare un valore calcolato per una colonna, tale impostazione verrà ricordata alla successiva consultazione della pagina.

Esistono due modi per configurare una colonna affinché mostri un valore calcolato:

- Seleziona e tieni premuto (o fai clic con il pulsante destro del mouse) sulla colonna per la quale vuoi visualizzare un valore calcolato. Se **Funzionalità di aggregazione griglia estese** è abilitata, seleziona **Visualizza totali colonne**, quindi seleziona il valore calcolato desiderato. Se quella funzionalità non è abilitata, seleziona **Calcola totale di questa colonna**. Questa azione provoca tre eventi:

    1. Il piè di pagina della griglia diventa visibile. 
    2. La tua preferenza per la visualizzazione di un valore calcolato per la colonna viene salvata. 
    3. Il calcolo desiderato viene avviato per la colonna e per tutte le altre colonne configurate in precedenza per mostrare un valore calcolato. Il tempo necessario per mostrare i valori calcolati dipende dalla dimensione del set di dati.

- Dopo che il piè di pagina diventa visibile, seleziona **Mostra totale** (o **Seleziona valore calcolato** se **Funzionalità di aggregazione griglia estese** è abilitata) nell'area del piè di pagina nella parte inferiore della colonna per la quale vuoi visualizzare un valore calcolato. Se non vi sono colonne configurate, quel pulsante sarà disponibile nel piè di pagina in tutte le colonne numeriche.

    Dopo che almeno una colonna è stata configurata per mostrare un valore calcolato, il pulsante **Mostra totale** (o **Seleziona valore calcolato**) sarà disponibile solo al passaggio del mouse o con lo stato attivo. L'azione di selezione del pulsante salva solo la tua preferenza per la visualizzazione di un valore calcolato nella colonna, di modo che la preferenza venga applicata durante le successive consultazioni della pagina. Nel piè di pagina, questo stato è indicato da un trattino che appare nella colonna (da notare che il valore calcolato apparirà immediatamente se il set di dati è sufficientemente piccolo).

Se commetti un errore e non desideri più visualizzare un valore calcolato in una colonna specifica, seleziona e tieni premuto (o fai clic con il pulsante destro del mouse) nella colonna, quindi seleziona **Nascondi totale** (o **Visualizza totali colonne \> Nessuno** se **Funzionalità di aggregazione griglia estese** è abilitata). In alternativa, seleziona **Nascondi totale** (o **Nascondi valore calcolato**) nel piè di pagina di quella colonna. Questa preferenza verrà salvata anche per visite future alla pagina. 

### <a name="calculating-aggregate-values"></a>Calcolare valori aggregati
Quando accedi a una pagina in cui il piè di pagina è visibile e le colonne sono già configurate per mostrare valori calcolati, tali valori potrebbero non essere visualizzati nel piè di pagina. Il comportamento dipende dalla dimensione del set di dati nella pagina. Se il set di dati è sufficientemente piccolo, i valori calcolati verranno visualizzati automaticamente, insieme al numero di righe nel set di dati. Se sono presenti trattini nel piè di pagina sotto le colonne configurate, il set di dati è troppo grande per consentire al sistema di mostrare immediatamente i valori calcolati. In questo caso, è necessaria un'azione esplicita per calcolare i valori. Per calcolare i valori, seleziona il pulsante **Calcola** nel piè di pagina. In alternativa, seleziona e tieni premuto (o fai clic con il pulsante destro) in una colonna per la quale vuoi visualizzare il totale, quindi seleziona **Calcola totale di questa colonna** (o **Visualizza totali colonne** e quindi il valore calcolato desiderato se **Funzionalità di aggregazione griglia estese** è abilitata).

Se il completamento del calcolo richiede troppo tempo, puoi annullare l'operazione in qualsiasi momento selezionando **Annulla**. A volte, il set di dati sarà troppo grande per calcolare i valori aggregati (un limite imposto dall'organizzazione). In tal caso, ti verrà richiesto di filtrare maggiormente i tuoi dati.

> [!NOTE]
> Gli amministratori di sistema possono modificare il limite per il numero di record disponibili per il calcolo dei valori aggregati regolando il parametro **Numero massimo di record locali per ogni griglia** nella pagina **Opzioni di prestazioni client**. Il valore predefinito è 25.000 record. Gli amministratori devono prestare attenzione quando regolano questo valore poiché un valore troppo grande può esaurire la memoria disponibile nel computer dell'utente. È consigliabile non avere un valore superiore a 50.000 record.

I valori calcolati verranno aggiornati automaticamente durante l'aggiornamento, l'eliminazione o la creazione di righe nel set di dati.

## <a name="typing-ahead-of-the-system"></a>Digitare prima del sistema
In molti scenari aziendali, la capacità di inserire rapidamente i dati nel sistema è molto importante. Prima dell'introduzione del nuovo controllo della griglia, gli utenti potevano modificare i dati solo nella riga corrente. Pertanto, dopo aver apportato modifiche in una riga, gli utenti non potevano passare a un'altra riga o creare una nuova riga fino a quando il sistema non convalidava correttamente le modifiche nella riga corrente e (in caso di creazione di una riga) non eseguiva tutta la logica associata alla creazione di una nuova riga. Per ridurre il tempo di attesa degli utenti per il completamento di queste operazioni e migliorare la produttività degli utenti stessi, la nuova griglia regola queste azioni di modo che siano asincrone. Gli utenti possono creare nuove righe o spostarsi ad altre righe per apportare modifiche mentre sono in corso le convalide delle righe precedenti e l'esecuzione della logica di creazione delle righe. 

[![Digitare prima del sistema.](./media/gridFastEntry-07-25-2022.gif)](./media/gridFastEntry-07-25-2022.gif)

Per supportare questo nuovo comportamento, una nuova colonna per lo stato della riga è stata aggiunta a destra della colonna di selezione della riga quando la griglia è in modalità di modifica. Questa colonna indica uno dei seguenti stati:

- **Vuoto** - Nessuna immagine di stato indica che la riga è stata salvata correttamente dal sistema.
- **Elaborazione in sospeso** - Questo stato indica che le modifiche nella riga non sono state ancora salvate dal server ma si trovano in una coda di modifiche che devono essere elaborate. Prima di agire all'esterno della griglia, è necessario attendere l'elaborazione di tutte le modifiche in sospeso. Inoltre, il testo in queste righe è in corsivo per indicare lo stato non salvato delle righe. 
- **Stato non valido** - Questo stato indica che durante l'elaborazione della riga è stato attivato un avviso o un messaggio e potrebbe aver impedito al sistema di salvare le modifiche in quella riga. Nella griglia precedente, se l'operazione di salvataggio non riusciva, si era costretti a tornare alla riga per risolvere immediatamente il problema. Nella nuova griglia, viene notificato che si è verificato un problema di convalida, ma è possibile decidere quando si desidera risolvere gli eventuali problemi nella riga. Quando si è pronti per risolvere un problema, è possibile spostare manualmente lo stato attivo sulla riga. In alternativa, è possibile selezionare l'azione **Risolvi questo problema**. Questa azione riporta immediatamente lo stato attivo sulla riga che presenta il problema e consente di apportare modifiche all'interno o all'esterno della griglia. Si noti che l'elaborazione delle successive righe in sospeso viene interrotta fino alla risoluzione di questo avviso di convalida. 
- **In sospeso** - Questo stato indica che l'elaborazione da parte del server è in sospeso perché la convalida della riga ha attivato una finestra di dialogo pop-up che richiede l'input dell'utente. Poiché l'utente potrebbe inserire i dati in un'altra riga, la finestra di dialogo pop-up non viene immediatamente presentata all'utente. Verrà invece visualizzata quando l'utente sceglie di riprendere l'elaborazione. Questo stato è accompagnato da una notifica che informa l'utente della situazione. La notifica include l'azione **Riprendere l'elaborazione** che attiverà la finestra di dialogo pop-up.

### <a name="differences-when-entering-data-ahead-of-the-system"></a>Differenze durante l'immissione di dati prima del sistema
Quando immetti dati prima della posizione che il sistema sta elaborando, puoi aspettarti alcuni cambiamenti nell'esperienza di immissione dei dati:

- Noterai che non sono presenti elenchi di ricerca a discesa, che i valori dei campi non vengono convalidati dopo il passaggio a un'altra colonna nella stessa riga e che le colonne inizialmente non mostrano i valori predefiniti. Questo comportamento si verifica quando esegui operazioni di creazione o aggiornamento prima del sistema. Tuttavia, dopo che il sistema raggiunge la posizione in cui stai attualmente effettuando modifiche, l'esperienza standard verrà ripristinata. Se hai apportato modifiche a un campo che in genere riceve un valore predefinito, le modifiche sostituiscono il valore predefinito del campo quando il server inizia a elaborare la riga.
- Se crei una nuova riga usando il tasto **freccia GIÙ**, tutte le colonne nella griglia appariranno come modificabili. Per impostazione predefinita, lo stato attivo sarà nella prima colonna della nuova riga. Questa colonna potrebbe non essere la stessa colonna con lo stato attivo iniziale nella griglia legacy o la stessa colonna in cui si sposta lo stato attivo dopo la selezione di un pulsante **Nuovo**. La tua organizzazione può personalizzare il sistema e modificare la colonna in cui viene spostato lo stato attivo iniziale quando selezioni il tasto **freccia GIÙ**. Per ulteriori informazioni, vedi la sezione [Specificare la colonna in cui viene spostato lo stato attivo quando vengono create nuove righe utilizzando il tasto freccia GIÙ](#developer-specifying-the-column-that-receives-the-initial-focus-when-new-rows-are-created-by-using-the-down-arrow-key). Indipendentemente da ciò, puoi utilizzare la personalizzazione per ottimizzare ogni griglia per l'immissione di dati. In particolare, puoi riordinare i campi di modo che la prima colonna sia la colonna in cui vuoi iniziare a immettere dati. Potresti anche voler riordinare i campi in generale per l'immissione di dati, per ridurre le tabulazioni e nascondere i campi che non sono richiesti per l'immissione di dati in questa particolare vista.

### <a name="pasting-from-excel"></a>Incollare da Excel
Gli utenti sono sempre stati in grado di esportare i dati dalle griglie delle app per la finanza e le operazioni in Microsoft Excel in Excel utilizzando il meccanismo **Esporta in Excel**. Tuttavia, la possibilità di inserire i dati prima del sistema, consente alla nuova griglia di supportare la copia delle tabelle da Excel e incollarle direttamente nelle griglie nelle app per la finanza e le operazioni. La cella della griglia da cui viene avviata l'operazione "incolla" determina da dove inizia l'operazione incolla della tabella copiata. Il contenuto della griglia viene sovrascritto dal contenuto della tabella copiata, tranne in due casi:

- Se il numero di colonne nella tabella copiata supera il numero di colonne che rimangono nella griglia, a partire dalla posizione incolla, l'utente viene avvisato che le colonne extra sono state ignorate. 
- Se il numero di righe nella tabella copiata supera il numero di righe nella griglia, a partire dalla posizione incolla, le celle esistenti vengono sovrascritte dal contenuto incollato e tutte le righe aggiuntive dalla tabella copiata vengono inserite come nuove righe nella parte inferiore della griglia. 

## <a name="evaluating-math-expressions"></a>Valutare espressioni matematiche
Come booster di produttività, gli utenti possono inserire formule matematiche nelle celle numeriche di una griglia. Non devono eseguire il calcolo in un'app esterna al sistema. Ad esempio, se si immette **=15\*4** e quindi si preme il tasto **TAB** per uscire dal campo, il sistema valuterà l'espressione e salverà un valore di **60** per il campo.

[![Valutare espressioni matematiche.](./media/gridMathExpression-07-25-2022.gif)](./media/gridMathExpression-07-25-2022.gif)

Per fare in modo che il sistema riconosca un valore come espressione, iniziare il valore con un segno uguale (**=**). Per ulteriori informazioni sugli operatori supportati e sulla sintassi, vedere [Simboli matematici supportati](http://bugwheels94.github.io/math-expression-evaluator/#supported-maths-symbols).

A partire dalla versione 10.0.29, la capacità di valutare espressioni matematiche nei controlli numerici è stata estesa ed è ora disponibile anche al di fuori della griglia.

## <a name="grouping-tabular-data"></a>Raggruppamento di dati tabulari
Gli utenti aziendali devono spesso eseguire analisi ad hoc dei dati. Sebbene questa analisi possa essere eseguita esportando dati in Microsoft Excel e usando tabelle pivot, la funzionalità **Raggruppamento in griglie**, che dipende dalla nuova funzionalità controllo griglia, consente agli utenti di organizzare i dati tabulari in modi interessanti nelle app per la finanza e le operazioni. Poiché questa funzionalità estende la funzionalità **Valori calcolati**, **Raggruppamento** ti consente di ottenere informazioni dettagliate significative sui dati fornendo valori calcolati (ad esempio, sottototali) a livello di gruppo.

[![Raggruppare dati in una griglia.](./media/grids-groupingWithTotals.png)](./media/grids-groupingWithTotals.png)

Per utilizzare questa funzionalità, fare clic con il pulsante destro del mouse sulla colonna in base alla quale eseguire il raggruppamento e selezionare **Raggruppa in base a questa colonna**. Questa azione ordina i dati in base alla colonna selezionata, aggiunge una nuova colonna **Raggruppa per** all'inizio della griglia e inserisce "righe di intestazione" all'inizio di ciascun gruppo. Queste righe di intestazione forniscono le seguenti informazioni su ciascun gruppo:

- Valore dei dati per il gruppo 
- Nome della colonna (queste informazioni saranno particolarmente utili in caso di più livelli di raggruppamento)
- Numero di righe di dati in questo gruppo
- Valori calcolati per qualsiasi colonna configurata (ad esempio, subtotali se la colonna è configurata per mostrare un totale)

Insieme alle [Visualizzazioni salvate](saved-views.md) abilitate, puoi salvare un raggruppamento come parte di una vista nelle pagine che consentono di salvare le query nelle viste. Ad esempio, quelli con i selettori di visualizzazioni di grandi dimensioni. Per ulteriori dettagli, vedi la sezione [Passaggio da una visualizzazione all'altra](saved-views.md#switching-between-views). 

### <a name="multiple-levels-of-grouping"></a>Più livelli di raggruppamento
Dopo aver raggruppato i dati in una singola colonna, puoi raggruppare i dati in una colonna diversa selezionando **Raggruppa in base a questa colonna** sulla colonna desiderata. Questo processo può essere ripetuto fino a quando non si ottengono 5 livelli di raggruppamento nidificati, ovvero la profondità massima supportata. A questo punto, non sarà più possibile raggruppare per colonne aggiuntive.

In qualsiasi momento, puoi rimuovere il raggruppamento su qualsiasi colonna facendo clic con il pulsante destro del mouse su quella colonna e selezionando **Separa**. È possibile anche rimuovere il raggruppamento da tutte le colonne selezionando **Opzioni griglia** e poi **Separa tutto**.

### <a name="sorting-grouped-data"></a>Ordinamento dei dati raggruppati
Dopo aver raggruppato i dati in base a una o più colonne, puoi modificare la direzione di ordinamento per qualsiasi colonna di raggruppamento tramite l'intestazione di colonna corrispondente. 

Se ordini una colonna non raggruppata, il raggruppamento rimane intatto. I dati vengono ordinati in ogni gruppo, in base alla colonna selezionata.

### <a name="expanding-and-collapsing-groups"></a>Espansione e compressione di gruppi
Il raggruppamento iniziale di dati avrà tutti i gruppi espansi. È possibile creare visualizzazioni riepilogative dei dati comprimendo i singoli gruppi oppure è possibile utilizzare l'espansione e la compressione del gruppo per facilitare lo spostamento tra i dati. Per espandere o comprimere un gruppo, selezionare il pulsante con la freccia (>) nella riga dell'intestazione del gruppo corrispondente. Tenere presente che lo stato di espansione/compressione dei singoli gruppi **non** è salvato nella personalizzazione.

### <a name="selecting-and-unselecting-rows-at-the-group-level"></a>Selezionare e deselezionare le righe a livello di gruppo
Come è possibile selezionare (o deselezionare) tutte le righe nella griglia selezionando la casella di controllo nella parte superiore della prima colonna nella griglia, è possibile anche selezionare rapidamente (o deselezionare) tutte le righe in un gruppo selezionando la casella di controllo nella riga dell'intestazione del gruppo corrispondente. La casella di controllo nella riga di intestazione del gruppo rifletterà sempre lo stato di selezione corrente delle righe di quel gruppo, indipendentemente dal fatto che tutte le righe siano selezionate, non sia selezionata alcuna riga o solo alcune righe siano selezionate.

### <a name="hiding-column-names"></a>Nascondere i nomi delle colonne
Quando si raggruppano i dati, il comportamento predefinito è mostrare il nome della colonna nella riga dell'intestazione del gruppo. Puoi scegliere di nascondere il nome della colonna nelle righe di intestazione del gruppo selezionando **Opzioni griglia** > **Nascondi nome della colonna del gruppo**.

### <a name="grouping-on-date-and-time-columns"></a>Raggruppamento in colonne di data e ora
Quando esegui il raggruppamento in base ai campi Data o DateTime, hai la possibilità di raggruppare per anno, mese o giorno. Il "valore" del gruppo nella riga di intestazione corrispondente corrisponde al formato di quel campo. Inoltre, per i campi DateTime e Ora, sarai in grado di raggruppare per ora, minuto o secondo.

> [!IMPORTANT]
> Al momento, gli utenti non possono aggiungere una colonna di raggruppamento dopo aver eseguito il raggruppamento in un segmento di una colonna di data o ora.

## <a name="freezing-columns"></a>Blocco delle colonne
Alcune colonne in una griglia potrebbero essere abbastanza importanti per il contesto da non desiderare che scorrano fuori dalla visualizzazione. Invece, è consigliabile fare in modo che i valori in tali colonne siano sempre visibili. La funzionalità **Congelamento delle colonne nelle griglie** fornisce questa flessibilità agli utenti. 

[![Bloccare colonne in una griglia.](./media/gridFreezingColumns-07-25-2022.gif)](./media/gridFreezingColumns-07-25-2022.gif)

Per bloccare una colonna, fare clic con il pulsante destro del mouse nell'intestazione della colonna, quindi selezionare **Blocca colonna**. La prima volta che si completa questo passaggio, la colonna selezionata diventa la prima colonna e non scorrerà più fuori dalla visualizzazione. Qualsiasi colonna successiva che blocchi verrà aggiunta a destra dell'ultima colonna bloccata. È possibile utilizzare la funzionalità di spostamento standard per riordinare le colonne bloccate in base alle proprie esigenze. Tuttavia, le colonne bloccate non possono essere spostate in modo che vengano visualizzate nel set di colonne non congelate. Allo stesso modo, le colonne non bloccate non possono essere spostate in modo che vengano visualizzate nel set di colonne bloccate.

Per sbloccare una colonna, fare clic con il pulsante destro del mouse nell'intestazione della colonna bloccata, quindi selezionare **Sblocca colonna**. 

Notare che la selezione della riga e le colonne dello stato della riga nella nuova griglia sono sempre bloccate come le prime due colonne. Pertanto, quando queste colonne sono incluse in una griglia, saranno sempre visibili all'utente, indipendentemente dalla posizione di scorrimento orizzontale nella griglia. Queste due colonne non possono essere riordinate.

## <a name="autofit-column-width"></a>Adatta automaticamente larghezza colonna
Come in Excel, gli utenti possono forzare il ridimensionamento di una colonna in base al contenuto attualmente mostrato in quella colonna. Tocca due volte (o fai doppio clic) i quadratini di ridimensionamento nella colonna. In alternativa, sposta lo stato attivo nell'intestazione della colonna, quindi seleziona **A** (per adattamento automatico).

## <a name="frequently-asked-questions"></a>Domande frequenti
### <a name="how-do-i-enable-the-new-grid-control-in-my-environment"></a>Come si abilita il nuovo controllo della griglia nell'ambiente? 

La funzionalità **Nuovo controllo griglia** è disponibile direttamente in Gestione funzionalità in qualsiasi ambiente. Dopo aver abilitato la funzionalità in Gestione funzionalità, tutte le sessioni utente successive utilizzeranno il nuovo controllo della griglia. 

Questa funzionalità ha iniziato ad essere abilitata per impostazione predefinita a partire dalla versione 10.0.21. Diventerà obbligatoria nell'ottobre 2022.

## <a name="developer-opting-out-individual-pages-from-using-the-new-grid"></a>[Sviluppatore] Rifiuto di singole pagine dall'uso della nuova griglia 
Se l'organizzazione rileva una pagina che presenta alcuni problemi durante l'utilizzo della nuova griglia, è disponibile un'API per consentire a un singolo modulo di utilizzare il controllo della griglia legacy, consentendo comunque al resto del sistema di utilizzare il nuovo controllo della griglia. Per rifiutare esplicitamente una singola pagina della nuova griglia, aggiungere il seguente post di chiamata `super()` nel metodo `run()` del modulo.

```this.forceLegacyGrid();```

Questa API verrà infine deprecata per consentire la rimozione del controllo della griglia legacy. Tuttavia, rimarrà disponibile per almeno 12 mesi dopo l'annuncio della deprecazione. Se qualsiasi problema richiede l'utilizzo di questa API, segnalalo a Microsoft.

### <a name="forcing-a-page-to-use-the-new-grid-after-previously-opting-out-the-grid"></a>Forzare una pagina a utilizzare la nuova griglia dopo aver precedentemente disattivato la griglia
Se hai disattivato l'utilizzo della nuova griglia per una singola pagina, potresti voler riattivare in seguito la nuova griglia dopo che i problemi sottostanti sono stati risolti. Per fare ciò, devi semplicemente rimuovere la chiamata a `forceLegacyGrid()`. La modifica non avrà effetto fino a quando non si verifica una delle seguenti condizioni:

- **Ridistribuzione dell'ambiente**: quando un ambiente viene aggiornato e ridistribuito, la tabella che archivia le pagine che sono state escluse dalla nuova griglia (FormControlReactGridState) viene cancellata automaticamente.
- **Svuotamento manuale della tabella**: per gli scenari di sviluppo, sarà necessario utilizzare SQL per cancellare la tabella FormControlReactGridState e quindi riavviare Microsoft Dynamics AX Application Object Server (AOS). Questa combinazione di azioni ripristinerà la memorizzazione nella cache delle pagine che sono state escluse dalla nuova griglia.

## <a name="developer-opting-individual-grids-out-of-the-typing-ahead-of-the-system-capability"></a>[Sviluppatore] Eliminazione delle singole griglie dalla digitazione prima della capacità del sistema
Sono apparsi alcuni scenari che non si prestano a funzionare bene con la funzionalità *Digitare prima del sistema* della griglia. (Ad esempio, un codice che viene attivato quando una riga viene convalidata provoca l'attivazione di una ricerca sull'origine dati e la ricerca può quindi danneggiare le modifiche non vincolate sulle righe esistenti.) Se l'organizzazione rileva uno scenario del genere, è disponibile un'API che consente a lo sviluppatore esclude una singola griglia dalla convalida di riga asincrona e ripristina il comportamento legacy.

Quando la convalida di riga asincrona è disabilitata in una griglia, gli utenti non possono creare una nuova riga o passare a una riga esistente diversa nella griglia mentre sono presenti problemi di convalida nella riga corrente. Come effetto collaterale di questa azione, le tabelle non possono essere incollate da Excel nelle griglie di finanza e operazioni.

Per rifiutare esplicitamente una singola griglia di una convalida di riga asincrona, aggiungere il seguente post di chiamata `super()` nel metodo `run()` del modulo.

```<gridControl>.allowPreemptiveClient(false);```

> [!NOTE]
> - Questa chiamata dovrebbe essere invocata solo in casi eccezionali e non dovrebbe essere la norma per tutte le griglie.
> - Non è consigliabile attivare questa API in fase di esecuzione dopo il caricamento del modulo.

## <a name="developer-size-to-available-width-columns"></a>[Sviluppatore] Colonne dalla dimensione alla larghezza disponibile
Se uno sviluppatore imposta la proprietà **WidthMode** su **SizeToAvailable** per le colonne all'interno della nuova griglia, tali colonne hanno inizialmente la stessa larghezza che avrebbero se la proprietà fosse impostata su **SizeToContent**. Tuttavia, si allungano per utilizzare qualsiasi larghezza extra disponibile all'interno della griglia. Se la proprietà è impostata su **SizeToAvailable** per più colonne, tutte queste colonne condividono qualsiasi larghezza extra disponibile all'interno della griglia. Tuttavia, se un utente ridimensiona manualmente una di queste colonne, la colonna diventa statica. Rimarrà a quella larghezza e non si allungherà più per occupare la larghezza della griglia disponibile in più.

## <a name="developer-specifying-the-column-that-receives-the-initial-focus-when-new-rows-are-created-by-using-the-down-arrow-key"></a>[Sviluppatore] Specificare la colonna in cui viene spostato lo stato attivo quando vengono create nuove righe utilizzando il tasto freccia GIÙ.
Come discusso nella sezione [Differenze durante l'inserimento di dati prima del sistema](#differences-when-entering-data-ahead-of-the-system), se la funzionalità "Digitare prima del sistema" è abilitata e un utente crea una nuova riga utilizzando il tasto **freccia GIÙ**, il comportamento predefinito consiste nello spostare lo stato attivo nella prima colonna della nuova riga. Questa esperienza potrebbe differire dall'esperienza nella griglia legacy o quando si seleziona un pulsante **Nuovo**.

Gli utenti e le organizzazioni possono creare viste salvate ottimizzate per l'immissione di dati (ad esempio, puoi riordinare le colonne di modo che la prima colonna sia quella in cui vuoi iniziare a immettere dati). Inoltre, a partire dalla versione 10.0.29, le organizzazioni possono modificare questo comportamento utilizzando il metodo **selectedControlOnCreate()**. Questo metodo consente a uno sviluppatore di specificare la colonna in cui viene spostato lo stato attivo iniziale quando si crea una nuova riga utilizzando il tasto **freccia GIÙ**. Come input, questa API usa l'ID controllo che corrisponde alla colonna in cui deve essere spostato lo stato attivo iniziale.

## <a name="known-issues"></a>Problemi noti
Questa sezione mantiene un elenco di problemi noti per il nuovo controllo griglia.

### <a name="open-issues"></a>Problemi aperti
- Dopo aver abilitato la funzionalità **Nuovo controllo griglia**, alcune pagine continueranno a utilizzare il controllo griglia esistente. Questo avverrà nelle seguenti situazioni:
 
    - È presente un elenco di schede nella pagina che viene visualizzata in più colonne.
    - È presente un elenco di schede raggruppate sulla pagina.
    - Una colonna della griglia con un controllo estendibile non reattivo.

    Quando un utente incontra per la prima volta una di queste situazioni, verrà visualizzato un messaggio sull'aggiornamento della pagina. Una volta visualizzato questo messaggio, la pagina continuerà a utilizzare la griglia esistente per tutti gli utenti fino al prossimo aggiornamento della versione del prodotto. Una migliore gestione di questi scenari, in modo che la nuova griglia possa essere utilizzata, verrà presa in considerazione per un aggiornamento futuro.

- [KB 4582758] I record sono sfocati quando si modifica lo zoom da 100 a qualsiasi altra percentuale

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]

