---
title: Designer formula nella creazione di report elettronici
description: "In questo argomento viene illustrato come utilizzare designer formula nei report elettronici (ER). Quando si progetta un formato di un documento elettronico specifico in ER, è possibile utilizzare le formule del tipo di Microsoft Excel per la trasformazione dei dati in modo da soddisfare i requisiti per la compilazione e la formattazione del documento. I diversi tipi di diritti sono supportati di testo, la data e l&quot;ora, logico matematico, informazioni, tipo di dati conversione e l&quot;altro (funzioni specifiche del dominio business)."
author: kfend
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 388b6398488e6f316c1ec07a00182e81c1dc8d08
ms.openlocfilehash: ac8d6c064ca826cc1c2fed07578ca9ce0c66ef66
ms.lasthandoff: 03/31/2017


---

# <a name="formula-designer-in-electronic-reporting"></a>Designer formula nella creazione di report elettronici

In questo argomento viene illustrato come utilizzare designer formula nei report elettronici (ER). Quando si progetta un formato di un documento elettronico specifico in ER, è possibile utilizzare le formule del tipo di Microsoft Excel per la trasformazione dei dati in modo da soddisfare i requisiti per la compilazione e la formattazione del documento. I diversi tipi di diritti sono supportati di testo, la data e l'ora, logico matematico, informazioni, tipo di dati conversione e l'altro (funzioni specifiche del dominio business).

<a name="formula-designer-overview"></a>Panoramica su Designer formula
-------------------------

La creazione di report elettronici (ER) supporta Designer formula. Di conseguenza, in fase di progettazione, è possibile configurare le espressioni che possono essere utilizzate per le seguenti attività in fase di esecuzione:

