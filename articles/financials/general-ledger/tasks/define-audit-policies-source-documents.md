--- 
title: Definire i criteri di controllo per i documenti di origine
description: In questa procedura viene illustrato come impostare ed eseguire le regole dei criteri di controllo di esecuzione.
author: ryansandness
manager: AnnBe
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: ryansand
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 4b05f744120e940bfea3e92b8aac3e41fc8151d9
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---
# <a name="define-audit-policies-for-source-documents"></a><span data-ttu-id="abc87-103">Definire i criteri di controllo per i documenti di origine</span><span class="sxs-lookup"><span data-stu-id="abc87-103">Define audit policies for source documents</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="abc87-104">In questa procedura viene illustrato come impostare ed eseguire le regole dei criteri di controllo di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="abc87-104">This procedure shows how to set up and run audit policy rules.</span></span> <span data-ttu-id="abc87-105">Nell'esempio vengono utilizzate le note spese con il tipo di spesa di hotel.</span><span class="sxs-lookup"><span data-stu-id="abc87-105">The example uses expense reports with the hotel expense type.</span></span> <span data-ttu-id="abc87-106">Questa procedura utilizza la società dimostrativa USMF.</span><span class="sxs-lookup"><span data-stu-id="abc87-106">This procedure uses the USMF demo company.</span></span> <span data-ttu-id="abc87-107">Il ruolo del revisore contiene le autorizzazioni corrette per eseguire queste attività.</span><span class="sxs-lookup"><span data-stu-id="abc87-107">The auditor role contains the correct permissions in order to perform these tasks.</span></span>

