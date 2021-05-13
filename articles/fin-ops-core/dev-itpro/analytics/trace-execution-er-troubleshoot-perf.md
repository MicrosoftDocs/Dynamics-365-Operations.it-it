---
title: Tenere traccia dell'esecuzione dei formati di creazione di report elettronici per risolvere i problemi di prestazioni
description: In questo argomento vengono fornite informazioni su come utilizzare la funzionalità di traccia delle prestazioni in Creazione di report elettronici (ER, Electronic Reporting) per risolvere problemi relativi alle prestazioni.
author: NickSelin
ms.date: 04/23/2021
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
ms.openlocfilehash: 13e631d3330eefed09111eca70a5aa111e88274f
ms.sourcegitcommit: ab3f5d0da6eb0177bbad720e73c58926d686f168
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2021
ms.locfileid: "5944655"
---
# <a name="trace-the-execution-of-er-formats-to-troubleshoot-performance-issues"></a>Generare la traccia dell'esecuzione di formati ER per risolvere problemi relativi alle prestazioni

[!include[banner](../includes/banner.md)]

Nell'ambito del processo di pianificazione delle configurazioni di Creazione di report elettronici per la generazione di documenti elettronici, si definisce il metodo utilizzato per acquisire dati dall'applicazione e immetterli nell'output generato. La funzionalità di traccia delle prestazioni ER consente di ridurre significativamente il tempo e il costo inerenti alla raccolta dei dettagli dell'esecuzione del formato ER e all'utilizzo degli stessi per risolvere problemi relativi alle prestazioni. In questa esercitazione vengono fornite indicazioni su come generare tracce delle prestazioni per i formati ER eseguiti e su come utilizzare le informazioni di queste tracce per migliorare le prestazioni.

## <a name="prerequisites"></a>Prerequisiti

Per completare gli esempi in questa esercitazione, è necessario disporre del seguente accesso:

- Accesso a uno dei seguenti ruoli:

    - Sviluppatore per la creazione di report elettronici
    - Consulente funzionale per la creazione di report elettronici
    - Amministratore di sistema

- Accesso all'istanza di Regulatory Configuration Service (RCS) di cui è stato eseguito il provisioning per lo stesso tenant dell'applicazione per uno dei seguenti ruoli:

    - Sviluppatore per la creazione di report elettronici
    - Consulente funzionale per la creazione di report elettronici
    - Amministratore di sistema

È inoltre necessario scaricare e archiviare localmente i file seguenti.

