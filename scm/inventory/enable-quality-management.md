---
title: "Panoramica sulla gestione della qualità"
description: "In questo articolo viene descritto come utilizzare la gestione della qualità in Microsoft Dynamics 365 for Finance and Operations per migliorare la qualità del prodotto all'interno della supply chain."
author: perlynne
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventTestAssociationTable, InventTestGroup, InventTestItemQualityGroup, InventTestTable, InventTestVariable, InventTestVariableOutcome
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 08c38aada355583c5a6872f75b57db95d9b81786
ms.openlocfilehash: c2c7a9c82809bd989eb362995dfe8e6d7829e89d
ms.contentlocale: it-it
ms.lasthandoff: 07/27/2017

---

# <a name="quality-management-overview"></a>Panoramica sulla gestione della qualità

[!include[banner](../includes/banner.md)]


In questo articolo viene descritto come utilizzare la gestione della qualità in Microsoft Dynamics 365 for Finance and Operations per migliorare la qualità del prodotto all'interno della supply chain.

La gestione della qualità può favorire la gestione dei tempi di completamento quando ci si occupa di prodotti non conformi, indipendentemente dal punto di origine dei prodotti. Poiché i tipi di diagnostica sono collegati alla dichiarazione di correzione, Microsoft Dynamics 365 for Finance and Operations consente di programmare le attività per correggere i problemi e impedire che si ripetano.

Oltre alla funzionalità per gestire la non conformità, la gestione della qualità include la funzionalità per tenere traccia dei problemi in base al tipo (anche i problemi interni) e per l'identificazione di soluzioni a breve termine o a lungo termine. Le statistiche relative agli indicatori di prestazioni chiave (KPI) forniscono un'analisi dei problemi di non conformità che si sono precedentemente verificati e le soluzioni applicate per correggerli. È possibile utilizzare i dati storici per analizzare l'efficienza delle misure di qualità che sono state adottate in precedenza e determinare le misure appropriate in futuro.

Quando si imposta un'associazione di controllo qualità, Finance and Operations può generare ordini di controllo qualità per diversi processi aziendali, eventi e condizioni. L'associazione di controllo qualità può coprire un articolo specifico, un determinato gruppo di articoli oppure tutti gli articoli.

## <a name="examples-of-the-use-of-quality-management"></a>Esempi di utilizzo di gestione della qualità
La gestione della qualità è flessibile e può essere implementata in vari modi per soddisfare i requisiti di livelli specifici di operazioni della catena di fornitura. Nei seguenti esempi viene illustrato i possibili usi di queste funzionalità:

-   Consente di avviare un processo di controllo qualità in base a criteri predefiniti (al momento della registrazione in magazzino di un ordine acquisto di un fornitore specifico).
-   Consente di bloccare l'inventario durante l'ispezione per impedire che venga utilizzato un magazzino non approvato (blocco completo di quantità degli ordini acquisto).
-   Utilizzare il campionamento articoli come parte di un'associazione di qualità per definire l'importo di inventario fisico corrente che deve essere controllato. Il campionamento può basarsi su quantità fisse o una percentuale.
-   Creare ordini di controllo qualità per le entrate parziali. Per creare un ordine di controllo qualità basato sulla quantità che viene fisicamente ricevuta con un ordine, è necessario selezionare la casella di controllo **Per quantità aggiornata** nel modulo **Campionamento articoli**.
-   Consente di creare i tipi di test che includono i valori di test minimi, massimi e di destinazione e di eseguire il test qualitativo-contro-quantitativo con i risultati di convalida predefiniti.
-   Specificare un livello di qualità accettabile (AQL) per controllare le tolleranze di misura di qualità.
-   Specificare le risorse che un'operazione di ispezione richiede, ad esempio area di test e strumenti di test.

## <a name="working-with-quality-associations"></a>Utilizzo delle associazioni di controllo qualità
Il processo aziendale che utilizza un'associazione di controllo qualità può essere correlato a diversi documenti di origine come ordini acquisto, ordini cliente o ordini di produzione.

Ciascun record di associazione di controllo qualità definisce il set di test, l'AQL e il piano di campionamento da applicare agli ordini di controllo qualità generati. Un record di un'associazione di controllo qualità deve essere definito per ogni variazione in un processo aziendale. Ad esempio, è possibile impostare un'associazione di controllo qualità che generi un ordine di controllo qualità quando si aggiorna l'entrata prodotti di un ordine acquisto. A seconda dell'impostazione del piano di esecuzione, il processo di attivazione stesso può essere bloccato quando è presente un ordine di controllo qualità aperto, o i processi seguenti, ad esempio la fatturazone di un ordine fornitore, possono essere bloccati.

