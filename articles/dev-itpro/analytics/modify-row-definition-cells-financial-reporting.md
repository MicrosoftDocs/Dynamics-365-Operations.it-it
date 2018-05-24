---
title: Modificare le celle di definizione riga
description: In questo articolo vengono descritte le informazioni necessarie per ogni cella in una definizione di riga in un report finanziario, e viene illustrato come immettere le informazioni.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 58881
ms.assetid: 0af492df-a84e-450c-8045-78ef1211abaf
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 23b8e0b51f63ecabc704a2fc5b3ebafe657b52f6
ms.contentlocale: it-it
ms.lasthandoff: 05/08/2018

---

# <a name="modify-row-definition-cells"></a>Modificare le celle di definizione riga

[!include [banner](../includes/banner.md)]

In questo articolo vengono descritte le informazioni necessarie per ogni cella in una definizione di riga in un report finanziario, e viene illustrato come immettere le informazioni. 

## <a name="specify-a-row-code-in-a-row-definition"></a>Specificare un codice di riga in una definizione riga

Nelle definizioni riga, i numeri o le etichette nella cella **Codice riga** identificano ogni riga nella definizione. È possibile specificare il codice di riga per fare riferimento ai dati nei calcoli e nella determinazione dei totali.

### <a name="row-code-requirements"></a>Requisiti dei codici di riga

È obbligatorio indicare un codice per tutte le righe. È possibile combinare codici di riga numerici, alfanumerici e non impostati (vuoti) in una definizione riga. Il codice di riga può essere qualsiasi numero intero positivo (inferiore a 100.000.000) o un'etichetta descrittiva che identifica la riga. Un'etichetta descrittiva deve seguire queste regole:

-   L'etichetta deve iniziare con un carattere alfabetico (a-z o A-Z) e può essere una qualsiasi combinazione di numeri e lettere fino a 16 caratteri. 

> [!Note] 
> Un'etichetta può includere il carattere di sottolineatura (\_), ma non sono consentiti altri caratteri speciali.

-   Nell'etichetta non si può utilizzare nessuna delle seguenti parole riservate: AND, OR, IF, THEN, ELSE, PERIODS, TO, BASEROW, UNIT, NULL, CPO o RPO.

Gli esempi seguenti sono validi codici di riga:

-   320
-   TL\_NET\_INCOME
-   TL\_NET\_94

### <a name="change-a-row-code-in-a-row-definition"></a>Modificare un codice di riga in una definizione riga

1.  In Progettazione report, fare clic su **Definizioni di riga** quindi aprire la definizione di riga da modificare.
2.  Nella riga appropriata, immettere il nuovo valore nella cella della colonna **Codice riga**.

### <a name="reset-numeric-row-codes"></a>Reimpostare i codici di riga numerici

1.  In Progettazione report, fare clic su **Definizioni di riga** quindi aprire la definizione di riga da modificare.
2.  Nel menu **Modifica** fare clic su **Rinumera righe**.
3.  Nella finestra di dialogo **Rinumera righe**, specificare i nuovi valori per il codice di riga iniziale e l'incremento del codice di riga. È possibile reimpostare i codici di riga numerici su valori equidistanti. Tuttavia, Progettazione report rinumera solo i codici di riga che iniziano con un numero, ad esempio 130 o 246. Non rinumera i codici di riga che iniziano con una lettera, ad esempio INCOME\_93 o TP0693. 

> [!Note] 
> Quando si rinumerano i codici di riga, Progettazione report aggiorna automaticamente i riferimenti **TOT** e **CAL**. Ad esempio, se una riga **TOT** fa riferimento a un intervallo che inizia con il codice di riga 100 e si rinumerano le righe a partire da 90, il riferimento **TOT** iniziale cambia da 100 a 90.

## <a name="add-a-description"></a>Aggiungere una descrizione
La cella di descrizione fornisce una descrizione dei dati finanziari nella riga del report, ad esempio "Ricavi" o "Reddito netto". Il testo nella cella **Descrizione** viene visualizzato nel report esattamente come lo si immette nella definizione di riga. 

> [!Note] 
> La larghezza della colonna di descrizione del report è impostata nella definizione di colonna. Se il testo nella colonna **Descrizione** della definizione di riga è lungo, verificare la larghezza della colonna **DESC**. Quando si utilizza la finestra di dialogo **Inserisci righe da**, i valori nella colonna **Descrizione** sono i valori del segmento o i valori della dimensione dei dati finanziari. È possibile inserire righe per aggiungere testo descrittivo, ad esempio un'intestazione o un totale di sezione, e per aggiungere la formattazione, ad esempio una riga prima di una riga del totale. Se il report include un albero gerarchico, è possibile includere il testo aggiuntivo definito per le unità gerarchiche nell'albero gerarchico. È inoltre possibile limitare il testo aggiuntivo a un'unità gerarchica specifica.

### <a name="add-the-description-for-a-line-on-a-report"></a>Aggiungere la descrizione per una riga di un report

1.  In Progettazione report, fare clic su **Definizioni di riga** quindi aprire la definizione di riga da modificare.
2.  Selezionare la cella **Descrizione** quindi immettere il nome della riga di report.
3.  Applicare la formattazione.

### <a name="add-additional-text-from-a-reporting-tree-in-the-description"></a>Aggiungere testo aggiuntivo da un albero gerarchico nella descrizione

1.  In Progettazione report, fare clic su **Definizioni di riga** quindi aprire la definizione di riga da modificare.
2.  Immettere il codice del testo aggiuntivo e qualsiasi altro testo nella cella **Descrizione** appropriata.
3.  Applicare la formattazione.

### <a name="limit-the-additional-text-to-a-specific-reporting-unit"></a>Limitare il testo aggiuntivo a un'unità gerarchica specifica

1.  In Progettazione report, fare clic su **Definizioni di riga** quindi aprire la definizione di riga da modificare.
2.  Individuare la riga in cui deve essere creato il testo aggiuntivo e fare doppio clic sulla cella nella colonna **Unità/Righe/Formule correlate**.
3.  Nella finestra di dialogo **Selezione unità gerarchica**, selezionare nel campo **Albero gerarchico** un albero gerarchico.
4.  Nel campo **Seleziona unità gerarchica per restrizione**, espandere o comprimere l'albero gerarchico e selezionare un'unità gerarchica.

## <a name="add-a-format-code"></a>Aggiungere un codice di formato
La cella **Codice formato** offre una selezione di opzioni preformattate per il contenuto della riga. Se la cella **Codice formato** è vuota, la riga viene interpretata come riga di dettaglio di dati finanziari. 
> [!Note] 
> Se un report contiene righe di formattazione non di importo correlate a righe di importo che sono state eliminate ad esempio, a causa di saldi a zero, è possibile utilizzare la colonna **Unità/Righe/Formule** correlate per impedire la stampa delle righe del formato e del titolo.

