---
title: Opzioni di programmazione delle operazioni
description: "In questo argomento vengono descritte le opzioni per la programmazione delle operazioni. Questo tipo di programmazione può essere utilizzato per ottenere una stima generale del processo di produzione nel tempo."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ProdSchedule
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 198123
ms.assetid: d680d7be-da64-4132-89fe-ad2fa59afb77
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: ede111a8c7e8fe17b95747aadef30d1af1fea6aa
ms.contentlocale: it-it
ms.lasthandoff: 05/25/2017


---

# <a name="operations-scheduling-options"></a>Opzioni di programmazione delle operazioni

[!include[banner](../includes/banner.md)]


In questo argomento vengono descritte le opzioni per la programmazione delle operazioni. Questo tipo di programmazione può essere utilizzato per ottenere una stima generale del processo di produzione nel tempo.

La programmazione delle operazioni calcola le informazioni seguenti per un ordine di produzione:

-   Le date di inizio e di fine vengono impostate per l'ordine di produzione e per ciascuna operazione.
-   Le risorse vengono assegnate alle operazioni.

Varie impostazioni consentono di determinare la modalità di calcolo delle informazioni relative alla programmazione della produzione. Queste impostazioni vengono definite nella pagina **Programmazione operazioni**. Mediante le seguenti informazioni è possibile descrivere le opzioni di programmazione.

## <a name="operations-scheduling"></a>Programmazione operazioni
### <a name="scheduling-direction"></a>Direzione programmazione

La direzione di programmazione è fondamentale ai fini del processo di programmazione. Una produzione può essere programmata in avanti o a ritroso a partire da qualsiasi data, a seconda dei requisiti di tempi e programmazione.

-   **Programmazione in avanti**: è possibile programmare la produzione per l'avvio al più presto possibile. La produzione può iniziare oggi, domani o in una qualsiasi data futura. La produzione è programmata per iniziare alla prima data possibile ed è pianificata per proseguire in avanti nel tempo fino alla prima data di fine possibile.
-   **Programmazione a ritroso**: è possibile programmare la produzione per l'avvio al più tardi possibile. La programmazione è basata sulla data in cui la produzione deve essere completata ed effettua un conteggio all'indietro dei tempi fino all'ultima data in cui è possibile far partire la produzione senza contravvenire alla scadenza prevista.

Sono disponibili le seguenti opzioni:

-   **Avanti da oggi**: programmazione in avanti dalla data corrente. La data corrente corrisponde alla data di sistema.
-   **Avanti da inizio programmato**: programmazione in avanti da una data di inizio precedente. Se non esiste una programmazione precedente, la direzione della programmazione è in avanti dalla data corrente.
-   **Avanti da data programmazione**: programmazione in avanti dalla data specificata nel campo **Data di programmazione**. Se non si specifica una data, la direzione della programmazione è in avanti dalla data corrente.
-   **Indietro da data consegna**: programmazione a ritroso dalla data di consegna specificata per l'ordine di produzione. Se si seleziona questa opzione ma non viene specificata una data, la data di consegna verrà impostata sulla data corrente.
-   **Indietro da fine programmata**: programmazione a ritroso da una data di fine precedentemente calcolata. Se non esiste una programmazione precedente, la data di fine verrà impostata sulla data corrente.
-   **Indietro da data programmazione**: programmazione a ritroso dalla data specificata nel campo **Data di programmazione**. Se non si specifica una data, viene usata la data corrente. La programmazione a ritroso dalla data di programmazione viene calcolata per l'ordine di produzione l'ultima volta in cui è stato calcolato un fabbisogno. Se per l'ordine di produzione non è stata specificata alcuna data azione, viene usata la data corrente.
-   **Indietro da data ritardo**: programmazione a ritroso dalla data ritardo calcolata per l'ordine di produzione l'ultima volta in cui è stato calcolato il fabbisogno. Se per l'ordine di produzione non è stata specificata alcuna data ritardo, viene usata la data corrente.
-   **Come ultima programmazione**: la direzione di programmazione e la data selezionate vengono salvate per la programmazione operazioni e la programmazione processi. È pertanto possibile selezionare questa opzione per la programmazione successiva. Se non è disponibile alcuna programmazione precedente dell'ordine di produzione, la programmazione sarà a ritroso dalla data di sistema corrente.
-   **Avanti da domani**: programmazione in avanti dalla data corrente più un giorno.
-   **Avanti dal processo precedente**: questa funzione è rilevante solo per la programmazione processi. Se si seleziona questa direzione di programmazione per la programmazione operazioni, l'ordine di produzione è programmato in avanti dalla data corrente. Nella programmazione processi, la programmazione viene definita per un singolo processo e tutti gli altri processi della produzione vengono programmati di conseguenza.
-   **Indietro dal processo precedente**: questa opzione è pertinente solo per la programmazione processi. Se si seleziona questa direzione di programmazione per la programmazione operazioni, gli ordini pianificati verranno programmati a ritroso dalla data corrente. Nella programmazione processi, la programmazione viene definita per un singolo processo e tutti gli altri processi della produzione vengono programmati di conseguenza.

