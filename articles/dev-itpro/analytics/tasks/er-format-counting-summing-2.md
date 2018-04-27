--- 
title: Configurare i calcoli per eseguire il conteggio e la somma
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
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: d41ce101c0b038627e2baf6b5eac2410095af7ce
ms.contentlocale: it-it
ms.lasthandoff: 04/13/2018

---
# <a name="configure-computations-to-do-counting-and-summing"></a><span data-ttu-id="d325b-103">Configurare i calcoli per eseguire il conteggio e la somma</span><span class="sxs-lookup"><span data-stu-id="d325b-103">Configure computations to do counting and summing</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="d325b-104">I passaggi seguenti descrivono come un utente con ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può configurare un formato per la creazione di report elettronici in modo che esegua calcoli e somme in base ai dati dell'output di testo già generato.</span><span class="sxs-lookup"><span data-stu-id="d325b-104">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) format to do counting and summing based on data of the already generated text output.</span></span> <span data-ttu-id="d325b-105">Questi passaggi possono essere eseguiti in qualsiasi società.</span><span class="sxs-lookup"><span data-stu-id="d325b-105">These steps can be performed in any company.</span></span>

<span data-ttu-id="d325b-106">Per effettuare queste operazioni, è innanzitutto necessario completare i passaggi nella procedura  'ER Configurare il formato per eseguire conteggi e somme (parte 1: creare il formato)'.</span><span class="sxs-lookup"><span data-stu-id="d325b-106">To complete these steps, you must first complete the steps in the “ER Configure format to do counting and summing (Part 1: Create format)” procedure.</span></span>

<span data-ttu-id="d325b-107">Questa procedura è per una funzionalità che è stata aggiunta in Dynamics 365 for Operations versione 1611.</span><span class="sxs-lookup"><span data-stu-id="d325b-107">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="create-a-format-configuration-to-add-counting-and-summing-details"></a><span data-ttu-id="d325b-108">Creare una configurazione di formato per aggiungere dettagli di conteggio e somma</span><span class="sxs-lookup"><span data-stu-id="d325b-108">Create a format configuration to add counting and summing details</span></span>
1. <span data-ttu-id="d325b-109">Andare ad Amministrazione organizzazione > Aree di lavoro > Creazione di report elettronici.</span><span class="sxs-lookup"><span data-stu-id="d325b-109">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="d325b-110">Fare clic su Configurazioni report.</span><span class="sxs-lookup"><span data-stu-id="d325b-110">Click Reporting configurations.</span></span>
3. <span data-ttu-id="d325b-111">Nella struttura espandere 'Modello Intrastat'.</span><span class="sxs-lookup"><span data-stu-id="d325b-111">In the tree, expand 'Intrastat model'.</span></span>
4. <span data-ttu-id="d325b-112">Nella struttura, selezionare 'Modello Intrastat\Intrastat (DE)'.</span><span class="sxs-lookup"><span data-stu-id="d325b-112">In the tree, select 'Intrastat model\Intrastat (DE)'.</span></span>
    * <span data-ttu-id="d325b-113">Si supponga di dover personalizzare il formato fornito da Microsoft aggiungendo righe con dettagli di riepilogo alla fine del report Intrastat.</span><span class="sxs-lookup"><span data-stu-id="d325b-113">Assume that you need to customize the format provided by Microsoft by adding lines with summary details at the end of the Intrastat report.</span></span> <span data-ttu-id="d325b-114">A tale scopo si deve derivare la propria istanza della configurazione Intrastat dall'istanza di Microsoft per apportare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="d325b-114">You need to do that by deriving our own instance of the Intrastat configuration from the Microsoft instance to make modifications.</span></span>  
