---
title: Previsione delle posizioni
description: Le spese relative ai lavoratori costituiscono spesso una grande proporzione dei costi di un'organizzazione. Le previsioni di posizione consentono di pianificare le spese e includerle nella pianificazione di budget.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: HcmPositionForecast
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 64413
ms.assetid: 35e791d2-1905-4808-a579-7f181ddddd91
ms.search.region: Global
ms.author: sigitac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: a44b3d2ee6e47e71103c7be04b731d4faa79c448
ms.contentlocale: it-it
ms.lasthandoff: 03/26/2018

---

# <a name="position-forecasting"></a>Previsione delle posizioni

[!include [banner](../includes/banner.md)]

Le spese relative ai lavoratori costituiscono spesso una grande proporzione dei costi di un'organizzazione. Le previsioni di posizione consentono di pianificare le spese e includerle nella pianificazione di budget.

## <a name="position-forecasting-in-budget-planning"></a>Previsione della posizione nella pianificazione del budget

[![Graphic top](./media/graphic-top.png)](./media/graphic-top.png) 

La previsione della posizione utilizza tre componenti principali per fornire importi di budget accurati per le spese di posizione. Gli importi possono quindi essere introdotti nel piano di budget per i calcoli di budget. 

Il componente principale è la **previsione di posizione**, che rappresenta tutti i dati sui costi correlati a una singola posizione. È possibile creare più versioni di una posizione prevista assegnando un diverso scenario del piano di budget a ciascuna versione. Più versioni consentono un approccio iterativo al budget e un confronto di scenari di simulazione. Ogni posizione prevista ha una posizione corrispondente in Risorse umane.

Un **elemento costo budget** è un componente di configurazione che rappresenta un costo specifico associato a una posizione, ad esempio retribuzione di base, assicurazione sanitaria a carico del datore di lavoro, indennità per uso del cellulare e così via. Un elemento di costo del budget include il conto principale utilizzato per i costi e le opzioni per il calcolo. Ogni elemento costo budget può essere assegnato a più posizioni previste. 

Un **gruppo di retribuzione** è un componente facoltativo di impostazione utilizzato per applicare un set di elementi di costo del budget e per i calcoli della retribuzione per le posizioni con caratteristiche retributive simili. Un gruppo di retribuzione può includere una griglia di retribuzione di tariffe retributive. Quando il gruppo viene assegnato a una posizione prevista, un livello e un passaggio della griglia possono assegnare i redditi della posizione prevista. L'insieme di elementi di costo viene aggiunto automaticamente.

### <a name="position-forecasting-processes"></a>Processi della previsione della posizione

[![graphic1b](./media/graphic1b.png)](./media/graphic1b.png) 

In un tipico processo per la previsione di posizione, è necessario innanzitutto creare i componenti di impostazione (elementi di costo del budget e gruppi di retribuzione). Le posizioni previste vengono quindi generate, in base alle posizioni esistenti. È quindi possibile apportare modifiche in qualsiasi momento. Ad esempio, è possibile aggiungere o terminare posizioni, modificare retribuzioni e benefit e aggiungere aumenti salariali. È possibile creare più versioni di una posizione prevista per agevolare il confronto tra diversi scenari di budget. In seguito, è possibile includere le posizioni previste nei piani di budget e riportare i costi delle posizioni previste come righe del piano di budget.

È possibile creare versioni aggiuntive di posizione prevista quando il piano di budget viene rivisto. Le nuove versioni forniscono una base per le revisioni.

## <a name="position-forecasting-setup"></a>Impostazione della previsione della posizione
[![graphic2](./media/graphic2-1024x327.png)](./media/graphic2.png)

### <a name="budget-cost-elements"></a>Elementi costo budget

Gli elementi di costo budget vengono utilizzati per definire i dettagli di costo per una posizione prevista. Tali informazioni includono il tipo di costo, le modalità di calcolo del costo e se il costo viene allocato a più date quando la posizione prevista viene inclusa in un piano di budget. 

