---
title: Resi su vendite
description: "In questo argomento vengono fornite informazioni sul processo per gli ordini di reso. Sono riportate informazioni sui resi dei clienti e sul relativo effetto sulle quantità di scorte disponibili e di determinazione costi."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 269384
ms.assetid: 98a4b517-e606-4036-b55f-1ab248898bdf
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-02-28T00:00:00.000Z
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: b66bf79413ad21f12f789eabafe8413af3f58c9c
ms.contentlocale: it-it
ms.lasthandoff: 06/13/2017

---

# <a name="sales-returns"></a>Resi su vendite

[!include[banner](../includes/banner.md)]


In questo argomento vengono fornite informazioni sul processo per gli ordini di reso. Sono riportate informazioni sui resi dei clienti e sul relativo effetto sulle quantità di scorte disponibili e di determinazione costi.

I clienti possono rendere gli articoli per diversi motivi. Ad esempio, un articolo potrebbe essere difettoso o potrebbe non soddisfare le aspettative del cliente. Il processo di reso inizia quando un cliente genera una richiesta per restituire un articolo. Dopo che la richiesta del cliente viene ricevuta, viene creato un ordine di reso in Microsoft Dynamics 365 for Finance and Operations.

## <a name="return-order-process"></a>Processo relativo all'ordine di reso
Nell'illustrazione riportata di seguito viene fornita una panoramica del processo relativo all'ordine di reso.  

[![salesreturns01](./media/salesreturns01.jpg)](./media/salesreturns01.jpg)  

Sono disponibili due tipi di processi dell'ordine di reso: reso fisico e solo credito.

-   **Reso fisico** - l'ordine di reso autorizza la restituzione fisica dei prodotti.
-   **Solo credito** - l'ordine di reso autorizza un credito al cliente, senza che sia necessaria la restituzione fisica dei prodotti.

### <a name="physical-return-order-process"></a>Processo relativo all'ordine di reso fisico

1.  **Creare un ordine di reso.** Documentare formalmente l'autorizzazione per il cliente a rendere tutti i prodotti difettosi o indesiderati. L'ordine di reso non richiede che la società accetti i prodotti resi o fornisca un credito per il cliente. Se il reso viene accettato, è possibile autorizzare l'invio di un articolo sostitutivo prima che l'articolo difettoso venga restituito.
2.  **Arrivare in magazzino per l'ispezione.** Eseguire un'ispezione iniziale e una convalida rispetto al documento dell'ordine di reso. L'ordine di reso supporta anche la quarantena degli articoli resi per l'ispezione e il controllo di qualità aggiuntivi.
3.  **Determinare lo smaltimento.** Finalizzare il processo di ispezione e determinare le operazioni da eseguire relativamente ai prodotti resi. In questa fase decidere se effettuare il credito al cliente, rifiutare o accettare il reso del prodotto, scartare il prodotto e inviare un prodotto sostitutivo al cliente.
4.  **Generare un documento di trasporto.** Generare un documento di trasporto e confermare la decisione di smaltimento presa nel passaggio 3. Finalizzare i processi di logistica.
5.  **Generare una fattura.** Chiudere l'ordine di reso.

### <a name="credit-only-process"></a>Processo solo credito

1.  **Creare un ordine di reso.** Documentare formalmente l'autorizzazione per il cliente a ricevere un credito senza restituire i prodotti difettosi o indesiderati. Il codice smaltimento **Solo credito** autorizza la decisione per l'accredito al cliente senza reso fisico.
2.  **Generare una fattura.** Generare la nota di accredito, quindi chiudere l'ordine di reso.

## <a name="return-material-authorization"></a>Autorizzazione reso
L'elaborazione dell'Autorizzazione reso (NAR) si basa sulla funzionalità dell'ordine cliente. Un NAR viene registrato come un ordine di reso, che viene creato come ordine cliente e può contenere un altro ordine cliente associato, definito ordine sostitutivo. Entrambi gli ordini clienti collegano al codice NAR di origine.

