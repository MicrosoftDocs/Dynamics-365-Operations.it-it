---
title: Aggiornamento della pianificazione del budget
description: Tra Microsoft Dynamics AX 2012 e Dynamics 365 Finance sono presenti differenze significative nella pianificazione del budget. Alcune funzionalità non sono state aggiornate e richiedono quindi la riconfigurazione. In questo argomento viene descritto quali elementi è necessario riconfigurare e vengono descritte le nuove funzionalità che devono essere considerate dopo il completamento dell'aggiornamento.
author: ryansandness
manager: AnnBe
ms.date: 04/10/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.custom: 272923
ms.assetid: 17cdfe74-bdfd-466a-9bdd-c12583f250c7
ms.search.region: Global
ms.author: ryansand
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: 1c62771170212039112c777e55d45a0d88d2f49d
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/05/2020
ms.locfileid: "4681000"
---
# <a name="upgrade-budget-planning"></a>Aggiornamento della pianificazione del budget

[!include [banner](../includes/banner.md)]

Tra Microsoft Dynamics AX 2012 e Dynamics 365 Finance sono presenti differenze significative nella pianificazione del budget. Alcune funzionalità non sono state aggiornate e richiedono quindi la riconfigurazione. In questo argomento viene descritto quali elementi è necessario riconfigurare e vengono descritte le nuove funzionalità che devono essere considerate dopo il completamento dell'aggiornamento.  

La pianificazione del budget in Finance include molti miglioramenti che non erano disponibili in Dynamics AX 2012. In questo argomento vengono illustrate le modifiche che devono eseguire i clienti che effettuano l'aggiornamento. Vengono inoltre illustrate le nuove funzionalità che devono essere considerate nel processo di aggiornamento. A causa delle dimensioni delle modifiche, tutti i piani di budget esistenti non potranno essere aperti fino a che non sono state apportate le modifiche descritte in questo argomento. Tuttavia, i report dovrebbero continuare a funzionare e non richiedono modifiche aggiuntive.

## <a name="overview-of-changes"></a>Panoramica delle modifiche
Nell'Impostazione budget di Finance and Operations sono state apportate molte modifiche significative. Le modifiche hanno lo scopo di rendere la struttura del budget più semplice da configurare e più riutilizzabile, per ridurre le operazioni di manutenzione annuali e le impostazioni. Le seguenti aree di AX 2012 non esistono più in Finance:

-   Modelli del piano di budget (configurazione di pianificazione del budget)
-   Cartelle del piano di budget (configurazione di pianificazione del budget)
-   Vincoli dello scenario (configurazione di pianificazione del budget)
-   Modelli per le regole e i modelli da utilizzare per le fasi di pianificazione del budget (processo di pianificazione del budget)
-   Campi di matrice per i modelli del foglio di lavoro
-   Procedura guidata modello di Microsoft Excel per la pianificazione del budget

Alcuni nuovi concetti non possono essere direttamente aggiornati dalla funzionalità precedente. Di conseguenza, è necessario completare alcune operazioni di riconfigurazione per includere i nuovi concetti. Nelle seguenti sezioni vengono descritti i concetti che hanno sostituito gli elementi nell'elenco precedente.

### <a name="columns"></a>Colonne

Le colonne costituiscono un nuovo concetto che sostituisce parti del modello di Excel e i campi della matrice. Le colonne possono rappresentare un periodo, mese, trimestre, anno o tutti gli intervalli di tempo. Il riferimento temporale è dinamico. Indica un periodo o un anno correlato in riferimento al processo di budget. Ad esempio, una colonna **Gennaio anno precedente** fa riferimento al periodo fiscale 1 per l'anno -1. Una colonna è specifica di uno scenario del piano di budget, ad esempio valori effettivi o la richiesta budget.

### <a name="layouts"></a>Layout

I layout sono un nuovo concetto che sostituisce il modello Excel. I layout contengono le colonne che definiscono quali dati del budget o effettivi devono essere mostrati. I layout vengono condivisi tra il client e il componente aggiuntivo di Excel. Di conseguenza, l'esperienza utente quando si immettono o si visualizzano i dati nel client di Finance and Operations è migliore rispetto all'esperienza utente di AX 2012. Nell'immettere i dati nel client di Finance non si è più limitati alla visualizzazione e all'immissione di un unico scenario in una visualizzazione transazione. Una visualizzazione di confronto consente invece di visualizzare e immettere facilmente gli importi per più periodi e conti contemporaneamente. I layout possono inoltre venire definiti in modo che sia possibile immettere e visualizzare la valuta, i commenti e altri dati facoltativi. I layout consentono anche di definire le dimensioni di contabilità generale e le descrizioni delle dimensioni da visualizzare. I layout includono inoltre vincoli di scenario per definire quali colonne di un modello possono essere modificate e quali colonne devono essere disponibili in Excel. Dopo aver definito un layout, un modello viene generato. Questo modello, a sua volta, crea il modello corrispondente di Excel. È quindi possibile modificare il modello Excel per includere più formule e formattazione e quindi caricarlo di nuovo. I layout vengono assegnati a ciascuna regola fase nella pagina **Processo di pianificazione del budget**. Di conseguenza, i layout sostituiscono i modelli, che sono stati assegnati e utilizzati in modo simile.