-   Trasformazione dei dati ricevuti da un database Microsoft Dynamics 365 for Operations e che devono essere inseriti in un modello dati ER progettato per fungere da origine dati per i formati ER (filtro, raggruppamento, conversioni dei tipi di dati e così via).
-   Formattazione dei dati che devono essere inviati a un documento generato elettronicamente secondo il layout e le condizioni di uno specifico formato ER (in base alle impostazioni cultura o la lingua richiesta, la codifica e così via).
-   Controllo del processo di generazione dei documenti elettronici (abilitazione/disabilitazione di determinati elementi di formato, dipendenza dall'elaborazione dei dati, interruzione della creazione del documento, visualizzazione di messaggi per gli utenti finali e così via).

La pagina Designer formula può essere aperta quando si esegue una delle seguenti operazioni:

-   Associazione di articoli di origini dati a componenti del modello dati.
-   Associazione di articoli di origini dati a componenti del formato.
-   Gestione completa dei campi calcolati come parte delle origini dati.
-   Definizione delle condizioni di visibilità per i parametri di input utente.
-   Progettazione delle trasformazioni di un formato.
-   Definizione delle condizioni di abilitazione per i componenti del formato.
-   Definizione dei nomi di file per i componenti FILE del formato.
-   Definizione delle condizioni per le convalide di controllo dei processi.
-   Definizione del testo del messaggio per le convalide di controllo dei processi.

## <a name="designing-er-formulas"></a>Progettazione di formule ER
### <a name="data-binding"></a>Associazione dati

Il Designer formula ER può essere utilizzato per definire un'espressione che trasforma i dati ricevuti da origini dati, in modo che i dati possono essere inseriti nel consumer di dati in fase di esecuzione:

-   Da origini dati di Dynamics 365 for Operations e dai parametri di runtime a un modello dati ER.
-   Da un modello dati ER a un formato ER.
-   Da origini dati di Dynamics 365 for Operations e dai parametri di runtime a un formato ER.

La figura seguente mostra la progettazione di un'espressione di questo tipo. In questo esempio, l'espressione restituisce il valore del campo **Intrastat.AmountMST** della tabella **Intrastat** di Dynamics 365 for Operations, dopo che il valore è stato arrotondato a due posizioni decimali. [immagine-espressione- associazione![(]. /media/picture-expression-binding.jpg)](. /media/picture-expression-binding.jpg) La seguente figura seguente viene illustrato come un'espressione di questo tipo può essere utilizzata. In questo esempio, il risultato dell'espressione pianificata ** Il valore Transaction.InvoicedAmount ** la parte ** modello di reporting VAT ** del modello dati. ![[] (picture-expression-binding2. /media/picture-expression-binding2.jpg)](. /media/picture-expression-binding2.jpg) In fase di esecuzione, la formula pianificata, ** ROTONDA (Intrastat.AmountMST, 2), arrotonderà ** il valore di ** AmountMST ** sistema per ciascun record Intrastat ** ** della tabella a due cifre decimali e Il valore viene inserito il valore di arrotondamento ** Transaction.InvoicedAmount ** al componente ** reporting VAT ** del modello dati.

### <a name="data-formatting"></a>Formattazione di dati

Il Designer formula ER può essere utilizzato per definire un'espressione che formatta i dati ricevuti da origini dati, in modo che i dati possono essere inviati come parte del documento elettronico generato. Se la formattazione deve essere applicata come regola tipica da riutilizzare per un formato, è possibile introdurre tale formattazione una volta in una configurazione di formato come trasformazione denominata con un'espressione di formattazione. Successivamente questa trasformazione denominata può essere collegata a molti componenti di formato il cui output deve essere formattato in base all'espressione creata. La figura seguente mostra la progettazione di una trasformazione di questo tipo. In questo esempio, la trasformazione **TrimmedString** accetta i dati in ingresso del tipo di dati **String** e tronca spazi iniziali e finali quando restituisce il valore stringa. [immagine-trasformazione- progettazione![(]. /media/picture-transformation-design.jpg)](. /media/picture-transformation-design.jpg) La figura seguente viene illustrato come una trasformazione di questo tipo può essere utilizzata. In questo esempio, più componenti di formato che inviano testo come output al documento elettronico generato in fase di esecuzione fanno riferimento alla trasformazione **TrimmedString** per nome. [immagine-trasformazione- utilizzo![(]. /media/picture-transformation-usage.jpg)](. /media/picture-transformation-usage.jpg) Quando i componenti di formato si riferiscono ** TrimmedString ** alla trasformazione, ad esempio ** partyName ** il componente nella precedente figura) che si invia il testo come un output al documento di generazione. Il testo non include gli spazi iniziali e finali. Se una formattazione deve essere applicata singolarmente, può essere introdotta come singola espressione di associazione di un determinato componente di formato. La figura seguente mostra un'espressione di questo tipo. In questo esempio, il componente di formato **partyType** è associato all'origine dati mediante un'espressione che converte i dati in ingresso dal campo **Model.Company.RegistrationType** nell'origine dati in testo maiuscolo e invia il testo come output al documento elettronico. [immagine-associazione-con- formula![(]. /media/picture-binding-with-formula.jpg)](. /media/picture-binding-with-formula.jpg)

### <a name="process-flow-control"></a>Controllo del flusso del processo

Designer formula ER può essere utilizzato per definire le espressioni che controllano il flusso del processo di generazione dei documenti. È possibile:

-   Definire le condizioni che determinano quando il processo di creazione di un documento deve essere arrestato.
-   Specificare le espressioni che creano messaggi per l'utente finale sui processi arrestati o che generano i messaggi del registro di esecuzione sul proseguimento del processo di creazione del report.
-   Specificare i nomi file dei documenti generati e controllare le condizioni della relativa creazione.

Ogni regola del controllo del flusso del processo è progettata come singola convalida. La figura seguente mostra una convalida di questo tipo. Ecco una spiegazione della configurazione in questo esempio:

-   La convalida viene valutata quando il nodo **INSTAT** viene creato nel file XML di creazione.
-   Se l'elenco delle transazioni è vuoto, la convalida interrompe il processo di esecuzione restituisce **FALSE**.
-   La convalida restituisce un messaggio di errore che include il testo dell'etichetta SYS70894 nella lingua preferita dell'utente.

[immagine- convalida![(]. /media/picture-validation.jpg)](. /media/picture-validation.jpg) Il Designer formula di ER consente inoltre di specificare un nome per un documento elettronico di generazione e di controllare il processo di creazione del file. La figura seguente mostra la progettazione di un controllo del flusso di processo di questo tipo. Ecco una spiegazione della configurazione in questo esempio:

-   L'elenco di record dell'origine dati **model.Intrastat** è suddiviso in batch, ciascuno dei quali contiene fino a 1000 record.
-   L'output crea un file ZIP contenente un file in formato XML per ogni batch creato.
-   Un'espressione restituisce un nome file per la generazione dei documenti elettronici concatenando il nome file e l'estensione di file. Per il secondo batch e tutti i batch successivi, il nome file contiene l'ID batch come suffisso.
-   Un'espressione abilita (restituendo **TRUE**) il processo di creazione di un file solo per i batch che contengono almeno un record.

[immagine-file- control![(]. /media/picture-file-control.jpg)](. /media/picture-file-control.jpg)

### <a name="basic-syntax"></a>Sintassi di base

Le espressioni ER possono contenere qualsiasi o tutti i seguenti elementi:

-   Costanti
-   Operatori
-   Riferimenti
-   Percorsi
-   Funzioni

#### <a name="constants"></a>Costanti

È possibile utilizzare testo e costanti numeriche (valori che non vengono calcolati) nella progettazione delle espressioni. Ad esempio, l'espressione ** VALORE ("100") + 20 ** utilizzare la costante numerica 20 e la costante" 100" in formato di stringa e restituisce il valore numerico ** ** 120. Le sequenze di escape sono supportate in Designer formula ER e quindi è possibile specificare la stringa dell'espressione che deve essere gestita diversamente. Ad esempio, l'espressione **"Leo Tolstoj ""Guerra e pace"" Volume 1"** restituisce la stringa di testo **Leo Tolstoj "Guerra e pace" Volume 1**.

#### <a name="operators"></a>Operatori

La seguente tabella mostra agli operatori aritmetici che è possibile utilizzare per eseguire le operazioni matematiche di base, ad esempio addizione, sottrazione, divisione e moltiplicazione.

| Operatore | Significato              | Esempio |
|----------|----------------------|---------|
| +        | Addizione             | 1+2     |
| -        | Sottrazione | 5-2 -1  |
| \*       | Moltiplicazione       | 7\*8    |
| /        | Divisione             | 9/3     |

Nella seguente tabella vengono visualizzati gli operatori di confronto che vengono supportati e che è possibile utilizzare per confrontare due valori.

| Operatore | Significato                  | Esempio    |
|----------|--------------------------|------------|
| =        | Uguale                    | X=Y        |
| &gt;     | Maggiore di             | DI X-Y&gt;     |
| &lt;     | Minore di                | DI X-Y&lt;     |
| &gt;=    | Uguale o maggiore di | X=Y&gt;    |
| &lt;=    | Uguale o minore di    | X=Y&lt;    |
| &lt;&gt; | Diverso da             | X&lt;&gt;Y |

Inoltre, è possibile utilizzare una e commerciale (&) come operatore di concatenazione del testo per unire, o concatenare, una o più stringhe di testo in un testo unico.

| Operatore | Significato     | Esempio                                        |
|----------|-------------|------------------------------------------------|
| &        | Concatena | "Niente da stampare" & ": " & "nessun record trovato" |

#### <a name="operator-precedence"></a>Precedenza di operatore

L'ordine in cui le parti di un'espressione composta vengono valutate è importante. Ad esempio, il risultato dell'espressione ** 1 + 4/2, ** varia a seconda che l'operazione di addizione o l'operazione di divisione viene eseguita per primi. È possibile utilizzare le parentesi per definire in modo esplicito come un'espressione viene valutata. Ad esempio, per indicare che l'operazione di addizione deve essere eseguita per prima, è possibile modificare l'espressione precedente in **(1 + 4) / 2**. Se l'ordine delle operazioni che devono essere eseguite in un'espressione non è definito in modo esplicito, l'ordine è basato sulla precedenza predefinita assegnata agli operatori supportati. Nelle seguenti tabelle vengono visualizzati gli operatori e la precedenza assegnata a ciascuno. Gli operatori con precedenza più alta (ad esempio, 7) vengono valutati prima degli operatori con precedenza inferiore (ad esempio, 1).

| Precedenza | Operatori      | Sintassi                                                   |
|------------|----------------|----------------------------------------------------------|
| 7          | Raggruppamento       | ( … )                                                    |
| 6          | Accesso a membro  | … . …                                                    |
| 5          | Chiamata di funzione  | … ( … )                                                  |
| 4          | Moltiplicativo | … \* … … / …                                             |
| 3          | Addizione       | … + … … - …                                              |
| 2          | Confronto     | … &lt; … … &lt;= … … =&gt; … … &gt; … … = … … &lt;&gt; … |
| 1          | Separazione     | … , …                                                    |

Gli operatori sulla stessa riga hanno uguale precedenza. Se un'espressione include più di uno di questi operatori, l'espressione viene valutata da sinistra a destra. Ad esempio, l'espressione ** \* 1 + 6/2 3 &gt; 5 ** resi ** ** riga. Si consiglia di utilizzare le parentesi per indicare in modo esplicito l'ordine desiderato della valutazione delle espressioni, per rendere le espressioni più facili da leggere e gestire.

#### <a name="references"></a>Riferimenti

Tutte le origini dati del componente ER corrente (un modello o un formato) disponibili nella progettazione di un'espressione possono essere utilizzate come riferimenti denominati. Ad esempio, il modello dati ER corrente contiene l'origine dati **ReportingDate** che restituisce un valore del tipo di dati **DATETIME**. Per formattare correttamente il valore del documento di generazione, è possibile fare riferimento all'origine dati nell'espressione nel seguente modo: ** DATETIMEFORMAT (ReportingDate dd-MILLIMETRO- ",") aaaa ** tutti i caratteri del nome un'origine dati di riferimento e non rappresentano una lettera dell'alfabeto deve essere preceduto dalle virgolette singole ('). Se il nome di un'origine dati di riferimento e contiene almeno un simbolo che non rappresenta una lettera dell'alfabeto, ad esempio segni di punteggiatura o altri simboli scritti), il nome deve essere racchiuso le singole virgolette. Di seguito sono riportati alcuni esempi.

-   L'origine dati **Today's date & time** deve essere utilizzata in un'espressione ER come segue: **'Today''s date & time'**
-   Al metodo **name()** dell'origine dati **Customers** deve essere fatto riferimento in un'espressione ER come segue: **Customers.'name()'**

#### <a name="path"></a>Percorso

Quando un'espressione fa riferimento a un'origine dati strutturata, è possibile utilizzare la definizione di percorso per selezionare un elemento primitivo specifico di tale origine dati. Un carattere di punto (.) viene utilizzato per separare i singoli elementi di origine dati strutturata. Ad esempio, il modello dati ER corrente contiene l'origine dati **InvoiceTransactions** che restituisce un elenco di record. La struttura di record** InvoiceTransactions** contiene i campi **AmountDebit** e **AmountCredit** che restituiscono valori numerici. Pertanto è possibile progettare la seguente espressione per il calcolo dell'importo fatturato: **InvoiceTransactions.AmountDebit - InvoiceTransactions.AmountCredit**

#### <a name="functions"></a>Funzioni

Nella sezione successiva vengono descritte le funzioni che possono essere utilizzate in espressioni ER. Tutte le origini dati del contesto dell'espressione (modello dati o formato ER corrente) nonché le costanti possono essere utilizzate come parametri di funzioni di chiamata, secondo l'elenco degli argomenti delle funzioni di chiamata. Ad esempio, il modello dati ER corrente contiene l'origine dati **InvoiceTransactions** che restituisce un elenco di record. La struttura di record** InvoiceTransactions** contiene i campi **AmountDebit** e **AmountCredit** che restituiscono valori numerici. Pertanto, per calcolare l'importo fatturato è possibile progettare la seguente espressione che usa la funzione di arrotondamento ER integrata: **ROUND (InvoiceTransactions.AmountDebit - InvoiceTransactions.AmountCredit, 2)**

## <a name="supported-functions"></a>Funzioni supportate
Le seguenti tabelle descrivono le funzioni di manipolazione dei dati che è possibile utilizzare per progettare i modelli di dati ER e report ER. L'elenco di funzioni non è fisso e può essere ampliato dagli sviluppatori. Per vedere l'elenco delle funzioni che è possibile utilizzare, accedere al riquadro delle funzioni in Designer formula ER.

### <a name="date-and-time-functions"></a>Funzioni di data e ora

| Funzione                                   | Descrizione                                                                                                                                                                                                                                                                                                                                                      | Esempio                                                                                                                                                                                                                                                                                               |
|--------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ADDDAYS (data/ora, giorni)                   | Aggiunge il numero di giorni specificato al valore data/ora specificato.                                                                                                                                                                                                                                                                                                | **ADDDAYS (NOW(), 7)** restituisce la data e l'ora di sette giorni in futuro.                                                                                                                                                                                                                            |
| DATETODATETIME (data)                      | Converte il valore di data specificato in un valore data/ora.                                                                                                                                                                                                                                                                                                            | ** DATETODATETIME (CompInfo. "getCurrentDate (") ** resi Dynamics corrente 365 per la data della sessione di operazioni, 12/24/2015, ad esempio ** 12/24/2015 di 12:00: 00 DI ** SERVICES. In questo esempio, **CompInfo** è l'origine dati ER del tipo **Dynamics 365 for Operations/Tabella** che fa riferimento alla tabella CompanyInfo. |
| NOW ()                                     | Restituisce la data e l'ora del server applicazioni corrente di Dynamics 365 for Operations come valore di data/ora.                                                                                                                                                                                                                                                             |                                                                                                                                                                                                                                                                                                       |
| TODAY ()                                   | Restituisce la data del server applicazioni corrente di Dynamics 365 for Operations come valore di data.                                                                                                                                                                                                                                                                          |                                                                                                                                                                                                                                                                                                       |
| NULLDATE ()                                | Restituisce un valore di data **null**.                                                                                                                                                                                                                                                                                                                                    |                                                                                                                                                                                                                                                                                                       |
| NULLDATETIME ()                            | Restituisce un valore di data/ora **null**.                                                                                                                                                                                                                                                                                                                                |                                                                                                                                                                                                                                                                                                       |
| DATETIMEFORMAT (data/ora, formato)          | Converte il valore specificato di data/ora in una stringa nel formato specificato. (Per informazioni sui formati supportati, vedere [standard](https://msdn.microsoft.com/en-us/library/az4se3k1(v=vs.110).aspx) e [personalizzato](https://msdn.microsoft.com/en-us/library/8kb3ddd4(v=vs.110).aspx)).                                                                        | **DATETIMEFORMAT (NOW(), "gg-MM-aaaa")** restituisce la data del server applicazioni corrente di Dynamics 365 for Operations, 12/24/2015, come **"24-12-2015"**, in base al formato personalizzato specificato.                                                                                                          |
| DATETIMEFORMAT (data/ora, impostazioni cultura) | Converte il valore di data/ora specificato in una stringa nel formato e nelle [impostazioni cultura](https://msdn.microsoft.com/en-us/goglobal/bb896001.aspx) specificati. (Per informazioni sui formati supportati, vedere [standard](https://msdn.microsoft.com/en-us/library/az4se3k1(v=vs.110).aspx) e [personalizzato](https://msdn.microsoft.com/en-us/library/8kb3ddd4(v=vs.110).aspx)). | **DATETIMEFORMAT (NOW(), "d", "de")** restituisce la data del server applicazioni corrente di Dynamics 365 for Operations, 12/24/2015, come **"24.12.2015"**, in base alle impostazioni cultura tedesche selezionate.                                                                                                             |
| SESSIONTODAY ()                            | Restituisce la data della sessione corrente di Dynamics 365 for Operations come valore di data.                                                                                                                                                                                                                                                                                      |                                                                                                                                                                                                                                                                                                       |
| SESSIONNOW ()                              | Restituisce la data e l'ora della sessione corrente di Dynamics 365 for Operations come valore di data/ora.                                                                                                                                                                                                                                                                         |                                                                                                                                                                                                                                                                                                       |
| DATEFORMAT (data, formato)                  | Restituisce una rappresentazione in formato stringa della data tramite il formato specificato.                                                                                                                                                                                                                                                                                                    | **DATEFORMAT (SESSIONTODAY (), "gg-MM-aaaa")** restituisce la data della sessione corrente di Dynamics 365 for Operations, 12/24/2015, come "**24-12-2015**" in base al formato personalizzato specificato.                                                                                                                      |
| DATEFORMAT (data, formato, impostazioni cultura)         | Convertire il valore di data specificato in una stringa nel formato e nelle [impostazioni cultura](https://msdn.microsoft.com/en-us/goglobal/bb896001.aspx) specificati. (Per informazioni sui formati supportati, vedere [standard](https://msdn.microsoft.com/en-us/library/az4se3k1(v=vs.110).aspx) e [personalizzato](https://msdn.microsoft.com/en-us/library/8kb3ddd4(v=vs.110).aspx)).     | **DATETIMEFORMAT (SESSIONNOW (), "d", "de")** restituisce la data della sessione corrente di Dynamics 365 for Operations, 12/24/2015, come **"24.12.2015"**, in base alle impostazioni cultura tedesche selezionate.                                                                                                                       |

### <a name="list-functions"></a>Funzioni di elenco

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>Funzione</th>
<th>descrizione</th>
<th>Esempio</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>SPLIT (input, lunghezza)</td>
<td>Divide la stringa di input specificata in sottostringhe, ciascuna delle quali ha lunghezza specificata. Restituisce il risultato come nuovo elenco.</td>
<td><strong>(SPACCATURA&quot;abcd&quot;, 3)</strong> restituisce un nuovo elenco è composto da due record con <strong>STRINGA</strong> un campo. Il campo del primo record contenente il testo <strong>&quot;ABC&quot;</strong> e il campo in base al record contenente il testo <strong>&quot;d&quot;</strong>.</td>
</tr>
<tr class="even">
<td>SPLITLIST (elenco, numero)</td>
<td>Divide l'elenco specificato in batch, ciascuno dei quali contiene il numero specificato di record. Restituisce il risultato come nuovo elenco di batch contenente i seguenti elementi:
<ul>
<li>Batch come normali elenchi (componente <strong>Value</strong>)</li>
<li>Il numero batch corrente (componente <strong>BatchNumber</strong>)</li>
</ul></td>
<td>Nel seguente esempio, l'origine dati <strong>Lines</strong> viene creata come un elenco di tre record, che è suddiviso in batch, ciascuno dei quali contiene fino a due record. <a href="./media/picture-splitlist-datasource.jpg"><img src="./media/picture-splitlist-datasource.jpg" alt="Data source that is divided into batches" class="alignnone wp-image-290681 size-full" width="397" height="136" /></a> nel campo viene visualizzato il layout pianificata di formato, dove le associazioni <strong>Righe</strong> all'origine dati vengono create per generare l'output in formato XML che invia i singoli nodi per ogni batch e i record. <a href="./media/picture-splitlist-format.jpg"><img src="./media/picture-splitlist-format.jpg" alt="Format layout that has bindings to a data source" class="alignnone wp-image-290691 size-full" width="374" height="161" /></a> il seguente è il risultato di esecuzione del formato previsto. <a href="./media/picture-splitlist-result.jpg"><img src="./media/picture-splitlist-result.jpg" alt="Result of running the format" class="alignnone wp-image-290701 size-full" width="358" height="191" /></a></td>
</tr>
<tr class="odd">
<td>LIST (record 1 [, record 2, ...])</td>
<td>Restituisce un nuovo elenco creato dagli argomenti specificati.</td>
<td><strong>LIST (model.MainData, model.OtherData)</strong> restituisce un record vuoto, dove l'elenco di campi contiene tutti i campi degli elenchi di record <strong>MainData</strong> e <strong>OtherData</strong>.</td>
</tr>
<tr class="even">
<td>LISTJOIN (elenco 1, elenco 2, ...)</td>
<td>Restituisce un elenco collegato dagli elenchi di argomenti specificati.</td>
<td><strong>LISTJOIN ((SPACCHI&quot;ABC&quot;, 1), SPACCATURA (&quot;definizione&quot;, 1))</strong> restituisce l'elenco dei record, in cui un campo <strong>STRINGA</strong> Tipo di dati include singole lettere.</td>
</tr>
<tr class="odd">
<td>ISEMPTY (elenco)</td>
<td>Restituisce <strong>TRUE</strong> se l'elenco specificato non contiene elementi. In caso contrario, restituisce <strong>FALSE</strong>.</td>
<td></td>
</tr>
<tr class="even">
<td>EMPTYLIST (elenco)</td>
<td>Restituisce un elenco vuoto utilizzando l'elenco specificato come origine della struttura elenco.</td>
<td><strong>EMPTYLIST ((SPACCHI&quot;ABC&quot;, 1))</strong> restituisce un nuovo vuote l'elenco contenente la stessa struttura dell'elenco che viene <strong>SPACCATURA</strong> restituito dalla funzione.</td>
</tr>
<tr class="odd">
<td>FIRST (elenco)</td>
<td>Restituisce il primo record dell'elenco specificato, se il record non è vuoto. In caso contrario, genera un'eccezione.</td>
<td></td>
</tr>
<tr class="even">
<td>FIRSTORNULL (elenco)</td>
<td>Restituisce il primo record dell'elenco specificato, se il record non è vuoto. In caso contrario, restituisce un record<strong>null</strong>.</td>
<td></td>
</tr>
<tr class="odd">
<td>LISTOFFIRSTITEM (elenco)</td>
<td>Restituisce un elenco che contiene solo il primo elemento di un elenco specifico.</td>
<td></td>
</tr>
<tr class="even">
<td>ALLITEMS (percorso)</td>
<td>Restituisce un nuovo elenco bidimensionale che rappresenta tutti gli elementi che corrispondono a un percorso specifico. Il percorso deve essere definito come percorso di origine dati valido in un elemento di origine dati di un tipo di dati elenco di record. Il percorso degli elementi di dati, stringa, data e così via genera un errore in fase di progettazione nel generatore di espressioni ER.</td>
<td>Se si <strong>(SPACCATURA&quot;abcdef&quot;, 2)</strong> immette come origine dati, <strong>CONTEGGIO (ALLITEMS (DS.Value)</strong> reso (DS).</td>
</tr>
<tr class="odd">
<td>ORDERBY (elenco [, espressione 1, espressione 2, …])</td>
<td>Restituisce l'elenco specificato, ordinato in base agli argomenti specificati che possono essere definiti come espressioni.</td>
<td>Quando <strong>Vendor </strong>viene configurato come origine dati ER che fa riferimento alla tabella VendTable,<strong> ORDERBY (Vendors, Vendors.'name()')</strong> restituisce l'elenco dei fornitori ordinato per nome in ordine crescente.</td>
</tr>
<tr class="even">
<td>REVERSE (elenco)</td>
<td>Restituisce l'elenco specificato in ordine inverso.</td>
<td>Quando <strong>Vendor </strong>viene configurato come origine dati ER che fa riferimento alla tabella VendTable, <strong>REVERSE (ORDERBY (Vendors, Vendors.'name()')) )</strong> restituisce l'elenco dei fornitori ordinato per nome in ordine decrescente.</td>
</tr>
<tr class="odd">
<td>WHERE (elenco, condizione)</td>
<td>Restituisce l'elenco specificato, che viene filtrato in base alla condizione specificata. Diversamente dalla funzione <strong>FILTRO</strong>, la condizione specificata viene applicata all'elenco nella memoria.</td>
<td>Quando <strong>Fornitore</strong> viene configurato come origine dati di ER che fa riferimento alla tabella di VendTable, <strong>DOVE (fornitori, Vendors.VendGroup = &quot;40&quot;)</strong> viene restituito un elenco di fornitori a cui appartiene al gruppo 40 fornitori.</td>
</tr>
<tr class="even">
<td>ENUMERATE (elenco)</td>
<td>Restituisce un nuovo elenco corrispondente ai record enumerati dell'elenco specificato e che espone i seguenti elementi:
<ul>
<li>Record dell'elenco specificati come normali elenchi (componente <strong>Value</strong>)</li>
<li>L'indice del record corrente (componente <strong>Number</strong>)</li>
</ul></td>
<td>Nel seguente esempio, l'origine dati <strong>Enumerated</strong> viene creata come elenco enumerato di record fornitori dall'origine dati <strong>Vendors</strong> che fa riferimento alla tabella <strong>VendTable</strong>. <a href="./media/picture-enumerate-datasource.jpg"><img src="./media/picture-enumerate-datasource.jpg" alt="Enumerated data source" class="alignnone wp-image-290711 size-full" width="387" height="136" /></a> in questo campo è il formato, in cui le associazioni di dati vengono create per generare l'output in formato XML che invia i singoli fornitori come nodi enumerati. <a href="./media/picture-enumerate-format.jpg"><img src="./media/picture-enumerate-format.jpg" alt="Format that has data bindings" class="alignnone wp-image-290721 size-full" width="414" height="138" /></a> il risultato dell'esecuzione del formato previsto. <a href="./media/picture-enumerate-result.jpg"><img src="./media/picture-enumerate-result.jpg" alt="Result of running the format" class="alignnone wp-image-290731 size-full" width="567" height="176" /></a></td>
</tr>
<tr class="odd">
<td>COUNT (elenco)</td>
<td>Restituisce il numero di record nell'elenco specificato, se l'elenco non è vuoto. In caso contrario, restituisce <strong>0</strong> (zero).</td>
<td><strong>CONTEGGIO ((SPACCHI&quot;abcd&quot;, 3))</strong> successivo <strong>2</strong>, poiché la funzione di creare un elenco è composto da due record.</td>
</tr>
<tr class="even">
<td>LISTOFFIELDS (percorso)</td>
<td>Restituisce un elenco di record creato da un argomento di uno dei seguenti tipi:
<ul>
<li>Enumerazione modello</li>
<li>Enumerazione formato</li>
<li>Contenitore</li>
</ul>
Nell'elenco creato sono presenti i record con i seguenti campi:
<ul>
<li>Nome</li>
<li>Etichetta</li>
<li>descrizione</li>
</ul>
I campi Descrizione ed Etichetta restituiscono valori in fase esecuzione in base alle impostazioni di lingua del formato.</td>
<td>Nel seguente esempio viene illustrata l'enumerazione introdotta in un modello dati. <a href="./media/ger-listoffields-function-model-enumeration.png"><img src="./media/ger-listoffields-function-model-enumeration-e1474545790761.png" alt="GER LISTOFFIELDS function - model enumeration" class="alignnone wp-image-1203943 size-full" width="514" height="155" /></a>le seguenti in esempio:
<ul>
<li>L'enumerazione di modello inserita in un report come origine dei dati.</li>
<li>L'espressione ER progettata per l'utilizzo dell'enumerazione di modello come parametro di questa funzione.</li>
<li>L'origine dati del tipo di elenco record inserito in un report mediante l'espressione ER creata.</li>
</ul>

<a href="./media/ger-listoffields-function-in-format-expression.png"><img src="./media/ger-listoffields-function-in-format-expression-e1474546110395.png" alt="GER LISTOFFIELDS function - in format expression" class="alignnone wp-image-1204033 size-full" width="549" height="318" /></a> il seguente esempio viene illustrato gli elementi di ER limitati all'origine dati di tipo elenco record creato utilizzando la funzione di LISTOFFIELDS.<a href="./media/ger-listoffields-function-format-design.png"><img src="./media/ger-listoffields-function-format-design.png" alt="GER LISTOFFIELDS function - format design" class="alignnone size-full wp-image-1204043" width="466" height="221" /></a>il risultato dell'esecuzione pianificata di formato.<a href="./media/ger-listoffields-function-format-output.png"><img src="./media/ger-listoffields-function-format-output.png" alt="GER LISTOFFIELDS function - format output" class="alignnone size-full wp-image-1204053" width="585" height="158" /></a><strong>Nota:</strong> nel testo tradotto per le etichette e le descrizioni viene immessa all'output di ER in conformità alle impostazioni del linguaggio configurate per elementi di formato di FILE e di CARTELLA padre.</td>
</tr>
<tr class="odd">
<td>STRINGJOIN (elenco, nome del campo, delimitatore)</td>
<td>Restituisce la stringa dei valori concatenati di un campo da un elenco separato da un delimitatore selezionato.</td>
<td>Se è stato immesso SPLIT("abc" , 1) come origine dati DS, l'espressione STRINGJOIN (DS, DS.Value, ":") restituisce "a:b:c"</td>
</tr>
<tr class="even">
<td>SPLITLISTBYLIMIT (elenco, valore limite, origine limite)</td>
<td>Divide l'elenco specificato in nuovo elenco di sottoelenchi e restituisce il risultato nel contenuto dell'elenco di record. Il parametro di valore limite specifica il valore del limite per dividere l'elenco di origine. Il parametro di origine limite specifica il passaggio secondo cui viene incrementata la somma totale. Il limite non è applicato a un singolo articolo dell'elenco specificato quando l'origine limite supera il limite definito.</td>
<td>Nel seguente esempio viene illustrato il formato di esempio utilizzando le origini dati. <a href="./media/ger-splitlistbylimit-format.png"><img src="./media/ger-splitlistbylimit-format.png" alt="GER SPLITLISTBYLIMIT - format" class="alignnone size-full wp-image-1204063" width="396" height="195" /></a><a href="./media/ger-splitlistbylimit-datasources.png"><img src="./media/ger-splitlistbylimit-datasources.png" alt="GER SPLITLISTBYLIMIT - datasources" class="alignnone size-full wp-image-1204073" width="320" height="208" /></a>l'esecuzione di risultato che invia piano l'elenco degli articoli di consumo.<a href="./media/ger-splitlistbylimit-output.png"><img src="./media/ger-splitlistbylimit-output.png" alt="GER SPLITLISTBYLIMIT - output" class="alignnone size-full wp-image-1204083" width="462" height="204" /></a>il seguente esempio viene visualizzato lo stesso formato che è stato rettificato per inviare l'elenco degli articoli di consumo in batch a un lotto deve includere le voci doganali al peso totale non deve superare il limite di 9.<a href="./media/ger-splitlistbylimit-format-1.png"><img src="./media/ger-splitlistbylimit-format-1.png" alt="GER SPLITLISTBYLIMIT - format 1" class="alignnone size-full wp-image-1204103" width="466" height="438" /></a><a href="./media/ger-splitlistbylimit-datasources-1.png"><img src="./media/ger-splitlistbylimit-datasources-1.png" alt="GER SPLITLISTBYLIMIT - datasources 1" class="alignnone size-full wp-image-1204093" width="645" height="507" /></a>il risultato di formato rettificata. <a href="./media/ger-splitlistbylimit-output-1.png"><img src="./media/ger-splitlistbylimit-output-1.png" alt="GER SPLITLISTBYLIMIT - output 1" class="alignnone size-full wp-image-1204113" width="676" height="611" /></a><strong>Annota che:</strong> il limite non si applica solo all'elenco di origine come valore (11) per l'origine del limite (peso) supera il limite definito (9). Utilizzare la funzione <strong>WHERE</strong> o l'espressione <strong>Enabled</strong> dell'elemento formato corrispondente per ignorare (saltare) i sottoelenchi durante la generazione dei report (se necessario).</td>
</tr>
<tr class="odd">
<td>FILTER (elenco, condizione)</td>
<td>Restituisce l'elenco specificato filtrato per la condizione specificata modificando la query. Diversamente dalla funzione <strong>WHERE</strong>, la condizione specificata viene applicata a livello di database a qualsiasi origine dati ER del tipo di record tabella.</td>
<td>Il FILTRO (fornitori, Vendors.VendGroup = &quot;40&quot;) viene restituito un elenco solo i fornitori che appartengono al gruppo "40 "i fornitori quando <strong>Fornitore</strong> viene configurato come origine dati di ER che fa riferimento <strong>VendTable</strong> alla tabella</td>
</tr>
</tbody>
</table>

### <a name="logical-functions"></a>Funzioni logiche

| Funzione                                                                                | descrizione                                                                                                                                                                                                                                                                     | Esempio                                                                                                                                                                                                                                                      |
|-----------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| CASO di (espressione opzione, 1, 1 risultato \[ opzione, 2, 2 risultato...\] \[,\]risultato predefinito) | Confronta il valore specificato di espressione rispetto alle opzioni alternative specificate. Restituisce il risultato dell'opzione uguale al valore dell'espressione. In caso contrario, restituisce il risultato predefinito eventualmente immesso (l'ultimo parametro che non è preceduto da un'opzione). | **CASE( DATETIMEFORMAT( NOW(), "MM"), "10", "WINTER", "11", "WINTER", "12", "WINTER", "")** restituisce la stringa **"WINTER"** quando la data della sessione corrente di Dynamics 365 for Operations è compresa tra ottobre e dicembre. In caso contrario, restituisce una stringa vuota. |
| IF (condizione, valore 1, valore 2)                                                        | Restituisce il valore specificato 1 quando viene soddisfatta la condizione data. In caso contrario, il valore restituito. 2. Se il valore 1 e il valore 2 in record o elenchi di record, il risultato sarà solo i campi disponibili in entrambi gli elenchi.                                                                     | **IF (1=2, "condizione soddisfatta", "condizione non soddisfatta")** restituisce la stringa **"condizione non soddisfatta"**.                                                                                                                                                      |
| NOT (condizione)                                                                         | Restituisce il valore logico inverso della condizione specificata.                                                                                                                                                                                                                   | **NOT (TRUE)** restituisce **FALSE**.                                                                                                                                                                                                                            |
| In 1 (condizione\[, condizione 2,...\])                                                 | Restituisce **TRUE** se *tutte *le condizioni specificate sono vere. In caso contrario, restituisce **FALSE**.                                                                                                                                                                                            | **AND (1=1, "a"="a")** restituisce **TRUE**. **AND (1=2, "a"="a")** restituisce **FALSE**.                                                                                                                                                                           |
| In alternativa (condizione 1\[, 2, condizione...\])                                                  | Restituisce **FALSE** se *tutte *le condizioni specificate sono false. Restituisce **TRUE** se *qualsiasi * condizione specificata è vera.                                                                                                                                                                 | **OR (1=2, "a"="a")** restituisce **TRUE**.                                                                                                                                                                                                                      |

### <a name="mathematical-functions"></a>Funzioni matematiche

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>Funzione</th>
<th>Descrizione</th>
<th>Esempio</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>ABS (number)</td>
<td>Restituisce il valore assoluto del numero specificato (il numero senza il relativo segno).</td>
<td><strong>ABS (-1)</strong> restituisce <strong>1</strong>.</td>
</tr>
<tr class="even">
<td>POWER (numero, potenza)</td>
<td>Restituisce il risultato dell'elevazione alla potenza specificata del numero positivo specificato.</td>
<td><strong>POWER (10, 2)</strong> restituisce <strong>100</strong>.</td>
</tr>
<tr class="odd">
<td>NUMBERVALUE (stringa, separatore decimale, separatore di raggruppamento delle cifre)</td>
<td>Converte la stringa specificata in numero. Il simbolo specificato viene utilizzato per separare l'intero e le parti frazionarie di numero decimale e separatore delle migliaia specificato verrà utilizzato.</td>
<td><strong>(NUMBERVALUE&quot;1 234,56&quot;, &quot;,&quot;, &quot; &quot;)</strong> restituisce il valore <strong>1234.56</strong>.</td>
</tr>
<tr class="even">
<td>VALUE (stringa)</td>
<td>Converte la stringa specificata in numero. Le virgole e i caratteri punto (). vengono considerati separatori decimali e un trattino iniziale (-) viene utilizzato come negativo. Genera un'eccezione se altri caratteri non numerici verranno incontrati nella stringa specificata.</td>
<td><strong>(VALORE&quot;1 234,56&quot;)</strong> getta eccezione.</td>
</tr>
<tr class="odd">
<td>ROUND (numero, decimali)</td>
<td>Restituisce il numero specificato, che viene arrotondato al numero di posizioni decimali specificato:
<ul>
<li>Se il valore di decimali specificato è maggiore di 0 (zero), il numero specificato viene arrotondato al numero di posizioni decimali specificato.</li>
<li>Se il valore di decimali specificato è 0 (zero), il numero specificato viene arrotondato all'intero più vicino.</li>
<li>Se il valore di decimali specificato è minore di 0 (zero), il numero specificato viene arrotondato a sinistra del separatore decimale.</li>
</ul></td>
<td><strong>ROUND (1200.767, 2)</strong> arrotonda a due posti decimali e restituisce <strong>1200.77</strong>. <strong>ROUND (1200.767, -3)</strong> arrotonda al più vicino multiplo di 1000 e restituisce <strong>1000</strong>.</td>
</tr>
<tr class="even">
<td>ROUNDDOWN (numero, decimali)</td>
<td>Restituisce il numero specificato, che viene arrotondato per difetto (verso lo zero) al numero di posizioni decimali specificato. <strong>Nota:</strong> Questa funzione si comporta analogamente a <strong>ROUND</strong> ma sempre per difetto.</td>
<td><strong>ROUNDDOWN (1200.767, 2)</strong> arrotonda per difetto a due posti decimali e restituisce <strong>1200.76</strong>. <strong>ROUNDDOWN (1700.767, -3)</strong> arrotonda per difetto al più vicino multiplo di 1000 e restituisce <strong>1000</strong>.</td>
</tr>
<tr class="odd">
<td>ROUNDUP (numero, decimali)</td>
<td>Restituisce il numero specificato, che viene arrotondato per eccesso (lontano da zero) al numero di posizioni decimali specificato. <strong>Nota:</strong> Questa funzione si comporta analogamente a <strong>ROUND</strong> ma sempre per eccesso.</td>
<td><strong>ROUNDUP (1200.763, 2)</strong> arrotonda per eccesso a due posti decimali e restituisce <strong>1200.77</strong>. <strong>ROUNDUP (1200.767, -3)</strong> arrotonda per eccesso al più vicino multiplo di 1000 e restituisce <strong>2000</strong>.</td>
</tr>
</tbody>
</table>

### <a name="record-functions"></a>Funzioni di record

| Funzione             | Descrizione                                                                                                                                                                                                                                     | Esempio                                                                                                                                             |
|----------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------|
| NULLCONTAINER (elenco) | Restituisce un record **null** con la stessa struttura dell'elenco di record o il record specificato. **Nota: **Questa funzione è obsoleta. Utilizzare **EMPTYRECORD** invece.                                                                                  | **NULLCONTAINER (SPLIT ("abc", 1))** restituisce un nuovo record vuoto con la stessa struttura dell'elenco restituito dalla funzione **SPLIT**. |
| EMPTYRECORD (record) | Restituisce un record **null** con la stessa struttura dell'elenco di record o il record specificato. ** Nota: ** A ** nullo ** registrare è un record in cui tutti i campi con un valore vuoto (** 0 ** \[\] zero per i numeri, una stringa vuota per le stringhe, e così via). | **EMPTYRECORD (SPLIT ("abc", 1))** restituisce un nuovo record vuoto con la stessa struttura dell'elenco restituito dalla funzione **SPLIT**.   |

### <a name="text-functions"></a>Funzioni di testo

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>Funzione</th>
<th>Descrizione</th>
<th>Esempio</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>UPPER (stringa)</td>
<td>Restituisce la stringa specificata, che viene convertita in lettere maiuscole.</td>
<td><strong>(TOMAIA&quot; esempio&quot;)</strong> resi <strong>&quot;CAMPIONE&quot;</strong>.</td>
</tr>
<tr class="even">
<td>LOWER (stringa)</td>
<td>Restituisce la stringa specificata, che viene convertita in lettere minuscole.</td>
<td><strong>ULTERIORI (scenda&quot; esempio&quot;)</strong> resi <strong>&quot; esempio&quot;</strong>.</td>
</tr>
<tr class="odd">
<td>LEFT (stringa, numero di caratteri)</td>
<td>Restituisce il numero specificato di caratteri a partire dall'inizio di una stringa specificata.</td>
<td><strong>(SINISTRA&quot; esempio&quot;, 3)</strong> resi <strong>&quot;Giorgio&quot;</strong>.</td>
</tr>
<tr class="even">
<td>RIGHT (stringa, numero di caratteri)</td>
<td>Restituisce il numero specificato di caratteri a partire dalla fine di una stringa specificata.</td>
<td><strong>(DESTRA&quot; esempio&quot;, 3)</strong> resi <strong>&quot;ple&quot;</strong>.</td>
</tr>
<tr class="odd">
<td>MID (stringa, posizione iniziale, numero di caratteri)</td>
<td>Restituisce il numero specificato di caratteri della stringa specificata a partire dalla posizione specificata.</td>
<td><strong>METÀ (DI&quot; esempio&quot;, 2, 3)</strong> resi <strong>&quot;amp&quot;</strong>.</td>
</tr>
<tr class="even">
<td>LEN (stringa)</td>
<td>Restituisce il numero di caratteri nella stringa specificata.</td>
<td><strong>(LEN&quot; esempio&quot;)</strong> successivo <strong>6</strong>.</td>
</tr>
<tr class="odd">
<td>CHAR (numero)</td>
<td>Restituisce la stringa di caratteri a cui viene fatto riferimento dal numero Unicode specificato.</td>
<td><strong>CARBONE (255)</strong> resi <strong>&quot;ÿ&quot;</strong>. <strong>Nota:</strong> la stringa restituita dipende dalla codifica selezionata nell'elemento del formato FILE padre. L'elenco delle codifiche supportate è disponibile nell'argomento <a href="https://msdn.microsoft.com/en-us/library/system.text.encoding(v=vs.110).aspx">Classe di codifica</a>.</td>
</tr>
<tr class="even">
<td>CONCATENATE (stringa 1 [, stringa 2, …])</td>
<td>Restituisce tutte le stringhe di testo specificate, che vengono unite in un'unica stringa.</td>
<td><strong>(CONCATENI&quot;ABC&quot;, &quot;definizione&quot;)</strong> resi <strong>&quot;abcdef&quot;</strong>. <strong>Nota:</strong> È possibile <strong>&quot;ABC&quot; &amp; &quot;definizione&quot;</strong> creare un'espressione anche <strong>&quot;abcdef&quot;</strong>i resi.</td>
</tr>
<tr class="odd">
<td>TRANSLATE (stringa, modello, sostituzione)</td>
<td>Restituisce la stringa specificata, in cui tutte le occorrenze dei caratteri la stringa modello specificata verranno sostituite dai caratteri alla posizione corrispondente della stringa di sostituzione specificata.</td>
<td><strong>(TRADUCA&quot;abcdef&quot;, &quot;CD&quot;, &quot;GH&quot;)</strong> sostituisce il criterio dalla <strong>&quot;GH&quot;</strong> stringa e verrà <strong>&quot;abGHef&quot;</strong>ripristinato.</td>
</tr>
<tr class="even">
<td>REPLACE (stringa, modello, sostituzione, flag espressione regolare)</td>
<td>Quando il flag espressione regolare specificato è <strong>true</strong>, restituisce la stringa specificata, che viene modificata applicando l'espressione regolare specificata come un argomento di modello per la funzione. Tale espressione viene utilizzata per individuare i caratteri che devono essere sostituiti. I caratteri dell'argomento di sostituzione specificato vengono utilizzati per sostituire i caratteri che si trovano. Quando il flag specificato espressione regolare è <strong>false</strong>, questa funzione si comporta analogamente a <strong>TRANSLATE</strong>.</td>
<td> <strong>(SOSTITUISCA&quot;+1 923 456 4971&quot;, &quot;^0-9 []&quot;, &quot;&quot;reale),</strong> applica rettificare un'espressione che consente di rimuovere tutti i simboli non numerici e verrà <strong>&quot;19234564971&quot;</strong>ripristinato. <strong>(SOSTITUISCA&quot;abcdef&quot;, &quot;CD&quot;, &quot;GH&quot;, falso)</strong> sostituisce il criterio dalla <strong>&quot;GH&quot;</strong> stringa e verrà <strong>&quot;abGHef&quot;</strong>ripristinato.</td>
</tr>
<tr class="odd">
<td>TEXT (input)</td>
<td>Restituisce l'input specificato, che viene convertito in stringa di testo che viene formattata in base alle impostazioni locali server dell'istanza corrente di Dynamics 365 for Operations. Per i valori di tipo <strong>real</strong>, la conversione di stringhe è limitata a due posizioni decimali.</td>
<td>Se Dynamics 365 per le impostazioni locali di istanza delle operazioni è impostato su <strong>EN-US</strong>, <strong>TESTO (ORA ()</strong> Dynamics corrente restituisce 365 per la data della sessione delle operazioni, 12/17/2015, ad esempio la stringa <strong>&quot;12/17/2015 di 07:59: DI SERVICES 23&quot;</strong>di testo. <strong>TESTO (1/3)</strong> successivo <strong>&quot;0.33&quot;</strong>.</td>
</tr>
<tr class="even">
<td>FORMAT (stringa 1, stringa 2[, stringa 3, ...])</td>
<td>Restituisce la stringa specificata, che viene formattata sostituendo tutte le occorrenze di <strong>%N</strong> con l'argomento <em>n</em>esimo. Gli argomenti sono stringhe. Se un argomento non viene specificato per un parametro, questo parametro viene restituito nella <strong>&quot;%N&quot;</strong> stringa. Per i valori di tipo <strong>real</strong>, la conversione di stringhe è limitata a due posizioni decimali.</td>
<td>In questo esempio, l'origine dati <strong>PaymentModel</strong> restituisce l'elenco dei record cliente tramite il componente <strong>Customer</strong> il valore della data di elaborazione tramite il campo <strong>ProcessingDate</strong>. <a href="./media/picture-format-datasource.jpg"><img src="./media/picture-format-datasource.jpg" alt="PaymentModel data source" class="alignnone wp-image-290751 size-full" width="293" height="143" /></a> nel formato di ER che è progettato per generare un file elettronico per i clienti selezionati, <strong>PaymentModel</strong> viene selezionato come origine dei dati e controllare il flusso di processo. Un'eccezione viene generata per utenti finali quando un cliente selezionato viene interrotto per la data in cui il report viene elaborato. La formula che è stata progettata per questo tipo di controllo di processo può utilizzare le risorse indicate di seguito:
<ul>
<li>Etichetta SYS70894 di Dynamics 365 for Operations, con il testo seguente:
<ul>
<li><strong>Per la lingua di EN-US:</strong> &quot;Niente da stampare&quot;</li>
<li><strong>Per il DE language:</strong> &quot;Lo zu di Nichts drucken&quot;</li>
</ul></li>
<li>Etichetta SYS18389 di Dynamics 365 for Operations, con il testo seguente:
<ul>
<li><strong>Per la lingua di EN-US:</strong> &quot;Il cliente viene interrotta %1 per %2.&quot;</li>
<li><strong>Per il DE language:</strong> &quot;Debitore " %1 " gesperrt di für %2 di wird.&quot;</li>
</ul></li>
</ul>
Ecco la formula che può essere pianificata: FORMATO (CONCATENI (@SYS70894&quot;&quot;&quot;. &quot;, @SYS18389&quot;&quot;), Model.Customer.Name, DATETIMEFORMAT (model.ProcessingDate, d) se un report &quot;viene&quot; elaborato, il 17 dicembre 2015 per <strong>Cliente avvio di Litware</strong> la lingua e la lingua <strong>EN-US</strong>, rimborsi della <strong>EN-US</strong> formula il seguente testo, che può essere inviato il messaggio delle eccezioni per all'utente di finale: Niente da stampare. &quot; La vendita al dettaglio di Litware del cliente viene interrotta per 12/17/2015.&quot; Se lo stesso report viene elaborato, <strong>DE</strong> il 17 dicembre 2015 per<strong> Cliente avvio di Litware</strong> la lingua <strong>DE</strong> e la lingua, rimborsi della formula il seguente testo, che utilizza un formato di data diversa: &quot;Lo zu di Nichts drucken. Gesperrt "a" für di 17.12.2015 di wird di Litware del contribuente.&quot; <strong>Nota: </strong>La seguente sintassi si applica nelle formule ER per le etichette:
<ul>
<li><strong>Per le etichette da Dynamics 365 per le risorse operative:</strong><strong>@&quot;X&quot;</strong>, dove X è l'ID etichetta nella struttura a oggetti applicativi (AOT)</li>
<li><strong>Per le etichette inclusi nelle configurazioni di ER:</strong><strong>@&quot; eR_LABEL: X&quot;</strong>, dove X è l'ID etichetta nella configurazione di ER</li>
</ul></td>
</tr>
<tr class="odd">
<td>NUMBERFORMAT (numero, formato)</td>
<td>Restituisce la rappresentazione di stringa del numero specificato nel formato specificato. Per informazioni sui formati supportati, <a href="https://msdn.microsoft.com/en-us/library/dwhawy9k(v=vs.110).aspx">standard</a> e <a href="https://msdn.microsoft.com/en-us/library/0c899ak8(v=vs.110).aspx">personalizzato</a>). Il contesto che questa funzione viene eseguita in determina la lingua utilizzata da formattare i numeri.</td>
<td>Per la lingua di EN-US, <strong>NUMBERFORMAT (0.45, &quot;p&quot;)</strong> reso. <strong>NUMBERFORMAT (10.45, &quot;#&quot;)</strong> successivo <strong>&quot;10&quot;</strong>.</td>
</tr>
<tr class="even">
<td>NUMERALSTOTEXT (numero, lingua, valuta, flag stampa nome valuta, decimali)</td>
<td>Restituisce il numero contabilizzato (convertito) in stringhe di testo nella lingua definita. Il codice lingua è facoltativo: quando è definito come stringa vuota, il codice lingua corrente del contesto (definito per una cartella o un file di generazione) verrà utilizzato in sostituzione. Il codice valuta è facoltativo. Quando è definito come stringa vuota, viene utilizzata la valuta della società. Il parametro <strong>Stampa nome valuta</strong> e il parametro <strong>Decimali</strong> vengono analizzati soltanto per i seguenti codici lingua: <strong>CS</strong>, <strong>ET</strong>, <strong>HU</strong>, <strong>LT</strong>, <strong>LV</strong>, <strong>PL</strong>, <strong>RU</strong>. Il parametro <strong>Stampa nome valuta</strong> viene analizzato solo per le società Dynamics 365 for Operations con il contesto del paese che supporta la declinazione della valuta.</td>
<td>NUMERALSTOTEXT (1234.56, &quot;verrà en&quot;, &quot;&quot;falsa, 2), restituiscono "mille duecento trentaquattro e 56 "NUMERALSTOTEXT (120 PL&quot;&quot;, falsi 0) viene restituito al dwadzieścia" NUMERALSTOTEXT di Sto (120.21, &quot;il RU&quot;, &quot;l'importo&quot;di EUR, il 2), restituiscono al евроцент di Сто двадцать евро 21"</td>
</tr>
<tr class="odd">
<td>PADLEFT (stringa, lunghezza, caratteri di riempimento)</td>
<td>Restituisce una stringa della lunghezza specificata in cui l'inizio della stringa corrente viene riempita con i caratteri specificati.</td>
<td>PADLEFT ("1234", 10, " ") restituisce la stringa di testo "      1234"</td>
</tr>
</tbody>
</table>

### <a name="data-collection-functions"></a>Funzioni raccolta dati

Funzione

descrizione

Esempio

FORMATELEMENTNAME ()

Restituisce il nome dell'elemento del formato corrente. Restituisce la stringa vuota se il flag **Raccogli dettagli di output** del file corrente è disattivato.

Per ulteriori informazioni sull'utilizzo di queste funzioni, fare riferimento alla guida attività **ER Utilizzare i dati dell'output del formato per il conteggio e la somma** (parte del processo aziendale **Acquisire/sviluppare componenti di soluzioni/servizi IT**.

SUMIFS (String chiave per la somma, stringa di criteri, range1 stringa di \[value1 di criteri, stringa di criteri, range2 stringa di value2 di criteri,...\])

Restituisce la somma dei valori dei nodi (con il nome definito come chiave) dell'XML che è stata raccolta durante l'esecuzione del formato e soddisfa le condizioni immesse (coppie di intervallo e valore). Restituisce il valore zero se il flag **Raccogli dettagli di output** del file corrente è disattivato.

SUMIF (stringa chiave per somma, stringa intervallo di criteri, stringa valore di criteri)

Restituisce la somma dei valori dei nodi (con il nome definito come chiave) dell'XML che è stata raccolta durante l'esecuzione del formato e soddisfa la condizione (coppie di intervallo e valore). Restituisce il valore zero se il flag **Raccogli dettagli di output** del file corrente è disattivato.

COUNTIFS (stringa di criteri, range1 stringa di \[value1 di criteri, stringa di criteri, range2 stringa di value2 di criteri,...\])

Restituisce il numero dei nodi dell'XML che è stata raccolta durante l'esecuzione del formato e soddisfa le condizioni immesse (coppie di intervallo e valore). Restituisce il valore zero se il flag **Raccogli dettagli di output** del file corrente è disattivato.

COUNTIF (stringa intervallo di criteri, stringa valore di criteri)

Restituisce il numero dei nodi dell'XML che è stata raccolta durante l'esecuzione del formato e soddisfa la condizione immessa (intervallo e valore). Restituisce il valore zero se il flag **Raccogli dettagli di output** del file corrente è disattivato.

COLLECTEDLIST (stringa di criteri, range1 stringa di \[value1 di criteri, stringa di criteri, range2 stringa di value2 di criteri,...\])

Restituisce l'elenco dei valori dei nodi dell'XML che è stata raccolta durante l'esecuzione del formato e soddisfa le condizioni immesse (intervallo e valore). Restituisce un elenco vuoto se il flag **Raccogli dettagli di output** del file corrente è disattivato.

### <a name="other-business-domainspecific-functions"></a>Altre funzioni (specifiche del dominio aziendale)

| Funzione                                                                         | descrizione                                                                                                                                                                                                                                                        | Esempio                                                                                                                                                                                                                                                                                                       |
|----------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| CONVERTCURRENCY (importo, valuta di origine, valuta di destinazione, data, società)        | Converte l'importo monetario specificato da valuta di origine nella valuta di destinazione utilizzando le impostazioni della società specificata di Dynamics 365 for Operations alla data specificata.                                                                            | **CONVERTCURRENCY (1, "EUR", "USD", TODAY(), "DEMF")** restituisce un equivalente di un euro in dollari statunitensi nella data della sessione corrente, in base alle impostazioni per la società DEMF.                                                                                                                                  |
| ROUNDAMOUNT (numero, decimali, regola arrotondamento)                                       | Arrotonda l'importo specificato in base alla regola di arrotondamento specificata e il numero specificato posizioni decimali. **Nota:** La regola di arrotondamento deve essere specificata come valore di enumerazione **RoundOffType** di Dynamics 365 for Operations.                          | ** Se model.RoundOff ** il parametro è impostato su **** ordine di ****, ** ROUNDAMOUNT (1000.787, 2, model.RoundOff) ** restituisce il valore 1000.78 ** **. Se il parametro **model.RoundOff** è impostato su **Normal** o **Rounding-up**, **ROUNDAMOUNT (1000.787, 2, model.RoundOff)** restituisce il valore **1000.79**. |
| CURCredRef (cifre)                                                              | Restituisce un riferimento creditore, in base alle cifre del numero di fattura specificato.                                                                                                                                                                                  | **CURCredRef ("VEND-200002")** restituisce **"2200002"**.                                                                                                                                                                                                                                                         |
| Modulo\_97 (cifre)                                                                 | Restituisce un riferimento creditore come espressione MOD97, in base alle cifre del numero di fattura specificato.                                                                                                                                                            | ** Modulo\_("97") VEND-200002 ** resi ** "20000285 "**.                                                                                                                                                                                                                                                           |
| ISOCredRef (cifre)                                                              | Restituisce un riferimento creditore ISO, in base alle cifre e ai simboli alfabetici del numero di fattura specificato. **Nota: **Per eliminare i simboli da alfabeti che non sono conformi ISO, il parametro di input deve essere tradotto prima di passarlo alla funzione. | **ISOCredRef ("VEND-200002")** restituisce **"RF23VEND-200002"**.                                                                                                                                                                                                                                                 |
| CN\_GBT\_AdditionalDimensionID (stringa, numero)                                  | Ottenere l'ID dimensione finanziaria aggiuntiva. Le dimensioni sono rappresentate nella stringa come ID separati da virgole. I numeri definiscono il codice di sequenza della dimensione richiesto nella stringa.                                                                            | CN\_GBT\_("AdditionalDimensionID AA, BB, CC, DD, EE, FF, GG, HH 3", ") reso CC"                                                                                                                                                                                                                                      |
| GetCurrentCompany ()                                                             | Restituisce il codice della società attualmente registrata.                                                                                                                                                                                                                    |                                                                                                                                                                                                                                                                                                               |
| Modulo\_10 cifre ()\_immettere BANCA di CH\_                                                       | Restituisce un riferimento creditore come espressione MOD10, in base alle cifre del numero di fattura specificato.                                                                                                                                                                      | \_modulo\_immettere BANCA di CH\_("10" VEND-200002 resi 3)                                                                                                                                                                                                                                                                   |
| SUM di registrazione cespiti\_(codice del cespite, il codice valore, data di inizio, Data di fine modello)               | Restituisce il contenitore dati preparati degli importi di un cespite per un periodo.                                                                                                                                                                                         | IL SUM di registrazione cespiti\_("COMP-000001 ", "corrente", Date1, Date2) restituisce il contenitore pronto di dati del cespite COMP-000001 "" con il modello corrente "" di valore per un periodo da Date1 a Date2.                                                                                                                        |
| SALDO di registrazione cespiti\_(codice del cespite, il codice modello di valore, di reporting anno, data) | Restituisce il contenitore dati preparati dei saldi di un cespite. L'anno di dichiarazione deve essere specificato come valore dell'enumerazione di Dynamics 365 for Operations **AssetYear**.                                                                                           | SUM di registrazione cespiti\_("COMP-000001 ", "corrente", anno di AxEnumAssetYear.This, SESSIONTODAY () restituisce il contenitore pronto dei saldi relativi al cespite COMP-000001 "" con il modello corrente "" di valore dei 365 correnti per la data della sessione delle operazioni.                                                                |

### <a name="functions-list-extension"></a>Estensione dell'elenco di funzioni

ER consente di estendere l'elenco di funzioni utilizzate nelle espressioni ER. A tal fine sono richieste alcune operazioni progettuali. Per informazioni dettagliate, vedere [Estensione dell'elenco di funzioni di creazione di report elettronici (ER)](general-electronic-reporting-formulas-list-extension.md).

<a name="see-also"></a>Vedere anche
--------

[Panoramica sui report elettronici](general-electronic-reporting.md)

[Estensione dell'elenco di funzioni di creazione di report elettronici (ER)](general-electronic-reporting-formulas-list-extension.md)


