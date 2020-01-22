---
title: Personalizzare l'esperienza utente
description: In questo argomento viene illustrato come personalizzare l'app.
author: jasongre
manager: AnnBe
ms.date: 01/07/2020
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
ms.openlocfilehash: ac8f154fdf892553f69d135727589bf13efd6076
ms.sourcegitcommit: 34395464ec80cea800b953eae49af579d436fc1b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "2935467"
---
# <a name="personalize-the-user-experience"></a>Personalizzare l'esperienza utente

[!include [banner](../includes/banner.md)]

In questo argomento viene illustrato come personalizzare l'app.

Sono disponibili tre classi di personalizzazione di base.

- Personalizzazioni effettuate in una pagina di impostazione. Alcuni esempi sono rappresentati dal tema del colore e dal fuso orario.
- Personalizzazioni correlate all'utilizzo della pagina. Queste personalizzazione sono definite personalizzazioni *implicite*. Ad esempio, il sistema tiene traccia della larghezza delle colonne della griglia se le si regola e dello stato espanso o compresso delle Schede dettaglio.
- Personalizzazioni che un utente applica all'aspetto di una pagina modificando il modo in cui un elemento viene visualizzato nella pagina, spesso attraverso una modalità di personalizzazione interattiva. Queste personalizzazione sono definite personalizzazioni *esplicite*. Ad esempio, l'utente può aggiungere, nascondere o riordinare gli elementi nella pagina.

Ogni personalizzazione che un utente applica è valida solo per tale utente, indipendentemente dal tipo di personalizzazione o dalla società con cui l'utente interagisce. Le modifiche che un utente apporta a una pagina non influiscono su altri utenti nel sistema.

## <a name="system-wide-options-for-the-current-user"></a>Opzioni a livello di sistema per l'utente corrente

La pagina **Opzioni utente** contiene molte impostazioni a livello di sistema per l'utente corrente. Per aprire la pagina **Opzioni utente**, selezionare il pulsante **Impostazioni** (il simbolo di ingranaggio) nella barra di navigazione e quindi selezionare **Opzioni utente**. La pagina **Opzioni utente** dispone di quattro schede contenenti varie impostazioni utente:

- **Visuale** - Consente di selezionare un tema di colori e le dimensioni predefinite degli elementi nelle pagine.
- **Preferenze** - Consente di selezionare valori predefiniti che vengono utilizzati ogni volta che si apre il sistema. Questi valori includono la società, la pagina iniziale e la modalità di visualizzazione predefinita/modifica. La modalità di visualizzazione/modifica determina se una pagina viene bloccata per la visualizzazione o aperta per la modifica ogni volta che la si apre. Questa scheda include anche opzioni per la lingua, il fuso orario, il formato di data e ora e il formato dei numeri. Infine, questa scheda include molte preferenze varie che cambiano da versione a versione.
- **Account** - Consente di impostare il nome utente e altre opzioni correlate all'account.
- **Flusso di lavoro** - Consente di selezionare opzioni correlate ai flussi di lavoro.

Oltre a modificare le impostazioni utente, è anche possibile visualizzare ed eliminare i dati utilizzo e le personalizzazioni nella pagina **Opzioni utente**. Selezionare **Dati utilizzo** nel riquadro azioni.

Quando si utilizza l'app, molte delle selezioni dell'utente vengono archiviate, in modo da facilitare l'utilizzo successivo del sistema. Nella scheda **Personalizzazione** è possibile visualizzare e gestire le modifiche personali effettuate nelle pagine del sistema. In questa scheda, è inoltre possibile reimpostare i callout della funzionalità (ovvero le finestre popup che introducono nuove funzionalità di sistema). Si viene quindi di nuovo avvisati sulle funzionalità precedentemente rilavate.

> [!NOTE]
> Se la funzionalità [Visualizzazioni salvate](saved-views.md) è attivata, è possibile visualizzare e gestire le personalizzazioni selezionando **Personalizzazione** nel riquadro azioni della pagina **Opzioni utente**.

## <a name="implicit-personalizations"></a>Personalizzazioni implicite

