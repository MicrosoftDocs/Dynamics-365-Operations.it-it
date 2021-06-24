---
title: Risoluzione dei problemi di prestazioni nelle configurazioni di ER
description: Questo argomento spiega come trovare e risolvere i problemi di prestazioni nelle configurazioni di Creazione di report elettronici (ER).
author: NickSelin
ms.date: 06/08/2021
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
ms.openlocfilehash: d77c2aad904ba911ac19009d6a981ea4153aaa48
ms.sourcegitcommit: 60afcd85b3b5b9e5e8981ebbb57c0161cf05e54b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2021
ms.locfileid: "6216867"
---
# <a name="troubleshooting-performance-issues-in-er-configurations"></a><span data-ttu-id="5ed3b-103">Risoluzione dei problemi di prestazioni nelle configurazioni di ER</span><span class="sxs-lookup"><span data-stu-id="5ed3b-103">Troubleshooting performance issues in ER configurations</span></span>

<span data-ttu-id="5ed3b-104">Questo argomento spiega come trovare e risolvere i problemi di prestazioni nelle [configurazioni](general-electronic-reporting.md#Configuration) [di Creazione di report elettronici](general-electronic-reporting.md) (ER).</span><span class="sxs-lookup"><span data-stu-id="5ed3b-104">This topic explains how to find and solve performance issues in [Electronic reporting](general-electronic-reporting.md) (ER) [configurations](general-electronic-reporting.md#Configuration).</span></span>

<span data-ttu-id="5ed3b-105">In genere, l'analisi delle prestazioni consiste in diversi passaggi.</span><span class="sxs-lookup"><span data-stu-id="5ed3b-105">Typically, performance investigation consists of several steps.</span></span>

1. <span data-ttu-id="5ed3b-106">[Raccolta dei](#collecting-data) dati.</span><span class="sxs-lookup"><span data-stu-id="5ed3b-106">[Collect](#collecting-data) data.</span></span>
2. <span data-ttu-id="5ed3b-107">Analisi dei dati raccolti.</span><span class="sxs-lookup"><span data-stu-id="5ed3b-107">Analyze the collected data.</span></span>
3. <span data-ttu-id="5ed3b-108">Sulla base dei risultati dell'analisi, utilizzare le configurazioni ER per [apportare modifiche](#making-changes) oppure decidere di raccogliere più dati.</span><span class="sxs-lookup"><span data-stu-id="5ed3b-108">Based on the results of the analysis, use ER configurations to [make changes](#making-changes), or decide to collect more data.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="5ed3b-109">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="5ed3b-109">Troubleshooting</span></span>

### <a name="analyze-execution-time"></a><span data-ttu-id="5ed3b-110">Analizzare il tempo di esecuzione</span><span class="sxs-lookup"><span data-stu-id="5ed3b-110">Analyze execution time</span></span>

<span data-ttu-id="5ed3b-111">Il tempo di esecuzione può dipendere da fattori imprevedibili, quali altre attività in esecuzione nello stesso ambiente e la memorizzazione nella cache che utilizza i dati quando vengono chiamati per la prima volta.</span><span class="sxs-lookup"><span data-stu-id="5ed3b-111">Execution time can depend on unpredictable factors, such as other tasks that are running in the same environment and caching that uses data when it's called for the first time.</span></span> <span data-ttu-id="5ed3b-112">Pertanto, è necessario ripetere l'esecuzione e la misurazione più volte.</span><span class="sxs-lookup"><span data-stu-id="5ed3b-112">Therefore, you should repeat the execution and measurement several times.</span></span>

<span data-ttu-id="5ed3b-113">A volte, i problemi di prestazioni non sono causati da una configurazione del formato ER utilizzata per i rapporti.</span><span class="sxs-lookup"><span data-stu-id="5ed3b-113">Sometimes, performance issues aren't caused by an ER format configuration that is used for reporting.</span></span> <span data-ttu-id="5ed3b-114">Sono invece causati dal codice X++ utilizzato per aprire quella configurazione del formato ER.</span><span class="sxs-lookup"><span data-stu-id="5ed3b-114">Instead, they are caused by the X++ code that is used to open that ER format configuration.</span></span>

1. <span data-ttu-id="5ed3b-115">Osservare il tempo di esecuzione del report, riportato nel [Centro azioni](#infolog-time) o nel [registro eventi](#event-log-time).</span><span class="sxs-lookup"><span data-stu-id="5ed3b-115">In either the [Action center](#infolog-time) or the [event log](#event-log-time), look at the execution time of the report.</span></span>
2. <span data-ttu-id="5ed3b-116">Confrontare il tempo di esecuzione del report con il tempo di esecuzione totale nello scenario.</span><span class="sxs-lookup"><span data-stu-id="5ed3b-116">Compare the execution time of the report with the total execution time in the scenario.</span></span>
3. <span data-ttu-id="5ed3b-117">Se il tempo di esecuzione del report è molto inferiore al tempo di esecuzione totale, considerare la quantità di dati elaborati dal report:</span><span class="sxs-lookup"><span data-stu-id="5ed3b-117">If the execution time of the report is much less than the total execution time, consider the amount of data that the report processes:</span></span>

    - <span data-ttu-id="5ed3b-118">Se il report elabora una piccola quantità di dati, il problema potrebbe riguardare il tempo di caricamento della configurazione.</span><span class="sxs-lookup"><span data-stu-id="5ed3b-118">If the report processes a small amount of data, the issue might involve the loading time of the configuration.</span></span>
    - <span data-ttu-id="5ed3b-119">Se il report elabora una grande quantità di dati, il problema potrebbe riguardare la preelaborazione di X++.</span><span class="sxs-lookup"><span data-stu-id="5ed3b-119">If the report processes a large amount of data, the issue might involve preprocessing X++.</span></span> <span data-ttu-id="5ed3b-120">Usare il [parser di traccia](#analyze-trace-parser-trace) per analizzare questo caso.</span><span class="sxs-lookup"><span data-stu-id="5ed3b-120">Use [Trace parser](#analyze-trace-parser-trace) to analyze this case.</span></span>

    <span data-ttu-id="5ed3b-121">Per altri casi, vedere le sezioni successive.</span><span class="sxs-lookup"><span data-stu-id="5ed3b-121">For other cases, see the next sections.</span></span>

4. <span data-ttu-id="5ed3b-122">Eseguire più test che coinvolgono diverse quantità di dati per determinare in che modo il tempo di esecuzione dipende dalla quantità di dati.</span><span class="sxs-lookup"><span data-stu-id="5ed3b-122">Run multiple tests that involve different amounts of data to determine how the execution time depends on the amount of data.</span></span>

### <a name="analyze-trace-parser-traces"></a><a name="analyze-trace-parser-trace"></a><span data-ttu-id="5ed3b-123">Analizzare le tracce con il parser di traccia</span><span class="sxs-lookup"><span data-stu-id="5ed3b-123">Analyze Trace parser traces</span></span>

<span data-ttu-id="5ed3b-124">Preparare un piccolo esempio o raccogliere diverse tracce durante le parti casuali della generazione del rapporto.</span><span class="sxs-lookup"><span data-stu-id="5ed3b-124">Prepare a small example, or collect several traces during random parts of the report generation.</span></span>

<span data-ttu-id="5ed3b-125">Quindi, nel [parser di traccia](#trace-parser), eseguire un-analisi bottom-to-up standard e rispondere alle seguenti domande:</span><span class="sxs-lookup"><span data-stu-id="5ed3b-125">Then, in [Trace parser](#trace-parser), do a standard bottom-to-up analysis, and answer the following questions:</span></span>

- <span data-ttu-id="5ed3b-126">Quali sono i metodi migliori in termini di consumo di tempo?</span><span class="sxs-lookup"><span data-stu-id="5ed3b-126">What are the top methods in terms of time consumption?</span></span>
- <span data-ttu-id="5ed3b-127">Quanta parte del tempo totale utilizzano questi metodi?</span><span class="sxs-lookup"><span data-stu-id="5ed3b-127">What part of the overall time do those methods use?</span></span>

<span data-ttu-id="5ed3b-128">Rispondere alle stesse domande per le query.</span><span class="sxs-lookup"><span data-stu-id="5ed3b-128">Answer the same questions for queries.</span></span>

<span data-ttu-id="5ed3b-129">Se si nota che i metodi sono preceduti dal prefisso "ER", passare alla sezione successiva.</span><span class="sxs-lookup"><span data-stu-id="5ed3b-129">If you see that methods are prefixed with "ER," move on to the next section.</span></span>

<span data-ttu-id="5ed3b-130">Se i metodi o le query hanno avuto origine nella suite di applicazioni, prendere in considerazione le ottimizzazioni generiche (ad esempio la creazione di indici).</span><span class="sxs-lookup"><span data-stu-id="5ed3b-130">If you see that methods or queries originated in the application suite, consider generic optimizations (for example, create indexes).</span></span>

<span data-ttu-id="5ed3b-131">Analizzare il numero di chiamate.</span><span class="sxs-lookup"><span data-stu-id="5ed3b-131">Analyze the number of calls.</span></span> <span data-ttu-id="5ed3b-132">Se il numero è significativamente più alto del previsto, prendere in considerazione la memorizzazione nella cache dei nodi corrispondenti della configurazione.</span><span class="sxs-lookup"><span data-stu-id="5ed3b-132">If the number is significantly higher than expected, consider caching the corresponding nodes of the configuration.</span></span>

### <a name="analyze-database-calls"></a><a name="analyze-database-calls"></a><span data-ttu-id="5ed3b-133">Analizzare le chiamate al database</span><span class="sxs-lookup"><span data-stu-id="5ed3b-133">Analyze database calls</span></span>

<span data-ttu-id="5ed3b-134">Preparare un esempio che contenga una piccola quantità di dati, in modo da poter raccogliere una [traccia ER](#electronic-reporting-traces).</span><span class="sxs-lookup"><span data-stu-id="5ed3b-134">Prepare an example that has a small amount of data, so that you can collect an [ER trace](#electronic-reporting-traces).</span></span>

<span data-ttu-id="5ed3b-135">Quindi, aprire la traccia nella soluzione di progettazione del mapping del modello ER e guardare in fondo alla pagina.</span><span class="sxs-lookup"><span data-stu-id="5ed3b-135">Then open the trace in the ER model mapping designer, and look at the bottom of the page.</span></span> <span data-ttu-id="5ed3b-136">Rispondere alle seguenti domande:</span><span class="sxs-lookup"><span data-stu-id="5ed3b-136">Answer the following questions:</span></span>

- <span data-ttu-id="5ed3b-137">C'è una duplicazione della query?</span><span class="sxs-lookup"><span data-stu-id="5ed3b-137">Is there any query duplication?</span></span> <span data-ttu-id="5ed3b-138">In caso affermativo, considerare una delle seguenti correzioni:</span><span class="sxs-lookup"><span data-stu-id="5ed3b-138">If there is, consider one of the following fixes:</span></span>

    - <span data-ttu-id="5ed3b-139">[Usare la memorizzazione nella cache](#use-caching) se si pensa che ci siano più chiamate all'interno di un unico record padre.</span><span class="sxs-lookup"><span data-stu-id="5ed3b-139">[Use caching](#use-caching) if you think that there are several calls inside one parent record.</span></span>
    - <span data-ttu-id="5ed3b-140">[Usare un campo calcolato memorizzato nella cache e parametrizzato](#cached-parameterized) se si pensa che ci siano chiamate allo stesso record all'interno di record diversi.</span><span class="sxs-lookup"><span data-stu-id="5ed3b-140">[Use a cached, parameterized calculated field](#cached-parameterized) if you think that there are calls to the same record inside different records.</span></span>
    - <span data-ttu-id="5ed3b-141">[Usare un'origine dati **JOIN**](#use-join-datasource) se occorre leggere un numero elevato di record diversi da un database.</span><span class="sxs-lookup"><span data-stu-id="5ed3b-141">[Use a **JOIN** data source](#use-join-datasource) if you have to read to a substantial number of different records from a database.</span></span>

- <span data-ttu-id="5ed3b-142">Il numero di query e record recuperati corrisponde alla quantità complessiva di dati?</span><span class="sxs-lookup"><span data-stu-id="5ed3b-142">Does the number of queries and fetched records correspond to the overall amount of data?</span></span> <span data-ttu-id="5ed3b-143">Ad esempio, se un documento ha 10 righe, le statistiche mostrano che il report estrae 10 righe o 1.000 righe?</span><span class="sxs-lookup"><span data-stu-id="5ed3b-143">For example, if a document has 10 lines, do the statistics show that the report extracts 10 lines or 1,000 lines?</span></span> <span data-ttu-id="5ed3b-144">Se si dispone di un numero considerevole di record recuperati, prendere in considerazione una delle seguenti correzioni:</span><span class="sxs-lookup"><span data-stu-id="5ed3b-144">If you have a substantial number of fetched records, consider one of the following fixes:</span></span>

    - <span data-ttu-id="5ed3b-145">[Usare la funzione **FILTER** anziché la funzione **WHERE**](#filter) per elaborare i dati sul lato SQL Server.</span><span class="sxs-lookup"><span data-stu-id="5ed3b-145">[Use the **FILTER** function instead of the **WHERE** function](#filter) to process data on the SQL Server side.</span></span>
    - <span data-ttu-id="5ed3b-146">Utilizzare la memorizzazione nella cache per evitare di recuperare gli stessi dati.</span><span class="sxs-lookup"><span data-stu-id="5ed3b-146">Use caching to avoid fetching the same data.</span></span>
    - <span data-ttu-id="5ed3b-147">[Utilizzare le funzioni dei dati raccolti](#collected-data) per evitare di recuperare gli stessi dati per il riepilogo.</span><span class="sxs-lookup"><span data-stu-id="5ed3b-147">[Use collected data functions](#collected-data) to avoid fetching the same data for summarization.</span></span>

### <a name="analyze-perfview-traces"></a><span data-ttu-id="5ed3b-148">Analizzare le tracce di PerfView</span><span class="sxs-lookup"><span data-stu-id="5ed3b-148">Analyze PerfView traces</span></span>

<span data-ttu-id="5ed3b-149">[PerfView](#perfview) è uno strumento per sviluppatori esperti.</span><span class="sxs-lookup"><span data-stu-id="5ed3b-149">[PerfView](#perfview) is a tool for experienced developers.</span></span> <span data-ttu-id="5ed3b-150">Per informazioni più dettagliate sui seguenti passaggi, vedere [Nozioni di base sull'indagine in tempo reale](https://channel9.msdn.com/Series/PerfView-Tutorial/Tutorial-12-Wall-Clock-Time-Investigation-Basics).</span><span class="sxs-lookup"><span data-stu-id="5ed3b-150">For more detailed information about the following steps, see [Wall Clock Time Investigation Basics](https://channel9.msdn.com/Series/PerfView-Tutorial/Tutorial-12-Wall-Clock-Time-Investigation-Basics).</span></span>

1. <span data-ttu-id="5ed3b-151">Raccogliere una traccia utilizzando il tempo di thread.</span><span class="sxs-lookup"><span data-stu-id="5ed3b-151">Collect a trace by using thread time.</span></span>
2. <span data-ttu-id="5ed3b-152">Includere solo gli stack che usano **runUnattended**, per filtrare solo il thread che ha l'esecuzione della configurazione.</span><span class="sxs-lookup"><span data-stu-id="5ed3b-152">Include only stacks that use **runUnattended**, to filter only the thread that has configuration execution.</span></span> <span data-ttu-id="5ed3b-153">(Aggiungere **runUnattended** alla casella di input **IncPats**.)</span><span class="sxs-lookup"><span data-stu-id="5ed3b-153">(Add **runUnattended** to the **IncPats** input box.)</span></span>
3. <span data-ttu-id="5ed3b-154">Ridurre tutta la CPU, la rete e il tempo bloccato.</span><span class="sxs-lookup"><span data-stu-id="5ed3b-154">Fold all CPU, network, and blocked time.</span></span>
4. <span data-ttu-id="5ed3b-155">Caricare le [impostazioni ER predefinite per PerfView](https://download.microsoft.com/download/2/d/0/2d037b0f-ffd1-4d65-b64f-fcdf51f2c81f/ER_PerfViewPresets.xml).</span><span class="sxs-lookup"><span data-stu-id="5ed3b-155">Load [ER presets for PerfView](https://download.microsoft.com/download/2/d/0/2d037b0f-ffd1-4d65-b64f-fcdf51f2c81f/ER_PerfViewPresets.xml).</span></span>
5. <span data-ttu-id="5ed3b-156">Selezionare **ER** \> **Altre impostazioni predefinite**.</span><span class="sxs-lookup"><span data-stu-id="5ed3b-156">Select **ER** \> **Other preset**.</span></span>
6. <span data-ttu-id="5ed3b-157">Guardare i nomi:</span><span class="sxs-lookup"><span data-stu-id="5ed3b-157">Look at the names:</span></span>

    - <span data-ttu-id="5ed3b-158">Probabilmente verrà mostrato il codice della piattaforma che consuma più tempo.</span><span class="sxs-lookup"><span data-stu-id="5ed3b-158">You will probably see the platform code that consumes the most time.</span></span>
    - <span data-ttu-id="5ed3b-159">È possibile toccare due volte (o fare doppio clic) ed esaminare l'elenco **callees**.</span><span class="sxs-lookup"><span data-stu-id="5ed3b-159">You can double-tap (or double-click) and go up through **callees**.</span></span>

        <span data-ttu-id="5ed3b-160">Se si trovano classi con il prefisso "ERExpression" e se queste sono funzioni correlate a formule, è possibile inferire il nome della funzione in base al nome della classe e guardare il repository ER per visualizzare gli attributi.</span><span class="sxs-lookup"><span data-stu-id="5ed3b-160">If you find classes that have the prefix "ERExpression," and if they are functions that are related to formulas, you can guess the function name based on the class name, and you can look at the ER repo to view the attributes.</span></span>

### <a name="fixes"></a><span data-ttu-id="5ed3b-161">Correzioni</span><span class="sxs-lookup"><span data-stu-id="5ed3b-161">Fixes</span></span>

- <span data-ttu-id="5ed3b-162">Se si nota che la maggior parte del tempo della CPU viene consumato dalle query, provare a ridurre il numero di query:</span><span class="sxs-lookup"><span data-stu-id="5ed3b-162">If you see that most of the CPU time is consumed by queries, try to reduce the number of queries:</span></span>

    - <span data-ttu-id="5ed3b-163">[Rivedere la traccia ER](#analyze-database-calls) per query duplicate.</span><span class="sxs-lookup"><span data-stu-id="5ed3b-163">[Review the ER trace](#analyze-database-calls) for duplicated queries.</span></span>
    - <span data-ttu-id="5ed3b-164">Guardare quanti record vengono recuperati e valutare quanti dati dovrebbero essere teoricamente recuperati.</span><span class="sxs-lookup"><span data-stu-id="5ed3b-164">See how many records are fetched, and evaluate how much data should theoretically be fetched.</span></span>

- <span data-ttu-id="5ed3b-165">Se la maggior parte del tempo della CPU viene consumato dalle funzioni utilizzate, provare a trovare il punto nella configurazione che utilizza la maggior parte delle risorse.</span><span class="sxs-lookup"><span data-stu-id="5ed3b-165">If you see that most of the CPU time is consumed by the functions that are used, try to find the place in the configuration that consumes the most resources.</span></span>
- <span data-ttu-id="5ed3b-166">Se la maggior parte del tempo della CPU viene consumato dalle funzioni di raccolta dati, considerare la possibilità di sostituirle con *SQL group by* sul lato di mapping del modello.</span><span class="sxs-lookup"><span data-stu-id="5ed3b-166">If you see that most of the CPU time is consumed by data collection functions, consider replacing them with *SQL group by* on the model mapping side.</span></span>

### <a name="collecting-data"></a><a name="collecting-data"></a><span data-ttu-id="5ed3b-167">Raccolta dei dati</span><span class="sxs-lookup"><span data-stu-id="5ed3b-167">Collecting data</span></span>

<span data-ttu-id="5ed3b-168">A seconda dell'ambiente, esistono diversi modi per raccogliere i dati disponibili:</span><span class="sxs-lookup"><span data-stu-id="5ed3b-168">Depending on your environment, there are several ways to collect available data:</span></span>

- <span data-ttu-id="5ed3b-169">Ottenere il tempo di esecuzione totale:</span><span class="sxs-lookup"><span data-stu-id="5ed3b-169">Get the total running time:</span></span>

    - <span data-ttu-id="5ed3b-170">Dal Centro azioni</span><span class="sxs-lookup"><span data-stu-id="5ed3b-170">From the Action center</span></span>
    - <span data-ttu-id="5ed3b-171">Dal registro degli eventi</span><span class="sxs-lookup"><span data-stu-id="5ed3b-171">From the event log</span></span>

- <span data-ttu-id="5ed3b-172">Creare un profilo per l'esecuzione:</span><span class="sxs-lookup"><span data-stu-id="5ed3b-172">Profile the execution:</span></span>

    - <span data-ttu-id="5ed3b-173">Usando gli strumenti ER</span><span class="sxs-lookup"><span data-stu-id="5ed3b-173">By using ER tools</span></span>
    - <span data-ttu-id="5ed3b-174">Usando il parser di traccia</span><span class="sxs-lookup"><span data-stu-id="5ed3b-174">By using Trace parser</span></span>
    - <span data-ttu-id="5ed3b-175">Usando PerfView</span><span class="sxs-lookup"><span data-stu-id="5ed3b-175">By using PerfView</span></span>

#### <a name="collecting-data-in-a-production-environment"></a><span data-ttu-id="5ed3b-176">Raccolta dei dati in un ambiente di produzione</span><span class="sxs-lookup"><span data-stu-id="5ed3b-176">Collecting data in a production environment</span></span>

<span data-ttu-id="5ed3b-177">A volte, i problemi possono essere riprodotti solo in un ambiente di produzione.</span><span class="sxs-lookup"><span data-stu-id="5ed3b-177">Sometimes, issues can be reproduced only in a production environment.</span></span> <span data-ttu-id="5ed3b-178">I dati possono essere raccolti in uno dei modi indicati di seguito:</span><span class="sxs-lookup"><span data-stu-id="5ed3b-178">Data can be collected in the following ways:</span></span>

- <span data-ttu-id="5ed3b-179">Usando le tracce del [parser di traccia](../perf-test/trace-trace-tutorial.md)</span><span class="sxs-lookup"><span data-stu-id="5ed3b-179">By using [Trace parser](../perf-test/trace-trace-tutorial.md) traces</span></span>
- <span data-ttu-id="5ed3b-180">Usando le tracce dell'[esecuzione ER](trace-execution-er-troubleshoot-perf.md)</span><span class="sxs-lookup"><span data-stu-id="5ed3b-180">By using [ER execution](trace-execution-er-troubleshoot-perf.md) traces</span></span>
- <span data-ttu-id="5ed3b-181">Usando il tempo di esecuzione totale</span><span class="sxs-lookup"><span data-stu-id="5ed3b-181">By using the total execution time</span></span>

#### <a name="collecting-data-in-a-development-environment"></a><span data-ttu-id="5ed3b-182">Raccolta dei dati in un ambiente di sviluppo</span><span class="sxs-lookup"><span data-stu-id="5ed3b-182">Collecting data in a development environment</span></span>

<span data-ttu-id="5ed3b-183">Oltre agli strumenti che possono essere utilizzati in un ambiente di produzione, esistono diversi strumenti che è possibile utilizzare in un ambiente di sviluppo:</span><span class="sxs-lookup"><span data-stu-id="5ed3b-183">In addition to the tools that can be used in a production environment, there are several tools that you can use in a development environment:</span></span>

- <span data-ttu-id="5ed3b-184">Registro eventi (Microsoft-Dynamics-ElectronicReporting).</span><span class="sxs-lookup"><span data-stu-id="5ed3b-184">Event log (Microsoft-Dynamics-ElectronicReporting).</span></span> <span data-ttu-id="5ed3b-185">Questo registro può fornire il tempo di esecuzione totale.</span><span class="sxs-lookup"><span data-stu-id="5ed3b-185">This log can give you the total execution time.</span></span>
- <span data-ttu-id="5ed3b-186">Strumenti .NET comuni, come PerfView.</span><span class="sxs-lookup"><span data-stu-id="5ed3b-186">Common .NET tools, such as PerfView.</span></span>

<span data-ttu-id="5ed3b-187">Inoltre, un ambiente di sviluppo offre maggiore flessibilità per sperimentare.</span><span class="sxs-lookup"><span data-stu-id="5ed3b-187">Additionally, a development environment gives you more flexibility to experiment.</span></span> <span data-ttu-id="5ed3b-188">Ad esempio, è possibile disattivare parti dei report per vedere come viene influenzato il tempo di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="5ed3b-188">For example, you can turn off parts of reports to see how the execution time is affected.</span></span>

### <a name="tools"></a><a name="tools"></a><span data-ttu-id="5ed3b-189">Strumenti</span><span class="sxs-lookup"><span data-stu-id="5ed3b-189">Tools</span></span>

#### <a name="execution-time-in-the-action-center"></a><a name="infolog-time"></a><span data-ttu-id="5ed3b-190">Tempo di esecuzione nel Centro azioni</span><span class="sxs-lookup"><span data-stu-id="5ed3b-190">Execution time in the Action center</span></span>

<span data-ttu-id="5ed3b-191">ER può mostrare il tempo di esecuzione della configurazione nel Centro azioni.</span><span class="sxs-lookup"><span data-stu-id="5ed3b-191">ER can show the execution time of the configuration in the Action center.</span></span> <span data-ttu-id="5ed3b-192">Questa opzione funziona solo per un utente specifico e un'azienda specifica e solo per sessioni interattive.</span><span class="sxs-lookup"><span data-stu-id="5ed3b-192">This option works only for a specific user and a specific company, and only for interactive sessions.</span></span> <span data-ttu-id="5ed3b-193">Per rendere disponibile questa funzione, seguire questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="5ed3b-193">To make this feature available, follow these steps.</span></span>

1. <span data-ttu-id="5ed3b-194">Andare a **Amministrazione organizzazione** \> **Creazione di report elettronici** \> **Configurazioni**.</span><span class="sxs-lookup"><span data-stu-id="5ed3b-194">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="5ed3b-195">Nella pagina **Configurazioni**, nel Riquadro azioni, nella scheda **Configurazioni**, nel gruppo **Impostazioni avanzate**, selezionare **Parametri utente**.</span><span class="sxs-lookup"><span data-stu-id="5ed3b-195">On the **Configurations** page, on the Action Pane, on the **Configurations** tab, in the **Advanced settings** group, select **User parameters**.</span></span>
3. <span data-ttu-id="5ed3b-196">Nella finestra di dialogo **Parametri utente**, impostare l'opzione **Mostra tempo di generazione file** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="5ed3b-196">In the **User parameters** dialog box, set the **Show file generation time** option to **Yes**.</span></span>

#### <a name="execution-time-in-the-event-log"></a><a name="event-log-time"></a><span data-ttu-id="5ed3b-197">Tempo di esecuzione nel registro eventi</span><span class="sxs-lookup"><span data-stu-id="5ed3b-197">Execution time in the event log</span></span>

1. <span data-ttu-id="5ed3b-198">Aprire il visualizzatore eventi di Windows.</span><span class="sxs-lookup"><span data-stu-id="5ed3b-198">Open Windows Event Viewer.</span></span>
2. <span data-ttu-id="5ed3b-199">In **Registri applicazioni e servizi**, aprire **Microsoft-Dynamics-ElectronicReporting/Operativo**.</span><span class="sxs-lookup"><span data-stu-id="5ed3b-199">Under **Applications and Services logs**, open **Microsoft-Dynamics-ElectronicReporting/Operational**.</span></span>
3. <span data-ttu-id="5ed3b-200">Cercare gli eventi **FormatMapingRun** in cui **EventID=2**, poiché questi eventi contengono informazioni sul tempo trascorso.</span><span class="sxs-lookup"><span data-stu-id="5ed3b-200">Look for **FormatMapingRun** events where **EventID=2**, because these events contain the information about elapsed time.</span></span>

#### <a name="trace-parser-traces"></a><a name="trace-parser"></a><span data-ttu-id="5ed3b-201">Tracce del parser di traccia</span><span class="sxs-lookup"><span data-stu-id="5ed3b-201">Trace parser traces</span></span> 

<span data-ttu-id="5ed3b-202">Poiché ER è implementato in X++, è possibile usare strumenti X++ comuni per analizzare le prestazioni.</span><span class="sxs-lookup"><span data-stu-id="5ed3b-202">Because ER is implemented in X++, you can use common X++ tools to analyze performance.</span></span> <span data-ttu-id="5ed3b-203">Per ulteriori informazioni, vedere [Acquisire le tracce usando il parser di traccia](../perf-test/trace-trace-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="5ed3b-203">For more information, see [Take traces by using Trace parser](../perf-test/trace-trace-tutorial.md).</span></span>

<span data-ttu-id="5ed3b-204">Esistono alcune limitazioni a questo approccio.</span><span class="sxs-lookup"><span data-stu-id="5ed3b-204">There are a few limitations to this approach.</span></span> <span data-ttu-id="5ed3b-205">Poiché parte di ER è implementata in C#, non tutti i dettagli saranno disponibili.</span><span class="sxs-lookup"><span data-stu-id="5ed3b-205">Because part of ER is implemented in C#, not all the details will be available.</span></span> <span data-ttu-id="5ed3b-206">Tuttavia, è possibile visualizzare i dettagli sull'utilizzo dei dati.</span><span class="sxs-lookup"><span data-stu-id="5ed3b-206">However, you can view the data usage details.</span></span> <span data-ttu-id="5ed3b-207">Inoltre, lunghe esecuzioni di report possono superare i limiti di archiviazione delle tracce.</span><span class="sxs-lookup"><span data-stu-id="5ed3b-207">Additionally, long report runs can exceed trace storage limitations.</span></span>

#### <a name="er-traces"></a><a name="electronic-reporting-traces"></a><span data-ttu-id="5ed3b-208">Tracce ER</span><span class="sxs-lookup"><span data-stu-id="5ed3b-208">ER traces</span></span>

<span data-ttu-id="5ed3b-209">ER è in grado di raccogliere le proprie tracce e dispone di strumenti di visualizzazione e analisi per tali tracce.</span><span class="sxs-lookup"><span data-stu-id="5ed3b-209">ER can collect its own traces, and it has visualization and analysis tools for those traces.</span></span> <span data-ttu-id="5ed3b-210">Per altre informazioni, vedi [Tenere traccia dell'esecuzione dei formati di creazione di report elettronici per risolvere i problemi di prestazioni](trace-execution-er-troubleshoot-perf.md).</span><span class="sxs-lookup"><span data-stu-id="5ed3b-210">For more information, see [Trace the execution of ER formats to troubleshoot performance issues](trace-execution-er-troubleshoot-perf.md).</span></span>

#### <a name="perfview"></a><a name="perfview"></a><span data-ttu-id="5ed3b-211">PerfView</span><span class="sxs-lookup"><span data-stu-id="5ed3b-211">PerfView</span></span>

<span data-ttu-id="5ed3b-212">Poiché sia X++ che ER sono implementati sulla piattaforma .NET, è possibile usare strumenti .NET comuni.</span><span class="sxs-lookup"><span data-stu-id="5ed3b-212">Because both X++ and ER are implemented on top of the .NET platform, you can use common .NET tools.</span></span> <span data-ttu-id="5ed3b-213">Ad esempio, puoi utilizzare lo strumento gratuito [PerfView](https://github.com/Microsoft/perfview).</span><span class="sxs-lookup"><span data-stu-id="5ed3b-213">For example, you can use the free [PerfView](https://github.com/Microsoft/perfview) tool.</span></span>

<span data-ttu-id="5ed3b-214">È anche possibile raccogliere dati dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="5ed3b-214">You can also collect data from the command line.</span></span> <span data-ttu-id="5ed3b-215">Ad esempio, lo script di Windows PowerShell seguente raccoglie il tempo di esecuzione fino all'interruzione dell'esecuzione di qualsiasi formato nel computer.</span><span class="sxs-lookup"><span data-stu-id="5ed3b-215">For example, the following Windows PowerShell script collects the execution time until any format execution is stopped on the machine.</span></span>

```powershell
c:\programs\PerfView collect "e:\traces\$(date -format "ddMMyyyy_hhmm").etl" `
    -CircularMB:20000 -ThreadTime `
    -NoNGenRundown `
    -StopOnEtwEvent:Microsoft-Dynamics-ElectronicReporting/FormatMappingRun/Stop
```

<span data-ttu-id="5ed3b-216">Esistono alcune limitazioni a questo approccio.</span><span class="sxs-lookup"><span data-stu-id="5ed3b-216">There are a few limitations to this approach.</span></span> <span data-ttu-id="5ed3b-217">È necessario disporre dell'accesso al computer.</span><span class="sxs-lookup"><span data-stu-id="5ed3b-217">You must have administrative access to the machine.</span></span> <span data-ttu-id="5ed3b-218">Inoltre, occorre essere uno sviluppatore esperto, perché la curva di apprendimento è particolarmente ripida.</span><span class="sxs-lookup"><span data-stu-id="5ed3b-218">Additionally, you must be an experienced developer, because there is a steep learning curve.</span></span>

### <a name="making-changes"></a><a name="making-changes"></a><span data-ttu-id="5ed3b-219">Apportare modifiche</span><span class="sxs-lookup"><span data-stu-id="5ed3b-219">Making changes</span></span>

#### <a name="use-caching"></a><a name="use-caching"></a><span data-ttu-id="5ed3b-220">Usare la memorizzazione nella cache</span><span class="sxs-lookup"><span data-stu-id="5ed3b-220">Use caching</span></span>

<span data-ttu-id="5ed3b-221">Sebbene la memorizzazione nella cache riduca la quantità di tempo necessaria per recuperare nuovamente i dati, ha un costo significativo in termini di memoria.</span><span class="sxs-lookup"><span data-stu-id="5ed3b-221">Although caching reduces the amount of time that is required to fetch data again, it costs memory.</span></span> <span data-ttu-id="5ed3b-222">Usare la memorizzazione nella cache nei casi in cui la quantità di dati recuperati non è molto grande.</span><span class="sxs-lookup"><span data-stu-id="5ed3b-222">Use caching in cases where the amount of fetched data isn't very large.</span></span> <span data-ttu-id="5ed3b-223">Per ulteriori informazioni e un esempio che mostra come utilizzare la memorizzazione nella cache, vedere [Migliorare il mapping del modello in base alle informazioni della traccia di esecuzione](trace-execution-er-troubleshoot-perf.md#improve-the-model-mapping-based-on-information-from-the-execution-trace).</span><span class="sxs-lookup"><span data-stu-id="5ed3b-223">For more information and an example that shows how to use caching, see [Improve the model mapping based on information from the execution trace](trace-execution-er-troubleshoot-perf.md#improve-the-model-mapping-based-on-information-from-the-execution-trace).</span></span>

#### <a name="use-a-cached-parameterized-calculated-field"></a><a name="cached-parameterized"></a><span data-ttu-id="5ed3b-224">Usare un campo calcolato memorizzato nella cache e parametrizzato</span><span class="sxs-lookup"><span data-stu-id="5ed3b-224">Use a cached, parameterized calculated field</span></span>

<span data-ttu-id="5ed3b-225">A volte, i valori devono essere cercati ripetutamente.</span><span class="sxs-lookup"><span data-stu-id="5ed3b-225">Sometimes, values must be looked up repeatedly.</span></span> <span data-ttu-id="5ed3b-226">Gli esempi includono nomi di account e numeri di conto.</span><span class="sxs-lookup"><span data-stu-id="5ed3b-226">Examples include account names and account numbers.</span></span> <span data-ttu-id="5ed3b-227">Per risparmiare tempo, è possibile creare un campo calcolato con parametri al livello più alto, quindi aggiungere il campo alla cache.</span><span class="sxs-lookup"><span data-stu-id="5ed3b-227">To help save time, you can create a calculated field that has parameters on the top level, and then add the field to the cache.</span></span>

<span data-ttu-id="5ed3b-228">Si consiglia di utilizzare questo approccio solo quando la dimensione dei dati memorizzati nella cache è ridotta.</span><span class="sxs-lookup"><span data-stu-id="5ed3b-228">We recommend that you use this approach only when the size of the cached data is small.</span></span> <span data-ttu-id="5ed3b-229">Per ulteriori informazioni, vedere [Migliorare le prestazioni delle soluzioni ER aggiungendo origini dati CAMPO CALCOLATO parametrizzate](er-calculated-field-ds-performance.md).</span><span class="sxs-lookup"><span data-stu-id="5ed3b-229">For more information, see [Improve the performance of ER solutions by adding parameterized CALCULATED FIELD data sources](er-calculated-field-ds-performance.md).</span></span>

#### <a name="use-a-join-data-source"></a><a name="use-join-datasource"></a><span data-ttu-id="5ed3b-230">Usare un'origine dati JOIN</span><span class="sxs-lookup"><span data-stu-id="5ed3b-230">Use a JOIN data source</span></span>

<span data-ttu-id="5ed3b-231">Un'origine dati **JOIN** permette di recuperare più record connessi tramite un'unica query.</span><span class="sxs-lookup"><span data-stu-id="5ed3b-231">A **JOIN** data source enables several connected records to be fetched by one query.</span></span> <span data-ttu-id="5ed3b-232">Non è necessario utilizzare una query separata per recuperare ogni record connesso.</span><span class="sxs-lookup"><span data-stu-id="5ed3b-232">A separate query doesn't have to be used to fetch each connected record.</span></span> <span data-ttu-id="5ed3b-233">Ad esempio, se si dispone di 1.000 righe e si recuperano i dati dell'articolo per ogni riga per relazione, si avranno 1.001 query (= 1.000 + 1).</span><span class="sxs-lookup"><span data-stu-id="5ed3b-233">For example, if you have 1,000 lines, and you fetch item data for each line by relation, you will have 1,001 queries (= 1,000 + 1).</span></span> <span data-ttu-id="5ed3b-234">Se si usa un'origine dati **JOIN**, sarà sufficiente un'unica query per recuperare gli stessi dati.</span><span class="sxs-lookup"><span data-stu-id="5ed3b-234">If you use a **JOIN** data source, you will use only one query to fetch the same data.</span></span> <span data-ttu-id="5ed3b-235">Per maggiori informazioni, vedere [Usare le origini dati JOIN nei mapping di modello ER per ottenere dati da più tabelle dell'applicazione](er-join-data-sources.md).</span><span class="sxs-lookup"><span data-stu-id="5ed3b-235">For more information, see [Use JOIN data sources in ER model mappings to get data from multiple application tables](er-join-data-sources.md).</span></span>

#### <a name="use-the-filter-function-instead-of-the-where-function"></a><a name="filter"></a><span data-ttu-id="5ed3b-236">Usare la funzione FILTER anziché la funzione WHERE</span><span class="sxs-lookup"><span data-stu-id="5ed3b-236">Use the FILTER function instead of the WHERE function</span></span>

<span data-ttu-id="5ed3b-237">La funzione **[FILTER](er-functions-list-filter.md)** esegue condizioni su SQL Server, mentre la funzione **WHERE** recupera tutti i dati dall'elenco, un record alla vota, e applica la condizione per ciascun record.</span><span class="sxs-lookup"><span data-stu-id="5ed3b-237">The **[FILTER](er-functions-list-filter.md)** function runs conditions on SQL Server, whereas the **WHERE** function fetches all data from the list, one record at a time, and applies the condition for each record.</span></span> <span data-ttu-id="5ed3b-238">Ad esempio, si desidera selezionare un record su 1.000 record.</span><span class="sxs-lookup"><span data-stu-id="5ed3b-238">For example, you want to select one record out of 1,000 records.</span></span> <span data-ttu-id="5ed3b-239">Se si usa **WHERE**, verranno recuperati tutti i 1.000 record.</span><span class="sxs-lookup"><span data-stu-id="5ed3b-239">If you use **WHERE**, all 1,000 records will be fetched.</span></span> <span data-ttu-id="5ed3b-240">Se invece si usa **FILTER**, verrà recuperato un singolo record.</span><span class="sxs-lookup"><span data-stu-id="5ed3b-240">However, if you use **FILTER**, exactly one record will be fetched.</span></span> <span data-ttu-id="5ed3b-241">**FILTER** può anche usare gli indici sul lato database.</span><span class="sxs-lookup"><span data-stu-id="5ed3b-241">**FILTER** can also use indexes on the database side.</span></span>

#### <a name="using-collected-data-functions-or-an-accumulated-data-data-source"></a><a name="collected-data"></a><span data-ttu-id="5ed3b-242">Utilizzo delle funzioni dei dati raccolti o di un'origine dati accumulata</span><span class="sxs-lookup"><span data-stu-id="5ed3b-242">Using collected data functions or an accumulated data data source</span></span>

<span data-ttu-id="5ed3b-243">Se la configurazione ha un componente *group by* che riepiloga i dati precedentemente recuperati per report, il componente recupererà nuovamente tutti i dati.</span><span class="sxs-lookup"><span data-stu-id="5ed3b-243">If your configuration has a *group by* component that summarizes previously fetched data by report, the component will fetch all the data again.</span></span> <span data-ttu-id="5ed3b-244">Utilizzando le funzioni dei dati raccolti, si abilite ER ad accumulare dati durante il primo recupero.</span><span class="sxs-lookup"><span data-stu-id="5ed3b-244">By using collected data functions, you enable ER to accumulate data during the first fetch.</span></span> <span data-ttu-id="5ed3b-245">Per ulteriori informazioni, vedere [Configurare il formato ER per eseguire il conteggio e la sommatoria](tasks/er-format-counting-summing-2.md).</span><span class="sxs-lookup"><span data-stu-id="5ed3b-245">For more information, see [ER Configure format to do counting and summing](tasks/er-format-counting-summing-2.md).</span></span>

#### <a name="rewrite-parts-of-the-configuration-in-x"></a><span data-ttu-id="5ed3b-246">Riscrivere parti della configurazione in X++</span><span class="sxs-lookup"><span data-stu-id="5ed3b-246">Rewrite parts of the configuration in X++</span></span>

<span data-ttu-id="5ed3b-247">ER supporta i metodi di chiamata di tabelle e classi, incluse le estensioni.</span><span class="sxs-lookup"><span data-stu-id="5ed3b-247">ER supports calling methods of tables and classes, including extensions.</span></span> <span data-ttu-id="5ed3b-248">Considerare la possibilità di riscrivere parti del mapping del modello in X++ per migliorare le prestazioni.</span><span class="sxs-lookup"><span data-stu-id="5ed3b-248">Consider rewriting parts of the model mapping in X++ to help improve performance.</span></span>

<span data-ttu-id="5ed3b-249">ER può utilizzare dati dalle seguenti origini:</span><span class="sxs-lookup"><span data-stu-id="5ed3b-249">ER can consume data from the following sources:</span></span>

- <span data-ttu-id="5ed3b-250">Classi (origini dati **oggetto** e **classe**)</span><span class="sxs-lookup"><span data-stu-id="5ed3b-250">Classes (**object** and **class** data sources)</span></span>
- <span data-ttu-id="5ed3b-251">Tabelle (origini dati **tabella** e **record di tabella**)</span><span class="sxs-lookup"><span data-stu-id="5ed3b-251">Tables (**table** and **table records** data sources)</span></span>

<span data-ttu-id="5ed3b-252">L'[API ER](er-apis-app73.md#how-to-access-internal-x-objects-by-using-erobjectsfactory) fornisce inoltre un modo per inviare dati precalcolati dal codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="5ed3b-252">The [ER API](er-apis-app73.md#how-to-access-internal-x-objects-by-using-erobjectsfactory) also provides a way to send precalculated data from the calling code.</span></span> <span data-ttu-id="5ed3b-253">La suite di applicazioni contiene numerosi esempi di questo approccio.</span><span class="sxs-lookup"><span data-stu-id="5ed3b-253">The application suite contains numerous examples of this approach.</span></span>
