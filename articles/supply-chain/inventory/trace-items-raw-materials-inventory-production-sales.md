---
title: Traccia di articoli e materie prime in magazzino, nella produzione e nelle vendite
description: "In questo argomento viene descritto come utilizzare la tracciabilità articolo per identificare il punto in cui vengono utilizzati gli articoli o le materie prime o quello in cui verranno utilizzati nei processi di produzione e vendita."
author: perlynne
manager: AnnBe
ms.date: 11/02/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventTrackingDimTracing, InventTrackingDimTracingCriteria
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 30191
ms.assetid: fdd0939a-855c-430f-a684-94f3baea1df4
ms.search.region: Global
ms.author: pjacobse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 2dd3709ae55e32ec2e5258ced2764c4eb218a4c4
ms.contentlocale: it-it
ms.lasthandoff: 11/03/2017

---

# <a name="item-and-raw-material-tracing-in-inventory-production-and-sales"></a>Traccia di articoli e materie prime in magazzino, nella produzione e nelle vendite

[!include[banner](../includes/banner.md)]


In questo argomento viene descritto come utilizzare la tracciabilità articolo per identificare il punto in cui vengono utilizzati gli articoli o le materie prime o quello in cui verranno utilizzati nei processi di produzione e vendita.

La funzionalità di tracciabilità articolo è disponibile nella pagina **Tracciabilità articolo**. Nelle sezioni seguenti viene descritto come utilizzare la tracciabilità articolo e quali sono le opzioni e i limiti.

## <a name="what-is-item-tracing"></a>Cos'è la tracciabilità articolo?
La tracciabilità articolo è uno strumento di business intelligence (BI) che fornisce visibilità nell'origine e nella destinazione di articoli e di materie prime nella supply chain. I produttori possono tracciare gli articoli, le materie prime o gli ingredienti dal fornitore fino alla produzione e alla vendita del prodotto finito. La tracciabilità articolo consente ai produttori di rispettare i requisiti normativi e ai responsabili della qualità e della produzione di analizzare ed eseguire operazioni al fine di analizzare gli scostamenti nella qualità dei prodotti e dei materiali. Di seguito sono riportati alcuni esempi delle modalità in cui i produttori possono utilizzare la tracciabilità articolo:

-   Identificare la quantità di un articolo o delle materie prime attualmente in magazzino e il luogo in cui sono immagazzinate.
-   Determinare gli articoli e le materie prime spedite e i relativi clienti.
-   Identificare tutte le spedizioni pianificate che includono l'articolo o le materie prime.
-   Individuare gli ordini di produzione che utilizzano l'articolo o la materia prima e che sono pianificati, in sospeso, o dichiarati finiti.
-   Individuare dove sono stati acquistati gli articoli o le materie prime.
-   Esaminare dove sono stati utilizzati gli articoli o le materie prime nella produzione di un altro articolo.

## <a name="what-can-i-trace-and-are-there-any-limitations"></a>Esistono delle limitazioni alla tracciabilità?
È possibile tracciare le operazioni di magazzino storiche per gli articoli e le materie prime in base a un numero di articolo e a una dimensione di tracciabilità, ad esempio il numero di serie, il numero batch o il numero batch del fornitore. È possibile tracciare un articolo o una materia prima solo se ha una dimensione di tracciabilità assegnata. Poiché la tracciabilità si basa sulle operazioni di magazzino, ci sono alcune limitazioni alla tracciabilità degli articoli. Ad esempio, sono previste limitazioni relative alle transazioni per i progetti, i cespiti e la vendita al dettaglio. Inoltre, i coprodotti sono visualizzati nel dettaglio traccia, ma i sottoprodotti non sono inclusi. La traccia include tutte le transazioni di magazzino da un'ubicazione a un'altra. Di conseguenza, gli utenti possono ritenere eccessiva la quantità di informazioni. La traccia viene visualizzata per una persona giuridica per volta. Non sono disponibili funzionalità interaziendali in un contesto interaziendale. È necessario avviare una nuova traccia per ogni società in cui un articolo viene ricevuto o rilasciato.

