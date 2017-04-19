---
title: Strutture di suddivisione del lavoro
description: 
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: ProjWorkBreakdownStructure
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 23861
ms.assetid: 241a0464-0056-4a69-b468-0afbe2d5f3ae
ms.search.region: Global
ms.author: kfend
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: eb32cf1b96dfef75131b8c7541e20a93615a87f7
ms.openlocfilehash: 1666691ec122e65128b74056817a0c40551f49b5
ms.lasthandoff: 03/31/2017


---

# <a name="work-breakdown-structures"></a>Strutture di suddivisione del lavoro



Strutture di suddivisione del lavoro Una struttura di suddivisione del lavoro configura è una descrizione del lavoro che verrà eseguito per un progetto. È una gerarchia di attività che rappresenta la conoscenza da parte del team di progetto della composizione del lavoro e delle dimensione, del costo e della durata di ciascun componente o attività. Una struttura di suddivisione del lavoro presenta tre scopi principali:

-   Descrivere la ripartizione o la composizione del lavoro nelle attività.
-   Programmare il lavoro del progetto
-   Stimare il costo di ciascuna attività.

Il grado di dettaglio in una struttura di suddivisione del lavoro dipende dal livello di accuratezza necessario nelle stime e dal livello di tracciabilità necessario per tali stime. I progetti con tolleranza molto bassa per gli slittamenti nella programmazione o nei costi richiedono in genere una struttura di suddivisione del lavoro più dettagliata e anche una tracciabilità diligente dello stato di avanzamento e dei costi del lavoro rispetto alla struttura di suddivisione del lavoro. Questo tipo di progetto è comune in settori di progettazione e di costruzione. 

Per contro, i progetti in settori quali media e pubblicità, software e infrastruttura IT tendono a una essere di tipo e la produttività è correlata all'esperienza e alla competenza dell'utente che esegue l'attività. Di conseguenza, questi settori utilizzano una struttura di suddivisione del lavoro per ottenere un'approssimazione della dimensione del progetto, non per tenere traccia dello stato di avanzamento del progetto. 

Generare una struttura di suddivisione del lavoro è un processo intensivo in genere eseguito per lungo periodo e che richiede la collaborazione e le informazioni di un'ampia gamma di persone. In questo argomento viene descritto come utilizzare i miglioramenti di WBS in Microsoft Dynamics 365 per le operazioni soddisfacciate le richieste delle stime e di tracciabilità.

## <a name="prerequisites-for-creating-a-wbs"></a>Prerequisiti per creare una struttura di suddivisione del lavoro
Per creare una struttura di suddivisione del lavoro, è necessario poter creare un programma lavori e stimare il costo di lavoro.

### <a name="prerequisites-for-creating-a-work-schedule"></a>Prerequisiti per creare un programma lavori

Per utilizzare le funzionalità complete di programmazione delle funzionalità di WBS, attenersi alle seguenti impostazioni:

1.  Impostare un calendario predefinito e un calendario di progetto:
    1.  ** Fare clic su Gestione progetti e contabilità ** &gt; ** impostazione ** &gt; ** ** programmazione. Nel campo **Calendario di lavoro predefinito**, specificare un calendario predefinito. Questo sarà il calendario di lavoro predefinito per qualsiasi nuovo progetto creato.
    2.  È possibile modificare il calendario predefinito per un progetto specifico. Fare clic sulla pagina dei dettagli del progetto, quindi nella Scheda dettaglio **Team progetto e programmazione** aggiornare il campo **Calendario di programmazione** selezionando un altro calendario.

2.  Impostare i giorni lavorativi e le ore lavorative standard. Il calendario impostato come calendario lavorativo per il progetto verrà utilizzato nella struttura di suddivisione del lavoro per determinare le seguenti informazioni:

-   Giorni lavorativi e ferie
-   Numero di ore lavorative in un giorno

Per impostare i giorni lavorativi e le ore lavorative per il calendario, o creare un nuovo calendario, fare clic su Amministrazione organizzazione ** ** &gt; ** il Ordinarie ** &gt; ** calendari **.

### <a name="prerequisites-for-estimating-the-cost-of-work"></a>Prerequisiti per stimare il costo del lavoro

Per utilizzare le funzionalità complete di stima dei costi della struttura di suddivisione del lavoro, è necessario impostare costi e prezzi di vendita per i lavoratori, categorie di lavoro, spese e commissioni e articoli.

