---
title: Novità o modifiche introdotte in Dynamics AX 7.0 (febbraio 2016)
description: Questo articolo descrive le funzionalità nuove o modificate in Microsoft Dynamics AX 7.0. Questa versione contiene funzionalità di piattaforma e di applicazione ed è stata rilasciata nel febbraio 2016.
author: sericks007
manager: AnnBe
ms.date: 10/23/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ROBOTS: NOINDEX, NOFOLLOW
audience: Application User, Developer, IT Pro
ms.reviewer: josaw
ms.search.scope: Operations
ms.custom: 91243
ms.assetid: 515bc6e7-a85d-4995-95c6-6cab6c8aa0f9
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e39328c73fe3dd101e32ec04d895483335184ae7
ms.sourcegitcommit: 4d6ec2b1a9674712e1efb8c46b919d554f21a2b3
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2019
ms.locfileid: "2627653"
---
# <a name="whats-new-or-changed-in-dynamics-ax-70-february-2016"></a>Novità o modifiche introdotte in Dynamics AX 7.0 (febbraio 2016)

[!include [banner](../includes/banner.md)]

Questo articolo descrive le funzionalità nuove o modificate in Microsoft Dynamics AX 7.0. Questa versione contiene funzionalità di piattaforma e di applicazione ed è stata rilasciata nel febbraio 2016.

## <a name="cost-management"></a>Gestione costi

<table>
<thead>
<tr>
<th>Operazioni che è possibile effettuare</th>
<th>Dynamics AX 2012</th>
<th>Dynamics AX 7.0</th>
<th>Perché questo è importante?</th>
</tr>
</thead>
<tbody>
<tr>
<td>Ottieni una breve panoramica del saldo del magazzini, del saldo del magazzino WIP e quali sono state le entrate e le uscite di magazzino nell'anno fiscale selezionato.</td>
<td>Non applicabile</td>
<td>L'area di lavoro <strong>Amministrazione costi</strong> contiene una sezione in cui viene presentato il rendiconto di magazzino o magazzino WIP per il periodo fiscale selezionato. Il rendiconto si basa su un cache del set di dati che, per impostazione predefinita, viene aggiornata ogni 24 ore. La cache di set di dati può essere configurata in modo che gli utenti possono aggiornarla manualmente per report in tempo reale. La <strong>scheda Stato aggiornamento dati</strong> nell'area di lavoro <strong>Amministrazione costi</strong> mostra la data dell'ultimo aggiornamento della cache.</td>
<td>I controllori dei costi sono interessati a sapere se il saldo del rendiconto di magazzino o magazzino WIP aumenta o diminuisce nel tempo. Classificando gli eventi operativi nel rendiconto, il supervisore costi può ottenere una panoramica del flusso dell'inventario. Se il magazzino o il magazzino WIP è valutato per costi standard, lo scostamento globale registrato può inoltre essere considerato.</td>
</tr>
<tr>
<td>Utilizzare il modulo<strong> Gestione costi</strong>.</td>
<td>Non applicabile</td>
<td>La gestione dei costi è introdotta come area di dominio. La configurazione e il principio collegati ai costi sono stati sparsi attraverso gestione articoli, controllo produzione e contabilità fornitori.</td>
<td>Poiché tutte le attività correlate alla gestione dei costi centralizzate in un modulo, sarà più semplice per i controller di costo gestire il sistema.</td>
</tr>
<tr>
<td>I tipi di registrazione correlati a contabilità scorte e conto di produzione sono stati aggiornati.</td>
<td>Le etichette nei moduli <strong>InventPosting</strong>, <strong>Risorsa</strong>, <strong>ResourceGroup</strong> e <strong>ProductionGroup</strong> non sono sempre allineate con le etichette <strong>LedgerPostingType</strong> effettivamente utilizzate. Non è semplice comprendere la terminologia utilizzata nelle etichette.</td>
<td>Le etichette sono state aggiornate in modo che le etichette nelle pagine <strong>InventPosting</strong>, <strong>Risorsa</strong>, <strong>ResourceGroup</strong> e <strong>ProductionGroup</strong> corrispondano sempre alle etichette <strong>LedgerPostingType</strong> effettive. Tutte le etichette sono state rinominate in modo che le etichette corrispondano agli eventi operativi. Si noti che l'effettiva logica di registrazione non è stata modificata.</td>
<td>È più semplice configurare il sistema, poiché le nuove etichette sono correlate a eventi operativi che utilizzano questo tipo di registrazione.</td>
</tr>
<tr>
<td>Importazione/esportazione di prezzo di acquisto, costo, o prezzo di vendita da Microsoft Excel in o da una versione di determinazione costi.</td>
<td>Non è possibile importare correttamente i prezzi o i costi in una versione di determinazione costi, poiché il modello dati richiede un ID InventDim.</td>
<td>L'introduzione delle entità di dati consente di implementare una funzionalità di esportazione/importazione. Questa funzionalità consente agli utenti di importare/esportare prezzi o costi in una versione di determinazione costi.
<ul>
<li>Importare l'elenco completo dei prezzi di acquisto dell'anno successivo che viene ottenuto dal reparto acquisti.</li>
<li>Spingere i costi e i prezzi di vendita standard delle sedi in una o più società di vendita in un'operazione.</li>
</ul></td>
<td>Può far risparmiare ai controller dei costi una quantità significativa di tempo per la gestione del sistema, in particolare quando devono gestire i costi predeterminati per l'anno fiscale successivo.</td>
</tr>
<tr>
<td>Ottieni una breve panoramica del saldo delle scorte e del costo unitario e medio di un oggetto di costo.</td>
<td>L'utente deve aprire il modulo e selezionare le dimensioni inventariali che riflettono l'oggetto di costo. Di conseguenza, l'utente deve conoscere le dimensioni inventariali che sono state contrassegnate per l'inventario finanziario per il prodotto specifico.</td>
<td>Viene introdotta una nuova pagina <strong>Oggetto di costo</strong>. Per impostazione predefinita, in questa pagina vengono visualizzati tutti gli oggetti di costo relativi al prodotto. La pagina mostra il costo unitario medio corrente di quantità di scorte, di valore e per l'oggetto di costo.</td>
<td>Rimuove alcune complessità e rende più semplice essere un controllore di costo.</td>
</tr>
<tr>
<td>Utilizzare la nuova pagina <strong>Voci di costo</strong> durante il controllo del magazzino.</td>
<td>Può essere complicato eseguire il controllo del magazzino nelle operazioni di magazzino registrate e le liquidazioni correlate, poiché le stesse transazioni possono essere fisiche e finanziarie.</td>
<td>La pagina <strong>Voci di costo</strong> offre una nuova modalità per visualizzare le operazioni di magazzino.
<ul>
<li>Le transazioni sono visualizzate in ordine cronologico</li>
<li>Solo le transazioni che contribuiscono ai costi vengono importate.</li>
<li>Non vi è nozione dei costi fisici o di costo finanziario.</li>
<li>Non vi è nozione della quantità fisica o finanziaria.</li>
<li>I costi vengono aggiunti incrementalmente.</li>
</ul></td>
<td>Può far risparmiare ai controller di costo molto tempo in cui devono eseguire il controllo del magazzino a livello di transazione.</td>
</tr>
<tr>
<td>Usare la nuova finestra di dialogo <strong>Rendiconto WIP produzione</strong> per vedere una visualizzazione riepilogativa dei costi accumulati per un prodotto specifico.</td>
<td>Non applicabile</td>
<td>Nel rendiconto WIP viene visualizzato un saldo riepilogativo WIP dell'ordine di produzione specifico, raggruppato nelle classificazioni dei costi appropriate. Un grafico mostra, in ordine cronologico, come le registrazioni operative hanno interessato il saldo WIP.</td>
<td>Può far risparmiare ai controller di costo una quantità significativa di tempo quando è necessario conoscere quale saldo WIP corrente è in un ordine di produzione specifico, o quanto materiale è stato utilizzato nell'ordine.</td>
</tr>
<tr>
<td>Utilizzare la funzionalità di visualizzazione di confronto dei costi che è stata introdotta negli ordini di produzione. La funzionalità rende più semplice confrontare i costi correlati a un ordine di produzione.</td>
<td>L'utente può confrontare solo i costi e i costi realizzati. Il confronto può essere effettuato al livello inferiore.</td>
<td>La funzionalità di confronto dei costi consente ai controller di costo di confrontare i seguenti dati:
<ul>
<li>Costo attivo rispetto a costo stimato = scostamento pianificato</li>
<li>Costo stimato rispetto a costo realizzato = scostamento di produzione</li>
<li>Scostamento di pianificazione + scostamento di produzione = scostamento totale</li>
</ul>
Questa funzionalità opera indipendentemente dai metodi di determinazione costi assegnati all'articolo prodotto. Per impostazione predefinita, in un grafico viene visualizzato il confronto dei costi dal tipo di gruppo di costi. Il grafico consente agli utenti di perforare in livelli più dettagliati.</td>
<td>Consente ai controller di costo o ai responsabili di produzione di analizzare da dove provengono gli scostamenti di produzione e cosa li causa.</td>
</tr>
</tbody>
</table>

## <a name="developer"></a>Sviluppatore

