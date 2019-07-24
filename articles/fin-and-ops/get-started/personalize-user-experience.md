---
title: Personalizzare l'esperienza utente
description: In questo argomento viene illustrato come personalizzare Microsoft Dynamics 365 for Finance and Operations.
author: jasongre
manager: AnnBe
ms.date: 06/11/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysUserSetup, DefaultDashboard
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 62363
ms.assetid: 57b445d7-3e9e-4228-8728-f63b9dbd77a3
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 51c4cbbba36ed4c93fbbba907031023060d51495
ms.sourcegitcommit: 0273905ceb371ba17d3a37d690e1f568aa968b4f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/11/2019
ms.locfileid: "1625013"
---
# <a name="personalize-the-user-experience"></a>Personalizzare l'esperienza utente

[!include [banner](../includes/banner.md)]

In questo argomento viene illustrato come personalizzare Microsoft Dynamics 365 for Finance and Operations.

Sono disponibili tre classi di base di personalizzazioni in Finance and Operations.

- Personalizzazioni effettuate in una pagina di impostazione. Alcuni esempi sono rappresentati dal tema del colore e dal fuso orario.
- Personalizzazioni correlate all'utilizzo delle pagine , denominate personalizzazioni *implicite*. Ad esempio, Finance and Operations tiene traccia della larghezza delle colonne della griglia se le si regola e dello stato espanso o compresso delle Schede dettaglio.
- Personalizzazioni che un utente applica per modificare l'aspetto di una pagina modificando il modo in cui un elemento viene visualizzato nella pagina, spesso attraverso una modalità di personalizzazione interattiva. Queste personalizzazione sono definite personalizzazioni *esplicite*. Ad esempio, l'utente può aggiungere, nascondere o riordinare gli elementi nella pagina.

Ogni personalizzazione che un utente applica in Finance and Operations è valida solo per tale utente, indipendentemente dal tipo di personalizzazione o dalla società con cui l'utente interagisce. Le modifiche che un utente apporta a una pagina non influiscono su altri utenti nel sistema.

## <a name="system-wide-options-for-the-current-user"></a>Opzioni a livello di sistema per l'utente corrente

La pagina **Opzioni utente** contiene molte impostazioni a livello di sistema per l'utente corrente. Per aprire la pagina **Opzioni utente**, selezionare il menu **Impostazioni** (il simbolo di ingranaggio) nella barra di navigazione e quindi selezionare **Opzioni utente**. La pagina **Opzioni utente** dispone di quattro schede contenenti varie impostazioni utente:

- **Visuale** - Consente di selezionare un tema di colori e le dimensioni predefinite degli elementi nelle pagine.
- **Preferenze** - Consente di selezionare valori predefiniti che vengono utilizzati ogni volta che si apre Finance and Operations. Questi valori includono la società, la pagina iniziale e la modalità di visualizzazione predefinita/modifica. La modalità di visualizzazione/modifica determina se una pagina viene bloccata per la visualizzazione o aperta per la modifica ogni volta che la si apre. Questa scheda include anche opzioni per la lingua, il fuso orario, il formato di data e ora e il formato dei numeri. Infine, questa scheda include molte preferenze varie che cambiano da versione a versione.
- **Account** - Consente di impostare il nome utente e altre opzioni correlate all'account.
- **Flusso di lavoro** - Consente di selezionare opzioni correlate ai flussi di lavoro.

Oltre a modificare le impostazioni utente, è anche possibile visualizzare ed eliminare i dati utilizzo e le personalizzazioni facendo clic sul pulsante **Dati utilizzo**. Quando si utilizza l'applicazione, molte delle selezioni dell'utente vengono salvate, in modo da facilitare l'utilizzo successivo del sistema. La scheda **Personalizzazione**, in particolare, consente di visualizzare e gestire le modifiche personali effettuate nelle pagine del sistema. I callout di funzionalità, le finestre popup che introducono a nuove funzionalità del prodotto (disponibili nell'aggiornamento 26 della piattaforma), possono essere reimpostati da questa scheda in modo da essere di nuovo avvisati sulle funzionalità incontrate in precedenza.  

## <a name="implicit-personalizations"></a>Personalizzazioni implicite

Le personalizzazioni implicite sono personalizzazioni che vengono applicate semplicemente interagendo con i controlli che ricordano il relativo stato visibile corrente.

