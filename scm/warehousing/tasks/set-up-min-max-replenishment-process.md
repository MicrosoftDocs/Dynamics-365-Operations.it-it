--- 
title: Impostare un processo di rifornimento minimo/massimo
description: Questa procedura mostra come impostare un nuovo processo di rifornimento che utilizza la strategia di rifornimento minima/massima.
author: perlynne
manager: AnnBe
ms.date: 06/07/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 02af5d1beb2d4eb6a7162b47c42854725fbdbec2
ms.contentlocale: it-it
ms.lasthandoff: 08/29/2017

---
# <a name="set-up-a-min-max-replenishment-process"></a><span data-ttu-id="5e706-103">Impostare un processo di rifornimento minimo/massimo</span><span class="sxs-lookup"><span data-stu-id="5e706-103">Set up a min-max replenishment process</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="5e706-104">Questa procedura mostra come impostare un nuovo processo di rifornimento che utilizza la strategia di rifornimento minima/massima.</span><span class="sxs-lookup"><span data-stu-id="5e706-104">This procedure shows you how to set up a new replenishment process which uses the minimum/maximum replenishment strategy.</span></span> <span data-ttu-id="5e706-105">Quando le scorte scendono sotto il livello minimo, il lavoro verrà creato per rifornire l'ubicazione.</span><span class="sxs-lookup"><span data-stu-id="5e706-105">When inventory falls below the minimum level, work will be created to replenish the location.</span></span> <span data-ttu-id="5e706-106">La procedura mostra anche come utilizzare le ubicazioni fisse di prelievo per consentire il ristoccaggio anche se le scorte scendono sotto il livello minimo e come consentire l'esecuzione regolare del processo di rifornimento utilizzando un processo batch.</span><span class="sxs-lookup"><span data-stu-id="5e706-106">The procedure also shows how to use fixed picking locations to allow restocking even if inventory falls below the minimum level, and how to enable the replenishment process to run regularly using a batch job.</span></span> <span data-ttu-id="5e706-107">Queste attività verranno in genere svolte da un responsabile del magazzino.</span><span class="sxs-lookup"><span data-stu-id="5e706-107">These tasks would typically be carried out by a warehouse manager.</span></span> <span data-ttu-id="5e706-108">È possibile eseguire questa procedura nella società di dati dimostrativi USMF utilizzando i valori di esempio nelle note oppure è possibile eseguirla sui propri dati.</span><span class="sxs-lookup"><span data-stu-id="5e706-108">You can run this procedure in the USMF demo data company using the example values in the notes, or can run it on your own data.</span></span> <span data-ttu-id="5e706-109">Se si utilizzano i propri dati, assicurarsi che un magazzino sia abilitato per i processi di gestione magazzino.</span><span class="sxs-lookup"><span data-stu-id="5e706-109">If you’re using your own data, make sure that you have a warehouse that’s enabled for Warehouse management processes.</span></span>


## <a name="create-a-fixed-picking-location"></a><span data-ttu-id="5e706-110">Creare un'ubicazioni fissa di prelievo</span><span class="sxs-lookup"><span data-stu-id="5e706-110">Create a fixed picking location</span></span>
1. <span data-ttu-id="5e706-111">Andare a Gestione magazzino > Impostazioni > Magazzino > Ubicazioni fisse.</span><span class="sxs-lookup"><span data-stu-id="5e706-111">Go to Warehouse management > Setup > Warehouse > Fixed locations.</span></span>
    * <span data-ttu-id="5e706-112">Si tratta di un'attività facoltativa per il rifornimento min- max, ma se si utilizza l'ubicazione fissa di prelievo, questa consente il rifornimento delle scorte anche se scendono al livello minimo, poiché il sistema può determinare quali articoli devono essere riforniti, anche se non ne sono rimasti.</span><span class="sxs-lookup"><span data-stu-id="5e706-112">This is an optional task for min-max replenishment, but if you use fixed picking location, this allows stock to be replenished even if it falls below the minimum level, because the system can determine which items need to be replenished, even if there aren't any left.</span></span>  