| Operazioni che è possibile effettuare | Dynamics AX 2012 | Dynamics AX 7.0 | Perché questo è importante? |
|------------------|------------------|-----------------|------------------------|
| Creare soluzioni web nel cloud che sono accessibili in molti dispositivi. | Non disponibile | La versione corrente di Dynamics AX si basa su un nuovo client e framework web del client. | È possibile fornire soluzioni di creazione di ultima generazione agli utenti finali. |
| Utilizzo di Microsoft Visual Studio sviluppare le soluzioni. | Microsoft MorphX è l'ambiente di sviluppo principale, ma parte dello sviluppo si verifica in Visual Studio. | Visual Studio è l'unico ambiente di sviluppo. | Include concetti familiari di Dynamics AX 2012 e li adatta in modo integrato al framework e ai paradigmi di Visual Studio. Abilita l'interoperabilità standard con altre lingue e progetti .NET. |
| Compilare Common Intermediate Language (CIL) per tutte le funzionalità. | X++ viene compilato al p-code. | Il nuovo compilatore X++ genera CIL per tutte le funzionalità. CIL è stesso Common Intermediate Language utilizzato da altre lingue di .NET-based. | CIL è più veloce, può fare riferimento efficientemente alle classi in librerie di collegamento dinamico gestite (DLL) e gestire può essere eseguito in una grande base di strumenti di utilità .NET. |
| Incorpora report e visualizzazioni di business intelligence (BI) nel client Microsoft Dynamics AX. | Non disponibile | Creare visualizzazioni molto intuitive e fluide. | Fornisce intuizioni decisionali basate su BI. |
| Integrazione con Microsoft Office. | Non disponibile | Nuove funzioni includono l'applicazione connettore di dati Excel, la pagina di **progettazione della cartella di lavoro**, API di esportazione e gestione documenti. | È possibile creare soluzioni di produttività per gli utenti finali. |
| Automatizzare la compilazione, il test e la distribuzione. | Parzialmente disponibile | Distribuire la topologia di sviluppo utilizzando Developer and Build VM. Configurare automaticamente Build VM per individuare e sviluppare i moduli di Visual Studio Online (VSO) e per l'esecuzione di test. Sono supportati la compilazione e i riferimenti del modulo X++ e di C\#. | Aumenta la produttività di sviluppo riducendo il costo e lo sforzo per test e convalide. |
| Personalizzazione con overlayering ed estensioni. | Le estensioni non sono disponibili. | La versione corrente di Dynamics AX contiene un nuovo modello di personalizzazione. | È possibile personalizzare il codice sorgente e i metadati degli elementi del modello forniti da Microsoft o da partner di terze parti di Microsoft. |
| Sviluppare nuovi controlli e elementi di interfaccia utente tramite X++ e una struttura web moderna. | I controlli personalizzati si basano su framework esterni quali Microsoft ActiveX e Windows Presentation Foundation (WPF). | È più semplice sviluppare i controlli nella versione corrente. Il framework X++ può essere utilizzato per comportamento e la logica di business dell'applicazione e un client HTML/JavaScript-based consente di ottenere visualizzazioni moderne. | I controlli possono essere progettati per assomigliare e comportarsi come i controlli predefiniti di Dynamics AX. |
| Valutare e ottimizzare le prestazioni mediante i nuovi strumenti. | PerfSDK, il toolkit di espansione di dati, l'applicazione web del parser e PerfTimer non sono disponibili. | PerfSDK, il toolkit di espansione di dati, l'applicazione web del parser e PerfTimer sono nuovi. | Il software development kit (SDK) consente di verificare e convalidare tutti i processi aziendali critici delle prestazioni nell'esecuzione dei test monoutente e, se applicabile, multiutente. Il toolkit di espansione di dati consente di espandere correttamente tutti i test delle prestazioni che devono avere i dati master e dati transazionali correttamente espansi. Il parser Trace consente di convalidare un test delle prestazioni monoutente o di esecuzione multiutente. Il PerfTimer consente di visualizzare se qualsiasi query o qualsiasi richiesta al metodo specifica sta causando un problema di prestazioni. Di conseguenza, non è necessario eseguire un'analisi dettagliata. |
| Esporre visualizzazione aggiornabile utilizzando OData. | Non disponibile | La versione corrente di Dynamics AX introduce un endpoint del servizio pubblico di OData che abilita l'accesso ai dati di Dynamics AX in modo coerente in una vasta gamma di client. | Le soluzioni possono interagire con i servizi RESTful, condividere dati in una modalità individuabile e abilitare una vasta integrazione con il protocollo di stack HTTP. |
| Approfitta del connettore aziendale per creare gli scenari di integrazione del supporto e di logica di business. | È possibile usare Business Connector per chiamare il codice X++ dal codice gestito. Si consiglia di utilizzare Business Connector solo per creare la regola business in C\#, non per scenari di integrazione. | Il connettore commerciale non è più supportato. Il requisito di creazione viene fornito dal fatto che X++ viene compilato nel codice gestito. Di conseguenza, Interop è più semplice. Gli scenari di integrazione vengono soddisfatti utilizzando OData. | Non è possibile utilizzare il connettore aziendale d'ora in avanti. |
| Selezionare la scala (ovvero il numero di posizioni decimali) nei campi del database reali e gli Extended Data Type (EDT). | La scala 16 è la scala predefinita e non può essere modificata dallo sviluppatore. | EDT e campi ora dispongono di una proprietà di scala che può applicarsi a singoli campi ed EDT. Il valore è predefinito è 6, non 16. | Le prestazioni con le tabelle NCCI (supporto in memoria in SQL) sono più veloci per ordine di grandezza quando si utilizza una scala inferiore. Modificare la scala secondo come necessario per i singoli campi. |

## <a name="financial-management"></a>Gestione finanziaria

<table>
<thead>
<tr>
<th>Operazioni che è possibile effettuare</th>
<th>Dynamics AX 2012</th>
<th>Dynamics AX 7.0</th>
<th>Perché questo è importante?</th>
</tr>
</thead>
<tbody>
<tr>
<td>Esportare strutture dei conti in Microsoft Excel.</td>
<td>Non disponibile</td>
<td>È ora possibile selezionare una struttura dei conti ed esportarla in Excel.</td>
<td>Molti clienti hanno richiesto la capacità di esportare le strutture dei conti in Excel per una funzione di filtro più semplice.</td>
</tr>
<tr>
<td>Visualizza strutture di contabilità generali e delle regole avanzate associate a una struttura dei conti in una singola pagina.</td>
<td> L'utente deve esplorare diversi moduli per visualizzare la contabilità generale e la struttura dei conti utilizzate.</td>
<td>I riquadri dettaglio informazioni sono stati aggiunti alla pagina della struttura dei conti.</td>
<td>È più semplice accedere alle informazioni importanti quando le strutture dei conti sono definite e modificate.</td>
</tr>
<tr>
<td>Visualizza contabilità generali associate a un piano dei conti in una singola pagina.</td>
<td>L'utente deve esplorare ogni società e aprire il modulo di contabilità generale per visualizzare il grafico del conto assegnato alla contabilità generale.</td>
<td>I riquadri dettaglio informazioni sono stati aggiunti alla pagina del <strong>piano dei conti</strong>.</td>
<td> È più semplice accedere alle informazioni importanti quando il piano dei conti è definito e assegnato.</td>
</tr>
<tr>
<td>Visualizzare rettifiche ai bilanci di chiusura e transazioni di chiusura del bilancio di chiusura in colonne separate nella pagina elenco <strong>Bilancio di verifica</strong>.</td>
<td>L'utente potrà vedere entrambi i tipi di transazioni in una singola colonna.</td>
<td>Un parametro aggiuntivo è stato aggiunto nella pagina elenco <strong>Bilancio di verifica</strong>.</td>
<td>Offre un'analisi più concisa dei dati ed è richiesto per la dichiarazione normativa in alcuni paesi.</td>
</tr>
<tr>
<td>Utilizzare la nuova pagina <strong>giornali di registrazione globali</strong>.</td>
<td>Non disponibile</td>
<td>Nuova pagina <strong>Giornali di registrazione globali</strong> per inserire i giornali di registrazione generali. Privilegi per questa pagina vengono aggiunti al ruolo <strong>Ragioniere</strong>.</td>
<td>Rende possibile a un ragioniere di servizi condivisi immettere i giornali di registrazione generale di diverse società senza dover lasciare il modulo o cambiare il contesto della società.</td>
</tr> 
<tr>
<td>Utilizzare la nuova pagina <strong>Esplora origine contabilità</strong>.</td>
<td>Disponibile da Dynamics AX 2012 R3 CU10.</td>
<td>Nuova pagina <strong>Esplora origine contabilità</strong> e azioni per arrivare alla pagina dalla pagina elenco <strong>Bilancio di verifica</strong> e dalla pagina <strong>Transazioni giustificativo</strong>.</td>
<td>Rende possibile visualizzare le informazioni più dettagliate sull'origine di un bilancio di verifica o di una voce contabile nella contabilità generale o per l'analisi ad hoc.</td>
</tr>
<tr>
<td>Aggiungere livelli di registrazione aggiuntivi.</td>
<td>L'aggiunta di livelli di registrazione aggiuntivi è stata un'esperienza di sviluppatore.</td>
<td>Dieci livelli di registrazione sono ora disponibili.</td>
<td>La maggior parte dei clienti aggiunge livelli di registrazione aggiuntivi.</td>
</tr>
<tr>
<td>Utilizzare l'opzione Giustificativo correlato.</td>
<td>Non disponibile</td>
<td>L'opzione Giustificativo correlato è disponibile per gli utenti per visualizzare il giustificativo nella società per contropartita quando si registrano transazioni interaziendali. Dai giustificativi correlati gli utenti possono fare clic sui dettagli e passare rapidamente al giustificativo della società per contropartita.</td>
<td>Nella registrazione delle transazioni interaziendali, gli utenti non avevano possibilità di visualizzare o tracciare il giustificativo registrato nella società per contropartita.</td>
</tr>
<tr>
<td>Chiusura di massa periodo finanziario</td>
<td>Non disponibile</td>
<td>Gli utenti sono in grado di aggiornare l'accesso al modulo e modificare lo stato del periodo per più società contemporaneamente.</td>
<td>Prima della funzionalità, gli utenti dovevano modificare la società a cui erano connessi, passare al modulo del calendario di contabilità generale e aggiornare manualmente l'accesso al modulo e lo stato del periodo.</td>
</tr>
<tr>
<td>Basare i tassi di cambio su Oanda.</td>
<td>La configurazione del provider dei tassi di cambio in modo da importare i tassi da Oanda è stata un'esperienza di sviluppatore.</td>
<td>Se gli utenti dispongono di una chiave per Oanda, possono immetterla durante la configurazione del provider di tassi di cambio.</td>
<td>Gli utenti possono usufruire della funzionalità predefinita facendo in modo che i tassi di cambio da Oanda vengano importati in modo programmato.</td>
</tr>
<tr>
<td>Filtrare i report finanziari (Management Reporter) in base alle dimensioni, gli attributi, le date e gli scenari.</td>
<td> Qualsiasi filtro dei report di Management Reporter viene gestito nella progettazione del report. Ad esempio, se un utente con privilegi di visualizzazione desidera visualizzare un report per una data diversa, una finestra di progettazione report deve apportare la modifica.</td>
<td>Sono state aggiunte opzioni di report che consentono di applicare filtri differenti durante la visualizzazione di un report. In base a tali filtri viene generato un nuovo report.</td>
<td>Gli utenti dei report finanziari possono applicare filtri diverse per le dimensioni, date, gli attributi e gli scenari senza richiedere aggiornamenti alle progettazioni dei report.</td>
</tr>
<tr>
<td>Visualizzare report finanziari (Management Reporter) nel client Microsoft Dynamics AX.</td>
<td>Un web client distinto è stato utilizzato per visualizzare i report di Management Reporter.</td>
<td>A tutti i report finanziari è possibile accedere nel client di Dynamics AX. L'utente seleziona un report da visualizzare e il report viene visualizzato nel client.</td>
<td>È ora possibile visualizzare i report finanziari senza che sia necessario accedere a un client/applicazione diverso.</td>
</tr>
<tr>
<td>Stampare report finanziari (Management Reporter) dal client Microsoft Dynamics AX.</td>
<td>La stampa di un report utilizza le opzioni di stampa del browser per stampare e stampa solo gli elementi visualizzati sullo schermo dell'utente.</td>
<td>L'utente può scegliere l'impostazione di pagina e livello di dettaglio per un report utilizzando l'opzione di stampa del report finanziario nel client Dynamics AX.</td>
<td>I report vengono stampati nel modo che gli utenti si aspettano anziché stampare una pagina Web.</td>
</tr><tr>
<td>Analisi dei dati finanziari utilizzando il pacchetto di contenuti Power BI "Monitora prestazioni finanziarie".</td>
<td>Non disponibile</td>
<td>Su PowerBI.com, selezionare <strong>Recupera i dati</strong> e quindi il pacchetto di contenuti <strong>Dynamics AX - Prestazioni finanziarie</strong>. Immettere l'url del endpoint di Dynamics AX per vedere i dati riflessi nel dashboard.</td>
<td>In tre o quattro clic, le organizzazioni possono distribuire il dashboard di Power BI contenente i dati finanziari importanti. Il contenuto può essere personalizzato dall'organizzazione.</td>
</tr>
<tr>
<td>Tracciare i processi di chiusura periodo finanziario.</td>
<td>Non disponibile</td>
<td>I modelli e le programmazioni di chiusura possono essere creati utilizzando la configurazione finanziaria di fine del periodo. Utilizzare l'area di lavoro <strong>Fine finanziaria di periodo</strong> per tenere traccia dello stato di avanzamento delle programmazioni di chiusura tra le più società.</td>
<td>Questa area di lavoro elimina i sistemi manuali per definire, effettuare la programmazione e comunicare le attività di chiusura. Di conseguenza, il numero di giorni alla chiusura viene ridotto</td>
</tr>
<tr>
<td>Monitorare il budget rispetto ai valori reali e creare le previsioni di contabilità generale utilizzando l'area di lavoro <strong>Budget contabili e previsioni</strong> e i moduli di richiesta informazioni aggiuntivi.</td>
<td>Non disponibile</td>
<td> L'area di lavoro può essere acceduta tramite il dashboard di Dynamics AX. Include collegamenti a diverse nuove pagine di richiesta informazioni: <strong>Rieilogo confronto tra valori effettivi e budget</strong><strong>Riepilogo statistiche di controllo del budget</strong>, <strong>Voci del registro di budget</strong> e <strong>Piani di budget</strong>.</td>
<td>Le nuove pagine di richiesta informazioni consentono l'accesso semplice alle informazioni del budget. L'area di lavoro combina tutte le attività di manutenzione e controllo del budget in una sola posizione semplice da utilizzare per gli amministratori di budget o i responsabili di contabilità.</td>
</tr>
<tr>
<td>Creare layout per le previsioni e il piano di budget.</td>
<td>Il documento <strong>Piano di budget</strong> viene visualizzato come un elenco di righe con le date di validità e importi delle combinazioni di dimensioni finanziarie. L'utente deve creare e utilizzare i modelli Excel per visualizzare i dati di piano di budget in una tabella Pivot.</td>
<td>Un numero illimitato di layout sono disponibili per le previsioni e di piano di budget. È possibile combinare le dimensioni finanziarie selezionate, le colonne definite dall'utente e un'altra attributi della riga (ad esempio i commenti, progetti e cespiti) nel layout. Gli utenti possono trascorrere il layout del documento di piano di budget immediatamente e modificare i dati utilizzando qualsiasi layout selezionato. La configurazione pianificazione del budget viene semplificata l'eliminazione dei vincoli dello scenario e il layout per definire i dati possono essere visualizzati e modificati in ogni fase del documento di piano di budget.</td>
<td>Fornisce la flessibilità di creare e modificare di piano di budget utilizzando sia Excel che il client di Dynamics AX. I modelli per le cartelle di lavoro di Excel possono essere generati utilizzando l'impostazione del layout di piano di budget.</td>
</tr>
<tr>
<td>Consente di stampare il report <strong>Transazioni fatture fornitore</strong> utilizzando le informazioni del report <strong>Elenco dettagliato date di scadenza</strong>, che include i giorni arretrati.</td>
<td>È necessario stampare due report diversi: <strong>Elenco dettagliato date di scadenza</strong> e <strong>Transazioni fatture fornitore</strong>.</td>
<td>Le informazioni sui due report sono state consolidate nel report <strong>Transazioni fatture fornitore</strong>. Il report <strong>Elenco dettagliato date di scadenza</strong> è stato rimosso.</td>
<td>Eliminate la necessità di stampare due report distinti ma correlati.</td>
</tr>
<tr>
<td>Generare i report normativi direttamente in formato PDF.</td>
<td>È innanzitutto necessario generare un report normativo in un formato quindi esportarlo nel formato PDF.</td>
<td>Il formato PDF è il formato predefinito per i report normativi.</td>
<td>Fornisce un'esperienza di visualizzazione consolidata sia sul monitor del computer che su una copia cartacea stampata.</td>
</tr>
<tr>
<td>Eseguire il processo di liquidazione IVA come processo batch.</td>
<td>Non disponibile</td>
<td>Nella pagina <strong>Periodo liquidazione IVA</strong> è possibile specificare che il processo di liquidazione deve essere eseguito in batch.</td>
<td>Per i periodi con molte transazioni fiscali, il processo di liquidazione può essere dispendioso in termini di tempo e può essere migliore eseguire il processo in background come processo batch.</td>
</tr>
</tbody>
</table>

