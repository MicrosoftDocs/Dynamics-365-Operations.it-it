---
title: Panoramica della pianificazione del budget
description: Questo argomento descrive la pianificazione del budget. Sono contenute informazioni che possono semplificare la configurazione della pianificazione del budget e l'impostazione dei processi di pianificazione del budget.
author: panolte
ms.date: 01/11/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BudgetPlanningConfiguration
audience: Application User
ms.reviewer: roschlom
ms.custom: 17251
ms.assetid: a2e06633-a800-4840-a962-88fed8462104
ms.search.region: Global
ms.author: sigitac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 14a5e1cea5a249b6087ef87560dd06bc026dd129
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5822133"
---
# <a name="budget-planning-overview"></a>Panoramica della pianificazione del budget

[!include [banner](../includes/banner.md)]

Questo argomento descrive la pianificazione del budget. Sono contenute informazioni che possono semplificare la configurazione della pianificazione del budget e l'impostazione dei processi di pianificazione del budget.

## <a name="overview-of-budget-planning"></a>Panoramica della pianificazione del budget

Un'organizzazione può configurare la pianificazione del budget e quindi impostare i processi di pianificazione del budget per soddisfare i criteri, le procedure e i requisiti della preparazione del budget. Quando si capiscono i concetti e la terminologia utilizzati in Microsoft Dynamics 365 Finance, è più facile ed efficace implementare la pianificazione del budget nell'organizzazione.

### <a name="key-terms"></a>Termini importanti

- **Processi di pianificazione del budget** I processi di pianificazione del budget determinano come possono essere aggiornati, indirizzati, rivisti e approvati i piani di budget nella gerarchia dell'organizzazione per la definizione del budget. Un processo di pianificazione del budget è legato a un ciclo del budget e a una organizzazione tramite una persona giuridica.
- **Piani di budget** I piani di budget contengono i dati per un ciclo del budget. È possibile avere più piani di budget che vengono utilizzati per vari scopi. Ad esempio, è possibile utilizzare i piani di budget per creare importi di budget per diverse unità organizzative. Inoltre, è possibile usarli per fare confronti e prendere decisioni informate.
- **Scenari di piani di budget** Gli scenari di piani di budget definiscono le categorie di dati per i piani di budget. Definire gli scenari del piano di budget per supportare le classi monetarie e altre classi di unità di misura, ad esempio le quantità. Esempi di scenari monetari di piano di budget includono le richieste "Richieste reparto" e "Anno precedente reparto". Esempi di scenari di piano di budget che usano quantità includono le "chiamate all'assistenza per l'anno precedente" e il "conteggio FTE (Full Time Equivalent)".
- **Fasi di pianificazione del budget** Le fasi di pianificazione del budget definiscono i passaggi che un piano di budget deve seguire dall'approvazione iniziale a quella finale. Le fasi di pianificazione del budget sono disposte in flussi di lavoro di pianificazione del budget.
- **Flussi di lavoro di pianificazione del budget** I flussi di lavoro di pianificazione del budget sono costituiti e definiscono le fasi della pianificazione del budget. I flussi di lavoro di pianificazione del budget sono associati ai flussi di lavoro impostazione budget. I flussi di lavoro impostazione budget sono i processi automatizzati e manuali che spostano i piani di budget tra le fasi di pianificazione del budget.

[![Terminologia relativa alla pianificazione del budget](./media/budgetplanning-terms-1024x504.png)](./media/budgetplanning-terms.png)

### <a name="typical-tasks"></a>Attività tipiche

È possibile utilizzare la pianificazione del budget per effettuare le attività indicate di seguito.

- Creare piani di budget per definire i ricavi e le spese previste per un ciclo del budget.
- Analizzare e aggiornare i piani di budget per più scenari.
- Instradare automaticamente i piani di budget, insieme a fogli di lavoro, documenti di motivazione e altri allegati, per la revisione e l'approvazione.
- Consolidare più piani di budget da un livello più basso dell'organizzazione in un unico piano di budget padre a un livello superiore. È inoltre possibile elaborare un piano di budget singolo a un livello superiore dell'organizzazione e allocare il budget ai livelli minimi.

