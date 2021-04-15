---
title: 'ER Utilizzare le dimensioni finanziarie come origine dati (Parte 1: progettare il modello dati)'
description: In questo argomento viene descritto come configurare un modello di Creazione di report elettronici (ER) per utilizzare le dimensioni finanziarie come origine dati per i report ER. (Parte 1)
author: NickSelin
ms.date: 05/27/2020
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERVendorPart, ERSolutionTable, ERSolutionCreateDropDialog, ERDataModelDesigner, ERDataModelContentsItemCreationDialog
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 92b44532dfae70f03d6686ca1d2f8b6f74345ee6
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5752462"
---
# <a name="er-use-financial-dimensions-as-a-data-source-part-1---design-data-model"></a><span data-ttu-id="7f274-104">ER Utilizzare le dimensioni finanziarie come origine dati (Parte 1: progettare il modello dati)</span><span class="sxs-lookup"><span data-stu-id="7f274-104">ER Use financial dimensions as a data source (Part 1 - Design data model)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="7f274-105">I passaggi seguenti descrivono come un amministratore di sistema o uno sviluppatore per la creazione di report elettronici può configurare un modello per la creazione di report elettronici in modo che utilizzi dimensioni finanziarie come origine dati per i report elettronici.</span><span class="sxs-lookup"><span data-stu-id="7f274-105">The following steps explain how either a system administrator or electronic reporting developer can configure an Electronic reporting (ER) model to use financial dimensions as a data source for ER reports.</span></span> <span data-ttu-id="7f274-106">Questi passaggi possono essere eseguiti in qualsiasi società.</span><span class="sxs-lookup"><span data-stu-id="7f274-106">These steps can be performed in any company.</span></span>

<span data-ttu-id="7f274-107">Per completare questi passaggi, è necessario completare i passaggi della procedura "Creare un provider di configurazione e contrassegnarlo come attivo".</span><span class="sxs-lookup"><span data-stu-id="7f274-107">To complete these steps, you must first complete the steps in the procedure, "Create a configuration provider and mark it as active".</span></span>


## <a name="create-a-new-data-model"></a><span data-ttu-id="7f274-108">Creare un nuovo modello dati</span><span class="sxs-lookup"><span data-stu-id="7f274-108">Create a new data model</span></span>
1. <span data-ttu-id="7f274-109">Andare ad Amministrazione organizzazione > Aree di lavoro > Creazione di report elettronici.</span><span class="sxs-lookup"><span data-stu-id="7f274-109">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
    * <span data-ttu-id="7f274-110">Assicurarsi che il provider "Litware, Inc."</span><span class="sxs-lookup"><span data-stu-id="7f274-110">Make sure that the "Litware, Inc."</span></span> <span data-ttu-id="7f274-111">sia disponibile e contrassegnato come attivo.</span><span class="sxs-lookup"><span data-stu-id="7f274-111">provider is available and marked as active.</span></span>  
2. <span data-ttu-id="7f274-112">Fare clic su Configurazioni report.</span><span class="sxs-lookup"><span data-stu-id="7f274-112">Click Reporting configurations.</span></span>
3. <span data-ttu-id="7f274-113">Fare clic su Crea configurazione per aprire la finestra di dialogo a discesa .</span><span class="sxs-lookup"><span data-stu-id="7f274-113">Click Create configuration to open the drop dialog.</span></span>
4. <span data-ttu-id="7f274-114">Nel campo Nome digitare 'Modello di esempio dimensioni finanziarie'.</span><span class="sxs-lookup"><span data-stu-id="7f274-114">In the Name field, type 'Financial dimensions sample model'.</span></span>
5. <span data-ttu-id="7f274-115">Fare clic su Crea configurazione.</span><span class="sxs-lookup"><span data-stu-id="7f274-115">Click Create configuration.</span></span>
6. <span data-ttu-id="7f274-116">Fare clic su Progettazione.</span><span class="sxs-lookup"><span data-stu-id="7f274-116">Click Designer.</span></span>
7. <span data-ttu-id="7f274-117">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="7f274-117">Click New to open the drop dialog.</span></span>
8. <span data-ttu-id="7f274-118">Digitare 'Voce' nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="7f274-118">In the Name field, type 'Entry'.</span></span>
9. <span data-ttu-id="7f274-119">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="7f274-119">Click Add.</span></span>
10. <span data-ttu-id="7f274-120">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="7f274-120">Click New to open the drop dialog.</span></span>
11. <span data-ttu-id="7f274-121">Nel campo Nome digitare "Società".</span><span class="sxs-lookup"><span data-stu-id="7f274-121">In the Name field, type 'Company'.</span></span>
12. <span data-ttu-id="7f274-122">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="7f274-122">Click Add.</span></span>
    * <span data-ttu-id="7f274-123">Aggiungeremo al modello un nuovo elenco di record.</span><span class="sxs-lookup"><span data-stu-id="7f274-123">We will add to our model a new record list.</span></span> <span data-ttu-id="7f274-124">Questo elenco esporrà (per qualsiasi report ER che usa questo modello come origine dati) le impostazioni delle dimensioni finanziarie selezionate.</span><span class="sxs-lookup"><span data-stu-id="7f274-124">This list will expose (for any ER reports using this model as data source) the settings of selected financial dimensions.</span></span> <span data-ttu-id="7f274-125">Ogni dimensione finanziaria verrà presentata in questo elenco come record con campi appropriati che rappresentano l'impostazione della dimensione.</span><span class="sxs-lookup"><span data-stu-id="7f274-125">Each financial dimension will be presented in this list as a record with appropriate fields representing dimension's setting.</span></span>  
