---
title: Panoramica dell'ordine fornitore
description: In questo articolo vengono fornite informazioni generali sugli ordini fornitore (PO) e collegamenti a ulteriori articoli correlati alle varie fasi che attraversa un PO.
author: kamaybac
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: PurchTable, PurchTablePart, PurchLineOpenOrder, PurchConfirmationRequestJournal
audience: Application User
ms.reviewer: kamaybac
ms.custom: 93083
ms.assetid: e9b7bc5b-1d7e-4ec2-97be-d655274b0613
ms.search.region: Global
ms.author: dabourq
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 77410fd131ecdcb05b682ac4660ec8c453b75218
ms.sourcegitcommit: ff09736563d3cd2bc74c7664edd1767b218401cb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2021
ms.locfileid: "6188223"
---
# <a name="purchase-order-overview"></a>Panoramica dell'ordine fornitore

[!include [banner](../includes/banner.md)]

In questo articolo vengono fornite informazioni generali sugli ordini fornitore (PO) e collegamenti a ulteriori articoli correlati alle varie fasi che attraversa un PO.

Un ordine fornitore (PO) è un documento che rappresenta un contratto con un fornitore per acquistare beni o servizi. Il documento consente inoltre di tenere traccia delle entrate di prodotti che vengono effettuate rispetto all'ordine e, successivamente, la contabilità delle fatture che il fornitore emette rispetto all'ordine.  

La pagina **Ordini fornitore** contiene una panoramica degli ordini disponibili e consente di modificare gli ordini. Quando si apre un PO, è possibile selezionare la visualizzazione **Intestazione**, che contiene informazioni specificate solo una volta per ogni ordine fornitore, esempio i dettagli del fornitore. In alternativa, è possibile selezionare la visualizzazione **Righe**, in cui è possibile modificare le righe dell'ordine. In genere, si alterneranno queste due visualizzazioni mentre si modificano gli ordini fornitore. Le spese non vengono elencate direttamente nella pagina **Ordini fornitore**, ma sono accessibili tramite i menu nell'intestazione e nelle righe ordine.  

Sono disponibili numerosi report in cui è possibile visualizzare informazioni su PO, entrate prodotti e fatture fornitore. Questi report si trovano nei moduli **Approvvigionamento** e **Contabilità fornitori**.  

Le aree di lavoro **Preparazione ordini acquisto** e **Ricevimento e follow-up ordine acquisto** consentono di visualizzare elenchi di PO nei vari stati che hanno raggiunto. Offrono inoltre un riepilogo delle azioni che devono essere prese. L'area di lavoro **Preparazione ordini acquisto** si concentra sulla creazione e revisione dell'ordine fornitore, l'elaborazione dell'ordine tramite l'approvazione e la conferma con il fornitore. L'area di lavoro **Ricevimento e follow-up ordine acquisto** è incentrata sulla elaborare le entrate di merci o servizi contro gli ordini fornitore. Include gli elenchi che consentono di analizzare le entrate scadute, o prossime alla consegna da parte del fornitore. Queste aree di lavoro non sono utilizzati per eseguire le attività di ricezione correlate che vengono eseguite nel magazzino. Tali attività vengono eseguite utilizzando pagine nei moduli **Gestione articoli** e **Gestione magazzino**. Elaborazione delle fatture fornitore deve essere eseguita utilizzando l'area di lavoro **Inserimento fatture fornitore** e i pagamenti devono essere eseguiti utilizzando l'area di lavoro **Pagamenti fornitore**.  

I seguenti articoli forniscono una panoramica delle varie fasi che attraversa un ordine fornitore:

-   [Creare gli ordini fornitore](purchase-order-creation.md)
-   [Approvare e confermare gli ordini fornitore](purchase-order-approval-confirmation.md)
-   [Entrata prodotti e ordini fornitore](product-receipt-against-purchase-orders.md)
-   [Panoramica delle fatture fornitore](../../finance/accounts-payable/vendor-invoices-overview.md)

## <a name="types-of-purchase-orders"></a>Tipi di ordini fornitore
Sono disponibili tre tipi di ordini fornitore. Quando si crea un ordine fornitore, è necessario specificare il tipo. È possibile impostare un tipo di ordine predefinito per i nuovi ordini nella pagina **Parametri di approvvigionamento**.

