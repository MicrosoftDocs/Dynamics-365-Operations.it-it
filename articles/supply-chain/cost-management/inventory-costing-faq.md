---
title: Domande frequenti sulla determinazione costi inventario
description: Questo articolo risponde ad alcune domande frequenti sulla determinazione costi inventario in Microsoft Dynamics 365 Supply Chain Management.
author: rachel-profitt
ms.date: 05/03/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: raprofit
ms.search.validFrom: 2022-05-03
ms.dyn365.ops.version: 10.0.27
ms.openlocfilehash: 467839b1d0ca6788a92ae60d46686374d0a58046
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8850846"
---
# <a name="inventory-costing-faq"></a>Domande frequenti sulla determinazione costi inventario

[!include [banner](../includes/banner.md)]

Questo articolo risponde ad alcune domande frequenti sulla determinazione costi inventario in Microsoft Dynamics 365 Supply Chain Management.

## <a name="inventory-close-adjustments-and-recalculation"></a>Chiusura, rettifica e ricalcolo inventario

### <a name="is-the-inventory-close-required"></a>È richiesta la chiusura dell'inventario?

Se prevedi di utilizzare la funzione di archiviazione dell'inventario, è necessaria la chiusura dell'inventario. Se non prevedi di utilizzare la funzione di archiviazione dell'inventario, ti consigliamo vivamente di eseguire comunque la chiusura dell'inventario, indipendentemente dai modelli di determinazione costi utilizzati.

### <a name="how-often-should-the-inventory-close-be-run"></a>Con quale frequenza deve essere eseguita la chiusura dell'inventario?

La chiusura dell'inventario deve essere eseguita almeno una volta per periodo contabile. Ad esempio, se la contabilità generale è impostata su un calendario fiscale basato su un mese di calendario, dovresti eseguire la chiusura dell'inventario una volta al mese.

### <a name="is-the-inventory-recalculation-required"></a>È richiesto il ricalcolo dell'inventario?

No, il ricalcolo dell'inventario non è richiesto. Se utilizzi un modello di determinazione dei costi periodico come FIFO (first in, first out), LIFO (last in, first out) o media ponderata, dovresti considerare attentamente se eseguire il ricalcolo dell'inventario. Può fornire una determinazione costi più accurata nei modelli euristici che hai selezionato.

### <a name="how-often-should-the-inventory-recalculation-be-run"></a>Con quale frequenza deve essere eseguito il ricalcolo dell'inventario?

Se hai intenzione di eseguire il ricalcolo dell'inventario, ti consigliamo di prendere in considerazione l'esecuzione quotidiana come processo batch. Se la tua organizzazione non richiede report frequenti sui valori di inventario per i modelli di determinazione dei costi periodici, puoi considerare di eseguire il calcolo dell'inventario con minore frequenza.

### <a name="when-should-i-use-the-on-hand-inventory-adjustment-on-the-closing-and-adjustments-page"></a>Quando dovrei utilizzare la rettifica dell'inventario disponibile nella pagina Chiusura e rettifiche?

La rettifica dell'inventario disponibile può essere eseguita solo dopo il completamento di una chiusura dell'inventario. In genere viene eseguita per la data successiva all'ultima chiusura. La rettifica dell'inventario disponibile può rettificare solo le scorte ancora disponibili alla data in cui si esegue la rettifica.

### <a name="when-should-i-use-the-inventory-transaction-adjustment-on-the-closing-and-adjustments-page"></a>Quando dovrei utilizzare la rettifica delle transazioni di inventario pagina Chiusura e rettifiche?

È necessario utilizzare la rettifica della transazione di inventario prima di eseguire una chiusura dell'inventario. In genere viene utilizzata per correggere una ricevuta errata. Non è possibile registrare la rettifica della transazione di inventario dopo che è stata eseguita una chiusura di inventario e la transazione è stata liquidata.

### <a name="are-purchase-order-returns-treated-like-other-issues-during-the-inventory-close"></a>I resi degli ordini fornitore vengono trattati come altre uscite durante la chiusura dell'inventario?

Sì. Una ricevuta dell'ordine fornitore è un'uscita che viene liquidata per una ricevuta nel modello euristico selezionato per l'articolo. Se usi un modello di determinazione dei costi periodico, è possibile utilizzare il contrassegno per ignorare il costo euristico.

### <a name="what-happens-to-sales-order-returns-during-the-inventory-close"></a>Cosa succede ai resi degli ordini cliente durante la chiusura dell'inventario?

Quando si esegue la chiusura dell'inventario, un reso di un ordine cliente viene considerato come una ricevuta nell'inventario. Le uscite vengono liquidate rispetto all'inventario, in base al modello euristico selezionato per l'articolo.

### <a name="what-cost-price-is-used-on-a-sales-order-return"></a>Quale prezzo di costo viene utilizzato per un reso di un ordine cliente?

Quando crei un reso correlato a un ordine cliente, il valore del campo **Prezzo unitario** viene copiato dall'ordine cliente originale e il campo **Prezzo di ritorno** sul reso è impostato sul prezzo di costo rettificato dalla transazione di inventario originale per la riga dell'ordine cliente che si sta restituendo. Se l'opzione **Valore aperto** per la relativa transazione di inventario è impostata su *sì*, la chiusura dell'inventario può causare aggiornamenti al costo di uscita dell'ordine cliente originale. Il campo **Prezzo di costo reso** non è aggiornato in questo scenario. Tuttavia, quando si registra un documento di trasporto dell'ordine di reso, il sistema controlla il prezzo di costo e utilizza il costo aggiornato nella transazione di inventario di reso.

Per un reso di un articolo di costo standard correlato a un ordine cliente, il sistema utilizzerà il costo standard dal momento dell'ordine cliente originale, anche se per l'articolo è attivo un nuovo costo standard.

Quando crei un reso che non è correlato a un ordine cliente, il campo **Prezzo di costo resto** è impostato sul prezzo dell'articolo attivo che hai per l'articolo nel sito per cui stai creando l'ordine di reso. Se non hai un prezzo di costo attivo in una versione di determinazione dei costi per l'articolo, il valore sarà 0 (zero). Se lasci il valore su 0 (zero), riceverai un avviso che indica che l'ID del lotto di reso o il prezzo del costo di reso non sono specificati.

### <a name="what-is-the-expected-performance-of-the-inventory-close"></a>Quali sono le prestazioni previste per la chiusura dell'inventario?

Molti fattori possono influenzare le prestazioni della chiusura dell'inventario. Questi fattori includono il numero totale di articoli, il numero totale di transazioni nel periodo, i modelli di inventario utilizzati e il numero di helper batch configurati nei parametri di gestione dell'inventario e del magazzino. Puoi aspettarti che la chiusura possa richiedere da pochi minuti a diverse ore. Non ci sono indicazioni specifiche sulla quantità di tempo che la chiusura dovrebbe impiegare per l'esecuzione. È necessario definire i requisiti aziendali non funzionali per le prestazioni della chiusura dell'inventario e collaborare strettamente con il partner per definire la pianificazione per l'esecuzione del processo di chiusura dell'inventario. Se si verificano prestazioni inaspettatamente basse del processo di chiusura dell'inventario, è necessario aprire un ticket di supporto.

## <a name="costing-sheet-and-indirect-costs"></a>Scheda di determinazione costi e costi indiretti

### <a name="which-costing-models-support-the-costing-sheet"></a>Quali modelli di determinazione costi supportano il foglio di determinazione costi?

Sebbene il foglio di determinazione costi sia generalmente utilizzato nelle organizzazioni che utilizzano la determinazione dei costi standard, è possibile utilizzarlo con qualsiasi modello di determinazione dei costi disponibile in Supply Chain Management.

### <a name="can-i-have-multiple-costing-sheets-for-various-parts-of-my-organization"></a>Posso avere più schede di determinazione costi per varie parti della mia organizzazione?

N. Puoi avere un solo foglio di determinazione costi per persona giuridica.

### <a name="can-i-have-different-costing-sheets-for-each-site"></a>Posso avere schede di determinazione costi diverse per ogni sito?

No, non puoi avere un foglio di determinazione costi diverso per ogni sito. Puoi creare un solo foglio di determinazione costi per ogni persona giuridica. Tuttavia, è possibile configurare nodi totali, gruppi di costi o nodi di costi indiretti per ogni sito. Questa configurazione è un processo manuale ed è necessario mantenere la gerarchia e le assegnazioni degli articoli nel foglio di determinazione costi quando si verificano modifiche organizzative oppure operative. Se un singolo articolo viene prodotto o acquistato in più di un sito, non esiste alcun meccanismo che consenta di trattare l'articolo in modo diverso sul foglio di determinazione costi per ciascun sito. Inoltre, tieni presente che tutti i codici di costo indiretto hanno una tariffa o un supplemento definito nella versione di determinazione dei costi. I costi che definisci sono sempre specifici del sito.

### <a name="can-i-deactivate-and-activate-versions-of-the-costing-sheet"></a>Posso disattivare e attivare le versioni del foglio di determinazione costi?

