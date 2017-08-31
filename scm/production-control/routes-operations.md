---
title: Cicli di lavorazione e operazioni
description: In questo argomento sono riportate informazioni su cicli di lavorazione e operazioni. Un ciclo di lavorazione definisce il processo per la produzione di un prodotto o della variante prodotto. Viene descritto ogni passaggio (operazione) del processo di produzione insieme all'ordine in cui queste operazioni devono essere eseguite. Per ciascun passaggio, il ciclo di lavorazione definisce inoltre le risorse operative richieste, il tempo di attrezzaggio necessario e il tempo di esecuzione e il modo in cui il costo deve essere calcolato.
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BOMDesigner, BOMDesignerRouteVersion, Route, RouteInventProd, RouteOpr, RouteOprTable
ms.author: sorenand
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 268124
ms.assetid: f78d5836-3e71-42b7-a5d1-41f19228d9d2
ms.search.region: Global
ms.search.industry: Manufacturing
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 08c38aada355583c5a6872f75b57db95d9b81786
ms.openlocfilehash: 017985645e0f77e7f269fce2932c0ec0f6eaaa1c
ms.contentlocale: it-it
ms.lasthandoff: 07/27/2017

---

# <a name="routes-and-operations"></a>Cicli di lavorazione e operazioni

[!include[banner](../includes/banner.md)]


In questo argomento sono riportate informazioni su cicli di lavorazione e operazioni. Un ciclo di lavorazione definisce il processo per la produzione di un prodotto o della variante prodotto. Viene descritto ogni passaggio (operazione) del processo di produzione insieme all'ordine in cui queste operazioni devono essere eseguite. Per ciascun passaggio, il ciclo di lavorazione definisce inoltre le risorse operative richieste, il tempo di attrezzaggio necessario e il tempo di esecuzione e il modo in cui il costo deve essere calcolato.

<a name="overview"></a>Panoramica
--------

Un ciclo di lavorazione descrive l'ordine delle operazioni necessarie per la produzione di un prodotto o una variante prodotto. Per ciascuna operazione, il ciclo di lavorazione inoltre definisce le risorse operative richieste, il tempo di attrezzaggio ed esecuzione necessario per l'operazione e il modo in cui il costo deve essere calcolato. È possibile utilizzare lo stesso ciclo di lavorazione per produrre i più prodotti oppure definire un ciclo di lavorazione univoco per ogni variante prodotto o prodotto. È inoltre possibile avere più cicli di lavorazione per lo stesso prodotto. In questo caso, il ciclo di lavorazione utilizzato varia, in base ai fattori quali la quantità che deve essere prodotta. La definizione di un ciclo di lavorazione in Microsoft Dynamics 365 for Finance and Operations è costituito da quattro diversi elementi che, insieme, descrivono il processo di produzione:

-   **Ciclo di lavorazione** - un ciclo definisce la struttura del processo di produzione. In altre parole, definisce l'ordine delle operazioni.
-   **Operazione** - un'operazione identifica un passaggio denominato in un ciclo di lavorazione, ad esempio **Assemblaggio**. La stessa operazione può verificarsi in più cicli di lavorazione e può contenere un numero di operazioni diverso.
-   **Relazione operativa** - una relazione operativa definisce le proprietà operative di un'operazione, ad esempio il tempo di attrezzaggio, il tempo di esecuzione, le categorie costi, i parametri del consumo e i requisiti risorsa. La relazione operativa consente di impostare le proprietà operative di un'operazione per la variazione, in base al ciclo di lavorazione in cui l'operazione viene utilizzata o ai prodotti che vengono prodotti.
-   **Versione del ciclo di lavorazione** - una versione del ciclo di lavorazione definisce il ciclo di lavorazione specifico utilizzato per creare un prodotto o una variante prodotto. Le versioni dei cicli di lavorazione consentono ai cicli di lavorazione di essere riutilizzati nei prodotti o di essere modificati nel tempo. Inoltre consentono l'utilizzo dei diversi cicli di lavorazione per produrre lo stesso prodotto. In questo caso, il ciclo di lavorazione utilizzato dipende da fattori quali l'ubicazione o la quantità che deve essere prodotta.