-   Per impostare i prezzi di vendita di manodopera, le spese e le categorie di commissioni, fare clic su ** gestione progetti e contabilità ** &gt; ** l'impostazione ** &gt; ** ** prezzi.
-   Per impostare il costo e il prezzo di vendita degli articoli, utilizzare la pagina **Accordi commerciali** per ogni articolo nella pagina elenco **Prodotti rilasciati** nella gestione delle informazioni sul prodotto.

## <a name="creating-a-wbs"></a>Creazione di una struttura di suddivisione del lavoro
Creare una struttura di suddivisione del lavoro include tre attività:

1.  **Scomposizione del lavoro** Consente di suddividere il lavoro in blocchi o attività gestibili.
2.  **Programma lavori** Consente di stimare il tempo necessario per completare un'attività, impostare le interdipendenze tra le attività e selezionare le date di inizio e di fine delle attività.
3.  **Stima costi** Consente di stimare i costi per ogni attività.

Nelle seguenti sezioni viene descritto come capacità di WBS possono ottenere ulteriori informazioni su ciascuna di queste attività.

### <a name="work-decomposition"></a>Scomposizione del lavoro

Creare una scomposizione o suddivisione del lavoro è in genere il primo passaggio nel processo di creazione di una struttura di suddivisione del lavoro. La funzionalità di WBS supporta le seguenti costruzioni di base per la scomposizione la o decomposizione di lavoro. 

**Attività principale di progetto** L'attività principale del progetto è l'attività di riepilogo di livello superiore per un progetto. Tutte le altre attività del progetto vengono create sotto questa attività. All'attività principale viene sempre assegnato il nome del progetto. Le risorse di lavoro, le date e la durata del nodo principale riepilogano i valori per le attività sottostanti all'attività principale. Non è possibile modificare le proprietà del nodo principale né eliminarlo.

**Attività di riepilogo o contenitore** Un'attività di riepilogo è un'attività con attività secondarie o attività costitutive sottostanti. A un'attività di riepilogo non ha di per sé alcuna risorsa di lavoro o costo. Le risorse di lavoro e il costo di un'attività riepilogo sono rappresentate dalla somma di risorse di lavoro e costo delle attività costitutive. La data di inizio meno recente delle attività costitutive viene utilizzata come data di inizio dell'attività di riepilogo e la data di fine meno recente delle attività costitutive viene utilizzata come data di fine. È possibile modificare il nome dell'attività di riepilogo, ma non è possibile modificare le proprietà di programmazione per risorse di lavoro, date e durata. Se si elimina un'attività di riepilogo, vengono eliminate anche tutte le relative attività costitutive. 

**Attività del nodo foglia** Un'attività del nodo foglia rappresenta il pacchetto di lavoro più granulare del progetto. Un nodo foglia ha risorse di lavoro stimate, un numero pianificato risorse, una data di inizio, una data di fine e una durata pianificate. 

È possibile completare le seguenti operazioni di gerarchia per consentire la creazione di una gerarchia di lavoro o la scomposizione per un progetto. 

**Nuova attività** Qualsiasi nuova attività creata viene automaticamente aggiunta al di sotto del nodo principale e un numero di struttura di suddivisione del lavoro viene automaticamente assegnata all'attività. Il numero di struttura di suddivisione del lavoro rappresenta il livello di attività nella gerarchia. Per le attività nel primo livello sotto l'attività principale del progetto, viene utilizzato uno schema di numerazione 1, 2, 3 e così via. Per le attività sottostanti il primo livello, viene utilizzato uno schema di numerazione 1.1, 1.2, 1.3 e così via. Per ciascun livello aggiunto sotto a un livello precedente, viene aggiunta una nuova serie di numeri preceduti da un punto. 

Attualmente, non è possibile personalizzare la numerazione delle strutture di suddivisione del lavoro. 

**Rientro attività** Quando applica un rientro un'attività, questa diventa figlio dell'attività che la precede. Il numero della struttura di suddivisione del lavoro di una nuova attività figlio verrà ricalcolato automaticamente in base al numero della struttura di suddivisione del lavoro della nuova attività padre. L'attività padre ora è un'attività contenitore o di riepilogo e quindi diventa un rollup delle attività costitutive. 

> [!NOTE] 
> Quando rientrate le attività in un'attività che è un nodo di foglia prima che inizi l'operazione del rientro, l'attività di riepilogo appena creato perda le propri date, lavoro e numero di risorse. Ora utilizza un riepilogo dei valori delle nuove attività costitutive. 

