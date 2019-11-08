---
title: Distribuire un ordine di lavoro
description: Nell'argomento viene descritto come distribuire un ordine di lavoro in Gestione cespiti.
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
ms.openlocfilehash: 026b34934d6527416a4632d8e1aee76a8836dcb0
ms.sourcegitcommit: fb66731f05207094149a6bc7b8549a4dabbb071a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2019
ms.locfileid: "2652013"
---
# <a name="dispatch-work-order"></a><span data-ttu-id="5dd3e-103">Distribuire un ordine di lavoro</span><span class="sxs-lookup"><span data-stu-id="5dd3e-103">Dispatch work order</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="5dd3e-104">È possibile programmare un ordine di lavoro o processi di ordine di lavoro utilizzando la funzionalità **Spedisci**.</span><span class="sxs-lookup"><span data-stu-id="5dd3e-104">You can schedule one work order or work order jobs to one worker using the **Dispatch** functionality.</span></span>

1. <span data-ttu-id="5dd3e-105">Fare clic su **Gestione cespiti** > **Comune** > **Ordini di lavoro** > **Tutti gli ordini di lavoro** o **Ordini di lavoro attivi**.</span><span class="sxs-lookup"><span data-stu-id="5dd3e-105">Click **Asset management** > **Common** > **Work orders** > **All Work orders** or **Active work orders**.</span></span>

2. <span data-ttu-id="5dd3e-106">Selezionare l'ordine di lavoro nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="5dd3e-106">Select the work order in the list.</span></span>

3. <span data-ttu-id="5dd3e-107">Nella scheda **Generale** fare clic su **Spedisci**.</span><span class="sxs-lookup"><span data-stu-id="5dd3e-107">On the **General** tab, click **Dispatch**.</span></span>

4. <span data-ttu-id="5dd3e-108">Nella finestra dialogo **Programma ordine di lavoro**, selezionare il lavoratore nel campo **Lavoratore**.</span><span class="sxs-lookup"><span data-stu-id="5dd3e-108">In the **Schedule work order** dialog, select the worker in the **Worker** field.</span></span>

5. <span data-ttu-id="5dd3e-109">Nel campo **Programma ore**, è possibile inserire le ore di lavoro previste nel caso differiscano dalle ore previste.</span><span class="sxs-lookup"><span data-stu-id="5dd3e-109">In the **Schedule hours** field, you can insert expected work hours in case expected work hours differ from forecast hours.</span></span>

6. <span data-ttu-id="5dd3e-110">Nel campo **Inizio programmato**, è possibile modificare la data e l'ora di inizio, se necessario.</span><span class="sxs-lookup"><span data-stu-id="5dd3e-110">In the **Scheduled start** field, you can edit start date and time, if required.</span></span>

7. <span data-ttu-id="5dd3e-111">Se il processo di programmazione deve rispettare i limiti di capacità in relazione alle risorse già programmate in altri processi, assicurarsi che gli interruttori **Cespite**, **Strumento** e **Lavoratore** siano impostati su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="5dd3e-111">If the scheduling process should observe capacity limitations regarding resources already scheduled on other jobs, make sure that the **Asset**, **Tool**, and **Worker** toggle buttons are set to **Yes**.</span></span> <span data-ttu-id="5dd3e-112">Se si desidera visualizzare informazioni dettagliate sul processo di programmazione, impostare l'interruttore **Dettagli** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="5dd3e-112">If you want to see detailed information about the scheduling process, select **Yes** on the **Verbose** toggle button.</span></span> <span data-ttu-id="5dd3e-113">Ciò significa che le informazioni dettagliate sui punteggi calcolati nell'ordine di lavoro sono visualizzati nel Registro informazioni.</span><span class="sxs-lookup"><span data-stu-id="5dd3e-113">This means detailed information about the calculated scores on the work order is shown in the Infolog.</span></span>

8. <span data-ttu-id="5dd3e-114">Impostare l'interruttore **Ignora programmazione** su **Sì** per ignorare i giorni chiusi nel calendario (si applica a cespite, lavoratore e strumenti).</span><span class="sxs-lookup"><span data-stu-id="5dd3e-114">Select **Yes** on the **Ignore schedule** toggle button to ignore closed days in the calendar (applies to asset, worker, and tools).</span></span> <span data-ttu-id="5dd3e-115">Impostare l'interruttore **Ignora esecuzione programmata** su **Sì** per ignorare le limitazioni eventualmente selezionate nell'ordine di lavoro relativo alla programmazione.</span><span class="sxs-lookup"><span data-stu-id="5dd3e-115">Select **Yes** on the **Ignore scheduled execution** toggle button to ignore limitations that may have been selected on the work order regarding scheduling.</span></span> 

    <span data-ttu-id="5dd3e-116">Per informazioni sull'impostazione dell'esecuzione programmata fare riferimento alla sezione [Esecuzione programmata](../setup-for-work-orders/scheduled-execution.md).</span><span class="sxs-lookup"><span data-stu-id="5dd3e-116">For information on the setup of scheduled execution, see the [Scheduled execution](../setup-for-work-orders/scheduled-execution.md) section.</span></span>

9. <span data-ttu-id="5dd3e-117">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="5dd3e-117">Click **OK**.</span></span> <span data-ttu-id="5dd3e-118">Lo stato del ciclo di vita di ordine di lavoro viene aggiornato automaticamente allo stato del ciclo di vita **Programmato** specificato in **Gestione cespiti** > **Impostazione** > **Ordini di lavoro** > **Modelli del ciclo di vita**.</span><span class="sxs-lookup"><span data-stu-id="5dd3e-118">The work order lifecycle state is automatically updated to the **Scheduled** lifecycle state specified **Asset management** > **Setup** > **Work orders** > **Lifecycle models**.</span></span>

<span data-ttu-id="5dd3e-119">Nella figura seguente è illustrato un esempio di selezioni di distribuzione nella finestra di dialogo **Programma ordine di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="5dd3e-119">The figure below shows an example of dispatch selections in the **Schedule work order** dialog.</span></span>

![Figura 1](media/04-work-order-scheduling.png)

[!NOTE]
<span data-ttu-id="5dd3e-121">Se si desidera eliminare la programmazione in un ordine di lavoro, selezionare l'ordine di lavoro **Tutti gli ordini di lavoro** e fare clic su **Elimina programmazione** nella scheda **Generale**. Aggiornare manualmente lo stato del ciclo di vita di ordine di lavoro se si elimina la programmazione.</span><span class="sxs-lookup"><span data-stu-id="5dd3e-121">If you want to delete the schedule on a work order, select the work order in **All work orders**, and then click **Delete schedule** on the **General** tab. Remember to manually update the work order lifecycle state if you delete the schedule.</span></span>

