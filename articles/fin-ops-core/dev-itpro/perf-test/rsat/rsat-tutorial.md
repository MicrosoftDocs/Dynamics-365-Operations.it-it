---
title: Esercitazione su Regression Suite Automation Tool
description: In questo articolo viene illustrato come utilizzare lo strumento Regression Suite Automation Tool (RSAT). Vengono descritte varie funzionalità e forniti esempi che utilizzano lo script avanzato.
author: FrankDahl
ms.date: 09/23/2021
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: fdahl
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: AX 7.0.0, Operations
ms.openlocfilehash: a270398ddebef0f47a2c31b0ffb022e3df6489c7
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9277406"
---
# <a name="regression-suite-automation-tool-tutorial"></a>Esercitazione Regression Suite Automation Tool

[!include [banner](../../includes/banner.md)]

> [!NOTE]
> Utilizzare gli strumenti del browser Internet per scaricare e salvare questa pagina in formato PDF.

Questa esercitazione descrive alcune delle funzionalità avanzate di Regression Suite Automation Tool (RSAT), include un'assegnazione demo e fornisce suggerimenti chiave e la strategia da adottare.

## <a name="notable-features-of-rsat-and-task-recorder"></a>Caratteristiche importanti di RSAT e Registrazione attività

### <a name="validate-a-field-value"></a>Convalidare un valore di campo

RSAT consente di includere passaggi di convalida nel caso di test per convalidare i valori previsti. Per informazioni su questa funzione, consultare l'articolo [Convalidare i valori previsti](rsat-validate-expected.md).

Nell'esempio seguente viene illustrato come utilizzare questa funzionalità per verificare se le scorte disponibili sono maggiori di 0 (zero).

1. Nei dati demo della società **USMF**, creare una registrazione attività che includa i seguenti passaggi:

    1. Fare clic su **Gestione informazioni sul prodotto \> Prodotti \> Prodotti rilasciati**.
    2. Utilizzare il filtro rapido per trovare i record. Ad esempio, filtrare in base al valore **1000** nel campo **Numero articolo**.
    3. Selezionare **Scorte disponibili**.
    4. Utilizzare il filtro rapido per trovare i record. Ad esempio, filtrare in base al valore **1** nel campo **Sito**.
    5. Nell'elenco contrassegnare la riga selezionata.
    6. Verificare che il valore del campo **Totale disponibile** sia **411,0000000000000000**.

2. Salva il file di registrazione attività come **registrazione dello sviluppatore** e collegalo al caso di test in Azure DevOps.
3. Aggiungere il test case al piano di test e caricare il test case in RSAT.
4. Aprire il file dei parametri di Excel e passare alla scheda **TestCaseSteps**.
5. Per convalidare se le scorte disponibili saranno sempre superiori a **0**, andare al passaggio **Convalida totale disponibile** e cambiare il valore da **411** a **0**. Modificare il valore del campo **Operatore** da un segno di uguale (**=**) a un segno di maggiore di (**\>**).
6. Salvare e chiudere il file di parametri di Excel.
7. Selezionare **Carica** per salvare le modifiche apportate al file di parametri di Excel in Azure DevOps.

A questo punto, se il valore del campo **Totale disponibile** per l'articolo specificato nelle scorte è maggiore di 0 (zero), i test avranno esito positivo, indipendentemente dal valore delle scorte disponibili effettivo.

### <a name="saved-variables-and-chaining-of-test-cases"></a>Variabili salvate e concatenamento di casi di test

Una delle funzionalità importanti di RSAT è il concatenamento dei test case, ovvero la capacità di un test di passare variabili ad altri test. Per ulteriori informazioni, consultare l'articolo [Copiare le variabili in casi di test concatenati](rsat-chain-test-cases.md).

### <a name="derived-test-case"></a>Test case derivato

RSAT consente di utilizzare la stessa registrazione di attività con più casi di test, permettendo l'esecuzione di un'attività con diverse configurazioni di dati. Vedere l'articolo [Casi di test derivati](rsat-derived-test-cases.md) per ulteriori informazioni.

### <a name="validate-notifications-and-messages"></a>Convalidare notifiche e messaggi

Questa funzionalità può essere utilizzata per convalidare un'azione avvenuta. Ad esempio, quando un ordine di produzione viene creato, valutato e quindi avviato, l'app visualizza un messaggio "Produzione - Avvio" per notificare all'utente che l'ordine di produzione è stato avviato.

![Produzione - Avvio notifica.](./media/use_rsa_tool_05.png)

È possibile convalidare questo messaggio mediante RSAT digitando il testo del messaggio nella scheda **MessageValidation** del file di parametri di Excel per la registrazione appropriata.

![Scheda Convalida messaggio.](./media/use_rsa_tool_06.png)

Dopo l'esecuzione del test case, il messaggio nel file di parametri di Excel viene confrontato al messaggio visualizzato. Se i messaggi non corrispondono, il test case non avrà esito positivo.

> [!NOTE]
> È possibile immettere più di un messaggio nella scheda **Convalida messaggio** del file di parametri di Excel. I messaggi possono anche essere messaggi di errore o di avviso anziché messaggi informativi.

### <a name="snapshot"></a>Snapshot

Questa funzionalità consente di acquisire schermate dei passaggi eseguiti durante la registrazione attività. È utile per scopi di controllo o debug.