Sebbene non venga conservata una cronologia dettagliata delle versioni per il foglio di determinazione costi, è possibile apportare modifiche al foglio di determinazione costi e quindi, quando sei pronto, salvarlo e convalidarlo. Non esiste alcun meccanismo che ti consenta di tornare a una versione precedente del foglio di determinazione costi o di visualizzare le modifiche apportate al foglio di determinazione costi. Se inizi le modifiche e non desideri che abbiano effetto, puoi chiudere la pagina senza salvare e convalidare le modifiche. Ti verrà chiesto di annullare le modifiche.

### <a name="can-i-create-indirect-costs-for-each-item"></a>Posso creare costi indiretti per ogni articolo?

Sul tuo foglio di determinazione costi, puoi creare codici di costo indiretto in cui il campo **Tipo di nodo** è impostato su *Supplemento*, *Tariffa*, o *Basato sull'unità di output*. È quindi possibile definire la tariffa o il supplemento in modo che sia specifico per un numero di articolo. Sulla Scheda dettaglio **Tariffa** o **Supplemento** aggiungi una riga alla griglia. Imposta il campo **Valido per** su *Tabella* e il campo **Relazione** sul numero di articolo specifico.

### <a name="can-i-create-an-indirect-cost-that-isnt-related-to-a-specific-item"></a>Posso creare un costo indiretto non correlato a un articolo specifico?

Sì. È possibile creare un codice di costo indiretto in cui il campo **Tipo di nodo** è impostato su *Basato sull'unità di output*. È quindi possibile impostare il campo **Sottotipo** su *Quantità*, *Peso*, o *Volume* per specificare la quantità, il peso o il volume dell'articolo che stai producendo. La tariffa che specifichi sulla Scheda dettaglio **Tariffa** verrà applicata al sottotipo selezionato. Ad esempio, se imposti il campo **Sottotipo** su *Quantità* e il campo **Tariffa** su *1,00 USD*, crei un ordine di produzione o batch per una quantità di 10. In questo caso, il costo indiretto che verrà aggiunto al prodotto finito è 10,00 USD.

### <a name="can-i-use-the-costing-sheet-to-split-my-production-costs-by-hours-and-materials"></a>Posso utilizzare il foglio di determinazione costi per dividere i miei costi di produzione per ore e materiali?

Sì. Puoi creare i nodi **Totale** sul foglio di determinazione costi per separare i costi in base a qualsiasi raggruppamento scelto. Ad esempio, puoi crearne un nodo **Totale** denominato *Ore* e un altro che si chiama *Materiali*. Sotto il nodo **Ore** aggiungi ogni gruppo di codice correlato alle tue ore. Sotto il nodo **Materiali** aggiungi ogni gruppo di costi correlato ai tuoi materiali.

## <a name="dimension-groups"></a>Gruppi di dimensioni

### <a name="can-i-manage-cost-at-the-batch-or-serial-number-level"></a>Posso gestire i costi a livello di batch o numero di serie?

Sì, se stai utilizzando un modello di determinazione dei costi periodico come FIFO, LIFO, data LIFO, media ponderata o data media ponderata, puoi abilitare l'opzione **Inventario finanziario** per la dimensione **Batch** o **Numero di serie** nel gruppo di dimensioni di tracciabilità per tenere traccia dei costi a un livello dettagliato.

### <a name="can-i-manage-costs-at-the-location-level"></a>Posso gestire i costi a livello di ubicazione?

No, non puoi abilitare l'opzione **Inventario finanziario** per la dimensione **Ubicazione** nel gruppo di dimensioni di immagazzinamento. Se la tua organizzazione deve tenere traccia dei costi a un livello più dettagliato, valuta se puoi creare magazzini virtuali, quindi seleziona l'opzione **Inventario finanziario** per la dimensione **Magazzino** nel tuo gruppo di dimensioni di immagazzinamento.

### <a name="should-i-enable-the-use-warehouse-management-processes-option-for-the-storage-dimension-group"></a>Devo abilitare l'opzione Usa processi di gestione magazzino per il gruppo di dimensioni di immagazzinamento?

Se ritieni di voler utilizzare le funzionalità avanzate di gestione del magazzino in futuro, dovresti abilitare l'opzione **Usa processi di gestione magazzino**. Dopo aver salvato un gruppo di dimensioni di immagazzinamento, non è più possibile modificare l'impostazione dell'opzione **Usa processi di gestione magazzino** per questo. Se decidi di utilizzare i processi di gestione magazzino in un secondo momento, dovrai creare un nuovo magazzino in cui l'opzione è abilitata. Non esiste un processo automatizzato che puoi utilizzare per spostare tutto l'inventario da un magazzino a un altro magazzino o per copiare le configurazioni correlate in un nuovo magazzino.

### <a name="can-i-enable-the-use-warehouse-management-processes-for-the-storage-dimension-group-even-if-im-not-planning-to-use-advanced-warehousing"></a>Posso abilitare i processi Usa processi di gestione magazzino per il gruppo di dimensioni di immagazzinamento anche se non ho intenzione di utilizzare il magazzino avanzato?

Sì, anche se non prevedi di utilizzare le funzionalità avanzate di gestione del magazzino, puoi abilitare l'opzione **Usa processi di gestione magazzino** per il gruppo di dimensioni di immagazzinamento. Per creare ed elaborare le transazioni, dovrai completare la configurazione minima, ad esempio gerarchie di prenotazione e gruppi di sequenza unità. Tuttavia, le impostazioni per il magazzino avanzato vengono generalmente ignorate quando si elaborano manualmente liste di prelievo, documenti di trasporto e entrate prodotti (ad esempio, nelle pagine dell'ordine cliente e dell'ordine fornitore).

### <a name="when-should-i-enable-the-physical-inventory-option-for-a-storage-or-tracking-dimension-group"></a>Quando devo abilitare l'opzione Inventario fisico per un gruppo di dimensioni di immagazzinamento o tracciabilità?

Dovresti abilitare l'opzione **Inventario fisico** per i gruppi di dimensioni di immagazzinamento e tracciabilità quando è necessario conservare record di inventario dettagliati in base a tale dimensione. In genere, verrà rilevata fisicamente anche qualsiasi dimensione attiva. Pertanto, qualsiasi ricevuta, uscita o movimento dell'inventario verrà monitorato dalla dimensione selezionata. Se una dimensione non è obbligatoria (ad esempio la targa), è possibile abilitare le opzioni **Entrata non specificata consentita** e **Uscita non specificata consentita** per consentire agli utenti di ricevere, emettere o spostare l'inventario anche quando la dimensione non è specificata.

### <a name="when-should-i-enable-the-financial-inventory-option-for-a-storage-or-tracking-dimension-group"></a>Quando devo abilitare l'opzione Inventario finanziario per un gruppo di dimensioni di immagazzinamento o tracciabilità?

Dovresti abilitare l'opzione **Inventario finanziario** per i gruppi di dimensioni di immagazzinamento e tracciabilità quando è necessario conservare record finanziari dettagliati in base a tale dimensione. Le dimensioni **Sito** sono sempre tracciate finanziariamente, mentre altre dimensioni sono facoltative per la tracciabilità finanziaria. Se usi un modello di determinazione dei costi periodico come FIFO, LIFO o media ponderata, l'abilitazione dell'opzione **Inventario finanziario** per una dimensione indica che si effettueranno liquidazioni solo nei casi in cui l'entrata e l'uscita hanno gli stessi valori di dimensione. Ad esempio, se si abilita l'opzione **Inventario finanziario** per la dimensione **Magazzino** avrai un costo diverso in ogni magazzino e non sarà possibile liquidare le entrate e le uscite da magazzini diversi.

### <a name="can-i-make-changes-to-a-product-storage-or-tracking-dimension-group-after-transactions-exist"></a>Posso apportare modifiche a un gruppo di dimensioni prodotto, magazzino o tracciabilità dopo che esistono transazioni?

Dopo aver creato un gruppo di modelli di articoli, è possibile modificare l'impostazione dei campi **Piano di copertura per dimensione**, **Per prezzi di acquisto**, e **Per prezzi di vendita** se la casella di controllo **Attivo** è selezionata per una dimensione nel gruppo di modelli di articoli. Non sono consentite altre modifiche. Ad esempio, non è possibile abilitare o disabilitare le opzioni **Attivo**, **Uscita non specificata consentita**, **Entrata non specificata consentita**, **Inventario fisico**, e **Inventario finanziario**.

### <a name="can-i-change-the-product-storage-or-tracking-dimension-group-for-a-released-product"></a>Posso modificare il prodotto, l'immagazzinamento o il gruppo di dimensioni di tracciabilità per un prodotto rilasciato?

Se l'inventario disponibile per un prodotto è 0 (zero) e l'opzione **Valore aperto** è impostata su *No* per tutte le transazioni di inventario, è possibile modificare i gruppi di dimensioni di stoccaggio e tracciabilità nella pagina di produzione rilasciata. Non è possibile modificare il gruppo di dimensioni prodotto dopo la creazione del record.

## <a name="item-model-groups"></a>Gruppi di modelli di articoli

### <a name="when-should-i-enable-the-stocked-product-option"></a>Quando devo abilitare l'opzione Prodotto stoccato?

