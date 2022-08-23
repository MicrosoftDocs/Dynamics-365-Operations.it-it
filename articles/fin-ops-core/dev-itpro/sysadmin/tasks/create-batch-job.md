---
title: Creare un processo batch
description: Un processo batch è un gruppo di attività inviate a un'istanza del server oggetti applicativi (AOS) in modo che vengano elaborate automaticamente.
author: matapg007
ms.date: 11/22/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: matgupta
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.search.form: BatchJob, SysRecurrence, BatchAlerts
ms.openlocfilehash: 06fb9a18e70c316be97645ba76f9462cd3ccc729
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9292452"
---
# <a name="create-a-batch-job"></a>Creare un processo batch

[!include [banner](../../includes/banner.md)]

Un processo batch è un gruppo di attività inviate a un'istanza del server oggetti applicativi (AOS) in modo che vengano elaborate automaticamente. I processi batch vengono eseguiti con le credenziali di sicurezza dell'utente da cui sono stati creati. Per creare un processo batch, attenersi alla seguente procedura. La società di dati dimostrativi utilizzata per creare questa procedura è USMF.


## <a name="create-the-batch-job"></a>Creare il processo batch
1. Andare a **Pannello di navigazione > Moduli > Amministrazione sistema > Richieste di informazioni > Processi batch**.
2. Selezionare **Nuovo**.
3. Nel campo **Descrizione processo** immetti una descrizione del processo batch.
4. Nel campo **Data/ora di inizio programmate**, immetti la data e l'ora in cui deve essere eseguito il processo batch.
5. Seleziona **Salva**.

## <a name="create-a-recurrence"></a>Creare una ricorrenza
1. Nel riquadro azioni seleziona **Processo batch**.
2. Seleziona **Ricorrenza**. Usare queste opzioni per immettere un intervallo e un criterio per la ricorrenza.  
3. Seleziona **OK**.

## <a name="add-alerts"></a>Aggiungere avvisi
1. Nel riquadro azioni seleziona **Processo batch**.
2. Seleziona **Avvisi**. Indicare se si desidera che i messaggi di avviso vengano inviati quando il processo batch termina, presenta una condizione di errore o viene annullato. Poi specificare se volete che gli allarmi vengano visualizzati come messaggi popup.   
3. Seleziona **OK**.

## <a name="add-a-task-to-a-batch-job"></a>Aggiungere un'attività a un processo batch
1.  Nella pagina **Processi batch**, seleziona **Visualizza attività**.
2.  Seleziona **Ctrl+N** per creare un'attività.
3.  Immettere una descrizione dell'attività batch.
4.  Nel campo **Account società**, seleziona il database aziendale in cui eseguire l'attività.
5.  Nel campo **Nome classe** seleziona il processo che deve essere eseguito dall'attività. 
6.  Se appropriato, seleziona un gruppo batch per l'attività.

    Le attività client devono essere assegnate a un gruppo di questo tipo. Vengono automaticamente assegnate al gruppo batch predefinito (noto anche come gruppo batch vuoto).

7.  Seleziona **Ctrl+S** per salvare l'attività.
8.  Per rendere l'attività selezionata dipendente da un'altra attività nel processo, seleziona la griglia **Include condizioni** quindi segui questi passaggi per ogni condizione che vuoi definire:

    1. Seleziona **Ctrl+N** per creare una condizione.
    2. Seleziona l'ID dell'attività padre.
    3. Seleziona lo stato che l'attività padre deve raggiungere prima che l'attività dipendente possa essere eseguita.
    4. Seleziona **Ctrl+S** per salvare la condizione.

    Se sono state definite più condizioni e devono essere *tutte* soddisfatte affinché l'attività dipendente possa essere eseguita, seleziona **Tutto** come tipo di condizione. Se invece l'attività dipendente può essere eseguita dopo che è stata soddisfatta una *qualsiasi* delle condizioni, seleziona **Qualsiasi** come tipo di condizione.

9.  Seleziona come devono essere gestiti gli errori delle attività. Per ignorare l'errore di un'attività specifica, seleziona l'opzione **Ignora errore attività** nella scheda **Generale** per l'attività in questione. In tal modo, l'errore dell'attività non causa la mancata riuscita del processo. È anche possibile utilizzare il campo **Numero massimo di tentativi** per specificare quante volte è possibile ripetere un'attività prima che venga considerata non riuscita. Come procedura consigliata, ti consigliamo di non impostare il campo **Numero massimo di tentativi** su un valore maggiore di **5**.

    Per ulteriori informazioni sui tentativi in batch, vedi [Abilitare i tentativi in batch](../retryable-batch.md).

## <a name="adjust-batch-job-status"></a>Modificare lo stato del processo batch
1. Andare a **Amministrazione sistema > Richieste di informazioni > Processi batch**.
2. Selezionare il processo batch appropriato.
3. Nel riquadro azioni seleziona **Processo batch > Funzioni > Cambia stato**.
4. Selezionare lo stato appropriato:
    - **Trattenuto**: impostare il processo batch su **trattenuto** di modo che sia trattenuto dallo scheduler dei processi batch. È equivalente a *fermo*.
    - **In attesa**: impostare il processo batch su **in attesa** di modo che sia in attesa di essere selezionato dallo scheduler di processi batch. E equivalente a *avvia*.
5. Seleziona **OK**.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