### <a name="budget-planning-processes"></a>Processi di pianificazione del budget

I processi di pianificazione del budget sono fondamentalmente gli stessi di AX 2012. La modifica più significativa è la sostituzione dei modelli con i layout. Se alcuni processi sono stati precedentemente completati in AX 2012, i processi vengono aggiornati con stato dello stato "Processo in corso" in modo da poter apportare modifiche. È necessario assegnare i layout necessari per ogni regola fase per determinare quali scenari e periodi di tempo vengono visualizzati quando il piano viene aperto nel client. I layout determinano anche quale modello di Excel viene aperto al di fuori di Dynamic 365 Finance in modo che sia possibile visualizzare il budget. **Struttura dei conti predefinita** è un nuovo campo obbligatorio per il processo di pianificazione del budget. Per ciascun processo di pianificazione del budget, assegnare la struttura dei conti principale che deve essere utilizzata per l'impostazione del budget.

### <a name="attachments"></a>Allegati

In AX 2012, i documenti di motivazione venivano salvati in una cartella dell'allegato. Nessun documento di motivazione precedente viene aggiornato. I documenti di questo tipo vengono ora archiviati nel database. Se queste informazioni devono essere salvate nella versione aggiornata, è possibile caricare i documenti di motivazione definitivi per ciascun piano come allegato tramite il pulsante **Motivazione** nel riquadro azioni. In AX 2012, i fogli di lavoro di Excel per ciascun piano di budget venivano creati in base al modello. In Finance tutti i piani aprono una copia del layout. Tuttavia, nessuna modifica apportata al file di Excel viene salvata. Tutte le formule o informazioni aggiuntive utilizzate in base al singolo piano devono essere aggiunte tramite i commenti, un documento di motivazione o un altro processo aggiuntivo.

## <a name="configuring-an-upgraded-environment-from-ax-2012"></a>Configurazione di un ambiente aggiornato da AX 2012
Per consentire di determinare la modalità di configurazione del sistema aggiornato, nel seguente esempio viene utilizzato un processo di budget aggiornato dei dati dimostrativi di AX 2012. I dati di configurazione predefiniti per le colonne sono stati creati per agevolare l'esecuzione del processo di aggiornamento. È possibile aggiornare o eliminare questi dati predefiniti se non soddisfano i propri requisiti di configurazione. **Nota:** sono presenti nuovi campi obbligatori che non verranno impostati nel sistema. Se si rimane bloccati in una pagina, ad esempio nella pagina **Configurazione di pianificazione del budget** e non è possibile uscire da questa pagina, si può chiudere il browser e quindi riaprirlo in una pagina distinta per immettere i dettagli secondo l'ordine corretto. Alcuni campi obbligatori non sono ancora stati impostati. Di conseguenza, possono verificarsi dei problemi fino a che tutti gli elementi sono stati configurati e tutti i campi obbligatori sono stati impostati. In questo argomento viene descritto come impostare questi campi, secondo le esigenze. Di seguito sono riportati alcuni campi obbligatori:

-   Pagina **Processo di pianificazione del budget**: campo **Struttura dei conti predefinita**
-   Pagina **Processo di pianificazione del budget**: campo **Layout** della scheda dettaglio **Regole e layout fase di pianificazione del budget**

### <a name="define-columns-and-layouts"></a>Definire le colonne e i layout

