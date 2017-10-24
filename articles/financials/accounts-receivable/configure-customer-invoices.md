---
title: Creare una fattura cliente
description: 
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 77772
ms.assetid: 00b4b40c-1576-4098-9aed-ac376fdeb8c5
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 2a668e390935e157d9fc7f0ef597f25c2a7b9950
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---

# <a name="create-a-customer-invoice"></a>Creare una fattura cliente

[!include[banner](../includes/banner.md)]


Una **fattura cliente per un ordine cliente** è una fattura correlata a una vendita e che un'organizzazione presenta a un cliente. Questo tipo di fattura cliente viene creato in base a un ordine cliente che include righe ordine e numeri articolo. I numeri articolo vengono specificati e registrati nella contabilità generale. Non sono disponibili inserimenti nel giornale di registrazione secondario per una fattura cliente relativa a un ordine cliente. Per ulteriori informazioni, vedere [Creare fatture ordine cliente](tasks/create-sales-order-invoices.md).

Una **fattura a testo libero** non è correlata a un ordine cliente. Contiene righe ordine che includono conti CoGe, descrizioni a testo libero e un importo di vendita immesso manualmente. Non è possibile immettere un numero articolo in questo tipo di fattura. È necessario immettere le informazioni sull'IVA appropriate. In ogni riga fattura viene indicato il conto principale per la vendita, che può essere distribuito in più conti CoGe facendo clic su **Distribuisci importi** nella **fattura a testo libero**. Il saldo cliente, inoltre, viene registrato nel conto riepilogativo dal profilo di registrazione utilizzato per la fattura a testo libero.

Per ulteriori informazioni, vedere: 

[Creare una fattura a testo libero](tasks/create-free-text-invoice.md)

[Creare un modello a testo libero](tasks/create-free-text-invoice-template.md)

[Assegnare al cliente un modello di fattura a testo libero](tasks/assign-free-text-invoice-template-customer.md)

[Generare e registrare fatture a testo libero ricorrenti](tasks/post-recurring-free-text-invoices.md)


Una **fattura proforma** è una fattura preparata come stima degli importi effettivi prima della registrazione della fattura vera e propria. È possibile stampare una fattura proforma sia per una fattura cliente basata su un ordine cliente che per una fattura a testo libero.

## <a name="post-and-print-individual-customer-invoices-that-are-based-on-sales-orders"></a>Registrare e stampare le singole fatture cliente basate sugli ordini cliente
Utilizzare questa procedura per creare una fattura basata su un ordine cliente. È possibile effettuare questa operazione se si decide di fatturare al cliente prima di consegnare le merci o servizi. 

Quando viene registrata una fattura, la quantità **Rimanente fattura** relativa a ciascun articolo viene aggiornata con il totale delle quantità fatturate, tratto dall'ordine cliente selezionato. Se entrambe le quantità **Rimanente fattura** e **Rimanente consegna** per tutti gli articoli dell'ordine cliente sono uguali a 0 (zero), lo stato dell'ordine cliente passa a **Fatturato**. Se la quantità **Rimanente fattura** è diversa da 0 (zero), lo stato dell'ordine cliente non viene modificato e per tale ordine è possibile immettere ulteriori fatture.

Nella pagina elenco **Tutti gli ordini cliente** è possibile visualizzare lo stato degli ordini. Utilizzare la pagina elenco **Fatture cliente aperte** per visualizzare le fatture registrate.

## <a name="post-and-print-individual-customer-invoices-that-are-based-on-packing-slips-and-the-date"></a>Registrare e stampare fatture cliente individuali in base ai documenti di trasporto e alla data
Utilizzare questa procedura quando uno più documenti di trasporto sono stati registrati per l'ordine cliente. La fattura cliente si basa sui documenti di trasporto e riflette le quantità in essi contenute. Le informazioni finanziarie per la fattura si basano sulle informazioni immesse al momento della registrazione della fattura stessa. 

È possibile creare una fattura cliente in base agli articoli delle righe dei documenti di trasporto spediti fino alla data corrente, anche se non sono stati ancora spediti tutti gli articoli di un ordine cliente specifico. Questa funzionalità è utilizzabile, ad esempio, se per ogni cliente la persona giuridica emette una fattura al mese per coprire tutte le consegne del mese in questione. Ogni documento di trasporto corrisponde a una consegna completa o parziale dell'ordine cliente. 

