---
title: Creare piani di retribuzione variabile
description: La retribuzione variabile rappresenta una retribuzione non regolare del dipendente, ad esempio premio o premi in azioni. Questo articolo descrive i componenti che devono essere impostati per utilizzare una retribuzione variabile e per iscrivere un dipendente in un piano di compensazione variabile.
author: andreabichsel
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
ms.search.form: HCMCompEligibility, HcmJobFunction, HcmWorker, HRMCompPerfPlan
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Human Resources
ms.custom: 16011
ms.assetid: fc3a394e-9ac6-4f8c-9162-dc16ec22720f
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: 6f35bd9e8fd96c7ce495677232a669de2b856809
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2020
ms.locfileid: "3009544"
---
# <a name="create-variable-compensation-plans"></a><span data-ttu-id="bd3a8-104">Creare piani di retribuzione variabile</span><span class="sxs-lookup"><span data-stu-id="bd3a8-104">Create variable compensation plans</span></span>

<span data-ttu-id="bd3a8-105">La retribuzione variabile rappresenta una retribuzione non regolare del dipendente, ad esempio premio o premi in azioni.</span><span class="sxs-lookup"><span data-stu-id="bd3a8-105">Variable compensation makes up an employee's irregular pay, such as bonuses or stock awards.</span></span> <span data-ttu-id="bd3a8-106">Questo articolo descrive i componenti che devono essere impostati per utilizzare una retribuzione variabile e per iscrivere un dipendente in un piano di compensazione variabile.</span><span class="sxs-lookup"><span data-stu-id="bd3a8-106">This article describes the components that must be set up before you can use variable compensation and enroll an employee in a variable compensation plan.</span></span>

<span data-ttu-id="bd3a8-107">Il calcolo degli importi di retribuzione variabile per i dipendenti può basarsi su diversi fattori, ad esempio le prestazioni del dipendente, il livello retributivo del dipendente e le prestazioni del reparto.</span><span class="sxs-lookup"><span data-stu-id="bd3a8-107">The calculation of variable compensation amounts for your employees can be based on several factors, such as the employee's performance, the employee's compensation level, and the department's performance.</span></span>

## <a name="variable-compensation-components"></a><span data-ttu-id="bd3a8-108">Componenti della retribuzione variabile</span><span class="sxs-lookup"><span data-stu-id="bd3a8-108">Variable compensation components</span></span>
### <a name="create-compensation-types"></a><span data-ttu-id="bd3a8-109">Creare tipi di retribuzione</span><span class="sxs-lookup"><span data-stu-id="bd3a8-109">Create compensation types</span></span>

<span data-ttu-id="bd3a8-110">I **tipi di retribuzione variabile**costituiscono una componente necessaria.</span><span class="sxs-lookup"><span data-stu-id="bd3a8-110">**Variable compensation types** are a required component.</span></span> <span data-ttu-id="bd3a8-111">I tipi di retribuzione variabile consentono di descrivere i tipi di retribuzione assegnati dall'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="bd3a8-111">Variable compensation types let you describe the kinds of variable compensation that your organization awards.</span></span> <span data-ttu-id="bd3a8-112">Consentono inoltre di specificare se la retribuzione avverrà in contanti o mediante un modulo non monetario, ad esempio come scorte.</span><span class="sxs-lookup"><span data-stu-id="bd3a8-112">They also let you specify whether the compensation will be in cash or in a non-monetary form, such as stock.</span></span>

### <a name="describe-vesting-rules"></a><span data-ttu-id="bd3a8-113">Descrivere regole di distribuzione incentivi</span><span class="sxs-lookup"><span data-stu-id="bd3a8-113">Describe vesting rules</span></span>

