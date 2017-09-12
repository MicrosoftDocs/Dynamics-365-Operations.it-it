--- 
title: Progettare il modello dati per utilizzare le dimensioni finanziarie come origine dati per la creazione di report elettronici (ER)
description: "I passaggi seguenti descrivono come un amministratore di sistema o uno sviluppatore per la creazione di report elettronici può configurare un modello per la creazione di report elettronici in modo che utilizzi dimensioni finanziarie come origine dati per i report elettronici."
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
ms.openlocfilehash: 0953ffb3a98d4f2852caecc3a59792698d1c9d9b
ms.contentlocale: it-it
ms.lasthandoff: 08/29/2017

---
# <a name="design-data-model-to-use-financial-dimensions-as-a-data-source-for-electronic-reporting-er"></a><span data-ttu-id="6ef60-103">Progettare il modello dati per utilizzare le dimensioni finanziarie come origine dati per la creazione di report elettronici (ER)</span><span class="sxs-lookup"><span data-stu-id="6ef60-103">Design data model to use financial dimensions as a data source for electronic reporting (ER)</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="6ef60-104">I passaggi seguenti descrivono come un amministratore di sistema o uno sviluppatore per la creazione di report elettronici può configurare un modello per la creazione di report elettronici in modo che utilizzi dimensioni finanziarie come origine dati per i report elettronici.</span><span class="sxs-lookup"><span data-stu-id="6ef60-104">The following steps explain how either a system administrator or electronic reporting developer can configure an Electronic reporting (ER) model to use financial dimensions as a data source for ER reports.</span></span> <span data-ttu-id="6ef60-105">Questi passaggi possono essere eseguiti in qualsiasi società.</span><span class="sxs-lookup"><span data-stu-id="6ef60-105">These steps can be performed in any company.</span></span>

<span data-ttu-id="6ef60-106">Per completare questi passaggi, è necessario completare i passaggi della procedura "Creare un provider di configurazione e contrassegnarlo come attivo".</span><span class="sxs-lookup"><span data-stu-id="6ef60-106">To complete these steps, you must first complete the steps in the procedure, “Create a configuration provider and mark it as active”.</span></span>


## <a name="create-a-new-data-model"></a><span data-ttu-id="6ef60-107">Creare un nuovo modello dati</span><span class="sxs-lookup"><span data-stu-id="6ef60-107">Create a new data model</span></span>
1. <span data-ttu-id="6ef60-108">Andare ad Amministrazione organizzazione > Aree di lavoro > Creazione di report elettronici.</span><span class="sxs-lookup"><span data-stu-id="6ef60-108">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
    * <span data-ttu-id="6ef60-109">Assicurarsi che il provider Litware, Inc.</span><span class="sxs-lookup"><span data-stu-id="6ef60-109">Make sure that the “Litware, Inc.”</span></span> <span data-ttu-id="6ef60-110">sia disponibile e contrassegnato come attivo.</span><span class="sxs-lookup"><span data-stu-id="6ef60-110">provider is available and marked as active.</span></span>  
