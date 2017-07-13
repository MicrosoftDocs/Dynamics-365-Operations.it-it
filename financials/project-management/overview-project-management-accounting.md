---
title: "Gestione progetti e contabilità"
description: "La funzionalità gestione progetti e contabilità può essere utilizzata in più settori per fornire un servizio, realizzare un prodotto oppure ottenere un risultato."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 87983
ms.assetid: b454ad57-2fd6-46c9-a77e-646de4153067
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: 12afcde947463b3abf58dea6138653a32dcda6f1
ms.contentlocale: it-it
ms.lasthandoff: 06/13/2017


---

# <a name="project-management-and-accounting"></a>Gestione progetti e contabilità

[!include[banner](../includes/banner.md)]


La funzionalità gestione progetti e contabilità può essere utilizzata in più settori per fornire un servizio, realizzare un prodotto oppure ottenere un risultato.  

Un progetto è un gruppo di attività progettato per fornire un servizio, produrre un prodotto o raggiungere un risultato. I progetti consumano risorse e generano risultati finanziari sotto forma di ricavi o cespiti.

## <a name="projects-across-industries"></a>Progetti tra settori
La funzionalità gestione progetti e contabilità può essere utilizzata in più settori, come illustrato nella figura seguente. [![Progetti tra settori](./media/projects-accross-industries.jpg)](./media/projects-accross-industries.jpg) 

In un call center un ticket può essere utilizzato per descrivere il set di azioni necessarie per risolvere una chiamata. Le società di consulenza, ad esempio le organizzazioni di consulenza tecnica o di gestione oppure le agenzie di pubblicità, fanno riferimento alle loro attività come progetti. Nel marketing una campagna rappresenta un set di lavoro che deve essere consegnato. Nella produzione basata su progetti, un ordine di produzione si riferisce ai vari lavori che devono essere eseguiti per produrre alcuni prodotti finiti. Qualsiasi nome venga utilizzato per i prodotti, questi progetti coinvolgono risorse, programmazioni e costi e la funzionalità gestione progetti e contabilità di Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition può facilitare la pianificazione, l'esecuzione e l'analisi di questi progetti.

## <a name="project-phases"></a>Fasi progetto
Sebbene il seguente flusso del processo sia teso verso progetti esterni o progetti che vengono completati per uno o più clienti, la funzionalità si applica anche ai progetti interni e di soli costi. 

![3 fasi di un progetto](./media/3-stages-of-a-project.png) 

Come illustrato nella precedente figura, gestione progetti e contabilità possono essere suddivise in tre fasi:

1.  Inizia
2.  Elabora
3.  Analizza

## <a name="initiate-the-project"></a>Inizio del progetto
Durante l'avvio del progetto, si verificano diversi processi chiave. È possibile utilizzare un'offerta di progetto per comunicare la manodopera, le spese e i materiali stimati al cliente. È possibile registrare i termini, i limiti e i contratti di fatturazione in un contratto di progetto. È possibile utilizzare una struttura di suddivisione del lavoro (WBS) per pianificare e valutare il lavoro. È possibile impostare le previsioni e i budget per facilitare l'esecuzione del progetto. La figura seguente mostra la struttura di un progetto.[![struttura di un progetto](./media/project-structure1.jpg)](./media/project-structure1.jpg)  

### <a name="create-project-quotations"></a>Creazione di offerte di progetto

Nella fase iniziale di vendita di un progetto, l'offerta di progetto consente di presentare a un cliente un'offerta non vincolante. Un'offerta può comprendere elementi, quali articoli e servizi inclusi, informazioni di base sul contatto, accordi commerciali e sconti speciali e possibili imposte e supplementi.

Può essere inoltre emessa una lettera di garanzia per una transazione dell'offerta di progetto tra l'organizzazione e il cliente. Dopo la creazione dell'offerta di progetto è possibile creare la richiesta di lettera di garanzia per il cliente e inviarla alla banca. Dopo l'approvazione della richiesta da parte della banca, la lettera di garanzia viene emessa al cliente. 

Per ulteriori informazioni, vedere [Offerte di progetti](project-quotations.md).

### <a name="create-project-contracts"></a>Creazione di contratti di progetto

Quando si stipula un contratto con un cliente o un'altra fonte di finanziamento per completare un progetto, si deve innanzitutto creare un contratto per il progetto. Quando poi si crea il progetto, è necessario assegnarlo al contratto corrispondente. Il tipo di progetto creato per un contratto di progetto determina il metodo utilizzato per rilasciare fatture ai clienti del progetto. È possibile modificare un contratto di progetto e il relativo progetto, ma non è possibile modificare il tipo di progetto. Per ulteriori informazioni sui tipi di progetto, vedere la sezione "Creazione progetti".

Per ulteriori informazioni sui contratti di progetto, vedere [Contratti di progetto](project-contracts.md).

### <a name="create-work-breakdown-structures"></a>Creazione di strutture di suddivisione del lavoro

Il grado di dettaglio in una struttura di suddivisione del lavoro dipende dal livello di accuratezza necessario nelle stime e dal livello di tracciabilità necessario per tali stime. I progetti con tolleranza molto bassa per gli slittamenti nella programmazione o nei costi richiedono in genere una struttura di suddivisione del lavoro più dettagliata e anche una tracciabilità diligente dello stato di avanzamento e dei costi del lavoro rispetto alla struttura di suddivisione del lavoro. 

Per ulteriori informazioni, vedere [Strutture di suddivisione del lavoro](work-breakdown-structures.md).

### <a name="create-project-forecasts-and-budgets"></a>Creazione di previsioni di progetto e budget

