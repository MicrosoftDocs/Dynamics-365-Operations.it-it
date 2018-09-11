--- 
title: Abilitare la stampa di etichette targa
description: Questa procedura consente la stampa automatica di un'etichetta Serial Shipping Container Code (SSCC) dopo il prelievo dell'ultimo articolo dall'inventario in un processo del lavoro di prelievo vendite.
author: perlynne
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SysCorpNetPrinterList, WHSParameters, NumberSequenceTableListPage, NumberSequenceDetails, WHSDocumentRoutingLayout, WHSDocumentRouting, WHSRFMenuItem, WHSRFMenu, WHSWorkTemplateTable
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 32d71167fdad65cb1dec37671999a497759ca484
ms.openlocfilehash: d562e3a757ed0d8dd0ccc88119cfaadb7d8e1c1f
ms.contentlocale: it-it
ms.lasthandoff: 09/11/2018

---
# <a name="enable-license-plate-label-printing"></a><span data-ttu-id="9f2f3-103">Abilitare la stampa di etichette targa</span><span class="sxs-lookup"><span data-stu-id="9f2f3-103">Enable license plate label printing</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="9f2f3-104">Questa procedura consente la stampa automatica di un'etichetta Serial Shipping Container Code (SSCC) dopo il prelievo dell'ultimo articolo dall'inventario in un processo del lavoro di prelievo vendite.</span><span class="sxs-lookup"><span data-stu-id="9f2f3-104">This procedure enables the automatic printing of a Serial shipping container code (SSCC) label after the last item is picked from inventory in a sales picking work process.</span></span> <span data-ttu-id="9f2f3-105">È possibile eseguire questa procedura nella società di dati dimostrativi USMF.</span><span class="sxs-lookup"><span data-stu-id="9f2f3-105">You can run this procedure in demo data company USMF.</span></span> <span data-ttu-id="9f2f3-106">Se tale procedura è stata eseguita utilizzando i propri dati, è necessario disporre di una sequenza numerica impostata per le targhe.</span><span class="sxs-lookup"><span data-stu-id="9f2f3-106">If you’re run it using your own data, you need to have a number sequence set up for license plates.</span></span> <span data-ttu-id="9f2f3-107">È necessario impostare una stampante di etichette prima di iniziare questa attività.</span><span class="sxs-lookup"><span data-stu-id="9f2f3-107">You need to set up a label printer before you begin this task.</span></span> <span data-ttu-id="9f2f3-108">Fare clic su Amministrazione organizzazione > Impostazioni > Stampanti di rete.</span><span class="sxs-lookup"><span data-stu-id="9f2f3-108">Go to Organization administration > Setup > Network printers.</span></span> <span data-ttu-id="9f2f3-109">Nel riquadro azioni fare clic su Opzioni, quindi sul pulsante Scarica programma di installazione agente di distribuzione documenti.</span><span class="sxs-lookup"><span data-stu-id="9f2f3-109">On the Action pane, click Options, and then click the Download document routing agent installer button.</span></span> <span data-ttu-id="9f2f3-110">Eseguire il programma di installazione e assicurarsi di disporre di una stampante di rete operativa impostata su Attiva prima di continuare con la procedura.</span><span class="sxs-lookup"><span data-stu-id="9f2f3-110">Run the installer and make sure that you have a working network printer set to Active before you continue with the procedure.</span></span>


## <a name="set-up-the-gs1-company-prefix"></a><span data-ttu-id="9f2f3-111">Imposta il prefisso della società GS1</span><span class="sxs-lookup"><span data-stu-id="9f2f3-111">Set up the GS1 company prefix</span></span>
1. <span data-ttu-id="9f2f3-112">Andare a Gestione magazzino > Impostazioni > Parametri di gestione magazzino.</span><span class="sxs-lookup"><span data-stu-id="9f2f3-112">Go to Warehouse management > Setup > Warehouse management parameters.</span></span>
2. <span data-ttu-id="9f2f3-113">Nel campo Prefisso società GS1 immettere i 7 numeri per il numero di società GS1.</span><span class="sxs-lookup"><span data-stu-id="9f2f3-113">In the GS1 company prefix field, enter the 7 numbers for your GS1 company number.</span></span>
3. <span data-ttu-id="9f2f3-114">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="9f2f3-114">Click Save.</span></span>
4. <span data-ttu-id="9f2f3-115">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="9f2f3-115">Close the page.</span></span>

