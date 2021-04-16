---
title: 'ER Configurare il formato per eseguire il conteggio e la sommatoria (Parte 4: eseguire il formato)'
description: Questo argomento descrive come configurare un formato di report elettronico per eseguire il conteggio e la somma in base ai dati dell'output di testo già generato. (Parte 4)
author: NickSelin
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, IntrastatParameters, Intrastat, InventItemIdLookupSimple, IntrastatCommodityLookup, ERFormatMappingRunLogTable, DocuView
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5792505de78aad458bd8745630915cf58f05f73f
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5748975"
---
# <a name="er-configure-format-to-do-counting-and-summing-part-4---run-format"></a><span data-ttu-id="14195-104">ER Configurare il formato per eseguire il conteggio e la sommatoria (Parte 4: eseguire il formato)</span><span class="sxs-lookup"><span data-stu-id="14195-104">ER Configure format to do counting and summing (Part 4 - Run format)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="14195-105">I passaggi seguenti descrivono come un utente con ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può configurare un formato per la creazione di report elettronici in modo che esegua calcoli e somme in base ai dati dell'output di testo già generato.</span><span class="sxs-lookup"><span data-stu-id="14195-105">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) format to do counting and summing based on data of the already generated text output.</span></span> <span data-ttu-id="14195-106">Queste operazioni possono essere eseguite nella società DEMF.</span><span class="sxs-lookup"><span data-stu-id="14195-106">These steps can be performed in the DEMF company.</span></span>

<span data-ttu-id="14195-107">Per effettuare queste operazioni, è innanzitutto necessario completare i passaggi nella "procedura ER Configurare il formato per eseguire conteggi e somme (parte 3: usare i calcoli per creare l'output)".</span><span class="sxs-lookup"><span data-stu-id="14195-107">To complete these steps, you must first complete the steps in the "ER Configure format to do counting and summing (Part 3: Use computations to make the output)" procedure.</span></span>