5. <span data-ttu-id="d325b-115">Fare clic su Crea configurazione per aprire la finestra di dialogo a discesa .</span><span class="sxs-lookup"><span data-stu-id="d325b-115">Click Create configuration to open the drop dialog.</span></span>
6. <span data-ttu-id="d325b-116">Nel campo Nuovo, immettere 'Deriva da nome: Intrastat (DE), Microsoft'.</span><span class="sxs-lookup"><span data-stu-id="d325b-116">In the New field, enter 'Derive from Name: Intrastat (DE), Microsoft'.</span></span>
7. <span data-ttu-id="d325b-117">Nel campo Nome, digitare 'Intrastat (DE) con conteggi e somme'.</span><span class="sxs-lookup"><span data-stu-id="d325b-117">In the Name field, type 'Intrastat (DE) with counting & summing'.</span></span>
8. <span data-ttu-id="d325b-118">Fare clic su Crea configurazione.</span><span class="sxs-lookup"><span data-stu-id="d325b-118">Click Create configuration.</span></span>

## <a name="configure-this-report-to-do-counting-and-summation-based-on-output-details"></a><span data-ttu-id="d325b-119">Configurare questo report per eseguire il conteggio e la sommatoria in base ai dettagli di output</span><span class="sxs-lookup"><span data-stu-id="d325b-119">Configure this report to do counting and summation based on output details</span></span>
1. <span data-ttu-id="d325b-120">Fare clic su Progettazione.</span><span class="sxs-lookup"><span data-stu-id="d325b-120">Click Designer.</span></span>
2. <span data-ttu-id="d325b-121">Selezionare Sì nel campo Raccogli dettagli di output.</span><span class="sxs-lookup"><span data-stu-id="d325b-121">Select Yes in the Collect output details field.</span></span>
    * <span data-ttu-id="d325b-122">Il flag attiverà in fase di esecuzione il processo di raccolta dei dettagli di output  per la generazione del file Intrastat.</span><span class="sxs-lookup"><span data-stu-id="d325b-122">This flag will activate at run-time the process of collecting output details for generating the Intrastat file.</span></span>  
    * <span data-ttu-id="d325b-123">È necessario eseguire il conteggio per le diverse direzioni Intrastat, quindi aggiungere un'enumerazione modello dedicata all'elenco delle origini dati di questa configurazione di formato.</span><span class="sxs-lookup"><span data-stu-id="d325b-123">You need to do counting for different Intrastat directions, so add a dedicated model enumeration to the data sources’ list of this format configuration.</span></span>  
3. <span data-ttu-id="d325b-124">Fare clic sulla scheda Mapping.</span><span class="sxs-lookup"><span data-stu-id="d325b-124">Click the Mapping tab.</span></span>
4. <span data-ttu-id="d325b-125">Fare clic su Aggiungi radice per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="d325b-125">Click Add root to open the drop dialog.</span></span>
5. <span data-ttu-id="d325b-126">Nella struttura selezionare 'Modello dati\Enumerazione'.</span><span class="sxs-lookup"><span data-stu-id="d325b-126">In the tree, select 'Data model\Enumeration '.</span></span>
6. <span data-ttu-id="d325b-127">Digitare 'Direction' nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="d325b-127">In the Name field, type 'Direction'.</span></span>
7. <span data-ttu-id="d325b-128">Nel campo Enumerazione modello immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="d325b-128">In the Model enumeration field, enter or select a value.</span></span>
    * <span data-ttu-id="d325b-129">Selezionare il valore Direction.</span><span class="sxs-lookup"><span data-stu-id="d325b-129">Select the value Direction.</span></span>  
