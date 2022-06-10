---
title: Risoluzione dei problemi di prestazioni nelle configurazioni di ER
description: Questo argomento spiega come trovare e risolvere i problemi di prestazioni nelle configurazioni di Creazione di report elettronici (ER).
author: NickSelin
ms.date: 05/12/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERModelMappingDesigner, EROperationDesigner, ERFormatMappingRunJobTable, ERParameters, ERSolutionTable
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: ''
ms.search.region: Global
ms.author: maximbel
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: e727e06c73ff445bf4219ac5a9eee7bec25740d9
ms.sourcegitcommit: 336a0ad772fb55d52b4dcf2fafaa853632373820
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/28/2022
ms.locfileid: "8811682"
---
# <a name="troubleshooting-performance-issues-in-er-configurations"></a>Risoluzione dei problemi di prestazioni nelle configurazioni di ER

Questo argomento spiega come trovare e risolvere i problemi di prestazioni nelle [configurazioni](general-electronic-reporting.md#Configuration) [di Creazione di report elettronici](general-electronic-reporting.md) (ER).

In genere, l'analisi delle prestazioni consiste in diversi passaggi.

1. [Raccolta dei](#collecting-data) dati.
2. Analisi dei dati raccolti.
3. Sulla base dei risultati dell'analisi, utilizzare le configurazioni ER per [apportare modifiche](#making-changes) oppure decidere di raccogliere più dati.

## <a name="troubleshooting"></a>Risoluzione dei problemi

### <a name="analyze-execution-time"></a>Analizzare il tempo di esecuzione

Il tempo di esecuzione può dipendere da fattori imprevedibili, quali altre attività in esecuzione nello stesso ambiente e la memorizzazione nella cache che utilizza i dati quando vengono chiamati per la prima volta. Pertanto, è necessario ripetere l'esecuzione e la misurazione più volte.

A volte, i problemi di prestazioni non sono causati da una configurazione del formato ER utilizzata per i rapporti. Sono invece causati dal codice X++ utilizzato per aprire quella configurazione del formato ER.

1. Osservare il tempo di esecuzione del report, riportato nel [Centro azioni](#infolog-time) o nel [registro eventi](#event-log-time).
2. Confrontare il tempo di esecuzione del report con il tempo di esecuzione totale nello scenario.
3. Se il tempo di esecuzione del report è molto inferiore al tempo di esecuzione totale, considerare la quantità di dati elaborati dal report:

    - Se il report elabora una piccola quantità di dati, il problema potrebbe riguardare il tempo di caricamento della configurazione.
    - Se il report elabora una grande quantità di dati, il problema potrebbe riguardare la preelaborazione di X++. Usare il [parser di traccia](#analyze-trace-parser-trace) per analizzare questo caso.

    Per altri casi, vedere le sezioni successive.

4. Eseguire più test che coinvolgono diverse quantità di dati per determinare in che modo il tempo di esecuzione dipende dalla quantità di dati.

### <a name="analyze-trace-parser-traces"></a><a name="analyze-trace-parser-trace"></a>Analizzare le tracce con il parser di traccia

Preparare un piccolo esempio o raccogliere diverse tracce durante le parti casuali della generazione del rapporto.

Quindi, nel [parser di traccia](#trace-parser), esegui un'analisi dal basso verso l'alto standard e rispondi alle seguenti domande:

- Quali sono i metodi migliori in termini di consumo di tempo?
- Quanta parte del tempo totale utilizzano questi metodi?

Rispondere alle stesse domande per le query.

Se si nota che i metodi sono preceduti dal prefisso "ER", passare alla sezione successiva.

Se i metodi o le query hanno avuto origine nella suite di applicazioni, prendere in considerazione le ottimizzazioni generiche (ad esempio la creazione di indici).

Analizzare il numero di chiamate. Se il numero è significativamente più alto del previsto, prendere in considerazione la memorizzazione nella cache dei nodi corrispondenti della configurazione.

### <a name="analyze-database-calls"></a><a name="analyze-database-calls"></a>Analizzare le chiamate al database

Preparare un esempio che contenga una piccola quantità di dati, in modo da poter raccogliere una [traccia ER](#electronic-reporting-traces).

Quindi, aprire la traccia nella soluzione di progettazione del mapping del modello ER e guardare in fondo alla pagina. Rispondere alle seguenti domande:

- C'è una duplicazione della query? In caso affermativo, considerare una delle seguenti correzioni:

    - [Usare la memorizzazione nella cache](#use-caching) se si pensa che ci siano più chiamate all'interno di un unico record padre.
    - [Usare un campo calcolato memorizzato nella cache e parametrizzato](#cached-parameterized) se si pensa che ci siano chiamate allo stesso record all'interno di record diversi.
    - [Usare un'origine dati **JOIN**](#use-join-datasource) se occorre leggere un numero elevato di record diversi da un database.

- Il numero di query e record recuperati corrisponde alla quantità complessiva di dati? Ad esempio, se un documento ha 10 righe, le statistiche mostrano che il report estrae 10 righe o 1.000 righe? Se si dispone di un numero considerevole di record recuperati, prendere in considerazione una delle seguenti correzioni:

    - [Usa a funzione **FILTER** anziché la funzione **WHERE**](#filter) per elaborare i dati sul lato Microsoft SQL Server.
    - Utilizzare la memorizzazione nella cache per evitare di recuperare gli stessi dati.
    - [Utilizzare le funzioni dei dati raccolti](#collected-data) per evitare di recuperare gli stessi dati per il riepilogo.

### <a name="analyze-perfview-traces"></a>Analizzare le tracce di PerfView

[PerfView](#perfview) è uno strumento per sviluppatori esperti. Per informazioni più dettagliate sui seguenti passaggi, vedere [Nozioni di base sull'indagine in tempo reale](https://channel9.msdn.com/Series/PerfView-Tutorial/Tutorial-12-Wall-Clock-Time-Investigation-Basics).

1. Raccogliere una traccia utilizzando il tempo di thread.
2. Includere solo gli stack che usano **runUnattended**, per filtrare solo il thread che ha l'esecuzione della configurazione. (Aggiungere **runUnattended** alla casella di input **IncPats**.)
3. Ridurre tutta la CPU, la rete e il tempo bloccato.
4. Caricare le [impostazioni ER predefinite per PerfView](https://download.microsoft.com/download/2/d/0/2d037b0f-ffd1-4d65-b64f-fcdf51f2c81f/ER_PerfViewPresets.xml).
5. Selezionare **ER** \> **Altre impostazioni predefinite**.
6. Guardare i nomi:

    - Probabilmente verrà mostrato il codice della piattaforma che consuma più tempo.
    - È possibile toccare due volte (o fare doppio clic) ed esaminare l'elenco **callees**.

        Se si trovano classi con il prefisso "ERExpression" e se queste sono funzioni correlate a formule, è possibile inferire il nome della funzione in base al nome della classe e guardare il repository ER per visualizzare gli attributi.

### <a name="fixes"></a>Correzioni

- Se si nota che la maggior parte del tempo della CPU viene consumato dalle query, provare a ridurre il numero di query:

    - [Rivedere la traccia ER](#analyze-database-calls) per query duplicate.
    - Guardare quanti record vengono recuperati e valutare quanti dati dovrebbero essere teoricamente recuperati.

- Se la maggior parte del tempo della CPU viene consumato dalle funzioni utilizzate, provare a trovare il punto nella configurazione che utilizza la maggior parte delle risorse.
- Se la maggior parte del tempo della CPU viene consumato dalle funzioni di raccolta dati, considerare la possibilità di sostituirle con *SQL group by* sul lato di mapping del modello.

### <a name="collecting-data"></a><a name="collecting-data"></a>Raccolta dei dati

A seconda dell'ambiente, esistono diversi modi per raccogliere i dati disponibili:

- Ottenere il tempo di esecuzione totale:

    - Dal Centro azioni
    - Dal registro degli eventi

- Creare un profilo per l'esecuzione:

    - Usando gli strumenti ER
    - Usando il parser di traccia
    - Usando PerfView

#### <a name="collecting-data-in-a-production-environment"></a>Raccolta dei dati in un ambiente di produzione

A volte, i problemi possono essere riprodotti solo in un ambiente di produzione. I dati possono essere raccolti in uno dei modi indicati di seguito:

- Usando le tracce del [parser di traccia](../perf-test/trace-trace-tutorial.md)
- Usando le tracce dell'[esecuzione ER](trace-execution-er-troubleshoot-perf.md)
- Usando il tempo di esecuzione totale

#### <a name="collecting-data-in-a-development-environment"></a>Raccolta dei dati in un ambiente di sviluppo

Oltre agli strumenti che possono essere utilizzati in un ambiente di produzione, esistono diversi strumenti che è possibile utilizzare in un ambiente di sviluppo:

- Registro eventi (Microsoft-Dynamics-ElectronicReporting). Questo registro può fornire il tempo di esecuzione totale.
- Strumenti .NET comuni, come PerfView.

Inoltre, un ambiente di sviluppo offre maggiore flessibilità per sperimentare. Ad esempio, è possibile disattivare parti dei report per vedere come viene influenzato il tempo di esecuzione.

### <a name="tools"></a><a name="tools"></a>Strumenti

#### <a name="execution-time-in-the-action-center"></a><a name="infolog-time"></a>Tempo di esecuzione nel Centro azioni

ER può mostrare il tempo di esecuzione della configurazione nel Centro azioni. Questa opzione funziona solo per un utente specifico e un'azienda specifica e solo per sessioni interattive. Per rendere disponibile questa funzione, seguire questi passaggi.

1. Andare a **Amministrazione organizzazione** \> **Creazione di report elettronici** \> **Configurazioni**.
2. Nella pagina **Configurazioni**, nel Riquadro azioni, nella scheda **Configurazioni**, nel gruppo **Impostazioni avanzate**, selezionare **Parametri utente**.
3. Nella finestra di dialogo **Parametri utente**, impostare l'opzione **Mostra tempo di generazione file** su **Sì**.

#### <a name="execution-time-in-the-event-log"></a><a name="event-log-time"></a>Tempo di esecuzione nel registro eventi

1. Aprire il visualizzatore eventi di Windows.
2. In **Registri applicazioni e servizi**, aprire **Microsoft-Dynamics-ElectronicReporting/Operativo**.
3. Cercare gli eventi **FormatMapingRun** in cui **EventID=2**, poiché questi eventi contengono informazioni sul tempo trascorso.

#### <a name="trace-parser-traces"></a><a name="trace-parser"></a>Tracce del parser di traccia 

Poiché ER è implementato in X++, è possibile usare strumenti X++ comuni per analizzare le prestazioni. Per ulteriori informazioni, vedere [Acquisire le tracce usando il parser di traccia](../perf-test/trace-trace-tutorial.md).

Esistono alcune limitazioni a questo approccio. Poiché parte di ER è implementata in C#, non tutti i dettagli saranno disponibili. Tuttavia, è possibile visualizzare i dettagli sull'utilizzo dei dati. Inoltre, lunghe esecuzioni di report possono superare i limiti di archiviazione delle tracce.

#### <a name="er-traces"></a><a name="electronic-reporting-traces"></a>Tracce ER

ER è in grado di raccogliere le proprie tracce e dispone di strumenti di visualizzazione e analisi per tali tracce. Per altre informazioni, vedi [Tenere traccia dell'esecuzione dei formati di creazione di report elettronici per risolvere i problemi di prestazioni](trace-execution-er-troubleshoot-perf.md).

#### <a name="perfview"></a><a name="perfview"></a>PerfView

Poiché sia X++ che ER sono implementati sulla piattaforma .NET, è possibile usare strumenti .NET comuni. Ad esempio, puoi utilizzare lo strumento gratuito [PerfView](https://github.com/Microsoft/perfview).

È anche possibile raccogliere dati dalla riga di comando. Ad esempio, lo script di Windows PowerShell seguente raccoglie il tempo di esecuzione fino all'interruzione dell'esecuzione di qualsiasi formato nel computer.

```powershell
c:\programs\PerfView collect "e:\traces\$(date -format "ddMMyyyy_hhmm").etl" `
    -CircularMB:20000 -ThreadTime `
    -NoNGenRundown `
    -StopOnEtwEvent:Microsoft-Dynamics-ElectronicReporting/FormatMappingRun/Stop
```

Esistono alcune limitazioni a questo approccio. È necessario disporre dell'accesso al computer. Inoltre, occorre essere uno sviluppatore esperto, perché la curva di apprendimento è particolarmente ripida.

### <a name="making-changes"></a><a name="making-changes"></a>Apportare modifiche

#### <a name="use-caching"></a><a name="use-caching"></a>Usare la memorizzazione nella cache

Sebbene la memorizzazione nella cache riduca la quantità di tempo necessaria per recuperare nuovamente i dati, ha un costo significativo in termini di memoria. Usare la memorizzazione nella cache nei casi in cui la quantità di dati recuperati non è molto grande. Per ulteriori informazioni e un esempio che mostra come utilizzare la memorizzazione nella cache, vedere [Migliorare il mapping del modello in base alle informazioni della traccia di esecuzione](trace-execution-er-troubleshoot-perf.md#improve-the-model-mapping-based-on-information-from-the-execution-trace).

#### <a name="reduce-volume-of-data-fetched"></a><a name="reduce-fetched-data"></a>Ridurre il volume dei dati recuperati

È possibile ridurre il consumo di memoria per la memorizzazione nella cache limitando il numero di campi nei record di una tabella dell'applicazione che si recupera in fase di esecuzione. In questo caso, recupererai solo quei valori di campo di una tabella dell'applicazione di cui hai bisogno nel mapping di modello ER. Gli altri campi in quella tabella non verranno recuperati. Pertanto, il volume di memoria necessario per memorizzare nella cache i record recuperati viene ridotto. Per ulteriori informazioni, vedi [Migliorare le prestazioni delle soluzioni ER riducendo il numero di campi della tabella recuperati in fase di esecuzione](er-reduce-fetched-fields-number.md).

#### <a name="use-a-cached-parameterized-calculated-field"></a><a name="cached-parameterized"></a>Usare un campo calcolato memorizzato nella cache e parametrizzato

A volte, i valori devono essere cercati ripetutamente. Gli esempi includono nomi di account e numeri di conto. Per risparmiare tempo, è possibile creare un campo calcolato con parametri al livello più alto, quindi aggiungere il campo alla cache.

Si consiglia di utilizzare questo approccio solo quando la dimensione dei dati memorizzati nella cache è ridotta. Per ulteriori informazioni, vedere [Migliorare le prestazioni delle soluzioni ER aggiungendo origini dati CAMPO CALCOLATO parametrizzate](er-calculated-field-ds-performance.md).

#### <a name="use-a-join-data-source"></a><a name="use-join-datasource"></a>Usare un'origine dati JOIN

Un'origine dati **JOIN** permette di recuperare più record connessi tramite un'unica query. Non è necessario utilizzare una query separata per recuperare ogni record connesso. Ad esempio, se si dispone di 1.000 righe e si recuperano i dati dell'articolo per ogni riga per relazione, si avranno 1.001 query (= 1.000 + 1). Se si usa un'origine dati **JOIN**, sarà sufficiente un'unica query per recuperare gli stessi dati. Per maggiori informazioni, vedere [Usare le origini dati JOIN nei mapping di modello ER per ottenere dati da più tabelle dell'applicazione](er-join-data-sources.md).

#### <a name="use-the-filter-function-instead-of-the-where-function"></a><a name="filter"></a>Usare la funzione FILTER anziché la funzione WHERE

La funzione **[FILTER](er-functions-list-filter.md)** esegue condizioni su SQL Server, mentre la funzione **WHERE** recupera tutti i dati dall'elenco, un record alla vota, e applica la condizione per ciascun record. Ad esempio, si desidera selezionare un record su 1.000 record. Se si usa **WHERE**, verranno recuperati tutti i 1.000 record. Se invece si usa **FILTER**, verrà recuperato un singolo record. **FILTER** può anche usare gli indici sul lato database.

#### <a name="using-collected-data-functions-or-an-accumulated-data-data-source"></a><a name="collected-data"></a>Utilizzo delle funzioni dei dati raccolti o di un'origine dati accumulata

Se la configurazione ha un componente *group by* che riepiloga i dati precedentemente recuperati per report, il componente recupererà nuovamente tutti i dati. Utilizzando le funzioni dei dati raccolti, si abilite ER ad accumulare dati durante il primo recupero. Per ulteriori informazioni, vedere [Configurare il formato ER per eseguire il conteggio e la sommatoria](tasks/er-format-counting-summing-2.md).

#### <a name="rewrite-parts-of-the-configuration-in-x"></a>Riscrivere parti della configurazione in X++

ER supporta i metodi di chiamata di tabelle e classi, incluse le estensioni. Considerare la possibilità di riscrivere parti del mapping del modello in X++ per migliorare le prestazioni.

ER può utilizzare dati dalle seguenti origini:

- Classi (origini dati **oggetto** e **classe**)
- Tabelle (origini dati **tabella** e **record di tabella**)

L'[API ER](er-apis-app73.md#how-to-access-internal-x-objects-by-using-erobjectsfactory) fornisce inoltre un modo per inviare dati precalcolati dal codice chiamante. La suite di applicazioni contiene numerosi esempi di questo approccio.