| Tipo di PO        | Descrizione                                                                                                                                                                                                                                                                           |
|----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Giornale di registrazione        | Usare questo tipo per creare un ordine bozza. Questo tipo non ha alcun effetto sulle quantità delle scorte e non genera transazioni articolo. Le righe del giornale di registrazione ordini non vengono incluse nella programmazione generale.                                                                                                       |
| Ordine acquisto | Utilizzare questo tipo per creare PO quando gli ordini vengono confermati con un fornitore e quando gli ordini vengono elaborati tramite entrata e fatturazione prima di effettuare il pagamento al fornitore. Si tratta del tipo di PO più comune.                                                                          |
| Ordine di reso | Utilizzare questo tipo quando vengono rese merci al fornitore. Questo tipo di ordine richiede di specificare il numero di autorizzazione reso (NAR) che il fornitore fornisce. Specificare il numero NAR nella scheda **Generale** dell'ordine fornitore. Le righe dell'ordine devono avere quantità negative. |

## <a name="purchase-order-statuses"></a>Stati dell'ordine fornitore
I PO includono diversi campi di stato che indicano lo stato di avanzamento dell'ordine. Tutti questi campi sono visibili nella visualizzazione **Intestazione** dell'ordine e alcuni di essi sono anche visibili nella griglia panoramica di tutti gli ordini. Il campo **Stato** mostra lo stato delle quantità dell'ordine. Sono disponibili i valori seguenti:

-   **Ordine aperto** – sono stati creati gli ordini e le quantità sono in ordine.
-   **Ricevuto** : alcuni dei quantitativi sono stati ricevuti, ma non sono stati ancora fatturati.
-   **Fatturato** : è stata fatturata l'intera quantità dell'ordine. **Nota:** se un ordine è stato *parzialmente* fatturato, né **Ricevuto** né **Fatturato** è uno stato appropriato. L'ordine, pertanto, avrà ancora lo stato di **Ordine aperto**.
-   **Annullato** – un ordine è stato confermato ma successivamente annullato. Pertanto, questo stato indica che non ci sono più quantità aperte in ordine.

Il campo **Stato documento** consente di esaminare rapidamente lo stato di avanzamento dell'ordine in termini di documenti che sono stati elaborati. Mostra lo stato del documento più recente che è stato completato per l'ordine. Sono disponibili i valori seguenti:

-   **Nessuno** : nessun documento è stato elaborato ancora per l'ordine.
-   **Richiesta informazioni su acquisto** : è stata generata una richiesta di informazioni sull'acquisto e l'ordine è in attesa di feedback dal fornitore.
-   **Ordine fornitore** – la conferma è stata elaborata sull'ordine.
-   **Entrata prodotti** – l'entrata prodotti è stato elaborata sull'ordine.
-   **Fattura** – una fattura è stata contabilizzata con l'ordine.

IL campo **Stato approvazione** viene utilizzato quando un ordine fornitore passa attraverso un processo di revisione o un flusso di lavoro. Sono disponibili i valori seguenti:

-   **Bozza**, **In revisione**, e **Respinto** – questi stati vengono utilizzati solo quando un flusso di lavoro di approvazione viene utilizzato per il PO.
-   **Approvato** – questo stato viene assegnato agli ordini che hanno completato l'approvazione del flusso di lavoro. Gli ordini creati senza utilizzare un flusso di lavoro di approvazione ricevono immediatamente lo stato **Approvato**.
-   **IN revisione esterna** – questo stato viene utilizzato in scenari in cui viene inviata una richiesta di informazioni sull'acquisto al fornitore, in modo che il fornitore possa confermare i termini dell'ordine fornitore. Questo stato viene inoltre utilizzato nel processo che viene avviato per l'azione **Richiesta di conferma**. Per questo processo, il fornitore viene richiesto di confermare i termini dell'ordine fornitore mediante il collegamento al sistema e registrando se conferma o rifiuta l'ordine.
-   **Confermato** – questo stato viene assegnato dopo l'ordine è stato confermato. In genere, questo stato è l'ultimo stato di approvazione che viene assegnato a un ordine.


## <a name="additional-resources"></a>Risorse aggiuntive

[Creare gli ordini fornitore](purchase-order-creation.md)

[Approvare e confermare gli ordini fornitore](purchase-order-approval-confirmation.md)

[Entrata prodotti e ordini fornitore](product-receipt-against-purchase-orders.md)

[Panoramica delle fatture fornitore](../../finance/accounts-payable/vendor-invoices-overview.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]