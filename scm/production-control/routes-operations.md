---
title: Cicli di lavorazione e le operazioni
description: In questo argomento vengono fornite informazioni sui cicli di lavorazione e le operazioni. Un ciclo definisce il processo per la produzione di un prodotto o della variante prodotto. Viene descritto ogni fase (operazione) nel processo di produzione e nell&quot;ordine in cui queste operazioni devono essere eseguite in. Per ciascuna fase, il ciclo di lavorazione inoltre di definire le risorse operative richieste, il tempo di attrezzaggio obbligatorio e il tempo e come costo deve essere calcolata.
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: BOMDesigner, BOMDesignerRouteVersion, Route, RouteInventProd, RouteOpr, RouteOprTable
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 268124
ms.assetid: f78d5836-3e71-42b7-a5d1-41f19228d9d2
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: sorenand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: f707d45290682e79ee439ba0d504852429defa90
ms.openlocfilehash: 556b9859d0b162b11f0bcbfc6552f6fd9a900596
ms.lasthandoff: 03/31/2017


---

# <a name="routes-and-operations"></a>Cicli di lavorazione e le operazioni

In questo argomento vengono fornite informazioni sui cicli di lavorazione e le operazioni. Un ciclo definisce il processo per la produzione di un prodotto o della variante prodotto. Viene descritto ogni fase (operazione) nel processo di produzione e nell'ordine in cui queste operazioni devono essere eseguite in. Per ciascuna fase, il ciclo di lavorazione inoltre di definire le risorse operative richieste, il tempo di attrezzaggio obbligatorio e il tempo e come costo deve essere calcolata.

<a name="overview"></a>Panoramica
--------

Un ciclo viene descritto l'ordine delle operazioni necessario per la produzione di un prodotto o una variante prodotto. Per ciascuna operazione, il ciclo di lavorazione inoltre di definire le risorse operative richieste, il tempo necessario per impostare ed eseguire l'operazione e come costo deve essere calcolata. È possibile utilizzare lo stesso ciclo di lavorazione per produrre i più prodotti, oppure definire un ciclo di lavorazione univoco per ogni variante prodotto o prodotto. È inoltre possibile avere più cicli di lavorazione per lo stesso prodotto. In questo caso, il ciclo di lavorazione utilizzato varia, in base ai fattori quali la quantità che deve essere prodotta. La definizione di un ciclo di lavorazione in Microsoft Dynamics 365 per le operazioni è costituito da quattro diversi elementi che, insieme, viene descritto il processo di produzione:

-   ** Il ciclo di lavorazione ** un ciclo definisce la struttura del processo di produzione. Si definisce l'ordine delle operazioni.
-   ** L'operazione ** - un'operazione identifica il processo denominato in un ciclo di lavorazione, come ** Assemblaggio **. La stessa operazione può verificarsi in più cicli di lavorazione e può contenere numeri di operazione diversi.
-   ** La relazione operativa ** di una relazione operativa definisce le proprietà operative di un'operazione, ad esempio il tempo e al tempo di attrezzaggio, categorie di costi, parametri del consumo e requisiti risorsa. La relazione operativa consente di impostare le proprietà di un'operazione di variare, in base al ciclo di lavorazione che l'operazione viene utilizzata nei prodotti o in producendi.
-   ** La versione del ciclo di lavorazione - ** una versione del ciclo di lavorazione definisce il ciclo di lavorazione utilizzato per creare un prodotto o una variante prodotto. Le versioni cicli di lavorazione consentono ai cicli di lavorazione di essere riutilizzate nei prodotti o di essere modificate nel tempo. Vengono inoltre consentono ai cicli di lavorazione diversi di essere utilizzate per produrre lo stesso prodotto. In questo caso, il ciclo di lavorazione utilizzato dipende da fattori quali la posizione o la quantità che è possibile produrre.

## <a name="routes"></a>Cicli di lavorazione
Un ciclo viene descritto l'ordine delle operazioni utilizzato per creare un prodotto o una variante prodotto. Ciascuna operazione viene assegnato un numero di operazione e un'operazione di successiva. L'ordine delle operazioni forma una rete di cicli di lavorazione che può essere rappresentata da un grafico diretta con uno o più punti di origine e un unico punto finale. In Dynamics 365 per le operazioni, i cicli di lavorazione vengono specifico in base al tipo di struttura. I due tipi di cicli di lavorazione sono cicli di lavorazione e le semplici reti di cicli di lavorazione. Nei parametri di Controllo produzione, è possibile specificare se visualizzare solo i cicli di lavorazione semplici possono essere utilizzati, o se le reti complesse più cicli di lavorazione possono essere utilizzate.

