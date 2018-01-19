---
title: Definizioni di colonna nei report finanziari
description: "In questo articolo vengono fornite informazioni sulle definizioni di colonna. Una definizione di colonna è un componente di report, o blocco predefinito, che specifica il contenuto delle colonne in un report. Al pari delle definizioni di riga, le definizioni delle colonne di base possono essere utilizzate nei report."
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 106601
ms.assetid: 66e72a48-edab-4e9d-815f-596a1623c258
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 8c877a4ad6d4c29607159da52bf1cedae1476f92
ms.contentlocale: it-it
ms.lasthandoff: 11/03/2017

---

# <a name="column-definitions-in-financial-reports"></a>Definizioni di colonna nei report finanziari

[!include[banner](../includes/banner.md)]


In questo articolo vengono fornite informazioni sulle definizioni di colonna. Una definizione di colonna è un componente di report, o blocco predefinito, che specifica il contenuto delle colonne in un report. Al pari delle definizioni di riga, le definizioni delle colonne di base possono essere utilizzate nei report.

<a name="create-and-modify-a-column-definition"></a>Creare e modificare una definizione di colonna
-------------------------------------

Una definizione di colonna può contenere da due a 255 colonne.

### <a name="create-a-column-definition"></a>Creare una definizione di colonna

1.  In Progettazione report, nel pannello di navigazione, fare clic su **Definizioni colonne**.
2.  Scegliere **Nuovo**, quindi **Definiziona colonna** dal menu **File**.
3.  Aggiungere il contenuto della definizione di colonna.

### <a name="open-a-column-definition"></a>Aprire una definizione colonna

1.  In Progettazione report, nel pannello di navigazione, fare clic su **Definizioni colonne**.
2.  Fare doppio clic su una definizione di colonna per aprirla.

### <a name="add-a-column-to-a-column-definition"></a>Aggiungere una colonna a una definizione di colonna

1.  In Progettazione report, fare clic su **Definizioni colonne** quindi aprire la definizione di colonna da modificare.
2.  Selezionare la colonna in cui una nuova colonna deve essere immessa.
3.  Nel menu **Modifica** fare clic su **Inserisci colonna**. La nuova colonna verrà visualizzata a sinistra di quella selezionata.

### <a name="delete-a-column-from-a-column-definition"></a>Eliminare una colonna da una definizione di colonna

1.  In Progettazione report fare clic su **Definizioni di colonna**, quindi aprire la definizione di colonna da modificare.
2.  Selezionare la colonna da eliminare.
3.  Scegliere **Elimina colonna** dal menu **Modifica**.

## <a name="contents-of-a-column-definition"></a>Contenuti di una definizione di colonna
Una definizione di colonna contiene le seguenti informazioni:

-   Una colonna dekle descrizioni per la definizione di riga
-   Colonne Importo che mostrano i dati dai dati finanziari, un foglio di lavoro di Microsoft Excel, o i calcoli basati su altri dati della definizione di colonna
-   Colonne di formattazione
-   Colonne attributo

Queste informazioni vengono visualizzate nekle seguenti aree nella definizione di colonna:

-   L'area delle intestazioni della definizione di colonna contiene il testo e la formattazione intestazione visualizzati nel report. Un'intestazione può essere applicata a una singola colonna di dati, estesa a più colonne o applicata a colonne su base condizionale. La definizione di colonna può includere il numero desiderato di righe di intestazione. **Nota:** Le intestazioni di colonna si applicano a ogni colonna dei dati nel report. Le intestazioni report vengono applicate all'intero report. Definire le intestazioni del report nella scheda **Intestazioni e piè di pagina** della definizione di report.
-   Le righe di dettaglio della colonna sono le righe sotto le righe di intestazione nella definizione di colonna. Le righe di dettaglio della colonna definiscono le informazioni incluse nel report. Nella tabella riportata di seguito vengono elencate e descritte le righe di dettaglio della colonna.

    | Nome della riga di dettaglio di colonna                                                | Descrizione                                                                                            |
    |-----------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------|
    | Tipo di colonna                                                           | (Obbligatorio) Specifica il tipo di dati nella colonna.                                                     |
    | Codice libro/Categoria attributi                                          | Specifica le informazioni di dati finanziari per le colonne di tipo **FD** e **ATTR**.                       |
    | Anno fiscale Periodo Periodi coperti                                    | Specifica le informazioni di dati finanziari per le colonne di tipo **FD** .                                     |
    | Formula                                                               | Specifica una formula di calcolo per le colonne di tipo **CALC**.                                        |
    | Larghezza colonna Spazi aggiuntivi prima di colonna Sostituzione formato Controllo stampa | Specifica le opzioni di formattazione speciali.                                                                        |
    | Restrizioni di colonna                                                   | Limita i dati.                                                                                         |
    | Unità gerarchica                                                        | Limita la colonna, in modo che mostra i dati solo per l'unità gerarchica specificata.                      |
    | Visualizzazione valuta Filtro valuta                                      | Formato della valuta.                                                                                       |
    | Filtro dimensioni                                                      | Specifica un filtro per limitare i dati a determinate unità gerarchiche dei dati finanziari.                           |
    | Filtro attributi                                                      | Specifica un filtro per limitare i dati finanziari.                                                       |
    | Data di inizio Data di fine                                                   | Limita i dati finanziari a date specifiche.                                                         |
    | Motivazione                                                         | Allinea a sinistra, al centro o a destra il testo di descrizione specificato nella definizione di riga. |

## <a name="column-restrictions-in-a-column-definition"></a>Restrizioni di colonna in una definizione di colonna
È possibile utilizzare le restrizioni di colonna per specificare come una definizione di colonna utilizza i dati o calcola le informazioni. È inoltre possibile limitare una colonna del report a un'unità specifica o per date specifiche. **Nota:** un codice **Restrizione di colonna** sostituisce qualsiasi impostazione in conflitto assegnata nella definizione di riga.

### <a name="column-restrictions-cell"></a>Cella Restrizioni di colonna

La cella **Restrizioni di colonna** può includere i codici che limitano o eliminano informazioni, ad esempio formattazione riga, dettagli e importi, per tale colonna.

#### <a name="add-a-column-restriction-in-a-column-definition"></a>Aggiungere una restrizione di colonna in una definizione di colonna

1.  In Progettazione report, aprire la definizione di colonna da modificare.
2.  Fare doppio clic sulla cella **Restrizioni di colonna** per la colonna da limitare.
3.  Nella finestra di dialogo **Restrizioni di colonna**, selezionare uno o più codici nell'elenco e fare clic su **OK**.

### <a name="column-restriction-codes"></a>Codici di restrizione colonna

Nella seguente tabella sono descritti i codici restrizione della colonna.

