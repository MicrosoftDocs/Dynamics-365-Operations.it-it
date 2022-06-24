---
title: Ricerca di prodotti e di clienti nel POS
description: Questo articolo fornisce una panoramica dei miglioramenti apportati alla funzionalità di ricerca prodotti e clienti in Dynamics 365 Commerce.
author: ShalabhjainMSFT
ms.date: 05/25/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: josaw
ms.custom: 141393
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: shajain
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: Retail April 2017 update
ms.openlocfilehash: 5f2d8162c810f63dc889a03d33fd111de69783de
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8859002"
---
# <a name="product-search-and-customer-search-in-the-point-of-sale-pos"></a>Ricerca di prodotti e di clienti nel POS

[!include [banner](includes/banner.md)]

Modern POS (MPOS) e POS cloud (CPOS) forniscono una funzionalità di ricerca di facile utilizzo che consente di cercare prodotti e clienti. Dal momento che la barra di ricerca è sempre presente nella parte superiore delle finestre MPOS e CPOS, i dipendenti possono trovare rapidamente prodotti e clienti.

I dipendenti possono cercare i prodotti negli assortimenti e nei cataloghi associati al punto vendita corrente. Possono inoltre cercare negli assortimenti e nei cataloghi associati a qualsiasi altro punto vendita della società. Di conseguenza, i cassieri possono vendere e restituire prodotti al di fuori dell'assortimento del punto vendita. Analogamente, i dipendenti possono cercare i clienti che sono associati al punto vendita corrente o a qualsiasi altro punto vendita della società. Inoltre, i dipendenti possono cercare i clienti che sono associati a un'altra società nell'organizzazione padre.

## <a name="product-search"></a>Ricerca prodotto

Per impostazione predefinita, le ricerche dei prodotti vengono effettuate nell'assortimento del punto vendita. Questo tipo di ricerca è denominata *ricerca prodotto locale*. Tuttavia, i dipendenti possono passare facilmente a qualsiasi catalogo associato al punto vendita corrente, oppure possono effettuare una ricerca in un altro punto vendita. Questo tipo di ricerca è denominata *ricerca prodotto remota*. Per cambiare il catalogo, selezionare il pulsante **Categorie** nella parte sinistra della pagina. Nella parte superiore del riquadro visualizzato, selezionare il pulsante **Cambia catalogo** e selezionare il catalogo in cui effettuare la ricerca. Il sistema cercherà i prodotti nel catalogo selezionato.

Nella pagina **Cambia catalogo**, i dipendenti possono selezionare facilmente qualsiasi punto vendita, oppure possono cercare prodotti in tutti i punti vendita.

![Cambiare il catalogo.](./media/Changecatalog.png "Cambiare il catalogo")

Una ricerca di prodotto locale esegue la ricerca nelle seguenti proprietà di prodotto:

- Numero prodotto
- Nome prodotto
- Descrizione
- Dimensioni
- Codice a barre
- Cerca nome

### <a name="additional-local-product-search-capabilities-conventional-sql-full-text-search"></a>Ulteriori funzionalità di ricerca di prodotti locali (ricerca full-text SQL convenzionale) 

- Per le ricerche con più parole chiave (ovvero le ricerche che utilizzano termini di ricerca), i rivenditori possono stabilire se i risultati della ricerca includono i risultati corrispondenti a *qualsiasi* termine di ricerca o solo i risultati che corrispondono a *tutti* i termini di ricerca. L'impostazione per questa funzionalità è disponibile nel profilo della funzionalità POS, in un nuovo gruppo denominato **Ricerca prodotto**. L'impostazione predefinita è **Abbina alcuni termini di ricerca**. Questa impostazione è quella consigliata. Quando si utilizza l'impostazione **Abbina alcuni termini di ricerca**, nei risultati vengono restituiti tutti i prodotti che corrispondono completamente o parzialmente a uno o più termini di ricerca. Tali risultati vengono ordinati automaticamente in ordine crescente in base ai prodotti che hanno il maggior numero di corrispondenze (complete o parziali) con le parole chiave.

    L'impostazione **Abbina tutti i termini di ricerca** restituisce solo i prodotti che corrispondono (completamente o parzialmente) a tutti i termini di ricerca. Questa impostazione è utile quando i nomi dei prodotti sono lunghi e i dipendenti desiderano visualizzare solo una parte dei nomi nei risultati della ricerca. Questo tipo di ricerca presenta tuttavia due limiti:

    - La ricerca viene effettuata in singole proprietà di prodotto. Ad esempio, vengono restituiti solo i prodotti che hanno tutte le parole chiave cercate in almeno una proprietà di prodotto.
    - La ricerca non viene eseguita nelle dimensioni.
