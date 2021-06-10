---
title: Sviluppare una struttura di retribuzione
description: In questo articolo viene illustrato come creare un piano di retribuzione fissa e iscrivere i dipendenti al piano in base alle regole di idoneità.
author: andreabichsel
ms.date: 02/10/2020
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, HcmCompensationWorkspace, HcmCompFixedPlansPart, HRMCompFixedPlanTable, HRMCompCreateGridDialog, HRCCompGridView, HRMCompEligibility,  HRCCompGrid
audience: Application User
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: abdca618aa544e32b68f4bbf2578afb9ef1a5905
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/18/2021
ms.locfileid: "6052891"
---
# <a name="develop-a-compensation-structure"></a><span data-ttu-id="4f227-103">Sviluppare una struttura di retribuzione</span><span class="sxs-lookup"><span data-stu-id="4f227-103">Develop a compensation structure</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="4f227-104">In questo articolo viene illustrato come creare un piano di retribuzione fissa e iscrivere i dipendenti al piano in base alle regole di idoneità.</span><span class="sxs-lookup"><span data-stu-id="4f227-104">This article walks you through creating a fixed compensation plan and enrolling employees in the plan through eligibility rules.</span></span> <span data-ttu-id="4f227-105">Questo articolo utilizza i dati dimostrativi USMF e si applica ai responsabili retribuzione e benefit.</span><span class="sxs-lookup"><span data-stu-id="4f227-105">This article uses the USMF demo data and applies to Compensation and Benefits Managers.</span></span>

## <a name="create-a-fixed-compensation-plan"></a><span data-ttu-id="4f227-106">Creare un piano di retribuzione fissa</span><span class="sxs-lookup"><span data-stu-id="4f227-106">Create a fixed compensation plan</span></span>

1. <span data-ttu-id="4f227-107">Selezionare **Gestione retribuzioni**.</span><span class="sxs-lookup"><span data-stu-id="4f227-107">Select **Compensation management**.</span></span>

2. <span data-ttu-id="4f227-108">Selezionare **Piani di retribuzione fissa**.</span><span class="sxs-lookup"><span data-stu-id="4f227-108">Select **Fixed compensation plans**.</span></span>

3. <span data-ttu-id="4f227-109">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="4f227-109">Select **New**.</span></span>

4. <span data-ttu-id="4f227-110">Nel campo **Piano** immettere un valore.</span><span class="sxs-lookup"><span data-stu-id="4f227-110">In the **Plan** field, enter a value.</span></span>

5. <span data-ttu-id="4f227-111">Nel campo **Descrizione** immettere un valore.</span><span class="sxs-lookup"><span data-stu-id="4f227-111">In the **Description** field, enter a value.</span></span>

6. <span data-ttu-id="4f227-112">Nel campo **Data di validità**, immettere una data.</span><span class="sxs-lookup"><span data-stu-id="4f227-112">In the **Effective date** field, enter a date.</span></span>

7. <span data-ttu-id="4f227-113">Nel campo **Tipo**, selezionare se il piano di retribuzione fissa è un piano di tipo **Fascia**, **Scala** o **Fase**.</span><span class="sxs-lookup"><span data-stu-id="4f227-113">In the **Type** field, select whether the fixed compensation plan is a **Band**, **Grade**, or **Step** plan.</span></span>

8. <span data-ttu-id="4f227-114">La casella di controllo **Suggerimento consentito** funge da valore predefinito per tutte le azioni aggiunte al piano in un evento di processo.</span><span class="sxs-lookup"><span data-stu-id="4f227-114">The **Recommendation allowed** checkbox acts as a default value for any actions added to this plan in a Process event.</span></span> <span data-ttu-id="4f227-115">L'autorizzazione di consigli consente di ignorare l'importo di riferimento calcolato quando si elabora la retribuzione.</span><span class="sxs-lookup"><span data-stu-id="4f227-115">Allowing recommendations enables you to override the calculated guideline amount when processing compensation.</span></span>

