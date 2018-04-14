--- 
title: Utilizzare una configurazione del mapping di modello per calcoli aggregati a livello di database (ER)
description: Questa procedura fornisce informazioni per progettare una nuova configurazione di mapping di modello (ER) per la creazione di report elettronici e usare le funzioni ER incorporate per i calcoli aggregati efficienti.
author: NickSelin
manager: AnnBe
ms.date: 12/12/2017
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
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 4b6533d1ba538bdc115a865f94212b84781e506e
ms.contentlocale: it-it
ms.lasthandoff: 04/13/2018

---
# <a name="use-a-model-mapping-configuration-for-aggregate-calculations-at-the-database-leveler"></a><span data-ttu-id="c776e-103">Utilizzare una configurazione del mapping di modello per calcoli aggregati a livello di database (ER)</span><span class="sxs-lookup"><span data-stu-id="c776e-103">Use a model mapping configuration for aggregate calculations at the database level(ER)</span></span> 

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="c776e-104">Questa procedura fornisce informazioni per progettare una nuova configurazione di mapping di modello (ER) per la creazione di report elettronici e usare le funzioni ER incorporate per i calcoli aggregati efficienti.</span><span class="sxs-lookup"><span data-stu-id="c776e-104">This procedure provides information about how to design a new Electronic reporting (ER) model mapping configuration and use built-in ER functions for efficient aggregate calculations.</span></span> <span data-ttu-id="c776e-105">In questa procedura verrà creata una configurazione per la società di esempio Litware, Inc.</span><span class="sxs-lookup"><span data-stu-id="c776e-105">In this procedure you will create a configuration for the sample company, Litware, Inc.</span></span> 

<span data-ttu-id="c776e-106">Questa procedura viene creata per utenti con il ruolo di amministratore di sistema o di sviluppatore di report elettronici.</span><span class="sxs-lookup"><span data-stu-id="c776e-106">This procedure is created for users with the assigned role of System administrator or Electronic reporting developer.</span></span> <span data-ttu-id="c776e-107">Tali passaggi possono essere completati mediante un set di dati.</span><span class="sxs-lookup"><span data-stu-id="c776e-107">These steps can be completed using any dataset.</span></span>

 <span data-ttu-id="c776e-108">Per effettuare queste operazioni, è innanzitutto necessario completare i passaggi della procedura "ER migliora l'efficienza dei calcoli di aggregazione eseguendoli a livello di database (Parte 1: Preparazione le configurazioni)".</span><span class="sxs-lookup"><span data-stu-id="c776e-108">To complete these steps, you must first complete the steps in the procedure, “ER improves the efficiency of aggregate calculations by performing them on database level (Part 1: Prepare configurations).”</span></span>

1. <span data-ttu-id="c776e-109">Passare a Amministrazione organizzazione > Reporting elettronico > Configurazioni.</span><span class="sxs-lookup"><span data-stu-id="c776e-109">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="c776e-110">Nella struttura espandere 'Modello Intrastat'.</span><span class="sxs-lookup"><span data-stu-id="c776e-110">In the tree, expand 'Intrastat model'.</span></span>
3. <span data-ttu-id="c776e-111">Nella struttura selezionare 'Modello Intrastat\Mapping di esempio Intrastat'.</span><span class="sxs-lookup"><span data-stu-id="c776e-111">In the tree, select 'Intrastat model\Intrastat sample mapping'.</span></span>
4. <span data-ttu-id="c776e-112">Fare clic su Progettazione.</span><span class="sxs-lookup"><span data-stu-id="c776e-112">Click Designer.</span></span>
5. <span data-ttu-id="c776e-113">Fare clic su Progettazione.</span><span class="sxs-lookup"><span data-stu-id="c776e-113">Click Designer.</span></span>
6. <span data-ttu-id="c776e-114">Nella struttura selezionare "Dynamics 365 for Operations\Table records".</span><span class="sxs-lookup"><span data-stu-id="c776e-114">In the tree, select 'Dynamics 365 for Operations\Table records'.</span></span>
7. <span data-ttu-id="c776e-115">Fare clic su Aggiungi radice.</span><span class="sxs-lookup"><span data-stu-id="c776e-115">Click Add root.</span></span>
    * <span data-ttu-id="c776e-116">Aggiungere una nuova origine dati che rappresenta i record da raggruppare.</span><span class="sxs-lookup"><span data-stu-id="c776e-116">Add a new data source representing records you want to group.</span></span>  
