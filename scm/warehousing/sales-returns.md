---
title: Resi su vendite
description: "In questo argomento vengono fornite informazioni sul processo per gli ordini di reso. Sono riportate informazioni sui resi dei clienti e sul relativo effetto sulle quantità di scorte disponibili e di determinazione costi."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 269384
ms.assetid: 98a4b517-e606-4036-b55f-1ab248898bdf
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 3d02a15387231160f5b8a237aa11008b91ef1223
ms.openlocfilehash: b265a20a271230de5dba6df93900a24aad642885
ms.lasthandoff: 03/31/2017


---

# <a name="sales-returns"></a>Resi su vendite

In questo argomento vengono fornite informazioni sul processo per gli ordini di reso. Sono riportate informazioni sui resi dei clienti e sul relativo effetto sulle quantità di scorte disponibili e di determinazione costi.

I clienti possono rendere gli articoli per diversi motivi. Ad esempio, un articolo difettoso potrebbe essere, o non è in base alle aspettative del cliente. Il processo di reso inizia quando un cliente generata una richiesta di restituire un articolo. Dopo che la richiesta del cliente viene ricevuta, viene creato un ordine di reso in Microsoft Dynamics 365 per le operazioni.

## <a name="return-order-process"></a>Processo dell'ordine di reso
Nella seguente figura viene fornita una panoramica del processo dell'ordine di reso.  

![[] (salesreturns01. /media/salesreturns01.jpg)](. /media/salesreturns01.jpg)  

Sono disponibili due tipi di processi dell'ordine di reso: reso e di credito solo fisiche.

-   ** La restituzione di Fisico ** - l'ordine di reso autorizzare il reso fisico dei prodotti.
-   ** Il credito solo ** - l'ordine di reso consente a un credito del cliente non viene richiesto al reso di un cliente fisicamente i prodotti.

### <a name="physical-return-order-process"></a>Processo dell'ordine di reso di Fisico

1.  ** Creare un ordine di reso. ** Documenti formalmente l'autorizzazione per il cliente restituiscano tutti i prodotti difettosi o indesiderati. L'ordine di reso non richiede che la società accettare i prodotti resi contratti o in Avere per il cliente. Se il reso viene accettato, è possibile autorizzare un articolo sostitutivo per essere inviato prima dell'articolo difettoso sia stato reso.
2.  ** Arrivi in magazzino per l'ispezione. ** Esegue un'ispezione iniziale e una convalida del documento dell'ordine di reso. L'ordine di reso anche supporta la quarantena di resi per l'ispezione e di controllo qualità aggiuntive.
3.  ** Di determinare lo smaltimento. ** Finalizzazione il processo di ispezione e determinare le operazioni da eseguire relativamente ai prodotti resi. Come parte di questo passaggio, decidere se accrediterete il cliente, rifiutare il prodotto reso, verrà accettata o il prodotto reso, scartare il prodotto e quindi inviare un prodotto di sostituzione al cliente.
4.  ** Generare un documento di trasporto. ** Generare un documento di trasporto e commetta la decisione di smaltimento che viene effettuato nel passaggio 3. Finalizzazione i processi di Logistica.
5.  ** Generazione di una fattura. ** Chiudere l'ordine di reso.

### <a name="credit-only-process"></a>Accreditare solo il processo

1.  ** Creare un ordine di reso. ** Documenti formalmente l'autorizzazione per il cliente ricevano in Avere senza restituire i prodotti difettosi o indesiderati. ** Avere solo ** il codice smaltimento autorizza la decisione per l'accredito il cliente senza reso di Fisico.
2.  ** Generazione di una fattura. ** Genera la nota di accredito quindi chiudere l'ordine di reso.

## <a name="return-material-authorization"></a>Autorizzazione reso
Autorizzazione reso (RMA) per l'elaborazione delle configurazioni sulla funzionalità di ordine cliente. Un RMA viene registrato come un ordine di reso, che viene creato come ordine cliente e può contenere altro ordine cliente associato, definito un ordine sostitutivo. Entrambi gli ordini clienti accedono al codice NAR origine.