<span data-ttu-id="bd3a8-114">Facoltativamente, le società possono impostare **regole di distribuzione incentivi**.</span><span class="sxs-lookup"><span data-stu-id="bd3a8-114">Optionally, companies can set up **vesting rules**.</span></span> <span data-ttu-id="bd3a8-115">Le regole di distribuzione incentivi descrivono come il premio variabile deve essere allocato nel tempo.</span><span class="sxs-lookup"><span data-stu-id="bd3a8-115">Vesting rules describe how the variable award should be allocated over time.</span></span> <span data-ttu-id="bd3a8-116">Ad esempio, una regola di distribuzione degli incentivi potrebbe indicare che il dipendente riceverà il 25% del proprio premio totale ogni anno per i quattro anni successivi.</span><span class="sxs-lookup"><span data-stu-id="bd3a8-116">For example, a vesting rule might state that the employee will receive 25 percent of his or her total award every year for the next four years.</span></span> <span data-ttu-id="bd3a8-117">Le regole di distribuzione incentivi sono solo informative.</span><span class="sxs-lookup"><span data-stu-id="bd3a8-117">Vesting rules are informational only.</span></span>

## <a name="variable-compensation-plans"></a><span data-ttu-id="bd3a8-118">Piani di retribuzione variabile</span><span class="sxs-lookup"><span data-stu-id="bd3a8-118">Variable compensation plans</span></span>
<span data-ttu-id="bd3a8-119">Il **piano di retribuzione variabile** contiene le regole, i metodi di calcolo e i valori predefiniti per il calcolo di retribuzione variabile per dipendenti iscritti al piano.</span><span class="sxs-lookup"><span data-stu-id="bd3a8-119">The **variable compensation plan** contains the rules, calculation methods, and default values for the calculation of variable compensation for enrolled employees.</span></span> <span data-ttu-id="bd3a8-120">Quando si crea un piano di retribuzione variabile, è necessario impostare il tipo di retribuzione variabile.</span><span class="sxs-lookup"><span data-stu-id="bd3a8-120">When you create a variable compensation plan, you must set the variable compensation type.</span></span> <span data-ttu-id="bd3a8-121">Il tipo di retribuzione variabile determina se il sistema calcolerà un importo in valuta o un numero di unità come premio.</span><span class="sxs-lookup"><span data-stu-id="bd3a8-121">The variable compensation type determines whether the system calculates a currency amount or a number of units as the award.</span></span> <span data-ttu-id="bd3a8-122">È inoltre necessario impostare il metodo di calcolo:</span><span class="sxs-lookup"><span data-stu-id="bd3a8-122">You must also set the calculation method:</span></span>

-   <span data-ttu-id="bd3a8-123">**Temporizzato** - Il calcolo del premio variabile è basato sulla retribuzione fissa che il dipendente ha avuto in una data specifica.</span><span class="sxs-lookup"><span data-stu-id="bd3a8-123">**Point in time** – The calculation of the variable award is based on the fixed compensation that the employee had on a specific date.</span></span> <span data-ttu-id="bd3a8-124">Tale data viene specificata all'evento processo quando i nuovi importi di retribuzione vengono elaborati.</span><span class="sxs-lookup"><span data-stu-id="bd3a8-124">That date is specified on the process event when new compensation amounts are processed.</span></span>
-   <span data-ttu-id="bd3a8-125">**Composito**: un importo del premio viene calcolato per ogni tariffa retributiva univoca della retribuzione fissa che il dipendente ha percepito tra la data di inizio e la data di fine del ciclo nell'evento di processo.</span><span class="sxs-lookup"><span data-stu-id="bd3a8-125">**Composite** – An award amount is calculated for each unique fixed compensation pay rate that the employee had between the cycle start date and the cycle end date on the process event.</span></span> <span data-ttu-id="bd3a8-126">I tassi vengono quindi sommati per determinare il premio finale.</span><span class="sxs-lookup"><span data-stu-id="bd3a8-126">The rates are then added together to determine the final award.</span></span> <span data-ttu-id="bd3a8-127">Ad esempio, durante il ciclo, un dipendente trasferito in una posizione diversa che aveva una retribuzione diversa.</span><span class="sxs-lookup"><span data-stu-id="bd3a8-127">For example, during the cycle, an employee transferred to a different position that had a different pay rate.</span></span> <span data-ttu-id="bd3a8-128">In questo caso, il premio variabile viene rettificato in base alla durata di ogni tariffa retributiva del dipendente.</span><span class="sxs-lookup"><span data-stu-id="bd3a8-128">In this case, the variable award is adjusted for the length of time that the employee had each pay rate.</span></span>

