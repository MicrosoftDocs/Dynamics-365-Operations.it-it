---
title: Panoramica delle fatture fornitore
description: Questo articolo fornisce informazioni generali sulle fatture fornitore.
author: abruer
ms.date: 02/25/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: VendorInvoiceWorkspace, VendInvoiceInfoListPage
audience: Application User
ms.reviewer: twheeloc
ms.custom:
- "13971"
- intro-internal
ms.assetid: 0ec4dbc0-2eeb-423b-8592-4b5d37e559d3
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b88390085d86956c38c0fc167395509d0c54f860
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8894173"
---
# <a name="vendor-invoices-overview"></a>Panoramica delle fatture fornitore

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]


Questo articolo fornisce informazioni generali sulle fatture fornitore. Le fatture fornitore sono obbligatorie per il pagamento di prodotti e servizi. Le fatture fornitore possono rappresentare una fattura per i servizi correnti oppure possono essere basate su ordini fornitore per articoli e servizi specifici.

## <a name="vendor-invoices"></a>Fatture fornitore

Una fattura fornitore da un ordine fornitore è generata quando i prodotti o servizi vengono ricevuti in base a un ordine fornitore che è stato emesso per un fornitore. La fattura fornitore contiene un'intestazione e una o più righe per articoli o servizi. Una fattura fornitore completa il ciclo dall'ordine fornitore all' entrata prodotti alla fattura fornitore.

Sebbene alcune fatture fornitore siano collegate a un ordine fornitore, le fatture fornitore possono anche contenere righe che non corrispondono alle righe ordine fornitore. È anche possibile creare fatture fornitore non associate ad alcun ordine fornitore. Queste fatture fornitore potrebbero rappresentare servizi in corso, come una bolletta. Non è necessario fare riferimento a un ordine fornitore quando si aggiunge un servizio in corso.

Sono disponibili diversi modi di immettere una fattura fornitore:

- Il registro fatture fornitore consente di immettere rapidamente le fatture che non fanno riferimento a un ordine fornitore, in modo da poter accumulare la spesa. Utilizzando il giornale di registrazione approvazioni fatture fornitore, è possibile selezionare le fatture e registrarle al saldo fornitore per stornare gli importi della competenza..
- Il giornale di registrazione fatture fornitore consente di immettere rapidamente le fatture che non fanno riferimento a un ordine fornitore, in un unico passaggio.
- Insieme al pool fatture fornitore, il registro fatture fornitore consente di immettere rapidamente fatture per accumulare la competenza. È possibile aprire successivamente gli ordini fornitore associati per registrare la fattura a fronte del conto spese.
- Le pagine **Fatture fornitore aperte** e **Fatture fornitore in sospeso** consentono di creare fatture fornitore da ordini fornitore confermati.

La discussione seguente fornisce ulteriori informazioni su come utilizzare la pagina **Fatture fornitore aperte** o **Fatture fornitore in sospeso** per creare una fattura fornitore da un ordine fornitore.

## <a name="understanding-invoice-line-quantities"></a>Informazioni sulle quantità righe fattura

Quando si apre una fattura fornitore da un ordine fornitore correlato, il sistema crea righe fattura dall'ordine fornitore. Per impostazione predefinita, il sistema prende le quantità dall'entrata prodotti. Tuttavia, è possibile utilizzare uno dei seguenti comportamenti predefiniti:

