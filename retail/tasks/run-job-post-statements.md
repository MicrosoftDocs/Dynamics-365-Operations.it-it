--- 
title: " Configurare ed eseguire un processo per registrare i rendiconti"
description: In questa procedura vengono descritti i passaggi per configurare ed eseguire un processo batch ricorrente al fine di registrare i rendiconti per un punto vendita o un gruppo di punti vendita selezionato.
author: josaw1
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 0e2dae54cc9ccfc0a85046c5478e539585c3744d
ms.contentlocale: it-it
ms.lasthandoff: 08/29/2017

---
# <a name="configure-and-run-a-job-to-post-statements"></a><span data-ttu-id="e0f39-103"> Configurare ed eseguire un processo per registrare i rendiconti</span><span class="sxs-lookup"><span data-stu-id="e0f39-103">Configure and run a job to post statements</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="e0f39-104">In questa procedura vengono descritti i passaggi per configurare ed eseguire un processo batch ricorrente al fine di registrare i rendiconti per un punto vendita o un gruppo di punti vendita selezionato.</span><span class="sxs-lookup"><span data-stu-id="e0f39-104">This procedure walks through configuring and running a recurrent batch job to post statements for a selected store or group of stores.</span></span> <span data-ttu-id="e0f39-105">Questa procedura utilizza i dati dimostrativi della società USRT.</span><span class="sxs-lookup"><span data-stu-id="e0f39-105">This procedure uses the USRT company in demo data.</span></span>

1. <span data-ttu-id="e0f39-106">Passare a Tutte le aree di lavoro </span><span class="sxs-lookup"><span data-stu-id="e0f39-106">Go to All workspaces > ..</span></span> <span data-ttu-id="e0f39-107">> Dati finanziari punto vendita al dettaglio.</span><span class="sxs-lookup"><span data-stu-id="e0f39-107">> Retail store financials.</span></span>
2. <span data-ttu-id="e0f39-108">Fare clic su Registra rendiconti.</span><span class="sxs-lookup"><span data-stu-id="e0f39-108">Click Post statements.</span></span>
    * <span data-ttu-id="e0f39-109">Selezionare una gerarchia organizzativa e quindi nella struttura dei nodi dell'organizzazione, selezionare un punto vendita o un nodo.</span><span class="sxs-lookup"><span data-stu-id="e0f39-109">Select an organizational hierarchy and then in the organization nodes tree, select either an individual store or a node.</span></span> <span data-ttu-id="e0f39-110">Selezionare un nodo se si desidera creare il processo batch per un gruppo di punti vendita.</span><span class="sxs-lookup"><span data-stu-id="e0f39-110">Select a node if you want to create the batch job for a group of stores.</span></span>  
    * <span data-ttu-id="e0f39-111">Fare clic sulla freccia per aggiungere la selezione.</span><span class="sxs-lookup"><span data-stu-id="e0f39-111">Click the arrow to add your selection.</span></span>  
3. <span data-ttu-id="e0f39-112">Fare clic sulla scheda Esecuzione in background.</span><span class="sxs-lookup"><span data-stu-id="e0f39-112">Click the Run in the background tab.</span></span>
4. <span data-ttu-id="e0f39-113">Selezionare o deselezionare la casella di controllo Elaborazione batch.</span><span class="sxs-lookup"><span data-stu-id="e0f39-113">Check or uncheck the Batch processing checkbox.</span></span>
5. <span data-ttu-id="e0f39-114">Fare clic su Ricorrenza.</span><span class="sxs-lookup"><span data-stu-id="e0f39-114">Click Recurrence.</span></span>
6. <span data-ttu-id="e0f39-115">Nel campo Data di inizio, immettere una data.</span><span class="sxs-lookup"><span data-stu-id="e0f39-115">In the Start date field, enter a date.</span></span>
7. <span data-ttu-id="e0f39-116">Immettere l'ora nel campo Ora di inizio.</span><span class="sxs-lookup"><span data-stu-id="e0f39-116">In the Start time field, enter a time.</span></span>
    * <span data-ttu-id="e0f39-117">Selezionare se si desidera terminare la ricorrenza dopo un numero specifico di cicli, a una data specifica o mai.</span><span class="sxs-lookup"><span data-stu-id="e0f39-117">Choose whether you want to end the recurrence after a specific number of runs, at a specific date, or never.</span></span> <span data-ttu-id="e0f39-118">Quindi scegliere le varie opzioni per definire la frequenza di esecuzione del processo.</span><span class="sxs-lookup"><span data-stu-id="e0f39-118">Then choose the various options to define how frequently you want the job to run.</span></span>  
8. <span data-ttu-id="e0f39-119">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="e0f39-119">Click OK.</span></span>
9. <span data-ttu-id="e0f39-120">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="e0f39-120">Click OK.</span></span>