### <a name="simple-routes"></a>Cicli di lavorazione semplici

Un ciclo di lavorazione sequenziale è semplice ed è disponibile un solo punto di partenza per il ciclo di lavorazione.  

[lavorazione semplice![(]. /media/routes-and-operations-1-simple-route.png)](. /media/routes-and-operations-1-simple-route.png)  

Se si attiva solo ai cicli di lavorazione semplici nei parametri di Controllo produzione, Dynamics 365 per le operazioni viene generato automaticamente i numeri delle operazioni (10, 20, 30 e così via, quando si definisce il ciclo di lavorazione.

### <a name="route-networks"></a>Reti del ciclo di lavorazione

Se si consente a più reti complesse del ciclo di lavorazione nei parametri di Controllo produzione, è possibile definire i cicli di lavorazione con i punti di origine e più operazioni che possono essere eseguiti in parallelo.  

[![Route network](./media/routes-and-operations-2-route-network.png)](./media/routes-and-operations-2-route-network.png)  

**Note:**

-   Ciascuna operazione può essere presente una sola operazione successiva del ciclo di lavorazione e di tutti deve terminare con una sola operazione.
-   Non esiste alcuna garanzia che più operazioni con la stessa operazione di attività successiva, ad esempio operazioni 30 e 40 nella precedente figura) effettivamente verranno eseguite in parallelo. La disponibilità e la capacità delle risorse possono inserire i vincoli in modo che le operazioni programmate.
-   Non è possibile utilizzare 0 (zero) come numero di operazione. Le il numero è prenotato e viene utilizzato per specificare che l'ultima operazione del ciclo di lavorazione non dispone di operazione successiva.

### <a name="parallel-operations"></a>Le operazioni parallele

Talvolta, una combinazione di più risorse operative che hanno caratteristiche di progetti è necessaria per eseguire un'operazione. Ad esempio, per un'operazione di assemblaggio potrebbe richiedere a una macchina, a uno strumento e a un lavoratore per ogni due computer sorvegli l'operazione. In questo esempio può essere modellizzato utilizzando le operazioni parallele, in cui un'operazione è indicata come l'operazione primaria e le altre vengono secondarie.  

[lavorazione![che ha operazioni primarie e secondarie (]. /media/routes-and-operations-3-parallel-operations.png)](. /media/routes-and-operations-3-parallel-operations.png)  

In genere, l'operazione primaria per la risorsa collo di bottiglia e detta di esecuzione per le operazioni secondarie. Tuttavia, durante la programmazione che include la capacità limitata, le risorse che sono programmati per l'operazione principale dalle operazioni secondarie deve essere disponibile e potranno essere capacità contemporaneamente.  

Sia l'operazione principale dalle operazioni secondarie devono avere la stessa operazione numero (30 nella precedente figura).  