## <a name="routes"></a>Cicli di lavorazione
Un ciclo di lavorazione descrive l'ordine delle operazioni utilizzate per la produzione di un prodotto o una variante prodotto. A ciascuna operazione viene assegnato un numero di operazione e un'operazione successiva. L'ordine delle operazioni forma una rete di cicli di lavorazione che può essere rappresentata da un grafico diretto con uno o più punti di origine e un unico punto finale. In Finance and Operations i cicli di lavorazione vengono distinti in base al tipo di struttura. I due tipi di cicli di lavorazione sono cicli di lavorazione semplici e reti di cicli di lavorazione. Nei parametri di controllo produzione, è possibile specificare se è possibile utilizzare solo i cicli di lavorazione semplici o reti più complesse di cicli di lavorazione.

### <a name="simple-routes"></a>Cicli di lavorazione semplici

Un ciclo di lavorazione semplice è sequenziale ed è disponibile un solo punto di partenza per il ciclo di lavorazione.  

[![Ciclo di lavorazione semplice](./media/routes-and-operations-1-simple-route.png)](./media/routes-and-operations-1-simple-route.png)  

Se si attiva solo i cicli di lavorazione semplici nei parametri di controllo produzione, Finance and Operations genera automaticamente i numeri delle operazioni (10, 20, 30 e così via) quando si definisce il ciclo di lavorazione.

### <a name="route-networks"></a>Reti di cicli di lavorazione

Se si consentono reti più complesse del ciclo di lavorazione nei parametri di controllo produzione, è possibile definire cicli di lavorazione con più punti di origine e più operazioni che possono essere eseguite in parallelo.  

[![Rete di cicli di lavorazione](./media/routes-and-operations-2-route-network.png)](./media/routes-and-operations-2-route-network.png)  

**Note:**

-   Ciascuna operazione può avere una sola operazione successiva e l'intero ciclo di lavorazione deve terminare con una sola operazione.
-   Non esiste alcuna garanzia che più operazioni con la stessa operazione successiva (ad esempio operazioni 30 e 40 nella precedente figura) verranno effettivamente eseguite in parallelo. La disponibilità e la capacità delle risorse possono determinare i vincoli nel modo in cui le operazioni sono programmate.
-   Non è possibile utilizzare 0 (zero) come numero di operazione. Questo numero è prenotato e viene utilizzato per specificare che l'ultima operazione del ciclo di lavorazione non dispone di operazione successiva.

### <a name="parallel-operations"></a>Operazioni parallele

Talvolta, una combinazione di più risorse operative che hanno caratteristiche diverse sono necessarie per eseguire un'operazione. Ad esempio, un'operazione di assemblaggio potrebbe richiedere una macchina, uno strumento e un lavoratore per ogni due macchine per la supervisione dell'operazione. Questo esempio può essere modellizzato utilizzando le operazioni parallele, in cui un'operazione è indicata come l'operazione primaria e le altre sono secondarie.  

[![Ciclo di lavorazione con operazioni primarie e secondarie](./media/routes-and-operations-3-parallel-operations.png)](./media/routes-and-operations-3-parallel-operations.png)  

In genere, l'operazione primaria rappresenta la risorsa collo di bottiglia e detta il tempo di esecuzione per le operazioni secondarie. Tuttavia, durante la programmazione che prevede la capacità limitata, le risorse che sono programmate per l'operazione primaria e le operazioni secondarie devono essere disponibili e avere allo stesso tempo capacità libera.  

Sia l'operazione primaria che le operazioni secondarie devono avere lo stesso numero di operazione (30 nella precedente figura).  