**Nota:** Mentre vi sono ordini di controllo qualità aperti, le quantità di inventario sono automaticamente bloccate. A seconda dell'impostazione di **Blocco completo** nella pagina **Campionamenti articolo**, la quantità è la quantità dell'ordine di controllo qualità o la quantità della riga di documento di origine.

Per un processo aziendale specificato, il record di un'associazione di controllo qualità identifica l'evento e le condizioni per cui viene generato un ordine di controllo qualità. Le condizioni possono essere specifiche a un sito o a una persona giuridica. Un ordine di controllo qualità che prevede test distruttivi può essere generato solo quando sono disponibili delle scorte per l'evento.

Negli esempi riportati di seguito viene illustrata la modalità di definizione di un record di associazione di controllo qualità per le variazioni in ciascun processo aziendale. Per ciascun esempio, sono riepilogati nella seguente tabella gli eventi e le condizioni definiti da un record di associazione di controllo qualità.

<table>
<tbody>
<tr>
<th>Tipo di riferimento</th>
<th>Tipo di evento</th>
<th>Esecuzione</th>
<th>Bloccaggio evento</th>
<th>Riferimento documento</th>
</tr>
<tr>
<td>Inventario</td>
<td>Non applicabile</td>
<td>Non applicabile</td>
<td>Nessuno</td>
<td>Tutti</td>
</tr>
<tr>
<td rowspan="7">Vendite</td>
<td rowspan="4">Il processo di prelievo è programmato</td>
<td rowspan="4">Prima</td>
<td>Nessuno</td>
<td rowspan="22">Solo ID specifico, Gruppo o Tutto</td>
</tr>
<tr>
<td>Processo di prelievo</td>
</tr>
<tr>
<td>Documento di trasporto</td>
</tr>
<tr>
<td>Fattura</td>
</tr>
<tr>
<td rowspan="3">Documento di trasporto</td>
<td rowspan="3">Prima</td>
<td>Nessuno</td>
</tr>
<tr>
<td>Documento di trasporto</td>
</tr>
<tr>
<td>Fattura</td>
</tr>
<tr>
<td rowspan="15">Acquisto</td>
<td rowspan="7">Elenco entrate</td>
<td rowspan="4">Prima</td>
<td>Nessuno</td>
</tr>
<tr>
<td>Elenco entrate</td>
</tr>
<tr>
<td>Entrata prodotti</td>
</tr>
<tr>
<td>Fattura</td>
</tr>
<tr>
<td rowspan="3">Dopo</td>
<td>Nessuno</td>
</tr>
<tr>
<td>Entrata prodotti</td>
</tr>
<tr>
<td>Fattura</td>
</tr>
<tr>
<td rowspan="3">Registrazione</td>
<td rowspan="3">Non applicabile</td>
<td>Nessuno</td>
</tr>
<tr>
<td>Entrata prodotti</td>
</tr>
<tr>
<td>Fattura</td>
</tr>
<tr>
<td rowspan="5">Entrata prodotti</td>
<td rowspan="3">Prima</td>
<td>Nessuno</td>
</tr>
<tr>
<td>Entrata prodotti</td>
</tr>
<tr>
<td>Fattura</td>
</tr>
<tr>
<td rowspan="2">Dopo</td>
<td>Nessuno</td>
</tr>
<tr>
<td>Fattura</td>
</tr>
<tr>
<td rowspan="8">Produzione</td>
<td rowspan="3">Registrazione</td>
<td rowspan="3">Non applicabile</td>
<td>Nessuno</td>
<td rowspan="12">Tutti</td>
</tr>
<tr>
<td>Dichiarato finito</td>
</tr>
<tr>
<td>Fine periodo</td>
</tr>
<tr>
<td rowspan="5">Dichiarato finito</td>
<td rowspan="3">Prima</td>
<td>Nessuno</td>
</tr>
<tr>
<td>Dichiarato finito</td>
</tr>
<tr>
<td>Fine periodo</td>
</tr>
<tr>
<td rowspan="2">Dopo</td>
<td>Nessuno</td>
</tr>
<tr>
<td>Fine periodo</td>
</tr>
<tr>
<td rowspan="4">Quarantena</td>
<td rowspan="3">Dichiarato finito</td>
<td rowspan="2">Prima</td>
<td>Dichiarato finito</td>
</tr>
<tr>
<td>Fine periodo</td>
</tr>
<tr>
<td>Dopo</td>
<td>Fine periodo</td>
</tr>
<tr>
<td>Fine periodo</td>
<td>Prima</td>
<td>Fine periodo</td>
</tr>
<tr>
<td rowspan="3">Operazione ciclo di lavorazione</td>
<td rowspan="3">Dichiarato finito</td>
<td rowspan="2">Prima</td>
<td>Nessuno</td>
<td rowspan="3">ID specifico, Gruppo o Tutti e Specifico risorsa, Gruppo o Tutti</td>
</tr>
<tr>
<td>Dichiarato finito</td>
</tr>
<tr>
<td>Dopo</td>
<td>Nessuno</td>
</tr>
<tr>
<td rowspan="3">Produzione co-prodotti</td>
<td>Registrazione</td>
<td>Non applicabile</td>
<td rowspan="3">Nessuno</td>
<td rowspan="3">Tutti</td>
</tr>
<tr>
<td rowspan="2">Dichiarato finito</td>
<td>Prima</td>
</tr>
<tr>
<td>Dopo</td>
</tr>
</tbody>
</table>

