---
title: Utilizzare le origini dati del codice a barre per generare immagini di codici a barre
description: Questo argomento spiega come utilizzare le origini dati del codice a barre per generare immagini di codici a barre.
author: NickSelin
ms.date: 10/21/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERModelMappingDesigner, EROperationDesigner
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-05-01
ms.dyn365.ops.version: Version 10.0.13
ms.openlocfilehash: 08b9d03517a600cf46b1093cfa3bc454621eabd0
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5748367"
---
# <a name="use-barcode-data-sources-to-generate-bar-code-images"></a>Utilizzare le origini dati del codice a barre per generare immagini di codici a barre

[!include[banner](../includes/banner.md)]

È possibile utilizzare il framework [Report elettronici](general-electronic-reporting.md) per progettare [componenti del formato ER](general-electronic-reporting.md#FormatComponentOutbound) che è possibile eseguire per generare i documenti in uscita elettronici e stampabili necessari. Per generare un documento in uscita nel formato Microsoft Office è necessario specificare il layout del report utilizzando un documento Microsoft Excel o un documento Microsoft Word come modello di report. La [pagina della progettazione delle operazioni ER](general-electronic-reporting.md#building-a-format-that-uses-a-data-model-as-a-base) consente di allegare un documento Excel o Word come modello per un formato ER. I seguenti elementi denominati nel modello allegato sono associati agli elementi del componente di formato configurato:

- Controlli del contenuto in Word
- Fogli, intervalli, celle, forme e immagini denominati in Excel

Questi elementi denominati vengono utilizzati come segnaposto per i dati immessi in un documento generato quando viene eseguito un formato ER. Gli elementi di formato ER sono associati alle origini dati. Queste origini dati specificano i dati che verranno inseriti nei documenti generati in fase di esecuzione. Per ulteriori informazioni, vedere [Incorporare immagini e forme nei documenti generati utilizzando ER](electronic-reporting-embed-images-shapes.md)

ER ora supporta il tipo di origine dati **Codice a barre**. Pertanto, ora è possibile generare un'immagine che rappresenti il codice a barre per il testo specificato. Quando si configura un formato ER, è possibile specificare le origini dati di tipo **Codice a barre** per generare immagini di codici a barre. È quindi possibile aggiungere quelle immagini ai documenti aziendali generati, come ordini, fatture, documenti di trasporto e ricevute. È anche possibile aggiungerli a vari tipi di etichette, come etichette di prodotti e scaffali, nonché etichette di imballaggio e spedizione.

I seguenti segnaposto possono essere utilizzati nei modelli di report per inserire le immagini di codici a barre:

- Controllo del contenuto [immagine](https://docs.microsoft.com/office/client-developer/word/content-controls-in-word) per Word
- Oggetto [immagine](https://support.office.com/article/insert-pictures-3c51edf4-22e1-460a-b372-9329a8724344) in Excel

Utilizzando un'origine di dati di tipo **Codice a barre** è possibile generare codici a barre nei seguenti formati:

- Codici a barre unidimensionali:

    - Codabar
    - Code 39
    - Code 93
    - Code 128
    - EAN-8
    - EAN-13
    - ITF-14
    - Posta intelligente
    - MSI
    - Plessey
    - PDF417
    - UPC-A
    - UPC-E

- Codici a barre bidimensionali:

    - Aztec
    - Matrice dati
    - Codice QR

Quando si configura un'origine dati **Codice a barre**, è possibile definire specifici parametri di rendering che vengono utilizzati per generare un'immagine:

- **Larghezza** - Specificare la larghezza del codice a barre in pixel. Un valore di **0** (zero) indica che viene utilizzata la larghezza predefinita. Il significato può variare per altri formati.
- **Altezza** - Specificare l'altezza del codice a barre in pixel. Un valore di **0** (zero) indica che viene utilizzata l'altezza predefinita. Il significato può variare per altri formati.
- **Margine** - Specificare la dimensione del margine del codice a barre in pixel. Il margine è l'area su ciascun lato di un codice a barre che deve essere mantenuta libera (zona libera). Un valore di **0** (zero) indica che viene utilizzato il margine predefinito. Il significato può variare per altri formati.
- **Contenuto dell'output** - Impostare il valore su **Sì** per generare un'immagine di codice a barre che contiene le informazioni codificate come testo. Il valore predefinito è **No**.
- **Codifica** - Specificare il tipo di caratteri codificati nell'immagine del codice a barre generata. Per impostazione predefinita, viene utilizzata la codifica **UTF-8**.

> [!IMPORTANT]
> Quando si aggiunge una nuova origine dati **Codice a barre**, è necessario posizionarla sotto un altro elemento (contenitore) come elemento nidificato.
>
> Quando si associa un'origine dati **Codice a barre** a un elemento cella in un formato e l'elemento cella rappresenta un controllo del contenuto di Word o un'immagine di Excel, l'origine dati viene presentata in quell'associazione come una funzione che ha un singolo parametro di tipo **Stringa**. È necessario utilizzare questo parametro per specificare il testo che deve essere trasformato in un'immagine di codice a barre e letto quando viene scannerizzato un codice a barre generato.

Per ulteriori informazioni su questa funzionalità, completare gli esempi in questo argomento.

## <a name="example-generate-a-payment-check-that-contains-a-bar-code-that-encodes-the-payable-amount"></a>Esempio: generare un assegno di pagamento che contiene un codice a barre che codifica l'importo da pagare

Questo esempio mostra come un utente nel ruolo **Amministratore di sistema** o **Consulente funzionale per la creazione di report elettronici** può configurare un formato ER che contiene un modello utilizzato per generare un documento in uscita in formato Excel che contiene un codice a barre. Di seguito è riportata una panoramica dei passaggi necessari.

1. [Completare i prerequisiti](#ExamplePrerequisites).
2. [Attivare un provider di configurazioni](#ExampleProvider).
3. [Importare la soluzione ER fornita](#ExampleImportSolution).
4. [Generare un assegno di pagamento](#ExampleGenerateCheque).
5. [Esaminare l'assegno di pagamento generato](#ExampleReviewGeneratedCheque).
6. [Modificare il formato della soluzione ER fornita](#ExampleModifyFormat).

    1. [Applicare un nuovo modello di assegno](#ExampleModifyFormatApplyTemplate).
    2. [Aggiungere una nuova origine dati codice a barre](#ExampleModifyFormatAddDataSource).
    3. [Associare un nuovo elemento di formato](#ExampleModifyFormatBindFormatElement).
    4. [Rendere disponibile la versione modificata per le esecuzioni di test](#ExampleModifyFormatMakeVersionAvailable).

        1. [Completare la versione modificata del formato](#CompleteToRun).
        2. [Rendere disponibile per l'utilizzo la versione bozza](#MarkToRun).

7. [Generare un assegno di pagamento](#ExampleGenerateCheque2).
8. [Convertire l'assegno generato in un PDF](#ExampleConvertToPDF).

In questo esempio, si utilizza la soluzione ER fornita che è stata configurata per generare assegni di pagamento. Questa soluzione genera assegni di pagamento in cui l'importo da pagare è scritto sia come numero che come testo. Questa soluzione ER viene modificata in modo che l'assegno includa anche un codice a barre generato in cui l'importo da pagare è codificato e può essere letto utilizzando uno scanner di codici a barre.

Queste operazioni possono essere completate nella società fittizia **USMF** in Microsoft Dynamics 365 Finance.

### <a name="complete-the-prerequisites"></a><a name="ExamplePrerequisites"></a>Completare i prerequisiti

Per completare l'esempio in questo argomento, è necessario avere accesso alla società USMF in Finance per uno dei seguenti ruoli:

- Consulente funzionale per la creazione di report elettronici
- Amministratore di sistema

Se l'esempio nell'argomento [Incorporare immagini e forme nei documenti generati utilizzando ER](electronic-reporting-embed-images-shapes.md) non è ancora stato completato, scaricare le seguenti configurazioni della soluzione ER di esempio.

| Descrizione contenuto         | Nome file                   |
|-----------------------------|-----------------------------|
| Configurazione del modello di dati ER | Model for cheques.xml       |
| Configurazione di formato ER     | Cheques printing format.xml |

Inoltre, scaricare il seguente file Excel che contiene il modello modificato per la soluzione ER fornita.

| Descrizione contenuto | Nome file                 |
|---------------------|---------------------------|
| Modello report     | Check template Excel.xlsx |

### <a name="activate-a-configuration-provider"></a><a name="ExampleProvider"></a>Attivare un provider di configurazioni

1. Andare a **Amministrazione organizzazione** \> **Aree di lavoro** \> **Creazione di report elettronici**.
2. Nella pagina **Configurazioni localizzazione** nella sezione **Provider di configurazione** verificare che il [provider di configurazione](general-electronic-reporting.md#Provider) per la società di esempio **Litware, Inc.** sia elencato e contrassegnato come attivo. Se non è elencato o non è contrassegnato come attivo, completare i passaggi dell'argomento [Creare un provider di configurazione e contrassegnarlo come attivo](tasks/er-configuration-provider-mark-it-active-2016-11.md).

![Impostazione della società di esempio come attiva nella pagina Configurazioni localizzazione](./media/er-barcode-data-source-active-provider.png)

### <a name="import-the-provided-er-solution"></a><a name="ExampleImportSolution"></a>Importare la soluzione ER fornita

1. Andare a **Amministrazione organizzazione** \> **Aree di lavoro** \> **Creazione di report elettronici**.
2. Nella pagina **Configurazioni localizzazione**, nella sezione **Configurazioni**, selezionare il riquadro **Configurazioni report**.
3. Nella pagina **Configurazioni**, se la configurazione **Modello per assegni** non è disponibile nella struttura delle configurazioni, seguire questi passaggi per importare la configurazione del modello di dati ER.

    1. Nella riquadro Azioni, selezionare **Scambia** \> **Carica da file XML**.
    2. Nella finestra di dialogo, selezionare **Sfoglia**, trovare e selezionare il file **Model for cheques.xml**, quindi selezionare **OK**.

4. Se la configurazione **Formato stampa assegni** non è disponibile nella struttura delle configurazioni, seguire questi passaggi per importare la configurazione di formato ER.

    1. Nella riquadro Azioni, selezionare **Scambia** \> **Carica da file XML**.
    2. Nella finestra di dialogo, selezionare **Sfoglia**, trovare e selezionare il file **Cheques printing format.xml**, quindi selezionare **OK**.

5. Nell'albero di configurazione, espandere **Modello per assegni**.
6. Esaminare l'elenco delle configurazioni ER importate nella struttura delle configurazioni.

### <a name="generate-a-payment-check"></a><a name="ExampleGenerateCheque"></a>Generare un assegno di pagamento

1. Passare a **Gestione cassa e banche** \> **Conti bancari** \> **Conti bancari**.
2. Nella pagina **Conti bancari**, selezionare il conto **USMF OPER**.
3. Nella pagina dei dettagli del conto bancario, nel riquadro azioni, nella scheda **Imposta**, nel gruppo **Layout**, selezionare **Assegno**.
4. Nella pagina **Layout assegno** selezionare **Modifica**.
5. Nella scheda dettaglio **Generale**, impostare l'opzione **Formato esportazione elettronica generica** su **Sì**.
6. Nel campo **Esporta configurazione formato** selezionare il formato ER **Formato stampa assegni** importato in precedenza.
7. Nel riquadro azioni fare clic su **Stampa di prova**.
8. Nella finestra di dialogo, impostare l'opzione **Formato assegno negoziabile** su **Sì**, quindi selezionare **OK**.

    ![Finestra di dialogo Layout assegno - Stampa di prova](./media/er-barcode-data-source-check-layout.png)

### <a name="review-the-generated-payment-check"></a><a name="ExampleReviewGeneratedCheque"></a>Esaminare l'assegno di pagamento generato

- Aprire l'assegno generato in Excel.
2. Esaminare l'assegno generato.

    ![Assegno di pagamento generato in Excel](./media/er-barcode-data-source-cheque1.png)

### <a name="modify-the-format-of-the-provided-er-solution"></a><a name="ExampleModifyFormat"></a>Modificare il formato della soluzione ER fornita

#### <a name="apply-a-new-check-template"></a><a name="ExampleModifyFormatApplyTemplate"></a>Applicare un nuovo modello di assegno

È possibile utilizzare l'applicazione desktop Excel per aprire il file **Cheque template Excel.xlsx** importato in precedenza. Si noti che questo modello differisce dal modello utilizzato per generare un assegno di pagamento nella soluzione ER fornita. Inoltre, include un elemento **AmountBarcode** per l'immagine del codice a barre.

![Elemento AmountBarcode nel modello Excel](./media/er-barcode-data-source-cheque2.png)

È ora necessario modificare la soluzione ER e quindi [riapplicare](modify-electronic-reporting-format-reapply-excel-template.md) il modello modificato.

1. Andare a **Amministrazione organizzazione** \> **Aree di lavoro** \> **Creazione di report elettronici**.
2. Nella pagina **Configurazioni localizzazione**, nella sezione **Configurazioni**, selezionare **Configurazioni report**.
3. Nella pagina **Configurazioni** nell'albero di configurazione, espandere **Modello per assegni** e selezionare **Formato stampa assegni**.
4. Nel riquadro azioni selezionare **Progettazione**.
5. Nella pagina della progettazione delle operazioni ER selezionare la scheda **Mapping** sul lato destro della pagina, quindi, nel riquadro dell'albero del formato a sinistra, selezionare **Espandi/Comprimi**.
6. Si noti che tutti gli elementi del formato cella sono associati alle origini dati appropriate.

    ![Associazione di elementi di formato cella a origini dati nella pagina della progettazione delle operazioni ER](./media/er-barcode-data-source-cells-bound.png)

7. Selezionare la scheda **Formato** sul lato destro della pagina.
8. Nel riquadro azioni selezionare i puntini di sospensione (**...**), quindi selezionare **Importa**.
9. Nel gruppo **Importa**, selezionare **Aggiorna da Excel**, quindi selezionare **Aggiorna modello**.
10. Nella finestra di dialogo, passare al file **Cheque template Excel.xlsx** salvato sul computer, selezionarlo e quindi selezionare **OK** per confermare che il modello selezionato deve essere applicato.
11. Selezionare la scheda **Mapping** sul lato destro della pagina, quindi, nel riquadro dell'albero del formato a sinistra, selezionare **Espandi/Comprimi**.
12. Si noti che l'elemento cella **AmountBarcode** è stato aggiunto al formato. Questo elemento è associato all'elemento **AmountBarcode** che è stato aggiunto al modello Excel modificato come segnaposto per un'immagine del codice a barre.

    ![Elemento cella AmountBarcode aggiunto al formato nella pagina della progettazione delle operazioni ER](./media/er-barcode-data-source-cell-added.png)

#### <a name="add-a-new-barcode-data-source"></a><a name="ExampleModifyFormatAddDataSource"></a>Aggiungere una nuova origine dati codice a barre

Successivamente, è necessario aggiungere una nuova origine dati di tipo **Codice a barre**.

1. Nella pagina della progettazione delle operazioni ER nella scheda **Mapping** sul lato destro della pagina, selezionare l'origine dati **print**.
2. Selezionare **Aggiungi** e quindi nel gruppo **Funzioni** selezionare il tipo di origine dati **Codice a barre**.

    ![Selezione del tipo di origine dati Codice a barre](./media/er-barcode-data-source-add.png)

3. Nella finestra di dialogo, nel campo **Nome**, immettere **barcode**.
4. Nel **Formato codice a barre**, selezionare **Codice 128**.
5. Nel campo **Larghezza** immetti **500**.
6. Selezionare **OK**.

    ![Finestra di dialogo Proprietà dell'origine dati](./media/er-barcode-data-source-add2.png)

#### <a name="bind-a-new-format-element"></a><a name="ExampleModifyFormatBindFormatElement"></a>Associare un nuovo elemento di formato

Successivamente, è necessario associare il nuovo elemento di formato all'origine dati appena aggiunta.

1. Nella pagina della progettazione delle operazioni ER nella scheda **Mapping** sul lato destro della pagina, selezionare l'origine dati **print\\barcode**.
2. Nel riquadro dell'albero del formato a sinistra, selezionare l'elemento cella **AmountBarcode**, quindi selezionare **Associa**.
3. Nel riquadro azioni selezionare **Mostra dettagli**.
4. Si noti che, poiché l'origine dati **Codice a barre** è rappresentata nell'associazione come una funzione che contiene un singolo parametro, il nome dell'elemento formato associato è stato preso automaticamente come argomento di quel parametro.

    ![Dettagli sull'origine dati del codice a barre nella pagina della progettazione delle operazioni ER](./media/er-barcode-data-source-bind1.png)

5. Selezionare **Modifica formula** per regolare l'associazione.

    Non si desidera che venga restituito il nome dell'elemento cella. Pertanto, è necessario configurare un'espressione che restituisca il testo contenente l'importo da pagare dell'assegno corrente. Perché l'intervallo **ChequeLines** padre è associato all'origine dati **model.cheques**, l'importo da pagare dell'assegno corrente è disponibile nel campo **model.cheques.attributes.amount** del tipo di dati **Reale**.

6. Nel campo **Formula** immettere **print.barcode(NUMBERFORMAT(@.attributes.amount, "F2"))**.
7. Selezionare **Salva** e quindi chiudere la [pagina della progettazione della formula ER](general-electronic-reporting-formula-designer.md).
8. Si noti che l'associazione è stata modificata.

    ![Associazione modificata nella pagina della progettazione delle operazioni ER](./media/er-barcode-data-source-bind2.png)

9. Selezionare **Salva** e quindi chiudere la pagina della progettazione delle operazioni ER.

#### <a name="make-the-modified-version-available-for-test-runs"></a><a name="ExampleModifyFormatMakeVersionAvailable"></a>Rendere disponibile la versione modificata per le esecuzioni di test

Per impostazione predefinita, le uniche versioni che vengono utilizzate quando si esegue un formato ER sono quelle che hanno lo stato **Completato** e **Condivisa**.

Completate le modifiche, è possibile completare il lavoro con l'attuale versione bozza e rendere le modifiche disponibili per l'uso. Per istruzioni, consultare la sezione [Completare la versione modificata del formato](#CompleteToRun) che segue.

Se si desidera continuare a lavorare con la versione corrente di bozza, ma è necessario utilizzarla per generare assegni, è necessario specificare esplicitamente che si desidera utilizzare la versione bozza del formato per l'esecuzione. Per istruzioni, consultare la sezione [Rendere disponibile la versione bozza](#MarkToRun).

##### <a name="complete-the-modified-format-version"></a><a name="CompleteToRun"></a>Completare la versione modificata del formato

1. Andare a **Amministrazione organizzazione** \> **Aree di lavoro** \> **Creazione di report elettronici**.
2. Nella pagina **Configurazioni localizzazione**, nella sezione **Configurazioni**, selezionare **Configurazioni report**.
3. Nella pagina **Configurazioni** nell'albero di configurazione, espandere **Modello per assegni** e selezionare **Formato stampa assegni**.
4. Nella scheda dettaglio **Versioni**, selezionare il record che lo stato **Bozza**.
5. Selezionare **Cambia stato**, quindi selezionare **Completa**.
6. Nella finestra di dialogo selezionare **OK**.

Lo stato della versione corrente viene modificato da **Bozza** a **Completato** e una nuova versione con lo stato **Bozza** viene creata. È possibile utilizzare questa nuova versione bozza per applicare ulteriori modifiche.

##### <a name="make-the-draft-version-available-for-use"></a><a name="MarkToRun"></a>Rendere disponibile per l'utilizzo la versione bozza

1. Andare a **Amministrazione organizzazione** \> **Aree di lavoro** \> **Creazione di report elettronici**.
2. Nella pagina **Configurazioni localizzazione**, nella sezione **Configurazioni**, selezionare **Configurazioni report**.
3. Nella pagina **Configurazioni**, nel Riquadro azioni, nella scheda **Configurazioni**, nel gruppo **Impostazioni avanzate**, selezionare **Parametri utente**.
4. Nella finestra di dialogo, impostare le opzioni **Esegui impostazione** su **Sì**, quindi selezionare **OK**.
5. Nell'albero di configurazione, espandere **Modello per assegni** e selezionare **Formato stampa assegni**.
6. Impostare l'opzione **Esegui bozza** su **Sì**.
7. Selezionare **Salva**.

La versione bozza del formato selezionato è contrassegnata come disponibile per l'uso quando viene eseguito il formato selezionato.

### <a name="generate-a-payment-check"></a><a name="ExampleGenerateCheque2"></a>Generare un assegno di pagamento

1. Passare a **Gestione cassa e banche** \> **Conti bancari** \> **Conti bancari**.
2. Nella pagina **Conti bancari**, selezionare il conto **USMF OPER**.
3. Nella pagina dei dettagli del conto bancario, nel riquadro azioni, nella scheda **Imposta**, nel gruppo **Layout**, selezionare **Assegno**.
4. Nella pagina **Layout assegno**, nel riquadro azioni, selezionare **Stampa di prova**.
5. Nella finestra di dialogo, impostare l'opzione **Formato assegno negoziabile** su **Sì**.
6. Selezionare **OK**.
7. Esaminare l'assegno generato. Si noti che è stato generato un codice a barre per codificare l'importo da pagare dell'assegno.

    ![Assegno di pagamento generato con codice a barre in Excel](./media/er-barcode-data-source-cheque3.png)

> [!IMPORTANT]
> Viene generata un'eccezione se l'argomento di un'origine dati **Codice a barre** non è conforme ai requisiti appropriati specifici per il formato del codice a barre. Ad esempio, quando l'origine dati **Codice a barre** viene chiamata per generare un codice a barre [EAN-8](https://wikipedia.org/wiki/EAN-8) per il testo fornito, viene generata un'eccezione se la lunghezza del testo supera i sette caratteri.

### <a name="convert-the-generated-check-to-a-pdf"></a><a name="ExampleConvertToPDF"></a>Convertire l'assegno generato in un PDF

Come descritto nell'argomento [Generare moduli FTI stampabili](er-generate-printable-fti-forms.md#finland) è possibile utilizzare un carattere speciale per produrre codici a barre in un documento generato. In questo caso, ulteriori trasformazioni del documento generato potrebbero dipendere dalla disponibilità di quel carattere nell'ambiente di trasformazione. Ad esempio, se si tenta di convertire un documento in formato PDF o di visualizzarne l'anteprima in un ambiente in cui manca il carattere, i codici a barre non verranno visualizzati correttamente.

Tuttavia, quando si utilizza l'origine dati **Codice a barre** per produrre codici a barre, il rendering dei codici a barre non dipende da alcun carattere. Pertanto, è possibile convertire facilmente i documenti che contengono i codici a barre in formato PDF. La seguente illustrazione mostra l'anteprima di un assegno di pagamento generato che è stato [convertito](electronic-reporting-destinations.md#OutputConversionToPDF) in un PDF, in base all'impostazione della [destinazione ER](electronic-reporting-destinations.md) configurata.

![Anteprima del PDF di un assegno di pagamento](./media/er-barcode-data-source-cheque4.png)

## <a name="limitations"></a>Limiti

> [!NOTE]
> Alcuni tipi di codici a barre generati hanno proporzioni fisse. Questo comportamento ha senso se è stata attivata la funzione **Abilita l'utilizzo della libreria EPPlus nel framework di creazione report elettronici** per utilizzare i documenti Excel in ER. In tal caso, un'immagine viene inserita in un segnaposto con proporzioni bloccate. Pertanto, quando le dimensioni di un segnaposto in un modello corrispondono al rapporto di un'immagine immessa, è possibile ridimensionare un'immagine reale in un documento generato per mantenere le proporzioni richieste. Per impedire il ridimensionamento delle immagini, utilizzare un segnaposto con proporzioni previste.

## <a name="additional-resources"></a>Risorse aggiuntive

- [Panoramica sui report elettronici](general-electronic-reporting.md)
- [Destinazioni dei report elettronici](electronic-reporting-destinations.md)
- [Linguaggio della formula nella creazione di report elettronici](er-formula-language.md)
- [Funzione NUMBERFORMAT](er-functions-text-numberformat.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]