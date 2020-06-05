---
title: Abilitare la stampa di etichette targa
description: In questo argomento viene descritto come abilitare la stampa automatica di un'etichetta Serial Shipping Container Code (SSCC) dopo il prelievo dell'ultimo articolo dall'inventario in un processo del lavoro di prelievo vendite.
author: perlynne
manager: tfehr
ms.date: 07/19/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysCorpNetPrinterList, WHSParameters, NumberSequenceTableListPage, NumberSequenceDetails, WHSDocumentRoutingLayout, WHSDocumentRouting, WHSRFMenuItem, WHSRFMenu, WHSWorkTemplateTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 43dc913e84fa53179855d7ab8dbbf4d179e2cc63
ms.sourcegitcommit: 8a2127c5af6cdbda30ccc1f9bef9bd4ab61e9e50
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/18/2020
ms.locfileid: "3383046"
---
# <a name="enable-license-plate-label-printing"></a><span data-ttu-id="550b7-103">Abilitare la stampa di etichette targa</span><span class="sxs-lookup"><span data-stu-id="550b7-103">Enable license plate label printing</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="550b7-104">In questo argomento viene descritto come abilitare la stampa automatica di un'etichetta Serial Shipping Container Code (SSCC) dopo il prelievo dell'ultimo articolo dall'inventario in un processo del lavoro di prelievo vendite.</span><span class="sxs-lookup"><span data-stu-id="550b7-104">This topic shows how to enable the automatic printing of a Serial shipping container code (SSCC) label after the last item is picked from inventory in a sales picking work process.</span></span> <span data-ttu-id="550b7-105">È possibile eseguire questa procedura nella società di dati dimostrativi USMF.</span><span class="sxs-lookup"><span data-stu-id="550b7-105">You can run this procedure in demo data company USMF.</span></span> <span data-ttu-id="550b7-106">Se tale procedura è stata eseguita utilizzando i propri dati, è necessario disporre di una sequenza numerica impostata per le targhe.</span><span class="sxs-lookup"><span data-stu-id="550b7-106">If you're run it using your own data, you need to have a number sequence set up for license plates.</span></span> <span data-ttu-id="550b7-107">È necessario impostare una stampante di etichette prima di iniziare questa attività.</span><span class="sxs-lookup"><span data-stu-id="550b7-107">You need to set up a label printer before you begin this task.</span></span> <span data-ttu-id="550b7-108">Fare clic su Amministrazione organizzazione > Impostazioni > Stampanti di rete.</span><span class="sxs-lookup"><span data-stu-id="550b7-108">Go to Organization administration > Setup > Network printers.</span></span> <span data-ttu-id="550b7-109">Nel riquadro azioni, fai clic su Opzioni, quindi sul pulsante del programma di installazione dell'agente di distribuzione Scarica documento.</span><span class="sxs-lookup"><span data-stu-id="550b7-109">On the Action Pane, click Options, and then click the Download document routing agent installer button.</span></span> <span data-ttu-id="550b7-110">Eseguire il programma di installazione e assicurarsi di disporre di una stampante di rete operativa impostata su Attiva prima di continuare con la procedura.</span><span class="sxs-lookup"><span data-stu-id="550b7-110">Run the installer and make sure that you have a working network printer set to Active before you continue with the procedure.</span></span>


## <a name="set-up-the-gs1-company-prefix"></a><span data-ttu-id="550b7-111">Imposta il prefisso della società GS1</span><span class="sxs-lookup"><span data-stu-id="550b7-111">Set up the GS1 company prefix</span></span>
1. <span data-ttu-id="550b7-112">Andare **Pannello di navigazione > Moduli > Gestione magazzino > Impostazioni > Parametri di gestione magazzino**.</span><span class="sxs-lookup"><span data-stu-id="550b7-112">Go to **Navigation pane > Modules > Warehouse management > Setup > Warehouse management parameters**.</span></span>
2. <span data-ttu-id="550b7-113">Nel campo **Prefisso società GS1** immettere i 7 numeri per il numero di società GS1.</span><span class="sxs-lookup"><span data-stu-id="550b7-113">In the **GS1 company prefix** field, enter the 7 numbers for your GS1 company number.</span></span>
3. <span data-ttu-id="550b7-114">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="550b7-114">Select **Save**.</span></span>
4. <span data-ttu-id="550b7-115">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="550b7-115">Close the page.</span></span>