È possibile utilizzare le previsioni se l'organizzazione si basa su una prospettiva operativa ed è incentrata sui ricavi e i costi derivati da transazioni specifiche. Tuttavia, se l'organizzazione è incentrata maggiormente sugli importi finanziari, può essere utilizzata l'impostazione del budget. Ciascun metodo ha i relativi vantaggi. Per ulteriori informazioni, vedere [Previsioni di progetto e budget](project-forecasts-budgets.md).

### <a name="create-projects"></a>Crea progetti

È possibile creare sei tipi di progetti in Microsoft Finance and Operations. Ogni tipo di progetto è impostato in modo diverso per i costi e il riconoscimento dei ricavi. La scelta del tipo di progetto dipende dallo scopo del progetto. Nella seguente tabella viene descritto l'utilizzo tipico di ciascun tipo di progetto.

                                                                                                                                                                         |
| Tipo di progetto      | Descrizione                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
|-------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Tempistica e materiali | Per i progetti di tempistica e materiali, al cliente vengono fatturati per tutti i costi che vengono sostenuti in un progetto, tra cui i costi per ore, spese, articoli e commissioni.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| A prezzi fissi       | Nei progetti a prezzo fisso le fatture sono costituite da transazioni di acconto. Un progetto a prezzo fisso viene fatturato in base a un programma di fatturazione che si basa su un contratto di progetto. I ricavi per un progetto a prezzo fisso possono essere calcolati e registrati in tutto il progetto utilizzando il metodo per percentuale completata. In alternativa, i ricavi possono essere calcolati e registrati quando il progetto viene completato, utilizzando il metodo per conclusione dei contratti. Le società possono trarre giovamento spesso da utilizzare il valore di lavoro in (WIP) processo per calcolare il grado di completamento di un progetto o di un gruppo di progetti.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| Investimento        | I progetti di investimento sono progetti che non determinano profitti immediati. In genere sono utilizzati per i progetti interni a lungo termine dove i costi devono essere capitalizzati. Solo i costi per articoli, ore e spese possono essere registrati per un progetto di investimento. I costi di un progetto di investimento vengono monitorati e controllati dalla funzionalità di stima. È possibile impostare i progetti di investimento con un limite di capitalizzazione massima facoltativo. Mentre un progetto di investimento avanza, si registrano i relativi costi nei conti WIP, dove i costi sono mantenuti fino al completamento del progetto. Quando il progetto viene eliminato, trasferire il valore WIP a un cespite, in un conto CoGe o un nuovo progetto. Nota: le transazioni relative ai progetti di investimento non verranno visualizzate nella pagina **Registra costi**, **Accumula ricavi** o **Crea proposte di fatturazione**.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| Piano dei costi      | Analogamente ai progetti di investimento, i piani dei costi vengono in genere utilizzati per tenere traccia dei progetti interni e solo le ore, le spese e gli articoli possono essere registrati per loro. Tuttavia, i piani dei costi hanno in genere una durata inferiore rispetto ai progetti di investimento. Inoltre, a differenza dei progetti di investimento, i piani dei costi non possono essere capitalizzati nei conti dello stato patrimoniale. Le transazioni di progetto vengono invece registrate solo nei conti profitti e perdite. **NOTA**: le transazioni relative ai piani dei costi non vengono riflesse nella pagina **Registra costi**, **Accumula ricavi** o **Crea proposte di fatturazione**. Poiché i piani dei costi in genere vengono utilizzati per tenere traccia dei progetti interni, non devono essere necessariamente associati a un conto cliente. Tuttavia, se l'impostazione richiede che le richieste articoli vengano create per gli ordini acquisto, è necessario associare il piano dei costi a un cliente. Questa associazione è necessaria, perché le richieste articoli vengono gestite come righe ordine cliente e il sistema richiede che venga specificato un cliente. Tuttavia, questa impostazione non finirà per creare automaticamente delle richieste articoli da un ordine acquisto. Per i piani dei costi, l'impostazione **Creare la richiesta articolo** è trascurata. Se è necessaria una richiesta articoli in un piano dei costi, è possibile crearne una manualmente, purché un cliente sia associato al progetto. |
| Interno          | I progetti interni sono utilizzati per tenere traccia dei costi in un piano interno all'organizzazione. I progetti interni possono fornire uno strumento di pianificazione per gestire il consumo di risorse. **Nota:** le transazioni relative ai progetti interni non vengono riflesse nella pagina **Accumula ricavi** o **Crea proposte di fatturazione**.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| Ora              | I progetti di tempistica vengono utilizzati per tenere traccia del tempo associato alle attività non addebitabili e non produttive, ad esempio un progetto per tenere traccia dei periodi di malattia per i lavoratori. Le transazioni nei progetti di tempistica non vengono registrate nella contabilità generale. Sono invece nei report relativi agli utilizzi dei lavoratori. In questi progetti è possibile registrare solo le transazioni orarie. Si utilizza un giornale di registrazione ore o una scheda attività per registrare le ore del progetto. Dopo la registrazione, le ore vengono visualizzate come transazioni di progetto ma non dispongono di transazioni di giustificativo corrispondenti. **Nota**: le transazioni relative ai progetti di tempistica non vengono riflesse nella pagina **Registra costi**, **Accumula ricavi** o **Crea proposte di fatturazione**.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |


### <a name="assign-workers-categories-and-resources"></a>Assegnazione di lavoratori, categorie e risorse