2. <span data-ttu-id="5e706-113">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="5e706-113">Click New.</span></span>
3. <span data-ttu-id="5e706-114">Nel campo Numero di articoli immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="5e706-114">In the Item number field, enter or select a value.</span></span>
    * <span data-ttu-id="5e706-115">Se si utilizza USMF, è possibile selezionare l'articolo A0001.</span><span class="sxs-lookup"><span data-stu-id="5e706-115">If you’re using USMF, you can select item A0001.</span></span>  
4. <span data-ttu-id="5e706-116">Nel campo Sito immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="5e706-116">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="5e706-117">Se si utilizza USMF, è possibile selezionare il sito 2.</span><span class="sxs-lookup"><span data-stu-id="5e706-117">If you’re using USMF, you can select site 2.</span></span>  
5. <span data-ttu-id="5e706-118">Nel campo Magazzino immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="5e706-118">In the Warehouse field, enter or select a value.</span></span>
    * <span data-ttu-id="5e706-119">Se si utilizza USMF, è possibile selezionare il magazzino 24.</span><span class="sxs-lookup"><span data-stu-id="5e706-119">If you’re using USMF, you can select warehouse 24.</span></span>  
6. <span data-ttu-id="5e706-120">Nel campo Ubicazione immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="5e706-120">In the Location field, enter or select a value.</span></span>
    * <span data-ttu-id="5e706-121">Se si utilizza USMF, è possibile selezionare CP-003.</span><span class="sxs-lookup"><span data-stu-id="5e706-121">If you’re using USMF, you can select CP-003.</span></span>  
7. <span data-ttu-id="5e706-122">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="5e706-122">Close the page.</span></span>

## <a name="create-a-replenishment-location-directive"></a><span data-ttu-id="5e706-123">Creare una direttiva ubicazione di rifornimento</span><span class="sxs-lookup"><span data-stu-id="5e706-123">Create a replenishment location directive</span></span>
1. <span data-ttu-id="5e706-124">Andare a Gestione magazzino > Impostazioni > Magazzino > Direttive ubicazione.</span><span class="sxs-lookup"><span data-stu-id="5e706-124">Go to Warehouse management > Setup > Location directives.</span></span>
    * <span data-ttu-id="5e706-125">Le direttive di ubicazione vengono utilizzate per determinare il luogo di prelievo degli articoli nel processo di rifornimento.</span><span class="sxs-lookup"><span data-stu-id="5e706-125">Location directives are used to determine where items should be picked from in the replenishment process.</span></span>  
2. <span data-ttu-id="5e706-126">Nel campo Tipo ordine di lavoro selezionare "Rifornimento".</span><span class="sxs-lookup"><span data-stu-id="5e706-126">In the Work order type field, select 'Replenishment'.</span></span>
3. <span data-ttu-id="5e706-127">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="5e706-127">Click New.</span></span>
4. <span data-ttu-id="5e706-128">Digitare un valore nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="5e706-128">In the Name field, type a value.</span></span>
5. <span data-ttu-id="5e706-129">Nel campo Tipo di lavoro, selezionare 'Preleva'.</span><span class="sxs-lookup"><span data-stu-id="5e706-129">In the Work type field, select 'Pick'.</span></span>
6. <span data-ttu-id="5e706-130">Nel campo Sito immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="5e706-130">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="5e706-131">Se si utilizza USMF, è possibile selezionare il sito 2.</span><span class="sxs-lookup"><span data-stu-id="5e706-131">If you’re using USMF, you can select site 2.</span></span>  
7. <span data-ttu-id="5e706-132">Nel campo Magazzino immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="5e706-132">In the Warehouse field, enter or select a value.</span></span>
    * <span data-ttu-id="5e706-133">Se si utilizza USMF, è possibile selezionare il magazzino 24.</span><span class="sxs-lookup"><span data-stu-id="5e706-133">If you’re using USMF, you can select warehouse 24.</span></span>  
