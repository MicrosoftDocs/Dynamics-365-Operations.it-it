---
title: 'ER Utilizzare le dimensioni finanziarie come origine dati (Parte 3: progettare il report)'
description: I passaggi seguenti descrivono come un utente con ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può configurare un modello per la creazione di report elettronici in modo che utilizzi dimensioni finanziarie come origine dati per i report elettronici.
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
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
ms.openlocfilehash: 29dcf008f342603615241ab75860893cadc2b69e
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/27/2019
ms.locfileid: "2182441"
---
# <a name="er-use-financial-dimensions-as-a-data-source-part-3-design-the-report"></a><span data-ttu-id="42986-103">ER utilizzare le dimensioni finanziarie come origine dati (parte 3: progettare il report)</span><span class="sxs-lookup"><span data-stu-id="42986-103">ER Use financial dimensions as a data source (Part 3: Design the report)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="42986-104">I passaggi seguenti descrivono come un utente con ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può configurare un modello per la creazione di report elettronici in modo che utilizzi dimensioni finanziarie come origine dati per i report elettronici.</span><span class="sxs-lookup"><span data-stu-id="42986-104">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) model to use financial dimensions as a data source for ER reports.</span></span> <span data-ttu-id="42986-105">Questi passaggi possono essere eseguiti in qualsiasi società.</span><span class="sxs-lookup"><span data-stu-id="42986-105">These steps can be performed in any company.</span></span>

<span data-ttu-id="42986-106">Per effettuare questi passaggi, è innanzitutto necessario completare i passaggi nella procedura 'ER Usare dimensioni finanziarie come origine dati (parte 2: mapping del modello)'.</span><span class="sxs-lookup"><span data-stu-id="42986-106">To complete these steps, you must first complete the steps in the “ER Use financial dimensions as a data source (Part 2: Model mapping)” procedure.</span></span>


## <a name="design-a-report-to-present-financial-dimensions"></a><span data-ttu-id="42986-107">Progettare un report per presentare dimensioni finanziarie</span><span class="sxs-lookup"><span data-stu-id="42986-107">Design a report to present financial dimensions</span></span>
1. <span data-ttu-id="42986-108">Passare a Amministrazione organizzazione > Reporting elettronico > Configurazioni.</span><span class="sxs-lookup"><span data-stu-id="42986-108">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="42986-109">Nella struttura selezionare 'Modello di esempio dimensioni finanziarie'.</span><span class="sxs-lookup"><span data-stu-id="42986-109">In the tree, select 'Financial dimensions sample model'.</span></span>
3. <span data-ttu-id="42986-110">Fare clic su Crea configurazione per aprire la finestra di dialogo a discesa .</span><span class="sxs-lookup"><span data-stu-id="42986-110">Click Create configuration to open the drop dialog.</span></span>
4. <span data-ttu-id="42986-111">Nel campo Nuovo immettere 'Formato basato sul modello dati Modello di esempio dimensioni finanziarie'.</span><span class="sxs-lookup"><span data-stu-id="42986-111">In the New field, enter 'Format based on data model Financial dimensions sample model'.</span></span>
    * <span data-ttu-id="42986-112">Utilizzare il modello creato in anticipo come origine dati per il nuovo report.</span><span class="sxs-lookup"><span data-stu-id="42986-112">Use the model that was created in advance as the data source for your new report.</span></span>  