-   **Ordine di reso** - per registrare un NAR, si crea un ordine di reso, ovvero un ordine cliente con il tipo assegnato, **Ordine di reso**. Tutte le modifiche apportate alle informazioni di NAR vengono aggiornate automaticamente nell'ordine cliente. Fino a quando l'ordine di reso ha stato **Aperto**, non verrà visualizzato nell'elenco degli ordini cliente. I NAR vengono utilizzati per la gestione degli arrivi e il ricevimento dei resi, nonché per autorizzare un'azione di smaltimento di solo credito (vedere la sezione **Codici smaltimento e azioni di smaltimento**). Tutti gli altri processi di follow-up devono essere gestiti nell'ordine cliente.
-   **Ordine sostitutivo** - quando un ordine sostitutivo deve essere inviato al cliente, il NAR può includere un secondo ordine cliente associato. È possibile creare manualmente un ordine sostitutivo perché il NAR supporti la spedizione immediata. In alternativa, è possibile creare l'ordine sostitutivo automaticamente dopo che l'arrivo, il controllo e l'entrata sono stati completati per l'articolo NAR con codice smaltimento che indica la sostituzione. L'ordine sostitutivo ha la stessa funzionalità associata a un ordine cliente. Ad esempio, è possibile utilizzarlo per configurare un prodotto personalizzato come articolo di sostituzione, creare un ordine di produzione per riparare un reso, creare un ordine acquisto con consegna diretta per inviare la sostituzione da un fornitore o per supportare scopi diversi.

## <a name="create-a-return-order"></a>Creare un ordine di reso
Il processo dell'ordine di reso inizia quando un cliente contatta l'organizzazione per restituire un prodotto difettoso o indesiderato e/o per ricevere un accredito. Dopo che l'organizzazione accetta il reso, il reso viene documentato con un ordine di reso. L'ordine di reso diventa il punto focale dell'elaborazione interna dell'articolo restituito. Nell'illustrazione che segue è descritta la procedura per la creazione di un ordine di reso.  

[![Procedura per creare un ordine di reso](./media/salesreturn02.png)](./media/salesreturn02.png)

### <a name="create-a-return-order-header"></a>Creare un'intestazione di ordine di reso

Quando si crea un ordine di reso, le informazioni nella tabella che segue devono essere incluse.

| Campo              | descrizione                                              | Commenti                                                                                                                                                                                                                                                                                                                                        |
|--------------------|----------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Account cliente   | Un riferimento alla tabella Clienti                       | È necessario immettere un conto cliente esistente.                                                                                                                                                                                                                                                                                                  |
| Indirizzo di consegna   | Indirizzo al quale viene restituito l'articolo                 | Per impostazione predefinita, viene utilizzato l'indirizzo dell'organizzazione. Se nell'intestazione viene selezionato un magazzino specifico, l'indirizzo di consegna viene modificato nell'indirizzo di consegna del magazzino. È possibile modificare questo indirizzo nella pagina **Dettagli ordini di reso**.                                                                                                  |
| Sito/magazzino     | Sito o magazzino che riceve il prodotto reso | L'indirizzo di consegna dell'ordine di reso viene determinato in base all'indirizzo di consegna del sito o del magazzino.                                                                                                                                                                                                                                 |
| Codice NAR         | ID assegnato all'ordine di reso              | Viene utilizzato come chiave alternativa nel corso del processo relativo all'ordine di reso. Il codice NAR assegnato si basa sulla sequenza numerica NAR impostata nella pagina **Parametri contabilità clienti**.                                                                                                                              |
| Scadenza           | Ultima data in cui un articolo può essere restituito               | Il valore predefinito viene calcolato in base alla data corrente cui viene aggiunto il periodo di validità. Ad esempio, se un reso è valido solo per 90 giorni dalla data in cui l'ordine di reso viene creato e se l'ordine di reso è stato creato il 1° maggio, il campo sarà impostato su **30 luglio**. Il periodo di validità viene impostato nella pagina **Parametri contabilità clienti**. |
| Codice motivo reso | Motivo del cliente per la restituzione degli articoli          | Il codice motivo è selezionato nell'elenco dei codici motivo definiti dall'utente. È possibile aggiornare questo campo in qualsiasi momento.                                                                                                                                                                                                                                    |

### <a name="create-return-order-lines"></a>Crea righe ordine di reso

Dopo aver completato l'intestazione di reso, è possibile creare righe di reso utilizzando uno dei seguenti metodi:

-   Immettere manualmente i dettagli dell'articolo, la quantità e altre informazioni per ogni riga di reso.
-   Creare una riga di reso utilizzando la funzione **Trova ordine cliente**. Si consiglia di utilizzare questa funzione quando si crea un ordine di reso. La funzione **Trova ordine cliente** stabilisce un riferimento dalla riga di reso alla riga dell'ordine cliente fatturata e recupera dettagli riga, quali il numero di articolo, la quantità, il prezzo, lo sconto e i valori di costo dalla riga di vendita. Il riferimento consente di garantire che, quando il prodotto viene restituito alla società, sia valutato allo stesso costo unitario di vendita. Il riferimento conferma inoltre che gli ordini di reso non sono creati per una quantità superiore a quella venduta indicata in fattura.