Dovresti abilitare l'opzione **Prodotto stoccato** per qualsiasi articolo che verrà tracciato nel tuo inventario. Quando questa opzione è abilitata, vengono conservate le transazioni di inventario dettagliate che tengono traccia dell'entrata e dell'uscita dell'articolo. Questa opzione è in genere abilitata per qualsiasi articolo tangibile che tieni nel tuo magazzino, ad esempio. Dovresti abilitare questa opzione anche se prevedi di aggiungere un articolo non tangibile come un articolo di servizio alle tue distinte base (DBA) o formule. Se non abiliti l'opzione **Prodotto stoccato** nessuna transazione di inventario viene registrata nel giornale di registrazione secondario di inventario e il costo degli articoli viene generalmente addebitato nella contabilità generale. Questa opzione viene spesso utilizzata, ad esempio, per forniture o servizi per negozi che non sono inclusi nelle distinte base o nelle formule.

### <a name="when-should-i-enable-the-post-physical-inventory-option"></a>Quando devo abilitare l'opzione Pubblica inventario fisico?

L'opzione **Pubblica inventario fisico** è in genere abilitata quando l'opzione **Prodotto stoccato** è abilitata. Quando si abilita questa opzione, il sistema terrà traccia dell'aggiornamento fisico dell'articolo nella transazione di inventario. Questa opzione viene utilizzata in coordinamento con i parametri in Contabilità fornitori, Contabilità clienti e Controllo produzione che specificano che l'aggiornamento fisico deve creare un giustificativo. In genere abiliti questa opzione quando desideri che la contabilità generale venga aggiornata ogni volta che aggiorni fisicamente l'inventario. Se Supply Chain Management non è il tuo sistema di registrazione per i dati finanziari, potresti voler disabilitare questa opzione.

### <a name="when-should-i-enable-the-post-financial-inventory-option"></a>Quando devo abilitare l'opzione Pubblica inventario finanziario?

L'opzione **Pubblica inventario finanziario** è in genere abilitata quando l'opzione **Prodotto stoccato** è abilitata. Questa opzione viene utilizzata in coordinamento con i parametri in Contabilità fornitori, Contabilità clienti e Controllo produzione che specificano che l'aggiornamento finanziario deve creare un giustificativo. In genere, abiliti questa opzione quando desideri che la contabilità generale venga aggiornata ogni volta che aggiorni finanziariamente l'inventario (ad esempio, fatturando ordini cliente e ordini fornitore o terminando un ordine di produzione). Se Supply Chain Management non è il tuo sistema di registrazione per i dati finanziari, potresti voler disabilitare questa opzione.

### <a name="when-should-i-enable-the-post-to-deferred-revenue-account-on-sales-delivery-option"></a>Quando devo abilitare l'opzione Registra in conto ricavi differiti alla consegna vendite?

Usi l'opzione **Registra in conto ricavi differiti alla consegna vendite** per indicare se vuoi riconoscere i ricavi nella contabilità generale quando registri un documento di trasporto per un ordine cliente. Questa opzione viene in genere utilizzata quando si verifica un lungo ritardo tra il documento di trasporto e la fattura di un ordine cliente o quando non è possibile fatturare tutti gli ordini cliente nel periodo. In genere, questa opzione viene disattivata se si registrano le fatture dell'ordine cliente subito dopo aver registrato il documento di trasporto. In questo modo si evita di generare registrazioni contabili generali aggiuntive che verranno immediatamente stornate quando si fattura un ordine cliente.

### <a name="when-should-i-enable-the-accrue-liability-on-product-receipt-option"></a>Quando devo abilitare l'opzione Passività ratei all'entrata prodotti?

Nella maggior parte delle organizzazioni, vorrai abilitare l'opzione **Passività ratei all'entrata prodotti** per tutti i gruppi di modelli di articoli, indipendentemente dal fatto che tu abbia un prodotto stoccato o un prodotto non stoccato. Questa opzione viene utilizzata per registrare un rateo nella contabilità generale, in base al prezzo di entrata del prodotto. Poiché in genere c'è un ritardo tra la registrazione dell'entrata prodotti per un ordine fornitore e la registrazione della fattura, la maggior parte delle organizzazioni deve riconoscere la passività nel bilancio per conformarsi alle normative locali come Generally Accepted Accounting Practices (GAAP). Se Supply Chain Management non è il tuo sistema di registrazione per i dati finanziari, potresti voler disabilitare questa opzione. Se la tua organizzazione utilizza le categorie di approvvigionamento negli ordini fornitore, puoi controllare il requisito di rateo abilitando l'opzione **Accumula spese su acquisti in entrata** per la regola dei criteri di categoria sulla pagina **Criteri di acquisto**.

### <a name="how-can-i-prevent-a-user-from-posting-a-purchase-order-product-receipt-if-a-receipt-registration-isnt-yet-posted"></a>Come posso impedire a un utente di registrare un'entrata prodotti di un ordine fornitore se la registrazione di una ricevuta non è ancora stata registrata?

È possibile impedire a un utente di registrare una ricevuta del prodotto dell'ordine fornitore se non è ancora avvenuta la registrazione dell'ordine fornitore abilitando l'opzione **Requisiti di registrazione** per il gruppo di modelli di articoli. Questa opzione viene in genere utilizzata nelle organizzazioni che utilizzano un processo di ricevimento in due fasi o in scenari in cui è necessario registrare un batch o un numero di serie, ad esempio, sugli articoli che si stanno ricevendo. L'opzione **Requisito di registrazione** si applica a *tutte* le ricevute di inventario per un articolo, non solo per gli ordini fornitore. Ad esempio, si applica a un giornale di registrazione inventario che ha una quantità positiva e un report dell'ordine di produzione come giornale di registrazione dichiarazioni di finito.

### <a name="how-can-i-prevent-a-user-from-posting-a-purchase-order-invoice-if-a-product-receipt-isnt-yet-posted"></a>Come posso impedire a un utente di registrare una fattura di un ordine fornitore se non è stata ancora registrata un'entrata prodotti?

È possibile impedire a un utente di registrare una fattura del prodotto dell'ordine fornitore se non è ancora avvenuta l'entrata prodotto dell'ordine fornitore abilitando l'opzione **Requisiti di ricevimento** per il gruppo di modelli di articoli. Questa opzione viene in genere utilizzata nelle organizzazioni che richiedono il riconoscimento fisico delle entrate nella contabilità generale per i ratei. L'opzione **Requisito di ricevimento** si applica a *tutte* le ricevute di inventario per un articolo, non solo per gli ordini fornitore. Ad esempio, si applica a un giornale di registrazione inventario che ha una quantità positiva e un report dell'ordine di produzione come giornale di registrazione dichiarazioni di finito. Se la tua organizzazione utilizza le categorie di approvvigionamento negli ordini fornitore, puoi controllare il requisito per una ricevuta abilitando l'opzione **Requisiti di ricevimento** per la regola dei criteri di categoria sulla pagina **Criteri di acquisto**.

### <a name="how-can-i-prevent-a-user-from-posting-a-sales-order-packing-slip-if-a-sales-order-picking-list-isnt-yet-posted"></a>Come posso impedire a un utente di registrare un documento di trasporto dell'ordine cliente se una distinta di prelievo dell'ordine cliente non è ancora stata pubblicata?

È possibile impedire a un utente di registrare un documento di trasporto o una fattura dell'ordine cliente se non è ancora stata creata una distinta di prelievo dell'ordine cliente abilitando l'opzione **Requisiti di prelievo** per il gruppo di modelli di articolo. Questa opzione viene in genere utilizzata nelle organizzazioni che eseguono un processo di prelievo fisico nel magazzino (ad esempio, utilizzando il dispositivo mobile del magazzino per effettuare il prelievo). L'opzione **Requisito di prelievo** si applica a *tutte* le uscite di inventario per un articolo, non solo per gli ordini cliente. Ad esempio, si applica a un giornale di registrazione inventario che ha una quantità negativa e un giornale di registrazione distinta di prelievo.

### <a name="how-can-i-prevent-a-user-from-posting-a-sales-order-invoice-if-the-sales-order-packing-slip-isnt-yet-posted"></a>Come posso impedire a un utente di registrare una fattura dell'ordine cliente se il documento di trasporto dell'ordine cliente non è ancora stato registrato?

È possibile impedire a un utente di registrare una fattura dell'ordine cliente se non si è ancora verificato un documento di trasporto dell'ordine cliente abilitando l'opzione **Requisiti di detrazione** per il gruppo di modelli di articolo. Questa opzione viene in genere utilizzata nelle organizzazioni che eseguono un processo di imballaggio fisico nel magazzino (ad esempio, utilizzando l'app per dispositivi mobili Warehouse Management per eseguire l'imballaggio o generando un documento che verrà incluso con gli articoli spediti). L'opzione **Requisito di detrazione** si applica a *tutte* le uscite di inventario per un articolo, non solo per gli ordini cliente. Ad esempio, si applica a un giornale di registrazione inventario che ha una quantità negativa e un giornale di registrazione distinta di prelievo.

### <a name="can-i-prevent-items-that-are-registered-from-being-sold"></a>Posso impedire che gli articoli registrati vengano venduti?

