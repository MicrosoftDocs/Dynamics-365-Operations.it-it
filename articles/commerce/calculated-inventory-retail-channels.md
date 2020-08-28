---
title: Calcolare la disponibilità scorte per i canali di vendita al dettaglio
description: In questo argomento vengono descritte le opzioni disponibili per mostrare le scorte disponibili per il punto vendita e i canali online.
author: hhainesms
manager: annbe
ms.date: 08/13/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: hhainesms
ms.search.validFrom: 2020-02-11
ms.dyn365.ops.version: Release 10.0.10
ms.openlocfilehash: 6d25a426268ebfb6990eb3dadb1ad451f86f59a1
ms.sourcegitcommit: 65a8681c46a1d99e7ff712094f472d5612455ff0
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/13/2020
ms.locfileid: "3694924"
---
# <a name="calculate-inventory-availability-for-retail-channels"></a>Calcolare la disponibilità scorte per i canali di vendita al dettaglio

[!include [banner](../includes/banner.md)]

Questo argomento descrive come un'azienda può utilizzare Microsoft Dynamics 365 Commerce per visualizzare la disponibilità scorte stimata per i prodotti nei canali online e dei punti vendita.

## <a name="accuracy-of-calculation"></a>Precisione del calcolo

Commerce utilizza più server e database per garantire scalabilità e prestazioni. Pertanto, è importante comprendere che i valori delle scorte disponibili forniti tramite l'applicazione del punto vendita (POS) le API per la disponibilità delle scorte e-commerce e le pagine di scorte disponibili nella sede centrale di Commerce potrebbero non essere accurati al 100% in tempo reale. Se le transazioni create per i prodotti nel canale online o del punto vendita non sono ancora state sincronizzate con il server e il database di Commerce Headquarters, le pagine delle scorte disponibili in Commerce Headquarters potrebbero non mostrare un valore di scorte in tempo reale accurato per tali prodotti. Al contrario, se l'azienda è stata configurata in modo che gli utenti di Commerce Headquarters o di altre applicazioni integrate possano vendere, ricevere, restituire o altrimenti modificare le scorte da un punto vendita o un magazzino online, il POS o il canale online potrebbero non avere tutte le informazioni richieste per mostrare un valore accurato per le scorte disponibili in tempo reale.

Questo argomento spiega i processi di sincronizzazione dei dati che possono essere eseguiti frequentemente per aiutare a limitare la latenza dei dati tra applicazioni o canali. Tuttavia, è fondamentale comprendere che tutti i dati sulle scorte disponibili forniti durante la giornata operativa sono considerati un valore stimato. Pertanto, se si tenta di confrontare le informazioni delle scorte disponibili fornite dall'applicazione con l'inventario fisico effettivo sugli scaffali o se si tenta di confrontare i valori delle scorte disponibili mostrati in POS con i dati delle scorte disponibili che si trovano nello stesso magazzino di Commerce Headquarters, i valori potrebbero differire. Questa differenza durante la giornata operativa è prevista e non deve essere considerata un problema. Se si desidera controllare i dati e assicurarsi che i valori forniti nelle API di disponibilità scorte e in Commerce Headquarters corrispondano alle unità fisiche effettive che trovi sugli scaffali del tuo punto vendita o magazzino, il momento migliore per farlo è dopo che le operazioni del canale sono state arrestate per quel giorno e tutte le transazioni sono state correttamente sincronizzate tra Commerce Headquarters e il canale.

## <a name="use-inventory-lookup-apis-for-e-commerce-inventory-availability-requests"></a>Utilizzare le API di ricerca delle scorte per le richieste di disponibilità scorte e-Commerce

È possibile utilizzare le seguenti API per mostrare la disponibilità scorte per un prodotto quando i clienti effettuano acquisti su un sito di e-commerce.

- **GetEstimatedAvailability** - Utilizzare questa API per ottenere la disponibilità scorte per l'articolo nel magazzino del canale e-Commerce o in tutti i magazzini collegati alla configurazione del gruppo di evasione ordini per il canale e-Commerce. Questa API può essere utilizzata anche per i magazzini in un'area o un raggio di ricerca specifici, in base ai dati di longitudine e latitudine.
- **GetEstimatedProductWarehouseAvailability** - Utilizzare questa API per richiedere le scorte per un articolo di un magazzino specifico. Ad esempio, è possibile utilizzarla per mostrare la disponibilità scorte in scenari che prevedono il prelievo ordine.

