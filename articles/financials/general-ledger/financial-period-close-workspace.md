---
title: Area di lavoro chiusura periodo finanziario
description: Questo articolo fornisce una panoramica dell'area di lavoro Chiusura periodo finanziario e della configurazione collegata.
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerPeriodCloseProjectWorkspace
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 13791
ms.assetid: 6ee51758-639b-448e-9cb2-56cf1d804273
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 0bbf8f979aeb8b861164e345f9e46bb396f370ce
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---

# <a name="financial-period-close-workspace"></a>Area di lavoro chiusura periodo finanziario

[!include[banner](../includes/banner.md)]


Questo articolo fornisce una panoramica dell'area di lavoro Chiusura periodo finanziario e della configurazione collegata.

Area di lavoro chiusura periodo finanziario

L'area di lavoro **Chiusura periodo finanziario** consente di tenere traccia dei processi di chiusura finanziari di più società, le aree e le persone. A seconda della visualizzazione dell'area di lavoro **Chiusura periodo finanziario**, vedrete tutte le attività e stati di una programmazione di chiusura, o solo le attività assegnate all'utente. 

È innanzitutto necessario selezionare una programmazione chiusura nella parte superiore dell'area di lavoro. Tutti i dati visualizzati nell'area di lavoro vengono quindi filtrati in base alla programmazione chiusura selezionata.

### <a name="summary-tiles"></a>Sezioni Riepilogo

Le sezioni **Riepilogo** forniscono una panoramica del processo e alcuni indicatori consentono di tenere traccia del processo di chiusura. È possibile visualizzare le attività scadute, quelle rimanenti per la data odierna, quelle in scadenza in data odierna ma bloccate a causa di dipendenze, nonché tutte le attività rimanenti per il processo. Queste informazioni sono valide per tutte le società incluse nella programmazione di chiusura selezionata. Questa informazione viene utilizzata per tutte le società incluse nella programmazione chiusura selezionata.

### <a name="tasks-and-status-section"></a>Sezione Attività e stati

Nella sezione **Attività e stato**, lo stato della programmazione chiusura generale viene suddiviso in diversi modi: stato per società, stato per area e stato per persona responsabile. È possibile visualizzare lo stato di tutte le attività nella programmazione chiusura, solo le attività in scadenza oggi o le attività già scadute modificando il filtro nella parte superiore dell'elenco delle schede. È inoltre possibile selezionare il filtro società per visualizzare lo stato per una società specifica. Ciascuna scheda dello stato fornisce una scomposizione sia per percentuale che è stata completata sia per numero di attività rimanenti. Fare clic sulla scheda o l'azione **Visualizza dettagli** per filtrare l'elenco dettagliato attività per la scheda selezionata. 

L'Ultima scheda è per l'elenco dettagliato attività. Questo elenco visualizza l'elenco completo attività e può essere filtrato in modo da mostrare solo le attività desiderate. È possibile filtrare l'elenco attività in vari modi. Ad esempio, è possibile filtrare per data di scadenza attività, società associata e area associata. È inoltre possibile selezionare di visualizzare o nascondere le attività completate nell'Elenco attività. 

Due indicatori vengono utilizzati per le attività:

-   L'icona del punto esclamativo indica che l'attività è scaduta. Per le attività già scadute, anche la data di scadenza viene evidenziata in rosso.
-   Un'icona di un lucchetto indica che l'attività dipende da altre attività non ancora completate. Un'attività che viene bloccata dalle dipendenze non può essere contrassegnata come completata. È possibile impostare le dipendenze per un'attività utilizzando l'azione **Imposta dipendenza**.

Nome dell'attività è un collegamento ipertestuale nella pagina di Microsoft Dynamics 365 for Operations o altre pagine Web a cui l'utente deve accedere per completare il lavoro. È possibile impostare il collegamento ipertestuale utilizzando il campo **Collegamento attività** quando si modifica o si crea un'attività. 