Quando un articolo viene registrato nell'inventario in Supply Chain Management, la quantità è fisicamente disponibile per essere emessa nel sistema. Se gli articoli che sono stati registrati ma non ancora ricevuti dovrebbero *non* essere disponibile per l'uscita per ordini cliente o ordini di produzione, ad esempio, considera l'utilizzo delle funzioni di stato inventario, blocco inventario, ordini di controllo qualità, ordini di quarantena o prenotazioni per gestire il processo aziendale.

## <a name="production-costing"></a>Determinazione costi di produzione

### <a name="can-i-use-one-costing-model-for-raw-materials-and-a-different-costing-model-for-finished-goods"></a>Posso utilizzare un modello di determinazione costi per le materie prime e un modello di determinazione costi diverso per i prodotti finiti?

Sì, puoi utilizzare diversi modelli di determinazione costi per ogni articolo. Non è raro che i produttori utilizzino un modello di determinazione costi periodico per le materie prime e un costo standard per i semilavorati e i prodotti finiti.

### <a name="how-can-i-drive-overhead-off-machine-costs"></a>Come posso ridurre il sovraccarico dei costi della macchina?

Per ridurre i costi delle macchine, è necessario creare risorse e gruppi di risorse per ciascuna macchina, in base ai requisiti aziendali. Ciascuna risorsa o gruppo di risorse può essere assegnata a categorie di costo per controllare il costo della macchina. Ciascuna categoria di costi può essere collegata a un gruppo di costi e ciascun gruppo di costi può essere utilizzato come base per il calcolo dei costi indiretti nel foglio di determinazione costi.

### <a name="how-do-i-recognize-cost-that-is-related-to-energy-consumption-for-example-water-energy-or-gas-consumption-on-the-costing-sheet"></a>Come riconosco il costo correlato al consumo di energia (ad esempio, consumo di acqua, energia o gas) sul foglio di determinazione costi?

In genere è possibile riconoscere i costi correlati al consumo di energia in due modi:

- Crea una riga nella tua distinta base o formula. In genere, questa riga viene creata come articolo in assistenza ed è possibile specificare l'unità di misura che si sta consumando in relazione alla quantità che si sta producendo. In questo modo l'utente può consumare una quantità diversa durante il processo produttivo. Puoi consumare automaticamente gli articoli in base al valore che selezioni nel campo **Principio di registrazione del consumo di materiali**.
- Crea un costo indiretto sul foglio determinazione costi. In genere, questo approccio viene utilizzato per allocare il costo totale del consumo di energia nel processo di produzione. È possibile utilizzare il gruppo di costi e la base di assorbimento per scalare il consumo in base ai materiali o alla manodopera nel ciclo di lavorazione, ad esempio.

È necessario selezionare l'opzione migliore, in base ai propri requisiti di dichiarazione, riconciliazione e operativi.

### <a name="can-i-capture-resource-details-in-the-bom-or-formula"></a>Posso acquisire i dettagli delle risorse nella distinta base o nella formula?

I dettagli della risorsa possono essere acquisiti solo in un'operazione di ciclo di lavorazione. Sebbene sia possibile creare un articolo in assistenza per rappresentare una risorsa e assegnare un costo per aumentare il calcolo del costo per un prodotto finito, in genere non consigliamo questo approccio. Si consiglia invece di creare un ciclo di lavorazione semplice con una riga per tenere traccia dei costi delle risorse e configurare l'operazione in modo che venga consumata automaticamente all'inizio o alla fine dell'ordine di produzione.

### <a name="can-i-view-the-calculation-details-if-the-cost-is-manually-entered"></a>Posso visualizzare i dettagli del calcolo se il costo è inserito manualmente?

N. Se inserisci manualmente il prezzo sulla pagina **Prezzo dell'articolo**, i pulsanti **Visualizza dettagli di calcolo** e **Dettagli di calcolo report** non sono disponibili. Se selezioni il pulsante **Rollup costo per gruppo di costi** per un prezzo di costo immesso manualmente, viene visualizzata una riga riepilogativa e verrà eseguito il rollup di tutti i costi nell'articolo finito.

### <a name="does-the-system-calculate-variances-on-a-production-order-when-i-manually-enter-the-cost"></a>Il sistema calcola gli scostamenti su un ordine di produzione quando inserisco manualmente il costo?

Sì, il sistema calcola gli scostamenti quando si inserisce manualmente un costo standard. Tuttavia, quando si immette manualmente un costo standard anziché calcolarlo, tutti i consumi di materiale, ciclo e costi indiretti nell'ordine di produzione vengono considerati uno scostamento sostitutivo. Se sono presenti scostamenti aggiuntivi, come il consumo di materiali o manodopera extra, verranno registrati come scostamenti dalla distinta base di produzione. Pertanto, si consiglia vivamente di eseguire sempre un calcolo per gli articoli che hanno una distinta base, un ciclo o costi indiretti.

### <a name="how-can-i-carry-the-variances-from-a-subproduction-order-to-the-parent-production-order"></a>Come posso trasferire gli scostamenti da un ordine di produzione secondaria all'ordine di produzione padre?

Quando utilizzi un modello di determinazione costi periodico come FIFO, LIFO o media ponderata, i costi di una sottoproduzione verranno riconosciuti nel modello euristico selezionato per gli articoli. Se è necessaria la determinazione dei costi effettivi, valuta l'utilizzo del principio di contrassegno per indicare quale produzione secondaria viene emessa per un ordine di produzione padre. In alternativa, considera l'utilizzo dell'opzione **Inventario finanziario** per le dimensioni **Batch** o **Numero di serie** nel gruppo di dimensioni di rilevamento, ad esempio.

### <a name="how-does-the-flushing-principle-affect-consumption"></a>In che modo il principio di registrazione del consumo di materiali in entrata influisce sui consumi?

Il principio di registrazione del consumo di materiali in entrata su una distinta base, una formula o una riga ciclo di lavorazione controlla i tempi e la tecnica utilizzati per consumare l'articolo o la manodopera. Se selezioni *Avvio*, l'articolo o la manodopera vengono consumati automaticamente quando si avvia l'ordine di produzione. Se selezioni *Fine*, l'articolo o la manodopera vengono consumati automaticamente quando dichiari l'ordine di produzione come finito. Se selezioni *Manuale*, un utente deve prelevare manualmente i materiali o registrare l'ora in un giornale di registrazione processi o schede cicli di lavorazione. Anche le distinte base e le formule hanno un'opzione *Disponibile in ubicazione*. Se si seleziona questa opzione, gli articoli vengono consumati automaticamente dopo essere stati trasferiti all'ubicazione del piano di produzione.

### <a name="how-should-i-run-cost-calculations-if-i-have-multi-level-boms-or-formulas"></a>Come devo eseguire i calcoli dei costi se ho DBA o formule multilivello?

In generale, ti consigliamo di iniziare dal livello più basso delle tue distinte base o formule per il calcolo. Per semplificare il filtro durante i calcoli dei costi di esecuzione in serie, puoi utilizzare i gruppi di calcolo per aiutare a separare i prodotti. Ti consigliamo inoltre di eseguire il processo periodico *Ricalcola i livelli della distinta base* prima di iniziare a calcolare i costi di esecuzione in serie. Ogni organizzazione dovrebbe considerare la combinazione di prodotti e definire una strategia che soddisfi le esigenze specifiche del prodotto e delle strutture DBA o formula.

## <a name="transfer-order-costing"></a>Determinazione costi ordine di trasferimento

### <a name="is-there-a-way-to-allocate-freight-to-a-transfer-order-cost"></a>C'è un modo per allocare le spese di trasporto a un costo dell'ordine di trasferimento?

È possibile aggiungere spese a un ordine di trasferimento per aggiungere costi. Il codice spese definisce l'addebito e il credito per l'addebito che stai aggiungendo. Devi prima creare i codici di addebito nel modulo **Gestione inventario**. Per aggiungere un addebito a un ordine di trasferimento, seleziona **Addebiti** nella riga dell'ordine di trasferimento a cui si desidera aggiungere un addebito.

## <a name="variances"></a>Scostamenti

### <a name="can-i-treat-variances-differently-based-on-the-site-or-warehouse"></a>Posso trattare gli scostamenti in modo diverso, in base al sito o al magazzino?

Non è disponibile alcuna opzione per configurare i conti di scostamento in base al sito. Quando usi la determinazione dei costi standard per un prodotto rilasciato, è possibile selezionare il conto principale utilizzato per le registrazioni dello scostamento dei costi standard sulla pagina **Registrazione**. Puoi selezionare di configurare gli account per un articolo, un gruppo di articoli o tutti gli articoli. È inoltre possibile configurare un gruppo di costi, un gruppo di gruppi di costi o tutti i gruppi di costi.

### <a name="can-i-separate-variances-that-are-the-result-of-currency-exchange-rates-from-other-types-of-variances"></a>Posso separare gli scostamenti risultanti dai tassi di cambio valuta da altri tipi di scostamenti?

Se uno scostamento è il risultato di una differenza del tasso di cambio tra il prezzo dell'ordine fornitore e il costo standard per un articolo, non è possibile separare la differenza del tasso di cambio dagli altri scostamenti.

## <a name="reporting"></a>Report

