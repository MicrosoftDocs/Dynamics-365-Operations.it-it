---
title: 'ER Utilizzare le dimensioni finanziarie come origine dati (Parte 3: progettare il report)'
description: In questo argomento viene descritto come configurare un modello di Creazione di report elettronici (ER) per utilizzare le dimensioni finanziarie come origine dati per i report ER. (Parte 3)
author: NickSelin
ms.date: 05/27/2020
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, ERSolutionCreateDropDialog, EROperationDesigner, ERComponentTypeDropDialog
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2a3b9a8b5775d2001f3384480e2f9593f2dfa8b1
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5752414"
---
# <a name="er-use-financial-dimensions-as-a-data-source-part-3---design-the-report"></a><span data-ttu-id="f5c72-104">ER Utilizzare le dimensioni finanziarie come origine dati (Parte 3: progettare il report)</span><span class="sxs-lookup"><span data-stu-id="f5c72-104">ER Use financial dimensions as a data source (Part 3 - Design the report)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="f5c72-105">I passaggi seguenti descrivono come un utente con ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può configurare un modello per la creazione di report elettronici in modo che utilizzi dimensioni finanziarie come origine dati per i report elettronici.</span><span class="sxs-lookup"><span data-stu-id="f5c72-105">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) model to use financial dimensions as a data source for ER reports.</span></span> <span data-ttu-id="f5c72-106">Questi passaggi possono essere eseguiti in qualsiasi società.</span><span class="sxs-lookup"><span data-stu-id="f5c72-106">These steps can be performed in any company.</span></span>

<span data-ttu-id="f5c72-107">Per effettuare questi passaggi, è innanzitutto necessario completare i passaggi nella procedura "ER Usare dimensioni finanziarie come origine dati (parte 2: mapping del modello)".</span><span class="sxs-lookup"><span data-stu-id="f5c72-107">To complete these steps, you must first complete the steps in the "ER Use financial dimensions as a data source (Part 2: Model mapping)" procedure.</span></span>


## <a name="design-a-report-to-present-financial-dimensions"></a><span data-ttu-id="f5c72-108">Progettare un report per presentare dimensioni finanziarie</span><span class="sxs-lookup"><span data-stu-id="f5c72-108">Design a report to present financial dimensions</span></span>
1. <span data-ttu-id="f5c72-109">Passare a Amministrazione organizzazione > Reporting elettronico > Configurazioni.</span><span class="sxs-lookup"><span data-stu-id="f5c72-109">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="f5c72-110">Nella struttura selezionare 'Modello di esempio dimensioni finanziarie'.</span><span class="sxs-lookup"><span data-stu-id="f5c72-110">In the tree, select 'Financial dimensions sample model'.</span></span>
3. <span data-ttu-id="f5c72-111">Fare clic su Crea configurazione per aprire la finestra di dialogo a discesa .</span><span class="sxs-lookup"><span data-stu-id="f5c72-111">Click Create configuration to open the drop dialog.</span></span>
4. <span data-ttu-id="f5c72-112">Nel campo Nuovo immettere 'Formato basato sul modello dati Modello di esempio dimensioni finanziarie'.</span><span class="sxs-lookup"><span data-stu-id="f5c72-112">In the New field, enter 'Format based on data model Financial dimensions sample model'.</span></span>
    * <span data-ttu-id="f5c72-113">Utilizzare il modello creato in anticipo come origine dati per il nuovo report.</span><span class="sxs-lookup"><span data-stu-id="f5c72-113">Use the model that was created in advance as the data source for your new report.</span></span>  