È possibile collegare file, note, immagini e URL a un'attività utilizzando l'azione **Allegati**. Ad esempio, è possibile indicare i numeri di giornale di registrazione utilizzati come parte di un'attività, aggiungere commenti su un'attività specifica, o collegare un file di report stampato per un'attività. Un'icona viene visualizzata nella colonna **Allegato** per l'attività se un allegato è presente. 

L'opzione **Attività completata** deve essere selezionata manualmente dopo che l'attività è stata completata. Quando un'attività è contrassegnata come completata, il campo **Data di completamento** viene aggiornato automaticamente alla data corrente e all'ora corrente. Gli indicatori di dipendenza vengono inoltre aggiornati nel modo appropriato.

## <a name="all-financial-period-close-tasks-list-page"></a>Pagina di elenco Tutte le attività di chiusura periodo finanziario
È possibile visualizzare tutte le attività correnti e precedenti di chiusura periodo nella pagina **Tutte le attività di chiusura periodo finanziario**. Questa pagina elenco viene utilizzata per l'analisi dello storico del processo di chiusura, poiché include informazioni sulla scadenza programmata, la data di completamento effettivo e sulla persona che ha completato l'attività. È possibile esportare facilmente le informazioni su questa pagina elenco in Microsoft Excel a scopo di report e controllo.

## <a name="financial-period-close-configuration-page"></a>Pagina Configurazione chiusura periodo finanziario
Prima di poter utilizzare l'area di lavoro **Chiusura periodo finanziario**, è necessario configurare il processo in Microsoft Dynamics 365 for Finance and Operations utilizzando la pagina **Configurazione chiusura periodo finanziario**. Fare clic su **Contabilità generale** &gt; **Periodo chiuso** &gt; **Configurazione chiusura periodo finanziario**.

### <a name="resources"></a>Risorse

Nella scheda **Risorse**, definite le persone che sono coinvolte nei processi di chiusura. Qualsiasi dipendente responsabile dell'attività di chiusura deve prima essere assegnato in questo campo. È inoltre necessario specificare la visualizzazione dell'area di lavoro del dipendente. Sono disponibili le seguenti opzioni:

-   **Solo attività assegnate** - L'utente visualizzerà solo le attività a lui assegnate.
-   **Tutte le attività e tutti gli stati** - L'utente visualizzerà tutte le attività di chiusura e lo stato del processo complessivo.

Gli utenti autorizzati a visualizzare solo le attività assegnate a loro non potranno aggiungere attività all'elenco delle attività, modificare o rimuovere attività dall'elenco delle attività.

### <a name="task-areas"></a>Aree attività

Le aree di attività si utilizzano per raggruppare attività di chiusura in aree logiche di proprietà all'interno dell'organizzazione. Ad esempio, i gruppi Contabilità fornitori, Contabilità clienti, o Contabilità generale possono essere utilizzati come aree di attività.

### <a name="calendars"></a>Calendari

Creare e modificare i calendari di chiusura finanziaria utilizzando la scheda Calendari. Questa scheda consente di definire i giorni lavorativi per i processi di chiusura e verrà utilizzata per la programmazione delle attività di chiusura.  Creare un nuovo calendario e specificare i giorni lavorativi da utilizzare per la programmazione delle attività.  È preferibile creare un calendario del lungo termine, ad esempio un anno o più anni, poiché può essere modificato dopo la creazione.  Dopo avere creato il calendario, fare clic sul pulsante Modifica per aggiornare il calendario per giorni specifici, ad esempio festività.  Le attività di chiusura verranno programmate i giorni in cui il valore Controllo è impostato su Aperto.  Se le attività non devono essere programmate in un giorno specifico, tale giorno deve avere il valore Controllo impostato su Chiuso.

### <a name="templates"></a>Modelli