I campi specifici definiscono il comportamento dell'elemento di costo del budget. A ciascun elemento di costo del budget è assegnato un tipo di costo di budget: **Reddito**, **Benefit**, **Imposte** o **Altro**. I tipi di costo di budget vengono utilizzati principalmente per calcolare i totali. Il valore **Sostituzione posizione prevista** specifica se gli importi dell'elemento possono essere modificati nella posizione prevista. Il campo **Metodo di allocazione** viene utilizzato quando una posizione prevista viene aggiunta al piano di budget. È possibile suddividere l'importo costi nelle righe separate di piano di budget con date differenti, su base mensile, trimestrale, settimanale, o quindicinale. Selezionando una data di inizio, è possibile assegnare il costo come singolo importo per la data di inizio che è impostata nella posizione prevista. 

Il calcolo dell'importo del costo dell'elemento del costo di budget utilizza le date di validità per attivare lo stesso elemento di costo da utilizzare in periodi diversi. Un unico conto principale viene assegnato in ogni periodo, insieme a una percentuale o a un importo annuale che indica l'importo costi. Un elemento di costo budget può utilizzare una percentuale di altri elementi di costo o un importo annuale, ma non entrambi. È inoltre possibile specificare un limite annuale. 

Se l'elemento di costo è basato su una percentuale, è necessario specificare gli elementi di costo del budget utilizzati come base per il calcolo.

**Esempio** 

L'organizzazione in cui lavora Jodi prevede un rimborso spese di formazione pari al 5% della retribuzione di base di un dipendente. Jodi desidera creare un elemento di costo del budget per questo costo. Jodi crea un nuovo elemento di costo del budget e assegna **Benefit** come tipo di costo del budget.

Jodi non vuole che i responsabili possano modificare l'importo del benefit. Di conseguenza, seleziona l'opzione **Non consentire modifiche costo** nel campo **Sostituzione posizione prevista**. L'organizzazione desidera che il costo venga assegnato ogni mese in ugual misura. Di conseguenza, Jodi seleziona **Trimestrale** nel campo **Metodo di allocazione**. 

In seguito, Jodi aggiunge una riga di calcolo dei costi, imposta le date e un conto principale e immette **5,00** come percentuale. L'organizzazione ha stabilito un tetto massimo di $ 5.000 all'anno per il benefit. Di conseguenza, Jodi immette tale importo come limite annuale. 

Infine, Jodi aggiunge tutti gli elementi di costo di reddito utilizzati per la retribuzione di base come base di calcolo. Il relativo elemento di costo del budget ora è pronto per essere utilizzato.

### <a name="compensation-groups"></a>Gruppi di retribuzione

I gruppi di retribuzione possono essere utilizzati per raggruppare le posizioni previste con attributi di retribuzione simili. Possono essere utilizzati anche per definire i redditi di una posizione prevista e gli aumenti annuali, oltre che per assegnare un gruppo di elementi di costo comuni del budget. 

La funzione di base dei gruppi di retribuzione è di assegnare un gruppo di articoli di costo di budget a una posizione prevista. Di conseguenza, i gruppi di retribuzione possono essere utilizzati per aggiungere costi comuni, ad esempio i piani di benefit e le imposte. Un responsabile che sta creando una posizione prevista non deve conoscere tutti gli elementi di costo da aggiungere. Gli elementi di costo possono essere aggiunti invece quando si seleziona il gruppo di retribuzione. Gli elementi vengono aggiunti all'impostazione del gruppo di retribuzione nella scheda **Elementi costo budget**. 

I gruppi di retribuzione possono inoltre determinare le tariffe di reddito per una posizione prevista. È possibile impostare un gruppo per utilizzare una base oraria o una base dello stipendio annuale per calcolare i redditi della posizione prevista. Nella scheda **Tabelle scaglioni retributivi**, una griglia di retribuzione di tariffe retributive determina i redditi aggiunti a una posizione prevista, in base a un livello e un passaggio assegnati. Queste griglie possono essere basate su griglie di retribuzione esistenti in Risorse umane. In alternativa, è possibile creare nuove griglie di retribuzione per la pianificazione del budget. 

