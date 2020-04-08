---
title: "ER Configurare il formato per eseguire il conteggio e la sommatoria (Parte 3: usare i calcoli per creare l'output)"
description: I passaggi seguenti descrivono come un utente con ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può configurare un formato per la creazione di report elettronici in modo che esegua calcoli e somme in base ai dati dell'output di testo già generato.
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, EROperationDesigner, ERDataSourceAddDropDialog, ERExpressionDesignerFormula, ERComponentTypeDropDialog
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e8a4965c07c5a084b21da40667747db36530284c
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/18/2020
ms.locfileid: "3141953"
---
# <a name="er-configure-format-to-do-counting-and-summing-part-3---use-computations-to-make-the-output"></a><span data-ttu-id="43514-103">ER Configurare il formato per eseguire il conteggio e la sommatoria (Parte 3: usare i calcoli per creare l'output)</span><span class="sxs-lookup"><span data-stu-id="43514-103">ER Configure format to do counting and summing (Part 3 - Use computations to make the output)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="43514-104">I passaggi seguenti descrivono come un utente con ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può configurare un formato per la creazione di report elettronici in modo che esegua calcoli e somme in base ai dati dell'output di testo già generato.</span><span class="sxs-lookup"><span data-stu-id="43514-104">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) format to do counting and summing based on data of the already generated text output.</span></span> <span data-ttu-id="43514-105">Questi passaggi possono essere eseguiti in qualsiasi società.</span><span class="sxs-lookup"><span data-stu-id="43514-105">These steps can be performed in any company.</span></span>

<span data-ttu-id="43514-106">Per effettuare queste operazioni, è innanzitutto necessario completare i passaggi nella procedura "ER Configurare il formato per eseguire conteggi e somme (parte 2: configurare i calcoli)".</span><span class="sxs-lookup"><span data-stu-id="43514-106">To complete these steps, you must first complete the steps in the "ER Configure format to do counting and summing (Part 2: Configure computations)" procedure.</span></span>

<span data-ttu-id="43514-107">Questa procedura è per una funzionalità che è stata aggiunta in Dynamics 365 for Operations versione 1611.</span><span class="sxs-lookup"><span data-stu-id="43514-107">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="configure-this-report-to-use-counting-and-summing-info"></a><span data-ttu-id="43514-108">Configurare questo report per utilizzare le informazioni di conteggio e somma</span><span class="sxs-lookup"><span data-stu-id="43514-108">Configure this report to use counting and summing info</span></span>
1. <span data-ttu-id="43514-109">Andare ad Amministrazione organizzazione > Aree di lavoro > Creazione di report elettronici.</span><span class="sxs-lookup"><span data-stu-id="43514-109">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="43514-110">Fare clic su Configurazioni report.</span><span class="sxs-lookup"><span data-stu-id="43514-110">Click Reporting configurations.</span></span>
3. <span data-ttu-id="43514-111">Nella struttura espandere 'Modello Intrastat'.</span><span class="sxs-lookup"><span data-stu-id="43514-111">In the tree, expand 'Intrastat model'.</span></span>
4. <span data-ttu-id="43514-112">Nella struttura, espandere 'Modello Intrastat\Intrastat (DE)'.</span><span class="sxs-lookup"><span data-stu-id="43514-112">In the tree, expand 'Intrastat model\Intrastat (DE)'.</span></span>
5. <span data-ttu-id="43514-113">Nella struttura selezionare 'Modello Intrastat\Intrastat (DE)\Intrastat (DE) con conteggio e somma'.</span><span class="sxs-lookup"><span data-stu-id="43514-113">In the tree, select 'Intrastat model\Intrastat (DE)\Intrastat (DE) with counting & summing'.</span></span>
6. <span data-ttu-id="43514-114">Fare clic su Progettazione.</span><span class="sxs-lookup"><span data-stu-id="43514-114">Click Designer.</span></span>
7. <span data-ttu-id="43514-115">Fare clic sulla scheda Mapping.</span><span class="sxs-lookup"><span data-stu-id="43514-115">Click the Mapping tab.</span></span>
8. <span data-ttu-id="43514-116">Fare clic su Aggiungi radice per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="43514-116">Click Add root to open the drop dialog.</span></span>
    * <span data-ttu-id="43514-117">Aggiungere una nuova origine dati per ottenere l'elenco dei blocchi memorizzati.</span><span class="sxs-lookup"><span data-stu-id="43514-117">Add a new data source to get the list of memorized blocks.</span></span>  
