---
title: Ottimizzare le prestazioni pianificando i processi batch dopo le ore lavorative
description: In questo argomento viene spiegato come risolvere problemi di prestazioni con Microsoft Dynamics 365 Human Resources pianificando i processi di lunga durata dopo le ore lavorative.
author: andreabichsel
manager: AnnBe
ms.date: 06/23/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-06-23
ms.dyn365.ops.version: Platform update 24
ms.openlocfilehash: 452a87cf5ba6c1ac73636584d75b2ec2ac555e02
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/17/2020
ms.locfileid: "4527767"
---
# <a name="optimize-performance-by-scheduling-batch-jobs-after-hours"></a><span data-ttu-id="cbca8-103">Ottimizzare le prestazioni pianificando i processi batch dopo le ore lavorative</span><span class="sxs-lookup"><span data-stu-id="cbca8-103">Optimize performance by scheduling batch jobs after hours</span></span>

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

## <a name="issue"></a><span data-ttu-id="cbca8-104">Uscita</span><span class="sxs-lookup"><span data-stu-id="cbca8-104">Issue</span></span>

<span data-ttu-id="cbca8-105">In Microsoft Dynamics 365 Human Resources possono verificarsi problemi di prestazioni se i processi batch di lunga durata vengono eseguiti durante le normali ore lavorative.</span><span class="sxs-lookup"><span data-stu-id="cbca8-105">Microsoft Dynamics 365 Human Resources can experience performance issues if long-running batch jobs run during typical business hours.</span></span>

## <a name="resolution"></a><span data-ttu-id="cbca8-106">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="cbca8-106">Resolution</span></span>

<span data-ttu-id="cbca8-107">Pianifica i seguenti processi batch durante le ore non lavorative.</span><span class="sxs-lookup"><span data-stu-id="cbca8-107">Schedule the following batch jobs during off hours.</span></span> <span data-ttu-id="cbca8-108">Si consiglia inoltre di rivedere la frequenza dei processi batch eseguiti frequentemente.</span><span class="sxs-lookup"><span data-stu-id="cbca8-108">We also recommend reviewing the frequency of batch jobs that run frequently.</span></span> <span data-ttu-id="cbca8-109">Se possibile, riduci la ricorrenza del processo batch.</span><span class="sxs-lookup"><span data-stu-id="cbca8-109">If possible, reduce the recurrence of the batch job.</span></span> <span data-ttu-id="cbca8-110">In molti casi, la frequenza predefinita è sufficiente.</span><span class="sxs-lookup"><span data-stu-id="cbca8-110">In many cases, the default frequency is sufficient.</span></span>

<span data-ttu-id="cbca8-111">I seguenti processi batch devono essere eseguiti di notte o dopo le ore lavorative.</span><span class="sxs-lookup"><span data-stu-id="cbca8-111">The following batch jobs should run at night or after hours.</span></span> <span data-ttu-id="cbca8-112">Assicurari di controllare il fuso orario per questi processi batch ricorrenti.</span><span class="sxs-lookup"><span data-stu-id="cbca8-112">Be sure to check the time zone for these recurring batch jobs.</span></span> <span data-ttu-id="cbca8-113">Alcuni processi batch potrebbero utilizzare Pacific Standard Time (PST).</span><span class="sxs-lookup"><span data-stu-id="cbca8-113">Some batch jobs might use Pacific Standard Time (PST).</span></span>