Quando la fattura viene registrata, la quantità **Rimanente fattura** per ogni articolo viene aggiornata con il totale delle quantità consegnate, tratto dai documenti di trasporto selezionati. Se entrambe le quantità **Rimanente fattura** e **Rimanente consegna** per tutti gli articoli dell'ordine cliente sono uguali a 0 (zero), lo stato dell'ordine cliente passa a **Fatturato**. Se la quantità **Rimanente fattura** è diversa da 0 (zero), lo stato dell'ordine cliente non viene modificato e per tale ordine è possibile immettere ulteriori fatture. 

Le operazioni di magazzino vengono aggiornate con il numero di fattura e lo stato nel campo **Stato riga** dell'ordine cliente passa a **Fatturato**. 

Visualizzare lo stato degli ordini cliente nella pagina elenco **Tutti gli ordini cliente**.

## <a name="consolidate-sales-orders-or-packing-slips-for-posting"></a>Consolidare gli ordini cliente o i documenti di trasporto per la registrazione
Utilizzare questo processo quando uno o più ordini cliente sono pronti per la fatturazione e si desidera consolidarli in una singola fattura. 

È possibile selezionare più fatture nella pagina elenco **Ordine cliente** e quindi utilizzare **Genera fatture** per consolidarle. Nella pagina **Registrazione fattura** è possibile modificare l'impostazione **Ordine riepilogativo** per riepilogare per numero ordine (in cui sono presenti più documenti di trasporto per un singolo ordine cliente) o per conto fatture (in cui sono presenti più ordini cliente per un singolo conto fatture). Utilizzare il pulsante **Disponi** per consolidare gli ordini cliente in singole fatture, in base alle impostazioni **Ordine riepilogativo**.

