---
title: 'ER Utilizzare le dimensioni finanziarie come origine dati (Parte 3: progettare il report)'
description: I passaggi seguenti descrivono come un utente con ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può configurare un modello per la creazione di report elettronici in modo che utilizzi dimensioni finanziarie come origine dati per i report elettronici.
author: NickSelin
manager: AnnBe
ms.date: 05/27/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERSolutionTable, ERSolutionCreateDropDialog, EROperationDesigner, ERComponentTypeDropDialog
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: cef61787e50561eaac4fd52741ab5f90d9c4171d
ms.sourcegitcommit: d9125c20b21459076e4fd92fd9ebfe2e53a0431b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "3406499"
---
# <a name="er-use-financial-dimensions-as-a-data-source-part-3---design-the-report"></a><span data-ttu-id="5ce38-103">ER Utilizzare le dimensioni finanziarie come origine dati (Parte 3: progettare il report)</span><span class="sxs-lookup"><span data-stu-id="5ce38-103">ER Use financial dimensions as a data source (Part 3 - Design the report)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="5ce38-104">I passaggi seguenti descrivono come un utente con ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può configurare un modello per la creazione di report elettronici in modo che utilizzi dimensioni finanziarie come origine dati per i report elettronici.</span><span class="sxs-lookup"><span data-stu-id="5ce38-104">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) model to use financial dimensions as a data source for ER reports.</span></span> <span data-ttu-id="5ce38-105">Questi passaggi possono essere eseguiti in qualsiasi società.</span><span class="sxs-lookup"><span data-stu-id="5ce38-105">These steps can be performed in any company.</span></span>

<span data-ttu-id="5ce38-106">Per effettuare questi passaggi, è innanzitutto necessario completare i passaggi nella procedura "ER Usare dimensioni finanziarie come origine dati (parte 2: mapping del modello)".</span><span class="sxs-lookup"><span data-stu-id="5ce38-106">To complete these steps, you must first complete the steps in the "ER Use financial dimensions as a data source (Part 2: Model mapping)" procedure.</span></span>


## <a name="design-a-report-to-present-financial-dimensions"></a><span data-ttu-id="5ce38-107">Progettare un report per presentare dimensioni finanziarie</span><span class="sxs-lookup"><span data-stu-id="5ce38-107">Design a report to present financial dimensions</span></span>
1. <span data-ttu-id="5ce38-108">Passare a Amministrazione organizzazione > Reporting elettronico > Configurazioni.</span><span class="sxs-lookup"><span data-stu-id="5ce38-108">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="5ce38-109">Nella struttura selezionare 'Modello di esempio dimensioni finanziarie'.</span><span class="sxs-lookup"><span data-stu-id="5ce38-109">In the tree, select 'Financial dimensions sample model'.</span></span>
3. <span data-ttu-id="5ce38-110">Fare clic su Crea configurazione per aprire la finestra di dialogo a discesa .</span><span class="sxs-lookup"><span data-stu-id="5ce38-110">Click Create configuration to open the drop dialog.</span></span>
4. <span data-ttu-id="5ce38-111">Nel campo Nuovo immettere 'Formato basato sul modello dati Modello di esempio dimensioni finanziarie'.</span><span class="sxs-lookup"><span data-stu-id="5ce38-111">In the New field, enter 'Format based on data model Financial dimensions sample model'.</span></span>
    * <span data-ttu-id="5ce38-112">Utilizzare il modello creato in anticipo come origine dati per il nuovo report.</span><span class="sxs-lookup"><span data-stu-id="5ce38-112">Use the model that was created in advance as the data source for your new report.</span></span>  