8. <span data-ttu-id="d325b-130">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="d325b-130">Click OK.</span></span>
9. <span data-ttu-id="d325b-131">Fare clic su Aggiungi radice per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="d325b-131">Click Add root to open the drop dialog.</span></span>
10. <span data-ttu-id="d325b-132">Nella struttura selezionare "Funzioni\Campo calcolato".</span><span class="sxs-lookup"><span data-stu-id="d325b-132">In the tree, select 'Functions\Calculated field'.</span></span>
11. <span data-ttu-id="d325b-133">Digitare '$BlockName' nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="d325b-133">In the Name field, type '$BlockName'.</span></span>
12. <span data-ttu-id="d325b-134">Fare clic su Modifica formula.</span><span class="sxs-lookup"><span data-stu-id="d325b-134">Click Edit formula.</span></span>
13. <span data-ttu-id="d325b-135">Nel campo Formula immettere'"block"'.</span><span class="sxs-lookup"><span data-stu-id="d325b-135">In the Formula field, enter '"block"'.</span></span>
14. <span data-ttu-id="d325b-136">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="d325b-136">Click Save.</span></span>
15. <span data-ttu-id="d325b-137">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="d325b-137">Close the page.</span></span>
16. <span data-ttu-id="d325b-138">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="d325b-138">Click OK.</span></span>
17. <span data-ttu-id="d325b-139">Fare clic su Aggiungi radice per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="d325b-139">Click Add root to open the drop dialog.</span></span>
18. <span data-ttu-id="d325b-140">Nella struttura selezionare "Funzioni\Campo calcolato".</span><span class="sxs-lookup"><span data-stu-id="d325b-140">In the tree, select 'Functions\Calculated field'.</span></span>
19. <span data-ttu-id="d325b-141">Nel campo Nome digitare '$RecName'.</span><span class="sxs-lookup"><span data-stu-id="d325b-141">In the Name field, type '$RecName'.</span></span>
20. <span data-ttu-id="d325b-142">Fare clic su Modifica formula.</span><span class="sxs-lookup"><span data-stu-id="d325b-142">Click Edit formula.</span></span>
21. <span data-ttu-id="d325b-143">Nel campo Formula immettere '"record"'.</span><span class="sxs-lookup"><span data-stu-id="d325b-143">In the Formula field, enter '"record"'.</span></span>
22. <span data-ttu-id="d325b-144">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="d325b-144">Click Save.</span></span>
23. <span data-ttu-id="d325b-145">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="d325b-145">Close the page.</span></span>
24. <span data-ttu-id="d325b-146">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="d325b-146">Click OK.</span></span>
25. <span data-ttu-id="d325b-147">Fare clic su Aggiungi radice per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="d325b-147">Click Add root to open the drop dialog.</span></span>
26. <span data-ttu-id="d325b-148">Nella struttura selezionare "Funzioni\Campo calcolato".</span><span class="sxs-lookup"><span data-stu-id="d325b-148">In the tree, select 'Functions\Calculated field'.</span></span>
27. <span data-ttu-id="d325b-149">Nel campo Nome digitare '$InvName'.</span><span class="sxs-lookup"><span data-stu-id="d325b-149">In the Name field, type '$InvName'.</span></span>
28. <span data-ttu-id="d325b-150">Fare clic su Modifica formula.</span><span class="sxs-lookup"><span data-stu-id="d325b-150">Click Edit formula.</span></span>
29. <span data-ttu-id="d325b-151">Nel campo Formula immettere '"InvoicedAmountEUR"'.</span><span class="sxs-lookup"><span data-stu-id="d325b-151">In the Formula field, enter '"InvoicedAmountEUR"'.</span></span>
30. <span data-ttu-id="d325b-152">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="d325b-152">Click Save.</span></span>
31. <span data-ttu-id="d325b-153">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="d325b-153">Close the page.</span></span>
32. <span data-ttu-id="d325b-154">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="d325b-154">Click OK.</span></span>
33. <span data-ttu-id="d325b-155">Nella struttura selezionare 'Intrastat\Dati'.</span><span class="sxs-lookup"><span data-stu-id="d325b-155">In the tree, select 'Intrastat\Data'.</span></span>
34. <span data-ttu-id="d325b-156">Fare clic sul pulsante Modifica per il campo 'Nome chiave dati raccolti'</span><span class="sxs-lookup"><span data-stu-id="d325b-156">Click Edit button for the ‘Collected data key name’ field</span></span>
35. <span data-ttu-id="d325b-157">Fare clic su Aggiungi origine dati.</span><span class="sxs-lookup"><span data-stu-id="d325b-157">Click Add data source.</span></span>
    * <span data-ttu-id="d325b-158">$BlockName</span><span class="sxs-lookup"><span data-stu-id="d325b-158">$BlockName</span></span>  