## <a name="setup-the-sscc-license-plate-number-sequence"></a><span data-ttu-id="550b7-116">Imposta la sequenza del numero di identificazione SSCC</span><span class="sxs-lookup"><span data-stu-id="550b7-116">Setup the SSCC license plate number sequence</span></span>
1. <span data-ttu-id="550b7-117">Andare a **Pannello di navigazione > Moduli > Amministrazione organizzazione > Sequenze numeriche > Sequenze numeriche**.</span><span class="sxs-lookup"><span data-stu-id="550b7-117">Go to **Navigation pane > Modules > Organization administration > Number sequences > Number sequences**.</span></span>
2. <span data-ttu-id="550b7-118">Selezionare un'opzione nel campo **Area**.</span><span class="sxs-lookup"><span data-stu-id="550b7-118">In the **Area** field, select an option.</span></span>
3. <span data-ttu-id="550b7-119">Selezionare un'opzione nel campo **Riferimento**.</span><span class="sxs-lookup"><span data-stu-id="550b7-119">In the **Reference** field, select an option.</span></span>
4. <span data-ttu-id="550b7-120">Digitare un valore nel campo **Società**.</span><span class="sxs-lookup"><span data-stu-id="550b7-120">In the **Company** field, type a value.</span></span>
5. <span data-ttu-id="550b7-121">Espandere la sezione **Segmenti**.</span><span class="sxs-lookup"><span data-stu-id="550b7-121">Expand the **Segments** section.</span></span>
6. <span data-ttu-id="550b7-122">Selezionare **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="550b7-122">Select **Edit**.</span></span>
7. <span data-ttu-id="550b7-123">Nella tabella **Segmenti**, selezionare la prima riga.</span><span class="sxs-lookup"><span data-stu-id="550b7-123">In the **Segments** table, select the first row</span></span>
8. <span data-ttu-id="550b7-124">Selezione **Rimuovi**.</span><span class="sxs-lookup"><span data-stu-id="550b7-124">Select **Remove**.</span></span>
9. <span data-ttu-id="550b7-125">Selezione **Rimuovi**.</span><span class="sxs-lookup"><span data-stu-id="550b7-125">Select **Remove**.</span></span>
10. <span data-ttu-id="550b7-126">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="550b7-126">Select **Save**.</span></span>
11. <span data-ttu-id="550b7-127">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="550b7-127">Close the page.</span></span>

## <a name="create-the-document-route-layout"></a><span data-ttu-id="550b7-128">Crea il layout di distribuzione dei documenti</span><span class="sxs-lookup"><span data-stu-id="550b7-128">Create the document route layout</span></span>
1. <span data-ttu-id="550b7-129">Andare a **Pannello di navigazione > Moduli > Gestione magazzino > Impostazioni > Distribuzione documenti > Layout distribuzione documenti**.</span><span class="sxs-lookup"><span data-stu-id="550b7-129">Go to **Navigation pane > Modules > Warehouse management > Setup > Document routing > Document routing layouts**.</span></span> <span data-ttu-id="550b7-130">Attiva il layout di SSCC.</span><span class="sxs-lookup"><span data-stu-id="550b7-130">Enable the SSCC layout.</span></span>  
2. <span data-ttu-id="550b7-131">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="550b7-131">Select **New**.</span></span>
3. <span data-ttu-id="550b7-132">Digitare un valore nel campo **ID layout**.</span><span class="sxs-lookup"><span data-stu-id="550b7-132">In the **Layout ID** field, type a value.</span></span>
4. <span data-ttu-id="550b7-133">Digitare un valore nel campo **Descrizione**</span><span class="sxs-lookup"><span data-stu-id="550b7-133">In the **Description** field, type a value.</span></span>
5. <span data-ttu-id="550b7-134">Selezionare **Inserisci al termine del testo**.</span><span class="sxs-lookup"><span data-stu-id="550b7-134">Select **Insert at end of text**.</span></span>
6. <span data-ttu-id="550b7-135">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="550b7-135">Select **Save**.</span></span>
7. <span data-ttu-id="550b7-136">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="550b7-136">Close the page.</span></span>

