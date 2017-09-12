---
title: "Impostare ordini di controllo qualità"
description: "In questa procedura viene illustrato come abilitare il processo di gestione della qualità in in cui le scorte in ingresso devono essere controllate subito dopo la registrazione degli arrivi."
author: perlynne
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0e7f66cccd76e5326fce75d1a13aff294c16fb9b
ms.openlocfilehash: 73981313fc662094ee4f8bb15a88271e16d41193
ms.contentlocale: it-it
ms.lasthandoff: 09/12/2017

---
# <a name="set-up-quality-orders"></a><span data-ttu-id="2bf0e-103">Impostare ordini di controllo qualità</span><span class="sxs-lookup"><span data-stu-id="2bf0e-103">Set up quality orders</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="2bf0e-104">In questa procedura viene illustrato come abilitare il processo di gestione della qualità in in cui le scorte in ingresso devono essere controllate subito dopo la registrazione degli arrivi.</span><span class="sxs-lookup"><span data-stu-id="2bf0e-104">This procedure shows you how to enable a quality management process where incoming inventory must be inspected immediately after arrival registration.</span></span> <span data-ttu-id="2bf0e-105">La procedura in genere verrà eseguita da un responsabile della qualità.</span><span class="sxs-lookup"><span data-stu-id="2bf0e-105">The procedure will typically be carried out by a quality manager.</span></span> <span data-ttu-id="2bf0e-106">Il processo comprende la creazione di un gruppo di controllo qualità per definire gli articoli che verranno campionati e un gruppo di test per raggruppare i test da eseguire sugli articoli nel gruppo di controllo qualità.</span><span class="sxs-lookup"><span data-stu-id="2bf0e-106">The process includes the creation of a quality group, to define the items that are going to be sampled, and a test group to group the tests that are to be performed on items in the quality group.</span></span> <span data-ttu-id="2bf0e-107">È possibile eseguire questa guida nella società di dati dimostrativi USMF.</span><span class="sxs-lookup"><span data-stu-id="2bf0e-107">You can run this guide in the USMF demo data company.</span></span>


## <a name="enable-quality-management"></a><span data-ttu-id="2bf0e-108">Abilitare la gestione qualità</span><span class="sxs-lookup"><span data-stu-id="2bf0e-108">Enable quality management</span></span>
1. <span data-ttu-id="2bf0e-109">Fare clic su Gestione magazzino > Impostazioni > Parametri di gestione articoli e magazzino.</span><span class="sxs-lookup"><span data-stu-id="2bf0e-109">Go to Inventory management > Setup > Inventory and warehouse management parameters.</span></span>
2. <span data-ttu-id="2bf0e-110">Fare clic sulla scheda Gestione qualità.</span><span class="sxs-lookup"><span data-stu-id="2bf0e-110">Click the Quality management tab.</span></span>
3. <span data-ttu-id="2bf0e-111">Impostare l'opzione Usa Gestione qualità su Sì.</span><span class="sxs-lookup"><span data-stu-id="2bf0e-111">Set the Use quality management option to Yes.</span></span>
4. <span data-ttu-id="2bf0e-112">Fare clic su Impostazione report.</span><span class="sxs-lookup"><span data-stu-id="2bf0e-112">Click Report setup.</span></span>
    * <span data-ttu-id="2bf0e-113">In USMF, l'impostazione dei report per la gestione della qualità già è definita.</span><span class="sxs-lookup"><span data-stu-id="2bf0e-113">In USMF, the report setup for quality management is already defined.</span></span> <span data-ttu-id="2bf0e-114">Se così non fosse, aggiungereste le nuove righe qui per i tipi differenti di report e selezionereste il tipo di documento da usare per ogni report.</span><span class="sxs-lookup"><span data-stu-id="2bf0e-114">If this wasn’t done, you’d add new lines here for the different report types, and select the type of document to be used for each report.</span></span>  
5. <span data-ttu-id="2bf0e-115">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="2bf0e-115">Close the page.</span></span>
6. <span data-ttu-id="2bf0e-116">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="2bf0e-116">Close the page.</span></span>

