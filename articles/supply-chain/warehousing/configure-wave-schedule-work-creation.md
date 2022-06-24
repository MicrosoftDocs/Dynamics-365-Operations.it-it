---
title: Pianificare la creazione del lavoro nel corso del ciclo
description: Questo articolo descrive come configurare e utilizzare il metodo di elaborazione del ciclo Pianifica creazione lavoro.
author: Mirzaab
ms.date: 01/14/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSPostMethod, WHSWavePostMethodTaskConfig, WHSWaveTemplateTable, WHSParameters, WHSWaveTableListPage, WHSWorkTableListPage, WHSWorkTable, BatchJobEnhanced, WHSPlannedWorkOrder
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-01-14
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 8b4505d66c37134bc8f672b38d195f4f677df9bc
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8852072"
---
# <a name="schedule-work-creation-during-wave"></a>Pianificare la creazione del lavoro nel corso del ciclo

[!include [banner](../../includes/banner.md)]

Utilizza la funzionalità *Pianifica creazione lavoro* come parte del processo di creazione dei cicli per aumentare la velocità di elaborazione dei cicli facendo in modo che il sistema crei il lavoro utilizzando l'elaborazione parallela.

Quando la funzionalità è abilitata, viene automaticamente creato il lavoro pianificato, che il sistema elaborerà in seguito per creare il lavoro effettivo. Se il numero di righe di carico del ciclo raggiunge una soglia predeterminata, il sistema creerà il lavoro effettivo più rapidamente applicando l'elaborazione parallela e asincrona.

## <a name="turn-on-the-scheduled-work-creation-features-in-feature-management"></a>Attivare le funzionalità di creazione del lavoro programmato nella gestione delle funzionalità

Per utilizzare le funzionalità descritte in questo articolo, è necessario attivarle per il sistema. Usa l'area di lavoro [Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) per attivare le seguenti funzionalità nel seguente ordine:

1. **Blocco del lavoro a livello di organizzazione** - Necessario per la configurazione sia manuale che automatica della creazione del lavoro programmato. (A partire dalla versione 10.0.21 di Supply Chain Management, questa funzionalità è obbligatoria, quindi è attivata per impostazione predefinita e non può essere disattivata di nuovo.)
1. **Programma creazione lavoro** - Necessario per la configurazione sia manuale che automatica della creazione del lavoro programmato.
1. **Metodo ciclo "Programma creazione lavoro" a livello di organizzazione** - Necessario per la configurazione sia manuale che automatica della creazione del lavoro programmato. Non hai bisogno di questa funzione se utilizzi solo la configurazione manuale.

<a name="Auto-enable-schedule-work-creation"></a>

## <a name="automatically-configure-scheduled-work-creation"></a>Configurare automaticamente la creazione del lavoro programmato

Se abiliti la funzionalità *Metodo ciclo "Programma creazione lavoro" a livello di organizzazione*, sul sistema si verifica automaticamente quanto segue:

- Il metodo ciclo *Programma creazione lavoro* (`WHSScheduleWorkCreationWaveStepMethod`) viene aggiunto e configurato per essere eseguito in parallelo tra tutte le persone giuridiche.
- I modelli ciclo di tutte le persone giuridiche che hanno **Tipo di modello ciclo** impostato su *Spedizione* e **Stato modello** impostato su *Valido* avrà il metodo *Crea lavoro* sostituito dal metodo *Programma creazione lavoro*. Tuttavia, i modelli ciclo delle persone giuridiche in cui il metodo *Crea lavoro* può essere ripetibile non verranno modificati.
- Le configurazioni delle attività per il metodo *Programma creazione lavoro* verranno create per tutti i magazzini di tutte le persone giuridiche che hanno **Usa processi di gestione magazzino** abilitato. Ciò significa che il metodo *Programma creazione lavoro* verrà ora eseguito in parallelo per impostazione predefinita. Anche i magazzini esistenti per i quali cambi **Usa processi di gestione magazzino** da *No* a *Sì* eseguiranno questo metodo in parallelo per impostazione predefinita.
- Tutte le persone giuridiche elaboreranno i cicli in batch e **Attesa blocco (ms)** verrà impostato sul valore predefinito di *60.000* ms se era precedentemente impostato su *0* ms.
- Tutti i nuovi modelli ciclo che crei avranno il metodo ciclo *Programma creazione lavoro* invece del metodo *Crea lavoro*.

Le configurazioni esistenti di elaborazione delle attività e dei cicli verranno mantenute anche per tutte le persone giuridiche che sono già configurate per elaborare i cicli in batch e per tutti i magazzini che sono già configurati per utilizzare il metodo *Programma creazione lavoro* in parallelo.

Se necessario, puoi ripristinare manualmente alcune o tutte le impostazioni effettuate automaticamente quando hai abilitato la funzionalità *Metodo ciclo "Programma creazione lavoro" a livello di organizzazione* effettuando le seguenti operazioni:

- Per i modelli ciclo, vai a **Gestione magazzino \> Impostazioni \> Ondate \> Modelli ondata**. Sostituisci il metodo *Programma creazione lavoro* con *Crea lavoro*.
- Per i parametri di magazzino, vai a **Gestione magazzino \> Impostazioni \> Parametri di gestione magazzino**. Nella scheda **Elaborazione ciclo** applica i tuoi valori preferiti per **Elabora cicli in batch** e **Attesa blocco (ms)**.
- Per i metodi ciclo, vai a **Gestione magazzino \> Impostazione \> Cicli \> Metodi di elaborazione ciclo**. Seleziona `WHSScheduleWorkCreationWaveStepMethod` e nel riquadro azioni seleziona **Configurazione attività**. Modifica o elimina il numero di attività batch e il gruppo di cicli assegnato per ogni magazzino elencato in base alle esigenze.