## <a name="setup-the-sscc-license-plate-number-sequence"></a><span data-ttu-id="9f2f3-116">Imposta la sequenza del numero di identificazione SSCC</span><span class="sxs-lookup"><span data-stu-id="9f2f3-116">Setup the SSCC license plate number sequence</span></span>
1. <span data-ttu-id="9f2f3-117">Andare a Amministrazione organizzazione > Sequenze numeriche > Sequenze numeriche.</span><span class="sxs-lookup"><span data-stu-id="9f2f3-117">Go to Organization administration > Number sequences > Number sequences.</span></span>
2. <span data-ttu-id="9f2f3-118">Selezionare un'opzione nel campo Area.</span><span class="sxs-lookup"><span data-stu-id="9f2f3-118">In the Area field, select an option.</span></span>
3. <span data-ttu-id="9f2f3-119">Selezionare un'opzione nel campo Riferimento.</span><span class="sxs-lookup"><span data-stu-id="9f2f3-119">In the Reference field, select an option.</span></span>
4. <span data-ttu-id="9f2f3-120">Digitare un valore nel campo Società.</span><span class="sxs-lookup"><span data-stu-id="9f2f3-120">In the Company field, type a value.</span></span>
5. <span data-ttu-id="9f2f3-121">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="9f2f3-121">In the list, mark the selected row.</span></span>
6. <span data-ttu-id="9f2f3-122">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="9f2f3-122">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="9f2f3-123">Espandere la sezione Segmenti.</span><span class="sxs-lookup"><span data-stu-id="9f2f3-123">Expand the Segments section.</span></span>
8. <span data-ttu-id="9f2f3-124">Fare clic su Modifica.</span><span class="sxs-lookup"><span data-stu-id="9f2f3-124">Click Edit.</span></span>
9. <span data-ttu-id="9f2f3-125">Nella tabella Segmenti, selezionare la prima riga</span><span class="sxs-lookup"><span data-stu-id="9f2f3-125">In the Segments table, select the first row</span></span>
10. <span data-ttu-id="9f2f3-126">Fare clic su Rimuovi.</span><span class="sxs-lookup"><span data-stu-id="9f2f3-126">Click Remove.</span></span>
11. <span data-ttu-id="9f2f3-127">Fare clic su Rimuovi.</span><span class="sxs-lookup"><span data-stu-id="9f2f3-127">Click Remove.</span></span>
12. <span data-ttu-id="9f2f3-128">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="9f2f3-128">Click Save.</span></span>
13. <span data-ttu-id="9f2f3-129">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="9f2f3-129">Close the page.</span></span>

## <a name="create-the-document-route-layout"></a><span data-ttu-id="9f2f3-130">Crea il layout di distribuzione dei documenti</span><span class="sxs-lookup"><span data-stu-id="9f2f3-130">Create the document route layout</span></span>
1. <span data-ttu-id="9f2f3-131">Andare a Gestione magazzino > Impostazioni > Distribuzione documenti > Layout distribuzione documenti.</span><span class="sxs-lookup"><span data-stu-id="9f2f3-131">Go to Warehouse management > Setup > Document routing > Document routing layouts.</span></span>
    * <span data-ttu-id="9f2f3-132">Attiva il layout di SSCC.</span><span class="sxs-lookup"><span data-stu-id="9f2f3-132">Enable the SSCC layout.</span></span>  
