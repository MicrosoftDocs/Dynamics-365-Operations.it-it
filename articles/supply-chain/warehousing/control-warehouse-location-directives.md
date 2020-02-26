---
title: Controllare il lavoro di magazzino utilizzando i modelli di lavoro e le direttive ubicazione
description: Questo argomento descrive come utilizzare i modelli di lavoro e le direttive di ubicazione per stabilire come e dove effettuare il lavoro nel magazzino.
author: perlynne
manager: AnnBe
ms.date: 02/05/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSLocDirFailure, WHSLocDirHint, WHSLocDirTable, WHSLocDirTableUOM, WHSRFMenuItem, WHSWork, WHSWorkClass, WHSWorkPool, WHSWorkTemplateTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 72921
ms.assetid: 377ab8af-5b0c-4b5e-a387-06ac1e1820c0
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4645cf36201aa1b87c22ba4dbfb1b8d8117f425a
ms.sourcegitcommit: fb7d0efd97754f1ae0b5aa765d0eeb3f57b8078f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/05/2020
ms.locfileid: "3028030"
---
# <a name="control-warehouse-work-by-using-work-templates-and-location-directives"></a>Controllare il lavoro di magazzino utilizzando i modelli di lavoro e le direttive ubicazione

[!include [banner](../includes/banner.md)]

Questo argomento descrive come utilizzare i modelli di lavoro e le direttive di ubicazione per stabilire come e dove effettuare il lavoro nel magazzino.

Le istruzioni che i lavoratori di magazzino ricevono su un dispositivo mobile sono determinate dai modelli di lavoro impostati in Dynamics 365 Supply Chain Management per definire i diversi processi e le diverse attività di magazzino. I modelli di lavoro determinano la modalità secondo cui il lavoro viene eseguito per ogni processo di magazzino. Collegando una direttiva di ubicazione ai modelli di lavoro, è possibile garantire che il lavoro venga effettuato nelle aree fisiche specifiche del magazzino.

## <a name="work-templates"></a>Modelli di lavoro
La pagina **Modelli di lavoro** consente di definire le operazioni di lavoro che devono essere eseguite nel magazzino. In genere, le operazioni di lavoro sono costituite da una coppia di azioni: un lavoratore di magazzino preleva le scorte disponibili da un'ubicazione quindi colloca le scorte prelevate in un'altra ubicazione. 

I modelli di lavoro sono composti da un'intestazione e dalle righe collegate. Ogni modello di lavoro è destinato a uno specifico *tipo di ordine di lavoro*. Molti tipi di ordine di lavoro sono associati ai documenti di origine, ad esempio ordini fornitore oppure ordini cliente. Tuttavia, altri tipi di ordine di lavoro rappresentano processi di magazzino distinti, ad esempio il conteggio di ciclo di lavorazione. Gli *ID pool di lavoro* consentono di organizzare il lavoro in gruppi. 

Le impostazioni nella definizione dell'intestazione di lavoro possono essere utilizzate per determinare quando un nuovo lavoro deve essere creato. Ad esempio, è possibile impostare un numero massimo di righe di prelievo e un tempo massimo previsto per il prelievo. Quindi, se il lavoro per un processo di prelievo ordine cliente supera uno di questi due valori, tale lavoro viene suddiviso in due parti. 

Le righe di lavoro per le attività fisiche necessarie per elaborare il lavoro. Ad esempio, per un processo di magazzino in uscita, può essere presente una riga di lavoro per il prelievo degli articoli dal magazzino e un'altra riga per la collocazione degli articoli in un'area di gestione temporanea. Può essere presente quindi una riga aggiuntiva per il prelievo degli articoli dall'area di gestione temporanea e un'altra riga per la collocazione degli articoli in un camion come parte del processo di caricamento. È possibile impostare un *codice della direttiva* nelle righe del modello di lavoro. Un codice della direttiva è collegato alla direttiva di ubicazione e quindi consente di garantire che il lavoro del magazzino venga elaborato nell'ubicazione corretta del magazzino. 