36. <span data-ttu-id="d325b-159">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="d325b-159">Click Save.</span></span>
37. <span data-ttu-id="d325b-160">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="d325b-160">Close the page.</span></span>
38. <span data-ttu-id="d325b-161">Fare clic sul pulsante Modifica per il campo Valore chiave dati raccolti.</span><span class="sxs-lookup"><span data-stu-id="d325b-161">Click the Edit button for the Collected data key value field.</span></span>
39. <span data-ttu-id="d325b-162">Nel campo Formula immettere 'IF(Intrastat.CommodityRecord.Direction=Direction.Import, "Import", "Export")'.</span><span class="sxs-lookup"><span data-stu-id="d325b-162">In the Formula field, enter 'IF(Intrastat.CommodityRecord.Direction=Direction.Import, "Import", "Export")'.</span></span>
    * <span data-ttu-id="d325b-163">IF(Intrastat.CommodityRecord.Direction=Direction.Import, "Import", "Export")</span><span class="sxs-lookup"><span data-stu-id="d325b-163">IF(Intrastat.CommodityRecord.Direction=Direction.Import, "Import", "Export")</span></span>  
40. <span data-ttu-id="d325b-164">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="d325b-164">Click Save.</span></span>
41. <span data-ttu-id="d325b-165">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="d325b-165">Close the page.</span></span>
    * <span data-ttu-id="d325b-166">Contare le righe della sequenza.</span><span class="sxs-lookup"><span data-stu-id="d325b-166">Count the lines of this sequence.</span></span> <span data-ttu-id="d325b-167">I risultati verranno utilizzati con il nome 'block' separatamente per le diverse direzioni.</span><span class="sxs-lookup"><span data-stu-id="d325b-167">The results will be used with the name “block” separately for different directions.</span></span> <span data-ttu-id="d325b-168">Il valore 'Import' verrà utilizzato per tutte le transazioni Intrastat di arrivi.</span><span class="sxs-lookup"><span data-stu-id="d325b-168">Value “Import” will be used for any arrivals Intrastat transactions.</span></span> <span data-ttu-id="d325b-169">Il valore 'Export' verrà utilizzato per tutte le transazioni Intrastat di spedizioni.</span><span class="sxs-lookup"><span data-stu-id="d325b-169">The value “Export” will be used for any Intrastat dispatches transactions.</span></span> <span data-ttu-id="d325b-170">Considerare questo come un foglio di calcolo di Excel virtuale.</span><span class="sxs-lookup"><span data-stu-id="d325b-170">Consider this to be a virtual Excel spreadsheet.</span></span> <span data-ttu-id="d325b-171">Per ciascuna transazione una riga in cui la prima colonna 'block' viene compilata, di conseguenza, con i valori 'Import' ed 'Export'.</span><span class="sxs-lookup"><span data-stu-id="d325b-171">For each transaction a row where the first column “block” is filled with the values “Import” and “Export” accordingly.</span></span>  