**Attività di rientro negativo** Quando si applica un rientro negativo a un'attività, questa non è più un'attività costitutiva dell'attività padre. Il numero della struttura di suddivisione del lavoro dell'attività verrà ricalcolato automaticamente in modo da riflettere il nuovo livello dell'attività nella gerarchia. Le risorse di lavoro, il costo e le date di attività della precedente attività padre dell'attività vengono ricalcolati per escludere tale attività. 

**Sposta su e Sposta giù** Quando si fa clic su **Sposta su** e **Sposta giù** si modifica la posizione di un'attività nella gerarchia dell'attività padre. La posizione di un'attività non influisce sulle risorse di lavoro, sui costi, sulle date o sulla durata dell'attività. Tuttavia, il numero della struttura di suddivisione del lavoro dell'attività verrà ricalcolato automaticamente in modo da riflettere la nuova posizione dell'attività.

### <a name="schedule-estimation"></a>Stima di programmazione

La stima di programmazione è generalmente il secondo passaggio per la creazione di una struttura di suddivisione del lavoro. Come procedura consigliata, è necessario completare la stima della programmazione dopo aver creato le attività. ** Struttura di suddivisione del lavoro ** pagina in Microsoft Dynamics 365 per l'operazione ha due sezioni. Il riquadro superiore è destinato alla stima della programmazione e il riquadro inferiore include una scheda **Costi e ricavi stimati** da utilizzare per la stima dei costi. 
**Dipendenze attività** In una struttura di suddivisione del lavoro, è possibile creare una relazione delle attività precedenti tra le attività. Quando si assegnano le attività precedenti a un'attività, tale attività può iniziare solo dopo che tutte le relative attività precedenti sono completate. La data di inizio pianificata dell'attività viene automaticamente impostata sulla data più recente di tutte le relative attività precedenti. 

** Attività della programmazione in Microsoft Dynamics 365 per le operazioni ** i fattori seguenti determinano la programmazione delle attività del nodo di foglia:

-   Attività precedenti
-   Risorsa
-   Numero di risorse
-   Data di inizio e di fine

La data di inizio di un'attività del nodo foglia senza attività precedenti viene automaticamente impostata sulla data di inizio della programmazione del progetto. La durata di un'attività del nodo foglia viene sempre calcolata come il numero di giorni lavorativi tra le relative date di inizio e di fine. 

Programmazione dei **** regolano il **** l'assistenza automatica di programmazione abilitata, le regole seguenti viene applicata all'attività di programmazione per le attività del nodo di foglia:

-   La data di inizio e di fine di un'attività devono essere giorni lavorativi, in base al calendario di programmazione del progetto.
-   La data di inizio di un'attività con attività precedenti viene automaticamente impostata sulla data di fine più recente delle relative attività precedenti.
-   Le risorse di lavoro di un'attività vengono automaticamente calcolate nel modo seguente:

Numero × di durata × del numero di persone di ore in un giorno lavorativo standard nel calendario del progetto. 

In alcuni casi, potrebbe essere utile deviare da tali regole. È possibile disattivare la programmazione automatica per impedire Microsoft Dynamics 365 per le operazioni automaticamente le impostazioni o la rettifica delle proprietà delle attività del nodo di foglia. Quando si immettono informazioni per un'attività che genera una violazione di tutte le regole di programmazione, viene visualizzata un'icona di errore di programmazione per l'attività. Se non si desidera che gli errori di programmazione vengano visualizzati, fare clic su **Gli errori di programmazione sono visualizzati** per disattivare la funzionalità. 

> [!NOTE] 
> I valori per un'attività del contenitore Riepilogo o continuano a essere calcolati come somma dei valori delle attività costituenti, indipendentemente da l assistenza automatica di programmazione è girata inserita/disinserita. 

**Correzione degli errori di programmazione** Quando l'assistenza per la programmazione automatica è attivata, è meno probabile che si verifichino gli errori di programmazione. Tuttavia, se si disattiva l'assistenza per la programmazione automatica quindi attiva di nuovo, è possibile che le icone di errore di programmazione vengano visualizzate lo struttura di suddivisione del lavoro. 

