--- 
title: Impostare i profili registrazione cespiti
description: "In questa guida attività verranno impostati i profili registrazione cespiti."
author: saraschi2
manager: AnnBe
ms.date: 02/24/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: dd4c2d67188b6c2c34f9046a6388de292d6c291e
ms.contentlocale: it-it
ms.lasthandoff: 08/07/2018

---
# <a name="set-up-fixed-asset-posting-profiles"></a><span data-ttu-id="20327-103">Impostare i profili registrazione cespiti</span><span class="sxs-lookup"><span data-stu-id="20327-103">Set up fixed asset posting profiles</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="20327-104">In questa guida attività verranno impostati i profili registrazione cespiti.</span><span class="sxs-lookup"><span data-stu-id="20327-104">This task guide will set up Fixed asset posting profiles.</span></span>  <span data-ttu-id="20327-105">Utilizza il ruolo Ragioniere e i dati dimostrativi per la persona giuridica USMF.</span><span class="sxs-lookup"><span data-stu-id="20327-105">It uses the Accountant role and demo data for the USMF legal entity.</span></span>  <span data-ttu-id="20327-106">Gli esempi forniti nella guida attività sono relativi a un profilo registrazione di base, anche se i profili registrazione devono essere creati per i requisiti specifici di report finanziari e piano dei conti.</span><span class="sxs-lookup"><span data-stu-id="20327-106">Examples given in the task guide are for a basic posting profile, though posting profiles must be created for your specific chart of accounts and financial reporting requirements.</span></span>

1. <span data-ttu-id="20327-107">Andare a Cespiti > Impostazioni > Profili registrazione cespiti.</span><span class="sxs-lookup"><span data-stu-id="20327-107">Go to Fixed assets > Setup > Fixed asset posting profiles.</span></span>
2. <span data-ttu-id="20327-108">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="20327-108">Click New.</span></span>
3. <span data-ttu-id="20327-109">Nel campo Profilo registrazione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="20327-109">In the Posting profile field, type a value.</span></span>
4. <span data-ttu-id="20327-110">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="20327-110">In the Description field, type a value.</span></span>
    * <span data-ttu-id="20327-111">Sarà necessario creare un profilo di registrazione per ogni tipo di transazione cespiti che si utilizzerà quando si utilizzano i cespiti.</span><span class="sxs-lookup"><span data-stu-id="20327-111">You will need to create a posting profile for each fixed asset transaction type you will be using when working with fixed assets.</span></span>  <span data-ttu-id="20327-112">Questa guida attività inizierà con il tipo di transazione Acquisizione.</span><span class="sxs-lookup"><span data-stu-id="20327-112">This task guide will start with the Acquisition transaction type.</span></span>  
5. <span data-ttu-id="20327-113">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="20327-113">Click Add.</span></span>
6. <span data-ttu-id="20327-114">Nel campo Libro immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="20327-114">In the Book field, enter or select a value.</span></span>
    * <span data-ttu-id="20327-115">Il campo Raggruppamenti consente di definire il profilo di registrazione fino a Tabella (un'unica impostazione di conto per ciascun cespite) o a Gruppo (un'unica impostazione di conto per ciascun gruppo cespite).</span><span class="sxs-lookup"><span data-stu-id="20327-115">The Groupings field allows you to define the posting profile down to the Table (one account set up for each fixed asset) or Group (one account set up for each fixed asset group).</span></span>  <span data-ttu-id="20327-116">Per la guida attività si lasceranno i valori impostati su "Tutti" per applicare a tutti i cespiti con il libro specificato.</span><span class="sxs-lookup"><span data-stu-id="20327-116">For this task guide I will leave the value set to “All” to apply to all fixed assets with the specified Book.</span></span>  
