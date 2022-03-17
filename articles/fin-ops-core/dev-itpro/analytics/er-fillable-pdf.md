---
title: Progettare le configurazioni ER per completare i modelli PDF
description: In questo argomento vengono fornite informazioni su come progettare un formato di report elettronico (ER) da completare in un modello PDF.
author: NickSelin
ms.date: 02/28/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: a568ddd93bfbc7d536e951a13470b3dedb796e1b
ms.sourcegitcommit: 753714ac0dabc4b7ce91509757cd19f7be4a4793
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/01/2022
ms.locfileid: "8367858"
---
# <a name="design-er-configurations-to-fill-in-pdf-templates"></a>Progettare le configurazioni ER per completare i modelli PDF

[!include[banner](../includes/banner.md)]

Le procedure in questo argomento sono esempi che mostrano come un utente nel ruolo di **Amministratore di sistema** o **Sviluppatore per la creazione di report elettronici** può configurare un formato di report elettronico (ER) che genera report come file PDF utilizzando documenti PDF compilabili come modelli di report. Queste operazione possono essere eseguite in qualsiasi società di Dynamics 365 Finance o Regulatory Configuration Service (RCS).

## <a name="prerequisites"></a>Prerequisiti

Prima di iniziare, è necessario assegnare uno dei seguenti tipi di accessi, a seconda del servizio utilizzato per completare le procedure descritte in questo argomento:

- Accesso a Finance per uno dei seguenti ruoli:

    - Sviluppatore per la creazione di report elettronici
    - Consulente funzionale per la creazione di report elettronici
    - Amministratore di sistema

- Accesso a RCS per uno dei seguenti ruoli:

    - Sviluppatore per la creazione di report elettronici
    - Consulente funzionale per la creazione di report elettronici
    - Amministratore di sistema

È inoltre necessario completare la procedura [Creare fornitori di configurazioni e contrassegnarli come attivi](tasks/er-configuration-provider-mark-it-active-2016-11.md).

Infine, scarica i seguenti file.