## <a name="what-criteria-can-i-specify-for-an-item-trace"></a>Quali criteri è possibile specificare per una traccia articolo?
I criteri necessari per una traccia articolo sono il numero articolo, una dimensione di tracciabilità, ad esempio un numero batch o un numero di serie, e la direzione. Nella seguente tabella sono descritti i criteri che è possibile utilizzare in una traccia articolo.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Gruppo campi</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Numero articolo</td>
<td>Consente di immettere l'identificatore dell'articolo o della materia prima di cui si sta eseguendo la traccia.</td>
</tr>
<tr class="even">
<td>Dimensioni prodotto</td>
<td>Facoltativo: tracciare gli aspetti specifici della definizione di prodotto, ad esempio la configurazione, la dimensione, il colore o lo stile.</td>
</tr>
<tr class="odd">
<td>Dimensioni di tracciabilità</td>
<td>Immettere la dimensione di tracciabilità di un numero batch, un numero batch fornitore o un numero di serie. Quando si utilizza il numero batch come criterio, il numero batch del fornitore viene visualizzato se sono state acquisite tali informazioni.</td>
</tr>
<tr class="even">
<td>Dimensioni di immagazzinamento</td>
<td>Facoltativo: tracciare gli articoli archiviati in un'ubicazione specifica.</td>
</tr>
<tr class="odd">
<td>Periodo</td>
<td>Facoltativo: immettere le date per limitare la traccia a un periodo specifico. Nei dettagli traccia verranno visualizzati solo i documenti e le transazioni creati tra queste date.</td>
</tr>
<tr class="even">
<td>Avanti o indietro</td>
<td>Selezionare la direzione per la traccia. È possibile eseguire la traccia in avanti o indietro:
<ul>
<li><strong>Indietro</strong>: consente di tracciare il downstream per identificare l'origine, la quantità che resta disponibile e tutti gli ordini di produzione almeno parzialmente dichiarati finiti.</li>
<li><strong>Avanti</strong>: consente di tracciare l'upstream per identificare la destinazione. È possibile individuare gli ordini cliente e i clienti a cui sono stati spediti almeno parzialmente l'articolo o le materie prime.</li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="what-information-is-included-in-the-trace-details"></a>Quali informazioni sono incluse nei dettagli traccia?
I risultati di una traccia vengono visualizzati in ordine cronologico nella struttura della scheda dettaglio **Dettagli** della pagina **Tracciabilità articolo**. L'ordine varia a seconda della direzione di traccia. Nei dettagli sono incluse tutte le transazioni dall'acquisto dell'articolo dal fornitore alla sua vendita al cliente. Nei risultati di traccia sono inoltre inclusi i prodotti provvisori relativi all'articolo o alla dimensione di tracciabilità specificata nei criteri di traccia. Il nodo di livello superiore mostra la quantità dell'articolo, nell'unità di magazzino, che resta disponibile in base alle dimensioni di immagazzinamento specificate nei criteri di traccia. **Nota:** i dettagli traccia forniscono un'istantanea delle informazioni disponibili quando viene eseguita la traccia. I dettagli traccia non vengono aggiornati se le informazioni sono state modificate dopo l'esecuzione della traccia.

## <a name="why-dont-some-nodes-contain-any-details"></a>Perché alcuni nodi non contengono dettagli?
Per ridurre la quantità di informazioni nei dettagli traccia, i dettagli sono inclusi solo nel nodo per la prima istanza dell'articolo o della materia prima. Se un nodo selezionato non contiene i dettagli, è possibile visualizzare il nodo che li contiene facendo clic su **Vai a riga tracciata**. È possibile ritornare al nodo lasciato facendo clic su **Torna**.

## <a name="can-i-view-only-a-particular-type-of-document-for-example-can-i-view-only-production-orders-customers-or-vendors"></a>È possibile visualizzare solo un tipo specifico di documento? Ad esempio, è possibile visualizzare solo gli ordini di produzione, i clienti o i fornitori?
Sì, dai dettagli traccia è possibile aprire le pagine elenco che includono solo un tipo specifico di documento o di transazione. È possibile accedere alle pagine dalla voce di menu **Tracciatura** nel Riquadro azioni, nei gruppi **Articolo** **Vendite**, **Acquisto**, **Produzione** e **Qualità**. Ad esempio, per visualizzare un elenco dei fornitori nei dettagli traccia, fare clic su **Tracciatura** &gt; **Acquisto** &gt; **Fornitori**. Le pagine elenco riepilogano i documenti o le transazioni dai dettagli traccia. Le pagine elenco **Transazioni in sospeso**, **Ordini in sospeso** e **Ordini cliente non spediti** indicano anche altre informazioni non incluse nei dettagli traccia. Inoltre, vengono sempre illustrati i risultati a partire dalla data corrente, anche se è stato specificato un intervallo di date. Nella seguente tabella sono descritti i dettagli aggiuntivi che queste pagine possono includere.