Nella tabella seguente vengono fornite ulteriori informazioni sulla modalità di generazione di ordini di controllo qualità per tipi specifici di processo.
<div class="tableSection">

<table>
<tbody>
<tr>
<th>Tipo di processo</th>
<th>Quando gli ordini di controllo qualità possono essere generati automaticamente</th>
<th>Quando gli ordini di controllo qualità possono essere generati se il test distruttivo è obbligatorio</th>
<th>Informazioni sulle condizioni</th>
<th>Informazioni sulla generazione manuale</th>
</tr>
<tr>
<td>Ordine fornitore</td>
<td>Prima o dopo la registrazione di un elenco di entrate o un'entrata prodotti per il materiale ricevuta</td>
<td>Dopo che l'entrata prodotti per il materiale ricevuto viene registrata, poiché il materiale deve essere disponibile per il test distruttivo</td>
<td>La richiesta di un ordine di controllo qualità può riflettere un sito, un articolo o un fornitore specifico o una combinazione di questi.</td>
<td>Un ordine di controllo qualità generato manualmente che si riferisce a un ordine fornitore può utilizzare le informazioni in un record di un'associazione di controllo qualità, ad esempio il piano di campionamento di test.</td>
</tr>
<tr>
<td>Ordine di quarantena</td>
<td>Prima o dopo che l'ordine di quarantena viene dichiarato finito o completato</td>
<td>Gli ordini di controllo qualità che richiedono i test distruttivi non possono essere generati. Si presume che la funzionalità di ordine di quarantena gestisca lo smaltimento del materiale distrutto.</td>
<td>La richiesta di un ordine di controllo qualità può riflettere un sito, un articolo o un fornitore specifico o una combinazione di questi.</td>
<td>Un ordine di controllo qualità generato manualmente che si riferisce a un ordine di quarantena può utilizzare le informazioni in un record di un'associazione di controllo qualità, ad esempio il piano di campionamento di test.</td>
</tr>
<tr>
<td>Ordine cliente</td>
<td>Prima di un processo di prelievo o un aggiornamento del documento di trasporto per gli articoli in spedizione</td>
<td>In qualsiasi fase</td>
<td>La richiesta di un ordine di controllo qualità può riflettere un sito, un articolo o un cliente specifico o una combinazione di questi.</td>
<td>Un ordine di controllo qualità generato manualmente che si riferisce a un ordine cliente può utilizzare le informazioni in un record di un'associazione di controllo qualità, ad esempio il piano di campionamento di test.</td>
</tr>
<tr>
<td>Ordine di produzione</td>
<td>Prima o dopo la registrazione della quantità finita per l'ordine di produzione</td>
<td>Dopo la registrazione della quantità finita per l'ordine di produzione</td>
<td>La richiesta di un ordine di controllo qualità può riflettere un sito o un articolo specifico o una combinazione di questi.</td>
<td>Un ordine di controllo qualità generato manualmente che si riferisce a un ordine di produzione può utilizzare le informazioni in un record di un'associazione di controllo qualità, ad esempio il piano di campionamento di test.</td>
</tr>
<tr>
<td>Ordine di produzione che ha un'operazione del ciclo di lavorazione</td>
<td>Prima o dopo che il report venga completato per un'operazione</td>
<td>Dopo la dichiarazione della fine dell'ultima operazione di produzione</td>
<td>La richiesta di un ordine di controllo qualità può riflettere un sito, un articolo o una risorsa operativa specifica o una combinazione di questi elementi.</td>
<td>Un ordine di controllo qualità generato manualmente che si riferisce a un'operazione del ciclo di lavorazione può utilizzare le informazioni in un record di un'associazione di controllo qualità, ad esempio il piano di campionamento di test.</td>
</tr>
<tr>
<td>Inventario</td>
<td>Un ordine di controllo qualità non può essere generato automaticamente per una transazione in un giornale di registrazione magazzino o per le transazioni degli ordini di trasferimento.</td>
<td></td>
<td></td>
<td>Un ordine di controllo qualità deve essere creato manualmente per la quantità in magazzino di un articolo. Scorte fisiche disponibili è un campo obbligatorio.</td>
</tr>
</tbody>
</table>

