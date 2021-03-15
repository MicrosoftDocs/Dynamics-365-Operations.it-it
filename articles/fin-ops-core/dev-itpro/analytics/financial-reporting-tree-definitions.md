---
title: Definizioni di albero gerarchico nei report finanziari
description: Questo articolo descrive le definizioni dell'albero gerarchico. Una definizione dell'albero gerarchico è un componente del report che definisce la struttura di un'organizzazione.
author: ShylaThompson
manager: AnnBe
ms.date: 10/07/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: kfend
ms.custom: 57592
ms.assetid: 747faa47-9a23-4277-bc11-8d0a1267c3a4
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 17f749863af3c37658935d5065cf053d0a165c1e
ms.sourcegitcommit: 5192cfaedfd861faea63d8954d7bcc500608a225
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2021
ms.locfileid: "5093903"
---
# <a name="reporting-tree-definitions-in-financial-reports"></a>Definizioni di albero gerarchico nei report finanziari

[!include [banner](../includes/banner.md)]

In questo articolo vengono fornite informazioni sulle definizioni di albero gerarchico. Una definizione di albero gerarchico è un componente di report, o blocco predefinito, che consente di definire la struttura e la gerarchia dell'organizzazione.

I report finanziari supportano il reporting flessibile in modo da facilitare le modifiche quando la struttura aziendale cambia. I report si basano su vari componenti o blocchi predefiniti. Uno di questi blocchi predefiniti è la definizione di albero gerarchico. Una definizione di albero gerarchico consente di definire la struttura e la gerarchia dell'organizzazione. Si tratta di una struttura gerarchica interdimensionale basata sulle relazioni dimensionali nei dati finanziari. Fornisce informazioni a livello di unità gerarchica e a livello di riepilogo per tutte le unità dell'albero. Le definizioni di albero gerarchico possono combinarsi con le definizioni di colonna e le definizioni di report per creare un gruppo di blocchi predefiniti che può essere utilizzato da più società. Un'unità gerarchica viene utilizzata per ogni riquadro in un organigramma. che può essere un singolo reparto relativo ai dati finanziari oppure un'unità di riepilogo di livello superiore che combina le informazioni di altre unità gerarchiche. Per una definizione di report che include un albero gerarchico, viene generato un report per ogni unità gerarchica e per il livello di riepilogo. Tutti questi report utilizzano le definizioni di riga e di colonna specificate nella definizione di report, a meno che la definizione di report specifichi di utilizzare l'albero gerarchico dalla definizione di riga. La definizioni di riga e colonna sono componenti importanti nella progettazione e la funzionalità dei report finanziari. Gli alberi gerarchici aumentano la potenza dei componenti e supportano il reporting flessibile quando la struttura aziendale cambia. I report finanziari che non sono basati su un albero gerarchico usano solo alcune funzionalità dei report finanziari. È possibile utilizzare più definizioni di albero gerarchico insieme nelle stesse definizioni di riga e di colonna per visualizzare i dati dell'organizzazione in vari modi.

## <a name="reporting-tree-best-practices"></a>Procedure consigliate per l'albero gerarchico
Prima di creare un albero gerarchico, considerare le seguenti procedure consigliate:

- Prima determinare quali dimensioni di reporting sono richieste dalla persona giuridica o la società.
- Considerare come è stata impostata la struttura e quindi tracciare un organigramma della società. Con l'organigramma sarà più facile immaginare come raggruppare le unità gerarchiche in uno o più alberi gerarchici.
- Iniziare con il livello più basso disponibile di dettagli, ad esempio reparti e progetti definiti nei dati finanziari. Aggiungere al livello di dettaglio tutti i riquadri necessari per mostrare divisioni o aree di livello superiore. Ogni riquadro rappresenta un'unità gerarchica potenziale in qualsiasi albero gerarchico creato.
- È inoltre necessario considerare la migliore modalità di generare gli alberi. È possibile utilizzare un processo di sviluppo automatizzato per creare un albero gerarchico, oppure crearlo manualmente. È importante comprendere entrambi i metodi prima di progettare gli alberi.
- È possibile utilizzare le unità gerarchiche definite nel sistema di dati finanziari per aggiungere unità gerarchiche alla definizione dell'albero gerarchico.

