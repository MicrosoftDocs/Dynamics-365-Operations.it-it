---
title: Esercitazione sull'utilizzo di Regression Suite Automation Tool
description: In questo argomento viene illustrato come utilizzare lo strumento Regression Suite Automation Tool (RSAT). Vengono descritte varie funzionalità e forniti esempi che utilizzano lo script avanzato.
author: kfend
manager: AnnBe
ms.date: 06/09/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 21761
ms.search.region: Global
ms.author: kfend
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: AX 7.0.0, Operations
ms.openlocfilehash: cf3ca501efb4e540994b01e651eee5b8aab4ddbc
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/27/2019
ms.locfileid: "2191088"
---
# <a name="use-the-regression-suite-automation-tool-tutorial"></a>Esercitazione sull'utilizzo di Regression Suite Automation Tool

[!include [banner](../includes/banner.md)]

> [!NOTE]
> Utilizzare gli strumenti del browser Internet per scaricare e salvare questa pagina in formato PDF. 

Questa esercitazione descrive alcune delle funzionalità avanzate di Regression Suite Automation Tool (RSAT), include un'assegnazione demo e fornisce suggerimenti chiave e la strategia da adottare.

## <a name="features-of-rsattask-recorder"></a>Funzionalità di RSAT/Registrazione attività

### <a name="validate-a-field-value"></a>Convalidare un valore di campo

