--- 
title: "Impostare prerequisiti per la gestione di non conformità"
description: "Utilizzare questa procedura per attivare i processi di gestione delle non conformità."
author: perlynne
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventParameters, InventTestReportSetup, SysUserManagement, SysUserSetup, InventTestDiagnosticType, InventTestMiscCharges, InventTestOperation, InventProblemType, InventProblemTypeSetup, InventQuarantineZone
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: 0a4062acc91e024e3a0a41c0b3cb35ff5ffe2a4a
ms.contentlocale: it-it
ms.lasthandoff: 10/16/2018

---
# <a name="set-up-prerequisites-for-nonconformance-management"></a><span data-ttu-id="32887-103">Impostare prerequisiti per la gestione di non conformità</span><span class="sxs-lookup"><span data-stu-id="32887-103">Set up prerequisites for nonconformance management</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="32887-104">Utilizzare questa procedura per attivare i processi di gestione delle non conformità.</span><span class="sxs-lookup"><span data-stu-id="32887-104">Use this procedure to enable nonconformance management processes.</span></span> <span data-ttu-id="32887-105">Con non conformità si intende una procedura o un elemento con un problema di qualità, il cui tipo e la cui origine vengono specificati nelle informazioni descrittive.</span><span class="sxs-lookup"><span data-stu-id="32887-105">A nonconformance describes a procedure or item that has a quality problem, where the descriptive information includes the source and type of problem.</span></span> <span data-ttu-id="32887-106">Questa procedura utilizza la società di dati dimostrativi USMF.</span><span class="sxs-lookup"><span data-stu-id="32887-106">This procedure uses the USMF demo data company.</span></span> <span data-ttu-id="32887-107">In genere, questa procedura viene eseguita da un responsabile della qualità.</span><span class="sxs-lookup"><span data-stu-id="32887-107">This procedure is typically performed by a quality manager.</span></span>


## <a name="enable-quality-management-processes-within-the-company"></a><span data-ttu-id="32887-108">Abilitare i processi di gestione della qualità all'interno della società</span><span class="sxs-lookup"><span data-stu-id="32887-108">Enable quality management processes within the company</span></span>
1. <span data-ttu-id="32887-109">Fare clic su Gestione magazzino > Impostazioni > Parametri di gestione articoli e magazzino.</span><span class="sxs-lookup"><span data-stu-id="32887-109">Go to Inventory management > Setup > Inventory and warehouse management parameters.</span></span>
2. <span data-ttu-id="32887-110">Fare clic sulla scheda Gestione qualità.</span><span class="sxs-lookup"><span data-stu-id="32887-110">Click the Quality management tab.</span></span>
3. <span data-ttu-id="32887-111">Selezionare Sì nel campo Usa Gestione qualità.</span><span class="sxs-lookup"><span data-stu-id="32887-111">Select Yes in the Use quality management field.</span></span>
    * <span data-ttu-id="32887-112">Selezionare questo parametro per attivare i processi di gestione della qualità per la società.</span><span class="sxs-lookup"><span data-stu-id="32887-112">Select this parameter to enable quality management processes for the company.</span></span>  
4. <span data-ttu-id="32887-113">Immettere un numero nel campo Tariffa oraria.</span><span class="sxs-lookup"><span data-stu-id="32887-113">In the Hourly rate field, enter a number.</span></span>
    * <span data-ttu-id="32887-114">Utilizzare il campo Tariffa oraria per immettere una tariffa oraria per la manodopera nella valuta locale.</span><span class="sxs-lookup"><span data-stu-id="32887-114">Use the Hourly rate field to enter an hourly labor rate in the local currency.</span></span> <span data-ttu-id="32887-115">La tariffa oraria viene utilizzata per calcolare i costi delle operazioni correlate a una non conformità.</span><span class="sxs-lookup"><span data-stu-id="32887-115">The hourly rate is used for calculating costs for operations that are related to a nonconformance.</span></span> <span data-ttu-id="32887-116">La tariffa oraria e i costi calcolati forniscono informazioni di riferimento per una non conformità e non interagiscono con altre funzionalità.</span><span class="sxs-lookup"><span data-stu-id="32887-116">The hourly rate and calculated costs provide reference information for a nonconformance, and they do not interact with other functionality.</span></span>  
5. <span data-ttu-id="32887-117">Fare clic su Impostazione report.</span><span class="sxs-lookup"><span data-stu-id="32887-117">Click Report setup.</span></span>
    * <span data-ttu-id="32887-118">Questa pagina consente di definire i tipi di note del report della qualità che verranno utilizzati in diversi tipi di report per la gestione della qualità.</span><span class="sxs-lookup"><span data-stu-id="32887-118">This page allows you define the quality report note types that will be used on different kinds of quality management reports.</span></span>  
