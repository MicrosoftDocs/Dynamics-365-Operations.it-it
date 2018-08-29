--- 
title: Progettare report per utilizzare le dimensioni finanziarie come origini dati
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
ms.sourcegitcommit: e782d33f3748524491dace28008cd9148ae70529
ms.openlocfilehash: 055401104ae62c75694dff0b2ee64d12b2621686
ms.contentlocale: it-it
ms.lasthandoff: 08/09/2018

---
# <a name="design-reports-to-use-financial-dimensions-as-data-sources"></a><span data-ttu-id="6e746-103">Progettare report per utilizzare le dimensioni finanziarie come origini dati</span><span class="sxs-lookup"><span data-stu-id="6e746-103">Design reports to use financial dimensions as data sources</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="6e746-104">I passaggi seguenti descrivono come un utente con ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può configurare un modello per la creazione di report elettronici in modo che utilizzi dimensioni finanziarie come origine dati per i report elettronici.</span><span class="sxs-lookup"><span data-stu-id="6e746-104">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) model to use financial dimensions as a data source for ER reports.</span></span> <span data-ttu-id="6e746-105">Questi passaggi possono essere eseguiti in qualsiasi società.</span><span class="sxs-lookup"><span data-stu-id="6e746-105">These steps can be performed in any company.</span></span>

<span data-ttu-id="6e746-106">Per effettuare questi passaggi, è innanzitutto necessario completare i passaggi nella procedura 'ER Usare dimensioni finanziarie come origine dati (parte 2: mapping del modello)'.</span><span class="sxs-lookup"><span data-stu-id="6e746-106">To complete these steps, you must first complete the steps in the “ER Use financial dimensions as a data source (Part 2: Model mapping)” procedure.</span></span>


## <a name="design-a-report-to-present-financial-dimensions"></a><span data-ttu-id="6e746-107">Progettare un report per presentare dimensioni finanziarie</span><span class="sxs-lookup"><span data-stu-id="6e746-107">Design a report to present financial dimensions</span></span>
1. <span data-ttu-id="6e746-108">Passare a Amministrazione organizzazione > Reporting elettronico > Configurazioni.</span><span class="sxs-lookup"><span data-stu-id="6e746-108">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="6e746-109">Nella struttura selezionare 'Modello di esempio dimensioni finanziarie'.</span><span class="sxs-lookup"><span data-stu-id="6e746-109">In the tree, select 'Financial dimensions sample model'.</span></span>
3. <span data-ttu-id="6e746-110">Fare clic su Crea configurazione per aprire la finestra di dialogo a discesa .</span><span class="sxs-lookup"><span data-stu-id="6e746-110">Click Create configuration to open the drop dialog.</span></span>
4. <span data-ttu-id="6e746-111">Nel campo Nuovo immettere 'Formato basato sul modello dati Modello di esempio dimensioni finanziarie'.</span><span class="sxs-lookup"><span data-stu-id="6e746-111">In the New field, enter 'Format based on data model Financial dimensions sample model'.</span></span>
    * <span data-ttu-id="6e746-112">Utilizzare il modello creato in anticipo come origine dati per il nuovo report.</span><span class="sxs-lookup"><span data-stu-id="6e746-112">Use the model that was created in advance as the data source for your new report.</span></span>  
