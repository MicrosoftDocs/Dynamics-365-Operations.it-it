---
title: Configurare l'importazione di dati da SharePoint
description: In questo argomento viene descritto come importare i dati da Microsoft SharePoint.
author: NickSelin
manager: AnnBe
ms.date: 05/21/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2018-04-01
ms.dyn365.ops.version: Release 8.0
ms.translationtype: HT
ms.sourcegitcommit: 821d8927211d7ac3e479848c7e7bef9f650d4340
ms.openlocfilehash: 9f23f73e9a98fc50c622255bf6ed027c41ec8010
ms.contentlocale: it-it
ms.lasthandoff: 08/13/2018

---
# <a name="configure-data-import-from-sharepoint"></a>Configurare l'importazione di dati da SharePoint

[!include[banner](../includes/banner.md)]

Per importare dati da un file ricevuto utilizzando il framework di creazione di report elettronici (ER, electronic reporting), è necessario configurare un formato di ER che supporti l'importazione e quindi eseguire il mapping di modello del tipo **A destinazione** che utilizza quel formato come origine dati. Per importare i dati, è necessario passare al file da importare. Il file ricevuto può essere selezionato manualmente dall'utente. Con la nuova funzionalità di ER per supportare l'importazione dei dati da Microsoft SharePoint, questo processo può essere configurato come quello automatico. È possibile utilizzare le configurazioni di ER per eseguire l'importazione di dati dai file che sono archiviati in cartelle di Microsoft SharePoint. In questo argomento viene descritto come completare l'importazione da SharePoint in Microsoft Dynamics 365 for Finance and Operations. Gli esempi utilizzano transazioni fornitore come dati aziendali.

## <a name="prerequisites"></a>Prerequisiti
Per completare gli esempi in questo argomento, è necessario disporre del seguente accesso:

- Accesso a Finance and Operations per uno dei seguenti ruoli:

    - Sviluppatore per la creazione di report elettronici
    - Consulente funzionale per la creazione di report elettronici
    - Amministratore di sistema

- Accesso all'istanza di Microsoft SharePoint Server configurato per l'utilizzo con Finance and Operations
- Configurazioni di formato ER e di modello per 1099 pagamenti

### <a name="create-required-er-configurations"></a>Creare le configurazioni di ER richieste
Riprodurre le guide attività  **ER Importare i data da un file di Microsoft Excel**, che fanno parte del processo aziendale **7.5.4.3 Acquisire/sviluppare componenti di soluzioni/servizi IT (10677)**. Queste guide attività illustrano in dettaglio il processo di progettazione e di utilizzo delle configurazioni ER per importare in modo interattivo transazioni fornitori da file di Microsoft Excel esterni. Per ulteriori informazioni, vedere [Analizzare i documenti ricevuti in Microsoft Excel](parse-incoming-documents-excel.md). Alla fine si avranno a disposizione:

- Configurazioni ER:

    - Configurazione del modello di ER, **1099 Modello pagamenti**
    - Configurazione del formato per ER, **Formato per importare transazioni fornitori da Excel**

    [![Configurazioni di ER per importare i dati da SharePoint](./media/GERImportFromSharePoint-01-Configurations.PNG)](./media/GERImportFromSharePoint-01-Configurations.PNG)

