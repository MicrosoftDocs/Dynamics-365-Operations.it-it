---
title: Area di lavoro chiusura periodo finanziario
description: Questo articolo fornisce una panoramica dell&quot;area di lavoro Chiusura periodo finanziario e della configurazione collegata.
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: LedgerPeriodCloseProjectWorkspace
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 13791
ms.assetid: 6ee51758-639b-448e-9cb2-56cf1d804273
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 114dee90b0fe525f0b3efabbf651d2804a22dd7d
ms.openlocfilehash: ba0d709d123f56edb2a5287376c06c1f41181b1c
ms.lasthandoff: 03/31/2017


---

# <a name="financial-period-close-workspace"></a>Area di lavoro chiusura periodo finanziario

Questo articolo fornisce una panoramica dell'area di lavoro Chiusura periodo finanziario e della configurazione collegata.

Area di lavoro chiusura periodo finanziario

** Finanziaria Chiusura del periodo ** l'area di lavoro consente di tenere traccia dei processi finanziari di chiusura tra più società, le aree e le persone. A seconda della visualizzazione ** finanziaria di chiusura periodo ** dell'area di lavoro, vedrete di tutte le attività e stati di una programmazione di chiusura, o solo delle attività assegnate all'utente. 

È innanzitutto necessario selezionare uno scadenzario chiusura nella parte superiore dell'area di lavoro. Tutti i dati visualizzati nell'area di lavoro vengono filtrati in base alla programmazione di chiusura selezionata.

### <a name="summary-tiles"></a>Sezioni Riepilogo

Le sezioni **Riepilogo** forniscono una panoramica del processo e alcuni indicatori consentono di tenere traccia del processo di chiusura. È possibile visualizzare le attività che sono attività scadute e rimanenti dalla data odierna, eseguire attività di oggi ma è bloccato a causa delle dipendenze e di tutte le attività rimanenti per il processo. Questa informazione viene utilizzata per tutte le società incluse nella programmazione di chiusura selezionata.

### <a name="tasks-and-status-section"></a>Sezione Attività e stati

** Attività e lo stato ** nell'area, lo stato della programmazione generale di chiusura viene suddiviso in diversi modi: lo stato dalla società, lo stato per area e lo stato dalla persona responsabile. È possibile visualizzare lo stato di tutte le attività nella programmazione di chiusura, solo le attività da oggi dovuto, o le attività già scadute modificando il filtro nella parte superiore dell'elenco della scheda. È inoltre possibile selezionare il filtro della società per visualizzare lo stato per una società specifica. In ciascuna scheda dello stato da una scomposizione sia dalla percentuale che è stata completata sia per numero di attività rimanenti. Fare clic sulla scheda o ** consente di visualizzare i ** l'azione per filtrare l'elenco dettagliato attività della scheda selezionata. 

Ultima scheda è per l'elenco dettagliato attività. Questo elenco viene visualizzato l'elenco completo attività e può essere filtrate in modo da indicare solo per le attività desiderata. È possibile filtrare l'elenco attività in vari modi. Ad esempio, è possibile filtrare la compensazione di attività, dalla società associata e dall'area collegata. È inoltre possibile selezionare per visualizzare o nascondere le attività completate nell'Elenco attività. 

Due indicatori vengono utilizzati per le attività:

-   L'icona del punto esclamativo indica che l'attività è scaduta. Per le attività già scadute, la data di scadenza viene evidenziata in rosso.
-   Un'icona di un lucchetto indica che l'attività dipende da altre attività non ancora completate. Un'attività che viene bloccata dalle dipendenze non può essere contrassegnata come completata. È possibile impostare le dipendenze per un'attività utilizzando ** ** Il valore dell'azione.

Nome dell'attività è un collegamento ipertestuale in Microsoft Dynamics 365 per la pagina di operazioni o altre pagine Web visualizzate in cui l'utente deve accedere completare il lavoro. È possibile impostare il collegamento ipertestuale utilizzando ** collegamento di attività ** liquidate quando si modificano o si crea un'attività. 