- **Quantità in Ricevi ora** Utilizzare questa opzione per le spedizioni parziali. Il valore predefinito nel campo **Quantità** verrà impostato sulla quantità specificata nel campo **Ricevi ora** nell'ordine fornitore.
- **Quantità ordinata** Utilizzare questa opzione per le spedizioni complete. Il valore predefinito nel campo **Quantità** verrà impostato sulla quantità specificata nel campo **Ordinato** nell'ordine fornitore.
- **Quantità registrata** Utilizzare questa opzione se l'articolo richiede la registrazione, come specificato nella pagina **Gruppi di modelli di articoli**. Il valore predefinito nel campo **Quantità** è la quantità fisica di aggiornamento registrata.
- **Quantità entrata prodotti**: utilizzare questa opzione se per l'ordine è già stata ricevuta un'entrata prodotti. Il valore predefinito nel campo **Quantità** deriva dalla quantità totale di entrate prodotti disponibili.
- **Quantità registrata e servizi**: utilizzare questa opzione se le quantità sono state registrate nei giornali di registrazione arrivi per articoli stoccati o articoli non stoccati. In questa opzione sono inoltre inclusi i servizi, indipendentemente dal relativo stato di registrazione.

Se la persona giuridica utilizza l'abbinamento fatture, è possibile visualizzare i risultati degli abbinamenti quantità nella colonna **Abbinamento quantità entrata prodotti**. È anche possibile utilizzare il pulsante **Dettagli corrispondenti** nella scheda **Revisione** del Riquadro azioni per visualizzare i risultati degli abbinamenti quantità.

## <a name="adding-a-line-that-wasnt-on-the-purchase-order"></a>Aggiungere una riga non presente dell'ordine fornitore

È possibile aggiungere una riga non presente nell'ordine fornitore alla fattura fornitore. È necessario selezionare un numero di articolo o una categoria di approvvigionamento. È possibile aggiungere le quantità, i prezzi e gli importi nella riga. La riga verrà inclusa solo nei criteri di abbinamento nei totali fattura.

## <a name="submitting-a-vendor-invoice-for-review"></a>Invio di una fattura fornitore per la revisione

L'organizzazione può utilizzare flussi di lavoro per gestire il processo di revisione per le fatture fornitore. La revisione del flusso di lavoro può essere necessaria per l'intestazione della fattura, per la riga di fattura o per entrambe. I controlli del flusso di lavoro vengono applicati all'intestazione o alla riga, a seconda della posizione dello stato attivo quando si seleziona il controllo. Anziché il pulsante **Registra**, è possibile utilizzare un pulsante **Invia** per inviare la fattura fornitore tramite il processo di revisione.

### <a name="preventing-invoice-from-being-submitted-to-workflow"></a>Impedire che la fattura venga inviata al flusso di lavoro 

Di seguito sono riportati diversi modi per impedire che una fattura venga inviata a un flusso di lavoro.

- **Il totale della fattura e il totale registrato non sono uguali.** La persona che ha inviato la fattura riceverà un avviso che i totali non sono uguali. L'avviso offre l'opportunità di correggere i saldi prima di inviare nuovamente la fattura al flusso di lavoro. Questa funzione è disponibile se il parametro **Proibisci l'invio al flusso di lavoro quando il totale della fattura e il totale della fattura registrata non sono uguali** nella pagina **Gestione funzionalità** è attivato. 
- **La fattura contiene addebiti non allocati.** La persona che ha inviato la fattura riceverà un avviso che la fattura contiene addebiti non allocati in modo da poter correggere la fattura prima di inviarla nuovamente al flusso di lavoro. Questa funzione è disponibile se il parametro **Proibisci l'invio al flusso di lavoro quando sono presenti addebiti non allocati in una fattura fornitore** nella pagina **Gestione funzionalità** è attivato.
- **La fattura contiene lo stesso numero di fattura di un'altra fattura registrata.** La persona che ha inviato la fattura riceverà un messaggio che indica che è stata trovata una fattura con un numero duplicato. Il numero duplicato può essere corretto prima di inviare nuovamente la fattura al flusso di lavoro. Questo avviso viene visualizzato quando il parametro **Verifica il numero di fattura utilizzato** in Contabilità fornitori è impostato su **Rifiuta duplicati**. Questa funzione è disponibile se il parametro **Proibisci l'invio al flusso di lavoro quando il numero di fattura esiste già in una fattura registrata e il sistema non è impostato per accettare numeri di fattura duplicati** nella pagina **Gestione funzionalità** è attivato.
- **La fattura contiene una riga in cui la quantità della fattura è inferiore alla quantità di entrata prodotti abbinata.** La persona che invia la fattura o tenta di effettuare la registrazione riceverà un messaggio indicante che le quantità non sono uguali. Questo messaggi offre l'opportunità di correggere i valori prima di inviare nuovamente la fattura al flusso di lavoro. Questa funzione è disponibile se il parametro **Blocca la registrazione e l'invio di fatture fornitore al flusso di lavoro** nella pagina **Gestione funzionalità** è attivata e il parametro **Blocca la pubblicazione e l'invio al flusso di lavoro** nella pagina **Parametri di contabilità fornitori** è attivata.

