--- 
title: Sviluppare una struttura e piani di stipendi/retribuzioni
description: "In questa guida attività viene illustrato il processo di creazione di un piano di retribuzione fissa e di abilitazione dei dipendenti a iscriversi al piano in base alle regole di idoneità."
author: kherr75
manager: AnnBe
ms.date: 06/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Operations
ms.search.region: Global
ms.author: kherr
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 3cb6b9d8ee6a3d70731c89d26352eb3869ce3d11
ms.contentlocale: it-it
ms.lasthandoff: 08/29/2017

---
# <a name="develop-salarycompensation-structure-and-plans"></a><span data-ttu-id="ce54b-103">Sviluppare una struttura e piani di stipendi/retribuzioni</span><span class="sxs-lookup"><span data-stu-id="ce54b-103">Develop salary/compensation structure and plans</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="ce54b-104">In questa guida attività viene illustrato il processo di creazione di un piano di retribuzione fissa e di abilitazione dei dipendenti a iscriversi al piano in base alle regole di idoneità.</span><span class="sxs-lookup"><span data-stu-id="ce54b-104">This task guide walks though the process of creating a Fixed compensation plan and enabling employees to be enrolled in the plan through eligibility rules.</span></span> <span data-ttu-id="ce54b-105">La società di dati dimostrativi utilizzata per creare questa attività è USMF e l'attività è destinata ai responsabili retribuzione e benefit.</span><span class="sxs-lookup"><span data-stu-id="ce54b-105">The demo data company used to create this task is USMF and the task is intended for Compensation and Benefits Managers.</span></span>


