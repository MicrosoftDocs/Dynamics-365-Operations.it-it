---
title: Generare un piano con vincoli
description: In questo argomento viene descritta la creazione di un piano in cui verranno considerati sia i vincoli materiali che di capacità.
author: ShylaThompson
manager: tfehr
ms.date: 08/02/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, ReqCreatePlanWorkspace, ReqTransPlanCard, ReqPlanSched
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d238ffd7ee76dcb782931312a132545a89f537b5
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5214396"
---
# <a name="generate-a-constrained-plan"></a><span data-ttu-id="02a8d-103">Generare un piano con vincoli</span><span class="sxs-lookup"><span data-stu-id="02a8d-103">Generate a constrained plan</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="02a8d-104">In questo argomento viene descritta la creazione di un piano in cui verranno considerati sia i vincoli materiali che di capacità.</span><span class="sxs-lookup"><span data-stu-id="02a8d-104">This topic explains how to create a plan that takes into account both material and capacity constraints.</span></span> <span data-ttu-id="02a8d-105">Il piano garantisce che la produzione non inizi prima che i materiali siano disponibili e che le risorse non siano sovraprenotate.</span><span class="sxs-lookup"><span data-stu-id="02a8d-105">The plan ensures that manufacturing doesn't start before materials are available and resources are not overbooked.</span></span> 

<span data-ttu-id="02a8d-106">La società di dati dimostrativi utilizzata per creare questa procedura è USMF.</span><span class="sxs-lookup"><span data-stu-id="02a8d-106">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="02a8d-107">Questa procedura è destinata al responsabile pianificazione produzione.</span><span class="sxs-lookup"><span data-stu-id="02a8d-107">This procedure is intended for the production planner.</span></span>


## <a name="set-up-a-constrained-plan"></a><span data-ttu-id="02a8d-108">Impostare un piano con vincoli</span><span class="sxs-lookup"><span data-stu-id="02a8d-108">Set up a constrained plan</span></span>
1. <span data-ttu-id="02a8d-109">Nella home page, selezionare l'area di lavoro **Pianificazione generale**.</span><span class="sxs-lookup"><span data-stu-id="02a8d-109">In the home page, select the **Master planning** workspace.</span></span>
2. <span data-ttu-id="02a8d-110">Selezionare **Piani generali** nell'elenco dei collegamenti all'estrema destra dell'area di lavoro.</span><span class="sxs-lookup"><span data-stu-id="02a8d-110">Select **Master plans** in the list of links on the far right side of the workspace.</span></span>
3. <span data-ttu-id="02a8d-111">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="02a8d-111">In the list, find and select the desired record.</span></span> <span data-ttu-id="02a8d-112">Esempio: **StaticPlan**</span><span class="sxs-lookup"><span data-stu-id="02a8d-112">Example: **StaticPlan**</span></span>  
4. <span data-ttu-id="02a8d-113">Selezionare **Sì** nel campo **Capacità limitata**.</span><span class="sxs-lookup"><span data-stu-id="02a8d-113">Select **Yes** in the **Finite capacity** field.</span></span>
5. <span data-ttu-id="02a8d-114">Nel campo **Intervallo temporale capacità limitata** immettere `30`.</span><span class="sxs-lookup"><span data-stu-id="02a8d-114">In the **Finite capacity time fence** field, enter `30`.</span></span>
6. <span data-ttu-id="02a8d-115">Espandere la sezione **Intervalli temporali in giorni**.</span><span class="sxs-lookup"><span data-stu-id="02a8d-115">Expand the **Time fences in days** section.</span></span>
7. <span data-ttu-id="02a8d-116">Selezionare **Sì** nel campo **Capacità**.</span><span class="sxs-lookup"><span data-stu-id="02a8d-116">Select **Yes** in the **Capacity** field.</span></span>
8. <span data-ttu-id="02a8d-117">Nel campo **Intervallo temporale programmazione capacità (giorni)** immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="02a8d-117">In the **Capacity scheduling time fence (days)** field, enter a number.</span></span> <span data-ttu-id="02a8d-118">Esempio: `60`</span><span class="sxs-lookup"><span data-stu-id="02a8d-118">Example: `60`</span></span>  
9. <span data-ttu-id="02a8d-119">Selezionare **Sì** nel campo **Ritardi calcolati**.</span><span class="sxs-lookup"><span data-stu-id="02a8d-119">Select **Yes** in the **Calculated delays** field.</span></span>
10. <span data-ttu-id="02a8d-120">Nel campo **Calcola intervallo temporale dei ritardi (giorni)** immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="02a8d-120">In the **Calculate delays time fence (days)** field, enter a number.</span></span> <span data-ttu-id="02a8d-121">Esempio: `60`</span><span class="sxs-lookup"><span data-stu-id="02a8d-121">Example: `60`</span></span> 
11. <span data-ttu-id="02a8d-122">Espandere la sezione **Ritardi calcolati**.</span><span class="sxs-lookup"><span data-stu-id="02a8d-122">Expand the **Calculated delays** section.</span></span>
12. <span data-ttu-id="02a8d-123">Selezionare **Sì** in tutti i campi **Aggiungere il ritardo calcolato alla data del fabbisogno**.</span><span class="sxs-lookup"><span data-stu-id="02a8d-123">Select **Yes** in all **Add the calculated delay to the requirement date** fields.</span></span>
13. <span data-ttu-id="02a8d-124">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="02a8d-124">Close the page.</span></span>

## <a name="create-a-constrained-plan"></a><span data-ttu-id="02a8d-125">Crea un piano con vincoli</span><span class="sxs-lookup"><span data-stu-id="02a8d-125">Create a constrained plan</span></span>
1. <span data-ttu-id="02a8d-126">Selezionare **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="02a8d-126">Select **Run**.</span></span>
2. <span data-ttu-id="02a8d-127">Nel campo **Piano generale**, immettere o selezionare il piano per cui sono stati impostati dei vincoli.</span><span class="sxs-lookup"><span data-stu-id="02a8d-127">In the **Master plan** field, enter or select the plan for which you have set up constraints.</span></span>  
3. <span data-ttu-id="02a8d-128">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="02a8d-128">Select **OK**.</span></span>
4. <span data-ttu-id="02a8d-129">Selezionare **Ordini pianificati**.</span><span class="sxs-lookup"><span data-stu-id="02a8d-129">Select **Planned orders**.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]