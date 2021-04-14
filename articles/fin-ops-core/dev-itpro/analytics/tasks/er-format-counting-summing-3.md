---
title: "ER Configurare il formato per eseguire il conteggio e la sommatoria (Parte 3: usare i calcoli per creare l'output)"
description: Questo argomento descrive come configurare un formato di report elettronico per eseguire il conteggio e la somma in base ai dati dell'output di testo già generato. (Parte 3)
author: NickSelin
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, EROperationDesigner, ERDataSourceAddDropDialog, ERExpressionDesignerFormula, ERComponentTypeDropDialog
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7073539ed4c1d9d5acbb0ca84b43538d87fc8b4b
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5748999"
---
# <a name="er-configure-format-to-do-counting-and-summing-part-3---use-computations-to-make-the-output"></a><span data-ttu-id="5af79-104">ER Configurare il formato per eseguire il conteggio e la sommatoria (Parte 3: usare i calcoli per creare l'output)</span><span class="sxs-lookup"><span data-stu-id="5af79-104">ER Configure format to do counting and summing (Part 3 - Use computations to make the output)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="5af79-105">I passaggi seguenti descrivono come un utente con ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può configurare un formato per la creazione di report elettronici in modo che esegua calcoli e somme in base ai dati dell'output di testo già generato.</span><span class="sxs-lookup"><span data-stu-id="5af79-105">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) format to do counting and summing based on data of the already generated text output.</span></span> <span data-ttu-id="5af79-106">Questi passaggi possono essere eseguiti in qualsiasi società.</span><span class="sxs-lookup"><span data-stu-id="5af79-106">These steps can be performed in any company.</span></span>

<span data-ttu-id="5af79-107">Per effettuare queste operazioni, è innanzitutto necessario completare i passaggi nella procedura "ER Configurare il formato per eseguire conteggi e somme (parte 2: configurare i calcoli)".</span><span class="sxs-lookup"><span data-stu-id="5af79-107">To complete these steps, you must first complete the steps in the "ER Configure format to do counting and summing (Part 2: Configure computations)" procedure.</span></span>

<span data-ttu-id="5af79-108">Questa procedura è per una funzionalità che è stata aggiunta in Dynamics 365 for Operations versione 1611.</span><span class="sxs-lookup"><span data-stu-id="5af79-108">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="configure-this-report-to-use-counting-and-summing-info"></a><span data-ttu-id="5af79-109">Configurare questo report per utilizzare le informazioni di conteggio e somma</span><span class="sxs-lookup"><span data-stu-id="5af79-109">Configure this report to use counting and summing info</span></span>
1. <span data-ttu-id="5af79-110">Andare ad Amministrazione organizzazione > Aree di lavoro > Creazione di report elettronici.</span><span class="sxs-lookup"><span data-stu-id="5af79-110">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="5af79-111">Fare clic su Configurazioni report.</span><span class="sxs-lookup"><span data-stu-id="5af79-111">Click Reporting configurations.</span></span>
3. <span data-ttu-id="5af79-112">Nella struttura espandere 'Modello Intrastat'.</span><span class="sxs-lookup"><span data-stu-id="5af79-112">In the tree, expand 'Intrastat model'.</span></span>
4. <span data-ttu-id="5af79-113">Nella struttura, espandere 'Modello Intrastat\Intrastat (DE)'.</span><span class="sxs-lookup"><span data-stu-id="5af79-113">In the tree, expand 'Intrastat model\Intrastat (DE)'.</span></span>
5. <span data-ttu-id="5af79-114">Nella struttura selezionare 'Modello Intrastat\Intrastat (DE)\Intrastat (DE) con conteggio e somma'.</span><span class="sxs-lookup"><span data-stu-id="5af79-114">In the tree, select 'Intrastat model\Intrastat (DE)\Intrastat (DE) with counting & summing'.</span></span>
6. <span data-ttu-id="5af79-115">Fare clic su Progettazione.</span><span class="sxs-lookup"><span data-stu-id="5af79-115">Click Designer.</span></span>
7. <span data-ttu-id="5af79-116">Fare clic sulla scheda Mapping.</span><span class="sxs-lookup"><span data-stu-id="5af79-116">Click the Mapping tab.</span></span>
8. <span data-ttu-id="5af79-117">Fare clic su Aggiungi radice per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="5af79-117">Click Add root to open the drop dialog.</span></span>
    * <span data-ttu-id="5af79-118">Aggiungere una nuova origine dati per ottenere l'elenco dei blocchi memorizzati.</span><span class="sxs-lookup"><span data-stu-id="5af79-118">Add a new data source to get the list of memorized blocks.</span></span>  