7. <span data-ttu-id="20327-117">Nel campo Conto principale, specificare i valori desiderati.</span><span class="sxs-lookup"><span data-stu-id="20327-117">In the Main account field, specify the desired values.</span></span>
    * <span data-ttu-id="20327-118">Per Acquisizioni, è possibile immettere un conto di contropartita o lasciarlo vuoto perché venga compilato per la transazione specifica.</span><span class="sxs-lookup"><span data-stu-id="20327-118">For Acquisitions, you can enter an offset account or leave it blank to be filled in for the specific transaction.</span></span>    
8. <span data-ttu-id="20327-119">Selezionare "Rettifica acquisizione" nel campo Tipo di transazione.</span><span class="sxs-lookup"><span data-stu-id="20327-119">In the Transaction type field, select 'Acquisition adjustment'.</span></span>
    * <span data-ttu-id="20327-120">Per le transazioni di rettifica acquisizione, verranno utilizzati gli stessi conti utilizzati per le transazioni di acquisizione.</span><span class="sxs-lookup"><span data-stu-id="20327-120">For Acquisition adjustment transactions, we will use the same accounts as used for Acquisition transactions.</span></span>  
9. <span data-ttu-id="20327-121">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="20327-121">Click Add.</span></span>
10. <span data-ttu-id="20327-122">Nel campo Libro immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="20327-122">In the Book field, enter or select a value.</span></span>
11. <span data-ttu-id="20327-123">Nel campo Conto principale, specificare i valori desiderati.</span><span class="sxs-lookup"><span data-stu-id="20327-123">In the Main account field, specify the desired values.</span></span>
    * <span data-ttu-id="20327-124">Per Rettifiche di acquisizione, è possibile immettere un conto di contropartita o lasciarlo vuoto perché venga compilato per la transazione specifica.</span><span class="sxs-lookup"><span data-stu-id="20327-124">For Acquisition adjustments, you can enter an offset account or leave it blank to be filled in for the specific transaction.</span></span>    
12. <span data-ttu-id="20327-125">Selezionare "Ammortamento" nel campo Tipo di transazione.</span><span class="sxs-lookup"><span data-stu-id="20327-125">In the Transaction type field, select 'Depreciation'.</span></span>
13. <span data-ttu-id="20327-126">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="20327-126">Click Add.</span></span>
14. <span data-ttu-id="20327-127">Nel campo Libro immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="20327-127">In the Book field, enter or select a value.</span></span>
15. <span data-ttu-id="20327-128">Nel campo Conto principale, specificare i valori desiderati.</span><span class="sxs-lookup"><span data-stu-id="20327-128">In the Main account field, specify the desired values.</span></span>
16. <span data-ttu-id="20327-129">Nel campo Conto di contropartita, specificare i valori desiderati.</span><span class="sxs-lookup"><span data-stu-id="20327-129">In the Offset account field, specify the desired values.</span></span>
17. <span data-ttu-id="20327-130">Selezionare 'Rettifica ammortamento' nel campo Tipo di transazione.</span><span class="sxs-lookup"><span data-stu-id="20327-130">In the Transaction type field, select 'Depreciation adjustment'.</span></span>
    * <span data-ttu-id="20327-131">Per le transazioni di rettifica ammortamento, verranno utilizzati gli stessi conti utilizzati per le transazioni di ammortamento.</span><span class="sxs-lookup"><span data-stu-id="20327-131">For Depreciation adjustment transactions, we will use the same accounts as used for Depreciation transactions.</span></span>  