**Nota:** le righe di reso con un riferimento a un ordine cliente vengono gestite come rettifiche o storni della vendita. Per ulteriori informazioni, vedere la sezione relativa alla registrazione nella contabilità generale più avanti in questo argomento.

### <a name="charges"></a>Spese

Commissioni e addebiti possono essere aggiunti all'ordine di reso tramite uno o più dei seguenti metodi:

-   È possibile aggiungere manualmente addebiti all'intestazione dell'ordine di reso, alla riga dell'ordine di reso o a entrambe.
-   Gli addebiti possono essere aggiunti automaticamente all'intestazione dell'ordine di reso come funzione del codice motivo reso.
-   Gli addebiti possono essere aggiunti automaticamente alla riga dell'ordine di reso in base al codice smaltimento della riga.

Gli addebiti vengono aggiunti automaticamente dopo che un codice motivo reso o il codice smaltimento è assegnato alla riga. Se il codice motivo viene cambiato in un secondo momento, la voce di addebito esistente non verrà deselezionata, ma potrebbe essere aggiunta una nuova voce di addebito, in base al nuovo codice motivo. Quando si aggiungono addebiti alle righe dell'ordine di reso, gli addebiti calcolati in base alla percentuale del valore della riga o dell'ordine diventano negativi quando la riga o l'ordine della riga è negativo, a meno che anche la percentuale non sia un numero negativo. Un addebito con valore negativo rappresenta un credito del cliente.

### <a name="return-reason-codes"></a>Codici motivo reso

Applicando codici motivo ai resi, è possibile rendere i modelli di restituzione più semplici da analizzare. I codici motivo forniscono informazioni sul motivo per cui un cliente desidera restituire gli articoli. Alcune organizzazioni hanno numerosi codici motivo. Queste organizzazioni potrebbero raggruppare i codici motivo in gruppi di codici motivo per ottenere una panoramica più dettagliata e per creare report cumulati.

### <a name="disposition-codes-and-disposition-actions"></a>Codici smaltimento e azioni di smaltimento

Un passaggio fondamentale nel processo dell'ordine di reso è l'assegnazione di un codice smaltimento alla riga dell'ordine di reso nella registrazione arrivi. Il codice smaltimento determina le seguenti informazioni:

-   **Le implicazioni finanziarie** - Al cliente deve essere accreditato l'importo degli articoli resi ed eventuali addebiti devono essere aggiunti alla riga dell'ordine di reso?
-   **Lo smaltimento dell'articolo reso** - L'articolo deve essere aggiunto di nuovo al magazzino, deve essere scartato o deve essere restituito al cliente?
-   **La logistica dell'articolo reso** - Un articolo sostitutivo deve essere rilasciato al cliente?

Oltre a stabilire la modalità di smaltimento delle merci rese, i codici smaltimento possono determinare gli addebiti da applicare alla riga di reso. Possono inoltre essere utilizzati per raggruppare i resi ed eseguire analisi statistiche. I codici smaltimento vengono definiti nell'ambito dell'impostazione degli ordini di reso. Tuttavia, ogni codice smaltimento deve fare riferimento a una delle azioni di smaltimento incorporate. Nella tabella che segue vengono elencati i codici smaltimento e le relative azioni. **Importante:** se un articolo non deve essere restituito, ma il cliente deve ancora ricevere l'accredito, assegnare il codice smaltimento **Solo credito** alla riga di reso.