<span data-ttu-id="bd3a8-129">L'importo del premio variabile può basarsi su una percentuale del reddito di base regolare del dipendente o su un numero stabilito di unità.</span><span class="sxs-lookup"><span data-stu-id="bd3a8-129">The amount of the variable award can be based on either a percentage of the employee's regular base earnings or a set number of units.</span></span>

-   <span data-ttu-id="bd3a8-130">Selezionare l'opzione **Percentuale della base** per immettere una percentuale predefinita e specificare se la base deve essere la tariffa di retribuzione fissa del dipendente o il punto di controllo per il livello retributivo del dipendente.</span><span class="sxs-lookup"><span data-stu-id="bd3a8-130">Select the **Percent of basis** option to enter a default percentage, and specify whether the basis should be the employee's fixed pay rate or the control point for the employee's compensation level.</span></span> <span data-ttu-id="bd3a8-131">Il livello retributivo viene impostato sulla mansione del dipendente.</span><span class="sxs-lookup"><span data-stu-id="bd3a8-131">The compensation level is set on the employee's job.</span></span> <span data-ttu-id="bd3a8-132">Uno dei punti di riferimento dalla struttura retributiva può essere impostato come punto di controllo nel piano di retribuzione fissa.</span><span class="sxs-lookup"><span data-stu-id="bd3a8-132">One of the reference points from the compensation structure can be set as the control point on the fixed compensation plan.</span></span> <span data-ttu-id="bd3a8-133">Il sistema utilizzerà il livello retributivo della mansione del dipendente e lo incrocerà con il punto di controllo elencato nel piano di retribuzione fissa del dipendente per trovare l'importo del punto di controllo per il livello retributivo del dipendente.</span><span class="sxs-lookup"><span data-stu-id="bd3a8-133">The system will use the compensation level from the employee's job and cross-reference it with the control point that is listed on the employee's fixed compensation plan to find the control point amount for the employee's compensation level.</span></span> <span data-ttu-id="bd3a8-134">L'importo del punto di controllo verrà quindi utilizzato in sostituzione della retribuzione fissa del dipendente come base per il premio.</span><span class="sxs-lookup"><span data-stu-id="bd3a8-134">The control point amount will then be used instead of the employee's fixed pay rate as the basis for the award.</span></span>
-   <span data-ttu-id="bd3a8-135">Selezionare l'opzione**Numero di unità** per immettere un numero di unità predefinito, il valore di ciascuna unità e la valuta del valore unitario se il piano di retribuzione è relativo a un premio non in contanti (ad esempio, 200 unità di scorte che vengono valutate a 40 EUR) o solo il numero di unità se il piano di retribuzione è relativo a un premio in contanti.</span><span class="sxs-lookup"><span data-stu-id="bd3a8-135">Select the **Number of units** option to enter a default number of units, the value of each unit and the currency of the unit value if the compensation plan is for a non-cash award (for example, 200 units of stock that are valued at 40 USD), or just the number of units if the compensation plan is for a cash award.</span></span> <span data-ttu-id="bd3a8-136">Per un premio in contanti, il dipendente riceverà il numero di unità specificate della valuta utilizzata per il proprio piano di retribuzione fissa, ad esempio 500 unità di 1 EUR.</span><span class="sxs-lookup"><span data-stu-id="bd3a8-136">For a cash award, the employee will receive the specified number of units of the currency that is used for his or her fixed compensation plan (for example, 500 units of 1 USD).</span></span> <span data-ttu-id="bd3a8-137">Il controllo della relazione uno-a-uno può essere utilizzato per indicare se esiste un mapping uno-a-uno diretto tra il numero di unità e il valore unitario.</span><span class="sxs-lookup"><span data-stu-id="bd3a8-137">The one-to-one relationship control can be used to indicate whether there is a direct one-to-one mapping between the number of units and the unit value.</span></span> <span data-ttu-id="bd3a8-138">Quando si crea un piano di retribuzione variabile per un piano basato su contanti usando il numero di unità, questa viene automaticamente bloccata su **Sì** e il valore unitario è **1,0000**.</span><span class="sxs-lookup"><span data-stu-id="bd3a8-138">When you create a variable compensation plan for a cash-based plan by using the number of units, this option is automatically locked to **Yes**, and the unit value is **1.0000**.</span></span>

