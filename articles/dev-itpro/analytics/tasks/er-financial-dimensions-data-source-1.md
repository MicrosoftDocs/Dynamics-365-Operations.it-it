---
title: 'ER Utilizzare le dimensioni finanziarie come origine dati (Parte 1: progettare il modello dati)'
description: I passaggi seguenti descrivono come un amministratore di sistema o uno sviluppatore per la creazione di report elettronici può configurare un modello per la creazione di report elettronici in modo che utilizzi dimensioni finanziarie come origine dati per i report elettronici.
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERVendorPart, ERSolutionTable, ERSolutionCreateDropDialog, ERDataModelDesigner, ERDataModelContentsItemCreationDialog
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 84f546b73eefe3ead78c6ab3fdbbc05d0db5fef5
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2019
ms.locfileid: "339512"
---
# <a name="er-use-financial-dimensions-as-a-data-source-part-1-design-data-model"></a><span data-ttu-id="fa7cf-103">ER utilizzare le dimensioni finanziarie come origine dati (parte 1: progettare il modello dati)</span><span class="sxs-lookup"><span data-stu-id="fa7cf-103">ER Use financial dimensions as a data source (Part 1: Design data model)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="fa7cf-104">I passaggi seguenti descrivono come un amministratore di sistema o uno sviluppatore per la creazione di report elettronici può configurare un modello per la creazione di report elettronici in modo che utilizzi dimensioni finanziarie come origine dati per i report elettronici.</span><span class="sxs-lookup"><span data-stu-id="fa7cf-104">The following steps explain how either a system administrator or electronic reporting developer can configure an Electronic reporting (ER) model to use financial dimensions as a data source for ER reports.</span></span> <span data-ttu-id="fa7cf-105">Questi passaggi possono essere eseguiti in qualsiasi società.</span><span class="sxs-lookup"><span data-stu-id="fa7cf-105">These steps can be performed in any company.</span></span>

<span data-ttu-id="fa7cf-106">Per completare questi passaggi, è necessario completare i passaggi della procedura "Creare un provider di configurazione e contrassegnarlo come attivo".</span><span class="sxs-lookup"><span data-stu-id="fa7cf-106">To complete these steps, you must first complete the steps in the procedure, “Create a configuration provider and mark it as active”.</span></span>


## <a name="create-a-new-data-model"></a><span data-ttu-id="fa7cf-107">Creare un nuovo modello dati</span><span class="sxs-lookup"><span data-stu-id="fa7cf-107">Create a new data model</span></span>
1. <span data-ttu-id="fa7cf-108">Andare ad Amministrazione organizzazione > Aree di lavoro > Creazione di report elettronici.</span><span class="sxs-lookup"><span data-stu-id="fa7cf-108">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
    * <span data-ttu-id="fa7cf-109">Assicurarsi che il provider Litware, Inc.</span><span class="sxs-lookup"><span data-stu-id="fa7cf-109">Make sure that the “Litware, Inc.”</span></span> <span data-ttu-id="fa7cf-110">sia disponibile e contrassegnato come attivo.</span><span class="sxs-lookup"><span data-stu-id="fa7cf-110">provider is available and marked as active.</span></span>  
