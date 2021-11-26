---
title: Report valore di magazzino
description: In questo argomento viene descritto come configurare, generare e utilizzare impostare i report sul valore. Questi report forniscono dettagli sulle quantità e sugli importi fisici e finanziari del magazzino.
author: banluo-ms
ms.date: 10/19/2021
ms.topic: article
ms.search.form: InventValueProcess, InventValueReportSetup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: banluo
ms.search.validFrom: 2021-10-19
ms.dyn365.ops.version: 10.0.9
ms.openlocfilehash: 7978c7b326ef1b62f76711ac187c28539eb1f449
ms.sourcegitcommit: ba10ba2cd4fb4267afb5aacae4f6a52aa2456e7e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/11/2021
ms.locfileid: "7798323"
---
# <a name="inventory-value-reports"></a>Report valore di magazzino

[!include [banner](../includes/banner.md)]

I report sul valore di magazzino forniscono dettagli sulle quantità e sugli importi fisici e finanziari del magazzino. Puoi visualizzare i report in molti modi diversi. Ad esempio, puoi mostrare i totali o le transazioni oppure filtrare per articoli o per intervallo di tempo. Puoi visualizzare i valori del costo del venduto (COGS) o del work in process (WIP) e impostare altre opzioni.

I report sul valore di magazzino consentono di eseguire le seguenti attività:

- Eseguire la riconciliazione tra la contabilità generale e l'inventario.
- Consultare l'inventario delle scorte disponibili e i valori per un periodo specifico.
- Creare configurazioni di report personalizzate per uno scopo specifico.
- Salvare le configurazioni dei report in modo che possano essere utilizzate più volte.
- Aggiungere intervalli per filtrare i dati quando esegui un report.

## <a name="types-of-inventory-value-report"></a>Tipo di report sul valore di magazzino

Esistono due tipi di report sul valore di magazzino: **Valore di magazzino** (il report standard) e **Report di archiviazione valori di magazzino**.

### <a name="standard-inventory-value-report"></a>Report sul valore di magazzino standard

Il report **Valore di magazzino** standard è un semplice report che consente di selezionare le informazioni incluse e quindi mostra tali informazioni sullo schermo. Non salva i risultati. Inoltre, non fornisce funzionalità interattive per l'applicazione di filtri, il drill-down, l'esplorazione o l'esportazione. Per questi motivi, è consigliabile utilizzare invece **Report di archiviazione valori di magazzino** nella maggior parte dei casi.

### <a name="inventory-value-report-storage-report"></a>Report di archiviazione valori di magazzino

Il **Report di archiviazione valori di magazzino** fornisce l'output come pagina interattiva in Microsoft Dynamics 365 Supply Chain Management o come documento esportato in uno dei diversi formati.

Quando visualizzi il rapporto nel tuo browser, le colonne e i saldi aggregati vengono regolati in modo dinamico, a seconda del layout che hai configurato. È possibile ordinare i risultati, filtrarli, approfondire i dati e altro ancora.

I risultati del report sono memorizzati nell'entità dati **Valore di inventario**. Di conseguenza, è possibile filtrare ed esportare i risultati in un formato come valori delimitati da virgole (CSV) o nel formato di Microsoft Excel.

Il report **Report di archiviazione valori di magazzino** è utile quando l'output contiene molte righe. Ad esempio, sono disponibili 50.000 articoli e sono stati creati 300 negozi come magazzini. In questo caso, se si richiedono saldi di fine inventario per articolo, sito e magazzino, l'output conterrà molte righe.

> [!NOTE]
> Nel report **Report di archiviazione valori di magazzino** non vengono inclusi i subtotali che sono definiti nel layout del report. Inoltre non include i saldi di contabilità generale, anche quando sono definiti nel layout del report. La riconciliazione con la contabilità generale deve essere effettuata utilizzando i saldi di verifica. Tuttavia, il report **Valore di magazzino** standard include questi subtotali e saldi.

## <a name="turn-on-the-inventory-value-report-storage-feature"></a>Attivare la funzione del report di archiviazione valori di magazzino