| Codice Restrizione di colonna | Descrizione                                                                                                                                                                                                                                                                                                                             |
|-------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| SU                      | Elimina la sottolineatura per una colonna in cui o un comando di sottolineatura (**---**) o un comando di doppia sottolineatura (**===**) viene immesso nella definizione di riga. Ad esempio, si può non volere sottolineare gli importi prodotti da un calcolo percentuale.                                                                        |
| ST                      | Elimina i totali, in modo che solo i dettagli vengono visualizzati nella colonna (ad esempio, una colonna statistica).                                                                                                                                                                                                                                      |
| SD                      | Elimina i dettagli, in modo che solo le righe **TOT** e **CAL** (dalla definizione di riga) vengono visualizzate nella colonna.                                                                                                                                                                                                                              |
| DR                      | Limita gli importi in una colonna **FD** agli importi in Dare.                                                                                                                                                                                                                                                                              |
| CR                      | Limita gli importi in una colonna **FD** agli importi in Avere.                                                                                                                                                                                                                                                                             |
| ADJ                     | Limita gli importi nella colonna agli importi di rettifica di periodo, se questi importi sono disponibili.                                                                                                                                                                                                                                        |
| XAD                     | Limita gli importi nella colonna in modo da escludere gli importi di rettifica di periodo.                                                                                                                                                                                                                                                     |
| TP                      | Limita gli importi nella colonna, in modo che solo le transazioni registrate vengono incluse, se le transazioni sono disponibili.                                                                                                                                                                                                                 |
| UPT                     | Limita gli importi nella colonna, in modo che solo le transazioni non registrate vengono incluse, se le transazioni sono disponibili. **Nota:** Non tutti i provider di dati supportano le transazioni non registrate. Per ulteriori informazioni, vedere [guida all'integrazione dei dati](http://go.microsoft.com/fwlink/?LinkID=162565) per il sistema Microsoft Dynamics ERP. |

### <a name="restrict-a-column-to-a-reporting-unit"></a>Limitare una colonna a un'unità gerarchica

1.  In Progettazione report, aprire la definizione di colonna da modificare.
2.  Fare doppio clic sulla cella **Unità gerarchica** per la colonna da limitare.
3.  Nella finestra di dialogo **Selezione unità gerarchica**, elenco **Albero gerarchico**, selezionare un albero.
4.  Espandere o comprimere l'elenco delle unità, selezionare un'unità gerarchica quindi fare clic su **OK**.

## <a name="format-column-headers"></a>Formattare intestazioni di colonna
È possibile aggiungere, modificare ed eliminare le intestazioni che vengono visualizzate nella parte superiore delle colonne in un report. È inoltre possibile configurare intestazioni di colonne con spanning condizionale basate sul campo **Periodo** dalle definizioni di colonna e sul campo **Periodo di base** dalle definizioni di report. La funzionalità periodo di base consente di risparmiare tempo quando si creano report di previsioni ricorrenti.

### <a name="create-and-manage-column-headers"></a>Creare e gestire le intestazioni di colonna

È possibile usare la finestra di dialogo **Intestazione colonna** per aggiungere, modificare ed eliminare le intestazioni che vengono visualizzate nella parte superiore delle colonne in un report. Nella seguente tabella sono descritti i campi della finestra di dialogo **Intestazione colonna**.

| Campo                 | Descrizione                                                                                                                                                                                                                                                                                                              |
|-----------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Testo intestazione colonna    | Questo testo verrà visualizzato nell'intestazione di colonna. È possibile immettere il testo direttamente in questo campo, o fare clic su **Inserisci testo automatico** per selezionare un'opzione che consente di aggiornare l'intestazione di colonna ogni volta che il report viene generato. Per includere più codici testo automatico, fare clic su **Inserisci testo automatico** ancora quindi fare clic su un altro codice nell'elenco. |
| Opzioni di formattazione        | Applica la formattazione all'intestazione di colonna, ad esempio casella o sottolineatura.                                                                                                                                                                                                                                                           |
| Estendi da Estendi a | Definisce la colonna o le colonne a cui si applica il testo dell'intestazione.                                                                                                                                                                                                                                                            |
| Motivazione         | Specifica in che modo il testo dell'intestazione di colonna deve essere allineato per la colonna o l'intervallo delle colonne specificato nei campi **Estendi da** ed **Estendi a**.                                                                                                                                                               |

### <a name="create-a-column-header"></a>Creare un'intestazione di colonna

1.  In Progettazione report, aprire la definizione di colonna da modificare.
2.  Fare doppio clic su una cella di intestazione.
3.  Nella finestra di dialogo **Intestazione colonna**, digitare il testo dell'intestazione di colonna. In alternativa, fare clic su **Inserisci testo automatico** e selezionare un'opzione.
4.  Nel campo **Opzioni di formattazione**, selezionare un formato dell'intestazione.
5.  Nel campo **Estendi da** immettere la lettera di colonna da cui l'intestazione di colonna deve cominciare. Nel campo **Estendi a** immettere la lettera di colonna a cui l'intestazione di colonna deve terminare.
6.  In **Giustificazione**, selezionare se il testo dell'intestazione di colonna deve essere allineato a sinistra, al centro o a destra.
7.  Scegliere **OK**.

### <a name="add-a-column-header-row"></a>Aggiungere una riga dell'intestazione di colonna

1.  In Progettazione report, aprire la definizione di colonna da modificare.
2.  Selezionare una cella nella riga di intestazione.
3.  Nel menu **Modifica** fare clic su **Inserisci riga**. La nuova riga viene inserita sopra la riga selezionata nel passaggio 2. **Nota:** se sono presenti quattro o più righe di intestazioni in un report, le intestazioni risulteranno sovrapposte quando il report verrà esportato in un foglio di calcolo Excel. Per visualizzare tutte le intestazioni nel report, aumentare il margine superiore nella definizione di report.

### <a name="delete-a-column-header-row"></a>Eliminare una riga dell'intestazione di colonna

1.  In Progettazione report, aprire la definizione di colonna da modificare.
2.  Nella riga di intestazione, selezionare la cella da eliminare.
3.  Nel menu **Modifica** fare clic su **Elimina riga**.

### <a name="create-an-automatically-generated-header"></a>Creare un'intestazione generata automaticamente

Progettazione report può generare automaticamente le intestazioni di colonna, in base ai codici testo automatico. I codici testo automatico sono variabili che vengono aggiornate in ogni volta che un report viene generato. Qualsiasi intestazione di colonna può includere questi codici per specificare le informazioni di report che possono variare, ad esempio le date o numeri di periodo. Di conseguenza, è possibile utilizzare una sola definizione di colonna per più definizioni di report, periodi e alberi gerarchici. Poiché i codici testo automatico si basano sulle informazioni del calendario dalle righe di dettaglio della definizione di colonna, sono supportati solo per le colonne **CALC**, **FD** e **WKS**. La modalità in cui un codice testo automatico viene visualizzato nella cella di intestazione di colonna influisce sulle informazioni visualizzate nel report. Nella finestra di dialogo **Intestazione di colonna**, i codici testo automatico vengono visualizzati con maiuscole e minuscole. Di conseguenza, il testo verrà visualizzato con maiuscole e minuscole nel report. Ad esempio, in un anno di calendario standard, **@CalMonthLong** risolve il mese **7** in **luglio**. Se il nome del mese è in maiuscolo (ad esempio **LUGLIO**)), immettere il codice testo automatico in caratteri maiuscoli nel campo **Testo intestazione colonna**. Ad esempio, immettere **@CALMONTHLONG**. È possibile combinare codici e testo. Ad esempio, si immette il testo di intestazione seguente: **Periodo @FiscalPeriod-@FiscalYear da @StartDate a @EndDate**. L'intestazione del report generata è simile al testo seguente: **Periodo 1-02 da 01/01/02 a 01/31/02**. **Nota:** Il formato di alcune parti del testo, ad esempio la data in formato esteso, dipende dalle impostazioni internazionali del server di Finance and Operations. Per modificare queste impostazioni, fare clic sul pulsante **Start**, fare clic su **Pannello di controllo**, quindi su **Paese e lingua**. Nella seguente tabella sono elencate le opzioni di testo automatico disponibili per le intestazioni di colonna.