9. <span data-ttu-id="5af79-119">Nella struttura selezionare "Funzioni\Campo calcolato".</span><span class="sxs-lookup"><span data-stu-id="5af79-119">In the tree, select 'Functions\Calculated field'.</span></span>
10. <span data-ttu-id="5af79-120">Digitare  '$BlocksList' nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="5af79-120">In the Name field, type '$BlocksList'.</span></span>
    * <span data-ttu-id="5af79-121">$BlocksList</span><span class="sxs-lookup"><span data-stu-id="5af79-121">$BlocksList</span></span>  
11. <span data-ttu-id="5af79-122">Fare clic su Modifica formula.</span><span class="sxs-lookup"><span data-stu-id="5af79-122">Click Edit formula.</span></span>
12. <span data-ttu-id="5af79-123">Nella struttura, selezionare 'Funzioni raccolta dati\COLLECTEDLIST'.</span><span class="sxs-lookup"><span data-stu-id="5af79-123">In the tree, select 'Data collection functions\COLLECTEDLIST'.</span></span>
13. <span data-ttu-id="5af79-124">Fare clic su Aggiungi funzione.</span><span class="sxs-lookup"><span data-stu-id="5af79-124">Click Add function.</span></span>
14. <span data-ttu-id="5af79-125">Fare clic su Aggiungi origine dati.</span><span class="sxs-lookup"><span data-stu-id="5af79-125">Click Add data source.</span></span>
15. <span data-ttu-id="5af79-126">Nel campo Formula immettere 'COLLECTEDLIST('$BlockName', '.</span><span class="sxs-lookup"><span data-stu-id="5af79-126">In the Formula field, enter 'COLLECTEDLIST('$BlockName', '.</span></span>
    * <span data-ttu-id="5af79-127">COLLECTEDLIST('$BlockName',</span><span class="sxs-lookup"><span data-stu-id="5af79-127">COLLECTEDLIST('$BlockName',</span></span>  
16. <span data-ttu-id="5af79-128">Nel campo Formula immettere 'COLLECTEDLIST('$BlockName', "\*")'.</span><span class="sxs-lookup"><span data-stu-id="5af79-128">In the Formula field, enter 'COLLECTEDLIST('$BlockName', "\*")'.</span></span>
    * <span data-ttu-id="5af79-129">COLLECTEDLIST('$BlockName', "\*")</span><span class="sxs-lookup"><span data-stu-id="5af79-129">COLLECTEDLIST('$BlockName', "\*")</span></span>  
17. <span data-ttu-id="5af79-130">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="5af79-130">Click Save.</span></span>
    * <span data-ttu-id="5af79-131">Il modello "\*" indica che tutti i blocchi verranno inclusi nell'elenco per il record.</span><span class="sxs-lookup"><span data-stu-id="5af79-131">The pattern "\*" means that all blocks will be included to the list for this record.</span></span>  
18. <span data-ttu-id="5af79-132">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="5af79-132">Close the page.</span></span>
19. <span data-ttu-id="5af79-133">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="5af79-133">Click OK.</span></span>
20. <span data-ttu-id="5af79-134">Fare clic sulla scheda Formato.</span><span class="sxs-lookup"><span data-stu-id="5af79-134">Click the Format tab.</span></span>
21. <span data-ttu-id="5af79-135">Nella struttura selezionare 'Intrastat\Dati'.</span><span class="sxs-lookup"><span data-stu-id="5af79-135">In the tree, select 'Intrastat\Data'.</span></span>
22. <span data-ttu-id="5af79-136">Fare clic su Aggiungi per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="5af79-136">Click Add to open the drop dialog.</span></span>
23. <span data-ttu-id="5af79-137">Nella struttura selezionare 'Testo\Sequenza'.</span><span class="sxs-lookup"><span data-stu-id="5af79-137">In the tree, select 'Text\Sequence'.</span></span>
24. <span data-ttu-id="5af79-138">Nel campo Nome digitare 'Totali per blocchi'.</span><span class="sxs-lookup"><span data-stu-id="5af79-138">In the Name field, type 'Totals by blocks'.</span></span>
    * <span data-ttu-id="5af79-139">Totali per blocchi</span><span class="sxs-lookup"><span data-stu-id="5af79-139">Totals by blocks</span></span>  
25. <span data-ttu-id="5af79-140">Nel campo Caratteri speciali, selezionare 'Nuova riga - Windows (CR LF)'.</span><span class="sxs-lookup"><span data-stu-id="5af79-140">In the Special characters field, select 'New line - Windows (CR LF)'.</span></span>
26. <span data-ttu-id="5af79-141">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="5af79-141">Click OK.</span></span>
27. <span data-ttu-id="5af79-142">Nella struttura selezionare 'Intrastat\Dati\Totali per blocchi'.</span><span class="sxs-lookup"><span data-stu-id="5af79-142">In the tree, select 'Intrastat\Data\Totals by blocks'.</span></span>
28. <span data-ttu-id="5af79-143">Fare clic su Aggiungi per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="5af79-143">Click Add to open the drop dialog.</span></span>
29. <span data-ttu-id="5af79-144">Nella struttura selezionare "Testo\Stringa".</span><span class="sxs-lookup"><span data-stu-id="5af79-144">In the tree, select 'Text\String'.</span></span>
30. <span data-ttu-id="5af79-145">Digitare 'Codice blocco' nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="5af79-145">In the Name field, type 'Block code'.</span></span>
    * <span data-ttu-id="5af79-146">Codice blocco</span><span class="sxs-lookup"><span data-stu-id="5af79-146">Block code</span></span>  
31. <span data-ttu-id="5af79-147">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="5af79-147">Click OK.</span></span>
32. <span data-ttu-id="5af79-148">Fare clic su Aggiungi stringa.</span><span class="sxs-lookup"><span data-stu-id="5af79-148">Click Add String.</span></span>
33. <span data-ttu-id="5af79-149">Nel campo Nome digitare 'Conteggio righe'.</span><span class="sxs-lookup"><span data-stu-id="5af79-149">In the Name field, type 'Lines counting'.</span></span>
    * <span data-ttu-id="5af79-150">Conteggio righe</span><span class="sxs-lookup"><span data-stu-id="5af79-150">Lines counting</span></span>  
34. <span data-ttu-id="5af79-151">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="5af79-151">Click OK.</span></span>
35. <span data-ttu-id="5af79-152">Fare clic su Aggiungi stringa.</span><span class="sxs-lookup"><span data-stu-id="5af79-152">Click Add String.</span></span>
36. <span data-ttu-id="5af79-153">Nel campo Nome digitare 'Importo totale'.</span><span class="sxs-lookup"><span data-stu-id="5af79-153">In the Name field, type 'Total amount'.</span></span>
    * <span data-ttu-id="5af79-154">Importo totale</span><span class="sxs-lookup"><span data-stu-id="5af79-154">Total amount</span></span>  
37. <span data-ttu-id="5af79-155">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="5af79-155">Click OK.</span></span>
38. <span data-ttu-id="5af79-156">Fare clic sulla scheda Mapping.</span><span class="sxs-lookup"><span data-stu-id="5af79-156">Click the Mapping tab.</span></span>
39. <span data-ttu-id="5af79-157">Nella struttura selezionare '$BlocksList'.</span><span class="sxs-lookup"><span data-stu-id="5af79-157">In the tree, select '$BlocksList'.</span></span>
40. <span data-ttu-id="5af79-158">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="5af79-158">Click Bind.</span></span>
    * <span data-ttu-id="5af79-159">Creare una riga di riepilogo per ciascun blocco memorizzato.</span><span class="sxs-lookup"><span data-stu-id="5af79-159">Create a summary line for each memorized block.</span></span>  
41. <span data-ttu-id="5af79-160">Fare clic sulla scheda Formato.</span><span class="sxs-lookup"><span data-stu-id="5af79-160">Click the Format tab.</span></span>
42. <span data-ttu-id="5af79-161">Nella struttura selezionare 'Intrastat\Dati\Totali per blocchi\Codice blocco'.</span><span class="sxs-lookup"><span data-stu-id="5af79-161">In the tree, select 'Intrastat\Data\Totals by blocks\Block code'.</span></span>
43. <span data-ttu-id="5af79-162">Fare clic sulla scheda Mapping.</span><span class="sxs-lookup"><span data-stu-id="5af79-162">Click the Mapping tab.</span></span>
44. <span data-ttu-id="5af79-163">Fare clic su Modifica formula.</span><span class="sxs-lookup"><span data-stu-id="5af79-163">Click Edit formula.</span></span>
45. <span data-ttu-id="5af79-164">Nel campo Formula immettere '"Block id: " & '.</span><span class="sxs-lookup"><span data-stu-id="5af79-164">In the Formula field, enter '"Block id: " & '.</span></span>
    * <span data-ttu-id="5af79-165">"Block id: " &</span><span class="sxs-lookup"><span data-stu-id="5af79-165">"Block id: " &</span></span>  
46. <span data-ttu-id="5af79-166">Nella struttura espandere '$BlocksList'.</span><span class="sxs-lookup"><span data-stu-id="5af79-166">In the tree, expand '$BlocksList'.</span></span>
47. <span data-ttu-id="5af79-167">Nella struttura selezionare '$BlocksList\Value'.</span><span class="sxs-lookup"><span data-stu-id="5af79-167">In the tree, select '$BlocksList\Value'.</span></span>
48. <span data-ttu-id="5af79-168">Fare clic su Aggiungi origine dati.</span><span class="sxs-lookup"><span data-stu-id="5af79-168">Click Add data source.</span></span>
49. <span data-ttu-id="5af79-169">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="5af79-169">Click Save.</span></span>
50. <span data-ttu-id="5af79-170">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="5af79-170">Close the page.</span></span>
51. <span data-ttu-id="5af79-171">Fare clic sulla scheda Formato.</span><span class="sxs-lookup"><span data-stu-id="5af79-171">Click the Format tab.</span></span>
52. <span data-ttu-id="5af79-172">Nella struttura selezionare 'Intrastat\Dati\Totali per blocchi\Conteggio righe'.</span><span class="sxs-lookup"><span data-stu-id="5af79-172">In the tree, select 'Intrastat\Data\Totals by blocks\Lines counting'.</span></span>
53. <span data-ttu-id="5af79-173">Fare clic sulla scheda Mapping.</span><span class="sxs-lookup"><span data-stu-id="5af79-173">Click the Mapping tab.</span></span>
54. <span data-ttu-id="5af79-174">Fare clic su Modifica formula.</span><span class="sxs-lookup"><span data-stu-id="5af79-174">Click Edit formula.</span></span>
    * <span data-ttu-id="5af79-175">Creare l'output per il numero di righe per ciascun blocco presentato nel report.</span><span class="sxs-lookup"><span data-stu-id="5af79-175">Create output for the number of lines for each block presented in this report.</span></span>  
55. <span data-ttu-id="5af79-176">Nel campo Formula, immettere '"Numero di righe in questo blocco: " & '.</span><span class="sxs-lookup"><span data-stu-id="5af79-176">In the Formula field, enter '"Number of lines in this block: " & '.</span></span>
    * <span data-ttu-id="5af79-177">"Numero di righe in questo blocco: " &</span><span class="sxs-lookup"><span data-stu-id="5af79-177">"Number of lines in this block: " &</span></span>  
56. <span data-ttu-id="5af79-178">Nel campo Formula, immettere '"Numero di righe in questo blocco: " & TEXT('.</span><span class="sxs-lookup"><span data-stu-id="5af79-178">In the Formula field, enter '"Number of lines in this block: " & TEXT('.</span></span>
    * <span data-ttu-id="5af79-179">"Numero di righe in questo blocco: " & TEXT(</span><span class="sxs-lookup"><span data-stu-id="5af79-179">"Number of lines in this block: " & TEXT(</span></span>  
57. <span data-ttu-id="5af79-180">Nella struttura, selezionare 'Funzioni raccolta dati\COUNTIFS'.</span><span class="sxs-lookup"><span data-stu-id="5af79-180">In the tree, select 'Data collection functions\COUNTIFS'.</span></span>
58. <span data-ttu-id="5af79-181">Fare clic su Aggiungi funzione.</span><span class="sxs-lookup"><span data-stu-id="5af79-181">Click Add function.</span></span>
59. <span data-ttu-id="5af79-182">Fare clic su Aggiungi origine dati.</span><span class="sxs-lookup"><span data-stu-id="5af79-182">Click Add data source.</span></span>
60. <span data-ttu-id="5af79-183">Nel campo Formula, immettere '"Numero di righe in questo blocco: " & TEXT(COUNTIFS('$BlockName', '.</span><span class="sxs-lookup"><span data-stu-id="5af79-183">In the Formula field, enter '"Number of lines in this block: " & TEXT(COUNTIFS('$BlockName', '.</span></span>
    * <span data-ttu-id="5af79-184">"Numero di righe in questo blocco: " & TEXT(COUNTIFS('$BlockName',</span><span class="sxs-lookup"><span data-stu-id="5af79-184">"Number of lines in this block: " & TEXT(COUNTIFS('$BlockName',</span></span>  
61. <span data-ttu-id="5af79-185">Nella struttura espandere '$BlocksList'.</span><span class="sxs-lookup"><span data-stu-id="5af79-185">In the tree, expand '$BlocksList'.</span></span>
62. <span data-ttu-id="5af79-186">Nella struttura selezionare '$BlocksList\Value'.</span><span class="sxs-lookup"><span data-stu-id="5af79-186">In the tree, select '$BlocksList\Value'.</span></span>
63. <span data-ttu-id="5af79-187">Fare clic su Aggiungi origine dati.</span><span class="sxs-lookup"><span data-stu-id="5af79-187">Click Add data source.</span></span>
64. <span data-ttu-id="5af79-188">Nel campo Formula, immettere '"Numero di righe in questo blocco: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value, '.</span><span class="sxs-lookup"><span data-stu-id="5af79-188">In the Formula field, enter '"Number of lines in this block: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value, '.</span></span>
    * <span data-ttu-id="5af79-189">"Numero di righe in questo blocco: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value,</span><span class="sxs-lookup"><span data-stu-id="5af79-189">"Number of lines in this block: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value,</span></span>  
65. <span data-ttu-id="5af79-190">Nella struttura selezionare '$RecName'.</span><span class="sxs-lookup"><span data-stu-id="5af79-190">In the tree, select '$RecName'.</span></span>
66. <span data-ttu-id="5af79-191">Fare clic su Aggiungi origine dati.</span><span class="sxs-lookup"><span data-stu-id="5af79-191">Click Add data source.</span></span>
67. <span data-ttu-id="5af79-192">Nel campo Formula, immettere '"Numero di righe in questo blocco: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value, '$RecName', "\*"))'.</span><span class="sxs-lookup"><span data-stu-id="5af79-192">In the Formula field, enter '"Number of lines in this block: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value, '$RecName', "\*"))'.</span></span>
    * <span data-ttu-id="5af79-193">"Numero di righe in questo blocco: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value, '$RecName', "\*"))</span><span class="sxs-lookup"><span data-stu-id="5af79-193">"Number of lines in this block: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value, '$RecName', "\*"))</span></span>  
68. <span data-ttu-id="5af79-194">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="5af79-194">Click Save.</span></span>
69. <span data-ttu-id="5af79-195">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="5af79-195">Close the page.</span></span>
70. <span data-ttu-id="5af79-196">Fare clic sulla scheda Formato.</span><span class="sxs-lookup"><span data-stu-id="5af79-196">Click the Format tab.</span></span>
71. <span data-ttu-id="5af79-197">Nella struttura selezionare 'Intrastat\Dati\Totali per blocchi\Importo totale'.</span><span class="sxs-lookup"><span data-stu-id="5af79-197">In the tree, select 'Intrastat\Data\Totals by blocks\Total amount'.</span></span>
72. <span data-ttu-id="5af79-198">Fare clic sulla scheda Mapping.</span><span class="sxs-lookup"><span data-stu-id="5af79-198">Click the Mapping tab.</span></span>
73. <span data-ttu-id="5af79-199">Fare clic su Modifica formula.</span><span class="sxs-lookup"><span data-stu-id="5af79-199">Click Edit formula.</span></span>
    * <span data-ttu-id="5af79-200">Creare l'output che costituirà il totale dell'importo fatturato per ciascun blocco presentato nel report.</span><span class="sxs-lookup"><span data-stu-id="5af79-200">Create output that will be the total of the invoiced amount for each block presented in this report.</span></span>  
74. <span data-ttu-id="5af79-201">Nel campo Formula immettere '"Somma dell'importo fatturato: " & TEXT(SUMIFS('$InvName', '$BlockName', '$BlocksList'.Value, '$RecName', "\*"))'.</span><span class="sxs-lookup"><span data-stu-id="5af79-201">In the Formula field, enter '"Sum of invoiced amount: " & TEXT(SUMIFS('$InvName', '$BlockName', '$BlocksList'.Value, '$RecName', "\*"))'.</span></span>
    * <span data-ttu-id="5af79-202">"Somma dell'importo fatturato: " & TEXT(SUMIFS('$InvName', '$BlockName', '$BlocksList'.Value, '$RecName', "\*"))</span><span class="sxs-lookup"><span data-stu-id="5af79-202">"Sum of invoiced amount: " & TEXT(SUMIFS('$InvName', '$BlockName', '$BlocksList'.Value, '$RecName', "\*"))</span></span>  
75. <span data-ttu-id="5af79-203">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="5af79-203">Click Save.</span></span>
76. <span data-ttu-id="5af79-204">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="5af79-204">Close the page.</span></span>
77. <span data-ttu-id="5af79-205">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="5af79-205">Click Save.</span></span>
78. <span data-ttu-id="5af79-206">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="5af79-206">Close the page.</span></span>



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]