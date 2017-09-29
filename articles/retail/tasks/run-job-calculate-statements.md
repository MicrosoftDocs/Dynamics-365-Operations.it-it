--- 
title: " Configurare ed eseguire un processo per calcolare i rendiconti"
description: In questa procedura vengono descritti i passaggi per configurare ed eseguire i processi batch ricorrenti al fine di creare e calcolare i rendiconti per un punto vendita o un gruppo di punti vendita selezionato.
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
ms.openlocfilehash: 2bae81073fa6561c02d2dac0cd83db6a10ad00c3
ms.contentlocale: it-it
ms.lasthandoff: 08/29/2017

---
# <a name="configure-and-run-a-job-to-calculate-statements"></a><span data-ttu-id="da08a-103"> Configurare ed eseguire un processo per calcolare i rendiconti</span><span class="sxs-lookup"><span data-stu-id="da08a-103">Configure and run a job to calculate statements</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="da08a-104">In questa procedura vengono descritti i passaggi per configurare ed eseguire i processi batch ricorrenti al fine di creare e calcolare i rendiconti per un punto vendita o un gruppo di punti vendita selezionato.</span><span class="sxs-lookup"><span data-stu-id="da08a-104">This procedure walks through configuring and running recurrent batch jobs to create and calculate statements for a selected store or group of stores.</span></span> <span data-ttu-id="da08a-105">Questa procedura utilizza i dati dimostrativi della società USRT.</span><span class="sxs-lookup"><span data-stu-id="da08a-105">This procedure uses the USRT company in demo data.</span></span>

1. <span data-ttu-id="da08a-106">Passare a Tutte le aree di lavoro > Dati finanziari punto vendita al dettaglio.</span><span class="sxs-lookup"><span data-stu-id="da08a-106">Go to All workspaces > Retail store financials.</span></span>
2. <span data-ttu-id="da08a-107">Fare clic su Calcola rendiconti.</span><span class="sxs-lookup"><span data-stu-id="da08a-107">Click Calculate statements.</span></span>
    * <span data-ttu-id="da08a-108">Selezionare un punto vendita specifico o un nodo se si desidera creare il processo batch per un gruppo di punti vendita.</span><span class="sxs-lookup"><span data-stu-id="da08a-108">Select either a specific store, or a node if you want to create the batch job for a group of stores.</span></span>  
    * <span data-ttu-id="da08a-109">Fare clic sulla freccia per aggiungere la selezione.</span><span class="sxs-lookup"><span data-stu-id="da08a-109">Click the arrow to add your selection.</span></span>  
3. <span data-ttu-id="da08a-110">Fare clic sulla scheda Esecuzione in background.</span><span class="sxs-lookup"><span data-stu-id="da08a-110">Click the Run in the background tab.</span></span>
4. <span data-ttu-id="da08a-111">In Elaborazione batch, selezionare 'Sì'.</span><span class="sxs-lookup"><span data-stu-id="da08a-111">Under Batch processing, select 'Yes'.</span></span>
5. <span data-ttu-id="da08a-112">Fare clic su Ricorrenza.</span><span class="sxs-lookup"><span data-stu-id="da08a-112">Click Recurrence.</span></span>
6. <span data-ttu-id="da08a-113">Nel campo Data di inizio, immettere una data.</span><span class="sxs-lookup"><span data-stu-id="da08a-113">In the Start date field, enter a date.</span></span>
7. <span data-ttu-id="da08a-114">Immettere l'ora nel campo Ora di inizio.</span><span class="sxs-lookup"><span data-stu-id="da08a-114">In the Start time field, enter a time.</span></span>
8. <span data-ttu-id="da08a-115">Selezionare l'opzione Nessuna data di fine.</span><span class="sxs-lookup"><span data-stu-id="da08a-115">Select the No end date option.</span></span>
9. <span data-ttu-id="da08a-116">Nel campo PatternUnit immettere 'Giorni'.</span><span class="sxs-lookup"><span data-stu-id="da08a-116">In the PatternUnit field, enter 'Days'.</span></span>
10. <span data-ttu-id="da08a-117">Nel campo Per immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="da08a-117">In the Per field, enter a number.</span></span>
11. <span data-ttu-id="da08a-118">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="da08a-118">Click OK.</span></span>
12. <span data-ttu-id="da08a-119">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="da08a-119">Click OK.</span></span>