La pianificazione del budget è integrata nei moduli. Pertanto, si possono includere le informazioni provenienti da budget precedenti, cespiti e risorse umane. Poiché la pianificazione del budget è integrato anche in Microsoft Excel e Microsoft Word, è possibile utilizzare questi programmi per lavorare con i dati di pianificazione del budget. Ad esempio, un responsabile budget può esportare la richiesta del budget di un reparto in uno scenario di piani di budget in un foglio di lavoro Excel. I dati possono quindi essere analizzati, aggiornati e essere tracciati nel foglio di lavoro e quindi essere pubblicati alle righe di piano di budget.

## <a name="configuring-budget-planning"></a>Configurazione della pianificazione del budget

La funzionalità introdotta in Dynamics 365 Finance versione 10.0.9 (aprile 2020) include una funzione che aiuta a migliorare le prestazioni quando si utilizza il pulsante **Pubblica** per aggiornare i record esistenti in Excel e quindi pubblicarli di nuovo sul client. Questa funzione accelera il processo di aggiornamento e aiuta anche a ridurre la probabilità che un aggiornamento venga bloccato quando si aggiornano più record contemporaneamente. Per rendere disponibile questa funzionalità, andare nell'area di lavoro **Gestione funzionalità** e attivare la funzionalità **Ottimizzazione delle query di pianificazione del budget per le prestazioni** sotto **Impostazione budget**. Consigliamo di attivare questa funzione.

La pagina **Configurazione pianificazione del budget** contiene la maggior parte delle impostazioni necessarie per impostare la pianificazione del budget. Nelle sezioni seguenti vengono descritti alcuni fattori da considerare per configurare la pianificazione del budget. Dopo aver completato la configurazione, si impostano i processi di pianificazione del budget.

### <a name="budget-planning-schema-optional"></a>Schema di pianificazione del budget (facoltativo)

Il primo passo facoltativo sebbene consigliato consiste nel creare uno schema contenente la procedura dell'organizzazione per la formulazione del budget. È possibile utilizzare un metodo qualsiasi per creare questo schema.

La figura seguente illustra un esempio generico, in cui flussi di lavoro separati di pianificazione del budget vengono creati per diversi livelli dell'organizzazione. Le fasi sono definite in ciascun flusso di lavoro e vengono assegnati scenari specifici a ciascuna fase per utilizzare i dati di budget. Le attività vengono completate per spostare i dati da una fase alla successiva. Ad esempio, gli importi possono essere aggregati o allocati a diversi conti, approvazioni o altra revisione. In questa illustrazione, il testo corsivo indica uno scenario che non può essere modificato durante la fase oppure i dati dello storico o che sono stati approvati in una fase precedente e pertanto non devono essere modificati.

[![Schema generico di pianificazione del budget](./media/budgetplanninggenericschema-300x145.png)](./media/budgetplanninggenericschema.png) 

La seguente illustrazione mostra un esempio in cui la sede centrale aziendale stima gli importi di base del budget iniziale e li distribuisce ai reparti vendite. I reparti vendite quindi stimano e inviano la previsione di nuovo alla sede centrale, dove il responsabile budget aggrega e modifica la previsione. Infine, il responsabile budget invia gli importi del budget rettificati al responsabile finanziario per la revisione, le rettifiche finali e l'approvazione.

[![Esempio di schema di pianificazione del budget](./media/budgetplanningexampleschema-300x145.png)](./media/budgetplanningexampleschema.png)

### <a name="organization-hierarchy-for-budget-planning"></a>Gerarchia organizzativa per la pianificazione del budget

