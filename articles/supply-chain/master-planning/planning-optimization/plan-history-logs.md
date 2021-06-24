---
title: Visualizzare la cronologia del piano e i log di pianificazione
description: In questo argomento viene descritto come visualizzare lo storico dei processi di pianificazione generati dalla funzionalità di ottimizzazione di pianificazione.
author: ChristianRytt
ms.date: 10/30/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: MPSPlanRegenerationJobList, MPSPlanRegenerationJobLogs
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: d7bba084b03f8698c8bf31d171d5e4e486ed06ad
ms.sourcegitcommit: a7649b361ec54b49c0e9ee1c1c63a8815f320225
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2021
ms.locfileid: "6187249"
---
# <a name="view-plan-history-and-planning-logs"></a><span data-ttu-id="83e4c-103">Visualizzare la cronologia del piano e i log di pianificazione</span><span class="sxs-lookup"><span data-stu-id="83e4c-103">View plan history and planning logs</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="83e4c-104">In questo argomento viene descritto come visualizzare lo storico dei processi di pianificazione generati dalla funzionalità di ottimizzazione di pianificazione in Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="83e4c-104">This topic explains how to view the history of planning jobs that are triggered by the Planning Optimization functionality in Microsoft Dynamics 365 Supply Chain Management.</span></span>

<span data-ttu-id="83e4c-105">Per visualizzare lo storico per un piano, aprire il piano andando a **Pianificazione generale** \> **Impostazione** \> **Piani** \> **Piani generali** e **Storico**.</span><span class="sxs-lookup"><span data-stu-id="83e4c-105">To view the history for a plan, open the plan by going to **Master planning** \> **Setup** \> **Plans** \> **Master plans** and selecting **History**.</span></span> <span data-ttu-id="83e4c-106">Lo storico elenca tutti i processi per il piano selezionato.</span><span class="sxs-lookup"><span data-stu-id="83e4c-106">The history lists all the jobs for the selected plan.</span></span> <span data-ttu-id="83e4c-107">L'elenco include i processi attivi e completati.</span><span class="sxs-lookup"><span data-stu-id="83e4c-107">The list includes completed and active jobs.</span></span>

<span data-ttu-id="83e4c-108">La cronologia dei processi per le esecuzioni della pianificazione principale di Ottimizzazione pianificazione conserva solo fino a 60 record per piano generale.</span><span class="sxs-lookup"><span data-stu-id="83e4c-108">The history of jobs for Planning Optimization master planning runs keeps only up to 60 records per master plan.</span></span> <span data-ttu-id="83e4c-109">Ogni volta che si esegue un nuovo calcolo della pianificazione generale, il primo record cronologico di quel piano viene eliminato.</span><span class="sxs-lookup"><span data-stu-id="83e4c-109">Whenever you run a new master planning calculation, that plan's earliest history record is deleted.</span></span>

<span data-ttu-id="83e4c-110">Oltre a visualizzare l'ora di inizio e lo stato dei processi, è possibile visualizzare il log per un processo specifico.</span><span class="sxs-lookup"><span data-stu-id="83e4c-110">In addition to seeing the start time and status of jobs, you can view the log for a specific job.</span></span> <span data-ttu-id="83e4c-111">Il log include ulteriori informazioni e gli avvisi.</span><span class="sxs-lookup"><span data-stu-id="83e4c-111">The log includes additional information and warnings.</span></span> <span data-ttu-id="83e4c-112">Non tutti i processi hanno un log.</span><span class="sxs-lookup"><span data-stu-id="83e4c-112">Not all jobs have a log.</span></span> <span data-ttu-id="83e4c-113">Per visualizzare il log per un processo, selezionare **Log**.</span><span class="sxs-lookup"><span data-stu-id="83e4c-113">To view the log for a job, select **Log**.</span></span> <span data-ttu-id="83e4c-114">Le voci del registro vengono archiviate solo per 30 giorni dopo la data di completamento del processo, dopodiché vengono eliminate automaticamente.</span><span class="sxs-lookup"><span data-stu-id="83e4c-114">Log entries are only stored for 30 days after the date the job finished, after that they are automatically deleted.</span></span>

## <a name="related-resources"></a><span data-ttu-id="83e4c-115">Risorse correlate</span><span class="sxs-lookup"><span data-stu-id="83e4c-115">Related resources</span></span>

- [<span data-ttu-id="83e4c-116">Panoramica sull'ottimizzazione della pianificazione</span><span class="sxs-lookup"><span data-stu-id="83e4c-116">Planning Optimization overview</span></span>](planning-optimization-overview.md)
- [<span data-ttu-id="83e4c-117">Introduzione all'ottimizzazione della pianificazione</span><span class="sxs-lookup"><span data-stu-id="83e4c-117">Get started with Planning Optimization</span></span>](get-started.md)
- [<span data-ttu-id="83e4c-118">Analisi di adeguatezza dell'ottimizzazione di pianificazione</span><span class="sxs-lookup"><span data-stu-id="83e4c-118">Planning Optimization fit analysis</span></span>](planning-optimization-fit-analysis.md)
- [<span data-ttu-id="83e4c-119">Applicare i filtri a un piano</span><span class="sxs-lookup"><span data-stu-id="83e4c-119">Apply filters to a plan</span></span>](plan-filters.md)
- [<span data-ttu-id="83e4c-120">Annullare un processo di pianificazione</span><span class="sxs-lookup"><span data-stu-id="83e4c-120">Cancel a planning job</span></span>](cancel-planning-job.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]