1. Nella pagina **Configurazione di pianificazione del budget**, fare clic sulla scheda **Colonne**. Come parte del processo di aggiornamento, nuove colonne vengono create automaticamente in base alle righe del piano di budget. Nelle colonne ora vengono utilizzate date dinamiche, in cui il tempo e l'anno sono compensati dall'anno fiscale definito nel processo di pianificazione del budget. **Nota:** per motivi di prestazioni durante l'aggiornamento, si presuppone che tutti i cicli di budget rappresentino gli anni di calendario, non gli anni fiscali. Se si utilizzano gli anni fiscali, è necessario apportare modifiche per mappare correttamente le colonne all'anno fiscale. Ad esempio, i seguenti elementi erano disponibili in AX 2012:
   -   Scenari del piano di budget: Effettivi, Base, Richiesta budget, Budget approvato
   -   Righe del piano di budget per tutti gli scenari nel 2017 ed effettivi per entrambi 2017 e 2016

   Verranno create le colonne che seguono in Finance and Operations:

   | Nome colonna    | Scenario del piano di budget | Periodo di tempo colonna | Offset anno |
   |----------------|----------------------|--------------------|-------------|
   | Gennaio - Scenario 1 | Effettivi              | 1                  | 0           |
   | Gennaio - Scenario 2 | Base             | 1                  | 0           |
   | Gennaio - Scenario 3 | Richiesta budget       | 1                  | 0           |
   | Gennaio - Scenario 4 | Budget approvato      | 1                  | 0           |
   | Gennaio - Scenario 5 | Effettivi              | 1                  | -1          |
   | Febbraio - Scenario 1 | Effettivi              | 1                  | 0           |
   | ...            | ...                  | ...                | ...         |

   In questo esempio, una colonna **Gennaio - Scenario 1** viene creata per i dati transazione del piano di budget più recenti trovati dove sono presenti transazioni per gennaio. Una colonna simile viene creata per ogni scenario con dati. Quando sono presenti colonne per tutti i periodi dell'anno, le colonne vengono create per gli anni precedenti.
2. Modificare i nomi e le descrizioni di colonna e gli altri dettagli, manualmente nel client o tramite aggiornamenti in blocco mediante il componente aggiuntivo di Excel che punta all'entità dati delle colonne del piano di budget. Tutti i filtri che sono stati precedentemente configurati per i campi della matrice sono ora impostati nelle colonne.
3. Creare un nuovo layout di budget. Un layout punta a più colonne per definire la visualizzazione mostrata in Excel e nel client. Il layout innanzitutto richiede che venga specificato un set di dimensioni di contabilità generale per determinare quali dimensioni finanziarie possono essere immesse. Dopo avere specificato il set di dimensioni, fare clic su **Descrizioni** per selezionare le descrizioni delle dimensioni da includere nel layout.
4. Nella scheda dettaglio **Elementi layout**, fare clic su **Aggiungi** per aggiungere i metadati per ogni riga, ad esempio una valuta, un commento o una classe di budget che determina i ricavi rispetto alle righe di spesa. A questo punto, aggiungere le colonne per il periodo e gli scenari applicabili a questo ciclo e fase di budget. È possibile apportare manualmente tali modifiche nel client o tramite il componente aggiuntivo di Excel che punta all'entità di dati di elementi del layout del piano di budget.
5. Per ciascun elemento del layout, selezionare se la colonna deve essere modificabile e se la colonna deve essere mostrata anche nella cartella di lavoro di Excel per il layout. **Nota:** per i piani storici, può essere opportuno considerare un layout contenente 12 colonne mensili per tutti gli scenari del piano di budget per tale processo.

### <a name="update-budget-planning-processes-to-use-the-appropriate-layout-for-each-budget-stage"></a>Aggiornare i processi di pianificazione del budget per l'utilizzo del layout appropriato per ogni fase del budget

1.  Nella pagina **Processo di pianificazione del budget**, selezionare il processo da configurare.
2.  Nel riquadro azioni fare clic su **Modifica**.
3.  Specificare la Struttura dei conti predefinita per il processo di budget. **Struttura dei conti predefinita** è un nuovo campo obbligatorio che deve essere impostato.
4.  Nella scheda dettaglio **Regole e layout fase di pianificazione del budget**, nel campo **Layout**, selezionare un layout in precedenza configurato e appropriato per questa fase.
5.  Continuare a selezionare lo stesso layout o diversi layout per le varie fasi di pianificazione del budget e quindi salvare le modifiche.

## <a name="additional-features-to-consider-in-your-budgeting-process"></a>Funzionalità aggiuntive da considerare nel processo di impostazione del budget
### <a name="budget-planning-workspace"></a>Area di lavoro di pianificazione del budget

Questa area di lavoro è stata progettata per il proprietario del budget e per i singoli contributori del budget. Include collegamenti a tutti i documenti di budget che richiedono attenzione. Include anche report e indicatori di prestazioni chiave (KPI) per il processo di budget. L'amministratore del budget può definire il processo di pianificazione del budget corrente per tutti gli utenti nella pagina **Parametri impostazione budget**. Nella scheda **Impostazioni area di lavoro**, la scheda dettaglio **Pianificazione del budget** include un campo in cui è possibile selezionare il processo di pianificazione del budget.

### <a name="alternate-layouts"></a>Layout alternativi

