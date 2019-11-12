---
title: Programmare un ordine di lavoro a una data e un'ora specifiche
description: In questo argomento viene descritto come programmare un ordine di lavoro a una data e un'ora specifiche in Gestisci cespite.
author: josaw1
manager: AnnBe
ms.date: 08/19/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 634bbb4326d560848d36f579a1179187d8369087
ms.sourcegitcommit: fb66731f05207094149a6bc7b8549a4dabbb071a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2019
ms.locfileid: "2652036"
---
# <a name="schedule-work-order-on-specific-date-and-time"></a>Programmare un ordine di lavoro a una data e un'ora specifiche

[!include [banner](../../includes/banner.md)]

 

Se un ordine di lavoro deve essere programmato a una data *e* un'ora specifiche, è possibile sostituire il processo di programmazione standard in Gestione cespiti e creare una programmazione specifica per un ordine di lavoro.

1. Fare clic su **Gestione cespiti** > **Comune** > **Ordini di lavoro** > **Tutti gli ordini di lavoro** o **Ordini di lavoro attivi**.

2. Nell'elenco degli ordini di lavoro, fare clic sull'identificazione dell'ordine di lavoro nella colonna **Ordine di lavoro**.

3. Fare clic su **Modifica**.

4. Nella Scheda dettaglio **Intestazione ordine di lavoro**, inserire la data di inizio e di fine nei campi **Data di inizio prevista** e **Data di fine prevista**.

    ![Figura 1](media/05-work-order-scheduling.png)

5. Nella scheda **Generale**, fare clic su **Programma** per utilizzare il processo di programmazione standard o fare clic su **Spedisci** se si desidera assegnare l'ordine di lavoro a un lavoratore specifico.

6. Per sostituire tutte le prenotazioni di capacità esistenti in modo da assicurarsi che l'ordine di lavoro sia programmato nel periodo previsto, effettuare le selezioni come illustrato nella figura sotto nella finestra di dialogo **Programma ordini di lavoro** > sezione **Capacità limitata**. Ciò significa che il processo di programmazione ignorerà le prenotazioni della capacità esistenti in quanto l'ordine di lavoro deve iniziare alla data e all'ora previste.

    ![Figura 2](media/06-work-order-scheduling.png)

7. Fare clic su **OK** per avviare la programmazione.

8. Se il processo di programmazione genera prenotazioni doppie, verrà visualizzato un messaggio e sarà possibile rettificare gli ordini di lavoro correlati.

>[!NOTE]
>Per programmare un addetto alla manutenzione per l'ordine di lavoro, l'addetto deve essere disponibile alla data e all'ora di inizio pianificate. La disponibilità del lavoratore viene impostata nel [calendario del lavoratore](../work-order-scheduling/maintenance-worker-calendar-and-scheduling.md). 
