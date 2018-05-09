--- 
title: Configurare i costi standard di manodopera e spese
description: In questa procedura viene illustrato come impostare i costi standard per la manodopera e le spese per un progetto.
author: KimANelson
manager: AnnBe
ms.date: 02/13/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Service industries
ms.author: knelson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: e4f1981bb35f7740bda6f662fd13f3505d1f8fda
ms.contentlocale: it-it
ms.lasthandoff: 05/08/2018

---
# <a name="configure-standard-costs-for-labor-and-expenses"></a><span data-ttu-id="96dc2-103">Configurare i costi standard di manodopera e spese</span><span class="sxs-lookup"><span data-stu-id="96dc2-103">Configure standard costs for labor and expenses</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="96dc2-104">In questa procedura viene illustrato come impostare i costi standard per la manodopera e le spese per un progetto.</span><span class="sxs-lookup"><span data-stu-id="96dc2-104">This procedure shows you how to set up standard costs for labor and expenses for a project.</span></span> <span data-ttu-id="96dc2-105">Questa attività utilizza il set di dati dimostrativi USSI.</span><span class="sxs-lookup"><span data-stu-id="96dc2-105">This task uses the USSI data set.</span></span>

1. <span data-ttu-id="96dc2-106">Passare a Gestione progetti e contabilità > Impostazioni > Prezzi > Prezzo di costo (ora).</span><span class="sxs-lookup"><span data-stu-id="96dc2-106">Go to Project management and accounting > Setup > Prices > Cost price (hour).</span></span>
2. <span data-ttu-id="96dc2-107">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="96dc2-107">Click New.</span></span>
3. <span data-ttu-id="96dc2-108">Nel campo Data di validità, immettere una data.</span><span class="sxs-lookup"><span data-stu-id="96dc2-108">In the Effective date field, enter a date.</span></span>
4. <span data-ttu-id="96dc2-109">Immettere un numero nel campo Prezzo di costo.</span><span class="sxs-lookup"><span data-stu-id="96dc2-109">In the Cost price field, enter a number.</span></span>
    * <span data-ttu-id="96dc2-110">È possibile impostare un prezzo di costo standard in base alla categoria del progetto oppure prezzi di costo per numero lavoratore, numero progetto, categoria, data o una qualsiasi combinazione di questi elementi.</span><span class="sxs-lookup"><span data-stu-id="96dc2-110">You can set up a standard cost price for the project category, or you can set up a cost price by worker number, project number, category, date, or any combination of these.</span></span> <span data-ttu-id="96dc2-111">Il prezzo di costo applicato corrisponderà a quello associato al livello di dettaglio più alto.</span><span class="sxs-lookup"><span data-stu-id="96dc2-111">The cost price that is applied is the cost price with the highest level of detail.</span></span>  
5. <span data-ttu-id="96dc2-112">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="96dc2-112">Click Save.</span></span>
6. <span data-ttu-id="96dc2-113">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="96dc2-113">Close the page.</span></span>
7. <span data-ttu-id="96dc2-114">Passare a Gestione progetti e contabilità > Impostazioni > Prezzi > Prezzo di vendita (ora).</span><span class="sxs-lookup"><span data-stu-id="96dc2-114">Go to Project management and accounting > Setup > Prices > Sales price (hour).</span></span>
8. <span data-ttu-id="96dc2-115">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="96dc2-115">Click New.</span></span>
9. <span data-ttu-id="96dc2-116">Nel campo Data di validità, immettere una data.</span><span class="sxs-lookup"><span data-stu-id="96dc2-116">In the Effective date field, enter a date.</span></span>
10. <span data-ttu-id="96dc2-117">Selezionare un'opzione nel campo Valido per.</span><span class="sxs-lookup"><span data-stu-id="96dc2-117">In the Valid for field, select an option.</span></span>
11. <span data-ttu-id="96dc2-118">Immettere un numero nel campo Determinazione prezzo.</span><span class="sxs-lookup"><span data-stu-id="96dc2-118">In the Pricing field, enter a number.</span></span>
    * <span data-ttu-id="96dc2-119">È possibile impostare un prezzo di vendita standard per transazioni orarie o per una categoria di progetto.</span><span class="sxs-lookup"><span data-stu-id="96dc2-119">You can set up a standard sales price for hour transactions or for a project category.</span></span> <span data-ttu-id="96dc2-120">Inoltre è possibile impostare i prezzi di vendita in base al numero del lavoratore, al numero del progetto, alla categoria, alla data della transazione oppure a una combinazione di questi elementi.</span><span class="sxs-lookup"><span data-stu-id="96dc2-120">You can also set up sales prices by worker number, project number, category, transaction date, or any combination of these.</span></span> <span data-ttu-id="96dc2-121">Il prezzo di vendita effettivo, che viene applicato quando un lavoratore immette una transazione nel giornale di registrazione ore, è il prezzo di vendita con il livello di dettagli più alto.</span><span class="sxs-lookup"><span data-stu-id="96dc2-121">The actual sales price, which is applied when a worker enters a transaction in the Hour journal, is the sales price with the highest level of detail.</span></span> <span data-ttu-id="96dc2-122">Se vengono impostati, ad esempio, un prezzo di vendita generale e un prezzo di vendita specifico per un lavoratore, verrà utilizzato automaticamente quello specifico per il lavoratore.</span><span class="sxs-lookup"><span data-stu-id="96dc2-122">For example, if both a general sales price and a worker-specific sales price are set up, the worker-specific sales price is used.</span></span>  