- Per utilizzare questa funzionalità durante l'esecuzione di RSAT con l'interfaccia utente, aprire il file **Microsoft.Dynamics.RegressionSuite.WindowsApp.exe.config** nella cartella di installazione di RSAT (ad esempio **C:\\Programmi (x86)\\Regression Suite Automation Tool**) e modificare il valore dell'elemento seguente da **false** a **true**.

    ```xml
    <add key="VerboseSnapshotsEnabled" value="false" />
    ```

- Per utilizzare questa funzionalità durante l'esecuzione di RSAT dall'interfaccia della riga di comando (ad esempio Azure DevOps), aprire il file **Microsoft.Dynamics.RegressionSuite.ConsoleApp.exe.config** nella cartella di installazione di RSAT (ad esempio **C:\\Programmi (x86)\\Regression Suite Automation Tool**) e modificare il valore dell'elemento seguente da **false** a **true**.

    ```xml
    <add key="VerboseSnapshotsEnabled" value="false" />
    ```

Quando si eseguono casi di test, RSAT genera snapshot (immagini) dei passaggi e li salva nella cartella di riproduzione dei casi di test nella directory di lavoro. Nella cartella di riproduzione, viene creata una sottocartella separata denominata **StepSnapshot**. Quella cartella contiene gli snapshot per i casi di test eseguiti.

## <a name="assignment"></a>Assegnazione

### <a name="scenario"></a>Scenario

1. Il responsabile della progettazione dei prodotti crea un nuovo prodotto rilasciato.
2. Il responsabile produzione inizia un ordine di produzione per portare il livello scorte a due pezzi.
3. La produzione inizia e termina l'ordine di produzione e verifica che la quantità disponibile sia due pezzi.
4. Il team delle vendite riceve un ordine per quattro pezzi del nuovo prodotto. Di conseguenza, il team delle vendite aggiorna i fabbisogni netti tramite il piano dinamico. Poiché non è disponibile ulteriore capacità, i criteri di ordine predefiniti sono impostati su "acquista anziché produrre". Di conseguenza, viene creato un ordine fornitore pianificato.
5. L'acquirente aggiunge un fornitore, stabilizza l'ordine fornitore pianificato e conferma l'ordine fornitore.
6. Quando le merci acquistate arrivano presso il punto vendita, l'operatore cerca l'ordine fornitore correlato e riceve le merci. Poiché l'ordine è ora completato, le merci possono essere prelevate e imballate a fronte dell'ordine cliente.
7. L'ufficio contabilità registra la fattura di acquisto e quella di vendita.

Nella figura seguente è illustrato il flusso di questo scenario.

![Flusso dello scenario demo.](./media/use_rsa_tool_14.png)

La seguente illustrazione mostra la gerarchia dei processi aziendali per questo scenario in Modellatore di processi aziendali LCS.

![Processi aziendali per lo scenario demo.](./media/use_rsa_tool_15.png)

## <a name="strategy--key-learning"></a>Strategia - Suggerimenti chiave

### <a name="data"></a>Dati

- Assicurarsi di disporre di volumi di dati rappresentativi (una copia dei dati della configurazione prodotto/Golden oltre ai dati migrati).
- Quando si generano nuovi dati tramite Registrazione attività, creare nomi di test che non saranno in conflitto con i nomi esistenti (ad esempio, utilizzare un prefisso come **RSATxxx**).
- Utilizzare il ripristino temporizzato di Azure per eseguire di nuovo i test in ambienti non di livello 1.
- Sebbene sia possibile utilizzare le funzioni **RANDOM** e **NOW** di Excel per generare una combinazione univoca, questa operazione risulta parecchio complessa. Ecco un esempio.

    ```Excel
    product = "AT" &TEXT(NOW(),"yyymmddhhmm")
    ```

### <a name="task-recorder"></a>Registrazione attività

- Definire gli scenari prima di iniziare la registrazione. Un progetto ben gestito comporta scenari di test predefiniti. Per generare un test case, prendere in considerazione la prevedibilità del risultato di questi scenari di test.
- Dividere le registrazioni se vengono eseguite da ruoli differenti oppure in caso di tempo di attesa o di evento esterno prima del passaggio successivo.
- Non selezionare i valori negli elenchi. Utilizzare invece formati di testo, ad esempio **FIFO**, **AudioRM** e **SiteWH**. Quando si esegue la selezione in un elenco, viene registrata la posizione del valore nell'elenco e non il valore stesso. Se si aggiungono degli elementi a tale elenco, la posizione del valore può cambiare. Di conseguenza, la registrazione utilizzerà un parametro differente e ciò potrebbe influenzare il resto dello scenario.
- Prendere in considerazione il comportamento multiutente. Ad esempio, non presupporre che l'ordine cliente appena creato verrà sempre selezionato automaticamente. Invece, utilizzare sempre il filtro per trovare l'ordine corretto.
- Utilizzare la funzione Copia di Registrazione attività per salvare il nome di un prodotto appena creato di modo che possa essere utilizzato in test case concatenati.
- Utilizzare la funzione Convalida di Registrazione attività per impostare checkpoint con cui verificare la corretta esecuzione dei passaggi.

### <a name="rsat"></a>RSAT