## <a name="create-multiple-reporting-trees"></a> Creare più alberi gerarchici
È possibile creare un numero illimitato di alberi gerarchici per visualizzare i dati dell'organizzazione in vari modi. Ogni albero gerarchico può includere qualsiasi combinazione di reparti e unità di riepilogo. Una definizione di report può contenere un collegamento a un sola albero gerarchico alla volta. Riorganizzando la struttura di alberi gerarchici, è possibile creare alberi gerarchici diversi. È quindi possibile utilizzare le stesse definizioni di riga e colonna per ogni albero gerarchico. In questo modo, è possibile creare rapidamente diversi layout di report finanziari. Se si creano più alberi gerarchici, è possibile stampare una serie di rendiconti finanziari ogni mese che analizzano e presentano le operazioni della società in vari modi. Per ulteriori informazioni, vedere gli esempi delle strutture di unità gerarchiche alla fine di questo articolo.

## <a name="create-a-reporting-tree-definition"></a> Creare una definizione di albero gerarchico
Una definizione di albero gerarchico contiene le colonne descritte nella seguente tabella.

| Colonna dell'albero gerarchico | Descrizione |
|-----------------------|-------------|
| Società               | Nome della società dell'unità gerarchica. Il valore **\@ANY**, in genere assegnato solo al livello di riepilogo, consente l'utilizzo dell'albero gerarchico per tutte le società. A tutti i rami figlio deve essere assegnata una società. |
| Nome unità             | Il codice che identifica l'unità gerarchica nell'albero gerarchico grafico. Assicurarsi di definire un sistema di codifica univoco che sia coerente e facile da comprendere per gli utenti. |
| Descrizione unità      | Il titolo dell'unità gerarchica viene visualizzato nell'intestazione o nel piè di pagina del report se si immette **UnitDesc** come codice nella scheda **Intestazioni e piè di pagina** della definizione di report. Il titolo viene visualizzato nella descrizione della riga del report se si immette **UnitDesc** nella cella **Descrizione** della definizione di riga. |
| Dimensioni            | Un'unità gerarchica che attinge le informazioni direttamente dai dati finanziari. Definisce il posizionamento logico e le lunghezze per il conto e i segmenti correlati. Ogni riga di unità gerarchica deve avere una dimensione in questa colonna. È anche possibile inserire una dimensione in una riga di unità di riepilogo (ad esempio, per le spese che sono direttamente correlate a tale unità). Se si immette una dimensione in una riga di unità di riepilogo, i conti utilizzati nelle unità padre non devono essere utilizzati in unità figlio. In caso contrario, gli importi potrebbero essere duplicati. |
| Definizioni di riga       | Il nome della definizione di riga per l'unità gerarchica. Per tutte le unità dell'albero gerarchico viene utilizzata la stessa definizione di riga. Quando si genera un report, viene utilizzata questa definizione di riga per ogni unità gerarchica. La definizione di riga può includere più collegamenti di dimensioni finanziarie. Se viene specificata una definizione di riga nell'albero gerarchico, selezionare la casella di controllo **Usa definizione di riga da albero gerarchico** nella scheda **Report** della definizione del report. |
| Collegamento riga              | Collegamento di riga da utilizzare per l'unità gerarchica. I collegamenti di riga vengono definiti affinché la definizione di riga identifichi le dimensioni finanziarie a cui effettuare il collegamento. |
| Collegamento esterno         | Collegamento di riga da utilizzare per l'unità gerarchica. Collegamenti riga vengono definiti perché la definizione di riga identifichi il report a cui collegarsi. |
| File esterno         | Percorso del file del foglio di lavoro del report finanziario da cui estrarre i dati. |
| Opzioni pagina          | Questa colonna controlla se i dettagli per l'unità gerarchica vengono eliminati quando il report viene visualizzato o stampato. |
| % rollup              | La percentuale dell'unità gerarchica da allocare alla unità padre. La percentuale immessa nella colonna viene applicata a ogni riga della definizione di riga prima che il valore nella riga venga aggiunto al report padre. Ad esempio, se un'unità figlio deve essere divisa equamente tra due reparti, gli importi in ogni riga verranno moltiplicati per 50 percento prima di aggiungere il valore al report del reparto. Un'unità gerarchica non può avere due unità padre. Per allocare gli importi da un'unità gerarchica a due unità padre, creare un'altra unità gerarchica con la stessa dimensione per eseguire il rollup del 50 percento aggiuntivo. Immettere percentuali intere senza separatore decimale. Ad esempio, **25** rappresenta l'allocazione del 25% al padre. Se si include un separatore decimale (**25**), 0,25% viene allocato all'elemento padre. Per utilizzare una percentuale minore di 1%, utilizzare l'opzione **Consenti rollup &lt;1%** nella definizione di report. Questa opzione è nella scheda **Opzioni aggiuntive** nella finestra di dialogo **Impostazioni del report**. Accedere alla finestra di dialogo dal pulsante **Altro** nella scheda **Impostazioni** della definizione di report. |
| Sicurezza dell'unità         | Le restrizioni su quali utenti e gruppi possono accedere alle informazioni dell'unità gerarchica. |
| Testo aggiuntivo       | Testo incluso nel report. |