- Esempio di file ricevuto per l'importazione dei dati:

    - File di Excel **1099import-data.xlsx**, con transazioni fornitori che devono essere importate in Finance and Operations

    [![Esempio di file di Microsoft Excel per l'importazione da SharePoint](./media/GERImportFromSharePoint-02-Excel.PNG)](./media/GERImportFromSharePoint-02-Excel.PNG)

> [!NOTE]
> Il formato per l'importazione delle transazioni fornitori è selezionato come mapping di modello predefinito. Se quindi si esegue un mapping di modello del **1099 modello pagamenti** e quel mapping di modello è di tipo **A destinazione**, il mapping di modello esegue questo formato per importare i dati da file esterni. Utilizza quindi i dati per aggiornare le tabelle dell'applicazione.

## <a name="configure-document-management-parameters"></a>Configurare i parametri di gestione documenti
1. Nella pagina **Parametri di gestione documenti** configurare l'accesso all'istanza di SharePoint Server che verrà utilizzato dalla società a cui è stato eseguito l'accesso. In questo esempio, la società è USMF.
2. Verificare la connessione all'istanza di SharePoint Server per assicurarsi di disporre dell'accesso.

    [![Impostazione gestione documenti - server SharePoint](./media/GERImportFromSharePoint-03-SharePointSetup.png)](./media/GERImportFromSharePoint-03-SharePointSetup.png)

3. Aprire il sito di SharePoint configurato e creare le seguenti cartelle in cui verranno memorizzati i file ricevuti:

    - Origine di importazione dei file (principale)
    - Origine di importazione dei file (alternativa)

    [![Impostazione gestione documenti - server SharePoint](./media/GERImportFromSharePoint-04-SharePointFolder1.png)](./media/GERImportFromSharePoint-04-SharePointFolder1.png)

    [![Impostazione gestione documenti - server SharePoint](./media/GERImportFromSharePoint-05-SharePointFolder2.png)](./media/GERImportFromSharePoint-05-SharePointFolder2.png)

4. In Finance and Operations, nella pagina **Tipi di documento**, creare i seguenti tipi di documento che verranno utilizzati per accedere alle cartelle di SharePoint appena create:

    - Principale di SP
    - Alternativa di SP

5. Per i tipi di documento creati, nel campo **Gruppo**, immettere **File** e nel campo **Posizione** immettere **SharePoint**. Immettere quindi l'indirizzo della cartella SharePoint:

    - Per il tipo di documento **Principale di SP**: origine di importazione dei file (principale)
    - Per il tipo di documento **Alternativa di SP**: origine di importazione dei file (alternativa)

    [![Impostazione di SharePoint - nuovo tipo di documento](./media/GERImportFromSharePoint-06-SharePointDocumentTypesSetup.png)](./media/GERImportFromSharePoint-06-SharePointDocumentTypesSetup.png)

## <a name="configure-er-sources-for-the-er-format"></a>Configurare le origini di ER per il formato di ER
1. Fare clic su **Amministrazione organizzazione** \> **Creazione di report elettronici** \> **Origine creazione di report elettronici**.
2. Nella pagina **Origine creazione di report elettronici** configurare i file di origine per l'importazione dei dati utilizzando il formato di ER configurato.
3. Definire una maschera del nome di file, in modo che solo i file con estensione xlsx vengano importati. La maschera del nome di file è facoltativa e viene utilizzata solo quando è stata definita. È possibile definire una sola maschera per ogni formato di ER.
4. Selezionare entrambe le cartelle di SharePoint create in precedenza.

    [![Impostazione dell'origine dei file di ER](./media/GERImportFromSharePoint-07-FormatSourceSetup.PNG)](./media/GERImportFromSharePoint-07-FormatSourceSetup.PNG)

> [!NOTE]
> - L'*origine* di ER viene definita per ogni società dell'applicazione individualmente. Le *configurazioni* di ER vengono invece condivise tra le società.
> - Quando si elimina un'impostazione di origine di ER per un formato di ER, vengono eliminati anche tutti gli stati dei file connessi (vedere sotto).

## <a name="review-the-files-states-for-the-er-format"></a>Esaminare gli stati dei file per il formato di ER
1. Nella pagina **Origine creazione di report elettronici** selezionare **Stati dei file per le origini** per esaminare il contenuto delle origini dei file configurate per il formato di ER corrente.
2. Nella sezione **File** esaminare l'elenco dei file. Questo elenco presenta gli elementi seguenti:

    - File di origine applicabili, in base alla maschera del nome di file (se viene definita una maschera del nome di file), e pronti per l'importazione di dati. Per tali file, la sezione **Registri delle origini per il formato di importazione** è vuota.
    - File precedentemente importati. Per ognuno di questi file, nella sezione **Registri delle origini per il formato di importazione** è possibile esaminare la cronologia di importazione del file.

È inoltre possibile aprire la pagina **Stati dei file per le origini** selezionando **Amministrazione organizzazione** \> **Creazione di report elettronici** \> **Stati dei file per le origini**. In questo caso, la pagina fornisce informazioni sulle origini dei file per tutti i formati di ER per cui sono state configurate le origini dei file nella società a cui si è attualmente connessi.

## <a name="import-data-from-excel-files-that-are-in-a-sharepoint-folder"></a>Importare dati da file di Excel in una cartella di SharePoint
1. In SharePoint, caricare il file di Microsoft Excel denominato **1099import-data.xlsx**, contenente le transazioni fornitori, nella cartella di SharePoint **Origine di importazione dei file (principale)** creata in precedenza.

    [![Contenuto di SharePoint - file di Microsoft Excel per l'importazione](./media/GERImportFromSharePoint-08-UploadFile.png)](./media/GERImportFromSharePoint-08-UploadFile.png)

2. In Finance and Operations, nella pagina **Stati dei file per le origini** selezionare **Aggiorna** per aggiornare la pagina. Si noti che il file di Excel che è stato caricato in SharePoint viene visualizzato in questo modulo con lo stato **Pronto**. Al momento sono disponibili i seguenti stati:

    - **Pronto** - Assegnato automaticamente per ogni nuovo file in una cartella di SharePoint. Questo stato indica che il file è pronto per l'importazione.
    - **Importazione** - Assegnato automaticamente da un report di ER quando il file viene bloccato dal processo di importazione per impedirne l'utilizzo da parte di altri processi (nel caso in cui vengano eseguiti più processi contemporaneamente).
    - **Importato** - Assegnato automaticamente da un report di ER al termine della corretta importazione di file. Questo stato indica che il file importato è stato eliminato dall'origine di file configurata (cartella di SharePoint).
    - **Non riuscito** - Assegnato automaticamente da un report di ER quando l'importazione dei file genera errori o eccezioni.
    - **In attesa** - Assegnato manualmente dall'utente in questo modulo. Questo stato indica che il file non verrà importato per il momento. Questo stato può essere utilizzato per posticipare l'importazione di alcuni file.

    [![Pagina degli stati dei file di ER per le origini selezionate](./media/GERImportFromSharePoint-09-FileStatesForm.png)](./media/GERImportFromSharePoint-09-FileStatesForm.png)

## <a name="import-data-from-sharepoint-files"></a>Importare i dati da file di SharePoint
1. Aprire la struttura delle configurazioni di ER, selezionare **1099 Modello pagamenti** ed espandere l'elenco di componenti del modello di ER.
2. Selezionare il nome del mapping di modello per aprire l'elenco di mapping di modello della configurazione del modello di ER selezionata.

    [![Pagina degli stati dei file di ER per le origini selezionate](./media/GERImportFromSharePoint-10-SelectModelMapping.PNG)](./media/GERImportFromSharePoint-10-SelectModelMapping.PNG)

3. Selezionare **Esegui** per eseguire il mapping di modello selezionato. Poiché sono state configurate origini di file per il formato di ER, è possibile modificare l'impostazione dell'opzione **Origine file** in base alle proprie esigenze. Se si mantiene l'impostazione di questa opzione, i file con estensione xslx vengono importati dalle origini configurate (le cartelle di SharePoint, in questo esempio).

    In questo esempio, si importa un solo file. Se tuttavia sono presenti più file questi vengono selezionati per l'importazione nell'ordine in cui sono stati aggiunti nella cartella di SharePoint. Ogni esecuzione di un formato di ER importa un singolo file selezionato.

    [![Eseguire il mapping di modello di ER](./media/GERImportFromSharePoint-11-RunModelMapping.PNG)](./media/GERImportFromSharePoint-11-RunModelMapping.PNG)

4. Il mapping di modello può essere eseguito automaticamente nella modalità batch. In questo caso, ogni volta che si esegue un batch in questo formato di ER, viene importato un singolo file dalle origini di file configurate. Utilizzare il codice seguente per implementare l'esecuzione batch.

    ```
    ERObjectsFactory::createMappingDestinationRunByImportFormatMappingId().run()
    ```

    Quando un file viene importato correttamente dalla cartella di SharePoint, viene eliminato da tale cartella.

5. Immettere l'ID giustificativo, ad esempio **V-00001**, quindi selezionare **OK**.

    [![Eseguire il mapping di modello di ER](./media/GERImportFromSharePoint-12-ModelMappingRunFinished.PNG)](./media/GERImportFromSharePoint-12-ModelMappingRunFinished.PNG)

6. Nella pagina **Stati dei file per le origini** selezionare **Aggiorna** per aggiornare la pagina.

    [![Pagina degli stati dei file di ER per le origini selezionate](./media/GERImportFromSharePoint-13-FileStatesForm.PNG)](./media/GERImportFromSharePoint-13-FileStatesForm.PNG)

7. Nella sezione **File** esaminare l'elenco dei file. Nella sezione **Registri delle origini per il formato di importazione** è presente la cronologia dell'importazione del file di Excel. Poiché questo file è stato importato correttamente, nella cartella di SharePoint viene contrassegnato come **Eliminato**.
8. Esaminare la cartella di SharePoint **Origine di importazione dei file (principale)**. I file di Excel importati correttamente sono stati eliminati da questa cartella.
9. In Finance and Operations, selezionare **Contabilità fornitori** \> **Attività periodiche** \> **Imposta 1099** \> **Liquidazione fornitore per i moduli 1099**.
10. Nei campi **Dal** e **Al** immettere i valori appropriati. Selezionare quindi **Transazioni 1099 manuali**.

    Le transazioni fornitori che sono state importate dai file di Excel in SharePoint per il giustificativo **V-00001** vengono visualizzate nella pagina.

    [![Pagina Transazioni 1099 fornitore](./media/GERImportFromSharePoint-14-ImportedTransactions.PNG)](./media/GERImportFromSharePoint-14-ImportedTransactions.PNG)

## <a name="prepare-an-excel-file-for-import"></a>Preparare un file di Excel per l'importazione
1. Aprire il file di Excel utilizzato in precedenza. Nella riga 3 della colonna 1, aggiungere un codice fornitore che non esiste nell'applicazione. Aggiungere nella riga altre informazioni sul fornitore false.

    [![Esempio di file di Microsoft Excel per l'importazione da SharePoint](./media/GERImportFromSharePoint-15-Excel.PNG)](./media/GERImportFromSharePoint-15-Excel.PNG)

2. Caricare il file di Excel aggiornato contenente le transazioni fornitori nella cartella di SharePoint **Origine di importazione dei file (principale)**.
3. In Finance and Operations, aprire la struttura delle configurazioni di ER, selezionare **1099 Modello pagamenti** ed espandere l'elenco di componenti del modello di ER.
4. Selezionare il nome del mapping di modello per aggiornare il mapping di modello in modo da considerare il codice fornitore errato come un errore durante il processo di importazione di dati.
5. Selezionare **Designer**.
6. Nella scheda **Convalide**, è necessario modificare l'azione post-convalida per la regola di convalida che è stata configurata per valutare se il conto fornitore importato esiste nell'applicazione. Aggiornare il valore del campo **Azione post-convalida** impostandolo su **Arresta esecuzione**, salvare le modifiche e chiudere la pagina.

    [![Pagina Progettazione mapping modello di ER](./media/GERImportFromSharePoint-16-UpdateModelMapping.PNG)](./media/GERImportFromSharePoint-16-UpdateModelMapping.PNG)

7. Salvare le modifiche e chiudere la finestra Progettazione mapping di modello di ER.
8. Selezionare **Esegui** per eseguire il mapping di modello di ER modificato.
9. Immettere l'ID giustificativo, ad esempio **V-00002**, quindi selezionare **OK**.

    Il Registro informazioni contiene la notifica che informa che il file della cartella di SharePoint include il conto fornitore errato e non può essere importato.

    [![Eseguire il mapping di modello di ER](./media/GERImportFromSharePoint-17-ModelMappingRunFinished.PNG)](./media/GERImportFromSharePoint-17-ModelMappingRunFinished.PNG)

10. Nella pagina **Stati dei file per le origini**, selezionare **Aggiorna**, quindi nella sezione **File** esaminare l'elenco dei file.

    [![Pagina degli stati dei file di ER per le origini selezionate](./media/GERImportFromSharePoint-18-FileStatesForm.PNG)](./media/GERImportFromSharePoint-18-FileStatesForm.PNG)

    La sezione **Registri delle origini per il formato di importazione** indica che il processo di importazione non è riuscito e che il file si trova ancora nella cartella di SharePoint (la casella di controllo **Eliminato** non è selezionata). Se si corregge questo file in SharePoint aggiungendo il codice fornitore appropriato è poi si cambia lo stato del file da **Non riuscito** a **Pronto** nella sezione **Registri delle origini per il formato di importazione**, è possibile importare il file nuovamente.

11. Esaminare la cartella di SharePoint **Origine di importazione dei file (principale)**. Il file di Excel che non è stato ancora importato è ancora disponibile in questa cartella.
12. In Finance and Operations, selezionare **Contabilità fornitori** \> **Attività periodiche** \> **Imposta 1099** \> **Liquidazione fornitore per i moduli 1099**, immettere i valori appropriati nei campi **Dal** e **Al** e quindi selezionare **Transazioni 1099 manuali**.

    Solo le transazioni per il giustificativo V-00001 sono disponibili. Non sono presenti transazioni per il giustificativo V-00002 anche se l'errore dell'ultima transazione importata viene trovato nel file di Excel.