> [!NOTE]
> Le seguenti configurazioni di **Trova qualsiasi termine di ricerca**/**Trova tutti i termini di ricerca** nei profili di funzionalità POS sono applicabili solo per le esperienze di ricerca di prodotto **locali** (ricerca full-text SQL convenzionale). Questa configurazione non ha effetto sulle esperienze di ricerca basate su cloud. Il nuovo motore di ricerca ha il proprio algoritmo avanzato che potenzia la pertinenza della ricerca per i risultati della ricerca del prodotto. 

- I rivenditori possono configurare la ricerca prodotto in modo da visualizzare suggerimenti di ricerca mentre gli utenti digitano nomi di prodotti. Una nuova impostazione per questa funzionalità è disponibile nel profilo della funzionalità POS, in un gruppo denominato **Ricerca prodotto**. L'impostazione è denominata **Mostra suggerimenti di ricerca durante la digitazione**. Questa funzionalità può consentire ai dipendenti di trovare rapidamente il prodotto che stanno cercando, in quanto non devono digitarne il nome completo.
- L'algoritmo di ricerca prodotto ora cerca i termini anche nella proprietà **Nome di ricerca** del prodotto.

![Suggerimenti su prodotti.](./media/Productsuggestions.png "Suggerimenti su prodotti")

## <a name="customer-search"></a>Ricerca cliente

La ricerca cliente viene utilizzata per trovare clienti per vari scopi. Ad esempio, i cassieri potrebbero aver bisogno di visualizzare l'elenco preferenze o lo storico degli acquisti di un cliente o aggiungere il cliente a una transazione. L'algoritmo di ricerca abbina i termini di ricerca ai valori presenti nelle seguenti proprietà cliente:

- Nome
- Indirizzo di posta elettronica
- Numero di telefono
- Numero carta fedeltà
- Indirizzo
- Numero di conto

Tra queste proprietà, il nome fornisce la maggiore flessibilità per ricerche con molteplici parole chiave, in quanto l'algoritmo restituisce tutti i clienti corrispondenti a una qualsiasi delle parole chiave cercate. I clienti con il maggior numero di corrispondenze sono visualizzati all'inizio dei risultati. Questo comportamento è utile ai cassieri nelle situazioni in cui effettuano ricerche digitando il nome completo ma il cognome e il nome sono stati scambiati durante la prima immissione dei dati. Tuttavia, per motivi di prestazioni, tutte le altre proprietà mantengono l'ordine delle parole chiave di ricerca. Quindi se l'ordine delle parole chiave non corrisponde a quello in cui i dati sono archiviati, non verrà restituito alcun risultato.

Per impostazione predefinita, una ricerca cliente viene eseguita nelle rubriche clienti associate al punto vendita. Questo tipo di ricerca è denominata *ricerca cliente locale*. Tuttavia, i dipendenti possono anche cercare i clienti globalmente. In altre parole, possono effettuare la ricerca nei punti vendita della società e in tutte le altre persone giuridiche. Questo tipo di ricerca è denominata *ricerca cliente remota*.

Per effettuare una ricerca globale, i dipendenti possono selezionare il pulsante **Risultati filtro** nella parte inferiore della pagina e quindi selezionare l'opzione **Cerca in tutti i punti vendita**, come illustrato nella figura di seguito. In questo caso, non vengono restituiti solo i clienti, ma anche tutti i tipi di parti incluse in qualsiasi rubrica nella sede centrale. Queste parti includono lavoratori, fornitori, contatti e concorrenti.

> [!NOTE]
> È necessario immettere almeno quattro caratteri perché una ricerca cliente remota restituisca dei risultati.

L'ID cliente non è visualizzato per i clienti cercati di altre persone giuridiche, poiché nessun ID cliente è stata creato per quelle parti nella società corrente. Tuttavia, se un dipendente apre la pagina dei dettagli del cliente, il sistema genera automaticamente un ID cliente per la parte e inoltre associa la rubrica clienti del punto vendita al cliente. Di conseguenza, il cliente sarà visibile nelle ricerche dei punti vendita locali eseguite successivamente.

![Ricerca cliente globale.](./media/Globalcustomersearch.png "Ricerca cliente globale")

### <a name="additional-local-customer-search-capabilities"></a>Funzionalità di ricerca di clienti aggiuntive

Quando l'utente cerca un numero di telefono, il sistema ignora caratteri speciali (ad esempio spazi, trattini e parentesi), che potrebbero essere stati aggiunti al momento della creazione del cliente. Di conseguenza, i cassieri non devono preoccuparsi del formato del numero di telefono durante la ricerca. Ad esempio, se il numero di telefono di un cliente è stato immesso come **123-456-7890**, un cassiere può cercare il cliente digitando **1234567890** oppure digitando le prime cifre del numero di telefono.

> [!NOTE]
> Un cliente può avere più numeri di telefono e più indirizzi e-mail. L'algoritmo di ricerca del cliente cerca anche attraverso questi indirizzi e-mail e numeri di telefono secondari, ma la pagina dei risultati di ricerca del cliente mostra solo l'indirizzo e-mail e il numero di telefono principali. Ciò può causare confusione poiché i risultati dei clienti restituiti non mostrerebbero l'indirizzo e-mail o il numero di telefono cercato. In una versione futura intendiamo migliorare la schermata dei risultati di ricerca dei clienti per mostrare queste informazioni.

La ricerca tradizionale dei clienti può richiedere molto tempo, poiché esegue la ricerca in più campi. I cassieri possono effettuare una ricerca in una singola proprietà del cliente, ad esempio il nome, l'indirizzo di posta elettronica o il numero di telefono. Le proprietà dell'algoritmo di ricerca del cliente sono collettivamente note come *criteri di ricerca del cliente*. L'amministratore di sistema può facilmente configurare uno o più criteri come collegamenti da visualizzare nel POS. Poiché la ricerca è limitata a un unico criterio, vengono visualizzati solo i risultati della ricerca pertinenti, pertanto le prestazioni sono molto superiori rispetto a quelle di una ricerca standard del cliente. La figura riportata di seguito mostra i collegamenti di ricerca del cliente nel POS.

![Collegamenti di ricerca del cliente.](./media/SearchShortcutsPOS.png "Collegamenti di ricerca del cliente")

Per impostare i criteri di ricerca come collegamenti, l'amministratore deve aprire la pagina **Parametri di commercio** in Commerce, quindi, nella scheda **Criteri di ricerca POS**, selezionare tutti i criteri che devono essere mostrati come collegamenti.

![Configurare i collegamenti di ricerca.](./media/ConfigureShortcutsAX.png "Configurare i collegamenti di ricerca")

> [!NOTE]
> Se si aggiungono troppi collegamenti, il menu a discesa nella barra della ricerca nel POS non riesce a visualizzarli correttamente a scapito della ricerca da parte del dipendente. Si consiglia di aggiungere solo i collegamenti necessari.

Il campo **Ordine di visualizzazione** determina l'ordine in cui i collegamenti vengono visualizzati nel POS. I criteri che vengono visualizzati sono le proprietà predefinite utilizzate dall'algoritmo di ricerca del cliente per cercare i clienti. Tuttavia, i partner possono aggiungere proprietà personalizzate come collegamenti di ricerca. Per aggiungere proprietà personalizzate come collegamenti di ricerca, l'amministratore di sistema deve estendere l'enumerazione (enum) estendibile utilizzata per i criteri di ricerca del cliente e quindi contrassegnare le proprietà personalizzate del partner come collegamenti. I partner sono responsabili della scrittura del codice per trovare i risultati derivanti dall'utilizzo dei collegamenti personalizzati.

Le traduzioni per i tasti di scelta rapida sono necessarie se vuoi che i tasti di scelta rapida vengano visualizzati sul POS. Se la lingua del tuo canale è diversa dalla lingua predefinita del sistema, devi definire la traduzione per ogni tasto di scelta rapida nella lingua prevista. È possibile definire le traduzioni selezionando **Traduci** per ogni tasto di scelta rapida. 

> [!NOTE]
> Una proprietà personalizzata che viene aggiunta all'enumerazione non influisce sull'algoritmo predefinito di ricerca del cliente. In altre parole, l'algoritmo di ricerca del cliente non cerca nella proprietà personalizzata. Gli utenti possono utilizzare una proprietà personalizzata per le ricerche solo se la proprietà personalizzata viene aggiunta come collegamento o se l'algoritmo di ricerca predefinito viene sovrascritto.

I rivenditori possono anche impostare la modalità di ricerca clienti predefinita in POS su **Cerca in tutti i punti vendita**. Questa configurazione può risultare utile in scenari in cui la ricerca di clienti creati al di fuori di POS deve essere eseguita immediatamente (ad esempio anche prima del processo di distribuzione). A questo proposito, il rivenditore deve attivare l'opzione **Modalità di ricerca di clienti predefinita** nel profilo funzionalità POS. Quando è impostata su **Sì**, ogni tentativo di ricerca di clienti eseguirà quindi una chiamata in tempo reale alla sede centrale.

Per impedire problemi imprevisti relativi alle prestazioni, questa configurazione è nascosta dietro a un flighting flag denominato **CUSTOMERSEARCH_ENABLE_DEFAULTSEARCH_FLIGHTING**. Pertanto, per visualizzare l'impostazione **Modalità di ricerca di clienti predefinita** nell'interfaccia utente, il rivenditore deve creare una richiesta di supporto per il relativo test di accettazione utente (UAT) e gli ambienti di produzione. Dopo il ricevimento della richiesta, il team di progettazione collaborerà con il rivenditore per assicurare che questi esegua il test nei relativi ambienti non di produzione per valutare le prestazioni e implementare le eventuali ottimizzazioni necessarie.

## <a name="cloud-powered-customer-search"></a>Ricerca di clienti basata su cloud

L'anteprima pubblica della funzionalità di ricerca di clienti che utilizza il servizio Azure Cognitive Services è stata rilasciata come parte della versione 10.0.18 di Commerce. Oltre ai miglioramenti delle prestazioni, gli utenti del servizio beneficiano anche di funzionalità di affinamento e di ricerca per pertinenza avanzate e migliorate. I miglioramenti delle prestazioni sono particolarmente evidenti quando si utilizza la funzionalità di ricerca globale ("Cerca in tutti i negozi") del POS. Questo perché i risultati della ricerca vengono recuperati dall'indice di ricerca di Azure anziché essere sottoposti a query nei dati in Commerce Headquarters. 

### <a name="enable-the-cloud-powered-search-feature"></a>Abilitare la funzionalità di ricerca basata su cloud

> [!NOTE]
> È necessario che Commerce Headquarters e Commerce Scale Unit siano aggiornati alla versione 10.0.18. Non è necessario aggiornare il POS.

Per abilitare la funzionalità di ricerca basata su cloud in Commerce Headquarters, seguire questi passaggi.

1. Andare a **Amministrazione sistema \> Aree di lavoro \> Gestione funzionalità**.
1. Trovare e selezionare la funzionalità **(Anteprima) Ricerca di clienti basata su cloud**, quindi selezionare **Abilita ora**.
1. Andare a **Retail e Commerce > Impostazione sedi centrali > Pianificatore di commercio> Inizializza utilità di pianificazione di commercio** e selezionare **OK** per visualizzare il nuovo processo **1010_CustomerSearch** nel modulo **Programma della distribuzione**.
1. Selezionare **Retail e Commerce > Vendita al dettaglio e commercio IT > Programmazione della distribuzione**.
1. Eseguire il processo **1010_CustomerSearch**. Questo processo pubblica la data nell'indice di ricerca di Azure. Al termine della pubblicazione dell'indice, lo stato del processo sarà **Applicato**.
1. Quando lo stato del processo **1010_CustomerSearch** diventa **Applicato**, eseguire il processo **1110 - Configurazione globale** per aggiornare i canali POS della funzionalità appena abilitata in **Gestione funzionalità**.
1. Successivamente, eseguire il processo **1010_CustomerSearch** a intervalli regolari per inviare gli aggiornamenti dei clienti all'indice di ricerca.

> [!NOTE]
> Per la pubblicazione dell'indice iniziale, il completamento del processo **1010_CustomerSearch** può richiedere alcune ore poiché invierà tutti i record cliente all'indice di ricerca di Azure. Gli aggiornamenti successivi dovrebbero durare alcuni minuti. Nel periodo di tempo in cui la funzionalità di ricerca basata su cloud è abilitata ma la pubblicazione dell'indice non è ancora completata, per la ricerca del cliente dal POS verrà utilizzata la ricerca basata su SQL esistente. Ciò garantisce che non vi siano interruzioni per memorizzare le operazioni.

### <a name="functional-differences-from-the-existing-search"></a>Differenze funzionali rispetto alla ricerca esistente

Il seguente elenco mostra come la funzionalità di ricerca di clienti basata su cloud differisce dalla funzionalità di ricerca esistente. 

- I clienti creati e modificati in Commerce Headquarters vengono inviati all'indice di ricerca di Azure quando viene eseguito il processo **1010_CustomerSearch**. Questi aggiornamenti dell'indice richiedono almeno 15-20 minuti. Gli utenti POS potranno cercare nuovi clienti (o cercare in base alle informazioni aggiornate) circa 15-20 minuti dopo gli aggiornamenti in Commerce Headquarters. Se il processo aziendale richiede che i clienti creati in Commerce Headquarters siano immediatamente ricercabili nel POS, questo potrebbe essere il servizio appropriato.
- I nuovi clienti creati nel POS vengono inviati all'indice di ricerca di Azure da Commerce Scale Unit e sono immediatamente disponibili per la ricerca in qualsiasi punto vendita. Tuttavia, se la funzionalità di creazione di clienti asincroni è attivata, i nuovi record cliente non verranno pubblicati nell'indice di ricerca di Azure da Commerce Scale Unit e non saranno ricercabili dal POS fino a quando le informazioni sul cliente non saranno sincronizzate con Commerce Headquarters e gli ID cliente non saranno generati per i clienti asincroni. Il processo **1010_CustomerSearch** sarà quindi in grado di inviare record cliente asincrono all'indice di ricerca di Azure. In media, ci vorranno circa 30 minuti prima che i clienti asincroni appena creati possano essere cercati nel POS. Questa stima presuppone che i processi **1010_CustomerSearch**, **P-processo** e **Sincronizza clienti e partner commerciali dalla modalità asincrona** siano pianificati per essere eseguiti ogni 15 minuti.
- La ricerca basata su cloud cerca anche le gli indirizzi e-mail e i numeri di telefono secondari dei clienti, ma attualmente i risultati della ricerca visualizzano solo il numero di telefono principale e l'indirizzo e-mail principale dei clienti. A prima vista può sembrare che siano stati restituiti risultati di ricerca irrilevanti, ma controllare l'indirizzo e-mail e il numero di telefono secondari di un cliente nei risultati di ricerca può aiutare a determinare se la parola chiave cercata ha prodotto una corrispondenza con il cliente. Per evitare tale confusione, esistono piani per migliorare la pagina dei risultati di ricerca per consentire agli utenti di comprendere il motivo per cui è stato restituito un risultato di ricerca.
- Il requisito di ricerca che utilizza almeno 4 caratteri in una ricerca globale ("Cerca in tutti i punti vendita") non è applicabile a questo servizio.

> [!NOTE]
> La funzionalità di ricerca di clienti che usa il servizio Azure Cognitive Services è disponibile in aree limitate per l'anteprima. La funzionalità di ricerca di clienti *non* è disponibile nelle seguenti aree geografiche:
> - Brasile
> - India

[!INCLUDE[footer-include](../includes/footer-banner.md)]
