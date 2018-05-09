--- 
title: Eseguire il formato per il conteggio e la somma
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
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 689514f0614aeb4a8bfad39459267005d0aaf6ef
ms.contentlocale: it-it
ms.lasthandoff: 05/08/2018

---
# <a name="run-the-format-to-do-counting-and-summing"></a><span data-ttu-id="cc0f0-103">Eseguire il formato per il conteggio e la somma</span><span class="sxs-lookup"><span data-stu-id="cc0f0-103">Run the format to do counting and summing</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="cc0f0-104">I passaggi seguenti descrivono come un utente con ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può configurare un formato per la creazione di report elettronici in modo che esegua calcoli e somme in base ai dati dell'output di testo già generato.</span><span class="sxs-lookup"><span data-stu-id="cc0f0-104">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) format to do counting and summing based on data of the already generated text output.</span></span> <span data-ttu-id="cc0f0-105">Queste operazioni possono essere eseguite nella società DEMF.</span><span class="sxs-lookup"><span data-stu-id="cc0f0-105">These steps can be performed in the DEMF company.</span></span>

<span data-ttu-id="cc0f0-106">Per effettuare queste operazioni, è innanzitutto necessario completare i passaggi nella procedura 'ER Configurare il formato per eseguire conteggi e somme (parte 3: usare i calcoli per creare l'output)'.</span><span class="sxs-lookup"><span data-stu-id="cc0f0-106">To complete these steps, you must first complete the steps in the “ER Configure format to do counting and summing (Part 3: Use computations to make the output)” procedure.</span></span>

<span data-ttu-id="cc0f0-107">Questa procedura è per una funzionalità che è stata aggiunta in Dynamics 365 for Operations versione 1611.</span><span class="sxs-lookup"><span data-stu-id="cc0f0-107">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="test-this-configuration-for-generation-of-the-intrastat-reports"></a><span data-ttu-id="cc0f0-108">Verificare la configurazione per la generazione di report Intrastat</span><span class="sxs-lookup"><span data-stu-id="cc0f0-108">Test this configuration for generation of the Intrastat reports</span></span>
1. <span data-ttu-id="cc0f0-109">Andare ad Amministrazione organizzazione > Aree di lavoro > Creazione di report elettronici.</span><span class="sxs-lookup"><span data-stu-id="cc0f0-109">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="cc0f0-110">Fare clic su Configurazioni report.</span><span class="sxs-lookup"><span data-stu-id="cc0f0-110">Click Reporting configurations.</span></span>
3. <span data-ttu-id="cc0f0-111">Nella struttura espandere 'Modello Intrastat'.</span><span class="sxs-lookup"><span data-stu-id="cc0f0-111">In the tree, expand 'Intrastat model'.</span></span>
4. <span data-ttu-id="cc0f0-112">Nella struttura, espandere 'Modello Intrastat\Intrastat (DE)'.</span><span class="sxs-lookup"><span data-stu-id="cc0f0-112">In the tree, expand 'Intrastat model\Intrastat (DE)'.</span></span>
5. <span data-ttu-id="cc0f0-113">Nella struttura selezionare 'Modello Intrastat\Intrastat (DE)\Intrastat (DE) con conteggio e somma'.</span><span class="sxs-lookup"><span data-stu-id="cc0f0-113">In the tree, select 'Intrastat model\Intrastat (DE)\Intrastat (DE) with counting & summing'.</span></span>
6. <span data-ttu-id="cc0f0-114">Nel riquadro azioni, fare clic su Configurazioni.</span><span class="sxs-lookup"><span data-stu-id="cc0f0-114">On the Action Pane, click Configurations.</span></span>
7. <span data-ttu-id="cc0f0-115">Fare clic su Parametri utente.</span><span class="sxs-lookup"><span data-stu-id="cc0f0-115">Click User parameters.</span></span>
8. <span data-ttu-id="cc0f0-116">Selezionare Sì nel campo Esegui impostazioni.</span><span class="sxs-lookup"><span data-stu-id="cc0f0-116">Select Yes in the Run settings field.</span></span>
9. <span data-ttu-id="cc0f0-117">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="cc0f0-117">Click OK.</span></span>
10. <span data-ttu-id="cc0f0-118">Fare clic su Modifica.</span><span class="sxs-lookup"><span data-stu-id="cc0f0-118">Click Edit.</span></span>
11. <span data-ttu-id="cc0f0-119">Selezionare Sì nel campo Esegui bozza.</span><span class="sxs-lookup"><span data-stu-id="cc0f0-119">Select Yes in the Run Draft field.</span></span>
12. <span data-ttu-id="cc0f0-120">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="cc0f0-120">Click Save.</span></span>
13. <span data-ttu-id="cc0f0-121">Passare a Imposta > Impostazione > Commercio estero > Parametri per il commercio estero.</span><span class="sxs-lookup"><span data-stu-id="cc0f0-121">Go to Tax > Setup > Foreign trade > Foreign trade parameters.</span></span>
14. <span data-ttu-id="cc0f0-122">Espandere la sezione Creazione di report elettronici.</span><span class="sxs-lookup"><span data-stu-id="cc0f0-122">Expand the Electronic reporting section.</span></span>
15. <span data-ttu-id="cc0f0-123">Selezionare la configurazione "Intrastat (DE) con conteggio e somma".</span><span class="sxs-lookup"><span data-stu-id="cc0f0-123">Select the “Intrastat (DE) with counting & summing” configuration.</span></span>
16. <span data-ttu-id="cc0f0-124">Selezionare la configurazione "Intrastat (DE) con conteggio e somma".</span><span class="sxs-lookup"><span data-stu-id="cc0f0-124">Select the “Intrastat (DE) with counting & summing” configuration.</span></span>
17. <span data-ttu-id="cc0f0-125">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="cc0f0-125">Click Save.</span></span>
18. <span data-ttu-id="cc0f0-126">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="cc0f0-126">Close the page.</span></span>
19. <span data-ttu-id="cc0f0-127">Passare a Imposta > Dichiarazioni > Commercio estero > Intrastat.</span><span class="sxs-lookup"><span data-stu-id="cc0f0-127">Go to Tax > Declarations > Foreign trade > Intrastat.</span></span>
20. <span data-ttu-id="cc0f0-128">Fare clic su Output.</span><span class="sxs-lookup"><span data-stu-id="cc0f0-128">Click Output.</span></span>
21. <span data-ttu-id="cc0f0-129">Fare clic su Report.</span><span class="sxs-lookup"><span data-stu-id="cc0f0-129">Click Report.</span></span>
    * <span data-ttu-id="cc0f0-130">Eseguire il processo di generazione report Intrastat.</span><span class="sxs-lookup"><span data-stu-id="cc0f0-130">Run the Intrastat report generation process.</span></span>  
