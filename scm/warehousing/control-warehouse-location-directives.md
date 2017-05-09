---
title: Controllare il lavoro di magazzino utilizzando i modelli di lavoro e le direttive ubicazione
description: Questo articolo descrive come utilizzare i modelli di lavoro e le direttive di ubicazione per stabilire come e dove effettuare il lavoro nel magazzino.
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: WHSLocDirFailure, WHSLocDirHint, WHSLocDirTable, WHSLocDirTableUOM, WHSRFMenuItem, WHSWork, WHSWorkClass, WHSWorkPool, WHSWorkTemplateTable
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 72921
ms.assetid: 377ab8af-5b0c-4b5e-a387-06ac1e1820c0
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: f77012e7b64b7f153103e9bbe91e8ded202b509a
ms.openlocfilehash: 64bcea1f305d67c01967184596a58a48a002cf48
ms.lasthandoff: 03/31/2017


---

# <a name="control-warehouse-work-by-using-work-templates-and-location-directives"></a>Controllare il lavoro di magazzino utilizzando i modelli di lavoro e le direttive ubicazione

[!include[banner](../includes/banner.md)]


Questo articolo descrive come utilizzare i modelli di lavoro e le direttive di ubicazione per stabilire come e dove effettuare il lavoro nel magazzino.

Le istruzioni che gli addetti al magazzino ricevono su un dispositivo mobile sono determinate dai modelli di lavoro impostati in Microsoft Dynamics 365 for Operations per definire i diversi processi e le diverse attività di magazzino. I modelli di lavoro determinano la modalità secondo cui il lavoro viene eseguito per ogni processo di magazzino. Collegando una direttiva di ubicazione ai modelli di lavoro, è possibile garantire che il lavoro venga effettuato nelle aree fisiche specifiche del magazzino.

## <a name="work-templates"></a>Modelli di lavoro
La pagina **Modelli di lavoro** consente di definire le operazioni di lavoro che devono essere eseguite nel magazzino. In genere, le operazioni di lavoro sono costituite da una coppia di azioni: un lavoratore di magazzino preleva le scorte disponibili da un'ubicazione quindi colloca le scorte prelevate in un'altra ubicazione. 

I modelli di lavoro sono composti da un'intestazione e dalle righe collegate. Ogni modello di lavoro è destinato a uno specifico *tipo di ordine di lavoro*. Molti tipi di ordine di lavoro sono associati ai documenti di origine, ad esempio ordini fornitore oppure ordini cliente. Tuttavia, altri tipi di ordine di lavoro rappresentano processi di magazzino distinti, ad esempio il conteggio di ciclo di lavorazione. Gli *ID pool di lavoro *consentono di organizzare il lavoro in gruppi. 

Le impostazioni nella definizione dell'intestazione di lavoro possono essere utilizzate per determinare quando un nuovo lavoro deve essere creato. Ad esempio, è possibile impostare un numero massimo di righe di prelievo e un tempo massimo previsto per il prelievo. Quindi, se il lavoro per un processo di prelievo ordine cliente supera uno di questi due valori, tale lavoro viene suddiviso in due parti. 

Le righe di lavoro per le attività fisiche necessarie per elaborare il lavoro. Ad esempio, per un processo di magazzino in uscita, può essere presente una riga di lavoro per il prelievo degli articoli dal magazzino e un'altra riga per la collocazione degli articoli in un'area di gestione temporanea. Può essere presente quindi una riga aggiuntiva per il prelievo degli articoli dall'area di gestione temporanea e un'altra riga per la collocazione degli articoli in un camion come parte del processo di caricamento. È possibile impostare un *codice della direttiva *nelle righe del modello di lavoro. Un codice della direttiva è collegato alla direttiva di ubicazione e quindi consente di garantire che il lavoro del magazzino venga elaborato nell'ubicazione corretta del magazzino. 

È possibile impostare una query per verificare se un determinato modello di lavoro è utilizzato. Ad esempio, è possibile stabilire un limite in modo da poter utilizzare un determinato modello di lavoro solo in un magazzino specifico. In alternativa, è possibile disporre di più modelli utilizzati per creare il lavoro per l'elaborazione dell'ordine cliente in uscita, a seconda dell'origine vendite. Il sistema utilizza il campo **Sequenza numerica** per determinare l'ordine in cui i modelli di lavoro disponibili vengono valutati. Di conseguenza, se si dispone di una query molto specifica per un determinato modello di lavoro, è necessario assegnare un numero progressivo basso. Tale query verrà valutata prima di altre query più generali. 

