---
title: Designer formula nella creazione di report elettronici
description: In questo argomento viene illustrato come utilizzare designer formula nei report elettronici (ER).
author: NickSelin
manager: AnnBe
ms.date: 11/27/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: 41d5671d180bae039d873419352d52afe90e386b
ms.contentlocale: it-it
ms.lasthandoff: 03/26/2018

---

# <a name="formula-designer-in-electronic-reporting"></a>Designer formula nella creazione di report elettronici

[!include[banner](../includes/banner.md)]

In questo argomento viene illustrato come utilizzare designer formula nei report elettronici (ER). Quando si progetta un formato di un documento elettronico specifico in ER, è possibile utilizzare le formule per la trasformazione dei dati in modo da soddisfare i requisiti per la compilazione e la formattazione del documento. Le formule somigliano alle formule in Microsoft Excel. Nelle formule, sono supportate funzioni di diverso tipo: testo, data e ora, logica matematica, informazioni, conversione del tipo di dati e altre (funzioni specifiche del dominio aziendale).

## <a name="formula-designer-overview"></a>Panoramica su Designer formula

ER supporta il Designer formula. Di conseguenza, in fase di progettazione, è possibile configurare le espressioni che possono essere utilizzate per le seguenti attività in fase di esecuzione:

- Trasformazione dei dati ricevuti da un database Microsoft Dynamics 365 for Finance and Operations e che devono essere inseriti in un modello dati ER progettato per fungere da origine dati per i formati ER. Se ad esempio, le trasformazioni possono includere il filtro, raggruppamento e conversione del tipo di dati.
- Formattare i dati che devono essere inviati a un documento elettronico di generazione in conformità al layout e agli stati di un formato specifico di ER. Se ad esempio, la formattazione deve essere eseguita in conformità alla lingua o cultura richiesta o alla codifica.
- Controllare il processo di creazione di documenti elettronici. Se ad esempio, le eventuali espressioni possono abilitare o disabilitare l'output di elementi specifici del formato, in base all'elaborazione dei dati. Possono inoltre interrompere il processo di creazione del documento o inviare messaggi agli utenti.

La pagina **Designer formula** può essere aperta quando si esegue una delle seguenti azioni:

- Associazione di articoli di origini dati a componenti del modello dati.
- Associazione di articoli di origini dati a componenti del formato.
- Gestione completa dei campi calcolati che sono parte delle origini dati.
- Definizione delle condizioni di visibilità per i parametri di input utente.
- Progettazione delle trasformazioni di un formato.
- Definizione delle condizioni di abilitazione per i componenti del formato.
- Definizione dei nomi di file per i componenti FILE del formato.
- Definizione delle condizioni per le convalide di controllo dei processi.
- Definizione del testo del messaggio per le convalide di controllo dei processi.

## <a name="designing-er-formulas"></a>Progettazione di formule ER

### <a name="data-binding"></a>Associazione dati

Il Designer formula ER può essere utilizzato per definire un'espressione che trasforma i dati ricevuti da origini dati, in modo che i dati possono essere inseriti nel consumer di dati in fase di runtime:

- Da origini dati di Finance and Operations e dai parametri di runtime a un modello dati ER
- Da un modello dati ER a un formato ER
- Da origini dati di Finance and Operations e dai parametri di runtime a un formato ER

La figura seguente mostra la progettazione di un'espressione di questo tipo. In questo esempio, l'espressione arrotonda a due posizioni decimali il valore del campo **Intrastat.AmountMST** della tabella Intrastat di Finance and Operations e quindi restituisce il valore arrotondato.

[![Associazione dati](./media/picture-expression-binding.jpg)](./media/picture-expression-binding.jpg)

La figura seguente mostra come è possibile utilizzare un'espressione di questo tipo. In questo esempio, il risultato dell'espressione pianificata è immesso nel componente **Transaction.InvoicedAmount** del modello dati **Modello di dichiarazione imposte**.

[![Associazione dati utilizzata](./media/picture-expression-binding2.jpg)](./media/picture-expression-binding2.jpg)

In fase di esecuzione, la formula progettata, **ROUND (Intrastat.AmountMST, 2)**, arrotonda a due posizioni decimali il valore del campo **AmountMST** per ogni record della tabella Intrastat. Quindi immette il valore arrotondato nel componente **Transaction.InvoicedAmount** del modello dati **Dichiarazione imposte**.

### <a name="data-formatting"></a>Formattazione di dati

Il Designer formula ER può essere utilizzato per definire un'espressione che formatta i dati ricevuti da origini dati, in modo che i dati possono essere inviati come parte del documento elettronico generato. Potrebbe essere presente una formattazione che deve essere applicata come regola standard da riutilizzare per un formato. In questo caso, è possibile introdurla una volta nella configurazione del formato come trasformazione denominata con espressione di formattazione. Successivamente questa trasformazione denominata può essere collegata a molti componenti di formato in cui l'output deve essere formattato in base all'espressione di formattazione creata.

La figura seguente mostra la progettazione di una trasformazione di questo tipo. In questo esempio, la trasformazione **TrimmedString** tronca i dati in ingresso del tipo di dati **String** rimuovendo spazi iniziali e finali. Itd restituisce quindi il valore stringa troncato.

[![Trasformazione](./media/picture-transformation-design.jpg)](./media/picture-transformation-design.jpg)

La figura seguente mostra come è possibile utilizzare una trasformazione di questo tipo. In questo esempio, più componenti di formato inviano testo come output per la generazione del documento elettronico in fase di runtime. Tutti questi componenti del formato fanno riferimento alla trasformazione **TrimmedString** per nome.

[![Trasformazione utilizzata](./media/picture-transformation-usage.jpg)](./media/picture-transformation-usage.jpg)

Quando i componenti del formato fanno riferimento alla trasformazione **TrimmedString** (ad esempio, il componente **partyName** della precedente figura), la trasformazione invia il testo come output alla generazione del documento elettronico. Questo testo non include gli spazi iniziali e finali.

Se una formattazione deve essere applicata singolarmente, può essere introdotta come singola espressione di associazione di un determinato componente di formato. La figura seguente mostra un'espressione di questo tipo. In questo esempio, il componente di formato **partyType** è associato all'origine dati mediante un'espressione che converte i dati in ingresso dal campo **Model.Company.RegistrationType** nell'origine dati in testo maiuscolo. L'espressione invia quindi il testo come output al documento elettronico.

[![Applicazione della formattazione a un singolo componente](./media/picture-binding-with-formula.jpg)](./media/picture-binding-with-formula.jpg)

### <a name="process-flow-control"></a>Controllo del flusso del processo

Designer formula ER può essere utilizzato per definire le espressioni che controllano il flusso del processo di generazione dei documenti elettronici. È possibile effettuare le attività seguenti:

- Definire le condizioni che determinano quando il processo di creazione di un documento deve essere arrestato.
- Specificare le espressioni che creano messaggi per l'utente sui processi arrestati o che generano i messaggi del registro di esecuzione sul proseguimento del processo di creazione del report.
- Specificare i nomi file dei documenti elettronici generati e controllare le condizioni della relativa creazione.

Ogni regola del controllo del flusso del processo è progettata come singola convalida. La figura seguente mostra una convalida di questo tipo. Ecco una spiegazione della configurazione in questo esempio:

- La convalida viene valutata quando il nodo **INSTAT** viene creato durante la generazione del file XML.
- Se l'elenco delle transazioni è vuoto, la convalida interrompe il processo di esecuzione restituisce **FALSE**.
- La convalida restituisce un messaggio di errore che include il testo dell'etichetta SYS70894 di Finance and Operations nella lingua preferita dell'utente.

[![Convalida](./media/picture-validation.jpg)](./media/picture-validation.jpg)

Designer formula ER può essere utilizzato anche per generare un nome file per la generazione di un documento elettronico e per controllare il processo di creazione del file. La figura seguente mostra la progettazione di un controllo del flusso di processo di questo tipo. Ecco una spiegazione della configurazione in questo esempio:

- L'elenco dei record dell'origine dati **model.Intrastat** è suddiviso in batch. Ogni batch contiene un massimo di 1.000 record.
- L'output crea un file ZIP contenente un file in formato XML per ogni batch creato.
- Un'espressione restituisce un nome file per la generazione dei documenti elettronici concatenando il nome file e l'estensione del nome file. Per il secondo batch e tutti i batch successivi, il nome file contiene l'ID batch come suffisso.
- Un'espressione abilita (restituendo **TRUE**) il processo di creazione file solo per i batch che contengono almeno un record.

[![Controllo file](./media/picture-file-control.jpg)](./media/picture-file-control.jpg)

### <a name="basic-syntax"></a>Sintassi di base

Le espressioni ER possono contenere qualsiasi o tutti i seguenti elementi:

- Costanti
- Operatori
- Riferimenti
- Percorsi
- Funzioni

#### <a name="constants"></a>Costanti

È possibile utilizzare testo e costanti numeriche (ovvero valori che non vengono calcolati) nella progettazione delle espressioni. Ad esempio, una costante numerica **20** e la costante di tipo stringa **"100**" vengono utilizzate nella seguente espressione **VALUE ("100") + 20** che restituisce il valore numerico **120**. Le sequenze di escape sono supportate in Designer formula ER. Di conseguenza, è possibile specificare una stringa di espressione che deve essere gestita in modo diverso. Ad esempio, l'espressione **"Leo Tolstoj ""Guerra e pace"" Volume 1"** restituisce la stringa di testo **Leo Tolstoj "Guerra e pace" Volume 1**.

