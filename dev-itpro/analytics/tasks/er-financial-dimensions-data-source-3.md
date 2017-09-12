--- 
title: Progettare un report per utilizzare le dimensioni finanziarie come origine dati per la creazione di report elettronici (ER)
description: "I passaggi seguenti descrivono come un utente con ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può configurare un modello per la creazione di report elettronici in modo che utilizzi dimensioni finanziarie come origine dati per i report elettronici."
author: NickSelin
manager: AnnBe
ms.date: 10/18/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 02787c96077e8bae54d8073e8d0770613ea2b49a
ms.contentlocale: it-it
ms.lasthandoff: 08/29/2017

---
# <a name="design-a-report-to-use-financial-dimensions-as-a-data-source-for-electronic-reporting-er"></a><span data-ttu-id="09f5e-103">Progettare un report per utilizzare le dimensioni finanziarie come origine dati per la creazione di report elettronici (ER)</span><span class="sxs-lookup"><span data-stu-id="09f5e-103">Design a report to use financial dimensions as a data source for electronic reporting (ER)</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="09f5e-104">I passaggi seguenti descrivono come un utente con ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può configurare un modello per la creazione di report elettronici in modo che utilizzi dimensioni finanziarie come origine dati per i report elettronici.</span><span class="sxs-lookup"><span data-stu-id="09f5e-104">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) model to use financial dimensions as a data source for ER reports.</span></span> <span data-ttu-id="09f5e-105">Questi passaggi possono essere eseguiti in qualsiasi società.</span><span class="sxs-lookup"><span data-stu-id="09f5e-105">These steps can be performed in any company.</span></span>

<span data-ttu-id="09f5e-106">Per effettuare questi passaggi, è innanzitutto necessario completare i passaggi nella procedura 'ER Usare dimensioni finanziarie come origine dati (parte 2: mapping del modello)'.</span><span class="sxs-lookup"><span data-stu-id="09f5e-106">To complete these steps, you must first complete the steps in the “ER Use financial dimensions as a data source (Part 2: Model mapping)” procedure.</span></span>


## <a name="design-a-report-to-present-financial-dimensions"></a><span data-ttu-id="09f5e-107">Progettare un report per presentare dimensioni finanziarie</span><span class="sxs-lookup"><span data-stu-id="09f5e-107">Design a report to present financial dimensions</span></span>
1. <span data-ttu-id="09f5e-108">Passare a Amministrazione organizzazione > Reporting elettronico > Configurazioni.</span><span class="sxs-lookup"><span data-stu-id="09f5e-108">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="09f5e-109">Nella struttura selezionare 'Modello di esempio dimensioni finanziarie'.</span><span class="sxs-lookup"><span data-stu-id="09f5e-109">In the tree, select 'Financial dimensions sample model'.</span></span>
3. <span data-ttu-id="09f5e-110">Fare clic su Crea configurazione per aprire la finestra di dialogo a discesa .</span><span class="sxs-lookup"><span data-stu-id="09f5e-110">Click Create configuration to open the drop dialog.</span></span>
4. <span data-ttu-id="09f5e-111">Nel campo Nuovo immettere 'Formato basato sul modello dati Modello di esempio dimensioni finanziarie'.</span><span class="sxs-lookup"><span data-stu-id="09f5e-111">In the New field, enter 'Format based on data model Financial dimensions sample model'.</span></span>
    * <span data-ttu-id="09f5e-112">Utilizzare il modello creato in anticipo come origine dati per il nuovo report.</span><span class="sxs-lookup"><span data-stu-id="09f5e-112">Use the model that was created in advance as the data source for your new report.</span></span>  
