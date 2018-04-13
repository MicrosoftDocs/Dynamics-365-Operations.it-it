---
title: Impostazione dell'evasione ordini nel punto vendita
description: In questo argomento viene fornita una panoramica su come impostare l'evasione ordini del punto vendita.
author: rubencdelgado
manager: AnnBe
ms.date: 10/30/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: RetailStoreTable, RetailTillLayout
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.search.region: Global
ms.search.industry: retail
ms.author: rubencdelgado
ms.search.validFrom: 2017-10-30
ms.dyn365.ops.version: 
ms.translationtype: HT
ms.sourcegitcommit: 72d4ff5e1311005d3bf43a13e28208cd9b3d1457
ms.openlocfilehash: ccff6533257379c0305f7414dd36e17d1c323c21
ms.contentlocale: it-it
ms.lasthandoff: 03/08/2018

---


# <a name="set-up-order-fulfillment-for-stores"></a>Impostazione dell'evasione ordini nel punto vendita

[!INCLUDE [banner](includes/banner.md)]

## <a name="overview"></a>Panoramica
Molti rivenditori vorrebbero ottimizzare l'evasione dell'ordine consentendo ai punti vendita di eseguire gli ordini. L'evasione degli ordini a livello di punto vendita può semplificare gli scenari di scorte in eccesso per un punto vendita specifico o potrebbe essere necessaria da un punto di vista logistico nei casi in cui un punto vendita disponga di capacità aggiuntiva o si trovi a una distanza di spedizione più vicina al cliente. Per rispondere a questa esigenza, un'operazione di evasione degli ordini unificata è disponibile presso il POS.

Negli ordini per l'evasione presso un punto vendita specifico, il magazzino del negozio è indicato sull'intestazione o sulle righe dell'ordine. 

L'operazione di evasione dell'ordine presso il POS offre una singola area di lavoro nel POS che può essere utilizzata per elaborare gli ordini. Ciò include tutte le operazioni, dall'accettazione dell'ordine, al contrassegno come spedito o all'avvio del ritiro del presso il punto vendita. 

## <a name="set-up-the-order-fulfillment-operation"></a>Impostare l'operazione di evasione dell'ordine

L'evasione ordini, [ID operazione 928](https://docs.microsoft.com/en-us/dynamics365/unified-operations/retail/pos-operations), può essere utilizzata per accedere all'area di lavoro per l'evasione degli ordini del POS. 