Nell'esempio precedente, i requisiti risorsa per l'operazione primaria (30) è il computer, mentre i requisiti risorsa per le operazioni secondarie (30 a 30 e ") vengono strumento e il lavoratore. Consente di un carico di cinquanta- PERCENT garantire che il lavoratore è programmato L'obiettivo due computer contemporaneamente.

### <a name="approval-of-routes"></a>Approvazione cicli di lavorazione

Un ciclo di lavorazione deve prima essere approvato che può essere utilizzata in Pianificazione o durante il processo di produzione. L'approvazione indica che la progettazione del ciclo di lavorazione è stata completata. Lo stesso prodotto rilasciato o varianti prodotto rilasciato può avere più cicli di lavorazione approvati. In genere, l'approvazione da un ciclo di lavorazione avviene la prima la versione del ciclo di lavorazione è approvata. Tuttavia, in alcuni scenari aziendali, l'approvazione del ciclo di lavorazione e del ciclo di lavorazione sono attività separate che possono essere coinvolti i proprietari di diversi.  

Ogni ciclo di lavorazione può essere approvato o non separatamente. Tuttavia, noti che, quando un ciclo di lavorazione viene annullata l'approvazione, tutte le versioni correlate del ciclo di lavorazione vengono inoltre non approvate. Nei parametri di Controllo produzione, è possibile specificare se i cicli di lavorazione possono essere non approvate e se i cicli di lavorazione approvati possono essere modificati.  

Se è necessario tenere un registro di record che approva ciascun ciclo di lavorazione, è possibile richiedere firme elettroniche per l'approvazione di un ciclo di lavorazione. Gli utenti dovranno quindi confermare la propria identità utilizzando firma elettronica [] (/dynamics365/operations/organization-administration/electronic-signature-overview).

## <a name="operations"></a>Operazioni
Un'operazione è un passaggio del processo di produzione. In Dynamics 365 per le operazioni, ciascuna operazione ha un ID e una descrizione semplice. Nelle tabelle seguenti sono indicati gli esempi comuni delle operazioni di officina meccanico.

| Operazione  | descrizione        |
|------------|--------------------|
| PipeCut    | Taglia di tubo       |
| TIGweld    | Saldatura di TIG        |
| JigAssy    | Assembly maschera       |
| Ispezione | Controllo di qualità |

Le proprietà operative per l'operazione, ad esempio il tempo di impostazione ed esecuzione, requisiti risorsa, informazioni di determinazione costi e al calcolo del consumo, vengono specificate alla relazione operativa. Per ulteriori informazioni sulle relazioni operative, vedere la sezione successiva.)

## <a name="operation-relations"></a>Relazioni operative
Le seguenti proprietà operative di un'operazione vengono gestite nella relazione operativa:

-   Categorie costi
-   Parametri di consumo
-   Tempi di lavorazione
-   Elaborazione delle quantità
-   Requisiti risorsa
-   Note e istruzioni

È possibile definire le relazioni operative più per la stessa operazione. Tuttavia, ciascuna relazione operativa è specifica a un'operazione e vengono archiviate le proprietà specifiche di un ciclo di lavorazione, un prodotto rilasciato, o in un set di prodotti rilasciati correlati a un gruppo di articoli. Di conseguenza, la stessa operazione può essere utilizzata in più cicli di lavorazione con proprietà operative diversi. Inoltre, è possibile gestire più facilmente i dati master se si utilizzano operazioni standard con le stesse proprietà operative, indipendentemente dall'lavorazione utilizzato e prodotto da produrre. L'ambito della relazione operativa è definito in ** codice articolo, ** ** relazione articolo, ** ** il ciclo di lavorazione ** e ** relazione ciclo di lavorazione ** le proprietà, come illustrato nella seguente tabella.

| Codice articolo | Relazione articolo         | Codice ciclo di lavorazione | Relazione ciclo di lavorazione   | Ambito della relazione operativa                                                                                                                                                                                                                                                                              |
|-----------|-----------------------|------------|------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Tabella     | &lt;ID articolo&gt;       | Ciclo      | &lt;ID ciclo di lavorazione&gt; | Le proprietà operative di un'operazione quando è utilizzato l'ID del ciclo di lavorazione=lavorazione in cui ** numero&lt;del ciclo di lavorazione **&gt; la produzione del prodotto rilasciato in cui ** numero di articolo ** ID&lt;articolo.=&gt;                                                                                                                        |
| Tabella     | &lt;ID articolo&gt;       | Tutti        |                  | Le proprietà operative predefinito di un'operazione quando utilizzato per la produzione del prodotto rilasciato in cui ** numero di articolo ** ID&lt;articolo.=&gt; Ovvero le proprietà operative vengono applicati quando non esistono relazioni operative relative specifica per il prodotto rilasciato.                                     |
| Raggruppa     | &lt;Identificazione del gruppo di articoli&gt; | Ciclo      | &lt;ID ciclo di lavorazione&gt; | Le proprietà operative di un'operazione quando è utilizzato nel ciclo di lavorazione in cui ** numero del ciclo di lavorazione ** l'ID&lt;del ciclo=&gt; la produzione rilasciati i prodotti associati all'ID gruppo di articoli &lt;gruppo di articoli, a meno che esista una relazione operativa a specifica per il prodotto rilasciato.                         |
| Raggruppa     | &lt;Identificazione del gruppo di articoli&gt; | Tutti        |                  | Le proprietà operative predefinito di un'operazione quando utilizzato per la produzione dei prodotti rilasciati associati all'ID gruppo di articoli &lt;gruppo di articoli, a meno che una relazione operativa presente più specifica.                                                                                                  |
| Tutti       |                       | Ciclo      | &lt;ID ciclo di lavorazione&gt; | Le proprietà operative predefinito dell'operazione quando è utilizzato nel ciclo di lavorazione in cui ** numero del ciclo di lavorazione ** identificazione&lt;del ciclo di lavorazione=&gt;. Ovvero le proprietà operative vengono applicati quando non esistono relazioni operative per il ciclo di lavorazione specifico al prodotto rilasciato o al gruppo di articoli. |
| Tutti       |                       | Tutti        |                  | Le proprietà operative predefinito di un'operazione. Queste proprietà operative vengono applicati quando una relazione operativa più specifica non è disponibile.                                                                                                                                                                |

È inoltre possibile specificare che una relazione operativa è specifica a un sito. In questo modo, le proprietà operative di un'operazione possono variare, a seconda della posizione ovvero il sito) in cui l'operazione viene eseguita. Per i prodotti configurati, è inoltre possibile specificare le proprietà operative diversi per ciascuna configurazione prodotto.  

Le relazioni operative consentono i lotti di flessibilità quando si definiscono i cicli di lavorazione. Inoltre, la capacità di definire le aree delle proprietà predefinita riduce la quantità di dati master che dovranno poi. Tuttavia, questa flessibilità significa anche per i quali è necessario considerare il contesto di modifica di una relazione operativa in.  

** Nota: ** Poiché le proprietà relazioni operative vengono archiviate in esecuzione per l'operazione del ciclo di lavorazione, tutti gli eventi la stessa operazione, ad esempio Assemblaggio) presentano lo stesso tempo di attrezzaggio, il tempo di esecuzione, requisiti risorsa, e così via. Di conseguenza, se due eventi di un'operazione devono verificarsi nello stesso ciclo di lavorazione ma non avere diversi, è necessario creare due operazioni distinte, ad esempio Assembly1 e Assembly2.

### <a name="modifying-product-specific-routes"></a>Cicli di lavorazione per un prodotto specifico di modifica

Quando si apre ** lavorazione ** la pagina ** modulo Dettagli prodotto rilasciato dalla pagina **, le versioni del ciclo di lavorazione associate al prodotto rilasciato selezionato. In questo contesto, per ciascuna operazione, Dynamics 365 per le operazioni vengono visualizzate le proprietà operative la relazione operativa alle corrispondenze per la versione del ciclo di lavorazione. Noterete che l'elenco delle operazioni include ** codice articolo e ** ** il ciclo di lavorazione ** le proprietà della relazione operativa. Di conseguenza, è possibile determinare la relazione operativa viene visualizzata.  

** Ciclo ** nella pagina, è possibile modificare le proprietà dell'operazione operative, ad esempio il tempo di esecuzione o categorie di costi. Le modifiche verranno salvate in relazione operativa specifiche al ciclo di lavorazione e al prodotto rilasciato a cui viene fatto riferimento nella versione del ciclo di lavorazione corrente. Se la relazione operativa indicato non è specifico al ciclo di lavorazione e al prodotto rilasciato, prima delle modifiche desiderate siano archiviate, viene creata una copia della relazione operativa. Questo *is* di copia specifico al ciclo di lavorazione e al prodotto rilasciato. Di conseguenza, le modifiche non influiranno sui cicli di lavorazione o altri prodotti rilasciati. Per verificare la relazione operativa viene modificanda ** lavorazione ** nella pagina, esaminare ** codice articolo e ** ** il ciclo di lavorazione ** campi.  

È inoltre possibile creare manualmente un'operazione specifiche di un ciclo di lavorazione e a un prodotto rilasciato utilizzando ** copia e relazione di modifica ** la funzione.  

** Nota: ** Se si aggiungono nuove operazioni a un ciclo di lavorazione ** ** nella pagina, una relazione operativa viene creata solo per il prodotto rilasciato corrente. Pertanto, se il ciclo di lavorazione viene utilizzato anche per produrre altri prodotti rilasciati, alcuna relazione operativa presente applicabile per i prodotti rilasciati il ciclo di lavorazione e non potrà più essere utilizzato per i prodotti rilasciati.

### <a name="maintaining-operation-relations-per-route"></a>Relazioni operative per la gestione di lavorazione

Quando si apre ** il ciclo di lavorazione Dettagli ** la pagina ** cicli di lavorazione ** dalla pagina elenco, l'elenco di tutte le relazioni operative applicate al ciclo di lavorazione selezionato è indicato. Di conseguenza, è possibile verificare facilmente le proprietà operative vengono utilizzate per cui prodotti. È possibile modificare sia i valori di una proprietà predefinita che i valori di una proprietà per un prodotto specifico.  

Se si aggiunge una nuova relazione operativa ** il ciclo di lavorazione ** dettagli della pagina, ** il ciclo di lavorazione ** il campo viene impostato automaticamente su ** ** lavorazione e ** relazione ciclo di lavorazione ** il campo è impostato sul numero del ciclo di lavorazione corrente.

### <a name="maintaining-operation-relations-per-operation"></a>Relazioni operative per la gestione delle operazioni

** Operazioni ** dalla pagina, è possibile aprire ** relazioni operative ** la pagina. In questa pagina, è possibile modificare tutte le relazioni operative per una specifica operazione. È inoltre possibile modificare le relazioni operative che contengono i valori predefiniti.  

Se le operazioni standard vengono utilizzate professionali e se i parametri operativi sono uguali in tutti i prodotti e processi, ** relazioni operative ** la pagina offre un metodo pratico gestire proprietà operative standard delle operazioni.

### <a name="applying-operation-relations"></a>Applicazione delle relazioni operative

In alcuni casi, Dynamics 365 per le operazioni devono trovare le proprietà operative per un'operazione. Ad esempio, quando viene creato un ordine fornitore, le proprietà operative di ciascuna operazione da copiare in base alle relazioni operative nel ciclo di produzione. In queste situazioni, Dynamics 365 per le operazioni la ricerca di relazioni operative rilevanti dalla combinazione più specifica la combinazione meno specifica.  

Quando Dynamics 365 per le operazioni viene ricercata la relazione operativa più appropriato per un prodotto rilasciato, una relazione operativa che corrisponde all'ID di articolo del prodotto rilasciato questa opzione su una relazione operativa che corrisponde all'ID del gruppo di articoli. La sua volta, una relazione operativa che corrisponde all'ID del gruppo di articoli è consigliabile alla relazione operativa predefinito. La ricerca viene eseguita nel seguente ordine:

1.  ** Codice articolo **=** Tabella ** e ** relazione articolo ** ID&lt;articolo=&gt;
2.  ** Codice articolo **=** gruppo ** e ** relazione articolo ** ID&lt;gruppo di articoli=&gt;
3.  ** Codice articolo **=** tutti **
4.  ** Codice di lavorazione **=** ** lavorazione e ** relazione ciclo di lavorazione ** identificazione&lt;del ciclo di lavorazione=&gt;
5.  ** Codice di lavorazione **=** tutti **
6.  ** Configurazione ** identificazione&lt;della configurazione=&gt;
7.  **Configuration**=
8.  ** Sito ** ID sito&lt;di=&gt;
9.  **Site**=

Di conseguenza, un'operazione è necessario utilizzare una sola volta per ogni ciclo di lavorazione. Se l'operazione viene eseguita più volte lo stesso ciclo di lavorazione, tutti gli eventi di tale operazione avranno lo stesso relazione operativa e non sarà possibile avere proprietà diverse, ad esempio tempo di esecuzione) per ogni occorrenza.

