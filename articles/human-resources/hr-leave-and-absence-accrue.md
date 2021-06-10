---
title: Accumula piani di congedo e assenza
description: È possibile accumulare congedi e assenze in Dynamics 365 Human Resources per uno o più dipendenti.
author: andreabichsel
ms.date: 05/04/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LeavePlanFormPart, LeaveAbsenceWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 86ca63b1703faa6f57ed2e5591c89a5e84363481
ms.sourcegitcommit: 318e406b84d43381d450272eb83c5eea9c5cf1c0
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/18/2021
ms.locfileid: "6059475"
---
# <a name="accrue-leave-and-absence-plans"></a><span data-ttu-id="dde2e-103">Accumula piani di congedo e assenza</span><span class="sxs-lookup"><span data-stu-id="dde2e-103">Accrue leave and absence plans</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="dde2e-104">È possibile accumulare congedi e assenze in Dynamics 365 Human Resources per uno o più dipendenti.</span><span class="sxs-lookup"><span data-stu-id="dde2e-104">You can accrue leave and absence in Dynamics 365 Human Resources for multiple employees or for an individual.</span></span>

## <a name="accrue-leave-and-absence-for-multiple-employees"></a><span data-ttu-id="dde2e-105">Accumulare congedi e assenze per più dipendenti</span><span class="sxs-lookup"><span data-stu-id="dde2e-105">Accrue leave and absence for multiple employees</span></span>

1. <span data-ttu-id="dde2e-106">Nella pagina **Congedo e assenza**, selezionare la scheda **Collegamenti**.</span><span class="sxs-lookup"><span data-stu-id="dde2e-106">On the **Leave and absence** page, select the **Links** tab.</span></span>

2. <span data-ttu-id="dde2e-107">Sotto **Gestisci congedo**, selezionare **Accumula piani di congedo e assenza**.</span><span class="sxs-lookup"><span data-stu-id="dde2e-107">Under **Manage leave**, select **Accrue leave and absence plans**.</span></span>

3. <span data-ttu-id="dde2e-108">Viene visualizzata la finestra di dialogo **Accumula piani di congedo e assenza**.</span><span class="sxs-lookup"><span data-stu-id="dde2e-108">The **Accrue leave and absence plans** dialog box appears.</span></span> <span data-ttu-id="dde2e-109">In **Accumula a partire da** selezionare **Data odierna** o selezionare **Data personalizzata** e inserire una data personalizzata.</span><span class="sxs-lookup"><span data-stu-id="dde2e-109">In **Accrue as of**, either select **Today's date** or select **Custom date** and enter a custom date.</span></span>

4. <span data-ttu-id="dde2e-110">Per eseguire gli accumuli per tutte le società, selezionare **Tutte le società**.</span><span class="sxs-lookup"><span data-stu-id="dde2e-110">If you want to run accruals for all companies, select **All companies**.</span></span> <span data-ttu-id="dde2e-111">Per elaborare gli accumuli per un unico piano di ferie, selezionare **No** per **Tutti i piani**, quindi selezionare un **Piano di congedo**.</span><span class="sxs-lookup"><span data-stu-id="dde2e-111">If you want to process accruals for a single leave plan, select **No** for **All plans**, and then select a **Leave plan**.</span></span> <span data-ttu-id="dde2e-112">Se si selezionano tutte le società, non è possibile selezionare un singolo piano di congedo.</span><span class="sxs-lookup"><span data-stu-id="dde2e-112">If you select all companies, you can't select an individual leave plan.</span></span>

5. <span data-ttu-id="dde2e-113">Se si desidera eseguire il processo di accumulo in background, selezionare **Esecuzione in background** e svolgere le seguenti attività:</span><span class="sxs-lookup"><span data-stu-id="dde2e-113">If you want to run the accrual process in the background, select **Run in the background** and do the following tasks:</span></span>

    1. <span data-ttu-id="dde2e-114">Immettere informazioni per il processo di accumulo.</span><span class="sxs-lookup"><span data-stu-id="dde2e-114">Enter information for the accrual process.</span></span>
    2. <span data-ttu-id="dde2e-115">Per impostare un processo ricorrente, selezionare **Ricorrenza**, immettere le informazioni sulla ricorrenza e selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="dde2e-115">To set up a recurring job, select **Recurrence**, enter the recurrence information, and then select **OK**.</span></span>
    3. <span data-ttu-id="dde2e-116">Per impostare un avviso di processo, selezionare **Avvisi**, selezionare gli avvisi da ricevere, quindi selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="dde2e-116">To set up a job alert, select **Alerts**, select the alerts to receive, and then select **OK**.</span></span>
    4. <span data-ttu-id="dde2e-117">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="dde2e-117">Select **OK**.</span></span> <span data-ttu-id="dde2e-118">Il processo di accumulo verrà eseguito con i parametri impostati.</span><span class="sxs-lookup"><span data-stu-id="dde2e-118">The accrual process will run with the parameters you set.</span></span> 

