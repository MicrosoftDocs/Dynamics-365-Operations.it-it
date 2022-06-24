---
title: Differire l'esecuzione di elementi di sequenza in formati ER
description: Questo articolo spiega come differire l'esecuzione di un elemento di sequenza in un formato ER.
author: NickSelin
ms.date: 04/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EROperationDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 58771
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-07-01
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: 5d4c5395c87c7bdc874f277a691e84081f68742d
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8880241"
---
# <a name="defer-the-execution-of-sequence-elements-in-er-formats"></a>Differire l'esecuzione di elementi di sequenza in formati ER

[!include [banner](../includes/banner.md)]

## <a name="overview"></a>Panoramica

È possibile utilizzare Designer operazioni del framework di [Creazione di report elettronici (ER)](general-electronic-reporting.md) per [configurare](tasks/er-format-configuration-2016-11.md) il componente di formato di una soluzione ER utilizzata per generare documenti in uscita in un formato testo. La struttura gerarchica del componente di formato configurato è costituita da elementi di formato di vari tipi. Questi elementi di formato vengono utilizzati per riempire i documenti generati con le informazioni necessarie in fase di esecuzione. Per impostazione predefinita, quando si esegue un formato ER, gli elementi del formato vengono eseguiti nello stesso ordine in cui sono presentati nella gerarchia dei formati: uno per uno, dall'alto verso il basso. Tuttavia, in fase di progettazione, è possibile modificare l'ordine di esecuzione di qualsiasi elemento di sequenza del componente di formato configurato.

Attivando l'opzione <a name="DeferredSequenceExecution"></a>**Esecuzione differita** per un elemento di formato sequenza nel formato configurato, è possibile differire (posticipare) l'esecuzione di quell'elemento. In questo caso, l'elemento non viene eseguito finché non vengono eseguiti tutti gli altri elementi dell'elemento padre.

Per ulteriori informazioni su questa funzionalità, completa l'esempio in questo articolo.

## <a name="limitations"></a>Limiti

L'opzione **Esecuzione differita** è supportata solo per gli elementi di sequenza configurati per un formato ER utilizzato per generare documenti **in uscita** in un formato di testo.

L'opzione **Esecuzione differita** non è applicabile alle sequenze che sono state configurate come sequenze ritagliate in cui la lunghezza massima è limitata.

## <a name="example-defer-the-execution-of-a-sequence-element-in-an-er-format"></a><a name="Example"></a>Esempio: differire l'esecuzione di un elemento di sequenza in un formato ER

I seguenti passaggi spiegano come un utente con [ruolo](../sysadmin/tasks/assign-users-security-roles.md) di amministratore di sistema o consulente funzionale per la creazione di report elettronici può configurare un formato ER che contiene un elemento un elemento di sequenza in cui l'ordine di esecuzione differisce dall'ordine nella gerarchia dei formati.

Queste operazioni possono essere eseguite nella società fittizia **USMF** in Microsoft Dynamics 365 Finance.

### <a name="prerequisites"></a>Prerequisiti

Per completare l'esempio in questo argomento, è necessario avere accesso alla società **USMF** in Finance per uno dei seguenti ruoli:

- Consulente funzionale per la creazione di report elettronici
- Amministratore di sistema