## <a name="create-a-test"></a><span data-ttu-id="2bf0e-117">Creare un test</span><span class="sxs-lookup"><span data-stu-id="2bf0e-117">Create a test</span></span>
1. <span data-ttu-id="2bf0e-118">Andare a Gestione articoli > Impostazioni > Controlo qualità > Test.</span><span class="sxs-lookup"><span data-stu-id="2bf0e-118">Go to Inventory management > Setup > Quality control > Tests.</span></span>
2. <span data-ttu-id="2bf0e-119">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="2bf0e-119">Click New.</span></span>
3. <span data-ttu-id="2bf0e-120">Digitare un valore nel campo Test.</span><span class="sxs-lookup"><span data-stu-id="2bf0e-120">In the Test field, type a value.</span></span>
4. <span data-ttu-id="2bf0e-121">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="2bf0e-121">In the Description field, type a value.</span></span>
5. <span data-ttu-id="2bf0e-122">Selezionare "Opzione" nel campo Tipo.</span><span class="sxs-lookup"><span data-stu-id="2bf0e-122">In the Type field, select 'Option'.</span></span>
    * <span data-ttu-id="2bf0e-123">In questo esempio, verrà selezionato "Opzione" che permetterà di assegnare i risultati del test in base ai valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="2bf0e-123">In this example, we'll select "Option" which will make it possible to assign the test results based on pre-defined values.</span></span>  
6. <span data-ttu-id="2bf0e-124">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="2bf0e-124">Click Save.</span></span>
7. <span data-ttu-id="2bf0e-125">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="2bf0e-125">Close the page.</span></span>

## <a name="create-test-variables-to-define-the-way-test-results-are-recorded"></a><span data-ttu-id="2bf0e-126">Creare variabili di test per definire la modalità in cui i risultati del test vengono registrati</span><span class="sxs-lookup"><span data-stu-id="2bf0e-126">Create Test variables to define the way test results are recorded</span></span>
1. <span data-ttu-id="2bf0e-127">Andare a Gestione articoli > Impostazioni > Controllo qualità > Variabili di test.</span><span class="sxs-lookup"><span data-stu-id="2bf0e-127">Go to Inventory management > Setup > Quality control > Test variables.</span></span>
2. <span data-ttu-id="2bf0e-128">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="2bf0e-128">Click New.</span></span>
3. <span data-ttu-id="2bf0e-129">Digitare un valore nel campo Variabile.</span><span class="sxs-lookup"><span data-stu-id="2bf0e-129">In the Variable field, type a value.</span></span>
4. <span data-ttu-id="2bf0e-130">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="2bf0e-130">In the Description field, type a value.</span></span>
5. <span data-ttu-id="2bf0e-131">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="2bf0e-131">Click Save.</span></span>
6. <span data-ttu-id="2bf0e-132">Fare clic su Risultati.</span><span class="sxs-lookup"><span data-stu-id="2bf0e-132">Click Outcomes.</span></span>
7. <span data-ttu-id="2bf0e-133">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="2bf0e-133">Click New.</span></span>
8. <span data-ttu-id="2bf0e-134">Digitare un valore nel campo Risultato.</span><span class="sxs-lookup"><span data-stu-id="2bf0e-134">In the Outcome field, type a value.</span></span>
9. <span data-ttu-id="2bf0e-135">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="2bf0e-135">In the Description field, type a value.</span></span>
10. <span data-ttu-id="2bf0e-136">Selezionare "Superato" nel campo Stato risultato.</span><span class="sxs-lookup"><span data-stu-id="2bf0e-136">In the Outcome status field, select 'Pass'.</span></span>
11. <span data-ttu-id="2bf0e-137">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="2bf0e-137">Click Save.</span></span>
12. <span data-ttu-id="2bf0e-138">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="2bf0e-138">Click New.</span></span>
13. <span data-ttu-id="2bf0e-139">Digitare un valore nel campo Risultato.</span><span class="sxs-lookup"><span data-stu-id="2bf0e-139">In the Outcome field, type a value.</span></span>
14. <span data-ttu-id="2bf0e-140">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="2bf0e-140">In the Description field, type a value.</span></span>
15. <span data-ttu-id="2bf0e-141">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="2bf0e-141">Click Save.</span></span>
16. <span data-ttu-id="2bf0e-142">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="2bf0e-142">Close the page.</span></span>
17. <span data-ttu-id="2bf0e-143">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="2bf0e-143">Close the page.</span></span>

