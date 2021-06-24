---
title: Approvare e confermare gli ordini fornitore
description: Questo argomento descrive gli stati di un ordine fornitore dopo che è stato creato e l'effetto dell'abilitazione della gestione delle modifiche sul POS.
author: kamaybac
ms.date: 04/02/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: PurchTable, PurchTablePart, PurchOrderInReview, PurchOrderApproved, PurchOrderInDraft, PurchOrderAssignedToMe, VendPurchOrderJournalListPage, PurchTableWorkflowDropDialog, VendPurchOrderJournal
audience: Application User
ms.reviewer: kamaybac
ms.custom: 93143
ms.assetid: cd12a944-c52c-4579-a301-7abe1d237c72
ms.search.region: Global
ms.search.industry: ''
ms.author: dabourq
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0a9b387be0b28564dd7ae88af33812a8bbf034c0
ms.sourcegitcommit: ff09736563d3cd2bc74c7664edd1767b218401cb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2021
ms.locfileid: "6188292"
---
# <a name="approve-and-confirm-purchase-orders"></a>Approvare e confermare gli ordini fornitore

[!include [banner](../includes/banner.md)]

In questo argomento vengono descritti gli stati che attraversa un ordine fornitore (PO) dopo che è stato creato e l'effetto dell'attivazione di gestione delle modifiche sui PO.

Dopo aver creato un ordine fornitore (PO), potrebbe essere necessario passare attraverso un processo di approvazione. Dopo che il fornitore ha accettato l'ordine, il PO è impostata su uno stato di **Confermato**.

## <a name="approval-of-purchase-orders"></a>Approvazione di ordini fornitore
I PO che non utilizzano la gestione delle modifiche hanno uno stato di **Approvato** appena creati, mentre i PO che utilizzano la gestione delle modifiche hanno uno stato di **Bozza** quando vengono creati. Un ordine fornitore creato consolidando un ordine pianificato dalla pianificazione generale viene impostato sempre su **Approvato**, indipendentemente dalle impostazioni della gestione modifiche. Un ordine fornitore consente di creare transazioni di magazzino solo quando raggiunge lo stato **Approvato**. Di conseguenza, tale inventario non viene visualizzato come disponibile per la prenotazione o il contrassegno fino a quando non viene accettato l'ordine.

Abilitare la gestione modifiche per i PO impostando l'opzione **Attiva gestione modifiche** nella pagina **Parametri di approvvigionamento**. Quando è attivata la gestione delle modifiche, i PO deve passare attraverso un flusso di lavoro di approvazione dopo essere stati completati. Supply Chain Management dispone di un editor di processo del flusso di lavoro in cui è possibile definire un flusso di lavoro per rappresentare il processo di approvazione. Il flusso di lavoro può includere regole per l'approvazione automatica, regole che determinano chi verrà assegnato per approvare specifici PO e regole di escalation di un flusso di lavoro che è stato in attesa di approvazione per molto tempo. È possibile attivare il processo di gestione delle modifiche per tutti i fornitori o per fornitori specifici. È inoltre possibile impostare il processo in modo che possa essere ignorato per singoli PO.

Quando è attivata la gestione delle modifiche, i PO passano attraverso sei stati di approvazione, dal **Bozza** a **Finalizzato**. Dopo l'approvazione di un ordine, gli utenti che desiderano modificalo devono utilizzare l'azione **Richiedi modifica**.

| Stato approvazione | Descrizione                                                                      | Richiedi modifica è abilitata |
|-----------------|----------------------------------------------------------------------------------|---------------------------|
| Bozze           | L'ordine fornitore è una bozza e non è stato sottoposto ad approvazione nel flusso di lavoro.     | Nessuno                        |
| In revisione       | L'ordine fornitore è stato inviato per l'approvazione nel flusso di lavoro. L'approvazione è in sospeso.       | No                        |
| Rifiutati        | L'ordine fornitore è stato rifiutato durante il processo di approvazione.                                 | No                        |
| Approvati        | L'ordine fornitore è stato approvato.                                                             | Sì                       |
| Confermato       | L'ordine fornitore è stato confermato. Un ordine fornitore non può essere confermato finché non viene approvato.        | Sì                       |
| Finalizzato       | L'ordine fornitore è stato reso finale. È ora finanziariamente chiuso e non può più essere modificato. | Nessuno                        |

## <a name="confirming-purchase-orders"></a>Conferma di ordini fornitore
I PO che hanno uno stato di approvazione di **Approvato** possono passare attraverso passaggi aggiuntivi prima di essere confermati. Ad esempio, potrebbe essere necessario inviare una richiesta di informazioni sull'acquisto al fornitore per informazioni su prezzi, sconti o le date di consegna. In questo caso, è possibile impostare l'ordine fornitore sullo stato **In revisione esterna** utilizzando l'azione **Richiesta informazioni su acquisto**.

I fornitori che sono impostati per utilizzare il portale fornitori possono esaminare gli ordini nel portale e approvarli o rifiutarli. Durante questo processo di revisione, l'ordine fornitoredi ha lo stato **In revisione esterna**. Il portale fornitori può essere configurato in modo che una conferma del fornitore confermi automaticamente l'ordine in Supply Chain Management. In alternativa, è possibile confermare manualmente un ordine fornitore dopo aver ricevuto conferma dal fornitore. Se un fornitore rifiuta un ordine fornitore, il rifiuto viene ricevuto con il motivo del rifiuto e suggerimenti per le modifiche. In questo caso, lo stato dell'ordine fornitore rimane **In revisione esterna**.

