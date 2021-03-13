---
title: Definire i criteri di controllo per i documenti di origine
description: In questo argomento viene illustrato come impostare ed eseguire regole dei criteri di controllo.
author: panolte
manager: AnnBe
ms.date: 08/20/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysPolicySourceDocumentRuleType, SysFieldLookUp, SysPolicyListPage, SysPolicy, AuditPolicyRule, SysQueryForm, SysQueryFieldLookUp, AuditPolicyDateSelection, AuditPolicyAdditionalOption, BatchJob, CaseDetail
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e020a9e82ff18055e40e3e0ddc7bbed1068c886c
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/16/2021
ms.locfileid: "5021431"
---
# <a name="define-audit-policies-for-source-documents"></a><span data-ttu-id="6c1c7-103">Definire i criteri di controllo per i documenti di origine</span><span class="sxs-lookup"><span data-stu-id="6c1c7-103">Define audit policies for source documents</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="6c1c7-104">In questo argomento viene illustrato come impostare ed eseguire regole dei criteri di controllo.</span><span class="sxs-lookup"><span data-stu-id="6c1c7-104">This topic explains how to set up and run audit policy rules.</span></span> <span data-ttu-id="6c1c7-105">Nell'esempio vengono utilizzate le note spese con il tipo di spesa di hotel.</span><span class="sxs-lookup"><span data-stu-id="6c1c7-105">The example uses expense reports with the hotel expense type.</span></span> <span data-ttu-id="6c1c7-106">Questa procedura utilizza la società dimostrativa USMF.</span><span class="sxs-lookup"><span data-stu-id="6c1c7-106">This procedure uses the USMF demo company.</span></span> <span data-ttu-id="6c1c7-107">Il ruolo del revisore contiene le autorizzazioni corrette per eseguire queste attività.</span><span class="sxs-lookup"><span data-stu-id="6c1c7-107">The auditor role contains the correct permissions in order to perform these tasks.</span></span>

