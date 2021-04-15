---
title: Accumula piani di congedo e assenza
description: È possibile accumulare congedi e assenze in Dynamics 365 Human Resources per uno o più dipendenti.
author: andreabichsel
ms.date: 06/01/2020
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
ms.openlocfilehash: 53c089da64f6b5f950a92afb9246454fb9a9686d
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5800263"
---
# <a name="accrue-leave-and-absence-plans"></a><span data-ttu-id="49be5-103">Accumula piani di congedo e assenza</span><span class="sxs-lookup"><span data-stu-id="49be5-103">Accrue leave and absence plans</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="49be5-104">È possibile accumulare congedi e assenze in Dynamics 365 Human Resources per uno o più dipendenti.</span><span class="sxs-lookup"><span data-stu-id="49be5-104">You can accrue leave and absence in Dynamics 365 Human Resources for multiple employees or for an individual.</span></span>

## <a name="accrue-leave-and-absence-for-multiple-employees"></a><span data-ttu-id="49be5-105">Accumulare congedi e assenze per più dipendenti</span><span class="sxs-lookup"><span data-stu-id="49be5-105">Accrue leave and absence for multiple employees</span></span>

1. <span data-ttu-id="49be5-106">Nella pagina **Congedo e assenza**, selezionare la scheda **Collegamenti**.</span><span class="sxs-lookup"><span data-stu-id="49be5-106">On the **Leave and absence** page, select the **Links** tab.</span></span>

2. <span data-ttu-id="49be5-107">Sotto **Gestisci congedo**, selezionare **Accumula piani di congedo e assenza**.</span><span class="sxs-lookup"><span data-stu-id="49be5-107">Under **Manage leave**, select **Accrue leave and absence plans**.</span></span>

3. <span data-ttu-id="49be5-108">Viene visualizzata la finestra di dialogo **Accumula piani di congedo e assenza**.</span><span class="sxs-lookup"><span data-stu-id="49be5-108">The **Accrue leave and absence plans** dialog box appears.</span></span> <span data-ttu-id="49be5-109">In **Accumula a partire da** selezionare **Data odierna** o selezionare **Data personalizzata** e inserire una data personalizzata.</span><span class="sxs-lookup"><span data-stu-id="49be5-109">In **Accrue as of**, either select **Today's date** or select **Custom date** and enter a custom date.</span></span>

4. <span data-ttu-id="49be5-110">Per eseguire gli accumuli per tutte le società, selezionare **Tutte le società**.</span><span class="sxs-lookup"><span data-stu-id="49be5-110">If you want to run accruals for all companies, select **All companies**.</span></span> <span data-ttu-id="49be5-111">Per elaborare gli accumuli per un unico piano di ferie, selezionare **No** per **Tutti i piani**, quindi selezionare un **Piano di congedo**.</span><span class="sxs-lookup"><span data-stu-id="49be5-111">If you want to process accruals for a single leave plan, select **No** for **All plans**, and then select a **Leave plan**.</span></span> <span data-ttu-id="49be5-112">Se si selezionano tutte le società, non è possibile selezionare un singolo piano di congedo.</span><span class="sxs-lookup"><span data-stu-id="49be5-112">If you select all companies, you can't select an individual leave plan.</span></span> 

5. <span data-ttu-id="49be5-113">Se si desidera eseguire il processo di accumulo in background, selezionare **Esecuzione in background** e svolgere le seguenti attività:</span><span class="sxs-lookup"><span data-stu-id="49be5-113">If you want to run the accrual process in the background, select **Run in the background** and do the following tasks:</span></span>

   1. <span data-ttu-id="49be5-114">Immettere informazioni per il processo di accumulo.</span><span class="sxs-lookup"><span data-stu-id="49be5-114">Enter information for the accrual process.</span></span>

   2. <span data-ttu-id="49be5-115">Per impostare un processo ricorrente, selezionare **Ricorrenza**, immettere le informazioni sulla ricorrenza e selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="49be5-115">To set up a recurring job, select **Recurrence**, enter the recurrence information, and the select **OK**.</span></span>

   3. <span data-ttu-id="49be5-116">Per impostare un avviso di processo, selezionare **Avvisi**, selezionare gli avvisi da ricevere, quindi selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="49be5-116">To set up a job alert, select **Alerts**, select the alerts to receive, and then select **OK**.</span></span>

   4. <span data-ttu-id="49be5-117">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="49be5-117">Select **OK**.</span></span> <span data-ttu-id="49be5-118">Il processo di accumulo verrà eseguito con i parametri impostati.</span><span class="sxs-lookup"><span data-stu-id="49be5-118">The accrual process will run with the parameters you set.</span></span>

## <a name="accrue-leave-and-absence-for-an-employee"></a><span data-ttu-id="49be5-119">Accumulare congedi e assenze per un dipendente</span><span class="sxs-lookup"><span data-stu-id="49be5-119">Accrue leave and absence for an employee</span></span>