## <a name="matching-vendor-invoices-to-product-receipts"></a>Abbinamento delle fatture fornitore con le entrate prodotti

È possibile immettere e salvare le informazioni relative alle fatture fornitore e abbinare le righe di fattura alle righe dell'entrata prodotti. È inoltre possibile abbinare quantità parziali per una riga

È possibile creare una fattura fornitore basata sulle voci entrata prodotti ricevute fino alla data corrente, anche se non sono stati ancora ricevuti tutti gli articoli di un ordine fornitore specifico. È possibile ad esempio utilizzare questa opzione se un fornitore emette una fattura al mese per coprire tutte le consegne spedite nel mese in questione. Ogni entrata prodotti corrisponde a una consegna completa o parziale degli articoli inclusi nell'ordine fornitore.

Quando una fattura è nel flusso di lavoro, l'approvatore può aggiornare le quantità della fattura in modo che corrispondano al valore nel campo **Quantità dell'entrata prodotti da associare**. Per fare ciò, seleziona la funzionalità **Aggiorna le quantità delle fatture in modo che corrispondano alle quantità dell'entrata prodotti nel flusso di lavoro** nell'area di lavoro **Gestione funzionalità** e seleziona **Abilita**. Se un approvatore nel processo del flusso di lavoro ha rimosso tutte le corrispondenze da tutte le entrate prodotti dalla riga della fattura, la riga della fattura verrà eliminata. Quando questa funzione non è abilitata, le quantità delle fatture non vengono aggiornate per le fatture nel flusso di lavoro.

Quando viene registrata la fattura, la quantità **Rimanente fattura** relativa a ogni articolo viene aggiornata con il totale delle quantità ricevute, tratto dalle entrate prodotti selezionate. Se entrambe le quantità **Rimanente fattura** e **Rimanente consegna** per tutti gli articoli dell'ordine fornitore sono uguali a 0 (zero), lo stato dell'ordine fornitore passa a **Fatturato**. Se la quantità **Rimanente fattura** è diversa da 0 (zero), lo stato dell'ordine fornitore non viene modificato e per tale ordine è possibile immettere ulteriori fatture.

In questa opzione si presuppone che per l'ordine fornitore sia stata registrata almeno un'entrata prodotti. La fattura fornitore si basa sulle entrate prodotti e riflette le quantità in esse contenute. Le informazioni finanziarie per la fattura si basano sulle informazioni immesse al momento della registrazione della fattura stessa.

Per ulteriori informazioni, vedere [Registrare la fattura fornitore e associarla alla quantità ricevuta](../accounts-payable/tasks/record-vendor-invoice-match-against-received-quantity.md).

## <a name="configure-an-automated-task-for-vendor-invoice-workflow-to-post-the-vendor-invoice-using-a-batch-job"></a>Configurare un'attività automatizzata per il flusso di lavoro della fattura fornitore per registrare la fattura fornitore utilizzando un processo batch

