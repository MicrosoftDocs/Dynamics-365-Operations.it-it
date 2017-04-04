---
title: Opzioni di formattazione avanzate nei report finanziari
description: "Quando si crea un report nei report finanziari, sono disponibili funzioni di formattazione aggiuntive, inclusi i filtri per dimensioni, restrizioni per le colonne e le unità di report, righe non stampabili e istruzioni IF/THEN/ELSE nei calcoli."
author: ShylaThompson
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: ShylaThompson
ms.search.scope: Management Reporter
ms.custom: 106571
ms.assetid: 895b5127-01d6-4495-b127-343387b743aa
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 
ms.dyn365.ops.version: 
translationtype: Human Translation
ms.sourcegitcommit: 388b6398488e6f316c1ec07a00182e81c1dc8d08
ms.openlocfilehash: 631fec1dc135565e6d38e7faf193a7a898b508cb
ms.lasthandoff: 03/29/2017


---

# <a name="advanced-formatting-options-in-financial-reporting"></a>Opzioni di formattazione avanzate nei report finanziari

Quando si crea un report nei report finanziari, sono disponibili funzioni di formattazione aggiuntive, inclusi i filtri per dimensioni, restrizioni per le colonne e le unità di report, righe non stampabili e istruzioni IF/THEN/ELSE nei calcoli. 

Nella seguente tabella vengono illustrate le funzioni avanzate di formattazione disponibili per progettare i report.

| Funzione                   | Descrizione                                                                                                                                                                                                                                                                                                                     |
|----------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Filtro dimensioni           | Per accedere a set di dati specifici, è possibile utilizzare le dimensioni della definizione di riga e la definizione di colonna. Numerosi report usano solo il segmento naturale nel formato della riga. Tuttavia, le righe possono essere modificate in modo da includere i valori di dimensione. I filtri dimensioni nella definizione di colonna vengono utilizzati per accedere ai valori di dimensione specifici. |
| Limitazione a unità gerarchica | È possibile impostare una riga di report in modo da visualizzare solo le informazioni collegate a un'unità gerarchica specifica.                                                                                                                                                                                                                      |
| Righe da non stampare (NP)     | Le righe da non stampare sono utili in molti report. Se più calcoli sono necessari per ottenere un valore, i calcoli possono essere nascosti nel report stampato. Le righe da non spampare sono inoltre utili per risolvere gli errori di progettazione del report e per il posizionamento avanzato nelle celle.                                                    |
| Restrizione di colonna         | La restrizione di colonna nella definizione di riga è utile per nascondere valori pertinenti solo in alcune righe del report. Quando i calcoli percentuali vengono eseguiti in una riga, la restrizione di colonna impedisce la stampa delle colonne totali o di altre colonne quando i numeri non sono applicabili.                              |
| Interruzione di colonna               | È possibile aggiungere interruzioni di colonna in una definizione di riga per mostrare le informazioni del report affiancate. È possibile aggiungere più interruzioni di colonna in una singola definizione di riga e le intestazioni di colonna vengono ripetute nella parte superiore di ogni colonna dopo l'interruzione di colonna. I commenti per un report vengono visualizzati tra le interruzioni di colonna.                              |
| Istruzione IF/THEN/ELSE     | È possibile modificare i calcoli in una definizione di riga o una definizione di colonna.                                                                                                                                                                                                                                                         |

## <a name="advanced-cell-placement"></a>Posizionamento avanzato nelle celle
Il posizionamento avanzato nelle celle, o *posizionamento forzato*, implica la collocazione di valori specifici in celle specifiche. Ad esempio, il posizionamento forzato viene usato spesso per spostare il saldo corretto in un rendiconto del flusso di cassa. È possibile utilizzare il posizionamento formato per gli scopi seguenti:

-   Immettere i valori da Microsoft Excel in celle specifiche.
-   Immettere i valori hardcoded specifici in un report.
-   Modificare i segni copiando un valore da una cella precedente e moltiplicando il valore per -1.

