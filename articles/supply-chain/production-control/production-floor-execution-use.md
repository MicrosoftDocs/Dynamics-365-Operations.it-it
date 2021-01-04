---
title: Modalità di utilizzo dell'interfaccia di esecuzione dell'area di produzione da parte dei lavoratori
description: Questo argomento descrive come utilizzare l'interfaccia di esecuzione dell'area di produzione dal punto di vista di un lavoratore.
author: johanhoffmann
manager: tfehr
ms.date: 10/05/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2020-10-05
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: 40c6794fdf25da44a75aba4a502a89966c0ec4d0
ms.sourcegitcommit: f27f5d07c040bdca1bcd616f5d3f2320d3b3337e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/15/2020
ms.locfileid: "4431458"
---
# <a name="how-workers-use-the-production-floor-execution-interface"></a>Modalità di utilizzo dell'interfaccia di esecuzione dell'area di produzione da parte dei lavoratori

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

L'interfaccia di esecuzione dell'area di produzione è ottimizzata per l'interazione a tocco. Il design offre un contrasto visivo che soddisfa i requisiti di accessibilità per gli ambienti di produzione. Offre tutte le stesse capacità funzionali del dispositivo scheda di processo. Tuttavia, consente anche di avviare più processi in parallelo da un elenco di processi. (Questa funzionalità è nota anche come *raggruppamento di processi*.) Inoltre, da un elenco di processi i lavoratori possono aprire una guida creata in Microsoft Dynamics 365 Guides. In questo modo, possono ottenere istruzioni visive in un HoloLens.

## <a name="sign-in-to-the-production-floor-execution-interface-as-a-worker"></a>Accedere all'interfaccia di esecuzione dell'area di produzione come lavoratore

Prima che i lavoratori possano iniziare a utilizzare il dispositivo, un supervisore o lo staff tecnico deve prepararlo e aprire la pagina corretta in Dynamics 365 Supply Chain Management. Per ulteriori informazioni su come configurare il dispositivo, vedere [Configurare un dispositivo per eseguire l'interfaccia di esecuzione dell'area di produzione](production-floor-execution-setup.md).

Dopo che il dispositivo è stato preparato, viene visualizzata la pagina di accesso. Questa pagina mostra le informazioni sullo stato dei processi per la cella di lavoro locale. Queste informazioni vengono aggiornate periodicamente. Nella pagina, i lavoratori utilizzano i loro ID badge per accedere. Sebbene i lavoratori non debbano disporre di un account utente per Supply Chain Management, devono avere un account *lavoratore registrato nel tempo* che possono utilizzare quando effettuano l'accesso.

![Pagina di accesso all'interfaccia di esecuzione dell'area di produzione](media/pfei-sign-in-page.png "Pagina di accesso all'interfaccia di esecuzione dell'area di produzione")

Le sezioni rimanenti di questo argomento descrivono il modo in cui i lavoratori interagiscono con l'interfaccia.

## <a name="all-jobs-tab"></a>Scheda Tutti i processi

La scheda **Tutti i processi** fornisce un elenco che mostra tutti i processi di produzione che hanno uno stato di *Non avviato*, *Arrestato* o *Avviato*.

![Scheda Tutti i processi](media/pfei-all-jobs-tab.png "Scheda Tutti i processi")

L'elenco dei processi ha le seguenti colonne. I numeri corrispondono ai numeri della precedente figura.

