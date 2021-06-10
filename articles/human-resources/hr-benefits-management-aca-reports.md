---
title: Genera rapporti Affordable Care Act nella gestione dei vantaggi
description: Questo argomento descrive come la gestione dei benefici ti aiuta a tenere traccia delle informazioni riportate nel modulo 1.095-B e nel modulo 1.095-C per il mandato del datore di lavoro Affordable Care Act (ACA).
author: andreabichsel
ms.date: 12/28/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-12-28
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: 1417232baeaf03721bd0b25cc3f9fd5f750c65d5
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/18/2021
ms.locfileid: "6052267"
---
# <a name="generate-aca-reports-in-benefits-management"></a><span data-ttu-id="895ee-103">Genera rapporti ACA nella gestione dei vantaggi</span><span class="sxs-lookup"><span data-stu-id="895ee-103">Generate ACA reports in Benefits management</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="895ee-104">La gestione dei benefici ti aiuta a tenere traccia delle informazioni riportate nel modulo 1.095-B e nel modulo 1.095-C per il mandato del datore di lavoro Affordable Care Act (ACA).</span><span class="sxs-lookup"><span data-stu-id="895ee-104">Benefits management helps you track information that is reported on Form 1095-B and Form 1095-C for the Affordable Care Act (ACA) employer mandate.</span></span> <span data-ttu-id="895ee-105">Come la capacità di reporting ACA nella vecchia area di lavoro **Benefici**, questa funzionalità si applica solo alle persone giuridiche negli Stati Uniti.</span><span class="sxs-lookup"><span data-stu-id="895ee-105">Like the ACA reporting capability in the old **Benefits** workspace, this functionality applies only to legal entities in the United States.</span></span>

