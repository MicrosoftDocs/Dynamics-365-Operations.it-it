--- 
title: Creare una gerarchia di report dell'organizzazione
description: Utilizzare questa procedura per creare una gerarchia di report per l'organizzazione.
author: YuyuScheller
manager: AnnBe
ms.date: 10/30/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: e57db8f4b692aa9c27916625897e268f63031782
ms.openlocfilehash: 995f61bd82ac08d057b41a6db735b6695aa34c33
ms.contentlocale: it-it
ms.lasthandoff: 10/30/2017

---
# <a name="create-an-organization-report-hierarchy"></a><span data-ttu-id="72e32-103">Creare una gerarchia di report dell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="72e32-103">Create an organization report hierarchy</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="72e32-104">Utilizzare questa procedura per creare una gerarchia di report per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="72e32-104">Use this procedure to create a report hierarchy for organization reporting.</span></span> <span data-ttu-id="72e32-105">Lo scopo di questa registrazione è quello di guidare l'utente nella gerarchia di dimensioni in modo che sia possibile continuare fino a quando non è creata l'intera struttura di reporting dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="72e32-105">The purpose of this recording is to guide you through the dimension hierarchy so that you can continue until the whole organization reporting structure is created.</span></span> <span data-ttu-id="72e32-106">Questa registrazione utilizza i dati dimostrativi della società USP2.</span><span class="sxs-lookup"><span data-stu-id="72e32-106">This recording uses the USP2 demo data company.</span></span>

1. <span data-ttu-id="72e32-107">Andare a Contabilità industriale > Dimensioni > Gerarchie di dimensioni.</span><span class="sxs-lookup"><span data-stu-id="72e32-107">Go to Cost accounting > Dimensions > Dimension hierarchies.</span></span>
2. <span data-ttu-id="72e32-108">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="72e32-108">Click New.</span></span>
3. <span data-ttu-id="72e32-109">Nel campo HierarchyTypeComboBox selezionare "Gerarchia classificazioni dimensione".</span><span class="sxs-lookup"><span data-stu-id="72e32-109">In the HierarchyTypeComboBox field, select 'Dimension classification hierarchy'.</span></span>
    * <span data-ttu-id="72e32-110">Selezionare Gerarchia classificazioni dimensione.</span><span class="sxs-lookup"><span data-stu-id="72e32-110">Select Dimension classification hierarchy.</span></span> <span data-ttu-id="72e32-111">Il tipo Gerarchia classificazioni dimensione viene utilizzato per definire regole e per il reporting.</span><span class="sxs-lookup"><span data-stu-id="72e32-111">The Dimension classification hierarchy type is used to define rules and for reporting purposes.</span></span> <span data-ttu-id="72e32-112">Supporta tutte le dimensioni, quali gli oggetti di costo, gli elementi di costo e le dimensioni statistiche.</span><span class="sxs-lookup"><span data-stu-id="72e32-112">It supports all dimensions, such as cost objects, cost elements, and statistical dimensions.</span></span>  
4. <span data-ttu-id="72e32-113">Fare clic su Crea.</span><span class="sxs-lookup"><span data-stu-id="72e32-113">Click Create.</span></span>
5. <span data-ttu-id="72e32-114">Nel campo Nome gerarchia dimensioni digitare "Organizzazione USP2".</span><span class="sxs-lookup"><span data-stu-id="72e32-114">In the Dimension hierarchy name field, type 'Oganization USP2'.</span></span>
6. <span data-ttu-id="72e32-115">Nel campo Dimensione immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="72e32-115">In the Dimension field, enter or select a value.</span></span>
    * <span data-ttu-id="72e32-116">Selezionare Centri di costo.</span><span class="sxs-lookup"><span data-stu-id="72e32-116">Select Cost centers.</span></span>  