## <a name="route-versions"></a>Versioni cicli di lavorazione
Le versioni cicli di lavorazione vengono utilizzate per le variazioni nella produzione dei prodotti o per aumentare il controllo del processo di produzione. Definiscono il ciclo di lavorazione deve essere utilizzato per un prodotto rilasciato specifico o una variante prodotto rilasciato produrre. È possibile utilizzare i seguenti vincoli per definire il ciclo di lavorazione viene utilizzato per un prodotto rilasciato:

-   Dimensioni prodotto (dimensione, colore, Stile configurazione, o)
-   Quantità di produzione
-   Sito di produzione
-   Data di produzione

Quando si producendo il prodotto presso un sito specifico, una quantità specifica, o in un periodo specifico, è possibile indicare una versione specifica del ciclo di lavorazione nella versione del ciclo di lavorazione predefinito. Tuttavia, noti che solo un ciclo di lavorazione attivo è consentito un prodotto rilasciato specifico e un set specifico dei vincoli.  

Nei parametri di Controllo produzione, è possibile richiedere che il periodo di validità della versione del ciclo di lavorazione sia sempre specificato.

### <a name="approval-of-route-versions"></a>Approvazione delle versioni cicli di lavorazione

Prima di una versione del ciclo di lavorazione possa essere utilizzata in Pianificazione o durante il processo di produzione, deve essere approvata. Quando si approva una versione del ciclo di lavorazione, è inoltre possibile approvare il ciclo di lavorazione correlato. Tuttavia, noti che una versione del ciclo di lavorazione può essere approvata solo se il ciclo di lavorazione correlato viene approvato.

