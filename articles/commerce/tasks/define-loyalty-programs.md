---
title: " Definire programmi fedeltà"
description: In questa procedura vengono descritti i passaggi per impostare un programma fedeltà con due livelli di fedeltà.
author: jashanno
manager: AnnBe
ms.date: 11/14/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 69424cdaae84ffe5ca8157f061ba5876b9eeeff9
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5256903"
---
# <a name="define-loyalty-programs"></a><span data-ttu-id="1a0f3-103"> Definire programmi fedeltà</span><span class="sxs-lookup"><span data-stu-id="1a0f3-103">Define loyalty programs</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="1a0f3-104">In questa procedura vengono descritti i passaggi per impostare un programma fedeltà con due livelli di fedeltà.</span><span class="sxs-lookup"><span data-stu-id="1a0f3-104">This procedure shows how to set up a loyalty program with two loyalty tiers.</span></span> <span data-ttu-id="1a0f3-105">Questa procedura utilizza la società di dati dimostrativi USRT.</span><span class="sxs-lookup"><span data-stu-id="1a0f3-105">This procedure uses the USRT demo data company.</span></span>

1. <span data-ttu-id="1a0f3-106">Passare a Retail e Commerce </span><span class="sxs-lookup"><span data-stu-id="1a0f3-106">Go to Retail and Commerce > ..</span></span> <span data-ttu-id="1a0f3-107">> Programmi fedeltà.</span><span class="sxs-lookup"><span data-stu-id="1a0f3-107">> Loyalty programs.</span></span>
2. <span data-ttu-id="1a0f3-108">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="1a0f3-108">Click New.</span></span>
3. <span data-ttu-id="1a0f3-109">Digitare un valore nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="1a0f3-109">In the Name field, type a value.</span></span>
4. <span data-ttu-id="1a0f3-110">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="1a0f3-110">In the Description field, type a value.</span></span>
5. <span data-ttu-id="1a0f3-111">Fare clic su Aggiungi riga.</span><span class="sxs-lookup"><span data-stu-id="1a0f3-111">Click Add line.</span></span>
6. <span data-ttu-id="1a0f3-112">Nel campo Livello immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="1a0f3-112">In the Level field, enter a number.</span></span>
7. <span data-ttu-id="1a0f3-113">Nel campo Livello immettere il nome del livello del programma fedeltà.</span><span class="sxs-lookup"><span data-stu-id="1a0f3-113">In the Tier field, enter a name for the loyalty tier.</span></span>
8. <span data-ttu-id="1a0f3-114">Digitare un valore nel campo Descrizione.</span><span class="sxs-lookup"><span data-stu-id="1a0f3-114">In the Description field, type a value.</span></span>
9. <span data-ttu-id="1a0f3-115">Nel campo Intervallo date fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="1a0f3-115">In the Date interval field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="1a0f3-116">Questo intervallo di date deve estendersi nel futuro.</span><span class="sxs-lookup"><span data-stu-id="1a0f3-116">This date interval should extend into the future.</span></span> <span data-ttu-id="1a0f3-117">Ad esempio, se l'intervallo di date selezionato per il livello oro è per un periodo di un anno, tutti i clienti qualificati per il livello oro possono ricevere i premi assegnati al livello oro per un anno.</span><span class="sxs-lookup"><span data-stu-id="1a0f3-117">For example, if the date interval that is selected for gold tier is a one-year period, any customer who qualifies for the gold tier can receive the rewards that are assigned to the gold tier for one year.</span></span> <span data-ttu-id="1a0f3-118">Se il cliente viene riqualificato per il livello oro mentre si trova in tale livello, la data in cui lo stato del livello scade viene prorogata di un altro anno a partire dalla data di riqualificazione.</span><span class="sxs-lookup"><span data-stu-id="1a0f3-118">If the customer re-qualifies for the gold tier while they are in the tier, the date that the tier expires is extended by another year from the date when they re-qualify.</span></span>  
10. <span data-ttu-id="1a0f3-119">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="1a0f3-119">In the list, click the link in the selected row.</span></span>
11. <span data-ttu-id="1a0f3-120">Fare clic su Aggiungi riga.</span><span class="sxs-lookup"><span data-stu-id="1a0f3-120">Click Add line.</span></span>
12. <span data-ttu-id="1a0f3-121">Nel campo Livello immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="1a0f3-121">In the Level field, enter a number.</span></span>
13. <span data-ttu-id="1a0f3-122">Nel campo Livello immettere il nome del livello del programma fedeltà.</span><span class="sxs-lookup"><span data-stu-id="1a0f3-122">In the Tier field, enter a name for the loyalty tier.</span></span>
14. <span data-ttu-id="1a0f3-123">Digitare un valore nel campo Descrizione.</span><span class="sxs-lookup"><span data-stu-id="1a0f3-123">In the Description field, type a value.</span></span>
15. <span data-ttu-id="1a0f3-124">Nel campo Intervallo date fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="1a0f3-124">In the Date interval field, click the drop-down button to open the lookup.</span></span>
16. <span data-ttu-id="1a0f3-125">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="1a0f3-125">In the list, click the link in the selected row.</span></span>
17. <span data-ttu-id="1a0f3-126">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="1a0f3-126">Click Save.</span></span>
18. <span data-ttu-id="1a0f3-127">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="1a0f3-127">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="1a0f3-128">Le regole livello definiscono il numero minimo di punti premio che devono essere acquisiti durante un periodo per avere diritto al livello.</span><span class="sxs-lookup"><span data-stu-id="1a0f3-128">Tier rules define the minimum number of a reward point needed to be earned during a time period to qualify for the tier.</span></span>  
19. <span data-ttu-id="1a0f3-129">Attivare l'espansione della sezione Regole livello.</span><span class="sxs-lookup"><span data-stu-id="1a0f3-129">Toggle the expansion of the Tier rules section.</span></span>
20. <span data-ttu-id="1a0f3-130">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="1a0f3-130">Click New.</span></span>
    * <span data-ttu-id="1a0f3-131">È possibile disporre di più regole livello per ogni livello.</span><span class="sxs-lookup"><span data-stu-id="1a0f3-131">You can have more than one tier rule per tier.</span></span> <span data-ttu-id="1a0f3-132">Ad esempio, si potrebbe disporre di tre criteri diversi per acquisire un livello, in base alla spesa di $500 in un mese, in base alla spesa di $1000 in un anno e in base all'esecuzione di 20 transazioni in un anno.</span><span class="sxs-lookup"><span data-stu-id="1a0f3-132">For example, you could have three different criteria to earn a tier; by spending $500 in one month, by spending $1000 over one year, and by having 20 transactions in one year.</span></span> <span data-ttu-id="1a0f3-133">A questo scopo, è necessario creare regole a tre livelli.</span><span class="sxs-lookup"><span data-stu-id="1a0f3-133">To do this, you would need to create three tier rules.</span></span>  
