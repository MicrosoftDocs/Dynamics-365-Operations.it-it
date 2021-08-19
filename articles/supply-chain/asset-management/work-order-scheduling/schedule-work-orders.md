---
title: Programmare ordini di lavoro
description: In questo argomento viene descritto come programmare ordini di lavoro in Gestione cespiti.
author: johanhoffmann
ms.date: 08/19/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetWorkOrderSchdulePreviewPart, EntAssetWorkOrderScheduleExclusively, EntAssetWorkOrderSchduleInfoPart, EntAssetWorkOrderScheduleListPage, EntAssetWorkOrderSchedule, EntAssetWorkOrderScheduleDelete
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: becd06c46afd92bf07d9a69147b7768e780aefa57f9045c11698c04154d6ddb8
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6718061"
---
# <a name="schedule-work-orders"></a>Programmare ordini di lavoro

[!include [banner](../../includes/banner.md)]

 

In questo argomento viene descritto come programmare ordini di lavoro in Gestione cespiti. 

Il numero di ore necessario per un ordine di lavoro viene definito dalla somma delle ore previste meno le ore registrate. Se è necessario più tempo, la previsione deve essere rettificata di conseguenza. In **Gestione cespiti** > **Comune** > **Ordini di lavoro** > **Tutti gli ordini di lavoro** o **Ordini di lavoro attivi**, è possibile visualizzare o modificare previsioni in un ordine di lavoro selezionando l'ordine di lavoro e facendo clic su **Previsione** nella scheda **Ordine di lavoro**. Dopo la creazione e la stima degli ordini di lavoro, è necessario assegnare gli addetti alla manutenzione e gli strumenti necessari per completare gli ordini di lavoro.

Solo gli ordini di lavoro con un ciclo di vita che consente la programmazione possono essere programmati. Per consentire la programmazione, andare a **Gestione cespiti** > **Impostazione** > **Ordini di lavoro** > **Stati del ciclo di vita** >  Scheda dettaglio **Generale** > interruttore **Consenti programmazione**.

1. Fare clic su **Gestione cespiti** > **Comune** > **Ordini di lavoro** > **Tutti gli ordini di lavoro**.

2. Selezionare gli ordini di lavoro da programmare nell'elenco. Ad esempio, è possibile ordinare l'elenco per **Stato del ciclo di vita corrente**.

3. Nella scheda **Generale** fare clic su **Programma**.

4. Nella finestra di dialogo **Programma ordini di lavoro**, è possibile aggiungere selezioni relative alla data di inizio prevista e al livello di servizio, se necessario. Se il processo di programmazione deve rispettare i limiti di capacità in relazione alle risorse già programmate per altri processi, assicurarsi che gli interruttori **Cespite**, **Strumento** e **Lavoratore** siano impostati su "Sì".

    [!NOTE]
    Se si impostano gli interruttori **Cespite**, **Strumenti** e **Lavoratore** su "No", le prenotazioni esistenti verranno ignorate. Nel Registro informazioni, viene visualizzato un elenco di programmazioni di ordine di lavoro che si sovrappongono ed è possibile fare clic sui messaggi per aprire un ordine di lavoro e riprogrammare, se necessario.

5. Per visualizzare informazioni dettagliate sul processo di programmazione, impostare l'interruttore **Dettagli** su "Sì". Ciò significa che le informazioni dettagliate sui punteggi calcolati per gli ordini di lavoro e gli addetti alla manutenzione saranno visualizzati nel Registro informazioni.

6. Fare clic su **OK** per avviare il processo di programmazione.

7. Al termine della programmazione, nel Registro informazioni viene visualizzato il numero di ordini di lavoro programmati nonché informazioni più dettagliate se l'interruttore **Dettagli** è impostato su "Sì".

>[!NOTE]
>Gli ordini di lavoro vengono programmati in un ciclo per ordine di lavoro, non per processo di ordine di lavoro. È anche possibile aprire la finestra di dialogo **Programma ordini di lavoro** direttamente in **Gestione cespiti** > **Periodico** > **Ordini di lavoro** > **Programma ordini di lavoro**. Effettuare le selezioni e fare clic su **OK** per avviare la programmazione degli ordini di lavoro. È possibile impostare la programmazione degli ordini di lavoro come processo batch nella finestra di dialogo **Programma ordini di lavoro** > Scheda dettaglio **Esecuzione in background**.

*Esempio:* nella figura seguente, la formula immessa nel campo **Data di inizio prevista** genererà la programmazione per tutti gli ordini di lavoro la cui data di inizio prevista è almeno una settimana dopo la data corrente. Questa formula può essere utile quando si esegue la programmazione di ordini di lavoro su base continuativa, ma si intende accertarsi che gli ordini di lavoro programmati per i 5-6 giorni successivi non vengano riprogrammati.

![Figura 1.](media/03-work-order-scheduling.png)