#### <a name="operators"></a>Operatori

La seguente tabella mostra agli operatori aritmetici che è possibile utilizzare per eseguire le operazioni matematiche di base, ad esempio addizione, sottrazione, moltiplicazione e divisione.

| Operatore | Significato               | Esempio |
|----------|-----------------------|---------|
| +        | Addizione              | 1+2     |
| -        | Sottrazione, negativa | 5-2, -1 |
| \*       | Moltiplicazione        | 7\*8    |
| /        | Divisione              | 9/3     |

Nella seguente tabella vengono visualizzati gli operatori di confronto supportati. È possibile utilizzare questi operatori per confrontare due valori.

| Operatore | Significato                  | Esempio    |
|----------|--------------------------|------------|
| =        | Uguale                    | X=Y        |
| &gt;     | Maggiore di             | X&gt;Y     |
| &lt;     | Minore di                | X&lt;Y     |
| &gt;=    | Uguale o maggiore di | X&gt;=Y    |
| &lt;=    | Uguale o minore di    | X&lt;=Y    |
| &lt;&gt; | Diverso da             | X&lt;&gt;Y |

Inoltre, è possibile utilizzare una e commerciale (&) come operatore di concatenazione del testo. In questo modo, è possibile unire, o concatenare, una o più stringhe di testo in un testo unico.

| Operatore | Significato     | Esempio                                             |
|----------|-------------|-----------------------------------------------------|
| &        | Concatena | "Niente da stampare" & ":&nbsp;" & "nessun record trovato" |

##### <a name="operator-precedence"></a>Precedenza di operatore

L'ordine in cui le parti di un'espressione composta vengono valutate è importante. Ad esempio, il risultato dell'espressione **1 + 4 / 2** varia a seconda se viene eseguita prima l'addizione o la divisione. È possibile utilizzare le parentesi per definire in modo esplicito come un'espressione viene valutata. Ad esempio, per indicare che l'operazione di addizione deve essere eseguita per prima, è possibile modificare l'espressione precedente in **(1 + 4) / 2**. Se l'ordine delle operazioni in un'espressione non è definito in modo esplicito, l'ordine è basato sulla precedenza predefinita assegnata agli operatori supportati. Nella seguente tabella viene visualizzata la precedenza assegnata a ciascun operatore. Gli operatori con una precedenza più alta (ad esempio, 7) vengono valutati prima degli operatori con una precedenza inferiore (ad esempio, 1).

| Precedenza | Operatori      | Sintassi                                                                  |
|------------|----------------|-------------------------------------------------------------------------|
| 7          | Raggruppamento       | ( … )                                                                   |
| 6          | Accesso a membro  | … . …                                                                   |
| 5          | Chiamata di funzione  | … ( … )                                                                 |
| 4          | Moltiplicativo | … \* …<br>… / …                                                         |
| 3          | Addizione       | … + …<br>… - …                                                          |
| 2          | Confronto     | … &lt; …<br>… &lt;= …<br>… =&gt; …<br>… &gt; …<br>… = …<br>… &lt;&gt; … |
| 1          | Separazione     | … , …                                                                   |

Se un'espressione include più operatori consecutivi con la stessa precedenza, tali operazioni vengono valutate da sinistra a destra. Ad esempio, l'espressione **1 + 6 / 2 \* 3 &gt; 5** restituisce **true**. Si consiglia di utilizzare le parentesi per indicare in modo esplicito l'ordine desiderato delle operazione nelle espressioni, per rendere le espressioni più facili da leggere e gestire.

#### <a name="references"></a>Riferimenti

Tutte le origini dati del componente ER corrente disponibili nella progettazione di un'espressione possono essere utilizzate come riferimenti denominati. (Il componente ER corrente può essere un modello o un formato). Ad esempio, il modello dati ER corrente contiene l'origine dati **ReportingDate** che restituisce un valore del tipo di dati **DATETIME**. Per formattare correttamente il valore per la generazione del documento, è possibile fare riferimento all'origine dati nell'espressione nel seguente modo: **DATETIMEFORMAT (ReportingDate, "gg-MM-aaaa")**.

Tutti i caratteri nel nome di un'origine dati di riferimento che non rappresentano una lettera di alfabeto devono essere preceduti da una virgoletta singola ('). Se il nome di un'origine dati di riferimento contiene almeno un simbolo che non rappresenta una lettera di alfabeto, il nome deve essere racchiuso tra virgolette singole. Ad esempio, i simboli non alfabetici possono essere segni di punteggiatura o altri simboli scritti. Di seguito sono riportati alcuni esempi:

- L'origine dati **Today's date & time** deve essere utilizzata in un'espressione ER come segue: **'Today''s date & time'**.
- Al metodo **name()** dell'origine dati **Customers** deve essere fatto riferimento in un'espressione ER come segue: **Customers.'name()'**.

Se i metodi delle origini dati di Finance and Operations includono dei parametri, la seguente sintassi viene utilizzata per chiamare i metodi:

- Se il metodo **isLanguageRTL** dell'origine dati **System** ha un parametro **EN-US** del tipo di dati **String**, questo metodo deve corrispondere all'espressione ER nel seguente modo: **System.'isLanguageRTL'("EN-US")**.
- Le virgolette non sono richieste quando un nome di metodo contiene solo simboli alfanumerici. Tuttavia, sono obbligatorie per un metodo di tabella se il nome include le parentesi.

Se l'origine dati **System** viene aggiunta a un mapping ER che fa riferimento alla classe dell'applicazione **Global** di Finance and Operations, l'espressione restituisce il valore booleano, **FALSE**. L'espressione modificata **System.' isLanguageRTL'("AR")** restituisce il valore booleano **TRUE**.

È possibile limitare il modo in cui i valori vengono passati ai parametri di questo tipo di metodo:

- Solo le costanti possono essere passate ai metodi di questo tipo. I valori delle costanti vengono definiti in fase di progettazione.
- Solo i tipi di dati primitivi (base) sono supportati per i parametri di questo tipo. I tipi di dati primitivi sono numeri interi, numeri reali, valori booleani, valori stringa e così via.

#### <a name="paths"></a>Percorsi

Quando un'espressione fa riferimento a un'origine dati strutturata, è possibile utilizzare la definizione di percorso per selezionare un elemento primitivo specifico di tale origine dati. Un carattere di punto (.) viene utilizzato per separare i singoli elementi di origine dati strutturata. Ad esempio, il modello dati ER corrente contiene l'origine dati **InvoiceTransactions** che restituisce un elenco di record. La struttura di record **InvoiceTransactions** contiene i campi **AmountDebit** e **AmountCredit** che restituiscono entrambi valori numerici. Pertanto è possibile progettare la seguente espressione per il calcolo dell'importo fatturato: **InvoiceTransactions.AmountDebit - InvoiceTransactions.AmountCredit**.

#### <a name="functions"></a>Funzioni

Nella sezione successiva vengono descritte le funzioni che possono essere utilizzate in espressioni ER. Tutte le origini dati del contesto dell'espressione (modello dati o formato ER corrente) possono essere utilizzate come parametri di funzioni di chiamata, secondo l'elenco degli argomenti delle funzioni di chiamata. Anche le costanti possono essere utilizzate come parametri delle funzioni di chiamata. Ad esempio, il modello dati ER corrente contiene l'origine dati **InvoiceTransactions** che restituisce un elenco di record. La struttura di record **InvoiceTransactions** contiene i campi **AmountDebit** e **AmountCredit** che restituiscono entrambi valori numerici. Pertanto, per calcolare l'importo fatturato è possibile progettare la seguente espressione che usa la funzione di arrotondamento ER integrata: **ROUND (InvoiceTransactions.AmountDebit - InvoiceTransactions.AmountCredit, 2)**.

## <a name="supported-functions"></a>Funzioni supportate

Le seguenti tabelle descrivono le funzioni di manipolazione dei dati che è possibile utilizzare per progettare i modelli di dati ER e report ER. L'elenco delle funzioni non è fisso. Gli sviluppatori possono estenderlo. Per vedere l'elenco delle funzioni che è possibile utilizzare, aprire il riquadro delle funzioni in Designer formula ER.

### <a name="date-and-time-functions"></a>Funzioni di data e ora