**Correzione degli errori di programmazione per attività** Quando di fa doppio clic sull'icona di errore di programmazione per un'attività specifica, in una finestra di dialogo vengono visualizzati tutti gli errori di programmazione per tale attività. È possibile decidere quali errori di programmazione correggersi per l'attività. 

** Riparando tutti gli errori di programmazione ** se si desidera che Microsoft Dynamics 365 per le operazioni ripariate tutti gli errori di programmazione nel WBS, nel riquadro azioni, fare clic su ** correggere le eventuali discrepanze di programmazione **. 

> [!NOTE] 
> Questa funzionalità può causare le modifiche significative al WBS. Gli errori vengono corretti nel seguente ordine:

1.  Lo sforzo stimato in tutte le attività viene modificato in modo che sia uguale alla capacità definita nel calendario di progetto.
2.  La data di inizio di ciascuna attività viene modificata in modo che l'attività cominci dopo che tutte le relative attività precedenti sono completate.
3.  La data di inizio di ciascuna attività viene modificata per rimuovere le pause tra le date di inizio delle attività precedenti.

### <a name="cost-estimation"></a>Stima costi

Come indicato in precedenza nel documento, si immette la stima dei costi per ciascuna attività del nodo foglia utilizzando la scheda **Costi e ricavi stimati** nel riquadro inferiore della pagina **Struttura di suddivisione del lavoro**. 

> [!NOTE] 
> Non è possibile modificare la stima dei costi per un'attività del contenitore o riepilogativo. La stima dei costi per un'attività di riepilogo corrisponde alla somma della stima dei costi delle relative attività del nodo foglia. Il costo totale stimato per ogni attività viene calcolato come la somma degli importi dei costi stimati per i seguenti tipi di transazione:

-   Manodopera
-   Articolo o materiale
-   Spese

Un tipo di transazione **Commissione** viene utilizzato per stimare i ricavi in base a commissione. Questo tipo di transazione non ha un componente costi e pertanto non viene considerato per la stima dei costi. 

Un tipo di transazione **Acconto** viene utilizzato per registrare il valore delle vendita con contratto in un tipo di progetto a valore fisso. Anche questo tipo di transazione non viene considerato per la stima dei costi. 

Quando si stimano i costi di manodopera, materiali e spese per ogni attività, è necessario assegnare una categoria di progetto al costo stimato. 

**Stimare i costi di manodopera** Per ogni attività del nodo foglia, assegnare risorse di lavoro in termini di ore e una categoria predefinita. Pertanto, quando si imposta una programmazione per un'attività, la stima dei costi di manodopera per tale attività viene aggiunta automaticamente alla categoria predefinita di manodopera. La stima dei costi viene visualizzata nella scheda **Costi e ricavi stimati** nella griglia **Dettagli riga** per tale attività. Se si richiedono stime dei costi di manodopera, è possibile aggiungerle nella scheda. Se si aumentano o si riducono le ore nella stima dei costi di manodopera, la programmazione per l'attività viene automaticamente ricalcolata. 

**Stimare i costi di materiale e spese** La scheda **Costi e ricavi stimati** consente anche di stimare i costi di materiale e spese per un'attività, se sono necessarie stime. 

Il prezzo di costo e di vendita per ogni riga di stima dei costi o di manodopera sono basati sull'impostazione definita per ogni categoria nelle tabelle di valutazione ** Gestione progetti e contabilità ** &gt; ** all'impostazione ** &gt; ** valutazione **. Per gli articoli, i prezzi di vendita e di costo vengono aggiunti per impostazione predefinita dagli accordi sugli articoli o commerciali nella pagina elenco **Prodotti rilasciati** nella gestione delle informazioni sul prodotto.

## <a name="tracking-progress-on-the-wbs"></a>Lo stato di avanzamento nella struttura di suddivisione del lavoro
Alcuni settori tengono traccia dello stato di avanzamento di un progetto a un livello molto granulare nella struttura di suddivisione del lavoro, mentre altri tengono traccia dello stato di avanzamento a un livello più alto della struttura di suddivisione del lavoro. In questa sezione viene descritto come utilizzare la tracciabilità dello stato di avanzamento nella struttura di suddivisione del lavoro in base ai requisiti del progetto. 

Microsoft Dynamics 365 per le operazioni nelle seguenti visualizzazioni per il WBS di un progetto: la visualizzazione di pianificazione, visualizzazione di tracciabilità di lavoro e visualizzazione di tracciabilità dei costi.