8. <span data-ttu-id="c776e-117">Nel campo Nome digitare "Transazioni".</span><span class="sxs-lookup"><span data-stu-id="c776e-117">In the Name field, type 'Transactions'.</span></span>
    * <span data-ttu-id="c776e-118">Transazioni</span><span class="sxs-lookup"><span data-stu-id="c776e-118">Transactions</span></span>  
9. <span data-ttu-id="c776e-119">Nel campo Tabella digitare "Intrastat".</span><span class="sxs-lookup"><span data-stu-id="c776e-119">In the Table field, type 'Intrastat'.</span></span>
    * <span data-ttu-id="c776e-120">Intrastat</span><span class="sxs-lookup"><span data-stu-id="c776e-120">Intrastat</span></span>  
10. <span data-ttu-id="c776e-121">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="c776e-121">Click OK.</span></span>
11. <span data-ttu-id="c776e-122">Nella struttura selezionare "Funzioni\Raggruppa per".</span><span class="sxs-lookup"><span data-stu-id="c776e-122">In the tree, select 'Functions\Group by'.</span></span>
    * <span data-ttu-id="c776e-123">Questo tipo di origine dei dati viene utilizzato per immettere una nuova origine dati in fase di esecuzione nei record di gruppo e per calcolare le aggregazioni richieste.</span><span class="sxs-lookup"><span data-stu-id="c776e-123">This data source type is used to introduce a new data source at run-time to group records and to calculate required aggregations.</span></span>  
12. <span data-ttu-id="c776e-124">Fare clic su Aggiungi radice.</span><span class="sxs-lookup"><span data-stu-id="c776e-124">Click Add root.</span></span>
13. <span data-ttu-id="c776e-125">Digitare 'TransactionsGroups' nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="c776e-125">In the Name field, type 'TransactionsGroups'.</span></span>
    * <span data-ttu-id="c776e-126">TransactionsGroups</span><span class="sxs-lookup"><span data-stu-id="c776e-126">TransactionsGroups</span></span>  
14. <span data-ttu-id="c776e-127">Fare clic su Modifica gruppo per.</span><span class="sxs-lookup"><span data-stu-id="c776e-127">Click Edit group by.</span></span>
15. <span data-ttu-id="c776e-128">Nella struttura selezionare "Transazioni".</span><span class="sxs-lookup"><span data-stu-id="c776e-128">In the tree, select 'Transactions'.</span></span>
    * <span data-ttu-id="c776e-129">Selezionare l'origine dati aggiunta di tipo "Elenco di record" che rappresenta i record da raggruppare.</span><span class="sxs-lookup"><span data-stu-id="c776e-129">Select the added data source of the ‘Record list’ type that represents the records that you want to group.</span></span>  