## <a name="quality-management-pages"></a>Pagine sulla gestione qualità
<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>Pagina</th>
<th>Descrizione</th>
<th>Esempio</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Associazioni di controllo qualità</td>
<td>Vedere le sezioni precedenti dell'articolo.</td>
<td>Un'associazione di controllo qualità definisce le seguenti informazioni per un ordine di controllo qualità generato:
<ul>
<li>L'evento della transazione</li>
<li>Il set di test che devono essere eseguiti sugli articoli</li>
<li>L'AQL</li>
<li>Il piano di campionamento</li>
</ul>
Occorre definire un'associazione di controllo qualità per ogni variazione in un processo aziendale che richieda la generazione automatica di un ordine di controllo qualità. Ad esempio, è possible generare un ordine di controllo qualità nei processi aziendali per ordini acquisto, ordini di quarantena, ordini cliente e ordini di produzione.</td>
</tr>
<tr class="even">
<td>Test</td>
<td>Utilizzare questa pagina per definire e visualizzare i singoli test che determinano se i prodotti sono conformi alle specifiche di qualità. È possibile assegnare uno o più test singoli a un gruppo di test. In questo caso, è inoltre necessario specificare le informazioni specifiche del test, ad esempio i valori di misurazione accettabili. I valori di misurazione vengono utilizzati per i test quantitativi, mentre le variabili di test vengono utilizzate per i test qualitativi.
<ul>
<li>A un test quantitativo è associato un tipo di test <strong>Intero</strong> o <strong>Frazione</strong> e di un'unità di misura designata. Le specifiche di qualità e i risultati del test vengono espressi sotto forma di numeri.</li>
<li>Un test qualitativo è un tipo di test <strong>Opzione</strong>. I test qualitativi richiedono informazioni aggiuntive sulla variabile di test misurata e sulle relative opzioni enumerate. Le specifiche di qualità e i risultati del test vengono espressi in base a un esito.</li>
</ul></td>
<td>Una società di produzione esegue due test sul materiale acquistato, ovvero un test quantitativo sulla qualità del materiale e un test qualitativo sul danno all'imballaggio. La società definisce informazioni aggiuntive sul test qualitativo per identificare la variabile di test, per l'imballaggio danneggiato, e i relativi risultati. La società utilizza la pagina <strong>Gruppi di test</strong> per assegnare i due test a un gruppo di test e per specificare le informazioni specifiche del test. Il gruppo di test viene assegnato a un ordine di controllo qualità, in modo che la società possa creare un report per i risultati dei due test.</td>
</tr>
<tr class="odd">
<td>Gruppi di test</td>
<td>Utilizzare questa pagina per impostare, modificare e visualizzare gruppi di test e i singoli test assegnati a un gruppo specifico. Nel riquadro superiore sono visualizzati i gruppi di test, mentre nel riquadro inferiore sono visualizzati i test assegnati a un gruppo di test selezionato. A un gruppo di test è possibile assegnare più criteri, tra cui un piano di campionamento, un AQL e la richiesta di test distruttivo. Quando si assegna un singolo test a un gruppo di test, è necessario definire informazioni aggiuntive, come sequenza, documenti e date di validità. In un test quantitativo, le informazioni definite dall'utente includono anche i valori di misurazione accettabili e in un test qualitativo includono la variabile di test e il risultato predefinito. Il gruppo di test assegnato a un ordine di controllo qualità definisce il set predefinito di test che devono essere eseguiti sull'articolo specificato. Tuttavia, è possibile aggiungere, eliminare o modificare i test in un ordine di controllo qualità. I risultati di ciascun test vengono riportati in un ordine di controllo qualità.</td>
<td>In una società di produzione è definito un gruppo di test per ogni variazione apportata alle linee guida per il controllo qualità. I vari gruppi di test riflettono le differenze nei piani di campionamento, nei set di test da eseguire congiuntamente, nel livello di qualità accettabile e in altri fattori. Per i test quantitativi sono inoltre presenti differenze nei valori di misurazione accettabili. Per applicare le linee guida per il controllo qualità, la società assegna un gruppo di test a ciascuna regola per la generazione automatica di ordini di controllo qualità (nella pagina <strong>Associazioni di controllo qualità</strong>) e assegna un gruppo di test agli ordini di controllo qualità creati manualmente.</td>
</tr>
<tr class="even">
<td>Gruppi di controllo qualità articoli</td>
<td>Utilizzare questa pagina per impostare, modificare e visualizzare gli articoli assegnati a un gruppo di controllo qualità o i gruppi di controllo qualità assegnati a un articolo. Un gruppo di controllo qualità rappresenta i requisiti di test comuni per gli articoli. Dopo la definizione dei requisiti di test nella pagine <strong>Gruppi di test</strong>, è possibile definire le regole per generare automaticamente gli ordini di controllo qualità. Per semplificare il processo, non si definiscono le regole per i singoli articoli. Invece, definire le regole per un gruppo di controllo qualità, utilizzando la pagina <strong>Associazioni di controllo qualità</strong>. È inoltre possibile utilizzare la pagina <strong>Gruppi di controllo qualità articoli</strong> per un gruppo di controllo qualità selezionato per assegnare gli articoli rilevanti al gruppo. È inoltre possibile utilizzare la pagina <strong>Gruppi di controllo qualità articoli</strong> per un articolo selezionato per assegnarvi i gruppi di controllo qualità rilevanti.</td>
<td>Una società di produzione acquista varie materie prime con gli stessi requisiti di test per quanto riguarda l'ispezione in entrata. La società definisce un gruppo di controllo qualità e vi assegna i numeri articolo associati alle materie prime. In seguito, la società acquista un nuovo tipo di materie prima con gli stessi requisiti di test. Invece di impostare nuovi requisiti di test per il nuovo materiale, la società aggiunge il relativo numero articolo al gruppo di controllo qualità esistente. La stessa società produce inoltre articoli con gli stessi requisiti di test della produzione e spedisce articoli con gli stessi requisiti per quanto riguarda l'esecuzione di test prima della spedizione. La società definisce due ulteriori gruppi di controllo qualità e assegna a ognuno i numeri di articolo rilevanti.</td>
</tr>
<tr class="odd">
<td>Variabili di test</td>
<td>Utilizzare questa pagina per definire e visualizzare le variabili associate a un test qualitativo. Per ciascuna variabile, è possibile definire i risultati enumerati che rappresentano le possibili opzioni. Definire i test nella pagina <strong>Test</strong>. Per i test qualitativi, è necessario impostare il tipo di test su <strong>Opzione</strong>. Utilizzare la pagina <strong>Gruppi di test</strong> per assegnare una variabile di test a un test specifico.</td>
<td>Una società produttrice di biscotti utilizza un test di ispezione per il prodotto finito. Il test di ispezione ha diverse variabili. Una variabile si riferisce al gusto e i possibili risultati per questa variabile sono buono o cattivo. Una seconda variabile riguarda il colore e i risultati possibili troppo scuro, troppo chiaro e corretto.</td>
</tr>
<tr class="even">
<td>Risultati variabile di test</td>
<td>Utilizzare questa pagina per impostare, modificare e visualizzare i possibili risultati di una variabile di test associata a un test qualitativo. Per ogni risultato è possibile assegnare lo stato <strong>superato</strong> o <strong>non superato</strong>. È necessario definire una variabile e i relativi risultati per un test qualitativo definito nella pagina <strong>Test</strong>. Per i test qualitativi, il tipo di test è impostato su <strong>Opzione</strong> nella pagina <strong>Test</strong>. Utilizzare la pagina <strong>Gruppi di test</strong> per assegnare una variabile di test e il risultato predefinito a un singolo test qualitativo.</td>
<td>Una società produttrice di biscotti utilizza un test di ispezione per il prodotto finito. Il test di ispezione ha diverse variabili. Una variabile si riferisce al gusto e i possibili risultati per questa variabile sono buono o cattivo. Una seconda variabile riguarda il colore e i risultati possibili troppo scuro, troppo chiaro e corretto. A ogni risultato viene assegnato lo stato <strong>superato</strong> o <strong>non superato</strong>. Durante il test di ispezione per ogni variabile, l'ispettore indica il risultato del test selezionando uno dei risultati.</td>
</tr>
</tbody>
</table>



<a name="see-also"></a>Vedere anche
--------

[Processi di gestione qualità](quality-management-processes.md)

[Attivazione della gestione di non conformità](enable-nonconformance-management.md)

