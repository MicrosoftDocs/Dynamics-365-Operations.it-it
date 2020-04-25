---
title: Visualizzazioni salvate
description: In questo argomento viene descritto come utilizzare le funzionalità relative alle visualizzazioni salvate.
author: jasongre
manager: AnnBe
ms.date: 04/10/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2019-07-31
ms.dyn365.ops.version: Platform update 28
ms.openlocfilehash: fe79558b9d2ac4ef1c83918b949d11983b2cc0d8
ms.sourcegitcommit: cd8a28be0acf31c547db1b8f6703dd4b0f62940c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/14/2020
ms.locfileid: "3260485"
---
# <a name="saved-views"></a>Visualizzazioni salvate

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

## <a name="introduction"></a>Introduzione
La personalizzazione riveste un ruolo fondamentale in quanto consente ad utenti e organizzazioni di ottimizzare l'esperienza utente per soddisfare le relative esigenze. Per ulteriori informazioni sulla personalizzazione, vedere [Personalizzare l'esperienza utente](personalize-user-experience.md).

Con la personalizzazione tradizionale, gli utenti possono avere soltanto un singolo insieme di personalizzazioni per modulo. La funzionalità Visualizzazioni salvate espande la personalizzazione in vari modi importanti:

-    Le visualizzazioni consentono agli utenti di avere molteplici insiemi di personalizzazione per modulo, a cui possono accedere rapidamente come necessario. Ciò consente a un utente di creare molteplici visualizzazioni ottimizzate di una pagina, dove ogni visualizzazione è stata adattata per soddisfare le esigenze di esecuzione di una particolare attività aziendale. 