<span data-ttu-id="14195-108">Questa procedura è per una funzionalità che è stata aggiunta in Dynamics 365 for Operations versione 1611.</span><span class="sxs-lookup"><span data-stu-id="14195-108">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="test-this-configuration-for-generation-of-the-intrastat-reports"></a><span data-ttu-id="14195-109">Verificare la configurazione per la generazione di report Intrastat</span><span class="sxs-lookup"><span data-stu-id="14195-109">Test this configuration for generation of the Intrastat reports</span></span>
1. <span data-ttu-id="14195-110">Andare ad Amministrazione organizzazione > Aree di lavoro > Creazione di report elettronici.</span><span class="sxs-lookup"><span data-stu-id="14195-110">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="14195-111">Fare clic su Configurazioni report.</span><span class="sxs-lookup"><span data-stu-id="14195-111">Click Reporting configurations.</span></span>
3. <span data-ttu-id="14195-112">Nella struttura espandere 'Modello Intrastat'.</span><span class="sxs-lookup"><span data-stu-id="14195-112">In the tree, expand 'Intrastat model'.</span></span>
4. <span data-ttu-id="14195-113">Nella struttura, espandere 'Modello Intrastat\Intrastat (DE)'.</span><span class="sxs-lookup"><span data-stu-id="14195-113">In the tree, expand 'Intrastat model\Intrastat (DE)'.</span></span>
5. <span data-ttu-id="14195-114">Nella struttura selezionare 'Modello Intrastat\Intrastat (DE)\Intrastat (DE) con conteggio e somma'.</span><span class="sxs-lookup"><span data-stu-id="14195-114">In the tree, select 'Intrastat model\Intrastat (DE)\Intrastat (DE) with counting & summing'.</span></span>
6. <span data-ttu-id="14195-115">Nel riquadro azioni, fare clic su Configurazioni.</span><span class="sxs-lookup"><span data-stu-id="14195-115">On the Action Pane, click Configurations.</span></span>
7. <span data-ttu-id="14195-116">Fare clic su Parametri utente.</span><span class="sxs-lookup"><span data-stu-id="14195-116">Click User parameters.</span></span>
8. <span data-ttu-id="14195-117">Selezionare Sì nel campo Esegui impostazioni.</span><span class="sxs-lookup"><span data-stu-id="14195-117">Select Yes in the Run settings field.</span></span>
9. <span data-ttu-id="14195-118">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="14195-118">Click OK.</span></span>
10. <span data-ttu-id="14195-119">Fare clic su Modifica.</span><span class="sxs-lookup"><span data-stu-id="14195-119">Click Edit.</span></span>
11. <span data-ttu-id="14195-120">Selezionare Sì nel campo Esegui bozza.</span><span class="sxs-lookup"><span data-stu-id="14195-120">Select Yes in the Run Draft field.</span></span>
12. <span data-ttu-id="14195-121">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="14195-121">Click Save.</span></span>
13. <span data-ttu-id="14195-122">Passare a Imposta > Impostazione > Commercio estero > Parametri per il commercio estero.</span><span class="sxs-lookup"><span data-stu-id="14195-122">Go to Tax > Setup > Foreign trade > Foreign trade parameters.</span></span>
14. <span data-ttu-id="14195-123">Espandere la sezione Creazione di report elettronici.</span><span class="sxs-lookup"><span data-stu-id="14195-123">Expand the Electronic reporting section.</span></span>
15. <span data-ttu-id="14195-124">Selezionare la configurazione "Intrastat (DE) con conteggio e somma".</span><span class="sxs-lookup"><span data-stu-id="14195-124">Select the "Intrastat (DE) with counting & summing" configuration.</span></span>
16. <span data-ttu-id="14195-125">Selezionare la configurazione "Intrastat (DE) con conteggio e somma".</span><span class="sxs-lookup"><span data-stu-id="14195-125">Select the "Intrastat (DE) with counting & summing" configuration.</span></span>
17. <span data-ttu-id="14195-126">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="14195-126">Click Save.</span></span>
18. <span data-ttu-id="14195-127">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="14195-127">Close the page.</span></span>
19. <span data-ttu-id="14195-128">Passare a Imposta > Dichiarazioni > Commercio estero > Intrastat.</span><span class="sxs-lookup"><span data-stu-id="14195-128">Go to Tax > Declarations > Foreign trade > Intrastat.</span></span>
20. <span data-ttu-id="14195-129">Fare clic su Output.</span><span class="sxs-lookup"><span data-stu-id="14195-129">Click Output.</span></span>
21. <span data-ttu-id="14195-130">Fare clic su Report.</span><span class="sxs-lookup"><span data-stu-id="14195-130">Click Report.</span></span>
    * <span data-ttu-id="14195-131">Eseguire il processo di generazione report Intrastat.</span><span class="sxs-lookup"><span data-stu-id="14195-131">Run the Intrastat report generation process.</span></span>  
22. <span data-ttu-id="14195-132">Nel campo Data iniziale impostare la data su "01-01-2000".</span><span class="sxs-lookup"><span data-stu-id="14195-132">In the From date field, set the date to '2000-01-01'.</span></span>
    * <span data-ttu-id="14195-133">Definire le date di inizio e fine del periodo di reporting che includono le transazioni esistenti nel modulo.</span><span class="sxs-lookup"><span data-stu-id="14195-133">Define start and end dates for the reporting period that include the existing on the form transactions.</span></span>  
23. <span data-ttu-id="14195-134">Nel campo Data finale impostare la data su "31-12-2022".</span><span class="sxs-lookup"><span data-stu-id="14195-134">In the To date field, set the date to '2022-12-31'.</span></span>
    * <span data-ttu-id="14195-135">Definire le date di inizio e fine del periodo di reporting che includono le transazioni esistenti nel modulo.</span><span class="sxs-lookup"><span data-stu-id="14195-135">Define start and end dates for the reporting period that include the existing on the form transactions.</span></span>  