5. <span data-ttu-id="f5c72-114">Nel campo Nome digitare 'Report dei giornali di registrazione di contabilità generale'.</span><span class="sxs-lookup"><span data-stu-id="f5c72-114">In the Name field, type 'Ledger journal report'.</span></span>
6. <span data-ttu-id="f5c72-115">Selezionare Voce nel campo Definizione modello dati.</span><span class="sxs-lookup"><span data-stu-id="f5c72-115">In the Data model definition field, select Entry.</span></span>
7. <span data-ttu-id="f5c72-116">Fare clic su Crea configurazione.</span><span class="sxs-lookup"><span data-stu-id="f5c72-116">Click Create configuration.</span></span>
8. <span data-ttu-id="f5c72-117">Fare clic su Progettazione.</span><span class="sxs-lookup"><span data-stu-id="f5c72-117">Click Designer.</span></span>
9. <span data-ttu-id="f5c72-118">Fare clic su Aggiungi radice per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="f5c72-118">Click Add root to open the drop dialog.</span></span>
10. <span data-ttu-id="f5c72-119">Nella struttura selezionare "XML\Elemento".</span><span class="sxs-lookup"><span data-stu-id="f5c72-119">In the tree, select 'XML\Element'.</span></span>
11. <span data-ttu-id="f5c72-120">Digitare 'Nodo principale' nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="f5c72-120">In the Name field, type 'Root'.</span></span>
12. <span data-ttu-id="f5c72-121">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="f5c72-121">Click OK.</span></span>
13. <span data-ttu-id="f5c72-122">Fare clic su Aggiungi per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="f5c72-122">Click Add to open the drop dialog.</span></span>
14. <span data-ttu-id="f5c72-123">Nella struttura selezionare "XML\Attributo".</span><span class="sxs-lookup"><span data-stu-id="f5c72-123">In the tree, select 'XML\Attribute'.</span></span>
15. <span data-ttu-id="f5c72-124">Nel campo Nome digitare "Società".</span><span class="sxs-lookup"><span data-stu-id="f5c72-124">In the Name field, type 'Company'.</span></span>
16. <span data-ttu-id="f5c72-125">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="f5c72-125">Click OK.</span></span>
17. <span data-ttu-id="f5c72-126">Fare clic su Aggiungi per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="f5c72-126">Click Add to open the drop dialog.</span></span>
18. <span data-ttu-id="f5c72-127">Nella struttura selezionare "XML\Elemento".</span><span class="sxs-lookup"><span data-stu-id="f5c72-127">In the tree, select 'XML\Element'.</span></span>
19. <span data-ttu-id="f5c72-128">Digitare 'Giornale di registrazione' nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="f5c72-128">In the Name field, type 'Journal'.</span></span>
20. <span data-ttu-id="f5c72-129">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="f5c72-129">Click OK.</span></span>
21. <span data-ttu-id="f5c72-130">Nella struttura selezionare 'Nodo principale: Elemento XML\Giornale di registrazione: Elemento XML'.</span><span class="sxs-lookup"><span data-stu-id="f5c72-130">In the tree, select 'Root: XML Element\Journal: XML Element'.</span></span>
22. <span data-ttu-id="f5c72-131">Fare clic su Aggiungi per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="f5c72-131">Click Add to open the drop dialog.</span></span>
23. <span data-ttu-id="f5c72-132">Nella struttura selezionare "XML\Attributo".</span><span class="sxs-lookup"><span data-stu-id="f5c72-132">In the tree, select 'XML\Attribute'.</span></span>
24. <span data-ttu-id="f5c72-133">Digitare 'Batch'. nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="f5c72-133">In the Name field, type 'Batch'.</span></span>
25. <span data-ttu-id="f5c72-134">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="f5c72-134">Click OK.</span></span>
26. <span data-ttu-id="f5c72-135">Fare clic su Aggiungi per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="f5c72-135">Click Add to open the drop dialog.</span></span>
27. <span data-ttu-id="f5c72-136">Nella struttura selezionare "XML\Elemento".</span><span class="sxs-lookup"><span data-stu-id="f5c72-136">In the tree, select 'XML\Element'.</span></span>
28. <span data-ttu-id="f5c72-137">Nel campo Nome digitare 'Transazione'.</span><span class="sxs-lookup"><span data-stu-id="f5c72-137">In the Name field, type 'Transaction'.</span></span>
29. <span data-ttu-id="f5c72-138">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="f5c72-138">Click OK.</span></span>
30. <span data-ttu-id="f5c72-139">Nella struttura selezionare 'Nodo principale: Elemento XML\Giornale di registrazione: Elemento XML\Transazione: Elemento XML'.</span><span class="sxs-lookup"><span data-stu-id="f5c72-139">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element'.</span></span>
31. <span data-ttu-id="f5c72-140">Fare clic su Aggiungi per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="f5c72-140">Click Add to open the drop dialog.</span></span>
32. <span data-ttu-id="f5c72-141">Nella struttura selezionare "XML\Attributo".</span><span class="sxs-lookup"><span data-stu-id="f5c72-141">In the tree, select 'XML\Attribute'.</span></span>
33. <span data-ttu-id="f5c72-142">Digitare 'Giustificativo' nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="f5c72-142">In the Name field, type 'Voucher'.</span></span>
34. <span data-ttu-id="f5c72-143">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="f5c72-143">Click OK.</span></span>
35. <span data-ttu-id="f5c72-144">Fare clic su Aggiungi attributo.</span><span class="sxs-lookup"><span data-stu-id="f5c72-144">Click Add Attribute.</span></span>
36. <span data-ttu-id="f5c72-145">Digitare 'Data' nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="f5c72-145">In the Name field, type 'Date'.</span></span>
37. <span data-ttu-id="f5c72-146">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="f5c72-146">Click OK.</span></span>
38. <span data-ttu-id="f5c72-147">Fare clic su Aggiungi attributo.</span><span class="sxs-lookup"><span data-stu-id="f5c72-147">Click Add Attribute.</span></span>
39. <span data-ttu-id="f5c72-148">Nel campo Nome digitare "Valuta".</span><span class="sxs-lookup"><span data-stu-id="f5c72-148">In the Name field, type 'Currency'.</span></span>
40. <span data-ttu-id="f5c72-149">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="f5c72-149">Click OK.</span></span>
41. <span data-ttu-id="f5c72-150">Fare clic su Aggiungi attributo.</span><span class="sxs-lookup"><span data-stu-id="f5c72-150">Click Add Attribute.</span></span>
42. <span data-ttu-id="f5c72-151">Nel campo Nome digitare 'Dare'.</span><span class="sxs-lookup"><span data-stu-id="f5c72-151">In the Name field, type 'Dt'.</span></span>
43. <span data-ttu-id="f5c72-152">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="f5c72-152">Click OK.</span></span>
44. <span data-ttu-id="f5c72-153">Fare clic su Aggiungi attributo.</span><span class="sxs-lookup"><span data-stu-id="f5c72-153">Click Add Attribute.</span></span>
45. <span data-ttu-id="f5c72-154">Nel campo Nome digitare 'Avere'.</span><span class="sxs-lookup"><span data-stu-id="f5c72-154">In the Name field, type 'Ct'.</span></span>
46. <span data-ttu-id="f5c72-155">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="f5c72-155">Click OK.</span></span>
47. <span data-ttu-id="f5c72-156">Fare clic su Aggiungi per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="f5c72-156">Click Add to open the drop dialog.</span></span>
48. <span data-ttu-id="f5c72-157">Nella struttura selezionare "XML\Elemento".</span><span class="sxs-lookup"><span data-stu-id="f5c72-157">In the tree, select 'XML\Element'.</span></span>
49. <span data-ttu-id="f5c72-158">Digitare 'Dimensioni' nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="f5c72-158">In the Name field, type 'Dimensions'.</span></span>
50. <span data-ttu-id="f5c72-159">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="f5c72-159">Click OK.</span></span>
51. <span data-ttu-id="f5c72-160">Nella struttura selezionare 'Nodo principale: Elemento XML\Giornale di registrazione: Elemento XML\Transazione: Elemento XML\Dimensioni: Elemento XML'.</span><span class="sxs-lookup"><span data-stu-id="f5c72-160">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element'.</span></span>
52. <span data-ttu-id="f5c72-161">Fare clic su Aggiungi per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="f5c72-161">Click Add to open the drop dialog.</span></span>
53. <span data-ttu-id="f5c72-162">Nella struttura selezionare "XML\Attributo".</span><span class="sxs-lookup"><span data-stu-id="f5c72-162">In the tree, select 'XML\Attribute'.</span></span>
54. <span data-ttu-id="f5c72-163">Digitare 'Codice' nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="f5c72-163">In the Name field, type 'Code'.</span></span>
55. <span data-ttu-id="f5c72-164">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="f5c72-164">Click OK.</span></span>
56. <span data-ttu-id="f5c72-165">Fare clic su Aggiungi attributo.</span><span class="sxs-lookup"><span data-stu-id="f5c72-165">Click Add Attribute.</span></span>
57. <span data-ttu-id="f5c72-166">Nel campo Nome digitare 'Valore'.</span><span class="sxs-lookup"><span data-stu-id="f5c72-166">In the Name field, type 'Value'.</span></span>
58. <span data-ttu-id="f5c72-167">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="f5c72-167">Click OK.</span></span>
59. <span data-ttu-id="f5c72-168">Fare clic su Aggiungi attributo.</span><span class="sxs-lookup"><span data-stu-id="f5c72-168">Click Add Attribute.</span></span>
60. <span data-ttu-id="f5c72-169">Nel campo Nome digitare 'Descrizione'.</span><span class="sxs-lookup"><span data-stu-id="f5c72-169">In the Name field, type 'Desc'.</span></span>
61. <span data-ttu-id="f5c72-170">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="f5c72-170">Click OK.</span></span>
<span data-ttu-id="f5c72-171">![Pagina della progettazione delle operazioni ER](../media/er-financial-dimensions-guides-format1.png)</span><span class="sxs-lookup"><span data-stu-id="f5c72-171">![ER Operations designer page](../media/er-financial-dimensions-guides-format1.png)</span></span>