**Nota:** In molti casi, è necessario configurare la definizione di report in modo da eseguire i calcoli delle colonne prima dei calcoli delle righe. Per completare questa configurazione, attenersi alla procedura seguente.

1.  In Progettazione report, aprire la definizione di report.
2.  Nella scheda **Impostazioni**, in **Priorità calcolo**, selezionare **Esegui prima calcolo colonna e poi riga**.

## <a name="designing-the-report"></a>Progettazione del report
Quando si progetta un report, è necessario prima creare tutte le righe di dettaglio per assicurarsi che venga effettuato il pull dei valori come previsto. Aggiungere quindi le sostituzioni di formato **NP** (non stampare) per eliminare il dettaglio che include i valori finali. **Importante:** Quando si utilizza il codice formato **CAL** nella definizione di riga, non è possibile eseguire il drill-down dei dettagli delle transazioni. Per la forzatura, le formule utilizzano il formato seguente: &lt;=&gt;la colonna di destinazione&lt;in base al codice&gt;&lt;di column.row per&gt; separare le eventuali posizioni aggiuntive per una riga con una virgola e uno spazio. Ecco un esempio: D=C.190,E=C.100

## <a name="examples-of-advanced-formatting-options"></a>Esempi delle opzioni di formattazione avanzate
Gli esempi seguenti mostrano come formattare la definizione di riga e la definizione di colonna per forzare il posizionamento in un report di base del flusso di cassa (esempio 1) e un report statistico (esempio 2).

### <a name="example-1-basic-forcing"></a>Esempio 1: Posizionamento forzato di base

La tabella indicata di seguito mostra un esempio di una definizione di riga che utilizza il posizionamento forzato di base.

| Codice di riga | Descrizione                      | Codice formato | Unità/righe/formule correlate | Sostituzione formato | Saldo normale | Controllo stampa | Restrizione di colonna | Modificatore di riga               | Collegamento a dimensioni finanziarie |
|----------|----------------------------------|-------------|-----------------------------|-----------------|----------------|---------------|--------------------|----------------------------|------------------------------|
| 100      | Liquidità a inizio periodo (NP) |             |                             |                 |                |               |                    | Modificatore di conto = \[/BB\] | +Segment2 \[\]= 1100         |
| 130      | Liquidità a inizio periodo      | CAL         | C=C.100,F=D.100             |                 |                |               |                    |                            |                              |
| 160      |                                  |             |                             |                 |                |               |                    |                            |                              |
| 190      |                                  |             |                             |                 |                |               |                    |                            |                              |

La tabella indicata di seguito mostra un esempio di una definizione di colonna che utilizza il posizionamento forzato di base nella riga.

|                              | A   | B    | C        | D      | E      | V    |
|------------------------------|-----|------|----------|--------|--------|------|
| Intestazione 1                     |     |      |          |        |        |      |
| Intestazione 2                     | A   | B    | C        | D      | E      | V    |
| Intestazione 3                     |     |      |          |        |        |      |
| Tipo di colonna                  | ROW | DESC | FD       | FD     | FD     | CALC |
| Codice libro/Categoria attributi |     |      | ACTUAL   | ACTUAL | ACTUAL |      |
| Anno fiscale                  |     |      | BASE     | BASE   | BASE   |      |
| Periodo                       |     |      | BASE     | BASE   | BASE   |      |
| Periodi coperti              |     |      | PERIODIC | YTD/BB | YTD    |      |
| Formula                      |     |      |          |        |        | E-D  |
| Larghezza colonna                 | 5   | 30   | 14       | 14     | 14     | 14   |

### <a name="example-2-statistical-reports"></a>Esempio 2: Report statistici

La tabella indicata di seguito mostra un esempio di una definizione di riga che utilizza il posizionamento forzato per un report statistico.

