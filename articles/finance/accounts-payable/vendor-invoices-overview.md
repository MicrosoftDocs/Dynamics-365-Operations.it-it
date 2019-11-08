---
title: Panoramica delle fatture fornitore
description: Questo argomento fornisce informazioni generali sulle fatture fornitore. Le fatture fornitore sono obbligatorie per il pagamento dei prodotti e dei servizi ricevuti. Le fatture fornitore possono rappresentare una fattura per i servizi correnti oppure possono essere basate su ordini fornitore per articoli e servizi specifici.
author: abruer
manager: AnnBe
ms.date: 07/17/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendorInvoiceWorkspace, VendInvoiceInfoListPage
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 13971
ms.assetid: 0ec4dbc0-2eeb-423b-8592-4b5d37e559d3
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 616d3f5560d18c7fdd8a092c3fbca0fde44be069
ms.sourcegitcommit: d37fb09101c30858bcb975931b3d8f947d72017b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/10/2019
ms.locfileid: "2570427"
---
# <a name="vendor-invoices-overview"></a>Panoramica delle fatture fornitore

[!include [banner](../includes/banner.md)]

Questo argomento fornisce informazioni generali sulle fatture fornitore. Le fatture fornitore sono obbligatorie per il pagamento dei prodotti e dei servizi ricevuti. Le fatture fornitore possono rappresentare una fattura per i servizi correnti oppure possono essere basate su ordini fornitore per articoli e servizi specifici.

## <a name="vendor-invoices"></a>Fatture fornitore

Una fattura fornitore da un ordine fornitore è una fattura generata quando i prodotti o servizi vengono ricevuti in base a un ordine fornitore che è stato emesso per un fornitore. La fattura fornitore contiene un'intestazione e una o più righe per articoli o servizi. Una fattura fornitore completa il ciclo dall'ordine fornitore all' entrata prodotti alla fattura fornitore.

Sebbene alcune fatture fornitore siano collegate a un ordine fornitore, le fatture fornitore possono anche contenere righe che non corrispondono alle righe ordine fornitore. È anche possibile creare fatture fornitore non associate ad alcun ordine fornitore. Queste fatture fornitore potrebbero rappresentare i servizi in corso, ad esempio una fattura di utilità, e non è necessario fare riferimento a un ordine fornitore quando si aggiungono.

Sono disponibili diversi modi di immettere una fattura fornitore:

- Il registro fatture fornitore consente di immettere rapidamente le fatture che non fanno riferimento a un ordine fornitore, in modo da poter accumulare la spesa. Utilizzando il giornale di registrazione approvazioni fatture fornitore, è possibile selezionare le fatture e registrarle al saldo fornitore per stornare gli importi della competenza..
- Il giornale di registrazione fatture fornitore consente di immettere rapidamente le fatture che non fanno riferimento a un ordine fornitore, in un unico passaggio.
- Insieme al pool fatture fornitore, il registro fatture fornitore consente di immettere rapidamente fatture per accumulare la competenza. È possibile aprire successivamente gli ordini fornitore associati per registrare la fattura a fronte del conto spese.
- Le pagine **Fatture fornitore aperte** e **Fatture fornitore in sospeso** consentono di creare fatture fornitore da ordini fornitore confermati.

La discussione seguente fornisce ulteriori informazioni su come utilizzare la pagina **Fatture fornitore aperte** o **Fatture fornitore in sospeso** per creare una fattura fornitore da un ordine fornitore.

## <a name="understanding-invoice-line-quantities"></a>Informazioni sulle quantità righe fattura

Quando si apre una fattura fornitore da un ordine fornitore correlato, righe fattura vengono create dall'ordine fornitore. Per impostazione predefinita, le quantità derivano dalla quantità di entrata prodotti. Tuttavia, è possibile utilizzare uno dei seguenti comportamenti predefiniti:

