---
title: Creare contratti avanzati per la fatturazione in base allo stato di avanzamento
description: Questo argomento spiega come creare contratti di progetto in modo da poter generare fatture per i clienti, in base a una percentuale del lavoro completato.
author: RadhikaRS
manager: AnnBe
ms.date: 03/26/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Service industries
ms.author: v-radsh
ms.dyn365.ops.version: 7
ms.search.validFrom: 2019-01-15
ms.openlocfilehash: 90cae104d0abad909606ef6a0e0c45ed95e74de2
ms.sourcegitcommit: dfef2faf881b2db1bd0f016df36e2b838105312b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/22/2020
ms.locfileid: "3282833"
---
# <a name="create-advanced-contracts-for-billing-based-on-progress"></a><span data-ttu-id="ee45e-103">Creare contratti avanzati per la fatturazione in base allo stato di avanzamento</span><span class="sxs-lookup"><span data-stu-id="ee45e-103">Create advanced contracts for billing based on progress</span></span>
[!include [banner](../includes/banner.md)]

<span data-ttu-id="ee45e-104">Questo argomento spiega come creare contratti di progetto in modo da poter creare fatture per i clienti, in base a una percentuale del lavoro completato.</span><span class="sxs-lookup"><span data-stu-id="ee45e-104">This topic explains how to create project contracts so that you can create invoices for customers, based on a percentage of completed work.</span></span> <span data-ttu-id="ee45e-105">Gli importi della fattura per le categorie di budget di lavoro, impostati per un progetto, vengono calcolati automaticamente,</span><span class="sxs-lookup"><span data-stu-id="ee45e-105">Invoice amounts are automatically calculated for the budget categories of work that you set up for a project.</span></span> <span data-ttu-id="ee45e-106">La tempistica della fattura viene impostata quando si negozia il contratto di progetto con il cliente.</span><span class="sxs-lookup"><span data-stu-id="ee45e-106">The invoice timing is set when you negotiate the project contract with the customer.</span></span>

<span data-ttu-id="ee45e-107">Utilizzare le seguenti procedure per impostare un contratto, un progetto associato e le regole di fatturazione da utilizzare per calcolare gli importi della fattura per le categorie di budget di lavoro impostate per il progetto.</span><span class="sxs-lookup"><span data-stu-id="ee45e-107">Use the procedures in this topic to set up a contract, an associated project, and the billing rules that calculate invoice amounts for the budget categories of work that you set up for the project.</span></span>

<span data-ttu-id="ee45e-108">Dopo avere creato il contratto e il progetto, è possibile impostare i dettagli del progetto.</span><span class="sxs-lookup"><span data-stu-id="ee45e-108">After you've created the contract and the project, you can set up the details of the project.</span></span> <span data-ttu-id="ee45e-109">Ad esempio, è possibile definire attività e assegnare lavoratori al progetto.</span><span class="sxs-lookup"><span data-stu-id="ee45e-109">For example, you can define activities and assign workers to the project.</span></span>

## <a name="example"></a><span data-ttu-id="ee45e-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="ee45e-110">Example</span></span>

<span data-ttu-id="ee45e-111">L'organizzazione dell'utente è una società di sviluppo software</span><span class="sxs-lookup"><span data-stu-id="ee45e-111">Your organization is a software development firm.</span></span> <span data-ttu-id="ee45e-112">Si concorda quindi di sviluppare un pacchetto di contabilità salariale per un cliente per una commissione totale di 20.000 dollari USA (USD).</span><span class="sxs-lookup"><span data-stu-id="ee45e-112">You agree to develop a payroll accounting package for a customer for a total fee of 20,000 US dollars (USD).</span></span> <span data-ttu-id="ee45e-113">L'organizzazione accetta di fatturare al cliente man mano che si completano specifiche percentuali del progetto.</span><span class="sxs-lookup"><span data-stu-id="ee45e-113">Your organization agrees to invoice the customer as you complete specific percentages of the project.</span></span> <span data-ttu-id="ee45e-114">È possibile impostare le seguenti categorie di progetti per il lavoro, in modo da poterle utilizzare nel processo di fatturazione:</span><span class="sxs-lookup"><span data-stu-id="ee45e-114">You set up the following project categories for the work, so that you can use them in the billing process:</span></span>