Se l'esempio nell'articolo [Differire l'esecuzione di elementi XML in formati ER](er-defer-xml-element.md#Example) non è ancora stato completato, scarica le seguenti [configurazioni](general-electronic-reporting.md#Configuration) della soluzione ER di esempio.

| Descrizione contenuto            | Nome file |
|--------------------------------|-----------|
| Configurazione del modello di dati ER    | [Model to learn deferred elements.version.1.xml](https://download.microsoft.com/download/7/6/0/760933ca-4ac3-4f50-bc0c-c35e596ee066/Modeltolearndeferredelements.version.1.xml) |
| Configurazione del mapping di modello ER | [Mapping to learn deferred elements.version.1.1.xml](https://download.microsoft.com/download/c/9/c/c9c4b9dd-b700-4385-a087-a84ce9fc1d0f/Mappingtolearndeferredelements.version.1.1.xml) |

Prima di iniziare, è inoltre necessario scaricare e salvare la seguente configurazione della soluzione ER di esempio.

| Descrizione contenuto     |Nome file |
|-------------------------|----------|
| Configurazione di formato ER | [Format to learn deferred sequences.version.1.1.xml](https://download.microsoft.com/download/0/f/5/0f55c341-8285-4d92-a46d-475d9a010927/Formattolearndeferredsequences.version.1.1.xml) |

### <a name="import-the-sample-er-configurations"></a>Importare le configurazioni ER di esempio

1. Andare a **Amministrazione organizzazione** \> **Aree di lavoro** \> **Creazione di report elettronici**.
2. Selezionare **Configurazioni report**.
3. Nella pagina **Configurazioni**, se la configurazione **Modello di apprendimento di elementi differiti** non è disponibile nella struttura delle configurazioni, importare la configurazione del modello di dati ER.

    1. Selezionare **Scambia**, quindi selezionare **Carica da file XML**.
    2. Selezionare **Sfoglia**, trovare e selezionare il file **Model to learn deferred elements.1.xml**, quindi selezionare **OK**.

4. Se la configurazione **Mapping di apprendimento di elementi differiti** non è disponibile nella struttura delle configurazioni, importare la configurazione del mapping di modello ER.

    1. Selezionare **Scambia**, quindi selezionare **Carica da file XML**.
    2. Selezionare **Sfoglia**, trovare e selezionare il file **Mapping to learn deferred XML elements.1.1.xml**, quindi selezionare **OK**.

5. Importare la configurazione del formato ER:

    1. Selezionare **Scambia**, quindi selezionare **Carica da file XML**.
    2. Selezionare **Sfoglia**, trovare e selezionare il file **Format to learn deferred sequences.1.1.xml**, quindi selezionare **OK**.

6. Nella struttura delle configurazioni, espandere **Modello di apprendimento di elementi differiti**.
7. Esaminare l'elenco delle configurazioni ER importate nella struttura delle configurazioni.

    ![Configurazioni ER importate nella pagina Configurazioni.](./media/ER-DeferredSequence-Configurations.png)

### <a name="activate-a-configurations-provider"></a>Attivare un provider di configurazioni

1. Andare a **Amministrazione organizzazione** \> **Aree di lavoro** \> **Creazione di report elettronici**.
2. Nella pagina **Configurazioni localizzazione**, nella sezione **Provider di configurazione**, verificare che il [provider di configurazione](general-electronic-reporting.md#Provider) per la società di esempio Litware, Inc. (`http://www.litware.com`) sia elencato e contrassegnato come attivo. Se questo provider di configurazione non è elencato o non è contrassegnato come attivo, completa i passaggi dell'articolo [Creare un provider di configurazione e contrassegnarlo come attivo](./tasks/er-configuration-provider-mark-it-active-2016-11.md).

    ![La società di esempio Litware, Inc. nella pagina Configurazioni localizzazione.](./media/ER-DeferredSequence-ElectronicReportingWorkspace.png)

### <a name="review-the-imported-model-mapping"></a>Esaminare il mapping di modello importato

Esaminare le impostazioni del componente mapping di modello ER configurato per accedere alle transazioni fiscali ed esporre i dati consultati su richiesta.

1. Andare a **Amministrazione organizzazione** \> **Aree di lavoro** \> **Creazione di report elettronici**.
2. Selezionare **Configurazioni report**.
3. Nella pagina **Configurazioni**, nella struttura delle configurazioni, espandere **Modello di apprendimento di elementi differiti**.
4. Selezionare la configurazione **Mapping di apprendimento di elementi differiti**.
5. Selezionare **Progettazione** per aprire l'elenco dei mapping.
6. Selezionare **Progettazione** per esaminare i dettagli dei mapping.
7. Selezionare **Mostra dettagli**.
8. Esaminare le origini dati configurate per accedere alle transazioni fiscali:

    - L'origine dati **Transazioni** di tipo *Record tabella* è configurata per accedere ai record della tabella dell'applicazione **TaxTrans**.
    - L'origine dati **Giustificativi** di tipo *Campo calcolato* è configurata per restituire i codici giustificativi richiesti (**INV-10000349** e **INV-10000350**) come elenco di record.
    - L'origine dati **Filtrate** di tipo *Campo calcolato* è configurato per selezionare dall'origine dati **Transazioni** solo le transazioni fiscali dei giustificativi richiesti.
    - Il campo **\$TaxAmount** di tipo *Campo calcolato* viene aggiunto all'origine dati **Filtrate** per esporre il valore di imposta di segno opposto.
    - L'origine dati **Raggruppate** di tipo *GroupBy* è configurata per raggruppare le transazioni fiscali filtrate dell'origine dati **Filtrate**.
    - Il campo di aggregazione **TotalSum** dell'origine dati **Raggruppate** è configurata per riepilogare i valori del campo **\$TaxAmount** dell'origine dati **Filtrate** per tutte le transazioni fiscali filtrate di quell'origine dati.

        ![Campo di aggregazione TotalSum nella pagina di modifica dei parametri "GroupBy".](./media/ER-DeferredSequence-GroupByParameters.png)

9. Verificare in che modo le origini dati configurate sono associate al modello di dati e come espongono i dati consultati per renderli disponibili in un formato ER:

    - L'origine dati **Filtrate** è associata al campo **Data.List** del modello di dati.
    - Il campo **\$TaxAmount** dell'origine dati **Filtrate** è associata al campo **Data.List.Value** del modello di dati.
    - Il campo **TotalSum** dell'origine dati **Raggruppate** è associato al campo **Data.Summary.Total** del modello di dati.

    ![Pagina Progettazione mapping modello.](./media/ER-DeferredSequence-ModelMapping.png)

10. Chiudere le pagine **Progettazione mapping modello** e **Mapping modello**.

### <a name="review-the-imported-format"></a>Esaminare il formato importato

1. Nella pagina **Configurazioni**, nella struttura delle configurazioni, selezionare la configurazione **Formato per ottenere sequenze differite**.
2. Selezionare **Progettazione** per esaminare i dettagli del formato.
3. Selezionare **Mostra dettagli**.
4. Verificare le impostazioni dei componenti di formato ER configurate per generare un documento in uscita in un formato di testo che include i dettagli delle transazioni fiscali:

    - L'elemento di formato sequenza **Report\\Lines** è configurato per riempire il documento in uscita con una singola riga generata a partire dagli elementi di sequenza nidificati (**Header**, **Record**, and **Summary**).

        ![Elemento di formato sequenza Lines ed elementi nidificati nella pagina Progettazione formati.](./media/ER-DeferredSequence-Format.png)

    - L'elemento di formato sequenza **Report\\Lines\\Header** è configurato per riempire il documento in uscita con una singola riga di intestazione che mostra la data e l'ora di inizio dell'elaborazione.
    - L'elemento di formato sequenza **Report\\Lines\\Record** è configurato per riempire il documento in uscita con una singolo riga che mostra i dettagli delle singole transazioni fiscali. Queste transazioni fiscali sono separate da un punto e virgola.

        ![Elemento di formato sequenza Record che utilizza un punto e virgola come delimitatore.](./media/ER-DeferredSequence-Format1.png)

    - L'elemento di formato sequenza **Report\\Lines\\Summary** è configurato per riempire il documento in uscita con una singolo riga di riepilogo che include la somma dei valori di imposta delle transazioni fiscali elaborate.

4. Nella scheda **Mappatura**, esaminare i seguenti dettagli:

    - L'elemento **Report\\Lines\\Header** non deve essere associato a un'origine dati per generare una singola riga in un documento in uscita.
    - L'elemento **Prefix1** genera simboli **P1** per indicare che la riga aggiunta è la riga di intestazione del report.
    - L'elemento **ExecutionDateTime** genera la data e l'ora (inclusi i millisecondi) in cui viene aggiunta la riga di intestazione.
    - L'elemento **Report\\Lines\\Record** è associato all'elenco **model.Data.List** per generare una singolo riga per ogni record dell'elenco associato.
    - L'elemento **Prefix2** genera simboli **P2** per indicare che la riga aggiunta è per i dettagli delle transazioni fiscali.
    - L'elemento **TaxAmount** è associato a **model.Data.List.Value** (visualizzato come **\@.Value** nella vista percorso relativa) per generare il valore di imposta della transazione fiscale corrente.
    - L'elemento **RunningTotal** è un segnaposto per il totale corrente dei valori di imposta. Attualmente, questo elemento non ha output, perché nessun valore di binding o predefinito è configurato per lo stesso.
    - L'elemento **ExecutionDateTime** genera la data e l'ora (inclusi i millisecondi) in cui viene la transazione corrente viene elaborata in questo report.
    - L'elemento **Report\\Lines\\Summary** non deve essere associato a un'origine dati per generare una singola riga in un documento in uscita.
    - L'elemento **Prefix3** genera simboli **P3** per indicare che la riga aggiunta contiene il valore di imposta totale.
    - L'elemento **TotalTaxAmount** è associato a **model.Data.Summary.Total** per generare la somma dei valori di imposta delle transazioni fiscali elaborate.
    - L'elemento **ExecutionDateTime** genera la data e l'ora (inclusi i millisecondi) in cui viene aggiunta la riga di riepilogo.

    ![Scheda Mapping nella pagina Progettazione formati.](./media/ER-DeferredSequence-Format2.png)

### <a name="run-the-imported-format"></a>Eseguire il formato importato

1. Nella pagina **Progettazione formati**, selezionare **Esegui**.
2. Scaricare il file proposto dal browser Web e aprirlo per esaminarlo.

    ![File di report di esempio scaricato.](./media/ER-DeferredSequence-Run.png)

Si noti che la riga di riepilogo 22 presenta la somma dei valori di imposta per le transazioni elaborate. Poiché il formato è configurato per utilizzare il binding **model.Data.Summary.Total** per restituire questa somma, la somma viene calcolata chiamando l'aggregazione **TotalSum** dell'origine dati **Raggruppate** di tipo *GroupBy* che utilizza il mapping di modello. Per calcolare questa aggregazione, il mapping di modello esegue l'iterazione su tutte le transazioni che sono state selezionate nell'origine dati **Filtrate**. Confrontando i tempi di esecuzione delle righe 21 e 22, è possibile determinare che il calcolo della somma ha richiesto 10 millisecondi (ms). Confrontando i tempi di esecuzione delle righe 2 e 21, è possibile determinare che la generazione di tutte le righe transazionali ha richiesto 7 millisecondi (ms). Pertanto, sono stati necessari in totale 17 ms.

### <a name="modify-the-format-so-that-the-summing-is-based-on-generated-output"></a>Modificare il formato di modo che la somma si basi sull'output generato

Se il volume delle transazioni è molto più grande del volume nell'esempio corrente, il tempo necessario per effettuare la somma potrebbe aumentare e causare problemi di prestazioni. Modificando l'impostazione del formato, è possibile prevenire questi problemi di prestazioni. Poiché si accede ai valori di imposta per includerli nel report generato, è possibile riutilizzare queste informazioni per sommare i valori di imposta. Per ulteriori informazioni, vedere [Configurare il formato per eseguire il conteggio e la sommatoria](./tasks/er-format-counting-summing-1.md).

1. Nella pagina **Progettazione formati**, nella scheda **Formato** selezionare l'elemento di file **Report** nella struttura dei formati.
2. Impostare l'opzione **Raccogli dettagli di output** su **Sì**. È ora possibile configurare questo formato utilizzando il contenuto di un report esistente come origine dati a cui è possibile accedere utilizzando le funzioni ER integrate nella categoria [Raccolta dati](er-functions-category-data-collection.md).
3. Nella scheda **Mapping**, selezionare l'elemento di sequenza **Report\\Lines**.
4. Configurare l'espressione **Nome chiave dati raccolti** come `WsColumn`.
5. Configurare l'espressione **Valore chiave dati raccolti** come `WsRow`.

    ![Elemento di sequenza Lines nella pagina Progettazione formati.](./media/ER-DeferredSequence-Format3.png)

6. Selezionare l'elemento numerico **Report\\Lines\\Record\\TaxAmount**.
7. Configurare l'espressione **Nome chiave dati raccolti** come `SummingAmountKey`.

    ![Elemento numerico TaxAmount nella pagina Progettazione formati.](./media/ER-DeferredSequence-Format4.png)

    È possibile considerare questa impostazione come la creazione di un foglio di lavoro virtuale, in cui il valore della cella A1 viene aggiunto al valore dell'importo fiscale di ogni transazione fiscale elaborata.

8. Selezionare l'elemento numerico **Report\\Lines\\Record\\RunningTotal** e quindi selezionare **Modifica formula**.
9. Configurare l'espressione `SUMIF(SummingAmountKey, WsColumn, WsRow)` usando la funzione ER [SUMIF](er-functions-datacollection-sumif.md) integrata.
10. Selezionare **Salva**.

    ![Espressione SUMIF.](./media/ER-DeferredSequence-FormulaDesigner.png)

11. Chiudere la pagina **Designer formula**.
12. Selezionare **Salva** e quindi selezionare **Esegui**.
13. Scaricare ed esaminare il file proposto dal browser Web.

    ![File scaricato: somma dei valori di imposta.](./media/ER-DeferredSequence-Run1.png)

    La riga 21 contiene il totale corrente dei valori di imposta calcolato per tutte le transazioni elaborate utilizzando l'output generato come origine dati. Questa origine dati comincia all'inizio del report e continua fino all'ultima transazione fiscale. La riga 22 contiene la somma dei valori di imposta di tutte le transazioni elaborate calcolate nel mapping di modello utilizzando l'origine dati di tipo *GroupBy*. Si noti che questi valori sono uguali. Pertanto, è possibile utilizzare la somma basata sull'output al posto di **GroupBy**. Confrontando i tempi di esecuzione delle righe 2 e 21, è possibile determinare che la generazione di tutte le righe transazionali e della somma ha richiesto 9 millisecondi (ms). Pertanto, per quanto riguarda la generazione di righe dettagliate e della somma dei valori di imposta, il formato modificato è circa due volte più veloce del formato originale.

14. Selezionare l'elemento numerico **Report\\Lines\\Summary\\TotalTaxAmount** e quindi selezionare **Modifica formula**.
15. Immettere l'espressione `SUMIF(SummingAmountKey, WsColumn, WsRow)` anziché l'espressione esistente.
16. Selezionare **Salva** e quindi selezionare **Esegui**.
17. Scaricare ed esaminare il file proposto dal browser Web.

    ![File scaricato con formula modificata.](./media/ER-DeferredSequence-Run2.png)

    Si noti che il totale corrente dei valori di imposta nell'ultima riga dei dettagli delle transazioni è ora uguale alla somma nella riga di riepilogo.

### <a name="put-values-of-output-based-summing-in-the-report-header"></a>Inserire i valori della somma basata su output nell'intestazione del report

Se, ad esempio, è necessario presentare la somma dei valori di imposta nell'intestazione del report, è possibile modificare il formato.

1. Nella pagina **Progettazione formati**, nella scheda **Formato** selezionare l'elemento di sequenza **Report\\Lines\\Summary**.
2. Selezionare **Sposta su**.
3. Selezionare **Salva** e quindi selezionare **Esegui**.
4. Scaricare ed esaminare il file proposto dal browser Web.

    ![File scaricato per la somma nell'intestazione del report.](./media/ER-DeferredSequence-Run3.png)

    Si noti che la somma dei valori di imposta nella riga di riepilogo 2 è ora uguale a 0 (zero), poiché questa somma viene ora calcolata in base all'output generato. Quando viene generata la riga 2, l'output generato non contiene ancora righe che hanno dettagli delle transazioni. È possibile configurare questo formato per differire l'esecuzione dell'elemento di sequenza **Report\\Lines\\Summary** fino a che l'elemento di sequenza **Report\\Lines\\Record** non è stato eseguito per tutte le transazioni fiscali.

### <a name="defer-the-execution-of-the-summary-sequence-so-that-the-calculated-total-is-used"></a>Differire l'esecuzione della sequenza di riepilogo in modo che venga utilizzato il totale calcolato

1. Nella pagina **Progettazione formati**, nella scheda **Formato** selezionare l'elemento di sequenza **Report\\Lines\\Summary**.
2. Impostare l'opzione **Esecuzione differita** su **Sì**.

    ![Opzione Esecuzione differita dell'elemento di sequenza Summary nella pagina Progettazione formati.](./media/ER-DeferredSequence-Format5.png)

3. Selezionare **Salva** e quindi selezionare **Esegui**.
4. Scaricare ed esaminare il file proposto dal browser Web.

    ![File scaricato - esecuzione differita.](./media/ER-DeferredSequence-Run4.png)

    L'elemento di sequenza **Report\\Lines\\Summary** viene ora eseguito solo dopo l'esecuzione di tutti gli altri elementi nidificati sotto l'elemento padre **Report\\Lines**. Pertanto, viene eseguito dopo l'esecuzione dell'elemento di sequenza **Report\\Lines\\Record** per tutte le transazioni fiscali dell'origine dati **model.Data.List**. I tempi di esecuzione delle righe 1, 2 e 3 e dell'ultima riga, 22, rivelano questa condizione.

## <a name="additional-resources"></a>Risorse aggiuntive

- [Configurare il formato per eseguire il conteggio e la sommatoria](./tasks/er-format-counting-summing-1.md)
- [Generare la traccia dell'esecuzione del formato ER per risolvere problemi relativi alle prestazioni](trace-execution-er-troubleshoot-perf.md)
- [Differire l'esecuzione di elementi XML in formati ER](er-defer-xml-element.md#Example)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
