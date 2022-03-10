---
title: Creazione di ordini di lavoro
description: Nell'argomento viene descritto come creare ordini di lavoro in Gestione cespiti.
author: johanhoffmann
ms.date: 02/01/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetMaintenancePlan, EntAssetObjectCalendarListPage, EntAssetObjectCalendarListPagePoolsOpen
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: c1477e3c1b99172d84d2cdc64fc0ed01c057e0fa59422b30c17868ca400de4d0
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6743700"
---
# <a name="creating-work-orders"></a>Creazione di ordini di lavoro

[!include [banner](../../includes/banner.md)]

Dopo aver programmato processi di manutenzione preventiva, il passaggio successivo prevede la creazione di ordini di lavoro per i processi. È possibile completare questo passaggio utilizzando uno dei programmi di manutenzione. I processi programmati in un programma di manutenzione possono avere diversi tipi di riferimenti, come illustrato nella tabella seguente.

| Tipo di riferimento | Descrizione |
|---|---|
| Piani di manutenzione | Processi di manutenzione preventiva basati su tipi di piani di manutenzione *Tempo* o *Contatore*. |
| Cicli di manutenzione | Processi di manutenzione preventiva contenenti vari cespiti che richiedono un tipo di manutenzione simile. |
| Richiesta di intervento di manutenzione | Una richiesta creata manualmente per la manutenzione o la riparazione di un cespite. Questa richiesta può essere convertita in un ordine di lavoro. |

## <a name="create-work-orders-based-on-your-maintenance-schedule"></a>Creare ordini di lavoro in base al proprio programma di manutenzione

Per creare ordini di lavoro basati sul programma di manutenzione, segui questi passaggi.

1. Apri una delle seguenti pagine, a seconda di come desideri selezionare gli elementi della pianificazione per i tuoi ordini di lavoro:

    - Tutti i programmi di manutenzione (**Gestione cespite \> Programma di gestione \> Tutti i programmi di manutenzione**)
    - Apri le righe dei programmi di manutenzione (**Gestione cespite \> Programma di gestione \> Apri righe programmi di manutenzione**)
    - Apri i pool dei programmi di manutenzione (**Gestione cespite \> Programma di gestione \> Apri pool programmi di manutenzione**)

1. Nella griglia seleziona la casella di controllo per ogni processo di manutenzione pianificata per cui desideri creare un ordine di lavoro. Quindi, nel riquadro azioni, seleziona **Ordine di lavoro**.

    Viene visualizzata la finestra di dialogo **Crea ordini di lavoro**. Il campo **Ore previste manutenzione** mostra il numero totale di ore previste per le righe selezionate.

    ![Finestra di dialogo Crea ordini di lavoro.](media/18-preventive-maintenance.png)

1. Nella sezione **Parametri**, specificare il numero di ordini di lavoro da creare. Consente di selezionare una delle opzioni indicate di seguito.

    - **Un ordine di lavoro per riga** - Crea un ordine di lavoro per riga del programma di manutenzione.
    - **Un ordine di lavoro per** - Crea ordini di lavoro raggruppati in base alle impostazioni delle altre opzioni che diventano disponibili quando selezioni questa opzione.

1. Nel campo **Tipo di ordine di lavoro** seleziona il tipo di ordine di lavoro da utilizzare per tutti gli ordini di lavoro creati.
1. Seleziona **OK** per creare gli ordini di lavoro in base alle tue impostazioni.

## <a name="group-work-order-lines-that-are-automatically-created-while-a-maintenance-plan-runs"></a>Raggruppare le righe ordine di lavoro che vengono create automaticamente durante l'esecuzione di un piano di manutenzione

Questa funzionalità consente di definire le regole per raggruppare le righe dell'ordine di lavoro in un unico ordine di lavoro quando il sistema è configurato per generare automaticamente gli ordini di lavoro, in base a un piano di manutenzione. In precedenza, gli ordini di lavoro generati automaticamente potevano contenere solo una riga. Tuttavia, ora puoi raggruppare gli ordini di lavoro per, ad esempio, cespite, tipo di cespite o unità funzionale. Gli ordini di lavoro generati manualmente potrebbero già essere raggruppati in questo modo, come descritto nella sezione precedente di questo argomento.

### <a name="enable-grouping-for-automatically-generated-work-orders"></a>Abilitare il raggruppamento per gli ordini di lavoro generati automaticamente

Prima di poter utilizzare questa funzione, è necessario attivarla nel sistema. Gli amministratori possono utilizzare le impostazioni della [gestione delle funzionalità](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) per controllare lo stato della funzione e abilitarla. Nell'area di lavoro **Gestione funzionalità**, la funzione è elencata nel modo seguente:

- **Modulo:** *Gestione cespiti*
- **Nome funzionalità:** *Applica regole per raggruppare ordini di lavoro durante l'esecuzione di un piano di manutenzione*

### <a name="set-up-grouping-for-automatically-generated-work-orders"></a>Configurare il raggruppamento per gli ordini di lavoro generati automaticamente

Per configurare il raggruppamento per gli ordini di lavoro generati automaticamente, segui questi passaggi.

1. Passa a **Gestione cespiti \> Imposta \> Manutenzione preventiva \> Piani di manutenzione**.
1. Per ogni piano in cui desideri generare ordini di lavoro raggruppati, segui questi passaggi:

    1. Seleziona il piano nel riquadro dell'elenco.
    1. Nella Scheda dettaglio **Righe**, verifica che la casella di controllo **Creazione automatica** sia selezionata su ogni riga.

1. Passa a **Gestione cespiti \> Periodica \> Manutenzione preventiva \> Piani di manutenzione programmata**.
1. Nella finestra di dialogo **Piani di manutenzione programmata**, nella sezione **Periodo**, specifica l'orizzonte temporale per il piano (fino a che punto guardare avanti quando si trovano lavori di manutenzione programmata per cui generare lavoro).
1. Imposta l'opzione **Crea automaticamente un ordine di lavoro dalla pianificazione** su *Sì*.
1. Nella sezione **Ordine di lavoro** seleziona una delle seguenti opzioni:

    - **Un ordine di lavoro per riga** - Crea un ordine di lavoro per riga del programma di manutenzione. Questa opzione fornisce la stessa funzionalità disponibile quando la funzionalità *Applica le regole per il raggruppamento degli ordini di lavoro durante l'esecuzione di un piano di manutenzione* è disattivata.
    - **Un ordine di lavoro per** - Crea ordini di lavoro raggruppati in base alle impostazioni delle altre opzioni che diventano disponibili quando selezioni questa opzione.

1. Se desideri che le opzioni vengano applicate quando esegui solo alcuni dei tuoi piani di manutenzione, nella Scheda dettaglio **Record da includere** aggiungi i filtri in base alle tue esigenze, proprio come faresti per altri processi batch in Microsoft Dynamics 365 Supply Chain Management.
1. Nella Scheda dettaglio **Esegui in background**, configura le opzioni batch e di pianificazione in base alle tue esigenze, proprio come faresti per altri processi batch in Supply Chain Management.
1. Seleziona **OK** per eseguire e/o pianificare i piani di manutenzione selezionati.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]