<table>
<thead>
<tr class="header">
<th>Codice smaltimento</th>
<th>Implicazioni finanziarie</th>
<th>Implicazioni per la logistica</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Solo credito</td>
<td><ul>
<li>Al cliente viene accreditato il prezzo di vendita meno le commissioni o gli addebiti.</li>
<li>Le perdite dovute allo scarto dell'articolo sono registrate nella contabilità generale.</li>
</ul></td>
<td>L'articolo non deve essere restituito. Questa azione di smaltimento viene utilizzata per i seguenti casi:
<ul>
<li>Esiste una relazione di fiducia sufficiente tra le parti.</li>
<li>Il costo del reso di un articolo difettoso è proibitivo.</li>
<li>Gli articoli non possono essere riammessi in magazzino. Per altri motivi un reso fisico non è obbligatorio.</li>
</ul></td>
</tr>
<tr class="even">
<td>Avere</td>
<td><ul>
<li>Al cliente viene accreditato il prezzo di vendita meno le commissioni o gli addebiti.</li>
<li>Il valore di magazzino viene aumentato dal costo del reso.</li>
</ul></td>
<td>L'articolo viene restituito e aggiunto di nuovo al magazzino.</td>
</tr>
<tr class="odd">
<td>Sostituzione e credito</td>
<td><ul>
<li>Al cliente viene accreditato il prezzo di vendita meno le commissioni o gli addebiti.</li>
<li>Il valore di magazzino aumenta del costo del reso.</li>
<li>Un ordine cliente distinto per una sostituzione viene creato e gestito separatamente.</li>
</ul></td>
<td>L'articolo viene restituito e aggiunto di nuovo al magazzino.</td>
</tr>
<tr class="even">
<td>Sostituzione e scarto</td>
<td><ul>
<li>Al cliente viene accreditato il prezzo di vendita, meno le commissioni o gli addebiti.</li>
<li>Le perdite dovute allo scarto dell'articolo sono registrate nella contabilità generale.</li>
<li>Un ordine cliente distinto per una sostituzione viene creato e gestito separatamente.</li>
</ul></td>
<td>L'articolo viene reso e scartato.</td>
</tr>
<tr class="odd">
<td>Reso a cliente</td>
<td>Nessuno, tranne eventuali commissioni o addebiti.</td>
<td>L'articolo viene reso, ma viene restituito al cliente dopo l'ispezione. Questa azione di smaltimento potrebbe essere utilizzata se l'articolo è stato danneggiato deliberatamente o se la garanzia è stata annullata.</td>
</tr>
<tr class="even">
<td>Scarti</td>
<td><ul>
<li>Al cliente viene accreditato il prezzo di vendita meno le commissioni o gli addebiti.</li>
<li>Le perdite dovute allo scarto dell'articolo sono registrate nella contabilità generale.</li>
</ul></td>
<td>L'articolo viene reso o scartato.</td>
</tr>
</tbody>
</table>

## <a name="arrival-at-the-warehouse-for-inspection"></a>Arrivo in magazzino per l'ispezione
Prima di poter ricevere fisicamente gli articoli resi in magazzino tramite la registrazione di un documento di trasporto, gli articoli devono essere registrati all'arrivo e sottoposti a un'ispezione facoltativa. Nell'illustrazione riportata di seguito viene fornita una panoramica del processo di arrivo. Le sezioni che seguono descrivono ciascun passaggio riportato nella figura.  

[![Processo di arrivo](./media/salesreturn03.png)](./media/salesreturn03.png)  

Il processo presenta numerose altre differenze, che non vengono descritte in questo argomento. Di seguito ne sono riportate alcune:

-   Non utilizzare l'elenco **Panoramica arrivi** per creare un giornale arrivi. Creare invece manualmente il giornale di registrazione arrivi. Gli ordini di reso avranno **Ordine cliente** come riferimento.
-   Se si utilizza la gestione magazzino, generare i trasporti pallet. La riga di reso avrà lo stato di **Arrivata** durante il trasporto pallet.
-   Registrare l'arrivo dell'articolo reso direttamente dalla riga dell'ordine di reso, utilizzando la funzione **Registrazione**.

Durante il processo di arrivo i resi si integrano nel processo generale degli arrivi in magazzino. Il processo di arrivo supporta anche la creazione di ordini di quarantena per i resi che devono subire un'ispezione separata.

### <a name="identify-products-in-the-arrival-overview-list"></a>Identificare i prodotti nell'elenco della panoramica degli arrivi

Nella pagina **Panoramica arrivi** vengono elencati tutti gli arrivi previsti in entrata. **Nota:** gli arrivi provenienti dagli ordini di reso devono essere elaborati separatamente da altri tipi di transazioni di arrivi. Dopo aver identificato un collo ricevuto nella pagina **Panoramica arrivi** (ad esempio utilizzando il documento NAR di accompagnamento), nel riquadro azioni fare clic su **Inizia arrivo** per creare e inizializzare un giornale di registrazione arrivi che corrisponda all'arrivo.

### <a name="edit-the-arrival-journal"></a>Modificare il giornale di registrazione arrivi

Impostando l'opzione **Gestione quarantena** su **Sì**, è possibile creare un ordine di quarantena per la riga di reso. Se una riga è stata inviata in quarantena per l'ispezione, non è possibile specificare un codice smaltimento. **Nota:** se si imposta l'opzione **Gestione quarantena** su **Sì** nel gruppo di modelli inventariali dell'articolo, l'opzione **Gestione quarantena** nella pagina **Righe giornale di registrazione** verrà contrassegnata per la riga del giornale di registrazione arrivi e non potrà essere modificata. Se la riga verrà inviata in quarantena, è necessario specificare il magazzino di quarantena appropriato. Se la riga di arrivo non è sottoposta a ispezione, l'addetto arrivi in magazzino deve specificare il codice smaltimento direttamente nella riga del giornale di registrazione arrivi e quindi registrare il giornale arrivi. Se lo stesso codice smaltimento non deve essere assegnato all'intera quantità della riga di reso o se la quantità totale della riga non è stata ancora ricevuta, è necessario dividere la riga. Dopo aver diviso una riga del giornale di registrazione arrivi, viene suddivisa anche la riga di reso (**SalesLine**) e creato un nuovo ID lotto. È possibile dividere la riga riducendo la quantità della riga del giornale di registrazione arrivi. Quando il giornale viene registrato, viene creata una nuova riga di reso con stato **Attesa** per la quantità rimanente. È inoltre possibile dividere la riga facendo clic su **Funzioni** &gt; **Dividi**.