### <a name="planning-view"></a>Visualizzazione pianificazione

La visualizzazione pianificazione consente di visualizzare la stima pianificata o di base della programmazione e delle informazioni sui costi. Sebbene non siano presenti funzionalità per tenere traccia della versione e della base della struttura di suddivisione del lavoro di un progetto, i valori in questa visualizzazione rappresentano la versione di base. Le sezioni Stima di programmazione e Stima costi di questo argomento descrivono questa visualizzazione e come viene utilizzata per creare una struttura di suddivisione del lavoro.

### <a name="effort-tracking-view"></a>Visualizzazione tracciabilità risorse

La visualizzazione Tracciabilità risorse consente di visualizzare lo stato di avanzamento delle attività nella struttura di suddivisione del lavoro. Confronta le ore effettive accumulate delle risorse di lavoro per un'attività con le ore pianificate delle risorse. Le seguenti formule forniscono i valori nella visualizzazione Tracciabilità risorse:

-   Percentuale di avanzamento = Risorse di lavoro effettive a data corrente ÷ Risorse di lavoro pianificate per l'attività
-   Risorsa rimanente (conosciuto anche come Stima \[a\]completo e così via) = lavoro previsto - risorsa fine effettiva
-   Stima al completamento = Risorse rimanenti + Risorse di lavoro effettive a data corrente
-   Scostamento risorse previsto = Risorsa pianificata - Stima al completamento

La visualizzazione Tracciabilità risorse consente di visualizzare una proiezione dello scostamento risorse per l'attività in base a se Stima al completamento è minore o maggiore delle risorse pianificate:

-   Se Stima al completamento è maggiore delle risorse pianificate, è previsto che per l'attività sia richiesto più tempo di quello originariamente pianificato ed è in ritardo rispetto alla programmazione.
-   Se Stima al completamento è minore delle risorse pianificate, è previsto che per l'attività sia richiesto meno tempo di quello originariamente pianificato ed è in anticipo rispetto alla programmazione.

**Riproiezione delle risorse di lavoro da parte del manager di progetto** Occasionalmente, il manager di progetto o un altro utente che tiene traccia dello stato di avanzamento di un progetto dovrà rivedere le stime originali per un'attività. L'attività può procedere più velocemente o più lentamente di quanto originariamente programmato per diversi motivi. Ad esempio, l'ambito è stato ridotto o i lavoratori hanno meno esperienza di quanto originariamente pianificato. Le proiezioni sono una percezione delle stime da parte di un manager di progetto, in base allo stato corrente in un progetto. In generale, non è necessario modificare i numeri di base, poiché una base di progetto rappresenta un documento pubblicato per la programmazione e la stima dei costi del progetto per cui tutte le parti interessate al progetto si sono accordate. 

Sono disponibili due modi in cui i manager di progetto possono modificare la risorsa sulle attività:

-   Modificare le risorse rimanenti che sono automaticamente impostate per aggiornare le risorse effettive rimanenti per l'attività.
-   Modificare la percentuale di avanzamento che è automaticamente impostata per l'avanzamento effettivo per l'attività.

Entrambi questi approcci causano un ricalcolo di stima di completamento, stima al completamento e percentuale di avanzamento del progetto e dello scostamento risorse previsto per l'attività. Stima di completamento, stima al completamento e percentuale di avanzamento nell'attività di riepilogo vengono anche ricalcolate e il relativo scostamento risorse previsto viene aggiornato. 

**Risorse modificate nelle attività di riepilogo** È possibile modificare le risorse nelle attività contenitore o di riepilogo. Che si modifichino questi valori utilizzando le risorse rimanenti o la percentuale di avanzamento nelle attività di riepilogo, i calcoli vengono effettuati automaticamente nel seguente ordine:

1.  Stima di completamento, stima al completamento e percentuale di avanzamento nell'attività vengono calcolati.
2.  La nuova Stima al completamento viene distribuita alle attività figlio nella stessa proporzione della quantità originale di Stima al completamento.
3.  La nuova Stima al completamento in ogni attività del nodo foglia viene calcolata.
4.  La risorsa rimanente e la percentuale di avanzamento vengono ricalcolati per tutte le attività figlio interessate, in base al nuovo valore di Stima al completamento. Lo scostamento risorse delle attività verrà anche ricalcolato.
5.  La stima al completamento delle attività di riepilogo verrà anche ricalcolata dai nodi foglia.