1. **Colonna di selezione** - La colonna più a sinistra utilizza segni di spunta per indicare i processi che sono stati selezionati dal lavoratore. I lavoratori possono selezionare più processi nell'elenco contemporaneamente. Per selezionare tutti i processi nell'elenco, selezionare il segno di spunta nell'intestazione della colonna. Quando viene selezionato un singolo processo, i dettagli su quel processo vengono visualizzati nella parte inferiore della pagina.
1. **Colonna Stato processo** - Questa colonna utilizza simboli per indicare lo stato di ogni processo. I processi che non hanno alcun simbolo in questa colonna hanno uno stato di *Non avviato*. Un triangolo verde indica i lavori con stato *Avviato*. Due linee verticali gialle indicano i lavori con stato *Arrestato*.
1. **Colonna Alta priorità** - Questa colonna utilizza punti esclamativi per indicare i processi con priorità alta.
1. **Ordine** - Questa colonna mostra il numero dell'ordine di produzione per un processo.
1. **Descrizione** - Questa colonna mostra una descrizione dell'operazione di cui fa parte un processo.
1. **Richiesto** - Questa colonna mostra la quantità che si prevede di produrre per un processo.
1. **Avviato** - Questa colonna mostra la quantità che è già stata avviata per un processo.
1. **Completato** - Questa colonna mostra la quantità che è già stata completata per un processo.
1. **Scartato** - Questa colonna mostra la quantità che è già stata scartata per un processo.
1. **Rimanente** - Questa colonna mostra la quantità che resta da completare per un processo.

## <a name="active-jobs-tab"></a>Scheda Processi attivi

![Scheda Processi attivi](media/pfei-active-jobs-tab.png "Scheda Processi attivi")

L'elenco dei processi nella scheda **Processi attivi** ha le seguenti colonne:

- **Colonna di selezione** - La colonna più a sinistra utilizza segni di spunta per indicare i processi che sono stati selezionati dal lavoratore. I lavoratori possono selezionare più processi nell'elenco contemporaneamente. Per selezionare tutti i processi nell'elenco, selezionare il segno di spunta nell'intestazione della colonna. Quando viene selezionato un singolo processo, i dettagli su quel processo vengono visualizzati nella parte inferiore della pagina.
- **Ordine** - Questa colonna mostra il numero dell'ordine di produzione per un processo.
- **Descrizione** - Questa colonna mostra una descrizione dell'operazione di cui fa parte un processo.
- **Richiesto** - Questa colonna mostra la quantità che si prevede di produrre per un processo.
- **Avviato** - Questa colonna mostra la quantità che è già stata avviata per un processo.
- **Completato** - Questa colonna mostra la quantità che è già stata completata per un processo.
- **Scartato** - Questa colonna mostra la quantità che è già stata scartata per un processo.
- **Rimanente** - Questa colonna mostra la quantità che resta da completare per un processo.

## <a name="starting-and-completing-production-jobs"></a>Avvio e completamento dei processi di produzione

I lavoratori iniziano un processo di produzione selezionando un processo nella scheda **Tutti i processi** e quindi selezionando **Avvia processo** per aprire la finestra di dialogo **Avvia processo**.

![Finestra di dialogo Avvia processo](media/pfei-start-job-dialog.png "Finestra di dialogo Avvia processo")

I lavoratori usano la finestra di dialogo **Avvia processo** per confermare la quantità di produzione e quindi avviare il processo. I lavoratori possono regolare la quantità selezionando il campo **Quantità** e quindi utilizzando la tastiera numerica che appare. I lavoratori quindi selezionano **Avvia** per iniziare a lavorare sul processo. La finestra di dialogo **Avvia processo** viene chiusa e il processo viene aggiunto alla scheda **Processi attivi**.

I lavoratori possono iniziare un processo che si trova in qualsiasi stato. Quando un lavoratore avvia un processo che ha uno stato di *Non avviato*, il campo **Quantità** nella finestra di dialogo **Avvia processo** mostra inizialmente la quantità totale. Quando un lavoratore avvia un processo che ha uno stato di *Avviato* o *Arrestato*, il campo **Quantità** mostra la quantità rimanente.

## <a name="reporting-good-quantities"></a>Dichiarazione di buone quantità

Quando un lavoratore completa o completa parzialmente un processo, può dichiarare le buone quantità prodotte selezionando un processo nella scheda **Processi attivi** e quindi selezionando **Dichiara avanzamento**. Quindi, nella finestra di dialogo **Dichiara avanzamento** il lavoratore inserisce la buona quantità utilizzando la tastiera numerica. La quantità è vuota per impostazione predefinita. Dopo aver immesso una quantità, il lavoratore può aggiornare lo stato del processo a *In corso*, *Arrestato* o *Completato*.