2. <span data-ttu-id="9f2f3-133">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="9f2f3-133">Click New.</span></span>
3. <span data-ttu-id="9f2f3-134">Digitare un valore nel campo ID layout.</span><span class="sxs-lookup"><span data-stu-id="9f2f3-134">In the Layout ID field, type a value.</span></span>
4. <span data-ttu-id="9f2f3-135">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="9f2f3-135">In the Description field, type a value.</span></span>
5. <span data-ttu-id="9f2f3-136">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="9f2f3-136">In the list, find and select the desired record.</span></span>
6. <span data-ttu-id="9f2f3-137">Fare clic su Inserisci al termine del testo.</span><span class="sxs-lookup"><span data-stu-id="9f2f3-137">Click Insert at end of text.</span></span>
7. <span data-ttu-id="9f2f3-138">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="9f2f3-138">Click Save.</span></span>
8. <span data-ttu-id="9f2f3-139">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="9f2f3-139">Close the page.</span></span>

## <a name="set-up-the-document-routing"></a><span data-ttu-id="9f2f3-140">Imposta la distribuzione dei documenti</span><span class="sxs-lookup"><span data-stu-id="9f2f3-140">Set up the document routing</span></span>
1. <span data-ttu-id="9f2f3-141">Andare a Gestione magazzino > Impostazioni > Distribuzione documenti > Distribuzione documenti.</span><span class="sxs-lookup"><span data-stu-id="9f2f3-141">Go to Warehouse management > Setup > Document routing > Document routing.</span></span>
2. <span data-ttu-id="9f2f3-142">Nel campo Tipo ordine di lavoro selezionare un'opzione.</span><span class="sxs-lookup"><span data-stu-id="9f2f3-142">In the Work order type field, select an option.</span></span>
3. <span data-ttu-id="9f2f3-143">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="9f2f3-143">Click New.</span></span>
4. <span data-ttu-id="9f2f3-144">Digitare un valore nel campo Magazzino.</span><span class="sxs-lookup"><span data-stu-id="9f2f3-144">In the Warehouse field, type a value.</span></span>
5. <span data-ttu-id="9f2f3-145">Digitare un valore nel campo Nome.</span><span class="sxs-lookup"><span data-stu-id="9f2f3-145">In the Name field, type a value.</span></span>
6. <span data-ttu-id="9f2f3-146">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="9f2f3-146">Click New.</span></span>
7. <span data-ttu-id="9f2f3-147">Nel campo ID layout, immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="9f2f3-147">In the Layout ID field, enter or select a value.</span></span>
8. <span data-ttu-id="9f2f3-148">Nel campo Nome selezionare il nome della stampante che si desidera utilizzare.</span><span class="sxs-lookup"><span data-stu-id="9f2f3-148">In the Name field, enter the printer name that you want to use..</span></span>
9. <span data-ttu-id="9f2f3-149">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="9f2f3-149">Click Save.</span></span>
10. <span data-ttu-id="9f2f3-150">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="9f2f3-150">Close the page.</span></span>

