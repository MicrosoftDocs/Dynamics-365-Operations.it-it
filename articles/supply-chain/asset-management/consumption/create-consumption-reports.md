---
title: Creare report dei consumi
description: In questo argomento viene illustrato come creare report dei consumi in Gestione cespiti.
author: josaw1
manager: AnnBe
ms.date: 08/21/2019
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
ms.openlocfilehash: 3d978f8b991211e477dd8f766fe67432d9d493d0
ms.sourcegitcommit: c0b581e4c647b6c47bc14d1d7bfe267832afecba
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/21/2019
ms.locfileid: "1913094"
---
# <a name="create-consumption-reports"></a><span data-ttu-id="9d9ec-103">Creare report dei consumi</span><span class="sxs-lookup"><span data-stu-id="9d9ec-103">Create consumption reports</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

<span data-ttu-id="9d9ec-104">Dopo aver creato e registrato registrazioni del consumo negli ordini di lavoro in Gestione cespiti, due report sono disponibili per visualizzare dettagli relativi al consumo.</span><span class="sxs-lookup"><span data-stu-id="9d9ec-104">When you've created and posted consumption registrations on work orders in Asset Management, two reports are available to display consumption details.</span></span>


## <a name="asset-consumption-report"></a><span data-ttu-id="9d9ec-105">Report del consumo dei cespiti</span><span class="sxs-lookup"><span data-stu-id="9d9ec-105">Asset consumption report</span></span>

<span data-ttu-id="9d9ec-106">Dopo aver registrato il consumo negli ordini di lavoro, è possibile stampare un report del consumo dei cespiti.</span><span class="sxs-lookup"><span data-stu-id="9d9ec-106">When you have posted consumption on work orders, you can print an asset consumption report.</span></span> <span data-ttu-id="9d9ec-107">Il report visualizza ore, costi orari, costi degli articoli e spese registrate nei cespiti.</span><span class="sxs-lookup"><span data-stu-id="9d9ec-107">The report displays hours, hour costs, item costs, and expenses posted on assets.</span></span>

1. <span data-ttu-id="9d9ec-108">Fare clic su **Gestione cespiti** > **Report** > **Cespiti** > **Consumo cespite**.</span><span class="sxs-lookup"><span data-stu-id="9d9ec-108">Click **Asset management** > **Reports** > **Assets** > **Asset consumption**.</span></span>

2. <span data-ttu-id="9d9ec-109">Nella finestra di dialogo **Consumo cespite**, selezionare i parametri e il livello di dettagli desiderati selezionando gli interruttori pertinenti su "Sì" e immettendo un livello di unità funzionale nella sezione **Mostra**.</span><span class="sxs-lookup"><span data-stu-id="9d9ec-109">In the **Asset consumption** dialog, select the parameters and detail level you want to see by selecting "Yes" on the relevant toggle buttons, and inserting a functional location level in the **Show** section.</span></span>
    - <span data-ttu-id="9d9ec-110">È possibile utilizzare il campo **Livelli** per indicare il livello di dettagli delle righe cespite in relazione alle unità funzionali.</span><span class="sxs-lookup"><span data-stu-id="9d9ec-110">You can use the **Levels** field to indicate how detailed you want the asset lines to be regarding functional locations.</span></span> <span data-ttu-id="9d9ec-111">Ad esempio, se si inserisce "1" nel campo e si ha una struttura di unità funzionali multilivello, tutti i cespiti per un'unità funzionale verranno visualizzati nel livello principale, quindi una riga può essere aggiunta dalle unità funzionali situate a un livello inferiore.</span><span class="sxs-lookup"><span data-stu-id="9d9ec-111">For example, if you insert the number "1" in the field, and you have a multi-level functional location structure, all assets for a functional location will be shown on the top level, and therefore a line may be added up from functional locations located at a lower level.</span></span> <span data-ttu-id="9d9ec-112">Se si inserisce "0" nel campo **Livelli**, verrà visualizzato un risultato dettagliato che mostra tutti i cespiti in tutti i livelli di unità funzionali a cui sono correlati.</span><span class="sxs-lookup"><span data-stu-id="9d9ec-112">If you insert the number "0" in the **Levels** field, you will see a detailed result showing all assets on all the functional location levels to which they are related.</span></span> 
    - <span data-ttu-id="9d9ec-113">Impostare l'interruttore **Somma di tutti i cespiti secondari** su "Sì" per visualizzare le somme di ogni cespite secondario nel report.</span><span class="sxs-lookup"><span data-stu-id="9d9ec-113">Select "Yes" on the **Sum on all sub assets** toggle button to see sums for each sub asset in the report.</span></span>