| Elenchi                    | Descrizione                                                                                                                                                                                                                                                                                                                   |
|--------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Ordini cliente non spediti | Visualizzare le righe dell'ordine cliente non prelevate e pertanto non visualizzate nei dettagli traccia.                                                                                                                                                                                                                        |
| Ordini in sospeso           | Visualizzare tutti gli ordini di produzione in sospeso per l'articolo tracciato, indipendentemente dalle dimensioni di tracciabilità utilizzate nei criteri di traccia. È inoltre possibile visualizzare gli ordini di produzione in sospeso in cui l'articolo tracciato è un ingrediente, non sono state effettuate registrazioni e nessuna transazione è stata dichiarata finita per l'ordine. |
| Transazioni in sospeso     | Visualizzare le operazioni di magazzino in sospeso per l'articolo tracciato che include le dimensioni di tracciabilità specificate o una dimensione di tracciabilità vuota. Nei dettagli traccia è inoltre possibile visualizzare le operazioni di magazzino in sospeso per gli articoli e le combinazioni della dimensione di tracciabilità o un valore vuoto.                                                |

## <a name="how-many-levels-can-i-trace-up-or-down-in-a-bom-or-formula"></a>Quanti livelli è possibile tracciare verso l'alto o verso il basso in una distinta base o in una formula?
È possibile tracciare un livello verso l'alto o verso il basso in una distinta base o una formula. Ad esempio, se viene eseguita una traccia sulle materie prime, è possibile visualizzare il prodotto finito e tutti i co-prodotti. Tuttavia, se viene eseguita la traccia di un co-prodotto, non includere il prodotto finito nei dettagli traccia.

## <a name="how-can-i-view-more-details-about-a-document-or-transaction-in-the-trace-details"></a>Come è possibile visualizzare più dettagli su un documento o una transazione nei dettagli traccia?
Nella scheda dettaglio **Dettagli** è possibile visualizzare altre informazioni su un documento selezionato o una transazione nei dettagli traccia in due modi:

-   Quando viene selezionato un nodo nei dettagli traccia nella scheda dettaglio **Dettagli**, nelle altre schede dettaglio della pagina vengono visualizzate informazioni su un documento o una transazione nel nodo.
-   Aprire la pagina dei dettagli per il documento in un nodo selezionato facendo clic su **Visualizza dettagli**. Ad esempio, se viene selezionato un nodo che descrive un ordine di produzione e si fa clic su **Visualizza dettagli**, viene visualizzata la pagina **Dettagli ordini di produzione**.

Alcune schede dettaglio offrono accesso ad altre informazioni relative al nodo selezionato. Ad esempio, nella scheda dettaglio **Non conformità**, è possibile fare clic su **Richieste di informazioni** per analizzare dove è presente uno storico di non conformità. Nella scheda dettaglio **Batch** è possibile fare clic su **Elenco scorte disponibili** per visualizzare la quantità di inventario fisico al momento disponibile e tutte le operazioni di magazzino che includono il batch.

## <a name="can-i-run-more-than-one-trace-and-then-compare-the-details"></a>È possibile eseguire più di una traccia e quindi confrontare i dettagli?
Dopo aver eseguito la traccia, è possibile utilizzare le opzioni seguenti del pulsante **Traccia da nodo** per eseguire una nuova traccia nella transazione del nodo selezionato:

-   **Indietro** o **Avanti**: consente di avviare una nuova traccia per il nodo selezionato e di sovrascrivere i dettagli della traccia corrente.
-   **Nuovo indietro** o **Nuovo avanti**: consente di avviare una nuova traccia in una nuova finestra e conservare i dettagli della traccia corrente.

Se si desidera utilizzare l'opzione **Nuovo indietro** o **Nuovo avanti**, è necessario utilizzare la funzionalità **Apri in nuova finestra** per visualizzare una nuova traccia in una nuova finestra.