9. <span data-ttu-id="4f227-116">Il campo **Tolleranza non compresa nell'intervallo** consente di specificare la modalità di gestione degli importi di retribuzione che non rientrano nell'intervallo specificato nella struttura retributiva per il livello specificato.</span><span class="sxs-lookup"><span data-stu-id="4f227-116">The **Out of range tolerance** field allows you to specify how you want to handle compensation amounts that fall outside of the specified compensation structure range for the given level.</span></span> <span data-ttu-id="4f227-117">L'impostazione del campo **Tolleranza non compresa nell'intervallo** su **Nessuno** consente di utilizzare qualsiasi importo di retribuzione.</span><span class="sxs-lookup"><span data-stu-id="4f227-117">Setting the **Out of range tolerance** field to **None** allows you to use any compensation amount.</span></span> <span data-ttu-id="4f227-118">Una **tolleranza flessibile** consentirà di avvisare l'utente se l'importo di retribuzione è inferiore all'importo del punto di riferimento minimo per il livello o superiore all'importo massimo per tale livello.</span><span class="sxs-lookup"><span data-stu-id="4f227-118">**Soft tolerance** warns users if the compensation amount is less than the minimum or greater than the maximum reference point amounts for that level.</span></span> <span data-ttu-id="4f227-119">Gli utenti possono ignorare l'avviso e continuare.</span><span class="sxs-lookup"><span data-stu-id="4f227-119">Users can ignore the warning and continue.</span></span> <span data-ttu-id="4f227-120">Nella **tolleranza rigida** viene generato un errore se la retribuzione di un dipendente viene stabilita all'esterno dei punti di riferimento minimo e massimo per il livello e la retribuzione del dipendente verrà automaticamente modificata perché rientri nell'intervallo.</span><span class="sxs-lookup"><span data-stu-id="4f227-120">**Hard tolerance** generates an error if an employee's compensation is outside the minimum and maximum reference points for the level and will automatically adjust the employee's compensation to fall within the range.</span></span>

10. <span data-ttu-id="4f227-121">Il campo **Regola di assunzione** calcola la retribuzione di un dipendente durante un evento di processo.</span><span class="sxs-lookup"><span data-stu-id="4f227-121">The **Hire rule** field calculates an employee's compensation during a process event.</span></span> <span data-ttu-id="4f227-122">Una **regola di assunzione** **Percentuale** consente di calcolare un aumento che viene ripartito per la la durata dell'intervallo di tempo in cui il lavoratore è stato assunto nel ciclo di lavorazione.</span><span class="sxs-lookup"><span data-stu-id="4f227-122">A **Hire rule** of **Percent** calculates an increase that's prorated for the length of the time the worker has been employed in the cycle.</span></span>

11. <span data-ttu-id="4f227-123">Digitare un valore nel campo **Valuta**.</span><span class="sxs-lookup"><span data-stu-id="4f227-123">In the **Currency** field, type a value.</span></span>

12. <span data-ttu-id="4f227-124">Nel campo **Conversione retribuzione** immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="4f227-124">In the **Pay rate conversion** field, enter or select a value.</span></span>

13. <span data-ttu-id="4f227-125">Espandere la sezione **Matrice utilizzo range retributivo**.</span><span class="sxs-lookup"><span data-stu-id="4f227-125">Expand the **Range utilization matrix** section.</span></span> <span data-ttu-id="4f227-126">Facoltativamente, aggiungere i record di utilizzo del range retributivo per velocizzare il raggiungimento da parte dei dipendenti del punto intermedio e per rallentare il raggiungimento da parte loro del massimo del range.</span><span class="sxs-lookup"><span data-stu-id="4f227-126">Optionally, add range utilization records to get employees to their midpoint faster and slow them from reaching the maximum of their range.</span></span>

14. <span data-ttu-id="4f227-127">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="4f227-127">Select **Save**.</span></span> <span data-ttu-id="4f227-128">Questo abilita il pulsante **Imposta retribuzione** per continuare a definire la struttura di retribuzione per il piano.</span><span class="sxs-lookup"><span data-stu-id="4f227-128">This enables the **Set up compensation** button and continue defining your compensation structure for the plan.</span></span>

15. <span data-ttu-id="4f227-129">Selezionare **Imposta retribuzione**.</span><span class="sxs-lookup"><span data-stu-id="4f227-129">Select **Set up compensation**.</span></span> <span data-ttu-id="4f227-130">È possibile creare una struttura di retribuzione utilizzando uno dei tre metodi seguenti:</span><span class="sxs-lookup"><span data-stu-id="4f227-130">You can create a compensation structure by using one of these three methods:</span></span>

    - <span data-ttu-id="4f227-131">Creare una struttura completamente nuova selezionando un set di punti di riferimento e aggiungendo i livelli per creare una struttura personalizzata.</span><span class="sxs-lookup"><span data-stu-id="4f227-131">Create a completely new structure by selecting a set of reference points and adding the levels to create your own structure.</span></span>
    - <span data-ttu-id="4f227-132">Copiare una struttura retributiva da un piano esistente come un punto di inizio e modificarlo per il nuovo piano.</span><span class="sxs-lookup"><span data-stu-id="4f227-132">Copy a compensation structure from an existing plan as a starting point and modify it for the new plan.</span></span>
    - <span data-ttu-id="4f227-133">Selezionare una griglia retributiva esistente.</span><span class="sxs-lookup"><span data-stu-id="4f227-133">Select an existing compensation grid.</span></span> <span data-ttu-id="4f227-134">Se la griglia retributiva è già utilizzata per un altro piano, tutte le modifiche apportate alla griglia vengono riflesse anche nell'altro piano.</span><span class="sxs-lookup"><span data-stu-id="4f227-134">If another plan already uses the compensation grid, the other plan also reflects any changes you make to the grid.</span></span>