È possibile impostare una query per verificare se un determinato modello di lavoro è utilizzato. Ad esempio, è possibile stabilire un limite in modo da poter utilizzare un determinato modello di lavoro solo in un magazzino specifico. In alternativa, è possibile disporre di più modelli utilizzati per creare il lavoro per l'elaborazione dell'ordine cliente in uscita, a seconda dell'origine vendite. Il sistema utilizza il campo **Sequenza numerica** per determinare l'ordine in cui i modelli di lavoro disponibili vengono valutati. Di conseguenza, se si dispone di una query molto specifica per un determinato modello di lavoro, è necessario assegnare un numero progressivo basso. Tale query verrà valutata prima di altre query più generali. 

Per interrompere o sospendere un processo di lavoro, è possibile utilizzare l'impostazione **Interrompi lavoro** della riga di lavoro. In tal caso, al lavoratore che esegue il lavoro non verrà richiesto di eseguire il passaggio successivo della riga di lavoro. Per passare al passaggio successivo, il lavoratore o un altro lavoratore dovrà selezionare di nuovo il lavoro. È inoltre possibile separare le attività all'interno di un lavoro utilizzando un diverso *ID classe di lavoro* nelle righe del modello di lavoro.

## <a name="location-directives"></a>Direttive ubicazione
Le direttive ubicazione sono regole che aiutano a identificare le ubicazioni di prelievo e stoccaggio per il movimento scorte. Ad esempio, in una transazione dell'ordine cliente, la direttiva ubicazione determina il punto di prelievo e il punto di stoccaggio degli articoli. Le direttive di ubicazione sono costituite dall'intestazione e dalle righe associate e possono essere create nella pagina **Direttive ubicazione**. 

Nell'intestazione, ogni direttiva ubicazione deve essere associata con un *tipo ordine di lavoro* per specificare il tipo di transazione di magazzino per cui la direttiva verrà utilizzata, ad esempio ordini cliente, rifornimento o prelievo delle materie prime. Il *tipo di lavoro* specifica se la direttiva ubicazione verrà utilizzata per il prelievo, per la collocazione o per un altro processo di magazzino, ad esempio il conteggio o le modifiche di stato delle scorte. È inoltre necessario specificare il *sito* e un *magazzino*. Un *codice della direttiva* specificato nell'intestazione può essere utilizzato per collegare la direttiva ubicazione a uno o più modelli di lavoro. 

Per quanto riguarda i modelli di lavoro, è possibile impostare una query per determinare quando una direttiva ubicazione specifica viene utilizzata. Ad esempio, è possibile specificare che quando il commercio elettronico è all'origine di un ordine cliente, le scorte devono essere prelevate da un'area dedicata nel magazzino. Il sistema utilizza il campo **Sequenza numerica** per determinare l'ordine in cui le direttive ubicazione disponibili vengono valutate. 

Le righe delle direttive ubicazione impostano restrizioni aggiuntive sull'applicazione delle regole di individuazione dell'ubicazione. È possibile specificare una quantità minima e una quantità massima a cui la direttiva deve essere applicata e specificare che la direttiva deve essere destinata a un'unità di magazzino specifica. Ad esempio, se l'unità di misura sono i pallet, gli articoli in pallet potranno essere stoccati in un'ubicazione specifica. È inoltre possibile specificare se la quantità può essere suddivisa tra più ubicazioni. Come l'intestazione della direttiva ubicazione, ciascuna riga direttiva ubicazione ha un numero progressivo che determina l'ordine in cui vengono valutate le righe. 

Le direttive ubicazione hanno un livello di dettagli aggiuntivo: *le azioni di direttiva ubicazione*. È possibile definire più azioni direttive ubicazione per ciascuna riga. Ancora una volta, viene utilizzato un numero progressivo per determinare l'ordine in cui le azioni vengono valutate. A questo livello, è possibile impostare una query per definire come individuare la migliore ubicazione nel magazzino. È inoltre possibile utilizzare le impostazioni **Strategia** predefinite per trovare un'ubicazione ottimale.

## <a name="location-directives-configuration-details"></a>Dettagli della configurazione delle direttive ubicazione 

 ### <a name="sequence-number"></a>Numero progressivo
 