È possibile programmare le risorse lavoratori in base ai requisiti e alla programmazione di un progetto o alle competenze e alla disponibilità dei lavoratori. Utilizzando le funzionalità di programmazione delle risorse, è possibile distribuire i lavoratori dell'organizzazione in modo efficace ed effettivo. È possibile trovare rapidamente i lavoratori più qualificati disponibili a lavorare al progetto. È inoltre possibile visualizzare facilmente come i lavoratori potrebbero essere utilizzati in modo più efficace nel corso del progetto. 

Di seguito sono indicati alcuni dei modi in cui è possibile utilizzare la funzionalità di programmazione:

-   Utilizzare le informazioni sugli attributi del lavoratore, ad esempio percorso formativo, competenze, certificazioni ed esperienza nei progetti per abbinare il lavoratore ai requisiti di un progetto.
-   Utilizzare le informazioni relative alla disponibilità e al calendario di un lavoratore per abbinare la programmazione del lavoratore al calendario del progetto.
-   Verificare la capacità di ciascun lavoratore e determinarne l'utilizzo. Ad esempio, se un lavoratore non è sufficientemente impegnato, quest'ultimo può essere assegnato a un progetto adatto ai suoi attributi e alla sua disponibilità.
-   Verificare la disponibilità di un lavoratore per assicurarsi che non si verifichino conflitti di calendario relativi alle sue assegnazioni.
-   Verificare le informazioni relative all'impiego dei lavoratori in una visualizzazione riepilogativa, ad esempio per reparto o per lavoratore, o in una visualizzazione dettagliata, ad esempio in base ai lavoratori di un reparto o ai dettagli settimanali per ciascun lavoratore.
-   Modificare le assegnazioni delle risorse per più unità di tempo, ad esempio giorno, settimana o mese, per ottimizzare l'impiego dei lavoratori.

## <a name="execute-the-project"></a>Esecuzione del progetto
Durante l'esecuzione del progetto i membri del team o i manager registrano il lavoro e le spese che vengono sostenuti, utilizzando i fogli presenze, le note spese e altri documenti aziendali. I manager di progetto dispongono di strumenti che permettono loro di monitorare il consumo di importi a budget per il progetto. I manager di progetto possono inoltre ordinare, prelevare o procurarsi i materiali per i progetti utilizzando gli ordini fornitore e altri documenti aziendali. Le fatture vengono redatte e approvate, in modo che i clienti possano ricevere le fatture per il lavoro in corso. Infine, è riconosciuto che durante questo processo i ricavi influiscono sui dati finanziari dell'organizzazione.

### <a name="manage-work-breakdown-structures"></a>Gestione delle strutture di suddivisione del lavoro

Una struttura di suddivisione del lavoro è una descrizione del lavoro che verrà completato per un progetto. Una struttura di suddivisione del lavoro è una gerarchia di attività. Rappresenta non solo il lavoro per ogni attività, ma anche la portata, il costo e la durata dell'attività. 

Per ulteriori informazioni, vedere [Strutture di suddivisione del lavoro](work-breakdown-structures.md).

### <a name="manage-project-forecasts-and-budgets"></a>Gestione delle previsioni e dei budget di progetto

Sono disponibili due modi per gestire e controllare i progetti: previsioni di progetto e budget di progetto. È possibile utilizzare le previsioni se l'organizzazione si basa su una prospettiva operativa ed è incentrata sui ricavi e i costi derivati da transazioni specifiche. Tuttavia, se l'organizzazione è incentrata maggiormente sugli importi finanziari, può essere utilizzata l'impostazione del budget.

Per ulteriori informazioni, vedere [Previsioni di progetto e budget](project-forecasts-budgets.md).

### <a name="create-production-orders"></a>Creazione di ordini di produzione

Un ordine di produzione correlato a un progetto può essere collegato a un ordine cliente o a una richiesta articolo utilizzando il metodo articolo finito o il metodo articolo consumato. Inoltre, se l'ordine di produzione è stato creato manualmente, non esiste alcun collegamento tra l'ordine di produzione e l'ordine cliente o la richiesta articolo (nessun collegamento all'ordine). Tuttavia, se l'ordine di produzione è stato creato automaticamente per soddisfare un ordine cliente o una richiesta articolo, esiste un collegamento tra l'ordine di produzione e l'ordine cliente o la richiesta articolo (collegamento all'ordine). 

In base alle combinazioni di questi fattori, utilizzare uno dei metodi seguenti:

-   **Articolo finito/collegamento all'ordine**: consente di collegare il progetto a un ordine cliente o a una richiesta articolo. Utilizzando questo metodo, i costi effettivi del progetto vengono registrati quando viene fatturato l'ordine cliente o quando viene aggiornato il documento di trasporto della richiesta articolo. Il costo viene registrato come articolo finito.
-   **Articolo finito/nessun collegamento all'ordine**: i costi effettivi non possono essere registrati fino a quando lo stato del ciclo di produzione di un articolo non è **Finito**. Il costo dell'articolo finito viene registrato come singola transazione.
-   **Articolo consumato/collegamento all'ordine**: consente di collegare il progetto a una richiesta articolo. Utilizzando questo metodo, è possibile visualizzare i costi effettivi del progetto quando lo stato della produzione è **Avviato** o finito. I costi vengono registrati in più transazioni articolo di progetto per le materie prime e le ore consumate nella produzione. Quando viene aggiornato il documento di trasporto per la richiesta articolo, non viene registrato alcun costo di progetto. È inoltre possibile definire il livello della gerarchia della distinta base (DBA) in cui viene tenuta traccia dei progetti nella produzione.
-   ****Articolo consumato/nessun collegamento all'ordine****: consente di collegare il progetto a una richiesta articolo. Utilizzando questo metodo, è possibile visualizzare i costi effettivi del progetto quando lo stato della produzione è **Avviato** o finito. I costi vengono registrati in più transazioni articolo di progetto per le materie prime e le ore consumate nella produzione. È inoltre possibile definire il livello della gerarchia DBA in cui viene tenuta traccia dei progetti nella produzione.