6. <span data-ttu-id="32887-119">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="32887-119">Close the page.</span></span>
7. <span data-ttu-id="32887-120">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="32887-120">Close the page.</span></span>

## <a name="enable-user-for-nonconformance-processing"></a><span data-ttu-id="32887-121">Abilitare l'utente per l'elaborazione di non conformità</span><span class="sxs-lookup"><span data-stu-id="32887-121">Enable user for nonconformance processing</span></span>
1. <span data-ttu-id="32887-122">Andare a Amministrazione sistema > Utenti > Utenti.</span><span class="sxs-lookup"><span data-stu-id="32887-122">Go to System administration > Users > Users.</span></span>
    * <span data-ttu-id="32887-123">Per elaborare l'approvazione di una non conformità, l'utente che approva o rifiuta le non conformità deve avere un valore "Nome" assegnato alla pagina Utenti.</span><span class="sxs-lookup"><span data-stu-id="32887-123">To process the approval of a nonconformance the user who  approves or rejects nonconformances must have a “Name” value assigned on the Users page.</span></span> <span data-ttu-id="32887-124">Per utilizzare le note del documento, l'utente deve inoltre avere Gestione documenti attivata nelle opzioni utente.</span><span class="sxs-lookup"><span data-stu-id="32887-124">To use the document notes, the user must also have Document handling activated in the user options.</span></span>  
2. <span data-ttu-id="32887-125">Utilizzare il filtro rapido per trovare i record.</span><span class="sxs-lookup"><span data-stu-id="32887-125">Use the Quick Filter to find records.</span></span> <span data-ttu-id="32887-126">Ad esempio, filtrare il campo Nome con il valore "Ricardo".</span><span class="sxs-lookup"><span data-stu-id="32887-126">For example, filter on the Name field with a value of 'Ricardo'.</span></span>
    * <span data-ttu-id="32887-127">Utilizzare il filtro per trovare l'utente che approverà o rifiuterà i record di non conformità.</span><span class="sxs-lookup"><span data-stu-id="32887-127">Use the filter to find the user who will be approving or rejecting the nonconformance records.</span></span>  
3. <span data-ttu-id="32887-128">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="32887-128">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="32887-129">Per elaborare l'approvazione di una non conformità, verificare che l'utente che approva o rifiuta le non conformità abbia un valore "Nome" assegnato alla pagina Utenti.</span><span class="sxs-lookup"><span data-stu-id="32887-129">To process the approval of a nonconformance, make sure the user who approves or rejects nonconformances has a “Name” value assigned on the Users page.</span></span>  
4. <span data-ttu-id="32887-130">Fare clic su Opzioni utente.</span><span class="sxs-lookup"><span data-stu-id="32887-130">Click User options.</span></span>
5. <span data-ttu-id="32887-131">Fare clic sulla scheda Preferenze.</span><span class="sxs-lookup"><span data-stu-id="32887-131">Click the Preferences tab.</span></span>
6. <span data-ttu-id="32887-132">Selezionare Sì nel campo Attiva gestione documenti.</span><span class="sxs-lookup"><span data-stu-id="32887-132">Select Yes in the Enable document handling field.</span></span>
    * <span data-ttu-id="32887-133">Per utilizzare le note del documento, l'utente deve inoltre avere Gestione documenti attivata nelle opzioni utente.</span><span class="sxs-lookup"><span data-stu-id="32887-133">To use the document notes, the user must also have Document handling activated in the user options.</span></span>  
7. <span data-ttu-id="32887-134">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="32887-134">Close the page.</span></span>
8. <span data-ttu-id="32887-135">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="32887-135">Close the page.</span></span>
9. <span data-ttu-id="32887-136">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="32887-136">Close the page.</span></span>