Questo numero indica la sequenza in cui una direttiva ubicazione viene elaborata per il tipo di ordine selezionato. La sequenza può essere modificata usando **Sposta su** e **Sposta giù** nel menu.
 
 ### <a name="work-type"></a>Tipo di lavoro
 
Questo è il tipo di lavoro da eseguire. Il tipo di lavoro disponibile è basato sul tipo di transazione di magazzino che è stato selezionato nel campo **Tipo ordine di lavoro**.
-   **Inserimento** - Un tipo di lavoro uguale a **Inserimento** indica che la direttiva ubicazione troverà l'ubicazione ottimale in cui posizionare o individuare le scorte in ingresso nel sistema, da rettifiche di ricezione, di produzione o di inventario. Può inoltre essere utilizzato per definire un inserimento in un'ubicazione di gestione temporanea o un'ubicazione di spedizione finale.
-   **Prelievo** - Un tipo di lavoro uguale a **Prelievo** indica che il magazzino troverà l'ubicazione ottimale da cui riservare fisicamente le scorte (creare lavoro). Il prelievo può essere completato (la riga di lavoro di prelievo può essere chiusa), anche se il lavoro non viene completato. L'utente può completare il prelievo fisico, che è un passaggio del prelievo. L'utente può quindi annullare da un dispositivo mobile e completare il lavoro in un secondo momento. Tuttavia, l'intestazione del lavoro viene chiusa quando viene completato l'inserimento finale. 
-   **Conteggio, Rettifiche, Personalizzato, Modifica stato magazzino, Compilazione targa, stampa, Modifica stato, Imballa in targhe nidificate** - Queste opzioni non sono utilizzabili in alcuna impostazione di direttiva ubicazione. Si tratta di un'enumerazione, pertanto non esiste alcun filtro connesso al tipo di ordine di lavoro. 

### <a name="directive-code"></a>Codice direttiva

Selezionare il codice della direttiva da associare a un modello di lavoro o un modello di rifornimento. Nel modulo **Codice direttiva** è possibile creare nuovi codici che possono essere utilizzati per le connessioni tra un modello di rifornimento di un modello di lavoro e la direttiva ubicazione. Il codice può essere utilizzato per impostare il collegamento tra una qualsiasi riga del modello di lavoro e la direttiva ubicazione (ad esempio l'hangar o l'ubicazione di gestione temporanea).

Se il codice viene impostato, quando il lavoro viene generato, il sistema non cercherà la direttiva ubicazione in base alla sequenza, ma in base al codice della direttiva. Ciò significa che si può essere più specifici nel modo in cui il modello di posizione viene utilizzato per un determinato passaggio in un modello di lavoro, ad esempio la gestione temporanea dei materiali. 

### <a name="site"></a>Sito

Il campo Sito è obbligatorio poiché la direttiva ubicazione necessita del sito e del magazzino per cui è valida. 

### <a name="warehouse"></a>Magazzino

Il campo Magazzino è obbligatorio poiché la direttiva ubicazione necessita del sito e del magazzino per cui è valida.

### <a name="multiple-sku"></a>Più SKU

Ciò consente più unità di stockkeeping (SKU) in un'ubicazione, ad esempio l'hangar. Se si seleziona **Più SKU**, l'ubicazione di inserimento verrà specificata nel lavoro (come previsto), ma sarà in grado solo di gestire l'inserimento di più elementi (se il lavoro include il prelievo e l'inserimento di SKU diverse, non l'inserimento di una singola SKU). Se non si seleziona **Più SKU**, l'ubicazione di inserimento verrà specificata solo se l'inserimento ha un solo genere di SKU. Per utilizzare entrambe le azioni, è necessario specificare due righe, una con Più SKU attivata e una con Più SKU disattivata. Queste devono avere la stessa struttura e la stessa impostazione. Per le operazioni di inserimento, è necessario disporre di direttive ubicazioni identiche, anche se non si fa distinzione tra più SKU o una singola SKU nell'ID lavoro. È inoltre necessario impostare il prelievo, se si dispone di un ordine con più articoli.

### <a name="sequence-number"></a>Numero progressivo

Immettere la sequenza in cui le righe della direttiva ubicazione vengono elaborate per il tipo di lavoro selezionato. È inoltre possibile modificare la sequenza, se necessario, utilizzando **Sposta su** e **Sposta giù**.