Le date di validità e di scadenza nelle tabelle scaglioni retributivi consentono di modificare le tariffe in qualsiasi data. Questa funzionalità è utile quando un'unità di contrattazione ha negoziato un incremento generale a metà di un ciclo di budget. In questo caso, si modifica la data di scadenza della tabella esistente al giorno nella data della modifica tariffa e si aggiunge una nuova tabella di tariffe che inizia alla nuova data. Quando si crea una nuova tabella di tariffe, se si seleziona **Crea una nuova griglia di retribuzione da una griglia esistente**, è possibile selezionare una tabella di tariffe esistente da Risorse umane. Nella tabella di tariffa creata, l'opzione **Modifica in massa** consente di applicare una percentuale o un importo forfettario di incremento o diminuzione a tutte le tariffe nella griglia. 

I campi **Programmazione incentivi** e **Data di incentivo** nel gruppo di retribuzione vengono utilizzati quando è necessario creare incrementi di retribuzione poiché le posizioni vanno da un passaggio al successivo. Un incremento di retribuzione annuale è uno scenario tipico. La programmazione incentivi determina se utilizzare la data di ricorrenza annuale della posizione o una singola data comune per l'incremento di passaggio. La programmazione incentivi si applica a tutte le posizioni previste del gruppo di retribuzione. 

L'elemento di costo selezionato nel gruppo di retribuzione viene utilizzato quando si creano redditi per le posizioni previste del gruppo, tra cui le retribuzioni di base e gli incrementi di passaggio. Il campo **Piano di retribuzione fissa** collega il gruppo di retribuzione a un piano di retribuzione fissa in Risorse umane. Questo collegamento consente di assegnare le informazioni di retribuzione fissa di un lavoratore a una posizione prevista e può pertanto realizzare il piano di budget per una pianificazione più accurata. Ricordare che la struttura della griglia di retribuzione (livelli e passaggi) per il gruppo di retribuzione deve corrispondere alla struttura del piano di retribuzione fissa. In caso contrario, il sistema non è viene correttamente collegato al gruppo di retribuzione e al piano di retribuzione fissa.

## <a name="creating-forecast-positions"></a>Creazione delle posizioni previste
[![graphic3](./media/graphic3-1024x327.png)](./media/graphic3.png)

### <a name="creating-forecast-positions-for-existing-positions"></a>Creazione di posizioni previste per le posizioni esistenti

Per una pianificazione più precisa del budget, è possibile creare posizioni previste utilizzando i dettagli delle posizioni esistenti in Microsoft Dynamics 365 for Finance and Operations, indipendentemente dalla posizione attualmente compilata o non compilata. 

La funzione **Aggiungi posizioni esistenti** visualizza tutte le posizioni di un'organizzazione. Impostando la data **A partire dal**, è possibile modificare l'elenco di posizioni in modo che contenga le posizioni lavorative esistenti in una data nel passato o, più comunemente, in futuro, ad esempio, all'inizio del ciclo di budget successivo. Selezionare un processo di pianificazione del budget e uno scenario del piano di budget, selezionare le posizioni dall'elenco e quindi fare clic su **OK** per creare posizioni previste per le posizioni selezionate. Si noti che è possibile creare solo una posizione prevista per ogni posizione esistente in un processo di pianificazione del budget e in uno scenario. Tuttavia, è possibile creare versioni aggiuntive assegnando gli diversi scenari del piano di budget. 

Se gli elementi di costo del budget sono stati assegnati alla posizione in Risorse umane, tali elementi di costo del budget vengono assegnati anche alla posizione prevista e utilizzano gli importi predefiniti. Il campo **Lavoratore assegnato** nella posizione prevista viene impostato sul nome del lavoratore assegnato alla posizione, se un lavoratore è assegnato. Questo campo è un campo di testo semplice. Non viene creato alcun collegamento diretto. 