8. <span data-ttu-id="5e706-134">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="5e706-134">Click Save.</span></span>
9. <span data-ttu-id="5e706-135">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="5e706-135">Click New.</span></span>
10. <span data-ttu-id="5e706-136">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="5e706-136">In the list, mark the selected row.</span></span>
11. <span data-ttu-id="5e706-137">Nel campo A quantità immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="5e706-137">In the To quantity field, enter a number.</span></span>
    * <span data-ttu-id="5e706-138">È ad esempio possibile impostarlo su 9999.</span><span class="sxs-lookup"><span data-stu-id="5e706-138">For example, you can set it to 9999.</span></span>  
12. <span data-ttu-id="5e706-139">Selezionare la casella di controllo Consenti divisione.</span><span class="sxs-lookup"><span data-stu-id="5e706-139">Select the Allow split check box.</span></span>
    * <span data-ttu-id="5e706-140">Se si seleziona questa opzione, il processo di creazione del lavoro consentirà la suddivisione delle quantità di righe di lavoro tra più ubicazioni.</span><span class="sxs-lookup"><span data-stu-id="5e706-140">If you select this option, the work creation process will allow work line quantities to be split across multiple locations.</span></span>  
13. <span data-ttu-id="5e706-141">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="5e706-141">Click Save.</span></span>
14. <span data-ttu-id="5e706-142">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="5e706-142">Click New.</span></span>
15. <span data-ttu-id="5e706-143">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="5e706-143">In the list, mark the selected row.</span></span>
16. <span data-ttu-id="5e706-144">Digitare un valore nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="5e706-144">In the Name field, type a value.</span></span>
17. <span data-ttu-id="5e706-145">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="5e706-145">Click Save.</span></span>
18. <span data-ttu-id="5e706-146">Fare clic su Modifica query.</span><span class="sxs-lookup"><span data-stu-id="5e706-146">Click Edit query.</span></span>
    * <span data-ttu-id="5e706-147">È possibile modificare questa query per aggiungere le restrizioni relative alla selezione dell'inventario nel processo di rifornimento.</span><span class="sxs-lookup"><span data-stu-id="5e706-147">You can edit this query to add restrictions where inventory can be selected from in the replenishment process.</span></span> <span data-ttu-id="5e706-148">Ad esempio, è possibile che l'inventario debba essere utilizzato solo dall'area di stoccaggio del magazzino.</span><span class="sxs-lookup"><span data-stu-id="5e706-148">For example, it could be that inventory should only be used from the Bulk area of the warehouse.</span></span>  
19. <span data-ttu-id="5e706-149">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="5e706-149">Click OK.</span></span>
20. <span data-ttu-id="5e706-150">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="5e706-150">Close the page.</span></span>

## <a name="create-a-replenishment-work-template"></a><span data-ttu-id="5e706-151">Creare un modello di lavoro di rifornimento</span><span class="sxs-lookup"><span data-stu-id="5e706-151">Create a replenishment work template</span></span>
1. <span data-ttu-id="5e706-152">Andare a Gestione magazzino > Impostazioni > Lavoro > Modelli di lavoro.</span><span class="sxs-lookup"><span data-stu-id="5e706-152">Go to Warehouse management > Setup > Work > Work templates.</span></span>
    * <span data-ttu-id="5e706-153">Il modello di lavoro consente di indicare al sistema come deve essere creato il lavoro di rifornimento min/max.</span><span class="sxs-lookup"><span data-stu-id="5e706-153">The work template is use to guide the system as to how the min/max replenishment work must be created.</span></span> <span data-ttu-id="5e706-154">Come minimo, deve essere presente una riga del modello di lavoro per un prelievo e un inserimento.</span><span class="sxs-lookup"><span data-stu-id="5e706-154">As a minimum, there must be a work template line for a pick and a put.</span></span> <span data-ttu-id="5e706-155">Il modello di lavoro dirà che non è valida fino al completamento di tutte le informazioni richieste.</span><span class="sxs-lookup"><span data-stu-id="5e706-155">The work template will say that it’s Invalid until all the necessary information has been filled in.</span></span>  