Completare i passaggi seguenti per creare una definizione di albero gerarchico:

1. Aprire Progettazione report.
2. Fare clic su **File** &gt; **Nuovo** &gt; **Definizione di albero gerarchico**.
3. Fare clic su **Modifica** &gt; **Inserisci unità gerarchiche da dimensioni**.
4. Nella finestra di dialogo **Inserisci unità gerarchiche da dimensioni** selezionare la casella di controllo per ogni dimensione da includere nell'albero gerarchico. La finestra di dialogo **Inserisci unità gerarchiche da dimensioni** contiene le seguenti sezioni.

    | Sezione                          | Descrizione |
    |----------------------------------|-------------|
    | Segmentazione dimensioni report | Utilizzare i pulsanti **Dividi segmenti** e **Combina segmenti** per modificare il numero e la lunghezza dei segmenti.<blockquote>[!NOTE] È possibile combinare solo segmenti che sono stati divisi. Per combinare più dimensioni, utilizzare caratteri jolly nei valori di dimensione.</blockquote> |
    | Includi/Posizione caratteri       | Questa sezione elenca le dimensioni definite nei dati finanziari e mostra il numero di caratteri nel valore più lungo definito per ogni dimensione. Selezionare la casella di controllo di una dimensione per includere la dimensione nella gerarchia dell'albero gerarchico. |
    | Gerarchia e intervalli di segmenti     | Questa sezione mostra la gerarchia di dimensioni. È possibile spostare le dimensioni nell'elenco per modificare il relativo ordine gerarchico. Nei campi **Da dimensione** e **A dimensione** è possibile specificare un intervallo di valori all'interno di ciascuna dimensione. Se non si specifica un intervallo, tutti i valori di dimensione vengono inseriti nell'albero gerarchico.<blockquote>[!NOTE] Se si utilizza più di una dimensione, nei risultati verranno restituite solo combinazioni di dimensioni registrate.</blockquote> |

    Per una schermata che mostra un esempio della finestra di dialogo **Inserisci unità gerarchiche da dimensioni**, vedere la sezione "Esempio della finestra di dialogo Inserisci unità gerarchiche da dimensioni" più avanti in questo articolo.

5. Per creare segmenti aggiuntivi, ad esempio dividendo un segmento in due più brevi segmenti, fare clic sulla posizione corretta nel campo **Posizione caratteri** quindi fare clic su **Dividi segmenti**.
6. Per unire due segmenti in un segmento, fare clic in uno dei due riquadri di segmenti da unire e quindi fare clic su **Combina segmenti**.
7. La gerarchia determina come le dimensioni si relazionano tra loro e l'intervallo per ogni dimensione. Per modificare la gerarchia di dimensioni, nell'area **Gerarchia e intervalli di segmenti**, selezionare la dimensione da spostare quindi fare clic su **Sposta su** o **Sposta giù**.
8. Per specificare un intervallo di valori di dimensione da aggiungere al nuovo albero gerarchico, nell'area **Gerarchia e intervalli di segmenti** eseguire questi passaggi:

    1. Nel campo **Da dimensione** per la dimensione, immettere il primo valore nell'intervallo.
    2. Nel campo **A dimensione** immettere l'ultimo valore dell'intervallo.

9. Per ogni dimensione nell'area **Gerarchia e intervalli di segmenti**, ripetere i passaggi 7 e 8.
10. Dopo aver terminato di definire come inserire le unità gerarchiche nel nuovo albero gerarchico, fare clic su **OK**.
11. Fare clic su **File** &gt; **Salva** per salvare l'albero gerarchico. Immettere un nome univoco e una descrizione per l'albero gerarchico, quindi fare clic su **OK**.

### <a name="open-an-existing-reporting-tree-definition"></a>Aprire una definizione di albero gerarchico esistente

