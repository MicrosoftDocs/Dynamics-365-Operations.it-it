---
title: Programmare un ordine di lavoro a una data e un'ora specifiche
description: In questo argomento viene descritto come programmare un ordine di lavoro a una data e un'ora specifiche in Gestisci cespite.
author: josaw1
manager: tfehr
ms.date: 08/19/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: e1b9fc2f51e92a4760a612d778b65cfc1b4e2a9e
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/16/2021
ms.locfileid: "5017369"
---
# <a name="schedule-work-order-on-specific-date-and-time"></a><span data-ttu-id="135ab-103">Programmare un ordine di lavoro a una data e un'ora specifiche</span><span class="sxs-lookup"><span data-stu-id="135ab-103">Schedule work order on specific date and time</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="135ab-104">Se un ordine di lavoro deve essere programmato a una data *e* un'ora specifiche, è possibile sostituire il processo di programmazione standard in Gestione cespiti e creare una programmazione specifica per un ordine di lavoro.</span><span class="sxs-lookup"><span data-stu-id="135ab-104">If a work order must be scheduled on a specific date *and* time, you can override the standard scheduling process in Asset Management and create a specific schedule for a work order.</span></span>

1. <span data-ttu-id="135ab-105">Fare clic su **Gestione cespiti** > **Comune** > **Ordini di lavoro** > **Tutti gli ordini di lavoro** o **Ordini di lavoro attivi**.</span><span class="sxs-lookup"><span data-stu-id="135ab-105">Click **Asset management** > **Common** > **Work orders** > **All Work orders** or **Active work orders**.</span></span>

2. <span data-ttu-id="135ab-106">Nell'elenco degli ordini di lavoro, fare clic sull'identificazione dell'ordine di lavoro nella colonna **Ordine di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="135ab-106">In the work order list, click on the Work order ID in the **Work order** column.</span></span>

3. <span data-ttu-id="135ab-107">Fare clic su **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="135ab-107">Click **Edit**.</span></span>

4. <span data-ttu-id="135ab-108">Nella Scheda dettaglio **Intestazione ordine di lavoro**, inserire la data di inizio e di fine nei campi **Data di inizio prevista** e **Data di fine prevista**.</span><span class="sxs-lookup"><span data-stu-id="135ab-108">On the **Work order header** FastTab, insert start and end dates and times in the **Expected start** and **Expected end** fields.</span></span>

    ![Figura 1](media/05-work-order-scheduling.png)

5. <span data-ttu-id="135ab-110">Nella scheda **Generale**, fare clic su **Programma** per utilizzare il processo di programmazione standard o fare clic su **Spedisci** se si desidera assegnare l'ordine di lavoro a un lavoratore specifico.</span><span class="sxs-lookup"><span data-stu-id="135ab-110">On the **General** tab, click **Schedule** to use the standard scheduling process, or click **Dispatch** if you want to assign the work order to a specific worker.</span></span>

6. <span data-ttu-id="135ab-111">Per sostituire tutte le prenotazioni di capacità esistenti in modo da assicurarsi che l'ordine di lavoro sia programmato nel periodo previsto, effettuare le selezioni come illustrato nella figura sotto nella finestra di dialogo **Programma ordini di lavoro** > sezione **Capacità limitata**.</span><span class="sxs-lookup"><span data-stu-id="135ab-111">In order to override any existing capacity reservations to ensure that the work order is scheduled in the expected period, make the selections as shown in the figure below in the **Schedule work order** dialog > **Finite capacity** section.</span></span> <span data-ttu-id="135ab-112">Ciò significa che il processo di programmazione ignorerà le prenotazioni della capacità esistenti in quanto l'ordine di lavoro deve iniziare alla data e all'ora previste.</span><span class="sxs-lookup"><span data-stu-id="135ab-112">This means that the scheduling process will ignore existing capacity reservations because the work order must start on the expected start time.</span></span>

    ![Figura 2](media/06-work-order-scheduling.png)

7. <span data-ttu-id="135ab-114">Fare clic su **OK** per avviare la programmazione.</span><span class="sxs-lookup"><span data-stu-id="135ab-114">Click **OK** to start scheduling.</span></span>

8. <span data-ttu-id="135ab-115">Se il processo di programmazione genera prenotazioni doppie, verrà visualizzato un messaggio e sarà possibile rettificare gli ordini di lavoro correlati.</span><span class="sxs-lookup"><span data-stu-id="135ab-115">If the scheduling process results in double bookings, you will see a message on the screen, and you can adjust the related work orders.</span></span>

>[!NOTE]
><span data-ttu-id="135ab-116">Per programmare un addetto alla manutenzione per l'ordine di lavoro, l'addetto deve essere disponibile alla data e all'ora di inizio pianificate.</span><span class="sxs-lookup"><span data-stu-id="135ab-116">In order to schedule a maintenance worker for the work order, that maintenance worker must be available at the expected start date and time.</span></span> <span data-ttu-id="135ab-117">La disponibilità del lavoratore viene impostata nel [calendario del lavoratore](../work-order-scheduling/maintenance-worker-calendar-and-scheduling.md).</span><span class="sxs-lookup"><span data-stu-id="135ab-117">Worker availability is set up in the [worker calendar](../work-order-scheduling/maintenance-worker-calendar-and-scheduling.md).</span></span> 