22. <span data-ttu-id="cc0f0-131">Nel campo Data iniziale impostare la data su "01-01-2000".</span><span class="sxs-lookup"><span data-stu-id="cc0f0-131">In the From date field, set the date to '2000-01-01'.</span></span>
    * <span data-ttu-id="cc0f0-132">Definire le date di inizio e fine del periodo di reporting che includono le transazioni esistenti nel modulo.</span><span class="sxs-lookup"><span data-stu-id="cc0f0-132">Define start and end dates for the reporting period that include the existing on the form transactions.</span></span>  
23. <span data-ttu-id="cc0f0-133">Nel campo Data finale impostare la data su "31-12-2022".</span><span class="sxs-lookup"><span data-stu-id="cc0f0-133">In the To date field, set the date to '2022-12-31'.</span></span>
    * <span data-ttu-id="cc0f0-134">Definire le date di inizio e fine del periodo di reporting che includono le transazioni esistenti nel modulo.</span><span class="sxs-lookup"><span data-stu-id="cc0f0-134">Define start and end dates for the reporting period that include the existing on the form transactions.</span></span>  
24. <span data-ttu-id="cc0f0-135">Selezionare 'Arrivi' nel campo Direzione.</span><span class="sxs-lookup"><span data-stu-id="cc0f0-135">In the Direction field, select 'Arrivals'.</span></span>
25. <span data-ttu-id="cc0f0-136">Selezionare Sì nel campo Genera file.</span><span class="sxs-lookup"><span data-stu-id="cc0f0-136">Select Yes in the Generate file field.</span></span>
26. <span data-ttu-id="cc0f0-137">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="cc0f0-137">Click OK.</span></span>
    * <span data-ttu-id="cc0f0-138">Esaminare l'output creato con le righe di riepilogo alla fine.</span><span class="sxs-lookup"><span data-stu-id="cc0f0-138">Review the created output with the summary lines in the end.</span></span>  