| Codice di riga | Descrizione               | Codice formato | Unità/righe/formule correlate     | Sostituzione formato      | Saldo normale | Controllo stampa | Restrizione di colonna | Modificatore di riga | Collegamento a dimensioni finanziarie               |
|----------|---------------------------|-------------|---------------------------------|----------------------|----------------|---------------|--------------------|--------------|--------------------------------------------|
| 50       | Informazioni statistiche   | REM         |                                 |                      |                |               |                    |              |                                            |
| 100      | Numero dipendenti - USA            | CAL         | 4                               | \#\#\#0.;($\#\#\#0.) |                |               |                    |              |                                            |
| 115      | Numero dipendenti - Internazionale | CAL         | 11                              | \#\#\#0.;($\#\#\#0.) |                |               |                    |              |                                            |
| 130      |                           |             |                                 |                      |                |               |                    |              |                                            |
| 190      | Vendite USA                  |             |                                 |                      | C              |               |                    |              | +Segment2 \[= 41\*\], Segment3 \[= 00\]    |
| 220      | Vendite internazionali       |             |                                 |                      | C              |               |                    |              | +Segment2 \[= 41\*\], 01:99\]= \[di Segment3 |
| 250      |                           |             |                                 |                      |                |               |                    |              |                                            |
| 280      |                           |             |                                 |                      |                |               |                    |              |                                            |
| 310      | Vendite USA                  | CAL         | D=C.190,E=C.100,F=(C.100/C.190) |                      |                |               |                    |              |                                            |
| 340      | Vendite internazionali       | CAL         | D=C.220,E=C115,F=(C.220/C.115)  |                      |                |               |                    |              |                                            |

La tabella indicata di seguito mostra un esempio di una definizione di colonna che utilizza il posizionamento forzato per un report statistico.

|                              | A   | B    | C      | D            | E     | V            |
|------------------------------|-----|------|--------|--------------|-------|--------------|
| Intestazione 1                     | A   | B    | C      | D            | E     | V            |
| Intestazione 2                     | -   | -    | Da inizio anno    | Vendite annue | Personale | $ a persona |
| Intestazione 3                     |     |      |        |              |       |              |
| Tipo di colonna                  | ROW | DESC | FD     | CALC         | CALC  | CALC         |
| Codice libro/Categoria attributi |     |      | ACTUAL |              |       |              |
| Anno fiscale                  |     |      | BASE   |              |       |              |
| Periodo                       |     |      | BASE   |              |       |              |
| Periodi coperti              |     |      | YTD    |              |       |              |
| Formula                      |     |      |        |              |       | E-D          |
| Larghezza colonna                 | 5   | 30   | 14     | 14           | 14    | 14           |

## <a name="restricting-a-row-to-a-specific-reporting-unit"></a>Limitazione di una riga a un'unità gerarchica specifica
Quando una riga del report è limitata a un'unità gerarchica specifica, la riga mostra i dati collegati solo quella unità gerarchica e ignora i dati per altre unità gerarchiche nell'albero gerarchico. Ad esempio, è possibile creare una riga che fornisce i dati dettagliati per le spese d'esercizio totali di un reparto specifico. Il report può contenere dati duplicati se il report contiene sia un albero gerarchico che una definizione di riga con più del solo conto naturale. Ad esempio, si ha un albero gerarchico in cui sono elencati i sei reparti dell'organizzazione e anche una definizione di riga che include una specifica combinazione di conto e reparto nella riga. Quando si genera il report, la combinazione specifica di conto e del reparto viene stampata a ogni livello dell'albero gerarchico, anche se il reparto potrebbe non corrispondere a ciò che c'è nell'albero. Questo comportamento si verifica perché la riga sostituisce quanto in genere viene filtrato dalla definizione di report. Una modalità in cui è possibile evitare la duplicazione dei dati è limitare una riga a un'unità gerarchica specifica. **Nota:** Se una riga include dimensioni e si limita la riga a un'unitò gerarchica figlio, l'importo della riga viene incluso per tale unità e per le relative unità padre, ma non si verifica duplicazione.

### <a name="restrict-a-row-to-a-reporting-unit"></a>Limitare una riga a un'unità gerarchica

1.  In Progettazione report, fare clic su **Definizioni di riga** quindi selezionare una definizione di riga da modificare.
2.  Fare doppio clic sulla cella **Unità/righe/formule correlate** appropriata.
3.  Nella finestra di dialogo**Selezione unità gerarchica**, nel campo **Albero gerarchico**, selezionare l'albero assegnato alla definizione di report.
4.  Selezionare un'unità gerarchica, quindi fare clic su **OK**. La limitazione viene visualizzata nella cella della definizione di riga.
5.  Fare doppio clic sulla cella nella colonna **Collegamento a dimensioni finanziarii** della riga limitata e immettere un collegamento al sistema di dati finanziari.

## <a name="selecting-print-control-in-a-row-definition"></a>Selezione di un controllo di stampa in una definizione di riga
È possibile specificare i codici di controllo di stampa per ciascuna colonna mediante la cella **Controllo stampa**.

### <a name="add-print-control-codes-to-a-report-row"></a>Aggiungere i codici di controllo di stampa in una riga del report

1.  In Progettazione report, aprire la definizione di riga da modificare.
2.  Fare doppio clic sulla cella **Controllo stampa**.
3.  Nella finestra di dialogo **Controllo stampa**, selezionare un codice di controllo di stampa, o premere e tenere premuto il tasto Ctrl per selezionare più codici. È inoltre possibile digitare i codici di stampa direttamente nella cella **Controllo stampa**. Separare più codici di controllo di stampa con virgole.
4.  Selezionare eventuali opzioni di stampa condizionali.
5.  Scegliere **OK**.

### <a name="regular-print-control-codes"></a>Codici di controllo di stampa normali

Nella seguente tabella sono descritti i codici di controllo di stampa normali per una definizione di riga.

| Codice di controllo di stampa | Interpretazione del codice di controllo di stampa         | Descrizione                                                                                                                                                                                                                                                                                                                                                                                                  |
|--------------------|--------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| NP                 | Riga da non stampare                                 | Impedisce la stampa nel report degli importi nella riga e esclude gli importi dai calcoli. Per includere una colonna contrassegnata da non stampare nel calcolo, fare riferimento alla colonna direttamente nella formula di calcolo. Ad esempio, la riga 240 da non stampare è inclusa nel calcolo seguente: **230+240+250**. Tuttavia, la riga 240 da non stampare non è inclusa nel calcolo seguente: **230:250**. |
| CS                 | Simbolo della valuta; usare il formato della valuta in questa riga | Include il simbolo della valuta in tutti gli importi non percentuali. I valori percentuali non ricevono mai un simbolo della valuta.                                                                                                                                                                                                                                                                                                |
| XD                 | Consente di eliminare la riga nel report dettagli del conto            | Consente di eliminare la visualizzazione dei conti nei report dettagli dei conti e nei report dettagli delle transazioni. Questo controllo di stampa è utile se una riga include più conti che non devono essere elencati nel report dettagli del conto o nel report dettagli della transazione.                                                                                                                                                           |
| X0                 | Consente di eliminare la riga se contiene tutti zeri                        | Esclude una riga dal report se tutte le celle nella riga sono vuote o contengono zeri. Questo controllo di stampa è significativo solo se l'opzione di eliminare il saldo zero non è selezionata nella definizione di report.                                                                                                                                                                                            |
| B0                 | Lascia vuote le colonne zero                         | Lascia vuote le colonne in una riga che contiene importi zero.                                                                                                                                                                                                                                                                                                                                                      |
| XR                 | Consente di eliminare il rollup                                  | Consente di eliminare il rollup. Se il report utilizza un albero gerarchico, non viene eseguito il rollup degli importi nella riga nei nodi padre successivi.                                                                                                                                                                                                                                                                               |
| SR                 | Elimina arrotondamento                                | Impedisce l'arrotondamento degli importi nella riga.                                                                                                                                                                                                                                                                                                                                                          |
| XT                 | Consente di eliminare la riga nel report dettagli della transazione        | Consente di eliminare la visualizzazione delle transazioni nei report dettagli delle transazioni. Questo controllo di stampa è utile se una riga include più conti che non devono essere elencati nel report dettagli della transazione.                                                                                                                                                                                                             |

### <a name="conditional-print-control-codes"></a>Codici di controllo di stampa condizionali

Nella seguente tabella sono descritti i codici di controllo di stampa condizionali per una definizione di riga.

| Codice di controllo di stampa | Descrizione                                  |
|--------------------|----------------------------------------------|
| (nessuno)             | Cancella la selezione di stampa condizionale.       |
| DR                 | Stampa solo i saldi in dare per la riga.  |
| CR                 | Stampa solo i saldi in avere per la riga. |

## <a name="column-restriction-cell-in-a-row-definition"></a>Cella Restrizione di colonna in una definizione di riga
La cella **Restrizione di colonna** in una definizione di riga ha più scopi. A seconda del tipo di riga, è possibile utilizzare la cella **Restrizione di colonna** per specificare una delle funzioni seguenti:

-   La cella può limitare la stampa degli importi della riga a una colonna specifica. Questa funzione è utile se si crea un conto patrimoniale tabulare.
-   La cella può specificare la colonna degli importi da ordinare.

## <a name="using-a-calculation-formula-in-a-row-definition"></a>Uso di una formula di calcolo in una definizione di riga
Una formula di calcolo in una definizione di riga può includere ** **+,-** **, ** **\* e/** ** nonché operatori ** IF/THEN/ELSE ** rendiconti. Inoltre, un calcolo può includere singole celle e importi assoluti (i numeri effettivi inclusi nella formula). La formula può contenere 1024 caratteri al massimo. I calcoli non possono essere applicati alle righe contenenti le celle del tipo **Collegamento a dimensioni finanziarie** (FD). Tuttavia, è possibile includere i calcoli di righe consecutive, eliminare la stampa di quelle righe e quindi calcolare il totale delle righe di calcolo.

### <a name="operators-in-a-calculation-formula"></a>Operatori in una formula di calcolo

Una formula di calcolo utilizza operatori più complessi di una formula di totale delle righe. Tuttavia, è possibile utilizzare ** **\* e/** ** gli operatori insieme agli operatori aggiuntivi per moltiplicare (\*) e per dividere (/) gli importi. Per utilizzare un intervallo o una somma in una formula di calcolo, è necessario utilizzare la chiocciola (@) davanti a qualsiasi codice di riga, a meno che stiate utilizzando una colonna nella definizione di riga. Ad esempio, per aggiungere l'importo nella riga 100 all'importo nella riga 330, è possibile utilizzare la formula di totale di riga ** 100+330 ** o formula di calcolo **@100+@330**. **Nota:** Utilizzare la chiocciola (@) prima di ciascun codice di riga utilizzato in una formula di calcolo. In caso contrario, il numero viene letto come importo assoluto. Ad esempio, la formula **@100+330 ** aggiunto EUR 330 all'importo nella riga 100. Quando si fa riferimento a una colonna in una formula di calcolo, la chiocciola (@) non è necessaria.

### <a name="create-a-calculation-formula"></a>Creare una formula di calcolo

1.  In Progettazione report, fare clic su **Definizioni di riga** quindi aprire la definizione di riga da modificare.
2.  Fare doppio clic sulla cella **Codice formato** quindi selezionare **CAL**.
3.  Nella cella **Unità/righe/formule correlate**, immettere la formula di calcolo.

### <a name="example-of-a-calculation-formula-for-specific-rows"></a>Esempio di una formula di calcolo per righe specifiche

In questo esempio, la formula di calcolo **@100+@330** indica che l'importo nella riga 100 viene aggiunto all'importo nella riga 330. La formula di totale di riga ** 340+370 ** aggiunto l'importo nella riga 340 all'importo nella riga 370. (Importo della riga 370 è l'importo della formula di calcolo).

| Codice di riga | Descrizione                 | Codice formato | Unità/righe/formule correlate | Controllo stampa | Modificatore di riga | Collegamento a dimensioni finanziarie |
|----------|-----------------------------|-------------|----------------------------|---------------|--------------|------------------------------|
| 340      | Liquidità a inizio periodo |             |                            | NP            | BB           | 1100:1110\]+Conto= di\[       |
| 370      | Liquidità a inizio anno   | CAL         | @100+@330                  | NP            |              |                              |
| 400      | Liquidità a inizio periodo | TOT         | 340+370                    |               |              |                              |

Quando la riga in una definizione di riga ha un codice formato **CAL** e si immette un calcolo matematico nella cella **Unità/righe/formule correlate**, è inoltre necessario immettere la lettera della colonna e della riga associate nel report. Ad esempio, immettere ** ** A.120 per indicare la colonna A, la riga 120. In alternativa, è possibile utilizzare la chiocciola (@) indicare tutte le colonne. Ad esempio, immettere **@120** per indicare tutte le colonne della riga 120. Tutti i calcoli matematici per cui non è presente una lettera di colonna o una chiocciola (@) vengono considerati come un numero reale. ** Nota: ** Se si utilizza un codice di riga di tipo etichetta per fare riferimento a una riga, è necessario utilizzare un punto (.) come separatore tra la lettera di colonna e l'etichetta, ad esempio ** A.GROSS\_MARGIN/A.SALES **). Se si utilizza la chiocciola (@), un separatore non è necessaria, ad esempio **@GROSS\_MARGIN/@SALES**).

### <a name="example-of-a-calculation-formula-for-a-specific-column"></a>Esempio di una formula di calcolo per una colonna specifica

In questo esempio, la formula di calcolo **E=C.340** indica che il calcolo nella cella nella colonna C, riga 340, viene eseguito solo nella colonna E. **Nota:** Quando si fa riferimento una colonna in una formula di calcolo, la chiocciola (@) non è obbligatoria.

| Codice di riga | Descrizione                 | Codice formato | Unità/righe/formule correlate | Controllo stampa | Modificatore di riga | Collegamento a dimensioni finanziarie |
|----------|-----------------------------|-------------|----------------------------|---------------|--------------|------------------------------|
| 340      | Liquidità a inizio periodo |             |                            | NP            | BB           | 1100:1110\]+Conto= di\[       |
| 370      | Liquidità a inizio anno   | CAL         | E=C.340                    | NP            |              |                              |
| 400      | Liquidità a inizio periodo | TOT         | 340+370                    |               |              |                              |

### <a name="modifying-a-number-in-selected-columns"></a>Modifica di un numero nelle colonne selezionate

Quando si modifica un numero o un calcolo in una colonna di una riga specifica ma non si desidera influire su altre colonne nel report, è possibile specificare **CAL** (calcolo) nella colonna **Codice formato** della definizione di riga.

-   Per eseguire un calcolo in tutte le colonne (**FD**) del report, non immettere un'assegnazione di colonna.
-   Per limitare una formula alle colonne specifiche, immettere la lettera di colonna, un segno uguale (**=**) quindi nella formula.
-   È possibile specificare più colonne. Quando si utilizza la chiocciola (@) con il posizionamento di una colonna specifica, la chiocciola (@) è correlata alla riga.
-   È possibile immettere più formule di colonna in una riga. Separare le formule utilizzando virgole.

### <a name="calculation-examples"></a>Esempi di calcolo

| Calcolo            | Azione creata                                                                                                   |
|------------------------|--------------------------------------------------------------------------------------------------------------------------|
| @130\*.75              | Per ciascuna colonna, il valore nella riga 130 viene moltiplicato per 0,75. Il risultato viene quindi inserito nella riga corrente di ogni colonna. |
| B=@130\*.75            | Lo stesso calcolo viene eseguito solo sulla colonna B.                                                                      |
| A, B, C= (@100/@130\*.75) | A= (A.100/A.130)\*.75 B= (B.100/B.130)\*.75 C= (C.100/C.130)\*.75                                                           |

### <a name="ifthenelse-statements-in-a-row-definition"></a>Istruzioni IF/THEN/ELSE in una definizione di riga

Le istruzioni **IF/THEN/ELSE** possono essere aggiunte a qualsiasi calcolo valido e essere utilizzate con il formato **CAL**. Si immettono le formule di calcolo **IF/THEN/ELSE** nella cella della colonna **Unità/righe/formule correlate**. ** IF/THEN/ELSE ** le formule di calcolo viene utilizzato il formato seguente: IF &lt;la formula di ALTRA falsa&gt; dichiarazione vera&gt; / &lt;Formule &lt;THEN formula&gt; ** formula &lt;ALTRA&gt;** la parte del rendiconto è facoltativa.

#### <a name="if-statements"></a>Istruzioni IF

L'istruzione che segue l'istruzione **IF** può essere qualsiasi istruzione che può essere valutata come vera o falsa. L'istruzione che segue l'istruzione **IF** può comprenderla una valutazione semplice, oppure può essere un'istruzione complessa che può contenere più espressioni. Di seguito sono riportati alcuni esempi.

-   ** Se A.2000&gt;** (dichiarazione semplice)
-   ** Se A.2000&gt;In A.20010&lt;, 000 ** (dichiarazione complessa)
-   ** Se A.20010000&gt;In alternativa ((A.340/B.1200\*2) &lt;1200)** (Rendiconto complessa contenente più espressioni)

Il termine **Periodi** in un'istruzione **IF** rappresenta il numero di periodi per il report. Il termine viene in genere utilizzato per calcolare una media annua fino a oggi. Ad esempio, quando si esegue un report per il periodo 7 YTD, l'istruzione **B.150/Periodi** indica che il valore nella riga 150 della colonna B viene diviso per 7.

#### <a name="then-and-else-formulas"></a>Formule THEN ed ELSE

Le formule **THEN** ed **ELSE** possono essere qualsiasi calcolo valido, da assegnazioni di valori molto semplici a formule complesse. Ad esempio, l'istruzione ** Se A.2000&gt;THEN A=B.200 ** i media ", se il valore della cella della colonna A della riga 200 è maggiore di 0 (zero), vengono inserite il valore della cella della colonna B della riga 200 nella cella della colonna A della riga corrente". L'istruzione **IF/THEN** precedente inserisce un valore in una colonna della riga corrente. Tuttavia, è possibile anche utilizzare una chiocciola (@) nelle valutazioni true/false o nella formula per rappresentare tutte le colonne. Di seguito sono riportati alcuni altri esempi descritti nelle sezioni seguenti:

-   ** IF A.200 &gt;THEN 0 B.200 **: Se il valore della cella A.200 è positivo, il valore della cella B.200 viene inserito in tutte le colonne della riga corrente.
-   ** IF A.200 &gt;THEN 0 @200**: Se il valore della cella A.200 è positivo, il valore di ogni colonna della riga 200 viene inserito nella colonna corrispondente della riga corrente.
-   ** Se @200&gt;0 utilizza @200**: Se il valore della riga 200 della colonna corrente è positivo, il valore della riga 200 viene aggiunto alla stessa colonna della riga corrente.

### <a name="restricting-a-calculation-to-a-reporting-unit-in-a-row-definition"></a>Limitazione di un calcolo a un'unità gerarchica in una definizione di riga

Per limitare un calcolo a una singola unità gerarchiche di un albero gerarchico, in modo che l'importo risultante non viene eseguito il rollup a un'unità di livello superiore, è possibile utilizzare **@Unit** il codice ** Formule/Righe/Unità correlate ** nella cella della definizione di riga. **@Unit** il codice è elencato nella colonna B di albero gerarchico, ** nome della periferica **. Quando si utilizza **@Unit** il codice, i valori non viene eseguito il rollup, ma il calcolo viene valutato a ogni livello dell'albero gerarchico. **Nota:** Per utilizzare questa funzione, un albero gerarchico deve essere associato alla definizione di riga. La riga di calcolo può fare riferimento a una riga di calcolo o una riga di dati finanziari. Il calcolo viene registrato nella cella **Unità/righe/formule correlate** della definizione di riga e nella restrizione di tipo di dati finanziari. Il calcolo deve utilizzare un calcolo condizionale che inizia con ** Se @Unit** predefiniti. Di seguito è riportato un esempio: IF @Unit(VENDITE) THEN @100 ELSE 0 questo calcolo include l'importo della riga 100 in ciascuna colonna del report, ma solo per l'unità di vendita. Se più unità sono denominate SALES, l'importo viene visualizzato in ciascuna di queste unità. Inoltre, la riga 100 può essere una riga di dati finanziari e può essere definita come da non stampare. In questo caso, si impedisce all'importo di apparire in tutte le unità dell'albero. È inoltre possibile limitare l'importo a una singola colonna del report, ad esempio la colonna H, utilizzando una restrizione di colonna per stampare il valore solo in quella colonna del report. È possibile includere combinazioni **OR** in un'istruzione **IF**. Di seguito è riportato un esempio: IF @Unit(VENDITE) OR @Unit(VENDITE OVEST) THEN 5 ELSE @100 è possibile specificare un'unità in una restrizione di tipo Calcolo in uno dei seguenti modi:

-   Immettere un nome di unità per includere le unità che corrispondono. Ad esempio, ** Se @Unit(VENDITE) ** consente il calcolo per qualsiasi unità denominata SALES, anche in presenza di diverse unità di vendita nell'albero gerarchico.
-   Immettere il nome della società e dell'unità per limitare il calcolo a unità specifiche di una società specifica. Ad esempio, immettere ** Se @Unit(ACME: ** VENDITE) limitare il calcolo alle unità di vendita della società ACME.
-   Immettere il codice gerarchia completo dell'albero gerarchico per limitare il calcolo a un'unità specifica. Ad esempio, immettere ** Se @Unit(RIEPILOGO^ACME^COSTA OVEST^VENDITE) **. **Nota:** Per trovare il codice gerarchia completo, fare clic con il pulsante destro del mouse sulla definizione di albero gerarchico e selezionare **Copia identificatore unità gerarchica (codice H)**.

#### <a name="restrict-a-calculation-to-a-reporting-unit"></a>Limitare un calcolo a un'unità gerarchica

1.  In Progettazione report, fare clic su **Definizioni di riga** quindi aprire la definizione di riga da modificare.
2.  Fare doppio clic sulla cella **Codice formato** quindi selezionare **CAL**.
3.  Fare clic su ** Formule/Righe/Unità correlate ** la cella quindi immettere un calcolo condizionale che inizia con ** Se @Unit** predefiniti.

### <a name="ifthenelse-statements-in-a-column-definition"></a>Istruzioni IF/THEN/ELSE in una definizione di colonna

Un'istruzione **IF/THEN/ELSE** abilita la dipendenza di un calcolo dai risultati di qualsiasi altra colonna. È possibile fare riferimento ad altre colonne, ma non è possibile fare riferimento a una cella del report nell'istruzione **IF**. Qualsiasi calcolo deve essere applicato all'intera colonna. Ad esempio, l'istruzione ** Se B100&gt;THEN B C ALTRA\*1.25 ** il mezzo, "se l'importo della colonna B è superiore a 100, vengono inserite il valore della colonna B in ** CALC ** colonna. Se l'importo nella colonna B non è maggiore di 100, moltiplica il valore nella colonna C per 1,25 e inserisci il risultato nella colonna **CALC**". Fare seguire sempre l'istruzione **IF** con un'istruzione logica che può essere valutata come vera o falsa. Le formule utilizzate per l'istruzione **THEN** e per l'istruzione **ELSE** possono contenere riferimenti a qualsiasi numero di colonne e le formule possono essere tanto complesse quanto si desidera. **Nota:** Non è possibile inserire i risultati di un calcolo in nessuna altra colonna. I risultati devono essere nella colonna che contiene la formula.