- Per eseguire il test in un'altra società, è possibile modificare la società nella scheda **Generale** del file di parametri di Excel. Assicurarsi che le impostazioni e i dati siano disponibili nella nuova società selezionata.
- È possibile modificare l'utente dei test nella scheda **Generale** del file di parametri di Excel. Specificare l'ID di posta elettronica dell'utente che esegue il test case. In questo modo, il test case può essere eseguito utilizzando le autorizzazioni di sicurezza dell'utente specificato.
- Per ritardare l'esecuzione del test, è possibile definire una pausa nella scheda **Generale** del file di parametri di Excel. Questa pausa può essere utilizzata in un processo batch (ad esempio se un flusso di lavoro deve essere eseguito per poter eseguire il passaggio successivo).

## <a name="advanced-scripting"></a>Script avanzato

### <a name="cli"></a>CLI

RSAT può essere chiamato da una finestra **Prompt dei comandi** o **PowerShell**.

> [!NOTE]
> Verificare che la variabile di ambiente **TestRoot** sia impostata sul percorso di installazione di RSAT. (in Microsoft Windows, aprire **Pannello di controllo**, selezionare **Sistema e sicurezza \> Sistema \> Impostazioni di sistema avanzate** e quindi **Variabili di ambiente**).

1. Aprire una finestra **Prompt dei comandi** o **PowerShell** come amministratore.
2. Passare alla directory di installazione RSAT.

    ```Console
    cd "c:\Program Files (x86)\Regression Suite Automation Tool\"
    ```

3. Elencare tutti i comandi.

    ```Console
    C:\Program Files (x86)\Regression Suite Automation Tool>Microsoft.Dynamics.RegressionSuite.ConsoleApp.exe help

    Usage:
        Microsoft.Dynamics.RegressionSuite.ConsoleApp.exe command
        or
        Microsoft.Dynamics.RegressionSuite.ConsoleApp.exe /settings "C:\Path to\file.settings" command

    Available commands:
        ?
        about
        cls
        download
        downloadsuite
        edit
        generate
        generatederived
        generatetestonly
        generatetestsuite
        help
        list
        listtestplans
        listtestsuite
        listtestsuitebyid
        listtestsuitenames
        playback
        playbackbyid
        playbackmany
        playbacksuite
        playbacksuitebyid
        quit
        upload
        uploadrecording
        usage
    ```

#### <a name=""></a>?

Elenca tutti i comandi o mostra la guida per un comando specifico, insieme ai parametri disponibili.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``?``**``[command]``

##### <a name="-optional-parameters"></a>?: Parametri facoltativi

`command`: Dove ``[command]`` è uno dei comandi dell'elenco precedente.

#### <a name="about"></a>informazioni su

Visualizza la versione del RSAT installato.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``about``**

#### <a name="cls"></a>cls

Cancella il contenuto dello schermo.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``cls``**

#### <a name="download"></a>scarica

Scarica gli allegati (file di registrazione, esecuzione e parametri) per il test case specificato da Azure DevOps nella directory di output. Puoi usare il comando ``list`` per ottenere tutti i test case disponibili e utilizzare qualsiasi valore dalla prima colonna come parametro **test_case_id**.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``download``**``[/retry[=<seconds>]] [test_case_id] [output_dir]``

##### <a name="download-optional-switches"></a>download: opzioni facoltative

+ `/retry[=seconds]`: se viene specificata questa opzione e i test case vengono bloccati da altre istanze RSAT, il processo di download attenderà il numero di secondi specificato, quindi proverà ancora una volta. Il valore predefinito per \[seconds\] è 120 secondi. Senza questa opzione, il processo verrà annullato immediatamente se i test case vengono bloccati.

##### <a name="download-required-parameters"></a>download: parametri obbligatori

+ `test_case_id`: rappresenta l'ID del test case.

##### <a name="download-optional-parameters"></a>download: parametri facoltativi

+ `output_dir`: rappresenta la directory di lavoro di output. È necessario che la directory sia già presente. La directory di lavoro delle impostazioni verrà utilizzata se questo parametro non è specificato.

##### <a name="download-examples"></a>download: esempi

`download 123 c:\temp\rsat`

`download /retry=240 765`

#### <a name="downloadsuite"></a>downloadsuite

Scarica gli allegati (file di registrazione, esecuzione e parametri) per tutti i test case nella suite di test specificata da Azure DevOps nella directory di output. Puoi usare il comando ``listtestsuitenames`` per ottenere tutte le suite di test disponibili e utilizzare qualsiasi valore come parametro **test_suite_name**.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``downloadsuite``**``[/retry[=<seconds>]] ([test_suite_name] | [/byid] [test_suite_id]) [output_dir]``

##### <a name="downloadsuite-optional-switches"></a>downloadsuite: opzioni facoltative

+ `/retry[=seconds]`: se viene specificata questa opzione e i test case vengono bloccati da altre istanze RSAT, il processo di download attenderà il numero di secondi specificato, quindi proverà ancora una volta. Il valore predefinito per \[seconds\] è 120 secondi. Senza questa opzione, il processo verrà annullato immediatamente se i test case vengono bloccati.
+ `/byid`: questa opzione indica che la suite di test desiderata è identificata dall'ID Azure DevOps e non dal nome della suite di test.

##### <a name="downloadsuite-required-parameters"></a>downloadsuite: parametri obbligatori

+ `test_suite_name`: rappresenta il nome della suite di test. Questo parametro è obbligatorio se lo è l'opzione /byid **non** è specificata. Questo nome è il nome della suite di test Azure DevOps.
+ `test_suite_id`: rappresenta l'ID della suite di test. Questo parametro è obbligatorio se lo è l'opzione /byid **è** specificata. Questo ID è un ID suite di test Azure DevOps.