È possibile collegare i file, note, immagini e URL un'attività utilizzando ** collegati ** l'azione. Ad esempio, è possibile indicare i numeri di giornale di registrazione utilizzati come parte di un'attività, aggiungere commenti su un'attività specifica, o collega un file di report stampato per un'attività. Un'icona viene visualizzato ** collegato ** nella colonna per l'attività se un allegato è presente. 

** Attività completa ** l'opzione deve essere selezionata anche manualmente dopo che l'attività è stata completata. Quando un'attività è contrassegnata come completata, ** data completata ** il campo viene aggiornato automaticamente alla data corrente e all'ora. Gli indicatori di dipendenza inoltre aggiornati in base alle proprie esigenze.

## <a name="all-financial-period-close-tasks-list-page"></a>Pagina di elenco Tutte le attività di chiusura periodo finanziario
È possibile visualizzare tutte le attività correnti e precedenti di chiusura periodo ** tutte le attività finanziarie di chiusura periodo ** dalla pagina elenco. Questa pagina elenco viene utilizzata Consumo consigliato per l'analisi dello storico del processo di chiusura, poiché include informazioni sulla fine programmata, la data di completamento effettivo e sulla persona che ha completato l'attività. È possibile esportare facilmente le informazioni su questa pagina elenco in Microsoft Excel per i report e motivi di controllo.

## <a name="financial-period-close-configuration-page"></a>Pagina Configurazione chiusura periodo finanziario
Per poter utilizzare ** finanziaria di chiusura periodo ** l'area di lavoro, è necessario configurare il processo in Microsoft Dynamics 365 per le operazioni mediante ** configurazione finanziaria di chiusura periodo ** la pagina. Fare clic su ** contabilità generale ** &gt; ** periodo di chiusura ** &gt; ** configurazione finanziaria di chiusura periodo **).

### <a name="resources"></a>Risorse

** Risorse ** nella scheda, definite le persone che sono coinvolte nei processi di chiusura. Tutto il dipendente responsabile dell'attività di chiusura deve prima essere assegnato in questo campo. È inoltre necessario specificare il punto di vista del dipendente dell'area di lavoro. Sono disponibili le seguenti opzioni:

-   **Solo attività assegnate** - L'utente visualizzerà solo le attività a lui assegnate.
-   **Tutte le attività e tutti gli stati** - L'utente visualizzerà tutte le attività di chiusura e lo stato del processo complessivo.

Gli utenti autorizzati a visualizzare solo le attività assegnate a loro non potranno aggiungere attività all'elenco delle attività, modificare o rimuovere attività dall'elenco delle attività.

### <a name="task-areas"></a>Aree attività

Le aree di attività si utilizzano per raggruppare attività di chiusura in aree logiche di proprietà all'interno dell'organizzazione. Ad esempio, i gruppi Contabilità fornitori, Contabilità clienti, o Contabilità generale possono essere utilizzati come aree di attività.

### <a name="calendars"></a>Calendari

Consente di creare e modificare i calendari finanziari di chiusura utilizzando la scheda dei calendari.  Questa impostazione corrisponde a definirete i giorni lavorativi per i processi di chiusura e verrà utilizzata per la programmazione delle attività di chiusura.  Creare un nuovo calendario e specificare i giorni lavorativi da utilizzare per la programmazione delle attività.  È preferibile creare un calendario del lungo termine, ad esempio un anno o più anni, poiché può essere modificata dopo la creazione.  Dopo avere creato il calendario, fare clic sul pulsante di modifica per aggiornare il calendario per giorni specifici, ad esempio festività.  Le attività di chiusura verranno programmate i giorni in cui il valore di controllo è impostato in modo da aprire.  Se la chiave Attività di chiusura vengono programmazione per un determinato giorno, tale giorno è necessario che il valore di controllo impostato su chiuso.

### <a name="templates"></a>Modelli

