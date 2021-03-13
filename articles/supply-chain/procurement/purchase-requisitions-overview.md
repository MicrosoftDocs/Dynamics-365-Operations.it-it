---
title: Panoramica della richiesta di acquisto
description: Vengono descritti il flusso di lavoro delle richieste di acquisto e i diversi stati che può avere una richiesta di acquisto.
author: RichardLuan
manager: tfehr
ms.date: 11/02/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchReqConsolidation, PurchReqCreate, PurchReqCreatePurchDetails, PurchReqCreatePurchListPage, PurchReqTable, PurchReqTableListPage, PurchReqConsolidationPartByVendor, PurchReqConsolidationLineDetail, PurchReqConsolidationCreate, PurchReqConsolidationBulkEdit, PurchReqConsolidationAddLine
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2174
ms.assetid: 77d07119-4d9f-4c0e-acbe-d319203571ab
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 189debe46ea28808cf3081a7d8f49686298e8c8e
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/16/2021
ms.locfileid: "5020081"
---
# <a name="purchase-requisition-overview"></a>Panoramica della richiesta di acquisto

[!include [banner](../includes/banner.md)]

Vengono descritti il flusso di lavoro delle richieste di acquisto e i diversi stati che può avere una richiesta di acquisto.

A seconda della configurazione dell'organizzazione, è possibile creare richieste di acquisto per i prodotti utilizzati. Una richiesta di acquisto è un documento interno con cui si autorizza il reparto acquisti ad acquistare articoli o servizi.  

Una volta approvata una richiesta di acquisto, questa può essere utilizzata per generare un ordine fornitore. Gli ordini fornitore sono i documenti esterni che il reparto acquisti invia ai fornitori.

## <a name="creating-purchase-requisitions"></a>Creazione di richieste di acquisto
È possibile creare una richiesta di acquisto nella pagina **Richieste di acquisto personali** e selezionare gli articoli e i servizi desiderati. È possibile selezionare articoli da un catalogo di approvvigionamento che l'organizzazione ha creato oppure richiedere articoli che non si trovano in un catalogo, selezionando una categoria di approvvigionamento e immettendo i dati del prodotto nel modulo.  

Prima di inviare una richiesta di acquisto per la revisione, è necessario configurare il flusso di lavoro nel client. Il processo del flusso di lavoro è necessario per far avanzare la richiesta di acquisto nei vari passaggi della procedura di revisione, dallo stato iniziale di **Bozza** fino allo stato finale di **Approvata**.

### <a name="purchase-requisition-statuses"></a>Stati della richiesta di acquisto

Quando si crea una richiesta di acquisto, a questa è assegnato uno stato. A ogni riga aggiunta alla richiesta di acquisto è anche assegnato uno stato. Se si invia una richiesta di acquisto al flusso di lavoro per la revisione, lo stato della richiesta di acquisto e di ciascuna riga viene aggiornato mentre le righe avanzano nel processo del flusso di lavoro.  

È possibile configurare il processo del flusso di lavoro della richiesta di acquisto in modo da inoltrare la richiesta di acquisto nel processo di revisione come singolo documento. In alternativa, le righe della richiesta di acquisto possono essere inoltrate singolarmente agli opportuni revisori. Se le righe della richiesta di acquisto vengono esaminate singolarmente, lo stato di ogni riga della richiesta di acquisto può essere aggiornato mentre la riga avanza nel processo di revisione. Quando tutte le righe hanno completato il processo di revisione e non rimangono altri passaggi di revisione per la richiesta di acquisto, viene aggiornato lo stato dell'intera richiesta di acquisto.

### <a name="purchase-requisition-workflow"></a>Flusso di lavoro delle richieste di acquisto

Nel diagramma riportato di seguito vengono illustrati gli stati assegnati a una richiesta di acquisto e a una riga della richiesta di acquisto mentre avanzano nel processo di revisione.  