## <a name="foundation"></a>Fondazione

<table>
<thead>
<tr>
<th>Operazioni che è possibile effettuare</th>
<th>Dynamics AX 2012</th>
<th>Dynamics AX 7.0</th>
<th>Perché questo è importante?</th>
</tr>
</thead>
<tbody>
<tr>
<td>Accedi in qualsiasi momento al client, da qualsiasi luogo.</td>
<td>Il client desktop 2012 di AX offre una serie di completa moduli, ma può essere eseguito solo i computer che eseguono Microsoft Windows e richiede l'impostazione. Il terminal server viene usato spessp con il client desktop per abilitare l'accesso su una wide area network (WAN). Il client web Enterprise Portal fornisce un set di moduli ridotto.</td>
<td>I due client AX 2012 sono stati sostituiti da un unico web client in base a standard che fornisce la serie completa di funzionalità del client desktop insieme alla portata del client Enterprise Portal.</td>
<td>Impedisce che il lavoro di sviluppo venga diviso tra due piattaforme di interfaccia utente. Utilizzando le interfacce standard web, elimina la necessità del terminal server.</td>
</tr>
<tr>
<td>Sii produttivo utilizzando il nuovo registratore attività.</td>
<td>Il registratore attività di AX 2012 richiede l'accesso diretto a un computer Application Object Server (AOS) e i privilegi massimi e non sono disponibili opzioni di modifica.</td>
<td>Il nuovo registratore attività può essere utilizzato direttamente dal web client. L'accesso al registratore attività non richiede i privilegi di admin. I passaggi di registrazione possono visualizzati dal vivo mentre si registra, nuove opzioni di modifica sono state introdotte e supporta più scenari oltre agli scenari esistenti di Business process modeler (BPM).</td>
<td>Il nuovo registratore attività fornisce un'esperienza semplficata e dà impulso a nuove funzionalità di Dynamics AX. Alcune delle funzionalità sono ora disponibili e altre seguiranno in futuro.</td>
</tr>
<tr>
<td>Aiuta gli utenti a comprendere meglio il proprio lavoro imminente con le aree di lavoro.</td>
<td>In tali pagine viene fornita una panoramica delle informazioni relative alla funzione lavorativa di un utente all'interno dell'azienda o dell'organizzazione.</td>
<td>Le aree di lavoro sono un concetto nuovo in Dynamics AX che sostituiscono i centri gestione ruolo come il modo principale per passare alle attività e alle pagine specifiche. Forniscono una panoramica di una pagina di un'attività aziendale e consentono agli utenti di comprendere lo stato corrente, il carico di lavoro imminente e le prestazioni del processo o utente. Le aree di lavoro sono più granulari rispetto ai centri gestione ruolo di AX 2012 e un utente può avere accesso a più aree di lavoro.</td>
<td>Le aree di lavoro hanno lo scopo di aumentare la produttività degli utenti. Gli sviluppatori devono creare un'area di lavoro per ogni significativa "attività" supportata nel prodotto. Un centro gestione ruolo legacy di AX 2012 verrà in genere sostituito da più aree di lavoro nella versione corrente di Dynamics AX.</td>
</tr>
<tr>
<td>Rendere i moduli reattivi alle dimensioni del riquadro di visualizzazione del browser o del dispositivo.</td>
<td>In AX 2012, il contenuto del modulo era rigidamente disposto in colonne e le proporzioni generali altezza/larghezza del modulo in gran parte erano determinate in base ai controlli del modulo.</td>
<td>Con lo spostamento sul Web della versione più recente di Dynamics AX, le dimensioni dei moduli sono ora basate sulla dimensione del riquadro di visualizzazione del browser o del dispositivo. I controlli e i parametri di layout sono state modificati o aggiunti per meglio rispondere alle modifiche delle dimensioni del riquadro di visualizzazione.</td>
<td>Il contenuto dei moduli deve essere più reattivo per usare in modo ottimale l'altezza/larghezza disponibile del browser o dispositivo. Per ottenere la reattività può essere necessario fare modifiche al modo in cui il modulo è modellato.</td>
</tr>
<tr>
<td>Utilizzare schemi per un'esperienza di sviluppo modulo avanzata.</td>
<td>Modelli di modulo erano disponibili come punto di partenza per sviluppo di moduli in AX 2012 in base allo stile di un modulo. Form Style Checker, componente aggiuntivo opzionale, forniva informazioni su come un modulo si discostava dal modello corrispondente.</td>
<td>Nella versione corrente di Dynamics AX, sono stati introdotti gli schemi di modulo. Gli schemi di modulo rappresentano una combinazione di modelli di modulo e Form Style Checker strettamente integrati nell'esperienza di sviluppo. Gli schemi sono stati definiti a livello del modulo (come in AX 2012) con altri schemi secondari ora disponibili a livello di gruppo e pagina a schede.</td>
<td>I moduli conformi agli schemi dispongono di numerosi vantaggi, tra cui un'interfaccia utente più coerente, un'esperienza di sviluppo più semplice, più facile percorso di aggiornamento moduli e maggiore fiducia nei tempi di risposta del layout modulo.</td>
</tr>
</tbody>
</table>

## <a name="help"></a>?

<table>
<thead>
<tr>
<th>Operazioni che è possibile effettuare</th>
<th>Dynamics AX 2012</th>
<th>Dynamics AX 7.0</th>
<th>Perché questo è importante?</th>
</tr>
</thead>
<tbody>
<tr>
<td>Accesso alla guida procedurale (guide di attività) e agli argomenti concettuali facendo clic su <strong>Guida</strong>.</td>
<td>La guida di AX 2012 punta agli argomenti HTML che vengono archiviati in un web server locale. I clienti e i partner possono creare la relativa specifica guida.</td>
<td>Nella Guida della versione corrente di attività di Dynamics AX sono visualizzate guide di attività archiviate in Microsoft Dynamics Lifecycle Services (LCS) BPM. Nella Guida sono inoltre visualizzati gli argomenti inclusi nel sito documenti di Microsoft. Per altre informazioni, vedere <a href="help-overview.md" data-raw-source="[Dynamics AX Help - Getting Started](help-overview.md)">Guida di Dynamics AX - Introduzione</a> e <a href="new-task-guides-available-february-2016.md" data-raw-source="[New task guides available (February 2016)](new-task-guides-available-february-2016.md)">Nuove Guide attività disponibili (febbraio 2016)</a>.</td>
<td>La guida attività fornisce un'esperienza controllata, guidata e interattiva che guida l'utente attraverso i passaggi di un'attività o un processo aziendale. È possibile scaricare e personalizzare le guide attività fornite da Microsoft. L'argomento illustra un modo più rapido e flessibile per creare, distribuire e aggiornare la documentazione del prodotto. Di conseguenza, aiuta a garantire l'accesso alle ultime informazioni tecniche.</td>
</tr>
</tbody>
</table>

## <a name="human-capital-management"></a>Gestione risorse umane

