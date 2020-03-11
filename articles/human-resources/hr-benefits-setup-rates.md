---
title: Configurare i tassi
description: ''
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: a2626e9fc5f15bbdad0f6accf64bc4b211939ed0
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2020
ms.locfileid: "3009600"
---
# <a name="configure-rates"></a><span data-ttu-id="c3fc5-102">Configurare i tassi</span><span class="sxs-lookup"><span data-stu-id="c3fc5-102">Configure rates</span></span>

[!include [banner](includes/preview-feature.md)]

<span data-ttu-id="c3fc5-103">I tassi in Microsoft Dynamics 365 Human Resources definiscono la quantità di datori di lavoro e dipendenti che versano contributi per un benefit.</span><span class="sxs-lookup"><span data-stu-id="c3fc5-103">Rates in Microsoft Dynamics 365 Human Resources define how much employers and employees contribute for a benefit.</span></span> <span data-ttu-id="c3fc5-104">Il valore può essere un importo o crediti flessibili, a seconda della configurazione.</span><span class="sxs-lookup"><span data-stu-id="c3fc5-104">The value can be an amount or flex credits, depending on your configuration.</span></span>

<span data-ttu-id="c3fc5-105">Utilizzare i tassi per determinare la quantità di dipendenti e datori di lavoro che pagano per ogni benefit in base a diversi fattori.</span><span class="sxs-lookup"><span data-stu-id="c3fc5-105">Use rates to determine how much employees and employers pay for each benefit, based on several factors.</span></span> <span data-ttu-id="c3fc5-106">I tassi di copertura diventano effettivi a una determinata data, pertanto è quindi possibile conservare un record cronologico dei tassi.</span><span class="sxs-lookup"><span data-stu-id="c3fc5-106">Coverage rates are date effective, so you can keep a historical record of rates.</span></span> 

## <a name="set-up-rates"></a><span data-ttu-id="c3fc5-107">Impostare i tassi</span><span class="sxs-lookup"><span data-stu-id="c3fc5-107">Set up rates</span></span>

1. <span data-ttu-id="c3fc5-108">Nell'area di lavoro **Gestione benefit**, sotto **Impostazione**, selezionare **Tassi**.</span><span class="sxs-lookup"><span data-stu-id="c3fc5-108">In the **Benefits management** workspace, under **Setup**, select **Rates**.</span></span>

2. <span data-ttu-id="c3fc5-109">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="c3fc5-109">Select **New**.</span></span>