5. <span data-ttu-id="09f5e-113">Nel campo Nome digitare 'Report dei giornali di registrazione di contabilità generale'.</span><span class="sxs-lookup"><span data-stu-id="09f5e-113">In the Name field, type 'Ledger journal report'.</span></span>
6. <span data-ttu-id="09f5e-114">Selezionare Voce nel campo Definizione modello dati.</span><span class="sxs-lookup"><span data-stu-id="09f5e-114">In the Data model definition field, select Entry.</span></span>
7. <span data-ttu-id="09f5e-115">Fare clic su Crea configurazione.</span><span class="sxs-lookup"><span data-stu-id="09f5e-115">Click Create configuration.</span></span>
8. <span data-ttu-id="09f5e-116">Fare clic su Progettazione.</span><span class="sxs-lookup"><span data-stu-id="09f5e-116">Click Designer.</span></span>
9. <span data-ttu-id="09f5e-117">Fare clic su Aggiungi radice per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="09f5e-117">Click Add root to open the drop dialog.</span></span>
10. <span data-ttu-id="09f5e-118">Nella struttura selezionare "XML\Elemento".</span><span class="sxs-lookup"><span data-stu-id="09f5e-118">In the tree, select 'XML\Element'.</span></span>
11. <span data-ttu-id="09f5e-119">Digitare 'Nodo principale' nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="09f5e-119">In the Name field, type 'Root'.</span></span>
12. <span data-ttu-id="09f5e-120">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="09f5e-120">Click OK.</span></span>
13. <span data-ttu-id="09f5e-121">Fare clic su Aggiungi per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="09f5e-121">Click Add to open the drop dialog.</span></span>
14. <span data-ttu-id="09f5e-122">Nella struttura selezionare "XML\Attributo".</span><span class="sxs-lookup"><span data-stu-id="09f5e-122">In the tree, select 'XML\Attribute'.</span></span>
15. <span data-ttu-id="09f5e-123">Nel campo Nome digitare "Società".</span><span class="sxs-lookup"><span data-stu-id="09f5e-123">In the Name field, type 'Company'.</span></span>
16. <span data-ttu-id="09f5e-124">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="09f5e-124">Click OK.</span></span>
17. <span data-ttu-id="09f5e-125">Fare clic su Aggiungi per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="09f5e-125">Click Add to open the drop dialog.</span></span>
18. <span data-ttu-id="09f5e-126">Nella struttura selezionare "XML\Elemento".</span><span class="sxs-lookup"><span data-stu-id="09f5e-126">In the tree, select 'XML\Element'.</span></span>
19. <span data-ttu-id="09f5e-127">Digitare 'Giornale di registrazione' nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="09f5e-127">In the Name field, type 'Journal'.</span></span>
20. <span data-ttu-id="09f5e-128">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="09f5e-128">Click OK.</span></span>
21. <span data-ttu-id="09f5e-129">Nella struttura selezionare 'Nodo principale: Elemento XML\Giornale di registrazione: Elemento XML'.</span><span class="sxs-lookup"><span data-stu-id="09f5e-129">In the tree, select 'Root: XML Element\Journal: XML Element'.</span></span>
22. <span data-ttu-id="09f5e-130">Fare clic su Aggiungi per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="09f5e-130">Click Add to open the drop dialog.</span></span>
23. <span data-ttu-id="09f5e-131">Nella struttura selezionare "XML\Attributo".</span><span class="sxs-lookup"><span data-stu-id="09f5e-131">In the tree, select 'XML\Attribute'.</span></span>
24. <span data-ttu-id="09f5e-132">Digitare 'Batch'. nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="09f5e-132">In the Name field, type 'Batch'.</span></span>
25. <span data-ttu-id="09f5e-133">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="09f5e-133">Click OK.</span></span>
26. <span data-ttu-id="09f5e-134">Fare clic su Aggiungi per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="09f5e-134">Click Add to open the drop dialog.</span></span>
27. <span data-ttu-id="09f5e-135">Nella struttura selezionare "XML\Elemento".</span><span class="sxs-lookup"><span data-stu-id="09f5e-135">In the tree, select 'XML\Element'.</span></span>
28. <span data-ttu-id="09f5e-136">Nel campo Nome digitare 'Transazione'.</span><span class="sxs-lookup"><span data-stu-id="09f5e-136">In the Name field, type 'Transaction'.</span></span>
29. <span data-ttu-id="09f5e-137">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="09f5e-137">Click OK.</span></span>
30. <span data-ttu-id="09f5e-138">Nella struttura selezionare 'Nodo principale: Elemento XML\Giornale di registrazione: Elemento XML\Transazione: Elemento XML'.</span><span class="sxs-lookup"><span data-stu-id="09f5e-138">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element'.</span></span>
31. <span data-ttu-id="09f5e-139">Fare clic su Aggiungi per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="09f5e-139">Click Add to open the drop dialog.</span></span>
32. <span data-ttu-id="09f5e-140">Nella struttura selezionare "XML\Attributo".</span><span class="sxs-lookup"><span data-stu-id="09f5e-140">In the tree, select 'XML\Attribute'.</span></span>
33. <span data-ttu-id="09f5e-141">Digitare 'Giustificativo' nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="09f5e-141">In the Name field, type 'Voucher'.</span></span>
34. <span data-ttu-id="09f5e-142">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="09f5e-142">Click OK.</span></span>
35. <span data-ttu-id="09f5e-143">Fare clic su Aggiungi attributo.</span><span class="sxs-lookup"><span data-stu-id="09f5e-143">Click Add Attribute.</span></span>
36. <span data-ttu-id="09f5e-144">Digitare 'Data' nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="09f5e-144">In the Name field, type 'Date'.</span></span>
37. <span data-ttu-id="09f5e-145">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="09f5e-145">Click OK.</span></span>
38. <span data-ttu-id="09f5e-146">Fare clic su Aggiungi attributo.</span><span class="sxs-lookup"><span data-stu-id="09f5e-146">Click Add Attribute.</span></span>
39. <span data-ttu-id="09f5e-147">Nel campo Nome digitare "Valuta".</span><span class="sxs-lookup"><span data-stu-id="09f5e-147">In the Name field, type 'Currency'.</span></span>
40. <span data-ttu-id="09f5e-148">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="09f5e-148">Click OK.</span></span>
41. <span data-ttu-id="09f5e-149">Fare clic su Aggiungi attributo.</span><span class="sxs-lookup"><span data-stu-id="09f5e-149">Click Add Attribute.</span></span>
42. <span data-ttu-id="09f5e-150">Nel campo Nome digitare 'Dare'.</span><span class="sxs-lookup"><span data-stu-id="09f5e-150">In the Name field, type 'Dt'.</span></span>
43. <span data-ttu-id="09f5e-151">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="09f5e-151">Click OK.</span></span>
44. <span data-ttu-id="09f5e-152">Fare clic su Aggiungi attributo.</span><span class="sxs-lookup"><span data-stu-id="09f5e-152">Click Add Attribute.</span></span>
45. <span data-ttu-id="09f5e-153">Nel campo Nome digitare 'Avere'.</span><span class="sxs-lookup"><span data-stu-id="09f5e-153">In the Name field, type 'Ct'.</span></span>
46. <span data-ttu-id="09f5e-154">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="09f5e-154">Click OK.</span></span>
47. <span data-ttu-id="09f5e-155">Fare clic su Aggiungi per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="09f5e-155">Click Add to open the drop dialog.</span></span>
48. <span data-ttu-id="09f5e-156">Nella struttura selezionare "XML\Elemento".</span><span class="sxs-lookup"><span data-stu-id="09f5e-156">In the tree, select 'XML\Element'.</span></span>
49. <span data-ttu-id="09f5e-157">Digitare 'Dimensioni' nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="09f5e-157">In the Name field, type 'Dimensions'.</span></span>
50. <span data-ttu-id="09f5e-158">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="09f5e-158">Click OK.</span></span>
51. <span data-ttu-id="09f5e-159">Nella struttura selezionare 'Nodo principale: Elemento XML\Giornale di registrazione: Elemento XML\Transazione: Elemento XML\Dimensioni: Elemento XML'.</span><span class="sxs-lookup"><span data-stu-id="09f5e-159">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element'.</span></span>
52. <span data-ttu-id="09f5e-160">Fare clic su Aggiungi per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="09f5e-160">Click Add to open the drop dialog.</span></span>
53. <span data-ttu-id="09f5e-161">Nella struttura selezionare "XML\Attributo".</span><span class="sxs-lookup"><span data-stu-id="09f5e-161">In the tree, select 'XML\Attribute'.</span></span>
54. <span data-ttu-id="09f5e-162">Digitare 'Codice' nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="09f5e-162">In the Name field, type 'Code'.</span></span>
55. <span data-ttu-id="09f5e-163">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="09f5e-163">Click OK.</span></span>
56. <span data-ttu-id="09f5e-164">Fare clic su Aggiungi attributo.</span><span class="sxs-lookup"><span data-stu-id="09f5e-164">Click Add Attribute.</span></span>
57. <span data-ttu-id="09f5e-165">Nel campo Nome digitare 'Valore'.</span><span class="sxs-lookup"><span data-stu-id="09f5e-165">In the Name field, type 'Value'.</span></span>
58. <span data-ttu-id="09f5e-166">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="09f5e-166">Click OK.</span></span>
59. <span data-ttu-id="09f5e-167">Fare clic su Aggiungi attributo.</span><span class="sxs-lookup"><span data-stu-id="09f5e-167">Click Add Attribute.</span></span>
60. <span data-ttu-id="09f5e-168">Nel campo Nome digitare 'Descrizione'.</span><span class="sxs-lookup"><span data-stu-id="09f5e-168">In the Name field, type 'Desc'.</span></span>
61. <span data-ttu-id="09f5e-169">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="09f5e-169">Click OK.</span></span>