- <span data-ttu-id="ee45e-115">Consulenza</span><span class="sxs-lookup"><span data-stu-id="ee45e-115">Consulting</span></span>
- <span data-ttu-id="ee45e-116">Progetta</span><span class="sxs-lookup"><span data-stu-id="ee45e-116">Design</span></span>
- <span data-ttu-id="ee45e-117">Installazione</span><span class="sxs-lookup"><span data-stu-id="ee45e-117">Installation</span></span>

<span data-ttu-id="ee45e-118">È inoltre possibile impostare regole di fatturazione che calcolano automaticamente gli importi delle fatture per la percentuale di lavoro di progetto completata in ciascuna categoria.</span><span class="sxs-lookup"><span data-stu-id="ee45e-118">You also set up billing rules that automatically calculate the invoice amounts for the percentage of project work that is completed in each category.</span></span>

<span data-ttu-id="ee45e-119">Il responsabile budget creerà un budget per le categorie di progetto.</span><span class="sxs-lookup"><span data-stu-id="ee45e-119">The budget manager creates a budget for the project categories.</span></span> <span data-ttu-id="ee45e-120">L'importo relativo al lavoro completato viene automaticamente calcolato come percentuale di lavoro effettivo rispetto agli importi a budget.</span><span class="sxs-lookup"><span data-stu-id="ee45e-120">The amount of completed work is automatically calculated as a percentage of actual work in comparison to the budgeted amounts.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ee45e-121">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="ee45e-121">Prerequisites</span></span>

<span data-ttu-id="ee45e-122">Prima di creare un progetto che utilizza regole di fatturazione, è necessario impostare le sequenze numeriche per le regole di fatturazione e un giornale di registrazione delle commissioni che viene utilizzato per la registrazione delle fatturazioni progressive.</span><span class="sxs-lookup"><span data-stu-id="ee45e-122">Before you create a project that uses billing rules, you must set up the number sequences for billing rules and a fee journal that is used to post progress billings.</span></span>

1. <span data-ttu-id="ee45e-123">Andare a **Gestione progetti e contabilità** \> **Impostazione** \> **Parametri Gestione progetti e contabilità**.</span><span class="sxs-lookup"><span data-stu-id="ee45e-123">Go to **Project management and accounting** \> **Setup** \> **Project management and accounting parameters**.</span></span>
2. <span data-ttu-id="ee45e-124">Nella pagina **Parametri Gestione progetti e contabilità**, nella scheda **Sequenze numeriche**, impostare la sequenza numerica che si desidera utilizzare nel momento in cui vengono create le regole di fatturazione.</span><span class="sxs-lookup"><span data-stu-id="ee45e-124">On the **Project management and accounting parameters** page, on the **Number sequences** tab, set up the number sequence that you want to use when billing rules are created.</span></span>
3. <span data-ttu-id="ee45e-125">Andare a **Gestione progetti e contabilità** \> **Giornali di registrazione** \> **Commissioni**.</span><span class="sxs-lookup"><span data-stu-id="ee45e-125">Go to **Project management and accounting** \> **Journals** \> **Fee**.</span></span>
4. <span data-ttu-id="ee45e-126">Nella pagina **Giornale di registrazione commissioni**, selezionare **Nuovo** e inserire il nome del giornale.</span><span class="sxs-lookup"><span data-stu-id="ee45e-126">On the **Fee journal** page, select **New**, and enter the journal name.</span></span>

## <a name="create-a-contract-for-progress-billings"></a><span data-ttu-id="ee45e-127">Creare un contratto per fatturazioni progressive</span><span class="sxs-lookup"><span data-stu-id="ee45e-127">Create a contract for progress billings</span></span>