5. <span data-ttu-id="5ce38-113">Nel campo Nome digitare 'Report dei giornali di registrazione di contabilità generale'.</span><span class="sxs-lookup"><span data-stu-id="5ce38-113">In the Name field, type 'Ledger journal report'.</span></span>
6. <span data-ttu-id="5ce38-114">Selezionare Voce nel campo Definizione modello dati.</span><span class="sxs-lookup"><span data-stu-id="5ce38-114">In the Data model definition field, select Entry.</span></span>
7. <span data-ttu-id="5ce38-115">Fare clic su Crea configurazione.</span><span class="sxs-lookup"><span data-stu-id="5ce38-115">Click Create configuration.</span></span>
8. <span data-ttu-id="5ce38-116">Fare clic su Progettazione.</span><span class="sxs-lookup"><span data-stu-id="5ce38-116">Click Designer.</span></span>
9. <span data-ttu-id="5ce38-117">Fare clic su Aggiungi radice per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="5ce38-117">Click Add root to open the drop dialog.</span></span>
10. <span data-ttu-id="5ce38-118">Nella struttura selezionare "XML\Elemento".</span><span class="sxs-lookup"><span data-stu-id="5ce38-118">In the tree, select 'XML\Element'.</span></span>
11. <span data-ttu-id="5ce38-119">Digitare 'Nodo principale' nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="5ce38-119">In the Name field, type 'Root'.</span></span>
12. <span data-ttu-id="5ce38-120">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="5ce38-120">Click OK.</span></span>
13. <span data-ttu-id="5ce38-121">Fare clic su Aggiungi per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="5ce38-121">Click Add to open the drop dialog.</span></span>
14. <span data-ttu-id="5ce38-122">Nella struttura selezionare "XML\Attributo".</span><span class="sxs-lookup"><span data-stu-id="5ce38-122">In the tree, select 'XML\Attribute'.</span></span>
15. <span data-ttu-id="5ce38-123">Nel campo Nome digitare "Società".</span><span class="sxs-lookup"><span data-stu-id="5ce38-123">In the Name field, type 'Company'.</span></span>
16. <span data-ttu-id="5ce38-124">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="5ce38-124">Click OK.</span></span>
17. <span data-ttu-id="5ce38-125">Fare clic su Aggiungi per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="5ce38-125">Click Add to open the drop dialog.</span></span>
18. <span data-ttu-id="5ce38-126">Nella struttura selezionare "XML\Elemento".</span><span class="sxs-lookup"><span data-stu-id="5ce38-126">In the tree, select 'XML\Element'.</span></span>
19. <span data-ttu-id="5ce38-127">Digitare 'Giornale di registrazione' nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="5ce38-127">In the Name field, type 'Journal'.</span></span>
20. <span data-ttu-id="5ce38-128">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="5ce38-128">Click OK.</span></span>
21. <span data-ttu-id="5ce38-129">Nella struttura selezionare 'Nodo principale: Elemento XML\Giornale di registrazione: Elemento XML'.</span><span class="sxs-lookup"><span data-stu-id="5ce38-129">In the tree, select 'Root: XML Element\Journal: XML Element'.</span></span>
22. <span data-ttu-id="5ce38-130">Fare clic su Aggiungi per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="5ce38-130">Click Add to open the drop dialog.</span></span>
23. <span data-ttu-id="5ce38-131">Nella struttura selezionare "XML\Attributo".</span><span class="sxs-lookup"><span data-stu-id="5ce38-131">In the tree, select 'XML\Attribute'.</span></span>
24. <span data-ttu-id="5ce38-132">Digitare 'Batch'. nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="5ce38-132">In the Name field, type 'Batch'.</span></span>
25. <span data-ttu-id="5ce38-133">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="5ce38-133">Click OK.</span></span>
26. <span data-ttu-id="5ce38-134">Fare clic su Aggiungi per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="5ce38-134">Click Add to open the drop dialog.</span></span>
27. <span data-ttu-id="5ce38-135">Nella struttura selezionare "XML\Elemento".</span><span class="sxs-lookup"><span data-stu-id="5ce38-135">In the tree, select 'XML\Element'.</span></span>
28. <span data-ttu-id="5ce38-136">Nel campo Nome digitare 'Transazione'.</span><span class="sxs-lookup"><span data-stu-id="5ce38-136">In the Name field, type 'Transaction'.</span></span>
29. <span data-ttu-id="5ce38-137">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="5ce38-137">Click OK.</span></span>
30. <span data-ttu-id="5ce38-138">Nella struttura selezionare 'Nodo principale: Elemento XML\Giornale di registrazione: Elemento XML\Transazione: Elemento XML'.</span><span class="sxs-lookup"><span data-stu-id="5ce38-138">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element'.</span></span>
31. <span data-ttu-id="5ce38-139">Fare clic su Aggiungi per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="5ce38-139">Click Add to open the drop dialog.</span></span>
32. <span data-ttu-id="5ce38-140">Nella struttura selezionare "XML\Attributo".</span><span class="sxs-lookup"><span data-stu-id="5ce38-140">In the tree, select 'XML\Attribute'.</span></span>
33. <span data-ttu-id="5ce38-141">Digitare 'Giustificativo' nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="5ce38-141">In the Name field, type 'Voucher'.</span></span>
34. <span data-ttu-id="5ce38-142">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="5ce38-142">Click OK.</span></span>
35. <span data-ttu-id="5ce38-143">Fare clic su Aggiungi attributo.</span><span class="sxs-lookup"><span data-stu-id="5ce38-143">Click Add Attribute.</span></span>
36. <span data-ttu-id="5ce38-144">Digitare 'Data' nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="5ce38-144">In the Name field, type 'Date'.</span></span>
37. <span data-ttu-id="5ce38-145">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="5ce38-145">Click OK.</span></span>
38. <span data-ttu-id="5ce38-146">Fare clic su Aggiungi attributo.</span><span class="sxs-lookup"><span data-stu-id="5ce38-146">Click Add Attribute.</span></span>
39. <span data-ttu-id="5ce38-147">Nel campo Nome digitare "Valuta".</span><span class="sxs-lookup"><span data-stu-id="5ce38-147">In the Name field, type 'Currency'.</span></span>
40. <span data-ttu-id="5ce38-148">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="5ce38-148">Click OK.</span></span>
41. <span data-ttu-id="5ce38-149">Fare clic su Aggiungi attributo.</span><span class="sxs-lookup"><span data-stu-id="5ce38-149">Click Add Attribute.</span></span>
42. <span data-ttu-id="5ce38-150">Nel campo Nome digitare 'Dare'.</span><span class="sxs-lookup"><span data-stu-id="5ce38-150">In the Name field, type 'Dt'.</span></span>
43. <span data-ttu-id="5ce38-151">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="5ce38-151">Click OK.</span></span>
44. <span data-ttu-id="5ce38-152">Fare clic su Aggiungi attributo.</span><span class="sxs-lookup"><span data-stu-id="5ce38-152">Click Add Attribute.</span></span>
45. <span data-ttu-id="5ce38-153">Nel campo Nome digitare 'Avere'.</span><span class="sxs-lookup"><span data-stu-id="5ce38-153">In the Name field, type 'Ct'.</span></span>
46. <span data-ttu-id="5ce38-154">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="5ce38-154">Click OK.</span></span>
47. <span data-ttu-id="5ce38-155">Fare clic su Aggiungi per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="5ce38-155">Click Add to open the drop dialog.</span></span>
48. <span data-ttu-id="5ce38-156">Nella struttura selezionare "XML\Elemento".</span><span class="sxs-lookup"><span data-stu-id="5ce38-156">In the tree, select 'XML\Element'.</span></span>
49. <span data-ttu-id="5ce38-157">Digitare 'Dimensioni' nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="5ce38-157">In the Name field, type 'Dimensions'.</span></span>
50. <span data-ttu-id="5ce38-158">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="5ce38-158">Click OK.</span></span>
51. <span data-ttu-id="5ce38-159">Nella struttura selezionare 'Nodo principale: Elemento XML\Giornale di registrazione: Elemento XML\Transazione: Elemento XML\Dimensioni: Elemento XML'.</span><span class="sxs-lookup"><span data-stu-id="5ce38-159">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element'.</span></span>
52. <span data-ttu-id="5ce38-160">Fare clic su Aggiungi per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="5ce38-160">Click Add to open the drop dialog.</span></span>
53. <span data-ttu-id="5ce38-161">Nella struttura selezionare "XML\Attributo".</span><span class="sxs-lookup"><span data-stu-id="5ce38-161">In the tree, select 'XML\Attribute'.</span></span>
54. <span data-ttu-id="5ce38-162">Digitare 'Codice' nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="5ce38-162">In the Name field, type 'Code'.</span></span>
55. <span data-ttu-id="5ce38-163">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="5ce38-163">Click OK.</span></span>
56. <span data-ttu-id="5ce38-164">Fare clic su Aggiungi attributo.</span><span class="sxs-lookup"><span data-stu-id="5ce38-164">Click Add Attribute.</span></span>
57. <span data-ttu-id="5ce38-165">Nel campo Nome digitare 'Valore'.</span><span class="sxs-lookup"><span data-stu-id="5ce38-165">In the Name field, type 'Value'.</span></span>
58. <span data-ttu-id="5ce38-166">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="5ce38-166">Click OK.</span></span>
59. <span data-ttu-id="5ce38-167">Fare clic su Aggiungi attributo.</span><span class="sxs-lookup"><span data-stu-id="5ce38-167">Click Add Attribute.</span></span>
60. <span data-ttu-id="5ce38-168">Nel campo Nome digitare 'Descrizione'.</span><span class="sxs-lookup"><span data-stu-id="5ce38-168">In the Name field, type 'Desc'.</span></span>
61. <span data-ttu-id="5ce38-169">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="5ce38-169">Click OK.</span></span>
<span data-ttu-id="5ce38-170">![Pagina della progettazione delle operazioni ER](../media/er-financial-dimensions-guides-format1.png)</span><span class="sxs-lookup"><span data-stu-id="5ce38-170">![ER Operations designer page](../media/er-financial-dimensions-guides-format1.png)</span></span>