Completare i passaggi in [Aggiungere l'operazione in una griglia dei pulsanti](https://docs.microsoft.com/en-us/dynamics365/unified-operations/retail/pos-screen-layouts) per specificare i parametri da utilizzare per richiamare l'esecuzione dell'ordine nel POS. Per impostazione predefinita, dopo aver specificato le operazioni di evasione degli ordini, viene selezionato **Tutti gli ordini**. Una volta configurata con questo parametro, l'operazione elencherà tutte le righe ordine per l'esecuzione ordine nel punto vendita corrente. È inoltre disponibile **Ordini da spedire**, che può essere assegnato a un pulsante e utilizzato quando l'utente desidera visualizzare solo gli ordini con spedizione dal punto vendita. Infine, è disponibile **Ordini per prelievo**. Quando viene richiamato nel POS, vengono elencati solo gli ordini da prelevare al negozio. I diversi parametri possono essere assegnati a pulsanti diversi per offrire all'utente una varietà di modi per visualizzare l'evasione degli ordini. 

### <a name="enable-users-to-access-order-fulfillment-at-the-point-of-sale"></a>Consentire agli utenti di accedere all'evasione dell'ordine nel POS. 

L'operazione di evasione degli ordini non dispone di propria autorizzazione immediatamente disponibile, ma in futuro, gli utenti possono richiedere di utilizzare l'autorizzazione **Consenti recupero ordine** per richiamare l'operazione dal POS.

A livello di punto vendita, un'impostazione di configurazione è disponibile per determinare se la riga dell'ordine deve essere accettata manualmente dal POS. Se tale opzione di configurazione non è impostata, le righe ordine verranno accettate per impostazione predefinita. Se tale opzione di configurazione è abilitata, gli utenti nel POS dovranno disporre dell'autorizzazione **Consenti accettazione ordine** per accettare gli ordini dal POS. 


### <a name="enable-manual-order-acceptance"></a>Consentire l'accettazione dell'ordine manuale

Per impostazione predefinita, righe di ordine assegnate a un punto vendita vengono come **Accettato**. Ciò significa che si presume che verranno evase dal POS assegnato e non saranno soggette a ulteriore assegnazione. In alcuni casi, i rivenditori potrebbero voler accettare manualmente gli ordini prima che possano essere soddisfatti. Ad esempio, se un punto vendita è a corto di personale e non è in grado di evadere gli ordini, un responsabile del punto vendita accetterà solo gli ordini per l'elaborazione che possono essere adeguatamente elaborati in un dato giorno. Fino a quando un ordine non viene accettato, può essere riassegnato dal back office a un altro negozio. In questo modo, l'accettazione dell'ordine fornisce anche un modo per indicare che un ordine è stato riconosciuto da un punto vendita e sarà soddisfatto. 

Le righe ordine per il prelievo dai punti vendita vengono contrassegnate come **In sospeso** e non sono soggette all'accettazione.

Per attivare l'accettazione manuale per le righe dell'ordine, passare a **Retail** > **Canali** > **Punti vendita al dettaglio** > **Tutti i punti vendita al dettaglio**. Selezionare il punto vendita e scegliere l'ID del punto vendita per visualizzare i dettagli del punto vendita. Fare clic su **Modifica**. Nella scheda dettaglio **Generale**, individuare l'intestazione secondaria **Evasione ordine** e modificare **Accettazione manuale** da **No** a **Sì**. 

### <a name="enable-reject-order-line-capability"></a>Attivare la funzionalità di rifiuto della riga ordine

Le righe ordine possono inoltre essere rifiutate dal POS. Rifiutare una riga ordine significa che la riga non verrà evasa in quel punto vendita e che la riga d'ordine verrà inviata di nuovo per la riassegnazione a un altro punto vendita o magazzino. L'autorizzazione di rifiuto della riga ordine è assegnata tramite l'autorizzazione **Consenti rifiuto ordine** nel gruppo di autorizzazioni POS associato al lavoratore. Quando si rifiuta una riga, i rivenditori possono impostare l'obbligo per i lavoratori di immettere una motivazione per il rifiuto. Ciò può essere ottenuto utilizzando i codici informativi di tipo **Attività codice informativo** ed **Evasione ordine** e assegnando il codice informativo in **Rifiuta riga ordine** nel profilo funzionalità associato al canale. 

>[!Note]
>Solo i codici informativi di tipo **Attività codice informativo** ed **Evasione ordine** possono essere assegnati all'azione **Rifiuta riga ordine**.

### <a name="synchronize-changes-to-the-channel-database"></a>Sincronizzare le modifiche apportate al database del canale

Dopo che l'operazione è stata assegnata a una griglia dei pulsanti, le autorizzazioni appropriate sono state assegnate e il canale è stato configurato, le modifiche devono essere sincronizzate nel database del canale. A tale scopo, passare a **Retail** > **IT vendita al dettaglio** > **Programmazione della distribuzione**. Selezionare la pianificazione "1090, Registri" per sincronizzare le modifiche della griglia dei pulsanti e quindi fare clic su **Esegui ora**. A questo punto, sincronizzare le modifiche delle autorizzazioni selezionando "1060-Personale" e quindi fare clic su **Esegui ora**. A questo punto, sincronizzare le modifiche del canale selezionando "1070-Configurazione canale" e quindi fare clic su **Esegui ora**. Infine, sincronizzare il codice informativo appena creato per il motivo di rifiuto selezionando "1110-Configurazione globale" e fare clic su **Esegui ora**.

## <a name="use-order-fulfillment-at-the-point-of-sale"></a>Utilizzare l'evasione ordine nel POS

Aprire il POS e selezionare l'operazione di evasione dell'ordine. A seconda della configurazione, verranno elencate tutte le righe, le righe ordine per il prelievo o le righe ordine da spedire. 

### <a name="order-fulfillment-view"></a>Visualizzazione dell'evasione ordine 

La visualizzazione di evasione ordini elenca le righe dell'ordine per l'evasione nel POS e include le seguenti colonne:

  - Numero ordine
  - Numero prodotto
  - descrizione
  - Quantità ordinata
  - Data di consegna richiesta
  - Nome cliente
  - Stato di adempimento
  
È possibile visualizzare ulteriori informazioni per una riga ordine specifica selezionando la riga dell'ordine e quindi aprendo il menu a comparsa situato appena sotto l'utente registrato o le informazioni sul turno visualizzate nell'intestazione del punto di vendita. Questo menu include 2 schede: una per i dettagli riga e un'altra per i dettagli dell'ordine. La scheda dettagli riga include le seguenti informazioni:

  - Quantità ordinata
  - Quantità rimanente da inviare/prelevare
  - Quantità prelevata
  - Quantità imballata
  - Quantità fatturata (già spedita o prelevata)
  - Modalità di consegna
  - Indirizzo di consegna
  
Il menu a comparsa dei dettagli presenta anche una scheda che fornisce ulteriori dettagli sul livello dell'ordine, tra cui:

  - Nome cliente
  - ID cliente
  - Numero ordine
  - Totale ordine
  - Saldo ordine
  
Nella parte inferiore della visualizzazione di evasione ordine è presente un riquadro azioni. Questo contiene tutte le azioni che è possibile eseguire per un record in una riga ordine. Se un'azione non è disponibile in base allo stato di una riga, tale azione non sarà disponibile. 

Per impostazione predefinita, gli ordini avranno stato **Accettato**. Lo stato dell'ordine può essere visualizzato come colonna nell'elenco di righe ordine. Se l'**Accettazione manuale** viene configurata a livello di canale, tutte le righe da spedire verranno visualizzate come **In sospeso** e dovranno essere accettate prima di poter essere evase. Per impostazione predefinita, gli ordini per il prelievo nei punti vendita vengono impostati come **In sospeso** e non devono essere accettati.

### <a name="order-fulfillment-line-actions"></a>Azioni della riga di evasione ordine

**Modifica** - Se lo stato dell'ordine è in sospeso, può essere modificato nel POS. Gli ordini che sono già stati parzialmente prelevati, imballati o fatturati non possono essere modificati dalla visualizzazione di evasione ordine.

**Accetta** - Se l'**Accettazione manuale** è configurata a livello di canale, le righe devono essere accettate prima di poter passare attraverso il processo di evasione degli ordini.

**Preleva** - L'opzione di prelievo supporta più azioni. Innanzitutto, **Preleva** aggiorna lo stato della riga ordine in modo che altri nel punto vendita non tentino di selezionare la stessa riga. Successivamente, **Stampa distinta di prelievo** stampa una distinta di prelievo per la riga o le righe e aggiorna anche il relativo stato su **Prelievo**. I formati della distinta di prelievo vengono controllati come parte dei formati di entrata. Per ulteriori informazioni sulle modalità di configurazione dei formati di ricevute, vedere [Modelli e stampa di ricevute](https://docs.microsoft.com/en-us/dynamics365/unified-operations/retail/receipt-templates-printing) Infine, **Contrassegna come prelevato** indica che la riga è stata selezionata. **Contrassegna come prelevato** avvia le operazioni di magazzino corrispondenti nel back office. Le azioni di prelievo possono essere eseguite contemporaneamente per più righe ordine negli ordini e con tutte le modalità di consegna.

**Rifiuta**- Le righe o le righe parziali possono essere rifiutate. Questo consente di riassegnarle dal back office a un altro punto vendita o magazzino. Le righe possono essere rifiutate solo se non sono ancora state prelevate o imballate. Per rifiutare una riga che è già stata prelevata o imballata, è necessario annullare il prelievo o l'imballaggio per tale riga dal back office. 

**Imballa** - L'opzione di imballaggio supporta due azioni: **Stampa documento di trasporto** consente di stampare un documento di trasporto per le righe selezionate e **Contrassegna come imballato** contrassegna le righe come imballate e contrassegna le righe come consegnate nel back office. Solo le righe ordine che appartengono allo stesso ordine e che hanno la stessa modalità di consegna possono essere imballate contemporaneamente. I formati della documento di trasporto vengono controllati come parte dei formati di entrata. Per ulteriori informazioni sulle modalità di configurazione dei formati di ricevute, vedere [Modelli e stampa di ricevute](https://docs.microsoft.com/en-us/dynamics365/unified-operations/retail/receipt-templates-printing)

**Spedisci** - L'azione di spedizione contrassegna le righe selezionate come **Consegnato** nel back office. Dopo che una la riga è stata spedita completamente, non verrà più visualizzata nell'evasione ordine.

**Preleva** - L'azione di prelievo aggiungere le righe alla visualizzazione transazione per il prelievo. Se sono presenti altre righe dell'ordine che attualmente non vengono prelevate, verranno aggiunte alla visualizzazione transazione con quantità pari a zero. Dopo che una la riga è stata prelevata completamente, non verrà più visualizzata nell'evasione ordine. 

### <a name="order-fulfillment-filtering"></a>Filtro di evasione ordine

L'evasione dell'ordine presso il POS include il filtro per aiutare l'utente a trovare facilmente ciò di cui ha bisogno. I filtri possono essere modificati nel riquadro azioni nella parte inferiore della schermata **POS**. Per impostazione predefinita, viene applicato un filtro **Tipo di consegna** in base alla modalità di impostazione dell'operazione. Se l'operazione è impostata con il parametro **Tutti gli ordini**, il filtro viene applicato quando si accede all'esecuzione dell'ordine. Lo stesso si applica ai parametri in **Ritiro presso punto vendita** e **Spedizione da punto vendita**. Gli altri filtri che possono essere applicati all'esecuzione dell'ordine includono:

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

