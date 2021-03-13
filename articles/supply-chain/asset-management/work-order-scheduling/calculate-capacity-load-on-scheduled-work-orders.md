---
title: Calcolare il carico di capacità in ordini di lavoro programmati
description: In questo argomento viene descritto come calcolare il carico di capacità in ordini di lavoro programmati in Gestisci cespite.
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
ms.openlocfilehash: 7b7e4a20ed56b1eac29d16d527693d6e455cdc37
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/16/2021
ms.locfileid: "5021656"
---
# <a name="calculate-capacity-load-on-scheduled-work-orders"></a><span data-ttu-id="1baa7-103">Calcolare il carico di capacità in ordini di lavoro programmati</span><span class="sxs-lookup"><span data-stu-id="1baa7-103">Calculate capacity load on scheduled work orders</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="1baa7-104">È possibile calcolare il carico di capacità in ordini di lavoro programmati per ottenere una panoramica del carico di lavoro nelle risorse per un periodo specifico.</span><span class="sxs-lookup"><span data-stu-id="1baa7-104">You can calculate capacity load on scheduled work orders to get an overview of the work load on resources for a specific period.</span></span> <span data-ttu-id="1baa7-105">I calcoli possono essere eseguiti per le risorse seguenti: addetti alla manutenzione, gruppi di lavoratori, strumenti e cespiti.</span><span class="sxs-lookup"><span data-stu-id="1baa7-105">Calculations can be made for the following resources: Maintenance workers, worker groups, tools, and assets.</span></span>

1. <span data-ttu-id="1baa7-106">Fare clic su **Gestione cespiti** > **Richieste di informazioni** > **Programma** > **Carico di capacità**.</span><span class="sxs-lookup"><span data-stu-id="1baa7-106">Click **Asset management** > **Inquiries** > **Schedule** > **Capacity load**.</span></span>

2. <span data-ttu-id="1baa7-107">Nella finestra di dialogo **Calcolare carico di capacità** > nel campo **Mostra**, selezionare il tipo di carico che si desidera calcolare: **Capacità**, **Prenotato**, or **Residuo**.</span><span class="sxs-lookup"><span data-stu-id="1baa7-107">In the **Calculate capacity load** dialog > **Show** field, select which load type you want to calculate: **Capacity**, **Reserved**, or **Remainder**.</span></span>

3. <span data-ttu-id="1baa7-108">Impostare l'interruttore **Ignora lo zero** su **Sì** se non si desidera visualizzare i risultati contenenti zero.</span><span class="sxs-lookup"><span data-stu-id="1baa7-108">Select **Yes** on the **Skip zero** toggle button if you do not want to show results containing zero.</span></span>

4. <span data-ttu-id="1baa7-109">Selezionare i tipi di risorsa per i quali si desidera calcolare il carico di capacità impostando gli interruttori pertinenti su **Sì**: **Lavoratore**, **Gruppo di addetti alla manutenzione**, **Strumento** e **Cespite**.</span><span class="sxs-lookup"><span data-stu-id="1baa7-109">Select the resource types for which you want to calculate capacity load by selecting **Yes** on the relevant toggle buttons: **Worker**, **Maintenance worker group**, **Tool**, and **Asset**.</span></span>

5. <span data-ttu-id="1baa7-110">Selezionare la data di inizio per il calcolo nel campo **Dal**.</span><span class="sxs-lookup"><span data-stu-id="1baa7-110">Select the start date for the calculation in the **From date** field.</span></span>

6. <span data-ttu-id="1baa7-111">Nel campo **Tipo di intervallo**, selezionare l'intervallo per il calcolo: **Giorno**, **Settimana**, **Mese** o **Trimestre**.</span><span class="sxs-lookup"><span data-stu-id="1baa7-111">In the **Interval type** field, select the interval for the calculation: **Day**, **Week**, **Month**, or **Quarter**.</span></span>

7. <span data-ttu-id="1baa7-112">Nel campo **Frequenza periodo**, inserire il numero di intervalli da calcolare.</span><span class="sxs-lookup"><span data-stu-id="1baa7-112">In the **Period frequency** field, insert the number of intervals you want to calculate.</span></span> <span data-ttu-id="1baa7-113">Ad esempio, se è stato selezionato **Giorno** come tipo di intervallo e si inserisce il numero "5 "in questo campo, verrà eseguito un calcolo di cinque giorni a partire dalla data di inizio.</span><span class="sxs-lookup"><span data-stu-id="1baa7-113">For example, if you have selected **Day** as the interval type, and you enter the number "5" in this field, a calculation of five days from the start date will be made.</span></span>

8. <span data-ttu-id="1baa7-114">Fare clic su **OK** per avviare il calcolo.</span><span class="sxs-lookup"><span data-stu-id="1baa7-114">Click **OK** to start the calculation.</span></span>

<span data-ttu-id="1baa7-115">Nella figura seguente viene illustrato il risultato di un calcolo relativo a tre settimane per il tipo di carico **Prenotato**.</span><span class="sxs-lookup"><span data-stu-id="1baa7-115">The figure below shows the result of a calculation covering three weeks for the load type **Reserved**.</span></span>

![Figura 1](media/08-work-order-scheduling.png)

[!NOTE]
<span data-ttu-id="1baa7-117">Se si selezionano i tipi di carico **Capacità** o **Residuo** per il calcolo, lo stesso risultato sarà visualizzato se non vengono effettuate prenotazioni per le risorse nel periodo selezionato.</span><span class="sxs-lookup"><span data-stu-id="1baa7-117">If you select the load types **Capacity** or **Remainder** for your calculation, the same result will be displayed if no reservations have been made for the resources in the selected period.</span></span>

<span data-ttu-id="1baa7-118">Per informazioni sulla modalità di calcolo del carico di capacità nelle righe di programma di manutenzione e ordini di lavoro non programmati, consultare [Calcolare carico di capacità](../capacity-planning/calculate-capacity-load.md).</span><span class="sxs-lookup"><span data-stu-id="1baa7-118">For information about how to calculate capacity load on maintenance schedule lines and not scheduled work orders, refer to [Calculate capacity load](../capacity-planning/calculate-capacity-load.md).</span></span>