Per interrompere o sospendere un processo di lavoro, è possibile utilizzare l'impostazione **Interrompi lavoro** della riga di lavoro. In tal caso, al lavoratore che esegue il lavoro non verrà richiesto di eseguire il passaggio successivo della riga di lavoro. Per passare al passaggio successivo, il lavoratore o un altro lavoratore dovrà selezionare di nuovo il lavoro. È inoltre possibile separare le attività all'interno di un lavoro utilizzando un diverso *ID classe di lavoro *nelle righe del modello di lavoro.

## <a name="location-directives"></a>Direttive ubicazione
Le direttive ubicazione sono regole che aiutano a identificare le ubicazioni di prelievo e stoccaggio per il movimento scorte. Ad esempio, in una transazione dell'ordine cliente, la direttiva ubicazione determina il punto di prelievo e il punto di stoccaggio degli articoli. Le direttive di ubicazione sono costituite dall'intestazione e dalle righe associate e possono essere create nella pagina **Direttive ubicazione**. 

Nell'intestazione, ogni direttiva ubicazione deve essere associata con un *tipo ordine di lavoro *per specificare il tipo di transazione di magazzino per cui la direttiva verrà utilizzata, ad esempio ordini cliente, rifornimento o prelievo delle materie prime. Il *tipo di lavoro *specifica se la direttiva ubicazione verrà utilizzata per il prelievo, per la collocazione o per un altro processo di magazzino, ad esempio il conteggio o le modifiche di stato delle scorte. È inoltre necessario specificare il *sito *e un *magazzino*. Un *codice della direttiva *specificato nell'intestazione può essere utilizzato per collegare la direttiva ubicazione a uno o più modelli di lavoro. 

Per quanto riguarda i modelli di lavoro, è possibile impostare una query per determinare quando una direttiva ubicazione specifica viene utilizzata. Ad esempio, è possibile specificare che quando il commercio elettronico è all'origine di un ordine cliente, le scorte devono essere prelevate da un'area dedicata nel magazzino. Il sistema utilizza il campo **Sequenza numerica** per determinare l'ordine in cui le direttive ubicazione disponibili vengono valutate. 

Le righe delle direttive ubicazione impostano restrizioni aggiuntive sull'applicazione delle regole di individuazione dell'ubicazione. È possibile specificare una quantità minima e una quantità massima a cui la direttiva deve essere applicata e specificare che la direttiva deve essere destinata a un'unità di magazzino specifica. Ad esempio, se l'unità di misura sono i pallet, gli articoli in pallet potranno essere stoccati in un'ubicazione specifica. È inoltre possibile specificare se la quantità può essere suddivisa tra più ubicazioni. Come l'intestazione della direttiva ubicazione, ciascuna riga direttiva ubicazione ha un numero progressivo che determina l'ordine in cui vengono valutate le righe. 

Le direttive ubicazione hanno un livello di dettagli aggiuntivo: *le azioni di direttiva ubicazione*. È possibile definire più azioni direttive ubicazione per ciascuna riga. Ancora una volta, viene utilizzato un numero progressivo per determinare l'ordine in cui le azioni vengono valutate. A questo livello, è possibile impostare una query per definire come individuare la migliore ubicazione nel magazzino. È inoltre possibile utilizzare le impostazioni **Strategia **predefinite per trovare un'ubicazione ottimale.

### <a name="example-of-the-use-of-location-directives"></a>Esempio di utilizzo delle direttive ubicazione

Per questo esempio, considereremo un processo di ordine fornitore in cui la direttiva ubicazione deve individuare capacità libera all'interno di un magazzino per gli articoli di magazzino registrati immediatamente alla banchina di entrata. Innanzitutto, si cerca capacità libera all'interno del magazzino consolidando le scorte disponibili esistenti. Se il consolidamento non è possibile, si cerca di individuare un'ubicazione vuota. 

Per questo scenario, dobbiamo definire due azioni di direttiva ubicazione. La prima azione nella sequenza deve utilizzare la strategia **Consolida** e la seconda deve utilizzare la strategia **Ubicazione vuota senza alcun lavoro in entrata**. A meno che definiamo una terza azione per gestire uno scenario di overflow, sono possibili due risultati in caso non vi sia più capacità in magazzino: il lavoro può essere creato anche se non è definita un'ubicazione o il processo di creazione di lavoro può interrompersi. Il risultato viene determinato dall'impostazione nella pagina **Errori direttiva ubicazione**, in cui è possibile decidere se selezionare l'opzione **Interrompi lavoro in caso di errore direttiva ubicazione** per ogni tipo di ordine di lavoro.