3. <span data-ttu-id="c3fc5-110">Specificare i valori per i seguenti campi:</span><span class="sxs-lookup"><span data-stu-id="c3fc5-110">Specify values for the following fields:</span></span>

   | <span data-ttu-id="c3fc5-111">Campo</span><span class="sxs-lookup"><span data-stu-id="c3fc5-111">Field</span></span> | <span data-ttu-id="c3fc5-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c3fc5-112">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="c3fc5-113">Tasso</span><span class="sxs-lookup"><span data-stu-id="c3fc5-113">Rate</span></span> | <span data-ttu-id="c3fc5-114">Il nome univoco che identifica il tasso di benefit.</span><span class="sxs-lookup"><span data-stu-id="c3fc5-114">A unique name that identifies the benefit rate.</span></span> |
   | <span data-ttu-id="c3fc5-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c3fc5-115">Description</span></span> | <span data-ttu-id="c3fc5-116">Una descrizione del tasso di benefit.</span><span class="sxs-lookup"><span data-stu-id="c3fc5-116">A description of the benefit rate.</span></span> |
   | <span data-ttu-id="c3fc5-117">Valido</span><span class="sxs-lookup"><span data-stu-id="c3fc5-117">Effective</span></span> | <span data-ttu-id="c3fc5-118">La data in cui il tasso entra in vigore.</span><span class="sxs-lookup"><span data-stu-id="c3fc5-118">The date the rate is effective.</span></span> <span data-ttu-id="c3fc5-119">Il valore predefinito è la data di sistema corrente.</span><span class="sxs-lookup"><span data-stu-id="c3fc5-119">The current system date is the default value.</span></span> 
   | <span data-ttu-id="c3fc5-120">Scadenza</span><span class="sxs-lookup"><span data-stu-id="c3fc5-120">Expiration</span></span> | <span data-ttu-id="c3fc5-121">La data di fine del tasso.</span><span class="sxs-lookup"><span data-stu-id="c3fc5-121">The end date of the rate.</span></span> <span data-ttu-id="c3fc5-122">31/12/2154 (che rappresenta mai) è il valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="c3fc5-122">12/31/2154 (which represents never) is the default value.</span></span> |
   | <span data-ttu-id="c3fc5-123">Usa livelli</span><span class="sxs-lookup"><span data-stu-id="c3fc5-123">Use tiers</span></span> | <span data-ttu-id="c3fc5-124">Il livello da utilizzare per il calcolo del tasso di benefit.</span><span class="sxs-lookup"><span data-stu-id="c3fc5-124">The tier to use for the benefit rate calculation.</span></span> <span data-ttu-id="c3fc5-125">Livello singolo per un tasso di benefit a un livello o Doppio livello per un tasso di benefit a due livelli.</span><span class="sxs-lookup"><span data-stu-id="c3fc5-125">Single tier for a one tier benefit rate or Double tier for a two tier benefit rate.</span></span> <span data-ttu-id="c3fc5-126">Un esempio di Doppio livello è un livello basato su sesso e età.</span><span class="sxs-lookup"><span data-stu-id="c3fc5-126">An example of a double tier is a tier based on gender and age.</span></span> |
   | <span data-ttu-id="c3fc5-127">Frequenza pagamenti</span><span class="sxs-lookup"><span data-stu-id="c3fc5-127">Payment frequency</span></span> | <span data-ttu-id="c3fc5-128">La frequenza di pagamento che determina ogni quanto tempo viene versato il tasso di premio benefit al fornitore del benefit.</span><span class="sxs-lookup"><span data-stu-id="c3fc5-128">The payment frequency that determines how often the benefit premium rate is paid to the benefit provider.</span></span> <span data-ttu-id="c3fc5-129">Ad esempio, se la frequenza di pagamento è mensile, il tasso di benefit rappresenta l'importo del pagamento mensile.</span><span class="sxs-lookup"><span data-stu-id="c3fc5-129">For example, if the payment frequency is monthly, then benefit rate represents the monthly payment amount.</span></span> |
   | <span data-ttu-id="c3fc5-130">Calcolo tasso di frequenza pagamenti</span><span class="sxs-lookup"><span data-stu-id="c3fc5-130">Pay frequency rate calculation</span></span> | <span data-ttu-id="c3fc5-131">Il metodo per il calcolo del tasso di frequenza pagamenti: Standard o Annuale.</span><span class="sxs-lookup"><span data-stu-id="c3fc5-131">The method for pay frequency rate calculation: Standard or Annual.</span></span> |
   | <span data-ttu-id="c3fc5-132">Arrotondamento tasso di frequenza pagamenti</span><span class="sxs-lookup"><span data-stu-id="c3fc5-132">Pay frequency rate rounding</span></span> | <span data-ttu-id="c3fc5-133">Il metodo per arrotondare il tasso: Standard o Troncato.</span><span class="sxs-lookup"><span data-stu-id="c3fc5-133">The method for rounding the rate: Standard or Truncated.</span></span> |
   | <span data-ttu-id="c3fc5-134">Importo dipendente non fumatore</span><span class="sxs-lookup"><span data-stu-id="c3fc5-134">Non-smoker employee amount</span></span> | <span data-ttu-id="c3fc5-135">L'importo addebitato dal fornitore del benefit per un dipendente non fumatore.</span><span class="sxs-lookup"><span data-stu-id="c3fc5-135">The amount the benefit provider charges for a nonsmoking employee.</span></span> <span data-ttu-id="c3fc5-136">È l'importo che il datore di lavoro paga al fornitore del benefit e deve essere basato sulla frequenza di pagamento per l'impostazione del tasso.</span><span class="sxs-lookup"><span data-stu-id="c3fc5-136">This is the amount the employer pays to the benefit provider and should be based on the payment frequency for the rate setup.</span></span> |
   | <span data-ttu-id="c3fc5-137">Importo datore di lavoro non fumatore</span><span class="sxs-lookup"><span data-stu-id="c3fc5-137">Non-smoker employer amount</span></span> | <span data-ttu-id="c3fc5-138">L'importo addebitato dal fornitore del benefit per un dipendente non fumatore.</span><span class="sxs-lookup"><span data-stu-id="c3fc5-138">The amount the benefit provider charges for a nonsmoking employee.</span></span> <span data-ttu-id="c3fc5-139">È l'importo che il datore di lavoro paga al fornitore del benefit e deve essere basato sulla frequenza di pagamento per l'impostazione del tasso.</span><span class="sxs-lookup"><span data-stu-id="c3fc5-139">This is the amount the employer pays to the benefit provider and it should be based on the payment frequency for the rate setup.</span></span> |
   | <span data-ttu-id="c3fc5-140">Importo dipendente fumatore</span><span class="sxs-lookup"><span data-stu-id="c3fc5-140">Smoker employee amount</span></span> | <span data-ttu-id="c3fc5-141">L'importo addebitato dal fornitore del benefit per un dipendente fumatore.</span><span class="sxs-lookup"><span data-stu-id="c3fc5-141">The amount the benefit provider charges for an employee who smokes.</span></span> <span data-ttu-id="c3fc5-142">È l'importo che il datore di lavoro paga al fornitore del benefit e deve essere basato sulla frequenza di pagamento per l'impostazione del tasso.</span><span class="sxs-lookup"><span data-stu-id="c3fc5-142">This is the amount the employer pays to the benefit provider and should be based on the payment frequency for the rate setup.</span></span> |
   | <span data-ttu-id="c3fc5-143">Importo datore di lavoro fumatore</span><span class="sxs-lookup"><span data-stu-id="c3fc5-143">Smoker employer amount</span></span> | <span data-ttu-id="c3fc5-144">L'importo addebitato dal fornitore del benefit per un dipendente fumatore.</span><span class="sxs-lookup"><span data-stu-id="c3fc5-144">The amount the benefit provider charges for an employee who smokes.</span></span> <span data-ttu-id="c3fc5-145">È l'importo che il datore di lavoro paga al fornitore del benefit e deve essere basato sulla frequenza di pagamento per l'impostazione del tasso.</span><span class="sxs-lookup"><span data-stu-id="c3fc5-145">This is the amount the employer pays to the benefit provider and should be based on the payment frequency for the rate setup.</span></span> |
   | <span data-ttu-id="c3fc5-146">Importo amministrativo</span><span class="sxs-lookup"><span data-stu-id="c3fc5-146">Administrative amount</span></span> | <span data-ttu-id="c3fc5-147">L'importo amministrativo addebitato da un amministratore di terze parti.</span><span class="sxs-lookup"><span data-stu-id="c3fc5-147">The administrative amount charged by a third party administrator.</span></span> <span data-ttu-id="c3fc5-148">È l'importo che il datore di lavoro paga all'amministratore di terze parti e deve essere basato sulla frequenza di pagamento per l'impostazione del tasso.</span><span class="sxs-lookup"><span data-stu-id="c3fc5-148">This is the amount that the employer pays to the third party administrator and it should be based the payment frequency for the rate setup.</span></span> |
   | <span data-ttu-id="c3fc5-149">Tasso crediti flessibili</span><span class="sxs-lookup"><span data-stu-id="c3fc5-149">Flex credit rate</span></span> | <span data-ttu-id="c3fc5-150">Il costo del benefit in numero di crediti flessibili.</span><span class="sxs-lookup"><span data-stu-id="c3fc5-150">The number of flex credits the benefit costs.</span></span> <span data-ttu-id="c3fc5-151">È applicabile solo ai tassi per piani di benefit associati a programmi di crediti flessibili.</span><span class="sxs-lookup"><span data-stu-id="c3fc5-151">This is only applicable to rates that are for benefit plans that are associated with flex credit programs.</span></span> <span data-ttu-id="c3fc5-152">Se si utilizzano tassi a livelli, il tasso di credito flessibile è definito in Azioni> Tassi a livelli.</span><span class="sxs-lookup"><span data-stu-id="c3fc5-152">If you use tier rates, the flex credit rate is defined in Actions > Tier rates.</span></span> |
   | <span data-ttu-id="c3fc5-153">Data di validità modifica</span><span class="sxs-lookup"><span data-stu-id="c3fc5-153">Change effective date</span></span> | <span data-ttu-id="c3fc5-154">La data in cui la modifica al tasso di benefit diventa effettiva.</span><span class="sxs-lookup"><span data-stu-id="c3fc5-154">The date when the benefit rate change takes effect.</span></span> <span data-ttu-id="c3fc5-155">Il sistema modificherà automaticamente il tasso di benefit e aggiornerà tutti i piani di benefit ad esso associati purché si esegua l'elaborazione dell'aggiornamento delle modifiche al tasso.</span><span class="sxs-lookup"><span data-stu-id="c3fc5-155">The system will automatically change the benefit rate and update all benefit plans associated with this rate, as long as you run Rate change update processing.</span></span> <span data-ttu-id="c3fc5-156">Non è necessario impostare questa data a meno che si desideri che il sistema aggiorni automaticamente i piani di benefit per i dipendenti in base a questo tasso.</span><span class="sxs-lookup"><span data-stu-id="c3fc5-156">You should not set this date unless you want the system to automatically update the employee benefit plans based on this rate.</span></span> <span data-ttu-id="c3fc5-157">Ciò è in genere riservato all'elaborazione automatica delle modifiche al tasso future.</span><span class="sxs-lookup"><span data-stu-id="c3fc5-157">This is normally reserved to automatic future rate change processing.</span></span> <span data-ttu-id="c3fc5-158">La data di entrata in vigore della modifica deve essere compresa tra la data di entrata in vigore e quella di scadenza del tasso di benefit.</span><span class="sxs-lookup"><span data-stu-id="c3fc5-158">The change effective date must be within the benefit rate effective and expiration dates.</span></span> |
   | <span data-ttu-id="c3fc5-159">Modifica tasso completata</span><span class="sxs-lookup"><span data-stu-id="c3fc5-159">Rate change completed</span></span> | <span data-ttu-id="c3fc5-160">La casella di controllo Modifiche tasso completate verrà selezionata automaticamente una volta completate le modifiche al tasso di benefit mediante l'elaborazione dell'aggiornamento delle modifiche al tasso.</span><span class="sxs-lookup"><span data-stu-id="c3fc5-160">The Rate change completed check box will be automatically selected after the benefit rate changes have been completed by the Rate change update processing.</span></span> |