## <a name="set-up-item-sampling"></a><span data-ttu-id="2bf0e-144">Imposta il campionamento articoli</span><span class="sxs-lookup"><span data-stu-id="2bf0e-144">Set up item sampling</span></span>
1. <span data-ttu-id="2bf0e-145">Andare a Gestione articoli > Impostazioni > Controllo qualità > Campionamento articoli.</span><span class="sxs-lookup"><span data-stu-id="2bf0e-145">Go to Inventory management > Setup > Quality control > Item sampling.</span></span>
2. <span data-ttu-id="2bf0e-146">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="2bf0e-146">Click New.</span></span>
3. <span data-ttu-id="2bf0e-147">Nel campo Campionamento articoli, digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="2bf0e-147">In the Item sampling field, type a value.</span></span>
4. <span data-ttu-id="2bf0e-148">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="2bf0e-148">In the Description field, type a value.</span></span>
5. <span data-ttu-id="2bf0e-149">Nel campo Valore immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="2bf0e-149">In the Value field, enter a number.</span></span>
    * <span data-ttu-id="2bf0e-150">Questo valore è correlato alla specifica della quantità selezionata nel campo adiacente.</span><span class="sxs-lookup"><span data-stu-id="2bf0e-150">This value relates to the Quantity specification that’s selected in the adjacent field.</span></span>  
6. <span data-ttu-id="2bf0e-151">Espandere o comprimere la sezione Elaborazione.</span><span class="sxs-lookup"><span data-stu-id="2bf0e-151">Expand or collapse the Process section.</span></span>
7. <span data-ttu-id="2bf0e-152">Selezionare o deselezionare la casella di controllo Bloccaggio totale.</span><span class="sxs-lookup"><span data-stu-id="2bf0e-152">Select or clear the Full blocking check box.</span></span>
    * <span data-ttu-id="2bf0e-153">Se si seleziona questa opzione, l'intera quantità del lotto o d della riga ordine viene bloccata se un test ha esito negativo.</span><span class="sxs-lookup"><span data-stu-id="2bf0e-153">If you select this option, the whole lot or order line quantity is blocked if a test is failed.</span></span> <span data-ttu-id="2bf0e-154">Se tale opzione non viene selezionata, solo gli articoli nell'ordine di controllo qualità sono bloccati.</span><span class="sxs-lookup"><span data-stu-id="2bf0e-154">If you don't select it, only the items in the quality order are blocked.</span></span>  
8. <span data-ttu-id="2bf0e-155">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="2bf0e-155">Click Save.</span></span>
9. <span data-ttu-id="2bf0e-156">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="2bf0e-156">Close the page.</span></span>

## <a name="create-a-quality-group"></a><span data-ttu-id="2bf0e-157">Creare un gruppo di controllo qualità</span><span class="sxs-lookup"><span data-stu-id="2bf0e-157">Create a quality group</span></span>
1. <span data-ttu-id="2bf0e-158">Andare a Gestione articoli > Impostazioni > Controllo qualità > Gruppi di controllo qualità.</span><span class="sxs-lookup"><span data-stu-id="2bf0e-158">Go to Inventory management > Setup > Quality control > Quality groups.</span></span>
2. <span data-ttu-id="2bf0e-159">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="2bf0e-159">Click New.</span></span>
3. <span data-ttu-id="2bf0e-160">Digitare un valore nel campo Gruppo di controllo qualità.</span><span class="sxs-lookup"><span data-stu-id="2bf0e-160">In the Quality group field, type a value.</span></span>
    * <span data-ttu-id="2bf0e-161">Utilizzare un nome descrittivo per identificare il tipo di articoli che conterrà il gruppo (i criteri di campionamento).</span><span class="sxs-lookup"><span data-stu-id="2bf0e-161">Use a descriptive name to help you identify which kind of items the group will contain (your sampling criteria).</span></span>  