Il report **Valore di magazzino** standard è abilitato per impostazione predefinita. Tuttavia, se vuoi generare il report **Report di archiviazione valori di magazzino** più avanzato, devi attivare la funzionalità nel sistema. Gli amministratori possono utilizzare le impostazioni della [gestione delle funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) per controllare lo stato della funzione e se necessario abilitarla. Nell'area di lavoro **Gestione funzionalità**, la funzione è elencata nel modo seguente:

- **Modulo:** *Gestione costi*
- **Nome funzionalità:** *Report di archiviazione valori di magazzino*

## <a name="define-inventory-value-report-configurations"></a><a name="report-configuration"></a>Definire le configurazioni del report sul valore di magazzino

Utilizza la pagina **Report valore di magazzino** per configurare il contenuto incluso nei diversi tipi di report sul valore di magazzino. Puoi definire qualsiasi numero di tipi di report. Ogni volta che generi un tipo di report sul valore di magazzino, selezionerai un tipo di report.

1. Vai a **Gestione costi \> Impostazioni criteri contabili inventario \> Report valori di magazzino**.
1. Eseguire uno dei passaggi riportati di seguito.

    - Per modificare un report esistente, selezionalo nel riquadro dell'elenco, quindi seleziona **Modifica** nel riquadro azioni.
    - Per creare un nuovo report, seleziona **Nuovo** nel riquadro azioni.

1. Nell'intestazione del report nuovo o selezionato, imposta i seguenti campi:

    - **ID**: immetti un identificatore breve per il report. Questo valore deve essere univoco per tutte le configurazioni del report del valore di magazzino. Non può essere modificato dopo aver salvato una nuova configurazione.
    - **Nome** – Immettere un nome descrittivo per il report.

1. Se stai creando una nuova configurazione del report, seleziona **Salva** nel riquadro azioni per rendere disponibili i campi rimanenti.
1. Nella scheda dettaglio **Generale**, impostare i seguenti campi:

    - **Intervallo di date**: seleziona un intervallo di date predefinito. Puoi sovrascrivere questo intervallo di date quando esegui il report.
    - **Intervallo**: seleziona *Data di registrazione* o *Ora della transazione*, a seconda della data e dell'ora da utilizzare quando vengono recuperati i record per il report.
    - **Set di dimensioni**: seleziona il set di dimensioni per cui eseguire i dati. (le dimensioni sono definite nella contabilità generale). Ad esempio, potresti eseguire i dati per *Account principale* o per *Conto principale + Business Unit*. Il set di dimensioni selezionato non deve avere più di due dimensioni. Per ulteriori informazioni, vedi [Set di dimensioni finanzarie](../../finance/general-ledger/financial-dimension-sets.md).