<span data-ttu-id="bd3a8-139">L'impostazione **Regola di assunzione** consente di specificare se tutti i dipendenti devono ricevere lo stesso aumento, indipendentemente dalla data in cui sono stati assunti (**Regola di assunzione** = **Nessuno**) o se i dipendenti devono ottenere una percentuale del premio in base alla durata dell'impiego durante il ciclo (**Regola di assunzione** = **Percentuale**).</span><span class="sxs-lookup"><span data-stu-id="bd3a8-139">The **Hire rule** setting lets you specify whether all employees should receive the same increase, regardless of the date they were hired (**Hire rule** = **None**), or whether employees should receive a percentage of the award that is based on the length of their employment during the cycle (**Hire rule** = **Percent**).</span></span> 

<span data-ttu-id="bd3a8-140">**Fattore**  consente di rettificare il premio di un dipendente, a seconda delle prestazioni del reparto del dipendente.</span><span class="sxs-lookup"><span data-stu-id="bd3a8-140">**Leverage** lets you to adjust an employee's award, based on the performance of the employee's department.</span></span> <span data-ttu-id="bd3a8-141">Metriche delle prestazioni possono essere impostate per ciascun reparto nella pagina **Reparti**, in **Moduli correlati** &gt; **Retribuzione** &gt; **Prestazioni**.</span><span class="sxs-lookup"><span data-stu-id="bd3a8-141">Performance metrics can be set for each department on the **Departments** page, under **Related forms** &gt; **Compensation** &gt; **Performance**.</span></span> <span data-ttu-id="bd3a8-142">Il premio che i dipendenti del reparto ricevono dipende dal valore del campo **Percentuale dell'obiettivo raggiunta**, che indica le prestazioni del reparto:</span><span class="sxs-lookup"><span data-stu-id="bd3a8-142">The award that employees in that department receive depends on the value of the **Percent of target achieved** field, which indicates the department's performance:</span></span>

-   <span data-ttu-id="bd3a8-143">Se le prestazioni del reparto sono 100 percento, il premio per i dipendenti in tale reparto viene moltiplicato per la percentuale impostata nel campo**Pagamento al 100%**.</span><span class="sxs-lookup"><span data-stu-id="bd3a8-143">If the department's performance is 100 percent, the award for the employees in that department is factored by the percentage that is set in the **Payout at 100%** field.</span></span>
-   <span data-ttu-id="bd3a8-144">Se le prestazioni del reparto sono superiori al 100 percento, il sistema aggiunge la percentuale impostata nel campo **Ogni 1% al di sopra dell'obiettivo** alla percentuale impostata nel campo **Pagamento al 100%** finché non viene raggiunto il valore impostato nel campo **Pagamento massimo consentito**.</span><span class="sxs-lookup"><span data-stu-id="bd3a8-144">If the department's performance is more than 100 percent, the system adds the percentage that is set in the **Per 1% over objective** field to the percentage that is set in the **Payout at 100%** field until the value that is set in the **Highest allowable payout** field is reached.</span></span>
-   <span data-ttu-id="bd3a8-145">Se le prestazioni del reparto sono inferiori al 100 percento, il sistema sottrae la percentuale impostata nel campo **Ogni 1% al di sotto dell'obiettivo** dalla percentuale impostata nel campo **Pagamento al 100%** finché non viene raggiunto il valore impostato nel campo **Pagamento minimo consentito**.</span><span class="sxs-lookup"><span data-stu-id="bd3a8-145">If the department's performance is less than 100 percent, the system subtracts the percentage that is set in the **Per 1% under objective** field from the percentage that is set in the **Payout at 100%** field until the value that is set in the **Lowest allowable payout** field is reached.</span></span>