4. <span data-ttu-id="c3fc5-161">Per tenere traccia e gestire le modifiche all'impostazione del tasso di benefit, selezionare **Azioni**, quindi selezionare **Gestisci versioni**.</span><span class="sxs-lookup"><span data-stu-id="c3fc5-161">To track and maintain changes to the benefit rate setup, select **Actions**, and then select **Maintain versions**.</span></span>

5. <span data-ttu-id="c3fc5-162">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="c3fc5-162">Select **Save**.</span></span> 

## <a name="set-up-tier-rates"></a><span data-ttu-id="c3fc5-163">Impostare tassi a livelli</span><span class="sxs-lookup"><span data-stu-id="c3fc5-163">Set up tier rates</span></span>

<span data-ttu-id="c3fc5-164">È possibile utilizzare tassi a livelli nell'impostazione del tasso se questo varia in base a vari fattori.</span><span class="sxs-lookup"><span data-stu-id="c3fc5-164">You can use tier rates in your rate setup if the rate varies depending on various factors.</span></span> <span data-ttu-id="c3fc5-165">Ad esempio, si potrebbero configurare tassi a livelli per indicare che se l'età è fino a 34,99 anni, l'importo per non fumatori è 2.</span><span class="sxs-lookup"><span data-stu-id="c3fc5-165">For example, you could configure tier rates to say that if your age is up to 34.99, then the non-smoker amount is 2.</span></span> <span data-ttu-id="c3fc5-166">Se l'età è fino a 39,99, l'importo per non fumatori è 3.</span><span class="sxs-lookup"><span data-stu-id="c3fc5-166">If your age is up to 39.99, then the non-smoker amount is 3.</span></span>