-   ** Ordine di reso ** - per registrare un RMA, si crea un ordine di reso, ovvero un ordine cliente con il tipo assegnato, ** Ordine di reso. ** Tutte le modifiche apportate alle informazioni di RMA viene aggiornata automaticamente nell'ordine cliente. Se l'ordine di reso è stato aperto ** **, non verrà visualizzato nell'elenco degli ordini cliente. I RMA per la gestione degli arrivi e il ricevimento di resi nonché per autorizzare un'azione di smaltimento di credito solo (vedere la sezione ** codici smaltimento e azioni di smaltimento **). Tutti gli altri processi di seguito devono essere gestiti nell'ordine cliente.
-   ** La ordine sostitutivo ** - quando un ordine sostitutivo deve essere inviati al cliente, il RMA può includere un secondo ordine cliente. È possibile creare manualmente un ordine di sostituzione per il RMA supportiate la consegna immediata. In alternativa, l'ordine sostitutivo possibile creare automaticamente dopo l'arrivo, controllo e l'entrata viene completata per la voce di RMA con un codice smaltimento che indica la sostituzione. L'ordine di sostituzione sarà la stessa funzionalità associata a un ordine cliente. Ad esempio, è possibile utilizzarlo per configurare un prodotto personalizzato come l'articolo di sostituzione, creare un ordine di produzione per correggere un reso, di creare un ordine fornitore di consegna diretta per inviare la sostituzione da un fornitore, o di supportare scopi diversi.

## <a name="create-a-return-order"></a>Creare un ordine di reso
Il processo dell'ordine di reso inizia quando contatti del cliente che l'organizzazione restituire un prodotto difettoso o indesiderato e/o l'accredito. Dopo che l'organizzazione accetta il reso, il reso viene documentato un ordine di reso. L'ordine di reso diventa il punto focale interno dell'elaborazione dell'articolo restituito. Nell'illustrazione riportata la procedura per la creazione di un ordine di reso.  

[procedura![per creare un ordine di reso (]. /media/salesreturn02.png)](. /media/salesreturn02.png)

### <a name="create-a-return-order-header"></a>Creare un'intestazione dell'ordine di reso

Quando si crea un ordine di reso, le informazioni nella tabella importare.

| Campo              | descrizione                                              | Commenti                                                                                                                                                                                                                                                                                                                                        |
|--------------------|----------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Account cliente   | Un riferimento alla tabella Customers                       | È necessario immettere un conto cliente esistente.                                                                                                                                                                                                                                                                                                  |
| Indirizzo di consegna   | Indirizzo a cui l'articolo viene restituito a                 | Per impostazione predefinita, l'indirizzo dell'organizzazione viene utilizzato. Se è stato selezionato un magazzino specifico nell'intestazione, l'indirizzo di consegna viene modificato nell'indirizzo di consegna del magazzino. È possibile modificare questo indirizzo ** dettagli dell'ordine di reso ** nella pagina.                                                                                                  |
| Relazioni sito/magazzino     | Sito del magazzino che riceve il prodotto reso | L'indirizzo di consegna dell'ordine di reso viene determinato in base all'indirizzo di consegna del sito o magazzino.                                                                                                                                                                                                                                 |
| Codice NAR         | Identificazione assegnata all'ordine di reso              | Viene utilizzato come chiave alternativa nel corso dell'ordine di reso. Codice NAR assegnato in base alla sequenza del codice NAR impostata ** parametri di contabilità clienti ** nella pagina.                                                                                                                              |
| Scadenza           | Ultima data in cui un articolo può essere restituito               | Il valore predefinito viene calcolato come la data corrente al periodo di validità. Ad esempio, se un reso è valido solo per i 90 giorni dalla data in cui l'ordine di reso verrà creato e cui è stato creato l'ordine di reso il 1° maggio, il campo è impostato su 30-July ** **. Il periodo di validità viene impostato ** parametri di contabilità clienti ** nella pagina. |
| Codice motivo reso | Il motivo del cliente per la restituzione del prodotto          | Il codice motivo è selezionato nell'elenco dei codici motivo definiti dall'utente. È possibile aggiornare questo campo in qualsiasi momento.                                                                                                                                                                                                                                    |

### <a name="create-return-order-lines"></a>Creare le righe degli ordini di reso

Dopo aver completato l'intestazione di reso, è possibile creare ritracce utilizzando uno dei seguenti metodi:

-   Immettere manualmente i dettagli dell'articolo, la quantità e altre informazioni per ciascun ritraccia.
-   Creare una ritraccia utilizzando ** ordine cliente Trova ** la funzione. Utilizzare questa funzione quando si crea un ordine di reso. ** Ordine cliente Trova ** la funzione stabilito un riferimento da ritraccia alla riga dell'ordine cliente fatturata e recupera i dettagli riga ad esempio il numero di articolo, la quantità, Scostamento prezzi, sconti e i valori di costo da una riga di vendita. Consente di riferimento garantire che, quando il prodotto viene restituito alla società, in riferimento allo stesso costo unitario che è stata venduta. Riferimento vengono inoltre convalidati gli ordini di reso vengono creati per una quantità che supera quella che è stata venduta sulla fattura.