<span data-ttu-id="bd3a8-146">È possibile impostare**livelli di tolleranza** sulle percentuali di soglia in modo da visualizzare un messaggio di avviso se il fattore causa il superamento della percentuale di soglia.</span><span class="sxs-lookup"><span data-stu-id="bd3a8-146">You can set **tolerance levels** on the threshold percentages, so that a warning message appears if the leverage causes the percentage to be outside the threshold percentage.</span></span> 

<span data-ttu-id="bd3a8-147">Per impostazione predefinita, il sistema cerca il reparto impostato sulla posizione del dipendente.</span><span class="sxs-lookup"><span data-stu-id="bd3a8-147">By default, the system looks for the department that is set on the employee's position.</span></span> <span data-ttu-id="bd3a8-148">Tuttavia, il premio per alcuni dipendenti potrebbe dipendere dalle prestazioni di più reparti.</span><span class="sxs-lookup"><span data-stu-id="bd3a8-148">However, the award for some employees might depend on the performance of multiple departments.</span></span> <span data-ttu-id="bd3a8-149">In questo caso, i diversi reparti e la percentuale del premio allocato alle prestazioni di ciascun reparto possono essere impostati all'iscrizione del dipendente al piano di retribuzione variabile.</span><span class="sxs-lookup"><span data-stu-id="bd3a8-149">In this case, the various departments and the percentage of the award that is allocated to the performance of each department can be set on the employee's variable compensation enrollment.</span></span> <span data-ttu-id="bd3a8-150">Per ulteriori informazioni, vedere la sezione "Iscrizione retribuzione variabile" che segue.</span><span class="sxs-lookup"><span data-stu-id="bd3a8-150">For more information, see the "Variable compensation enrollment" section that follows.</span></span> 

<span data-ttu-id="bd3a8-151">Il fattore viene utilizzato solo se l'impostazione **Retribuzione basata sulla produttività** è selezionata quando viene eseguito il processo retributivo.</span><span class="sxs-lookup"><span data-stu-id="bd3a8-151">Leverage is used only if **Pay for performance** is selected when the compensation process is run.</span></span> 

<span data-ttu-id="bd3a8-152">La scheda **Sostituzioni livelli** consente di sostituire la percentuale predefinita o il numero di unità del premio, in base al livello retributivo del dipendente.</span><span class="sxs-lookup"><span data-stu-id="bd3a8-152">The **Levels overrides** tab lets you override the award's default percentage or number of units, based on the compensation level of the employee.</span></span> <span data-ttu-id="bd3a8-153">Se **Abilita sostituzioni per livelli** è impostato su **Sì** per i dipendenti che sono iscritti al piano di retribuzione variabile, il sistema prende il livello dalla mansione di un dipendente e quindi lo cerca nella tabella delle sostituzioni livelli per determinare la percentuale o il numero di unità per tale livello.</span><span class="sxs-lookup"><span data-stu-id="bd3a8-153">If **Enable overrides for levels** is set to **Yes** for employees who are enrolled in the variable compensation plan, the system takes the level from an employee's job, and then looks for it in the levels overrides table to determine the percentage or number of units for that level.</span></span> <span data-ttu-id="bd3a8-154">Se il livello non viene trovato nella tabella delle sostituzioni livelli, la percentuale o il numero di unità predefinito dalla scheda **Generale** viene utilizzato.</span><span class="sxs-lookup"><span data-stu-id="bd3a8-154">If the level is not found in the level overrides table, the default percentage or number of units from the **General** tab is used.</span></span> <span data-ttu-id="bd3a8-155">La percentuale e il numero di unità possono inoltre essere sostituiti nell'iscrizione del dipendente nel piano di retribuzione variabile.</span><span class="sxs-lookup"><span data-stu-id="bd3a8-155">The percentage and number of units can also be overridden on the employee's enrollment in the variable compensation plan.</span></span>

