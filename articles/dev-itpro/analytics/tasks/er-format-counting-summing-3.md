--- 
title: Usare i calcoli per generare l'output per il conteggio e la somma
description: "I passaggi seguenti descrivono come un utente con ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può configurare un formato per la creazione di report elettronici in modo che esegua calcoli e somme in base ai dati dell'output di testo già generato."
author: NickSelin
manager: AnnBe
ms.date: 10/28/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: e782d33f3748524491dace28008cd9148ae70529
ms.openlocfilehash: e09b9fc87619d87c1de0e68ff370c0d6ebe72fc8
ms.contentlocale: it-it
ms.lasthandoff: 08/09/2018

---
# <a name="use-computations-to-generate-the-output-for-counting-and-summing"></a><span data-ttu-id="3590f-103">Usare i calcoli per generare l'output per il conteggio e la somma</span><span class="sxs-lookup"><span data-stu-id="3590f-103">Use computations to generate the output for counting and summing</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="3590f-104">I passaggi seguenti descrivono come un utente con ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può configurare un formato per la creazione di report elettronici in modo che esegua calcoli e somme in base ai dati dell'output di testo già generato.</span><span class="sxs-lookup"><span data-stu-id="3590f-104">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) format to do counting and summing based on data of the already generated text output.</span></span> <span data-ttu-id="3590f-105">Questi passaggi possono essere eseguiti in qualsiasi società.</span><span class="sxs-lookup"><span data-stu-id="3590f-105">These steps can be performed in any company.</span></span>

<span data-ttu-id="3590f-106">Per effettuare queste operazioni, è innanzitutto necessario completare i passaggi nella procedura 'ER Configurare il formato per eseguire conteggi e somme (parte 2: configurare i calcoli)'.</span><span class="sxs-lookup"><span data-stu-id="3590f-106">To complete these steps, you must first complete the steps in the “ER Configure format to do counting and summing (Part 2: Configure computations)” procedure.</span></span>

<span data-ttu-id="3590f-107">Questa procedura è per una funzionalità che è stata aggiunta in Dynamics 365 for Operations versione 1611.</span><span class="sxs-lookup"><span data-stu-id="3590f-107">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="configure-this-report-to-use-counting-and-summing-info"></a><span data-ttu-id="3590f-108">Configurare questo report per utilizzare le informazioni di conteggio e somma</span><span class="sxs-lookup"><span data-stu-id="3590f-108">Configure this report to use counting and summing info</span></span>
1. <span data-ttu-id="3590f-109">Andare ad Amministrazione organizzazione > Aree di lavoro > Creazione di report elettronici.</span><span class="sxs-lookup"><span data-stu-id="3590f-109">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="3590f-110">Fare clic su Configurazioni report.</span><span class="sxs-lookup"><span data-stu-id="3590f-110">Click Reporting configurations.</span></span>
3. <span data-ttu-id="3590f-111">Nella struttura espandere 'Modello Intrastat'.</span><span class="sxs-lookup"><span data-stu-id="3590f-111">In the tree, expand 'Intrastat model'.</span></span>
4. <span data-ttu-id="3590f-112">Nella struttura, espandere 'Modello Intrastat\Intrastat (DE)'.</span><span class="sxs-lookup"><span data-stu-id="3590f-112">In the tree, expand 'Intrastat model\Intrastat (DE)'.</span></span>
5. <span data-ttu-id="3590f-113">Nella struttura selezionare 'Modello Intrastat\Intrastat (DE)\Intrastat (DE) con conteggio e somma'.</span><span class="sxs-lookup"><span data-stu-id="3590f-113">In the tree, select 'Intrastat model\Intrastat (DE)\Intrastat (DE) with counting & summing'.</span></span>
6. <span data-ttu-id="3590f-114">Fare clic su Progettazione.</span><span class="sxs-lookup"><span data-stu-id="3590f-114">Click Designer.</span></span>
7. <span data-ttu-id="3590f-115">Fare clic sulla scheda Mapping.</span><span class="sxs-lookup"><span data-stu-id="3590f-115">Click the Mapping tab.</span></span>
8. <span data-ttu-id="3590f-116">Fare clic su Aggiungi radice per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="3590f-116">Click Add root to open the drop dialog.</span></span>
    * <span data-ttu-id="3590f-117">Aggiungere una nuova origine dati per ottenere l'elenco dei blocchi memorizzati.</span><span class="sxs-lookup"><span data-stu-id="3590f-117">Add a new data source to get the list of memorized blocks.</span></span>  