<table>
<thead>
<tr>
<th>Operazioni che è possibile effettuare</th>
<th>Dynamics AX 2012</th>
<th>Dynamics AX 7.0</th>
<th>Perché questo è importante?</th>
</tr>
</thead>
<tbody>
<tr>
<td>Trasferire le competenze e i certificati i partecipanti di una classe al completamento del corso.</td>
<td>Si tratta di un processo manuale.</td>
<td>Quando un corso è stato completato, una nuova opzione diventa disponibile per aggiornare i record di un partecipante alle competenze e nuovi certificati.</td>
<td>Fornisce una nuova modalità efficiente di aggiornare i record dipendente.</td>
</tr>
<tr>
<td>Verifica rapidamente l'impiego.</td>
<td>Si tratta di un processo manuale.</td>
<td>Il reparto di HR può verificare rapidamente l'impiego con un'area di lavoro o la pagina dei dipendenti.</td>
<td>Il reparto HR non deve più accedere a diverse pagine per verificare la data di inizio, il responsabile, i mesi nella posizione e i dati di retribuzione.</td>
</tr>
<tr>
<td>Consenti ai dipendenti di visualizzare, aggiornare ed eliminare le informazioni nel sistema.</td>
<td>Disponibile, ma con funzionalità di visualizzazione e aggiornamento limitate.</td>
<td>Questa funzionalità è abilitata e consente a dipendenti e terzisti di visualizzare una vasta gamma di dati personali. Facoltativamente, un flusso di lavoro può essere utilizzato quando le informazioni vengono create, aggiornate o eliminate.</td>
<td>Consente ai dipendenti di avere il controllo delle proprie informazioni, sia che include aggiornare l'indirizzo o le informazioni di contatto, candidarsi per un lavoro, compilare un questionario o aggiornare la propria immagine. Quando un flusso di lavoro è abilitato, le informazioni possono essere riviste da un approvatore o essere approvate, in base ai processi aziendali.</td>
</tr>
<tr>
<td>Consente ai responsabili di modificare o visualizzare le informazioni dei dipendenti.</td>
<td>Disponibile, ma con funzionalità di visualizzazione e aggiornamento limitate.</td>
<td>A seconda delle impostazioni di configurazione e della sicurezza, gli amministratori possono visualizzare o modificare le informazioni sul personale.</td>
<td>Consente agli amministratori di accedere ai dati importanti per un dipendente, in modo che possono prendere migliori decisioni sul resourcing, le prestazioni e lo sviluppo del dipendente.</td>
</tr>
<tr>
<td>È possibile sfruttare la funzionalità responsabile self-service.</td>
<td>Non disponibile</td>
<td>I responsabili possono ora inviare le richieste di nuove assunzioni (dipendenti e terzisti), il trasferimento e fine rapporto (fine del rapporto di impiego). I responsabili possono anche richiedere una nuova posizione, estendere la durata di posizioni o richiedere modifiche di posizione.</td>
<td>Questi scenari erano prima esposti solo alle Risorse umane. L'abilitazione di questi scenari fornisce potenti strumenti per i responsabili di un'organizzazione. È possibile attivare i flussi di lavoro facoltativi per fornire il giusto livello di revisione e approvazione.</td>
</tr>
<tr>
<td>Accedere ai risultati di elaborazione di retribuzione.</td>
<td>I risultati sono disponibili solo al momento dell'elaborazione.</td>
<td>Ora si può accedere ai risultati di elaborazione di retribuzione in un punto qualsiasi dopo che il processo è stato eseguito.</td>
<td>Fornisce un controllo eccellente del processo e il risultato del processo. Fornisce anche una visualizzazione completa dei dati prima che i record dipendente vengano aggiornati.</td>
</tr>
<tr>
<td>Accedere ai risultati di elaborazione di benefit.</td>
<td>I risultati sono disponibili solo al momento dell'elaborazione.</td>
<td>Ora si può accedere ai risultati di elaborazione di benefit in un punto qualsiasi dopo che il processo è stato eseguito.</td>
<td>Fornisce una visualizzazione completa dei dati che vengono aggiornati da registrazione benefit e dalle variazioni di costo.</td>
</tr>
<tr>
<td>Visualizzare modifiche relative alla sequenza temporale della "data di entrata in vigore".</td>
<td>Non disponibile</td>
<td>Questo strumento di confronto è disponibile per i dipendenti, le posizioni e i processi. Fornisce una visualizzazione completa delle modifiche da una versione di un record a un altro.</td>
<td>Consente di risparmiare tempo quando si visualizzano modifiche che hanno avuto luogo nel tempo sui dipendenti, le posizioni e i record di processo. Consente di confrontare rapidamente due versioni di un record, o tutti i record, nel tempo.</td>
</tr>
<tr>
<td>Visualizzare dipendenti per società.</td>
<td>Si tratta di un processo manuale che viene eseguito tramite il filtro.</td>
<td>Gli elenchi del terzista e dipendente vengono automaticamente filtrati in base alla società a cui si è connessi.</td>
<td>Fornisce un punto di vista filtrato dei dipendenti da un dipendente nella società collegata. Per un punto di vista non filtrato di tutti i dipendenti e terzisti, l'elenco di lavoratori è di nuovo disponibile. Nella versione corrente di Dynamics AX, il sistema non modificare la società in base al dipendente selezionato nell'elenco.</td>
</tr>
<tr>
<td>Aggiorna l'elenco dei partecipanti al corso.</td>
<td>Non disponibile</td>
<td>I partecipanti del corso possono essere rimossi dall'elenco dei partecipanti.</td>
<td>Fornisce un modo semplice di aggiornare partecipanti registrati per errore.</td>
</tr>
<tr>
<td>Gestisci eventi retributivi in un gruppo.</td>
<td>Non disponibile</td>
<td>Questa funzionalità migliora l'elaborazione delle modifiche di retribuzione per i dipendenti.</td>
<td>Fornisce un processo semplice e aggiornato per aggiornare i record dipendente tramite l'area di lavoro di retribuzione e le pagine correlate.</td>
</tr>
</tbody>
</table>

## <a name="inventory-management"></a>Gestione inventario

Non sono state aggiunte nuove funzionalità.

## <a name="localization"></a>Localizzazione

<table>
<thead>
<tr>
<th>Operazioni che è possibile effettuare</th>
<th>Dynamics AX 2012</th>
<th>Dynamics AX 7.0</th>
<th>Perché questo è importante?</th>
</tr>
</thead>
<tbody>
<tr>
<td>Configurare e generare i documenti elettronici per soddisfare le esigenze giuridiche in diversi paesi UE.</td>
<td>I documenti elettronici vengono specificati in X++ o come Extensible Stylesheet Language Transformations (XSLT). Tutte le rettifiche di formato richiedono lavoro di sviluppo. L'accesso ai dati e la formattazione non sono isolati. Una distribuzione di formato rettificata richiede un nuovo pacchetto di aggiornamento di Microsoft Dynamics AX che sostituisce il formato esistente. Le modifiche personalizzate di ogni formato devono essere trasferite manualmente al codice sorgente del nuovo pacchetto di aggiornamento di Microsoft Dynamics AX.</td>
<td>Creazione di report elettronici (ER) è un nuovo strumento per la configurazione e la creazione di documenti elettronici mirati a un utente commerciale anziché uno sviluppatore. ER consente di impostare i modelli di dati specifici di dominio e indipendenti dal database di Microsoft Dynamics AX come origini dati per i formati di documento. Un utente commerciale può configurare i formati, in base a tali modelli di dati specifici di dominio ad esempio, per i pagamenti, i report Intrastat, o i report IVA. L'utente può configurare i formati utilizzando gli strumenti visivi semplici che sono simili in Excel. ER attualmente supporta la creazione di documenti elettronici in formato di testo, XML ed Excel. I documenti possono essere generati contemporaneamente e essere inseriti nei file ZIP. I modelli di dati e i formati supportano il controllo delle versioni. Le versioni del formato possono essere periodi validi. Ciascuna versione del formato o del modello dati è archiviata nella distinta e viene distribuita a partner e clienti tramite LCS. I partner e clienti possono personalizzare i modelli di dati e i formati di Microsoft, o crearne di propri. ER salva le modifiche di configurazione del cliente e il partner come delta alle configurazioni di Microsoft, semplificando gli aggiornamenti alle nuove versioni delle configurazioni di Microsoft. Utilizzando LCS, i partner possono anche condividere le configurazioni del formato e del modello dati con altri partner e clienti, che possono personalizzarli e condividerli. La personalizzazione delta e l'aggiornamento semplice sono supportati lungo l'intera catena di personalizzazione.</td>
<td>ER semplifica la creazione, la gestione e l'aggiornamento dei formati di documenti elettronici per soddisfare le esigenze giuridiche in diversi paesi. ER rende il processo di creare o di modificare i formati di documenti elettronici più veloce e più semplice. Le modifiche possono essere effettuate dagli utenti aziendali anziché gli sviluppatori. ER rende più veloce e più semplice per i partner e clienti aggiornare le personalizzazioni di formato alle nuove versioni dei formati emessi da Microsoft o altri partner. ER fornisce una modalità in comune (attraverso LCS) per Microsoft e i partner per distribuire le configurazioni di documenti elettronici ad altri partner e clienti. ER inoltre rende più semplice per partner e clienti personalizzare, aggiornare e distribuire i formati di documenti elettronici per i propri requisiti aziendali specifici.</td>
</tr>
<tr>
<td>(MEX) Generare report regolatori dell'imposta sul valore aggiunto (IVA) messicana.</td>
<td>È necessario generare report <strong>IVA acquisto e vendita</strong> utilizzando la funzionalità IVA non realizzata, in modo che gli utenti possono identificare le transazioni appartenenti alle sezioni e non realizzate in base allo stato.</td>
<td>I report <strong>IVA acquisto e vendita</strong> sono stati modificati e ora considerano la funzionalità condizionale IVA solo tramite i periodi di liquidazione specifici per la definizione dei codici IVA non realizzati e realizzati.</td>
<td>Le modifiche nella configurazione dei codici IVA sono necessarie prima che gli utenti possano generare i report correttamente. Una funzionalità IVA condizionale è richiesta e l'utente deve configurare i periodi di liquidazione separati, realizzati e non realizzati per identificare le transazioni in aree di sezione correlate.</td>
</tr>
<tr>
<td>(JPN) Gestire il documento giapponese della dichiarazione di ammortamento accelerato del cespite.</td>
<td>Non disponibile</td>
<td>Le informazioni importanti della dichiarazione centralmente archiviate in un unico documento per migliore gestione.</td>
<td>La conformità di documento e facilità della guida di gestione riducono le uscite durante i controlli e altri esami.</td>
</tr>
<tr>
<td>(JPN) Verificare i caratteri JBA nel conto bancario.</td>
<td>Non disponibile</td>
<td>È possibile verificare che i campi del nome kana contengano solo caratteri consentiti dal formato della banca JBA.</td>
<td>Contribuisce a ridurre le interruzoni agli utenti durante la creazione del file di pagamento a causa di caratteri non validi.</td>
</tr>
<tr>
<td>(JPN) Colmpare la differenza in centesimi del cespite Giappone alla fine dell'anno fiscale.</td>
<td>Non disponibile</td>
<td>Nella pagina <strong>Parametri cespiti</strong> è possibile scegliere la fine del periodo fiscale o dell'anno fiscale.</td>
<td>Fornisce maggiore flessibilità per rispettare le procedure locali.</td>
</tr>
<tr>
<td>(JPN) Generare le tabelle accodate di dichiarazione fiscale aziendale giapponese serie 16 a un importo riepilogativo per tipo principale del cespite.</td>
<td>Non disponibile</td>
<td>Sui modelli di valore di un cespite, è possibile scegliere di riepilogare per tipo principale. Per impostazione predefinita, questa funzionalità è utilizzata per i cespiti appena creati.</td>
<td>Per grandi le società con migliaia di cespiti, i report riepilogati notevolmente riducono la dimensione del report generato.</td>
</tr>
<tr>
<td>(JPN) Iniziare ad allocare il fondo di ammortamento speciale all'anno fiscale successivo per i cespiti di Giappone.</td>
<td>Non disponibile</td>
<td>Sui modelli di valore di un cespite con un profilo di ammortamento straordinario appropriato, è possibile scegliere di avviare l'allocazione dal periodo fiscale successivo o anno fiscale successivo.</td>
<td>Fornisce maggiore flessibilità per rispettare le procedure locali.</td>
</tr>
<tr>
<td>(JPN) Generare un report IVA sui consumi in Giappone che include le aliquote IVA rivedute.</td>
<td>Il report IVA sui consumi è disponibile per un'aliquota d'imposta del 5%.</td>
<td>Il report IVA sui consumi contiene una sezione dell'aliquota d'imposta riveduta ad esempio l'8%).</td>
<td>Il layout è stato da poco annunciato dal governo.</td>
</tr>
<tr>
<td>(UE) Configurare le impostazioni di arrotondamento per elenco vendite UE.</td>
<td>Le impostazioni di arrotondamento per l'elenco vendite UE per diversi paesi sono hardcoded in X + + o in Extensible Stylesheet Language Transformations (XSLT).</td>
<td>Le impostazioni di arrotondamento vengono aggiunte ai parametri di commercio estero. È possibile configurare precisione di arrotondamento, metodo di arrotondamento, precisione dell'output e il comportamento per importi inferiori alla precisione di arrotondamento.</td>
<td>Questo unifica e semplifica la configurazione dell'elenco vendite UE. La correzione delle impostazioni di arrotondamento non richiede più attività di sviluppo.</td>
</tr>
<tr>
<td>(UE) Configurare le regole di applicabilità reverse charge.</td>
<td>Le regole di applicabilità reverse charge sono hardcoded per lo scenario reverse chargd interno. La soglia di applicabilità può essere impostata per gruppo di articoli. La funzionalità è disponibile per la sola Gran Bretagna.</td>
<td>È possibile configurare regole di applicabilità reverse charge per tipo di documento (ordine fornitore/cliente, fattura fornitore, fattura a testo libero, ecc.) e un gruppo reverse charge combina gli articolo, i gruppi di articoli e le categorie di acquisto/vendita. Le regole di applicabilità hanno date di validità. È inoltre possibile contrassegnare singoli codici IVA in fasce IVA applicabili per reverse charge. Il report fattura di vendita viene regolato per rappresentare i dettagli del reverse charge applicato. La funzionalità è disponibile per tutti paesi europei.</td>
<td>Questa modifica unifica la configurazione delle regole di applicabilità reverse charge e supporta l'adozione dei regolamenti reverse charge nazionali dei paesi europei.</td>
</tr>
<tr>
<td>(DE) Generare il file di controllo tedesco - GDPdUGoBD</td>
<td>Gli utenti possono impostare la definizione di tabelle contenenti dati finanziari da esportare in un formato accettato da autorità e revisori tedeschi.</td>
<td>La funzionalità è stata implementata come configurazione per la creazione di report elettronici. La funzionalità è disponibile per la Germania e l'Austria.</td>
<td>Questa modifica offre molte più possibilità nella formattazione dei dati, le trasformazioni e fornisce inoltre tutti i vantaggi provenienti dalla gestione del ciclo di vita della configurazione dei report elettronici, come la facilità di scambio di configurazioni, il controllo delle versioni e così via.</td>
</tr>
<tr>
<td>(FR) Elenco saldi con conti totali di gruppo - report.</td>
<td>Il report Elenco saldi con conti totali di gruppo viene implementato come report SSRS (LedgerAccountSum_FR).</td>
<td>Il report Elenco saldi con conti totali di gruppo viene implementato come report Management Reporter disponibile nella cartella di report finanziari localizzati della raccolta di risorse LCS.</td>
<td>Ciò consente agli utenti di ottenere tutti i vantaggi e libertà nelle personalizzazioni dall'uso dei report finanziari in Management Reporter.</td>
</tr>
<tr>
<td>(UE) Report Avviso di pagamento, Nota di partecipazione e Controllo per i pagamenti.</td>
<td>Tutti questi report sono implementati e report SSRS.</td>
<td>Questi report sono stati implementati come modelli Open XML da utilizzare in Microsoft Excel.</td>
<td>Le configurazioni di pagamento elettronico contengono modelli e impostazione di formato file di pagamento. Ciò consente agli utenti di ottenere tutti i vantaggi e libertà nelle personalizzazioni dei report dall'uso della creazione di report finanziari.</td>
</tr>
<tr>
<td>(UE) Configurare le impostazioni di arrotondamento per Intrastat.</td>
<td>Le impostazioni di arrotondamento per i report Intrastat per diversi paesi sono hardcoded in X + + o in Extensible Stylesheet Language Transformations (XSLT).</td>
<td>Le impostazioni di arrotondamento vengono aggiunte ai parametri di commercio estero. È possibile configurare precisione di arrotondamento, metodo di arrotondamento, precisione dell'output e il comportamento per importi inferiori alla precisione di arrotondamento.</td>
<td>Questo unifica e semplifica la configurazione dei report Intrastat. La correzione delle impostazioni di arrotondamento non richiede più attività di sviluppo.</td>
</tr>
<tr>
<td>(UE) Impostare i codici voci doganali Intrastat in gerarchie di categorie.</td>
u<td>I codici voci doganali Intrastat sono un elenco separato. Sebbene esista una gerarchia di categorie di tipo codice voce doganale, questi codici potrebbero automaticamente essere impostati in componenti Retail HQ e categorie di vendita.</td>
<td>L'elenco separato di codici voci doganali Intrastat viene unito a una gerarchia di prodotti di tipo codice voce doganale.</td>
<td>Questo unifica l'approccio per l'assegnazione di codici di voce doganale alle categorie e ai prodotti rilasciati nei documenti di vendita e acquisto.</td>
</tr>
<tr>
<td>(UE) Riportare quantità in unità supplementari per Intrastat utilizzando l'impostazione di conversione unità.</td>
<td>Il codice voce doganale Intrastat ha un campo di testo per identificare le unità supplementari e la scheda<strong> Prodotto</strong> dispone di un campo per identificare la quantità di unità supplementari in chilogrammi.</td>
<td>Le unità supplementari per il codice voce doganale Intrastat vengono scelte dall'elenco delle unità. La quantità di unità supllementari viene calcolata tramite le impostazioni di conversione unità.</td>
<td>Questo unifica l'approccio per il ricalcolo da unità di transazione a unità supplementaru.</td>
</tr>
<tr>
<td>(UE) Assegnare il metodo di trasporto predefinito alla modalità di consegna.</td>
<td>Non disponibile</td>
<td>Un campo per il metodo di trasporto predefinito viene aggiunto alla modalità di consegna.</td>
<td>In questo modo si semplifica la preparazione della dichiarazione Intrastat.</td>
</tr>
<tr>
<td>(UE) Contrassegnare un rilasciato prodotto per non dichiararlo in Intrastat.</td>
<td>Non disponibile</td>
<td>Un'opzione per escludere l'articolo dalla dichiarazione Intrastat viene aggiunta al prodotto rilasciato.</td>
<td>In questo modo si semplifica la preparazione della dichiarazione Intrastat.</td>
</tr>
</tbody>
</table>