18. <span data-ttu-id="20327-132">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="20327-132">Click Add.</span></span>
19. <span data-ttu-id="20327-133">Nel campo Libro immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="20327-133">In the Book field, enter or select a value.</span></span>
20. <span data-ttu-id="20327-134">Nel campo Conto principale, specificare i valori desiderati.</span><span class="sxs-lookup"><span data-stu-id="20327-134">In the Main account field, specify the desired values.</span></span>
21. <span data-ttu-id="20327-135">Nel campo Conto di contropartita, specificare i valori desiderati.</span><span class="sxs-lookup"><span data-stu-id="20327-135">In the Offset account field, specify the desired values.</span></span>
22. <span data-ttu-id="20327-136">Selezionare 'Vendita di dismissione' nel campo Tipo di transazione.</span><span class="sxs-lookup"><span data-stu-id="20327-136">In the Transaction type field, select 'Disposal - sale'.</span></span>
23. <span data-ttu-id="20327-137">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="20327-137">Click Add.</span></span>
24. <span data-ttu-id="20327-138">Nel campo Libro immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="20327-138">In the Book field, enter or select a value.</span></span>
25. <span data-ttu-id="20327-139">Nel campo Conto principale, specificare i valori desiderati.</span><span class="sxs-lookup"><span data-stu-id="20327-139">In the Main account field, specify the desired values.</span></span>
    * <span data-ttu-id="20327-140">Per Dismissioni, è possibile immettere un conto di contropartita o lasciarlo vuoto perché venga compilato per la transazione specifica.</span><span class="sxs-lookup"><span data-stu-id="20327-140">For Disposals, you can enter an offset account or leave it blank to be filled in for the specific transaction.</span></span>  
26. <span data-ttu-id="20327-141">Selezionare 'Scarto' nel campo Tipo di transazione.</span><span class="sxs-lookup"><span data-stu-id="20327-141">In the Transaction type field, select 'Disposal - scrap'.</span></span>
    * <span data-ttu-id="20327-142">Verranno utilizzati gli stessi conti per la vendita di dismissione e lo scarto di dismissione.</span><span class="sxs-lookup"><span data-stu-id="20327-142">We will use the same accounts for Disposal sale and Disposal scrap.</span></span>  
27. <span data-ttu-id="20327-143">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="20327-143">Click Add.</span></span>
28. <span data-ttu-id="20327-144">Nel campo Libro immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="20327-144">In the Book field, enter or select a value.</span></span>
29. <span data-ttu-id="20327-145">Nel campo Conto principale, specificare i valori desiderati.</span><span class="sxs-lookup"><span data-stu-id="20327-145">In the Main account field, specify the desired values.</span></span>
    * <span data-ttu-id="20327-146">Per Dismissioni, è possibile immettere un conto di contropartita o lasciarlo vuoto perché venga compilato per la transazione specifica.</span><span class="sxs-lookup"><span data-stu-id="20327-146">For Disposals, you can enter an offset account or leave it blank to be filled in for the specific transaction.</span></span>  
30. <span data-ttu-id="20327-147">Espandere la sezione Dismissione.</span><span class="sxs-lookup"><span data-stu-id="20327-147">Expand the Disposal section.</span></span>
    * <span data-ttu-id="20327-148">È necessario impostare i profili di registrazione dismissioni sia per la vendita che per lo scarto.</span><span class="sxs-lookup"><span data-stu-id="20327-148">You must set up disposal posting profiles for both sale and scrap.</span></span>  <span data-ttu-id="20327-149">Si inizierà con le transazioni di vendita di dismissione.</span><span class="sxs-lookup"><span data-stu-id="20327-149">We will start with disposal sale transactions.</span></span>  
31. <span data-ttu-id="20327-150">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="20327-150">Click Add.</span></span>
32. <span data-ttu-id="20327-151">Nel campo Libro immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="20327-151">In the Book field, enter or select a value.</span></span>
33. <span data-ttu-id="20327-152">Nel campo Valore registrato, selezionare "Valore di acquisizione".</span><span class="sxs-lookup"><span data-stu-id="20327-152">In the Post value field, select 'Acquisition value'.</span></span>
    * <span data-ttu-id="20327-153">Il valore di acquisizione indirizzerà i valori di acquisizione e di rettifica acquisizione per tutti gli anni.</span><span class="sxs-lookup"><span data-stu-id="20327-153">Acquisition value will address Acquisition and Acquisition adjustment values for all years.</span></span>  <span data-ttu-id="20327-154">È inoltre possibile definire i conti per questi tipi di transazione separatamente.</span><span class="sxs-lookup"><span data-stu-id="20327-154">You can also define accounts for these transaction types separately.</span></span>  
    * <span data-ttu-id="20327-155">È possibile impostare il processo di dismissione per utilizzare conti diversi a seconda se la dismissione determina una perdita o un profitto.</span><span class="sxs-lookup"><span data-stu-id="20327-155">You can set the disposal process to use different accounts depending upon if the disposal results in a gain or loss.</span></span>  <span data-ttu-id="20327-156">Si imposterà Tipo valore di vendita su "Tutti" per utilizzare gli stessi conti per tutti i tipi di dismissioni.</span><span class="sxs-lookup"><span data-stu-id="20327-156">I will set the Sales value type to “All” to use the same accounts for all types of disposals.</span></span>  