16. <span data-ttu-id="c776e-130">Fare clic su Aggiungi campo a.</span><span class="sxs-lookup"><span data-stu-id="c776e-130">Click Add field to.</span></span>
17. <span data-ttu-id="c776e-131">Fare clic su Informazioni da raggruppare.</span><span class="sxs-lookup"><span data-stu-id="c776e-131">Click What to group.</span></span>
18. <span data-ttu-id="c776e-132">Nella struttura espandere "Transazioni".</span><span class="sxs-lookup"><span data-stu-id="c776e-132">In the tree, expand 'Transactions'.</span></span>
19. <span data-ttu-id="c776e-133">Nella struttura, selezionare "Transazioni\Direzione".</span><span class="sxs-lookup"><span data-stu-id="c776e-133">In the tree, select 'Transactions\Direction'.</span></span>
20. <span data-ttu-id="c776e-134">Fare clic su Aggiungi campo a.</span><span class="sxs-lookup"><span data-stu-id="c776e-134">Click Add field to.</span></span>
21. <span data-ttu-id="c776e-135">Fare clic su Campi raggruppati.</span><span class="sxs-lookup"><span data-stu-id="c776e-135">Click Grouped fields.</span></span>
    * <span data-ttu-id="c776e-136">Selezionare il campo per specificare il livello di raggruppamento.</span><span class="sxs-lookup"><span data-stu-id="c776e-136">Select the field to specify the grouping level.</span></span> <span data-ttu-id="c776e-137">In base a questa selezione, l'origine dati restituisce in fase di esecuzione tutti i gruppi di transazioni quanti sono i codici di direzione soddisfatti nella tabella Intrastat.</span><span class="sxs-lookup"><span data-stu-id="c776e-137">Based on this selection, the data source will return at run-time as many groups of transactions as there are direction codes that will be met in the Intrastat table.</span></span>  
22. <span data-ttu-id="c776e-138">Nella struttura selezionare "Transazioni\Importo fattura(AmountMST)".</span><span class="sxs-lookup"><span data-stu-id="c776e-138">In the tree, select 'Transactions\Invoice amount(AmountMST)'.</span></span>
    * <span data-ttu-id="c776e-139">Selezionare il campo per specificare l'origine per il calcolo di aggregazione.</span><span class="sxs-lookup"><span data-stu-id="c776e-139">Select the field to specify the source for aggregation calculation.</span></span>  
23. <span data-ttu-id="c776e-140">Fare clic su Aggiungi campo a.</span><span class="sxs-lookup"><span data-stu-id="c776e-140">Click Add field to.</span></span>
24. <span data-ttu-id="c776e-141">Fare clic su Campi di aggregazione.</span><span class="sxs-lookup"><span data-stu-id="c776e-141">Click Aggregation fields.</span></span>
25. <span data-ttu-id="c776e-142">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="c776e-142">In the list, mark the selected row.</span></span>
26. <span data-ttu-id="c776e-143">Selezionare "Somma" nel campo Metodo.</span><span class="sxs-lookup"><span data-stu-id="c776e-143">In the Method field, select 'Sum'.</span></span>
    * <span data-ttu-id="c776e-144">Selezionare il tipo di aggregazione.</span><span class="sxs-lookup"><span data-stu-id="c776e-144">Select the aggregation type.</span></span>  
27. <span data-ttu-id="c776e-145">Digitare 'SumOfAmountMST' nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="c776e-145">In the Name field, type 'SumOfAmountMST'.</span></span>
    * <span data-ttu-id="c776e-146">Specificare il nome dell'aggregazione nell'origine dati configurata.</span><span class="sxs-lookup"><span data-stu-id="c776e-146">Specify the name of this aggregation in the configured data source.</span></span>  
28. <span data-ttu-id="c776e-147">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="c776e-147">Click Save.</span></span>
    * <span data-ttu-id="c776e-148">Tenere presente che il campo "Esecuzione in" indica che il raggruppamento verrà eseguito in fase di esecuzione nel database SQL.</span><span class="sxs-lookup"><span data-stu-id="c776e-148">Note that the ‘Execution at’ field indicates that this grouping will be performed at run-time in the SQL database.</span></span>  
