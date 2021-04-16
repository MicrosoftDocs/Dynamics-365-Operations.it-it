---
title: Creare report dei consumi
description: In questo argomento viene illustrato come creare report dei consumi in Gestione cespiti.
author: johanhoffmann
ms.date: 08/21/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 8add0602e0ebe7a5c0cf2c76de6fa2f4f21a2f72
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5837923"
---
# <a name="create-consumption-reports"></a>Creare report dei consumi

[!include [banner](../../includes/banner.md)]

 

Dopo aver creato e registrato registrazioni del consumo negli ordini di lavoro in Gestione cespiti, due report sono disponibili per visualizzare dettagli relativi al consumo.


## <a name="asset-consumption-report"></a>Report del consumo dei cespiti

Dopo aver registrato il consumo negli ordini di lavoro, è possibile stampare un report del consumo dei cespiti. Il report visualizza ore, costi orari, costi degli articoli e spese registrate nei cespiti.

1. Fare clic su **Gestione cespiti** > **Report** > **Cespiti** > **Consumo cespite**.

2. Nella finestra di dialogo **Consumo cespite**, selezionare i parametri e il livello di dettagli desiderati selezionando gli interruttori pertinenti su **Sì** e immettendo un livello di unità funzionale nella sezione **Mostra**.
    - È possibile utilizzare il campo **Livelli** per indicare il livello di dettagli delle righe cespite in relazione alle unità funzionali. 
    
        Ad esempio, se si immette "1" nel campo e si ha una struttura di unità funzionali multilivello, tutti i cespiti per un'unità funzionale verranno visualizzati nel livello principale, quindi una riga può essere aggiunta dalle unità funzionali situate a un livello inferiore. 
        
        Se si immette "0" nel campo **Livelli**, verrà visualizzato un risultato dettagliato che mostra tutti i cespiti in tutti i livelli di unità funzionali a cui sono correlati. 
        
    - Impostare l'interruttore **Somma di tutti i cespiti secondari** su **Sì** per visualizzare le somme di ogni cespite secondario nel report.

3. Selezionare un intervallo di date nella sezione **Date**.

4. Nella Scheda dettaglio **Destinazione**, selezionare se si desidera visualizzare il report sullo schermo, stamparlo o salvarlo come file o messaggio di posta elettronica.

5. Se necessario, è possibile selezionare specifici cespiti da visualizzare nel report. Nella Scheda dettaglio **Record da includere**, fare clic su **Filtro** e aggiungere i cespiti da includere nel report.

6. Scegliere **OK** per generare il report.


## <a name="work-order-consumption-report"></a>Report del consumo degli ordini di lavoro

Dopo aver registrato il consumo negli ordini di lavoro, è possibile stampare un report su tale consumo. Il report visualizza ore, costi orari, costi degli articoli e spese registrate negli ordini di lavoro.

1. Fare clic su **Gestione cespiti** > **Report** > **Ordini di lavoro** > **Consumo ordini di lavoro**.

2. Nella finestra di dialogo **Consumo ordini di lavoro**, selezionare i parametri da includere nel report impostando gli interruttori pertinenti della sezione **Mostra** su **Sì**.

3. Selezionare un intervallo di date nella sezione **Date**.

4. Nella Scheda dettaglio **Destinazione**, selezionare se si desidera visualizzare il report sullo schermo, stamparlo o salvarlo come file o messaggio di posta elettronica.

5. Se necessario, è possibile selezionare specifici ordini di lavoro da visualizzare nel report. Nella Scheda dettaglio **Record da includere**, fare clic su **Filtro** e aggiungere gli ordini di lavoro da includere nel report.

6. Scegliere **OK** per generare il report.


>[!NOTE]
>È inoltre possibile generare un [report di ordine di lavoro](../work-orders/work-order-report.md) contenente ulteriori dettagli su un ordine di lavoro.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]