4. <span data-ttu-id="2bf0e-162">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="2bf0e-162">In the Description field, type a value.</span></span>
5. <span data-ttu-id="2bf0e-163">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="2bf0e-163">Click Save.</span></span>
6. <span data-ttu-id="2bf0e-164">Fare clic su Aggiungi articoli.</span><span class="sxs-lookup"><span data-stu-id="2bf0e-164">Click Add items.</span></span>
7. <span data-ttu-id="2bf0e-165">Selezionare la riga numero articolo</span><span class="sxs-lookup"><span data-stu-id="2bf0e-165">Select the Item number row</span></span>
    * <span data-ttu-id="2bf0e-166">In questo esempio il filtro verrà eseguito in base al numero di articolo.</span><span class="sxs-lookup"><span data-stu-id="2bf0e-166">In this example the filtering will be run based on  the item number.</span></span>  
8. <span data-ttu-id="2bf0e-167">Digitare un valore nel campo Criteri.</span><span class="sxs-lookup"><span data-stu-id="2bf0e-167">In the Criteria field, type a value.</span></span>
    * <span data-ttu-id="2bf0e-168">Ad esempio, digitare T* per filtrare i numeri di articolo che iniziano con T.</span><span class="sxs-lookup"><span data-stu-id="2bf0e-168">For example, type T* to filter on the item numbers that start with T.</span></span>  
9. <span data-ttu-id="2bf0e-169">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="2bf0e-169">Click OK.</span></span>
10. <span data-ttu-id="2bf0e-170">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="2bf0e-170">Click OK.</span></span>
11. <span data-ttu-id="2bf0e-171">Fare clic su Gruppi di controllo qualità articoli.</span><span class="sxs-lookup"><span data-stu-id="2bf0e-171">Click Item quality groups.</span></span>
12. <span data-ttu-id="2bf0e-172">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="2bf0e-172">Close the page.</span></span>
13. <span data-ttu-id="2bf0e-173">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="2bf0e-173">Close the page.</span></span>

## <a name="create-a-test-group"></a><span data-ttu-id="2bf0e-174">Creazione di un gruppo di test</span><span class="sxs-lookup"><span data-stu-id="2bf0e-174">Create a test group</span></span>
1. <span data-ttu-id="2bf0e-175">Andare a Gestione articoli > Impostazioni > Controllo qualità > Gruppi di test.</span><span class="sxs-lookup"><span data-stu-id="2bf0e-175">Go to Inventory management > Setup > Quality control > Test groups.</span></span>
2. <span data-ttu-id="2bf0e-176">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="2bf0e-176">Click New.</span></span>
3. <span data-ttu-id="2bf0e-177">Digitare un valore nel campo Gruppo di test.</span><span class="sxs-lookup"><span data-stu-id="2bf0e-177">In the Test group field, type a value.</span></span>
    * <span data-ttu-id="2bf0e-178">Assegnare al gruppo di test un nome che consente di ricordare il tipo di test eseguito e il gruppo di controllo qualità a cui deve essere associato.</span><span class="sxs-lookup"><span data-stu-id="2bf0e-178">Give the Test group a name that will help you remember what kind of tests are being run, and which quality group it should be associated with.</span></span> <span data-ttu-id="2bf0e-179">Ad esempio, se deve essere utilizzato con un gruppo di controllo qualità che seleziona gli articoli che iniziano con "T" è possibile chiamarlo "Test articoli con la T".</span><span class="sxs-lookup"><span data-stu-id="2bf0e-179">For example, it it’s to be used with a quality group that selects items starting with “T”, you could call it “T-item tests”.</span></span>  