29. <span data-ttu-id="c776e-149">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="c776e-149">Close the page.</span></span>
30. <span data-ttu-id="c776e-150">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="c776e-150">Click OK.</span></span>
31. <span data-ttu-id="c776e-151">Nella struttura espandere 'Totali'.</span><span class="sxs-lookup"><span data-stu-id="c776e-151">In the tree, expand 'Totals'.</span></span>
32. <span data-ttu-id="c776e-152">Nella struttura espandere 'TransactionsGroups'.</span><span class="sxs-lookup"><span data-stu-id="c776e-152">In the tree, expand 'TransactionsGroups'.</span></span>
33. <span data-ttu-id="c776e-153">Nella struttura espandere 'TransactionsGroups\aggregated'.</span><span class="sxs-lookup"><span data-stu-id="c776e-153">In the tree, expand 'TransactionsGroups\aggregated'.</span></span>
34. <span data-ttu-id="c776e-154">Nella struttura selezionare 'TransactionsGroups\aggregated\SumOfAmountMST'.</span><span class="sxs-lookup"><span data-stu-id="c776e-154">In the tree, select 'TransactionsGroups\aggregated\SumOfAmountMST'.</span></span>
35. <span data-ttu-id="c776e-155">Nella struttura selezionare 'Totals\Total invoice value(TotalInvoiceValue) = IF(ISEMPTY(IntrastatTotals), 0.0, IntrastatTotals.aggregated.'$AmountMSTRounded')'.</span><span class="sxs-lookup"><span data-stu-id="c776e-155">In the tree, select 'Totals\Total invoice value(TotalInvoiceValue) = IF(ISEMPTY(IntrastatTotals), 0.0, IntrastatTotals.aggregated.'$AmountMSTRounded')'.</span></span>
36. <span data-ttu-id="c776e-156">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="c776e-156">Click Bind.</span></span>
    * <span data-ttu-id="c776e-157">In base a questa impostazione, l'origine dati calcolerà la somma dei valori del campo "AmountMST" per ogni gruppo di transazioni.</span><span class="sxs-lookup"><span data-stu-id="c776e-157">Based on this setting, this data source will calculate the sum of values of the ‘AmountMST’ field for each groups of transactions.</span></span> <span data-ttu-id="c776e-158">Questo calcolo di aggregazione sarà disponibile come elemento TransactionsGroups.aggregated.TotalAmount.</span><span class="sxs-lookup"><span data-stu-id="c776e-158">This aggregation calculation will be available as TransactionsGroups.aggregated.TotalAmount item.</span></span>  
