---
title: Programmare capacità carico di lavoro
description: In questo articolo viene descritto come impostare e programmare la capacità di carico di lavoro per i lavoratori di un magazzino o per un intero magazzino.
author: Mirzaab
ms.date: 05/26/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WMSWorkloadCapacity
audience: Application User
ms.reviewer: kamaybac
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: bce77798867b373d955320b94c845430d83b5369
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8860379"
---
# <a name="schedule-workload-capacity"></a>Programmare capacità carico di lavoro

[!include[banner](../includes/banner.md)]

È possibile pianificare la capacità del carico di lavoro per i magazzini nonché proiettare i carichi di lavoro correnti e futuri per i lavoratori nei singoli magazzini. È possibile proiettare il carico di lavoro per l'intero magazzino, oppure proiettare separatamente il carico di lavoro per i carichi di lavoro in ingresso e in uscita.

Per proiettare il carico di lavoro in uscita per i magazzini selezionati, devono essere disponibili i dati della programmazione generale per tali magazzini. Per ulteriori informazioni, vedere [Panoramica dei piani generali](../master-planning/master-plans.md).

## <a name="schedule-and-view-workloads-for-a-warehouse"></a>Pianificare e visualizzare i carichi di lavoro per un magazzino

Per pianificare la capacità del carico di lavoro per un magazzino, creare un'impostazione del carico di lavoro per uno o più magazzini, quindi associare l'impostazione del carico di lavoro a un piano generale. Nell'impostazione della capacità del carico di lavoro, è possibile definire i limiti di peso o volume per le transazioni in entrata e in uscita. È inoltre possibile creare più impostazioni per ciascun magazzino e associare l'impostazione ai singoli piani generali. Ad esempio, è possibile utilizzare questo approccio per essere conformi alle modifiche stagionali nella forza lavoro.

Se i lavoratori di un magazzino lavorano con transazioni sia per i carichi di lavoro in ingresso che in uscita, è possibile configurare le impostazioni di capacità del magazzino di modo che il carico di lavoro è proiettato in una visualizzazione combinata.

Per pianificare e visualizzare i carichi di lavoro per i magazzini, è necessario completare le seguenti attività:

1. Creare un'impostazione di capacità del carico di lavoro e definirne i limiti di capacità per uno o più magazzini.
2. Associare le impostazioni di capacità del carico di lavoro con un piano generale per creare le proiezioni del carico di lavoro e specificare il tempo durante il quale verranno applicate queste proiezioni.

### <a name="create-a-workload-capacity-setup-for-a-warehouse"></a>Creare un'impostazione di capacità del carico di lavoro per un magazzino

1. Selezionare **Gestione articoli** \> **Impostazione** \> **Monitoraggio di magazzino** \> **Capacità di carico di lavoro**.
2. Nel riquadro azioni selezionare **Nuova** per creare una nuova impostazione di capacità del carico di lavoro.
3. Fare clic su **Nuovo** nella Scheda dettaglio **Magazzini**, quindi immettere i valori sulla riga per associare un magazzino all'impostazione di capacità del carico di lavoro.
4. Selezionare la casella controllo **Carico di lavoro combinato in entrata e in uscita** se il report **Capacità di carico di lavoro** deve visualizzare il carico di lavoro totale delle transazioni in entrata e in uscita in una visualizzazione.
5. Nella Scheda dettaglio **Tipi di transazione** selezionare i tipi di transazione in entrata e in uscita a cui si applicheranno i limiti del carico di lavoro.

    > [!NOTE]
    > È necessario selezionare almeno un tipo di transazione sia per il carico di lavoro in ingresso che per quello in uscita.

#### <a name="define-limits-for-volume-or-weight"></a>Definizione dei limiti per volume o peso

È possibile impostare limiti per il volume o il peso a seconda di quale limitazione è rilevante per la forza lavoro di magazzino. I limiti specificati vengono inclusi nella proiezione di capacità del carico di lavoro che è possibile visualizzare nel report **Capacità di carico di lavoro**.

Per proiettare le informazioni relative a volume e peso degli articoli, il volume standard e il peso di un articolo di magazzino devono essere specificati per tutti i prodotti. I campi obbligatori sono disponibili nei seguenti gruppi di campi nella Scheda dettaglio **Gestione articoli** della pagina **Dettagli prodotto rilasciato** :

- Movimentazione
- Dimensioni fisiche
- Misure peso

Se queste informazioni non sono state specificate correttamente, alla generazione del report **Capacità di carico di lavoro** si riceverà un messaggio. Dal report è quindi possibile effettuare il drill-down per identificare le informazioni mancanti necessarie per proiettare il carico di lavoro futuro.

### <a name="associate-a-workload-capacity-setup-with-a-master-plan"></a>Associare un'impostazione della capacità del carico di lavoro a un piano generale

1. Selezionare **Gestione articoli** \> **Periodico** \> **Programma carico di lavoro**.
2. Nel campo **Piano generale** selezionare il piano generale da utilizzare per le proiezioni del carico di lavoro.
3. Nel campo **Numero di giorni** specificare il numero di giorni coperti dalla proiezione del carico di lavoro.
4. Nel campo **Carico di lavoro** selezionare l'impostazione del carico di lavoro da associare al piano generale.

### <a name="view-workload-capacity"></a>Visualizzare la capacità del carico di lavoro

1. Selezionare **Gestione inventario** \> **Richieste di informazioni e report** \> **Report inventario fisico** \> **Capacità di carico di lavoro**.
2. Nel campo **Numero di colonne** specificare il numero delle colonne da visualizzare nel report.
3. Nel campo **Tipo di ordine**, selezionare **Pianificato e confermato**, **Pianificato** o **Confermato** per indicare il tipo di ordini da proiettare nel report.
4. Nel campo **Tipo di carico** selezionare un tipo di carico per indicare se la capacità del carico di lavoro deve essere proiettata per il volume o il peso.
5. Nel campo **Capacità di carico di lavoro** selezionare un'impostazione di capacità del carico da lavoro.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]