### <a name="fromto-quantity"></a>Quantità da/a

Offre la possibilità di specificare un intervallo di quantità per quando deve essere selezionata la sequenza di griglia intermedia. È possibile specificare l'intervallo Da/A sulla quantità nella rispettiva unità.

### <a name="unit"></a>Unità

È possibile specificare una quantità minima e una quantità massima a cui la direttiva deve essere applicata e specificare che la direttiva deve essere destinata a un'unità di magazzino specifica. Il campo Unità nella riga viene utilizzato solo per valutare le quantità.

Quando si verifica se la riga della direttiva ubicazione è applicabile, questa sarà basata sulla quantità nella rispettiva unità specificata nella riga della direttiva ubicazione. Ogni volta che viene raggiunta una riga della direttiva ubicazione, il sistema tenterà di convertire l'unità della domanda in unità specificata nella riga. Se la conversione UdM non è disponibile, il sistema passerà alla riga successiva. 

### <a name="locate-quantity"></a>Trova quantità

Questa opzione viene utilizzata solo per l'inserimento/individuazione della quantità in magazzino. È solo per il tipo di lavoro di inserimento. I valori validi sono:

-   **Quantità targa** - Quando si valuta se la quantità è compresa negli intervalli "Da" e "A", utilizzare la quantità sulla targa ricevuta.
-   **Quantità in unità** - Quando si valuta se la quantità rientra negli intervalli di quantità "da" e "A", utilizzare la quantità da convertire in unità durante la transazione specifica.
-   **Quantità rimanente** - Quando si valuta se la quantità rientra negli intervalli di quantità "da" e "A", utilizzare la quantità ancora da ricevere nella riga dell'ordine fornitore che attualmente viene archiviata.
-   **Quantità prevista** - Quando si valuta se la quantità rientra negli intervalli di quantità "da" e "A", utilizzare la quantità totale della riga dell'ordine fornitore, indipendentemente da quanto è già stato ricevuto.

### <a name="restrict-by-unit"></a>Limita per unità

Ciò consente di rendere una riga di direttiva ubicazione specifica a un'unità di misura o a più unità di misura. Quando si riserva una quantità, se si vuole riservare solo pallet di uno specifico set di ubicazioni, la sequenza di griglia intermedia restringe quella particolare sequenza a "PL" in modo che qualsiasi quantità inferiore a un pallet non seleziona la sequenza. Selezionare **Limita per unità** per impostare le unità. È inoltre possibile limitare la riga a più di un'unità. Questo sistema funziona solo con le direttive ubicazione di tipo prelievo. 

### <a name="round-up-to-unit"></a>Arrotonda a unità

Questo campo viene utilizzato con il campo **Limita per unità**. Se la riga della direttiva ubicazione **Limita per unità** è impostata su "scatola", la selezione di **Arrotonda a unità** indica che il lavoro generato dalla direttiva per il prelievo di materie prime deve essere arrotondato a più di un'unità di movimentazione (specificata in **Limita per unità**). Notare che questo funziona solo per il prelievo di materie prime e solo con le direttive ubicazione di tipo prelievo.

### <a name="locate-packing-qty"></a>Individua quantità di imballaggio

Se una quantità di imballaggio viene specificata in un ordine cliente, un ordine di trasferimento o un ordine di produzione, il sistema si limita a selezionare solo le ubicazioni con una quantità di imballaggio nella posizione. Questo sistema funziona solo con le direttive ubicazione di tipo prelievo.

### <a name="allow-split"></a>Consenti divisione

Questo specifica se una direttiva ubicazione può suddividere la quantità da ricevere o la quantità di riservare tra più ubicazioni magazzino o se l'intera quantità deve essere individuata in una singola ubicazione o essere riservata da una singola ubicazione per creare il lavoro. 

### <a name="sequence-number"></a>Numero progressivo

Questo numero è la sequenza in cui la direttiva ubicazione viene elaborata per il tipo di lavoro selezionato. Se necessario, è possibile modificare la sequenza. Tuttavia, attenzione a usare i numeri sequenziali, poiché l'elaborazione verrà eseguita sempre in sequenza. 

