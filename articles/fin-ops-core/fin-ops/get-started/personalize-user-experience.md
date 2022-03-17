---
title: Personalizzare l'esperienza utente
description: In questo argomento viene illustrato come personalizzare l'app.
author: jasongre
ms.date: 03/03/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SysUserSetup, DefaultDashboard
audience: Application User, IT Pro
ms.reviewer: sericks
ms.custom: 62363
ms.assetid: 57b445d7-3e9e-4228-8728-f63b9dbd77a3
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4bdce3cd12358112e40a783c73795bd6f35545c8
ms.sourcegitcommit: 2e554371f5005ef26f8131ac27eb171f0bb57b4e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/04/2022
ms.locfileid: "8384645"
---
# <a name="personalize-the-user-experience"></a>Personalizzare l'esperienza utente

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]


[!INCLUDE [PEAP](../../../includes/peap-1.md)]

Questo argomento spiega come personalizzare l'app e tratta i seguenti argomenti: 

- **Opzioni a livello di sistema:** queste opzioni di personalizzazione sono realizzate in una pagina di configurazione e sono disponibili per tutti gli utenti. Alcuni esempi sono rappresentati dal tema del colore e dal fuso orario. 
- **Accesso alla personalizzazione limitato**: a questo livello di accesso, le azioni dell'utente associate all'utilizzo tipico della pagina vengono automaticamente salvate dall'app e ripristinate alla successiva visita della pagina. Ad esempio, l'app memorizza la larghezza delle colonne della griglia se le si regola e dello stato espanso o compresso delle Schede dettaglio. 
- **Accesso completo alla personalizzazione**: a questo livello di accesso, gli utenti hanno accesso a tutte le funzionalità di personalizzazione nell'app. In particolare, hanno accesso alla barra degli strumenti **Personalizzazione**. 
- **Condivisione delle personalizzazioni**: gli utenti che hanno pieno accesso alla personalizzazione possono esportare le loro personalizzazioni di pagina e condividerle con altri utenti.
- **Amministrazione delle personalizzazioni**: gli utenti con privilegi possono accedere alla pagina di gestione **Personalizzazione** per gestire tutte le personalizzazioni a livello organizzativo. 

## <a name="system-wide-options-for-the-current-user"></a>Opzioni a livello di sistema per l'utente corrente

La pagina **Opzioni utente** contiene molte impostazioni a livello di sistema per l'utente corrente. Queste opzioni sono disponibili per tutti gli utenti, anche per gli utenti che non hanno avuto accesso alla personalizzazione. Per aprire la pagina **Opzioni utente**, selezionare il pulsante **Impostazioni** nella barra di navigazione e quindi selezionare **Opzioni utente**. La pagina **Opzioni utente** dispone di quattro schede contenenti varie impostazioni utente:

- **Visuale** - Consente di selezionare un tema di colori e le dimensioni predefinite degli elementi nelle pagine.
- **Preferenze** - Consente di selezionare valori predefiniti che vengono utilizzati ogni volta che si apre il sistema. Questi valori includono la società predefinita, la pagina iniziale e la modalità di visualizzazione predefinita/modifica. La modalità di visualizzazione/modifica determina se una pagina viene bloccata per la visualizzazione o aperta per la modifica ogni volta che la si apre. Questa scheda include anche opzioni per la lingua, il fuso orario, il formato di data e ora e il formato dei numeri. Infine, questa scheda include molte preferenze varie che cambiano da versione a versione.
- **Account**: consente di visualizzare o modificare il nome utente e altre opzioni correlate all'account.
- **Flusso di lavoro** - Consente di selezionare opzioni correlate ai flussi di lavoro.

Oltre a modificare le impostazioni utente, è anche possibile visualizzare ed eliminare i dati utilizzo e le personalizzazioni dalla pagina **Opzioni utente**. Per visualizzare i dati di utilizzo, selezionare **Dati di utilizzo** nel riquadro azioni. Nella scheda **Personalizzazione** è possibile visualizzare e gestire le modifiche personali effettuate nelle pagine del sistema. In questa scheda, è inoltre possibile reimpostare i callout della funzionalità (ovvero le finestre popup che introducono nuove funzionalità di sistema). Si viene quindi di nuovo avvisati sulle funzionalità precedentemente rilavate.

> [!NOTE]
> Se la funzionalità [Visualizzazioni salvate](saved-views.md) è attivata, è possibile visualizzare e gestire le personalizzazioni selezionando **Personalizzazione** nel riquadro azioni della pagina **Opzioni utente**.

## <a name="restricted-personalization-access-formerly-implicit-personalizations"></a>Accesso limitato alla personalizzazione (personalizzazioni precedentemente implicite)

A livello di **accesso alla personalizzazione limitato**, le azioni dell'utente associate all'utilizzo tipico della pagina vengono automaticamente salvate dall'app e ripristinate alla successiva visita della pagina. Non è richiesta alcuna azione di salvataggio esplicita. 

Ecco un elenco delle azioni che rientrano nel normale utilizzo della pagina e sono coperte da un accesso limitato alla personalizzazione: 