### <a name="how-many-inventory-value-report-configurations-can-i-create-and-use"></a>Quante configurazioni di report del valore di magazzino posso creare e utilizzare?

Non c'è limite al numero di configurazioni di report del valore di magazzino che è possibile creare. È necessario valutare i requisiti di dichiarazione specifici e creare il numero di configurazioni necessarie per soddisfare tali requisiti. Per eseguire il report o l'opzione di archiviazione del report sarà necessaria almeno una configurazione del report sul valore di magazzino.

### <a name="can-i-use-the-inventory-value-report-to-analyze-the-cost-of-an-item-in-each-warehouse"></a>Posso utilizzare il report sul valore di magazzino per analizzare il costo di un articolo in ciascun magazzino?

Sì. Puoi abilitare l'opzione **Visualizza** o **Totale** per ciascuna dimensione **Magazzino** nella configurazione del report sul valore di magazzino. Tuttavia, il report mostrerà i valori solo per le dimensioni in cui l'opzione **Inventario finanziario** è abilitata per il gruppo di dimensioni di immagazzinamento. Per altre dimensioni mostrerà solo colonne vuote. Per ulteriori informazioni, vedi [Esempi e logica di report del valore di magazzino](inventory-value-report-examples.md).

### <a name="how-can-i-view-the-inventory-quantity-as-of-a-specific-date-with-the-weighted-average"></a>Come posso visualizzare la quantità di inventario a una data specifica con la media ponderata?

Puoi utilizzare il report **Aging delle scorte**, che include una colonna **Costo unitario medio** che mostra il valore dell'inventario a una data specifica. Per ulteriori informazioni, vedi [Esempi e logica di report di aging di magazzino](inventory-aging-report.md).

### <a name="how-can-i-view-which-receipt-transactions-are-settled-against-an-issue-transaction"></a>Come posso visualizzare quali transazioni di ricevuta vengono liquidate a fronte di una transazione di uscita?

È possibile visualizzare le liquidazioni per una transazione di inventario selezionando **Liquidazioni** o **Esplora costi** sulla scheda **Inventario** nel riquadro azioni della pagina **Transazione di inventario** o **Dettagli transazione di inventario**. Se selezioni una ricevuta per visualizzare le uscite relative alla transazione, esplora costi non mostra i dettagli. I dettagli vengono mostrati solo se si seleziona una transazione di uscita.

### <a name="how-does-the-inventory-value-report-show-items-that-have-a-positive-physical-quantity-and-a-negative-financial-value"></a>In che modo il report del valore di magazzino mostra gli articoli che hanno una quantità fisica positiva e un valore finanziario negativo?

Il report del valore di magazzino separa gli importi e le quantità fisici e finanziari nelle colonne. I valori visualizzati nel report corrispondono all'intervallo di date selezionato per l'esecuzione del report. Il livello di riepilogo visualizzato dipende dalle impostazioni selezionate. Se un articolo ha transazioni che sono state fisicamente ricevute ed emesse finanziariamente, le quantità e i valori vengono sommati in modo indipendente. Se hai scelto di visualizzare il livello di dettaglio come transazioni, le righe per ciascuna entrata e uscita vengono visualizzate separatamente e le quantità e gli importi fisici e finanziari, rispettivamente. Per ulteriori informazioni, vedi [Esempi e logica di report del valore di magazzino](inventory-value-report-examples.md).

### <a name="what-is-the-impact-of-storage-and-tracking-dimension-groups-on-the-inventory-value-report"></a>Qual è l'impatto dei gruppi di dimensioni di tracciabilità e immagazzinamento sul report sul valore di magazzino?

Se abiliti l'opzione **Valore finanziario** per una dimensione in un gruppo di dimensioni di tracciabilità e immagazzinamento, è possibile selezionare l'opzione **Visualizza** o **Totale** per la dimensione nella configurazione del report sul valore di magazzino. Se selezioni l'opzione **Visualizza** o **Totale** per una dimensione in cui l'opzione **Valore finanziario** non è selezionata, la colonna sarà vuota nell'output del report. Se hai abilitato l'opzione **Valore finanziario** per una dimensione in un gruppo di dimensioni di tracciabilità e immagazzinamento e non selezioni l'opzione **Visualizza** o **Totale** sulla configurazione del report del valore di magazzino, il sistema riepilogherà i valori per le dimensioni selezionate che sono tracciati finanziariamente.

### <a name="can-i-customize-the-power-bi-embedded-reports-for-costing"></a>Posso personalizzare i report incorporati Power BI per la determinazione costi?

Sì, gli utenti che dispongono delle autorizzazioni di sicurezza corrette possono aggiornare il canvas di progettazione del report per qualsiasi report integrato Power BI in Supply Chain Management. Per ulteriori informazioni, vedi [Personalizzare i report incorporati nelle aree di lavoro analitiche](../../fin-ops-core/dev-itpro/analytics/customize-analytical-workspace.md).

### <a name="where-can-i-view-the-variance-analysis-statement"></a>Dove posso visualizzare la dichiarazione di analisi dello scostamento?

È possibile accedere alla dichiarazione di analisi dello scostamento andando in **Gestione costi \> Richieste di informazioni e report \> Contabilità inventario - report di analisi** o **Gestione costi \> Richieste di informazioni e report \> Contabilità produzione - Report di analisi**. Entrambe le opzioni aprono lo stesso report e il report ha lo stesso comportamento.

## <a name="item-prices-and-default-costs"></a>Prezzi degli articoli e costi predefiniti

### <a name="can-i-maintain-the-cost-for-each-product-variant"></a>Posso mantenere il costo per ciascuna variante di prodotto?

Sì. Puoi abilitare l'opzione **Usa il prezzo di costo per variante** sulla scheda dettaglio **Gestione costi** della pagina **Prodotto rilasciato** per abilitare il prezzo per variante di prodotto. (Questa opzione è disponibile solo per le rappresentazioni generali prodotto.) Quindi, sulla pagina **Prezzo dell'articolo** (che puoi aprire dalle pagine **Versione determinazione costi** o **Prodotto rilasciato**), è possibile selezionare **Visualizzazione delle dimensioni** per specificare se vuoi visualizzare la dimensione **Configurazione**, **Dimensione**, **Colore**, o **Stile**. Per salvare l'impostazione e utilizzare le dimensioni selezionate ogni volta che si apre la pagina, abilita l'opzione **Salva configurazione** quindi seleziona **OK**. Puoi inserire le dimensioni solo per gli articoli in cui le dimensioni sono attive nel gruppo di dimensioni del prodotto.

### <a name="can-i-maintain-the-cost-for-each-warehouse"></a>Posso mantenere il costo per ciascun magazzino?

No, non è possibile mantenere il prezzo dell'articolo per magazzino. Tuttavia, è possibile mantenere gli accordi commerciali per i prezzi di acquisto o di vendita per magazzino. Innanzitutto, seleziona l'opzine **Per prezzi di acquisto** o **Per prezzi di vendita** per la dimensione sulla pagina **Gruppo di dimensioni di immagazzinamento**. Quindi, quando crei il giornale di registrazione accordi commerciali e apri le righe per le dimensioni, seleziona **Inventario \> Visualizza dimensioni** per selezionare quale dimensione deve essere visualizzata nella griglia. Per salvare l'impostazione e utilizzare le dimensioni selezionate ogni volta che si apre la pagina, abilita l'opzione **Salva configurazione** quindi seleziona **OK**. Puoi inserire le dimensioni solo per gli articoli in cui le dimensioni sono attive nel gruppo di dimensioni del prodotto.

### <a name="what-are-price-charges"></a>Cosa sono le spese prezzo?

Le spese prezzo consentono di aggiungere un importo fisso al prezzo unitario del prezzo dell'articolo o dell'accordo commerciale. Quando inserisci un importo nel campo **Spese prezzo** puoi anche inserire un valore nel campo **Quantità correlate a spese**. Le spese prezzo vengono ammortizzate sulla quantità correlata a spese specificata. Abilita l'opzione **Incl. nel prezzo unitario** se vuoi includere le spese di prezzo nel prezzo unitario dell'articolo. Questa opzione è sempre abilitata per un costo standard.

### <a name="how-should-i-configure-prices-for-items-that-are-procured-in-multiple-currencies"></a>Come devo configurare i prezzi per gli articoli acquistati in più valute?

Se inserisci un prezzo predefinito nel campo **Prezzo d'acquisto** sulla pagina **Prodotto rilasciato** si presume che sia nella valuta contabile della contabilità generale per la persona giuridica in cui ti trovi. Allo stesso modo, se si immette un prezzo di acquisto in una versione di determinazione dei costi in cui il campo **Tipo di prezzo** è impostato su *Acquisto*, si presume che il prezzo sia nella valuta contabile della persona giuridica. Quando crei un ordine fornitore per un fornitore che ha una valuta diversa, il sistema converte automaticamente la valuta dall'importo della valuta contabile alla valuta della transazione utilizzando il tasso di cambio specificato nel campo **Tipo di tasso di cambio valuta contabile** nella contabilità generale.