### <a name="procure-products-and-services"></a>Approvvigionamento di prodotti e servizi

L'acquisto e la vendita di articoli sono attività predominanti in molte aziende basate su progetti.

#### <a name="purchase-orders-for-projects"></a>Ordini fornitore per progetti

Lo scopo dell'ordine fornitore determina quando verrà consumato l'ordine e, di conseguenza, quando gli articoli verranno addebitati a un progetto.

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>Metodo</th>
<th>Scopo</th>
<th>Consumo articoli</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Creare direttamente un ordine fornitore.</td>
<td>Acquistare articoli da un fornitore esterno per il consumo relativo a un progetto. È possibile creare l'ordine fornitore nei seguenti modi:
<ul>
<li>Dal progetto stesso. In questo caso il progetto è già definito per l'ordine fornitore.</li>
<li>Accedendo all'ordine fornitore del progetto. È necessario selezionare sia il fornitore sia il progetto per cui viene creato l'ordine fornitore.</li>
</ul></td>
<td>Gli articoli vengono consumati quando viene aggiornata la fattura fornitore.</td>
</tr>
<tr class="even">
<td>Creare un ordine fornitore da un ordine cliente.</td>
<td>Acquistare articoli quando si crea un ordine fornitore da un progetto.</td>
<td>Gli articoli vengono consumati quando l'ordine cliente viene fatturato al cliente.</td>
</tr>
<tr class="odd">
<td>Creare un ordine fornitore da una richiesta articolo.</td>
<td>Acquistare articoli quando si crea una richiesta di articoli da un progetto.</td>
<td>Gli articoli vengono consumati quando viene aggiornato il documento di trasporto relativo alla richiesta articolo.</td>
</tr>
</tbody>
</table>

#### <a name="sales-orders-for-projects"></a>Ordini cliente per progetti

In Gestione progetti e contabilità è possibile registrare il consumo di articoli in diversi modi. È possibile vendere o acquistare articoli a partire da un progetto oppure prenotarli per un progetto. 

È possibile ordinare gli articoli dall'inventario della società per il consumo in un progetto. In alternativa, è possibile acquistare gli articoli da un fornitore esterno. Gli articoli possono essere consumati in tutti i tipi di progetti tranne quelli di tempistica. 

Il modo in cui è possibile ordinare gli articoli dipende da dove vengono ordinati:

-   Per ordinare gli articoli dall'inventario della società, è necessario immettere l'ordine come richiesta articolo. Se si utilizza la pagina **Richieste articoli**, è possibile impostare la richiesta in modo che gli articoli vengano ricevuti come consegne parziali. Di conseguenza, è possibile posticipare il consumo di una quantità di articoli fino a quando gli articoli non vengono richiesti.
-   Per ordinare gli articoli da un fornitore esterno, è necessario creare l'ordine fornitore nella pagina **Ordine fornitore**.

> [!NOTE] 
> Il documento di trasporto per un ordine cliente correlato al progetto non può essere annullato se gli articoli sono già stati contrassegnati per l'imballaggio. 

Nella seguente tabella vengono elencati i metodi per ordinare gli articoli e viene descritto il modo in cui gli articoli vengono consumati.

| Metodo            | Scopo                                                                                                                                                        | Utilizzo della transazioni articolo                                                                                                                  |
|-------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------|
| Ordine cliente       | Consente di immettere una transazione direttamente in un progetto di tempistica e materiali.                                                                                                   | Le transazioni articolo vengono consumate al momento della registrazione della fattura cliente.                                                                               |
| Giornale di registrazione magazzino | Consente di immettere e gestire rapidamente i record relativi agli articoli. Se ad esempio si desidera immettere una richiesta articolo in base a un elenco stampato, è possibile utilizzare un giornale di registrazione magazzino. | Le transazioni articolo vengono consumate al momento della registrazione del giornale.                                                                                        |
| Richiesta articolo  | Consente di immettere gli articoli non destinati al consumo immediato. Questo metodo consente di tenere traccia del numero di articoli consumati nell'ambito di un singolo record di richiesta articolo.    | Le transazioni articolo vengono consumate quando il documento di trasporto viene aggiornato. In altri termini, la richiesta articolo viene creata al momento della registrazione del documento di trasporto. |
| Ordini acquisto   | Consente di immettere le transazioni in una delle tre diverse aree, a seconda del metodo di acquisto.                                                                              | Le transazioni articolo vengono consumate quando il documento di trasporto viene aggiornato oppure al momento della fatturazione al cliente o al fornitore.                                      |

### <a name="process-project-invoices"></a>Elaborazione delle fatture progetto

La procedura di fatturazione da applicare è determinata dal tipo di progetto. È possibile fatturare solo i due tipi di progetto esterni, ovvero i progetti di tempistica e materiali e quelli a prezzo fisso. I progetti di tempistica e materiali e quelli a prezzo fisso sono sempre collegati a un contratto di progetto. 

Prima di creare una fattura cliente per un progetto, è possibile creare una fattura preliminare o una proposta di fatturazione. In una proposta di fatturazione, è possibile selezionare le transazioni di progetto da includere in una fattura di progetto. È quindi possibile esaminare i dettagli della fattura prima di registrare la fattura di progetto e inviarla al cliente o a un'altra fonte di finanziamento. 