Se un elemento di costo del budget è selezionato, l'importo annuale di retribuzione fissa viene assegnato alla posizione prevista utilizzando l'elemento di costo selezionato, purché il lavoratore assegnato abbia un piano di retribuzione fissa. Se il lavoratore non ha un piano di retribuzione fissa o se nessun lavoratore è assegnato, viene utilizzato l'importo predefinito per l'elemento di costo del budget. 

Quando l'opzione è **Assegna gruppo di retribuzione** è impostata su **Sì**, se il lavoratore assegnato alla posizione ha un piano di retribuzione fissa in base al passaggio che è collegato a un gruppo di retribuzione (come descritto in precedenza), il livello e il passaggio del lavoratore vengono assegnati alla posizione prevista, insieme al gruppo di retribuzione. L'elemento di costo di budget utili non distribuito del gruppo di retribuzione viene aggiunto alla posizione prevista e vengono utilizzati la tariffa retributiva e il passaggio del gruppo di retribuzione. 

Il valore dell'opzione **Assegna gruppo di retribuzione** ha la priorità rispetto all'impostazione dell'**assegnazione dell'elemento costo budget**. È possibile usare le due impostazioni contemporaneamente. 

[![graphic4](./media/graphic4.png)](./media/graphic4.png) 

Un'altra opzione consiste nell'assegnare una data di anniversario. La data selezionata (data di inizio rettificata, data di inizio lavoratore, data di inizio impiego o data di anzianità) del lavoratore assegnato verrà impostata come data di ricorrenza annuale della posizione prevista e utilizzata per informazioni e durante la generazione degli aumenti retributivi.

### <a name="creating-new-forecast-positions"></a>Creazione di nuove posizioni previste

È possibile creare nuove posizioni previste in due modi: copiando una posizione prevista esistente e creando una posizione prevista completamente nuova. 

Quando una posizione prevista è selezionata, selezionare **Copia posizione prevista selezionata** per creare una nuova posizione prevista con uno stato di previsione **Proposto**. Questa posizione di previsione ha tutti gli stessi dati della posizione prevista copiata, eccetto il lavoratore assegnato e tutte note sugli elementi di costo del budget. Si noti che una nuova posizione corrispondente verrà creata in Risorse umane. Questa posizione ha come descrizione **Creata dalla previsione**. 

È inoltre possibile creare una posizione prevista completamente nuova. Selezionare un processo esistente e selezionare anche un processo di pianificazione del budget e uno scenario del piano di budget. È possibile aggiungere tutti gli altri dettagli da aggiungere. Anche in questo caso, in Risorse umane viene creata contemporaneamente una nuova posizione.

## <a name="working-with-forecast-positions"></a>Utilizzo delle posizioni previste
[![graphic5](./media/graphic5-1024x327.png)](./media/graphic5.png)

### <a name="multiple-versions-of-a-forecast-position"></a>Più versioni di una posizione prevista

È possibile modificare le posizioni previste per applicare le modifiche conosciute per il ciclo di budget o alle modifiche proposte del modello. Un metodo comune consiste nel creare un set di base di posizioni previste, creare le copie di tali posizioni previste e quindi utilizzare le copie per creare modelli di diversi set di modifiche. Le copie vengono assegnate a un diverso scenario del piano di budget ma, almeno fino a che non sono state apportate le modifiche, sono identiche alle posizioni previste da cui sono state copiate. Gli originali e le copie condividono la stessa posizione in Risorse umane. 

La funzione **Copia in scenario** fornisce questa funzionalità. Si noti che ogni posizione delle Risorse umane può avere solo una posizione prevista in ogni scenario del piano di budget.

### <a name="modifying-forecast-positions"></a>Modifica delle posizioni previste