Quando crei un giornale di registrazione degli accordi commerciali, puoi specificare la valuta in cui stai esprimendo il prezzo su ciascuna riga. Puoi creare accordi commerciali per più valute, fornitori specifici e molte altre combinazioni di fattori. Se crei un ordine fornitore in cui esiste un accordo commerciale per la valuta che hai selezionato, il sistema utilizzerà l'accordo commerciale con la valuta corrispondente. Quando si registrano transazioni quali entrate prodotti o fatture, l'importo verrà convertito nella valuta contabile della contabilità generale utilizzando il tasso di cambio della valuta contabile specificato nella contabilità generale.

### <a name="how-should-i-configure-costs-for-items-that-are-procured-in-multiple-currencies"></a>Come devo configurare i costi per gli articoli acquistati in più valute?

I costi non possono essere configurati in più di una valuta. Il costo specificato per il prezzo dell'articolo o i costi predefiniti inseriti nel campo **Prezzo** della scheda dettaglio **Gestione costi** della pagina **Prodotto rilasciato** sono sempre espressi nella valuta contabile della contabilità generale per la persona giuridica che hai selezionato.

Se la tua organizzazione utilizza la determinazione dei costi standard, dovresti definire una strategia per definire i costi quando sono presenti più valute. È inoltre necessario definire un processo per aggiornare regolarmente il costo per ridurre il numero di scostamenti registrati.

### <a name="can-i-use-the-profit-setting-on-the-cost-group-page-to-calculate-sales-prices"></a>Posso utilizzare l'impostazione Profitto nella pagina Gruppo costi per calcolare i prezzi di vendita?

Sì, puoi usare l'impostazione **Profitto** della pagina **Gruppo di costi** per aggiungere una percentuale quando i prezzi di vendita vengono calcolati utilizzando un calcolo dei costi. Per ulteriori informazioni, vedi [Calcoli DBA](bom-calculations.md).

## <a name="marking"></a>Contrassegno in corso

### <a name="how-does-marking-affect-periodic-costing-models"></a>In che modo il contrassegno influisce sui modelli di determinazione costi periodici?

Se utilizzi un modello di determinazione dei costi periodico come FIFO, LIFO o media ponderata e hai contrassegnato una transazione in entrata rispetto a una transazione in uscita, il modello euristico dell'articolo viene ignorato durante il processo di chiusura dell'inventario. Il sistema utilizzerà invece il costo effettivo della ricevuta per il costo dell'uscita.

### <a name="what-happens-during-the-inventory-close-when-i-use-marking"></a>Cosa succede durante la chiusura dell'inventario quando utilizzo il contrassegno?

Quando si contrassegnano le entrate e le uscite, la chiusura dell'inventario regolerà le transazioni contrassegnate insieme. Quando il contrassegno viene utilizzato per creare la liquidazione, il campo **Principio** della pagina **Liquidazione** sarà impostato su *Contrassegno*. Se una transazione viene contrassegnata prima di essere aggiornata fisicamente o finanziariamente, l'uscita utilizzerà il costo della ricevuta contrassegnata anziché il costo medio corrente. Se le transazioni vengono contrassegnate dopo l'aggiornamento finanziario, il processo di chiusura e rettifica dell'inventario regolerà il costo di uscita in modo che corrisponda al costo di entrata.

### <a name="can-i-manually-mark-transactions-when-i-use-standard-costing-or-moving-average"></a>Posso contrassegnare manualmente le transazioni quando utilizzo il costo standard o la media mobile?

No, non puoi contrassegnare manualmente le entrate o le uscite quando utilizzi la determinazione dei costi standard o la media mobile. Se le transazioni (ad esempio, consegna diretta o ordini interaziendali) vengono contrassegnate automaticamente, il record di contrassegno rimarrà e fungerà da prenotazione definitiva. Tuttavia, quando si utilizza la determinazione dei costi standard o la media mobile, il contrassegno dei record non ha alcun effetto sul costo degli articoli.

### <a name="how-does-marking-affect-the-profit-and-loss-statement"></a>In che modo il contrassegno influisce sul rendiconto profitti e perdite?

Quando si contrassegna una transazione di uscita su un'entrata, il costo dell'uscita corrisponderà all'entrata selezionata. Quando registri fisicamente e finanziariamente l'uscita, la registrazione influirà sui conti **Costo della merce venduta, consegnata** e **Costo della merce venduta, fatturata** specificati nel profilo di registrazione dell'inventario. Se una transazione viene contrassegnata dopo l'aggiornamento fisico o finanziario, il processo *Chiusura e rettifica dell'inventario* creerà una rettifica che ha un giustificativo corrispondente che rettifica il conto **Costo della merce venduta, fatturata** e compensa nel conto specificato per **Costo delle unità, fatturate** (inventario).

### <a name="how-does-marking-affect-master-planning"></a>In che modo il contrassegno influisce sulla pianificazione generale?

La scheda **Aggiornamento standard** sulla pagina **Parametri di pianificazione generale** include un campo denominato **Aggiorna contrassegno**. L'opzione selezionata viene utilizzata quando si consolida un ordine pianificato generato dalla pianificazione generale. Di seguito vengono illustrate le opzioni disponibili.

- *No* – Il sistema non esegue alcun contrassegno.
- *Standard* – Il sistema contrassegna le entrate rispetto alle uscite in base al pegging. Un ordine di richiesta viene contrassegnato in base a un ordine di evasione. Se una certa quantità rimane in fase di evasione, l'ordine di evasione non viene contrassegnato.
- *Esteso* – Il sistema contrassegna sia gli ordini di approvvigionamento che gli ordini di evasione, indipendentemente dal fatto che una qualsiasi quantità rimanga aperta nell'ordine di evasione.

## <a name="negative-inventory"></a><a name="negative-inventory"></a>Scorte negative

### <a name="when-should-i-allow-physical-negative-inventory"></a>Quando dovrei consentire l'inventario fisico negativo?

In generale, non ti consigliamo di consentire l'inventario fisico negativo, perché non è possibile avere meno di 0 (zero) di un articolo tangibile nel magazzino. Tuttavia, i processi aziendali di alcuni settori e scenari aziendali potrebbero limitare le operazioni che richiedono che l'inventario possa diventare fisicamente negativo. Ad esempio, i rivenditori potrebbero non voler impedire la vendita di un articolo che viene portato nel registro, anche quando il sistema indica che non sono disponibili articoli. I produttori di processo forniscono un altro esempio. Per questi produttori, la quantità che viene consumata può superare quanto raccomandato nella formula. In alternativa, il consumo potrebbe essere stimato anziché preciso, in modo che il consumo superi la quantità in una ubicazione specifica, come un serbatoio.

Quando possibile, dovresti valutare il tuo processo aziendale e cercare di migliorarlo per garantire che l'inventario non possa essere negativo. Se è necessario consentire l'inventario negativo, devi disporre di un processo aziendale chiaro per correggere l'inventario negativo, poiché può influire negativamente sui costi.

### <a name="when-should-i-allow-financial-negative-inventory"></a>Quando dovrei consentire l'inventario finanziario negativo?

In generale, consigliamo che la maggior parte delle organizzazioni consenta l'inventario negativo finanziario. (Nella maggior parte dei casi, le fatture degli ordini fornitore non vengono elaborate prima di poter spedire gli articoli.) È necessario abilitare questa opzione quando si hanno processi aziendali specifici che richiedono che il prezzo di vendita rifletta il costo finale di un ordine fornitore. Ad esempio, questo requisito potrebbe essere applicato in un settore di produzione su ordinazione o in aree specifiche in cui è imposto per legge.

### <a name="what-happens-to-the-cost-of-my-issues-when-the-inventory-is-negative"></a>Cosa succede al costo delle uscite quando l'inventario è negativo?

Quando l'inventario del tuo articolo è negativo e emetti più articoli di quelli che hai fisicamente, il sistema utilizzerà il prezzo articolo predefinito per calcolare la media corrente se utilizzi un modello di costo periodico come FIFO, LIFO o media ponderata. Se non viene specificato alcun prezzo predefinito per l'articolo, il sistema emetterà l'inventario con un valore pari a 0 (zero). Questo comportamento può rendere imprecisi i calcoli futuri della media corrente o mobile.

### <a name="can-i-prevent-items-from-being-picked-packed-or-sold-on-sales-orders-and-production-orders-if-there-isnt-enough-on-hand-inventory"></a>Posso impedire che gli articoli vengano prelevati, imballati o venduti negli ordini cliente e negli ordini di produzione se le scorte disponibili non sono sufficienti?

Sì. Ti consigliamo di disabilitare l'opzione **Negativo fisico** per il gruppo di modelli di articoli per impedire che gli articoli vengano prelevati, imballati o venduti negli ordini cliente e negli ordini di produzione.

### <a name="can-i-prevent-items-from-being-invoiced-on-a-sales-order-if-no-purchase-orders-have-been-invoiced-for-the-same-item"></a>Posso impedire che gli articoli vengano fatturati in un ordine cliente se non sono stati fatturati gli ordini fornitore per lo stesso articolo?

Sì. Ti consigliamo di disabilitare l'opzione **Negativo finanziario** per il gruppo di modelli di articoli per impedire che gli articoli vengano fatturati in un ordine cliente se non sono stati fatturati gli ordini fornitore per lo stesso articolo.