27. <span data-ttu-id="cc0f0-139">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="cc0f0-139">Click New.</span></span>
28. <span data-ttu-id="cc0f0-140">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="cc0f0-140">In the list, mark the selected row.</span></span>
29. <span data-ttu-id="cc0f0-141">Selezionare 'Spedizioni' nel campo Direzione.</span><span class="sxs-lookup"><span data-stu-id="cc0f0-141">In the Direction field, select 'Dispatches'.</span></span>
30. <span data-ttu-id="cc0f0-142">Nel campo Numero di articoli immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="cc0f0-142">In the Item number field, enter or select a value.</span></span>
31. <span data-ttu-id="cc0f0-143">Nel campo Voce doganale immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="cc0f0-143">In the Commodity field, enter or select a value.</span></span>
32. <span data-ttu-id="cc0f0-144">Impostare Peso su '10'.</span><span class="sxs-lookup"><span data-stu-id="cc0f0-144">Set Weight to '10'.</span></span>
33. <span data-ttu-id="cc0f0-145">Impostare Importo fattura su '10000'.</span><span class="sxs-lookup"><span data-stu-id="cc0f0-145">Set Invoice amount to '10000'.</span></span>
34. <span data-ttu-id="cc0f0-146">Impostare Importo statistico su '10000'.</span><span class="sxs-lookup"><span data-stu-id="cc0f0-146">Set Statistical amount to '10000'.</span></span>
35. <span data-ttu-id="cc0f0-147">Fare clic su Output.</span><span class="sxs-lookup"><span data-stu-id="cc0f0-147">Click Output.</span></span>
36. <span data-ttu-id="cc0f0-148">Fare clic su Report.</span><span class="sxs-lookup"><span data-stu-id="cc0f0-148">Click Report.</span></span>
37. <span data-ttu-id="cc0f0-149">Selezionare 'Spedizioni' nel campo Direzione.</span><span class="sxs-lookup"><span data-stu-id="cc0f0-149">In the Direction field, select 'Dispatches'.</span></span>
38. <span data-ttu-id="cc0f0-150">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="cc0f0-150">Click OK.</span></span>
    * <span data-ttu-id="cc0f0-151">Esaminare l'output creato con le righe di riepilogo alla fine.</span><span class="sxs-lookup"><span data-stu-id="cc0f0-151">Review the created output with the summary lines in the end.</span></span> <span data-ttu-id="cc0f0-152">Tenere presente che è stato modificato rispetto alla prima esecuzione.</span><span class="sxs-lookup"><span data-stu-id="cc0f0-152">Note that it has been changed in comparison to the first run.</span></span>  