## <a name="can-i-save-the-trace-details"></a>È possibile salvare i dettagli traccia?
È possibile salvare le informazioni nella scheda **Dettagli** come file XML facendo clic su **Esporta** sotto l'azione ****Tracciatura**** nel Riquadro azioni. Oltre ai dettagli traccia, il file XML include i criteri di traccia, il nodo padre e la quantità disponibile. La funzionalità per salvare i dettagli di una traccia è utile se, ad esempio, si desidera collegare le informazioni a un ordine di controllo qualità o ad altra documentazione di conformità. È possibile specificare dove il file viene salvato. Per visualizzare il file immediatamente, selezionare l'opzione **Mostra documento**. **Nota:** il file viene sempre salvato, anche se si desidera solo visualizzarlo. Per impostazione predefinita, il file XML verrà visualizzato in una finestra del browser. Tuttavia, è possibile fare clic con il pulsante destro del mouse sul file, selezionare **Apri con** e quindi il programma da utilizzare per visualizzare i contenuti.

## <a name="can-i-calculate-a-balance-for-a-particular-item-or-ingredient"></a>È possibile calcolare un saldo per un articolo o un ingrediente specifico?
È possibile esportare le informazioni contenute nelle pagine di riepilogo in Microsoft Excel. Aprire la pagina rilevante, fare clic sull'icona **Apri in Microsoft Office** quindi selezionare **Esporta in Microsoft Excel**. Questa funzionalità risulta particolarmente utile se si desidera calcolare un saldo collettivo per un articolo o un ingrediente dalla pagina **Riepilogo delle transazioni**. Nella pagina **Riepilogo delle transazioni** è possibile filtrare l'articolo o l'ingrediente e, facoltativamente, il batch, quindi esportare le informazioni in Excel. In Excel, è ad esempio possibile isolare la quantità disponibile, la quantità venduta e quella utilizzata nella produzione.

## <a name="can-i-investigate-whether-there-is-a-history-of-issues-with-items-or-raw-materials"></a>È possibile esaminare se è presente lo storico dei problemi con gli articoli o le materie prime?
Nei dettagli traccia sono incluse le informazioni sugli ordini di controllo qualità e le non conformità che riguardano l'articolo o le materie prime. Per visualizzare un riepilogo degli ordini di controllo qualità e delle non conformità, fare clic su **Ordini di controllo qualità** o **Non conformità** nel Riquadro azioni. **Nota:** gli ordini di controllo qualità distruttivi possono essere visualizzati più volte nei dettagli traccia. Quando viene creato un ordine di controllo qualità distruttivo per un documento, ad esempio un ordine fornitore, questo viene visualizzato per ogni transazione per tale documento.

## <a name="are-there-any-reporting-capabilities-that-are-related-to-item-tracing"></a>Esistono funzionalità di creazione di report correlate alla tracciabilità articolo?
È possibile generare il report **Spedito ai clienti** per identificare la quantità dell'articolo o delle materie prime spediti e i clienti relativi. Per una richiesta di informazioni correlata alla conformità, è possibile generare il report per tutti i clienti. Per una richiesta di informazioni correlata al servizio clienti, è possibile generare il report per un cliente selezionato. Se il prodotto era una materia prima utilizzata nella produzione di un articolo finito, anche quest'ultimo verrà incluso. **Nota:** se si utilizzano le funzionalità per l'eliminazione o l'archivio degli ordini cliente, i risultati del report includeranno inoltre tutti gli ordini cliente eliminati o archiviati.

## <a name="can-i-trace-coproducts-and-byproducts"></a>È possibile tracciare i co-prodotti e i sottoprodotti?
È possibile tracciare i co-prodotti, ma non è possibile tracciare i sottoprodotti poiché a questi non vengono in genere assegnate le dimensioni di tracciabilità. Quando viene tracciato un articolo, i dettagli traccia includono eventuali co-prodotti correlati. Un nodo contenente un co-prodotto include la parola "co-prodotto" nei dettagli. È inoltre possibile visualizzare i dettagli relativi a un co-prodotto selezionando il nodo nei dettagli traccia e quindi facendo clic sulla scheda dettaglio **Produzione**.