### <a name="process-the-quarantine-order"></a>Elaborare l'ordine di quarantena

Se i prodotti resi vengono inviati per l'ispezione nel magazzino di quarantena, un'eventuale elaborazione aggiuntiva è completata in un ordine di quarantena. Un ordine di quarantena viene creato per ciascuna riga di arrivo che viene inviata in quarantena. Il codice smaltimento indica il risultato del processo di ispezione. È possibile dividere un ordine di quarantena, così come è possibile dividere il giornale di registrazione arrivi. Se si divide l'ordine di quarantena, si provoca una divisione corrispondente della riga di reso. Dopo l'inserimento del codice smaltimento, completare l'ordine di quarantena utilizzando la funzione **Fine** o **Dichiarazione di finito**. Se si seleziona **Dichiarazione di finito**, viene creato un nuovo arrivo nel magazzino designato. È possibile quindi elaborare l'arrivo mediante la pagina **Panoramica arrivi**. Se l'arrivo deriva da un ordine di quarantena, non è possibile modificare il codice smaltimento assegnato durante l'ispezione. Se si completa l'ordine di quarantena utilizzando la funzione **Fine**, il lotto viene automaticamente registrato. Talvolta, un articolo può essere rinviato dalla quarantena alla spedizione e al reparto addetto al ricevimento. Ad esempio, l'addetto alle ispezioni della quarantena potrebbe non sapere dove posizionare l'articolo in magazzino. In questo caso il documento di trasporto corrispondente deve essere aggiornato per registrare correttamente ed eseguire azioni sul codice smaltimento specificato a causa della quarantena. La conferma della ricezione può essere inviata al cliente quando la riga di reso viene registrata. Il report **Conferma reso** è simile al documento dell'ordine di reso. Il report **Conferma reso** non è inserito nel giornale di registrazione né è in altro modo registrato nel sistema e non costituisce un passaggio obbligatorio nel processo dell'ordine di reso.

## <a name="replace-a-product"></a>Sostituire un prodotto
Sono disponibili due metodi per la gestione della sostituzione prodotto:

-   **Sostituzione preliminare** - Sostituire un prodotto prima che il prodotto reso venga consegnato dal cliente.
-   **Sostituzione in base al codice smaltimento** - Consente di creare automaticamente una nuova riga di ordine sostitutivo.

### <a name="up-front-replacement"></a>Sostituzione preliminare

Nella sostituzione preliminare l'articolo sostitutivo può essere consegnato al cliente prima che avvenga il reso. Questo metodo è utile se, ad esempio, l'articolo è un pezzo meccanico che non può essere eliminato se non è disponibile un pezzo di ricambio o se si desidera semplicemente che il cliente abbia il prodotto sostitutivo al più presto. L'ordine sostitutivo preliminare è un ordine cliente indipendente. Le informazioni di intestazione vengono inizializzate dal cliente e le informazioni relative alle righe vengono inizializzate dall'ordine di reso. È possibile modificare, elaborare ed eliminare l'ordine sostitutivo indipendentemente dall'ordine di reso. Quando si elimina un ordine sostitutivo, viene visualizzato un messaggio che l'ordine è stato creato come ordine sostitutivo. Nella figura seguente è illustrato il processo per la sostituzione preliminare.  

[![Processo di sostituzione preliminare](https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn04.png)](https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn04.png)  

L'ordine di reso contiene un riferimento all'ordine sostitutivo. Se un ordine sostitutivo preliminare viene creato per un ordine di reso prima della restituzione dell'articolo difettoso, non è possibile selezionare i codici smaltimento da sostituire dopo che l'articolo difettoso è stato reso.

### <a name="replacement-by-disposition-code"></a>Sostituzione in base al codice smaltimento

Se si spedisce un articolo sostitutivo al cliente e si utilizza l'azione di smaltimento **Sostituzione e scarto** o **Sostituzione e credito** sull'ordine di reso, utilizzare il processo che viene visualizzato nella figura seguente.  

[![Processo di sostituzione quando viene utilizzato un codice smaltimento](https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn05.png)](https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn05.png)  

