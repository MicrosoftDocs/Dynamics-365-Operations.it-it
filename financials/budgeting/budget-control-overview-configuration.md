---
title: Panoramica del controllo del budget
description: Questo articolo introduce il concetto di controllo del budget e fornisce informazioni per semplificare la configurazione del controllo del budget in Microsoft Dynamics 365 for Operations in modo che sia possibile gestire le risorse finanziarie.
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 60493
ms.assetid: be964167-43bc-431d-9adb-48bff32d68d5
ms.search.region: Global
ms.author: sigitac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: 4caef8eb4d11ad5d2ba1ce0e23d869c0b26b5466
ms.contentlocale: it-it
ms.lasthandoff: 04/25/2017


---

# <a name="budget-control-overview"></a>Panoramica del controllo del budget

[!include[banner](../includes/banner.md)]


Questo articolo introduce il concetto di controllo del budget e fornisce informazioni per semplificare la configurazione del controllo del budget in Microsoft Dynamics 365 for Operations in modo che sia possibile gestire le risorse finanziarie.

<a name="overview"></a>Panoramica
--------

Il controllo del budget in Microsoft Dynamics 365 for Operations supporta la gestione delle risorse finanziarie di un'organizzazione tramite il piano dei conti, i flussi di lavoro, i gruppi di utenti, i documenti di origine e i giornali di registrazione, il calcolo configurabile dei fondi disponibili, i cicli di budget e le soglie. Se i controlli sono sul posto, un'organizzazione può programmare, misurare, gestire e programmare le risorse finanziarie nel corso dell'anno fiscale. 

Dopo che i budget sono stati approvati in Dynamics 365 for Operations, utilizzando i piani di budget è possibile generare le voci del registro di budget per registrare il budget di spesa per un'organizzazione. In alternativa è possibile creare o importare le voci del registro di budget da un'applicazione di terze parti senza utilizzare la funzionalità di pianificazione del budget. 

Le spese possono essere registrate utilizzando i conti principali e le dimensioni finanziarie. Il controllo del budget complessivo di spesa può essere configurato in base ai criteri e ai requisiti dell'organizzazione, raggruppando combinazioni di dimensioni finanziarie e conti principali. 

Nel seguente diagramma viene illustrata la posizione del controllo del budget nelle fasi di un ciclo di budget tipico.

[![Ciclo di budget](./media/budgetingcycle-300x198.png)](./media/budgetingcycle.png) 

È possibile configurare il controllo del budget in base a diversi fattori:

-   **Dimensioni finanziarie** - Quali dimensioni finanziarie devono essere utilizzate per la dichiarazione del budget e dei valori effettivi e quali dimensioni finanziarie sono necessarie per controllare il budget? Alcune combinazioni specifiche di dimensioni o alcuni conti principali hanno bisogno di un'attenzione specifica? Ad esempio, è presente un requisito per tenere traccia dei valori effettivi del budget in base al centro di costo e al programma? Le spese di viaggio necessitano di attenzione speciale?
-   **Tempo** - Quale periodo di tempo (periodo fiscale, periodo fiscale fino alla data odierna e così via) verrà utilizzato per valutare i fondi budget disponibili?
-   **Documenti di origine**: quali documenti di origine devono essere valutati per il controllo del budget? I documenti devono essere valutati per riga o per documento?
-   **Calcolo dei fondi disponibili** - I documenti quali richieste di acquisto (impegno preliminare di spesa) e ordini fornitore (impegni di spesa) devono essere considerati nel calcolo dei fondi disponibili? I documenti in stato di bozza devono essere considerati nel calcolo?
-   **Autorizzazione di sostituzione** - Chi ha l'autorizzazione a superare il budget disponibile?

Il controllo del budget è completamente integrato in Dynamics 365 for Operations. Di conseguenza, è possibile valutare la disponibilità di budget sia per acquisti pianificati che per acquisti effettivi. Sono disponibili sia richieste di informazioni che report sul budget. Di conseguenza, gli utenti possono valutare il budget nel ciclo di budget e apportare le rettifiche richieste sotto forma di revisioni o trasferimenti di budget. Un responsabile budget può esportare il budget e i valori effettivi in Microsoft Excel per analizzare e prevedere meglio i dati, in base alle esigenze.

## <a name="configuring-budget-control"></a>Configurazione del controllo del budget
### <a name="budget-cycle-time-span"></a>Durata ciclo di budget

Dopo aver configurato l'impostazione del budget di base, è possibile definire il tempo o il periodo iniziale e finale per l'impostazione e il controllo del budget nella pagina **Durata ciclo di budget**. I cicli di budget spesso corrispondono ai calendari fiscali ma possono estendere gli anni fiscali.

I passaggi successivi della configurazione vengono completati nelle diverse schede della pagina **Configurazione controllo del budget**.

