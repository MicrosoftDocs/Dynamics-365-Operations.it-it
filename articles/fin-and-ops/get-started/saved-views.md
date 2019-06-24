---
title: Visualizzazioni salvate
description: In questo argomento viene descritto come utilizzare le funzionalità relative alle visualizzazioni salvate.
author: jasongre
manager: AnnBe
ms.date: 06/05/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard
ROBOTS: NOINDEX, NOFOLLOW
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2019-07-31
ms.dyn365.ops.version: Platform update 28
ms.openlocfilehash: ea2f2dbd615480bb76e1d04a106ae69bf6f45f4b
ms.sourcegitcommit: fcae2e7938d7dbd94b76b0948b084d90d5fc919c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/05/2019
ms.locfileid: "1620780"
---
# <a name="saved-views"></a>Visualizzazioni salvate

[!include [banner](../includes/banner.md)]
[!include [private preview banner](../includes/private-preview-banner.md)]

## <a name="introduction"></a>Introduzione
La personalizzazione riveste un ruolo fondamentale in quanto consente ad utenti e organizzazioni di ottimizzare l'esperienza utente in Microsoft Dynamics 365 for Finance and Operations per soddisfare le relative esigenze. Per ulteriori informazioni sulla personalizzazione, vedere [Personalizzare l'esperienza utente](personalize-user-experience.md).

Con la personalizzazione tradizionale, gli utenti possono avere soltanto un singolo insieme di personalizzazioni per modulo. La funzionalità Visualizzazioni salvate espande la personalizzazione in vari modi importanti:

-    Le visualizzazioni consentono agli utenti di avere molteplici insiemi di personalizzazione per modulo, a cui possono accedere rapidamente come necessario. Ciò consente a un utente di creare molteplici visualizzazioni ottimizzate di una pagina, dove ogni visualizzazione è stata adattata per soddisfare le esigenze di esecuzione di una particolare attività aziendale. 

