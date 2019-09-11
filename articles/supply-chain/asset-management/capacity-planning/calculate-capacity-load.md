---
title: Calcola carico di capacità
description: In questo argomento viene descritto come calcolare il carico di capacità in Gestione cespiti.
author: josaw1
manager: AnnBe
ms.date: 08/16/2019
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
ms.openlocfilehash: c6d15861492a46ddb1222db2210f8c751ed38cb3
ms.sourcegitcommit: 109a6ef2d20758dc4a25c51b11e22dd2214a1cc4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/16/2019
ms.locfileid: "1886795"
---
# <a name="calculate-capacity-load"></a><span data-ttu-id="77ba1-103">Calcola carico di capacità</span><span class="sxs-lookup"><span data-stu-id="77ba1-103">Calculate capacity load</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

<span data-ttu-id="77ba1-104">In Gestione cespiti, è possibile calcolare il carico di capacità in</span><span class="sxs-lookup"><span data-stu-id="77ba1-104">In Asset Management, you can calculate capacity load on</span></span>

- <span data-ttu-id="77ba1-105">righe di programma di manutenzione</span><span class="sxs-lookup"><span data-stu-id="77ba1-105">maintenance schedule lines</span></span>  
- <span data-ttu-id="77ba1-106">ordini di lavoro non ancora programmati</span><span class="sxs-lookup"><span data-stu-id="77ba1-106">work orders that have not yet been scheduled</span></span>  
- <span data-ttu-id="77ba1-107">ordini di lavoro programmati</span><span class="sxs-lookup"><span data-stu-id="77ba1-107">scheduled work orders</span></span>

<span data-ttu-id="77ba1-108">Ciò è utile se si desidera ottenere una panoramica del carico di capacità previsto per un periodo specifico.</span><span class="sxs-lookup"><span data-stu-id="77ba1-108">This is useful if you want to get an overview of expected capacity load for a specific period.</span></span> <span data-ttu-id="77ba1-109">Il calcolo del carico di capacità può essere eseguito in tutti i cespiti o nei cespiti selezionati.</span><span class="sxs-lookup"><span data-stu-id="77ba1-109">Calculation of capacity load can be done on all assets or selected assets.</span></span> <span data-ttu-id="77ba1-110">È anche possibile eseguire un calcolo nelle attività dii tempi di fermo per la manutenzione o nei pool di ordini di lavoro.</span><span class="sxs-lookup"><span data-stu-id="77ba1-110">You can also make a calculation on maintenance downtime activities or work order pools.</span></span>

1. <span data-ttu-id="77ba1-111">Fare clic su **Gestione cespiti** > **Richieste di informazioni** > ,**Carico di capacità** o **Gestione cespiti** > **Comune** > **Pool di ordini di lavoro** > **Tutti i pool di ordini di lavoro** / **Pool di ordini di lavoro attivi** > selezionare il pool di ordini di lavoro nell'elenco > pulsante **Carico di capacità** o **Gestione cespiti** > **Comune** > **Attività tempi di fermo per manutenzione** > **Tutte le attività dei tempi di fermo per la manutenzione** / **Attività tempi di fermo per manutenzione attive** > selezionare l'attività dei tempi di fermo per la manutenzione nell'elenco > pulsante **Carico di capacità**.</span><span class="sxs-lookup"><span data-stu-id="77ba1-111">Click **Asset management** > **Inquiries** > **Capacity load**, or **Asset management** > **Common** > **Work order pools** > **All work order pools** / **Active work order pools** > select work order pool in the list > **Capacity load** button, or **Asset management** > **Common** > **Maintenance downtime activities** > **All maintenance downtime activities** / **Active maintenance downtime activities** > select maintenance activity in the list > **Capacity load** button.</span></span>

2. <span data-ttu-id="77ba1-112">Nella finestra di dialogo **Calcolare carico di capacità** selezionare un periodo per il calcolo nei campi **Data/ora di inizio** e **Data/ora di fine**.</span><span class="sxs-lookup"><span data-stu-id="77ba1-112">In the **Calculate capacity load** dialog, select a period for the calculation in the **Start date/time** and **End date/time** fields.</span></span>