## <a name="run-this-configuration-in-debug-mode-to-review-the-collected-counting--summing-data"></a><span data-ttu-id="cc0f0-153">Eseguire la configurazione in modalità di debug per esaminare i dati di conteggio e somma raccolti</span><span class="sxs-lookup"><span data-stu-id="cc0f0-153">Run this configuration in debug mode to review the collected counting & summing data</span></span>
1. <span data-ttu-id="cc0f0-154">Passare a Amministrazione organizzazione > Reporting elettronico > Configurazioni.</span><span class="sxs-lookup"><span data-stu-id="cc0f0-154">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="cc0f0-155">Nella struttura espandere 'Modello Intrastat'.</span><span class="sxs-lookup"><span data-stu-id="cc0f0-155">In the tree, expand 'Intrastat model'.</span></span>
3. <span data-ttu-id="cc0f0-156">Nella struttura, espandere 'Modello Intrastat\Intrastat (DE)'.</span><span class="sxs-lookup"><span data-stu-id="cc0f0-156">In the tree, expand 'Intrastat model\Intrastat (DE)'.</span></span>
4. <span data-ttu-id="cc0f0-157">Nella struttura selezionare 'Modello Intrastat\Intrastat (DE)\Intrastat (DE) con conteggio e somma'.</span><span class="sxs-lookup"><span data-stu-id="cc0f0-157">In the tree, select 'Intrastat model\Intrastat (DE)\Intrastat (DE) with counting & summing'.</span></span>
5. <span data-ttu-id="cc0f0-158">Nel riquadro azioni, fare clic su Configurazioni.</span><span class="sxs-lookup"><span data-stu-id="cc0f0-158">On the Action Pane, click Configurations.</span></span>
6. <span data-ttu-id="cc0f0-159">Fare clic su Parametri utente.</span><span class="sxs-lookup"><span data-stu-id="cc0f0-159">Click User parameters.</span></span>
7. <span data-ttu-id="cc0f0-160">Selezionare Sì nel campo Esegui in modalità di debug.</span><span class="sxs-lookup"><span data-stu-id="cc0f0-160">Select Yes in the Run in debug mode field.</span></span>
8. <span data-ttu-id="cc0f0-161">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="cc0f0-161">Click OK.</span></span>
9. <span data-ttu-id="cc0f0-162">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="cc0f0-162">Close the page.</span></span>
10. <span data-ttu-id="cc0f0-163">Passare a Imposta > Dichiarazioni > Commercio estero > Intrastat.</span><span class="sxs-lookup"><span data-stu-id="cc0f0-163">Go to Tax > Declarations > Foreign trade > Intrastat.</span></span>
11. <span data-ttu-id="cc0f0-164">Fare clic su Output.</span><span class="sxs-lookup"><span data-stu-id="cc0f0-164">Click Output.</span></span>
12. <span data-ttu-id="cc0f0-165">Fare clic su Report.</span><span class="sxs-lookup"><span data-stu-id="cc0f0-165">Click Report.</span></span>
13. <span data-ttu-id="cc0f0-166">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="cc0f0-166">Click OK.</span></span>
14. <span data-ttu-id="cc0f0-167">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="cc0f0-167">Close the page.</span></span>
15. <span data-ttu-id="cc0f0-168">Passare a Amministrazione organizzazione > Reporting elettronico > Configurazioni.</span><span class="sxs-lookup"><span data-stu-id="cc0f0-168">Go to Organization administration > Electronic reporting > Configurations.</span></span>
16. <span data-ttu-id="cc0f0-169">Nella struttura espandere 'Modello Intrastat'.</span><span class="sxs-lookup"><span data-stu-id="cc0f0-169">In the tree, expand 'Intrastat model'.</span></span>
17. <span data-ttu-id="cc0f0-170">Nella struttura, espandere 'Modello Intrastat\Intrastat (DE)'.</span><span class="sxs-lookup"><span data-stu-id="cc0f0-170">In the tree, expand 'Intrastat model\Intrastat (DE)'.</span></span>
18. <span data-ttu-id="cc0f0-171">Nella struttura selezionare 'Modello Intrastat\Intrastat (DE)\Intrastat (DE) con conteggio e somma'.</span><span class="sxs-lookup"><span data-stu-id="cc0f0-171">In the tree, select 'Intrastat model\Intrastat (DE)\Intrastat (DE) with counting & summing'.</span></span>
19. <span data-ttu-id="cc0f0-172">Fare clic su Registri debug.</span><span class="sxs-lookup"><span data-stu-id="cc0f0-172">Click Debug logs.</span></span>
    * <span data-ttu-id="cc0f0-173">Tenere presente che un record del registro di debug è stato creato per il processo di esecuzione della configurazione selezionata.</span><span class="sxs-lookup"><span data-stu-id="cc0f0-173">Note that a debug log record has been created for the execution process of the selected configuration.</span></span>  
20. <span data-ttu-id="cc0f0-174">Fare clic su Allega.</span><span class="sxs-lookup"><span data-stu-id="cc0f0-174">Click Attach.</span></span>
21. <span data-ttu-id="cc0f0-175">Fare clic su Apri.</span><span class="sxs-lookup"><span data-stu-id="cc0f0-175">Click Open.</span></span>
    * <span data-ttu-id="cc0f0-176">Esaminare il file XML creato che contiene i dettagli di conteggio e somma che sono stati raccolti durante l'esecuzione della configurazione selezionata.</span><span class="sxs-lookup"><span data-stu-id="cc0f0-176">Review the created XML file that contains counting and summing details that were collected during the execution of the selected configuration.</span></span>  