16. <span data-ttu-id="4f227-135">Selezionare **Crea nuova matrice da matrice di incremento retributivo esistente**.</span><span class="sxs-lookup"><span data-stu-id="4f227-135">Select **Create new from existing compensation matrix**.</span></span>

17. <span data-ttu-id="4f227-136">Nel campo **Copia da griglia** immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="4f227-136">In the **Copy from grid** field, enter or select a value.</span></span> <span data-ttu-id="4f227-137">Facoltativamente è possibile modificare il nome della nuova griglia retributiva che viene creata come copia della griglia selezionata.</span><span class="sxs-lookup"><span data-stu-id="4f227-137">Optionally, you can change the name of the new compensation grid that you create by copying the selected grid.</span></span>

18. <span data-ttu-id="4f227-138">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="4f227-138">Select **OK**.</span></span>

19. <span data-ttu-id="4f227-139">Selezionare **Modifica in massa**.</span><span class="sxs-lookup"><span data-stu-id="4f227-139">Select **Mass change**.</span></span> <span data-ttu-id="4f227-140">La **modifica in massa** consente di gestire gli importi della matrice di incremento retributivo applicando una percentuale o un aumento dell'importo fisso a uno o più livelli o punti di riferimento.</span><span class="sxs-lookup"><span data-stu-id="4f227-140">**Mass change** allows you to maintain the compensation matrix amounts by applying a percent or flat amount increase to one or more levels or reference points.</span></span>

20. <span data-ttu-id="4f227-141">Nel campo **Importo di rettifica** immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="4f227-141">In the **Adjustment amount** field, enter a number.</span></span>

21. <span data-ttu-id="4f227-142">Nell'elenco contrassegnare tutte le righe o rimuoverne il contrassegno.</span><span class="sxs-lookup"><span data-stu-id="4f227-142">In the list, mark or unmark all rows.</span></span>

22. <span data-ttu-id="4f227-143">Fare clic su **Applica alla griglia**.</span><span class="sxs-lookup"><span data-stu-id="4f227-143">Click **Apply to grid**.</span></span>

23. <span data-ttu-id="4f227-144">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="4f227-144">Close the page.</span></span> <span data-ttu-id="4f227-145">Una volta creata la struttura retributiva, è possibile selezionare i punti di riferimento da utilizzare come punto di controllo per il piano di retribuzione fissa.</span><span class="sxs-lookup"><span data-stu-id="4f227-145">After you create the compensation structure, you can select which of the reference points to use as the control point for the fixed compensation plan.</span></span> <span data-ttu-id="4f227-146">Il punto di controllo viene utilizzato per calcolare il Rapporto di comparazione di un dipendente.</span><span class="sxs-lookup"><span data-stu-id="4f227-146">The control point is used to calculate an employee's Compa Ratio.</span></span>

24. <span data-ttu-id="4f227-147">Nel campo **Punto di controllo** immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="4f227-147">In the **Control point** field, enter or select a value.</span></span>

25. <span data-ttu-id="4f227-148">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="4f227-148">Close the page.</span></span>

## <a name="create-an-eligibility-rule-for-the-fixed-compensation-plan"></a><span data-ttu-id="4f227-149">Creare una regola di idoneità per il piano di retribuzione fissa</span><span class="sxs-lookup"><span data-stu-id="4f227-149">Create an eligibility rule for the fixed compensation plan</span></span>

<span data-ttu-id="4f227-150">Un piano di retribuzione fissa non può essere assegnato a un dipendente fino a quando non sono state definite le regole di idoneità per il piano.</span><span class="sxs-lookup"><span data-stu-id="4f227-150">You can't assign a fixed compensation plan to an employee until you define eligibility rules for the plan.</span></span>  

1. <span data-ttu-id="4f227-151">Selezionare **Regole di idoneità**.</span><span class="sxs-lookup"><span data-stu-id="4f227-151">Select **Eligibility rules**.</span></span>