| Opzione e codice testo automatico                | descrizione                                                                                                                                                                                                                                                                                      |
|-----------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Nome del mese (@CalMonthLong)              | Stampa il nome del mese corrente nell'intestazione di colonna. Se si decide di arrotondare gli importi nel report a migliaia, milioni o miliardi, o se si imposta la larghezza di colonna nel report a meno di nove caratteri, il nome del mese è abbreviato i primi tre caratteri. |
| Nome mese abbreviato (@CalMonthShort) | Stampa il nome abbreviato del mese per il periodo fiscale selezionato.                                                                                                                                                                                                                          |
| Numero periodo (@FiscalPeriod)           | Stampae il formato numerico del periodo fiscale che viene identificato per la colonna. Se la colonna copre più periodi, l'ultimo periodo dell'intervallo viene stampato.                                                                                                                                   |
| Descrizione periodo (@FiscalPeriodName)  | Stampa la descrizione del periodo fiscale identificato nei dati finanziari.                                                                                                                                                                                                                    |
| Anno fiscale (@FiscalYear)               | Stampa anno fiscale per la colonna in formato numerico.                                                                                                                                                                                                                                            |
| Anno di calendario (@CalYear)                | Stampa anno di calendario per la colonna in formato numerico.                                                                                                                                                                                                                                          |
| Data di inizio (@StartDate)                 | Stampa la data di inizio per la colonna.                                                                                                                                                                                                                                                             |
| Data di fine (@EndDate)                     | Stampa la data di fine per la colonna.                                                                                                                                                                                                                                                               |
| Nome dell'unità dalla struttura (@UnitName)         | Se si limita una colonna a un'unità specifica dell'albero gerarchico, stampa il nome dell'unità nell'intestazione di colonna.                                                                                                                                                                                     |
| Descrizione unità (@UnitDesc)            | Se si limita una colonna a un'unità specifica dell'albero gerarchico, stampa la descrizione dell'unità nell'intestazione di colonna.                                                                                                                                                                              |
| Codice libro (@BookCode)                   | Stampa il codice libro specificato nella colonna.                                                                                                                                                                                                                                             |
| Riga vuota (@Blank)                     | Inserisce una riga vuota nell'intestazione di colonna.                                                                                                                                                                                                                                                       |

### <a name="create-a-conditional-spanning-header"></a>Creare un'intestazione con spanning condizionale

Le intestazioni con spanning condizionale possono comprendere più colonne basate sui dati specifici di periodo. Ad esempio, se si dispone di un report di budget per l'anno fiscale e si desidera visualizzare gli effettivi budget dei mesi passati insieme ai budget previsti dei mesi futuri, è possibile utilizzare un'intestazione con spanning condizionale per aggiornare automaticamente l'intestazione del report. Quando si creare un'intestazione estesa condizionale, è necessario tenere presente gli aspetti indicati di seguito.

-   Qualsiasi condizione di interruzione (campo **Estendi a**) che trova corrispondenza prima di una condizione di avvio (campo **Estendi da**) viene ignorata. Ad esempio, la colonna B ha la condizione di estensione definita come BASE+1 a BASE, BASE è in colonna C e BASE+1 in colonna D. In questo caso, la condizione di interruzione in colonna C viene ignorata e la stampa dell'intestazione inizia alla colonna D.
-   Se si specificano le intestazioni di colonna che si sovrappongono, si sovrappongono quando vengono stampate nel report. Il report viene generato, ma il seguente avviso viene visualizzato nel campo **Stato coda report**: "Le intestazioni di colonna che usano Base si intersecano con altre intestazioni di colonna e possono causare la sovrapposizione del testo". Ad esempio, la definizione di intestazione nella colonna B è B a BASE+1 e la definizione dell'intestazione della colonna D è BASE+1 a F. In questo caso, le intestazioni vengono stampate una sopra l'altra diventando così illeggibili. Ogni volta che BASE viene usato in una definizione **Estendi da/Estendi a**, accertarsi di visualizzare il report generato, per verificare se le intestazioni si sovrappongano.
-   Se si specifica BASE nella definizione di estensione in una colonna Nessuna stampa (**NP**), viene ignorato, indipendentemente da quanto definito nella definizione di colonna. Essenzialmente, questo scenario è lo stesso di non creare una definizione dell'intestazione di colonna.
-   Per le colonne con stampa condizionale (**P&lt;B**, **P&gt;=B**), le intestazioni con spanning condizionale si comportano analogamente a qualsiasi normale definizione di intestazione di colonna. Ad esempio, se la condizione è falsa, qualsiasi corrispondenza successiva di colonna per la condizione di estensione avvia la stampa dell'intestazione.

#### <a name="create-a-conditional-spanning-header"></a>Creare un'intestazione con spanning condizionale

1.  In Progettazione report, aprire la definizione di colonna da modificare.
2.  Fare doppio clic su una cella di intestazione.
3.  Nella finestra di dialogo **Intestazione colonna**, digitare il testo dell'intestazione di colonna. In alternativa, fare clic su **Inserisci testo automatico** e selezionare un'opzione.
4.   Nel campo **Opzioni di formattazione**, selezionare uno stile di formattazione dell'intestazione.
5.  Specificare un periodo in relazione al periodo base specificato quando il report viene generato. Nei campi **Estendi da** ed **Estendi a**, immettere uno dei seguenti valori: **BASE**, **BASE-X** o **BASE+X**, in cui la X è il numero di periodi dal periodo base. Ad esempio, se si immette **BASE** nel campo **Estendi da**, il testo dell'intestazione di colonna con spanning condizionale inizia nell'intestazione di colonna in cui il valore **Periodo base** della definizione di report è uguale al valore **Periodo** della definizione di colonna. Termina nella colonna indicata nel campo **Estendi a**. Pertanto, se l'estensione è BASE a M e il valore **Periodo base** della definizione di report è **4**, l'intestazione inizia nella colonna in cui il periodo è impostato su **4** e termina alla colonna M. Le intestazioni si interrompono e iniziano solo alle colonne di stampa.
6.  In **Giustificazione**, selezionare se il testo dell'intestazione di colonna deve essere allineato a sinistra, al centro o a destra.
7.  Scegliere **OK**.

#### <a name="example-of-a-conditional-spanning-header"></a>Esempio di un'intestazione con spanning condizionale

Phyllis sta creando un report per una previsione dinamica di sei mesi. Desidera che la parola "Effettiva" sia stampata sulle colonne contenenti gli effettivi dati e la parola "Budget" sia stampata sulle colonne contenenti le previsioni di budget. Ogni mese che il report viene eseguito, è presente una colonna effettiva in più e una colonna budget in meno. Sebbene Phyllis possa modificare manualmente la definizione di colonna ogni volta che il report viene generato per rettificare le intestazioni, per risparmiare tempo e lo sforzo, decide di creare intestazioni con spanning condizionale che creeranno automaticamente le intestazioni sulle colonne appropriate ogni volta che il report viene eseguito. Phyllis apre Progettazione report, fa clic su **Definizione colonna** nel pannello di navigazione e apre la definizione di colonna del report. Immette le seguenti informazioni. Il periodo di base della definizione di report è 4.