1. Nella scheda dettaglio **Colonne**, imposta i seguenti campi. Questi campi controllano le colonne incluse nel report e i tipi di dati contenuti in tali colonne.

    - **Magazzino**: imposta questa opzione su *Sì* per mostrare i valori di magazzino. Puoi quindi riconciliare tali valori con i saldi dei conti CoGe.
    - **WIP**: imposta questa opzione su *Sì* per mostrare i valori WIP. Puoi quindi riconciliare tali valori con i saldi dei conti WIP nella contabilità generale. Quando imposti questa opzione su *Sì*, il report mostrerà solo le quantità fisiche e le quantità di magazzino con stato WIP. Gli ordini di produzione con stato WIP sono stati prelevati o dichiarati finiti, ma non sono stati conclusi.
    - **COGS differito**: imposta questa opzione su *Sì* per visualizzare una colonna che mostra le quantità fisiche e gli importi di inventario per COGS differiti. Il COGS differito viene visualizzato utilizzando quantità e importi fisici, poiché compensa le quantità e gli importi del documento di trasporto.
    - **COGS**: imposta questa opzione su *Sì* per visualizzare una colonna che mostra le quantità finanziarie e gli importi per COGS. Il COGS viene visualizzato utilizzando quantità e importi finanziati, poiché compensa le quantità e gli importi della fattura.
    - **Profitti e perdite**: imposta questa opzione su *Sì* per visualizzare una colonna che mostra l'importo finanziario registrato nei conti profitti e perdite per l'inventario.
    - **Stampa i valori cumulativi del conto per il confronto**: imposta questa opzione su *Sì* per visualizzare una colonna che mostra il saldo del conto CoGe. In questo modo, non dovrai controllare il bilancio di verifica. Questa opzione funziona solo con il report **Valore di magazzino** standard, non con il report **Report di archiviazione valori di magazzino**. Dopo aver impostato questa opzione su *Sì*, devi utilizzare i seguenti campi per specificare ciascun conto CoGe che vuoi elencare, a seconda delle opzioni di **Posizione finanziaria** che hai abilitato.

        > [!NOTE]
        > Se selezioni un conto *totale* per uno di questi campi, verrà mostrato sia l'importo di ciascun conto inventario incluso nel conto totale sia l'importo del conto totale.

        - **Conto inventario**: specifica il conto CoGe per il quale visualizzare le informazioni sul magazzino. (Entrambe le opzioni **Inventario** e **Stampa i valori cumulativi del conto per il confronto** devono essere impostate su *Sì*).
        - **Conto WIP**: specifica il conto CoGe per il quale visualizzare le informazioni sul WIP. (Entrambe le opzioni **WIP** e **Stampa i valori cumulativi del conto per il confronto** devono essere impostate su *Sì*).
        - **Conto COGS differito**: specifica il conto CoGe per il quale visualizzare le informazioni sul COGS differito. (Entrambe le opzioni **COGS differito** e **Stampa i valori cumulativi del conto per il confronto** devono essere impostate su *Sì*).
        - **Conto COGS**: specifica il conto CoGe per il quale visualizzare le informazioni sul COGS. (Entrambe le opzioni **COGS** e **Stampa i valori cumulativi del conto per il confronto** devono essere impostate su *Sì*).

    - **Riepiloga i valori fisici e finanziari**: imposta questa opzione su *Sì* per visualizzare una colonna che mostra la quantità di scorte totali e l'importo di magazzino (un riepilogo dei valori di magazzino sia fisico che finanziario). Se questa opzione è impostata su *No*, il report mostrerà i valori di magazzino fisico e finanziario.
    - **Includi non registrate in contabilità generale** imposta questa opzione su *Sì* per visualizzare una colonna che mostra le transazioni che non sono mai state registrate nella contabilità generale. Le transazioni per i seguenti tipi di articoli potrebbero non essere registrate nella contabilità generale:

        - Articoli ricevuti e non ancora fatturati quando l'opzione **Registra inventario fisico** è deselezionata per il relativo gruppo di modelli di articoli.
        - Articoli ricevuti e non ancora fatturati quando l'opzione **Registra entrata prodotti nella contabilità generale** è deselezionata nella Scheda dettaglio **Entrata prodotti** della scheda **Generale** della pagina **Parametri contabilità fornitori** (**Contabilità fornitori \> Imposta \> Parametri contabilità fornitori**).

    - **Calcola il costo medio unitario**. imposta questa opzione su *Sì* per visualizzare una colonna che mostra il costo medio unitario. Il costo unitario medio è la quantità totale divisa per l'importo totale.
    - **Valore e quantità totale**: imposta questa opzione su *Sì* per visualizzare colonne che mostrano la quantità totale di scorte fisiche (e quantità finanziarie) e l'importo totale delle scorte fisiche (e importi finanziari). È possibile impostare questa opzione su *Sì* solo se l'opzione **Riepiloga i valori fisici e finanziari** è impostata su *No*.
    - **Dimensioni inventariali**: in questa griglia, seleziona la casella di controllo **Visualizza** per ogni dimensione che desideri visualizzare nel report. Solo le dimensioni in cui l'opzione **Inventario finanziario** è abilitata mostreranno i valori sul report. Altre dimensioni mostreranno solo colonne vuote. Per le dimensioni che scegli di mostrare, puoi selezionare la casella di controllo **Totale** per includere anche i totali.
    - **ID risorsa**: imposta l'opzione **Visualizza** su *Sì* per visualizzare una colonna che identifica l'articolo per ogni riga. Imposta l'opzione **Totale** su *Sì* per includere anche i totali. A seconda del tipo di articolo elencato in ciascuna riga, la colonna mostra uno dei seguenti tipi di informazioni:

        - **Materiale**: la colonna mostra il valore del campo `ItemID` per il record materiale pertinente.
        - **Manodopera**: la colonna mostra il valore del campo `WorkCenterID` per il record manodopera pertinente.
        - **Costi indiretti**: la colonna mostra il valore del campo `CodeID` per il record dei costi pertinente.

        Se l'opzione **Visualizza** è impostata su *No* per entrambi i campi **ID risorsa** e **Gruppo di risorse**, vedrai solo un valore di magazzino totale basato sulle dimensioni inventariali che hai selezionato.

    - **Gruppo di risorse**: imposta l'opzione **Visualizza** su *Sì* per visualizzare una colonna che identifica il gruppo di risorse per ogni riga. Imposta l'opzione **Totale** su *Sì* per includere anche i totali. A seconda del tipo di articolo elencato in ciascuna riga, la colonna mostra uno dei seguenti tipi di informazioni:

        - **Materiale**: la colonna mostra il valore del campo `ItemGroup` per il record materiale pertinente.
        - **Manodopera**: la colonna mostra il valore del campo `WorkcenterGroup` per il record manodopera pertinente.
        - **Costi indiretti**: la colonna mostra il valore del campo `CostGroup` per il record dei costi pertinente. (Il valore `CostGroupType` deve essere *Indiretto*.)

        Se l'opzione **Visualizza** è impostata su *No* per entrambi i campi **ID risorsa** e **Gruppo di risorse**, vedrai solo un valore di magazzino totale basato sulle dimensioni inventariali che hai selezionato.