37. <span data-ttu-id="c776e-159">Nella struttura espandere 'TransactionsGroups'.</span><span class="sxs-lookup"><span data-stu-id="c776e-159">In the tree, expand 'TransactionsGroups'.</span></span>
38. <span data-ttu-id="c776e-160">Nella struttura selezionare 'TransactionsGroups'.</span><span class="sxs-lookup"><span data-stu-id="c776e-160">In the tree, select 'TransactionsGroups'.</span></span>
39. <span data-ttu-id="c776e-161">Fare clic su Modifica.</span><span class="sxs-lookup"><span data-stu-id="c776e-161">Click Edit.</span></span>
40. <span data-ttu-id="c776e-162">Fare clic su Modifica gruppo per.</span><span class="sxs-lookup"><span data-stu-id="c776e-162">Click Edit group by.</span></span>
41. <span data-ttu-id="c776e-163">Nella struttura espandere "Transazioni".</span><span class="sxs-lookup"><span data-stu-id="c776e-163">In the tree, expand 'Transactions'.</span></span>
42. <span data-ttu-id="c776e-164">Nella struttura selezionare "Transazioni\Importo fattura(AmountMST)".</span><span class="sxs-lookup"><span data-stu-id="c776e-164">In the tree, select 'Transactions\Invoice amount(AmountMST)'.</span></span>
43. <span data-ttu-id="c776e-165">Fare clic su Aggiungi campo a.</span><span class="sxs-lookup"><span data-stu-id="c776e-165">Click Add field to.</span></span>
44. <span data-ttu-id="c776e-166">Fare clic su Campi di aggregazione.</span><span class="sxs-lookup"><span data-stu-id="c776e-166">Click Aggregation fields.</span></span>
45. <span data-ttu-id="c776e-167">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="c776e-167">In the list, mark the selected row.</span></span>
46. <span data-ttu-id="c776e-168">Selezionare "Max" nel campo Metodo.</span><span class="sxs-lookup"><span data-stu-id="c776e-168">In the Method field, select 'Max'.</span></span>
47. <span data-ttu-id="c776e-169">Digitare 'MaxOfAmountMST' nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="c776e-169">In the Name field, type 'MaxOfAmountMST'.</span></span>
48. <span data-ttu-id="c776e-170">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="c776e-170">Click Save.</span></span>
    * <span data-ttu-id="c776e-171">Attualmente, l'esecuzione delle origini dati GROUPBY può essere convertita a livello del database SQL con alcune limitazioni.</span><span class="sxs-lookup"><span data-stu-id="c776e-171">Currently, the execution of GROUPBY data sources can be translated to the SQL database level with some limitations.</span></span> <span data-ttu-id="c776e-172">La conversione può essere effettuata per le origini dati di tipo "Elenco record" o per le origini dati rappresentate come espressione utilizzando la funzione FILTER.</span><span class="sxs-lookup"><span data-stu-id="c776e-172">Translation can be done for either data sources of the ‘Record list’ type or data sources represented as an expression using the FILTER function.</span></span> <span data-ttu-id="c776e-173">Può inoltre essere eseguita quando l'unica aggregazione viene configurata per un singolo campo dei record del raggruppamento.</span><span class="sxs-lookup"><span data-stu-id="c776e-173">It can also be done when the only one aggregation is configured for a single field of the grouping records.</span></span>  
    * <span data-ttu-id="c776e-174">Tenere presente che anche se più di un'aggregazione è stata configurata per il campo AmountMST, il campo "Esecuzione in" indica che il raggruppamento verrà eseguito in fase di esecuzione nel database SQL.</span><span class="sxs-lookup"><span data-stu-id="c776e-174">Note that even though more than one aggregation was configured for the AmountMST field, the ‘Execution at’ field still indicates that this grouping will be performed at run-time in the SQL database.</span></span> <span data-ttu-id="c776e-175">Ciò accade perché solo un'aggregazione viene limitata all'elemento del modello dati e verrà utilizzata in fase di esecuzione per estrarre dati dall'origine dati.</span><span class="sxs-lookup"><span data-stu-id="c776e-175">This is because only one aggregation is bound to the data model item and will be used at run-time to pull data from this data source.</span></span>  
49. <span data-ttu-id="c776e-176">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="c776e-176">Close the page.</span></span>
50. <span data-ttu-id="c776e-177">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="c776e-177">Click OK.</span></span>
51. <span data-ttu-id="c776e-178">Nella struttura espandere 'TransactionsGroups'.</span><span class="sxs-lookup"><span data-stu-id="c776e-178">In the tree, expand 'TransactionsGroups'.</span></span>
52. <span data-ttu-id="c776e-179">Nella struttura espandere 'TransactionsGroups\aggregated'.</span><span class="sxs-lookup"><span data-stu-id="c776e-179">In the tree, expand 'TransactionsGroups\aggregated'.</span></span>
53. <span data-ttu-id="c776e-180">Nella struttura selezionare 'TransactionsGroups\aggregated\MaxOfAmountMST'.</span><span class="sxs-lookup"><span data-stu-id="c776e-180">In the tree, select 'TransactionsGroups\aggregated\MaxOfAmountMST'.</span></span>
54. <span data-ttu-id="c776e-181">Nella struttura selezionare 'Totals\Total statistical value(TotalStatisticalValue) = IF(ISEMPTY(IntrastatTotals), 0.0, IntrastatTotals.aggregated.'$StatisticalValueRounded')'.</span><span class="sxs-lookup"><span data-stu-id="c776e-181">In the tree, select 'Totals\Total statistical value(TotalStatisticalValue) = IF(ISEMPTY(IntrastatTotals), 0.0, IntrastatTotals.aggregated.'$StatisticalValueRounded')'.</span></span>
55. <span data-ttu-id="c776e-182">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="c776e-182">Click Bind.</span></span>
56. <span data-ttu-id="c776e-183">Nella struttura espandere 'TransactionsGroups'.</span><span class="sxs-lookup"><span data-stu-id="c776e-183">In the tree, expand 'TransactionsGroups'.</span></span>
57. <span data-ttu-id="c776e-184">Nella struttura selezionare 'TransactionsGroups'.</span><span class="sxs-lookup"><span data-stu-id="c776e-184">In the tree, select 'TransactionsGroups'.</span></span>
58. <span data-ttu-id="c776e-185">Fare clic su Modifica.</span><span class="sxs-lookup"><span data-stu-id="c776e-185">Click Edit.</span></span>
59. <span data-ttu-id="c776e-186">Fare clic su Modifica gruppo per.</span><span class="sxs-lookup"><span data-stu-id="c776e-186">Click Edit group by.</span></span>
    * <span data-ttu-id="c776e-187">Tenere presente che il campo "Esecuzione in" indica che il raggruppamento verrà eseguito in fase di esecuzione nel memoria in quanto entrambe le aggregazioni dello stesso campo sono associate agli elementi del modello dati.</span><span class="sxs-lookup"><span data-stu-id="c776e-187">Note that the ‘Execution at’ field indicates that this grouping will be performed at run-time in memory because both aggregations of the same field are bound to the data model items.</span></span>   