1. <span data-ttu-id="49be5-120">Nel record del dipendente, selezionare **Congedo**.</span><span class="sxs-lookup"><span data-stu-id="49be5-120">On the employee's record, select **Leave**.</span></span>

2. <span data-ttu-id="49be5-121">Selezionare **Accumula congedi e assenze**.</span><span class="sxs-lookup"><span data-stu-id="49be5-121">Select **Accrue leave and absence**.</span></span>

3. <span data-ttu-id="49be5-122">Viene visualizzata la finestra di dialogo **Accumula piani di congedo e assenza**.</span><span class="sxs-lookup"><span data-stu-id="49be5-122">The **Accrue leave and absence plans** dialog box appears.</span></span> <span data-ttu-id="49be5-123">In **Accumula a partire da** selezionare **Data odierna** o selezionare **Data personalizzata** e inserire una data personalizzata.</span><span class="sxs-lookup"><span data-stu-id="49be5-123">In **Accrue as of**, either select **Today's date** or select **Custom date** and enter a custom date.</span></span>

4. <span data-ttu-id="49be5-124">Per eseguire gli accumuli per tutte le società, selezionare **Tutte le società**.</span><span class="sxs-lookup"><span data-stu-id="49be5-124">If you want to run accruals for all companies, select **All companies**.</span></span> <span data-ttu-id="49be5-125">Per elaborare gli accumuli per un unico piano di ferie, selezionare **No** per **Tutti i piani**, quindi selezionare un **Piano di congedo**.</span><span class="sxs-lookup"><span data-stu-id="49be5-125">If you want to process accruals for a single leave plan, select **No** for **All plans**, and then select a **Leave plan**.</span></span> <span data-ttu-id="49be5-126">Se si selezionano tutte le società, non è possibile selezionare un singolo piano di congedo.</span><span class="sxs-lookup"><span data-stu-id="49be5-126">If you select all companies, you can't select an individual leave plan.</span></span> 

5. <span data-ttu-id="49be5-127">Se si desidera eseguire il processo di accumulo in background, selezionare **Esecuzione in background** e svolgere le seguenti attività:</span><span class="sxs-lookup"><span data-stu-id="49be5-127">If you want to run the accrual process in the background, select **Run in the background** and do the following tasks:</span></span>

   1. <span data-ttu-id="49be5-128">Immettere informazioni per il processo di accumulo.</span><span class="sxs-lookup"><span data-stu-id="49be5-128">Enter information for the accrual process.</span></span>

   2. <span data-ttu-id="49be5-129">Per impostare un processo ricorrente, selezionare **Ricorrenza**, immettere le informazioni sulla ricorrenza e selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="49be5-129">To set up a recurring job, select **Recurrence**, enter the recurrence information, and the select **OK**.</span></span>

   3. <span data-ttu-id="49be5-130">Per impostare un avviso di processo, selezionare **Avvisi**, selezionare gli avvisi da ricevere, quindi selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="49be5-130">To set up a job alert, select **Alerts**, select the alerts to receive, and then select **OK**.</span></span>

   4. <span data-ttu-id="49be5-131">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="49be5-131">Select **OK**.</span></span> <span data-ttu-id="49be5-132">Il processo di accumulo verrà eseguito con i parametri impostati.</span><span class="sxs-lookup"><span data-stu-id="49be5-132">The accrual process will run with the parameters you set.</span></span>

## <a name="delete-leave-and-absence-accruals-for-multiple-employees"></a><span data-ttu-id="49be5-133">Eliminare gli accumuli di congedi e assenze per più dipendenti</span><span class="sxs-lookup"><span data-stu-id="49be5-133">Delete leave and absence accruals for multiple employees</span></span>

<span data-ttu-id="49be5-134">Consente di eliminare i record di accumuli per un piano e un intervallo di date specifici.</span><span class="sxs-lookup"><span data-stu-id="49be5-134">Delete accrual records for a specific plan and date range.</span></span> <span data-ttu-id="49be5-135">Le date di accumulo devono essere quelle odierne o nel futuro.</span><span class="sxs-lookup"><span data-stu-id="49be5-135">Accrual dates must be dated today or in the future.</span></span>

1. <span data-ttu-id="49be5-136">Nella pagina **Congedo e assenza**, selezionare la scheda **Collegamenti**.</span><span class="sxs-lookup"><span data-stu-id="49be5-136">On the **Leave and absence** page, select the **Links** tab.</span></span>

2. <span data-ttu-id="49be5-137">Sotto **Gestisci congedo**, selezionare **Elimina accumuli piani di congedo e assenza**.</span><span class="sxs-lookup"><span data-stu-id="49be5-137">Under **Manage leave**, select **Delete leave and absence plan accruals**.</span></span>

3. <span data-ttu-id="49be5-138">Nella finestra di dialogo **Elimina accumuli piani di congedo e assenza** selezionare **Piano di congedo**.</span><span class="sxs-lookup"><span data-stu-id="49be5-138">In the **Delete leave and absence plan accruals** dialog box, select the **Leave plan**.</span></span> 