È possibile utilizzare un modello di chiusura finanziaria per definire tutte le attività che fa parte di un processo di chiusura. Un'attività di chiusura è un impegno lavorativo ricorrente assegnato a un utente da completare nell'ambito di ogni processo di chiusura. Nel modello, una data di scadenza relativa deve essere definita per ogni attività di chiusura. La data di scadenza relativa è il numero di giorni prima o dopo la data di fine periodo definita in cui l'attività scade per ciascun periodo. Anche un'ora di scadenza verrà assegnato a ogni attività. L'ora di scadenza è impostata utilizzando il contesto del fuso orario e verrà convertita nel fuso orario relativo a ciascun utente. 

È possibile assegnare un'attività nel modello a una o più società in cui tale attività è applicabile. Se una persona diversa viene assegnata per completare tale impegno lavorativo in ciascuna società, potrebbe essere utile creare più attività per lo stesso impegno lavorativo. Creare un'attività per ciascuna società. 

La voce di menu **Collegamento attività** è associata all'impegno lavorativo dell'attività e può essere utilizzata per accedere direttamente alla pagina associata dal collegamento di attività nell'area di lavoro. Ad esempio, un'attività di chiusura per eseguire il processo di rivalutazione valuta per Contabilità fornitori può essere collegata alla pagina **Rivalutazione valuta estera** associata in Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition. È inoltre possibile effettuare il collegamento a un URL esterno. 

> [Suggerimento]: se si desidera collegare un report di Management Reporter specifico a un'attività di chiusura periodo finanziario, è possibile utilizzare l'URL del report. Per accedere all'URL del report, aprire il report nella funzionalità di progettazione dei report, quindi fare clic su **File** &gt; **Visualizza report** per aprire il report in un Web browser. È quindi possibile copiare l'URL nella barra degli indirizzi del browser e incollarlo nel campo **Collegamento attività** **URL**. 

È possibile definire le dipendenze di attività nel modello. Se un'attività è stata impostata in modo da dipendere da una o più attività, tale attività non può essere contrassegnata come completata fino al completamento di tutte le dipendenze. 

È possibile creare più modelli di chiusura finanziaria. È quindi possibile utilizzare vari modelli per tenere traccia dei processi di chiusura per i diversi tipi di periodo, ad esempio la fine mese o fine anno, o per tenere traccia delle società che utilizzano diversi processi di chiusura. Dopo che un modello viene creato, è possibile copiarlo in un nuovo modello e apportare le modifiche necessarie. È possibile assegnare un solo modello a ogni programmazione di chiusura.

### <a name="closing-schedules"></a>Programmazioni chiusura

Utilizzare una programmazione chiusura per assegnare un modello di chiusura finanziaria a un periodo finanziario specifico che deve essere chiuso. Le attività dal modello verranno quindi generate automaticamente per il periodo specificato e la nuova programmazione chiusura verrà aggiunta all'area di lavoro. Quando si crea una nuova programmazione chiusura, il campo **Data di fine periodo** consente di determinare le date di scadenza effettive per le attività di chiusura, in base alla data di scadenza correlata assegnata nel modello di chiusura finanziaria. 

Assegnare il calendario appropriato per la programmazione di chiusura, per indicare i giorni lavorativi da utilizzare nella programmazione delle attività. Se non si definisce un calendario specifico, le date di scadenza attività utilizzeranno tutti i giorni della settimana. 

È inoltre necessario definire le società che verranno associate alla programmazione di chiusura. Se le attività del modello vengono assegnate a più società, verranno create attività separate per ciascuna società presente nella programmazione di chiusura e verranno assegnate all'attività del modello. 

Dopo che una programmazione di chiusura viene completata, selezionare l'opzione **Chiusa**. Lo storico delle attività ancora sarà disponibile nella pagina elenco **Tutte le attività di chiusura periodo finanziario**, ma la programmazione di chiusura verrà rimossa dall'area di lavoro. Dopo che una programmazione di chiusura è stata contrassegnata come **Chiusa**, non sarà possibile aggiungere attività, modificare attività, o rimuovere attività.




