---
title: Visualizzazioni salvate
description: In questo argomento viene descritto come utilizzare le funzionalità relative alle visualizzazioni salvate.
author: jasongre
ms.date: 05/17/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2019-07-31
ms.dyn365.ops.version: Platform update 28
ms.openlocfilehash: 8a5daee72f4f339fbebffb5c1d64814959775340
ms.sourcegitcommit: 13fa6385d8f3bb18df5a52fd2b0f4ad3484ad0ba
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/17/2021
ms.locfileid: "6050558"
---
# <a name="saved-views"></a>Visualizzazioni salvate

[!include [banner](../includes/banner.md)]


## <a name="introduction"></a>Introduzione

La personalizzazione riveste un ruolo fondamentale in quanto consente ad utenti e organizzazioni di ottimizzare l'esperienza utente per soddisfare le relative esigenze. Per ulteriori informazioni sulla personalizzazione, vedere [Personalizzare l'esperienza utente](personalize-user-experience.md).

Con la personalizzazione tradizionale, gli utenti possono avere soltanto un singolo insieme di personalizzazioni per pagina. La funzionalità **Visualizzazioni salvate** espande la personalizzazione in vari modi importanti:

- Le visualizzazioni consentono agli utenti di avere molteplici insiemi di personalizzazione per modulo, a cui possono accedere rapidamente come necessario. Ciò consente a un utente di creare molteplici visualizzazioni ottimizzate di una pagina, dove ogni visualizzazione è stata adattata per soddisfare le esigenze di esecuzione di una particolare attività aziendale. 
- Le visualizzazioni create per specifici tipi di pagina possono anche includere filtri o ordinamenti aggiunti dagli utenti, che consentono agli stessi di ritornare rapidamente a set di dati filtrati comunemente. Vedere la sezione [Quali pagine supportano le visualizzazioni](saved-views.md#what-pages-support-views) per ulteriori informazioni. 
- Le visualizzazioni possono essere pubblicate per gli utenti con ruoli di sicurezza specifici e persone giuridiche specifiche. Pertanto, qualsiasi utente che ha un ruolo specifico e accesso a una determinata persona giuridica può accedere a tale visualizzazione e utilizzarla, anche se tale utente non dispone dell'autorizzazione per personalizzarla. Questa capacità di pubblicazione consente alle organizzazioni di definire visualizzazioni standard aziendali ottimizzate per le relative esigenze. Per ulteriori informazioni, vedere la sezione [Gestione delle personalizzazioni a livello organizzativo con visualizzazioni](saved-views.md#managing-personalizations-at-an-organizational-level-with-views).
- Diversamente dalla personalizzazione tradizionale, le visualizzazioni non vengono salvate automaticamente quando un utente esegue personalizzazioni o filtra un elenco. Sono necessari salvataggi espliciti per offrire agli utenti la flessibilità di creare una visualizzazione prima o dopo che sono state apportate le modifiche associate a quella visualizzazione. Questo requisito garantisce inoltre che le definizioni della visualizzazione non vengano modificate involontariamente da filtri o personalizzazioni che non sono destinati all'uso a lungo termine. Gli elementi che il sistema memorizza automaticamente come parte dell'utilizzo tipico della pagina (ad esempio, larghezza delle colonne o stato delle sezioni espanso o compresso) verranno salvati per visualizzazione.
- Le visualizzazioni possono essere aggiunte alle aree di lavoro come riquadri, elenchi o collegamenti. Pertanto, un set di dati filtrato può essere disponibile in un'area di lavoro e gli utenti possono associare un set di personalizzazioni rilevante per quel set di dati con un riquadro o collegamento.

## <a name="switching-between-views"></a>Passaggio da una visualizzazione all'altra

Dopo che le visualizzazioni sono state rese disponibili per un ambiente, qualsiasi pagina che supporta le visualizzazioni includerà un selettore di visualizzazioni compresso nella parte superiore del modulo che visualizza il nome della visualizzazione corrente.

Il selettore di visualizzazioni include due variazioni di dimensioni: 

- **Selettori di visualizzazioni grandi**: le pagine con un elenco avranno un selettore di visualizzazioni più grande per alcuni motivi. In particolare, il selettore di visualizzazioni più grande indica le pagine in cui la visualizzazione può includere filtri definiti dall'utente. Poiché i filtri sono inclusi nelle visualizzazioni, la dimensione più grande del selettore è anche garantita in quanto i nomi di visualizzazioni saranno spesso la migliore descrizione dei dati visualizzati sullo schermo e l'aspettativa è che gli utenti passeranno più spesso da una visualizzazione all'altra su questi tipi di pagine.
- **Selettori di visualizzazioni piccoli**: tutte le altre pagine a schermo intero (con l'eccezione delle aree di lavoro e del dashboard) hanno un selettore di visualizzazioni più piccolo visualizzato accanto al titolo della pagina. Le visualizzazioni in queste pagine includono solo personalizzazioni, non filtri definiti dall'utente. In queste pagine, il sottotitolo o titolo del record è in genere l'informazione più importante nella parte superiore della pagina. La dimensione più piccola del selettore della visualizzazione riflette inoltre una frequenza prevista di passaggio da una visualizzazione all'altra inferiore in queste pagine. 
 
Se si seleziona il nome della visualizzazione, viene aperto il selettore di visualizzazioni che visualizza l'elenco delle visualizzazioni disponibili per tale pagina.

- **Visualizzazione standard**: la visualizzazione **Standard** è la visualizzazione predefinita della pagina senza personalizzazioni esplicite applicate.
- **Visualizzazioni personali**: le visualizzazioni senza lucchetti rappresentano le visualizzazioni personali. Si tratta delle visualizzazioni create personalmente o ricevute da un amministratore.
- **Visualizzazioni bloccate**: alcune visualizzazioni, ad esempio la visualizzazione **Standard** e qualsiasi visualizzazione pubblicata nel ruolo, presentano un simbolo di un lucchetto accanto al selettore di visualizzazioni. Questo simbolo indica che non è possibile modificare le visualizzazioni. Tuttavia, le modifiche che riflettono l'utilizzo della pagina vengono salvate automaticamente. Queste modifiche includono modifiche alla larghezza di una colonna della griglia e modifiche allo stato espanso o compresso di una Scheda dettaglio. Tuttavia se si dispone di privilegi di personalizzazione è possibile creare una visualizzazione personale basata su una visualizzazione bloccata utilizzando l'azione **Salva con nome**.
- **Nuove visualizzazioni**: le visualizzazioni pubblicate che non sono state ancora aperte sono contrassegnate da una scintilla a sinistra del nome della visualizzazione.

Per passare a un'altra visualizzazione, innanzitutto aprire il selettore di visualizzazioni e selezionare la visualizzazione che si desidera caricare. 

## <a name="creating-and-modifying-views"></a>Creazione e modifica di visualizzazioni

A differenza della personalizzazione tradizionale, le visualizzazioni non vengono salvate automaticamente quando un utente personalizza la pagina o quando un utente applica un filtro a un elenco o lo ordina. Un'azione esplicita è necessaria per salvare le modifiche a una visualizzazione. Questo requisito offre agli utenti la flessibilità di creare una visualizzazione prima o dopo che sono state apportate le modifiche associate a quella visualizzazione. Assicura inoltre che le definizioni della visualizzazione non vengano modificate involontariamente da filtri o personalizzazioni occasionali. Si noti che gli elementi di utilizzo tipico della pagina (ad esempio, larghezza delle colonne o stato delle sezioni espanso o compresso) vengono salvati automaticamente nella visualizzazione corrente, anche pe rle visualizzazioni bloccate.

Per garantire che lo stato corrente della visualizzazione sia noto, quando si inizia a modificare una visualizzazione personalizzandola o filtrandola, un asterisco (\*) appare accanto al nome della visualizzazione corrente. Questo simbolo indica che si sta visualizzando una versione non salvata e modificata di quella visualizzazione.

Per salvare le modifiche, attenersi alla procedura seguente.

1. Selezionare il nome della visualizzazione per aprire il selettore di visualizzazioni.
2. Per modificare la visualizzazione esistente, selezionare **Salva**: Questa azione non è disponibile per le visualizzazioni bloccate. 
3. Per creare una nuova visualizzazione:

    1. Selezionare **Salva con nome**. 
    2. Immettere un nome di visualizzazione ed eventualmente una descrizione.
    3. Selezionare **Salva**.

## <a name="changing-the-default-view"></a>Modifica della visualizzazione predefinita

La visualizzazione predefinita è la visualizzazione che il sistema tenta di aprire quando si apre per la prima volta la pagina. Si consiglia di impostare la visualizzazione predefinita sulla visualizzazione che si prevede di utilizzare più spesso come visualizzazione predefinita. 

> [!NOTE]
> Esiste un'unica visualizzazione predefinita globale tra le aziende. Se si modifica la visualizzazione predefinita, tale visualizzazione verrà aperta per impostazione predefinita, indipendentemente dalla persona giuridica in cui ci si trova attualmente. 

Per cambiare la visualizzazione predefinita di una pagina, seguire questi passaggi:

1. Passare alla visualizzazione che si utilizza come visualizzazione predefinita. 
2. Selezionare il nome della visualizzazione per aprire il selettore di visualizzazioni. 
3. Selezionare **Altro** e **Aggiungi come predefinita**.

In alternativa, quando si crea una nuova visualizzazione (mediante l'azione **Salva con nome** ), è possibile impostare quella nuova visualizzazione come visualizzazione predefinita impostando l'opzione **Aggiungi come predefinita** prima di salvare la visualizzazione.

In alcuni casi, la query associata alla visualizzazione predefinita non viene eseguita quando si apre per la prima volta una pagina. Ad esempio, se si apre la pagina tramite un riquadro, la query del riquadro verrà eseguita indipendentemente dalla query associata alla visualizzazione predefinita. Inoltre, se si apre a una pagina con una visualizzazione **Standard** che ha già una query definita, la query originale verrà eseguita al posto della query della visualizzazione predefinita. In questo caso, riceverai un messaggio informativo al caricamento della visualizzazione. Se si cambia visualizzazione dopo che la pagina è stata caricata, è possibile eseguire la query di visualizzazione come previsto. A partire dalla versione 10.0.10, il messaggio informativo che si riceve avrà un'azione incorporata che consente di caricare direttamente la query della visualizzazione predefinita.

## <a name="managing-personal-views"></a>Gestione delle visualizzazioni personali

La finestra dialogo **Gestisci le mie visualizzazioni** fornisce funzionalità di gestione di base delle visualizzazioni personali e dell'ordine delle visualizzazioni nel selettore di visualizzazioni. Per aprire questa pagina, selezionare il nome della visualizzazione per aprire il menu a discesa del selettore di visualizzazioni, selezionare **Altro**, quindi selezionare **Gestisci le mie visualizzazioni**.

Per un elenco delle visualizzazioni disponibili per quella pagina, si ha a disposizione il set di azioni seguente.

- **Modificare la visualizzazione predefinita**: utilizzare l'azione **Aggiungi come predefinita** per impostare la visualizzazione attualmente selezionata come visualizzazione predefinita per la pagina.
- **Riordinare le visualizzazioni**: utilizzare le azioni **Sposta in alto** e **Sposta in basso** per organizzare le visualizzazioni secondo un ordine specifico.
- **Rinominare una visualizzazione**: utilizzare l'azione **Rinomina** per modificare il nome della visualizzazione personale attualmente selezionata. Questa azione è disattivata per le visualizzazioni bloccate. 
- **Eliminare una visualizzazione**: utilizzare l'azione **Elimina** per eliminare definitivamente la visualizzazione attualmente selezionata dalla pagina. Non è possibile ripristinare una visualizzazione rimossa.

Qualsiasi modifica apportata in questa finestra di dialogo diventerà effettiva dopo la selezione del pulsante **Salva**.

## <a name="managing-personalizations-at-an-organizational-level-with-views"></a>Gestione di personalizzazioni a livello organizzativo con visualizzazioni

Per informazioni su come le visualizzazioni salvate aiutano a migliorare la gestione delle personalizzazioni a livello organizzativo, questa sezione descrive alcune differenze nella gestione della personalizzazione con e senza la funzionalità **Visualizzazioni salvate**.

Senza le visualizzazioni, gli amministratori applicavano un insieme di personalizzazioni di una pagina a un utente, a un gruppo utenti o a utenti tramite la pagina Personalizzazione. Se tali utenti disponevano di diritti di personalizzazione, le personalizzazioni erano applicate a tale pagina. Tuttavia, non si aveva la possibilità di impedire agli utenti di personalizzare ulteriormente la pagina, di conseguenza l'organizzazione non era in grado di assicurare un'interfaccia utente coerente per gli utenti. Se uno di questi utenti non disponeva di diritti di personalizzazione, le personalizzazioni ad essi assegnate da un amministratore non venivano caricate. Inoltre, se un nuovo utente veniva assunto in un'organizzazione, gli amministratori dovevano caricare manualmente un insieme di personalizzazioni per l'utente. Non esisteva un meccanismo automatico per definire che un determinato set di personalizzazioni doveva essere disponibile in quel ruolo.

Con la funzionalità **Visualizzazioni salvate**, la gestione delle personalizzazioni a livello di organizzazione è molto più semplice, principalmente perché le visualizzazioni possono essere pubblicate nei gruppi di utenti. Dopo che una visualizzazione è stata pubblicata, qualsiasi utente che ha uno dei ruoli di sicurezza definiti e ha accesso a una delle persone giuridiche specificate sarà in grado di vedere e utilizzare la visualizzazione, anche se l'utente potrebbe non avere accesso alla personalizzazione. Sebbene ogni utente disponga di una copia della visualizzazione pubblicata in cui gli elementi di utilizzo della pagina vengono applicati automaticamente, nessun utente può salvare personalizzazioni o aggiornamenti della query in una visualizzazione pubblicata. In altre parole, le visualizzazioni pubblicate sono bloccate. Inoltre, se ai nuovi utenti vengono assegnati ruoli in persone giuridiche in cui sono state pubblicate le visualizzazioni, vedranno automaticamente le visualizzazioni associate ai loro ruoli e alle persone giuridiche. Nessuna azione aggiuntiva è richiesta dall'amministratore. Allo stesso modo, se gli utenti cambiano ruolo in un'organizzazione o ottengono l'accesso a diverse persone giuridiche, potrebbero non essere più in grado di accedere alle visualizzazioni precedentemente pubblicate per loro. Anche in questo caso, nessuna azione aggiuntiva è richiesta dall'amministratore.

Gli aggiornamenti a una visualizzazione pubblicata possono essere distribuiti facilmente agli utenti pubblicando di nuovo la visualizzazione su ruoli di sicurezza e persone giuridiche appropriati.

La capacità di pubblicazione consente alle organizzazioni di definire visualizzazioni standard aziendali ottimizzate per le relative esigenze e destinate ad utenti con specifici ruoli di sicurezza.

## <a name="publishing-views"></a>Pubblicazione di visualizzazioni

Durante il processo di pubblicazione, le visualizzazioni possono essere assegnate a uno o più ruoli di sicurezza per una o più persone giuridiche. Pertanto, qualsiasi utente con diritti di accesso a una persona giuridica che è assegnato a uno dei ruoli può accedere e utilizzare le visualizzazioni. Tuttavia, l'utente non può modificare le visualizzazioni. Per impostazione predefinita, gli amministratori di sistema possono accedere all'azione **Pubblica** nel menu a discesa del selettore di visualizzazioni. Tuttavia, anche altri utenti attendibili della tua organizzazione possono avere accesso alla pubblicazione della visualizzazione tramite il nuovo ruolo **Amministratore di visualizzazioni salvate**.

Per pubblicare una visualizzazione, attenersi alla procedura riportata di seguito:

1. Creare e salvare una copia personale della visualizzazione che si intende pubblicare. 
2. Con quella visualizzazione attualmente caricata, selezionare il nome della visualizzazione per aprire il menu a discesa del selettore di visualizzazioni. 
3. Selezionare il pulsante **Altro**, quindi selezionare **Pubblica**. Viene visualizzata la finestra di dialogo Pubblica.
4. Immettere un nome per la visualizzazione. Questo è il nome che gli utenti che ricevono la visualizzazione vedranno nei relativi selettori di visualizzazioni. I nomi delle visualizzazioni pubblicate per una pagina devono essere univoci. Non sono consentiti nomi duplicati, anche se l'elenco dei ruoli o delle persone giuridiche a cui le visualizzazioni sono applicate differisce.
5. **Aggiornamento 10.0.17 o successive:** se la funzionalità **(Anteprima) Supporto alla traduzione per le visualizzazioni dell'organizzazione** è attivata, è possibile aggiungere traduzioni per il nome della visualizzazione in tutte le lingue richieste dalla propria organizzazione selezionando il pulsante **Traduzioni** accanto al campo **Nome**. Il nome della visualizzazione verrà quindi mostrato agli utenti nella loro lingua corrente. È inoltre possibile impostare la lingua predefinita per specificare la traduzione che verrà mostrata agli utenti che utilizzano lingue per le quali non è definita alcuna traduzione.
5. Facoltativo: immettere una descrizione per la visualizzazione, in modo che gli utenti che ricevono questa visualizzazione possano comprenderne meglio lo scopo. 
6. Determinare se la visualizzazione deve essere pubblicata come visualizzazione predefinita per gli utenti selezionati. Quando una visualizzazione viene impostata come predefinita, gli utenti la vedranno la prossima volta che apriranno la pagina di destinazione. La visualizzazione predefinita globale singola di ogni utente interessato verrà modificata. Tuttavia, gli utenti possono comunque modificare la visualizzazione predefinita dopo la pubblicazione.

    > [!NOTE]
    > Tenere presente quanto segue quando si pubblica una visualizzazione come visualizzazione predefinita: 
    > -  Se si pubblica una visualizzazione come predefinita su tutte o alcune persone giuridiche, si modifica la visualizzazione predefinita singola **globale** di ogni utente interessato. 
    > -  Se un utente ha ruoli in cui più visualizzazioni vengono pubblicate come predefinite, l'ultima visualizzazione pubblicata verrà utilizzata come visualizzazione predefinita dell'utente. 

8. Aggiungere i ruoli di sicurezza corrispondenti agli utenti che sono interessati da questa visualizzazione. 
9. Determinare se si desidera pubblicare la visualizzazione nei ruoli figlio di ciascun ruolo di sicurezza selezionato. In tal caso, selezionare la casella di controllo **Includi ruoli figlio** nella riga per i ruoli di sicurezza appropriati. Questa casella di controllo non è disponibile per i ruoli che non hanno ruoli figlio.
10. Aggiungere le persone giuridiche per cui la visualizzazione deve essere disponibile. 

    > [!NOTE]
    > Tenere presente le seguenti aspettative quando si pubblica una visualizzazione per una persona giuridica.
    > 
    > Se si pubblica una visualizzazione su una persona giuridica, ma non la si pubblica come visualizzazione predefinita, gli utenti inizialmente vedranno la visualizzazione nel selettore solo per le persone giuridiche specificate. Tuttavia, dopo che la visualizzazione è stata caricata per la prima volta, sarà sempre nel selettore di visualizzazioni dell'utente per quella pagina, indipendentemente dalla persona giuridica.

11. Selezionare **Pubblica**

Da notare che in alcuni ambienti la visualizzazione pubblicata sarà visibile solo dopo un certo tempo (fino a un'ora).

 

## <a name="modifying-a-published-view"></a>Modifica di una visualizzazione pubblicata

Dopo aver pubblicato una visualizzazione, potrebbe essere necessario modificarla. Sebbene non sia possibile apportare modifiche in tempo reale a una visualizzazione pubblicata, in quanto la modifica di tali visualizzazioni è bloccata per tutti gli utenti (inclusi gli editori), è possibile pubblicare di nuovo una visualizzazione per aggiornarla.

Se le modifiche che si desidera apportare a una visualizzazione pubblicata sono relative solo ai parametri di pubblicazione (il nome e la descrizione della visualizzazione o i ruoli di sicurezza su cui la visualizzazione è pubblicata), procedere come segue:

1. Passare alla visualizzazione pubblicata per i parametri che si desidera aggiornare. 
2. Selezionare **Ripubblica** dal menu a discesa del selettore di visualizzazioni. Se si utilizza la versione 10.0.12 o precedente, è necessario selezionare **Pubblica** e poi **Sì** per aggiornare la visualizzazione esistente.
3. Aggiornare il nome, la descrizione, i ruoli di sicurezza e le persone giuridiche della visualizzazione. 
4. Selezionare **Pubblica** Se in origine è stata selezionata questa visualizzazione pubblicata come visualizzazione predefinita, sarà nuovamente la visualizzazione predefinita per gli utenti dopo averla ripubblicata. 

Se le modifiche apportate alla visualizzazione pubblicata comportano la modifica delle personalizzazioni o dei filtri associati alla visualizzazione, procedere come segue:

1. Caricare la visualizzazione pubblicata che si desidera modificare. 
2. Apportare le modifiche necessarie alla bozza locale.
3. Selezionare **Ripubblica** dal menu a discesa del selettore di visualizzazioni.
4. Selezionare **Sì** per indicare che si desidera pubblicare la visualizzazione insieme alle modifiche non salvate. 
5. Regolare tutti i parametri di pubblicazione che richiedono una regolazione, quindi selezionare **Pubblica**. 

## <a name="managing-published-views"></a>Gestione di visualizzazioni pubblicate

Come per la gestione delle visualizzazioni personali, la finestra di dialogo **Gestisci le mie visualizzazioni** fornisce agli utenti funzionalità di gestione di base dei privilegi di pubblicazione per le visualizzazioni pubblicate delle pagine (oltre che per le visualizzazioni personali). Per aprire questa pagina, selezionare il nome della visualizzazione per aprire il menu a discesa del selettore di visualizzazioni, selezionare **Altro**, quindi selezionare **Gestisci le mie visualizzazioni**.

Sebbene tutti gli utenti dispongano di una scheda **Visualizzazioni personali** che elenca le visualizzazioni personali, gli utenti con privilegi di pubblicazione dispongono anche di una scheda **Visualizzazioni organizzazione** che mostra tutte le visualizzazioni pubblicate e non pubblicate per tale pagina. Poiché è possibile che vi siano vari utenti che pubblicano visualizzazioni, è importante poter gestire l'elenco completo delle visualizzazioni pubblicate, indipendentemente se si è l'utente che ha effettivamente pubblicato la visualizzazione.

Per l'elenco di tutte le visualizzazioni pubblicate per la pagina, si ha a disposizione il set di azioni seguente. 

- **Ripubblica**: utilizzare l'azione **Ripubblica** per pubblicare di nuovo una visualizzazione dopo che i parametri di pubblicazione (nome, Descrizione, ruoli di sicurezza o persone giuridiche) sono stati modificati.
- **Pubblica**: utilizzare l'azione **Pubblica** per pubblicare una visualizzazione attualmente non pubblicata. 
- **Annulla pubblicazione**: utilizza l'azione **Annulla pubblicazione** per rendere inattiva una visualizzazione. La visualizzazione sarà ancora disponibile nel sistema, ma gli utenti non la vedranno nel selettore di visualizzazione fino a quando non verrà nuovamente pubblicata.
- **Salva come personale**: utilizzare l'azione **Salva come personale** per creare una bozza personale della visualizzazione pubblicata. Questa funzionalità consente di comprendere i contenuti di una visualizzazione non pubblicata o che non è stata ancora pubblicata. È possibile usarla per modificare e quindi ripubblicare una visualizzazione.
- **Elimina**: utilizzare l'azione **Elimina** per eliminare definitivamente una visualizzazione pubblicata o con pubblicazione annullata. Questa azione rimuove anche la visualizzazione per tutti gli utenti del sistema. La rimozione delle visualizzazione pubblicate avrà effetto dopo la selzione del pulsante **Salva**. Una volta eliminata, una visualizzazione non può essere recuperata. 

## <a name="managing-views-globally"></a>Gestire globalmente le visualizzazioni

Sebbene alcune funzionalità di gestione siano presenti in ogni pagina, come indicato in questo argomento, gli **amministratori di sistema** e gli **amministratori di visualizzazioni salvate** possono gestire le visualizzazioni in modo più olistico per il sistema tramite la pagina **Personalizzazione**. In particolare, questa pagina presenta le seguenti sezioni e funzionalità: 

- **Visualizzazioni pubblicate** - Questa sezione elenca tutte le visualizzazioni che sono state pubblicate per l'organizzazione. Da qui, è possibile ripubblicare una visualizzazione dopo aver modificato i ruoli di sicurezza o le persone giuridiche a cui è destinata la visualizzazione. È possibile anche esportare, eliminare o annullare la pubblicazione di queste visualizzazioni. È possibile utilizzare l'azione **Salva come personale** per creare una copia personale della visualizzazione, in modo da poter aggiornare la visualizzazione o ottenere una migliore comprensione del relativo contenuto. 
- **Visualizzazioni non pubblicate**: questa sezione elenca tutte le visualizzazioni dell'organizzazione nel tuo sistema che non sono attualmente pubblicate. Queste visualizzazioni vengono spesso inserite nel sistema tramite la funzionalità di importazione. È possibile pubblicare, esportare o eliminare queste visualizzazioni. L'azione **Pubblicazione rapida** aggiunta nella versione 10.0.12 consente di pubblicare più visualizzazioni da questa sezione in un'unica azione, utilizzando il ruolo di sicurezza esistente e le configurazioni della persona giuridica. È possibile utilizzare l'azione **Salva come personale** per creare copie personali di queste visualizzazioni, in modo da ottenere una migliore comprensione del relativo contenuto.
- **Visualizzazioni personali** - Questa sezione elenca tutte le visualizzazioni che sono state create dagli utenti nel sistema. Da qui, è possibile pubblicare una visualizzazione personale nell'organizzazione o copiare una o più visualizzazioni per altri utenti. È anche possibile esportare o eliminare queste visualizzazioni, secondo le necessità.
- **Impostazioni utente**: selezionare un utente da visualizzare o regolare la capacità dell'utente di utilizzare la personalizzazione per l'intero sistema o per pagine specifiche che l'utente ha visitato. È possibile visualizzare e interagire con le personalizzazioni dell'utente nel sistema. Puoi anche eliminare tutte le personalizzazioni per quell'utente o ripristinare i callout delle funzionalità per l'utente. Se i callout della funzionalità vengono reimpostati, e l'utente ha precedentemente ignorato una finestra popup che introduce nuove funzionalità, questa viene di nuovo visualizzata la volta successiva che l'utente rileva tali funzionalità.
- **Impostazioni di sistema** - È possibile disattivare temporaneamente la personalizzazione per tutti gli utenti nel sistema. In questo caso, non vengono applicate personalizzazioni agli utenti e tutte le pagine vengono reimpostate allo stato predefinito. Se si attivano nuovamente le personalizzazioni in un secondo momento, queste vengono applicate nuovamente. È inoltre possibile eliminare in modo permanente tutte le personalizzazioni per tutti gli utenti nel sistema. Le personalizzazioni che sono state eliminate non possono essere recuperate. Pertanto, prima di eseguire questa attività, assicurarsi di esportare tutte le personalizzazioni che si desidera importare successivamente.

Gli utenti che hanno accesso alla pagina **Personalizzazione** possono anche importare le visualizzazioni dell'organizzazione o personali tramite il pulsante **Importa visualizzazioni** nel riquadro azioni. Per le visualizzazioni dell'organizzazione, puoi selezionare **Pubblica immediatamente** per rendere le visualizzazioni disponibili agli utenti senza un'ulteriore pubblicazione esplicita.

## <a name="known-issues"></a>Problemi noti
Per un elenco di problemi noti con le visualizzazioni salvate, vedere [Creare moduli che utilizzano appieno le visualizzazioni salvate](../../dev-itpro/user-interface/understanding-saved-views.md).

## <a name="frequently-asked-questions"></a>Domande frequenti

### <a name="how-do-i-enable-saved-views-in-my-environment"></a>Come si abilitano le visualizzazioni salvate nel proprio ambiente?

> [!NOTE]
> Nota: la funzionalità **Visualizzazione salvate** richiede il sistema di personalizzazione in Finance and Operations per essere abilitata. Se la personalizzazione è disattivata per l'intero ambiente, le visualizzazioni verranno disabilitate anche se si esegue la procedura seguente. 

Puoi attivare e disattivare la funzionalità **Visualizzazioni salvate** tramite la gestione delle funzionalità in qualsiasi ambiente. Dopo l'attivazione, le visualizzazioni salvate verranno abilitate in tutte le sessioni utente successive.

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

Per le pagine con grandi selettori di visualizzazione (personalizzazioni e query possono essere salvate nella visualizzazione), saranno visibili principalmente i dati collegati alla query associata alla visualizzazione predefinita. Esistono due eccezioni principali:

- Se si passa da un riquadro a una pagina, la query del riquadro verrà eseguita indipendentemente dalla query associata alla visualizzazione predefinita. Se quel riquadro è stato creato dopo aver abilitato le visualizzazioni, la selezione di un riquadro aprirà la pagina con la visualizzazione associata a quel riquadro.
- Se si accede a una pagina e quel punto di ingresso include una query, la query originale verrà eseguita al posto della query della visualizzazione predefinita. Quando ciò avviene, si verrà avvisati mediante un messaggio informativo durante il caricamento della visualizzazione. È inoltre possibile confermare passando a questa visualizzazione dopo il caricamento della pagina, in quanto la visualizzazione della query dovrebbe essere eseguita.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