Fare clic su **Espandi al livello** nella Visualizzazione tracciabilità risorse per impostare il livello in cui tracciare e gestione del struttura di suddivisione del lavoro. La struttura di suddivisione del lavoro viene automaticamente espansa a tale livello nella Visualizzazione tracciabilità risorse ogni volta che viene aperta.

### <a name="cost-tracking-view"></a>Visualizzazione tracciabilità costi

La visualizzazione Tracciabilità costi consente di visualizzare la tracciabilità del consumo di costo per un'attività. In questa visualizzazione, il costo effettivo che è stato speso per un'attività fino alla data corrente viene confrontato con il costo pianificato per l'attività. Le seguenti formule forniscono i valori nella visualizzazione Tracciabilità costi:

-   Percentuale di costo consumata = Costo effettivo fino a data corrente ÷ Costo pianificato per l'attività
-   Costo di completamento = Costo pianificato – Costo effettivo fino a data corrente
-   Stima al completamento = Costo di completamento + Costo effettivo fino a data corrente
-   Scostamento costo previsto = Costo pianificato - Stima al completamento

La visualizzazione Tracciabilità costi consente di visualizzare una proiezione dello scostamento costo per l'attività in base a se Stima al completamento è minore o maggiore del costo pianificato:

-   Se Stima al completamento è maggiore del costo pianificato, è previsto che per l'attività sia richiesto più denaro di quello originariamente pianificato ed è oltre il budget.
-   Se Stima al completamento è minore del costo pianificato, è previsto che per l'attività sia richiesto meno denaro di quello originariamente pianificato ed è sotto il budget.

**Riproiezione del costo da parte del manager di progetto** I manager di progetto devono utilizzare il Costo di completamento per rivedere la stima dei costi originale su un'attività. Il manager di progetto può modificare il valore di Costo di completamento nel costo richiesto per completare l'attività. Se si modifica il valore di Costo di completamento, Costo di completamento, Costo al completamento e Percentuale di costo consumata dell'attività e lo Scostamento costo previsto su un'attività vengono ricalcolati. Costo di completamento, Costo di completamento, Costo al completamento e Percentuale di costo consumata nell'attività di riepilogo vengono anche ricalcolati e il relativo scostamento costo previsto viene aggiornato. 

> [!NOTE] 
> Quando rivedete semplice per un'attività di WBS nella visualizzazione di tracciabilità di sforzo, il ctc dell'attività, EAC, la percentuale del costo consumato e lo scostamento costo previsto tutte vengono ricalcolati nella visualizzazione di tracciabilità dei costi. Tuttavia, le revisioni costi non influiscono sui valori nella visualizzazione Tracciabilità risorse, poiché il costo per tipo di transazione (manodopera, materiali, o spese) o dalla categoria di progetto non viene rivisto. 

**Revisione della proiezione per i costi nelle attività di riepilogo** È possibile rivedere i costi nelle attività di riepilogo e i calcoli si verificano automaticamente nel seguente ordine:

1.  Costo al completamento, Costo do completamento e percentuale di costo consumata nell'attività vengono ricalcolati.
2.  Il nuovo Costo al completamento viene distribuito alle attività figlio nella stessa proporzione del Costo al completamento originale nell'attività.
3.  Il nuovo Costo al completamento per ogni attività viene calcolato.
4.  Il CTS e la percentuale dei costi consumata vengono ricalcolate per le attività figlio interessate, in base al valore di Costo al completamento. Lo scostamento costo delle attività verrà anche ricalcolato.
5.  Il Costo al completamento per tutte le attività di riepilogo viene ricalcolato in base alla modifica.

Fare clic su **Espandi al livello** nella Visualizzazione tracciabilità costi per impostare il livello in cui tracciare e gestione del struttura di suddivisione del lavoro. La struttura di suddivisione del lavoro viene automaticamente espansa a tale livello nella Visualizzazione tracciabilità costi ogni volta che viene aperta.

### <a name="earned-value-management"></a>Gestione valori ottenuti

È possibile utilizzare il metodo (EVM) di costo realizzato per tenere traccia dello stato di avanzamento di un progetto. È possibile visualizzare metriche dei valori ottenuti nel Centro gestione ruolo del manager progetto. Il componente del grafico dei valori ottenuti mostra i valori su scala cronologica del valore pianificato e del costo effettivo. Il valore ottenuto a partire dalla data corrente viene visualizzato come punto. I dati su scala cronologica per il valore ottenuto non sono attualmente disponibili. 