2. <span data-ttu-id="5e706-156">Nel campo Tipo ordine di lavoro selezionare "Rifornimento".</span><span class="sxs-lookup"><span data-stu-id="5e706-156">In the Work order type field, select 'Replenishment'.</span></span>
3. <span data-ttu-id="5e706-157">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="5e706-157">Click New.</span></span>
4. <span data-ttu-id="5e706-158">Digitare un valore nel campo Modello di lavoro.</span><span class="sxs-lookup"><span data-stu-id="5e706-158">In the Work template field, type a value.</span></span>
5. <span data-ttu-id="5e706-159">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="5e706-159">Click Save.</span></span>
6. <span data-ttu-id="5e706-160">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="5e706-160">Click New.</span></span>
7. <span data-ttu-id="5e706-161">Nel campo Tipo di lavoro, selezionare 'Preleva'.</span><span class="sxs-lookup"><span data-stu-id="5e706-161">In the Work type field, select 'Pick'.</span></span>
8. <span data-ttu-id="5e706-162">Nel campo ID classe lavoro immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="5e706-162">In the Work class ID field, enter or select a value.</span></span>
    * <span data-ttu-id="5e706-163">Questo deve essere una classe di lavoro correlata al rifornimento.</span><span class="sxs-lookup"><span data-stu-id="5e706-163">This should be a work class related to replenishment.</span></span> <span data-ttu-id="5e706-164">Se si utilizza USMF, selezionare Rifornisci.</span><span class="sxs-lookup"><span data-stu-id="5e706-164">If you’re using USMF, select Replenish.</span></span>  
9. <span data-ttu-id="5e706-165">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="5e706-165">Click New.</span></span>
10. <span data-ttu-id="5e706-166">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="5e706-166">In the list, mark the selected row.</span></span>
11. <span data-ttu-id="5e706-167">Nel campo Tipo di lavoro selezionare "Inserisci".</span><span class="sxs-lookup"><span data-stu-id="5e706-167">In the Work type field, select 'Put'.</span></span>
12. <span data-ttu-id="5e706-168">Nel campo ID classe lavoro immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="5e706-168">In the Work class ID field, enter or select a value.</span></span>
13. <span data-ttu-id="5e706-169">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="5e706-169">Click Save.</span></span>
14. <span data-ttu-id="5e706-170">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="5e706-170">Close the page.</span></span>

## <a name="create-a-new-replenishment-template"></a><span data-ttu-id="5e706-171">Creare un nuovo modello di rifornimento</span><span class="sxs-lookup"><span data-stu-id="5e706-171">Create a new replenishment template</span></span>
1. <span data-ttu-id="5e706-172">Andare a Gestione magazzino > Impostazioni > Rifornimento > Modelli rifornimento.</span><span class="sxs-lookup"><span data-stu-id="5e706-172">Go to Warehouse management > Setup > Replenishment > Replenishment templates.</span></span>
    * <span data-ttu-id="5e706-173">Il modello di rifornimento viene utilizzato per definire gli articoli e le quantità e l'ubicazione da rifornire.</span><span class="sxs-lookup"><span data-stu-id="5e706-173">The replenishment template is used to define the items and quantities, and the location to replenish.</span></span>  
2. <span data-ttu-id="5e706-174">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="5e706-174">Click New.</span></span>
3. <span data-ttu-id="5e706-175">Digitare un valore nel campo Modello rifornimento.</span><span class="sxs-lookup"><span data-stu-id="5e706-175">In the Replenish template field, type a value.</span></span>
    * <span data-ttu-id="5e706-176">Assegnare al modello un nome per indicare che è per il rifornimento min/max.</span><span class="sxs-lookup"><span data-stu-id="5e706-176">Give the template a name to indicate that it’s for min/max replenishment.</span></span>  