È possibile aggiungere un'attività di registrazione automatica al flusso di lavoro della fattura fornitore in modo che le fatture vengano elaborate in un batch. La registrazione delle fatture in un batch consente al processo di flusso di lavoro di continuare senza dover attendere il completamento della registrazione, migliorando le prestazioni complessive di tutte le attività inviate al flusso di lavoro.

Per registrare una fattura fornitore in un batch, nella pagina **Gestione funzionalità**, attivare il parametro **Registrazione batch fatture fornitore**. I flussi di lavoro della fattura fornitore vengono configurati accedendo a **Contabilità fornitor i> Impostazione > Flussi di lavoro contabilità fornitori**.

È possibile vedere l'attività **Registra la fattura fornitore utilizzando un batch** nell'editor del flusso di lavoro, indipendentemente se il parametro della funzione, **Registrazione batch fatture fornitore**, è abilitato. Quando il parametro della funzione non è abilitato, una fattura che contiene **Registra la fattura fornitore tramite un'attività batch** non verrà elaborata nel flusso di lavoro fino a quando il parametro non viene abilitato. L'attività **Registra la fattura fornitore utilizzando un batch** non deve essere utilizzata nello stesso flusso di lavoro dell'attività automatizzata **Registra fatture fornitore**. Inoltre, l'attività **Registra la fattura fornitore utilizzando un batch** deve essere l'ultimo elemento nella configurazione del flusso di lavoro.

È possibile specificare il numero di fatture da includere nel batch e il numero di ore di attesa prima di riprogrammare un batch, andando a **Contabilità fornitori > Impostazione > Parametri contabilità fornitori > Fattura > Flusso di lavoro fattura**. 

## <a name="working-with-multiple-invoices"></a>Utilizzo con più fatture

È possibile utilizzare più fatture e registrarle tutte contemporaneamente. Se è necessario creare più fatture, utilizzare la pagina **Fatture fornitore in sospeso**. Se è necessario registrare e stampare più fatture fornitore, utilizzare il **giornale di approvazione fatture**. Se si utilizza il **giornale di approvazione fatture** è necessario che sia registrata almeno un'entrata prodotti per l'ordine fornitore e che sia registrata una fattura per l'ordine fornitore in un registro fatture. Le informazioni finanziarie relative alla fattura derivano dalla fattura inserita nel registro.

## <a name="recovering-vendor-invoices-that-are-being-used"></a>Ripristinare fatture fornitore utilizzate

Una fattura fornitore in uso non può essere modificata da un altro utente. Tuttavia, lo stato di una fattura può talvolta indicare che la fattura è in uso, anche se non è attivamente modificata. Ad esempio, l'applicazione potrebbe non rispondere più durante la modifica della fattura o un utente potrebbe aver lasciato inavvertitamente la fattura aperta nell'applicazione.

È possibile utilizzare la pagina **Ripristina fatture fornitore** per ripristinare o emettere fatture fornitore utilizzate per più di quattro ore, in modo che possano essere modificate. È possibile aprire questa pagina da **Attività periodica** o da un riquadro nell'area di lavoro **Inserimento fatture fornitore**. Dopo il ripristino di una fattura, questa sarà disponibile per la modifica nella pagina **Fattura fornitore**.

È possibile accedere alla pagina **Ripristina fatture fornitore** solo se si dispone dei diritti e dei privilegi di sicurezza **Ripristina fatture fornitore utilizzate**. Inoltre, il parametro **Consenti ripristino fatture fornitore** nella pagina **Parametri contabilità fornitori** deve essere abilitato.

## <a name="resetting-the-workflow-status-for-vendor-invoices-from-unrecoverable-to-draft"></a>Reimpostare lo stato flusso di lavoro di fatture fornitore da Irreversibile a Bozza

Un'istanza del flusso di lavoro interrotta a causa di un errore irreversibile avrà lo stato **Irriversibile**. Quando lo stato di un flusso di lavoro di fatture fornitore è **Irreversibile**, è possibile reimpostarlo su **Bozza** selezionando **Richiama**. È quindi possibile modificare la fattura fornitore. Questa funzionalità è disponibile se il parametro **Reimpostare lo stato flusso di lavoro di fatture fornitore da Irreversibile a Bozza** nella pagina **Gestione funzionalità** è attivato.