2. <span data-ttu-id="6ef60-111">Fare clic su Configurazioni report.</span><span class="sxs-lookup"><span data-stu-id="6ef60-111">Click Reporting configurations.</span></span>
3. <span data-ttu-id="6ef60-112">Fare clic su Crea configurazione per aprire la finestra di dialogo a discesa .</span><span class="sxs-lookup"><span data-stu-id="6ef60-112">Click Create configuration to open the drop dialog.</span></span>
4. <span data-ttu-id="6ef60-113">Nel campo Nome digitare 'Modello di esempio dimensioni finanziarie'.</span><span class="sxs-lookup"><span data-stu-id="6ef60-113">In the Name field, type 'Financial dimensions sample model'.</span></span>
5. <span data-ttu-id="6ef60-114">Fare clic su Crea configurazione.</span><span class="sxs-lookup"><span data-stu-id="6ef60-114">Click Create configuration.</span></span>
6. <span data-ttu-id="6ef60-115">Fare clic su Progettazione.</span><span class="sxs-lookup"><span data-stu-id="6ef60-115">Click Designer.</span></span>
7. <span data-ttu-id="6ef60-116">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="6ef60-116">Click New to open the drop dialog.</span></span>
8. <span data-ttu-id="6ef60-117">Digitare 'Voce' nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="6ef60-117">In the Name field, type 'Entry'.</span></span>
9. <span data-ttu-id="6ef60-118">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="6ef60-118">Click Add.</span></span>
10. <span data-ttu-id="6ef60-119">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="6ef60-119">Click New to open the drop dialog.</span></span>
11. <span data-ttu-id="6ef60-120">Nel campo Nome digitare "Società".</span><span class="sxs-lookup"><span data-stu-id="6ef60-120">In the Name field, type 'Company'.</span></span>
12. <span data-ttu-id="6ef60-121">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="6ef60-121">Click Add.</span></span>
    * <span data-ttu-id="6ef60-122">Aggiungeremo al modello un nuovo elenco di record.</span><span class="sxs-lookup"><span data-stu-id="6ef60-122">We will add to our model a new record list.</span></span> <span data-ttu-id="6ef60-123">Questo elenco esporrà (per qualsiasi report ER che usa questo modello come origine dati) le impostazioni delle dimensioni finanziarie selezionate.</span><span class="sxs-lookup"><span data-stu-id="6ef60-123">This list will expose (for any ER reports using this model as data source) the settings of selected financial dimensions.</span></span> <span data-ttu-id="6ef60-124">Ogni dimensione finanziaria verrà presentata in questo elenco come record con campi appropriati che rappresentano l'impostazione della dimensione.</span><span class="sxs-lookup"><span data-stu-id="6ef60-124">Each financial dimension will be presented in this list as a record with appropriate fields representing dimension’s setting.</span></span>  
