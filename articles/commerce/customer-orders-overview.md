---
title: Ordini cliente in POS
description: In questo argomento vengono fornite informazioni sugli ordini cliente in POS. Gli ordini cliente sono anche noti come ordini speciali. Questo argomento include una discussione sui parametri e i flussi di transazioni correlati.
author: josaw1
ms.date: 08/02/2021
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: RetailFunctionalityProfile
audience: Application User
ms.reviewer: josaw
ms.custom:
- "260594"
- intro-internal
ms.assetid: 6fc835ef-d62e-4f23-9d49-50299be642ca
ms.search.region: global
ms.search.industry: Retail
ms.author: anpurush
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: 9ebdad47d761f775cf26666dc3e2736818fb4832
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2022
ms.locfileid: "7982820"
---
# <a name="customer-orders-in-point-of-sale-pos"></a>Ordini cliente in POS

[!include [banner](includes/banner.md)]

In questo argomento vengono fornite informazioni su come creare e gestire ordini cliente nell'app POS. Gli ordini cliente possono essere utilizzati per acquisire le vendite in cui gli acquirenti desiderano ritirare i prodotti in un secondo momento, ritirare i prodotti in una posizione diversa o ricevere gli articoli spediti. 

In un mondo commerciale omni-canale, molti rivenditori offrono l'opzione degli ordini cliente, o ordini speciali, per soddisfare vari requisiti di prodotti ed evasione. Di seguito sono riportati alcuni scenari comuni:

- Un cliente desidera che i prodotti siano consegnati a un indirizzo specifico in una data specifica.
- Un cliente desidera prelevare i prodotti da un punto vendita o da una posizione diversa dal punto vendita o posizione in cui il cliente ha acquisito i prodotti.
- Un cliente all'interno di un punto vendita desidera ordinare i prodotti oggi e ritirarli nello stesso punto vendita in un secondo momento.

I rivenditori possono utilizzare gli ordini cliente anche per ridurre al minimo le vendite perse che l'esaurimento delle scorte potrebbero causare altrimenti, poiché la merce può essere consegnata o prelevata in una data o in una località diversa.

## <a name="set-up-customer-orders"></a>Impostare gli ordini cliente
Prima di provare a utilizzare la funzionalità di ordine cliente in POS, assicurarsi di completare tutte le configurazioni richieste in Commerce headquarters.

### <a name="configure-modes-of-delivery"></a>Configurare le modalità di consegna