4. <span data-ttu-id="2bf0e-180">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="2bf0e-180">In the Description field, type a value.</span></span>
5. <span data-ttu-id="2bf0e-181">Nel campo Campionamento articoli, selezionare la riga di campionamento articoli creata prima.</span><span class="sxs-lookup"><span data-stu-id="2bf0e-181">In the Item sampling field, select the item sampling line that you created before.</span></span>
6. <span data-ttu-id="2bf0e-182">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="2bf0e-182">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="2bf0e-183">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="2bf0e-183">Click Add.</span></span>
8. <span data-ttu-id="2bf0e-184">Immettere un numero nel campo Numero progressivo.</span><span class="sxs-lookup"><span data-stu-id="2bf0e-184">In the Sequence number field, enter a number.</span></span>
9. <span data-ttu-id="2bf0e-185">Nel campo Test selezionare il test creato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="2bf0e-185">In the Test field, select the test that you created earlier.</span></span>
10. <span data-ttu-id="2bf0e-186">Trovare e selezionare il record desiderato nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="2bf0e-186">In the list, find and select the desired record.</span></span>
11. <span data-ttu-id="2bf0e-187">Fare clic sulla scheda Test.</span><span class="sxs-lookup"><span data-stu-id="2bf0e-187">Click the Test tab.</span></span>
12. <span data-ttu-id="2bf0e-188">Nel campo Variabile selezionare la variabile creata in precedenza.</span><span class="sxs-lookup"><span data-stu-id="2bf0e-188">In the Variable field, select the test variable that you created before</span></span>
13. <span data-ttu-id="2bf0e-189">Trovare e selezionare il record desiderato nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="2bf0e-189">In the list, find and select the desired record.</span></span>
14. <span data-ttu-id="2bf0e-190">Nel campo Risultato predefinito fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="2bf0e-190">In the Default outcome field, click the drop-down button to open the lookup.</span></span>
15. <span data-ttu-id="2bf0e-191">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="2bf0e-191">In the list, click the link in the selected row.</span></span>
16. <span data-ttu-id="2bf0e-192">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="2bf0e-192">Click Save.</span></span>
17. <span data-ttu-id="2bf0e-193">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="2bf0e-193">Close the page.</span></span>

## <a name="define-when-quality-orders-will-be-created"></a><span data-ttu-id="2bf0e-194">Definire quando gli ordini di controllo qualità verranno creati</span><span class="sxs-lookup"><span data-stu-id="2bf0e-194">Define when quality orders will be created</span></span>
1. <span data-ttu-id="2bf0e-195">Andare a Gestione articoli > Impostazioni > Controllo qualità > Associazioni di controllo qualità.</span><span class="sxs-lookup"><span data-stu-id="2bf0e-195">Go to Inventory management > Setup > Quality control > Quality associations.</span></span>
2. <span data-ttu-id="2bf0e-196">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="2bf0e-196">Click New.</span></span>
3. <span data-ttu-id="2bf0e-197">Selezionare un'opzione nel campo Tipo di riferimento.</span><span class="sxs-lookup"><span data-stu-id="2bf0e-197">In the Reference type field, select an option.</span></span>
4. <span data-ttu-id="2bf0e-198">Selezionare "Gruppo" nel campo Codice articolo.</span><span class="sxs-lookup"><span data-stu-id="2bf0e-198">In the Item code field, select 'Group'.</span></span>
    * <span data-ttu-id="2bf0e-199">In questo esempio verrà selezionato "Gruppo" e utilizzato il gruppo di controllo qualità creato prima.</span><span class="sxs-lookup"><span data-stu-id="2bf0e-199">In this example, we’ll select "Group" and use the quality group we created before.</span></span> <span data-ttu-id="2bf0e-200">È inoltre possibile impostare il gruppo su "Tabella" per specificare gli articoli manualmente oppure selezionare "Tutti" per aggiungere tutti gli articoli all'ordine di controllo qualità.</span><span class="sxs-lookup"><span data-stu-id="2bf0e-200">You could also set this to "Table" to specify the items manually, or select "All" to add all items to the quality order.</span></span>  