### <a name="scheduling-date"></a>Data di programmazione

Data utilizzata per le direzioni di programmazione **Avanti da data programmazione** e **Indietro da data programmazione**. La programmazione è quindi è a ritroso o in avanti a partire da tale data. Per ulteriori informazioni, vedere la sezione precedente, "Direzione programmazione".

### <a name="recalculate-bom-levels"></a>Ricalcola livelli DBA

Quando si seelziona **Ricalcola livelli DBA**, i livelli della distinta base (DBA) selezionati verranno ricalcolati per garantire l'ordine corretto di programmazione.

## <a name="limitations"></a>Limiti
### <a name="finite-capacity"></a>Capacità limitata

La programmazione dipende dalla disponibilità delle risorse necessarie per completare la produzione. Se la capacità disponibile non è sufficiente, gli ordini di produzione possono essere ritardati o persino interrotti. Se alla programmazione delle operazioni viene applicata la capacità limitata, vengono considerate le prenotazioni della capacità esistente delle risorse e tale capacità viene vista come non disponibile. L'ordine di produzione viene programmato in base alla disponibilità della capacità di risorse necessaria. La programmazione delle operazioni utilizza la sequenza di operazioni specificata per determinare l'ordine delle operazioni nel ciclo di lavorazione produzione. La programmazione delle operazioni consente di prenotare capacità dei gruppi di risorse in base agli orari operativi definiti nel ciclo di lavorazione produzione. La capacità del gruppo di risorse corrisponde alla somma delle capacità disponibili di tutte le risorse in tutti i gruppi risorse.

### <a name="finite-material"></a>Materiale limitato

La programmazione dipende anche dalla disponibilità dei materiali necessari per la produzione. I ritardi nella produzione sono dovuti a volte proprio alla disponibilità insufficiente di componenti. La programmazione può essere basata anche sull'utilizzo dei materiali. Basta specificare i materiali che devono essere disponibili per la produzione anziché i materiali che non sono critici. Questo tipo di programmazione è denominato programmazione con materiale limitato. Se vengono specificati materiali limitati, la produzione viene programmata in base alla disponibilità dei materiali. **Nota:** Quando l'ottimizzazione è basata sia sulla capacità sia sui materiali, la produzione viene calcolata in modo da soddisfare entrambe le limitazioni. La disponibilità della capacità e dei materiali viene pertanto tenuta in considerazione e l'avvio delle operazioni relative all'ordine di produzione non potrà essere programmato fino a quando le capacità e i materiali non saranno disponibili allo stesso tempo e nelle quantità richieste. Selezionare questa casella di controllo se i materiali devono essere considerati limitati durante la programmazione. Se i materiali sono limitati, verrà considerata la copertura del materiale per la programmazione specifica. In altri termini, verranno prese in considerazione le date ritardo calcolate per gli articoli. La programmazione prenota le materie prime ed esplode la produzione corrente. Se la programmazione viene eseguita più volte, l'esplosione e le prenotazioni verranno effettuate soltanto la prima volta. Se si apportano modifiche alla DBA di produzione o al ciclo di lavorazione, la programmazione successiva eseguirà un'esplosione. L'esplosione presuppone che il materiale sia necessario il giorno stesso. Poiché la produzione non viene programmata nel momento in cui si esegue l'esplosione del programma generale, la data corrente viene utilizzata come stima migliore per indicare quando gli articoli saranno disponibili. Viene quindi verificato se gli articoli sono disponibili. In caso affermativo, è possibile soddisfare il fabbisogno della produzione. In caso contrario, verrà generato un ordine pianificato e verrà effettuata una selezione di contropartita per tale ordine. Se per l'ordine pianificato è impostata la stabilizzazione automatica, l'ordine verrà stabilizzato automaticamente per gli acquisti o la produzione. Lo stato della produzione passerà automaticamente allo stato specificato nel campo **Stato produzione richiesto** della finestra di dialogo **Gruppi di copertura**. Se la casella di controllo viene deselezionata, il materiale verrà sempre considerato disponibile. La programmazione non considera pertanto se i materiali sono disponibili nel momento in cui sono richiesti.