Per utilizzare gli ordini cliente è necessario configurare le modalità di consegna che il canale del punto vendita può utilizzare. È necessario definire almeno una modalità di consegna che può essere utilizzata quando le righe ordine vengono spedite a un cliente da un punto vendita. È necessario anche definire almeno una modalità di prelievo di consegna che può essere utilizzata quando le righe ordine vengono prelevate dal punto vendita. Le modalità di consegna sono definite nella pagina **Modalità di consegna** in Commerce headquarters. Per altre informazioni su come configurare le modalità di consegna per i canali Commerce, vedere [Definire le modalità di consegna](./configure-call-center-delivery.md#define-delivery-modes).

![Pagina Modalità di consegna.](media/customer-order-modes-of-delivery.png)


### <a name="set-up-fulfillment-groups"></a>Impostare gruppi di evasione

Alcuni punti vendita o ubicazioni di magazzino potrebbero non essere in grado di evadere gli ordini cliente. Configurando i gruppi di evasione, un'organizzazione può specificare quali negozi e ubicazioni di magazzino vengono mostrati come opzioni agli utenti che creano ordini cliente in POS. I gruppi di evasione sono configurati nella pagina **Gruppi di evasione**. Le organizzazioni possono creare tutti i gruppi di evasione di cui hanno bisogno. Dopo aver definito un gruppo di evasione ordini, collegalo a un punto vendita selezionando **Assegnazione del gruppo di evasione** nella scheda **Impostazione** nel riquadro azioni della pagina **Punti vendita**.

In Commerce versione 10.0.12 e successive, le organizzazioni possono definire se le combinazioni magazzino o magazzino e punto vendita definite nei gruppi di evasione ordini possono essere utilizzate per la spedizione, per il prelievo o sia per la spedizione che per il prelievo. Ciò consente una maggiore flessibilità per l'azienda nel determinare quali magazzini possono essere selezionati durante la creazione di un ordine cliente per gli articoli da spedire rispetto a quali punti vendita possono essere selezionati quando si crea un ordine cliente per gli articoli da ritirare. Per usare queste opzioni di configurazione, attiva la funzionalità **Possibilità di specificare le ubicazioni come "Spedizione" o "Ritiro" abilitata nel gruppo di evasione**. Se un magazzino collegato a un gruppo di evasione ordini non è un punto vendita, può essere configurato solo come ubicazione di spedizione. Non può essere utilizzato quando gli ordini per il ritiro sono configurati in POS.

![Pagina Gruppi di evasione.](media/customer-order-fulfillment-group.png)

### <a name="configure-channel-settings"></a>Configurare impostazioni di canale

Quando si lavora con gli ordini clienti in POS, è necessario considerare alcune delle impostazioni del canale del punto vendita. Queste impostazioni si trovano nella pagina **Punti vendita** in Commerce headquarters.

- **Magazzino** - Questo campo indica il magazzino che verrà utilizzato quando si decrementa l'inventario per cash and carry e gli ordini di ritiro dei clienti legati a questo negozio. Come procedura consigliata, incoraggiamo l'uso di magazzini univoci per ogni canale di negozio, per evitare problemi di logica aziendale in conflitto tra i negozi.
- **Magazzino di spedizione** - Questo campo indica il magazzino che verrà utilizzato quando si decrementa l'inventario per gli ordini cliente da spedire al negozio selezionato. Se la funzionalità **Possibilità di specificare le ubicazioni come "Spedizione" o "Ritiro" abilitata nel gruppo di evasione** è stato abilitata nel tuo ambiente, gli utenti POS possono scegliere un magazzino specifico da cui spedire in POS, invece di scegliere un negozio da cui spedire. Pertanto, quando questa funzione è abilitata, il magazzino di spedizione non viene più utilizzato, poiché l'utente sceglierà il magazzino specifico da cui spedire l'ordine al momento della creazione dell'ordine.
- **Assegnazione del gruppo di evasione** - Selezionare questo pulsante (nella scheda **Impostazione** del riquadro azioni) per collegare i gruppi di evasione ordini a cui si fa riferimento e mostrare le opzioni per le ubicazioni di prelievo o le origini della spedizione quando gli ordini dei clienti vengono creati in POS.
- **Utilizza imposta basata su destinazione** - Questa opzione indica se l'indirizzo di spedizione viene utilizzato per determinare il gruppo imposte applicato alle righe ordine spedite all'indirizzo del cliente.
- **Utilizza imposta basata su cliente** - Questa opzione indica se il gruppo imposte definito per l'indirizzo di consegna del cliente viene utilizzato per tassare gli ordini dei clienti creati in POS per la spedizione all'indirizzo del cliente.

![Impostazione del canale del punto vendita nella pagina Punti vendita.](media/customer-order-all-stores.png)

### <a name="set-up-customer-order-parameters"></a>Impostare i parametri degli ordini cliente

Prima di provare a creare ordini cliente in POS, è necessario configurare i parametri appropriati in Commerce headquarters. Questi parametri possono essere trovati nella scheda **Ordini cliente** della pagina **Parametri di commercio**.

- **Tipo di ordine predefinito** - È possibile specificare il tipo di ordine assegnato per impostazione predefinita agli ordini cliente creati in POS. Questi ordini cliente possono essere ordini di vendita o ordini di offerta. Indipendentemente dal tipo di ordine predefinito, gli utenti possono comunque creare ordini di vendita e ordini cliente in POS.
- **Percentuale di deposito predefinita** - Specificare la percentuale dell'importo totale dell'ordine che il cliente deve pagare come deposito prima che un ordine possa essere confermato. A seconda dei privilegi, le filiali del punto vendita potrebbero essere in grado di sostituire l'importo utilizzando l'operazione **Sostituzione deposito** in POS, se tale operazione è configurata per il layout della schermata della transazione.
- **Modalità di prelievo per consegna** - Specificare la modalità di consegna da applicare alle righe dell'ordine di vendita configurate per il ritiro in POS.
- **Esegui modalità di consegna** - Specificare la modalità di consegna da applicare alle righe ordine di vendita che sono considerate righe ordine di esecuzione quando viene creato un carrello misto, in cui alcune righe verranno prelevate o spedite e altre righe verranno eseguite immediatamente dal cliente.
- **Percentuale spese di annullamento** - se un addebito viene applicato quando un ordine cliente viene annullato, specificare l'importo dell'addebito.
- **Codice di spese di annullamento** - Specificare il codice di spese della contabilità clienti da utilizzare quando viene applicato una spesa di annullamento agli ordini cliente annullati tramite POS. Il codice di spese definisce la logica di registrazione finanziaria per la spesa di annullamento.
- **Codice di spese di spedizione** - Se l'opzione **Utilizza addebiti automatici avanzati** è impostata su **Sì**, questa impostazione del parametro non ha effetto. Se questa opzione è impostata su **No**, agli utenti verrà richiesto di inserire manualmente una spesa di spedizione quando creano gli ordini cliente in POS. Utilizzare questo parametro per mappare un codice di spese della contabilità clienti che verrà applicato agli ordini quando gli utenti inseriscono una spesa di spedizione. Il codice di spese definisce la logica di registrazione finanziaria per la spesa di spedizione.
- **Utilizza addebiti automatici avanzati** - Impostare questa opzione su **Sì** per utilizzare gli addebiti automatici calcolati dal sistema quando gli ordini cliente vengono creati in POS. Questi addebiti automatici possono essere utilizzati per calcolare le spese di spedizione o altre spese specifiche per ordine o articolo. Per ulteriori informazioni su come impostare e usare le spese automatiche avanzate, vedere [Spese automatiche avanzate omnicanale](./omni-auto-charges.md).

![Scheda Ordini cliente nella pagina Parametri di commercio.](media/customer-order-parameters.png)

### <a name="update-transaction-screen-layouts-in-pos"></a>Aggiornare i layout delle schermate delle transazioni in POS

Assicurarsi che il [layout dello schermo](./pos-screen-layouts.md) in POS sia configurato per supportare la creazione e la gestione degli ordini cliente e che tutte le operazioni POS richieste siano configurate. Ecco alcune delle operazioni POS consigliate per supportare correttamente la creazione e la gestione degli ordini cliente:
- **Spedisci tutti i prodotti** - Questa operazione viene utilizzata per specificare che tutte le righe nel carrello delle transazioni verranno spedite a una destinazione.
- **Spedisci prodotti selezionati** - Questa operazione viene utilizzata per specificare che le righe selezionate nel carrello delle transazioni verranno spedite a una destinazione.
- **Preleva tutti i prodotti** - Questa operazione viene utilizzata per specificare che tutte le righe nel carrello delle transazioni verranno prelevate da un'ubicazione selezionata del punto vendita.
- **Preleva prodotti selezionati** - Questa operazione viene utilizzata per specificare che le righe selezionate nel carrello delle transazioni verranno prelevate da un'ubicazione selezionata del punto vendita.
- **Esegui tutti i prodotti** - Questa operazione viene utilizzata per specificare che verranno eseguite tutte le righe nel carrello delle transazioni. Se questa operazione viene utilizzata in POS, l'ordine cliente verrà convertito in una transazione cash and carry.
- **Esegui prodotti selezionati** - Questa operazione viene utilizzata per specificare che le righe selezionate nel carrello delle transazioni vengono eseguite dal cliente al momento dell'acquisto. Questa operazione è utile solo in uno scenario di [ordine ibrido](./hybrid-customer-orders.md).
- **Richiama ordine** - Questa operazione viene utilizzata per cercare e recuperare gli ordini cliente in modo che gli utenti POS possano modificare, annullare o eseguire operazioni relative all'evasione degli ordini come richiesto.
- **Modifica modalità di consegna** - Questa operazione può essere utilizzata per modificare rapidamente la modalità di consegna per le righe già configurate per la spedizione, senza richiedere che gli utenti eseguano nuovamente il flusso "Spedisci tutti i prodotti" o "Spedisci prodotti selezionati".
- **Sostituzione deposito** - Questa operazione può essere utilizzata per modificare l'importo del deposito che il cliente pagherà per l'ordine cliente selezionato.

![Operazioni nella schermata delle transazioni POS.](media/customer-order-screen-layout.png)

## <a name="work-with-customer-orders-in-pos"></a>Utilizzare gli ordini cliente in POS

> [!NOTE]
> La funzionalità di riconoscimento dei ricavi non è attualmente supportata per l'utilizzo nei canali di Commerce (e-commerce, POS, servizio clienti). Gli articoli configurati con il riconoscimento dei ricavi non devono essere aggiunti agli ordini creati nei canali di Commerce. 

### <a name="create-a-customer-order-for-products-that-will-be-shipped-to-the-customer"></a>Creare un ordine cliente per i prodotti che verranno spediti al cliente

1. Nella schermata della transazione POS, aggiungere un cliente alla transazione.
2. Aggiungere prodotti al carrello.
3. Selezionare **Spedizione selezionata** o **Spedisci tutto** per spedire i prodotti a un indirizzo sul conto cliente.
4. Selezionare l'opzione per creare un ordine cliente.
5. Confermare o modificare l'ubicazione in "Spedisci da", confermare o modificare l'indirizzo di spedizione e selezionare un metodo di spedizione.
6. Immettere la data di spedizione dell'ordine desiderata dal cliente.
7. Utilizzare le funzioni di pagamento per pagare gli importi calcolati dovuti oppure utilizzare l'operazione **Sostituzione deposito** per modificare gli importi dovuti e quindi applicare il pagamento.
8. Se il totale dell'ordine non è stato pagato, inserire una carta di credito che verrà acquisita per il saldo dovuto sull'ordine quando verrà fatturato.

### <a name="create-a-customer-order-for-products-that-the-customer-will-pick-up"></a>Creare un ordine cliente per i prodotti che verranno prelevati dal cliente

1. Nella schermata della transazione POS, aggiungere un cliente alla transazione.
2. Aggiungere prodotti al carrello.
3. Seleziona **Prelievo selezionato** o **Preleva tutto** per avviare la configurazione del prelievo dell'ordine.
4. Selezionare l'ubicazione del punto vendita dal quale il cliente preleverà i prodotti selezionati.
5. Seleziona la data in cui l'articolo verrà ritirato.
6. Utilizzare le funzioni di pagamento per pagare gli importi calcolati dovuti oppure utilizzare l'operazione **Sostituzione deposito** per modificare gli importi dovuti e quindi applicare il pagamento.
7. Se il totale dell'ordine non è stato pagato per intero, seleziona se il cliente fornirà il pagamento in un secondo momento (al ritiro) o se una carta di credito verrà inserita ora, quindi utilizzata e acquisita al momento del ritiro.

### <a name="edit-an-existing-customer-order"></a>Modificare un ordine cliente esistente

Gli ordini al dettaglio creati nel canale online o in negozio possono essere richiamati e modificati tramite POS secondo necessità.

> [!IMPORTANT]
> Non tutti gli ordini di vendita al dettaglio possono essere modificati tramite l'applicazione POS. Gli ordini creati in un canale del call center non possono essere modificati tramite POS se l'impostazione [Attiva completamento ordine](./set-up-order-processing-options.md#enable-order-completion) è attivata per il canale del call center. Per garantire una corretta elaborazione dei pagamenti, gli ordini originati in un canale del call center e che utilizzano la funzionalità Abilita completamento ordine devono essere modificati tramite l'applicazione del call center in Commerce headquarters.

> [!NOTE]
> Si consiglia di non modificare ordini e preventivi in POS creati da un utente non del servizio clienti in Commerce headquarters. Tali ordini e preventivi non utilizzano il motore di determinazione dei prezzi di Commerce, quindi se vengono modificati in POS, il motore di determinazione dei prezzi di Commerce ne aggiorna il prezzo.


Nella versione 10.0.17 e successive, gli utenti possono modificare gli ordini idonei tramite l'applicazione POS, anche se l'ordine è parzialmente evaso. Tuttavia, gli ordini completamente fatturati non possono ancora essere modificati tramite POS. Per abilitare questa capacità attiva la funzionalità **Modificare gli ordini parzialmente evasi nel punto vendita** nell'area di lavoro **Gestione funzionalità**. Se questa funzione non è abilitata o se stai utilizzando la versione 10.0.16 o precedente, gli utenti potranno modificare gli ordini cliente nel POS solo se l'ordine è completamente aperto. Inoltre, se la funzione è abilitata, puoi limitare i punti vendita che possono modificare gli ordini parzialmente evasi. L'opzione per disabilitare questa funzionalità per punti vendita specifici può essere configurata tramite il **Profilo funzionalità** nella scheda dettaglio **Generale**.


1. Selezionare **Richiama ordine**.
2. Usare **Cerca** per inserire filtri per trovare l'ordine, quindi selezionare **Applica**.
3. Selezionare l'ordine nell'elenco dei risultati, quindi selezionare **Modifica**. Se il pulsante **Modifica** non è disponibile, l'ordine è in uno stato in cui non può essere modificato.
4. Dal carrello delle transazioni, apportare le modifiche necessarie all'ordine cliente. Alcuni cambiamenti potrebbero non essere consentiti durante la modifica.
5. Completare il processo di modifica selezionando un'operazione di pagamento.
6. Per uscire dal processo di modifica senza salvare le modifiche, puoi utilizzare l'operazione **Annulla transazione**.

#### <a name="pricing-impact-when-orders-are-edited"></a>Impatto sui prezzi quando gli ordini vengono modificati

Quando gli ordini vengono effettuati in POS o in un sito di e-commerce di Commerce, i clienti accettano un importo. Questo importo include un prezzo e potrebbe anche includere uno sconto. Un cliente che effettua un ordine e successivamente contatta il servizio clienti per modificare tale ordine (ad esempio per aggiungere un altro articolo) avrà aspettative specifiche sull'applicazione degli sconti. Anche se le promozioni sulle righe di ordine esistenti sono scadute, il cliente si aspetterà che gli sconti originariamente applicati a tali righe rimangano in vigore. Tuttavia, se nessun sconto era in vigore quando l'ordine è stato originariamente effettuato, ma in seguito è entrato in vigore uno sconto, il cliente si aspetterà che il nuovo sconto venga applicato all'ordine modificato. In caso contrario, il cliente potrebbe semplicemente annullare l'ordine esistente e quindi creare un nuovo ordine a cui viene applicato il nuovo sconto. Come mostra questo scenario, prezzi e sconti che i clienti hanno accettato devono essere mantenuti. Allo stesso tempo, gli utenti di POS e del servizio clienti devono avere la possibilità di ricalcolare i prezzi e gli sconti per le righe dell'ordine di vendita come necessario.

Quando gli ordini vengono richiamati e modificati in POS, i prezzi e gli sconti delle righe di ordini esistenti sono considerati "bloccati". In altre parole, non cambiano, anche se alcune righe di ordine vengono cancellate o modificate, o se vengono aggiunte nuove righe di ordine. Per modificare i prezzi e gli sconti delle righe di vendita esistenti, l'utente POS deve selezionare **Ricalcola**. Il blocco del prezzo viene quindi rimosso dalle righe di ordine esistenti. Tuttavia, prima del rilascio della versione 10.0.21 di Commerce, questa funzionalità non era disponibile nel servizio clienti. Qualsiasi modifica alle righe di ordine ha invece comportato il ricalcolo di prezzi e sconti.

Nella versione 10.0.21 di Commerce, una nuova funzionalità denominata **Impedisci calcolo non intenzionale dei prezzi per ordini commerciali** è disponibile nell'area di lavoro **Gestione funzionalità**. Per impostazione predefinita, questa funzionalità è attivata. Quando è attivata, una nuova proprietà **Prezzo bloccato** è disponibile per tutti gli ordini e-commerce. Una volta completata l'acquisizione degli ordini effettuati da qualsiasi canale, questa proprietà viene automaticamente abilitata (ovvero, la casella di controllo è selezionata) per tutte le righe di ordine. Il motore di determinazione dei prezzi di Commerce esclude quindi tali righe di ordine da tutti i calcoli di prezzi e sconti. Pertanto, se l'ordine viene modificato, le righe verranno escluse dal calcolo di prezzi e sconti per impostazione predefinita. Tuttavia, gli utenti del servizio clienti possono disabilitare la proprietà (ovvero deselezionare la casella di controllo) per qualsiasi riga di ordine e quindi selezionare **Ricalcola** per includere le righe di ordine esistenti nei calcoli dei prezzi.

Anche quando applicano uno sconto manuale a una riga di vendita esistente, gli utenti del servizio clienti devono disabilitare la proprietà **Prezzo bloccato** della riga di vendita prima di applicare lo sconto manuale.

Gli utenti del servizio clienti possono anche disabilitare la proprietà **Prezzo bloccato** per le righe di ordine in blocco selezionando **Rimuovi blocco prezzo** nel gruppo **Calcola** della scheda **Vendi** nel riquadro azioni della pagina **Ordine cliente**. In questo caso, il blocco del prezzo viene rimosso da tutte le righe di ordine eccetto le righe che non sono modificabili (in altre parole, le righe il cui stato è **Fatturato parzialmente** o **Fatturato**). Quindi, dopo che le modifiche all'ordine sono state completate e inviate, il blocco del prezzo viene riapplicato a tutte le righe di ordine.

> [!IMPORTANT]
> Quando la funzionalità **Impedisci calcolo non intenzionale dei prezzi per ordini commerciali** è attivata, l'impostazione della valutazione dell'accordo commerciale verrà ignorata nei flussi di lavoro dei prezzi. In altre parole, le finestre di dialogo della valutazione dell'accordo commerciale non mostreranno la sezione **Relativo al prezzo**. Questo comportamento si verifica perché lo scopo dell'impostazione di valutazione dell'accordo commerciale e della funzionalità di blocco del prezzo è simile: impedire modifiche non intenzionali dei prezzi. Tuttavia, l'esperienza utente per la valutazione dell'accordo commerciale non si adatta agli ordini di grandi dimensioni in cui gli utenti devono selezionare una o più righe di ordine per il ricalcolo dei prezzi.

> [!NOTE]
> La proprietà **Prezzo bloccato** può essere disabilitata per una o più righe selezionate solo quando si utilizza il modulo **Servizio clienti**. Il comportamento del POS rimane invariato. In altre parole, l'utente POS non può sbloccare i prezzi per le righe di ordine selezionate. Tuttavia, può selezionare **Ricalcola** per rimuovere il blocco del prezzo da tutte le righe di ordine esistenti.

### <a name="cancel-a-customer-order"></a>Annullare un ordine cliente

1. Selezionare **Richiama ordine**.
2. Usare **Cerca** per inserire filtri per trovare l'ordine, quindi selezionare **Applica**.
3. Selezionare l'ordine nell'elenco dei risultati, quindi selezionare **Annulla**. Se il pulsante **Annulla** non è disponibile, l'ordine è in uno stato in cui non può essere più annullato.
4. Se sono configurate spese di annullamento, confermarle. È possibile modificare le spese di annullamento prima di confermarle, come necessario. 
5. Dal carrello delle transazioni, completare il processo di annullamento selezionando un'operazione di pagamento. Se i depositi pagati superano la spesa di annullamento, potrebbe essere dovuto il rimborso.
6. Per uscire dal processo di annullamento senza salvare le modifiche, puoi utilizzare l'operazione **Annulla transazione**.

## <a name="finalizing-the-customer-order-shipment-or-pickup-from-pos"></a>Finalizzare la spedizione dell'ordine cliente o il ritiro dal POS

Dopo aver creato un ordine, gli articoli verranno ritirati dal cliente in un punto vendita o spediti, a seconda della configurazione dell'ordine. Per ulteriori informazioni su questo processo, vedere la documentazione sull'[evasione degli ordini del punto vendita](./order-fulfillment-overview.md).

## <a name="asynchronous-transaction-flow-for-customer-orders"></a>Flusso asincrono della transazione per gli ordini cliente

Gli ordini cliente possono essere creati in POS in modalità sincrona o in modalità asincrona. Se si notano problemi di prestazioni o ritardi degli utenti quando si creano gli ordini cliente in POS, valutare la possibilità di attivare la creazione di ordini asincroni.

### <a name="enable-customer-orders-to-be-created-in-asynchronous-mode"></a>Abilitare la creazione degli ordini cliente in modalità asincrona

1. In Commerce headquarters, nella pagina **Profili funzionalità** selezionare il profilo funzionalità che corrisponde al punto vendita che si desidera configurare.
2. Nella Scheda dettaglio **Generale** , impostare l'opzione **Crea ordine cliente in modalità asincrona** su **Sì**.

Quando l'opzione **Crea ordine cliente in modalità asincrona** è impostata su **Sì**, ordini cliente vengono creati sempre in modalità asincrona, anche se Retail Transaction Service (RTS) è disponibile. Se si imposta questa opzione su **No**, ordini cliente vengono creati sempre in modalità sincrona utilizzando RTS. Quando gli ordini cliente vengono creati in modalità asincrona, vengono estratti e creati come transazioni di vendita al dettaglio in Commerce headquarters dai processi Pull (P) di Commerce. Gli ordini cliente corrispondenti per le transazioni di vendita al dettaglio vengono creati quando **Sincronizza ordini** viene eseguito manualmente o tramite un processo batch.

## <a name="additional-resources"></a>Risorse aggiuntive

[Ordini cliente ibridi](hybrid-customer-orders.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