## <a name="create-mobile-device-menu"></a><span data-ttu-id="9f2f3-151">Crea il menu del dispositivo mobile</span><span class="sxs-lookup"><span data-stu-id="9f2f3-151">Create mobile device menu</span></span>
1. <span data-ttu-id="9f2f3-152">Andare a Gestione magazzino > Impostazioni > Dispositivo mobile > Voci di menu del dispositivo mobile.</span><span class="sxs-lookup"><span data-stu-id="9f2f3-152">Go to Warehouse management > Setup > Mobile device > Mobile device menu items.</span></span>
2. <span data-ttu-id="9f2f3-153">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="9f2f3-153">Click New.</span></span>
3. <span data-ttu-id="9f2f3-154">Digitare un valore nel campo Nome voce di menu.</span><span class="sxs-lookup"><span data-stu-id="9f2f3-154">In the Menu item name field, type a value.</span></span>
4. <span data-ttu-id="9f2f3-155">Digitare un valore nel campo Titolo.</span><span class="sxs-lookup"><span data-stu-id="9f2f3-155">In the Title field, type a value.</span></span>
5. <span data-ttu-id="9f2f3-156">Selezionare un'opzione nel campo Modalità.</span><span class="sxs-lookup"><span data-stu-id="9f2f3-156">In the Mode field, select an option.</span></span>
6. <span data-ttu-id="9f2f3-157">Selezionare Sì nel campo Utilizza lavoro esistente.</span><span class="sxs-lookup"><span data-stu-id="9f2f3-157">Select Yes in the Use existing work field.</span></span>
7. <span data-ttu-id="9f2f3-158">Selezionare Sì nel campo Genera targa.</span><span class="sxs-lookup"><span data-stu-id="9f2f3-158">Select Yes in the Generate license plate field.</span></span>
8. <span data-ttu-id="9f2f3-159">Espandere la sezione Classi di lavoro.</span><span class="sxs-lookup"><span data-stu-id="9f2f3-159">Expand the Work classes section.</span></span>
9. <span data-ttu-id="9f2f3-160">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="9f2f3-160">Click New.</span></span>
10. <span data-ttu-id="9f2f3-161">Nel campo ID classe, digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="9f2f3-161">In the Work class ID field, type a value.</span></span>
11. <span data-ttu-id="9f2f3-162">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="9f2f3-162">Click Save.</span></span>
12. <span data-ttu-id="9f2f3-163">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="9f2f3-163">Close the page.</span></span>
13. <span data-ttu-id="9f2f3-164">Andare a Gestione magazzino > Impostazioni > Dispositivo mobile > Menu del dispositivo mobile.</span><span class="sxs-lookup"><span data-stu-id="9f2f3-164">Go to Warehouse management > Setup > Mobile device > Mobile device menu.</span></span>
14. <span data-ttu-id="9f2f3-165">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="9f2f3-165">In the list, find and select the desired record.</span></span>
15. <span data-ttu-id="9f2f3-166">Nella struttura selezionare "Nella struttura selezionare la voce di menu creata prima".</span><span class="sxs-lookup"><span data-stu-id="9f2f3-166">In the tree, select 'In the tree, select the menu item that you created before.'.</span></span>
16. <span data-ttu-id="9f2f3-167">Fare clic su Modifica.</span><span class="sxs-lookup"><span data-stu-id="9f2f3-167">Click Edit.</span></span>
17. <span data-ttu-id="9f2f3-168">Fare clic sulla freccia per aggiungere la voce di menu al menu.</span><span class="sxs-lookup"><span data-stu-id="9f2f3-168">Click on the arrow to add the menu item to the menu.</span></span>
18. <span data-ttu-id="9f2f3-169">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="9f2f3-169">Click Save.</span></span>
19. <span data-ttu-id="9f2f3-170">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="9f2f3-170">Close the page.</span></span>

## <a name="update-a-work-template"></a><span data-ttu-id="9f2f3-171">Aggiorna un modello di lavoro</span><span class="sxs-lookup"><span data-stu-id="9f2f3-171">Update a work template</span></span>
1. <span data-ttu-id="9f2f3-172">Andare a Gestione magazzino > Impostazioni > Lavoro > Modelli di lavoro.</span><span class="sxs-lookup"><span data-stu-id="9f2f3-172">Go to Warehouse management > Setup > Work > Work templates.</span></span>
2. <span data-ttu-id="9f2f3-173">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="9f2f3-173">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="9f2f3-174">Fare clic su Modifica.</span><span class="sxs-lookup"><span data-stu-id="9f2f3-174">Click Edit.</span></span>
4. <span data-ttu-id="9f2f3-175">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="9f2f3-175">Click New.</span></span>
5. <span data-ttu-id="9f2f3-176">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="9f2f3-176">In the list, mark the selected row.</span></span>
6. <span data-ttu-id="9f2f3-177">Nel campo Tipo di lavoro, selezionare 'Stampa'.</span><span class="sxs-lookup"><span data-stu-id="9f2f3-177">In the Work type field, select 'Print'.</span></span>
7. <span data-ttu-id="9f2f3-178">Nel campo ID classe lavoro immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="9f2f3-178">In the Work class ID field, enter or select a value.</span></span>
8. <span data-ttu-id="9f2f3-179">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="9f2f3-179">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="9f2f3-180">Fare clic su Sposta su.</span><span class="sxs-lookup"><span data-stu-id="9f2f3-180">Click Move up.</span></span>
10. <span data-ttu-id="9f2f3-181">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="9f2f3-181">Click Save.</span></span>
11. <span data-ttu-id="9f2f3-182">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="9f2f3-182">Close the page.</span></span>