<span data-ttu-id="c3fc5-167">È anche possibile usare doppi livelli.</span><span class="sxs-lookup"><span data-stu-id="c3fc5-167">You can also use double tiers.</span></span> <span data-ttu-id="c3fc5-168">Se si seleziona **Doppio livello** per il valore **Usa livelli** nel modulo **Impostazione tasso**, è possibile definire i tassi in base a due dimensioni.</span><span class="sxs-lookup"><span data-stu-id="c3fc5-168">If you select **Double tier** for the **Use tiers** value on the **Rate setup** form, you can define rates based on two dimensions.</span></span> <span data-ttu-id="c3fc5-169">Ad esempio, si potrebbe configurare un sistema a doppio livello per indicare che per un maschio di età fino a 34,99 anni, l'importo per non fumatori è 2.</span><span class="sxs-lookup"><span data-stu-id="c3fc5-169">For example, you could configure a double tire system to say that if you are male and your age is up to 34.99, then the non-smoker amount is 2.</span></span> <span data-ttu-id="c3fc5-170">Per un maschio di età fino a 39,99, l'importo per non fumatori è 3.</span><span class="sxs-lookup"><span data-stu-id="c3fc5-170">If you are male and your age is up to 39.99, then the non-smoker amount is 3.</span></span> <span data-ttu-id="c3fc5-171">Per una femmina di età fino a 34,99, l'importo per non fumatori è 1,8.</span><span class="sxs-lookup"><span data-stu-id="c3fc5-171">If you are female and your age is up to 34.99, then the non-smoker amount is 1.8.</span></span> <span data-ttu-id="c3fc5-172">Per una femmina di età fino a 39,99, l'importo per non fumatori è 2,8.</span><span class="sxs-lookup"><span data-stu-id="c3fc5-172">If you are female and your age is up to 39.99, then the non-smoker amount is 2.8.</span></span>

1. <span data-ttu-id="c3fc5-173">Nell'area di lavoro **Gestione benefit**, sotto **Impostazione**, selezionare **Tassi**.</span><span class="sxs-lookup"><span data-stu-id="c3fc5-173">In the **Benefits management** workspace, under **Setup**, select **Rates**.</span></span>

2. <span data-ttu-id="c3fc5-174">Selezionare uno o più tassi dall'elenco, selezionare **Azioni**, quindi selezionare **Tassi a livelli**.</span><span class="sxs-lookup"><span data-stu-id="c3fc5-174">Select one or more rates from the list, select **Actions**, and then select **Tier rates**.</span></span>