24. <span data-ttu-id="14195-136">Selezionare 'Arrivi' nel campo Direzione.</span><span class="sxs-lookup"><span data-stu-id="14195-136">In the Direction field, select 'Arrivals'.</span></span>
25. <span data-ttu-id="14195-137">Selezionare Sì nel campo Genera file.</span><span class="sxs-lookup"><span data-stu-id="14195-137">Select Yes in the Generate file field.</span></span>
26. <span data-ttu-id="14195-138">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="14195-138">Click OK.</span></span>
    * <span data-ttu-id="14195-139">Esaminare l'output creato con le righe di riepilogo alla fine.</span><span class="sxs-lookup"><span data-stu-id="14195-139">Review the created output with the summary lines in the end.</span></span>  
27. <span data-ttu-id="14195-140">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="14195-140">Click New.</span></span>
28. <span data-ttu-id="14195-141">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="14195-141">In the list, mark the selected row.</span></span>
29. <span data-ttu-id="14195-142">Selezionare 'Spedizioni' nel campo Direzione.</span><span class="sxs-lookup"><span data-stu-id="14195-142">In the Direction field, select 'Dispatches'.</span></span>
30. <span data-ttu-id="14195-143">Nel campo Numero di articoli immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="14195-143">In the Item number field, enter or select a value.</span></span>
31. <span data-ttu-id="14195-144">Nel campo Voce doganale immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="14195-144">In the Commodity field, enter or select a value.</span></span>
32. <span data-ttu-id="14195-145">Impostare Peso su '10'.</span><span class="sxs-lookup"><span data-stu-id="14195-145">Set Weight to '10'.</span></span>
33. <span data-ttu-id="14195-146">Impostare Importo fattura su '10000'.</span><span class="sxs-lookup"><span data-stu-id="14195-146">Set Invoice amount to '10000'.</span></span>
34. <span data-ttu-id="14195-147">Impostare Importo statistico su '10000'.</span><span class="sxs-lookup"><span data-stu-id="14195-147">Set Statistical amount to '10000'.</span></span>
35. <span data-ttu-id="14195-148">Fare clic su Output.</span><span class="sxs-lookup"><span data-stu-id="14195-148">Click Output.</span></span>
36. <span data-ttu-id="14195-149">Fare clic su Report.</span><span class="sxs-lookup"><span data-stu-id="14195-149">Click Report.</span></span>
37. <span data-ttu-id="14195-150">Selezionare 'Spedizioni' nel campo Direzione.</span><span class="sxs-lookup"><span data-stu-id="14195-150">In the Direction field, select 'Dispatches'.</span></span>
38. <span data-ttu-id="14195-151">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="14195-151">Click OK.</span></span>
    * <span data-ttu-id="14195-152">Esaminare l'output creato con le righe di riepilogo alla fine.</span><span class="sxs-lookup"><span data-stu-id="14195-152">Review the created output with the summary lines in the end.</span></span> <span data-ttu-id="14195-153">Tenere presente che è stato modificato rispetto alla prima esecuzione.</span><span class="sxs-lookup"><span data-stu-id="14195-153">Note that it has been changed in comparison to the first run.</span></span>  