## <a name="set-up-the-document-routing"></a><span data-ttu-id="550b7-137">Imposta la distribuzione dei documenti</span><span class="sxs-lookup"><span data-stu-id="550b7-137">Set up the document routing</span></span>
1. <span data-ttu-id="550b7-138">Andare a **Pannello di navigazione > Moduli > Gestione magazzino > Impostazioni > Distribuzione documenti > Distribuzione documenti**.</span><span class="sxs-lookup"><span data-stu-id="550b7-138">Go to **Navigation pane > Modules > Warehouse management > Setup > Document routing > Document routing**.</span></span>
2. <span data-ttu-id="550b7-139">Nel campo **Tipo ordine di lavoro** selezionare un'opzione.</span><span class="sxs-lookup"><span data-stu-id="550b7-139">In the **Work order type** field, select an option.</span></span>
3. <span data-ttu-id="550b7-140">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="550b7-140">Select **New**.</span></span>
4. <span data-ttu-id="550b7-141">Digitare un valore nel campo **Magazzino**.</span><span class="sxs-lookup"><span data-stu-id="550b7-141">In the **Warehouse** field, type a value.</span></span>
5. <span data-ttu-id="550b7-142">Digitare un valore nel campo **Nome**.</span><span class="sxs-lookup"><span data-stu-id="550b7-142">In the **Name** field, type a value.</span></span>
6. <span data-ttu-id="550b7-143">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="550b7-143">Select **New**.</span></span>
7. <span data-ttu-id="550b7-144">Nel campo **ID layout**, immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="550b7-144">In the **Layout ID** field, enter or select a value.</span></span>
8. <span data-ttu-id="550b7-145">Nel campo **Nome** selezionare il nome della stampante che si desidera utilizzare.</span><span class="sxs-lookup"><span data-stu-id="550b7-145">In the **Name** field, enter the printer name that you want to use.</span></span>
9. <span data-ttu-id="550b7-146">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="550b7-146">Select **Save**.</span></span>
10. <span data-ttu-id="550b7-147">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="550b7-147">Close the page.</span></span>