Le personalizzazioni implicite sono personalizzazioni che vengono applicate semplicemente interagendo con i controlli che memorizzano il relativo stato visibile corrente.

- **Colonne della griglia** - È possibile regolare la larghezza di una colonna in una griglia selezionando la barra di ridimensionamento a sinistra o a destra dell'intestazione di colonna e facendola scorrere verso sinistra o verso destra fino a raggiungere la larghezza desiderata. L'app memorizza la larghezza che si imposta per una colonna. Quindi, alla successiva apertura della pagina che include quella griglia, la colonna verrà ridimensionata a quella larghezza.
- **Schede dettaglio** - Alcune pagine hanno sezioni espandibili denominate *Schede dettaglio*. L'app memorizza le informazioni sulle Schede dettaglio che sono state espanse e compresse. Quindi, la volta successiva che si apre la pagina, le stesse Schede dettaglio saranno compresse o espanse, a seconda dell'ultima interazione con la pagina. In alcuni casi, comprimere una scheda dettaglio può migliorare le prestazioni del sistema poiché l'app non dovrà recuperare le informazioni relative alle Schede dettaglio finché non vengono espanse. Come descritto più avanti in questo argomento, è possibile modificare anche l'ordine delle Schede dettaglio in una pagina.
- **Riquadri dettagli** – Alcune pagine includono un riquadro **Informazioni correlate** che mostra informazioni di sola lettura correlate all'argomento corrente della pagina. Ciascuna sezione del riquadro **Informazioni correlate** è chiamata *riquadro dettagli*. È possibile espandere o comprimere il riquadro **Informazioni correlate** ed è possibile espandere o comprimere i singoli riquadri dettagli. L'app memorizza queste preferenze. Quindi, la volta successiva che si apre la pagina, il riquadro **Informazioni correlate** e i singoli riquadri dettagli saranno espansi o compressi, in base all'ultima interazione con la pagina. In alcuni casi, comprimere un riquadro dettaglio può migliorare le prestazioni del sistema poiché l'app non dovrà recuperare le informazioni relative ai riquadri dettaglio finché non vengono espansi.
- **Riquadri azioni** - Un *riquadro azioni* appare accanto alla parte superiore della maggior parte delle pagine. Il riquadro azioni contiene pulsanti per molte delle azioni che è possibile eseguire nella pagina corrente. Questi pulsanti sono spesso organizzati in schede. È possibile aggiungere l'intero riquadro azioni aperto oppure fare in modo che venga compresso per impostazione predefinita. Quindi, la volta successiva che si apre la pagina, il riquadro azioni saranno aperto o compresso, a seconda dell'ultima interazione con la pagina. Se è stato aggiunto il riquadro azioni aperto, verrà visualizzata l'ultima scheda utilizzata.
- **QuickFilter** - Un *QuickFilter* viene visualizzato sopra molte griglie. Il QuickFilter consente di filtrare la griglia, in base alla colonna che si seleziona. L'app memorizza la colonna su cui è stato basato il filtro. Quindi, la volta successiva che si apre la pagina contenente la griglia, la griglia viene filtrata in base alla stessa colonna. Tuttavia, è possibile filtrare la griglia selezionando una colonna diversa.
- **Filtri di intestazione di colonna** - Quando si filtra una griglia utilizzando i *Filtri di intestazione di colonna*, è possibile modificare l'operatore di filtro per trovare i dati desiderati. Ad esempio, è possibile modificare l'operatore **inizia con** in **è esattamente**. Ogni volta che si utilizza un filtro di intestazione di colonna e si modifica l'operatore di filtro, l'app memorizza la modifica. La volta successiva che si filtra tale colonna, l'operatore di filtro verrà ripristinato.
- **Pannello di navigazione** - È possibile aprire il *Pannello di navigazione* selezionando il pulsante **Espandere il pannello di navigazione** in alto a sinistra di qualsiasi pagina. Questo pulsante viene talvolta indicato come pulsante _**Menu**_, *hamburger*, *menu hamburger* o *pulsante hamburger*. È possibile aggiungere il pannello di navigazione aperto oppure compresso per impostazione predefinita. Dopo che si imposta il pannello di navigazione in modo che resti aperto, l'app lo manterrà aperto fino a quando non lo si comprime.

