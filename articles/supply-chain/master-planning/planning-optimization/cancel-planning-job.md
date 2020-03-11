---
title: Annullare un processo di pianificazione
description: In questo argomento viene descritto come annullare un processo attivo di pianificazione che utilizza la funzionalità di ottimizzazione di pianificazione.
author: ChristianRytt
manager: AnnBe
ms.date: 02/18/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: 18c5c7b8030fc6adbc548dab750e4f454aebc867
ms.sourcegitcommit: a688c864fc609e35072ad8fd2c01d71f6a5ee7b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/20/2020
ms.locfileid: "3076349"
---
# <a name="cancel-a-planning-job"></a><span data-ttu-id="05110-103">Annullare un processo di pianificazione</span><span class="sxs-lookup"><span data-stu-id="05110-103">Cancel a planning job</span></span>

[!include [banner](../../includes/banner.md)]
[!include [banner](../../includes/preview-banner.md)]

<span data-ttu-id="05110-104">In Microsoft Dynamics 365 Supply Chain Management è possibile annullare un processo attivo di pianificazione che utilizza la funzionalità di ottimizzazione di pianificazione.</span><span class="sxs-lookup"><span data-stu-id="05110-104">In Microsoft Dynamics 365 Supply Chain Management, you can cancel an active planning job that uses the Planning optimization functionality.</span></span> <span data-ttu-id="05110-105">Quando si seleziona **Annulla** nella finestra di dialogo e un processo di ottimizzazione di pianificazione viene attivato direttamente dall'interfaccia utente (non in background), il processo di ottimizzazione di pianificazione non verrà annullato.</span><span class="sxs-lookup"><span data-stu-id="05110-105">When you select **Cancel** in the dialog box when a Planning optimization job is triggered directly from the user interface (not in the background), this will not cancel the Planning optimization job.</span></span> <span data-ttu-id="05110-106">Anche se si riceve un avviso come "Operazione annullata", sarà comunque necessario utilizzare i seguenti passaggi per annullare un processo di pianificazione con l'ottimizzazione della pianificazione.</span><span class="sxs-lookup"><span data-stu-id="05110-106">Even if you receive a warning such as “Operation canceled”, you will still need to use the following steps to cancel a planning job with Planning optimization.</span></span>


<span data-ttu-id="05110-107">Per annullare un processo attivo di pianificazione, effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="05110-107">To cancel an active planning job, follow these steps.</span></span> 

> [!NOTE]
> <span data-ttu-id="05110-108">Solo i processi attivo possono essere annullati.</span><span class="sxs-lookup"><span data-stu-id="05110-108">Only active jobs can be canceled.</span></span>

1. <span data-ttu-id="05110-109">Passare a **Pianificazione generale \> Impostazione \> Piani**.</span><span class="sxs-lookup"><span data-stu-id="05110-109">Go to **Master planning \> Setup \> Plans**.</span></span>
2. <span data-ttu-id="05110-110">Selezionare un piano appropriato per l'esecuzione di pianificazione.</span><span class="sxs-lookup"><span data-stu-id="05110-110">Select an appropriate plan for the planning run.</span></span>
3. <span data-ttu-id="05110-111">Selezionare **Storico**.</span><span class="sxs-lookup"><span data-stu-id="05110-111">Select **History**.</span></span>
4. <span data-ttu-id="05110-112">Selezionare il processo di pianificazione da annullare.</span><span class="sxs-lookup"><span data-stu-id="05110-112">Select the planning job to cancel.</span></span>
5. <span data-ttu-id="05110-113">Selezionare **Annulla**.</span><span class="sxs-lookup"><span data-stu-id="05110-113">Select **Cancel**.</span></span>

<span data-ttu-id="05110-114">Lo stato del processo sarà **Annullamento in corso** finché il servizio di ottimizzazione di pianificazione non conferma che il processo è stato annullato.</span><span class="sxs-lookup"><span data-stu-id="05110-114">The job status will be **Canceling** until the Planning Optimization service confirms that the job has been canceled.</span></span> <span data-ttu-id="05110-115">Lo stato quindi diventa **Annullato**.</span><span class="sxs-lookup"><span data-stu-id="05110-115">The status will then be changed to **Canceled**.</span></span>

> [!NOTE]
> <span data-ttu-id="05110-116">Per visualizzare le modifiche di stato, è necessario aggiornare la pagina facendo clic sul pulsante **Aggiorna**.</span><span class="sxs-lookup"><span data-stu-id="05110-116">To see status changes, you must refresh the page by selecting the **Refresh** button.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="05110-117">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="05110-117">Additional resources</span></span>

[<span data-ttu-id="05110-118">Panoramica sull'ottimizzazione della pianificazione</span><span class="sxs-lookup"><span data-stu-id="05110-118">Planning Optimization overview</span></span>](planning-optimization-overview.md)

[<span data-ttu-id="05110-119">Introduzione all'ottimizzazione della pianificazione</span><span class="sxs-lookup"><span data-stu-id="05110-119">Get started with Planning Optimization</span></span>](get-started.md)

[<span data-ttu-id="05110-120">Analisi di adeguatezza dell'ottimizzazione di pianificazione</span><span class="sxs-lookup"><span data-stu-id="05110-120">Planning Optimization fit analysis</span></span>](planning-optimization-fit-analysis.md)

[<span data-ttu-id="05110-121">Visualizzare la cronologia del piano e i log di pianificazione</span><span class="sxs-lookup"><span data-stu-id="05110-121">View plan history and planning logs</span></span>](plan-history-logs.md)

[<span data-ttu-id="05110-122">Applicare i filtri a un piano</span><span class="sxs-lookup"><span data-stu-id="05110-122">Apply filters to a plan</span></span>](plan-filters.md)