> [!NOTE]
> Queste API sostituiscono le API **GetProductAvailabilities** e **GetAvailableInventoryNearby** in Dynamics 365 Retail versione 10.0.7 e precedenti.

Entrambe le API recuperano i dati dal server Commerce e forniscono una stima delle scorte disponibili per una combinazione specifica di prodotto o variante di prodotto e magazzino. Sebbene altre API disponibili sul server Commerce possano accedere direttamente a Commerce Headquarters per recuperare le quantità di scorte disponibili per i prodotti, non è consigliabile utilizzarle in un ambiente di e-commerce a causa di potenziali problemi di prestazioni e del relativo impatto che queste frequenti richieste possono avere sui server Commerce Headquarters. Inoltre, se le scorte disponibili vengono calcolate tramite il server Commerce, è più probabile che il calcolo includa le scorte vendute nelle recenti transazioni e-Commerce che non sono ancora state sincronizzate con Commerce Headquarters. Sebbene Commerce Headquarters potrebbe non disporre delle informazioni su queste transazioni, il server Commerce e il database del canale dispongono dei dati. Pertanto, i dati verranno presi in considerazione e possono aiutare a fornire una stima più accurata delle scorte disponibili di un prodotto.

### <a name="get-started-with-e-commerce-calculated-inventory-availability"></a>Introduzione alla disponibilità scorte calcolata di e-Commerce

Prima di utilizzare le due API menzionate in precedenza, devi abilitare la funzionalità **Calcolo della disponibilità del prodotto ottimizzato** attraverso l'area di lavoro **Gestione funzionalità** in Commerce Headquarters.

Prima che le API possano calcolare la migliore stima della disponibilità scorte per un articolo, è necessario elaborare uno snapshot periodico della disponibilità scorte da Commerce Headquarters e inviarla al database del canale utilizzato da e-Commerce Commerce Scale Unit. Lo snapshot rappresenta le informazioni presenti in Commerce Headquarters in merito alla disponibilità scorte per una combinazione specifica di prodotto o variante di prodotto e magazzino. Può includere rettifiche o movimenti di inventario causati dalle entrate in magazzino, spedizioni o altri processi eseguiti in Commerce Headquarters e di cui il canale e-commerce ha informazioni solo a causa del processo di sincronizzazione.

Lo snapshot del database creato dal processo **Disponibilità prodotto** calcola solo le transazioni di inventario che sono state elaborate e registrate in Commerce Headquarters al momento in cui è stato acquisito lo snapshot. Se le scorte sono state vendute per un prodotto in un magazzino del punto vendita tramite una vendita ordine cliente in contanti o asincrono nell'applicazione POS, Commerce Headquarters non avrà immediatamente le informazioni sulla relativa transazione di uscita dal magazzino per la vendita. Conterrà le informazioni sulle scorte vendute per questi tipi di vendite del punto vendita solo dopo che il processo P ha caricato la relativa transazione dal database del canale del punto vendita in Commerce Headquarters e il relativo ordine di vendita è stato creato mediante la registrazione degli estratti conto o i processi di registrazione su inserimento continuo. Il processo di creazione dell'ordine in Commerce Headquarters crea le relative transazioni di inventario. Per gli ordini di canale e-Commerce, Commerce Headquarters ha le informazioni sulle transazioni di inventario solo dopo che le transazioni sono state inviate a in Commerce Headquarters tramite il processo P e dopo che il processo di sincronizzazione degli ordini è stato completato. Pertanto, è importante comprendere che il valore dello snapshot di magazzino fornito nel processo **Disponibilità prodotto** potrebbe non essere accurato al 100% in tempo reale a causa della costante elaborazione delle vendite che si verifica sui server distribuiti.

Per creare uno snapshot di magazzino in Commerce Headquarters, attenersi alla seguente procedura.

