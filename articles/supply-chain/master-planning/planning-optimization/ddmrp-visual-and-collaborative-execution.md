---
title: Esecuzione collaborativa e visiva
description: Questo articolo descrive come monitorare i punti di disaccoppiamento, le zone buffer, gli ordini pianificati e la cronologia della pianificazione del fabbisogno di materiale basato sulla domanda (DDMRP).
author: t-benebo
ms.date: 06/30/2022
ms.topic: article
ms.search.form: EcoResProductDetailsExtended, ReqDDMRPWorkspace, ReqDecouplingPointsStatusByNetFlow, ReqDecouplingPointStatusByOnHand, ReqPlannedOrderForm, ReqItemDecoupledLeadTime
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2022-06-30
ms.dyn365.ops.version: 10.0.28
ms.openlocfilehash: 92e38c6ea19b60ae0a61e55f240ff52698e06933
ms.sourcegitcommit: 3e04f7e4bc0c29c936dc177d5fa11761a58e9a02
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2022
ms.locfileid: "9689778"
---
# <a name="visual-and-collaborative-execution"></a>Esecuzione collaborativa e visiva

[!include [banner](../../includes/banner.md)]
[!INCLUDE [preview-banner](../../includes/preview-banner.md)]
<!-- KFM: Preview until further notice -->

Questo articolo descrive come monitorare i punti di disaccoppiamento, le zone buffer, gli ordini pianificati e la cronologia della pianificazione del fabbisogno di materiale basato sulla domanda (DDMRP).

## <a name="visually-track-buffers-and-quantities-for-a-selected-item"></a>Monitorare visivamente i buffer e le quantità per un articolo selezionato

In Microsoft Dynamics 365 Supply Chain Management, è possibile monitorare visivamente in che modo i buffer, le quantità disponibili e i livelli del flusso netto cambiano nel tempo per ciascun prodotto rilasciato selezionato. Attenersi alla seguente procedura per aprire e rivedere i grafici.

1. Fai clic su **Gestione informazioni sul prodotto \> Prodotti \> Prodotti rilasciati**.
1. Selezionare un articolo rilasciato impostato come punto di disaccoppiamento. (Per ulteriori informazioni, vedere [Posizionamento delle scorte](ddmrp-inventory-positioning.md).)
1. Nella scheda **Piano** del riquadro Azioni selezionare **Copertura articolo**.
1. Nella pagina **Copertura articoli** selezionare un record di copertura articoli che crea un punto di disaccoppiamento. (Questo record mostrerà il nome di un gruppo di copertura impostato per creare punti di disaccoppiamento.)
1. Selezionare la scheda **Disponibile**. Questa scheda include un grafico che mostra le variazioni della quantità nel tempo, assieme al valore del livello disponibile registrato per un periodo specifico ogni volta che viene eseguita l'ottimizzazione della pianificazione. La scheda include inoltre una tabella che mostra quali delle seguenti categorie hanno fatto registrare livelli disponibili:

    - **Critica**: meno della metà del minimo per il periodo.
    - **Bassa**: tra metà del minimo e il minimo.
    - **Disponibilità nella media**: tra il minimo e il minimo più la zona verde.
    - **Superiore alla media**: superiore alla media.

    ![Livelli storicamente disponibili nella scheda Disponibile.](media/ddmrp-on-hand-graph.png "Livelli storicamente disponibili nella scheda Disponibile")

    > [!NOTE]
    > I colori usati nella scheda **Disponibile** rappresentano intervalli diversi rispetto a quelli usati da colori simili nella scheda **Valori buffer**.

1. Per visualizzare in che modo i valori di buffer sono cambiati nel tempo e il confronto con i livelli disponibili e di flusso netto, selezionare la scheda **Valori buffer**.

    ![Livelli storicamente disponibili e di flusso netto nella scheda Valori buffer.](media/ddmrp-buffer-values-graph.png "Livelli storicamente disponibili e di flusso netto nella scheda Valori buffer")

## <a name="track-the-status-and-planned-orders-for-all-decoupling-points"></a>Monitorare lo stato e gli ordini pianificati per tutti i punti di disaccoppiamento