## <a name="define-diagnostic-types-for-nonconformance-processing"></a><span data-ttu-id="32887-137">Definire i tipi di diagnostica per l'elaborazione di non conformità</span><span class="sxs-lookup"><span data-stu-id="32887-137">Define diagnostic types for nonconformance processing</span></span>
1. <span data-ttu-id="32887-138">Andare a Gestione articoli > Impostazioni > Gestione qualità > Tipi di diagnostica.</span><span class="sxs-lookup"><span data-stu-id="32887-138">Go to Inventory management > Setup > Quality management > Diagnostic types.</span></span>
    * <span data-ttu-id="32887-139">Utilizzare la pagina Tipi di diagnostica per definire una classificazione delle azioni di diagnostica.</span><span class="sxs-lookup"><span data-stu-id="32887-139">Use the Diagnostic types page to define a classification of diagnostic actions.</span></span> <span data-ttu-id="32887-140">Una correzione identifica il tipo di azione di diagnostica che è consigliabile eseguire per una non conformità approvata, l'autore e la data di completamento richiesta e pianificata.</span><span class="sxs-lookup"><span data-stu-id="32887-140">A correction identifies what type of diagnostic action should be taken on an approved nonconformance, who should perform it, and the requested and planned completion date.</span></span>  
2. <span data-ttu-id="32887-141">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="32887-141">Click New.</span></span>
3. <span data-ttu-id="32887-142">Digitare un valore nel campo Diagnostica.</span><span class="sxs-lookup"><span data-stu-id="32887-142">In the Diagnostic field, type a value.</span></span>
4. <span data-ttu-id="32887-143">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="32887-143">In the Description field, type a value.</span></span>
5. <span data-ttu-id="32887-144">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="32887-144">Close the page.</span></span>

## <a name="define-quality-charges-for-nonconformance-processing"></a><span data-ttu-id="32887-145">Definire le spese di gestione qualità per l'elaborazione di non conformità</span><span class="sxs-lookup"><span data-stu-id="32887-145">Define quality charges for nonconformance processing</span></span>
1. <span data-ttu-id="32887-146">Andare a Gestione articoli > Impostazioni > Gestione qualità > Spese gestione qualità.</span><span class="sxs-lookup"><span data-stu-id="32887-146">Go to Inventory management > Setup > Quality management > Quality charges.</span></span>
    * <span data-ttu-id="32887-147">Utilizzare la pagina Spese gestione qualità per definire una classificazione delle spese che verranno utilizzate nelle operazioni correlate alle non conformità.</span><span class="sxs-lookup"><span data-stu-id="32887-147">Use the Quality charges page to define a classification of charges that will used in operations related to nonconformances.</span></span>  
2. <span data-ttu-id="32887-148">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="32887-148">Click New.</span></span>
3. <span data-ttu-id="32887-149">Digitare un valore nel campo Codice spese.</span><span class="sxs-lookup"><span data-stu-id="32887-149">In the Charges code field, type a value.</span></span>
4. <span data-ttu-id="32887-150">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="32887-150">In the Description field, type a value.</span></span>
5. <span data-ttu-id="32887-151">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="32887-151">Close the page.</span></span>

## <a name="define-the-operations-for-nonconformance-processing"></a><span data-ttu-id="32887-152">Definire le operazioni per l'elaborazione di non conformità</span><span class="sxs-lookup"><span data-stu-id="32887-152">Define the operations for nonconformance processing</span></span>
1. <span data-ttu-id="32887-153">Andare a Gestione articoli > Impostazioni > Gestione qualità > Operazioni.</span><span class="sxs-lookup"><span data-stu-id="32887-153">Go to Inventory management > Setup > Quality management > Operations.</span></span>
    * <span data-ttu-id="32887-154">Utilizzare la pagina Operazioni per definire una classificazione delle operazioni che è possibile eseguire per una non conformità approvata.</span><span class="sxs-lookup"><span data-stu-id="32887-154">Use the Operations page to define a classification of the work that may be performed for an approved nonconformance.</span></span> <span data-ttu-id="32887-155">Quando si correla un'operazione a una non conformità, è possibile definire anche informazioni dettagliate sul materiale, le ore di manodopera e le spese varie che sono necessari per l'esecuzione dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="32887-155">When you relate an operation to a nonconformance, you can define information about the associated material, labor hours, and miscellaneous charges that are required to perform the operation.</span></span> <span data-ttu-id="32887-156">Tali informazioni costituiscono la base per il calcolo di un costo stimato per l'esecuzione dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="32887-156">This information provides the basis for calculating an estimated cost for performing the operation.</span></span>  
2. <span data-ttu-id="32887-157">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="32887-157">Click New.</span></span>
3. <span data-ttu-id="32887-158">Digitare un valore nel campo Operazione.</span><span class="sxs-lookup"><span data-stu-id="32887-158">In the Operation field, type a value.</span></span>
4. <span data-ttu-id="32887-159">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="32887-159">In the Description field, type a value.</span></span>
5. <span data-ttu-id="32887-160">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="32887-160">Close the page.</span></span>