## <a name="accrue-leave-and-absence-for-an-employee"></a><span data-ttu-id="dde2e-119">Accumulare congedi e assenze per un dipendente</span><span class="sxs-lookup"><span data-stu-id="dde2e-119">Accrue leave and absence for an employee</span></span>

1. <span data-ttu-id="dde2e-120">Nel record del dipendente, selezionare **Congedo**.</span><span class="sxs-lookup"><span data-stu-id="dde2e-120">On the employee's record, select **Leave**.</span></span>

2. <span data-ttu-id="dde2e-121">Selezionare **Accumula congedi e assenze**.</span><span class="sxs-lookup"><span data-stu-id="dde2e-121">Select **Accrue leave and absence**.</span></span>

3. <span data-ttu-id="dde2e-122">Viene visualizzata la finestra di dialogo **Accumula piani di congedo e assenza**.</span><span class="sxs-lookup"><span data-stu-id="dde2e-122">The **Accrue leave and absence plans** dialog box appears.</span></span> <span data-ttu-id="dde2e-123">In **Accumula a partire da** selezionare **Data odierna** o selezionare **Data personalizzata** e inserire una data personalizzata.</span><span class="sxs-lookup"><span data-stu-id="dde2e-123">In **Accrue as of**, either select **Today's date** or select **Custom date** and enter a custom date.</span></span>

4. <span data-ttu-id="dde2e-124">Per eseguire gli accumuli per tutte le società, selezionare **Tutte le società**.</span><span class="sxs-lookup"><span data-stu-id="dde2e-124">If you want to run accruals for all companies, select **All companies**.</span></span> <span data-ttu-id="dde2e-125">Per elaborare gli accumuli per un unico piano di ferie, selezionare **No** per **Tutti i piani**, quindi selezionare un **Piano di congedo**.</span><span class="sxs-lookup"><span data-stu-id="dde2e-125">If you want to process accruals for a single leave plan, select **No** for **All plans**, and then select a **Leave plan**.</span></span> <span data-ttu-id="dde2e-126">Se si selezionano tutte le società, non è possibile selezionare un singolo piano di congedo.</span><span class="sxs-lookup"><span data-stu-id="dde2e-126">If you select all companies, you can't select an individual leave plan.</span></span>

5. <span data-ttu-id="dde2e-127">Se si desidera eseguire il processo di accumulo in background, selezionare **Esecuzione in background** e svolgere le seguenti attività:</span><span class="sxs-lookup"><span data-stu-id="dde2e-127">If you want to run the accrual process in the background, select **Run in the background** and do the following tasks:</span></span>

   1. <span data-ttu-id="dde2e-128">Immettere informazioni per il processo di accumulo.</span><span class="sxs-lookup"><span data-stu-id="dde2e-128">Enter information for the accrual process.</span></span>

   2. <span data-ttu-id="dde2e-129">Per impostare un processo ricorrente, selezionare **Ricorrenza**, immettere le informazioni sulla ricorrenza e selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="dde2e-129">To set up a recurring job, select **Recurrence**, enter the recurrence information, and the select **OK**.</span></span>

   3. <span data-ttu-id="dde2e-130">Per impostare un avviso di processo, selezionare **Avvisi**, selezionare gli avvisi da ricevere, quindi selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="dde2e-130">To set up a job alert, select **Alerts**, select the alerts to receive, and then select **OK**.</span></span>

   4. <span data-ttu-id="dde2e-131">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="dde2e-131">Select **OK**.</span></span> <span data-ttu-id="dde2e-132">Il processo di accumulo verrà eseguito con i parametri impostati.</span><span class="sxs-lookup"><span data-stu-id="dde2e-132">The accrual process will run with the parameters you set.</span></span>

## <a name="delete-leave-and-absence-accruals-for-multiple-employees"></a><span data-ttu-id="dde2e-133">Eliminare gli accumuli di congedi e assenze per più dipendenti</span><span class="sxs-lookup"><span data-stu-id="dde2e-133">Delete leave and absence accruals for multiple employees</span></span>

<span data-ttu-id="dde2e-134">Consente di eliminare i record di accumuli per un piano e un intervallo di date specifici.</span><span class="sxs-lookup"><span data-stu-id="dde2e-134">Delete accrual records for a specific plan and date range.</span></span> <span data-ttu-id="dde2e-135">Le date di accumulo devono essere quelle odierne o nel futuro.</span><span class="sxs-lookup"><span data-stu-id="dde2e-135">Accrual dates must be dated today or in the future.</span></span>

