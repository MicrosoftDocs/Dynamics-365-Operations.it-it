---
title: Carichi di lavoro di esecuzione della produzione per unità di scala nel cloud e nella rete perimetrale
description: Questo argomento descrive il funzionamento dei carichi di lavoro di esecuzione della produzione con le unità di scala nel cloud e nella rete perimetrale.
author: cabeln
manager: ''
ms.date: 10/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: SCM
ms.author: cabeln
ms.search.validFrom: 2020-10-06
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 6bef28d16236a7862550f3ab87f73baf8dab97b0
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5251076"
---
# <a name="manufacturing-execution-workloads-for-cloud-and-edge-scale-units"></a>Carichi di lavoro di esecuzione della produzione per unità di scala nel cloud e nella rete perimetrale

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

> [!WARNING]
> Alcune funzionalità aziendali non sono completamente supportate nell'anteprima pubblica quando vengono utilizzate le unità di scala del carico di lavoro.

Nell'esecuzione della produzione, le unità di scala nel cloud e nella rete perimetrale offrono le seguenti funzionalità, anche quando le unità della rete perimetrale non sono connesse all'hub:

- Gli operatori macchine e i supervisori del reparto di produzione possono accedere al piano di produzione operativo.
- Gli operatori possono mantenere il piano aggiornato eseguendo lavori di produzione discreti e di elaborazione.
- Il supervisore del reparto di produzione può modificare il piano operativo.
- I lavoratori possono accedere alle funzionali di orario e presenze per l'entrata e l'uscita dalla rete perimetrale per garantire il corretto calcolo della retribuzione.

Questo argomento descrive il funzionamento dei carichi di lavoro di esecuzione della produzione con le unità di scala nel cloud e nella rete perimetrale.

## <a name="the-manufacturing-lifecycle"></a>Il ciclo di vita della produzione

Come mostrato nella figura seguente, il ciclo di vita della produzione è suddiviso in tre fasi: *Piano*, *Esecuzione* e *Finalizzazione*.

[![Fasi di esecuzione della produzione quando viene utilizzato un unico ambiente](media/mes-phases.png "Fasi di esecuzione della produzione quando viene utilizzato un unico ambiente")](media/mes-phases-large.png)

La fase di _Piano_ include la definizione del prodotto, la pianificazione, la creazione e la programmazione degli ordini e il rilascio. La fase di rilascio indica il passaggio dalla fase di _Piano_ alla fase di _Esecuzione_. Quando un ordine di produzione viene rilasciato, i processi dell'ordine di produzione saranno visibili nell'area di produzione e pronti per l'esecuzione.

Quando un processo di produzione viene contrassegnato come completato, si posta dalla fase di _Esecuzione_ alla fase di _Finalizzazione_. Nella fase di _Finalizzazione_, le registrazioni dalla fase di *Esecuzione* vengono inserite in un flusso di lavoro di approvazione, in cui vengono elaborate, approvate e trasferite. A quel punto, l'ordine di produzione è completato. Pertanto, viene generata la base per la retribuzione dei lavoratori.

## <a name="splitting-the-execute-phase-into-a-separate-workload"></a>Suddivisione della fase di esecuzione in un carico di lavoro separato

Come mostrato nella figura seguente, quando vengono utilizzate le unità di scala, la fase di _Esecuzione_ viene suddivisa come carico di lavoro separato.

[![Fasi di esecuzione della produzione quando vengono utilizzate le unità di scala](media/mes-phases-workloads.png "Fasi di esecuzione della produzione quando vengono utilizzate le unità di scala")](media/mes-phases-workloads-large.png)

Il modello ora passa da un'installazione a istanza singola a un modello basato sull'hub e sulle unità di scala. Le fasi _Piano_ e _Finalizzazione_ vengono eseguite come operazioni di back-office sull'hub, mentre il carico di lavoro di esecuzione della produzione viene eseguito sulle unità di scala. I dati vengono trasferiti in modo asincrono tra l'hub e le unità di scala.

Quando un ordine di produzione viene rilasciato sull'hub, tutti i dati necessari per elaborare i processi di produzione vengono trasferiti all'unità di scala. Questi dati includono ordini di produzione, cicli di lavorazione di produzione, distinte base e prodotti. Anche i dati non correlati a un ordine di produzione (come attività indirette, codici di assenza e parametri di produzione) vengono trasferiti dall'hub all'unità di scala. In genere i dati che provengono dall'hub e che vengono trasferiti all'unità di scala possono essere creati o aggiornati solo nell'hub. Ad esempio, non è possibile creare un nuovo codice di assenza o un'attività indiretta sull'unità di scala&mdash;possono essere utilizzati solo per la registrazione. Le registrazioni effettuate sull'unità di scala durante l'esecuzione vengono quindi trasferite all'hub, dove vengono elaborati l'approvazione di orari e presenze, l'inventario e gli aggiornamenti finanziari.