![Finestra di dialogo Dichiarazione avanzamento](media/pfei-report-progress-dialog.png "Finestra di dialogo Dichiarazione avanzamento")

## <a name="reporting-scrap"></a>Dichiarazione dello scarto

Quando un lavoratore completa o completa parzialmente un processo, può dichiarare lo scarto selezionando un processo nella scheda **Processi attivi** e quindi selezionando **Dichiara scarto**. Quindi, nella finestra di dialogo **Dichiara scarto** il lavoratore inserisce la quantità di scarto utilizzando la tastiera numerica. Il lavoratore seleziona anche un motivo (*Nessuno*, *Macchina*, *Operatore* o *Materiale*).

![Finestra di dialogo Dichiarazione scarto](media/pfei-report-scrap-dialog.png "Finestra di dialogo Dichiarazione scarto")

## <a name="completing-a-job-and-starting-a-new-job"></a>Completare un processo e iniziare un nuovo processo

Di solito, i lavoratori completano un processo selezionando uno o più processi correnti nella scheda **Processi attivi** e quindi selezionando **Dichiara avanzamento**. Quindi inseriscono la quantità prodotta (la buona quantità) e impostano lo stato su *Completato*. Se è stato selezionato più di un processo, un lavoratore utilizza i pulsanti **Indietro** e **Avanti** per spostarsi tra loro. Per iniziare un nuovo processo, il lavoratore lo seleziona nella scheda **Tutti i processi** e quindi seleziona **Avvia processo**.

Un lavoratore può anche avviare un nuovo processo mentre il processo precedente è ancora aperto. Ancora una volta il lavoratore seleziona il nuovo processo nella scheda **Tutti i processi** e quindi seleziona **Avvia processo**. Tuttavia, in questo caso, la finestra di dialogo **Avvia processo** informa il lavoratore che sta attualmente lavorando su un processo e che deve quindi interrompere o completare quel processo prima di iniziare il nuovo processo.

## <a name="working-on-multiple-jobs-in-parallel"></a>Lavorare su più processi in parallelo

Un lavoratore può svolgere più processi contemporaneamente (ovvero, in parallelo). In questo caso, la raccolta di processi su cui sta lavorando il lavoratore è chiamata *aggregazione di processi*. Il lavoratore può aggiungere nuovi processi all'aggregazione o completare uno o più processi nell'aggregazione. I due scenari seguenti mostrano come un lavoratore può lavorare sui processi in parallelo.

### <a name="scenario-1-a-worker-who-has-no-active-jobs-wants-to-start-two-jobs-and-work-on-them-in-parallel"></a>Scenario 1: un lavoratore che non ha processi attivi desidera avviare due processi e lavorarci in parallelo

Il lavoratore seleziona il due processi nella scheda **Tutti i processi** e quindi seleziona **Avvia processo**. La finestra di dialogo **Avvia processo** mostra entrambi i processi selezionati e il lavoratore può regolare la quantità da avviare su ogni processo. Il lavoratore quindi conferma la finestra di dialogo e può avviare entrambi i processi.

### <a name="scenario-2-a-worker-who-has-two-active-jobs-that-are-in-progress-wants-to-start-a-third-job-and-work-on-it-in-parallel-with-the-other-two"></a>Scenario 2: un lavoratore che ha due processi attivi in corso e desidera avviare un terzo processo e lavorarci parallelamente agli altri due

Il lavoratore seleziona il terzo processo nella scheda **Tutti i processi** e quindi seleziona **Aggregazione**. Nella finestra di dialogo **Aggregazione**, il lavoratore può regolare la quantità da avviare. Il lavoratore quindi conferma la finestra di dialogo selezionando **Aggregazione**.

## <a name="working-on-indirect-activities"></a>Utilizzo delle attività indirette