13. <span data-ttu-id="7f274-126">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="7f274-126">Click New to open the drop dialog.</span></span>
14. <span data-ttu-id="7f274-127">Digitare un 'Impostazione dimensioni' nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="7f274-127">In the Name field, type 'Dimensions setting'.</span></span>
15. <span data-ttu-id="7f274-128">Nel campo Tipo di articolo selezionare "Elenco di record".</span><span class="sxs-lookup"><span data-stu-id="7f274-128">In the Item type field, select 'Record list'.</span></span>
16. <span data-ttu-id="7f274-129">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="7f274-129">Click Add.</span></span>
17. <span data-ttu-id="7f274-130">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="7f274-130">Click New to open the drop dialog.</span></span>
18. <span data-ttu-id="7f274-131">Digitare 'Codice' nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="7f274-131">In the Name field, type 'Code'.</span></span>
19. <span data-ttu-id="7f274-132">Nel campo Tipo di articolo selezionare "Stringa".</span><span class="sxs-lookup"><span data-stu-id="7f274-132">In the Item type field, select 'String'.</span></span>
20. <span data-ttu-id="7f274-133">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="7f274-133">Click Add.</span></span>
21. <span data-ttu-id="7f274-134">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="7f274-134">Click New to open the drop dialog.</span></span>
22. <span data-ttu-id="7f274-135">Nel campo Nome digitare "Nome".</span><span class="sxs-lookup"><span data-stu-id="7f274-135">In the Name field, type 'Name'.</span></span>
23. <span data-ttu-id="7f274-136">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="7f274-136">Click Add.</span></span>
24. <span data-ttu-id="7f274-137">Nella struttura selezionare 'Voce'.</span><span class="sxs-lookup"><span data-stu-id="7f274-137">In the tree, select 'Entry'.</span></span>
25. <span data-ttu-id="7f274-138">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="7f274-138">Click New to open the drop dialog.</span></span>
26. <span data-ttu-id="7f274-139">Digitare 'Giornale di registrazione' nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="7f274-139">In the Name field, type 'Journal'.</span></span>
27. <span data-ttu-id="7f274-140">Nel campo Tipo di articolo selezionare "Elenco di record".</span><span class="sxs-lookup"><span data-stu-id="7f274-140">In the Item type field, select 'Record list'.</span></span>
28. <span data-ttu-id="7f274-141">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="7f274-141">Click Add.</span></span>
29. <span data-ttu-id="7f274-142">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="7f274-142">Click New to open the drop dialog.</span></span>
30. <span data-ttu-id="7f274-143">Digitare 'Batch'. nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="7f274-143">In the Name field, type 'Batch'.</span></span>
31. <span data-ttu-id="7f274-144">Nel campo Tipo di articolo selezionare "Stringa".</span><span class="sxs-lookup"><span data-stu-id="7f274-144">In the Item type field, select 'String'.</span></span>
32. <span data-ttu-id="7f274-145">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="7f274-145">Click Add.</span></span>
33. <span data-ttu-id="7f274-146">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="7f274-146">Click New to open the drop dialog.</span></span>
34. <span data-ttu-id="7f274-147">Nel campo Nome digitare 'Transazione'.</span><span class="sxs-lookup"><span data-stu-id="7f274-147">In the Name field, type 'Transaction'.</span></span>
35. <span data-ttu-id="7f274-148">Nel campo Tipo di articolo selezionare "Elenco di record".</span><span class="sxs-lookup"><span data-stu-id="7f274-148">In the Item type field, select 'Record list'.</span></span>
36. <span data-ttu-id="7f274-149">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="7f274-149">Click Add.</span></span>
37. <span data-ttu-id="7f274-150">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="7f274-150">Click New to open the drop dialog.</span></span>
38. <span data-ttu-id="7f274-151">Digitare 'Data' nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="7f274-151">In the Name field, type 'Date'.</span></span>
39. <span data-ttu-id="7f274-152">Nel campo Tipo di articolo selezionare "Data".</span><span class="sxs-lookup"><span data-stu-id="7f274-152">In the Item type field, select 'Date'.</span></span>
40. <span data-ttu-id="7f274-153">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="7f274-153">Click Add.</span></span>
41. <span data-ttu-id="7f274-154">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="7f274-154">Click New to open the drop dialog.</span></span>
42. <span data-ttu-id="7f274-155">Digitare 'Dare' nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="7f274-155">In the Name field, type 'Debit'.</span></span>
43. <span data-ttu-id="7f274-156">Nel campo Tipo di articolo selezionare "Reale".</span><span class="sxs-lookup"><span data-stu-id="7f274-156">In the Item type field, select 'Real'.</span></span>
44. <span data-ttu-id="7f274-157">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="7f274-157">Click Add.</span></span>
45. <span data-ttu-id="7f274-158">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="7f274-158">Click New to open the drop dialog.</span></span>
46. <span data-ttu-id="7f274-159">Nel campo Nome digitare 'Avere'.</span><span class="sxs-lookup"><span data-stu-id="7f274-159">In the Name field, type 'Credit'.</span></span>
47. <span data-ttu-id="7f274-160">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="7f274-160">Click Add.</span></span>
48. <span data-ttu-id="7f274-161">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="7f274-161">Click New to open the drop dialog.</span></span>
49. <span data-ttu-id="7f274-162">Nel campo Nome digitare "Valuta".</span><span class="sxs-lookup"><span data-stu-id="7f274-162">In the Name field, type 'Currency'.</span></span>
50. <span data-ttu-id="7f274-163">Nel campo Tipo di articolo selezionare "Stringa".</span><span class="sxs-lookup"><span data-stu-id="7f274-163">In the Item type field, select 'String'.</span></span>
51. <span data-ttu-id="7f274-164">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="7f274-164">Click Add.</span></span>
52. <span data-ttu-id="7f274-165">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="7f274-165">Click New to open the drop dialog.</span></span>
53. <span data-ttu-id="7f274-166">Digitare 'Giustificativo' nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="7f274-166">In the Name field, type 'Voucher'.</span></span>
54. <span data-ttu-id="7f274-167">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="7f274-167">Click Add.</span></span>
55. <span data-ttu-id="7f274-168">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="7f274-168">Click New to open the drop dialog.</span></span>
56. <span data-ttu-id="7f274-169">Digitare 'Dati dimensioni' nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="7f274-169">In the Name field, type 'Dimensions data'.</span></span>
57. <span data-ttu-id="7f274-170">Nel campo Tipo di articolo selezionare "Elenco di record".</span><span class="sxs-lookup"><span data-stu-id="7f274-170">In the Item type field, select 'Record list'.</span></span>
58. <span data-ttu-id="7f274-171">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="7f274-171">Click Add.</span></span>
    * <span data-ttu-id="7f274-172">Abbiamo aggiunto al modello un nuovo elenco di record.</span><span class="sxs-lookup"><span data-stu-id="7f274-172">We added to our model a new record list.</span></span> <span data-ttu-id="7f274-173">Questo elenco esporrà (per qualsiasi report ER che usa questo modello come origine dati) i valori delle dimensioni finanziarie selezionate.</span><span class="sxs-lookup"><span data-stu-id="7f274-173">This list will expose (for any ER reports using this model as data source) the values of selected financial dimensions.</span></span> <span data-ttu-id="7f274-174">Ogni dimensione finanziaria verrà presentata in questo elenco come record con campi appropriati che rappresentano i valori della dimensione.</span><span class="sxs-lookup"><span data-stu-id="7f274-174">Each financial dimension will be presented in this list as a record with appropriate fields representing dimension's values.</span></span> <span data-ttu-id="7f274-175">Anche il nome della dimensione verrà presentato in questo record come campo da utilizzare, se necessario, per facilitare la selezione.</span><span class="sxs-lookup"><span data-stu-id="7f274-175">Dimension name will be also presented in this record as a field to be used, if needed, for selection purposes.</span></span>  
