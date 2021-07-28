---
title: Programmare un ordine di lavoro a una data e un'ora specifiche
description: In questo argomento viene descritto come programmare un ordine di lavoro a una data e un'ora specifiche in Gestisci cespite.
author: johanhoffmann
ms.date: 08/19/2019
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
ms.openlocfilehash: c28ade5bb6a22b9d15380085ea479e79ba246c1e
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/06/2021
ms.locfileid: "6354062"
---
# <a name="schedule-work-order-on-specific-date-and-time"></a>Programmare un ordine di lavoro a una data e un'ora specifiche

[!include [banner](../../includes/banner.md)]

 

Se un ordine di lavoro deve essere programmato a una data *e* un'ora specifiche, è possibile sostituire il processo di programmazione standard in Gestione cespiti e creare una programmazione specifica per un ordine di lavoro.

1. Fare clic su **Gestione cespiti** > **Comune** > **Ordini di lavoro** > **Tutti gli ordini di lavoro** o **Ordini di lavoro attivi**.

2. Nell'elenco degli ordini di lavoro, fare clic sull'identificazione dell'ordine di lavoro nella colonna **Ordine di lavoro**.

3. Fare clic su **Modifica**.

4. Nella Scheda dettaglio **Intestazione ordine di lavoro**, inserire la data di inizio e di fine nei campi **Data di inizio prevista** e **Data di fine prevista**.

    ![Figura 1.](media/05-work-order-scheduling.png)

5. Nella scheda **Generale**, fare clic su **Programma** per utilizzare il processo di programmazione standard o fare clic su **Spedisci** se si desidera assegnare l'ordine di lavoro a un lavoratore specifico.

6. Per sostituire tutte le prenotazioni di capacità esistenti in modo da assicurarsi che l'ordine di lavoro sia programmato nel periodo previsto, effettuare le selezioni come illustrato nella figura sotto nella finestra di dialogo **Programma ordini di lavoro** > sezione **Capacità limitata**. Ciò significa che il processo di programmazione ignorerà le prenotazioni della capacità esistenti in quanto l'ordine di lavoro deve iniziare alla data e all'ora previste.

    ![Figura 2.](media/06-work-order-scheduling.png)

7. Fare clic su **OK** per avviare la programmazione.

8. Se il processo di programmazione genera prenotazioni doppie, verrà visualizzato un messaggio e sarà possibile rettificare gli ordini di lavoro correlati.

>[!NOTE]
>Per programmare un addetto alla manutenzione per l'ordine di lavoro, l'addetto deve essere disponibile alla data e all'ora di inizio pianificate. La disponibilità del lavoratore viene impostata nel [calendario del lavoratore](../work-order-scheduling/maintenance-worker-calendar-and-scheduling.md). 



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]