1. <span data-ttu-id="6c1c7-108">Nel pannello di navigazione, andare a **Moduli > Controllo workbench > Impostazione > Tipo di regola dei criteri**.</span><span class="sxs-lookup"><span data-stu-id="6c1c7-108">In the navigation pane, go to **Modules > Audit workbench > Setup > Policy rule type**.</span></span>
2. <span data-ttu-id="6c1c7-109">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="6c1c7-109">Select **New**.</span></span>
3. <span data-ttu-id="6c1c7-110">Nel campo **Nome regola** digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="6c1c7-110">In the **Rule name** field, type a value.</span></span>
4. <span data-ttu-id="6c1c7-111">Digitare un valore nel campo **Descrizione**</span><span class="sxs-lookup"><span data-stu-id="6c1c7-111">In the **Description** field, type a value.</span></span>
5. <span data-ttu-id="6c1c7-112">Nel campo **Nome query** selezionare **Riga nota spese**.</span><span class="sxs-lookup"><span data-stu-id="6c1c7-112">In the **Query name** field, select **Expense report line**</span></span>
6. <span data-ttu-id="6c1c7-113">Nel campo **Tipo di query** selezionare **Aggrega**.</span><span class="sxs-lookup"><span data-stu-id="6c1c7-113">In the **query type** field, select **Aggregate**</span></span>
7. <span data-ttu-id="6c1c7-114">Nel campo **Persona giuridica** selezionare **Persona giuridica**.</span><span class="sxs-lookup"><span data-stu-id="6c1c7-114">In the **Legal entity** field, select **Legal entity**</span></span>
8. <span data-ttu-id="6c1c7-115">Nel campo **Riferimento alla data del documento** selezionare **Data e ora modifica**.</span><span class="sxs-lookup"><span data-stu-id="6c1c7-115">In the **Document date reference** field, select **Modified date and time**</span></span>
9. <span data-ttu-id="6c1c7-116">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="6c1c7-116">Select **Save**.</span></span>
10. <span data-ttu-id="6c1c7-117">Nel pannello di navigazione, andare a **Moduli > Controllo workbench > Impostazione > Criteri di controllo**.</span><span class="sxs-lookup"><span data-stu-id="6c1c7-117">In the navigation pane, go to **Modules > Audit workbench > Setup > Audit policies**.</span></span>
11. <span data-ttu-id="6c1c7-118">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="6c1c7-118">Select **New**.</span></span>
12. <span data-ttu-id="6c1c7-119">Digitare un valore nel campo **Nome**.</span><span class="sxs-lookup"><span data-stu-id="6c1c7-119">In the **Name** field, type a value.</span></span>
13. <span data-ttu-id="6c1c7-120">Espandere la sezione **Organizzazioni criteri**.</span><span class="sxs-lookup"><span data-stu-id="6c1c7-120">Expand the **Policy organizations** section.</span></span>
14. <span data-ttu-id="6c1c7-121">Nella struttura selezionare **Contoso Entertainment Systems USA**, quindi selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="6c1c7-121">In the tree, select **Contoso Entertainment System USA**, then select **Add**.</span></span>
15. <span data-ttu-id="6c1c7-122">Nella struttura selezionare **Contoso Consulting USA**, quindi selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="6c1c7-122">In the tree, select **Contoso Consulting USA**, then select **Add**.</span></span>
16. <span data-ttu-id="6c1c7-123">Nella struttura selezionare **Contoso Retail USA**, quindi selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="6c1c7-123">In the tree, select **Contoso Retail USA**, then select **Add**.</span></span>
17. <span data-ttu-id="6c1c7-124">Comprimere la sezione **Organizzazioni criteri**.</span><span class="sxs-lookup"><span data-stu-id="6c1c7-124">Collapse the **Policy organizations** section.</span></span>
18. <span data-ttu-id="6c1c7-125">Espandere la sezione **Regole dei criteri**.</span><span class="sxs-lookup"><span data-stu-id="6c1c7-125">Expand the **Policy rules** section.</span></span>
19. <span data-ttu-id="6c1c7-126">Nell'elenco, individuare e selezionare la regola dei criteri creata in precedenza.</span><span class="sxs-lookup"><span data-stu-id="6c1c7-126">In the list, find and select the Policy Rule that was created previously.</span></span>
20. <span data-ttu-id="6c1c7-127">Selezionare **Crea regola dei criteri**.</span><span class="sxs-lookup"><span data-stu-id="6c1c7-127">Select **Create policy rule**.</span></span>
21. <span data-ttu-id="6c1c7-128">Nel campo **Data di validità** immettere una data e un'ora.</span><span class="sxs-lookup"><span data-stu-id="6c1c7-128">In the **Effective date** field, enter a date and time.</span></span>
22. <span data-ttu-id="6c1c7-129">Selezionare **Filtro**.</span><span class="sxs-lookup"><span data-stu-id="6c1c7-129">Select **Filter**.</span></span>
23. <span data-ttu-id="6c1c7-130">Nell'elenco, selezionare la riga per **Categoria di spesa** e impostare i dettagli su **Hotel**.</span><span class="sxs-lookup"><span data-stu-id="6c1c7-130">In the list, select the row for **Expense category**, and set the details to **Hotel**.</span></span>
24. <span data-ttu-id="6c1c7-131">Nel campo **Criteri** immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="6c1c7-131">In the **Criteria** field, enter or select a value.</span></span>
25. <span data-ttu-id="6c1c7-132">Selezionare la scheda **Aggrega**.</span><span class="sxs-lookup"><span data-stu-id="6c1c7-132">Select the **Aggregate** tab.</span></span>
26. <span data-ttu-id="6c1c7-133">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="6c1c7-133">Select **Add**.</span></span>
27. <span data-ttu-id="6c1c7-134">Nell'elenco, selezionare un valore di **Importo transazione**.</span><span class="sxs-lookup"><span data-stu-id="6c1c7-134">In the list, select a field value of **Transaction amount**.</span></span>
28. <span data-ttu-id="6c1c7-135">Nel campo **Campo** immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="6c1c7-135">In the **Field** field, enter or select a value.</span></span>
29. <span data-ttu-id="6c1c7-136">Nel campo **AggregateFunction** selezionare **Somma**.</span><span class="sxs-lookup"><span data-stu-id="6c1c7-136">In the **AggregateFunction** field, select **Sum**.</span></span>
30. <span data-ttu-id="6c1c7-137">Selezionare la scheda **Raggruppa per**.</span><span class="sxs-lookup"><span data-stu-id="6c1c7-137">Select the **Group by** tab.</span></span>
31. <span data-ttu-id="6c1c7-138">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="6c1c7-138">Select **Add**.</span></span>
32. <span data-ttu-id="6c1c7-139">Nell'elenco selezionare un valore di **Dipendente**.</span><span class="sxs-lookup"><span data-stu-id="6c1c7-139">In the list, select a value of **Employee** .</span></span>
33. <span data-ttu-id="6c1c7-140">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="6c1c7-140">Select **Add**.</span></span>
34. <span data-ttu-id="6c1c7-141">Nell'elenco selezionare un valore di **Categoria di spesa**.</span><span class="sxs-lookup"><span data-stu-id="6c1c7-141">In the list, select a value of **Expense category**.</span></span>
35. <span data-ttu-id="6c1c7-142">Nel campo **Campo** immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="6c1c7-142">In the **Field** field, enter or select a value.</span></span>
36. <span data-ttu-id="6c1c7-143">Selezionare la scheda **Avere**.</span><span class="sxs-lookup"><span data-stu-id="6c1c7-143">Select the **Having** tab.</span></span>
37. <span data-ttu-id="6c1c7-144">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="6c1c7-144">Select **Add**.</span></span>
38. <span data-ttu-id="6c1c7-145">Selezionare **Importo transazione**.</span><span class="sxs-lookup"><span data-stu-id="6c1c7-145">Select **Transaction amount**.</span></span>
39. <span data-ttu-id="6c1c7-146">Nel campo **Campo** immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="6c1c7-146">In the **Field** field, enter or select a value.</span></span>
40. <span data-ttu-id="6c1c7-147">Nel campo **AggregateFunction** selezionare **Somma**.</span><span class="sxs-lookup"><span data-stu-id="6c1c7-147">In the **AggregateFunction** field, select **Sum**.</span></span>
41. <span data-ttu-id="6c1c7-148">Nel campo **Criteri** digitare `>2000`.</span><span class="sxs-lookup"><span data-stu-id="6c1c7-148">In the **Criteria** field, type `>2000`.</span></span>
42. <span data-ttu-id="6c1c7-149">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="6c1c7-149">Select **OK**.</span></span>
43. <span data-ttu-id="6c1c7-150">Selezionare **Test**.</span><span class="sxs-lookup"><span data-stu-id="6c1c7-150">Select **Test**.</span></span>
44. <span data-ttu-id="6c1c7-151">Nel campo **Data iniziale di selezione documenti** immettere una data e un'ora.</span><span class="sxs-lookup"><span data-stu-id="6c1c7-151">In the **Document selection starting date** field, enter a date and time.</span></span>
45. <span data-ttu-id="6c1c7-152">Nel campo **Data finale di selezione documenti** immettere una data e un'ora.</span><span class="sxs-lookup"><span data-stu-id="6c1c7-152">In the **Document selection ending date** field, enter a date and time.</span></span>
46. <span data-ttu-id="6c1c7-153">Selezionare **Esegui test**.</span><span class="sxs-lookup"><span data-stu-id="6c1c7-153">Select **Run test**.</span></span>
47. <span data-ttu-id="6c1c7-154">Nel riquadro azioni, selezionare **Criteri di controllo**.</span><span class="sxs-lookup"><span data-stu-id="6c1c7-154">On the Action Pane, select **Audit policy**.</span></span>
48. <span data-ttu-id="6c1c7-155">Selezionare **Opzioni aggiuntive**.</span><span class="sxs-lookup"><span data-stu-id="6c1c7-155">Select **Additional options**.</span></span>
49. <span data-ttu-id="6c1c7-156">Nel campo **Data di inizio** immettere una data e un'ora.</span><span class="sxs-lookup"><span data-stu-id="6c1c7-156">In the **Starting date** field, enter a date and time.</span></span>
50. <span data-ttu-id="6c1c7-157">Nel campo **Data di fine** immettere una data e un'ora.</span><span class="sxs-lookup"><span data-stu-id="6c1c7-157">In the **Ending date** field, enter a date and time.</span></span>
51. <span data-ttu-id="6c1c7-158">Selezionare **Batch**.</span><span class="sxs-lookup"><span data-stu-id="6c1c7-158">Select **Batch**.</span></span>
52. <span data-ttu-id="6c1c7-159">Espandere la sezione **Esecuzione in background**.</span><span class="sxs-lookup"><span data-stu-id="6c1c7-159">Expand the **Run in the background** section.</span></span>
53. <span data-ttu-id="6c1c7-160">Selezionare **Sì** nel campo **Elaborazione batch**.</span><span class="sxs-lookup"><span data-stu-id="6c1c7-160">Select **Yes** in the **Batch processing** field.</span></span>
54. <span data-ttu-id="6c1c7-161">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="6c1c7-161">Select **OK**.</span></span>
55. <span data-ttu-id="6c1c7-162">Nel pannello di navigazione, andare a **Moduli > Controllo workbench > Casi di controllo**.</span><span class="sxs-lookup"><span data-stu-id="6c1c7-162">In the navigation pane, go to **Modules > Audit workbench > Audit cases**.</span></span>
56. <span data-ttu-id="6c1c7-163">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="6c1c7-163">In the list, find and select the desired record.</span></span>
57. <span data-ttu-id="6c1c7-164">Espandere la sezione **Associazioni**.</span><span class="sxs-lookup"><span data-stu-id="6c1c7-164">Expand the **Associations** section.</span></span>
58. <span data-ttu-id="6c1c7-165">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="6c1c7-165">In the list, find and select the desired record.</span></span>

