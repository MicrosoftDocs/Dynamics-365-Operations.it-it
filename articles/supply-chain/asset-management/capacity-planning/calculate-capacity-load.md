---
title: Calcola carico di capacità
description: In questo argomento viene descritto come calcolare il carico di capacità in Gestione cespiti.
author: johanhoffmann
ms.date: 08/16/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetCapacityLoad, EntAssetWorkOrderCapacityLoadCalculate, EntAssetWorkOrderCapacityLoad
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: eed75cd5268b19d819d42e764bdbb5e6f4c79a0a732c5023b3fc40da798e2ca1
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6757880"
---
# <a name="calculate-capacity-load"></a>Calcolare carico di capacità

[!include [banner](../../includes/banner.md)]


In Gestione cespiti, è possibile calcolare il carico di capacità in:

- righe di programma di manutenzione  
- ordini di lavoro non ancora programmati  
- ordini di lavoro programmati

Ciò è utile se si desidera ottenere una panoramica del carico di capacità previsto per un periodo specifico. Il calcolo del carico di capacità può essere eseguito in tutti i cespiti o nei cespiti selezionati. È anche possibile eseguire un calcolo nelle attività dii tempi di fermo per la manutenzione o nei pool di ordini di lavoro.

1. Fare clic su **Gestione cespiti** > **Richieste di informazioni** > ,**Carico di capacità** o **Gestione cespiti** > **Comune** > **Pool di ordini di lavoro** > **Tutti i pool di ordini di lavoro** / **Pool di ordini di lavoro attivi** > selezionare il pool di ordini di lavoro nell'elenco > pulsante **Carico di capacità** o **Gestione cespiti** > **Comune** > **Attività tempi di fermo per manutenzione** > **Tutte le attività dei tempi di fermo per la manutenzione** / **Attività tempi di fermo per manutenzione attive** > selezionare l'attività dei tempi di fermo per la manutenzione nell'elenco > pulsante **Carico di capacità**.

2. Nella finestra di dialogo **Calcolare carico di capacità** selezionare un periodo per il calcolo nei campi **Data/ora di inizio** e **Data/ora di fine**.

3. Impostare l'interruttore **Includi programma di manutenzione** su "Sì" se si desidera includere le righe di programma di manutenzione nel calcolo.

4. Impostare l'interruttore **Includi ordine di lavoro** su "Sì" se si desidera includere processi di ordine di lavoro nel calcolo.

5. È possibile utilizzare il campo **Livello** per indicare il livello di dettagli del carico di capacità in relazione alle unità funzionali. 

    Ad esempio, se si inserisce "1" nel campo e si ha una struttura di unità funzionali multilivello, tutte le righe di programma di manutenzione e gli ordini di lavoro per un'unità funzionale verranno visualizzati nel livello principale, quindi le ore in una riga possono essere aggiunte dalle unità funzionali che si trovano in un livello inferiore. 
    
    Se si inserisce "0" nel campo **Livello**, verrà visualizzato un risultato dettagliato che mostra tutte le righe di programma di manutenzione e tutti gli ordini di lavoro in tutti i livelli di unità funzionali a cui sono correlati.

6. Fare clic su **OK** per avviare il calcolo.

7. Nei gruppi **Raggruppa per**, fare clic sui pulsanti appropriati per visualizzare il livello di dettagli necessario per il calcolo. Nel schermata di seguito, i pulsanti selezionati **Raggruppa per** sono evidenziati nel colore blu. Fare clic su un pulsante per attivarlo o disattivarlo.

    ![Figura 1.](media/01-capacity-planning.png)

>[!NOTE]
>Se si desidera concentrarsi esclusivamente sulla pianificazione capacità in relazione agli ordini di lavoro programmati, vedere [Calcolare il carico di capacità in ordini di lavoro programmati](../work-order-scheduling/calculate-capacity-load-on-scheduled-work-orders.md).



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]