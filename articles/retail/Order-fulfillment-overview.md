---
title: Panoramica dell'evasione ordine presso il punto vendita
description: In questo argomento viene fornita una panoramica dell'evasione ordine del punto vendita.
author: rubencdelgado
manager: AnnBe
ms.date: 10/30/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.search.scope: 
ms.search.region: Global
ms.author: rubencdelgado
ms.search.validFrom: 2017-10-30
ms.dyn365.ops.version: 
ms.translationtype: HT
ms.sourcegitcommit: ec6cb212766dd90fa9db7719a2119419ecb935c7
ms.openlocfilehash: e0aa0e576f88fd497472aa4141704a66d51605c3
ms.contentlocale: it-it
ms.lasthandoff: 12/20/2017

---

# <a name="store-order-fulfillment"></a>Evasione ordine del punto vendita

Molti rivenditori vorrebbero ottimizzare l'evasione dell'ordine consentendo ai punti vendita di eseguire gli ordini. L'evasione degli ordini a livello di punto vendita può semplificare gli scenari di scorte in eccesso per un punto vendita specifico o potrebbe essere necessaria da un punto di vista logistico nei casi in cui un punto vendita disponga di capacità aggiuntiva o si trovi a una distanza di spedizione più vicina al cliente. Per rispondere a questa esigenza, un'operazione di evasione degli ordini unificata è disponibile presso il POS.

Negli ordini per l'evasione presso un punto vendita specifico, il magazzino del negozio è indicato sull'intestazione o sulle righe dell'ordine. 

L'operazione di evasione dell'ordine presso il POS offre una singola area di lavoro nel POS che può essere utilizzata per elaborare gli ordini. Ciò include tutte le operazioni, dall'accettazione dell'ordine, al contrassegno come spedito o all'avvio del ritiro del presso il punto vendita. 

## <a name="access-unified-order-fulfillment-in-the-point-of-sale"></a>Accedere all'evasione dell'ordine unificato nel POS

L'evasione ordini, [ID operazione 928](https://docs.microsoft.com/en-us/dynamics365/unified-operations/retail/pos-operations), può essere utilizzata per accedere all'area di lavoro per l'evasione degli ordini del POS. 

L'operazione di evasione degli ordini non dispone di propria autorizzazione immediatamente disponibile, ma in futuro, gli utenti saranno in grado di utilizzare l'autorizzazione **Consenti recupero ordine** per richiamare l'operazione dal POS.

A livello di punto vendita, un'impostazione di configurazione è disponibile per determinare se la riga dell'ordine deve essere accettata manualmente dal POS. Se tale opzione di configurazione non è impostata, le righe ordine verranno accettate per impostazione predefinita. Se tale opzione di configurazione è abilitata, gli utenti nel POS dovranno selezionare l'autorizzazione **Consenti accettazione ordine** per accettare gli ordini dal POS.
Le righe ordine possono inoltre essere rifiutate dal POS. Rifiutare una riga ordine significa che la riga non verrà evasa in quel punto vendita e che la riga d'ordine verrà inviata di nuovo per la riassegnazione a un altro punto vendita o magazzino. L'autorizzazione di rifiuto della riga ordine è assegnata tramite l'autorizzazione **Consenti rifiuto ordine**. 

## <a name="order-fulfillment-operation-parameters"></a>Parametri dell'operazione di evasione dell'ordine

L'evasione ordini fornisce parametri predefiniti che possono essere applicati all'operazione quando viene richiamata nel POS. Quando il parametro **Tutti gli ordini** è configurato, tutti gli ordini vengono mostrati quando l'operazione viene utilizzata. Il parametro **Ordini da spedire** mostra solo gli ordini che devono essere spediti dal punto vendita e **Ordini per prelievo** mostra gli ordini che verranno prelevati nel punto vendita. 

## <a name="orders-for-fulfillment"></a>Ordini per l'evasione

L'operazione di evasione dell'ordine mostra solo gli ordini che verranno prelevati o spediti dal punto vendita corrente. Gli ordini da evadere per altri POS non vengono elencati quando si utilizza l'operazione di evasione degli ordini. 

## <a name="line-selection"></a>Selezione delle righe

Le righe possono essere selezionate mediante la funzione **Seleziona** nel riquadro azioni. Se **Seleziona** è attivata, più righe possono essere selezionate per l'elaborazione. È possibile rimuovere le righe selezionate facendo clic sulla stessa riga di nuovo. 