2. <span data-ttu-id="fa7cf-111">Fare clic su Configurazioni report.</span><span class="sxs-lookup"><span data-stu-id="fa7cf-111">Click Reporting configurations.</span></span>
3. <span data-ttu-id="fa7cf-112">Fare clic su Crea configurazione per aprire la finestra di dialogo a discesa .</span><span class="sxs-lookup"><span data-stu-id="fa7cf-112">Click Create configuration to open the drop dialog.</span></span>
4. <span data-ttu-id="fa7cf-113">Nel campo Nome digitare 'Modello di esempio dimensioni finanziarie'.</span><span class="sxs-lookup"><span data-stu-id="fa7cf-113">In the Name field, type 'Financial dimensions sample model'.</span></span>
5. <span data-ttu-id="fa7cf-114">Fare clic su Crea configurazione.</span><span class="sxs-lookup"><span data-stu-id="fa7cf-114">Click Create configuration.</span></span>
6. <span data-ttu-id="fa7cf-115">Fare clic su Progettazione.</span><span class="sxs-lookup"><span data-stu-id="fa7cf-115">Click Designer.</span></span>
7. <span data-ttu-id="fa7cf-116">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="fa7cf-116">Click New to open the drop dialog.</span></span>
8. <span data-ttu-id="fa7cf-117">Digitare 'Voce' nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="fa7cf-117">In the Name field, type 'Entry'.</span></span>
9. <span data-ttu-id="fa7cf-118">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="fa7cf-118">Click Add.</span></span>
10. <span data-ttu-id="fa7cf-119">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="fa7cf-119">Click New to open the drop dialog.</span></span>
11. <span data-ttu-id="fa7cf-120">Nel campo Nome digitare "Società".</span><span class="sxs-lookup"><span data-stu-id="fa7cf-120">In the Name field, type 'Company'.</span></span>
12. <span data-ttu-id="fa7cf-121">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="fa7cf-121">Click Add.</span></span>
    * <span data-ttu-id="fa7cf-122">Aggiungeremo al modello un nuovo elenco di record.</span><span class="sxs-lookup"><span data-stu-id="fa7cf-122">We will add to our model a new record list.</span></span> <span data-ttu-id="fa7cf-123">Questo elenco esporrà (per qualsiasi report ER che usa questo modello come origine dati) le impostazioni delle dimensioni finanziarie selezionate.</span><span class="sxs-lookup"><span data-stu-id="fa7cf-123">This list will expose (for any ER reports using this model as data source) the settings of selected financial dimensions.</span></span> <span data-ttu-id="fa7cf-124">Ogni dimensione finanziaria verrà presentata in questo elenco come record con campi appropriati che rappresentano l'impostazione della dimensione.</span><span class="sxs-lookup"><span data-stu-id="fa7cf-124">Each financial dimension will be presented in this list as a record with appropriate fields representing dimension’s setting.</span></span>  