42. <span data-ttu-id="d325b-172">Nella struttura espandere 'Intrastat\Dati: Sequenza'.</span><span class="sxs-lookup"><span data-stu-id="d325b-172">In the tree, expand 'Intrastat\Data: Sequence'.</span></span>
43. <span data-ttu-id="d325b-173">Nella struttura selezionare 'Intrastat\Dati: Sequenza\Arrivi?'.</span><span class="sxs-lookup"><span data-stu-id="d325b-173">In the tree, select 'Intrastat\Data: Sequence\Arrivals?'.</span></span>
44. <span data-ttu-id="d325b-174">Fare clic sul pulsante Modifica per il campo 'Nome chiave dati raccolti'.</span><span class="sxs-lookup"><span data-stu-id="d325b-174">Click Edit button for the ‘Collected data key name’ field.</span></span>
    * <span data-ttu-id="d325b-175">Contare le righe della sequenza.</span><span class="sxs-lookup"><span data-stu-id="d325b-175">Count the lines of this sequence.</span></span> <span data-ttu-id="d325b-176">I risultati verranno memorizzati utilizzando il nome 'record'.</span><span class="sxs-lookup"><span data-stu-id="d325b-176">The results will be memorized using the name “record”.</span></span>  
45. <span data-ttu-id="d325b-177">Nella struttura selezionare '$RecName'.</span><span class="sxs-lookup"><span data-stu-id="d325b-177">In the tree, select '$RecName'.</span></span>
46. <span data-ttu-id="d325b-178">Fare clic su Aggiungi origine dati.</span><span class="sxs-lookup"><span data-stu-id="d325b-178">Click Add data source.</span></span>
47. <span data-ttu-id="d325b-179">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="d325b-179">Click Save.</span></span>
48. <span data-ttu-id="d325b-180">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="d325b-180">Close the page.</span></span>
49. <span data-ttu-id="d325b-181">Fare clic sul pulsante Modifica per il campo Valore chiave dati raccolti.</span><span class="sxs-lookup"><span data-stu-id="d325b-181">Click Edit button for the ‘Collected data key value’ field</span></span>
50. <span data-ttu-id="d325b-182">Nel campo Formula, immettere  'Intrastat.CommodityRecord.CommodityCode'.</span><span class="sxs-lookup"><span data-stu-id="d325b-182">In the Formula field, enter 'Intrastat.CommodityRecord.CommodityCode'.</span></span>
51. <span data-ttu-id="d325b-183">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="d325b-183">Click Save.</span></span>
52. <span data-ttu-id="d325b-184">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="d325b-184">Close the page.</span></span>
    * <span data-ttu-id="d325b-185">Contare le righe della sequenza.</span><span class="sxs-lookup"><span data-stu-id="d325b-185">Count the lines of this sequence.</span></span> <span data-ttu-id="d325b-186">I risultati verranno utilizzati con il nome 'record' separatamente per i diversi codici voce doganale.</span><span class="sxs-lookup"><span data-stu-id="d325b-186">The results will be used with the name “record” separately for different commodity codes.</span></span> <span data-ttu-id="d325b-187">Considerare questo come un foglio di calcolo di Excel virtuale.</span><span class="sxs-lookup"><span data-stu-id="d325b-187">Consider this to be a virtual Excel spreadsheet.</span></span> <span data-ttu-id="d325b-188">Per ciascuna transazione una riga in cui la prima colonna 'block' viene compilata, di conseguenza, con i valori 'Import' ed 'Export' e il secondo blocco 'record' è compilato con il valore del codice di voce doganale.</span><span class="sxs-lookup"><span data-stu-id="d325b-188">For each transaction a row where the first column “block” is filled with the values “Import” and “Export” accordingly and the second block “record” is filled with the commodity code value.</span></span>  