Le modifiche apportate alle posizioni previste sono limitate alle posizioni previste a cui sono state apportate. Le modifiche non influiscono sui record delle posizioni in Risorse umane. La maggior parte delle modifiche vengono limitate alla posizione prevista che viene modificata. Ovvero le modifiche sono specifiche al processo di pianificazione del budget e allo scenario del piano di budget assegnati. Fanno eccezione sono le modifiche ai campi che verranno condivise per la posizione tra i processi e gli scenari. Questi campi includono i campi della scheda **Generale** e della scheda **Dimensioni finanziarie**. Quando questi campi vengono modificati, i nuovi valori vengono applicati alla posizione in tutti gli scenari di pianificazione del budget. Di conseguenza, questi campi consentono di aggiornare velocemente tutte le versioni.

#### <a name="budget-cost-elements"></a>Elementi costo budget

Gli elementi costo budget forniscono le informazioni principali i piani di budget: l'importo del budget e il conto principale. L'importo budget corrisponde all'importo da inviare al piano di budget quando una posizione prevista viene inclusa in un piano. L'importo budget viene calcolato e non può essere direttamente modificato. Questo importo corrisponde all'importo annuale o a un calcolo della percentuale degli elementi di base dell'importo annuale (come definito nell'impostazione dell'elemento di costo budget). L'importo viene quindi moltiplicato per il numero di giorni nell'intervallo di date elemento (dalla data di inizio alla data di fine) e anche per il valore **Equivalente a tempo pieno** (FTE) per la posizione prevista. 

Ad esempio, una riga dell'elemento di costo budget dal 1° gennaio 2017, al 30 giugno 2017, con un importo annuale di 100.000 e un valore FTE di **0,50** viene calcolata come 100.000 × (181 gg ÷ 365 gg) × 0,50 = 24.794,52. 

Le righe dell'elemento di costo budget devono essere ricalcolate quando il valore di FTE viene modificato nella posizione prevista. Le righe devono essere ricalcolate quando le date di attivazione o le date di pensionamento vengono modificate. Le modifiche alle date possono determinare un aggiornamento delle date di inizio e di fine dell'elemento di costo budget, che devono essere comprese tra le date della posizione prevista. Quando è necessario il ricalcolo, il pulsante **Ricalcola** diventa disponibile e viene visualizzato il messaggio "Richiede calcolo". Il ricalcolo viene anche richiesto se è necessario aggiungere o eliminare un elemento di costo budget.

**Esempio** 

L'organizzazione sta valutando due opzioni per ridurre il costo di una posizione da contabile. Un'opzione consiste nella conclusione della posizione durante l'anno. L'altra opzione è di modificare la posizione a tempo a ridotto per l'intero anno. Brad ha creato una posizione prevista per la posizione esistente del contabile in uno scenario di base. Copia questa posizione prevista di base nello scenario A, fissa la data di pensionamento al 31 maggio e ricalcola. Brad quindi copia la posizione prevista di base nello scenario B, modifica il valore FTE su **0,50** e ricalcola. Brad ora ha tre versioni, ciascuna delle quali ha totali di costo allineati rispetto alle relative opzioni.

#### <a name="assigning-a-compensation-group"></a>Assegnazione di un gruppo di retribuzione

Quando è necessario assegnare un gruppo di retribuzione a una posizione prevista, gli elementi di costo budget predefiniti del budget del gruppo di retribuzione vengono aggiunti. Se gli elementi di costo budget sono già assegnati alla posizione prevista, tali elementi di costo rimangono. Se un gruppo di retribuzione è già stato assegnato e viene modificato, gli elementi di costo budget esistenti vengono rimossi e sostituiti dall'insieme del gruppo di retribuzione. 