## <a name="additional-settings-that-change-the-posting-behavior"></a>Impostazioni aggiuntive che modificano il comportamento di registrazione
I seguenti campi modificano il comportamento del processo di registrazione.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Campo</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Quantità</td>
<td>Selezionare le quantità su cui basare la registrazione del documento. Le opzioni disponibili variano, in base al tipo di documento che si sta registrando, ad esempio un documento di trasporto o una fattura.
<ul>
<li><strong>Consegna ora</strong>: selezionare tutte le quantità immesse nel campo <strong>Consegna ora</strong>. Utilizzare questa opzione per confermare o consegnare un ordine parziale.</li>
<li><strong>Prelevata</strong>: selezionare tutte le quantità che sono state prelevate.</li>
<li><strong>Tutto</strong>: selezionare tutte le quantità dell'ordine cliente che non sono state ancora aggiornate in base al tipo di documento corrente.</li>
<li><strong>Documento di trasporto</strong>: selezionare tutte le quantità che sono state aggiornate in base a un documento di trasporto</li>
<li><strong>Quantità prelevata e prodotti non stoccati</strong>: selezionare tutte le quantità che sono state prelevate e tutte le quantità di prodotti non stoccate.</li>
</ul></td>
</tr>
<tr class="even">
<td>Registrazione</td>
<td><ul>
<li>Selezionare questa opzione per inserire nel giornale di registrazione l'ordine cliente.</li>
<li>Deselezionare questa opzione per stampare un ordine cliente proforma. <strong>Nota:</strong> Se è stato stipulato un accordo per uno scadenzario pagamenti, quest'ultimo non verrà visualizzato nell'ordine cliente proforma, Gli scadenziari pagamenti sono mostrati soltanto negli ordini cliente effettivi.</li>
</ul></td>
</tr>
<tr class="odd">
<td>Ultima selezione</td>
<td>Selezionare questa opzione per applicare la query selezionata in un momento successivo. Questa opzione viene utilizzata per i processi batch. La query viene eseguita quando viene eseguito il processo batch.</td>
</tr>
<tr class="even">
<td>Riduci quantità</td>
<td>Selezionare questa opzione per ridurre automaticamente la quantità consegnata quando il documento viene registrato, in modo che la quantità consegnata corrisponda alle scorte disponibili.</td>
</tr>
<tr class="odd">
<td>Stampa</td>
<td>Specifica quando stampare i documenti:
<ul>
<li><strong>Corrente</strong>: consente di eseguire la stampa di documenti dopo l'aggiornamento di ciascuna fattura.</li>
<li><strong>Dopo:</strong> la stampa viene effettuata dopo l'aggiornamento di tutte le fatture.</li>
</ul>
<strong>Nota:</strong> il campo <strong>Stampa</strong> sarà disponibile solo se si seleziona l'opzione <strong>Stampa fattura</strong>, <strong>Stampa conferma</strong>, <strong>Stampa distinta di prelievo</strong> o <strong>Stampa documento di trasporto</strong>. Ad esempio, nella pagina <strong>Ordinamento moduli</strong>, il sistema è stato impostato in modo da ordinare le informazioni in base al conto fatture. Sarà quindi possibile selezionare <strong>Dopo</strong> per stampare i documenti in un batch ordinato in base al conto fatture. In caso contrario, i documenti vengono stampati prima che l'elaborazione venga completata e non vengono ordinati nell'ordine specificato nella pagina <strong>Ordinamento moduli</strong>.</td>
</tr>
<tr class="even">
<td>Stampa fattura</td>
<td>Selezionare questa opzione per stampare la fattura. Se questa opzione è spenta, è possibile registrare una fattura senza stamparla.</td>
</tr>
<tr class="odd">
<td>Invia posta elettronica</td>
<td>Selezionare questa opzione per inviare la fattura per l'ordine cliente al cliente come allegato di posta elettronica dopo la registrazione della fattura. Gli allegati vengono inviati come file PDF e XML. Questa opzione è disponibile solo se si seleziona l'opzione <strong>Abilita CFD (fatture elettroniche)</strong> nella pagina <strong>Parametri fatture elettroniche</strong>. <strong>Nota</strong> (MEX) Questo controllo è disponibile solo per le persone giuridiche il cui indirizzo principale è in Messico.</td>
</tr>
<tr class="even">
<td>Utilizza destinazione gestione stampa</td>
<td>Selezionare questa opzione per utilizzare le impostazioni di stampa specificate per la transazione, il documento, o il modulo nella pagina <strong>Impostazione Gestione stampa</strong>.</td>
</tr>
<tr class="odd">
<td>Verifica limite di credito</td>
<td>Selezionare le informazioni che devono essere analizzate quando viene eseguito un controllo del limite di credito.
<ul>
<li><strong>Nessuno</strong>: non è presente alcuna richiesta di controllo del limite di credito.</li>
<li><strong>Saldo</strong>: il limite di credito viene verificato rispetto al saldo cliente.</li>
<li><strong>Saldo+Documento di trasporto o entrata prodotti</strong>: il limite di credito viene verificato rispetto al saldo e alle consegne del cliente.</li>
<li><strong>Saldo+Tutto</strong>: la verifica del limite di credito viene eseguita in base al saldo del cliente, alle consegne e agli ordini aperti.</li>
</ul></td>
</tr>
<tr class="even">
<td>Correzione credito</td>
<td>Selezionare questa opzione per visualizzare una nota di accredito come debito nelle transazioni giustificativo.</td>
</tr>
<tr class="odd">
<td>Quantità rimanente a credito</td>
<td>Se si registra una nota di accredito, selezionare questa opzione per mantenere in ordinazione la quantità rimanente. Se questa opzione non viene selezionata, la quantità rimanente verrà impostata su 0 (zero).</td>
</tr>
<tr class="even">
<td>Aggiorna riepilogo per</td>
<td>Selezionare la modalità di riepilogo di più ordini cliente.
<ul>
<li><strong>Nessuno</strong>: gli ordini cliente non vengono riepilogati. Per ogni ordine cliente, ad esempio, viene creata una fattura separata.</li>
<li><strong>Conto fatture</strong>: riepiloga tutti gli ordini selezionati in base ai criteri impostati nella pagina <strong>Parametri aggiornamento riepilogativo</strong>.</li>
<li><strong>Ordine</strong>: un intervallo di ordini selezionato viene riepilogato in un unico ordine specificato. Gli ordini vengono riepilogati in base ai criteri impostati nella pagina <strong>Parametri aggiornamento riepilogativo</strong>. Se si seleziona questa opzione, è necessario selezionare un valore nel campo <strong>Ordine cliente</strong>.</li>
<li><strong>Riepilogo automatico</strong>: se sono stati specificati aggiornamenti riepilogativi nella pagina <strong>Aggiornamento riepilogativo</strong>, tutti gli ordini selezionati vengono riepilogati in base ai criteri impostati nella pagina <strong>Parametri aggiornamento riepilogativo</strong>. Se gli aggiornamenti riepilogativi non sono stati specificati, l'ordine verrà registrato separatamente.</li>
<li><strong>Documento di trasporto</strong>: un intervallo di ordini selezionato viene riepilogato in un'unica fattura per ogni documento di trasporto. Questa opzione è disponibile solo se nel campo <strong>Quantità</strong> è selezionata l'opzione <strong>Documento di trasporto</strong>.</li>
</ul></td>
</tr>
</tbody>
</table>






