---
title: Pianificare la creazione del lavoro nel corso del ciclo
description: Questo argomento descrive come configurare e utilizzare il metodo di elaborazione del ciclo Pianifica creazione lavoro.
author: perlynne
manager: mirzaab
ms.date: 01/14/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSPostMethod, WHSWavePostMethodTaskConfig, WHSWaveTemplateTable, WHSParameters, WHSWaveTableListPage, WHSWorkTableListPage, WHSWorkTable, BatchJobEnhanced, WHSPlannedWorkOrder
audience: Application User
ms.reviewer: ''
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2021-01-14
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: ed8f43c7db139b7b16ac6901d5db56ba2f021690
ms.sourcegitcommit: b7a7a14f8650913f6797ae1c4a82ad8adfe415fd
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2021
ms.locfileid: "5078276"
---
# <a name="schedule-work-creation-during-wave"></a>Pianificare la creazione del lavoro nel corso del ciclo

[!include [banner](../includes/banner.md)]

Utilizza la funzionalità *Pianifica creazione lavoro* come parte del processo di creazione dei cicli per aumentare la velocità di elaborazione dei cicli facendo in modo che il sistema crei il lavoro utilizzando l'elaborazione parallela.

Quando la funzionalità è abilitata, viene automaticamente creato il lavoro pianificato, che il sistema elaborerà in seguito per creare il lavoro effettivo. Se il numero di righe di carico del ciclo raggiunge una soglia predeterminata, il sistema creerà il lavoro effettivo più rapidamente applicando l'elaborazione parallela e asincrona.

## <a name="enable-the-schedule-work-creation-feature"></a>Abilitare la funzione Pianifica creazione lavoro

### <a name="enable-the-feature-in-feature-management"></a>Abilitare la funzionalità nella gestione delle funzionalità

Prima di poter utilizzare la funzionalità *Pianifica creazione lavoro*, è necessario attivarla nel sistema. Gli amministratori possono utilizzare l'area di lavoro [Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) per controllare lo stato della funzionalità e attivarla se necessario. Nell'area di lavoro, la funzionalità è elencata nel modo seguente:

- **Modulo:** *Gestione Magazzino*
- **Nome funzionalità:** *Pianifica creazione lavoro*

> [!NOTE]
> La funzionalità *Blocco lavoro a livello di organizzazione* deve essere abilitata prima di poter abilitare *Pianifica creazione lavoro*.

### <a name="manually-enable-batch-processing-of-waves"></a>Abilitare manualmente l'elaborazione in batch dei cicli

Per sfruttare un metodo asincrono parallelo per creare il lavoro di magazzino, il processo di ciclo deve essere eseguito in batch. Per configurarlo:

1. Andare a  **Gestione magazzino\>Imposta \> Parametri di gestione magazzino**.

1. Nella scheda **Generale**, imposta **Elabora cicli in batch** su *Sì*. Facoltativamente, puoi anche selezionare un **Gruppo batch elaborazione ondata** per impedire che l'elaborazione della coda batch venga eseguita contemporaneamente ad altri processi.

1. Imposta il **Tempo di attesa per il blocco (ms)**, che si applica quando il sistema elabora più ondate contemporaneamente. Per la maggior parte dei processi di ondata più grandi, è consigliabile impostare un valore pari a *60000*.

### <a name="manually-enable-the-new-wave-step-method-for-existing-wave-templates"></a>Abilitare manualmente il nuovo metodo del passaggio ondata per i modelli di ondata esistenti

Inizia creando il nuovo metodo di passaggio di ondata e abilitandolo per l'elaborazione parallela di attività asincrone.

1. Andare a  **Gestione magazzino \> Imposta \> Ondate \> Metodi di elaborazione ondata**.

1. Selezionare  **Rigenera metodo** e notare come *WHSScheduleWorkCreationWaveStepMethod* sia stato aggiunto all'elenco dei metodi di elaborazione ondata che puoi utilizzare nei modelli di ondate di spedizione.

1. Selezionare il record con il **Nome metodo** *WHSScheduleWorkCreationWaveStepMethod* e selezionare **Configurazione attività**.