1. In Progettazione report, nel pannello di navigazione, fare clic su **Definizioni di albero gerarchico**.
2. Nell'elenco di alberi gerarchici fare doppio clic su un nome per aprirlo.
3. Per visualizzare tutti i blocchi predefiniti associati all'albero gerarchico, fare clic con il pulsante destro del mouse sulla definizione di albero gerarchico e selezionare **Associazioni**.

### <a name="roll-up-data-in-a-reporting-tree"></a>Rollup dei dati in un albero gerarchico

Quando si usa un albero gerarchico, è possibile aggregare importi da unità gerarchiche figlio a livello di unità gerarchica padre. Questa aggregazione è nota come rollup dei dati. Le seguenti regole vengono utilizzate per il rollup di importi nelle unità padre in un albero gerarchico:

- In un albero gerarchico, le unità figlio devono contenere dimensioni, a meno che l'albero gerarchico sia un albero a livello singolo. Le unità padre in genere non contengono le dimensioni in un albero gerarchico.

    > [!NOTE]
    > Specificare le dimensioni sia per le unità figlio che le unità padre può causare la duplicazione dei dati nel report.

- Le unità gerarchiche contenenti le dimensioni nell'albero gerarchico corrispondono alle dimensioni utilizzate nelle definizioni di riga e di colonna. La combinazione di dimensioni determina gli importi restituiti per tale unità. Ad esempio, le righe 6 e 7 nell'Esempio 2 più avanti in questo articolo restituiranno solo i valori per i reparti 00 e 01, rispettivamente.
- Gli importi per le unità gerarchiche padre che non contengono dimensioni nell'albero gerarchico vengono determinati dal report dell'unità figlio e sottoposti a rollup dell'importo nell'unità padre specificata. Ad esempio, se l'unità padre (vedere Contoso USA nell'esempio 2 degli esempi di rollup dei dati) ha due unità figlio (022 e 023) e non contiene le dimensioni, un report viene generato per ogni figlio e il padre. Il totale del padre è la somma dei due importi figlio.

### <a name="manage-reporting-units"></a>Gestire le unità gerarchiche

Ogni definizione di albero gerarchico viene visualizzata in visualizzazioni univoche. Esiste una visualizzazione grafica che mostra la gerarchia padre/figlio e una visualizzazione foglio di lavoro contenente le informazioni specifiche per ogni unità gerarchica. La visualizzazione grafica e la visualizzazione del foglio di lavoro sono collegate. Quando si seleziona un'unità gerarchica in una visualizzazione, verrà selezionata anche nell'altra visualizzazione. È possibile creare gerarchie interdimensionali basate sulle relazioni dimensionali nei dati finanziari. Quando si crea una definizione di albero gerarchico, è possibile utilizzare più volte le stesse definizioni di riga, che si stia generando nuovamente un rendiconto del reddito di reparto o un rendiconto di riepilogo del reddito consolidato. Le dimensioni definite nella definizione di riga possono essere combinate alle dimensioni della definizione di albero gerarchico per fornire varie visualizzazioni delle prestazioni dell'organizzazione.

### <a name="reporting-unit-structure"></a> Struttura dell'unità gerarchica

I seguenti tipi di punti di unità gerarchica vengono utilizzati nei report finanziari:

- Un'unità di dettaglio attinge le informazioni direttamente dai dati finanziari, un foglio di lavoro di Excel, o un altro foglio di lavoro di report finanziari.
- Un'unità di riepilogo riassume i dati delle unità di livello inferiore.

Un'unità gerarchica padre è un'unità di riepilogo che aggrega informazioni riepilogative da un'unità di dettaglio. Un'unità di riepilogo può essere sia un'unità di dettaglio che di riepilogo. Pertanto, un'unità di riepilogo può attingere informazioni da un foglio di lavoro di Excel, i dati finanziari o un'unità di livello inferiore. Un'unità padre può essere unità figlio di un'unità padre di livello superiore. Un'unità gerarchica figlio può essere un'unità di dettaglio che effettua il pull di informazioni direttamente dai dati finanziari o un foglio di lavoro di Excel. Un'unità gerarchica figlio può essere anche un'unità di riepilogo intermedia. In altre parole, può essere l'unità padre di un'unità di livello inferiore e anche l'unità figlio di un'unità di riepilogo di livello superiore. Nello scenario più comune per le unità gerarchiche, le unità padre hanno una cella vuota nella colonna **Dimensioni** e le unità figlio hanno collegamenti a combinazioni di dimensioni specifiche o jolly.