### <a name="define-parameters"></a>Definisci parametri

In base alle dimensioni finanziarie abilitate per il budget, è possibile utilizzare tutte le dimensioni finanziarie o un sottoinsieme di esse per il controllo del budget. 

Inoltre, è possibile specificare l'intervallo di tempo predefinito (ad esempio **Anno fiscale**, **Anno fiscale al**, **Periodo fiscale** o **Trimestrale**) in cui il controllo del budget verrà eseguito nella durata ciclo di budget correlata. È inoltre possibile specificare identificare un responsabile e una soglia predefiniti del budget da utilizzare per informare gli utenti quando la soglia è stata raggiunta. I valori in questi campi verranno utilizzati come valori predefiniti in qualsiasi nuova regola di controllo del budget o gruppo di budget creato. Tuttavia, i valori predefiniti possono essere modificati per i singoli gruppi o regole. 

Le modalità secondo cui i budget vengono creati e registrati nel registro di budget consentono di determinare l'intervallo di tempo selezionato per valutare i fondi budget disponibili. Se è stato sviluppato e utilizzato un importo annualizzato per una combinazione di valori di dimensione, può avere senso un metodo basato su anno fiscale o anno fiscale fino a oggi. Tuttavia, se un'organizzazione che crea budget per periodo fiscale o alloca a periodi fiscali desidera un controllo più dettagliato, può considerare intervalli di tempo trimestrali o periodo fiscale fino a oggi. 

Inoltre, la lingua di un'organizzazione in relazione all'impostazione del budget e al controllo del budget consente anche di definire la configurazione.

### <a name="over-budget-permissions"></a>Autorizzazioni oltre il budget

Successivamente, nella scheda **Autorizzazioni oltre il budget** è possibile specificare i gruppi di utenti. È inoltre possibile specificare se gli utenti che sono membri di un gruppo dispongono dell'autorizzazione a superare il budget. È possibile impedire agli utenti di superare il budget che ha superato la soglia del budget impostata nella pagina **Parametri budget** oppure è possibile impedire loro di superare il budget di qualsiasi importo, indipendentemente dalla soglia. In base alla dinamicità con cui un'organizzazione gestisce le spese, queste autorizzazioni possono contribuire a gestire le risorse finanziarie. 

### <a name="budget-funds-available"></a>Fondi budget disponibili

Nella scheda **Fondi budget disponibili** è possibile definire la formula da utilizzare per calcolare i fondi budget disponibili. A seconda della prudenza usata da un'organizzazione per gestire le proprie risorse finanziarie o dei regolamenti o dei requisiti del settore, il calcolo può includere documenti in bozza o non registrati. 

> [!NOTE] 
> Se il calcolo viene modificato durante il ciclo di budget, le modifiche non interessano i documenti che precedentemente hanno superato le verifiche del controllo del budget e sono stati registrati o completati.

### <a name="documents-and-journals"></a>Documenti e giornali di registrazione

Successivamente, nella pagina **Documenti e giornali di registrazione** è possibile selezionare i documenti di origine e i giornali di registrazione che saranno soggetti alle verifiche del controllo del budget e se le verifiche vengono eseguite all'immissione della riga o per l'intero documento. 

È consigliabile abbinare i documenti di origine selezionati con le caselle di controllo per i saldi inclusi nel calcolo dei fondi budget disponibili. Ad esempio, se si seleziona **Prenotazioni budget per gli impegni di spesa**, è necessario selezionare l'opzione **Ordini fornitore**. Quando viene eseguita una verifica del budget per gli importi e i conti in una riga acquisto, la categoria di controllo del budget assegnata alla prenotazione è **Impegno di spesa**. Quando viene eseguita una verifica del budget per gli importi e i conti in una richiesta di acquisto, la categoria di controllo del budget assegnata alla prenotazione è **Impegno preliminare di spesa**. 

Se **Prenotazioni budget per impegni di spesa** e/o **Prenotazioni budget per impegni preliminari di spesa** sono inclusi nel calcolo dei fondi budget disponibili e devono essere riflessi tramite le registrazioni nella contabilità generale, la contabilità per impegni di spesa deve essere attivata nella pagina **Parametri di contabilità generale**.  

### <a name="assign-budget-models"></a>Assegna modelli di budget

Successivamente, nella scheda **Assegna modelli di budget** assegnare i modelli di budget agli intervalli di durata ciclo di budget da includere nel controllo del budget.

### <a name="define-budget-control-rules"></a>Definisci regole di controllo del budget

Successivamente nella scheda **Definisci regole di controllo del budget**, è necessario creare le regole specifiche in base alle dimensioni finanziarie abilitate dal controllo del budget. Ad esempio, se l'attenzione è relativa alla spesa o all'intervallo di spese per un reparto, è possibile utilizzare le impostazioni presenti in questa scheda per definire e valutare tali spese. Soglie diverse possono essere definite per ogni regola di controllo del budget. 