13. <span data-ttu-id="6ef60-125">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="6ef60-125">Click New to open the drop dialog.</span></span>
14. <span data-ttu-id="6ef60-126">Digitare un 'Impostazione dimensioni' nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="6ef60-126">In the Name field, type 'Dimensions setting'.</span></span>
15. <span data-ttu-id="6ef60-127">Nel campo Tipo di articolo selezionare "Elenco di record".</span><span class="sxs-lookup"><span data-stu-id="6ef60-127">In the Item type field, select 'Record list'.</span></span>
16. <span data-ttu-id="6ef60-128">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="6ef60-128">Click Add.</span></span>
17. <span data-ttu-id="6ef60-129">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="6ef60-129">Click New to open the drop dialog.</span></span>
18. <span data-ttu-id="6ef60-130">Digitare 'Codice' nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="6ef60-130">In the Name field, type 'Code'.</span></span>
19. <span data-ttu-id="6ef60-131">Nel campo Tipo di articolo selezionare "Stringa".</span><span class="sxs-lookup"><span data-stu-id="6ef60-131">In the Item type field, select 'String'.</span></span>
20. <span data-ttu-id="6ef60-132">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="6ef60-132">Click Add.</span></span>
21. <span data-ttu-id="6ef60-133">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="6ef60-133">Click New to open the drop dialog.</span></span>
22. <span data-ttu-id="6ef60-134">Nel campo Nome digitare "Nome".</span><span class="sxs-lookup"><span data-stu-id="6ef60-134">In the Name field, type 'Name'.</span></span>
23. <span data-ttu-id="6ef60-135">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="6ef60-135">Click Add.</span></span>
24. <span data-ttu-id="6ef60-136">Nella struttura selezionare 'Voce'.</span><span class="sxs-lookup"><span data-stu-id="6ef60-136">In the tree, select 'Entry'.</span></span>
25. <span data-ttu-id="6ef60-137">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="6ef60-137">Click New to open the drop dialog.</span></span>
26. <span data-ttu-id="6ef60-138">Digitare 'Giornale di registrazione' nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="6ef60-138">In the Name field, type 'Journal'.</span></span>
27. <span data-ttu-id="6ef60-139">Nel campo Tipo di articolo selezionare "Elenco di record".</span><span class="sxs-lookup"><span data-stu-id="6ef60-139">In the Item type field, select 'Record list'.</span></span>
28. <span data-ttu-id="6ef60-140">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="6ef60-140">Click Add.</span></span>
29. <span data-ttu-id="6ef60-141">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="6ef60-141">Click New to open the drop dialog.</span></span>
30. <span data-ttu-id="6ef60-142">Digitare 'Batch'. nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="6ef60-142">In the Name field, type 'Batch'.</span></span>
31. <span data-ttu-id="6ef60-143">Nel campo Tipo di articolo selezionare "Stringa".</span><span class="sxs-lookup"><span data-stu-id="6ef60-143">In the Item type field, select 'String'.</span></span>
32. <span data-ttu-id="6ef60-144">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="6ef60-144">Click Add.</span></span>
33. <span data-ttu-id="6ef60-145">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="6ef60-145">Click New to open the drop dialog.</span></span>
34. <span data-ttu-id="6ef60-146">Nel campo Nome digitare 'Transazione'.</span><span class="sxs-lookup"><span data-stu-id="6ef60-146">In the Name field, type 'Transaction'.</span></span>
35. <span data-ttu-id="6ef60-147">Nel campo Tipo di articolo selezionare "Elenco di record".</span><span class="sxs-lookup"><span data-stu-id="6ef60-147">In the Item type field, select 'Record list'.</span></span>
36. <span data-ttu-id="6ef60-148">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="6ef60-148">Click Add.</span></span>
37. <span data-ttu-id="6ef60-149">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="6ef60-149">Click New to open the drop dialog.</span></span>
38. <span data-ttu-id="6ef60-150">Digitare 'Data' nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="6ef60-150">In the Name field, type 'Date'.</span></span>
39. <span data-ttu-id="6ef60-151">Nel campo Tipo di articolo selezionare "Data".</span><span class="sxs-lookup"><span data-stu-id="6ef60-151">In the Item type field, select 'Date'.</span></span>
40. <span data-ttu-id="6ef60-152">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="6ef60-152">Click Add.</span></span>
41. <span data-ttu-id="6ef60-153">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="6ef60-153">Click New to open the drop dialog.</span></span>
42. <span data-ttu-id="6ef60-154">Digitare 'Dare' nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="6ef60-154">In the Name field, type 'Debit'.</span></span>
43. <span data-ttu-id="6ef60-155">Nel campo Tipo di articolo selezionare "Reale".</span><span class="sxs-lookup"><span data-stu-id="6ef60-155">In the Item type field, select 'Real'.</span></span>
44. <span data-ttu-id="6ef60-156">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="6ef60-156">Click Add.</span></span>
45. <span data-ttu-id="6ef60-157">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="6ef60-157">Click New to open the drop dialog.</span></span>
46. <span data-ttu-id="6ef60-158">Nel campo Nome digitare 'Avere'.</span><span class="sxs-lookup"><span data-stu-id="6ef60-158">In the Name field, type 'Credit'.</span></span>
47. <span data-ttu-id="6ef60-159">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="6ef60-159">Click Add.</span></span>
48. <span data-ttu-id="6ef60-160">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="6ef60-160">Click New to open the drop dialog.</span></span>
49. <span data-ttu-id="6ef60-161">Nel campo Nome digitare "Valuta".</span><span class="sxs-lookup"><span data-stu-id="6ef60-161">In the Name field, type 'Currency'.</span></span>
50. <span data-ttu-id="6ef60-162">Nel campo Tipo di articolo selezionare "Stringa".</span><span class="sxs-lookup"><span data-stu-id="6ef60-162">In the Item type field, select 'String'.</span></span>
51. <span data-ttu-id="6ef60-163">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="6ef60-163">Click Add.</span></span>
52. <span data-ttu-id="6ef60-164">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="6ef60-164">Click New to open the drop dialog.</span></span>
53. <span data-ttu-id="6ef60-165">Digitare 'Giustificativo' nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="6ef60-165">In the Name field, type 'Voucher'.</span></span>
54. <span data-ttu-id="6ef60-166">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="6ef60-166">Click Add.</span></span>
55. <span data-ttu-id="6ef60-167">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="6ef60-167">Click New to open the drop dialog.</span></span>
56. <span data-ttu-id="6ef60-168">Digitare 'Dati dimensioni' nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="6ef60-168">In the Name field, type 'Dimensions data'.</span></span>
57. <span data-ttu-id="6ef60-169">Nel campo Tipo di articolo selezionare "Elenco di record".</span><span class="sxs-lookup"><span data-stu-id="6ef60-169">In the Item type field, select 'Record list'.</span></span>
58. <span data-ttu-id="6ef60-170">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="6ef60-170">Click Add.</span></span>
    * <span data-ttu-id="6ef60-171">Abbiamo aggiunto al modello un nuovo elenco di record.</span><span class="sxs-lookup"><span data-stu-id="6ef60-171">We added to our model a new record list.</span></span> <span data-ttu-id="6ef60-172">Questo elenco esporrà (per qualsiasi report ER che usa questo modello come origine dati) i valori delle dimensioni finanziarie selezionate.</span><span class="sxs-lookup"><span data-stu-id="6ef60-172">This list will expose (for any ER reports using this model as data source) the values of selected financial dimensions.</span></span> <span data-ttu-id="6ef60-173">Ogni dimensione finanziaria verrà presentata in questo elenco come record con campi appropriati che rappresentano i valori della dimensione.</span><span class="sxs-lookup"><span data-stu-id="6ef60-173">Each financial dimension will be presented in this list as a record with appropriate fields representing dimension’s values.</span></span> <span data-ttu-id="6ef60-174">Anche il nome della dimensione verrà presentato in questo record come campo da utilizzare, se necessario, per facilitare la selezione.</span><span class="sxs-lookup"><span data-stu-id="6ef60-174">Dimension name will be also presented in this record as a field to be used, if needed, for selection purposes.</span></span>  