##### <a name="downloadsuite-optional-parameters"></a>downloadsuite: parametri facoltativi

+ `output_dir`: rappresenta la directory di lavoro di output. È necessario che la directory sia già presente. La directory di lavoro delle impostazioni verrà utilizzata se questo parametro non è specificato.

##### <a name="downloadsuite-examples"></a>downloadsuite: esempi

`downloadsuite NameOfTheSuite c:\temp\rsat`

`downloadsuite /byid 123 c:\temp\rsat`

`downloadsuite /retry=240 /byid 765`

`downloadsuite /retry=240 /byid 765 c:\temp\rsat`

#### <a name="edit"></a>modifica

Permette di aprire il file dei parametri nel programma Excel e di modificarlo.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``edit``**``[excel_file]``

##### <a name="edit-required-parameters"></a>modifica: parametri obbligatori

+ `excel_file`: deve contenere un percorso completo di un file Excel esistente.

##### <a name="edit-examples"></a>modifica: esempi

`edit c:\RSAT\123\TestCase_123_Base.xlsx`

`edit e:\temp\TestCase_456_Base.xlsx`

#### <a name="generate"></a>generate

Genera i file di esecuzione del test e dei parametri per il test case specificato nella directory di output. È possibile usare il comando ``list`` per ottenere tutti i test case disponibili. Utilizzare qualsiasi valore della prima colonna come parametro **test_case_id**.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``generate``**``[/retry[=<seconds>]] [/dllonly] [/keepcustomexcel] [test_case_id] [output_dir]``

##### <a name="generate-optional-switches"></a>generate: opzioni facoltative

+ `/retry[=seconds]`: se viene specificata questa opzione e i test case vengono bloccati da altre istanze RSAT, il processo di generazione attenderà il numero di secondi specificato, quindi proverà ancora una volta. Il valore predefinito per \[seconds\] è 120 secondi. Senza questa opzione, il processo verrà annullato immediatamente se i test case vengono bloccati.
+ `/dllonly`: Genera solo file di esecuzione del test. Non genera nuovamente il file dei parametri di Excel.
+ `/keepcustomexcel`: aggiorna il file dei parametri esistente. Rigenera anche i file di esecuzione.

##### <a name="generate-required-parameters"></a>generare: parametri obbligatori

+ `test_case_id`: rappresenta l'ID del test case.

##### <a name="generate-optional-parameters"></a>generate: parametri facoltativi

+ `output_dir`: rappresenta la directory di lavoro di output. È necessario che la directory sia già presente. La directory di lavoro delle impostazioni verrà utilizzata se questo parametro non è specificato.

##### <a name="generate-examples"></a>generare: esempi

`generate 123 c:\temp\rsat`

`generate /retry=240 765 c:\rsat\last`

`generate /retry=240 /dllonly 765`

`generate /retry=240 /keepcustomexcel 765`

#### <a name="generatederived"></a>generatederived

Genera un nuovo test case derivato (test case figlio) dal test case fornito. Il nuovo test case viene anche aggiunto alla suite di test specificata. Puoi usare il comando ``list`` per ottenere tutti i test case disponibili e utilizzare qualsiasi valore dalla prima colonna come parametro **test_case_id**.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``generatederived``**``[/retry[=<seconds>]] [parent_test_case_id] [test_plan_id] [test_suite_id]``

##### <a name="generatederived-optional-switches"></a>generatederived: opzioni facoltative

+ `/retry[=seconds]`: se viene specificata questa opzione e i test case vengono bloccati da altre istanze RSAT, il processo di generazione attenderà il numero di secondi specificato, quindi proverà ancora una volta. Il valore predefinito per \[seconds\] è 120 secondi. Senza questa opzione, il processo verrà annullato immediatamente se i test case vengono bloccati.

##### <a name="generatederived-required-parameters"></a>generatederived: parametri obbligatori

+ `parent_test_case_id`: rappresenta l'ID del test case padre.
+ `test_plan_id`: rappresenta l'ID del piano di test.
+ `test_suite_id`: rappresenta l'ID della suite di test.

##### <a name="generatederived-examples"></a>generatederived: esempi

`generatederived 123 8901 678`

`generatederived /retry 123 8901 678`

#### <a name="generatetestonly"></a>generatetestonly

Genera solo i file di esecuzione del test per il test case specificato. Non genera il file dei parametri di Excel. I file vengono generati nella directory di output specificata. Puoi usare il comando ``list`` per ottenere tutti i test case disponibili e utilizzare qualsiasi valore dalla prima colonna come parametro **test_case_id**.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``generatetestonly``**``[/retry[=<seconds>]] [test_case_id] [output_dir]``

##### <a name="generatetestonly-optional-switches"></a>generatetestonly: opzioni facoltative

+ `/retry[=seconds]`: se viene specificata questa opzione e i test case vengono bloccati da altre istanze RSAT, il processo di generazione attenderà il numero di secondi specificato, quindi proverà ancora una volta. Il valore predefinito per \[seconds\] è 120 secondi. Senza questa opzione, il processo verrà annullato immediatamente se i test case vengono bloccati.

##### <a name="generatetestonly-required-parameters"></a>generatetestonly: parametri obbligatori

