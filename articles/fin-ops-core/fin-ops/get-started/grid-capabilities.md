---
title: Funzionalità del controllo griglia
description: Questo argomento descrive diverse potenti funzionalità del controllo griglia. La nuova funzionalità della griglia deve essere abilitata per avere accesso a queste funzionalità.
author: jasongre
manager: AnnBe
ms.date: 01/22/2021
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
ms.openlocfilehash: 3be09f6c469e90b153bff1d8a09b98f5a46b933a
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2021
ms.locfileid: "5570899"
---
# <a name="grid-capabilities"></a>Funzionalità di griglia

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Il nuovo controllo griglia offre una serie di funzionalità utili e potenti che possono essere utilizzate per migliorare la produttività degli utenti, creare viste più interessanti dei dati e ottenere informazioni dettagliate significative sui dati. In questo articolo vengono illustrate le seguenti funzionalità: 

-  Calcolo totali in corso
-  Digitare prima del sistema
-  Valutare espressioni matematiche 
-  Raggruppamento di dati tabulari (abilitato separatamente utilizzando la funzionalità **(Anteprima) Raggruppamento in griglie**)
-  Blocco delle colonne

## <a name="calculating-totals"></a>Calcolo totali in corso
Nelle app Finance and Operations, gli utenti hanno la possibilità di vedere i totali nella parte inferiore delle colonne numeriche nelle griglie. Questi totali sono visualizzati in una sezione a piè di pagina nella parte inferiore della griglia. 

### <a name="showing-the-grid-footer"></a>Visualizzare il piè di pagina della griglia
C'è un'area per i piè di pagina nella parte inferiore di ogni griglia tabulare nelle app Finance and Operations. Il piè di pagina può mostrare informazioni preziose correlate ai dati visualizzati nella griglia. Di seguito sono riportati alcuni esempi di queste informazioni:

- Il numero di righe selezionate nella tabella (quando è selezionato più di un record)
- I totali complessivi nella parte inferiore delle colonne numeriche configurate
- Il numero di righe nel set di dati 

Questo piè di pagina è nascosto per impostazione predefinita, ma può essere attivato. Per visualizzare il piè di pagina per una griglia, fare clic con il tasto destro del mouse sull'intestazione di una colonna nella griglia e selezionare l'opzione **Mostra piè di pagina**. Dopo aver attivato il piè di pagina per una griglia particolare, tale impostazione verrà memorizzata fino a quando l'utente non sceglierà di nasconderlo. Per nascondere il piè di pagina, fare clic con il pulsante destro del mouse su un'intestazione di colonna e selezionare **Nascondi piè di pagina**.  L'azione **Mostra piè di pagina/Nascondi piè di pagina** potrebbe essere spostata in una nuova posizione in un aggiornamento futuro. 

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

Se il calcolo richiede troppo tempo, è possibile annullare l'operazione selezionando il pulsante **Annulla**. A volte, tuttavia, il set di dati sarà troppo grande per calcolare i totali (un limite imposto dalla propria organizzazione) e verrà invece richiesto di filtrare ulteriormente i dati.

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
Gli utenti sono sempre stati in grado di esportare i dati dalle griglie nelle app Finance and Operations in Excel utilizzando il meccanismo **Esporta in Excel**. Tuttavia, la possibilità di inserire i dati prima del sistema, consente alla nuova griglia di supportare la copia delle tabelle da Excel e incollarle direttamente nelle griglie nelle app Finance and Operations. La cella della griglia da cui viene avviata l'operazione "incolla" determina da dove inizia l'operazione incolla della tabella copiata. Il contenuto della griglia viene sovrascritto dal contenuto della tabella copiata, tranne in due casi:

- Se il numero di colonne nella tabella copiata supera il numero di colonne che rimangono nella griglia, a partire dalla posizione incolla, l'utente viene avvisato che le colonne extra sono state ignorate. 
- Se il numero di righe nella tabella copiata supera il numero di righe nella griglia, a partire dalla posizione incolla, le celle esistenti vengono sovrascritte dal contenuto incollato e tutte le righe aggiuntive dalla tabella copiata vengono inserite come nuove righe nella parte inferiore della griglia. 