## <a name="manufacturing"></a>Produzione

| Operazioni che è possibile effettuare | Dynamics AX 2012 |
|------------------|------------------|
| Eseguire una verifica di disponibilità materiale per gli ordini di produzione in una pagina separata che viene aperta dall'area di lavoro **Gestione area produzione**. | Non disponibile |
| Avviare e segnalare lo stato di avanzamento nei processi di produzione tramite la nuova pagina **Dispositivo schede processo**. | Il modulo **Registrazione processi** principalmente viene inoltrato a grandi schermi del terminale e l'interfaccia utente in genere è acceduta tramite clic sul mouse. |

## <a name="master-planning-and-forecasting"></a>Offerta e pianificazione generale

| Operazioni che è possibile effettuare | Dynamics AX 2012 | Dynamics AX 7.0 | Perché questo è importante? |
|------------------|------------------|-----------------|------------------------|
| Avvisare l'utente se un ordine cliente o un ordine di produzione non è pronto per la consegna alla data programmata. | Gli avvisi creati dalla pianificazione generale sono chiamati *messaggi di ritardo*. *Ritardo* è un contratto tra due parti per acquistare o vendere un cespite a un prezzo accordato alla data odierna ( *prezzo di ritardo*), sebbene consegna e pagamento avverranno in futuro (*data di consegna*). | *Messaggi di ritardo* e *date ritardo* sono stati rinominati *ritardi calcolati* e *date ritardate* rispettivamente. | La terminologia utilizzata in AX 2012 era inesatta e ha comportato traduzioni non corrette. |
| Ottieni informazioni rapide sullo stato dell'esecuzione di pianificazione generale, gli ordini pianificati urgenti e gli ordini pianificati che causano ritardi. | Le informazioni sono disponibili, ma sono sparse su diversi moduli. | L'area di lavoro **Pianificazione generale** offre informazioni a colpo d'occhio su quando l'ultima esecuzione di pianificazione generale è stata completata, se si sono verificati errori, quali sono gli ordini pianificati urgenti e quali ordini pianificati causano ritardi. | Puoi ottenere vantaggi dalla panoramica offerta dall'area di lavoro. Le informazioni rilevanti sono presentate per facilitare la pianificazione generale e consentono di migliorare la produttività. |
| Utilizzare Excel per aggiornare le previsioni della domanda. | Non disponibile | È possibile approfittare dell'integrazione fluida con Excel quando si immettono le previsioni della domanda, si effettuano aggiornamenti e si eliminano previsioni della domanda. | Consente di aumentare l'efficienza e la produttività. |
| Stimare la domanda futura e creare le previsioni della domanda in base ai dati transazione storici. | In Microsoft Dynamics AX 2012 R3, i modelli previsionali in Microsoft SQL Server Analysis Service vengono utilizzati per creare le previsioni di previsione della domanda. | Stimare la domanda futura utilizzando la potenza e l'estendibilità di un servizio cloud Microsoft Azure Machine Learning. È semplice da usare ed estende i modelli previsionali nel Machine Learning per soddisfare i requisiti del cliente. Nel servizio vengono eseguite selezioni di modello di corrispondenza migliore e offre a indicatori di prestazioni chiave (KPI) da utilizzare per calcolare l'accuratezza di previsione. | Genera previsioni più accurate utilizzando le tecniche di apprendimento automatico. |
| Ottimizza la data e la quantità degli ordini, in base a una panoramica visiva azioni relative all'esecuzione di pianificazione generale. | La panoramica del grafico di azioni è disponibile ma mostra tutte le azioni correlate. Quando le azioni vengono applicate, immediatamente scompaiono dalla visualizzazione. | Il piano di azioni fornisce una migliore panoramica. Include le opzioni che consentono di visualizzare solo le azioni applicate e le azioni direttamente correlate. Quando le azioni vengono applicate, sembrano attenuate ma vengono comunque visualizzate. Di conseguenza, la panoramica verrà mantenuta. Informazioni aggiuntive verranno aggiunte al grafico di azioni per visualizzare i dati in una pagina. | Trai giovamento da analisi di produttività, perché ti concentri solo sulle azioni rilevanti. |

## <a name="procurement-and-sourcing"></a>Approvvigionamento

| Operazioni che è possibile effettuare | Dynamics AX 2012 | Dynamics AX 7.0 | Perché questo è importante? |
|------------------|------------------|-----------------|------------------------|
| Utilizzare l'area di lavoro **Preparazione ordini acquisto** per ottenere informazioni rapide sullo stato degli ordini fornitore che vengono preparati. | Non supportato | L'area di lavoro **Preparazione ordini acquisto** offre una panoramica degli ordini dal momento in cui vengono creati come bozza e vengono tracciati, tramite gli stati di approvazione del flusso di lavoro e verso la conferma. | Il reparto acquisti non deve più raccogliere informazioni da più pagine più ma ora può utilizzare la panoramica offerta dall'area di lavoro. |
| Utilizzare l'area di lavoro **Ricevimento e follow-up ordine acquisto** per ottenere informazioni rapide sugli ordini fornitore con entrata in sospeso, per fornire assistenza con il follow-up. | Non supportato | L'area di lavoro **Ricevimento e follow-up ordine acquisto** offre una panoramica degli ordini fornitore confermati con ricevimenti o spedizioni in sospeso. L'area di lavoro include gli elenchi delle entrate post-scadenza e in sospeso per agevolare la revisione dinamica e il follow-up da parte del fornitore. L'area di lavoro inoltre elenca gli ordini acquisto che la registrazione arrivi è stata eseguita per il magazzino, per garantire che l'entrata viene registrata. I resi dell'ordine fornitore che non sono stati ancora spediti sono inoltre disponibili per la revisione. | Il reparto acquisti trae giovamento nella panoramica dell'area di lavoro. Le informazioni rilevanti sono presentate per facilitare il follow-up e consentono di migliorare la produttività. |
| Inviare ordini fornitore per la conferma al portale fornitori ospitato nel client Dynamics AX. Lasciare il fornitore confermare o rifiutare. | Non supportato | L'interfaccia del portale fornitori consente ai fornitori di ricevere ordini fornitore che è possibile confermare o rifiutare. È inoltre possibile per il fornitore avere una panoramica di tutti gli ordini fornitore confermati in un conto. L'addetto acquisti può inviare un ordine fornitore che richiede una conferma dal fornitore. Il fornitore deve essere un utente Microsoft Azure Active Directory (Azure AD) registrato in Dynamics AX, un contatto per il fornitore e avere un ruolo di sicurezza dedicato. | Il reparto acquisti trae giovamento dalla riduzione del lavoro di burocrazia e dalla mancata necessità di tenere traccia delle risposte agli ordini fornitore, che sono immesse direttamente nel sistema. Avere un'origine di verità riduce i malintesi tra il cliente e il fornitore. |

