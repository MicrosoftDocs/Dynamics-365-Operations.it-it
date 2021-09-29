---
title: Progettare una configurazione per generare documenti in uscita in formato Excel
description: Questo argomento descrive come progettare un formato di report elettronico (ER) per compilare un modello Excel e quindi generare documenti in formato Excel in uscita.
author: NickSelin
ms.date: 09/14/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EROperationDesigner, ERParameters
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: fd3171ad24f9c06f04372b30f2682b6da516bcb6
ms.sourcegitcommit: 7a2001e4d01b252f5231d94b50945fd31562b2bc
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/15/2021
ms.locfileid: "7488140"
---
# <a name="design-a-configuration-for-generating-documents-in-excel-format"></a>Progettare una configurazione per la generazione di documenti in formato Excel

[!include[banner](../includes/banner.md)]

Puoi progettare una configurazione del formato del [report elettronico (ER)](general-electronic-reporting.md) che abbia un [componente del formato](general-electronic-reporting.md#FormatComponentOutbound) ER che puoi configurare per generare un documento in uscita in un formato cartella di lavoro Microsoft Excel. A tale scopo devono essere utilizzati componenti specifici del formato ER.

Per ulteriori informazioni su questa funzionalità, segui i passaggi nell'argomento [Progettare una configurazione per la generazione di report in formato OPENXML](tasks/er-design-reports-openxml-2016-11.md).

## <a name="add-a-new-er-format"></a>Aggiungi un nuovo formato ER

Quando si aggiunge una nuova configurazione del formato ER per generare un documento in uscita in un formato cartella di lavoro Excel, devi selezionare il valore **Excel** per l'attributo **Tipo di formato** del formato o lasciare vuoto l'attributo **Tipo di formato**.

- Se selezioni **Excel**, puoi configurare il formato per generare un documento in uscita solo in formato Excel.
- Se lasci vuoto l'attributo, puoi configurare il formato per generare un documento in uscita in qualsiasi formato supportato dal framework ER.

Per configurare il componente del formato ER della configurazione, seleziona **Progettazione** nel riquadro azioni e apri il componente del formato ER per la modifica nella progettazione dell'operazione ER.

![Pagina Configurazioni.](./media/er-excel-format-add-format.png)

## <a name="excel-file-component"></a>Componente del file Excel

### <a name="manual-entry"></a>Immissione manuale

Devi aggiungere un componente **Excel\\File** nel formato ER configurato per generare un documento in uscita in formato Excel.

![Componente Excel\File.](./media/er-excel-format-add-file-component.png)

Per specificare il layout del documento in uscita, allega una cartella di lavoro di Excel con estensione .xlsx al componente **Excel\\File** come modello per i documenti in uscita.

> [!NOTE]
> Quando si collega manualmente un modello, devi utilizzare un [tipo di documento](../../../fin-ops-core/fin-ops/organization-administration/configure-document-management.md#configure-document-types) che è stato configurato a tale scopo nei [parametri ER](electronic-reporting-er-configure-parameters.md#parameters-to-manage-documents).

![Aggiunta di un allegato al componente Excel\File.](./media/er-excel-format-add-file-component2.png)

Per specificare come compilare il modello allegato quando si esegue il formato ER configurato, devi aggiungere componenti **Foglio**, **Intervallo** e **Cella** nidificati al componente **Excel\\File**. Ciascun componente nidificato deve essere associato a un elemento denominato Excel.

### <a name="template-import"></a>Importazione di modelli

Puoi selezionare **Importa da Excel** nella scheda **Importa** del riquadro azioni per importare un nuovo modello in un formato ER vuoto. In questo esempio, un componente **Excel\\File** verrà creato automaticamente e il modello importato verrà allegato ad esso. Tutti i componenti ER richiesti verranno inoltre creati automaticamente, in base all'elenco di elementi denominati Excel rilevati.

![Selezione di Importa da Excel.](./media/er-excel-format-import-template.png)

> [!NOTE]
> Se desideri creare l'elemento **Foglio** facoltativo nel formato ER modificabile, imposta l'opzione **Crea elemento in formato foglio Excel** su **Sì**.

## <a name="sheet-component"></a>Componente foglio

Il componente **Foglio** indica un foglio di lavoro della cartella di lavoro Excel allegata che deve essere compilato. Il nome del foglio di lavoro in un modello di Excel è definito nella proprietà **Foglio** di questo componente.

> [!NOTE]
> Questo componente è facoltativo per le cartelle di lavoro di Excel che contengono un singolo foglio di lavoro.

Nella scheda **Mappatura** della progettazione dell'operazione ER, puoi configurare la proprietà **Enabled** per un componente **Foglio** per specificare se il componente deve essere inserito in un documento generato:

- Se un'espressione della proprietà **Enabled** è configurata per tornare su **True** in fase di runtime o se nessuna espressione è configurata, il foglio di lavoro appropriato verrà inserito nel documento generato.
- Se un'espressione della proprietà **Enabled** è configurata per tornare su **False** in fase di runtime, il documento generato non conterrà un foglio di lavoro.

![Esempio di un componente Foglio.](./media/er-excel-format-sheet-component.png)

## <a name="range-component"></a>Componente Intervallo

Il componente **Intervallo** indica un intervallo Excel che deve essere controllato da questo componente ER. Il nome dell'intervallo è definito nella proprietà **Excel range** di questo componente.

La proprietà **Replication direction** specifica se e come verrà ripetuto l'intervallo in un documento generato:

- Se la proprietà **Replication direction** è impostata su **Nessuna replica**, l'intervallo Excel appropriato non verrà ripetuto nel documento generato.
- Se la proprietà **Replication direction** è impostata su **Verticale**, l'intervallo Excel appropriato verrà ripetuto nel documento generato. Ciascun intervallo replicato viene inserito al di sotto dell'intervallo originale in un modello di Excel. Il numero di ripetizioni è definito dal numero di record in un'origine dati di tipo **Elenco di record** associato a questo componente ER.
- Se la proprietà **Replication direction** è impostata su **Orizzontale**, l'intervallo Excel appropriato verrà ripetuto nel documento generato. Ciascun intervallo replicato viene inserito a destra dell'intervallo originale in un modello di Excel. Il numero di ripetizioni è definito dal numero di record in un'origine dati di tipo **Elenco di record** associato a questo componente ER.

Per ulteriori informazioni sulla replica orizzontale, segui i passaggi [Utilizzare intervalli espandibili orizzontalmente per aggiungere dinamicamente le colonne in report di Excel](tasks/er-horizontal-1.md).

Il componente **Intervallo** può avere altri componenti ER nidificati che vengono utilizzati per immettere valori negli intervalli denominati Excel appropriati.

- Se qualche componente del gruppo **Testo** viene utilizzato per immettere valori, il valore viene inserito in un intervallo di Excel come valore di testo.

    > [!NOTE]
    > Utilizza questo modello per formattare i valori immessi in base alle impostazioni internazionali definite nell'applicazione.

- Se il componente **Cella** del gruppo **Excel** viene utilizzato per immettere valori, il valore viene inserito in un intervallo di Excel come valore del tipo di dati definito dall'associazione del componente **Cella** (ad esempio, **Stringa**, **Reale** o **Intero**).

    > [!NOTE]
    > Utilizza questo modello per abilitare l'applicazione Excel a formattare i valori immessi in base alle impostazioni internazionali del computer locale che apre il documento in uscita.

Nella scheda **Mappatura** della progettazione dell'operazione ER, puoi configurare la proprietà **Enabled** per un componente **Intervallo** per specificare se il componente deve essere inserito in un documento generato:

- Se un'espressione della proprietà **Enabled** è configurata per tornare su **True** in fase di runtime o se nessuna espressione è configurata, l'intervallo appropriato verrà compilato nel documento generato.
- Se un'espressione della proprietà **Enabled** è configurata per tornare su **False** in fase di runtime e se questo intervallo non rappresenta le colonne e le righe intere, l'intervallo appropriato non verrà compilato nel documento generato.
- Se un'espressione della proprietà **Enabled** è configurata per tornare su **False** in fase di runtime e se questo intervallo rappresenta le colonne e le righe intere, l'intervallo generato conterrà queste righe e colonne come righe e colonne nascoste.

## <a name="cell-component"></a>Componente cellulare

Il componente **Cella** viene utilizzato per riempire celle, forme e immagini denominate Excel. Per indicare un oggetto denominato Excel che deve essere compilato da un componente ER **Cella**, devi specificare il nome dell'oggetto nella proprietà **Excel range** del componente **Cella**.

Nella scheda **Mappatura** della progettazione dell'operazione ER, puoi configurare la proprietà **Enabled** per un componente **Cella** per specificare se l'oggetto deve essere inserito in un documento generato:

- Se un'espressione della proprietà **Enabled** è configurata per tornare su **True** in fase di runtime o se nessuna espressione è configurata, l'oggetto appropriato verrà compilato nel documento generato. L'associazione di questo componente **Cella** specifica un valore che viene inserito nell'oggetto appropriato.
- Se un'espressione della proprietà **Enabled** è configurata per tornare su **False** in fase di runtime, l'oggetto appropriato non verrà compilato nel documento generato.

Quando un componente **Cella** è configurato per immettere un valore in una cella, può essere associato a un'origine dati che restituisce il valore di un tipo di dati primitivo (ad esempio, **Stringa**, **Reale** o **Intero**). In questo caso, il valore viene inserito nella cella come valore dello stesso tipo di dati.

Quando un componente **Cella** è configurato per immettere un valore in una forma Excel, può essere associato a un'origine dati che restituisce un valore di un tipo di dati primitivo (ad esempio, **Stringa**, **Reale** o **Intero**). In questo caso, il valore viene inserito nella forma Excel come testo di quella forma. Per valori di tipi di dati che non lo sono **Stringa**, la conversione in testo viene eseguita automaticamente.

> [!NOTE]
> Puoi configurare un componente **Cella** per riempire una forma solo nei casi in cui è supportata una proprietà del testo della forma.

Quando un componente **Cella** è configurato per immettere un valore in un'immagine Excel, può essere associato a un'origine dati che restituisce un valore di un tipo di dati **Contenitore** che rappresenta un'immagine in formato binario. In questo caso, il valore viene inserito nell'immagine Excel come immagine.

> [!NOTE]
> Ogni immagine e forma di Excel è considerata ancorata dal suo angolo in alto a sinistra a una cella o intervallo Excel specifici. Se desideri replicare un'immagine o una forma di Excel, devi configurare la cella o l'intervallo a cui è ancorata come cella o intervallo replicato.

Per ulteriori informazioni su come incorporare immagini e forme, vedi [Incorporare immagini e forme nei documenti generati utilizzando ER](electronic-reporting-embed-images-shapes.md).

## <a name="page-break-component"></a>Componente interruzione di pagina

Il componente **PageBreak** forza Excel ad avviare una nuova pagina. Questo componente non è richiesto quando desideri utilizzare il paging predefinito di Excel, ma è necessario utilizzarlo quando desideri che Excel segua il formato ER per strutturare il paging.

## <a name="page-component"></a><a name="page-component"></a>Componente Pagina

### <a name="overview"></a>Panoramica

Puoi usare il componente **Pagina** quando vuoi che Excel segua il tuo formato ER e strutturi l'impaginazione in un documento in uscita generato. Quando un formato ER esegue componenti che sono sotto il componente **Pagina**, le interruzioni di pagina richieste vengono aggiunte automaticamente. Durante questo processo, vengono considerate le dimensioni del contenuto generato, l'impostazione della pagina del modello di Excel e il formato della carta selezionato nel modello di Excel.

Se devi dividere un documento generato in diverse sezioni, ognuna delle quali ha una diversa impaginazione, puoi configurare diversi componenti **Pagina** in ogni componente [Foglio](er-fillable-excel.md#sheet-component).

### <a name="structure"></a><a name="page-component-structure"></a>Struttura

Se il primo componente sotto il componente **Pagina** è un componente [Intervallo](er-fillable-excel.md#range-component) in cui la proprietà **Direzione replica** è impostata su **Nessuna replica**, questo intervallo è considerato l'intestazione della pagina per l'impaginazione che si basa sulle impostazioni del corrente componente **Pagina**. L'intervallo di Excel associato a questo componente di formato viene ripetuto nella parte superiore di ogni pagina generata utilizzando le impostazioni del componente **Pagina** corrente.

> [!NOTE]
> Per l'impaginazione corretta, se l'intervallo [Righe da ripetere in alto](https://support.microsoft.com/office/repeat-specific-rows-or-columns-on-every-printed-page-0d6dac43-7ee7-4f34-8b08-ffcc8b022409) è configurato nel modello di Excel, l'indirizzo di questo intervallo di Excel deve essere uguale all'indirizzo dell'intervallo di Excel associato al componente precedentemente descritto **Intevallo**.

Se l'ultimo componente sotto il componente **Pagina** è un componente **Intervallo** in cui la proprietà **Direzione replica** è impostata su **Nessuna replica**, questo intervallo è considerato il piè di pagina per l'impaginazione che si basa sulle impostazioni del corrente componente **Pagina**. L'intervallo di Excel associato a questo componente di formato viene ripetuto nella parte inferiore di ogni pagina generata utilizzando le impostazioni del componente **Pagina** corrente.

> [!NOTE]
> Per una corretta impaginazione, gli intervalli di Excel associati ai componenti **Intervallo** non devono essere ridimensionati in fase di esecuzione. Non è consigliabile formattare le celle di questo intervallo utilizzando le opzioni **Testo a capo in una cella** e **Adatta automaticamente l'altezza della riga** di [Excel](https://support.microsoft.com/office/wrap-text-in-a-cell-2a18cff5-ccc1-4bce-95e4-f0d4f3ff4e84).

Puoi aggiungere molti altri componenti **Intervallo** tra i componenti **Intevallo** facoltativi per specificare come viene compilato un documento generato.

Se il set di componenti nidificati **Intevallo** sotto il componente **Pagina** non è conforme alla struttura precedentemente descritta, si verifica un [errore](er-components-inspections.md#i17) di convalida in fase di progettazione nella finestra di progettazione del formato ER. Il messaggio di errore informa che il problema può causare problemi in fase di esecuzione.

> [!NOTE]
> Per generare un output corretto, non specificare un'associazione per nessun componente **Intevallo** sotto il componente **Pagina** se la proprietà **Direzione replica** per questo componente **Intevallo** è impostata su **Nessuna replica** e l'intervallo è configurato per generare intestazioni di pagina o piè di pagina.

Se desideri che la somma e il conteggio relativi all'impaginazione calcolino i totali parziali e i totali per pagina, ti consigliamo di configurare le origini dati [Raccolta dati](er-data-collection-data-sources.md) richieste. Per imparare a usare il componente **Pagina** per impaginare un documento di Excel generato, completa le procedure in [Progettare un formato ER per impaginare i documenti generati in Excel](er-paginate-excel-reports.md).

### <a name="limitations"></a><a name="page-component-limitations"></a>Limiti

Quando usi il componente **Pagina** per l'impaginazione di Excel, non conoscerai il numero finale di pagine in un documento generato finché l'impaginazione non sarà completata. Pertanto, non è possibile calcolare il numero totale di pagine utilizzando le formule ER e stampare il numero corretto di pagine di un documento generato su qualsiasi pagina prima dell'ultima pagina.

> [!TIP]
> Per ottenere questo risultato in un'intestazione o un piè di pagina di Excel utilizzando l'apposita [formattazione](/office/vba/excel/concepts/workbooks-and-worksheets/formatting-and-vba-codes-for-headers-and-footers) di Excel per intestazioni e piè di pagina.

I componenti **Pagina** configurati non vengono considerati quando si aggiorna un modello di Excel nel formato modificabile in Dynamics 365 Finance versione 10.0.22. Questa funzionalità è considerata per ulteriori versioni di Finance.

Se configuri il tuo modello di Excel per usare la [formattazione condizionale](/office/dev/add-ins/excel/excel-add-ins-conditional-formatting), in alcuni casi potrebbe non funzionare come previsto.

### <a name="applicability"></a>Applicabilità

Il componente **Pagina** funziona per il componente formato [file di Excel](er-fillable-excel.md#excel-file-component) solo quando tale componente è configurato per utilizzare un modello in Excel. Se [sostituisci](tasks/er-design-configuration-word-2016-11.md) il modello di Excel con un modello di Word e quindi esegui il formato ER modificabile, il componente **Pagina** verrà ignorato.

Il componente **Pagina** funziona solo quando la funzionalità **Abilita l'utilizzo della libreria EPPlus nel framework di creazione di report elettronici** è abilitata. Viene generata un'eccezione in fase di esecuzione se ER tenta di elaborare il componente **Pagina** mentre questa funzione è disabilitata.

> [!NOTE]
> Viene generata un'eccezione in fase di esecuzione se un formato ER elabora il componente **Pagina** per un modello di Excel che contiene almeno una formula che fa riferimento a una cella non valida. Per evitare errori di runtime, correggi il modello di Excel come descritto in [Come correggere un errore #RIF!](https://support.microsoft.com/office/how-to-correct-a-ref-error-822c8e46-e610-4d02-bf29-ec4b8c5ff4be).

## <a name="footer-component"></a>Componente piè di pagina

Il componente **Piè di pagina** viene utilizzato per compilare i piè di pagina nella parte inferiore di un foglio di lavoro generato in una cartella di lavoro di Excel.

> [!NOTE]
> È possibile aggiungere questo componente per ogni componente **Foglio** per specificare diversi piè di pagina per diversi fogli di lavoro in una cartella di lavoro Excel generata.

Quando si configura un singolo componente **Piè di pagina**, è possibile usare la proprietà **Aspetto intestazione/piè di pagina** per specificare le pagine per le quali viene utilizzato il componente. Sono disponibili i valori seguenti:

- **Qualsiasi** - Esegue il componente **Piè di pagina** configurato per qualsiasi pagina del foglio di lavoro Excel padre.
- **Prima** - Esegue il componente **Piè di pagina** configurato soltanto per la prima pagina del foglio di lavoro Excel padre.
- **Pari** - Esegue il componente **Piè di pagina** configurato soltanto per le pagine pari del foglio di lavoro Excel padre.
- **Dispari** - Esegue il componente **Piè di pagina** configurato soltanto per le pagine dispari del foglio di lavoro Excel padre.

Per un singolo componente **Foglio**, è possibile aggiungere diversi componenti **Piè di pagina**, ognuno dei quali ha un valore diverso per la proprietà **Aspetto intestazione/piè di pagina**. In questo modo, è possibile generare diversi piè di pagina per diversi tipi di pagine in un foglio di lavoro Excel.

> [!NOTE]
> Assicurarsi che ogni componente **Piè di pagina** aggiunto a un singolo componente **Foglio** abbia un valore diverso per la proprietà **Aspetto intestazione/piè di pagina**. Altrimenti, si ha un [errore di convalida](er-components-inspections.md#i16). Il messaggio di errore ricevuto informa dell'incoerenza.

Sotto il componente **Piè di pagina** aggiunto, aggiungere i componenti nidificati necessari di tipo **Testo\\Stringa**, **Testo\\DataTime** o di altro tipo. Configurare le associazioni per tali componenti per specificare come viene riempito il piè di pagina.

È anche possibile usare [codici di formattazione](/office/vba/excel/concepts/workbooks-and-worksheets/formatting-and-vba-codes-for-headers-and-footers) speciali per formattare correttamente il contenuto di un piè di pagina generato. Per informazioni su come utilizzare questo approccio, seguire i passaggi nell'[Esempio 1](#example-1) più avanti in questo argomento.

> [!NOTE]
> Quando si configurano i formati ER, assicurarsi di considerare il [limite](https://support.microsoft.com/office/excel-specifications-and-limits-1672b34d-7043-467e-8e27-269d656771c3) di Excel e il numero massimo di caratteri per una singola intestazione o piè di pagina.

## <a name="header-component"></a>Componente intestazione

Il componente **Intestazione** viene utilizzato per compilare i piè di pagina nella parte superiore di un foglio di lavoro generato in una cartella di lavoro di Excel. È usato come il componente **Piè di pagina**.

## <a name="edit-an-added-er-format"></a>Modifica un formato ER aggiunto

### <a name="update-a-template"></a>Aggiorna un modello

Puoi selezionare **Aggiorna da Excel** nella scheda **Importa** del riquadro azioni per importare un modello aggiornato in un formato ER modificabile. Durante questo processo, un modello del componente **Excel\\File** selezionato verrà sostituito da un nuovo modello. Il contenuto del formato ER modificabile verrà sincronizzato con il contenuto del modello ER aggiornato.

- Un nuovo componente in formato ER verrà automaticamente creato per ogni nome Excel se il componente in formato ER non viene trovato nel formato modificabile.
- Ogni componente del formato ER verrà eliminato dal formato ER modificabile se non viene trovato il nome Excel appropriato per esso.

> [!NOTE]
> Imposta l'opzione **Crea elemento in formato foglio Excel** su **Sì** se desideri creare l'elemento **Foglio** opzionale nel formato ER modificabile.
>
> Se il formato ER modificabile era originariamente contenuto negli elementi **Foglio**, ti consigliamo di impostare l'opzione **Crea elemento in formato foglio Excel** su **Sì** quando importi un modello aggiornato. Altrimenti, tutti gli elementi nidificati dell'elemento originale **Foglio** verrà creato da zero. Pertanto, tutti i collegamenti degli elementi di formato ricreati andranno persi nel formato ER aggiornato.

![Creare l'opzione elemento formato del foglio di Excel nella finestra di dialogo Aggiorna da Excel.](./media/er-excel-format-update-template.png)

Per saperne di più su questa funzionalità, segui i passaggi in [Modificare i formati per la creazione di report elettronici riapplicando modelli di Excel](modify-electronic-reporting-format-reapply-excel-template.md).

## <a name="validate-an-er-format"></a>Convalida un formato ER

Quando si convalida un formato ER che può essere modificato, viene eseguito un controllo di coerenza per assicurarsi che il nome Excel sia presente nel modello Excel attualmente utilizzato. Riceverai una notifica di eventuali incoerenze. Per alcune incoerenze, verrà offerta l'opzione per risolvere automaticamente i problemi.

![Messaggio di errore di convalida.](./media/er-excel-format-validate.png)

## <a name="control-the-calculation-of-excel-formulas"></a>Controllare il calcolo delle formule di Excel

Quando viene generato un documento in uscita in un formato di cartella di lavoro Microsoft Excel, alcune celle di questo documento potrebbero contenere formule Excel. Quando la funzionalità **Abilita l'utilizzo della libreria EPPlus nel framework di creazione report elettronici** è abilitata, è possibile controllare quando le formule vengono calcolate modificando il valore del parametro **Opzioni di calcolo** [nel](https://support.microsoft.com/office/change-formula-recalculation-iteration-or-precision-in-excel-73fc7dac-91cf-4d36-86e8-67124f6bcce4#ID0EAACAAA=Windows) modello Excel in uso:

- Selezionare **Automatico** per ricalcolare tutte le formule dipendenti ogni volta che un documento generato viene aggiunto da nuovi intervalli, celle, ecc.

    >[!NOTE]
    > Ciò potrebbe causare un problema di prestazioni per i modelli di Excel che contengono più formule correlate.

- Selezionare **Manuale** per evitare il ricalcolo della formula quando viene generato un documento.

    >[!NOTE]
    > Il ricalcolo delle formule viene forzato manualmente quando un documento generato viene aperto per l'anteprima utilizzando Excel.
    > Non utilizzare questa opzione se si configura una destinazione ER che presuppone l'utilizzo di un documento generato senza la sua anteprima in Excel (conversione PDF, invio di e-mail, ecc.) perché il documento generato potrebbe non contenere valori nelle celle che contengono formule.

## <a name="example-1-format-footer-content"></a><a name="example-1"></a>Esempio 1: formattare il contenuto del piè di pagina

1. Utilizzare le configurazioni ER fornite per [generare](er-generate-printable-fti-forms.md) un documento di fattura a testo libero stampabile.
2. Esaminare il piè di pagina del documento generato. Da notare che contiene informazioni sul numero di pagina corrente e sul numero totale di pagine nel documento.

    ![Esaminare il piè di pagina di un documento generato in formato Excel.](./media/er-fillable-excel-footer-1.gif)

3. Nella progettazione del formato ER, [aprire](er-generate-printable-fti-forms.md#features-that-are-implemented-in-the-sample-er-format) il formato ER di esempio per la revisione.

    Il piè di pagina del foglio di lavoro **Fattura** viene generato in base alle impostazioni di due componenti **Stringa** che si trovano sotto il componente **Piè di pagina**:

    - Il primo componente **Stringa** compila i seguenti codici di formattazione speciali per forzare Excel ad applicare una formattazione specifica:

        - **&C** - Allinea il testo del piè di pagina al centro.
        - **&"Segoe UI,Regular"&8** - Presenta il testo del piè di pagina nel carattere "Segoe UI Regular" con una dimensione di 8 punti.

    - Il secondo componente **Stringa** compila il testo che contiene il numero di pagina corrente e il numero totale di pagine nel documento corrente.

    ![Esaminare il componente formato ER piè di pagina nella pagina Progettazione formati.](./media/er-fillable-excel-footer-2.png)

4. Personalizza il formato ER di esempio per modificare il piè di pagina della pagina corrente:

    1. [Creare](er-quick-start2-customize-report.md#DeriveProvidedFormat) un formato ER **Fattura a testo libero (Excel) personalizzata** derivato basato sul formato ER di esempio.
    2. Aggiungere la prima nuova coppia di componenti **Stringa** per il componente **Piè di pagina** del foglio di lavoro **Fattura**:

        1. Aggiungere un componente **Stringa** che allinea il nome dell'azienda a sinistra e lo presenta nel carattere "Segoe UI Regular" con la dimensione di 8 punti (**"&L&"Segoe UI,Regular"e8"**).
        2. Aggiungere un componente **Stringa** che compila il nome dell'azienda (**model.InvoiceBase.CompanyInfo.Name**).

    3. Aggiungere la seconda nuova coppia di componenti **Stringa** per il componente **Piè di pagina** del foglio di lavoro **Fattura**:

        1. Aggiungere un componente **Stringa** che allinea la data di elaborazione a destra e la presenta nel carattere "Segoe UI Regular" con la dimensione di 8 punti (**"&R&"Segoe UI,Regular"e8"**).
        2. Aggiungere un componente **Stringa** che riempie la data di elaborazione in un formato personalizzato (**"&nbsp;"&DATEFORMAT(SESSIONTODAY(), "aaaa-MM-gg")**).

        ![Esaminare il componente formato ER piè di pagina nella pagina Progettazione formati.](./media/er-fillable-excel-footer-3.png)

    4. [Completare](er-quick-start2-customize-report.md#CompleteDerivedFormat) la versione bozza del formato ER **Fattura a testo libero (Excel) personalizzata** derivato.

5. [Configurare](er-generate-printable-fti-forms.md#configure-print-management) Gestione stampa per utilizzare il formato ER **Fattura a testo libero (Excel) personalizzata** derivato anziché il formato ER di esempio.
6. Genera un documento FTI stampabile ed esaminare il piè di pagina del documento generato.

    ![Esame del piè di pagina di un documento generato in formato Excel.](./media/er-fillable-excel-footer-4.gif)

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica sui report elettronici](general-electronic-reporting.md)

[Progettare una configurazione per la generazione di report in formato OPENXML](tasks\er-design-reports-openxml-2016-11.md)

[Modificare i formati per la creazione di report elettronici riapplicando modelli di Excel](modify-electronic-reporting-format-reapply-excel-template.md)

[Utilizzare intervalli espandibili orizzontalmente per aggiungere dinamicamente le colonne in report di Excel](tasks/er-horizontal-1.md)

[Incorporare immagini e forme nei documenti generati utilizzando ER](electronic-reporting-embed-images-shapes.md)

[Configurare la creazione di report elettronici (ER) per eseguire il pull dei dati in Power BI](general-electronic-reporting-report-configuration-get-data-powerbi.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