5. <span data-ttu-id="2bf0e-201">Nel campo Articolo selezionare il gruppo di controllo qualità creato prima.</span><span class="sxs-lookup"><span data-stu-id="2bf0e-201">In the Item field, select the quality group that you created before.</span></span>
    * <span data-ttu-id="2bf0e-202">Le opzioni disponibili nel campo Articolo dipendono dall'opzione impostata nel campo Codice articolo.</span><span class="sxs-lookup"><span data-stu-id="2bf0e-202">The options available in the Item field depend on what you set in the Item code field.</span></span>  
6. <span data-ttu-id="2bf0e-203">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="2bf0e-203">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="2bf0e-204">Espandere o comprimere la sezione Elaborazione.</span><span class="sxs-lookup"><span data-stu-id="2bf0e-204">Expand or collapse the Process section.</span></span>
8. <span data-ttu-id="2bf0e-205">Nel campo Tipo di evento selezionare un'opzione.</span><span class="sxs-lookup"><span data-stu-id="2bf0e-205">In the Event type field, select an option.</span></span>
    * <span data-ttu-id="2bf0e-206">Si tratta dell'evento che attiva il test.</span><span class="sxs-lookup"><span data-stu-id="2bf0e-206">This is the event that triggers the test.</span></span> <span data-ttu-id="2bf0e-207">Le opzioni disponibili in questo campo dipendono dal processo selezionato nel campo del Tipo di riferimento.</span><span class="sxs-lookup"><span data-stu-id="2bf0e-207">The options available here depend on which process you selected in the Reference type field.</span></span>  
9. <span data-ttu-id="2bf0e-208">Selezionare un'opzione nel campo Esecuzione.</span><span class="sxs-lookup"><span data-stu-id="2bf0e-208">In the Execution field, select an option.</span></span>
10. <span data-ttu-id="2bf0e-209">Espandere o comprimere la sezione Processo ordine di controllo qualità.</span><span class="sxs-lookup"><span data-stu-id="2bf0e-209">Expand or collapse the Quality order process section.</span></span>
11. <span data-ttu-id="2bf0e-210">Nel campo Bloccaggio evento fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="2bf0e-210">In the Event blocking field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="2bf0e-211">In questo campo viene visualizzato l'elenco dei processi che è possibile bloccare se l'ordine di controllo qualità è ancora aperto.</span><span class="sxs-lookup"><span data-stu-id="2bf0e-211">This field shows the list of processes that it’s possible to block if the quality order is still open.</span></span> <span data-ttu-id="2bf0e-212">Le opzioni disponibili dipendono dall'opzione selezionata nel campo Tipo di evento.</span><span class="sxs-lookup"><span data-stu-id="2bf0e-212">The options depend on what you selected in the Event type field.</span></span>  
12. <span data-ttu-id="2bf0e-213">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="2bf0e-213">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="2bf0e-214">Tale opzione dipenderà dai valori selezionati precedenti.</span><span class="sxs-lookup"><span data-stu-id="2bf0e-214">This will be depending on the previous selected values.</span></span> <span data-ttu-id="2bf0e-215">Selezionare se i seguenti processi devono essere bloccati mentre si hanno ordini di controllo qualità aperti collegati a una riga documento di origine.</span><span class="sxs-lookup"><span data-stu-id="2bf0e-215">Select if the following processes must be blocked while having open quality orders linked to a source document line.</span></span>  
13. <span data-ttu-id="2bf0e-216">Espandere o comprimere la sezione Specifiche.</span><span class="sxs-lookup"><span data-stu-id="2bf0e-216">Expand or collapse the Specifications section.</span></span>
14. <span data-ttu-id="2bf0e-217">Nel campo Gruppo di test selezionare il gruppo di test creato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="2bf0e-217">In the Test group field, select the test group that you created before.</span></span>
15. <span data-ttu-id="2bf0e-218">Trovare e selezionare il record desiderato nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="2bf0e-218">In the list, find and select the desired record.</span></span>
16. <span data-ttu-id="2bf0e-219">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="2bf0e-219">Click Save.</span></span>
17. <span data-ttu-id="2bf0e-220">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="2bf0e-220">Close the page.</span></span>