59. <span data-ttu-id="7f274-176">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="7f274-176">Click New to open the drop dialog.</span></span>
60. <span data-ttu-id="7f274-177">Digitare 'Codice' nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="7f274-177">In the Name field, type 'Code'.</span></span>
61. <span data-ttu-id="7f274-178">Nel campo Tipo di articolo selezionare "Stringa".</span><span class="sxs-lookup"><span data-stu-id="7f274-178">In the Item type field, select 'String'.</span></span>
62. <span data-ttu-id="7f274-179">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="7f274-179">Click Add.</span></span>
63. <span data-ttu-id="7f274-180">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="7f274-180">Click New to open the drop dialog.</span></span>
64. <span data-ttu-id="7f274-181">Nel campo Nome digitare "Descrizione".</span><span class="sxs-lookup"><span data-stu-id="7f274-181">In the Name field, type 'Description'.</span></span>
65. <span data-ttu-id="7f274-182">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="7f274-182">Click Add.</span></span>
66. <span data-ttu-id="7f274-183">Fare clic su Nuovo per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="7f274-183">Click New to open the drop dialog.</span></span>
67. <span data-ttu-id="7f274-184">Nel campo Nome digitare "Nome".</span><span class="sxs-lookup"><span data-stu-id="7f274-184">In the Name field, type 'Name'.</span></span>
68. <span data-ttu-id="7f274-185">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="7f274-185">Click Add.</span></span>
69. <span data-ttu-id="7f274-186">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="7f274-186">Click Save.</span></span>
70. <span data-ttu-id="7f274-187">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="7f274-187">Close the page.</span></span>

![Pagina della progettazione del modello di dati ER](../media/er-financial-dimensions-guides-data-model.png)



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]