Quando si seleziona un livello retributivo e un passaggio, un elemento di costo budget di reddito (secondo quanto definito nel gruppo di retribuzione) viene aggiunto. L'importo annuale viene calcolato utilizzando la tariffa nel livello e il passaggio selezionati e le ore annuali al gruppo di retribuzione (o, per una retribuzione in base annuale, se una fattura nel livello e il passaggio). Anche in questo caso, l'importo viene moltiplicato per l'intervallo di date della riga dell'elemento di costo e il valore FTE della posizione prevista.

#### <a name="generating-increases"></a>Generazione di incrementi

I redditi annuali (uno per anno di calendario) possono essere creati automaticamente per le posizioni previste con un gruppo di retribuzione basata su passaggio assegnato. Fare clic su **Genera incrementi** per aggiungere un elemento di costo budget dei redditi al passaggio massimo successivo. La data di inizio del nuovo elemento di costo budget di reddito è la data pianificata di incremento indicata nella posizione prevista. Questa data viene impostata dal gruppo di retribuzione in uno dei due modi seguenti. Se la programmazione dell'incremento del gruppo di retribuzione è impostata come **Data comune**, la data di incremento viene specificata nel gruppo di retribuzione. Se la programmazione di incremento è impostata sul campo **Data di ricorrenza annuale** viene utilizzata la data di ricorrenza annuale della posizione prevista e il ciclo di budget fornisce l'anno. Se sono presenti più anni di calendario in un ciclo di budget, vengono aggiunti più incrementi. 

La data di fine dell'elemento di costo corrente del budget viene aggiornata con il giorno prima della data di incremento. Il processo di ricalcolo viene utilizzato automaticamente quando vengono generati gli incrementi. Di conseguenza, non è necessario ricalcolare manualmente. 

Se si fa clic su **Genera incrementi** una seconda volta, il processo viene eseguito ancora ma non aggiunge più record. Viene creato solo un incremento per anno di calendario.

#### <a name="changes-from-other-pages"></a>Modifiche tramite altre pagine

Gli aggiornamenti alle posizioni previste possono essere provenienti da altre aree, ad esempio da un elemento di costo budget o da pagine di configurazione del gruppo di retribuzione. È inoltre possibile modificare le posizioni previste utilizzando il processo di aggiornamento in massa. 

Sono disponibili due opzioni nella pagina di configurazione **Elemento costo budget**: **Aggiungi a posizioni** e **Aggiorna posizioni**. L'opzione **Aggiungi a posizioni** aggiunge l'elemento costo budget alle posizioni previste selezionate. Se l'elemento è già assegnato a una posizione prevista, la posizione prevista viene ignorata. L'opzione **Aggiorna posizioni** applica i valori correnti (conto principale, percentuali, importo annuale e così via) alle posizioni previste selezionate. 

Ogni processo ha una pagina analoga in cui è possibile selezionare le posizioni previste. La pagina **Aggiungi a posizioni** visualizza tutte le posizioni previste disponibili per la selezione, mentre la pagina **Aggiorna posizioni** visualizza solo le posizioni previste che hanno già l'elemento costo budget assegnato. Di conseguenza, la pagina **Aggiorna posizioni** offre un modo per individuare a quali posizioni di previsione è già stato associato l'elemento costo. È possibile spostare le posizioni di previsioni da una griglia superiore a una inferiore per includerle nell'aggiornamento. 

Si noti che la funzione **Modifica date** nella scheda **Calcolo costi** modifica immediatamente le date di inizio e di fine dell'elemento costo budget nelle posizioni previste. Non sono disponibili opzioni di selezione. 

Nella pagina **Gruppo di retribuzione** la funzione **Aggiorna tariffe posizione** applica le tariffe della tabella di tariffe corrente di retribuzione alle posizioni previste assegnate al gruppo. Le tariffe vengono aggiornate e righe aggiuntive dell'elemento costo vengono aggiunte per ogni nuova riga della tabella di tariffa (in base alle date). Tuttavia, gli elementi costo budget e le date di incremento non vengono aggiornati. È possibile selezionare quale processo di pianificazione del budget e scenario del piano di budget aggiornare. Di conseguenza, è possibile aggiornare uno scenario ma lasciare gli altri scenari invariati per il confronto. 