### <a name="activating-the-default-route-version"></a>Attivazione della versione del ciclo di lavorazione predefinito

Se si attiva una versione del ciclo di lavorazione, la designate come la versione del ciclo di lavorazione predefinito che la pianificazione generale utilizzerà, o che verrà utilizzata per la creazione degli ordini di produzione. È possibile utilizzare solo una versione attiva per un set specifico dei vincoli, ad esempio periodo, il sito, o quantità). Se la versione che si sta tentando di attivare i conflitti con una versione già attiva, si riceverà un messaggio di errore. Per evitare di attivazione ambigua, è necessario quindi disattivare la versione separati o modificare i vincoli (in genere il periodo) nella versione del ciclo di lavorazione.

### <a name="electronic-signatures"></a>Firme elettroniche

Se è necessario tenere un registro di record che approva attiva e ogni versione del ciclo di lavorazione, è possibile richiedere firme elettroniche per queste attività. Gli utenti che approvano e attivare le versioni del ciclo di lavorazione quindi dovranno confermare la propria identità utilizzando firma elettronica [] (/dynamics365/operations/organization-administration/electronic-signature-overview).

### <a name="product-change-that-uses-case-management"></a>Modifica di un prodotto che utilizza la gestione dei casi

In caso di modifica del prodotto per l'approvazione e l'attivazione dei nuovi cicli di lavorazione o variabili e delle versioni cicli di lavorazione fornisce un metodo semplice per visualizzare una panoramica dei vincoli di versione del ciclo di lavorazione. È inoltre possibile approvare e attivare tutti i cicli di lavorazione correlate a una modifica specifica in un'unica operazione e documentare i risultati nel caso del prodotto.