Nell'esempio precedente, il requisito risorsa per l'operazione primaria (30) è la macchina, mentre i requisiti risorsa per le operazioni secondarie (30' e 30'') sono lo strumento e il lavoratore. Un carico del 50% garantisce che il lavoratore programmato possa supervisionare due macchine contemporaneamente.

### <a name="approval-of-routes"></a>Approvazione cicli di lavorazione

Prima che un ciclo di lavorazione possa essere utilizzato nella pianificazione o nel processo di produzione, deve essere approvato. L'approvazione indica che la progettazione del ciclo di lavorazione è stata completata. Lo stesso prodotto rilasciato o varianti prodotto rilasciate possono avere più cicli di lavorazione approvati. In genere, l'approvazione di un ciclo di lavorazione si verifica quando la prima versione rilevante del ciclo di lavorazione è approvata. Tuttavia, in alcuni scenari aziendali, l'approvazione del ciclo di lavorazione e delle versione del ciclo di lavorazione sono attività separate che possono coinvolgere i proprietari del processo.  

Ogni ciclo di lavorazione può essere approvato o non approvato separatamente. Tuttavia, se un ciclo di lavorazione non è approvato, anche tutte le versioni del ciclo di lavorazione correlate non sono approvate. Nei parametri di controllo produzione, è possibile specificare se i cicli di lavorazione possono essere non approvati e se i cicli di lavorazione approvati possono essere modificati.  

Se è necessario tenere un registro per registrare chi approva ciascun ciclo di lavorazione è possibile richiedere firme elettroniche per l'approvazione di un ciclo di lavorazione. Gli utenti dovranno quindi confermare la propria identità utilizzando una [firma elettronica](/dynamics365/unified-operations/fin-and-ops/organization-administration/electronic-signature-overview).

## <a name="operations"></a>Operations
Un'operazione costituisce un passaggio del processo di produzione. In Finance and Operations ciascuna operazione ha un ID e una descrizione semplice. Nelle tabelle seguenti sono indicati gli esempi comuni delle operazioni di un'officina meccanica.

| Operazione  | descrizione        |
|------------|--------------------|
| PipeCut    | Taglio tubi       |
| TIGweld    | Saldatura TIG        |
| JigAssy    | Assemblaggio struttura di montaggio       |
| Ispezione | Ispezione di controllo qualità |

Le proprietà operative dell'operazione, ad esempio il tempo di attrezzaggio, il tempo di esecuzione, i requisiti risorse, le informazioni di determinazione costi e il calcolo del consumo, sono specificate nella relazione operativa. Per ulteriori informazioni sulle relazioni operative, vedere la sezione successiva.

## <a name="operation-relations"></a>Relazioni operative
Le seguenti proprietà operative di un'operazione vengono gestite nella relazione operativa:

-   Categorie costi
-   Parametri di consumo
-   Tempi di elaborazione
-   Quantità di elaborazione
-   Requisiti risorsa
-   Note e istruzioni

È possibile definire più relazioni operative per la stessa operazione. Tuttavia, ciascuna relazione operativa è specifica di un'operazione e vengono memorizzare le proprietà specifiche di un ciclo di lavorazione, un prodotto rilasciato, o un set di prodotti rilasciati correlati a un gruppo di articoli. Di conseguenza, la stessa operazione può essere utilizzata in più cicli di lavorazione con proprietà operative diverse. Inoltre, è possibile gestire più facilmente i dati master se si utilizzano operazioni standard con le stesse proprietà operative, indipendentemente dal ciclo di lavorazione utilizzato e dal prodotto da produrre. L'ambito della relazione operativa è definito tramite le proprietà **Codice articolo**, **Relazione articolo**, **Codice ciclo di lavorazione** e **Relazione ciclo di lavorazione** come illustrato nella seguente tabella.

| Codice articolo | Relazione articolo         | Codice ciclo di lavorazione | Relazione ciclo di lavorazione   | Ambito della relazione operativa                                                                                                                                                                                                                                                                              |
|-----------|-----------------------|------------|------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Tabella     | &lt;ID articolo&gt;       | Ciclo      | &lt;ID ciclo di lavorazione&gt; | Le proprietà operative di un'operazione quando utilizzata nel ciclo di lavorazione in cui **Numero ciclo di lavorazione**=&lt;ID ciclo di lavorazione&gt; per la produzione del prodotto rilasciato in cui **Numero articolo**=&lt;ID articolo&gt;.                                                                                                                        |
| Tabella     | &lt;ID articolo&gt;       | Tutti        |                  | Le proprietà operative predefinite di un'operazione quando utilizzata per la produzione del prodotto rilasciato in cui **Numero articolo**=&lt;ID articolo&gt;. Ovvero, le proprietà operative vengono applicate quando non esistono relazioni operative specifiche del ciclo di lavorazione per il prodotto rilasciato.                                     |
| Raggruppa     | &lt;ID gruppo di articoli&gt; | Ciclo      | &lt;ID ciclo di lavorazione&gt; | Le proprietà operative di un'operazione quando è utilizzata nel ciclo di lavorazione in cui **Numero ciclo di lavorazione**=&lt;ID ciclo di lavorazione&gt; per produrre i prodotti rilasciati associai all'ID gruppo di articoli del &lt;gruppo di articoli&gt; a meno che esista una relazione operativa specifica per il prodotto rilasciato.                         |
| Raggruppa     | &lt;ID gruppo di articoli&gt; | Tutti        |                  | Le proprietà operative predefinite di un'operazione quando utilizzata per la produzione dei prodotti rilasciati associati all'ID gruppo di articoli del &lt;gruppo di articoli&gt;, a meno che sia presente una relazione operativa più specifica.                                                                                                  |
| Tutti       |                       | Ciclo      | &lt;ID ciclo di lavorazione&gt; | Le proprietà operative predefinite dell'operazione quando è utilizzate nel ciclo di lavorazione in cui **Numero del ciclo di lavorazione**=&lt;ID del ciclo di lavorazione&gt;. Ovvero, le proprietà operative vengono applicate quando non esistono relazioni operative per questo ciclo di lavorazione né per il prodotto rilasciato né per il gruppo di articoli associato. |
| Tutti       |                       | Tutti        |                  | Le proprietà operative predefinite di un'operazione. Queste proprietà operative vengono applicate quando una relazione operativa più specifica non è disponibile.                                                                                                                                                                |

È inoltre possibile specificare che una relazione operativa è specifica di un sito. In questo modo, le proprietà operative di un'operazione possono variare, a seconda dell'ubicazione (ovvero il sito) in cui l'operazione viene eseguita. Per i prodotti configurati, è inoltre possibile specificare proprietà operative diverse per ciascuna configurazione prodotto.  

Le relazioni operative offrono molta flessibilità quando si definiscono i cicli di lavorazione. Inoltre, la capacità di definire delle proprietà predefinite riduce la quantità di dati master da gestire. Tuttavia, questa flessibilità significa anche che è necessario considerare il contesto di modifica di una relazione operativa.  

**Nota**: poiché le proprietà operative vengono archiviate in relazioni operative per operazione per ciclo di lavorazione, tutti le occorrenze della stessa operazione, ad esempio Assemblaggio, presentano lo stesso tempo di attrezzaggio, tempo di esecuzione, gli stessi requisiti risorsa e così via. Di conseguenza, se due occorrenze di un'operazione devono verificarsi nello stesso ciclo di lavorazione ma con tempi di esecuzione diversi, è necessario creare due operazioni distinte, ad esempio Assembly1 e Assembly2.

### <a name="modifying-product-specific-routes"></a>Modifica di cicli di lavorazione specifici di prodotto

Quando si apre la pagina **Ciclo di lavorazione** dalla pagina **Dettagli prodotto rilasciato**, vengono mostrate le versioni del ciclo di lavorazione associate al prodotto rilasciato selezionato. In questo contesto, per ciascuna operazione, Finance and Operations visualizza le proprietà operative per la relazione operativa con migliore corrispondenza rispetto alla versione del ciclo di lavorazione. Si può notare che l'elenco delle operazioni include le proprietà **Codice articolo** e **Codice ciclo di lavorazione** della relazione operativa. Di conseguenza, è possibile determinare quale relazione operativa viene visualizzata.  

Nella pagina **Ciclo di lavorazione**, è possibile modificare le proprietà operative dell'operazione, ad esempio il tempo di esecuzione o le categorie di costi. Le modifiche verranno salvate nella relazione operativa specifica del ciclo di lavorazione e del prodotto rilasciato a cui viene fatto riferimento nella versione del ciclo di lavorazione corrente. Se la relazione operativa mostrata non è specifica del ciclo di lavorazione e del prodotto rilasciato, prima che le modifiche siano archiviate, viene creata una copia della relazione operativa. Questa copia *è* specifica del ciclo di lavorazione e del prodotto rilasciato. Di conseguenza, le modifiche non influiranno su altri cicli di lavorazione o prodotti rilasciati. Per verificare quale relazione operativa viene modificata nella pagina **Ciclo di lavorazione**, esaminare i campi **Codice articolo** e **Codice ciclo di lavorazione**.  

È inoltre possibile creare manualmente un'operazione specifica di un ciclo di lavorazione e un prodotto rilasciato utilizzando la funzione **Copia e modifica relazione**.  

**Nota:** se si aggiungono nuove operazioni a un ciclo di lavorazione nella pagina **Ciclo di lavorazione**, viene creata una relazione operativa solo per il prodotto rilasciato corrente. Pertanto, se il ciclo di lavorazione viene utilizzato anche per produrre altri prodotti rilasciati, nessuna relazione operativa sarà presente applicabile per questi prodotti rilasciati e il ciclo di lavorazione non potrà più essere utilizzato per tali prodotti rilasciati.

### <a name="maintaining-operation-relations-per-route"></a>Gestire le relazioni operative per ciclo di lavorazione

Quando si apre la pagina **Dettagli ciclo di lavorazione** dalla pagina elenco **Cicli di lavorazione**, viene mostrato l'elenco di tutte le relazioni operative applicate al ciclo di lavorazione selezionato. Di conseguenza, è possibile verificare facilmente quali proprietà operative vengono utilizzate per quali prodotti. È possibile modificare sia i valori di una proprietà predefinita che i valori di una proprietà specifica di prodotto.  

Se si aggiunge una nuova relazione operativa nella pagina **Dettagli ciclo di lavorazione**, il campo **Codice ciclo di lavorazione** viene impostato automaticamente su **Ciclo di lavorazione** e il campo **Relazione ciclo di lavorazione** viene impostato sul numero del ciclo di lavorazione corrente.

### <a name="maintaining-operation-relations-per-operation"></a>Gestire le relazioni operative per operazione

Nella pagina **Operazioni** è possibile aprire la pagina **Relazioni operative**. In questa pagina, è possibile modificare tutte le relazioni operative per una specifica operazione. È inoltre possibile modificare le relazioni operative che contengono i valori predefiniti.  

Se le operazioni standard vengono utilizzate in azienda e se i parametri operativi sono uguali per tutti i prodotti e processi, la pagina **Relazioni operative** offre un metodo pratico gestire proprietà operative predefinite di tali operazioni.

### <a name="applying-operation-relations"></a>Applicare le relazioni operative

In alcuni casi, Finance and Operations deve trovare le proprietà operative per un'operazione. Ad esempio, quando viene creato un ordine fornitore, le proprietà operative di ciascuna operazione devono essere copiate dalle relazioni operative al ciclo di produzione. In queste situazioni, Finance and Operations cerca le relazioni operative rilevanti dalla combinazione più specifica alla combinazione meno specifica.  

Quando Finance and Operations cerca la relazione operativa più rilevante per un prodotto rilasciato, una relazione operativa che corrisponde all'ID articolo del prodotto rilasciato ha priorità rispetto a una relazione operativa che corrisponde all'ID del gruppo di articoli. A sua volta, una relazione operativa che corrisponde all'ID del gruppo di articoli ha priorità rispetto alla relazione operativa predefinita. L'ordine di ricerca è il seguente:

1.  **Codice articolo**=**Tabella** e **Relazione articolo**=&lt;ID articolo&gt;
2.  **Codice articolo**=**Gruppo** e **Relazione articolo**=&lt;ID gruppo di articoli&gt;
3.  **Codice articolo**=**Tutto**
4.  **Codice ciclo di lavorazione**=**Ciclo di lavorazione** e **Relazione ciclo di lavorazione**=&lt;ID ciclo di lavorazione&gt;
5.  **Codice ciclo di lavorazione**=**Tutto**
6.  **Configurazione**=&lt;ID configurazione&gt;
7.  **Configurazione**=
8.  **Sito**=&lt;ID sito&gt;
9.  **Sito**=

Di conseguenza, un'operazione essere utilizzata una sola volta per ogni ciclo di lavorazione. Se l'operazione viene eseguita più volte nello stesso ciclo di lavorazione, tutti le occorrenze di tale operazione avranno la stessa relazione operativa e non sarà possibile avere proprietà diverse, ad esempio il tempo di esecuzione, per ogni occorrenza.

## <a name="route-versions"></a>Versioni cicli di lavorazione
Le versioni del ciclo di lavorazione vengono utilizzate per adeguare il ciclo di lavorazione alle variazioni nella produzione dei prodotti o per migliorare il controllo del processo di produzione. Definiscono quale ciclo di lavorazione deve essere utilizzato quando si produce un prodotto rilasciato specifico o una variante prodotto rilasciata. È possibile utilizzare i seguenti vincoli per definire quale ciclo di lavorazione utilizzare per un prodotto rilasciato:

-   Le dimensioni prodotto (dimesnioni, colore, stile o configurazione)
-   Quantità di produzione
-   Sito di produzione
-   Data di produzione

Quando si produce il prodotto presso un sito specifico, con una quantità specifica o in un periodo specifico, è possibile indicare una versione specifica del ciclo di lavorazione come versione del ciclo di lavorazione predefinito. Tuttavia, si noti che solo un ciclo di lavorazione attivo è consentito per un prodotto rilasciato specifico e per un set specifico di vincoli.  

Nei parametri di controllo produzione, è possibile richiedere che il periodo di validità di una versione del ciclo di lavorazione sia sempre specificato.

### <a name="approval-of-route-versions"></a>Approvazione delle versioni del ciclo di lavorazione

Prima che una versione di un ciclo di lavorazione possa essere utilizzata nella pianificazione o nel processo di produzione, deve essere approvata. Quando si approva una versione del ciclo di lavorazione, è possibile approvare anche il ciclo di lavorazione correlato. Tuttavia, si noti che una versione di un ciclo di lavorazione può essere approvata solo se anche il ciclo di lavorazione correlata viene approvato.

### <a name="activating-the-default-route-version"></a>Attivazione della versione predefinita del ciclo di lavorazione

Se si attiva una versione del ciclo di lavorazione, si designa tale versione come versione predefinita del ciclo di lavorazione che la pianificazione generale utilizzerà o che verrà utilizzata per la creazione degli ordini di produzione. È possibile disporre solo di una versione attiva per un set specifico di vincoli, ad esempio periodo, sito o quantità. Se la versione che si sta tentando di attivare è in conflitto con una versione già attiva, viene visualizzato un messaggio di errore. È quindi necessario disattivare la versione in conflitto o modificare i vincoli della versione (in genere il periodo) nella versione del ciclo di lavorazione per impedire un'attivazione ambigua.

### <a name="electronic-signatures"></a>Firme elettroniche

Se è necessario tenere un registro per registrare chi approva e attiva ciascuna versione del ciclo di lavorazione è possibile richiedere firme elettroniche per queste attività. Gli utenti che approvano e attivano le versioni del ciclo di lavorazione dovranno quindi confermare la propria identità utilizzando una [firma elettronica](/dynamics365/unified-operations/fin-and-ops/organization-administration/electronic-signature-overview).

### <a name="product-change-that-uses-case-management"></a>Modifica dei prodotti con gestione dei casi

Il caso di modifica del prodotto per l'approvazione e l'attivazione di nuovi o modificati cicli di lavorazione e versioni di cicli di lavorazione fornisce un modo semplice di visualizzare una panoramica dei vincoli della versione del ciclo di lavorazione. È inoltre possibile approvare e attivare tutti i cicli di lavorazione correlati a una modifica specifica con un'unica operazione e documentare i risultati nel caso del prodotto.

## <a name="maintaining-routes"></a>Gestione dei cicli di lavorazione
In base ai requisiti aziendali, è possibile ridurre le risorse necessarie per gestire le definizioni di processo.

### <a name="making-routes-independent-of-resources"></a>Impostazione di cicli di lavorazione indipendenti dalle risorse

In molti sistemi, la risorsa operativa o il gruppo di risorse che devono eseguire un'operazione devono essere specificati nel ciclo di lavorazione. Tuttavia, in Finance and Operations è possibile definire un insieme di requisiti che una risorsa operativa deve soddisfare per essere applicabile all'operazione. Di conseguenza, il gruppo di risorse o la risorsa operativa specifici che devono essere utilizzati non devono essere determinati fino a che l'operazione viene effettivamente programmata. Questa funzionalità è particolarmente utile se si dispone di numerosi lavoratori o macchine che possono eseguire la stessa operazione.  

Ad esempio, si specifica che un'operazione richiede una risorsa operativa del tipo **Macchina** con capacità di **punzonatura** di 20 tonnellate. Il motore di programmazione risolverà quindi tali requisiti per una risorsa operativa o un gruppo di risorse specifico quando l'operazione verrà programmata. È possibile specificare solo tali requisiti anziché associare l'operazione a una macchina specifica e questo garantisce maggiore flessibilità. Inoltre, la gestione è più semplice quando le risorse vengono spostate o quando nuove risorse vengono aggiunte.  

Per ulteriori informazioni sui diversi tipi di requisiti risorsa e sul loro utilizzo, vedere Requisiti risorsa operativa e [Capacità risorsa](resource-capabilities.md).

### <a name="sharing-routes-across-sites"></a>Condivisione dei cicli di lavorazione tra siti

Se si produce lo stesso prodotto in più siti di produzione e se i passaggi per la produzione del prodotto sono uguali in tutti i siti, spesso è possibile progettare un ciclo di lavorazione condiviso utilizzato in tutti i siti di produzione. Per creare un ciclo di lavorazione condiviso, non specificare un sito nel ciclo di lavorazione stesso. Tuttavia, è necessario creare una versione del ciclo di lavorazione che associa il ciclo di lavorazione condiviso al prodotto in ciascun sito.  

È inoltre necessario assicurarsi che i requisiti risorsa per ciascuna operazione del ciclo di lavorazione non richiedano risorse operative specifiche o gruppi di risorse specifici, ma siano invece espressi in termini di capacità delle risorse necessarie. Il motore di programmazione sarà quindi in grado di assegnare le risorse operative appropriate dal sito in cui la produzione viene programmata. Ad esempio, se sono presenti piccole differenze nel tempo di esecuzione, o se il tempo di attrezzaggio per una determinata operazione è specifico del sito, è possibile specificare queste informazioni aggiungendo un'ulteriore relazione operativa per il sito.  

Per sfruttare completamente i vantaggi dei cicli di lavorazione condivisi, è necessario inoltre utilizzare il consumo delle risorse nella distinta base (BOM) corrispondente. Quando si imposta il flag del consumo delle risorse nella riga DBA, il magazzino e l'ubicazione presso la quale le materie prime devono essere utilizzate vengono dedotti dalla risorsa operativa per cui l'operazione verrà programmata. Di conseguenza, il magazzino e l'ubicazione non devono necessario determinati fino al momento in cui la produzione è effettivamente programmata. In questo modo, è possibile rendere indipendenti sia la DBA che il ciclo di lavorazione dell'ubicazione fisica in cui il prodotto viene prodotto.

### <a name="standard-operation-relations"></a>Relazioni operative standard

Se in azienda vengono utilizzate operazioni standardizzare nella produzione e se sono presenti variazioni minime o assenti nel tempo di attrezzaggio ed esecuzione, nel calcolo del consumo e dei costi e così via, potrebbe essere utile creare relazioni operative predefinite per tutte le operazioni. In questo caso, evitare di creare relazioni operative specifiche do cicli di lavorazione o prodotti rilasciati.  

Se inoltre i requisiti risorsa vengono espressi in termini di competenze e capacità e se i cicli di lavorazione vengono resi indipendente, è possibile limitare al minimo la gestione dei processi aziendali.  

Quando si utilizza questo metodo, la pagina **Relazioni operative** viene impostata come destinazione principale per la gestione dei tempi di esecuzione e di altre proprietà.

### <a name="resource-specific-process-times"></a>Tempi di processi specifici della risorsa

Se non si specifica una risorsa operativa o un gruppo di risorse come parte dei requisiti risorsa per un'operazione, le risorse applicabili possono funzionare secondo velocità diverse. Come risultato, il tempo necessario per elaborare l'operazione potrebbe variare. Per risolvere questo problema, è possibile utilizzare il campo **Formula** della relazione operativa per specificare come viene calcolato il tempo di elaborazione. Sono disponibili le seguenti opzioni:

-   **Standard** – (opzione predefinita) nel calcolo vengono utilizzati solo i campi della relazione operativa e viene moltiplicato il tempo di esecuzione specificato per la quantità dell'ordine.
-   **Capacità** – il calcolo include il campo **Capacità** della risorsa operativa. Di conseguenza, il tempo è dipendente dalla risorsa. Il valore specificato per la risorsa operativa è la capacità oraria. Questo valore viene moltiplicato per la quantità ordine e il valore **Fattore** della relazione operativa.
-   **Batch** – una capacità batch viene calcolata utilizzando le informazioni relative alla relazione operativa. Numero di batch e, di conseguenza, il tempo di elaborazione possono quindi essere calcolati in base alla quantità dell'ordine.
-   **Batch risorsa** – questa opzione è fondamentalmente uguale all'opzione **Batch**. Tuttavia, il calcolo include il campo **Capacità batch** della risorsa operativa. Di conseguenza, il tempo è dipendente dalla risorsa.


<a name="see-also"></a>Vedere anche
--------

[Distinte base e formule](bill-of-material-bom.md)

[Categorie di costi utilizzate nei cicli di lavorazione](../cost-management/cost-categories-used-production-routings.md)

[Capacità risorsa](resource-capabilities.md)

[Panoramica delle firme elettroniche](/dynamics365/unified-operations/fin-and-ops/organization-administration/electronic-signature-overview)