53. <span data-ttu-id="d325b-189">Nella struttura espandere 'Intrastat\Dati: Sequenza\Spedizioni?'.</span><span class="sxs-lookup"><span data-stu-id="d325b-189">In the tree, select 'Intrastat\Data: Sequence\Dispatches?'.</span></span>
54. <span data-ttu-id="d325b-190">Fare clic sul pulsante Modifica per il campo 'Nome chiave dati raccolti'</span><span class="sxs-lookup"><span data-stu-id="d325b-190">Click Edit button for the ‘Collected data key name’ field</span></span>
55. <span data-ttu-id="d325b-191">Nella struttura selezionare '$RecName'.</span><span class="sxs-lookup"><span data-stu-id="d325b-191">In the tree, select '$RecName'.</span></span>
56. <span data-ttu-id="d325b-192">Fare clic su Aggiungi origine dati.</span><span class="sxs-lookup"><span data-stu-id="d325b-192">Click Add data source.</span></span>
57. <span data-ttu-id="d325b-193">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="d325b-193">Click Save.</span></span>
58. <span data-ttu-id="d325b-194">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="d325b-194">Close the page.</span></span>
59. <span data-ttu-id="d325b-195">Fare clic sul pulsante Modifica per il campo Valore chiave dati raccolti.</span><span class="sxs-lookup"><span data-stu-id="d325b-195">Click the Edit button for the ‘Collected data key value’ field.</span></span>
60. <span data-ttu-id="d325b-196">Nel campo Formula, immettere  'Intrastat.CommodityRecord.CommodityCode'.</span><span class="sxs-lookup"><span data-stu-id="d325b-196">In the Formula field, enter 'Intrastat.CommodityRecord.CommodityCode'.</span></span>
61. <span data-ttu-id="d325b-197">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="d325b-197">Click Save.</span></span>
62. <span data-ttu-id="d325b-198">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="d325b-198">Close the page.</span></span>
63. <span data-ttu-id="d325b-199">Nella struttura espandere 'Intrastat\Dati: Sequenza\Spedizioni: Sequenza?'.</span><span class="sxs-lookup"><span data-stu-id="d325b-199">In the tree, expand 'Intrastat\Data: Sequence\Dispatches: Sequence?'.</span></span>
64. <span data-ttu-id="d325b-200">Nella struttura espandere 'Intrastat\Dati: Sequenza\Spedizioni: Sequenza?\Record =  Intrastat.CommodityRecord'.</span><span class="sxs-lookup"><span data-stu-id="d325b-200">In the tree, expand 'Intrastat\Data: Sequence\Dispatches: Sequence?\Record =  Intrastat.CommodityRecord'.</span></span>
65. <span data-ttu-id="d325b-201">Fare clic sulla scheda Formato.</span><span class="sxs-lookup"><span data-stu-id="d325b-201">Click the Format tab.</span></span>
66. <span data-ttu-id="d325b-202">Nella struttura selezionare 'Intrastat\Dati\Spedizioni\Record\Importo fattura EUR'.</span><span class="sxs-lookup"><span data-stu-id="d325b-202">In the tree, select 'Intrastat\Data\Dispatches\Record\Invoice amount EUR'.</span></span>
67. <span data-ttu-id="d325b-203">Fare clic sulla scheda Mapping.</span><span class="sxs-lookup"><span data-stu-id="d325b-203">Click the Mapping tab.</span></span>
68. <span data-ttu-id="d325b-204">Fare clic sul pulsante Modifica per il campo 'Nome chiave dati raccolti'.</span><span class="sxs-lookup"><span data-stu-id="d325b-204">Click the Edit button for the ‘Collected data key name’ field.</span></span>
69. <span data-ttu-id="d325b-205">Nella struttura selezionare '$InvName'.</span><span class="sxs-lookup"><span data-stu-id="d325b-205">In the tree, select '$InvName'.</span></span>
70. <span data-ttu-id="d325b-206">Fare clic su Aggiungi origine dati.</span><span class="sxs-lookup"><span data-stu-id="d325b-206">Click Add data source.</span></span>
71. <span data-ttu-id="d325b-207">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="d325b-207">Click Save.</span></span>
72. <span data-ttu-id="d325b-208">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="d325b-208">Close the page.</span></span>
    * <span data-ttu-id="d325b-209">Riepilogare i valori dell'importo fatturato per le righe della sequenza.</span><span class="sxs-lookup"><span data-stu-id="d325b-209">Summarize the invoiced amount values for lines of this sequence.</span></span> <span data-ttu-id="d325b-210">I risultati verranno utilizzati con il nome 'InvoicedAmountEUR' separatamente per le diverse direzioni e i diversi codici voce doganale Intrastat.</span><span class="sxs-lookup"><span data-stu-id="d325b-210">The results will be used with the name “InvoicedAmountEUR” separately for different Intrastat directions and commodity codes.</span></span> <span data-ttu-id="d325b-211">Considerare questa come una creazione virtuale nel foglio di calcolo di Excel.</span><span class="sxs-lookup"><span data-stu-id="d325b-211">Consider this to be a virtual creation in Excel spreadsheet.</span></span> <span data-ttu-id="d325b-212">Per ciascuna transazione una riga in cui la prima colonna 'block' viene compilata, di conseguenza, con i valori 'Import' ed 'Export'.</span><span class="sxs-lookup"><span data-stu-id="d325b-212">For each transaction a row where the first column “block” is filled with the values “Import” and “Export” accordingly.</span></span> <span data-ttu-id="d325b-213">Il secondo blocco 'record' viene compilato con il valore del codice voce doganale e la terza colonna 'InvoicedAmountEUR' viene compilata con il valore dell'importo della fattura.</span><span class="sxs-lookup"><span data-stu-id="d325b-213">The second block “record” is filled with the commodity code value, and the third column “InvoicedAmountEUR” is filled with the invoice amount value.</span></span>  