|                     | A    | B             | C             | D             | E             | V             | G             | H             | I             | J             | K             | L             | L             |
|---------------------|------|---------------|---------------|---------------|---------------|---------------|---------------|---------------|---------------|---------------|---------------|---------------|---------------|
| Intestazione 1            |      | Effettiva        | Budget        |               |               |               |               |               |               |               |               |               |               |
| Intestazione 2            |      | @CalMonthLong | @CalMonthLong | @CalMonthLong | @CalMonthLong | @CalMonthLong | @CalMonthLong | @CalMonthLong | @CalMonthLong | @CalMonthLong | @CalMonthLong | @CalMonthLong | @CalMonthLong |
| Intestazione 3            |      |               |               |               |               |               |               |               |               |               |               |               |               |
| Tipo di colonna         | DESC | FD            | FD            | FD            | FD            | FD            | FD            | FD            | FD            | FD            | FD            | FD            | FD            |
| Codice libro/Attributo |      | EFFETTIVO        | BUDGET2012    | EFFETTIVO        | BUDGET2012    | EFFETTIVO        | BUDGET2012    | EFFETTIVO        | BUDGET2012    | EFFETTIVO        | BUDGET2012    | EFFETTIVO        | BUDGET2012    |
| Anno fiscale         |      | BASE          | BASE          | BASE          | BASE          | BASE          | BASE          | BASE          | BASE          | BASE          | BASE          | BASE          | BASE          |
| Periodo              |      | 1             | 1             | 2             | 2             | 3             | 3             | 4             | 4             | 5             | 5             | 6             | 6             |
| Periodi coperti     |      | PERIODIC      | PERIODIC      | PERIODIC      | PERIODIC      | PERIODIC      | PERIODIC      | PERIODIC      | PERIODIC      | PERIODIC      | PERIODIC      | PERIODIC      | PERIODIC      |
| Larghezza colonna        | 30   | 10            | 10            | 10            | 10            | 10            | 10            | 10            | 10            | 10            | 10            | 10            | 10            |
| Controllo stampa       |      | P&lt;=B       | P&gt;B        | P&lt;=B       | P&gt;B        | P&lt;=B       | P&gt;B        | P&lt;=B       | P&gt;B        | P&lt;=B       | P&gt;B        | P&lt;=B       | P&gt;B        |

Phyllis fa doppio clic su una cella di intestazione di colonna per aprire la finestra di dialogo **Intestazione colonna**, in cui immette le seguenti informazioni.

| Campo              | Valore                 |
|--------------------|-----------------------|
| Testo intestazione colonna | Effettiva                |
| Inserisci testo automatico    | Non viene effettuata alcuna selezione. |
| Opzioni di formattazione     | Casella                   |
| Motivazione      | Non viene effettuata alcuna selezione. |
| Estendi da        | B                     |
| Estendi a          | BASE                  |
| Intestazione Budget      | BASE+1 a colonna finale  |

Dopo aver completato di immettere informazioni, Phyllis fa clic su **OK**. Quindi fa doppio clic sulla cella di intestazione della colonna C per aprire la finestra di dialogo **Intestazione colonna**, in cui immette le seguenti informazioni.

| Campo              | Valore                 |
|--------------------|-----------------------|
| Testo intestazione colonna | Budget                |
| Inserisci testo automatico    | Non viene effettuata alcuna selezione. |
| Opzioni di formattazione     | Casella                   |
| Motivazione      | Non viene effettuata alcuna selezione. |
| Estendi da        | C                     |
| Estendi a          | BASE+2                |

Ora, ogni volta che questo report viene generato, la parola "Effettiva" verrà stampata sulle colonne contenenti gli effettivi dati e la parola "Budget" verrà stampata sulle colonne contenenti le previsioni di budget. Inoltre, il numero di colonne verrà rettificato ogni mese.

## <a name="apply-column-justification"></a>Applicare la giustificazione nelle colonne
La cella **Giustificazione** viene utilizzata per applicare la formattazione di giustificazione a una colonna di descrizione di un report. Questa opzione influisce solo sulle descrizioni della colonna, non gli effettivi valori.

1.  In Progettazione report, aprire la definizione di colonna da modificare.
2.  Fare doppio clic sulla cella **Giustificazione**.
3.  Selezionare uno dei seguenti valori nell'elenco:
    -   **Nessuno** – Giustificazione non applicata.
    -   **Sinistra** - allinea le descrizioni di colonna a sinistra.
    -   **Centro** - allinea le descrizioni di colonna al centro.
    -   **Destra** - allinea le descrizioni di colonna a destra.

## <a name="add-special-formatting-options"></a>Aggiungere le opzioni di formattazione speciali
Nella definizione di colonna, le righe di dettaglio della colonna di formattazione applicano formattazione speciale alle colonne selezionate. Sebbene alcune opzioni **Controllo stampa** e **Restrizioni di colonna** sono specifiche delle colonne **FD**, la maggior parte delle opzioni si applica a tutti i tipi di colonna. La formattazione specificata nella definizione di colonna sostituisce la formattazione specificata nella definizione di report. Tuttavia, la formattazione specificata nella definizione di riga sostituisce la formattazione specificata nella definizione di colonna. Le seguenti righe vengono considerate righe di formattazione:

-   Larghezza colonna
-   Spazi aggiuntivi prima di colonna
-   Sostituzione formato/valuta
-   Controllo stampa

### <a name="changing-the-column-width"></a>Modificare la larghezza di colonna

La cella **Larghezza colonna** specifica il numero di caratteri da utilizzare per la larghezza della colonna del report stampato. Larghezza di colonna è importante per le colonne contenenti gli importi (colonne di tipo **CALC**, **WKS**, o **FD**), le descrizioni (colonne di tipo **DESC**), ovvero compilazione (colonne di tipo **FILL**). Per impostazione predefinita, l'opzione **Adattamento automatico** è selezionata, in modo che la larghezza di ogni colonna automaticamente verrà modificata per adattarsi ai contenuti.

#### <a name="specify-the-width-of-a-column-on-a-report"></a>Specificare la larghezza di una colonna del report

1.  In Progettazione report, aprire la definizione di colonna da modificare.
2.  Nella cella **Larghezza colonna**, immettere il numero di spazi per la larghezza di colonna. La larghezza massima di qualsiasi colonna è 255 caratteri (questo numero include i centesimi, le virgole e le parentesi). In alternativa, per consentire a Progettazione report di selezionare la larghezza appropriata per la colonna, in base al contenuto della cella, fare doppio clic sulla cella **Larghezza colonna**, quindi su **Adattamento automatico**.

### <a name="add-space-between-columns"></a>Aggiungere spazio tra colonne

La cella **Spazi aggiuntivi prima di colonna** specifica la larghezza di separatore tra una colonna e le colonne adiacenti nella definizione di colonna. L'impostazione **Spazi aggiuntivi prima di colonna** influisce su tutte le righe di dettaglio della colonna, ma non le righe dell'intestazione di colonna. Utilizzare questa opzione per separare i gruppi di colonne o aggiungere alcuni spazi prima della descrizione, in modo che la colonna di descrizione sia rientrata rispetto ai titoli allineati a sinistra nel report. Il numero predefinito di spazi tra ogni colonna è due. È possibile modificare questa impostazione nella scheda **Impostazioni** nella definizione di report.

#### <a name="specify-the-space-between-columns"></a>Specificare lo spazio tra colonne

1.  In Progettazione report, aprire la definizione di colonna da modificare.
2.  Nella cella **Spazi aggiuntivi prima di colonna** immettere il numero di spazi da inserire tra le colonne.

### <a name="specify-a-currency"></a>Specificare la valuta

La cella **Sostituzione formato/valuta** specifica la formattazione dei decimali, la valuta e gli importi percentuali nella colonna. Questa formattazione sostituisce la formattazione specificata nella definizione di report o nelle impostazioni predefinite di sistema.

#### <a name="assign-a-format-currency-override-to-a-report-column"></a>Assegnare una sostituzione di formato o valuta a una colonna del report

1.  In Progettazione report aprire la definizione di colonna da modificare.
2.  Fare doppio clic su una cella **Sostituzione formato/valuta** di una colonna contenente importi.
3.  Nella finestra di dialogo **Sostituzione formato** selezionare le opzioni di formattazione.

### <a name="add-a-print-control-code"></a>Aggiungere un codice di controllo di stampa

