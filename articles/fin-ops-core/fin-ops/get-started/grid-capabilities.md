---
title: Funzionalità del controllo griglia
description: Questo argomento descrive diverse potenti funzionalità del controllo griglia. La nuova funzionalità della griglia deve essere abilitata per avere accesso a queste funzionalità.
author: jasongre
ms.date: 03/21/2022
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
ms.openlocfilehash: 08348185a424d20b6da1563189496b7dd51944d9
ms.sourcegitcommit: edc887e0526c415466e9691e642028ecd97cdbe7
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/14/2022
ms.locfileid: "8602964"
---
# <a name="grid-capabilities"></a>Funzionalità di griglia

[!include [banner](../includes/banner.md)]

Il nuovo controllo griglia offre una serie di funzionalità utili e potenti che possono essere utilizzate per migliorare la produttività degli utenti, creare viste più interessanti dei dati e ottenere informazioni dettagliate significative sui dati. In questo articolo vengono illustrate le seguenti funzionalità: 

- Calcolo totali in corso
- Digitare prima del sistema
- Valutare espressioni matematiche 
- Raggruppamento di dati tabulari (abilitato separatamente utilizzando la funzionalità **Raggruppamento in griglie**)
- Blocco delle colonne (abilitato separatamente utilizzando la funzionalità **Congelamento delle colonne nelle griglie**)
- Adatta automaticamente larghezza colonna
- Colonne estensibili

## <a name="calculating-totals"></a>Calcolo totali in corso
Nelle app per finanza e operazioni, gli utenti hanno la possibilità di vedere i totali nella parte inferiore delle colonne numeriche nelle griglie. Questi totali sono visualizzati in una sezione a piè di pagina nella parte inferiore della griglia. 

### <a name="showing-the-grid-footer"></a>Visualizzare il piè di pagina della griglia
C'è un'area per i piè di pagina nella parte inferiore di ogni griglia tabulare nelle app per finanza e operazioni. Il piè di pagina può mostrare informazioni preziose correlate ai dati visualizzati nella griglia. Di seguito sono riportati alcuni esempi di queste informazioni:

- Il numero di righe selezionate nella tabella (quando è selezionato più di un record)
- I totali complessivi nella parte inferiore delle colonne numeriche configurate
- Il numero di righe nel set di dati 

Questo piè di pagina è nascosto per impostazione predefinita, ma può essere attivato. Per visualizzare il piè di pagina per una griglia, seleziona il pulsante **Opzioni griglia** nell'intestazione della griglia, quindi seleziona l'opzione **Mostra piè di pagina**. Dopo aver attivato il piè di pagina per una griglia particolare, tale impostazione verrà memorizzata fino a quando l'utente non sceglierà di nasconderlo. Per nascondere il piè di pagina, seleziona **Nascondi piè di pagina** nel menu **Opzioni griglia**.

### <a name="specifying-columns-with-totals"></a>Specificare colonne con totali
Al momento, nessuna colonna mostra i totali per impostazione predefinita. Questa è considerata come un'attività di impostazione unica, simile alla regolazione della larghezza delle colonne nelle griglie. Dopo aver specificato che si desidera visualizzare i totali per una colonna, tale impostazione verrà ricordata alla successiva visita della pagina.

Esistono due modi per configurare una colonna per mostrare un totale: 

- Fare clic con il pulsante destro del mouse sulla colonna per la quale si desidera visualizzare un totale e selezionare **Totale di questa colonna**. Questa azione provoca tre eventi:

    1. Il piè di pagina diventa visibile. 
    2. La preferenza per la visualizzazione di un totale in questa colonna viene salvata. 
    3. Un calcolo dei totali viene avviato per questa colonna e per le altre colonne per le quali è stata impostata la visualizzazione dei totali. Il tempo necessario per mostrare un totale dipende dalla dimensione del set di dati di cui si stanno genrando i totali.

- Dopo che il piè di pagina è visibile, selezionare **Mostra totale** nell'area per i piè di pagina nella parte inferiore della colonna per cui si desidera visualizzare un totale. Se non vi sono colonne configurate, il pulsante **Mostra totale** sarà disponibile per tutte le colonne numeriche. 

    Una volta configurata almeno una colonna per i totali, il pulsante **Mostra totale** sarà disponibile solo al passaggio del mouse o quando è l'elemento attivo. L'azione di selezione **Mostra totale** salva solo la preferenza per la visualizzazione di un totale in questa colonna, in modo che la preferenza venga applicata durante le future visite alla pagina. Nel piè di pagina, questo stato è indicato da un trattino che appare nella colonna. (In alternativa, se il set di dati è abbastanza piccolo, viene immediatamente mostrato un totale.)