## <a name="maintaining-routes"></a>Cicli di lavorazione gestione
In base ai requisiti aziendali, è possibile ridurre la risorsa necessario per gestire le definizioni di processo.

### <a name="making-routes-independent-of-resources"></a>Impostazione dei cicli di lavorazione indipendenti dalle risorse

In molti sistemi, la risorsa operativa o il gruppo di risorse che devono eseguire un'operazione deve essere specificato nel ciclo di lavorazione. Tuttavia, in Dynamics 365 per le operazioni, è possibile definire un insieme di richieste da una risorsa operativa deve soddisfare per essere applicabile per l'operazione. Di conseguenza, il gruppo di risorse o la risorsa operativa specifica che deve essere utilizzato non deve essere risoluti fino a programmare l'operazione effettivamente. Questa funzionalità è particolarmente utile se si dispone di numerosi lavoratori o computer che possono eseguire la stessa operazione.  

Ad esempio, si specifica che un'operazione richiede una risorsa operativa ** del computer in ** che ha a ** timbrando ** la capacità di 20 tonnellate. Il motore di programmazione quindi risolverà tali requisiti a una risorsa operativa o a un gruppo di risorse specifica quando l'operazione verrà programmata. Poiché è possibile specificare solo tali requisiti anziché legare l'operazione a un computer specifico, è molto più flessibile. Inoltre, la manutenzione è più semplice quando le risorse viene modificato o nuove risorse vengono aggiunti.  

Per ulteriori informazioni sui diversi tipi di requisiti risorsa e come tal caso, vedere Requisiti di risorse operative e [] capacità delle risorse (resource-capabilities.md).

### <a name="sharing-routes-across-sites"></a>Divisione dei cicli di lavorazione che avvenga tra siti