> [!Important]
> Il controllo del budget verrà attivato per qualsiasi conto principale del tipo **Profitti e perdite**, **Spese**, **Ricavi, Stato patrimoniale, Passività, Capitale netto** o **Cespite**. Se questa scheda contiene una regola con criteri vuoti, il controllo del budget verrà abilitato per **tutte**le combinazioni di dimensioni finanziarie contenenti i conti principali per tali tipi. Pertanto è importante creare regole di controllo del budget che definiscono solo gli intervalli delle combinazioni di dimensioni finanziarie per cui è importante attivare il controllo del budget.  

### <a name="select-main-accounts"></a>Seleziona conti principali

Se **Conto principale** non è selezionato come dimensione di controllo del budget nella pagina **Definisci parametri**, ma vengono gestite spese specifiche, è possibile selezionarle nella scheda **Seleziona conti principali**. Se **Conto principale** viene selezionato come dimensione di controllo del budget, non è richiesta alcuna voce.  

### <a name="define-budget-groups"></a>Definisci i gruppi di budget

Successivamente, nella scheda **Definisci gruppi di budget** è possibile facoltativamente definire le combinazioni univoche di dimensioni finanziarie in cui le risorse di budget vengono riunite per un controllo del budget secondario. È possibile creare un singolo record contenente l'intera organizzazione o definire più gruppi per rappresentare i diversi reparti o centri di costo.  

### <a name="define-message-levels"></a>Definisci livelli messaggio

Se i messaggi di avviso relativi al controllo del budget devono essere eliminati per tutti i gruppi di utenti, è possibile specificare tali gruppi nella pagina **Definisci livelli messaggio**. I membri dei gruppi di utenti continueranno a ricevere messaggi di errore quando i fondi di budget vengono superati in base alle autorizzazioni di budget superato.

### <a name="activate-budget-control"></a>Attiva controllo del budget

Dopo che il controllo del budget è stato configurato, è possibile attivarlo nella scheda **Attiva controllo del budget**. La versione bozza diventerà effettiva.
> [!Important]
> Dopo che il controllo del budget è abilitato e attivo e le transazioni vengono registrate, non deve essere disabilitato a metà anno. Quando il controllo del budget è disattivato, le attività non vengono registrate ai fini del controllo del budget e le verifiche del budget non vengono più eseguite. Di conseguenza, i documenti già registrati potrebbero non riflettere correttamente alcuni importi o saldi di sblocco in richieste di informazioni e report correlati al controllo del budget. Questi includono le statistiche di controllo del budget per qualsiasi attività downstream o rettifica di documenti e giornali di registrazione. 

Inoltre, si noti che le transazioni, ad esempio le voci del registro di budget, registrate prima dell'attivazione del controllo del budget non vengono considerate per il controllo del budget. Pertanto si consiglia cui di attivare il controllo del budget solo all'inizio di un nuovo ciclo di budget. Verificare che le voci del registro di budget che contengono i saldi iniziali del budget per il controllo del budget ottengano i saldi budget aggiornati solo dopo l'attivazione del controllo del budget. Qualsiasi documento aperto (ad esempio, un ordine fornitore) verrà verificato per il controllo dei fondi di budget disponibili e otterrà una prenotazione budget per il controllo del budget, quando l'utente manualmente attiva la verifica del controllo del budget nel documento.

## <a name="using-budget-control"></a>Utilizzo del controllo del budget
Una volta che il controllo del budget è abilitato, gli utenti riceveranno i messaggi di avviso e di errore del controllo del budget nei documenti e nei giornali di registrazioni configurati per il controllo del budget. Si tenga presente che è possibile configurare il controllo del budget in modo che gli utenti vengano avvisati quando superano i fondi di budget, ma che possano sempre continuare a confermare o registrare la transazione. Gli utenti possono visualizzare i dettagli delle verifiche del budget nella pagina **Errori e avvisi di controllo del budget**.   

Da questa pagina l'utente può espandere la pagina **Statistiche di controllo del budget per periodo** per visualizzare i dettagli di disponibilità e le prenotazioni di budget per la combinazione selezionata di dimensioni di controllo del budget. Gli utenti possono inoltre accedere alla pagina **Statistiche di controllo del budget**in cui la disponibilità del budget viene visualizzata per tutte le combinazioni di dimensioni finanziarie utilizzate nel controllo del budget. 

Se il controllo del budget è attivato per gli ordini fornitore, il responsabile budget può utilizzare l'area di lavoro **Budget contabili e previsioni** per verificare la coda di tutti gli ordini fornitore non confermati con errori e avvisi di verifica budget. Se il responsabile budget dispone delle autorizzazioni per superare il budget, può confermare l'ordine fornitore direttamente nell'area di lavoro.    