60. <span data-ttu-id="c776e-188">Nell'elenco contrassegnare tutte le righe o rimuoverne il contrassegno.</span><span class="sxs-lookup"><span data-stu-id="c776e-188">In the list, mark or unmark all rows.</span></span>
61. <span data-ttu-id="c776e-189">Fare clic su Elimina.</span><span class="sxs-lookup"><span data-stu-id="c776e-189">Click Delete.</span></span>
62. <span data-ttu-id="c776e-190">Fare clic su Sì.</span><span class="sxs-lookup"><span data-stu-id="c776e-190">Click Yes.</span></span>
63. <span data-ttu-id="c776e-191">Fare clic su Elimina.</span><span class="sxs-lookup"><span data-stu-id="c776e-191">Click Delete.</span></span>
64. <span data-ttu-id="c776e-192">Fare clic su Sì.</span><span class="sxs-lookup"><span data-stu-id="c776e-192">Click Yes.</span></span>
65. <span data-ttu-id="c776e-193">Fare clic su Aggiungi campo a.</span><span class="sxs-lookup"><span data-stu-id="c776e-193">Click Add field to.</span></span>
66. <span data-ttu-id="c776e-194">Fare clic su Informazioni da raggruppare.</span><span class="sxs-lookup"><span data-stu-id="c776e-194">Click What to group.</span></span>
67. <span data-ttu-id="c776e-195">Nella struttura espandere 'Record voce doganale(Intrastat)'.</span><span class="sxs-lookup"><span data-stu-id="c776e-195">In the tree, expand 'Commodity record(Intrastat)'.</span></span>
68. <span data-ttu-id="c776e-196">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="c776e-196">Click Save.</span></span>
    * <span data-ttu-id="c776e-197">Tenere presente che il campo "Esecuzione in" indica che il raggruppamento verrà eseguito in fase di esecuzione in memoria anche se non sono presenti aggregazioni definite e l'origine dati selezionata di tipo "Record di tabella" fa riferimento alla stessa tabella "Intrastat".</span><span class="sxs-lookup"><span data-stu-id="c776e-197">Note that the ‘Execution at’ field indicates that this grouping will be performed at run-time in memory even though there are no aggregations defined and the selected data source of ‘Table records’ type refers to the same ‘Intrastat’ table.</span></span> <span data-ttu-id="c776e-198">Ciò accade perché l'origine dati contiene alcuni campi calcolati che non possono essere convertiti a livello del database SQL.</span><span class="sxs-lookup"><span data-stu-id="c776e-198">This is because the data source contains some calculated fields which can’t yet be translated to the SQL database level.</span></span>  


