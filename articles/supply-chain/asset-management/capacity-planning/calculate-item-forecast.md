---
title: Calcolare le previsioni articolo
description: In questo argomento viene descritto come calcolare le previsioni articolo in Gestione cespiti.
author: josaw1
manager: tfehr
ms.date: 08/16/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetItemForecast
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 155dc720804196ccc44fad5eaf71e3563a9c68cf
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/16/2021
ms.locfileid: "5022560"
---
# <a name="calculate-item-forecast"></a><span data-ttu-id="61599-103">Calcolare le previsioni articolo</span><span class="sxs-lookup"><span data-stu-id="61599-103">Calculate item forecast</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="61599-104">Esattamente come è possibile eseguire i calcoli del carico di capacità, descritti nella sezione precedente, è possibile eseguire i calcoli della previsioni articolo in:</span><span class="sxs-lookup"><span data-stu-id="61599-104">Just as you can make capacity load calculations, which are described in the previous section, you can also make item forecast calculations on:</span></span>

- <span data-ttu-id="61599-105">righe di programma di manutenzione</span><span class="sxs-lookup"><span data-stu-id="61599-105">maintenance schedule lines</span></span>  
- <span data-ttu-id="61599-106">ordini di lavoro non ancora programmati</span><span class="sxs-lookup"><span data-stu-id="61599-106">work orders that have not yet been scheduled</span></span>  
- <span data-ttu-id="61599-107">ordini di lavoro programmati</span><span class="sxs-lookup"><span data-stu-id="61599-107">scheduled work orders</span></span>

<span data-ttu-id="61599-108">Questa funzionalità è utile se si desidera ottenere una panoramica del consumo previsto degli articoli (pezzi di ricambio nonché altri articoli necessari per il completamento degli ordini di lavoro) per un periodo specifico.</span><span class="sxs-lookup"><span data-stu-id="61599-108">This is useful if you want to get an overview of expected item consumption (spare parts as well as other items required for completing work orders) for a specific period.</span></span> <span data-ttu-id="61599-109">Il calcolo delle previsioni articolo può essere eseguito in tutti i cespiti o nei cespiti selezionati.</span><span class="sxs-lookup"><span data-stu-id="61599-109">Calculation of item forecast can be done on all assets or selected assets.</span></span> <span data-ttu-id="61599-110">È inoltre possibile eseguire un calcolo in un'attività dei tempi di fermo per la manutenzione (**Tutte le attività tempi di fermo per manutenzione** o **Attività tempi di fermo per manutenzione attive**) oppure in un pool di ordini di lavoro (**Tutti i pool di ordini di lavoro** o **Pool di ordini di lavoro attivi**).</span><span class="sxs-lookup"><span data-stu-id="61599-110">You can also make a calculation on a maintenance downtime activity (**All maintenance downtime activities** or **Active maintenance downtime activities**), or on a work order pool (**All work order pools** or **Active work order pools**).</span></span>

1. <span data-ttu-id="61599-111">Fare clic su **Gestione cespiti** > **Richieste di informazioni** > ,**Previsione articolo** o **Gestione cespiti** > **Comune** > **Pool di ordini di lavoro** > **Tutti i pool di ordini di lavoro** / **Pool di ordini di lavoro attivi** > selezionare il pool degli ordini di lavoro nell'elenco > pulsante **Previsione articolo** o **Gestione cespiti** > **Comune** > **Attività tempi di fermo per manutenzione** > **Tutte le attività tempi di fermo per manutenzione** / **Attività tempi di fermo per manutenzione attive** > selezionare l'attività dei tempi di fermo per la manutenzione nell'elenco > pulsante **Previsione articolo**.</span><span class="sxs-lookup"><span data-stu-id="61599-111">Click **Asset management** > **Inquiries** > **Item forecast**, or **Asset management** > **Common** > **Work order pools** > **All work order pools** / **Active work order pools** > select work order pool in the list > **Item forecast** button, or **Asset management** > **Common** > **Maintenance downtime activities** > **All maintenance downtime activities** / **Active maintenance downtime activities** > select maintenance downtime activity in the list > **Item forecast** button.</span></span>