### <a name="organize-reporting-units"></a> Organizzare le unità gerarchiche

È possibile ridisporre la struttura organizzativa di una definizione di albero gerarchico spostando le unità gerarchiche nella visualizzazione grafica. È inoltre possibile promuovere unità gerarchiche a un livello superiore nell'albero gerarchico e abbassarle a un livello inferiore nell'albero gerarchico.

1. In Progettazione report, aprire l'albero gerarchico da modificare.
2. Nella visualizzazione grafica della definizione di albero gerarchico, selezionare un'unità gerarchica.
3. Trascinare l'unità in una nuova posizione. In alternativa, fare clic con il pulsante destro del mouse e selezionare **Promuovi unità gerarchica** o **Abbassa di livello unità gerarchica.**
4. Fare clic su **File** &gt; **Salva** per salvare le modifiche.

### <a name="add-text-about-a-reporting-unit"></a> Aggiungere testo su un'unità gerarchica

Una voce di testo aggiuntivo è una stringa di testo statica lunga fino a 255 caratteri che aggiunge informazioni nella definizione di albero gerarchico. Ad esempio, il testo può essere una descrizione breve della società. È possibile creare fino a dieci voci di testo aggiuntivo per ogni unità gerarchica in una definizione di albero gerarchico. Il testo aggiuntivo viene visualizzato nel report dell'unità gerarchica a cui il testo verrà assegnato. È possibile aggiungere le voci di testo dalla colonna **Descrizione** della definizione di riga e dalla scheda **Intestazioni e piè di pagina** nella definizione di report.

1. In Progettazione report, aprire l'albero gerarchico da modificare.
2. Fare doppio clic sulla cella **Testo aggiuntivo** della riga dell'unità gerarchica.
3. Nella prima riga vuota della finestra di dialogo **Testo aggiuntivo**, digitare il testo. Alla prima riga che contiene il testo viene fatto riferimento come UnitText1, indipendentemente dalla relativa posizione nella finestra di dialogo **Testo aggiuntivo**.
4. Per aggiungere più voci di testo per l'unità gerarchica, digitare il testo in una riga vuota.
5. Scegliere **OK**.

### <a name="remove-additional-text-from-a-reporting-unit"></a>Rimuovere il testo aggiuntivo da un'unità gerarchica

1. In Progettazione report aprire la definizione dell'albero gerarchico da modificare.
2. Fare doppio clic sulla cella **Testo aggiuntivo** della riga relativa all'unità gerarchica.
3. Nella finestra di dialogo **Testo aggiuntivo**, selezionare la voce da rimuovere e fare clic su **Cancella**. In alternativa, fare clic con il pulsante destro del mouse sulla voce e quindi selezionare **Taglia**.
4. Scegliere **OK**.

### <a name="restrict-access-to-a-reporting-unit"></a>Limitare l'accesso a un'unità gerarchica

È possibile impedire a determinati utenti e gruppi di accedere a un'unità gerarchica. È inoltre possibile definire restrizioni in modo che si applicano alle unità gerarchiche figlio dell'unità gerarchica.

1. In Progettazione report, aprire l'albero gerarchico da modificare.
2. Fare doppio clic sulla cella **Sicurezza unità** della riga relativa all'unità gerarchica a cui limitare l'accesso.
3. Nella finestra di dialogo **Sicurezza dell'unità**, fare clic su **Utenti e gruppi**.
4. Selezionare utenti o gruppi che devono avere accesso all'unità gerarchica quindi fare clic su **OK**.
5. Per limitare l'accesso alle unità gerarchiche figlio, selezionare la casella di controllo **Aggiungi sicurezza a unità gerarchiche figlio.**
6. Scegliere **OK**.

### <a name="remove-access-to-a-reporting-unit"></a>Rimuovere l'accesso a un'unità gerarchica

1. In Progettazione report, aprire l'albero gerarchico da modificare.
2. Fare doppio clic sulla cella **Sicurezza dell'unità** per la riga dell'unità gerarchica a cui rimuovere l'accesso.
3. Nella finestra di dialogo **Sicurezza dell'unità** selezionare un nome, quindi fare clic su **Rimuovi**.
4. Scegliere **OK**.

### <a name="link-to-reports"></a>Collegamento ai report