## <a name="map-report-elements-to-data-sources"></a><span data-ttu-id="5ce38-171">Mappare gli elementi del report alle origini dati</span><span class="sxs-lookup"><span data-stu-id="5ce38-171">Map report elements to data sources</span></span>
1. <span data-ttu-id="5ce38-172">Fare clic sulla scheda Mapping.</span><span class="sxs-lookup"><span data-stu-id="5ce38-172">Click the Mapping tab.</span></span>
2. <span data-ttu-id="5ce38-173">Nella struttura, espandere 'modello: Modello dati Modello di esempio dimensioni finanziarie'.</span><span class="sxs-lookup"><span data-stu-id="5ce38-173">In the tree, expand 'model: Data model Financial dimensions sample model'.</span></span>
3. <span data-ttu-id="5ce38-174">Nella struttura, espandere 'modello: Modello dati Modello di esempio dimensioni finanziarie\Giornale di registrazione: Elenco di record'.</span><span class="sxs-lookup"><span data-stu-id="5ce38-174">In the tree, expand 'model: Data model Financial dimensions sample model\Journal: Record list'.</span></span>
4. <span data-ttu-id="5ce38-175">Nella struttura, espandere 'modello: Modello dati Modello di esempio dimensioni finanziarie\Giornale di registrazione: Elenco di record\Transazione: Elenco di record'.</span><span class="sxs-lookup"><span data-stu-id="5ce38-175">In the tree, expand 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list'.</span></span>
5. <span data-ttu-id="5ce38-176">Nella struttura, espandere 'modello: Modello dati Modello di esempio dimensioni finanziarie\Giornale di registrazione: Elenco di record\Transazione: Elenco di record\Dati dimensioni: Elenco di record'.</span><span class="sxs-lookup"><span data-stu-id="5ce38-176">In the tree, expand 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list'.</span></span>
6. <span data-ttu-id="5ce38-177">Nella struttura selezionare 'Nodo principale: Elemento XML\Giornale di registrazione: Elemento XML\Transazione: Elemento XML\Dimensioni: Elemento XML\Descrizione: Attributo XML'.</span><span class="sxs-lookup"><span data-stu-id="5ce38-177">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element\Desc: XML Attribute'.</span></span>
7. <span data-ttu-id="5ce38-178">Nella struttura, selezionare 'modello: Modello dati Modello di esempio dimensioni finanziarie\Giornale di registrazione: Elenco di record\Transazione: Elenco di record\Dati dimensioni: Elenco di record\Descrizione: Stringa'.</span><span class="sxs-lookup"><span data-stu-id="5ce38-178">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list\Description: String'.</span></span>
8. <span data-ttu-id="5ce38-179">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="5ce38-179">Click Bind.</span></span>
9. <span data-ttu-id="5ce38-180">Nella struttura selezionare 'Nodo principale: Elemento XML\Giornale di registrazione: Elemento XML\Transazione: Elemento XML\Dimensioni: Elemento XML\Valore: Attributo XML'.</span><span class="sxs-lookup"><span data-stu-id="5ce38-180">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element\Value: XML Attribute'.</span></span>
10. <span data-ttu-id="5ce38-181">Nella struttura, selezionare 'modello: Modello dati Modello di esempio dimensioni finanziarie\Giornale di registrazione: Elenco di record\Transazione: Elenco di record\Dati dimensioni: Elenco di record\Codice: Stringa'.</span><span class="sxs-lookup"><span data-stu-id="5ce38-181">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list\Code: String'.</span></span>
11. <span data-ttu-id="5ce38-182">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="5ce38-182">Click Bind.</span></span>
12. <span data-ttu-id="5ce38-183">Nella struttura selezionare 'Nodo principale: Elemento XML\Giornale di registrazione: Elemento XML\Transazione: Elemento XML\Dimensioni: Elemento XML\Codice: Attributo XML'.</span><span class="sxs-lookup"><span data-stu-id="5ce38-183">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element\Code: XML Attribute'.</span></span>
13. <span data-ttu-id="5ce38-184">Nella struttura, selezionare 'modello: Modello dati Modello di esempio dimensioni finanziarie\Giornale di registrazione: Elenco di record\Transazione: Elenco di record\Dati dimensioni: Elenco di record\Nome: Stringa'.</span><span class="sxs-lookup"><span data-stu-id="5ce38-184">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list\Name: String'.</span></span>
14. <span data-ttu-id="5ce38-185">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="5ce38-185">Click Bind.</span></span>
15. <span data-ttu-id="5ce38-186">Nella struttura, selezionare 'modello: Modello dati Modello di esempio dimensioni finanziarie\Giornale di registrazione: Elenco di record\Transazione: Elenco di record\Dati dimensioni: Elenco di record'.</span><span class="sxs-lookup"><span data-stu-id="5ce38-186">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list'.</span></span>
16. <span data-ttu-id="5ce38-187">Nella struttura selezionare 'Nodo principale: Elemento XML\Giornale di registrazione: Elemento XML\Transazione: Elemento XML\Dimensioni: Elemento XML'.</span><span class="sxs-lookup"><span data-stu-id="5ce38-187">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element'.</span></span>
17. <span data-ttu-id="5ce38-188">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="5ce38-188">Click Bind.</span></span>
18. <span data-ttu-id="5ce38-189">Nella struttura selezionare 'Nodo principale: Elemento XML\Giornale di registrazione: Elemento XML\Transazione: Elemento XML\Avere: Attributo XML'.</span><span class="sxs-lookup"><span data-stu-id="5ce38-189">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Ct: XML Attribute'.</span></span>
19. <span data-ttu-id="5ce38-190">Nella struttura, selezionare 'modello: Modello dati Modello di esempio dimensioni finanziarie\Giornale di registrazione: Elenco di record\Transazione: Elenco di record\Avere: Reale'.</span><span class="sxs-lookup"><span data-stu-id="5ce38-190">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Credit: Real'.</span></span>
20. <span data-ttu-id="5ce38-191">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="5ce38-191">Click Bind.</span></span>
21. <span data-ttu-id="5ce38-192">Nella struttura selezionare 'Nodo principale: Elemento XML\Giornale di registrazione: Elemento XML\Transazione: Elemento XML\Dare: Attributo XML'.</span><span class="sxs-lookup"><span data-stu-id="5ce38-192">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dt: XML Attribute'.</span></span>
22. <span data-ttu-id="5ce38-193">Nella struttura, selezionare 'modello: Modello dati Modello di esempio dimensioni finanziarie\Giornale di registrazione: Elenco di record\Transazione: Elenco di record\Dare: Reale'.</span><span class="sxs-lookup"><span data-stu-id="5ce38-193">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Debit: Real'.</span></span>
23. <span data-ttu-id="5ce38-194">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="5ce38-194">Click Bind.</span></span>
24. <span data-ttu-id="5ce38-195">Nella struttura selezionare 'Nodo principale: Elemento XML\Giornale di registrazione: Elemento XML\Transazione: Elemento XML\Valuta: Attributo XML'.</span><span class="sxs-lookup"><span data-stu-id="5ce38-195">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Currency: XML Attribute'.</span></span>
25. <span data-ttu-id="5ce38-196">Nella struttura, selezionare 'modello: Modello dati Modello di esempio dimensioni finanziarie\Giornale di registrazione: Elenco di record\Transazione: Elenco di record\Valuta: Stringa'.</span><span class="sxs-lookup"><span data-stu-id="5ce38-196">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Currency: String'.</span></span>
26. <span data-ttu-id="5ce38-197">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="5ce38-197">Click Bind.</span></span>
27. <span data-ttu-id="5ce38-198">Nella struttura selezionare 'Nodo principale: Elemento XML\Giornale di registrazione: Elemento XML\Transazione: Elemento XML\Data: Attributo XML'.</span><span class="sxs-lookup"><span data-stu-id="5ce38-198">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Date: XML Attribute'.</span></span>
28. <span data-ttu-id="5ce38-199">Nella struttura, selezionare 'modello: Modello dati Modello di esempio dimensioni finanziarie\Giornale di registrazione: Elenco di record\Transazione: Elenco di record\Data: Data'.</span><span class="sxs-lookup"><span data-stu-id="5ce38-199">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Date: Date'.</span></span>
29. <span data-ttu-id="5ce38-200">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="5ce38-200">Click Bind.</span></span>
30. <span data-ttu-id="5ce38-201">Nella struttura selezionare 'Nodo principale: Elemento XML\Giornale di registrazione: Elemento XML\Transazione: Elemento XML\Giustificativo: Attributo XML'.</span><span class="sxs-lookup"><span data-stu-id="5ce38-201">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Voucher: XML Attribute'.</span></span>
31. <span data-ttu-id="5ce38-202">Nella struttura, selezionare 'modello: Modello dati Modello di esempio dimensioni finanziarie\Giornale di registrazione: Elenco di record\Transazione: Elenco di record\Giustificativo: Stringa'.</span><span class="sxs-lookup"><span data-stu-id="5ce38-202">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Voucher: String'.</span></span>
32. <span data-ttu-id="5ce38-203">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="5ce38-203">Click Bind.</span></span>
33. <span data-ttu-id="5ce38-204">Nella struttura selezionare 'Nodo principale: Elemento XML\Giornale di registrazione: Elemento XML\Transazione: Elemento XML'.</span><span class="sxs-lookup"><span data-stu-id="5ce38-204">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element'.</span></span>
34. <span data-ttu-id="5ce38-205">Nella struttura, selezionare 'modello: Modello dati Modello di esempio dimensioni finanziarie\Giornale di registrazione: Elenco di record\Transazione: Elenco di record'.</span><span class="sxs-lookup"><span data-stu-id="5ce38-205">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list'.</span></span>
35. <span data-ttu-id="5ce38-206">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="5ce38-206">Click Bind.</span></span>
36. <span data-ttu-id="5ce38-207">Nella struttura selezionare 'Nodo principale: Elemento XML\Giornale di registrazione: Elemento XML\Batch: Attributo XML'.</span><span class="sxs-lookup"><span data-stu-id="5ce38-207">In the tree, select 'Root: XML Element\Journal: XML Element\Batch: XML Attribute'.</span></span>
37. <span data-ttu-id="5ce38-208">Nella struttura, selezionare 'modello: Modello dati Modello di esempio dimensioni finanziarie\Giornale di registrazione: Elenco di record\Batch: Stringa'.</span><span class="sxs-lookup"><span data-stu-id="5ce38-208">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Batch: String'.</span></span>
38. <span data-ttu-id="5ce38-209">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="5ce38-209">Click Bind.</span></span>
39. <span data-ttu-id="5ce38-210">Nella struttura selezionare 'Nodo principale: Elemento XML\Giornale di registrazione: Elemento XML'.</span><span class="sxs-lookup"><span data-stu-id="5ce38-210">In the tree, select 'Root: XML Element\Journal: XML Element'.</span></span>
40. <span data-ttu-id="5ce38-211">Nella struttura, selezionare 'modello: Modello dati Modello di esempio dimensioni finanziarie\Giornale di registrazione: Elenco di record'.</span><span class="sxs-lookup"><span data-stu-id="5ce38-211">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list'.</span></span>
41. <span data-ttu-id="5ce38-212">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="5ce38-212">Click Bind.</span></span>
42. <span data-ttu-id="5ce38-213">Nella struttura selezionare 'Nodo principale: Elemento XML\Società: Attributo XML'.</span><span class="sxs-lookup"><span data-stu-id="5ce38-213">In the tree, select 'Root: XML Element\Company: XML Attribute'.</span></span>
43. <span data-ttu-id="5ce38-214">Nella struttura, selezionare 'modello: Modello dati Modello di esempio dimensioni finanziarie\Società: Stringa'.</span><span class="sxs-lookup"><span data-stu-id="5ce38-214">In the tree, select 'model: Data model Financial dimensions sample model\Company: String'.</span></span>
44. <span data-ttu-id="5ce38-215">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="5ce38-215">Click Bind.</span></span>
45. <span data-ttu-id="5ce38-216">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="5ce38-216">Click Save.</span></span>
46. <span data-ttu-id="5ce38-217">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="5ce38-217">Close the page.</span></span>
<span data-ttu-id="5ce38-218">![Pagina della progettazione delle operazioni ER](../media/er-financial-dimensions-guides-format2.png)</span><span class="sxs-lookup"><span data-stu-id="5ce38-218">![ER Operations designer page](../media/er-financial-dimensions-guides-format2.png)</span></span>