1. Nella Scheda dettaglio **Righe**, imposta i seguenti campi. Questi campi consentono di aggiungere le corrispondenti sottosezioni correlate al WIP al report o di rimuoverle.

    - **Materiale**: imposta questa opzione su *Sì* per mostrare informazioni sui materiali. *Materiale* è un tipo di risorsa predefinito perché i materiali devono essere inclusi in tutte le configurazioni del report per creare un output affidabile.
    - **Manodopera**: imposta questa opzione su *Sì* per mostrare i costi del manodopera di WIP.
    - **Costi indiretti**: imposta questa opzione su *Sì* per mostrare i costi indiretti WIP.
    - **Esternalizzazione diretta**: imposta questa opzione su *Sì* per mostrare i costi di esternalizzazione diretta WIP. Queste informazioni sono utili per il conto lavoro.
    - **Livello dettagli**: seleziona un'opzione di visualizzazione per il report:

        - *Transazioni*: visualizza tutte le transazioni rilevanti sul report. Tieni presente che potresti riscontrare problemi di prestazioni quando visualizzi report che includono un grande volume di transazioni. Pertanto, se vuoi utilizzare questa opzione di visualizzazione, è consigliabile utilizzare il report **Report di archiviazione valori di magazzino**.
        - *Totali*: visualizza il risultato totale.

    - **Includi saldo iniziale**: imposta questa opzione su *Sì* per mostrare il saldo iniziale. Questa opzione è disponibile solo quando il campo **Livello dettagli** è impostato su *Transazioni*.

## <a name="generate-an-inventory-value-report-storage-report"></a>Generare un report di archiviazione valori di magazzino

Seguire questi passaggi per generare e archiviare un report **Report di archiviazione valori di magazzino**.