<span data-ttu-id="ee45e-128">Utilizzare questa procedura per creare un contratto di progetto per un progetto a prezzo fisso.</span><span class="sxs-lookup"><span data-stu-id="ee45e-128">Use this procedure to create a project contract for a fixed-price project.</span></span> <span data-ttu-id="ee45e-129">Creare una fattura di progetto quando il lavoro nel progetto è completato e raggiunge una specifica percentuale.</span><span class="sxs-lookup"><span data-stu-id="ee45e-129">You create a project invoice when the work that is completed on the project reaches a specified percentage.</span></span>

1. <span data-ttu-id="ee45e-130">Passare a **Gestione progetti e contabilità** \> **Progetti** \> **Contratti di progetto**.</span><span class="sxs-lookup"><span data-stu-id="ee45e-130">Go to **Project management and accounting** \> **Projects** \> **Project contracts**.</span></span>
2. <span data-ttu-id="ee45e-131">Nella pagina **Contratti di progetto**, selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="ee45e-131">On the **Project contracts** page, select **New**.</span></span>
3. <span data-ttu-id="ee45e-132">Nella finestra di dialogo **Nuovo contratto di progetto**, impostare i seguenti campi:</span><span class="sxs-lookup"><span data-stu-id="ee45e-132">In the **New project contract** dialog box, set the following fields:</span></span>

    - <span data-ttu-id="ee45e-133">**Nome**</span><span class="sxs-lookup"><span data-stu-id="ee45e-133">**Name**</span></span>
    - <span data-ttu-id="ee45e-134">**Tipo di finanziamento**</span><span class="sxs-lookup"><span data-stu-id="ee45e-134">**Funding type**</span></span>
    - <span data-ttu-id="ee45e-135">**Fonte di finanziamento**</span><span class="sxs-lookup"><span data-stu-id="ee45e-135">**Funding source**</span></span>
    - <span data-ttu-id="ee45e-136">**Valuta di vendita** – Per impostazione predefinita, questa valuta viene utilizzata per le fatture dei clienti che sono associate al contratto di progetto.</span><span class="sxs-lookup"><span data-stu-id="ee45e-136">**Sales currency** – By default, this currency is used for customer invoices that are associated with the project contract.</span></span> <span data-ttu-id="ee45e-137">Tuttavia, è possibile cambiare la valuta di vendita su una fattura cliente specifico.</span><span class="sxs-lookup"><span data-stu-id="ee45e-137">However, you can change the sales currency on a specific customer invoice.</span></span>

4. <span data-ttu-id="ee45e-138">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="ee45e-138">Select **OK**.</span></span> <span data-ttu-id="ee45e-139">Le informazioni vengono copiate nell'intestazione della pagina **Contratti di progetto**.</span><span class="sxs-lookup"><span data-stu-id="ee45e-139">The information is copied to the header of the **Project contracts** page.</span></span>
5. <span data-ttu-id="ee45e-140">Nella pagina **Contratti di progetto**, inserire il resto delle informazioni richieste per il progetto.</span><span class="sxs-lookup"><span data-stu-id="ee45e-140">On the **Project contracts** page, fill in the rest of the required information for the project.</span></span>

## <a name="create-a-project-for-progress-billings"></a><span data-ttu-id="ee45e-141">Creare un progetto per le fatturazioni progressive</span><span class="sxs-lookup"><span data-stu-id="ee45e-141">Create a project for progress billings</span></span>

<span data-ttu-id="ee45e-142">Seguire i seguenti passaggi per creare un progetto e tutti i sottoprogetti associati a un contratto di progetto.</span><span class="sxs-lookup"><span data-stu-id="ee45e-142">Follow these steps to create a project and any subprojects that are associated with a project contract.</span></span>