1. <span data-ttu-id="dde2e-136">Nella pagina **Congedo e assenza**, selezionare la scheda **Collegamenti**.</span><span class="sxs-lookup"><span data-stu-id="dde2e-136">On the **Leave and absence** page, select the **Links** tab.</span></span>

2. <span data-ttu-id="dde2e-137">Sotto **Gestisci congedo**, selezionare **Elimina accumuli piani di congedo e assenza**.</span><span class="sxs-lookup"><span data-stu-id="dde2e-137">Under **Manage leave**, select **Delete leave and absence plan accruals**.</span></span>

3. <span data-ttu-id="dde2e-138">Nella finestra di dialogo **Elimina accumuli piani di congedo e assenza** selezionare **Piano di congedo**.</span><span class="sxs-lookup"><span data-stu-id="dde2e-138">In the **Delete leave and absence plan accruals** dialog box, select the **Leave plan**.</span></span>

4. <span data-ttu-id="dde2e-139">Se applicabile, selezionare **Elimina rettifiche saldo**.</span><span class="sxs-lookup"><span data-stu-id="dde2e-139">If applicable, choose **Delete balance adjustments**.</span></span>

5. <span data-ttu-id="dde2e-140">Immettere o selezionare una **data accumulo congedo**.</span><span class="sxs-lookup"><span data-stu-id="dde2e-140">Enter or select a **Leave accrual date**.</span></span> <span data-ttu-id="dde2e-141">Questa data deve essere la data odierna o una futura.</span><span class="sxs-lookup"><span data-stu-id="dde2e-141">This date has to be either today or in the future.</span></span>

6. <span data-ttu-id="dde2e-142">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="dde2e-142">Select **OK**.</span></span> <span data-ttu-id="dde2e-143">Il processo di accumulo elimina gli accumuli con i parametri impostati.</span><span class="sxs-lookup"><span data-stu-id="dde2e-143">The accrual process will delete accruals with the parameters you set.</span></span>

## <a name="delete-leave-and-absence-accruals-for-a-single-employee"></a><span data-ttu-id="dde2e-144">Eliminare gli accumuli di congedi e assenze per un singolo dipendente</span><span class="sxs-lookup"><span data-stu-id="dde2e-144">Delete leave and absence accruals for a single employee</span></span>

1. <span data-ttu-id="dde2e-145">Nel record del dipendente, selezionare **Congedo**.</span><span class="sxs-lookup"><span data-stu-id="dde2e-145">On the employee's record, select **Leave**.</span></span>

2. <span data-ttu-id="dde2e-146">Selezionare **Elimina accumuli piani di congedo e assenza**.</span><span class="sxs-lookup"><span data-stu-id="dde2e-146">Select **Delete leave and absence plan accruals**.</span></span>

3. <span data-ttu-id="dde2e-147">Nella finestra di dialogo **Elimina accumuli piani di congedo e assenza** selezionare **Piano di congedo**.</span><span class="sxs-lookup"><span data-stu-id="dde2e-147">In the **Delete leave and absence plan accruals** dialog box, select **Leave plan**.</span></span>

4. <span data-ttu-id="dde2e-148">Se applicabile, selezionare **Elimina rettifiche saldo**.</span><span class="sxs-lookup"><span data-stu-id="dde2e-148">If applicable, choose **Delete balance adjustments**.</span></span>

5. <span data-ttu-id="dde2e-149">Immettere o selezionare una **data accumulo congedo**.</span><span class="sxs-lookup"><span data-stu-id="dde2e-149">Enter or select a **Leave accrual date**.</span></span> <span data-ttu-id="dde2e-150">Questa data deve essere la data odierna o una futura.</span><span class="sxs-lookup"><span data-stu-id="dde2e-150">This date must be either today or in the future.</span></span>

6. <span data-ttu-id="dde2e-151">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="dde2e-151">Select **OK**.</span></span> <span data-ttu-id="dde2e-152">Il processo di accumulo elimina gli accumuli con i parametri impostati.</span><span class="sxs-lookup"><span data-stu-id="dde2e-152">The accrual process will delete accruals with the parameters you set.</span></span>

## <a name="review-leave-accrual-and-deletion-processes"></a><span data-ttu-id="dde2e-153">Revisionare i processi di accumulo ed eliminazione dei congedi</span><span class="sxs-lookup"><span data-stu-id="dde2e-153">Review leave accrual and deletion processes</span></span>

<span data-ttu-id="dde2e-154">**Controllo accumuli congedi** viene visualizzato ogni volta che si esegue o si elimina un accumulo per uno o tutti i dipendenti.</span><span class="sxs-lookup"><span data-stu-id="dde2e-154">**Leave accrual audit** displays each time you run or delete an accrual for one or all employees.</span></span> <span data-ttu-id="dde2e-155">Vengono visualizzate anche la data e la persona che ha eseguito l'azione.</span><span class="sxs-lookup"><span data-stu-id="dde2e-155">The date and person who performed the action also displays.</span></span>