4. <span data-ttu-id="5e706-177">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="5e706-177">In the Description field, type a value.</span></span>
5. <span data-ttu-id="5e706-178">Selezionare la casella di controllo Consenti domanda ondata per utilizzare le quantità non prenotate.</span><span class="sxs-lookup"><span data-stu-id="5e706-178">Select the Allow wave demand to use unreserved quantities check box.</span></span>
    * <span data-ttu-id="5e706-179">Se si seleziona questa opzione, il rifornimento della domanda di ondata utilizzerà le quantità correlate al rifornimento min/max.</span><span class="sxs-lookup"><span data-stu-id="5e706-179">If you select this option, it enables wave demand replenishment to consume quantities that are related to min/max replenishment.</span></span> <span data-ttu-id="5e706-180">Ad esempio, questo può essere utile se il lavoro di rifornimento min/max non viene elaborato immediatamente, per evitare che il lavoro inutile di rifornimento della domanda venga creato.</span><span class="sxs-lookup"><span data-stu-id="5e706-180">For example, this might be useful if the min/max replenishment work isn’t processed immediately, to avoid unnecessary demand replenishment work from being created.</span></span>  
6. <span data-ttu-id="5e706-181">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="5e706-181">Click New.</span></span>
7. <span data-ttu-id="5e706-182">Immettere un numero nel campo Numero progressivo.</span><span class="sxs-lookup"><span data-stu-id="5e706-182">In the Sequence number field, enter a number.</span></span>
8. <span data-ttu-id="5e706-183">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="5e706-183">In the Description field, type a value.</span></span>
9. <span data-ttu-id="5e706-184">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="5e706-184">In the list, mark the selected row.</span></span>
10. <span data-ttu-id="5e706-185">Nel campo Unità di rifornimento immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="5e706-185">In the Replenishment unit field, enter or select a value.</span></span>
    * <span data-ttu-id="5e706-186">Selezionare, ad esempio, pz.</span><span class="sxs-lookup"><span data-stu-id="5e706-186">For example, select pcs.</span></span> <span data-ttu-id="5e706-187">Questa impostazione è obbligatoria.</span><span class="sxs-lookup"><span data-stu-id="5e706-187">This setting is mandatory.</span></span> <span data-ttu-id="5e706-188">Consente di specificare un'unità di misura diversa per il lavoro di rifornimento rispetto all'unità specificata per i livelli delle scorte minime e massime in questo modello.</span><span class="sxs-lookup"><span data-stu-id="5e706-188">It allows you to specify a different unit of measurement for replenishment work compared to the unit specified for the minimum and maximum stock levels in this template.</span></span>  
11. <span data-ttu-id="5e706-189">Nel campo Modello di lavoro immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="5e706-189">In the Work template field, enter or select a value.</span></span>
    * <span data-ttu-id="5e706-190">Scegliere il modello di lavoro creato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="5e706-190">Choose the work template that you created earlier.</span></span>  
12. <span data-ttu-id="5e706-191">Nel campo Quantità minima immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="5e706-191">In the Minimum quantity field, enter a number.</span></span>
    * <span data-ttu-id="5e706-192">Selezionare la quantità minima per avviare il rifornimento.</span><span class="sxs-lookup"><span data-stu-id="5e706-192">Select the minimum quantity that should trigger the replenishment.</span></span> <span data-ttu-id="5e706-193">Ad esempio, impostarla su 50.</span><span class="sxs-lookup"><span data-stu-id="5e706-193">For example, set this to 50.</span></span> <span data-ttu-id="5e706-194">È possibile lasciarla impostata su zero, se si sta rifornendo un'ubicazione fissa e l'opzione Rifornisci ubicazioni fisse vuote viene impostata su Sì.</span><span class="sxs-lookup"><span data-stu-id="5e706-194">It is possible to leave this set to zero, if you’re replenishing a fixed location and the Replenish empty fixed locations option is set to Yes.</span></span> <span data-ttu-id="5e706-195">Si consiglia inoltre di selezionare l'opzione Rifornisci solo ubicazioni fisse per motivi di prestazioni.</span><span class="sxs-lookup"><span data-stu-id="5e706-195">We also recommend that you select the Replenish only fixed locations option for performance reasons.</span></span>  