Dopo aver creato una colonna di **report** nella definizione di riga e si è specificato il report da includere nel report, è necessario aggiornare l'albero gerarchico con la colonna collegata e le informazioni sul report. Un report può essere importato in qualsiasi unità nell'albero gerarchico.

### <a name="identify-the-report-in-a-reporting-tree"></a>Identificare il report in un albero gerarchico

1. In Progettazione report, aprire l'albero gerarchico da modificare.
2. Nella colonna **Definizioni di riga**, le informazioni nelle celle sono basare sulle informazioni della riga selezionata, poiché la stessa definizione di riga deve essere utilizzata in tutte le unità dell'albero gerarchico. Fare doppio clic sulla cella **Definizioni di riga** quindi selezionare la definizione di riga contenente informazioni sul report.
3. Nella cella **Collegamento al foglio di lavoro** per un'unità gerarchica, selezionare il nome del collegamento corrispondente al report.
4. Nella cella **Percorso cartella di lavoro o report** per un'unità gerarchica, digitare il nome del report o cercare e selezionare il report.
5. Per specificare un foglio di lavoro in un report, immettere il nome del foglio di lavoro della cella **Nome del foglio di lavoro**.
6. Ripetere i passaggi da 3 a 5 per ogni unità gerarchica che deve ricevere i dati da un report. Per impedire che dati errati siano visualizzati nel report, assicurarsi che i nomi dei report corretti compaiano nella corrispondente unità dell'albero gerarchico.

## <a name="examples"></a>Esempi
### <a name="reporting-unit-structure--example-1"></a>Struttura di unità gerarchiche - Esempio 1

Ecco la struttura delle unità gerarchiche nel seguente albero gerarchico:

- L'unità gerarchica Contoso Japan è un'unità padre delle unità figlio Contoso Japan Sales e Contoso Japan Consulting,
- L'unità di divisione Contoso Japan Sales è sia unità figlio dell'unità Contoso Japan che unità padre delle unità Home Sales e Auto Sales.
- Le unità gerarchiche di dettaglio di livello inferiore (Home Sales, Auto Sales, Client Services e Operations) rappresentano reparti nei dati finanziari. Queste unità gerarchiche sono nell'area ombreggiata del diagramma.
- Le unità di riepilogo di livello superiore riepilogano le informazioni dalle unità di dettaglio.

[![ContosoEntertainmentSummaryReportStructure](./media/contosoentertainmentsummaryreportstructure.png)](./media/contosoentertainmentsummaryreportstructure.png)

### <a name="reporting-unit-structure--example-2"></a>Struttura di unità gerarchiche - Esempio 2

Nel seguente diagramma viene illustrato un albero gerarchico che ha una struttura organizzativa che viene suddivisa per funzione aziendale.

[![summaryofallunitscontoso](./media/summaryofallunitscontoso.png)](./media/summaryofallunitscontoso.png)

### <a name="example-of-the-insert-reporting-units-from-dimensions-dialog-box"></a>Esempio della finestra di dialogo Inserisci unità gerarchiche da dimensioni

L'illustrazione seguente mostra un esempio della finestra di dialogo **Inserisci unità gerarchiche da dimensioni**. Per questo esempio, i risultati restituiranno la combinazione di business unit, centri di costo e reparti.

[![InsertReportingUnits](./media/insertreportingunits.png)](./media/insertreportingunits.png)

La definizione di albero gerarchico risultante è ordinata per business unit, quindi per centro di costo e poi per reparto. La dimensione per la quinta unità gerarchica è **Business Unit = \[001\], Cost Center =\[\], Department = \[022\]** e identifica un'unità gerarchica per i conti che sono specifici per la business unit 001 e il reparto 022.

[![ReportingTree](./media/reportingtree-1024x646.png)](./media/reportingtree.png)

### <a name="examples-of-data-roll-up"></a>Esempi di rollup dei dati

Negli esempi seguenti vengonoi mostrate le informazioni possibili utilizzate in una definizione di albero gerarchico per dati sottoposti a rollup.

#### <a name="example-1"></a>Esempio 1

[![MutliCompanyRollUp](./media/mutlicompanyrollup.png)](./media/mutlicompanyrollup.png)

#### <a name="example-2"></a>Esempio 2

[![CrossCompanyDepartmentRollUp](./media/crosscompanydepartmentrollup.png)](./media/crosscompanydepartmentrollup.png)

## <a name="additional-resources"></a>Risorse aggiuntive

[Creazione di report finanziari](financial-reporting-intro.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]