## <a name="variable-compensation-enrollment"></a><span data-ttu-id="bd3a8-156">Iscrizione retribuzione variabile</span><span class="sxs-lookup"><span data-stu-id="bd3a8-156">Variable compensation enrollment</span></span>
### <a name="determine-who-is-eligible-for-the-plan"></a><span data-ttu-id="bd3a8-157">Stabilire chi è idoneo per il piano</span><span class="sxs-lookup"><span data-stu-id="bd3a8-157">Determine who is eligible for the plan</span></span>

<span data-ttu-id="bd3a8-158">Se si desidera iscrivere i dipendenti a un piano di retribuzione variabile, il primo passaggio consiste nello stabilire chi è idoneo per la retribuzione specificata nel piano.</span><span class="sxs-lookup"><span data-stu-id="bd3a8-158">When you're ready to enroll employees in a variable compensation plan, the first step is to determine who is eligible for the compensation that is specified in the plan.</span></span> <span data-ttu-id="bd3a8-159">Non è possibile assegnare il piano ai dipendenti se non si stabilisce l'idoneità.</span><span class="sxs-lookup"><span data-stu-id="bd3a8-159">You can't assign the plan to any employees unless you determine eligibility.</span></span> <span data-ttu-id="bd3a8-160">Per impostare l'idoneità, aprire la pagina **Regole di idoneità** per creare una nuova regola di idoneità per il piano, quindi definire i criteri che un dipendente deve soddisfare per essere idoneo per il piano di retribuzione.</span><span class="sxs-lookup"><span data-stu-id="bd3a8-160">To set up eligibility, open the **Eligibility rules** page to create a new eligibility rule for your plan, and then define the criteria that an employee must meet to be eligible for the compensation plan.</span></span> <span data-ttu-id="bd3a8-161">È possibile limitare l'idoneità in base al reparto, al sindacato, al paese di retribuzione (località), alla mansione, alla funzione lavorativa, al tipo di mansione e/o al livello retributivo.</span><span class="sxs-lookup"><span data-stu-id="bd3a8-161">You can limit eligibility by department, labor union, compensation region (location), job, job function, job type, and/or compensation level.</span></span> <span data-ttu-id="bd3a8-162">I dipendenti possono essere iscritti a un piano di retribuzione solo se soddisfano **tutti** i criteri impostati nella regola di idoneità.</span><span class="sxs-lookup"><span data-stu-id="bd3a8-162">Employees can be enrolled in a compensation plan only if they meet **all** the criteria that are set on the eligibility rule.</span></span> 

<span data-ttu-id="bd3a8-163">**Nota:** le regole di idoneità determinano l'idoneità per i piani di retribuzione fissa e variabile.</span><span class="sxs-lookup"><span data-stu-id="bd3a8-163">**Note:** Eligibility rules determine eligibility for both fixed compensation plans and variable compensation plans.</span></span> <span data-ttu-id="bd3a8-164">Le regole di idoneità utilizzano i seguenti campi nei record relativi a mansione, posizione e dipendente per stabilire se un dipendente è idoneo per un piano di retribuzione:</span><span class="sxs-lookup"><span data-stu-id="bd3a8-164">The eligibility rules use the following fields on the job, position, and employee records to determine whether an employee is eligible for a compensation plan:</span></span>