1. Passare a **Gestione costi \> Richieste di informazioni e report \> Report di archiviazione valori di magazzino**.
1. Nel Riquadro azioni selezionare **Nuovo**.
1. Nella finestra di dialogo **Valore di magazzino**, nella scheda dettaglio **Parametri**, impostare i seguenti campi:

    - **Nome** – Immetti un nome univoco per il report.
    - **ID**: seleziona la [configurazione del report sul valore di magazzino](#report-configuration) da utilizzare per il report. La configurazione stabilisce le opzioni per le colonne e le righe che verranno incluse nel report.
    - **Intervallo di date**: utilizza i campi in questa sezione per definire quali record sono inclusi nel report. Per definire l'intervallo di date, è possibile selezionare un intervallo predefinito (relativo alla data di generazione del report) nel campo **Codice intervallo di date** oppure selezionando date specifiche nei campi **Data iniziale** e **Data finale**.

1. Sulla scheda dettaglio **Record da includere**, impostare filtri e vincoli per definire quali dati sono inclusi nel report. Seleziona **Filtro** per aprire una finestra di dialogo di editor di query standard, in cui puoi definire criteri di selezione, criteri di ordinamento e join. I campi funzionano esattamente come funzionano per altri tipi di query in Supply Chain Management. Tutti questi filtri verranno applicati alle transazioni di magazzino ma non al saldo di contabilità generale. Tieni presente questo comportamento quando imposti i filtri. In caso contrario, potresti notare una discrepanza tra l'inventario e la contabilità generale.
1. Nella scheda dettaglio **Esegui in background**, specificare come, quando e con quale frequenza viene generato il report. I campi funzionano esattamente come funzionano per altri tipi di [processi in background](../../fin-ops-core/dev-itpro/sysadmin/batch-processing-overview.md) in Supply Chain Management.

    > [!NOTE]
    > Questo report viene sempre eseguito come parte di un processo batch.

1. Selezionare **OK** per applicare le impostazioni e chiudere la finestra di dialogo.

Al termine del processo batch, il report verrà elencato nella pagina **Report di archiviazione valori di magazzino**. Potrebbe essere necessario aggiornare la pagina per visualizzare il report.

> [!IMPORTANT]
> Nella configurazione del report sul valore di magazzino selezionata, potresti ottenere un saldo iniziale errato se selezioni la stessa data in entrambi i campi **Data iniziale** e **Data finale** e se imposti anche l'opzione **Includi saldo iniziale** su *Sì*.

## <a name="explore-an-inventory-value-report-storage-report"></a>Esplorare un report di archiviazione valori di magazzino

Dopo aver generato un report, è possibile visualizzarlo ed esplorarlo in qualsiasi momento seguendo questi passaggi.

1. Passare a **Gestione costi \> Richieste di informazioni e report \> Report di archiviazione valori di magazzino**.
1. Selezionare un report dell''elenco. La pagina mostra i dettagli della [configurazione del report sul valore di magazzino](#report-configuration) utilizzata per generare il report selezionato.
1. Nel riquadro azioni, seleziona **Visualizza dettagli** per mostrare il contenuto del report.
1. Esplorare il report seguendo uno di questi passaggi:

    - Come per la maggior parte delle pagine standard in Supply Chain Management, è possibile selezionare quasi qualsiasi intestazione di colonna per ordinare o filtrare la griglia in base ai valori in colonna.
    - Usare il campo **Filtro** per filtrare il report in base a qualsiasi valore in una delle diverse colonne disponibili.
    - Utilizzare il menu Visualizza (sopra il campo **Filtro** ) per salvare e caricare le combinazioni preferite di opzioni di ordinamento e filtro.

## <a name="export-an-inventory-value-report-storage-report"></a>Esportare un report di archiviazione valori di magazzino

Qualsiasi report generato viene archiviato nell'entità dati **Valori di inventario**. È possibile utilizzare le funzionalità standard di gestione dei dati di Supply Chain Management per esportare i dati da questa entità in qualsiasi formato di dati supportato, come CSV o Excel.

L'esempio seguente mostra come esportare un report **Report di archiviazione valori di magazzino**.

1. Passare all'**Amministrazione sistema \> Aree di lavoro \> Gestione dati**.
1. Nella sezione **Importare / Esportare**, selezionare il riquadro **Esportare**.
1. Nella pagina visualizzata **Esportare**, impostare il processo di esportazione. Immettere innanzitutto un nome di gruppo per il lavoro.
1. Nella sezione **Entità selezionate**, selezionare **Aggiungi entità**.
1. Nella finestra di dialogo visualizzata, impostare i seguenti campi:

    - **Nome entità** - Selezionare *Valore di inventario*.
    - **Formato dei dati di destinazione** - Selezionare il formato in cui esportare i dati.

1. Selezionare **Aggiungi** per aggiungere la nuova riga e quindi selezionare **Chiudi** per chiudere la finestra di dialogo.
1. In genere, è possibile esportare un report alla volta. Per esportare un report singolo, impostare un filtro per la riga appena aggiunta alla finestra di dialogo **Richiesta**. In questo modo, è possibile definire quale report dall'entità **Valore di inventario** è incluso nell'esportazione. Seguire i passaggi seguenti per Impostare le opzioni di filtro ed esportare un singolo report:

    1. Nella scheda **Intervallo**, selezionare **Aggiungere** per aggiungere una nuova riga.
    2. Impostare il campo **Codice articolo** su *Valore di inventario*.
    3. Impostare il campo **Tabella derivata** su *Valore di inventario*.
    4. Impostare il campo **Campo** sul campo che si desidera filtrare. Generalmente, userete il campo **Nome esecuzione** e/o il campo **Tempo esecuzione**.
    5. Impostare il campo **Criteri** sul valore che si desidera cercare nel campo selezionato. (Se si è selezionato il campo **Nome esecuzione** nel passaggio precedente, questo valore sarà il nome del report. Se si è selezionato il campo **Tempo esecuzione**, sarà il momento in cui il report è stato generato).
    6. Se necessario, aggiungere più righe nella scheda **Intervallo** in base alle esigenze, fino a che non è stato identificato in modo univoco il report che si sta cercando.

1. Selezionare **OK** per salvare le impostazioni e chiudere la finestra di dialogo.
1. Selezionare **Salva** per salvare l'impostazione dell'esportazione.
1. Nella scheda **Opzioni di esportazione** selezionare **Esporta adesso** per generare il file di esportazione.
1. Nella pagina visualizzata **Riepilogo dell'esecuzione**, è possibile vedere lo stato del processo di esportazione e l' elenco delle entità esportate. Nella sezione **Stato elaborazione entità** selezionare l'entità **Valore di inventario** nell'elenco e quindi selezionare **Scarica file** per scaricare i dati esportati da tale entità.

Per ulteriori informazioni su come utilizzare la gestione dei dati per esportare i dati, vedere [Panoramica processi di importazione ed esportazione dati](../../fin-ops-core/dev-itpro/data-entities/data-import-export-job.md).

## <a name="generate-a-standard-inventory-value-report"></a>Generare un report sul valore di magazzino standard

Utilizza la seguente procedura per generare un report **Valore di magazzino** standard.

1. Vai a **Gestione costi \> Richieste di informazioni e report \> Contabilità inventario - report sullo stato \> Valore di magazzino**.
1. Nella finestra di dialogo **Report sul valore di magazzino**, nella scheda dettaglio **Parametri**, impostare i seguenti campi:

    - **Nome** – Immetti un nome univoco per il report.
    - **ID**: seleziona la [configurazione del report sul valore di magazzino](#report-configuration) da utilizzare per il report. La configurazione stabilisce le opzioni per le colonne e le righe che verranno incluse nel report.
    - **Intervallo di date**: utilizza i campi in questa sezione per definire quali record sono inclusi nel report. Per definire l'intervallo di date, è possibile selezionare un intervallo predefinito (relativo alla data di generazione del report) nel campo **Codice intervallo di date** oppure selezionando date specifiche nei campi **Data iniziale** e **Data finale**.

1. Sulla scheda dettaglio **Record da includere**, impostare filtri e vincoli per definire quali dati sono inclusi nel report. Seleziona **Filtro** per aprire una finestra di dialogo di editor di query standard, in cui puoi definire criteri di selezione, criteri di ordinamento e join. I campi funzionano esattamente come funzionano per altri tipi di query in Supply Chain Management.
1. Nella scheda dettaglio **Esegui in background**, specificare come, quando e con quale frequenza viene generato il report. I campi funzionano esattamente come funzionano per altri tipi di [processi in background](../../fin-ops-core/dev-itpro/sysadmin/batch-processing-overview.md) in Supply Chain Management.
1. Selezionare **OK** per applicare le impostazioni e chiudere la finestra di dialogo. Viene visualizzato il report.

## <a name="reading-inventory-value-reports"></a>Lettura dei report sul valore di magazzino

Questa sezione fornisce alcune indicazioni su come leggere e comprendere un report sul valore di magazzino.

Supply Chain Management supporta i due concetti importanti seguenti relativi allo stato dell'inventario:

- **Finanziario aggiornato**: questo concetto indica che le transazioni di magazzino sono già state fatturate. Per gli ordini di produzione, indica la fine di un ordine di produzione.
- **Fisico aggiornato**: questo concetto indica che le transazioni di magazzino non sono ancora state fatturate, ma sono state ricevute o spedite. Per gli ordini di produzione, indica che il materiale è stato prelevato o che l'ordine di produzione è stato dichiarato finito.

Una volta compresi questi due concetti, dovrebbe essere facile comprendere le seguenti colonne nell'output del report:

- **Inventario: quantità finanziaria**: la quantità aggiornata finanziariamente.
- **Inventario: importo finanziario**: valore dell'importo di magazzino aggiornato finanziariamente.
- **Inventario: quantità fisica registrata**: la quantità aggiornata fisicamente.
- **Inventario: importo fisico registrato**: valore dell'importo di magazzino aggiornato fisicamente.
- **Inventario: quantità fisica non registrata**: la quantità che dispone di transazioni di magazzino ma non è stata registrata nella contabilità generale. Ad esempio, hai un gruppo di modelli di articoli in cui **Registra inventario fisico** e **Registra inventario finanziario** le opzioni sono cancellate e hai un elemento che è collegato a quel gruppo. Puoi quindi creae un ordine fornitore, riceverlo e fatturarlo. A questo punto, se esamini il report sul valore di magazzino per l'articolo, vedrai che la quantità e il valore dell'ordine fornitore sono mostrati nelle colonne **Inventario: quantità fisica non registrata** e **Inventario: importo fisico non registrato**.
- **Inventario: importo fisico non registrato**: puoi impostare i tuoi report in modo che mostrino gli importi non registrati. Tuttavia, se utilizzi il report per la riconciliazione di magazzino, non utilizzare questo valore. In caso contrario, l'importo non viene registrato nella contabilità generale.
- **Inventario: quantità**: la quantità totale di tutte le colonne della quantità nel report.
- **Inventario: importo**: la quantità totale di tutte le colonne dell'importo nel report. Quando esegui la riconciliazione di magazzino, non utilizzare questa colonna se il tuo report include la colonna **Inventario: importo fisico non registrato**. In questo caso devi escludere l'importo **Inventario: importo fisico non registrato** dall'importo totale.
- **Costo unitario medio**: l'importo totale diviso per la quantità totale.

In genere, utilizzerai un report sul valore di magazzino per visualizzare il valore e la quantità dell'inventario. Tuttavia, a volte il report non mostra tutte le dimensioni di magazzino pertinenti. Se non vedi le dimensioni previste, verifica le seguenti impostazioni:

- Rivedi i gruppi di dimensioni di tracciabilità e immagazzinamento dell'articolo. Solo le dimensioni in cui l'opzione **Inventario finanziario** è abilitata possono essere mostrate sul report.
- Vai a **Gestione costi \> Impostazioni criteri contabili inventario \> Report sul valore di magazzino**, seleziona la configurazione del report che hai utilizzato per generare il report e assicurati che le dimensioni dell'inventario richieste siano selezionate nella colonna **Visualizza**.

Ad esempio, hai un articolo che ha il numero dell'articolo *A0001*. Nel gruppo delle dimensioni di immagazzinamento, solo il sito è abilitato per l'inventario finanziario. Il sito e il magazzino sono entrambi abilitati per l'inventario fisico. Nel gruppo di dimensioni di tracciabilità, il numero di batch è abilitato per l'inventario fisico ma non per l'inventario finanziario. Puoi quindi utilizzare una configurazione del report in cui sono selezionati sito, magazzino e numero di batch. Quando visualizzi il report, vedi un valore solo per il sito. Le colonne per il magazzino e il numero di batch sono vuote. Come mostra questo esempio, i report sul valore dell'inventario possono mostrare solo le dimensioni dell'inventario abilitate per l'inventario finanziario.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
