---
title: Progettare una configurazione per generare documenti in uscita in formato Excel
description: Questo argomento descrive come progettare un formato di report elettronico (ER) per compilare un modello Excel e quindi generare documenti in formato Excel in uscita.
author: NickSelin
manager: AnnBe
ms.date: 11/02/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
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
ms.openlocfilehash: c8d6a18741d57829d1929fb8362dc4ba8e03a1bd
ms.sourcegitcommit: 5192cfaedfd861faea63d8954d7bcc500608a225
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2021
ms.locfileid: "5094031"
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

![Pagina Configurazioni](./media/er-excel-format-add-format.png)

## <a name="excel-file-component"></a>Componente del file Excel

### <a name="manual-entry"></a>Immissione manuale

Devi aggiungere un componente **Excel\\File** nel formato ER configurato per generare un documento in uscita in formato Excel.

![Componente Excel\File](./media/er-excel-format-add-file-component.png)

Per specificare il layout del documento in uscita, allega una cartella di lavoro di Excel con estensione .xlsx al componente **Excel\\File** come modello per i documenti in uscita.

> [!NOTE]
> Quando si collega manualmente un modello, devi utilizzare un [tipo di documento](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/configure-document-management#configure-document-types) che è stato configurato a tale scopo nei [parametri ER](electronic-reporting-er-configure-parameters.md#parameters-to-manage-documents).

![Aggiunta di un allegato al componente Excel\File](./media/er-excel-format-add-file-component2.png)

Per specificare come compilare il modello allegato quando si esegue il formato ER configurato, devi aggiungere componenti **Foglio**, **Intervallo** e **Cella** nidificati al componente **Excel\\File**. Ciascun componente nidificato deve essere associato a un elemento denominato Excel.

### <a name="template-import"></a>Importazione di modelli

Puoi selezionare **Importa da Excel** nella scheda **Importa** del riquadro azioni per importare un nuovo modello in un formato ER vuoto. In questo esempio, un componente **Excel\\File** verrà creato automaticamente e il modello importato verrà allegato ad esso. Tutti i componenti ER richiesti verranno inoltre creati automaticamente, in base all'elenco di elementi denominati Excel rilevati.

![Selezione di Importa da Excel](./media/er-excel-format-import-template.png)

> [!NOTE]
> Se desideri creare l'elemento **Foglio** facoltativo nel formato ER modificabile, imposta l'opzione **Crea elemento in formato foglio Excel** su **Sì**.

## <a name="sheet-component"></a>Componente foglio

Il componente **Foglio** indica un foglio di lavoro della cartella di lavoro Excel allegata che deve essere compilato. Il nome del foglio di lavoro in un modello di Excel è definito nella proprietà **Foglio** di questo componente.

> [!NOTE]
> Questo componente è facoltativo per le cartelle di lavoro di Excel che contengono un singolo foglio di lavoro.

Nella scheda **Mappatura** della progettazione dell'operazione ER, puoi configurare la proprietà **Enabled** per un componente **Foglio** per specificare se il componente deve essere inserito in un documento generato:

- Se un'espressione della proprietà **Enabled** è configurata per tornare su **True** in fase di runtime o se nessuna espressione è configurata, il foglio di lavoro appropriato verrà inserito nel documento generato.
- Se un'espressione della proprietà **Enabled** è configurata per tornare su **False** in fase di runtime, il documento generato non conterrà un foglio di lavoro.

![Esempio di un componente Foglio](./media/er-excel-format-sheet-component.png)

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

## <a name="edit-an-added-er-format"></a>Modifica un formato ER aggiunto

### <a name="update-a-template"></a>Aggiorna un modello

Puoi selezionare **Aggiorna da Excel** nella scheda **Importa** del riquadro azioni per importare un modello aggiornato in un formato ER modificabile. Durante questo processo, un modello del componente **Excel\\File** selezionato verrà sostituito da un nuovo modello. Il contenuto del formato ER modificabile verrà sincronizzato con il contenuto del modello ER aggiornato.

- Un nuovo componente in formato ER verrà automaticamente creato per ogni nome Excel se il componente in formato ER non viene trovato nel formato modificabile.
- Ogni componente del formato ER verrà eliminato dal formato ER modificabile se non viene trovato il nome Excel appropriato per esso.

> [!NOTE]
> Imposta l'opzione **Crea elemento in formato foglio Excel** su **Sì** se desideri creare l'elemento **Foglio** opzionale nel formato ER modificabile.
>
> Se il formato ER modificabile era originariamente contenuto negli elementi **Foglio**, ti consigliamo di impostare l'opzione **Crea elemento in formato foglio Excel** su **Sì** quando importi un modello aggiornato. Altrimenti, tutti gli elementi nidificati dell'elemento originale **Foglio** verrà creato da zero. Pertanto, tutti i collegamenti degli elementi di formato ricreati andranno persi nel formato ER aggiornato.

![Crea l'opzione dell'elemento del formato del foglio Excel nella finestra di dialogo Aggiorna da Excel](./media/er-excel-format-update-template.png)

Per saperne di più su questa funzionalità, segui i passaggi in [Modificare i formati per la creazione di report elettronici riapplicando modelli di Excel](modify-electronic-reporting-format-reapply-excel-template.md).

## <a name="validate-an-er-format"></a>Convalida un formato ER

Quando si convalida un formato ER che può essere modificato, viene eseguito un controllo di coerenza per assicurarsi che il nome Excel sia presente nel modello Excel attualmente utilizzato. Riceverai una notifica di eventuali incoerenze. Per alcune incoerenze, verrà offerta l'opzione per risolvere automaticamente i problemi.

![Messaggio di errore di convalida](./media/er-excel-format-validate.png)

## <a name="control-the-calculation-of-excel-formulas"></a>Controllare il calcolo delle formule di Excel

Quando viene generato un documento in uscita in un formato di cartella di lavoro Microsoft Excel, alcune celle di questo documento potrebbero contenere formule Excel. Quando la funzionalità **Abilita l'utilizzo della libreria EPPlus nel framework di creazione report elettronici** è abilitata, è possibile controllare quando le formule vengono calcolate modificando il valore del parametro **Opzioni di calcolo** [nel](https://support.microsoft.com/office/change-formula-recalculation-iteration-or-precision-in-excel-73fc7dac-91cf-4d36-86e8-67124f6bcce4#ID0EAACAAA=Windows) modello Excel in uso:

- Selezionare **Automatico** per ricalcolare tutte le formule dipendenti ogni volta che un documento generato viene aggiunto da nuovi intervalli, celle, ecc.
    >[!NOTE]
    > Ciò potrebbe causare un problema di prestazioni per i modelli di Excel che contengono più formule correlate.
- Selezionare **Manuale** per evitare il ricalcolo della formula quando viene generato un documento.
    >[!NOTE]
    > Il ricalcolo delle formule viene forzato manualmente quando un documento generato viene aperto per l'anteprima utilizzando Excel.
    > Non utilizzare questa opzione se si configura una destinazione ER che presuppone l'utilizzo di un documento generato senza la sua anteprima in Excel (conversione PDF, invio di e-mail, ecc.) perché il documento generato potrebbe non contenere valori nelle celle che contengono formule.

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica sui report elettronici](general-electronic-reporting.md)

[Progettare una configurazione per la creazione di report nel formato OPENXML](tasks\er-design-reports-openxml-2016-11.md)

[Modificare i formati per la creazione di report elettronici riapplicando modelli di Excel](modify-electronic-reporting-format-reapply-excel-template.md)

[Utilizzare intervalli espandibili orizzontalmente per aggiungere dinamicamente le colonne in report di Excel](tasks/er-horizontal-1.md)

[Incorporare immagini e forme nei documenti generati utilizzando ER](electronic-reporting-embed-images-shapes.md)

[Configurare la creazione di report elettronici (ER) per eseguire il pull dei dati in Power BI](general-electronic-reporting-report-configuration-get-data-powerbi.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]