### <a name="how-does-negative-inventory-affect-financial-ratios-such-as-gross-profit-margin"></a>In che modo l'inventario negativo influenza gli indici finanziari come il margine di profitto lordo?

Quando consenti all'inventario di diventare negativo, il valore dell'inventario nello stato patrimoniale e il costo del venduto nel rendiconto profitti e perdite possono essere sottovalutati, soprattutto se per i tuoi articoli non è configurato alcun prezzo predefinito. Pertanto, i report e gli indici finanziari come i margini di profitto lordo possono essere sopravvalutati, perché il costo non è corretto. Se usi un modello di determinazione costi periodico come FIFO, LIFO o media ponderata, il valore delle uscite può essere rettificato quando esegui il processo di chiusura e rettifica dell'inventario dopo che le quantità di inventario negative sono state corrette. Tuttavia, se usi la media mobile, non c'è modo di rivalutare le singole transazioni.

### <a name="how-should-i-correct-negative-inventory"></a>Come devo correggere l'inventario negativo?

Ti consigliamo di monitorare e correggere frequentemente l'inventario negativo quando la tua organizzazione o i requisiti aziendali richiedono che l'inventario diventi negativo. È possibile correggere i valori di inventario eseguendo un conteggio ciclo, registrando una rettifica o registrando un giornale di registrazione movimenti. Se è necessario riconoscere i guadagni imprevisti di inventario in un conto di contabilità generale specifico, devi pianificare l'utilizzo di un giornale di registrazione movimenti. In caso contrario, quando si utilizza il conteggio del ciclo o il processo di rettifica dell'inventario, il sistema registrerà la rettifica dell'inventario nel conto **Entrata inventario** e compensa nei conti **Spese di magazzino, profitto** specificati nel profilo di registrazione dell'inventario.

### <a name="do-i-have-to-create-a-new-item-if-my-inventory-has-gone-negative-and-i-use-moving-average"></a>Devo creare un nuovo articolo se il mio inventario è negativo e utilizzo la media mobile?

N. Se la tua organizzazione consente all'inventario di diventare fisicamente negativo e stai utilizzando la media mobile come modello di inventario, il sistema utilizzerà la sequenza dei costi di fallback assegnata nella pagina **Parametri di gestione articoli e magazzino** per determinare come verrà assegnato il costo alle uscite. In generale, ti consigliamo di evitare che il tuo inventario diventi fisicamente negativo. Per ulteriori informazioni, vedi altre domande nella sezione [Inventario negativo](#negative-inventory) di questo articolo.

## <a name="not-stocked-products"></a>Prodotti non stoccati

### <a name="can-i-post-sales-order-picking-lists-for-not-stocked-products"></a>Posso registrare liste di prelievo ordini cliente per prodotti non stoccati?

Quando si genera una distinta di prelievo per un ordine cliente che include articoli che si trovano in un gruppo di modelli articoli non stoccati, non verranno visualizzate righe per gli articoli non stoccati. Non è possibie utilizzare l'app per dispositivi mobili Warehouse Management per elaborare gli articoli non stoccati.

Quando si genera un documento di trasporto per un ordine cliente che include articoli che si trovano in un gruppo di modelli articoli non stoccati, imposta il campo **Quantità** su *Quantità prelevata e prodotti non stoccati* per includere gli articoli non stoccati nella generazione del documento. Se selezioni *Tutto*, solo gli articoli stoccati saranno inclusi nel documento di trasporto.

### <a name="should-i-use-a-not-stocked-product-or-a-category-sales-category-or-procurement-category"></a>Devo utilizzare un prodotto non stoccato o una categoria (categoria di vendita o categoria di approvvigionamento)?

La scelta tra un prodotto non stoccato e una categoria dipende dalle specifiche esigenze aziendali. I prodotti non stoccati generalmente offrono un maggiore controllo sui valori predefiniti, come quantità e prezzi sugli ordini fornitore e sugli ordini cliente. Pertanto, i prodotti nonstoccati sono preferiti negli scenari in cui lo stesso prodotto o servizio viene acquistato o venduto più di una volta. Le categorie sono utili negli scenari in cui il prezzo, gli articoli, le descrizioni e così via non sono coerenti da una transazione all'altra. Le categorie possono essere utilizzate anche su qualsiasi prodotto per aiutare a classificare il tipo di prodotto che viene venduto o acquistato.

## <a name="service-items"></a>Articoli di tipo Assistenza

### <a name="what-is-the-difference-between-a-service-item-and-a-not-stocked-product"></a>Qual è la differenza tra un articolo in assistenza e un prodotto non stoccato?

Un articolo in assistenza è un tipo di prodotto. Quando crei un prodotto appena rilasciato, puoi impostare il campo **Tipo di prodotto** su *Articolo* o *Servizio*. *Articolo* è in genere selezionato per indicare che l'oggetto è tangibile, mentre *Servizio* è in genere selezionato per indicare che l'elemento è intangibile.

Qualsiasi prodotto rilasciato, indipendentemente dal fatto che si tratti di un articolo o di un servizio, può essere stoccato o meno. L'impostazione stoccato o non stoccato è controllata dal gruppo di modelli di articolo selezionato per il prodotto rilasciato. Quando selezioni un gruppo di articoli che non è stoccato, il sistema non crea transazioni di inventario per l'ordine cliente o l'ordine fornitore correlato, ad esempio.

### <a name="can-i-include-not-stocked-items-in-a-bom"></a>Posso includere articoli non stoccati in una distinta base?

No, non puoi includere un prodotto rilasciato che è collegato a un gruppo di modelli di articoli in cui l'opzione **Stoccato** è disabilitata in una distinta base o in una formula. Non importa se il campo **Tipo di prodotto** è impostato su *Articolo* o *Servizio*. Solo gli articoli stoccati possono essere inclusi nella distinta base o nelle righe formula.

## <a name="costing-modelspecific-questions"></a>Domande specifiche del modello di determinazione costi

### <a name="which-costing-model-should-i-use"></a>Quale modello di determinazione costi devo usare?

I modelli di determinazione costi da selezionare dipendono dai requisiti aziendali. Prima di selezionare un modello di determinazione costi da utilizzare in Supply Chain Management, è necessario verificare che il modello sia consentito dalle normative locali. Ti consigliamo di convalidare la tua selezione con un contabile certificato nella tua area.

### <a name="can-i-use-more-than-one-costing-model-in-my-organization"></a>Posso utilizzare più di un modello di determinazione costi nella mia organizzazione?

Sì. Non c'è limite al numero di gruppi di modelli di articoli o di modelli di determinazione costi selezionabili in Supply Chain Management.

### <a name="can-i-use-more-than-one-costing-model-for-each-item"></a>Posso utilizzare più di un modello di determinazione costi per ogni articolo?

N. È possibile selezionare un solo modello di determinazione costi per ogni prodotto rilasciato. Questo comportamento è controllato dal gruppo di modelli di articoli. Se devi utilizzare più di un modello di determinazione costi per generare report sui valori di inventario, dovresti prendere in considerazione l'utilizzo del componente aggiuntivo Contabilità inventario globale.

### <a name="when-i-use-manufacturing-execution-which-costing-methodology-should-i-use"></a>Quando utilizzo l'esecuzione della produzione, quale metodologia di determinazione costi dovrei utilizzare?

I modelli di determinazione costi da selezionare dipendono dai requisiti aziendali. Non vi è alcun vantaggio o svantaggio specifico nell'utilizzo di qualsiasi modello di determinazione costi quando l'organizzazione utilizza anche l'esecuzione della produzione.

### <a name="when-is-fefo-used"></a>Quando si usa il FEFO?

FEFO (First expired, first out) non è una metodologia di determinazione costi. Al contrario, è una tecnica di prenotazione che viene spesso utilizzata nelle organizzazioni di produzione. È possibile abilitare le prenotazioni FEFO per un gruppo di modelli di articoli abilitando l'opzione **Controllo in base a data FEFO** e quindi selezionando un valore nel campo **Criteri di prelievo**.

### <a name="are-there-performance-benefits-to-selecting-one-costing-model-over-another"></a>Ci sono vantaggi in termini di prestazioni nella selezione di un modello di determinazione costi rispetto a un altro?

In generale, il modello di determinazione costi selezionato per un articolo ha un impatto minimo sulle prestazioni complessive del sistema. Tuttavia, la quantità di tempo necessaria per eseguire il processo di chiusura o ricalcolo dell'inventario potrebbe essere influenzata dal modello di determinazione costi dell'inventario selezionato. Ad esempio, se usi il costo standard o la media mobile, il processo di chiusura dell'inventario ha un impatto minimo sul sistema, poiché non aggiorna ogni transazione di inventario e non crea liquidazioni. Tuttavia, un modello di determinazione dei costi periodico come FIFO, LIFO o media ponderata può aumentare la quantità di tempo necessaria per completare il processo di chiusura dell'inventario. In particolare, il processo di chiusura può essere più lungo quando si immette un numero elevato nel campo **Numero massimo di iterazioni consentito per articolo** o un numero basso nel campo **Importo minimo consentito** per il processo *Chiudi inventario*.

### <a name="when-should-i-use-the-fixed-receipt-price-option"></a>Quando dovrei utilizzare l'opzione Prezzo di entrata fisso?