1. Andare a **Retail e Commerce \> Vendita al dettaglio e commercio IT \> Prodotti e inventario \> Disponibilità prodotto**.
1. Selezionare **OK** per eseguire il processo **Disponibilità prodotto**. È inoltre possibile pianificare questo processo in modo che venga eseguito in un batch.

Una volta terminata l'esecuzione del processo **Disponibilità prodotto**, i dati acquisiti devono essere inviati ai database del canale e-Commerce, in modo che lo snapshot più recente di magazzino di Commerce Headquarters possa essere considerato nel calcolo delle scorte disponibili stimato.

1. Selezionare **Retail e Commerce \> Vendita al dettaglio e commercio IT \> Programmazione della distribuzione**.
1. Eseguire il processo **1130** (**Disponibilità prodotto**) per sincronizzare i dati dello snapshot che il processo **Disponibilità prodotto** ha creato da Commerce Headquarters ai database del canale.

Quando la disponibilità delle scorte è richiesta dalle API **GetEstimatedAvailability** o **GetEstimatedProductWarehouseAvailability** viene eseguito un calcolo per cercare di ottenere la migliore stima possibile dell'inventario per il prodotto. Il calcolo fa riferimento a tutti gli ordini dei clienti e-Commerce presenti nel database del canale che non erano inclusi nei dati dello snapshot forniti dal processo 1130. Questa logica viene eseguita monitorando l'ultima transazione di inventario elaborata da Commerce Headquarters e confrontandola con le transazioni nel database del canale. Fornisce una base per la logica di calcolo sul lato canale, in modo che i movimenti di magazzino aggiuntivi che si sono verificati per le transazioni di vendita degli ordini dei clienti nel database del canale e-Commerce possano essere presi in considerazione nel valore di inventario stimato fornito dall'API.

La logica di calcolo sul lato canale restituisce un valore fisicamente disponibile stimato e un valore disponibile totale per il prodotto e il magazzino richiesti. Se desiderato, i valori possono essere visualizzati sul sito e-Commerce oppure possono essere utilizzati per attivare altre logiche aziendali sul sito e-Commerce. Ad esempio, è possibile mostrare un messaggio "esaurito" invece della quantità effettiva disponibile che l'API ha passato.

La logica di calcolo che le API di e-commerce lato canale utilizzano per il valore di magazzino stimato può valutare le scorte solo in base agli ordini dei clienti che sono stati creati nel database del canale e che non sono ancora stati sincronizzati e registrati in Commerce Headquarters. Se il database del canale contiene anche dati transazionali per le vendite cash-and-carry per i magazzini specifici del negozio, le vendite cash-and-carry non vengono prese in considerazione nel calcolo e-Commerce sul lato canale per tali magazzini.

## <a name="configure-the-inventory-lookup-operation-in-the-pos-channel"></a>Configurare l'operazione di ricerca dell'inventario nel canale POS

In Retail versione 10.0.9 e precedenti, l'operazione **Ricerca in magazzino** dal POS ha utilizzato una chiamata di servizio in tempo reale a Commerce Headquarters per ottenere informazioni di inventario per il prodotto selezionato, sia per il negozio corrente dell'utente sia per tutti gli altri negozi configurati per il gruppo di evasione come parte della configurazione del canale per il negozio. In Commerce versione 10.0.10 e successive, è possibile disattivare le chiamate di servizio in tempo reale a Commerce Headquarters. Al contrario, è possibile utilizzare il calcolo sul lato canale sul server Commerce per determinare le scorte disponibili fisicamente per il negozio e qualsiasi altra ubicazione definita nel gruppo di evasione ordini. Questa configurazione di inventario calcolata dal canale è utile anche per le ubicazioni in cui la connettività Internet non è affidabile, poiché non è necessario essere online per ottenere ricerche di inventario da Commerce Headquarters.