** Nota: ** Le ritracce con un riferimento a un ordine cliente vengono considerate le rettifiche contrario, storni, la vendita. Per ulteriori informazioni, vedere "posta l'area nella contabilità generale", più avanti in questo argomento.

### <a name="charges"></a>Spese

Le commissioni e le spese possono essere aggiunti all'ordine di reso a uno o più dei seguenti metodi:

-   È possibile aggiungere manualmente spese all'intestazione dell'ordine di reso, alla riga dell'ordine di reso, o in entrambi.
-   Le spese possono essere aggiunti automaticamente nell'intestazione dell'ordine di reso in funzione del codice motivo reso.
-   Le spese possono essere aggiunti automaticamente alla riga dell'ordine di reso, in base al codice di smaltimento della riga.

Le spese devono essere aggiunte automaticamente dopo che un codice motivo reso o il codice di smaltimento è assegnato alla riga. Se il codice motivo viene modificato in un secondo momento, la voce esistente di spese non verrà deselezionata, ma una nuova immissione delle spese può essere aggiunti, in base al nuovo codice motivo. Quando si aggiungono spese alle righe dell'ordine di reso, Spese calcolate in base alla percentuale di riga o il valore diventa ordine negative quando la riga o di riga è negativo, a meno che la percentuale è anche un numero negativo. Le spese con un valore negativo rappresentano un credito del cliente.

### <a name="return-reason-codes"></a>Codici motivo reso

Applicazione dei codici motivo per i resi, è possibile rendere più criteri di reso semplice analizzare. I codici motivo vengono fornite informazioni sul motivo per cui un cliente desidera restituire gli articoli. In alcune organizzazioni con numerosi codici motivo. Questo l'organizzazione potrebbe raggruppare i codici motivo in gruppi di codici motivo per ottenere una panoramica più dettagliata e per il reporting cumulata.

### <a name="disposition-codes-and-disposition-actions"></a>Codici smaltimento e azioni di smaltimento

Un passaggio fondamentale nel processo dell'ordine di reso è l'assegnazione di un codice smaltimento alla riga dell'ordine di reso nella registrazione arrivi. Codice di smaltimento determina le seguenti informazioni:

-   ** Le implicazioni finanziarie ** del cliente deve essere registrato in Avere per gli articoli resi e delle spese devono essere aggiunte alla riga dell'ordine di reso?
-   ** Lo smaltimento del reso deve ** - l'articolo è possibile aggiungere di nuovo al magazzino, deve essere scartata, o essere trasferite al cliente?
-   ** La logistica del reso deve ** di un articolo sostitutivo essere emesso al cliente?

Oltre a delle merci restituite vengono eliminate, codici smaltimento possono determinare le spese da applicare alla ritraccia. Possono inoltre essere utilizzati per raggruppare i resi eseguire analisi statistiche. I codici smaltimento vengono definiti come parte dell'impostazione degli ordini di reso. Tuttavia, ogni codice smaltimento deve fare riferimento a una delle azioni l'accessibilità di smaltimento. Nella tabella riportata di seguito sono elencati i codici smaltimento incorporati e le relative azioni. ** Importante: ** Se un articolo viene restituito, ma il cliente deve ancora accreditare, assegna ** Solo credito ** il codice smaltimento alla ritraccia.

<table>
<thead>
<tr class="header">
<th>Codice smaltimento</th>
<th>Implicazioni finanziarie</th>
<th>Implicazioni per Logistica</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Solo credito</td>
<td><ul>
<li>Il cliente viene accreditato il prezzo di vendita il tutte le commissioni o le spese.</li>
<li>Perdita dalla riduzione dell'articolo viene registrata nella contabilità generale.</li>
</ul></td>
<td>L'articolo non deve essere restituito. Questa azione di smaltimento vengono utilizzate per i seguenti casi:
<ul>
<li>Esiste una relazione di trust sufficiente tra le parti.</li>
<li>Costo di reso di un articolo difettoso è proibitivo.</li>
<li>Gli articoli non possono essere abilitati al magazzino. A causa di altre condizioni, un reso fisico non è obbligatorio.</li>
</ul></td>
</tr>
<tr class="even">
<td>Avere</td>
<td><ul>
<li>Il cliente viene accreditato il prezzo di vendita il tutte le commissioni o le spese.</li>
<li>Il valore di magazzino verrà aumentato dal costo del reso.</li>
</ul></td>
<td>L'articolo viene restituito e aggiunta al magazzino.</td>
</tr>
<tr class="odd">
<td>Sostituzione e credito</td>
<td><ul>
<li>Il cliente viene accreditato il prezzo di vendita il tutte le commissioni o le spese.</li>
<li>Il valore di magazzino verrà aumentato dal costo del reso.</li>
<li>Un ordine cliente distinto per una sostituzione viene creato e separatamente di lavorazione.</li>
</ul></td>
<td>L'articolo viene restituito e aggiunta al magazzino.</td>
</tr>
<tr class="even">
<td>Sostituzione e scarto</td>
<td><ul>
<li>Il cliente viene accreditato il prezzo di vendita, meno tutte le commissioni o le spese.</li>
<li>Perdita dalla riduzione dell'articolo viene registrata nella contabilità generale.</li>
<li>Un ordine cliente distinto per una sostituzione viene creato e separatamente di lavorazione.</li>
</ul></td>
<td>L'articolo viene restituito e ridotto.</td>
</tr>
<tr class="odd">
<td>Reso a cliente</td>
<td>Nessuno, a meno che l'eventuale commissioni o le spese.</td>
<td>L'articolo viene restituito ma viene restituito al cliente dopo l'ispezione. Questa azione di smaltimento può essere utilizzata se l'articolo è stato danneggiato deliberatamente, o se la garanzia è stata annullata.</td>
</tr>
<tr class="even">
<td>Scarti</td>
<td><ul>
<li>Il cliente viene accreditato il prezzo di vendita il tutte le commissioni o le spese.</li>
<li>Perdita dalla riduzione dell'articolo viene registrata nella contabilità generale.</li>
</ul></td>
<td>L'articolo viene restituito o ridotto.</td>
</tr>
</tbody>
</table>