## <a name="create-mobile-device-menu"></a><span data-ttu-id="550b7-148">Crea il menu del dispositivo mobile</span><span class="sxs-lookup"><span data-stu-id="550b7-148">Create mobile device menu</span></span>
1. <span data-ttu-id="550b7-149">Andare a **Pannello di navigazione > Moduli > Gestione magazzino > Impostazione > Dispositivo mobile > Voci di menu del dispositivo mobile**.</span><span class="sxs-lookup"><span data-stu-id="550b7-149">Go to **Navigation pane > Modules > Warehouse management > Setup > Mobile device > Mobile device menu items**.</span></span>
2. <span data-ttu-id="550b7-150">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="550b7-150">Select **New**.</span></span>
3. <span data-ttu-id="550b7-151">Digitare un valore nel campo **Nome voce di menu**.</span><span class="sxs-lookup"><span data-stu-id="550b7-151">In the **Menu item name** field, type a value.</span></span>
4. <span data-ttu-id="550b7-152">Digitare un valore nel campo **Titolo**.</span><span class="sxs-lookup"><span data-stu-id="550b7-152">In the **Title** field, type a value.</span></span>
5. <span data-ttu-id="550b7-153">Selezionare un'opzione nel campo **Modalità**.</span><span class="sxs-lookup"><span data-stu-id="550b7-153">In the **Mode** field, select an option.</span></span>
6. <span data-ttu-id="550b7-154">Selezionare **Sì** nel campo **Utilizza lavoro esistente**.</span><span class="sxs-lookup"><span data-stu-id="550b7-154">Select **Yes** in the **Use existing work** field.</span></span>
7. <span data-ttu-id="550b7-155">Selezionare **Sì** nel campo **Genera targa**.</span><span class="sxs-lookup"><span data-stu-id="550b7-155">Select **Yes** in the **Generate license plate** field.</span></span>
8. <span data-ttu-id="550b7-156">Espandere la sezione **Classi di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="550b7-156">Expand the **Work classes** section.</span></span>
9. <span data-ttu-id="550b7-157">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="550b7-157">Select **New**.</span></span>
10. <span data-ttu-id="550b7-158">Nel campo **ID classe lavoro**, digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="550b7-158">In the **Work class ID** field, type a value.</span></span>
11. <span data-ttu-id="550b7-159">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="550b7-159">Select **Save**.</span></span>
12. <span data-ttu-id="550b7-160">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="550b7-160">Close the page.</span></span>
13. <span data-ttu-id="550b7-161">Andare a **Pannello di navigazione > Moduli > Gestione magazzino > Impostazione > Dispositivo mobile > Menu del dispositivo mobile**.</span><span class="sxs-lookup"><span data-stu-id="550b7-161">Go to **navigation pane > Modules > Warehouse management > Setup > Mobile device > Mobile device menu**.</span></span>
14. <span data-ttu-id="550b7-162">Nella struttura selezionare la voce di menu creata prima.</span><span class="sxs-lookup"><span data-stu-id="550b7-162">In the tree, select the menu item that you created before.</span></span>
15. <span data-ttu-id="550b7-163">Selezionare **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="550b7-163">Select **Edit**.</span></span>
16. <span data-ttu-id="550b7-164">Selezionare la freccia per aggiungere la voce di menu al menu.</span><span class="sxs-lookup"><span data-stu-id="550b7-164">Select the arrow to add the menu item to the menu.</span></span>
17. <span data-ttu-id="550b7-165">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="550b7-165">Select **Save**.</span></span>
18. <span data-ttu-id="550b7-166">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="550b7-166">Close the page.</span></span>

## <a name="update-a-work-template"></a><span data-ttu-id="550b7-167">Aggiorna un modello di lavoro</span><span class="sxs-lookup"><span data-stu-id="550b7-167">Update a work template</span></span>
1. <span data-ttu-id="550b7-168">Andare a **Pannello di navigazione > Moduli > Gestione magazzino > Impostazioni > Lavoro > Modelli di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="550b7-168">Go to **Navigation pane > Modules > Warehouse management > Setup > Work > Work templates**.</span></span>
2. <span data-ttu-id="550b7-169">Selezionare **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="550b7-169">Select **Edit**.</span></span>
3. <span data-ttu-id="550b7-170">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="550b7-170">Select **New**.</span></span>
4. <span data-ttu-id="550b7-171">Nel campo **Tipo di lavoro**, selezionare **Stampa**.</span><span class="sxs-lookup"><span data-stu-id="550b7-171">In the **Work type** field, select **Print**.</span></span>
5. <span data-ttu-id="550b7-172">Nel campo **ID classe lavoro** immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="550b7-172">In the **Work class ID** field, enter or select a value.</span></span>
6. <span data-ttu-id="550b7-173">Selezionare **Sposta su**.</span><span class="sxs-lookup"><span data-stu-id="550b7-173">Select **Move up**.</span></span>
7. <span data-ttu-id="550b7-174">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="550b7-174">Select **Save**.</span></span>
8. <span data-ttu-id="550b7-175">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="550b7-175">Close the page.</span></span>