- **Larghezza colonne griglia** - È possibile regolare la larghezza di una colonna in una griglia selezionando la barra di ridimensionamento a sinistra o a destra dell'intestazione di colonna e facendola scorrere verso sinistra o verso destra fino a raggiungere la larghezza desiderata. L'app memorizza la larghezza che si imposta per una colonna. Quindi, alla successiva apertura della pagina, la colonna verrà ridimensionata a quella larghezza.
- **Totali colonne e piè di pagina griglia**: *(disponibile solo con il nuovo controllo griglia attivato)* È possibile decidere se visualizzare o meno un totale nella parte inferiore di qualsiasi colonna numerica in una griglia e se il piè di pagina della griglia dovrebbe essere visibile. L'app memorizza queste preferenze e le applica alla successiva apertura della pagina. Per ulteriori informazioni, vedere [Funzionalità di griglia](grid-capabilities.md). 
- **Schede dettaglio** - Alcune pagine hanno sezioni espandibili denominate *Schede dettaglio*. L'app memorizza le informazioni sulle Schede dettaglio che sono state espanse o compresse. La volta successiva che si apre la pagina, le stesse Schede dettaglio saranno compresse o espanse, a seconda dell'ultima interazione con la pagina. In alcuni casi, comprimere una scheda dettaglio può migliorare le prestazioni del sistema poiché l'app non dovrà recuperare le informazioni relative alle Schede dettaglio finché non vengono espanse. Come descritto più avanti in questo argomento, è possibile modificare anche l'ordine delle Schede dettaglio in una pagina.
- **Riquadri dettagli** – Alcune pagine includono un riquadro **Informazioni correlate** che mostra informazioni di sola lettura correlate all'argomento corrente della pagina. Ciascuna sezione del riquadro **Informazioni correlate** è chiamata *Riquadro dettagli*. È possibile espandere o comprimere il riquadro **Informazioni correlate** ed è possibile espandere o comprimere i singoli riquadri dettagli. L'app memorizza queste preferenze. La volta successiva che si apre la pagina, il riquadro **Informazioni correlate** e i singoli riquadri dettagli saranno espansi o compressi, in base all'ultima interazione con la pagina. In alcuni casi, comprimere un riquadro dettaglio o il riquadro **Informazioni correlate** può migliorare le prestazioni del sistema poiché l'app non dovrà recuperare le informazioni relative ai riquadri dettaglio finché non vengono espansi.
- **Riquadri azioni** - Un *riquadro azioni* appare accanto alla parte superiore della maggior parte delle pagine. Il riquadro azioni contiene pulsanti per molte delle azioni che è possibile eseguire nella pagina corrente. Questi pulsanti sono spesso organizzati in schede. È possibile *aggiungere* l'intero riquadro azioni aperto oppure fare in modo che venga compresso per impostazione predefinita. La volta successiva che si apre la pagina, il riquadro azioni saranno aperto o compresso, a seconda dell'ultima interazione con la pagina. Se è stato aggiunto il riquadro azioni aperto, verrà visualizzata l'ultima scheda utilizzata.
- **QuickFilter** - Un *QuickFilter* viene visualizzato sopra molte griglie. Il QuickFilter consente di filtrare la griglia, in base alla singola colonna che si seleziona. L'app memorizza la colonna su cui è stato basato il filtro. Quindi, la volta successiva che si apre la pagina la griglia utilizzerà la stessa colonna per filtrare. Tuttavia, è possibile comunque filtrare la griglia selezionando una colonna diversa.
- **Filtri di intestazione di colonna** - Quando si filtra una griglia utilizzando i *Filtri di intestazione di colonna*, è possibile modificare l'operatore di filtro per trovare i dati desiderati. Ad esempio, è possibile modificare l'operatore **inizia con** in **è esattamente**. Ogni volta che si utilizza un filtro di intestazione di colonna e si modifica l'operatore di filtro, l'app memorizza la modifica. La volta successiva che si filtra tale colonna, l'operatore di filtro verrà ripristinato.
- **Pannello di navigazione** - È possibile aprire il *Pannello di navigazione* selezionando il pulsante **Espandere il pannello di navigazione** in alto a sinistra di qualsiasi pagina. Questo pulsante viene talvolta indicato come pulsante _**Menu**_, *hamburger*, *menu hamburger* o *pulsante hamburger*. È possibile aggiungere il pannello di navigazione aperto oppure compresso per impostazione predefinita. Dopo che si imposta il pannello di navigazione in modo che resti aperto, l'app lo manterrà aperto fino a quando non lo si comprime.

## <a name="full-personalization-access-formerly-explicit-personalizations"></a>Accesso completo alla personalizzazione (personalizzazioni precedentemente esplicite)

A livello di **accesso completo alla personalizzazione**, gli utenti hanno accesso a tutte le funzionalità di personalizzazione fornite dall'app. Poiché persone e aziende diverse hanno esigenze diverse quando interagiscono con l'app, soprattutto in termini di campi utilizzati, la personalizzazione fornisce strumenti che consentono agli utenti e alle organizzazioni di personalizzare la modalità di utilizzo e interazione con le informazioni all'interno dell'app. Queste funzionalità sono fondamentali per fornire esperienze semplificate e ottimizzate nell'app personalizzate per te e la tua organizzazione. 

Se la funzionalità [Visualizzazioni salvate](saved-views.md) è attivata, è necessario un salvataggio esplicito per confermare queste modifiche all'esperienza utente per una visualizzazione specifica. Quando la funzionalità **Visualizzazioni salvate** è disattivata, queste modifiche vengono salvate automaticamente.

Le seguenti sezioni descrivono l'estensione delle funzionalità di personalizzazione disponibili per gli utenti a livello di **accesso completo alla personalizzazione**. Di seguito ne sono riportate alcune:

- Opzioni di menu di scelta rapida
- Barra degli strumenti **Personalizzazione**
- Aggiunta di riquadri, elenchi e collegamenti alle aree di lavoro
- Aggiunta di un riepilogo da un'area di lavoro a un dashboard
- Personalizzazione della dashboard