34. <span data-ttu-id="20327-157">Nel campo Conto principale, specificare i valori desiderati.</span><span class="sxs-lookup"><span data-stu-id="20327-157">In the Main account field, specify the desired values.</span></span>
35. <span data-ttu-id="20327-158">Nel campo Conto di contropartita, specificare i valori desiderati.</span><span class="sxs-lookup"><span data-stu-id="20327-158">In the Offset account field, specify the desired values.</span></span>
36. <span data-ttu-id="20327-159">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="20327-159">Click Add.</span></span>
37. <span data-ttu-id="20327-160">Nel campo Libro immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="20327-160">In the Book field, enter or select a value.</span></span>
    * <span data-ttu-id="20327-161">Nel campo Valore registrato, selezionare "Ammortamento (anni precedenti)".</span><span class="sxs-lookup"><span data-stu-id="20327-161">In the Post value field, select 'Depreciation (prior years)'.</span></span>  
38. <span data-ttu-id="20327-162">Nel campo Conto principale, specificare i valori desiderati.</span><span class="sxs-lookup"><span data-stu-id="20327-162">In the Main account field, specify the desired values.</span></span>
39. <span data-ttu-id="20327-163">Nel campo Conto di contropartita, specificare i valori desiderati.</span><span class="sxs-lookup"><span data-stu-id="20327-163">In the Offset account field, specify the desired values.</span></span>
40. <span data-ttu-id="20327-164">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="20327-164">Click Add.</span></span>
41. <span data-ttu-id="20327-165">Nel campo Libro immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="20327-165">In the Book field, enter or select a value.</span></span>
42. <span data-ttu-id="20327-166">Nel campo Valore registrato, selezionare "Ammortamento (anno in corso)".</span><span class="sxs-lookup"><span data-stu-id="20327-166">In the Post value field, select 'Depreciation (this year)'.</span></span>
43. <span data-ttu-id="20327-167">Nel campo Conto principale, specificare i valori desiderati.</span><span class="sxs-lookup"><span data-stu-id="20327-167">In the Main account field, specify the desired values.</span></span>
44. <span data-ttu-id="20327-168">Nel campo Conto di contropartita, specificare i valori desiderati.</span><span class="sxs-lookup"><span data-stu-id="20327-168">In the Offset account field, specify the desired values.</span></span>
45. <span data-ttu-id="20327-169">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="20327-169">Click Add.</span></span>
46. <span data-ttu-id="20327-170">Nel campo Libro immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="20327-170">In the Book field, enter or select a value.</span></span>
47. <span data-ttu-id="20327-171">Nel campo Valore registrato, selezionare "Rettifiche all'ammortamento (anni precedenti)".</span><span class="sxs-lookup"><span data-stu-id="20327-171">In the Post value field, select 'Depreciation adjustments (prior years)'.</span></span>
48. <span data-ttu-id="20327-172">Nel campo Conto principale, specificare i valori desiderati.</span><span class="sxs-lookup"><span data-stu-id="20327-172">In the Main account field, specify the desired values.</span></span>
49. <span data-ttu-id="20327-173">Nel campo Conto di contropartita, specificare i valori desiderati.</span><span class="sxs-lookup"><span data-stu-id="20327-173">In the Offset account field, specify the desired values.</span></span>
50. <span data-ttu-id="20327-174">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="20327-174">Click Add.</span></span>
51. <span data-ttu-id="20327-175">Nel campo Libro immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="20327-175">In the Book field, enter or select a value.</span></span>
52. <span data-ttu-id="20327-176">Nel campo Valore registrato, selezionare "Rettifiche all'ammortamento (anno in corso)".</span><span class="sxs-lookup"><span data-stu-id="20327-176">In the Post value field, select 'Depreciation adjustments (this year)'.</span></span>
53. <span data-ttu-id="20327-177">Nel campo Conto principale, specificare i valori desiderati.</span><span class="sxs-lookup"><span data-stu-id="20327-177">In the Main account field, specify the desired values.</span></span>
54. <span data-ttu-id="20327-178">Nel campo Conto di contropartita, specificare i valori desiderati.</span><span class="sxs-lookup"><span data-stu-id="20327-178">In the Offset account field, specify the desired values.</span></span>
55. <span data-ttu-id="20327-179">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="20327-179">Click Add.</span></span>
56. <span data-ttu-id="20327-180">Nel campo Libro immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="20327-180">In the Book field, enter or select a value.</span></span>
57. <span data-ttu-id="20327-181">Nel campo Valore registrato, selezionare "Valore contabile".</span><span class="sxs-lookup"><span data-stu-id="20327-181">In the Post value field, select 'Net book value'.</span></span>
58. <span data-ttu-id="20327-182">Nel campo Conto principale, specificare i valori desiderati.</span><span class="sxs-lookup"><span data-stu-id="20327-182">In the Main account field, specify the desired values.</span></span>
59. <span data-ttu-id="20327-183">Nel campo Conto di contropartita, specificare i valori desiderati.</span><span class="sxs-lookup"><span data-stu-id="20327-183">In the Offset account field, specify the desired values.</span></span>
60. <span data-ttu-id="20327-184">Nel campo Vendita o scarto selezionare 'Scarto'.</span><span class="sxs-lookup"><span data-stu-id="20327-184">In the Sale or scrap field, select 'Scrap'.</span></span>
61. <span data-ttu-id="20327-185">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="20327-185">Click Add.</span></span>
62. <span data-ttu-id="20327-186">Nel campo Libro immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="20327-186">In the Book field, enter or select a value.</span></span>
63. <span data-ttu-id="20327-187">Nel campo Valore registrato, selezionare "Valore di acquisizione".</span><span class="sxs-lookup"><span data-stu-id="20327-187">In the Post value field, select 'Acquisition value'.</span></span>
64. <span data-ttu-id="20327-188">Nel campo Conto principale, specificare i valori desiderati.</span><span class="sxs-lookup"><span data-stu-id="20327-188">In the Main account field, specify the desired values.</span></span>
65. <span data-ttu-id="20327-189">Nel campo Conto di contropartita, specificare i valori desiderati.</span><span class="sxs-lookup"><span data-stu-id="20327-189">In the Offset account field, specify the desired values.</span></span>
66. <span data-ttu-id="20327-190">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="20327-190">Click Add.</span></span>
67. <span data-ttu-id="20327-191">Nel campo Libro immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="20327-191">In the Book field, enter or select a value.</span></span>
    * <span data-ttu-id="20327-192">Nel campo Valore registrato, selezionare "Ammortamento (anni precedenti)".</span><span class="sxs-lookup"><span data-stu-id="20327-192">In Post value field, select 'Depreciation (prior years)'.</span></span>  