## <a name="manufacturing-execution-tasks-that-can-be-run-on-workloads"></a>Attività di esecuzione della produzione che possono essere eseguite sui carichi di lavoro

Le attività di esecuzione della produzione seguenti possono attualmente essere eseguite sui carichi di lavoro quando vengono utilizzate le unità di scala:

- Entrata, accesso, uscita e assenza
- Inizio processo
- Aggregare i processi
- Segnala stato
- Dichiara scarto
- Attività indiretta
- Interruzione

## <a name="working-with-manufacturing-execution-workloads-on-the-hub"></a>Lavorare con i carichi di lavoro di esecuzione della produzione nell'hub

Di solito, i processi necessari per eseguire i carichi di lavoro di esecuzione della produzione vengono eseguiti automaticamente per mantenere sincronizzati l'hub e tutte le unità di scala, se necessario. Tuttavia, in caso di problemi, è possibile attivare manualmente l'elaborazione delle registrazioni non elaborate ricevute dai carichi di lavoro e/o controllare il registro di elaborazione della registrazione.

### <a name="manually-process-raw-registrations"></a>Elaborare manualmente le registrazioni non elaborate

Un processo batch in Supply Chain Management viene eseguito automaticamente per elaborare tutte le registrazioni ricevute dai carichi di lavoro. Tale processo crea i giornali di registrazione di produzione richiesti e le voci del registro quando viene elaborata una registrazione per un processo completato nel carico di lavoro.

Sebbene il processo di solito venga eseguito automaticamente, è possibile eseguirlo manualmente in qualsiasi momento accedendo all'hub e andando a **Controllo produzione \> Attività periodiche \> Gestione carico di lavoro di backoffice \> Elabora registrazioni non elaborate**.

### <a name="check-the-raw-registration-processing-log"></a>Controllare il registro di elaborazione delle registrazioni non elaborate

Per esaminare il registro di elaborazione delle registrazioni, accedere all'hub, andare a **Controllo produzione \> Attività periodiche \> Gestione carico di lavoro di backoffice \> Registro di elaborazione registrazioni non elaborate**. Nella pagina **Registro di elaborazione registrazioni non elaborate** viene visualizzato un elenco di registrazioni non elaborate in corso di elaborazione e lo stato di ogni registrazione.

![Pagina Registro di elaborazione registrazioni non elaborate](media/mes-processing-log.png "Pagina Registro di elaborazione registrazioni non elaborate")

È possibile utilizzare qualsiasi registrazione nell'elenco selezionandola e quindi selezionando uno dei seguenti pulsanti nel riquadro azioni:

- **Elabora** - Elabora manualmente la registrazione selezionata. Questa azione può essere utile se il processo _Elabora registrazioni non elaborate_ non è stato eseguito o non è riuscito.
- **Annulla** - Annulla la registrazione selezionata.

## <a name="working-with-manufacturing-execution-workloads-on-a-scale-unit"></a>Utilizzare i carichi di lavoro di esecuzione della produzione in un'unità di scala

Di solito, i processi necessari per eseguire i carichi di lavoro di esecuzione della produzione vengono eseguiti automaticamente per mantenere sincronizzati l'hub e tutte le unità di scala, se necessario. Tuttavia, in caso di problemi, è possibile controllare la cronologia degli ordini elaborati su un'unità di scala o eseguire manualmente il processo _Elaborazione messaggi da hub di produzione a unità di scala_.

### <a name="view-the-history-of-manufacturing-jobs-that-have-been-processed-on-a-scale-unit"></a>Visualizzare la cronologia dei processi di produzione elaborati su un'unità di scala

Per esaminare la cronologia dei processi di produzione elaborati su un'unità di scala, accedere al computer con l'unità di scala e andare a **Controllo produzione \> Attività periodiche \> Gestione carico di lavoro di backoffice \> Cronologia elaborazione processi di produzione**. Nella pagina **Cronologia elaborazione processi di produzione** viene visualizzata cronologia di elaborazione degli ordini di produzione sull'unità di scala. È possibile utilizzare qualsiasi ordine di produzione nell'elenco selezionandolo e quindi selezionando uno dei seguenti pulsanti nel riquadro azioni:

- **Elabora** - Elabora manualmente l'ordine di produzione selezionato.
- **Annulla** - Annulla l'ordine di produzione selezionato.

### <a name="manufacturing-hub-to-scale-unit-message-processor-job"></a>Processo Elaborazione messaggi da hub di produzione a unità di scala

Il processo _Elaborazione messaggi da hub di produzione a unità di scala_ elabora i dati dall'hub all'unità di scala. Questo processo viene avviato automaticamente quando viene distribuito il carico di lavoro di esecuzione della produzione. Tuttavia, è possibile eseguirlo manualmente in qualsiasi momento andando a **Controllo produzione \> Attività periodiche \> Gestione carico di lavoro di backoffice \> Elaborazione messaggi da hub di produzione a unità di scala**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]