La scala cronologica nel grafico del valore ottenuto viene visualizzata per settimana o mese. In questa sezione vengono descritte i tre pilastri colonne del metodo EVM: valore pianificato, valore ottenuto e costo effettivo. 

**Valore pianificato** In base alla teoria EVM il tracciato del valore pianificato rappresenta la velocità a cui il team del progetto ha pianificato di ottenere il valore del progetto. 

Microsoft Dynamics 365 per le operazioni utilizza il 0:100 che vengono la regola quando traccia il valore previsto. In base alla regola, il valore dell'attività viene registrato nell'attività a partire dalla relativa data di fine. Nessun valore viene registrato finché l'attività non è completata al 100 percento. 

In Gestione progetti e contabilità, è possibile immettere la data di fine dei nodi foglia e il relativo costo pianificato. Quando il grafico del valore pianificato viene visualizzato per settimana, il valore pianificato è riepilogato per settimana per tutte le attività del nodo foglia per la durata del progetto. 

**Valore ottenuto** In base alla teoria EVM il tracciato del valore ottenuto rappresenta la velocità a cui il team del progetto ottiene effettivamente il valore del progetto. 

Microsoft Dynamics 365 per le operazioni utilizza il 0:100 che vengono la regola quando il relativo costo realizzato di mapping. In base alla regola, il valore dell'attività viene registrato nell'attività a partire dalla relativa data di fine. Nessun valore viene registrato finché l'attività non è completata al 100 percento. 

Quando il valore ottenuto viene calcolato, la percentuale dello stato di avanzamento di ogni attività viene considerata. Nella regola 0:100, solo le attività completate in un periodo specificato vengono considerate per il calcolo del valore ottenuto a partire dalla fine del periodo. Il valore ottenuto del progetto viene calcolato per tutte le attività che sono state completate quando il diagramma viene creato. 

> [!NOTE] 
> Attualmente, il sistema per la registrazione di l WBS non ha strutture dati per archiviare le percentuali dello storico di avanzamento in ogni attività. Pertanto, il valore ottenuto può essere dichiarato solo a partire dal momento in cui il cubo viene elaborato. Elaborare regolarmente il cubo per aggiornare i dati del valore ottenuto visualizzati nel Centro gestione ruolo. 

**Costo effettivo** In base alla teoria EVM il tracciato del costo effettivo rappresenta la velocità a cui il denaro viene speso nel progetto. 

Le transazioni registrate in un progetto vengono utilizzate per tracciare la riga di costo effettivo. I costi vengono riepilogati per data. Questi dati vengono utilizzati per rappresentare graficamente i costi effettivi per settimana o mese nel grafico del valore ottenuto.

### <a name="how-to-use-the-concepts-of-planned-value-earned-value-and-actual-cost"></a>Come utilizzare i concetti di valore pianificato, valore ottenuto e costo effettivo

**Scostamento programmazione** Durante la pianificazione, si crea una previsione di lavoro in una sequenza temporale. Di conseguenza, il valore pianificato è la velocità a cui gli addetti alla pianificazione del progetto hanno previsto che il progetto venisse completato. Quando un progetto è in corso, il lavoro viene completato e il progetto ottiene valore. Confrontando il valore pianificato al valore ottenuto, è possibile visualizzare l'andamento del lavoro per un progetto. Il risultato del confronto è denominato scostamento di programmazione. 

Se il valore pianificato per un periodo è maggiore del valore ottenuto, la quantità di lavoro effettuata in un progetto è minore rispetto a quella pianificata. Di conseguenza, il progetto sarà in ritardo rispetto alla programmazione. Poiché il valore pianificato e il valore ottenuto vengono espressi in termini monetari, anche al tempo di ritardo per il progetto verrà assegnato un valore monetario. 

Se il valore pianificato per un periodo è minore del valore ottenuto, la quantità di lavoro effettuata in un progetto è maggiore rispetto a quella pianificata. Di conseguenza, il progetto sarà in anticipo rispetto alla programmazione. Anche al lead time verrà assegnato un valore monetario.

**Scostamento costo** Poiché il valore ottenuto utilizza il prezzo di costo come moltiplicatore, il valore ottenuto indica il costo di lavoro che viene eseguito in un progetto. Durante l'avanzamento di un progetto, il registro delle transazioni fornisce un record del denaro effettivamente speso nel progetto. Confrontando il valore ottenuto al costo effettivo, è possibile visualizzare la quantità di denaro spesa rispetto al valore ottenuto. Il risultato del confronto è denominato scostamento costo. 