2. <span data-ttu-id="4f227-152">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="4f227-152">Select **New**.</span></span>

3. <span data-ttu-id="4f227-153">Nel campo **Idoneità** immettere un valore.</span><span class="sxs-lookup"><span data-stu-id="4f227-153">In the **Eligibility** field, enter a value.</span></span>

4. <span data-ttu-id="4f227-154">Nel campo **Descrizione** immettere un valore.</span><span class="sxs-lookup"><span data-stu-id="4f227-154">In the **Description** field, enter a value.</span></span>

5. <span data-ttu-id="4f227-155">Nel campo **Data di validità**, immettere una data.</span><span class="sxs-lookup"><span data-stu-id="4f227-155">In the **Effective date** field, enter a date.</span></span> <span data-ttu-id="4f227-156">Le regole di idoneità vengono utilizzate per i piani di retribuzione fissa e variabile.</span><span class="sxs-lookup"><span data-stu-id="4f227-156">Both fixed and variable compensation plans use eligibility rules.</span></span> <span data-ttu-id="4f227-157">Nel campo **Tipo** selezionare il tipo di piano.</span><span class="sxs-lookup"><span data-stu-id="4f227-157">In the **Type** field, select the type of plan.</span></span>

6. <span data-ttu-id="4f227-158">Nel campo **Piano** immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="4f227-158">In the **Plan** field, enter or select a value.</span></span> <span data-ttu-id="4f227-159">Selezionare i criteri che un dipendente deve soddisfare per essere idoneo per il piano di retribuzione.</span><span class="sxs-lookup"><span data-stu-id="4f227-159">Select the criteria an employee must meet in order to be eligible for the compensation plan.</span></span> <span data-ttu-id="4f227-160">I criteri possono includere:</span><span class="sxs-lookup"><span data-stu-id="4f227-160">Criteria can include:</span></span>

    - <span data-ttu-id="4f227-161">**Reparto**</span><span class="sxs-lookup"><span data-stu-id="4f227-161">**Department**</span></span>
    - <span data-ttu-id="4f227-162">**Sindacato**</span><span class="sxs-lookup"><span data-stu-id="4f227-162">**Labor union**</span></span>
    - <span data-ttu-id="4f227-163">**Ubicazione** (**Paese di retribuzione**)</span><span class="sxs-lookup"><span data-stu-id="4f227-163">**Location** (**Compensation region**)</span></span>
    - <span data-ttu-id="4f227-164">**Mansione**</span><span class="sxs-lookup"><span data-stu-id="4f227-164">**Job**</span></span>
    - <span data-ttu-id="4f227-165">**Funzione**</span><span class="sxs-lookup"><span data-stu-id="4f227-165">**Function**</span></span>
    - <span data-ttu-id="4f227-166">**Tipo di posizione**</span><span class="sxs-lookup"><span data-stu-id="4f227-166">**Job type**</span></span>
    - <span data-ttu-id="4f227-167">**Livello retributivo**</span><span class="sxs-lookup"><span data-stu-id="4f227-167">**Compensation level**</span></span>
    
    <span data-ttu-id="4f227-168">Il dipendente deve soddisfare tutti i criteri specificati per essere idoneo per il piano di retribuzione.</span><span class="sxs-lookup"><span data-stu-id="4f227-168">The employee must meet all specified criteria to be eligible for the compensation plan.</span></span> <span data-ttu-id="4f227-169">Se non viene specificato alcun criterio, tutti i dipendenti sono idonei per il piano di retribuzione.</span><span class="sxs-lookup"><span data-stu-id="4f227-169">If you don't specify any criteria, all employees are eligible for the compensation plan.</span></span> <span data-ttu-id="4f227-170">Se un dipendente non soddisfa i criteri specificati nella regola di idoneità o non è stata specificata una regola di idoneità per un piano di retribuzione, il piano di retribuzione non viene visualizzato nella ricerca quando viene creato un record di retribuzione fissa per un dipendente.</span><span class="sxs-lookup"><span data-stu-id="4f227-170">If an employee doesn't meet the criteria specified in the eligibility rule, or an eligibility rule has not been specified for a compensation plan, the compensation plan won't appear in the lookup when you create a fixed compensation record for an employee.</span></span>

7. <span data-ttu-id="4f227-171">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="4f227-171">Close the page.</span></span>

8. <span data-ttu-id="4f227-172">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="4f227-172">Close the page.</span></span>



[!INCLUDE[footer-include](../includes/footer-banner.md)]