### <a name="name"></a>Nome

Immettere un nome per l'azione della direttiva ubicazione. Assicurarsi di indicare un nome specifico.

### <a name="fixed-location-usage"></a>Utilizzo ubicazioni fisse 

-   **Posizioni fisse e non fisse** - La direttiva ubicazione considererà tutte le ubicazioni.
-   **Solo ubicazioni fisse per il prodotto** - La direttiva ubicazione considererà solo le ubicazioni fisse per i prodotti.
-   **Solo ubicazioni fisse per la variante prodotto** - La direttiva ubicazione considererà solo le ubicazioni fisse per le varianti prodotti.

### <a name="allow-negative-inventory"></a>Consenti inventario negativo

Selezionare questa opzione per consentire scorte negative nell'ubicazione di magazzino specificata nelle direttive ubicazione. 

### <a name="batch-enabled"></a>Batch abilitato 

Selezionare questa casella di controllo per utilizzare le strategie batch per gli articoli che vengono abilitati per il batch. Se una riga viene raggiunta dove **Batch abilitato** è impostato con nessun articolo batch, il processo passerà alla riga d'azione successiva. 

### <a name="strategy"></a>Strategia

-   **Consolidato** - Questa strategia viene utilizzata per consolidare gli articoli in un'ubicazione specifica quando articoli simili sono già disponibili. Questo sistema funziona solo con le direttive ubicazione di tipo inserimento. L'impostazione comune per l'inserimento sarà di consolidare la prima riga di azione, quindi nel secondo tentativo di inserire senza consolidamento. Il consolidamento delle merci rende più efficiente il prelievo in un secondo momento.
-   **Corrispondenza quantità imballaggio** - Questa strategia troverà un'ubicazione che contiene una targa con l'esatta quantità. Non può essere utilizzata con le ubicazioni che non sono controllate con una targa. Questa strategia funziona solo con le direttive ubicazione di tipo prelievo.
-   **Prenotazione batch FEFO** - Questa strategia viene utilizzata quando il magazzino viene individuato utilizzando una data di scadenza batch e viene allocato per la prenotazione batch. È possibile utilizzare questa strategia solo per gli articoli abilitati per il batch. Questo sistema funziona solo con le direttive ubicazione di tipo prelievo. 
-   **Arrotonda per eccesso alla targa completa** - Questa strategia viene utilizzata per arrotondare la quantità di scorte da abbinare alla quantità di targa assegnata agli articoli da prelevare. È possibile utilizzare questa strategia solo per il tipo di rifornimento della direttiva ubicazione di tipo prelievo. 
-   **Ubicazione vuota senza alcun lavoro in entrata** - Questa strategia viene utilizzata per individuare le ubicazioni vuote. L'ubicazione viene considerata vuota se non è presente un inventario fisico e non è previsto lavoro in entrata. Questa strategia viene utilizzata solo per direttiva ubicazione di tipo inserimento. 

### <a name="example-of-the-use-of-location-directives"></a>Esempio di utilizzo delle direttive ubicazione

Per questo esempio, considerare un processo di ordine fornitore in cui la direttiva ubicazione deve individuare capacità libera all'interno di un magazzino per gli articoli di magazzino registrati immediatamente alla banchina di entrata. Innanzitutto, occorre cercare capacità libera all'interno del magazzino consolidando le scorte disponibili esistenti. Se il consolidamento non è possibile, occorre cercare di individuare un'ubicazione vuota. 

Per questo scenario, è necessario definire due azioni di direttiva ubicazione. La prima azione nella sequenza deve utilizzare la strategia **Consolida** e la seconda deve utilizzare la strategia **Ubicazione vuota senza alcun lavoro in entrata**. A meno che non si definisca una terza azione per gestire uno scenario di overflow, sono possibili due risultati in caso non vi sia più capacità in magazzino: il lavoro può essere creato anche se non è definita un'ubicazione o il processo di creazione di lavoro può interrompersi. Il risultato viene determinato dall'impostazione nella pagina **Errori direttiva ubicazione**, in cui è possibile decidere se selezionare l'opzione **Interrompi lavoro in caso di errore direttiva ubicazione** per ogni tipo di ordine di lavoro.