Per informazioni su come elaborare le fatture dei progetti, vedere [Fatturazione progetto](../accounts-payable/project-invoicing.md).


### <a name="calculate-the-cost-to-complete-a-project"></a>Calcolo del costo di completamento di un progetto

Quando si crea una stima, è possibile scegliere il metodo per il calcolo dei costi di completamento del progetto. Selezionare un metodo nel campo **Metodo costi di completamento** della pagina **Crea stima**. Il metodo scelto si applica separatamente a ogni riga dei costi nella stima dei costi. Quando una riga ha lo stato di **Creato**, è possibile modificare il metodo applicato ad essa nella pagina **Stima dei costi**. 

Nella seguente tabella sono descritti i metodi per calcolare il costo per completare un progetto.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Metodo</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Costo totale - Effettivo</td>
<td>I costi stimati devono essere immessi manualmente. Dopo che è stata completata la colonna <strong>Costo totale</strong> o <strong>Quantità totale</strong> nella pagina <strong>Stima dei costi</strong>, i costi effettivi vengono sottratti dai totali immessi dagli utenti. Il risultato è il costo per completare il progetto. In genere, non viene tenuta traccia dello stato di avanzamento dei costi in base, ad esempio, al numero di soggiorni e di pasti in hotel registrati in ogni periodo. Al contrario. Si basa invece su un confronto con l'importo totale delle ore stimate. Questo metodo non richiede un modello previsionale e il costo totale o la quantità totale può essere modificata manualmente. Quando un valore viene immesso nella colonna <strong>Costo totale</strong> o <strong>Quantità totale</strong>, Finance and Operations confronta il valore con le transazioni effettive registrate nel periodo e quindi riduce il valore nella colonna <strong>Quantità da completare</strong> o <strong>Costi di completamento</strong>.</td>
</tr>
<tr class="even">
<td>Budget totale - Effettivo</td>
<td>I costi effettivi vengono comparati con il modello previsionale selezionato per determinare il costo. Questo metodo utilizza un modello di budget totale che include le transazioni previste. Per ottenere una panoramica più precisa del progetto, è possibile rettificare il modello di budget quando il progetto è in corso. Se si deve rettificare la previsione, attenersi alla procedura generale seguente:
<ol>
<li>Copiare le transazioni previsionali in un altro modello previsionale.</li>
<li>Confrontare le transazioni previsionali con le transazioni effettive.</li>
<li>Gestire, diminuire, incrementare le stime per il periodo successivo.</li>
</ol>
Finance and Operations non riduce automaticamente le stime previste. Pertanto, si consiglia di conservare un modello previsionale originale del progetto a prezzo fisso per creare un riferimento di base con cui eseguire il confronto una volta che il progetto è stato completato. 
> [!NOTE]: quando si seleziona questo metodo, utilizzare almeno due modelli previsionali. Un modello deve contenere la previsione originale. Nell'altro occorre copiare le transazioni previsionali da un altro modello. Questo metodo vale solo per i progetti a prezzo fisso e i progetti di investimento.</td>
> </tr>
<tr class="odd">
<td>Budget residuo</td>
<td>Questo metodo utilizza un modello di budget residuo per calcolare il costo di completamento del progetto. Quando si utilizza questo metodo, i costi effettivi e gli importi previsti nel modello di budget residuo vengono sommati. Il risultato è il costo totale. Prima di utilizzare questo metodo, il modello di budget residuo deve essere configurato per detrarre le transazioni basate sulle transazioni effettive registrate nel sistema. Nella pagina <strong>Modelli previsionali</strong> assicurarsi che i campi siano contrassegnati nel gruppo <strong>Riduzione previsioni automatica</strong>. In genere, un budget residuo viene copiato da un budget originale. Man mano che vengono immesse le transazioni, le transazioni nel budget residuo diminuiscono. Se durante il progetto si determina che il budget residuo debba essere rettificato, si addebitano le transazioni previsionali al budget residuo. <strong>Nota:</strong> questo metodo può essere applicato solo se alla stima è collegato un modello previsionale.</td>
</tr>
<tr class="even">
<td>Come stima precedente</td>
<td>Lo stesso metodo di stima utilizzato nel periodo precedente è applicabile. Questo metodo richiede un modello previsionale se il periodo precedente aveva richiesto un modello previsionale.</td>
</tr>
<tr class="odd">
<td>Imposta costi di completamento su zero</td>
<td>In genere, questo metodo è utilizzato prima che il progetto di stima sia eliminato. Questo metodo confronta le stime totali con le transazioni effettive registrate e rimuove la colonna <strong>Costi di completamento</strong>. La percentuale di completamento risultante è sempre pari a 100. Il campo <strong>Previsioni</strong> non è selezionato per ogni riga dei costi creata e la stima totale viene copiata dalla stima dei costi precedente. Il consumo effettivo per il periodo di stima viene sottratto dal costo di completamento del progetto. Per questo metodo non è necessario un modello previsionale.</td>
</tr>
<tr class="even">
<td>Da modello dei costi</td>
<td>Viene applicato il metodo Costi di completamento impostato nel modello dei costi associato al progetto di stima selezionato.</td>
</tr>
</tbody>
</table>

## <a name="analyze-the-project"></a>Analisi del progetto
Al relativo livello più fondamentale, un progetto viene utilizzato per raggruppare le transazioni che registrano i costi e poi per registrare questi costi nella contabilità generale. 

