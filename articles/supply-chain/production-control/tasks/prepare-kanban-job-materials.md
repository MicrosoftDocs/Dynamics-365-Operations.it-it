---
title: Preparare un processo kanban quando sono disponibili materiali per la cella di lavoro
description: Questa attività riguarda la preparazione di un processo kanban di lavorazione quando tutti i materiali sono disponibili per la cella di lavoro.
author: johanhoffmann
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanBoardWorkCell
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: cf163968474e91da7e3d47fd638a857a76179645
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/18/2020
ms.locfileid: "3148977"
---
# <a name="prepare-a-process-kanban-job-when-materials-are-available-for-the-work-cell"></a><span data-ttu-id="3d537-103">Preparare un processo kanban quando sono disponibili materiali per la cella di lavoro</span><span class="sxs-lookup"><span data-stu-id="3d537-103">Prepare a process kanban job when materials are available for the work cell</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="3d537-104">Questa attività riguarda la preparazione di un processo kanban di lavorazione quando tutti i materiali sono disponibili per la cella di lavoro.</span><span class="sxs-lookup"><span data-stu-id="3d537-104">This task focuses on preparing a process kanban job when all materials are available for the work cell.</span></span> <span data-ttu-id="3d537-105">La società di dati dimostrativi utilizzata per creare questa attività è USMF.</span><span class="sxs-lookup"><span data-stu-id="3d537-105">The demo data company used to create this task is USMF.</span></span> <span data-ttu-id="3d537-106">Questa attività è destinata all'operatore.</span><span class="sxs-lookup"><span data-stu-id="3d537-106">This task is intended for the machine operator.</span></span>

1. <span data-ttu-id="3d537-107">Andare a Bacheca kanban per i processi lavorazione.</span><span class="sxs-lookup"><span data-stu-id="3d537-107">Go to Kanban board for process jobs.</span></span>
2. <span data-ttu-id="3d537-108">Nel campo Cella di lavoro fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="3d537-108">In the Work cell field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="3d537-109">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="3d537-109">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="3d537-110">Selezionare la cella di lavoro 1250 e fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="3d537-110">Select work cell 1250 and click OK.</span></span>  
4. <span data-ttu-id="3d537-111">Nell'elenco selezionare la riga 4.</span><span class="sxs-lookup"><span data-stu-id="3d537-111">In the list, select row 4.</span></span>
    * <span data-ttu-id="3d537-112">Nella società dimostrativa senza dati, il processo kanban 000329 nella riga 4 è il primo processo non ancora completato.</span><span class="sxs-lookup"><span data-stu-id="3d537-112">In the clean demo company, Kanban 000329 in row 4 is the first job that is not completed yet.</span></span>  
5. <span data-ttu-id="3d537-113">Attivare/disattivare l'espansione della sezione Distinta di prelievo.</span><span class="sxs-lookup"><span data-stu-id="3d537-113">Toggle the expansion of the Picking list section.</span></span>
    * <span data-ttu-id="3d537-114">Verificare che lo stato della fornitura sia disponibile per tutti gli articoli nella distinta di prelievo.</span><span class="sxs-lookup"><span data-stu-id="3d537-114">Verify that the supply status is available for all items in the picking list.</span></span>  
    * <span data-ttu-id="3d537-115">Se più processi vengono selezionati, la distinta di prelievo indicherà somma di tutti gli articoli necessari per i processi selezionati.</span><span class="sxs-lookup"><span data-stu-id="3d537-115">If multiple jobs are selected, the picking list will show the sum of all items needed for the selected jobs.</span></span>  
6. <span data-ttu-id="3d537-116">Fare clic su Prepara.</span><span class="sxs-lookup"><span data-stu-id="3d537-116">Click Prepare.</span></span>
    * <span data-ttu-id="3d537-117">Il processo di preparazione è ora completato.</span><span class="sxs-lookup"><span data-stu-id="3d537-117">The preparation process is now completed.</span></span> <span data-ttu-id="3d537-118">La casella di controllo selezionata per tutte le righe della distinta di prelievo indica che lo stato della fornitura è Prelevato.</span><span class="sxs-lookup"><span data-stu-id="3d537-118">The selected check box for all rows in the picking list indicates that the supply status is picked.</span></span>  