### <a name="shortcut-menu-options"></a>Opzioni di menu di scelta rapida

I menu di scelta rapida forniscono un modo per modificare l'interfaccia di una pagina in modo che soddisfi meglio i requisiti dell'organizzazione. Un menu di scelta rapida è noto anche con il nome di *menu del pulsante destro del mouse* o un *menu contestuale*.

Alcune delle modifiche più tipiche e più importanti che possono essere apportate a una pagina sono disponibili direttamente come opzioni in un menu di scelta rapida. Ad esempio, per aggiungere o nascondere le colonne di una griglia, è sufficiente fare clic con il pulsante destro del mouse sull'intestazione di una colonna e selezionare **Inserisci colonne** o **Nascondi questa colonna**.

Inoltre, i tipi più fondamentali di personalizzazione sono disponibili facendo clic con il pulsante destro del mouse su un elemento e quindi selezionando **Personalizza**. Tenere presente che non tutti gli elementi nella pagina possono essere personalizzati. Quando si utilizza questo metodo di personalizzazione, viene visualizzata la *finestra delle proprietà* dell'elemento.

![Personalizzazione delle proprietà di un elemento.](./media/cli-element-property-window.png)

È possibile utilizzare la finestra delle proprietà per personalizzare un elemento nei seguenti modi:

- Modificare l'etichetta dell'elemento.
- Nascondere l'elemento in modo che non venga mostrato nella pagina. I dati del campo non vengono eliminati o modificati. Le informazioni semplicemente non vengono più visualizzate nella pagina.
- Includere le informazioni nella sezione di riepilogo della Scheda dettaglio (se l'elemento è in una Scheda dettaglio).
- Ignorare il campo in modo che non diventi mai in stato attivo mentre si scorre la pagina.
- Impedire la modifica dei dati nel campo (per qualsiasi record).
- Designare un campo come obbligatorio per l'inserimento dei dati. Se non è stato inserito alcun valore in questo campo, verrà visualizzato con un bordo rosso e un asterisco per indicare questo stato. Questa opzione è disponibile solo a partire dalla versione 10.0.11 quando le funzionalità [Visualizzazioni salvate](saved-views.md) e **Designa i campi come richiesto utilizzando la personalizzazione** sono attivate.

La finestra delle proprietà potrebbe includere altre funzionalità di personalizzazione, a seconda dell'elemento. Ad esempio, la finestra delle proprietà di un riquadro potrebbe consentire di promuovere il riquadro in una dashboard e le finestre delle proprietà per gli elementi nella dashboard predefinita potrebbe consentire di creare una nuova area di lavoro personalizzata.

### <a name="personalization-toolbar"></a>Barra degli strumenti di personalizzazione

Se si desidera apportare più modifiche a una pagina o apportare modifiche che non sono disponibili attraverso altri meccanismi (ad esempio se si desidera riordinare gli elementi), è possibile utilizzare la barra degli strumenti **Personalizzazione**. Per aprire la barra degli strumenti **Personalizzazione**, effettuare una delle seguenti operazioni:

- Selezionare **CTRL+MAIUSC+ P** da qualsiasi elemento della pagina.
- Selezionare **Personalizza questa pagina** nella finestra di proprietà dell'elemento.
- Selezionare **Personalizza questa pagina** nel gruppo **Personalizza** della scheda **Opzioni** del riquadro azioni di qualsiasi pagina.
- Selezionare il pulsante **Impostazioni** (il simbolo di ingranaggio) sulla barra di navigazione, quindi **Personalizza**.

[![Barra degli strumenti di personalizzazione.](./media/restyledPersonalizationToolbar.png)](./media/restyledPersonalizationToolbar.png)

#### <a name="navigating-the-page"></a>Esplorazione della pagina

Quando viene aperta la barra degli strumenti **Personalizzazione**, la pagina sottostante è di sola lettura (in altre parole, non è possibile modificare i dati), ma è ancora interattiva. In particolare, è possibile espandere o comprimere il riquadro **Informazioni correlate**, cambiare schede ed espandere o comprimere le sezioni, esattamente come quelle azioni vengono eseguite nella pagina. Per applicare una personalizzazione a una sezione comprimibile o a una scheda (ad esempio per nascondere una Scheda dettaglio), è sufficiente selezionare il pulsante che appare accanto alla sezione o alla scheda quando diventa attivo da tastiera o quando ci si sofferma con il puntatore del mouse.

#### <a name="personalization-tools"></a>Barre degli strumenti di personalizzazione

Nella barra degli strumenti **Personalizzazione** sono disponibili gli strumenti seguenti:

- Utilizzare lo strumento **Selezione** per selezionare e modificare le proprietà di un elemento. Per utilizzare questo strumento, selezionare il pulsante **Selezione** sulla barra degli strumenti quindi selezionare l'elemento desiderato. Viene visualizzata la finestra delle proprietà dell'elemento in cui è possibile modificare qualsiasi proprietà di tale elemento. È possibile ripetere il processo per altri elementi che possono essere personalizzati nella pagina. Tenere presente che alcune proprietà di personalizzazione potrebbero non essere disponibili in alcuni scenari. Ad esempio, non è possibile bloccare un campo obbligatorio.
- Utilizzare lo strumento **Nascondi** per nascondere un elemento nella pagina. Per utilizzare questo strumento, selezionare il pulsante **Nascondi** sulla barra degli strumenti quindi selezionare l'elemento da nascondere. Quando si usa lo strumento **Nascondi**, tutti gli elementi correntemente nascosti diventano visibili, ma vengono visualizzati in un contenitore ombreggiato. È possibile rendere visibile un elemento selezionandolo. Per vedere come apparirà la pagina quando gli elementi sono nascosti, passare a un altro strumento di personalizzazione o chiudere la barra degli strumenti della personalizzazione.
- Utilizzare lo strumento **Aggiungi campi** per aggiungere campi nella pagina. Quando si utilizza questo strumento, è possibile aggiungere solo i campi che fanno parte della definizione della pagina. Per informazioni su come creare nuovi campi che non fanno parte della definizione della pagina corrente, vedere [Creare e utilizzare campi personalizzati](user-defined-fields.md). Dopo aver selezionato il pulsante **Aggiungi campi** sulla barra degli strumenti, è necessario prima di tutto selezionare la griglia o sezione in cui si desidera aggiungere un campo. Viene visualizzata una finestra di dialogo con l'elenco di campi correlati alla griglia o alla sezione selezionata. Nella finestra di dialogo, selezionare uno o più campi da aggiungere dall'elenco **Campi consigliati** o **Tutti i campi**. Dopo aver scelto i campi desiderati, selezionare **Aggiorna**. Per rimuovere un campo aggiunto in precedenza, ripetere il processo, ma deselezionare il campo nella finestra di dialogo.

    L'elenco **Campi consigliati** mostra i campi che sono stati precedentemente aggiunti da altri utenti dell'organizzazione. Questo elenco di campi viene aggiornato in base alla frequenza di ricorrenza del **Processo batch raccomandazione**. È disponibile un'esperienza simile quando si aggiungono nuovi campi di filtro utilizzando il riquadro Filtro in una pagina.

- Utilizzare lo strumento **Sposta** se si desidera spostare un elemento in un punto diverso nel gruppo corrente di elementi. Si noti che non è possibile spostare un elemento al di fuori del gruppo padre. Per utilizzare questo strumento, selezionare il pulsante **Sposta** sulla barra degli strumenti quindi selezionare l'elemento da spostare. Quando si seleziona un elemento, l'app determina le posizioni in cui l'elemento può essere spostato. Queste posizioni sono note come *aree di rilascio*. Man mano che si trascina l'elemento nel gruppo corrente, ogni zona di rilascio viene visualizzata come singola riga colorata e in grassetto accanto all'area in cui l'elemento può essere rilasciato.
- Utilizzare lo strumento **Ignora** per rimuovere un elemento dalla sequenza di tabulazione della tastiera nella pagina. Quando si seleziona il pulsante **Ignora** sulla barra degli strumenti, tutti gli elementi correntemente ignorati vengono visualizzati in un contenitore ombreggiato. È possibile aggiungere o rimuovere i campi in modo interattivo nella sequenza della scheda.
- Utilizzare lo strumento **Mostra su intestazione** quando si desidera che un campo venga visualizzato nella sezione di riepilogo della Scheda dettaglio. Quando si seleziona il pulsante **Mostra su intestazione** sulla barra degli strumenti, tutti i campi che sono stati selezionati come campi riepilogativi vengono visualizzati in un contenitore ombreggiato. È possibile aggiungere e rimuovere in modo interattivo i campi dal riepilogo della Scheda dettaglio selezionando i campi interessati.
- Utilizzare lo strumento **Richiedi** per designare un elemento come richiesto per l'immissione dei dati. Quando si seleziona il pulsante **Richiedi** sulla barra degli strumenti, tutti gli elementi che sono stati personalizzati per essere richiesti sono mostrati in un contenitore ombreggiato. È quindi possibile renderli nuovamente non necessari. Questa opzione è disponibile nella versione 10.0.12 e successive quando la funzionalità **Designa i campi come richiesto utilizzando la personalizzazione** è attivata.
- Utilizzare lo strumento **Blocca** per contrassegnare un elemento come modificabile o non modificabile. Quando si seleziona il pulsante **Blocca** sulla barra degli strumenti, tutti gli elementi correntemente non modificabili vengono visualizzati in un contenitore ombreggiato. È quindi possibile renderli nuovamente modificabili. Alcuni campi sono obbligatori e non possono essere resi non modificabili. Accanto a questi campi è presente un simbolo di lucchetto.
- Utilizzare lo strumento **Aggiungi un'app da Power Apps** per incorporare un'app creata con Microsoft Power Apps nella pagina. Per informazioni dettagliate su come incorporare un'app da Power Apps in una pagina, vedere [Incorporare le app da Power Apps](embed-power-apps.md). Questa opzione è disponibile solo quando la funzionalità [Visualizzazioni salvate](saved-views.md) è disattivata.
- Utilizzare il pulsante **Aggiungi un'app** per incorporare un'app creata in Microsoft Power Apps o da una terza parte nella pagina. Questa opzione è disponibile solo quando la funzionalità [Visualizzazioni salvate](saved-views.md) è attivata. 
- Utilizzare lo strumento **Cancella** per reimpostare lo stato di installazione predefinito della pagina. Tutte le personalizzazioni della pagina corrente saranno cancellate. Non è possibile annullare questa azione. Di conseguenza, utilizzare questo strumento solo se si è certi di voler reimpostare la pagina. Quando la funzionalità **Visualizzazioni salvate** è attivata, questo strumento cancella le personalizzazioni per la visualizzazione corrente.
- Utilizzare lo strumento **Importa** per caricare una personalizzazione da un file precedentemente creato. 

    - Quando la funzionalità **Visualizzazioni salvate** è disattivata, puoi scegliere se aggiungere o sostituire le tue personalizzazioni esistenti con le personalizzazioni che vengono importate per la pagina. Non è possibile annullare questa azione. Di conseguenza, una volta importate le personalizzazione, è necessario cancellare manualmente o annullare tutte le modifiche non desiderate.
    - Quando la funzionalità **Visualizzazioni salvate** è attivata, le personalizzazioni importate diventeranno una visualizzazione sulla pagina. Se la visualizzazione esiste già, avrai la possibilità di ignorare l'importazione, sostituire la visualizzazione corrente con lo stesso nome o rinominare la visualizzazione importata.

- Utilizzare lo strumento **Esporta** per salvare le impostazioni per la pagina in un file. È possibile quindi condividere le personalizzazioni con altri utenti. Tali utenti devono semplicemente importare il file contenente le personalizzazioni per la pagina. Quando la funzionalità **Visualizzazioni salvate** è attivata, questo strumento salva la visualizzazione corrente in un file per la condivisione.
- Selezionare il pulsante **Chiudi** per chiudere la barra degli strumenti **Personalizzazione** e ripristinare la pagina allo stato interattivo precedente.

Tradizionalmente, quando viene utilizzata la barra degli strumenti **Personalizzazione**, le personalizzazioni diventano immediatamente. Tuttavia, se la funzionalità [Visualizzazioni salvate](saved-views.md) è abilitata, è necessario salvare esplicitamente le personalizzazioni in una visualizzazione selezionata.

In alcuni casi, quando si seleziona uno strumento,viene visualizzata un'icona a forma di lucchetto accanto a un elemento. Il simbolo indica che non è possibile modificare le proprietà dell'elemento correlate allo strumento selezionato, perché le modifiche a tali proprietà impediscono il corretto funzionamento della pagina.

### <a name="adding-tiles-lists-and-links-to-a-workspace"></a>Aggiunta di riquadri, elenchi e collegamenti a un'area di lavoro

Per alcune pagine che includono gli elenchi, la funzionalità di personalizzazione **Aggiungi ad area di lavoro** è disponibile nel gruppo **Personalizza** della scheda **Opzioni** del riquadro azioni. Questa funzionalità consente di eseguire la distribuzione push delle informazioni rilevanti dall'elenco corrente in un'area di lavoro specifica. Le informazioni visualizzate nell'area di lavoro possono essere basate sull'intero elenco o una versione filtrata e ordinata dell'elenco. È inoltre possibile specificare se le informazioni appaiono nell'area di lavoro come elenco, come riquadro di riepilogo che può mostrare il numero di voci nell'elenco o come collegamento.

> [!NOTE]
> Se la funzionalità [Visualizzazioni salvate](saved-views.md) è abilitata, il contenuto da sottoporre al push in un'area di lavoro viene direttamente collegato a una visualizzazione. La query della visualizzazione viene utilizzata per recuperare i dati nell'area di lavoro e il riquadro o il collegamento corrispondente nell'area di lavoro apre la pagina in quella visualizzazione, in modo che la query e le personalizzazioni della visualizzazione vengano applicate. Se la visualizzazione viene aggiornata, gli elementi dell'area di lavoro corrispondenti verranno adattati alla nuova definizione della visualizzazione.

[![Aggiungi ad area di lavoro.](./media/personalization-addtoworkspace.png)](./media/personalization-addtoworkspace.png)

- Per aggiungere un elenco a un'area di lavoro, prima di tutto ordinare o filtrare l'elenco nella pagina in modo che mostri le informazioni come si desidera vengano visualizzate nell'area di lavoro. Se la funzionalità **Visualizzazioni salvate** è abilitata, non è possibile continuare fino a quando non verrà salvata una visualizzazione che abbia queste condizioni. Quindi, selezionare **Aggiungi ad area di lavoro**. Selezionare un'area di lavoro, quindi nel campo **Presentazione** selezionare **Elenco**. Dopo aver selezionato **Configura**, viene visualizzata una finestra di dialogo in cui è possibile selezionare le colonne da visualizzare nell'elenco nell'area di lavoro. È possibile inoltre specificare l'etichetta da utilizzare per l'elenco nell'area di lavoro.
- Per aggiungere un riquadro a un'area di lavoro, filtrare prima di tutto l'elenco nella pagina in modo da mostrare i dati da riepilogare o a cui si desidera accedere rapidamente. Se la funzionalità **Visualizzazioni salvate** è abilitata, non è possibile continuare fino a quando non verrà salvata una visualizzazione che abbia queste condizioni. Quindi, selezionare **Aggiungi ad area di lavoro**. Selezionare un'area di lavoro, quindi nel campo **Presentazione** selezionare **Riquadro**. Dopo aver selezionato **Configura**, viene visualizzata una finestra di dialogo in cui è possibile specificare l'etichetta da utilizzare per il riquadro nell'area di lavoro. È inoltre possibile specificare se il riquadro deve visualizzare un conteggio. Una volta che il riquadro è aggiunto all'area di lavoro, è possibile selezionarlo per aprire la pagina corrente dall'area di lavoro. Sarà quindi possibile visualizzare l'elenco filtrato associato al riquadro.
    - A partire dalla versione 10.0.26, se la funzionalità **Consenti agli utenti di selezionare e modificare le dimensioni dei riquadri** è abilitata, è possibile selezionarne una tra le quattro **Dimensioni riquadri** per il tuo nuovo riquadro nella finestra di dialogo **Configura riquadro**. Questa funzionalità consente anche di regolare la dimensione del riquadro dopo che è stata creato direttamente dall'area di lavoro.   
- Per aggiungere un collegamento a un'area di lavoro, filtrare innanzitutto l'elenco nella pagina in modo da mostrare i dati desiderati. Se la funzionalità **Visualizzazioni salvate** è abilitata, non è possibile continuare fino a quando non verrà salvata una visualizzazione che abbia queste condizioni. Quindi, selezionare **Aggiungi ad area di lavoro**. Selezionare un'area di lavoro, quindi nel campo **Presentazione** selezionare **Collegamento**. Dopo aver selezionato **Configura**, viene visualizzata una finestra di dialogo in cui è possibile specificare l'etichetta da utilizzare per il collegamento. È facoltativamente possibile specificare un'etichetta per la sezione in cui verrà posizionato il collegamento. Se tale sezione non esiste, verrà creata una nuova sezione.

> [!NOTE]
> A partire dalla versione 10.0.25, quando si configura l'elenco, il riquadro o il collegamento, potrebbe essere necessario selezionare anche le viste dell'area di lavoro a cui si desidera aggiungere l'elemento se la funzionalità **(Anteprima) Supporto visualizzazioni salvate per aree di lavoro** è abilitata. Le visualizzazioni dell'area di lavoro disponibili appariranno nella sezione **Opzioni area di lavoro** di ogni finestra di dialogo **Configura**. 

Dopo avere aggiunto l'elenco, il riquadro o il collegamento in un'area di lavoro, è possibile aprire l'area di lavoro e riordinare gli elementi come si desidera.

### <a name="adding-a-summary-from-a-workspace-to-a-dashboard"></a>Aggiunta di un riepilogo da un'area di lavoro a un dashboard

In alcune aree di lavoro sono presenti riquadri di conteggio (ovvero riquadri contenenti numeri) e può essere utile visualizzare tali riquadri anche nel dashboard. In un'area di lavoro, fare clic con il pulsante destro del mouse su un riquadro di conteggio, selezionare **Personalizza** e nella finestra delle proprietà del riquadro selezionare **Aggiungi a dashboard**. La volta successiva che si apre e si aggiorna la dashboard selezionata, il conteggio viene visualizzato sotto il riquadro di navigazione di tale area di lavoro. È possibile selezionare il conteggio in modo che passi direttamente ai dati che rappresenta.

### <a name="changing-the-size-of-a-tile"></a>Modifica delle dimensioni di un riquadro
A partire dalla versione 10.0.26, la funzionalità **Consenti agli utenti di selezionare e modificare le dimensioni dei riquadri** consente agli utenti di modificare le dimensioni di qualsiasi riquadro non KPI tramite la personalizzazione. In un'area di lavoro, fare clic con il pulsante destro del mouse su un riquadro e quindi selezionare **Personalizza**. Nella finestra delle proprietà del riquadro, seleziona la dimensione desiderata dalle opzioni **Dimensione riquadro**. La dimensione del riquadro viene regolata immediatamente. Se è abilitata la funzionalità **(Anteprima) Supporto visualizzazioni salvate per aree di lavoro**, è possibile salvare questa personalizzazione in una visualizzazione dell'area di lavoro.  

### <a name="personalizing-your-dashboard"></a>Personalizzazione del dashboard

Il dashboard è spesso la prima pagina che si visualizza quando si apre l'app. Può essere personalizzato come qualsiasi altra pagina del sistema, utilizzando gli stessi meccanismi descritti in precedenza in questo argomento. 

> [!WARNING]
> Attualmente, quando nascondi il contenuto nella dashboard, è importante scegliere come target direttamente un riquadro, non lo spazio circostante. Se si nasconde il gruppo attorno a un riquadro, potrebbero verificarsi risultati imprevisti se vengono aggiunti più riquadri in un secondo momento o se il sistema passa a un'altra lingua.

Una funzionalità di personalizzazione unica disponibile nella dashboard è la possibilità di aggiungere riquadri. 

- Se la funzionalità **App a tutta pagina** è disattivata, aggiungi un nuovo riquadro facendo clic con il pulsante destro del mouse su un elemento nella dashboard e selezionando **Aggiungi un'area di lavoro**. Il nuovo riquadro dell'area di lavoro viene creato nella parte inferiore del dashboard. È possibile rinominare questo nuovo riquadro dell'area di lavoro come si preferisce. È inoltre possibile aggiungere elenchi, riquadri e collegamenti nell'area di lavoro come descritto nella sezione [Aggiunta di riquadri, elenchi e collegamenti a un'area di lavoro](personalize-user-experience.md#adding-tiles-lists-and-links-to-a-workspace) di questo argomento.
- Se la funzionalità **App a tutta pagina** è attivata, aggiungi un nuovo riquadro facendo clic con il pulsante destro del mouse su un elemento nella dashboard e selezionando **Aggiungi un'app**. Nella finestra di dialogo, selezionare se si desidera aggiungere un riquadro per una nuova area di lavoro o un riquadro con contenuto da Power Apps o un sito Web. Quindi seguire i passaggi per configurare l'opzione selezionata. Un nuovo riquadro viene creato nella parte inferiore del dashboard. Per ulteriori informazioni su come aggiungere, modificare, eliminare e condividere queste applicazioni incorporate, vedi [Incorporare le applicazioni canvas da Power Apps](embed-power-apps.md) e [Incorporare le applicazioni di terze parti](embed-website.md).

## <a name="sharing-personalizations"></a>Condividere le personalizzazioni

Dopo avere personalizzato una pagina, ci sono alcuni metodi utilizzabili per condividere le personalizzazioni con altri utenti. Nell'elenco seguente, i metodi sono disposti in ordine dal più consigliato al meno consigliato.

1. Pubblica le visualizzazioni per gli utenti.
2. Copiare visualizzazioni o personalizzazioni per gli utenti.
3. Esporta e importa visualizzazioni o personalizzazioni.

### <a name="publish-views-to-users"></a>Pubblicare le visualizzazioni per gli utenti

Se la funzionalità [Visualizzazioni salvate](saved-views.md) è attivata e, se la pagina supporta le visualizzazioni, il modo migliore per condividere le personalizzazioni con altri utenti è pubblicare la visualizzazione per gli utenti che hanno uno o più ruoli di sicurezza. Per ulteriori informazioni, vedi [Pubblicazione di visualizzazioni](saved-views.md#publishing-views).

### <a name="copy-views-or-personalizations-to-users"></a>Copiare visualizzazioni o personalizzazioni per gli utenti

Se la funzionalitò [Visualizzazioni salvate](saved-views.md) è disattivata o, se la pagina non supporta le visualizzazioni, il modo consigliato per condividere le personalizzazioni è copiarle tra gli utenti. Questo metodo è disponibile solo per utenti privilegiati (ad esempio, amministratori di sistema). Tuttavia, gli amministratori possono cercare la personalizzazione di un utente specifico nel sistema (inclusa la visualizzazione personale dell'utente se le visualizzazioni salvate sono abilitate) e copiare la configurazione per altri utenti.

Se le visualizzazioni salvate sono abilitate, seguire questi passaggi per copiare le personalizzazioni.

1. Vai a **Amministrazione sistema \> Impostazioni \> Personalizzazione**.
2. Segui questi passaggi per copiare le visualizzazioni personali:

    1. Selezionare **Visualizzazioni personali**.
    2. Selezionare le visualizzazioni desiderate nell'elenco.
    3. Selezionare **Copia agli utenti**.
    4. Seleziona gli utenti a cui distribuire le visualizzazioni.

    Segui questi passaggi per copiare le personalizzazioni nelle pagine che non supportano le visualizzazioni:

    1. Selezionare **Impostazioni utente**.
    2. Seleziona l'utente che dispone della personalizzazione che desideri distribuire.
    3. Selezionare **Gestisci tutte le personalizzazioni**.
    4. Selezionare le personalizzazioni desiderate nell'elenco.
    5. Selezionare **Copia agli utenti**.
    6. Seleziona gli utenti a cui distribuire le personalizzazioni.

Se le visualizzazioni salvate non sono abilitate, seguire questi passaggi per copiare una personalizzazione.

1. Vai a **Amministrazione sistema \> Impostazioni \> Personalizzazione**.
2. Selezionare **Applica**.
3. Seleziona gli utenti a cui distribuire la personalizzazione.
4. Selezionare **Seleziona personalizzazione esistente**.
5. Trova e seleziona la (singola) personalizzazione che ti interessa.
6. Selezionare **OK**.

### <a name="export-and-import-views-or-personalizations"></a>Esportare e importare visualizzazioni o personalizzazioni

Un altro modo per condividere le personalizzazioni è tramite esportazione e importazione. I singoli utenti o un amministratore che agisce per loro conto possono utilizzare questo metodo per esportare le loro personalizzazioni o visualizzazioni e quindi fornire il file esportato ad altri utenti per l'importazione. In alternativa, gli utenti possono fornire le proprie personalizzazioni esportate a un utente che dispone dei privilegi di amministratore e tale utente può quindi utilizzare la pagina di amministrazione **Personalizzazione** per applicare il file di personalizzazione a più utenti contemporaneamente.

> [!IMPORTANT]
> Poiché le personalizzazioni persistono tra gli aggiornamenti, la reimportazione di tutte le personalizzazioni dopo un aggiornamento del servizio o in qualsiasi altro momento non è necessaria e altamente sconsigliata.

#### <a name="export"></a>Esporta

In generale, puoi esportare una delle tue visualizzazioni o personalizzazioni aprendo la pagina appropriata, aprendo la barra degli strumenti **Personalizzazione**, quindi selezionando **Esporta**. Per ulteriori informazioni sulla barra degli strumenti, vedere la sezione [Barra degli strumenti di personalizzazione](#personalization-toolbar) precedente in questo argomento. In alternativa, se le [visualizzazioni salvate](saved-views.md) sono abilitate, puoi andare a **Impostazioni \> Opzioni utente \> Personalizzazione** per visualizzare un elenco di tutte le tue personalizzazioni nel sistema. Da lì è possibile selezionare le visualizzazioni o le personalizzazioni da esportare, quindi selezionare **Esporta**.

Inoltre, gli amministratori possono esportare le personalizzazioni di altri utenti seguendo questi passaggi.

1. Vai a **Amministrazione sistema \> Impostazioni \> Personalizzazione**.
2. Nella scheda **Utenti** selezionare l'utente desiderato.
3. Trova e seleziona la visualizzazione o personalizzazione che ti interessa.
4. Selezionare **Esporta**.

#### <a name="import"></a>Importazione

Per importare una visualizzazione o una personalizzazione, è sufficiente aprire la barra degli strumenti **Personalizzazione** e selezionare **Importa**. Inoltre, gli amministratori possono importare un file e darlo immediatamente a uno o più utenti.

Se le visualizzazioni salvate sono abilitate, segui questi passaggi.

1. Vai a **Amministrazione sistema \> Impostazioni \> Personalizzazione**.
2. Nel riquadro azioni, selezionare **Importa visualizzazioni \> Visualizzazioni utente**.
3. Selezionare la modalità di importazione:

    - **Seleziona utenti specifici** - Fornire la visualizzazione o la personalizzazione agli utenti selezionati.
    - **Importa così com'è** - Importa la visualizzazione o la personalizzazione allo stesso utente che l'ha esportata.

4. Selezionare **Sfoglia** e quindi individuare e selezionare la personalizzazione da importare.
5. Selezionare **Avanti**.
6. Se hai selezionato **Seleziona utenti specifici** al passaggio 3, selezionare gli utenti per cui importare la personalizzazione.
7. Selezionare **Importa**.
8. Risolvi i conflitti come richiesto.

Se le visualizzazioni salvate non sono abilitate, segui questi passaggi.

1. Vai a **Amministrazione sistema \> Impostazioni \> Personalizzazione**.
2. Selezionare **Applica**.
3. Seleziona gli utenti a cui distribuire la personalizzazione.
4. Selezionare **Importa personalizzazioni da file**.
5. Selezionare **Sfoglia** e quindi individuare e selezionare la personalizzazione da importare.
6. Selezionare **OK**.

## <a name="administration-of-personalizations"></a>Amministrazione delle personalizzazioni

La pagina **Personalizzazione** è l'hub centrale per la gestione delle personalizzazioni a livello organizzativo. Il contenuto e le funzionalità in questa pagina dipendono dall'abilitazione o meno della funzionalità **Visualizzazioni salvate**.

Per i clienti che hanno attivato la funzionalità **Visualizzazioni salvate** vedere la sezione "Gestione delle visualizzazioni a livello globale" nell'argomento [Visualizzazioni salvate](saved-views.md).

Per i clienti che non hanno ancora attivato la funzionalità [Visualizzazioni salvate](saved-views.md), questa pagina include quattro schede:

- **Applica** - È possibile importare o selezionare una personalizzazione per uno o più utenti. Per applicare una personalizzazione a uno o più utenti, selezionare innanzitutto un ruolo e gli utenti con quel ruolo. Selezionare quindi una personalizzazione esistente da applicare agli utenti selezionati o importare un file di personalizzazione. La personalizzazione viene convalidata e applicata a tutti gli utenti selezionati alla successiva apertura della pagina selezionata.
- **Cancella** - È possibile cancellare tutte le personalizzazioni di una pagina o un'area di lavoro per uno o più utenti. Selezionare prima di tutto una pagina o un'area di lavoro per vedere l'elenco degli utenti che l'hanno personalizzata. Selezionare quindi gli utenti per i quali occorre cancellare le personalizzazioni della pagina o dell'area di lavoro e selezionare **Cancella**. Tutte le personalizzazione che gli utenti selezionati hanno applicato alla pagina o all'area di lavoro selezionata vengono cancellate. Non è possibile annullare questa azione. Se tuttavia una personalizzazione della pagina o dell'area di lavoro viene salvata, tale personalizzazione può essere reimportata.
- **Utenti** - Selezionare un utente per visualizzare l'elenco delle pagine che l'utente ha personalizzato. È quindi possibile attivare o disattivare la capacità dell'utente selezionato di utilizzare la personalizzazione di pagine specifiche o dell'intero sistema. È inoltre possibile importare, esportare o cancellare una personalizzazione per l'utente. Inoltre, è possibile reimpostare i callout delle funzionalità per l'utente. In questo caso, se l'utente ha precedentemente ignorato una finestra popup che introduce nuove funzionalità, questa viene di nuovo visualizzata la volta successiva che l'utente rileva tali funzionalità.
- **Sistema** - È possibile disattivare temporaneamente la personalizzazione per tutti gli utenti nel sistema. In questo caso, tutte le personalizzazione vengono eliminate per tutti gli utenti e tutte le pagine vengono reimpostate allo stato predefinito. Se si attivano nuovamente le personalizzazioni in un secondo momento, queste vengono applicate nuovamente. È inoltre possibile eliminare in modo permanente tutte le personalizzazioni per tutti gli utenti nel sistema. Le personalizzazioni che sono state eliminate non possono essere recuperate. Pertanto, prima di eseguire questa attività, assicurarsi di esportare tutte le personalizzazioni che si desidera importare successivamente.

## <a name="personalizing-inventory-dimensions"></a>Personalizzazione delle dimensioni inventariali

Quando si personalizza l'impostazione delle dimensioni inventariali in una pagina, considerare le impostazioni create utilizzando l'opzione **Visualizza dimensioni**. Ad esempio, è possibile utilizzare la personalizzazione per nascondere una colonna per la dimensione inventariale del numero batch, ma alla successiva apertura della pagina la colonna sarà di nuovo visibile. Questo comportamento si verifica perché le impostazioni **Visualizzazione di dimensioni** controllano le colonne di dimensioni inventariali che vengono visualizzate. Le impostazioni **Visualizzazione dimensioni** vengono applicate a tutte le pagine e sostituiscono qualsiasi impostazione personalizzata dei campi delle dimensioni inventariali nelle singole pagine.

Di conseguenza, nell'esempio precedente, se non si desidera che la colonna relativa alla dimensione inventariale del numero batch venga visualizzata in una pagina, è necessario cancellare la dimensione come parte dell'opzione **Dimensioni di visualizzazione** della tabella per quella pagina.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