13. <span data-ttu-id="fa7cf-125">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="fa7cf-125">Click New to open the drop dialog.</span></span>
14. <span data-ttu-id="fa7cf-126">Digitare un 'Impostazione dimensioni' nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="fa7cf-126">In the Name field, type 'Dimensions setting'.</span></span>
15. <span data-ttu-id="fa7cf-127">Nel campo Tipo di articolo selezionare "Elenco di record".</span><span class="sxs-lookup"><span data-stu-id="fa7cf-127">In the Item type field, select 'Record list'.</span></span>
16. <span data-ttu-id="fa7cf-128">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="fa7cf-128">Click Add.</span></span>
17. <span data-ttu-id="fa7cf-129">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="fa7cf-129">Click New to open the drop dialog.</span></span>
18. <span data-ttu-id="fa7cf-130">Digitare 'Codice' nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="fa7cf-130">In the Name field, type 'Code'.</span></span>
19. <span data-ttu-id="fa7cf-131">Nel campo Tipo di articolo selezionare "Stringa".</span><span class="sxs-lookup"><span data-stu-id="fa7cf-131">In the Item type field, select 'String'.</span></span>
20. <span data-ttu-id="fa7cf-132">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="fa7cf-132">Click Add.</span></span>
21. <span data-ttu-id="fa7cf-133">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="fa7cf-133">Click New to open the drop dialog.</span></span>
22. <span data-ttu-id="fa7cf-134">Nel campo Nome digitare "Nome".</span><span class="sxs-lookup"><span data-stu-id="fa7cf-134">In the Name field, type 'Name'.</span></span>
23. <span data-ttu-id="fa7cf-135">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="fa7cf-135">Click Add.</span></span>
24. <span data-ttu-id="fa7cf-136">Nella struttura selezionare 'Voce'.</span><span class="sxs-lookup"><span data-stu-id="fa7cf-136">In the tree, select 'Entry'.</span></span>
25. <span data-ttu-id="fa7cf-137">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="fa7cf-137">Click New to open the drop dialog.</span></span>
26. <span data-ttu-id="fa7cf-138">Digitare 'Giornale di registrazione' nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="fa7cf-138">In the Name field, type 'Journal'.</span></span>
27. <span data-ttu-id="fa7cf-139">Nel campo Tipo di articolo selezionare "Elenco di record".</span><span class="sxs-lookup"><span data-stu-id="fa7cf-139">In the Item type field, select 'Record list'.</span></span>
28. <span data-ttu-id="fa7cf-140">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="fa7cf-140">Click Add.</span></span>
29. <span data-ttu-id="fa7cf-141">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="fa7cf-141">Click New to open the drop dialog.</span></span>
30. <span data-ttu-id="fa7cf-142">Digitare 'Batch'. nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="fa7cf-142">In the Name field, type 'Batch'.</span></span>
31. <span data-ttu-id="fa7cf-143">Nel campo Tipo di articolo selezionare "Stringa".</span><span class="sxs-lookup"><span data-stu-id="fa7cf-143">In the Item type field, select 'String'.</span></span>
32. <span data-ttu-id="fa7cf-144">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="fa7cf-144">Click Add.</span></span>
33. <span data-ttu-id="fa7cf-145">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="fa7cf-145">Click New to open the drop dialog.</span></span>
34. <span data-ttu-id="fa7cf-146">Nel campo Nome digitare 'Transazione'.</span><span class="sxs-lookup"><span data-stu-id="fa7cf-146">In the Name field, type 'Transaction'.</span></span>
35. <span data-ttu-id="fa7cf-147">Nel campo Tipo di articolo selezionare "Elenco di record".</span><span class="sxs-lookup"><span data-stu-id="fa7cf-147">In the Item type field, select 'Record list'.</span></span>
36. <span data-ttu-id="fa7cf-148">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="fa7cf-148">Click Add.</span></span>
37. <span data-ttu-id="fa7cf-149">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="fa7cf-149">Click New to open the drop dialog.</span></span>
38. <span data-ttu-id="fa7cf-150">Digitare 'Data' nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="fa7cf-150">In the Name field, type 'Date'.</span></span>
39. <span data-ttu-id="fa7cf-151">Nel campo Tipo di articolo selezionare "Data".</span><span class="sxs-lookup"><span data-stu-id="fa7cf-151">In the Item type field, select 'Date'.</span></span>
40. <span data-ttu-id="fa7cf-152">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="fa7cf-152">Click Add.</span></span>
41. <span data-ttu-id="fa7cf-153">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="fa7cf-153">Click New to open the drop dialog.</span></span>
42. <span data-ttu-id="fa7cf-154">Digitare 'Dare' nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="fa7cf-154">In the Name field, type 'Debit'.</span></span>
43. <span data-ttu-id="fa7cf-155">Nel campo Tipo di articolo selezionare "Reale".</span><span class="sxs-lookup"><span data-stu-id="fa7cf-155">In the Item type field, select 'Real'.</span></span>
44. <span data-ttu-id="fa7cf-156">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="fa7cf-156">Click Add.</span></span>
45. <span data-ttu-id="fa7cf-157">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="fa7cf-157">Click New to open the drop dialog.</span></span>
46. <span data-ttu-id="fa7cf-158">Nel campo Nome digitare 'Avere'.</span><span class="sxs-lookup"><span data-stu-id="fa7cf-158">In the Name field, type 'Credit'.</span></span>
47. <span data-ttu-id="fa7cf-159">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="fa7cf-159">Click Add.</span></span>
48. <span data-ttu-id="fa7cf-160">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="fa7cf-160">Click New to open the drop dialog.</span></span>
49. <span data-ttu-id="fa7cf-161">Nel campo Nome digitare "Valuta".</span><span class="sxs-lookup"><span data-stu-id="fa7cf-161">In the Name field, type 'Currency'.</span></span>
50. <span data-ttu-id="fa7cf-162">Nel campo Tipo di articolo selezionare "Stringa".</span><span class="sxs-lookup"><span data-stu-id="fa7cf-162">In the Item type field, select 'String'.</span></span>
51. <span data-ttu-id="fa7cf-163">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="fa7cf-163">Click Add.</span></span>
52. <span data-ttu-id="fa7cf-164">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="fa7cf-164">Click New to open the drop dialog.</span></span>
53. <span data-ttu-id="fa7cf-165">Digitare 'Giustificativo' nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="fa7cf-165">In the Name field, type 'Voucher'.</span></span>
54. <span data-ttu-id="fa7cf-166">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="fa7cf-166">Click Add.</span></span>
55. <span data-ttu-id="fa7cf-167">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="fa7cf-167">Click New to open the drop dialog.</span></span>
56. <span data-ttu-id="fa7cf-168">Digitare 'Dati dimensioni' nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="fa7cf-168">In the Name field, type 'Dimensions data'.</span></span>
57. <span data-ttu-id="fa7cf-169">Nel campo Tipo di articolo selezionare "Elenco di record".</span><span class="sxs-lookup"><span data-stu-id="fa7cf-169">In the Item type field, select 'Record list'.</span></span>
58. <span data-ttu-id="fa7cf-170">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="fa7cf-170">Click Add.</span></span>
    * <span data-ttu-id="fa7cf-171">Abbiamo aggiunto al modello un nuovo elenco di record.</span><span class="sxs-lookup"><span data-stu-id="fa7cf-171">We added to our model a new record list.</span></span> <span data-ttu-id="fa7cf-172">Questo elenco esporrà (per qualsiasi report ER che usa questo modello come origine dati) i valori delle dimensioni finanziarie selezionate.</span><span class="sxs-lookup"><span data-stu-id="fa7cf-172">This list will expose (for any ER reports using this model as data source) the values of selected financial dimensions.</span></span> <span data-ttu-id="fa7cf-173">Ogni dimensione finanziaria verrà presentata in questo elenco come record con campi appropriati che rappresentano i valori della dimensione.</span><span class="sxs-lookup"><span data-stu-id="fa7cf-173">Each financial dimension will be presented in this list as a record with appropriate fields representing dimension’s values.</span></span> <span data-ttu-id="fa7cf-174">Anche il nome della dimensione verrà presentato in questo record come campo da utilizzare, se necessario, per facilitare la selezione.</span><span class="sxs-lookup"><span data-stu-id="fa7cf-174">Dimension name will be also presented in this record as a field to be used, if needed, for selection purposes.</span></span>  