## <a name="explicit-personalizations"></a>Personalizzazioni esplicite

Persone e società diverse hanno una diversa prospettiva in merito ai dati che ritengono più importanti e ai dati che non sono necessari per la conduzione degli affari. È possibile personalizzare il modo in cui le informazioni vengono ordinate e con cui si interagisce. È inoltre possibile specificare che alcune informazioni debbano essere nascoste. Queste funzionalità sono fondamentali per un'esperienza personale e produttiva e sono esempi di personalizzazioni esplicite. Le personalizzazioni esplicite sono quelle che l'utente applica esplicitamente per modificare l'aspetto o il comportamento di un elemento o di una pagina.

### <a name="shortcut-menu-options"></a>Opzioni di menu di scelta rapida

I menu di scelta rapida forniscono alcuni modi per modificare una pagina in modo esplicito in modo che soddisfi meglio i requisiti dell'utente o della società. Un menu di scelta rapida è noto anche con il nome di *menu del pulsante destro del mouse* o *menu contestuale*.

Alcune delle modifiche più tipiche e più importanti che possono essere apportate a una pagina sono disponibili direttamente come opzioni in un menu di scelta rapida. Ad esempio, a partire dall'aggiornamento 17 della piattaforma, per aggiungere o nascondere le colonne di una griglia, è sufficiente fare clic con il pulsante destro del mouse sull'intestazione di una colonna e selezionare **Aggiungi colonne** o **Nascondi questa colonna**.

Inoltre, i tipi più fondamentali di personalizzazione esplicita sono disponibili facendo clic con il pulsante destro del mouse su un elemento e quindi selezionando **Personalizza**. Tenere presente che non tutti gli elementi nella pagina possono essere personalizzati. Quando si utilizza questo metodo di personalizzazione, viene visualizzata la finestra delle proprietà dell'elemento.

![Personalizzazione delle proprietà di un elemento](./media/personalization-element-properties.png)

È possibile utilizzare la finestra delle proprietà per personalizzare un elemento nei seguenti modi:

- Modificare l'etichetta dell'elemento.
- Nascondere l'elemento in modo che non venga mostrato nella pagina. I dati del campo non vengono eliminati o modificati. Le informazioni semplicemente non vengono più visualizzate nella pagina.
- Includere le informazioni nella sezione di riepilogo della Scheda dettaglio (se l'elemento è in una Scheda dettaglio).
- Ignorare il campo, in modo che non diventi mai in stato attivo mentre si scorre la pagina.
- Impedire la modifica dei dati nel campo (per qualsiasi record).

La finestra delle proprietà potrebbe includere altre funzionalità di personalizzazione, a seconda dell'elemento. Ad esempio, la finestra delle proprietà di un riquadro potrebbe consentire di promuovere il riquadro in un dashboard e la finestra delle proprietà di un dashboard potrebbe consentire di creare una nuova area di lavoro in quel dashboard.

### <a name="the-personalization-toolbar"></a>Barra degli strumenti di personalizzazione

Se si desidera apportare più modifiche a una pagina o apportare modifiche che non sono disponibili attraverso altri meccanismi (ad esempio se si desidera riordinare gli elementi), è possibile utilizzare la barra degli strumenti **Personalizzazione**. Per aprire la barra degli strumenti **Personalizzazione**, effettuare una delle seguenti operazioni:

- Selezionare **Personalizza modulo** nella finestra di proprietà dell'elemento.
- Selezionare **Personalizza questa pagina** nel gruppo **Personalizza** della scheda **Opzioni** del riquadro azioni di qualsiasi pagina.
- Selezionare il pulsante **Impostazioni** (il simbolo di ingranaggio) sulla barra di navigazione, quindi **Personalizza**.

[![Barra degli strumenti di personalizzazione](./media/restyledPersonalizationToolbar.png)](./media/restyledPersonalizationToolbar.png)

#### <a name="navigating-the-page"></a>Esplorazione della pagina

Quando viene aperta la barra degli strumenti **Personalizzazione**, la pagina sottostante è di sola lettura (in altre parole, non è possibile modificare i dati), ma è ancora interattiva. In particolare, è possibile espandere o comprimere il riquadro **Informazioni correlate**, cambiare schede ed espandere o comprimere le sezioni, esattamente come quelle azioni vengono eseguite nella pagina. Per applicare una personalizzazione a una sezione comprimibile o a una scheda (ad esempio per nascondere una Scheda dettaglio), è sufficiente selezionare il pulsante che appare accanto alla sezione o alla scheda quando diventa attivo da tastiera o quando ci si sofferma con il puntatore del mouse.

#### <a name="personalization-tools"></a>Barre degli strumenti di personalizzazione

Nella barra degli strumenti **Personalizzazione** sono disponibili gli strumenti seguenti:

- Utilizzare lo strumento **Selezione** per selezionare e modificare le proprietà di un elemento. Per utilizzare questo strumento, selezionare il pulsante **Selezione** sulla barra degli strumenti quindi selezionare l'elemento desiderato. Viene visualizzata la finestra delle proprietà dell'elemento ed è possibile modificare qualsiasi proprietà di tale elemento. È possibile ripetere il processo per altri elementi che possono essere personalizzati nella pagina. Tenere presente che alcune proprietà di personalizzazione potrebbero non essere disponibili in alcuni scenari. Ad esempio, non è possibile bloccare un campo obbligatorio.
- Utilizzare lo strumento **Nascondi** per nascondere un elemento nella pagina. Per utilizzare questo strumento, selezionare il pulsante **Nascondi** sulla barra degli strumenti quindi selezionare l'elemento da nascondere. Quando si usa lo strumento **Nascondi**, tutti gli elementi correntemente nascosti diventano visibili, ma vengono visualizzati in un contenitore ombreggiato. È possibile rendere visibile un elemento selezionandolo. Per vedere come apparirà la pagina quando gli elementi sono nascosti, passa a un altro strumento di personalizzazione.
- Utilizzare lo strumento **Aggiungi un campo** per aggiungere un campo nella pagina. Quando si utilizza questo strumento, è possibile aggiungere solo i campi che fanno parte della definizione della pagina. Per informazioni su come creare nuovi campi che non fanno parte della definizione della pagina corrente, vedere [Creare e utilizzare campi personalizzati](user-defined-fields.md). Dopo aver selezionato il pulsante **Aggiungi un campo** sulla barra degli strumenti, è necessario prima di tutto selezionare il gruppo o l'area in cui si desidera aggiungere un campo. Viene visualizzata una finestra di dialogo con l'elenco di campi correlati al gruppo selezionato o all'area selezionata. Nella finestra di dialogo selezionare uno o più campi da aggiungere e quindi selezionare **Inserisci**. Per rimuovere un campo aggiunto in precedenza, ripetere il processo, ma deselezionare il campo nella finestra di dialogo.
- Utilizzare lo strumento **Sposta** se si desidera spostare un elemento in un punto diverso nel gruppo corrente di elementi. Si noti che non è possibile spostare un elemento al di fuori del gruppo padre. Per utilizzare questo strumento, selezionare il pulsante **Sposta** sulla barra degli strumenti quindi selezionare l'elemento da spostare. Quando si seleziona un elemento, l'app determina le posizioni in cui l'elemento può essere spostato. Queste posizioni sono note come *aree di rilascio*. Man mano che si trascina l'elemento nel gruppo corrente, ogni zona di rilascio viene visualizzata come singola riga colorata e in grassetto accanto all'area in cui l'elemento può essere rilasciato.
- Utilizzare lo strumento **Ignora** per rimuovere un elemento dalla sequenza di tabulazione della tastiera nella pagina. Quando si seleziona il pulsante **Ignora** sulla barra degli strumenti, tutti gli elementi correntemente ignorati vengono visualizzati in un contenitore ombreggiato. È possibile aggiungere o rimuovere i campi in modo interattivo nella sequenza della scheda.
- Utilizzare lo strumento **Mostra su intestazione** quando si desidera che un campo venga visualizzato nella sezione di riepilogo della Scheda dettaglio. Quando si seleziona il pulsante **Mostra su intestazione** sulla barra degli strumenti, tutti i campi che sono stati selezionati come campi riepilogativi vengono visualizzati in un contenitore ombreggiato. È possibile aggiungere e rimuovere in modo interattivo i campi dal riepilogo della Scheda dettaglio selezionando i campi interessati.
- Utilizzare lo strumento **Blocca** per contrassegnare un elemento come modificabile o non modificabile. Quando si seleziona il pulsante **Blocca** sulla barra degli strumenti, tutti gli elementi correntemente non modificabili vengono visualizzati in un contenitore ombreggiato. È quindi possibile renderli nuovamente modificabili. Alcuni campi sono obbligatori e non possono essere resi non modificabili. Accanto a questi campi è presente un simbolo di lucchetto.
- Utilizzare il pulsante **Aggiungi una PowerApp** per incorporare un'app creata con Microsoft PowerApps nella pagina. Per informazioni dettagliate su come incorporare un'app PowerApps in una pagina, vedere [Incorporare le app PowerApps](embed-power-apps.md).
- Utilizzare lo strumento **Cancella** per reimpostare lo stato di installazione predefinito della pagina. Tutte le personalizzazioni della pagina corrente saranno cancellate. L'azione di annullamento non è disponibile. Di conseguenza, utilizzare questo strumento solo se si è certi di voler reimpostare la pagina.
- Utilizzare lo strumento **Importa** per caricare una personalizzazione da un file precedentemente creato. Quando si importano le personalizzazione per una pagina, è possibile scegliere se devono essere aggiunte o sostituire tutte le personalizzazione esistenti della pagina. L'azione di annullamento non è disponibile. Di conseguenza, una volta importate le personalizzazione, è necessario cancellare manualmente o annullare tutte le modifiche non desiderate.
- Utilizzare lo strumento **Esporta** per salvare le impostazioni per la pagina in un file. È possibile quindi condividere le personalizzazioni con altri utenti. Tali utenti devono semplicemente importare il file contenente le personalizzazioni per la pagina.
- Selezionare il pulsante **Chiudi** per chiudere la barra degli strumenti **Personalizzazione** e ripristinare la pagina allo stato interattivo precedente.

Tradizionalmente, quando viene utilizzata la barra degli strumenti **Personalizzazione**, le personalizzazioni diventano immediatamente. Tuttavia, se la funzionalità [Visualizzazioni salvate](saved-views.md) è abilitata, è necessario salvare esplicitamente le personalizzazioni in una visualizzazione selezionata.

In alcuni casi, quando si seleziona uno strumento,viene visualizzata un'icona a forma di lucchetto accanto a un elemento. Il simbolo indica che non è possibile modificare le proprietà dell'elemento correlate allo strumento selezionato, perché le modifiche a tali proprietà impediscono il corretto funzionamento della pagina.

### <a name="adding-a-tile-list-or-link-to-a-workspace"></a>Aggiunta di un riquadro, un elenco o un collegamento a un'area di lavoro

Per alcune pagine che includono gli elenchi, la funzionalità di personalizzazione **Aggiungi ad area di lavoro** è disponibile nel gruppo **Personalizza** della scheda **Opzioni** del riquadro azioni. Questa funzionalità consente di eseguire la distribuzione push delle informazioni rilevanti dall'elenco corrente in un'area di lavoro specifica. Le informazioni visualizzate nell'area di lavoro possono essere basate sull'intero elenco o una versione filtrata e ordinata dell'elenco. È inoltre possibile specificare se le informazioni appaiono nell'area di lavoro come elenco, come riquadro di riepilogo che può mostrare il numero di voci nell'elenco o come collegamento.

> [!NOTE]
> Se la funzionalità [Visualizzazioni salvate](saved-views.md) è abilitata, il contenuto da sottoporre al push in un'area di lavoro viene direttamente collegato a una visualizzazione. La query della visualizzazione viene utilizzata per recuperare i dati nell'area di lavoro e il riquadro o il collegamento corrispondente nell'area di lavoro apre la pagina in quella visualizzazione, in modo che la query e le personalizzazioni della visualizzazione vengano applicate.

[![Aggiungi ad area di lavoro](./media/personalization-addtoworkspace.png)](./media/personalization-addtoworkspace.png)

- Per aggiungere un elenco a un'area di lavoro, prima di tutto ordinare o filtrare l'elenco nella pagina in modo che mostri le informazioni come si desidera vengano visualizzate nell'area di lavoro. Se la funzionalità Visualizzazioni salvate è abilitata, non è possibile continuare fino a quando non verrà salvata una visualizzazione che abbia queste condizioni. Quindi, selezionare **Aggiungi ad area di lavoro**. Selezionare un'area di lavoro, quindi nel campo **Presentazione** selezionare **Elenco**. Dopo aver selezionato **Configura**, viene visualizzata una finestra di dialogo in cui è possibile selezionare le colonne da visualizzare nell'elenco nell'area di lavoro. È possibile inoltre specificare l'etichetta da utilizzare per l'elenco nell'area di lavoro.
- Per aggiungere un riquadro a un'area di lavoro, filtrare prima di tutto l'elenco nella pagina in modo da mostrare i dati da riepilogare o a cui si desidera accedere rapidamente. Se la funzionalità Visualizzazioni salvate è abilitata, non è possibile continuare fino a quando non verrà salvata una visualizzazione che abbia queste condizioni. Quindi, selezionare **Aggiungi ad area di lavoro**. Selezionare un'area di lavoro, quindi nel campo **Presentazione** selezionare **Riquadro**. Dopo aver selezionato **Configura**, viene visualizzata una finestra di dialogo in cui è possibile specificare l'etichetta da utilizzare per il riquadro nell'area di lavoro. È inoltre possibile specificare se il riquadro deve visualizzare un conteggio. Una volta che il riquadro è aggiunto all'area di lavoro, è possibile selezionarlo per aprire la pagina corrente dall'area di lavoro. Sarà quindi possibile visualizzare l'elenco filtrato associato al riquadro.
- Per aggiungere un collegamento a un'area di lavoro, filtrare innanzitutto l'elenco nella pagina in modo da mostrare i dati desiderati. Se la funzionalità Visualizzazioni salvate è abilitata, non è possibile continuare fino a quando non verrà salvata una visualizzazione che abbia queste condizioni. Quindi, selezionare **Aggiungi ad area di lavoro**. Selezionare un'area di lavoro, quindi nel campo **Presentazione** selezionare **Collegamento**. Dopo aver selezionato **Configura**, viene visualizzata una finestra di dialogo in cui è possibile specificare l'etichetta da utilizzare per il collegamento. È facoltativamente possibile specificare un'etichetta per una nuova sezione che contiene il collegamento.

Dopo avere aggiunto l'elenco, il riquadro o il collegamento in un'area di lavoro, è possibile aprire l'area di lavoro e riordinare gli elementi come si desidera.

### <a name="adding-a-summary-from-a-workspace-to-a-dashboard"></a>Aggiunta di un riepilogo da un'area di lavoro a un dashboard

In alcune aree di lavoro sono presenti riquadri di conteggio (ovvero riquadri contenenti numeri) e può essere utile visualizzare tali riquadri anche nel dashboard. In un'area di lavoro, fare clic con il pulsante destro del mouse su un riquadro di conteggio, selezionare **Personalizza** e nella finestra delle proprietà del riquadro selezionare **Aggiungi a dashboard**. La volta successiva che si apre e aggiorna il dashboard selezionato, il conteggio viene visualizzato sotto il riquadro di navigazione di tale area di lavoro. È possibile selezionare il conteggio in modo che passi direttamente ai dati che rappresenta.

### <a name="personalizing-your-dashboard"></a>Personalizzazione del dashboard

Il dashboard è spesso la prima pagina che si visualizza quando si apre l'app. È possibile personalizzare il dashboard in modo che mostri solo i riquadri dell'area di lavoro che si desidera vedere. È inoltre possibile riorganizzare i riquadri in modo che siano visualizzati nell'ordine in cui si preferisce visualizzarli, rinominare i riquadri di navigazione dell'area di lavoro oppure aggiungere un riquadro dell'area di lavoro nuovo.

Per personalizzare il dashboard, fare clic con il pulsante destro del mouse su un qualsiasi riquadro e quindi selezionare **Personalizza** per aprire la finestra delle proprietà del riquadro.

- Se si desidera nascondere o rinominare il riquadro selezionato, è possibile apportare la modifica direttamente nella finestra delle proprietà.
- Per riordinare i riquadri dell'area di lavoro, nella finestra delle proprietà selezionare **Personalizza modulo** per aprire la barra degli strumenti **Personalizzazione**. È quindi possibile utilizzare lo strumento **Sposta** per riordinare i riquadri nel modo desiderato.
- Per aggiungere un nuovo riquadro dell'area di lavoro, nella finestra delle proprietà selezionare **Aggiungi area di lavoro**. Il nuovo riquadro dell'area di lavoro viene creato nella parte inferiore del dashboard. È possibile rinominare questo nuovo riquadro dell'area di lavoro come si preferisce. È inoltre possibile aggiungere elenchi, riquadri e collegamenti nell'area di lavoro come descritto nella sezione [Aggiunta di elenchi, riquadri o collegamenti nelle aree di lavoro](#adding-a-tile-list-or-link-to-a-workspace) di questo argomento.

## <a name="administration-of-personalizations"></a>Amministrazione delle personalizzazioni

Dopo avere personalizzato una pagina, è possibile condividere le personalizzazioni con altri utenti esportando la pagina personalizzata. È possibile richiedere agli altri utenti di aprire la pagina personalizzata e di importare il file di personalizzazione creato. In alternativa, è possibile assegnare le personalizzazioni a un utente con privilegi di amministratore. Tale utente può quindi applicare il file di personalizzazione a più utenti contemporaneamente.

Gli utenti con privilegi di amministratore possono anche gestire le personalizzazioni per altri utenti nella pagina **Personalizzazione**.

Per i clienti che non hanno attivato la funzionalità [Visualizzazioni salvate](saved-views.md), questa pagina include quattro schede:

- **Applica** - È possibile importare o selezionare una personalizzazione per uno o più utenti. Per applicare una personalizzazione a uno o più utenti, selezionare innanzitutto un ruolo e gli utenti con quel ruolo. Selezionare quindi una personalizzazione esistente da applicare agli utenti selezionati o importare un file di personalizzazione. La personalizzazione viene convalidata e applicata a tutti gli utenti selezionati alla successiva apertura della pagina selezionata.
- **Cancella** - È possibile cancellare tutte le personalizzazioni di una pagina o un'area di lavoro per uno o più utenti. Selezionare prima di tutto una pagina o un'area di lavoro per vedere l'elenco degli utenti che l'hanno personalizzata. Selezionare quindi gli utenti per i quali occorre cancellare le personalizzazioni della pagina o dell'area di lavoro e selezionare **Cancella**. Tutte le personalizzazione che gli utenti selezionati hanno applicato alla pagina o all'area di lavoro selezionata vengono cancellate. Non è possibile annullare questa azione. Se tuttavia una personalizzazione della pagina o dell'area di lavoro viene salvata, tale personalizzazione può essere reimportata.
- **Utenti** - Selezionare un utente per visualizzare l'elenco delle pagine che l'utente ha personalizzato. È quindi possibile attivare o disattivare la capacità dell'utente selezionato di utilizzare la personalizzazione di pagine specifiche o dell'intero sistema. È inoltre possibile importare, esportare o cancellare una personalizzazione per l'utente. Inoltre, è possibile reimpostare i callout delle funzionalità per l'utente. In questo caso, se l'utente ha precedentemente ignorato una finestra popup che introduce nuove funzionalità, questa viene di nuovo visualizzata la volta successiva che l'utente rileva tali funzionalità.
- **Sistema** - È possibile disattivare temporaneamente la personalizzazione per tutti gli utenti nel sistema. In questo caso, tutte le personalizzazione vengono eliminate per tutti gli utenti e tutte le pagine vengono reimpostate allo stato predefinito. Se si attivano nuovamente le personalizzazioni in un secondo momento, queste vengono applicate nuovamente. È inoltre possibile eliminare in modo permanente tutte le personalizzazioni per tutti gli utenti nel sistema. Le personalizzazioni che sono state eliminate non possono essere recuperate. Pertanto, prima di eseguire questa attività, assicurarsi di esportare tutte le personalizzazioni che si desidera importare successivamente.

Per i clienti che hanno attivato la funzionalità [Visualizzazioni salvate](saved-views.md), la pagina **Personalizzazione** include cinque schede:

- **Visualizzazioni pubblicate** - Queste visualizzazioni sono state pubblicate nell'organizzazione. Per modificare gli utenti che sono interessati da queste visualizzazioni, è possibile modificare i ruoli di sicurezza o le persone giuridiche associate a ciascuna visualizzazione. È inoltre possibile esportare o eliminare una o più visualizzazioni pubblicate.
- **Visualizzazioni non pubblicate** - Queste visualizzazioni rappresentano le visualizzazioni modello importate nel sistema ma non ancora pubblicate. È possibile pubblicare, esportare o eliminare queste visualizzazioni.
- **Visualizzazioni personali** - Queste visualizzazioni sono state create dagli utenti nel sistema. È possibile pubblicare una visualizzazione personale nell'organizzazione o copiare una o più visualizzazioni in altri utenti. È anche possibile esportare o eliminare queste visualizzazioni, secondo le necessità.
- **Utenti** - Selezionare un utente per visualizzare l'elenco delle pagine che l'utente ha personalizzato. È quindi possibile attivare o disattivare la capacità dell'utente selezionato di utilizzare la personalizzazione di pagine specifiche o dell'intero sistema. È inoltre possibile importare, esportare o cancellare una personalizzazione per l'utente. Inoltre, è possibile reimpostare i callout delle funzionalità per l'utente. In questo caso, se l'utente ha precedentemente ignorato una finestra popup che introduce nuove funzionalità, questa viene di nuovo visualizzata la volta successiva che l'utente rileva tali funzionalità.
- **Sistema** - È possibile disattivare temporaneamente la personalizzazione per tutti gli utenti nel sistema. In questo caso, tutte le personalizzazione vengono eliminate per tutti gli utenti e tutte le pagine vengono reimpostate allo stato predefinito. Se si attivano nuovamente le personalizzazioni in un secondo momento, queste vengono applicate nuovamente. È inoltre possibile eliminare in modo permanente tutte le personalizzazioni per tutti gli utenti nel sistema. Le personalizzazioni che sono state eliminate non possono essere recuperate. Pertanto, prima di eseguire questa attività, assicurarsi di esportare tutte le personalizzazioni che si desidera importare successivamente.

Gli utenti che hanno accesso alla pagina **Personalizzazione** possono anche importare le visualizzazioni modello o personali tramite il pulsante **Importa visualizzazioni** nel riquadro azioni.

## <a name="personalizing-inventory-dimensions"></a>Personalizzazione delle dimensioni inventariali

Quando si personalizza l'impostazione delle dimensioni inventariali in una pagina, considerare le impostazioni create utilizzando l'opzione **Visualizza dimensioni**. Ad esempio, è possibile utilizzare la personalizzazione per nascondere una colonna per la dimensione inventariale del numero batch, ma alla successiva apertura della pagina la colonna sarà di nuovo visibile. Questo comportamento si verifica perché le impostazioni **Visualizzazione di dimensioni** controllano le colonne di dimensioni inventariali che vengono visualizzate. Le impostazioni **Visualizzazione dimensioni** vengono applicate a tutte le pagine e sostituiscono qualsiasi impostazione personalizzata dei campi delle dimensioni inventariali nelle singole pagine.

Di conseguenza, nell'esempio precedente, se non si desidera che la colonna relativa alla dimensione inventariale del numero batch venga visualizzata in una pagina, è necessario cancellare la dimensione come parte dell'opzione **Dimensioni di visualizzazione** della tabella per quella pagina.