Quando selezioni la casella di controllo **Prezzo di entrata fisso** sulla pagina **Gruppo di modelli di articoli** per un articolo, il sistema utilizzerà il prezzo di entrata come costo standard per l'entrata inventario. Se c'è una differenza tra il prezzo di acquisto e il prezzo di costo articolo predefinito configurato per un prodotto, la differenza verrà registrata nel conto **Profitto sul prezzo di entrata fisso** o **Perdita sul prezzo di entrata fisso** e compensa nel conto **Deviazione prezzo di entrata fisso**. (Tutti questi conti sono specificati sulla pagina **Registrazione**.)

Dovresti selezionare la casella di controllo **Prezzo di entrata fisso** quando usi un modello di determinazione dei costi periodico come FIFO, LIFO o media ponderata e richiedi che uno scostamento del prezzo di acquisto venga registrato nella contabilità generale se il prezzo dell'entrata è diverso dal costo dell'articolo predefinito.

### <a name="moving-average"></a>Media mobile

### <a name="is-moving-average-the-same-as-a-floating-average"></a>La media mobile è uguale a una media con valore oscillante?

I termini media mobile, media con valore oscillante e media corrente sono spesso usati come sinonimi. Di questi termini, la media mobile è l'unico modello ufficiale di determinazione costi disponibile in Supply Chain Management. Sebbene la media corrente non sia un modello di determinazione costi ufficiale, è la tecnica utilizzata quando si utilizza un modello di determinazione dei costi periodico come FIFO, LIFO o media ponderata. Il termine media con valore oscillante non viene utilizzato in Supply Chain Management e potrebbe avere connotazioni diverse in altri sistemi.

### <a name="how-can-i-accommodate-the-difference-between-the-product-receipt-price-and-invoice-price-when-i-use-moving-average"></a>Come posso compensare la differenza tra il prezzo di entrata prodotto e il prezzo della fattura quando utilizzo la media mobile?

Quando si utilizza la media mobile, il costo fisico (prezzo di entrata) viene utilizzato per calcolare la media mobile per tutte le transazioni di uscita. Se c'è una differenza tra il costo fisico (prezzo di entrata) e il costo finanziario (prezzo fattura), il sistema registra automaticamente la differenza sul conto principale specificato per il tipo di registrazione **Differenza di prezzo per media mobile** sulla scheda **Inventario** della pagina **Profilo di registrazione inventario**.

### <a name="where-is-the-price-difference-for-moving-average-presented-in-the-general-ledger"></a>Dov'è la differenza di prezzo per la media mobile presentata nella contabilità generale?

Quando c'è una differenza di prezzo tra la registrazione di un aggiornamento fisico e un aggiornamento finanziario per un'entrata, la differenza viene registrata nel conto principale specificato per il tipo di registrazione **Differenza di prezzo per media mobile** sulla scheda **Inventario** della pagina **Profilo di registrazione inventario**. Per ulteriori informazioni, vedere [Media mobile](moving-average.md).

### <a name="when-i-use-moving-average-what-happens-if-there-is-an-issue-before-the-receipt"></a>Quando utilizzo la media mobile, cosa succede se si verifica un'uscita prima dell'entrata?

In genere, potrebbe verificarsi un'uscita prima dell'entrata perché si autorizzano scorte fisiche negative per il gruppo di modelli di articoli o perché l'uscita è retrodatata. Per ulteriori informazioni, vedi la sezione [Inventario negativo](#negative-inventory) descritta in questo articolo.

Se stai retrodatando le transazioni, ti consigliamo di considerare attentamente il processo e le operazioni aziendali per determinare se esiste un modo per evitare questo scenario. Se si retrodata una transazione per un articolo che utilizza la media mobile, il sistema assegnerà la media mobile corrente alla transazione. Le uscite successive non vengono rettificate. Per ulteriori informazioni sulla media mobile con transazioni retrodatate, vedi [Media mobile](moving-average.md).

### <a name="standard-costing"></a>Determinazioni costi standard

### <a name="what-is-the-difference-between-standard-costing-and-fixed-receipt-price"></a>Qual è la differenza tra il costo standard e il prezzo di entrata fisso?

La determinazione dei costi standard richiede la definizione di un prezzo dell'articolo e l'attivazione del costo in una versione di determinazione costi. Tale costo viene utilizzato per tutte le entrate e le uscite. Gli scostamenti per le entrate in magazzino vengono registrati nella contabilità generale utilizzando i conti di scostamento costi standard specificati nella scheda **Costo standard** della pagina **Profilo di registrazione dell'inventario**.

Tuttavia, quando si utilizza il prezzo di ricevimento fisso, viene fisso solo il costo per i ricevimenti e il sistema utilizza il costo specificato nella scheda dettaglio **Gestione costi** della pagina **Prodotto rilasciato**. Le differenze tra il costo predefinito e il prezzo dell'ordine fornitore comportano la registrazione dello scostamento del prezzo di acquisto nei conti profitti e perdite del prezzo di entrata fisso. Le uscite non utilizzano il prezzo di entrata fisso. Al contrario, le uscite verranno valutate in base alla media corrente al momento della registrazione (a meno che non si utilizzi il contrassegno) e verranno rivalutate in base al modello euristico selezionato quando si esegue la chiusura dell'inventario.

### <a name="can-i-use-fefo-reservations-with-standard-costing"></a>Posso utilizzare le prenotazioni FEFO con i costi standard?

Sì, puoi utilizzare le prenotazioni FEFO su un gruppo di modelli di articoli quando selezioni la determinazione dei costi standard. Le prenotazioni FEFO controllano la logica di prenotazione utilizzata per la gestione fisica degli articoli, mentre la determinazione dei costi standard controlla il costo fisico e finanziario di un articolo.

### <a name="can-i-upload-pending-prices"></a>Posso caricare i prezzi in sospeso?

Sì, puoi utilizzare il componente aggiuntivo Excel o il Data Management Framework per caricare un prezzo in sospeso. Ti consigliamo di utilizzare le seguenti entità:

- Prezzi articoli in sospeso (V2)
- Costi unitari della categoria costi del ciclo di lavorazione in sospeso
- Fattori di calcolo nodo di scheda di determinazione costi (V2)

### <a name="how-often-can-i-update-the-standard-cost-for-an-item"></a>Con quale frequenza posso aggiornare il costo standard di un articolo?

Non c'è limite alla frequenza per attivare un nuovo costo standard. Se attivi un nuovo costo per un articolo lo stesso giorno in cui è stato attivato l'ultimo costo, il sistema utilizzerà il costo attivato più recente su nuove transazioni o aggiornamenti (come aggiornamenti alle transazioni esistenti).

### <a name="can-i-deactivate-or-delete-an-activated-cost"></a>Posso disattivare o eliminare un costo attivato?

No, non puoi disattivare o eliminare un costo attivato. Se hai attivato un costo in modo errato, puoi attivare un nuovo costo con il costo corretto.

### <a name="are-calculation-groups-used-with-standard-costing"></a>I gruppi di calcolo vengono utilizzati con la determinazione dei costi standard?

I gruppi di calcolo possono essere utilizzati con qualsiasi articolo, indipendentemente dal gruppo di modelli di articoli scelto. I gruppi di calcolo vengono utilizzati durante il processo di rollup dei costi o di calcolo dei costi per determinare le impostazioni da utilizzare per gli articoli per i quali si esegue il calcolo. Per ulteriori informazioni sui gruppi di calcolo, vedi [Gruppi di calcoli DBA](bom-calculation-groups.md).

### <a name="when-should-i-use-a-planned-costing-version"></a>Quando dovrei utilizzare una versione di determinazione dei costi pianificata?

Le versioni di determinazione costi possono avere un tipo di *Costo standard* o *Costo pianificato*. Il tipo *Costo standard* viene utilizzato per i costi attivi nel sistema e che verranno registrati nelle transazioni. Il tipo *Costo pianificato* viene utilizzato per eseguire simulazioni sui costi e non influisce sul costo delle transazioni.

### <a name="can-the-total-cost-from-one-entity-be-transferred-to-another-entity-as-the-selling-cost"></a>Il costo totale di un'entità può essere trasferito a un'altra entità come costo di vendita?

Non esiste un modo automatizzato per copiare i costi da un'azienda all'altra. Inoltre, non esiste un modo automatizzato per copiare i costi da un prezzo di acquisto a un prezzo di vendita. Se la tua organizzazione deve completare una di queste attività, valuta se puoi utilizzare Data Management Framework per esportare i dati dalla tua versione di determinazione dei costi e caricarli in un'altra società, come prezzo di vendita nella versione di determinazione dei costi o come accordo commerciale. Potrebbe essere necessaria la manipolazione manuale dei file.

### <a name="what-is-the-best-way-to-copy-planned-costs-to-a-standard-costing-version"></a>Qual è il modo migliore per copiare i costi pianificati in una versione di determinazione costi standard?

Puoi usare il pulsante **Copia** sulla pagina **Versioni di determinazione costi** per copiare i prezzi degli articoli, i prezzi delle categorie di costo o i costi indiretti da una versione di determinazione costi a un'altra.