13. <span data-ttu-id="5e706-196">Nel campo Quantità massima immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="5e706-196">In the Maximum quantity field, enter a number.</span></span>
    * <span data-ttu-id="5e706-197">Ad esempio, impostarla su 100.</span><span class="sxs-lookup"><span data-stu-id="5e706-197">For example, set this to 100.</span></span>  
14. <span data-ttu-id="5e706-198">Nel campo Unità immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="5e706-198">In the Unit field, enter or select a value.</span></span>
    * <span data-ttu-id="5e706-199">Assegnare l'unità per le quantità minima e massima.</span><span class="sxs-lookup"><span data-stu-id="5e706-199">Assign the unit for the minimum and maximum quantities.</span></span> <span data-ttu-id="5e706-200">Ad esempio, impostarla su pz.</span><span class="sxs-lookup"><span data-stu-id="5e706-200">For example, set this to pcs.</span></span>  
15. <span data-ttu-id="5e706-201">Selezionare la casella di controllo Rifornisci ubicazioni fisse vuote.</span><span class="sxs-lookup"><span data-stu-id="5e706-201">Select the Replenish empty fixed locations check box.</span></span>
    * <span data-ttu-id="5e706-202">Selezionare questa casella di controllo per rifornire le ubicazioni fisse quando sono vuote.</span><span class="sxs-lookup"><span data-stu-id="5e706-202">Select this check box to replenish fixed locations when they are empty.</span></span> <span data-ttu-id="5e706-203">In caso contrario, verranno rifornite solo le ubicazioni in cui è presente una quantità disponibile.</span><span class="sxs-lookup"><span data-stu-id="5e706-203">Otherwise, only the locations where there is a quantity on hand will be replenished.</span></span>  
16. <span data-ttu-id="5e706-204">Selezionare la casella di controllo Rifornisci solo ubicazioni fisse.</span><span class="sxs-lookup"><span data-stu-id="5e706-204">Select the Replenish only fixed locations check box.</span></span>
17. <span data-ttu-id="5e706-205">Fare clic su Seleziona prodotti.</span><span class="sxs-lookup"><span data-stu-id="5e706-205">Click Select products.</span></span>
    * <span data-ttu-id="5e706-206">Si tratta della posizione per definire quali prodotti devono essere riforniti.</span><span class="sxs-lookup"><span data-stu-id="5e706-206">This is the place to define which products should be replenished.</span></span> <span data-ttu-id="5e706-207">Se l'opzione relativa alle ubicazioni di prelievo fisse è selezionata, è necessario definire le ubicazioni anche in questa query.</span><span class="sxs-lookup"><span data-stu-id="5e706-207">If the Fixed picking locations option is selected, you also need to define the locations in this query.</span></span> <span data-ttu-id="5e706-208">Sono disponibili query specifiche sulle varianti così come query specifiche sui prodotti.</span><span class="sxs-lookup"><span data-stu-id="5e706-208">Variant-specific queries are available as well product-specific queries.</span></span>  
18. <span data-ttu-id="5e706-209">Selezionare la riga Articoli.</span><span class="sxs-lookup"><span data-stu-id="5e706-209">Select the Items row.</span></span>
19. <span data-ttu-id="5e706-210">Digitare un valore nel campo Criteri.</span><span class="sxs-lookup"><span data-stu-id="5e706-210">In the Criteria field, type a value.</span></span>
    * <span data-ttu-id="5e706-211">Selezionare gli articoli che devono essere riforniti presso ubicazioni fisse.</span><span class="sxs-lookup"><span data-stu-id="5e706-211">Select the items that should be replenished at the fixed locations.</span></span> <span data-ttu-id="5e706-212">Ad esempio, immettere A* per selezionare tutti i numeri di articolo che iniziano con A.</span><span class="sxs-lookup"><span data-stu-id="5e706-212">For example, type A* to select all item numbers beginning with A.</span></span>  