## <a name="projects"></a>Progetti

| Operazioni che è possibile effettuare | Dynamics AX 2012 | Dynamics AX 7.0 | Perché questo è importante? |
|------------------|------------------|-----------------|------------------------|
| Prenotare lavoratori come risorse nei progetti. | Similmente alle risorse, i lavoratori sono prenotati direttamente nei progetti oltre alle risorse. | è ora possibile utilizzare la tabella del centro di lavoro in cui le risorse di produzione e produzione sono archiviate per prenotare i lavoratori come risorse in un progetto. | Quando prenotate i progetti, è necessario prenotare solo le risorse. |

## <a name="retail-sales-marketing-and-customer-service"></a>Vendite retail, marketing e servizio clienti

### <a name="retail-hq"></a>Retail HQ

Retail HQ ospitato da Microsoft Azure offre la gestione centralizzata e visibilità completa in tutti gli aspetti delle operazioni commerciali in un web client.

<table>
<thead>
<tr>
<th>Operazioni che è possibile effettuare</th>
<th>Dynamics AX 2012</th>
<th>Dynamics AX 7.0</th>
<th>Perché questo è importante?</th>
</tr>
</thead>
<tbody>
<tr>
<td>Non esegue operazioni di commercio.</td>
<td>Gli utenti devono accedere a diversi moduli per gestire i dati:
<ul>
<li>Gestione di categorie</li>
<li>Gestione prodotti</li>
<li>Attributi del prodotto del canale</li>
<li>Assortimenti</li>
<li>Gestione cataloghi</li>
<li>Kit</li>
<li>Prezzi e sconti</li>
</ul></td>
<td>L'area di lavoro <strong>Categoria e gestione del prodotto</strong> abilita le seguenti funzionalità:
<ul>
<li>Gestione dell'assortimento.</li>
<li>Traccia del ciclo di vita di assortimento.</li>
<li>Gestione prodotti rilasciati.</li>
</ul>
L'area di lavoro <strong>Gestione prezzi e sconti</strong> abilita le seguenti funzionalità:
<ul>
<li>Gestione prezzi e sconti per un canale e una categoria specificati.</li>
<li>Gestione regole prezzi di categoria.</li>
<li>Priorità di prezzi e sconti, che consentono di assegnare le priorità ai gruppi prezzi e agli sconti, in modo da poter definire l'ordine a cui vengono applicati.</li>
<li>Gestione affiliazione e sconti catalogo.</li>
</ul>
L'area di lavoro <strong>Gestione cataloghi</strong> abilita le seguenti funzionalità:
<ul>
<li>Riepilogo dei cataloghi attivi.</li>
<li>Traccia del ciclo di vita dei cataloghi in una unica ubicazione.</li>
</ul></td>
<td><ul>
<li>Le aree di lavoro aggiornamento delle ore e la produttività dei lavoratori lasciandoli centralmente merito alle attività e azioni correlati al ruolo di vendita.</li>
<li>La funzionalità di priorità di sconto prezzi fornisce a clienti più controllo su come i prezzi e gli sconti vengono utilizzati. La funzionalità abilita anche nuovi scenari in cui prezzi di negozio più alti vincono sui prezzi standard.</li>
</ul></td>
</tr>
<tr>
<td>Gestire le distribuzioni e le operazioni del canale di vendita al dettaglio.</td>
<td>L'utente deve accedere ai moduli e per effettuare le seguenti attività:
<ul>
<li>Creare e configurare nuovi canali e le entità correlate.</li>
<li>Gestire le attività giornaliere del negozio.</li>
<li>Elaborare le transazioni di vendita al dettaglio in Microsoft Dynamics AX, generare le istruzioni al dettaglio e aggiornare Microsoft Dynamics AX magazzino e finanziari.</li>
</ul>
</td>
<td>L'area di lavoro <strong>Distribuzione del canale</strong> consente di eseguire le attività seguenti:
<ul>
<li>Creare nuovi canali e le entità correlate„”.</li>
<li>Tenere traccia dello stato di avanzamento della configurazione del punto di vendita al dettaglio.</li>
<li>Intraprendere le azioni necessarie per completare un'attività, o immettere informazioni per completare l'attività.</li>
<li>Tenere traccia dello stato di dispositivi e direttamente convalidare e scaricare l'installazione del programma Retail Modern POS (MPOS) nei negozi.</li>
<li>Accedere a tutte le pagine correlate.</li>
</ul>L'area di lavoro 
<strong>Gestione punto venditaal dettaglio</strong> consente di eseguire le attività seguenti:
<ul>
<li>Gestire i lavoratori e le autorizzazioni di POS dei lavoratori.</li>
<li>Tenere traccia dello stato dello spostamento per un archivio specificato o il gruppo di archivi.</li>
<li>Direttamente convalidare e scaricare l'impostazione di programma di MPOS in archivi.</li>
<li>Stampare i report e nelle pagine correlate accesso.</li>
</ul>L'area di lavoro 
<strong>Dati finanziari punto vendita al dettaglio</strong> consente di eseguire le attività seguenti:
<ul>
<li>Creare, calcolare e registrare rendiconti per un dato canale.</li>
<li>Programmare i processi batch aggiornare le scorte e calcolare e registrare le istruzioni.</li>
<li>Tracciare i rendiconti aperti.</li>
<li>Tenere traccia dello stato dello spostamento per un archivio specificato o il gruppo di archivi.</li>
<li>Stampare i report e accedere rapidamente a tutte le pagine correlate.</li>
</ul></td>
<td>Le aree di lavoro aggiornamento delle ore e la produttività dei lavoratori lasciandoli centralmente merito alle attività e azioni correlati alla distribuzione canale, gestione negozio e finanza.</td>
</tr>
<tr>
<td>Gestisci operazioni IT vendita al dettaglio.</td>
<td>L'utente deve accedere a più moduli.</td>
<td>L'area di lavoro <strong>IT di vendita al dettaglio</strong> abilita le richieste di informazioni Commerce Data Exchange in un'unica posizione per un canale specificato, in modo che è possibile eseguire le attività seguenti:
<ul>
<li>Sessioni di download.</li>
<li>Sessioni di caricamento.</li>
<li>Tenere traccia delle sessioni non riuscite e il ri-avviarle o eseguirle ancora.</li>
<li>Visualizza o esegui processi imminenti.</li>
</ul></td>
<td>Le aree di lavoro migliorano l'efficienza e la produttività dei lavoratori lasciandoli gestire centralmente le attività e le azioni correlate alle operazioni IT di vendita al dettaglio.</td>
</tr>
<tr>
<td>Importare/esportare dati le entità di dati.</td>
<td>AX 2012 supporta la migrazione Microsoft Dynamics Retail Management System (RMS) predefinita tramite il framework di importazione/esportazione dati.</td>
<td>Le entità di dati al dettaglio sono state espanse per supportare tutti i dati master e di riferimento correlati a vendere al dettaglio. È inoltre disponibile supporto avanzato per le entità di dati nell'intera soluzione Dynamics AX.</td>
<td>Le entità di dati consentono ai clienti di effettuare l'importazione e l'esportazione guidate dai metadati. Le entità di OData consentono anch'esse ai clienti di integrare i clienti Dynamics AX con i programmi di terze parti.</td>
</tr>
<tr>
<td>Eseguire l'analisi dei dati intelligente utilizzando i report di BI da Dynamics Microsoft AX e il client POS.</td>
<td>Più di 25 report di back office e cinque report di canale sono disponibili.</td>
<td>Più di 30 report di back office e 10 report di canale sono disponibili.</td>
<td>Questi report danno ai clienti più BI per prevedere le tendenze, scoprire informazioni e operare sempre alle massime prestazioni.</td>
</tr>
<tr>
<td>Analisi dei dati di vendita del canale di vendita al dettaglio utilizzando il pacchetto di contenuti Power BI "Monitora Retail Channel Performance".</td>
<td>Non disponibile</td>
<td>Su PowerBI.com, selezionare <strong>Recupera i dati</strong> e quindi il pacchetto di contenuti <strong>Dynamics AX - Retail Channel Performance</strong>. Immettere l'url del endpoint di Dynamics AX per vedere i dati riflessi nel dashboard.</td>
<td>In tre o quattro clic, le organizzazioni possono distribuire il dashboard di Power BI contenente i dati finanziari importanti. Il contenuto può essere personalizzato dall'organizzazione. Inoltre, gli utenti possono incorporare i riquadri del dashboard di Power BI nelle aree di lavoro personalizzate in Dynamics AX, in modo che è quindi possibile visualizzare le informazioni analitiche a colpo d'occhio.</td>
</tr>
<tr>
<td>Configura autorizzazioni consumatore.</td>
<td>Non disponibile</td>
<td>I clienti possono scegliere se le operazioni POS possono essere disponibili per gli utenti. Il server al dettaglio utilizzano le autorizzazioni per le chiamate dell'interfaccia API.</td>
<td>Fornisce la capacità di configurazione delle autorizzazioni a livello utente.</td>
</tr>
<tr>
<td>Gestire e convalidare le configurazioni dell'entità.</td>
<td>Non disponibile</td>
<td>L'amministratore di configurazione e la funzionalità di validator abilita le seguenti funzionalità:
<ul>
<li>Caricamento bulk dei dati di configurazione</li>
<li>Convalida entità aziendali</li>
</ul></td>
<td>Fornisce la capacità di avviarsi la configurazione e di convalidare lo stato e la completezza di configurazione per i vari elementi di configurazione.</td>
</tr>
</tbody>
</table>

### <a name="retail-hardware-station"></a>Stazione hardware Retail

| Operazioni che è possibile effettuare | Dynamics AX 2012 | Dynamics AX 7.0 | Perché questo è importante? |
|------------------|------------------|-----------------|------------------------|
| Abilitare i dispositivi POS per connettersi alle unità periferiche ad esempio stampatrici, i cassetti della cassa, radio o di pagamento. | Il profilo hardware di MPOS viene utilizzato per specificare i dispositivi utilizzati. | Un profilo hardware aggiunto supporta il hardware più diverso da una postazione al successivo. Un nuovo profilo di postazione hardware supporta un terminale ID univoco per ogni postazione hardware quando le transazioni di (EFT) di bonifico vengono elaborate. Il supporto di EFT è stato fuso in postazione hardware per ridurre presenze di MPOS l'elaborazione di pagamento EFT. | Fornisce maggiore flessibilità per le implementazioni. Anche fornisce la sicurezza avanzata e l'esposizione riduttrice i dati della carta di credito. |