- **Quantità in Ricevi ora** Utilizzare questa opzione per le spedizioni parziali. Il valore predefinito del campo **Quantità** deriva dalla quantità specificata nel campo **Ricevi ora** nell'ordine fornitore.
- **Quantità ordinata** Utilizzare questa opzione per le spedizioni complete. Il valore predefinito del campo **Quantità** deriva dalla quantità specificata nel campo **Ordinata** nell'ordine fornitore.
- **Quantità registrata** Utilizzare questa opzione se l'articolo richiede la registrazione, come specificato nella pagina **Gruppi di modelli di articoli**. Il valore predefinito nel campo **Quantità** è la quantità fisica di aggiornamento registrata.
- **Quantità entrata prodotti**: utilizzare questa opzione se per l'ordine è già stata ricevuta un'entrata prodotti. Il valore predefinito nel campo **Quantità** deriva dalla quantità totale di entrate prodotti disponibili.
- **Quantità registrata e servizi**: utilizzare questa opzione se le quantità sono state registrate nei giornali di registrazione arrivi per articoli stoccati o articoli non stoccati. In questa opzione sono inoltre inclusi i servizi, indipendentemente dal relativo stato di registrazione.

Se la persona giuridica utilizza l'abbinamento fatture, è possibile visualizzare i risultati degli abbinamenti quantità nella colonna **Abbinamento quantità entrata prodotti**. È anche possibile utilizzare il pulsante **Dettagli corrispondenti** nella scheda **Revisione** del Riquadro azioni per visualizzare i risultati degli abbinamenti quantità.

## <a name="adding-a-line-that-wasnt-on-the-purchase-order"></a>Aggiungere una riga non presente dell'ordine fornitore

È possibile aggiungere una riga non presente nell'ordine fornitore alla fattura fornitore. È necessario selezionare un numero di articolo o una categoria di approvvigionamento. È possibile aggiungere le quantità, i prezzi e gli importi nella riga. La riga verrà inclusa solo nei criteri di abbinamento nei totali fattura.

## <a name="submitting-a-vendor-invoice-for-review"></a>Invio di una fattura fornitore per la revisione

L'organizzazione può utilizzare flussi di lavoro per gestire il processo di revisione per le fatture fornitore. La revisione del flusso di lavoro può essere necessaria per l'intestazione della fattura, per la riga di fattura o per entrambe. I controlli del flusso di lavoro vengono applicati all'intestazione o alla riga, a seconda della posizione dello stato attivo quando si seleziona il controllo. Anziché il pulsante **Registra**, verrà visualizzato il pulsante **Invia** che può essere utilizzato per inviare la fattura fornitore tramite il processo di revisione.

## <a name="matching-vendor-invoices-to-product-receipts"></a>Abbinamento delle fatture fornitore con le entrate prodotti

È possibile immettere e salvare le informazioni relative alle fatture fornitore e abbinare le righe di fattura alle righe dell'entrata prodotti. È inoltre possibile abbinare quantità parziali per una riga

È possibile creare una fattura fornitore basata sulle voci entrata prodotti ricevute fino alla data corrente, anche se non sono stati ancora ricevuti tutti gli articoli di un ordine fornitore specifico. È possibile ad esempio utilizzare questa opzione se un fornitore emette una fattura al mese per coprire tutte le consegne spedite nel mese in questione. Ogni entrata prodotti corrisponde a una consegna completa o parziale degli articoli inclusi nell'ordine fornitore.

Quando viene registrata la fattura, la quantità **Rimanente fattura** relativa a ogni articolo viene aggiornata con il totale delle quantità ricevute, tratto dalle entrate prodotti selezionate. Se entrambe le quantità **Rimanente fattura** e **Rimanente consegna** per tutti gli articoli dell'ordine fornitore sono uguali a 0 (zero), lo stato dell'ordine fornitore passa a **Fatturato**. Se la quantità **Rimanente fattura** è diversa da 0 (zero), lo stato dell'ordine fornitore non viene modificato e per tale ordine è possibile immettere ulteriori fatture.

In questa opzione si presuppone che per l'ordine fornitore sia stata registrata almeno un'entrata prodotti. La fattura fornitore si basa sulle entrate prodotti e riflette le quantità in esse contenute. Le informazioni finanziarie per la fattura si basano sulle informazioni immesse al momento della registrazione della fattura stessa.

Per ulteriori informazioni, vedere [Registrare la fattura fornitore e associarla alla quantità ricevuta](../accounts-receivable/tasks/record-vendor-invoice-match-against-received-quantity.md).