L'articolo sostitutivo verrà consegnato utilizzando un ordine cliente indipendente, l'ordine cliente sostitutivo. Questo ordine cliente viene creato quando il documento di trasporto per l'ordine di reso viene generato. L'intestazione dell'ordine utilizza le informazioni del cliente cui viene fatto riferimento nell'intestazione dell'ordine di reso. Le informazioni delle righe vengono raccolte in base alle informazioni immesse nella pagina **Articolo sostitutivo**. La pagina **Articolo sostitutivo** deve essere specificata nelle righe con azioni di smaltimento che iniziano con la parola "sostituire". Tuttavia, né la quantità né l'identità dell'articolo sostitutivo vengono convalidate o limitate. Questo comportamento prende in considerazione i casi in cui il cliente desidera lo stesso articolo, ma in una configurazione o dimensione diversa, nonché i casi in cui i clienti desiderano un articolo completamente diverso. Per impostazione predefinita, nella pagina **Articolo sostitutivo** viene immesso un articolo identico. Tuttavia, è possibile selezionare un articolo diverso, a condizione che la funzione sia stata installata. **Nota:** è possibile modificare ed eliminare l'ordine cliente sostitutivo dopo che è stato creato.

## <a name="generate-a-packing-slip"></a>Generare un documento di trasporto
Affinché i resi possano essere ricevuti nel magazzino, è necessario aggiornare il documento di trasporto relativo all'ordine cui essi si riferiscono. Come il processo di aggiornamento della fattura rappresenta l'aggiornamento della transazione finanziaria, il processo di aggiornamento del documento di trasporto rappresenta l'aggiornamento fisico del record di magazzino. In altre parole, consente di eseguire il commit delle modifiche nel magazzino. Nel caso dei resi, i passaggi assegnati all'azione di smaltimento vengono implementati durante l'aggiornamento del documento di trasporto. Quando si genera il documento di trasporto, si verificano i seguenti eventi:

-   Nel magazzino il processo standard viene utilizzato per eseguire un'entrata fisica. Le registrazioni contabili vengono generate se il gruppo di modelli inventariali (**Registra inventario fisico**) e i parametri di Contabilità clienti (**Registra il documento di trasporto nella contabilità generale**) sono impostati in modo appropriato.
-   Gli articoli che sono stati contrassegnati con un'azione di smaltimento che contiene la parola "scarto" vengono scartati e le perdite di magazzino vengono registrate nella contabilità generale.
-   Gli articoli che sono stati contrassegnati con l'azione di smaltimento **Reso a cliente** vengono ricevuti e consegnati al cliente. Questi articoli non influiscono sulle scorte.
-   Viene creato un ordine cliente sostitutivo. L'ordine cliente si basa su informazioni contenute nella pagina **Articolo sostitutivo**.

È possibile generare il documento di trasporto solo per le righe che hanno uno stato di reso **Registrato** e solo per l'intera quantità sulla riga di reso. Se più righe dell'ordine di reso hanno lo stato **Registrato**, è possibile generare il documento di trasporto per un sottoinsieme delle righe eliminando le altre righe dalla pagina **Registra documento di trasporto**. I resi parziali vengono definiti in termini di righe di ordini di reso, non in termini di spedizioni di ordini di reso. Pertanto, se si riceve l'intera quantità indicata in una singola riga dell'ordine di reso ma non si riceve niente di quanto specificato nelle altre righe dell'ordine, la consegna non è da considerarsi parziale. Se tuttavia una riga dell'ordine di reso richiede ad esempio che vengano restituite dieci unità di un determinato articolo, ma si ricevono solo quattro unità, la consegna è parziale. Se non tutti i resi previsti sono arrivati, è possibile accantonare la spedizione e attendere l'arrivo della quantità rimanente. In alternativa, è possibile registrare la quantità parziale. Durante il processo di registrazione del documento di trasporto è possibile associare il numero di riferimento del documento di trasporto indicato nei documenti di spedizione del cliente alle righe dell'ordine. Questa associazione facoltativa serve solo a scopo di riferimento e non comporta l'esecuzione di aggiornamenti transazionali. In generale è possibile ignorare il processo del documento di trasporto e passare direttamente alla fatturazione. In questo caso le operazioni che avrebbero dovuto essere eseguite durante la generazione dei documenti di trasporto vengono completate durante la fatturazione.