21. <span data-ttu-id="1a0f3-134">Nel campo Punto premio fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="1a0f3-134">In the Reward point field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="1a0f3-135">Questo punto premio fedeltà non deve essere riscattabile.</span><span class="sxs-lookup"><span data-stu-id="1a0f3-135">This should be a non-redeemable loyalty reward point.</span></span>  
22. <span data-ttu-id="1a0f3-136">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="1a0f3-136">In the list, click the link in the selected row.</span></span>
23. <span data-ttu-id="1a0f3-137">Nel campo Numero minimo punti emessi immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="1a0f3-137">In the Minimum issued points field, enter a number.</span></span>
    * <span data-ttu-id="1a0f3-138">Per il livello più basso, se tutti i clienti possono avere diritto semplicemente partecipando al programma, immettere '0'.</span><span class="sxs-lookup"><span data-stu-id="1a0f3-138">For the lowest level tier, if all customers qualify simply by participating in the program, enter '0'.</span></span>  
24. <span data-ttu-id="1a0f3-139">Nel campo Intervallo date di valutazione fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="1a0f3-139">In the Evaluation date interval field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="1a0f3-140">Questo intervallo di date deve estendersi nel passato.</span><span class="sxs-lookup"><span data-stu-id="1a0f3-140">This date interval should extend into the past.</span></span> <span data-ttu-id="1a0f3-141">Solo i punti ottenuti durante questo intervallo di date verranno conteggiati per il raggiungimento del valore minimo di punti emessi.</span><span class="sxs-lookup"><span data-stu-id="1a0f3-141">Only points earned during this date interval will be counted towards reaching the minimum issued points value.</span></span>  
25. <span data-ttu-id="1a0f3-142">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="1a0f3-142">In the list, click the link in the selected row.</span></span>
26. <span data-ttu-id="1a0f3-143">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="1a0f3-143">Click Save.</span></span>
27. <span data-ttu-id="1a0f3-144">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="1a0f3-144">In the list, find and select the desired record.</span></span>
28. <span data-ttu-id="1a0f3-145">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="1a0f3-145">Click New.</span></span>
29. <span data-ttu-id="1a0f3-146">Nel campo Punto premio fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="1a0f3-146">In the Reward point field, click the drop-down button to open the lookup.</span></span>
30. <span data-ttu-id="1a0f3-147">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="1a0f3-147">In the list, click the link in the selected row.</span></span>
31. <span data-ttu-id="1a0f3-148">Nel campo Numero minimo punti emessi immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="1a0f3-148">In the Minimum issued points field, enter a number.</span></span>
32. <span data-ttu-id="1a0f3-149">Nel campo Intervallo date di valutazione fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="1a0f3-149">In the Evaluation date interval field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="1a0f3-150">Questo intervallo di date deve estendersi nel passato.</span><span class="sxs-lookup"><span data-stu-id="1a0f3-150">This date interval should extend into the past.</span></span>  
33. <span data-ttu-id="1a0f3-151">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="1a0f3-151">In the list, click the link in the selected row.</span></span>
34. <span data-ttu-id="1a0f3-152">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="1a0f3-152">Click Save.</span></span>
35. <span data-ttu-id="1a0f3-153">Fare clic su Gruppi di prezzi.</span><span class="sxs-lookup"><span data-stu-id="1a0f3-153">Click Price groups.</span></span>
    * <span data-ttu-id="1a0f3-154">Se si desiderano offrire sconti ai clienti programma fedeltà,</span><span class="sxs-lookup"><span data-stu-id="1a0f3-154">If you want to give loyalty customers discounts.</span></span> <span data-ttu-id="1a0f3-155">sarà necessario assegnare uno o più gruppi di prezzi al programma di fedeltà e assegnare i gruppi di prezzi agli sconti.</span><span class="sxs-lookup"><span data-stu-id="1a0f3-155">you'll need to assign one or more price groups to the loyalty program and assign the price groups to discounts.</span></span> <span data-ttu-id="1a0f3-156">È consigliabile non combinare gruppi di prezzi tra diversi tipi di entità di sconto.</span><span class="sxs-lookup"><span data-stu-id="1a0f3-156">It is a best practice to not mix price groups across different types of discounting entities.</span></span>  <span data-ttu-id="1a0f3-157">Ad esempio, non utilizzare lo stesso gruppo di prezzi per uno sconto del programma fedeltà e uno sconto del canale.</span><span class="sxs-lookup"><span data-stu-id="1a0f3-157">For example, don't use the same price group for a loyalty discount and a channel discount.</span></span>  
36. <span data-ttu-id="1a0f3-158">Nel campo Gruppo di prezzi fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="1a0f3-158">In the Price group field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="1a0f3-159">Il collegamento Gruppi di prezzi nella parte superiore della pagina è per il programma di fedeltà.</span><span class="sxs-lookup"><span data-stu-id="1a0f3-159">The Price groups link at the top of the page is for the loyalty program.</span></span> <span data-ttu-id="1a0f3-160">Il collegamento Gruppi di prezzi nella scheda dettaglio Livelli programma è per un solo livello specifico del programma fedeltà.</span><span class="sxs-lookup"><span data-stu-id="1a0f3-160">The Price groups link in the Program tiers FastTab is for a specific loyalty tier only.</span></span>  
37. <span data-ttu-id="1a0f3-161">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="1a0f3-161">In the list, click the link in the selected row.</span></span>
38. <span data-ttu-id="1a0f3-162">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="1a0f3-162">Click Save.</span></span>
39. <span data-ttu-id="1a0f3-163">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="1a0f3-163">Close the page.</span></span>
40. <span data-ttu-id="1a0f3-164">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="1a0f3-164">Click Save.</span></span>



[!INCLUDE[footer-include](../../includes/footer-banner.md)]