### <a name="finite-property"></a>Proprietà limitata

Selezionare questa casella di controllo se la programmazione dei processi deve includere i requisiti di proprietà.

### <a name="keep-production-unit"></a>Mantieni unità di produzione

Selezionare se il motore di programmazione deve programmare solo le risorse che sono già specificate nell'unità di produzione.

### <a name="keep-warehouse-from-resource"></a>Mantieni magazzino dalla risorsa

Selezionare se il motore di programmazione deve programmare solo le risorse che sono collegate al magazzino di input specificato nella risorsa.

## <a name="references"></a>Riferimenti
### <a name="schedule-references"></a>Programma riferimenti

Quando i riferimenti dipendono dagli ordini di produzione, sono noti anche come produzioni secondarie. Le produzioni secondarie possono essere programmate nella programmazione di un ordine di produzione. Selezionare questa casella di controllo se la programmazione delle produzioni secondarie si deve basare sulla programmazione della produzione principale. In relazione alla produzione principale, le produzioni sovrapposte verranno programmate in avanti, mentre quelle sottostanti verranno programmate a ritroso. I riferimenti agli ordini di produzione possono essere visualizzati nel campo **Livello di riferimento** della pagina **Ordini di produzione**.

### <a name="synchronize-references"></a>Sincronizza i riferimenti

È possibile sincronizzare i riferimenti con l'ordine di produzione. Se si seleziona questa opzione, le date delle produzioni secondarie vengono spostate e allineate in modo da adeguarsi alle modifiche apportate alla programmazione dell'ordine di produzione. Se a un ordine di produzione sono associate una o più produzioni secondarie, queste dovrebbero essere programmate con la produzione principale. In questo caso, non sarà possibile avviare la produzione principale prima della fine delle produzioni secondarie correlate. Quindi selezionare questa casella di controllo se la programmazione delle produzioni secondarie si deve basare sugli orari di inizio e fine della programmazione selezionata. È possibile selezionare questa casella di controllo solo se è selezionata anche la casella di controllo **Programma riferimenti**.

## <a name="cancellation"></a>Annullamento
### <a name="cancel-queue-time"></a>Annulla tempo di attesa

Selezionare questa casella di controllo per escludere il tempo di attesa dalla programmazione.

### <a name="cancel-setup"></a>Annulla attrezzaggio

Selezionare questa casella di controllo per escludere il tempo di attrezzaggio dalla programmazione.

### <a name="cancel-process"></a>Annulla processo

Selezionare questa casella di controllo per escludere il tempo di esecuzione dalla programmazione.

### <a name="cancel-overlap"></a>Annulla sovrapposizione

Selezionare questa casella di controllo per escludere il tempo di sovrapposizione dalla programmazione.

### <a name="cancel-transport"></a>Annulla trasporto

Selezionare questa casella di controllo per escludere il tempo di transito dalla programmazione.

## <a name="set-default"></a>Imposta predefinito
È possibile salvare i valori correnti come valori predefiniti. Sono disponibili due opzioni:

-   Imposta come predefinito personale
-   Imposta come predefinito per tutti


<a name="see-also"></a>Vedere anche
--------

[Programmazione operazioni](operations-scheduling.md)