68. <span data-ttu-id="20327-193">Nel campo Conto principale, specificare i valori desiderati.</span><span class="sxs-lookup"><span data-stu-id="20327-193">In the Main account field, specify the desired values.</span></span>
69. <span data-ttu-id="20327-194">Nel campo Conto di contropartita, specificare i valori desiderati.</span><span class="sxs-lookup"><span data-stu-id="20327-194">In the Offset account field, specify the desired values.</span></span>
70. <span data-ttu-id="20327-195">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="20327-195">Click Add.</span></span>
71. <span data-ttu-id="20327-196">Nel campo Libro immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="20327-196">In the Book field, enter or select a value.</span></span>
72. <span data-ttu-id="20327-197">Nel campo Valore registrato, selezionare "Ammortamento (anno in corso)".</span><span class="sxs-lookup"><span data-stu-id="20327-197">In the Post value field, select 'Depreciation (this year)'.</span></span>
73. <span data-ttu-id="20327-198">Nel campo Conto principale, specificare i valori desiderati.</span><span class="sxs-lookup"><span data-stu-id="20327-198">In the Main account field, specify the desired values.</span></span>
74. <span data-ttu-id="20327-199">Nel campo Conto di contropartita, specificare i valori desiderati.</span><span class="sxs-lookup"><span data-stu-id="20327-199">In the Offset account field, specify the desired values.</span></span>
75. <span data-ttu-id="20327-200">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="20327-200">Click Add.</span></span>
76. <span data-ttu-id="20327-201">Nel campo Libro immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="20327-201">In the Book field, enter or select a value.</span></span>
77. <span data-ttu-id="20327-202">Nel campo Valore registrato, selezionare "Rettifiche all'ammortamento (anni precedenti)".</span><span class="sxs-lookup"><span data-stu-id="20327-202">In the Post value field, select 'Depreciation adjustments (prior years)'.</span></span>
78. <span data-ttu-id="20327-203">Nel campo Conto principale, specificare i valori desiderati.</span><span class="sxs-lookup"><span data-stu-id="20327-203">In the Main account field, specify the desired values.</span></span>
79. <span data-ttu-id="20327-204">Nel campo Conto di contropartita, specificare i valori desiderati.</span><span class="sxs-lookup"><span data-stu-id="20327-204">In the Offset account field, specify the desired values.</span></span>
80. <span data-ttu-id="20327-205">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="20327-205">Click Add.</span></span>
81. <span data-ttu-id="20327-206">Nel campo Libro immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="20327-206">In the Book field, enter or select a value.</span></span>
82. <span data-ttu-id="20327-207">Nel campo Valore registrato, selezionare "Rettifiche all'ammortamento (anno in corso)".</span><span class="sxs-lookup"><span data-stu-id="20327-207">In the Post value field, select 'Depreciation adjustments (this year)'.</span></span>
83. <span data-ttu-id="20327-208">Nel campo Conto principale, specificare i valori desiderati.</span><span class="sxs-lookup"><span data-stu-id="20327-208">In the Main account field, specify the desired values.</span></span>
84. <span data-ttu-id="20327-209">Nel campo Conto di contropartita, specificare i valori desiderati.</span><span class="sxs-lookup"><span data-stu-id="20327-209">In the Offset account field, specify the desired values.</span></span>
85. <span data-ttu-id="20327-210">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="20327-210">Click Add.</span></span>
86. <span data-ttu-id="20327-211">Nel campo Libro immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="20327-211">In the Book field, enter or select a value.</span></span>
87. <span data-ttu-id="20327-212">Nel campo Valore registrato, selezionare "Valore contabile".</span><span class="sxs-lookup"><span data-stu-id="20327-212">In the Post value field, select 'Net book value'.</span></span>
88. <span data-ttu-id="20327-213">Nel campo Conto principale, specificare i valori desiderati.</span><span class="sxs-lookup"><span data-stu-id="20327-213">In the Main account field, specify the desired values.</span></span>
89. <span data-ttu-id="20327-214">Nel campo Conto di contropartita, specificare i valori desiderati.</span><span class="sxs-lookup"><span data-stu-id="20327-214">In the Offset account field, specify the desired values.</span></span>