## <a name="line-details"></a>Dettagli riga

I dettagli riga possono essere visualizzati mediante il menu a comparsa dei dettagli riga. Quando questo menu viene utilizzato, vengono fornite due schede per mostrare informazioni aggiuntive per la riga selezionata. La prima scheda **Dettagli riga** mostra i dettagli per la riga stessa, ad esempio quantità ordinata e rimanente. Vengono forniti dettagli aggiuntivi inclusi la quantità prelevata, imballata e fatturata nonché le modalità di consegna e all'indirizzo di consegna. La scheda **Dettagli ordini** fornisce informazioni di intestazione ordine inclusi il cliente, l'ID del cliente, il numero di ordine, il totale dell'ordine e il saldo.

Se più righe sono selezionate, il menu a comparsa dettagli riga di ordine indicherà solo che sono selezionate più righe. Per visualizzare i dettagli di una singola riga, rimuovere le righe finché rimane una sola riga. 

## <a name="pending-order-lines"></a>Righe ordine in sospeso

L'evasione ordine unificata include la possibilità di accettare manualmente gli ordini. Per impostazione predefinita, gli ordini per l'evasione presso il POS sono già accettati. Tuttavia, se i processi aziendali impongono che un lavoratore a livello di POS debba accettare gli ordini, l'accettazione manuale può essere attivata a livello di POS. Per consentire all'accettazione dell'ordine, andare a **Retail** > **Canali** > **Punti vendita al dettaglio** > **Tutti i punti vendita al dettaglio**. Aprire il punto vendita desiderato, quindi nella scheda **Generale** individuare l'intestazione secondaria **Evasione ordine**. Questa intestazione secondaria include un'opzione denominata **Accettazione manuale** configurata su **No** per impostazione predefinita. Impostando questa opzione su **Sì** e sincronizzando le modifiche nel database di canale, le righe di ordine possono essere elaborate tramite il processo di accettazione.

I lavoratori con autorizzazione **Consenti accettazione ordine** possono aprire l'evasione dell'ordine e selezionare le righe per l'accettazione. Una volta accettate le righe, il loro stato cambia da **In sospeso** ad **Accettato** e il resto del processo di evasione dell'ordine può procedere. Quando è attivata l'**Accettazione manuale** gli ordini non verranno elaborati fino a che non sono stati accettati. 

Gli ordini per il prelievo del punto vendita non hanno mai stato **In sospeso**. Questo per evitare uno scenario in cui un cliente arriva al POS e la riga dell'ordine non può essere elaborata perché un lavoratore con il privilegio appropriato non è disponibile.

## <a name="accepted-order-lines"></a>Righe ordine accettate

Gli ordini con stato della riga **Accettato** possono continuare con la parte restante del processo di evasione dell'ordine nel POS. Dopo che un ordine è stato accettato, qualsiasi azione rimanente può essere intrapresa per la riga dell'ordine. 

Ad esempio, una riga d'ordine accettata può essere selezionata e quindi prelevata direttamente senza passare per il prelievo e l'imballaggio.

## <a name="line-actions"></a>Azioni riga

### <a name="pick"></a>Preleva

La categoria di azioni **Prelievo** viene fornita a supporto del processo di prelievo delle righe ordine dai ripiani. L'azione di prelievo può essere eseguita solo nelle righe ordine in precedenza accettate. 

**Azione: Prelievo**

- Stato POS risultante: Prelievo
- Stato back office risultante: Nessuna modifica

Dopo che un ordine è stato accettato, le righe possono essere selezionate e contrassegnate come **Prelievo**. Contrassegnando una riga come **Prelievo** è possibile indicare che il lavoro di prelievo già stato eseguito su una riga. Questo impedisce a due lavoratori di tentare di selezionare le stesse righe di ordine contemporaneamente.  

**Azione: Stampa distinta di prelievo**

- Stato risultante: Prelievo
- Stato back office risultante: Nessuna modifica

Le distinte di prelievo possono essere stampate presso il POS per supportare i lavoratori nell'esecuzione del processo di prelievo. Una distinta di prelievo stampata può essere trasportata con il lavoratore che esegue il prelievo e mentre i prodotti vengono prelevati, l'operatore li contrassegnerà manualmente come selezionato nella distinta di prelievo. 