5. <span data-ttu-id="42986-113">Nel campo Nome digitare 'Report dei giornali di registrazione di contabilità generale'.</span><span class="sxs-lookup"><span data-stu-id="42986-113">In the Name field, type 'Ledger journal report'.</span></span>
6. <span data-ttu-id="42986-114">Selezionare Voce nel campo Definizione modello dati.</span><span class="sxs-lookup"><span data-stu-id="42986-114">In the Data model definition field, select Entry.</span></span>
7. <span data-ttu-id="42986-115">Fare clic su Crea configurazione.</span><span class="sxs-lookup"><span data-stu-id="42986-115">Click Create configuration.</span></span>
8. <span data-ttu-id="42986-116">Fare clic su Progettazione.</span><span class="sxs-lookup"><span data-stu-id="42986-116">Click Designer.</span></span>
9. <span data-ttu-id="42986-117">Fare clic su Aggiungi radice per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="42986-117">Click Add root to open the drop dialog.</span></span>
10. <span data-ttu-id="42986-118">Nella struttura selezionare "XML\Elemento".</span><span class="sxs-lookup"><span data-stu-id="42986-118">In the tree, select 'XML\Element'.</span></span>
11. <span data-ttu-id="42986-119">Digitare 'Nodo principale' nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="42986-119">In the Name field, type 'Root'.</span></span>
12. <span data-ttu-id="42986-120">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="42986-120">Click OK.</span></span>
13. <span data-ttu-id="42986-121">Fare clic su Aggiungi per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="42986-121">Click Add to open the drop dialog.</span></span>
14. <span data-ttu-id="42986-122">Nella struttura selezionare "XML\Attributo".</span><span class="sxs-lookup"><span data-stu-id="42986-122">In the tree, select 'XML\Attribute'.</span></span>
15. <span data-ttu-id="42986-123">Nel campo Nome digitare "Società".</span><span class="sxs-lookup"><span data-stu-id="42986-123">In the Name field, type 'Company'.</span></span>
16. <span data-ttu-id="42986-124">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="42986-124">Click OK.</span></span>
17. <span data-ttu-id="42986-125">Fare clic su Aggiungi per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="42986-125">Click Add to open the drop dialog.</span></span>
18. <span data-ttu-id="42986-126">Nella struttura selezionare "XML\Elemento".</span><span class="sxs-lookup"><span data-stu-id="42986-126">In the tree, select 'XML\Element'.</span></span>
19. <span data-ttu-id="42986-127">Digitare 'Giornale di registrazione' nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="42986-127">In the Name field, type 'Journal'.</span></span>
20. <span data-ttu-id="42986-128">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="42986-128">Click OK.</span></span>
21. <span data-ttu-id="42986-129">Nella struttura selezionare 'Nodo principale: Elemento XML\Giornale di registrazione: Elemento XML'.</span><span class="sxs-lookup"><span data-stu-id="42986-129">In the tree, select 'Root: XML Element\Journal: XML Element'.</span></span>
22. <span data-ttu-id="42986-130">Fare clic su Aggiungi per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="42986-130">Click Add to open the drop dialog.</span></span>
23. <span data-ttu-id="42986-131">Nella struttura selezionare "XML\Attributo".</span><span class="sxs-lookup"><span data-stu-id="42986-131">In the tree, select 'XML\Attribute'.</span></span>
24. <span data-ttu-id="42986-132">Digitare 'Batch'. nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="42986-132">In the Name field, type 'Batch'.</span></span>
25. <span data-ttu-id="42986-133">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="42986-133">Click OK.</span></span>
26. <span data-ttu-id="42986-134">Fare clic su Aggiungi per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="42986-134">Click Add to open the drop dialog.</span></span>
27. <span data-ttu-id="42986-135">Nella struttura selezionare "XML\Elemento".</span><span class="sxs-lookup"><span data-stu-id="42986-135">In the tree, select 'XML\Element'.</span></span>
28. <span data-ttu-id="42986-136">Nel campo Nome digitare 'Transazione'.</span><span class="sxs-lookup"><span data-stu-id="42986-136">In the Name field, type 'Transaction'.</span></span>
29. <span data-ttu-id="42986-137">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="42986-137">Click OK.</span></span>
30. <span data-ttu-id="42986-138">Nella struttura selezionare 'Nodo principale: Elemento XML\Giornale di registrazione: Elemento XML\Transazione: Elemento XML'.</span><span class="sxs-lookup"><span data-stu-id="42986-138">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element'.</span></span>
31. <span data-ttu-id="42986-139">Fare clic su Aggiungi per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="42986-139">Click Add to open the drop dialog.</span></span>
32. <span data-ttu-id="42986-140">Nella struttura selezionare "XML\Attributo".</span><span class="sxs-lookup"><span data-stu-id="42986-140">In the tree, select 'XML\Attribute'.</span></span>
33. <span data-ttu-id="42986-141">Digitare 'Giustificativo' nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="42986-141">In the Name field, type 'Voucher'.</span></span>
34. <span data-ttu-id="42986-142">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="42986-142">Click OK.</span></span>
35. <span data-ttu-id="42986-143">Fare clic su Aggiungi attributo.</span><span class="sxs-lookup"><span data-stu-id="42986-143">Click Add Attribute.</span></span>
36. <span data-ttu-id="42986-144">Digitare 'Data' nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="42986-144">In the Name field, type 'Date'.</span></span>
37. <span data-ttu-id="42986-145">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="42986-145">Click OK.</span></span>
38. <span data-ttu-id="42986-146">Fare clic su Aggiungi attributo.</span><span class="sxs-lookup"><span data-stu-id="42986-146">Click Add Attribute.</span></span>
39. <span data-ttu-id="42986-147">Nel campo Nome digitare "Valuta".</span><span class="sxs-lookup"><span data-stu-id="42986-147">In the Name field, type 'Currency'.</span></span>
40. <span data-ttu-id="42986-148">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="42986-148">Click OK.</span></span>
41. <span data-ttu-id="42986-149">Fare clic su Aggiungi attributo.</span><span class="sxs-lookup"><span data-stu-id="42986-149">Click Add Attribute.</span></span>
42. <span data-ttu-id="42986-150">Nel campo Nome digitare 'Dare'.</span><span class="sxs-lookup"><span data-stu-id="42986-150">In the Name field, type 'Dt'.</span></span>
43. <span data-ttu-id="42986-151">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="42986-151">Click OK.</span></span>
44. <span data-ttu-id="42986-152">Fare clic su Aggiungi attributo.</span><span class="sxs-lookup"><span data-stu-id="42986-152">Click Add Attribute.</span></span>
45. <span data-ttu-id="42986-153">Nel campo Nome digitare 'Avere'.</span><span class="sxs-lookup"><span data-stu-id="42986-153">In the Name field, type 'Ct'.</span></span>
46. <span data-ttu-id="42986-154">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="42986-154">Click OK.</span></span>
47. <span data-ttu-id="42986-155">Fare clic su Aggiungi per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="42986-155">Click Add to open the drop dialog.</span></span>
48. <span data-ttu-id="42986-156">Nella struttura selezionare "XML\Elemento".</span><span class="sxs-lookup"><span data-stu-id="42986-156">In the tree, select 'XML\Element'.</span></span>
49. <span data-ttu-id="42986-157">Digitare 'Dimensioni' nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="42986-157">In the Name field, type 'Dimensions'.</span></span>
50. <span data-ttu-id="42986-158">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="42986-158">Click OK.</span></span>
51. <span data-ttu-id="42986-159">Nella struttura selezionare 'Nodo principale: Elemento XML\Giornale di registrazione: Elemento XML\Transazione: Elemento XML\Dimensioni: Elemento XML'.</span><span class="sxs-lookup"><span data-stu-id="42986-159">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element'.</span></span>
52. <span data-ttu-id="42986-160">Fare clic su Aggiungi per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="42986-160">Click Add to open the drop dialog.</span></span>
53. <span data-ttu-id="42986-161">Nella struttura selezionare "XML\Attributo".</span><span class="sxs-lookup"><span data-stu-id="42986-161">In the tree, select 'XML\Attribute'.</span></span>
54. <span data-ttu-id="42986-162">Digitare 'Codice' nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="42986-162">In the Name field, type 'Code'.</span></span>
55. <span data-ttu-id="42986-163">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="42986-163">Click OK.</span></span>
56. <span data-ttu-id="42986-164">Fare clic su Aggiungi attributo.</span><span class="sxs-lookup"><span data-stu-id="42986-164">Click Add Attribute.</span></span>
57. <span data-ttu-id="42986-165">Nel campo Nome digitare 'Valore'.</span><span class="sxs-lookup"><span data-stu-id="42986-165">In the Name field, type 'Value'.</span></span>
58. <span data-ttu-id="42986-166">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="42986-166">Click OK.</span></span>
59. <span data-ttu-id="42986-167">Fare clic su Aggiungi attributo.</span><span class="sxs-lookup"><span data-stu-id="42986-167">Click Add Attribute.</span></span>
60. <span data-ttu-id="42986-168">Nel campo Nome digitare 'Descrizione'.</span><span class="sxs-lookup"><span data-stu-id="42986-168">In the Name field, type 'Desc'.</span></span>
61. <span data-ttu-id="42986-169">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="42986-169">Click OK.</span></span>