<span data-ttu-id="895ee-106">Per utilizzare questa funzionalità, è necessario prima attivarla in **Gestione avanzata dei vantaggi**.</span><span class="sxs-lookup"><span data-stu-id="895ee-106">To use this functionality, you must first turn on **Advanced Benefits Management**.</span></span> <span data-ttu-id="895ee-107">Per ulteriori informazioni, comprese importanti avvertenze sulla gestione dei vantaggi, vedi [Abilita o disabilita la gestione dei vantaggi](hr-admin-manage-features.md#enable-or-disable-benefits-management).</span><span class="sxs-lookup"><span data-stu-id="895ee-107">For more information, including important caveats about Benefits management, see [Enable or disable Benefits management](hr-admin-manage-features.md#enable-or-disable-benefits-management).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="895ee-108">Puoi utilizzare il reporting ACA solo dall'area di lavoro **Gestione dei vantaggi** o dalla vecchia area di lavoro **Benefici**, non da entrambe.</span><span class="sxs-lookup"><span data-stu-id="895ee-108">You can use ACA reporting only from either the **Benefits management** workspace or the old **Benefits** workspace, not from both.</span></span> <span data-ttu-id="895ee-109">Ad esempio, se si è passati alla gestione dei vantaggi, il reporting ACA è disponibile solo dall'area di lavoro **Gestione dei vantaggi**, non dalla vecchia area di lavoro **Benefici**.</span><span class="sxs-lookup"><span data-stu-id="895ee-109">For example, if you switched to Benefits management, ACA reporting is available only from the **Benefits management** workspace, not from the old **Benefits** workspace.</span></span>
>
> <span data-ttu-id="895ee-110">Se si passa alla gestione dei benefici nel mezzo di un anno di iscrizione, è necessario configurare correttamente i dati dei dipendenti per l'intero anno nella gestione dei vantaggi.</span><span class="sxs-lookup"><span data-stu-id="895ee-110">If you switch to Benefits management in the middle of an enrollment year, you must correctly configure employee data for the whole year in Benefits management.</span></span> <span data-ttu-id="895ee-111">In questo modo, ti assicuri di ricevere informazioni accurate sui rapporti per l'intero anno.</span><span class="sxs-lookup"><span data-stu-id="895ee-111">In this way, you ensure that you will receive accurate reporting information for the whole year.</span></span>

## <a name="getting-started"></a><span data-ttu-id="895ee-112">Introduzione</span><span class="sxs-lookup"><span data-stu-id="895ee-112">Getting started</span></span>

<span data-ttu-id="895ee-113">Per tenere traccia delle informazioni per i moduli 1.095, creare prima uno o più gruppi di copertura Affordable Care.</span><span class="sxs-lookup"><span data-stu-id="895ee-113">To track information for 1095 forms, first create one or more Affordable Care coverage groups.</span></span> <span data-ttu-id="895ee-114">Questi gruppi indicano le seguenti informazioni:</span><span class="sxs-lookup"><span data-stu-id="895ee-114">These groups indicate the following information:</span></span>

- <span data-ttu-id="895ee-115">L'offerta di copertura fornita a un dipendente</span><span class="sxs-lookup"><span data-stu-id="895ee-115">The offer of coverage that was provided to an employee</span></span>
- <span data-ttu-id="895ee-116">La quota del dipendente del premio mensile più basso, se il costo è superiore alla soglia di povertà federale</span><span class="sxs-lookup"><span data-stu-id="895ee-116">The employee's share of the lowest-cost monthly premium, if the cost is above the federal poverty line</span></span>
- <span data-ttu-id="895ee-117">L'approdo sicuro utilizzato dal datore di lavoro, se applicabile</span><span class="sxs-lookup"><span data-stu-id="895ee-117">The safe harbor that is used by the employer, if applicable</span></span>

<span data-ttu-id="895ee-118">I gruppi di copertura Affordable Care ti aiutano a gestire queste informazioni per più record di dipendenti che hanno le stesse condizioni.</span><span class="sxs-lookup"><span data-stu-id="895ee-118">Affordable Care coverage groups help you manage this information for multiple employee records that have the same conditions.</span></span> <span data-ttu-id="895ee-119">Puoi facilmente assegnare gruppi a uno o più dipendenti.</span><span class="sxs-lookup"><span data-stu-id="895ee-119">You can easily assign groups to one or more employees.</span></span>

### <a name="create-or-edit-an-affordable-care-coverage-group"></a><span data-ttu-id="895ee-120">Crea o modifica un gruppo di copertura Affordable Care</span><span class="sxs-lookup"><span data-stu-id="895ee-120">Create or edit an Affordable Care coverage group</span></span>

1. <span data-ttu-id="895ee-121">Nell'area di lavoro **Gestione dei vantaggi**, seleziona **Gruppo di copertura Affordable Care**.</span><span class="sxs-lookup"><span data-stu-id="895ee-121">In the **Benefits management** workspace, select **Affordable Care coverage group**.</span></span>

    ![Selezione del gruppo di copertura Affordable Care](./media/hr-benefits-management-aca-coverage-group.png)

2. <span data-ttu-id="895ee-123">Seleziona **Nuovo** per creare un nuovo gruppo di copertura Affordable Care o **Modifica** per modificare un gruppo esistente.</span><span class="sxs-lookup"><span data-stu-id="895ee-123">Select **New** to create a new Affordable Care coverage group or **Edit** to change an existing group.</span></span>

    ![Selezione di Nuovo o Modifica](./media/hr-benefits-management-aca-new.png)

3. <span data-ttu-id="895ee-125">Impostare i seguenti campi.</span><span class="sxs-lookup"><span data-stu-id="895ee-125">Set the following fields.</span></span>

    | <span data-ttu-id="895ee-126">Campo</span><span class="sxs-lookup"><span data-stu-id="895ee-126">Field</span></span> | <span data-ttu-id="895ee-127">Descrizione</span><span class="sxs-lookup"><span data-stu-id="895ee-127">Description</span></span> |
    |---|---|
    | <span data-ttu-id="895ee-128">Nome</span><span class="sxs-lookup"><span data-stu-id="895ee-128">Name</span></span> | <span data-ttu-id="895ee-129">Immetti un nome per il gruppo.</span><span class="sxs-lookup"><span data-stu-id="895ee-129">Enter a name for the group.</span></span> |
    | <span data-ttu-id="895ee-130">Descrizione</span><span class="sxs-lookup"><span data-stu-id="895ee-130">Description</span></span> | <span data-ttu-id="895ee-131">Immettere una descrizione del gruppo.</span><span class="sxs-lookup"><span data-stu-id="895ee-131">Enter a description of the group.</span></span> |
    | <span data-ttu-id="895ee-132">Offerta di copertura</span><span class="sxs-lookup"><span data-stu-id="895ee-132">Offer of coverage</span></span> | <span data-ttu-id="895ee-133">La copertura offerta ai dipendenti, al loro coniuge o partner e ai loro dipendenti.</span><span class="sxs-lookup"><span data-stu-id="895ee-133">The coverage that is offered to employees, their spouse or partner, and their dependents.</span></span> |
    | <span data-ttu-id="895ee-134">Quota costo dipendente</span><span class="sxs-lookup"><span data-stu-id="895ee-134">Employee share of cost</span></span> | <span data-ttu-id="895ee-135">L'importo di cui il dipendente è responsabile.</span><span class="sxs-lookup"><span data-stu-id="895ee-135">The amount that the employee is responsible for.</span></span> |
    | <span data-ttu-id="895ee-136">Sezione applicabile 4980H Safe Harbor</span><span class="sxs-lookup"><span data-stu-id="895ee-136">Applicable section 4980H safe harbor</span></span> | <span data-ttu-id="895ee-137">4980H Safe Harbor o codice sblocco transizione.</span><span class="sxs-lookup"><span data-stu-id="895ee-137">The 4980H safe harbor or transition relief code.</span></span> |
    | <span data-ttu-id="895ee-138">Mese iniziale piano</span><span class="sxs-lookup"><span data-stu-id="895ee-138">Plan start month</span></span> | <span data-ttu-id="895ee-139">Seleziona il mese di calendario in cui inizia l'anno del tuo piano di benefit.</span><span class="sxs-lookup"><span data-stu-id="895ee-139">Select the calendar month when your benefit plan year begins.</span></span> |
    | <span data-ttu-id="895ee-140">Gruppo valido da</span><span class="sxs-lookup"><span data-stu-id="895ee-140">Group valid from</span></span> | <span data-ttu-id="895ee-141">La prima data in cui questo record è valido.</span><span class="sxs-lookup"><span data-stu-id="895ee-141">The first date when this record is valid.</span></span> |
    | <span data-ttu-id="895ee-142">Gruppo valido fino a</span><span class="sxs-lookup"><span data-stu-id="895ee-142">Group valid through</span></span> | <span data-ttu-id="895ee-143">L'ultima data in cui questo record è valido.</span><span class="sxs-lookup"><span data-stu-id="895ee-143">The last date when this record is valid.</span></span> <span data-ttu-id="895ee-144">Se non c'è una data di scadenza, inserisci **Mai**.</span><span class="sxs-lookup"><span data-stu-id="895ee-144">If there is no expiration date, enter **Never**.</span></span> |

    ![Creazione di un gruppo di copertura](./media/hr-benefits-management-aca-new-group.png)

4. <span data-ttu-id="895ee-146">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="895ee-146">Select **Save**.</span></span>

### <a name="assign-multiple-employees-to-an-affordable-care-coverage-group"></a><span data-ttu-id="895ee-147">Assegna più dipendenti a un gruppo di copertura Affordable Care</span><span class="sxs-lookup"><span data-stu-id="895ee-147">Assign multiple employees to an Affordable Care coverage group</span></span>

1. <span data-ttu-id="895ee-148">Nell'area di lavoro **Gestione dei vantaggi**, seleziona **Gruppo di copertura Affordable Care**.</span><span class="sxs-lookup"><span data-stu-id="895ee-148">In the **Benefits management** workspace, select **Affordable Care coverage group**.</span></span>
2. <span data-ttu-id="895ee-149">Seleziona il gruppo a cui assegnare i dipendenti.</span><span class="sxs-lookup"><span data-stu-id="895ee-149">Select the group to assign employees to.</span></span>
3. <span data-ttu-id="895ee-150">Seleziona **Assegnazione di massa**.</span><span class="sxs-lookup"><span data-stu-id="895ee-150">Select **Mass assignment**.</span></span>

    ![Selezione dell'assegnazione di massa](./media/hr-benefits-management-aca-mass-assignment.png)

4. <span data-ttu-id="895ee-152">Seleziona i dipendenti nell'elenco, quindi seleziona **Assegna**.</span><span class="sxs-lookup"><span data-stu-id="895ee-152">Select employees in the list, and then select **Assign**.</span></span>

    ![Assegnazione dei dipendenti selezionati a un gruppo](./media/hr-benefits-management-aca-assign-coverage-group.png)

## <a name="maintain-multiple-versions-of-coverage-options"></a><span data-ttu-id="895ee-154">Mantenimento di più versioni di opzioni di copertura</span><span class="sxs-lookup"><span data-stu-id="895ee-154">Maintain multiple versions of coverage options</span></span>

<span data-ttu-id="895ee-155">Puoi mantenere più versioni di qualsiasi gruppo di copertura.</span><span class="sxs-lookup"><span data-stu-id="895ee-155">You can maintain multiple versions of any coverage group.</span></span> <span data-ttu-id="895ee-156">Quando qualcosa cambia nella tua organizzazione o nei vantaggi offerti, puoi mantenere aggiornate le informazioni del gruppo senza dover creare un nuovo gruppo e riassegnarvi i dipendenti.</span><span class="sxs-lookup"><span data-stu-id="895ee-156">When something changes in your organization or the benefits that are offered, you can keep the group's information up to date without having to create a new group and reassign employees to it.</span></span>

<span data-ttu-id="895ee-157">Dopo aver creato i gruppi di copertura Affordable Care, puoi assegnarvi i dipendenti in massa.</span><span class="sxs-lookup"><span data-stu-id="895ee-157">After you've created Affordable Care coverage groups, you can mass-assign employees to them.</span></span> <span data-ttu-id="895ee-158">Puoi anche assegnare individualmente i dipendenti a gruppi e indicare se le informazioni ACA vengono tracciate e riportate.</span><span class="sxs-lookup"><span data-stu-id="895ee-158">You can also individually assign employees to groups, and indicate whether ACA information is tracked and reported.</span></span>

<span data-ttu-id="895ee-159">Se non è necessario tenere traccia e segnalare le informazioni ACA per un dipendente, puoi impostare l'opzione **Copertura del rapporto** su **No**.</span><span class="sxs-lookup"><span data-stu-id="895ee-159">If you don't have to track and report ACA information for an employee, you can set the **Report coverage** option to **No**.</span></span> <span data-ttu-id="895ee-160">Ad esempio, potresti avere dipendenti part-time che non richiedono rapporti ACA.</span><span class="sxs-lookup"><span data-stu-id="895ee-160">For example, you might have part-time employees who don't require ACA reporting.</span></span>

### <a name="override-default-values-for-an-employee"></a><span data-ttu-id="895ee-161">Sostituisci i valori predefiniti per un dipendente</span><span class="sxs-lookup"><span data-stu-id="895ee-161">Override default values for an employee</span></span>

<span data-ttu-id="895ee-162">Per i dipendenti assegnati a un gruppo di copertura Affordable Care, è possibile modificare le seguenti opzioni per tutti i mesi che richiedono valori diversi:</span><span class="sxs-lookup"><span data-stu-id="895ee-162">For employees who are assigned to an Affordable Care coverage group, you can change the following options for any months that require different values:</span></span>

- <span data-ttu-id="895ee-163">Offerta di copertura</span><span class="sxs-lookup"><span data-stu-id="895ee-163">Offer of coverage</span></span>
- <span data-ttu-id="895ee-164">Quota costo dipendente</span><span class="sxs-lookup"><span data-stu-id="895ee-164">Employee share of cost</span></span>
- <span data-ttu-id="895ee-165">Sezione applicabile 4980H Safe Harbor</span><span class="sxs-lookup"><span data-stu-id="895ee-165">Applicable section 4980H safe harbor</span></span>

> [!NOTE]
> <span data-ttu-id="895ee-166">Per i rapporti ACA 2020, devi segnalare sia i codici di avviamento postale di lavoro che quelli di casa nel modulo 1.095-C.</span><span class="sxs-lookup"><span data-stu-id="895ee-166">For 2020 ACA reports, you must report both work and home ZIP Codes on Form 1095-C.</span></span> <span data-ttu-id="895ee-167">I valori vengono inseriti automaticamente, in base alle posizioni attive correnti.</span><span class="sxs-lookup"><span data-stu-id="895ee-167">Values are automatically filled in, based on current active locations.</span></span> <span data-ttu-id="895ee-168">Se una delle due località era diversa durante qualsiasi parte dell'anno, è necessario sostituire il valore.</span><span class="sxs-lookup"><span data-stu-id="895ee-168">If either location was different during any part of the year, you must override the value.</span></span> <span data-ttu-id="895ee-169">Il campo **CAP** (riga 17) del report 1.095-C è riempita solo se il codice **Offerta di copertura** contiene **1L** tramite **1Q**, come segue:</span><span class="sxs-lookup"><span data-stu-id="895ee-169">The **ZIP Code** field (line 17) of the 1095-C report is filled in only if the **Offer of coverage** code contains **1L** through **1Q**, as follows:</span></span>
>
> - <span data-ttu-id="895ee-170">**1L, 1M o 1N:** il codice CAP della residenza principale</span><span class="sxs-lookup"><span data-stu-id="895ee-170">**1L, 1M, or 1N:** The primary residence ZIP Code</span></span>
> - <span data-ttu-id="895ee-171">**1O, 1P, 1Q:** il CAP del luogo di lavoro principale</span><span class="sxs-lookup"><span data-stu-id="895ee-171">**1O, 1P, 1Q:** The primary work ZIP Code</span></span>

<span data-ttu-id="895ee-172">Per inserire eccezioni per qualsiasi valore di un gruppo di copertura Affordable Care, segui questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="895ee-172">To enter exceptions for any values of an Affordable Care coverage group, follow these steps.</span></span>

1. <span data-ttu-id="895ee-173">Nell'area di lavoro **Gestione personale**, selezionare **Collegamenti**, quindi selezionare **Lavoratori**.</span><span class="sxs-lookup"><span data-stu-id="895ee-173">In the **Personnel management** workspace, select **Links**, and then select **Workers**.</span></span>
2. <span data-ttu-id="895ee-174">Selezionare il dipendente dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="895ee-174">Select the employee in the list.</span></span>
3. <span data-ttu-id="895ee-175">Nella scheda **Impiego**, nella sezione **Ulteriori informazioni**, seleziona **Copertura Affordable Care**.</span><span class="sxs-lookup"><span data-stu-id="895ee-175">On the **Employment** tab, in the **More information** section, select **Affordable Care coverage**.</span></span>

    ![Modifica delle opzioni per un dipendente](./media/hr-benefits-management-aca-change-single-employee.png)

4. <span data-ttu-id="895ee-177">Seleziona **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="895ee-177">Select **Edit**.</span></span>
5. <span data-ttu-id="895ee-178">Per ogni mese che richiede modifiche, seleziona la casella di controllo **Ignora predefinito**, quindi modifica gli altri valori come richiesto.</span><span class="sxs-lookup"><span data-stu-id="895ee-178">For each month that requires changes, select the **Override default** check box, and then change the other values as required.</span></span>

    ![Sovrascrittura dei valori predefiniti](./media/hr-benefits-management-aca-override-default.png)

6. <span data-ttu-id="895ee-180">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="895ee-180">Select **Save**.</span></span>

## <a name="report-health-care-coverage"></a><span data-ttu-id="895ee-181">Report di copertura delle spese mediche</span><span class="sxs-lookup"><span data-stu-id="895ee-181">Report health care coverage</span></span>

<span data-ttu-id="895ee-182">Devi tenere traccia di qualsiasi copertura sanitaria autoassicurata e sponsorizzata dal datore di lavoro per i dipendenti a tempo pieno e part-time.</span><span class="sxs-lookup"><span data-stu-id="895ee-182">You must track any employer-sponsored, self-insured health care coverage for full-time and part-time employees.</span></span> <span data-ttu-id="895ee-183">Includere ogni dipendente, insieme alle persone a carico, nel report 1.095-C per i mesi in cui sono stati coperti.</span><span class="sxs-lookup"><span data-stu-id="895ee-183">Include each employee, together with their dependents, on the 1095-C report for the months when they were covered.</span></span>

<span data-ttu-id="895ee-184">Per indicare se è necessario segnalare un piano di benefit, attieniti alla seguente procedura.</span><span class="sxs-lookup"><span data-stu-id="895ee-184">To indicate whether a benefit plan must be reported, follow these steps.</span></span>

1. <span data-ttu-id="895ee-185">Nell'area di lavoro **Gestione benefit**, seleziona **Piani di benefit**.</span><span class="sxs-lookup"><span data-stu-id="895ee-185">In the **Benefits management** workspace, select **Benefit plans**.</span></span>
2. <span data-ttu-id="895ee-186">Seleziona il piano di benefit da segnalare.</span><span class="sxs-lookup"><span data-stu-id="895ee-186">Select the benefit plan to report.</span></span>
3. <span data-ttu-id="895ee-187">Seleziona **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="895ee-187">Select **Edit**.</span></span>
4. <span data-ttu-id="895ee-188">Impostare l'opzione **Segnalato in Affordable Care Act** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="895ee-188">Set the **Reported under the Affordable Care Act** option to **Yes**.</span></span>

    ![Report di copertura delle spese mediche](./media/hr-benefits-management-aca-report-coverage.png)

5. <span data-ttu-id="895ee-190">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="895ee-190">Select **Save**.</span></span>

<span data-ttu-id="895ee-191">Se un dipendente sceglie la copertura sanitaria per un dipendente, il periodo di copertura del dipendente è determinato dalla data in cui il dipendente è stato iscritto o rimosso.</span><span class="sxs-lookup"><span data-stu-id="895ee-191">If an employee chooses health care coverage for a dependent, the dependent's coverage period is determined by the date when the dependent was enrolled or removed.</span></span> <span data-ttu-id="895ee-192">Le date di copertura per le persone a carico vengono calcolate automaticamente in base al periodo in cui la persona a carico era idonea e attiva in un piano durante l'anno di iscrizione.</span><span class="sxs-lookup"><span data-stu-id="895ee-192">Coverage dates for dependents are automatically calculated based on the period when the dependent was eligible and active in a plan during the enrollment year.</span></span>

## <a name="generate-1095-b-and-1095-c-forms"></a><span data-ttu-id="895ee-193">Genera moduli 1095-B e 1095-C</span><span class="sxs-lookup"><span data-stu-id="895ee-193">Generate 1095-B and 1095-C forms</span></span>

<span data-ttu-id="895ee-194">Puoi inoltre generare i moduli ACA 1.095-B e 1.095-C, quindi distribuirli a ciascuno dei dipendenti.</span><span class="sxs-lookup"><span data-stu-id="895ee-194">You can generate ACA 1095-B and 1095-C forms, and then distribute them to each of your employees.</span></span> <span data-ttu-id="895ee-195">Puoi inoltre generare elettronicamente il modulo 1.095-C e i file di trasmissione 1.094-C corrispondenti da inviare all'Internal Revenue Service (IRS).</span><span class="sxs-lookup"><span data-stu-id="895ee-195">You can also electronically generate Form 1095-C and the corresponding 1094-C transmittal files to send to the Internal Revenue Service (IRS).</span></span>

1. <span data-ttu-id="895ee-196">Nell'area di lavoro **Gestione dei benefit**, seleziona **Modulo ACA 1.095-B** o **Modulo ACA 1.095-C**.</span><span class="sxs-lookup"><span data-stu-id="895ee-196">In the **Benefits management** workspace, select **ACA 1095-B form** or **ACA 1095-C form**.</span></span>
2. <span data-ttu-id="895ee-197">Modifica i parametri in base alle esigenze, quindi seleziona **OK**.</span><span class="sxs-lookup"><span data-stu-id="895ee-197">Change the parameters as required, and then select **OK**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="895ee-198">Quando si stampano moduli 1.095-C per più di 500 dipendenti, si riceveranno più di un file PDF.</span><span class="sxs-lookup"><span data-stu-id="895ee-198">If you're printing 1095-C forms for more than 500 employees, you will receive more than one PDF file.</span></span> <span data-ttu-id="895ee-199">Ti consigliamo di aumentare il valore del campo **Dimensioni massime del file in megabyte** nella pagina **Parametri di gestione dei documenti** su **150**.</span><span class="sxs-lookup"><span data-stu-id="895ee-199">We recommend that you increase the value of the **Maximum file size in megabytes** field on the **Document management parameters** page to **150**.</span></span> <span data-ttu-id="895ee-200">Per aprire rapidamente quella pagina, puoi utilizzare il campo di ricerca sulla barra di navigazione.</span><span class="sxs-lookup"><span data-stu-id="895ee-200">(To quickly open that page, you can use the search field on the navigation bar.)</span></span>
    >
    > ![Modifica delle dimensioni massime del file](./media/hr-benefits-management-aca-maximum-file-size.png)

3. <span data-ttu-id="895ee-202">Per controllare lo stato dei tuoi report e visualizzarli, utilizza il campo di ricerca sulla barra di navigazione per aprire la pagina **Processi di creazione report elettronici**.</span><span class="sxs-lookup"><span data-stu-id="895ee-202">To check the status of your reports and view them, use the search field on the navigation bar to open the **Electronic reporting jobs** page.</span></span>

    ![Ricerca della pagina dei lavori di creazione di report elettronici](./media/hr-benefits-management-aca-search-electronic-reporting-jobs.png)

4. <span data-ttu-id="895ee-204">Seleziona il report da visualizzare, quindi seleziona **Visualizza file**.</span><span class="sxs-lookup"><span data-stu-id="895ee-204">Select the report to view, and then select **Show files**.</span></span>

    ![Visualizzazione dei file](./media/hr-benefits-management-aca-show-files.png)

5. <span data-ttu-id="895ee-206">Selezionare **Apri**.</span><span class="sxs-lookup"><span data-stu-id="895ee-206">Select **Open**.</span></span>

    ![Apertura di un file](./media/hr-benefits-management-aca-open-file.png)

6. <span data-ttu-id="895ee-208">Dalla barra di notifica che appare nella parte inferiore della finestra del browser, apri il file zip, quindi seleziona il report.</span><span class="sxs-lookup"><span data-stu-id="895ee-208">From the Notification bar that appears at the bottom of the browser window, open the zip file, and then select the report.</span></span> <span data-ttu-id="895ee-209">Puoi visualizzare o stampare il file PDF.</span><span class="sxs-lookup"><span data-stu-id="895ee-209">You can view or print the PDF file.</span></span>

    ![Modulo 1.095-C di esempio](./media/hr-benefits-management-aca-1095-c-form.png)

## <a name="view-aca-coverage-information"></a><span data-ttu-id="895ee-211">Visualizza le informazioni sulla copertura ACA</span><span class="sxs-lookup"><span data-stu-id="895ee-211">View ACA coverage information</span></span>

<span data-ttu-id="895ee-212">La pagina **Copertura Affordable Care del lavoratore** visualizza le seguenti informazioni:</span><span class="sxs-lookup"><span data-stu-id="895ee-212">The **Worker Affordable Care coverage** page shows the following information:</span></span>

- <span data-ttu-id="895ee-213">Dipendenti assegnati a ciascun gruppo di copertura</span><span class="sxs-lookup"><span data-stu-id="895ee-213">Employees who are assigned to each coverage group</span></span>
- <span data-ttu-id="895ee-214">Dipendenti che non devono essere inclusi in un report</span><span class="sxs-lookup"><span data-stu-id="895ee-214">Employees who don't have to be included on a report</span></span>
- <span data-ttu-id="895ee-215">Dipendenti non assegnati</span><span class="sxs-lookup"><span data-stu-id="895ee-215">Unassigned employees</span></span>

<span data-ttu-id="895ee-216">Per visualizzare queste informazioni, attenersi alla seguente procedura.</span><span class="sxs-lookup"><span data-stu-id="895ee-216">To view this information, follow these steps.</span></span>

1. <span data-ttu-id="895ee-217">Nell'area di lavoro **Gestione dei vantaggi**, seleziona **Copertura Affordable Care del lavoratore**.</span><span class="sxs-lookup"><span data-stu-id="895ee-217">In the **Benefits management** workspace, select **Worker Affordable Care coverage**.</span></span>
2. <span data-ttu-id="895ee-218">Nel campo **Nome gruppo** seleziona un gruppo.</span><span class="sxs-lookup"><span data-stu-id="895ee-218">In the **Group name** field, select a group.</span></span>

    ![Visualizzazione della copertura ACA](./media/hr-benefits-management-aca-view-coverage.png)

<span data-ttu-id="895ee-220">Se uno qualsiasi dei valori predefiniti del gruppo di copertura Affordable Care viene sovrascritto, un asterisco verrà visualizzato accanto al valore modificato.</span><span class="sxs-lookup"><span data-stu-id="895ee-220">If any default values from the Affordable Care coverage group have been overridden, an asterisk appears next to the value that was changed.</span></span> <span data-ttu-id="895ee-221">Se i valori per tutti i 12 mesi sono uguali e non sono stati ignorati, il valore verrà visualizzato nella colonna **Tutti i 12 mesi**.</span><span class="sxs-lookup"><span data-stu-id="895ee-221">If the values for all 12 months are the same and haven't been overridden, the value appears in the **All 12 months** column.</span></span>

<span data-ttu-id="895ee-222">Puoi visualizzare i dipendenti contrassegnati come non soggetti a report ACA e che non richiedono un modulo 1.095-C.</span><span class="sxs-lookup"><span data-stu-id="895ee-222">You can view employees who are marked as not ACA-reportable, and who won't require a Form 1095-C.</span></span> <span data-ttu-id="895ee-223">Nel campo **Filtra per**, seleziona **Non segnalabile ACA**.</span><span class="sxs-lookup"><span data-stu-id="895ee-223">In the **Filter by** field, select **Not ACA reportable**.</span></span>

<span data-ttu-id="895ee-224">Puoi visualizzare i dipendenti che non sono assegnati a un gruppo o che sono assegnati a un gruppo scaduto.</span><span class="sxs-lookup"><span data-stu-id="895ee-224">You can view employees who aren't assigned to a group, or who are assigned to an expired group.</span></span> <span data-ttu-id="895ee-225">Nel campo **Filtra per**, seleziona **Gruppo non assegnato o scaduto**.</span><span class="sxs-lookup"><span data-stu-id="895ee-225">In the **Filter by** field, select **Unassigned or expired group**.</span></span>

### <a name="export-to-excel"></a><span data-ttu-id="895ee-226">Esporta in Excel</span><span class="sxs-lookup"><span data-stu-id="895ee-226">Export to Excel</span></span>

<span data-ttu-id="895ee-227">Per esportare uno qualsiasi degli elenchi in Microsoft Excel, segui questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="895ee-227">To export any of the lists to Microsoft Excel, follow these steps.</span></span>

1. <span data-ttu-id="895ee-228">Selezionare il pulsante **Apri in Microsoft Office**.</span><span class="sxs-lookup"><span data-stu-id="895ee-228">Select the **Open in Microsoft Office** button.</span></span>
2. <span data-ttu-id="895ee-229">Seleziona **Tabella temporanea di Human Resources HCM per uso interno**.</span><span class="sxs-lookup"><span data-stu-id="895ee-229">Select **HCM Human Resources temporary table for internal use**.</span></span>
3. <span data-ttu-id="895ee-230">Selezionare **Scarica**.</span><span class="sxs-lookup"><span data-stu-id="895ee-230">Select **Download**.</span></span>

### <a name="view-aca-reportable-dependents"></a><span data-ttu-id="895ee-231">Visualizza i dipendenti segnalabili da ACA</span><span class="sxs-lookup"><span data-stu-id="895ee-231">View ACA-reportable dependents</span></span>

<span data-ttu-id="895ee-232">Se devi segnalare le persone coperte perché fornisci una copertura autoassicurata, puoi visualizzare le persone a carico che sono coperte da piani di benefit che sono contrassegnati come **ACA segnalabile**.</span><span class="sxs-lookup"><span data-stu-id="895ee-232">If you must report covered individuals because you provide self-insured coverage, you can view dependents who are covered under benefit plans that are marked as **ACA reportable**.</span></span> <span data-ttu-id="895ee-233">Nel riquadro azioni, seleziona **Visualizza copertura dipendente**.</span><span class="sxs-lookup"><span data-stu-id="895ee-233">On the Action Pane, select **View Dependent coverage**.</span></span>

![Visualizzazione della copertura dipendente](./media/hr-benefits-management-aca-view-dependent-coverage.png)

<span data-ttu-id="895ee-235">Vengono visualizzate le informazioni sulla copertura per le persone a carico del dipendente.</span><span class="sxs-lookup"><span data-stu-id="895ee-235">Coverage information for the employee's dependents is shown.</span></span>

![Copertura dei dipendenti](./media/hr-benefits-management-aca-dependents.png)

> [!NOTE]
> <span data-ttu-id="895ee-237">La pagina mostra solo i piani di benefit contrassegnati come **Segnalabile ACA**.</span><span class="sxs-lookup"><span data-stu-id="895ee-237">The page shows only benefits plans that are marked as **ACA reportable**.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]