4. <span data-ttu-id="49be5-139">Se applicabile, selezionare **Elimina rettifiche saldo**.</span><span class="sxs-lookup"><span data-stu-id="49be5-139">If applicable, choose **Delete balance adjustments**.</span></span>

5. <span data-ttu-id="49be5-140">Immettere o selezionare una **data accumulo congedo**.</span><span class="sxs-lookup"><span data-stu-id="49be5-140">Enter or select a **Leave accrual date**.</span></span> <span data-ttu-id="49be5-141">Questa data deve essere la data odierna o una futura.</span><span class="sxs-lookup"><span data-stu-id="49be5-141">This date has to be either today or in the future.</span></span> 

6. <span data-ttu-id="49be5-142">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="49be5-142">Select **OK**.</span></span> <span data-ttu-id="49be5-143">Il processo di accumulo elimina gli accumuli con i parametri impostati.</span><span class="sxs-lookup"><span data-stu-id="49be5-143">The accrual process will delete accruals with the parameters you set.</span></span> 

## <a name="delete-leave-and-absence-accruals-for-a-single-employee"></a><span data-ttu-id="49be5-144">Eliminare gli accumuli di congedi e assenze per un singolo dipendente</span><span class="sxs-lookup"><span data-stu-id="49be5-144">Delete leave and absence accruals for a single employee</span></span>

1. <span data-ttu-id="49be5-145">Nel record del dipendente, selezionare **Congedo**.</span><span class="sxs-lookup"><span data-stu-id="49be5-145">On the employee's record, select **Leave**.</span></span>

2. <span data-ttu-id="49be5-146">Selezionare **Elimina accumuli piani di congedo e assenza**.</span><span class="sxs-lookup"><span data-stu-id="49be5-146">Select **Delete leave and absence plan accruals**.</span></span>

3. <span data-ttu-id="49be5-147">Nella finestra di dialogo **Elimina accumuli piani di congedo e assenza** selezionare **Piano di congedo**.</span><span class="sxs-lookup"><span data-stu-id="49be5-147">In the **Delete leave and absence plan accruals** dialog box, select **Leave plan**.</span></span> 

4. <span data-ttu-id="49be5-148">Se applicabile, selezionare **Elimina rettifiche saldo**.</span><span class="sxs-lookup"><span data-stu-id="49be5-148">If applicable, choose **Delete balance adjustments**.</span></span>

5. <span data-ttu-id="49be5-149">Immettere o selezionare una **data accumulo congedo**.</span><span class="sxs-lookup"><span data-stu-id="49be5-149">Enter or select a **Leave accrual date**.</span></span> <span data-ttu-id="49be5-150">Questa data deve essere la data odierna o una futura.</span><span class="sxs-lookup"><span data-stu-id="49be5-150">This date must be either today or in the future.</span></span> 

6. <span data-ttu-id="49be5-151">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="49be5-151">Select **OK**.</span></span> <span data-ttu-id="49be5-152">Il processo di accumulo elimina gli accumuli con i parametri impostati.</span><span class="sxs-lookup"><span data-stu-id="49be5-152">The accrual process will delete accruals with the parameters you set.</span></span> 

## <a name="review-leave-accrual-and-deletion-processes"></a><span data-ttu-id="49be5-153">Revisionare i processi di accumulo ed eliminazione dei congedi</span><span class="sxs-lookup"><span data-stu-id="49be5-153">Review leave accrual and deletion processes</span></span>

<span data-ttu-id="49be5-154">**Controllo accumuli congedi** viene visualizzato ogni volta che si esegue o si elimina un accumulo per uno o tutti i dipendenti.</span><span class="sxs-lookup"><span data-stu-id="49be5-154">**Leave accrual audit** displays each time you run or delete an accrual for one or all employees.</span></span> <span data-ttu-id="49be5-155">Vengono visualizzate anche la data e la persona che ha eseguito l'azione.</span><span class="sxs-lookup"><span data-stu-id="49be5-155">The date and person who performed the action also displays.</span></span>

1. <span data-ttu-id="49be5-156">Nella pagina **Congedo e assenza**, selezionare la scheda **Collegamenti**.</span><span class="sxs-lookup"><span data-stu-id="49be5-156">On the **Leave and absence** page, select the **Links** tab.</span></span>

2. <span data-ttu-id="49be5-157">Sotto **Gestisci congedo**, selezionare **Elimina controllo accumuli congedi**.</span><span class="sxs-lookup"><span data-stu-id="49be5-157">Under **Manage leave**, select **Delete leave accrual audit**.</span></span>

## <a name="see-also"></a><span data-ttu-id="49be5-158">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="49be5-158">See also</span></span>

[<span data-ttu-id="49be5-159">Panoramica di congedo e assenza</span><span class="sxs-lookup"><span data-stu-id="49be5-159">Leave and absence overview</span></span>](hr-leave-and-absence-overview.md)</br>
[<span data-ttu-id="49be5-160">Creare un piano di congedo e assenza</span><span class="sxs-lookup"><span data-stu-id="49be5-160">Create a leave and absence plan</span></span>](hr-leave-and-absence-plans.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]