## <a name="generate-an-invoice"></a>Genera fattura
Sebbene la pagina **Ordine di reso** contiene le informazioni e le azioni necessarie per la gestione degli aspetti logistici speciali dell'ordine di reso, è necessario utilizzare la pagina **Ordine cliente** per completare il processo di fatturazione. L'organizzazione può quindi fatturare gli ordini di reso e gli ordini cliente contemporaneamente e la stessa persona può completare il processo di fatturazione, a seconda delle esigenze. Per visualizzare l'ordine di reso nella pagina **Ordine cliente**, fare clic sul collegamento del numero di ordine cliente per aprire l'ordine cliente associato. È inoltre possibile individuare l'ordine di reso nella pagina **Tutti gli ordini cliente**. Gli ordini di reso sono ordini cliente che hanno un tipo di ordine di **Ordine di reso**.

### <a name="credit-correction"></a>Correzione credito

Durante il processo di fatturazione verificare che tutti gli addebiti vari siano corretti. Per far sì che le registrazioni contabili diventino correzioni (Storno), valutare l'opportunità di utilizzare l'opzione **Correzione credito** nella scheda **Altro** della pagina **Registrazione fattura** quando si registra la fattura o la nota di accredito. **Nota:** per impostazione predefinita, l'opzione **Correzione credito** è attivata se l'opzione **Nota di accredito correttiva** nella pagina **Parametri contabilità clienti** è stata attivata. Tuttavia, è consigliabile non registrare resi con Storno.

## <a name="create-intercompany-return-orders"></a>Creare ordini di reso interaziendali
Gli ordini di reso possono essere completati tra due società della propria organizzazione. Sono supportati gli scenari che seguono:

-   semplici resi interaziendali tra due società appartenenti a una relazione interaziendale
-   una catena interaziendale che viene stabilita quando un ordine di reso cliente viene creato nella società venditrice
-   una catena interaziendale che viene stabilita quando un ordine di reso fornitore viene creato nella società acquirente
-   resi di spedizione consegna diretta tra un cliente esterno e due società appartenenti a una relazione interaziendale

### <a name="setup"></a>Imposta

Nella seguente figura è indicata la configurazione minima necessaria per due società per partecipare a una relazione interaziendale e per consentire il commercio interaziendale.  

[![Configurazione minima](https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn06.png)](https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn06.png)  

Nello scenario seguente CompBuy è l'azienda acquirente, mentre CompSell è l'azienda venditrice. In genere, la società venditrice spedisce le merci alla società acquirente o, in scenari di spedizione di consegna, direttamente al cliente finale. In CompBuy l'IC del fornitore\_CompSell viene definito come endpoint interaziendale associato alla società CompSell. Contemporaneamente, in CompSell, l'IC del cliente\_CompBuy viene definito come endpoint interaziendale associato alla società CompBuy. I dettagli dei criteri di azione e i mapping dei valori appropriati devono essere definiti in entrambe le società. In uno scenario di spedizione di consegna diretta un ordine di reso interaziendale, che corrisponde a un ordine cliente interaziendale, viene creato nella società venditrice. Il codice NAR dell'ordine di reso interaziendale può essere selezionato dalla sequenza di codici NAR in CompSell oppure può essere copiato dal codice NAR assegnato all'ordine di reso originale in CompBuy. Le impostazioni del codice NAR sui criteri azioni **PurchaseRequisition** in CompBuy determinano le azioni. Se il codice NAR viene sincronizzato, è necessario attenuare il rischio del numero di scontri se le due società utilizzano la stessa sequenza numerica.

### <a name="simple-intercompany-returns"></a>Resi interaziendali semplici

Questo scenario interessa due società della stessa organizzazione, come illustrato nella figura seguente.  

[![Reso interaziendale semplice](https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn07.png)](https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn07.png)  

È possibile stabilire la catena di ordini quando viene creato un ordine di reso fornitore nell'azienda acquirente o viene creato un ordine di reso cliente nell'azienda venditrice. Finance and Operations crea l'ordine corrispondente nell'altra società e garantisce che l'intestazione e le informazioni sulla riga dell'ordine di reso fornitore riflettano le impostazioni nell'ordine di reso di un cliente. L'ordine di reso che viene stabilito può includere o escludere il riferimento (**Trova ordine cliente**) a una fattura di vendita esistente. I documenti di trasporto e le fatture dei due ordini possono essere elaborati singolarmente. Ad esempio, non sarà necessario generare un documento di trasporto per l'ordine di reso fornitore prima di generare il documento di trasporto per l'ordine di reso di un cliente.

### <a name="direct-delivery-shipment-returns-among-three-parties"></a>Resi di spedizione consegna diretta tra tre parti

Questo scenario può verificarsi se una vendita precedente del tipo **Consegna diretta** è stata completata e se una fattura al cliente è disponibile nella società che interagisce con il cliente. Nella seguente figura la società CompBuy ha precedentemente venduto e fatturato prodotti al cliente Extern. I prodotti sono stati spediti direttamente dalla società CompSell al cliente tramite una catena di ordini interaziendali.  

