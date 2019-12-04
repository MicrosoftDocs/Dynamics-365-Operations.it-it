---
title: Annullare un processo di pianificazione
description: In questo argomento viene descritto come annullare un processo attivo di pianificazione che utilizza la funzionalità di ottimizzazione di pianificazione.
author: ChristianRytt
manager: AnnBe
ms.date: 10/26/2019
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
ms.openlocfilehash: a2d90f04985fdd66ca83582ee676100fffb26981
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/06/2019
ms.locfileid: "2773992"
---
[!include [banner](../../includes/banner.md)]
[!include [banner](../../includes/preview-banner.md)]

# <a name="cancel-a-planning-job"></a><span data-ttu-id="9396a-103">Annullare un processo di pianificazione</span><span class="sxs-lookup"><span data-stu-id="9396a-103">Cancel a planning job</span></span>

<span data-ttu-id="9396a-104">In Microsoft Dynamics 365 Supply Chain Management è possibile annullare un processo attivo di pianificazione che utilizza la funzionalità di ottimizzazione di pianificazione.</span><span class="sxs-lookup"><span data-stu-id="9396a-104">In Microsoft Dynamics 365 Supply Chain Management, you can cancel an active planning job that uses the Planning Optimization functionality.</span></span>

<span data-ttu-id="9396a-105">Per annullare un processo attivo di pianificazione, effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="9396a-105">To cancel an active planning job, follow these steps.</span></span>

> [!NOTE]
> <span data-ttu-id="9396a-106">Solo i processi attivo possono essere annullati.</span><span class="sxs-lookup"><span data-stu-id="9396a-106">Only active jobs can be canceled.</span></span>

1. <span data-ttu-id="9396a-107">Passare a **Pianificazione generale \> Impostazione \> Piani**.</span><span class="sxs-lookup"><span data-stu-id="9396a-107">Go to **Master planning \> Setup \> Plans**.</span></span>
2. <span data-ttu-id="9396a-108">Selezionare un piano appropriato per l'esecuzione di pianificazione.</span><span class="sxs-lookup"><span data-stu-id="9396a-108">Select an appropriate plan for the planning run.</span></span>
3. <span data-ttu-id="9396a-109">Selezionare **Storico**.</span><span class="sxs-lookup"><span data-stu-id="9396a-109">Select **History**.</span></span>
4. <span data-ttu-id="9396a-110">Selezionare il processo di pianificazione da annullare.</span><span class="sxs-lookup"><span data-stu-id="9396a-110">Select the planning job to cancel.</span></span>
5. <span data-ttu-id="9396a-111">Selezionare **Annulla**.</span><span class="sxs-lookup"><span data-stu-id="9396a-111">Select **Cancel**.</span></span>

<span data-ttu-id="9396a-112">Lo stato del processo sarà **Annullamento in corso** finché il servizio di ottimizzazione di pianificazione non conferma che il processo è stato annullato.</span><span class="sxs-lookup"><span data-stu-id="9396a-112">The job status will be **Canceling** until the Planning Optimization service confirms that the job has been canceled.</span></span> <span data-ttu-id="9396a-113">Lo stato quindi diventa **Annullato**.</span><span class="sxs-lookup"><span data-stu-id="9396a-113">The status will then be changed to **Canceled**.</span></span>

> [!NOTE]
> <span data-ttu-id="9396a-114">Per visualizzare le modifiche di stato, è necessario aggiornare la pagina facendo clic sul pulsante **Aggiorna**.</span><span class="sxs-lookup"><span data-stu-id="9396a-114">To see status changes, you must refresh the page by selecting the **Refresh** button.</span></span>

## <a name="related-resources"></a><span data-ttu-id="9396a-115">Risorse correlate</span><span class="sxs-lookup"><span data-stu-id="9396a-115">Related resources</span></span>

[<span data-ttu-id="9396a-116">Panoramica dell'ottimizzazione di pianificazione</span><span class="sxs-lookup"><span data-stu-id="9396a-116">Planning Optimization overview</span></span>](planning-optimization-overview.md)

[<span data-ttu-id="9396a-117">Introduzione all'ottimizzazione di pianificazione</span><span class="sxs-lookup"><span data-stu-id="9396a-117">Get started with Planning Optimization</span></span>](get-started.md)

[<span data-ttu-id="9396a-118">Analisi di adeguatezza dell'ottimizzazione di pianificazione</span><span class="sxs-lookup"><span data-stu-id="9396a-118">Planning Optimization fit analysis</span></span>](planning-optimization-fit-analysis.md)

[<span data-ttu-id="9396a-119">Visualizzare la cronologia del piano e i log di pianificazione</span><span class="sxs-lookup"><span data-stu-id="9396a-119">View plan history and planning logs</span></span>](plan-history-logs.md)

[<span data-ttu-id="9396a-120">Applicare i filtri a un piano</span><span class="sxs-lookup"><span data-stu-id="9396a-120">Apply filters to a plan</span></span>](plan-filters.md)