I layout alternativi sono una nuova funzionalità che consente di visualizzare i piani nei diversi layout. Uno o più layout possono essere forniti come opzioni. Sarà quindi possibile visualizzare un piano di un layout mensile o in un layout trimestrale. È possibile definire layout alternativi nella scheda dettaglio **Regole e layout fase di pianificazione del budget** della pagina **Processo di pianificazione del budget**.

### <a name="budget-milestones"></a>Punti cardine del budget

Come parte del processo di budget, è fondamentale comprendere le date e le scadenze chiave. È ora possibile configurare le date in modo che contengano descrizioni. Gli utenti del budget potranno visualizzare queste descrizioni all'apertura dei budget per la modifica o la visualizzazione di qualsiasi elemento a loro assegnato.

### <a name="copy-from-budget-plan-allocation"></a>Copia dall'allocazione del piano di budget

Un nuovo metodo di allocazione consente di effettuare una distribuzione da un piano padre a un piano figlio senza dover passare da un livello intermedio della gerarchia. Questo metodo è particolarmente utile per i clienti che in precedenza hanno creato la dimensione finanziaria solo per la distribuzione e le approvazioni del budget.

### <a name="generating-budget-plans-from-new-budget-sources"></a>Creazione di piani di budget da nuove origini del budget

Le opzioni seguenti sono state aggiunte come processi periodici. Queste opzioni consentono di generare un piano di budget con i dati esistenti da un altro modulo come punto di partenza:

-   Genera piano di budget da previsioni della domanda
-   Genera piano di budget da previsione dell'offerta
-   Genera piano di budget da progetto
-   Genera piano di budget da registro di budget

### <a name="more-complete-tracking-of-amounts"></a>Tracciabilità più completa degli importi

In AX 2012, la pianificazione del budget aveva un singolo importo di piano memorizzato per ogni valore. In Finance il modello dati è stato espanso. Sono ora disponibili importi di valuta di contabilizzazione, valuta di transazione e di valuta di dichiarazione per ogni valore. Durante l'aggiornamento, queste nuove colonne vengono completate automaticamente per i dati esistenti.

### <a name="do-not-convert-currency-in-aggregation"></a>Non convertire la valuta in aggregazione

In genere, quando un piano figlio viene aggregato a un livello padre, gli importi vengono convertiti automaticamente dalla valuta di transazione alla valuta di contabilizzazione per l'organizzazione. Quando si imposta l'opzione **Non convertire la valuta in aggregazione** su **No** gli importi aggregati rimangono nella valuta originale. Di conseguenza, questa opzione consente correzioni più precise che interessano le fluttuazioni del tasso di cambio.

### <a name="looking-back-from-a-budget-plan-to-other-modules-that-contributed-to-the-budget"></a>Effettuare ricerche dal piano di budget ad altri moduli che contribuiscono al budget

I piani di budget possono essere generati da domanda o previsione dell'offerta, progetto e da altre aree. La Richiesta di informazioni Piani di budget per set di dimensioni include diverse opzioni che consentono di eseguire query per identificare i dati all'origine del piano di budget.

### <a name="overwrite-or-append-to-plan-for-allocation-schedules"></a>Sovrascrivere o aggiungere a un piano per le programmazioni di allocazione

Se sono presenti più origini per gli importi che devono essere distribuiti, è possibile specificare che gli importi devono essere di tipo aggiuntivo. In questo caso, gli importi non sovrascriveranno gli importi correnti. Verranno invece aggiunti agli importi esistenti.

### <a name="default-financial-dimension-set-for-budget-planning-configuration"></a>Set di dimensioni finanziarie predefinite per la configurazione di pianificazione del budget

La pagina **Configurazione di pianificazione del budget** include ora un campo in cui è possibile specificare il set di dimensioni finanziarie predefinite. Sebbene questo campo sia facoltativo, potrebbe essere necessario per alcune richieste di informazioni. Potrebbe essere necessario per raggruppare o filtrare il raggruppamento di report per set di dimensioni.

### <a name="data-entities"></a>Entità di dati

Sono state aggiunte diverse entità di dati per consentire l'implementazione rapida della pianificazione del budget. Le entità anche consentono anche di effettuare le modifiche tramite Excel. Pertanto, non è necessario creare gli articoli uno alla volta nel client. Di seguito è riportato un elenco di nuove entità di dati:

-   Nome entità
-   Parametri budget
-   Parametro piano di budget
-   Scenari del piano di budget
-   Fasi piano di budget
-   Fase flusso di lavoro del piano di budget
-   Programmazioni allocazione del piano di budget
-   Allocazioni fasi del piano di budget
-   Priorità piano di budget
-   Colonne piano di budget
-   Elementi di layout del piano di budget






[!INCLUDE[footer-include](../../../includes/footer-banner.md)]