A livello generale, queste transazioni sono il risultato di documenti aziendali, quali fogli presenze, note spese, fatture fornitore o operazioni di magazzino. Il ciclo di vita di un progetto in genere inizia con stime, previsioni e budget che aiutano a pianificare e prevedere il lavoro e l'impatto finanziario del progetto. Quando si analizza un progetto, è possibile valutare non solo le transazioni che hanno avuto luogo durante il progetto, ma anche l'accuratezza delle stime e delle previsioni, i tassi di utilizzo dei membri del team del progetto e il successo globale del progetto.

### <a name="analyze-cash-flow"></a>Analisi del flusso di cassa

Utilizzare il monitoraggio del flusso di cassa per verificare sia i flussi di cassa previsti che i flussi di cassa effettivi di un progetto. È possibile esaminare i flussi di cassa mentre un progetto è in corso o visualizzare i flussi di cassa di un progetto completato. 

Monitorando i flussi di cassa, è possibile valutare un singolo progetto, utilizzare i report per visualizzare più progetti e trasferire i flussi di cassa del progetto alle previsioni di cassa nella contabilità generale.

#### <a name="cash-inflow-forecasting"></a>Previsione delle entrate di cassa

In base alla configurazione è possibile prevedere le affluenze di cassa per un progetto selezionato. Se ad esempio il progetto è datato 5 marzo 2012 e la fattura è datata 31 marzo 2012, ecco come è possibile prevedere la data di scadenza e la data prevista di pagamento vendita.

-   **Data del progetto:** 5 marzo 2012.
-   **Data fattura:** 31 marzo 2012. Questa data viene determinata in base alla frequenza di fatturazione. Per questo esempio si imposterà la frequenza di fatturazione sul mese corrente. Di conseguenza, tutte le transazioni registrate in marzo verranno fatturate l'ultimo giorno del mese.
-   **Data di scadenza:** 14 aprile 2012. Questa data viene determinata in base ai termini di pagamento stabiliti per il progetto. Per questo esempio sono stati selezionati termini di pagamento di 14 giorni. Di conseguenza, alla data della fattura vengono aggiunti 14 giorni per arrivare alla data di scadenza del 14 aprile 2012.
-   **Data prevista pagamento vendita:** 27 aprile 2012. Questa data viene calcolata aggiungendo il numero di giorni contenuti nel campo **Giorni di tolleranza generali** della pagina **Parametri Gestione progetti e contabilità** al numero di giorni presenti nel campo **Giorni di tolleranza particolare** della pagina **Contratti di progetto**, quindi aggiungendo il totale al numero di giorni nel campo **Data di scadenza**. Per questo esempio, verrà immesso **3** nel campo **Giorni di tolleranza generali** e **10** nel campo **Giorni di tolleranza particolare**. Di conseguenza, alla data di scadenza vengono aggiunti 13 giorni per arrivare alla data prevista di pagamento vendita del 27 aprile 2012.

I giorni di tolleranza generali possono sostituire i singoli giorni di tolleranza o essere aggiunti ai singoli giorni di tolleranza:

-   Per utilizzare i giorni di tolleranza generali come sostituzione dei singoli giorni di tolleranza, immettere la media dei giorni che intercorrono tra la data di scadenza e la data di pagamento effettiva calcolata per i clienti.
-   Per aggiungere i giorni di tolleranza generali ai giorni di tolleranza singoli, nel campo **Giorni di tolleranza generali** immettere la stima del numero di giorni tra il giorno in cui il cliente invia il pagamento e il giorno in cui l'organizzazione riceve il pagamento.

Stabilire i giorni di tolleranza singoli nel contratto del progetto. I giorni vengono calcolati sulla base della data di scadenza della fattura di vendita e dell'esperienza maturata dalle società con i criteri di pagamento del cliente.

#### <a name="actual-cash-inflow"></a>Entrate di cassa effettive

Le entrate di cassa effettive sono simili alla previsione delle entrate di cassa, con la differenza che i calcoli iniziano a partire dalla data della fattura. Ecco un esempio:

-   **Data fattura:** 2 marzo 2012.
-   **Data di scadenza:** 16 marzo 2012. I termini di pagamento sono impostati a 14 giorni.
-   **Data prevista pagamento vendita:** 29 marzo 2012. Il calcolo include i tre giorni di tolleranza generali e i 10 giorni di tolleranza singoli.

#### <a name="cost-forecasting"></a>Previsione dei costi

In base ai giorni definiti, la data di pagamento dei costi può differire dalla data del progetto. In questo caso, la data di pagamento dei costi viene calcolata aggiungendo il numero di giorni a partire dalla data del progetto al numero di giorni in termini di pagamento. 

Ad esempio, la data di progetto della transazione è il 5 marzo 2012 e si impostano i seguenti termini di pagamento:

-   **Ore:** Mese corrente (**M**)
-   **Spese:** 14 giorni (**D14**)
-   **Articoli:** 30 giorni (**D30**)

In base alle impostazioni, ecco la data di pagamento dei costi per ogni tipo di transazione:

-   **Ore:** 31 marzo 2012, ovvero l'ultimo giorno del mese selezionato.
-   **Spese:** 19 marzo 2012, ovvero 14 giorni dopo la data della transazione.
-   **Articoli:** 4 aprile 2012, ovvero 30 giorni dopo la data della transazione.

> [!NOTE] 
> La data di scadenza dell'ordine fornitore si basa piuttosto sulla transazione fornitore quando viene creato l'ordine fornitore del progetto. La data di scadenza non è determinata da alcuna impostazione predefinita. 