## <a name="create-fixed-compensation-plan"></a><span data-ttu-id="ce54b-106">Consente di creare un piano di retribuzione fissa</span><span class="sxs-lookup"><span data-stu-id="ce54b-106">Create fixed compensation plan</span></span>
1. <span data-ttu-id="ce54b-107">Fare clic su Gestione retribuzioni.</span><span class="sxs-lookup"><span data-stu-id="ce54b-107">Click Compensation management.</span></span>
2. <span data-ttu-id="ce54b-108">Care clic su Piani di retribuzione fissa.</span><span class="sxs-lookup"><span data-stu-id="ce54b-108">Click Fixed compensation plans.</span></span>
3. <span data-ttu-id="ce54b-109">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="ce54b-109">Click New.</span></span>
4. <span data-ttu-id="ce54b-110">Digitare un valore nel campo Piano.</span><span class="sxs-lookup"><span data-stu-id="ce54b-110">In the Plan field, type a value.</span></span>
5. <span data-ttu-id="ce54b-111">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="ce54b-111">In the Description field, type a value.</span></span>
6. <span data-ttu-id="ce54b-112">Nel campo Data di validità, immettere una data.</span><span class="sxs-lookup"><span data-stu-id="ce54b-112">In the Effective date field, enter a date.</span></span>
7. <span data-ttu-id="ce54b-113">Nel campo Tipo, selezionare se il piano di retribuzione fissa è un piano di tipo Fascia, Scala o Fase.</span><span class="sxs-lookup"><span data-stu-id="ce54b-113">In the Type field, select whether the Fixed compensation plan is a Band, Grade, or Step plan.</span></span>
8. <span data-ttu-id="ce54b-114">La casella di controllo Suggerimento consentito funge da valore predefinito per tutte le azioni aggiunte al piano in un evento di processo.</span><span class="sxs-lookup"><span data-stu-id="ce54b-114">The Recommendation allowed checkbox acts as a default value for any actions added to this plan in a Process event.</span></span>  <span data-ttu-id="ce54b-115">L'autorizzazione di consigli consente di ignorare l'importo di riferimento calcolato quando si elabora la retribuzione.</span><span class="sxs-lookup"><span data-stu-id="ce54b-115">Allowing recommendations enables you to override the calculated guideline amount when processing compensation.</span></span>
9. <span data-ttu-id="ce54b-116">La tolleranza non compresa nell'intervallo consente di specificare la modalità di gestione degli importi di retribuzione che non rientrano nell'intervallo specificato nella struttura retributiva per il livello specificato.</span><span class="sxs-lookup"><span data-stu-id="ce54b-116">The Out of range tolerance allows you to specify how you want to handle compensation amounts that fall outside of the specified compensation structure range for the given level.</span></span>  <span data-ttu-id="ce54b-117">Una tolleranza non compresa nell'intervallo impostata su Nessuno consentirà l'utilizzo di qualsiasi importo di retribuzione.</span><span class="sxs-lookup"><span data-stu-id="ce54b-117">An Out of range tolerance of None will allow any compensation amount to be used.</span></span>  <span data-ttu-id="ce54b-118">Una tolleranza flessibile consentirà di avvisare l'utente se l'importo di retribuzione è inferiore all'importo del punto di riferimento minimo per il livello o superiore all'importo massimo per tale livello.</span><span class="sxs-lookup"><span data-stu-id="ce54b-118">A Soft tolerance will warn the user if the compensation amount is less than the minimum reference point amount for that level, or greater than the maximum amount for that level.</span></span> <span data-ttu-id="ce54b-119">L'utente può ignorare l'avviso e continuare.</span><span class="sxs-lookup"><span data-stu-id="ce54b-119">The user can ignore the warning and continue.</span></span>  <span data-ttu-id="ce54b-120">Nella tolleranza rigida verrà generato un errore se la retribuzione di un dipendente viene stabilita all'esterno dei punti di riferimento minimo e massimo per il livello e la retribuzione del dipendente verrà automaticamente modificata perché rientri nell'intervallo.</span><span class="sxs-lookup"><span data-stu-id="ce54b-120">A Hard tolerance will generate an error if an employee's compensation is set outside of the minimum and maximum reference points for the level and will automatically adjust the employee's compensation to fall within the range.</span></span>
10. <span data-ttu-id="ce54b-121">Il campo Regola di assunzione viene utilizzato quando viene eseguito un evento processo di retribuzione per calcolare la retribuzione di un dipendente.</span><span class="sxs-lookup"><span data-stu-id="ce54b-121">The Hire rule field is used when a compensation Process event is run to calculate an employee's compensation.</span></span>  <span data-ttu-id="ce54b-122">Una regola di assunzione Percentuale consentirà di calcolare un aumento che viene ripartito per la la durata dell'intervallo di tempo in cui il lavoratore è stato assunto nel ciclo di lavorazione.</span><span class="sxs-lookup"><span data-stu-id="ce54b-122">A Hire rule of Percent will calculate an increase that's prorated for the length of the time the worker has been employed in the cycle.</span></span>
11. <span data-ttu-id="ce54b-123">Digitare un valore nel campo Valuta.</span><span class="sxs-lookup"><span data-stu-id="ce54b-123">In the Currency field, type a value.</span></span>
12. <span data-ttu-id="ce54b-124">Nel campo Conversione retribuzione immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="ce54b-124">In the Pay rate conversion field, enter or select a value.</span></span>
13. <span data-ttu-id="ce54b-125">Espandere la sezione Matrice utilizzo range retributivo.</span><span class="sxs-lookup"><span data-stu-id="ce54b-125">Expand the Range utilization matrix section.</span></span>
    * <span data-ttu-id="ce54b-126">Facoltativamente, aggiungere i record di utilizzo del range retributivo per velocizzare il raggiungimento da parte dei dipendenti del punto intermedio e per rallentare il raggiungimento da parte loro del massimo del range.</span><span class="sxs-lookup"><span data-stu-id="ce54b-126">Optionally, add range utilization records to get employees to their midpoint faster and slow them from reaching the maximum of their range.</span></span>  