Selezionando le posizioni previste e facendo clic su **Aggiornamento in massa**, è possibile aggiungere o modificare più posizione previste contemporaneamente. Sono disponibili molte opzioni. Un'opzione della tabella **Dimensioni finanziarie** è leggermente diversa dalle altre ed è correlata agli elementi costo budget. È possibile aggiungere elementi costo budget impostando l'opzione **Valori predefiniti del budget** su **Sì**. Se nessun elemento costo budget è selezionato, ma **Impostazioni predefinite budget** è impostato su **Sì**, tutti gli elementi di costo assegnati vengono rimossi. 

Il processo di ricalcolo viene automaticamente utilizzato in qualsiasi posizione prevista che modificata.

## <a name="bringing-forecast-positions-into-budget-plans"></a>Inserimento di posizioni previste nei piani di budget

[![graphic6](./media/graphic6-1024x327.png)](./media/graphic6.png)

Lo scopo della creazione e della modifica delle posizioni di previsione consiste nell'aggiungerle ai piani di budget, in modo che i piani di budget includano importi budget più accurati. Sono disponibili due metodi per l'aggiunta di posizioni previste al piano di budget. È possibile utilizzare un processo di creazione o un processo di selezione nel piano di budget.

### <a name="generating-a-budget-plan-from-forecast-positions"></a>Generazione di un piano di budget da posizioni previste

La funzione **Genera righe del piano di budget da posizioni previste** consente di creare o aggiornare piani di budget in modo che contengano importi del budget e conteggi FTE delle posizioni previste. Gli importi di budget della posizione prevista diventano gli importi riga del piano di budget e verranno aggregati in base ai valori di dimensione finanziaria e alla data di validità. Il processo di generazione assegna la posizione prevista di origine alla riga del piano di budget. Per visualizzare la posizione è possibile aggiungere la posizione prevista come una riga nel layout del piano di budget oppure utilizzare la richiesta **Righe del piano di budget**. Per ignorare questa assegnazione, impostare l'opzione **Includi posizione nella riga del piano di budget** su **No**. 

È possibile selezionare uno scenario del piano di budget FTE per includere il numero di equivalenti a tempo pieno (FTE) nel piano di budget. È possibile selezionare solo scenari di tipo quantità inclusi nel layout del piano di budget di destinazione. Se si seleziona uno scenario FTE, è necessario specificare anche un conto principale FTE. Questo conto viene utilizzato per creare le righe di piano di budget di quantità. 

Il processo di pianificazione del budget e lo scenario del piano di budget selezionati nell'origine determinano il processo di pianificazione del budget e lo scenario dello scenario di destinazione. Poiché questi attributi vengono assegnati alle posizioni previste, devono essere sincronizzati con il piano di budget. Di conseguenza, gli attributi non possono essere modificati nella destinazione. 

Per altri processi di generazione, sono disponibili tre opzioni:

-   **Crea un nuovo piano di budget**: consente di creare un nuovo piano con gli attributi selezionati nella sezione **Destinazione**.
-   **Sostituisci lo scenario del piano di budget esistente**: consente di eliminare tutti i dati del piano di budget di destinazione nello scenario del piano di budget selezionato e creare nuove righe che utilizzano i dati della posizione prevista selezionata.
-   **Aggiornare lo scenario del piano di budget esistente e aggiungere nuovi dati**: consente di aggiornare le righe esistenti del piano di destinazione che corrispondono alle righe di origine e anche di aggiungere nuove righe per i nuovi dati. La corrispondenza si basa su conto CoGe, data, classe del budget e altri valori, ad esempio la posizione prevista. Tutte le righe con un numero di posizione che corrisponde al numero di posizione di origine vengono sostituite dalle nuove righe dall'origine.

### <a name="selecting-forecast-positions"></a>Selezione di posizioni previste

