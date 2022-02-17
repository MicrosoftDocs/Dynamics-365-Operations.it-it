---
title: Importare dati da file selezionati manualmente in modalità batch
description: Questo argomento spiega come importare i dati dai file selezionati manualmente in modalità batch.
author: NickSelin
ms.date: 01/07/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, ERImportFormatSourceTable, ERWorkspace
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2022-01-01
ms.dyn365.ops.version: Release 10.0.25
ms.openlocfilehash: 8615b5a0623fd696c64f4ec03e481a2bcb16c0ac
ms.sourcegitcommit: 89655f832e722cefbf796a95db10c25784cc2e8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/31/2022
ms.locfileid: "8075612"
---
# <a name="import-data-from-manually-selected-files-in-batch-mode"></a>Importare dati da file selezionati manualmente in modalità batch

[!include[banner](../includes/banner.md)]
[!include[banner](../includes/preview-banner.md)]

Per utilizzare il framework [Creazione di report elettronici (ER)](general-electronic-reporting.md) per importare i dati dai file in entrata selezionati manualmente in modalità batch, configura un [formato](er-overview-components.md#format-component) ER che supporta l'importazione. Quindi esegui un [mapping del modello](er-overview-components.md#model-mapping-component) del tipo **A destinazione** che utilizza quel formato come origine dati. Per importare i dati, accedi al file da importare e selezionano manualmente. 

La nuova funzionalità di ER che supporta l'importazione dei dati in modalità batch abilita la configurazione di questo processo come automatico. È possibile utilizzare le configurazioni ER per eseguire l'importazione dei dati pianificando un nuovo processo batch dall'interfaccia utente (UI) di ER.

Questo argomento spiega come completare l'importazione di dati da un file selezionato manualmente in modalità batch. Gli esempi utilizzano transazioni fornitore come dati aziendali. I passaggi in questi esempi possono essere completati nella società **USMF**. Non è richiesta alcuna codifica.

## <a name="prerequisites"></a>Prerequisiti

Per completare gli esempi in questo argomento, è necessario disporre del seguente accesso:

- Uno dei seguenti ruoli:

    - Sviluppatore per la creazione di report elettronici
    - Consulente funzionale per la creazione di report elettronici
    - Amministratore di sistema

- Configurazioni di modelli e formati ER per pagamenti con imposta 1099

### <a name="create-the-required-er-configurations"></a>Creare le configurazioni di ER richieste

Per creare le configurazioni ER richieste e ottenere altri prerequisiti, segui uno di questi passaggi:

- Riprodurre le guide attività **ER Importare i data da un file di Microsoft Excel**, che fanno parte del processo aziendale **7.5.4.3 Acquisire/sviluppare componenti di soluzioni/servizi IT (10677)**. Queste guide attività illustrano in dettaglio il processo di progettazione e di utilizzo delle configurazioni ER per importare in modo interattivo transazioni fornitori da file di Microsoft Excel. Per ulteriori informazioni, vedere [Analizzare i documenti in entrata in formato Excel](parse-incoming-documents-excel.md).
- Completa gli esempi in [Configurare l'importazione dei dati da SharePoint](er-configure-data-import-sharepoint.md). Questi esempi illustrano in dettaglio il processo di progettazione e di utilizzo delle configurazioni ER che importano in modo interattivo transazioni fornitori da file Excel archiviati in una cartella di SharePoint.

### <a name="download-the-required-er-configurations"></a>Scaricare le configurazioni di ER richieste

1. Scarica le seguenti configurazioni ER e salvare in locale.

    | Descrizione contenuto | File |
    |---------------------|------|
    | Configurazione del modello di dati ER **1099 Modello pagamenti** | [1099model.xml](https://download.microsoft.com/download/b/d/9/bd9e8373-d558-4ab8-aa9b-31981adc97ea/1099model.xml) |
    | Configurazione del formato ER **Formato per importazione transazioni fornitori (Excel)** | [1099format-import-from-excel.xml](https://download.microsoft.com/download/b/3/8/b38faf0a-fbaf-4e9e-84c2-dedae7464880/1099format-import-from-excel.xml) |

2. Utilizza l'opzione ER [Carica da file XML](er-defer-sequence-element.md#import-the-sample-er-configurations) per importare le configurazioni ER scaricate nella tua istanza di Dynamics 365 Finance nel seguente ordine:

    1. Configurazione del modello di dati ER
    2. Configurazione di formato ER

### <a name="download-the-required-excel-files"></a>Scaricare i file Excel richiesti

- Scarica il seguente set di dati di esempio e salvalo in locale.

    | Descrizione contenuto | File |
    |---------------------|------|
    | File **1099import-data.xlsx** che contiene dati di esempio per l'importazione | [1099import-data.xlsx](https://download.microsoft.com/download/f/f/4/ff4dbce9-8364-4391-adee-877945ff01f7/1099import-data.xlsx) |

### <a name="review-the-prerequisites"></a>Rivedere i prerequisiti

1. Andare a **Amministrazione organizzazione** \> **Creazione di report elettronici** \> **Configurazioni**.
2. Nella pagina **Configurazioni**, rivedi la soluzione ER preparata per l'importazione dei dati in modalità batch.
3. Rivedi la configurazione del formato **Per importare transazioni fornitori (Excel)**.

    - Il componente di formato di questa configurazione è progettato per analizzare un file Excel in entrata.
    - Il componente di mapping del modello di questa configurazione viene utilizzato per compilare il modello di dati di base utilizzando i dati del file Excel analizzato.

    ![Configurazione del formato ER per l'importazione dei dati in modalità batch dall'interfaccia utente di ER.](./media/er-configure-data-import-batch-configurations-1.png)

4. Rivedi la configurazione del modello di dati ER **1099 Modello pagamenti**.

    - Il componente di modello di questa configurazione rappresenta la struttura contiene del modello di dati utilizzata per trasmettere i dati tra i componenti ER in esecuzione.
    - Il componente di mapping del modello di questa configurazione viene utilizzato per estrarre i dati dal componente di formato eseguito e quindi aggiornare le tabelle dell'applicazione.

    ![Configurazione del modello di dati ER per l'importazione dei dati in modalità batch dall'interfaccia utente di ER.](./media/er-configure-data-import-batch-configurations-2.png)

5. Apri il file **1099import-data.xlsx** in Excel.

    ![File Excel di esempio con dati per l'importazione in modalità batch.](./media/er-configure-data-import-batch-excel-content.png)

## <a name="enable-batch-data-import-for-er-from-the-ui"></a>Abilitare l'importazione di dati in batch per ER dall'interfaccia utente

1. Andare a **Amministrazione sistema** \> **Aree di lavoro** \> **Gestione funzionalità**.
2. Nell'area di lavoro **Gestione funzionalità**, seleziona la funzionalità **Esegui importazione ER di documenti caricati manualmente in batch**, quindi seleziona **Abilita ora**.

## <a name="import-data-from-manually-selected-excel-files"></a>Importare dati da file Excel selezionati manualmente

1. Andare a **Amministrazione organizzazione** \> **Creazione di report elettronici** \> **Configurazioni**.
2. Nella pagina **Configurazioni**, seleziona la configurazione del modello di dati **1099 Modello pagamenti**.
3. Nella Scheda dettagli **Componenti di configurazione**, seleziona il collegamento **Per l'importazione manuale delle transazioni 1099**.
4. Nella pagina **Mapping da modello a origine dati**, il modello **Per l'importazione manuale delle transazioni 1099** è preselezionato. Selezionare **Esegui**.
5. Nella scheda **Parametri** seleziona **Sfoglia**. Trova e seleziona il file **1099import-data.xlsx**, quindi seleziona **OK**.
6. Nel campo **Immetti ID giustificativo**, immetti **V-00001**.
7. Nella scheda **Esegui in background**, imposta l'opzione **Elaborazione batch** su **Sì**.

    Tieni presente che il campo **Descrizione attività** è impostato su **Esecuzione del mapping di modelli "Per l'importazione manuale delle transazioni 1099", configurazione "1099 Modello pagamenti"**. Questo valore indica che l'esecuzione del mapping del modello selezionato verrà pianificata come un nuovo processo batch.

    ![Specificare i dettagli dell'importazione dati in modalità batch nella finestra di dialogo Parametri report elettronici.](./media/er-configure-data-import-batch-execution-parameters.png)

8. Seleziona **OK**. Un messaggio informa che è stato pianificato un nuovo processo batch.

    ![Messaggio relativo a un nuovo processo batch pianificato nella pagina di mapping del modello all'origine dati.](./media/er-configure-data-import-batch-scheduled-job-info.png)

## <a name="review-the-data-import-results-on-the-batch-job-page"></a>Esaminare i risultati dell'importazione dei dati nella pagina Processo batch

1. Vai a **Elementi comuni** \> **Richieste di informazioni** \> **Processi batch** \> **Processi batch personali**.
2. Nella pagina **Processo batch**, filtra l'elenco dei processi batch per trovare il batch pianificato, quindi selezionalo.
3. Seleziona il collegamento **ID processo** per rivedere i dettagli del lavoro.
4. Nella scheda dettaglio **Attività batch**, seleziona **Registro**.

    ![Pulsante Registro nella pagina Processo batch.](./media/er-configure-data-import-batch-scheduled-job-record.png)

5. Rivedi i dettagli dell'esecuzione.

    ![Registro di esecuzione del processo batch pianificato nella pagina Processo batch.](./media/er-configure-data-import-batch-scheduled-job-log.png)

## <a name="change-the-data-import-parameters"></a>Modificare i parametri di importazione dei dati

Dopo che il batch è stato pianificato e anche se non è stato ancora eseguito, puoi modificare i parametri dell'importazione dei dati pianificata.

1. Vai a **Elementi comuni** \> **Richieste di informazioni** \> **Processi batch** \> **Processi batch personali**.
2. Nella pagina **Processo batch**, filtra l'elenco dei processi batch per trovare il batch pianificato, quindi selezionalo.
3. Selezionare **Cambia stato**.
4. Nella finestra di dialogo **Seleziona nuovo stato**, seleziona **Trattenuto** e quindi **OK**.
5. Seleziona il collegamento **ID processo** per accedere ai dettagli del lavoro.
6. Nella scheda dettaglio **Attività batch**, seleziona **Parametri**.
7. Nella finestra di dialogo **Parametri per la creazione di report elettronici**, segui questi passaggi.

    1. Seleziona **Sfoglia** per selezionare il file alternativo per l'importazione dei dati.
    2. Seleziona **Immetti ID giustificativo** per modificare il numero del giustificativo per l'importazione delle transazioni fornitore.

        ![Modifica dei parametri dell'importazione dati per il processo batch pianificato nella finestra di dialogo Parametri report elettronici.](./media/er-configure-data-import-batch-scheduled-job-parameters.png)

    3. Seleziona **OK**.

8. Assicurati che il batch sia ancora selezionato, quindi seleziona di nuovo **Modifica stato**.
9. Nella finestra di dialogo **Seleziona nuovo stato**, seleziona **In attesa** e quindi **OK**.

## <a name="review-the-data-import-results-on-the-er-source-page"></a>Esaminare i risultati dell'importazione dei dati nella pagina di origine ER

1. Vai a **Amministrazione organizzazione** \> **Creazione di report elettronici** \> **Origine creazione di report elettronici**.
2. Seleziona il record **Per importazione transazioni fornitori (Excel)** che è stato creato automaticamente durante l'importazione dei dati.

    ![Record per la configurazione Per l'importazione delle transazioni dei fornitori (Excel) nella pagina di origine Creazione di report elettronici.](./media/er-configure-data-import-batch-files-source-1.png)

3. Seleziona **Stati dei file per le origini**.
4. Nelle Schede dettaglio **File** e **Registri di origine per il formato di importazione**, rivedi i dettagli di importazione.
5. Nella scheda dettaglio **File**, seleziona il record. Tieni presente che il file importato è allegato a questo record.

    ![File importato allegato al record nella pagina Stati file per le origini.](./media/er-configure-data-import-batch-files-source-2.png)

6. Seleziona **Allegati** per rivedere il file importato.

    ![File importato nella pagina di visualizzazione del documento.](./media/er-configure-data-import-batch-files-source-3.png)

    > [!TIP]
    > Per mantenere questi allegati, il framework ER utilizza un tipo di documento che è [impostato](electronic-reporting-er-configure-parameters.md#parameters-to-manage-documents) per l'attuale società nel campo **Altri** dei parametri ER.

## <a name="review-the-data-import-results-on-the-vendor-settlement-for-1099s-page"></a>Esaminare i risultati dell'importazione dei dati nella pagina Liquidazione fornitore per 1099

1. Passa a **Contabilità fornitori** \> **Attività periodiche** \> **Imposta 1099** \> **Liquidazione fornitore per i moduli 1099**.
2. Nel campo **Dal**, immetti **31/12/2017** (31 dicembre 2017).
3. Seleziona **Transazioni 1099 manuali**.

    ![Transazioni fornitore importate nella pagina delle transazioni Imposta 1099.](./media/er-configure-data-import-batch-imported-data.png)

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica sui report elettronici](general-electronic-reporting.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