5. <span data-ttu-id="6e746-113">Nel campo Nome digitare 'Report dei giornali di registrazione di contabilità generale'.</span><span class="sxs-lookup"><span data-stu-id="6e746-113">In the Name field, type 'Ledger journal report'.</span></span>
6. <span data-ttu-id="6e746-114">Selezionare Voce nel campo Definizione modello dati.</span><span class="sxs-lookup"><span data-stu-id="6e746-114">In the Data model definition field, select Entry.</span></span>
7. <span data-ttu-id="6e746-115">Fare clic su Crea configurazione.</span><span class="sxs-lookup"><span data-stu-id="6e746-115">Click Create configuration.</span></span>
8. <span data-ttu-id="6e746-116">Fare clic su Progettazione.</span><span class="sxs-lookup"><span data-stu-id="6e746-116">Click Designer.</span></span>
9. <span data-ttu-id="6e746-117">Fare clic su Aggiungi radice per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="6e746-117">Click Add root to open the drop dialog.</span></span>
10. <span data-ttu-id="6e746-118">Nella struttura selezionare "XML\Elemento".</span><span class="sxs-lookup"><span data-stu-id="6e746-118">In the tree, select 'XML\Element'.</span></span>
11. <span data-ttu-id="6e746-119">Digitare 'Nodo principale' nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="6e746-119">In the Name field, type 'Root'.</span></span>
12. <span data-ttu-id="6e746-120">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="6e746-120">Click OK.</span></span>
13. <span data-ttu-id="6e746-121">Fare clic su Aggiungi per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="6e746-121">Click Add to open the drop dialog.</span></span>
14. <span data-ttu-id="6e746-122">Nella struttura selezionare "XML\Attributo".</span><span class="sxs-lookup"><span data-stu-id="6e746-122">In the tree, select 'XML\Attribute'.</span></span>
15. <span data-ttu-id="6e746-123">Nel campo Nome digitare "Società".</span><span class="sxs-lookup"><span data-stu-id="6e746-123">In the Name field, type 'Company'.</span></span>
16. <span data-ttu-id="6e746-124">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="6e746-124">Click OK.</span></span>
17. <span data-ttu-id="6e746-125">Fare clic su Aggiungi per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="6e746-125">Click Add to open the drop dialog.</span></span>
18. <span data-ttu-id="6e746-126">Nella struttura selezionare "XML\Elemento".</span><span class="sxs-lookup"><span data-stu-id="6e746-126">In the tree, select 'XML\Element'.</span></span>
19. <span data-ttu-id="6e746-127">Digitare 'Giornale di registrazione' nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="6e746-127">In the Name field, type 'Journal'.</span></span>
20. <span data-ttu-id="6e746-128">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="6e746-128">Click OK.</span></span>
21. <span data-ttu-id="6e746-129">Nella struttura selezionare 'Nodo principale: Elemento XML\Giornale di registrazione: Elemento XML'.</span><span class="sxs-lookup"><span data-stu-id="6e746-129">In the tree, select 'Root: XML Element\Journal: XML Element'.</span></span>
22. <span data-ttu-id="6e746-130">Fare clic su Aggiungi per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="6e746-130">Click Add to open the drop dialog.</span></span>
23. <span data-ttu-id="6e746-131">Nella struttura selezionare "XML\Attributo".</span><span class="sxs-lookup"><span data-stu-id="6e746-131">In the tree, select 'XML\Attribute'.</span></span>
24. <span data-ttu-id="6e746-132">Digitare 'Batch'. nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="6e746-132">In the Name field, type 'Batch'.</span></span>
25. <span data-ttu-id="6e746-133">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="6e746-133">Click OK.</span></span>
26. <span data-ttu-id="6e746-134">Fare clic su Aggiungi per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="6e746-134">Click Add to open the drop dialog.</span></span>
27. <span data-ttu-id="6e746-135">Nella struttura selezionare "XML\Elemento".</span><span class="sxs-lookup"><span data-stu-id="6e746-135">In the tree, select 'XML\Element'.</span></span>
28. <span data-ttu-id="6e746-136">Nel campo Nome digitare 'Transazione'.</span><span class="sxs-lookup"><span data-stu-id="6e746-136">In the Name field, type 'Transaction'.</span></span>
29. <span data-ttu-id="6e746-137">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="6e746-137">Click OK.</span></span>
30. <span data-ttu-id="6e746-138">Nella struttura selezionare 'Nodo principale: Elemento XML\Giornale di registrazione: Elemento XML\Transazione: Elemento XML'.</span><span class="sxs-lookup"><span data-stu-id="6e746-138">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element'.</span></span>
31. <span data-ttu-id="6e746-139">Fare clic su Aggiungi per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="6e746-139">Click Add to open the drop dialog.</span></span>
32. <span data-ttu-id="6e746-140">Nella struttura selezionare "XML\Attributo".</span><span class="sxs-lookup"><span data-stu-id="6e746-140">In the tree, select 'XML\Attribute'.</span></span>
33. <span data-ttu-id="6e746-141">Digitare 'Giustificativo' nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="6e746-141">In the Name field, type 'Voucher'.</span></span>
34. <span data-ttu-id="6e746-142">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="6e746-142">Click OK.</span></span>
35. <span data-ttu-id="6e746-143">Fare clic su Aggiungi attributo.</span><span class="sxs-lookup"><span data-stu-id="6e746-143">Click Add Attribute.</span></span>
36. <span data-ttu-id="6e746-144">Digitare 'Data' nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="6e746-144">In the Name field, type 'Date'.</span></span>
37. <span data-ttu-id="6e746-145">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="6e746-145">Click OK.</span></span>
38. <span data-ttu-id="6e746-146">Fare clic su Aggiungi attributo.</span><span class="sxs-lookup"><span data-stu-id="6e746-146">Click Add Attribute.</span></span>
39. <span data-ttu-id="6e746-147">Nel campo Nome digitare "Valuta".</span><span class="sxs-lookup"><span data-stu-id="6e746-147">In the Name field, type 'Currency'.</span></span>
40. <span data-ttu-id="6e746-148">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="6e746-148">Click OK.</span></span>
41. <span data-ttu-id="6e746-149">Fare clic su Aggiungi attributo.</span><span class="sxs-lookup"><span data-stu-id="6e746-149">Click Add Attribute.</span></span>
42. <span data-ttu-id="6e746-150">Nel campo Nome digitare 'Dare'.</span><span class="sxs-lookup"><span data-stu-id="6e746-150">In the Name field, type 'Dt'.</span></span>
43. <span data-ttu-id="6e746-151">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="6e746-151">Click OK.</span></span>
44. <span data-ttu-id="6e746-152">Fare clic su Aggiungi attributo.</span><span class="sxs-lookup"><span data-stu-id="6e746-152">Click Add Attribute.</span></span>
45. <span data-ttu-id="6e746-153">Nel campo Nome digitare 'Avere'.</span><span class="sxs-lookup"><span data-stu-id="6e746-153">In the Name field, type 'Ct'.</span></span>
46. <span data-ttu-id="6e746-154">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="6e746-154">Click OK.</span></span>
47. <span data-ttu-id="6e746-155">Fare clic su Aggiungi per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="6e746-155">Click Add to open the drop dialog.</span></span>
48. <span data-ttu-id="6e746-156">Nella struttura selezionare "XML\Elemento".</span><span class="sxs-lookup"><span data-stu-id="6e746-156">In the tree, select 'XML\Element'.</span></span>
49. <span data-ttu-id="6e746-157">Digitare 'Dimensioni' nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="6e746-157">In the Name field, type 'Dimensions'.</span></span>
50. <span data-ttu-id="6e746-158">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="6e746-158">Click OK.</span></span>
51. <span data-ttu-id="6e746-159">Nella struttura selezionare 'Nodo principale: Elemento XML\Giornale di registrazione: Elemento XML\Transazione: Elemento XML\Dimensioni: Elemento XML'.</span><span class="sxs-lookup"><span data-stu-id="6e746-159">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element'.</span></span>
52. <span data-ttu-id="6e746-160">Fare clic su Aggiungi per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="6e746-160">Click Add to open the drop dialog.</span></span>
53. <span data-ttu-id="6e746-161">Nella struttura selezionare "XML\Attributo".</span><span class="sxs-lookup"><span data-stu-id="6e746-161">In the tree, select 'XML\Attribute'.</span></span>
54. <span data-ttu-id="6e746-162">Digitare 'Codice' nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="6e746-162">In the Name field, type 'Code'.</span></span>
55. <span data-ttu-id="6e746-163">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="6e746-163">Click OK.</span></span>
56. <span data-ttu-id="6e746-164">Fare clic su Aggiungi attributo.</span><span class="sxs-lookup"><span data-stu-id="6e746-164">Click Add Attribute.</span></span>
57. <span data-ttu-id="6e746-165">Nel campo Nome digitare 'Valore'.</span><span class="sxs-lookup"><span data-stu-id="6e746-165">In the Name field, type 'Value'.</span></span>
58. <span data-ttu-id="6e746-166">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="6e746-166">Click OK.</span></span>
59. <span data-ttu-id="6e746-167">Fare clic su Aggiungi attributo.</span><span class="sxs-lookup"><span data-stu-id="6e746-167">Click Add Attribute.</span></span>
60. <span data-ttu-id="6e746-168">Nel campo Nome digitare 'Descrizione'.</span><span class="sxs-lookup"><span data-stu-id="6e746-168">In the Name field, type 'Desc'.</span></span>
61. <span data-ttu-id="6e746-169">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="6e746-169">Click OK.</span></span>