9. <span data-ttu-id="3590f-118">Nella struttura selezionare "Funzioni\Campo calcolato".</span><span class="sxs-lookup"><span data-stu-id="3590f-118">In the tree, select 'Functions\Calculated field'.</span></span>
10. <span data-ttu-id="3590f-119">Digitare  '$BlocksList' nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="3590f-119">In the Name field, type '$BlocksList'.</span></span>
    * <span data-ttu-id="3590f-120">$BlocksList</span><span class="sxs-lookup"><span data-stu-id="3590f-120">$BlocksList</span></span>  
11. <span data-ttu-id="3590f-121">Fare clic su Modifica formula.</span><span class="sxs-lookup"><span data-stu-id="3590f-121">Click Edit formula.</span></span>
12. <span data-ttu-id="3590f-122">Nella struttura, selezionare 'Funzioni raccolta dati\COLLECTEDLIST'.</span><span class="sxs-lookup"><span data-stu-id="3590f-122">In the tree, select 'Data collection functions\COLLECTEDLIST'.</span></span>
13. <span data-ttu-id="3590f-123">Fare clic su Aggiungi funzione.</span><span class="sxs-lookup"><span data-stu-id="3590f-123">Click Add function.</span></span>
14. <span data-ttu-id="3590f-124">Fare clic su Aggiungi origine dati.</span><span class="sxs-lookup"><span data-stu-id="3590f-124">Click Add data source.</span></span>
15. <span data-ttu-id="3590f-125">Nel campo Formula immettere 'COLLECTEDLIST('$BlockName', '.</span><span class="sxs-lookup"><span data-stu-id="3590f-125">In the Formula field, enter 'COLLECTEDLIST('$BlockName', '.</span></span>
    * <span data-ttu-id="3590f-126">COLLECTEDLIST('$BlockName',</span><span class="sxs-lookup"><span data-stu-id="3590f-126">COLLECTEDLIST('$BlockName',</span></span>  
16. <span data-ttu-id="3590f-127">Nel campo Formula immettere 'COLLECTEDLIST('$BlockName', "\*")'.</span><span class="sxs-lookup"><span data-stu-id="3590f-127">In the Formula field, enter 'COLLECTEDLIST('$BlockName', "\*")'.</span></span>
    * <span data-ttu-id="3590f-128">COLLECTEDLIST('$BlockName', "\*")</span><span class="sxs-lookup"><span data-stu-id="3590f-128">COLLECTEDLIST('$BlockName', "\*")</span></span>  
17. <span data-ttu-id="3590f-129">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="3590f-129">Click Save.</span></span>
    * <span data-ttu-id="3590f-130">Il modello "\*" indica che tutti i blocchi verranno inclusi nell'elenco per il record.</span><span class="sxs-lookup"><span data-stu-id="3590f-130">The pattern “\*” means that all blocks will be included to the list for this record.</span></span>  
18. <span data-ttu-id="3590f-131">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="3590f-131">Close the page.</span></span>
19. <span data-ttu-id="3590f-132">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="3590f-132">Click OK.</span></span>
20. <span data-ttu-id="3590f-133">Fare clic sulla scheda Formato.</span><span class="sxs-lookup"><span data-stu-id="3590f-133">Click the Format tab.</span></span>
21. <span data-ttu-id="3590f-134">Nella struttura selezionare 'Intrastat\Dati'.</span><span class="sxs-lookup"><span data-stu-id="3590f-134">In the tree, select 'Intrastat\Data'.</span></span>
22. <span data-ttu-id="3590f-135">Fare clic su Aggiungi per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="3590f-135">Click Add to open the drop dialog.</span></span>
23. <span data-ttu-id="3590f-136">Nella struttura selezionare 'Testo\Sequenza'.</span><span class="sxs-lookup"><span data-stu-id="3590f-136">In the tree, select 'Text\Sequence'.</span></span>
24. <span data-ttu-id="3590f-137">Nel campo Nome digitare 'Totali per blocchi'.</span><span class="sxs-lookup"><span data-stu-id="3590f-137">In the Name field, type 'Totals by blocks'.</span></span>
    * <span data-ttu-id="3590f-138">Totali per blocchi</span><span class="sxs-lookup"><span data-stu-id="3590f-138">Totals by blocks</span></span>  
25. <span data-ttu-id="3590f-139">Nel campo Caratteri speciali, selezionare 'Nuova riga - Windows (CR LF)'.</span><span class="sxs-lookup"><span data-stu-id="3590f-139">In the Special characters field, select 'New line - Windows (CR LF)'.</span></span>
26. <span data-ttu-id="3590f-140">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="3590f-140">Click OK.</span></span>
27. <span data-ttu-id="3590f-141">Nella struttura selezionare 'Intrastat\Dati\Totali per blocchi'.</span><span class="sxs-lookup"><span data-stu-id="3590f-141">In the tree, select 'Intrastat\Data\Totals by blocks'.</span></span>
28. <span data-ttu-id="3590f-142">Fare clic su Aggiungi per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="3590f-142">Click Add to open the drop dialog.</span></span>
29. <span data-ttu-id="3590f-143">Nella struttura selezionare "Testo\Stringa".</span><span class="sxs-lookup"><span data-stu-id="3590f-143">In the tree, select 'Text\String'.</span></span>
30. <span data-ttu-id="3590f-144">Digitare 'Codice blocco' nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="3590f-144">In the Name field, type 'Block code'.</span></span>
    * <span data-ttu-id="3590f-145">Codice blocco</span><span class="sxs-lookup"><span data-stu-id="3590f-145">Block code</span></span>  
31. <span data-ttu-id="3590f-146">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="3590f-146">Click OK.</span></span>
32. <span data-ttu-id="3590f-147">Fare clic su Aggiungi stringa.</span><span class="sxs-lookup"><span data-stu-id="3590f-147">Click Add String.</span></span>
33. <span data-ttu-id="3590f-148">Nel campo Nome digitare 'Conteggio righe'.</span><span class="sxs-lookup"><span data-stu-id="3590f-148">In the Name field, type 'Lines counting'.</span></span>
    * <span data-ttu-id="3590f-149">Conteggio righe</span><span class="sxs-lookup"><span data-stu-id="3590f-149">Lines counting</span></span>  
34. <span data-ttu-id="3590f-150">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="3590f-150">Click OK.</span></span>
35. <span data-ttu-id="3590f-151">Fare clic su Aggiungi stringa.</span><span class="sxs-lookup"><span data-stu-id="3590f-151">Click Add String.</span></span>
36. <span data-ttu-id="3590f-152">Nel campo Nome digitare 'Importo totale'.</span><span class="sxs-lookup"><span data-stu-id="3590f-152">In the Name field, type 'Total amount'.</span></span>
    * <span data-ttu-id="3590f-153">Importo totale</span><span class="sxs-lookup"><span data-stu-id="3590f-153">Total amount</span></span>  
37. <span data-ttu-id="3590f-154">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="3590f-154">Click OK.</span></span>
38. <span data-ttu-id="3590f-155">Fare clic sulla scheda Mapping.</span><span class="sxs-lookup"><span data-stu-id="3590f-155">Click the Mapping tab.</span></span>
39. <span data-ttu-id="3590f-156">Nella struttura selezionare '$BlocksList'.</span><span class="sxs-lookup"><span data-stu-id="3590f-156">In the tree, select '$BlocksList'.</span></span>
40. <span data-ttu-id="3590f-157">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="3590f-157">Click Bind.</span></span>
    * <span data-ttu-id="3590f-158">Creare una riga di riepilogo per ciascun blocco memorizzato.</span><span class="sxs-lookup"><span data-stu-id="3590f-158">Create a summary line for each memorized block.</span></span>  
41. <span data-ttu-id="3590f-159">Fare clic sulla scheda Formato.</span><span class="sxs-lookup"><span data-stu-id="3590f-159">Click the Format tab.</span></span>
42. <span data-ttu-id="3590f-160">Nella struttura selezionare 'Intrastat\Dati\Totali per blocchi\Codice blocco'.</span><span class="sxs-lookup"><span data-stu-id="3590f-160">In the tree, select 'Intrastat\Data\Totals by blocks\Block code'.</span></span>
43. <span data-ttu-id="3590f-161">Fare clic sulla scheda Mapping.</span><span class="sxs-lookup"><span data-stu-id="3590f-161">Click the Mapping tab.</span></span>
44. <span data-ttu-id="3590f-162">Fare clic su Modifica formula.</span><span class="sxs-lookup"><span data-stu-id="3590f-162">Click Edit formula.</span></span>
45. <span data-ttu-id="3590f-163">Nel campo Formula immettere '"Block id: " & '.</span><span class="sxs-lookup"><span data-stu-id="3590f-163">In the Formula field, enter '"Block id: " & '.</span></span>
    * <span data-ttu-id="3590f-164">"Block id: " &</span><span class="sxs-lookup"><span data-stu-id="3590f-164">"Block id: " &</span></span>  
46. <span data-ttu-id="3590f-165">Nella struttura espandere '$BlocksList'.</span><span class="sxs-lookup"><span data-stu-id="3590f-165">In the tree, expand '$BlocksList'.</span></span>
47. <span data-ttu-id="3590f-166">Nella struttura selezionare '$BlocksList\Value'.</span><span class="sxs-lookup"><span data-stu-id="3590f-166">In the tree, select '$BlocksList\Value'.</span></span>
48. <span data-ttu-id="3590f-167">Fare clic su Aggiungi origine dati.</span><span class="sxs-lookup"><span data-stu-id="3590f-167">Click Add data source.</span></span>
49. <span data-ttu-id="3590f-168">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="3590f-168">Click Save.</span></span>
50. <span data-ttu-id="3590f-169">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="3590f-169">Close the page.</span></span>
51. <span data-ttu-id="3590f-170">Fare clic sulla scheda Formato.</span><span class="sxs-lookup"><span data-stu-id="3590f-170">Click the Format tab.</span></span>
52. <span data-ttu-id="3590f-171">Nella struttura selezionare 'Intrastat\Dati\Totali per blocchi\Conteggio righe'.</span><span class="sxs-lookup"><span data-stu-id="3590f-171">In the tree, select 'Intrastat\Data\Totals by blocks\Lines counting'.</span></span>
53. <span data-ttu-id="3590f-172">Fare clic sulla scheda Mapping.</span><span class="sxs-lookup"><span data-stu-id="3590f-172">Click the Mapping tab.</span></span>
54. <span data-ttu-id="3590f-173">Fare clic su Modifica formula.</span><span class="sxs-lookup"><span data-stu-id="3590f-173">Click Edit formula.</span></span>
    * <span data-ttu-id="3590f-174">Creare l'output per il numero di righe per ciascun blocco presentato nel report.</span><span class="sxs-lookup"><span data-stu-id="3590f-174">Create output for the number of lines for each block presented in this report.</span></span>  
55. <span data-ttu-id="3590f-175">Nel campo Formula, immettere '"Numero di righe in questo blocco: " & '.</span><span class="sxs-lookup"><span data-stu-id="3590f-175">In the Formula field, enter '"Number of lines in this block: " & '.</span></span>
    * <span data-ttu-id="3590f-176">"Numero di righe in questo blocco: " &</span><span class="sxs-lookup"><span data-stu-id="3590f-176">"Number of lines in this block: " &</span></span>  
56. <span data-ttu-id="3590f-177">Nel campo Formula, immettere '"Numero di righe in questo blocco: " & TEXT('.</span><span class="sxs-lookup"><span data-stu-id="3590f-177">In the Formula field, enter '"Number of lines in this block: " & TEXT('.</span></span>
    * <span data-ttu-id="3590f-178">"Numero di righe in questo blocco: " & TEXT(</span><span class="sxs-lookup"><span data-stu-id="3590f-178">"Number of lines in this block: " & TEXT(</span></span>  
57. <span data-ttu-id="3590f-179">Nella struttura, selezionare 'Funzioni raccolta dati\COUNTIFS'.</span><span class="sxs-lookup"><span data-stu-id="3590f-179">In the tree, select 'Data collection functions\COUNTIFS'.</span></span>
58. <span data-ttu-id="3590f-180">Fare clic su Aggiungi funzione.</span><span class="sxs-lookup"><span data-stu-id="3590f-180">Click Add function.</span></span>
59. <span data-ttu-id="3590f-181">Fare clic su Aggiungi origine dati.</span><span class="sxs-lookup"><span data-stu-id="3590f-181">Click Add data source.</span></span>
60. <span data-ttu-id="3590f-182">Nel campo Formula, immettere '"Numero di righe in questo blocco: " & TEXT(COUNTIFS('$BlockName', '.</span><span class="sxs-lookup"><span data-stu-id="3590f-182">In the Formula field, enter '"Number of lines in this block: " & TEXT(COUNTIFS('$BlockName', '.</span></span>
    * <span data-ttu-id="3590f-183">"Numero di righe in questo blocco: " & TEXT(COUNTIFS('$BlockName',</span><span class="sxs-lookup"><span data-stu-id="3590f-183">"Number of lines in this block: " & TEXT(COUNTIFS('$BlockName',</span></span>  
61. <span data-ttu-id="3590f-184">Nella struttura espandere '$BlocksList'.</span><span class="sxs-lookup"><span data-stu-id="3590f-184">In the tree, expand '$BlocksList'.</span></span>
62. <span data-ttu-id="3590f-185">Nella struttura selezionare '$BlocksList\Value'.</span><span class="sxs-lookup"><span data-stu-id="3590f-185">In the tree, select '$BlocksList\Value'.</span></span>
63. <span data-ttu-id="3590f-186">Fare clic su Aggiungi origine dati.</span><span class="sxs-lookup"><span data-stu-id="3590f-186">Click Add data source.</span></span>
64. <span data-ttu-id="3590f-187">Nel campo Formula, immettere '"Numero di righe in questo blocco: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value, '.</span><span class="sxs-lookup"><span data-stu-id="3590f-187">In the Formula field, enter '"Number of lines in this block: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value, '.</span></span>
    * <span data-ttu-id="3590f-188">"Numero di righe in questo blocco: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value,</span><span class="sxs-lookup"><span data-stu-id="3590f-188">"Number of lines in this block: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value,</span></span>  
65. <span data-ttu-id="3590f-189">Nella struttura selezionare '$RecName'.</span><span class="sxs-lookup"><span data-stu-id="3590f-189">In the tree, select '$RecName'.</span></span>
66. <span data-ttu-id="3590f-190">Fare clic su Aggiungi origine dati.</span><span class="sxs-lookup"><span data-stu-id="3590f-190">Click Add data source.</span></span>
67. <span data-ttu-id="3590f-191">Nel campo Formula, immettere '"Numero di righe in questo blocco: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value, '$RecName', "\*"))'.</span><span class="sxs-lookup"><span data-stu-id="3590f-191">In the Formula field, enter '"Number of lines in this block: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value, '$RecName', "\*"))'.</span></span>
    * <span data-ttu-id="3590f-192">"Numero di righe in questo blocco: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value, '$RecName', "\*"))</span><span class="sxs-lookup"><span data-stu-id="3590f-192">"Number of lines in this block: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value, '$RecName', "\*"))</span></span>  
68. <span data-ttu-id="3590f-193">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="3590f-193">Click Save.</span></span>
69. <span data-ttu-id="3590f-194">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="3590f-194">Close the page.</span></span>
70. <span data-ttu-id="3590f-195">Fare clic sulla scheda Formato.</span><span class="sxs-lookup"><span data-stu-id="3590f-195">Click the Format tab.</span></span>
71. <span data-ttu-id="3590f-196">Nella struttura selezionare 'Intrastat\Dati\Totali per blocchi\Importo totale'.</span><span class="sxs-lookup"><span data-stu-id="3590f-196">In the tree, select 'Intrastat\Data\Totals by blocks\Total amount'.</span></span>
72. <span data-ttu-id="3590f-197">Fare clic sulla scheda Mapping.</span><span class="sxs-lookup"><span data-stu-id="3590f-197">Click the Mapping tab.</span></span>
73. <span data-ttu-id="3590f-198">Fare clic su Modifica formula.</span><span class="sxs-lookup"><span data-stu-id="3590f-198">Click Edit formula.</span></span>
    * <span data-ttu-id="3590f-199">Creare l'output che costituirà il totale dell'importo fatturato per ciascun blocco presentato nel report.</span><span class="sxs-lookup"><span data-stu-id="3590f-199">Create output that will be the total of the invoiced amount for each block presented in this report.</span></span>  
74. <span data-ttu-id="3590f-200">Nel campo Formula immettere '"Somma dell'importo fatturato: " & TEXT(SUMIFS('$InvName', '$BlockName', '$BlocksList'.Value, '$RecName', "\*"))'.</span><span class="sxs-lookup"><span data-stu-id="3590f-200">In the Formula field, enter '"Sum of invoiced amount: " & TEXT(SUMIFS('$InvName', '$BlockName', '$BlocksList'.Value, '$RecName', "\*"))'.</span></span>
    * <span data-ttu-id="3590f-201">"Somma dell'importo fatturato: " & TEXT(SUMIFS('$InvName', '$BlockName', '$BlocksList'.Value, '$RecName', "\*"))</span><span class="sxs-lookup"><span data-stu-id="3590f-201">"Sum of invoiced amount: " & TEXT(SUMIFS('$InvName', '$BlockName', '$BlocksList'.Value, '$RecName', "\*"))</span></span>  
75. <span data-ttu-id="3590f-202">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="3590f-202">Click Save.</span></span>
76. <span data-ttu-id="3590f-203">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="3590f-203">Close the page.</span></span>
77. <span data-ttu-id="3590f-204">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="3590f-204">Click Save.</span></span>
78. <span data-ttu-id="3590f-205">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="3590f-205">Close the page.</span></span>