L'area di lavoro **MRP basata sulla domanda** fornisce diversi strumenti, assieme agli indicatori di prestazione chiave (KPI) e a panoramiche sullo stato degli articoli dei punti di disaccoppiamento e degli ordini pianificati correlati. Per aprirla, andare a **Pianificazione generale \> Aree di lavoro \> MRP basata sulla domanda**.

![MRP basata sulla domanda.](media/ddmrp-workspace.png "MRP basata sulla domanda")

## <a name="get-overviews-of-decoupling-points-and-planned-orders"></a>Ottenere panoramiche dei punti di disaccoppiamento e degli ordini pianificati

Oltre all'area di lavoro **MRP basata sulla domanda**, Supply Chain Management fornisce diverse pagine in cui sono visualizzate informazioni sull'impostazione di DDMRP, sui punti di disaccoppiamento e sugli ordini pianificati. Alcune di queste pagini presentano, nel riquadro Azioni, dei pulsanti particolarmente utili per gestire i buffer, eseguire la pianificazione generale e aprire altre visualizzazioni correlate.

- Per visualizzare lo stato dei punti di disaccoppiamento in base al livello del flusso netto, andare a **Pianificazione generale \> Pianificazione generale \> DDMRP \> Stato dei punti di disaccoppiamento in base al flusso netto**.
- Per visualizzare lo stato dei punti di accoppiamento in base al livello delle scorte disponibili, andare a **Pianificazione generale \> Pianificazione generale \> DDMRP \> Stato dei punti di disaccoppiamento in base alle scorte disponibili**.
- Per visualizzare gli ordini pianificati per i punti di disaccoppiamento, andare a **Pianificazione generale \> Pianificazione generale \> DDMRP \> Ordini pianificati per i punti di disaccoppiamento**.
- Per visualizzare i lead time disaccoppiati, andare a **Pianificazione generale \> Pianificazione generale \> DDMRP \> Lead time disaccoppiato**.

## <a name="clean-up-decoupling-point-buffer-values"></a>Pulizia dei valori di buffer dei punti di disaccoppiamento

Nel tempo, il sistema accumulerà una grande quantità di dati storici correlati ai calcoli continui del buffer. Questi dati storici causeranno un aumento del volume dei dati e alla lunga potrebbero incidere sulle prestazioni del sistema. È quindi consigliabile pulire occasionalmente i valori di buffer dei punti di disaccoppiamento meno recenti.

> [!WARNING]
> Il processo di pulizia rimuoverà le impostazioni dei valori di buffer storici e le informazioni storiche su scorte disponibili/flusso netto. Questa operazione non è reversibile.

Attenersi ai seguenti passaggi per pulire i valori di buffer dei punti di disaccoppiamento.

1. Andare a **Pianificazione generale \> Pianificazione generale \> DDMRP \> Pulisci valori buffer punti di disaccoppiamento**.
1. Nella finestra di dialogo **Pulisci valori buffer punti di disaccoppiamento** impostare i seguenti campi:

    - **Elimina record più vecchi di (giorni)**: specificare l'età dei record più recenti da conservare, in giorni. Tutti i record dei valori di buffer dei punti di disaccoppiamento più vecchi rispetto a questo valore verranno eliminati.
    - **Piano generale**: selezionare un piano generale che include gli articoli che dovranno essere interessati dalla pulizia. La pulizia verrà applicata a tutti gli articoli nel piano, una volta applicate le impostazioni **Filtro** specificate in questa finestra di dialogo.

1. Per limitare il set di record su cui dovrà essere eseguito il processo batch, nella Scheda dettaglio **Record da includere**, selezionare **Filtro** per aprire la finestra di dialogo **Richiesta di informazioni**. Questa finestra di dialogo funziona esattamente come per gli altri tipi di [processi in background](../../../fin-ops-core/dev-itpro/sysadmin/batch-processing-overview.md) in Supply Chain Management.
1. Nella Scheda dettaglio **Esegui in background**, specificare come, quando e con quale frequenza dovrà essere eseguita la pulizia. I campi funzionano esattamente come funzionano per altri tipi di [processi in background](../../../fin-ops-core/dev-itpro/sysadmin/batch-processing-overview.md) in Supply Chain Management.
1. Selezionare **OK** per aggiungere un nuovo processo alla coda batch per l'esecuzione.