## <a name="map-report-elements-to-data-sources"></a><span data-ttu-id="09f5e-170">Mappare gli elementi del report alle origini dati</span><span class="sxs-lookup"><span data-stu-id="09f5e-170">Map report elements to data sources</span></span>
1. <span data-ttu-id="09f5e-171">Fare clic sulla scheda Mapping.</span><span class="sxs-lookup"><span data-stu-id="09f5e-171">Click the Mapping tab.</span></span>
2. <span data-ttu-id="09f5e-172">Nella struttura, espandere 'modello: Modello dati Modello di esempio dimensioni finanziarie'.</span><span class="sxs-lookup"><span data-stu-id="09f5e-172">In the tree, expand 'model: Data model Financial dimensions sample model'.</span></span>
3. <span data-ttu-id="09f5e-173">Nella struttura, espandere 'modello: Modello dati Modello di esempio dimensioni finanziarie\Giornale di registrazione: Elenco di record'.</span><span class="sxs-lookup"><span data-stu-id="09f5e-173">In the tree, expand 'model: Data model Financial dimensions sample model\Journal: Record list'.</span></span>
4. <span data-ttu-id="09f5e-174">Nella struttura, espandere 'modello: Modello dati Modello di esempio dimensioni finanziarie\Giornale di registrazione: Elenco di record\Transazione: Elenco di record'.</span><span class="sxs-lookup"><span data-stu-id="09f5e-174">In the tree, expand 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list'.</span></span>
5. <span data-ttu-id="09f5e-175">Nella struttura, espandere 'modello: Modello dati Modello di esempio dimensioni finanziarie\Giornale di registrazione: Elenco di record\Transazione: Elenco di record\Dati dimensioni: Elenco di record'.</span><span class="sxs-lookup"><span data-stu-id="09f5e-175">In the tree, expand 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list'.</span></span>
6. <span data-ttu-id="09f5e-176">Nella struttura selezionare 'Nodo principale: Elemento XML\Giornale di registrazione: Elemento XML\Transazione: Elemento XML\Dimensioni: Elemento XML\Descrizione: Attributo XML'.</span><span class="sxs-lookup"><span data-stu-id="09f5e-176">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element\Desc: XML Attribute'.</span></span>
7. <span data-ttu-id="09f5e-177">Nella struttura, selezionare 'modello: Modello dati Modello di esempio dimensioni finanziarie\Giornale di registrazione: Elenco di record\Transazione: Elenco di record\Dati dimensioni: Elenco di record\Descrizione: Stringa'.</span><span class="sxs-lookup"><span data-stu-id="09f5e-177">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list\Description: String'.</span></span>
8. <span data-ttu-id="09f5e-178">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="09f5e-178">Click Bind.</span></span>
9. <span data-ttu-id="09f5e-179">Nella struttura selezionare 'Nodo principale: Elemento XML\Giornale di registrazione: Elemento XML\Transazione: Elemento XML\Dimensioni: Elemento XML\Valore: Attributo XML'.</span><span class="sxs-lookup"><span data-stu-id="09f5e-179">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element\Value: XML Attribute'.</span></span>
10. <span data-ttu-id="09f5e-180">Nella struttura, selezionare 'modello: Modello dati Modello di esempio dimensioni finanziarie\Giornale di registrazione: Elenco di record\Transazione: Elenco di record\Dati dimensioni: Elenco di record\Codice: Stringa'.</span><span class="sxs-lookup"><span data-stu-id="09f5e-180">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list\Code: String'.</span></span>
11. <span data-ttu-id="09f5e-181">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="09f5e-181">Click Bind.</span></span>
12. <span data-ttu-id="09f5e-182">Nella struttura selezionare 'Nodo principale: Elemento XML\Giornale di registrazione: Elemento XML\Transazione: Elemento XML\Dimensioni: Elemento XML\Codice: Attributo XML'.</span><span class="sxs-lookup"><span data-stu-id="09f5e-182">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element\Code: XML Attribute'.</span></span>
13. <span data-ttu-id="09f5e-183">Nella struttura, selezionare 'modello: Modello dati Modello di esempio dimensioni finanziarie\Giornale di registrazione: Elenco di record\Transazione: Elenco di record\Dati dimensioni: Elenco di record\Nome: Stringa'.</span><span class="sxs-lookup"><span data-stu-id="09f5e-183">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list\Name: String'.</span></span>
14. <span data-ttu-id="09f5e-184">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="09f5e-184">Click Bind.</span></span>
15. <span data-ttu-id="09f5e-185">Nella struttura, selezionare 'modello: Modello dati Modello di esempio dimensioni finanziarie\Giornale di registrazione: Elenco di record\Transazione: Elenco di record\Dati dimensioni: Elenco di record'.</span><span class="sxs-lookup"><span data-stu-id="09f5e-185">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list'.</span></span>
16. <span data-ttu-id="09f5e-186">Nella struttura selezionare 'Nodo principale: Elemento XML\Giornale di registrazione: Elemento XML\Transazione: Elemento XML\Dimensioni: Elemento XML'.</span><span class="sxs-lookup"><span data-stu-id="09f5e-186">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element'.</span></span>
17. <span data-ttu-id="09f5e-187">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="09f5e-187">Click Bind.</span></span>
18. <span data-ttu-id="09f5e-188">Nella struttura selezionare 'Nodo principale: Elemento XML\Giornale di registrazione: Elemento XML\Transazione: Elemento XML\Avere: Attributo XML'.</span><span class="sxs-lookup"><span data-stu-id="09f5e-188">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Ct: XML Attribute'.</span></span>
19. <span data-ttu-id="09f5e-189">Nella struttura, selezionare 'modello: Modello dati Modello di esempio dimensioni finanziarie\Giornale di registrazione: Elenco di record\Transazione: Elenco di record\Avere: Reale'.</span><span class="sxs-lookup"><span data-stu-id="09f5e-189">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Credit: Real'.</span></span>
20. <span data-ttu-id="09f5e-190">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="09f5e-190">Click Bind.</span></span>
21. <span data-ttu-id="09f5e-191">Nella struttura selezionare 'Nodo principale: Elemento XML\Giornale di registrazione: Elemento XML\Transazione: Elemento XML\Dare: Attributo XML'.</span><span class="sxs-lookup"><span data-stu-id="09f5e-191">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dt: XML Attribute'.</span></span>
22. <span data-ttu-id="09f5e-192">Nella struttura, selezionare 'modello: Modello dati Modello di esempio dimensioni finanziarie\Giornale di registrazione: Elenco di record\Transazione: Elenco di record\Dare: Reale'.</span><span class="sxs-lookup"><span data-stu-id="09f5e-192">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Debit: Real'.</span></span>
23. <span data-ttu-id="09f5e-193">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="09f5e-193">Click Bind.</span></span>
24. <span data-ttu-id="09f5e-194">Nella struttura selezionare 'Nodo principale: Elemento XML\Giornale di registrazione: Elemento XML\Transazione: Elemento XML\Valuta: Attributo XML'.</span><span class="sxs-lookup"><span data-stu-id="09f5e-194">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Currency: XML Attribute'.</span></span>
25. <span data-ttu-id="09f5e-195">Nella struttura, selezionare 'modello: Modello dati Modello di esempio dimensioni finanziarie\Giornale di registrazione: Elenco di record\Transazione: Elenco di record\Valuta: Stringa'.</span><span class="sxs-lookup"><span data-stu-id="09f5e-195">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Currency: String'.</span></span>
26. <span data-ttu-id="09f5e-196">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="09f5e-196">Click Bind.</span></span>
27. <span data-ttu-id="09f5e-197">Nella struttura selezionare 'Nodo principale: Elemento XML\Giornale di registrazione: Elemento XML\Transazione: Elemento XML\Data: Attributo XML'.</span><span class="sxs-lookup"><span data-stu-id="09f5e-197">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Date: XML Attribute'.</span></span>
28. <span data-ttu-id="09f5e-198">Nella struttura, selezionare 'modello: Modello dati Modello di esempio dimensioni finanziarie\Giornale di registrazione: Elenco di record\Transazione: Elenco di record\Data: Data'.</span><span class="sxs-lookup"><span data-stu-id="09f5e-198">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Date: Date'.</span></span>
29. <span data-ttu-id="09f5e-199">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="09f5e-199">Click Bind.</span></span>
30. <span data-ttu-id="09f5e-200">Nella struttura selezionare 'Nodo principale: Elemento XML\Giornale di registrazione: Elemento XML\Transazione: Elemento XML\Giustificativo: Attributo XML'.</span><span class="sxs-lookup"><span data-stu-id="09f5e-200">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Voucher: XML Attribute'.</span></span>
31. <span data-ttu-id="09f5e-201">Nella struttura, selezionare 'modello: Modello dati Modello di esempio dimensioni finanziarie\Giornale di registrazione: Elenco di record\Transazione: Elenco di record\Giustificativo: Stringa'.</span><span class="sxs-lookup"><span data-stu-id="09f5e-201">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Voucher: String'.</span></span>
32. <span data-ttu-id="09f5e-202">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="09f5e-202">Click Bind.</span></span>
33. <span data-ttu-id="09f5e-203">Nella struttura selezionare 'Nodo principale: Elemento XML\Giornale di registrazione: Elemento XML\Transazione: Elemento XML'.</span><span class="sxs-lookup"><span data-stu-id="09f5e-203">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element'.</span></span>
34. <span data-ttu-id="09f5e-204">Nella struttura, selezionare 'modello: Modello dati Modello di esempio dimensioni finanziarie\Giornale di registrazione: Elenco di record\Transazione: Elenco di record'.</span><span class="sxs-lookup"><span data-stu-id="09f5e-204">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list'.</span></span>
35. <span data-ttu-id="09f5e-205">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="09f5e-205">Click Bind.</span></span>
36. <span data-ttu-id="09f5e-206">Nella struttura selezionare 'Nodo principale: Elemento XML\Giornale di registrazione: Elemento XML\Batch: Attributo XML'.</span><span class="sxs-lookup"><span data-stu-id="09f5e-206">In the tree, select 'Root: XML Element\Journal: XML Element\Batch: XML Attribute'.</span></span>
37. <span data-ttu-id="09f5e-207">Nella struttura, selezionare 'modello: Modello dati Modello di esempio dimensioni finanziarie\Giornale di registrazione: Elenco di record\Batch: Stringa'.</span><span class="sxs-lookup"><span data-stu-id="09f5e-207">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Batch: String'.</span></span>
38. <span data-ttu-id="09f5e-208">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="09f5e-208">Click Bind.</span></span>
39. <span data-ttu-id="09f5e-209">Nella struttura selezionare 'Nodo principale: Elemento XML\Giornale di registrazione: Elemento XML'.</span><span class="sxs-lookup"><span data-stu-id="09f5e-209">In the tree, select 'Root: XML Element\Journal: XML Element'.</span></span>
40. <span data-ttu-id="09f5e-210">Nella struttura, selezionare 'modello: Modello dati Modello di esempio dimensioni finanziarie\Giornale di registrazione: Elenco di record'.</span><span class="sxs-lookup"><span data-stu-id="09f5e-210">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list'.</span></span>
41. <span data-ttu-id="09f5e-211">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="09f5e-211">Click Bind.</span></span>
42. <span data-ttu-id="09f5e-212">Nella struttura selezionare 'Nodo principale: Elemento XML\Società: Attributo XML'.</span><span class="sxs-lookup"><span data-stu-id="09f5e-212">In the tree, select 'Root: XML Element\Company: XML Attribute'.</span></span>
43. <span data-ttu-id="09f5e-213">Nella struttura, selezionare 'modello: Modello dati Modello di esempio dimensioni finanziarie\Società: Stringa'.</span><span class="sxs-lookup"><span data-stu-id="09f5e-213">In the tree, select 'model: Data model Financial dimensions sample model\Company: String'.</span></span>
44. <span data-ttu-id="09f5e-214">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="09f5e-214">Click Bind.</span></span>
45. <span data-ttu-id="09f5e-215">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="09f5e-215">Click Save.</span></span>
46. <span data-ttu-id="09f5e-216">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="09f5e-216">Close the page.</span></span>