[![Stati dell'intestazione e delle righe della richiesta di acquisto](./media/purchasereq_headerline_statuses.jpg)](./media/purchasereq_headerline_statuses.jpg)

### <a name="purchase-requisition-header-and-line-status-relationships"></a>Intestazione richiesta di acquisto e relazioni degli stati delle righe

Lo stato generale della richiesta di acquisto viene determinato dallo stato delle relative righe. Pertanto, si dovrà completare il processo di revisione per tutte le righe della richiesta di acquisto prima di poter completare il processo di revisione dell'intera richiesta di acquisto. Nella tabella riportata di seguito vengono descritti gli stati assegnati all'intestazione e alle righe della richiesta di acquisto man mano che la richiesta di acquisto avanza nel processo del flusso di lavoro.

<table>
<thead>
<tr class="header">
<th>Stato richiesta di acquisto</th>
<th>Stato riga richiesta di acquisto</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Bozze</td>
<td>Bozze</td>
<td>La richiesta di acquisto e la riga della richiesta di acquisto sono state create, ma non inviate per la revisione. Le richieste di acquisto e le righe della richiesta di acquisto con lo stato <strong>Bozza</strong> possono essere modificate. Una richiesta di acquisto o una riga della richiesta di acquisto è inoltre nello stato <strong>Bozza</strong> se è stata richiamata ma non è stato inviata di nuovo per la revisione. <strong>Nota:</strong> è possibile inviare o richiamare una richiesta di acquisto a livello di documento. Tuttavia, non è possibile inviare o richiamare una singola riga della richiesta di acquisto.</td>
</tr>
<tr class="even">
<td>In revisione</td>
<td><ul>
<li>In revisione</li>
<li>Rifiutati</li>
</ul></td>
<td>Se il flusso di lavoro è stato configurato per inoltrare le righe della richiesta di acquisto a singoli revisori, ciascuna riga può avere lo stato <strong>In revisione</strong> o <strong>Rifiutato</strong>. Lo stato della richiesta di acquisto viene aggiornato quando il processo di revisione è stato completato per tutte le righe della richiesta di acquisto e non vi sono altri passaggi di revisione per la richiesta di acquisto.
<ul>
<li><strong>In revisione</strong>: le righe della richiesta di acquisto sono state inviate in revisione. Quando il processo del flusso di lavoro è completo per una riga della richiesta di acquisto, questa resta nello stato <strong>In revisione</strong> finché non vengono riviste tutte le righe della richiesta di acquisto.</li>
<li><strong>Rifiutata</strong>: una riga della richiesta di acquisto è stata rifiutata. Le righe della richiesta di acquisto rifiutate possono essere modificate e inviate nuovamente.</li>
</ul>
Se si invia nuovamente una riga della richiesta di acquisto che è stata rifiutata, il processo di revisione ricomincia per tutte le righe della richiesta di acquisto ancora in revisione. </br><strong>Nota:</strong> è possibile richiamare una richiesta di acquisto che è già stata inviata. Quando si richiama una richiesta di acquisto, vengono richiamate anche tutte le altre righe della richiesta di acquisto. Le righe della richiesta di acquisto richiamate possono essere eliminate.</td>
</tr>
<tr class="odd">
<td>Rifiutati</td>
<td>Rifiutati</td>
<td>La richiesta di acquisto e tutte le righe della richiesta di acquisto sono state rifiutate. Le richieste di acquisto e le righe delle richieste rifiutate possono essere inviate nuovamente.</td>
</tr>
<tr class="even">
<td>Approvati</td>
<td><ul>
<li>Approvati</li>
<li>Annullato</li>
<li>Chiuso</li>
</ul></td>
<td>Tutte le righe della richiesta di acquisto hanno completato il processo di revisione e non vi sono più passaggi di revisione per la richiesta di acquisto.
<ul>
<li><strong>Approvato</strong>: il processo di revisione della riga della richiesta di acquisto è stato completato e la riga viene approvata.</li>
<li><strong>Annullato</strong>: la riga della richiesta di acquisto è stata approvata ma è stata annullata perché non più necessaria. È possibile annullare solo le righe della richiesta di acquisto approvate.</li>
<li><strong>Chiuso</strong>: la riga della richiesta di acquisto è stata approvata e i documenti sono stati generati, a seconda dello scopo della richiesta.
<ul>
<li>Se lo scopo della richiesta di acquisto è consumo, è stato generato un ordine fornitore per la riga della richiesta di acquisto.</li>
<li>Se lo scopo della richiesta di acquisto è il rifornimento, uno o più documenti di evasione sono stati generati.</li>
</ul></li>
</ul></td>
</tr>
<tr class="odd">
<td>Annullato</td>
<td>Annullato</td>
<td>La richiesta di acquisto e tutte le righe della richiesta di acquisto sono state annullate.</br> <strong>Note:</strong> se non è più richiesto un articolo indicato in una riga della richiesta di acquisto, è necessario annullare la riga della richiesta di acquisto se è già stata approvata. È possibile annullare solo le righe della richiesta di acquisto approvate. Se righe della richiesta di acquisto sono in revisione, anche la richiesta avrà lo stato <strong>In revisione</strong>. In questo caso, è possibile richiamare la richiesta di acquisto ed eliminare la riga della richiesta di acquisto appropriata.</td>
</tr>
<tr class="even">
<td>Chiuso</td>
<td><ul>
<li>Chiuso</li>
<li>Annullato</li>
</ul></td>
<td>La richiesta di acquisto viene chiusa e uno o più documenti di evasione sono stati generati.
<ul>
<li><strong>Chiuso</strong>: la riga della richiesta di acquisto è stata approvata e i documenti sono stati generati, a seconda dello scopo della richiesta.
<ul>
<li>Se lo scopo della richiesta di acquisto è consumo, è stato generato un ordine fornitore per la riga della richiesta di acquisto.</li>
<li>Se lo scopo della richiesta di acquisto è il rifornimento, uno o più documenti di evasione sono stati generati.</li>
</ul></li>
<li><strong>Annullato</strong>: la riga della richiesta di acquisto è stata approvata ma è stata annullata perché non più necessaria. È possibile annullare solo le righe della richiesta di acquisto approvate.</li>
</ul>
<strong>Nota:</strong> se non è più richiesto un articolo indicato in una riga della richiesta di acquisto che è stata chiusa, è necessario annullare la riga nel documento di evasione generato per la riga.</td>
</tr>
</tbody>
</table>

## <a name="distributing-costs-to-multiple-financial-accounts"></a>Distribuire i costi a più conti finanziari
È possibile distribuire il costo di un prodotto incluso in una richiesta di acquisto a più conti finanziari. Se l'organizzazione utilizza dimensioni, ad esempio centri di costo e reparti, è possibile distribuire il costo di un prodotto alle dimensioni relative ai conti finanziari.

## <a name="requisition-purposes"></a>Scopi della richiesta
Gli scopi della richiesta di acquisto rendono il processo di evasione della richiesta più flessibile. Quando si crea una richiesta di acquisto, è possibile assegnarle uno di due scopi: consumo o rifornimento. In base allo scopo della richiesta di acquisto e della configurazione dell'organizzazione, la richiesta può essere soddisfatta da un ordine fornitore, un ordine di trasferimento, un ordine di produzione o un kanban.  

Nei criteri di approvvigionamento è possibile determinare gli scopi disponibili quando una richiesta di acquisto viene creata per l'organizzazione.

### <a name="requisitions-that-have-a-purpose-of-consumption"></a>Richieste di acquisto con scopo di consumo

Una richiesta di acquisto con scopo di consumo rappresenta una domanda di articoli o servizi che verranno utilizzati internamente dall'organizzazione. La domanda creata da questo tipo di richiesta di acquisto è sempre soddisfatta da un ordine fornitore. Se Supply Chain Management è impostato in modo da generare automaticamente gli ordini fornitore, gli ordini fornitore vengono generati dopo che viene approvata la richiesta di acquisto.

### <a name="requisitions-that-have-a-purpose-of-replenishment"></a>Richieste di acquisto con scopo di rifornimento

Una richiesta di acquisto con scopo di rifornimento rappresenta una domanda di rifornimento del magazzino. Si potrebbe ad esempio decidere di creare una richiesta di acquisto per rifornirsi di articoli da vendere in una specifica ubicazione di vendita al dettaglio in un momento specifico. La domanda della richiesta di acquisto può essere soddisfatta da un ordine fornitore, un ordine di trasferimento, un ordine di produzione o un kanban.  

Quando lo scopo della richiesta è il rifornimento, la domanda viene espressa come quantità anziché importo monetario. Di conseguenza, la contabilità di impegno di spesa, il controllo del budget, le regole di business per la determinazione dei cespiti (BRAD), la contabilità di progetto e alcune regole correlate non sono applicabili. Solo i prodotti che vengono stoccati e rilasciati alla persona giuridica specificata possono soddisfare la domanda della richiesta di rifornimento. Per definire i prodotti disponibili quando lo scopo della richiesta di acquisto è rifornimento, utilizzare la pagina **Regola dei criteri di accesso alle categorie di rifornimento**.  

Per utilizzare le richieste di acquisto con scopo di rifornimento, è necessario impostare la programmazione generale in modo da includere la domanda della richiesta di acquisto. Il metodo di evasione della domanda creata da una richiesta con scopo di rifornimento viene automaticamente determinato dai criteri di fornitura impostati per gli articoli nell'organizzazione e pianificati con la programmazione generale.

## <a name="purchase-requisitions-and-requests-for-quotation"></a>Richieste di acquisto e richieste di offerte
In alcuni casi, è necessario avviare un processo di richiesta di offerta (RdO) per identificare il fornitore e il prezzo per i prodotti richiesti in una richiesta di acquisto. Una richiesta di offerta può essere generata quando la richiesta di acquisto è in fase di revisione. Quando si accetta l'offerta, le informazioni su fornitore, prezzo e così via vengono trasferite alla richiesta di acquisto.  

È possibile mettere una richiesta di acquisto in attesa selezionando la casella di controllo **In attesa** nella pagina **Dettagli richiesta di acquisto** . L'elaborazione della richiesta di acquisto può continuare solo dopo che si rimuove la sospensione deselezionando la casella di controllo.  

> [!NOTE]
> In e-Procurement, la richiesta di offerta per la richiesta di acquisto può consentire ai fornitori di aggiungere righe alternative. In questo caso le alternative approvate sono riflesse nella richiesta di acquisto.

## <a name="demand-consolidation"></a>Consolidamento domanda
Consolidando le righe della richiesta di acquisto da più richieste di acquisto, è possibile aumentare la capacità di negoziazione con i fornitori per ottenere prezzi migliori, diminuire i costi di spedizione e di gestione e ridurre i costi generali.  

Le righe della richiesta di acquisto sono idonee per il consolidamento della domanda solo se le seguenti istruzioni sono vere:

-   La richiesta di acquisto è stata approvata.
-   La richiesta di acquisto soddisfa i criteri della regola dei criteri di acquisto per l'elaborazione manuale e il consolidamento della domanda.

Le righe della richiesta di acquisto approvate che soddisfano i criteri per l'elaborazione manuale sono elencate nella pagina **Rilascia richieste di acquisto approvate**. Se una riga della richiesta di acquisto soddisfa anche i criteri per il consolidamento domanda, è possibile aggiungerla a un'opportunità di consolidamento.  

Un'opportunità di consolidamento è un set di righe della richiesta di acquisto che vengono raggruppate in modo che il professionista dell'acquisto possa negoziare il migliore accordo con i fornitori. Le righe della richiesta di acquisto selezionate in un'opportunità di consolidamento vengono visualizzate nella pagina **Consolidamento richiesta di acquisto**. È possibile modificare le righe in questa pagina, se sono necessarie modifiche. È inoltre possibile aggiungere nuove righe o rimuovere le righe esistenti dall'opportunità di consolidamento.  

Dopo avere aggiunto le righe della richiesta di acquisto a un'opportunità di consolidamento e avere apportato eventuali modifiche, è possibile creare un ordine fornitore per le righe della richiesta di acquisto consolidate.  

> [!NOTE]
> Le modifiche apportate a una riga della richiesta di acquisto nella pagina **Consolidamento richiesta di acquisto** vengono riflesse nell'ordine fornitore creato. Nella richiesta di acquisto la riga tuttavia rimarrà invariata in modo da conservare lo storico.  

Per creare un ordine fornitore per le righe della richiesta di acquisto non idonee per il consolidamento della domanda o non selezionate per un'opportunità di consolidamento, è necessario elaborare le righe manualmente.

### <a name="consolidating-purchase-requisition-lines"></a>Consolidamento delle righe della richiesta di acquisto

Il processo per il consolidamento della domanda inizia nel momento in cui una richiesta di acquisto viene approvata in un flusso di lavoro e le prenotazioni budget e gli impegni preliminari di spesa sono stati registrati, se il controllo del budget è configurato per l'organizzazione. Nel seguente diagramma viene illustrato il flusso di processo per il consolidamento della domanda.  

[![Flusso del processo per il consolidamento della domanda](./media/demand-consolidation.gif)](./media/demand-consolidation.gif)  

Per consolidare le righe della richiesta di acquisto approvate, attenersi alla seguente procedura:

1.  Esaminare le righe approvate della richiesta di acquisto tenute in sospeso per l'elaborazione manuale e idonee per il consolidamento della domanda.
2.  Selezionare righe da aggiungere a un'opportunità di consolidamento.
3.  Creare una nuova opportunità di consolidamento o aggiungere le righe della richiesta di acquisto a un'opportunità di consolidamento esistente.
4.  Applicare tutte le modifiche da apportare alle righe della richiesta e rimuovere le voci della richiesta che non si desidera più includere nell'opportunità di consolidamento.
5.  Creare gli ordini fornitore per le righe consolidate della richiesta di acquisto o per le righe della richiesta di acquisto in un'opportunità di consolidamento.


<a name="additional-resources"></a>Risorse aggiuntive
--------

[Creare una richiesta per il consumo](tasks/create-requisition-consumption.md)

[Flusso di lavoro delle richieste di acquisto](purchase-requisitions-workflow.md)