## <a name="map-report-elements-to-data-sources"></a><span data-ttu-id="42986-170">Mappare gli elementi del report alle origini dati</span><span class="sxs-lookup"><span data-stu-id="42986-170">Map report elements to data sources</span></span>
1. <span data-ttu-id="42986-171">Fare clic sulla scheda Mapping.</span><span class="sxs-lookup"><span data-stu-id="42986-171">Click the Mapping tab.</span></span>
2. <span data-ttu-id="42986-172">Nella struttura, espandere 'modello: Modello dati Modello di esempio dimensioni finanziarie'.</span><span class="sxs-lookup"><span data-stu-id="42986-172">In the tree, expand 'model: Data model Financial dimensions sample model'.</span></span>
3. <span data-ttu-id="42986-173">Nella struttura, espandere 'modello: Modello dati Modello di esempio dimensioni finanziarie\Giornale di registrazione: Elenco di record'.</span><span class="sxs-lookup"><span data-stu-id="42986-173">In the tree, expand 'model: Data model Financial dimensions sample model\Journal: Record list'.</span></span>
4. <span data-ttu-id="42986-174">Nella struttura, espandere 'modello: Modello dati Modello di esempio dimensioni finanziarie\Giornale di registrazione: Elenco di record\Transazione: Elenco di record'.</span><span class="sxs-lookup"><span data-stu-id="42986-174">In the tree, expand 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list'.</span></span>
5. <span data-ttu-id="42986-175">Nella struttura, espandere 'modello: Modello dati Modello di esempio dimensioni finanziarie\Giornale di registrazione: Elenco di record\Transazione: Elenco di record\Dati dimensioni: Elenco di record'.</span><span class="sxs-lookup"><span data-stu-id="42986-175">In the tree, expand 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list'.</span></span>
6. <span data-ttu-id="42986-176">Nella struttura selezionare 'Nodo principale: Elemento XML\Giornale di registrazione: Elemento XML\Transazione: Elemento XML\Dimensioni: Elemento XML\Descrizione: Attributo XML'.</span><span class="sxs-lookup"><span data-stu-id="42986-176">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element\Desc: XML Attribute'.</span></span>
7. <span data-ttu-id="42986-177">Nella struttura, selezionare 'modello: Modello dati Modello di esempio dimensioni finanziarie\Giornale di registrazione: Elenco di record\Transazione: Elenco di record\Dati dimensioni: Elenco di record\Descrizione: Stringa'.</span><span class="sxs-lookup"><span data-stu-id="42986-177">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list\Description: String'.</span></span>
8. <span data-ttu-id="42986-178">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="42986-178">Click Bind.</span></span>
9. <span data-ttu-id="42986-179">Nella struttura selezionare 'Nodo principale: Elemento XML\Giornale di registrazione: Elemento XML\Transazione: Elemento XML\Dimensioni: Elemento XML\Valore: Attributo XML'.</span><span class="sxs-lookup"><span data-stu-id="42986-179">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element\Value: XML Attribute'.</span></span>
10. <span data-ttu-id="42986-180">Nella struttura, selezionare 'modello: Modello dati Modello di esempio dimensioni finanziarie\Giornale di registrazione: Elenco di record\Transazione: Elenco di record\Dati dimensioni: Elenco di record\Codice: Stringa'.</span><span class="sxs-lookup"><span data-stu-id="42986-180">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list\Code: String'.</span></span>
11. <span data-ttu-id="42986-181">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="42986-181">Click Bind.</span></span>
12. <span data-ttu-id="42986-182">Nella struttura selezionare 'Nodo principale: Elemento XML\Giornale di registrazione: Elemento XML\Transazione: Elemento XML\Dimensioni: Elemento XML\Codice: Attributo XML'.</span><span class="sxs-lookup"><span data-stu-id="42986-182">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element\Code: XML Attribute'.</span></span>
13. <span data-ttu-id="42986-183">Nella struttura, selezionare 'modello: Modello dati Modello di esempio dimensioni finanziarie\Giornale di registrazione: Elenco di record\Transazione: Elenco di record\Dati dimensioni: Elenco di record\Nome: Stringa'.</span><span class="sxs-lookup"><span data-stu-id="42986-183">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list\Name: String'.</span></span>
14. <span data-ttu-id="42986-184">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="42986-184">Click Bind.</span></span>
15. <span data-ttu-id="42986-185">Nella struttura, selezionare 'modello: Modello dati Modello di esempio dimensioni finanziarie\Giornale di registrazione: Elenco di record\Transazione: Elenco di record\Dati dimensioni: Elenco di record'.</span><span class="sxs-lookup"><span data-stu-id="42986-185">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list'.</span></span>
16. <span data-ttu-id="42986-186">Nella struttura selezionare 'Nodo principale: Elemento XML\Giornale di registrazione: Elemento XML\Transazione: Elemento XML\Dimensioni: Elemento XML'.</span><span class="sxs-lookup"><span data-stu-id="42986-186">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element'.</span></span>
17. <span data-ttu-id="42986-187">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="42986-187">Click Bind.</span></span>
18. <span data-ttu-id="42986-188">Nella struttura selezionare 'Nodo principale: Elemento XML\Giornale di registrazione: Elemento XML\Transazione: Elemento XML\Avere: Attributo XML'.</span><span class="sxs-lookup"><span data-stu-id="42986-188">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Ct: XML Attribute'.</span></span>
19. <span data-ttu-id="42986-189">Nella struttura, selezionare 'modello: Modello dati Modello di esempio dimensioni finanziarie\Giornale di registrazione: Elenco di record\Transazione: Elenco di record\Avere: Reale'.</span><span class="sxs-lookup"><span data-stu-id="42986-189">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Credit: Real'.</span></span>
20. <span data-ttu-id="42986-190">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="42986-190">Click Bind.</span></span>
21. <span data-ttu-id="42986-191">Nella struttura selezionare 'Nodo principale: Elemento XML\Giornale di registrazione: Elemento XML\Transazione: Elemento XML\Dare: Attributo XML'.</span><span class="sxs-lookup"><span data-stu-id="42986-191">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dt: XML Attribute'.</span></span>
22. <span data-ttu-id="42986-192">Nella struttura, selezionare 'modello: Modello dati Modello di esempio dimensioni finanziarie\Giornale di registrazione: Elenco di record\Transazione: Elenco di record\Dare: Reale'.</span><span class="sxs-lookup"><span data-stu-id="42986-192">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Debit: Real'.</span></span>
23. <span data-ttu-id="42986-193">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="42986-193">Click Bind.</span></span>
24. <span data-ttu-id="42986-194">Nella struttura selezionare 'Nodo principale: Elemento XML\Giornale di registrazione: Elemento XML\Transazione: Elemento XML\Valuta: Attributo XML'.</span><span class="sxs-lookup"><span data-stu-id="42986-194">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Currency: XML Attribute'.</span></span>
25. <span data-ttu-id="42986-195">Nella struttura, selezionare 'modello: Modello dati Modello di esempio dimensioni finanziarie\Giornale di registrazione: Elenco di record\Transazione: Elenco di record\Valuta: Stringa'.</span><span class="sxs-lookup"><span data-stu-id="42986-195">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Currency: String'.</span></span>
26. <span data-ttu-id="42986-196">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="42986-196">Click Bind.</span></span>
27. <span data-ttu-id="42986-197">Nella struttura selezionare 'Nodo principale: Elemento XML\Giornale di registrazione: Elemento XML\Transazione: Elemento XML\Data: Attributo XML'.</span><span class="sxs-lookup"><span data-stu-id="42986-197">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Date: XML Attribute'.</span></span>
28. <span data-ttu-id="42986-198">Nella struttura, selezionare 'modello: Modello dati Modello di esempio dimensioni finanziarie\Giornale di registrazione: Elenco di record\Transazione: Elenco di record\Data: Data'.</span><span class="sxs-lookup"><span data-stu-id="42986-198">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Date: Date'.</span></span>
29. <span data-ttu-id="42986-199">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="42986-199">Click Bind.</span></span>
30. <span data-ttu-id="42986-200">Nella struttura selezionare 'Nodo principale: Elemento XML\Giornale di registrazione: Elemento XML\Transazione: Elemento XML\Giustificativo: Attributo XML'.</span><span class="sxs-lookup"><span data-stu-id="42986-200">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Voucher: XML Attribute'.</span></span>
31. <span data-ttu-id="42986-201">Nella struttura, selezionare 'modello: Modello dati Modello di esempio dimensioni finanziarie\Giornale di registrazione: Elenco di record\Transazione: Elenco di record\Giustificativo: Stringa'.</span><span class="sxs-lookup"><span data-stu-id="42986-201">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Voucher: String'.</span></span>
32. <span data-ttu-id="42986-202">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="42986-202">Click Bind.</span></span>
33. <span data-ttu-id="42986-203">Nella struttura selezionare 'Nodo principale: Elemento XML\Giornale di registrazione: Elemento XML\Transazione: Elemento XML'.</span><span class="sxs-lookup"><span data-stu-id="42986-203">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element'.</span></span>
34. <span data-ttu-id="42986-204">Nella struttura, selezionare 'modello: Modello dati Modello di esempio dimensioni finanziarie\Giornale di registrazione: Elenco di record\Transazione: Elenco di record'.</span><span class="sxs-lookup"><span data-stu-id="42986-204">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list'.</span></span>
35. <span data-ttu-id="42986-205">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="42986-205">Click Bind.</span></span>
36. <span data-ttu-id="42986-206">Nella struttura selezionare 'Nodo principale: Elemento XML\Giornale di registrazione: Elemento XML\Batch: Attributo XML'.</span><span class="sxs-lookup"><span data-stu-id="42986-206">In the tree, select 'Root: XML Element\Journal: XML Element\Batch: XML Attribute'.</span></span>
37. <span data-ttu-id="42986-207">Nella struttura, selezionare 'modello: Modello dati Modello di esempio dimensioni finanziarie\Giornale di registrazione: Elenco di record\Batch: Stringa'.</span><span class="sxs-lookup"><span data-stu-id="42986-207">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Batch: String'.</span></span>
38. <span data-ttu-id="42986-208">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="42986-208">Click Bind.</span></span>
39. <span data-ttu-id="42986-209">Nella struttura selezionare 'Nodo principale: Elemento XML\Giornale di registrazione: Elemento XML'.</span><span class="sxs-lookup"><span data-stu-id="42986-209">In the tree, select 'Root: XML Element\Journal: XML Element'.</span></span>
40. <span data-ttu-id="42986-210">Nella struttura, selezionare 'modello: Modello dati Modello di esempio dimensioni finanziarie\Giornale di registrazione: Elenco di record'.</span><span class="sxs-lookup"><span data-stu-id="42986-210">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list'.</span></span>
41. <span data-ttu-id="42986-211">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="42986-211">Click Bind.</span></span>
42. <span data-ttu-id="42986-212">Nella struttura selezionare 'Nodo principale: Elemento XML\Società: Attributo XML'.</span><span class="sxs-lookup"><span data-stu-id="42986-212">In the tree, select 'Root: XML Element\Company: XML Attribute'.</span></span>
43. <span data-ttu-id="42986-213">Nella struttura, selezionare 'modello: Modello dati Modello di esempio dimensioni finanziarie\Società: Stringa'.</span><span class="sxs-lookup"><span data-stu-id="42986-213">In the tree, select 'model: Data model Financial dimensions sample model\Company: String'.</span></span>
44. <span data-ttu-id="42986-214">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="42986-214">Click Bind.</span></span>
45. <span data-ttu-id="42986-215">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="42986-215">Click Save.</span></span>
46. <span data-ttu-id="42986-216">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="42986-216">Close the page.</span></span>