| Funzione | Descrizione | Esempio |
|----------|-------------|---------|
| ADDDAYS (data/ora, giorni) | Aggiunge il numero di giorni specificato al valore data/ora specificato. | **ADDDAYS (NOW(), 7)** restituisce la data e l'ora di sette giorni in futuro. |
| DATETODATETIME (data) | Converte il valore di data specificato in un valore data/ora. | **DATETODATETIME (CompInfo. 'getCurrentDate()')** restituisce la data della sessione Finance and Operations corrente, 24 dicembre 2015, come **12/24/2015 12:00:00 AM**. In questo esempio, **CompInfo** è l'origine dati ER del tipo **Finance and Operations/Tabella** e fa riferimento alla tabella CompanyInfo. |
| NOW () | Restituisce la data e l'ora del server applicazioni corrente di Finance and Operations come valore di data/ora. | |
| TODAY () | Restituisce la data e l'ora del server applicazioni corrente di Finance and Operations come valore di data. | |
| NULLDATE () | Restituisce un valore di data **null**. | |
| NULLDATETIME () | Restituisce un valore di data/ora **null**. | |
| DATETIMEFORMAT (data/ora, formato) | Converte il valore specificato di data/ora in una stringa nel formato specificato. (Per informazioni sui formati supportati, vedere [standard](https://msdn.microsoft.com/en-us/library/az4se3k1(v=vs.110).aspx) e [personalizzato](https://msdn.microsoft.com/en-us/library/8kb3ddd4(v=vs.110).aspx).) | **DATETIMEFORMAT (NOW(), "dd-MM-yyyy")** restituisce la data del server di applicazioni Finance and Operations, 24 dicembre 2015, come **"24-12-2015"**, basato sul formato specificato personalizzato. |
| DATETIMEFORMAT (data/ora, impostazioni cultura) | Converte il valore di data/ora specificato in una stringa nel formato e nelle [impostazioni cultura](https://msdn.microsoft.com/en-us/goglobal/bb896001.aspx) specificati. (Per informazioni sui formati supportati, vedere [standard](https://msdn.microsoft.com/en-us/library/az4se3k1(v=vs.110).aspx) e [personalizzato](https://msdn.microsoft.com/en-us/library/8kb3ddd4(v=vs.110).aspx)). | **DATETIMEFORMAT (NOW(), "d", "de")** restituisce la data del server applicazioni corrente di Finance and Operations, 24 dicembre 2015, come **"24.12.2015"**, in base alle impostazioni cultura tedesche selezionate. |
| SESSIONTODAY () | Restituisce la data e l'ora della sessione corrente di Finance and Operations come valore di data. | |
| SESSIONNOW () | Restituisce la data e l'ora della sessione corrente di Finance and Operations come valore di data/ora. | |
| DATEFORMAT (data, formato) | Restituisce una rappresentazione di stringa della data specificata nel formato specificato. | **DATEFORMAT (SESSIONTODAY (), "dd-MM-yyyy")** restituisce la data della sessione Finance and Operations, 24 dicembre 2015, come **"24-12-2015"**, basato sul formato specificato personalizzato. |
| DATEFORMAT (data, formato, impostazioni cultura) | Convertire il valore di data specificato in una stringa nel formato e nelle [impostazioni cultura](https://msdn.microsoft.com/en-us/goglobal/bb896001.aspx) specificati. (Per informazioni sui formati supportati, vedere [standard](https://msdn.microsoft.com/en-us/library/az4se3k1(v=vs.110).aspx) e [personalizzato](https://msdn.microsoft.com/en-us/library/8kb3ddd4(v=vs.110).aspx)). | **DATETIMEFORMAT (SESSIONNOW (), "d", "de")** restituisce la data della sessione corrente di Finance and Operations, 24 dicembre 2015, come **"24.12.2015"**, in base alle impostazioni cultura tedesche selezionate. |
| DAYOFYEAR (data) | Restituisce la rappresentazione integer del numero di giorni tra l'1 gennaio e la data specificata. | **DAYOFYEAR (DATEVALUE ("01-03-2016", "dd-MM-yyyy"))** restituisce **61**. **DAYOFYEAR (DATEVALUE ("01-01-2016", "dd-MM-yyyy"))** restituisce **1**. |
| DAYS (data 1, data 2) | Restituisce il numero di giorni compresi tra la prima data specificata e la seconda data specificata. Restituisce un valore positivo quando la prima data è successiva alla seconda data, restituisce **0** (zero) quando la prima data corrisponde alla seconda data o restituisce un valore negativo in caso contrario. | **DAYS (TODAY (), DATEVALUE( DATETIMEFORMAT( ADDDAYS(NOW(), 1), "yyyyMMdd"), "yyyyMMdd"))** restituisce **-1**. |

### <a name="data-conversion-functions"></a>Funzioni conversione dati

| Funzione | descrizione | Esempio |
|----------|-------------|---------|
| DATETODATETIME (data) | Converte il valore di data specificato in un valore data/ora. | **DATETODATETIME (CompInfo. 'getCurrentDate()')** restituisce la data della sessione Finance and Operations corrente, 24 dicembre 2015, come **12/24/2015 12:00:00 AM**. In questo esempio, **CompInfo** è l'origine dati ER del tipo **Finance and Operations/Tabella** e fa riferimento alla tabella CompanyInfo. |
| DATEVALUE (stringa, formato) | Restituisce una rappresentazione data della stringa specificata nel formato specificato. | **DATEVALUE ("21-Dec-2016", "dd-MMM-yyyy")** restituisce la data 21 dicembre 2016 in base al formato personalizzato specificato alle impostazioni cultura **EN-US** dell'applicazione predefinita. |
| DATEVALUE (stringa, formato, impostazioni cultura) | Restituisce una rappresentazione data della stringa specificata nel formato e nella cultura specificate. | **DATEVALUE ("21-Gen-2016", "dd-MMM-yyyy", "IT")** restituisce la data 21 gennaio 2016 in base al formato e alla cultura personalizzati specificati. Tuttavia, **DATEVALUE ("21-Gen-2016", "dd-MMM-yyyy", "EN-US")** genera un'eccezione per informare l'utente che la stringa specificata non viene riconosciuta come data valida. |
| DATETIMEVALUE (stringa, formato) | Restituisce una rappresentazione data/ora della stringa specificata nel formato specificato. | **DATETIMEVALUE ("21-Dec-2016 02:55:00", "dd-MMM-yyyy hh:mm:ss")** restituisce 2:55:00 AM il 21 dicembre 2016, in base al formato personalizzato specificato e alla cultura predefinita dell'applicazione **EN-US**. |
| DATETIMEVALUE (stringa, formato, impostazioni cultura) | Restituisce una rappresentazione data/ora della stringa specificata nel formato e nella cultura specificate. | **DATETIMEVALUE ("21-Gen-2016 02:55:00", "dd-MMM-yyyy hh:mm:ss", "IT")** restituisce 2:55:00 AM il 21 dicembre 2016, in base al formato personalizzato specificato e alla cultura predefinita dell'applicazione EN-US. Tuttavia, **DATETIMEVALUE ("21-Gen-2016 02:55:00", "dd-MMM-yyyy hh:mm:ss", "EN-US")** genera un'eccezione per informare l'utente che la stringa specificata non viene riconosciuta come data/ora valida. |

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
<td><strong>SPLIT (&quot;abcd&quot;, 3)</strong> restituisce un nuovo elenco costituito da due record con un campo <strong>STRING</strong>. Il campo del primo record contenente il testo <strong>&quot;abc&quot;</strong> e il campo nel secondo record contenente il testo <strong>&quot;d&quot;</strong>.</td>
</tr>
<tr class="even">
<td>SPLITLIST (elenco, numero)</td>
<td>Divide l'elenco specificato in batch, ciascuno dei quali contiene il numero specificato di record. Restituisce il risultato come nuovo elenco di batch contenente i seguenti elementi:
<ul>
<li>Batch come normali elenchi (componente <strong>Value</strong>)</li>
<li>Il numero batch corrente (componente <strong>BatchNumber</strong>)</li>
</ul></td>
<td>Nella seguente figura, un'origine dati <strong>Righe</strong> viene creata come un elenco di record con tre record. Questo elenco viene suddiviso in batch, ciascuno contenente fino a due record.
<p><a href="./media/picture-splitlist-datasource.jpg"><img src="./media/picture-splitlist-datasource.jpg" alt="Data source that is divided into batches" class="alignnone wp-image-290681 size-full" width="397" height="136" /></a></p>
<p>Nella figura seguente è illustrato il layout di formato progettato. In questo layout di formato, le associazioni all'origine dati <strong>Righe</strong> vengono create per generare l'output in formato XML. Questo output presenta nodi individuali per ogni batch e i record contenuti.</p>
<p><a href="./media/picture-splitlist-format.jpg"><img src="./media/picture-splitlist-format.jpg" alt="Format layout that has bindings to a data source" class="alignnone wp-image-290691 size-full" width="374" height="161" /></a></p>
<p>Nella figura seguente è illustrato il risultato dell'esecuzione del formato progettato.</p>
<a href="./media/picture-splitlist-result.jpg"><img src="./media/picture-splitlist-result.jpg" alt="Result of running the format" class="alignnone wp-image-290701 size-full" width="358" height="191" /></a></td>
</tr>
<tr class="odd">
<td>LIST (record 1 [, record 2, …])</td>
<td>Restituisce un nuovo elenco creato dagli argomenti specificati.</td>
<td><strong>LIST (model.MainData, model.OtherData)</strong> restituisce un record vuoto, dove l'elenco di campi contiene tutti i campi degli elenchi di record <strong>MainData</strong> e <strong>OtherData</strong>.</td>
</tr>
<tr class="even">
<td>LISTJOIN (elenco 1, elenco 2, …)</td>
<td>Restituisce un elenco collegato dagli elenchi di argomenti specificati.</td>
<td><strong>LISTJOIN (SPLIT (&quot;abc&quot;, 1), SPLIT (&quot;def&quot;, 1))</strong> restituisce un elenco di sei record, in cui un campo del tipo di dati <strong>STRING</strong> contiene le singole lettere.</td>
</tr>
<tr class="odd">
<td>ISEMPTY (elenco)</td>
<td>Restituisce <strong>TRUE</strong> se l'elenco specificato non contiene elementi. In caso contrario, restituisce <strong>FALSE</strong>.</td>
<td></td>
</tr>
<tr class="even">
<td>EMPTYLIST (elenco)</td>
<td>Restituisce un elenco vuoto utilizzando l'elenco specificato come origine della struttura elenco.</td>
<td><strong>EMPTYLIST (SPLIT (&quot;abc&quot;, 1))</strong> restituisce un nuovo elenco vuoto con la stessa struttura dell'elenco restituito dalla funzione <strong>SPLIT</strong>.</td>
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
<td>Restituisce un nuovo elenco bidimensionale che rappresenta tutti gli elementi che corrispondono a un percorso specifico. Il percorso deve essere definito come percorso di un'origine dati valido in un elemento di origine dati di un tipo di dati elenco di record. Gli elementi di dati come stringa percorso e data devono generare un errore in fase di progettazione nel generatore di espressioni ER.</td>
<td>Se si immette <strong>SPLIT(&quot;abcdef&quot; , 2)</strong> come origine dati (DS), <strong>COUNT( ALLITEMS (DS.Value))</strong> restituisce <strong>3</strong>.</td>
</tr>
<tr class="odd">
<td>ORDERBY (elenco [, espressione 1, espressione 2, …])</td>
<td>Restituisce l'elenco specificato dopo che è stato ordinato in base agli argomenti specifici. Questi argomenti possono essere definiti come espressioni.</td>
<td>Se <strong>Vendor</strong> viene configurato come origine dati ER che fa riferimento alla tabella VendTable, <strong>ORDERBY (Vendors, Vendors.'name()')</strong> restituisce un elenco dei fornitori ordinato per nome in ordine crescente.</td>
</tr>
<tr class="even">
<td>REVERSE (elenco)</td>
<td>Restituisce l'elenco specificato in ordine inverso.</td>
<td>Se <strong>Vendor</strong> viene configurato come origine dati ER che fa riferimento alla tabella VendTable, <strong>REVERSE (ORDERBY (Vendors, Vendors.'name()')) )</strong> restituisce un elenco dei fornitori ordinato per nome in ordine decrescente.</td>
</tr>
<tr class="odd">
<td>WHERE (elenco, condizione)</td>
<td>Restituisce l'elenco specificato dopo che è stato filtrato in base alla condizione specifica. La condizione specificata viene applicata all'elenco nella memoria. In questo modo, la funzione <strong>WHERE</strong> è diversa dalla funzione <strong>FILTER</strong>.</td>
<td>Se <strong>Vendor</strong> viene configurato come origine dati ER che fa riferimento alla tabella VendTable, <strong>WHERE(Vendors, Vendors.VendGroup = &quot;40&quot;)</strong> restituisce un elenco solo dei fornitori che appartengono al gruppo 40.</td>
</tr>
<tr class="even">
<td>ENUMERATE (elenco)</td>
<td>Restituisce un nuovo elenco corrispondente ai record enumerati dell'elenco specificato e che espone i seguenti elementi:
<ul>
<li>Record dell'elenco specificati come normali elenchi (componente <strong>Value</strong>)</li>
<li>L'indice del record corrente (componente <strong>Number</strong>)</li>
</ul></td>
<td>Nella seguente illustrazione, un'origine dati <strong>Enumerated</strong> viene creata come elenco enumerato di record fornitori dall'origine dati <strong>Vendors</strong> che fa riferimento alla tabella VendTable.
<p><a href="./media/picture-enumerate-datasource.jpg"><img src="./media/picture-enumerate-datasource.jpg" alt="Enumerated data source" class="alignnone wp-image-290711 size-full" width="387" height="136" /></a></p>
<p>Nella figura seguente è illustrato il formato. In questo formato, le associazioni dati vengono create per generare l'output in formato XML. Questo output presenta i singoli fornitori come nodi enumerati.</p>
<p><a href="./media/picture-enumerate-format.jpg"><img src="./media/picture-enumerate-format.jpg" alt="Format that has data bindings" class="alignnone wp-image-290721 size-full" width="414" height="138" /></a></p>
<p>Nella figura seguente è illustrato il risultato dell'esecuzione del formato progettato.</p>
<a href="./media/picture-enumerate-result.jpg"><img src="./media/picture-enumerate-result.jpg" alt="Result of running the format" class="alignnone wp-image-290731 size-full" width="567" height="176" /></a></td>
</tr>
<tr class="odd">
<td>COUNT (elenco)</td>
<td>Restituisce il numero di record nell'elenco specificato, se l'elenco non è vuoto. In caso contrario, restituisce <strong>0</strong> (zero).</td>
<td><strong>COUNT (SPLIT(&quot;abcd&quot; , 3))</strong> restituisce <strong>2</strong>, perché la funzione <strong>SPLIT</strong> crea un elenco costituito da due record.</td>
</tr>
<tr class="even">
<td>LISTOFFIELDS (percorso)</td>
<td>Restituisce un elenco di record creato da un argomento di uno dei seguenti tipi:
<ul>
<li>Enumerazione modello</li>
<li>Enumerazione formato</li>
<li>Contenitore</li>
</ul>
<p>L'elenco creato contiene record con i seguenti campi:</p>
<ul>
<li>Nome</li>
<li>Etichetta</li>
<li>descrizione</li>
</ul>
I campi <strong>Descrizione</strong> ed <strong>Etichetta</strong> restituiscono valori in fase esecuzione in base alle impostazioni di lingua del formato.</td>
<td>Nella seguente figura viene illustrata l'enumerazione introdotta in un modello dati.
<p><a href="./media/ger-listoffields-function-model-enumeration.png"><img src="./media/ger-listoffields-function-model-enumeration-e1474545790761.png" alt="Enumeration in a model" class="alignnone wp-image-1203943 size-full" width="514" height="155" /></a></p>
<p>La figura di seguito mostra questi dettagli:</p>
<ul>
<li>L'enumerazione del modello viene inserita in un report come origine dei dati.</li>
<li>Un'espressione ER utilizza l'enumerazione modello come parametro della funzione <strong>LISTOFFIELDS</strong>.</li>
<li>Un'origine dati del tipo di elenco record viene inserita in un report mediante l'espressione ER creata.</li>
</ul>
<p><a href="./media/ger-listoffields-function-in-format-expression.png"><img src="./media/ger-listoffields-function-in-format-expression-e1474546110395.png" alt="Format" class="alignnone wp-image-1204033 size-full" width="549" height="318" /></a></p>
<p>L'esempio seguente illustra gli elementi di formato ER che sono limitati all'origine dati del tipo elenco record creato utilizzando la funzione di <strong>LISTOFFIELDS</strong>.</p>
<p><a href="./media/ger-listoffields-function-format-design.png"><img src="./media/ger-listoffields-function-format-design.png" alt="Format design" class="alignnone size-full wp-image-1204043" width="466" height="221" /></a></p>
<p>Nella figura seguente è illustrato il risultato dell'esecuzione del formato progettato.</p>
<p><a href="./media/ger-listoffields-function-format-output.png"><img src="./media/ger-listoffields-function-format-output.png" alt="Format output" class="alignnone size-full wp-image-1204053" width="585" height="158" /></a></p>
<blockquote>[!NOTE]<br>
Il testo tradotto per le etichette e le descrizioni viene immesso nell'output del formato ER in base alle impostazioni di lingua configurate per gli elementi di formato FILE e CARTELLA padre.</blockquote></td>
</tr>
<tr class="odd">
<td>LISTOFFIELDS (percorso, lingua)</td>
<td>Restituisce un elenco di record creato da un argomento, ad esempio enumerazione modello, enumerazione formato o un contenitore. L'elenco creato contiene record con i seguenti campi:
<ul>
<li>Nome</li>
<li>Etichetta</li>
<li>descrizione</li>
<li>È tradotto</li>
</ul>
<p>I campi <strong>Descrizione</strong> ed <strong>Etichetta</strong> restituiscono valori in fase esecuzione in base alle impostazioni di lingua del formato e alla lingua specificata. Il campo <strong>È tradotto</strong> indica che il campo <strong>Etichetta</strong> è stato tradotto nella lingua specificata.</td>
<td>Ad esempio, usare il tipo di origine dati <strong>Campo calcolato</strong> per configurare le origini dati <strong>enumType_de</strong> e <strong>enumType_deCH</strong> per l''enumerazione del modello dati <strong>enumType</strong>:
<ul>
<li>enumType_de = <strong>LISTOFFIELDS</strong> (enumType, &quot;de&quot;)</li>
<li>enumType_deCH = <strong>LISTOFFIELDS</strong> (enumType, &quot;de-CH&quot;)</li>
</ul>
In questo caso, è possibile utilizzare la seguente espressione per visualizzare l'etichetta del valore enumerato in tedesco svizzero, se la traduzione è disponibile. Se la traduzione tedesca svizzera non è disponibile, l'etichetta appare in tedesco: <strong>IF (NOT (enumType_deCH.IsTranslated), enumType_de.Label, enumType_deCH.Label)</strong>.</td>
</tr>
<tr class="even">
<td>STRINGJOIN (elenco, nome del campo, delimitatore)</td>
<td>Restituisce una stringa costituita da valori concatenati del campo specificato dell'elenco specificato. I valori sono separati dal delimitatore specificato.</td>
<td>Se è stato immesso <strong>SPLIT(&quot;abc&quot; , 1)</strong> come origine dati (DS), l'espressione <strong>STRINGJOIN (DS, DS.Value, &quot;:&quot;)</strong> restituisce <strong>&quot;a:b:c&quot;</strong>.</td>
</tr>
<tr class="odd">
<td>SPLITLISTBYLIMIT (elenco, valore limite, origine limite)</td>
<td>Divide l'elenco specificato in nuovo elenco di sottoelenchi e restituisce il risultato nel contenuto dell'elenco di record. Il parametro di valore limite definisce il valore del limite per la divisione dell'elenco originale. Il parametro di origine limite definisce il passaggio secondo cui viene incrementata la somma totale. Il limite non è applicato a un singolo articolo dell'elenco originale se l'origine limite supera il limite definito.</td>
<td>Nelle figure seguenti viene illustrato un formato e le origini dati per esso utilizzate. 
<p><a href="./media/ger-splitlistbylimit-format.png"><img src="./media/ger-splitlistbylimit-format.png" alt="Format" class="alignnone size-full wp-image-1204063" width="396" height="195" /></a></p>
<p><a href="./media/ger-splitlistbylimit-datasources.png"><img src="./media/ger-splitlistbylimit-datasources.png" alt="Data sources" class="alignnone size-full wp-image-1204073" width="320" height="208" /></a></p>
<p>Nella figura seguente è illustrato il risultato dell'esecuzione del formato. In questo caso, l'output è un elenco di voci doganali.</p>
<p><a href="./media/ger-splitlistbylimit-output.png"><img src="./media/ger-splitlistbylimit-output.png" alt="Output" class="alignnone size-full wp-image-1204083" width="462" height="204" /></a></p>
<p>Nelle illustrazioni seguenti, lo stesso formato è stato rettificato per presentare l'elenco di voci doganali in batch quando un singolo batch deve includere voci doganali e il peso totale che non deve superare il limite di 9.</p>
<p><a href="./media/ger-splitlistbylimit-format-1.png"><img src="./media/ger-splitlistbylimit-format-1.png" alt="Adjusted format" class="alignnone size-full wp-image-1204103" width="466" height="438" /></a></p>
<p><a href="./media/ger-splitlistbylimit-datasources-1.png"><img src="./media/ger-splitlistbylimit-datasources-1.png" alt="Data sources for the adjusted format" class="alignnone size-full wp-image-1204093" width="645" height="507" /></a></p>
<p>Nella figura seguente è illustrato il risultato dell'esecuzione del formato rettificato.</p>
<p><a href="./media/ger-splitlistbylimit-output-1.png"><img src="./media/ger-splitlistbylimit-output-1.png" alt="Output of the adjusted format" class="alignnone size-full wp-image-1204113" width="676" height="611" /></a></p>
<blockquote>[!NOTE]<br>
Il limite non si applica all'ultima voce dell'elenco di origine poiché il valore (11) dell'origine del limite (peso) supera il limite definito (9). Utilizzare la funzione <strong>WHERE</strong> o l'espressione <strong>Enabled</strong> dell'elemento formato corrispondente per ignorare (saltare) i sottoelenchi durante la generazione dei report come necessario.</blockquote></td>
</tr>
<tr class="even">
<td>FILTER (elenco, condizione)</td>
<td>Restituisce l'elenco specificato dopo che è stata modifica la query per il filtro in base alla condizione specifica. Diversamente dalla funzione <strong>WHERE</strong>, la condizione specificata viene applicata a livello di database a qualsiasi origine dati ER del tipo di <strong>Record tabella</strong>. L'elenco e la condizione possono essere definite mediante le tabelle e le relazioni.</td>
  <td>Se <strong>Vendor</strong> viene configurato come origine dati ER che fa riferimento alla tabella VendTable, <strong>FILTER (Vendors, Vendors.VendGroup = &quot;40&quot;)</strong> restituisce un elenco solo dei fornitori che appartengono al gruppo 40. Se <strong>Fornitore</strong> viene configurato come origine dati ER che fa riferimento alla tabella <strong>VendTable</strong> e <strong>parmVendorBankGroup</strong> che è configurato come origine dati ER restituisce il valore in tipo di dati stringa, <strong>FILTER (Vendor.'&lt;Relations'.VendBankAccount, Vendor.'&lt;Relations'.VendBankAccount.BankGroupID = parmVendorBankGroup)</strong> restituisce solo un elenco di conti fornitori che appartengono a un gruppo bancario specifico.</td>
</tr>
</tbody>
</table>

### <a name="logical-functions"></a>Funzioni logiche

| Funzione | descrizione | Esempio |
|----------|-------------|---------|
| CASE (espressione, opzione 1, risultato 1 \[, opzione 2, risultato 2\] … \[, risultato predefinito\]) | Confronta il valore specificato di espressione rispetto alle opzioni alternative specificate. Restituisce il risultato dell'opzione che è uguale al valore dell'espressione. In caso contrario, restituisce il risultato predefinito facoltativo, se è specificato. Il risultato predefinito è l'ultimo parametro che non è preceduto da un'opzione. | **CASE( DATETIMEFORMAT( NOW(), "MM"), "10", "WINTER", "11", "WINTER", "12", "WINTER", "")** restituisce la stringa **"WINTER"** quando la data della sessione corrente di Finance and Operations è compresa tra ottobre e dicembre. In caso contrario, restituisce una stringa vuota. |
| IF (condizione, valore 1, valore 2) | Restituisce il primo valore specificato quando viene soddisfatta la condizione specificata. In caso contrario, restituisce il secondo valore specificato. Se il valore 1 e il valore 2 sono record o elenchi di record, il risultato ha solo i campi che sono in entrambi gli elenchi. | **IF (1=2, "condizione soddisfatta", "condizione non soddisfatta")** restituisce la stringa **"condizione non soddisfatta"**. |
| NOT (condizione) | Restituisce il valore logico inverso della condizione specificata. | **NOT (TRUE)** restituisce **FALSE**. |
| AND (condizione 1\[, condizione 2, …\]) | Restituisce **TRUE** se *tutte* le condizioni specificate sono vere. In caso contrario, restituisce **FALSE**. | **AND (1=1, "a"="a")** restituisce **TRUE**. **AND (1=2, "a"="a")** restituisce **FALSE**. |
| OR (condizione 1\[, condizione 2, …\]) | Restituisce **FALSE** se *tutte* le condizioni specificate sono false. Restituisce **TRUE** se *qualsiasi* condizione specificata è vera. | **OR (1=2, "a"="a")** restituisce **TRUE**. |

### <a name="mathematical-functions"></a>Funzioni matematiche

| Funzione | Descrizione | Esempio |
|----------|-------------|---------|
| ABS (number) | Restituisce il valore assoluto del numero specificato. Ovvero restituisce il numero senza il segno. | **ABS (-1)** restituisce **1**. |
| POWER (numero, potenza) | Restituisce il risultato dell'elevazione alla potenza specificata del numero positivo specificato. | **POWER (10, 2)** restituisce **100**. |
| NUMBERVALUE (stringa, separatore decimale, separatore di raggruppamento delle cifre) | Converte la stringa specificata in numero. Il separatore decimale specificato viene utilizzato tra il numero intero e le parti frazionarie di un numero decimale. Il separatore di raggruppamento di cifre specificato viene utilizzato come separatore delle migliaia. | **NUMBERVALUE("1 234,56", ",", " ")** restituisce il valore **1234.56**. |
| VALUE (stringa) | Converte la stringa specificata in numero. Le virgole e i caratteri punto (). vengono considerati separatori decimali e un trattino iniziale (-) viene utilizzato come negativo. Genera un'eccezione se altri caratteri non numerici vengono incontrati nella stringa specificata. | **VALUE ("1 234,56")** genera un'eccezione. |
| ROUND (numero, decimali) | Restituisce il numero specificato dopo che è stato arrotondato al numero di posizioni decimali specificato:<ul><li>Se il valore del parametro dei decimali specificato è maggiore di 0 (zero), il numero specificato viene arrotondato al numero di posizioni decimali specificato.</li><li>Se il valore del parametro dei decimali specificato è **0** (zero), il numero specificato viene arrotondato all'intero più vicino.</li><li>Se il valore del parametro dei decimali specificato è minore di 0 (zero), il numero specificato viene arrotondato a sinistra del separatore decimale.</li></ul> | **ROUND (1200.767, 2)** arrotonda a due posti decimali e restituisce **1200.77**. **ROUND (1200.767, -3)** arrotonda al più vicino multiplo di 1000 e restituisce **1000**. |
| ROUNDDOWN (numero, decimali) | Restituisce il numero specificato dopo che è stato arrotondato per difetto al numero di posizioni decimali specificato.<blockquote>[!NOTE]<br>Questa funzione si comporta analogamente a <strong>ROUND</strong> ma sempre per difetto (verso lo zero).</blockquote> | **ROUNDDOWN (1200.767, 2)** arrotonda per difetto a due posti decimali e restituisce **1200.76**. **ROUNDDOWN (1700.767, -3)** arrotonda per difetto al più vicino multiplo di 1000 e restituisce **1000**. |
| ROUNDUP (numero, decimali) | Restituisce il numero specificato dopo che è stato arrotondato per eccesso al numero di posizioni decimali specificato.<blockquote>[!NOTE]<br>Questa funzione si comporta analogamente a <strong>ROUND</strong> ma sempre per eccesso (lontano da zero).</blockquote> | **ROUNDUP (1200.763, 2)** arrotonda per eccesso a due posti decimali e restituisce **1200.77**. **ROUNDUP (1200.767, -3)** arrotonda per eccesso al più vicino multiplo di 1000 e restituisce **2000**. |

### <a name="data-conversion-functions"></a>Funzioni conversione dati

| Funzione | descrizione | Esempio |
|----------|-------------|---------|
| VALUE (stringa) | Converte la stringa specificata in numero. Le virgole e i caratteri punto (). vengono considerati separatori decimali e un trattino iniziale (-) viene utilizzato come negativo. Genera un'eccezione se altri caratteri non numerici vengono incontrati nella stringa specificata. | **VALUE ("1 234,56")** genera un'eccezione. |
| NUMBERVALUE (stringa, separatore decimale, separatore di raggruppamento delle cifre) | Converte la stringa specificata in numero. Il separatore decimale specificato viene utilizzato tra il numero intero e le parti frazionarie di un numero decimale. Il separatore di raggruppamento di cifre specificato viene utilizzato come separatore delle migliaia. | **NUMBERVALUE("1 234,56", ",", " ")** restituisce **1234.56**. |
| INTVALUE (stringa) | Restituisce una rappresentazione integer della stringa specificata. Tutte le posizioni decimali sono troncate. | **INTVALUE ("100.77")** restituisce **100**. |
| INTVALUE (numero) | Restituisce una rappresentazione integer del numero specificato. Tutte le posizioni decimali sono troncate. | **INTVALUE (-100.77)** restituisce **-100**. |
| INT64VALUE (stringa) | Restituisce una rappresentazione int64 della stringa specificata. Tutte le posizioni decimali sono troncate. | **INT64VALUE ("22565422744")** restituisce **22565422744**. |
| INT64VALUE (number) | Restituisce una rappresentazione int64 del numero specificato. Tutte le posizioni decimali sono troncate. | **INT64VALUE (22565422744.00)** restituisce **22565422744**. |

### <a name="record-functions"></a>Funzioni di record

| Funzione | descrizione | Esempio |
|----------|-------------|---------|
| NULLCONTAINER (elenco) | Restituisce un record **null** con la stessa struttura dell'elenco di record o il record specificato.<blockquote>[!NOTE]<br>Questa funzione è obsoleta. Utilizzare <strong>EMPTYRECORD</strong> invece.</blockquote> | **NULLCONTAINER (SPLIT ("abc", 1))** restituisce un nuovo record vuoto con la stessa struttura dell'elenco restituito dalla funzione **SPLIT**. |
| EMPTYRECORD (record) | Restituisce un record **null** con la stessa struttura dell'elenco di record o il record specificato.<blockquote>[!NOTE]<br>Un record <strong>null</strong> è un record in cui il valore di tutti i campi è vuoto. Un valore vuoto è <strong>0</strong> (zero) per i numeri, stringa vuota per le stringhe e così via.</blockquote> | **EMPTYRECORD (SPLIT ("abc", 1))** restituisce un nuovo record vuoto con la stessa struttura dell'elenco restituito dalla funzione **SPLIT**. |

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
<th>descrizione</th>
<th>Esempio</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>UPPER (stringa)</td>
<td>Restituisce la stringa specificata dopo che è stata convertita in lettere maiuscole.</td>
<td><strong>UPPER(&quot;Esempio&quot;)</strong> restituisce <strong>&quot;ESEMPIO&quot;</strong>.</td>
</tr>
<tr class="even">
<td>LOWER (stringa)</td>
<td>Restituisce la stringa specificata dopo che è stata convertita in lettere minuscole.</td>
<td><strong>LOWER (&quot;Esempio&quot;)</strong> restituisce <strong>&quot;esempio&quot;</strong>.</td>
</tr>
<tr class="odd">
<td>LEFT (stringa, numero di caratteri)</td>
<td>Restituisce il numero specificato di caratteri a partire dall'inizio di una stringa specificata.</td>
<td><strong>LEFT (&quot;Esempio&quot;, 3)</strong> restituisce <strong>&quot;Ese&quot;</strong>.</td>
</tr>
<tr class="even">
<td>RIGHT (stringa, numero di caratteri)</td>
<td>Restituisce il numero specificato di caratteri a partire dalla fine di una stringa specificata.</td>
<td><strong>RIGHT (&quot;Esempio&quot;, 3)</strong> restituisce <strong>&quot;pio&quot;</strong>.</td>
</tr>
<tr class="odd">
<td>MID (stringa, posizione iniziale, numero di caratteri)</td>
<td>Restituisce il numero specificato di caratteri della stringa specificata a partire dalla posizione specificata.</td>
<td><strong>MID (&quot;Esempio&quot;, 2, 3)</strong> restituisce <strong>&quot;sem&quot;</strong>.</td>
</tr>
<tr class="even">
<td>LEN (stringa)</td>
<td>Restituisce il numero di caratteri nella stringa specificata.</td>
<td><strong>LEN (&quot;Esempio&quot;)</strong> restituisce <strong>6</strong>.</td>
</tr>
<tr class="odd">
<td>CHAR (numero)</td>
<td>Restituisce la stringa di caratteri a cui viene fatto riferimento dal numero Unicode specificato.</td>
<td><strong>CHAR (255)</strong> restituisce <strong>&quot;ÿ&quot;</strong>.
<blockquote>[!NOTE]<br>
La stringa restituita dalla funzione dipende dalla codifica selezionata nell'elemento del formato FILE padre. Per l'elenco di codifiche supportate, vedere <a href="https://msdn.microsoft.com/en-us/library/system.text.encoding(v=vs.110).aspx">Classe di codifica</a>.</blockquote>
</td>
</tr>
<tr class="even">
<td>CONCATENATE (stringa 1 [, stringa 2, …])</td>
<td>Restituisce tutte le stringhe di testo specificate dopo che sono state unite in un'unica stringa.</td>
<td><strong>CONCATENATE (&quot;abc&quot;, &quot;def&quot;)</strong> restituisce <strong>&quot;abcdef&quot;</strong>.
<blockquote>[!NOTE]<br>
Anche l'espressione <strong>&quot;abc&quot; &amp; &quot;def&quot;</strong> restituisce <strong>&quot;abcdef&quot;</strong>.</blockquote>
</td>
</tr>
<tr class="odd">
<td>TRANSLATE (stringa, modello, sostituzione)</td>
<td>Restituisce la stringa specificata dopo che tutte le occorrenze dei caratteri la stringa modello specificata sono state sostituite dai caratteri alla posizione corrispondente della stringa di sostituzione specificata.</td>
<td><strong>TRANSLATE (&quot;abcdef&quot;, &quot;cd&quot;, &quot;GH&quot;)</strong> sostituisce il modello <strong>&quot;cd&quot;</strong> con la stringa <strong>&quot;GH&quot;</strong> e restituisce <strong>&quot;abGHef&quot;</strong>.</td>
</tr>
<tr class="even">
<td>REPLACE (stringa, modello, sostituzione, flag espressione regolare)</td>
<td>Quando il flag espressione regolare specificato è <strong>true</strong>, restituisce la stringa specificata dopo che è stata modificata applicando l'espressione regolare specificata come un argomento di modello per la funzione. Tale espressione viene utilizzata per individuare i caratteri che devono essere sostituiti. I caratteri dell'argomento di sostituzione specificato vengono utilizzati per sostituire i caratteri che si trovano. Quando il flag specificato espressione regolare è <strong>false</strong>, questa funzione si comporta analogamente a <strong>TRANSLATE</strong>.</td>
<td><strong>REPLACE (&quot;+1 923 456 4971&quot;, &quot;[^0-9]&quot;, &quot;&quot;, true)</strong> applica un'espressione regolare che rimuove tutti i simboli non numerici e restituisce <strong>&quot;19234564971&quot;</strong>. <strong>REPLACE (&quot;abcdef&quot;, &quot;cd&quot;, &quot;GH&quot;, false)</strong> sostituisce il modello <strong>&quot;cd&quot;</strong> con la stringa <strong>&quot;GH&quot;</strong> e restituisce <strong>&quot;abGHef&quot;</strong>.</td>
</tr>
<tr class="odd">
<td>TEXT (input)</td>
<td>Restituisce l'input specificato dopo che è stato convertito in stringa di testo che viene formattata in base alle impostazioni locali server dell'istanza corrente di Finance and Operations. Per i valori di tipo <strong>real</strong>, la conversione di stringhe è limitata a due posizioni decimali.</td>
<td>Se le impostazioni locali server dell'istanza di Finance and Operations vengono definite come <strong>EN-US</strong>, <strong>TEXT (NOW ())</strong> restituisce la data della sessione corrente di Finance and Operations, 17 dicembre 2015, come la stringa di testo <strong>&quot;12/17/2015 07:59:23 AM&quot;</strong>. <strong>TEXT (1/3)</strong> restituisce <strong>&quot;0.33&quot;</strong>.</td>
</tr>
<tr class="even">
<td>FORMAT (stringa 1, stringa 2[, stringa 3, …])</td>
<td>Restituisce la stringa specificata dopo che è stata formattata sostituendo tutte le occorrenze di <strong>%N</strong> con l'argomento <em>n-esimo</em>. Gli argomenti sono stringhe. Se un argomento non viene fornito per un parametro, il parametro viene restituito come <strong>&quot;%N&quot;</strong> nella stringa. Per i valori di tipo <strong>real</strong>, la conversione di stringhe è limitata a due posizioni decimali.</td>
<td>In questa illustrazione, l'origine dati <strong>PaymentModel</strong> restituisce l'elenco dei record cliente tramite il componente <strong>Customer</strong> il valore della data di elaborazione tramite il campo <strong>ProcessingDate</strong>.
<p><a href="./media/picture-format-datasource.jpg"><img src="./media/picture-format-datasource.jpg" alt="PaymentModel data source" class="alignnone wp-image-290751 size-full" width="293" height="143" /></a></p>
<p>Nel formato ER che è progettato per generare un file elettronico per i clienti selezionati, <strong>PaymentModel</strong> è selezionato come origine dati e controlla il flusso di processo. Un'eccezione viene generata per informare l'utente quando un cliente selezionato viene interrotto per la data in cui il report viene elaborato. La formula che è stata progettata per questo tipo di controllo di processo può utilizzare le risorse indicate di seguito:</p>
<ul>
<li>Etichetta SYS70894 di Finance and Operations, con il testo seguente:
<ul>
<li><strong>Per la lingua EN-US:</strong> &quot;Nothing to print&quot;</li>
<li><strong>Per la lingua DE:</strong> &quot;Nichts zu drucken&quot;</li>
</ul></li>
<li>Etichetta SYS18389 di Finance and Operations, con il testo seguente:
<ul>
<li><strong>Per la lingua EN-US:</strong> &quot;Customer %1 is stopped for %2.&quot;</li>
<li><strong>Per la lingua DE:</strong> &quot;Debitor '%1' wird für %2 gesperrt.&quot;</li>
</ul></li>
</ul>
<p>Questa è la formula che può essere progettata:</p>
<p>FORMAT (CONCATENATE (@&quot;SYS70894&quot;, &quot;. &quot;, @&quot;SYS18389&quot;), model.Customer.Name, DATETIMEFORMAT (model.ProcessingDate, &quot;d&quot;))</p>
<p>Se un report viene elaborato per il cliente <strong>Litware Retail</strong> il 17 dicembre 2015, nelle impostazioni cultura <strong>EN-US</strong> e la lingua <strong>EN-US</strong>, questa formula restituisce il seguente testo, che può essere presentato come un messaggio di eccezione all'utente:</p>
<p>&quot;Nothing to print. Customer Litware Retail is stopped for 12/17/2015.&quot;</p>
<p>Se lo stesso viene elaborato per il cliente <strong>Litware Retail</strong> il 17 dicembre 2015, nelle impostazioni culture <strong>DE</strong> e la lingua <strong>DE</strong>, la formula restituisce il seguente testo, che utilizza un formato della data diverso:</p>
<p>&quot;Nichts zu drucken. Debitor 'Litware Retail' wird für 17.12.2015 gesperrt.&quot;</p>
<blockquote>[!NOTE]<br>
La seguente sintassi si applica nelle formule ER per le etichette:
<ul>
<li><strong>Per le etichette di risorse di Finance and Operations:</strong> <strong>@&quot;X&quot;</strong>, dove X è l'ID etichetta nella struttura a oggetti applicativi (AOT, Application Object Tree)</li>
<li><strong>Per le etichette che si trovano in configurazioni ER:</strong> <strong>@&quot;GER_LABEL:X&quot;</strong>, dove X è l'ID di etichetta nella configurazione ER</li>
</ul></blockquote></td>
</tr>
<tr class="odd">
<td>NUMBERFORMAT (numero, formato)</td>
<td>Restituisce una rappresentazione di stringa del numero specificato nel formato specificato. (Per informazioni sui formati supportati, vedere <a href="https://msdn.microsoft.com/en-us/library/dwhawy9k(v=vs.110).aspx">standard</a> e <a href="https://msdn.microsoft.com/en-us/library/0c899ak8(v=vs.110).aspx">personalizzato</a>). Il contesto in cui questa funzione viene eseguita determina la lingua utilizzata per formattare i numeri.</td>
<td>Per le impostazioni cultura EN-US, <strong>NUMBERFORMAT (0.45, &quot;p&quot;)</strong> restituisce <strong>&quot;45.00 %&quot;</strong>. <strong>NUMBERFORMAT (10.45, &quot;#&quot;)</strong> restituisce <strong>&quot;10&quot;</strong>.</td>
</tr>
<tr class="even">
<td>NUMERALSTOTEXT (numero, lingua, valuta, flag stampa nome valuta, decimali)</td>
<td>Restituisce il numero specificato dopo che è stato contabilizzato (convertito) in stringhe di testo nella lingua definita. Il codice lingua è facoltativo. Quando definito come stringa vuota, viene utilizzato il codice lingua per il contesto di esecuzione. Il codice lingua per il contesto di esecuzione viene definito per una cartella o un file di generazione. Anche il codice valuta è facoltativo. Quando viene definito come stringa vuota, viene utilizzata la valuta della società.
<blockquote>[!NOTE]<br>
I parametri Flag stampa nome valuta e Decimali vengono analizzati soltanto per i seguenti codici lingua: <strong>CS</strong>, <strong>ET</strong>, <strong>HU</strong>, <strong>LT</strong>, <strong>LV</strong>, <strong>PL</strong> e <strong>RU</strong>. Inoltre, il parametro Flag stampa nome valuta viene analizzato solo per le società Finance and Operations in cui il contesto del paese o area supporta la declinazione dei nomi valuta.</blockquote></td>
<td><strong>NUMERALSTOTEXT (1234.56, &quot;EN&quot;, &quot;&quot;, false, 2)</strong> restituisce <strong>&quot;One Thousand Two Hundred Thirty Four and 56&quot;</strong>. <strong>NUMERALSTOTEXT (120, &quot;PL&quot;, &quot;&quot;, false, 0)</strong> restituisce <strong>&quot;Sto dwadzieścia&quot;</strong>. <strong>NUMERALSTOTEXT (120.21, &quot;RU&quot;, &quot;EUR&quot;, true, 2)</strong> restituisce <strong>&quot;Сто двадцать евро 21 евроцент&quot;</strong>.</td>
</tr>
<tr class="odd">
<td>PADLEFT (stringa, lunghezza, caratteri di riempimento)</td>
<td>Restituisce una stringa della lunghezza specificata in cui l'inizio della stringa specificata viene riempita con i caratteri specificati.</td>
<td><strong>PADLEFT (&quot;1234&quot;, 10, &quot;&nbsp;&quot;)</strong> restituisce la stringa di testo <strong>&quot;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;1234&quot;</strong>.</td>
</tr>
<tr class="even">
<td>TRIM (stringa)</td>
<td>Restituisce la stringa di testo specificata dopo il troncamento degli spazi iniziali e finali e la rimozione di più spazi tra le parole in spazi singoli.</td>
<td><strong>TRIM (&quot;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Sample&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;text&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&quot;)</strong> restituisce <strong>&quot;Sample text&quot;</strong>.</td>
</tr>
<tr class="odd">
<td>GETENUMVALUEBYNAME (percorso origine dati di enumerazione, testo dell'etichetta del valore dell'enumerazione)</td>
<td>Restituisce un valore dell'origine dati di enumerazione specificata in base al testo specificato dall'etichetta dell'enumerazione.</td>
<td>Nella seguente figura viene illustrata l'enumerazione <strong>ReportDirection</strong> introdotta in un modello dati. Tenere presente che le etichette vengono definite per i valori dell'enumerazione.
<p><a href="./media/ER-data-model-enumeration-values.PNG"><img src="./media/ER-data-model-enumeration-values.PNG" alt="Available values for data model enumeration" class="alignnone wp-image-290681 size-full" width="397" height="136" /></a></p>
<p>La figura di seguito mostra questi dettagli:</p>
<ul>
<li>L'enumerazione modello <strong>ReportDirection</strong> viene inserita in un report come origine dati <strong>$Direction</strong>.</li>
<li>Un'espressione ER <strong>$IsArrivals</strong> viene progettata per l'utilizzo dell'enumerazione di modello come parametro di questa funzione. Il valore di questa condizione è <strong>TRUE</strong>.</li>
</ul>
<a href="./media/ER-data-model-enumeration-usage.PNG"><img src="./media/ER-data-model-enumeration-usage.PNG" alt="Example of data model enumeration" class="alignnone wp-image-290681 size-full" width="397" height="136" /></a></td>
</tr>
</tbody>
</table>

### <a name="data-conversion-functions"></a>Funzioni conversione dati

| Funzione | descrizione | Esempio |
|----------|-------------|---------|
| TEXT (input) | Restituisce l'input specificato dopo che è stato convertito in stringa di testo che viene formattata in base alle impostazioni locali server dell'istanza corrente di Finance and Operations. Per i valori di tipo **real**, la conversione di stringhe è limitata a due posizioni decimali. | Se le impostazioni locali server dell'istanza di Finance and Operations vengono definite come **EN-US**, **TEXT (NOW ())** restituisce la data della sessione corrente di Finance and Operations, 17 dicembre 2015, come la stringa di testo **"12/17/2015 07:59:23 AM"**. **TEXT (1/3)** restituisce **"0.33"**. |
| QRCODE (stringa) | Restituisce l'immagine del codice QR in formato binario base64 per la stringa specificata. | **QRCODE ("Testo di esempio")** restituisce **U2FtcGxlIHRleHQ=**. |

### <a name="data-collection-functions"></a>Funzioni raccolta dati

| Funzione | descrizione | Esempio |
|----------|-------------|---------|
| FORMATELEMENTNAME () | Restituisce il nome dell'elemento del formato corrente. Restituisce la stringa vuota se il flag **Raccogli dettagli di output** del file corrente è disattivato. | Per ulteriori informazioni sull'utilizzo di questa funzione, fare riferimento alla guida attività **ER Utilizzare i dati dell'output del formato per il conteggio e la somma** che è parte del processo aziendale **Acquisire/sviluppare componenti di soluzioni/servizi IT**. |
| SUMIFS (stringa chiave per somma, stringa intervallo di criteri1, stringa valore di criteri1 \[, stringa intervallo di criteri2, stringa valore di criteri2, …\]) | Restituisce la somma dei valori dei nodi XML (in cui il nome viene definito come chiave) che sono stati raccolti durante l'esecuzione del formato e che soddisfano le condizioni specificate (coppie di intervallo e valore). Restituisce il valore **0** (zero) se il flag **Raccogli dettagli di output** del file corrente è disattivato. | |
| SUMIF (stringa chiave per somma, stringa intervallo di criteri, stringa valore di criteri) | Restituisce la somma dei valori dei nodi XML (in cui il nome viene definito come chiave) che sono stati raccolti durante l'esecuzione del formato e che soddisfano la condizione specificata (intervallo e valore). Restituisce il valore **0** (zero) se il flag **Raccogli dettagli di output** del file corrente è disattivato. | |
| COUNTIFS (stringa chiave per somma, stringa intervallo di criteri1, stringa valore di criteri1 \[, stringa intervallo di criteri2, stringa valore di criteri2, …\]) | Restituisce il numero dei nodi dell'XML che è stato raccolto durante l'esecuzione del formato e che soddisfa le condizioni specificate (coppie di intervalli e valori). Restituisce il valore **0** (zero) se il flag **Raccogli dettagli di output** del file corrente è disattivato. | |
| COUNTIF (stringa intervallo di criteri, stringa valore di criteri) | Restituisce il numero dei nodi dell'XML che è stato raccolto durante l'esecuzione del formato e che soddisfa la condizione immessa (intervallo e valore). Restituisce il valore **0** (zero) se il flag **Raccogli dettagli di output** del file corrente è disattivato. | |
| COLLECTEDLIST (stringa chiave per somma, stringa intervallo di criteri1, stringa valore di criteri1 \[, stringa intervallo di criteri2, stringa valore di criteri2, …\]) | Restituisce un elenco di valori dei nodi dell'XML raccolto durante l'esecuzione del formato e che soddisfa le condizioni specificate (intervallo e valore). Restituisce un elenco vuoto quando il flag **Raccogli dettagli di output** del file corrente è disattivato. | |

### <a name="other-business-domainspecific-functions"></a>Altre funzioni (specifiche del dominio aziendale)

| Funzione | descrizione | Esempio |
|----------|-------------|---------|
| CONVERTCURRENCY (importo, valuta di origine, valuta di destinazione, data, società) | Converte l'importo monetario specificato da valuta di origine specificata nella valuta di destinazione specificata utilizzando le impostazioni della società specificata di Finance and Operations alla data specificata. | **CONVERTCURRENCY (1, "EUR", "USD", TODAY(), "DEMF")** restituisce un equivalente di un euro in dollari statunitensi nella data della sessione corrente, in base alle impostazioni per la società DEMF. |
| ROUNDAMOUNT (numero, decimali, regola arrotondamento) | Arrotonda l'importo specificato al numero specificato posizioni decimali in base alla regola di arrotondamento specificata.<blockquote>[!NOTE]<br>La regola di arrotondamento deve essere specificata come valore di enumerazione <strong>RoundOffType</strong> di Finance and Operations.</blockquote> | Se il parametro **model.RoundOff** è impostato su **Downward**, **ROUNDAMOUNT (1000.787, 2, model.RoundOff)** restituisce il valore **1000.78**. Se il parametro **model.RoundOff** è impostato su **Normal** o **Rounding-up**, **ROUNDAMOUNT (1000.787, 2, model.RoundOff)** restituisce il valore **1000.79**. |
| CURCredRef (cifre) | Restituisce un riferimento creditore, in base alle cifre del numero di fattura specificato. | **CURCredRef ("VEND-200002")** restituisce **"2200002"**. |
| MOD\_97 (cifre) | Restituisce un riferimento creditore come espressione MOD97, in base alle cifre del numero di fattura specificato. | **MOD\_97 ("VEND-200002")** restituisce **"20000285"**. |
| ISOCredRef (cifre) | Restituisce un riferimento creditore International Organization for Standardization (ISO), in base alle cifre e ai simboli alfabetici del numero di fattura specificato.<blockquote>[!NOTE]<br>Per eliminare i simboli da alfabeti che non sono conformi ISO, il parametro di input deve essere tradotto prima di passarlo alla funzione.</blockquote> | **ISOCredRef ("VEND-200002")** restituisce **"RF23VEND-200002"**. |
| CN\_GBT\_AdditionalDimensionID (stringa, numero) | Ottenere l'ID dimensione finanziaria aggiuntiva. Le dimensioni sono rappresentate nella stringa come ID che sono separati da virgole. In questa stringa, i numeri definiscono il codice di sequenza della dimensione richiesta. | **CN\_GBT\_AdditionalDimensionID ("AA,BB,CC,DD,EE,FF,GG,HH",3)** restituisce **"CC"**. |
| GetCurrentCompany () | Restituisce la rappresentazione in formato testo del codice della persona giuridica (società) a cui un utente è attualmente connesso. | **GETCURRENTCOMPANY ()** restituisce **USMF** per un utente collegato alla società **Contoso Entertainment System USA** di Finance and Operations. |
| CH\_BANK\_MOD\_10 (cifre) | Restituisce un riferimento creditore come un'espressione MOD10, in base alle cifre del numero di fattura specificato. | **CH\_BANK\_MOD\_10 ("VEND-200002")** restituisce **3**. |
| FA\_SUM (codice del cespite, codice del modello di valore, data di inizio, data di fine) | Restituisce il contenitore dati preparati dell'importo cespiti per un periodo specificato. | **FA\_SUM ("COMP-000001", "Current", Date1, Date2)** restituisce il contenitore dati preparati dei cespiti **"COMP-000001"** con il modello di valore **"Current"** per il periodo compreso tra **Date1** e **Date2**. |
| FA\_BALANCE (codice del cespite, codice del modello di valore, anno di dichiarazione, data di dichiarazione) | Restituisce il contenitore dati preparati del saldo cespiti. L'anno di dichiarazione deve essere specificato come valore dell'enumerazione di Finance and Operations **AssetYear**. | **FA\_SUM ("COMP-000001", "Current", AxEnumAssetYear.ThisYear, SESSIONTODAY ())** restituisce il contenitore dati preparati dei saldi del cespite **"COMP-000001"** con il modello di valore **"Current"** sulla data della sessione corrente di for Finance and Operations. |
| TABLENAME2ID (stringa) | Restituisce una rappresentazione in formato intero di un ID tabella per il nome di tabella specificato. | **TABLENAME2ID ("Intrastat")** restituisce **1510**. |
| ISVALIDCHARACTERISO7064 (stringa) | Restituisce il valore booleano **TRUE** quando la stringa specificata rappresenta un numero di conto bancario internazionale (IBAN) valido. In caso contrario, restituisce il valore booleano **FALSE** | **ISVALIDCHARACTERISO7064 ("AT61 1904 3002 3457 3201")** restituisce **TRUE**. **ISVALIDCHARACTERISO7064 ("AT61")** restituisce **FALSE**. |

### <a name="functions-list-extension"></a>Estensione dell'elenco di funzioni

ER consente di estendere l'elenco di funzioni utilizzate nelle espressioni ER. A tal fine sono richieste alcune operazioni progettuali. Per informazioni dettagliate, vedere [Estensione dell'elenco di funzioni di creazione di report elettronici (ER)](general-electronic-reporting-formulas-list-extension.md).

## <a name="see-also"></a>Vedere anche

[Panoramica sui report elettronici](general-electronic-reporting.md)

[Estensione dell'elenco di funzioni di creazione di report elettronici (ER)](general-electronic-reporting-formulas-list-extension.md)