3. <span data-ttu-id="77ba1-113">Impostare l'interruttore **Includi programma di manutenzione** su "Sì" se si desidera includere le righe di programma di manutenzione nel calcolo.</span><span class="sxs-lookup"><span data-stu-id="77ba1-113">Select "Yes" on the **Include maintenance schedule** toggle button if you want to include maintenance schedule lines in the calculation.</span></span>

4. <span data-ttu-id="77ba1-114">Impostare l'interruttore **Includi ordine di lavoro** su "Sì" se si desidera includere processi di ordine di lavoro nel calcolo.</span><span class="sxs-lookup"><span data-stu-id="77ba1-114">Select "Yes" on the **Include work order** toggle button if you want to include work order jobs in the calculation.</span></span>

5. <span data-ttu-id="77ba1-115">È possibile utilizzare il campo **Livello** per indicare il livello di dettagli del carico di capacità in relazione alle unità funzionali.</span><span class="sxs-lookup"><span data-stu-id="77ba1-115">You can use the **Level** field to indicate how detailed you want the capacity load lines to be regarding functional locations.</span></span> <span data-ttu-id="77ba1-116">Ad esempio, se si inserisce "1" nel campo e si ha una struttura di unità funzionali multilivello, tutte le righe di programma di manutenzione e gli ordini di lavoro per un'unità funzionale verranno visualizzati nel livello principale, quindi le ore in una riga possono essere aggiunte dalle unità funzionali che si trovano in un livello inferiore.</span><span class="sxs-lookup"><span data-stu-id="77ba1-116">For example, if you insert the number "1" in the field, and you have a multi-level functional location structure, all maintenance schedule lines and work orders for a functional location will be shown on the top level, and therefore the hours on a line may be added up from functional locations located at a lower level.</span></span> <span data-ttu-id="77ba1-117">Se si inserisce "0" nel campo **Livello**, verrà visualizzato un risultato dettagliato che mostra tutte le righe di programma di manutenzione e tutti gli ordini di lavoro in tutti i livelli di unità funzionali a cui sono correlati.</span><span class="sxs-lookup"><span data-stu-id="77ba1-117">If you insert the number "0" in the **Level** field, you will see a detailed result showing all maintenance schedule lines and all work orders on all the functional location levels to which they are related.</span></span>

6. <span data-ttu-id="77ba1-118">Fare clic su **OK** per avviare il calcolo.</span><span class="sxs-lookup"><span data-stu-id="77ba1-118">Click **OK** to start the calculation.</span></span>

7. <span data-ttu-id="77ba1-119">Nei gruppi di riquadri azioni **Raggruppa per**, fare clic sui pulsanti appropriati per visualizzare il livello di dettagli necessario per il calcolo.</span><span class="sxs-lookup"><span data-stu-id="77ba1-119">In the **Group by...** action pane groups, click the relevant buttons to show the required detail level of the calculation.</span></span> <span data-ttu-id="77ba1-120">I pulsanti selezionati nei gruppi di riquadri azioni sono evidenziati in blu.</span><span class="sxs-lookup"><span data-stu-id="77ba1-120">The selected action pane group buttons are highlighted in blue color.</span></span> <span data-ttu-id="77ba1-121">Fare clic su un pulsante per attivarlo o disattivarlo.</span><span class="sxs-lookup"><span data-stu-id="77ba1-121">Click on a button to activate or deactivate it.</span></span>

<span data-ttu-id="77ba1-122">Nella figura seguente viene illustrato un esempio dell'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="77ba1-122">The figure below shows an example of the interface.</span></span>

![Figura 1](media/01-capacity-planning.png)

>[!NOTE]
><span data-ttu-id="77ba1-124">Se si desidera concentrarsi esclusivamente sulla pianificazione capacità in relazione agli ordini di lavoro programmati, vedere [Calcolare il carico di capacità in ordini di lavoro programmati](../work-order-scheduling/calculate-capacity-load-on-scheduled-work-orders.md).</span><span class="sxs-lookup"><span data-stu-id="77ba1-124">If you want to focus only on capacity planning regarding scheduled work orders, refer to [Calculate capacity load on scheduled work orders](../work-order-scheduling/calculate-capacity-load-on-scheduled-work-orders.md).</span></span>

