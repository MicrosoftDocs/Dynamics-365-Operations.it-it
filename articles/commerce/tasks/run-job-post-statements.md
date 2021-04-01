---
title: Configurare ed eseguire il processo per registrare i rendiconti
description: In questa procedura vengono descritti i passaggi per configurare ed eseguire un processo batch ricorrente al fine di registrare i rendiconti per un punto vendita o un gruppo di punti vendita selezionato.
author: josaw1
manager: AnnBe
ms.date: 07/29/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailChannelOperationsWorkspace, RetailOperatingUnitPicker, SysRecurrence
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2b1401d51491205731843abe6e2278f798c5c979
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5232739"
---
# <a name="configure-and-run-job-to-post-statements"></a><span data-ttu-id="e0f1b-103">Configurare ed eseguire il processo per registrare i rendiconti</span><span class="sxs-lookup"><span data-stu-id="e0f1b-103">Configure and run job to post statements</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e0f1b-104">In questa procedura vengono descritti i passaggi per configurare ed eseguire un processo batch ricorrente al fine di registrare i rendiconti per un punto vendita o un gruppo di punti vendita selezionato.</span><span class="sxs-lookup"><span data-stu-id="e0f1b-104">This procedure walks through configuring and running a recurrent batch job to post statements for a selected store or group of stores.</span></span> <span data-ttu-id="e0f1b-105">Questa procedura utilizza i dati dimostrativi della società USRT.</span><span class="sxs-lookup"><span data-stu-id="e0f1b-105">This procedure uses the USRT company in demo data.</span></span>

1. <span data-ttu-id="e0f1b-106">Passare a Tutte le aree di lavoro </span><span class="sxs-lookup"><span data-stu-id="e0f1b-106">Go to All workspaces > ..</span></span> <span data-ttu-id="e0f1b-107">> Dati finanziari punto vendita.</span><span class="sxs-lookup"><span data-stu-id="e0f1b-107">> Store financials.</span></span>
2. <span data-ttu-id="e0f1b-108">Fare clic su Registra rendiconti in batch.</span><span class="sxs-lookup"><span data-stu-id="e0f1b-108">Click Post statements in batch.</span></span>
    * <span data-ttu-id="e0f1b-109">Selezionare una gerarchia organizzativa e quindi nella struttura dei nodi dell'organizzazione, selezionare un punto vendita o un nodo.</span><span class="sxs-lookup"><span data-stu-id="e0f1b-109">Select an organizational hierarchy and then in the organization nodes tree, select either an individual store or a node.</span></span> <span data-ttu-id="e0f1b-110">Selezionare un nodo se si desidera creare il processo batch per un gruppo di punti vendita.</span><span class="sxs-lookup"><span data-stu-id="e0f1b-110">Select a node if you want to create the batch job for a group of stores.</span></span>  
    * <span data-ttu-id="e0f1b-111">Fare clic sulla freccia per aggiungere la selezione.</span><span class="sxs-lookup"><span data-stu-id="e0f1b-111">Click the arrow to add your selection.</span></span>  
3. <span data-ttu-id="e0f1b-112">Fare clic sulla scheda Esecuzione in background. ![Esecuzione in background](../dev-itpro/media/runbackground.png "Esecuzione in background")</span><span class="sxs-lookup"><span data-stu-id="e0f1b-112">Click the Run in the background tab. ![Run in the background](../dev-itpro/media/runbackground.png "Run in the background")</span></span> 
4. <span data-ttu-id="e0f1b-113">Selezionare o deselezionare la casella di controllo Elaborazione batch.</span><span class="sxs-lookup"><span data-stu-id="e0f1b-113">Check or uncheck the Batch processing checkbox.</span></span>
<span data-ttu-id="e0f1b-114">![Elaborazione batch](../dev-itpro/media/batchprocessing.png "Elaborazione e ricorrenza batch")</span><span class="sxs-lookup"><span data-stu-id="e0f1b-114">![Batch Processing](../dev-itpro/media/batchprocessing.png "Batch Processing & Recurrance")</span></span> 
5. <span data-ttu-id="e0f1b-115">Fare clic su Ricorrenza.</span><span class="sxs-lookup"><span data-stu-id="e0f1b-115">Click Recurrence.</span></span>
6. <span data-ttu-id="e0f1b-116">Nel campo Data di inizio, immettere una data.</span><span class="sxs-lookup"><span data-stu-id="e0f1b-116">In the Start date field, enter a date.</span></span>
7. <span data-ttu-id="e0f1b-117">Immettere l'ora nel campo Ora di inizio.</span><span class="sxs-lookup"><span data-stu-id="e0f1b-117">In the Start time field, enter a time.</span></span>
    * <span data-ttu-id="e0f1b-118">Selezionare se si desidera terminare la ricorrenza dopo un numero specifico di cicli, a una data specifica o mai.</span><span class="sxs-lookup"><span data-stu-id="e0f1b-118">Choose whether you want to end the recurrence after a specific number of runs, at a specific date, or never.</span></span> <span data-ttu-id="e0f1b-119">Quindi scegliere le varie opzioni per definire la frequenza di esecuzione del processo.</span><span class="sxs-lookup"><span data-stu-id="e0f1b-119">Then choose the various options to define how frequently you want the job to run.</span></span>  
8. <span data-ttu-id="e0f1b-120">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="e0f1b-120">Click OK.</span></span>
9. <span data-ttu-id="e0f1b-121">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="e0f1b-121">Click OK.</span></span>



[!INCLUDE[footer-include](../../includes/footer-banner.md)]