Il tipo di ordine di lavoro associato agli ordini di lavoro può impostare la programmazione per un addetto alla manutenzione (**Gestione cespiti** > **Impostazione** > **Ordini di lavoro** > **Tipi di ordine di lavoro** >  interruttore **Un addetto alla manutenzione** impostato su "Sì"). Ciò significa che se il tipo di ordine di lavoro viene utilizzato in un ordine di lavoro, l'interruttore **Un addetto alla manutenzione** viene automaticamente impostato su "Sì" nella pagina dettagli **Tutti gli ordini di lavoro** > visualizzazione **Intestazione** > Scheda dettaglio **Programma**. Durante la programmazione degli ordini di lavoro, tutti i processi di ordine di lavoro creati nell'ordine di lavoro verranno successivamente programmati per lo stesso addetto alla manutenzione. Se necessario, è possibile modificare la selezione di **Un addetto alla manutenzione** in **Tutti gli ordini di lavoro** per consentire la programmazione di uno o più addetti nei processi di ordine di lavoro.

Il processo di programmazione in Gestione cespiti include vari fattori nel calcolo della programmazione:

- Il calcolo dei punteggi per ordini di lavoro e addetti alla manutenzione. I punteggi per ordini di lavoro e addetti alla manutenzione sono impostati in **Parametri di gestione cespiti**. 
- La verifica della presenza di capacità corrispondenti, ovvero competenze e certificati, necessarie per eseguire il processo. Competenze e certificati per gli addetti alla manutenzione sono impostati nel modulo **Risorse umane** (**Risorse umane** > **Lavoratori** > **Lavoratori** > selezionare il lavoratore nell'elenco > scheda **Lavoratore** > sezione **Competenze** > pulsanti **Competenze** e **Certificati** ). Inoltre, competenze e certificati possono essere aggiunti ai tipi di processo di manutenzione e ai settori di processo di manutenzione. Per ulteriori informazioni su competenze e tipi di processo di manutenzione, vedere [Categorie di tipi di processo di manutenzione e tipi di processo di manutenzione, varianti di tipi di processo di manutenzione, settori di processo di manutenzione ed elenchi di controllo di manutenzione:](../setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md).  

## <a name="scores-used-in-work-order-scheduling"></a>Punteggi utilizzati nella programmazione degli ordini di lavoro

Il calcolo dei punteggi per un processo di ordine di lavoro è basato sulla data di inizio prevista e sul livello di servizio dell'ordine di lavoro.

Calcolo della **Data di inizio**: per ogni data futura calcolata a partire dalla data di inizio prevista, il punteggio della data di inizio viene sottratto e moltiplicato per il punteggio, ovvero "10" negli esempi seguenti.

Calcolo della **Criticità**: Il punteggio della criticità moltiplicato per la criticità nell'ordine di lavoro.

Calcolo del **Livello di servizio**: il punteggio del livello di servizio diviso per il livello di servizio nell'ordine di lavoro.

Negli esempi seguenti, il punteggio di criticità è "2 "e i punteggi del livello di servizio sono "5" e "100".

**Esempio 1:**

| ID ordine di lavoro | Data di inizio prevista | Criticità dell'ordine di lavoro | Livello del servizio di ordine di lavoro | Calcolo               | Punteggio      |
|---------------|---------------------|------------------------|--------------------------|---------------------------|------------|
| WO-00010816   | Domani            | 2                      | 20              | (-1 \* 10) + (2 \* 2) + 5 / 20     | \- 5.75    |
| WO-00010817   | Due giorni dopo la data corrente   | 2                      | 20              | (-2 \* 10) + (2 \* 2) + 5 / 20     | \- 15.75   |
| WO-00010818   | Due giorni dopo la data corrente   | 3                      | 5               | (-2 \* 10) + (2 \* 3) + 5 / 5      | \- 13      |

Gli ordini di lavoro verranno programmati nell'ordine seguente: WO-000108 **16**, WO-000108 **18**, WO-000108 **17**.

**Esempio 2:**

| ID ordine di lavoro | Data di inizio prevista | Criticità dell'ordine di lavoro | Livello del servizio di ordine di lavoro | Calcolo                 | Punteggio    |
|---------------|---------------------|------------------------|---------------------|----------------------------------|----------|
| WO-00010816   | Domani            | 2                      | 20                  | (-1 \* 10) + (2 \* 2) + 100 / 20 | \- 1     |
| WO-00010817   | Due giorni dopo la data corrente   | 2                      | 20                  | (-2 \* 10) + (2 \* 2) + 100 / 20 | \- 11    |
| WO-00010818   | Due giorni dopo la data corrente   | 3                      | 5                   | (-2 \* 10) + (2 \* 3) + 100 / 5  | 6        |

Se il punteggio del livello di servizio viene aumentato a "100" anziché a "5 ", l'ordine di programmazione sarà: WO-000108 **18**, WO-000108 **16**, WO-000108 **17**.

Tutti i punteggi di valutazione relativi al calcolo per determinare quali addetti alla manutenzione devono completare gli ordini di lavoro sono impostati come numeri, che vengono aggiunti al calcolo di ogni addetto alla manutenzione durante la programmazione dell'ordine di lavoro. L'addetto alla manutenzione con il punteggio più alto viene selezionato per l'ordine di lavoro. Di seguito è riportata una breve descrizione dei punteggi degli addetti alla manutenzione:

| Punteggio addetto alla manutenzione| Descrizione |
|---|---|
| Lavoratore responsabile | Se l'addetto alla manutenzione viene selezionato come lavoratore responsabile nell'ordine di lavoro, il punteggio viene addizionato. |
| Gruppo di addetti alla manutenzione responsabile | Se l'addetto alla manutenzione fa parte del gruppo di addetti alla manutenzione responsabile nell'ordine di lavoro, il punteggio viene addizionato. |
| Addetto alla manutenzione preferito         | Se l'addetto alla manutenzione viene selezionato come addetto preferito nel cespite, il punteggio viene addizionato. |
| Gruppo di addetti alla manutenzione preferito   | Se il lavoratore fa parte del gruppo di addetti alla manutenzione preferito nel cespite, il punteggio viene addizionato.  |
| Ubicazione  | Se la società utilizza unità funzionali, gli addetti alla manutenzione ottengono l'intero punteggio se si trovano nell'unità funzionale associata al cespite. Se l'unità funzionale del cespite ha un'ubicazione principale, gli addetti alla manutenzione in quell'unità funzionale ottengono la metà del punteggio. Se anche quell'ubicazione ha un'ubicazione principale, gli addetti alla manutenzione in quell'ubicazione ottengono un terzo del punteggio. Se anche quell'ubicazione ha un'ubicazione principale, gli addetti alla manutenzione in quell'ubicazione ottengono un quarto del punteggio e così via. Se la società utilizza l'ubicazione dei cespiti, che non è consigliata, ubicazione, area e zona vengono utilizzate per calcolare i punteggi dell'ubicazione. I lavoratori ottengono il punteggio pieno se si trovano nell'ubicazione e l'area e la zona correlate al cespite. Se l'ubicazione del lavoratore corrisponde solo all'ubicazione e all'area, il punteggio di valutazione dell'addetto alla manutenzione è pari a 2/3 dell'intero punteggio. Se l'ubicazione dell'addetto alla manutenzione corrisponde solo all'ubicazione, il punteggio di valutazione dell'addetto alla manutenzione è pari a 1/3 dell'intero punteggio. |
| Data di inizio del lavoratore  | Quando la data di inizio è successiva alla data di inizio prevista, il punteggio viene sottratto.  |

>[!NOTE]
>Se un punteggio è impostato su "0" , non viene calcolato. Ciò utile se, ad esempio, non si desidera includere il lavoratore responsabile nella programmazione.

## <a name="competencies-used-in-work-order-scheduling"></a>Competenze utilizzate nella programmazione degli ordini di lavoro

Competenze e requisiti di certificato possono essere impostati nei tipi di processo di manutenzione (**Gestione cespiti** > **Impostazione** > **Processi** > **Tipi di processo di manutenzione**) e nei settori di processo di manutenzione (**Gestione cespiti** > **Impostazione** > **Processi** > **Settore processo di manutenzione**). 

I tipi di processo di manutenzione e i settori di processo di manutenzione sono selezionati nei processi di ordine di lavoro. Se competenze o certificati sono stati selezionati in un tipo di processo di manutenzione o settore di processo di manutenzione e questo tipo o settore è utilizzato in un processo di ordine di lavoro, solo gli addetti alla manutenzione con competenze e certificati corrispondenti sono programmati per lavorare sull'ordine di lavoro.

<a name="gantt"></a>

## <a name="work-with-scheduled-work-orders-using-a-gantt-chart"></a>Utilizzare ordini di lavoro pianificati con un diagramma di Gantt

Il **diagramma di Gantt degli ordini di lavoro pianificati** fornisce un'interfaccia grafica in cui è possibile visualizzare e riprogrammare gli ordini di lavoro.

Per visualizzare e lavorare con il diagramma di Gantt:

1. Andare a **Gestione cespiti > Ordini di lavoro > Diagramma di Gantt degli ordini di lavoro pianificati**.

1. Utilizzare gli elenchi a discesa e i campi nella sezione **Impostazioni** per impostare l'unità funzionale, l'intervallo di tempo e la scala temporale da mostrare nel diagramma di Gantt.

1. Selezionare **Applica**.

    - Il diagramma di Gantt si aggiorna per mostrare gli ordini di lavoro pianificati che corrispondono alle impostazioni. Ogni ordine di lavoro è rappresentato da un rettangolo blu.
    - Per riprogrammare un ordine di lavoro visualizzato, selezionarlo e quindi trascinarlo nella nuova data e ora appropriate.

1. Se sono state apportate modifiche, seleziona **Salva** nel riquadro azioni per salvarle.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]