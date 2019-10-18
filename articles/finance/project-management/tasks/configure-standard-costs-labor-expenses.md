---
title: Configurare i costi standard di manodopera e spese
description: In questo argomento viene illustrato come impostare i costi standard per la manodopera e le spese per un progetto.
author: KimANelson
manager: AnnBe
ms.date: 08/02/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjCostPriceHour, ProjSalesPriceHour, ProjCostPriceExpense, ProjSalesPriceCost
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Service industries
ms.author: knelson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 60ab8eb94d4a8a0fb2c1e732ec7b25bfd5e7611e
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/27/2019
ms.locfileid: "2185407"
---
# <a name="configure-standard-costs-for-labor-and-expenses"></a><span data-ttu-id="56602-103">Configurare i costi standard di manodopera e spese</span><span class="sxs-lookup"><span data-stu-id="56602-103">Configure standard costs for labor and expenses</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="56602-104">In questo argomento viene illustrato come impostare i costi standard per la manodopera e le spese per un progetto.</span><span class="sxs-lookup"><span data-stu-id="56602-104">This topic explains how to set up standard costs for labor and expenses for a project.</span></span> <span data-ttu-id="56602-105">Questa attività utilizza il set di dati dimostrativi USSI.</span><span class="sxs-lookup"><span data-stu-id="56602-105">This task uses the USSI data set.</span></span>