1. <span data-ttu-id="abc87-108">Fare clic su Controllo workbench > Impostazione > Tipo di regola dei criteri.</span><span class="sxs-lookup"><span data-stu-id="abc87-108">Go to Audit workbench > Setup > Policy rule type.</span></span>
2. <span data-ttu-id="abc87-109">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="abc87-109">Click New.</span></span>
3. <span data-ttu-id="abc87-110">Digitare un valore nel campo Regola.</span><span class="sxs-lookup"><span data-stu-id="abc87-110">In the Rule name field, type a value.</span></span>
4. <span data-ttu-id="abc87-111">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="abc87-111">In the Description field, type a value.</span></span>
5. <span data-ttu-id="abc87-112">Nel campo Nome query selezionare Riga nota spese.</span><span class="sxs-lookup"><span data-stu-id="abc87-112">In the Query name field, select Expense report line</span></span>
6. <span data-ttu-id="abc87-113">Nel campo Tipo di query selezionare Aggrega</span><span class="sxs-lookup"><span data-stu-id="abc87-113">In the query type field, select Aggregate</span></span>
7. <span data-ttu-id="abc87-114">Nel campo Persona giuridica selezionare Persona giuridica.</span><span class="sxs-lookup"><span data-stu-id="abc87-114">In the Legal entity field, select Legal entity</span></span>
8. <span data-ttu-id="abc87-115">Nel campo Riferimento alla data del documento selezionare Data e ora modifica</span><span class="sxs-lookup"><span data-stu-id="abc87-115">In the Document date reference field, select Modified date and time</span></span>
9. <span data-ttu-id="abc87-116">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="abc87-116">Click Save.</span></span>
10. <span data-ttu-id="abc87-117">Fare clic su Controllo workbench > Impostazione > Criteri di controllo.</span><span class="sxs-lookup"><span data-stu-id="abc87-117">Go to Audit workbench > Setup > Audit policies.</span></span>
11. <span data-ttu-id="abc87-118">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="abc87-118">Click New.</span></span>
12. <span data-ttu-id="abc87-119">Digitare un valore nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="abc87-119">In the Name field, type a value.</span></span>
13. <span data-ttu-id="abc87-120">Espandere la sezione Organizzazioni criteri.</span><span class="sxs-lookup"><span data-stu-id="abc87-120">Expand the Policy organizations section.</span></span>
14. <span data-ttu-id="abc87-121">Nella struttura selezionare "Contoso Entertainment Systems USA"</span><span class="sxs-lookup"><span data-stu-id="abc87-121">In the tree, select 'Contoso Entertainment System USA'.</span></span>
15. <span data-ttu-id="abc87-122">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="abc87-122">Click Add.</span></span>
16. <span data-ttu-id="abc87-123">Nella struttura selezionare "Contoso Consulting USA".</span><span class="sxs-lookup"><span data-stu-id="abc87-123">In the tree, select 'Contoso Consulting USA'.</span></span>
17. <span data-ttu-id="abc87-124">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="abc87-124">Click Add.</span></span>
18. <span data-ttu-id="abc87-125">Nella struttura selezionare "Contoso Retail USA".</span><span class="sxs-lookup"><span data-stu-id="abc87-125">In the tree, select 'Contoso Retail USA'.</span></span>
19. <span data-ttu-id="abc87-126">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="abc87-126">Click Add.</span></span>
20. <span data-ttu-id="abc87-127">Comprimere la sezione Organizzazioni criteri.</span><span class="sxs-lookup"><span data-stu-id="abc87-127">Collapse the Policy organizations section.</span></span>
21. <span data-ttu-id="abc87-128">Espandere la sezione Regole dei criteri.</span><span class="sxs-lookup"><span data-stu-id="abc87-128">Expand the Policy rules section.</span></span>
22. <span data-ttu-id="abc87-129">Nell'elenco, individuare e selezionare la regola dei criteri creata in precedenza.</span><span class="sxs-lookup"><span data-stu-id="abc87-129">In the list, find and select the Policy Rule that was created previously.</span></span>
23. <span data-ttu-id="abc87-130">Fare clic su Crea regola dei criteri.</span><span class="sxs-lookup"><span data-stu-id="abc87-130">Click Create policy rule.</span></span>
24. <span data-ttu-id="abc87-131">Nel campo Data di validità immettere una data e un'ora.</span><span class="sxs-lookup"><span data-stu-id="abc87-131">In the Effective date field, enter a date and time.</span></span>
25. <span data-ttu-id="abc87-132">Fare clic su Filtro.</span><span class="sxs-lookup"><span data-stu-id="abc87-132">Click Filter.</span></span>
26. <span data-ttu-id="abc87-133">Nell'elenco, selezionare la riga per la categoria di spesa e impostare i dettagli su Hotel</span><span class="sxs-lookup"><span data-stu-id="abc87-133">In the list, select the row for Expense category, and set the details to Hotel</span></span>
27. <span data-ttu-id="abc87-134">Nel campo Criteri immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="abc87-134">In the Criteria field, enter or select a value.</span></span>
28. <span data-ttu-id="abc87-135">Fare clic sulla scheda Aggrega.</span><span class="sxs-lookup"><span data-stu-id="abc87-135">Click the Aggregate tab.</span></span>
29. <span data-ttu-id="abc87-136">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="abc87-136">Click Add.</span></span>
30. <span data-ttu-id="abc87-137">Nell'elenco, selezionare un valore del campo Importo transazione:</span><span class="sxs-lookup"><span data-stu-id="abc87-137">In the list, select a field value of Transaction amount</span></span>
31. <span data-ttu-id="abc87-138">Nel campo Campo immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="abc87-138">In the Field field, enter or select a value.</span></span>
32. <span data-ttu-id="abc87-139">Nel campo AggregateFunction selezionare "Somma".</span><span class="sxs-lookup"><span data-stu-id="abc87-139">In the AggregateFunction field, select 'Sum'.</span></span>
33. <span data-ttu-id="abc87-140">Fare clic sulla scheda Raggruppa per.</span><span class="sxs-lookup"><span data-stu-id="abc87-140">Click the Group by tab.</span></span>
34. <span data-ttu-id="abc87-141">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="abc87-141">Click Add.</span></span>
35. <span data-ttu-id="abc87-142">Nell'elenco selezionare un valore di Dipendente </span><span class="sxs-lookup"><span data-stu-id="abc87-142">In the list, select a value of Employee</span></span> 
36. <span data-ttu-id="abc87-143">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="abc87-143">Click Add.</span></span>
37. <span data-ttu-id="abc87-144">Nell'elenco selezionare un valore di Categoria di spesa</span><span class="sxs-lookup"><span data-stu-id="abc87-144">In the list, select a value of Expense category</span></span>
38. <span data-ttu-id="abc87-145">Nel campo Campo immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="abc87-145">In the Field field, enter or select a value.</span></span>
39. <span data-ttu-id="abc87-146">Fare clic sulla scheda Avere.</span><span class="sxs-lookup"><span data-stu-id="abc87-146">Click the Having tab.</span></span>
40. <span data-ttu-id="abc87-147">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="abc87-147">Click Add.</span></span>
41. <span data-ttu-id="abc87-148">Selezionare Importo transazione</span><span class="sxs-lookup"><span data-stu-id="abc87-148">Select Transaction amount</span></span>
42. <span data-ttu-id="abc87-149">Nel campo Campo immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="abc87-149">In the Field field, enter or select a value.</span></span>
43. <span data-ttu-id="abc87-150">Nel campo AggregateFunction selezionare "Somma".</span><span class="sxs-lookup"><span data-stu-id="abc87-150">In the AggregateFunction field, select 'Sum'.</span></span>
44. <span data-ttu-id="abc87-151">Nel campo Criteri digitare '>2000'.</span><span class="sxs-lookup"><span data-stu-id="abc87-151">In the Criteria field, type '>2000'.</span></span>
45. <span data-ttu-id="abc87-152">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="abc87-152">Click OK.</span></span>
46. <span data-ttu-id="abc87-153">Test di clic su Test.</span><span class="sxs-lookup"><span data-stu-id="abc87-153">Click Test.</span></span>
47. <span data-ttu-id="abc87-154">Nel campo Data iniziale di selezione documenti immettere una data e un'ora.</span><span class="sxs-lookup"><span data-stu-id="abc87-154">In the Document selection starting date field, enter a date and time.</span></span>
48. <span data-ttu-id="abc87-155">Nel campo Data finale di selezione documenti immettere una data e un'ora.</span><span class="sxs-lookup"><span data-stu-id="abc87-155">In the Document selection ending date field, enter a date and time.</span></span>
49. <span data-ttu-id="abc87-156">Fare clic su Esegui test.</span><span class="sxs-lookup"><span data-stu-id="abc87-156">Click Run test.</span></span>
50. <span data-ttu-id="abc87-157">Nel riquadro azioni, fare clic su Criteri di controllo.</span><span class="sxs-lookup"><span data-stu-id="abc87-157">On the Action Pane, click Audit policy.</span></span>
51. <span data-ttu-id="abc87-158">Fare clic su Opzioni aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="abc87-158">Click Additional options.</span></span>
52. <span data-ttu-id="abc87-159">Nel campo Data di inizio immettere una data e un'ora.</span><span class="sxs-lookup"><span data-stu-id="abc87-159">In the Starting date field, enter a date and time.</span></span>
53. <span data-ttu-id="abc87-160">Nel campo Data di fine immettere una data e un'ora.</span><span class="sxs-lookup"><span data-stu-id="abc87-160">In the Ending date field, enter a date and time.</span></span>
54. <span data-ttu-id="abc87-161">Fare clic su Batch.</span><span class="sxs-lookup"><span data-stu-id="abc87-161">Click Batch.</span></span>
55. <span data-ttu-id="abc87-162">Espandere la sezione Esecuzione in background.</span><span class="sxs-lookup"><span data-stu-id="abc87-162">Expand the Run in the background section.</span></span>
56. <span data-ttu-id="abc87-163">Selezionare Sì nel campo Elaborazione batch.</span><span class="sxs-lookup"><span data-stu-id="abc87-163">Select Yes in the Batch processing field.</span></span>
57. <span data-ttu-id="abc87-164">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="abc87-164">Click OK.</span></span>
58. <span data-ttu-id="abc87-165">Fare clic su Controllo workbench > Casi di controllo.</span><span class="sxs-lookup"><span data-stu-id="abc87-165">Go to Audit workbench > Audit cases.</span></span>
59. <span data-ttu-id="abc87-166">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="abc87-166">In the list, find and select the desired record.</span></span>
60. <span data-ttu-id="abc87-167">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="abc87-167">In the list, click the link in the selected row.</span></span>
61. <span data-ttu-id="abc87-168">Espandere la sezione Associazioni.</span><span class="sxs-lookup"><span data-stu-id="abc87-168">Expand the Associations section.</span></span>
62. <span data-ttu-id="abc87-169">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="abc87-169">In the list, find and select the desired record.</span></span>
63. <span data-ttu-id="abc87-170">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="abc87-170">In the list, click the link in the selected row.</span></span>