Per informazioni su questa funzionalità, vedere [Creare una nuova registrazione attività che dispone di una funzione Convalida](./hol-set-up-regression-suite-automation-tool.md#create-a-new-task-recording-that-has-a-validate-function).

### <a name="saved-variable"></a>Variabile salvata

Per informazioni su queste funzionalità, vedere [Modificare una registrazione attività esistente per creare una variabile salvata](./hol-set-up-regression-suite-automation-tool.md#modify-an-existing-task-recording-to-create-a-saved-variable).

### <a name="derived-test-case"></a>Test case derivato

1. Aprire Regression Suite Automation Tool (RSAT) e selezionare entrambi i test case creati in [Impostare e installare Regression Suite Automation Tool](./hol-set-up-regression-suite-automation-tool.md).
2. Selezionare **Nuovo \> Crea test case derivato**.

    ![Comando Crea test case derivato nel menu Nuovo](./media/use_rsa_tool_01.png)

3. Viene visualizzato un messaggio indicante che un test case derivato verrà creato per ogni test case selezionato nel gruppo di test corrente e che ogni test case derivato disporrà di una propria copia del file di parametri di Excel. Selezionare **OK**.

    > [!NOTE]
    > Quando si esegue un test case derivato, questo utilizza la registrazione attività del relativo test case padre e la propria copia del file di parametri di Excel. In questo modo, è possibile eseguire lo stesso test con parametri differenti, senza dover avere più di una registrazione attività. Un test case derivato non deve far parte dello stesso gruppo di test come test case padre.

    ![Finestra di messaggio](./media/use_rsa_tool_02.png)

    Vengono creati due ulteriori test case derivati e la relativa casella di controllo **Derivato?** è selezionata.

    ![Test case derivati creati](./media/use_rsa_tool_03.png)

    Un test case derivato viene automaticamente creato in Azure DevOps. È un elemento secondario del test case **Creare un nuovo prodotto** e viene contrassegnato con una parola chiave speciale: **RSAT: DerivedTestSteps**. Questi test case vengono inoltre aggiunti automaticamente al piano di test in Azure DevOps.

    ![Parola chiave RSAT:DerivedTestSteps](./media/use_rsa_tool_04.png)

    > [!NOTE]
    > Se, per un qualsiasi motivo, i test case derivati creati non sono nell'ordine corretto, accedere a Azure DevOps e riordinare i test case nel gruppo di test, di modo che RSAT possa eseguirli nell'ordine corretto.

4. Selezionare i test case derivati, quindi selezionare **Modifica** per aprire i file di parametri di Excel corrispondenti.
5. Modificare questi file di parametri di Excel esattamente come i file padre. In altre parole, assicurarsi che l'ID prodotto sia impostato di modo che venga generato automaticamente. Verificare inoltre che la variabile salvata venga copiata nei campi appropriati.
6. Nella scheda **Generale** di entrambi i file di parametri di Excel, impostare il valore del campo **Società** su **USSI**, di modo che i test case derivati siano eseguiti per una persona giuridica differente rispetto al test case padre. Per eseguire i test case per un utente specifico (o per il ruolo associato a un utente specifico), è possibile aggiornare il valore del campo **Verifica utente**.
7. Selezionare **Esegui** e verificare che il prodotto venga creato nelle persone giuridiche USMF e USSI.

### <a name="validate-notifications"></a>Convalidare le notifiche

Questa funzionalità può essere utilizzata per convalidare un'azione avvenuta. Ad esempio, quando un ordine di produzione viene creato, valutato e quindi avviato, l'app visualizza un messaggio "Produzione - Avvio" per notificare all'utente che l'ordine di produzione è stato avviato.

![Notifica Produzione - Avvio](./media/use_rsa_tool_05.png)

È possibile convalidare questo messaggio mediante RSAT digitando il testo del messaggio nella scheda **MessageValidation** del file di parametri di Excel per la registrazione appropriata.

![Scheda Convalida messaggio](./media/use_rsa_tool_06.png)

Dopo l'esecuzione del test case, il messaggio nel file di parametri di Excel viene confrontato al messaggio visualizzato. Se i messaggi non corrispondono, il test case non avrà esito positivo.

> [!NOTE]
> È possibile immettere più di un messaggio nella scheda **Convalida messaggio** del file di parametri di Excel. I messaggi possono anche essere messaggi di errore o di avviso anziché messaggi informativi.

### <a name="validate-values-by-using-operators"></a>Convalidare i valori utilizzando operatori

Nelle versioni precedenti di RSAT, è possibile convalidare i valori solo se un valore di controllo è uguale a un valore previsto. La nuova funzionalità consente di verificare se una variabile non è uguale a, è minore di o è maggiore di un valore specificato.

- Per utilizzare questa funzionalità, aprire il file **Microsoft.Dynamics.RegressionSuite.WindowsApp.exe.config** nella cartella di installazione di RSAT (ad esempio **C:\\Programmi (x86)\\Regression Suite Automation Tool**) e modificare il valore dell'elemento seguente da **false** a **true**.

    ```
    <add key="AddOperatorFieldsToExcelValidation" value="false" />
    ```

    Nel file di parametri di Excel, viene visualizzato un nuovo campo **Operatore**.

    > [!NOTE]
    > Se si utilizza una versione precedente di RSAT, è necessario generare nuovi file di parametri di Excel.

    ![Campo Operatore](./media/use_rsa_tool_07.png)

Nell'esempio seguente viene illustrato come utilizzare questa funzionalità per verificare se le scorte disponibili sono maggiori di 0 (zero).

1. Nei dati demo della società **USMF**, creare una registrazione attività che includa i seguenti passaggi:

    1. Fare clic su **Gestione informazioni sul prodotto \> Prodotti \> Prodotti rilasciati**.
    2. Utilizzare il filtro rapido per trovare i record. Ad esempio, filtrare in base al valore **1000** nel campo **Numero articolo**.
    3. Selezionare **Scorte disponibili**.
    4. Utilizzare il filtro rapido per trovare i record. Ad esempio, filtrare in base al valore **1** nel campo **Sito**.
    5. Nell'elenco contrassegnare la riga selezionata.
    6. Verificare che il valore del campo **Totale disponibile** sia **411,0000000000000000**.

2. Salvare la registrazione attività nella libreria BPM in LCS e sincronizzarla con Azure DevOps.
3. Aggiungere il test case al piano di test e caricare il test case in RSAT.
4. Apre il file di parametri di Excel. Nella scheda **InventOnhandItem** verrà visualizzata una sezione **Convalida InventOnhandItem** che include un campo **Operatore**.

    ![Campo Operatore](./media/use_rsa_tool_08.png)

5. Per verificare se le scorte disponibili saranno sempre maggiori di 0, modificare il valore del campo **Valore** da **411** a **0** e il valore del campo **Operatore** dal segno uguale (**=**) al segno maggiore di (**\>**).

    ![Valori dei campi Valore e Operatore modificati](./media/use_rsa_tool_09.png)

6. Salvare e chiudere il file di parametri di Excel.
7. Selezionare **Carica** per salvare le modifiche apportate al file di parametri di Excel in Azure DevOps.

A questo punto, se il valore del campo **Totale disponibile** per l'articolo specificato nelle scorte è maggiore di 0 (zero), i test avranno esito positivo, indipendentemente dal valore delle scorte disponibili effettivo.

### <a name="generator-logs"></a>Registri di generatori

Questa funzionalità crea una cartella contenente i registri dei test case eseguiti.

- Per utilizzare questa funzionalità, aprire il file **Microsoft.Dynamics.RegressionSuite.WindowsApp.exe.config** nella cartella di installazione di RSAT (ad esempio **C:\\Programmi (x86)\\Regression Suite Automation Tool**) e modificare il valore dell'elemento seguente da **false** a **true**.

    ```
    <add key="LogGeneration" value="false" />
    ```

Dopo l'esecuzione dei test case, è possibile trovare i file di registro in **C:\\Utenti\\\<Nome utente\>\\AppData\\Roaming\\regressionTool\\generatorLogs**.

![Cartella GeneratorLogs](./media/use_rsa_tool_10.png)

> [!NOTE]
> Se dei test case erano presenti prima di modificare il valore nel file .config, i registri non verranno generati per quei test case fino a che non si generano nuovi file di esecuzione di test.
> 
> ![Comando Genera solo file di esecuzione test nel menu Nuovo](./media/use_rsa_tool_11.png)

### <a name="snapshot"></a>Snapshot

Questa funzionalità consente di acquisire schermate dei passaggi eseguiti durante la registrazione attività.

- Per utilizzare questa funzionalità, aprire il file **Microsoft.Dynamics.RegressionSuite.WindowsApp.exe.config** nella cartella di installazione di RSAT (ad esempio **C:\\Programmi (x86)\\Regression Suite Automation Tool**) e modificare il valore dell'elemento seguente da **false** a **true**.

    ```
    <add key="VerboseSnapshotsEnabled" value="false" />
    ```

In **C:\\Utenti\\\<Nome utente\>\\AppData\\Roaming\\regressionTool\\playback** viene creata una cartella distinta per ogni test case eseguito.

![Cartella degli snapshot per un test case](./media/use_rsa_tool_12.png)

In ognuna di queste cartelle, è possibile trovare gli snapshot dei passaggi eseguiti durante l'esecuzione di test case.

![File di snapshot](./media/use_rsa_tool_13.png)

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

![Flusso dello scenario demo](./media/use_rsa_tool_14.png)

Nella figura seguente sono illustrati i processi aziendali di questo scenario in RSAT.

![Processi aziendali per lo scenario demo](./media/use_rsa_tool_15.png)

## <a name="strategy--key-learning"></a>Strategia - Suggerimenti chiave

### <a name="data"></a>Dati

- Assicurarsi di disporre di volumi di dati rappresentativi (una copia dei dati della configurazione prodotto/Golden oltre ai dati migrati).
- Quando si generano nuovi dati tramite Registrazione attività, creare nomi di test che non saranno in conflitto con i nomi esistenti (ad esempio, utilizzare un prefisso come **RSATxxx**).
- Utilizzare il ripristino temporizzato di Azure per eseguire di nuovo i test in ambienti non di livello 1.
- Sebbene sia possibile utilizzare le funzioni **RANDOM** e **NOW** di Excel per generare una combinazione univoca, questa operazione risulta parecchio complessa. Ecco un esempio.

    ```
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

### <a name="command-line"></a>Riga di comando

RSAT può essere chiamato da una finestra **Prompt dei comandi**.

> [!NOTE]
> Verificare che la variabile di ambiente **TestRoot** sia impostata sul percorso di installazione di RSAT. (in Microsoft Windows, aprire **Pannello di controllo**, selezionare **Sistema e sicurezza \> Sistema \> Impostazioni di sistema avanzate** e quindi **Variabili di ambiente**).

1. Aprire una finestra **Prompt dei comandi** come amministratore.
2. Eseguire lo strumento dalla directory di installazione.

    ```
    cd "c:\Program Files (x86)\Regression Suite Automation Tool\"
    ```

3. Elencare tutti i comandi.

    ```
    C:\Program Files (x86)\Regression Suite Automation Tool>Microsoft.Dynamics.RegressionSuite.ConsoleApp.exe help

    Usage:
        Microsoft.Dynamics.RegressionSuite.ConsoleApp.exe command
        or
        Microsoft.Dynamics.RegressionSuite.ConsoleApp.exe /settings "C:\Path to\file.settings" command

    Available commands:
        list
        listtestsuite suite_name
        download test_case_id output_dir
        generate test_case_id output_dir
        generatederived parent_test_case_id test_plan_id test_suite_id
        generatetestonly test_case_id output_dir
        edit excel_file
        playback excel_file
        playbackmany excel_file1 [excel_file2 [.. excel_fileN]]
        playbackbyid test_case_id1 [test_case_id2 [.. test_case_idN]]
        playbacksuite suite_name
        clear
        help
        about
        quit
    ```

### <a name="windows-powershell-examples"></a>Esempi di Windows PowerShell

#### <a name="run-a-test-case-in-a-loop"></a>Eseguire un test case in un ciclo

Si ha uno script di test che crea un nuovo cliente. Tramite lo script, questo test case può essere eseguito in un ciclo randomizzando i seguenti dati prima dell'esecuzione di ogni iterazione:

- ID cliente
- Nome cliente
- Indirizzo cliente

L'ID cliente sarà in formato *ATCUS\<numero\>*, dove \<numero\> è un valore compreso tra **000000001** e **999999999**.

Nel seguente esempio viene utilizzato un parametro **start** per definire il primo numero utilizzato. Un secondo parametro, **nr**, viene utilizzato per definire il numero di clienti che devono essere creati. Per ogni iterazione, i parametri nel file di parametri di Excel vengono modificati utilizzando una funzione UpdateCustomer. La riga di comando di RSAT viene quindi richiamata in una funzione RunTestCase.

Aprire Microsoft Windows PowerShell Integrated Scripting Environment (ISE) in modalità amministratore e incollare il seguente codice nella finestra denominata **Untitled1.ps1**.

```
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
$excelFilename = "full path to excel file parameter file"
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

```
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