## <a name="define-problem-types-for-nonconformance-processing"></a><span data-ttu-id="32887-161">Definire i tipi di problema per l'elaborazione di non conformità</span><span class="sxs-lookup"><span data-stu-id="32887-161">Define problem types for nonconformance processing</span></span>
1. <span data-ttu-id="32887-162">Andare a Gestione articoli > Impostazioni > Gestione qualità > Tipi di problema.</span><span class="sxs-lookup"><span data-stu-id="32887-162">Go to Inventory management > Setup > Quality management > Problem types.</span></span>
    * <span data-ttu-id="32887-163">Utilizzare la pagina Tipi di problemi per definire una classificazione dei problemi relativi alla qualità riscontarti nei vari tipi di non conformità.</span><span class="sxs-lookup"><span data-stu-id="32887-163">Use the Problem types page to define a classification of quality problems that are encountered in the various nonconformance types.</span></span> <span data-ttu-id="32887-164">I tipi di non conformità includono Interno, Cliente, Fornitore, Richiesta di assistenza, Produzione e Produzione co-prodotti.</span><span class="sxs-lookup"><span data-stu-id="32887-164">The nonconformance types include Internal, Customer, Vendor, Service request, Production, and Co-product production.</span></span> <span data-ttu-id="32887-165">Un tipo di problema singolo può essere associato a più tipi di non conformità.</span><span class="sxs-lookup"><span data-stu-id="32887-165">A single problem type can be associated with multiple nonconformance types.</span></span>  
2. <span data-ttu-id="32887-166">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="32887-166">Click New.</span></span>
3. <span data-ttu-id="32887-167">Digitare un valore nel campo Tipo di problema.</span><span class="sxs-lookup"><span data-stu-id="32887-167">In the Problem type field, type a value.</span></span>
4. <span data-ttu-id="32887-168">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="32887-168">In the Description field, type a value.</span></span>
5. <span data-ttu-id="32887-169">Fare clic su Tipi di non conformità.</span><span class="sxs-lookup"><span data-stu-id="32887-169">Click Non conformance types.</span></span>
    * <span data-ttu-id="32887-170">Utilizzare la pagina Tipi di non conformità per autorizzare l'utilizzo di un tipo di problema per uno o più tipi di non conformità.</span><span class="sxs-lookup"><span data-stu-id="32887-170">Use the Non conformance types page to authorize the use of a problem type for one or more of the nonconformance types.</span></span> <span data-ttu-id="32887-171">Un tipo di problema relativo a un codice errato, ad esempio, può essere applicato a tutti i tipi di non conformità, mentre un tipo di problema relativo a reclami dei clienti può essere utilizzato solo per i tipi di non conformità cliente e richiesta di assistenza.</span><span class="sxs-lookup"><span data-stu-id="32887-171">For example, a problem type regarding a defect code could apply to all nonconformance types, whereas a problem type about customer complaints may only apply to the customer and service request nonconformance types.</span></span>  
6. <span data-ttu-id="32887-172">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="32887-172">Click New.</span></span>
7. <span data-ttu-id="32887-173">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="32887-173">In the list, mark the selected row.</span></span>
8. <span data-ttu-id="32887-174">Selezionare un'opzione nel campo Tipo di non conformità.</span><span class="sxs-lookup"><span data-stu-id="32887-174">In the Non conformance type field, select an option.</span></span>
9. <span data-ttu-id="32887-175">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="32887-175">Close the page.</span></span>
10. <span data-ttu-id="32887-176">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="32887-176">Close the page.</span></span>

## <a name="define-quarantine-zones-for-nonconformance-processing"></a><span data-ttu-id="32887-177">Definire le aree quarantena per l'elaborazione di non conformità</span><span class="sxs-lookup"><span data-stu-id="32887-177">Define quarantine zones for nonconformance processing</span></span>
1. <span data-ttu-id="32887-178">Andare a Gestione articoli > Impostazioni > Gestione qualità > Aree quarantena.</span><span class="sxs-lookup"><span data-stu-id="32887-178">Go to Inventory management > Setup > Quality management > Quarantine zones.</span></span>
2. <span data-ttu-id="32887-179">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="32887-179">Click New.</span></span>
3. <span data-ttu-id="32887-180">Digitare un valore nel campo Aree quarantena.</span><span class="sxs-lookup"><span data-stu-id="32887-180">In the Quarantine zone field, type a value.</span></span>
4. <span data-ttu-id="32887-181">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="32887-181">In the Description field, type a value.</span></span>
5. <span data-ttu-id="32887-182">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="32887-182">Close the page.</span></span>