14. <span data-ttu-id="ce54b-127">In questa fase, è necessario salvare il piano di retribuzione fissa per attivare il pulsante Imposta retribuzione e continuare a definire la struttura di retribuzione per il piano.</span><span class="sxs-lookup"><span data-stu-id="ce54b-127">At this point, you must save the Fixed compensation plan to enable the Set up compensation button and continue defining your compensation structure for the plan.</span></span>  <span data-ttu-id="ce54b-128">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="ce54b-128">Click Save.</span></span>
15. <span data-ttu-id="ce54b-129">Fare clic su Imposta retribuzione.</span><span class="sxs-lookup"><span data-stu-id="ce54b-129">Click Set up compensation.</span></span>
    * <span data-ttu-id="ce54b-130">Esistono tre modi per creare una struttura retributiva.</span><span class="sxs-lookup"><span data-stu-id="ce54b-130">There are three ways to create a compensation structure.</span></span> <span data-ttu-id="ce54b-131">1: Creare una struttura completamente nuova selezionando un set di punti di riferimento e aggiungendo i livelli per creare una struttura personalizzata.</span><span class="sxs-lookup"><span data-stu-id="ce54b-131">1: Create a completely new structure by selecting a set of reference points and adding the levels to create your own structure.</span></span> <span data-ttu-id="ce54b-132">2: Copiare una struttura retributiva da un piano esistente come un punto di inizio e modificarlo per il nuovo piano.</span><span class="sxs-lookup"><span data-stu-id="ce54b-132">2: Copy a compensation structure from an existing plan as a starting point and modify it for the new plan.</span></span> <span data-ttu-id="ce54b-133">3: Selezionare una griglia retributiva esistente.</span><span class="sxs-lookup"><span data-stu-id="ce54b-133">3: Select an existing compensation grid.</span></span> <span data-ttu-id="ce54b-134">Se la griglia retributiva è già utilizzata da un altro piano, tutte le modifiche apportate alla griglia verranno riflesse anche nell'altro piano.</span><span class="sxs-lookup"><span data-stu-id="ce54b-134">If the compensation grid is already being used by another plan, any changes made to the grid will also be reflected in the other plan.</span></span>  
16. <span data-ttu-id="ce54b-135">Selezionare l'opzione Crea nuova matrice da matrice di incremento retributivo esistente.</span><span class="sxs-lookup"><span data-stu-id="ce54b-135">Select the Create new from existing compensation matrix option.</span></span>
17. <span data-ttu-id="ce54b-136">Nel campo Copia da griglia immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="ce54b-136">In the Copy from grid field, enter or select a value.</span></span>
    * <span data-ttu-id="ce54b-137">Facoltativamente è possibile modificare il nome della nuova griglia retributiva che verrà creata come copia della griglia selezionata.</span><span class="sxs-lookup"><span data-stu-id="ce54b-137">Optionally you can change the name of the new compensation grid that will be created as a copy of the selected grid.</span></span>  
18. <span data-ttu-id="ce54b-138">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="ce54b-138">Click OK.</span></span>
19. <span data-ttu-id="ce54b-139">Fare clic su Modifica in massa.</span><span class="sxs-lookup"><span data-stu-id="ce54b-139">Click Mass change.</span></span>
    * <span data-ttu-id="ce54b-140">La modifica in massa consente di gestire gli importi della matrice di incremento retributivo applicando una percentuale o un aumento dell'importo fisso a uno o più livelli e/o punti di riferimento.</span><span class="sxs-lookup"><span data-stu-id="ce54b-140">Mass change allows you to maintain the compensation matrix amounts by applying a percent or flat amount increase to one or more levels and/or reference points.</span></span>  
20. <span data-ttu-id="ce54b-141">Nel campo Importo di rettifica immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="ce54b-141">In the Adjustment amount field, enter a number.</span></span>
21. <span data-ttu-id="ce54b-142">Nell'elenco contrassegnare tutte le righe o rimuoverne il contrassegno.</span><span class="sxs-lookup"><span data-stu-id="ce54b-142">In the list, mark or unmark all rows.</span></span>
22. <span data-ttu-id="ce54b-143">Fare clic su Applica alla griglia.</span><span class="sxs-lookup"><span data-stu-id="ce54b-143">Click Apply to grid.</span></span>
23. <span data-ttu-id="ce54b-144">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="ce54b-144">Close the page.</span></span>
    * <span data-ttu-id="ce54b-145">Una volta che una struttura retributiva è stata creata o selezionata, è possibile selezionare i punti di riferimento da utilizzare come punto di controllo per il piano di retribuzione fissa.</span><span class="sxs-lookup"><span data-stu-id="ce54b-145">Once a compensation structure has been created or selected, you can select which of the reference points should be used as the Control point for the Fixed compensation plan.</span></span>  <span data-ttu-id="ce54b-146">Il punto di controllo viene utilizzato per calcolare il Rapporto di comparazione di un dipendente.</span><span class="sxs-lookup"><span data-stu-id="ce54b-146">The Control point is used to calculate an employee's Compa Ratio.</span></span>  
24. <span data-ttu-id="ce54b-147">Nel campo Punto di controllo immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="ce54b-147">In the Control point field, enter or select a value.</span></span>
25. <span data-ttu-id="ce54b-148">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="ce54b-148">Close the page.</span></span>