La data di pagamento dei costi non viene calcolata in base ai giorni di tolleranza. Una volta finito il progetto e completate la determinazioni costi e la fatturazione, il costo e le vendite vengono registrati nei conti profitti e perdite. 

Quando tutte le vendite e le fatture fornitore vengono completate, è possibile visualizzare la relazione tra i campi nella pagina **Flusso di cassa** e i campi nella pagina **Rendiconti progetto**.

| Pagina Flusso di cassa | Pagina Rendiconti progetto |
|----------------|-------------------------|
| Entrate di cassa   | Ricavi                 |
| Uscite di cassa  | Costo totale              |
| Flussi di cassa netti | Margine lordo            |

### <a name="review-costs"></a>Verifica dei costi

La pagina **Controllo costi** consente di monitorare i costi sostenuti dall'organizzazione durante un progetto. Confrontando i costi a budget originali per il progetto con i costi correnti effettivi e i costi impegnati, è possibile determinare se il progetto procede secondo i piani, ha superato il budget o è al di sotto del budget. 

> [!NOTE] 
> Quando si utilizza la pagina **Controllo costi** per visualizzare lo stato corrente dei costi dei progetti, utilizzare i modelli previsionali selezionati per il budget originale e quello residuo. Se si selezionano altri modelli previsionali durante l'esecuzione del calcolo dei costi, i risultati non saranno accurati.

#### <a name="viewing-the-remaining-budgeted-amounts"></a>Visualizzazione degli importi a budget residui

Se **Budget residuo** è selezionato come metodo di controllo dei costi nella pagina **Parametri Gestione progetti e contabilità**, nella pagina **Controllo costi** vengono calcolati i costi che non sono stati registrati come effettivi o contrassegnati come impegnati. In particolare, gli importi nelle colonne della scheda **Generale** nel riquadro inferiore della pagina **Controllo costi** vengono calcolati nei modi indicati di seguito:

-   **Costo effettivo**: importo totale speso per il progetto per la riga costi selezionata. L'importo di costo effettivo viene calcolato alla pagina **Aggiornamenti contabili**.
-   **Costo impegnato**: importo aggiuntivo delle spese che la persona giuridica si è impegnata a pagare. Gli importi specifici dei costi impegnati vengono calcolati nella pagina **Costi impegnati**.
-   **Budget residuo**: somma dell'importo di budget originale ancora disponibile per la riga costi selezionata. L'importo a budget residuo viene calcolato alla pagina **Anteprima Contabilità generale**.
-   **Costo totale**: somma del costo effettivo, del costo impegnato e degli importi a budget residui.

Nella scheda **Deviazione** della pagina **Controllo costi** è possibile visualizzare il costo previsto totale a confronto con il budget originale. Il confronto evidenzia tutte le differenze tra gli importi. Di conseguenza, è possibile visualizzare dove i dati non corrispondono. I valori delle deviazioni vengono calcolati nei seguenti modi:

-   **Budget originale**: importo originariamente a budget per la riga costi selezionata. L'importo a budget originale viene calcolato alla pagina **Anteprima Contabilità generale**.
-   **Costo totale**: somma del costo effettivo, del costo impegnato e del budget residuo, riportati nella scheda **Generale**.
-   **Deviazione**: differenza tra il costo totale e il budget originale.
-   **Scostamento in base alla quantità**: differenza totale dell'importo tra la previsione originale e la previsione totale. La differenza può essere espressa matematicamente come (Quantità prevista totale) x (Prezzo medio originale - Prezzo medio totale). Questo calcolo si applica solo alle ore del progetto.
-   **Scostamento in base al prezzo**: differenza totale dell'importo tra la previsione originale e la previsione totale. La differenza può essere espressa matematicamente come (Prezzo previsto originale) x (Quantità prevista originale - Quantità prevista totale). Questo calcolo si applica solo alle ore del progetto.

#### <a name="viewing-the-total-budgeted-amounts"></a>Visualizzazione degli importi a budget totali

Se **Budget totale** è selezionato come metodo di controllo dei costi nella pagina **Parametri Gestione progetti e contabilità**, nella pagina **Controllo costi** vengono calcolati i costi effettivi e i costi totali del progetto per permettere di rilevare eventuali differenze tra i due. In particolare, gli importi nelle colonne nel riquadro inferiore della scheda **Generale** della pagina **Controllo costi** vengono calcolati nei modi indicati di seguito:

-   **Costo a budget totale**: importo a budget totale per la riga dei costi selezionata.
-   **Costo effettivo**: importo totale dei costi sostenuti nel progetto fino alla data odierna per le righe dei costi selezionate.
-   **Costo impegnato**: importo totale impegnato per la riga costi selezionata.
-   **Scostamento**: differenza tra la somma dei costi effettivi e impegnati e il costo totale. Lo scostamento indica se è necessario specificare costi aggiuntivi per il budget totale.

Nella scheda **Deviazione** della pagina **Controllo costi** è possibile visualizzare la differenza tra il budget totale e il budget originale facendo riferimento ai campi riportati di seguito:

-   **Budget originale**: importo originariamente a budget per la riga costi. Il budget originale viene calcolato nella pagina **Anteprima Contabilità generale**.
-   **Costo a budget totale**: costo totale originariamente a budget per la riga costi. Il costo totale a budget viene calcolato nella pagina **Anteprima Contabilità generale**.
-   **Deviazione**: deviazione per la riga dei costi. Questo importo viene calcolato sottraendo il costo totale dal budget originale.
-   **Scostamento in base alla quantità**: differenza totale tra il budget originale e il budget totale. Questo importo viene calcolato sottraendo le ore del budget totale alle ore del budget originale e quindi moltiplicando la differenza per il prezzo di costo a budget originale. La differenza può essere espressa matematicamente come (Prezzo di costo a budget originale) × (Ore del budget originale - Ore del budget totale). Questo calcolo si applica solo alle ore del progetto.
-   **Scostamento in base al prezzo**: questo valore viene calcolato sottraendo le ore del budget totale dalle ore del budget originale e quindi moltiplicando la differenza per il numero totale di ore consumate. La differenza può essere espressa matematicamente come (Ore totali impiegate) × (Ore del budget originale - Ore del budget totale). Questo calcolo si applica solo alle ore del progetto.

### <a name="analyze-utilization"></a>Analisi dell'utilizzo

Il tasso di utilizzo è la percentuale di tempo impiegata da un lavoratore in attività fatturabili o produttive in un periodo lavorativo specifico. Le ore fatturabili sono ore del lavoratore che possono essere addebitate a un cliente specifico. 

Il tasso di utilizzo di un lavoratore si calcola dividendo il numero di ore fatturabili per il numero di ore lavorative in un periodo specifico. Ad esempio, se un lavoratore ha 30 ore fatturabili in un periodo e il numero di ore lavorative nello stesso periodo è 40, il tasso di utilizzo del lavoratore sarà 75 percento 

Quando si calcola il tasso di utilizzo di lavoratore, è possibile calcolare la percentuale fatturabile o la percentuale produttiva:

-   **Percentuale fatturabile**: differenza tra le ore fatturabili e le ore non fatturabili o ore regolari.
-   **Percentuale produttiva**: differenza tra ore produttive e ore non produttive o ore regolari. Le ore produttive sono le ore che il lavoratore dedica alla realizzazione di un progetto specifico. Le ore produttive in genere vengono fatturate ai clienti, salvo nel caso di progetti interni. Le ore non produttive non vengono mai fatturate a un cliente.

I tassi di utilizzo vengono calcolati nella pagina **Utilizzo ore**. I calcoli si basano sulle preferenze predefinite. Le preferenze specificano inoltre in che modo le ore vengono calcolate assegnando **Utilizzo** o **Costi indiretti** a ogni tipo di progetto. Ciò è valido per i calcoli delle percentuali fatturabili e per i calcoli delle percentuali produttive.

-   **Utilizzo**: le ore dichiarate per il tipo di progetto selezionato vengono sempre considerate per l'utilizzo fatturabile o produttivo.
-   **Costi indiretti**: le ore dichiarate per il tipo di progetto selezionato vengono sempre considerate per l'utilizzo non fatturabile o non produttivo.
-   **In base a proprietà riga**: le proprietà di riga di una particolare transazione oraria determinano se le ore vengono considerate fatturabili o produttive.
-   **Non incluse**: le ore non vengono considerate fattori importanti per il calcolo dell'utilizzo fatturabile o produttivo.

Nella pagina **Utilizzo ore**, oltre alla percentuale complessiva del tasso di utilizzo per un lavoratore o un progetto, è possibile visualizzare il numero di ore considerate nei calcoli dei tassi di utilizzo per ciascuno dei seguenti tipi di ore:

-   **Ore non incluse**: queste ore non sono incluse nel tasso di utilizzo delle ore.
-   **Ore incluse**: queste ore vengono calcolate aggiungendo le ore effettive e le ore improduttive. Queste ore sono incluse nel tasso di utilizzo.
-   **Ore improduttive**: se si calcola una percentuale fatturabile, queste ore sono identiche alle ore non addebitabili. Se si calcola una percentuale produttiva, queste ore sono identiche alle ore non produttive.
-   **Ore utilizzo**: se si calcola una percentuale fatturabile, queste ore sono identiche alle ore addebitabili. Se si calcola una percentuale produttiva, queste ore sono identiche alle ore produttive.

Quando si calcola il tasso di utilizzo per un lavoratore, è possibile utilizzare ore regolari o ore incluse. Se si utilizzano le ore incluse, verificare che i lavoratori registrino tutte le ore lavorate per i periodi dei fogli presenze, poiché il calcolo è espresso come percentuale di ore inserite. Quando si calcola il tasso di utilizzo ore per un progetto, un contratto di progetto, un record cliente o una categoria, è necessario utilizzare le ore incluse per eseguire il calcolo.

### <a name="review-project-statements"></a>Verifica rendiconti progetto

È possibile creare un rendiconto progetto per visualizzare uno snapshot rapido dello stato di avanzamento di un progetto. Quando si eseguono i rendiconti progetto, è possibile determinare i criteri utilizzati per calcolare il rendiconto selezionando le opzioni nella scheda **Generale** della pagina **Rendiconti progetto**. È possibile scegliere di includere o escludere le seguenti informazioni:

-   Tipi di progetto
-   Tipi di transazione
-   Data progetto/data contabile
-   Dati

Dopo che viene calcolato il rendiconto, è possibile visualizzare le seguenti informazioni nelle varie schede della pagina **Rendiconti progetto**:

-   **Generale**: contiene informazioni generali sulla struttura profitti e perdite di base del progetto.
-   **Profitti e perdite**: per informazioni sui ricavi sospesi.
-   **WIP**: contiene informazioni sui saldi conti WIP.
-   **Consumo**: contiene informazioni sul consumo di ore, articoli, spese e transazioni retributive.
-   **Fattura**: contiene informazioni sulle fatture e sulla fatturazione in acconto.
-   **Tariffa oraria**: contiene le tariffe orarie per le ore che sono registrate nei conti costi e ricavi.