20. <span data-ttu-id="5e706-213">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="5e706-213">Click Add.</span></span>
    * <span data-ttu-id="5e706-214">Aggiungere l'entità Ubicazione (a meno che non sia già presente) per poter limitare il lavoro di rifornimento alle ubicazioni di prelievo fisse all'interno di un'area specifica del magazzino.</span><span class="sxs-lookup"><span data-stu-id="5e706-214">Add the Location entity (unless it already exists) to be able to restrict the replenishment work to the fixed picking locations within a specific area of the warehouse.</span></span>  
21. <span data-ttu-id="5e706-215">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="5e706-215">In the list, mark the selected row.</span></span>
22. <span data-ttu-id="5e706-216">Impostare il campo Tabella su Ubicazioni.</span><span class="sxs-lookup"><span data-stu-id="5e706-216">Set the Table field to Locations.</span></span>
23. <span data-ttu-id="5e706-217">Nel campo Campo selezionare ID profilo ubicazione.</span><span class="sxs-lookup"><span data-stu-id="5e706-217">In the Field field, select Location profile ID.</span></span>
24. <span data-ttu-id="5e706-218">Nel campo Criteri immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="5e706-218">In the Criteria field, enter or select a value.</span></span>
25. <span data-ttu-id="5e706-219">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="5e706-219">Click OK.</span></span>
26. <span data-ttu-id="5e706-220">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="5e706-220">Close the page.</span></span>

## <a name="set-the-replenishment-process-to-run-as-a-batch-job"></a><span data-ttu-id="5e706-221">Impostare il processo di rifornimento in modo che venga eseguito come processo batch</span><span class="sxs-lookup"><span data-stu-id="5e706-221">Set the replenishment process to run as a batch job</span></span>
1. <span data-ttu-id="5e706-222">Andare a Gestione magazzino > Impostazioni > Rifornimento > Rifornimenti.</span><span class="sxs-lookup"><span data-stu-id="5e706-222">Go to Warehouse management > Replenishment > Replenishments.</span></span>
    * <span data-ttu-id="5e706-223">La pagina Rifornimento consente di impostare il rifornimento da eseguire come processo batch o di richiedere che venga attivato manualmente.</span><span class="sxs-lookup"><span data-stu-id="5e706-223">The Replenishments page allows you to set up replenishment to run as a batch job, or to require that it’s started manually.</span></span>  
2. <span data-ttu-id="5e706-224">Fare clic su Filtro.</span><span class="sxs-lookup"><span data-stu-id="5e706-224">Click Filter.</span></span>
3. <span data-ttu-id="5e706-225">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="5e706-225">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="5e706-226">Nel campo Criteri immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="5e706-226">In the Criteria field, enter or select a value.</span></span>
5. <span data-ttu-id="5e706-227">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="5e706-227">Click OK.</span></span>
6. <span data-ttu-id="5e706-228">Espandere la sezione Esecuzione in background.</span><span class="sxs-lookup"><span data-stu-id="5e706-228">Expand the Run in the background section.</span></span>
7. <span data-ttu-id="5e706-229">Impostare l'opzione Elaborazione batch su Sì.</span><span class="sxs-lookup"><span data-stu-id="5e706-229">Set the Batch processing option to Yes.</span></span>
8. <span data-ttu-id="5e706-230">Fare clic su Ricorrenza.</span><span class="sxs-lookup"><span data-stu-id="5e706-230">Click Recurrence.</span></span>
9. <span data-ttu-id="5e706-231">Selezionare l'opzione Nessuna data di fine.</span><span class="sxs-lookup"><span data-stu-id="5e706-231">Select the No end date option.</span></span>
10. <span data-ttu-id="5e706-232">Impostare il Criterio ricorrenza.</span><span class="sxs-lookup"><span data-stu-id="5e706-232">Set the Recurrance pattern.</span></span>
    * <span data-ttu-id="5e706-233">Selezionare, ad esempio, Giorni.</span><span class="sxs-lookup"><span data-stu-id="5e706-233">For example, select Days.</span></span>  
11. <span data-ttu-id="5e706-234">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="5e706-234">Click OK.</span></span>
12. <span data-ttu-id="5e706-235">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="5e706-235">Click OK.</span></span>