1. <span data-ttu-id="ee45e-143">Passare a **Gestione progetti e contabilità** \> **Progetti** \> **Tutti i progetti**.</span><span class="sxs-lookup"><span data-stu-id="ee45e-143">Go to **Project management and accounting** \> **Projects** \> **All projects**.</span></span>
2. <span data-ttu-id="ee45e-144">Nella pagina **Tutti i progetti**, selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="ee45e-144">On the **All projects** page, select **New**.</span></span>
3. <span data-ttu-id="ee45e-145">Nella finestra di dialogo **Nuovo progetto**, nel campo **Tipo di progetto**, selezionare **Tempistica e materiali**.</span><span class="sxs-lookup"><span data-stu-id="ee45e-145">In the **New project** dialog box, in the **Project type** field, select **Time and material**.</span></span>
4. <span data-ttu-id="ee45e-146">Consente di selezionare un tipo di gruppo di progetti.</span><span class="sxs-lookup"><span data-stu-id="ee45e-146">Select a project group.</span></span> <span data-ttu-id="ee45e-147">Un gruppo di progetti definisce le informazioni di registrazione per i progetti assegnati al gruppo.</span><span class="sxs-lookup"><span data-stu-id="ee45e-147">A project group defines the posting information for the projects that are assigned to the group.</span></span>
5. <span data-ttu-id="ee45e-148">Selezionare **Crea progetto**.</span><span class="sxs-lookup"><span data-stu-id="ee45e-148">Select **Create project**.</span></span>
6. <span data-ttu-id="ee45e-149">Dopo avere creato il progetto, impostare la fase di progetto su **In corso**.</span><span class="sxs-lookup"><span data-stu-id="ee45e-149">After the project is created, set the project stage to **In process**.</span></span>

## <a name="create-a-budget-for-a-project"></a><span data-ttu-id="ee45e-150">Creare un budget per un progetto.</span><span class="sxs-lookup"><span data-stu-id="ee45e-150">Create a budget for a project</span></span>

<span data-ttu-id="ee45e-151">Le categorie di budget vengono utilizzate per calcolare automaticamente gli importi delle fatture per la percentuale di lavoro completata per ciascuna categoria.</span><span class="sxs-lookup"><span data-stu-id="ee45e-151">Budget categories are used to automatically calculate the invoice amounts for the percentage of work that is completed for each category.</span></span> <span data-ttu-id="ee45e-152">Seguire questi passaggi per creare delle categorie di budget per i costi stimati.</span><span class="sxs-lookup"><span data-stu-id="ee45e-152">Follow these steps to create budget categories for the estimated costs.</span></span>

1. <span data-ttu-id="ee45e-153">Passare a **Gestione progetti e contabilità** \> **Progetti** \> **Tutti i progetti**.</span><span class="sxs-lookup"><span data-stu-id="ee45e-153">Go to **Project management and accounting** \> **Projects** \> **All projects**.</span></span>
2. <span data-ttu-id="ee45e-154">Nella pagina **Tutti i progetti**, selezionare e aprire il progetto desiderato.</span><span class="sxs-lookup"><span data-stu-id="ee45e-154">On the **All projects** page, select and open the project that you want.</span></span>
3. <span data-ttu-id="ee45e-155">Nella pagina **Progetti**, nel riquadro azioni, nella scheda **Pianificare** nel gruppo **Budget**, selezionare **Budget del progetto**.</span><span class="sxs-lookup"><span data-stu-id="ee45e-155">On the **Projects** page, on the Action Pane, on the **Plan** tab, in the **Budget** group, select **Project budget**.</span></span>
4. <span data-ttu-id="ee45e-156">Nella pagina **Budget del progetto**, immettere un costo stimato per ogni categoria nel progetto.</span><span class="sxs-lookup"><span data-stu-id="ee45e-156">On the **Project budget** page, enter an estimated cost for each category in the project.</span></span>