Quando il calcolo sul lato canale è configurato e gestito correttamente, può fornire una stima più affidabile dell'inventario del negozio corrente, poiché utilizza i dati transazionali presenti nel database del canale Commerce, ma che Commerce Headquarters potrebbe non disporre ancora delle relative informazioni. Ad esempio, se si utilizza la chiamata di servizio in tempo reale esistente per le ricerche di inventario in POS, probabilmente Commerce Headquarters non avrà ancora le informazioni su una vendita cash-and-carry appena avvenuta per un prodotto. Pertanto, il valore dell'inventario disponibile restituito da Commerce Headquarters per quel prodotto supererà probabilmente le scorte disponibili effettive del negozio di un'unità. Tuttavia, se si utilizza il calcolo sul lato canale, la vendita cash-and-carry può essere presa in considerazione nel calcolo e detratta dal valore di scorte disponibili che viene mostrato. Sebbene i valori forniti sia dal calcolo lato canale sia dalla chiamata di servizio in tempo reale siano solo stime delle scorte disponibili, il valore fornito dal calcolo lato canale è molto più probabile che sia accurato per il punto vendita corrente.

### <a name="get-started-with-pos-channel-side-calculated-inventory-availability"></a>Introduzione alla disponibilità scorte calcolata lato canale POS

Per utilizzare la logica di calcolo sul lato canale e disattivare le chiamate di servizio in tempo reale per le ricerche di inventario dall'applicazione POS, devi prima abilitare la funzionalità **Calcolo della disponibilità del prodotto ottimizzato** attraverso l'area di lavoro **Gestione funzionalità** in Commerce Headquarters. Oltre ad abilitare la funzione, devi apportare modifiche al **profilo Funzionalità**.

Per modificare il **profilo Funzionalità**, segui la procedura seguente:

1. Passare a **Retail e Commerce \> Impostazione canale \> Impostazione POS \> Profili POS \> Profili funzionalità**.
1. Selezionare un profilo funzionalità.
1. Nella scheda dettaglio **Funzioni**, nella sezione **Calcolo disponibilità scorte**, cambiare il valore del campo **Modalità di calcolo disponibilità scorte** da **Servizio in tempo reale** a **Canale**. Per impostazione predefinita, tutti i profili di funzionalità utilizzano chiamate di servizio in tempo reale. Pertanto, è necessario modificare il valore di questo campo se si desidera utilizzare la logica di calcolo sul lato canale. Ogni punto vendita al dettaglio collegato al profilo di funzionalità selezionato sarà interessato da questa modifica.

Devi quindi sincronizzare le modifiche al canale attraverso il processo di pianificazione della distribuzione procedendo come segue:

1. Selezionare **Retail e Commerce \> Vendita al dettaglio e commercio IT \> Programmazione della distribuzione**.
1. Eseguire il processo **1070** (**Configurazione canale**).

Al termine della configurazione, le informazioni fornite sulle scorte fisicamente disponibili non utilizzano più una chiamata di servizio in tempo reale quando un utente nell'applicazione POS utilizza l'operazione **Ricerca in magazzino** (visualizzazioni standard e matrice). I dati sulle scorte fisicamente disponibili per il negozio corrente e tutti i negozi nel gruppo di evasione ordini vengono calcolati in base all'ultimo snapshot noto che è stata consegnata al database del canale da Commerce Headquarters. Il valore dello snapshot viene ulteriormente perfezionato dal calcolo sul lato canale per regolare il valore delle scorte fisicamente disponibili, in base alle vendite aggiuntive o alle transazioni di reso esistenti per il prodotto selezionato nel database del canale che non sono state incluse nell'ultimo snapshot sincronizzato dal processo 1130. Se il database del canale non contiene dati transazionali per nessuno dei magazzini o negozi nel gruppo di evasione ordini, non contiene le transazioni aggiuntive che possono essere prese in considerazione in un ricalcolo del valore. Pertanto, la migliore stima delle scorte disponibili che può essere mostrata per quei magazzini o negozi è costituita dai dati dell'ultimo snapshot di Commerce Headquarters noto.

Le schermate **Evasione ordine** del POS sfruttano anche il calcolo lato canale per mostrare le scorte disponibili per gli articoli quando viene selezionata una riga di evasione dell'ordine e un utente visualizza il pannello **Dettagli** per le scorte disponibili dell'articolo selezionato.

## <a name="optimize-your-inventory-data"></a>Ottimizzare i dati di magazzino