### <a name="add-a-format-code-to-a-report-row"></a>Aggiungere un codice formato a una riga di report

1.  In Progettazione report, fare clic su **Definizioni di riga** quindi selezionare una definizione di riga da modificare.
2.  Fare doppio clic sulla cella **Codice formato**.
3.  Selezionare un codice formato nell'elenco. Nella seguente tabella sono descritti i codici formato e le relative azioni.

| <strong>Codice formato</strong>  | <strong>Interpretazione del codice di formato</strong> |                                                                                                                             <strong>Azione</strong>                                                                                                                              |
|-------------------------------|----------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|            (Nessuno)             |                                                    |                                                                                                                  Cancella il contenuto della cella <strong>Codice formato</strong>.                                                                                                                   |
|              TOT              |                       Totale                        |                                         Identifica una riga che utilizza gli operatori matematici nella colonna <strong>Unità/Righe/Formule correlate</strong>. I totali contengono gli operatori semplici, ad esempio <strong>+</strong> o <strong>-</strong>.                                         |
|              CAL              |                    Calcolo                     | Identifica una riga nella cui colonna <strong>Formule/Righe/Unità correlate</strong> vengono utilizzati operatori matematici. I calcoli contengono gli operatori complessi, ad esempio <strong>+</strong>, <strong>-</strong>, <strong>\</strong><em>, **/</em><em> e le istruzioni **IF/THEN/ELSE</em>*. |
|              DES              |                    descrizione                     |                                                                                                             Identifica una riga di intestazione o una riga vuota in un report.                                                                                                              |
|          LFT RGT CEN          |                 Centro da sinistra a destra                  |                                                                                 Allinea il testo di descrizione della riga nella pagina del report, indipendentemente dalla posizione del testo nella definizione di colonna.                                                                                 |
|              CBR              |                  Riga di base di modifica                   |                                                                                                         Identifica una riga che imposta la riga di base per i calcoli della colonna.                                                                                                         |
|            COLUMN             |                    Interruzione di colonna                    |                                                                                                                        Inizia una nuova colonna nel report.                                                                                                                        |
|             PAGE              |                     Interruzione di pagina                     |                                                                                                                         Inizia una nuova pagina nel report.                                                                                                                         |
|             \---              |                  Sottolineatura singola                  |                                                                                                            Inserisce una singola riga sotto tutte le colonne di importo nel report.                                                                                                            |
|              ===              |                  Sottolineatura doppia                  |                                                                                                            Inserisce una doppia riga sotto tutte le colonne di importo nel report.                                                                                                            |
|             LINE1             |                     Linea sottile                      |                                                                                                                    Disegna una singola linea sottile sulla pagina.                                                                                                                     |
|             LINE2             |                     Linea spessa                     |                                                                                                                    Disegna orizzontalmente una linea spessa singola nella pagina.                                                                                                                    |
|             LINE3             |                    Linea punteggiata                     |                                                                                                                   Disegna una singola linea punteggiata sulla pagina.                                                                                                                    |
|             LINE4             |              Linea spessa e linea sottile              |                                                                                             Disegna una doppia linea sottile sulla pagina. La linea superiore è spessa e la linea inferiore è sottile.                                                                                             |
|             LINE5             |              Linea sottile e linea spessa              |                                                                                             Disegna una doppia linea sottile sulla pagina. La linea superiore è sottile e la linea inferiore è spessa.                                                                                             |
|            BXB BXC            |                     Riga con riquadri                      |                                                                            Disegna una casella intorno alle righe del report che iniziano con la riga di tipo <strong>BXB</strong> e terminano con la riga di tipo <strong>BXC</strong>.                                                                            |
|              REM              |                       Commento                       |                                                               Identifica una riga che corrisponde a una riga di commento che non deve essere stampata nel report. In una riga di commento, ad esempio, potrebbero essere spiegate le tecniche di formattazione utilizzate.                                                                |
| SORT ASORT SORTDESC ASORTDESC |                        Ordina                        |                                                                   Ordina le spese o i ricavi, ordina un report di scostamento budget o effettivo per lo scostamento massimo o ordina le descrizioni di riga in ordine alfabetico.                                                                   |

## <a name="specify-related-formulasrowsunits"></a>Specificare unità/righe/formule correlate
La cella **Unità/Righe/Formule correlate** ha più scopi. A seconda del tipo di riga, una cella **Unità/Righe/Formule correlate** può eseguire una delle seguenti funzioni:

-   Definire le righe da includere nel calcolo quando si utilizza un codice formato **TOT** o **CAL**.
-   Collegare una riga di formattazione a una riga di importo, in modo che la formattazione venga stampata solo quando viene stampato l'importo relativo.
-   Limitare una riga a un'unità gerarchica specifica.
-   Definire la riga di base per il calcolo quando si utilizza il codice formato **BASEROW**.
-   Definire le righe da ordinare quando si utilizza uno dei codici formato di ordinamento.

### <a name="use-a-row-total-in-a-row-definition"></a>Utilizzare un totale di riga in una definizione di riga

Utilizzare una formula di totale di riga per aggiungere o sottrarre importi in altre righe. Una formula per creare un totale di riga può includere gli operatori + e - per combinare singoli codici e intervalli di riga. Gli intervalli sono indicati dai due punti (:). La formula può contenere 1024 caratteri al massimo. Di seguito è riportato un esempio di formula standard di totale: 400+420+430+450+460LIABILITIES+EQUITY520:546520:546-LIABILITIES

### <a name="components-of-a-row-total-formula"></a>Componenti di una formula di totale di riga

Quando si crea una formula di totale di riga, è necessario utilizzare i codici di riga per specificare le righe per aggiungere o sottrarre la definizione di riga corrente e utilizzare gli operatori per specificare come le righe vengono combinate. Le righe di totale e di importo possono essere utilizzate in qualsiasi combinazione. **Nota:** tutte le righe di totale comprese in un intervallo vengono escluse. Per creare un totale complessivo, è possibile specificare l'intervallo di righe. Se la prima riga dell'intervallo è una riga di totale, tale riga viene inclusa nel nuovo totale. Nella seguente tabella viene descritto come gli operatori vengono utilizzati nelle formule di totale di riga.

| Operatore | Formula di esempio | descrizione                                                 |
|----------|-----------------|-------------------------------------------------------------|
| +        | 100+330         | Aggiunge l'importo della riga 100 all'importo della riga 330.        |
| :        | 100:330         | Aggiunge i totali di tutte le righe comprese tra la riga 100 e la riga 330.    |
| -        | 100-330         | Sottrae l'importo della riga 100 dall'importo della riga 330. |

### <a name="create-a-row-total"></a>Creare un totale di riga

1.  In Progettazione report fare clic su **Definizioni di riga**, quindi aprire la definizione di riga che si intende modificare.
2.  Fare doppio clic sulla cella **Codice formato** nella definizione di riga e selezionare **TOT**.
3.  Nella cella **Unità/Righe/Formule correlate**, immettere la formula del totale.