[![Resi di spedizione consegna diretta tra tre parti](https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn08.png)](https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn08.png)  

Se il cliente Extern desidera restituire i prodotti, viene creato un ordine di reso (RMA02) per il cliente nell'azienda CompBuy. Per stabilire la catena interaziendale, l'ordine di reso deve essere contrassegnato per la consegna diretta. Quando si utilizza la funzione **Trova ordine cliente** per selezionare la fattura cliente da restituire, viene stabilita una catena di ordini interaziendali costituita dai seguenti documenti:

-   **Ordine di reso originale:** RMA02 (società CompBuy)
-   **Ordine fornitore:** PO02 (società CompBuy)
-   **Ordine di reso interaziendale:** RMA\_00032 (società CompSell)

Dopo che la catena interaziendale di consegna diretta viene creata, la gestione fisica e l'elaborazione dei resi devono verificarsi nel contesto dell'ordine di reso interaziendale, RMA\_00032 nella società CompSell. I prodotti non possono essere ricevuti nella società CompBuy. Quando un codice smaltimento viene assegnato all'ordine di reso interaziendale, viene sincronizzato con l'ordine di reso originale per consentire la corretta fatturazione dell'ordine originale.

## <a name="post-to-the-ledger"></a>Registrare nella contabilità generale
Le registrazioni contabili generate quando l'ordine di reso viene fatturato sono influenzate da alcuni parametri e impostazioni importanti:

-   **Prezzo di costo reso** - per i modelli inventariali diversi da **Costo standard**, il parametro **Prezzo di costo reso** determina il costo dell'articolo quando viene riaccettato in magazzino o scartato. Per calcolare una valutazione corretta del magazzino, è importante definire il parametro **Prezzo di costo reso** correttamente. Se si utilizza la funzione **Trova ordine cliente** per creare una riga di ordine di reso che contiene un riferimento a una fattura cliente, il valore **Prezzo di costo reso** corrisponde al prezzo di costo dell'articolo che viene venduto. In caso contrario, il valore del prezzo di costo deriva dall'impostazione per articolo oppure può essere immesso manualmente.
-   **Correzione credito/Storno** - Il parametro **Correzione credito** nella pagina **Registrazione fattura** determina se le registrazioni devono essere registrate come voci (DR/CR) positive o come voci negative, da correggere.

Negli esempi successivi il prezzo di costo del reso è rappresentato come **Prezzo di costo di magazzino**.

### <a name="example-1-the-return-order-doesnt-reference-a-customer-invoice"></a>Esempio 1: l'ordine di reso non fa riferimento a una fattura cliente

L'ordine di reso non fa riferimento a una fattura cliente. L'articolo reso viene registrato in Avere. Il parametro **Correzione credito** non è selezionato quando la fattura dell'ordine di reso, o nota di accredito, viene generata.  

[![L'ordine di reso non fa riferimento a una fattura cliente](https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn09.png)](https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn09.png)  

**Nota:** il prezzo nel record generale dell'articolo viene utilizzato come valore predefinito per il parametro **Prezzo di costo reso**. Il prezzo predefinito è diverso dal prezzo di costo al momento dell'uscita da magazzino. Di conseguenza, l'implicazione è che si è verificata una perdita di 3. Inoltre, l'ordine di reso non include lo sconto concesso al cliente nell'ordine cliente. Di conseguenza, si verifica un credito in eccesso.

### <a name="example-2-credit-correction-is-selected-for-the-return-order"></a>Esempio 2: la correzione del credito è selezionata per l'ordine di reso

L'esempio 2 corrisponde all'esempio 1, ma il parametro **Correzione credito** è selezionato quando viene generata la fattura dell'ordine di reso.  

[![Ordine di reso in presenza della selezione di una correzione di credito ](https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn10.png)](https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn10.png)  

**Nota:** le registrazioni contabili vengono immesse come correzioni negative.

### <a name="example-3-the-return-order-line-is-created-by-using-the-find-sales-order-function"></a>Esempio 3: la riga dell'ordine di reso viene creata utilizzando la funzione Trova ordine cliente

In questo esempio la riga dell'ordine di reso viene creata utilizzando la funzione **Trova ordine cliente**. Il parametro **Correzione credito** non è selezionato quando viene creata la fattura.  

[![Riga ordine di reso creata usando Trova ordine cliente ](https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn11.png)](https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn11.png)  

**Nota:** **Sconto** e **Prezzo di costo reso** vengono impostati correttamente. Di conseguenza, viene eseguito uno storno esatto della fattura cliente.