Nella pagina **Gerarchia organizzativa**, è possibile specificare una gerarchia organizzativa come gerarchia di pianificazione del budget per ciascun processo di pianificazione del budget. La gerarchia di pianificazione del budget non deve corrispondere alla gerarchia di organizzazione normale utilizzata per altri scopi. Poiché la gerarchia viene utilizzata per aggregare e distribuire i dati, è possibile desiderare che abbia una struttura diversa. Nello schema di esempio, i reparti vendite sono sotto un livello della sede centrale che include i reparti di amministrazione e budget. Questa struttura probabilmente è diversa dalla struttura utilizzata per gestire le operazioni per i reparti vendite. Una sola gerarchia organizzativa può essere assegnata a ogni processo di pianificazione del budget.

Per ulteriori informazioni sulle gerarchie organizzative, vedere [Organizzazioni e gerarchie organizzative](../../fin-and-ops/organization-administration/organizations-organizational-hierarchies.md).

### <a name="user-security"></a>Sicurezza utente

La pianificazione del budget può seguire uno dei due modelli di sicurezza per definire le autorizzazioni utente. Per specificare il modello di sicurezza, impostare un parametro di pianificazione del budget nella pagina **Configurazione pianificazione del budget**.

### <a name="budget-planning-workflows-stages"></a>Fasi del flusso di lavoro di pianificazione del budget

I flussi di lavoro di pianificazione del budget vengono utilizzati insieme ai flussi di lavoro impostazione budget per gestire la creazione e l'evoluzione del piano di budget.

Un flusso di lavoro di pianificazione del budget è costituito da un insieme ordinato di fasi in cui si sposta il piano di budget. Ogni flusso di lavoro di pianificazione del budget è associato a un flusso di lavoro impostazione budget. I flussi di lavoro impostazione budget sono uno dei tipi di flussi di lavoro utilizzati in Dynamics 365 Finance. Il flusso indirizza i piani di budget, insieme ai fogli di lavoro, alle motivazioni e agli allegati mediante l'organizzazione per essere rivisti e approvati.

Creare un flusso di lavoro di pianificazione del budget nella sezione **Fasi del flusso di lavoro** della pagina **Configurazione pianificazione del budget**. Sarà possibile selezionare le fasi e il flusso di lavoro impostazione budget che verranno utilizzati e si potranno configurare impostazioni aggiuntive.

La procedura consigliata consiste nel creare un flusso di lavoro di pianificazione del budget per ciascun livello della gerarchia di impostazione budget. Assegnare un flusso di lavoro impostazione budget che contiene gli elementi che corrispondono alle fasi del flusso di lavoro di pianificazione del budget. Nello schema di esempio visualizzato in precedenza in questo argomento, un flusso di lavoro di pianificazione del budget viene creato per i reparti vendite e un altro viene creato per la sede centrale. Un flusso di lavoro impostazione budget sposta i piani di budget tra le fasi.

Creare il flusso di lavoro impostazione budget per la pianificazione del budget nella pagina **Flussi di lavoro impostazione budget**. Il processo è analogo a quello per creare altri flussi di lavoro. Nella figura seguente viene illustrato un esempio di un flusso di lavoro della sede centrale.

[![Flusso di lavoro impostazione budget per la pianificazione del budget](./media/budgetingworkflowforbudgetplanning-300x300.png)](./media/budgetingworkflowforbudgetplanning.png) 

Il flusso di lavoro contiene i seguenti elementi:

- Allocazione ai reparti vendite e aggregazione degli invii
- Revisione del responsabile del budget
- Approvazione del responsabile finanziario
- Transizioni di gestione temporanea tra ciascuna fase del flusso di lavoro di pianificazione del budget

Assegnare il flusso di lavoro impostazione budget a ogni flusso di lavoro di pianificazione del budget nella sezione **Fasi del flusso di lavoro** della pagina **Configurazione pianificazione del budget**.

### <a name="parameters-scenarios-and-stages"></a>Parametri, scenari e fasi

Le impostazioni iniziali nella pagina **Configurazione pianificazione del budget** consentono di creare alcuni blocchi predefiniti per i passaggi di configurazione successivi:

- **Parametri** I parametri definiscono le regole di sicurezza da applicare ai piani di budget e le dimensioni finanziarie predefinite che devono essere utilizzate quando gli utenti analizzano gli importi nello scenario di piano di budget.
- **Scenari** Gli scenari includono le categorie dei dati desiderati per il piano di budget. Definire gli scenari del piano di budget per supportare le classi monetarie e altre classi di unità di misura, ad esempio la quantità. Nel piano di budget, gli scenari rappresentano una versione dei dati di pianificazione del budget. Esempi di scenari monetari di piano del budget includono le richieste "Vendite anno precedente" e "Contratti firmati". Esempi di scenari che utilizzano quantità includono "Numero di chiamate di vendita" e "Conteggio FTE".
- **Fasi** Le fasi definiscono i passaggi seguiti dal piano di budget dall'approvazione iniziale a quella finale. Esempi di fasi di progettazione del budget includono "l'aggiornamento cumulativo della sede centrale", "la revisione dei responsabili finanziari" e "la fase finale".

### <a name="allocation-schedules"></a>Programmazioni allocazione

Nella pianificazione del budget, è possibile allocare gli importi o le quantità nelle righe del piano di budget da uno scenario a un altro scenario o persino nello stesso scenario. Ad esempio, si possono allocare importi o quantità per lo stesso scenario se si desiderano applicare le modifiche alle dimensioni finanziarie o le date degli importi in quello scenario. Un'allocazione può essere effettuata in un piano di budget o da un piano di budget a un altro.

Le programmazioni di allocazione allocano automaticamente le righe del piano di budget durante l'elaborazione del flusso di lavoro. È possibile eseguire le allocazioni utilizzando uno dei seguenti metodi dell'elenco **Metodo di allocazione**:

- **Alloca nei periodi**: utilizzare una chiave di allocazione per periodo per allocare le righe del piano di budget dallo scenario del piano di budget di origine tra i periodi dello scenario di destinazione.

    > [!NOTE]
    > Prima di allocare in più periodi, è necessario impostare le chiavi di allocazione nella pagina **Categorie di allocazione per periodo**.

- **Alloca a dimensioni**: le righe del piano di budget vengono allocate dallo scenario del piano di budget di origine tra le dimensioni finanziarie nello scenario di destinazione.

    > [!NOTE]
    > Prima di allocare le dimensioni, è necessario impostare i termini di allocazione budget nella pagina **Termini di allocazione budget**.

- **Aggrega**: le righe del piano di budget sono aggregate dallo scenario del piano di budget di origine nei piani di budget associati allo scenario di destinazione nel piano di budget padre.
- **Distribuisci**: le righe del piano di budget sono distribuite dallo scenario del piano di budget di origine nel piano di budget padre allo scenario di destinazione nei piani di budget associati.
- **Utilizza regole di allocazione contabilità generale**: le righe di piano di budget vengono distribuite dallo scenario di origine del piano di budget allo scenario di destinazione del piano del budget in base alla regola di allocazione di contabilità generale selezionata.
- **Copia da piano di budget**: consente di selezionare un piano di budget di utilizzare come origine dell'allocazione.

### <a name="stage-allocations"></a>Allocazioni di fasi

Le allocazioni di fase vengono utilizzate per allocare automaticamente le righe del piano di budget durante l'elaborazione del flusso di lavoro. Quando si utilizzano le allocazioni di fase, le righe del piano di budget nello scenario di destinazione possono essere create e modificate senza l'intervento della persona che ha preparato il piano di budget o del revisione del piano di budget.

Quando si imposta un'allocazione di fase, associare il flusso di lavoro e la fase di pianificazione del budget alla pianificazione di allocazione. Il flusso di lavoro di pianificazione del budget deve essere associato a un flusso di lavoro di impostazione del budget che utilizza l'attività del flusso di lavoro automatizzata **Allocazione di fasi di pianificazione del budget**. Quando il flusso di lavoro raggiunge la fase specificata, l'allocazione avviene automaticamente. Questa attività automatica può essere utilizzata per creare le righe del piano di budget in un nuovo scenario.