| <span data-ttu-id="cbca8-114">Processo batch</span><span class="sxs-lookup"><span data-stu-id="cbca8-114">Batch job</span></span> | <span data-ttu-id="cbca8-115">Occorrenza predefinita</span><span class="sxs-lookup"><span data-stu-id="cbca8-115">Default occurrence</span></span> |
| --- | --- |
| <span data-ttu-id="cbca8-116">Pulizia Storico processi batch</span><span class="sxs-lookup"><span data-stu-id="cbca8-116">Batch job history cleanup</span></span> | <span data-ttu-id="cbca8-117">1 volta al mese</span><span class="sxs-lookup"><span data-stu-id="cbca8-117">1 time per month</span></span> |
| <span data-ttu-id="cbca8-118">Esporta pulizia gestione temporanea</span><span class="sxs-lookup"><span data-stu-id="cbca8-118">Export staging cleanup</span></span> | <span data-ttu-id="cbca8-119">1 volta al giorno</span><span class="sxs-lookup"><span data-stu-id="cbca8-119">1 time per day</span></span> |
| <span data-ttu-id="cbca8-120">Sincronizzazione richiesta mancante integrazione Common Data Service</span><span class="sxs-lookup"><span data-stu-id="cbca8-120">Common Data Service integration missed request sync</span></span> | <span data-ttu-id="cbca8-121">1 volta al giorno</span><span class="sxs-lookup"><span data-stu-id="cbca8-121">1 time per day</span></span> |
| <span data-ttu-id="cbca8-122">Processo del sistema di compressione del database che deve essere eseguito regolarmente durante le ore non lavorative</span><span class="sxs-lookup"><span data-stu-id="cbca8-122">Database compression system job that needs to run regularly during off hours</span></span> | <span data-ttu-id="cbca8-123">1 volta al giorno</span><span class="sxs-lookup"><span data-stu-id="cbca8-123">1 time per day</span></span> |
| <span data-ttu-id="cbca8-124">Processo del sistema di ricostruzione dell'indice del database che deve essere eseguito regolarmente durante le ore non lavorative</span><span class="sxs-lookup"><span data-stu-id="cbca8-124">Database index rebuild system job that needs to run regularly during off hours</span></span> | <span data-ttu-id="cbca8-125">1 volta al giorno</span><span class="sxs-lookup"><span data-stu-id="cbca8-125">1 time per day</span></span> |

1. <span data-ttu-id="cbca8-126">In Risorse umane, selezionare **Amministrazione sistema**.</span><span class="sxs-lookup"><span data-stu-id="cbca8-126">In Human Resources, select **System administration**.</span></span>

2. <span data-ttu-id="cbca8-127">Nella barra **Cerca**, cerca uno dei processi batch sopra indicati.</span><span class="sxs-lookup"><span data-stu-id="cbca8-127">In the **Search** bar, search for one of the above batch jobs.</span></span>

3. <span data-ttu-id="cbca8-128">Selezionare **Esecuzione in background** e quindi selezionare **Ricorrenza**.</span><span class="sxs-lookup"><span data-stu-id="cbca8-128">Select **Run in the background**, and then select **Recurrence**.</span></span>

   ![Impostare la ricorrenza](media/talent-batch-history-cleanup-recurrence.png)

4. <span data-ttu-id="cbca8-130">In **Definisci ricorrenza**, impostare la **Data di inizio** e **Ora di inizio** in modo che si verificano durante le ore non lavorative o nel fine settimana.</span><span class="sxs-lookup"><span data-stu-id="cbca8-130">Under **Define recurrence**, set the **Start date** and **Start time** to occur during off hours or the weekend.</span></span> <span data-ttu-id="cbca8-131">Seleziona **Nessuna data di fine**.</span><span class="sxs-lookup"><span data-stu-id="cbca8-131">Select **No end date**.</span></span> 

   ![Definire la data e l'ora di inizio della ricorrenza](media/talent-batch-history-cleanup-define-recurrence.png)

5. <span data-ttu-id="cbca8-133">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="cbca8-133">Select **OK**.</span></span>

6. <span data-ttu-id="cbca8-134">Se necessario, apporta le modifiche a tutti gli altri parametri in **Esegui in background** e selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="cbca8-134">If needed, change any other parameters under **Run in the background**, and then select **OK**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="cbca8-135">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="cbca8-135">Additional resources</span></span>

[<span data-ttu-id="cbca8-136">Ottimizzare le prestazioni con attività di pulizia automatica</span><span class="sxs-lookup"><span data-stu-id="cbca8-136">Optimize performance with auto cleanup tasks</span></span>](hr-admin-troubleshooting-batch-history.md)