### <a name="relate-a-format-row-to-an-amount-row"></a>Collegare una riga di formato a una riga di importo

Nella colonna **Codice formato** in una definizione di riga, i codici di formato **DES**, **LFT**, **RGT**, **CEN**, **---** e **===** applicano la formattazione alle righe non di importo. Per impedire la stampa di questa formattazione quando le righe di importo correlate vengono eliminate, ad esempio perché le righe di importo contengono valori zero o nessuna attività del periodo), è necessario correlare le righe di formato alle corrispondenti righe di importo. Questa funzionalità è utile se si desidera impedire la stampa delle intestazioni o della formattazione correlate ai subtotali quando non vi sono dettagli da stampare per il periodo. 
> [!Note] 
> È inoltre possibile impedire la stampa delle righe di importo dettagliato deselezionando l'opzione per visualizzare le righe senza importo. Questa opzione si trova nella scheda **Impostazioni** della definizione di report. Per impostazione predefinita, i conti dettagli sulle transazioni che hanno un saldo a zero o nessuna attività del periodo vengono eliminati nei report. Per visualizzare i conti dettagli sulle transazioni, selezionare la casella di controllo **Visualizza righe senza importo** nella scheda **Impostazioni** della definizione di report.

### <a name="relate-a-format-row-to-an-amount-row"></a>Collegare una riga di formato a una riga di importo

1.  In Progettazione report, fare clic su **Definizioni di riga** quindi selezionare una definizione di riga da modificare.
2.  Nella riga di formattazione, nella cella **Unità/Righe/Formule correlate**, immettere il codice della riga di importo da eliminare. **Nota:** per eliminare una riga di importo, il saldo della riga deve essere 0 (zero). Una riga di importo con un saldo non verrà eliminata.
3.  Scegliere **Salva** dal menu **File**.

### <a name="example-of-preventing-printing-of-rows"></a>Esempio per impedire la stampa delle righe

Nel seguente esempio, Phyllis desidera impedire la stampa dell'intestazione e dei caratteri di sottolineatura nella riga **Cassa totale** del report perché non c'è stata attività in nessun conto di cassa. Di conseguenza, nella riga 220 (che, come indicato dal codice formato **---**, è una riga di formattazione), nella cella **Unità/Righe/Formule correlate**, immette **250**, ovvero il codice della riga di importo riga che desidera eliminare. [![RelatedRowsRowDefinition](./media/relatedrowsrowdefinition-1024x144.png)](./media/relatedrowsrowdefinition.png)

## <a name="select-the-base-row-for-a-column-calculation"></a>Selezionare la riga di base per il calcolo di una colonna
Nella dichiarazione relazionale, assegnare uno o più righe di base nella definizione di riga utilizzando il codice formato **CBR** (riga di base di modifica). Una riga di base viene quindi correlata a un calcolo nella definizione di colonna. Di seguito sono riportati esempi tipici di calcoli CBR:

-   Percentuale del ricavo totale poiché correlato a singoli articoli di ricavo
-   Percentuale della spesa totale poiché correlato a singoli articoli di spesa
-   Percentuale di margine lordo poiché correlato ai dettagli di reparto o divisione.

Una o più righe di base sono definite nella definizione di riga e quindi la definizione di colonna determina la relazione della riga di base. Il codice utilizzato nella formula di colonna è **BASEROW**. Le seguenti operazioni matematiche di base sono utilizzate con **BASEROW**: divisione, moltiplicazione, addizione o sottrazione. L'operazione utilizzata più spesso è la divisione per **BASEROW**, in cui il risultato viene visualizzato come percentuale. I calcoli di colonna che utilizzano **BASEROW** nella formula utilizzano la definizione di riga per i codici di riga di base correlati. Le righe **CBR** hanno le seguenti caratteristiche:

-   Le righe **CBR** non vengono stampate nel report finale.
-   Il codice formato **CBR** e il relativo codice di riga sono posizionati sopra la riga o la selezione che visualizza i calcoli correlati.

In una definizione di colonna il tipo di colonna **CALC** indica una colonna che specifica una formula nella riga **Formula**. La formula viene eseguita sui dati per la colonna del report e utilizza la parola chiave Baserow per i calcoli di base dei codici formato **CBR** nella riga. Nella definizione di riga, il codice formato **CBR** definisce la riga di base per le colonne che calcolano una percentuale o moltiplicano per la riga di base ogni riga del report. È possibile avere più codici formato **CBR** in un formato di riga, ad esempio uno per le vendite nette, uno per le vendite lorde e uno per le spese totali. In genere, il codice formato **CBR** viene utilizzato per creare una percentuale dei conti confrontati con una riga di totale. Una riga di base viene utilizzata per tutti i calcoli finché non viene definita un'altra riga di base. È necessario definire un codice formato **CBR** di inizio e un codice formato **CBR** di fine. Ad esempio, per determinare le spese come percentuale delle vendite nette, è possibile dividere il valore di ciascuna riga di spesa per il valore della riga di vendite nette. In questo caso, la riga di vendite nette è la riga di base. È possibile definire una definizione di colonna che indica i risultati correnti e da inizio anno, insieme a una percentuale di base di ogni risultato, come illustrato nell'esempio di seguito. Iniziare con un conto economico dettagliato.

### <a name="select-the-base-row-in-a-row-definition-for-a-column-calculation"></a>Selezionare la riga di base in una definizione di riga per il calcolo di una colonna

1.  In Progettazione report, fare clic su **Definizioni colonne** quindi aprire la definizione di colonna di un conto economico.
2.  Aggiungere una nuova colonna alla definizione di colonna e impostare il tipo di colonna su **CALC**.
3.  Nella cella **Formula** della nuova colonna, immettere la formula **X/BASEROW**, dove **X** è il tipo di colonna **FD** per visualizzare una percentuale.
4.  Fare doppio clic sulla cella **Sostituzione formato/valuta**.
5.  Nella finestra di dialogo **Sostituzione formato**, nell'elenco **Categoria formato**, selezionare **Percentuale** e fare clic su **OK**.
6.  Nel menu **File**, fare clic su **Salva con nome** per salvare la definizione di colonna con un nuovo nome. Aggiungere **CBR** al nome file corrente (ad esempio **CUR\_YTD\_CBR**). La definizione di colonna è nella definizione di colonna della riga di base.
7.  In Progettazione report, fare clic su **Definizioni di riga** e aprire la definizione di riga da modificare utilizzando il calcolo della riga di base.
8.  Inserire una nuova riga sopra la riga in cui il calcolo della riga di base deve iniziare.
9.  Fare doppio clic sulla cella **Codice formato** della definizione di riga e selezionare **CBR**.
10. Nella cella **Unità/Righe/Formule correlate**, immettere il numero di codice della riga di base.

### <a name="example-of-base-row-calculation"></a>Esempio di calcolo della riga di base