È possibile utilizzare la pagina **Storico flusso di lavoro** per reimpostare lo stato flusso di lavoro su **Bozza**. È possibile visualizzare questa pagina da **Fattura fornitore** o dal percorso **Comune > Richieste di informazioni > Flusso di lavoro**. Per reimpostare lo stato del flusso di lavoro su **Bozza**, selezionare **Richiama**. È inoltre possibile reimpostare lo stato del flusso di lavoro su Bozza selezionando l'azione **Richiama** nella pagina **Fattura fornitore** o **Fatture fornitore in sospeso**. Dopo la reimpostazione dello stato flusso di lavoro su **Bozza**, diventa disponibile per modificare la pagina **Fattura fornitore**.

## <a name="viewing-the-invoice-total-on-the-pending-vendor-invoices-page"></a>Visualizzazione del totale della fattura nella pagina Fatture fornitore in sospeso

È possibile visualizzare il totale della fattura nella pagina **Fatture fornitore in sospeso** abilitando il parametro **Visualizza totale fatture su elenco fatture fornitore in sospeso** nella pagina **Parametri di contabilità fornitori**. 

## <a name="vendor-open-transactions-report"></a>Report di transazioni aperte fornitore

Il report **Transazioni fornitore aperte** fornisce informazioni dettagliate sulle transazioni aperte per ciascun fornitore alla data specificata. Questo report viene spesso utilizzato durante la procedura di controllo per verificare i saldi tra le transazioni del libro fornitore e le transazioni del conto CoGe.

Per ogni transazione, il report include i seguenti dettagli:

- Numero fattura
- Data transazione
- Numero del giustificativo
- Importo della transazione nella valuta della transazione e nella valuta contabile
- Saldo in avere della transazione nella valuta della transazione e nella valuta contabile
- Saldo in dare della transazione nella valuta della transazione e nella valuta contabile
- Subtotale nella valuta di contabilizzazione
- Data di scadenza pagamento

### <a name="filter-the-data-on-the-report"></a>Filtrare i dati nel report

Quando generi il report **Transazioni fornitore aperte**, sono disponibili i seguenti parametri predefiniti. È possibile utilizzarli per filtrare i dati che verranno inclusi nel report.

- **Escludi liquidazione futura** – Selezionare questa casella di controllo per escludere le transazioni liquidate dopo la data immessa nel campo **Transazioni aperte per**.
- **Transazioni aperte per** – Immettere una data per includere le transazioni aperte a partire da tale data. Se non inserisci una data, questo campo è impostato sulla data massima. (La data massima è l'ultima data accettata dal sistema, 31 dicembre 2154.) Per impostazione predefinita, alla successiva esecuzione del report, in questo campo verrà impostata l'ultima data inserita.

Puoi usare i filtri sotto il campo **Record da includere** per limitare ulteriormente i dati della transazione inclusi nel report.

## <a name="additional-resources"></a>Risorse aggiuntive

- [Imposta criteri fatture fornitore](../accounts-receivable/tasks/set-up-vendor-invoice-policies.md)
- [Dati principali della fattura in sistema di contabilità fornitori utilizzando la fattura fornitore](tasks/key-invoice-data-ap-system-vendor-invoice.md)
- [Inserire dati fattura nella contabilità fornitori tramite un giornale di approvazione](tasks/key-invoice-data-into-ap-system-approval-journal.md)
- [Inserire dati fattura nel sistema di contabilità fornitore tramite un pool di fatture](tasks/key-invoice-data-into-ap-system-invoice-pool.md)
- [Registrare una fattura fornitore nel giornale di registrazione fatture](tasks/record-vendor-invoice-invoice-journal.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
