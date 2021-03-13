---
title: Ottimizzare le prestazioni con attività di pulizia automatica
description: In questo articolo viene spiegato come risolvere alcuni problemi di prestazioni con Microsoft Dynamics 365 Human Resources tramite la pulizia della cronologia dei processi batch.
author: andreabichsel
manager: tfehr
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Platform update 24
ms.openlocfilehash: 97f6e310d3a69c870fe8ef03bd7a10cc7ab652e5
ms.sourcegitcommit: ea2d652867b9b83ce6e5e8d6a97d2f9460a84c52
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2021
ms.locfileid: "5113115"
---
# <a name="optimize-performance-with-auto-cleanup-tasks"></a><span data-ttu-id="3433f-103">Ottimizzare le prestazioni con le attività di pulizia automatiche</span><span class="sxs-lookup"><span data-stu-id="3433f-103">Optimize performance with auto cleanup tasks</span></span>

<span data-ttu-id="3433f-104">**Problema**</span><span class="sxs-lookup"><span data-stu-id="3433f-104">**Issue**</span></span>

<span data-ttu-id="3433f-105">Microsoft Dynamics 365 Human Resources può riscontrare problemi di prestazioni se la cronologia dei processi batch diventa troppo grande.</span><span class="sxs-lookup"><span data-stu-id="3433f-105">Microsoft Dynamics 365 Human Resources can experience performance issues if the batch job history grows too large.</span></span>

<span data-ttu-id="3433f-106">**Causa**</span><span class="sxs-lookup"><span data-stu-id="3433f-106">**Cause**</span></span>

<span data-ttu-id="3433f-107">I processi batch eseguiti frequentemente possono portare a una crescita insostenibile della cronologia dei processi batch.</span><span class="sxs-lookup"><span data-stu-id="3433f-107">Batch jobs that run frequently can lead to unsustainable growth of the batch job history.</span></span> <span data-ttu-id="3433f-108">Questo può causare problemi di prestazioni.</span><span class="sxs-lookup"><span data-stu-id="3433f-108">This can cause performance issues.</span></span> 

<span data-ttu-id="3433f-109">**Risoluzione**</span><span class="sxs-lookup"><span data-stu-id="3433f-109">**Resolution**</span></span>

<span data-ttu-id="3433f-110">Pianificare un'attività automatica per ripulire la cronologia dei processi batch.</span><span class="sxs-lookup"><span data-stu-id="3433f-110">Schedule an automatic task to clean up your batch job history.</span></span> <span data-ttu-id="3433f-111">Si consiglia di impostare l'attività da eseguire settimanalmente, ma potrebbe essere necessario eseguire la pulizia più o meno frequentemente, a seconda del proprio ambiente.</span><span class="sxs-lookup"><span data-stu-id="3433f-111">We recommend setting up the task to run weekly, but you might need to run the cleanup more or less frequently, depending on your environment.</span></span> <span data-ttu-id="3433f-112">La seguente procedura contiene le impostazioni consigliate, ma è possibile modificarle in base alle proprie esigenze.</span><span class="sxs-lookup"><span data-stu-id="3433f-112">The following procedure contains our recommended settings, but you can change these according to your needs.</span></span>

1. <span data-ttu-id="3433f-113">In Risorse umane, selezionare **Amministrazione sistema**.</span><span class="sxs-lookup"><span data-stu-id="3433f-113">In Human Resources, select **System administration**.</span></span>

2. <span data-ttu-id="3433f-114">Nella barra **Ricerca**, immettere **Pulizia storico processi batch**.</span><span class="sxs-lookup"><span data-stu-id="3433f-114">In the **Search** bar, enter **Batch job history clean-up**.</span></span>

   ![Cercare Pulizia storico processi batch](media/talent-batch-history-cleanup-search-bar.png)

3. <span data-ttu-id="3433f-116">In **Limite cronologico (giorni)**, immettere **30**.</span><span class="sxs-lookup"><span data-stu-id="3433f-116">In **History limit (days)**, enter **30**.</span></span>

   ![Impostare il limite cronologico su 30](media/talent-batch-history-cleanup-history-limit.png)

4. <span data-ttu-id="3433f-118">Selezionare **Esecuzione in background** e quindi selezionare **Ricorrenza**.</span><span class="sxs-lookup"><span data-stu-id="3433f-118">Select **Run in the background** and then select **Recurrence**.</span></span>

   ![Impostare la ricorrenza](media/talent-batch-history-cleanup-recurrence.png)

5. <span data-ttu-id="3433f-120">In **Definisci ricorrenza**, impostare la **Data di inizio** e **Ora di inizio** in modo che si verificano durante le ore non lavorative o nel fine settimana, quindi selezionare **Nessuna data di fine**.</span><span class="sxs-lookup"><span data-stu-id="3433f-120">Under **Define recurrence**, set the **Start date** and **Start time** to occur during off-hours or the weekend, and then select **NO END DATE**.</span></span> 

   ![Definire la data e l'ora di inizio della ricorrenza](media/talent-batch-history-cleanup-define-recurrence.png)

6. <span data-ttu-id="3433f-122">In **Criterio di ricorrenza**, selezionare **Giorni** e impostare **Ripeti dopo l'intervallo specificato** su **7**.</span><span class="sxs-lookup"><span data-stu-id="3433f-122">Under **RECURRENCE PATTERN**, select **Days** and set **REPEAT AFTER SPECIFIED INTERVAL** to **7**.</span></span>

   ![Impostare la pulizia con frequenza settimanale](media/talent-batch-history-cleanup-recurrence-pattern.png)

7. <span data-ttu-id="3433f-124">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="3433f-124">Select **OK**.</span></span>

8. <span data-ttu-id="3433f-125">Apportare le modifiche necessarie a tutti gli altri parametri in **Esegui in background** e selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="3433f-125">Change any other parameters under **Run in the background** as necessary, and then select **OK**.</span></span>