- <span data-ttu-id="bd3a8-165">Nella pagina **Mansione**:</span><span class="sxs-lookup"><span data-stu-id="bd3a8-165">On the **Job** page:</span></span>
  -   <span data-ttu-id="bd3a8-166">Il campo **Mansione**</span><span class="sxs-lookup"><span data-stu-id="bd3a8-166">The **Job** field</span></span>
  -   <span data-ttu-id="bd3a8-167">I campi **Funzione** e **Tipo di mansione** sulla scheda **Classificazione mansione**</span><span class="sxs-lookup"><span data-stu-id="bd3a8-167">The **Function** and **Job type** fields on the **Job classification** tab</span></span>
  -   <span data-ttu-id="bd3a8-168">Il campo **Livello** sulla scheda **Retribuzione**</span><span class="sxs-lookup"><span data-stu-id="bd3a8-168">The **Level** field on the **Compensation** tab</span></span>
- <span data-ttu-id="bd3a8-169">Nella pagina **Posizioni**: i campi **Reparto** e **Paese di retribuzione**</span><span class="sxs-lookup"><span data-stu-id="bd3a8-169">On the **Positions** page: The **Department** and **Compensation region** fields</span></span>
- <span data-ttu-id="bd3a8-170">Nella pagina <strong>Dipendenti</strong>: le informazioni sui sindacati associati al dipendente in <strong>Informazioni personali</strong> &gt; <strong>Sindacati</strong> nella scheda *<strong><em>Lavoratore</em></strong>*</span><span class="sxs-lookup"><span data-stu-id="bd3a8-170">On the <strong>Employees</strong> page: The information about labor unions that is associated with the employee under <strong>Personal information</strong> &gt; <strong>Labor unions</strong> on the *<strong><em>Worker</em></strong>* tab</span></span>

### <a name="enable-enrollment-for-the-variable-compensation-plan"></a><span data-ttu-id="bd3a8-171">Abilitare l'iscrizione al piano di retribuzione variabile</span><span class="sxs-lookup"><span data-stu-id="bd3a8-171">Enable enrollment for the variable compensation plan</span></span>

<span data-ttu-id="bd3a8-172">Nella pagina **Piani di retribuzione variabile**, impostare l'opzione **Abilita iscrizione** su **Sì** per consentire l'iscrizione dei dipendenti idonei al piano.</span><span class="sxs-lookup"><span data-stu-id="bd3a8-172">On the **Variable compensation plans** page, set the **Enable enrollment** option to **Yes** to allow eligible employees to be enrolled in the plan.</span></span>

### <a name="enroll-the-employee"></a><span data-ttu-id="bd3a8-173">Iscrivere il dipendente al piano</span><span class="sxs-lookup"><span data-stu-id="bd3a8-173">Enroll the employee</span></span>

<span data-ttu-id="bd3a8-174">È ora possibile iscrivere i dipendenti al piano di retribuzione variabile.</span><span class="sxs-lookup"><span data-stu-id="bd3a8-174">You can now enroll employees in the variable compensation plan.</span></span> <span data-ttu-id="bd3a8-175">Per iscrivere un dipendente, passare alla pagina **Dipendenti** e selezionare il dipendente.</span><span class="sxs-lookup"><span data-stu-id="bd3a8-175">To enroll an employee, go to the **Employees** page, and select the employee.</span></span> <span data-ttu-id="bd3a8-176">Quindi, nel riquadro azioni, fare clic su **Retribuzione** &gt; **Iscrizione al piano di retribuzione variabile**.</span><span class="sxs-lookup"><span data-stu-id="bd3a8-176">Then, on the Action Pane, click **Compensation** &gt; **Variable plan enrollment**.</span></span> 