59. <span data-ttu-id="fa7cf-175">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="fa7cf-175">Click New to open the drop dialog.</span></span>
60. <span data-ttu-id="fa7cf-176">Digitare 'Codice' nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="fa7cf-176">In the Name field, type 'Code'.</span></span>
61. <span data-ttu-id="fa7cf-177">Nel campo Tipo di articolo selezionare "Stringa".</span><span class="sxs-lookup"><span data-stu-id="fa7cf-177">In the Item type field, select 'String'.</span></span>
62. <span data-ttu-id="fa7cf-178">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="fa7cf-178">Click Add.</span></span>
63. <span data-ttu-id="fa7cf-179">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="fa7cf-179">Click New to open the drop dialog.</span></span>
64. <span data-ttu-id="fa7cf-180">Nel campo Nome digitare "Descrizione".</span><span class="sxs-lookup"><span data-stu-id="fa7cf-180">In the Name field, type 'Description'.</span></span>
65. <span data-ttu-id="fa7cf-181">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="fa7cf-181">Click Add.</span></span>
66. <span data-ttu-id="fa7cf-182">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="fa7cf-182">Click New to open the drop dialog.</span></span>
67. <span data-ttu-id="fa7cf-183">Nel campo Nome digitare "Nome".</span><span class="sxs-lookup"><span data-stu-id="fa7cf-183">In the Name field, type 'Name'.</span></span>
68. <span data-ttu-id="fa7cf-184">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="fa7cf-184">Click Add.</span></span>
69. <span data-ttu-id="fa7cf-185">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="fa7cf-185">Click Save.</span></span>
70. <span data-ttu-id="fa7cf-186">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="fa7cf-186">Close the page.</span></span>