Le attività indirette sono attività che non sono direttamente correlate a un ordine di produzione. Le attività indirette possono essere definite in modo flessibile, come descritto in [Impostare attività indirette per orario e presenze](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-indirect-activities-for-time-and-attendance).

Ad esempio, Shannon, una lavoratrice del reparto produzione presso Contoso, desidera partecipare a una riunione aziendale e le riunioni sono considerate un'attività indiretta. Si applica uno dei due scenari seguenti:

- **Shannon sta lavorando a uno o più processi attivi.** Shannon sceglie **Attività**, identifica l'attività (riunione) e conferma la sua selezione. Un messaggio che appare la informa che ha dei processi in corso. Dal messaggio, Shannon può scegliere di completare o arrestare i processi su cui sta lavorando prima di andare alla riunione.
- **Shannon non ha processi attivi.** Shannon sceglie **Attività**, identifica l'attività (riunione) e conferma la sua selezione. Ora è registrata come partecipante alla riunione.

In entrambi gli scenari, dopo che Shannon ha confermato la sua selezione, va alla pagina di accesso o a una pagina che attende la conferma di essere tornata dalla sua attività indiretta. La pagina che appare dipende dalla configurazione dell'interfaccia di esecuzione dell'area di produzione. (Per ulteriori informazioni, vedere [Configurare l'interfaccia di esecuzione dell'area di produzione](production-floor-execution-configure.md).)

## <a name="working-on-breaks"></a>Utilizzo delle pause

I lavoratori possono registrare le pause. Le pause possono essere definite in modo flessibile, come descritto in [Retribuzione basata sulle registrazioni](pay-based-on-registrations.md).

Un lavoratore registra una pausa selezionando **Pausa** e quindi selezionando la scheda che rappresenta il tipo di pausa (come pranzo). Dopo che il lavoratore ha confermato la selezione, il dispositivo mostra la pagina di accesso o una pagina che attende che il lavoratore confermi di essere tornato dalla pausa. La pagina che appare dipende dalla configurazione dell'interfaccia di esecuzione dell'area di produzione. (Per ulteriori informazioni, vedere [Configurare l'interfaccia di esecuzione dell'area di produzione](production-floor-execution-configure.md).)

## <a name="opening-instructions"></a>Apertura delle istruzioni

I lavoratori possono aprire un documento allegato a un processo selezionando **Istruzioni**. Il pulsante **Istruzioni** è disponibile solo se un documento è associato al processo nei dati master. Ad esempio, un documento allegato a un prodotto nella pagina **Prodotti rilasciati** in Supply Chain Management sarà disponibile per essere aperta dai lavoratori nell'interfaccia di esecuzione del reparto produzione.

## <a name="opening-mixed-reality-guides-for-hololens"></a>Apertura delle guide di realtà mista per HoloLens

[Dynamics 365 Guides](https://dynamics.microsoft.com/mixed-reality/guides/) può aiutare a potenziare i lavoratori fornendo un apprendimento pratico che utilizza la realtà mista. È possibile definire processi standardizzati con istruzioni dettagliate che guidano i lavoratori all'individuazione di strumenti e parti di cui hanno bisogno e mostrano il modo in cui utilizzare questi strumenti in situazioni di lavoro reali. Ecco una panoramica del processo.

1. Ogni volta che un lavoratore apre un elenco di processi nell'interfaccia di esecuzione del reparto di produzione, l'interfaccia trova tutte le guide pertinenti per i processi visualizzati.
1. Il lavoratore seleziona **Guides** per visualizzare l'elenco delle guide.
1. Il lavoratore seleziona una guida pertinente nell'elenco.
1. L'interfaccia di esecuzione del reparto di produzione mostra un codice QR per la guida selezionata.
1. Il lavoratore indossa un dispositivo HoloLens e fissa il codice QR per avviare la guida.
1. Il lavoratore utilizza la guida per apprendere come eseguire l'attività.

Per ulteriori informazioni su come creare, assegnare e utilizzare le guide per HoloLens, vedere [Fornire guide di realtà mista per i lavoratori in produzione](instruction-guides-in-production-overview.md).