Se lo stesso prodotto prodotto in più siti di produzione e se i passaggi per la produzione del prodotto sono uguali a tutti i siti, è possibile progettare un ciclo di lavorazione spesso comune utilizzato in tutti i siti di produzione. Per creare un ciclo di lavorazione comune, non specificare un sito in l ciclo di lavorazione. Tuttavia, non è necessario creare una versione del ciclo di lavorazione che associa il ciclo di lavorazione comune al prodotto in ciascun sito.  

È inoltre necessario assicurarsi che i requisiti risorsa per ciascuna operazione nel ciclo di lavorazione non di richiedere le risorse operative specifiche o gruppi di risorse, tuttavia è invece espressi in termini di capacità delle risorse necessarie. Il motore di programmazione sarà quindi assegnare le risorse operative appropriate dal sito che la produzione viene programmata sopra. Ad esempio, se si creano piccole differenze tempo di esecuzione, o se il tempo di attrezzaggio per una determinata operazione è specifico del sito, è possibile specificare queste informazioni aggiungendo una relazione operativa aggiuntivo per il sito.  

Per sfruttare completamente dai benefit dei cicli di lavorazione comuni, è necessario inoltre possibile utilizzare il consumo delle risorse nella distinta base (BOM) corrispondente. Quando si imposta il flag del consumo delle risorse nella riga DBA, il magazzino e la posizione alle materie prime devono essere utilizzate da è arguito dalla risorsa operativa che l'operazione verrà programmata sopra. Di conseguenza, il magazzino e l'ubicazione non è necessario determinare fino a programmare la produzione effettiva. In questo modo, è possibile effettuare sia la DBA in cui indipendente di lavorazione dell'ubicazione fisica in cui il prodotto viene prodotto.

### <a name="standard-operation-relations"></a>Relazioni operative standard

Se gli standardizzassero professionali utilizzare le operazioni in qualsiasi produzione e se è presente poca o non sono consentite variazioni nel tempo di attrezzaggio, il tempo, il calcolo del consumo, i costi, e così via, potrebbe essere utile per creare relazioni operative predefinito per tutte le operazioni. In questo caso, di creare relazioni operative specifiche a qualsiasi ciclo di lavorazione o prodotto rilasciato.  

Se inoltre esprimete i requisiti risorsa in termini di competenze e capacità e si i cicli di lavorazione e indipendente, è possibile limitare al minimo il corso la gestione dei processi aziendali.  

Quando si utilizza questo metodo, ** relazioni operative ** la pagina viene impostata come destinazione la principale per il runtime della gestione e altre proprietà.

### <a name="resource-specific-process-times"></a>periodi specifici trattati Risorsa-

Se non si specifica una risorsa operativa o un gruppo di risorse insieme ai requisiti risorsa per un'operazione, le risorse applicabili possono eseguire le diverse velocità. Come risultato, il tempo necessario per elaborare l'operazione potrebbe variare. Per risolvere questo problema, è possibile utilizzare ** formula ** liquidate alla relazione operativa per specificare come tempo di processo viene calcolato. Sono disponibili le seguenti opzioni:

-   ** Il valore predefinito ** - (opzione predefinita) nel calcolo vengono utilizzate solo i campi della relazione operativa e l'importo il tempo di esecuzione specificato per la quantità dell'ordine.
-   ** La capacità ** - Il calcolo include ** capacità ** sistema dalla risorsa operativa. Di conseguenza, l'ora viene disponibilità dipendente. Il valore specificato per la risorsa operativa è capacità oraria. Questo valore viene moltiplicato per la quantità ordine e ** fattore ** il valore della relazione operativa.
-   ** Il processo batch - ** una capacità batch viene calcolato utilizzando le informazioni relative alla relazione operativa. Numero di lotto e, di conseguenza, il tempo di esecuzione possono quindi essere calcolati in base alla quantità dell'ordine.
-   ** Il processo batch delle risorse ** questa opzione è fondamentalmente lo stesso batch ** ** dell'opzione. Tuttavia, il calcolo include ** capacità batch ** sistema dalla risorsa operativa. Di conseguenza, l'ora viene disponibilità dipendente.


<a name="see-also"></a>Vedere anche
--------

[Bills of materials and formulas](bill-of-material-bom.md)

[Cost categories used in production routing](../cost-management/cost-categories-used-production-routings.md)

[Resource capabilities](resource-capabilities.md)

[Electronic signature overview](/dynamics365/operations/organization-administration/electronic-signature-overview)