3. <span data-ttu-id="9d9ec-114">Selezionare un intervallo di date nella sezione **Date**.</span><span class="sxs-lookup"><span data-stu-id="9d9ec-114">Select a date interval in the **Dates** section.</span></span>

4. <span data-ttu-id="9d9ec-115">Nella Scheda dettaglio **Destinazione**, selezionare se si desidera visualizzare il report sullo schermo, stamparlo o salvarlo come file o messaggio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="9d9ec-115">On the **Destination** FastTab, select if you want to display the report on screen, print it, or save it as a file or email.</span></span>

5. <span data-ttu-id="9d9ec-116">Se necessario, è possibile selezionare specifici cespiti da visualizzare nel report.</span><span class="sxs-lookup"><span data-stu-id="9d9ec-116">If required, you can select specific assets to be displayed in the report.</span></span> <span data-ttu-id="9d9ec-117">Nella Scheda dettaglio **Record da includere**, fare clic su **Filtro** e aggiungere i cespiti da includere nel report.</span><span class="sxs-lookup"><span data-stu-id="9d9ec-117">On the **Records to include** FastTab, click **Filter**, and add the assets you want to include in the report.</span></span>

6. <span data-ttu-id="9d9ec-118">Scegliere **OK** per generare il report.</span><span class="sxs-lookup"><span data-stu-id="9d9ec-118">Click **OK** to generate the report.</span></span>


## <a name="work-order-consumption-report"></a><span data-ttu-id="9d9ec-119">Report del consumo degli ordini di lavoro</span><span class="sxs-lookup"><span data-stu-id="9d9ec-119">Work order consumption report</span></span>

<span data-ttu-id="9d9ec-120">Dopo aver registrato il consumo negli ordini di lavoro, è possibile stampare un report su tale consumo.</span><span class="sxs-lookup"><span data-stu-id="9d9ec-120">When you have posted consumption on work orders, you can print a work order consumption report.</span></span> <span data-ttu-id="9d9ec-121">Il report visualizza ore, costi orari, costi degli articoli e spese registrate negli ordini di lavoro.</span><span class="sxs-lookup"><span data-stu-id="9d9ec-121">The report displays hours, hour costs, item costs, and expenses posted on work orders.</span></span>

1. <span data-ttu-id="9d9ec-122">Fare clic su **Gestione cespiti** > **Report** > **Ordini di lavoro** > **Consumo ordini di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="9d9ec-122">Click **Asset management** > **Reports** > **Work orders** > **Work order consumption**.</span></span>

2. <span data-ttu-id="9d9ec-123">Nella finestra di dialogo **Consumo ordini di lavoro**, selezionare i parametri da includere nel report impostando gli interruttori pertinenti della sezione **Mostra** su "Sì".</span><span class="sxs-lookup"><span data-stu-id="9d9ec-123">In the **Work order consumption** dialog, select the parameters you want to include in the report by selecting "Yes" on the relevant toggle buttons in the **Show** section.</span></span>

3. <span data-ttu-id="9d9ec-124">Selezionare un intervallo di date nella sezione **Date**.</span><span class="sxs-lookup"><span data-stu-id="9d9ec-124">Select a date interval in the **Dates** section.</span></span>

4. <span data-ttu-id="9d9ec-125">Nella Scheda dettaglio **Destinazione**, selezionare se si desidera visualizzare il report sullo schermo, stamparlo o salvarlo come file o messaggio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="9d9ec-125">On the **Destination** FastTab, select if you want to display the report on screen, print it, or save it as a file or email.</span></span>

5. <span data-ttu-id="9d9ec-126">Se necessario, è possibile selezionare specifici ordini di lavoro da visualizzare nel report.</span><span class="sxs-lookup"><span data-stu-id="9d9ec-126">If required, you can select specific work orders to be displayed in the report.</span></span> <span data-ttu-id="9d9ec-127">Nella Scheda dettaglio **Record da includere**, fare clic su **Filtro** e aggiungere gli ordini di lavoro da includere nel report.</span><span class="sxs-lookup"><span data-stu-id="9d9ec-127">On the **Records to include** FastTab, click **Filter**, and add the work orders you want to include in the report.</span></span>

6. <span data-ttu-id="9d9ec-128">Scegliere **OK** per generare il report.</span><span class="sxs-lookup"><span data-stu-id="9d9ec-128">Click **OK** to generate the report.</span></span>


>[!NOTE]
><span data-ttu-id="9d9ec-129">È inoltre possibile generare un [report di ordine di lavoro](../work-orders/work-order-report.md) contenente ulteriori dettagli su un ordine di lavoro.</span><span class="sxs-lookup"><span data-stu-id="9d9ec-129">You can also generate a [work order report](../work-orders/work-order-report.md), which contains more work order details.</span></span>

