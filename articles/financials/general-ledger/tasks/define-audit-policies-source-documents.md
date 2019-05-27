---
title: Definire i criteri di controllo per i documenti di origine
description: In questa procedura viene illustrato come impostare ed eseguire le regole dei criteri di controllo di esecuzione.
author: ryansandness
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysPolicySourceDocumentRuleType, SysFieldLookUp, SysPolicyListPage, SysPolicy, AuditPolicyRule, SysQueryForm, SysQueryFieldLookUp, AuditPolicyDateSelection, AuditPolicyAdditionalOption, BatchJob, CaseDetail
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: ryansand
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a82c3e8e8787beb309b75b73cda36f4ca8031d6f
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "1558885"
---
# <a name="define-audit-policies-for-source-documents"></a><span data-ttu-id="06753-103">Definire i criteri di controllo per i documenti di origine</span><span class="sxs-lookup"><span data-stu-id="06753-103">Define audit policies for source documents</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="06753-104">In questa procedura viene illustrato come impostare ed eseguire le regole dei criteri di controllo di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="06753-104">This procedure shows how to set up and run audit policy rules.</span></span> <span data-ttu-id="06753-105">Nell'esempio vengono utilizzate le note spese con il tipo di spesa di hotel.</span><span class="sxs-lookup"><span data-stu-id="06753-105">The example uses expense reports with the hotel expense type.</span></span> <span data-ttu-id="06753-106">Questa procedura utilizza la società dimostrativa USMF.</span><span class="sxs-lookup"><span data-stu-id="06753-106">This procedure uses the USMF demo company.</span></span> <span data-ttu-id="06753-107">Il ruolo del revisore contiene le autorizzazioni corrette per eseguire queste attività.</span><span class="sxs-lookup"><span data-stu-id="06753-107">The auditor role contains the correct permissions in order to perform these tasks.</span></span>