-    Le visualizzazioni create per specifici tipi di pagina possono anche includere filtri o ordinamenti aggiunti dagli utenti, che consentono agli stessi di ritornare rapidamente a set di dati filtrati comunemente. Vedere la sezione [Quali pagine supportano le visualizzazioni](saved-views.md#what-pages-support-views) per ulteriori informazioni. 

-    Le visualizzazioni possono essere pubblicate per gli utenti con ruoli di sicurezza specifici e persone giuridiche specifiche. Pertanto, qualsiasi utente che ha un ruolo specifico e accesso a una determinata persona giuridica può accedere a tale visualizzazione e utilizzarla, anche se tale utente potrebbe non essere in grado di personalizzarla. Questa capacità di pubblicazione consente alle organizzazioni di definire visualizzazioni standard aziendali ottimizzate per le relative esigenze. Per ulteriori informazioni, vedere la sezione [Gestione delle personalizzazioni a livello organizzativo con visualizzazioni](saved-views.md#managing-personalizations-at-an-organizational-level-with-views).

-    Diversamente dalla personalizzazione tradizionale, le visualizzazioni non vengono salvate automaticamente quando un utente esegue personalizzazioni esplicite o filtra un elenco. Salvataggi espliciti sono necessari per fornire flessibilità nella creazione di una visualizzazione prima o dopo le modifiche associate a quella visualizzazione e per assicurarsi che le definizioni delle visualizzazioni non vengano modificate inavvertitamente da filtri o personalizzazioni non progettate per l'utilizzo a lungo termine.  

-    Le visualizzazioni possono essere aggiunte alle aree di lavoro come riquadri, elenchi o collegamenti. Pertanto, un set di dati filtrato può essere disponibile in un'area di lavoro e gli utenti possono associare un set di personalizzazioni rilevanti per quel set di dati con il riquadro o il collegamento.

## <a name="switching-between-views"></a>Passaggio da una visualizzazione all'altra
Dopo l'abilitazione delle visualizzazioni per un ambiente, qualsiasi pagina che supporta le visualizzazioni includerà un selettore di visualizzazioni compresso nella parte superiore del modulo che visualizza il nome della visualizzazione corrente.  

Il selettore di visualizzazioni include due variazioni di dimensioni: 

-   **Selettori di visualizzazioni grandi**: le pagine con un elenco avranno un selettore di visualizzazioni più grande per alcuni motivi. In particolare, il selettore di visualizzazioni più grande indica le pagine in cui la visualizzazione può includere filtri definiti dall'utente. Poiché i filtri sono inclusi nelle visualizzazioni, la dimensione più grande del selettore è anche garantita in quanto i nomi di visualizzazioni saranno spesso la migliore descrizione dei dati visualizzati sullo schermo e l'aspettativa è che gli utenti passeranno più spesso da una visualizzazione all'altra su questi tipi di pagine.  
 
-   **Selettori di visualizzazioni piccoli**: tutti gli altri moduli a pagina intera (con l'eccezione delle aree di lavoro e del dashboard) hanno un selettore di visualizzazioni più piccolo visualizzato accanto al titolo della pagina. Le visualizzazioni in queste pagine includono solo personalizzazioni (e non filtri definiti dall'utente). In queste pagine, il titolo del modulo o del record è in genere l'informazione più importante nella parte superiore del modulo. La dimensione più piccola riflette inoltre una frequenza prevista di passaggio da una visualizzazione all'altra inferiore in queste pagine. 
 
Se si fa clic sul nome della visualizzazione, viene aperto il selettore di visualizzazioni che visualizza l'elenco delle visualizzazioni disponibili per tale pagina

-    **Visualizzazione standard**: la visualizzazione **Standard** (in precedenza noto come la visualizzazione **Classica** ) è la pagina predefinita, a cui non sono applicate personalizzazioni esplicite.
-    **Visualizzazioni personali**: le visualizzazioni senza lucchetti rappresentano le visualizzazioni personali. Si tratta delle visualizzazioni create personalmente o ricevute da un amministratore.  
-    **Visualizzazioni bloccate**: alcune visualizzazioni, ad esempio la visualizzazione **Standard** e qualsiasi visualizzazione pubblicata nel ruolo, presentano un simbolo di un lucchetto accanto al selettore di visualizzazioni. Questo simbolo indica che non è possibile modificare le visualizzazioni. Tuttavia, le personalizzazione implicite che riflettano l'utilizzo della pagina vengono salvate automaticamente. Queste personalizzazione implicite includono la modifica alla larghezza di una colonna della griglia o l'espansione o la compressione di una scheda dettaglio. Tuttavia se si dispone di privilegi di personalizzazione è possibile creare una visualizzazione personale basata su una visualizzazione bloccata utilizzando l'azione **Salva con nome**.
-    **Nuove visualizzazioni**: le visualizzazioni pubblicate che non sono state ancora aperte sono contrassegnate da una scintilla a sinistra del nome della visualizzazione.  

Per passare a un'altra visualizzazione, innanzitutto aprire il selettore di visualizzazioni e selezionare la visualizzazione che si desidera caricare. 

## <a name="creating-and-modifying-views"></a>Creazione e modifica di visualizzazioni
A differenza dalla personalizzazione tradizionale, le visualizzazioni non vengono salvate automaticamente quando un utente esegue personalizzazioni esplicite (o filtra un elenco). Un'azione esplicita è necessaria per salvare le modifiche a una visualizzazione. Ciò fornisce all'utente la flessibilità nella creazione di una visualizzazione prima o dopo le modifiche associate a quella visualizzazione e assicura che le definizioni delle visualizzazioni non vengano modificate inavvertitamente da filtri o personalizzazioni occasionali. Da notare che le personalizzazioni implicite (ad esempio l'espansione o la compressione di una scheda dettaglio o la modifica della larghezza di una colonna della griglia) vengono salvate automaticamente nella visualizzazione corrente, anche per le visualizzazioni bloccate. 

Per assicurarsi che lo stato corrente della visualizzazione è noto, quando si iniziano ad apportare modifiche a una visualizzazione eseguendo una personalizzazione esplicita o applicando filtri, un asterisco verrà visualizzato accanto al nome della visualizzazione corrente a indicare che si sta utilizzando una versione modificata e non salvata di quella visualizzazione.

Per salvare le modifiche, attenersi alla procedura seguente.
1.  Selezionare il nome della visualizzazione per aprire il selettore di visualizzazioni.
2.  Per modificare la visualizzazione esistente:
     1. Selezionare **Salva**. Da notare che questa azione non verrà abilitata per le visualizzazioni bloccate. 
3.  Per creare una nuova visualizzazione:
     1.    Selezionare **Salva con nome**. 
     2.    Immettere un nome di visualizzazione ed eventualmente una descrizione.
     3.    Selezionare **Salva**.

## <a name="changing-the-default-view"></a>Modifica della visualizzazione predefinita
La visualizzazione predefinita è la visualizzazione che il sistema tenterà di aprire quando si accede per la prima volta alla pagina. Si consiglia di impostare la visualizzazione che si prevede di utilizzare più spesso come visualizzazione predefinita.  

Per cambiare la visualizzazione predefinita di una pagina, seguire questi passaggi: 
1.  Passare alla visualizzazione che si utilizza come visualizzazione predefinita. 
2.  Selezionare il nome della visualizzazione per aprire il selettore di visualizzazioni. 
3.  Selezionare **Altro** e **Aggiungi come predefinita**.  

In alternativa, quando si crea una nuova visualizzazione (mediante l'azione **Salva con nome** ), è possibile impostare quella nuova visualizzazione come visualizzazione predefinita impostando l'opzione **Aggiungi come predefinita** prima di salvare la visualizzazione.

In alcuni casi, la query associata alla visualizzazione predefinita non viene eseguita quando si accede per la prima volta a una pagina. Ad esempio, se si passa da un riquadro a una pagina, la query del riquadro verrà eseguita indipendentemente dalla query associata alla visualizzazione predefinita. Inoltre, se si accede a una pagina con una visualizzazione standard che ha già una query definita, la query originale verrà eseguita al posto della query della visualizzazione predefinita. In questo caso, un messaggio informativo verrà visualizzato durante il caricamento della visualizzazione. Il passaggio da una visualizzazione all'altra dopo il caricamento della pagina dovrebbe consentire l'esecuzione della query della visualizzazione nel modo previsto. A partire dalla versione 10.0.10 dell'aggiornamento 34 della piattaforma, il messaggio informativo avrà un'azione incorporata che consente di caricare direttamente la query della visualizzazione predefinita.

## <a name="managing-personal-views"></a>Gestione delle visualizzazioni personali 
La finestra dialogo **Gestisci le mie visualizzazioni** fornisce funzionalità di gestione di base delle visualizzazioni personali e dell'ordine delle visualizzazioni nel selettore di visualizzazioni. Per aprire questa pagina, fare clic sul nome della visualizzazione per aprire il menu a discesa del selettore di visualizzazioni, selezionare **Altro**, quindi selezionare **Gestisci le mie visualizzazioni**.  

Per un elenco delle visualizzazioni disponibili per quella pagina, si ha a disposizione il set di azioni seguente.  
-    **Modificare la visualizzazione predefinita**: utilizzare l'azione **Aggiungi come predefinita** per impostare la visualizzazione attualmente selezionata come visualizzazione predefinita per la pagina.  
-    **Riordinare le visualizzazioni**: utilizzare le azioni **Sposta in alto** e **Sposta in basso** per organizzare le visualizzazioni secondo un ordine specifico.  
-    **Rinominare una visualizzazione**: utilizzare l'azione **Rinomina** per modificare il nome della visualizzazione personale attualmente selezionata. Questa azione è disattivata per le visualizzazioni bloccate. 
-    **Eliminare una visualizzazione**: utilizzare l'azione **Rimuovi** per eliminare definitivamente la visualizzazione attualmente selezionata dalla pagina. Non è possibile ripristinare una visualizzazione rimossa.  

Qualsiasi modifica apportata in questa finestra di dialogo diventerà effettiva dopo la selezione del pulsante **Salva**.

## <a name="managing-personalizations-at-an-organizational-level-with-views"></a>Gestione di personalizzazioni a livello organizzativo con visualizzazioni
Per informazioni su come le visualizzazioni salvate aiutano a migliorare la gestione delle personalizzazioni a livello organizzativo, questa sezione descrive alcune differenze nella gestione della personalizzazione con e senza la funzionalità Visualizzazioni salvate.

Senza le visualizzazioni, gli amministratori applicavano un insieme di personalizzazioni di una pagina a un utente, a un gruppo utenti o a utenti tramite la pagina Personalizzazione. Se tali utenti disponevano di diritti di personalizzazione, le personalizzazioni erano applicate a tale pagina. Tuttavia, non si aveva la possibilità di impedire agli utenti di personalizzare ulteriormente la pagina, di conseguenza l'organizzazione non era in grado di assicurare un'interfaccia utente coerente per gli utenti. Se uno di questi utenti non disponeva di diritti di personalizzazione, le personalizzazioni ad essi assegnate da un amministratore non venivano caricate. Inoltre, se un nuovo utente veniva assunto in un'organizzazione, gli amministratori dovevano caricare manualmente un insieme di personalizzazioni per l'utente. Non esisteva un meccanismo automatico per definire che un determinato set di personalizzazioni doveva essere disponibile in quel ruolo.

Con la funzionalità Visualizzazioni salvate, la gestione delle personalizzazioni a livello di organizzazione è molto più semplice, principalmente perché le visualizzazioni possono essere pubblicate nei gruppi di utenti. Dopo che una visualizzazione è stata pubblicata, qualsiasi utente che ha uno dei ruoli di sicurezza definiti e ha accesso a una delle persone giuridiche specificate sarà in grado di vedere e utilizzare la visualizzazione, anche se l'utente potrebbe non essere in grado di personalizzarla. Sebbene ogni utente disponga di una copia della visualizzazione pubblicata in cui le personalizzazioni implicite vengono applicate, nessun utente può salvare personalizzazioni esplicite o aggiornamenti della query in una visualizzazione pubblicata. In altre parole, le visualizzazioni pubblicate sono bloccate. Inoltre, se ai nuovi utenti vengono assegnati ruoli in persone giuridiche in cui sono state pubblicate le visualizzazioni, vedranno automaticamente le visualizzazioni associate ai loro ruoli e alle persone giuridiche. Nessuna azione aggiuntiva è richiesta dall'amministratore. Allo stesso modo, se gli utenti cambiano ruolo in un'organizzazione o ottengono l'accesso a diverse persone giuridiche, potrebbero non essere più in grado di accedere alle visualizzazioni precedentemente pubblicate per loro. Anche in questo caso, nessuna azione aggiuntiva è richiesta dall'amministratore.

Gli aggiornamenti a una visualizzazione pubblicata possono essere distribuiti facilmente agli utenti pubblicando di nuovo la visualizzazione su ruoli di sicurezza e persone giuridiche appropriati.

La capacità di pubblicazione consente alle organizzazioni di definire visualizzazioni standard aziendali ottimizzate per le relative esigenze e destinate ad utenti con specifici ruoli di sicurezza.  

## <a name="publishing-views"></a>Pubblicazione di visualizzazioni
Durante il processo di pubblicazione, le visualizzazioni possono essere assegnate a uno o più ruoli di sicurezza per una o più persone giuridiche. Pertanto, qualsiasi utente con diritti di accesso a una persona giuridica che è assegnato a uno dei ruoli può accedere e utilizzare le visualizzazioni, sebbene non le possa modificare. Gli amministratori di sistema possono accedere all'azione **Pubblica** nel menu a discesa del selettore di visualizzazioni. Tuttavia, anche altri utenti attendibili della tua organizzazione possono avere accesso alla pubblicazione della visualizzazione tramite il nuovo ruolo **Amministratore di visualizzazioni salvate**.

Per pubblicare una visualizzazione, attenersi alla procedura riportata di seguito: 
1.  Creare e salvare una copia personale della visualizzazione che si intende pubblicare. 
2.  Con quella visualizzazione attualmente caricata, selezionare il nome della visualizzazione per aprire il menu a discesa del selettore di visualizzazioni. 
3.  Selezionare il pulsante **Altro**, quindi selezionare **Pubblica**. Viene visualizzata la finestra di dialogo Pubblica.  
4.  Immettere un nome di visualizzazione ed eventualmente una descrizione della visualizzazione. Questo è il nome che gli utenti che ricevono la visualizzazione vedranno nei relativi selettori di visualizzazioni. I nomi delle visualizzazioni pubblicate per una pagina devono essere univoci. Non sono consentiti nomi duplicati, anche se l'elenco dei ruoli o delle persone giuridiche a cui le visualizzazioni sono applicate differisce.
5.  Aggiungere i ruoli di sicurezza corrispondenti agli utenti che sono interessati da questa visualizzazione.
6. Aggiungere le persone giuridiche per cui la visualizzazione deve essere disponibile. 
7. [10.0.9/Update 33 o successivi della piattaforma] Determinare se la visualizzazione deve essere pubblicata come visualizzazione predefinita per gli utenti selezionati. Impostare una visualizzazione come predefinita significa che è la visualizzazione che gli utenti vedranno la prossima volta che apriranno la pagina di destinazione. Ciò modificherà la visualizzazione predefinita per tali utenti; tuttavia, gli utenti possono comunque modificare la visualizzazione predefinita dopo la pubblicazione.    
8.  Selezionare **Pubblica**

Da notare che in alcuni ambienti la visualizzazione pubblicata sarà visibile solo dopo un certo tempo (fino a un'ora).

## <a name="modifying-a-published-view"></a>Modifica di una visualizzazione pubblicata
Dopo la pubblicazione di una visualizzazione, è possibile apportare modifiche a tale visualizzazione. Sebbene non sia possibile apportare modifiche in tempo reale a una visualizzazione pubblicata, in quanto la modifica di tali visualizzazioni è bloccata, è possibile pubblicare di nuovo una pubblicazione per effettuare gli aggiornamenti.  

Se le modifiche che si desidera apportare a una visualizzazione pubblicata sono relative solo ai parametri di pubblicazione (il nome e la descrizione della visualizzazione o i ruoli di sicurezza su cui la visualizzazione è pubblicata), procedere come segue: 
1.  Passare alla visualizzazione pubblicata per i parametri che si desidera aggiornare. 
2.  Selezionare **Pubblica** dal menu a discesa del selettore di visualizzazioni. 
3.  Selezionare **Sì** se si desidera aggiornare la visualizzazione corrente (o **No** se si desidera pubblicarla con un nome diverso).
4.  Aggiornare il nome, la descrizione e/o i ruoli di sicurezza della visualizzazione. 
5.  Selezionare **Pubblica** 
6.  [10.0.8/Update 32 o precedenti della piattaforma] Se si aggiorna il nome della visualizzazione pubblicata, è inoltre necessario eliminare la visualizzazione pubblicata con il nome precedente (vedere la sezione **Gestione di visualizzazioni pubblicate** per ulteriori dettagli). 
7. [10.0.9/Update 33 o successivi della piattaforma] Se in origine questa visualizzazione pubblicata è stata scelta come visualizzazione predefinita, dopo la ripubblicazione sarà nuovamente la visualizzazione predefinita per tali utenti.  

Se le modifiche apportate alla visualizzazione pubblicata comportano la modifica delle personalizzazioni o dei filtri associati alla visualizzazione, procedere come segue: 
1.  Passare alla visualizzazione pubblicata che si desidera modificare. 
2.  Salvare una copia della visualizzazione pubblicata per crearne una bozza locale. 
3.  Modificare la bozza locale con le modifiche necessarie.
4.  Pubblicare la visualizzazione con il nome originale. 

## <a name="managing-published-views"></a>Gestione di visualizzazioni pubblicate
Come per la gestione delle visualizzazioni personali, la finestra di dialogo **Gestisci le mie visualizzazioni** fornisce agli utenti funzionalità di gestione di base dei privilegi di pubblicazione per le visualizzazioni pubblicate delle pagine (oltre che per le visualizzazioni personali). Per aprire questa pagina, selezionare il nome della visualizzazione per aprire il menu a discesa del selettore di visualizzazioni, selezionare **Altro**, quindi selezionare **Gestisci le mie visualizzazioni**.

Tutti gli utenti dispongono di una scheda **Visualizzazioni personali** che elenca le visualizzazioni personali mentre gli utenti con privilegi di pubblicazione dispongono anche di una scheda **Pubblicate** che mostra tutte le visualizzazioni pubblicate per tale pagina. Poiché è possibile che vi siano vari utenti che pubblicano visualizzazioni, è importante poter gestire l'elenco completo delle visualizzazioni pubblicate, indipendentemente se si è l'utente che ha effettivamente pubblicato la visualizzazione.

Per l'elenco di tutte le visualizzazioni pubblicate per la pagina, si ha a disposizione il set di azioni seguente. 

-    **Pubblicare**: utilizzare l'azione **Pubblica** per pubblicare di nuovo una visualizzazione dopo che i parametri di pubblicazione (nome, descrizione, ruoli di sicurezza o persone giuridiche) sono stati modificati.
-    **Rimuovere**: utilizzare l'azione **Rimuovi** per eliminare definitivamente una visualizzazione pubblicata. Questa azione rimuove la visualizzazione per tutti gli utenti del sistema. La rimozione delle visualizzazione pubblicate avrà effetto dopo la selzione del pulsante **Salva**.

## <a name="frequently-asked-questions"></a>Domande frequenti
### <a name="how-do-i-enable-saved-views-in-my-environment"></a>Come si abilitano le visualizzazioni salvate nel proprio ambiente? 
Nota: la funzionalità **Visualizzazione salvate** richiede il sistema di personalizzazione in Finance and Operations per essere abilitata. Se la personalizzazione è disattivata per l'intero ambiente, le visualizzazioni verranno disabilitate anche se si esegue la procedura seguente. 

**10.0.9/Update 33 e successivi della piattaforma** La funzionalità **Visualizzazioni salvate** è disponibile direttamente in Gestione funzionalità in qualsiasi ambiente. Come altre funzionalità di anteprima pubblica, l'abilitazione di questa funzionalità in produzione è soggetta alle [condizioni d'uso supplementari](https://go.microsoft.com/fwlink/?linkid=2105274).  

**10.0.8/Update 32 e precedenti della piattaforma** La funzionalità **Visualizzazioni salvate** può essere abilitata in ambienti di Livello 1 (Sviluppo/Test) e Livello 2 (Sandbox) al fine di fornire ulteriori test e modifiche di progettazione seguendo i passaggi seguenti.

1.  **Abilitare l'anteprima**: Eseguire la seguente istruzione SQL: 

    `INSERT INTO SYSFLIGHTING (FLIGHTNAME, enabled, FLIGHTSERVICEID, PARTITION) VALUES('CLISavedViewsEnableFeature', 1, 0, 5637144576);`

2. **Reimpostare IIS** per liberare la cache statica delle versioni di anteprima. 

3.  **Individuare la funzionalità**: spostarsi nell'area di lavoro **Gestione funzionalità**. Se **Visualizzazioni salvate** non appare nell'elenco, selezionare il pulsante **Controlla aggiornamenti**.   

4.  **Abilitare la funzionalità**: Individuare la funzionalità **Visualizzazioni salvate** nell'elenco delle funzionalità e selezionare **Abilita ora** nel riquadro dei dettagli.

Tutte le sessioni utente successive verranno avviate con le visualizzazioni salvate abilitate.


### <a name="what-happens-to-existing-personalizations-when-views-are-enabled"></a>Cosa succede alle personalizzazioni esistenti quando le visualizzazioni vengono abilitate? 
Quando le visualizzazioni vengono abilitate, tutte le personalizzazioni esistenti per un utente e un modulo vengono salvate in una nuova visualizzazione denominata **Visualizzazione personale** che viene impostata automaticamente come visualizzazione predefinita. Ciò garantisce la coerenza dell'esperienza utente prima e dopo l'abilitazione delle visualizzazioni, salvo per il selettore di visualizzazioni visualizzato nei moduli.  

### <a name="what-pages-support-views"></a>Quali pagine supportano le visualizzazioni? 
Le visualizzazioni sono disponibili nella maggior parte delle pagine. In particolare, le visualizzazioni sono attualmente disponibili per tutte le pagine a schermo intero ad eccezione dei dashboard e delle aree di lavoro. Inoltre, le pagine non a schermo intero, tra cui finestre di dialogo, finestre di dialogo a discesa, ricerche, anteprime avanzate, non supportano attualmente le visualizzazioni. È possibile che il supporto delle visualizzazioni per ulteriori tipi di pagine, ad esempio aree di lavoro e finestre di dialogo, sia preso in considerazione per un aggiornamento futuro.   

### <a name="who-is-allowed-to-publish-views"></a>A chi è consentito pubblicare visualizzazioni?
Solo gli amministratori di sistema e gli utenti assegnati al ruolo **Amministratore di visualizzazioni salvate** hanno le autorizzazioni per pubblicare le visualizzazioni. 

### <a name="why-am-i-not-able-to-save-filters-with-this-view"></a>Perché non è possibile salvare filtri con una visualizzazione? 
Non è possibile salvare filtri con una visualizzazione per vari motivi: 

- La pagina può non supportare il salvataggio di filtri nella definizione della visualizzazione. Da notare che solo le pagine con grandi selettori di visualizzazioni consentono il salvataggio di personalizzazioni e modifiche di query come visualizzazioni. Per ulteriori informazioni, vedere la sezione **Passaggio da una visualizzazione all'altra**. 

- La pagina in questione potrebbe non supportare correttamente le visualizzazioni, perché potrebbe ignorare la query di visualizzazione completamente o utilizzare una tabella temporanea con dati non persistenti. 

### <a name="what-data-will-i-see-when-i-visit-a-page"></a>Quali dati saranno visibili quando si visita una pagina? 
Per le pagine con selettori di visualizzazione piccoli (solo le personalizzazioni possono essere salvate nella visualizzazione), saranno visibili gli stessi dati che sono sempre visibili quando si visita la pagina. 

Per le pagine con grandi selettori di visualizzazione (personalizzazioni e query possono essere salvate nella visualizzazione), saranno visibili principalmente i dati collegati alla query associata alla visualizzazione predefinita. Vi sono due eccezioni principali - Se si passa da un riquadro a una pagina, la query del riquadro verrà eseguita indipendentemente dalla query associata alla visualizzazione predefinita. Se quel riquadro è stato creato dopo aver abilitato le visualizzazioni, la selezione di un riquadro aprirà la pagina con la visualizzazione associata a quel riquadro.   
     - Se si accede a una pagina e quel punto di ingresso include una query, la query originale verrà eseguita al posto della query della visualizzazione predefinita. Quando ciò avviene, si verrà avvisati mediante un messaggio informativo durante il caricamento della visualizzazione. È inoltre possibile confermare passando a questa visualizzazione dopo il caricamento della pagina, in quanto la visualizzazione della query dovrebbe essere eseguita.  