59. <span data-ttu-id="6ef60-175">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="6ef60-175">Click New to open the drop dialog.</span></span>
60. <span data-ttu-id="6ef60-176">Digitare 'Codice' nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="6ef60-176">In the Name field, type 'Code'.</span></span>
61. <span data-ttu-id="6ef60-177">Nel campo Tipo di articolo selezionare "Stringa".</span><span class="sxs-lookup"><span data-stu-id="6ef60-177">In the Item type field, select 'String'.</span></span>
62. <span data-ttu-id="6ef60-178">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="6ef60-178">Click Add.</span></span>
63. <span data-ttu-id="6ef60-179">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="6ef60-179">Click New to open the drop dialog.</span></span>
64. <span data-ttu-id="6ef60-180">Nel campo Nome digitare "Descrizione".</span><span class="sxs-lookup"><span data-stu-id="6ef60-180">In the Name field, type 'Description'.</span></span>
65. <span data-ttu-id="6ef60-181">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="6ef60-181">Click Add.</span></span>
66. <span data-ttu-id="6ef60-182">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="6ef60-182">Click New to open the drop dialog.</span></span>
67. <span data-ttu-id="6ef60-183">Nel campo Nome digitare "Nome".</span><span class="sxs-lookup"><span data-stu-id="6ef60-183">In the Name field, type 'Name'.</span></span>
68. <span data-ttu-id="6ef60-184">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="6ef60-184">Click Add.</span></span>
69. <span data-ttu-id="6ef60-185">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="6ef60-185">Click Save.</span></span>
70. <span data-ttu-id="6ef60-186">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="6ef60-186">Close the page.</span></span>