<span data-ttu-id="bd3a8-177">**Nota:** l'opzione **Iscrizione** deve essere impostata su **Sì** nel piano di retribuzione variabile.</span><span class="sxs-lookup"><span data-stu-id="bd3a8-177">**Note:** **Enrollment** must be set to **Yes** on the variable compensation plan.</span></span> <span data-ttu-id="bd3a8-178">Il campo **Piano** indica solo i piani per i quali un dipendente è idoneo in base alle regole di idoneità impostate per tali piani.</span><span class="sxs-lookup"><span data-stu-id="bd3a8-178">The **Plan** field shows only the plans that the employee is eligible for, based on the eligibility rules that are set up for those plans.</span></span> <span data-ttu-id="bd3a8-179">Se non si specifica alcuna regola di idoneità per un piano, nessun dipendente sarà idoneo per tale piano.</span><span class="sxs-lookup"><span data-stu-id="bd3a8-179">If an eligibility rule isn't set for a plan, no employees will be eligible for that plan.</span></span> 

<span data-ttu-id="bd3a8-180">Assicurarsi che il campo **Data di validità** sia impostato correttamente.</span><span class="sxs-lookup"><span data-stu-id="bd3a8-180">Make sure that the **Effective date** field is set correctly.</span></span> <span data-ttu-id="bd3a8-181">Se il piano di retribuzione variabile utilizza il metodo di calcolo **Composito**, la data di validità dell'iscrizione può essere considerata durante il calcolo del premio del dipendente.</span><span class="sxs-lookup"><span data-stu-id="bd3a8-181">If the variable compensation plan uses the **Composite** calculation method, the effective date of the enrollment might be considered during the calculation of the employee's award.</span></span> 

<span data-ttu-id="bd3a8-182">È possibile utilizzare la scheda **Sostituzioni** per sostituire i valori specifici per il dipendente.</span><span class="sxs-lookup"><span data-stu-id="bd3a8-182">You can use the **Overrides** tab to override specific values for the employee.</span></span> <span data-ttu-id="bd3a8-183">Ad esempio, se **Regola di assunzione**  è impostato su **Percentuale** nel piano e una data di assunzione diversa deve essere utilizzata durante il calcolo della percentuale dell'assunzione del dipendente, è possibile impostare la data di assunzione nel campo **Data regola di assunzione**.</span><span class="sxs-lookup"><span data-stu-id="bd3a8-183">For example, if **Hire rule** is set to **Percent** on the plan, and a different hire date should be used during the calculation of the employee's hire percentage, you can set the hire date in the **Hire rule date** field.</span></span> <span data-ttu-id="bd3a8-184">È inoltre possibile sostituire il valore **Percentuale premio** o il valore **Numero di unità** per un dipendente specifico, a seconda delle impostazioni del piano.</span><span class="sxs-lookup"><span data-stu-id="bd3a8-184">You can also override either the **Award percent** value or the **Number of units** value for a specific employee, depending on the plan's settings.</span></span> <span data-ttu-id="bd3a8-185">Questi valori verranno comunque moltiplicati per la regola di assunzione, i fattori di prestazioni e altri impostazioni nel piano.</span><span class="sxs-lookup"><span data-stu-id="bd3a8-185">These values will still be factored by the hire rule, performance factors, and other settings on the plan.</span></span> 

<span data-ttu-id="bd3a8-186">**Sostituzioni organizzative** vengono utilizzate per basare il premio del dipendente sulle prestazioni di uno o più reparti.</span><span class="sxs-lookup"><span data-stu-id="bd3a8-186">**Organizational overrides** are used to base an employee's award on the performance of one or more departments.</span></span> <span data-ttu-id="bd3a8-187">La percentuale allocata tra reparti deve essere pari al 100%.</span><span class="sxs-lookup"><span data-stu-id="bd3a8-187">The percentage that is allocated across departments should total 100 percent.</span></span> <span data-ttu-id="bd3a8-188">La singola prestazioni di un dipendente viene anche considerata.</span><span class="sxs-lookup"><span data-stu-id="bd3a8-188">The employee's individual performance is also considered.</span></span> <span data-ttu-id="bd3a8-189">Queste impostazioni vengono utilizzate solo se **Retribuzione basata sulla produttività** è selezionata quando viene eseguito il processo retributivo.</span><span class="sxs-lookup"><span data-stu-id="bd3a8-189">These settings are used only if **Pay for performance** is selected when the compensation process is run.</span></span>


