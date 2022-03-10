---
title: Addebiti automatici avanzati omnicanale
description: In questo argomento vengono descritte le funzionalità per la gestione di altre spese ordine relative agli ordini dei canali di commercio utilizzando funzionalità di addebiti automatici avanzati.
author: hhaines
ms.date: 03/30/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: hhaines
ms.search.validFrom: ''
ms.dyn365.ops.version: 10
ms.openlocfilehash: ef6396ec66a0f96ba97b176c46bf70d83a080883cf496312398f14dce3ad9758
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6743433"
---
# <a name="omni-channel-advanced-auto-charges"></a>Addebiti automatici avanzati omnicanale

[!include [banner](includes/banner.md)]

In questo argomento vengono fornite informazioni sulla configurazione e la distribuzione delle funzionalità di addebiti automatici avanzati disponibili in Dynamics 365 for Retail versione 10.0.

Quando le funzionalità di addebiti automatici avanzati sono abilitate, per gli ordini creati in qualsiasi canale di commercio (POS, servizio clienti e online) è possibile utilizzare le configurazioni degli [addebiti automatici](/dynamics365/unified-operations/retail/configure-call-center-delivery#define-charges-for-delivery-services) definite nell'applicazione ERP per le spese correlate a livello di riga e intestazione.

Nelle versioni precedenti alla versione 10.0 di Retail, le configurazioni di [addebiti automatici](/dynamics365/unified-operations/retail/configure-call-center-delivery#define-charges-for-delivery-services) sono accessibili solo tramite ordini creati nei canali e-Commerce e servizio clienti. Nelle versioni 10.0 e successive, gli ordini creati dal POS possono utilizzare le configurazioni degli addebiti automatici. In tal modo, le spese varie extra possono essere aggiunte in modo sistematico alle transazioni di vendita.

Quando si utilizzano le versioni precedenti alla versione 10.0, a un utente POS viene richiesto di immettere manualmente le spese di spedizione durante la creazione di una transazione POS "Spedisci tutto" o "Spedizione selezionata". Sebbene le funzionalità relative alle spese varie dell'applicazione siano utilizzate secondo il modo in cui le spese sono scritte nell'ordine, non viene fornito un calcolo sistematico; il calcolo è basato sull'input dell'utente per determinare il valore delle spese. Le spese possono essere aggiunte solo come singolo codice spese relativo alla "spedizione" e non possono essere modificate facilmente nel POS dopo la creazione.

L'utilizzo di richieste manuali per l'aggiunta di spese di spedizione è ancora disponibile nelle versioni 10.0 e successive. Se un'organizzazione non abilita il parametro **Spese automatiche avanzate**, le richieste POS per l'immissione manuale delle spese rimarranno invariate.

Con le funzionalità di addebiti automatici avanzati, gli utenti POS possono avere calcoli sistematici per qualsiasi spese varie definite basate sulle tabelle di impostazione degli addebiti automatici. Inoltre, gli utenti avranno la possibilità di aggiungere o modificare un numero illimitato di spese e commissioni aggiuntive a una transazione di vendita POS a livello di riga o intestazione (per un ordine cliente o cash and carry).

## <a name="enable-advanced-auto-charges"></a>Abilitare gli addebiti automatici avanzati

Nella pagina **Retail e Commerce \> Impostazione sedi centrali \> Parametri \> Parametri di commercio**, passare alla scheda **Ordini cliente**. Nella scheda Dettaglio **Addebiti**, immettere **Utilizza addebiti automatici avanzati** su **Sì**.

![Parametro Addebiti automatici avanzati.](media/advancedchargesparameter.png)

Quando gli addebiti automatici avanzati sono abilitati, agli utenti non viene più richiesto di immettere manualmente le spese di spedizione nel terminale POS quando si crea un ordine cliente con Spedisci tutto o Spedizione selezionata. Le spese ordine POS sono calcolate in modo sistematico e aggiunte alla transazione POS (se viene trovata una tabella di addebiti automatici corrispondente che soddisfa il criterio dell'ordine creato). Gli utenti possono anche aggiungere o gestire le spese a livello di riga o intestazione manualmente mediante operazioni POS aggiunte di recente che possono essere aggiunte ai layout dello schermo POS.

Quando gli addebiti automatici avanzati sono abilitati, i **parametri di commercio** esistenti per **Codice spese di spedizione** e **Rimborso spese di spedizione** non sono più utilizzati. Questi parametri sono applicabili solo se il parametro **Utilizza addebiti automatici avanzati** è impostato su **No**.

Prima di abilitare questa funzionalità, assicurarsi di formare i dipendenti, in quanto la funzionalità abilitata modifica il flusso di processo aziendale relativo al modo in cui le spese di spedizione o altre spese sono calcolate e aggiunte agli ordini cliente POS. Assicurarsi di comprendere l'impatto del flusso di processo sulla creazione delle transazioni dal POS. Per gli ordini e-Commerce e del servizio clienti, l'impatto dell'abilitazione degli addebiti automatici avanzati è minimo. Le applicazioni e-Commerce e del servizio clienti continueranno ad avere lo stesso comportamento in relazione alle tabelle di addebiti automatici per calcolare spese di ordine extra. Gli utenti dei canali servizio utenti continueranno ad avere la possibilità di modificare manualmente gli addebiti automatici calcolati dal sistema a livello di riga o intestazione o di aggiungere manualmente ulteriori spese varie a livello di riga o di intestazione.

## <a name="add-pos-operations"></a>Aggiungere operazioni POS

Affinché gli addebiti automatici avanzati funzionino correttamente nell'ambiente dell'applicazione POS sono state aggiunte nuove operazioni POS. Queste operazioni devono essere aggiunte ai [layout dello schermo POS](/dynamics365/unified-operations/retail/pos-screen-layouts) e distribuite ai dispositivi POS quando si distribuiscono gli addebiti automatici avanzati. Se queste operazioni non sono aggiunte, gli utenti non potranno gestire le spese varie nelle transazioni POS e non potranno rettificare o modificare i valori spese calcolati in modo sistematico in base alle configurazioni di addebiti automatici. Si consiglia di distribuire almeno l'operazione **Gestisci spese** al layout POS.

Le nuove operazioni sono descritte di seguito.

- **142 - Gestisci spese** – Utilizzare questa operazione per consentire agli utenti POS di visualizzare e modificare spese varie per la transazione POS aggiunte manualmente o in modo sistematico mediante calcoli degli addebiti automatici.
- **141 - Aggiungi spese intestazione** – Utilizzare questa operazione per consentire all'utente di aggiungere manualmente spese varie a livello di intestazione a qualsiasi transazione di vendita POS (e selezionare il codice spese da utilizzare).
- **140 - Aggiungi spese riga** – Utilizzare questa operazione per consentire all'utente di aggiungere manualmente spese varie a livello di riga a qualsiasi riga di transazione di vendita POS (e selezionare il codice spese da utilizzare).
- **143 - Ricalcola spese** – Utilizzare questa operazione per eseguire un ricalcolo completo delle spese per la transazione di vendita. Qualsiasi addebito automatico sovrascritto dall'utente in precedenza verrà ricalcolato in base alla configurazione corrente del carrello.

Come con le operazioni POS, le configurazioni di protezione possono essere effettuate per richiedere l'approvazione del responsabile per l'esecuzione dell'operazione.

È importante notare che le operazioni POS elencate sopra possono anche essere aggiunte al layout POS anche se il parametro **Utilizza spese automatiche avanzate** è disabilitato. In questo scenario, le organizzazioni avranno ancora il vantaggio di poter visualizzare manualmente le spese aggiunte e di modificarle utilizzando l'operazione **Gestisci spese**. Gli utenti possono anche utilizzare le operazioni **Aggiungi spese intestazione** e **Aggiungi spese riga** per le transazioni POS anche se il parametro **Utilizza spese automatiche avanzate** è disabilitato. L'operazione **Ricalcola spese** è meno funzionale se utilizzata quando **Utilizza spese automatiche avanzate** è disabilitato. In questo scenario, non viene ricalcolato nulla e tutte le spese aggiunte manualmente alla transazione vengono reimpostate su $0.00.

## <a name="use-case-examples"></a>Esempi di casi di utilizzo

In questa sezione vengono presentati casi di utilizzo di esempio allo scopo di facilitare la comprensione della configurazione e dell'utilizzo degli addebiti automatici e delle spese varie nel contesto degli ordini dei canali. Questi esempi illustrano il comportamento dell'applicazione quando il parametro **Utilizza addebiti automatici avanzati** è stato abilitato.

### <a name="auto-charges-header-charges-example"></a>Esempio di spese intestazione con addebiti automatici

#### <a name="use-case-scenario"></a>Scenario del caso di utilizzo

Un rivenditore desidera aggiungere automaticamente le spese di spedizione quando si creano transazioni in qualsiasi canale di commercio che richiedono la spedizione dei prodotti al cliente. Il rivenditore offre due metodi di consegna: Su strada e Via aerea. Se un cliente sceglie la consegna Su strada e il valore dell'ordine è inferiore a $100, il rivenditore vuole addebitare al cliente una spesa di trasporto di $10. Se il valore dell'ordine è superiore a $100 e il cliente sceglie la spedizione via terra, al cliente non saranno addebitate spese di spedizione extra. Se il cliente sceglie la spedizione Via aerea per tutti gli ordini, indipendentemente dal valore totale degli stessi, gli verranno addebitate delle spese di spedizione di $20.

#### <a name="setup-and-configuration"></a>Impostazione e configurazione

Questo scenario richiede la configurazione di due tabelle di addebiti automatici.

Accedere a **Contabilità clienti \> Impostazione spese \> Spese automatiche**.

Configurare due differenti addebiti automatici a livello di intestazione. Configurarne uno per la modalità di consegna "Su strada" e uno per la consegna "Via aerea". Per questo scenario, configurarli per l'utilizzo di "Tutti i clienti".

Per le spese di consegna su strada, nella sezione delle righe della pagina **Spese automatiche**, definire un addebito di $10 che verrà applicato per gli ordini tra $0,01 e $100. Creare un'altra riga spese per indicare che gli ordini superiori a $100,01 non comporteranno spese.

![Esempio di due tabelle di addebiti automatici.](media/headerchargesexample.png)

Per le spese di consegna via aerea, nella sezione delle righe del modulo degli addebiti automatici, definire un addebito di $20 che verrà applicata a tutti gli ordini (per un valore tra $0,01 e $9.999.999).

Inviare le spese a Commerce Scale Unit/database canale di modo che il POS possa utilizzarle eseguendo il processo **1040 - Programmazione della distribuzione**.

#### <a name="sales-processing-for-this-scenario"></a>Elaborazione delle vendite per questo scenario

Dopo il completamento della procedura di configurazione descritta sopra e l'applicazione delle spese al database del canale, qualsiasi ordine cliente o transazione di vendita creato nel POS, nel servizio clienti o nei canali di e-Commerce che hanno i metodi di spedizione Su strada e Via aerea impostati a livello di intestazione utilizzerà tali spese e le applicherà automaticamente alla vendita.

A questo punto, le spese verranno applicate a tutte le transazioni di vendita create nell'ambito della persona giuridica che utilizzano queste modalità di consegna, in quanti non è presente una funzionalità per designare che una configurazione di addebito automatico verrà applicata solo a uno specifico canale di vendita.

Per gli scenari relativi a POS e e-Commerce, poiché non si ha un'"intestazione" definita chiaramente su tali ordini, le spese a livello di intestazione verranno applicate solo se tutte le righe di vendita nella transazione sono impostate per la spedizione con la stessa identica modalità di consegna. Se sono presenti "modalità miste" di evasione nelle transazioni create mediante POS o e-Commerce, soltanto gli addebiti automatici a livello di riga verranno considerati e applicati.

Negli scenari relativi al servizio clienti, l'utente controlla l'impostazione della modalità di consegna nell'intestazione dell'ordine, quindi le spese a livello di intestazione verranno applicate per tali ordini anche se alcune delle righe di vendita sono state configurate per utilizzare una modalità di consegna differente. Le spese a livello di intestazione per gli ordini del servizio clienti saranno sempre basate sulla modalità di consegna definita a livello di intestazione dell'ordine cliente.

### <a name="auto-charges-line-charges-example"></a>Esempio di spese riga con addebiti automatici

#### <a name="use-case-scenario"></a>Scenario del caso di utilizzo 

Un rivenditore desidera aggiungere ulteriori spese al cliente per le commissioni di impostazione quando il cliente acquista un determinato modello di computer. Questo computer richiede ulteriori azioni di configurazione non opzionali che il rivenditore eseguirà per il cliente. Il rivenditore ha informato i clienti che verrà applicata un'ulteriore commissione per questa configurazione. Il rivenditore preferisce gestire le spese relative a questa commissione separatamente dal prezzo di vendita del prodotto per i report finanziari. Una commissione di impostazione di $19,99 verrà addebitata al cliente quando questo specifico computer viene acquistato in un qualsiasi canale.

#### <a name="setup-and-configuration"></a>Impostazione e configurazione

Questo scenario richiede la configurazione di una tabella di addebiti automatici a livello di riga.

Accedere a **Contabilità clienti \> Impostazione spese \> Spese automatiche**.

Impostare il menu a discesa **Livello** su **Riga** e creare un nuovo record di addebiti automatici per tutti i clienti e per lo specifico prodotto o gruppo di prodotti a cui le commissioni di impostazione verranno addebitate.

![Esempio di tabella di addebiti automatici a livello di riga.](media/linechargesexample.png)

Inviare le spese a Commerce Scale Unit/database canale di modo che il POS possa utilizzarle eseguendo il processo **1040 - Programmazione della distribuzione**.

#### <a name="sales-processing-for-this-scenario"></a>Elaborazione delle vendite per questo scenario

Dopo il completamento della procedura di configurazione precedente e l'applicazione delle modifiche al database del canale, qualsiasi ordine cliente o transazione di vendita creata nel POS, nel servizio clienti o nei canali di e-Commerce che include questo articolo genererà una spesa a livello di riga da aggiungere sistematicamente al totale dell'ordine.

A questo punto, le spese verranno applicate a qualsiasi riga di vendita che corrisponde alla configurazione degli addebiti automatici a livello di riga della persona giuridica, in quanto non è presente una funzionalità per configurare un addebito automatico a livello di riga da applicare solo a uno specifico canale di vendita.

### <a name="manual-header-charges-example"></a>Esempio di spese intestazione manuali

#### <a name="use-case-scenario-description"></a>Descrizione dello scenario del caso di utilizzo

Un rivenditore sta facendo un'eccezione ai processi tipici fornendo una speciale consegna a domicilio dei prodotti ai clienti che ordinano prodotti nel punto vendita. Il rivenditore e il cliente hanno concordato che il cliente pagherà una spesa di movimentazione aggiuntiva di $25 per tale servizio. L'incaricato dell'ordine deve aggiungere questa commissione aggiuntiva alla transazione. Poiché la commissione è una commissione di copertura non correlata a un qualsiasi singolo prodotto nell'ordine, verrà utilizzata una spesa intestazione.

#### <a name="setup-and-configuration"></a>Impostazione e configurazione

Verificare che il codice spese che verrà utilizzato in questo scenario sia stato configurato correttamente selezionando **Contabilità clienti \> Impostazione spese \> Spese** per definire un codice spese appropriato per lo scenario.

![Esempi di spese.](media/chargesexample.png)

Se la spesa deve essere considerata come una spesa relativa alla "spedizione" nell'ambito di sconti o promozioni inerenti allo spedizione, impostare **Spese di spedizione** nel codice spese su **Sì**. Se questa spesa può inoltre essere sistematicamente rimborsata durante l'elaborazione di una transazione di reso nell'applicazione POS, impostare **Rimborsabile** su **Sì**. Il flag **Rimborsabile** è applicabile solo quando il parametro **Utilizza addebiti automatici avanzati** è impostato su **Sì**.

Inviare le spese a Commerce Scale Unit/database canale di modo che il POS possa utilizzarle eseguendo il processo **1040 - Programmazione della distribuzione**.

L'operazione **Aggiungi spese intestazione** deve essere configurata nel [layout dello schermo POS](/dynamics365/unified-operations/retail/pos-screen-layouts) di modo che sia possibile chiamare questa operazione (141) tramite un pulsante accessibile all'utente dal POS. Le modifiche al layout dello schermo devono essere distribuite al canale nonché attraverso la funzione di programmazione della distribuzione.

#### <a name="sales-processing-of-manual-header-charges"></a>Elaborazione delle vendite delle spese intestazione manuali

Per eseguire lo scenario nell'applicazione POS, l'utente POS creerà la transazione di vendita come al solito, aggiungendo i prodotti e qualsiasi altra configurazione alla vendita. Prima della riscossione del pagamento, l'utente deve eseguire l'operazione **Aggiungi spese intestazione**, che richiederà all'utente di selezionare un codice spese e di immettere il valore delle spese. Dopo che l'utente ha completato il processo, la spesa viene aggiunta all'ordine cliente come spesa a livello di intestazione.

Questo processo può essere applicato al servizio clienti utilizzando le funzionalità **Spese** presente nella scheda **Vendi** nella barra degli strumenti. Nella pagina **Gestisci spese**, l'utente può aggiungere una nuove riga spese all'intestazione dell'ordine.

### <a name="manual-line-charges-example"></a>Esempio di spese riga manuali

#### <a name="use-case-scenario"></a>Scenario del caso di utilizzo

Un cliente ha richiesto una confezione regalo per due dei cinque articoli nell'ordine cliente. Il rivenditore fornisce questo servizio opzionale per una spesa di $2 per articolo. L'incaricato dell'ordine dovrà aggiungere queste spese agli articoli per i quali è stata richiesta la confezione regalo.

#### <a name="setup-and-configuration"></a>Impostazione e configurazione

Verificare che il codice spese che verrà utilizzato in questo scenario sia stato configurato correttamente selezionando **Contabilità clienti \> Impostazione spese \> Spese** per definire un codice spese appropriato per lo scenario.

Se la spesa deve essere considerata come relativa alla "spedizione" nell'ambito di sconti o promozioni inerenti allo spedizione, impostare **Spese di spedizione** nel codice spese su **Sì**. Se la spesa può inoltre essere sistematicamente rimborsata durante l'elaborazione di una transazione di reso nell'applicazione POS, impostare **Rimborsabile** su **Sì**. Il flag **Rimborsabile** è applicabile solo quando il parametro **Utilizza addebiti automatici avanzati** è impostato su **Sì**.

Inviare le spese a Commerce Scale Unit/database canale di modo che il POS possa utilizzarle eseguendo il processo **1040 - Programmazione della distribuzione**.

L'operazione **Aggiungi spese riga** deve essere configurata nel [layout dello schermo POS](/dynamics365/unified-operations/retail/pos-screen-layouts) di modo che sia possibile chiamare questa operazione (140) tramite un pulsante accessibile all'utente dal POS. Le modifiche al layout dello schermo devono essere distribuite al canale nonché attraverso la funzione di programmazione della distribuzione.

#### <a name="sales-processing-of-the-manual-line-charge"></a>Elaborazione delle vendite delle spese riga manuali

Per eseguire lo scenario nell'applicazione POS, l'utente POS creerà la transazione di vendita come al solito, aggiungendo i prodotti e qualsiasi altra configurazione alla vendita. Prima della riscossione del pagamento, l'utente deve selezionare la riga specifica in cui la spesa verrà applicata dal display dell'elenco di articoli POS ed eseguire l'operazione **Aggiungere spese riga**. All'utente verrà richiesto di selezionare un codice spese e immettere il valore delle spese. Dopo che l'utente ha completato il processo, la spesa viene collegata alla riga e aggiunta al totale dell'ordine come spesa a livello di riga. L'utente può ripetere il processo per aggiungere ulteriori spese riga ad altre righe di articoli nella transazione se necessario.

Lo stesso processo può essere applicato nel call center mediante la funzionalità di "gestione delle spese" nel menu a discesa **Dati finanziari** della sezione **Righe ordine cliente** nella pagina **Ordine cliente**. La selezione di questa opzione aprirà la pagina **Gestisci spese** nella quale l'utente può aggiungere una nuova riga spesa alla transazione.

## <a name="additional-features"></a>Funzionalità aggiuntive

### <a name="editing-charges-on-a-pos-sales-transaction"></a>Modifica delle spese in una transazione di vendita POS

L'operazione **Gestisci spese** (142) deve essere aggiunta al [layout dello schermo POS](/dynamics365/unified-operations/retail/pos-screen-layouts) di modo che un utente possa visualizzare e modificare o sostituire qualsiasi spesa a livello di riga o di intestazione creata manualmente o calcolata dal sistema. Se l'operazione non viene aggiunta, gli utenti non potranno rettificare il valore delle spese nella transazione POS e nemmeno visualizzare i dettagli delle spese come il tipo di codice spese associato alla spesa.

Nella pagina **Gestisci spese** nel POS, l'utente può visualizzare i dettagli relativi alle spese a livello di intestazione o riga. L'utente può utilizzare la funzione **Modifica** disponibile in questa pagina per apportare modifiche all'importo addebitato a una specifica riga spese. Quando una riga spese viene sovrascritta manualmente, non verrà ricalcolata in modo sistematico a meno che l'utente non esegua l'operazione **Ricalcola spese**.

Se l'opzione **Codice motivo forzatura spese** è stata configurata nella pagina di configurazione **Parametri di commercio**, all'utente verrà richiesto di fornire un codice motivo quando le spese vengono modificate nell'applicazione POS.

Se i codici motivo sono stati acquisiti per le spese sovrascritte, un nuovo report è inoltre disponibile per esaminare e controllare tali modifiche. Il report si trova in **Retail e Commerce \> Richieste di informazioni e report \> Storico sostituzione spese**.

### <a name="refunding-charges-on-a-pos-return-transaction"></a>Rimborso delle spese in una transazione di reso POS

Se il parametro **Utilizza addebiti automatici avanzati** è impostato su **Sì**, il parametro di commercio esistente per **Rimborso spese di spedizione** non è più applicabile. Per indicare quali spese devono essere rimborsate in modo sistematico a un cliente quando si utilizzano gli addebiti automatici avanzati, assicurarsi che il codice spese correlato sia stato configurato come **Rimborsabile** nella pagina **Codice spese**. Verificare che le impostazioni siano state sincronizzate ai database dei canali di commercio mediante l'elaborazione della programmazione della distribuzione.

### <a name="refunding-charges-on-a-return-order-transaction"></a>Rimborso delle spese in una transazione ordine di reso

Le spese non vengono rimborsate sistematicamente agli **ordini di reso** creati in Commerce. Agli utenti viene richiesto di selezionare l'opzione **Copia spese** quando si crea l'**ordine di reso**. Se l'opzione **Copia spese** non è selezionata, le spese della transazione di vendita originale non verranno automaticamente rimborsate. Se l'opzione **Copia spese** è stata selezionata, tutte le spese verranno copiate nell'ordine di reso e l'utente può modificare o rimuovere manualmente tutte le spese che non desidera siano rimborsate. Il processo dell'ordine di reso nel servizio clienti attualmente non consente l'utilizzo del flag **Rimborsabile** in **Codice spese**.

### <a name="configuring-pos-receipts-to-show-charges"></a>Configurazione di ricevute POS per visualizzare le spese

I seguenti elementi di ricevuta sono stati aggiunti alla riga e al piè di pagina delle ricevute per supportare la funzionalità di addebiti automatici avanzati.

- **Spese di spedizione riga** – Questo elemento a livello di riga può essere utilizzato per ricapitolare specifici codici spese applicati alla riga di vendita. Solo i codici spese che sono stati contrassegnati come spese di **Spedizione** nella pagina **Codice spese** saranno visualizzati qui.
- **Altre spese riga** – Questo elemento a livello di riga può essere utilizzato per ricapitolare qualsiasi codice spese non di spedizione applicato alla riga di vendita. **Altre spese riga** sono codici spese in cui il flag **Spedizione** nella pagina **Codice spese** non è stato abilitato.
- **Dettagli spese di spedizione ordine** – Questo elemento a livello di piè di pagina visualizza le descrizioni dei codici spese applicati all'ordine che sono stati contrassegnati come spese di **Spedizione** nella pagina di impostazione **Codice spese**.
- **Spese di spedizione ordine** – Questo elemento a livello di piè di pagina mostra il valore in dollari delle spese correlate alla spedizione.
- **Dettagli altre spese ordine** – Questo elemento a livello di piè di pagina visualizza la descrizione dei codici spese applicati all'ordine che non sono stati contrassegnati come spese relative alla spedizione.
- **Altre spese ordine** – Questo elemento a livello di piè di pagina visualizza il valore in dollari delle altre spese non relative alla spedizione.

Si consiglia inoltre l'aggiunta di campi di testo libero al piè di pagina della ricevuta, per definire le aree in cui le spese verranno ricapitolate.

### <a name="preventing-charges-from-being-calculated-until-the-pos-order-is-completed"></a>Impedire il calcolo delle spese fino a che l'ordine POS sia completato

Alcune organizzazioni possono preferire di attendere che l'utente abbia finito di aggiungere tutte le righe di vendita alla transazione POS prima di calcolare le spese. Per impedire il calcolo delle spese quando degli articoli sono aggiunti alla transazione POS, attivare il parametro **Calcolo addebito manuale** nel **profilo funzionalità** utilizzato dal punto vendita. L'attivazione di questo parametro richiederà all'utente POS di utilizzare l'operazione **Calcola totali** una volta completata l'aggiunta dei prodotti alla transazione POS. L'operazione **Calcola totali** avvierà il calcolo di tutti gli addebiti automatici per l'intestazione o le righe dell'ordine come applicabile.

### <a name="charges-override-reports"></a>Report di sostituzione delle spese

Se gli utenti sostituiscono manualmente le spese calcolate o aggiungono una spesa manuale alla transazione, questi dati saranno disponibili per il controllo nel report **Storico sostituzione spese**. Il report è accessibile da **Retail e Commerce \> Richieste di informazioni e report \> Storico sostituzione spese**. È importante notare che i dati necessari per questo report vengono importati dal database del canale in HQ mediante processi di programmazione della distribuzione "P". Di conseguenza, le informazioni sulle sostituzioni appena eseguite nel POS possono non essere immediatamente disponibili in questo report fino a che il processo non ha caricato i dati della transazione del punto vendita in HQ.

## <a name="additional-resources"></a>Risorse aggiuntive

[Abilitare e configurare addebiti automatici per canale](auto-charges-by-channel.md)

[Spese intestazione con ripartizione proporzionale in righe di vendita corrispondenti](pro-rate-charges-matching-lines.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