## <a name="manually-configure-scheduled-work-creation"></a>Configurare manualmente la creazione del lavoro programmato

Se non hai abilitato la funzionalità [*Metodo ciclo "Programma creazione lavoro" a livello di organizzazione*](#Auto-enable-schedule-work-creation), puoi utilizzare le procedure fornite in questa sezione per configurare manualmente la creazione del lavoro programmato secondo le necessità.

### <a name="manually-enable-batch-processing-of-waves"></a>Abilitare manualmente l'elaborazione in batch dei cicli

Per sfruttare un metodo asincrono parallelo per creare il lavoro di magazzino, il processo di ciclo deve essere eseguito in batch. Per configurarlo:

1. Fare clic su **Gestione magazzino \> Impostazione \> Parametri di gestione magazzino**.
1. Nella scheda **Generale**, imposta **Elabora cicli in batch** su *Sì*. Facoltativamente, puoi anche selezionare un **Gruppo batch elaborazione ondata** per impedire che l'elaborazione della coda batch venga eseguita contemporaneamente ad altri processi.
1. Imposta il **Tempo di attesa per il blocco (ms)**, che si applica quando il sistema elabora più ondate contemporaneamente. Per la maggior parte dei processi di ondata più grandi, è consigliabile impostare un valore pari a *60000*.

### <a name="manually-enable-the-new-wave-step-method-for-existing-wave-templates"></a>Abilitare manualmente il nuovo metodo del passaggio ondata per i modelli di ondata esistenti

Inizia creando il nuovo metodo di passaggio di ondata e abilitandolo per l'elaborazione parallela di attività asincrone.

1. Andare a **Gestione magazzino \> Impostazione \> Ondate \> Metodi di elaborazione ondata**.
1. Seleziona **Rigenera metodo** e nota come *WHSScheduleWorkCreationWaveStepMethod* sia stato aggiunto all'elenco dei metodi di elaborazione ondata che puoi utilizzare nei modelli di ondate di spedizione.
1. Selezionare il record con il **Nome metodo** *WHSScheduleWorkCreationWaveStepMethod* e selezionare **Configurazione attività**.
1. Per aggiungere una nuova riga alla griglia, selezionare **Nuovo** nel riquadro azioni e utilizzare le impostazioni seguenti:

    - **Magazzino**: seleziona il magazzino che utilizzerai per l'elaborazione di Pianifica creazione lavoro.
    - **Numero massimo di attività batch**: specifica un numero massimo di attività batch. Nella maggior parte dei casi, questo valore dovrebbe essere compreso tra 8 e 16, tuttavia è consigliabile sperimentare l'impostazione ottimale in base ai tuoi scenari.
    - **Gruppo batch elaborazione ondata**: selezionare un gruppo batch di elaborazione ondata dedicato per ottimizzare l'elaborazione della coda batch.

Ora sei pronto per aggiornare un modello di ondata esistente (o crearne uno nuovo) per il metodo di elaborazione ondata *Pianifica creazione lavoro*.

1. Selezionare **Gestione magazzino \> Impostazioni \> Ondate \> Modelli ondata**.
1. Selezionare **Modifica** nel riquadro azioni.
1. Nel riquadro dell'elenco, seleziona il modello di ondata che desideri aggiornare (se stai testando utilizzando i dati demo, puoi usare *Spedizione predefinita 24*).
1. Espandi la Scheda dettaglio **Metodi** e seleziona la riga con il **Nome** *Pianifica creazione lavoro* nella griglia **Metodi rimanenti**.
1. Seleziona la freccia che punta alla colonna **Metodi selezionati** per spostare la riga selezionata in quella colonna. Puoi avere solo un metodo selezionato alla volta che utilizza `WHSScheduleWorkCreationWaveStepMethod` o `createWork`, quindi la riga esistente con **Nome del metodo** `createWork` viene automaticamente spostata nella griglia **Metodi rimanenti**.

## <a name="set-wave-task-processing-threshold-data"></a>Impostare i dati della soglia di elaborazione dell'attività di ondata

Il sistema creerà i dati della soglia di elaborazione dell'attività di ondata predefinita la prima volta che un processo di ondata viene eseguito utilizzando un'elaborazione basata su attività. I dati vengono utilizzati per controllare quando l'elaborazione di ondata verrà eseguita in modo asincrono e sarà basata su attività, il che consente di elaborare e creare lavoro in parallelo.

I dati predefiniti utilizzeranno inizialmente un valore di soglia di 15 per il numero minimo di righe di carico (`MINIMUMWAVELOADLINES`). Ciò significa che quando il sistema elabora un'ondata con più di 15 righe di carico, utilizzerà l'elaborazione delle attività asincrone. Puoi inserire/aggiornare manualmente questi dati nella tabela `WHSWaveTaskProcessingThresholdParameters` negli ambienti di test. Se è necessario modificare questa impostazione in un ambiente di produzione, devi contattare il supporto Microsoft per richiedere l'aggiornamento.

## <a name="work-with-the-scheduled-work-creation"></a>Lavorare con la creazione del lavoro programmato

Per i dettagli su come lavorare con la creazione del lavoro programmato, vedi [Creazione ed elaborazione dei cicli](wave-processing.md). 


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