9. <span data-ttu-id="43514-118">Nella struttura selezionare "Funzioni\Campo calcolato".</span><span class="sxs-lookup"><span data-stu-id="43514-118">In the tree, select 'Functions\Calculated field'.</span></span>
10. <span data-ttu-id="43514-119">Digitare  '$BlocksList' nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="43514-119">In the Name field, type '$BlocksList'.</span></span>
    * <span data-ttu-id="43514-120">$BlocksList</span><span class="sxs-lookup"><span data-stu-id="43514-120">$BlocksList</span></span>  
11. <span data-ttu-id="43514-121">Fare clic su Modifica formula.</span><span class="sxs-lookup"><span data-stu-id="43514-121">Click Edit formula.</span></span>
12. <span data-ttu-id="43514-122">Nella struttura, selezionare 'Funzioni raccolta dati\COLLECTEDLIST'.</span><span class="sxs-lookup"><span data-stu-id="43514-122">In the tree, select 'Data collection functions\COLLECTEDLIST'.</span></span>
13. <span data-ttu-id="43514-123">Fare clic su Aggiungi funzione.</span><span class="sxs-lookup"><span data-stu-id="43514-123">Click Add function.</span></span>
14. <span data-ttu-id="43514-124">Fare clic su Aggiungi origine dati.</span><span class="sxs-lookup"><span data-stu-id="43514-124">Click Add data source.</span></span>
15. <span data-ttu-id="43514-125">Nel campo Formula immettere 'COLLECTEDLIST('$BlockName', '.</span><span class="sxs-lookup"><span data-stu-id="43514-125">In the Formula field, enter 'COLLECTEDLIST('$BlockName', '.</span></span>
    * <span data-ttu-id="43514-126">COLLECTEDLIST('$BlockName',</span><span class="sxs-lookup"><span data-stu-id="43514-126">COLLECTEDLIST('$BlockName',</span></span>  
16. <span data-ttu-id="43514-127">Nel campo Formula immettere 'COLLECTEDLIST('$BlockName', "\*")'.</span><span class="sxs-lookup"><span data-stu-id="43514-127">In the Formula field, enter 'COLLECTEDLIST('$BlockName', "\*")'.</span></span>
    * <span data-ttu-id="43514-128">COLLECTEDLIST('$BlockName', "\*")</span><span class="sxs-lookup"><span data-stu-id="43514-128">COLLECTEDLIST('$BlockName', "\*")</span></span>  
17. <span data-ttu-id="43514-129">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="43514-129">Click Save.</span></span>
    * <span data-ttu-id="43514-130">Il modello "\*" indica che tutti i blocchi verranno inclusi nell'elenco per il record.</span><span class="sxs-lookup"><span data-stu-id="43514-130">The pattern "\*" means that all blocks will be included to the list for this record.</span></span>  
18. <span data-ttu-id="43514-131">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="43514-131">Close the page.</span></span>
19. <span data-ttu-id="43514-132">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="43514-132">Click OK.</span></span>
20. <span data-ttu-id="43514-133">Fare clic sulla scheda Formato.</span><span class="sxs-lookup"><span data-stu-id="43514-133">Click the Format tab.</span></span>
21. <span data-ttu-id="43514-134">Nella struttura selezionare 'Intrastat\Dati'.</span><span class="sxs-lookup"><span data-stu-id="43514-134">In the tree, select 'Intrastat\Data'.</span></span>
22. <span data-ttu-id="43514-135">Fare clic su Aggiungi per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="43514-135">Click Add to open the drop dialog.</span></span>
23. <span data-ttu-id="43514-136">Nella struttura selezionare 'Testo\Sequenza'.</span><span class="sxs-lookup"><span data-stu-id="43514-136">In the tree, select 'Text\Sequence'.</span></span>
24. <span data-ttu-id="43514-137">Nel campo Nome digitare 'Totali per blocchi'.</span><span class="sxs-lookup"><span data-stu-id="43514-137">In the Name field, type 'Totals by blocks'.</span></span>
    * <span data-ttu-id="43514-138">Totali per blocchi</span><span class="sxs-lookup"><span data-stu-id="43514-138">Totals by blocks</span></span>  
25. <span data-ttu-id="43514-139">Nel campo Caratteri speciali, selezionare 'Nuova riga - Windows (CR LF)'.</span><span class="sxs-lookup"><span data-stu-id="43514-139">In the Special characters field, select 'New line - Windows (CR LF)'.</span></span>
26. <span data-ttu-id="43514-140">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="43514-140">Click OK.</span></span>
27. <span data-ttu-id="43514-141">Nella struttura selezionare 'Intrastat\Dati\Totali per blocchi'.</span><span class="sxs-lookup"><span data-stu-id="43514-141">In the tree, select 'Intrastat\Data\Totals by blocks'.</span></span>
28. <span data-ttu-id="43514-142">Fare clic su Aggiungi per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="43514-142">Click Add to open the drop dialog.</span></span>
29. <span data-ttu-id="43514-143">Nella struttura selezionare "Testo\Stringa".</span><span class="sxs-lookup"><span data-stu-id="43514-143">In the tree, select 'Text\String'.</span></span>
30. <span data-ttu-id="43514-144">Digitare 'Codice blocco' nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="43514-144">In the Name field, type 'Block code'.</span></span>
    * <span data-ttu-id="43514-145">Codice blocco</span><span class="sxs-lookup"><span data-stu-id="43514-145">Block code</span></span>  
31. <span data-ttu-id="43514-146">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="43514-146">Click OK.</span></span>
32. <span data-ttu-id="43514-147">Fare clic su Aggiungi stringa.</span><span class="sxs-lookup"><span data-stu-id="43514-147">Click Add String.</span></span>
33. <span data-ttu-id="43514-148">Nel campo Nome digitare 'Conteggio righe'.</span><span class="sxs-lookup"><span data-stu-id="43514-148">In the Name field, type 'Lines counting'.</span></span>
    * <span data-ttu-id="43514-149">Conteggio righe</span><span class="sxs-lookup"><span data-stu-id="43514-149">Lines counting</span></span>  
34. <span data-ttu-id="43514-150">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="43514-150">Click OK.</span></span>
35. <span data-ttu-id="43514-151">Fare clic su Aggiungi stringa.</span><span class="sxs-lookup"><span data-stu-id="43514-151">Click Add String.</span></span>
36. <span data-ttu-id="43514-152">Nel campo Nome digitare 'Importo totale'.</span><span class="sxs-lookup"><span data-stu-id="43514-152">In the Name field, type 'Total amount'.</span></span>
    * <span data-ttu-id="43514-153">Importo totale</span><span class="sxs-lookup"><span data-stu-id="43514-153">Total amount</span></span>  
37. <span data-ttu-id="43514-154">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="43514-154">Click OK.</span></span>
38. <span data-ttu-id="43514-155">Fare clic sulla scheda Mapping.</span><span class="sxs-lookup"><span data-stu-id="43514-155">Click the Mapping tab.</span></span>
39. <span data-ttu-id="43514-156">Nella struttura selezionare '$BlocksList'.</span><span class="sxs-lookup"><span data-stu-id="43514-156">In the tree, select '$BlocksList'.</span></span>
40. <span data-ttu-id="43514-157">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="43514-157">Click Bind.</span></span>
    * <span data-ttu-id="43514-158">Creare una riga di riepilogo per ciascun blocco memorizzato.</span><span class="sxs-lookup"><span data-stu-id="43514-158">Create a summary line for each memorized block.</span></span>  
41. <span data-ttu-id="43514-159">Fare clic sulla scheda Formato.</span><span class="sxs-lookup"><span data-stu-id="43514-159">Click the Format tab.</span></span>
42. <span data-ttu-id="43514-160">Nella struttura selezionare 'Intrastat\Dati\Totali per blocchi\Codice blocco'.</span><span class="sxs-lookup"><span data-stu-id="43514-160">In the tree, select 'Intrastat\Data\Totals by blocks\Block code'.</span></span>
43. <span data-ttu-id="43514-161">Fare clic sulla scheda Mapping.</span><span class="sxs-lookup"><span data-stu-id="43514-161">Click the Mapping tab.</span></span>
44. <span data-ttu-id="43514-162">Fare clic su Modifica formula.</span><span class="sxs-lookup"><span data-stu-id="43514-162">Click Edit formula.</span></span>
45. <span data-ttu-id="43514-163">Nel campo Formula immettere '"Block id: " & '.</span><span class="sxs-lookup"><span data-stu-id="43514-163">In the Formula field, enter '"Block id: " & '.</span></span>
    * <span data-ttu-id="43514-164">"Block id: " &</span><span class="sxs-lookup"><span data-stu-id="43514-164">"Block id: " &</span></span>  
46. <span data-ttu-id="43514-165">Nella struttura espandere '$BlocksList'.</span><span class="sxs-lookup"><span data-stu-id="43514-165">In the tree, expand '$BlocksList'.</span></span>
47. <span data-ttu-id="43514-166">Nella struttura selezionare '$BlocksList\Value'.</span><span class="sxs-lookup"><span data-stu-id="43514-166">In the tree, select '$BlocksList\Value'.</span></span>
48. <span data-ttu-id="43514-167">Fare clic su Aggiungi origine dati.</span><span class="sxs-lookup"><span data-stu-id="43514-167">Click Add data source.</span></span>
49. <span data-ttu-id="43514-168">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="43514-168">Click Save.</span></span>
50. <span data-ttu-id="43514-169">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="43514-169">Close the page.</span></span>
51. <span data-ttu-id="43514-170">Fare clic sulla scheda Formato.</span><span class="sxs-lookup"><span data-stu-id="43514-170">Click the Format tab.</span></span>
52. <span data-ttu-id="43514-171">Nella struttura selezionare 'Intrastat\Dati\Totali per blocchi\Conteggio righe'.</span><span class="sxs-lookup"><span data-stu-id="43514-171">In the tree, select 'Intrastat\Data\Totals by blocks\Lines counting'.</span></span>
53. <span data-ttu-id="43514-172">Fare clic sulla scheda Mapping.</span><span class="sxs-lookup"><span data-stu-id="43514-172">Click the Mapping tab.</span></span>
54. <span data-ttu-id="43514-173">Fare clic su Modifica formula.</span><span class="sxs-lookup"><span data-stu-id="43514-173">Click Edit formula.</span></span>
    * <span data-ttu-id="43514-174">Creare l'output per il numero di righe per ciascun blocco presentato nel report.</span><span class="sxs-lookup"><span data-stu-id="43514-174">Create output for the number of lines for each block presented in this report.</span></span>  
55. <span data-ttu-id="43514-175">Nel campo Formula, immettere '"Numero di righe in questo blocco: " & '.</span><span class="sxs-lookup"><span data-stu-id="43514-175">In the Formula field, enter '"Number of lines in this block: " & '.</span></span>
    * <span data-ttu-id="43514-176">"Numero di righe in questo blocco: " &</span><span class="sxs-lookup"><span data-stu-id="43514-176">"Number of lines in this block: " &</span></span>  
56. <span data-ttu-id="43514-177">Nel campo Formula, immettere '"Numero di righe in questo blocco: " & TEXT('.</span><span class="sxs-lookup"><span data-stu-id="43514-177">In the Formula field, enter '"Number of lines in this block: " & TEXT('.</span></span>
    * <span data-ttu-id="43514-178">"Numero di righe in questo blocco: " & TEXT(</span><span class="sxs-lookup"><span data-stu-id="43514-178">"Number of lines in this block: " & TEXT(</span></span>  
57. <span data-ttu-id="43514-179">Nella struttura, selezionare 'Funzioni raccolta dati\COUNTIFS'.</span><span class="sxs-lookup"><span data-stu-id="43514-179">In the tree, select 'Data collection functions\COUNTIFS'.</span></span>
58. <span data-ttu-id="43514-180">Fare clic su Aggiungi funzione.</span><span class="sxs-lookup"><span data-stu-id="43514-180">Click Add function.</span></span>
59. <span data-ttu-id="43514-181">Fare clic su Aggiungi origine dati.</span><span class="sxs-lookup"><span data-stu-id="43514-181">Click Add data source.</span></span>
60. <span data-ttu-id="43514-182">Nel campo Formula, immettere '"Numero di righe in questo blocco: " & TEXT(COUNTIFS('$BlockName', '.</span><span class="sxs-lookup"><span data-stu-id="43514-182">In the Formula field, enter '"Number of lines in this block: " & TEXT(COUNTIFS('$BlockName', '.</span></span>
    * <span data-ttu-id="43514-183">"Numero di righe in questo blocco: " & TEXT(COUNTIFS('$BlockName',</span><span class="sxs-lookup"><span data-stu-id="43514-183">"Number of lines in this block: " & TEXT(COUNTIFS('$BlockName',</span></span>  
61. <span data-ttu-id="43514-184">Nella struttura espandere '$BlocksList'.</span><span class="sxs-lookup"><span data-stu-id="43514-184">In the tree, expand '$BlocksList'.</span></span>
62. <span data-ttu-id="43514-185">Nella struttura selezionare '$BlocksList\Value'.</span><span class="sxs-lookup"><span data-stu-id="43514-185">In the tree, select '$BlocksList\Value'.</span></span>
63. <span data-ttu-id="43514-186">Fare clic su Aggiungi origine dati.</span><span class="sxs-lookup"><span data-stu-id="43514-186">Click Add data source.</span></span>
64. <span data-ttu-id="43514-187">Nel campo Formula, immettere '"Numero di righe in questo blocco: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value, '.</span><span class="sxs-lookup"><span data-stu-id="43514-187">In the Formula field, enter '"Number of lines in this block: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value, '.</span></span>
    * <span data-ttu-id="43514-188">"Numero di righe in questo blocco: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value,</span><span class="sxs-lookup"><span data-stu-id="43514-188">"Number of lines in this block: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value,</span></span>  
65. <span data-ttu-id="43514-189">Nella struttura selezionare '$RecName'.</span><span class="sxs-lookup"><span data-stu-id="43514-189">In the tree, select '$RecName'.</span></span>
66. <span data-ttu-id="43514-190">Fare clic su Aggiungi origine dati.</span><span class="sxs-lookup"><span data-stu-id="43514-190">Click Add data source.</span></span>
67. <span data-ttu-id="43514-191">Nel campo Formula, immettere '"Numero di righe in questo blocco: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value, '$RecName', "\*"))'.</span><span class="sxs-lookup"><span data-stu-id="43514-191">In the Formula field, enter '"Number of lines in this block: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value, '$RecName', "\*"))'.</span></span>
    * <span data-ttu-id="43514-192">"Numero di righe in questo blocco: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value, '$RecName', "\*"))</span><span class="sxs-lookup"><span data-stu-id="43514-192">"Number of lines in this block: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value, '$RecName', "\*"))</span></span>  
68. <span data-ttu-id="43514-193">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="43514-193">Click Save.</span></span>
69. <span data-ttu-id="43514-194">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="43514-194">Close the page.</span></span>
70. <span data-ttu-id="43514-195">Fare clic sulla scheda Formato.</span><span class="sxs-lookup"><span data-stu-id="43514-195">Click the Format tab.</span></span>
71. <span data-ttu-id="43514-196">Nella struttura selezionare 'Intrastat\Dati\Totali per blocchi\Importo totale'.</span><span class="sxs-lookup"><span data-stu-id="43514-196">In the tree, select 'Intrastat\Data\Totals by blocks\Total amount'.</span></span>
72. <span data-ttu-id="43514-197">Fare clic sulla scheda Mapping.</span><span class="sxs-lookup"><span data-stu-id="43514-197">Click the Mapping tab.</span></span>
73. <span data-ttu-id="43514-198">Fare clic su Modifica formula.</span><span class="sxs-lookup"><span data-stu-id="43514-198">Click Edit formula.</span></span>
    * <span data-ttu-id="43514-199">Creare l'output che costituirà il totale dell'importo fatturato per ciascun blocco presentato nel report.</span><span class="sxs-lookup"><span data-stu-id="43514-199">Create output that will be the total of the invoiced amount for each block presented in this report.</span></span>  
74. <span data-ttu-id="43514-200">Nel campo Formula immettere '"Somma dell'importo fatturato: " & TEXT(SUMIFS('$InvName', '$BlockName', '$BlocksList'.Value, '$RecName', "\*"))'.</span><span class="sxs-lookup"><span data-stu-id="43514-200">In the Formula field, enter '"Sum of invoiced amount: " & TEXT(SUMIFS('$InvName', '$BlockName', '$BlocksList'.Value, '$RecName', "\*"))'.</span></span>
    * <span data-ttu-id="43514-201">"Somma dell'importo fatturato: " & TEXT(SUMIFS('$InvName', '$BlockName', '$BlocksList'.Value, '$RecName', "\*"))</span><span class="sxs-lookup"><span data-stu-id="43514-201">"Sum of invoiced amount: " & TEXT(SUMIFS('$InvName', '$BlockName', '$BlocksList'.Value, '$RecName', "\*"))</span></span>  
75. <span data-ttu-id="43514-202">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="43514-202">Click Save.</span></span>
76. <span data-ttu-id="43514-203">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="43514-203">Close the page.</span></span>
77. <span data-ttu-id="43514-204">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="43514-204">Click Save.</span></span>
78. <span data-ttu-id="43514-205">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="43514-205">Close the page.</span></span>