| Descrizione contenuto                       | Nome file                                     |
|-------------------------------------------|-----------------------------------------------|
| Modello per la prima pagina del report | [IntrastatReportTemplate1.pdf](https://download.microsoft.com/download/0/8/3/0832c82b-4448-4562-afbf-01e0efc8d999/IntrastatReportTemplate1.pdf)                  |
| Modello per altre pagine del report    | [IntrastatReportTemplate2.pdf](https://download.microsoft.com/download/c/7/a/c7a8a806-2192-4034-9052-e8b84b527d5e/IntrastatReportTemplate2.pdf)                  |
| Formato ER di esempio - PDF                          | [Intrastat report (PDF).version.1.1.xml](https://download.microsoft.com/download/a/8/7/a87aea3e-3f60-404c-8899-c471d20e7ea9/IntrastatreportPDFversion1.1.xml)        |
| Formato ER di esempio - Excel                          | [Intrastat (import from Excel).version.1.1.xml](https://download.microsoft.com/download/a/2/c/a2c0c145-d989-4e55-9d47-9647c02e4ee4/IntrastatimportfromExcelversion1.1.xml) |
| Set di dati di esempio                            | [Intrastat sample data.xlsx](https://download.microsoft.com/download/9/f/1/9f1c5b96-3800-475f-8cf6-1ddd42873758/Intrastatsampledata.xlsx)                    |

## <a name="design-the-format-configuration"></a>Progettare la configurazione di formato

### <a name="get-access-to-the-list-of-configurations-provided-by-microsoft"></a>Ottenere l'accesso all'elenco delle configurazioni fornite da Microsoft

1. Andare a **Amministrazione organizzazione \> Aree di lavoro \> Creazione di report elettronici**.
2. Assicurarsi che il fornitore **Litware, Inc.** sia disponibile e contrassegnato come attivo.
3. Nel riquadro per il provider **Microsoft**, selezionare **Archivi**.

    > [!NOTE]
    > Se un archivio di tipo **LC** è già presente, ignorare i passaggi di questa procedura.

4. Selezionare **Aggiungi**.
5. Nella finestra di dialogo a discesa, nel gruppo di campi **Tipo di archivio di configurazioni** selezionare **LC**.
6. Selezionare **Crea archivio**.
7. Selezionare **OK**.

### <a name="get-the-model-configurations-provided-by-microsoft"></a>Ottenere le configurazioni del modello fornite da Microsoft

1. Nel lato sinistro della pagina **Archivi di configurazione**, selezionare il pulsante **Mostra filtri** (il simbolo di un imbuto).
2. Aggiungere un filtro per il valore **LC** nel campo **Tipo** e utilizzare l'operatore **inizia con**.
3. Selezionare **Applica**.
4. Selezionare **Apri**.
5. Nella struttura selezionare **Modello Intrastat**.
6. Nella scheda dettaglio **Versioni**, selezionare la versione **1**.

    > [!NOTE]
    > Se il pulsante **Importa** nella scheda dettaglio **Versioni** non è disponibile, ignorare i passaggi di questa procedura.

7. Selezionare **Importa**.
8. Selezionare **Sì** per confermare l'importazione della versione selezionata della configurazione del modello **Modello Intrastat**.

### <a name="create-a-new-format-configuration"></a>Creare una nuova configurazione di formato

1. Nell'area di lavoro **Creazione di report elettronici**, selezionare il riquadro **Configurazioni report**.
2. Nella struttura selezionare **Modello Intrastat**.
3. Selezionare **Crea configurazione**.

    > [!NOTE]
    > Se il pulsante **Crea configurazione** non è disponibile, è necessario attivare la modalità di progettazione nella pagina **Parametri per la creazione di report elettronici** che può essere aperta dall'area di lavoro **Creazione di report elettronici**.

4. Nella finestra di dialogo a discesa, nel gruppo di campi **Nuovo**, selezionare l'opzione **Formato basato sul modello dati Intrastat**.
5. Nel campo **Nome**, immettere **Report Intrastat (PDF)**.
6. Nel campo **Descrizione**, immettere **Report Intrastat in formato PDF**.

    > [!NOTE]
    > Il provider di configurazione attiva viene inserito automaticamente. Tale provider potrà gestire la configurazione. Anche se altri provider possono utilizzare la configurazione, non potranno gestirla.

7. Facoltativo: nel campo **Tipo formato** è possibile selezionare un formato specifico per il documento elettronico. Se si seleziona **PDF**, al momento della progettazione, la finestra di progettazione delle operazioni ER offrirà solo gli elementi relativi al formato applicabili ai documenti generati in formato PDF (**PDF\File**, **PDF\Unione PDF** e così via). Se si lascia vuoto questo campo, verrà specificato un formato di documento elettronico in fase di progettazione nella finestra di progettazione delle operazioni ER quando verrà aggiunto un primo elemento di formato. Ad esempio, se si aggiungono **Excel\File** come primo elemento di formato, la finestra di progettazione delle operazioni ER visualizzerà solo gli elementi di formato applicabili ai documenti generati in formato Excel (**Excel\Cella**, **Excel\Intervallo**, e così via.). formato.
8. Selezionare **Crea configurazione**.

Viene creata una nuova configurazione di formato. È possibile utilizzare la versione bozza della configurazione per archiviare il componente del formato ER progettato per generare i documenti elettronici in formato PDF.

### <a name="design-the-format-of-an-electronic-document"></a>Progettazione del formato di un documento elettronico

A questo punto, nella configurazione del formato ER creato, si progetterà il formato ER che genera il report **Controllo Intrastat** in formato PDF. La prima pagina del report deve mostrare un riepilogo del report e i dettagli delle transazioni per il commercio estero dichiarate. Le altre pagine devono mostrare solo i dettagli delle transazioni del commercio estero dichiarate. Poiché le pagine del report generati devono avere diversi layout, due diversi modelli in formato PDF verranno utilizzati nel formato ER.

In qualsiasi visualizzatore PDF, aprire i modelli PDF scaricati. Si noti che ciascun modello contiene i più campi che devono essere completati. In ciascun modello, i dettagli delle transazioni del commercio estero verranno visualizzati come 42 righe, ciascuna delle quali è costituita da nove campi. Il numero di riga viene visualizzata alla fine di ciascun nome del campo, ad esempio **Data 1**...**Data 42** e **Voce doganale 1**...**Voce doganale 42**.

Nella figura seguente è illustrato il modello PDF per la prima pagina del report.

![Modello 1.](media/rcs-ger-filloutpdf-template1.png)

Nella figura seguente è illustrato il modello PDF per le altre pagine del report.

![Modello 2.](media/rcs-ger-filloutpdf-template2.png)

1. Nella pagina **Configurazioni**, selezionare **Progettazione**.
2. Selezionare **Aggiungi radice**.
3. Nella finestra di dialogo a discesa, nella struttura selezionare **PDF \> Unione PDF**.

    Quando si seleziona l'elemento **Unione PDF** come elemento principale del formato, tutti i documenti PDF generati in fase di esecuzione vengono uniti in un unico documento PDF definitivo. Se è necessario un solo modello PDF per generare tutti i documenti richiesti utilizzando il formato ER che si progetta, è possibile selezionare **File PDF** come elemento principale.

4. Nel campo **Nome** immettere **Output**.
5. Nel campo **Preferenze lingua** selezionare **Preferenze utente**. Il report verrà generato nella lingua preferita dall'utente che lo esegue.
6. Nel campo **Preferenze cultura** selezionare **Preferenze utente**. I valori e le date presentati nelle pagine del report verranno formattati in base alle impostazioni locali preferite dell'utente che esegue il report.
7. Selezionare **OK**.
8. Nel riquadro azioni, nella scheda **Importa** selezionare **Importa da PDF**.

    Quando un documento PDF compilabile viene importato come modello per questo formato ER, vengono creati automaticamente tutti gli elementi di formato ER necessari (**File PDF**, **Gruppo campi** e **Capo**) nel formato progettato, in base alla struttura del documento PDF che viene importato.

9. Selezionare **Sfoglia**. Passare al file **IntrastatReportTemplate1.pdf** scaricato in precedenza come prerequisito e selezionarlo.
10. Selezionare **OK**.

    Il file selezionato viene caricato e verrà compilato il campo **Modello** della finestra di dialogo **Importa da PDF**.

11. Impostare l'opzione **Campi gruppo** su **Sì**. Se il documento PDF selezionato contiene gruppi di campi, questi verranno utilizzati per raggruppare gli elementi di formato ER creati. Verrà creato un elemento di formato **Gruppo di campi** per questo scopo.

    Se l'opzione è impostata su **No**, gli elementi di formato ER necessari verranno creati come un elenco normali di elementi nidificati sotto l'elemento di formato **File PDF** creato.

12. Selezionare **OK**.

    ![Importare dalla finestra di dialogo PDF.](media/rcs-ger-filloutpdf-importtemplate.png)

13. Nella struttura espandere **Output**.

    Si noti che il componente **File PDF** è stato creato automaticamente per gestire la creazione della prima pagina del report generata in fase di esecuzione.

14. Nella struttura espandere **Output \> File PDF**.

    Si noti che l'elenco strutturato degli elementi di formato è stato creato automaticamente in questo formato ER, in base alla struttura del documento PDF compilabile importato in precedenza.

15. Nella struttura selezionare **Output \> File PDF**.
16. Nel campo **Nome** immettere **Pagina 1**.

    Questa voce di formato verrà utilizzata per generare la prima pagina del report **Controllo Intrastat**. La pagina mostrerà un riepilogo del report e i dettagli delle transazioni del commercio estero.

    Se si lascia vuoto il campo **Preferenze lingua**, l'impostazione **Preferenze lingua** dell'elemento padre **Unione PDF** determineranno la lingua del report generato utilizzando questo elemento di formato. È possibile selezionare un altro valore per sovrascrivere l'impostazione dell'elemento padre.

    Se si lascia vuoto il campo **Preferenze cultura**, l'impostazione **Preferenze cultura** dell'elemento padre **Unione PDF** determineranno le impostazioni internazionali del report generato utilizzando questo elemento di formato. Le impostazioni internazionali determinano il formato dei valori e delle date nelle pagine del report. È possibile selezionare un altro valore per sovrascrivere l'impostazione dell'elemento padre.

17. Nel riquadro azioni, selezionare la scheda **Importazione**. Si noti che il pulsante **Aggiorna da PDF** è diventato disponibile per l'elemento di formato selezionato **File PDF**.

    È possibile utilizzare questo pulsante per importare un modello PDF aggiornato nel formato modificato. Quando il modello PDF aggiornato viene importato, l'elenco degli elementi di formato verrà modificato di conseguenza:

    - Per tutti i nuovi campi del modello PDF aggiornato, i nuovi elementi di formato vengono creati nel formato ER modificato.
    - Se il modello PDF aggiornato non include più campi che corrispondono a elementi di formato esistenti nel formato ER modificato, tali elementi di formato vengono eliminati dal formato ER.

18. Nella scheda **Formato**, selezionare **Allegati**.

    Si noti che il documento PDF importato è allegato al formato ER modificato.

    ![Anteprima allegato PDF.](media/rcs-ger-filloutpdf-attachedtemplate.png)

19. Continuare a progettare questo formato importando il secondo modello PDF, aggiungendo i collegamenti necessari alle origini dati e così via.
20. Selezionare **Salva**.
21. Chiudere la pagina.
22. Selezionare **Elimina**.
23. Selezionare **Sì**.

Per informazioni su come i nuovi elementi di formato **Unione PDF**, **File PDF**, **Gruppo campi** e **Campo** possono essere utilizzati per generare i documenti in formato PDF, è possibile importare e analizzare il formato di ER di esempio.

### <a name="import-the-format-configuration"></a>Importare la configurazione del formato

A questo punto, verranno importati il formato ER di esempio in precedenza scaricato per generare il report **Controllo Intrastat** in formato PDF. La prima pagina del report deve mostrare un riepilogo del report e i dettagli delle transazioni per il commercio estero dichiarate. Le altre pagine devono mostrare solo i dettagli delle transazioni del commercio estero dichiarate.

1. Nella pagina **Configurazioni**, selezionare **Scambia \> Carica da file XML**.
2. Selezionare **Sfoglia**. Passare al file **Intrastat report (PDF).version.1.1.xml** scaricato in precedenza come prerequisito e selezionarlo.
3. Selezionare **OK**.

## <a name="analyze-the-format-configuration"></a>Analizzare la configurazione del formato

### <a name="format-layout"></a>Layout del formato

1. Nella pagina **Configurazioni**, nella struttura selezionare **Modello Intrastat \> Report Intrastat (PDF)**.
2. Selezionare **Designer**.
3. Selezionare **Mostra dettagli**.
4. Nella struttura espandere **Output: PDF Merger**.

    Si noti che il formato ER contiene due elementi **File PDF**, ciascuno dei quali utilizza un modello PDF diverso. Un modello viene utilizzato per generare la prima pagina del report in formato PDF e un altro per generare le altre pagine.

5. Nella struttura espandere **Output: Unione PDF \> Pagina 1: file PDF (IntrastatReportTemplate1)**.
6. Nella struttura espandere **Output: Unione PDF \> Pagina N.: file PDF (IntrastatReportTemplate2)**.

    Si noti che, poiché il contenuto dei due modelli PDF differisce, anche la struttura degli elementi di formato nidificati per i due elementi **File PDF** differisce.

### <a name="format-mapping"></a>Mapping formato

1. Nella pagina **Progettazione formati** selezionare la scheda **Mapping**.
2. Nella struttura espandere **Paging \> Pagine**.

    ![Finestra di progettazione formule in cui viene espanso l'albero del modello.](media/rcs-ger-filloutpdf-reviewformat.png)

    Considerare i seguenti dettagli:

    - L'elemento di formato **Output \> Pagina 1** del tipo di **File PDF** non è limitato ad alcuna origine dati e l'espressione **Abilitato** di questo elemento di formato è vuota. Di conseguenza, in fase di esecuzione, il modello PDF **IntrastatReportTemplate1** verrà compilato una sola volta quando viene generato un singolo documento PDF.
    - L'elemento di formato **Output \> Pagina N** del tipo di **File PDF** è limitato all'origine dati **Paging.PageN** del tipo **Elenco di record** e l'espressione **Abilitato** di questo elemento di formato è vuota. Di conseguenza, in fase di esecuzione, il modello PDF **IntrastatReportTemplate2** verrà compilato per ciascun record dall'elenco dei record associati quando viene generato un singolo documento PDF.
    - Poiché gli elementi di formato **Pagina 1: file PDF** e **Pagina N: file PDF** sono i figli dell'elemento di formato **Output: unione PDF**, tutti i documenti PDF che vengono compilati vengono uniti in un unico documento PDF finale.
    - Le origini dati **Paging.Page1** e **Paging.PageN** vengono configurate come filtri di record dall'origine dati **Paging.Pages**. Questa origine dati è configurata per suddividere l'intero set di tutte le transazioni del commercio estero in batch. Ogni batch contiene un massimo di 42 record. La seguente espressione ER viene utilizzata per suddividere le transazioni in batch:

        SPLITLIST(Totals.CommodityRecord,42)

    - L'origine dati **Paging.Pages** contiene l'elemento **Paging.Pages.Enumerated** che restituisce i dettagli di ciascun record incluso in un batch. Queste informazioni includono la sequenza del record nel batch corrente (il campo **Paging.Pages.Enumerated.Number**). Il campo **Paging.Pages.Enumerated.Number** viene utilizzato nell'espressione **Nome** di elementi di formato **Campo PDF** per generare in modo dinamico il nome di un campo in base al numero di transazione in un batch. Il nome del campo generato verrà utilizzato quindi per compilare il campo PDF corretto nel modello PDF utilizzato.
    - L'elemento di formato **Output \> Pagina N \> Dettagli 2** del tipo **Gruppo PDF** è limitato all'origine dati **Paging.PageN.Enumerated** (o **\@.Enumerated** se viene utilizzata la modalità di visualizzazione **Percorso relativo**) del tipo **Elenco di record**. Di conseguenza, in fase di esecuzione, gli elementi nidificati di questo gruppo PDF verranno compilati per ciascun record dall'elenco dei record associati. In questo modo, le singole righe PDF vengono virtualmente generate quando per ogni N° di 42 record dell'elenco **Paging.PageN.Enumerated** vengono compilati i seguenti campi PDF: data N, direzione N, voce doganale N e così via. Pertanto , a questo proposito, il comportamento di questo elemento di formato **Gruppo di campi** è simile al comportamento di elementi di formato **XML \> Sequenza** e **Testo \> Sequenza**.

3. Nella struttura espandere **Output \> Pagina N \> Details2**.
4. Nella struttura selezionare **Output \> Pagina N \> Details2 \> PageFooter**.

    Si noti che l'attributo **Nome** dell'elemento di formato è definito come **PageFooter**. Si noti che l'espressione **Nome** dell'elemento di formato è vuota.

5. Nella struttura selezionare **Output \> Pagina N \> Details2 \> Correction 1**.

    Si noti che l'attributo **Nome** dell'elemento di formato è definito come **Correction 1**. Si noti che l'espressione **Nome** dell'elemento di formato è definita come **Paging.FldName("Correction",\@.Number)**.

![Progettazione formati in cui viene selezionato un mapping.](media/rcs-ger-filloutpdf-reviewformat2.png)

Si noti che l'elemento di formato **Field** viene utilizzato per compilare un singolo campo di un documento PDF compilabile definito come modello dell'elemento padre **File PDF**. L'associazione dell'elemento di formato **File PDF** o dei suoi elementi nidificati, se ne contiene, specifica il valore inserito nei campi PDF corrispondenti. Le diverse proprietà dell'elemento di formato **Campo** possono essere utilizzate per specificare quale campo PDF viene compilato da un singolo elemento di formato:

- Nella scheda **Formato**, l'attributo **Nome** dell'elemento di formato
- Nella scheda **Mapping**, l'espressione **Nome** dell'elemento di formato

Poiché entrambe le proprietà sono facoltative per un elemento di formato **Campo**, vengono applicate le seguenti regole per specificare il campo PDF di destinazione:

- Se l'attributo **Nome** è vuoto e l'espressione **Nome** restituisce una stringa vuota in fase di esecuzione, viene generata un'eccezione in fase di esecuzione per notificare all'utente che non è possibile trovare un campo PDF nel modello PDF utilizzato per compilare il documento PDF.
- Se l'attributo **Nome** è definito e l'espressione **Nome** è vuota, viene compilato il campo PDF che ha lo stesso nome dell'attributo **Nome** dell'elemento formato.
- Se l'attributo **Nome** è definito e l'espressione **Nome** è configurata, viene compilato il campo PDF che ha lo stesso nome del valore restituito dall'espressione **Nome** dell'elemento di formato.

> [!NOTE]
> Una casella di controllo PDF può essere compilata come selezionata nei seguenti modi:
>
> - Quando l'elemento di formato **Campo** corrispondente viene associato a un campo di origine dati di tipo **Booleano** con valore **True**
> - Quando l'elemento di formato **Campo** corrispondente contiene un elemento di formato **Stringa** nidificato associato a un campo di origine dati con un valore di testo di **1**, **True** o **Sì**

## <a name="run-the-format-configuration"></a>Eseguire la configurazione di formato

### <a name="import-the-format-configuration"></a>Importare la configurazione del formato

A questo punto, si caricherà il formato di ER di esempio **Intrastat (import from Excel)**. Questo formato è progettato per analizzare una cartella di lavoro Microsoft Excel selezionata dall'utente che simula le transazioni del commercio estero.

1. Nella pagina **Configurazioni**, selezionare **Scambia \> Carica da file XML**.
2. Selezionare **Sfoglia**. Passare al file **Intrastat (import from Excel).version.1.1.xml** scaricato in precedenza come prerequisito e selezionarlo.
3. Selezionare **OK**.
4. Nella struttura selezionare **Modello Intrastat \> Intrastat (import from Excel)**.
5. Selezionare **Modifica**.
6. Impostare l'opzione **Impostazione predefinita per mapping di modello** su **Sì**.

    > [!NOTE]
    > Se in precedenza è stata impostata l'opzione **Impostazione predefinita per mapping di modello** su **Sì** per la configurazione del **Modello Intrastat** o per un'altra configurazione nidificata nel **modello Intrastat**, impostare questa opzione su **No**.

    Quando l'opzione **Impostazione predefinita per mapping di modello** è impostata su **Sì**, il formato ER **Intrastat (import from Excel)** importato viene assegnato come origine dati predefinita per la configurazione di formato **Report Intrastat (PDF)**. Quindi, quando viene eseguita la configurazione del formato **Report Intrastat (PDF)**, il contenuto della cartella di lavoro di Excel analizzata dal formato ER **Intrastat (import from Excel)** simulerà le transazioni di commercio estero per cui deve essere creato il report. Nella figura seguente viene illustrato un esempio di una cartella di lavoro di Excel.

    ![Cartella di lavoro di Excel con dati di esempio.](media/rcs-ger-filloutpdf-excelworkbook.png)

### <a name="run-the-format-configuration"></a>Eseguire la configurazione di formato

1. Nella pagina **Configurazioni**, nella struttura selezionare **Modello Intrastat \> Report Intrastat (PDF)**.
2. Selezionare **Esegui**.
3. Selezionare **Sfoglia**. Passare al file **Intrastat sample data.xlsx** scaricato in precedenza come prerequisito e selezionarlo.
4. Selezionare **OK**.
5. Nel campo **Direzione report** selezionare **Entrambe** per compilare tutte le transazioni dalla cartella di lavoro Excel importata nel report PDF che viene generato.
6. Selezionare **OK**.
7. Esaminare il documento PDF che viene generato.

L'illustrazione seguente mostra un esempio della prima pagina del report generato.

![Prima pagina del report generato.](media/rcs-ger-filloutpdf-generatedreport.png)

L'illustrazione seguente mostra un esempio di un'altra prima pagina del report generato.

![Altra pagina del report generato.](media/rcs-ger-filloutpdf-generatedreport2.png)

## <a name="limitations"></a>Limiti

I nomi dei campi compilabili devono essere univoci nel modulo PDF che intendi utilizzare come modello di report. Per ciascuno di questi campi, al momento dell'importazione di un modulo PDF viene creato un elemento di formato individuale con il nome corrispondente nel formato ER modificabile. Se un modulo PDF contiene più campi con lo stesso nome, viene creato un unico elemento di formato per i campi che non consente la loro compilazione individualmente in fase di esecuzione.

## <a name="frequently-asked-questions"></a>Domande frequenti

### <a name="when-i-run-the-er-format-to-generate-a-report-in-pdf-format-why-do-i-get-the-following-errors--cannot-handle-iref-streams-the-current-implementation-of-pdfsharp-cannot-handle-this-pdf-feature-introduced-with-acrobat-6-and-a-pdf-name-must-start-with-a-slash-"></a>Quando eseguo il formato ER per generare un report in formato PDF, perché ottengo i seguenti errori: **Impossibile gestire i flussi iref. L'attuale implementazione di PDFSharp non è in grado di gestire questa funzionalità PDF introdotta con Acrobat 6.** e **Un nome PDF deve iniziare con una barra (/).**

Il framework ER utilizza la versione 1.5 della raccolta PDFSharp per generare questi report PDF. Alcune funzionalità di PDF 1.5 (Adobe Reader 6.0) non sono ancora implementati in questa libreria. Pertanto, PDFSharp non può ancora aprire alcuni file contrassegnati come **per PDF 1.5 o versioni successive** e può causare gli errori ricevuti. Usa una delle seguenti soluzioni per risolvere il problema:

-   Quando utilizzi il tuo modello PDF: esegui il downgrade del modello a una versione di Adobe precedente e inizia a utilizzare un nuovo modello nel tuo formato ER.
-   Quando utilizzi un modello di formato ER che è stato condiviso con te da un altro provider di configurazione come parte di una soluzione ER: contatta il proprietario di questa soluzione ER e fornisci una descrizione del problema.
-   Quando si utilizza la soluzione ISV che contiene una versione precedente della libreria PDFSharp: contattare il proprietario della soluzione e suggerire un aggiornamento alla versione più recente di PDFSharp.

## <a name="additional-resources"></a>Risorse aggiuntive

- [ER Progettare una configurazione per la creazione di report nel formato OPENXML (novembre 2016)](tasks/er-design-reports-openxml-2016-11.md)
- [Progettare le configurazioni di ER per generare report in formato di Word](tasks/er-design-configuration-word-2016-11.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