## <a name="map-report-elements-to-data-sources"></a><span data-ttu-id="6e746-170">Mappare gli elementi del report alle origini dati</span><span class="sxs-lookup"><span data-stu-id="6e746-170">Map report elements to data sources</span></span>
1. <span data-ttu-id="6e746-171">Fare clic sulla scheda Mapping.</span><span class="sxs-lookup"><span data-stu-id="6e746-171">Click the Mapping tab.</span></span>
2. <span data-ttu-id="6e746-172">Nella struttura, espandere 'modello: Modello dati Modello di esempio dimensioni finanziarie'.</span><span class="sxs-lookup"><span data-stu-id="6e746-172">In the tree, expand 'model: Data model Financial dimensions sample model'.</span></span>
3. <span data-ttu-id="6e746-173">Nella struttura, espandere 'modello: Modello dati Modello di esempio dimensioni finanziarie\Giornale di registrazione: Elenco di record'.</span><span class="sxs-lookup"><span data-stu-id="6e746-173">In the tree, expand 'model: Data model Financial dimensions sample model\Journal: Record list'.</span></span>
4. <span data-ttu-id="6e746-174">Nella struttura, espandere 'modello: Modello dati Modello di esempio dimensioni finanziarie\Giornale di registrazione: Elenco di record\Transazione: Elenco di record'.</span><span class="sxs-lookup"><span data-stu-id="6e746-174">In the tree, expand 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list'.</span></span>
5. <span data-ttu-id="6e746-175">Nella struttura, espandere 'modello: Modello dati Modello di esempio dimensioni finanziarie\Giornale di registrazione: Elenco di record\Transazione: Elenco di record\Dati dimensioni: Elenco di record'.</span><span class="sxs-lookup"><span data-stu-id="6e746-175">In the tree, expand 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list'.</span></span>
6. <span data-ttu-id="6e746-176">Nella struttura selezionare 'Nodo principale: Elemento XML\Giornale di registrazione: Elemento XML\Transazione: Elemento XML\Dimensioni: Elemento XML\Descrizione: Attributo XML'.</span><span class="sxs-lookup"><span data-stu-id="6e746-176">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element\Desc: XML Attribute'.</span></span>
7. <span data-ttu-id="6e746-177">Nella struttura, selezionare 'modello: Modello dati Modello di esempio dimensioni finanziarie\Giornale di registrazione: Elenco di record\Transazione: Elenco di record\Dati dimensioni: Elenco di record\Descrizione: Stringa'.</span><span class="sxs-lookup"><span data-stu-id="6e746-177">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list\Description: String'.</span></span>
8. <span data-ttu-id="6e746-178">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="6e746-178">Click Bind.</span></span>
9. <span data-ttu-id="6e746-179">Nella struttura selezionare 'Nodo principale: Elemento XML\Giornale di registrazione: Elemento XML\Transazione: Elemento XML\Dimensioni: Elemento XML\Valore: Attributo XML'.</span><span class="sxs-lookup"><span data-stu-id="6e746-179">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element\Value: XML Attribute'.</span></span>
10. <span data-ttu-id="6e746-180">Nella struttura, selezionare 'modello: Modello dati Modello di esempio dimensioni finanziarie\Giornale di registrazione: Elenco di record\Transazione: Elenco di record\Dati dimensioni: Elenco di record\Codice: Stringa'.</span><span class="sxs-lookup"><span data-stu-id="6e746-180">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list\Code: String'.</span></span>
11. <span data-ttu-id="6e746-181">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="6e746-181">Click Bind.</span></span>
12. <span data-ttu-id="6e746-182">Nella struttura selezionare 'Nodo principale: Elemento XML\Giornale di registrazione: Elemento XML\Transazione: Elemento XML\Dimensioni: Elemento XML\Codice: Attributo XML'.</span><span class="sxs-lookup"><span data-stu-id="6e746-182">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element\Code: XML Attribute'.</span></span>
13. <span data-ttu-id="6e746-183">Nella struttura, selezionare 'modello: Modello dati Modello di esempio dimensioni finanziarie\Giornale di registrazione: Elenco di record\Transazione: Elenco di record\Dati dimensioni: Elenco di record\Nome: Stringa'.</span><span class="sxs-lookup"><span data-stu-id="6e746-183">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list\Name: String'.</span></span>
14. <span data-ttu-id="6e746-184">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="6e746-184">Click Bind.</span></span>
15. <span data-ttu-id="6e746-185">Nella struttura, selezionare 'modello: Modello dati Modello di esempio dimensioni finanziarie\Giornale di registrazione: Elenco di record\Transazione: Elenco di record\Dati dimensioni: Elenco di record'.</span><span class="sxs-lookup"><span data-stu-id="6e746-185">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list'.</span></span>
16. <span data-ttu-id="6e746-186">Nella struttura selezionare 'Nodo principale: Elemento XML\Giornale di registrazione: Elemento XML\Transazione: Elemento XML\Dimensioni: Elemento XML'.</span><span class="sxs-lookup"><span data-stu-id="6e746-186">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element'.</span></span>
17. <span data-ttu-id="6e746-187">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="6e746-187">Click Bind.</span></span>
18. <span data-ttu-id="6e746-188">Nella struttura selezionare 'Nodo principale: Elemento XML\Giornale di registrazione: Elemento XML\Transazione: Elemento XML\Avere: Attributo XML'.</span><span class="sxs-lookup"><span data-stu-id="6e746-188">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Ct: XML Attribute'.</span></span>
19. <span data-ttu-id="6e746-189">Nella struttura, selezionare 'modello: Modello dati Modello di esempio dimensioni finanziarie\Giornale di registrazione: Elenco di record\Transazione: Elenco di record\Avere: Reale'.</span><span class="sxs-lookup"><span data-stu-id="6e746-189">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Credit: Real'.</span></span>
20. <span data-ttu-id="6e746-190">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="6e746-190">Click Bind.</span></span>
21. <span data-ttu-id="6e746-191">Nella struttura selezionare 'Nodo principale: Elemento XML\Giornale di registrazione: Elemento XML\Transazione: Elemento XML\Dare: Attributo XML'.</span><span class="sxs-lookup"><span data-stu-id="6e746-191">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dt: XML Attribute'.</span></span>
22. <span data-ttu-id="6e746-192">Nella struttura, selezionare 'modello: Modello dati Modello di esempio dimensioni finanziarie\Giornale di registrazione: Elenco di record\Transazione: Elenco di record\Dare: Reale'.</span><span class="sxs-lookup"><span data-stu-id="6e746-192">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Debit: Real'.</span></span>
23. <span data-ttu-id="6e746-193">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="6e746-193">Click Bind.</span></span>
24. <span data-ttu-id="6e746-194">Nella struttura selezionare 'Nodo principale: Elemento XML\Giornale di registrazione: Elemento XML\Transazione: Elemento XML\Valuta: Attributo XML'.</span><span class="sxs-lookup"><span data-stu-id="6e746-194">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Currency: XML Attribute'.</span></span>
25. <span data-ttu-id="6e746-195">Nella struttura, selezionare 'modello: Modello dati Modello di esempio dimensioni finanziarie\Giornale di registrazione: Elenco di record\Transazione: Elenco di record\Valuta: Stringa'.</span><span class="sxs-lookup"><span data-stu-id="6e746-195">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Currency: String'.</span></span>
26. <span data-ttu-id="6e746-196">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="6e746-196">Click Bind.</span></span>
27. <span data-ttu-id="6e746-197">Nella struttura selezionare 'Nodo principale: Elemento XML\Giornale di registrazione: Elemento XML\Transazione: Elemento XML\Data: Attributo XML'.</span><span class="sxs-lookup"><span data-stu-id="6e746-197">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Date: XML Attribute'.</span></span>
28. <span data-ttu-id="6e746-198">Nella struttura, selezionare 'modello: Modello dati Modello di esempio dimensioni finanziarie\Giornale di registrazione: Elenco di record\Transazione: Elenco di record\Data: Data'.</span><span class="sxs-lookup"><span data-stu-id="6e746-198">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Date: Date'.</span></span>
29. <span data-ttu-id="6e746-199">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="6e746-199">Click Bind.</span></span>
30. <span data-ttu-id="6e746-200">Nella struttura selezionare 'Nodo principale: Elemento XML\Giornale di registrazione: Elemento XML\Transazione: Elemento XML\Giustificativo: Attributo XML'.</span><span class="sxs-lookup"><span data-stu-id="6e746-200">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Voucher: XML Attribute'.</span></span>
31. <span data-ttu-id="6e746-201">Nella struttura, selezionare 'modello: Modello dati Modello di esempio dimensioni finanziarie\Giornale di registrazione: Elenco di record\Transazione: Elenco di record\Giustificativo: Stringa'.</span><span class="sxs-lookup"><span data-stu-id="6e746-201">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Voucher: String'.</span></span>
32. <span data-ttu-id="6e746-202">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="6e746-202">Click Bind.</span></span>
33. <span data-ttu-id="6e746-203">Nella struttura selezionare 'Nodo principale: Elemento XML\Giornale di registrazione: Elemento XML\Transazione: Elemento XML'.</span><span class="sxs-lookup"><span data-stu-id="6e746-203">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element'.</span></span>
34. <span data-ttu-id="6e746-204">Nella struttura, selezionare 'modello: Modello dati Modello di esempio dimensioni finanziarie\Giornale di registrazione: Elenco di record\Transazione: Elenco di record'.</span><span class="sxs-lookup"><span data-stu-id="6e746-204">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list'.</span></span>
35. <span data-ttu-id="6e746-205">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="6e746-205">Click Bind.</span></span>
36. <span data-ttu-id="6e746-206">Nella struttura selezionare 'Nodo principale: Elemento XML\Giornale di registrazione: Elemento XML\Batch: Attributo XML'.</span><span class="sxs-lookup"><span data-stu-id="6e746-206">In the tree, select 'Root: XML Element\Journal: XML Element\Batch: XML Attribute'.</span></span>
37. <span data-ttu-id="6e746-207">Nella struttura, selezionare 'modello: Modello dati Modello di esempio dimensioni finanziarie\Giornale di registrazione: Elenco di record\Batch: Stringa'.</span><span class="sxs-lookup"><span data-stu-id="6e746-207">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Batch: String'.</span></span>
38. <span data-ttu-id="6e746-208">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="6e746-208">Click Bind.</span></span>
39. <span data-ttu-id="6e746-209">Nella struttura selezionare 'Nodo principale: Elemento XML\Giornale di registrazione: Elemento XML'.</span><span class="sxs-lookup"><span data-stu-id="6e746-209">In the tree, select 'Root: XML Element\Journal: XML Element'.</span></span>
40. <span data-ttu-id="6e746-210">Nella struttura, selezionare 'modello: Modello dati Modello di esempio dimensioni finanziarie\Giornale di registrazione: Elenco di record'.</span><span class="sxs-lookup"><span data-stu-id="6e746-210">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list'.</span></span>
41. <span data-ttu-id="6e746-211">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="6e746-211">Click Bind.</span></span>
42. <span data-ttu-id="6e746-212">Nella struttura selezionare 'Nodo principale: Elemento XML\Società: Attributo XML'.</span><span class="sxs-lookup"><span data-stu-id="6e746-212">In the tree, select 'Root: XML Element\Company: XML Attribute'.</span></span>
43. <span data-ttu-id="6e746-213">Nella struttura, selezionare 'modello: Modello dati Modello di esempio dimensioni finanziarie\Società: Stringa'.</span><span class="sxs-lookup"><span data-stu-id="6e746-213">In the tree, select 'model: Data model Financial dimensions sample model\Company: String'.</span></span>
44. <span data-ttu-id="6e746-214">Fare clic su Associa.</span><span class="sxs-lookup"><span data-stu-id="6e746-214">Click Bind.</span></span>
45. <span data-ttu-id="6e746-215">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="6e746-215">Click Save.</span></span>
46. <span data-ttu-id="6e746-216">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="6e746-216">Close the page.</span></span>