Nello schema di esempio mostrato in precedenza in questo argomento, un'allocazione viene eseguita per trasferire gli importi da un piano di budget e dagli scenari della fase "di base" della sede centrale a un altro piano di budget e agli scenari della fase "di stima" dei reparti vendite. La figura seguente mostra la sezione dello schema di esempio.

[![Allocazioni di fasi](./media/stageallocation-204x300.png)](./media/stageallocation.png) 

Inoltre, nello schema di esempio, un'aggregazione viene eseguita dai piani di budget e dagli scenari della fase "inviata" dei reparti vendite a un piano padre della fase di "aggiornamento cumulativo" delle sedi centrali. La figura seguente mostra la sezione dello schema di esempio.

[![Aggregazione](./media/aggregation-109x300.png)](./media/aggregation.png)

### <a name="priorities"></a>Priorità

Si può scegliere di utilizzare le priorità di piano di budget per definire le categorie e gli obiettivi per i piani di budget impostati. Le priorità possono essere anche utilizzate per l'organizzazione, la classificazione e la valutazione di diversi piani di budget. Ad esempio, è possibile creare una priorità di pianificazione del budget per le spese sanitarie e quindi valutare i piani di budget assegnati a tale priorità. Inoltre, è possibile assegnare un numero ai piani di budget per indicare una classificazione.

### <a name="columns-and-layouts"></a>Colonne e layout

Le cifre del budget vengono visualizzate nel piano di budget in righe e colonne. È innanzitutto necessario definire le colonne e quindi creare un layout per definirne la presentazione.

Per definire una colonna, selezionare uno scenario di piano di budget. Gli importi righe di quello scenario vengono visualizzati nel piano di budget. È possibile selezionare un periodo per filtrare l'importo ed è possibile applicare i filtri in base al conto CoGe.

Quando si definisce un layout, selezionare un set di dimensioni di contabilità generale per creare le righe di piano di budget da mostrare e selezionare le colonne come elementi del layout. È possibile creare più layout, in modo che un piano di budget indica i dati desiderati alle diverse fasi del processo di pianificazione del budget.

Oltre alle colonne per gli importi del budget, è possibile definire le colonne per i campi del progetto, del progetto proposto, del cespite e dei cespiti proposti dal piano di budget. È inoltre possibile definire una colonna per le posizioni in budget. Questa opzione è utile quando è necessario analizzare i budget del personale.

Per lo schema di esempio, è possibile voler creare colonne per gli scenari "Vendite anno fiscale", "Contratti" e "Previsione". La seguente illustrazione mostra la sezione rilevante dello schema. È quindi possibile suddividere uno o tutti questi scenari in colonne separate per ogni trimestre dell'anno fiscale, in modo che il responsabile del reparto vendite possa correttamente immettere gli importi di previsione per ciascun periodo.

[![Colonne](./media/columns.png)](./media/columns.png)

Inoltre, è possibile specificare se ogni elemento di layout (colonna) è modificabile e se è disponibile in qualsiasi modello del foglio di lavoro creato per il layout. Per lo schema di esempio, nel layout utilizzato per la fase di "stima", le colonne di "previsione" sono modificabili, mentre le colonne di "vendite anno fiscale" e dei "contratti" sono di sola lettura.

> [!NOTE]
> Per impostazione predefinita viene limitato a 36 colonne a meno che non si estenda la pianificazione di budget con i passaggi descritti in [Estendere il layout di pianificazione del budget](./extending-budget-planning-layout.md).

### <a name="templates"></a>Modelli

Nella sezione **Layout** della pagina **Configurazione pianificazione del budget**, è possibile generare, visualizzare o caricare un modello di Excel per ogni layout. Questi modelli sono le cartelle di lavoro che vengono collegate a ogni di piano di budget per fornire funzionalità aggiuntive di analisi, creazione di grafici e immissioni dati.

Quando un modello viene generato, il layout è bloccato e non può essere modificato. Il blocco assicura che il formato del modello corrisponda al layout del piano di budget e includa gli stessi dati. Una volta generato, un modello può essere visualizzato e modificato. Ad esempio, è possibile aggiungere grafici al modello o personalizzarne ulteriormente l'aspetto.