## <a name="evaluating-math-expressions"></a>Valutare espressioni matematiche
Come booster di produttività, gli utenti possono inserire formule matematiche nelle celle numeriche di una griglia. Non devono eseguire il calcolo in un'app esterna al sistema. Ad esempio, se si immette **=15\*4** e quindi si preme il tasto **TAB** per uscire dal campo, il sistema valuterà l'espressione e salverà un valore di **60** per il campo.

Per fare in modo che il sistema riconosca un valore come espressione, iniziare il valore con un segno uguale (**=**). Per ulteriori informazioni sugli operatori supportati e sulla sintassi, vedere [Simboli matematici supportati](http://bugwheels94.github.io/math-expression-evaluator/#supported-maths-symbols).

## <a name="grouping-tabular-data"></a>Raggruppamento di dati tabulari
Gli utenti aziendali devono spesso eseguire analisi ad hoc dei dati. Sebbene questa operazione possa essere eseguita esportando dati in Microsoft Excel e usando tabelle pivot, la funzionalità **Raggruppamento in griglie** che generalmente è disponibile nella versione 10.0.16/Platform update 40 e dipende dalla nuova funzionalità controllo griglia consente agli utenti di organizzare i dati tabulari in modi interessanti nelle app Finance and Operations. Poiché questa funzionalità estende la funzionalità **Totali**, **Raggruppamento** consente di ottenere informazioni dettagliate significative sui dati fornendo subtotali a livello di gruppo.

Per utilizzare questa funzionalità, fare clic con il pulsante destro del mouse sulla colonna in base alla quale eseguire il raggruppamento e selezionare **Raggruppa in base a questa colonna**. Questa azione ordina i dati in base alla colonna selezionata, aggiunge una nuova colonna **Raggruppa per** all'inizio della griglia e inserisce "righe di intestazione" all'inizio di ciascun gruppo. Queste righe di intestazione forniscono le seguenti informazioni su ciascun gruppo: 
-  Valore dei dati per il gruppo 
-  Nome della colonna (queste informazioni saranno particolarmente utili in caso di più livelli di raggruppamento)  
-  Numero di righe di dati in questo gruppo
-  Subtotali per qualsiasi colonna configurata per mostrare i totali

Con la funzionalità [Visualizzazioni salvate](saved-views.md) abilitata, questo raggruppamento può essere salvato mediante personalizzazione come parte di una visualizzazione per un accesso rapido alla successiva visita della pagina.  

### <a name="multiple-levels-of-grouping"></a>Più livelli di raggruppamento
Dopo aver raggruppato i dati in una singola colonna, puoi raggruppare i dati in una colonna diversa selezionando **Raggruppa in base a questa colonna** sulla colonna desiderata. Questo processo può essere ripetuto fino a quando non si ottengono 5 livelli di raggruppamento nidificati, ovvero la profondità massima supportata. A questo punto, non sarà più possibile raggruppare per colonne aggiuntive.  

In qualsiasi momento, puoi rimuovere il raggruppamento su qualsiasi colonna facendo clic con il pulsante destro del mouse su quella colonna e selezionando **Separa**. È possibile anche rimuovere il raggruppamento da tutte le colonne selezionando **Opzioni griglia** e poi **Separa tutto**.   

Tenere presente che, prima della versione 10.0.16/Platform update 40, è supportato solo un livello di raggruppamento. In queste versioni, se i dati sono raggruppati e si seleziona **Raggruppa in base a questa colonna** per una colonna diversa, il raggruppamento originale viene sostituito.  


### <a name="expanding-and-collapsing-groups"></a>Espansione e compressione di gruppi
Il raggruppamento iniziale di dati avrà tutti i gruppi espansi. È possibile creare visualizzazioni riepilogative dei dati comprimendo i singoli gruppi oppure è possibile utilizzare l'espansione e la compressione del gruppo per facilitare lo spostamento tra i dati. Per espandere o comprimere un gruppo, selezionare il pulsante con la freccia (>) nella riga dell'intestazione del gruppo corrispondente. Tenere presente che lo stato di espansione/compressione dei singoli gruppi **non** è salvato nella personalizzazione.

### <a name="selecting-and-unselecting-rows-at-the-group-level"></a>Selezionare e deselezionare le righe a livello di gruppo
Come è possibile selezionare (o deselezionare) tutte le righe nella griglia selezionando la casella di controllo nella parte superiore della prima colonna nella griglia, è possibile anche selezionare rapidamente (o deselezionare) tutte le righe in un gruppo selezionando la casella di controllo nella riga dell'intestazione del gruppo corrispondente. La casella di controllo nella riga di intestazione del gruppo rifletterà sempre lo stato di selezione corrente delle righe di quel gruppo, indipendentemente dal fatto che tutte le righe siano selezionate, non sia selezionata alcuna riga o solo alcune righe siano selezionate.

### <a name="hiding-column-names"></a>Nascondere i nomi delle colonne
Quando si raggruppano i dati, il comportamento predefinito è mostrare il nome della colonna nella riga dell'intestazione del gruppo. A partire dalla versione 10.0.14/aggiornamento della piattaforma 38, è possibile scegliere di nascondere il nome della colonna nelle righe di intestazione del gruppo selezionando **Opzioni griglia** > **Nascondi nome della colonna del gruppo**.

## <a name="freezing-columns"></a>Blocco delle colonne
Alcune colonne in una griglia potrebbero essere abbastanza importanti per il contesto da non desiderare che scorrano fuori dalla visualizzazione. Invece, è consigliabile fare in modo che i valori in tali colonne siano sempre visibili. Nella versione 10.0.17, la funzionalità **Blocca colonne nella griglia** fornisce questa flessibilità agli utenti. 

Per bloccare una colonna, fare clic con il pulsante destro del mouse nell'intestazione della colonna, quindi selezionare **Blocca colonna**. La prima volta che si completa questo passaggio, la colonna selezionata diventa la prima colonna e non scorrerà più fuori dalla visualizzazione. Qualsiasi colonna successiva che blocchi verrà aggiunta a destra dell'ultima colonna bloccata. È possibile utilizzare la funzionalità di spostamento standard per riordinare le colonne bloccate in base alle proprie esigenze. Tuttavia, le colonne bloccate non possono essere spostate in modo che vengano visualizzate nel set di colonne non congelate. Allo stesso modo, le colonne non bloccate non possono essere spostate in modo che vengano visualizzate nel set di colonne bloccate.

Per sbloccare una colonna, fare clic con il pulsante destro del mouse nell'intestazione della colonna bloccata, quindi selezionare **Sblocca colonna**. 

Notare che la selezione della riga e le colonne dello stato della riga nella nuova griglia sono sempre bloccate come le prime due colonne. Pertanto, quando queste colonne sono incluse in una griglia, saranno sempre visibili all'utente, indipendentemente dalla posizione di scorrimento orizzontale nella griglia. Queste due colonne non possono essere riordinate.

## <a name="frequently-asked-questions"></a>Domande frequenti
### <a name="how-do-i-enable-the-new-grid-control-in-my-environment"></a>Come si abilita il nuovo controllo della griglia nell'ambiente? 

**10.0.9 / Platform update 33 e successive**

La funzionalità **Nuovo controllo griglia** è disponibile direttamente in Gestione funzionalità in qualsiasi ambiente. Come altre funzionalità di anteprima pubblica, l'abilitazione di questa funzionalità in produzione è soggetta alle [condizioni d'uso supplementari](https://go.microsoft.com/fwlink/?linkid=2105274).  

**10.0.8 / Platform update 32 e 10.0.7 / Platform update 31**

La funzionalità **Nuovo controllo griglia** può essere abilitata in ambienti di Livello 1 (Sviluppo/Test) e Livello 2 (Sandbox) al fine di fornire ulteriori test e modifiche di progettazione seguendo i passaggi seguenti.

1.  **Abilitare l'anteprima**: Eseguire la seguente istruzione SQL: 

    `INSERT INTO SYSFLIGHTING (FLIGHTNAME, enabled, FLIGHTSERVICEID, PARTITION) VALUES('CLIReactGridEnableFeature', 1, 0, 5637144576);`

2. **Reimpostare IIS** per liberare la cache statica delle versioni di anteprima. 

3.  **Individuare la funzionalità**: spostarsi nell'area di lavoro **Gestione funzionalità**. Se **Nuovo controllo griglia** non appare nell'elenco delle funzioni, selezionare **Controlla aggiornamenti**.   

4.  **Abilitare la funzionalità**: Individuare la funzionalità **Nuovo controllo griglia** nell'elenco delle funzionalità e selezionare **Abilita ora** nel riquadro dei dettagli. Si noti che è richiesto un aggiornamento del browser. 

Tutte le sessioni utente successive verranno avviate con il nuovo controllo griglia abilitato.

## <a name="developer-opting-out-individual-pages-from-using-the-new-grid"></a>[Sviluppatore] Rifiuto di singole pagine dall'uso della nuova griglia 
Se l'organizzazione rileva una pagina che presenta alcuni problemi durante l'utilizzo della nuova griglia, è disponibile un'API a partire dalla versione 10.0.13/Platform update 37 per consentire a un singolo modulo di utilizzare il controllo della griglia legacy, consentendo comunque al resto del sistema di utilizzare il nuovo controllo della griglia. Per rifiutare esplicitamente una singola pagina della nuova griglia, aggiungere il seguente post di chiamata `super()` nel metodo `run()` del modulo.

 ```this.forceLegacyGrid();```

Questa API verrà rispettata fino alla versione di ottobre 2021 quando il nuovo controllo della griglia diventa obbligatorio. Se qualsiasi problema richiede l'utilizzo di questa API, segnalalo a Microsoft.

## <a name="developer-size-to-available-width-columns"></a>[Sviluppatore] Colonne dalla dimensione alla larghezza disponibile
Se uno sviluppatore imposta la proprietà **WidthMode** su **SizeToAvailable** per le colonne all'interno della nuova griglia, tali colonne hanno inizialmente la stessa larghezza che avrebbero se la proprietà fosse impostata su **SizeToContent**. Tuttavia, si allungano per utilizzare qualsiasi larghezza extra disponibile all'interno della griglia. Se la proprietà è impostata su **SizeToAvailable** per più colonne, tutte queste colonne condividono qualsiasi larghezza extra disponibile all'interno della griglia. Tuttavia, se un utente ridimensiona manualmente una di queste colonne, la colonna diventa statica. Rimarrà a quella larghezza e non si allungherà più per occupare la larghezza della griglia disponibile in più.  

## <a name="known-issues"></a>Problemi noti
Questa sezione mantiene un elenco di problemi noti per il nuovo controllo griglia.  

### <a name="open-issues"></a>Problemi aperti
-  Dopo aver abilitato la funzionalità **Nuovo controllo griglia**, alcune pagine continueranno a utilizzare il controllo griglia esistente. Questo avverrà nelle seguenti situazioni:  
    -  È presente un elenco di schede nella pagina che viene visualizzata in più colonne.
    -  È presente un elenco di schede raggruppate sulla pagina.
    -  Una colonna della griglia con un controllo estendibile non reattivo.

    Quando un utente incontra per la prima volta una di queste situazioni, verrà visualizzato un messaggio sull'aggiornamento della pagina. Una volta visualizzato questo messaggio, la pagina continuerà a utilizzare la griglia esistente per tutti gli utenti fino al prossimo aggiornamento della versione del prodotto. Una migliore gestione di questi scenari, in modo che la nuova griglia possa essere utilizzata, verrà presa in considerazione per un aggiornamento futuro.    
    
-  [KB 4582758] I record sono sfocati quando si modifica lo zoom da 100 a qualsiasi altra percentuale
-  [KB 4592012] Errore client imprevisto in IE11 quando si incollano più righe da Excel
    -  Microsoft non sta cercando di risolvere questo problema

### <a name="fixed-as-part-of-10016"></a>Cespiti come parte del 10.0.16

-  [KB 4598335] I controlli stringa su più righe non rispettano i relativi DisplayHeights negli elenchi/nelle schede 
-  [KB 4591891] Le righe della proposta di fattura scompaiono quando si deselezionano le righe
-  [KB 4592104] Impossibile modificare i record dopo aver fatto clic su "Risolvi problema" ed essere passati a una riga diversa senza risolvere il problema di convalida
-  [KB 4594449] Pulsanti "Mai" e "Cancella" mancanti nel selettore della data 
-  [KB 4594448] L'immissione dell'ora viene trattata in modo diverso con la nuova griglia
-  [KB 4600059] Errore client imprevisto con limitazione dei messaggi e-mail
-  [KB 4574584] Anteprima allegato di spesa non disponibile quando si passa con il mouse sull'icona della ricevuta

### <a name="fixed-as-part-of-10015"></a>Cespiti come parte del 10.0.15    

-  (Aggiornamento qualitativo) [KB 4594444] Errore client imprevisto con anteprima per il controllo delle voci segmentate
-  [KB 4582723] Le opzioni di visualizzazione non vengono mostrate se eseguite successivamente nel ciclo di vita del modulo
-  [KB 4591988] Problemi di utilizzo della tastiera per selezionare un valore da una ricerca ReferenceGroup
-  [KB 4588958] Il test Regression Suite Automation Tool (RSAT) ha esito negativo con errore: TypeError: impossibile leggere la proprietà "text" di undefined
-  [KB 4591970] L'errore client imprevisto durante l'operazione incolla da Excel è stato eseguito immediatamente dopo aver fatto clic nella griglia
-  [KB 4591904] Le modifiche ai dati non vengono salvate se dopo aver modificato un controllo l'utente ha immediatamente fatto clic e ha aperto la ricerca di un altro controllo
-  [KB 4584752] Errore client imprevisto nella pagina Proposte di fatturazione progetto
-  [KB 4584540] Impossibile lasciare la griglia dopo aver incollato una singola riga in una riga del giornale di registrazione
-  [KB 4591908] Quando crei una nuova riga, lo stato attivo rimane nella colonna in cui ti trovavi

### <a name="fixed-as-part-of-10014"></a>Cespiti come parte del 10.0.14

-  (Aggiornamento di qualità) [KB 4584752] Errore client imprevisto nella pagina Proposte di fatturazione progetto
-  (Aggiornamento di qualità) [KB 4583880] I test Regression Suite Automation Tool (RSAT) hanno esito negativo sull'azione OpenLookup con "Impossibile leggere la proprietà RowIndex di undefined"
-  [KB 4583847] Errore client imprevisto durante la navigazione tra le ricerche

### <a name="fixed-as-part-of-10013"></a>Cespiti come parte del 10.0.13

-  (Aggiornamento di qualità) [KB 4584752] Errore client imprevisto nella pagina Proposte di fatturazione progetto
-  (Aggiornamento di qualità) [KB 4583880] I test Regression Suite Automation Tool (RSAT) hanno esito negativo sull'azione OpenLookup con "Impossibile leggere la proprietà RowIndex di undefined"
-  (Aggiornamento di qualità) [KB 4583847] Errore client imprevisto durante la navigazione tra le ricerche 
-  (Aggiornamento di qualità) [Bug 471777] Impossibile selezionare i campi in una griglia per modificare o creare un'app per dispositivi mobili
-  [KB 4582727] La griglia si blocca dopo che l'utente riceve la finestra di dialogo per gli elementi con quantità multiple
-  [Bug 474851] I collegamenti ipertestuali nei controlli del gruppo di riferimento non funzionano 
-  [Bug 474848] Le anteprime avanzate con griglie non vengono visualizzate
-  [KB 4582726] La proprietà RotateSign non viene rispettata  
-  [Bug 470173] Le caselle di controllo nelle righe inattive si attivano e disattivano quando si fa clic sullo spazio bianco nella cella
-  [Bug 474848] Le anteprime avanzate con griglie non vengono visualizzate
-  [Bug 474851] I collegamenti ipertestuali nei controlli del gruppo di riferimento non funzionano 
-  [Bug 471777] Impossibile selezionare i campi in una griglia per modificare o creare un'app per dispositivi mobili
-  [KB 4569441] Problemi con il rendering di elenchi di schede a più colonne, descrizioni comandi sulle immagini e opzioni di visualizzazione in alcuni campi
-  [KB 4575279] Non tutte le righe contrassegnate vengono eliminate nel giornale di registrazione generale
-  [KB 4575233] Le opzioni di visualizzazione non vengono ripristinate dopo lo spostamento in un'altra riga
-  [Bug 477884] Le ricerche restituiscono un valore / record errato se è attivato un nuovo controllo della griglia
-  [KB 4571095] La registrazione della ricevuta del prodotto si verifica quando si preme accidentalmente INVIO (gestione corretta dell'azione predefinita di una pagina)
-  [KB 4575437] Le ricerche con controlli modificabili si chiudono inaspettatamente
-  [KB 4569418] Riga duplicata creata nel modulo di programmazione consegna
-  [KB 4575435] L'anteprima avanzata a volte persiste anche quando il puntatore del mouse non è vicino al campo
-  [KB 4575434] La ricerca non filtra quando il campo è stato modificato
-  [KB 4575430] I valori nei campi di password non sono mascherati nella griglia
-  [KB 4569438] Il messaggio "Elaborazione interrotta a causa di un problema di convalida" viene visualizzato dopo aver contrassegnato le righe durante la liquidazione delle transazioni dei fornitori
-  [KB 4569434] L'aggiornamento del modulo Persone giuridiche genera un numero inferiore di record
-  [KB 4575297] Lo stato attivo continua a spostarsi nel riquadro di registrazione attività durante la modifica e la tabulazione in una griglia
-  [KB 4566773] Transazioni di correzione non visualizzate come negative nella richiesta di informazioni su transazioni giustificativo 
-  [KB 4575288] Lo stato attivo viene ripristinato sulla riga attiva quando si seleziona il bordo tra le righe in un elenco semplice
-  [KB 4575287] Lo stato attivo non torna alla prima colonna quando si utilizza la freccia GIÙ per creare una nuova riga nei giornali di registrazione
-  [KB 4564819] Impossibile eliminare le righe in una fattura a testo libero (perché l'origine dati ChangeGroupMode = ImplicitInnerOuter)
-  [KB 4563317] Le descrizioni dei comandi/anteprime avanzate non vengono visualizzate per le immagini.

### <a name="fixed-as-part-of-10012"></a>Cespiti come parte del 10.0.12

- [KB 4558545] I controlli della tabella non aggiornano il contenuto degli elementi visualizzati.
- [KB 4558570] Gli elementi saranno visualizzati nella pagina anche dopo l'eliminazione del record.
- [KB 4558572] Lo stile associato al pannello Elenco **ExtendedStyle** non verrà applicato.
- [KB 4558573] Gli errori di convalida non possono essere corretti quando la modifica richiesta è esterna alla griglia.
- [KB 4558584] I numeri negativi non verranno visualizzati correttamente.
- [KB 4560726] Si verifica un "errore client imprevisto" dopo lo scambio tra gli elenchi mediante un controllo Visualizza elenco.
- [KB 4562141] Gli indici di griglia vengono disattivati dopo l'aggiunta di un nuovo record.
- [KB 4562151] Le opzioni della registrazione attività **Convalida** e **Copia** non sono disponibili per i controlli di data/numero. 
- [KB 4562153] Le caselle di controllo di selezione multipla non sono visibili nelle griglie elenco/scheda.
- [KB 4562646] A volte non è possibile fare clic al di fuori della griglia dopo aver selezionato più righe nella griglia.
- [KB 4562647] Lo stato attivo viene ripristinato sul primo controllo nella finestra di dialogo **Pubblica** dopo l'aggiunta di una nuova riga nella griglia dei ruoli di sicurezza.
- [KB 4563310] L'anteprima avanzata non viene chiusa dopo la modifica di una riga.
- [KB 4563313] Si verifica un "errore client imprevisto" in Internet Explorer quando un valore è selezionato in una ricerca.
- [KB 4564557] Le ricerche e i menu a discesa non si aprono in Internet Explorer
- [KB 4563324] La navigazione non funziona dopo l'apertura dell'area di lavoro **Gestione dipendente**.

### <a name="fixed-as-part-of-10011"></a>Cespiti come parte del 10.0.11

- [Problema 432458] Le righe vuote o duplicate sono mostrate all'inizio di alcune raccolte secondarie.
- [KB 4549711] Le righe in una proposta di pagamento non possono essere rimosse correttamente dopo l'attivazione del nuovo controllo griglia.
- [KB 4558374] Non è possibile creare record che richiedono una finestra di dialogo del selettore polimorfico.
- [KB 4558375] Il testo della guida non viene visualizzato nelle colonne della nuova griglia.
- [KB 4558376] Le griglie del pannello elenco non vengono visualizzate all'altezza corretta in Internet Explorer.
- [KB 4558377] Le colonne della casella combinata con larghezza **SizeToAvailable** non vengono visualizzate in alcune pagine.
- [KB 4558378] Il drill-through a volte apre il record errato.
- [KB 4558379] Si verifica un errore quando vengono aperte le ricerche in cui **ReplaceOnLookup**=**No**.
- [KB 4558380] Lo spazio disponibile nella griglia non viene riempito immediatamente dopo la compressione di una parte della pagina.
- [KB 4558381] I numeri negativi non verranno visualizzati correttamente / Gli utenti potrebbero bloccarsi dopo che si sono verificati problemi di convalida.
- [KB 4558382] Si verificano errori del client imprevisti.
- [KB 4558383] I controlli all'esterno della griglia non sono aggiornati dopo l'eliminazione dell'ultimo record.
- [KB 4558587] I gruppi di riferimento con caselle combinate per i campi di sostituzione non mostrano i valori.
- [KB 4562143] I campi non verranno aggiornati dopo una modifica alla riga / l'elaborazione della griglia si bloccherà dopo l'eliminazione della riga.
- [KB 4562645] Si verifica un'eccezione quando viene aperta una ricerca durante l'esecuzione dei test Regression Suite Automation Tool (RSAT).

### <a name="fixed-as-part-of-10010"></a>Cespiti come parte del 10.0.10

- [Problema 414301] Alcuni dati delle righe precedenti scompaiono quando vengono create nuove righe.
- [Bug 417044] Non esiste un messaggio di griglia vuoto per le griglie in stile elenco.
- [KB 4539058] Alcune griglie (in genere nelle schede dettaglio) a volte non vengono visualizzate (ma verranno visualizzate se si esegue lo zoom indietro).
- [KB 4549734] Le righe attive non vengono trattate come contrassegnate se la colonna di marcatura è nascosta.
- [KB 4549796] I valori non possono essere modificati in una griglia quando è in modalità visualizzazione.
- [KB 4558367] La selezione del testo non è coerente quando le righe vengono modificate.
- [KB 4558368] La selezione multipla tramite tastiera è consentita in scenari a selezione singola.
- [KB 4558369] Le immagini di stato scompaiono nella griglia gerarchica.
- [KB 4558370] Scorrendo, una nuova riga non verrà visualizzata.
- [KB 4558372] La nuova griglia si blocca nella modalità di elaborazione se il numero di colonne nel contenuto incollato supera il numero di colonne rimanenti nella griglia.
- [KB 4562631] L'ora non è formattata correttamente.

### <a name="quality-update-for-1009platform-update-33"></a>Aggiornamento di qualità per 10.0.9/Aggiornamento della piattaforma 33

- [KB 4550367] L'ora non è formattata correttamente.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]