Nel seguente esempio di definizione di riga, la riga 100 indica che la riga di base per i calcoli è la riga 280. [![Esempio di calcolo della riga di base.](./media/cbrrowdefinition.png)](./media/cbrrowdefinition.png) Nel seguente esempio di definizione di colonna, i calcoli utilizzano il codice formato **CBR**. Il calcolo della colonna C divide il valore della colonna B del report per il valore della riga 280 della colonna B. La sostituzione del formato nella colonna B stampa il risultato del calcolo come percentuale. In modo analogo, ogni importo nella colonna E è l'importo della colonna D come percentuale di vendite nette. [![Esempio di definizione di colonna.](./media/cbrcolumndefinition2.png)](./media/cbrcolumndefinition2.png) Il seguente esempio mostra un report che può essere generato in base a calcoli precedenti. [![Esempio di report in base a calcoli di esempio precedenti.](./media/cbrreport-1024x272.png)](./media/cbrreport.png)

## <a name="select-a-sorting-code-for-a-row-definition"></a>Selezionare un codice di ordinamento per una definizione di riga
I codici di ordinamento ordinano conti o valori, ordinano un report di scostamento budget o effettivo per lo scostamento massimo o ordinano le descrizioni di riga in ordine alfabetico. Sono disponibili i codici di ordinamento seguenti:

-   **SORT** Ordina il report in ordine crescente, in base ai valori della colonna specificata.
-   **ASORT** Ordina il report in ordine crescente, in base al valore assoluto dei valori della colonna specificata. In altre parole, il segno di ciascun valore viene ignorato quando i valori vengono ordinati. Il codice di formato ordina sequenzialmente i valori in base alla grandezza dello scostamento, indipendentemente dal fatto che lo scostamento sia positivo o negativo.
-   **SORTDESC** Ordina il report in ordine decrescente, in base ai valori della colonna specificata.
-   **ASORTDESC** Ordina il report in ordine decrescente, in base al valore assoluto dei valori della colonna specificata.

### <a name="select-a-sorting-code"></a>Selezionare un codice di ordinamento

1. In Progettazione report, fare clic su **Definizioni di riga** quindi aprire la definizione di riga da modificare.
2. Fare doppio clic sulla cella **Codice formato** quindi selezionare un codice di ordinamento.
3. Nella cella **Unità/Righe/Formule correlate**, specificare l'intervallo dei codici di riga da ordinare. Per specificare un intervallo, immettere il primo codice di riga, due punti (:) e l'ultimo codice di riga. Ad esempio, immettere **160:490** per specificare che l'intervallo è compreso tra la riga 160 e la riga 490.
4. Nella cella **Restrizione colonna**, immettere la lettera della colonna del report da utilizzare per l'ordinamento. 
   > [!Note] 
   > Includere solo le righe di importo nel calcolo di ordinamento.

### <a name="examples-of-ascending-and-descending-column-values"></a>Esempi di valori di colonna crescenti e decrescenti

Nel seguente esempio, i valori nella colonna D del report verranno elencati in ordine crescente per le righe da 160 a 490. Inoltre, i valori assoluti nella colonna G del report verranno elencati in ordine decrescente per le righe da 610 a 940.

| Codice di riga | Descrizione                                         | Codice formato | Unità/righe/formule correlate | Saldo normale | Restrizione di colonna | Collegamento a dimensioni finanziarie |
|----------|-----------------------------------------------------|-------------|-----------------------------|----------------|--------------------|------------------------------|
| 100      | Ordinato per scostamento mensile in ordine crescente       | DES         |                             |                |                    |                              |
| 130      |                                                     | SORT        | 160:490                     |                | D                  |                              |
| 160      | Vendite                                               |             |                             | C              |                    | 4100                         |
| 190      | Resi vendite                                       |             |                             |                |                    | 4110                         |
|          | ...                                                 |             |                             |                |                    |                              |
| 490      | Interessi attivi                                     |             |                             | C              |                    | 7000                         |
| 520      |                                                     | DES         |                             |                |                    |                              |
| 550      | Ordinato per scostamento assoluto da inizio anno in ordine decrescente | DES         |                             |                |                    |                              |
| 580      |                                                     | ASORTDESC   | 610:940                     |                | G                  |                              |
| 610      | Vendite                                               |             |                             | Z              |                    | 4100                         |
| 640      | Sales Returns                                       |             |                             |                |                    | 4110                         |
|          | ...                                                 |             |                             |                |                    |                              |
| 940      | Interessi attivi                                     |             |                             | Z              |                    | 7000                         |


## <a name="specify-a-format-override-cell"></a>Specificare una cella di sostituzione di formato
La cella **Sostituzione formato** specifica la formattazione utilizzata per la riga quando il report viene stampato. Questa formattazione sostituisce la formattazione specificata nella definizione di colonna e nella definizione di report. Per impostazione predefinita, la formattazione specificata in tali definizioni è valuta. Se una riga di report elenca il numero di cespiti, ad esempio il numero di edifici, e un'altra riga elenca il valore monetario di tali cespiti, è possibile sostituire la formattazione di valuta e immettere la formattazione numerica per la riga che specifica il numero di edifici. Specificare queste informazioni nella finestra di dialogo **Sostituzione formato**. Le opzioni disponibili dipendono dalla categoria di formato selezionato. L'area **Esempio** della finestra di dialogo mostra i formati di esempio. Sono disponibili le seguenti categorie di formato:

-   Formattazione di valuta
-   Formattazione numerica
-   Formattazione percentuale
-   Formattazione personalizzata

### <a name="override-cell-formatting"></a>Sostituire la formattazione delle celle

1.  In Progettazione report, aprire la definizione di riga da modificare.
2.  Nella riga con il formato da sostituire, fare doppio clic sulla cella nella colonna **Sostituzione formato**.
3.  Nella finestra di dialogo **Sostituzione formato**, selezionare le opzioni di formattazione da utilizzare per la riga nel report.
4.  Scegliere **OK**.

### <a name="currency-formatting"></a>Formattazione di valuta

La formattazione di valuta si applica a un importo fiscale e include il simbolo della valuta. Sono disponibili le opzioni seguenti:

- **Simbolo di valuta** - Il simbolo di valuta per il report. Questo valore sostituisce l'impostazione **Opzioni internazionali** delle informazioni di società.
- **Numeri negativi** I numeri negativi possono avere un segno meno (-), possono essere racchiusi tra parentesi oppure possono avere un triangolo (∆).
- **Posizioni decimali** – Il numero di cifre da visualizzare dopo la virgola decimale.
- **Testo di sostituzione valore zero** – Il testo da includere nel report quando un importo è 0 (zero). Questo testo verrà visualizzato come ultima riga nell'area **Esempio**. 
  > [!Note] 
  > Se la stampa è eliminata per i valori zero o nessuna attività del periodo, il testo viene eliminato.

### <a name="numeric-formatting"></a>Formattazione numerica