-    Le visualizzazioni create per specifici tipi di pagina possono anche includere filtri o ordinamenti aggiunti dagli utenti, che consentono agli stessi di ritornare rapidamente a set di dati filtrati comunemente. Vedere la sezione [Quali pagine supportano le visualizzazioni](saved-views.md#what-pages-support-views) per ulteriori informazioni. 

-    Le visualizzazioni possono essere pubblicate su ruoli di sicurezza, nel senso che qualsiasi utente con un determinato ruolo potrà accedere e utilizzare quella visualizzazione, indipendentemente dalla capacità di personalizzazione dell'utente. Questa capacità di pubblicazione consente alle organizzazioni di definire visualizzazioni standard aziendali ottimizzate per le relative esigenze. Vedere la sezione [Gestione delle personalizzazioni a livello organizzativo con visualizzazioni](saved-views.md#managing-personalizations-at-an-organizational-level-with-views) per ulteriori informazioni.

-    Diversamente dalla personalizzazione tradizionale, le visualizzazioni non vengono salvate automaticamente quando un utente esegue personalizzazioni esplicite o filtra un elenco. Salvataggi espliciti sono necessari per fornire flessibilità nella creazione di una visualizzazione prima o dopo le modifiche associate a quella visualizzazione e per assicurarsi che le definizioni delle visualizzazioni non vengano modificate inavvertitamente da filtri o personalizzazioni non progettate per l'utilizzo a lungo termine.  

## <a name="switching-between-views"></a>Passaggio da una visualizzazione all'altra
Dopo l'abilitazione delle visualizzazioni per un ambiente, qualsiasi pagina che supporta le visualizzazioni includerà un selettore di visualizzazioni compresso nella parte superiore del modulo che visualizza il nome della visualizzazione corrente.  

Il selettore di visualizzazioni include due variazioni di dimensioni: 

-   **Selettori di visualizzazioni grandi**: le pagine con un elenco avranno un selettore di visualizzazioni più grande per alcuni motivi. In particolare, il selettore di visualizzazioni più grande indica le pagine in cui la visualizzazione può includere filtri definiti dall'utente. Poiché i filtri sono inclusi nelle visualizzazioni, la dimensione più grande del selettore è anche garantita in quanto i nomi di visualizzazioni saranno spesso la migliore descrizione dei dati visualizzati sullo schermo e l'aspettativa è che gli utenti passeranno più spesso da una visualizzazione all'altra su questi tipi di pagine.  
 
-   **Selettori di visualizzazioni piccoli**: tutti gli altri moduli a pagina intera hanno un selettore di visualizzazioni più piccolo visualizzato accanto al titolo della pagina. Le visualizzazioni in queste pagine includono solo personalizzazioni (e non filtri definiti dall'utente). In queste pagine, il titolo del modulo o del record è in genere l'informazione più importante nella parte superiore del modulo. La dimensione più piccola riflette inoltre una frequenza prevista di passaggio da una visualizzazione all'altra inferiore in queste pagine. 
 
Se si fa clic sul nome della visualizzazione, viene aperto il selettore di visualizzazioni che visualizza l'elenco delle visualizzazioni disponibili per tale pagina

-    **Visualizzazione classica**: la visualizzazione classica è la visualizzazione predefinita della pagina senza personalizzazioni esplicite applicate.  
-    **Visualizzazioni personali**: le visualizzazioni senza lucchetti rappresentano le visualizzazioni personali. Si tratta delle visualizzazioni create personalmente o ricevute da un amministratore.  
-    **Visualizzazioni bloccate**: alcune visualizzazioni (come la visualizzazione classica e le visualizzazioni pubblicate sul proprio ruolo) presentano un lucchetto accanto al selettore di visualizzazioni, per segnalare che non è possibile modificare tali visualizzazioni. Tuttavia, le personalizzazioni implicite relative all'utilizzo delle pagine vengono salvate automaticamente, ad esempio la modifica della larghezza di una colonna della griglia o l'espansione o la compressione di una scheda dettaglio. È tuttavia possibile creare una visualizzazione personale basata su una visualizzazione bloccata utilizzando l'azione **Salva una copia**, se si dispone di privilegi di personalizzazione.
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
     1.    Selezionare **Salva una copia**. 
     2.    Immettere un nome di visualizzazione ed eventualmente una descrizione.
     3.    Selezionare **Salva**.

## <a name="changing-the-default-view"></a>Modifica della visualizzazione predefinita
La visualizzazione predefinita è la visualizzazione che il sistema tenterà di aprire quando si accede per la prima volta alla pagina. Si consiglia di impostare la visualizzazione che si prevede di utilizzare più spesso come visualizzazione predefinita.  

Per cambiare la visualizzazione predefinita di una pagina, seguire questi passaggi: 
1.  Passare alla visualizzazione che si utilizza come visualizzazione predefinita. 
2.  Selezionare il nome della visualizzazione per aprire il selettore di visualizzazioni. 
3.  Selezionare **Altro** e **Aggiungi come predefinita**.  

In alternativa, quando si crea una nuova visualizzazione (mediante l'azione **Salva una copia** ), è possibile impostare quella nuova visualizzazione come visualizzazione predefinita impostando l'opzione **Aggiungi come predefinita** prima di salvare la visualizzazione.  

In alcuni casi, la query associata alla visualizzazione predefinita non viene eseguita quando si accede per la prima volta a una pagina. Ad esempio, se si passa da un riquadro a una pagina, la query del riquadro verrà eseguita indipendentemente dalla query associata alla visualizzazione predefinita. Inoltre, se si accede a una pagina dove la visualizzazione classica ha già una query definita, la query originale verrà eseguita al posto della query della visualizzazione predefinita. In questo caso, un messaggio informativo verrà visualizzato durante il caricamento della visualizzazione. Il passaggio da una visualizzazione all'altra dopo il caricamento della pagina dovrebbe consentire l'esecuzione della query della visualizzazione nel modo previsto.

## <a name="managing-personal-views"></a>Gestione delle visualizzazioni personali 
La finestra dialogo **Gestisci le mie visualizzazioni** fornisce funzionalità di gestione di base delle visualizzazioni personali e dell'ordine delle visualizzazioni nel selettore di visualizzazioni. Per aprire questa pagina, fare clic sul nome della visualizzazione per aprire il menu a discesa del selettore di visualizzazioni, selezionare **Altro**, quindi selezionare **Gestisci le mie visualizzazioni**.  

Per un elenco delle visualizzazioni disponibili per quella pagina, si ha a disposizione il set di azioni seguente.  
-    **Modificare la visualizzazione predefinita**: utilizzare l'azione **Aggiungi come predefinita** per impostare la visualizzazione attualmente selezionata come visualizzazione predefinita per la pagina.  
-    **Riordinare le visualizzazioni**: utilizzare le azioni **Sposta in alto** e **Sposta in basso** per organizzare le visualizzazioni secondo un ordine specifico.  
-    **Rinominare una visualizzazione**: utilizzare l'azione **Rinomina** per modificare il nome della visualizzazione personale attualmente selezionata. Questa azione è disattivata per le visualizzazioni bloccate. 
-    **Eliminare una visualizzazione**: utilizzare l'azione **Rimuovi** per eliminare definitivamente la visualizzazione attualmente selezionata dalla pagina. Non è possibile ripristinare una visualizzazione rimossa.  

Qualsiasi modifica apportata in questa finestra di dialogo diventerà effettiva dopo la selezione del pulsante **Salva**.

## <a name="managing-personalizations-at-an-organizational-level-with-views"></a>Gestione di personalizzazioni a livello organizzativo con visualizzazioni
Per comprendere i miglioramenti nella gestione delle personalizzazioni a livello organizzativo, diamo un'occhiata al funzionamento della gestione delle personalizzazioni prima dell'utilizzo delle visualizzazioni.  

Senza le visualizzazioni, gli amministratori applicavano un insieme di personalizzazioni di una pagina a un utente, a un gruppo utenti o a utenti che utilizzavano il modulo Personalizzazione. Se tali utenti disponevano di diritti di personalizzazione, le personalizzazioni erano applicate a tale pagina. Tuttavia, non si aveva la possibilità di impedire agli utenti di personalizzare ulteriormente la pagina, di conseguenza l'organizzazione non era in grado di assicurare un'interfaccia utente coerente per gli utenti. Se uno di questi utenti non disponeva di diritti di personalizzazione, le personalizzazioni ad essi assegnate da un amministratore non venivano caricate. Inoltre, se un nuovo utente veniva assunto in un'organizzazione, gli amministratori dovevano caricare manualmente un insieme di personalizzazioni per l'utente. Non esisteva un meccanismo automatico per definire un determinato set di personalizzazioni disponibile per quell'utente.

Con la funzionalità Visualizzazioni salvate, la gestione delle personalizzazioni a livello di organizzazione è molto più semplice, principalmente grazie alla capacità di pubblicare visualizzazioni su ruoli di sicurezza. Dopo la pubblicazione di una visualizzazione, qualsiasi utente con un determinato ruolo potrà accedere e utilizzare la visualizzazione, indipendentemente dalla capacità di personalizzazione dell'utente. Sebbene ogni utente disponga di una copia della visualizzazione pubblicata in cui le personalizzazioni implicite vengono applicate, nessun utente può salvare personalizzazioni esplicite o aggiornamenti della query nella visualizzazione pubblicata (la visualizzazione è bloccata). Inoltre, se a nuovi utenti viene assegnato un ruolo su cui la visualizzazione è stata pubblicata, questi vedranno automaticamente le visualizzazioni associate ai relativi ruoli senza alcuna azione da parte dell'amministratore. Analogamente, se un utente cambia ruolo in un'organizzazione, le visualizzazioni associate al ruolo precedente non saranno più accessibili, anche in questo senza alcuna azione da parte dell'amministratore. Gli aggiornamenti a una visualizzazione pubblicata possono essere distribuiti facilmente agli utenti pubblicando di nuovo la visualizzazione su ruoli di sicurezza appropriati.

La capacità di pubblicazione consente alle organizzazioni di definire visualizzazioni standard aziendali ottimizzate per le relative esigenze e destinate ad utenti con specifici ruoli di sicurezza.  

## <a name="publishing-views"></a>Pubblicazione di visualizzazioni
Durante il processo di pubblicazione, alle visualizzazioni è possibile assegnare uno o più ruoli di sicurezza, il che significa che qualsiasi utente con quel ruolo potrà accedere e utilizzare quella visualizzazione, sebbene non possa modificare la visualizzazione. Attualmente, solo gli amministratori di sistema dispongono dei diritti per l'azione **Pubblica** nel menu a discesa del selettore di visualizzazioni.  

Per pubblicare una visualizzazione, attenersi alla procedura riportata di seguito: 
1.  Creare e salvare una copia personale della visualizzazione che si intende pubblicare. 
2.  Con quella visualizzazione attualmente caricata, selezionare il nome della visualizzazione per aprire il menu a discesa del selettore di visualizzazioni. 
3.  Selezionare il pulsante **Altro**, quindi selezionare **Pubblica**. Viene visualizzata la finestra di dialogo Pubblica.  
4.  Immettere un nome di visualizzazione ed eventualmente una descrizione della visualizzazione. Questo è il nome che gli utenti che ricevono la visualizzazione vedranno nei relativi selettori di visualizzazioni. Da notare che non sono consentiti nomi duplicati per le visualizzazioni pubblicate, anche se l'elenco dei ruoli a cui sono applicate differisce.  
5.  Aggiungere qualsiasi ruolo di sicurezza che corrisponde agli utenti che otterranno tale visualizzazione.  
6.  Selezionare **Pubblica**

Da notare che in alcuni ambienti la visualizzazione pubblicata sarà visibile solo dopo un certo tempo (fino a un'ora).

## <a name="modifying-a-published-view"></a>Modifica di una visualizzazione pubblicata
Dopo la pubblicazione di una visualizzazione, è possibile apportare modifiche a tale visualizzazione. Sebbene non sia possibile apportare modifiche in tempo reale a una visualizzazione pubblicata, in quanto la modifica di tali visualizzazioni è bloccata, è possibile pubblicare di nuovo una pubblicazione per effettuare gli aggiornamenti.  

Se le modifiche che si desidera apportare a una visualizzazione pubblicata sono relative solo ai parametri di pubblicazione (il nome e la descrizione della visualizzazione o i ruoli di sicurezza su cui la visualizzazione è pubblicata), procedere come segue: 
1.  Passare alla visualizzazione pubblicata per i parametri che si desidera aggiornare. 
2.  Selezionare **Pubblica** dal menu a discesa del selettore di visualizzazioni. 
3.  Selezionare **Sì** se si desidera aggiornare la visualizzazione corrente (o **No** se si desidera pubblicarla con un nome diverso).
4.  Aggiornare il nome, la descrizione e/o i ruoli di sicurezza della visualizzazione. 
5.  Selezionare **Pubblica** 
6.  Se si aggiorna il nome della visualizzazione pubblicata, è inoltre necessario eliminare la visualizzazione pubblicata con il nome precedente (vedere la sezione **Gestione di visualizzazioni pubblicate** per ulteriori dettagli). 

Se le modifiche apportate alla visualizzazione pubblicata comportano la modifica delle personalizzazioni o dei filtri associati alla visualizzazione, procedere come segue: 
1.  Passare alla visualizzazione pubblicata che si desidera modificare. 
2.  Salvare una copia della visualizzazione pubblicata per crearne una bozza locale. 
3.  Modificare la bozza locale con le modifiche necessarie.
4.  Pubblicare la visualizzazione con il nome originale. 

## <a name="managing-published-views"></a>Gestione di visualizzazioni pubblicate
Come per la gestione delle visualizzazioni personali, la finestra di dialogo **Gestisci le mie visualizzazioni** fornisce agli utenti funzionalità di gestione di base dei privilegi di pubblicazione per le visualizzazioni pubblicate delle pagine (oltre che per le visualizzazioni personali). Per aprire questa pagina, selezionare il nome della visualizzazione per aprire il menu a discesa del selettore di visualizzazioni, selezionare **Altro**, quindi selezionare **Gestisci le mie visualizzazioni**.

Tutti gli utenti dispongono di una scheda **Visualizzazioni personali** che elenca le visualizzazioni personali mentre gli utenti con privilegi di pubblicazione dispongono anche di una scheda **Pubblicate** che mostra tutte le visualizzazioni pubblicate per tale pagina. Poiché è possibile che vi siano vari utenti che pubblicano visualizzazioni, è importante poter gestire l'elenco completo delle visualizzazioni pubblicate, indipendentemente se si è l'utente che ha effettivamente pubblicato la visualizzazione.

Per l'elenco di tutte le visualizzazioni pubblicate per la pagina, si ha a disposizione il set di azioni seguente. 

-    **Pubblicare**: utilizzare l'azione **Pubblica** per pubblicare di nuovo una visualizzazione con parametri di pubblicazione modificati (nome, descrizione, ruoli di sicurezza).  
-    **Rimuovere**: utilizzare l'azione **Rimuovi** per eliminare definitivamente una visualizzazione pubblicata. Questa azione rimuove la visualizzazione per tutti gli utenti del sistema.  
 
Qualsiasi modifica apportata in questa finestra di dialogo diventerà effettiva dopo la selezione del pulsante **Salva**.

## <a name="frequently-asked-questions"></a>Domande frequenti
### <a name="how-do-i-enable-saved-views-in-my-environment"></a>Come si abilitano le visualizzazioni salvate nel proprio ambiente? 
Per abilitare le visualizzazioni salvate, un amministratore di sistema deve effettuare le seguenti operazioni: 
1.  Andare alla pagina **Personalizzazione** utilizzando la ricerca per navigazione. 
2.  Selezionare la scheda **Impostazioni**.
3.  Impostare l'opzione **Abilita visualizzazioni salvate** su **Sì**.

Dopo l'abilitazione di questa funzionalità, tutte le sessioni utente successive verranno avviate con le visualizzazioni abilitate.  

Da notare che se la personalizzazione è disattivata per l'ambiente, le visualizzazioni verranno abilitate anche se si esegue la procedura precedente. Questo perché la funzionalità relativa alle visualizzazioni si basa sul sottosistema di personalizzazione.

### <a name="what-happens-to-existing-personalizations-when-views-are-enabled"></a>Cosa succede alle personalizzazioni esistenti quando le visualizzazioni vengono abilitate? 
Quando le visualizzazioni vengono abilitate, tutte le personalizzazioni esistenti per un utente e un modulo vengono salvate in una nuova visualizzazione denominata **Visualizzazione personale** che viene impostata automaticamente come visualizzazione predefinita. Ciò garantisce la coerenza dell'esperienza utente prima e dopo l'abilitazione delle visualizzazioni, salvo per il selettore di visualizzazioni visualizzato nei moduli.  

### <a name="what-pages-support-views"></a>Quali pagine supportano le visualizzazioni? 
Le visualizzazioni sono disponibili nella maggior parte delle pagine in Finance and Operations. In particolare, le visualizzazioni sono attualmente disponibili per tutte le pagine a schermo intero ad eccezione dei dashboard e delle aree di lavoro. Inoltre, le pagine non a schermo intero, tra cui finestre di dialogo, finestre di dialogo a discesa, ricerche, anteprime avanzate, non supportano le visualizzazioni. È possibile che il supporto delle visualizzazioni per ulteriori tipi di pagine, ad esempio aree di lavoro e finestre di dialogo, sia preso in considerazione per un aggiornamento futuro.   

### <a name="who-is-allowed-to-publish-views"></a>A chi è consentito pubblicare visualizzazioni?
Attualmente gli amministratori di sistema sono i soli utenti che dispongono dei diritti di pubblicazione di visualizzazioni.  È in fase di ideazione un nuovo ruolo di sicurezza, che fornirebbe ai clienti maggiore flessibilità in relazione alla pubblicazione.  

### <a name="why-am-i-not-able-to-save-filters-with-this-view"></a>Perché non è possibile salvare filtri con una visualizzazione? 
Non è possibile salvare filtri con una visualizzazione per vari motivi: 

- La pagina può non supportare il salvataggio di filtri nella definizione della visualizzazione. Da notare che solo le pagine con grandi selettori di visualizzazioni consentono il salvataggio di personalizzazioni e modifiche di query come visualizzazioni. Per ulteriori informazioni, vedere la sezione "Passaggio da una visualizzazione all'altra". 

- Se la visualizzazione è quella predefinita e il percorso di navigazione alla pagina include una query, la query della visualizzazione potrebbe non essere applicata inizialmente. I due scenari principali sono: 
     - Se si passa da un riquadro a una pagina, la query del riquadro verrà eseguita indipendentemente dalla query associata alla visualizzazione predefinita. 
     - Se si accede a una pagina e quel punto di ingresso include una query, la query originale verrà eseguita al posto della query della visualizzazione predefinita. 
     
  In questo caso, un messaggio informativo verrà visualizzato durante il caricamento della visualizzazione. È inoltre possibile confermare passando a questa visualizzazione dopo il caricamento della pagina, in quanto la visualizzazione della query dovrebbe essere eseguita.  

- La pagina in questione potrebbe non supportare le visualizzazioni correttamente in quanto può ignorare del tutto la query della visualizzazione. Segnalare tali istanze mediante il meccanismo **Feedback**. Per accedere alla pagina del feedback, fare clic su **Guida e supporto tecnico** e **Feedback**.  
