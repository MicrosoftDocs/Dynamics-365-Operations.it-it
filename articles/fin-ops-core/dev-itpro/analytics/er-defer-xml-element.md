---
title: Differire l'esecuzione di elementi XML in formati ER
description: Questo argomento spiega come differire l'esecuzione di un elemento XML in un formato ER.
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
ms.search.validFrom: 2020-01-01
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: afe0f9945d86c0c7da88b427f582483ed38a54db837818c3e63c5ae2cc60cfbb
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6718383"
---
# <a name="defer-the-execution-of-xml-elements-in-er-formats"></a>Differire l'esecuzione di elementi XML in formati ER

[!include [banner](../includes/banner.md)]

## <a name="overview"></a>Panoramica

È possibile utilizzare Designer operazioni del framework di [creazione di report elettronici (ER)](general-electronic-reporting.md)per [configurare](./tasks/er-format-configuration-2016-11.md) il [componente di formato](general-electronic-reporting.md#FormatComponentOutbound) di una soluzione ER utilizzata per generare documenti in uscita in formato XML. La struttura gerarchica del componente di formato configurato è costituita da elementi di formato di vari tipi. Questi elementi di formato vengono utilizzati per riempire i documenti generati con le informazioni necessarie in fase di esecuzione. Per impostazione predefinita, quando si esegue un formato ER, gli elementi del formato vengono eseguiti nello stesso ordine in cui sono presentati nella gerarchia dei formati: uno per uno, dall'alto verso il basso. Tuttavia, in fase di progettazione, è possibile modificare l'ordine di esecuzione di qualsiasi elemento XML del componente di formato configurato.

Attivando l'opzione <a name="DeferredXmlElementExecution"></a>**Esecuzione differita** per un elemento XML nel formato configurato, è possibile differire (posticipare) l'esecuzione di quell'elemento. In questo caso, l'elemento non viene eseguito finché non vengono eseguiti tutti gli altri elementi dell'elemento padre.

Per ulteriori informazioni su questa funzionalità, completare l'esempio in questo argomento.

## <a name="limitations"></a>Limiti

L'opzione **Esecuzione differita** è supportata solo per gli elementi XML configurati per un formato ER utilizzato per generare documenti **in uscita** in formato XML.

L'opzione **Esecuzione differita** è supportata solo per gli elementi XML che risiedono in un solo altro elemento XML. Pertanto, non è applicabile agli elementi XML che risiedono in altri tipi di elementi di formato (ad esempio, in un elemento **Sequenza XML**).

L'opzione **Esecuzione differita** non è supportata per elementi XML che si trovano nell'elemento di formato **Common\\File** quando l'opzione **Dividi file** è impostata su **Sì**. Per ulteriori informazioni su come dividere file XML, vedere [Dividere i file XML generati in base alla dimensione del file e alla quantità del contenuto](er-split-files.md).

## <a name="example-defer-the-execution-of-an-xml-element-in-an-er-format"></a><a name="Example"></a>Esempio: Differire l'esecuzione di un elemento XML in un formato ER

I seguenti passaggi spiegano come un utente con [ruolo](../sysadmin/tasks/assign-users-security-roles.md) di amministratore di sistema o consulente funzionale per la creazione di report elettronici può configurare un formato ER che contiene un elemento XML in cui l'ordine di esecuzione differisce dall'ordine nella gerarchia dei formati.

Queste operazioni possono essere eseguite nella società fittizia **USMF** in Microsoft Dynamics 365 Finance.

### <a name="prerequisites"></a>Prerequisiti

Per completare l'esempio in questo argomento, è necessario avere accesso alla società **USMF** in Finance per uno dei seguenti ruoli:

- Consulente funzionale per la creazione di report elettronici
- Amministratore di sistema

Se l'esempio nell'argomento [Differire l'esecuzione di elementi di sequenza in formati ER](er-defer-sequence-element.md#Example) non è ancora stato completato, scaricare le seguenti [configurazioni](general-electronic-reporting.md#Configuration) della soluzione ER di esempio.

| Descrizione contenuto            | Nome file |
|--------------------------------|-----------|
| Configurazione del modello di dati ER    | [Model to learn deferred elements.version.1.xml](https://download.microsoft.com/download/7/6/0/760933ca-4ac3-4f50-bc0c-c35e596ee066/Modeltolearndeferredelements.version.1.xml) |
| Configurazione del mapping di modello ER | [Mapping to learn deferred elements.version.1.1.xml](https://download.microsoft.com/download/c/9/c/c9c4b9dd-b700-4385-a087-a84ce9fc1d0f/Mappingtolearndeferredelements.version.1.1.xml) |

Prima di iniziare, è inoltre necessario scaricare e salvare la seguente configurazione della soluzione ER di esempio sul computer locale.

| Descrizione contenuto     | Nome file |
|-------------------------|-----------|
| Configurazione di formato ER | [Format to learn deferred XML elements.version.1.1.xml](https://download.microsoft.com/download/4/7/8/478fa846-22e9-4fa0-89b1-d3aeae660067/FormattolearndeferredXMLelements.version.1.1.xml) |

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
    2. Selezionare **Sfoglia**, trovare e selezionare il file **Format to learn deferred XML elements.1.1.xml**, quindi selezionare **OK**.

6. Nella struttura delle configurazioni, espandere **Modello di apprendimento di elementi differiti**.
7. Esaminare l'elenco delle configurazioni ER importate nella struttura delle configurazioni.

    ![Configurazioni ER importate nella pagina Configurazioni.](./media/ER-DeferredXml-Configurations.png)

### <a name="activate-a-configuration-provider"></a>Attivare un provider di configurazioni

1. Andare a **Amministrazione organizzazione** \> **Aree di lavoro** \> **Creazione di report elettronici**.
2. Nella pagina **Configurazioni localizzazione**, nella sezione **Provider di configurazione**, verificare che il [provider di configurazione](general-electronic-reporting.md#Provider) per la società di esempio Litware, Inc. (`http://www.litware.com`) sia elencato e contrassegnato come attivo. Se questo provider di configurazione non è elencato o non è contrassegnato come attivo, completare i passaggi dell'argomento [Creare un provider di configurazione e contrassegnarlo come attivo](./tasks/er-configuration-provider-mark-it-active-2016-11.md).

    ![La società di esempio Litware, Inc. nella pagina Configurazioni localizzazione.](./media/ER-DeferredXml-ElectronicReportingWorkspace.png)

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

        ![Campo di aggregazione TotalSum nella pagina di modifica dei parametri "GroupBy".](./media/ER-DeferredXml-GroupByParameters.png)

9. Verificare in che modo le origini dati configurate sono associate al modello di dati e come espongono i dati consultati per renderli disponibili in un formato ER:

    - L'origine dati **Filtrate** è associata al campo **Data.List** del modello di dati.
    - Il campo **\$TaxAmount** dell'origine dati **Filtrate** è associata al campo **Data.List.Value** del modello di dati.
    - Il campo **TotalSum** dell'origine dati **Raggruppate** è associato al campo **Data.Summary.Total** del modello di dati.

    ![Pagina Progettazione mapping modello.](./media/ER-DeferredXml-ModelMapping.png)

10. Chiudere le pagine **Progettazione mapping modello** e **Mapping modello**.

### <a name="review-the-imported-format"></a>Esaminare il formato importato

1. Nella pagina **Configurazioni**, nella struttura delle configurazioni, selezionare la configurazione **Formato per ottenere i elementi XML differiti**.
2. Selezionare **Progettazione** per esaminare i dettagli del formato.
3. Selezionare **Mostra dettagli**.
4. Verificare le impostazioni dei componenti di formato ER configurate per generare un documento in uscita in formato XML che includa i dettagli delle transazioni fiscali:

    - L'elemento XML **Report\\Message** è configurato per riempire il documento in uscita con un singolo nodo che include gli elementi XML nidificati (**Header**, **Record**, and **Summary**).
    - L'elemento XML **Report\\Message\\Header** è configurato per riempire il documento in uscita con una singola intestazione che mostra la data e l'ora di inizio dell'elaborazione.
    - L'elemento XML **Report\\Message\\Record** è configurato per riempire il documento in uscita con un singolo record che mostra i dettagli di una singola transazione fiscale.
    - L'elemento XML **Report\\Message\\Summary** è configurato per riempire il documento in uscita con un singolo nodo di riepilogo che mostra la somma dei valori di imposta delle transazioni fiscali elaborate.

    ![Elemento XML Message ed elementi XML nidificati nella pagina Progettazione formati.](./media/ER-DeferredXml-Format.png)

5. Nella scheda **Mappatura**, esaminare i seguenti dettagli:

    - L'elemento **Report\\Message\\Header** non deve essere associato a un'origine per generare un singolo nodo in un documento in uscita.
    - L'attributo **ExecutionDateTime** genera la data e l'ora (inclusi i millisecondi) in cui viene aggiunto il nodo di intestazione.
    - L'elemento **Report\\Message\\Record** è associato all'elenco **model.Data.List** per generare un singolo nodo di record per ogni record dell'elenco associato.
    - L'attributo **TaxAmount** è associato a **model.Data.List.Value** (visualizzato come **\@.Value** nella vista percorso relativa) per generare il valore di imposta della transazione fiscale corrente.
    - L'attributo **RunningTotal** è un segnaposto per il totale corrente dei valori di imposta. Attualmente, questo attributo non ha output, perché nessun valore di binding o predefinito è configurato per lo stesso.
    - L'attributo **ExecutionDateTime** genera la data e l'ora (inclusi i millisecondi) in cui viene la transazione corrente viene elaborata in questo report.
    - L'elemento **Report\\Message\\Summary** non deve essere associato a un'origine dati per generare un singolo nodo in un documento in uscita.
    - L'attributo **TotalTaxAmount** è associato a **model.Data.Summary.Total** per generare la somma dei valori di imposta delle transazioni fiscali elaborate.
    - L'attributo **ExecutionDateTime** genera la data e l'ora (inclusi i millisecondi) in cui viene aggiunto il nodo di riepilogo.

    ![Scheda Mapping nella pagina Progettazione formati.](./media/ER-DeferredXml-Format2.png)

### <a name="run-the-imported-format"></a>Eseguire il formato importato

1. Nella pagina **Progettazione formati**, selezionare **Esegui**.
2. Scaricare il file proposto dal browser Web e aprirlo per esaminarlo.

    ![File scaricato - formato importato.](./media/ER-DeferredXml-Run.png)

Si noti che il nodo di riepilogo presenta la somma dei valori di imposta per le transazioni elaborate. Poiché il formato è configurato per utilizzare il binding **model.Data.Summary.Total** per restituire questa somma, la somma viene calcolata chiamando l'aggregazione **TotalSum** dell'origine dati **Raggruppate** di tipo *GroupBy* nel mapping di modello. Per calcolare questa aggregazione, il mapping di modello esegue l'iterazione su tutte le transazioni che sono state selezionate nell'origine dati **Filtrate**. Confrontando i tempi di esecuzione del nodo di riepilogo e dell'ultimo nodo di record, è possibile determinare che il calcolo della somma ha richiesto 12 millisecondi (ms). Confrontando i tempi di esecuzione del primo e dell'ultimo nodo di record, è possibile determinare che la generazione di tutti i nodi di record ha richiesto 9 ms. Pertanto, sono stati necessari in totale 21 ms.

### <a name="modify-the-format-so-that-the-calculation-is-based-on-generated-output"></a>Modificare il formato di modo che il calcolo si basi sull'output generato

Se il volume della transazione è molto più grande del volume nell'esempio corrente, il tempo di calcolo potrebbe aumentare e causare problemi di prestazioni. Modificando l'impostazione del formato, è possibile prevenire questi problemi di prestazioni. Poiché si accede ai valori di imposta per includerli nel report generato, è possibile riutilizzare queste informazioni per calcolare i valori di imposta. Per ulteriori informazioni, vedere [Configurare il formato per eseguire il conteggio e la sommatoria](./tasks/er-format-counting-summing-1.md).

1. Nella pagina **Progettazione formati**, nella scheda **Formato** selezionare l'elemento di file **Report** nella struttura dei formati.
2. Impostare l'opzione **Raccogli dettagli di output** su **Sì**. È ora possibile configurare questo formato utilizzando il contenuto di un report generato come origine dati a cui è possibile accedere utilizzando le funzioni ER integrate nella categoria [Raccolta dati](er-functions-category-data-collection.md).
3. Nella scheda **Mapping**, selezionare l'elemento XML **Report\\Message\\Record**.
4. Configurare l'espressione **Nome chiave dati raccolti** come `WsColumn`.
5. Configurare l'espressione **Valore chiave dati raccolti** come `WsRow`.

    ![Registrare l'elemento XML nella pagina Progettazione formati.](./media/ER-DeferredXml-Format3.png)

6. Selezionare l'attributo **Report\\Message\\Record\\TaxAmount**.
7. Configurare l'espressione **Nome chiave dati raccolti** come `SummingAmountKey`.

    ![Attributo TaxAmount nella pagina Progettazione formati.](./media/ER-DeferredXml-Format4.png)

    È possibile considerare questa impostazione come la creazione di un foglio di lavoro virtuale, in cui il valore della cella A1 viene aggiunto al valore dell'importo fiscale di ogni transazione fiscale elaborata.

8. Selezionare l'attributo **Report\\Message\\Record\\RunningTotal** e quindi selezionare **Modifica formula**.
9. Configurare l'espressione `SUMIF(SummingAmountKey, WsColumn, WsRow)` usando la funzione ER [SUMIF](er-functions-datacollection-sumif.md) integrata e quindi selezionare **Salva**.

    ![Espressione SUMIF.](./media/ER-DeferredXml-FormulaDesigner.png)

10. Chiudere la pagina **Designer formula**.
11. Selezionare **Salva** e quindi selezionare **Esegui**.
12. Scaricare ed esaminare il file proposto dal browser Web.

    ![Elenco generato del valore dell'imposta con il totale parziale.](./media/ER-DeferredXml-Run1.png)

    L'ultimo nodo di record contiene il totale corrente dei valori di imposta calcolato per tutte le transazioni elaborate utilizzando l'output generato come origine dati. Questa origine dati comincia all'inizio del report e continua fino all'ultima transazione fiscale. Il nodo di riepilogo contiene la somma dei valori di imposta di tutte le transazioni elaborate calcolate nel mapping di modello utilizzando l'origine dati di tipo *GroupBy*. Si noti che questi valori sono uguali. Pertanto, è possibile utilizzare la somma basata sull'output al posto di **GroupBy**. Confrontando i tempi di esecuzione del primo nodo di record e del nodo di riepilogo, è possibile determinare che la generazione di tutti i nodi di record e della somma ha richiesto 11 ms. Pertanto, per quanto riguarda la generazione dei nodi di record e della somma dei valori di imposta, il formato modificato è circa due volte più veloce del formato originale.

13. Selezionare l'attributo **Report\\Message\\Summary\\TotalTaxAmount** e quindi selezionare **Modifica formula**.
14. Immettere l'espressione `SUMIF(SummingAmountKey, WsColumn, WsRow)` anziché l'espressione esistente.
15. Selezionare **Salva** e quindi selezionare **Esegui**.
16. Scaricare ed esaminare il file proposto dal browser Web.

    ![Elenco generato dei valori delle imposte utilizzando la formula modificata.](./media/ER-DeferredXml-Run2.png)

    Si noti che il totale corrente dei valori di imposta nell'ultimo nodo di record è ora uguale alla somma nel nodo di riepilogo.

### <a name="put-values-of-output-based-summing-in-the-report-header"></a>Inserire i valori della somma basata su output nell'intestazione del report

Se, ad esempio, è necessario presentare la somma dei valori di imposta nell'intestazione del report, è possibile modificare il formato.

1. Nella pagina **Progettazione formati**, nella scheda **Formato** selezionare l'elemento XML **Report\\Message\\Summary**.
2. Selezionare **Sposta su**.
3. Selezionare **Salva** e quindi selezionare **Esegui**.
4. Scaricare ed esaminare il file proposto dal browser Web.

    ![File scaricato dei valori delle imposte per l'intestazione del report.](./media/ER-DeferredXml-Run3.png)

    Si noti che la somma dei valori di imposta nel nodo di riepilogo ora è uguale a 0 (zero), poiché questa somma viene ora calcolata in base all'output generato. Quando viene generato il primo nodo di record, l'output generato non contiene ancora nodi di record che hanno dettagli delle transazioni. È possibile configurare questo formato per differire l'esecuzione dell'elemento **Report\\Message\\Summary** fino a che l'elemento **Report\\Message\\Record** non è stato eseguito per tutte le transazioni fiscali.

### <a name="defer-the-execution-of-the-summary-xml-element-so-that-the-calculated-total-is-used"></a>Differire l'esecuzione dell'elemento XML di riepilogo in modo che venga utilizzato il totale calcolato

1. Nella pagina **Progettazione formati**, nella scheda **Formato** selezionare l'elemento XML **Report\\Message\\Summary**.
2. Impostare l'opzione **Esecuzione differita** su **Sì**.

    ![Opzione Esecuzione differita dell'elemento XML Summary nella pagina Progettazione formati.](./media/ER-DeferredXml-Format5.png)

3. Selezionare **Salva** e quindi selezionare **Esegui**.
4. Scaricare ed esaminare il file proposto dal browser Web.

    ![File scaricato - esecuzione differita.](./media/ER-DeferredXml-Run4.png)

    L'elemento **Report\\Message\\Summary** viene ora eseguito solo dopo l'esecuzione di tutti gli altri elementi nidificati sotto l'elemento padre **Report\\Message**. Pertanto, viene eseguito dopo l'esecuzione dell'elemento **Report\\Message\\Record** per tutte le transazioni fiscali dell'origine dati **model.Data.List**. I tempi di esecuzione del primo e dell'ultimo nodo di record e dei nodi di intestazione e di riepilogo rivelano tale condizione.

## <a name="additional-resources"></a>Risorse aggiuntive

- [Configurare il formato per eseguire il conteggio e la sommatoria](./tasks/er-format-counting-summing-1.md)
- [Generare la traccia dell'esecuzione del formato ER per risolvere problemi relativi alle prestazioni](trace-execution-er-troubleshoot-perf.md)
- [Differire l'esecuzione di elementi di sequenza in formati ER](er-defer-sequence-element.md#Example)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