Per garantire la migliore stima possibile dell'inventario, è fondamentale utilizzare i seguenti processi batch Commerce ed eseguirli frequentemente:

- **Processo P** - Il processo P è disponibile nella pagina **Programmazioni della distribuzione** e deve essere eseguito frequentemente. Questo processo porta gli ordini e-Commerce, gli ordini asincroni dei clienti creati dal POS e gli ordini cash-and-carry creati dal POS dai database del canale in Commerce Headquarters in modo che possano essere elaborati ulteriormente. Fino a quando questi dati non vengono sincronizzati dal canale in Commerce Headquarters, Commerce Headquarters non ha informazioni sulle rettifiche delle scorte dei prodotti nei magazzini risultanti da tali transazioni.
- **Sincronizza ordini** - Questo processo elabora i dati transazionali non elaborati in Commerce Headquarters forniti dal processo P e converte le transazioni e-commerce e degli ordini asincroni dei clienti in ordini di vendita in Commerce Headquarters. Fino a quando questo processo non viene elaborato e non vengono creati gli ordini cliente, non vengono create le transazioni di inventario. Pertanto, le scorte disponibili in Commerce Headquarters non prendono in considerazione le transazioni.
- **Calcola rendiconti transazionali in batch** - Per le transazioni cash-and-carry create nel punto vendita, il processo di registrazione dell'alimentazione su inserimento continuo assicura che l'inventario correlato alle vendite venga aggiornato in modo efficiente. Per ottenere l'elaborazione più efficiente delle transazioni di inventario per gli ordini cash-and-carry, assicurarsi di configurare il sistema per l'uso della [registrazione su inserimento continuo](https://docs.microsoft.com/dynamics365/commerce/trickle-feed).
- **Registra rendiconti transazionali in batch** - Questo processo è richiesto anche per la registrazione su inserimento continuo. Segue il processo **Calcola rendiconti transazionali in batch**. Questo processo registra sistematicamente gli estratti conto calcolati, in modo che gli ordini di vendita per le vendite cash-and-carry vengano creati in Commerce Headquarters che riflette in modo più accurato l'inventario del punto vendita.
- **Disponibilità prodotto** - Questo processo crea lo snapshot dell'inventario da Commerce Headquarters.
- **1130 (disponibilità prodotto)** - Questo processo si trova nella pagina **Programmazioni della distribuzione** e deve essere eseguito immediatamente dopo il processo **Disponibilità prodotto**. Questo processo trasporta i dati dello snapshot dell'inventario da Commerce Headquarters ai database del canale.

Si consiglia di non eseguire questi processi batch troppo frequentemente (ogni pochi minuti). Esecuzioni frequenti sovraccaricano Commerce headquarters (HQ) e possono potenzialmente influire sulle prestazioni. In generale, è buona norma eseguire la disponibilità del prodotto e 1.130 lavori su base oraria e pianificare il processo P, sincronizzare gli ordini e gestire i processi relativi alla registrazione dei feed con la stessa frequenza o una frequenza maggiore.

> [!NOTE]
> Per motivi di prestazioni, quando vengono utilizzati i calcoli delle scorte disponibili sul lato canale per effettuare una richiesta di disponibilità scorte utilizzando l'API e-Commerce o la nuova logica di inventario sul canale POS, il calcolo utilizza una cache per determinare se è trascorso abbastanza tempo per giustificare la nuova esecuzione della logica di calcolo. La cache predefinita è impostata su 60 secondi. Ad esempio, hai attivato il calcolo lato canale per il tuo negozio e hai visualizzato le scorte disponibili per un prodotto nella pagina **Ricerca in magazzino**. Se viene venduta un'unità del prodotto, la pagina **Ricerca in magazzino** non mostrerà l'inventario ridotto fino a quando la cache non sarà stata canCellaata. Dopo che gli utenti registrano le transazioni nel POS, devono attendere 60 secondi prima di verificare che l'inventario disponibile sia stato ridotto.

Se lo scenario aziendale richiede un tempo di cache inferiore, contattare il rappresentante dell'assistenza tecnica per assistenza.