73. <span data-ttu-id="d325b-214">Nella struttura espandere 'Intrastat\Dati\Arrivi?'.</span><span class="sxs-lookup"><span data-stu-id="d325b-214">In the tree, expand 'Intrastat\Data\Arrivals?'.</span></span>
74. <span data-ttu-id="d325b-215">Nella struttura espandere 'Intrastat\Dati\Arrivi?\Record =  Intrastat.CommodityRecord'.</span><span class="sxs-lookup"><span data-stu-id="d325b-215">In the tree, expand 'Intrastat\Data\Arrivals?\Record =  Intrastat.CommodityRecord'.</span></span>
75. <span data-ttu-id="d325b-216">Fare clic sulla scheda Formato.</span><span class="sxs-lookup"><span data-stu-id="d325b-216">Click the Format tab.</span></span>
76. <span data-ttu-id="d325b-217">Nella struttura selezionare 'Intrastat\Dati\Arrivi\Record\Importo fattura EUR'.</span><span class="sxs-lookup"><span data-stu-id="d325b-217">In the tree, select 'Intrastat\Data\Arrivals\Record\Invoice amount EUR'.</span></span>
77. <span data-ttu-id="d325b-218">Fare clic sulla scheda Mapping.</span><span class="sxs-lookup"><span data-stu-id="d325b-218">Click the Mapping tab.</span></span>
78. <span data-ttu-id="d325b-219">Fare clic sul pulsante Modifica per il campo 'Nome chiave dati raccolti'.</span><span class="sxs-lookup"><span data-stu-id="d325b-219">Click the Edit button for the ‘Collected data key name’ field.</span></span>
79. <span data-ttu-id="d325b-220">Nella struttura selezionare '$InvName'.</span><span class="sxs-lookup"><span data-stu-id="d325b-220">In the tree, select '$InvName'.</span></span>
80. <span data-ttu-id="d325b-221">Fare clic su Aggiungi origine dati.</span><span class="sxs-lookup"><span data-stu-id="d325b-221">Click Add data source.</span></span>
81. <span data-ttu-id="d325b-222">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="d325b-222">Click Save.</span></span>
82. <span data-ttu-id="d325b-223">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="d325b-223">Close the page.</span></span>
83. <span data-ttu-id="d325b-224">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="d325b-224">Click Save.</span></span>
84. <span data-ttu-id="d325b-225">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="d325b-225">Close the page.</span></span>