La formattazione numerica si applica a qualsiasi importo e non include un simbolo della valuta. Sono disponibili le seguenti opzioni:

- **Numeri negativi** I numeri negativi possono avere un segno meno (-), possono essere racchiusi tra parentesi oppure possono avere un triangolo (∆).
- **Posizioni decimali** – Il numero di cifre da visualizzare dopo la virgola decimale.
- **Testo di sostituzione valore zero** – Il testo da includere nel report quando un importo è 0 (zero). Questo testo verrà visualizzato come ultima riga nell'area **Esempio**. 
  > [!Note] 
  > Se la stampa è eliminata per i valori zero o nessuna attività del periodo, il testo viene eliminato.

### <a name="percentage-formatting"></a>Formattazione percentuale

La formattazione percentuale include il segno di percentuale (%). Sono disponibili le seguenti opzioni:

- **Numeri negativi** I numeri negativi possono avere un segno meno (-), possono essere racchiusi tra parentesi oppure possono avere un triangolo (∆).
- **Posizioni decimali** – Il numero di cifre da visualizzare dopo la virgola decimale.
- **Testo di sostituzione valore zero** – Il testo da includere nel report quando un importo è 0 (zero). Questo testo verrà visualizzato come ultima riga nell'area **Esempio**. 
  > [!Note] 
  > Se la stampa è eliminata per i valori zero o nessuna attività del periodo, il testo viene eliminato.

### <a name="custom-formatting"></a>Formattazione personalizzata

Utilizzare la categoria di formattazione personalizzata per creare una sostituzione di formato personalizzata. Sono disponibili le seguenti opzioni:

- **Tipo** - Formato personalizzato.
- **Testo di sostituzione valore zero** – Il testo da includere nel report quando un importo è 0 (zero). Questo testo verrà visualizzato come ultima riga nell'area **Esempio**. 
  > [!Note] 
  > Se la stampa è eliminata per i valori zero o nessuna attività del periodo, il testo viene eliminato.

Il tipo deve rappresentare il valore positivo e quindi il valore negativo. In genere, si immette un formato simile che differenzia i valori positivi e i valori negativi. Ad esempio, per specificare che i valori positivi e negativi hanno entrambi due posizioni decimali, ma i valori negativi vengono visualizzati tra parentesi, immettere **0.00;(0.00)**. Nella seguente tabella vengono indici i formati personalizzati da utilizzare per controllare il formato dei valori. Tutti gli esempi cominciano dal valore 1234,56.

| Formatta                         | Positiva   | Negativo     | Zero    |
|--------------------------------|------------|--------------|---------|
| 0                              | 1235       | -1235        | 0       |
| 0;0                            | 1235       | 1235         | 0       |
| 0;(0);-                        | 1235       | 1235         | -       |
| \#,\#\#\#;(\#,\#\#\#);“”       | 1,235      | (1,235)      | (Vuoto) |
| \#,\#\#0.00;(\#,\#\#0.00);zero | 1,234.56   | (1,234.56)   | Zero    |
| 0.00%;(0.00%)                  | 123456.00% | (123456.00%) | 0.00%   |

## <a name="specify-a-normal-balance-cell"></a>Specificare una cella saldo normale
La cella **Saldo normale** in una definizione di riga controlla il segno degli importi in una riga. Per invertire il segno di una riga, o se il saldo normale di un conto è in Avere, immettere una **C** nella cella **Saldo normale** per quella riga. Progettazione report inverte il segno su tutti i saldi contabili in avere della riga. Quando Progettazione report converte i conti, rimuove la caratteristica dare/avere da tutti gli importi e quindi rende il totale diretto. Ad esempio, per calcolare il ricavo netto, sottrarre le spese dal reddito. In genere, le righe di totale e di calcolo non sono interessate da un codice **C**. Tuttavia, il controllo di stampa **XCR** nella definizione di colonna inverte il segno di qualsiasi riga contenente una **C** nella colonna **Saldo normale**. La formattazione è particolarmente importante se si desidera visualizzare tutti gli scostamenti sfavorevoli come importi negativi. Se un numero di totale o calcolo ha il segno errato, immettere una **C** nella cella **Saldo normale** per invertire il segno della riga.

## <a name="specify-a-row-modifier-cell"></a>Specificare una cella del modificatore di riga
Il contenuto della cella **Modificatore di riga** in una definizione di riga sostituisce gli anni fiscali, i periodi e altre informazioni specificate nella definizione di colonna per la riga. Il modificatore selezionato si applica a ciascun conto nella riga. È possibile modificare ogni riga utilizzando uno o più dei seguenti tipi di modificatori:

-   Modificatori di conto
-   Modificatori di codice registro
-   Attributi di transazione e conto

### <a name="override-a-column-definition"></a>Sostituire una definizione colonna