Se si commette un errore e non si desidera più vedere un totale in una determinata colonna, fare clic con il pulsante destro sulla colonna e scegliere **Nascondi totale** oppure selezionare il pulsante **Nascondi totale** nel piè di pagina in quella colonna. Questa preferenza verrà salvata anche per visite future alla pagina. 

### <a name="calculating-totals"></a>Calcolo totali in corso
Quando si arriva a una pagina con il piè di pagina visibile e le colonne sono già configurate per i totali, questi possono o meno essere visualizzati nel piè di pagina. Il comportamento dipende dalla dimensione del set di dati nella pagina. Se il set di dati è sufficientemente piccolo, i totali verranno visualizzati automaticamente, insieme al numero di righe nel set di dati. Se sono presenti trattini nel piè di pagina sotto le colonne configurate per i totali, il set di dati è troppo grande per consentire al sistema di mostrare immediatamente i totali e per calcolare i totali è necessaria un'azione esplicita. A questo proposito, fare clic sul pulsante **Calcola** nel piè di pagina o fare clic con il pulsante destro del mouse su una colonna per la quale si desidera un totale e selezionare **Totale in questa colonna**.

Se il calcolo richiede troppo tempo per essere completato, è possibile annullare l'operazione selezionando il pulsante **Annulla**. A volte, il set di dati sarà troppo grande per calcolare i totali (un limite imposto dalla propria organizzazione) e verrà invece richiesto di filtrare ulteriormente i dati. 

> [!NOTE]
> Le amministrazioni di sistema possono modificare il limite per il numero di record disponibili per il calcolo dei totali regolando il parametro **Numero massimo di record locali per ogni griglia** nella pagina **Opzioni di prestazione del cliente**. Il valore predefinito è 25.000 record. Gli amministratori devono prestare attenzione quando regolano questo valore perché un valore troppo grande può esaurire la memoria disponibile sul computer dell'utente. La raccomandazione è di non superare i 50.000 record.   

I totali verranno aggiornati automaticamente a mano a mano che si aggiornano, eliminano o si creano righe nel set di dati.

## <a name="typing-ahead-of-the-system"></a>Digitare prima del sistema
In molti scenari aziendali, la capacità di inserire rapidamente i dati nel sistema è molto importante. Prima dell'introduzione del nuovo controllo della griglia, gli utenti potevano modificare i dati solo nella riga corrente. Prima di poter creare una nuova riga o passare a una riga diversa, erano costretti ad attendere che il sistema convalidasse correttamente eventuali modifiche. Nel tentativo di ridurre il tempo di attesa degli utenti per il completamento di queste convalide e di migliorare la produttività degli stessi, la nuova griglia regola tali convalide in modo che siano asincrone. Pertanto, l'utente può spostarsi su altre righe per apportare modifiche mentre sono in corso le convalide delle righe precedenti. 

Per supportare questo nuovo comportamento, una nuova colonna per lo stato della riga è stata aggiunta a destra della colonna di selezione della riga quando la griglia è in modalità di modifica. Questa colonna indica uno dei seguenti stati:

- **Vuoto** - Nessuna immagine di stato indica che la riga è stata salvata correttamente dal sistema.
- **Elaborazione in sospeso** - Questo stato indica che le modifiche nella riga non sono state ancora salvate dal server ma si trovano in una coda di modifiche che devono essere elaborate. Prima di agire all'esterno della griglia, è necessario attendere l'elaborazione di tutte le modifiche in sospeso. Inoltre, il testo in queste righe è in corsivo per indicare lo stato non salvato delle righe. 
- **Stato non valido** - Questo stato indica che durante l'elaborazione della riga è stato attivato un avviso o un messaggio e potrebbe aver impedito al sistema di salvare le modifiche in quella riga. Nella griglia precedente, se l'operazione di salvataggio non riusciva, si era costretti a tornare alla riga per risolvere immediatamente il problema. Nella nuova griglia, viene notificato che si è verificato un problema di convalida, ma è possibile decidere quando si desidera risolvere gli eventuali problemi nella riga. Quando si è pronti per risolvere un problema, è possibile spostare manualmente lo stato attivo sulla riga. In alternativa, è possibile selezionare l'azione **Risolvi questo problema**. Questa azione riporta immediatamente lo stato attivo sulla riga che presenta il problema e consente di apportare modifiche all'interno o all'esterno della griglia. Si noti che l'elaborazione delle successive righe in sospeso viene interrotta fino alla risoluzione di questo avviso di convalida. 
- **In sospeso** - Questo stato indica che l'elaborazione da parte del server è in sospeso perché la convalida della riga ha attivato una finestra di dialogo pop-up che richiede l'input dell'utente. Poiché l'utente potrebbe inserire i dati in un'altra riga, la finestra di dialogo pop-up non viene immediatamente presentata all'utente. Verrà invece visualizzata quando l'utente sceglie di riprendere l'elaborazione. Questo stato è accompagnato da una notifica che informa l'utente della situazione. La notifica include l'azione **Riprendere l'elaborazione** che attiverà la finestra di dialogo pop-up.

Quando gli utenti inseriscono dei dati prima della posizione in cui il server sta elaborando, possono prevedere qualche degrado nell'esperienza di immissione dei dati, come la mancanza di ricerche, la convalida a livello di controllo e l'inserimento di valori predefiniti. Gli utenti che necessitano di un elenco a discesa per trovare un valore sono invitati ad attendere che il server raggiunga la riga corrente. La convalida a livello di controllo e l'inserimento dei valori predefiniti si verificheranno quando il server elabora quella riga.

### <a name="pasting-from-excel"></a>Incollare da Excel
Gli utenti sono sempre stati in grado di esportare i dati dalle griglie delle app per finanza e operazioni in Microsoft Excel in Excel utilizzando il meccanismo **Esporta in Excel**. Tuttavia, la possibilità di inserire i dati prima del sistema, consente alla nuova griglia di supportare la copia delle tabelle da Excel e incollarle direttamente nelle griglie nelle app per finanza e operazioni. La cella della griglia da cui viene avviata l'operazione "incolla" determina da dove inizia l'operazione incolla della tabella copiata. Il contenuto della griglia viene sovrascritto dal contenuto della tabella copiata, tranne in due casi:

- Se il numero di colonne nella tabella copiata supera il numero di colonne che rimangono nella griglia, a partire dalla posizione incolla, l'utente viene avvisato che le colonne extra sono state ignorate. 
- Se il numero di righe nella tabella copiata supera il numero di righe nella griglia, a partire dalla posizione incolla, le celle esistenti vengono sovrascritte dal contenuto incollato e tutte le righe aggiuntive dalla tabella copiata vengono inserite come nuove righe nella parte inferiore della griglia. 

## <a name="evaluating-math-expressions"></a>Valutare espressioni matematiche
Come booster di produttività, gli utenti possono inserire formule matematiche nelle celle numeriche di una griglia. Non devono eseguire il calcolo in un'app esterna al sistema. Ad esempio, se si immette **=15\*4** e quindi si preme il tasto **TAB** per uscire dal campo, il sistema valuterà l'espressione e salverà un valore di **60** per il campo.