+ `test_case_id`: rappresenta l'ID del test case.

##### <a name="generatetestonly-optional-parameters"></a>generatetestonly: parametri facoltativi

+ `output_dir`: rappresenta la directory di lavoro di output. È necessario che la directory sia già presente. La directory di lavoro delle impostazioni verrà utilizzata se questo parametro non è specificato.

##### <a name="generatetestonly-examples"></a>generatetestonly: esempi

`generatetestonly 123 c:\temp\rsat`

`generatetestonly /retry=240 765`

#### <a name="generatetestsuite"></a>generatetestsuite

Genera i file di automazione del test per tutti i test case nella suite di test specificata. Puoi usare il comando ``listtestsuitenames`` per ottenere tutte le suite di test disponibili e utilizzare qualsiasi valore come parametro **test_suite_name**.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``generatetestsuite``**``[/retry[=<seconds>]] [/dllonly] [/keepcustomexcel] ([test_suite_name] | [/byid] [test_suite_id]) [output_dir]``

##### <a name="generatetestsuite-optional-switches"></a>generatetestsuite: opzioni facoltative

+ `/retry[=seconds]`: se viene specificata questa opzione e i test case vengono bloccati da altre istanze RSAT, il processo di generazione attenderà il numero di secondi specificato, quindi proverà ancora una volta. Il valore predefinito per \[seconds\] è 120 secondi. Senza questa opzione, il processo verrà annullato immediatamente se i test case vengono bloccati.
+ `/dllonly`: Genera solo file di esecuzione del test. Non genera nuovamente il file dei parametri di Excel.
+ `/keepcustomexcel`: aggiorna il file dei parametri esistente. Rigenera anche i file di esecuzione.
+ `/byid`: questa opzione indica che la suite di test desiderata è identificata dall'ID Azure DevOps e non dal nome della suite di test.

##### <a name="generatetestsuite-required-parameters"></a>generatetestsuite: parametri obbligatori

+ `test_suite_name`: rappresenta il nome della suite di test. Questo parametro è obbligatorio se lo è l'opzione /byid **non** è specificata. Questo nome è il nome della suite di test Azure DevOps.
+ `test_suite_id`: rappresenta l'ID della suite di test. Questo parametro è obbligatorio se lo è l'opzione /byid **è** specificata. Questo ID è un ID suite di test Azure DevOps.

##### <a name="generatetestsuite-optional-parameters"></a>generatetestsuite: parametri facoltativi

+ `output_dir`: rappresenta la directory di lavoro di output. È necessario che la directory sia già presente. La directory di lavoro delle impostazioni verrà utilizzata se questo parametro non è specificato.

##### <a name="generatetestsuite-examples"></a>generatetestsuite: esempi

`generatetestsuite Tests c:\temp\rsat`

`generatetestsuite /retry Purchase c:\rsat\last`

`generatetestsuite /dllonly /byid 121`

`generatetestsuite /keepcustomexcel /byid 121`

#### <a name="help"></a>guida