- **Colonne della griglia** - È possibile regolare la larghezza di una colonna in una griglia selezionando la barra di ridimensionamento a sinistra o a destra dell'intestazione di colonna e facendola scorrere verso sinistra o verso destra fino a raggiungere la larghezza desiderata. Finance and Operations memorizza la larghezza che si imposta per una colonna. Ridimensiona quindi la colonna a quella larghezza ogni volta che si pare la pagina contenente la griglia.
- **Schede dettaglio** - Alcune pagine hanno sezioni espandibili denominate *Schede dettaglio*. Finance and Operations memorizza le informazioni sulle Schede dettaglio che sono state espanse e compresse. Quindi, ogni volta che si torna alla pagina, le stesse Schede dettaglio saranno compresse o espanse, a seconda dell'ultima interazione con la pagina. In alcuni casi, comprimere una scheda dettaglio può migliorare le prestazioni del sistema poiché Finance and Operations non dovrà recuperare le informazioni relative a tale Scheda dettaglio finché questa non viene espansa. Come descritto più avanti in questo argomento, è possibile modificare anche l'ordine delle Schede dettaglio in una pagina.
- **Riquadri dettaglio** - Alcune pagine presentano una sezione denominata *Riquadro dettaglio*. Questo riquadro contiene informazioni di sola lettura che sono correlate all'argomento corrente della pagina. Ciascuna sezione del riquadro dettaglio è chiamata casella *Dettaglio*. È possibile visualizzare o nascondere l'intero riquadro dettaglio ed è possibile espandere o comprimere singole caselle dettaglio. Finance and Operations memorizza le preferenze dell'utente. Quindi, ogni volta che si torna alla pagina, lo stato del riquadro dettaglio e delle singole caselle Dettaglio viene ripristinato, in base all'ultima interazione con la pagina. In alcuni casi, comprimere un riquadro dettaglio può migliorare le prestazioni del sistema poiché Finance and Operations non dovrà recuperare le informazioni relative a tale riquadro finché questo non viene espanso.
- **Riquadri azioni** - Un *riquadro azioni* appare accanto alla parte superiore della maggior parte delle pagine. Il riquadro azioni contiene pulsanti per molte delle azioni che è possibile eseguire nella pagina corrente. Questi pulsanti sono spesso organizzati in schede. È possibile tenere aperto l'intero riquadro azioni oppure fare in modo che venga compresso per impostazione predefinita. Quindi, la volta successiva che si aprire la pagina, Finance and Operations ripristinerà lo stato aggiunto del riquadro azioni. Se il riquadro azioni è impostato per rimanere sempre aperto, Finance and Operations visualizza anche la scheda di azioni utilizzate più di recente.
- **QuickFilter** - Un *QuickFilter* viene visualizzato sopra molte griglie. Il QuickFilter consente di filtrare la griglia, in base alla colonna che si seleziona. Finance and Operations memorizza la colonna su cui è stato basato il filtro. Quindi, la volta successiva che si apre la pagina contenente la griglia, la griglia viene filtrata in base alla stessa colonna. Tuttavia, è possibile filtrare la griglia in base a una colonna diversa.
- **Filtri di intestazione di colonna** - Quando si filtra una griglia utilizzando i *Filtri di intestazione di colonna*, è possibile modificare l'operatore di filtro per trovare i dati desiderati. Ad esempio, è possibile modificare l'operatore **inizia con** in **è esattamente**. Ogni volta che si utilizza un filtro di intestazione di colonna e si modifica l'operatore di filtro, Finance and Operations memorizza la modifica. Ripristinerà l'operatore di filtro la volta successiva che si filtra tale colonna.
- **Pannello di navigazione** - È possibile aprire il *Pannello di navigazione* selezionando il pulsante **Menu** nel riquadro sinistro di qualsiasi pagina. Il pulsante **Menu** viene talvolta indicato con il termine *hamburger*, *menu hamburger* o *pulsante hamburger*. È possibile impostare il pannello di navigazione in modo che resti sempre aperto oppure lo si può mantenere compresso per impostazione predefinita. Dopo che si imposta il pannello di navigazione in modo che resti aperto, Finance and Operations lo manterrà aperto fino a quando non lo si comprime.

## <a name="explicit-personalizations"></a>Personalizzazioni esplicite