Per fare in modo che il sistema riconosca un valore come espressione, iniziare il valore con un segno uguale (**=**). Per ulteriori informazioni sugli operatori supportati e sulla sintassi, vedere [Simboli matematici supportati](http://bugwheels94.github.io/math-expression-evaluator/#supported-maths-symbols).

## <a name="grouping-tabular-data"></a>Raggruppamento di dati tabulari
Gli utenti aziendali devono spesso eseguire analisi ad hoc dei dati. Sebbene questa operazione possa essere eseguita esportando dati in Microsoft Excel e usando tabelle pivot, la funzionalità **Raggruppamento in griglie** che dipende dalla nuova funzionalità controllo griglia consente agli utenti di organizzare i dati tabulari in modi interessanti nelle app per finanza e operazioni. Poiché questa funzionalità estende la funzionalità **Totali**, **Raggruppamento** consente di ottenere informazioni dettagliate significative sui dati fornendo subtotali a livello di gruppo.

Per utilizzare questa funzionalità, fare clic con il pulsante destro del mouse sulla colonna in base alla quale eseguire il raggruppamento e selezionare **Raggruppa in base a questa colonna**. Questa azione ordina i dati in base alla colonna selezionata, aggiunge una nuova colonna **Raggruppa per** all'inizio della griglia e inserisce "righe di intestazione" all'inizio di ciascun gruppo. Queste righe di intestazione forniscono le seguenti informazioni su ciascun gruppo:

- Valore dei dati per il gruppo 
- Nome della colonna (queste informazioni saranno particolarmente utili in caso di più livelli di raggruppamento)
- Numero di righe di dati in questo gruppo
- Subtotali per qualsiasi colonna configurata per mostrare i totali

Con la funzionalità [Visualizzazioni salvate](saved-views.md) abilitata, questo raggruppamento può essere salvato mediante personalizzazione come parte di una visualizzazione per un accesso rapido alla successiva visita della pagina.

### <a name="multiple-levels-of-grouping"></a>Più livelli di raggruppamento
Dopo aver raggruppato i dati in una singola colonna, puoi raggruppare i dati in una colonna diversa selezionando **Raggruppa in base a questa colonna** sulla colonna desiderata. Questo processo può essere ripetuto fino a quando non si ottengono 5 livelli di raggruppamento nidificati, ovvero la profondità massima supportata. A questo punto, non sarà più possibile raggruppare per colonne aggiuntive.

In qualsiasi momento, puoi rimuovere il raggruppamento su qualsiasi colonna facendo clic con il pulsante destro del mouse su quella colonna e selezionando **Separa**. È possibile anche rimuovere il raggruppamento da tutte le colonne selezionando **Opzioni griglia** e poi **Separa tutto**.

### <a name="sorting-grouped-data"></a>Ordinamento dei dati raggruppati
Dopo aver raggruppato i dati in base a una o più colonne, puoi modificare la direzione di ordinamento per qualsiasi colonna di raggruppamento tramite l'intestazione di colonna corrispondente. 

Il comportamento dell'ordinamento su colonne non raggruppate dipende dalla versione del prodotto:

- Nella versione 10.0.24 e precedenti, se si ordina su una colonna non raggruppata, il raggruppamento viene rimosso da tutte le colonne e i dati vengono ordinati sulla colonna selezionata. 
- Nella versione 10.0.25 e successive, se si ordina su una colonna non raggruppata, il raggruppamento rimane intatto e i dati vengono ordinati all'interno di ogni gruppo, in base alla colonna selezionata.

### <a name="expanding-and-collapsing-groups"></a>Espansione e compressione di gruppi
Il raggruppamento iniziale di dati avrà tutti i gruppi espansi. È possibile creare visualizzazioni riepilogative dei dati comprimendo i singoli gruppi oppure è possibile utilizzare l'espansione e la compressione del gruppo per facilitare lo spostamento tra i dati. Per espandere o comprimere un gruppo, selezionare il pulsante con la freccia (>) nella riga dell'intestazione del gruppo corrispondente. Tenere presente che lo stato di espansione/compressione dei singoli gruppi **non** è salvato nella personalizzazione.

### <a name="selecting-and-unselecting-rows-at-the-group-level"></a>Selezionare e deselezionare le righe a livello di gruppo
Come è possibile selezionare (o deselezionare) tutte le righe nella griglia selezionando la casella di controllo nella parte superiore della prima colonna nella griglia, è possibile anche selezionare rapidamente (o deselezionare) tutte le righe in un gruppo selezionando la casella di controllo nella riga dell'intestazione del gruppo corrispondente. La casella di controllo nella riga di intestazione del gruppo rifletterà sempre lo stato di selezione corrente delle righe di quel gruppo, indipendentemente dal fatto che tutte le righe siano selezionate, non sia selezionata alcuna riga o solo alcune righe siano selezionate.

### <a name="hiding-column-names"></a>Nascondere i nomi delle colonne
Quando si raggruppano i dati, il comportamento predefinito è mostrare il nome della colonna nella riga dell'intestazione del gruppo. Puoi scegliere di nascondere il nome della colonna nelle righe di intestazione del gruppo selezionando **Opzioni griglia** > **Nascondi nome della colonna del gruppo**.

### <a name="grouping-on-date-and-time-columns"></a>Raggruppamento in colonne di data e ora
A partire dalla versione 10.0.24, per i campi Data o DateTime, l'opzione è stata aggiunta al gruppo per anno, mese o giorno. Il "valore" del gruppo nella riga di intestazione corrispondente corrisponde al formato di quel campo. Inoltre, per i campi DateTime e Ora, sarai in grado di raggruppare per ora, minuto o secondo. 

## <a name="freezing-columns"></a>Blocco delle colonne
Alcune colonne in una griglia potrebbero essere abbastanza importanti per il contesto da non desiderare che scorrano fuori dalla visualizzazione. Invece, è consigliabile fare in modo che i valori in tali colonne siano sempre visibili. La funzionalità **Congelamento delle colonne nelle griglie** fornisce questa flessibilità agli utenti. 

Per bloccare una colonna, fare clic con il pulsante destro del mouse nell'intestazione della colonna, quindi selezionare **Blocca colonna**. La prima volta che si completa questo passaggio, la colonna selezionata diventa la prima colonna e non scorrerà più fuori dalla visualizzazione. Qualsiasi colonna successiva che blocchi verrà aggiunta a destra dell'ultima colonna bloccata. È possibile utilizzare la funzionalità di spostamento standard per riordinare le colonne bloccate in base alle proprie esigenze. Tuttavia, le colonne bloccate non possono essere spostate in modo che vengano visualizzate nel set di colonne non congelate. Allo stesso modo, le colonne non bloccate non possono essere spostate in modo che vengano visualizzate nel set di colonne bloccate.

Per sbloccare una colonna, fare clic con il pulsante destro del mouse nell'intestazione della colonna bloccata, quindi selezionare **Sblocca colonna**. 

Notare che la selezione della riga e le colonne dello stato della riga nella nuova griglia sono sempre bloccate come le prime due colonne. Pertanto, quando queste colonne sono incluse in una griglia, saranno sempre visibili all'utente, indipendentemente dalla posizione di scorrimento orizzontale nella griglia. Queste due colonne non possono essere riordinate.

## <a name="autofit-column-width"></a>Adatta automaticamente larghezza colonna
Come per Excel, gli utenti possono forzare automaticamente il ridimensionamento di una colonna in base al contenuto attualmente mostrato in quella colonna. Per fare ciò, fai doppio clic sui quadratini di ridimensionamento nella colonna o mettendo lo stato attivo nell'intestazione della colonna e premendo **A** (per adattamento automatico). Questa funzionalità è disponibile a partire dalla versione 10.0.23.

## <a name="frequently-asked-questions"></a>Domande frequenti
### <a name="how-do-i-enable-the-new-grid-control-in-my-environment"></a>Come si abilita il nuovo controllo della griglia nell'ambiente? 

La funzionalità **Nuovo controllo griglia** è disponibile direttamente in Gestione funzionalità in qualsiasi ambiente. Dopo aver abilitato la funzionalità in Gestione funzionalità, tutte le sessioni utente successive utilizzeranno il nuovo controllo della griglia. 

Questa funzionalità è abilitata per impostazione predefinita a partire dalla versione 10.0.21 ed è destinata a diventare obbligatoria in ottobre 2022.  

## <a name="developer-opting-out-individual-pages-from-using-the-new-grid"></a>[Sviluppatore] Rifiuto di singole pagine dall'uso della nuova griglia 
Se l'organizzazione rileva una pagina che presenta alcuni problemi durante l'utilizzo della nuova griglia, è disponibile un'API per consentire a un singolo modulo di utilizzare il controllo della griglia legacy, consentendo comunque al resto del sistema di utilizzare il nuovo controllo della griglia. Per rifiutare esplicitamente una singola pagina della nuova griglia, aggiungere il seguente post di chiamata `super()` nel metodo `run()` del modulo.

```this.forceLegacyGrid();```

Questa API verrà rispettata fino a quando il nuovo controllo della griglia diventa obbligatorio. Tale modifica è attualmente prevista per ottobre 2022. Se qualsiasi problema richiede l'utilizzo di questa API, segnalalo a Microsoft.

### <a name="forcing-a-page-to-use-the-new-grid-after-previously-opting-out-the-grid"></a>Forzare una pagina a utilizzare la nuova griglia dopo aver precedentemente disattivato la griglia
Se hai disattivato l'utilizzo della nuova griglia per una singola pagina, potresti voler riattivare in seguito la nuova griglia dopo che i problemi sottostanti sono stati risolti. Per fare ciò, devi semplicemente rimuovere la chiamata a `forceLegacyGrid()`. La modifica non avrà effetto fino a quando non si verifica una delle seguenti condizioni:

- **Ridistribuzione dell'ambiente**: quando un ambiente viene aggiornato e ridistribuito, la tabella che archivia le pagine che sono state escluse dalla nuova griglia (FormControlReactGridState) viene cancellata automaticamente.
- **Svuotamento manuale della tabella**: per gli scenari di sviluppo, sarà necessario utilizzare SQL per cancellare la tabella FormControlReactGridState e quindi riavviare Microsoft Dynamics AX Application Object Server (AOS). Questa combinazione di azioni ripristinerà la memorizzazione nella cache delle pagine che sono state escluse dalla nuova griglia.

## <a name="developer-opting-individual-grids-out-of-the-typing-ahead-of-the-system-capability"></a>[Sviluppatore] Eliminazione delle singole griglie dalla digitazione prima della capacità del sistema
Sono apparsi alcuni scenari che non si prestano a funzionare bene con la funzionalità *Digitare prima del sistema* della griglia. (Ad esempio, un codice che viene attivato quando una riga viene convalidata provoca l'attivazione di una ricerca sull'origine dati e la ricerca può quindi danneggiare le modifiche non vincolate sulle righe esistenti.) Se l'organizzazione rileva uno scenario del genere, è disponibile un'API che consente a lo sviluppatore esclude una singola griglia dalla convalida di riga asincrona e ripristina il comportamento legacy.

Quando la convalida di riga asincrona è disabilitata in una griglia, gli utenti non possono creare una nuova riga o passare a una riga esistente diversa nella griglia mentre sono presenti problemi di convalida nella riga corrente. Come effetto collaterale di questa azione, le tabelle non possono essere incollate da Excel nelle griglie Finanza e operazioni.

Per rifiutare esplicitamente una singola griglia di una convalida di riga asincrona, aggiungere il seguente post di chiamata `super()` nel metodo `run()` del modulo.

```<gridControl>.allowPreemptiveClient(false);```

> [!NOTE]
> - Questa chiamata dovrebbe essere invocata solo in casi eccezionali e non dovrebbe essere la norma per tutte le griglie.
> - Non è consigliabile attivare questa API in fase di esecuzione dopo il caricamento del modulo.

## <a name="developer-size-to-available-width-columns"></a>[Sviluppatore] Colonne dalla dimensione alla larghezza disponibile
Se uno sviluppatore imposta la proprietà **WidthMode** su **SizeToAvailable** per le colonne all'interno della nuova griglia, tali colonne hanno inizialmente la stessa larghezza che avrebbero se la proprietà fosse impostata su **SizeToContent**. Tuttavia, si allungano per utilizzare qualsiasi larghezza extra disponibile all'interno della griglia. Se la proprietà è impostata su **SizeToAvailable** per più colonne, tutte queste colonne condividono qualsiasi larghezza extra disponibile all'interno della griglia. Tuttavia, se un utente ridimensiona manualmente una di queste colonne, la colonna diventa statica. Rimarrà a quella larghezza e non si allungherà più per occupare la larghezza della griglia disponibile in più.

## <a name="known-issues"></a>Problemi noti
Questa sezione mantiene un elenco di problemi noti per il nuovo controllo griglia.

### <a name="open-issues"></a>Problemi aperti
- Dopo aver abilitato la funzionalità **Nuovo controllo griglia**, alcune pagine continueranno a utilizzare il controllo griglia esistente. Questo avverrà nelle seguenti situazioni:
 
    - È presente un elenco di schede nella pagina che viene visualizzata in più colonne.
    - È presente un elenco di schede raggruppate sulla pagina.
    - Una colonna della griglia con un controllo estendibile non reattivo.

    Quando un utente incontra per la prima volta una di queste situazioni, verrà visualizzato un messaggio sull'aggiornamento della pagina. Una volta visualizzato questo messaggio, la pagina continuerà a utilizzare la griglia esistente per tutti gli utenti fino al prossimo aggiornamento della versione del prodotto. Una migliore gestione di questi scenari, in modo che la nuova griglia possa essere utilizzata, verrà presa in considerazione per un aggiornamento futuro.

- [KB 4582758] I record sono sfocati quando si modifica lo zoom da 100 a qualsiasi altra percentuale
- [KB 4592012] Errore client imprevisto in IE11 quando si incollano più righe da Excel

    Microsoft non sta cercando di risolvere questo problema


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
