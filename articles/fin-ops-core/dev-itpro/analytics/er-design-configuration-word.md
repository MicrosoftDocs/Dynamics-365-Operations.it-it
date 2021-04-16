---
title: Progettare una nuova configurazione ER per generare report in formato Word
description: Questo argomento spiega come gli utenti possono configurare un nuovo formato Creazione di report elettronici (ER) per generare report come documenti di Microsoft Word.
author: NickSelin
ms.date: 12/17/2020
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, EROperationDesigner,  LedgerJournalTable, LedgerJournalTransVendPaym
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-01-01
ms.dyn365.ops.version: Version 10.0.6
ms.openlocfilehash: 4885caf017fa0f9d36d293fa32aad53c21d3f162
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5753578"
---
# <a name="design-a-new-er-configuration-to-generate-reports-in-word-format"></a>Progettare una nuova configurazione ER per generare report in formato Word

[!include [banner](../includes/banner.md)]

Per generare report come documenti di Microsoft Word, è necessario progettare un modello per i report utilizzando, ad esempio, l'applicazione desktop Word. La seguente illustrazione mostra il modello di esempio per il report di controllo che può essere generato per mostrare i dettagli dei pagamenti fornitore elaborati.

![Modello di esempio per il report di controllo nell'applicazione desktop di Word](./media/er-design-configuration-word-image1.png)

Per utilizzare un documento Word come modello per report in formato Word, è possibile configurarne una nuova [soluzione](er-quick-start1-new-solution.md) di [Creazione di report elettronici (ER)](general-electronic-reporting.md). Questa soluzione deve includere una [configurazione](general-electronic-reporting.md#Configuration) ER che contiene un componente di [formato](general-electronic-reporting.md#FormatComponentOutbound) ER.

> [!NOTE]
> Quando si crea una nuova configurazione del formato ER per generare report in formato Word, è necessario selezionare **Word** come tipo di formato nella finestra di dialogo a discesa **Crea configurazione** o lasciare vuoto il campo **Tipo di formato**.

![Creazione di una configurazione di formato personalizzata nella pagina Configurazioni](./media/er-design-configuration-word-image2.gif)

Il componente di formato ER della soluzione deve contenere l'elemento di formato **Excel\\File** e tale elemento di formato deve essere collegato al documento di Word che verrà utilizzato come modello per i report generati in fase di esecuzione. Per configurare il componente formato ER, è necessario aprire la versione [bozza](general-electronic-reporting.md#component-versioning) della configurazione ER creata nella finestra di progettazione del formato ER. Quindi aggiungere l'elemento **Excel\\File**, allegare il modello di Word al formato ER modificabile e collegare tale modello all'elemento **Excel\\File** aggiunto.

> [!NOTE]
> Quando si collega manualmente un modello, devi utilizzare un [tipo di documento](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/configure-document-management#configure-document-types) che è stato [configurato](electronic-reporting-er-configure-parameters.md#parameters-to-manage-documents) in precedenza nei parametri ER per archiviare i modelli dei formati ER.

![Allegare un modello nella pagina Progettazione formati](./media/er-design-configuration-word-image3.gif)

Puoi aggiungere gli elementi nidificati **Excel\\Intervallo** ed **Excel\\Cella** per l'elemento **Excel\\File** per specificare la struttura dei dati che verranno immessi nei report generati in fase di esecuzione. È quindi necessario associare tali elementi alle origini dati del formato ER modificabile per specificare i dati effettivi che verranno immessi nei report generati in fase di esecuzione.

![Aggiunta degli elementi nidificati nella pagina Progettazione formati](./media/er-design-configuration-word-image4.gif)

Quando si salvano le modifiche al formato ER in fase di progettazione, la struttura gerarchica del formato viene archiviata nel modello Word allegato come [parte XML personalizzata](https://docs.microsoft.com/visualstudio/vsto/custom-xml-parts-overview?view=vs-2019) denominata **Report**. È necessario accedere al modello modificato, scaricarlo da Finance, archiviarlo localmente e aprirlo nell'applicazione desktop Word. La figura seguente mostra il modello di esempio archiviato localmente per il report di controllo che contiene la parte XML personalizzata **Report**.

![Visualizzazione in anteprima del modello di report di esempio nell'applicazione desktop di Word](./media/er-design-configuration-word-image5.gif)

Quando le associazioni degli elementi di formato **Excel\\Intervallo** e **Excel\\Cella** vengono eseguiti in fase di esecuzione, i dati forniti da ogni associazione entrano nel documento Word generato come un singolo campo della parte XML personalizzata **Report**. Per inserire i valori dai campi della parte XML personalizzata in un documento generato, è necessario aggiungere i [controlli del contenuto](https://docs.microsoft.com/office/client-developer/word/content-controls-in-word) Word appropriati al modello di Word per fungere da segnaposto per i dati che verranno compilati in fase di esecuzione. Per specificare la modalità di compilazione dei controlli del contenuto, eseguire il mapping di ogni controllo del contenuto al campo appropriato della parte XML personalizzata **Report**.

![Aggiunta e mapping dei controlli del contenuto nell'applicazione desktop Word](./media/er-design-configuration-word-image6.gif)

È quindi necessario sostituire il modello di Word originale del formato ER modificabile con il modello modificato che ora contiene i controlli del contenuto di Word che sono stati mappati ai campi della parte XML personalizzata **Report**.

![Sostituzione del modello nella pagina Progettazione formati](./media/er-design-configuration-word-image7.gif)

Quando si esegue il formato ER configurato, il modello di Word allegato viene utilizzato per generare un nuovo report. I dati effettivi vengono archiviati nel report di Word come una parte XML personalizzata denominata **Report**. Quando il report generato viene aperto, i controlli del contenuto di Word vengono compilati con i dati della parte XML personalizzata **Report**.

## <a name="frequently-asked-questions"></a>Domande frequenti

**Domanda:** ho configurato un formato ER per stampare un documento Word che contiene un indirizzo aziendale. Nel modello Word per questo formato ER, ho inserito un controllo del contenuto di testo RTF per presentare un indirizzo aziendale. In Finanza, ho inserito l'indirizzo dell'azienda come testo su più righe e 'ho selezionato **INVIO** per aggiungere un ritorno a capo per ogni riga che ho inserito. Pertanto, mi aspetto che l'indirizzo dell'azienda appaia come testo su più righe nei documenti generati. Tuttavia, l'indirizzo viene visualizzato come una singola riga di testo che contiene simboli speciali anziché ritorni a capo. Cosa c'è di sbagliato nelle mie impostazioni?

**Risposta:** invece di utilizzare un controllo del contenuto di testo RTF, è necessario utilizzare un controllo del contenuto di testo semplice e selezionare la casella di controllo **Consenti ritorni a capo (più paragrafi)** nelle proprietà del controllo.

## <a name="additional-resources"></a>Risorse aggiuntive

- [Riutilizzare le configurazioni ER con i modelli Escel per generare report nel formato Word](./tasks/er-design-configuration-word-2016-11.md)
- [Incorporare immagini e forme nei documenti generati utilizzando ER](electronic-reporting-embed-images-shapes.md#embed-an-image-in-a-word-document)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]