## <a name="arrival-at-the-warehouse-for-inspection"></a>Arrivo in magazzino per l'ispezione
Prima di poter ricevere fisicamente gli articoli restituiti in magazzino registra un documento di trasporto, gli articoli devono sostituire con la registrazione arrivi e un'ispezione facoltativa. Nella seguente figura viene fornita una panoramica del processo di arrivo. Le sezioni che seguono descrivono ciascun passaggio riportato nella figura.  

[processo di arrivo![(]. /media/salesreturn03.png)](. /media/salesreturn03.png)  

Il processo sono disponibili numerose altre differenze non vengono descritte in questo argomento. Consente di eseguire alcune di queste modifiche:

-   Non utilizzare ** panoramica arrivi ** elenco per creare un giornale arrivi. In questo caso, creare manualmente il giornale di registrazione arrivi. Gli ordini di reso avranno ** ordine cliente ** come riferimento.
-   Se si utilizza la gestione magazzino, generare i trasporti pallet. La ritraccia avrà lo stato di ** arrivati ** durante il trasporto pallet.
-   Registrare l'arrivo di reso direttamente dalla riga dell'ordine di reso, utilizzando ** registrazione ** la funzione.

Durante il processo di arrivo, resi sono integrati con il processo generale per gli arrivi di magazzino. Il processo di arrivo anche supporta la creazione degli ordini di quarantena per i resi che devono subire un'ispezione separata.

### <a name="identify-products-in-the-arrival-overview-list"></a>Identificazione dei prodotti nell'elenco della panoramica arrivi

** Panoramica arrivi ** pagina vengono elencati tutti gli arrivi previsti in entrata. ** Nota: ** Gli arrivi dagli ordini di reso devono essere elaborate separatamente da altri tipi di transazioni arrivi. Dopo aver identificato un collo ** ricevuto nella panoramica arrivi ** di pagine, ad esempio utilizzando il documento accompagnante di RMA), nel riquadro azioni, fare clic su ** entrata di inizio ** per creare e inizializzare un giornale di registrazione arrivi che corrisponde all'entrata.

### <a name="edit-the-arrival-journal"></a>Modifica del giornale di registrazione arrivi

Impostando ** gestione della quarantena ** l'opzione ** Sì **, è possibile creare un ordine di quarantena per la ritraccia. Se una riga è stata inviata in quarantena per l'ispezione, non è possibile specificare un codice smaltimento. ** Nota: ** Se si imposta ** gestione della quarantena ** l'opzione ** Sì ** nel gruppo di modelli inventariali dell'articolo, ** gestione della quarantena ** l'opzione ** il giornale di registrazione le righe ** nella pagina verrà contrassegnata per la riga del giornale di registrazione arrivi e non può essere modificata. Se la riga verrà inviata a quarantena, è necessario specificare il magazzino di quarantena appropriato. Se la riga di arrivo non sottoporre a ispezione, l'addetto arrivi di magazzino deve specificare il codice di smaltimento direttamente nella riga del giornale di registrazione arrivi e quindi registrare il giornale arrivi. Se lo stesso codice smaltimento assegnato all'intera quantità di ritraccia, o se la quantità totale della riga non è stata ancora ricevuta, è necessario dividere la riga. Dopo aver diviso una riga del giornale di registrazione arrivi, vengono suddivise la ritraccia (SalesLine ** **) e si crea un nuovo ID lotto. È possibile dividere la riga riducendo la quantità della riga del giornale di registrazione arrivi. Quando il giornale viene registrato, una nuova ritraccia viene creata a cui è stato programmato ** ** per la quantità rimanente. È inoltre possibile dividere la riga facendo clic su Funzioni ** ** &gt; ** la divisione **.