## <a name="run-this-configuration-in-debug-mode-to-review-the-collected-counting--summing-data"></a><span data-ttu-id="14195-154">Eseguire la configurazione in modalità di debug per esaminare i dati di conteggio e somma raccolti</span><span class="sxs-lookup"><span data-stu-id="14195-154">Run this configuration in debug mode to review the collected counting & summing data</span></span>
1. <span data-ttu-id="14195-155">Passare a Amministrazione organizzazione > Reporting elettronico > Configurazioni.</span><span class="sxs-lookup"><span data-stu-id="14195-155">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="14195-156">Nella struttura espandere 'Modello Intrastat'.</span><span class="sxs-lookup"><span data-stu-id="14195-156">In the tree, expand 'Intrastat model'.</span></span>
3. <span data-ttu-id="14195-157">Nella struttura, espandere 'Modello Intrastat\Intrastat (DE)'.</span><span class="sxs-lookup"><span data-stu-id="14195-157">In the tree, expand 'Intrastat model\Intrastat (DE)'.</span></span>
4. <span data-ttu-id="14195-158">Nella struttura selezionare 'Modello Intrastat\Intrastat (DE)\Intrastat (DE) con conteggio e somma'.</span><span class="sxs-lookup"><span data-stu-id="14195-158">In the tree, select 'Intrastat model\Intrastat (DE)\Intrastat (DE) with counting & summing'.</span></span>
5. <span data-ttu-id="14195-159">Nel riquadro azioni, fare clic su Configurazioni.</span><span class="sxs-lookup"><span data-stu-id="14195-159">On the Action Pane, click Configurations.</span></span>
6. <span data-ttu-id="14195-160">Fare clic su Parametri utente.</span><span class="sxs-lookup"><span data-stu-id="14195-160">Click User parameters.</span></span>
7. <span data-ttu-id="14195-161">Selezionare Sì nel campo Esegui in modalità di debug.</span><span class="sxs-lookup"><span data-stu-id="14195-161">Select Yes in the Run in debug mode field.</span></span>
8. <span data-ttu-id="14195-162">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="14195-162">Click OK.</span></span>
9. <span data-ttu-id="14195-163">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="14195-163">Close the page.</span></span>
10. <span data-ttu-id="14195-164">Passare a Imposta > Dichiarazioni > Commercio estero > Intrastat.</span><span class="sxs-lookup"><span data-stu-id="14195-164">Go to Tax > Declarations > Foreign trade > Intrastat.</span></span>
11. <span data-ttu-id="14195-165">Fare clic su Output.</span><span class="sxs-lookup"><span data-stu-id="14195-165">Click Output.</span></span>
12. <span data-ttu-id="14195-166">Fare clic su Report.</span><span class="sxs-lookup"><span data-stu-id="14195-166">Click Report.</span></span>
13. <span data-ttu-id="14195-167">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="14195-167">Click OK.</span></span>
14. <span data-ttu-id="14195-168">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="14195-168">Close the page.</span></span>
15. <span data-ttu-id="14195-169">Passare a Amministrazione organizzazione > Reporting elettronico > Configurazioni.</span><span class="sxs-lookup"><span data-stu-id="14195-169">Go to Organization administration > Electronic reporting > Configurations.</span></span>
16. <span data-ttu-id="14195-170">Nella struttura espandere 'Modello Intrastat'.</span><span class="sxs-lookup"><span data-stu-id="14195-170">In the tree, expand 'Intrastat model'.</span></span>
17. <span data-ttu-id="14195-171">Nella struttura, espandere 'Modello Intrastat\Intrastat (DE)'.</span><span class="sxs-lookup"><span data-stu-id="14195-171">In the tree, expand 'Intrastat model\Intrastat (DE)'.</span></span>
18. <span data-ttu-id="14195-172">Nella struttura selezionare 'Modello Intrastat\Intrastat (DE)\Intrastat (DE) con conteggio e somma'.</span><span class="sxs-lookup"><span data-stu-id="14195-172">In the tree, select 'Intrastat model\Intrastat (DE)\Intrastat (DE) with counting & summing'.</span></span>
19. <span data-ttu-id="14195-173">Fare clic su Registri debug.</span><span class="sxs-lookup"><span data-stu-id="14195-173">Click Debug logs.</span></span>
    * <span data-ttu-id="14195-174">Tenere presente che un record del registro di debug è stato creato per il processo di esecuzione della configurazione selezionata.</span><span class="sxs-lookup"><span data-stu-id="14195-174">Note that a debug log record has been created for the execution process of the selected configuration.</span></span>  
20. <span data-ttu-id="14195-175">Fare clic su Allega.</span><span class="sxs-lookup"><span data-stu-id="14195-175">Click Attach.</span></span>
21. <span data-ttu-id="14195-176">Fare clic su Apri.</span><span class="sxs-lookup"><span data-stu-id="14195-176">Click Open.</span></span>
    * <span data-ttu-id="14195-177">Esaminare il file XML creato che contiene i dettagli di conteggio e somma che sono stati raccolti durante l'esecuzione della configurazione selezionata.</span><span class="sxs-lookup"><span data-stu-id="14195-177">Review the created XML file that contains counting and summing details that were collected during the execution of the selected configuration.</span></span>  



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]