7. <span data-ttu-id="72e32-117">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="72e32-117">Click Save.</span></span>
8. <span data-ttu-id="72e32-118">Fare clic su Visualizza gerarchia.</span><span class="sxs-lookup"><span data-stu-id="72e32-118">Click View hierarchy.</span></span>
9. <span data-ttu-id="72e32-119">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="72e32-119">Click New.</span></span>
10. <span data-ttu-id="72e32-120">Nel campo Nome nodo digitare "CEO".</span><span class="sxs-lookup"><span data-stu-id="72e32-120">In the Node name field, type 'CEO'.</span></span>
11. <span data-ttu-id="72e32-121">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="72e32-121">Click Save.</span></span>
12. <span data-ttu-id="72e32-122">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="72e32-122">Click New.</span></span>
13. <span data-ttu-id="72e32-123">Nel campo Nome nodo digitare "Centri di costo CEO".</span><span class="sxs-lookup"><span data-stu-id="72e32-123">In the Node name field, type 'CEO cost centers'.</span></span>
14. <span data-ttu-id="72e32-124">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="72e32-124">Click Save.</span></span>
15. <span data-ttu-id="72e32-125">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="72e32-125">Click New.</span></span>
16. <span data-ttu-id="72e32-126">Nel campo Nome nodo digitare "Area orientale".</span><span class="sxs-lookup"><span data-stu-id="72e32-126">In the Node name field, type 'Region East'.</span></span>
17. <span data-ttu-id="72e32-127">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="72e32-127">Click Save.</span></span>
18. <span data-ttu-id="72e32-128">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="72e32-128">Click New.</span></span>
19. <span data-ttu-id="72e32-129">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="72e32-129">In the list, mark the selected row.</span></span>
20. <span data-ttu-id="72e32-130">Nel campo Membro di dimensione di inizio immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="72e32-130">In the From dimension member field, enter or select a value.</span></span>
    * <span data-ttu-id="72e32-131">Selezionare il membro di dimensione corrispondente al nodo.</span><span class="sxs-lookup"><span data-stu-id="72e32-131">Select the dimension member that corresponds to the node.</span></span>  
21. <span data-ttu-id="72e32-132">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="72e32-132">Click Save.</span></span>
22. <span data-ttu-id="72e32-133">Nella struttura, selezionare "Organizzazione USP2\CEO\Centri di costo CEO".</span><span class="sxs-lookup"><span data-stu-id="72e32-133">In the tree, select 'Oganization USP2\CEO\CEO cost centers'.</span></span>
23. <span data-ttu-id="72e32-134">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="72e32-134">Click New.</span></span>
24. <span data-ttu-id="72e32-135">Nel campo Nome nodo digitare "Area occidentale".</span><span class="sxs-lookup"><span data-stu-id="72e32-135">In the Node name field, type 'Region West'.</span></span>
25. <span data-ttu-id="72e32-136">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="72e32-136">Click Save.</span></span>
26. <span data-ttu-id="72e32-137">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="72e32-137">Click New.</span></span>
27. <span data-ttu-id="72e32-138">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="72e32-138">In the list, mark the selected row.</span></span>
28. <span data-ttu-id="72e32-139">Nel campo Membro di dimensione di inizio immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="72e32-139">In the From dimension member field, enter or select a value.</span></span>
    * <span data-ttu-id="72e32-140">Selezionare il membro di dimensione corrispondente al nodo.</span><span class="sxs-lookup"><span data-stu-id="72e32-140">Select the dimension member that corresponds to the node.</span></span>  
29. <span data-ttu-id="72e32-141">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="72e32-141">Click Save.</span></span>
30. <span data-ttu-id="72e32-142">Nella struttura selezionare "Organizzazione USP2\CEO".</span><span class="sxs-lookup"><span data-stu-id="72e32-142">In the tree, select 'Oganization USP2\CEO'.</span></span>
31. <span data-ttu-id="72e32-143">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="72e32-143">Click New.</span></span>
32. <span data-ttu-id="72e32-144">Nel campo Nome nodo digitare "Centri di costo CFO".</span><span class="sxs-lookup"><span data-stu-id="72e32-144">In the Node name field, type 'CFO cost centers'.</span></span>
33. <span data-ttu-id="72e32-145">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="72e32-145">Click Save.</span></span>
34. <span data-ttu-id="72e32-146">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="72e32-146">Click New.</span></span>
35. <span data-ttu-id="72e32-147">Nel campo Nome nodo digitare "Campagna marketing".</span><span class="sxs-lookup"><span data-stu-id="72e32-147">In the Node name field, type 'Marketing campa'.</span></span>
36. <span data-ttu-id="72e32-148">Nel campo Nome nodo digitare "Campagna di marketing".</span><span class="sxs-lookup"><span data-stu-id="72e32-148">In the Node name field, type 'Marketing campaign'.</span></span>
37. <span data-ttu-id="72e32-149">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="72e32-149">Click Save.</span></span>
38. <span data-ttu-id="72e32-150">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="72e32-150">Click New.</span></span>
39. <span data-ttu-id="72e32-151">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="72e32-151">In the list, mark the selected row.</span></span>
40. <span data-ttu-id="72e32-152">Nel campo Membro di dimensione di inizio immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="72e32-152">In the From dimension member field, enter or select a value.</span></span>
    * <span data-ttu-id="72e32-153">Selezionare il membro di dimensione corrispondente al nodo.</span><span class="sxs-lookup"><span data-stu-id="72e32-153">Select the dimension member that corresponds to the node.</span></span>  