### <a name="process-the-quarantine-order"></a>Elaborare l'ordine di quarantena

Se i prodotti resi vengono inviati per l'ispezione nel magazzino di quarantena, elaborare eventuali aggiuntivo è completato un ordine di quarantena. Un ordine di quarantena viene creato per ciascun la riga che viene inviata in quarantena. Codice di smaltimento indica il risultato del processo di ispezione. È possibile dividere un ordine di quarantena, così come è possibile dividere il giornale di registrazione arrivi. Se si divide l'ordine di quarantena, dovute una divisione della ritraccia. Dopo che il codice di smaltimento è specificato, completare l'ordine di quarantena utilizzando ** fine ** la funzione o ** dichiarazione di finito ** la funzione. Se si seleziona ** dichiarazione di finito **, un nuovo entrata viene creato nel magazzino designato. È possibile elaborare il entrata mediante ** panoramica arrivi ** la pagina. Se gli arrivi deriva da un ordine di quarantena, non è possibile modificare il codice smaltimento assegnato durante l'ispezione. Se il completamento dell'ordine di quarantena utilizzando ** fine ** la funzione, il lotto viene registrato automaticamente. Talvolta, un articolo può essere rinviato dalla quarantena alla spedizione e al reparto addetto. Ad esempio, l'addetto alle ispezioni della quarantena non potrebbe disporre dove posizionare l'articolo in magazzino. In questo caso, il documento di trasporto corrispondente deve essere aggiornato per registrare correttamente ed eseguire azioni sul codice smaltimento specificato a causa della quarantena. Avviso di ricevimento può essere inviato al cliente quando la ritraccia viene registrata. ** Rilevazione di reso ** il report è simile al documento dell'ordine di reso. ** Rilevazione di reso ** il report non registrato o di non viene registrato nel sistema e non costituisce un passaggio obbligatorio nel processo dell'ordine di reso.

## <a name="replace-a-product"></a>Sostituire un prodotto
Sono disponibili due metodi per la gestione di sostituzione prodotto:

-   ** Sostituzione preliminare ** - Replace un prodotto prima del prodotto restituito viene ricevuto dal cliente.
-   ** La sostituzione dal codice di smaltimento ** consente di creare automaticamente una nuova riga di ordine sostitutivo.

### <a name="up-front-replacement"></a>Sostituzione preliminare

Nella sostituzione aperta, l'articolo di sostituzione può essere consegnate al cliente prima che l'articolo venga restituito. Questo metodo è utile se, ad esempio, si tratta di un pezzo meccanico che non possono essere eliminati al pezzo di ricambio sia disponibile per prendere la sua posizione, o se si desidera semplicemente il più presto possibile il cliente che il prodotto per sostituzione. L'ordine aperto sostitutivo in un ordine cliente indipendente. Le informazioni di intestazione vengono l'inizializzazione del cliente e le informazioni relative alle righe sono l'inizializzazioneordine di reso. È possibile modificare, eliminare ed elaborazione dell'ordine sostitutivo indipendentemente dall'ordine di reso. Quando si elimina un ordine sostitutivo, verrà visualizzato un messaggio che l'ordine è stato creato come ordine sostitutivo. Nella figura seguente è illustrato il processo per la sostituzione aperta.  

[] i processi aperti in sostituzione![(https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn04.png) (https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn04.png)]  

L'ordine di reso contiene un riferimento all'ordine sostitutivo. Se un ordine aperte in sostituzione viene creato per un ordine di reso prima dell'articolo difettoso venga restituito, non è possibile selezionare i codici smaltimento per la sostituzione dopo che l'articolo è difettoso restituzione.

### <a name="replacement-by-disposition-code"></a>Sostituzione del codice smaltimento

Se si spediscono un articolo sostitutivo al cliente e si utilizza ** sostituire e scarto o ** ** sostituire e accrediti ** l'azione di smaltimentoordine di reso, utilizzare il processo che viene visualizzata nella figura seguente.  