Identico a [?](#section) comandi.

#### <a name="list"></a>elenco

Elenca tutti i test case disponibili nel piano di test corrente.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``list``**

#### <a name="listtestplans"></a>listtestplans

Elenca tutti i piani di test disponibili.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``listtestplans``**

#### <a name="listtestsuite"></a>listtestsuite

Elenca i test case per la suite di test specificata. Puoi usare il comando ``listtestsuitenames`` per ottenere tutte le suite di test disponibili e utilizzare qualsiasi valore dell'elenco come parametro **suite_name**.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``listtestsuite``**``[test_suite_name]``

##### <a name="listtestsuite-required-parameters"></a>listtestsuite: parametri obbligatori

+ `test_suite_name`: il nome della suite desiderata.

##### <a name="listtestsuite-examples"></a>listtestsuite: esempi

`listtestsuite "sample suite name"`

`listtestsuite NameOfTheSuite`

#### <a name="listtestsuitebyid"></a>listtestsuitebyid

Elenca i test case per la suite di test specificata.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``listtestsuitebyid``**``[test_suite_id]``

##### <a name="listtestsuitebyid-required-parameters"></a>listtestsuitebyid: parametri obbligatori

+ `test_suite_id`: l'ID della suite desiderata.

##### <a name="listtestsuitebyid-examples"></a>listtestsuitebyid: esempi

`listtestsuitebyid 12345`

#### <a name="listtestsuitenames"></a>listtestsuitenames

Elenca tutte le suite di test disponibili nel piano di test corrente.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``listtestsuitenames``**

#### <a name="playback"></a>playback

Riproduce il test case associato al file dei parametri Excel specificato. Questo comando utilizza i file di automazione locali esistenti e non scarica i file da Azure DevOps. Questo comando non è supportato per i test case del commercio POS.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``playback``**``[/retry[=<seconds>]] [/comments[="comment"]] [excel_parameter_file]``

##### <a name="playback-optional-switches"></a>playback: opzioni facoltative

+ `/retry[=seconds]`: se viene specificata questa opzione e i test case vengono bloccati da altre istanze RSAT, il processo di riproduzione attenderà il numero di secondi specificato, quindi proverà ancora una volta. Il valore predefinito per \[seconds\] è 120 secondi. Senza questa opzione, il processo verrà annullato immediatamente se i test case vengono bloccati.
+ `/comments[="comment"]`: Fornisci una stringa di informazioni personalizzata che verrà inclusa nel campo **Commenti** nelle pagine di riepilogo e risultati del test per le esecuzioni di test case di Azure DevOps.

##### <a name="playback-required-parameters"></a>playback: parametri obbligatori

+ `excel_parameter_file`: il percorso completo di un file di parametri di Excel. Il file deve essere già presente.

##### <a name="playback-examples"></a>playback: esempi

`playback c:\RSAT\2745\attachments\Create_Purchase_Order_2745_Base.xlsx`

`playback /retry e:\temp\test.xlsx`

`playback /retry=300 e:\temp\test.xlsx`

`playback /comments="Payroll solution 10.0.0" e:\temp\test.xlsx`

#### <a name="playbackbyid"></a>playbackbyid

Riproduce più test case contemporaneamente. I test case sono identificati dall'ID. Questo comando scaricherà i file da Azure DevOps. Puoi usare il comando ``list`` per ottenere tutti i test case disponibili e utilizzare uno qualsiasi dei valori dalla prima colonna come parametro **test_case_id**.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``playbackbyid``**``[/retry[=<seconds>]] [/comments[="comment"]] [test_case_id1] [test_case_id2] ... [test_case_idN]``

##### <a name="playbackbyid-optional-switches"></a>playbackbyid: opzioni facoltative

+ `/retry[=seconds]`: se viene specificata questa opzione e i test case vengono bloccati da altre istanze RSAT, il processo di riproduzione attenderà il numero di secondi specificato, quindi proverà ancora una volta. Il valore predefinito per \[seconds\] è 120 secondi. Senza questa opzione, il processo verrà annullato immediatamente se i test case vengono bloccati.
+ `/comments[="comment"]`: Fornisci una stringa di informazioni personalizzata che verrà inclusa nel campo **Commenti** nelle pagine di riepilogo e risultati del test per le esecuzioni di test case di Azure DevOps.

##### <a name="playbackbyid-required-parameters"></a>playbackbyid: parametri obbligatori

+ `test_case_id1`: l'ID del test case esistente.
+ `test_case_id2`: l'ID del test case esistente.
+ `test_case_idN`: l'ID del test case esistente.

##### <a name="playbackbyid-examples"></a>playbackbyid: esempi

`playbackbyid 878`

`playbackbyid 2345 667 135`

`playbackbyid /comments="Payroll solution 10.0.0" 2345 667 135`

`playbackbyid /retry /comments="Payroll solution 10.0.0" 2345 667 135`

#### <a name="playbackmany"></a>playbackmany

Riproduce più test case contemporaneamente. I test case sono identificati dai file dei parametri di Excel. Questo comando utilizza i file di automazione locali esistenti e non scarica i file da Azure DevOps.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``playbackmany``**``[/retry[=<seconds>]] [/comments[="comment"]] [excel_parameter_file1] [excel_parameter_file2] ... [excel_parameter_fileN]``

##### <a name="playbackmany-optional-switches"></a>playbackmany: opzioni facoltative

+ `/retry[=seconds]`: se viene specificata questa opzione e i test case vengono bloccati da altre istanze RSAT, il processo di riproduzione attenderà il numero di secondi specificato, quindi proverà ancora una volta. Il valore predefinito per \[seconds\] è 120 secondi. Senza questa opzione, il processo verrà annullato immediatamente se i test case vengono bloccati.
+ `/comments[="comment"]`: Fornisci una stringa di informazioni personalizzata che verrà inclusa nel campo **Commenti** nelle pagine di riepilogo e risultati del test per le esecuzioni di test case di Azure DevOps.

##### <a name="playbackmany-required-parameters"></a>playbackmany: parametri obbligatori

+ `excel_parameter_file1`: il percorso completo di un file di parametri di Excel. Il file deve essere già presente.
+ `excel_parameter_file2`: il percorso completo di un file di parametri di Excel. Il file deve essere già presente.
+ `excel_parameter_fileN`: il percorso completo di un file di parametri di Excel. Il file deve essere già presente.

##### <a name="playbackmany-examples"></a>playbackmany: esempi

`playbackmany c:\RSAT\2745\attachments\Create_Purchase_Order_2745_Base.xlsx`

`playbackmany e:\temp\test.xlsx f:\RSAT\sample1.xlsx c:\RSAT\sample2.xlsx`

`playbackmany /retry=180 /comments="Payroll solution 10.0.0" e:\temp\test.xlsx f:\rsat\sample1.xlsx c:\RSAT\sample2.xlsx`

#### <a name="playbacksuite"></a>playbacksuite

Riproduce tutti i test case da una o più suite di test specificate. Se viene specificata l'opzione /local, gli allegati locali verranno utilizzati per la riproduzione. In caso contrario, gli allegati verranno scaricati da Azure DevOps. Puoi usare il comando ``listtestsuitenames`` per ottenere tutte le suite di test disponibili e utilizzare qualsiasi valore della prima colonna come parametro **suite_name**.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``playbacksuite``**``[/updatedriver] [/local] [/retry[=<seconds>]] [/comments[="comment"]] ([test_suite_name1] .. [test_suite_nameN] | [/byid] [test_suite_id1] .. [test_suite_idN])``

##### <a name="playbacksuite-optional-switches"></a>playbacksuite: opzioni facoltative

+ `/updatedriver`: se viene specificata questa opzione, il webdriver del browser Internet verrà aggiornato come richiesto prima dell'esecuzione del processo di riproduzione.
+ `/local`: questa opzione indica che gli allegati locali devono essere utilizzati per la riproduzione invece di scaricare i file da Azure DevOps.
+ `/retry[=seconds]`: se viene specificata questa opzione e i test case vengono bloccati da altre istanze RSAT, il processo di riproduzione attenderà il numero di secondi specificato, quindi proverà ancora una volta. Il valore predefinito per \[seconds\] è 120 secondi. Senza questa opzione, il processo verrà annullato immediatamente se i test case vengono bloccati.
+ `/comments[="comment"]`: Fornisci una stringa di informazioni personalizzata che verrà inclusa nel campo **Commenti** nelle pagine di riepilogo e risultati del test per le esecuzioni di test case di Azure DevOps.
+ `/byid`: questa opzione indica che la suite di test desiderata è identificata dall'ID Azure DevOps e non dal nome della suite di test.

##### <a name="playbacksuite-required-parameters"></a>playbacksuite: parametri obbligatori

+ `test_suite_name1`: rappresenta il nome della suite di test. Questo parametro è obbligatorio se lo è l'opzione /byid **non** è specificata. Questo nome è il nome della suite di test Azure DevOps.
+ `test_suite_nameN`: rappresenta il nome della suite di test. Questo parametro è obbligatorio se lo è l'opzione /byid **non** è specificata. Questo nome è il nome della suite di test Azure DevOps.
+ `test_suite_id1`: rappresenta l'ID della suite di test. Questo parametro è obbligatorio se lo è l'opzione /byid **è** specificata. Questo ID è l'ID suite di test Azure DevOps.
+ `test_suite_idN`: rappresenta l'ID della suite di test. Questo parametro è obbligatorio se lo è l'opzione /byid **è** specificata. Questo ID è l'ID suite di test Azure DevOps.

##### <a name="playbacksuite-examples"></a>playbacksuite: esempi

`playbacksuite suiteName`

`playbacksuite suiteName suiteNameToo`

`playbacksuite /updatedriver /local /retry=180 /byid 151 156`

`playbacksuite /updatedriver /local /comments="Payroll solution 10.0.0" /byid 150`

#### <a name="playbacksuitebyid"></a>playbacksuitebyid

Esegue tutti i test case nella suite di test Azure DevOps specificata.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``playbacksuitebyid``**``[/updatedriver] [/local] [/retry[=<seconds>]] [/comments[="comment"]] [test_suite_id]``

##### <a name="playbacksuitebyid-optional-switches"></a>playbacksuitebyid: opzioni facoltative

+ `/retry[=seconds]`: se viene specificata questa opzione e i test case vengono bloccati da altre istanze RSAT, il processo di riproduzione attenderà il numero di secondi specificato, quindi proverà ancora una volta. Il valore predefinito per \[seconds\] è 120 secondi. Senza questa opzione, il processo verrà annullato immediatamente se i test case vengono bloccati.
+ `/comments[="comment"]`: Fornisci una stringa di informazioni personalizzata che verrà inclusa nel campo **Commenti** nelle pagine di riepilogo e risultati del test per le esecuzioni di test case di Azure DevOps.
+ `/byid`: questa opzione indica che la suite di test desiderata è identificata dall'ID Azure DevOps e non dal nome della suite di test.

##### <a name="playbacksuitebyid-required-parameters"></a>playbacksuitebyid: parametri obbligatori

+ `test_suite_id`: rappresenta l'ID della suite di test così come esiste in Azure DevOps.

##### <a name="playbacksuitebyid-examples"></a>playbacksuitebyid: esempi

`playbacksuitebyid 2900`

`playbacksuitebyid /retry 2099`

`playbacksuitebyid /retry=200 2099`

`playbacksuitebyid /retry=200 /comments="some comment" 2099`

#### <a name="quit"></a>quit

Chiude l'applicazione. Questo comando è utile solo quando le applicazioni sono in esecuzione in modalità interattiva.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``quit``**

##### <a name="quit-examples"></a>quit: esempi

`quit`

#### <a name="upload"></a>upload

Carica i file allegati (file di registrazione, esecuzione e parametri) che appartengono a una suite di test o test case specificati in Azure DevOps.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``upload``**``([test_suite_name] | [test_case_id1] .. [test_case_idN])``

##### <a name="upload-required-parameters"></a>upload: parametri obbligatori

+ `test_suite_name` Tutti i file che appartengono alla suite di test verranno caricati.
+ `test_case_id1`: rappresenta il primo ID test case che deve essere caricato. Utilizza questo parametro solo quando non è stato fornito alcun nome della suite di test.
+ `test_case_idN`: rappresenta l'ultimo ID test case che deve essere caricato. Utilizza questo parametro solo quando non è stato fornito alcun nome della suite di test.

##### <a name="upload-examples"></a>upload: esempi

`upload sample_suite`

`upload 2900`

`upload 123 456`

#### <a name="uploadrecording"></a>uploadrecording

Carica solo il file di registrazione che appartiene a uno o più test case specificati in Azure DevOps.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``uploadrecording``**``[test_case_id1] .. [test_case_idN]``

##### <a name="uploadrecording-required-parameters"></a>uploadrecording: parametri obbligatori

+ `test_case_id1`: rappresenta il primo ID test case per la registrazione che deve essere caricato in Azure DevOps.
+ `test_case_idN`: rappresenta l'ultimo ID test case per la registrazione che deve essere caricato in Azure DevOps.

##### <a name="uploadrecording-examples"></a>uploadrecording: esempi

`uploadrecording 123`

`uploadrecording 123 456`

#### <a name="usage"></a>usage

Visualizza le tre modalità di utilizzo di questa applicazione.

``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``usage``**

Esecuzione dell'applicazione in modo interattivo:

+ ``Microsoft.Dynamics.RegressionSuite.ConsoleApp``

Esecuzione dell'applicazione specificando un comando:

+ ``Microsoft.Dynamics.RegressionSuite.ConsoleApp ``**``[command]``**

Esecuzione dell'applicazione fornendo un file di impostazioni:

+ ``Microsoft.Dynamics.RegressionSuite.ConsoleApp``**``/settings [drive:\Path to\file.settings] [command]``**

### <a name="windows-powershell-examples"></a>Esempi di Windows PowerShell

#### <a name="run-a-test-case-in-a-loop"></a>Eseguire un test case in un ciclo

Si ha uno script di test che crea un nuovo cliente. Tramite lo script, questo test case può essere eseguito in un ciclo randomizzando i seguenti dati prima dell'esecuzione di ogni iterazione:

- ID cliente
- Nome cliente
- Indirizzo cliente

L'ID cliente sarà in formato *ATCUS\<number\>*, dove \<number\> è un valore compreso tra **000000001** e **999999999**.

Nel seguente esempio viene utilizzato un parametro **start** per definire il primo numero utilizzato. Un secondo parametro, **nr**, viene utilizzato per definire il numero di clienti che devono essere creati. Per ogni iterazione, i parametri nel file di parametri di Excel vengono modificati utilizzando una funzione UpdateCustomer. La riga di comando di RSAT viene quindi richiamata in una funzione RunTestCase.

Aprire Microsoft Windows PowerShell Integrated Scripting Environment (ISE) in modalità amministratore e incollare il seguente codice nella finestra denominata **Untitled1.ps1**.

```powershell
param ( [int]$start = 1, [int]$nr = 1 )
function UpdateCustomer
{
    param ([string]$paramFilename, [string]$sheetName, [string]$CustId)
    $xl = New-Object -COM "Excel.Application"
    $xl.Visible = $false
    $wb = $xl.Workbooks.Open($paramFilename)
    $ws = $wb.Sheets.Item($sheetName)
    $ws.Cells.Item(3, 2).Value = "ATCUS" + $CustId
    $ws.Cells.Item(4, 2).Value = "Automated Test Customer " + $CustId
    $ws.Cells.Item(8, 2).Value = "Automated Test Street " + $CustId
    $wb.Save()
    $wb.Close()
    $xl.Quit()
    [System.Runtime.Interopservices.Marshal]::ReleaseComObject($xl)
}
function RunTestCase
{
    param ( [string]$filename )
    $cmd = "cd c:\Program Files (x86)\Regression Suite Automation Tool\ &&  "
    $cmd = $cmd + "Microsoft.Dynamics.RegressionSuite.ConsoleApp.exe playback "
    $cmd = $cmd + $filename
    cmd /c $cmd
}
$excelFilename = "full path to Excel parameter file"
l$sheetName = "DirPartyQuickCreateForm"
for ($i = $start; $i -lt $start + $nr; $i++ )
{
    $CustomerId = $i.ToString("000000000")
    Write-Host "customer : " $CustomerId
    UpdateCustomer $excelFilename $sheetName $CustomerId
    RunTestCase $excelFilename
```

#### <a name="run-a-script-that-depends-on-data-in-microsoft-dynamics-365"></a>Eseguire uno script che dipende dai dati in Microsoft Dynamics 365

Nell'esempio seguente viene utilizzata una chiamata Open Data Protocol (OData) per individuare lo stato di un ordine fornitore. Se lo stato non è **fatturato**, è ad esempio possibile chiamare un test case RSAT che registra la fattura.

```powershell
function Odata_Get
{
    Param ( [string] $environment, [string] $cmd )
    [Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12
    $tenant = "your tenant"
    $creds = @{
        grant_type = "client_credentials"
        client_id = "your client application Id"
        client_secret = "your client secret"
        resource = $environment
    }
    $headers = $null
    $bearer = Invoke-RestMethod https://login.microsoftonline.com/$tenant/oauth2/token -Method Post -Body $creds -Headers $headers;
    $headers = @{
        Authorization = "Bearer " + $bearer.access_token
    }
    $Odata_cmd = $environment + '/data/' + $cmd
    return (Invoke-RestMethod -Uri $Odata_cmd -Method Get -Headers $headers -ContentType application/json )
}
function PurchaseOrderStatus
{
    Param ( [string] $environment, [string] $purchaseOrderNumber )
    $cmd = 'PurchaseOrderHeaders?$filter=PurchaseOrderNumber eq '
    $cmd = $cmd + "'" + $purchaseOrderNumber + "'"
    $response = Odata_Get -environment $environment -cmd $cmd
    return $response.value.PurchaseOrderStatus
}
$environment = "https://your environment"
$orderStatus = PurchaseOrderStatus -environment $environment -purchaseOrderNumber '000003'
if ($orderStatus -eq $null) {   write-host 'doesn''t exist'}
elseif ($orderStatus -ne 'invoiced') { RunTestCase "PostInvoice" }
```


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