3. <span data-ttu-id="c3fc5-175">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="c3fc5-175">Select **New**.</span></span>

3. <span data-ttu-id="c3fc5-176">Specificare i valori per i seguenti campi:</span><span class="sxs-lookup"><span data-stu-id="c3fc5-176">Specify values for the following fields:</span></span>

   | <span data-ttu-id="c3fc5-177">Campo</span><span class="sxs-lookup"><span data-stu-id="c3fc5-177">Field</span></span> | <span data-ttu-id="c3fc5-178">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c3fc5-178">Description</span></span> |
   | --- | --- | 
   | <span data-ttu-id="c3fc5-179">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c3fc5-179">Description</span></span> | <span data-ttu-id="c3fc5-180">Il valore del campo Descrizione verrà applicato dalla descrizione nel record Impostazione tasso.</span><span class="sxs-lookup"><span data-stu-id="c3fc5-180">The Description field value will be applied from the description in the rate setup record.</span></span> <span data-ttu-id="c3fc5-181">Ciò consente di identificare a quale impostazione sono collegati i tassi a livello.</span><span class="sxs-lookup"><span data-stu-id="c3fc5-181">This helps you identify which rate setup the tier rates are linked to.</span></span> |
   | <span data-ttu-id="c3fc5-182">Codice livello</span><span class="sxs-lookup"><span data-stu-id="c3fc5-182">Tier code</span></span> | <span data-ttu-id="c3fc5-183">Selezionare un codice di livello.</span><span class="sxs-lookup"><span data-stu-id="c3fc5-183">Select a tier code.</span></span> <span data-ttu-id="c3fc5-184">I codici di livello sono definiti nel modulo Codici di livello.</span><span class="sxs-lookup"><span data-stu-id="c3fc5-184">Tier codes are defined in the Tier codes form.</span></span> <span data-ttu-id="c3fc5-185">Il sistema visualizzerà automaticamente la descrizione del codice di livello nella griglia a sinistra.</span><span class="sxs-lookup"><span data-stu-id="c3fc5-185">The system will automatically display the description of the tier code in the grid to the left.</span></span> |
   | <span data-ttu-id="c3fc5-186">Tipo di livello</span><span class="sxs-lookup"><span data-stu-id="c3fc5-186">Tier type</span></span> | <span data-ttu-id="c3fc5-187">Specifica quale campo deve essere utilizzato come criterio di selezione per il processo di calcolo del tasso a livelli.</span><span class="sxs-lookup"><span data-stu-id="c3fc5-187">Specifies what field should be used as a selection criterion for the tier rate calculation process.</span></span> <span data-ttu-id="c3fc5-188">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="c3fc5-188">For example:</span></span></br></br><ul><li><span data-ttu-id="c3fc5-189">Se si utilizza Età, il sistema utilizzerà la data di nascita del dipendente nel processo di calcolo del tasso di benefit.</span><span class="sxs-lookup"><span data-stu-id="c3fc5-189">If Age is used, the system will use the employee’s birthdate in the benefit rate calculation process.</span></span></li><li><span data-ttu-id="c3fc5-190">Se si utilizza Retribuzione, il sistema utilizzerà la retribuzione benefit del dipendente nel processo di calcolo del tasso di benefit.</span><span class="sxs-lookup"><span data-stu-id="c3fc5-190">If Salary is used, the system will use the employee’s annual benefit salary in the benefit rate calculation process.</span></span></li><li><span data-ttu-id="c3fc5-191">Se si utilizza Tipo di mansione, il sistema utilizzerà il record della posizione attiva corrente del dipendente per determinare il tipo di mansione in base al record di mansione collegato alla posizione.</span><span class="sxs-lookup"><span data-stu-id="c3fc5-191">If Job type is used, the system will use the employee’s current active position record to determine the job type by the job record linked to the position.</span></span></li></ul></br></br><span data-ttu-id="c3fc5-192">I tipi di livelli sono Età, Retribuzione, Fisico, Sesso, Equivalente a tempo pieno, Tipo di mansione, Paese di retribuzione e Livello.</span><span class="sxs-lookup"><span data-stu-id="c3fc5-192">The tier types are Age, Salary, Physical, Gender, Full time equivalent, Job type, Compensation region, and Level.</span></span> | 
   | <span data-ttu-id="c3fc5-193">Livello</span><span class="sxs-lookup"><span data-stu-id="c3fc5-193">Level</span></span> | <span data-ttu-id="c3fc5-194">Il valore da utilizzare con il tipo di livello durante il processo di calcolo del tasso di benefit.</span><span class="sxs-lookup"><span data-stu-id="c3fc5-194">The value to use with the tier type during benefit rate calculation process.</span></span> <span data-ttu-id="c3fc5-195">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="c3fc5-195">For example:</span></span></br></br><ul><li><span data-ttu-id="c3fc5-196">Se il tipo di livello è Età, sarebbe il valore dell'età.</span><span class="sxs-lookup"><span data-stu-id="c3fc5-196">If the tier type is Age, this would be the age value.</span></span></li><li><span data-ttu-id="c3fc5-197">Se il tipo di livello è Retribuzione, sarebbe l'importo della retribuzione.</span><span class="sxs-lookup"><span data-stu-id="c3fc5-197">If the tier type is Salary, this would be the salary amount.</span></span></li><li> <span data-ttu-id="c3fc5-198">Se il tipo di livello è Tipo di mansione, sarebbe il tipo di mansione.</span><span class="sxs-lookup"><span data-stu-id="c3fc5-198">If the tier type is Job type, this would be the job type.</span></span></li></ul></br></br><span data-ttu-id="c3fc5-199">Con un tipo di livello Età o Retribuzione, il sistema utilizza un approccio crescente durante la selezione del tasso a livelli, il che significa che il valore nel campo Livello rappresenta il limite inferiore del livello.</span><span class="sxs-lookup"><span data-stu-id="c3fc5-199">With a tier type of Age or Salary, the system uses an ascending approach during tier rate selection, meaning the value in the Level field represents the lower bound of the tier.</span></span> <span data-ttu-id="c3fc5-200">Con il tipo di livello Tipo di lavoro, il sistema utilizza un approccio di corrispondenza esatta durante la selezione del tasso a livelli.</span><span class="sxs-lookup"><span data-stu-id="c3fc5-200">With a tier type of Job type, the system uses an exact match approach during tier rate selection.</span></span> |
   | <span data-ttu-id="c3fc5-201">Tipo di calcolo</span><span class="sxs-lookup"><span data-stu-id="c3fc5-201">Calculation type</span></span> | <span data-ttu-id="c3fc5-202">Specifica come utilizzare l'importo nel campo Importo di calcolo e quale calcolo matematico eseguire se necessario.</span><span class="sxs-lookup"><span data-stu-id="c3fc5-202">Specifies how to use the amount in the calculation amount field and what math calculation to perform if necessary.</span></span> <span data-ttu-id="c3fc5-203">Se il tipo di calcolo è un importo fisso, il sistema utilizza i campi Importo così come sono.</span><span class="sxs-lookup"><span data-stu-id="c3fc5-203">If the calculation type is a flat amount, the system uses the amount fields as is.</span></span> <span data-ttu-id="c3fc5-204">Se il tipo di calcolo è per importo della retribuzione o della copertura in $, il sistema utilizza l'importo di calcolo e la direzione di calcolo nel calcolo matematico.</span><span class="sxs-lookup"><span data-stu-id="c3fc5-204">If the calculation type is per $ amount of salary or coverage, the system uses the calculation amount and calculation direction in its math calculation.</span></span></br></br><span data-ttu-id="c3fc5-205">Se il tipo di calcolo è per importo della retribuzione in $, il sistema utilizzerà la seguente equazione matematica:</span><span class="sxs-lookup"><span data-stu-id="c3fc5-205">If the calculation type is per $ amount of salary, the system will use the following math equation:</span></span></br></br><span data-ttu-id="c3fc5-206">Retribuzione benefit annua divisa per l'importo di calcolo (arrotondato per eccesso o per difetto) moltiplicata per gli importi per fumatore o non fumatore per dipendente o datore di lavoro.</span><span class="sxs-lookup"><span data-stu-id="c3fc5-206">Annual benefit salary divided by Calculation amount (rounded up or down) times the amounts for smoker or non-smoker for employee or employer.</span></span></br></br><span data-ttu-id="c3fc5-207">Se il tipo di calcolo è per importo della copertura in $, il sistema utilizzerà la seguente equazione matematica:</span><span class="sxs-lookup"><span data-stu-id="c3fc5-207">If the calculation type is per $ amount of coverage, the system will use the following math equation:</span></span></br></br><span data-ttu-id="c3fc5-208">Importo della copertura diviso per l'importo di calcolo (arrotondato per eccesso o per difetto) moltiplicato per gli importi per fumatore o non fumatore per dipendente o datore di lavoro.</span><span class="sxs-lookup"><span data-stu-id="c3fc5-208">Coverage amount divided by Calculation amount (rounded up or down) times the amounts for smoker or non-smoker for employee or employer.)</span></span></br></br><span data-ttu-id="c3fc5-209">In entrambi i calcoli, la direzione di calcolo viene utilizzata per determinare se arrotondare per eccesso o per difetto la retribuzione benefit annua o l'importo della copertura diviso per l'importo di calcolo.</span><span class="sxs-lookup"><span data-stu-id="c3fc5-209">In both calculations, the Calculation direction is used to determine whether to round the Annual benefit salary or Coverage amount divided by Calculation amount up or down.</span></span> |
   | <span data-ttu-id="c3fc5-210">Importo di calcolo</span><span class="sxs-lookup"><span data-stu-id="c3fc5-210">Calculation amount</span></span> | <span data-ttu-id="c3fc5-211">L'importo da utilizzare durante il processo di calcolo del tasso di benefit.</span><span class="sxs-lookup"><span data-stu-id="c3fc5-211">The amount to use during the benefit rate calculation process.</span></span> <span data-ttu-id="c3fc5-212">Questo importo sarà il divisore durante il calcolo matematico del tasso a livelli.</span><span class="sxs-lookup"><span data-stu-id="c3fc5-212">This amount will be the divisor during the math calculation of the tier rate.</span></span> |
   | <span data-ttu-id="c3fc5-213">Direzione di calcolo</span><span class="sxs-lookup"><span data-stu-id="c3fc5-213">Calculation direction</span></span> | <span data-ttu-id="c3fc5-214">La direzione (Aumenta o Diminuisci) in base alla quale l'importo del risultato calcolato deve essere arrotondato.</span><span class="sxs-lookup"><span data-stu-id="c3fc5-214">The direction (Increase or Decrease) that the calculated result amount should be rounded.</span></span> <span data-ttu-id="c3fc5-215">Il sistema supporta tre direzioni di calcolo: Vuoto (metodo esatto), Aumenta e Diminuisci.</span><span class="sxs-lookup"><span data-stu-id="c3fc5-215">The system supports three calculation directions: Blank (exact method), Increase, and Decrease.</span></span></br></br><ul><li><span data-ttu-id="c3fc5-216">Se vuoto, il sistema utilizzerà il calcolo esatto dell'importo della retribuzione/copertura diviso per l'importo di calcolo.</span><span class="sxs-lookup"><span data-stu-id="c3fc5-216">If blank, the system will use the exact calculation of the salary/coverage amount divided by the calculation amount.</span></span> <span data-ttu-id="c3fc5-217">Se questo valore ha una frazione, il sistema lo utilizzerà nel calcolo.</span><span class="sxs-lookup"><span data-stu-id="c3fc5-217">If this value has a fraction, then the system will use this in its calculation.</span></span></li><li><span data-ttu-id="c3fc5-218">Se la direzione è Aumenta, il sistema aumenterà il calcolo matematico dell'importo della retribuzione/copertura diviso per l'importo di calcolo all'intero successivo, il che significa che 12,25 aumenterà a 13.</span><span class="sxs-lookup"><span data-stu-id="c3fc5-218">If Increase, the system will increase the math calculation of the salary/coverage amount divided by the calculation amount to the next integer, which means 12.25 would increase to 13.</span></span></li><li><span data-ttu-id="c3fc5-219">Se la direzione è Diminuisci, il sistema diminuirà il calcolo matematico dell'importo della retribuzione/copertura diviso per l'importo di calcolo all'intero corrente, il che significa che 12,25 diminuirà a 12.</span><span class="sxs-lookup"><span data-stu-id="c3fc5-219">If Decrease, the system will decrease the math calculation of the salary/coverage amount divided by the calculation amount to the current integer, which means 12.25 would decrease to 12.</span></span></li></ul> |
   | <span data-ttu-id="c3fc5-220">Importo dipendente non fumatore</span><span class="sxs-lookup"><span data-stu-id="c3fc5-220">Non-smoker employee amount</span></span> | <span data-ttu-id="c3fc5-221">L'importo addebitato dal fornitore del benefit per un dipendente non fumatore.</span><span class="sxs-lookup"><span data-stu-id="c3fc5-221">The amount a benefit provider charges for a nonsmoking employee.</span></span> <span data-ttu-id="c3fc5-222">È l'importo che il datore di lavoro paga al fornitore del benefit e deve essere basato sulla frequenza di pagamento per l'impostazione del tasso.</span><span class="sxs-lookup"><span data-stu-id="c3fc5-222">This is the amount the employer pays to the benefit provider and it should be based on the payment frequency for the rate setup.</span></span> |
   | <span data-ttu-id="c3fc5-223">Importo datore di lavoro non fumatore</span><span class="sxs-lookup"><span data-stu-id="c3fc5-223">Non-smoker employer amount</span></span> | <span data-ttu-id="c3fc5-224">L'importo addebitato dal fornitore del benefit per un dipendente non fumatore.</span><span class="sxs-lookup"><span data-stu-id="c3fc5-224">The amount a benefit provider charges for a nonsmoking employee.</span></span> <span data-ttu-id="c3fc5-225">È l'importo che il datore di lavoro paga al fornitore del benefit e deve essere basato sulla frequenza di pagamento per l'impostazione del tasso.</span><span class="sxs-lookup"><span data-stu-id="c3fc5-225">This is the amount the employer pays to the benefit provider and it should be based on the payment frequency for the rate setup.</span></span> |
   | <span data-ttu-id="c3fc5-226">Importo dipendente fumatore</span><span class="sxs-lookup"><span data-stu-id="c3fc5-226">Smoker employee amount</span></span> | <span data-ttu-id="c3fc5-227">L'importo addebitato dal fornitore del benefit per un dipendente non fumatore.</span><span class="sxs-lookup"><span data-stu-id="c3fc5-227">The amount a benefit provider charges for a nonsmoking employee.</span></span> <span data-ttu-id="c3fc5-228">È l'importo che il datore di lavoro paga al fornitore del benefit e deve essere basato sulla frequenza di pagamento per l'impostazione del tasso.</span><span class="sxs-lookup"><span data-stu-id="c3fc5-228">This is the amount the employer pays to the benefit provider and it should be based on the payment frequency for the rate setup.</span></span> |
   | <span data-ttu-id="c3fc5-229">Importo datore di lavoro fumatore</span><span class="sxs-lookup"><span data-stu-id="c3fc5-229">Smoker employer amount</span></span> | <span data-ttu-id="c3fc5-230">L'importo addebitato dal fornitore del benefit per un dipendente non fumatore.</span><span class="sxs-lookup"><span data-stu-id="c3fc5-230">The amount a benefit provider charges for a nonsmoking employee.</span></span> <span data-ttu-id="c3fc5-231">È l'importo che il datore di lavoro paga al fornitore del benefit e deve essere basato sulla frequenza di pagamento per l'impostazione del tasso.</span><span class="sxs-lookup"><span data-stu-id="c3fc5-231">This is the amount the employer pays to the benefit provider and it should be based on the payment frequency for the rate setup.</span></span> |
   | <span data-ttu-id="c3fc5-232">Importo amministrativo</span><span class="sxs-lookup"><span data-stu-id="c3fc5-232">Administrative amount</span></span> | <span data-ttu-id="c3fc5-233">L'importo amministrativo addebitato da un amministratore di terze parti.</span><span class="sxs-lookup"><span data-stu-id="c3fc5-233">The administrative amount charged by a third-party administrator.</span></span> <span data-ttu-id="c3fc5-234">È l'importo che il datore di lavoro paga all'amministratore di terze parti e deve essere basato sulla frequenza di pagamento per l'impostazione del tasso.</span><span class="sxs-lookup"><span data-stu-id="c3fc5-234">This is the amount that the employer pays to the third-party administrator and it should be based the payment frequency for the rate setup.</span></span> |
   | <span data-ttu-id="c3fc5-235">Tasso non fumatore crediti flessibili</span><span class="sxs-lookup"><span data-stu-id="c3fc5-235">Flex credit non-smoker rate</span></span> | <span data-ttu-id="c3fc5-236">Il costo del benefit in crediti flessibili, basato sul calcolo definito per il livello per non fumatori.</span><span class="sxs-lookup"><span data-stu-id="c3fc5-236">The number of flex credits the benefit costs, based on the calculation defined for the tier level for non-smokers.</span></span> <span data-ttu-id="c3fc5-237">Ad esempio, se il tipo di calcolo è "Per importo della copertura in $", l'importo di calcolo è 10.000 e il tasso non fumatore in crediti flessibili è 6; ciò significa che se un dipendente non fumatore sceglie una copertura di $10.000, questa costerà 6 crediti flessibili.</span><span class="sxs-lookup"><span data-stu-id="c3fc5-237">For example, if the calculation type is ‘Per $ amount of coverage’, the calculation amount is 10,000, and the flex credit non-smoker rate is 6, that means that if a nonsmoking employee chooses $10,000 of coverage, it will cost 6 flex credits.</span></span> <span data-ttu-id="c3fc5-238">Se sceglie una copertura di $20.000, costerà 12 crediti flessibili e così via.</span><span class="sxs-lookup"><span data-stu-id="c3fc5-238">If they choose $20,000 of coverage, it will cost 12 flex credits, and so on.</span></span> |
   | <span data-ttu-id="c3fc5-239">Tasso fumatore crediti flessibili</span><span class="sxs-lookup"><span data-stu-id="c3fc5-239">Flex credit smoker rate</span></span> | <span data-ttu-id="c3fc5-240">Il costo del benefit in crediti flessibili, basato sul calcolo definito per il livello per fumatori.</span><span class="sxs-lookup"><span data-stu-id="c3fc5-240">The number of flex credits the benefit costs, based on the calculation defined for the tier level for smokers.</span></span> |

5. <span data-ttu-id="c3fc5-241">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="c3fc5-241">Select **Save**.</span></span> 