41. <span data-ttu-id="72e32-154">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="72e32-154">Click Save.</span></span>
42. <span data-ttu-id="72e32-155">Nella struttura, selezionare "Organizzazione USP2\CEO\Centri di costo CFO".</span><span class="sxs-lookup"><span data-stu-id="72e32-155">In the tree, select 'Organization USP2\CEO\CFO cost centers'.</span></span>
43. <span data-ttu-id="72e32-156">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="72e32-156">Click New.</span></span>
44. <span data-ttu-id="72e32-157">Nel campo Nome nodo digitare "Fiere commerciali".</span><span class="sxs-lookup"><span data-stu-id="72e32-157">In the Node name field, type 'Trade shows'.</span></span>
45. <span data-ttu-id="72e32-158">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="72e32-158">Click Save.</span></span>
46. <span data-ttu-id="72e32-159">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="72e32-159">Click New.</span></span>
47. <span data-ttu-id="72e32-160">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="72e32-160">In the list, mark the selected row.</span></span>
48. <span data-ttu-id="72e32-161">Nel campo Membro di dimensione di inizio immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="72e32-161">In the From dimension member field, enter or select a value.</span></span>
    * <span data-ttu-id="72e32-162">Selezionare il membro di dimensione corrispondente al nodo.</span><span class="sxs-lookup"><span data-stu-id="72e32-162">Select the dimension member that corresponds to the node.</span></span>  
49. <span data-ttu-id="72e32-163">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="72e32-163">Click Save.</span></span>
50. <span data-ttu-id="72e32-164">Nella struttura selezionare "Organizzazione USP2\CEO".</span><span class="sxs-lookup"><span data-stu-id="72e32-164">In the tree, select 'Oganization USP2\CEO'.</span></span>
51. <span data-ttu-id="72e32-165">Nel campo Nome nodo digitare "Centri di costo CIO".</span><span class="sxs-lookup"><span data-stu-id="72e32-165">In the Node name field, type 'CIO cost centers'.</span></span>
52. <span data-ttu-id="72e32-166">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="72e32-166">Click Save.</span></span>
53. <span data-ttu-id="72e32-167">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="72e32-167">Click New.</span></span>
54. <span data-ttu-id="72e32-168">Nel campo Nome nodo digitare "Call center".</span><span class="sxs-lookup"><span data-stu-id="72e32-168">In the Node name field, type 'Call centers'.</span></span>
55. <span data-ttu-id="72e32-169">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="72e32-169">Click Save.</span></span>
56. <span data-ttu-id="72e32-170">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="72e32-170">Click New.</span></span>
57. <span data-ttu-id="72e32-171">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="72e32-171">In the list, mark the selected row.</span></span>
58. <span data-ttu-id="72e32-172">Nel campo Membro di dimensione di inizio immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="72e32-172">In the From dimension member field, enter or select a value.</span></span>
    * <span data-ttu-id="72e32-173">Selezionare il membro di dimensione corrispondente al nodo.</span><span class="sxs-lookup"><span data-stu-id="72e32-173">Select the dimension member that corresponds to the node.</span></span>  
59. <span data-ttu-id="72e32-174">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="72e32-174">Click Save.</span></span>