Se il costo effettivo che viene speso per un periodo è maggiore del valore ottenuto, è stato speso più denaro di quello guadagnato. Di conseguenza, il progetto è fuori budget. 

Se il costo effettivo che viene speso per un periodo è minore del valore ottenuto, è stato guadagnato più denaro di quello speso. Di conseguenza, il progetto è sotto il budget.

## <a name="wbs-templates"></a>Modelli WBS
È possibile utilizzare la funzionalità relativa ai modelli di WBS per creare modelli standard per i progetti. Se i progetti che la società offre comportano molto lavoro ripetibile, è necessario considerare la possibilità di creare un modello di struttura di suddivisione del lavoro. 

È possibile creare un modello di struttura di suddivisione del lavoro dalla struttura di suddivisione del lavoro di un progetto esistente, in modo che la conoscenza e le procedure consigliate riunite durante la pianificazione di tale progetto possano essere riutilizzate in progetti simili in futuro. Tuttavia, talvolta, può non avere senso salvare l'intera struttura di suddivisione del lavoro come modello. Di conseguenza, è anche possibile creare i modelli da parti della struttura di suddivisione del lavoro di un progetto.

### <a name="saving-a-projects-wbs-as-a-template"></a>Salvataggio della struttura di suddivisione del lavoro di un progetto come modello

Dopo avere creato un modello, è possibile importarlo nella struttura di suddivisione del lavoro di un nuovo progetto nel nodo principale o in qualsiasi attività nella struttura di suddivisione del lavoro del progetto.

### <a name="importing-a-wbs-template-into-a-projects-wbs"></a>Importazione di un modello di struttura di suddivisione del lavoro in una struttura di suddivisione del lavoro del progetto

Quando si importano le attività, le attività nel modello vengono organizzate in base alla data di inizio dell'attività in cui sono importate. Durante l'importazione, le relazioni delle attività precedenti nelle attività del modello verranno utilizzate per calcolare le date di inizio delle attività importate. Il calendario di lavoro standard del progetto di destinazione viene applicato per calcolare le date di fine delle attività importate, in modo che i giorni lavorativi e le ore lavorative standard definiti nel calendario lavorativo del progetto corrente vengano mantenuti. 

Gli importi dei costi e i prezzi di vendita nelle righe di stima si applicano per garantire che i prezzi specifici al progetto o al contratto di progetto abbiano date valide.

### <a name="differences-between-a-projects-wbs-and-a-wbs-template"></a>Differenze tra struttura di suddivisione del lavoro di un progetto e modello di struttura di suddivisione del lavoro

-   Le attività nei modelli di struttura di suddivisione del lavoro non hanno date di inizio e di fine.

I giorni lavorativi e non lavorativi non sono impostati per i modelli di struttura di suddivisione del lavoro.

-   I modelli di struttura di suddivisione del lavoro utilizzano sempre il calendario di programmazione impostato come calendario predefinito per tutti i progetti.

Il calendario di programmazione predefinito viene utilizzato solo per trovare le ore in cui si è fuori in un giorno lavorativo standard.

-   Le relazioni delle attività precedenti non vengono copiate in un modello di struttura di suddivisione del lavoro.

Poiché i modelli di struttura di suddivisione del lavoro non hanno date, la logica della data di inizio basata sulla data di fine di un'attività precedente non è richiesta.

-   Una riga di stima dei costi di manodopera viene creata automaticamente quando un'attività viene creata nel modello di struttura di suddivisione del lavoro. Il prezzo di vendita e l'importo costi vengono copiati dal lavoratore selezionato.

La spesa e i costi degli articoli possono essere creati manualmente, appena possibile nella struttura di suddivisione del lavoro di un progetto.

-   Gli errori di programmazione vengono visualizzati se sono presenti scostamenti dalla seguente formula:

Lavoro richiesto = Numero di risorse × Durata × Numero di ore in un giorno lavorativo standard 

È possibile correggere tutti gli errori di programmazione contemporaneamente facendo clic su **Correggi tutti gli errori di programmazione**. 

In alternativa, è possibile correggere gli errori di programmazione singolarmente facendo clic sull'icona di avviso per ogni attività.