[processo![sostituzione![quando un codice smaltimento viene utilizzato] (https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn05.png) (https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn05.png)]  

Articolo sostitutivo verrà consegnato utilizzando un ordine cliente, indipendentemente l'ordine cliente in sostituzione. Questo ordine cliente quando viene creato il documento di trasporto per l'ordine di reso viene generato. L'intestazione dell'ordine vengono utilizzate le informazioni del cliente a cui viene fatto riferimento nell'intestazione dell'ordine di reso. Le informazioni delle righe vengono raccolte in base alle informazioni immesse ** articolo sostitutivo ** nella pagina. ** Articolo sostitutivo ** la pagina deve essere rimpiazzate righe con azioni di smaltimento che iniziano con la parola "sostituito". Tuttavia, né la quantità né l'identità dell'articolo sostitutivo viene convalidata o limitata. Questo comportamento consente i casi in cui il cliente desidera lo stesso articolo ma in una configurazione o una dimensione diversa nonché i casi in cui i clienti desidera completamente un articolo diverso. Per impostazione predefinita, un gli stessi viene immesso ** articolo sostitutivo ** nella pagina. Tuttavia, è possibile selezionare un articolo diverso, a condizione che la funzione è stata installata. ** Nota: ** È possibile modificare ed eliminare l'ordine cliente in sostituzione dopo che ha creato.

## <a name="generate-a-packing-slip"></a>Generare un documento di trasporto
Affinché i resi possano essere ricevuti nel magazzino, è necessario aggiornare il documento di trasporto per l'ordine che gli articoli appartengono. Come il processo di aggiornamento della fattura rappresenta l'aggiornamento della transazione finanziaria, il processo di aggiornamento del documento di trasporto rappresenta l'aggiornamento fisico del record di inventario. Ovvero il processo commit delle modifiche al magazzino. Nel caso dei resi, i passaggi assegnati all'azione di smaltimento vengono implementati durante l'aggiornamento del documento di trasporto. Quando si genera il documento di trasporto, i seguenti eventi: si verificano

-   Nel magazzino, il processo standard viene utilizzato per eseguire una entrata fisica. Le registrazioni contabili vengono generate se il gruppo di modelli inventariali (** registrare l'inventario fisico **) e i parametri di Contabilità clienti (** documento di trasporto di registrazione nella contabilità generale **) sono impostati in modo appropriato.
-   Gli articoli che sono stati contrassegnati con un'azione di smaltimento che contiene la parola "e" vengono ridotti e perdite di magazzino viene registrato nella contabilità generale.
-   Gli articoli che sono stati contrassegnati con ** reso al cliente ** l'azione di smaltimento vengono ricevuti e consegnati direttamente al cliente. Questi articoli non influiscono su l netto.
-   Un ordine cliente in sostituzione viene creato. L'ordine cliente è basato su informazioni ** articolo sostitutivo ** nella pagina.

È possibile generare il documento di trasporto solo per le righe delle fatture ordine fornitore di reso ** ** e registrato solo per l'intera quantità in ritraccia. Se più righe dell'ordine di reso è registrato ** ** lo stato, è possibile generare il documento di trasporto per un sottoinsieme delle righe eliminazione di altre righe ** documento di trasporto di registrazione ** dalla pagina. I resi parziali vengono definiti in base a righe dell'ordine di reso, non in termini di spedizioni degli ordini di reso. Di conseguenza, se si riceve l'intera quantità indicata in una riga di ordine di reso, ma non si riceve niente di quanto specificato nelle altre righe dell'ordine di reso, la consegna non è una consegna parziale. Tuttavia, se una riga di ordine di reso che richiede 10 unità di un articolo vengano restituite quattro, ma si ricevono solo unità, la consegna è una consegna parziale. Se non tutti i resi previsti sono arrivati, è possibile accantonare la spedizione e attendere l'arrivo della quantità rimanente per il calcolo. In alternativa, è possibile registrare e la quantità parziale. Durante il processo di registrazione dei documenti di trasporto, è possibile associare il numero di riferimento del documento di trasporto indicato nei documenti di spedizione del cliente alle righe dell'ordine. Questa associazione è facoltativa ed è solo a scopo di riferimento. E non comporta l'esecuzione di aggiornamenti transazionali. È possibile ignorare nel processo del documento di trasporto e passare direttamente alla fatturazione. In questo caso, le operazioni che per eseguito durante la generazione di documenti di trasporto vengono completate durante la fatturazione.

## <a name="generate-an-invoice"></a>Genera fattura
Sebbene ** ordine di reso ** la pagina contenente le informazioni e le azioni necessarie per la gestione degli aspetti logistici speciali l'ordine di reso, è necessario utilizzare ** ordine cliente ** la pagina per completare il processo di fatturazione. L'organizzazione può quindi fatturare gli ordini e ordini cliente di reso contemporaneamente e la stessa persona può completare il processo di fatturazione, a seconda delle esigenze. Per visualizzare l'ordine di reso ** ** ordine cliente dalla pagina, fare clic sul collegamento del numero di ordine cliente possibile aprire l'ordine cliente associato. È inoltre possibile individuare l'ordine di reso ** tutti gli ordini cliente ** nella pagina. Gli ordini di reso vengono ordini cliente di tipo ordine ** Ordine di reso **.

### <a name="credit-correction"></a>Correzione credito

Durante il processo di fatturazione, verificare che tutte le spese varie e magazzini. Per determinare le registrazioni contabili per diventare correzioni (Storno), valutare l'opportunità di utilizzare ** correzione del credito ** l'opzione ** un'altra ** nella scheda ** fattura di registrazione ** della pagina si registra la fattura o della nota di accredito. ** Nota: ** Per impostazione predefinita, ** correzione del credito ** l'opzione è attivata se ** nota di accredito come correzione ** l'opzione ** parametri di contabilità clienti ** nella pagina è stata attivata. Tuttavia, è consigliabile non registrare le dichiarazioni a Storno.

## <a name="create-intercompany-return-orders"></a>Creare ordini di reso interaziendali
Gli ordini di reso possono essere completati tra due società della propria organizzazione. Negli scenari seguenti sono supportati:

-   Il sistema di gestione interaziendale semplice preferibile tra due società appartenenti a una relazione interaziendale
-   Una catena interaziendale che viene stabilita quando un ordine di reso cliente viene creato nella società venditrice
-   Una catena interaziendale che viene stabilita quando un ordine di reso fornitore viene creato nella società acquirente
-   La spedizione diretta di consegna è preferibile tra un cliente esterno e due società appartenenti a una relazione interaziendale

### <a name="setup"></a>Imposta

Nella seguente figura l'impostazione minima necessaria per due società è a una relazione interaziendale e per consentire il commercio interaziendale.  

[![Minimum setup](https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn06.png)](https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn06.png)  

Nel seguente scenario, CompBuy è la società acquirente e CompSell è la società venditrice. In genere, la società venditrice spedisce le merci alla società acquirente o, in scenari nella spedizione di consegna, direttamente al cliente finale. In CompBuy, l'IC\_CompSell del fornitore viene definito come endpoint interaziendale associato alla società CompSell. Contemporaneamente, in CompSell, l'IC\_CompBuy del cliente viene definito come endpoint interaziendale associato alla società CompBuy. I dettagli dei criteri azioni appropriata e copiare i mapping di valori devono essere definiti in entrambe le società. In uno scenario nella spedizione di consegna, un ordine di reso interaziendali, che corrisponde a un ordine cliente interaziendale, viene creato nella società venditrice. Codice NAR dell'ordine di reso interaziendali può essere selezionato dalla sequenza di codici NAR in CompSell, oppure può essere copiato dal codice NAR assegnato all'ordine di reso originario in CompBuy. Le impostazioni del codice NAR ** PurchaseRequisition ** sui criteri azioni in CompBuy determinano le azioni. Se il codice NAR viene sincronizzato, è necessario pianificare attenuare del rischio di numero di scontri se le due società utilizzano la stessa sequenza numerica.

### <a name="simple-intercompany-returns"></a>Tornare semplici interaziendale

Questo scenario interessa due società incluse nella stessa organizzazione, come illustrato nella figura seguente.  

[] semplice reso![(https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn07.png) (https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn07.png)]  

La catena degli ordini può essere impostato quando un ordine di reso fornitore viene creato nella società acquirente o un ordine di reso cliente viene creato nella società venditrice. Dynamics 365 per le operazioni crea l'ordine corrispondente nell'altra società e garantisce che l'intestazione e le informazioni sulla riga dell'ordine di reso fornitore riflettano le impostazioni nell'ordine di reso di un cliente. L'ordine di reso che è definito può includere o escludere il riferimento (** ordine cliente Trova **) a una fattura di vendita esistente. I documenti di trasporto e fatture dei due ordini possono essere elaborati singolarmente. Ad esempio, non sarà necessario generare un documento di trasporto per l'ordine di reso fornitore prima di generare il documento di trasporto per l'ordine di reso di un cliente.

### <a name="direct-delivery-shipment-returns-among-three-parties"></a>Tornare diretti di spedizione di consegna tra tre fasi

Questo scenario è possibile verificare se una vendita precedente ** consegna diretta ** di tipo è stata completata e se una fattura al cliente è disponibile nella società che interagisce con il cliente. Nella seguente figura, la società CompBuy precedentemente ha venduto prodotti e fatturati al cliente esterno. I prodotti sono stati spediti direttamente dalla società CompSell al cliente da catena di ordini interaziendali.  

[resi diretti di spedizione di consegna![tra tre fasi] (https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn08.png) (https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn08.png)]  

Se il cliente esterno desidera restituire i prodotti, un ordine di reso (RMA02) viene creato per il cliente nella società CompBuy. Per stabilire la catena interaziendale, l'ordine di reso deve essere contrassegnato per la consegna diretta. Quando si utilizza ** ordine cliente Trova ** viene eseguito per selezionare la fattura cliente da restituire, una catena di ordini interaziendali costituita dai seguenti documenti viene stabilita:

-   ** Ordine di reso originale: ** RMA02 (società CompBuy)
-   ** Ordine fornitore: ** PO02 (società CompBuy)
-   ** Ordine di reso interaziendale: ** RMA\_00032 (società CompSell)

Dopo che la catena interaziendale di consegna diretta viene creata, gestione ed elaborare qualsiasi fisici dei resi devono verificarsi nel contesto dell'ordine di reso interaziendali, RMA\_00032 nella società CompSell. I prodotti non possono essere ricevuti nella società CompBuy. Quando un codice smaltimento assegnato all'ordine di reso interaziendali, viene sincronizzato con l'ordine di reso originale per consentire la fatturazione dell'ordine originale.

## <a name="post-to-the-ledger"></a>Eseguire registrazioni nella contabilità generale
Le registrazioni contabili generate quando l'ordine di reso viene fatturato sono influenzate da altri parametri e impostazioni principali:

-   ** Il prezzo di costo reso ** - per i modelli inventariali diverso da ** costo standard, ** ** prezzo di costo reso ** il parametro determina il costo del prodotto durante ha accettato al magazzino o scartato. Per calcolare una valutazione del magazzino corretta, è importante definito ** prezzo di costo reso ** il parametro correttamente. Se si utilizza ** ordine cliente Trova ** viene eseguito per creare una riga di ordine di reso che contiene un riferimento a una fattura cliente, ** prezzo di costo reso ** il valore corrisponde al prezzo di costo dell'articolo che viene venduto. In caso contrario, il valore dei prezzi di costo per articolo viene installato oppure può essere immesso manualmente.
-   ** La rettifica/Storno di credito ** - ** correzione del credito ** il parametro ** fattura di registrazione ** nella pagina determina se le registrazioni devono essere registrate come voci in DR/CR () o come voci, correggendo negative.

Negli esempi successive, il prezzo di costo reso è rappresentato come ** Inv. Prezzo di costo **.

### <a name="example-1-the-return-order-doesnt-reference-a-customer-invoice"></a>Esempio 1: L'ordine di reso non fa riferimento a una fattura cliente

L'ordine di reso non fa riferimento a una fattura cliente. L'articolo restituito viene registrato in Avere. ** Correzione credito ** il parametro non è selezionata quando la fattura dell'ordine di reso, o nota di accredito, viene generata.  

[l'ordine di reso![non fa riferimento a un cliente invoic] (https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn09.png) (https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn09.png)]  

** Nota: ** Il prezzo del record generale dell'articolo viene utilizzato come impostazione predefinita per ** prezzo di costo reso ** il parametro. Il prezzo predefinito è diverso dal prezzo di costo al momento dell'uscita da magazzino. Di conseguenza, la implicazione che è una perdita di 3 è stata sostenuta. Inoltre, l'ordine di reso non include lo sconto che sia stato concesso al cliente nell'ordine cliente. Di conseguenza, un'impostazione di credito viene eseguita in eccesso.

### <a name="example-2-credit-correction-is-selected-for-the-return-order"></a>Esempio 2: La correzione del credito è selezionata per l'ordine di reso

Esempio 2 corrisponde all'esempio 1, ma ** correzione del credito ** il parametro è selezionato quando la fattura dell'ordine di reso è stata generata.  

[ordine di reso![in cui la correzione del credito è selezionata (https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn10.png)] (https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn10.png)]  

** Nota: ** Le registrazioni contabili vengono immesse come correzioni negative.

### <a name="example-3-the-return-order-line-is-created-by-using-the-find-sales-order-function"></a>Esempio 3: La riga dell'ordine di reso viene creata utilizzando la funzione di ordine cliente Trova

In questo esempio, la riga ordine di reso verrà creata utilizzando ** ordine cliente Trova ** la funzione. ** Correzione credito ** il parametro non è selezionata quando la fattura.  

[riga dell'ordine di reso![che viene creata utilizzando l'ordine cliente] Trova (https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn11.png) (https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn11.png)]  

** Nota: ** ** Sconto ** e ** prezzo di costo reso ** vengono impostati correttamente. Di conseguenza, uno storno esatto della fattura cliente viene eseguita.