1. <span data-ttu-id="dde2e-156">Nella pagina **Congedo e assenza**, selezionare la scheda **Collegamenti**.</span><span class="sxs-lookup"><span data-stu-id="dde2e-156">On the **Leave and absence** page, select the **Links** tab.</span></span>

2. <span data-ttu-id="dde2e-157">Sotto **Gestisci congedo**, selezionare **Elimina controllo accumuli congedi**.</span><span class="sxs-lookup"><span data-stu-id="dde2e-157">Under **Manage leave**, select **Delete leave accrual audit**.</span></span>

## <a name="preview-leave-accrual-transaction-auditing"></a><span data-ttu-id="dde2e-158">(Anteprima) Controllo transazione accumulo per congedo</span><span class="sxs-lookup"><span data-stu-id="dde2e-158">(Preview) Leave accrual transaction auditing</span></span>

[!include [Preview feature](includes/preview-feature.md)]

<span data-ttu-id="dde2e-159">Questa funzionalità di anteprima consente ai responsabili delle ferie e delle assenze di comprendere le transazioni di accumulo di ferie e assenze relative ai saldi di ferie di un dipendente per un tipo di ferie specifico.</span><span class="sxs-lookup"><span data-stu-id="dde2e-159">This preview feature helps leave and absence managers understand the leave and absence accrual transactions related to an employee’s time off balances for a specific leave type.</span></span>

<span data-ttu-id="dde2e-160">Per visualizzare i dettagli della transazione.</span><span class="sxs-lookup"><span data-stu-id="dde2e-160">To view transaction details:</span></span>

1. <span data-ttu-id="dde2e-161">Nel record del dipendente, selezionare **Congedo**.</span><span class="sxs-lookup"><span data-stu-id="dde2e-161">On the employee's record, select **Leave**.</span></span>

2. <span data-ttu-id="dde2e-162">Seleziona **Visualizza tempo libero**, quindi seleziona la scheda **Saldi**.</span><span class="sxs-lookup"><span data-stu-id="dde2e-162">Select **View time off**, and then select the **Balances** tab.</span></span>

<span data-ttu-id="dde2e-163">Per visualizzare le transazioni di maturazione relative a un tipo di ferie specifico, seleziona il valore numerico nella colonna **Saldo corrente**.</span><span class="sxs-lookup"><span data-stu-id="dde2e-163">To view the accrual transactions related to a specific leave type, select the numerical value in the **Current balance** column.</span></span>

<span data-ttu-id="dde2e-164">Per visualizzare i dettagli della transazione per un importo di accumulo specifico, seleziona una riga di accumulo, apri il pannello **Informazioni correlate** a destra, quindi apri la sezione **Dettagli transazioni**.</span><span class="sxs-lookup"><span data-stu-id="dde2e-164">To view the transaction details for a specific accrual amount, select an accrual row, open the **Related information** panel on the right, and then open the **Transaction details** section.</span></span> <span data-ttu-id="dde2e-165">La sezione Dettagli transazioni mostra:</span><span class="sxs-lookup"><span data-stu-id="dde2e-165">The Transaction details section displays:</span></span>

- <span data-ttu-id="dde2e-166">Modifiche al saldo del tipo di congedo del dipendente</span><span class="sxs-lookup"><span data-stu-id="dde2e-166">Changes to the employee’s leave type balance</span></span>
- <span data-ttu-id="dde2e-167">Dettagli sull'impiego per quel periodo di maturazione specificato</span><span class="sxs-lookup"><span data-stu-id="dde2e-167">Employment details for that specified accrual period</span></span>
- <span data-ttu-id="dde2e-168">Dettagli sul periodo di maturazione e sui tassi</span><span class="sxs-lookup"><span data-stu-id="dde2e-168">Details about the accrual period and rates</span></span>
- <span data-ttu-id="dde2e-169">Eventuali modifiche apportate alle configurazioni del piano di congedo</span><span class="sxs-lookup"><span data-stu-id="dde2e-169">Any changes made to leave plan configurations</span></span>

![Visualizzare il controllo delle transazioni di accumulo dei congedi](media/hr-leave-and-absence-accrue-audit.png)

## <a name="see-also"></a><span data-ttu-id="dde2e-171">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dde2e-171">See also</span></span>

[<span data-ttu-id="dde2e-172">Panoramica di congedo e assenza</span><span class="sxs-lookup"><span data-stu-id="dde2e-172">Leave and absence overview</span></span>](hr-leave-and-absence-overview.md)</br>
[<span data-ttu-id="dde2e-173">Creare un piano di congedo e assenza</span><span class="sxs-lookup"><span data-stu-id="dde2e-173">Create a leave and absence plan</span></span>](hr-leave-and-absence-plans.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