## <a name="create-an-eligibility-rule-for-the-new-fixed-compensation-plan"></a><span data-ttu-id="ce54b-149">Crea una regola di idoneità per il nuovo piano di retribuzione fissa.</span><span class="sxs-lookup"><span data-stu-id="ce54b-149">Create an eligibility rule for the new Fixed compensation plan</span></span>
    * <span data-ttu-id="ce54b-150">Il nuovo piano di retribuzione fissa non può essere assegnato a un dipendente fino a quando non sono state definite le regole di idoneità per il piano.</span><span class="sxs-lookup"><span data-stu-id="ce54b-150">The new Fixed compensation plan cannot be assigned to an employee until Eligibility rules have been defined for the plan.</span></span>  
1. <span data-ttu-id="ce54b-151">Fare clic su Regole di idoneità.</span><span class="sxs-lookup"><span data-stu-id="ce54b-151">Click Eligibility rules.</span></span>
2. <span data-ttu-id="ce54b-152">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="ce54b-152">Click New.</span></span>
3. <span data-ttu-id="ce54b-153">Digitare un valore nel campo Idoneità.</span><span class="sxs-lookup"><span data-stu-id="ce54b-153">In the Eligibility field, type a value.</span></span>
4. <span data-ttu-id="ce54b-154">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="ce54b-154">In the Description field, type a value.</span></span>
5. <span data-ttu-id="ce54b-155">Nel campo Data di validità, immettere una data.</span><span class="sxs-lookup"><span data-stu-id="ce54b-155">In the Effective date field, enter a date.</span></span>
    * <span data-ttu-id="ce54b-156">Le regole di idoneità vengono utilizzate sia per i piani di retribuzione fissa che variabile.</span><span class="sxs-lookup"><span data-stu-id="ce54b-156">Eligibility rules are used for both Fixed and Variable compensation plans.</span></span>  <span data-ttu-id="ce54b-157">Nel campo Tipo, selezionare il tipo di piano relativo a tale set di regole.</span><span class="sxs-lookup"><span data-stu-id="ce54b-157">In the Type field, select which type of plan this set of eligibility rules is for.</span></span>  
6. <span data-ttu-id="ce54b-158">Nel campo Piano immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="ce54b-158">In the Plan field, enter or select a value.</span></span>
    * <span data-ttu-id="ce54b-159">Selezionare i criteri che un dipendente deve soddisfare per essere idoneo per il piano di retribuzione.</span><span class="sxs-lookup"><span data-stu-id="ce54b-159">Select the criteria an employee must meet in order to be eligible for the compensation plan.</span></span> <span data-ttu-id="ce54b-160">I criteri possono includere un reparto, un sindacato, una località (paese di retribuzione), una mansione, una funzione, un tipo di mansione o un livello retributivo.</span><span class="sxs-lookup"><span data-stu-id="ce54b-160">Criteria can include a Department, Labor union, Location (Compensation region), Job, Function, Job type, or Compensation level.</span></span> <span data-ttu-id="ce54b-161">Il dipendente deve soddisfare tutti i criteri specificati per essere idoneo per il piano di retribuzione.</span><span class="sxs-lookup"><span data-stu-id="ce54b-161">The employee must meet all specified criteria to be eligible for the compensation plan.</span></span> <span data-ttu-id="ce54b-162">Se non viene specificato alcun criterio, tutti i dipendenti sono idonei per il piano di retribuzione.</span><span class="sxs-lookup"><span data-stu-id="ce54b-162">If no criteria are specified, all employees are eligible for the compensation plan.</span></span> <span data-ttu-id="ce54b-163">Se un dipendente non soddisfa i criteri specificati nella regola di idoneità o non è stata specificata una regola di idoneità per un piano di retribuzione, il piano di retribuzione non verrà visualizzato nella ricerca quando viene creato un record di retribuzione fissa per un dipendente.</span><span class="sxs-lookup"><span data-stu-id="ce54b-163">If an employee does not meet the criteria specified in the eligibility rule, or an eligibility rule has not been specified for a compensation plan, the compensation plan will not appear in the lookup when creating a Fixed compensation record for an employee.</span></span>  
7. <span data-ttu-id="ce54b-164">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="ce54b-164">Close the page.</span></span>
8. <span data-ttu-id="ce54b-165">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="ce54b-165">Close the page.</span></span>