È possibile utilizzare un modelloinventario finanziario per definire tutte le attività che fa parte di un processo di chiusura. Un'attività di chiusura è una risorsa ricorrente di attività assegnato a un utente per completare nell'ambito di ogni processo di chiusura. Nel modello, la data di scadenza deve essere definito per ciascuna attività di chiusura. La data di scadenza correlata al numero di giorni prima o dopo la data di fine periodo definita che l'attività verrà generato ogni periodo. Un tempo scadenza verrà assegnato a ogni attività. L'orario scadenza viene impostato utilizzando il contesto del fuso orario e convertite nel fuso orario per ciascun utente. 

È possibile assegnare un'attività nel modello a una o più società in cui tale attività è applicabile. Se una persona diversa viene assegnata per completare la risorsa di lavoro in ogni società, è utile avvalersi creare più attività per lo stesso Attività di lavoro. Creare un'attività per ciascuna società. 

** Collegamento di attività ** la voce di menu è associata Attività di attività e può essere utilizzata per passare direttamente nella pagina associata dal collegamento di attività nell'area di lavoro. Ad esempio, un'attività di chiusura eseguire il processo di rivalutazione valuta per la contabilità fornitori può essere associata al collegato ** rivalutazione valuta estera ** impagina in Microsoft Dynamics 365 per le operazioni. È inoltre possibile effettuare il collegamento a un URL esterno. 

> [! Suggerimento] se si desidera collegare un report specifico di Management Reporter per l'attività finanziaria di chiusura periodo, è possibile utilizzare il report con URL. Per accedere al report URL, aprire il report in Progettazione report e quindi su ** file ** &gt; ** il rapporto di visualizzazione ** aprirlo in un Web browser. È quindi possibile copiare l'URL nella barra degli indirizzi del browser e incollarlo nel campo **Collegamento attività** **URL**. 

È possibile definire le dipendenze di attività nel modello. Se un'attività è stata impostata dipendere da una o più attività, tale attività non può essere contrassegnata come completato fino al completamento di tutte le dipendenze. 

È possibile creare più modelli di chiusura Riepilogo finanziario. È quindi possibile utilizzare vari modelli per tenere traccia dei processi di chiusura per i diversi tipi di periodo, ad esempio la fine mese o di fine anno, o per tenere traccia delle società che utilizzano i diversi processi di chiusura. Dopo che un modello viene creata, è possibile copiarlo in un nuovo modello e apportare le modifiche necessarie. È possibile assegnare un solo modello a ogni programmazione di chiusura.

### <a name="closing-schedules"></a>Programmazioni chiusura

Utilizzare una programmazione di chiusura per assegnare un modelloinventario finanziario in un periodo finanziario specifico che deve essere chiuso. Le attività dal modello verranno generate automaticamente per il periodo specificato e la nuova programmazione di chiusura verrà inserito nell'area di lavoro. Quando si crea una nuova programmazione di chiusura, ** data di fine del periodo ** il campo consente di determinare le date di scadenza effettive per le attività di chiusura, in base alla data di scadenza correlata assegnata nel modello di chiusura Riepilogo finanziario. 

Assegnare il calendario appropriato per la programmazione di chiusura, per indicare i giorni lavorativi da utilizzare nella programmazione delle attività. Se non si definisce un calendario specifico, le date di scadenza di attività verranno utilizzati tutti i giorni della settimana. 

È inoltre necessario definire le società che verranno associate alla programmazione di chiusura. Se la chiave Attività del modello verranno assegnate a più società, le attività verranno create separate per ogni società che si trova nella programmazione di chiusura e verranno assegnate all'attività del modello. 

Dopo che una programmazione di chiusura viene completata, selezionare ** chiuso ** l'opzione. Lo storico delle attività ancora sarà disponibile ** tutte le attività finanziarie di chiusura periodo ** dalla pagina elenco, ma la programmazione di chiusura verrà rimossa dall'area di lavoro. Dopo che una programmazione di chiusura è stata contrassegnata come ** ** chiuso, non sarà possibile aggiungere attività per, non si modificano le attività, o non rimossi dalle attività.