Il formato della distinta di prelievo è configurato in Dynamics 365 for Retail e aggiunto al profilo di ricevuta. Per ulteriori informazioni sulla configurazione dei profili di ricevute, vedere [Modelli e stampa di ricevute](https://docs.microsoft.com/en-us/dynamics365/unified-operations/retail/receipt-templates-printing)

Se le righe vengono selezionate e una distinta di prelievo viene stampata per le righe, queste vengono aggiornate automaticamente con stato **Prelievo**. 

**Azione: Contrassegna come prelevato**

- Stato risultante: Prelevato o Prelevato in parte
- Stato back office risultante: Prelevato o Prelevato in parte

Al termine del processo di prelievo fisico, le righe possono essere contrassegnate come **Prelevate**. Selezionando una riga e contrassegnandola come **Prelevata** si esegue una chiamata in tempo reale per aggiornare la riga dell'ordine in Dynamics 365 for Retail. Dopo che la riga è stata contrassegnata come **Prelevata** nel POS, anche lo stato di back office viene aggiornato come **Prelevato** e le transazioni di magazzino riflettono la quantità specificata come diminuita.

Se gli ordini vengono elaborati nel tempo, quantità parziali possono essere elaborate per una riga specifica. Se una riga viene selezionata e viene eseguita l'azione è **Contrassegna come prelevato** e la quantità è maggiore di uno, viene richiesto all'utente di specificare la quantità. La quantità rimanente da prelevare viene compilata automaticamente. Se viene specificata una quantità inferiore alla quantità rimanente, lo stato della riga diventa **Prelevato in parte**. Quando la riga dell'ordine viene aggiornata nel back office, rifletterà anche lo stato parzialmente prelevato e la quantità inserita dall'utente verrà utilizzata per l'aggiornamento dell'inventario. 

Se una riga ordine viene selezionata per errore, la procedura di annullamento deve essere eseguita sulla riga dell'ordine nel back office. Al momento non esiste alcuna azione di annullamento prelievo supportata presso il punto vendita. 

Le righe ordine di ordini diversi possono essere selezionate e contrassegnate come **Prelievo**, stampate sulla stessa distinta di prelievo o contrassegnate come **Prelevato**. 

### <a name="pack"></a>Imballa

Le righe ordine possono essere imballate in qualsiasi momento dopo che la riga ordine è stata accettata. 

**Azione: Stampa documento di trasporto**

- Stato risultante: Imballato o Imballato in parte
- Stato back office risultante: Consegnato o Consegnato in parte

Questa azione consente di contrassegnare le righe come imballate o parzialmente imballate e stampare un documento di trasporto. Un documento di trasporto può essere stampato per i prodotti che sono stati imballati insieme. Il formato del documento di trasporto è configurato in Dynamics 365 for Retail e aggiunto al profilo di ricevuta. Per ulteriori informazioni sulla configurazione dei profili di ricevute, vedere [Modelli e stampa di ricevute](https://docs.microsoft.com/en-us/dynamics365/unified-operations/retail/receipt-templates-printing)

**Azione: Contrassegna come imballato**

- Stato risultante: Imballato o Imballato in parte
- Stato back office risultante: Consegnato o Consegnato in parte

L'azione **Contrassegna come imballato** può essere utilizzata per indicare che le righe sono state imballate senza stampare un documento di trasporto. **Stampa documento di trasporto** e **Contrassegna come imballato** determinano transazioni di magazzino nel back office. Le righe d'imballaggio nel POS determineranno la generazione di giornali di documenti di trasporto nel back office. 

Se una riga ordine viene imballata per errore, il giornale di registrazione documenti di trasporto dovrà essere corretto nel back office. 

Solo le righe sullo stesso ordine e con la stessa modalità di consegna possono essere imballate contemporaneamente.

Attualmente, l'opzione per contrassegnare le righe di prelievo del POS come **Imballato** è disabilitata. La funzionalità verrà aggiunta in una versione successiva. Il processo di creazione del documento di trasporto verrà migliorato per supportare l'inserimento di informazioni di spedizione di terze parti nel processo del documento di trasporto.

### <a name="pick-up"></a>Preleva

Gli ordini per il prelievo presso il POS possono essere ritirati direttamente una volta recuperati nel POS. Gli ordini di prelievo presso il POS non sono soggetti ad accettazione. 

**Azione: Preleva**

- Stato risultante: Fatturato o Parzialmente fatturato
- Stato back office risultante: Fatturato o Parzialmente fatturato

Se una riga viene selezionata per il prelievo dall'evasione ordine unificata, l'intero ordine viene caricato nel POS e viene contrassegnata la quantità completa per la riga selezionata. Anche altre righe dell'ordine vengono caricate nella visualizzazione transazione del POS, ma con la quantità contrassegnata come zero. 

Dopo che le righe per il prelievo sono state caricate nella visualizzazione della transazione, la transazione può essere elaborata con il metodo solito. 

Le righe che sono state interamente fatturate tramite prelievo non verranno più visualizzate nell'elaborazione unificata degli ordini. Le righe che sono state parzialmente prelevate continueranno a comparire nell'evasione ordine unificata fino a quando non saranno state prelevate per intero. 

Se una riga viene prelevata per errore, è necessario eseguire un reso per correggere l'errore.  

Solo le righe sullo stesso ordine e con la stessa modalità di consegna possono essere prelevate contemporaneamente. 

### <a name="shipping"></a>Spedizione

Le righe ordine da spedire dal punto vendita possono essere elaborate nell'evasione ordine unificata mediante l'azione **Spedisci**. Se l'accettazione manuale della riga ordine è configurata a livello di canale, gli ordini devono essere accettati prima della spedizione. Dopo che una riga ordine è stata accettata e ha stato **In sospeso** o altro stato, le righe possono essere spedite. 

**Azione: Spedisci**

- Stato risultante: Fatturato o Parzialmente fatturato
- Stato back office risultante: Fatturato o Parzialmente fatturato

Le righe spedite dall'evasione ordine unificata vengono fatturate dal back office in modo analogo a quando l'ordine viene fatturato direttamente dal back office. Le righe spedite dall'evasione ordine unificata non vengono caricate nella visualizzazione transazioni e non vi sono pagamenti eseguiti nel momento in cui le righe vengono spedite. 

Le righe ordine completamente spedite non appaiono più nell'evasione ordine unificata. Le righe che sono state parzialmente spedite continueranno a comparire nell'evasione ordine unificata fino a quando non saranno state spedite per intero. 

Solo le righe dello stesso ordine possono essere spedite contemporaneamente. Se le righe dello stesso ordine hanno diverse modalità di consegna, possono comunque essere selezionate per la spedizione contemporaneamente. 

### <a name="reject"></a>Rifiuta

Le righe o le righe parziali possono essere rifiutate. Questo consente di riassegnarle dal back office a un altro punto vendita o magazzino. Le righe possono essere rifiutate solo se non sono ancora state prelevate o imballate. Per rifiutare una riga che è già stata prelevata o imballata, è necessario annullare il prelievo o l'imballaggio per tale riga dal back office. 

**Azione: Rifiuta**

- Stato risultante: Rifiutato
- Stato back office risultante: Nessuna modifica 

Le righe ordine rifiutate possono essere visualizzate dall'area lavoro **Elaborazione e richiesta di informazioni ordini cliente**. Deselezionare il filtro persona nell'area di lavoro per visualizzare tutte le righe dell'ordine rifiutate nei POS. Nella scheda **Righe ordine rifiutate** della visualizzazione nella sezione **Ordini e preferiti** è possibile visualizzare i dettagli della riga ordine. Inoltre, gli utenti possono fare clic sul pulsante **Righe ordine rifiutate** nella sezione **Riepilogo** per passare a una visualizzazione dell'ordine cliente. Questa visualizzazione mostra tutti gli ordini con una o più righe rifiutate dell'ordine. Se la gestione distribuita dell'ordine (DOM) è attivata, questi ordini respinti verranno automaticamente riassegnati ai POS appropriati per l'evasione, tuttavia, tuttavia queste righe ordine possono anche essere riassegnate manualmente. A questo scopo, selezionare la riga con **Stato di adempimento** **Rifiutato** e modificare il sito/magazzino come necessario. Fare clic sul menu a discesa **Aggiorna riga** e fare clic su **Reimposta stato di adempimento** per cambiare lo stato di evasione da **Rifiutato** ad **Accettato** o **In sospeso** in base all'impostazione dell'evasione dell'ordine. Dopo che lo stato di evasione viene reimpostato, i lavoratori del POS potranno visualizzare le righe ordine nel POS.

## <a name="line-quantity-tracking"></a>Tracciabilità quantità riga

Una riga ordine singola con quantità superiore a uno può essere elaborata più volte nel tempo, determinando più stati secondari per le righe ordine. Ad esempio, se un configuratore ha un progetto che richiede 500 schede, ma il configuratore preleva o dispone di poche schede alla volta nel corso del progetto, potrebbero esserci quantità che vengono prelevate, imballate e spedite contemporaneamente. 

Ogni volta che una riga viene selezionata, la quantità rimanente per la riga verrà compilata automaticamente presumendo che la quantità rimanente venga elaborata. Usando l'esempio precedente, se 200 schede sono già state prelevate e la riga per le schede viene selezionata per il prelievo, la quantità rimanente di 300 verrà automaticamente inserita nella quantità. Lo stesso vale se 200 schede sono già state fatturate. In tal caso, solo la quantità rimanente verrà compilata automaticamente. 

Continuando con l'esempio precedente, se 200 schede sono contrassegnate come imballate e viene selezionata la spedizione, l'intera quantità di 500 verrà riempita automaticamente. Se vengono spedite solo 200 schede, il sistema supporrà che le schede precedentemente imballate siano state spedite e la quantità imballata verrà diminuita. Se vengono spedite 201 schede, le schede imballate vengono prima diminuite con la scheda singola rimanente sottratta dalla quantità rimanente. 

## <a name="line-statuses"></a>Stati per la riga

Le righe ordine nel POS hanno diversi stati per riflettere lo stato della riga ordine. Gli stati nel POS e nel back office non sempre corrispondono. Lo stato della riga ordine può essere visualizzato attraverso il POS utilizzando le operazioni di evasione degli ordini. Nel back office, le righe ordini possono essere visualizzate da Dettagli ordini. I dettagli dell'ordine sono accessibili tramite **Retail** > **Clienti** > **Tutti gli ordini cliente**. Selezionare **ID ordine** per visualizzare i dettagli dell'ordine. Nei dettagli dell'ordine selezionare la scheda **Ordine cliente**, quindi **Stato dettagliato** nell'intestazione secondaria **Visualizzazione**. 

**In sospeso** - Le righe ordine che sono state assegnate a un POS, ma non ancora accettate, hanno lo stato **In sospeso** se visualizzate nel POS. Le righe in attesa di accettazione nel punto vendita avranno lo stato **Elaborazione ordine** nel back office.

**Accettato** - Le righe ordine che sono state accettate manualmente o accettate automaticamente avranno lo stato **Accettato** se visualizzate nel POS. Le righe con stato **Accettato** verranno visualizzate come **Elaborazione ordine** nel back office.

**Prelievo** - Le righe in fase di prelievo presso il POS hanno lo stato di **Prelievo**. Quelle stesse righe, quando vengono visualizzate nel back office, verranno visualizzate come **Elaborazione ordine**.

**Prelevato** e **Prelevato in parte** - Le righe prelevate o parzialmente prelevate nel POS avranno lo stato **Prelevato** o **Prelevato in parte**. Le stesse righe nel back office verranno inoltre visualizzate come **Prelevato** o **Prelevato in parte**.

**Imballato** e **Parzialmente imballato** - Le righe imballate o parzialmente imballate nel POS avranno lo stato **Imballato** o **Parzialmente imballato**. Le stesse righe nel back office verranno inoltre visualizzate come **Consegnate** o **Consegnato in parte**.

**Fatturato in parte** - Le righe parzialmente prelevate o parzialmente spedite avranno lo stato **Fatturato in parte** nel POS e nel back office.

**Fatturato** - Le righe interamente fatturate nel POS e non verranno più mostrate per l'evasione. Nel back office lo stato per queste righe sarà **Fatturato**.

## <a name="order-fulfillment-filtering"></a>Filtro di evasione ordine

L'evasione dell'ordine presso il POS include il filtro per aiutare l'utente a trovare facilmente ciò di cui ha bisogno. I filtri possono essere modificati dal riquadro azioni nella parte inferiore della schermata **POS**. Per impostazione predefinita, viene applicato un filtro **Tipo di consegna** in base alla modalità di impostazione dell'operazione. Se l'operazione è impostata con il parametro **Tutti gli ordini**, il filtro viene applicato quando si accede all'esecuzione dell'ordine. Lo stesso si applica ai parametri in **Ritiro presso punto vendita** e **Spedizione da punto vendita**. Gli altri filtri che possono essere applicati all'esecuzione dell'ordine includono:

  - Numero cliente
  - Nome cliente
  - Indirizzo di posta elettronica cliente
  - Numero ordine
  - Modalità di consegna
  - Numero ricevuta
  - ID riferimento canale
  - Numero punto vendita di origine
  - Stato riga
  - Data creazione
  - Data di consegna
  - Data di ricevimento