È anche possibile aggiungere importi del budget di posizione prevista direttamente nel piano di budget. Utilizzare la funzione **Aggiungi posizioni** sopra le righe di piano di budget per selezionare le posizioni previste da importare. 

Gli scenari del piano di budget che è possibile selezionare come origine sono limitati agli scenari inclusi nel layout del piano. L'opzione nella scheda **Destinazione** consente di specificare che il conto principale e lo scenario FTE disponibili per includere i conteggi di FTE, ma non sono obbligatori. 

La procedura di selezione si comporta analogamente all'opzione **Aggiornare lo scenario del piano di budget esistente e aggiungere nuovi dati** per un processo di generazione. Tutte le righe del piano di budget esistenti in cui viene aggiunta la posizione prevista vengono rimosse e sostituite dalle nuove righe basate sullo stato corrente della posizione prevista.

#### <a name="date-options"></a>Opzioni data

Per il processo di generazione e della procedura di selezione, la data di inizio della riga dell'elemento costo budget determina la data di validità della riga corrispondente di piano di budget. Il campo **Metodo di allocazione** nella pagina di configurazione elemento costo budget specifica il metodo di allocazione:

-   **Data di inizio**: la data di inizio dell'elemento costo budget viene utilizzata come data di validità della riga del piano di budget.
-   **Mensile**: l'importo budget è suddiviso uniformemente per il numero di mesi nell'intervallo di date per produrre un importo mensile tipico assegnato al primo giorno di ogni mese. Se il primo periodo è un mese parziale, l'importo per tale mese viene moltiplicato per il numero di giorni che il costo attivo del mese e il risultato viene assegnato alla data di inizio. L'importo per l'ultimo mese corrisponde alla differenza tra l'importo del budget totale e la somma di tutti gli altri mesi. Di conseguenza, l'arrotondamento può influire sull'importo per l'ultimo mese.
-   **Trimestrale**: questo metodo è analogo al metodo **Mensile**, ma i calcoli vengono effettuati per i periodi di tre mesi.
-   **Settimanale**: la logica è simile alla logica dei metodi **Mensile** e **Trimestrale**. L'importo budget è suddiviso uniformemente per il numero di settimane nell'intervallo di date per produrre un importo settimanale tipico assegnato al primo giorno di ogni settimana. Se il primo periodo è una settimana parziale, l'importo per tale settimana viene moltiplicato per il numero di giorni che il costo attivo della settimana e il risultato viene assegnato alla data di inizio. L'importo per l'ultima settimana corrisponde alla differenza tra l'importo del budget totale e la somma di tutte le altre settimane. Di conseguenza, l'arrotondamento può influire sull'importo per l'ultima settimana.
-   **Bisettimanale**: questo metodo è analogo al metodo **Settimanale**, ma i calcoli vengono effettuati per i periodi di due settimane.

#### <a name="changing-budget-plan-lines-that-have-forecast-positions"></a>Modifica di righe di piano di budget con posizioni previste

Le righe di piano di budget mostrano l'origine degli importi di budget (numero posizione prevista), ma non sono collegate. Di conseguenza, le modifiche alla posizione prevista non vengono visualizzate nella riga del piano di budget e le modifiche alla riga del piano di budget vengono visualizzate nella posizione prevista. Se si modifica una posizione prevista e si desidera che gli aggiornamenti vengano inclusi in un piano del budget, è necessario riportare la posizione prevista nel piano. Tuttavia, si ricordi che il processo rimuove tutte le righe a cui la posizione di previsione è assegnata. Di conseguenza, tutte le modifiche apportate alle righe verranno rimosse. 

Per visualizzare in quali piani di budget una posizione prevista è stata inclusa, è possibile generare il report **Posizioni previste per piano di budget**. In alternativa, nella posizione prevista è possibile aprire il riquadro Dettaglio informazioni **Piani di budget associati** per visualizzare i piani.