Persone e società diverse hanno una diversa prospettiva in merito ai dati che ritengono più importanti o ai dati che non sono necessari per la conduzione degli affari. In Finance and Operations, è possibile personalizzare il modo in cui le informazioni vengono ordinate e con cui si interagisce. È inoltre possibile specificare che alcune informazioni debbano essere nascoste. Queste funzionalità sono fondamentali per un'esperienza personale e produttiva e sono esempi di personalizzazioni esplicite. Le personalizzazioni esplicite sono quelle che l'utente applica esplicitamente con l'intento di modificare l'aspetto o il comportamento di un elemento o di una pagina.

### <a name="shortcut-menu-options"></a>Opzioni di menu di scelta rapida

I menu di scelta rapida forniscono alcuni modi per modificare una pagina in modo esplicito in modo che rispecchi meglio i requisiti dell'utente o della società. Un menu di scelta rapida è noto anche con il nome di *menu del pulsante destro del mouse* o *menu contestuale*.

Alcune delle modifiche più tipiche e più importanti che possono essere apportate a una pagina sono disponibili direttamente come opzioni in un menu di scelta rapida. Ad esempio, a partire dall'aggiornamento 17 della piattaforma, per aggiungere o nascondere le colonne di una griglia, è sufficiente fare clic con il pulsante destro del mouse sull'intestazione di una colonna della griglia e selezionare **Aggiungi colonne** o **Nascondi questa colonna**.

Inoltre, i tipi più fondamentali di personalizzazione esplicita sono disponibili facendo clic con il pulsante destro del mouse su un elemento e quindi selezionando **Personalizza**. Tenere presente che non tutti gli elementi nella pagina possono essere personalizzati. Quando si utilizza questo metodo di personalizzazione, viene visualizzata la finestra delle proprietà dell'elemento.

![Personalizzazione delle proprietà di un elemento](./media/personalization-element-properties.png)

È possibile utilizzare la finestra delle proprietà per personalizzare un elemento nei seguenti modi:

- Modificare l'etichetta dell'elemento.
- Nascondere l'elemento in modo che non venga mostrato nella pagina. I dati del campo non vengono eliminati o modificati. Le informazioni semplicemente non vengono più visualizzate nella pagina.
- Includere le informazioni nella sezione di riepilogo della Scheda dettaglio (se l'elemento è in una Scheda dettaglio).
- Ignorare il campo quando si preme TAB per spostarsi tra i campi presenti nella pagina.
- Impedire la modifica dei dati nel campo (per qualsiasi record).

La finestra delle proprietà potrebbe includere altre funzionalità di personalizzazione, a seconda dell'elemento. Ad esempio, la finestra delle proprietà di un riquadro potrebbe consentire di promuovere il riquadro in un dashboard e la finestra delle proprietà di un dashboard potrebbe consentire di creare una nuova area di lavoro in quel dashboard.

### <a name="the-personalization-toolbar"></a>Barra degli strumenti di personalizzazione

Se si desidera apportare più modifiche a una pagina o apportare modifiche che non sono disponibili attraverso altri meccanismi (ad esempio un nuovo ordine degli elementi), è possibile utilizzare la barra degli strumenti **Personalizzazione**. Per aprire la barra degli strumenti **Personalizzazione**, selezionare **Personalizza modulo** nella finestra delle proprietà di un elemento. È inoltre possibile selezionare **Personalizza modulo** nel gruppo **Personalizza** della scheda **Opzioni** del riquadro azioni di ogni pagina.

[![Barra degli strumenti di personalizzazione](./media/restyledPersonalizationToolbar.png)](./media/restyledPersonalizationToolbar.png)

#### <a name="navigating-the-page"></a>Esplorazione della pagina

La possibilità di esplorare la pagina mentre la **barra degli strumenti Personalizzazione** è aperta dipende dalla versione della piattaforma in esecuzione.

- Prima dell'aggiornamento 19 della piattaforma, mentre la barra degli strumenti **Personalizzazione** è aperta, la pagina è in sola lettura (non è possibile inserire nulla) e non interattiva (non è possibile apportare modifiche agli elementi visibili nella pagina). Se si desidera modificare gli elementi in una sezione compressa o in una scheda diversa, occorre chiudere la barra degli strumenti **Personalizzazione**, espandere una sezione o passare alla scheda desiderata e quindi riaprire la barra degli strumenti **Personalizzazione**.

- A partire dall'aggiornamento 19 della piattaforma, se la barra degli strumenti **Personalizzazione** è aperta, la pagina è ancora in sola lettura ma è molto più interattiva. In particolare, è possibile espandere o comprimere il riquadro Dettaglio informazioni, passare tra le schede ed espandere o comprimere le sezioni mentre la barra degli strumenti **Personalizzazione** è aperta nello stesso modo in cui si farebbe normalmente nella pagina. Per applicare una modifica di personalizzazione a una sezione comprimibile o a una scheda (ad esempio per nascondere una Scheda dettaglio), si selezionerà il pulsante che appare accanto alla sezione comprimibile o alla scheda quando diventa attivo da tastiera o quando ci si sofferma con il puntatore del mouse.

#### <a name="personalization-tools"></a>Barre degli strumenti di personalizzazione

Nella barra degli strumenti **Personalizzazione** sono disponibili gli strumenti seguenti:

- Utilizzare lo strumento **Selezione** per selezionare e modificare le proprietà di un elemento. Selezionare lo strumento **Selezione** e quindi selezionare l'elemento di cui modificare le proprietà. Quando si seleziona un elemento, la finestra delle proprietà dell'elemento si apre ed è possibile modificare qualsiasi proprietà di tale elemento. È possibile ripetere il processo per altri elementi che possono essere personalizzati in tale pagina. Tuttavia, a causa del modo in cui alcuni elementi vengono utilizzati, Finance and Operations non consente di modificare alcune delle proprietà di tali elementi. Pertanto, quando si seleziona un elemento, è possibile che alcune proprietà non possano essere modificate. Ad esempio, non è possibile nascondere un campo obbligatorio.
- Utilizzare lo strumento **Sposta** se si desidera selezionare e spostare un elemento in un punto diverso all'interno del gruppo corrente di elementi. (Non è possibile spostare un elemento al di fuori del gruppo padre). Selezionare lo strumento **Sposta** e quindi selezionare l'elemento da spostare. Quando si seleziona un elemento, Finance and Operations analizza la pagina per determinare il punto in cui l'elemento può essere spostato. Crea quindi una serie di "aree di rilascio". Man mano che si trascina l'elemento nel gruppo corrente, ogni "zona di rilascio" viene visualizzata come singola riga colorata e in grassetto accanto all'area in cui l'elemento può essere rilasciato.
- Utilizzare lo strumento **Nascondi** per nascondere un elemento nella pagina. Selezionare lo strumento **Nascondi** e quindi selezionare l'elemento da nascondere. Quando si seleziona lo strumento **Nascondi**, tutti gli elementi correntemente nascosti diventano visibili e vengono visualizzati in un contenitore ombreggiato. È quindi possibile scoprirli. Selezionando lo strumento **Selezione** è possibile vedere come apparirà la pagina con gli elementi selezionati nascosti.

    - A partire dall'aggiornamento 18 della piattaforma, è possibile nascondere i campi obbligatori e le sezioni che contengono campi obbligatori. Ciò consente di creare un'esperienza semplificata in cui i campi obbligatori che sono impostati su valori predefiniti dalla logica di business non vengono mostrati. I campi obbligatori nascosti vengono inoltre resi temporaneamente visibili se sono vuoti quando si prova a eseguire il salvataggio.

- Utilizzare lo strumento **Riepilogo** quando si desidera che un elemento venga visualizzati nella sezione di riepilogo della Scheda dettaglio. Lo strumento Riepilogo si applica solo ai campi che sono contenuti in una sezione della Scheda dettaglio. Quando si seleziona lo strumento **Riepilogo**, tutti i campi che sono stati selezionati come campi riepilogativi vengono visualizzati in un contenitore ombreggiato. È possibile aggiungere e rimuovere in modo interattivo i campi dal riepilogo della Scheda dettaglio selezionando i campi interessati.
- Utilizzare lo strumento **Ignora** per rimuovere un elemento dalla sequenza di tabulazione della tastiera nella pagina. Quando si seleziona lo strumento **Ignora**, tutti gli elementi correntemente ignorati vengono visualizzati in un contenitore ombreggiato. È quindi possibile inserirli nuovamente nella sequenza di tabulazione.
- Utilizzare lo strumento **Modifica** per contrassegnare un elemento come modificabile o non modificabile. Quando si seleziona lo strumento **Modifica**, tutti gli elementi correntemente non modificabili vengono visualizzati in un contenitore ombreggiato. È quindi possibile renderli nuovamente modificabili. Alcuni campi sono obbligatori e non possono essere resi non modificabili. Accanto a questi campi è presente un simbolo di lucchetto.
- Utilizzare il pulsante **Inserisci** per vedere un elenco di elemento che possono essere inseriti in una pagina.

    - Selezionare lo strumento **Campo** in **Inserisci** per aggiungere un campo nella pagina. Quando si utilizza lo strumento **Campo**, è possibile aggiungere solo i campi che fanno parte della definizione della pagina ma che attualmente non sono visualizzati nella pagina. Per informazioni su come creare nuovi campi che non fanno parte della definizione della pagina corrente, vedere [Campi personalizzati](user-defined-fields.md). Dopo aver selezionato lo strumento **Campo**, è necessario prima di tutto selezionare il gruppo o l'area in cui si desidera aggiungere un campo. Viene visualizzata una finestra di dialogo con l'elenco di campi correlati al gruppo selezionato o all'area selezionata. Nella finestra di dialogo selezionare uno o più campi da aggiungere e quindi selezionare **Inserisci**. Per rimuovere un campo aggiunto in precedenza, ripetere il processo, ma deselezionare il campo nella finestra di dialogo.
    - Selezionare lo strumento **PowerApp** in **Inserisci** per incorporare un'app creata tramite Microsoft PowerApps nella pagina. Per informazioni dettagliate su come incorporare un'app PowerApp in una pagina, vedere [Incorporare PowerApps](embed-power-apps.md).

- Selezionare il pulsante **Gestisci** per visualizzare un elenco di opzioni di gestione correlate a tutte le personalizzazioni per la pagina corrente.

    - Selezionare **Cancella** per reimpostare la pagina sullo stato installato predefinito. Tutte le personalizzazioni della pagina corrente vengono cancellate. L'azione di annullamento non è disponibile. Di conseguenza, utilizzare questa opzione solo se si è certi di voler reimpostare la pagina.
    - Selezionare **Importa** per caricare una personalizzazione da un file precedentemente creato per la pagina. Tutte le personalizzazioni correnti per la pagina vengono sostituite con le personalizzazioni del file selezionato.
    - Selezionare **Esporta** per salvare le impostazioni per la pagina in un file. È possibile condividere le personalizzazioni con altri utenti. Tali utenti devono semplicemente importare il file contenente le personalizzazioni per la pagina.

- Selezionare il pulsante **Chiudi** per chiudere la barra degli strumenti **Personalizzazione** e ripristinare la pagina allo stato interattivo precedente.

Quando la barra degli strumenti **Personalizzazione** viene utilizzata, le operazioni di salvataggio sono implicite. Le personalizzazioni diventano effettive non appena le si crea e non occorre selezionare un pulsante **Salva**. In alcuni casi, quando si seleziona uno strumento,viene visualizzata un'icona a forma di lucchetto accanto a un elemento. Il simbolo indica che non è possibile modificare le proprietà dell'elemento correlate allo strumento selezionato, perché le modifiche a tali proprietà impediscono il corretto funzionamento della pagina.

### <a name="adding-a-tile-list-or-link-to-a-workspace"></a>Aggiunta di un riquadro, un elenco o un collegamento a un'area di lavoro

Per alcune pagine che includono elenchi, è disponibile una funzionalità di personalizzazione aggiuntiva. Il pulsante **Aggiungi ad area di lavoro** nel gruppo **Personalizza** nella scheda **Opzioni** del riquadro azioni consente di mostrare le informazioni dell'elenco corrente in un'area di lavoro specifica. È possibile mostrare una visualizzazione filtrata e ordinata delle informazioni nell'area di lavoro oppure è possibile mostrare la visualizzazione predefinita. È inoltre possibile specificare se le informazioni appaiono nell'area di lavoro come elenco, come riquadro di riepilogo che può mostrare il numero di voci nell'elenco come collegamento.

[![Aggiungi ad area di lavoro](./media/personalization-addtoworkspace.png)](./media/personalization-addtoworkspace.png)

- Per aggiungere un elenco a un'area di lavoro, prima di tutto ordinare o filtrare l'elenco nella pagina in modo che mostri le informazioni come si desidera vengano visualizzate nell'area di lavoro. Selezionare quindi **Aggiungi ad area di lavoro**. Selezionare un'area di lavoro, quindi nel campo **Presentazione** selezionare **Elenco**. Dopo aver selezionato **Configura**, viene visualizzata una finestra di dialogo in cui è possibile selezionare le colonne da visualizzare nell'elenco nell'area di lavoro. È possibile inoltre specificare l'etichetta da utilizzare per l'elenco nell'area di lavoro.
- Per aggiungere un riquadro a un'area di lavoro, filtrare prima di tutto l'elenco nella pagina in modo da mostrare i dati da riepilogare o a cui si desidera accedere rapidamente. Selezionare quindi **Aggiungi ad area di lavoro**. Selezionare un'area di lavoro, quindi nel campo **Presentazione** selezionare **Riquadro**. Dopo aver selezionato **Configura**, viene visualizzata una finestra di dialogo in cui è possibile specificare l'etichetta da utilizzare per il riquadro nell'area di lavoro. È inoltre possibile specificare se il riquadro deve visualizzare un conteggio. Dopo avere aggiunto il riquadro nell'area di lavoro, è possibile selezionarlo per aprire la pagina corrente dall'area di lavoro e visualizzare l'elenco filtrato che è associato al riquadro.
- Per aggiungere un collegamento a un'area di lavoro, filtrare innanzitutto l'elenco nella pagina in modo da mostrare i dati desiderati. Selezionare quindi **Aggiungi ad area di lavoro**. Selezionare un'area di lavoro, quindi nel campo **Presentazione** selezionare **Collegamento**. Dopo aver selezionato **Configura**, viene visualizzata una finestra di dialogo in cui è possibile specificare l'etichetta da utilizzare per il collegamento. È facoltativamente possibile specificare un'etichetta per una nuova sezione che conterrà il collegamento.

Dopo avere aggiunto l'elenco, il riquadro o il collegamento in un'area di lavoro, è possibile aprire l'area di lavoro e riordinare gli elementi come si desidera.

### <a name="adding-a-summary-from-a-workspace-to-a-dashboard"></a>Aggiunta di un riepilogo da un'area di lavoro a un dashboard

In alcune aree di lavoro sono presenti riquadri di conteggio (ovvero riquadri contenenti numeri) e può essere utile visualizzare tali riquadri anche nel dashboard. In un'area di lavoro, fare clic con il pulsante destro del mouse su un riquadro di conteggio e quindi selezionare **Personalizza**. Nella finestra delle proprietà del riquadro selezionare quindi **Aggiungi a dashboard**. La volta successiva che si apre (e aggiorna) il dashboard selezionato, il conteggio viene visualizzato sotto il riquadro di navigazione di tale area di lavoro. È possibile selezionare il conteggio in modo che passi direttamente ai dati che rappresenta.

### <a name="personalizing-your-dashboard"></a>Personalizzazione del dashboard

Il dashboard è spesso la prima pagina che si visualizza quando si apre Finance and Operations. È possibile personalizzare il dashboard in modo che mostri solo i riquadri dell'area di lavoro che si desidera vedere. È inoltre possibile riorganizzare i riquadri in modo che siano nell'ordine in cui si preferisce visualizzarli, rinominare i riquadri di navigazione dell'area di lavoro oppure aggiungere un riquadro dell'area di lavoro completamente nuovo.

Per personalizzare il dashboard, fare clic con il pulsante destro del mouse su un qualsiasi riquadro e quindi selezionare **Personalizza** per aprire la finestra delle proprietà del riquadro.

- Se si desidera nascondere o rinominare il riquadro selezionato, è possibile apportare la modifica direttamente nella finestra delle proprietà.
- Per riordinare i riquadri dell'area di lavoro, nella finestra delle proprietà selezionare **Personalizza modulo** per aprire la barra degli strumenti **Personalizzazione**. È quindi possibile utilizzare lo strumento **Sposta** per disporre i riquadri nel modo desiderato.
- Per creare un nuovo riquadro dell'area di lavoro, nella finestra delle proprietà selezionare **Aggiungi area di lavoro**. Il nuovo riquadro dell'area di lavoro viene creato nella parte inferiore del dashboard. È possibile rinominare questo nuovo riquadro dell'area di lavoro come si preferisce. È inoltre possibile aggiungere elenchi, riquadri e collegamenti nell'area di lavoro come descritto nella sezione [Aggiunta di elenchi, riquadri o collegamenti nelle aree di lavoro](personalize-user-experience.md#adding-a-tile-list-or-link-to-a-workspace) di questo argomento.

## <a name="administration-of-personalization"></a>Amministrazione della personalizzazione

Dopo avere personalizzato una pagina, è possibile condividere le personalizzazioni con altri utenti esportando la pagina personalizzata. È possibile richiedere agli altri utenti di aprire la pagina personalizzata e di importare il file di personalizzazione creato. In alternativa, è possibile assegnare la personalizzazione a un utente con privilegi di amministratore. Tale utente può quindi applicare il file di personalizzazione a più utenti contemporaneamente.

Gli utenti con privilegi di amministrazione possono anche gestire le personalizzazioni per altri utenti nella pagina **Personalizzazione**. Questa pagina include quattro schede:

- **Applica** - È possibile importare o selezionare una personalizzazione per uno o più utenti. Per applicare una personalizzazione a uno o più utenti, selezionare innanzitutto un ruolo e gli utenti con quel ruolo. Selezionare quindi una personalizzazione esistente da applicare agli utenti selezionati o importare un file di personalizzazione. La personalizzazione viene convalidata e applicata a tutti gli utenti selezionati alla successiva apertura della pagina selezionata.
- **Cancella** - È possibile cancellare tutte le personalizzazioni di una pagina o un'area di lavoro per uno o più utenti. Selezionare prima di tutto una pagina o un'area di lavoro per vedere l'elenco degli utenti che l'hanno personalizzata. Selezionare quindi gli utenti per i quali occorre cancellare le personalizzazioni della pagina o dell'area di lavoro e selezionare **Cancella**. Tutte le personalizzazione che gli utenti selezionati hanno applicato alla pagina o all'area di lavoro selezionata vengono cancellate. Non è possibile annullare questa azione. Se tuttavia una personalizzazione della pagina o dell'area di lavoro viene salvata, tale personalizzazione può essere reimportata.
- **Gestione per utente** - Selezionare un utente per visualizzare l'elenco di pagine che l'utente ha personalizzato. È quindi possibile scegliere di attivare o disattivare la capacità dell'utente selezionato di utilizzare la personalizzazione di pagine specifiche o dell'intero sistema. È inoltre possibile importare, esportare o cancellare una personalizzazione per l'utente selezionato. Inoltre, è possibile reimpostare i callout di funzionalità per l'utente selezionato di modo che tutte le finestre popup chiuse in precedenza che introducevano nuove funzionalità siano visualizzate di nuovo quando l'utente incontra di nuovo tali funzionalità.   
- **Sistema** - È possibile disabilitare temporaneamente tutte le personalizzazioni per tutti gli utenti nel sistema. In questo caso, le personalizzazioni vengono eliminate. Tutte le pagine vengono semplicemente reimpostate sullo stato predefinito per tutti gli utenti. Se si abilitano nuovamente le personalizzazioni in un secondo momento, queste vengono applicate nuovamente. È inoltre possibile eliminare in modo permanente tutte le personalizzazioni per tutti gli utenti nel sistema. Non è possibile recuperare le personalizzazioni che sono state eliminate. Pertanto, prima di eseguire questa attività, assicurarsi di esportare tutte le personalizzazioni che si desidera importare successivamente.

## <a name="personalization-of-inventory-dimensions"></a>Personalizzazione delle dimensioni inventariali

Quando si personalizza l'impostazione delle dimensioni inventariali in una pagina, considerare le impostazioni create utilizzando l'opzione **Visualizza dimensioni**. Ad esempio, è possibile utilizzare la personalizzazione per nascondere una colonna per la dimensione inventariale del numero batch, ma alla successiva apertura della pagina la colonna sarà di nuovo visibile. Questo comportamento si verifica perché le impostazioni **Visualizzazione di dimensioni** controllano le colonne di dimensioni inventariali che vengono visualizzate.

Le impostazioni **Visualizzazione dimensioni** vengono applicate a tutte le pagine e sostituiscono qualsiasi impostazione personalizzata dei campi delle dimensioni inventariali in ogni singola pagina.

Di conseguenza, nell'esempio precedente, se non si desidera che la colonna relativa alla dimensione inventariale del numero batch venga visualizzata in una pagina, è necessario cancellare la dimensione come parte dell'opzione **Dimensioni di visualizzazione** della tabella per quella pagina.