> [!NOTE]
> Un modello deve essere salvato in un percorso a cui l'utente ha accesso, in modo da poterlo caricare nel layout una volta completata la modifica. In tal modo il modello verrà utilizzato con i piani di budget che utilizzano il layout.

### <a name="descriptions"></a>Descrizioni

Nella sezione **Layout** è possibile assegnare le descrizioni per visualizzare il nome di una dimensione finanziaria inclusa in un layout. Ad esempio, un'organizzazione potrebbe voler mostrare il nome dell'account principale accanto al numero dell'account principale in un piano di budget. Tuttavia, potrebbe voler omettere i nomi di altre dimensioni finanziarie, per evitare di ingombrare lo schermo.

## <a name="setting-up-budget-planning-processes"></a>Impostazione dei processi di pianificazione del budget

Dopo aver completato la configurazione della pianificazione del budget, è possibile impostare i processi di pianificazione del budget nella pagina **Processo di pianificazione del budget**. I processi di pianificazione del budget sono set di regole che determinano come possono essere aggiornati, indirizzati, rivisti e approvati i piani del budget nella gerarchia dell'organizzazione per la definizione del budget.

Per ciascun processo di pianificazione del budget, selezionare per prima cosa un ciclo di budget e una contabilità generale. Ogni processo di pianificazione del budget è correlato a un solo ciclo di budget e una contabilità generale. Quindi selezionare la gerarchia organizzativa del budget nella Scheda dettaglio **Amministrazione del processo di pianificazione del budget** e assegnare un flusso di lavoro di pianificazione del budget a tutti i centri di responsabilità dell'organizzazione visualizzati nella griglia.

Per assegnare o modificare il flusso di lavoro di pianificazione del budget per centri di responsabilità simili, selezionare **Assegna flusso di lavoro**, quindi selezionare il tipo di organizzazione da destinare e il flusso di lavoro di pianificazione del budget da utilizzare. L'ID del flusso di lavoro di impostazione del budget associato a ciascun flusso di lavoro di pianificazione del budget viene aggiunto alla griglia automaticamente.

Quando si definiscono le regole di fase e i modelli nella Scheda dettaglio **Regole e layout fase di pianificazione del budget**, è possibile definire un diverso set di regole e layout predefiniti per ogni fase di pianificazione del budget. Ad esempio, la fase di "stima" del reparto vendite può permettere agli utenti di modificare le righe di un piano di budget ma proibire di aggiungere righe. La fase "Invio completato" può permettere agli utenti di visualizzare le righe, ma non di aggiungerle o modificarle, perché il lavoro in questa fase è completato e le modifiche del piano di budget devono essere evitate. Per selezionare i layout disponibili per il piano di budget, selezionare **Layout alternativi**.

Si può scegliere di selezionare le priorità di pianificazione del budget nella scheda dettaglio **Vincoli di priorità di piano di budget**. Le priorità possono essere selezionate nei piani di budget.

Il passaggio finale consiste nell'attivare il processo di pianificazione del budget utilizzando il menu **Azioni**. Un processo di pianificazione del budget non può essere utilizzato fino a quando non è stato attivato.

Il menu **Azioni** può essere utilizzato per creare un nuovo processo copiandone uno esistente. Questa funzionalità è utile per le organizzazioni che seguono lo stesso flusso di processo per ogni ciclo di budget ed effettuano poche o nessuna modifica.

Un altro comando utile nel menu **Azioni** è **Visualizza stato del processo di budget**. Questo comando consente di mostrare graficamente i piani di budget all'interno di un processo, insieme ai dati rilevanti, ad esempio lo stato del flusso di lavoro dei piani, i riepiloghi per importo e per unità e la navigazione con un clic ai piani di budget stessi.

[![Stato del processo di pianificazione del budget](./media/budgetplanningprocessstatus-300x171.png)](./media/budgetplanningprocessstatus.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]