La cella **Controllo stampa** può contenere i codici che regolano la visualizzazione o le caratteristiche di stampa di una colonna. Sono disponibili due tipi di codici di controllo di stampa: codici di controllo di stampa normali e codici di controllo di stampa condizionali.

#### <a name="regular-print-control-codes"></a>Codici di controllo di stampa normali

| Codice di controllo di stampa | Traduzione                                     | Descrizione                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
|--------------------|-------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| NP                 | Non stampare                                     | Esclude gli importi nella colonna dal report stampato e dai calcoli. Per includere una colonna contrassegnata da non stampare nel calcolo, fare riferimento alla colonna direttamente nella formula di calcolo. Ad esempio, la colonna C da non stampare è inclusa nel calcolo seguente: **B+C+D**. Tuttavia, la colonna C da non stampare non è inclusa nel calcolo seguente: **B:D**.                                                                                                                                          |
| XCR                | Cambia il segno se il saldo tipico della riga è in Avere | Crea un report di budget o comparativo in cui qualsiasi scostamento sfavorevole (ad esempio minori ricavi o un eccesso di spesa) è sempre negativo. Applicare il codice a un colonna **CALC** per invertire il segno dell'importo della colonna se il saldo tipico di una riga specificata è un credito (identificato da una **C** nella colonna **Saldo normale** della definizione di riga). **Nota:** Per le righe **TOT** e **CAL** che in genere portano un saldo in avere, assicurarsi di immettere una **C** nella colonna **Saldo normale** della definizione di riga. |
| X0                 | Consente di eliminare la colonna se contiene tutti zeri o spazi vuoti          | Esclude una colonna **FD** dal report se tutte le celle nella colonna sono vuote o contengono zeri.                                                                                                                                                                                                                                                                                                                                                                                                                             |
| SR                 | Elimina arrotondamento                               | Impedisce l'arrotondamento degli importi nella colonna.                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| XR                 | Consente di eliminare il rollup                                 | Consente di eliminare il rollup. Se il report utilizza un albero gerarchico, non viene eseguito il rollup degli importi nella colonna nei nodi padre successivi.                                                                                                                                                                                                                                                                                                                                                                                                   |
| RP                 | Ripete la colonna su ciascuna pagina                      | Ripete una colonna specificata in ciascuna pagina del report. Ad esempio, è possibile utilizzare il codice di controllo di stampa **RP** per includere una colonna di tipo **ROW** che effettua il pull nei codici di riga in ciascuna pagina.                                                                                                                                                                                                                                                                                                                                           |
| WT                 |  Testo a capo                                      |  Se il testo in una colonna è troppo lungo per lo spazio disponibile, manda il testo a capo per tenere tutto il testo nella colonna.                                                                                                                                                                                                                                                                                                                                                                                                                            |

#### <a name="conditional-print-control-codes"></a>Codici di controllo di stampa condizionali

| Codice di controllo di stampa condizionale | descrizione                                                                             |
|--------------------------------|-----------------------------------------------------------------------------------------|
| (nessuno)                         | Cancella la selezione di stampa condizionale.                                                  |
| P&lt;B                         | Visualizza una colonna specificata solo se il periodo è inferiore al periodo base.             |
| P&gt;B                         | Visualizza una colonna specificata solo se il periodo è superiore al periodo base.             |
| P=B                            | Visualizza una colonna specificata solo se il periodo è uguale al periodo base.              |
| P&lt;=B                        | Visualizza una colonna specificata solo se il periodo è minore o uguale al periodo base. |
| P&gt;=B                        | Visualizza una colonna specificata solo se il periodo è maggiore o uguale al periodo base. |

#### <a name="add-print-control-codes-to-a-report-column"></a>Aggiungere i codici di controllo di stampa in una colonna del report

1.  In Progettazione report aprire la definizione di colonna da modificare.
2.  Fare doppio clic sulla cella **Controllo stampa**.
3.  Nella finestra di dialogo **Controllo stampa** selezionare un codice nell'elenco **Seleziona opzioni controllo di stampa**. Per selezionare più di un codice, tenere premuto il tasto Ctrl e selezionare i codici.
4.  Selezionare un'opzione nel campo **Opzioni stampa condizionale**. Per impostazione predefinita, è selezionato **(nessuno)**. È possibile selezionare un solo codice di stampa condizionale alla volta.
5.  Fare clic su **OK**.

> [!TIP]
> È inoltre possibile immettere i codici di stampa direttamente nella cella **Controllo stampa**. Separare più codici di controllo di stampa con una virgola.


## <a name="column-types"></a>Tipi di colonna
Il tipo di informazioni che ogni colonna di un report include è specificato dal valore nella riga **Tipo di colonna** nella definizione di colonna. Ogni definizione di colonna deve includere almeno una colonna di descrizione (**DESC**) e una colonna di importo (**FD**, **WKS** o **CALC**). **Nota:** I codici del tipo di colonna non sono applicabili a tutti i sistemi contabili. Se si seleziona un tipo che non è valido per il sistema contabile, la colonna è vuota nel report.

### <a name="specify-a-column-type"></a>Specificare un tipo di colonna

1.  In Progettazione report, aprire la definizione di colonna da modificare.
2.  Nella colonna appropriata, fare doppio clic su una cella nella riga **Tipo di colonna**.
3.  Nell'elenco selezionare un tipo di colonna. Nella tabella seguente vengono descritti i diversi tipi di colonna.
    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Codice tipo di colonna</th>
    <th>Descrizione</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>FD</td>
    <td>Visualizza dati finanziari o dati di un foglio di lavoro di Excel quando si utilizza una colonna <strong>Collegamento a Dimensioni finanziarie</strong> o una colonna <strong>Collegamento a Foglio di lavoro</strong> nella definizione di riga. Quando si seleziona il tipo di colonna <strong>FD</strong>, le impostazioni predefinite vengono specificate automaticamente nelle righe seguenti: <ul>
    <li><strong>Codice registro/categoria di attributi:</strong> ACTUAL</li>
    <li><strong>Codice registro/categoria di attributi:</strong> ACTUAL</li>
    <li><strong>Anno fiscale:</strong> BASE</li>
    <li><strong>Periodo:</strong> BASE</li>
    <li><strong>Periodi coperti:</strong> PERIODIC</li>
    <li><strong>Larghezza colonna:</strong> 14</li>
    </ul>