1. Per aggiungere una nuova riga alla griglia, selezionare **Nuovo** nel riquadro azioni e utilizzare le impostazioni seguenti:

    - **Magazzino**: seleziona il magazzino che utilizzerai per l'elaborazione di Pianifica creazione lavoro.

    - **Numero massimo di attività batch**: specifica un numero massimo di attività batch. Nella maggior parte dei casi, questo valore dovrebbe essere compreso tra 8 e 16, tuttavia è consigliabile sperimentare l'impostazione ottimale in base ai tuoi scenari.

    - **Gruppo batch elaborazione ondata**: selezionare un gruppo batch di elaborazione ondata dedicato per ottimizzare l'elaborazione della coda batch.

Ora sei pronto per aggiornare un modello di ondata esistente (o crearne uno nuovo) per il metodo di elaborazione ondata *Pianifica creazione lavoro*.

1. Passare a  **Gestione magazzino \> Imposta \> Ondate \> Modelli ondata**.

1. Selezionare **Modifica** nel riquadro azioni.

1. Nel riquadro dell'elenco, seleziona il modello di ondata che desideri aggiornare (se stai testando utilizzando i dati demo, puoi usare *Spedizione predefinita 24*).

1. Espandi la Scheda dettaglio **Metodi** e seleziona la riga con il **Nome** *Pianifica creazione lavoro* nella griglia **Metodi rimanenti**.

1. Seleziona la freccia che punta alla colonna **Metodi selezionati** per spostare la riga selezionata in quella colonna. Puoi avere solo un metodo selezionato alla volta che utilizza *WHSScheduleWorkCreationWaveStepMethod* o *createWork*, quindi la riga esistente con **Nome del metodo** *createWork* viene automaticamente spostata nella griglia **Metodi rimanenti**.

## <a name="set-wave-task-processing-threshold-data"></a>Impostare i dati della soglia di elaborazione dell'attività di ondata

Il sistema creerà i dati della soglia di elaborazione dell'attività di ondata predefinita la prima volta che un processo di ondata viene eseguito utilizzando un'elaborazione basata su attività. I dati vengono utilizzati per controllare quando l'elaborazione di ondata verrà eseguita in modo asincrono e sarà basata su attività, il che consente di elaborare e creare lavoro in parallelo.

I dati predefiniti utilizzeranno inizialmente un valore di soglia di 15 per il numero minimo di righe di carico (MINIMUMWAVELOADLINES). Ciò significa che quando il sistema elabora un'ondata con più di 15 righe di carico, utilizzerà l'elaborazione delle attività asincrone. È possibile inserire/aggiornare manualmente questi dati nella tabella **WHSWaveTaskProcessingThresholdParameters** negli ambienti di test, ma se è necessario modificare questa impostazione in un ambiente di produzione, è necessario contattare il supporto Microsoft per richiedere l'aggiornamento.

## <a name="work-with-the-feature"></a>Utilizzare la funzione

Quando la funzionalità *Pianifica creazione lavoro* è abilitata, l'elaborazione dell'ondata creerà il lavoro pianificato, che verrà in seguito utilizzato dal nuovo processo di creazione del lavoro. Durante la creazione del lavoro, il lavoro verrà bloccato utilizzando la funzionalità *Blocco lavoro a livello di organizzazione*.

Il diagramma di flusso seguente mostra come viene creato il lavoro pianificato durante l'elaborazione dell'ondata.

![Programma creazione lavoro](media/schedule-work-creation-process.png)

### <a name="planned-work"></a>Lavoro pianificato

La pagina **Dettagli lavoro pianificato** (**Gestione magazzino \> Lavoro \> Dettagli del lavoro pianificato**) mostra le informazioni sul lavoro pianificato, che viene inizialmente creato durante l'elaborazione dell'ondata. Sono disponibili i seguenti valori di **Stato processo**:

- **In coda**: il lavoro pianificato attende di essere utilizzato per creare lavoro.
- **Completato**: il lavoro pianificato è stato utilizzato per creare lavoro.
- **Non riuscita**: l'elaborazione dell'ondata non è riuscita. Notare che il lavoro pianificato può essere in uno stato **Non riuscita** con o senza lavoro effettivo correlato. Quando il processo di creazione del lavoro effettivo non riesce, il lavoro effettivo rimane nello stato *Annullato*.

### <a name="batch-job-for-the-work-creation-process"></a>Processo batch per il processo di creazione del lavoro

Per visualizzare i processi batch per l'elaborazione delle ondate, selezionare **Processi batch** nel riquadro azioni della pagina **Tutte le ondate**.

Da qui, è possibile visualizzare tutti i dettagli dell'attività batch per ciascuno degli ID processo batch.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]