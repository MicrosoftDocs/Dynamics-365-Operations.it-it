---
title: Incorporare immagini e forme nei documenti generati utilizzando ER
description: Questo articolo spiega come utilizzare lo strumento Creazione di report elettronici per generare documenti aziendali con immagini e forme incorporate.
author: NickSelin
ms.date: 04/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EROperationDesigner, ERParameters
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 27621
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: fe0e6d6def50670566f44cfb5cd6bb4abe5faf15
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8851050"
---
# <a name="embed-images-and-shapes-in-documents-that-you-generate-by-using-er"></a>Incorporare immagini e forme nei documenti generati utilizzando ER

[!include [banner](../includes/banner.md)]

È possibile utilizzare lo strumento Creazione di report elettronici (ER) per progettare report che è possibile eseguire per generare i documenti elettronici richiesti. È possibile usare documenti Microsoft Excel o Microsoft Word per specificare il layout di un report. La pagina della progettazione delle operazioni ER consente di allegare il documento Excel o Word come modello per il report. I seguenti elementi denominati nel modello allegato sono associati agli elementi di formato del report ER: Gli elementi di formato del report sono associati alle origini dati. Questi elementi specificano i dati che verranno inseriti, al runtime, nei documenti generati.

Questa nuova funzionalità va oltre le funzionalità esistenti di ER per la creazione di documenti nei formati Microsoft Office. Per ulteriori informazioni, riprodurre le guide attività che seguono. È possibile trovare queste guide attività nel processo aziendale 7.5.4.3 Acquisire/sviluppare componenti di servizi/soluzioni IT (10677).

- ER progetta una configurazione per la creazione di report nel formato OPENXML
- ER progetta una configurazione per la generazione di report in formato Microsoft WORD

## <a name="embed-an-image-in-an-excel-document"></a>Incorporare un'immagine in un documento Excel

### <a name="embed-an-image-in-an-excel-worksheet"></a>Incorporare un'immagine in un foglio di lavoro Excel

Innanzitutto, è necessario aggiungere un segnaposto per l'immagine in un documento Excel. Aprire una cartella di lavoro di Excel e aggiungere un'immagine come segnaposto per l'immagine che si aggiungerà in seguito. Quindi utilizzare lo strumento ER per aggiungere una nuova configurazione del formato ER per includere il report che si sta progettando. Allegare la cartella di lavoro di Excel come modello per il formato del report, quindi importare il contenuto della cartella di lavoro nel formato ER. La definizione del formato verrà creata automaticamente. Il segnaposto immagine aggiunto sarà incluso nella definizione del formato ER come elemento **CELL**.

> [!NOTE]
> È possibile specificare manualmente la definizione del formato invece di importarla. Quando si salvano le modifiche, il formato verrà convalidato.

Quindi, associare l'elemento **CELL** del formato ER al campo dall'origine dati del formato che fornisce i dati dell'immagine in formato binario al runtime. Quando un modello di dati ER viene utilizzato come origine dati di un formato, il tipo di dati del campo deve essere [Contenitore](er-formula-supported-data-types-composite.md#container). Attualmente, un campo del modello di dati ER che ha il tipo di dati [Contenitore](er-formula-supported-data-types-composite.md#container) può essere associato a diversi tipi di origini dati che restituiscono immagini in formato binario. È possibile accedere a un campo in una tabella di dati e a un file allegato al record della tabella di dati utilizzando il framework di gestione documenti.

> [!IMPORTANT]
> - Per riempire il segnaposto dell'immagine nel documento che si sta creando utilizzando il modello Excel, il formato ER deve contenere l'elemento **CELL** che fa riferimento all'elemento immagine denominato nel modello di Excel. In caso contrario, nell'output del report non verrà visualizzato alcun segnaposto immagine. Se l'associazione di un elemento **CELL** non restituisce dati al runtime, il documento generato mostrerà il segnaposto dell'immagine dal modello. Per nascondere un'immagine nel documento che si sta generando, definire un elemento **CELL** e specificare che l'espressione **Abilitare** dovrebbe restituire un valore di **FALSO**.
> - Nel modello Excel usare un nome univoco per ogni elemento. Questi elementi includono immagini e celle. Se si duplica il nome di un elemento, il contenuto del report che viene generato sarà ambiguo e confuso.

### <a name="embed-images-in-the-header-and-footer-of-an-excel-worksheet"></a>Incorporare immagini nell'intestazione e nel piè di pagina di un foglio di lavoro Excel

Utilizzare il documento della cartella di lavoro di Excel come modello per specificare il layout di un report. La cartella di lavoro può contenere più fogli di lavoro, ognuno dei quali può essere progettato in modo che abbia un'intestazione e un piè di pagina. Excel supporta fino a tre immagini nell'intestazione e nel piè di pagina di ogni foglio di lavoro. Le immagini possono essere allineate a sinistra, a destra o al centro.