2. <span data-ttu-id="61599-112">Nella finestra di dialogo **Calcolare previsioni articolo** selezionare un periodo per il calcolo nei campi **Data/ora di inizio** e **Data/ora di fine**.</span><span class="sxs-lookup"><span data-stu-id="61599-112">In the **Calculate item forecast** dialog, select a period for the calculation in the **Start date/time** and **End date/time** fields.</span></span>

3. <span data-ttu-id="61599-113">Impostare l'interruttore **Includi programma di manutenzione** su "Sì" se si desidera includere le righe di programma di manutenzione nel calcolo delle previsioni.</span><span class="sxs-lookup"><span data-stu-id="61599-113">Select "Yes" on the **Include maintenance schedule** toggle button if you want to include maintenance schedule lines in the forecast calculation.</span></span>

4. <span data-ttu-id="61599-114">Impostare l'interruttore **Includi ordine di lavoro** su "Sì" se si desidera includere processi di ordine di lavoro nel calcolo delle previsioni.</span><span class="sxs-lookup"><span data-stu-id="61599-114">Select "Yes" on the **Include work order** toggle button if you want to include work order jobs in the forecast calculation.</span></span>

5. <span data-ttu-id="61599-115">È possibile utilizzare il campo **Livello** per indicare il livello di dettagli delle righe di previsione articolo in relazione alle unità funzionali.</span><span class="sxs-lookup"><span data-stu-id="61599-115">You can use the **Level** field to indicate how detailed you want the item forecast lines to be regarding functional locations.</span></span> 

      <span data-ttu-id="61599-116">Ad esempio, se si inserisce "1" nel campo e si ha una struttura di unità funzionali multilivello, tutte le righe di programma di manutenzione e gli ordini di lavoro per un'unità funzionale verranno visualizzati nel livello principale, quindi le ore in una riga possono essere aggiunte dalle unità funzionali che si trovano in un livello inferiore.</span><span class="sxs-lookup"><span data-stu-id="61599-116">For example, if you insert the number "1" in the field, and you have a multi-level functional location structure, all maintenance schedule lines and work orders for a functional location will be shown on the top level, and therefore the hours on a line may be added up from functional locations located at a lower level.</span></span> 
  
      <span data-ttu-id="61599-117">Se si inserisce "0" nel campo **Livello**, verrà visualizzato un risultato dettagliato che mostra tutte le righe di programma di manutenzione e tutti gli ordini di lavoro in tutti i livelli di unità funzionali a cui sono correlati.</span><span class="sxs-lookup"><span data-stu-id="61599-117">If you insert the number "0" in the **Level** field, you will see a detailed result showing all maintenance schedule lines and all work orders on all the functional location level to which they are related.</span></span>

6. <span data-ttu-id="61599-118">Fare clic su **OK** per avviare il calcolo.</span><span class="sxs-lookup"><span data-stu-id="61599-118">Click **OK** to start the calculation.</span></span>

7. <span data-ttu-id="61599-119">Nei gruppi **Raggruppa per**, fare clic sui pulsanti appropriati per visualizzare il livello di dettagli necessario per il calcolo.</span><span class="sxs-lookup"><span data-stu-id="61599-119">In the **Group by...** groups, click the relevant buttons to show the required detail level of the calculation.</span></span> <span data-ttu-id="61599-120">Nel schermata di seguito, i pulsanti selezionati **Raggruppa per** sono evidenziati nel colore blu.</span><span class="sxs-lookup"><span data-stu-id="61599-120">In the screenshot below, the selected **Group by** buttons are highlighted in blue color.</span></span> <span data-ttu-id="61599-121">Fare clic su un pulsante per attivarlo o disattivarlo.</span><span class="sxs-lookup"><span data-stu-id="61599-121">Click on a button to activate or deactivate it.</span></span>

8. <span data-ttu-id="61599-122">Fare clic sul pulsante **Visualizza dimensioni** se si desidera visualizzare il prodotto, l'immagazzinamento o le dimensioni di tracciabilità correlati agli articoli.</span><span class="sxs-lookup"><span data-stu-id="61599-122">Click the **Display dimensions** button if you want to see the product, storage, or tracking dimensions related to the items.</span></span> <span data-ttu-id="61599-123">Selezionare le casella di controllo pertinenti, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="61599-123">Select the relevant check boxes, and click **OK**.</span></span>

![Figura 1](media/02-capacity-planning.png)