## <a name="map-report-elements-to-data-sources"></a><span data-ttu-id="f5c72-172">Mappare gli elementi del report alle origini dati</span><span class="sxs-lookup"><span data-stu-id="f5c72-172">Map report elements to data sources</span></span>
1. <span data-ttu-id="f5c72-173">Fare clic sulla scheda Mapping.</span><span class="sxs-lookup"><span data-stu-id="f5c72-173">Click the Mapping tab.</span></span>
2. <span data-ttu-id="f5c72-174">Nella struttura, espandere 'modello: Modello dati Modello di esempio dimensioni finanziarie'.</span><span class="sxs-lookup"><span data-stu-id="f5c72-174">In the tree, expand 'model: Data model Financial dimensions sample model'.</span></span>
3. <span data-ttu-id="f5c72-175">Nella struttura, espandere 'modello: Modello dati Modello di esempio dimensioni finanziarie\Giornale di registrazione: Elenco di record'.</span><span class="sxs-lookup"><span data-stu-id="f5c72-175">In the tree, expand 'model: Data model Financial dimensions sample model\Journal: Record list'.</span></span>
4. <span data-ttu-id="f5c72-176">Nella struttura, espandere 'modello: Modello dati Modello di esempio dimensioni finanziarie\Giornale di registrazione: Elenco di record\Transazione: Elenco di record'.</span><span class="sxs-lookup"><span data-stu-id="f5c72-176">In the tree, expand 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list'.</span></span>
5. <span data-ttu-id="f5c72-177">Nella struttura, espandere 'modello: Modello dati Modello di esempio dimensioni finanziarie\Giornale di registrazione: Elenco di record\Transazione: Elenco di record\Dati dimensioni: Elenco di record'.</span><span class="sxs-lookup"><span data-stu-id="f5c72-177">In the tree, expand 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list'.</span></span>
6. <span data-ttu-id="f5c72-178">Nella struttura selezionare 'Nodo principale: Elemento XML\Giornale di registrazione: Elemento XML\Transazione: Elemento XML\Dimensioni: Elemento XML\Descrizione: Attributo XML'.</span><span class="sxs-lookup"><span data-stu-id="f5c72-178">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element\Desc: XML Attribute'.</span></span>
7. <span data-ttu-id="f5c72-179">Nella struttura, selezionare 'modello: Modello dati Modello di esempio dimensioni finanziarie\Giornale di registrazione: Elenco di record\Transazione: Elenco di record\Dati dimensioni: Elenco di record\Descrizione: Stringa'.</span><span class="sxs-lookup"><span data-stu-id="f5c72-179">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list\Description: String'.</span></span>
8. <span data-ttu-id="f5c72-180">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="f5c72-180">Click Bind.</span></span>
9. <span data-ttu-id="f5c72-181">Nella struttura selezionare 'Nodo principale: Elemento XML\Giornale di registrazione: Elemento XML\Transazione: Elemento XML\Dimensioni: Elemento XML\Valore: Attributo XML'.</span><span class="sxs-lookup"><span data-stu-id="f5c72-181">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element\Value: XML Attribute'.</span></span>
10. <span data-ttu-id="f5c72-182">Nella struttura, selezionare 'modello: Modello dati Modello di esempio dimensioni finanziarie\Giornale di registrazione: Elenco di record\Transazione: Elenco di record\Dati dimensioni: Elenco di record\Codice: Stringa'.</span><span class="sxs-lookup"><span data-stu-id="f5c72-182">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list\Code: String'.</span></span>
11. <span data-ttu-id="f5c72-183">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="f5c72-183">Click Bind.</span></span>
12. <span data-ttu-id="f5c72-184">Nella struttura selezionare 'Nodo principale: Elemento XML\Giornale di registrazione: Elemento XML\Transazione: Elemento XML\Dimensioni: Elemento XML\Codice: Attributo XML'.</span><span class="sxs-lookup"><span data-stu-id="f5c72-184">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element\Code: XML Attribute'.</span></span>
13. <span data-ttu-id="f5c72-185">Nella struttura, selezionare 'modello: Modello dati Modello di esempio dimensioni finanziarie\Giornale di registrazione: Elenco di record\Transazione: Elenco di record\Dati dimensioni: Elenco di record\Nome: Stringa'.</span><span class="sxs-lookup"><span data-stu-id="f5c72-185">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list\Name: String'.</span></span>
14. <span data-ttu-id="f5c72-186">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="f5c72-186">Click Bind.</span></span>
15. <span data-ttu-id="f5c72-187">Nella struttura, selezionare 'modello: Modello dati Modello di esempio dimensioni finanziarie\Giornale di registrazione: Elenco di record\Transazione: Elenco di record\Dati dimensioni: Elenco di record'.</span><span class="sxs-lookup"><span data-stu-id="f5c72-187">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list'.</span></span>
16. <span data-ttu-id="f5c72-188">Nella struttura selezionare 'Nodo principale: Elemento XML\Giornale di registrazione: Elemento XML\Transazione: Elemento XML\Dimensioni: Elemento XML'.</span><span class="sxs-lookup"><span data-stu-id="f5c72-188">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element'.</span></span>
17. <span data-ttu-id="f5c72-189">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="f5c72-189">Click Bind.</span></span>
18. <span data-ttu-id="f5c72-190">Nella struttura selezionare 'Nodo principale: Elemento XML\Giornale di registrazione: Elemento XML\Transazione: Elemento XML\Avere: Attributo XML'.</span><span class="sxs-lookup"><span data-stu-id="f5c72-190">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Ct: XML Attribute'.</span></span>
19. <span data-ttu-id="f5c72-191">Nella struttura, selezionare 'modello: Modello dati Modello di esempio dimensioni finanziarie\Giornale di registrazione: Elenco di record\Transazione: Elenco di record\Avere: Reale'.</span><span class="sxs-lookup"><span data-stu-id="f5c72-191">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Credit: Real'.</span></span>
20. <span data-ttu-id="f5c72-192">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="f5c72-192">Click Bind.</span></span>
21. <span data-ttu-id="f5c72-193">Nella struttura selezionare 'Nodo principale: Elemento XML\Giornale di registrazione: Elemento XML\Transazione: Elemento XML\Dare: Attributo XML'.</span><span class="sxs-lookup"><span data-stu-id="f5c72-193">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dt: XML Attribute'.</span></span>
22. <span data-ttu-id="f5c72-194">Nella struttura, selezionare 'modello: Modello dati Modello di esempio dimensioni finanziarie\Giornale di registrazione: Elenco di record\Transazione: Elenco di record\Dare: Reale'.</span><span class="sxs-lookup"><span data-stu-id="f5c72-194">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Debit: Real'.</span></span>
23. <span data-ttu-id="f5c72-195">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="f5c72-195">Click Bind.</span></span>
24. <span data-ttu-id="f5c72-196">Nella struttura selezionare 'Nodo principale: Elemento XML\Giornale di registrazione: Elemento XML\Transazione: Elemento XML\Valuta: Attributo XML'.</span><span class="sxs-lookup"><span data-stu-id="f5c72-196">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Currency: XML Attribute'.</span></span>
25. <span data-ttu-id="f5c72-197">Nella struttura, selezionare 'modello: Modello dati Modello di esempio dimensioni finanziarie\Giornale di registrazione: Elenco di record\Transazione: Elenco di record\Valuta: Stringa'.</span><span class="sxs-lookup"><span data-stu-id="f5c72-197">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Currency: String'.</span></span>
26. <span data-ttu-id="f5c72-198">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="f5c72-198">Click Bind.</span></span>
27. <span data-ttu-id="f5c72-199">Nella struttura selezionare 'Nodo principale: Elemento XML\Giornale di registrazione: Elemento XML\Transazione: Elemento XML\Data: Attributo XML'.</span><span class="sxs-lookup"><span data-stu-id="f5c72-199">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Date: XML Attribute'.</span></span>
28. <span data-ttu-id="f5c72-200">Nella struttura, selezionare 'modello: Modello dati Modello di esempio dimensioni finanziarie\Giornale di registrazione: Elenco di record\Transazione: Elenco di record\Data: Data'.</span><span class="sxs-lookup"><span data-stu-id="f5c72-200">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Date: Date'.</span></span>
29. <span data-ttu-id="f5c72-201">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="f5c72-201">Click Bind.</span></span>
30. <span data-ttu-id="f5c72-202">Nella struttura selezionare 'Nodo principale: Elemento XML\Giornale di registrazione: Elemento XML\Transazione: Elemento XML\Giustificativo: Attributo XML'.</span><span class="sxs-lookup"><span data-stu-id="f5c72-202">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Voucher: XML Attribute'.</span></span>
31. <span data-ttu-id="f5c72-203">Nella struttura, selezionare 'modello: Modello dati Modello di esempio dimensioni finanziarie\Giornale di registrazione: Elenco di record\Transazione: Elenco di record\Giustificativo: Stringa'.</span><span class="sxs-lookup"><span data-stu-id="f5c72-203">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Voucher: String'.</span></span>
32. <span data-ttu-id="f5c72-204">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="f5c72-204">Click Bind.</span></span>
33. <span data-ttu-id="f5c72-205">Nella struttura selezionare 'Nodo principale: Elemento XML\Giornale di registrazione: Elemento XML\Transazione: Elemento XML'.</span><span class="sxs-lookup"><span data-stu-id="f5c72-205">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element'.</span></span>
34. <span data-ttu-id="f5c72-206">Nella struttura, selezionare 'modello: Modello dati Modello di esempio dimensioni finanziarie\Giornale di registrazione: Elenco di record\Transazione: Elenco di record'.</span><span class="sxs-lookup"><span data-stu-id="f5c72-206">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list'.</span></span>
35. <span data-ttu-id="f5c72-207">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="f5c72-207">Click Bind.</span></span>
36. <span data-ttu-id="f5c72-208">Nella struttura selezionare 'Nodo principale: Elemento XML\Giornale di registrazione: Elemento XML\Batch: Attributo XML'.</span><span class="sxs-lookup"><span data-stu-id="f5c72-208">In the tree, select 'Root: XML Element\Journal: XML Element\Batch: XML Attribute'.</span></span>
37. <span data-ttu-id="f5c72-209">Nella struttura, selezionare 'modello: Modello dati Modello di esempio dimensioni finanziarie\Giornale di registrazione: Elenco di record\Batch: Stringa'.</span><span class="sxs-lookup"><span data-stu-id="f5c72-209">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Batch: String'.</span></span>
38. <span data-ttu-id="f5c72-210">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="f5c72-210">Click Bind.</span></span>
39. <span data-ttu-id="f5c72-211">Nella struttura selezionare 'Nodo principale: Elemento XML\Giornale di registrazione: Elemento XML'.</span><span class="sxs-lookup"><span data-stu-id="f5c72-211">In the tree, select 'Root: XML Element\Journal: XML Element'.</span></span>
40. <span data-ttu-id="f5c72-212">Nella struttura, selezionare 'modello: Modello dati Modello di esempio dimensioni finanziarie\Giornale di registrazione: Elenco di record'.</span><span class="sxs-lookup"><span data-stu-id="f5c72-212">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list'.</span></span>
41. <span data-ttu-id="f5c72-213">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="f5c72-213">Click Bind.</span></span>
42. <span data-ttu-id="f5c72-214">Nella struttura selezionare 'Nodo principale: Elemento XML\Società: Attributo XML'.</span><span class="sxs-lookup"><span data-stu-id="f5c72-214">In the tree, select 'Root: XML Element\Company: XML Attribute'.</span></span>
43. <span data-ttu-id="f5c72-215">Nella struttura, selezionare 'modello: Modello dati Modello di esempio dimensioni finanziarie\Società: Stringa'.</span><span class="sxs-lookup"><span data-stu-id="f5c72-215">In the tree, select 'model: Data model Financial dimensions sample model\Company: String'.</span></span>
44. <span data-ttu-id="f5c72-216">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="f5c72-216">Click Bind.</span></span>
45. <span data-ttu-id="f5c72-217">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="f5c72-217">Click Save.</span></span>
46. <span data-ttu-id="f5c72-218">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="f5c72-218">Close the page.</span></span>
<span data-ttu-id="f5c72-219">![Pagina della progettazione delle operazioni ER](../media/er-financial-dimensions-guides-format2.png)</span><span class="sxs-lookup"><span data-stu-id="f5c72-219">![ER Operations designer page](../media/er-financial-dimensions-guides-format2.png)</span></span>



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]