1. <span data-ttu-id="56602-106">Nel pannello di navigazione, andare a **Moduli > Gestione progetti e contabilità > Impostazioni > Prezzi > Prezzo di costo (ora)**.</span><span class="sxs-lookup"><span data-stu-id="56602-106">In the navigation pane, go to **Modules > Project management and accounting > Setup > Prices > Cost price (hour)**.</span></span>
2. <span data-ttu-id="56602-107">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="56602-107">Select **New**.</span></span>
3. <span data-ttu-id="56602-108">Nel campo **Data di validità**, immettere una data.</span><span class="sxs-lookup"><span data-stu-id="56602-108">In the **Effective date** field, enter a date.</span></span>
4. <span data-ttu-id="56602-109">Immettere un numero nel campo **Prezzo di costo**.</span><span class="sxs-lookup"><span data-stu-id="56602-109">In the **Cost price** field, enter a number.</span></span> <span data-ttu-id="56602-110">È possibile impostare un prezzo di costo standard in base alla categoria del progetto oppure prezzi di costo per numero lavoratore, numero progetto, categoria, data o una qualsiasi combinazione di questi elementi.</span><span class="sxs-lookup"><span data-stu-id="56602-110">You can set up a standard cost price for the project category, or you can set up a cost price by worker number, project number, category, date, or any combination of these.</span></span> <span data-ttu-id="56602-111">Il prezzo di costo applicato corrisponderà a quello associato al livello di dettaglio più alto.</span><span class="sxs-lookup"><span data-stu-id="56602-111">The cost price that is applied is the cost price with the highest level of detail.</span></span>  
5. <span data-ttu-id="56602-112">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="56602-112">Select **Save**.</span></span>
6. <span data-ttu-id="56602-113">Nel pannello di navigazione, andare a **Moduli > Gestione progetti e contabilità > Impostazioni > Prezzi > Prezzo di vendita (ora)**.</span><span class="sxs-lookup"><span data-stu-id="56602-113">In the navigation pane, go to **Modules > Project management and accounting > Setup > Prices > Sales price (hour)**.</span></span>
7. <span data-ttu-id="56602-114">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="56602-114">Select **New**.</span></span>
8. <span data-ttu-id="56602-115">Nel campo **Data di validità**, immettere una data.</span><span class="sxs-lookup"><span data-stu-id="56602-115">In the **Effective date** field, enter a date.</span></span>
9. <span data-ttu-id="56602-116">Selezionare un'opzione nel campo **Valido per**.</span><span class="sxs-lookup"><span data-stu-id="56602-116">In the **Valid for** field, select an option.</span></span>
10. <span data-ttu-id="56602-117">Immettere un numero nel campo **Determinazione prezzo**.</span><span class="sxs-lookup"><span data-stu-id="56602-117">In the **Pricing** field, enter a number.</span></span> <span data-ttu-id="56602-118">È possibile impostare un prezzo di vendita standard per transazioni orarie o per una categoria di progetto.</span><span class="sxs-lookup"><span data-stu-id="56602-118">You can set up a standard sales price for hour transactions or for a project category.</span></span> <span data-ttu-id="56602-119">Inoltre è possibile impostare i prezzi di vendita in base al numero del lavoratore, al numero del progetto, alla categoria, alla data della transazione oppure a una combinazione di questi elementi.</span><span class="sxs-lookup"><span data-stu-id="56602-119">You can also set up sales prices by worker number, project number, category, transaction date, or any combination of these.</span></span> <span data-ttu-id="56602-120">Il prezzo di vendita effettivo, che viene applicato quando un lavoratore immette una transazione nel giornale di registrazione ore, è il prezzo di vendita con il livello di dettagli più alto.</span><span class="sxs-lookup"><span data-stu-id="56602-120">The actual sales price, which is applied when a worker enters a transaction in the Hour journal, is the sales price with the highest level of detail.</span></span> <span data-ttu-id="56602-121">Se vengono impostati, ad esempio, un prezzo di vendita generale e un prezzo di vendita specifico per un lavoratore, verrà utilizzato automaticamente quello specifico per il lavoratore.</span><span class="sxs-lookup"><span data-stu-id="56602-121">For example, if both a general sales price and a worker-specific sales price are set up, the worker-specific sales price is used.</span></span>  
11. <span data-ttu-id="56602-122">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="56602-122">Select **Save**.</span></span>
12. <span data-ttu-id="56602-123">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="56602-123">Close the page.</span></span>
13. <span data-ttu-id="56602-124">Nel pannello di navigazione, andare a **Moduli > Gestione progetti e contabilità > Impostazioni > Prezzi > Prezzo di costo (spesa)**.</span><span class="sxs-lookup"><span data-stu-id="56602-124">In the navigation pane, go to **Modules > Project management and accounting > Setup > Prices > Cost price (expense)**.</span></span>
14. <span data-ttu-id="56602-125">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="56602-125">Select **New**.</span></span>
15. <span data-ttu-id="56602-126">Nel campo **Data di validità**, immettere una data.</span><span class="sxs-lookup"><span data-stu-id="56602-126">In the **Effective date** field, enter a date.</span></span>
16. <span data-ttu-id="56602-127">Immettere un numero nel campo **Prezzo di costo**.</span><span class="sxs-lookup"><span data-stu-id="56602-127">In the **Cost price** field, enter a number.</span></span> <span data-ttu-id="56602-128">Più campi possono essere completati, ma questo è il minimo necessario per salvare il record.</span><span class="sxs-lookup"><span data-stu-id="56602-128">Multiple fields can be filled in, but this is the minimum needed to save the record.</span></span>  
17. <span data-ttu-id="56602-129">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="56602-129">Select **Save**.</span></span>
18. <span data-ttu-id="56602-130">Nel pannello di navigazione, andare a **Moduli > Gestione progetti e contabilità > Impostazioni > Prezzi > Prezzo di vendita (spesa)**.</span><span class="sxs-lookup"><span data-stu-id="56602-130">In the navigation pane, go to **Modules > Project management and accounting > Setup > Prices > Sales price (expense)**.</span></span>
19. <span data-ttu-id="56602-131">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="56602-131">Select **New**.</span></span>
20. <span data-ttu-id="56602-132">Nel campo **Data di validità**, immettere una data.</span><span class="sxs-lookup"><span data-stu-id="56602-132">In the **Effective date** field, enter a date.</span></span>
21. <span data-ttu-id="56602-133">Selezionare un'opzione nel campo **Valido per**.</span><span class="sxs-lookup"><span data-stu-id="56602-133">In the **Valid for** field, select an option.</span></span>
22. <span data-ttu-id="56602-134">Immettere un numero nel campo **Determinazione prezzo**.</span><span class="sxs-lookup"><span data-stu-id="56602-134">In the **Pricing** field, enter a number.</span></span> <span data-ttu-id="56602-135">Il prezzo di vendita effettivo, applicato quando un lavoratore immette una transazione in un giornale di registrazione spese, corrisponde al prezzo di vendita con il più alto livello di dettaglio.</span><span class="sxs-lookup"><span data-stu-id="56602-135">The actual sales price, which is applied when a worker enters transactions in an expense journal, is the sales price with the highest level of detail.</span></span> <span data-ttu-id="56602-136">Se vengono impostati, ad esempio, un prezzo di vendita generale e un prezzo di vendita specifico per un lavoratore, verrà selezionato automaticamente quello specifico per il lavoratore.</span><span class="sxs-lookup"><span data-stu-id="56602-136">For example, if both a general and a worker-specific sales price are set up, the worker-specific sales price is used.</span></span>  
23. <span data-ttu-id="56602-137">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="56602-137">Select **Save**.</span></span>