1.  In Progettazione report, aprire la definizione di riga da modificare.
2.  Nella riga in cui si desidera sostituire la definizione di colonna, fare doppio clic sulla cella **Modificatore di riga** .
3.  Nella finestra di dialogo **Modificatore di riga**, selezionare un'opzione nel campo **Modificatore di conto**. Per una descrizione delle opzioni, vedere la sezione Modificatori di conto.
4.  Nel campo **Modificatore di codice registro**, selezionare il codice registro da utilizzare per la riga.
5.  In **Attributi**, seguire questi passaggi per aggiungere una voce per ogni attributo che deve essere incluso nel codice di riga:
    1.  Fare doppio clic sulla cella **Attributo** e selezionare il nome di un attributo. **Attenzione:** sostituire il simbolo cancelletto (\#) con un valore numerico.
    2.  Fare doppio clic sulla cella **Da** e immettere il primo valore per l'intervallo.
    3.  Fare doppio clic sulla cella **A** e immettere l'ultimo valore per l'intervallo.

6.  Scegliere **OK**.

### <a name="account-modifiers"></a>Modificatori di conto

Quando si seleziona un conto specifico, Progettazione report in genere combina il conto e gli anni fiscali, i periodi e altre informazioni specificate nella definizione di colonna. È possibile utilizzare informazioni diverse, ad esempio periodi fiscali diversi, per righe specifiche. Nella seguente tabella vengono indicati i modificatori di conto disponibili. Sostituire il simbolo cancelletto (\#) con un valore uguale o inferiore al numero di periodi di un anno fiscale.

| Modificatore di conto | Cosa viene stampato                                                                           |
|------------------|-------------------------------------------------------------------------------------------|
| /BB              | Il saldo iniziale per un conto.                                                     |
| /\#              | Il saldo per il periodo specificato.                                                     |
| /-\#             | Il saldo per il periodo che è \# periodi prima del periodo corrente.                  |
| /+\#             | Il saldo per il periodo che è \# periodi dopo il periodo corrente.                   |
| /C               | Il saldo del periodo corrente.                                                       |
| /C-\#            | Il saldo per il periodo che è \# periodi prima del periodo corrente.                  |
| /C+\#            | Il saldo per il periodo che è \# periodi dopo il periodo corrente.                   |
| /Y               | Il saldo da inizio anno del periodo corrente.                                      |
| /Y-\#            | Il saldo da inizio anno per il periodo che è \# periodi prima del periodo corrente. |
| /Y+\#            | Il saldo da inizio anno per il periodo che è \# periodi dopo il periodo corrente.  |

### <a name="book-code-modifiers"></a>Modificatori di codice registro

È possibile limitare una riga a un codice registro esistente. La definizione di colonna deve includere almeno una colonna **FD** con un codice registro. 
> [!NOTE]
> La restrizione del codice registro per una riga sostituisce le restrizioni del codice registro nella definizione di colonna per la riga.

### <a name="account-and-transaction-attributes"></a>Attributi di conto e di transazione

Alcuni sistemi di contabilità supportano gli attributi di conto e gli attributi di transazione nei dati finanziari. Questi attributi vengono eseguiti come segmenti di conti virtuali e possono riportare ulteriori informazioni sul conto o sulla transazione. Queste informazioni aggiuntive possono essere ID conto, ID batch, codici postali o altri attributi. Se il sistema contabile supporta gli attributi, è possibile utilizzare gli attributi di conto o gli attributi di transazione come modificatori riga nella definizione di riga. Per informazioni su come sostituire le informazioni di riga, vedere la sezione "Sostituire una definizione colonna" in precedenza in questo articolo.

## <a name="specify-a-link-to-financial-dimensions-cell"></a>Specificare il collegamento a una cella di dimensioni finanziarie
La cella **Collegamento a dimensioni finanziarie** contiene i collegamenti ai dati finanziari che devono essere inclusi in ciascuna riga del report. La cella contiene i valori di dimensione, ma è possibile specificare le celle in un foglio di lavoro di Microsoft Excel in luogo o in aggiunta ai valori di segmento o di dimensione. Per aprire la finestra di dialogo **Dimensioni**, fare doppio clic sulla cella **Collegamento a dimensioni finanziarie**. 
> [!NOTE]
> Nella progettazione report non è possibile selezionare conti, dimensioni o campi del sistema Microsoft Dynamics ERP che includono uno dei seguenti caratteri riservati: & \*, \[, \], { oppure }. Per specificare le informazioni per una riga già presente nella definizione di riga, aggiungere le informazioni nella cella **Collegamento a dimensioni finanziarie**. Per aggiungere nuove righe di collegamento ai dati finanziari, utilizzare la finestra di dialogo **Inserisci righe da** per creare nuove righe nella definizione di report. Il titolo di colonna cambia a seconda di come la colonna è stata configurata, come illustrato nella seguente tabella.

| Tipo di collegamento selezionato       | Descrizione del collegamento delle modifiche di colonna a |
|----------------------------------|----------------------------------------------------|
| Dimensioni finanziarie             | Collegamento a dimensioni finanziarie                       |
| Foglio di lavoro esterno               | Collegamento a foglio di lavoro                                  |
| Dimensioni finanziarie + foglio di lavoro | Collegamento a dimensioni finanziarie + foglio di lavoro           |
| Report di strumento di creazione report di gestione       | Report di strumento di creazione report di gestione                         |

### <a name="specify-a-dimension-or-range"></a>Specificare una dimensione o un intervallo

1.  In Progettazione report, aprire la definizione di riga da modificare.
2.  Fare doppio clic su una cella della colonna **Collegamento a Dimensioni finanziarie**.
3.  Nella finestra di dialogo **Dimensioni** fare doppio clic su una cella in corrispondenza del nome della dimensione.
4.  Nella finestra di dialogo per la dimensione, selezionare **Singolo o intervallo**.
5.  Nel campo **Da**, immettere la dimensione iniziale o fare clic su ![Sfoglia](https://i-technet.sec.s-msft.com/dynimg/IC679490.gif "Sfoglia") per cercare le dimensioni disponibili. Per immettere un intervallo di dimensioni, immettere la dimensione finale nel campo **A**.
6.  Fare clic su **OK** per chiudere la finestra di dialogo per la dimensione. Nella finestra di dialogo **Dimensioni** è visualizzata la dimensione o l'intervallo aggiornato.
7.  Scegliere **OK** per chiudere la finestra di dialogo **Dimensioni**.

## <a name="display-zero-balance-accounts-in-a-row-definition"></a>Visualizzare conti con saldo zero in una definizione di riga
Per impostazione predefinita, Progettazione report non stampa una riga se non ha un saldo corrispondente nei dati finanziari. Di conseguenza, è possibile creare una definizione di riga contenente tutti i valori di segmenti naturali o tutti i valori di dimensione e quindi utilizzare la definizione di riga per uno dei reparti.

### <a name="modify-zero-balance-settings"></a>Modificare le impostazioni di saldo zero

1.  In Progettazione report, aprire la definizione di report da modificare.
2.  Nella scheda **Impostazioni**, selezionare in **Altra formattazione** le opzioni per la definizione di riga utilizzata nella definizione di report.
3.  Scegliere **Salva** dal menu **File** per salvare le modifiche.

## <a name="use-wildcard-characters-and-ranges-in-a-row-definition"></a>Utilizzare i caratteri jolly e gli intervalli in una definizione di riga
Quando si immette un valore di segmento naturale nella finestra di dialogo <strong>Dimensioni</strong>, è possibile inserire un carattere jolly (? o \*) in qualsiasi posizione di un segmento. Progettazione report estrae tutti i valori per le posizioni definite senza considerare i caratteri jolly. Ad esempio, la definizione di riga contiene solo i valori di segmenti naturali e i segmenti naturali hanno quattro caratteri. Se si immette <strong>6???</strong> in una riga, Progettazione report include tutti i conti con un valore di segmento naturale che inizia con 6. Se si immette <strong>6\</strong><em>, vengono restituiti gli stessi risultati, ma i risultati includono anche i valori di larghezza variabile, ad esempio **60</em>* e <strong>600000</strong>. Progettazione report sostituisce ogni carattere jolly (?) con l'intervallo completo di valori possibili che includono lettere e caratteri speciali. Ad esempio, nell'intervallo compreso tra <strong>12?0</strong> e <strong>12?4</strong>, il carattere jolly in <strong>12?0</strong> viene sostituito con il valore minimo del set di caratteri e il carattere jolly in <strong>12?4</strong> viene sostituito con il valore massimo del set di caratteri. 
> [!Note] 
> È consigliabile evitare di utilizzare i caratteri jolly per i conti iniziali e finali negli intervalli. Se si utilizzano i caratteri jolly nel conto iniziale o finale, è possibile che i risultati siano imprevisti.

### <a name="single-segment-or-single-dimension-ranges"></a>Intervalli di dimensione singola o segmento singolo

È possibile specificare un intervallo di valori di dimensione o di segmento. Il vantaggio di specificare un intervallo consiste nel fatto che non si deve aggiornare la definizione di riga ogni volta che un nuovo valore di dimensione o di segmento viene aggiunto ai dati finanziari. Ad esempio, l'intervallo **+Account=\[6100:6900\]** effettua il pull dei valori dei conti compresi tra 6100 e 6900 nell'importo di riga. Quando un intervallo include un carattere jolly (?), Progettazione report non valuta l'intervallo sulla base di un carattere alla volta. I limiti minimo e massimo dell'intervallo sono determinati e quindi i valori finali e tutti i valori tra loro sono inclusi. 
> [!Note] 
> Nella progettazione report non è possibile selezionare conti, dimensioni o campi del sistema Microsoft Dynamics ERP che includono uno dei seguenti caratteri riservati: & \*, \[, \], { oppure }. È possibile aggiungere una e commerciale (&) solo quando vengono automaticamente create le definizioni di riga utilizzando la finestra di dialogo **Inserisci righe da dimensioni**.

### <a name="multiple-segment-or-multiple-dimension-ranges"></a>Intervalli di più dimensioni o segmenti

Quando si immette un intervallo utilizzando le combinazioni di più valori di dimensione, il confronto dell'intervallo viene eseguito sulla base di ..\dimensioni-finanziarie\una-dimensione-alla-volta. Il confronto dell'intervallo non può essere eseguito in base a carattere alla volta o in base a un segmento parziale. Ad esempio, l'intervallo **+Account=\[5000:6000\], Department=\[1000:2000\], Cost center=\[00\]** comprende solo i conti corrispondenti a ogni segmento. In questo esempio, la prima dimensione deve essere compresa nell'intervallo da 5000 a 6000, la seconda dimensione deve essere compresa nell'intervallo da 1000 a 2000 e l'ultima dimensione deve essere 00. Ad esempio, **+Account=\[5100\], Department=\[1100\], Cost center=\[01\]** non viene incluso nel report, perché l'ultimo segmento non rientra nell'intervallo specificato. Se il valore del segmento include spazi, racchiudere il valore in parentesi quadre (\[ \]). I seguenti valori sono validi per un segmento a quattro caratteri: **\[ 234\], \[123 \], \[1 34\]**. I valori di dimensione devono essere racchiusi tra parentesi quadre (\[ \]) e Progettazione report aggiunge queste parentesi automaticamente. Quando un intervallo di più segmenti o dimensioni include caratteri jolly (? oppure \*), il limite superiore e inferiore dell'intervallo a più segmenti o dimensioni vengono determinati e vengono inclusi i valori finali e tutti i valori compresi tra loro. Se l'intervallo è ampio, ad esempio l'intervallo di tutti i conti compresi tra 40000 e 99999, è necessario specificare un conto di inizio e un conto di fine validi se possibile. 
> [!Note] 
> Nella progettazione report non è possibile selezionare conti, dimensioni o campi del sistema Microsoft Dynamics ERP che includono uno dei seguenti caratteri riservati: & \*, \[, \], { oppure }. È possibile aggiungere una e commerciale (&) solo quando vengono automaticamente create le definizioni di riga utilizzando la finestra di dialogo **Inserisci righe da dimensioni**.

## <a name="add-or-subtract-from-other-accounts-in-a-row-definition"></a>Aggiungere o sottrarre da altri conti in una definizione riga
Per aggiungere o sottrarre gli importi monetari di un conto dagli importi monetari di un altro conto, è possibile utilizzare il segno più (+) e il segno meno (-) nella cella **Collegamento a dimensioni finanziarie**. Nella seguente tabella vengono visualizzati i formati accettabili per l'aggiunta e la sottrazione dei collegamenti ai dati finanziari.

| Operazione  | Utilizzare questo formato  |
|------------|-----------------|
| Aggiungere due conti completi.                                                       | +Division=\[000\], Account=\[1205\], Department=\[00\]+Division=\[100\], Account=\[1205\], Department=\[00\] |
| Aggiungere due valori di segmento.                                                                 | +Account=\[1205\]+Account=\[1210\]                                                                           |
| Aggiungere i valori di segmento includendo i caratteri jolly.                                    | +Account=\[120?+Account=\[11??\]                                                                             |
| Aggiungere un intervallo di conti completi.                                                | +Division=\[000:100\], Account=\[1205\], Department=\[00\]                                                   |
| Aggiungere un intervallo di valori di segmento.                                                          | +Account=\[1200:1205\]                                                                                       |
| Aggiungere un intervallo di valori di segmento includendo i caratteri jolly.                         | +Account=\[120?:130?\]                                                                                       |
| Sottrarre un conto completo da un altro conto completo.              | +Division=\[000\], Account=\[1205\], Department=\[00\]-Division=\[100\], Account=\[1205\], Department=\[00\] |
| Sottrarre un valore di segmento da un altro valore di segmento.                                  | +Account=\[1205\]-Account=\[1210\]                                                                           |
| Sottrarre un valore di segmento che include un carattere jolly da un altro valore di segmento. | +Account=\[1200\]-Account=\[11??\]                                                                           |
| Sottrarre un intervallo di conti completi.                                           | -Division=\[000:100\], Account=\[1200:1205\], Department=\[00:01\]                                           |
| Sottrarre un intervallo di valori di segmento.                                                     | -Account=\[1200:1205\]                                                                                       |
| Sottrarre un intervallo di valori di segmento includendo i caratteri jolly.                    | -Account=\[120?:130?\]                                                                                       |

Sebbene sia possibile modificare direttamente i conti, è possibile anche utilizzare la finestra di dialogo **Dimensioni** per applicare la formattazione corretta ai collegamenti dei dati finanziari. I valori possono includere caratteri jolly (? oppure \*). Tuttavia, nella progettazione report non è possibile selezionare conti, dimensioni o campi del sistema Microsoft Dynamics ERP che includono uno dei seguenti caratteri riservati: &, \*, \[, \], { oppure }. 
> [!Note] 
> Per sottrarre i valori, è necessario racchiudere i valori tra parentesi. Ad esempio, se si immette **450?-(4509)**, viene visualizzato come **+Account=\[4509\]-Account=\[450?\]** e si indica a Progettazione report di sottrarre l'importo per il segmento di conto 4509 dall'importo di un segmento di conto che inizia con 450.

### <a name="add-or-subtract-accounts-from-other-accounts"></a>Aggiungere o sottrarre i conti da altri conti

1.  In Progettazione report, aprire la definizione di riga da modificare.
2.  Nella riga appropriata, fare doppio clic sulla cella della colonna **Collegamento a dimensioni finanziarie**.
3.  Nella prima riga della finestra di dialogo **Dimensioni**, effettuare le operazioni seguenti:
    1.  Nel primo campo, selezionare tutte le dimensioni (impostazione predefinita) o fare clic per aprire la finestra di dialogo **Gestire i set di dimensioni**, in cui è possibile creare, modificare, copiare o eliminare un set.
    2.  Fare doppio clic sulla cella **Operatore +/-** e selezionare l'operatore più (**+**) o meno (**-**) che si applica a uno o più valori o set di dimensioni nella riga.
    3.  Nella colonna appropriata del valore di dimensione, fare doppio clic sulla cella per aprire la finestra di dialogo **Dimensioni** e scegliere se il valore di dimensione è associato a un utente o un intervallo, a un set di valori di dimensione o a conti di totalizzazione. Per le descrizioni dei campi della finestra di dialogo **Dimensioni**, vedere la sezione "Descrizione della finestra di dialogo Dimensioni".
    4.  Immettere i valori di segmento nella colonna **Da** e nella colonna **A**.

4.  Ripetere i passaggi da 2 a 3 per aggiungere ulteriori operazioni.

> [!Note] 
> L'operatore si applica a tutte le dimensioni della riga.

## <a name="description-of-the-dimensions-dialog-box"></a>Descrizione della finestra di dialogo Dimensioni
Nella seguente tabella sono descritti i campi della finestra di dialogo **Dimensioni**.

| Articolo                | Descrizione                                                                                                                                                                                                                                                                                             |
|---------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Utente o intervallo | Nel campo **Da**, immettere il nome di un conto o fare clic sul pulsante **Sfoglia** ![Sfoglia](https://i-technet.sec.s-msft.com/dynimg/IC679490.gif "Sfoglia") per individuare il conto. Per selezionare un intervallo, immettere o individuare un valore nel campo **A**.                                             |
| Set di valori di dimensione | Nel campo **Nome** immettere il nome di un set di valori di dimensione. Per creare, modificare, copiare o eliminare un set, fare clic su **Gestire set di valori di dimensione**. Il campo **Formula** viene popolato automaticamente con la formula della cella **Collegamento a dimensioni finanziarie** per il set di valori di dimensione nella definizione di riga. |
| Conti di totalizzazione   | Nel campo **Nome**, immettere o selezionare una dimensione dei conti di totalizzazione. Il campo **Formula** viene popolato automaticamente con la formula della cella **Collegamento a dimensioni finanziarie** per il conto di totalizzazione nella definizione di report.                                                                       |

## <a name="add-dimension-value-sets-in-a-row-definition"></a>Aggiungere set di valori di dimensione in una definizione di riga
Un set di valori di dimensione è un gruppo denominato di valori di dimensione. Un set di valori di dimensione può contenere i valori in una sola dimensione, ma è possibile utilizzare un set di valori di dimensione in più definizioni di riga, definizioni di colonna, definizioni di albero gerarchico e definizioni di report. È inoltre possibile combinare set di valori di dimensione in una definizione di report. Quando una modifica ai dati finanziari richiede di modificare il set di valori di dimensione, è possibile aggiornare la definizione del set di valori di dimensione e l'aggiornamento si applica a tutte le aree che utilizzano il set di valori di dimensione. Ad esempio, se in genere si indica un intervallo di valori per il collegamento ai dati finanziari, ad esempio i valori compresi tra 5100 e 5600, è possibile assegnare questo intervallo a un set di conti denominato Sales. Dopo la creazione di un set di valori di dimensione è possibile selezionarlo come collegamento ai dati finanziari. In un altro esempio, se si dispone di un intervallo di valori da 5100 a 5600 assegnato a Vendite e 4175 è assegnato a Sconti, è possibile determinare le vendite totali sottraendo Sconti da Vendite. Questa operazione è visualizzata come **(5100:5600)-4175**.

### <a name="create-a-set-of-dimension-values"></a>Creare un set di valori di dimensione

1.  In Progettazione report, aprire la definizione di riga, colonna o albero da modificare.
2.  Nel menu **Modifica**, fare clic su **Gestire set di valori di dimensione**.
3.  Nella finestra di dialogo **Gestire set di valori di dimensione**, campo **Dimensione**, selezionare il tipo di set di valori di dimensione da creare quindi fare clic su **Nuovo**.
4.  Nella finestra di dialogo **Nuovo** immettere un nome e una descrizione per il set.
5.  Nella colonna **Da**, fare doppio clic su una cella.
6.  Nella finestra di dialogo **Conto**, selezionare il nome del conto nell'elenco o individuare la voce nel campo **Cerca**. Fare clic su **OK**.
7.  Ripetere i passaggi da 5 a 6 nella colonna **A** per progettare una formula per tale operatore.
8.  Quando la formula viene completata, fare clic su **OK**.
9.  Nella finestra di dialogo **Gestisci set di dimensioni** fare clic su **Chiudi**.

### <a name="update-a-set-of-dimension-values"></a>Aggiornare un set di valori di dimensione

1. In Progettazione report aprire la definizione di riga, di colonna o di albero gerarchico da modificare.
2. Nel menu **Modifica**, fare clic su **Gestire set di valori di dimensione**.
3. Nella finestra di dialogo **Gestire set di valori di dimensione**, campo **Dimensione**, selezionare il tipo di dimensione.
4. Nell'elenco, selezionare il set di valori di dimensione da aggiornare e quindi fare clic su **Modifica**.
5. Nella finestra di dialogo **Modifica**, modificare i valori di formula da includere nel set. 
   > [!Note] 
   > Se si aggiungono nuovi conti o dimensioni, assicurarsi di modificare i set esistenti di valori di dimensione per includere le modifiche.
6. Fare doppio clic sulla cella e selezionare l'operatore, il conto **Da** e il conto **A** appropriati.
7. Fare clic su **OK** nella finestra di dialogo **Modifica** e salvare le modifiche.

### <a name="copy-a-dimension-set"></a>Copiare un set di dimensioni

1.  In Progettazione report, aprire la definizione di riga, colonna o albero da modificare.
2.  Nel menu **Modifica**, fare clic su **Gestire set di valori di dimensione**.
3.  Nella finestra di dialogo **Gestire set di valori di dimensione**, campo **Dimensione**, selezionare il tipo di dimensione.
4.  Nell'elenco selezionare il set da copiare e fare clic su **Salva con nome**.
5.  Immettere un nuovo nome per il set copiato e scegliere **OK**.

### <a name="delete-a-dimension-set"></a>Eliminare un set di dimensioni

1.  In Progettazione report aprire la definizione di riga, di colonna o di albero gerarchico da modificare.
2.  Nel menu **Modifica**, fare clic su **Gestire set di valori di dimensione**.
3.  Nella finestra di dialogo **Gestire set di valori di dimensione**, campo **Dimensione**, selezionare il tipo di dimensione.
4.  Selezionare il set da eliminare, quindi fare clic su **Elimina**. Fare clic su **Sì** per eliminare definitivamente il set di valori di dimensione.


## <a name="additional-resources"></a>Risorse aggiuntive

[Creazione di report finanziari](financial-reporting-intro.md)