## <a name="create-billing-rules-for-progress-billings"></a><span data-ttu-id="ee45e-157">Creare regole per fatturazioni progressive</span><span class="sxs-lookup"><span data-stu-id="ee45e-157">Create billing rules for progress billings</span></span>

1. <span data-ttu-id="ee45e-158">Passare a **Gestione progetti e contabilità** \> **Progetti** \> **Contratti di progetto**.</span><span class="sxs-lookup"><span data-stu-id="ee45e-158">Go to **Project management and accounting** \> **Projects** \> **Project contracts**.</span></span>
2. <span data-ttu-id="ee45e-159">Nella pagina **Contratti di progetto**, selezionare e aprire un contratto di progetto.</span><span class="sxs-lookup"><span data-stu-id="ee45e-159">On the **Project contracts** page, select and open a project contract.</span></span>
3. <span data-ttu-id="ee45e-160">Nella pagina del contratto di progetto, nella scheda dettaglio **Regole di fatturazione**, selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="ee45e-160">On the project contract page, on the **Billing rules** FastTab, select **Add**.</span></span>
4. <span data-ttu-id="ee45e-161">Nella pagina **Regola di fatturazione**, nel campo **Tipo di riga**, selezionare **Avanzamento**.</span><span class="sxs-lookup"><span data-stu-id="ee45e-161">On the **Billing rule** page, in the **Line type** field, select **Progress**.</span></span>
5. <span data-ttu-id="ee45e-162">Nella scheda dettaglio **Dettagli regola di fatturazione**, nel campo **Valore di contratto** , immettere il valore totale del contratto.</span><span class="sxs-lookup"><span data-stu-id="ee45e-162">On the **Billing rule line details** FastTab, in the **Contract value** field, enter the total value of the contract.</span></span>
6. <span data-ttu-id="ee45e-163">Nel campo **Categorie** selezionare la categoria in cui registrare la transazione.</span><span class="sxs-lookup"><span data-stu-id="ee45e-163">In the **Category** field, select the category to post the fee transaction to.</span></span>
7. <span data-ttu-id="ee45e-164">Nel campo **Progetto** selezionare il progetto che utilizza questa regola di fatturazione.</span><span class="sxs-lookup"><span data-stu-id="ee45e-164">In the **Project** field, select the project that uses this billing rule.</span></span>
8. <span data-ttu-id="ee45e-165">Facoltativo: Assegnare la regola di fatturazione a progetti aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="ee45e-165">Optional: Assign the billing rule to additional projects.</span></span> <span data-ttu-id="ee45e-166">Nella scheda dettaglio **Progetto**, nella sezione **Progetti disponibili**, selezionare un progetto, quindi selezionare il pulsante freccia a destra per aggiungere il progetto alla sezione **Progetti selezionati**.</span><span class="sxs-lookup"><span data-stu-id="ee45e-166">On the **Project** FastTab, in the **Available projects** section, select a project, and then select the right arrow button to add the project to the **Selected projects** section.</span></span>
9. <span data-ttu-id="ee45e-167">Facoltativo: calcolare l'importo percentuale che il cliente trattiene dai pagamenti su una fattura.</span><span class="sxs-lookup"><span data-stu-id="ee45e-167">Optional: Calculate the percentage amount that the customer withholds from payments on an invoice.</span></span> <span data-ttu-id="ee45e-168">Nella scheda dettaglio **Condizioni di ritenuta sul pagamento**, selezionare la fonte di finanziamento, quindi nel campo **Percentuale ritenuta** , immettere la percentuale di ritenuta.</span><span class="sxs-lookup"><span data-stu-id="ee45e-168">On the **Payment retention terms** FastTab, select the funding source, and then, in the **Retention percentage** field, enter the retention percentage.</span></span>
10. <span data-ttu-id="ee45e-169">Ripetere la procedura per creare regole di fatturazione aggiuntive al contratto di progetto.</span><span class="sxs-lookup"><span data-stu-id="ee45e-169">Repeat these steps to create additional billing rules for the project contract.</span></span>