Le impostazioni predefinite possono essere modificate.</td>
    </tr>
    <tr class="even">
    <td>CALC</td>
    <td>Visualizza il risultato di un calcolo semplice o complesso specificato nella cella <strong>Formula</strong>. Per ulteriori informazioni, vedere <a href="advanced-formatting-options-financial-reporting.md">Opzioni di formattazione avanzate nei report finanziari</a>.</td>
    </tr>
    <tr class="odd">
    <td>DESC</td>
    <td>Visualizza la descrizione di riga dalla definizione di riga. Sebbene la colonna di descrizione sia spesso la prima colonna del report, è possibile metterla in qualsiasi posizione.</td>
    </tr>
    <tr class="even">
    <td>ROW</td>
    <td>Visualizza i singoli codici di riga per le righe finanziarie della colonna <strong>Codice di riga</strong> nella definizione di riga. Per ulteriori informazioni, vedere <a href="row-definitions-financial-reporting.md">Definizioni di riga nei report finanziari</a>.</td>
    </tr>
    <tr class="odd">
    <td>ACCT (codici conto)</td>
    <td>Visualizza i valori segmento o i valori di dimensione di dati finanziari da applicare a ogni riga. Per i report dei dettagli delle transazioni e dei conti, viene stampato il conto completo (ad esempio, <strong>110140-070-0101</strong>). Se nella colonna <strong>Collegamento a Dimensioni finanziarie</strong> sono stati specificati intervalli in una definizione di riga associata, l'intervallo viene racchiuso in parentesi quadre e viene considerato come un valore singolo (ad esempio, <strong>[110140:110700]-070-[0101:0200]</strong>). Per i report finanziari e quelli generali che possono rappresentare una combinazione di più conti, viene stampato il collegamento ai dati finanziari presente nella definizione di riga (ad esempio, <strong>1100:1200</strong>).</td>
    </tr>
    <tr class="even">
    <td>FILL</td>
    <td>Riempie la cella con un carattere racchiuso in virgolette singole. Se non si immette un carattere, la colonna è vuota. Ad esempio, per riempire una colonna con puntini di sospensione (...), immettere <strong>FILL</strong> <strong>'.'</strong>.</td>
    </tr>
    <tr class="odd">
    <td>PAGE</td>
    <td>Inserisce un'interruzione di pagina verticale nel report. Le colonne che si trovano a destra della colonna <strong>PAGE</strong> verranno visualizzate in una pagina distinta.</td>
    </tr>
    <tr class="even">
    <td>WKS</td>
    <td>Visualizza i dati di cui è effettuato il pull da un foglio di lavoro di Excel. Quando si seleziona il tipo di colonna <strong>WKS</strong>, le impostazioni predefinite vengono specificate automaticamente nelle righe seguenti: <ul>
    <li><strong>Anno fiscale:</strong> PERIODIC</li>
    <li><strong>Periodo:</strong> BASE</li>
    </ul>
Le impostazioni predefinite possono essere modificate.</td>
    </tr>
    <tr class="odd">
    <td>ATTR</td>
    <td>Se il sistema contabile supporta gli attributi, viene visualizzato un attributo di transazione o del conto nella colonna. Un attributo, che deve essere applicato a un solo conto completo, estrae le informazioni del conto o della transazione sottostanti dai dati finanziari. Gli attributi a livello di conto consentono di visualizzare dati del conto, mentre quelli a livello di transazione consentono di visualizzare i dati relativi al momento in cui la transazione è stata registrata. Quando si seleziona <strong>ATTR</strong> come tipo di colonna, specificare la categoria di attributi nella riga di dettaglio <strong>Codice registro/categoria di attributi</strong> della definizione di colonna.</td>
    </tr>
    </tbody>
    </table>

### <a name="financial-dimensions-column"></a>Colonna Dimensioni finanziarie

Le seguenti definizioni di riga di **Definizione colonna** si applicano alle colonne con un tipo di colonna **FD** (importi dalle dimensioni finanziarie).

#### <a name="book-codeattribute-category-cell"></a>Cella Codice libro/Categoria attributi

La cella **Codice libro/Categoria attributi** identifica il codice libro dei dati nella colonna **FD**. Una definizione di colonna può includere più colonne effettive, budget e statistiche. Una definizione di colonna può inoltre visualizzare periodi diversi, ad esempio corrente o fino a oggi, e importi diversi. L'elenco dei codici libro riflette le opzioni effettivo, budget e statistiche (non finanziarie) che sono state stabilite nei dati finanziari.

#### <a name="fiscal-year-cell"></a>Cella Anno fiscale

La cella **Anno fiscale** identifica l'anno fiscale che la colonna deve includere. L'anno può essere in relazione all'anno base specificato quando il report viene generato. Sono disponibili le seguenti opzioni.

| Opzione  | Descrizione                                                                                                                  |
|---------|------------------------------------------------------------------------------------------------------------------------------|
| BASE    | Utilizza l'anno di base specificato al momento del report.                                                                          |
| BASE+\# | Utilizza l'anno che viene \# anni dopo l'anno di base. Ad esempio, per utilizzare il terzo anno dopo l'anno di base, immettere **BASE+3**. |
| BASE-\# | Utilizza l'anno che viene \# anni prima dell'anno di base. Ad esempio, per utilizzare l'anno precedente, immettere **BASE-1**.                 |
| \#      | Immettere l'anno fiscale effettivo.                                                                                                |

#### <a name="period-cell"></a>Cella Periodo

La cella **Periodo** identifica i periodi fiscali che la colonna deve includere. Il periodo può essere in relazione al periodo base specificato quando il report viene generato. Sono disponibili le seguenti opzioni.

| Opzione          | descrizione                                                                                                                                                                                                                          |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| BASE            | Utilizza il periodo base.                                                                                                                                                                                                                 |
| BASE+\#         | Utilizza il periodo che viene \# periodi dopo il periodo di base. Ad esempio, per utilizzare il terzo periodo dopo il periodo di base, immettere **BASE+3**.                                                                                               |
| BASE-\#         | Utilizza il periodo che viene \# periodi prima del periodo di base. Ad esempio, per utilizzare il periodo precedente, immettere **BASE-1**.                                                                                                                 |
| BASE-\#:BASE    | Utilizza più periodi, da diversi periodi prima del periodo base fino al periodo base. Ad esempio, per utilizzare i tre periodi precedenti e il periodo base, immettere **BASE-3:BASE**.                                                |
| BASE:BASE+\#    | Utilizza più periodi, dal periodo base fino a diiversi periodi dopo il periodo base. Ad esempio, per utilizzare il periodo base e i due periodi successivi, immettere **BASE:BASE+2**.                                                  |
| BASE-\#:BASE+\# | Utilizza più periodi, da diversi periodi prima del periodo base fino a diversi periodi dopo il periodo base. Ad esempio, per utilizzare i tre periodi precedenti, il periodo base e i due periodi successivi, immettere **BASE-3:BASE+2**. |
| 1:BASE          | Utilizza più periodi, dal primo periodo fino al periodo base.                                                                                                                                                                 |
| \#              | Utilizza sempre un numero specifico di periodi. Non è consigliabile scegliere questa opzione, poiché riduce la flessibilità della definizione di colonna.                                                                                       |
| \#                                      : \#           | Utilizza sempre uno specifico intervallo di periodi. Non è consigliabile scegliere questa opzione, poiché riduce la flessibilità della definizione di colonna.                                                                                    |

È possibile andare oltre i limiti dell'anno fiscale in qualsiasi specifica di periodi ed è possibile combinare gli anni in un intervallo di periodi. Ad esempio, si specificano i periodi come **BASE-5** (per rappresentare gli ultimi sei periodi) e si esegue un report con un periodo di base di 2. In questo caso, nel report vengono visualizzati i dati dei primi due periodi dell'anno fiscale specificato e degli ultimi quattro periodi dell'anno fiscale precedente.

### <a name="specify-the-periods-for-an-fd-column"></a>Specificare i periodi in una colonna di tipo DF