1. <span data-ttu-id="06753-108">Fare clic su Controllo workbench > Impostazione > Tipo di regola dei criteri.</span><span class="sxs-lookup"><span data-stu-id="06753-108">Go to Audit workbench > Setup > Policy rule type.</span></span>
2. <span data-ttu-id="06753-109">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="06753-109">Click New.</span></span>
3. <span data-ttu-id="06753-110">Digitare un valore nel campo Regola.</span><span class="sxs-lookup"><span data-stu-id="06753-110">In the Rule name field, type a value.</span></span>
4. <span data-ttu-id="06753-111">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="06753-111">In the Description field, type a value.</span></span>
5. <span data-ttu-id="06753-112">Nel campo Nome query selezionare Riga nota spese.</span><span class="sxs-lookup"><span data-stu-id="06753-112">In the Query name field, select Expense report line</span></span>
6. <span data-ttu-id="06753-113">Nel campo Tipo di query selezionare Aggrega</span><span class="sxs-lookup"><span data-stu-id="06753-113">In the query type field, select Aggregate</span></span>
7. <span data-ttu-id="06753-114">Nel campo Persona giuridica selezionare Persona giuridica.</span><span class="sxs-lookup"><span data-stu-id="06753-114">In the Legal entity field, select Legal entity</span></span>
8. <span data-ttu-id="06753-115">Nel campo Riferimento alla data del documento selezionare Data e ora modifica</span><span class="sxs-lookup"><span data-stu-id="06753-115">In the Document date reference field, select Modified date and time</span></span>
9. <span data-ttu-id="06753-116">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="06753-116">Click Save.</span></span>
10. <span data-ttu-id="06753-117">Fare clic su Controllo workbench > Impostazione > Criteri di controllo.</span><span class="sxs-lookup"><span data-stu-id="06753-117">Go to Audit workbench > Setup > Audit policies.</span></span>
11. <span data-ttu-id="06753-118">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="06753-118">Click New.</span></span>
12. <span data-ttu-id="06753-119">Digitare un valore nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="06753-119">In the Name field, type a value.</span></span>
13. <span data-ttu-id="06753-120">Espandere la sezione Organizzazioni criteri.</span><span class="sxs-lookup"><span data-stu-id="06753-120">Expand the Policy organizations section.</span></span>
14. <span data-ttu-id="06753-121">Nella struttura selezionare "Contoso Entertainment Systems USA"</span><span class="sxs-lookup"><span data-stu-id="06753-121">In the tree, select 'Contoso Entertainment System USA'.</span></span>
15. <span data-ttu-id="06753-122">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="06753-122">Click Add.</span></span>
16. <span data-ttu-id="06753-123">Nella struttura selezionare "Contoso Consulting USA".</span><span class="sxs-lookup"><span data-stu-id="06753-123">In the tree, select 'Contoso Consulting USA'.</span></span>
17. <span data-ttu-id="06753-124">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="06753-124">Click Add.</span></span>
18. <span data-ttu-id="06753-125">Nella struttura selezionare "Contoso Retail USA".</span><span class="sxs-lookup"><span data-stu-id="06753-125">In the tree, select 'Contoso Retail USA'.</span></span>
19. <span data-ttu-id="06753-126">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="06753-126">Click Add.</span></span>
20. <span data-ttu-id="06753-127">Comprimere la sezione Organizzazioni criteri.</span><span class="sxs-lookup"><span data-stu-id="06753-127">Collapse the Policy organizations section.</span></span>
21. <span data-ttu-id="06753-128">Espandere la sezione Regole dei criteri.</span><span class="sxs-lookup"><span data-stu-id="06753-128">Expand the Policy rules section.</span></span>
22. <span data-ttu-id="06753-129">Nell'elenco, individuare e selezionare la regola dei criteri creata in precedenza.</span><span class="sxs-lookup"><span data-stu-id="06753-129">In the list, find and select the Policy Rule that was created previously.</span></span>
23. <span data-ttu-id="06753-130">Fare clic su Crea regola dei criteri.</span><span class="sxs-lookup"><span data-stu-id="06753-130">Click Create policy rule.</span></span>
24. <span data-ttu-id="06753-131">Nel campo Data di validità immettere una data e un'ora.</span><span class="sxs-lookup"><span data-stu-id="06753-131">In the Effective date field, enter a date and time.</span></span>
25. <span data-ttu-id="06753-132">Fare clic su Filtro.</span><span class="sxs-lookup"><span data-stu-id="06753-132">Click Filter.</span></span>
26. <span data-ttu-id="06753-133">Nell'elenco, selezionare la riga per la categoria di spesa e impostare i dettagli su Hotel</span><span class="sxs-lookup"><span data-stu-id="06753-133">In the list, select the row for Expense category, and set the details to Hotel</span></span>
27. <span data-ttu-id="06753-134">Nel campo Criteri immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="06753-134">In the Criteria field, enter or select a value.</span></span>
28. <span data-ttu-id="06753-135">Fare clic sulla scheda Aggrega.</span><span class="sxs-lookup"><span data-stu-id="06753-135">Click the Aggregate tab.</span></span>
29. <span data-ttu-id="06753-136">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="06753-136">Click Add.</span></span>
30. <span data-ttu-id="06753-137">Nell'elenco, selezionare un valore del campo Importo transazione:</span><span class="sxs-lookup"><span data-stu-id="06753-137">In the list, select a field value of Transaction amount</span></span>
31. <span data-ttu-id="06753-138">Nel campo Campo immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="06753-138">In the Field field, enter or select a value.</span></span>
32. <span data-ttu-id="06753-139">Nel campo AggregateFunction selezionare "Somma".</span><span class="sxs-lookup"><span data-stu-id="06753-139">In the AggregateFunction field, select 'Sum'.</span></span>
33. <span data-ttu-id="06753-140">Fare clic sulla scheda Raggruppa per.</span><span class="sxs-lookup"><span data-stu-id="06753-140">Click the Group by tab.</span></span>
34. <span data-ttu-id="06753-141">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="06753-141">Click Add.</span></span>
35. <span data-ttu-id="06753-142">Nell'elenco selezionare un valore di Dipendente </span><span class="sxs-lookup"><span data-stu-id="06753-142">In the list, select a value of Employee</span></span> 
36. <span data-ttu-id="06753-143">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="06753-143">Click Add.</span></span>
37. <span data-ttu-id="06753-144">Nell'elenco selezionare un valore di Categoria di spesa</span><span class="sxs-lookup"><span data-stu-id="06753-144">In the list, select a value of Expense category</span></span>
38. <span data-ttu-id="06753-145">Nel campo Campo immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="06753-145">In the Field field, enter or select a value.</span></span>
39. <span data-ttu-id="06753-146">Fare clic sulla scheda Avere.</span><span class="sxs-lookup"><span data-stu-id="06753-146">Click the Having tab.</span></span>
40. <span data-ttu-id="06753-147">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="06753-147">Click Add.</span></span>
41. <span data-ttu-id="06753-148">Selezionare Importo transazione</span><span class="sxs-lookup"><span data-stu-id="06753-148">Select Transaction amount</span></span>
42. <span data-ttu-id="06753-149">Nel campo Campo immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="06753-149">In the Field field, enter or select a value.</span></span>
43. <span data-ttu-id="06753-150">Nel campo AggregateFunction selezionare "Somma".</span><span class="sxs-lookup"><span data-stu-id="06753-150">In the AggregateFunction field, select 'Sum'.</span></span>
44. <span data-ttu-id="06753-151">Nel campo Criteri digitare '>2000'.</span><span class="sxs-lookup"><span data-stu-id="06753-151">In the Criteria field, type '>2000'.</span></span>
45. <span data-ttu-id="06753-152">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="06753-152">Click OK.</span></span>
46. <span data-ttu-id="06753-153">Test di clic su Test.</span><span class="sxs-lookup"><span data-stu-id="06753-153">Click Test.</span></span>
47. <span data-ttu-id="06753-154">Nel campo Data iniziale di selezione documenti immettere una data e un'ora.</span><span class="sxs-lookup"><span data-stu-id="06753-154">In the Document selection starting date field, enter a date and time.</span></span>
48. <span data-ttu-id="06753-155">Nel campo Data finale di selezione documenti immettere una data e un'ora.</span><span class="sxs-lookup"><span data-stu-id="06753-155">In the Document selection ending date field, enter a date and time.</span></span>
49. <span data-ttu-id="06753-156">Fare clic su Esegui test.</span><span class="sxs-lookup"><span data-stu-id="06753-156">Click Run test.</span></span>
50. <span data-ttu-id="06753-157">Nel riquadro azioni, fare clic su Criteri di controllo.</span><span class="sxs-lookup"><span data-stu-id="06753-157">On the Action Pane, click Audit policy.</span></span>
51. <span data-ttu-id="06753-158">Fare clic su Opzioni aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="06753-158">Click Additional options.</span></span>
52. <span data-ttu-id="06753-159">Nel campo Data di inizio immettere una data e un'ora.</span><span class="sxs-lookup"><span data-stu-id="06753-159">In the Starting date field, enter a date and time.</span></span>
53. <span data-ttu-id="06753-160">Nel campo Data di fine immettere una data e un'ora.</span><span class="sxs-lookup"><span data-stu-id="06753-160">In the Ending date field, enter a date and time.</span></span>
54. <span data-ttu-id="06753-161">Fare clic su Batch.</span><span class="sxs-lookup"><span data-stu-id="06753-161">Click Batch.</span></span>
55. <span data-ttu-id="06753-162">Espandere la sezione Esecuzione in background.</span><span class="sxs-lookup"><span data-stu-id="06753-162">Expand the Run in the background section.</span></span>
56. <span data-ttu-id="06753-163">Selezionare Sì nel campo Elaborazione batch.</span><span class="sxs-lookup"><span data-stu-id="06753-163">Select Yes in the Batch processing field.</span></span>
57. <span data-ttu-id="06753-164">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="06753-164">Click OK.</span></span>
58. <span data-ttu-id="06753-165">Fare clic su Controllo workbench > Casi di controllo.</span><span class="sxs-lookup"><span data-stu-id="06753-165">Go to Audit workbench > Audit cases.</span></span>
59. <span data-ttu-id="06753-166">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="06753-166">In the list, find and select the desired record.</span></span>
60. <span data-ttu-id="06753-167">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="06753-167">In the list, click the link in the selected row.</span></span>
61. <span data-ttu-id="06753-168">Espandere la sezione Associazioni.</span><span class="sxs-lookup"><span data-stu-id="06753-168">Expand the Associations section.</span></span>
62. <span data-ttu-id="06753-169">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="06753-169">In the list, find and select the desired record.</span></span>
63. <span data-ttu-id="06753-170">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="06753-170">In the list, click the link in the selected row.</span></span>