Nella versione Finance 10.0.21 è possibile gestire le immagini di intestazione e piè di pagina generate da una soluzione ER che dispone di un modello Excel.

Se si desidera che un'immagine predefinita venga visualizzata nell'intestazione o nel piè di pagina di un documento generato, è possibile aggiungere un'immagine all'intestazione o al piè di pagina di un foglio di lavoro di un modello ER. Per accedere a questa immagine nel formato ER, è necessario aggiungere il componente **Immagine** nel componente [Intestazione](er-fillable-excel.md#header-component) o [Piè di pagina](er-fillable-excel.md#footer-component) del formato. Configurare l'allineamento del componente **Immagine**, a seconda dei casi. 

È possibile anche usare il componente **Immagine** per inserire un'immagine nell'intestazione o nel piè di pagina di un documento generato al runtime, anche se il modello non contiene un'immagine predefinita. Per specificare il contenuto multimediale da inserire nell'intestazione o nel piè di pagina di un documento generato come nuova immagine o come sostituzione di un'immagine predefinita, è necessario associare il componente **Immagine** a un'origine dati del tipo [Contenitore](er-formula-supported-data-types-composite.md#container) che rappresenta un'immagine in formato binario.

Ogni componente **Intestazione** o **Piè di pagina** può contenere un componente **Immagine** per ogni allineamento supportato: **Sinistra**, **Centro** e **Destra**.

La proprietà **Scala altezza** del componente **Immagine** consente di utilizzare l'associazione configurata per controllare la dimensione di un'immagine:

- Selezionare **Originale** per mantenere la dimensione iniziale dell'immagine.
- Selezionare **Relativo** per ridimensionare l'altezza dell'immagine in proporzione all'altezza dell'intestazione o del piè di pagina che contiene quell'immagine.

    - In questo caso, l'altezza dell'immagine deve essere definita come percentuale dell'intestazione o del piè di pagina padre.
    - Se il valore di ridimensionamento supera il 100%, l'immagine potrebbe sovrapporsi all'area dati del foglio di lavoro corrispondente.
    - Se l'altezza dell'immagine viene modificata quando viene applicata la scala, anche la larghezza viene modificata per mantenere le proporzioni originali dell'immagine.

- Selezionare **Assoluto** per ridimensionare l'immagine in base ai valori di altezza e larghezza (in pixel) forniti in fase di progettazione.

    - Se l'altezza specificata supera l'altezza dell'intestazione o del piè di pagina padre, l'immagine potrebbe sovrapporsi all'area dati del foglio di lavoro corrispondente.

È possibile anche usare la proprietà **Abilitato** del componente **Immagine** per controllare la visibilità di un'immagine inserita in un documento generato utilizzando questo componente.

> [!NOTE]
> È necessario utilizzare il designer del formato ER per aggiungere un componente **Immagine** nel formato ER modificabile. Non è possibile aggiungere il componente quando si usa l'area di lavoro [Gestione documenti aziendali](er-business-document-management.md) per modificare il modello di un documento aziendale.

Per saperne di più su questa funzionalità, seguire i passaggi in [Progettare un formato ER per generare un report in formato Excel con immagini incorporate nelle intestazioni o piè di pagina](er-embed-images-header-footer-excel-reports.md).

## <a name="embed-a-shape-in-an-excel-document"></a>Incorporare una forma in un documento Excel

Innanzitutto, è necessario aggiungere un segnaposto per la forma in un documento Excel. Aprire una cartella di lavoro di Excel e selezionare **Forma**, **Casella di testo** o **WordArt** come segnaposto per la forma. Quindi utilizzare lo strumento ER per aggiungere una nuova configurazione del formato ER per includere il report che si sta progettando. Allegare la cartella di lavoro di Excel come modello per il formato del report, quindi importare il contenuto della cartella di lavoro nel formato ER. La definizione del formato verrà creata automaticamente. Il segnaposto della forma aggiunto verrà incluso nella definizione del formato ER come elemento **CELL** che fa riferimento all'elemento di forma Excel denominato.

> [!NOTE]
> È possibile specificare manualmente la definizione del formato invece di importarla. Quando si salvano le modifiche, il formato verrà convalidato.

Quindi, associare l'elemento **CELL** nel formato ER al campo dall'origine dati del formato che fornisce i dati al runtime. Questi dati possono essere convertiti in una stringa di testo. Quando l'elemento **CELL** nel formato ER fa riferimento a un elemento forma nel modello Excel che supporta il testo, il testo fornito tramite questa associazione al runtime verrà mostrato in una forma nel documento che viene generato.

> [!IMPORTANT]
> - Se si desidera utilizzare il modello Excel che include il segnaposto della forma per generare un nuovo documento, il formato ER deve contenere un elemento **CELL** che fa riferimento all'elemento forma di Excel. In caso contrario, nell'output del report non verrà visualizzato alcun segnaposto forma. Se l'associazione di un elemento **CELL** che fa riferimento all'elemento della forma Excel denominato non restituisce alcun dato al runtime, il documento generato mostrerà il testo del segnaposto della forma dal modello Excel. Per nascondere una forma nel documento che si sta generando, definire un elemento **CELL** che fa riferimento all'elemento forma di Excel denominata e specificare che l'espressione **Abilitare** dovrebbe restituire un valore di **FALSO**.
> - Nel modello Excel usare un nome univoco per ogni elemento. Questi elementi includono forme e celle. Se si duplica il nome di un elemento, il contenuto del report che viene generato sarà ambiguo e confuso.

## <a name="embed-an-image-in-a-word-document"></a>Incorporare un'immagine in un documento Word
> [!IMPORTANT]
> È possibile riutilizzare il formato ER che usa un modello Excel per creare documenti che includono immagini incorporate. Nel formato ER assicurarsi che sia specificato un nome per l'elemento **CELL** che fa riferimento a un elemento immagine denominato in Excel e che è associato a un'origine dati che restituisce un'immagine al runtime.

Innanzitutto, è necessario configurare il layout del documento di Word. Usare il controllo **Contenuto immagine** per creare un segnaposto per l'immagine incorporata. Per accedere a questo controllo, è necessario innanzitutto rendere visibile la scheda **Sviluppatore** sulla barra multifunzione di Word.

Quindi, eliminare il modello Excel dal formato ER e allegare il documento modello Word. Aggiornare il riferimento al modello e salvare le modifiche. La struttura gerarchica del formato ER corrente viene salvata nel modello Word come nuova parte XML personalizzata con il nome **Report**.

Quindi, salvare il modello Word per il formato ER corrente sul computer locale. Aprire il modello e aprire il riquadro **Mapping XML**. Trovare la parte XML personalizzata denominata **Report**, quindi puntare sul'elemento **CELL** nel report ER associato a un'origine dati che restituisce un'immagine in formato binario. Associare l'elemento di questa parte XML al controllo **Contenuto immagine** selezionato e salvare le modifiche.

[![incorporare immagini.](./media/embed-images-shapes-01.png)](./media/embed-images-shapes-01.png)

Infine, eliminare il modello di Word dal formato ER e allegare il documento di Word che include le parti XML personalizzate mappate. Aggiornare il riferimento al formato nel modello e salvare le modifiche apportate a questo formato ER.

## <a name="more-information"></a>Ulteriori informazioni
Per familiarizzare con i dettagli di questa funzionalità, riprodurre la serie di guide attività, **ER Creare report in formati di Microsoft Office con immagini incluse**. Queste guide attività mostrano come incorporare le immagini di un logo aziendale e la firma di una persona autorizzata negli assegni di pagamento generati utilizzando lo strumento ER nei documenti Excel e Word.

La tabella seguente elenca i file necessari per completare le guide attività **ER Creare report in formati di Microsoft Office con immagini incluse**. Scaricare e salvare i file nel computer locale.

| descrizione                                          | Nome file                   |
|------------------------------------------------------|-----------------------------|
| Configurazione del modello di dati ER                          | [Model for cheques.xml](https://download.microsoft.com/download/6/e/a/6ea166fd-1382-4fdb-8dcb-0f13379f9c8e/Modelforcheques.xml)       |
| Configurazione di formato ER                              | [Cheques printing format.xml](https://download.microsoft.com/download/1/7/c/17c301e3-c4ee-4886-ae75-440fcc002c8c/Chequesprintingformat.xml) |
| Immagine del logo dell'azienda                                   | [Company logo.png](https://download.microsoft.com/download/8/2/e/82e6bd81-caac-4e9a-bfce-1392ce7c8616/Companylogo.png)            |
| Immagine della firma                                      | [Signature image.png](https://download.microsoft.com/download/5/0/9/509151b3-06fc-4870-9408-7c9a43b72771/Signatureimage.png)         |
| Immagine della firma alternativa                          | [Signature image 2.png](https://download.microsoft.com/download/3/0/0/30045bf1-0ff6-4215-9162-b77c2f5dcc7c/Signatureimage2.png)       |
| Modello di Microsoft Word per la stampa di assegni di pagamento  | [Cheque template Word.docx](https://download.microsoft.com/download/4/4/d/44d9d255-9ad1-42fe-87db-23f319fd8e89/ChequetemplateWord.docx)   |
| Modello di Microsoft Excel per la stampa di assegni di pagamento | [Cheque template.xlsx](https://download.microsoft.com/download/1/f/6/1f671963-73aa-48d5-ae69-45f21fe7dfb4/Cheque%20template.xlsx)        |

Il grafico seguente fornisce un esempio della stampa di prova per un assegno di pagamento generato dal modello Excel.

[![Stampa di prova dell'assegno di pagamento.](./media/embed-images-shapes-02.png)](./media/embed-images-shapes-02.png)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