12. <span data-ttu-id="96dc2-123">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="96dc2-123">Click Save.</span></span>
13. <span data-ttu-id="96dc2-124">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="96dc2-124">Close the page.</span></span>
14. <span data-ttu-id="96dc2-125">Passare a Gestione progetti e contabilità > Impostazioni > Prezzi > Prezzo di costo (spesa).</span><span class="sxs-lookup"><span data-stu-id="96dc2-125">Go to Project management and accounting > Setup > Prices > Cost price (expense).</span></span>
15. <span data-ttu-id="96dc2-126">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="96dc2-126">Click New.</span></span>
16. <span data-ttu-id="96dc2-127">Nel campo Data di validità, immettere una data.</span><span class="sxs-lookup"><span data-stu-id="96dc2-127">In the Effective date field, enter a date.</span></span>
17. <span data-ttu-id="96dc2-128">Immettere un numero nel campo Prezzo di costo.</span><span class="sxs-lookup"><span data-stu-id="96dc2-128">In the Cost price field, enter a number.</span></span>
    * <span data-ttu-id="96dc2-129">Più campi possono essere completati, ma questo è il minimo necessario per salvare il record.</span><span class="sxs-lookup"><span data-stu-id="96dc2-129">Multiple fields can be filled in, but this is the minimum needed to save the record.</span></span>  
18. <span data-ttu-id="96dc2-130">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="96dc2-130">Click Save.</span></span>
19. <span data-ttu-id="96dc2-131">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="96dc2-131">Close the page.</span></span>
20. <span data-ttu-id="96dc2-132">Passare a Gestione progetti e contabilità > Impostazioni > Prezzi > Prezzo di vendita (spesa).</span><span class="sxs-lookup"><span data-stu-id="96dc2-132">Go to Project management and accounting > Setup > Prices > Sales price (expense).</span></span>
21. <span data-ttu-id="96dc2-133">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="96dc2-133">Click New.</span></span>
22. <span data-ttu-id="96dc2-134">Nel campo Data di validità, immettere una data.</span><span class="sxs-lookup"><span data-stu-id="96dc2-134">In the Effective date field, enter a date.</span></span>
23. <span data-ttu-id="96dc2-135">Selezionare un'opzione nel campo Valido per.</span><span class="sxs-lookup"><span data-stu-id="96dc2-135">In the Valid for field, select an option.</span></span>
24. <span data-ttu-id="96dc2-136">Immettere un numero nel campo Determinazione prezzo.</span><span class="sxs-lookup"><span data-stu-id="96dc2-136">In the Pricing field, enter a number.</span></span>
    * <span data-ttu-id="96dc2-137">Il prezzo di vendita effettivo, applicato quando un lavoratore immette una transazione in un giornale di registrazione spese, corrisponde al prezzo di vendita con il più alto livello di dettaglio.</span><span class="sxs-lookup"><span data-stu-id="96dc2-137">The actual sales price, which is applied when a worker enters transactions in an expense journal, is the sales price with the highest level of detail.</span></span> <span data-ttu-id="96dc2-138">Se vengono impostati, ad esempio, un prezzo di vendita generale e un prezzo di vendita specifico per un lavoratore, verrà selezionato automaticamente quello specifico per il lavoratore.</span><span class="sxs-lookup"><span data-stu-id="96dc2-138">For example, if both a general and a worker-specific sales price are set up, the worker-specific sales price is used.</span></span>  
25. <span data-ttu-id="96dc2-139">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="96dc2-139">Click Save.</span></span>