## <a name="working-with-multiple-invoices"></a>Utilizzo con più fatture

È possibile utilizzare più fatture e registrarle tutte contemporaneamente. Se è necessario creare più fatture, utilizzare la pagina **Fatture fornitore in sospeso**. Se è necessario registrare e stampare più fatture fornitore, utilizzare il giornale di approvazione fatture. Se si utilizza il giornale di approvazione fatture è necessario che sia registrata almeno un'entrata prodotti per l'ordine fornitore e che sia registrata una fattura per l'ordine fornitore in un registro fatture. Le informazioni finanziarie relative alla fattura derivano dalla fattura inserita nel registro.

## <a name="recovering-vendor-invoices-that-are-being-used"></a>Ripristinare fatture fornitore utilizzate

Una fattura fornitore in uso non può essere modificata da un altro utente. Tuttavia, lo stato di una fattura può talvolta indicare che la fattura è in uso, anche se non è attivamente modificata. Ad esempio, l'applicazione potrebbe non rispondere più durante la modifica della fattura o un utente potrebbe aver lasciato inavvertitamente la fattura aperta nell'applicazione.

È possibile utilizzare la pagina **Ripristina fatture fornitore** per ripristinare o emettere fatture fornitore utilizzate per più di quattro ore, in modo che possano essere modificate. È possibile aprire questa pagina da **Attività periodica** o da un riquadro nell'area di lavoro **Inserimento fatture fornitore**. Dopo il ripristino di una fattura, questa sarà disponibile per la modifica nella pagina **Fattura fornitore**.

È possibile accedere alla pagina **Ripristina fatture fornitore** solo se si dispone dei diritti e dei privilegi di sicurezza **Ripristina fatture fornitore utilizzate**. Inoltre, il parametro **Consenti ripristino fatture fornitore** nella pagina **Parametri contabilità fornitori** deve essere abilitato.

## <a name="resetting-the-workflow-status-for-vendor-invoices-from-unrecoverable-to-draft"></a>Reimpostare lo stato flusso di lavoro di fatture fornitore da Irreversibile a Bozza

Un'istanza del flusso di lavoro interrotta a causa di un errore irreversibile avrà lo stato **Irriversibile**. Quando lo stato di un flusso di lavoro di fatture fornitore è **Irreversibile**, è possibile reimpostarlo su **Bozza** selezionando **Richiama**. È quindi possibile modificare la fattura fornitore. Questa funzionalità è disponibile se il parametro **Reimposta stato Bozza per flusso di lavoro fatture fornitore** nella pagina **Gestione funzionalità** è abilitato.

È possibile utilizzare la pagina **Storico flusso di lavoro** per reimpostare lo stato flusso di lavoro su **Bozza**. È possibile visualizzare questa pagina da **Fattura fornitore** o dal percorso **Comune > Richieste di informazioni > Flusso di lavoro**. Per reimpostare lo stato del flusso di lavoro su **Bozza**, selezionare **Richiama**. È inoltre possibile reimpostare lo stato del flusso di lavoro su Bozza selezionando l'azione **Richiama** nella pagina **Fattura fornitore** o **Fatture fornitore in sospeso**. Dopo la reimpostazione dello stato flusso di lavoro su **Bozza**, diventa disponibile per modificare la pagina **Fattura fornitore**.



## <a name="additional-resources"></a>Risorse aggiuntive

- [Impostare criteri di fatture fornitore](../accounts-receivable/tasks/set-up-vendor-invoice-policies.md)
- [Inserire dati fattura nella contabilità fornitori tramite una fattura fornitore](tasks/key-invoice-data-ap-system-vendor-invoice.md)
- [Inserire dati fattura nella contabilità fornitori tramite un giornale di approvazione](tasks/key-invoice-data-into-ap-system-approval-journal.md)
- [Inserire dati fattura nel sistema di contabilità fornitore tramite un pool di fatture](tasks/key-invoice-data-into-ap-system-invoice-pool.md)
- [Registrare una fattura fornitore nel giornale di registrazione fatture](tasks/record-vendor-invoice-invoice-journal.md)