### <a name="retail-server-and-data-management"></a>Server al dettaglio e gestione dei dati

Il server al dettaglio e la gestione dei dati consente agli utenti e le imprese creare un esperienza di acquisto di omni-canale tra online, in-store e canali del call center.

<table>
<thead>
<tr>
<th>Operazioni che è possibile effettuare</th>
<th>Dynamics AX 2012</th>
<th>Dynamics AX 7.0</th>
<th>Perché questo è importante?</th>
</tr>
</thead>
<tbody>
<tr>
<td>Eseguire la connessione al database Commerce Runtime (CRT) che archivia i dati aziendali per il canale utilizzando i servizi CRT.</td>
<td>OData V3 è supportato.</td>
<td>OData V4 è supportato.</td>
<td>Consente al cliente di restare aggiornato con gli standard di OData. Crea inoltre un'esperienza affidabile omni-canale con integrazione delle vendite a livello di in-store, mobile e canali online.</td>
</tr>
<tr>
<td>Media servizi a dettaglio come set hostable servizi.</td>
<td>Il commercio API elettronico non è supportato tramite il server al dettaglio.</td>
<td>Il commercio API elettronico è ora disponibile attraverso server al dettaglio diretto per supportare gli scenari online.</td>
<td>Fornisce servizi ospitati e evolutivi di commercio elettronico che possono essere utilizzati con i negozi online di terze parti.</td>
</tr>
<tr>
<td>Spostare i dati tra il back office di Microsoft Dynamics AX e i canali utilizzando Commerce Data Exchange.</td>
<td>Commerce Data Exchange è un sistema per trasferire i dati tra Microsoft Dynamics AX e canali di vendita al dettaglio, ad esempio i negozi online o i passaggi vendita fisici. Per ulteriori informazioni, vedere <a href="https://technet.microsoft.com/library/dn741440.aspx">Commerce Data Exchange [AX 2012]</a>.</td>
<td>È parità funzionale a Microsoft Dynamics AX 2012 CU8. Considerare però i seguenti dettagli:
<ul>
<li>Commerce Data Exchange è stato ricostruito per il cloud.</li>
<li>Il servizio di Async usa l'accesso al database diretto al database del canale.</li>
<li>Commerce Data Exchange: Il servizio in tempo reale è ospitato come servizio personalizzato di Microsoft Dynamics AX.</li>
<li>MPOS gestisce la sincronizzazione tra i database offline e il server di vendita al dettaglio.</li>
</ul></td>
<td>Commerce Data Exchange è stato ricostruito per il cloud. Continua a gestire il trasferimento i dati tra Microsoft Dynamics AX e canali di vendita al dettaglio, ad esempio i negozi online o i passaggi vendita fisici.</td>
</tr>
<tr>
<td>Supporta l'elaborazione del pagamento multicanale semintegrata plug and play utilizzando l'SDK di pagamento.</td>
<td>AX 2012 fornisce le seguenti funzionalità:
<ul>
<li>Supporto per tutti i canali: POS, e-commercio e call center.</li>
<li>Supporto per scheda presente e scheda non presente.</li>
<li>Pagina per l'accettazione di pagamento.</li>
<li>Supporto periferico a LS5300 e a MX925 come codice di esempio in Retail SDK.</li>
</ul></td>
<td>La versione corrente di Dynamics AX supporta qualsiasi Microsoft Dynamics AX for Retail 2012 esistente per le funzionalità di credito/debito e quattro nuovi miglioramenti.</td>
<td>Consente al cliente di eseguire transazioni di credito/debito per i pagamenti.</td>
</tr>
<tr>
<td>Attivare i dispositivi utilizzando un account Microsoft (Microsoft Azure Active Directory (Azure AD)).</td>
<td>Non disponibile</td>
<td>Sono fornite le seguenti funzionalità:
<ul>
<li>Sicurezza avanzata in base all'attivazione basata su Azure AD per aggiungere il cloud.</li>
<li>Sicurezza avanzata per la gestione dei token.</li>
<li>Affidabilità, risoluzione dei problemi e messaggistica di errore migliori durante l'attivazione</li>
<li>Attività di amministrazione IT semplificate correlate all'attivazione.</li>
<li>Modello di rischio rivisitato e problemi di sicurezza corretti.</li>
</ul></td>
<td>Sono disponibili i seguenti benefit:
<ul>
<li>La sicurezza viene migliorata tramite Azure AD e token/ID dispositivo (chiamate di RS che utilizzano un token, archiviazione di app specifica per l'utente).</li>
<li>Interrompe l'utilizzo remoto non autorizzato di MPOS (dispositivo di mattone).</li>
<li>Tiene traccia dei dispositivi MPOS per scopi di conformità PCI.</li>
<li>Esegue il mapping di dispositivi fisici a un'entità aziendali (registro) utilizzando un token della periferica.</li>
<li>Inizializza le impostazioni relative a funzionalità di rettificare MPOS (sequenze numeriche e profili hardware) del primo punto di tocco di MPOS.</li>
<li>Riferimento le informazioni della periferica dalle sedi.</li>
</ul></td>
</tr>
<tr>
<td>Gestire il contenuto dettagliato di media per creare e servire tramite la raccolta di media.</td>
<td>Non disponibile</td>
<td><ul>
<li>Supportare il caricamento di immagini e anche visualizzare, gestire e eliminare, dalla galleria multimediale, sia per le immagini ospitate esternamente che per le immagini ospitate da Retail.</li>
<li>Supportare caricamento e visualizzazione di immagini dalle pagine di entità (<strong>Prodotti</strong>, <strong>Cataloghi</strong>, e così via) collegando un'immagine dalla galleria e caricando un'immagine dal desktop.</li>
<li>Ottimizzare le immagini di anteprima, la dimensione personalizzata e l'originale.</li>
<li>Ammassano le entità di collegamento utilizzando un modello e i processi in background per l'associazione di stoccaggio.</li>
<li>L'integrazione di Microsoft Excel sovrascrive la limitazione del gruppo di attributi delle convenzioni di denominazione e i percorsi predefiniti.</li>
<li>Supporta le immagini offline e le immagini sicure per il contenuto di personalmente identificabile (PII) di informazioni, ad esempio immagini di Vendita a dettaglio- ospitate cliente e dipendenti.</li>
</ul></td>
<td><ul>
<li>Gestisce le criticità relative alle immagini esternamente ospitate, in modo da evitare di andare avanti e indietro e invece gestire in un'unica posizione.</li>
<li>Fornisce la gestione dei contenuti potente tramite la galleria multimediale per le immagini caricate e esternamente ospitate e inoltre fornisce il filtro per individuare le immagini.</li>
<li>Consente di semplicemente creare associazioni in blocco tra le immagini esternamente ospitate e le entità, ad esempio prodotti e cataloghi.</li>
<li>Supporta di immagazzinamento Vendita al dettaglio- ospitata per le immagini e l'integrazione di Excel per gli aggiornamenti facili.</li>
</ul></td>
</tr>
</tbody>
</table>

### <a name="rich-clientele-experience"></a>Esperienza dettagliata del cliente

Esperienze immersive di cellulare di offerte di vendita al dettaglio un punto qualsiasi momento, qualsiasi e in qualsiasi periferica. Questa funzionalità abilita le esperienze avanzate archivio e di acquisto tra tutti i canali.

<table>
<thead>
<tr>
<th>Operazioni che è possibile effettuare</th>
<th>Dynamics AX 2012</th>
<th>Dynamics AX 7.0</th>
<th>Perché questo è importante?</th>
</tr>
</thead>
<tbody>
<tr>
<td>Ricerca, spostarsi ricerca, o digitalizzi i prodotti, aggiungere prodotti al carrello, accettare il pagamento e verificare utilizzando un'utente intuitiva, tocco- semplice da usare, dettagliata e immersive in MPOS.</td>
<td>AX 2012 abilita le seguenti funzionalità:
<ul>
<li>Eseguire le vendite, i resi e le annullata.</li>
<li>Creare, modificare e prendere gli ordini cliente.</li>
<li>Fare clic su Esegui un'operazione non relativa al cassetto.</li>
<li>Prelievo e ricevere gli ordini e eseguire i conteggi predefiniti.</li>
<li>Visualizzare report di tipo in-store.</li>
</ul></td>
<td>La parità funzionale con AX 2012 MPOS è specificata. In questo campo sono incluse le seguenti funzioni:
<ul>
<li>Ricerca del cliente tra punti vendita/canali.</li>
<li>La possibilità di creare ordini cliente senza accedere a Real-time Service.</li>
<li>Flussi di lavoro, stato e messaggi di errore di attivazione dispositivi migliorati.</li>
<li>Miglioramenti di estensibilità, ad esempio i trigger pre-registrazioned e supporto di attività per aggiornare la personalizzazione.</li>
</ul></td>
<td>Il personale di vendita possono elaborare le transazioni di vendita e ordini cliente e esegue i funzionamenti e la gestione articoli quotidiani, utilizzando i dispositivi mobili un punto qualsiasi nell'archivio.</td>
</tr>
<tr>
<td>Posizione iniziale come applicazione web tramite la posizione del cloud.</td>
<td>Non disponibile</td>
<td>La parità funzionale con MPOS è specificata. In questo campo sono incluse le seguenti funzioni:
<ul>
<li>Attivazione dispositivo con AAD</li>
<li>Design layout responsivo</li>
<li>Supporto per i browser Edge, Internet Explorer e Chrome.</li>
</ul></td>
<td>Fornisce una posizione di applicazione web con funzionalità che viene compatibile a MPOS che può essere utilizzato tra le piattaforme e i browser a alcun costo di distribuzione.</td>
</tr>
<tr>
<td>Integrazione con i sistemi di gestione dei contenuti per creare un sito Web e-Commerce omnicanale.</td>
<td>Microsoft SharePoint e le stanze frontali di negozio di terze parti sono supportati.</td>
<td>Una piattaforma e-Commerce viene fornita che supporta negozi di terze parti. Nella piattaforma sono incluse le seguenti funzionalità:
<ul>
<li>Un API utente completa.</li>
<li>Integrazione di autenticazione con qualsiasi fornitore OpenID di terze parti</li>
<li>Integrazione di pagamento.</li>
</ul></td>
<td>I clienti ora hanno la flessibilità di utilizzare il sistema di gestione dei contenuti delle prelievo.</td>
</tr>
<tr>
<td>Clienti di destinazione tramite i cataloghi di acquisto per corrispondenza e transazioni aggiornate tramite la registrazione ordine veloce, le vendite assistite e l'evasione utilizzando call center.</td>
<td><ul>
<li>Canale servizio clienti</li>
<li>Cataloghi di acquisto per corrispondenza</li>
<li>Registrazione ordine veloce e marketing assistita</li>
<li>Riempimento ordine migliorata</li>
<li>Servizio clienti</li>
<li>Valutazione e promozioni/sconti integrato</li>
</ul></td>
<td>La parità della capacità alla soluzione 2012 della call center di AX è disponibile, a eccezione della sostituzione dei prezzi.</td>
<td>Le call center a un tipo di canale di vendita al dettaglio che consente i lavoratori eseguire gli ordini dai clienti sul telefono e creare ordini cliente.</td>
</tr>
</tbody>
</table>

### <a name="commerce-essentials"></a>Elementi fondamentali del commercio

Una vendita al dettaglio e consente commercio- concentrate di opzione di configurazione aggiornamento le distribuzioni di vendita a dettaglio.

| Operazioni che è possibile effettuare | Dynamics AX 2012 | Dynamics AX 7.0 | Perché questo è importante? |
|------------------|------------------|-----------------|------------------------|
| Utilizzare il dashboard commerciale dei concetti di base. | Una pagina area ai collegamenti alle voci di menu è disponibile. | Il dashboard commerciale dei concetti di base fornisce collegamenti a frequenti attività, inclusi i collegamenti alle aree di lavoro, il controllo web di Power BI, i preferiti, pagine recenti ed elementi di lavoro correnti. | Il dashboard avanzato autorizzare i lavoratori rendendoli più efficienti e immettendo un punto di partenza flessibile per qualsiasi attività di vendita a dettaglio- specifica. |
| Entità di dati utilizzo delle modifiche di account di accesso. | Le modifiche al conto vengono esportate in una cartella del file system. | Le modifiche al conto sono accessibili tramite le entità di dati. | Questa funzionalità offre la maggiore flessibilità quando si sposta i dati tra i sistemi disparati. Questa funzionalità è possibile migliorata mediante applicazioni di OData, anche. |
| Posizione cloud e MPOS di utilizzo. | Solo la posizione aziendale (EPOS) in uscita de casella di media. | MPOS e la posizione del cloud sostituiscono il client di EPOS. Il canale e-Commerce vengono è stato aggiunto a Elementi fondamentali del commercio per impostazione predefinita. | Questa funzionalità abilita il supporto di del canale di uscita de casella ai client rapidamente schierabili del punto di vendita. |
| Attuazione e gestire architettura a due livelli. | Il framework di importazione/esportazione dei dati fornisce la capacità di spostare i dati tra AX 2012 e i sistemi di terze parti. | Entità di dati create per aggiornare contribuzione all'architettura a due stadi. | Le domande di lavoro OData e le entità di dati forniscono un livello di astrazione per rendere gli scenari a due stadi più facili implementare e gestire. |
| Semplifichi i moduli. | Il codice personalizzato è necessario per semplificare l'interfaccia utente. | Le estensioni di menu e del modulo immettere la semplificazione standardizzata di interfaccia utente. | Questa funzionalità offre una modalità più veloce e più semplice ottimizzare i moduli in base a esigenze del rivenditore. |

### <a name="pos-task-recorder"></a>Registrazione attività POS

<table>
<thead>
<tr>
<th>Operazioni che è possibile effettuare</th>
<th>Dynamics AX 2012</th>
<th>Dynamics AX 7.0</th>
<th>Perché questo è importante?</th>
</tr>
</thead>
<tbody>
<tr>
<td>Creare e condivida consente i documenti di attività per la posizione moderna.</td>
<td>Non disponibile</td>
<td>Il registrazione attività di MPOS supporta le seguenti funzionalità:
<ul>
<li>Creare registrazioni di attività per varie attività da eseguire in MPOS.</li>
<li>Generare un documento che include i passaggi e le schermate e associarlo con un nodo nel modello del processo aziendale.</li>
</ul></td>
<td>I partner e i fornitori software indipendente (ISVs) possono personalizzare MPOS e immettere i documenti di supporto per formare i propri utenti.</td>
</tr>
</tbody>
</table>

### <a name="extensibility"></a>Estendibilità

<table>
<thead>
<tr>
<th>Operazioni che è possibile effettuare</th>
<th>Dynamics AX 2012</th>
<th>Dynamics AX 7.0</th>
<th>Perché questo è importante?</th>
</tr>
</thead>
<tbody>
<tr>
<td>Supporto ai componenti Retail estendibili e facilmente distribuibili a HQ, call center, e-Commerce e POS.</td>
<td>I componenti possono essere estese utilizzando la vendita al dettaglio SDK. Alcuna funzionalità di distribuzione e comprimere è supportata.</td>
<td>I hook di Extensibility vengono aggiornati tra le varie componenti per aggiornare la isolamento e l'utilità del codice di supporto. Di seguito sono indicate alcune funzionalità incluse:
<ul>
<li>Flusso di lavoro, attività e operazione.</li>
<li>Trigger preliminari e successivi che consentono di facilmente estendere un flusso di lavoro.</li>
<li>Trigger di applicazione e operazione.</li>
</ul>
Inoltre, un framework è disponibile che consente di sviluppare e pacchettizzare tali componenti utilizzando MSBuild quindi in modo integrato distribuire la personalizzazione tramite Microsoft Dynamics Lifecycle Services (LCS).</td>
<td>I rivenditori hanno requisiti molto specifici, in base a verticali e geografie dell'operazione. Immettendo una semplice piattaforma estendibile, abilitiamo l'utilizzo tra più verticali e i mercati. Poiché la vendita al dettaglio e nell'architettura molto distribuita, la capacità senza cuciture di distribuire notevolmente migliora la produttività.</td>
</tr>
</tbody>
</table>

### <a name="lifecycle-management"></a>Gestione ciclo di vita

Lifecycle Services (LCS) fornisce un set di servizi che clienti e partner possono utilizzare per gestire il ciclo di vita di sistema dall'iscrizione alle operazioni giornaliere.

<table>
<thead>
<tr>
<th>Operazioni che è possibile effettuare</th>
<th>Dynamics AX 2012</th>
<th>Dynamics AX 7.0</th>
<th>Perché questo è importante?</th>
</tr>
</thead>
<tbody>
<tr>
<td>Gestire il programma tramite servizi cloud di distribuzione.</td>
<td>Non disponibile</td>
<td>Le seguenti topologie possono essere implementate nel cloud:
<ul>
<li>Topologia di prova retail 1-box</li>
<li>Topologia retail multi-box ad alta disponibilità.</li>
<li>Topologia di sviluppo con Retail SDK.</li>
</ul>
Presenza di installazione migliore del componente client "a tocco" tramite l'impostazione self service:
<ul>
<li>Retail Modern POS.</li>
<li>Stazione hardware Retail</li>
<li>Supporto per il caricamento e la distribuzione di pacchetti personalizzati tramite l'installazione self service</li>
</ul></td>
<td>Servizi cloud di distribuzione forniscono i benefit seguenti:
<ul>
<li>Impegno e complessità di distribuzione significativamente ridotti per i componenti Retail HQ.</li>
<li>Distribuzione nativa al cloud pubblico di Microsoft Azure.</li>
<li>Migliore installazione self service dei componenti in-store per una configurazione più semplice e intuitiva</li>
</ul></td>
</tr>
<tr>
<td>Monitorare le integrità del sistema e diagnostichi errori e le uscite.</td>
<td>Questa funzionalità richiede <a href="https://www.microsoft.com/download/details.aspx?id=42636">System Center 2012 Management Pack per Microsoft Dynamics AX 2012 R3 CU8 Retail</a>.</td>
<td>Il monitoraggio e la diagnostica per i componenti al dettaglio è ora disponibili tramite <strong>Comprensioni operative</strong> il dashboard in LC.</td>
<td><strong>Comprensioni operative</strong> Il dashboard è in un portale basato su cloud del monitoraggio che sostituiscono la necessità di impostare l'infrastruttura di System Center Operations Manager (SCOM).</td>
</tr>
<tr>
<td>Creare, configurare, scaricare e impostare la postazione al dettaglio e i dispositivi hardware tramite il portale self service.</td>
<td>Utilizzando la imballatore e Enterprise Portal di impostazione, un utente può eseguire di installazione e una configurazione automatizzate di tutti i componenti necessarie in un computer specifico, in base alla topologia definita.</td>
<td>Poiché sono disponibili solo due colli di impostazione, uno per il client di MPOS e altre per il componente al dettaglio di postazione hardware, self service è ridotto l'importo di lavoro richiesto a ogni livello di impostare tali componenti client.</td>
<td>Il self service mira a ridurre i requisiti e apportare più facili per un utente di eseguire l'installazione.</td>
</tr>
</tbody>
</table>

## <a name="sales"></a>Vendite

<table>
<thead>
<tr>
<th>Operazioni che è possibile effettuare</th>
<th>Dynamics AX 2012</th>
<th>Dynamics AX 7.0</th>
<th>Perché questo è importante?</th>
</tr>
</thead>
<tbody>
<tr>
<td>Recupera una breve panoramica di alternative di consegna quando promettete gli ordini clienti.</td>
<td>Quando è presente di vincoli del prodotto disponibilità e la data di consegna richiesta dal cliente per uno o più prodotti nell'ordine non può essere soddisfatta, l'attività di promessa di ordine diventa una sfida. Per cercare le alternative che è possibile compensare la disponibilità e tempo di trasporto rilascia in modo dalla data richiesta in grado di soddisfare cliente, o per offrire a clienti una soluzione di consegna di che possono accettare e fidarsi, il processore di ordine può essere necessario aprire diversi moduli, ciascuna delle quali offre solo un sottoinsieme delle informazioni richieste. Più in modo specifico, un modulo indica la quantità disponibile tra siti, un altro modulo indica la quantità disponibile nell'impostazione interaziendale, un terzo modulo consente agli utenti di calcolare la data disponibile precedente per un sito/varianti per volta e scorte disponibili quarte di un modulo per fornire gli ordini. Di conseguenza, gli utenti non ritengono quelle con determinati considerate tutte le opzioni rilevanti anziché appena di scegliere una soluzione immediata ma suboptimale. Gli utenti e non ritengono effettive, poiché le esegue di numerose si verificano durante il flusso di promessa di ordine aperte e chiuse le pagine di e combinate le comprensioni e opzioni.</td>
<td>In base degli algoritmi esistenti per il calcolo della data di consegna, <strong>Alternative di consegna </strong>la pagina offre una nuovautente per la promessa di ordine:
<ul>
<li>Consolida il informazioni rilevanti i moduli più di uno spazio.</li>
<li>Offre pacchetti di "pronta consegna" alternativi, ad esempio una combinazione delle modalità di sito/magazzino/variante/trasporto, in base al criterio di consegna più veloce (prima data disponibile) che l'utente può scegliere.</li>
<li>Consente di selezionare opzioni utente dall'interfaccia di simulazione e le trasferire nella riga ordine cliente.</li>
</ul></td>
<td>Le società che aspirano immettere il servizio di assistenza clienti più quando eseguono il commit a una strategia di ottimizzazione di scorte è possibile promettere gli ordini in maniera affidabile e in modo competitivo. Dopo tutto, l'attività dei loro clienti esige che i prodotti siano disponibili in tempo. <strong>Alternative di consegna</strong> La pagina attività sull'attività di promessa di ordine più rapidamente, il più semplice e più sistematico identificando e consigliando migliori le date di consegna alternative di ordine in una posizione interattivo.</td>
</tr>
</tbody>
</table>

## <a name="service-management"></a>Gestione assistenza

Non sono state aggiunte nuove funzionalità.

## <a name="transportation-management"></a>Gestione trasporto

Non sono state aggiunte nuove funzionalità.

## <a name="travel-and-expense"></a>Viaggi e spese

Non sono state aggiunte nuove funzionalità.

## <a name="warehouse-management"></a>Gestione magazzino

| Operazioni che è possibile effettuare | Dynamics AX 2012 | Dynamics AX 7.0 | Perché questo è importante? |
|------------------|------------------|-----------------|------------------------|
| Download, installare e configurare il programma di installazione per il portale dei dispositivi mobili del magazzino. | È possibile scaricare, impostare e configurare il portale durante il processo di installazione di Microsoft Dynamics AX, mediante un'impostazione standard. È progettato per i semoventi locali di distribuzione e configurazione. | È possibile scaricare un programma di installazione autonomo tramite una voce di menu in gestione magazzino. È progettato per i semoventi locali di distribuzione e configurazione. | Quando state impostando la funzionalità del dispositivo mobile, è necessario installare e configurare il portale dei dispositivi mobili del magazzino in locale e ottenere una connessione a Dynamics AX nel cloud. |

## <a name="additional-resources"></a>Risorse aggiuntive

[Novità o modifiche](whats-new-changed.md)

[Nuove Guide attività disponibili (febbraio 2016)](new-task-guides-available-february-2016.md)