È inoltre disponibile un'opzione per generare una conferma proforma per un ordine prima che la conferma effettiva è stata elaborata. Questa opzione crea solo un report che è possibile condividere con il fornitore. Non crea alcuna informazione di giornale di registrazione.

Dopo che il fornitore ha accettato l'ordine, il passaggio successivo consiste nel registrare l'ordine fornitore come impegnato. È possibile completare questo passaggio utilizzando l'azione **Conferma** azione o l'azione **Conferma**. Entrambe le azioni impostano lo stato di approvazione dell'ordine su **Confermato**. La conferma di un ordine avvia due ulteriori processi:

-   Un giornale di registrazione viene creato per memorizzare una copia esatta di ciò che è stato confermato nel sistema. In alcuni casi, gli ordini richiedono modifiche e giornali di registrazione aggiuntivi vengono creati dopo la conferma dell'ordine aggiornato. Questi giornali di registrazione consentono di visualizzare lo storico delle diverse versioni dell'ordine che sono stati confermate.
-   Distribuzioni contabili vengono create e si verificano controlli ordine e le verifiche del budget se è stata attivata questa funzionalità. Se uno dei controlli ha esito negativo, viene visualizzato un messaggio di errore indicante che è necessario apportare modifiche all'ordine fornitore prima che sia confermato nuovamente.

Un fornitore potrebbe richiedere qualche tipo di garanzia che il pagamento verrà fornito per un acquisto. Esistono vari metodi per fornire questa garanzia all'interno dei processi di contabilità fornitori. Ad esempio, l'azione **Pagamento anticipato** riserva fondi per l'ordine fornitore e il pagamento anticipato viene registrato nell'ordine.

## <a name="changing-purchase-orders"></a>Modifica degli ordini fornitore
In alcuni casi, potrebbe essere necessario modificare un ordine fornitore dopo il raggiungimento di uno stato di approvazione di **Approvato** o **Confermato**.

Se l'ordine fornitore è stato creato utilizzando un processo di gestione delle modifiche, è possibile apportare modifiche richiamando l'ordine oppure, se l'ordine è già stato approvato, utilizzando l'azione **Richiedi modifica**. In questo caso, lo stato di approvazione viene nuovamente modificato in **Bozza**, ed è quindi possibile modificare l'ordine. Dopo avere apportato le modifiche, potrebbe essere necessario inviare di nuovo il PO per la riapprovazione. È possibile configurare i tipi di modifiche che richiedono la riapprovazione utilizzando una regola dei criteri **Regola di riapprovazione per gli ordini fornitore** nella pagina **Criteri acquisto**.

Se parte della quantità ordinata per una riga dell'ordine fornitore è stata consegnata, non è possibile modificare la quantità ordinata quando l'ordine fornitore si trova in **Bozze**. Tuttavia, è possibile modificare la quantità **Rimanente consegna** nella riga per l'ordine fornitore che si trova in **Bozze**.

Dopo che un ordine è stato confermato non è possibile eliminarlo. Tuttavia, è possibile annullare la quantità totale o la quantità rimanente in un ordine, purché la quantità non sia stata ricevuta o fatturata. È quindi possibile utilizzare l'azione **Finalizza** per prevenire l'ulteriore elaborazione. 


## <a name="canceling-purchase-orders"></a>Annullamento di ordini fornitore

Un ordine fornitore può essere annullato usando l'azione **Annulla** nell'intestazione.

Se la quantità è stata parzialmente registrata, ricevuta o fatturata, è possibile annullare solo la quantità rimanente che non è stata registrata, ricevuta o fatturata. La quantità dell'ordine viene quindi ridotta di conseguenza. Quando la quantità sulla riga viene aggiornata, viene aggiornato anche lo stato della riga. Ad esempio, la quantità originale nella riga è 5 e viene ricevuta una quantità di 3. In questo caso, solo due possono quantità essere cancellate. La riga viene quindi aggiornata allo stato **Ricevuta**.

Se una quantità rimanente per la consegna viene aggiunta alla riga ordine e supera la quantità nella riga ordine, l'azione **Annulla** non annulla la quantità in eccesso. In questo caso, la riga rimane nello stato **Ordine aperto** poiché ha quantità rimanente. Ad esempio, la quantità originale nella riga è 5 e la quantità rimanente per la consegna è 7. Se l'ordine viene annullato, cinque quantità vengono annullate e rimane una quantità di 2, come si può vedere nelle transazioni di inventario.

Per annullare l'intera quantità su una riga di ordine fornitore, è necessario annullare la quantità rimanente per la consegna sulla riga. La riga sarà quindi aggiornata allo stato **Annullata**.

Se un ordine fornitore è in gestione delle modifiche, qualsiasi modifica, come l'annullamento dell'ordine o della quantità rimanente per la consegna, deve essere inviata al sistema del flusso di lavoro e approvata prima che il processo possa essere completato e le transazioni di inventario possano essere aggiornate come annullate.

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica degli ordini fornitore](purchase-order-overview.md)

[Creare gli ordini fornitore](purchase-order-creation.md)

[Entrata prodotti e ordini fornitore](product-receipt-against-purchase-orders.md)

[Panoramica delle fatture fornitore](../../finance/accounts-payable/vendor-invoices-overview.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]