| File                                  | Contenuto                               |
|---------------------------------------|---------------------------------------|
| Performance trace model.version.1     | [Configurazione del modello di dati ER di esempio](https://download.microsoft.com/download/0/a/a/0aa84e48-8040-4c46-b542-e3bf15c9b2ad/Performancetracemodelversion.1.xml)    |
| Performance trace metadata.version.1  | [Configurazione dei metadati ER di esempio](https://download.microsoft.com/download/a/9/3/a937e8c4-1f8a-43e4-83ee-7d599cf7d983/Performancetracemetadataversion.1.xml)      |
| Performance trace mapping.version.1.1 | [Configurazione del mapping di modello ER di esempio](https://download.microsoft.com/download/7/7/3/77379bdc-7b22-4cfc-9b64-a9147599f931/Performancetracemappingversion1.1.xml) |
| Performance trace format.version.1.1  | [Configurazione di formato ER di esempio](https://download.microsoft.com/download/8/6/8/868ba581-5a06-459e-b173-fb00f038b37f/Performancetraceformatversion1.1.xml)       |

### <a name="configure-er-parameters"></a>Configurare i parametri ER

Ogni traccia delle prestazioni ER generata nell'applicazione viene archiviata come allegato del record del registro di esecuzione. Il framework DM (Document Management) viene utilizzato per gestire questi allegati. È necessario configurare in anticipo i parametri ER? per specificare il tipo di documento DM da utilizzare per allegare le tracce delle prestazioni. Nell'area di lavoro **Creazione di report elettronici**, selezionare **Parametri per la creazione di report elettronici**. Quindi, nella pagina **Parametri per la creazione di report elettronici**, nella scheda **Allegati**, nel campo **Altri**, selezionare il tipo di documento DM da utilizzare per le tracce delle prestazioni.

![Pagina Parametri per la creazione di report elettronici](./media/GER-PerfTrace-GER-Parameters-DocumentType.png)

Per essere disponibile nel campo di ricerca **Altri**, un tipo di documento DM deve essere configurato nel seguente modo nella pagina **Tipi di documento** (**Amministrazione organizzazione \> Gestione documenti \> Tipi di documento**):

- **Classe:** Allega file
- **Gruppo:** File

![Pagina Tipi di documento](./media/GER-PerfTrace-DM-DocumentType.png)

> [!NOTE]
> Il tipo di documento selezionato deve essere disponibile in ogni società dell'istanza corrente poiché gli allegati DM sono specifici della società.

### <a name="configure-rcs-parameters"></a>Configurare parametri RCS

Le tracce delle prestazioni ER generate saranno importate in RCS per scopi di analisi mediante la progettazione formato ER e la progettazione mapping ER. Poiché le tracce delle prestazioni ER sono archiviate come allegati del record del registro di esecuzione relativo al formato ER, è necessario configurare in anticipo i parametri RCS per specificare il tipo di documento DM da utilizzare per allegare le tracce delle prestazioni. Nell'istanza di RCS di cui è stato eseguito il provisioning per la società, nell'area di lavoro **Creazione di report elettronici**, selezionare **Parametri per la creazione di report elettronici**. Quindi, nella pagina **Parametri per la creazione di report elettronici**, nella scheda **Allegati**, nel campo **Altri**, selezionare il tipo di documento DM da utilizzare per le tracce delle prestazioni.

![Pagina Parametri per la creazione di report elettronici in RCS](./media/GER-PerfTrace-RCS-Parameters-DocumentType.png)

Per essere disponibile nel campo di ricerca **Altri**, un tipo di documento DM deve essere configurato nel seguente modo nella pagina **Tipi di documento** (**Amministrazione organizzazione \> Gestione documenti \> Tipi di documento**):

- **Classe:** Allega file
- **Gruppo:** File

## <a name="design-an-er-solution"></a>Progettare una soluzione ER

Si supponga di aver iniziato a progettare una nuova soluzione ER per generare un nuovo report che presenta le transazioni fornitore. Attualmente, è possibile trovare le transazioni di un fornitore selezionato nella pagina **Transazioni fornitore** (accedere a **Contabilità fornitori \> Fornitori \> Tutti i fornitori**, selezionare un fornitore e quindi, nel riquadro Azioni, nella scheda **Fornitore**, nel gruppo **Transazioni**, selezionare **Transazioni**). Tuttavia, si desidera avere tutte le transazioni fornitore contemporaneamente in un documento elettronico in formato XML. Questa soluzione comporterà diverse configurazioni ER contenenti il modello dati, i metadati, il mapping di modello e i componenti formato necessari.

1. Accedere all'istanza di RCS di cui è stato eseguito il provisioning per la società.
2. In questa esercitazione si creeranno e modificheranno configurazioni per la società di esempio **Litware, Inc**. Di conseguenza, verificare che questo provider di configurazioni sia stato aggiunto a RCS e sia selezionato come attivo. Per istruzioni, vedere la procedura [Creare provider di configurazioni e contrassegnarli come attivi](tasks/er-configuration-provider-mark-it-active-2016-11.md).
3. Nell'area di lavoro **Creazione di report elettronici**, selezionare il riquadro **Configurazioni report**.
4. Nella pagina **Configurazioni**, importare le configurazioni ER scaricate come prerequisito in RCS, nel seguente ordine: modello dati, metadati, mapping di modello, formato. Per ogni configurazione, procedere come segue:

    1. Nella riquadro Azioni, selezionare **Scambia \> Carica da file XML**.
    2. Selezionare **Sfoglia** per selezionare il file appropriato per la configurazione ER necessaria in formato XML.
    3. Selezionare **OK**.

    ![Pagina Configurazioni in RCS](./media/GER-PerfTrace-RCS-ImportedConfigurations.png)

## <a name="run-the-er-solution-to-trace-execution"></a>Eseguire la soluzione ER per generare la traccia dell'esecuzione

Presupponiamo di aver completato la progettazione della prima versione della soluzione ER. Ora si desidera testarla nell'istanza e analizzare le prestazioni di esecuzione.

### <a name="import-an-er-configuration-from-rcs-into-finance-and-operations"></a><a id='import-configuration'></a>Importare una configurazione ER da RCS in Finance and Operations

1. Accedere all'istanza dell'applicazione.
2. Per questa esercitazione, si importeranno le configurazioni dall'istanza di RCS (in cui si progettano i componenti ER) nell'istanza (dove vengono testati e infine utilizzati). Di conseguenza, è necessario assicurarsi che tutti gli elementi necessari siano stati preparati. Per istruzioni, vedere la procedura [Importare le configurazioni di creazione di report elettronici da Regulatory Configuration Service (RCS)](rcs-download-configurations.md).
3. Seguire questi passaggi per importare le configurazioni da RCS nell'applicazione:

    1. Nell'area di lavoro **Creazione di report elettronici**, nel riquadro del provider di configurazioni **Litware, Inc.**, selezionare **Archivi**.
    2. Nella pagina **Archivio di configurazioni** selezionare l'archivio del tipo **RCS**, quindi selezionare **Apri**.
    3. Nella Scheda dettaglio **Configurazioni** selezionare la configurazione **Formato traccia delle prestazioni**.
    4. Nella Scheda dettaglio **Versioni** selezionare la versione **1.1** della configurazione selezionata, quindi selezionare **Importa**.

    ![Configurazione della pagina dell'archivio](./media/GER-PerfTrace-GER-ImportedConfigurations.png)

Le versioni corrispondenti delle configurazioni del modello dati e del mapping di modello vengono importate automaticamente come prerequisiti per la configurazione di formato ER importata.

### <a name="turn-on-the-er-performance-trace"></a>Attivare la traccia delle prestazioni ER

1. Andare a **Amministrazione organizzazione\> Creazione di report elettronici \> Configurazioni**.
2. Nella pagina **Configurazioni**, nel Riquadro azioni, nella scheda **Configurazioni**, nel gruppo **Impostazioni avanzate**, selezionare **Parametri utente**.
3. Nella finestra di dialogo **Parametri utente**, nella sezione **Traccia esecuzione**, effettuare le seguenti operazioni:

    1. Nel campo **Formato traccia dell'esecuzione**, selezionare **Debug formato traccia** per avviare la raccolta dei dettagli dell'esecuzione del formato ER. Quando questo valore è selezionato, la traccia delle prestazioni raccoglierà informazioni sul tempo dedicato alle seguenti azioni:

        - Esecuzione di ogni origine dati nel mapping di modello chiamato per acquisire i dati
        - Elaborazione di ogni elemento del formato per immettere dati nell'output generato

        Il campo **Formato traccia dell'esecuzione** consente di specificare il formato della traccia delle prestazioni generata in cui sono archiviati i dettagli dell'esecuzione per gli elementi del mapping e del formato ER. Selezionando **Esegui debug formato di traccia** come valore, sarà possibile analizzare il contenuto della traccia nella progettazione Operazione ER e vedere gli elementi del mapping o del formato ER menzionati nella traccia.

    2. Impostare le seguenti opzioni su **Sì** per raccogliere dettagli specifici dell'esecuzione dei componenti mapping di modello ER e formato ER:

        - **Raccogli statistiche di query** - Quando questa opzione è attivata, la traccia delle prestazioni raccoglierà le seguenti informazioni:

            - Il numero di chiamate database effettuate dalle origini dati
            - Il numero di chiamate duplicate al database
            - Dettagli delle istruzioni SQL utilizzate per effettuare chiamate database

        - **Traccia acceso alla memorizzazione nella cache** - Quando questa opzione è attivata, la traccia delle prestazioni raccoglierà informazioni sull'utilizzo della cache del mapping di modello ER.
        - **Traccia accesso ai dati** - Quando questa opzione è attivata, la traccia delle prestazioni raccoglierà informazioni sul numero di chiamate al database per le origini dati eseguite del tipo di elenco di record.
        - **Enumerazione elenco tracce** - Quando questa opzione è attivata, la traccia delle prestazioni raccoglierà informazioni sul numero di record richiesti dalle origini dati del tipo di elenco di record.

    > [!NOTE]
    > I parametri nella finestra di dialogo **Parametri utente** sono specifici all'utente e alla società corrente.

    ![Finestra di dialogo Parametri dell'utente](./media/GER-PerfTrace-GER-UserParameters.png)

### <a name="run-the-er-format"></a><a id='run-format'></a>Eseguire il formato ER

1. Selezionare la società **DEMF**.
2. Andare a **Amministrazione organizzazione\> Creazione di report elettronici \> Configurazioni**.
3. Nella pagina **Configurazioni**, nella struttura della configurazione, selezionare **Formato traccia delle prestazioni**.
4. Nel Riquadro azioni selezionare **Esegui**.

Da notare che il file generato presenta informazioni su 265 transazioni per sei fornitori.

## <a name="review-the-execution-trace"></a>Esaminare la traccia dell'esecuzione

### <a name="export-the-generated-trace-from-the-application"></a><a id='export-trace'></a>Esportare la traccia generata dall'applicazione

Le tracce delle prestazioni sono disaccoppiate dal formato ER di origine e possono essere serializzate in un file zip esterno.

1. Andare a **Amministrazione organizzazione \> Creazione di report elettronici \> Registri debug configurazione**.
2. Nella pagina **Voci di registro report elettronici**, nel riquadro sinistro, nel campo **Nome configurazione**, selezionare **Formato traccia delle prestazioni** per individuare i record del registro generati dall'esecuzione della configurazione **Formato traccia delle prestazioni**.
3. Selezionare il pulsante **Allegati** (il simbolo di graffetta) nell'angolo superiore destro della pagina, oppure premere **CTRL+MAIUSC+A**.

    ![Pulsante Allegati nella pagina Voci di registro report elettronici](./media/GER-PerfTrace-GER-DebugLog.png)

4. Nella pagina **Allegati per voci di registro report elettronici**, nel riquadro Azioni, selezionare **Apri** per ottenere la traccia delle prestazioni come file zip e archiviarlo localmente.

    ![Allegati per Voci di registro report elettronici](./media/GER-PerfTrace-GER-DebugLog-AttachedTrace.png)

> [!NOTE]
> La traccia generata contiene un riferimento al report ER di origine tramite un identificatore di report univoco solo nel formato **GUID**. Il numero di versione del formato non viene considerato.

Si noti che l'associazione tra la traccia delle prestazioni generata per il formato ER eseguito e il mapping di modello ER è basata sul descrittore radice utilizzato e il modello dati comune. Il numero di versione del formato e il mapping di modello non vengono considerati. Anche l'impostazione del flag **Impostazione predefinita per mapping di modello** per il mapping di modello non è considerata.

### <a name="import-the-generated-trace-into-rcs"></a><a id='import-trace'></a>Importare la traccia generata in RCS

1. In RCS, nell'area di lavoro **Creazione di report elettronici**, selezionare il riquadro **Configurazioni report**.
2. Nella pagina **Configurazioni**, nella struttura di configurazione, espandere **Modello traccia delle prestazioni** e selezionare **Formato traccia delle prestazioni**.
3. Nel riquadro azioni selezionare **Progettazione**.
4. Nella pagina **Progettazione formati**, nel riquadro azioni, selezionare **Traccia delle prestazioni**.
5. Nella finestra di dialogo **Impostazioni risultati traccia delle prestazioni**, selezionare **Importa traccia delle prestazioni**.
6. Selezionare **Sfoglia** per selezionare il file zip esportato in precedenza.
7. Selezionare **OK**.

    ![Finestra di dialogo Impostazioni risultati traccia delle prestazioni in RCS](./media/GER-PerfTrace-RCS-ImportedPerfTrace.png)

### <a name="use-the-performance-trace-for-analysis-in-rcs--format-execution"></a>Utilizzare la traccia delle prestazioni per l'analisi in RCS - Esecuzione del formato

1. In RCS, nella pagina **Progettazione formati**, selezionare **Espandi/Comprimi** per espandere il contenuto di tutti gli elementi del formato.

    Si noti che ulteriori informazioni vengono visualizzate per alcuni elementi del formato corrente:

    - Il tempo effettivo impiegato per immettere dati nell'output generato utilizzando l'elemento del formato
    - Lo stesso tempo espresso come percentuale del tempo totale impiegato per la generazione dell'intero output

    ![Pagina Progettazione formati in RCS](./media/GER-PerfTrace-RCS-TraceInfoInFormat.png)

2. Chiudere la pagina **Progettazione formati**.

### <a name="use-the-performance-trace-for-analysis-in-rcs--model-mapping"></a><a id='use-trace'></a>Utilizzare la traccia delle prestazioni per l'analisi in RCS - mapping di modello

1. In RCS, nella pagina **Configurazioni**, nella struttura della configurazione, selezionare **Mapping traccia delle prestazioni**.
2. Nel riquadro azioni selezionare **Progettazione**.
3. Selezionare **Progettazione**.
4. Nella pagina **Progettazione mapping modello**, nel riquadro azioni, selezionare **Traccia delle prestazioni**.
5. Selezionare la traccia importata in precedenza.
6. Selezionare **OK**.

Si noti che le nuove informazioni diventano disponibili per alcuni elementi dell'origine dati del mapping di modello corrente:

- Il tempo effettivo impiegato per acquisire dati utilizzando l'origine dati
- Lo stesso tempo espresso come percentuale del tempo totale impiegato per l'esecuzione dell'intero mapping di modello

Da notare che ER segnala che il mapping di modello corrente duplica le richieste di database durante l'esecuzione dell'origine dati VendTable/\<Relations/VendTrans.VendTable\_AccountNum. Questa duplicazione si verifica perché l'elenco delle transazioni fornitore viene chiamato due volte per ogni record fornitore iterato:

- Una chiamata viene effettuata per immettere i dettagli di ogni transazione nel modello dati, in base alle associazioni configurate.
- Una chiamata viene effettuata per immettere il numero calcolato di transazioni per fornitore nel modello dati.

![Messaggio sulle richieste di database duplicate nella pagina Progettazione mapping modello in RCS](./media/GER-PerfTrace-RCS-TraceInfoInMapping1.png)

Il valore **\[Q:530\]** indica che la tabella VendTrans è stata chiamata 530 volte per restituire un record da quella tabella all'origine dati VendTable/\<Relations/VendTrans.VendTable\_AccountNum. Il valore **\[530\]** indica l'origine dati VendTable/\<Relations/VendTrans.VendTable\_AccountNum che è stata chiamata 530 volte per restituire un record da quell'origine dati e immettere i dettagli della stessa nel modello dati.

Si consiglia di utilizzare la memorizzazione nella cache per l'origine dati VendTable/\<Relations/VendTrans.VendTable\_AccountNum, per ridurre il numero di chiamate effettuate per acquisire i dettagli per 265 transazioni e migliorare le prestazioni del mapping di modello.

Può anche essere utile ridurre il numero di chiamate effettuate all'origine dati LedgerTransTypeList. Questa origine dati viene utilizzata per associare ogni valore dell'enumerazione **LedgerTransType** alla relativa etichetta. Utilizzando questa origine dati, è possibile trovare un'etichetta appropriata e immetterla nel modello dati per ogni transazione fornitore. Il numero corrente di chiamate a questa origine dati (9.027) è alto per 265 transazioni.

![Pagina Progettazione mapping modello in RCS che mostra 9.027 chiamate all'origine dati](./media/GER-PerfTrace-RCS-TraceInfoInMapping1a.png)

## <a name="improve-the-model-mapping-based-on-information-from-the-execution-trace"></a>Migliorare il mapping di modello basato sulle informazioni della traccia dell'esecuzione

### <a name="modify-the-logic-of-the-model-mapping"></a>Modificare la logica del mapping di modello

1. Seguire i passaggi seguenti per utilizzare la memorizzazione nella cache allo scopo di impedire chiamate al database:

    1. Nel RCS, nella pagina **Progettazione mapping modello**, nel riquadro **Origini dati**, selezionare **VendTable**.
    2. Selezionare **Cache**.
    3. Espandere **VendTable**, espandere l'elenco delle relazioni uno-a-molti per l'origine dati VendTable (l'elemento **\<Relazioni**) e selezionare **VendTrans.VendTable\_AccountNum**.
    4. Selezionare **Cache**.

    ![Impostazione della memorizzazione nella cache per impedire chiamate duplicate](./media/GER-PerfTrace-RCS-ChangeMapping-Cache.png)

2. Attenersi ai passaggi seguenti per includere l'origine dati LedgerTransTypeList nell'ambito dell'origine dati VendTable:

    1. Nel riquadro **Tipi di origine dati**, espandere **Funzioni** e selezionare **Campo calcolato**.
    2. Nel riquadro **Origini dati**, selezionare **VendTable**.
    3. Selezionare **Aggiungi**.
    4. Nel campo **Nome** immettere **\$TransType**.
    5. Selezionare **Modifica formula**.
    6. Nel campo **Formula** immettere **LedgerTransTypeList**.
    7. Selezionare **Salva**.
    8. Chiudere la pagina **Editor formule**.
    9. Fare clic su **OK**.

3. Seguire questi passaggi per effettuare la memorizzazione nella cache del campo **\$TransType**:

    1. Selezionare **LedgerTransTypeList**.
    2. Selezionare **Cache**.
    3. Selezionare **VendTable.\$TransType**.
    4. Selezionare **Cache**.

    ![Impostazione della memorizzazione nella cache del campo $TransType](./media/GER-PerfTrace-RCS-ChangeMapping-Cache2.png)

4. Attenersi alla procedura seguente per modificare il campo **\$TransTypeRecord** di modo che inizi a utilizzare il campo **\$TransType** memorizzato nella cache:

    1. Nel riquadro **Origini dati**, espandere **VendTable**, espandere **\<Relazioni**, espandere **VendTrans.VendTable\_AccountNum** e selezionare **VendTable. VendTrans.VendTable\_AccountNum.\$TransTypeRecord**.
    2. Selezionare **Modifica**.
    3. Selezionare **Modifica formula**.
    4. Nel campo **Formula**, individuare la seguente espressione:

        FIRSTORNULL (WHERE (LedgerTransTypeList, LedgerTransTypeList.Enum = \@.TransType))

    5. Nel campo **Formula**, immettere la seguente espressione:

        FIRSTORNULL (WHERE (VendTable.'\$TransType', VendTable.'\$TransType'.Enum = \@.TransType)).

    6. Selezionare **Salva**.
    7. Chiudere la pagina **Editor formule**.
    8. Selezionare **OK**.

5. Selezionare **Salva**.
6. Chiudere la pagina **Progettazione mapping modello**.
7. Chiudere la pagina **Mapping modello**.

### <a name="complete-the-modified-version-of-the-er-model-mapping"></a>Completare la versione modificata del mapping di modello ER

1. In RCS, nella pagina **Configurazioni**, nella Scheda dettaglio **Versioni**, selezionare la versione **1.2** della configurazione **Mapping traccia delle prestazioni**.
2. Selezionare **Cambia stato**.
3. Selezionare **Completa**.

### <a name="import-the-modified-er-model-mapping-configuration-from-rcs-into-the-application"></a>Importare la configurazione del mapping di modello ER modificata da RCS nell'applicazione

Ripetere la procedura nella sezione [Importare una configurazione ER da RCS in Finance and Operations](#import-configuration) vista in precedenza in questo argomento per importare la versione 1.2 della configurazione **Mapping traccia delle prestazioni**.

## <a name="run-the-modified-er-solution-to-trace-execution"></a>Eseguire la soluzione ER modificata per generare la traccia dell'esecuzione

### <a name="run-the-er-format"></a>Eseguire il formato ER

Ripetere i passaggi nella sezione [Eseguire il formato ER](#run-format) vista in precedenza in questo argomento per generare una nuova traccia delle prestazioni.

## <a name="work-with-the-execution-trace"></a>Utilizzare la traccia dell'esecuzione

### <a name="export-the-generated-trace-from-the-application"></a>Esportare la traccia generata dall'applicazione

Ripetere i passaggi nella sezione [Esportare la traccia generata dall'applicazione](#export-trace) vista in precedenza in questo argomento per salvare una nuova traccia delle prestazioni localmente.

### <a name="import-the-generated-trace-into-rcs"></a>Importare la traccia generata in RCS

Ripetere i passaggi nella sezione [Importare la traccia generata in RCS](#import-trace) vista in precedenza in questo argomento per importare la nuova traccia delle prestazioni in RCS.

### <a name="use-the-performance-trace-for-analysis-in-rcs--model-mapping"></a>Utilizzare la traccia delle prestazioni per l'analisi in RCS - mapping di modello

Ripetere i passaggi nella sezione [Utilizzare la traccia delle prestazioni per l'analisi in RCS - mapping di modello](#use-trace) vista in precedenza in questo argomento per analizzare la traccia delle prestazioni più recente.

Si noti che le rettifiche apportate al mapping di modello hanno eliminato le query duplicate al database. Anche il numero di chiamate alle tabelle di database e alle origini dati per questo mapping di modello sono state ridotti. Di conseguenza, le prestazioni dell'intera soluzione ER sono state migliorate.

![Informazioni sulla traccia per l'origine dati VendTable nella pagina Progettazione mapping modello in RCS](./media/GER-PerfTrace-RCS-TraceInfoInMapping2.png)

Nelle informazioni sulla traccia, il valore **\[12\]** per l'origine dati VendTable indica che questa origine dati è stata chiamata 12 volte. Il valore **\[Q:6\]** indica che sei chiamate sono state convertite in chiamate database alla tabella VendTable. Il valore **\[C:6\]** indica che i record recuperati dal database sono stati memorizzati nella cache e altre sei chiamate sono state elaborate utilizzando la cache.

Si noti che il numero di chiamate all'origine dati LedgerTransTypeList è stato ridotto da 9.027 a 240.

![Informazioni sulla traccia per l'origine dati LedgerTransTypeList nella pagina Progettazione mapping modello in RCS](./media/GER-PerfTrace-RCS-TraceInfoInMapping2a.png)

## <a name="review-the-execution-trace-in-the-application"></a>Verificare la traccia di esecuzione nell'applicazione

Oltre a RCS, alcune versioni possono offrire funzionalità per un'esperienza di progettazione di framework ER. Queste versioni hanno un'opzione **Abilita modalità progettazione** che può essere attivata. Questa opzione è presente nella scheda **Generale** della pagina **Parametri per la creazione di report elettronici**, accessibile dall'area di lavoro **Creazione di report elettronici**.

![Attivare l'opzione di modalità progettazione nella pagina Parametri per la creazione di report elettronici](./media/GER-PerfTrace-GER-Parameters-DesignMode.png)

Se si utilizza una di queste versioni, è possibile analizzare i dettagli delle tracce delle prestazioni generate direttamente nell'applicazione. Non è necessario esportarli dall'applicazione e importarli in RCS.

## <a name="review-the-execution-trace-by-using-external-tools"></a>Esaminare la traccia dell'esecuzione utilizzando strumenti esterni

### <a name="configure-user-parameters"></a>Configurare parametri utente

1. Andare a **Amministrazione organizzazione\> Creazione di report elettronici \> Configurazioni**.
2. Nella pagina **Configurazioni**, nel Riquadro azioni, nella scheda **Configurazioni**, nel gruppo **Impostazioni avanzate**, selezionare **Parametri utente**.
3. Nella finestra di dialogo **Parametri dell'utente**, nella sezione **Traccia esecuzione**, nel campo **Formato traccia dell'esecuzione**, selezionare **XML PerfView**.

### <a name="run-the-er-format"></a>Eseguire il formato ER

Ripetere i passaggi nella sezione [Eseguire il formato ER](#run-format) vista in precedenza in questo argomento per generare una nuova traccia delle prestazioni.

Si noti che il Web browser offre un file zip per il download. Questo file contiene la traccia delle prestazioni in formato PerfView. È quindi possibile utilizzare lo strumento di analisi delle prestazioni PerfView per analizzare i dettagli dell'esecuzione del formato ER.

![Informazioni sulla traccia delle prestazioni in formato PerfView](./media/GER-PerfTrace2-PerfViewTrace1.PNG)

## <a name="use-external-tools-to-review-an-execution-trace-that-includes-database-queries"></a>Utilizzare strumenti esterni per esaminare una traccia dell'esecuzione che include le query di database

In seguito ai miglioramenti apportati al framework ER, la traccia delle prestazioni che viene generata nel formato di PerfView ora offre ulteriori dettagli sull'esecuzione del formato ER. In Microsoft Dynamics 365 for Finance and Operations versione 10.0.4 (luglio 2019), questa traccia può anche includere i dettagli delle query SQL eseguite nel database dell'applicazione.

### <a name="configure-user-parameters"></a>Configurare parametri utente

1. Andare a **Amministrazione organizzazione** \> **Creazione di report elettronici** \> **Configurazioni**.
2. Nella pagina **Configurazioni**, nel Riquadro azioni, nella scheda **Configurazioni**, nel gruppo **Impostazioni avanzate**, selezionare **Parametri utente**.
3. Nella finestra di dialogo **Parametri utente**, nella sezione **Traccia esecuzione**, impostare i seguenti parametri:

    - Nel campo **Formato traccia dell'esecuzione**, selezionare **XML PerfView**.
    - Impostare l'opzione **Raccogli statistiche di query** su **Sì**.
    - Impostare l'opzione **Traccia query** su **Sì**.

    ![Sezione Traccia esecuzione, finestra di dialogo Parametri utente](./media/GER-PerfTrace2-GER-UserParameters.PNG)

### <a name="run-the-er-format"></a>Eseguire il formato ER

Ripetere i passaggi nella sezione [Eseguire il formato ER](#run-format) vista in precedenza in questo argomento per generare una nuova traccia delle prestazioni.

Si noti che il Web browser offre un file zip per il download. Questo file contiene la traccia delle prestazioni in formato PerfView. È quindi possibile utilizzare lo strumento di analisi delle prestazioni PerfView per analizzare i dettagli dell'esecuzione del formato ER. Questa traccia ora include i dettagli di accesso al database SQL durante l'esecuzione del formato ER.

![Informazioni sulla traccia per il formato ER eseguito in PerfView](./media/GER-PerfTrace2-PerfViewTrace2.PNG)

## <a name="additional-resources"></a>Risorse aggiuntive

- [Panoramica sui report elettronici](general-electronic-reporting.md)
- [Migliorare le prestazioni delle soluzioni ER aggiungendo origini dati CAMPO CALCOLATO parametrizzate](er-calculated-field-ds-performance.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