1.  In Progettazione report aprire la definizione di colonna da modificare.
2.  Nella colonna **FD** fare doppio clic sulla cella nella riga **Periodo** e selezionare un'opzione nell'elenco.
3.  Nella barra delle formule sopra il pannello di navigazione, o nella cella **Periodo**, completare la formula. Sostituire qualsiasi cancelletto (\#) con il valore appropriato.

#### <a name="periods-covered-cell"></a>Cella Periodi coperti

La cella **Periodi coperti** identifica l'importo che la colonna deve visualizzare. Questo importo è relativo al valore nelle celle **Anno fiscale** e **Periodo** per la colonna. Sono disponibili le seguenti opzioni.

| Opzione      | Descrizione                                                                 |
|-------------|-----------------------------------------------------------------------------|
| PERIODIC    | Consente di visualizzare la somma di attività per il periodo o l'intervallo dei periodi corrente. |
| PERIODIC/BB | Consente di visualizzare il saldo iniziale per il periodo o l'intervallo dei periodi corrente.   |
| YTD         | Consente di visualizzare la somma dell'attività dell'anno fino a oggi.                               |
| YTD/BB      | Visualizza il saldo iniziale dell'anno.                                 |

### <a name="specify-the-periods-that-are-covered-for-an-fd-column"></a>Specificare i periodi coperti per una colonna FD

1.  In Progettazione report, aprire la definizione di colonna da modificare.
2.  Nella colonna **FD** fare doppio clic sulla cella nella riga **Periodi coperti** e selezionare un'opzione nell'elenco.

### <a name="attribute-filter-in-a-column-definition"></a>Filtro attributi in una definizione di colonna

Gli attributi sono valori di dati finanziari che definiscono ulteriormente un conto o una transazione. Gli attributi del conto sono **Cespite**, **Passività**, **Ricavi** e **Spesa**. Gli attributi di transazione sono **Descrizione transazione** e **Data applicazione transazione**. Il supporto di attributi può differire tra i sistemi Microsoft Dynamics ERP. La cella **Filtro attributi** limita i dati nelle colonne **FD** a valori specifici o a intervalli per le categorie di attributo. Sebbene questa funzionalità possa essere utilizzata insieme a una colonna **ATTR**, la colonna **ATTR** non è richiesta. Nella colonna **FD** esiste un limite nei conti o transazioni che il report includerà dal filtro attributi. **Nota:** Per verificare quali attributi sono supportati dal sistema ERP in uso, vedere la guida di integrazione del sistema.

#### <a name="apply-an-attribute-filter-for-an-fd-column-on-a-report"></a>Applicare un filtroattributi per una colonna FD di un report

1.  In Progettazione report, aprire la definizione di colonna da modificare.
2.  Fare doppio clic sulla cella **Filtro attributi** per una colonna di tipo **DF**.
3.  Nella finestra di dialogo **Filtro attributi** fare doppio clic su una cella nella colonna **Attributo**, quindi selezionare il tipo di filtro.
4.  Per limitare ulteriormente i risultati, immettere un intervallo nelle colonne **Da** e **A**. Il campo **Da** deve contenere un valore.
5.  Scegliere **OK**.

#### <a name="example-of-an-attribute-filter"></a>Esempio di filtro attributi

Il seguente esempio mostra la parte di una descrizione della colonna con un attributo di conto nella riga **Codice libro/Categoria attributi**. Il filtro attributi per la colonna specifica l'intervallo di valori da includere nel report.

|                              | A    | B                    |
|------------------------------|------|----------------------|
| Tipo di colonna                  | DESC | DF                   |
| Codice registro/categoria di attributi |      | ACTUAL               |
| Anno fiscale                  |      | BASE                 |
| Periodo                       |      | 1:BASE               |
| Periodi coperti              |      | PERIODIC             |
| ...                          |      |                      |
| Larghezza colonna                 | 30   |                      |
| ...                          |      |                      |
| Filtro attributi             |      |  Riferimento=\[01:10\] |

### <a name="dimension-filter-in-a-column-definition"></a>Filtro dimensioni in una definizione di colonna

Un filtro dimensioni viene utilizzato per limitare la colonna **FD** a valori di dimensione specifici. Il filtro può includere una singola dimensione, un intervallo o un gruppo di dimensioni Il filtro può includere anche set di valori di dimensione. Poiché i valori di dimensione possono variare, un sistema basato sulle dimensioni ..\financial-dimensions\ non deve corrispondere a una lunghezza esatta. Il filtro viene applicato, indipendentemente dal fatto che il report include un albero gerarchico. È possibile utilizzare un carattere jolly (\* o?) in qualsiasi posizione. Se si specifica più conti, inserire una virgola tra i conti, come nell'esempio seguente: +conto=\[1200\], +conto=\[1100\], reparto=\[01?\] Per ricevere tutti i reparti per un conto specifico, è possibile escludere la dimensione Reparto dal filtro dimensioni. Ad esempio, entrambi i seguenti filtri dimensioni vengono gestiti nello stesso modo:

-   +Conto=\[1100\],Reparto
-   +Conto=\[1100\]

È inoltre possibile utilizzare qualsiasi combinazione di caratteri alfanumerici per la corrispondenza esatta ed è possibile definire le dimensioni parziali. Ad esempio, **Ubicazione = \[10\*\]** include tutti i valori di dimensione ubicazione che iniziano con 10.

#### <a name="apply-a-dimension-filter-for-a-column-on-a-report"></a>Applicare un filtro dimensioni per una colonna del report

1.  In Progettazione report, aprire la definizione di colonna da modificare.
2.  Fare doppio clic sulla cella **Filtro dimensioni** per una colonna **FD**.
3.  Nella finestra di dialogo **Dimensioni**, immettere i filtri da applicare.
4.  Scegliere **OK**.

### <a name="format-a-multiple-currency-report-in-a-column-definition"></a>Formattare un report con più valute in una definizione di colonna

Un report con più valute può visualizzare gli importi nella valuta naturale (locale), nella valuta funzionale (predefinita) o nella valuta di dichiarazione. La valuta funzionale di una società è definita nel sistema Microsoft Dynamics ERP. Non confondere questa impostazione ERP con le opzioni locali del sistema operativo, in cui è possibile configurare i simboli della valuta predefinita utilizzati nei report. Le seguenti celle correlate alla valuta sono disponibili nella definizione di colonna:

-   **Visualizzazione di valuta** - Consente di specificare il tipo di valuta, ovvero naturale, funzionale o di dichiarazione, in cui sono visualizzate le transazioni. Questa funzionalità viene talvolta definita conversione di valuta. La conversione valuta è la capacità di riportare gli importi di contabilità generale in una valuta che non sia la valuta funzionale della società o la valuta in cui la transazione è stata immessa.
-   **Filtro valuta** Consente di specificare un filtro valuta. Solo le transazioni immesse nella valuta selezionata vengono visualizzate nel report.

> [!NOTE]
> Per creare report che utilizzano più valute, è necessario selezionare la casella di controllo **Includi tutte le valute di dichiarazione** nella scheda **Report** della definizione di report. Per determinare la valuta funzionale di una società, effettuare le operazioni indicate di seguito.

1.  In Progettazione report, menu **Società**, fare clic su **Società**.
2.  Nella finestra di dialogo **Società**, selezionare una società e quindi fare clic su **Visualizza**.
3.  Nella finestra di dialogo **Visualizza società**, in **Opzioni internazionali**, è possibile visualizzare la valuta definita per la società selezionata.

#### <a name="specify-the-currency-on-a-multiple-currency-report"></a>Specificare la valuta in un report con più valute

1.  In Progettazione report, aprire la definizione di colonna da modificare.
2.  Fare doppio clic sulla cella **Visualizzazione valuta** nella colonna **FD** appropriata e selezionare l'opzione per la visualizzazione di informazioni sulla valuta: **Valuta naturale/di origine**, **Valuta funzionale da informazioni società**, o la valuta di dichiarazione.
3.  Fare doppio clic sulla cella **Filtro valuta** nella colonna **FD** appropriata e selezionare il codice valuta appropriato nell'elenco. Solo le transazioni immesse in questa valuta vengono visualizzate nel report.

> [!NOTE]
> Le opzioni che vengono descritte in questo modulo possono differire, a seconda del sistema ERP. Per ulteriori informazioni, vedere la [Documentazione relativa al sistema Microsoft ERP](https://www.microsoft.com/en-us/download/details.aspx?id=5916).

### <a name="example-for-currency-display-and-currency-filter-cells"></a>Esempio delle celle Visualizzazione valuta e Filtro valuta

Phyllis ha eseguito le seguenti selezioni di valuta nella definizione di colonna:

-   **Filtro valuta:** Yen
-   **Visualizzazione valuta:** Funzionale (dollari USA)

A causa di filtro valuta da Phyllis selezionato, il report include solo le transazioni immesse in Yen giapponesi (JPY). A causa della visualizzazione valuta che ha selezionato, nel report vengono visualizzate le transazioni nella valuta funzionale, dollari USA (USD).

#### <a name="currency-filter-and-currency-display-combinations"></a>Combinazioni di Filtro valuta e Visualizzazione valuta

Nella seguente tabella vengono visualizzati i risultati del report che possono verificarsi per varie combinazioni delle opzioni nelle celle **Visualizzazione valuta** e **Filtro valuta** a causa delle selezioni che Phyllis ha effettuato. La valuta funzionale è USD.

| Cella Visualizzazione valuta                        | Cella Filtro valuta | Risultato report                                                                                                                                                                                    |
|----------------------------------------------|----------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Valuta naturale/di origine                 | **YEN**              | **Y 6.000** – Il risultato mostra solo solo le transazioni immesse in JPY.                                                                                                                        |
| Valuta funzionale da informazioni società | **YEN**              | **$ 60** – Il risultato mostra solo le transazioni immesse nel JPY e visualizza quelle transazioni in USD. **Nota:** Il tasso di conversione è circa 100 JPY per USD.                    |
| Valuta funzionale da informazioni società | Vuoto                | **$2.310\*\*** - Il risultato mostra tutti i dati nella valuta funzionale specificata nelle informazioni di società. **Nota:** Questo importo corrisponde alla somma di tutte le transazioni in valuta funzionale. |
| Valuta naturale/di origine                 | Vuoto                | **$ 2.250** – Il risultato mostra tutti gli importi nella valuta in cui la transazione è stata eseguita.                                                                                                 |

### <a name="calculation-column-in-a-column-definition"></a>Colonna di calcolo in una definizione di colonna

Una colonna di tipo **CALC** in una definizione di colonna supporta i calcoli complessi nella cella **Formula** e può includere gli operatori **+**, **-**, **\*** e **/** e anche le istruzioni **IF/THEN/ELSE**. Una colonna di calcolo può inoltre fare riferimento a una qualsiasi altra colonna, anche a colonne successive. Inoltre, una colonna di calcolo può includere l'anno e il periodo fiscale per supportare le intestazioni per la colonna. La formula del calcolo può essere composto da 1.024 caratteri al massimo. Per esprimere il risultato di calcolo come percentuale, utilizzare una sostituzione speciale di formato. **Nota:** I risultati delle formule di calcolo non includono i valori negli intervalli di colonne da non stampare. Ad esempio, **A:D** stampa **0** (zero), mentre **A+B+C** per i valori da non stampare calcola il valore.

#### <a name="operators-in-calculation-columns"></a>Operatori nelle colonne di calcolo

Per aggiungere, sottrarre, moltiplicare, o dividere le colonne, immettere le lettere di colonna in ordine del calcolo quindi utilizzare operatore appropriato per separare ogni lettera di colonna. Nella seguente tabella viene illustrato gli operatori da utilizzare in una colonna di calcolo.

| Operatore | Esempio di calcolo | descrizione                                                                                                                                                                                                                                    |
|----------|---------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| +        | A+C                 | Aggiunge l'importo di colonna A all'importo in colonna C.                                                                                                                                                                                          |
| :        | A:C A:C-D           | Somma un intervallo di colonne consecutive. Ad esempio, la formula **A:C** aggiunge le somme delle colonne da A a C e la formula **A:C-D** aggiunge le somme delle colonne da A a C e quindi sottrae l'importo in colonna D.                          |
| -        | A-C                 | Sottrae l'importo in colonna A dall'importo in colonna C. **Nota:** È inoltre possibile utilizzare il segno meno (-) per invertire i segni nella colonna. Ad esempio, utilizzare **-A+B** per aggiungere l'inverso dell'importo in colonna A all'importo in colonna B. |
| \*       | A\*C                | Moltiplica l'importo di colonna A per l'importo in colonna C.                                                                                                                                                                                     |
| /        | A/C                 | Divide l'importo di colonna A per l'importo in colonna C.                                                                                                                                                                                       |

#### <a name="use-a-calculation-formula-in-a-column-definition"></a>Usare una formula di calcolo in una definizione di colonna

1.  In Progettazione report, aprire la definizione di colonna da modificare.
2.  Nella colonna **CALC** appropriata, immettere una formula nella cella **Formula**.

#### <a name="complex-calculations"></a>Calcoli complessi

Un calcolo complesso può contenere qualsiasi combinazione di riferimenti a celle, di operatori, di valori e di livelli di parentesi nidificate. Ad esempio, per calcolare la media delle colonne A e B, utilizzare la formula di calcolo **((A+B)/2)**.

#### <a name="specify-report-cells-in-a-column-calculation"></a>Specificare le celle di report nel calcolo della colonna

È possibile riferirsi a una cella specifica del report immettendo una lettera di colonna e un codice di riga. Ad esempio, **B.100** si riferisce al codice di riga 100 in colonna B. È possibile dividere un'intera colonna per un importo di una cella di report specifica che si trova nella stessa colonna. Ad esempio, il calcolo **B/B.100** significa che l'importo in colonna B deve essere diviso per il valore nel codice di riga 100 in colonna B. Se il calcolo si riferisce a una colonna che dipende da un'altra colonna, la colonna dipendente viene risolta prima. Se si riferisce una colonna a un'altra colonna che fa riferimento alla prima colonna, causerete un errore di riferimento circolare. **Nota:** Il calcolo può essere errato se si modifica la priorità di calcolo per il report. È possibile stabilire la priorità di calcolo nella scheda **Impostazioni** della definizione di report.

#### <a name="multiply-or-divide-a-column-by-a-base-row"></a>Moltiplicare o dividere una colonna per una riga di base

È possibile creare una colonna che visualizza tutti i valori in una colonna specificata come percentuale di un numero base. Di conseguenza, è possibile visualizzare le relazioni tra le righe, ad esempio una percentuale di una riga di vendita o una percentuale di riga spese totali. Per moltiplicare o dividere ogni riga in una colonna specifica per una riga di base, immettere la colonna da utilizzare nel calcolo quindi immettere **\*BASEROW** o **/BASEROW**. Ad esempio, immettere **C\*BASEROW** o **C/BASEROW**. **Nota:** Quando si utilizza un calcolo con riga di base in una definizione di colonna, assicurarsi che ogni definizione di riga utilizzata con la definizione di colonna contenga almeno una riga di base per i calcoli.

#### <a name="divide-the-amount-in-a-column-by-the-number-of-periods"></a>Dividere l'importo in una colonna per il numero di periodi

È possibile dividere l'importo in una colonna per un numero di periodi specificato. Ad esempio, la formula **B/Periodi** divide il valore in colonna B per il numero di periodi in colonna B. Se il calcolo comprende più colonne, specificare il numero di periodi da utilizzare nel calcolo. Ad esempio, la formula **(B+C)/Periodi** aggiunge gli importi in colonna B e in colonna C quindi divide il risultato per il valore dei periodi.

<a name="see-also"></a>Vedere anche
--------

[Definizioni di riga nei report finanziari](row-definitions-financial-reporting.md)

[Opzioni di formattazione avanzate nei report finanziari](advanced-formatting-options-financial-reporting.md)




